# Removing-html-markup-from-text

## Removing HTML Markup from Text

When parsing HTML content, it’s often necessary to remove markup entirely. The handler in Listing 34-1 removes all HTML tags from the text provided, returning only the remaining text—the contents of the tags.

**APPLESCRIPT**

[Open in Script Editor](applescript://com.apple.scripteditor?action=new&name=Remove%20HTML%20Markup%20From%20Text&script=on%20removeMarkupFromText%28theText%29%0D%20%20%20%20set%20tagDetected%20to%20false%0D%20%20%20%20set%20theCleanText%20to%20%22%22%0D%20%20%20%20repeat%20with%20a%20from%201%20to%20length%20of%20theText%0D%20%20%20%20%20%20%20%20set%20theCurrentCharacter%20to%20character%20a%20of%20theText%0D%20%20%20%20%20%20%20%20if%20theCurrentCharacter%20is%20%22%3C%22%20then%0D%20%20%20%20%20%20%20%20%20%20%20%20set%20tagDetected%20to%20true%0D%20%20%20%20%20%20%20%20else%20if%20theCurrentCharacter%20is%20%22%3E%22%20then%0D%20%20%20%20%20%20%20%20%20%20%20%20set%20tagDetected%20to%20false%0D%20%20%20%20%20%20%20%20else%20if%20tagDetected%20is%20false%20then%0D%20%20%20%20%20%20%20%20%20%20%20%20set%20theCleanText%20to%20theCleanText%20%26%20theCurrentCharacter%20as%20string%0D%20%20%20%20%20%20%20%20end%20if%0D%20%20%20%20end%20repeat%0D%20%20%20%20return%20theCleanText%0Dend%20removeMarkupFromText%0D)

**Listing 34-1**AppleScript: Handler that removes HTML markup from text

1. `on removeMarkupFromText(theText)`
2. `set tagDetected to false`
3. `set theCleanText to ""`
4. `repeat with a from 1 to length of theText`
5. `set theCurrentCharacter to character a of theText`
6. `if theCurrentCharacter is "<" then`
7. `set tagDetected to true`
8. `else if theCurrentCharacter is ">" then`
9. `set tagDetected to false`
10. `else if tagDetected is false then`
11. `set theCleanText to theCleanText & theCurrentCharacter as string`
12. `end if`
13. `end repeat`
14. `return theCleanText`
15. `end removeMarkupFromText`

Listing 34-2 shows how to call the handler in Listing 34-1.

**APPLESCRIPT**

[Open in Script Editor](applescript://com.apple.scripteditor?action=new&name=Call%20Handler%20to%20Remove%20HTML%20Markup%20from%20Text&script=set%20theText%20to%20%22%3Ca%20href%3D%5C%22http%3A%2F%2Fwww.apple.com%2Fmac%5C%22%3EThis%20is%20a%20%3CB%3Egreat%3C%2FB%3E%20time%20to%20own%20a%20Mac!%3C%2Fa%3E%22%0AremoveMarkupFromText%28theText%29)

**Listing 34-2**AppleScript: Calling a handler to remove HTML markup from text

1. `set theText to "<a href=\"http://www.apple.com/mac\">This is a <B>great</B> time to own a Mac!</a>"`
2. `removeMarkupFromText(theText)`
3. `--> Result: "This is a great time to own a Mac!"`
