## Update an existing address

```ruby
# Update address with id 1 for location with id 1
Ohanakapa.patch('locations/1/address/1', { street: 'Updated Street' })
```

```shell
curl -X PATCH "https://ohana-api-demo.herokuapp.com/api/locations/1/address/1" -d '{"address_1":"Updated Street"}' -H "X-Api-Token: test" -H "Content-Type: application/json"
```

> When successful, the above command returns a `200` HTTP status code and JSON
> structured like this:

```json
{
  "id": 1,
  "address_1": "Updated Street",
  "address_2": null,
  "city": "Redwood City",
  "state_province": "CA",
  "postal_code": "94065"
}
```

This endpoint updates an existing address for the specified location.

### HTTP Request

`PATCH https://ohana-api-demo.herokuapp.com/api/locations/:location_id/address/:address_id`

### JSON Parameters

| Name | Type | Requirement | Detail |
|:-----|:-----|:---------|:-------|
| address_1 | string | required | The primary part of the Street Address |
| address_2 | string | optional | The secondary part of the Street Address, such as the Suite, Room, or Floor number |
| city | string | required | The City name |
| state_province | string | required | 2-letter US state_province abbreviation |
| postal_code | string | required | A valid postal code. Note that the API currently assumes this will be a US 5 or 9-digit ZIP code. 9-digit ZIP codes are separated with a dash, like this: 94025-9881. If you are using non-US data, you will need to replace the [postal code validation](https://github.com/codeforamerica/ohana-api/blob/master/app/validators/zip_validator.rb) with your own. |
| country | string | required | 2-letter [ISO 3361-1](http://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code |

<aside class="warning">All PATCH requests require a valid token passed via the
`X-Api-Token` HTTP header</aside>
