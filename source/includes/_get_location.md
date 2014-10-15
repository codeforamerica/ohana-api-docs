## Get a specific location

```ruby
# Find a location by id
Ohanakapa.location(1)

# Find a location by slug
Ohanakapa.location('redwood-shores-branch')
```

```shell
# Find a location by slug
curl "https://ohana-api-demo.herokuapp.com/api/locations/redwood-shores-branch"

# Find a location by id
curl "https://ohana-api-demo.herokuapp.com/api/locations/1"
```

> When successful, the above command returns a `200` HTTP status code and JSON
> structured like this:

```json
{
  "id": 14,
  "accessibility": [ ],
  "admin_emails": [ ],
  "alternate_name": null,
  "coordinates": [
    -122.2586432,
    37.5304228
  ],
  "description": "Provides general reading materials, including large-type books, videos, music cassettes and CDs, and books on tape. Offers children's programs and a Summer Reading Club. Meeting room is available to nonprofit groups. Participates in the Peninsula Library System.",
  "emails": [ ],
  "hours": null,
  "languages": [ ],
  "latitude": 37.5304228,
  "longitude": -122.2586432,
  "name": "Redwood Shores Branch",
  "short_desc": "Provides general reading materials and reference services.",
  "slug": "redwood-shores-branch",
  "transportation": null,
  "updated_at": "2014-09-09T07:54:08.641-07:00",
  "urls": [
    "http://www.redwoodcity.org/library"
  ],
  "url": "https://ohana-api-demo.herokuapp.com/api/locations/redwood-shores-branch",
  "address": {
    "id": 14,
    "street_1": "399 Marine Parkway",
    "street_2": null,
    "city": "Redwood City",
    "state": "CA",
    "postal_code": "94065"
  },
  "contacts": [
    {
      "department": null,
      "email": null,
      "id": 22,
      "name": "Dave Genesy",
      "title": "Library Director",
      "phones": []
    }
  ],
  "mail_address": {
    "id": 14,
    "attention": "Redwood Shores Branch",
    "street_1": "399 Marine Parkway",
    "street_2": null,
    "city": "Redwood City",
    "state": "CA",
    "postal_code": "94065"
  },
  "phones": [
    {
      "id": 15,
      "department": null,
      "extension": null,
      "number": "650 780-5740",
      "number_type": "voice",
      "vanity_number": null
    }
  ],
  "services": [
    {
      "id": 15,
      "audience": null,
      "description": null,
      "eligibility": "Resident of California to obtain a library card",
      "fees": "None.",
      "funding_sources": [
        "City"
      ],
      "how_to_apply": "Walk in. Proof of California residency required to receive a library card.",
      "keywords": [
        "EDUCATION SERVICES",
        "Library",
        "Libraries",
        "Public Libraries"
      ],
      "name": null,
      "service_areas": [
        "San Mateo County"
      ],
      "short_desc": null,
      "urls": [ ],
      "wait": "No wait.",
      "updated_at": "2014-04-16T19:51:28.610-07:00",
      "categories": [ ]
    }
  ],
  "organization": {
    "id": 4,
    "alternate_name": null,
    "date_incorporated": null,
    "description": "Redwood City Public Library",
    "email": null,
    "name": "Redwood City Public Library",
    "slug": "redwood-city-public-library",
    "website": null,
    "url": "https://ohana-api-demo.herokuapp.com/api/organizations/redwood-city-public-library",
    "locations_url": "https://ohana-api-demo.herokuapp.com/api/organizations/redwood-city-public-library/locations"
  }
}
```

This endpoint retrieves a specific location.

### HTTP Request

`GET https://ohana-api-demo.herokuapp.com/api/locations/1`

or

`GET https://ohana-api-demo.herokuapp.com/api/locations/redwood-shores-branch`

### URL Parameters

Parameter | Description
--------- | -----------
id | The ID or slug of the location to retrieve
