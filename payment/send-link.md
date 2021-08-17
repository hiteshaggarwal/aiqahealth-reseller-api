# Send Payment Link

Used to send payment link to user.

**URL** : `/payment/send-link`

**Method** : `POST`

**Auth required** : YES

**Data constraints**

```json
{
	"id": "subscription id"
}
```

**Data example**

```json
{
	"id": 123
}
```

## Success Response

**Code** : `200`

**Status** : `success`

**Data** :

```json
{
	"message": "Payment link has been sent to 999999xxxx"
}
```
