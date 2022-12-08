You can use [Formatter’s](https://zapier.com/help/create/format/get-started-with-formatter) Date/Time transform to change dates and times in your Zap. The Date/Time transform can reformat dates and times or add/subtract time from existing date/time data.

If you have an app that formats dates as MM/DD/YYYY but you need to send it to an app that formats dates as DD/MM/YYYY, you can use the Date/Time transform to change the date format.

## [1\. Add a Formatter step](https://zapier.com/help/create/format/modify-date-and-time-formats-in-zaps#add-a-formatter-step)

Some Date/Time transforms will have additional required or optional fields.

___

## [2\. Customize your date and time options](https://zapier.com/help/create/format/modify-date-and-time-formats-in-zaps#customize-your-date-and-time-options)

Modify date and time formats in Zaps  
Adding a new option: o - for ordinal day of the month (1st, 20th, etc.)

You can represent dates and times by combining variables in the following table:

### [Date/Time custom value table](https://zapier.com/help/create/format/modify-date-and-time-formats-in-zaps#date-time-custom-value-table)

|  | **Token** | **Output** |
| --- | --- | --- |
| **Year** | YYYY | 2000, 2001, 2002 ... 2012, 2013 |
|  | YY | 00, 01, 02 ... 12, 13 |
| **Month** | MMMM | January, February, March ... |
|  | MMM | Jan, Feb, Mar ... |
|  | MM | 01, 02, 03 ... 11, 12 |
|  | M | 1, 2, 3 ... 11, 12 |
| **Day of Year** | DDDD | 001, 002, 003 ... 364, 365 |
|  | DDD | 1, 2, 3 ... 364, 365 |
| **Day of Month** | DD | 01, 02, 03 ... 30, 31 |
|  | D | 1, 2, 3 ... 30, 31 |
|  | Do | 1st, 2nd, 3rd ... 30th, 31st |
| **Day of Week** | dddd | Monday, Tuesday, Wednesday ... |
|  | ddd | Mon, Tue, Wed ... |
|  | d | 1, 2, 3 ... 6, 7 |
| **Hour** | HH | 00, 01, 02 ... 23, 24 |
|  | H | 0, 1, 2 ... 23, 24 |
|  | hh | 01, 02, 03 ... 11, 12 |
|  | h | 1, 2, 3 ... 11, 12 |
| **AM / PM** | A | AM, PM |
|  | a | am, pm |
| **Minute** | mm | 00, 01, 02 ... 58, 59 |
|  | m | 0, 1, 2 ... 58, 59 |
| **Second** | ss | 00, 01, 02 ... 58, 59 |
|  | s | 0, 1, 2 ... 58, 59 |
| **Sub-second** | SSS | 000, 001, 002 ... 998, 999 |
|  | SS | 00, 01, 02 ... 98, 99 |
|  | S | 0, 1, 2 ... 8, 9 |
| **Timezone** | ZZ | \-07:00, -06:00 ... +06:00, +07:00 |
|  | Z | \-0700, -0600 ... +0600, +0700 |
| **Timestamp** | X | 1381685817 |

___

## [3\. Test your Date/Time transform](https://zapier.com/help/create/format/modify-date-and-time-formats-in-zaps#test-your-date-time-transform)

Once you've set up the Formatter Date/Time transform, you can use the results in further actions in your Zap.