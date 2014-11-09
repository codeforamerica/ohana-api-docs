## Get a specific organization

```ruby
# Find an organization by id
Ohanakapa.organization(1)

# Find an organization by slug
Ohanakapa.organization('peninsula-family-service')
```

```shell
# Find an organization by slug
curl "https://ohana-api-demo.herokuapp.com/api/organizations/peninsula-family-service"

# Find an organization by id
curl "https://ohana-api-demo.herokuapp.com/api/organizations/1"
```

> When successful, the above command returns a `200` HTTP status code and JSON
> structured like this:

```json
{
  "id": 1,
  "accreditations": [],
  "alternate_name": null,
  "date_incorporated": null,
  "description":"Peninsula Family Service strengthens the community by providing children, families, and older adults the support and tools to realize their full potential and lead healthy, stable lives.",
  "email": null,
  "funding_sources": [],
  "licenses": [],
  "name": "Peninsula Family Service",
  "slug": "peninsula-family-service",
  "website": null,
  "url": "http://ohana-api-demo.herokuapp.com/api/organizations/peninsula-family-service",
  "locations_url": "http://ohana-api-demo.herokuapp.com/api/organizations/peninsula-family-service/locations",
  "contacts":[
    {
      "department":"Operations",
      "email":"e.feeney@foobar.org",
      "id":32,
      "name":"Elizabeth Feeney",
      "title":"CEO",
      "phones":[
        {
          "id":54,
          "department":"Operations",
          "extension":null,
          "number":"703-444-1234",
          "number_type":"fax",
          "vanity_number":null
        },
        {
          "id":55,
          "department":"Operations",
          "extension":"101",
          "number":"650-555-1212",
          "number_type":"voice",
          "vanity_number":null
        }
      ]
    }
  ],
  "phones":[
    {
      "id":53,
      "department":"Operations",
      "extension":"101",
      "number":"123-456-7890",
      "number_type":"voice",
      "vanity_number":null
    }
  ]
}
```

This endpoint retrieves a specific organization.

### HTTP Request

`GET https://ohana-api-demo.herokuapp.com/api/organizations/peninsula-family-service`

or

`GET https://ohana-api-demo.herokuapp.com/api/organizations/1`

### URL Parameters

Parameter | Description
--------- | -----------
id | The ID or slug of the organization to retrieve
