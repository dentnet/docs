# Operator Sponsorship

To interact with a blockchain, normally you need to pay a transaction fee (sometimes called gas or gas fee). On DENTNet the native unit used to pay fees is DENTX, whereas DENT is the token used to purchase mobile data, voice minutes etc.&#x20;

Most subscribers that only interact with DENTNet through their operator do not have (or desire) a DENTX balance. To solve this, DENTNet supports a feature called Operator Sponsorship. This enables an operator to designate the wallet of a user as sponsored and offer to pay all the related network fees for it.

{% hint style="info" %}
The DENT App is an example of using Operator Sponsorship. In this case, DENT sponsors transaction fees for the DENT App users.
{% endhint %}

This is accomplished through a custom pallet called Sponsor which is wholly integrated into the DENTNet fee charging mechanism. If a wallet is marked as sponsored, any fees for it will be charged to the sponsor, allowing the user to interact with DENTNet without having a DENTX balance.
