# Organizations

## Get all organizations

```ruby
# Provide an API Endpoint
Ohanakapa.configure do |c|
  c.api_endpoint = 'https://ohana-api-demo.herokuapp.com/api'
end

# Fetch all organizations
Ohanakapa.organizations
```

```shell
curl "https://ohana-api-demo.herokuapp.com/api/organizations" -H "User-Agent: MyClient/1.0.0"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 7,
    "accreditations": [],
    "alternate_name": null,
    "date_incorporated": null,
    "description": "An organization created for testing purposes.",
    "email": null,
    "funding_sources": [],
    "licenses": [],
    "name": "Admin Test Org",
    "slug": "admin-test-org",
    "website": null,
    "url": "http://ohana-api-demo.herokuapp.com/api/organizations/admin-test-org",
    "locations_url": "http://ohana-api-demo.herokuapp.com/api/organizations/admin-test-org/locations",
    "contacts": [],
    "phones": []
  },
  {
    "id": 6,
    "accreditations": [],
    "alternate_name": null,
    "date_incorporated": null,
    "description": "An organization created for testing purposes.",
    "email": null,
    "funding_sources": [],
    "licenses": [],
    "name": "Fake Org",
    "slug": "fake-org",
    "website": null,
    "url": "http://ohana-api-demo.herokuapp.com/api/organizations/fake-org",
    "locations_url": "http://ohana-api-demo.herokuapp.com/api/organizations/fake-org/locations",
    "contacts": [],
    "phones": []
  }
]
```

This endpoint retrieves all organizations.

### HTTP Request

`GET https://ohana-api-demo.herokuapp.com/api/organizations`

Note that the URL above is just an example for the demo instance.
To access an API that serves a particular region, you would need to look up
the appropriate endpoint. All known API deployments are listed in the
[deployments](#live-deployments-of-ohana-api) section at the top of this page.

### URL Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
page | 1 | The particular page of results.
per_page | 30 | Amount of organizations to return per page, up to 100.

