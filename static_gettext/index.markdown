---
title:      "`static_gettext`: Localization for Static Documents"
layout:     static_gettext
bodyclass:  homepage
seo:
    desc:     "`static_gettext` is a tiny internationalization framework for static documents (HTML or otherwise)."
    keywords: "gettext, static documents, localization, l10n, internationalization, i18n"
feed:   
    url:    /static_gettext/atom.xml
    title:  "`static_gettext`: Changelog"
---
`static_gettext` is an internationalization framework for static, plaintext
documents and templates.  It's geared towards straightforward translation
of static websites, but can be easily used for any set of files you'd like
to translate as a group.

<img src="/static_gettext/workflow.png" width="565" height="380" alt="static_gettext in a nutshell">

Implemented as a thin wrapper around the GNU [gettext][] project,
`static_gettext` produces standard _message files_ that any translator can
easily work with.  After translation, these can be used to generate
localizations for your world-wide audience.

[gettext]:  http://www.gnu.org/software/gettext/

Workflow
--------

*   Install the script by copying the latest stable version of
    `static_gettext.py` somewhere useful (I'd suggest `~/bin` or
    `/usr/local/bin`):

        curl http://github.com/mikewest/static_gettext/raw/v0.13/static_gettext.py > /usr/local/bin/static_gettext.py
    
*   **Markup translatable strings** in your documents by wrapping them
    in `{{ '{' }}% blocktrans %}...{{ '{' }}% endblocktrans %}` tags.
    This should feel familar if you've ever worked with Django's i18n
    engine.
    
    For example:
    
        <h1>Hello, world!</h1>
    
    Would be marked up as:
    
        <h1>{{ '{' }}% blocktrans %}Hello, world!{{ '{' }}% endblocktrans %}</h1>
    
    And so on...
    
*   **Extract those strings into _message files_** by pointing the `static_gettext`
    script to your source files, telling it which languages you'll be localizing
    your documents into, and to a directory into which the message files
    ought be written:

        static_gettext.py --make-messages --languages LANG_1,LANG_2,LANG_3,... --input=/path/to/source/files --locale=/path/to/locale/files

    With that command, all files under `/path/to/source/files` will be read in,
    and a single directory per target language will be generated under
    `/path/to/locale/files`.  You'll end up with `.po` files for each:

        /path/to/locale/files/en_US/LC_MESSAGES/messages.po
        /path/to/locale/files/de_DE/LC_MESSAGES/messages.po
        ...
        /path/to/locale/files/LANG_N/LC_MESSAGES/messages.po

    These _message files_ contain all translatable strings found in your source
    documents, and maps each to a target-language translation.

*   **Translate the message files**: In each message file, you'll see a list of
    key/value pairs:

        #: src/index.html:4
        msgid "Hello, world!"
        msgstr ""

    Your job is straightforward: add the proper translation as the `msgstr` component
    of the pair:

        #: src/index.html:4
        msgid "Hello, world!"
        msgstr "Hallo Welt!"

    Easy!

*   **Build localized versions of your documents** by pointing the script at
    your source files, the target languages, the message file root, and a directory
    into which the localizations ought be written:

        static_gettext.py --build --languages LANG_1,LANG_2,LANG_3,... --input=/path/to/source/files --locale=/path/to/locale/files --output=/path/to/output/files

    A subdirectory of `/path/to/output/files` will be created for each target
    language, and each file inside `/path/to/source/files` will be copied over
    with translatable strings replaced with the target language version:

        /path/to/output/files/en_US/index.html:

            <h1>Hello, world!</h1>

        /path/to/output/files/de_DE/index.html:

            <h1>Hallo Welt!</h1>

The [example project][example] you'll find in the [GitHub repository][example]
shows the recommend project layout: everything in a single tree, with source
files under `./src`, message files under `./locale`, and built localizations
under `./build`.  Those serve as the defaults for the `--input`, `--output`,
and `--locale` arguments.

[example]:  http://github.com/mikewest/static_gettext/tree/master/example/

Changelog
---------

<ul>
{% for post in site.categories.static_gettext: %}
  <li><strong>v{{ post.version }} ({{ post.date | date: "%Y-%m-%d" }})</strong>: {{ post.content }}</li>
{% endfor %}
</ul>

