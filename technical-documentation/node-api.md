# Node API

A DENTNet node implements a standard Substrate/Polkadot JSON-RPC API that allows you to interact both with your local node and the entire DENTNet network. For example, you can use an RPC method to read a stored value, submit a transaction, or request information about the chain like latest block, runtime version etc.

## Accessing the API

The RPC API is reachable both via HTTP and WS for streaming applications, and the node exposes it by default on port 9944 on localhost. Since some methods provide access to core node operations you should not directly expose a node to the public Internet.&#x20;

The API is most easily accessed and integrated using [@polkadot-js/api](https://polkadot.js.org/docs/api/) but there are other tools such a [Subxt](https://github.com/paritytech/subxt/) for Rust.

To get a list of the available RPC methods, the node has an RPC endpoint called `rpc_methods`. You can call this method (and the others) using a tool like curl:

```sh
% curl -H 'Content-Type: application/json' -d '{
 "id":1,"jsonrpc":"2.0","method":"rpc_methods","params":[]
}' http://127.0.0.1:9944/
{
  "jsonrpc": "2.0",
  "result": {
    "methods": [
      "account_nextIndex",
      "author_hasKey",
      "author_hasSessionKeys",
      "author_insertKey",
      "author_pendingExtrinsics",
      "author_removeExtrinsic",
      "author_rotateKeys",
      "author_submitAndWatchExtrinsic",
      "author_submitExtrinsic",
      "author_unwatchExtrinsic",
      "babe_epochAuthorship",
      "chainHead_unstable_body",
      "chainHead_unstable_call",
      "chainHead_unstable_continue",
      "chainHead_unstable_follow",
      "chainHead_unstable_header",
      "chainHead_unstable_stopOperation",
      "chainHead_unstable_storage",
      "chainHead_unstable_unfollow",
      "chainHead_unstable_unpin",
      "chainSpec_v1_chainName",
      "chainSpec_v1_genesisHash",
      "chainSpec_v1_properties",
      "chain_getBlock",
      "chain_getBlockHash",
      "chain_getFinalisedHead",
      "chain_getFinalizedHead",
      "chain_getHead",
      "chain_getHeader",
      "chain_getRuntimeVersion",
      "chain_subscribeAllHeads",
      "chain_subscribeFinalisedHeads",
      "chain_subscribeFinalizedHeads",
      "chain_subscribeNewHead",
      "chain_subscribeNewHeads",
      "chain_subscribeRuntimeVersion",
      "chain_unsubscribeAllHeads",
      "chain_unsubscribeFinalisedHeads",
      "chain_unsubscribeFinalizedHeads",
      "chain_unsubscribeNewHead",
      "chain_unsubscribeNewHeads",
      "chain_unsubscribeRuntimeVersion",
      "childstate_getKeys",
      "childstate_getKeysPaged",
      "childstate_getKeysPagedAt",
      "childstate_getStorage",
      "childstate_getStorageEntries",
      "childstate_getStorageHash",
      "childstate_getStorageSize",
      "grandpa_proveFinality",
      "grandpa_roundState",
      "grandpa_subscribeJustifications",
      "grandpa_unsubscribeJustifications",
      "offchain_localStorageGet",
      "offchain_localStorageSet",
      "payment_queryFeeDetails",
      "payment_queryInfo",
      "rpc_methods",
      "state_call",
      "state_callAt",
      "state_getChildReadProof",
      "state_getKeys",
      "state_getKeysPaged",
      "state_getKeysPagedAt",
      "state_getMetadata",
      "state_getPairs",
      "state_getReadProof",
      "state_getRuntimeVersion",
      "state_getStorage",
      "state_getStorageAt",
      "state_getStorageHash",
      "state_getStorageHashAt",
      "state_getStorageSize",
      "state_getStorageSizeAt",
      "state_queryStorage",
      "state_queryStorageAt",
      "state_subscribeRuntimeVersion",
      "state_subscribeStorage",
      "state_traceBlock",
      "state_unsubscribeRuntimeVersion",
      "state_unsubscribeStorage",
      "subscribe_newHead",
      "sync_state_genSyncSpec",
      "system_accountNextIndex",
      "system_addLogFilter",
      "system_addReservedPeer",
      "system_chain",
      "system_chainType",
      "system_dryRun",
      "system_dryRunAt",
      "system_health",
      "system_localListenAddresses",
      "system_localPeerId",
      "system_name",
      "system_nodeRoles",
      "system_peers",
      "system_properties",
      "system_removeReservedPeer",
      "system_reservedPeers",
      "system_resetLogFilter",
      "system_syncState",
      "system_unstable_networkState",
      "system_version",
      "transaction_unstable_submitAndWatch",
      "transaction_unstable_unwatch",
      "unsubscribe_newHead",
      "vending_package",
      "vending_packageDetails"
    ]
  },
  "id": 1
}
```

### Calling methods

The most commonly used methods for someone interested in submitting transactions on DENTNet will be `author_submitExtrinsic` and `author_submitAndWatchExtrinsic` .

To use this you first need to create a signed transaction to use as a parameter. For example, to send 12345 DENTX from account A to B we first create the signed transaction.&#x20;

```
0x55028400d43593c715fdd31c61141abd04a99fd6822c8558854ccde39a5684e7a56da27d01b05ac213bc8831c58f95620e36b5e4ed92fbf60da9760318073a63f6779b73358f3eab02675fed0a695da7a542eed7d4b39e4ca8a5ea764adc57fcb67304d887950200000500008eaf04151687736326c9fea17e25fc5287613693c912909cb226aa4794f26a481b00004405635d4a399d02
```

and then submit it by calling the `author_submitExtrinsic` method:

```bash
% curl -H "Content-Type: application/json" -d '{
 "id":1, "jsonrpc":"2.0", "method": "author_submitExtrinsic", 
 "params": ["0x5502..<abbreviated>..99d02"]
}' http://localhost:9944/
```

Details of how transactions are created can be found in the Polkadot documentation at [Transaction Construction](https://wiki.polkadot.network/docs/build-transaction-construction)

Using @polkadot/api to submit the same transaction is easier as the extrinsic can be created:

```typescript
const { ApiPromise } = require('@polkadot/api');
const { Keyring } = require('@polkadot/keyring');

const PRIVKEY = '0xe5be9a5092b81bca64be81d212e7f2f9eba183bb7a90954f7b76361f6edb5c0a'
const RECIPIENT = 'dx8TbX2EdNtU2qMhTyeKcReSPzXZFGTMnNDqgGaSnznVWw32k';

async function main () {
  // Instantiate the API
  const wsProvider = new WsProvider('ws://127.0.0.1:9944/');
  const api = await ApiPromise.create({ provider: wsProvider });

  // Construct the keyring and add our key
  const keyring = new Keyring({ type: 'sr25519' });
  const sender = keyring.addFromUri(PRIVKEY);

  // Create a extrinsic, transferring 12345 DENTX units to recipient
  const transfer = api.tx.balances.transferAllowDeath(RECIPIENT, 12345);
  const hash = await transfer.signAndSend(sender);

  console.log('Transfer sent with hash', hash.toHex());
}

main().catch(console.error).finally(() => process.exit());
```

Note that private keys should never be directly embedded in code as in the above example but be handled securely.
