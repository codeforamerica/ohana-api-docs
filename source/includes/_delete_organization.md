## Delete an existing organization

```ruby
# Delete organization with id 1
Ohanakapa.delete('organizations/1')
```

```shell
curl --request DELETE "https://ohana-api-demo.herokuapp.com/api/organizations/1" \
  -H "X-Api-Token: your_secret_token"
```

> When successful, the above command returns a `204` HTTP status code with an empty body.

This endpoint deletes an existing organization.

### HTTP Request

`DELETE https://ohana-api-demo.herokuapp.com/api/organizations/:organization_id`

<aside class="warning">All DELETE requests require a valid token passed via the
`X-Api-Token` HTTP header</aside>
