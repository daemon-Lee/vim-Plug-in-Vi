# Cài đặt Plus-in Vim thuần bằng tay
Mặc định, thư mục `~/.vim` sẽ không có cấu trúc để lưu trữ Plug-in, chúng ta sẽ tạo các thư mục lưu trữ tên là `my-plusins` hoặc bất kỳ tên nào bạn muốn.
```bash
$ mkdir -p ~/.vim/pack/my-plugins
```
Sau đó thêm các plugin muốn cài vào thư mục đó, nó sẽ load tự động khi mở vim lên.

Ví dụ khi cài NERDTree ( Sidebar chọn file cho Vim ), ta thực hiện:
```bash
$ git clone --depth 1 \
  https://github.com/preservim/nerdtree.git \
  ~/.vim/plugged/nerdtree
```
Nó có nghĩa là: clone plugin vào thư mục '~/.vim/pack/vendor/start/' với tên 'nerdtree'

## Tham khảo
https://shapeshed.com/vim-packages/
