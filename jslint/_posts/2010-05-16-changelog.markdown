---
title:    "Changelog"
layout:   nil
version:  2010-04-06
---
*   Updated to version of JSLint from 2010-04-06

*   Added support for `#RRGGBBAA` style hex colours for alpha support via
    IE's `filter` attribute.  The following should pass linting now, when
    the `css` option is set:
    
        .myclass {
            filter:progid:DXImageTransform.Microsoft.Gradient(StartColorStr=#FFFFFF50,EndColorStr=#FFFFFF50);
        }
    
    In the current JSLint trunk, it throws a "Bad hex value" warning.

*   Added support for CSS3's `::` selector to designate pseudo-elements.
    The following should pass linting now, when the `css` option is set:

        .myclass::first-line {
            color:  red;
        }

    In the current JSLint trunk, it throws a "Expected pseudo, found
    ':first-line' warning.

*   Added support for vendor-specific prefixes in pseudo-selectors.  The
    following should pass linting now, when the `css` option is set:

        input::-moz-focus-inner {
            padding:  0;
        }
    
    This is especially important, given Gecko's tendency to add 3px of
    padding to input elements that can only be removed via manipulation
    of `input::-moz-focus-inner`, but was [rejected][vendorprefix] when
    submitted to the list.

[vendorprefix]: http://tech.groups.yahoo.com/group/jslint_com/message/1280
