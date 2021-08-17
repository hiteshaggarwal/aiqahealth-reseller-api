# Customer Registration

Used to register/subscribe a customer.

**URL** : `/subscribe`

**Method** : `POST`

**Auth required** : YES

**Data constraints**

```json
{
	"name": "[Name of customer]",
	"phone": "[Valid 10 digit mobile number]",
	"email": "[Valid email address]",
	"gender": "[Gender of customer (m = male, f = female, o = other)]",
	"dob": "[Date of birth of customer in YYYY-MM-DD format]",
	"pincode": "[Valid 6 digit pincode]",
	"product": "[Valid product product_type:productid eg. mutual_aid:2]",
	"members_detail": [
		{
			"relation": "[Relation with policy holder (self, spouse, daughter, son, parent, spouse_parent)]",
			"gender": "gender of the member in case of parent, spouse_parent or spouse",
			"dob": "dob of member, not required for self",
			"name": "name of member, not required for self",
			"height": "height of member in cms",
			"weight": "weight of member in kgs"
		}
	]
}
```

**Data example**

```json
{
	"name": "Ram Kumar",
	"phone": "9999999999",
	"email": "customer@email.com",
	"gender": "m",
	"dob": "01-01-1985",
	"pincode": "123456",
	"product": "mutaul_aid:2",
	"members_detail": [
		{
			"relation": "self",
			"height": 180,
			"weight": 72
		},
		{
			"relation": "spouse",
			"gender": "f",
			"dob": "1985-01-01",
			"name": "Ram's Spouse",
			"height": 180,
			"weight": 72
		},
		{
			"relation": "son",
			"dob": "2015-01-01",
			"name": "Ram's Son",
			"height": 90,
			"weight": 20
		}
	]
}
```

## Success Response

**Code** : `200`

**Status** : `success`

**Data** :

```json
{
	"subscription": "newly generated subscription id",
	"message": "Congratulations! Amit Kumar and 2 other members are successfully subscribed for {Product Name}. Please complete the payment to activate the policy."
}
```

## Error Response

**Condition** : If 'params' are wrong.

**Code** : `0`

**Status** : `error`

**Message** : `Different error decriptions based on invalid params`

**Errors** :

```json
{
	"params_name": [
      "Params invalidity error"
   ],
   ...
}
```
