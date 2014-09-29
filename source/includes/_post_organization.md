## Create a new organization

```ruby
# Create a new organization
Ohanakapa.post('organizations', query: { name: 'New Organization' })
```

```shell
curl --request POST "https://ohana-api-demo.herokuapp.com/api/organizations?name=New Organization" \
  -H "X-Api-Token: your_secret_token"
```

> When successful, the above command returns a `201` HTTP status code and JSON
> structured like this:

```json
{
  "id": 14,
  "name": "New Organization",
  "slug": "new-organization",
  "urls": [],
  "url": "http://ohana-api-demo.herokuapp.com/api/organizations/new-organization",
  "locations_url": "http://ohana-api-demo.herokuapp.com/api/organizations/new-organization/locations"
}
```

This endpoint creates a new organization.

### HTTP Request

`POST https://ohana-api-demo.herokuapp.com/api/organizations`

### URL Parameters

Parameter | Description | Type | Required?
--------- | ----------- | ---- | ---------
name | The organization's name | String | Yes
urls | A list of the organization's websites | Array of Strings | No

<aside class="warning">All POST requests require a valid token passed via the
`X-Api-Token` HTTP header</aside>
