# Accounts

An account is a digital representation of a participant on DENTNet, defined by a unique cryptographic key pair. The public key serves as an address through which digital assets are sent and received, while the private key, kept confidential, validates ownership and authorizes transactions on DENTNet.

Accounts can hold balances of tokens like DENT and mobile assets such as voice minutes, and may interact with smart contracts (pallets) to perform various functions like purchasing data on DENTNet.&#x20;

### Addresses

An address on DENTNet is represented by 47 alphanumeric characters prefixed with "dx" and is derived by SS58 encoding the public key of the corresponding account.

As DENTNet is built on top of Polkadot SDK, addresses are compatible with the Polkadot address system and DENTNet supports account abstraction, multi-signature accounts, and proxy accounts.

### DENTX Balance

Accounts created on DENTNet have a DENTX balance. This balance is used to pay transaction fees and perform Staking.  Each account needs to have an existential amount of DENTX to reside on DENTNet.

{% hint style="info" %}
The existential amount of DENTX is 0.01
{% endhint %}

With the concept of [operator-sponsorship.md](../advanced-concepts/operator-sponsorship.md "mention")an existential balance is not required for consumer accounts, as they are secured by the sponsor. This ensures that consumers can both hold and transact with mobile assets like voice minutes on DENTNet without directly acquiring DENTX.

### Account Creation

Mobile operators that use DENTNet for their subscribers can create accounts using the [API](../../technical-documentation/node-api.md) or CLI (on request). The key generation should be done securely in a protected backend system. If subscribers want to have control over their keys, a new account can be created by the user and the assets can be moved to the new account.

There are several ways to create an account as a user. Please see the [Wallets](../../tools/wallets/) section for details.&#x20;

### Locking

Accounts on DENTNet support the locking of DENTX. Funds that are locked can not be withdrawn or used for other transactions. Funds get locked during staking or when bonding to run a Validator.
