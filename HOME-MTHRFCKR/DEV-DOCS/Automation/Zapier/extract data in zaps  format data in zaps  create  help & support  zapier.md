With [Formatter](https://zapier.com/help/create/format/get-started-with-formatter), you can use the _Text_ extract function to perform a specific search within your text and return the first match found. This is useful if you have a lot of text (such as an email) and only want to use a certain part of it (such as the sender's phone number).

## [Add the Formatter app](https://zapier.com/help/create/format/extract-data-in-zaps#add-the-formatter-app)

___

## [Extract Email Address](https://zapier.com/help/create/format/extract-data-in-zaps#extract-email-address)

This function looks for a string of letters, numbers, and certain symbols (such as periods, plus signs, and dashes), immediately followed by an @ symbol, and then a site domain such as example.com.

___

## [Extract Number](https://zapier.com/help/create/format/extract-data-in-zaps#extract-number)

This function looks for one or more digits in a row. It can accommodate a single period used as a decimal separator, or multiple commas for digit grouping.

___

## [Extract Phone Number](https://zapier.com/help/create/format/extract-data-in-zaps#extract-phone-number)

This function looks for a 10-digit phone number either in groups of 3-3-4 digits, or groups of 4-3-3 digits, with an optional country code and extension number. The numbers can be separated by hyphens `-`, periods `.`, or spaces.

Area codes will be recognized when they are surrounded by parentheses, such as in the phone number `(123) 456-7890`.

To recognize an extension, the function looks for a number following either `x`, `ext`, or `extension` followed by the extension number.

___

## [Extract URL](https://zapier.com/help/create/format/extract-data-in-zaps#extract-url)

This function looks for a string of letters, numbers, and dashes, followed by a period, then a recognized [top-level domain (TLD)](https://en.wikipedia.org/wiki/Top-level_domain). It can also account for an "https://" or "http://" prefix, along with one or more [subdomains](https://en.wikipedia.org/wiki/Subdomain), folders, and query parameters.

If these extract functions cannot find the text you need, you can use the [Extract Pattern](https://zapier.com/help/create/format/find-text-with-regex-in-a-formatter-step) function to create a custom solution. Given the complexity of regular expressions, our support team cannot troubleshoot or provide support for them.

If you have questions about creating a custom regular expression pattern to meet your needs, we recommend reaching out to the [Zapier Community](https://community.zapier.com/).