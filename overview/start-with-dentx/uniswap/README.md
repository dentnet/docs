# Uniswap

Assets like ETH, DAI, or DENT can be swapped for DENTX using the Uniswap Protocol. As the Uniswap protocol is unavailable on DENTNet, the swap is provided on Ethereum. Read the [dentx-on-ethereum.md](dentx-on-ethereum.md "mention") section and double-check the contract address when interacting with DENTX on Ethereum.&#x20;

{% hint style="warning" %}
Make sure to only use the Uniswap swap at the address

[https://app.uniswap.org/swap?outputCurrency=0xd65981da8d0bc8ef308d81c2b4955b0781fcdbfb](https://app.uniswap.org/swap?outputCurrency=0xd65981da8d0bc8ef308d81c2b4955b0781fcdbfb)

&#x20;and always double-check the token contract address.
{% endhint %}

To use your Uniswap to get DENTX on DENTNet, you need to follow these steps:

1. [Swap assets to DENTX using Uniswap](./#id-1.-swap)
2. [Create an account on DENTNet](./#id-2.-create-dentnet-account)
3. [Send DENTX to DENTNet](./#id-3.-bridge-dentx)

### 1. Swap

{% embed url="https://youtu.be/LKUmyshcV3c?si=RDsuxH1Mf4uFYokb" %}

Using [Uniswap Protocol](https://uniswap.org), many tokens like ETH or DAI can now be swapped for DENTX. \
A [Liquidity Pool](https://docs.uniswap.org/contracts/v2/concepts/core-concepts/pools) v3 DENT/DENTX is provided by DENT Wireless. Start swapping by following this link:&#x20;

{% embed url="https://app.uniswap.org/swap?outputCurrency=0xd65981da8d0bc8ef308d81c2b4955b0781fcdbfb" %}
Swap for DENTX
{% endembed %}

Uniswap supports swapping assets in **both directions** and offers to add more liquidity to the pool from other market participants. The [Uniswap documentation](https://docs.uniswap.org/contracts/v3/overview) explains how it works in detail.

### 2. Create DENTNet account

To create an account, use one of the supported [wallets](../../../tools/wallets/ "mention").

### 3. Send DENTX to DENTNet

Once you have DENTX on Ethereum, e.g., in a MEW or Metamask wallet, you can use the [bridge](../../../tools/bridge/ "mention") to send the Ethereum DENTX to your DENTNet account. Ethereum gas fees apply to send assets from Ethereum to DENTNet.

Follow the instructions in the [move-dentx-from-ethereum-to-dentnet.md](../../../tools/bridge/move-dentx-from-ethereum-to-dentnet.md "mention") section.

{% hint style="info" %}
Using the [bridge](../../../tools/bridge/ "mention")you can also send DENTX from DENTNet to an Ethereum wallet, like Metamask and swap DENTX for other assets like DENT token.
{% endhint %}
