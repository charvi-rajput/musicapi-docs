# Errors & Status Codes

The Music API uses standard HTTP status codes to indicate success or failure.

## Success Responses

| Code | Description             | Comments                              |
|------|-------------------------| ------------------------------------- |
| 200  | OK                      |Successful Response for all operations | 


## Error Responses

| Code | Description             | Comments                             |
|------|-------------------------| -------------------------------------|
| 401  | Unauthorised            | Already Deleted for Delete operation |


### Example Error

```json
{
  "errormsg": "This playlist is already deleted."
}
```