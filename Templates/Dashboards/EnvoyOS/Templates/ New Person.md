---
type: person
description: A basic structure for capturing the details of a person, they could be a contact or a research subject
---

# New Person

---

**Tags**:: #person <% tp.system.suggester(["This person is a Friend", "This person is a relative" , "This person is a guy from Internet"], ["#contact", ""]) %>  
**Links**:: [[Templates/Dashboards/EnvoyOS/Dashboards/ People](../Dashboards/%20People.md)

---

<% await tp.file.move("/People/" + tp.file.title) %>

## Biography / Connection

<!-- If you have a bio of the person, you can enter it here -->

## Contact Details

<!-- If the person is a contact, put their details here -->

Email::  
Mobile::  
Twitter::  
GitHub::

## Links

<!-- Any links go here, like book or article links, links to bios, wiki pages, etc. -->

## Notes

<!-- Any additional notes -->
