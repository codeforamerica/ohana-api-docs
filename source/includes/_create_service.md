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
  "id": 22,
  "accepted_payments": [
    "Cash",
    "Credit Card",
    "Check"
  ],
  "alternate_name": "Fotos para pasaportes",
  "audience": "Profit and nonprofit businesses, the public, military facilities, schools and government entities",
  "description": "[NOTE THIS IS NOT A REAL SERVICE--THIS IS FOR TESTING PURPOSES OF THIS ALPHA APP] Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent suscipit metus eu orci lobortis dictum. In hac habitasse platea dictumst. Vivamus vulputate, neque ut sodales gravida, lorem nunc pharetra ligula, ac cursus sem justo a sapien. Duis vitae vestibulum magna. Sed vel augue in justo rhoncus viverra. Nam ac felis a purus lobortis porttitor sit amet quis est. Suspendisse vulputate nisl quis nisi fermentum aliquet euismod at augue. Sed ultricies, purus dapibus tristique dictum, tortor mauris porttitor nulla, at porta nisl sem sed dolor. Proin ac hendrerit erat. Duis porta iaculis orci, eu euismod quam tristique in. Phasellus nec purus sit amet sapien volutpat egestas.",
  "eligibility": "None",
  "email": "passports@example.org",
  "fees": "None, except for permits and photocopying. Cash, checks and credit cards accepted",
  "funding_sources": [
    "City",
    "County",
    "Federal",
    "State"
  ],
  "how_to_apply": "Walk in or apply by phone or mail",
  "keywords": [
    "Salud",
    "Medicina"
  ],
  "languages": [
    "English",
    "Spanish"
  ],
  "name": "Passport Photos",
  "required_documents": [
    "Government-issued identification"
  ],
  "service_areas": [
    "San Mateo County",
    "Alameda County"
  ],
  "status": "active",
  "website": "http://www.example.com",
  "wait": "No wait to 2 weeks",
  "updated_at": "2014-04-18T12:49:47.791-07:00",
  "categories": [],
  "regular_schedules":[],
  "holiday_schedules":[]
}
```

This endpoint creates a new service for a location.

### HTTP Request

`POST https://ohana-api-demo.herokuapp.com/api/locations/:location_id/services`

### JSON Parameters

| Name | Type | Requirement | Detail |
|:-----|:-----|:---------|:-------|
| accepted_payments | Array of Strings | optional | Methods of payment for this service, such as `['Cash', 'Credit Card', 'Medicare']`. You can define the list of all possible payment methods in [settings.yml](https://github.com/codeforamerica/ohana-api/blob/master/config/settings.yml#L9-19). |
| alternate_name | string | optional | Another name this Service might be known by. |
| audience | string | optional | Group of people served |
| categories | array of objects | optional | Categories assigned to the service based on the Open Eligibility taxonomy. See the [Categories](#categories) section for more details. |
| description | string | required | Description of the service provided |
| eligibility | string | optional | Requirements to receive the service |
| email | string | optional | The service's main email address. |
| fees | string | optional | Fees charged to receive the service |
| funding_sources | array of strings | optional | Source of funds used to support the service |
| how_to_apply | string | required | Description of the service's application process |
| keywords | array of strings | optional | Keywords that people might use to search for this service, but that you might not want to include in the service description (such as common misspellings). |
| languages | array of strings | optional | Languages in which this service is provided. You can define the list of all possible languages in [settings.yml](https://github.com/codeforamerica/ohana-api/blob/master/config/settings.yml#L56-143). |
| name | string | required | Name of the service |
| required_documents | array of strings | optional | The documents that are required to receive this service. You can define the list of all possible documents in [settings.yml](https://github.com/codeforamerica/ohana-api/blob/master/config/settings.yml#L145-150). |
| service_areas | array of strings | optional | Cities, Counties, or other geographical area served. The values will typically be validated against a list of service areas defined in a deployment's [settings.yml](https://github.com/codeforamerica/ohana-api/blob/master/config/settings.yml#L152-172). |
| status | string | required | Must be one of `active`, `defunct`, or `inactive`. |
| wait | string | optional | Wait times associated with the service |
| website | string | optional | The service's website. Must include "http://" or "https://" |


<aside class="warning">All POST requests require a valid token passed via the
`X-Api-Token` HTTP header</aside>
