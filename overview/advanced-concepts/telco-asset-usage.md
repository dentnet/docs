# Telco Asset Usage

Depending on the type of asset and units (like voice minutes or data bytes), real-time usage will be tracked in a corresponding off-chain, "layer 2" type of system (or OCS in telecommunications terminology).

Usage is regularly synchronized to the DENTNet main network by "rolling up" the amount of used data/minutes/etc. and sending the cumulative value.&#x20;

DENTNet supports batched writes where operators can synchronize multiple telco asset packages in one extrinsic.

Usage tracking is handled by the vending pallet, where the telco asset is locked for sale/transfer while it's in use.&#x20;

DENTNet supports reading balances and expiry directly on-chain.
