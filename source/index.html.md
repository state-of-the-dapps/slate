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
{}
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
curl "https://api.stateofthedapps.com/dapps/<slug>"
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP Request

`GET https://api.stateofthedapps.com/dapps/<slug>`


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

