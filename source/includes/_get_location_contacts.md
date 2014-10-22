# Contacts

## Get all contacts belonging to a location

```ruby
# Provide an API Endpoint
Ohanakapa.configure do |c|
  c.api_endpoint = 'https://ohana-api-demo.herokuapp.com/api'
end

# Fetch all contacts belonging to the location with id 1
Ohanakapa.get('locations/1/contacts')
```

```shell
curl "https://ohana-api-demo.herokuapp.com/api/locations/1/contacts" -H "User-Agent: MyClient/1.0.0"
```

> The above command returns JSON structured like this:

```json
[
  {
    "department": null,
    "email": null,
    "id": 1,
    "name": "Susan Houston",
    "title": "Director of Older Adult Services",
    "phones": []
  },
  {
    "department": null,
    "email": null,
    "id": 2,
    "name": " Christina Gonzalez",
    "title": "Center Director",
    "phones": []
  }
]
```

This endpoint retrieves all contacts that belong to a particular location.

### HTTP Request

`GET https://ohana-api-demo.herokuapp.com/api/locations/:id/contacts`

### URL Parameters

Parameter | Default | Description
--------- | ------- | -----------
page | 1 | The particular page of results.
per_page | 30 | Amount of contacts to return per page, up to 100.
