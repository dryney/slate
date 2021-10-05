---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='https://chainbeat.io/contact/new'>Contact us for a Developer Key</a>

includes:
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the Chainbeat API
---

# Introduction

Welcome to the Chainbeat API! You can use our API to access Chainbeat API endpoints, which can get information on reports.

We have language bindings in Shell! You can view code examples in the dark area to the right.


# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" -H "Authorization: Bearer api_token"
```

> Make sure to replace `api_token` with your API key.

Chainbeat uses API keys to allow access to the API. You can register a new Chainbeat API key at our [feedback form](https://chainbeat.io/contact/new).

Chainbeat expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: Bearer api_token`

<aside class="notice">
You must replace <code>api_token</code> with your personal API key.
</aside>

# Reports

## Transactions

```shell
curl -X GET "https://chainbeat.io/api/v2/celo/0x765de816845861e75a25fca122bb6898b8b1282a/transactions.json" -H "Authorization: Bearer api_token"
```

> The above command returns JSON structured like this:

```json
  {
   "transactions":[
      {
         "date":"2021-09-27",
         "value":7720
      },
      {
         "date":"2021-09-28",
         "value":7452
      },
      {
         "date":"2021-09-29",
         "value":8584
      },
      {
         "date":"2021-09-30",
         "value":7109
      },
      {
         "date":"2021-10-01",
         "value":10766
      },
      {
         "date":"2021-10-02",
         "value":10211
      },
      {
         "date":"2021-10-03",
         "value":9255
      }
   ],
   "top_addresses":[
      {
         "position":1,
         "address":"0x59e48c6b2acb0c3e2a0afb98cfe720c4d02c19ca",
         "transactions_count":"41,054",
         "percent_of_total_transactions_count":"67.19",
         "eth_value":"0"
      },
      {
         "position":2,
         "address":"0xadd7c542667728e6b91dc091a6def2489f2de35c",
         "transactions_count":"2,989",
         "percent_of_total_transactions_count":"4.89",
         "eth_value":"0"
      },
      {
         "position":3,
         "address":"0xa4812cc1be496440948c3058f1ec20ba534c3366",
         "transactions_count":"920",
         "percent_of_total_transactions_count":"1.51",
         "eth_value":"0"
      },
      {
         "position":4,
         "address":"0xb07535cc39af3f1baf98e3c723ac1e8265ab614f",
         "transactions_count":"717",
         "percent_of_total_transactions_count":"1.17",
         "eth_value":"0"
      },
      {
         "position":5,
         "address":"0x5776b4893faca32a9224f18950406c9599f3b013",
         "transactions_count":"254",
         "percent_of_total_transactions_count":"0.42",
         "eth_value":"0"
      },
      {
         "position":6,
         "address":"0x04c359b782e9a5780ae8b67351a9f9e06b0c3e5b",
         "transactions_count":"150",
         "percent_of_total_transactions_count":"0.25",
         "eth_value":"0"
      },
      {
         "position":7,
         "address":"0xf484dcd112000fd70c075677a84eef410e5de117",
         "transactions_count":"150",
         "percent_of_total_transactions_count":"0.25",
         "eth_value":"0"
      },
      {
         "position":8,
         "address":"0x38371cc4db100815c59520bf5ca9c8db7faa52f0",
         "transactions_count":"148",
         "percent_of_total_transactions_count":"0.24",
         "eth_value":"0"
      },
      {
         "position":9,
         "address":"0x42b64299dc52856d9a80abf48af6d65ec6d556f8",
         "transactions_count":"123",
         "percent_of_total_transactions_count":"0.20",
         "eth_value":"0"
      },
      {
         "position":10,
         "address":"0x8a045c8dcb7977425aa5a13887477d0dd4c2c28e",
         "transactions_count":"119",
         "percent_of_total_transactions_count":"0.19",
         "eth_value":"0"
      }
   ],
   "top_methods":[
      {
         "position":1,
         "method":"transferFrom",
         "transactions_count":"41,554",
         "percent_of_total_transactions_count":"68.01",
         "errors_count":0
      },
      {
         "position":2,
         "method":"transfer",
         "transactions_count":"7,679",
         "percent_of_total_transactions_count":"12.57",
         "errors_count":10
      },
      {
         "position":3,
         "method":"approve",
         "transactions_count":"6,504",
         "percent_of_total_transactions_count":"10.65",
         "errors_count":1
      },
      {
         "position":4,
         "method":"0xe1d6aceb",
         "transactions_count":"5,204",
         "percent_of_total_transactions_count":"8.52",
         "errors_count":6
      },
      {
         "position":5,
         "method":"increaseAllowance",
         "transactions_count":"174",
         "percent_of_total_transactions_count":"0.28",
         "errors_count":0
      },
      {
         "position":6,
         "method":"Transfer",
         "transactions_count":"3",
         "percent_of_total_transactions_count":"0.00",
         "errors_count":3
      }
   ],
   "total_transactions":61097,
   "successful_transactions":61077,
   "failed_transactions":20,
   "sum_ether":"477.146294347919736798",
   "sum_usd":"2938.16094266569546568870639041378374",
   "start_date":"2021-09-27T00:00:00.000Z",
   "end_date":"2021-10-03T23:59:59.999Z"
}
```

