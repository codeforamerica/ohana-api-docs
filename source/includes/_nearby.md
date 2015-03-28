# Nearby

## Find locations that are near a specific location.

```ruby
# Provide an API Endpoint
Ohanakapa.configure do |c|
  c.api_endpoint = 'https://ohana-api-demo.herokuapp.com/api'
end

# Fetch all locations within 2 miles of ZIP code 94103
Ohanakapa.get('locations/22/nearby', radius: 2)
```

```shell
curl "https://ohana-api-demo.herokuapp.com/api/locations/22/nearby?radius=2" -H "User-Agent: MyClient/1.0.0"
```

> The above command returns a summarized JSON representation containing the following location attributes:

```json
[
  {
    "id": 15,
    "alternate_name": null,
    "latitude": 37.7517064,
    "longitude": -122.4456187,
    "name": "New location test",
    "slug": "new-location-test",
    "address": {
      "id": 28,
      "address_1": "1290 Ridder Park Drive",
      "address_2": null,
      "city": "San Francisco",
      "state_province": "CA",
      "postal_code": "94103"
    }
  }
]
```

This endpoint retrieves all locations that are near the specified location.

### HTTP Request

`GET https://ohana-api-demo.herokuapp.com/api/locations/:location_id/nearby`

### URL Query Parameters

Parameter | Description
--------- | -----------
radius | Default in miles is 0.5, minimum is 0.1, and maximum is 50.
page | The particular page of results. Default is 1.
per_page | Amount of locations to return per page, up to 100. Default is 30.