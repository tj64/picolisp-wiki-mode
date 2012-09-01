picolisp-wiki-mode
==================

*GNU Emacs major mode* for editing **PicoLisp-Wiki** files

## Commentary: ##

*picolisp-wiki-mode* is a major mode for editing text files for
*PicoLisp-Wiki* in GNU Emacs. picolisp-wiki-mode is free software,
licensed under the GNU GPL.

## Dependencies: ##

picolisp-wiki-mode requires easymenu, a standard package since GNU Emacs
19 and XEmacs 19, which provides a uniform interface for creating
menus in GNU Emacs and XEmacs.

## Installation: ##

Make sure to place `picolisp-wiki-mode.el` somewhere in the
load-path and add the following lines to your `.emacs` file to
associate picolisp-wiki-mode with `.text` files:


    (autoload 'picolisp-wiki-mode "picolisp-wiki-mode"
       "Major mode for editing Picolisp-Wiki files" t)
    (setq auto-mode-alist
       (cons '("\\.text" . picolisp-wiki-mode) auto-mode-alist))  


There is no consensus on an official file extension so change `.text` to
`.plw`, `.lw`, `.lwik`, or whatever you call your picolisp-wiki files.

## Customization: ##

Although no configuration is *necessary* there are a few things
that can be customized.  The `M-x customize-mode` command
provides an interface to all of the possible customizations.

## Usage: ##

Keybindings for inserting are grouped by prefixes based on their
function. For example, commands inserting links and lists begin with
`C-c C-l`, those inserting floating content with `C-c C-f`, all other
inserting commands with `C-c C-c`. The primary commands in each group
will are described below. You can obtain a list of all keybindings by
pressing `C-c C-h`.

    ;; Element insertion
    "\C-c\C-l n" Insert Internal Link
    "\C-c\C-l x" Insert External Link
    "\C-c\C-l u" Insert Unordered List
    "\C-c\C-l o" Insert Ordered List
    "\C-c\C-l i" Insert List Item
    "\C-c\C-f l" Insert Left-Floating-Content
    "\C-c\C-f n" Insert Non-Floating Content
    "\C-c\C-f r" Insert Right-Floating-Content
    "\C-c\C-c k" Insert Line Breaks
    "\C-c\C-c 1" Insert Header 1
    "\C-c\C-c 2" Insert Header 2
    "\C-c\C-c 3" Insert Header 3
    "\C-c\C-c 4" Insert Header 4
    "\C-c\C-c 5" Insert Header 5
    "\C-c\C-c 6" Insert Header 6
    "\C-c\C-c b" Insert Bold
    "\C-c\C-c i" Insert Italic
    "\C-c\C-c u" Insert Underlined
    "\C-c\C-c p" Insert Pre Block
    "\C-c\C-c c" Insert Comment
    "\C-c\C-c -" Insert Horizontal Rule (hr)
    ;; Visibility cycling
    "<tab>" Picolisp Wiki Cycle
    "<S-iso-lefttab>" Picolisp Wiki Shifttab
    ;; Header navigation
    "C-M-n" Outline Next Visible Heading
    "C-M-p" Outline Previous Visible Heading
    "C-M-f" Outline Forward Same Level
    "C-M-b" Outline Backward Same Level
    "C-M-u" Outline Up Heading

Many of the commands described above behave differently depending on
whether Transient Mark mode is enabled or not.  When it makes sense,
if Transient Mark mode is on and a region is active, the command
applies to the text in the region (e.g., `C-c C-c b` makes the region
bold).  For users who prefer to work outside of Transient Mark mode,
in Emacs 22 it can be enabled temporarily by pressing `C-SPC C-SPC`.

## Outline Navigation: ##

picolisp-wiki-mode supports *outline-minor-mode* as well as
*org-mode-style visibility cycling* for PicoLisp-Wikli-style headers.
There are two types of visibility cycling: Pressing `S-TAB` cycles
globally between the table of contents view (headers only), outline
view (top-level headers only), and the full document view. Pressing
`TAB` while the point is at a header will cycle through levels of
visibility for the subtree: completely folded, visible children,
and fully visible. 

  * Outline Navigation:

    Navigation between headings is possible using `outline-mode`.
    Use `C-M-n` and `C-M-p` to move between the next and previous
    visible headings.  Similarly, `C-M-f` and `C-M-b` move to the
    next and previous visible headings at the same level as the one
    at the point.  Finally, `C-M-u` will move up to a lower-level
    (more inclusive) visible heading.

FIXME: different header levels are not yet recognized by the outine
commands.

## Acknowledgments: ##

picolisp-wiki-mode is based on `markdown.el` (available from ELPA).
It has benefited greatly from the efforts of the following people:

  * Thorsten Jolitz tjolitz [at] gmail [dot] com

## Bugs: ##

picolisp-wiki-mode is developed and tested primarily using GNU Emacs
24, compatibility with earlier Emacsen is no priority. For bugs and
todo's, see the `HISTORY.org` file in the
[github-repo](https://github.com/tj64/picolisp-wiki-mode).

If you find any bugs in picolisp-wiki-mode, please construct a test case
or a patch and email me at tjolitz [at] gmail [dot] com.

## History: ##

picolisp-wiki-mode was written and is maintained by Thorsten Joltiz.
The *first version (0.9)* was released on `Sept 01, 2012`. For further
information see the `HISTORY.org` file in the
[github-repo](https://github.com/tj64/picolisp-wiki-mode).
