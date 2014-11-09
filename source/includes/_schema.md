# Schema

All data is sent and received as JSON. Blank fields are included as `null` instead of being omitted, and all timestamps are returned in ISO 8601 format:
`YYYY-MM-DDTHH:MM:SSZ`.

## Summary Representations

When you fetch a list of locations (via either the `locations` or the `search` endpoint), the response includes a subset of the attributes for that location. This is the “summary” representation of the resource. Some attributes are computationally expensive for the API to provide. For performance reasons, the summary representation excludes those attributes. To obtain those attributes, fetch the “detailed” representation.

The location attributes that are excluded from the `/search` and `/locations` endpoints are `accessibility`, `email`, `languages`, `transportation`, `mail_address`, `regular_schedules`, and `holiday_schedules`. The associated `contacts` and `services` are also excluded, but the URLs to those representations are provided as `contacts_url` and `services_url`. The `organization` association is also summarized to exclude `contacts` and `phones`.

The attributes provided in the summary representation are defined in the [Locations Serializer](https://github.com/codeforamerica/ohana-api/blob/master/app/serializers/locations_serializer.rb).


The [nearby](#nearby) endpoint returns an even smaller JSON representation consisting of the following attributes: `id`, `alternate_name`, `latitude`, `longitude`, `name`, `slug`, `address`.

## Detailed Representations

When you fetch an individual resource, the response typically includes all attributes for that resource. This is the “detailed” representation of the resource. One exception is when fetching an individual location. All of the location's attributes are included in the response, but the `organization` association is summarized to only include `id`, `alternate_name`, `name`, `slug`, and `url`.