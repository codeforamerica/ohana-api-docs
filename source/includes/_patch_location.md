## Update an existing location

```ruby
# Update location whose id is 1
Ohanakapa.update_location(1, { name: 'Updated Name' })
```

```shell
curl --request PATCH "https://ohana-api-demo.herokuapp.com/api/locations/1?name=Updated Name" \
  -H "X-Api-Token: your_secret_token"
```

> When successful, the above command returns a `200` HTTP status code and JSON
> structured like this:

```json
{
  "id": 14,
  "accessibility": [ ],
  "admin_emails": [ ],
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
  "name": "Updated Name",
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
    "street": "399 Marine Parkway.",
    "city": "Redwood City",
    "state": "CA",
    "zip": "94065"
  },
  "contacts": [
    {
      "email": null,
      "extension": null,
      "fax": null,
      "id": 22,
      "name": "Dave Genesy",
      "phone": null,
      "title": "Library Director"
    }
  ],
  "faxes": [ ],
  "mail_address": {
    "id": 14,
    "attention": "Redwood Shores Branch",
    "street": "399 Marine Parkway",
    "city": "Redwood City",
    "state": "CA",
    "zip": "94065"
  },
  "phones": [
    {
      "id": 15,
      "department": null,
      "extension": null,
      "number": "650 780-5740",
      "number_type": null,
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
    "name": "Redwood City Public Library",
    "slug": "redwood-city-public-library",
    "urls": [ ],
    "url": "https://ohana-api-demo.herokuapp.com/api/organizations/redwood-city-public-library",
    "locations_url": "https://ohana-api-demo.herokuapp.com/api/organizations/redwood-city-public-library/locations"
  }
}
```

This endpoint updates an existing location.

### HTTP Request

`PATCH https://ohana-api-demo.herokuapp.com/api/locations/1`

### URL Parameters

Parameter | Description | Type | Required?
--------- | ----------- | ---- | ---------
accessibility | The types of accessibility amenities available at the location | Array of Strings | No
admin_emails | The emails that are allowed to update the location | Array of Strings | No
description | The location's description | String | Yes
emails | List of emails used to contact the location | Array of Strings | No
hours | The location's business hours | String | No
languages | The languages spoken at the location | Array of Strings | No
name | The location's name | String | Yes
short_desc | The location's short description | String | Depends on the API, but No by default
transportation | The transportation options closest to the location | String | No
urls | A list of the location's websites | Array of Strings | No

<aside class="warning">All PATCH requests require a valid token passed via the
`X-Api-Token` HTTP header</aside>

