# PhemtoCMS &ndash; Installation

## Installing the PhemtoCMS core

Copy all files from the installation package to your web server.

> PhemtoCMS determines your site's base path automatically. If this fails, set `base` in `config/phemto.pc`, e.g. `base: https://example.com/my-site`.

> If your server does not support `.htaccess`, users could access your content's source files. Remember to manually set directory access rights in this case.

## Installing themes

Extract the theme files to your theme directory (default: `theme`).

## Installing plugins

Extract the plugin to your plugins directory (default: `plugins`).

Note that the directory name has to match the lowercased plugin name, e.g. a plugin named `Blog` is expected at `plugins/blog`.
