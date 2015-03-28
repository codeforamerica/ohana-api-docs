# Mail Address

## Create a new mail address

```ruby
# Create a mail address for location with id 1
Ohanakapa.post('locations/1/mail_address/', { address_1: 'New Street', city: 'Albequerque', state_province: 'NM', postal_code: '12345', country: 'US' })
```

```shell
curl -X POST "https://ohana-api-demo.herokuapp.com/api/locations/1/mail_address" -d '{"address_1":"New street","city":"Albequerque","state_province":"NM","postal_code":"12345", "country":"US"}' -H "X-Api-Token: your_token" -H "Content-Type: application/json"
```

> When successful, the above command returns a `201` HTTP status code and JSON
> structured like this:

```json
{
  "id": 2,
  "attention": null,
  "address_1": "New Street",
  "address_2": null,
  "city": "Albequerque",
  "state_province": "NM",
  "postal_code": "12345"
}
```

This endpoint creates a new mail address for the specified location.

### HTTP Request

`POST https://ohana-api-demo.herokuapp.com/api/locations/:location_id/mail_address`

### JSON Parameters

| Name | Type | Requirement | Detail |
|:-----|:-----|:---------|:-------|
| attention | string | optional | Any person the letter might be addressed to. |
| address_1 | string | required | The primary part of the Street Address or P.O. Box number. |
| address_2 | string | optional | The secondary part of the Street Address, such as the Suite, Room, or Floor number |
| city | string | required | The City name |
| state_province | string | required | 2-letter US state_province abbreviation |
| postal_code | string | required | A valid postal code. Note that the API currently assumes this will be a US 5 or 9-digit ZIP code. 9-digit ZIP codes are separated with a dash, like this: 94025-9881. If you are using non-US data, you will need to replace the [postal code validation](https://github.com/codeforamerica/ohana-api/blob/master/app/validators/zip_validator.rb) with your own. |
| country | string | required | 2-letter [ISO 3361-1](http://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code |

<aside class="warning">All POST requests require a valid token passed via the
`X-Api-Token` HTTP header</aside>
