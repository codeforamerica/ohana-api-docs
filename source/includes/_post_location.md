## Create a new location

```ruby
# Create a new location
Ohanakapa.post("organizations/#{organization_id}/locations",
  query: { name: 'New Location' })
```

```shell
curl --request POST "https://ohana-api-demo.herokuapp.com/api/organizations/1/locations/?name=New Location" \
  -H "X-Api-Token: your_secret_token"
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

This endpoint creates a new location.

### HTTP Request

`POST https://ohana-api-demo.herokuapp.com/api/organizations/1/locations`

### URL Parameters

Parameter | Description | Type | Required?
--------- | ----------- | ---- | ---------
organization_id | The ID of the organization for which to create a location | Integer | Yes
description | The location's description | String | Yes
accessibility | The types of accessibility amenities available at the location | Array of Strings | No
admin_emails | The emails that are allowed to update the location | Array of Strings | No
emails | List of emails used to contact the location | Array of Strings | No
hours | The location's business hours | String | No
languages | The languages spoken at the location | Array of Strings | No
name | The location's name | String | Yes
short_desc | The location's short description | String | Depends on the API, but No by default
transportation | The transportation options closest to the location | String | No
urls | A list of the location's websites | Array of Strings | No
address_attributes | If you wish to create a location's address at the same time as the location creation, you can pass in the address attributes in the address_attributes hash | Hash | No
contacts_attributes | If you wish to create a location's contacts at the same time as the location creation, you can pass in the contacts attributes in the contacts_attributes hash | Hash | No
faxes_attributes | If you wish to create a location's faxes at the same time as the location creation, you can pass in the faxes attributes in the faxes_attributes hash | Hash | No
mail_address_attributes | If you wish to create a location's mailing address at the same time as the location creation, you can pass in the mail address attributes in the mail_address_attributes hash | Hash | No
phones_attributes | If you wish to create a location's phones at the same time as the location creation, you can pass in the phones attributes in the phones_attributes hash | Hash | No


<aside class="warning">All POST requests require a valid token passed via the
`X-Api-Token` HTTP header</aside>

