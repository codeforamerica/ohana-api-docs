## Update an existing address

```ruby
# Update address with id 1 for location with id 1
Ohanakapa.patch('locations/1/address/1', { street: 'Updated Street' })
```

```shell
curl --request PATCH "https://ohana-api-demo.herokuapp.com/api/locations/1/address/1?street=Updated street" \
  -H "X-Api-Token: your_secret_token"
```

> When successful, the above command returns a `200` HTTP status code and JSON
> structured like this:

```json
{
  "id": 1,
  "street": "Updated Street",
  "city": "Redwood City",
  "state": "CA",
  "zip": "94065"
}
```

This endpoint updates an existing address.

### HTTP Request

`PATCH https://ohana-api-demo.herokuapp.com/api/locations/:location_id/address/:address_id`

### URL Parameters

Parameter | Description | Type | Required?
--------- | ----------- | ---- | ---------
street | The street | String | Yes
city | The city | String | Yes
state | The state | String | Yes
zip | The 5-digit ZIP code | String | Yes

<aside class="warning">All PATCH requests require a valid token passed via the
`X-Api-Token` HTTP header</aside>
