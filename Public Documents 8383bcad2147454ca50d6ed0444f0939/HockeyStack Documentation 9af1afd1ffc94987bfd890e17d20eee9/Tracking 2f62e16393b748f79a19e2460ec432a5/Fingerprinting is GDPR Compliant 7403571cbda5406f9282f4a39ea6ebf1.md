# Fingerprinting is GDPR Compliant

Ever since cookies fell out of fashion, one of the hottest debated subjects related to GDPR in recent years is whether fingerprinting is also ruled illegal in European countries. Since HockeyStack also uses its own fingerprinting technology, you might need to convince yourself or your customers that it is in fact legal **when used correctly**.

In this document, we will explain some of the main reasons why and how HockeyStack’s fingerprinting technology can be classified as GDPR compliant.

## Opt-in Banners

Most European companies already have an opt-in or a classic cookie banner when a visitor enters their website for the first time. When a visitor gives their consent, the necessary scripts that were mentioned in the banner are fired automatically. You can also add HockeyStack’s tracking script to this list so that you would only track the visitors who are aware and give their consent.

The HockeyStack snippet that you should use for this purpose is:

```html
<script>
  var script = document.createElement("script");
  script.id = "fphs";
  script.src = "https://cdn.jsdelivr.net/npm/hockeystack@latest/hockeystack.min.js";
  script.async = 1;
  script.dataset.apikey = "YOUR_API_KEY";
  script.dataset.cookieless = 1;
  document.getElementsByTagName('head')[0].appendChild(script);
</script>
```

Don’t forget to change YOUR_API_KEY with your own API key that you see from your dashboard.

If you don’t already have a banner like this, there are services that offer a free banner like [GlowCookies](https://github.com/manucaralmo/GlowCookies) so that you wouldn’t need to create one from scratch.

## Not Collecting PII

As you can see the list from [here](How%20Does%20Cookieless%20Tracking%20Work%2048fba433c0dd47289653eaee943fe7eb.md), HockeyStack does not track any PII (Personally Identifiable Information) like the IP address of the visitor directly. Instead, our identification method relies on the amount of non-PII data we collect which helps us create a unique profile for the visitor.

It basically means that there are no other visitors that have the exact same combination of all this device and geographical information that on their own are not actually PII. 

We don’t even store most of this data either. They are used to create an irreversible hash id of that visitor and then discarded after this process. More info about that is [here](How%20Does%20Cookieless%20Tracking%20Work%2048fba433c0dd47289653eaee943fe7eb.md).

## Relation to Third Parties

Whatever fingerprinting data we collect on these visitors - in no way, shape or form - is shared with or sold to a third party. This also ensures that we are not involuntarily a part of any non-compliant activity.

Here is a link to [our Privacy Policy](https://hockeystack.com/privacy-policy) for more details.