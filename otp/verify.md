# Verify OTP

Used to verify otp.

**URL** : `/otp/verify`

**Method** : `POST`

**Auth required** : NO

**Data constraints**

```json
{
	"mobile": "[valid 10 digit mobile number]",
	"token": "[valid token fetch from otp/send otp/resend api]",
	"otp": "[valid 4 digit otp]"
}
```

**Data example**

```json
{
	"mobile": "9999999999",
	"token": "94a08da1fecbb6e8b46990538c7b50b2",
	"otp": "1234"
}
```

## Success Response

**Code** : `200`

**Status** : `success`

**Data** :

```json
{
	"token": "ACCESS TOKEN",
	"user": "Reseller Details"
}
```

## Error Response

**Condition** : If 'mobile', 'token' or 'otp' is wrong.

**Code** : `0`

**Status** : `error`

**Message** : `Please enter a valid mobile number|Invalid Token|Enter 4 digit one time password`

**Errors** :

```json
{
	"mobile": ["Please enter a valid mobile number"],
	"token": ["Invalid Token"],
	"otp": ["Enter 4 digit one time password"]
}
```

---

**Condition** : If 'otp' expired.

**Code** : `403`

**Status** : `error`

**Message** : `Your OTP has been expired. Please try again.`

**Errors** : `{}`

---

**Condition** : If 'otp' attampts exceeds.

**Code** : `403`

**Status** : `error`

**Message** : `You've reached the maximum otp attempts.`

**Errors** : `{}`

---

**Condition** : If 'otp' is invalid.

**Code** : `205`

**Status** : `error`

**Message** : `Invalid OTP, You have {NUMBERS} more attempt(s) left.`

**Errors** : `{}`
