---
title: Kawaa API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:

search: true

---

# Overview

Welcome to the Kawaa API!

You can use our [REST](https://en.wikipedia.org/wiki/Representational_state_transfer) API to access Kawaa API endpoints. 
JSON is returned by all API responses, including errors.

All requests should be done over **HTTPS**, otherwise they will fail.

# Authentication

Kawaa uses two types of keys to allow access to the API: `X-Api-Key` and `X-Auth-Key`.

## X-Api-Key

> Example Request

```shell
curl "https://api.kawaa.co/meets"
  -H "X-Api-Key: YOUR_API_KEY"
```

> Make sure to replace `YOUR_API_KEY` with your API key.

You can get a new API key by contacting [cto@kawaa.co](mailto:cto@kawaa.co).

We expect for the API key to be included in all API requests to the server in a header that looks like the following:

`X-Api-Key: YOUR_API_KEY`

<aside class="notice">
You must replace <code>YOUR_API_KEY</code> with your API key.
</aside>

## X-Auth-Key

> Example request exposing sensitive info

```shell
curl "https://api.kawaa.co/account"
  -H "X-Api-Key: YOUR_API_KEY"
  -H "X-Auth-Key: YOUR_AUTH_KEY"
```
Some endpoints require stricter authetification because they expose some sensitive information or they give access to writable resources.
In that case you should use `X-Auth-Key` in your requests' headers alongside with your `X-Api-Key`. Your `X-Auth-Key` is personal and shouldn't be communicated anywhere.
It's created on registeration a new account on Kawaa. You can obtain it by:

`curl -X POST https://api.kawaa.co/account/login
	-d "email=YOUR_EMAIL@FOO.COM&password=YOUR_PASSWORD" -H "X-Api-Key: YOUR_API_KEY" `

<aside class="notice">
You must replace <code>YOUR_API_KEY</code> with your API key, <code>YOUR_EMAIL@FOO.COM</code> and <code>YOUR_PASSWORD</code> with the email and password you used when creating your account on Kawaa.
</aside>

# Pagination

> Example Request

```shell
curl "https://api.kawaa.co/meets"
  -H "X-Api-Key: YOUR_API_KEY"
```

> Example Response

```json
{
	"meta": {
		"limit": 20,
		"next": "?limit=20&offset=20",
		"offset": 0,
		"previous": null,
		"total": 3150
	},
	"meets": [
		# meets here
	]
}
```

All GET endpoints which return a collection support cursor based pagination with pagination information inside a `meta` object.
It contains the following fields:

- `limit`: A limit on the number of retrieved items (for this call).
- `offset`: Index of the first item in the retrieved portion. That index is relative to the whole collection.
	- _If `offset` is **0**, it means that the first item in the retrived portion is at **first** position in the whole collection._
- `total`: Total number of items in the collection.
- `next`: There's no need to construct by yourself the query params to retrieve the next portion of items. The API returns for you a string to be appended to your next call.
If it's `null`, there're no more items to be retrieved.
	- _Taking the example on the right, our next call should be `https://api.kawaa.co?limit=20&offset=20`_
- `previous`: The same as `next` but for previous items.

## Requests with pagination

> Example Request

```shell
curl "https://api.kawaa.co/meets?limit=20&offset=40"
  -H "X-Api-Key: YOUR_API_KEY"
```

All GET endpoints supporting pagination accept two **optional** parameters:

Parameter | Default | Description (see above)
--------- | ------- | -----------
limit | 20 | Limit of the items to be retrieved
offset | 0 | Position of the item from which we start counting

# Endpoints

All available endpoints are documented and accessible [here](https:/api.kawaa.co/documentation).
