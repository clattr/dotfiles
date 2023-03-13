"  file: ~/.vimrc
" a comment starts with a double quotation mark
" this .vimrc should work on macOS and Linux
" macOS and language specifics are marked

" begin variable definitions
" set variables acc to your situation

" default working directory 
let DOCDIR = "/Users/MYUSERNAME/texte"

" my tmp/backup directory 
let MYTMP = "/Users/MYUSERNAME/tmp/vim"

" see abbreviations below
let FIRSTNAME = "Vorname"
let SURNAME = "Nachname"

" end variable definitions


" leader , see keybindings below
let mapleader = ","

" syntax highlighting on/off
" :syntax enable
syntax off

" forget vi
set nocompatible

" get rid of the startup message
set shortmess+=I

" character encoding
set encoding=utf-8

" be case insensitive while searching
set ignorecase

" but be case sensitive when searching with uppercase
set smartcase

" hilight search results
" turn off hilighted results with F7, see keybindings below
set hlsearch

" start search immediately, show intermediate results
set incsearch

" set this to prevent search from wrapping from bottom to top
" espec. if you often search in ranges like .,$ (current line to end)
set nowrapscan

" show the mode vim is in
set showmode

" show ruler
set ruler

" dont'beep, just visual
set visualbell

" tabstops
set tabstop=4
set softtabstop=4
set shiftwidth=4

" tabs become spaces
set expandtab
set smarttab

" line width andline wrapping
set textwidth=90

" wrap on/off if line exceeds textwidth
" set nowrap
set wrap

" status line
" set statusline=%F%m%r%h%w___[%{&ff}]___gesamt:%L%y[%p%%]___Zeile:%05l___Spalte:%04v
set statusline=%F%m%r%h%w___[%{&ff}]___total:%L%y[%p%%]___line:%05l___column:%04v
" always a status line
set laststatus=2


" matching parenthesis
" dont't show matching parenthesis
" meaningless in macOS, might be relevant for Linux
" set noshowmatch
" tenth of secondes to show matching parenthesis
" set matchtime=10
" necessary and sufficient for macOS
" don't load plugin for showing matching parenthesis
let loaded_matchparen = 1

" change directory for tmp swp files
" the . concatenates 2 strings, here the command arguments 
exe "set backupdir=" . MYTMP
exe "set directory=" . MYTMP

" Color
" highlight current line (cursorline)
set cul

" adjust color of current line
hi CursorLine term=none cterm=none ctermbg=254

" Visual term=reverse ctermbg=216 guibg=LightGrey
hi Visual term=reverse ctermbg=158 guibg=LightGrey


" Assign default files to buffers
" examples
" exe "badd " . DOCDIR . "/mylog.txt"
" exe "badd " . DOCDIR . "/vim.txt"
" :badd $HOME/.vimrc


" abbreviations start here
" ========================
" qq as prefix for abbreviations works for German
" might be changed for English or other languages
ia qqdsm Dear Sir or Madam
"ia qqsgdh Sehr geehrte Damen und Herren,
ia qqys Yours sincerely
"ia qqmfg Mit freundlichen Grüßen
ia qqrem <!----><Esc><Left><Left>
ia qq2 ²
ia qq3 ³
exe "ia qqme " . FIRSTNAME . " " . SURNAME

" internet time stamp RFC 3339: 2011-07-19-T20:36:53+02:00
" man 3 strftime for variables
ia qqstamp <esc>:silent r! date '+\%d.\%m.\%Y-\%H:\%M:\%S'<cr><s-a>

" date/time in format: 2023-03-13-T16:49:55-CET 
" set TZ acc to your location
ia qqdate <esc>:silent r! TZ=Europe/Berlin date '+\%Y-\%m-\%d-T\%H:\%M:\%S-\%Z'<cr><s-a>

" end of abbreviations


" keybindings start here
" ======================

" leader defintion see beginning of file

" for special characters always press
" <CTRL-K> <special-character><special-character>
" example: <CTRL-K><ALT-ß><ALT-ß>
" results in \

" <s-   Shift
" <c-   Control
" for <Option> i.e. <m- you also have to sue the <crl-k> mojo
" <m-   Meta/Alt/Option
" <d-   Command (Mac only)

" F2: show difference between current and saved version of file
:noremap <F2> <esc>:w !diff -c % -<cr>

" F3: paste clipboard [only OS X macOS]
:noremap <F3> <esc>>:r !pbpaste<cr>

" F4: delete content of current buffer
:noremap <F4> <esc>gg0d<s-g><esc>        

" F5: save session/workspace
:noremap <F5> <esc>:mksession! ~/.vim_session<cr>

" F6: restore session
:noremap <F6> <esc>:source ~/.vim_session<cr>

