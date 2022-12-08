![[56CA857B-3CE6-4900-9CCE-D46C0D1393D9.jpeg]]![[5BA05065-7C87-40A7-B757-28CCE47C1831.jpeg]]![[F593BC77-272B-4C6D-9E4F-07E6C5E967A9.jpeg]]![[9067CE63-5FD2-4D6C-A053-57786D816968.jpeg]]![[C8DAA904-720D-4551-8E3E-25F8F9B8F600.jpeg]]![[C7713679-7600-4533-8AA3-A909B1C5D244.jpeg]]


# Create Journal Entry

This Action will create a new Journal entry in the Journal you specify.


### About this action

Triggers, queries, and actions are the building blocks of Applets. Triggers tell an Applet to start, queries ask a question, and actions are its end result.

#### Developer info

Description

This Action will create a new Journal entry in the Journal you specify.

API endpoint slug 

`day\_one.create\_journal\_entry`

Filter code method

`DayOne.createJournalEntry.skip(string?: reason)`

Runtime method

`runAction("day\_one.create\_journal\_entry", {})`

### Action fields

#### Journal ID Dropdown list

Label

Which Journal?

Helper text

Select a specific Journal. New Journals must be created in the Day One app.

Slug

`journal\_id`

Required

`true 

Can have default value

`false`'

#### Body Text input > Long text

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

`DayOne.createJournalEntry.setBody(string: body)`

#### Tags Text input > Tags

Label

Tags

Helper text

Comma separated, spaces are ok.

Slug

tags

Required

`false`

Can have default value

`true`

Filter code method

`DayOne.createJournalEntry.setTags(string: tags)`

#### Latitude Text input > Short text

Label

Latitude

Helper text

The latitude of the entry location.

Slug

latitude

Required

`false`

Can have default value

`true`

Filter code method

`DayOne.createJournalEntry.setLatitude(string: latitude)`

#### Longitude Text input > Short text

Label

Longitude

Helper text

The longitude of the entry location.

Slug

longitude

Required

`false`

Can have default value

`true`

Filter code method

`DayOne.createJournalEntry.setLongitude(string: longitude)`

#### Placename Text input > Short text

Label

Place Name

Helper text

The name of the entry location.

Slug

placename

Required

`false`

Can have default value

`true`

Filter code method

`DayOne.createJournalEntry.setPlacename(string: placename)`

#### Image Text input > Photo

Label

Image URL

Slug

image

Required

`false`

Can have default value

`true`

Filter code method

`DayOne.createJournalEntry.setImage(string: image)`

---

#ifttt 