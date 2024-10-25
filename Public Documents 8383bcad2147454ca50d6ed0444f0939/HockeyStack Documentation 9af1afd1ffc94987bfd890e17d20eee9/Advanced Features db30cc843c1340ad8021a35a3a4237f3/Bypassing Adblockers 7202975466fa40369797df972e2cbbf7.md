# Bypassing Adblockers

To bypass adblockers, HockeyStack will use your own domain as the tracking URL. You will need to add a CNAME record pointing to `cdn.hockeystack.com` and add a parameter to the tracking code.

First, you should add a CNAME record pointing to `cdn.hockeystack.com`. Go to your domain registrar's admin panel, and create a new CNAME record with the following:

**Host:** This will be the subdomain for your website. Anything you want. Be sure it doesn't contain words such as `track`, `hockeystack`, or `tracker`. Examples include, but are not limited to, `pineapple`, `alpaca`, and, `hello`.

**Points to:** `cdn.hockeystack.com`

[Adding a CNAME record in GoDaddy](https://ca.godaddy.com/help/add-a-cname-record-19236)

[Adding a CNAME record in Cloudflare](https://support.cloudflare.com/hc/en-us/articles/360020615111-Configuring-a-CNAME-setup)

[Adding a CNAME record in Hover](https://help.hover.com/hc/en-us/articles/217282457-Managing-DNS-records-#h_5eab4aa7-b044-4cc6-a3c0-5869f583edc8)

[Adding a CNAME record in NameCheap](https://www.namecheap.com/support/knowledgebase/article.aspx/9646/2237/how-to-create-a-cname-record-for-your-domain)

[Adding a CNAME record in Hostinger](https://support.hostinger.com/en/articles/4738777-how-to-add-and-remove-cname-records-on-hpanel)

## **How to add the custom domain to the tracking code?**

All you need to do is change the source of the script tag.

### Example:

Change

```html
<script async data-apikey="<your-api-key>" data-cookieless src="https://cdn.hockeystack.com/script.js"></script>
```

to

```html
<script async data-apikey="<your-api-key>" data-cookieless src="https://cnamehost.yourdomain.com/script.js"></script>
```

### Example for other platforms:

Change

```html
<script>
  var script = document.createElement("script");
  script.id = "gtmhs";
  script.src = "https://cdn.hockeystack.com/script.js";
  script.async = 1;
  script.dataset.apikey = "<your-api-key>";
  script.dataset.cookieless = 1;
  document.getElementsByTagName('head')[0].appendChild(script);
</script>
```

to

```html
<script>
  var script = document.createElement("script");
  [scri](http://script.id/)pt.id = "gtmhs";
  script.src = "https://cnamehost.yourdomain.com/script.js";
  script.async = 1;
  script.dataset.apikey = "<your-api-key>";
  script.dataset.cookieless = 1;
  document.getElementsByTagName('head')[0].appendChild(script);
</script>
```

---

If you have any other questions or issues, you can always reach us through live support or just send an email to [hello@hockeystack.com](mailto:hello@hockeystack.com)!