# CSS Style Guide

MercadoLibre CSS Style Guide.

## Intro

The main goal of this guide is to set standards for writing our CSS files and
components, helping the readability and maintainability of our code. By doing
this, we can significantly reduce the time required to understand any front-end
implementation.

By writing clean code, we are able to:

+ achieve a code that’s easier to understand;
+ detect errors and potential problems;
+ easily identify what code can be reused;
+ build or update any functionality on any code already implemented;
+ work on any file regardless of who wrote it.

> "Consistent code, even when written by a team, should look like one person
wrote it." by [Addy Osmani]
(http://addyosmani.com/blog/javascript-style-guides-and-beautifiers/)

## Table of contents

+ [File Names](#file-names)
+ [General Formatting](#general-formatting)
+ [Selectors](#selectors)
+ [Properties](#properties)
+ [Comments](#comments)
+ [Tools](#tools)

## File Names

+ Don't name your files as your project.

    ```css
    /* DON'T */
    sales.css
    checkout.css
    ```

    ```css
    /* DO */
    base.css
    component-name.css
    ```

+ Name your stylesheet as your component name.

    ```css
    /* DON'T */
    styles.css
    main.css
    mobile.css
    full-page.css
    meli.css
    sandra.css /* ;) */
    a.css
    ```

    ```css
    /* DO */
    payment-methods.css
    message-boxes.css
    categories.css
    search-result.css
    ```

+ Use `base.css` as a name for your application basic styles, such as headings,
  typography, etc.

+ Separate the component name with a hyphen. Don't use camelCase or underscores.

    ```css
    /* DON'T */
    message_boxes.css
    paymentMethods.css
    ```

    ```css
    /* DO */
    message-boxes.css
    payment-methods.css
    ```

+ Extend your components by adding a `.sufix` in the filename.

    Extensions are specific styles that extend a given component.

    ```css
    /* DO */
    payment-methods.css
    payment-methods.mla.css
    ```

+ Separate your modifiers stylesheets with __double underscore__.

    Modifiers are stylesheets with styles that modify a component. For example:
    styles within media queries for different screen resolution target or an
    specific browsers.

    ```css
    /* DO */
    payment-methods__large.css /* media queries for big screens */
    payment-methods__small.css /* media queries for mobile devices */
    payment-methods__ie8.css /* "hacks" for IE8 */
    ```

    _Note: use conditional comments in your html file for referencing IE
    stylesheets._

## General Formatting

### Spacing

+ Use 4 spaces for indentation. Don't use tab.
  ([Instructions to configure Sublime Text ](http://git.io/tfOqOA))
+ Don't mix spaces and tabs.
+ Remove all spaces at the end of the line.
+ Use space between the selector and the bracket.
+ Use space between property and value.
+ Always leave a blank line between rules

### Selectors & Properties

+ Write one selector per line.

    ```css
    /* DO */
    .selector1,
    .selector2,
    .selector3 {
        property: value;
    }
    ```

+ Write one property per line.

    ```css
    /* DO */
    .selector1 {
        property: value;
        property: value;
    }
    ```

## Selectors

+ Only in English.

+ Separate words with a hyphen. Don't use camelCase or underscores.

    ```css
    /* DON'T */
    .homePage
    .box_registracion
    ```

    ```css
    /* DO */
    .home-page
    .registration-box
    ```

+ Use app-prefixes ONLY for cross-application stylesheets or reusable widgets.

    ```css
    /* DON'T */
    .cho-header
    .myml-sales
    ```

    ```css
    /* DO */
    .commons-header
    .ml-footer
    ```

+ __Avoid ID selectors__ as much as you can.

    _Declarations defined for an ID selector can't be reused._

+ Avoid tag selectors unless is for extending another selector.

    _Tag selectors are not specific enough._

## Properties

+ Alphabetize declarations.

+ Whenever possible, use shorthands.

    ```css
    /* DON'T */
    .selector {
        padding-bottom: 2em;
        padding-left: 1em;
        padding-right: 1em;
        padding-top: 0;
    }
    ```

    ```css
    /* DO */
    .selector {
        padding: 0 1em 2em;
    }
    ```

+ Omit unit specification when value is `0`.

    ```css
    /* DON'T */
    margin: 0em;
    padding: 0px;
    ```

    ```css
    /* DO */
    margin: 0;
    padding: 0;
    ```

+ Omit the `0` when value is between `0` and `1`.

    ```css
    /* DON'T */
    margin: 0.5em;
    ```

    ```css
    /* DO */
    margin: .5em;
    ```

+ Always use single quotation marks.

    ```css
    /* DON'T */
    background-image: url(sprite.png);
    background-image: url("sprite.png");
    ```

    ```css
    /* DO */
    background-image: url('sprite.png');
    ```

+ Use lowercase for hexadecimal values, and shorthand notation when allowed.

    ```css
    /* DON'T */
    color: #111111;
    background: #F3F3F3;
    ```

    ```css
    /* DO */
    color: #111;
    background: #f3f3f3;
    ```

+ Use rgba for background colors.

    _Take advantage of the opacity feature._

+ Always use `;` at the end of every declaration.

+ Don't use `!important`.

## Comments

+ All your code should be documented.

+ Use single-line comments to add hints, notes, suggestions or warnings.

+ Comment whenever necessary to explain the code.

+ Don't comment on vendor-prefixes.

    ```css
    /* DON'T */
    .selector {
        -webkit-border-radius: 3px; /* Safari */
    }
    ```

### Comment types

+ __Component header__

    Use this as a header for every stylesheet or component

    ```css
     /**
      * Component Name
      * @authors: pmontesano, hmammana, ndevalle
      * @description: small description of what the component does, where
      * is used, etc.
      */
    ```

+ __Block separator__

    Use this format for meaningful separations of code.

    ```css
    /* Sidebar
    ---------------------------------------------------------------*/
    ```

+ __Inline comment__

    Use regular comment formatting for small descriptions of properties or
    rules.

    ```css
    .ch-price {
        line-height: 1em; /* 16px */
    }
    ```

    Always comment values that might seem "[magic](http://git.io/BjYf0g)":

    ```css
    .form-actions {
        margin-left: 175px; /* label width + 15px */
    }
    ```

    And properties that apparently make no sense:

    ```css
    .payment-methods {
        display: inline-block;
        height: 20px; /* default value, exceptions added to each logo */
        text-align: left; /* just in case the container has text-align:right */
    }
    ```

## Tools

+ [Can I use...](http://caniuse.com/) Compatibility tables for support for
  HTML5, CSS3, SVG and more in desktop and mobile browsers.
+ [CSS BEAUTIFIER](http://html.fwpolice.com/css/) Beautifies your CSS to be
  consistent and easy to read
+ [CSSLint](http://csslint.net/) is an open source CSS code quality tool.
+ [Daturi](http://daturi.me/) is a tool for converting images to Base64.
+ [Dust-Me Selectors](https://addons.mozilla.org/en-us/firefox/addon/dust-me-selectors/)
  is a development tool that scans your website to find unused CSS selectors.
+ [Helium](https://github.com/geuis/helium-css) is a tool for discovering
  unused CSS across many pages on a web site.
+ [ProCSSor](http://procssor.com/) is an advanced CSS Prettifier.
+ [Spritemapper](http://yostudios.github.io/Spritemapper/) is a command line
  CSS spritemap generator.
+ [The W3C CSS Validation Service](http://jigsaw.w3.org/css-validator/)
+ [#CSSCreator](http://csscreator.com/properties) is a list of CSS properties
  and selectors with the first browser versions that support them.

## License

Licensed under the MIT license.  
Copyright (c) 2015 [MercadoLibre, Inc](http://www.mercadolibre.com/).
