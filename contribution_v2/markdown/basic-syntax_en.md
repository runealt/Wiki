<h2>Basic Syntax</h2>

### Overview

Nearly all Markdown applications support the basic syntax outlined in the original Markdown design document. There are minor variations and discrepancies between Markdown processors — those are noted inline wherever possible.

### Headings

To create a heading, add number signs `#` in front of a word or phrase. The number of number signs you use should correspond to the heading level. For example, to create a heading level three `<h3>`, use three number signs `e.g., ### My Header`.

| Markdown | HTML | Rendered Output |
| --- | --- | --- |
| # Heading level 1 | \<h1>Heading level 1\</h1> | <h1>Heading level 1</h1> |
| # Heading level 2 | \<h1>Heading level 2\</h1> | <h1>Heading level 2</h1> |
| # Heading level 3 | \<h1>Heading level 3\</h1> | <h1>Heading level 3</h1> |
| # Heading level 4 | \<h1>Heading level 4\</h1> | <h1>Heading level 4</h1> |
| # Heading level 5 | \<h1>Heading level 5\</h1> | <h1>Heading level 5</h1> |
| # Heading level 6 | \<h1>Heading level 6\</h1> | <h1>Heading level 6</h1> |

#### Alternate Syntax

Alternatively, on the line below the text, add any number of `==` characters for heading level 1 or `--` characters for heading level 2.

| Markdown | HTML | Rendered Output |
| --- | --- | --- |
| Heading level 1<br>=============== | \<h1>Heading level 1\</h1> | <h1>Heading level 1</h1> |
| Heading level 2<br>--------------- | \<h1>Heading level 2\</h1> | <h1>Heading level 2</h1> |

#### Heading Best Practices

Markdown applications don’t agree on how to handle a missing space between the number signs `#` and the heading name. For compatibility, always put a space between the number signs and the heading name

| ✅ Do this | ❌ Don't do this |
| --- | --- |
| # Here's a Heading | #Here's a Heading |

You should also put blank lines before and after a heading for compatibility.

| ✅ Do this | ❌ Don't do this |
| --- | --- |
| Try to put a blank line before...<br><br># Heading<br><br>...and after a heading. | Without blank lines, this might not look right.<br># Heading<br>Don't do this! |

### Paragraphs :id=basic-paragraphs

To create paragraphs, use a blank line to separate one or more lines of text.

| Markdown | HTML | Rendered Output |
| --- | --- | --- |
| I really like using Markdown.<br><br>I think I'll use it to format all of my documents from now on. | \<p>I really like using Markdown.\</p><br><br>\<p>I think I'll use it to format all of my documents from now on.\</p> | I really like using Markdown<br><br>I think I'll use it to format all of my documents from now on. |

#### Paragraph Best Practices

Unless the [paragraph is in a list](contribution_v2/markdown/basic-syntax_en?id=paragraphs), don’t indent paragraphs with spaces or tabs.

!>Note: If you need to indent paragraphs in the output, see the section on how to [indent (tab)](contribution_v2/markdown/hacks_en?id=indent-tab).

| ✅ Do this | ❌ Don't do this |
| --- | --- |
| Don't put tabs or spaces in front of your paragraphs.<br><br>Keep lines left-aligned like this. | &nbsp;&nbsp;&nbsp;&nbsp;This can result in unexpected formatting problems.<br><br>&nbsp;&nbsp;&nbsp;&nbsp;Don't add tabs or spaces in front of paragraphs. |

### Line Breaks

To create a line break or new line (), end a line with two or more spaces, and then type return.<br>

| Markdown | HTML | Rendered Output |
| --- | --- | --- |
| This is the first line.<br>And this is the second line. | \<p>This is the first line.\<br><br>And this is the second line.\</p> | This is the first line.<br>And this is the second line. |
