# Cài đặt Vim bằng các gói quản lý Plugin

Có nhiều gói quản lý Plugin như: Bundle, Vim-Plug, Pathogen,... vân vân và mây mây.
- [Vim-Plug](#Vim-Plug)
- [Vundle](#Vundle)

## Vim-Plug
Khá nhiều đặc điểm hay
- Cú pháp gọn, dễ nhớ
- Khá nhanh
- Cài đặt cũng dễ

Cách cài đặt:
```bash
  $ curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```
Sử dụng:
1. Chúng ta mở `~/.vimrc` lên
2. Kiếm đoạn nào trống trống ấy :))
3. Rồi thêm phần mở đầu `call plug#begin()`
4. Bên dưới ta ghi các Plugin muốn cái theo cú pháp `Plug "xxxx"` (Với xxxx là đuôi của đường dẫn github tới plugin cần cài)
5. Sau khi thêm, ta kết thúc phần cài đặt plugin bằng cách thêm `call plug#end()` vào cuối

Ví dụ:
```bash
" Gọi đầu tiên
call plug#begin('~/.vim/plugged')

" Cài plugin Shorthand notation;  https://github.com/junegunn/vim-easy-align
Plug 'junegunn/vim-easy-align'

" Hoặc sử dụng đường dẫn trực tiếp luôn
Plug 'https://github.com/junegunn/vim-github-dashboard.git'

" Cài đặt nhiều Plugin bằng cách sử |
Plug 'SirVer/ultisnips' | Plug 'honza/vim-snippets'

" Loading sau khi cài Plugin. 
Plug 'scrooloose/nerdtree', { 'on':  'NERDTreeToggle' }
Plug 'tpope/vim-fireplace', { 'for': 'clojure' }

" Cài plugin với branch tùy chọn
Plug 'rdnetto/YCM-Generator', { 'branch': 'stable' }

" Cài plugin bằng tag released
Plug 'fatih/vim-go', { 'tag': '*' }

" Tùy chọn khi cài plugin
Plug 'nsf/gocode', { 'tag': 'v.20150303', 'rtp': 'vim' }

" Cài plugin từ bên ngoài ~/.vim/plugged với post-update
Plug 'junegunn/fzf', { 'dir': '~/.fzf', 'do': './install --all' }

" Kết thúc việc cài plugin
call plug#end()
```
Sau đó save và reload bằng lệnh `:source %` hoặc ta thoát mở lại. Sau đó gõ câu lệnh `:PlugInstall` để cài đặc các plugin nhé :D

Ngoài ra còn một số lệnh như:
- PlugUpdate: cập nhật các Plugin đến phiên bản mới nhất
- PlugClean: Xóa các Plugin đã cài nhưng không có trong config
- PlugUpgrade: Tự update chính Vim-Plug
- PlugStatus: Xem trạng thái của các Plugin
- PlugSnapshot: Tạo bản backup phòng trường hợp bị mất

## [Vundle](https://github.com/VundleVim/Vundle.vim)
1. Cài đặt Vundle:
```bash
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```
2. Configure Plugins:
Cho phần cài đặt cấu hình vào đầu file `.vimrc` để dùng **Vundle**. Dưới đây mình cùng đến với một ví dụ.
```bash
set nocompatible              " be iMproved, required
filetype off                  " required

" set the runtime path to include Vundle and initialize
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
" alternatively, pass a path where Vundle should install plugins
"call vundle#begin('~/some/path/here')

" let Vundle manage Vundle, required
Plugin 'VundleVim/Vundle.vim'

" The following are examples of different formats supported.
" Keep Plugin commands between vundle#begin/end.
" plugin on GitHub repo
Plugin 'tpope/vim-fugitive'
" plugin from http://vim-scripts.org/vim/scripts.html
" Plugin 'L9'
" Git plugin not hosted on GitHub
Plugin 'git://git.wincent.com/command-t.git'
" git repos on your local machine (i.e. when working on your own plugin)
Plugin 'file:///home/gmarik/path/to/plugin'
" The sparkup vim script is in a subdirectory of this repo called vim.
" Pass the path to set the runtimepath properly.
Plugin 'rstacruz/sparkup', {'rtp': 'vim/'}
" Install L9 and avoid a Naming conflict if you've already installed a
" different version somewhere else.
" Plugin 'ascenator/L9', {'name': 'newL9'}

" All of your Plugins must be added before the following line
call vundle#end()            " required
filetype plugin indent on    " required
" To ignore plugin indent changes, instead use:
"filetype plugin on
"
" Brief help
" :PluginList       - lists configured plugins
" :PluginInstall    - installs plugins; append `!` to update or just :PluginUpdate
" :PluginSearch foo - searches for foo; append `!` to refresh local cache
" :PluginClean      - confirms removal of unused plugins; append `!` to auto-approve removal
"
" see :h vundle for more details or wiki for FAQ
" Put your non-Plugin stuff after this line
```
3. Cài đặt Plugins:
Để cài đặt, chúng ta khởi chạy `vim` và gõ lệnh `:PluginInstall`

Hoặc cài đặt thông qua command line: `vim +PluginInstall +qall`
