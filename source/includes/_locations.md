# Locations

## Get all locations

```ruby
# Provide an API Endpoint
Ohanakapa.configure do |c|
  c.api_endpoint = 'https://ohana-api-demo.herokuapp.com/api'
end

# Fetch all locations
Ohanakapa.locations
```

```shell
curl "https://ohana-api-demo.herokuapp.com/api/locations" -H "User-Agent: MyClient/1.0.0"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 31,
    "admin_emails": [ ],
    "coordinates": [
      -122.4456187,
      37.7517064
    ],
    "description": "Testing adding a new location",
    "latitude": 37.7517064,
    "longitude": -122.4456187,
    "name": "New location test",
    "short_desc": null,
    "slug": "new-location-test",
    "updated_at": "2014-09-10T08:21:14.853-07:00",
    "website": null,
    "contacts_url": "https://ohana-api-demo.herokuapp.com/api/locations/new-location-test/contacts",
    "services_url": "https://ohana-api-demo.herokuapp.com/api/locations/new-location-test/services",
    "url": "https://ohana-api-demo.herokuapp.com/api/locations/new-location-test",
    "address": {
      "id": 28,
      "street_1": "1290 Ridder Park Drive",
      "street_2": null,
      "city": "San Francisco",
      "state": "CA",
      "postal_code": "94103"
    },
    "organization": {
      "id": 8,
      "accreditations": [],
      "alternate_name": null,
      "date_incorporated": null,
      "description": "Test description",
      "email": null,
      "funding_sources": [],
      "licenses": [],
      "name": "Admin Test Org",
      "slug": "admin-test-org",
      "website": null,
      "url": "https://ohana-api-demo.herokuapp.com/api/organizations/admin-test-org",
      "locations_url": "https://ohana-api-demo.herokuapp.com/api/organizations/admin-test-org/locations"
    },
    "phones": [ ]
  },
  {
    "id": 30,
    "admin_emails": [ ],
    "coordinates": [
      -122.4136494,
      37.7756408
    ],
    "description": "Location with no service",
    "latitude": 37.7756408,
    "longitude": -122.4136494,
    "name": "Location with no service",
    "short_desc": null,
    "slug": "location-with-no-service",
    "updated_at": "2014-09-10T08:21:14.848-07:00",
    "website": null,
    "contacts_url": "https://ohana-api-demo.herokuapp.com/api/locations/location-with-no-service/contacts",
    "faxes_url": "https://ohana-api-demo.herokuapp.com/api/locations/location-with-no-service/faxes",
    "services_url": "https://ohana-api-demo.herokuapp.com/api/locations/location-with-no-service/services",
    "url": "https://ohana-api-demo.herokuapp.com/api/locations/location-with-no-service",
    "address": {
      "id": 27,
      "street_1": "155 9th St",
      "street_2": null,
      "city": "San Francisco",
      "state": "CA",
      "postal_code": "94103"
    },
    "organization": {
      "id": 8,
      "accreditations": [],
      "alternate_name": null,
      "date_incorporated": null,
      "description": "Test description",
      "email": null,
      "funding_sources": [],
      "licenses": [],
      "name": "Admin Test Org",
      "slug": "admin-test-org",
      "website": null,
      "url": "https://ohana-api-demo.herokuapp.com/api/organizations/admin-test-org",
      "locations_url": "https://ohana-api-demo.herokuapp.com/api/organizations/admin-test-org/locations"
    },
    "phones": [ ]
  }
]
```

This endpoint retrieves all locations.

### HTTP Request

`GET https://ohana-api-demo.herokuapp.com/api/locations`

Note that the URL above is just an example for the demo instance.
To access an API that serves a particular region, you would need to look up
the appropriate endpoint. All known API deployments are listed in the
[deployments](#live-deployments-of-ohana-api) section at the top of this page.

### URL Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
page | 1 | The particular page of results.
per_page | 30 | Amount of locations to return per page, up to 100.
