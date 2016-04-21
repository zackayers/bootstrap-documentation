# **Bootstrap**

**[Overview](#overview)** | **[Bootstrap Grid](#bootstrap-grid)** | **[508 Compliance](#508-compliance)** | **[Helper Classes](#helper-classes)** | **[JavaScript](#javascript)**

--------------------------------------------------------------------------------

# Overview

## What is Bootstrap

Bootstrap is an open-source, HTML, CSS, and JS framework for developing responsive web applications.

## Bootstrap Documentation

Bootstrap's documentation can be found at [getbootstrap.com] (http://getboostrap.com)

Bootstrap breaks their documentation out into 3 sections: CSS, Components, and JavaScript.

1. CSS
⋅⋅* Contains classes for the grid systems, forms, buttons, and other helper classes.

2. Components
⋅⋅* Contains classes for navigation, breadcrumbs, labels, etc.

3. JavaScript
⋅⋅* Contains functionality such as modals (lightbox/popup), tooltips, and accordions (referred by Bootstrap as "collapse").

--------------------------------------------------------------------------------

# Bootstrap Grid

## Single Declarations

Bootstrap includes a responsive, mobile first fluid grid system that appropriately scales up to 12 columns as the device or viewport size increases. It includes predefined classes for easy layout options, as well as powerful mixins for generating more semantic layouts.

##  Introduction

Grid systems are used for creating page layouts through a series of rows and columns that house your content. Here's how the Bootstrap grid system works:

* Rows must be placed within a .container (fixed-width) or .container-fluid (full-width) for proper alignment and padding.
* Use rows to create horizontal groups of columns.
* Content should be placed within columns, and only columns may be immediate children of rows.
* Predefined grid classes like `.row` and `.col-xs-4` are available for quickly making grid layouts. Less mixins can also be used for more semantic layouts.
* Columns create gutters (gaps between column content) via padding. That padding is offset in rows for the first and last column via negative margin on .rows.
* The negative margin is why the examples below are outdented. It's so that content within grid columns is lined up with non-grid content.
* Grid columns are created by specifying the number of twelve available columns you wish to span. For example, three equal columns would use three `.col-xs-4`.
* If more than 12 columns are placed within a single row, each group of extra columns will, as one unit, wrap onto a new line.
* Grid classes apply to devices with screen widths greater than or equal to the breakpoint sizes, and override grid classes targeted at smaller devices. Therefore, e.g. applying any `.col-md-*` class to an element will not only affect its styling on medium devices but also on large devices if a `.col-lg-*` class is not present.

* [Basic Grid Example] (http://getbootstrap.com/css/#grid-example-basic)

--------------------------------------------------------------------------------

# 508 Compliance

Using color to add meaning only provides a visual indication, which will not be conveyed to users of assistive technologies – such as screen readers. Ensure that information denoted by the color is either obvious from the content itself (the contextual colors are only used to reinforce meaning that is already present in the text/markup), or is included through alternative means, such as additional text hidden with the `.sr-only` class.

Hide an element to all devices except screen readers with `.sr-only`. Combine `.sr-only` with `.sr-only-focusable` to show the element again when it's focused (e.g. by a keyboard-only user). Necessary for following accessibility best practices.

--------------------------------------------------------------------------------

# Helper Classes

Bootstrap contains a number of helper classes, all of which can be found here: [getbootstrap.com/css/#helper-classes](http://getbootstrap.com/css/#helper-classes).

## Contextual Colors

Conveys meaning through color with a handful of emphasis utility classes. These may aslso be applied to links and will darken on hover just like Bootstrap's default link styles.

## Contextual Backgrounds

Similar to contextual colors, just with backgrounds.

## Close Icon

`<button type="button" class="close" aria-label="Close"><span aria-hidden="true">&times;</span></button>`

## Quick Floats

Float an element to the left or right with a class:
```
<div class="pull-left">...</div>
<div class="pull-right">...</div>
```

## Center Content

`<div class="center-block">...</div>`

## Clearfix

Easily clear floats (more info on clearfix can be found here at [CSS Tricks](https://css-tricks.com/all-about-floats/#article-header-id-3)) by adding `.clearfix` to a parent element.

## Showing and Hiding Content

Force an element to be shown or hidden (including for screen readers) with the use of `.show` and `.hidden` classes. These classes use `!important` to avoid specificity conflicts, just like the quick floats. They are only available for block level toggling. They can also be used as mixins. `.hide` is available, but it does not always affect screen readers and is deprecated as of v3.0.1. Use `.hidden` or `.sr-only` instead. Furthermore, `.invisible` can be used to toggle only the visibility of an element, meaning its display is not modified and the element can still affect the flow of the document.

--------------------------------------------------------------------------------

# JavaScript

## Popovers

Bootstrap Reference: [getbootrap.com/javascript/#popovers](http://getbootstrap.com/javascript/#popovers)

We'll use the popovers content for our "tooltip text".

*Why don't we just use Bootstrap's tooltips?* Bootstrap's popovers gives us the flexibility to add more text, as well as a title. Check out Bootstrap's documentation for popovers (we can even apply subtle animations like a fade).

*Opt-in functionality*
For performance reasons, the Tooltip and Popover data-apis are opt-in, meaning you must initialize them yourself. One way to initialize all popovers on a page would be to select them by their `data-toggle` attribute:

```javascript
$(function () {
  $('[data-toggle="popover"]').popover()
});
```

*Specific markup required for dismiss-on-next-click*
For proper cross-browser and cross-platform behavior, you must use the `<a>` tag, not the `<button>` tag, and you also must include the `role="button"` and `tabindex` attributes.

Reference: [getbootstrap.com/javascript/#dismiss-on-next-click](http://getbootstrap.com/javascript/#dismiss-on-next-click)

## Collapse

Bootstrap Reference: [getbootstrap.com/javascript/#collapse](http://getbootstrap.com/javascript/#collapse)

Collapse is Bootstrap's version of the accordion. It's incredibly simple to implement, just check out Bootstrap's docs above.
