# Voice Minutes

Voice minutes are offered by mobile network operators as prepaid packages or subscriptions to their subscribers to charge for access to their network infrastructure.

### Purchase

DENTNet supports the purchase of voice minute packages with different types of size, validity, and country coverage using the Vending pallet. The voice minute packages will be added to the account of the user/subscriber and activated to be used. Once activated, the expiry date is set on-chain.

### Usage Handling

DENTNet is connected to a Layer2 VoIP service and is adding the activated voice minutes to the database of this service.

When subscribers of the operator perform a voice call, the L2 VoIP service handles this and deducts the balance from its database. Through a batch rollup mechanism, the DENTNet voice minute balance is kept in sync with the L2 VoIP service.&#x20;

Other operators can integrate their voice minutes charging system with DENTNet's Layer2 VoIP service.
