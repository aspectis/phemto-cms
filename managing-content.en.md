# PhemtoCMS &ndash; Managing content

> TODO: Documentation for layout blocks

## File names

All content file names end in `.$languageId.md`, e.g. `.en.md`. Only use lowercase characters `a-z`, digits `0-9`, `-` and `_`.

## Metadata

Atop pages and posts, metadata can be added, starting and ending with lines of `---` above any content, i.e. the first line has to be `---`. The metadata block is interpreted as _[PhemtoConfig](configuration.en.md)_ text.

## Shortcodes

Shortcodes are helpers with double curly brace notation that will be replaced upon output rendering. By default, `{{snippet ...}}` and `{{plugin ...}}` can be used &ndash; see below for details.

More shortcodes are available with the _Shorts_ plugin:

- `{{email $email}}`: Inserts a linked, scrambled email address that requires JavaScript to be accessible, preventing email addresses from being harvested by spam bots.

  Example: `{{email janedoe@example.com}}`

- `{{img $src [$alt [$caption]]}}`: Inserts an image with source `$src` and the required `alt` attribute `$alt` (empty when omitted). If `$caption` is set, displays `<caption>` tag below `<img>` and wraps both in `<figure>`.

  Example: `{{img "files/images/photo.jpg" "" "Photo: Aspectis, license: CC-BY 3.0"}}`

## Content types

### Pages

Default location: `content/pages`

Just type away. Soft hyphens can (and should) be inserted into very long words by using `&shy;`. [Snippets](#snippets) can be inserted with `{{snippet <snippet>}}`, plugins with `{{plugin <plugin>}}`.

Available metadata settings:

- `title` (required): The page title used in the navigation and as `<h1>` on the page itself (depending on your theme).
- `titleHidden` (default: `false`): Omit the page's title. Use to set a heading that differs from the title, or display no title at all. Note that this does not affect the title displayed in the navigation, thus `title` must be set regardless.
- `layout` (default: `default`): The layout to use (has to be available in your theme).
- `hidden`: (default: `false`): Hide this page completely. An error 404 is returned when a hidden page is requested.
- `hiddenFromSearch` (default: `false`): Prevent this page from being searched via the search plugin. If the page is otherwise visible, this does not prevent crawlers from indexing it.

A simple page example (`content/pages/welcome.en.md`):

```
---
title: Welcome
titleHidden
---

# Welcome to my website

It's a pleasure meeting you. Have a look around.
```

### Snippets

Default location: `content/snippets`

Snippets can be used on any page. They usually contain content that appears in multiple places or in special areas of your theme, like the footer. To include a snippet, use `{{snippet $snippet}}`, e.g. `{{snippet footer-links}}`.

Snippets cannot have metadata.

### Posts

> Requires the _Blog_ plugin

Default location: `content/posts`

Posts work a lot like pages, yet they are displayed by the _Blog_ plugin in their own template. Their metadata must contain a `title`, optionally `author` and `date` (in the format YYYY-MM-DD) can be set. A simple example:

```
---
title: My first post
author: Jane Doe
date: 2016-02-29
---

Welcome to my new website!
```

### Files

Default location: `content/files`

Binary files go here, e.g. images and PDFs. Embed an image with `![Alt text](files/image.jpg)`. To link to a file (or any other resource), use `[Link text](files/document.pdf)`.

> If your server does not have _mod_rewrite_ support, prepend `content/` to all file paths.
