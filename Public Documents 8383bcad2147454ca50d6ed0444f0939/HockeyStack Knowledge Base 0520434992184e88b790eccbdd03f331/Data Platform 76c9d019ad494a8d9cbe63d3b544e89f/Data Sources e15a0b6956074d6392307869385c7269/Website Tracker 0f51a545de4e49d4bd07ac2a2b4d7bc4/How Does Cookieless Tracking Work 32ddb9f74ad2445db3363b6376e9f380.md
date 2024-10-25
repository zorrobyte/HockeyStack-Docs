# How Does Cookieless Tracking Work?

In this day and age, opting out of cookies has become the default and tracking tools switching to cookie-less alternatives has become the fashion. Thankfully, the HockeyStack team follows the fashion trends.

The HockeyStack snippet that you receive when you sign up by default is modified for cookieless tracking:

```jsx
<script async data-apikey="YOUR_API_KEY" data-cookieless src="https://cdn.jsdelivr.net/npm/hockeystack@latest/hockeystack.min.js"></script>
```

The `data-cookieless` attribute runs the script under cookieless tracking and removing that would automatically switch you to cookie-based tracking.

## But then how do you track unique visitors?

Although we can't disclose all the details, we use a fingerprint generated at the server and hashed (sha256) with a unique salt so that it would be impossible to obtain the original data from the fingerprint.

To create this fingerprint, we use data such as but not limited to:

- Device type
- Screen height, width, and depth
- Browser
- OS
- Browser language
- Browser version
- Plugins installed
- Extensions
- Country and city-level geolocation data
- Timezone

All this data is gathered through the browser, and its variety ensures that the fingerprint created is as unique as possible.

<aside>
💡 It is important to note that HockeyStack does not in any way store IP addresses or other PII (personally identifiable information) to create this fingerprint.

The validity of the fingerprint relies on the combination of all these different datapoints. When hashed, it gives no one, including HockeyStack itself, to attain any further information about the visitor.

`ec5d7eb1-4c2b-4da0-a214-c7059f1fa9e6` This is an example user id that was generated from the system. As you can see, it is impossible to decrypt but gives you an opportunity to record unique traffic.

</aside>

If you have any concerns about how this fingerprinting technology complies with GDPR, you can read more about it here:

[Fingerprinting is GDPR Compliant](How%20Does%20Cookieless%20Tracking%20Work%2032ddb9f74ad2445db3363b6376e9f380/Fingerprinting%20is%20GDPR%20Compliant%203292c11b01774b379c3d402ccae0648c.md)

[Reverting to Cookie-Based Tracking ](https://www.notion.so/Reverting-to-Cookie-Based-Tracking-ef061e985748493fabe1e5796fa114af?pvs=21)

---

If you have any other questions or issues, you can always reach us through the live support or just sending an email to [hello@hockeystack.com](mailto:hello@hockeystack.com)!