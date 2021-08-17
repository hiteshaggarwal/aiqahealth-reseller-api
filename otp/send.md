# Send OTP

Used to send otp.

**URL** : `/otp/send` `/otp/resend`

**Method** : `POST`

**Auth required** : NO

**Data constraints**

```json
{
    "mobile": "[valid 10 digit mobile number]",
}
```

**Data example**

```json
{
    "mobile": "9999999999"
}
```

## Success Response

**Code** : `200`

**Status** : `success`

**Data** : 

```json
{
    "token": "32 character long token for security",
    "message": "OTP has been sent to 999999xxxx"
}
```

## Error Response

**Condition** : If 'mobile' number is wrong.

**Code** : `0`

**Status** : `error`

**Message** : `Please enter a valid mobile number`

**Errors** : 

```json
{
    "mobile": [
        "Please enter a valid mobile number"
    ]
}
```