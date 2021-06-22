# Tùy chỉnh Vim cơ bản

Mặc định, file config của vim sẽ nằm ở `~/.vimrc` trong một số trường hợp nó có thể ở `/etc/vim/vimrc` hoặc `/etc/vimrc`.
Hoặc nếu file không tồn tại, bạn hãy tạo file mới bằng lệnh

```bash
$ touch ~/.vimrc
```

sau đó bạn mở file lên theo lệnh
```bash
$ vim ~/.vimrc
```
Chuyển sang **INSERT MODE** và thêm các config như sau:
```bash
" Bật highlight cú pháp cho một loại file (như .py, .cpp, .xml)
syntax enable
syntax on

" Hiện số thứ tự của dòng
set number

" Không hiện số thứ tự của dòng
set nonumber

" Hiện số thứ tự theo cách relative
" Dòng hiện tại đánh số 0, dòng trên và dòng dưới là 1, 
" và cứ thế đối với các dòng khác
set relativenumber

" Hiện số thứ tự theo cách hybrid
" Dòng hiện tại đánh số là số dòng thực tế, 
" dòng trên và dòng dưới là 1, và cứ thế đối với các dòng khác
set number relativenumber

" Chỉnh 4 space mỗi tab
set tabstop=4

" Chỉnh 4 space mỗi indent
set shiftwidth=4

" Sử dụng space character thay tab character khi nhấn Tab
set expandtab

" Tự động indent khi xuống hàng
set autoindent

" Sử dụng clipboard hệ thống thay buffer của vim
set clipboard=unnamedplus

" Chỉnh độ delay (ms) giữa lần chuyển chế độ
set ttimeoutlen=50

" Highlight dòng hiện tại
set cursorline
```
