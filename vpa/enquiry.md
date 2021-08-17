# Vpa Registration Enquiry

Used to enquire vpa status.

**URL** : `/vpa/enquiry`

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
	"userId": "[valid user id]",
	"vpa": "[valid upi id]"
}
```

**Data example**

```json
{
	"userId": 100,
	"vpa": "ram.kumar@upi"
}
```

```json
{
	"applicationId": 1001,
	"vpa": "ram.kumar@upi"
}
```

## Success Response

**Code** : `200`

**Status** : `success`

**Data** :

```json
{
	"status": "boolean (true = if transaction is done, false = if transaction is not done)",
	"message": "Mandate status message",
	"activation": "Congratulations! Policy {applicationId} is activated. props only comes if a policy just activated."
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
