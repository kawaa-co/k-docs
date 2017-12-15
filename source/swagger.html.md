--- 

title: Kawaa API 

language_tabs: 
   - shell 

toc_footers: 
   - <a href='#'>Sign Up for a Developer Key</a> 
   - <a href='https://github.com/lavkumarv'>Documentation Powered by lav</a> 

includes: 
   - errors 

search: true 

--- 

# Introduction 

**Version:** 0.0.1 

# /ACCOUNT
## ***GET*** 

**Summary:** Return current user

**Description:** Return current user

### HTTP Request 
`***GET*** /account` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| admin | query | Return infos on number of organized meets, administrated groups and places. | No | boolean |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Return current user |

## ***POST*** 

**Summary:** Create user account

**Description:** Create user account

### HTTP Request 
`***POST*** /account` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| email | formData | Email  address of the user. | Yes | string |
| password | formData | Password  that the user has chosen. | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | Create user account |

## ***PUT*** 

**Summary:** Update user account

**Description:**         */!\ Object (JSON) and Array can not be used with this interface, and will return a format error.*


### HTTP Request 
`***PUT*** /account` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| nickname | formData | Nickname of the user. | No | string |
| first_name | formData | First_name of the user. | No | string |
| last_name | formData | Last_name of the user. | No | string |
| password | formData | Password that the user has chosen. | No | string |
| email | formData | Email address of the user. | No | string |
| locations | form | Array of locations of the user. | No | array |
| new_location[name] | formData | name of the location | No | string |
| new_location[lat] | formData | the latitude of the location | Yes | float |
| new_location[lng] | formData | the longitude of the location | Yes | float |
| new_location[area] | formData | the range of the influenced area of the location (in km) | No | string |
| new_location[address] | formData | the address of the location | No | string |
| new_location[city] | formData | the city of the location | No | string |
| new_location[zip_code] | formData | the zip code of the location | No | string |
| new_location[country] | formData | the two letter code of the country of the location | Yes | string |
| avatar | formData | Id of the image of the user. | No | integer |
| new_avatar | formData | File of image of the user. | No | file |
| add_tag | formData | Id of the tag which will be added. | No | integer |
| tags | form | Array of tag’s id for the group. | No | array |
| locale | formData | Prefered language for mail and interface | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Update user account |

## ***DELETE*** 

**Summary:** Delete account.

**Description:** Delete account.

### HTTP Request 
`***DELETE*** /account` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | Delete account. |

# /ACCOUNT/FORGOT_PASSWORD
## ***POST*** 

**Summary:** Send token for password reset.

**Description:** Send token for password reset.

### HTTP Request 
`***POST*** /account/forgot_password` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| email | formData | Email address of the user. | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | Send token for password reset. |

## ***GET*** 

**Summary:** Check token for password reset.

**Description:** Check token for password reset.

### HTTP Request 
`***GET*** /account/forgot_password` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| token | query | Token sent to the user. | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Check token for password reset. |

## ***PUT*** 

**Summary:** Send token for password reset.

**Description:** Send token for password reset.

### HTTP Request 
`***PUT*** /account/forgot_password` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| token | formData | Token sent to the user. | Yes | string |
| password | formData | New password. | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Send token for password reset. |

# /ACCOUNT/LOGIN
## ***POST*** 

**Summary:** Login to account.

**Description:** Login to account.

### HTTP Request 
`***POST*** /account/login` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| password | formData | Password  that the user has chosen. | Yes | string |
| email | formData | Email  address of the user. | Yes | string |
| admin | formData | Return infos on number of organized meets, administrated groups and places. | No | boolean |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | Login to account. |

## ***GET*** 

**Summary:** Check login validity

**Description:** Check login validity

### HTTP Request 
`***GET*** /account/login` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Check login validity |

# /ACCOUNT/PROVIDER_LOGIN
## ***POST*** 

**Summary:** Login to account with a provider.

**Description:** Login to account with a provider.

### HTTP Request 
`***POST*** /account/provider_login` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| provider | formData | The login provider. | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | Login to account with a provider. |

# /ACCOUNT/SETTINGS
## ***GET*** 

**Summary:** Get users's settings (about notifications, etc.)

**Description:** Get users's settings (about notifications, etc.)

### HTTP Request 
`***GET*** /account/settings` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get users's settings (about notifications, etc.) |

## ***PUT*** 

**Summary:** Update users's settings (about notifications, etc.)

**Description:** Update users's settings (about notifications, etc.)

### HTTP Request 
`***PUT*** /account/settings` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Update users's settings (about notifications, etc.) |

# /ACCOUNT/GROUPS
## ***GET*** 

**Summary:** Get information about groups and places related to given user

**Description:** Get information about groups and places related to given user

### HTTP Request 
`***GET*** /account/groups` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| place | query | true for returning only places and false fror only groups. Keep empty for unfiltered result. | No | boolean |
| role | query | User's role in the groups (member, administrator). | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get information about groups and places related to given user |

# /ACCOUNT/MEMBERS
## ***GET*** 

**Summary:** List all memberships of the user

**Description:** List all memberships of the user

### HTTP Request 
`***GET*** /account/members` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | List all memberships of the user |

# /ACCOUNT/MEETS
## ***GET*** 

**Summary:** Get list of meets which user is/was involved (participations or organisations)

**Description:** Get list of meets which user is/was involved (participations or organisations)

### HTTP Request 
`***GET*** /account/meets` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| time_scope | query | _past_ or _future_ ; keep empty for an unfiltered return. | No | string |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| lat | query |  | No | float |
| lng | query |  | No | float |
| range | query | range in kilometers | No | float |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get list of meets which user is/was involved (participations or organisations) |

# /ACCOUNT/MEETSHIPS
## ***GET*** 

**Summary:** Get list of meetships for an user.

**Description:** Get list of meetships for an user.

### HTTP Request 
`***GET*** /account/meetships` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| role | query | User's role in the groups (staff, administrator). | Yes | string |
| status | query | Status of meetships to be returned. | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get list of meetships for an user. |

# /ACCOUNT/GROUPS_MEETS
## ***GET*** 

**Summary:** Get list of meets belonging to user's groups where is not involved

**Description:** Get list of meets belonging to user's groups where is not involved

### HTTP Request 
`***GET*** /account/groups_meets` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| time_scope | query | _past_ or _future_ ; keep empty for an unfiltered return. | No | string |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| lat | query |  | No | float |
| lng | query |  | No | float |
| range | query | range in kilometers | No | float |
| scope | query | To filter the request (only `unregistred` are now available) | No | string |
| status | query | Filter by status of meets. | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get list of meets belonging to user's groups where is not involved |

# /ACCOUNT/SUGGESTED_MEETS
## ***GET*** 

**Summary:** Suggested meets for user

**Description:** Suggested meets for user

### HTTP Request 
`***GET*** /account/suggested_meets` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| lat | query |  | No | float |
| lng | query |  | No | float |
| range | query | range in kilometers | No | float |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Suggested meets for user |

