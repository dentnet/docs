# Validator UI

The Validator UI is based on PolkadotJS. It can be accessed at [https://main.dentnet.io/polkadotjs](https://main.dentnet.io/polkadotjs).

This section contains information on how to create an account and connect a node with an account to register as a Validator.

We recommend using:

* Most up-to-date version of Google Chrome
* [vault-app.md](wallets/vault-app.md "mention") to connect with external key storage
* PC or Mac with a webcam attached or integrated

Detailed information about the PolkadotJS software is available here: [https://polkadot.js.org/docs/](https://polkadot.js.org/docs/).&#x20;

### Creating accounts

To register as a Validator, a Stash Account is needed. Follow these steps to create accounts in the Validator UI:

1. To create accounts, you can use the [vault-app.md](wallets/vault-app.md "mention") to create a (derived) key. When you tap on the new key in the app, a QR will be shown on your device.
2. Now switch to your computer and open the **"Accounts"** section of the Validator UI by visiting  [https://main.dentnet.io/polkadotjs/#/accounts](https://main.dentnet.io/polkadotjs/#/accounts).
3. Click on the "From QR" button and scan the QR code that appeared on your phone. Choose a name for the account and click "Save".&#x20;

<figure><img src="../assets/Screenshot 2024-01-31 at 15.48.24.png" alt=""><figcaption></figcaption></figure>

Now you can see the account listed under the "via qr" section.

<figure><img src="../assets/Screenshot 2024-01-31 at 15.49.01.png" alt=""><figcaption></figcaption></figure>

If you click on your account, you can copy the address to receive DENTX or look up transactions in the [explorer.md](explorer.md "mention").

### Register as a Validator

Open the UI, and make sure your Stash account is connected (listed in the "via qr" section). Open the section "**Staking**" and select the "**Accounts**" tab or use this link [https://main.dentnet.io/polkadotjs/#/staking/actions](https://main.dentnet.io/polkadotjs/#/staking/actions).

<figure><img src="../assets/Screenshot 2024-01-22 at 10.14.47.png" alt="" width="125"><figcaption></figcaption></figure>

Press the "**+ Validator**" button in the UI to open the "**Setup Validator**" sheet.

<figure><img src="../assets/Screenshot 2024-01-31 at 16.41.31 (1).png" alt=""><figcaption></figcaption></figure>

Select your Stash account in the "stash account" field.&#x20;

Please be aware that you can stop running a Validator anytime in the Validator UI, but **your funds are locked** for some time after you stop the validation. You can find the exact bonding duration in the Validator UI.

Select your payment destination. It can be the stash account or another account.&#x20;

Click the "**next**" button to continue to the next screen.

Enter the author keys you extracted from your Node following this section to [#find-the-keys-of-your-node](validator-ui.md#find-the-keys-of-your-node "mention").&#x20;

Set the commission to **10** and allow nominations, as shown in the screenshot.&#x20;

The stash account can set the commission percentage. The commission defines how much rewards are distributed directly to the Validator. The rest of the rewards will be distributed to all stakers using the nomination pool.&#x20;

<figure><img src="../assets/Screenshot 2024-01-31 at 08.54.19.png" alt=""><figcaption></figcaption></figure>

If a Validator operator changes the commission from 10% to another value, pool operators can remove this Validator from their nomination pools. As a consequence, this Validator will have less stake and will receive fewer rewards.

Finalize the setup by clicking "Bond & Validate". Then sign the transaction.

### Signing Transactions

To sign a transaction, click on "Sign via Qr". Open the "**Vault**" app on your mobile device and and tap on the scan button (the red circled button on the bottom of the home screen).
