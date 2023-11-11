[![Day One](https://applets.imgix.net/https%3A%2F%2Fassets.ifttt.com%2Fimages%2Fchannels%2F1969755261%2Ficons%2Fmonochrome_large.png?w=240&h=240&auto=compress&s=d7a38e5505264de46d3f1a13b1f7ea48 "Day One")Day One](https://ifttt.com/day_one "Day One")

# Create Journal Entry

This Action will create a new Journal entry in the Journal you specify.

.unified-header, .service-header { background-color: #44C0FF; }

## About This Action

Triggers, queries, and actions are the building blocks of Applets. Triggers tell an Applet to start, queries ask a question, and actions are its end result.

### Developer Info

Description

This Action will create a new Journal entry in the Journal you specify.

API endpoint slug

day\_one.create\_journal\_entry

Filter code method

DayOne.createJournalEntry.skip(string?: reason)

Runtime method

runAction("day\_one.create\_journal\_entry", {})

## Action Fields

### Journal ID Dropdown List

Label

Which Journal?

Helper text

Select a specific Journal. New Journals must be created in the Day One app.

Slug

journal\_id

Required

true

Can have default value

false

### Body Text Input > Long Text

Label

Body

Helper text

Add plain text and Markdown, HTML will be stripped.

Slug

body

Required

false

Can have default value

true

Filter code method

DayOne.createJournalEntry.setBody(string: body)

### Tags Text Input > Tags

Label

Tags

Helper text

Comma separated, spaces are ok.

Slug

tags

Required

false

Can have default value

true

Filter code method

DayOne.createJournalEntry.setTags(string: tags)

### Latitude Text Input > Short Text

Label

Latitude

Helper text

The latitude of the entry location.

Slug

latitude

Required

false

Can have default value

true

Filter code method

DayOne.createJournalEntry.setLatitude(string: latitude)

### Longitude Text Input > Short Text

Label

Longitude

Helper text

The longitude of the entry location.

Slug

longitude

Required

false

Can have default value

true

Filter code method

DayOne.createJournalEntry.setLongitude(string: longitude)

### Placename Text Input > Short Text

Label

Place Name

Helper text

The name of the entry location.

Slug

placename

Required

false

Can have default value

true

Filter code method

DayOne.createJournalEntry.setPlacename(string: placename)

### Image Text Input > Photo

Label

Image URL

Slug

image

Required

false

Can have default value

true

Filter code method

DayOne.createJournalEntry.setImage(string: image)
