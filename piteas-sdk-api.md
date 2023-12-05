# ⛓ Piteas SDK/API

Piteas has an offchain model for its dex aggregator. Unlike traditional aggregator models, it doesn't create routes through API calls; the entire process is managed offchain by pathfinder, which then provides the call data response to the UI.

At this stage, Piteas API is not publicly accessible\*. [_<mark style="color:blue;">(Modified)</mark>_](piteas-sdk-api.md#request-example-and-api-parameters) It is open for access to Piteas' main app, widget app, and some partner protocols. We don't have our own RPC service; quote/request data is fetched entirely through native Pulsechain RPC using our algorithms. Therefore, the number of quote requests needs to be limited. So, if you're looking to run an arbitrage bot, Piteas API is not suitable for you at this stage. However, if you have a project or product and require API access, please provide us with the following information for consideration:

* Brief information about your product.
* Estimated number of API requests covering daily, hourly, and minute intervals.
* If it involves integration for a portal, the number of users.

You can send this request form via Telegram/Twitter to initiate the integration/negotiation process.

***

### Piteas Public API - SDK Beta Release

Piteas SDK beta release has been published. Please note that this version may contain errors and is in the development stage. Ensure you consider request limits.

{% hint style="success" %}
To execute the swap process, sending the calldata from the response data to the swap function in [PiteasRouter ](contracts.md)is sufficient. You can adjust the necessary value data and gas estimate settings according to your conditions. Please also take a look at the router contract because the arguments in the response data are defined for the conditions in the contract.
{% endhint %}

The SDK version is in the beta stage, so please avoid sending more than **10 requests per minute**. Exceeding this limit may result in your blockage and cause access issues for one hour. Limits will be adjusted after the beta version.

{% content-ref url="contracts.md" %}
[contracts.md](contracts.md)
{% endcontent-ref %}

### Request Example and API parameters

> Test URL for 1,000,000 PLS to DAI :arrow\_down\_small:\
> \
> https://**sdk.piteas.io**/quote?tokenInAddress=PLS\&tokenInChainId=369\&tokenOutAddress=0xefD766cCb38EaF1dfd701853BFCe31359239F305\&tokenOutChainId=369\&amount=1000000000000000000000000\&allowedSlippage=0.50

{% swagger method="get" path="/quote" baseUrl="https://sdk.piteas.io" summary="Quote" %}
{% swagger-description %}
Swap quote request on Piteas SDK
{% endswagger-description %}

{% swagger-parameter in="query" required="true" name="tokenInAddress" type="string" %}
Example: 0x2A06a971fE6ffa002fd242d437E3db2b5cC5B433\
Use **PLS** for native token
{% endswagger-parameter %}

{% swagger-parameter in="query" name="tokenInChainId" required="true" type="number" %}
Default: **369**
{% endswagger-parameter %}

{% swagger-parameter in="query" name="tokenOutAddress" required="true" type="string" %}
Example: 0x2A06a971fE6ffa002fd242d437E3db2b5cC5B433\
Use **PLS** for native token
{% endswagger-parameter %}

{% swagger-parameter in="query" name="tokenOutChainId" required="true" type="number" %}
Default: **369**
{% endswagger-parameter %}

{% swagger-parameter in="query" name="amount" required="true" type="integer" %}
Amount with decimals
{% endswagger-parameter %}

{% swagger-parameter in="query" name="allowedSlippage" type="string" required="true" %}
Default: **0.5**
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Quote Success" %}
```json
{
  "srcToken": {
    "address": "0xA1077a294dDE1B09bB078844df40758a5D0f9a27",
    "symbol": "WPLS",
    "decimals": 18,
    "chainId": 369
  },
  "destToken": {
    "address": "0xefD766cCb38EaF1dfd701853BFCe31359239F305",
    "symbol": "DAI",
    "decimals": 18,
    "chainId": 369
  },
  "srcAmount": "0xd3c21bcecceda1000000",
  "destAmount": "0x2e33260eb8b008f09",
  "gasUseEstimate": 4025000,
  "gasUseEstimateUSD": 0.033025699048724835,
  "methodParameters": {
    "data": "...",
    "calldata": "...",
    "value": "0xd3c21bcecceda1000000"
  },
  "route": {
    "paths": [
      [...],
      [...],
      [...]
    ],
    "swaps": [
      {...},
      {...},
      {...}
    ]
  }
}
```
{% endswagger-response %}

{% swagger-response status="429: Too Many Requests" description="Limit Error" %}
Please note that you cannot send more than **10 requests within 1 minute**. If you exceed this limit and encounter a 429 error, you will be **blocked** by the SDK manager for **one hour**.
{% endswagger-response %}
{% endswagger %}
