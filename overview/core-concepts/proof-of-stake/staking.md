# Staking

DENTNet allows the staking of DENTX. Each holder of DENTX can stake their DENTX and will get rewarded for locking the token.

### Staking Implementation

The core of DENTNet uses Nominated Proof-Of-Stake. Staked funds and Validators are connected as each staked DENTX is assigned to one or more Validators. This logic allows DENTNet to connect different user groups to different Validators, like subscribers to Validators of their mobile operator.

The connection between staked funds and Validators is established via nomination pools. Each nomination pool contains a list of Validators. Funds bonded to a nomination pool receive staking rewards based on the performance of the Validators in the pool.&#x20;

A nomination pool operated by the [technical-committee.md](../../advanced-concepts/technical-committee.md "mention") is available with the launch of DENTNet. It contains the set of Validators operated by launch partners. See also the [validators.md](validators.md "mention") section for more details.

### Rewards and Inflation

DENTNet uses an inflation model with the target of locking in **50%** of the issued DENTX.&#x20;

Based on the current staking ratio (DENTX staked / DENTX issued), the reward rate and inflation rate are calculated to attract more funds or stabilize the amount of funds locked.&#x20;

DENTNet targets an amount at stake of **50%** of the issued DENTX. When this is reached, the network will optimize for a **10%** inflation rate and a 20% staking reward rate.

This table shows the **approximate** staking reward and inflation rates based on the staking rate.

These values are **targets** that DENTNet algorithms try to achieve. **They are not guaranteed.**&#x20;


| Staking ratio | Staking reward rate | Inflation rate |
| ------------- | ------------------- | -------------- |
| 10 %          | 40 %                | 4 %            |
| 20 %          | 27.5 %              | 5.5 %          |
| 30 %          | 23.3 %              | 6.99 %         |
| 40 %          | 21.5 %              | 8.6 %          |
| **50 %**      | **20 %**            | **10 %**       |
| 52.2 %        | 15.4 %              | 8.03 %         |
| 60 %          | 13 %                | 7.8 %          |

### Locking

DENTX funds on stake can be unbonded at any time and are locked for 7 days after unbonding. After the locking period, the DENTX can be transferred from the wallet. You can see your account's locking periods and status in the [dashboard.md](../../../tools/dashboard.md "mention"). See also [#locking](../accounts.md#locking "mention") in the [accounts.md](../accounts.md "mention") section.

### Payout

Stakers receive staking rewards in the form of DENTX.

The payout needs to be requested. You can request payouts using the [dashboard.md](../../../tools/dashboard.md "mention").&#x20;

If not requested, payouts **expire** after 84 days.

Please visit your Staking Dashboard regularly to don't miss your rewards.

