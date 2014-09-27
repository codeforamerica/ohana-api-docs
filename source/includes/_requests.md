# Making Requests

```shell
# In your shell, you can just pass the correct header with each request
curl "https://ohana-api-demo.herokuapp.com/api" \
  -H "User-Agent: MyClient/1.0.0"
```

```ruby
# Provide an API Endpoint
Ohanakapa.configure do |c|
  c.api_endpoint = 'https://ohana-api-demo.herokuapp.com/api'
end

# Fetch all locations
Ohanakapa.locations
```

If you are using your own client to communicate with Ohana API, please keep the following in mind:

- Always set the **User-Agent** header. Assuming your client is called "My Client", and its current version is 1.0.0, a good value would be `MyClient/1.0.0`.

- Always set the **Accept** header to `application/vnd.ohanapi+json; version=1`

Note that our [Ruby library](https://github.com/codeforamerica/ohanakapa-ruby) already does this for you.
