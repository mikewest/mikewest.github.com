---
title:  "VimRoom"
layout: default
seo:
    desc:     "VimRoom is WriteRoom, implemented inside Vim (not gVim.  Vim.)."
    keywords: "vim, vimroom, writeroom, distraction free, writing, plugin"
feed:   
    url:    /vimroom/atom.xml
    title:  "VimRoom: Changelog"
---
VimRoom
=======

<ul class="actions">
  <li><a href="http://github.com/mikewest/vimroom/tarball/v0.4" class="cta">Download current version (v0.4)</a></li> 
  <li><a href="http://github.com/mikewest/vimroom" class="cta">Source on GitHub</a></li> 
</ul>

I do most of my writing in Vim, because I'm a big nerd.  It does most of what
I want a writing environment to do, but I miss some of the "[distraction
free"][df] features of the quite exceptional [WriteRoom][].  Fullscreening
Vim means that text ends up flat up against the left side of my monitor, but
I'd much prefer it to be centered.  I'd also like a little of the visual
clutter to fade away.  In other words, instead of this:

<img src="./without-vimroom.jpg" width="600" height="361" alt="Screenshot of Vim, without VimRoom active">

I'd like to work in this:

<img src="./with-vimroom.jpg" width="600" height="361" alt="Screenshot of vim, with VimRoom active">

Some of this is possible with [MacVim][], but I'd rather do as much as
possible in a platform-independent way.  So, command-line Vim it is.

[df]:         http://www.kungfugrippe.com/post/1169153343/only-you
[WriteRoom]:  http://www.hogbaysoftware.com/products/writeroom
[MacVim]:     http://code.google.com/p/macvim/

Installation
------------

I think the best way to install Vim plugins is via Tim Pope's [Pathogen][].  Using that plugin, you can simply clone the VimRoom repository into your `bundles` directory, and you're done.

Without Pathogen, installation is almost as trivial: simply copy `./plugins/vimroom.vim` from the repository into your `plugins` directory.  That's it!

[Pathogen]: http://www.vim.org/scripts/script.php?script_id=2332

Configuration
-------------

By default, VimRoom binds `<Leader>V` to `<Plug>VimroomToggle`, and sets up an 80 column workspace with at least 5 columns of space on either side (it doesn't help at all to have single-column sidebars, you see), and 3 lines of space above and below.  It assumes a black background when hiding visual distractions.  As of v0.4, VimRoom also sets up a `:VimroomToggle` command that has the same effect.

Changing any of these assumptions is a simple matter of setting variables in your `.vimrc`.

*   `g:vimroom_width` is the width of your workspace.
*   `g:vimroom_min_sidebar_width` is the minimum sidebar width.  This will automatically expand to take up all the free space left after setting the main workspace window to `g:vimroom_width` columns.
*   `g:vimroom_sidebar_height` sets the height of the upper and lower "sidebars."  If you don't want vertical padding, set this to 0.
*   `g:vimroom_background` is the background color to be used for hiding elements.  Set this to your terminal's background color ("white", "black", etc.)
*   `g:vimroom_scrolloff` specifies how many lines of text ought appear before and after the cursor.  This defaults to 999, which centers the cursor on the screen.

You can bind the `<Plug>VimroomToggle` function to any key combination you like via the usual mechanisms.  For example:

    nnoremap <silent> <Leader>mz <Plug>VimroomToggle

Would bind the function to `<Leader>mz`.  Trivial, right?

And that's it!

Changelog
---------

<ul>
{% for post in site.categories.vimroom %}
  <li><strong>v{{ post.version }} ({{ post.date | date: "%Y-%m-%d" }})</strong>: {{ post.content }}</li>
{% endfor %}
</ul>
