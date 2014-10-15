# Schema

All data is sent and received as JSON. Blank fields are included as `null` instead of being omitted, and all timestamps are returned in ISO 8601 format:
`YYYY-MM-DDTHH:MM:SSZ`.

## Summary Representations

When you fetch a list of locations (via either the `locations` or the `search` endpoint), the response includes a subset of the attributes for that location. This is the “summary” representation of the resource. Some attributes are computationally expensive for the API to provide. For performance reasons, the summary representation excludes those attributes. To obtain those attributes, fetch the “detailed” representation.

The attributes that are excluded are `contacts` and `services`. Instead, the URLs to those attributes are provided as `contacts_url` and `services_url`.

The attributes provided in the summary representation are defined in the [Locations Serializer](https://github.com/codeforamerica/ohana-api/blob/master/app/serializers/locations_serializer.rb).

## Detailed Representations

When you fetch an individual resource, the response typically includes all attributes for that resource. This is the “detailed” representation of the resource.