# The Marketer’s Guide to Using Regex

Regex (Regular Expressions) is an immensely powerful tool to search in text, and can be used to create goals and filters quickly without adding too many and/or blocks.

For example, you’re looking for UTM Campaigns that either include “_brand_” in the middle of the text, or “_brand” at the end of the text, or “brand_” in the beginning of the text. If you were to do a ‘contains “brand_”’, this would also match “nonbrand_”, which you definitely don’t want. In this case, you would do “matches regex `/_brand_|^brand_|_brand$/`” to get the correct filter.

I know this looks really complex, but don’t get discouraged — it’s actually pretty easy! Let’s break it down.

- Every Regex would start and end with `/`. This denotes that this is Regex and it’s not just some random text.
- The `|` symbol means “OR”. You can think of this as a replacement for `,` when saying “contains one of”

So, if you want to create a filter that says “Deal Type contains one of Renewal, Upsell, Cross-Sell”, your regex would be: `/Renewal|Upsell|Cross-Sell/` 

- The `^` symbol means this is the beginning of the text.
- The `$` symbol means this is the end of the text.

So if you want to create a filter that says “UTM Campaign is empty”, your regex would be `/^$/` . You want to match, the beginning of the sentence, and the end of the sentence, with no text in between, which means it is empty!

- The `.` symbol matches any ****character.
- The regex for “is not empty” would be `/./`
- `\d` matches any number
- If you use any of the above characters in your match, you should preface it with `\` to say that “this is not a special character. this is just the text I want to match.” For example, a UTM Campaign containing “|” would have to be matched like this: `/\|/`
- **Regex in HockeyStack is case sensitive.**

You can use [regex101.com](http://regex101.com) to test your regex. (You can omit the `/` when testing here)