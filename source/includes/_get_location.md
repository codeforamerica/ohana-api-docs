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
  "name": "Redwood Shores Branch",
  "short_desc": "Provides general reading materials and reference services.",
  "slug": "redwood-shores-branch",
  "transportation": null,
  "website": "http://www.redwoodcity.org/library",
  "updated_at": "2014-09-09T07:54:08.641-07:00",
  "url": "https://ohana-api-demo.herokuapp.com/api/locations/redwood-shores-branch",
  "address": {
    "id": 14,
    "address_1": "399 Marine Parkway",
    "address_2": null,
    "city": "Redwood City",
    "state_province": "CA",
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
    "address_1": "399 Marine Parkway",
    "address_2": null,
    "city": "Redwood City",
    "state_province": "CA",
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
      "application_process": "Walk in. Proof of California residency required to receive a library card.",
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
      "categories": [],
      "contacts": [],
      "phones": [],
      "regular_schedules":[
        {
          "weekday":"Monday",
          "opens_at":"2000-01-01T08:00:00.000Z",
          "closes_at":"2000-01-01T12:00:00.000Z"
        },
        {
          "weekday":"Monday",
          "opens_at":"2000-01-01T14:00:00.000Z",
          "closes_at":"2000-01-01T16:00:00.000Z"
        },
        {
          "weekday":"Wednesday",
          "opens_at":"2000-01-01T10:00:00.000Z",
          "closes_at":"2000-01-01T15:00:00.000Z"
        }
      ],
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
    "id": 4,
    "alternate_name": null,
    "name": "Redwood City Public Library",
    "slug": "redwood-city-public-library",
    "url": "https://ohana-api-demo.herokuapp.com/api/organizations/redwood-city-public-library",
  }
}
```

This endpoint retrieves a specific location.

### HTTP Request

`GET https://ohana-api-demo.herokuapp.com/api/locations/1`

or

`GET https://ohana-api-demo.herokuapp.com/api/locations/redwood-shores-branch`

### Note about location status
For clients that display information about a particular Location, it
might make sense to display a warning or other message if the Location
currently doesn’t have any active services. You can determine if that’s
the case by checking if the Location’s JSON contains an `active`
attribute set to `false`.

### Note about holiday schedules
A location can have one more holiday schedules that describe whether or not the location is closed on a particular day of the year, or during a range of days. If the location is not closed, it will also provide `opens_at` and `closes_at` fields to describe the special holiday hours.

Although the `start_date` and `end_date` fields are provided as a `Date` type with day, month, and year details, make sure to only extract the day and month because the actual year is not guaranteed to be the current year. In addition, make sure you don't extract the weekday name from this field because it's not guaranteed to be correct. The only important information from this field is the month and the day of the month, such as `December 24`.

For a Ruby on Rails example of how you would display Regular and Holiday Schedules on website in a user-friendly manner, check out the [Ohana Web Search](https://github.com/codeforamerica/ohana-web-search/blob/master/app/helpers/schedules_helper.rb) source code.

### URL Parameters

Parameter | Description
--------- | -----------
id | The ID or slug of the location to retrieve
