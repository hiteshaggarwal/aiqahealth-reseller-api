# Check Payment status

Used to check payment status.

**URL** : `/payment/check/:subscription_id`

**Method** : `GET`

**Auth required** : YES

## Success Response

**Code** : `200`

**Status** : `success`

**Data** :

```json
{
	"status": "boolean (true = if transaction is done, false = if transaction is not done)",
	"message": "Congratulations! Policy {application id} is activated. (if success)"
}
```