# /ACCOUNT/REGISTERED_MEETS
## ***GET*** 

**Summary:** Meets where user is registered

**Description:** Meets where user is registered

### HTTP Request 
`***GET*** /account/registered_meets` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| time_scope | query | _past_ or _future_ ; keep empty for an unfiltered return. | No | string |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| status | query | Filter by status of meets. | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Meets where user is registered |

# /ACCOUNT/ORGANIZED_MEETS
## ***GET*** 

**Summary:** Meets organized by specified user

**Description:** Meets organized by specified user

### HTTP Request 
`***GET*** /account/organized_meets` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| time_scope | query | _past_ or _future_ ; keep empty for an unfiltered return. | No | string |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| status | query | Filter by status of meets. | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Meets organized by specified user |

# /ACCOUNT/COMMENTS
## ***GET*** 

**Summary:** Get list of comments

**Description:** Get list of comments

### HTTP Request 
`***GET*** /account/comments` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get list of comments |

# /ACCOUNT/RECEIVED_INVITATIONS
## ***GET*** 

**Summary:** Get list of user's received invitations

**Description:** Get list of user's received invitations

### HTTP Request 
`***GET*** /account/received_invitations` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get list of user's received invitations |

# /ACCOUNT/SENT_INVITATIONS
## ***GET*** 

**Summary:** Get list of user's sent invitations

**Description:** Get list of user's sent invitations

### HTTP Request 
`***GET*** /account/sent_invitations` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| status | query | To filter the request (accepted, refused, pending, canceled) | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get list of user's sent invitations |

# /USERS
## ***GET*** 

**Summary:** Return users list

**Description:** Return users list

### HTTP Request 
`***GET*** /users` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Return users list |

## ***POST*** 

**Summary:** Create new user in the system.

**Description:** Create new user in the system.

### HTTP Request 
`***POST*** /users` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| password | formData |  | No | string |
| email | formData |  | No | string |
| nickname | formData |  | No | string |
| first_name | formData |  | No | string |
| last_name | formData |  | No | string |
| locale | formData | Prefered language for mail and interface | No | string |
| status | formData | Status of the user. | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | Create new user in the system. |

# /USERS/{ID}
## ***GET*** 

**Summary:** Get information about an user

**Description:** Get information about an user

### HTTP Request 
`***GET*** /users/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | User ID | Yes | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get information about an user |

## ***PUT*** 

**Summary:** Update information about an user

**Description:**           */!\ Object (JSON) and Array can not be used with this interface, and will return a format error.*


### HTTP Request 
`***PUT*** /users/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | User ID | Yes | integer |
| nickname | formData | Nickname of the user. | No | string |
| first_name | formData | First_name of the user. | No | string |
| last_name | formData | Last_name of the user. | No | string |
| password | formData | Password  that the user has chosen. | No | string |
| email | formData | Email  address of the user. | No | string |
| locations | form | Array of locations of the user. | No | array |
| avatar | formData | Id of the image of the user. | No | integer |
| new_avatar | formData | File of image of the user. | No | file |
| add_tag | formData | The id of the tag which will be added. | No | integer |
| tags | form | Array of tag’s id for the group. | No | array |
| locale | formData | Prefered language for mail and interface | No | string |
| status | formData |  | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Update information about an user |

## ***DELETE*** 

**Summary:** Delete an user

**Description:** Delete an user

