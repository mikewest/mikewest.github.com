---
title:  "Installation -- `static_gettext`: Localization for Static Documents"
layout: static_gettext
---

Prerequisites
-------------

You won't have to do much to get up and running with `static_gettext`.  The
prerequisites are trivial:

*   Python 2.5+
*   Some moderately recent version of [gettext][]

If you're running on OSX, these are installed by default.  If you're running
on Debian (Ubuntu), running the following command will take care of you:

    sudo apt-get install python gettext

Other operating systems (like Windows) are untested... You're on your own, so
good luck!

Installation
------------

It's hardly worth the name "installation", but you'll need to grab the
`static_gettext.py` script somehow, and put it somewhere accessible on
your computer.  The easiest mechanism is simply to [download the current
version][tarball], extract it, and move it into your project directory.

If you like living on the edge, you can grab the latest version directly
via something like:

    curl -O http://github.com/mikewest/static_gettext/raw/master/static_gettext.py

Or clone the whole repository:

    git clone git://github.com/mikewest/static_gettext.git

Enjoy!

[gettext]:  http://www.gnu.org/software/gettext/
[tarball]: http://github.com/mikewest/static_gettext/tarball/v0.9
