jQuery Bootstrap 3 Breakpoint Check
===================================

Check the current visibility of bootstrap 3 breakpoints.

### Why another breakpoint check for bootstrap 3?

The plugin I have created for simple reasons:

-	I needed something that works and is easy to integrate into existing projects (in my daily work)
-	I did not want to create a new code in each project. A plugin repository is mostly stable
-	Bootstrap did not provide its own Javascript API for this
-	I had fun doing it^^

Installation
------------

You can download the plugin manually or install by composer. ... and the plugin requires jQuery. ;) jQuery must be properly integrated into the page.

### Install via Composer (recommended for php projects)

If you do not have [Composer](http://getcomposer.org/), you may install it by following the instructions at [getcomposer.org](http://getcomposer.org/doc/00-intro.md#installation-nix).

You can then install the package using the following command:

```
php composer.phar require --prefer-dist cakebake/jquery-breakpoint-check "*"
```

or add

```
"cakebake/jquery-breakpoint-check": "*"
```

to the require section of your `composer.json` file and run `php composer.phar update`.

### Manual Installation

#### Download:

-	[Current Master Branch](https://github.com/cakebake/jquery-breakpoint-check/archive/master.zip)
-	[Latest releases](https://github.com/cakebake/jquery-breakpoint-check/releases)

Include one of the two javascript files from the folder `js` after jQuery include. For productive projects, you can use the `jquery-breakpoint-check.min.js` version. For more details see file `test.html`.

Example:

```html
<script src="js/jquery-breakpoint-check.min.js"></script>
```

Usage
-----

Is the current screen resolution `xs` breakpoint?

```js
if ($.isXs()) {
    alert('Is xs breakpoint :)');
}
```

Is the current screen resolution `sm` breakpoint?

```js
if ($.isSm()) {
    alert('Is sm breakpoint :)');
}
```

Is the current screen resolution `md` breakpoint?

```js
if ($.isMd()) {
    alert('Is md :)');
}
```

Is the current screen resolution `lg` breakpoint?

```js
if ($.isLg()) {
    alert('Is lg breakpoint :)');
}
```

Is the current screen resolution `custom` breakpoint?

Create a CSS-Class with visibility for your custom breakpoint. For example:

```
.visible-grid-float-breakpoint {
    @media (min-width: @grid-float-breakpoint-max) {
        display: none;
        visibility: hidden;
    }
}
```

```js
if ($.isBreakpoint('grid-float-breakpoint')) {
    alert('It is my custom breakpoint :)');
}
```

Check the current breakpoint on screen resize.

```js
$(window).resize(function () {
    if ($.isXs()) {
        alert('Is xs breakpoint :)');
    } else if ($.isSm()) {
        alert('Is sm breakpoint :)');
    } else if ($.isMd()) {
        alert('Is md :)');
    } else if ($.isLg()) {
        alert('Is lg breakpoint :)');
    }
}).resize();
```

Hide a div on `xs` and `lg` breakpoint.

```js
$(window).resize(function () {
    var selector = $("div.selector");
    if ($.isXs() || $.isLg()) {
        selector.hide();
    } else {
        selector.hide();
    }
}).resize();
```

Copyright and License
---------------------

Copyright (C) Jens A. (cakebake)

Released under [the MIT license](LICENSE)