### HTTP Request 
`***DELETE*** /users/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | User ID | Yes | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | Delete an user |

# /USERS/{ID}/GROUPS
## ***GET*** 

**Summary:** Get information about groups and places related to given user

**Description:** Get information about groups and places related to given user

### HTTP Request 
`***GET*** /users/{id}/groups` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | User ID | Yes | integer |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| role | query | User's role in the groups (member, administrator). | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get information about groups and places related to given user |

# /USERS/{ID}/MEMBERS
## ***GET*** 

**Summary:** Get information about groups and places related to given user

**Description:** Get information about groups and places related to given user

### HTTP Request 
`***GET*** /users/{id}/members` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | User ID | Yes | integer |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get information about groups and places related to given user |

# /USERS/{ID}/MEETS
## ***GET*** 

**Summary:** Get list of meets in which user is/was involved (participations or organisations).

**Description:** Get list of meets in which user is/was involved (participations or organisations).

### HTTP Request 
`***GET*** /users/{id}/meets` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | User ID | Yes | integer |
| time_scope | query | _past_ or _future_ ; keep empty for an unfiltered return. | No | string |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| lat | query |  | No | float |
| lng | query |  | No | float |
| range | query | range in kilometers | No | float |
| role | query | User's role in the meets (organizator, participant). | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get list of meets in which user is/was involved (participations or organisations). |

# /USERS/{ID}/GROUPS_MEETS
## ***GET*** 

**Summary:** Get list of meets belonging to user's groups where is not involved (deprecated)

**Description:** Get list of meets belonging to user's groups where is not involved (deprecated)

### HTTP Request 
`***GET*** /users/{id}/groups_meets` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | User ID | Yes | integer |
| time_scope | query | _past_ or _future_ ; keep empty for an unfiltered return. | No | string |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| lat | query |  | No | float |
| lng | query |  | No | float |
| range | query | range in kilometers | No | float |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get list of meets belonging to user's groups where is not involved (deprecated) |

# /USERS/{ID}/SUGGESTED_MEETS
## ***GET*** 

**Summary:** Suggested meets for user

**Description:** Suggested meets for user

### HTTP Request 
`***GET*** /users/{id}/suggested_meets` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | User ID | Yes | integer |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| lat | query |  | No | float |
| lng | query |  | No | float |
| range | query | range in kilometers | No | float |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Suggested meets for user |

# /USERS/{ID}/REGISTERED_MEETS
## ***GET*** 

**Summary:** Meets where user is registered (deprecated, use /user/ID/meets?role=participant instead)

**Description:** Meets where user is registered (deprecated, use /user/ID/meets?role=participant instead)

### HTTP Request 
`***GET*** /users/{id}/registered_meets` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | User ID | Yes | integer |
| time_scope | query | _past_ or _future_ ; keep empty for an unfiltered return. | No | string |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Meets where user is registered (deprecated, use /user/ID/meets?role=participant instead) |

# /USERS/{ID}/ORGANIZED_MEETS
## ***GET*** 

**Summary:** Meets organized by specified user (deprecated, use /user/ID/meets?role=organizator instead)

**Description:** Meets organized by specified user (deprecated, use /user/ID/meets?role=organizator instead)

### HTTP Request 
`***GET*** /users/{id}/organized_meets` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | User ID | Yes | integer |
| time_scope | query | _past_ or _future_ ; keep empty for an unfiltered return. | No | string |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Meets organized by specified user (deprecated, use /user/ID/meets?role=organizator instead) |

# /USERS/{ID}/COMMENTS
## ***GET*** 

**Summary:** Get list of comments

**Description:** Get list of comments

### HTTP Request 
`***GET*** /users/{id}/comments` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | User ID | Yes | integer |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get list of comments |

# /USERS/{ID}/RECEIVED_INVITATIONS
## ***GET*** 

**Summary:** Get list of user's invitations

**Description:** Get list of user's invitations

### HTTP Request 
`***GET*** /users/{id}/received_invitations` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | User ID | Yes | integer |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get list of user's invitations |

# /USERS/{ID}/SENT_INVITATIONS
## ***GET*** 

**Summary:** Get list of user's invitations

**Description:** Get list of user's invitations

### HTTP Request 
`***GET*** /users/{id}/sent_invitations` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | User ID | Yes | integer |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| status | query | To filter the request (accepted, refused, pending, canceled) | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get list of user's invitations |

# /GROUPS
## ***GET*** 

**Summary:** Return groups list

**Description:** Return groups list

### HTTP Request 
`***GET*** /groups` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| place | query | 1 to search only place, 0 for group only, and not specified for both. | No | integer |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| lat | query |  | No | float |
| lng | query |  | No | float |
| range | query | range in kilometers | No | float |
| q | query | an url-encoded request with tags or words separated by circumflex char ( circumflex: '^') | No | string |
| c | query | Category to return (bar, cafe, restaurant, museum, hotel, tiers, coworking_space, other) | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Return groups list |

## ***POST*** 

**Summary:** Create a group.

**Description:**         */!\ Object (JSON) and Array can not be used with this interface, and will return a format error.*


### HTTP Request 
`***POST*** /groups` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| name | formData | The name of the group | Yes | string |
| description | formData | Description of the group/place | No | string |
| administrator | formData | User's id, Administrator of the group | No | integer |
| place | formData | 'true' if is a place or 'false' if not. | No | boolean |
| tags | form | Id of Tags for the group | No | array |
| avatar | formData | Avatar's ID of the group. | No | integer |
| new_avatar | formData | Avatar of the group. | No | file |
| photos | form | Photos of the group. | No | array |
| new_location[name] | formData | name of the location | No | string |
| new_location[lat] | formData | the latitude of the location | Yes | float |
| new_location[lng] | formData | the longitude of the location | Yes | float |
| new_location[area] | formData | the range of the influenced area of the location (in km) | No | string |
| new_location[address] | formData | the address of the location | No | string |
| new_location[city] | formData | the city of the location | No | string |
| new_location[zip_code] | formData | the zip code of the location | No | string |
| new_location[country] | formData | the two letter code of the country of the location | Yes | string |
| moderation | formData | The group can be of 3 types: open, moderate, closed | No | string |
| offer | formData | The id of the chosen offer | No | integer |
| category | formData | Optional, category of the group (bar, cafe, restaurant, museum, hotel, tiers, coworking_space, other) | No | string |
| status | formData | The status of the group (disabled, published, draft or suspended). | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | Create a group. |

# /GROUPS/{ID}
## ***PUT*** 

**Summary:** Update a group.

**Description:**         */!\ Object (JSON) and Array can not be used with this interface, and will return a format error.*


### HTTP Request 
`***PUT*** /groups/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Group ID | Yes | string |
| name | formData | The name of the group | No | string |
| description | formData | The name of the place | No | string |
| avatar | formData | Resource's id, avatar of the group | No | integer |
| new_avatar | formData | File, Picture of the avatar | No | file |
| place | formData | true if is a place or false if not. | No | boolean |
| tags | form | Array of tags'is for the group | No | array |
| add_tag | formData | Id of a tag for the group | No | integer |
| photos | form | photos of the group | No | array |
| location | formData | id of the location of the group. | No | integer |
| new_location[name] | formData | name of the location | No | string |
| new_location[lat] | formData | the latitude of the location | Yes | float |
| new_location[lng] | formData | the longitude of the location | Yes | float |
| new_location[area] | formData | the range of the influenced area of the location (in km) | No | string |
| new_location[address] | formData | the address of the location | No | string |
| new_location[city] | formData | the city of the location | No | string |
| new_location[zip_code] | formData | the zip code of the location | No | string |
| new_location[country] | formData | the two letter code of the country of the location | Yes | string |
| moderation | formData | The group can be of 3 types, open, moderate, closed | No | string |
| offer | formData | The id of the chosen offer | No | integer |
| category | formData | Optional, category of the group (bar, cafe, restaurant, museum, hotel, tiers, coworking_space, other) | No | string |
| status | formData | The status of the group (disabled, published, draft or suspended). | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Update a group. |

## ***DELETE*** 

**Summary:** Delete a group.

**Description:** Delete a group.

### HTTP Request 
`***DELETE*** /groups/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Group ID | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | Delete a group. |

## ***GET*** 

**Summary:** Return a group

**Description:** Return a group

### HTTP Request 
`***GET*** /groups/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| id | path | Place ID | Yes | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Return a group |

# /GROUPS/{ID}/MEMBER
## ***POST*** 

**Summary:** A user joins a group. User will get inserted in the members table and status put accordingly.

**Description:**           */!\ Object (JSON) and Array can not be used with this interface, and will return a format error.*


### HTTP Request 
`***POST*** /groups/{id}/member` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Group ID | Yes | integer |
| user | formData | User ID | No | integer |
| new_user[email] | formData | Email of the new user. | Yes | string |
| new_user[first_name] | formData | First name of the new user. | No | string |
| new_user[last_name] | formData | Last name of the new user. | No | string |
| options | form | Options is a json hash of several data/fields | No | object |
| status | formData | Member's status | No | string |
| role | formData | Role of the Member (member, staff, administrator) | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | A user joins a group. User will get inserted in the members table and status put accordingly. |

## ***GET*** 

**Summary:** Get a Member

**Description:** Get a Member

### HTTP Request 
`***GET*** /groups/{id}/member` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Group ID | Yes | integer |
| member | query | Member ID | No | integer |
| user | query | or User ID | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get a Member |

## ***PUT*** 

**Summary:** Update a member. Member's status will have to be modified in the members table.

**Description:**           */!\ Object (JSON) and Array can not be used with this interface, and will return a format error.*


### HTTP Request 
`***PUT*** /groups/{id}/member` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Group ID | Yes | integer |
| member | formData | Member ID | No | integer |
| user | formData | or User ID | No | integer |
| status | formData | Member's status | No | string |
| options | form | Options is a json hash of several data/fields | No | object |
| role | formData | Role of the Member (member, staff, administrator) | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Update a member. Member's status will have to be modified in the members table. |

## ***DELETE*** 

**Summary:** Leave a group. User status will have to be modified in the members table.

**Description:** Leave a group. User status will have to be modified in the members table.

### HTTP Request 
`***DELETE*** /groups/{id}/member` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Group ID | Yes | integer |
| member | query | Member ID | No | integer |
| user | query | or User ID | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | Leave a group. User status will have to be modified in the members table. |

# /GROUPS/{ID}/MEMBERS
## ***GET*** 

