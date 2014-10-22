## Delete an existing mail address

```ruby
# Delete mail address with id 1 for location with id 1
Ohanakapa.delete('locations/1/mail_address/1')
```

```shell
curl --request DELETE "https://ohana-api-demo.herokuapp.com/api/locations/1/mail_address/1" -H "X-Api-Token: your_secret_token"
```

> When successful, the above command returns a `204` HTTP status code with an empty body.

This endpoint deletes an existing mail address.

### HTTP Request

`DELETE https://ohana-api-demo.herokuapp.com/api/locations/:location_id/mail_address/:mail_address_id`

<aside class="warning">All DELETE requests require a valid token passed via the
`X-Api-Token` HTTP header</aside>
