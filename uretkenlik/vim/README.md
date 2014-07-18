# Vim

## Mode

* `i` - insert
* `esc` - command
* `v` - visual

## Command

* `w` - write
* `q` - quit

## Move

```
       ^
       k
 < h       l >
       j
       v
```

* `:80` - Go to line 80
* `80G` - Go to lin 80
* `w` - word >
* `e` - end of the word
* `W` - whole word >
* `b` - word <
* `B` - whole word <
* `$` - end of the line
* `^` - begining of the line with space
* `0` - begining of the line without space
* `gg` - beginging of the file
* `G` - end of the file
* `}` - next paragraph
* `{` - previous paragraph
* `f` - find letter >
* `F` - find letter <
* `ctrl + d` - half of the page v
* `ctrl + f` - full of the page v
* `ctrl + u` - half of the page ^
* `ctrl + b` - full of the page ^
* `M` - middle of the page
* `H` - top of the page
* `L` - last line of the page
* `zt` - curser to stay to top
* `zb` - curser to stay botton
* `zz` - curser to stay middle on the window

## Basic Edit

* `x` - delete >
* `X` - delete <
* `u` - undo
* `dw` - delete word >
* `db` - delete word <
* `cw` - delete word then change mode to insert
* `cd` - delete line then change mode to insert
* `O` - insert line ^
* `o` - insert line v
* `F"ct"` - delete all thing between `"`. You can use `{` or `(` everything you want instead of `"`.
* `ci"` - delete inside. You can use `{` or `(` everything you want instead of `"`.
* `ca"` - delete around. You can use `{` or `(` everything you want instead of `"`.

## Paste Copy

* `p` - paste >
* `P` - paste <
* `y` - copy
* `yw` - copy word
* `yy` - copy line

## Search

* `?regex_search_term` - search term in file <
* `/regex_search_term` - search term in file >
       * `n` >
       * `N` <
* `d/regex_search_term` - delete text from cursor to search term.
* `:set incsearch`
* `:set hlsearch`
* `nohl` - don't highlight search terms

## Replace

* :[range]s[ubstitute]/{pattern}/{string}/[flags] [count]
* range
       * `%` all file
* flags
       * `g` - global
       * `c` - confirm
       * `i` - ignorecase
* `%s/foo/baz/gc` - change all foo to baz with confirm
* `%s//baz/gc` - change all last search term to baz with confirm

## Macro

* `qa` - start to record macro `a`
* `q` - stop to record macro
* `:reg` - list of macro
* `@a` - execute macro a
* `@@` - execute last macro

## Command line

* `:!` - execute shell command
* `:r` - read output of shell command
* `:r ~curl --silent url` - get the source code of url.

## Buffer

* `:ls` - list buffer
* `bn` - next buffer
* `bp` - previous buffer
* `b#` - last buffer
* `bf` - first buffer
* `bd` - delete buffer
* `bd12` - delete 12. buffer

## Window

* `vs filename` - Vertical split
* `s` - horizontal split
* `ctrl + w hjkl` - change window
* `ctrl + W HJKL` - move window
* `ctrl + w >` - resize current window to >
* `ctrl + w <` - resize current window to <
* `ctrl + w +` - rezise current window to ^
* `ctrl + w -` - resize current window to v
* `ctrl + =` - equal current window size


## Tab

* `tabe filename` - new tab
* `gt` - change tab
* `:q` - close tab or window

## Indent

**Normal mode**

* `>>` - add indent
* `<<` - remove indent
* `3>>` - add indent for 3 lines
* `3<<` - remove indent for 3 lines
* `=` - equal indent

**Insert mode**

* `ctrl + t` - add indent
* `ctrl + d` - remove indent

**Settings**

* `set list|nolist`
* `set expandtab|noexpandtab`
* `set shiftwidth=2`
* `set smartindent`
* `set softtabstop`

## Folding

* `zf5j` - new folding 5 line
* `zo|O` - open folding
* `zc|C` - clone folding
* `zd` - delete folding
* `zi` - open or close all folding

**Settings**

* `set fdm:syntax`
* `set fdm:marker` then `set foldmarker={{{,}}}`

## Plugins

* https://github.com/gmarik/Vundle.vim
* https://github.com/altercation/vim-colors-solarized
* https://github.com/majutsushi/tagbar
* https://github.com/scrooloose/nerdtree
* https://github.com/sirver/ultisnips
* https://github.com/airblade/vim-gitgutter
