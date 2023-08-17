# 💸 Revenue Model

### How does Piteas generate revenue?

<figure><img src="../.gitbook/assets/howitworks---New (1).jpg" alt=""><figcaption><p>Piteas - Revenue Flow</p></figcaption></figure>

As you know, Piteas aggregates liquidity from multiple DEXs, enabling you to swap at the best rate. Following the protocol's launch, it did not charge any swap fees for a little over a month, and subsequently introduced the new fee model. The protocol assesses how much better our best offer is compared to the next best offer, ensuring we maintain our commitment to delivering the best price on the network, and charges a portion of the savings as protocol revenue. Our priority is the widespread adoption and usage of the protocol.

The main objective of this revenue model is to protect the protocol's economy and the user's earnings. The first rule remains unchanged: if the best offer is not presented to the user, no fee is charged. And if a saving is provided to the user, the protocol can also take a share. This share is capped at a maximum of 5000 bps and is significantly lower, below 2000 bps, for major routes.

To find the offer of other dex protocols, Piteas runs a secondary pathfinder internally and conducts a direct path search by disabling trade splitting features. This means it always gets an offer by utilizing the multi-hop feature, which is expected to result in an offer better than, at worst, the best offer from any individual dex.

The second revenue model is positive slippage. This represents the profit generated from the change in liquidity on the network until the swap transaction is confirmed, which positively affects the output amount.

_We are continuing the development process to create new use cases for PTS Token and provide privileges for token holders._