**Summary:** Return group members

**Description:** Return group members

### HTTP Request 
`***GET*** /groups/{id}/members` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Group ID | Yes | integer |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| by_name | query | Sort by last name. | No | string |
| by_organizations_count | query | Sort by num of organized meets. | No | string |
| by_registrations_count | query | Sort by num of participated meets. | No | string |
| role | query | Return members according their role, if empty return all. | No | string |
| q | query | an url-encoded request for first_name, last_name and email look-up. | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Return group members |

# /GROUPS/{ID}/COMMENTS
## ***GET*** 

**Summary:** Return group comments

**Description:** Return group comments

### HTTP Request 
`***GET*** /groups/{id}/comments` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| id | path | Group ID | Yes | integer |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| room | query | The room of the comments (0 for all, 1, 2 or 3) | No | integer |
| category | query | 0 for discussion, 1 for opinion (avis). | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Return group comments |

## ***POST*** 

**Summary:** Post a comment for this group

**Description:** Post a comment for this group

### HTTP Request 
`***POST*** /groups/{id}/comments` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Group ID | Yes | integer |
| room | formData | The room of the comment (1 for member, 2 for staff or 3 for admin) | No | integer |
| uploads | form | Resources' ids. | No | array |
| new_upload | formData | New file to upload. | No | file |
| content | formData | The content of the comment | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | Post a comment for this group |

# /GROUPS/{ID}/ANIMATION_FORMATS
## ***GET*** 

**Summary:** Return group's animataion formats.

**Description:** Return group's animataion formats.

### HTTP Request 
`***GET*** /groups/{id}/animation_formats` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| id | path | Group ID | Yes | integer |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Return group's animataion formats. |

# /GROUPS/{ID}/POSTS
## ***GET*** 

**Summary:** Return group's post.

**Description:** Return group's post.

### HTTP Request 
`***GET*** /groups/{id}/posts` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| id | path | Group ID | Yes | integer |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Return group's post. |

# /GROUPS/{ID}/STATS
## ***GET*** 

**Summary:** Get stats of the group.

**Description:** Get stats of the group.

### HTTP Request 
`***GET*** /groups/{id}/stats` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Group ID | Yes | integer |
| interval | query | Time interval in days. Defaults to 7. | No | integer |
| start_date | query | Start of the period in the form of YYYY-MM-DD. Defaults to 1 year ago. | No | string |
| end_date | query | End of the period in the form of YYYY-MM-DD. Defaults to today. | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get stats of the group. |

# /GROUPS/{ID}/LINKS
## ***GET*** 

**Summary:** Get links of a group with other groups/places.

**Description:** Get links of a group with other groups/places.

### HTTP Request 
`***GET*** /groups/{id}/links` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| id | path | Group ID | Yes | integer |
| link | query | Select by type of the link. | No | string |
| as | query |  | No | string |
| status | query | Select by status of the links. | No | string |
| visible | query | Filter by visibility of the link. | No | boolean |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get links of a group with other groups/places. |

## ***POST*** 

**Summary:** Create a relation with another group

**Description:** Create a relation with another group

### HTTP Request 
`***POST*** /groups/{id}/links` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Group ID | Yes | integer |
| target_id | formData | The id of the target group. | Yes | integer |
| link | formData | Set type of the link. | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | Create a relation with another group |

## ***PUT*** 

**Summary:** Validate a relation with another group

**Description:** Validate a relation with another group

### HTTP Request 
`***PUT*** /groups/{id}/links` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Group ID | Yes | integer |
| link_id | formData | Link ID | Yes | integer |
| status | formData | Set status of the link. | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Validate a relation with another group |

## ***DELETE*** 

**Summary:** Delete groups' link.

**Description:** Delete groups' link.

### HTTP Request 
`***DELETE*** /groups/{id}/links` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Group ID | Yes | integer |
| link_id | query | Link ID | Yes | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | Delete groups' link. |

# /GROUPS/{ID}/LINKS/LOCATIONS
## ***GET*** 

**Summary:** Get locations of group's links that have a 'neutral' relationship.

**Description:** Get locations of group's links that have a 'neutral' relationship.

### HTTP Request 
`***GET*** /groups/{id}/links/locations` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| id | path | Group ID | Yes | integer |
| lat | query |  | No | float |
| lng | query |  | No | float |
| range | query | range in kilometers | No | float |
| zip_code | query | The zip code of searched locations. If several, separate them by circumflex char. ( circumflex: '^') | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get locations of group's links that have a 'neutral' relationship. |

# /GROUPS/{ID}/MEETS/AROUND
## ***GET*** 

**Summary:** Get all the group’s meets around a location

**Description:** Get all the group’s meets around a location

### HTTP Request 
`***GET*** /groups/{id}/meets/around` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| id | path | Group ID | Yes | integer |
| time_scope | query | _past_ or _future_ ; keep empty for an unfiltered return. | No | string |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| lat | query |  | No | float |
| lng | query |  | No | float |
| range | query | range in kilometers | No | float |
| by_name | query | Sort by name. | No | string |
| by_participants_count | query | Order by number of participants | No | string |
| q | query | An url-encoded request with tags or words separated by circumflex char. ( circumflex: '^') | No | string |
| zip_code | query | The zip code of searched meets. If several, separate them by circumflex char. ( circumflex: '^') | No | string |
| language | query | The language of the meets (2-charecters language code, ex. 'fr') | No | string |
| status | query | Filter meets by status | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get all the group’s meets around a location |

# /GROUPS/{ID}/MEETS/LOCATIONS
## ***GET*** 

**Summary:** Get all locations of group’s meets.

**Description:** Get all locations of group’s meets.

### HTTP Request 
`***GET*** /groups/{id}/meets/locations` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| id | path | Group ID | Yes | integer |
| time_scope | query | _past_ or _future_ ; keep empty for an unfiltered return. | No | string |
| lat | query |  | No | float |
| lng | query |  | No | float |
| range | query | range in kilometers | No | float |
| q | query | An url-encoded request with tags or words separated by circumflex char. ( circumflex: '^') | No | string |
| zip_code | query | The zip code of searched locations. If several, separate them by circumflex char. ( circumflex: '^') | No | string |
| language | query | The language of the meets (2-charecters language code, ex. 'fr') | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get all locations of group’s meets. |

# /GROUPS/{ID}/MEETS/NEXT
## ***GET*** 

**Summary:** Get all the future meets for a group.

**Description:** Get all the future meets for a group.

### HTTP Request 
`***GET*** /groups/{id}/meets/next` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| id | path | Group ID | Yes | integer |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| by_name | query | Sort by name. | No | string |
| by_participants_count | query | Order by number of participants | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get all the future meets for a group. |

# /GROUPS/{ID}/MEETS/PREVIOUS
## ***GET*** 

**Summary:** Get all the past meets for a group.

**Description:** Get all the past meets for a group.

