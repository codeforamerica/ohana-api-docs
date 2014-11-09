## Create a new location

```ruby
# Create a new location for organization with id 1
Ohanakapa.post("organizations/1/locations",
  query: { name: 'New Location', description: 'New description' })
```

```shell
curl -X POST "https://ohana-api-demo.herokuapp.com/api/organizations/1/locations" -d '{"name":"New Location","description":"New description"}' -H "X-Api-Token: your_token" -H "Content-Type: application/json"
```

> When successful, the above command returns a `201` HTTP status code and JSON
> structured like this:

```json
{
  "id": 14,
  "name": "New Location",
  "slug": "new-location"
}
```

This endpoint creates a new location for the specified organization.

### HTTP Request

`POST https://ohana-api-demo.herokuapp.com/api/organizations/:organization_id/locations`

### JSON Parameters

| Name | Type | Requirement | Details |
--------- | ----------- | ---- | ---------
| accessibility | array of strings | optional | Accessibility options available at the location. Accepted values are `cd`, `deaf_interpreter`, `disabled_parking`, `elevator`, `ramp`, `restroom`, `tape_braille`, `tty`, `wheelchair`, and `wheelchair_van`. |
| address_attributes | object | required unless the location is marked as virtual | Physical address of location. See the [Address](#address) section for the columns in that table. |
| admin_emails | array of strings | optional | Email address for a person allowed to administer the location (via the Ohana API Admin interface for example). |
| alternate_name | String | optional | Another name this location might be known by. |
| contacts_attributes | array of objects | optional | Points of contact at the location. See the [Contacts](#contacts) section for the columns in that table. |
| latitude | float | optional | Latitude portion of the location's coordinates. Note that the app automatically geocodes addresses if the data doesn't include coordinates |
| longitude | float | optional | Longitude portion of the location's coordinates. Note that the app automatically geocodes addresses if the data doesn't include coordinates |
| description | string | required | Description of services provided at the location |
| email | string | optional | General Email address for location. Emails that belong to contacts should go in the Contact object. |
| holiday_schedules_attributes | array of objects | optional | Holiday hours of operation for the location. See [Holiday Schedules](#holiday-schedules) section for the columns in that table. |
| languages | array of strings | optional | Languages spoken at the location |
| mail_address_attributes | object | optional | Mailing address of location.  See the [Mail Address](#mail-address) section for the columns in that table. |
| name | string | required | Name of the location |
| phones_attributes | array of objects | optional | Phone numbers for the location. See the [Phones](#phones) section for the columns in that table. |
| regular_schedules_attributes | array of objects | optional | Regular hours of operation for the location. See [Regular Schedules](#regular-schedules) section for the columns in that table. |
| short_desc | string | optional | Succinct description of services provided at the location. |
| transportation | string | optional | Public transportation options near the location |
| website | string | optional | The location's website. Must include "http://" or "https://" |
| virtual | boolean | required if the location does not have a physical address | Whether or not the location has a physical address. If `false`, it must have an address associated with it. The default value is `false`. |


<aside class="warning">All POST requests require a valid token passed via the
`X-Api-Token` HTTP header</aside>

