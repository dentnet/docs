# Swap DENT on DENTNet

DENTNet allows the swapping of bridged DENT tokens for DENTX.&#x20;

The DENT tokens need to already be in a DENTNet wallet, to which the swapped DENTX will be credited.

The normal network fees (gas) apply for a transaction, however for swapping there is a special arrangement depending on the status of the wallet:

* If there are DENTX funds in the wallet, the fee will be deducted in DENTX directly as usual.
* If there is no DENTX available in the wallet (such as a wallet that has been funded with only DENT via the bridge), the DENT will be swapped to DENTX and the fee will be deducted during the swap operation and the remaining DENTX will be added to the wallet.

The swap ratio is a fixed rate defined by DENTNet and may change over time, however you will always see what the rate and expected network fee is before performing a swap.

DENT is a token with a fixed supply. In contrast, DENTX has a variable supply to enable the use of [proof-of-stake](../../core-concepts/proof-of-stake/ "mention") consensus algorithm. DENTNet is not offering a swap of DENTX for DENT.

{% hint style="warning" %}
Swap from DENTX to DENT is not available on DENTNet.&#x20;
{% endhint %}

Swapped DENT tokens are stored in a wallet within DENTNet and can be transferred to the circulating supply of the DENT App.
