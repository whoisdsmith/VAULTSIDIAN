# Day One URL Scheme

Day One iOS and Mac apps support URLs to send data into the apps from external sources.

Note: If you're using the Day One URL scheme in Terminal (or your preferred CLI app), you'll need to type "open" followed by the URL scheme. Also, if you have both Day One Classic and Day One 2.0 installed on the same device, the URL Scheme will route to Day One 2.0.

**Navigation:**  
Open Day One: [dayone://](dayone://)  
Open Timeline: <dayone://entries>  
Open Calendar: <dayone://calendar>  
Open Starred: <dayone://starred>  
Preferences: <dayone://preferences>

**Entry Create:**  
Create Entry with Text: [dayone://post?entry=Hello Self](dayone://post?entry=Hello%20Self)  
Create Entry with Tags: [dayone://post?entry=Hello Self&tags=My Tag, Test](dayone://post?entry=Hello%20Self&tags=My%20Tag,%20Test)  
Create Entry in Journal: [dayone://post?entry=Hello Self&journal=Day One](dayone://post?entry=Hello%20Self&journal=Day%20One)  
Create Entry with Clipboard Image: [dayone://post?entry=Hello Self&imageClipboard=1](dayone://post?entry=Hello%20Self&imageClipboard=1)

**Entry Edit:**  
Edit Entry: [dayone://edit?entryId=[UUID]](dayone://edit?entryId=%5BUUID%5D) (Don't include brackets.)

## On This Day

On This Day = dayone://thisday

## Siri Shortcuts

Settings > Siri Shortcuts = dayone://siri

See Also: [Day One Tools](http://intercom.help/dayone/day-one-2-0/day-one-tools)

___

# Article #DayOne
