---
title:    "Changelog"
layout:   nil
version:  "0.5"
---
*   Changed navigation mappings in Vimroom mode to move over wrapped lines
    as they're displayed on the screen ("display lines" in Vim vernacular)
    as opposed to the default navigation over hard line-breaks ("logical
    lines").  These mappings are only implemented if `j`/`<Down>` and
    `k`/`<Up>` aren't already mapped to something else.

*   Explicitly setting `textwidth` when toggling Vimroom.

*   Turning off display of `cursorline` in the various padding windows.
