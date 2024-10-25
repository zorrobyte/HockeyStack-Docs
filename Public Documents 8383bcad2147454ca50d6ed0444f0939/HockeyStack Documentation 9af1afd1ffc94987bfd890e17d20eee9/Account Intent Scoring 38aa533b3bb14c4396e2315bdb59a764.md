# Account Intent Scoring

<aside>
⚠️ This section requires Intent Scoring to be available on your HockeyStack plan. If you’re unsure, feel free to ask your customer success manager.

</aside>

HockeyStack’s Intent Scoring uses all historical data you have gathered to score accounts on their predicted probability of conversion.

## How it works

![Screenshot 2023-12-03 at 13.20.10.png](Account%20Intent%20Scoring%2038aa533b3bb14c4396e2315bdb59a764/Screenshot_2023-12-03_at_13.20.10.png)

Go to Settings > Reporting & Tracking to find the configuration for scoring. There are two fields you need to fill out:

- **Intent Signals:** A selection of goals that can be used to score intent
- **Conversion Goal:** The conversion we are measuring probability for. Usually an inbound meeting booking, opportunity creation, or similar.

After you select these, Intent Scoring will run daily to update scores on all your accounts. The scores will be stored under the Company Property and User Property called “Lead Score”. There are 3 values that Lead Score can take:

- **Hot:** Score is 1 standard deviation above the average. (It is in the 84th percentile of all scored accounts)
- **Warm:** Score is between the average and 1 standard deviation above the average. (It is in the 50th percentile of all scored accounts)
- **Cold**: Score is below the average.

## Best Practices

- Your conversion goal needs to have enough volume so that HockeyStack can accurately analyze historical trends. Therefore it is better to select a broader goal.
- Each of your intent signals should have enough volume historically so that the score coefficients will be accurate. Therefore it is better to select broader goals, or bundle specific goals together that you think have similar intent levels.
    - For example: Viewing a very specific landing page might show really high intent, but if the data has only a few visits recorded to that page, the coefficient of scoring will be inaccurate.