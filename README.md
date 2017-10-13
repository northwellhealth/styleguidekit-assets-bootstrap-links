![license](https://img.shields.io/github/license/pattern-lab/styleguidekit-assets-default.svg) ![current release](https://img.shields.io/github/release/pattern-lab/styleguidekit-assets-default.svg)
[![Packagist](https://img.shields.io/packagist/v/pattern-lab/styleguidekit-assets-default.svg)](https://packagist.org/packages/pattern-lab/styleguidekit-assets-default) [![Gitter](https://img.shields.io/gitter/room/pattern-lab/frontend-viewer.svg)](https://gitter.im/pattern-lab/frontend-viewer)

# Static Assets for the Default StyleguideKit

This code is responsible for creating Pattern Lab's UI look, feel, and functionality. These assets are are meant to be used in conjunction with the default [Mustache](https://github.com/pattern-lab/styleguidekit-mustache-default) and [Twig](https://github.com/pattern-lab/styleguidekit-twig-default) StyleguideKits, which control Pattern Lab-specific UI _inside_ the iframe.

This fork simply modifies the original StyleguideKit to add an XS link.

## Installation

### Node
Pattern Lab Node uses [npm](https://www.npmjs.com/) to manage project dependencies. To install the default static assets run:

    npm install git://github.com/notacouch/styleguidekit-assets-bootstrap-links#bootstrap

### PHP 

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

### PHP 
    
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
```

## Development Requirements

In order to modify these assets you need to install the following:

* the [Development Edition of Pattern Lab](https://github.com/pattern-lab/edition-php-development)
* [Node.js](http://nodejs.org) and NPM
* [Bower](http://bower.io)
* [Ruby Sass](http://sass-lang.com/install)
	
## Development Set-up
Read the [contribution guidelines](https://github.com/pattern-lab/styleguidekit-assets-default/blob/master/.github/CONTRIBUTING.md)

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

Read the [contribution guidelines](https://github.com/pattern-lab/styleguidekit-assets-default/blob/master/.github/CONTRIBUTING.md)