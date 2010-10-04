---
title:    "Changelog"
layout:   nil
version:  2010-10-01
---
*	Fixing a bug in yesterday's fix for font shorthand syntax.  The
	line-height doesn't _have_ to be specified.  It can be inherited.

*	Fixing support for `url(/path/to/image.jpg)` in `background` shorthand
	syntax.  The following should pass linting now, when the `css` option
	is set:

		div {
			background:	url(/path/to/image.jpg);
		}
	
	In the current JSLint trunk, it throws a JavaScript error.  That's bad.
