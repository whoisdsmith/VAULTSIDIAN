You can insert the time your Zap runs into any action by using the `{{zap_meta_human_now}}` command. This will print a human-readable date and time in the following format: `MM/DD/YY hh:mmAM/PM` (e.g.,`01/15/21 06:05PM`).

When used in a [date/time field](https://zapier.com/help/create/basics/different-field-types-in-zaps) and certain text fields, this command returns a date and time based on the time zone set in your Zapier [profile settings](https://zapier.com/help/create/customize/app/settings/profile). If you have no time zone selected, it will use UTC as the default.

[![Zap run time in message](https://cdn.zappy.app/476ccbd8e29a918bbb2bbf460d415fac.gif)](https://cdn.zappy.app/476ccbd8e29a918bbb2bbf460d415fac.gif)

When you add the `{{zap_meta_human_now}}` command to a field, it will show as "no data". However, the timestamp will be displayed when you test the step or when the Zap runs.

## [Machine-readable timestamps](https://zapier.com/help/create/customize/insert-the-time-your-zap-runs-into-a-field#machine-readable-timestamps)

You can use different versions of this command to ensure the correct date and time format is passed to certain apps.

## [{{zap\_meta\_utc\_iso}}](https://zapier.com/help/create/customize/insert-the-time-your-zap-runs-into-a-field#zap_meta_utc_iso)

This timestamp will print the date and time in a format that apps (and APIs) can easily read. This command will always output an ISO-8601 timestamp in UTC time (for example, 2021-01-15T18:07:48**+00:00**).

## [{{zap\_meta\_timestamp}}](https://zapier.com/help/create/customize/insert-the-time-your-zap-runs-into-a-field#zap_meta_timestamp)

This timestamp displays [UNIX time](https://en.wikipedia.org/wiki/Unix_time). Some APIs might require a timestamp in this format instead.

## [Other available timestamps](https://zapier.com/help/create/customize/insert-the-time-your-zap-runs-into-a-field#other-available-timestamps)

There are different commands you can use to ensure the timestamp uses specific timezones in the United States: