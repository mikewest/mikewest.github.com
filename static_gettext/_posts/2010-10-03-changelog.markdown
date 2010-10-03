---
title:    "Changelog"
layout:   nil
version:  0.11
---
Adding `{{ '{' }}{ LANGUAGE_CODE }}` tag to allow the current target language
code to be embedded in the document.  This is expecially useful for
HTML documents.  For example, `<html lang="{{ '{' }}{ LANGUAGE_CODE }}">` in
the template will be rendered as `<html lang="de-de">` in a German
localization.

Magic!

[Closes issue #3][gh-3].

[gh-3]: http://github.com/mikewest/static_gettext/issues#issue/3
