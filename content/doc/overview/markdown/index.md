---
authors: [Georg Makowski]
title: Markdown Layout
description: One-page Markdown overview
subtitle: false
date: 2022-05-12T22:30:17+02:00 
menu:
  doc:
    name: Markdown Layout
    parent: tldr
    pre: edit
resources:
- src: Markdown.svg
  name: featured
  params:
    alt: Markdown logo
    background: light
    width: tiny
    type: symbol
    padding: one
- src: erda-estremera-eMX1aIAp9Nw-unsplash.jpg
  name: bigsplash
  params: 
    caption: This caption and the attribution are not available for directly included images. We need to provide the additional information in associated resource parameters (&rightarrow; [Resources](https://perplex.desider.at/doc/intro/workflow/resources)).
    alt: Big splash of water
- src: mulyadi-JJMoAiVl9jA-unsplash.jpg
  name: smallsplash
  params:
    caption: Caption (only from a resource)
    alt: Splash of water
categories: [Overview, Markdown]
tags: [Block, Inline]
weight: 6
---

Samples of Hugo’s extended CommonMark syntax to give a quick impression of the default layout.
{.p-first}
<!--more-->

This page shows the default style the theme applies to Markdown elements. Image captions and notes are not a part of this default set.

## Headings

The following HTML elements `<h1>`—`<h6>` represent the title, three levels of section headings, and two levels of paragraph headings.

Because the templates generate the title section from frontmatter meta-data the Markdown **should not** contain a title. As usual, the theme processes frontmatter parameters for the [title section](https://perplex.desider.at/doc/page/title).
{.box-info}

---

# Title

{{% pangram 3 %}}
{.placeholder data-pagefind-ignore="all"}

---

## Section
{{% pangram 3 %}}
{.placeholder data-pagefind-ignore="all"}

### Subsection
{{% pangram 3 %}}
{.placeholder data-pagefind-ignore="all"}

#### Sub-subsection
{{% pangram 3 %}}
{.placeholder data-pagefind-ignore="all"}

##### Paragraph
{{% pangram 3 %}}
{.placeholder data-pagefind-ignore="all"}

###### Small Paragraph
{{% pangram 3 %}}
{.placeholder data-pagefind-ignore="all"}

## Images

Since version 0.108.0 Hugo allows distinguishing stand-alone and embedded images.

### Stand-alone

![A big splash of water](bigsplash)

### Embedded

![A smaller splash of water](smallsplash) {{% pangram 6 %}}
{.placeholder data-pagefind-ignore="all"}

{{% pangram 6 %}}
{.placeholder data-pagefind-ignore="all"}

## Link

- This is an internal [example link](#images).

- This is an external [example link](https://example.com "example.com").

## Blockquotes

The blockquote element contains content from another source.

### Without attribution

> {{% pangram 5 %}}
> {.placeholder data-pagefind-ignore="all"}
>
> **Note** that you can use _Markdown syntax_ within a blockquote.

### With attribution and footnote

> Don't communicate by sharing memory, share memory by communicating.
> — _Rob Pike_[^1]

[^1]: The above quote is excerpted from Rob Pike's [talk](https://www.youtube.com/watch?v=PAAkCSZUG1c) during Gopherfest, on November 18, 2015.

## Tables

Tables aren't part of CommonMark, but Hugo supports their syntax as an extension by default.

### Centered table columns

| Name  | Age |
|:-----:|:---:|
|  Bob  | 27  |
| Alice | 23  |

### Inline Markdown within tables

| Inline    | Markdown |        In         |  Table |
|:----------|:--------:|:-----------------:|-------:|
| _italics_ | **bold** | ~~strikethrough~~ | `code` |

## Code Blocks

### With backticks (code fences)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Example HTML5 Document</title>
</head>
<body>
  <p>Test</p>
</body>
</html>
```

### Code block indented with four spaces

    <!DOCTYPE html>
    <html lang="en">
    <head>
      <meta charset="UTF-8">
      <title>Example HTML5 Document</title>
    </head>
    <body>
      <p>Test</p>
    </body>
    </html>

### Code block with Hugo's internal highlight shortcode

{{< highlight html >}}
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Example HTML5 Document</title>
</head>
<body>
  <p>Test</p>
</body>
</html>
{{< /highlight >}}

## List Types

### Ordered list

1. First item
2. Second item
3. Third item

### Unordered list

- List item
- Another item
- And another item

### Nested unordered and ordered list

- Item 1

  1. First sub-item of the first item
  
  2. Second sub-item of the first item

- Item 2

  1. First sub-item of the second item

  2. Second sub-item of the second item
  
### Definition list

The definition list is also an extension for Goldmark supported by Hugo.

First term
: Description of the first term

Second term
: Description of the second term

## Missing Markdown elements

Some inline HTML tags have no corresponding syntax in Goldmark. We can either enable raw HTML in Markdown or use Hugo to generate them.

### Additional inline elements

sub & sup
: H{_2}O, X{^n} + Y{^n} = Z{^n}

kbd
: Press {~CTRL} + {~ALT} + {~Delete} to end the session.

mark
: Most {!salamanders} are nocturnal, and hunt for insects, worms, and other small creatures.

cite
: We can reference a {=book}.
{.dl-loose .inline}

{{< mnote >}}
This theme supports safe Markdown &rightarrow; `unsafe: false`. The elements here are generated by `replaceRE …` of [replacement codes](https://perplex.desider.at/doc/enhancing/replace).
{{< /mnote >}}

### Inline with special attributes

The link element is tweaked to produce the following two tags when their name is provided as link target and combined with a title attribute:

abbr
: The link `[HTML](abbr "HyperText Markup Language")` generates [HTML](abbr "HyperText Markup Language")

dfn
: The link `[Replacement codes](dfn "replacement codes")` generates the definition tag:
  
  [Replacement codes](dfn "replacement codes") are defined by curly braces and a marker directly after the first brace.
{.dl-loose .inline}

{{< mnote >}}
The render-link hook recognizes and processes these special links.
{{< /mnote >}}
