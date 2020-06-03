# Is JSON Equal
This is a simple utility that checks if one JSON string is business equivalent
to another JSON string.  Other more elaborate JSON checkers exist on
github, but I wanted something very simple.

To use this for JSON message testing just add the isJsonEqual.go file to whatever
package in you project works for you.

Three levels of testing exist
* MemberEqual: checks if the members that exist in both JSONs are equal - for PUSH
* DeepEqual: checks if the members that exist in both JSONs are identical - for GET
* KeysEqual: Checks if the keys are identical but not values - for CRUD testing - for PATCH

Here might be the JSON PUSHed to the service:
```json
{
  "first_name":"Tim",
  "last_name":"Dadd",
  "address":"The World",
  "emails": [
    {"type": "Personal", "email": "tim.dadd@home.com", "preferred":true},
    {"type": "Business", "email": "tim.dadd@work.com", "preferred":false}
  ],
  "phones": [
    { "type": "mobile", "country": 44, "number": "07892 123 456", "Messages": true },
    { "type": "mobile", "country": 63, "number": "0892 123 456", "Messages": true },
    { "type": "mobile", "country": 52, "number": "0987 123 456", "Messages": false }
  ]
}
```

This might be the response from the PUSH with UUID, creation date etc.
```json
{
  "uuid": "ac8e13c0-ab25-4e7b-8686-4486b4b9f763",
  "created_at": "2020-06-01T00:00:00Z",
  "updated_at": "0001-01-01T00:00:00Z",
  "deleted_at": null,
  "first_name": "Tim",
  "middle_name": null,
  "last_name": "Dadd",
  "address": "The World",
  "emails": [
    {"type": "Personal", "email": "tim.dadd@home.com", "preferred":true},
    {"type": "Business", "email": "tim.dadd@work.com", "preferred":false}
  ],
  "phones": [
    { "type": "mobile", "country": 44, "number": "07892 123 456", "Messages": true },
    { "type": "mobile", "country": 63, "number": "0892 123 456", "Messages": true },
    { "type": "mobile", "country": 52, "number": "0987 123 456", "Messages": false }
  ]
}
```