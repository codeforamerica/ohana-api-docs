## Create a new contact

```ruby
# Create a contact for location with id 1
Ohanakapa.post('locations/1/contacts/', { department: 'Referrals', name: 'Moncef' })
```

```shell
curl -X POST "https://ohana-api-demo.herokuapp.com/api/locations/1/contacts" -d '{"department":"Referrals","name":"Moncef"}' -H "X-Api-Token: your_token" -H "Content-Type: application/json"
```

> When successful, the above command returns a `201` HTTP status code and JSON
> structured like this:

```json
{
  "id": 1,
  "email": null,
  "name": "Moncef",
  "title": null,
  "department": "Referrals",
  "phones": []
}
```

This endpoint creates a new contact for the specified entity.

### HTTP Request

`POST https://ohana-api-demo.herokuapp.com/api/locations/:location_id/contacts`

### JSON Parameters

| Name | Type | Requirement | Detail |
|:-----|:-----|:---------|:-------|
| name | string | required | The Contact's full name |
| title | string | optional | The Contact's title |
| email | string | optional | The Contact's email address |
| department | string | optional | The department where the Contact works. |

<aside class="warning">All POST requests require a valid token passed via the
`X-Api-Token` HTTP header</aside>
