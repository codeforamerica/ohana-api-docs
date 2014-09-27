# Address

## Create a new address

```ruby
# Create an address for location with id 1
Ohanakapa.post('locations/1/address/', { street: 'New Street', city: 'Albequerque', state: 'NM', zip: '12345' })
```

```shell
curl --request PATCH "https://ohana-api-demo.herokuapp.com/api/locations/1/address/1?street=New street&city=Albequerque&state=NM&zip=12345" \
  -H "X-Api-Token: your_secret_token"
```

> When successful, the above command returns a `200` HTTP status code and JSON
> structured like this:

```json
{
  "id": 2,
  "street": "New Street",
  "city": "Albequerque",
  "state": "NM",
  "zip": "12345"
}
```

This endpoint create a new address for a location.

### HTTP Request

`POST https://ohana-api-demo.herokuapp.com/api/locations/:location_id/address`

### URL Parameters

Parameter | Description | Type | Required?
--------- | ----------- | ---- | ---------
street | The street | String | Yes
city | The city | String | Yes
state | The state | String | Yes
zip | The 5-digit ZIP code | String | Yes

<aside class="warning">All POST requests require a valid token passed via the
`X-Api-Token` HTTP header</aside>
