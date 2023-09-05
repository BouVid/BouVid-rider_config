# Rider Configuration

## IdeaVim
Below is a Vim configuration file (`.ideavimrc`) with descriptions for each configuration option and key mapping.

```vim
set nu                   " Enable line numbering
set relativenumber        " Enable relative line numbering
set incsearch            " Enable incremental search
set scrolloff=8          " Set the number of lines to keep in view when scrolling

" Plugins
Plug 'preservim/nerdtree'     " Plugin for file tree navigation
Plug 'machakann/vim-highlightedyank'  " Plugin for highlighting yanked text

" Leader Key
let mapleader = " "          " Set the leader key to Space
noremap <Space> <Nop>        " Map Space key to do nothing

" Tabbing
nnoremap <S-l> gt            " Switch to the next tab
vnoremap <S-l> gt            " Switch to the next tab in visual mode
nnoremap <S-h> gT            " Switch to the previous tab
vnoremap <S-h> gT            " Switch to the previous tab in visual mode

" Clipboard Buffer
nnoremap <leader>d "*d       " Delete (cut) to the clipboard
nnoremap <leader>D "*dd      " Delete (cut) the entire line to the clipboard
nnoremap <leader>y "*y       " Yank (copy) to the clipboard
nnoremap <leader>Y "*yy      " Yank (copy) the entire line to the clipboard
nnoremap <leader>p "*p       " Paste from the clipboard
vnoremap <leader>d "*d       " Delete (cut) to the clipboard in visual mode
vnoremap <leader>D "*dd      " Delete (cut) the entire line to the clipboard in visual mode
vnoremap <leader>y "*y       " Yank (copy) to the clipboard in visual mode
vnoremap <leader>Y "*yy      " Yank (copy) the entire line to the clipboard in visual mode
vnoremap <leader>p "*p       " Paste from the clipboard in visual mode

" Terminal
nnoremap <C-t> :action ActivateTerminalToolWindow<CR>  " Open terminal

" Quality of Life
nnoremap <leader>s "ayiw :%s/\<<C-r>a\>/<C-r>a/gI<Left><Left><Left>  " Search and replace in the entire file
nnoremap <leader>r :action RenameElement<CR>            " Rename the current element
nnoremap <leader>= :action ReformatCode<CR>              " Reformat code
nnoremap <leader>q :wq<CR>                               " Save and quit
nnoremap <leader>Q :tabo<CR>                              " Close all other tabs
nnoremap <C-d> <C-d>zz                                   " Scroll down and center
nnoremap <C-o> <C-o>zz                                   " Scroll up and center
nnoremap <C-i> <C-i>zz                                   " Jump forward and center
nnoremap <C-u> <C-u>zz                                   " Jump backward and center

" Commenting
nnoremap gc :action CommentByLineComment<CR>             " Comment/uncomment the current line
vnoremap gc :action CommentByLineComment<CR>             " Comment/uncomment selected lines in visual mode

" Documentation
nnoremap <C-k> :action QuickJavaDoc<CR>                  " Show JavaDoc documentation for the current element

" Navigation
nnoremap <leader>fr :action RecentFiles<CR>              " Open recent files dialog
nnoremap <leader>fg :action GotoFile<CR>                " Go to a specific file
nnoremap <leader>fi :action FindInPath<CR>              " Find text in project
nnoremap <leader>ff :action Find<CR>                    " Find text in current file
nnoremap <leader>e :NERDTreeFocus<CR>                   " Focus on NERDTree file explorer

" Code Completion
inoremap <C-y> :action EditorChooseLookupItem<CR>        " Choose a code completion suggestion

" Go To
nnoremap gr :action ShowUsages<CR>                      " Show usages of the current element
nnoremap gi :action ReSharperGotoImplementation<CR>     " Go to implementation of the current interface or method
nnoremap gd :action GotToDeclaration<CR>                " Go to the declaration of the current element
nnoremap gt :action GotoTest<CR>                        " Go to the test for the current element
nnoremap gD :action GotoTypeDeclaration<CR>             " Go to the type declaration
nnoremap [g :action GotoPreviousError<CR>               " Go to the previous error
nnoremap ]g :action GotoNextError<CR>                   " Go to the next error

" Debugger
nnoremap <leader>b :action ToggleLineBreakpoint<CR>      " Toggle a breakpoint

