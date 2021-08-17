# Check Pincode

Used to check pincode.

**URL** : `/check-pin/:pincode`

**Method** : `GET`

**Auth required** : NO

## Success Response

**Code** : `200`

**Status** : `success`

**Data** : `Name of the state`

## Error Response

**Condition** : If 'pincode' is wrong.

**Code** : `0`

**Status** : `error`

**Message** : `The pincode field is required|The pincode must be 6 digits|The selected pincode is invalid.`

**Errors** : 

```json
{
    "pin": [
        "The pincode field is required|The pincode must be 6 digits|The selected pincode is invalid."
    ]
}
```