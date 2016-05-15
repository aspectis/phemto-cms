# PhemtoCMS &ndash; Configuration

> TODO: Add plugin config documentation

PhemtoCMS is configured solely with **PhemtoConfig** files. They are basically simplified YAML, using tabs instead of spaces for indention. Use no or double quotes for values, single quotes are literals. All paths shall be typed without a trailing slash.

## Basic options

Your page will run without any configuration if you're adhering to the defaults. These are the site-wide options set in `config/phemto.pc`, all optional except `siteTitle`:

> TODO: Update!

- `base` (default: none): Overrides determined base path with this.
- `cacheDir` (default: `cache`): The directory to store cache files in.
- `cacheEnabled` (default: `false`): Enable page caching. Note that this is a beta feature and that the cache has to be purged manually.
- `contentDir` (default: `content`): The direcory in which your content is located.
- `contentFileExt` (default: `html`): The file extension of content files. Change to `md` if you are using Markdown.
- `defaultLangId` (default: `en`): The ID of your site's default language if no other language is specified. We recommend using [ISO 639-1](https://www.loc.gov/standards/iso639-2/php/code_list.php).
- `errorLogFile` (default: _empty string_): If set, PHP errors are logged to this file.
- `home` (default: `home`): Your site's front page. A file named `$home.$defaultLangId.md` must be present in `$contentDir/pages`.
- `indexRewritten` (default: `false`): PhemtoCMS tries to detect if _mod_rewrite_ is enabled and decides if `index.php` can be omitted in the URL. Enable this option if you get URLs with `index.php` despite _mod_rewrite_ being available.
- `languages` (default: see [below](#default-language-settings)): Settings for every language your content is available in (`dateFormat`, `name` and `locale`). Have a look at the source of `phemto/Phemto.php` for all details.
- `pluginsDir` (default: `plugins`): The location of your plugins directory.
- `siteTitle` (default: _empty string_): Your site's title. This is the only required option, which can also be set via strings files if the title is language-dependent.
- `themeDir` (default: `theme`): The location of your theme directory. Change if you want to have multiple themes installed.

### Default language settings

```
languages:
	en:
		dateFormat: m/d/Y
		timeFormat: h:i A
		name: English
		locale: en_US
```

## Content-related options

### Site structure (page tree)

Default location: `config/tree.pc`

The structure of your site used for building the main navigation. Lines without indention depict the first level, one tab the second and so on. A simple example:

```
home
about-us
	child-page
		grand-child
back-to-1st-level
sitemap
```

### Strings

Strings files contain plain strings without any HTML that are used as-is outside of theme templates. User strings files are names `config/strings.$langId.pc`. Your theme and every plugin can optionally add their own strings files.

Aside from `siteTitle`, setting `siteTagline` (which is appended to the title on the front page) and `siteDescription` (used for the corresponding `<meta>` tag) is recommended.
