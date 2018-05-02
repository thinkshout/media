# TS Media Module (ThinkShout Edition)

## Introduction

Originally built to allow some updates to the existing Media module, this stripped-down version
provides the minimum amount of functionality and frees up the "media" namespace
to avoid conflicting with Drupal's core media module.

## How to use this version of the TS media module.

If you've been previously using the default branch of the thinkshout/media module
through composer, updating to this version is a two-step process.

1. Uninstall the thinkshout media module:

`drush pmu media`

2. Update your composer.json file:

In your composer.json file find:

```
"thinkshout/media": "dev-8.x-1.x",
```

and replace it with

```
"thinkshout/media": "dev-ts_media",
```

3. Run `composer update` to get the latest thinkshout/ts_media module.

4. Install ts_media `drush en ts_media`

### If you've already done the above steps and deployed them, start here:
From here down, you can only proceed if your database already believes the media module is uninstalled. You will need to deploy
the code above to your database before you can proceed. This means two deploys, which can be done sequentially or over time.

5. Upgrade to ts_media_2

In your composer.json file find:

```
"thinkshout/media": "dev-ts_media",
```

and replace it with

```
"thinkshout/media": "dev-ts_media_2",
```

6. Run `composer update` to get the latest thinkshout/ts_media module.

7. Run `drush cr && drush updb` -- this should convert all your media_entity items into media items.

Note: You'll see some expected warning when you run updb:

```
The following module is missing from the file system: media_entity_document bootstrap.inc:268                                                              [warning]
The following module is missing from the file system: media_entity_image bootstrap.inc:268
```

Those are fine, and will go away after the updb.

## Things to check after installing

The Thinkshout Media module didn't really do a whole lot, so if you've just
switched to the new version there are only a few things to check.

- There is a Media link in the admin toolbar and a button to "Add a new Media" below it.
- There is a button to "Add media" on the /admin/content/media page
- The /admin/content/media page looks somewhat themed.

and of course, test adding media to some items, both embedded and as a field.

## Debugging errors on install or update

If you're seeing errors when trying to install or update this module, you can find a path forward here.

### Error 1: The ts_media module should not be installed if a media module is already installed

If you see this error, you've come from one of two scenarios:

1. I'm installing the ts_media_2 module on a brand new version of Drupal

Don't do this! Instead use the bene_media module.

2. I'm trying to install ts_media after moving away from the old thinkshout media module.

You need to follow the deployment steps outlined above, with a two-step deployment process, for this module
to be installable. Please check out the ts_media branch instead of this ts_media_2 branch.
