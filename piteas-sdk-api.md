# ⛓ Piteas SDK/API

Piteas has an offchain model for its dex aggregator. Unlike traditional aggregator models, it doesn't create routes through API calls; the entire process is managed offchain by pathfinder, which then provides the call data response to the UI.

At this stage, Piteas API is not publicly accessible. It is open for access to Piteas' main app, widget app, and some partner protocols. We don't have our own RPC service; quote/request data is fetched entirely through native Pulsechain RPC using our algorithms. Therefore, the number of quote requests needs to be limited. So, if you're looking to run an arbitrage bot, Piteas API is not suitable for you at this stage. However, if you have a project or product and require API access, please provide us with the following information for consideration:

* Brief information about your product.
* Estimated number of API requests covering daily, hourly, and minute intervals.
* If it involves integration for a portal, the number of users.

You can send this request form via Telegram/Twitter to initiate the integration/negotiation process.

> _**We are actively working on making Piteas API publicly accessible, and you can stay updated on this by following our official social media accounts.**_
