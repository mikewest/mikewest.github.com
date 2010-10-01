---
title:      "Mike West's Projects"
layout:     default
bodyclass:  projectlist
---
Projects
========

*   [<img src="/static_gettext/logo.png" alt="" width="280" height="158"> `static_gettext`][static_gettext] is an internationalization framework
    for static, plaintext documents and templates. It's geared towards 
    straightforward translation of static websites, but can be easily used for
    any set of files you'd like to translate as a group.

*   [<img src="/jslint_utils/logo.png" alt="" width="280" height="158"> `jslint utils`][jslintutils] is a collection of scripts that wrap JSLint
    and Rhino, enabling easy linting on the command line, and automated reporting
    of linting errors via a continuous integration system like Hudson.

*   [<img src="/send_to_instapaper/logo.png" alt="" width="280" height="158"> Send to Instapaper][StI] is a Chrome extension that replicates the
    functionality of Instapaper's bookmarklet in an elegant and embedded
    way.  I use it daily.

[static_gettext]:   /static_gettext/
[static_gettext_logo]:  http://www.google.com/images/logo.gif
[jslintutils]:      /jslint_utils/
[StI]:              https://chrome.google.com/extensions/detail/liamajdghafnpofaconeimppimbdbhgi/

Trivial Forks
-------------

*   [`yuidoc`][yuidoc]: A quick fork of YUI Docs that runs texty bits through
    Markdown before rendering the page.

*   [Jekyll][]: My Jekyll fork, explained in detail [on my blog][jekyllfork].

*   [`jslint`][jslint]: JSLint rocks, but it [needs some bad parts][badjslint].
    I've forked it to add in some functionality that Douglas Crockford doesn't
    seem to be in any hurry to add, and to revert a few changes he's made that
    I think are more damaging than helpful.


[yuidoc]:       http://github.com/mikewest/yuidoc/
[jslint]:       http://github.com/mikewest/jslint/
[badjslint]:    http://mikewest.org/2010/05/jslint-needs-some-bad-parts
[Jekyll]:       http://github.com/mikewest/jekyll
[jekyllfork]:   http://mikewest.org/2009/11/my-jekyll-fork

Abandonware
-----------

*   [Fallow][]: Ruby-based blogging engine that I wrote as a "Teach myself Ruby"
    project.  I've since thrown it away in favour of Jekyll.

*   [Etags for Nginx][nginx-etags]: Nginx doesn't generate Etags for static
    content.  With this plugin, it does.  Kinda.  Sorta.  I wouldn't recommend
    using this in production.

*   [DataRequestor][]: Pompously described (in _2005_) as "Ajax without the
    confusing API."  Unmaintained, untouched since SXSW 2005, released under
    MIT license.

*   [PerfectTime][]: JavaScript snippet that converts times on a page to a
    user's local timezone.

*   [`mcw_templates`][mcw_templates]:   A TextPattern plugin that enables import
    and export of templates.  I haven't used TextPattern in years, so I've no
    idea if this plugin still works.

[Fallow]:           http://github.com/mikewest/fallow
[nginx-etags]:      http://github.com/mikewest/nginx-static-etags
[DataRequestor]:    http://github.com/mikewest/datarequestor
[PerfectTime]:      http://github.com/mikewest/perfecttime
[mcw_templates]:    http://github.com/mikewest/mcw_templates

<small class="license">&copy;2010 <a href="http://mikewest.org/">Mike West</a></small>
