# Services

## Get all services belonging to a location

```ruby
# Provide an API Endpoint
Ohanakapa.configure do |c|
  c.api_endpoint = 'https://ohana-api-demo.herokuapp.com/api'
end

# Fetch all services belonging to the location with id 1
Ohanakapa.get('locations/1/services')
```

```shell
curl "https://ohana-api-demo.herokuapp.com/api/locations/1/services" -H "User-Agent: MyClient/1.0.0"
```

> The above command returns JSON structured like this:

```json
[
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
    "application_process": "Walk in or apply by phone or mail",
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
    "wait_time": "No wait to 2 weeks",
    "updated_at": "2014-04-18T12:49:47.791-07:00",
    "categories": [],
    "contacts": [],
    "phones": [],
    "regular_schedules":[],
    "holiday_schedules":[]
  },
  {
    "id": 23,
    "audience": "Second service and nonprofit businesses, the public, military facilities, schools and government entities",
    "description": "[NOTE THIS IS NOT A REAL ORGANIZATION--THIS IS FOR TESTTING PURPOSES OF THIS ALPHA APP] Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent suscipit metus eu orci lobortis dictum. In hac habitasse platea dictumst. Vivamus vulputate, neque ut sodales gravida, lorem nunc pharetra ligula, ac cursus sem justo a sapien. Duis vitae vestibulum magna. Sed vel augue in justo rhoncus viverra. Nam ac felis a purus lobortis porttitor sit amet quis est. Suspendisse vulputate nisl quis nisi fermentum aliquet euismod at augue. Sed ultricies, purus dapibus tristique dictum, tortor mauris porttitor nulla, at porta nisl sem sed dolor. Proin ac hendrerit erat. Duis porta iaculis orci, eu euismod quam tristique in. Phasellus nec purus sit amet sapien volutpat egestas.",
    "eligibility": "None",
    "fees": "None, except for permits and photocopying. Cash, checks and credit cards accepted",
    "funding_sources": [
      "City",
      "County",
      "Federal",
      "State"
    ],
    "application_process": "Walk in or apply by phone or mail",
    "keywords": [
      "Ruby on Rails/Postgres/Redis",
      "testing"
    ],
    "name": "Example Service Name",
    "service_areas": [
      "San Mateo County",
      "Alameda County"
    ],
    "status": "active",
    "website": "http://www.example.com",
    "wait_time": "No wait to 2 weeks",
    "categories": [],
    "contacts": [],
    "phones": [],
    "regular_schedules":[],
    "holiday_schedules":[]
  }
]
```

This endpoint retrieves all services that belong to a particular location.

### HTTP Request

`GET https://ohana-api-demo.herokuapp.com/api/locations/:id/services`

Note that the URL above is just an example for the demo instance.
To access an API that serves a particular region, you would need to look up
the appropriate endpoint. All known API deployments are listed in the
[deployments](#live-deployments-of-ohana-api) section at the top of this page.

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
page | 1 | The particular page of results.
per_page | 30 | Amount of services to return per page, up to 100.
