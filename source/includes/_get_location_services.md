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
    "id": 15,
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
    "name": "Help applying for CalFresh",
    "service_areas": [
      "San Mateo County"
    ],
    "short_desc": null,
    "urls": [ ],
    "wait": "No wait.",
    "updated_at": "2014-04-16T19:51:28.610-07:00",
    "categories": [ ]
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
