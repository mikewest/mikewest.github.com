---
title:  "JSLint Utils"
layout: default
---
`JSLint Utils` A collection of useful bash scripts
==================================================

<ul class="actions">
  <li><a href="http://github.com/mikewest/jslint-utils/tarball/v1.1" class="cta">Download current version (v1.1)</a></li> 
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

With [Rhino installed][rhino], you can lint a specific JavaScript file
or stylesheet from the command line by running:

    run-jslint.sh [FILE TO LINT]

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

    jslint-to-xml.sh [FILE TO LINT] [REPORT DIRECTORY]

The file specified as the script's first argument will be linted, and a
report will be generated in the directory specified as the second argument.

Running against multiple files at once is generally best done via `find`.
Take a look at [the project's =Makefile=][make] for how I'd suggest that
best be done.


Questions?  Bugs?
-----------------

If anything's unclear, [file a bug via GitHub][issues], [drop me an email][email],
or comment here:

<div id="disqus_thread"></div>
<script type="text/javascript">
  /**
    * var disqus_identifier; [Optional but recommended: Define a unique identifier (e.g. post id or slug) for this thread] 
    */
  var disqus_identifier = "jslintutils",
      disqus_developer  = 1,
      disqus_skip_auth  = true;
  (function() {
   var dsq = document.createElement('script'); dsq.type = 'text/javascript'; dsq.async = true;
   dsq.src = 'http://projectsmikewestorg.disqus.com/embed.js';
   (document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]).appendChild(dsq);
  })();
</script>
<noscript>Please enable JavaScript to view the <a href="http://disqus.com/?ref_noscript=projectsmikewestorg">comments powered by Disqus.</a></noscript>
<a href="http://disqus.com" class="dsq-brlink">blog comments powered by <span class="logo-disqus">Disqus</span></a>

<small class="license">&copy;2010 <a href="http://mikewest.org/">Mike West</a>: Project source is <a href="http://github.com/mikewest/jslint-utils/blob/master/LICENSE.markdown" rel="license">BSD licensed</a>, and <a href="http://github.com/mikewest/jslint-utils">available on GitHub</a></small>

[JSLint]: http://jslint.com/
[make]:   http://github.com/mikewest/jslint-utils/blob/master/Makefile
[issues]: http://github.com/mikewest/jslint-utils/issues
[rhino]:  http://www.mozilla.org/rhino/download.html
[email]:  mailto:mike@mikewest.org
