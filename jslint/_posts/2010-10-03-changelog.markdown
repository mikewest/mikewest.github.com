---
title:    "Changelog"
layout:   nil
version:  2010-10-01
---
*   Updated to the official JSLint version from 2010-10-01.

*   Fixed simple `font` shorthand syntax.  The following should pass
    linting now, when the `css` flag is set:

        p {
            font: 12px/1 Helvetica;
        }

    In trunk, it throws an error when it hits the `/`, which cascades
    into errors for the line-height and font-family.

*   Added `last-child` as an acceptable pseudoclass.  The following
    should pass linting now, when the CSS flag is set:

        p:last-child {}

    In trunk, it throws an error, claiming that `last-child` isn't a
    pseudoclass.