### HTTP Request 
`***GET*** /groups/{id}/meets/previous` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| id | path | Group ID | Yes | integer |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| by_name | query | Sort by name. | No | string |
| by_participants_count | query | Order by number of participants | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get all the past meets for a group. |

# /GROUPS/{ID}/MEETSHIPS
## ***GET*** 

**Summary:** Get all meetships of a group.

**Description:** Get all meetships of a group.

### HTTP Request 
`***GET*** /groups/{id}/meetships` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Group ID | Yes | integer |
| status | query | Select according to status. | No | string |
| time_scope | query | _past_ or _future_ ; keep empty for an unfiltered return. | No | string |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get all meetships of a group. |

## ***PUT*** 

**Summary:** Change status of a meetship.

**Description:** Change status of a meetship.

### HTTP Request 
`***PUT*** /groups/{id}/meetships` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Group ID | Yes | integer |
| meet_id | formData | Id of the affected meet. | Yes | integer |
| status | formData | Status of the meetship. | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Change status of a meetship. |

# /GROUPS/{ID}/QUERY_FORMS
## ***GET*** 

**Summary:** Get query_forms related to a group.

**Description:** Get query_forms related to a group.

### HTTP Request 
`***GET*** /groups/{id}/query_forms` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| id | path | Group ID | Yes | integer |
| target_type | query |  | Yes | string |
| target_ids | form | An Array of ids narrowing search to related target | No | array |
| kind | query | Select query_forms with the provided kind | No | string |
| category | query | Category of the form. | No | string |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get query_forms related to a group. |

# /INVITATIONS/{TOKEN}
## ***GET*** 

**Summary:** Get Invitation

**Description:** Get Invitation

### HTTP Request 
`***GET*** /invitations/{token}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| token | path | Token assigned to the invitation. | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get Invitation |

## ***PUT*** 

**Summary:** Validate Invitation

**Description:** Validate Invitation

### HTTP Request 
`***PUT*** /invitations/{token}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| token | path | Token assigned to the invitation. | Yes | string |
| validation | formData | Accept invitation. | Yes | boolean |
| nickname | formData | Update nickname of the new user. | No | string |
| first_name | formData | Update firstname of the new user. | No | string |
| last_name | formData | Update lastname of the new user. | No | string |
| password | formData | Update password of the new user. | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Validate Invitation |

# /INVITATIONS/{ID}
## ***DELETE*** 

**Summary:** Cancel Invitation

**Description:** Cancel Invitation

### HTTP Request 
`***DELETE*** /invitations/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Token assigned to the invitation. | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | Cancel Invitation |

# /ANIMATION_FORMATS
## ***GET*** 

**Summary:** Return animations list

**Description:** Return animations list

### HTTP Request 
`***GET*** /animation_formats` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| q | query | an url-encoded request with tag(s) or partial tag(s) (separated by circumflex char (circumflex: '^')) | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Return animations list |

## ***POST*** 

**Summary:** Create an animation.

**Description:** Create an animation.

### HTTP Request 
`***POST*** /animation_formats` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| name | formData | Title of the animation format. | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | Create an animation. |

# /ANIMATION_FORMATS/{ID}
## ***GET*** 

**Summary:** Get an animation format.

**Description:** Get an animation format.

### HTTP Request 
`***GET*** /animation_formats/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| id | path |  | Yes | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get an animation format. |

## ***PUT*** 

**Summary:** Update an animation.

**Description:** Update an animation.

### HTTP Request 
`***PUT*** /animation_formats/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | AnimationFormat ID. | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Update an animation. |

## ***DELETE*** 

**Summary:** Delete an animation.

**Description:** Delete an animation.

### HTTP Request 
`***DELETE*** /animation_formats/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | AnimationFormat ID. | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | Delete an animation. |

# /ANIMATION_FORMATS/{ID}/MEETS
## ***GET*** 

**Summary:** Get meet organized with a given animation format.

**Description:** Get meet organized with a given animation format.

### HTTP Request 
`***GET*** /animation_formats/{id}/meets` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| id | path |  | Yes | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get meet organized with a given animation format. |

# /TAGS
## ***GET*** 

**Summary:** Return tags list

**Description:** Return tags list

### HTTP Request 
`***GET*** /tags` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| q | query | an url-encoded request with tag(s) or partial tag(s) (separated by circumflex char (circumflex: '^')) | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Return tags list |

## ***POST*** 

**Summary:** Create a tag

**Description:** Create a tag

### HTTP Request 
`***POST*** /tags` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| name | formData | the tag in question with the hashtag, ex. #social | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | Create a tag |

# /TAGS/SUGGESTIONS
## ***GET*** 

**Summary:** Suggest tags.

**Description:** Suggest tags.

### HTTP Request 
`***GET*** /tags/suggestions` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| q | query | A description to be searched for matches. | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Suggest tags. |

# /TAGS/{ID}
## ***PUT*** 

**Summary:** Update a tag.

**Description:** Update a tag.

### HTTP Request 
`***PUT*** /tags/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Tag ID. | Yes | string |
| name | formData | The name of the tag | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Update a tag. |

## ***DELETE*** 

**Summary:** Delete a tag.

**Description:** Delete a tag.

### HTTP Request 
`***DELETE*** /tags/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Tag ID. | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | Delete a tag. |

## ***GET*** 

**Summary:** Return a tag

**Description:** Return a tag

### HTTP Request 
`***GET*** /tags/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| id | path | Tag id. | Yes | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Return a tag |

# /LOCATIONS
## ***GET*** 

**Summary:** Return locations list

**Description:** Return locations list

### HTTP Request 
`***GET*** /locations` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Return locations list |

## ***POST*** 

**Summary:** Create a location

**Description:** Create a location

### HTTP Request 
`***POST*** /locations` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| name | formData | name of location | No | string |
| lat | formData | the latitude of the location | Yes | float |
| lng | formData | the longitude of the location | Yes | float |
| area | formData | if is an influence area, the range of the influenced area of the location (in km) | No | float |
| address | formData | the address of the location | No | string |
| city | formData | the city of the location | No | string |
| zip_code | formData | the zip code of the location | No | string |
| country | formData | the two letter code of the country of the location | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | Create a location |

# /LOCATIONS/{ID}
## ***PUT*** 

**Summary:** Update a location.

**Description:** Update a location.

### HTTP Request 
`***PUT*** /locations/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Location ID | Yes | string |
| name | formData | name of location | No | string |
| lat | formData | the latitude of the location | No | float |
| lng | formData | the longitude of the location | No | float |
| area | formData | the range of the influenced area of the location (in km) | No | string |
| address | formData | the address of this location | No | string |
| city | formData | the city of the location | No | string |
| zip_code | formData | the zip code of the location | No | string |
| country | formData | the two letter code of the country of the location | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Update a location. |

## ***DELETE*** 

**Summary:** Delete a location.

**Description:** Delete a location.

### HTTP Request 
`***DELETE*** /locations/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Location ID | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | Delete a location. |

## ***GET*** 

**Summary:** Return a location

**Description:** Return a location

### HTTP Request 
`***GET*** /locations/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Location ID. | Yes | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Return a location |

