# Why is My HockeyStack Integration Failing?

Although it is very easy to add HockeyStack to your website, there can be many ways the process can go south due to site configurations, update periods and misplacement of the script. Here are some ways to overcome the issue, but keep in mind that if these do not work, we are one click away in the live support chat :)

# **Check whether the script is present in your site**

The first thing to do if the integration fails is to check whether the HockeyStack script was added your website at the first place. If it is not present, then it can't track your visitors yet.

In order to check, go to your website. You need to open your website's code using "**Inspect**". 

- In **Chrome**, right click and choose the **Inspect** option from the menu to open Chrome DevTools.
- In **Safari**, go to **Safari** > **Preferences** and then select the **Advanced** tab. Turn on "Show Develop menu in menu bar". Now, from the new **Develop** tab in your menu bar, click **Show Web Inspector**.
- In **Firefox**, right click and choose the **Inspect Element** option from the menu. Choose the **Elements** tab from the menu bar, and search for the keyword "**hockeystack**". If there are no results found, then the script was not yet added to your site.

## **The script isn't added to my site, how do I add it?**

First of all, go back to our [integration guide](https://www.notion.so/The-Definitive-Guide-to-Your-Initial-Integration-1a4df43666364fcdb4429e9f184d5583?pvs=21) and go over the steps to see whether you missed any.

If you are sure that you've added the script correctly, then the reason just might be that it takes time for the website to be updated. This is especially true for certain integration methods, like Google Tag Manager or Swipe Pages. Flush your cache, wait for 5-10 minutes if you just added the script, and search your website's code one more time.

<aside>
⚠️ If you are using the Google Tag Manager method and you have an adblocker, it probably blocks GTM too so it cannot load HockeyStack. Turn your adblocker off and refresh the site to see whether the script is added now.

</aside>

## **The script is added, but Integration still fails**

If you can see the script on your website, then we are one step closer to the solution :)

First, check your domain information. Make sure that you haven't mistakenly copied the API key of a different domain since each one you add generates a new, unique key. Also check that you wrote the domain url correctly in your HockeyStack dashboard, you can always update it from the Settings.

If you have an adblocker, it might also be a reason why HockeyStack does not verify the integration. Turn it off and visit your website again.

# **This domain already exists**

If you get this error, then it means that another account had already verified this domain url. If it wasn't you, please contact us from the live chat at the bottom right corner of the page.

---

If you have any other questions or issues, you can always reach us through the live support or just sending an email to [hello@hockeystack.com](mailto:hello@hockeystack.com)!