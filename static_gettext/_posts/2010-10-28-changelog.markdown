---
title:    "Changelog"
layout:   nil
version:  0.13
---
Adding rudimentary RTL support

*   Added `{{ '{' }}{ LANGUAGE_DIRECTION }}` tag that is replaced with either
    `ltr` or `rtl` according to a whitelist culled [from Wikimedia][1].
    Thanks to [Tom Bigelajzen][2] for the push in the right direction.

*   Converted `isGettextAvailable` to a static method.

[1]: http://meta.wikimedia.org/wiki/Template:List_of_language_names_ordered_by_code
[2]: http://tombigel.com/