# /RESOURCES
## ***GET*** 

**Summary:** Return resources list

**Description:** Return resources list

### HTTP Request 
`***GET*** /resources` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| q | query | Search query in title... | No | string |
| c | query | Category to return (self_kawaa, user_avatar, default_user_avatar, default_group_avatar, default_group_photo, default_meet_photo, group_avatar, group_photo, meet_photo, comment_upload, animation_cover, animation_photo, animation_video, animation_doc) | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Return resources list |

## ***POST*** 

**Summary:** Create a resource

**Description:** Create a resource

### HTTP Request 
`***POST*** /resources` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| title | formData | Name of resource | No | string |
| file | formData | File, image of resource | No | file |
| slug | formData | Url of the resource | No | string |
| group_id | formData | Optional, if the resource is attached to a group | No | integer |
| meet_id | formData | Optional, if the resource is attached to a meet | No | integer |
| category | formData | Optional, category of the resource (self_kawaa, user_avatar, group_avatar, group_photo, meet_photo, comment_upload, animation_cover, animation_photo, animation_video, animation_doc) | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | Create a resource |

# /RESOURCES/{ID}
## ***PUT*** 

**Summary:** Update a resource.

**Description:** Update a resource.

### HTTP Request 
`***PUT*** /resources/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Resource ID. | Yes | integer |
| title | formData | name of resource | No | string |
| legend | formData | legend of the resource | No | string |
| category | formData | Optional, category of the resource (self_kawaa, user_avatar, group_avatar, group_photo, meet_photo, comment_upload, animation_cover, animation_photo, animation_video, animation_doc) | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Update a resource. |

## ***DELETE*** 

**Summary:** Delete a resource.

**Description:** Delete a resource.

### HTTP Request 
`***DELETE*** /resources/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | resource ID. | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | Delete a resource. |

## ***GET*** 

**Summary:** Return a resource

**Description:** Return a resource

### HTTP Request 
`***GET*** /resources/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| id | path | Resource id. | Yes | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Return a resource |

# /QUERY_FORMS/{ID}
## ***GET*** 

### HTTP Request 
`***GET*** /query_forms/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| id | path |  | Yes | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | get QueryForm(s) |

## ***PUT*** 

### HTTP Request 
`***PUT*** /query_forms/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| rating | formData | Rating form 1 to 5. | No | integer |
| comment | formData | Aditional comment. | No | string |
| id | path |  | Yes | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | updated QueryForm |

# /QUERY_FORMS
## ***POST*** 

### HTTP Request 
`***POST*** /query_forms` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| kind | formData | Select query_forms with the provided kind | Yes | string |
| category | formData | Category of the form. | Yes | string |
| datetime | formData | In format YYYY-MM-DD HH:MM. If not given, feedback emails will be sent 1 day after meet's datetime. | No | dateTime |
| rating | formData | Rating form 1 to 5. | No | integer |
| blueprint_id | formData | ID of the related Form_Query blueprint | No | integer |
| target_id | formData | ID of the related target | No | integer |
| target_type | formData | Type of the related target | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | created QueryForm |

# /WALLETS
## ***POST*** 

**Summary:** Create a wallet.

**Description:** Create a wallet.

### HTTP Request 
`***POST*** /wallets` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| target_id | formData | Id of group or meet. | Yes | integer |
| target_type | formData | Group or Meet | Yes | string |
| price | formData | Price to be paid. If not supplied a free determined price is set (open-price). | No | string |
| iban | formData | IBAN of the wallet. | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | Create a wallet. |

# /WALLETS/INIT_PAYMENT
## ***GET*** 

**Summary:** Get a token to process payment.

**Description:** Get a token to process payment.

### HTTP Request 
`***GET*** /wallets/init_payment` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| amount | query | Amount of money to be transfered. | Yes | string |
| meet | query | Id of the meet. | Yes | integer |
| return_url | query | Url encoded string represnting an url to which user gets redirected after paying. | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get a token to process payment. |

# /WALLETS/CREDIT
## ***PUT*** 

**Summary:** Credit a wallet (Send money).

**Description:** Credit a wallet (Send money).

### HTTP Request 
`***PUT*** /wallets/credit` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| token | formData | A token issued on /wallets/init_payment. | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Credit a wallet (Send money). |

# /WALLETS/{ID}
## ***GET*** 

**Summary:** Get a wallet.

**Description:** Get a wallet.

### HTTP Request 
`***GET*** /wallets/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Id of the affected wallet. | Yes | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get a wallet. |

# /WALLETS/{ID}/CARD
## ***POST*** 

**Summary:** Register a card for future rebills.

**Description:** Register a card for future rebills.

### HTTP Request 
`***POST*** /wallets/{id}/card` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Id of the affected wallet. | Yes | integer |
| card_number | formData | Card number. | Yes | string |
| card_type | formData | CB, Visa or MasterCard | Yes | string |
| card_cvv | formData | Card CVV. | Yes | string |
| card_date | formData | Card expiration date in MM/YYYY format. | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | Register a card for future rebills. |

## ***DELETE*** 

**Summary:** Unregister a card.

**Description:** Unregister a card.

### HTTP Request 
`***DELETE*** /wallets/{id}/card` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Id of the affected wallet. | Yes | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | Unregister a card. |

# /WALLETS/{ID}/DEBIT
## ***PUT*** 

**Summary:** Debit a wallet (Draw money).

**Description:** Debit a wallet (Draw money).

### HTTP Request 
`***PUT*** /wallets/{id}/debit` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Id of the affected wallet. | Yes | integer |
| amount | formData | Amount of money to be transfered. | Yes | float |
| wallet_credit | formData | Id of the wallet to credit(to send money to). | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Debit a wallet (Draw money). |

# /OPTIONS
## ***GET*** 

**Summary:** List options

**Description:** List options

### HTTP Request 
`***GET*** /options` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| platform | query | list all available Options | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | List options |

## ***POST*** 

**Summary:** Create an option

**Description:** Create an option

### HTTP Request 
`***POST*** /options` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| platform | formData | Platform for the Option (all, web, ios, etc.) | Yes | string |
| name | formData | Name of the Option | Yes | string |
| data | form | The data Options | Yes | object |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | Create an option |

# /OPTIONS/{PLATFORM}/{NAME}
## ***GET*** 

**Summary:** Return an option

**Description:** Return an option

### HTTP Request 
`***GET*** /options/{platform}/{name}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| platform | path | Platform for the Option (all, web, ios, etc.) | Yes | string |
| name | path | Name of the Option | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Return an option |

## ***PUT*** 

**Summary:** Update an Option

**Description:** Update an Option

### HTTP Request 
`***PUT*** /options/{platform}/{name}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| platform | path | Platform for the Option (all, web, ios, etc.) | Yes | string |
| name | path | Name of the Option | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Update an Option |

## ***DELETE*** 

