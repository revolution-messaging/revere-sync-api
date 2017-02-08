### Constituent Resources
***
	POST constituent/:access_token

***

#### Create a constituent

**Parameters**

| Name           | Type   | Required | Description             |
| -------------- | ------ | -------- | ------------------------------- |
| access_token   | String | True     | Access Token Hash  |


**Request**

At least **one paramater** is required to post data. Below are the allowed fields for a constituent.

| Name                | Type     | Required | Description |
| --------------------| -------- | -------- | ---------------------------------------------------------------------------------------- |
| `name`              | String   | False    | Full name, will be created from `firstname` and `lastname` automatically if possible.    |
| `firstname`         | String   | False    | First Name of Constituent |
| `lastname`          | String   | False    | Last Name of Constituent |
| `address`           | String   | False    | Primary Street Address |
| `address_two`       | String   | False    | Secondary Street Address|
| `city`              | String   | False    | City of Constituent |
| `state`             | String   | False    | Two Char String ( IE: WA ) |
| `zipcode`           | String   | False    | Five Digit Zip Code and four seperated by `-`. `98036` or `98036-1513` are OK. |
| `email`             | String   | False    | Email of Constituent  |
| `work_email`        | String   | False    | Work Email of Constituent  |
| `phone`             | String   | False    | Phone of Constituent, will populate msisdn when phone provided. |
| `msisdn`            | String   | False    | Mobile Phone number of Constituent, gets populated by `phone` if only phone is provided. |
| `work_phone`        | String   | False    | Work Phone number of Constituent |
| `home_phone`        | String   | False    | Home Phone number of Constituent |
| `employer`          | String   | False    | Employer of Constituent |
| `work_address` 	  | String   | False    | Work address of Constituent. |
| `work_address_two`  | String   | False    | Work address, second line of Constituent |
| `work_city`         | String   | False    | Work city of Constituent. | 
| `work_state`        | String   | False    | Work State, TWO Char String (IE: WA). |
| `work_zipcode` 	  | String   | False    | Work Zip Code, a five digit zip code and four seperated by `-`. `98036` or `98036-1513` are OK. |
| `mail_address`      | String   | False    | Mail address of Constituent. |
| `mail_address_two`  | String   | False    | Mail address, second line of Constituent |
| `mail_city`         | String   | False    | Mail city of Constituent. | 
| `mail_state`        | String   | False    | Mail State, TWO Char String (IE: WA). |
| `mail_zipcode`      | String   | False    | Mail Zip Code, a five digit zip code and four seperated by `-`. `98036` or `98036-1513` are OK. |
| `vote_address`      | String   | False    | Voter address of Constituent. |
| `vote_address_two`  | String   | False    | Voter address, second line of Constituent |
| `vote_city`         | String   | False    | Voter city of Constituent. | 
| `vote_state`        | String   | False    | Voter State, TWO Char String (IE: WA). |
| `vote_zipcode`      | String   | False    | Voter Zip Code, a five digit zip code and four seperated by `-`. `98036` or `98036-1513` are OK. |
| `metadata`          | Object   | False    | Metadata object (see table), IE: `source`:`string` for an ActionKit integration |
| `tags`              | String   | False    | Can be one String or an Array of Strings    |



| MetaData Field Object | Type     | Required | Description |
| ----------------------| -------- | ---------| ------------------------------------------------------------------------- |
| `source`              | string   | False    | A string, such as `facebook`, `twitter`, `EveryActionForm` etc.           |
| `preferredPhone`      | string   | False    | Must be `msisdn`, `work_phone`, or `home_phone` and field must be present.|
| `preferredEmail`      | string   | False    | Must be `email` or `work_email` and field must be present.                |
| `phoneOptInStatus`    | string   | False    | Must be `I` for in or `O` for out. Default is `O`.                        |
| `emailOptInStatus`    | string   | False    | Must be `I` for in or `O` for out. Default is `O`                         |


Example Request
 
**JSON Request Body**

``` json
{
	"name":"Steve Bob",
	"firstname":"Steve",
	"lastname":"Bob",
	"address":"555 Fake St.",
	"address_two":"APT 24",
	"city":"Seattle",
	"state":"WA",
	"zipcode":"98045",
	"email":"steve@steve.com",
	"home_phone":"1-555-555-5555",
	"msisdn":"1-555-555-5555",
	"employer":"Steve's Company",
	"metadata": {
		"source":"facebook",
		"emailOptInStatus":"I"
	},
	"tags":"amazingpeople2016"
}
```


**Response**

``` json
{
  "error":false,
  "message":"Contact accepted.",
  "id":"57d723cbd9dc8cdc5ad00191"
}
```

Example Request with multiple tags
 
**JSON Request Body**

```
{
	"name": "Steve Bob",
	"firstname": "Steve",
	"lastname": "Bob",
	"address": "555 Fake St.",
	"address_two": "APT 24",
	"city": "Seattle",
	"state": "WA",
	"zipcode": "98045",
	"email": "steve@steve.com",
	"home_phone": "1-555-555-5555",
	"msisdn": "1-555-555-5555",
	"employer": "Steve's Company",
	"metadata": {
		"source": "facebook",
		"emailOptInStatus": "I"
	},
	"tags": ["amazingpeople2016", "halflife3?"]
}
```


**Response**

``` json
{
  "error":false,
  "message":"Contact accepted.",
  "id":"57d723cbd9dc8cdc5ad00191"
}
```