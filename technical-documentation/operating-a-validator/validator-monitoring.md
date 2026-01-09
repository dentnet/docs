# Validator Monitoring

DENTNet supports [Prometheus](https://prometheus.io) to monitor the performance of your validator nodes.

You can follow these steps to set up your monitoring, incl. [Grafana](https://grafana.com) or use an individual setup.

This document is an **example** of how to set up monitoring. Please perform your setup based on your network structure and security setup.

### Set up a dedicated monitoring machine

The monitoring should run on a machine different from your node. The monitoring machine will access the node on port **9615** to fetch the current status.&#x20;

Make sure your network and firewall setup allows this communication.

We strongly recommend opening up port 9615 only between your monitoring machine and your node.&#x20;

### Enable Prometheus port on the DENTNet node(s)

Connect to each of **your DENTNet nodes** you want to monito&#x72;**,** find your docker-compose.yml, and edit it:

Add a new mapping in the `ports:` section

```
- "9615:9615"
```

Add the lines to the `command:` section

```
- "--prometheus-external"
- "--prometheus-port=9615"
```

Save the file and restart the docker for the new settings to take effect.

```
docker-compose up -d
```

### Download Prometheus and Alertmanager

First, connect to your **monitoring machine**.

Download **Prometheus** at [https://prometheus.io/download/](https://prometheus.io/download/) and untar using

```
tar xvfz prometheus-*.tar.gz
```

Download **Alertmanager** from [https://prometheus.io/download/](https://prometheus.io/download/) and untar using

```
tar xvfz alertmanager-*.tar.gz
```

### Edit Prometheus Configuration

Create the Prometheus config directory

```
mkdir /etc/prometheus
```

Create a file at `/etc/prometheus/rules.yml` to set up how you will be alerted. Add this sample content or modify it as needed:

```yaml
groups:
  - name: alert_rules
    rules:
      - alert: InstanceDown
        expr: up == 0
        for: 5m
        labels:
          severity: critical
        annotations:
          summary: "Instance [{{ $labels.instance }}] down"
          description: "[{{ $labels.instance }}] of job [{{ $labels.job }}] has been down for more than 5 minutes."
```

Next, create a file at `/etc/prometheus/prometheus.yml`.

Ensure you enter your nodes' correct IPs in the last line of the file ("targets").

<pre class="language-yaml" data-title="prometheus.yml"><code class="lang-yaml">global:
  scrape_interval: 15s
  scrape_timeout: 10s
  evaluation_interval: 15s
alerting:
  alertmanagers:
  - static_configs:
    - targets: [127.0.0.1:9093]
    scheme: http
    timeout: 10s
    api_version: v2
rule_files:
  - '/etc/prometheus/rules.yml'
scrape_configs:
- job_name: prometheus
  honor_timestamps: true
  scrape_interval: 15s
  scrape_timeout: 10s
  metrics_path: /metrics
  scheme: http
  static_configs:
  - targets:
    - localhost:9090
- job_name: "substrate_node"
  scrape_interval: 5s
  static_configs:
  - targets: ["<a data-footnote-ref href="#user-content-fn-1">&#x3C;your_node_ip_1></a>:9615", "&#x3C;<a data-footnote-ref href="#user-content-fn-2">your_node_ip_2</a>>:9615"]
</code></pre>

### Edit Alertmanager Configuration

Create the Alertmanager config directory

```
mkdir /etc/alertmanager
```

Create a configuration file named `alertmanager.yml` under /etc/alertmanager. Edit `alermanager.yml` to fit your needs.

An example file with SMTP email alerts

```
global:
 resolve_timeout: 1m

route:
 receiver: 'smtp-notifications'

receivers:
- name: 'smtp-notifications'
  email_configs:
  - to: my-email@example.com
    from: alerts@example.com
    smarthost: smtp.example.com:587
    auth_username: my-user
    auth_password: my-password
    send_resolved: true
```

### Start Prometheus and Alertmanager

Start Alertmanager and Prometheus, e.g. by entering

<pre><code><strong># change to alertmanager directory
</strong><strong>./alertmanager --config.file=/etc/alertmanager/alertmanager.yml &#x26;
</strong></code></pre>

```
# change to prometheus directory
./prometheus --config.file=/etc/prometheus/prometheus.yml &
```

You can check the output for error messages to make sure your setup is working.

### Add Grafana

Follow the instructions to download and install **Grafana** at [https://grafana.com/docs/grafana/latest/setup-grafana/installation/](https://grafana.com/docs/grafana/latest/setup-grafana/installation/)&#x20;

In your Grafana installation add the data source for your Prometheus instance, e.g. by adding a datasource.yml file:

```
vi /etc/grafana/provisioning/datasources/datasource.yml
```

Insert the needed settings:

```yaml
apiVersion: 1

datasources:
- name: Prometheus
  type: prometheus
  url: http://localhost:9090
  isDefault: true
  access: proxy
  editable: true
```

Finally, restart Grafana on your monitoring machine.

### Open Grafana in Browser

Open the Grafana web interface using your monitoring machine address and the Grafana port, such as `http://localhost:3000` . The default username and password are `admin/admin.`

### Add a Dashboard&#x20;

Create a new dashboard by using the **Import** function and this URL `https://grafana.com/grafana/dashboards/13759-substrate-node-template-metrics/`\
and your Prometheus data source from the dropdown.

You can now see the stats of your validator(s) on Grafana and you will be alerted via email if an instance is down.

[^1]: Replace with the (internal) IPs of your node.&#x20;

[^2]: Add multiple nodes if you want to monitor more than one node.
