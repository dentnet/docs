# Fees

As on any other blockchain network, storage and computation resources are limited. Transaction fees prevent individual parties from consuming too many resources.&#x20;

DENTNet uses the Substrate weight-based fee model. Fees are charged prior to transaction execution and once the fee is paid, nodes will execute the transaction.

### Fee Calculation

Block producers charge a fee to be economically sustainable. That fee must always be covered by the sender of the transaction.&#x20;

Transaction volume on blockchains is highly irregular, and therefore transaction fees need a mechanism to adjust. However, users should be able to predict transaction fees.

DENTNet uses an established fee mechanism with tips to address these two points.&#x20;

DENTNet fees consist of three parts:

1. **Base fee**: a fixed fee that is applied to every transaction and set by the runtime.
2. **Length fee**: a fee that gets multiplied by the length of the transaction, in bytes.
3. **Weight fee**: a varying fee for each runtime function based on its weight (which can be thought of as a measure of how much CPU time is used on the network).

The DENTNet Runtime defines the following values:

* Base fee: 0.01 DENTX
* Length fee: 0.0001 DENTX per byte

The weight to fee conversion on DENTNet is modeled to be roughly 0.01 DENTX per unit weight. The unit weight is the weight used by an empty (no-op) extrinsic and defined as 124,414,000. The empty extrinsic would then have weight fee 0.01 DENTX.

```
weight_fee = 0.01 DENTX * (weight / 124,414,000)
```

Using the above, some typical transaction fees on DENTNet are:

* Simple balance transfer: 0.04 DENTX
* Swap DENT token: 0.09 DENTX
* Transfer DENT token: 0.07 DENTX
* Issuing a mobile data package: 0.17 DENTX

#### Fee Multiplier <a href="#fee-multiplier" id="fee-multiplier"></a>

Substrate supports an additional fee for transactions if the network becomes too busy and starts to decelerate the system. This fee can create an incentive to avoid the production of low-priority or insignificant transactions. In contrast, those additional fees will decrease if the network calms down and can execute transactions without much difficulty.

This is also implemented on DENTNet as Fee Multiplier

```
final_fee = fee * fee_multiplier
```

The fee\_multiplier is based on how full blocks are and vary over time using a complex formula. For more information see [Adjustment of fees over time](https://research.web3.foundation/Polkadot/overview/token-economics#adjustment-of-fees-over-time).
