## Update an existing contact

```ruby
# Update contact with id 1 for location with id 1
Ohanakapa.patch('locations/1/contacts/1', { street: 'Updated Street' })
```

```shell
curl -X PATCH "https://ohana-api-demo.herokuapp.com/api/locations/1/contacts/1" -d '{"title":"Updated title"}' -H "X-Api-Token: test" -H "Content-Type: application/json"
```

> When successful, the above command returns a `200` HTTP status code and JSON
> structured like this:

```json
{
  "id": 1,
  "email": null,
  "name": "Moncef",
  "title": "Updated title",
  "department": "Referrals",
  "phones": []
}
```

This endpoint updates an existing contact for the specified location.

### HTTP Request

`PATCH https://ohana-api-demo.herokuapp.com/api/locations/:location_id/contacts/:contact_id`

### JSON Parameters

| Name | Type | Requirement | Detail |
|:-----|:-----|:---------|:-------|
| name | string | required | The Contact's full name |
| title | string | optional | The Contact's title |
| email | string | optional | The Contact's email address |
| department | string | optional | The department where the Contact works. |

<aside class="warning">All PATCH requests require a valid token passed via the
`X-Api-Token` HTTP header</aside>
