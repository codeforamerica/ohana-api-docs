## Update an existing service

```ruby
# Update service with id 1 for location with id 1
Ohanakapa.patch('locations/1/services/1', { name: 'Updated Service' })
```

```shell
curl -X PATCH "https://ohana-api-demo.herokuapp.com/api/locations/1/services/1" -d '{"name":"Updated Service"}' -H "X-Api-Token: test" -H "Content-Type: application/json"
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

This endpoint updates an existing service for the specified location.

### HTTP Request

`PATCH https://ohana-api-demo.herokuapp.com/api/locations/:location_id/services/:service_id`

### JSON Parameters

| Name | Type | Requirement | Detail |
|:-----|:-----|:---------|:-------|
| audience | string | optional | Group of people served |
| categories | array of objects | optional | Categories assigned to the service based on the Open Eligibility taxonomy. See the [Categories](#categories) section for more details. |
| description | string | optional | Description of the service provided |
| eligibility | string | optional | Requirements to receive the service |
| fees | string | optional | Fees charged to receive the service |
| funding_sources | array of strings | optional | Source of funds used to support the service |
| keywords | array of strings | optional | Keywords that define this service for search purposes |
| how_to_apply | string | optional | Description of how to apply to receive the service |
| name | string | optional | Name of the service |
| service_areas | array of strings | optional | Cities and Counties served. The values will typically be validated against a list of service areas defined in a deployment's [settings.yml](https://github.com/codeforamerica/ohana-api/blob/master/config/settings.yml#L132-152). |
| short_desc | string | optional | Succinct description of the service provided. 200 characters maximum. |
| urls | array of strings | optional | The service's website URLs. Must include "http://" or "https://"
| wait | string | optional | Wait times associated with the service |

<aside class="warning">All PATCH requests require a valid token passed via the
`X-Api-Token` HTTP header</aside>