**Summary:** Delete an Option

**Description:** Delete an Option

### HTTP Request 
`***DELETE*** /options/{platform}/{name}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| platform | path | Platform for the Option (all, web, ios, etc.) | Yes | string |
| name | path | Name of the Option | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | Delete an Option |

# /MEETS/COUNT
## ***GET*** 

**Summary:** Meet counts

**Description:** Meet counts

### HTTP Request 
`***GET*** /meets/count` 

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Meet counts |

# /MEETS
## ***GET*** 

**Summary:** List of meets.

**Description:** List of meets.

### HTTP Request 
`***GET*** /meets` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| time_scope | query | _past_ or _future_ ; keep empty for an unfiltered return. | No | string |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| lat | query |  | No | float |
| lng | query |  | No | float |
| range | query | range in kilometers | No | float |
| q | query | an url-encoded request with tags or words separated by circumflex char. ( circumflex: '^') | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | List of meets. |

## ***POST*** 

**Summary:** Create a new meet.

**Description:**         mutually exclusive: place, new_location and location
        mutually exclusive: end_datetime and duration


### HTTP Request 
`***POST*** /meets` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| name | formData |  | Yes | string |
| groups | form | List of groups ids to be associated with. First group of the list gets a meetship with rank 1. | No | array |
| place | formData | The ID of the place where the meet will take place. | No | integer |
| new_location[name] | formData | name of the location | No | string |
| new_location[lat] | formData | the latitude of the location | Yes | float |
| new_location[lng] | formData | the longitude of the location | Yes | float |
| new_location[area] | formData | the range of the influenced area of the location (in km) | No | string |
| new_location[address] | formData | the address of the location | No | string |
| new_location[city] | formData | the city of the location | No | string |
| new_location[zip_code] | formData | the zip code of the location | No | string |
| new_location[country] | formData | the two letter code of the country of the location | Yes | string |
| location | formData | If no place is specified, the ID of the location where the meet will take place. | No | integer |
| organizator | formData | Organizator, ID of the member who organize this meets | No | integer |
| description | formData |  | No | string |
| tags | form | Array of Tags' IDs for this meet | No | array |
| new_photo | formData | Image of the meet. | No | file |
| moderation | formData | The meet can be of 3 types, open, moderate, closed. | No | string |
| access | formData | The access to the meet can be general(accessible by everyone) or restricted(accessible only in groups to which it belongs). | No | string |
| datetime | formData | In format YYYY-MM-DD HH:MM | No | dateTime |
| end_datetime | formData | In format YYYY-MM-DD HH:MM. If specified, don't specified `duration`. | No | dateTime |
| duration | formData | The duration of the meet in seconds. If specified, don't specified `end_datetime`. | No | integer |
| animation_format | formData | Id of an animation format which will be linked to the meet. | No | integer |
| provider_data | form | Data supplied by the provider. | No | object |
| status | formData | The status of the meet (disabled, published, draft or suspended). | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | Create a new meet. |

# /MEETS/LOCATIONS
## ***GET*** 

**Summary:** List all locations of next meets

**Description:** List all locations of next meets

### HTTP Request 
`***GET*** /meets/locations` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| time_scope | query | _past_ or _future_ ; keep empty for an unfiltered return. | No | string |
| lat | query |  | No | float |
| lng | query |  | No | float |
| range | query | range in kilometers | No | float |
| q | query | an url-encoded request with tags or words separated by circumflex char. ( circumflex: '^') | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | List all locations of next meets |

# /MEETS/{ID}
## ***GET*** 

**Summary:** Get a sigle meet.

**Description:** Get a sigle meet.

### HTTP Request 
`***GET*** /meets/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| id | path | Id of the affected meet | Yes | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get a sigle meet. |

## ***PUT*** 

**Summary:** Update information about meeting

**Description:**           mutually_exclusive :place, :new_location, :location
          mutually_exclusive :end_datetime, :duration
          mutually_exclusive :add_group, :groups
          mutually_exclusive :add_tag, :tags


### HTTP Request 
`***PUT*** /meets/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Id of the affected meet | Yes | integer |
| name | formData |  | No | string |
| add_group | formData | The ID of the new parent group | No | integer |
| groups | form |  | No | array |
| place | formData | The ID of the place where the meet will take place. | No | integer |
| new_location[name] | formData | name of the location | No | string |
| new_location[lat] | formData | the latitude of the location | Yes | float |
| new_location[lng] | formData | the longitude of the location | Yes | float |
| new_location[area] | formData | the range of the influenced area of the location (in km) | No | string |
| new_location[address] | formData | the address of the location | No | string |
| new_location[city] | formData | the city of the location | No | string |
| new_location[zip_code] | formData | the zip code of the location | No | string |
| new_location[country] | formData | the two letter code of the country of the location | Yes | string |
| location | formData | If no place is specified, the ID of the location where the meet will take place. | No | integer |
| description | formData |  | No | string |
| add_tag | formData | Id of a new tag. | No | integer |
| tags | form |  | No | array |
| photos | form | Images'ids of the meet. | No | array |
| moderation | formData | The meet can be of 3 types, open, moderate, closed. | No | string |
| access | formData | The access to the meet can be general(accessible by everyone) or restricted(accessible only in groups to which it belongs). | No | string |
| datetime | formData | In format YYYY-MM-DD HH:MM | No | dateTime |
| end_datetime | formData | In format YYYY-MM-DD HH:MM. If specified, don't specified `duration`. | No | dateTime |
| duration | formData | The duration of the meet in seconds. If specified, don't specified `end_datetime`. | No | integer |
| provider_data | form | Data supplied by the provider. | No | object |
| animation_format | formData | Id of an animation format which will be linked to the meet. | No | integer |
| status | formData | The status of the meet (disabled, published, draft or suspended). | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Update information about meeting |

## ***DELETE*** 

**Summary:** Delete a meet.

**Description:** Delete a meet.

### HTTP Request 
`***DELETE*** /meets/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Id of the affected meet | Yes | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | Delete a meet. |

# /MEETS/{ID}/MEETSHIPS
## ***GET*** 

**Summary:** Get all meetships of a meet.

**Description:** Get all meetships of a meet.

### HTTP Request 
`***GET*** /meets/{id}/meetships` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Id of the affected meet | Yes | integer |
| status | query | Select according to status. | No | string |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get all meetships of a meet. |

# /MEETS/{ID}/INVITATIONS
## ***GET*** 

**Summary:** Get Invitations of a Meet

**Description:** Get Invitations of a Meet

### HTTP Request 
`***GET*** /meets/{id}/invitations` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Id of the affected meet | Yes | integer |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get Invitations of a Meet |

## ***POST*** 

**Summary:** Send several invitations for joining a group

**Description:**           */!\ Object (JSON) and Array can not be used with this interface, and will return a format error.*


### HTTP Request 
`***POST*** /meets/{id}/invitations` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Id of the affected meet | Yes | integer |
| list | form | Data of users to which invitations will be sent. | Yes | array |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | Send several invitations for joining a group |

