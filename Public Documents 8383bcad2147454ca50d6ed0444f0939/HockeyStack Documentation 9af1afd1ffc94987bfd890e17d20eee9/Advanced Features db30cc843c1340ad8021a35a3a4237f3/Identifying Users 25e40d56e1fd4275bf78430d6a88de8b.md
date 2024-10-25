# Identifying Users

<aside>
⚠️ Beware, this guide requires basic coding and javascript knowledge.

</aside>

<aside>
⚠️ If you will be using personally identifiable information (PII) in your identifier, please include this in your privacy policy. HockeyStack bears no responsibility for holding this type of data.

</aside>

It is just as important to know who your users are as what actions they’ve performed.

You can send both a unique identifier (usually email but can also be another id, username etc.) and any other custom properties (plan, role, company etc.) of your users to HockeyStack.

Bear in mind that using this method does not send a separate action to HockeyStack, it only updates the properties of that user. For sending custom actions, see [Tracking Custom Goals](Tracking%20Custom%20Goals%2085721f0b370744aeb223121db0788829.md).

# Sending Unique Identifier

As mentioned before, this unique identifier is in most cases **the email of the user**. However, if you know the consequences (ask us!), you can send any other unique identifier - like an id or a username - here as well.

## Method #1

For this method, you would need HockeyStack to be already loaded in the website. See the [disclaimer](Identifying%20Users%2025e40d56e1fd4275bf78430d6a88de8b.md) for more technical info. Then, anywhere in your JavaScript, include:

```jsx
HockeyStack.identify('<your identifier>');
```

## Method #2

Change the script to include `data-identity`.

### Example for HTML

Add the highlighted section to your integration snippet:

```html
<script async **data-identity="<your identifier>"** data-apikey="<your api key>" data-cookieless src="https://cdn.jsdelivr.net/npm/hockeystack@latest/hockeystack.min.js"></script>
```

### Example for other platforms

Add the highlighted line to your integration snippet:

```html
<script>
  var hsscript = document.createElement("script");
  hsscript.id = "hockeystackscript";
  hsscript.src = "[https://cdn.jsdelivr.net/npm/hockeystack@latest/hockeystack.min.js](https://cdn.jsdelivr.net/npm/hockeystack@latest/hockeystack.min.js)";
  hsscript.async = 1;
  hsscript.dataset.apikey = "<your api key>";
  hsscript.dataset.cookieless = 1;
  hsscript.dataset.identity = <your identifier>;
  document.getElementsByTagName('head')[0].appendChild(hsscript);
</script>
```

# Sending Custom Properties

You can also send custom properties other than an identifier! It works similar to sending an identifier, but instead, you use an object:

```jsx
// assuming there is an object called `user` in your code that has the necessary data
HockeyStack.identify({
	plan: user.plan, // "Premium"
  revenue: user.revenue // 150.2
});

// or you can use the same identify call to both send a unique identifier and other custom properties
HockeyStack.identify(user.email,
	{
		plan: user.plan, // "Premium"
	  revenue: user.revenue // 150.2
	});
```

<aside>
🛠 You can send **Strings**, **Numbers** or **Booleans** as custom properties.

</aside>

# ⚠️ Disclaimer

You should be very careful whether the HockeyStack object has been defined in the code at that point or not. If not defined, your users can get an error that would prevent the rest of the script (where you added the `identify` function) from executing.

In order to overcome this error:

1. Or you can check whether the HockeyStack object is undefined.

```jsx
if (typeof HockeyStack !== 'undefined') HockeyStack.identify('<your identifier>');
```

2. Or you can put a try-catch block around the identify function:

```sql
try { HockeyStack.identify('<your identifier>'); } catch(e) {}
```

3. You can add another script that creates the HockeyStack buffer object:

```sql
<script>window.HockeyStack = window.HockeyStack || { identify: () => {}, goal: () => {} };</script>
```

---

If you have any other questions or issues, you can always reach us through the live support or just sending an email to [hello@hockeystack.com](mailto:hello@hockeystack.com)!