" F7: turn off highlighted search results
:noremap <F7> <esc>:nohlsearch<cr>        

" F8: toggle spell checking on/off
:noremap <F8> <esc>:set invspell<cr>        


" moving around in normal mode
" ------------

" go to first non blank char on line (macOS / German)
:nnoremap ö ^

" go to end of line (macOS / German)
:nnoremap ä $

" got to middle of the line (macOS / German)
:nnoremap ü :call cursor(0, len(getline('.'))/2)<cr> 

" jump forward in jump list, replaces CTRL-]
:nnoremap <leader>0 <C-]>


" moving around in insert mode
" ------------
" go to end of line æ <opt>ä (macOS / German)
:inoremap æ <esc>A

" go to first non blank char on line œ is <opt>ö (macOS / German)
:inoremap œ <esc>^i


" Managing tab pages
" ----------

" new tabpage
:nnoremap <leader>n :tabnew<cr>

" go to tab page 1
:nnoremap <leader>1 :tabn 1<cr>

" go to tab page 2
:nnoremap <leader>2 :tabn 2<cr>

" go to tab page 3
:nnoremap <leader>3 :tabn 3<cr>

" go to tab page 4
:nnoremap <leader>4 :tabn 4<cr>

" go to tab page 5
:nnoremap <leader>5 :tabn 5<cr>

" go to tab page 6
:nnoremap <leader>6 :tabn 6<cr>

" go to tab page 7
:nnoremap <leader>7 :tabn 7<cr>

" go to tab page 8
:nnoremap <leader>8 :tabn 8<cr>

" move current tab as first in line
:nnoremap <leader>m :tabm0<cr>

" move current tab as last in line
:nnoremap <leader>l :tabm<cr>

" close tab
:nnoremap <leader>x :tabclose!<cr>


" Managing windows
" ----------------

" split horizontally 
:nnoremap <leader>z <c-w>s

" split horizontally, new window, new buffer
:nnoremap <leader>h <c-w>n

" split vertically
:nnoremap <leader>v <c-w>v

" go to top window (or top left/right)
:nnoremap <leader>t <c-w>t

" go to previous window
:nnoremap <leader>p <c-w>p

" go to bottom window (or top left/right)
:nnoremap <leader>b <c-w>b

" go to window below
:nnoremap <leader>j <c-w>j

" go to window above
:nnoremap <leader>k <c-w>k

" close current window
:nnoremap <leader>w <c-w>c



" Vim like nvalt
" --------------
" imitating basic nvalt https://brettterpstra.com/projects/nvalt/
" by using quickfix ( special mode to speedup the edit-compile-edit cycle)
" Idea: search for a term in files of your directory of texts
"       select a file from the list of search results, edit ...
"       optional: select a different file from list ... 
"
" workflow: invoke with <leader>o
"            search term with <leader>s
"            browse in result list with
"                <leader>g to next file or
"                <leader>q to previuos file
"                select file with <enter>
"            edit file, go to next file ...
"            clear result list with <leader>u
"            close quickfix mode 

" invoke with <leader>o
:nnoremap <leader>o :botright cope 20<cr><esc>:exe "cd " . DOCDIR<cr><esc>

" show files in current directory
:nnoremap <leader>f :!ls -al\|less<cr>

" search as in nvalt, show results in window (see cope)
:nnoremap <leader>s <C-W>b<esc>:vimgrep //j *.*<left><left><left><left><left><left>

" jump to next search result in quickfix window 
:nnoremap <leader>g <esc>:cn<cr><esc>

" jump to previous search result in quickfix window 
:nnoremap <leader>q <esc>:cp<cr><esc>

" clear search result list in quickfix window
:nnoremap <leader>u <esc>:cex[]<cr><esc>

" switch to nvalt docs directory
:nnoremap <leader>d <esc>:exe "cd " . DOCDIR<cr><esc>

" close quickfix window
:nnoremap <leader>c :ccl<cr><esc>


" Editing
" --------------
" <option> <key> shortcuts for editing
" <CTRL-K><ALT-ß><ALT-ß>

" <CTRL-K><ALT-+><ALT-+>
" if LHS and RHS are both special characters use the
" <ctlr-k> ...  twice!
" also wenn <alt-ß> im insert moder der backslash \ werden soll:
" :inoremap <CTRL-K><CTRL-K><ALT-ß> \

" option-ß is \ (macOS / German)
:inoremap ¿ \

" <option-+> is ~ (macOS / German)
:inoremap ± ~

" <option-r> replace text in current buffer (g globally, c confirm)
"  (macOS / German)
:nnoremap ® :%s///gc<left><left><left><left>

" open file explorer window 
:nnoremap <leader>e <esc>:Explore<cr><esc>


" =================
" end of keybindings


" end of .vimrc


