---
title:  "JSLint Utils"
layout: default
seo:
    desc:     "JSLint Utils: easily integrate JSLint and Hudson, and lint on the command line"
    keywords: "jslint, hudson, continuous integration, rhino, command line, node.js, node"
feed:   
    url:    /jslint_utils/atom.xml
    title:  "JSLint Utils: Changelog"
---
`JSLint Utils` A collection of useful bash scripts
==================================================

<ul class="actions">
  <li><a href="http://github.com/mikewest/jslint-utils/tarball/v1.6" class="cta">Download current version (v1.6)</a></li> 
  <li><a href="http://github.com/mikewest/jslint-utils" class="cta">Source code on GitHub</a></li> 
</ul>

One of the few tools that I consider truly indispensable when developing
websites is [JSLint][].  I love it.  It makes my life as a webdev simpler
and less prone to idiotic mistakes.  Hitting the website to check changes
to my scripts is, however, a huge pain in the ass.  Hence, this project.

`JSLint Utils` is a set of utility scripts that wrap JSLint/Rhino, 
enabling linting on the command line, and automated reporting of
linting errors via a continuous integration system like Hudson.

Usage: CLI
----------

With [Node.js][node] (_recommended_) or [Rhino][rhino] installed, you can
lint a specific JavaScript file or stylesheet from the command line by running:

    /path/to/run-jslint.sh [FILE TO LINT]

If the file is clean, the script will output on `stdout`:

    jslint: No problems found in good.js

If not, you'll get a list of errors on `stderr`, and an return code
of 1:

    [error.js] Lint at line 1 character 1: 'x' is not defined.
    x = "is not defined";

Usage: Hudson
-------------

Integration with CI systems like Hudson generally takes place via `make`
files and XML dumps.  In short, you'll write a `make` file that lints
all the files you care about, and dumps the results in a specific XML 
format into a directory.  Hudson reads through the test results in that
directory, and generates reports based on success or failure.

Before generating any test results, you'll need to specify the basename
to be used for the reporting.  It makes good sense to follow the JUnit 
methodology here by using a reversed domain name as your package name.

Edit line 12 of `jslint-to-xml.sh` to specify your basename:

    TEST_BASENAME="org.mikewest.static"

With that configuration out of the way, you can generate an XML report
manually by running:

    /path/to/jslint-to-xml.sh [FILE TO LINT] [REPORT DIRECTORY]

The file specified as the script's first argument will be linted, and a
report will be generated in the directory specified as the second argument.

Running against multiple files at once is generally best done via `find`.
Take a look at [the project's `Makefile`][make] for how I'd suggest that
best be done.  Make sure you configure the source and reporting directories
by changing the relevant lines of the file, and it should Just Work™.

Hudson Configuration
--------------------

In your Hudson project, you'll need to do a tiny bit of configuration work
in order to get linting running on an automated basis.  Assuming you've
already put a project together, you'll need to do a few things:

1.  Add a new build step that runs `make hudson` in the source directory
    of your static assets.  You'll find this in the "Build" panel of the
    project configuration.

    <img src="/jslint_utils/hudson-build.png" width="561" alt="Screenshot of the build panel in Hudson config" class="screenshot">

2.  Instruct Hudson to look for JUnit-style test reports by checking the
    "Publish JUnit test report result" box in "Post-build Actions", and 
    entering the report directory you've configured in the `Makefile`.

    <img src="/jslint_utils/hudson-xmlpath.png" width="561" alt="Screenshot of the post-build panel in Hudson config" class="screenshot">

3.  Commit something, and watch while Hudson does it's thing.

4.  Pat yourself on the back for a job well done.

Changelog
---------

<ul>
{% for post in site.categories.jslint_utils %}
  <li><strong>v{{ post.version }} ({{ post.date | date: "%Y-%m-%d" }})</strong>: {{ post.content }}</li>
{% endfor %}
</ul>

Questions?  Bugs?
-----------------

If anything's unclear, [file a bug via GitHub][issues] or [drop me an email][email].

<small class="license">&copy;2010 <a href="http://mikewest.org/">Mike West</a>: Project source is <a href="http://github.com/mikewest/jslint-utils/blob/master/LICENSE.markdown" rel="license">BSD licensed</a>, and <a href="http://github.com/mikewest/jslint-utils">available on GitHub</a></small>

[JSLint]: http://jslint.com/
[make]:   http://github.com/mikewest/jslint-utils/blob/master/Makefile
[issues]: http://github.com/mikewest/jslint-utils/issues
[node]:   http://nodejs.org/#download
[rhino]:  http://www.mozilla.org/rhino/download.html
[email]:  mailto:mike@mikewest.org
