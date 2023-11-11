# Bare Bones Software | BBEdit Pattern Playgrounds

---

The "Pattern Playground" window provides an interactive interface for experimenting with the behavior of Grep patterns (regular expressions). This makes the process of creating complicated patterns much less trial-and-error, since you can see exactly what will match, and how, before committing to any irreversible actions.

Choose "Pattern Playground" from the Search menu to open a shared window, or make a new pattern tester any time by choosing File => New => Pattern Playground. (You can have multiple pattern playground windows open.)

![Pattern Playground window image](http://www.barebones.com/images/bbedit/PatternPlayground.png)

Here's a brief description of how the window works:

- The "Search pattern" section is where you do most of the work. You can choose an existing pattern from the Grep patterns menu (same one as provided in the Find window and elsewhere), or start typing from scratch. The pattern is checked live as you type. If the pattern is valid, it will search whatever text is displayed in the "Contents of" section (see below).
    
- Next to the Grep patterns menu is a history menu, which provides a local (to the window) history of patterns in which you have successfully used the "Next" button. You can use this to explore different iterations of a working pattern.
    
- To the right of the history menu is the Grep Cheat Sheet, which provides quick access to common regular expression idioms.
    
- The "Search results" and "Next" button are available when a pattern matches anything in the "Contents of" section. The results line will show you how many matches there are for the specified pattern. The "Next" button will highlight the next match of the entire pattern, *or* if a capture group is selected (see below), the next match of the selected capture group.
    
- The "Use for Find" button will copy the current search and replace patterns to the global Find state, thus setting them up in the Find and Multi-File Search windows and turning on Grep.
    
- The "Capture groups" list will show you all of the defined capture groups ("subpatterns") in the Grep pattern, including the implicit "`\0`" capture group which represents the entire match. (If your pattern has positional assertions, "`\0`" *may* not represent the entirety of the pattern match! Who knew?)

    The "`#`" column always shows the capture group number. If the pattern contains any named capture groups (e.g. `(?P<foobar>)`), the "Name" column will display the name of the capture group (e.g. `foobar`).

    The list is populated for any valid pattern. If you perform a search, however, more data gets filled in. The "Text" column will display the text which is actually contained by the capture group; so by selecting different groups, you can see how the pattern internally matches your text, and then adjust the pattern as desired.

- The "Replace Pattern" field can be used to experiment with substitions. As you edit, the "Replacement Text" field shows the results of applying the replacement pattern to the current match.
    
- The "Contents of" section shows a popup menu which lists all open documents, in alphabetical order. When you choose a document, the text area will fill with a copy of that document's contents. (The text area is not editable, but changes to the document in its editing window will reflect in the text area.)

    The first item on the document menu is "Scratch Space". This makes the text area at the bottom editable (it isn't normally), so you can paste in text from somewhere else for testing, and make small edits. You should not rely on this as a general purpose document editor.

    When you have a matching search pattern entered, the portion of the pattern (or the selected capture group) that matches the text will be highlighted using the system's standard color for highlighting search matches. You can use the "Next" button to proceed to the next match.

Additional notes and behaviors:

- The pattern tester is wired into the Search menu mechanics, so that "Find Next" or its keyboard equivalent do the same thing as the "Next" button.
    
- When a pattern tester window is active, the "Use Selection for Find" command changes to "Use Pattern for Find". This allows use of the appropriate keyboard equivalent for the "Use for Find" button.
    
- The Capture Groups and Replacement Pattern sections in Pattern Playground windows are collapsible.
    
- If you make edits to a pattern, and then close the Pattern Playground window without either saving it or clicking "Use for Find", BBEdit will prompt you, and give you a chance to save the pattern.

---

[Back to Technical Notes](http://www.barebones.com/support/bbedit/technotes.html)
