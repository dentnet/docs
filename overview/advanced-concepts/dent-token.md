# DENT Token

The DENT token is the core of the DENT Wireless mobile data ecosystem. It allows a worldwide marketplace of telecommunication assets on DENTNet. Operators (or Service Providers) can offer telecommunication assets and users can purchase these assets.

### Offering Assets

Operators can use the DENT token to sell telecommunication assets like mobile data and voice minutes on DENTNet. The Vending pallet provides the interface to offer these assets. An offer contains the details of the packages to be bought. For voice packages, these are the number of minutes, the supported countries to call, the duration until the package expires once activated, and more. Finally, also the price in DENT is set here. Offering an asset on DENTNet using the Vending pallet is an extrinsic and DENTX needs to be paid by the offering party.&#x20;

### Purchase of Assets

Using the Vending pallet [accounts](../core-concepts/accounts.md) on DENTNet can get [voice minutes](telecommunication-assets/voice-minutes.md) in exchange for DENT tokens. These DENT tokens need to be on the account before the purchase. DENTNet supports the purchase of these assets from any operator, as long as the account has enough DENT tokens to pay the given price for the asset and DENTX for the fees of the transactions.&#x20;

Using the concept of [operator-sponsorship.md](operator-sponsorship.md "mention"), the fees can be paid by the operator that is sponsoring the account.

Once the asset is sold from the operator to the account, the operator receives the DENT tokens.

### DENT Deposit

DENT can be deposited from one DENTNet account to another using the **transfer** method of the **Asset** pallet.

DENTs can be also deposited from ERC20 wallets to DENTNet using the [DENTNet Bridge](../../tools/wallets/polkadotjs.md).&#x20;

{% hint style="info" %}
&#x20;The total supply of the DENT token is 100B and will not change.
{% endhint %}

### Fiat Purchases of Telecommunication Assets

When subscribers are buying mobile data from operators using fiat payment methods, the equivalent in DENT tokens for the asset purchase can be disbursed by the operator. In this case, DENT are transferred from an operator account to the subscriber account before initiating the asset purchase. Once the purchase of the asset is completed, the operator will get the DENT back to their vending account. Operators need to fund their accounts with DENT tokens upfront to have liquidity for parallel purchases of their subscribers.
