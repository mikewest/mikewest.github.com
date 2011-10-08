---
title:    "Changelog"
layout:   nil
version:  "0.7"
---
*   Fixed [Issue #2][1] by adding a new `g:vimroom_navigational_keys` option
    to enable users to determine whether navigational keys ought to be mapped
    as navigating over "display" lines instead of "logical" lines. I also
    wrapped the mappings in a try/catch block, just in case.
