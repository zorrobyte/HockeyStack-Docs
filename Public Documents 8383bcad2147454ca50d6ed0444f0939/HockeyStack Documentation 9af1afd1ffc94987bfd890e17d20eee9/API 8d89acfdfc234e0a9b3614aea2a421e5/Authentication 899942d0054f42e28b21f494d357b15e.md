# Authentication

In order to authenticate your requests, you need two pieces of data: an API key and an API secret.

## API Key

This is the same API key you’ve used in the code snippet you put on your website. You can access it again from **Settings > Domain Details**.

## API Secret

This is different from your API key and as the name suggests, you shouldn’t share it publicly. You can access it from **Settings > Integrations**.

# Sending the request

When sending a request to the API, you need to pass the API key as part of the request body. You can pass the API secret either using the Authorization request header with the `Secret` prefix (prioritized method) or as part of the request body like the API key (fallback method).

The below `curl` example features both of these cases:

```bash
curl -X POST https://hockeystack.com/data/api/goal \
  -H "Authorization: Secret <your-API-secret>" \
  -H "Content-Type: application/json" \
  -d '{"apiKey":"<your-API-key>", "apiSecret":"<your-API-secret>", <any-other-data>}' \
```