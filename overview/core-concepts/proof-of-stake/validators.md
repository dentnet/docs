# Validators

### Role of Validators

Validators have a core function on DENTNet. They create blocks, and each Validator earns rewards for this work.

DENTNet runs a carefully selected set of Validators operated by launch partners and DENT Wireless.

{% hint style="info" %}
For operating a Validator, please read our **technical** documentation [operating-a-validator](../../../technical-documentation/operating-a-validator/ "mention").&#x20;
{% endhint %}

### Validator Rewards

Validators who produce blocks are rewarded with DENTX. Rewards are a combination of **block creation rewards** and **validator staking rewards**.

Validators can earn **era points** during each era by doing different tasks for block creation on DENTNet. Simply said, every block a Validator calculates, gives era points. The more points, the higher the reward for a specific era. This logic promotes the Validators' activity. The distribution of the rewards is proportional to all Validators based on the era points.

Thus, having more stake in a Validator does not influence the amount of **block creation rewards** it receives.  There is a probabilistic component in the calculation of rewards, so they may not be exactly equal for all validators.

In addition, DENTNet calculates the **validator staking reward** for the validators. Validators are bonding DENTX on DENTNet. Based on the total amount staked on DENTNet, the era points, and the bonded DENTX, the Validator will receive **validator staking rewards.**

Block creation rewards and validator staking rewards are summed up and provided as a payout for the Validator.

### Validator Payouts

Validators receive rewards in the form of DENTX. The payout differs for the type of rewards:

1. Block creation rewards - are paid out **immediately** when the block is created
2. Staking rewards - are paid out **daily**

Rewards are paid out to the stash account.

### Slashing <a href="#slashing" id="slashing"></a>

Slashing will happen if a Validator misbehaves (e.g. goes offline, attacks the network, or runs modified software) in the network. They will get slashed by losing a percentage of their bonded/staked DENTX.

### Validator Slots

DENTNet has a maximum amount of active validators. Active Validators perform block creation and earn era points. Inactive Validators wait to be selected as active. The selection is based on the stake and is performed daily.&#x20;

This means Validators with more funds bonded have a higher chance of being selected and earning rewards. You can add more DENTX to your Validator bond anytime to avoid being not selected.

{% hint style="info" %}
The current number of Validator slots is **20**.
{% endhint %}



