## Delete an existing service

```ruby
# Delete service with id 1 for location with id 1
Ohanakapa.delete('locations/1/service/1')
```

```shell
curl --request DELETE "https://ohana-api-demo.herokuapp.com/api/locations/1/service/1" -H "X-Api-Token: your_secret_token"
```

> When successful, the above command returns a `204` HTTP status code with an empty body.

This endpoint deletes an existing service.

### HTTP Request

`DELETE https://ohana-api-demo.herokuapp.com/api/locations/:location_id/service/:service_id`

<aside class="warning">All DELETE requests require a valid token passed via the
`X-Api-Token` HTTP header</aside>
