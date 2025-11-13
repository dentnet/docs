# Events

While extrinsics represent information from the outside world, events represent information from the network and specific pallets in particular. Extrinsics can trigger events; for example, the Staking pallet emits a Reward event when claiming staking rewards to tell the user how much the account was credited and the Vending pallet emits a PriceUpdated event when the price of a mobile package changes.

Events can be subscribed to and used by operators to trigger processes in their own system like refreshing the user interface of an app or informing users about low balance via push notification.

For reliable handling of events, it is important to monitor events in each block for those that contain your addresses of interest. Monitoring events instead of transaction data ensures that you can properly react to changes on DENTNet.