This endpoint retrieves transactions report.

### HTTP Request

`GET "https://chainbeat.io/api/v2/network/smart_contract_address/transactions.json`

### Query Parameters

Parameter | required parameter? | Description
--------- | ------- | -----------
network | true | Smart contract network.
smart_contract_address | true | Smart contract address.
date_interval| false | Date interval for the report. Valid Date Intervals: <code>today</code> <code>yesterday</code> <code>last_7_days</code> <code>this_month</code> <code>last_month</code> <code>last_30_days</code> <code>last_90_days</code> <code>year_to_date</code> <code>life_time</code>
address | false | Used to filter the report by address
method | false | Used to filter the report by method
status | false | Used to filter the report by transaction status. Valid statuses: <code>success</code> <code>error</code>


<aside class="success">
Remember — Without a date_interval parameter, the query will return data for the last 7 days!
</aside>

## Active Users

```shell
curl -X GET "https://chainbeat.io/api/v2/network/smart_contract_address/active_users.json" -H "Authorization: Bearer api_token"
```

> The above command returns JSON structured like this:

```json
{
   "active_users":[
      {
         "date":"2021-09-27",
         "value":1932
      },
      {
         "date":"2021-09-28",
         "value":1448
      },
      {
         "date":"2021-09-29",
         "value":1777
      },
      {
         "date":"2021-09-30",
         "value":2139
      },
      {
         "date":"2021-10-01",
         "value":1951
      },
      {
         "date":"2021-10-02",
         "value":1073
      },
      {
         "date":"2021-10-03",
         "value":1048
      }
   ],
   "top_addresses":[
      {
         "position":1,
         "address":"0x59e48c6b2acb0c3e2a0afb98cfe720c4d02c19ca",
         "transactions_count":"41,054",
         "percent_of_total_transactions_count":"67.17"
      },
      {
         "position":2,
         "address":"0xadd7c542667728e6b91dc091a6def2489f2de35c",
         "transactions_count":"2,989",
         "percent_of_total_transactions_count":"4.89"
      },
      {
         "position":3,
         "address":"0xa4812cc1be496440948c3058f1ec20ba534c3366",
         "transactions_count":"920",
         "percent_of_total_transactions_count":"1.51"
      },
      {
         "position":4,
         "address":"0xb07535cc39af3f1baf98e3c723ac1e8265ab614f",
         "transactions_count":"717",
         "percent_of_total_transactions_count":"1.17"
      },
      {
         "position":5,
         "address":"0x5776b4893faca32a9224f18950406c9599f3b013",
         "transactions_count":"254",
         "percent_of_total_transactions_count":"0.42"
      },
      {
         "position":6,
         "address":"0x04c359b782e9a5780ae8b67351a9f9e06b0c3e5b",
         "transactions_count":"150",
         "percent_of_total_transactions_count":"0.25"
      },
      {
         "position":7,
         "address":"0xf484dcd112000fd70c075677a84eef410e5de117",
         "transactions_count":"150",
         "percent_of_total_transactions_count":"0.25"
      },
      {
         "position":8,
         "address":"0x38371cc4db100815c59520bf5ca9c8db7faa52f0",
         "transactions_count":"148",
         "percent_of_total_transactions_count":"0.24"
      },
      {
         "position":9,
         "address":"0x42b64299dc52856d9a80abf48af6d65ec6d556f8",
         "transactions_count":"123",
         "percent_of_total_transactions_count":"0.20"
      },
      {
         "position":10,
         "address":"0x8a045c8dcb7977425aa5a13887477d0dd4c2c28e",
         "transactions_count":"119",
         "percent_of_total_transactions_count":"0.19"
      }
   ],
   "active_users_total":8568,
   "active_users_per_day":1624,
   "max_users_per_day":2139,
   "min_users_per_day":1048,
   "start_date":"2021-09-27T00:00:00.000Z",
   "end_date":"2021-10-03T23:59:59.999Z"
}
```

