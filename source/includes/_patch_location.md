## Update an existing location

```ruby
# Update location whose id is 1
Ohanakapa.update_location(1, { name: 'Updated Name' })
```

```shell
curl -X PATCH "https://ohana-api-demo.herokuapp.com/api/locations/1" -d '{"name":"Updated name"}' -H "X-Api-Token: test" -H "Content-Type: application/json"
```

> When successful, the above command returns a `200` HTTP status code and JSON
> structured like this:

```json
{
  "id": 14,
  "active": true,
  "accessibility": [ ],
  "admin_emails": [ ],
  "alternate_name": null,
  "coordinates": [
    -122.2586432,
    37.5304228
  ],
  "description": "Provides general reading materials, including large-type books, videos, music cassettes and CDs, and books on tape. Offers children's programs and a Summer Reading Club. Meeting room is available to nonprofit groups. Participates in the Peninsula Library System.",
  "email": null,
  "languages": [ ],
  "latitude": 37.5304228,
  "longitude": -122.2586432,
  "name": "Updated Name",
  "short_desc": "Provides general reading materials and reference services.",
  "slug": "redwood-shores-branch",
  "transportation": null,
  "website": "http://www.redwoodcity.org/library",
  "updated_at": "2014-09-09T07:54:08.641-07:00",
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
      "accepted_payments": [],
      "alternate_name": null,
      "audience": null,
      "description": null,
      "eligibility": "Resident of California to obtain a library card",
      "email": null,
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
      "languages": [],
      "name": null,
      "required_documents": [],
      "service_areas": [
        "San Mateo County"
      ],
      "status": "active",
      "website": null,
      "wait_time": "No wait.",
      "updated_at": "2014-04-16T19:51:28.610-07:00",
      "categories": [ ],
      "contacts": [],
      "phones": [],
      "regular_schedules":[],
      "holiday_schedules":[]
    }
  ],
  "regular_schedules":[
    {
      "weekday":"Monday",
      "opens_at":"2000-01-01T08:00:00.000Z",
      "closes_at":"2000-01-01T17:00:00.000Z"
    },
    {
      "weekday":"Tuesday",
      "opens_at":"2000-01-01T08:00:00.000Z",
      "closes_at":"2000-01-01T17:00:00.000Z"
    },
    {
      "weekday":"Wednesday",
      "opens_at":"2000-01-01T08:00:00.000Z",
      "closes_at":"2000-01-01T17:00:00.000Z"
    },
    {
      "weekday":"Thursday",
      "opens_at":"2000-01-01T08:00:00.000Z",
      "closes_at":"2000-01-01T17:00:00.000Z"
    },
    {
      "weekday":"Friday",
      "opens_at":"2000-01-01T08:00:00.000Z",
      "closes_at":"2000-01-01T17:00:00.000Z"
    },
    {
      "weekday":"Saturday",
      "opens_at":"2000-01-01T10:00:00.000Z",
      "closes_at":"2000-01-01T18:00:00.000Z"
    },
    {
      "weekday":"Sunday",
      "opens_at":"2000-01-01T11:00:00.000Z",
      "closes_at":"2000-01-01T17:00:00.000Z"
    }
  ],
  "holiday_schedules":[
    {
      "closed":true,
      "start_date":"0001-01-01",
      "end_date":"0001-01-01",
      "opens_at":null,
      "closes_at":null
    },
    {
      "closed":false,
      "start_date":"0001-12-24",
      "end_date":"0001-12-24",
      "opens_at":"2000-01-01T10:00:00.000Z",
      "closes_at":"2000-01-01T16:00:00.000Z"
    },
    {
      "closed":true,
      "start_date":"0001-06-01",
      "end_date":"0001-09-01",
      "opens_at":null,
      "closes_at":null
    }
  ],
  "organization": {
    "id": 8,
    "alternate_name": null,
    "name": "Admin Test Org",
    "slug": "admin-test-org",
    "url": "https://ohana-api-demo.herokuapp.com/api/organizations/admin-test-org",
  }
}
```

This endpoint updates an existing location.

### HTTP Request

`PATCH https://ohana-api-demo.herokuapp.com/api/locations/1`

### JSON Parameters

| Name | Type | Requirement | Details |
|:-----|:-----|:---------|:-------|
| accessibility | array of strings | optional | Accessibility options available at the location. Accepted values are `cd`, `deaf_interpreter`, `disabled_parking`, `elevator`, `ramp`, `restroom`, `tape_braille`, `tty`, `wheelchair`, and `wheelchair_van`. |
| admin_emails | array of strings | optional | Email address for a person allowed to administer the location (via the Ohana API Admin interface for example). |
| alternate_name | String | optional | Another name this location might be known by. |
| latitude | float | optional | Latitude portion of the location's coordinates. Note that the app automatically geocodes addresses if the data doesn't include coordinates |
| longitude | float | optional | Longitude portion of the location's coordinates. Note that the app automatically geocodes addresses if the data doesn't include coordinates |
| description | string | required | Description of services provided at the location |
| email | string | optional | General Email address for location. Emails that belong to contacts should go in the Contact object. |
| languages | array of strings | optional | Languages spoken at the location |
| name | string | required | Name of the location |
| short_desc | string | optional | Succinct description of services provided at the location. |
| transportation | string | optional | Public transportation options near the location |
| website | string | optional | The location's website. Must include "http://" or "https://" |
| virtual | boolean | required if the location does not have a physical address | Whether or not the location has a physical address. If `false`, it must have an address associated with it. The default value is `false`. |

<aside class="warning">All PATCH requests require a valid token passed via the
`X-Api-Token` HTTP header</aside>

