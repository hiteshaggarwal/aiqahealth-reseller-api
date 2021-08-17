# Vpa Registration

Used to register vpa.

**URL** : `/vpa/register`

**Method** : `POST`

**Auth required** : YES

**Data constraints**

```json
{
	"applicationId": "[valid application id]",
	"vpa": "[valid upi id]"
}
```

or

```json
{
	"mobile": "[valid 10 digit mobile number]",
	"email": "[valid email id]",
	"name": "[name of customer]",
	"dob": "[dob of customer YYYY-MM-DD]",
	"gender": "[gender of customer (m = male, f = female, o = other)]",
	"vpa": "[valid upi id]"
}
```

**Data example**

```json
{
	"mobile": "9999999999",
	"email": "customer@email.com",
	"name": "Ram Kumar",
	"dob": "1985-01-01",
	"gender": "m",
	"vpa": "ram.kumar@upi"
}
```

## Success Response

**Code** : `200`

**Status** : `success`

**Data** :

```json
{
	"message": "Success massage from mutual aid",
	"enquiry": {
		"userId": "userId from mutual aid (if not requested with applicationId)",
		"applicationId": "applicationId from mutual aid (if requested with applicationId)",
		"vpa": "vpa/upi id"
	},
	"expiry": "request expiry date in YYYY-MM-DD HH:MM:SS"
}
```

## Error Response

**Condition** : If 'params' are wrong.

**Code** : `0`

**Status** : `error`

**Message** : `Params invalidity messages.`

**Errors** :

```json
{
	"params_name": ["Params invalidity messages."],
   ...
}
```

---

**Condition** : Any other error from mutual aid.

**Code** : `0`

**Status** : `error`

**Message** : `Exception message from mutual aid.`

**Errors** : `{}`

---

**Condition** : If 'upi' is invalid

**Code** : `0`

**Status** : `error`

**Message** : `Exception message from mutual aid.`

**Errors** :

```json
{
	"upi": ["Exception message from mutual aid."]
}
```
