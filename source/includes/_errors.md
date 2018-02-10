# Errors

The Ohana API uses the following error codes:

Error Code | Meaning
---------- | -------
400 | Bad Request -- You passed an invalid URL parameter
401 | Unauthorized -- You sent a missing or invalid `X-Api-Token` value
404 | Not Found -- The specified entity could not be found
406 | Not Acceptable -- You requested a format that isn't JSON
422 | Unprocessable Entity -- You sent an invalid entity attribute
500 | Internal Server Error -- The app generated an error. Please try again later.
503 | Service Unavailable -- We're temporarily offline. Please try again later.
