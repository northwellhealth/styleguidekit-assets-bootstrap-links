![License: MIT](https://img.shields.io/github/license/notacouch/styleguidekit-assets-bootstrap-links.svg)
![Packagist](https://img.shields.io/packagist/v/notacouch/styleguidekit-assets-bootstrap-links.svg)]

# Static Assets for the Default StyleguideKit

These static assets are meant to be used with the default [Mustache](https://github.com/pattern-lab/styleguidekit-mustache-default) and [Twig](https://github.com/pattern-lab/styleguidekit-twig-default) StyleguideKits. They control the look, feel, and functionality of the front-end of Pattern Lab PHP.

This fork simply modifies the original StyleguideKit to add an XS link.

## Installation

Pattern Lab PHP uses [Composer](https://getcomposer.org/) to manage project dependencies. To install these static assets add the following to your composer.json:

```json
  "repositories": [
    {
      "type": "vcs",
      "url": "https://github.com/notacouch/styleguidekit-assets-bootstrap-links"
    }
  ]
```

Then run:

    composer require pattern-lab/styleguidekit-assets-default
    
## Modify viewport ranges

Follow instructions provided in the original release of this feature: [Release v3.5.0](https://github.com/pattern-lab/styleguidekit-assets-default/releases/tag/v3.5.0). Don't forget to add `xs` to the array, its first entry will replace `ishMinimum`.

JSON example:

```json
  "ishViewportRange": {
    "xs": [240, 767],
    "s": [768, 991],
    "m": [992, 1199],
    "l": [1200, 2600]
  },
```

YAML example:

```yaml
  ishViewportRange:
    xs: 
      - 240
      - 767
    s:
      - 768
      - 991
    m:
      - 992
      - 1199
    l:
      - 1200
      - 2600
  },
```

## Development Requirements

In order to modify these assets you need to install the following:

* the [Development Edition of Pattern Lab PHP](https://github.com/pattern-lab/edition-php-development)
* [Node.js](http://nodejs.org) and NPM
* [Bower](http://bower.io)
* [Ruby Sass](http://sass-lang.com/install)
	
## Development Set-up

Once you've installed the requirements do the following to set-up for development:

1. `cd /path/to/dev-edition/packages/notacouch/styleguidekit-assets-bootstrap-links`
2. `git config branch.dev.remote origin`
3. `npm install`
4. `bower install`

## Making Changes

To make changes **always edit files in `src/`**. To make sure that these changes are reflected in the front-end and `dist/` folder run the following:

    gulp --copy-dist=../../../public

To watch for changes you can use:

    gulp --watch --copy-dist=../../../public

At this point changes to the static assets should compile to the correct locations in the project as well as `dist/`.
