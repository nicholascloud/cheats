# VIM Cheat Sheet

## Help

- `:h term`: search the help system for `term`

## Navigation

_By character:_

- `#h`: left a particular number of characters, where `#` is a number
- `#l`: right a particular number of characters, where `#` is a number
- `fx`: jump forward to the first occurance of `x`, where `x` is any character
- `#fx`: jump forward to the nth occurance of `x`, where `#` is a number and `x` is any character
- `;`: repeat last character movement
- `,`: repeat last character movement in the opposite direction

_By word:_

- `e`: end of current word (letters, digits, underscores)
- `E`: end of current word (non-whitespace characters)
- `b`: previous word (letters, digits, underscores)
- `B`: previous word (non-whitespace characters)
- `w`: next word (letters, digits, underscores)
- `W`: next word (non-whitespace characters)
- `#w`: forward a given number of words, where `#` is a number

_By line:_

- `h`: left
- `j`: down
- `k`: up
- `l`: right
- `^`: first non-blank character of the line
- `$`: last non-blank character of the line
- `0`: beginning of line
- `gm`: move to the middle of the line (not the middle of the line text, but the middle of coloums visible in the window)
- `#j`: down a particular number of lines, where # is a number
- `#k`: up a particular number of lines, where # is a number

_By paragraph:_

- `{`: beginning of paragraph
- `}`: end of paragraph
- `{` `{` `{`...: continue moving to the beginning of previous paragraphs
- `}` `}` `}`...: continue moving to the end of following paragraphs

_By screen:_

- `H`: first line of the current screen
- `M`: middle line of the current screen
- `L`: last line of the current screen
- `Ctrl+f`: page screen down
- `Ctrl+b`: page screen up
- `Ctrl+d`: page one-half screen down
- `Ctrl+u`: page one-half screen up
- `Ctrl+y`: page one line up
- `Ctrl+e`: page one line down

- `zt`: scroll current line to the top of the screen
- `zz`: scroll current line to the middle of the screen
- `zb`: scroll current line to the (near) bottom of the screen

_By file:_

- `gg`: beginning of the file
- `G`: end of the file
- `:#`: go to line (where # is a number)

_By code:_

- `%`: go to matching braces or parentheses

_By (book)mark:_

- `mx`: mark the cursor position with the letter `x`
- `` `x ``: jump to the exact line and column of marker `x`
- `'x`: jump to the beginning of the line marked by `x`
- `d'x`: delete from cursor to mark `x`
- `` `0 `` - `` `9 ``: mark at last location of the cursor, where `\`0` is most recent (maintained automatically by vim)
- `''`: last position of the cursor (at a mark?)
- `'.`: mark at the last edit
- `:marks`: display a list of marks

__Note:__ Lower-case marks are file specific. Upper case marks are global across files.

## Window Management

- `:new`: create new file and split window horizontally
- `:q`: close window

- `:split`: split window horizontally
- `:vsplit`: split window vertically
- `Ctrl+w s`: split window horizontally
- `Ctrl+w v`: split window vertically
- `Ctrl+w j`: move focus down
- `Ctrl+w k`: move focus up
- `Ctrl+w h`: move focus left
- `Ctrl+w l`: move focus right
- `Ctrl+w w`: cycle window focus counter-clockwise
- `Ctrl+w W`: cycle window focus clockwise
- `Ctrl+w p`: focus previous window
- `Ctrl+w t`: move focus to top-left window
- `Ctrl+w b`: move focus to bottom right window

- `Ctrl+w c`: close window (? doesn't appear to work)
- `Ctrl+w o`: close all windows but current

- `Ctrl+w r`: rotate windows counter-clockwise
- `Ctrl+w R`: rotate windows clockwise
- `Ctrl+w x`: exchange current window with next window
- `Ctrl+w T`: move current window to new tab

## Search and Replace

- `/term`: search forward for term
- `?term`: search backward for term
- `:%s/find/replace/`: search for the first occurance `find` and substitute `replace` on the current line
- `:[x,y] s/find/replace/`: search for the first occurance of `find` and substitute `replace` on lines x - y

- `n`: search again (forwards)
- `N`: search again (backwards)

_Search Flags_

- `g`: search whole document
- `c`: ask for confirmation when replacing a match

## Editing

- `u`: undo operation
- `Ctrl+R`: redo operation
- `yy` or `Y`: copy line
- `p`: paste below cursor
- `P`: paste above cursor
- `cw`: change word
- `#cw`: change a given number of words, where `#` is a number
- `r`: replace character
- `v`: enter visual mode to select text by character
- `V`: enter visual mode to select text by line
- `.`: repeat last edit

_Insert_

- `i`: insert text at the cursor
- `I`: insert text at the beginning of the line
- `a`: append text after cursor
- `o`: insert a blank line _below_ the current line, and enter `insert` mode
- `O`: insert a blank line _above_ the current line, and enter `insert` mode

_Delete_

- `d$`: delete all text from the cursor to the end of the line

## Spellcheck

See: [Vim documentation: spell](http://vimdoc.sourceforge.net/htmldoc/spell.html)

- `:setlocal spell spelllang=en_us`: enable spellcheck for the current session
- `zg`: add misspelled word to spellfile
- `zug`: remove a word from spellfile
- `z=`: suggest alternative spellings for misspelled word

## File System

- `:cd path`: change vim's working dirctory, where `path` is a file system path
- `gf`: open file path under cursor
- `:e filepath`: open a file, where `filepath` is a file system path to a file
- `:e .`: browse the working directory for a file to open
- `:e dirpath`: browse a directory for a file, where `dirpath` is a file system path to a directory

_Directory listing commands_

- `i`: thin, long, wide, or tree listings
- `s`: sort on name, time, or file size
- `r`: reverse sort order
- `gh`: hide or unhide dotfiles
- `<enter>`: open file or directory
- `x`: view file with associated application
- `d`: make directory
- `D`: delete file or directory
- `R`: rename file or directory
- `-`: go up one directory
- `q`: exit browse mode

## Buffer Management

- `:b name`: switch to buffer, where `name` is the name of the file loaded in the buffer
- `:bp`: go to previous buffer
- `:bn`: go to the next buffer
- `:ls`: list all open buffers
- `:b#`: go to a specific buffer, where `#` represents the buffer number (obtained from `:ls`)
- `:bf`: go to first buffer
- `:bl`: go to last buffer
- `:ba`: open a window for every buffer
- `:bd`: deletes the current buffer (close file)

- `Ctrl+w J`: move buffer up one window
- `Ctrl+w K`: move buffer down one window
- `Ctrl+w H`: move buffer left one window
- `Ctrl+w L`: move buffer right one window

## Options

- `:options`: view all available vim options
- `:set`: view all options that differ from default values

## Program

- `Ctrl+z`: suspend VIM and run in background (returns to terminal)
- `fg`: (after suspend) run VIM in the foreground (returns to VIM)
