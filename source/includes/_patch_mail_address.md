## Update an existing mail address

```ruby
# Update mail address with id 1 for location with id 1
Ohanakapa.patch('locations/1/mail_address/1', { street: 'Updated Street' })
```

```shell
curl -X PATCH "https://ohana-api-demo.herokuapp.com/api/locations/1/mail_address/1" -d '{"street_1":"Updated Street"}' -H "X-Api-Token: test" -H "Content-Type: application/json"
```

> When successful, the above command returns a `200` HTTP status code and JSON
> structured like this:

```json
{
  "id": 1,
  "attention": null,
  "street_1": "Updated Street",
  "street_2": null,
  "city": "Redwood City",
  "state": "CA",
  "postal_code": "94065"
}
```

This endpoint updates an existing mail address for the specified location.

### HTTP Request

`PATCH https://ohana-api-demo.herokuapp.com/api/locations/:location_id/mail_address/:mail_address_id`

### JSON Parameters

| Name | Type | Requirement | Detail |
|:-----|:-----|:---------|:-------|
| attention | string | optional | Any person the letter might be addressed to. |
| street_1 | string | required | The primary part of the Street Address or P.O. Box number. |
| street_2 | string | optional | The secondary part of the Street Address, such as the Suite, Room, or Floor number |
| city | string | required | The City name |
| state | string | required | 2-letter US state abbreviation |
| postal_code | string | required | A valid postal code. Note that the API currently assumes this will be a US 5 or 9-digit ZIP code. 9-digit ZIP codes are separated with a dash, like this: 94025-9881. If you are using non-US data, you will need to replace the [postal code validation](https://github.com/codeforamerica/ohana-api/blob/master/app/validators/zip_validator.rb) with your own. |
| country_code | string | required | 2-letter [ISO 3361-1](http://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code |

<aside class="warning">All PATCH requests require a valid token passed via the
`X-Api-Token` HTTP header</aside>
