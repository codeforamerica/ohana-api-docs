## Delete an existing phone

```ruby
# Delete phone with id 1 for location 1
Ohanakapa.delete('/locations/1/phones/1')
```

```shell
curl --request DELETE "https://ohana-api-demo.herokuapp.com/api/locations/1/phones/1" -H "X-Api-Token: your_secret_token"
```

> When successful, the above command returns a `204` HTTP status code with an empty body.

This endpoint deletes an existing phone for the specified entity.

### HTTP Request

For locations:
`DELETE https://ohana-api-demo.herokuapp.com/api/locations/:location_id/phones/:phone_id`

For contacts:
`DELETE https://ohana-api-demo.herokuapp.com/api/locations/:location_id/contacts/:contact_id/phones/:phone_id`

<aside class="warning">All DELETE requests require a valid token passed via the
`X-Api-Token` HTTP header</aside>
