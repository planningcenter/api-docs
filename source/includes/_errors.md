# Errors

The PCO API uses the following error codes:

Error Code | Description           | Example Cause
---------- | --------------------- | -------------
400        | Bad Request           | Something is wrong in your request.
401        | Unauthorized          | You did not use the proper API token and/or secret.
403        | Forbidden             | You tried to view a resource you don't have access to; You tried to create a resource, but your user has an insufficient role.
404        | Not Found             | You've tried to access a URL or resource ID that doesn't exist.
500        | Internal Server Error | We had a problem with our server. Try again later.
503        | Service Unavailable   | We're temporarially offline for maintanance. Please try again later.
