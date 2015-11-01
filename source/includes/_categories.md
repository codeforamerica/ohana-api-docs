# Categories

## Get all categories

```ruby
# Provide an API Endpoint
Ohanakapa.configure do |c|
  c.api_endpoint = 'https://ohana-api-demo.herokuapp.com/api'
end

# Fetch all locations
Ohanakapa.categories
```

```shell
curl "https://ohana-api-demo.herokuapp.com/api/categories" -H "User-Agent: MyClient/1.0.0"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "depth": 0,
    "taxonomy_id": "101",
    "name": "Emergency",
    "parent_id": null
  },
  {
    "id": 2,
    "depth": 1,
    "taxonomy_id": "101-01",
    "name": "Disaster Response",
    "parent_id": 1
  },
  {
    "id": 3,
    "depth": 1,
    "taxonomy_id": "101-02",
    "name": "Emergency Cash",
    "parent_id": 1
  },
  {
    "id": 4,
    "depth": 2,
    "taxonomy_id": "101-02-01",
    "name": "Help Pay for Food",
    "parent_id": 3
  }
]
```

This endpoint retrieves all categories.

### HTTP Request

`GET https://ohana-api-demo.herokuapp.com/api/categories`

The categories are based on the taxonomy used by the instance of the API. By default, the API uses the [Open Eligibility](http://openeligibility.org/) Human Services taxonomy. Categories are organized in a tree structure using the [Ancestry gem](https://github.com/stefankroes/ancestry).
