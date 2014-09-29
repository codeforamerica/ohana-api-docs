## Update an existing fax

```ruby
# Update fax with id 1 for location with id 1
Ohanakapa.patch('locations/1/faxes/1', { number: '703-444-1234' })
```

```shell
curl --request PATCH "https://ohana-api-demo.herokuapp.com/api/locations/1/faxes/1?number=703-444-1234" \
  -H "X-Api-Token: your_secret_token"
```

> When successful, the above command returns a `200` HTTP status code and JSON
> structured like this:

```json
{
  "id": 1,
  "number": "703-444-1234",
  "department": "Redwood City"
}
```

This endpoint updates an existing fax.

### HTTP Request

`PATCH https://ohana-api-demo.herokuapp.com/api/locations/:location_id/faxes/:fax_id`

### URL Parameters

Parameter | Description | Type | Required?
--------- | ----------- | ---- | ---------
number | The fax number | String | Yes
department | The department for the fax number | String | No

<aside class="warning">All PATCH requests require a valid token passed via the
`X-Api-Token` HTTP header</aside>
