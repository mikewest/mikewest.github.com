---
title:    "Changelog"
layout:   nil
version:  "0.10"
---
Changing workflow to remove the compliation step.  There's no good reason
to expose that internal complexity to the user; she's never going to
compile the binary message file without also building the site.

Additionally, added the ability to change the list of file extensions that
are parsed for translatable text.  The default remains 
`.html,.js,.css,.txt,.xml,.markdown` but the user can now override that by
providing an `--extensions` argument.
