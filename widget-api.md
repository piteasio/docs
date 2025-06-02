# 🖼️ Widget API

Piteas Widget API is a versatile tool that can be seamlessly integrated into your portal by configuring it to meet your specific needs. It designed to be open for everyone to use and integrate. You can easily integrate it into your portal by making the necessary configurations.

The interface allows users to buy and sell for ERC20 tokens. An iframe integration may be useful if your application provides services around these ERC20 tokens. (For example, users can buy PLS through a Piteas iframe on your site).

### iframe vs. custom UI

One benefit of an iframe integration is that the your site will automatically keep up with any improvements/additions to the site. After the initital integration is setup no further work is needed to pull in updates as the exchange site is updated over time.

***

### <mark style="color:green;">Piteas Widget Generator is live!</mark>&#x20;

Feel free to use the repo/version here to configure the widget however you like and embed it into your website. Released repo url is here: [https://widget-generator-piteas.netlify.app](https://widget-generator-piteas.netlify.app) :tada:

{% embed url="https://github.com/piteasio/widget-generator" %}
Piteas Widget Generator
{% endembed %}

***

### Example

Swap route for **1000 DAI to PLS**

```
<iframe
    src="https://widget.piteas.io/#/swap?inputCurrency=0xefD766cCb38EaF1dfd701853BFCe31359239F305&outputCurrency=PLS&exactField=input&exactAmount=1000"
    height="720px"
    width="100%"
    style="
      border: 0;
      margin: 0 auto;
      margin-bottom: 0.5rem;
      display: block;
      max-width: 960px;
      min-width: 300px;
    "
  />
```

To include a Piteas widget API within your site just add an iframe element within your website code and link to the Piteas frontent.

***

## Query Parameters

The Piteas  front-end supports URL query parameters to allow for custom linking to the Piteas frontend. Users and developers can use these query parameters to link to the Piteas frontend with custom prefilled settings.

Each Page has specific available URL parameters that can be set. Global parameters can be used on all pages.

A parameter used on an incorrect page will have no effect on frontend settings. Parameters not set with a URL parameter will be set to standard frontend defaults.

#### Swap Page[​](https://docs.uniswap.org/contracts/v2/guides/interface-integration/custom-interface-linking#swap-page) <a href="#swap-page" id="swap-page"></a>

<table><thead><tr><th width="196.33333333333331">Parameter</th><th width="210">Type</th><th>Description</th></tr></thead><tbody><tr><td>inputCurrency</td><td><code>address or symbol</code></td><td>Input currency that will be swapped for output currency.</td></tr><tr><td>outputCurrency</td><td><code>address or symbol</code></td><td>Output currency that input currency will be swapped for.</td></tr><tr><td>exactAmount</td><td><code>number</code></td><td>The custom token amount to buy or sell.</td></tr><tr><td>exactField</td><td><code>string</code></td><td>The field to set custom token amount for. Must be <code>input</code>.</td></tr></tbody></table>

#### Symbols[​](https://docs.uniswap.org/contracts/v2/guides/interface-integration/custom-interface-linking#defaults) <a href="#defaults" id="defaults"></a>

ETH or PLS defaults as the input currency. When a different token is selected for either input or output ETH will default as the opposite selected currency. **(ETH=PLS)**\
\
Pre loaded symbols 👇

<table data-header-hidden data-full-width="false"><thead><tr><th align="center"></th><th align="center"></th><th align="center"></th><th align="center"></th><th align="center"></th><th align="center"></th></tr></thead><tbody><tr><td align="center">PLS</td><td align="center">DAI</td><td align="center">USDT</td><td align="center">USDC</td><td align="center">WPLS</td><td align="center">PTS</td></tr><tr><td align="center">PLSX</td><td align="center">HEX</td><td align="center">EHEX</td><td align="center">WETH</td><td align="center">WBTC</td><td align="center">USDL</td></tr><tr><td align="center">INC</td><td align="center">CST</td><td align="center">PHUX</td><td align="center">PHIAT</td><td align="center">IM</td><td align="center">NINEINCH</td></tr><tr><td align="center">BEAR</td><td align="center">MINT</td><td align="center">HOA</td><td align="center">PDAI</td><td align="center">UP</td><td align="center">UPX</td></tr></tbody></table>

#### Constraints[​](https://docs.uniswap.org/contracts/v2/guides/interface-integration/custom-interface-linking#constraints) <a href="#constraints" id="constraints"></a>

Addresses must be valid ERC20 addresses. Slippage and amount values must be valid numbers accepted by the frontend (or error will prevent from swapping). Slippage can 0, or within the range 10->9999 bips (which converts to 0%, 0.01%->99%)

When selecting PLS as the output currency a user must also choose an inputCurrency that is not PLS (to prevent PLS being populated in both fields)

#### Setting Amounts[​](https://docs.uniswap.org/contracts/v2/guides/interface-integration/custom-interface-linking#setting-amounts) <a href="#setting-amounts" id="setting-amounts"></a>

Two parameters, exactField and exactAmount can be used to set specific token amounts to be sold or bought. Both fields must be set in the URL or there will be no effect on the settings.

***

#### Global[​](https://docs.uniswap.org/contracts/v2/guides/interface-integration/custom-interface-linking#global) <a href="#global" id="global"></a>

<table data-full-width="false"><thead><tr><th>Parameter</th><th>Type</th><th>Description</th></tr></thead><tbody><tr><td>theme</td><td><code>String</code></td><td>Sets them to dark or light mode.</td></tr></tbody></table>

Theme Options:[​](https://docs.uniswap.org/contracts/v2/guides/interface-integration/custom-interface-linking#theme-options)

> Theme can be set as `light` or `dark`.

Example Usage:[​](https://docs.uniswap.org/contracts/v2/guides/interface-integration/custom-interface-linking#example-usage)

> `https://widget.piteas.io/#/swap?theme=light`

***

### Final Another Example

Swap route for **1000000 PLS to PHUX**

```
<iframe
    src="https://widget.piteas.io/#/swap?inputCurrency=PLS&outputCurrency=0x9663c2d75ffd5F4017310405fCe61720aF45B829&theme=dark&exactField=input&exactAmount=1000000"
    height="720px"
    width="100%"
    style="
      border: 0;
      margin: 0 auto;
      margin-bottom: 0.5rem;
      display: block;
      max-width: 960px;
      min-width: 300px;
    "
  />
```
