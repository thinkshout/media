# TS Media Module (ThinkShout Edition)

## Introduction

Originally built to allow some updates to the existing Media module, this stripped-down version
provides the minimum amount of functionality and frees up the "media" namespace
to avoid conflicting with Drupal's core media module.

## How to use this version of the TS media module.

If you've been previously using the default branch of the thinkshout/media module
through composer, updating to this version is easy.

1. Uninstall the thinkshout media module:

`drush pmu media`

2. Update thinkshout media using composer:

```sh
composer require thinkshout/media:dev-ts_media
```

3. Install ts_media `drush en ts_media`

## Things to check after installing

The Thinkshout Media module didn't really do a whole lot, so if you've just
switched to the new version there are only a few things to check.

- There is a Media link in the admin toolbar and a button to "Add a new Media" below it.
- There is a button to "Add media" on the /admin/content/media page
- The /admin/content/media page looks somewhat themed.

and of course, test adding media to some items, both embedded and as a field.
