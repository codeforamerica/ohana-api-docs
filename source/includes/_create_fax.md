## Create a new fax

```ruby
# Create a fax for location with id 1
Ohanakapa.post('locations/1/faxes', { number: '703-555-1212', department: 'Director of User Experience' })
```

```shell
curl --request POST "https://ohana-api-demo.herokuapp.com/api/locations/1/faxes?number=703-555-1212&department=Director of User Experience" \
  -H "X-Api-Token: your_secret_token"
```

> When successful, the above command returns a `201` HTTP status code and JSON
> structured like this:

```json
{
  "id": 2,
  "number": "703-555-1212",
  "department": "Director of User Experience"
}
```

This endpoint create a new fax for a location.

### HTTP Request

`POST https://ohana-api-demo.herokuapp.com/api/locations/:location_id/faxes`

### URL Parameters

Parameter | Description | Type | Required?
--------- | ----------- | ---- | ---------
number | The fax number | String | Yes
department | The department for the fax number | String | No

<aside class="warning">All POST requests require a valid token passed via the
`X-Api-Token` HTTP header</aside>
