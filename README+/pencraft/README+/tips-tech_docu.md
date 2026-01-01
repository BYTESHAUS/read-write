# Technical documentation&nbsp;&nbsp;&mdash;&nbsp;&nbsp;Tips

## Content

### Split the flow.

Long-running sentences, paragraphs, and chapters are first-degree misdemeanors.

Does such a commonplace deserve a reminder? Yes, it still has to be met everywhere and became more poignant in the era of smartphones.

### Emphasizing

#### Quotes

* Except for citations use quotation marks for metaphors while _italic_ to introduce terms. Example:
> To compare _multitasking_ vs. _parallelism_ imagine the CPU being a "kitchen" where a quick cook vs. an orderly brigade can prepare the same courses.

#### References

Where it matters, distinguish most internal and external links (Here <sup>🔗</sup> attaches to the latter).

## Navigation 

### Totals

* Numbering totals will keep readers and editors focused.\
Page 3 of **7**, Appendix 1/**3**, Chapter 11 of **20**.

## Characters and symbols 

### Replacements

Many typography symbols may appear in text when markup is broken. To exclude doubts it's better to insert their symbolic versions, escape tags, or codes when possible:

* <mark>“”</mark>, <mark>«»</mark>, or <tt>\&quot;</tt> instead of <mark>""</mark>,
* <mark>⟨ ⟩</mark> or <tt>\&lt; \&gt;</tt> instead of angle brackets <mark><></mark>,
* <tt>\&amp;</tt> for **&**,
* <tt>\&mdash;</tt> for long dash\
[and so on](https://www.w3schools.com/html/html_entities.asp).

Using/defining shortcuts for them in your editors will be fastly rewarded. (Like <tt>Ctrl+Shift-Space</tt> for non-breaking space in Microsoft Word)

### Helpers

Replacements can be coded and ensure the text layout: <tt>\&nbsp</tt> for non-breakable space, <tt>\&#8209</tt>; for non-breaking hyphen, and so on.

### Pictograms / emojis

Small images are smart helpers to annotate, navigate, and focus unless heavily overused. They may apply to everything - text, solution items (folders and filenames), and even program output (UTF-8 glyphs to rescue).

A team should limit them to a subset<sup>🍋</sup>, define the exact meaning of most, and put some on a blacklist (for ambiguity or cultural issues).

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<sup>🍋</sup> <sub>By default markdown emojis, supported by GitHub &mdash; see this [cheatsheet](https://github.com/ikatyang/emoji-cheat-sheet/blob/master/README.md)<sup>🔗</sup>.</sub>

#### Side effects

Special characters and escape tags spoil the familiar "plain" search but as a side-effect create a sort of bookmarking/tagging.

Ensure that your spell- and grammarcheckers recognize replacements.

## Checklist

- [ ] Make character replacements (see above)
// including non-breakable spaces and hyphens for spots where wrapping will look bad
- [ ]  Run spell/grammar check.
- [ ] Prove internal links
- [ ] Prove external links for existence
// much resources degrade with time to _404_. 
- [ ] check for "hidden" typos as double spaces
- [ ] SynonymIZE: repeated terms and buzzwords.
- [ ] ...

## Wrap up

**Last but not least** - stamp with an ending sign or note, even if there's a "conclusion" section (there might be appendices missing).

Ensure yourself and your readers that it was the intentional ending. Use custom note (like below), typographical ["tombstone"](https://en.wikipedia.org/wiki/Tombstone_(typography))<sup><b>w</b></sup>, or exquisite [Q.E.D.](https://en.wikipedia.org/wiki/Q.E.D.)<sup><b>w</b></sup>

🔚 🌘 2024-2026 ...TO BE CONTINUED ✏️...
