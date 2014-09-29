## Get a specific organization

```ruby
# Find an organization by id
Ohanakapa.organization(1)

# Find an organization by slug
Ohanakapa.organization('redwood-shores-branch')
```

```shell
# Find an organization by slug
curl "https://ohana-api-demo.herokuapp.com/api/organizations/redwood-shores-branch"

# Find an organization by id
curl "https://ohana-api-demo.herokuapp.com/api/organizations/1"
```

> When successful, the above command returns a `200` HTTP status code and JSON
> structured like this:

```json
{
  "id": 1365,
  "name": "South San Francisco Farmers Market",
  "slug": "south-san-francisco-farmers-market",
  "urls": [ ],
  "url": "http://ohana-api-demo.herokuapp.com/api/organizations/south-san-francisco-farmers-market",
  "locations_url": "http://ohana-api-demo.herokuapp.com/api/organizations/south-san-francisco-farmers-market/locations"
}
```

This endpoint retrieves a specific organization.

### HTTP Request

`GET https://ohana-api-demo.herokuapp.com/api/organizations/redwood-shores-branch`

or

`GET https://ohana-api-demo.herokuapp.com/api/organizations/1`
