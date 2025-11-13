# Transactions

DENTNet uses [Substrate](https://substrate.io/), a modular framework to efficiently build blockchains. Substrate provides modules called pallets and support libraries that make up the base layer of DENTNet. On top there are custom pallets and modules that support the telecom-related functionality and much more.

Within each functional **pallet** on DENTNet, it's possible to **call** and execute its functions, provided you have permission to do so. Because these calls originate outside of the blockchain runtime, such transactions are referred to as **extrinsics**. Extrinsics normally contain a signature, data to related to the invoked function, a reference to the pallet and call that it is intended for, and some technical data like nonce, runtime version etc. For example, the Staking pallet contains all functions related to staking, and the Sponsor pallet all functions for [operator-sponsorship.md](../advanced-concepts/operator-sponsorship.md "mention").&#x20;

Extrinsics can be one of 3 distinct types:

* **Signed transactions:** these must contain the signature of the account sending the inbound request to the runtime. With signed transactions, the account used to submit the request typically pays the transaction fee and must sign it using the account's private key.
* **Unsigned transactions:** these don't carry any information about who submitted the transaction, since the format of this type of transaction doesn't require a signature.&#x20;
* **Inherents:** are a special type of unsigned transaction made by block authors that carry information required to build a block such as timestamps, storage proofs, and uncle blocks.

In case of a purchase of a voice package on a sponsored account, the Sponsor pallet is used to deduct the transaction fee from the operator account, and the Vending pallet is used to take care of issuing the voice package to and deducting the DENTs from the user's wallet.&#x20;

All extrinsics submitted by an account can be found in our [explorer.md](../../tools/explorer.md "mention").
