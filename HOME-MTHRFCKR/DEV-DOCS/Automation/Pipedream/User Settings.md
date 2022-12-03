You can find important account details, text editor configuration, and more in your [Settings (opens new window)](https://pipedream.com/settings).

-   [Account](https://pipedream.com/docs/#account)
    -   [Username](https://pipedream.com/docs/#username)
    -   [Changing your username](https://pipedream.com/docs/#changing-your-username)
    -   [Changing your email](https://pipedream.com/docs/#changing-your-email)
    -   [Pipedream API Key](https://pipedream.com/docs/#pipedream-api-key)
    -   [Delete Account](https://pipedream.com/docs/#delete-account)
-   [Application](https://pipedream.com/docs/#application)
-   [Environment Variables](https://pipedream.com/docs/#environment-variables)
-   [Billing and Usage](https://pipedream.com/docs/#billing-and-usage)
    -   [Subscription](https://pipedream.com/docs/#subscription)
    -   [Usage](https://pipedream.com/docs/#usage)
    -   [Limits](https://pipedream.com/docs/#limits)

## [#](https://pipedream.com/docs/#account) Account

You'll find your Pipedream username, email, and other basic account details in your [Account Settings (opens new window)](https://pipedream.com/settings/account).

### [#](https://pipedream.com/docs/#username) Username

Your Pipedream username functions as your user or org identity. If you've made any resources [public](https://pipedream.com/docs/public-workflows/), these resources will appear on your public profile at:

You can change your username at any time (see below).

### [#](https://pipedream.com/docs/#changing-your-username) Changing your username

You can change your Pipedream username by editing the **Username** field in your Account Settings.

Existing workflow URLs that contain your old username will continue to resolve to the correct workflow. However, links to your public profile with your old username (for example, [https://pipedream.com/@old-username (opens new window)](https://pipedream.com/@old-username)) will no longer resolve.

### [#](https://pipedream.com/docs/#changing-your-email) Changing your email

Pipedream sends system emails to the email address tied to your Pipedream login - for example, [error notifications](https://pipedream.com/docs/workflows/error-handling/global-error-workflow/) and emails sent using [`$send.email()`](https://pipedream.com/docs/destinations/email/).

You can change the email address to which these emails are delivered by modifying the **Email** in your Account Settings. Once changed, an email will be delivered to the new address requesting you verify it.

Pipedream marketing emails may still be sent to the original email address you used when signing up for Pipedream. To change the email address tied to marketing emails, please [reach out to our team (opens new window)](https://pipedream.com/support).

### [#](https://pipedream.com/docs/#pipedream-api-key) Pipedream API Key

Pipedream provides a [REST API](https://pipedream.com/docs/api/overview/) for interacting with Pipedream programmatically. You'll find your API key here, which you use to [authorize requests to the API](https://pipedream.com/docs/api/auth/).

You can revoke and regenerate your API key from here at any time.

### [#](https://pipedream.com/docs/#delete-account) Delete Account

You can delete your Pipedream account at any time by visiting your Account Settings and pressing the **Delete your Account** button. Account deletion is immediately and irreversible.

## [#](https://pipedream.com/docs/#application) Application

You can change how the Pipedream app displays data, and basic text editor config, in your [Application Settings (opens new window)](https://pipedream.com/settings/app).

For example, you can:

-   Change the clock format to 12-hour or 24-hour mode
-   Enable Vim keyboard shortcuts in the Pipedream text editor, or enable word wrap
-   Set the number of spaces that will be added in the editor when pressing `Tab`

## [#](https://pipedream.com/docs/#environment-variables) Environment Variables

Environment variables allow you to securely store secrets or other config values that you can access in Pipedream workflows via `process.env`. [Read more about environment variables here](https://pipedream.com/docs/environment-variables/).

## [#](https://pipedream.com/docs/#billing-and-usage) Billing and Usage

You'll find information on your usage data (for specific [Pipedream limits](https://pipedream.com/docs/limits/)) in your [Billing Settings (opens new window)](https://pipedream.com/settings/billing). You can also upgrade to [paid plans (opens new window)](https://pipedream.com/pricing) from this page.

### [#](https://pipedream.com/docs/#subscription) Subscription

You can upgrade to [paid plans (opens new window)](https://pipedream.com/pricing) from this section.

If you've already upgraded, you'll see an option to **Manage Subscription** here, which directs you to your personal Stripe portal. Here, you can change your payment method, review the details of previous invoices, and more.

### [#](https://pipedream.com/docs/#usage) Usage

[Invocations](https://pipedream.com/docs/pricing/#invocations) are Pipedream's billable unit, and [free users](https://pipedream.com/docs/pricing/#developer-tier) are limited on the number of daily invocations they can run. The **Usage** section displays a chart of the daily invocations across a historical range of time to provide insight into your usage patterns.

Hover over a specific column in the chart to see the number of invocations run for that specific day:

![Daily invocations tooltip](https://pipedream.com/docs/assets/img/daily-invocations-tooltip.5e2d664c.png)

_Click_ on a specific column to see invocations for that day, broken out by workflow / source:

![Invocations broken out by workflow / source](https://pipedream.com/docs/assets/img/usage-by-resource.e8d694aa.png)

[Developer (free) tier](https://pipedream.com/docs/pricing/#developer-tier) users will see the last 30 days of usage in this chart. Users on [paid plans (opens new window)](https://pipedream.com/pricing) will see the cumulative usage tied to their current billing period.

### [#](https://pipedream.com/docs/#limits) Limits

For users on the [Developer (free) tier](https://pipedream.com/docs/pricing/#developer-tier), this section displays your usage towards your [invocations](https://pipedream.com/docs/limits/#daily-invocations) and [compute time](https://pipedream.com/docs/limits/#compute-time-per-day) quota for the current UTC day.