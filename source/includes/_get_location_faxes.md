# Faxes

## Get all faxes belonging to a location

```ruby
# Provide an API Endpoint
Ohanakapa.configure do |c|
  c.api_endpoint = 'https://ohana-api-demo.herokuapp.com/api'
end

# Fetch all faxes belonging to the location with id 1
Ohanakapa.get('locations/1/faxes')
```

```shell
curl "https://ohana-api-demo.herokuapp.com/api/locations/1/faxes" \
  -H "User-Agent: MyClient/1.0.0"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "number": "703-555-1212",
    "department": "Director of User Experience"
  },
  {
    "id": 2,
    "number": "703-444-1234",
    "department": "Chief Data Officer"
  }
]
```

This endpoint retrieves all faxes that belong to a particular location.

### HTTP Request

`GET https://ohana-api-demo.herokuapp.com/api/locations/:id/faxes`

Note that the URL above is just an example for the demo instance.
To access an API that serves a particular region, you would need to look up
the appropriate endpoint. All known API deployments are listed in the
[deployments](#live-deployments-of-ohana-api) section at the top of this page.

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
page | 1 | The particular page of results.
per_page | 30 | Amount of faxes to return per page, up to 100.
