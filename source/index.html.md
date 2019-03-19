---
title: State of the DApps API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='mailto:support@stateofthedapps.com'>Request a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

search: true
---

# Introduction

Welcome to the State of the DApps API! You can use our API to access State of the DApps API endpoints, which can get information on various dapps and statistics in our database.

You can view code examples in the dark area to the right.

This example API documentation page was created with [Slate](https://github.com/lord/slate).

## Technical facts

> **API Endpoint**

```
https://api.stateofthedapps.com/
```

* Content-type: `application/json`
* CDN Cache strategy: 5 minutes
* Data refresh interval: 30 minutes
* Data source: Infura API (Ethereum & POA), native node (EOS), CryptoCompare (USD exchange rate)

## Usage
Public, with attribution to State of the DApps (<https://www.stateofthedapps.com/>)


# DApps

## Get All DApps

```shell
curl "https://api.stateofthedapps.com/dapps"
```

> The above command returns JSON structured like this:

```json
{
  "items": [
    {
      "categories": [
        "social"
      ],
      "created": "2018-12-16",
      "iconUrl": "https://cdn.stateofthedapps.com/dapps/steemit/icon_steemit_af91cb339644dd9cb2bc612d0281686547c0197ad2e1bb282bba749ae5da1785_opti.png",
      "iconSmallUrl": "https://cdn.stateofthedapps.com/dapps/steemit/icon_small_steemit_b8baea4a2e2917c3321ada0829f8b6865bc440c15af99a86a99ba75594bd98a1_opti.png",
      "imageKeyVisual": "",
      "imageKeyVisualSmall": "",
      "isNew": false,
      "name": "Steemit",
      "platform": "Steem",
      "rank": 1,
      "rankDelta": 1,
      "slug": "steemit",
      "sparklines": {
        "users": []
      },
      "stats": {
        "dau": 5352
      },
      "teaser": "Social blogging platform"
    },
    { ... }
  ],
  "pager": {
    "totalCount": 2218,
    "limit": 50,
    "offset": 0
  }
}
```

### HTTP Request

`GET https://api.stateofthedapps.com/dapps`

### Query Parameters

* limit=50
* offset=0
* page=1
* platform=ethereum|eos|poa
* sort=new|most-viewed|hot|rank|rating|name|dau|mau|vol_7d|dev_30d|usd_value_7d
* order=asc|desc
* status=any
* category=games
* tags=a,b,c / tags[]=a&tags[]=b
* text=abc

## Get a Specific DApp

```shell
curl "https://api.stateofthedapps.com/dapps/augur"
```

> The above command returns JSON structured like this:

```json
{
  "item": {
    "alert": "",
    "audits": [],
    "authors": ["Jack Peterson", "Joey Krug"],
    "badges": [],
    "categories": ["exchanges"],
    "contractsKovan": [],
    "contractsMainnet": ["0xb3337164e91b9f05c87c7662c7ac684e8e0ff3e7", ...],
    "contractsRinkeby": [],
    "contractsRopsten": [],
    "contractsPoaMainnet": [],
    "contractsGoChainMainnet": [],
    "contractsXDaiMainnet": [],
    "contractsEosMainnet": [],
    "contractsSteemMainnet": [],
    "created": "2015-08-15",
    "description": "Augur allows users to create prediction markets on the outcome of any future event. Trade on the outcome of an upcoming election, hedge against natural disasters and market crashes.\n\nCompanies can use Augur to guide decision making by forecasting vital information such as total product sales and project completion times.\n\nThere are no limits on what events can be created and traded on. If you want to trade on it, a market can be created for it. Augur is a permissionless protocol built on top of the Ethereum blockchain. Anyone, anywhere in the world can participate.",
    "iconUrl": "https://cdn.stateofthedapps.com/dapps/augur/icon_augur_f412c0212bbbadf73dfd57a36d557128c4ab2455c35c904fb75b1485cf5d9966_opti.png",
    "iconSmallUrl": "https://cdn.stateofthedapps.com/dapps/augur/icon_small_augur_1a1dbce16d0d1b4738fe6cf4c166e9f0473033e35eb4080c1862172d570c840f_opti.png",
    "isNew": false,
    "isNsfw": false,
    "lastUpdated": "2019-01-21",
    "license": "GPL",
    "logoUrl": "https://cdn.stateofthedapps.com/dapps/augur/logo_augur_671f1d1d8b0c845ce2a264d0b86f20bffdefcc229d0c4e55281dbabae5790768_opti.jpg",
    "name": "Augur",
    "nofollow": false,
    "platform": "Ethereum",
    "productImage": "https://cdn.stateofthedapps.com/dapps/augur/product_image_augur_bf73d2b2ec4a6d57f7c706f419557e78f8eceeba5e7212a493513da831b24e9a_opti.jpg",
    "productImageSmall": "https://cdn.stateofthedapps.com/dapps/augur/product_image_small_augur_c49b37b5f809ed0eb272ccf3206b4dd171262770b97e7fc2dd04004fcccc3284_opti.jpg",
    "profileScore": 1.0,
    "rank": 33,
    "rankDelta": -1,
    "relatedDapps": [{
      "name": "Gnosis",
      "categories": ["exchanges"],
      "iconUrl": "https://cdn.stateofthedapps.com/dapps/gnosis/icon_gnosis_7128ae7885c96a248446636810c20cfb31799baf6c6df4fcef69505088ef13a6_opti.png",
      "iconSmallUrl": "https://cdn.stateofthedapps.com/dapps/gnosis/icon_gnosis_7128ae7885c96a248446636810c20cfb31799baf6c6df4fcef69505088ef13a6_opti.png",
      "slug": "gnosis",
      "teaser": "Prediction market platform"
    }, { ... }],
    "reviews": [],
    "sites": {
      "websiteUrl": "http://www.augur.net/",
      "dappUrl": "https://dev.augur.net/",
      "androidUrl": "",
      "iosUrl": ""
    },
    "slug": "augur",
    "socials": [{
      "platform": "github",
      "url": "https://github.com/AugurProject"
    }, {
      "platform": "reddit",
      "url": "https://www.reddit.com/r/augur"
    }, {
      "platform": "chat",
      "url": "http://invite.augur.net/"
    }, {
      "platform": "blog",
      "url": "https://medium.com/@augurproject"
    }, {
      "platform": "twitter",
      "url": "https://twitter.com/AugurProject"
    }, {
      "platform": "facebook",
      "url": "https://www.facebook.com/augurproject"
    }],
    "sparklines": {
      "users": [146, 122, 140, 116, 105, 84, 95, 124, 93, 158, 105, 98, 89, 85, 101, 77, 140, 204, 103, 113, 102, 203, 173, 132, 103, 133, 149, 104, 170, 125],
      "transactions": [367, 304, 340, 249, 257, 263, 256, 303, 232, 297, 271, 199, 315, 221, 285, 189, 295, 490, 313, 286, 297, 613, 490, 373, 357, 550, 463, 345, 646, 376],
      "value": [21.06935988933668, 101.32061466801004, 20.584593834005023, 34.04320683754522, 84.31616995798343, 44.78567616874754, 15.68848322628699, 54.00712759740337, 53.28368897921183, 16.238432270108266, 34.099599131003316, 23.27206083611255, 89.55256387754584, 49.4807641395691, 25.732853903566248, 8.515336536790278, 101.31670744147316, 40.60623474602912, 30.617434171221426, 42.59837559924722, 43.6447530618896, 49.81445816545752, 63.06701575776657, 148.03975408661537, 97.0255831147726, 262.1103648556857, 218.6820398275529, 511.8279279223417, 314.1800572815031, 105.27810843612464],
      "poa_value": [0, ...],
      "gochain_value": [0, ...],
      "xdai_value": [0, ...],
      "eos_value": [0, ...],
      "steem_value": [0, ...],
      "gh_events": [9, 57, 104, 63, 116, 78, 17, 12, 0, 0, 25, 123, 105, 17, 19, 131, 108, 165, 74, 114, 40, 40, 105, 213, 146, 117, 104, 28, 22, 202]
    },
    "stats": {
      "ctr": 0.3926218708827404,
      "positive": 1,
      "negative": 0,
      "neutral": 0,
      "impressions": 759,
      "clicks": 298,
      "flagged": 0,
      "shared": 0,
      "suggested": 1,
      "dau": 125,
      "dau_pct": -26.470588235294116,
      "mau": 1948,
      "mau_pct": -22.85148514851485,
      "tx_1d": 376,
      "tx_30d": 10242,
      "tx_7d": 3110,
      "value_1d": 105.27810843612464,
      "value_30d": 2704.7993463209064,
      "value_7d": 1657.143835524596,
      "value_7d_pct": 345.87032123313526,
      "wau": 574,
      "dev_30d": 2354,
      "dev_30d_pct": -2.6065370293752586,
      "dev_90d": 6812,
      "listed": 0,
      "rating": 0.20654329147389294,
      "votes": 1,
      "star_rating": 5.0,
      "poa_value_7d": 0,
      "poa_value_7d_pct": null,
      "wau_pct": -19.382022471910112,
      "poa_value_1d": 0,
      "poa_value_1d_pct": null,
      "poa_value_30d": 0,
      "poa_value_30d_pct": null,
      "value_1d_pct": -66.49115499339406,
      "value_30d_pct": -74.27833556408879,
      "eos_value_1d": 0,
      "eos_value_1d_pct": null,
      "eos_value_30d": 0,
      "eos_value_30d_pct": null,
      "eos_value_7d": 0,
      "eos_value_7d_pct": null,
      "usd_value_1d": 14612.601450934102,
      "usd_value_30d": 375426.14926934184,
      "usd_value_7d": 230011.56437081393,
      "steem_value_1d": 0,
      "steem_value_1d_pct": null,
      "steem_value_30d": 0,
      "steem_value_30d_pct": null,
      "steem_value_7d": 0,
      "steem_value_7d_pct": null,
      "gochain_value_1d": 0,
      "gochain_value_1d_pct": null,
      "gochain_value_30d": 0,
      "gochain_value_30d_pct": null,
      "gochain_value_7d": 0,
      "gochain_value_7d_pct": null,
      "xdai_value_1d": 0,
      "xdai_value_1d_pct": null,
      "xdai_value_30d": 0,
      "xdai_value_30d_pct": null,
      "xdai_value_7d": 0,
      "xdai_value_7d_pct": null
    },
    "status": "live",
    "tags": ["prediction", "market", "forecasting", "trading", "profits"],
    "teaser": "Decentralized prediction market"
  }
}
```

### HTTP Request

`GET https://api.stateofthedapps.com/dapps/<slug>`


## Lookup a DApp by Name or Address

Use this to check if a DApp exists with the given name or contract address. With the returned `slug` the dapp details can be found using [`/dapps/<slug>`](#get-a-specific-dapp)

```shell
curl "https://api.stateofthedapps.com/dapps/lookup?name=Status"

curl "https://api.stateofthedapps.com/dapps/lookup?address=0xd248B0D48E44aaF9c49aea0312be7E13a6dc1468"
```

> The above commands return JSON structured like this:

```json
{"item": {"slug": "status"}}
```

### HTTP Request

`GET https://api.stateofthedapps.com/dapps/lookup`

### Query Parameters

Parameter | Description
--------- | --------------
name      | The name to lookup if a dapp exists
address   | The contract address to lookup if a dapp exists

If no match is found, a HTTP 404 is returned.


# Tags

## Get All Tags

Returns the tags that are associated with dapps, sorted by popularity in descending order.

```shell
curl "https://api.stateofthedapps.com/tags"
```

> The above command returns JSON structured like this:

```json
{
  "items": [
    "integrity",
    "teaching",
    "merchant",
    "risk",
    "tickets",
    "open-source",
    "skills",
    "companies",
    "elections",
    "subcurrency",
    "protection",
    "forum",
    "auction",
    "economics",
    "credit"
  ]
}
```

### HTTP Request

`GET https://api.stateofthedapps.com/tags`

### Query Parameters

Parameter | Default | Description
--------- | ------- | --------------
text      | *none*  | Filter tags matching the provided string, case insensitive
type      | *none*  | For which data type to return the tags, should be `dapps`
limit     | 15      | The maximum number of tags to return


# Categories

## Get All Categories

Returns the categories and how many dapps they contain, sorted by usage in descending order.

```shell
curl "https://api.stateofthedapps.com/categories"
```

> The above command returns JSON structured like this:

```json
{
  "items": [
    {
      "name": "Games",
      "slug": "games",
      "dappCount": 521
    }, {
      "name": "Gambling",
      "slug": "gambling",
      "dappCount": 400
    }, {
      "name": "Social",
      "slug": "social",
      "dappCount": 284
    }, {
      "name": "Finance",
      "slug": "finance",
      "dappCount": 275
    }
  ]
}
```

### HTTP Request

`GET https://api.stateofthedapps.com/categories`


# Statistics

The purpose of the statistics API is to provide high level statistics of the global dapp ecosystem, with breakdown per platform (Ethereum, EOS and POA) and per category.

## Get All Statistics

```shell
curl "https://api.stateofthedapps.com/stats"
```

> The above command returns JSON structured like this (sample as of 2018-12-14, subdocuments ommitted, but documented below):

```json
{
    "dappContractCount": 5423,
    "dappCount": 2307,
    "dappDau": 42372,
    "dappTx24Hr": 1034468,
    "dappVol24Hr": 0,
    "dappUSDVol24Hr": 17495009.94100345,
    "statuses": [...],
    "categories": [...],
    "platforms": [...]
}
```

### HTTP Request

`GET https://api.stateofthedapps.com/stats`

### Response

The above request returns JSON structured like this:

* `dappCount` the total number of DApps on State of the DApps.
* `dappContractCount` the total number of DApps contracts on State of the DApps.
* `dappDau` the global daily (last 24h) active user count for DApps of all platforms combined. Active users are counted by the number of unique source addresses that send a transaction to DApp contracts.
* `dappTx24Hr` the global number of transations to DApp contracts of all platform in the last 24h.
* `dappVol24Hr` (deprecated)
* `dappUSDVol24Hr` the global transaction volume of all dapps combined, converted to USD, in the last 24h. We only count the native (ETH, EOS, POA) value of transfers sent TO a dapp, not any token values.


> `statuses` breakdown of the number of dapps per `status`, array of documents with the format:

```json
{
    "dappCount": 1218,
    "status": "live"
}
```

### Statuses list


* `status` the name of the status.
* `dappCount` the total number of DApps with this status.

### Categories list

`categories` breakdown of the number of dapps per `category` (transaction statistics only for Ethereum), array of documents with the format:

```json
{
   "category": "storage",
   "dappCount": 55,
   "dappContractCount": 19,
   "dappMau": 78080,
   "dappTx30D": 92667
}
```

* `category` the name of the category.
* `dappCount` the total number of DApps for this `category`.
* `dappContractCount` the total number of DApps contracts for this `category`.
* `dappMau` the monthly (last 30 days) active user count for all DApps of this `category`. Active users are counted by the number of unique source addresses that send a transaction to DApp contracts.
* `dappTx30D` the number of transations  for all DApps of this `category` in the last 30 days.

### Platforms list

`platforms` breakdown per platform, array of documents with the format:

```json
{
    "platform": "ethereum",
    "dappCount": 2190,
    "dappContractCount": 5219,
    "dappDau": 10713,
    "dappTx24Hr": 55542,
    "dappVol24Hr": 66580.91393945477,
    "dappUSDVol24Hr": 5736611.545023423,
    "categories": [...],
}
```

* `platform` the name of the platform.
* `dappCount` the total number of DApps for this `platform`.
* `dappContractCount` the total number of DApps contracts for this `platform`.
* `dappDau` the daily (last 24h) active user count for all DApps of this `platform`. Active users are counted by the number of unique source addresses that send a transaction to DApp contracts.
* `dappTx24Hr` the number of transations  for all DApps of this `platform` in the last 24h.
* `dappVol24Hr` the transaction volume of all dapps of this `platform`, in the platform native currency, for the last 24h. We only count the native (ETH, EOS, POA) value of transfers sent TO a dapp, not any token values.
* `dappUSDVol24Hr` the transaction volume of all dapps of this `platform` combined, converted to USD, in the last 24h. We only the native (ETH, EOS, POA) value of transfers sent TO a dapp.
* `categories` breakdown of the number of dapps per `category` for this `platform`, (transaction statistics only for Ethereum), array of documents with the above documented `categories` format.

## Known issues / Limitations
* DApp growth figures aren’t exposed yet via this API, but this is expected to be added Soon. Bug us for raising the priority of this.
* Category transaction statistics are only counted for Ethereum and lack USD equivalent values.
* USD values are calculated with the last known exchange rate.

