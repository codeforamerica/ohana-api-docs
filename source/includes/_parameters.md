# Parameters

Many API methods take optional parameters. For GET requests to the `search` endpoint, parameters can be passed as an HTTP query string parameter:

`$ curl -i "https://ohana-api-demo.herokuapp.com/api/search?keyword=food"`

For POST, PATCH, and PUT requests, parameters not included in the URL should be encoded as JSON with a Content-Type of `application/json`:

`$ curl -X PATCH "https://ohana-api-demo.herokuapp.com/api/locations/1/address/1" -d '{"address_1":"New street","city":"Albequerque","state_province":"NM","postal_code":"12345","country":"US"}' -H "X-Api-Token: test" -H "Content-Type: application/json"`