# Authentication

```ruby
# Provide an API Token
Ohanakapa.configure do |c|
  c.api_token = 'your_secret_token'
end

# Update location with id: 1
Ohanakapa.update_location(1, { name: 'New Name' })
```

```shell
# With shell, you can just pass the X-Api-Token header with each POST, PATCH, or DELETE request
curl --request PATCH "https://ohana-api-demo.herokuapp.com/api/locations/1?name=Foo" -H "X-Api-Token: your_secret_token"
```

Note that the [Ohana API Rails application](https://github.com/codeforamerica/ohana-api)
already comes with an admin interface, but if you wanted to write your own
standalone admin interface, you would need to pass a valid token via the
`X-Api-Token` HTTP header in all POST, PUT, PATCH, and DELETE requests.

If you have access to the API, you would need to set the `ADMIN_APP_TOKEN`
environment variable on the API server to the token sent by the admin app.
The easiest way to generate an API token is to register an application in the
appropriate developer portal.

If you don't have access to the API, you'll first need to get permission to
write to the API from the entity that is maintaining the data. For example,
if you want to be able to update San Mateo County data, you would need to
contact the Human Services Agency. If you're granted permission, then you
can register your application in the
[San Mateo County Developer portal](http://developer.smc-connect.org).
Once you obtain your API token, you'll need to ask the API maintainer to set
the `ADMIN_APP_TOKEN` environment variable on the API server to your token.

In most cases, it would not make sense to have multiple apps writing to the API
at the same time. Most communities will just use the built-in admin interface,
so if a community is already actively using the built-in admin interface, they
most likely will not grant write access to an external application.
