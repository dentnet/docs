# Treasury

The Treasury is a pot of funds collected through a portion of block production rewards, transaction fees, slashing, and staking inefficiencies.

Tokens that are deposited into the Treasury (i.e. the **inflow**) are determined by the following mechanisms:

* **Transaction fees:** 80% of the transaction fees of every submitted extrinsic is diverted to the Treasury, while 20% is given to the block producers.
* **Staking inefficiencies:** the network tries to reach the ideal staking rate, see [staking.md](proof-of-stake/staking.md "mention"). The Annual Percentage Yield (APY) for stakers (nominators & validators) decreases whenever the actual staking rate is not equal to the ideal staking rate. To keep inflation within given boundaries, the system does not create fewer tokens. Instead, some share of the overall reward for stakers is moved to the Treasury.
* **Slashes:** whenever validators and nominators are slashed, a share of the slashed tokens is diverted to the Treasury. These are typically rare and unpredictable events.
* **Transfers:** everyone can send funds to the Treasury directly. This is a rare event and should not occur normally.

The outflow is determined by the following mechanisms:

* **Burned tokens:** at the end of each spend period 1% of the available funds are burned.
* **Investments in infrastructure:** will be used to invest in the development and expansion of the DENT infrastructure such as operator integrations, extending local breakouts, improved countries rates, etc.
* **Investments in ecosystem growth:** will be used to support the ecosystem growth with marketing and sales activities.
