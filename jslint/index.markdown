---
title:  "JSLint Prime: A fork with some bad parts"
layout: default
seo:
    desc:     "JSLint Prime: a fork of Douglas Crockford's JSLint, with some 'bad parts'."
    keywords: "jslint, fork, less hurting of feelings, crockford, bad parts"
feed:   
    url:    /jslint/atom.xml
    title:  "JSLint: Changelog"
---
`JSLint′` A fork with some bad parts
====================================

<ul class="actions">
  <li><a href="http://github.com/mikewest/jslint/tarball/v2010-11-21" class="cta">Download current version (2010-11-21)</a></li> 
  <li><a href="http://github.com/mikewest/jslint" class="cta">Source on GitHub</a></li> 
</ul>

One of the few tools that I consider truly indispensable when developing
websites is JSLint. Too bad it's almost impossible to contribute back to
the project, and that the project's run by someone who "will hurt your
feelings."

Instead of [complaining too much][badparts], I forked the official project
and started adding in some bugfixes and additions that I find useful (which
generally seem to focus on the CSS parser).  Periodically, I merge the
current trunk into my branch in the hopes that Crockford might, someday, do
the reverse.  We'll see.

[badparts]: http://mikewest.org/2010/05/jslint-needs-some-bad-parts

Tests
-----

Each change that I make to Crockford's official JSLint is backed up with QUnit
tests.  You'll find them in the [`/test` directory of the project][test].

[test]: http://github.com/mikewest/jslint/tree/master/test/

JSLint Utils
------------

If you use [JSLint Utils][utils], I'd recommend hopping into the project's
`lib/vendor` directory, and running `make fork`.  That'll drop the official
JSLint, and bring you up to date with the latest version of JSLint′.  It's
awesome.

[utils]:  /jslint_utils/

Changelog
---------

<ul>
{% for post in site.categories.jslint %}
  <li><strong>{{ post.date | date: "%Y-%m-%d" }} (Based on JSLint from {{ post.version }})</strong>: {{ post.content }}</li>
{% endfor %}
</ul>
