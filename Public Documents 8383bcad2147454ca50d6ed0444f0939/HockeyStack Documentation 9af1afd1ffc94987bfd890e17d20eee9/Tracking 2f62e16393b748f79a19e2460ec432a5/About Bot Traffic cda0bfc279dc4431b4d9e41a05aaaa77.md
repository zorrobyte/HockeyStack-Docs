# About Bot Traffic

Analytics tools should be able to differentiate between real traffic vs bot traffic. At HockeyStack, we make this possible through three different methods:

## `navigator.webdriver`

This is not the most robust method, but it is the easiest to explain. Webdrivers control browsers remotely and act like real users to perform a variety of tasks, rangin from simple automations to data crawling. By default, they should enable this variable in the `navigator` object, so we check it to eliminate possible bot traffic.

## IP Address

This is a lot more common. Most crawlers and performance tools have specific IP adresses that they reach their website from. We keep and update a list of those in order to recognize the traffic. Keep in mind that we don't store any tracked IP addresses, and these are just deleted once a response has been sent from the server.

## User-Agent

Very much like IP addresses, we store a list of terms that bot traffic insert to their user agents. This is updated the most frequently and is checked first on the browser-side in order to prevent any requests being sent to our servers.

<aside>
💡 If you suspect that HockeyStack is not able to detect a certain bot, we are more than happy to update our lists! Just write us through the live support chat or send an email to [hello@hockeystack.com](mailto:hello@hockeystack.com).

</aside>

---

If you have any other questions or issues, you can always reach us through the live support or just sending an email to [hello@hockeystack.com](mailto:hello@hockeystack.com)!