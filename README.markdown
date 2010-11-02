projects.mikewest.org
=====================

A Jekyll-based project documentation site, listing the project I've been
working on recently, and documenting each to whatever extent I found
reasonable at the time.

Each project lives in a separate directory, and the project changelogs are
"posts" in the `.../[project name]/_posts/` directory.  Jekyll tags each
post with `[project name]`, which I use in each project's `index.markdown`
file to write out the project's changelog.

Each project's `atom.xml` operates on a similar principle, rendering the
changelog with hardcoded URLs for each project.  It's a bit of manual labor
that I haven't quite figured out how to easily automate.  I bet it'd be doable
via a new page layout, but I haven't gotten to the point of playing with
that approach yet.

The main `atom.xml` in the project's root directory renders all posts, so,
all changes from all projects.  I'm explicitly mapping project tags to 
friendly names, which is ugly but effective.
