---
title:    "Changelog"
layout:   nil
version:  "v1.3"
---
Added metadata to the rendered image:

*   If there's enough room, `[WIDTH]x[HEIGHT] ([ASPECT RATIO])` will be
    rendered in the bottom-right corner of the image, using inverted
    background and foreground colours.

*   If there's not quite enough room for that string, we'll try the
    shorter string `[WIDTH]x[HEIGHT]`.  If there's not even room for
    that, we'll leave off the metadata entirely.

*   Common ratios (16:9, 4:3) are given a margin of error for those
    pesky half-pixel roundings.

*   Change usage: pass in individual properties instead of the
    OptionParse object.  This makes it possible to use as a lib.

*   Added error handling for bad hex values.

*   Dropped the margin of error, and converted the aspect ratio
    calculation to floating point.

*   Making BSD license explicit.

Closes [issue #1][gh-1].

[gh-1]: http://github.com/mikewest/PyPlaceholder/issues#issue/1
