## Encoding and Decoding Text

A standard practice when creating URL's is to encode spaces and special characters (high-level ASCII) to hexadecimal equivalents. For example, spaces in URL's are routinely converted to `%20`. The process of encoding and decoding URLs and other text in this manner can be accomplished through scripting.

### Encoding Characters

The handler in Listing 32-1 encodes a single character.

**APPLESCRIPT**

[Open in Script Editor](applescript://com.apple.scripteditor?action=new&script=on%20encodeCharacter%28theCharacter%29%0A%20%20%20%20set%20theASCIINumber%20to%20%28the%20ASCII%20number%20theCharacter%29%0A%20%20%20%20set%20theHexList%20to%20%7B%220%22%2C%20%221%22%2C%20%222%22%2C%20%223%22%2C%20%224%22%2C%20%225%22%2C%20%226%22%2C%20%227%22%2C%20%228%22%2C%20%229%22%2C%20%22A%22%2C%20%22B%22%2C%20%22C%22%2C%20%22D%22%2C%20%22E%22%2C%20%22F%22%7D%0A%20%20%20%20set%20theFirstItem%20to%20item%20%28%28theASCIINumber%20div%2016%29%20%2B%201%29%20of%20theHexList%0A%20%20%20%20set%20theSecondItem%20to%20item%20%28%28theASCIINumber%20mod%2016%29%20%2B%201%29%20of%20theHexList%0A%20%20%20%20return%20%28%22%25%22%20%26%20theFirstItem%20%26%20theSecondItem%29%20as%20string%0Aend%20encodeCharacter)

**Listing 32-1**AppleScript: Handler that URL encodes a character

1. `on encodeCharacter(theCharacter)`
2. `set theASCIINumber to (the ASCII number theCharacter)`
3. `set theHexList to {"0", "1", "2", "3", "4", "5", "6", "7", "8", "9", "A", "B", "C", "D", "E", "F"}`
4. `set theFirstItem to item ((theASCIINumber div 16) + 1) of theHexList`
5. `set theSecondItem to item ((theASCIINumber mod 16) + 1) of theHexList`
6. `return ("%" & theFirstItem & theSecondItem) as string`
7. `end encodeCharacter`

Listing 32-2 shows how to call the handler in Listing 32-1.

**APPLESCRIPT**

[Open in Script Editor](applescript://com.apple.scripteditor?action=new&script=encodeCharacter%28%22%24%22%29)

**Listing 32-2**AppleScript: Calling a handler to URL encode a character

1. `encodeCharacter("$")`
2. `--> Result: "%24"`

### Encoding Text

The handler in Listing 32-3 encodes an entire string. Provide a string and indicate whether to encode two levels of special characters. The first level includes commonly encoded special characters, such as `$`, `%`, and `*`. The second level includes extended special characters that aren’t typically encoded—`.`, `-`, `_`, and `:`. High-level ASCII characters, such as copyright symbols, trademark symbols, and spaces, are always encoded.

**APPLESCRIPT**

[Open in Script Editor](applescript://com.apple.scripteditor?action=new&script=on%20encodeText%28theText%2C%20encodeCommonSpecialCharacters%2C%20encodeExtendedSpecialCharacters%29%0A%20%20%20%20set%20theStandardCharacters%20to%20%22abcdefghijklmnopqrstuvwxyz0123456789%22%0A%20%20%20%20set%20theCommonSpecialCharacterList%20to%20%22%24%2B!%27%2F%3F%3B%26%40%3D%23%25%3E%3C%7B%7D%5C%22~%60%5E%5C%5C%7C*%22%0A%20%20%20%20set%20theExtendedSpecialCharacterList%20to%20%22.-_%3A%22%0A%20%20%20%20set%20theAcceptableCharacters%20to%20theStandardCharacters%0A%20%20%20%20if%20encodeCommonSpecialCharacters%20is%20false%20then%20set%20theAcceptableCharacters%20to%20theAcceptableCharacters%20%26%20theCommonSpecialCharacterList%0A%20%20%20%20if%20encodeExtendedSpecialCharacters%20is%20false%20then%20set%20theAcceptableCharacters%20to%20theAcceptableCharacters%20%26%20theExtendedSpecialCharacterList%0A%20%20%20%20set%20theEncodedText%20to%20%22%22%0A%20%20%20%20repeat%20with%20theCurrentCharacter%20in%20theText%0A%20%20%20%20%20%20%20%20if%20theCurrentCharacter%20is%20in%20theAcceptableCharacters%20then%0A%20%20%20%20%20%20%20%20%20%20%20%20set%20theEncodedText%20to%20%28theEncodedText%20%26%20theCurrentCharacter%29%0A%20%20%20%20%20%20%20%20else%0A%20%20%20%20%20%20%20%20%20%20%20%20set%20theEncodedText%20to%20%28theEncodedText%20%26%20encodeCharacter%28theCurrentCharacter%29%29%20as%20string%0A%20%20%20%20%20%20%20%20end%20if%0A%20%20%20%20end%20repeat%0A%20%20%20%20return%20theEncodedText%0Aend%20encodeText)

**Listing 32-3**AppleScript: Handler that URL encodes text

1. `on encodeText(theText, encodeCommonSpecialCharacters, encodeExtendedSpecialCharacters)`
2. `set theStandardCharacters to "abcdefghijklmnopqrstuvwxyz0123456789"`
3. ``set theCommonSpecialCharacterList to "$+!'/?;&@=#%><{}\"~`^\\|*"``
4. `set theExtendedSpecialCharacterList to ".-_:"`
5. `set theAcceptableCharacters to theStandardCharacters`
6. `if encodeCommonSpecialCharacters is false then set theAcceptableCharacters to theAcceptableCharacters & theCommonSpecialCharacterList`
7. `if encodeExtendedSpecialCharacters is false then set theAcceptableCharacters to theAcceptableCharacters & theExtendedSpecialCharacterList`
8. `set theEncodedText to ""`
9. `repeat with theCurrentCharacter in theText`
10. `if theCurrentCharacter is in theAcceptableCharacters then`
11. `set theEncodedText to (theEncodedText & theCurrentCharacter)`
12. `else`
13. `set theEncodedText to (theEncodedText & encodeCharacter(theCurrentCharacter)) as string`
14. `end if`
15. `end repeat`
16. `return theEncodedText`
17. `end encodeText`

Note

This handler calls the `encodeCharacter()` handler. See [Listing 32-1](https://developer.apple.com/library/archive/documentation/LanguagesUtilities/Conceptual/MacAutomationScriptingGuide/EncodeandDecodeText.html#//apple_ref/doc/uid/TP40016239-CH51-SW1#//apple_ref/doc/uid/TP40016239-CH51-SW5).

Listing 32-4 shows how to call the handler in Listing 32-3 to encode only high-level ASCII characters.

**APPLESCRIPT**

[Open in Script Editor](applescript://com.apple.scripteditor?action=new&script=encodeText%28%22*smith-wilson%C2%A9%20report_23.txt%22%2C%20false%2C%20false%29)

**Listing 32-4**AppleScript: Calling a handler to URL encode high-level ASCII characters in text

1. `encodeText("*smith-wilson© report_23.txt", false, false)`
2. `--> Result: "*smith-wilson%A9%20report_23.txt"`

Listing 32-5 shows how to call the handler in Listing 32-3 to encode high-level ASCII characters and all special characters.

**APPLESCRIPT**

[Open in Script Editor](applescript://com.apple.scripteditor?action=new&script=encodeText%28%22*smith-wilson%C2%A9%20report_23.txt%22%2C%20true%2C%20true%29)

**Listing 32-5**AppleScript: Calling a handler to URL encode high- and low-level ASCII characters in text

1. `encodeText("*smith-wilson© report_23.txt", true, true)`
2. `--> Result: "%2Asmith%2Dwilson%A9%20report%5F23%2Etxt"`

Listing 32-6 shows how to call the handler in Listing 32-3 to encode high-level ASCII characters and special characters, excluding periods, hyphens, underscores, and colons.

**APPLESCRIPT**

[Open in Script Editor](applescript://com.apple.scripteditor?action=new&script=encodeText%28%22annual%20smith-wilson_report.txt%22%2C%20true%2C%20false%29)

**Listing 32-6**AppleScript: Calling a handler to URL encode high- and low-level ASCII characters in text with certain exclusions

1. `encodeText("annual smith-wilson_report.txt", true, false)`
2. `--> Result: "annual%20smith-wilson_report.txt"`

Note

When you use AppleScriptObjC, you can use methods of the `NSString` class to encode text. The handler in Listing 32-7 demonstrates how to do this.

**APPLESCRIPT**

[Open in Script Editor](applescript://com.apple.scripteditor?action=new&script=on%20encodeText%28theText%29%0A%20%20%20%20set%20theString%20to%20stringWithString_%28theText%29%20of%20NSString%20of%20current%20application%0A%20%20%20%20set%20theEncoding%20to%20NSUTF8StringEncoding%20of%20current%20application%0A%20%20%20%20set%20theAdjustedString%20to%20stringByAddingPercentEscapesUsingEncoding_%28theEncoding%29%20of%20theString%0A%20%20%20%20return%20%28theAdjustedString%20as%20string%29%0Aend%20encodeText)

**Listing 32-7**AppleScriptObjC: Handler that URL encodes text

1. `on encodeText(theText)`
2. `set theString to stringWithString_(theText) of NSString of current application`
3. `set theEncoding to NSUTF8StringEncoding of current application`
4. `set theAdjustedString to stringByAddingPercentEscapesUsingEncoding_(theEncoding) of theString`
5. `return (theAdjustedString as string)`
6. `end encodeText`

### Decoding Text

The handler in Listing 32-8 decodes an encoded character hex string.

**APPLESCRIPT**

[Open in Script Editor](applescript://com.apple.scripteditor?action=new&script=on%20decodeCharacterHexString%28theCharacters%29%0A%20%20%20%20copy%20theCharacters%20to%20%7BtheIdentifyingCharacter%2C%20theMultiplierCharacter%2C%20theRemainderCharacter%7D%0A%20%20%20%20set%20theHexList%20to%20%22123456789ABCDEF%22%0A%20%20%20%20if%20theMultiplierCharacter%20is%20in%20%22ABCDEF%22%20then%0A%20%20%20%20%20%20%20%20set%20theMultiplierAmount%20to%20offset%20of%20theMultiplierCharacter%20in%20theHexList%0A%20%20%20%20else%0A%20%20%20%20%20%20%20%20set%20theMultiplierAmount%20to%20theMultiplierCharacter%20as%20integer%0A%20%20%20%20end%20if%0A%20%20%20%20if%20theRemainderCharacter%20is%20in%20%22ABCDEF%22%20then%0A%20%20%20%20%20%20%20%20set%20theRemainderAmount%20to%20offset%20of%20theRemainderCharacter%20in%20theHexList%0A%20%20%20%20else%0A%20%20%20%20%20%20%20%20set%20theRemainderAmount%20to%20theRemainderCharacter%20as%20integer%0A%20%20%20%20end%20if%0A%20%20%20%20set%20theASCIINumber%20to%20%28theMultiplierAmount%20*%2016%29%20%2B%20theRemainderAmount%0A%20%20%20%20return%20%28ASCII%20character%20theASCIINumber%29%0Aend%20decodeCharacterHexString)

**Listing 32-8**AppleScript: Handler that decodes an encoded character hex string

1. `on decodeCharacterHexString(theCharacters)`
2. `copy theCharacters to {theIdentifyingCharacter, theMultiplierCharacter, theRemainderCharacter}`
3. `set theHexList to "123456789ABCDEF"`
4. `if theMultiplierCharacter is in "ABCDEF" then`
5. `set theMultiplierAmount to offset of theMultiplierCharacter in theHexList`
6. `else`
7. `set theMultiplierAmount to theMultiplierCharacter as integer`
8. `end if`
9. `if theRemainderCharacter is in "ABCDEF" then`
10. `set theRemainderAmount to offset of theRemainderCharacter in theHexList`
11. `else`
12. `set theRemainderAmount to theRemainderCharacter as integer`
13. `end if`
14. `set theASCIINumber to (theMultiplierAmount * 16) + theRemainderAmount`
15. `return (ASCII character theASCIINumber)`
16. `end decodeCharacterHexString`

Listing 32-9 shows how to call the handler in Listing 32-8.

**APPLESCRIPT**

[Open in Script Editor](applescript://com.apple.scripteditor?action=new&script=decodeCharacterHexString%28%22%2524%22%29)

**Listing 32-9**AppleScript: Calling a handler to decode an encoded character hex string

1. `decodeCharacterHexString("%24")`
2. `--> Result: "$"`

The handler in Listing 32-10 decodes any encoded character hex strings in the specified text.

**APPLESCRIPT**

[Open in Script Editor](applescript://com.apple.scripteditor?action=new&script=on%20decodeText%28theText%29%0A%20%20%20%20set%20flagA%20to%20false%0A%20%20%20%20set%20flagB%20to%20false%0A%20%20%20%20set%20theTempCharacter%20to%20%22%22%0A%20%20%20%20set%20theCharacterList%20to%20%7B%7D%0A%20%20%20%20repeat%20with%20theCurrentCharacter%20in%20theText%0A%20%20%20%20%20%20%20%20set%20theCurrentCharacter%20to%20contents%20of%20theCurrentCharacter%0A%20%20%20%20%20%20%20%20if%20theCurrentCharacter%20is%20%22%25%22%20then%0A%20%20%20%20%20%20%20%20%20%20%20%20set%20flagA%20to%20true%0A%20%20%20%20%20%20%20%20else%20if%20flagA%20is%20true%20then%0A%20%20%20%20%20%20%20%20%20%20%20%20set%20theTempCharacter%20to%20theCurrentCharacter%0A%20%20%20%20%20%20%20%20%20%20%20%20set%20flagA%20to%20false%0A%20%20%20%20%20%20%20%20%20%20%20%20set%20flagB%20to%20true%0A%20%20%20%20%20%20%20%20else%20if%20flagB%20is%20true%20then%0A%20%20%20%20%20%20%20%20%20%20%20%20set%20end%20of%20theCharacterList%20to%20decodeCharacterHexString%28%28%22%25%22%20%26%20theTempCharacter%20%26%20theCurrentCharacter%29%20as%20string%29%0A%20%20%20%20%20%20%20%20%20%20%20%20set%20theTempCharacter%20to%20%22%22%0A%20%20%20%20%20%20%20%20%20%20%20%20set%20flagA%20to%20false%0A%20%20%20%20%20%20%20%20%20%20%20%20set%20flagB%20to%20false%0A%20%20%20%20%20%20%20%20else%0A%20%20%20%20%20%20%20%20%20%20%20%20set%20end%20of%20theCharacterList%20to%20theCurrentCharacter%0A%20%20%20%20%20%20%20%20end%20if%0A%20%20%20%20end%20repeat%0A%20%20%20%20return%20theCharacterList%20as%20string%0Aend%20decodeText)

**Listing 32-10**AppleScript: Handler that decodes any encoded character hex strings in specified text

1. `on decodeText(theText)`
2. `set flagA to false`
3. `set flagB to false`
4. `set theTempCharacter to ""`
5. `set theCharacterList to {}`
6. `repeat with theCurrentCharacter in theText`
7. `set theCurrentCharacter to contents of theCurrentCharacter`
8. `if theCurrentCharacter is "%" then`
9. `set flagA to true`
10. `else if flagA is true then`
11. `set theTempCharacter to theCurrentCharacter`
12. `set flagA to false`
13. `set flagB to true`
14. `else if flagB is true then`
15. `set end of theCharacterList to decodeCharacterHexString(("%" & theTempCharacter & theCurrentCharacter) as string)`
16. `set theTempCharacter to ""`
17. `set flagA to false`
18. `set flagB to false`
19. `else`
20. `set end of theCharacterList to theCurrentCharacter`
21. `end if`
22. `end repeat`
23. `return theCharacterList as string`
24. `end decodeText`

Note

This handler calls the `decodeCharacterHexString()` handler. See [Listing 32-8](https://developer.apple.com/library/archive/documentation/LanguagesUtilities/Conceptual/MacAutomationScriptingGuide/EncodeandDecodeText.html#//apple_ref/doc/uid/TP40016239-CH51-SW1#//apple_ref/doc/uid/TP40016239-CH51-SW6).

Listing 32-11 shows how to call the handler in Listing 32-10.

**APPLESCRIPT**

[Open in Script Editor](applescript://com.apple.scripteditor?action=new&script=decodeText%28%22%252Asmith%252Dwilson%25A9%2520report%255F23%252Etxt%22%29)

**Listing 32-11**AppleScript: Calling a handler to decode any encoded character hex strings in specified text

1. `decodeText("%2Asmith%2Dwilson%A9%20report%5F23%2Etxt")`
2. `--> Result: "*smith-wilson© report_23.txt"`

Note

When you use AppleScriptObjC, you can use methods of the `NSString` class to decode URL encoded text. The handler in Listing 32-12 demonstrates how to do this.

**APPLESCRIPT**

[Open in Script Editor](applescript://com.apple.scripteditor?action=new&script=on%20decodeText%28theText%29%0A%20%20%20%20set%20theString%20to%20stringWithString_%28theText%29%20of%20NSString%20of%20current%20application%0A%20%20%20%20set%20theEncoding%20to%20NSUTF8StringEncoding%20of%20current%20application%0A%20%20%20%20set%20theAdjustedString%20to%20stringByReplacingPercentEscapesUsingEncoding_%28theEncoding%29%20of%20theString%0A%20%20%20%20return%20%28theAdjustedString%20as%20string%29%0Aend%20decodeText)

**Listing 32-12**AppleScriptObjC: Handler that decodes URL encoded text

1. `on decodeText(theText)`
2. `set theString to stringWithString_(theText) of NSString of current application`
3. `set theEncoding to NSUTF8StringEncoding of current application`
4. `set theAdjustedString to stringByReplacingPercentEscapesUsingEncoding_(theEncoding) of theString`
5. `return (theAdjustedString as string)`
6. `end decodeText`
