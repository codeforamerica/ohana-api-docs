## Create a new service

```ruby
# Create a service for location with id 1
Ohanakapa.post('locations/1/services', { name: 'Free Eye Exam', audience: 'Low-income children between the ages of 5 and 12.', description: 'Provides free eye exams for low-income children between the ages of 5 and 12.' })
```

```shell
curl --request POST "https://ohana-api-demo.herokuapp.com/api/locations/1/servicees?audience=Low-income children&description=Provides free eye exams for low-income children between the ages of 5 and 12&name=Free Eye Exam" \
  -H "X-Api-Token: your_secret_token"
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

`POST https://ohana-api-demo.herokuapp.com/api/locations/:location_id/servicees`

### URL Parameters

Parameter | Description | Type | Required?
--------- | ----------- | ---- | ---------
audience | The service number | String | No
description | The department for the service number | String | Yes
eligibility | The department for the service number | String | No
fees | The department for the service number | String | No
funding_sources | The department for the service number | String | No
how_to_apply | The department for the service number | String | No
keywords | A list of keywords that pertain to this service. | Array of Strings | No
name | The name of the service | String | Yes
service_areas | The department for the service number | String | No
short_desc | The department for the service number | String | No
urls | The department for the service number | String | No
wait | The department for the service number | String | No

<aside class="warning">All POST requests require a valid token passed via the
`X-Api-Token` HTTP header</aside>
