## Update an existing organization

```ruby
# Update organization whose id is 1
Ohanakapa.patch('organizations/1', query: { name: 'Updated Name' })
```

```shell
curl -X PATCH "https://ohana-api-demo.herokuapp.com/api/organizations/1/address/1" -d '{"name":"Updated Name"}' -H "X-Api-Token: test" -H "Content-Type: application/json"
```

> When successful, the above command returns a `200` HTTP status code and JSON
> structured like this:

```json
{
  "id": 1,
  "accreditations": [],
  "alternate_name": null,
  "date_incorporated": null,
  "description": "Test description",
  "email": null,
  "funding_sources": [],
  "licenses": [],
  "name": "Updated Name",
  "slug": "updated-name",
  "website": null,
  "url": "https://ohana-api-demo.herokuapp.com/api/organizations/admin-test-org",
  "locations_url": "https://ohana-api-demo.herokuapp.com/api/organizations/admin-test-org/locations",
  "contacts": [],
  "phones": []
}
```

This endpoint updates an existing organization.

### HTTP Request

`PATCH https://ohana-api-demo.herokuapp.com/api/organizations/1`

### JSON Parameters

| Name | Type | Requirement | Details |
|:-----|:-----|:---------|:-------|
| accreditations | Array of Strings | optional | A list of accreditations an organization has received. |
| alternate_name | String | optional | Another name this organization might be known by. |
| date_incorporated | Date | optional | The date this organization was incorporated. |
| description | String | required | A description of what the organization does. |
| email | String | optional | The organization's primary email. |
| funding_sources | Array of Strings | optional | A list of sources of funds for an organization. |
| legal_status | String | optional | The conditions an organization is operating under; e.g. non-profit, private corporation or a government organization. |
| licenses | Array of Strings | optional | A list of licenses an organization has obtained to operate legally. |
| name | String | required | Name of the organization |
| tax_id | String | optional | Tax identifier, such as Federal Employer Identification Number. |
| tax_status | String | optional | Internal Revenue Service tax designation, such as `501(c)(3)` for tax-exempt organizations. |
| website | String | optional | The organization's website |

<aside class="warning">All PATCH requests require a valid token passed via the
`X-Api-Token` HTTP header</aside>