This endpoint retrieves Active Users report.


### HTTP Request

`GET https://chainbeat.io/api/v2/network/smart_contract_address/active_users.json<ID>`

### URL Parameters

Parameter | required parameter? | Description
--------- | ------- | -----------
network | true | Smart contract network.
smart_contract_address | true | Smart contract address.
date_interval| false | Date interval for the report. Valid Date Intervals: <code>today</code> <code>yesterday</code> <code>last_7_days</code> <code>this_month</code> <code>last_month</code> <code>last_30_days</code> <code>last_90_days</code> <code>year_to_date</code> <code>life_time</code>
address | false | Used to filter the report by address


<aside class="success">
Remember — Without a date_interval parameter, the query will return data for the last 7 days!
</aside>

## Volume Report

```shell
curl -X GET "https://chainbeat.io/api/v2/network/smart_contract_address/volumes.json" -H "Authorization: Bearer api_token"
```

> The above command returns JSON structured like this:

```json
{
   "volume":[
      {
         "date":"2021-09-27",
         "value":14721092.02
      },
      {
         "date":"2021-09-28",
         "value":11741912.31
      },
      {
         "date":"2021-09-29",
         "value":9411820.76
      },
      {
         "date":"2021-09-30",
         "value":15780333.17
      },
      {
         "date":"2021-10-01",
         "value":17238040.7
      },
      {
         "date":"2021-10-02",
         "value":18391915.44
      },
      {
         "date":"2021-10-03",
         "value":12138204.44
      }
   ],
   "top_addresses":[
      {
         "position":1,
         "address":"0x56d0ae52f33f7c2e38e92f6d20b8ccfd7dc318ce",
         "sum_volume":"9,811,673.73",
         "percent_of_total_volume":"9.87",
         "transfers_count":9561
      },
      {
         "position":2,
         "address":"Contract: 0xaf106f8d4756490e7069027315f4886cc94a8f73",
         "sum_volume":"8,760,875.27",
         "percent_of_total_volume":"8.81",
         "transfers_count":4960
      },
      {
         "position":3,
         "address":"0x1b7a4130827f8531626baeee53fe02ea1c8865b7",
         "sum_volume":"7,683,501.69",
         "percent_of_total_volume":"7.73",
         "transfers_count":580
      },
      {
         "position":4,
         "address":"0xb07535cc39af3f1baf98e3c723ac1e8265ab614f",
         "sum_volume":"7,135,355.31",
         "percent_of_total_volume":"7.18",
         "transfers_count":368
      },
      {
         "position":5,
         "address":"0xadd7c542667728e6b91dc091a6def2489f2de35c",
         "sum_volume":"4,553,173.62",
         "percent_of_total_volume":"4.58",
         "transfers_count":12835
      },
      {
         "position":6,
         "address":"0xa00b0540f43e00a634d016a31b0a39d95170e6bf",
         "sum_volume":"3,870,772.53",
         "percent_of_total_volume":"3.89",
         "transfers_count":92
      },
      {
         "position":7,
         "address":"0xa5037661989789d0310ac2b796fa78f1b01f195d",
         "sum_volume":"3,675,301.53",
         "percent_of_total_volume":"3.70",
         "transfers_count":1029
      },
      {
         "position":8,
         "address":"0x42b64299dc52856d9a80abf48af6d65ec6d556f8",
         "sum_volume":"3,631,552.00",
         "percent_of_total_volume":"3.65",
         "transfers_count":140
      },
      {
         "position":9,
         "address":"0x4b14ec915133df0c0302eaa0c93736abc5ad8619",
         "sum_volume":"3,110,853.14",
         "percent_of_total_volume":"3.13",
         "transfers_count":1914
      },
      {
         "position":10,
         "address":"0x4c9c42dcc8062528d87266be769bc21d9a26bdcc",
         "sum_volume":"3,035,357.78",
         "percent_of_total_volume":"3.05",
         "transfers_count":5326
      }
   ],
   "top_transactions":[
      {
         "position":1,
         "transaction_hash":"0x4a6ff6d6b119b5ac62afc6c5fef3528b96bfa1bda1fca374c5c671e4b53e0eed",
         "transaction_timestamp":"2021-09-28T07:11:08.000Z",
         "from_address":"0xb23bdc9b1459cd37624fd6065984eda808a59b4a",
         "amount":"1,001,600.00"
      },
      {
         "position":2,
         "transaction_hash":"0x51e058b700655d588cc2898f85a78c6656f37d6743e746b500a64cd5cee4a7d8",
         "transaction_timestamp":"2021-09-28T06:17:08.000Z",
         "from_address":"0xc32cbaf3d44da6fbc761289b871af1a30cc7f993",
         "amount":"1,001,600.00"
      },
      {
         "position":3,
         "transaction_hash":"0x792c5aff8cd2d2ca36d5bcd64c3afb50e22b373cbab460ab5ee9e96721c467a2",
         "transaction_timestamp":"2021-09-27T14:52:32.000Z",
         "from_address":"0x1e0f3bfc926c4c4b98d428de9bbf0e5fa5909063",
         "amount":"950,000.00"
      },
      {
         "position":4,
         "transaction_hash":"0xa0991f34570196eb19edc89ea66094b486f3c3440a2f9bfc32bf9fecc161fceb",
         "transaction_timestamp":"2021-09-27T16:11:18.000Z",
         "from_address":"0xb23bdc9b1459cd37624fd6065984eda808a59b4a",
         "amount":"950,000.00"
      },
      {
         "position":5,
         "transaction_hash":"0x40edaaddc3d03b07e4b19fffda11f9f6b04aea3df3890572abd443432641ab46",
         "transaction_timestamp":"2021-10-01T15:56:30.000Z",
         "from_address":"0x0c23e7e1c8b18ddbb451d7f46168ee445f8a0b61",
         "amount":"602,247.90"
      },
      {
         "position":6,
         "transaction_hash":"0xc3876845122af62fe56725edfce5f0b171f7528cbdd67f7ed07ccff68d4bd6b1",
         "transaction_timestamp":"2021-10-01T14:44:45.000Z",
         "from_address":"0x1b7a4130827f8531626baeee53fe02ea1c8865b7",
         "amount":"602,237.25"
      },
      {
         "position":7,
         "transaction_hash":"0xd02904de169bcbb8bc25a448e6c2a45686046b88bb95d3c908be4d8e50ac87a9",
         "transaction_timestamp":"2021-10-01T08:34:00.000Z",
         "from_address":"0x13a559c8d8fa0acbf06897aea6da91f344da3ec6",
         "amount":"501,000.00"
      },
      {
         "position":8,
         "transaction_hash":"0x05f2a445b75e8de499a111aaee91bcc8c8e2d74079849e9605d1b17f7824e0ab",
         "transaction_timestamp":"2021-10-01T08:33:05.000Z",
         "from_address":"0xaf106f8d4756490e7069027315f4886cc94a8f73",
         "amount":"501,000.00"
      },
      {
         "position":9,
         "transaction_hash":"0x5cea4a98d43b5a1b6808c60e02bd649bc0094d52679bd8810205a924ac80ee90",
         "transaction_timestamp":"2021-09-27T13:53:06.000Z",
         "from_address":"0xaf106f8d4756490e7069027315f4886cc94a8f73",
         "amount":"501,000.00"
      },
      {
         "position":10,
         "transaction_hash":"0x908b6a81272740df7b9d5f265c0e8c1b50f7e2a8766571b5b73062fc4a76303b",
         "transaction_timestamp":"2021-09-27T13:55:16.000Z",
         "from_address":"0x13a559c8d8fa0acbf06897aea6da91f344da3ec6",
         "amount":"501,000.00"
      }
   ],
   "sum_value":99423318.84,
   "successful_transactions":null,
   "avg_per_day":14203331.262857143,
   "max_per_day":18391915.44,
   "min_per_day":9411820.76,
   "usd_volume":0,
   "usd_per_day":0,
   "total_volume":99423318842011047738027627,
   "start_date":"2021-09-27T00:00:00.000Z",
   "end_date":"2021-10-03T23:59:59.999Z"
}
```

This endpoint retrieves Volume report.

### HTTP Request

`GET https://chainbeat.io/api/v2/network/smart_contract_address/volumes.json`

### URL Parameters

Parameter | required parameter? | Description
--------- | ------- | -----------
network | true | Smart contract network.
smart_contract_address | true | Smart contract address.
date_interval| false | Date interval for the report. Valid Date Intervals: <code>today</code> <code>yesterday</code> <code>last_7_days</code> <code>this_month</code> <code>last_month</code> <code>last_30_days</code> <code>last_90_days</code> <code>year_to_date</code> <code>life_time</code>
address | false | Used to filter the report by address

<aside class="success">
Remember — Without a date_interval parameter, the query will return data for the last 7 days!
</aside>
