# How to do stuff in Vim

Some resources
-   [Everyday Vim – A Basic Vim Commands Cheat Sheet](https://spin.atomicobject.com/2016/04/19/vim-commands-cheat-sheet/)
-   [Tab navigation](https://vim.fandom.com/wiki/Alternative_tab_navigation)
-   [vim-colorschemes](https://github.com/flazz/vim-colorschemes)

Stuff I know
```
## select visually and replace
select visually: v or shift+v or ctrl+shift+v
insert: shift+i
finish: esc

## indentation

ctrl + t // indent forward 
ctrl + d // indent backwards

## split pane
Split vertically: 
ctrl + w followed by v

navigate: 
ctrl + w followed by l to go to the right pane
ctrl + w followed by h to go to the left pane

If you are working with two panes, press ctrl + w twice to jump to the other pane.

split vertically: 
ctrl + w followed by s

navigate: 
ctrl + w followed by k to go up
ctrl + w followed by j to go down

Control the current workspace
Increase or decrease width: 
ctrl + w followed by shift + > or < // sucks! increases or decreases once. repetition of the whole command is needed

Increase or decrease height:
ctrl + w followed by + or -

Equal height of top and bottom pane:
ctrl + w followed by =


## Code block
Visual selection of code in vertical and horizontal direction: ctrl + shift + v

comment a code block: ?
Move one code block down or up: { to go up and } to go down

## Optimise for a language
-   Optimise for C++?
-   Optimise for Python?
-   Optimise for Html?
-   For other type of files?

## Run terminal commands while working in vim
ESC followed by :! <command>
```

My `vimrc`
```
" Uniform encoding throughout so that the characters typed in vim don't look
" garbage somewhere else.
set encoding=UTF-8

" Just so you know where you are in the file.
set number
set ruler
set cursorline

" Show the command you are typing or it's action in the bottom bar.
set showcmd

" Type a command starting with : and press tab to autocomplete.
set wildmenu

" Highlight the search results in the file.
set showmatch

" Highlight the matched characters as you type.
set incsearch

" Keep the last search results highlighted.
set hlsearch

" Optimisation for different file types.
syntax enable
filetype indent on

" I would like it to be different for different file types but I don't know how to do it.
set tabstop=2
set expandtab
set softtabstop=2
set shiftwidth=2

" Copy from one Vim window with yy to global clipboard and past anywhere. 
set clipboard=unnamed

" Tab navigation
nnoremap th  :tabfirst<CR>
nnoremap tk  :tabnext<CR>
nnoremap tj  :tabprev<CR>
nnoremap tl  :tablast<CR>
```

