## Create a new organization

```ruby
# Create a new organization
Ohanakapa.post('organizations', query: { name: 'New Organization' })
```

```shell
curl -X POST "https://ohana-api-demo.herokuapp.com/api/organizations -d '{"name":"New Organization","description":"New description"}' -H "X-Api-Token: your_token" -H "Content-Type: application/json"
```

> When successful, the above command returns a `201` HTTP status code and JSON
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
  "name": "New Organization",
  "slug": "new-organization",
  "website": null,
  "url": "https://ohana-api-demo.herokuapp.com/api/organizations/new-organization",
  "locations_url": "https://ohana-api-demo.herokuapp.com/api/organizations/new-organization/locations"
}
```

This endpoint creates a new organization.

### HTTP Request

`POST https://ohana-api-demo.herokuapp.com/api/organizations`

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

<aside class="warning">All POST requests require a valid token passed via the
`X-Api-Token` HTTP header</aside>
