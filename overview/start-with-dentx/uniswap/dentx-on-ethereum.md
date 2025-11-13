# DENTX on Ethereum

In June 2024, DENT introduced the ERC20 version of DENTX for the purpose of allowing swapping assets like ETH for DENTX on Uniswap.

{% hint style="info" %}
DENTX's Ethereum/ERC20 contract address is **0xd65981da8d0bc8ef308d81c2b4955b0781fcdbfb**. \
Always use this contract address when interacting with DENTX on Ethereum.
{% endhint %}

Utilizing this smart contract, DENTX can be moved between Ethereum and DENTNet and vice versa using the [bridge](../../../tools/bridge/ "mention").&#x20;

DENTX on Ethereum is an ERC20 with a variable supply, reflecting all DENTX moved from DENTNet to Ethereum.

For example, if 10 DENTX are moved from DENTNet to Ethereum, the total supply of the ERC20 will increase by 10 DENTX. These 10 DENTX will be locked on the DENTNet side (inactive issuance).&#x20;

If 5 DENTX are moved from Ethereum to DENTNet, the total supply of the ERC20 will decrease by 5 DENTX.&#x20;

The total supply of the DENTX token is always defined by the total supply value on DENTNet.
