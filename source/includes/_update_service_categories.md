## Update a service's categories

```ruby
# Update categories for the service with id 1 by passing in an array of
# oe_ids.
Ohanakapa.put('services/1/categories', { oe_ids: ['101', '102'] })
```

```shell
# Update categories for the service with id 1 by passing in an array of
# oe_ids.

curl -X PUT "https://ohana-api-demo.herokuapp.com/api/services/1/categories" -d '{"oe_ids": ["101", "102"]}' -H "X-Api-Token: your_token" -H "Content-Type: application/json"
```

> When successful, the above command returns the updated service with a `200` HTTP status code:

```json
{
  "id":1,
  "accepted_payments":[],
  "alternate_name":null,
  "audience":"Older adults age 55 or over, ethnic minorities and low-income persons",
  "description":"A walk-in center for older adults that provides social services, wellness, recreational, educational and creative activities including arts and crafts, computer classes and gardening classes.",
  "eligibility":"Age 55 or over for most programs, age 60 or over for lunch program",
  "email":null,
  "fees":"$2.50 suggested donation for lunch for age 60 or over, donations for other services appreciated. Cash and checks accepted.",
  "funding_sources":["City","County","Donations","Fees","Fundraising"],
  "how_to_apply":"Walk in or apply by phone.",
  "keywords":[],
  "languages":[],
  "name":"Fair Oaks Adult Activity Center",
  "required_documents":[],
  "service_areas":["Colma"],
  "status":"active",
  "website":null,
  "wait":"No wait.",
  "updated_at":"2014-10-21T16:02:55.656-07:00",
  "categories":[
    {
      "id": 1,
      "depth": 0,
      "oe_id": "101",
      "name": "Emergency",
      "parent_id": null
    },
    {
      "id": 17,
      "depth": 0,
      "oe_id": "102",
      "name": "Food",
      "parent_id": null
    }
  ]
}
```

This endpoint updates a service with the specified categories.

### HTTP Request

`PUT https://ohana-api-demo.herokuapp.com/api/services/:service_id/categories`

### JSON Parameters

| Name | Type | Requirement | Detail |
|:-----|:-----|:---------|:-------|
| oe_ids | Array | required | An array of valid `oe_id`s. |

<aside class="warning">All PUT requests require a valid token passed via the
`X-Api-Token` HTTP header</aside>
