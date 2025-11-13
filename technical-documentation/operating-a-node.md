# Operating a Node

This section contains information on how to set up a DENTNet node. DENT Wireless will provide these values for setup to chosen DENTNet node and Validator operators:

* SPEC\_URL\_PROVIDED\_BY\_DENT
* DOCKER\_URL\_PROVIDED\_BY\_DENT
* SYNC\_URL\_PROVIDED\_BY\_DENT
* DOCKER\_PW\_PROVIDED\_BY\_DENT

### Install docker

First, go to [https://docs.docker.com/engine/install/](https://docs.docker.com/engine/install/), choose your platform, and follow the instructions to install Docker on your computer or server.&#x20;

{% hint style="info" %}
If you are unfamiliar with Docker, please check the documentation and available videos, e.g., on [https://docs.docker.com/](https://docs.docker.com/).
{% endhint %}

### Adjust Power Management

If you are set up on a personal computer, make sure to disable sleep and automatic shutdown.

### Set up Installation

Create a directory for all DENTNet files and download the DENTNet spec file and docker compose yaml file you received from DENT.

```
mkdir dentnet-mainnet
cd dentnet-mainnet

curl -o docker-compose.yml <DOCKER_URL_PROVIDED_BY_DENT>
curl -o dentnet_live_spec_raw.json <SPEC_URL_PROVIDED_BY_DENT>
```

Open **port 30333 on your firewall** and forward it to your docker server. The DENTNet Node allows connections from other nodes to build the peer-to-peer network through this port.

{% hint style="warning" %}
**Only** open port **30333** to the **public.**\
**Only** access your node **locally** using **RPC** on port 19944.
{% endhint %}

Create a directory for the chain data.

```
mkdir -p ./data1/chains/dentnet/
```

To get synced up faster download the snapshot provided by DENT. This step can be skipped if you want to let the node sync by itself. Depending on the network speed full sync from 0 might take a few days.

```
curl -o - -L <SYNC_URL_PROVIDED_BY_DENT> | tar -xvf - -C ./data1/chains/dentnet/
```

On Linux machines, please update the access rights for the downloaded data.

```
chown -R 101:101 ./data1
```

### Pull the Binary Image

```
docker login -u dentnet
```

Paste the password provided by DENT (DOCKER\_PW\_PROVIDED\_BY\_DENT).

```
docker compose pull
```

### Start the DENTNet Node

```
docker compose up -d
```

To view the logs of your node you can use this command:

```
docker compose logs -f 
```

or

```
docker compose logs -f --tail=20
```

to avoid scrolling through all the logs.

A usual output looks like

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

If your node is synced, you see this output normally.

### Get Your Node ID

```sh
curl -H "Content-Type: application/json" -d \
'{"id":1, "jsonrpc":"2.0", "method": "system_localPeerId"}' \
http://localhost:19944/
```

Check the port number from the ports mapping in the docker-compose.yml. You should be able to see your node in the web interface: [https://rpc.dentnet.io/apps/#/explorer/node](https://rpc.dentnet.io/apps/#/explorer/node).

### Hardware

The minimum recommended hardware for running a node is

* Intel i5 or AMD equivalent
* 16GB RAM
* 1TB disk space

If you intend to [operate a Validator](operating-a-validator/) on this node, please use:

* Intel i7 (or AMD equivalent) or higher
* 4 physical cores @ 3.4GHz or faster
* 32 GB RAM
* 1 TB SSD

