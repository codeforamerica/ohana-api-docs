## Get a category's children categories

```ruby
# Provide an API Endpoint
Ohanakapa.configure do |c|
  c.api_endpoint = 'https://ohana-api-demo.herokuapp.com/api'
end

# Fetch all children of the category with a specific `oe_id`.
Ohanakapa.get('categories/:category_oe_id/children')
```

```shell
# Fetch all children of the category with a specific `oe_id`.

curl "https://ohana-api-demo.herokuapp.com/api/categories/101/children" -H "User-Agent: MyClient/1.0.0"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id":2,
    "depth":1,
    "oe_id":"101-01",
    "name":"Disaster Response",
    "parent_id":1
  },
  {
    "id":3,
    "depth":1,
    "oe_id":"101-02",
    "name":"Emergency Cash",
    "parent_id":1
  },
  {
    "id":10,
    "depth":1,
    "oe_id":"101-03",
    "name":"Emergency Food",
    "parent_id":1
  },
  {
   "id":11,
   "depth":1,
   "oe_id":"101-04",
   "name":"Emergency Shelter",
   "parent_id":1
  },
  {
    "id":12,
    "depth":1,
    "oe_id":"101-05",
    "name":"Help Find Missing Persons",
    "parent_id":1
  },
  {
    "id":13,
    "depth":1,
    "oe_id":"101-06",
    "name":"Immediate Safety",
    "parent_id":1
  },
  {
    "id":16,
    "depth":1,
    "oe_id":"101-07",
    "name":"Psychiatric Emergency Services",
    "parent_id":1
  }
]
```

This endpoint retrieves all children categories of a specific category.

### HTTP Request

`GET https://ohana-api-demo.herokuapp.com/api/categories/:category_oe_id/children`