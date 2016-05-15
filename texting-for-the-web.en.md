# PhemtoCMS &ndash; Texting for the web with Markdown

PhemtoCMS' content is written in **Markdown**, a very simple markup language that compiles to HTML. For example, two line breaks denote a paragraph (`<p>` &hellip; `</p>`), one line break is a simple break (`<br>`). [Read a short introduction](https://en.wikipedia.org/wiki/Markdown), [learn everything there is to know about Markdown](https://daringfireball.net/projects/markdown/), or just [download the PDF cheatsheet](https://guides.github.com/pdfs/markdown-cheatsheet-online.pdf) (only first page relevant) if you are in a hurry. It is also possible to type plain HTML within Markdown files &ndash; yet even then not Markdown within HTML.

You can write Markdown with every text editor (see the [note about Windows Notepad](introduction.en.md#note-about-notepad)). There are also multiple in-browser editors available, e.g. [StackEdit](https://stackedit.io/editor).

> To be extended

## General markup

Use `<h1>` (Markdown: `# Heading`) exactly once per page. If the page title is displayed as `<h1>` (depending on your theme), only use `<h2>` (Markdown: `## Subheading`) and below in the page's content.

## Links

Provide meaningful text within links, e.g. use `[Download our newsletter](files/newsletter.pdf)` instead of `Download our newsletter [here](files/newsletter.pdf)`.

If possible, directly link to files instead of making your visitors search on a linked page. Use `[Download our newsletter](files/newsletter.pdf)` instead of `Our newsletter can be found under [documents](documents/)`. Feel free to addtionally link to a page with `Older newsletters can be found under [documents](documents/)`.

## Typography

**Bold** (Markdown: `**`&hellip;`**`) and _italic_ (Markdown: `_`&hellip;`_`) should be used very sparingly, <u>underline</u> not ever. If there are important buzzwords in your text, better place them in the title.

Refrain from changing font size and text color with inline styles. If you really need bigger or colored text, ask your designer.

Markdown does not replace simple quotes, dashes, etc., with typographic ones. Of course, PhemtoCMS has a plugin for that, enabled by default.
