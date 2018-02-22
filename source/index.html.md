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

# Endpoints Groups

## CREATE GROUP

> Example Request

```shell
curl -X POST "https://api.kawaa.co/groups" \
  -d '{
    "name": "My Group",
    "description": "some description",
    "tags": [ 123 ],
    "avatar": 234,
    "extra_infos": [
        { "name": "website", "title": { "fr": "Site web", "en": "Website" }, "value": "www.kawaa.co" },
        { "name": "opening_hours", "title": { "fr": "Horaires d'\''overture", "en": "Opening hours" }, "value": "Tous les jours entre 10h et 22h" }
    ],
    "new_location": {
      "name": "Sensespace",
      "address": "11 Rue Biscornet",
      "city": "Paris",
      "lat": 48.8504762,
      "lng": 2.3696405,
      "zip_code": "75012",
      "country": "FR"
    },
    "status": "published"
  }' \
  -H "X-Api-Key: API_KEY" \
  -H "X-Auth-Key: YOUR_AUTH_KEY" \
  -H "Content-Type: application/json"
```

> Make sure to replace `API_KEY` with your API key and `YOUR_AUTH_KEY` with the key obtained on `POST /account/login`.

**Endpoint**

`POST /groups` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Auth key(see [above](#authentication)). | Yes | string |
| name | body | Group's name. | Yes | string |
| description | body | Group's description. | No | string |
| administrator | body | ID of an user, to be assigned as group's administrator. If not given the current user becomes group's admin. | No | integer |
| tags | body | Array of tags' IDs. | No | array[integer] |
| avatar | body | Resource's ID, to be set as group's avatar (obtained from [`POST /resources`](#create-resource)). | No | integer |
| new_avatar | body | Avatar of the group. | No | file |
| photos | body | Resources' IDs, to be set as group's photos (obtained from [`POST /resources`](#create-resource)). | No | array[integer] |
| extra_infos | body | Array of INFO objects used to better describe the group (see in **NOTES** below)| No | array[INFO] |
| place | body | *true* if is a place or *false* if not. | No | boolean |
| new_location | body | LOCATION object used to localize the group (see in **NOTES** below). | No | LOCATION |
| category | body | If the group is a place, it could have one of the following categories: *bar, cafe, restaurant, museum, hotel, tiers, coworking_space or other* | No | string |
| status | body | Group's status could be: *published or draft*. | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | Create a group. |

**NOTES**

- mutually exclusive params:
  - `avatar` and `new_avatar`

- *LOCATION* object:

| Name | Description | Required | Type |
| ---- | ----------- | -------- | ---- |
| name | name of the location | No | string |
| lat | latitude of the location | Yes | float |
| lng | longitude of the location | Yes | float |
| area | range of the influenced area of the location (in km) | No | string |
| address | address of the location | No | string |
| city | city of the location | No | string |
| zip_code | zip code of the location | No | string |
| country | 2-letter code of the country of the location | Yes | string |

- *INFO* object:

| Name | Description | Required | Type |
| ---- | ----------- | -------- | ---- |
| name | unique identifier of the field (for ex: *telephone*, *website*, *contact_person*) | No | string |
| title | Field's title to be desplayed in different languages (see below) | No | TRANSLATION |
| value | Field's value (for ex: *0912345565*, *mysite.com*, *John Doe*) | No | string |

- *TRANSLATION* is a key/value object. The key is a 2-letter code representing a language (for ex: *fr*, *en*) and the value is the corresponding translation. For ex: `{ 'fr': 'Numéro de téléphone', 'en': 'Phone number' }`

## CREATE GROUP LINK

**Description**

Create a relation between two groups (origin and target). The origin group is the one initiating the relation. Depending on the type of the link there could be a transfer of meets between both groups. For ex. if one organizes a meet in the origin group, the meet is automatically linked to the target group.

**Endpoint**

`POST /groups/:id/links` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Auth key(see [above](#authentication)). | Yes | string |
| id | path | ID of the origin group. | Yes | integer |
| target_id | body | ID of the target group. | Yes | integer |
| link | body | Type of the link. It could be *hierachical* (there's a transfer of meets from origin to target) or *neutral* (there's no trasnfer) | No | string |
| flag | body | Flag used to regroup different kinds of group_links (for ex: *partner*, *sponsor*). | No | string |
| symbol | body | String represantation of a symbol used to visaully differentiate the kinds of group_links (most often on the maps). | No | string |
| color | body | Hex represantation of a color used to visaully differentiate the kinds of group_links (most often on the maps). | No | string |
| title | body | See **NOTES**. | No | TRANSLATION |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | Create a group link. |

**NOTES**

- *TRANSLATION* is a key/value object. The key is a 2-letter code representing a language (for ex: *fr*, *en*) and the value is the corresponding translation. For ex: `{ 'fr': 'Numéro de téléphone', 'en': 'Phone number' }`

# Endpoints Resources

## CREATE RESOURCE

**Description**

Upload photos and avatars.

> Example Request

```shell
curl -X POST "https://api.kawaa.co/resources" \
  -d '{
    "title": "My avatar",
    "slug": "https://kawaa.s3.eu-central-1.amazonaws.com/api/uploads/resource/file/23/140520_75GaiteLyrique_2.jpg",
    "category": "group_avatar"
  }' \
  -H "X-Api-Key: API_KEY" \
  -H "X-Auth-Key: YOUR_AUTH_KEY" \
  -H "Content-Type: application/json"
```

> Make sure to replace `API_KEY` with your API key and `YOUR_AUTH_KEY` with the key obtained on `POST /account/login`.

**Endpoint**

`POST /resources` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Auth key(see [above](#authentication)). | Yes | string |
| title | body | Resource's title. | No | string |
| file | body | File | No | file |
| slug | body | Resource's external url. | No | string |
| category | body | Resource's category. It could be one of the following: *self_kawaa, user_avatar, group_avatar, group_photo, meet_photo, comment_upload, animation_cover, animation_photo, animation_video, animation_doc, post_photo* | No | string |

**NOTES**

- mutually exclusive params:
  - `file` and `slug`

All other available endpoints are documented and accessible [here](https:/api.kawaa.co/documentation).
