## Update an existing service

```ruby
# Update service with id 1 for location with id 1
Ohanakapa.patch('locations/1/service/1', { name: 'Updated Service' })
```

```shell
curl --request PATCH "https://ohana-api-demo.herokuapp.com/api/locations/1/service/1?name=Updated Service" \
  -H "X-Api-Token: your_secret_token"
```

> When successful, the above command returns a `200` HTTP status code and JSON
> structured like this:

```json
{
  "id": 1,
  "audience": "Low-income residents.",
  "description": "Provides assistance and guidance to those wishing to apply for CalFresh",
  "eligibility": "Residents of California earning less than $25,000 per year",
  "fees": "None.",
  "funding_sources": [
    "Federal", "State"
  ],
  "how_to_apply": "Walk in, online, phone.",
  "keywords": [
    "SNAP",
    "Food Stamps"
  ],
  "name": "Updated Service",
  "service_areas": [
    "San Mateo County"
  ],
  "short_desc": null,
  "urls": [ ],
  "wait": "No wait.",
  "updated_at": "2014-04-16T19:51:28.610-07:00",
  "categories": [ ]
}
```

This endpoint updates an existing service.

### HTTP Request

`PATCH https://ohana-api-demo.herokuapp.com/api/locations/:location_id/service/:service_id`

### URL Parameters

Parameter | Description | Type | Required?
--------- | ----------- | ---- | ---------
street | The street | String | Yes
city | The city | String | Yes
state | The state | String | Yes
zip | The 5-digit ZIP code | String | Yes

<aside class="warning">All PATCH requests require a valid token passed via the
`X-Api-Token` HTTP header</aside>
