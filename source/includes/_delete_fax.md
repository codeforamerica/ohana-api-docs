## Delete an existing fax

```ruby
# Delete fax with id 1 for location with id 1
Ohanakapa.delete('locations/1/faxes/1')
```

```shell
curl --request DELETE "https://ohana-api-demo.herokuapp.com/api/locations/1/faxes/1" \
  -H "X-Api-Token: your_secret_token"
```

> When successful, the above command returns a `204` HTTP status code with an empty body.

This endpoint deletes an existing fax.

### HTTP Request

`DELETE https://ohana-api-demo.herokuapp.com/api/locations/:location_id/faxes/:fax_id`

<aside class="warning">All DELETE requests require a valid token passed via the
`X-Api-Token` HTTP header</aside>
