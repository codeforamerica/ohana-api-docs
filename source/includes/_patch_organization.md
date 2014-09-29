## Update an existing organization

```ruby
# Update organization whose id is 1
Ohanakapa.patch('organizations/1', query: { name: 'Updated Name' })
```

```shell
curl --request PATCH "https://ohana-api-demo.herokuapp.com/api/organizations/1?name=Updated Name" \
  -H "X-Api-Token: your_secret_token"
```

> When successful, the above command returns a `200` HTTP status code and JSON
> structured like this:

```json
{
  "id": 1,
  "name": "Updated Name",
  "slug": "updated-name",
  "urls": [],
  "url": "http://ohana-api-demo.herokuapp.com/api/organizations/updated-name",
  "locations_url": "http://ohana-api-demo.herokuapp.com/api/organizations/updated-name/locations"
}
```

This endpoint updates an existing organization.

### HTTP Request

`PATCH https://ohana-api-demo.herokuapp.com/api/organizations/1`

### URL Parameters

Parameter | Description | Type | Required?
--------- | ----------- | ---- | ---------
name | The organization's name | String | Yes
urls | A list of the organization's websites | Array of Strings | No

<aside class="warning">All PATCH requests require a valid token passed via the
`X-Api-Token` HTTP header</aside>
