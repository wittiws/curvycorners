## Introduction ##

For reasons of size and complexity, CurvyCorners doesn't use a full-scale CSS parser. It is therefore a bit "simple-minded" when it comes to CSS, and that means that support is somewhat limited.

## Limitations ##

  * No support for `:hover`
  * No support for attribute or child selectors, e.g. `div.a>div` or `div[lang="es"]`
  * No support for sibling selectors, e.g. `div+div`
  * Limited support for scoped ID selectors, e.g. `div #mybox`

### scoped ID selectors ###

The following selectors may not work as expected:

  * `div #mybox`
  * `div.rounded #mybox`

Because an ID identifies a page element uniquely, qualifying it with an enclosing scope may cause the selector to fail (e.g. if `#mybox` is a top-level DIV, or if it is not located within a DIV of class rounded). However, CurvyCorners assumes that the element is to be referenced anyway and will apply the appropriate rounding styles.

## Examples of supported selectors ##

  * `.myclass`
  * `#mydiv frameset.myclass`
  * `form.rounded frameset, div.rounded`

## Warning ##

Because CurvyCorners appends extra DIVs to the boxes you wish to round, the following selector will reliably not work:
```
#myBox div
```
This is because the style will be applied not just to the top-level DIVs within the element whose ID is myBox, but also to the DIVs inserted by CurvyCorners.

## Formally: what is supported ##

  * a selector-list, where a selector-list is either a single selector or a single selector followed by a comma and an optional space, followed by a selector-list.
  * A single selector may be either a simple-selector or a simple-selector followed by a space followed by another simple-selector.
  * A simple-selector may be either an ID of the form `#myID`, or a tag-class-selector.
  * A tag-class-selector may be any one of:
    1. a tag name (e.g. `div`);
    1. a class name preceded by a dot (e.g. `.myClass`); or
    1. a tag name followed by a dot followed by a class name (e.g. `div.myClass`).