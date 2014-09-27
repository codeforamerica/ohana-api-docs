# Pagination

Requests that return multiple items will be paginated to 30 items by default. You can specify further pages with the `?page` parameter. For some resources, you can also set a custom page size up to 100 with the `?per_page` parameter.

Note that page numbering is 1-based and that omitting the `?page` parameter will return the first page.

```shell
curl 'http://api.smc-connect.org/locations?page=2&per_page=10'
```

```ruby
Ohanakapa.locations(page: 2, per_page: 10)
```

## Link Header

The pagination info is included in the Link header. It is important to follow these Link header values instead of constructing your own URLs.

> A Link Header appears in the HTTP Response like this:

```
Link: <http://api.smc-connect.org/locations?page=57>; rel="last", <http://api.smc-connect.org/locations?page=2>; rel="next"
```

The possible `rel` values are:

Name  | Description
----  | -----------
next  | Shows the URL of the immediate next page of results.
last  | Shows the URL of the last page of results.
first | Shows the URL of the first page of results.
prev  | Shows the URL of the immediate previous page of results.