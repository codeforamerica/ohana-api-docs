# Cross Origin Resource Sharing

```shell
# A sample request sent from a browser hitting http://example.com:
$ curl -i https://ohana-api-demo.herokuapp.com/api/locations -H "Origin: http://example.com"

HTTP/1.1 200 OK
Access-Control-Allow-Origin: http://example.com
Access-Control-Allow-Methods: GET, PUT, PATCH, POST, DELETE
Access-Control-Expose-Headers: Etag, Last-Modified, Link, X-Total-Count
Access-Control-Max-Age: 1728000
Access-Control-Allow-Credentials: true
```

```shell
# A valid CORS preflight request must include the `Access-Control-Request-Method` header
$ curl -i https://ohana-api-demo.herokuapp.com/api/locations -H "Origin: http://example.com" -H "Access-Control-Request-Method: GET" -X OPTIONS

HTTP/1.1 200 OK
Access-Control-Allow-Origin: http://example.com
Access-Control-Allow-Methods: GET, PUT, PATCH, POST, DELETE
Access-Control-Expose-Headers: Etag, Last-Modified, Link, X-Total-Count
Access-Control-Max-Age: 1728000
Access-Control-Allow-Credentials: true
```

```shell
# A valid CORS preflight request can also include the `Allow-Control-Request-Headers` header:
$ curl -i https://ohana-api-demo.herokuapp.com/api/locations -H "Origin: http://example.com" -H "Access-Control-Request-Method: GET" -H "Access-Control-Request-Headers: If-None-Match" -X OPTIONS

HTTP/1.1 200 OK
Access-Control-Allow-Origin: http://example.com
Access-Control-Allow-Methods: GET, PUT, PATCH, POST, DELETE
Access-Control-Expose-Headers: Etag, Last-Modified, Link, X-Total-Count
Access-Control-Max-Age: 1728000
Access-Control-Allow-Credentials: true
Access-Control-Allow-Headers: If-None-Match
```

The API supports Cross Origin Resource Sharing (CORS) for AJAX requests. You can read the [CORS W3C working draft](http://www.w3.org/TR/cors) for more details.

The API supports the following endpoints for CORS requests:

- /organizations
- /locations
- /search

The following methods are allowed:

- GET, PUT, PATCH, POST, DELETE

The following additional headers are exposed:

- Etag
- Last-Modified
- Link
- X-Total-Count


View sample requests and responses on the right in the Shell tab.

View the [source code](https://github.com/codeforamerica/ohana-api/blob/master/config/application.rb#L43-52).
