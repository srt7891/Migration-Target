# Wiki Style Guide

[[_TOC_]]

## Document Layout

Most pages will use variation of the following layout:

```markdown
# <h1 style=”color:#fff;background-color:#2f5597;border-radius:5px;padding:5px;”>Card Title</h1>

[[_TOC_]]

---

## <h2 style="color:rgb(0,120,215)">Overview</h2>

Short introduction.

---

## <h2 style="color:rgb(0,120,215)">Section Header 2</h2>

### <h3>Sub Section 3</h3>

Section content....

- [ ] Item 1
- [ ] Item 2
- [ ] Item 3

or 

- [ ] Item 1

Information about Item 1 

- [ ] Item 2

Information about Item 2  

- [ ] Item 3
 
Information about Item 3  

---

## <h2 style="color:rgb(0,120,215)">Section Header 2</h2>

### <h3>Sub Section 3</h3>

Section content...

#### <h4>Sub Section 4</h4>

Section content...

---
## <h2 style="color:rgb(0,120,215)">Resources</h2>

Section content... (Optional)

-	[Link Name](URL)
-	[Link Name](URL)
-	[Link Name](URL)

---
## <h2 style="color:rgb(0,120,215)">Legend</h2>

-	**Core Minimum** – practices that, if not present, require the project to be stopped until such time that the practices can be enacted.
-	**Good Practices** – practices that should be present on a project, but would not require project stoppage if absent, and should have plans for implementation.
-	**Risks** – practices that if present should be included on the risk list with an active mitigation plan.
```

### Document Design Details

1. Card Title: The card title/page topic should be a level one heading using an h1 html tag.
1. Short introduction: 1-3 sentences providing a high-level overview of the topic.
1. [TOC]: page table of contents
1. Section Header: Each section will start with an h2 html tag.  Section can include additional sections using h3 and h4 tags.
1. The preferred list is to use a checkbox.  If a list of resources an unordered list can also be used.
1. The top of each page has the big blue banner describing what the page pertains to
1. The overview section goes afterwards with ‘Overview’ in blue text
1. TOC comes after the overview Section
1. A long horizontal line to divide each top level section of the page.
1. Use markdown Header format for anything that needs to be in the TOC
1. The styling of aforementioned headers should be that of one level lower (created via html header tags)
1. Top level sections are also encased in the big blue banner
1. The Resources and Legend sections are the one exception to the above rule and is encased in a gray banner


## Headings

Start a line with a hash character # to set a heading. Organize your remarks with subheadings by starting a line with additional hash characters, for example ####. Up to six levels of headings are supported.

### Add spacing to headings

Prefer spacing after # and newlines before and after

```markdown

...text before

# Heading 1

Text after ...

```

## Paragraphs and line breaks

Make your text easier to read by breaking it up with paragraphs or line breaks.

In a Markdown file, enter two spaces before the line break to begin a new paragraph, or enter two consecutive line breaks to begin a new paragraph.

## Horizontal rules

To add a horizontal rule, add a line that's a series of dashes ---. The line above the line containing the --- must be blank.

## List and checkbox

Recommend to use checkboxes when possible.

Organize related items with lists. You can add ordered lists with numbers, or unordered lists with just bullets.

Ordered lists start with a number followed by a period for each list item. Unordered lists start with a -. Begin each list item on a new line. In a Markdown file or widget, enter two spaces prior to the line break to begin a new paragraph, or enter two line breaks consecutively to begin a new paragraph.

## Links

In Markdown files and widgets, you can set text hyperlinks for your URL using the standard Markdown link syntax:

[Link Text](Link URL)

When linking to another Markdown page in the same Git or TFVC repository, the link target can be a relative path or an absolute path in the repository.

Supported links for Markdown widget:

- URL: [text to display](http://address.com)

Supported links for Wiki:

- Absolute path of Wiki pages: [text to display](/Getting-Started/Style-Guide)
- URL: [text to display](http://address.com)

## Images

Use the following syntax to add an image:

```markdown
![Text](URL)
```

The text in the brackets describes the image being linked and the URL points to the image location.

## Tables

Organize structured data with tables. Tables are especially useful for describing function parameters, object methods, and other data that has a clear name to description mapping. You can format tables in pull requests, wiki, and Markdown files such as README files and Markdown widgets.

- Place each table row on its own line  
- Separate table cells using the pipe character |
- The first two lines of a table set the column headers and the alignment of elements in the table
- Use colons when dividing the header and body of tables to specify column alignment (left, center, right)
- To start a new line, use the HTML break tag (Works within a Wiki but not elsewhere)
- Make sure to end each row with a CR or LF.
- A blank space is required before and after work item or pull request (PR) mentions inside a table cell.

---