# /MEETS/{ID}/INVITATION
## ***POST*** 

**Summary:** Send Ivitation for Joining a Meet

**Description:**           */!\ Object (JSON) and Array can not be used with this interface, and will return a format error.*


### HTTP Request 
`***POST*** /meets/{id}/invitation` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Id of the affected meet | Yes | integer |
| email | formData | Email to which the invitation will be sent. | Yes | string |
| groups | form | Ids of groups to which one is invited. | No | array |
| message | formData | Message to be sent as part of the email. | No | string |
| locale | formData | Abreviation of the language to be used in communication with the invitee. | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | Send Ivitation for Joining a Meet |

# /MEETS/{ID}/PARTICIPANT
## ***POST*** 

**Summary:** Append a Member (Join a meet)

**Description:**           */!\ Object (JSON) and Array can not be used with this interface, and will return a format error.*


### HTTP Request 
`***POST*** /meets/{id}/participant` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Id of the affected meet | Yes | integer |
| user | formData | User ID | No | integer |
| member | formData | Member ID | No | integer |
| new_member[email] | formData | Email of the new member. | Yes | string |
| new_member[first_name] | formData | First name of the new member. | Yes | string |
| new_member[last_name] | formData | Last name of the new member. | Yes | string |
| options | form | Options is a json hash of several data/fields | No | object |
| query_form_id | formData | ID of the related Query_Form | No | integer |
| disclose_email | formData | New member authorizes group's admin and staff to see his/her email. | No | boolean |
| role | formData | Role of the Member (participant, organizator) | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | Append a Member (Join a meet) |

## ***GET*** 

**Summary:** Get Participation

**Description:** Get Participation

### HTTP Request 
`***GET*** /meets/{id}/participant` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Id of the affected meet | Yes | integer |
| participant | query | Participant ID | No | integer |
| member | query | or Member ID | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get Participation |

## ***PUT*** 

**Summary:** Update Participation

**Description:**           */!\ Object (JSON) and Array can not be used with this interface, and will return a format error.*


### HTTP Request 
`***PUT*** /meets/{id}/participant` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Id of the affected meet | Yes | integer |
| participant | formData | Participant ID | No | integer |
| member | formData | or Member ID | No | integer |
| status | formData | Participant's status | No | string |
| options | form | Options is a json hash of several data/fields | No | object |
| role | formData | Role of the Member (participant, organizator) | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Update Participation |

## ***DELETE*** 

**Summary:** Cancel participation (Quit a meet)

**Description:** Cancel participation (Quit a meet)

### HTTP Request 
`***DELETE*** /meets/{id}/participant` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Id of the affected meet | Yes | integer |
| participant | query | Participant ID | No | integer |
| member | query | or Member ID | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | Cancel participation (Quit a meet) |

# /MEETS/{ID}/PARTICIPANTS/PROVIDER
## ***POST*** 

### HTTP Request 
`***POST*** /meets/{id}/participants/provider` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Id of the affected meet | Yes | integer |
| provider | formData | Name of the provider. | Yes | string |
| participants_data | form | Data supplied by the provider. | Yes | array |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 |  |

# /MEETS/{ID}/PARTICIPANTS
## ***GET*** 

**Summary:** Return meet participants

**Description:** Return meet participants

### HTTP Request 
`***GET*** /meets/{id}/participants` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Id of the affected meet | Yes | integer |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| by_name | query | Sort by users' last name. | No | string |
| by_email | query | Sort by users' email. | No | string |
| by_role | query | Sort by participants' role. | No | string |
| role | query | Filter by role of the participants (participant, organizator) | No | string |
| status | query | Filter by status of the participants (refused, active, invited, pending, suspended) | No | string |
| presence_status | query | Filter by presence_status (in options_data) | No | string |
| q | query | an url-encoded request for first_name, last_name and email look-up. | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Return meet participants |

# /MEETS/{ID}/PARTICIPANTS/STATS
## ***GET*** 

**Summary:** Return meet participants

**Description:** Return meet participants

### HTTP Request 
`***GET*** /meets/{id}/participants/stats` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Id of the affected meet | Yes | integer |
| kind | query | Kind of stat data to be returned. | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Return meet participants |

# /MEETS/{ID}/COMMENTS
## ***GET*** 

**Summary:** Return meet comments

**Description:** Return meet comments

### HTTP Request 
`***GET*** /meets/{id}/comments` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| id | path | Id of the affected meet | Yes | integer |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| room | query | The room of the comments (0 for all, 1, 2 or 3) | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Return meet comments |

## ***POST*** 

**Summary:** Post a comment for this meet

**Description:** Post a comment for this meet

### HTTP Request 
`***POST*** /meets/{id}/comments` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Id of the affected meet | Yes | integer |
| room | formData | The room of the comment (1 for member, 2 not used or 3 for organizator) | No | integer |
| uploads | form | Resources' ids. | No | array |
| new_upload | formData | New file to upload. | No | file |
| content | formData | The content of the comment | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | Post a comment for this meet |

# /MEETS/{ID}/QUERY_FORMS
## ***POST*** 

**Summary:** Create a query_form blueprint for a meet

**Description:** Create a query_form blueprint for a meet

### HTTP Request 
`***POST*** /meets/{id}/query_forms` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Id of the affected meet | Yes | integer |
| category | formData | Category of the form. | Yes | string |
| datetime | formData | In format YYYY-MM-DD HH:MM. If not given, feedback emails will be sent 1 day after meet's datetime. | No | dateTime |
| message | formData | Custom message to be desplayed when user starts a feedback. | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 201 | Create a query_form blueprint for a meet |

## ***PUT*** 

**Summary:** Update a query_form blueprint for a meet

**Description:** Update a query_form blueprint for a meet

### HTTP Request 
`***PUT*** /meets/{id}/query_forms` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Id of the affected meet | Yes | integer |
| blueprint_id | formData | Id of the affected query_form | Yes | integer |
| datetime | formData | In format YYYY-MM-DD HH:MM. If not given, feedback emails will be sent 1 day after meet's datetime. | No | dateTime |
| message | formData | Custom message to be desplayed when user starts a feedback. | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Update a query_form blueprint for a meet |

## ***GET*** 

**Summary:** Get query_forms of a meet.

**Description:** Get query_forms of a meet.

### HTTP Request 
`***GET*** /meets/{id}/query_forms` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| X-Auth-Key | header | Identity token | Yes | string |
| id | path | Id of the affected meet | Yes | integer |
| limit | query | for pagination | No | integer |
| offset | query | for pagination | No | integer |
| blueprint_id | query | Id of the blueprint if selected 'kind' is 'report' | No | integer |
| category | query | Select query_forms with the provided category | No | string |
| kind | query | Select query_forms with the provided kind | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Get query_forms of a meet. |

<!-- Converted with the swagger-to-slate https://github.com/lavkumarv/swagger-to-slate -->
