# Actions

## `/data/api/goal`

Sends custom goals to HockeyStack.

| **identity** | `string` | *required* | The identity of the user, most commonly the email.  |
| --- | --- | --- | --- |
| **userProperties** | `object` | *optional* | The additional properties of a user. Accepts string and number values. |
| **actionDate** | `date` | *optional* | The ISO date at which the action happened. If not provided, falls back to the time of the request. |
| **actionName** | `string` | *required* | The name of the action given by the user. This is like the name of an ordinary goal. |
| **actionProperties** | `object` | *optional* | The additional properties of an action. Accepts string and number values. |
| **includeInAnalytics** | `boolean` | *optional* | Whether the action will be included while calculating metrics like session count. Individual custom goals create sessions that do not include any other action so it might ruin the accuracy of particular metrics. |

### How Can I Send Revenue Goals to HockeyStack?

Glad you asked. HockeyStack distinguishes revenue goals from other custom goals through `actionProperties`. Certain property names are reserved for this purpose. When you send data with these properties, HockeyStack will automatically detect that you are sending revenue data and make the necessary adjustments in your dashboard as well.

| **revenue** | `number` | *required* | The revenue number associated with the action. Can be either integer or double. |
| --- | --- | --- | --- |
| **currency** | `string` | *optional* | The three-letter code of the currency. See the full list [here](https://en.wikipedia.org/wiki/ISO_4217). If not specified, the main currency of the account will be used in revenue calculations. |
| **period** | `string` | *required* | The frequency of the payment. Accepts “one-time”, “month”, “year”. |

An example revenue goal would look like:

```json
{
	"apiKey": "82ee9e4a8b15fc058046998d5e9fbe",
	"identity": "jim@dundermifflin.com",
	"userProperties": {
    "company": "Dunder Mifflin",
		"plan": "Start",
    "employeeId": 47185,
		"renewsAt": "2025-12-31T00:00:00.000Z"
	},
	"actionDate": "2022-01-29T17:09:16.050Z",
	"actionName": "Upgraded Plan",
	"actionProperties": {
		"revenue": 300,
		"currency": "USD",
		"period": "month",
		"previousPlan": "Free"
	},
	"includeInAnalytics": 1
}
```

### How Can I Send Goals in Batches?

In order to send goals in batches, you need to add each goal’s data in an array called `actions`. This does not include authentication properties API Key and API Secret. An example of goals sent in batches would look like:

```json
{
	"apiKey": "82ee9e4a8b15fc058046998d5e9fbe",
	"actions": [
		{
			"identity": "jim@dundermifflin.com",
			"userProperties": {
				"company": "Dunder Mifflin",
				"plan": "Free",
		    "employeeId": 47185
			},
			"actionDate": "2022-01-28T14:12:43.761Z",
			"actionName": "Created Order",
			"actionProperties": {
				"order_id": 597,
				"type": "paper"
		  },
			"includeInAnalytics": 1
		},
		{
			"identity": "jim@dundermifflin.com",
			"userProperties": {
				"plan": "Start",
				"renewsAt": "2025-12-31T00:00:00.000Z"
			},
			"actionDate": "2022-01-29T17:09:16.050Z",
			"actionName": "Upgraded Plan",
			"actionProperties": {
				"revenue": 300,
				"currency": "USD",
				"period": "month"
			},
			"includeInAnalytics": 1
		}
	]
}
```

<aside>
⚠️ As you can see from the previous example, you do not need to send the same user properties for each goal. HockeyStack automatically keeps track of their latest version and updates only the relevant properties when a new request arrives.

</aside>