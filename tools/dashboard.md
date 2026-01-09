# Dashboard

[https://main.dentnet.io/dashboard/](Link to DENTNet Dashboard)

The DENTNet Dashboard provides users with a web application to participate in the DENTNet staking ecosystem. Whether you're looking to stake your DENTX, track rewards, or swap your DENT token to DENTX, this section will walk you through the key features and functionalities of the dashboard.

### **Connect Wallet**

First connect a supported DENTNet wallet app, such as the [vault-app.md](wallets/vault-app.md "mention") or the [polkadotjs.md](wallets/polkadotjs.md "mention"). Once the Staking Dashboard is connected, it allows you to access DENTX and DENT tokens, and participate in staking.

#### **How to use**

To connect your wallet, go to the top right of the screen, click "**Connect**", and follow the prompts to connect your wallet with the dashboard.&#x20;

<figure><img src="../assets/Screenshot 2024-02-02 at 16.18.47.png" alt="" width="161"><figcaption></figcaption></figure>

Please also refer to the documentation of the wallet app you are using to initiate the connection with the Staking Dashboard.

### **"Overview" Section**

The overview section gives users a snapshot of essential metrics and statistics related to the DENTNet staking ecosystem.

#### How to Use

Ensure your wallet is connected and click "**Overview**" on the sidebar. You can now check the following metrics:

* **Historical rewards rate:** All-time rate of rewards gained against staked DENTX.
* **DENTX supply staked:** Amount of DENTX currently staked.
* Time remaining of the era
* **DENTX balance:** Amount of DENTX you are staking and the amount of DENTX you have free(free and staking)
* **Recent payouts:** Daily chart of your payouts for the last 30 days.
* **Network stats:** See relevant statistics of DENTNet

Be aware that the overview section is only for viewing purposes. You cannot take any action in this section.

### **"Staking" Section**

Staking makes you get rewards by adding your DENTX to a staking pool. Read the  [staking.md](../overview/core-concepts/proof-of-stake/staking.md "mention") section for more details on how staking works at DENTNet.

#### How to use

First, ensure your wallet is connected. Then click **Staking** on the sidebar.

To start staking, find the "**Pool Membership**" card and click "**Join**". Then, type the amount of DENTX you want to add to the pool and click "**Submit**." A prompt from your wallet app will appear. Sign and approve the transaction to finish the process. If the prompt does not appear, go to your wallet app and sign the transaction there.

When joining a pool, your funds are **bonded to this pool**.&#x20;

If you want to unbond funds, a locking period of **7 eras (days)** applies before you can withdraw it.

Once the transaction has been successful, you will see an updated version of the screen with the following information:

#### **Bonded funds**

This shows how many DENTX you have in pools and how many you have free. You can increase and decrease your bonded funds and see funds locked in the bonding period.&#x20;

* **Increase bonded funds:** You can increase your bonded funds using the "**+**" buttons and enter the amount of DENTX you want to add. To change your bonded funds, you must sign the transaction in your wallet app.
* **Remove bonded funds:** Click the "**-**" buttons and enter the amount of DENTX you want to remove. To change your bonded funds, you must sign the transaction in your wallet app. After removing your bonded funds, the bonding period will apply and your funds will be locked. Click "**Unlock**" button to see an overview of the rewards you will get after the era is unlocked and when the rewards will be available.

<figure><img src="../assets/Screenshot 2024-02-05 at 14.36.57.png" alt="" width="81"><figcaption><p>Unlock Button</p></figcaption></figure>

* **Withdraw unbonded funds:** If the bonding period is over, use the "Unlock" icon to withdraw the funds back to your wallet. You must sign the withdrawal transaction in your wallet app.

#### **Pool membership**

You can see the pool name you are staking, its status, and manage your pool membership. Click "**Manage**" to leave a pool and stop receiving rewards or change who can claim your rewards on your behalf.

#### **Unclaimed rewards**

You can see the unclaimed rewards you have. Click on "**Withdraw**" to make your rewards available in your wallet. Click on "**Compound**" to claim the rewards and stake them in the same pool to earn more. To compound your rewards, you must sign the transaction in your wallet app.

You can also see the following helpful information in the Staking section:

* **Members in pool:** See the number of people staking in the pool. With the launch of DENTNet, the DENT pool will be available.
* **Minimum to join pool**: Check the minimum amount of DENTX required to join a pool.
* **Pool stats**: You can see the status of the pool, the number of members in the pool, total bonded bunds, and the latest claimed rewards.

### **"Payouts" Section**

This section provides historical information on the rewards given to your account.

#### How to use

Ensure your wallet is connected and click "**Payouts**" on the sidebar. You can now check the following information:

* **Last era payout**: See the total rewards given away in the previous era.
* **Payout history**: Explore a chart of your daily payouts in the last 30 days and the 10-day average.
* **Recent payouts**: See the transactions of your recent payouts. Click on the payout to go to [explorer.md](explorer.md "mention") and see the transaction details.

### **"DENT to DENTX" Section**&#x20;

The "**DENT to DENTX**" feature allows you to swap your DENT tokens within DENTNet for DENTX.

The swap ratio is a fixed rate defined by DENTNet and may change over time. More background information about the swap is available in the [swap-dent-on-dentnet.md](../overview/start-with-dentx/swap-on-dentnet/swap-dent-on-dentnet.md "mention") section.

#### **How to use**

Ensure your wallet is connected and click "**DENT to DENTX**" on the sidebar. Once connected, the swap section will display helpful information for swapping your DENT tokens to DENTX:

* **DENTX balance:** Check the amount of DENTX you have in your connected DENTNet wallet.
* **DENT tokens balance:** Check the amount of DENT Tokens you have in your connected DENTNet wallet.
* **Swap preview:** See the DENTX you will get for the DENT tokens you enter.
* **Recent swaps:** See your recent swaps of your recent payouts. Click on a swap to go to [DENTNet Explorer](#user-content-fn-1)[^1] and see the transaction details.

Now you are ready to swap.&#x20;

Be aware that you can only swap DENT Tokens that are on a DENTNet wallet. If you still have DENTs on an Ethereum wallet, you can use the [bridge](bridge/ "mention") to transfer your DENTs to DENTNet.

To start swapping, type the number of DENT tokens you want to swap on the "**Amount to swap**" input field. You can only enter as many DENT tokens as you have in your connected wallet. By entering an amount, you will see a "**Swap preview**" on the right side of the input field, including the amount of DENTX you will receive, the fee, and the route. If satisfied with the result, click the "**Swap Now**" button below the input field. A prompt will appear for you to confirm the swap.

_Please note that the swap cannot be reversed once executed, and there is no way to swap DENTX back to DENT tokens._

Click on "**Confirm**" to process the transaction. On a successful transaction, the prompt will show you the status of the swap, DENTX you received, the fees you paid, and a link to view the transaction on [explorer.md](explorer.md "mention").&#x20;

If the transaction fails, you will still have to pay a fee for processing the swap. The prompt will display the status and the charged fees.&#x20;

Close the prompt to see your updated DENTX and DENT Tokens balance.



[^1]: 
