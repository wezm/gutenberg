+++
title = "Creating a theme"
weight = 30
+++

Creating is exactly like creating a normal site with Gutenberg, except you
will want to use many [Tera blocks](https://tera.netlify.com/docs/templates/#inheritance) to
allow users to easily modify it.

## Getting started
As mentioned, a theme is just like any site: start with running `gutenberg init MY_THEME_NAME`.

The only thing needed to turn that site into a theme is to add `theme.toml` configuration file with the
following fields:

```toml
name = "my theme name"
description = "A classic blog theme"
license = "MIT"
homepage = "https://github.com/Keats/gutenberg-hyde"
# The minimum version of Gutenberg required
min_version = "0.3"

# Any variable there can be overriden in the end user `config.toml`
# You don't need to prefix variables by the theme name but as this will
# be merged with user data, some kind of prefix or nesting is preferable
# Use snake_casing to be consistent with the rest of Gutenberg
[extra]

# The theme author info: you!
[author]
name = "Vincent Prouillet"
homepage = "https://vincent.is"

# If this is porting a theme from another static site engine, provide
# the info of the original author here
[original]
author =  "mdo"
homepage = "http://markdotto.com/"
repo = "https://www.github.com/mdo/hyde"
```

A simple theme you can use as example is [Hyde](https://github.com/Keats/hyde).

## Working on a theme
As a theme is just a site, you can simply use `gutenberg serve` and make changes to your
theme, with live reloading working as expected.

Make sure to commit every directory (including `content`) in order for other people
to be able to build the theme from your repository.

### Caveat

Please note that [include paths](https://tera.netlify.com/docs/templates/#include) can only be used in normal templates.
Theme templates should use [macros](https://tera.netlify.com/docs/templates/#macros) instead.

## Submitting a theme to the gallery

If you want your theme to be featured in the [themes](./themes/_index.md) section
of this site, the theme will require two more things:

- `screenshot.png`: a screenshot of the theme in action with a max size of around 2000x1000
- `README.md`: a thorough README explaining how to use the theme and any other information
of importance

The first step is to make sure the theme is fulfilling those three requirements:

- have a `screenshot.png` of the theme in action with a max size of around 2000x1000
- have a thorough `README.md` explaining how to use the theme and any other information
of importance
- be of reasonably high quality

When your theme is ready, you can submit it to the [themes repository](https://github.com/Keats/gutenberg-themes)
by following the process in the README.

