---
authors: [Georg Makowski]
title: Mermaid
description: Show Mermaid diagrams
subtitle: false
date: 2022-01-22T18:05:56+01:00 
weight: 730
menu:
  doc:
    name: Mermaid
    parent: plugin
    pre: account_tree
categories: [module, markdown]
tags: [mermaid, diagram]
---

Mermaid is a popular Javascript library creating SVG diagrams from text and code descriptions.
{.p-first} <!--more-->

The [Mermaid site](https://mermaid.js.org) offers Tutorials and good documentation. 

## Syntax

```md {.left-in}
‍```mermaid
%%{init: { 
    "theme": "forest",
    "fontFamily": "ibm plex sans" 
}}%%
stateDiagram-v2
    [*] --> Still
    Still --> [*]
    Still --> Moving
    Moving --> Still
    Moving --> Crash
    Crash --> [*]
‍```
```

The diagram descriptions are formatted as [code blocks](doc/basic/code) with the language identifier `mermaid`. The example shows the code for the state diagram below.

Mermaid diagrams can change their color theme and also some attributes can be configured in a JSON preamble enclosed by `%%`.

Not all themes or configurable attributes are available with every type of diagram for now. We have to test our diagrams before we publish them. One good way is the official [Mermaid live editor](https://mermaid.live).

## Layout

The following diagrams are only a few examples to give an impression of the layout. More diagram types exist and their number is growing. 

### State diagram
```mermaid {.fig--w-tiny .fig--posh-left-inside}
%%{init:
  { 
    "theme": "forest",
    "fontFamily": "ibm plex sans" 
  }
}%%
stateDiagram-v2
    [*] --> Still
    Still --> [*]
    Still --> Moving
    Moving --> Still
    Moving --> Crash
    Crash --> [*]
```

{{% pangram 5 %}}
{.placeholder data-pagefind-ignore="all"}

{{% pangram 7 %}}
{.placeholder data-pagefind-ignore="all"}

{{% pangram 6 %}}
{.placeholder data-pagefind-ignore="all"}

### Flow chart

```mermaid {.fig--w-large}
%%{init:
  { 
    "theme": "base",
    "fontFamily": "ibm plex sans" 
  }
}%%
flowchart LR
    A(Start) -->|Show edges| B[Hard Edge]
    B -->|Link text| C(Round edge)
    C -->|Show decision| D{Decision}
    D -->|One| E[Result one]
    D -->|Two| F[Result two]
```

### Entity relation

```mermaid {.fig--w-text}
%%{init:
  { 
    "theme": "base",
    "fontFamily": "ibm plex sans" 
  }
}%%
erDiagram
    CUSTOMER }|..|{ DELIVERY-ADDRESS : has
    CUSTOMER ||--o{ ORDER : places
    CUSTOMER ||--o{ INVOICE : "liable for"
    DELIVERY-ADDRESS ||--o{ ORDER : receives
    INVOICE ||--|{ ORDER : covers
    ORDER ||--|{ ORDER-ITEM : includes
    PRODUCT-CATEGORY ||--|{ PRODUCT : contains
    PRODUCT ||--o{ ORDER-ITEM : "ordered in"
```
