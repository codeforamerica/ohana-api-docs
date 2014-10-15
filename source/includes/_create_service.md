## Create a new service

```ruby
# Create a service for location with id 1
Ohanakapa.post('locations/1/services', { name: 'Free Eye Exam', audience: 'Low-income children between the ages of 5 and 12.', description: 'Provides free eye exams for low-income children between the ages of 5 and 12.' })
```

```shell
curl -X POST "https://ohana-api-demo.herokuapp.com/api/locations/1/services" -d '{"audience":"Low-income children","description":"Provides free eye exams for low-income children between the ages of 5 and 12","name":"Free Eye Exam"}' -H "X-Api-Token: your_token" -H "Content-Type: application/json"
```

> When successful, the above command returns a `201` HTTP status code and JSON
> structured like this:

```json
{
  "id": 2,
  "audience": "Low-income children",
  "description": "Provides free eye exams for low-income children between the ages of 5 and 12.",
  "eligibility": null,
  "fees": "None.",
  "funding_sources": [ ],
  "how_to_apply": null,
  "keywords": [ ],
  "name": "Free Eye Exam",
  "service_areas": [ ],
  "short_desc": null,
  "urls": [ ],
  "wait": null,
  "updated_at": "2014-04-16T19:51:28.610-07:00",
  "categories": [ ]
}
```

This endpoint create a new service for a location.

### HTTP Request

`POST https://ohana-api-demo.herokuapp.com/api/locations/:location_id/services`

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

<aside class="warning">All POST requests require a valid token passed via the
`X-Api-Token` HTTP header</aside>
