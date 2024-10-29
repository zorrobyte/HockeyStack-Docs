---
hidden: true
---

# ActiveCampaign API Errors

## ActiveCampaign API Errors

## Headers

```json

{
"Accept": "application/json, text/plain, */*",
"Api-Token": "8a54e2648f91bf2d87c7847c6b9778e0899615db9a895cd6a672687250d20366fcd72ee4",
"User-Agent": "axios/0.21.4"
}
```

## Requests

*   [https://ac.api-us1.com/api/3/activities](https://ac.api-us1.com/api/3/activities)

    ### Status

    `500 - Internal Server Error`

    ### Response

    ```xml
    <?xml version="1.0" encoding="iso-8859-1"?>
    <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
    "[http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd](http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd)">
    <html xmlns="[http://www.w3.org/1999/xhtml](http://www.w3.org/1999/xhtml)" xml:lang="en" lang="en">
    <head>
    <title>500 Internal Server Error</title>
    </head>
    <body>
    <h1>500 Internal Server Error</h1>
    </body>
    </html>
    ```

    ### Query Parameters

    ```json
    {
    "after": "2022-10-23T16:46:08+00:00",
    "include": "reference.link,reference.contact,reference.message,reference.log,reference.log.message",
    "limit": 100,
    "offset": 4600,
    "orders[tstamp]": "ASC"
    }
    ```
*   [https://ac.api-us1.com/api/3/contacts/269413](https://ac.api-us1.com/api/3/contacts/269413)

    ### Status

    `502 - Bad Gateway`

    ### Response

    ```html
    <html>
    <head><title>502 Bad Gateway</title></head>
    <body>
    <center><h1>502 Bad Gateway</h1></center>
    <hr><center>cloudflare</center>
    </body>
    </html>
    ```
*   [https://ac.api-us1.com/api/3/activities](https://ac.api-us1.com/api/3/activities)

    ### Status

    `504 - Gateway Timeout`

    ### Query Parameters

    ```json
    {
    "after": "2022-10-23T15:17:32+00:00",
    "include": "reference.link,reference.contact,reference.message,reference.log,reference.log.message",
    "limit": 100,
    "offset": 9900,
    "orders[tstamp]": "ASC"
    }
    ```
