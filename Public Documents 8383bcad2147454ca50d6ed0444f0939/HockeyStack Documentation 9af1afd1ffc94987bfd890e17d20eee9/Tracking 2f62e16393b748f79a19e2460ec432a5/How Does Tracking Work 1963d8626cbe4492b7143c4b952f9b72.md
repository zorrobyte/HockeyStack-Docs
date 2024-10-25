# How Does Tracking Work?

HockeyStack's automatic tracking is not magic, although it certainly feels like that. It happens through a script file hosted through a CDN network, much like any other web analytics tool out there. What separates HockeyStack from the general pack is that it listens to all events registered on your website so that it can track clicks, submissions, and searches, as well as pageviews.

The tracking script is at the time of this writing about 8.5 kilobytes. Although byte size definitely matters, an addition of this small magnitude would not affect your site speed at all.

A few notes:

- HockeyStack does not collect passwords or any other sensitive information from form submissions.
- HockeyStack —by default— does not use cookies to save identifiers.

Collected data:

- Website visit behavior, including pageviews, sessions, referrers, clicks, scrolls, form submissions
- Emails from forms submitted
- Geolocation data at the city granularity
- Device and browser metadata

---

If you have any other questions or issues, you can always reach us through the live support or just sending an email to [hello@hockeystack.com](mailto:hello@hockeystack.com)!