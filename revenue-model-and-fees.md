# 💸 Revenue Model & Fees

### How does Piteas generate revenue?

Piteas aggregates liquidity from multiple DEXs, enabling you to swap at the best rate. The protocol assesses how much better our best offer is compared to the next best offer, ensuring we maintain our commitment to delivering the best price on the network, and charges a portion of the savings as protocol revenue. Our priority is the widespread adoption and usage of the protocol.

The main objective of this revenue model is to protect the protocol's economy and the user's earnings. The first rule remains unchanged: if the best offer is not presented to the user, no fee is charged. And if a saving is provided to the user, the protocol can also take a share. A rule has also been set for unexpected gains on exotic routes, capping any fee charged at no more than 2%, positive slippage isn’t included in this cap. For non-mega swaps on major routes, there’s usually no fee at all — or just a small one. Since it operates on a dynamic fee model, we can't provide exact figures, but based on swap statistics from early 2025, the average fee amount can be estimated at \~0.15%.

To find the offer of other dex protocols, Piteas runs a secondary pathfinder internally and conducts a direct path search by disabling trade splitting features. This means it always gets an offer by utilizing the multi-hop feature, which is expected to result in an offer better than, at worst, the best offer from any individual dex.

The second revenue model is positive slippage. This represents the profit generated from the change in liquidity on the network until the swap transaction is confirmed, which positively affects the output amount.

### **Use of Revenue**

Tokens bought back are transferred to the **PTS Treasury Wallet** and will be used for staking or other incentive mechanisms. For now, all buyback operations are fully managed by the team. However, in the future, the plan is to have these executed by AI agents in a non-periodic and unpredictable manner.

{% hint style="success" %}
At least 50% of protocol revenue is used/will be used as token utility.
{% endhint %}

<table><thead><tr><th width="291">Wallet</th><th>Address</th></tr></thead><tbody><tr><td><strong>Revenue &#x26; Buyback Wallet</strong></td><td>0x31415995b2ffaDf05FE929fDB6a87FD18A2817dD</td></tr><tr><td><strong>PTS Treasury Wallet</strong></td><td>0x0101838F92c2e6cbE6C2Be716056A0a291f6824a</td></tr></tbody></table>

> _The revenue wallet here are managed by the Piteas team. They can be used for transferring funds externally due to the protocol's needs, making payments for expenses, providing funding for development stages, and can be used in various ways for token utility purposes._
