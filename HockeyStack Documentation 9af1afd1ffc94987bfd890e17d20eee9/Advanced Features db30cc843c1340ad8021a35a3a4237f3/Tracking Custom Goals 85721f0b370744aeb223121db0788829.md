# Tracking Custom Goals

<aside>
⚠️ Beware, this guide requires basic coding and javascript knowledge.

</aside>

No analytics tool would be complete without giving you the opportunity to send custom goals yourself. In this guide, we will explore how this is possible with HockeyStack and how you can leverage this data in your dashboard.

## Within your code

Whether you want to track form submissions or specific button clicks, the general syntax to send this data back to HockeyStack is:

```jsx
HockeyStack.goal('Goal name' [, properties]);
```

Let's dissect this. The method takes in two arguments: a *required* `String` variable representing the name of the custom goal, and an *optional* `Object` variable consisting of any special property you want to send with your goal.

Here is an example goal you can send after the visitor added an item to their cart:

```jsx
HockeyStack.goal('Added to cart', {
	product: 'Rick Astley - Whenever You Need Somebody CD',
	productId: 23318,
	category: 'Music'
});
```

Keep in mind that this is also valid:

```jsx
HockeyStack.goal('Added to cart');
```

<aside>
⚠️ To send custom goals, you would need HockeyStack to be already loaded in the page. To make sure, you can define it as an empty object before the page loads or add a try-catch block around the goal method.

See the disclaimer in [Identifying Users](Identifying%20Users%2025e40d56e1fd4275bf78430d6a88de8b.md) for more details.

</aside>

<aside>
⚠️ Custom goals currently fully support String and Number variables as properties. You can also send Arrays or Objects, but you wouldn't be able to use the full functionalities of custom goals in the HockeyStack dashboard.

</aside>

## In Your HockeyStack Dashboard

After you send your custom goals, you can analyze them in your HockeyStack dashboard just like any other action.

Without any other configuration, custom goals show up in the **Users** page:

![Here you see HockeyStack's automatic tracking and custom goals together.
To see the properties, just click on that specific goal.](Tracking%20Custom%20Goals%2085721f0b370744aeb223121db0788829/Screen_Shot_2021-06-15_at_10.50.23.png)

Here you see HockeyStack's automatic tracking and custom goals together.
To see the properties, just click on that specific goal.

In order to track them as actual goals, there is one more step. Go to **Goals**, and click **+** at the top right corner. In your definition, choose **Custom Goals**. HockeyStack will list all the custom goals that you send to it here. You can choose whichever you want and define it as a normal goal.

This is *optional*, but you can also filter your custom goals through their properties. Click **+ property** and choose from the properties that HockeyStack detected automatically.

![Tracking%20Custom%20Goals%2085721f0b370744aeb223121db0788829/Screen_Shot_2021-06-15_at_11.10.47.png](Tracking%20Custom%20Goals%2085721f0b370744aeb223121db0788829/Screen_Shot_2021-06-15_at_11.10.47.png)

---

If you have any other questions or issues, you can always reach us through the live support or just sending an email to [hello@hockeystack.com](mailto:hello@hockeystack.com)!