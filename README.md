# my-vimrc

<h2> Requirement </h2> 
https://github.com/VundleVim/Vundle.vim

https://github.com/junegunn/vim-plug

My vimrc configuration 

```vimrc
call plug#begin()
Plug 'mattn/emmet-vim'
Plug 'mhartington/oceanic-next'
Plug 'vim-airline/vim-airline'
Plug 'vim-airline/vim-airline-themes'
Plug 'jcherven/jummidark.vim'
Plug 'neoclide/coc.nvim', {'branch': 'release'}
Plug 'unegunn/fzf', { 'do': { -> fzf#install() } }
Plug 'jremmen/vim-ripgrep'
Plug 'preservim/nerdtree'
Plug 'ryanoasis/vim-devicons'
Plug 'metakirby5/codi.vim'
Plug 'preservim/nerdcommenter'
Plug 'tpope/vim-surround'
Plug 'wfxr/minimap.vim'
Plug 'Valloric/YouCompleteMe'
Plug 'jiangmiao/auto-pairs'

" Use release branch (recommended)
"Plug 'neoclide/coc.nvim', {'branch': 'release'}

" Or build from source code by using yarn: https://yarnpkg.com
"Plug 'neoclide/coc.nvim', {'branch': 'master', 'do': 'yarn install --frozen-lockfile'}

call plug#end()

colorscheme OceanicNext
set encoding=UTF-8
set guifont=Cousine\ Nerd\ Font,\ Regular
nmap <F6> :NERDTreeToggle<CR>
map <C-Up> :m -2<CR>
map <C-k> :m -2<CR>
map <C-Down> :m +1<CR>
map <C-j> :m +1<CR>
nnoremap d "_d
nnoremap c d
nnoremap C D
vnoremap c d
nnoremap x "_x
nmap <C-_>   <Plug>NERDCommenterToggle
vmap <C-_>   <Plug>NERDCommenterToggle<CR>gv

"set relativenumber
set number
set ignorecase
runtime macros/matchit.vim

let g:minimap_width = 15
let g:minimap_auto_start = 1
let g:minimap_auto_start_win_enter = 1
hi MinimapCurrentLine ctermfg=Green guifg=#50FA7B guibg=#32302f
let g:minimap_cursor_color = 'MinimapCurrentLine'


inoremap " ""<left>
inoremap ' ''<left>
inoremap ( ()<left>
inoremap [ []<left>
inoremap { {}<left>
inoremap {<CR> {<CR>}<ESC>O
inoremap {;<CR> {<CR>};<ESC>O

let MY_YCM_HIGHLIGHT_GROUP = {
      \   'typeParameter': 'PreProc',
      \   'parameter': 'Normal',
      \   'variable': 'Normal',
      \   'property': 'Normal',
      \   'enumMember': 'Normal',
      \   'event': 'Special',
      \   'member': 'Normal',
      \   'method': 'Normal',
      \   'class': 'Special',
      \   'namespace': 'Special',
      \ }

for tokenType in keys( MY_YCM_HIGHLIGHT_GROUP )
  call prop_type_add( 'YCM_HL_' . tokenType,
		    \ { 'highlight': MY_YCM_HIGHLIGHT_GROUP[ tokenType ] } )
endfor

"-----------------------------------------------------------------
set nocompatible              " required
filetype off                  " required

" set the runtime path to include Vundle and initialize
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()

" alternatively, pass a path where Vundle should install plugins
"call vundle#begin('~/some/path/here')

" let Vundle manage Vundle, required
Plugin 'gmarik/Vundle.vim'

" add all your plugins here (note older versions of Vundle
" used Bundle instead of Plugin)
Plugin 'Valloric/YouCompleteMe'
"Plugin 'ycm-core/YouCompleteMe'

" ...

" All of your Plugins must be added before the following line
call vundle#end()            " required
filetype plugin indent on    " required
```
