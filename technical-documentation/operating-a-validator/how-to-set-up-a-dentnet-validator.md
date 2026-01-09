# How to set up a DENTNet Validator?

There are three steps to set up a Validator:

1. Set up a DENTNet Node
2. Create and fund a Stash Account
3. Connect the Stash account with your Node

Please follow the instructions on this page in detail if you want to set up a Validator.

### Set up a DENTNet Node

Follow the instructions to set up a [DENTNet Node](../operating-a-node.md). Please make sure to check the Validator hardware requirements in the documentation.

### Create a Stash Account

Once you see your Node running and registered, create an account on DENTNet. You can do this in our [validator-ui.md](../../tools/validator-ui.md "mention").

Then, deposit the minimum amount of DENTX needed to run a Validator to the created account. DENTNet will bond these funds while running the Validator.

If your Validator fails (e.g. not reachable) to create blocks, funds in the stash wallet can be slashed, and you might lose some of your funds.

### Find the Keys of your Node

Connect to your machine where the DENTNet Node is operating. Run this command in your terminal to access the keys:

```sh
curl -H "Content-Type: application/json" -d  \
'{"id":1, "jsonrpc":"2.0", "method": "author_rotateKeys", "params":[]}'  \
http://localhost:19944
```

The output of the command should be like this:

```json
{"jsonrpc":"2.0","result":"0x36e56b7e38512487c5dc24a7c705f665efbd9b1efbd53b8cf61bedef20e81fdaa8db5935e95f594cce269e7ca0e60b6133cbe9d22dff0c3ba67310742eab6d18ea766b75ff75e339e700497b10b8a7b4a71465ebe80a8c938668eabe642a4c2a06e98d0433eeac4e9c106e8dbd84341d43da42f9bf381a928e8eef61b13e0c64","id":1}
```

This value in "result" is your **Author Key** and is needed to connect your **Stash Account** with your machine in the next step.

### Enable Validator Mode of your Node

Update the `docker-compose.yml` of your node and uncomment or add the `validator` option in the `command:` section

```
    ...
    - "--rpc-cors=all"
    - "--rpc-methods=unsafe"
    - "--validator"
```

&#x20;Then restart your the node using

```
docker compose up -d
```

### Register your Node as a Validator

Open the [Validator UI](../../tools/validator-ui.md), go to Staking => Accounts, and make sure your wallet is connected.

<figure><img src="../../assets/Screenshot 2024-01-22 at 10.14.47.png" alt="" width="125"><figcaption></figcaption></figure>

Press the "+ Validator" button in the UI to open the "Setup Validator" sheet.&#x20;

Select your Stash Account in the "stash account" field.&#x20;

Please be aware that you can stop running a Validator anytime in the Validator UI, but **your funds are locked** for some time after you stop the validation. You can find the exact bonding duration in the Validator UI.

Select your payment destination. It can be the stash account or another account.&#x20;

Enter the author keys you extracted from your Node following this section to [#find-the-keys-of-your-node](how-to-set-up-a-dentnet-validator.md#find-the-keys-of-your-node "mention").&#x20;

Set the commission to **10** and allow nominations, as shown in the screenshot.&#x20;

The stash account can set the commission percentage. The commission defines how much rewards are distributed directly to the Validator. The rest of the rewards will be distributed to all stakers using the nomination pool.&#x20;

<figure><img src="../../assets/Screenshot 2024-01-31 at 08.54.19.png" alt=""><figcaption></figcaption></figure>

If a Validator operator changes the commission from 10% to another value, pool operators can remove this Validator from their nomination pools. As a consequence, this Validator will have less stake and will receive fewer rewards.

Finalize the setup by clicking "Bond & Validate" and signing the transaction.
