# Cài đặt Plus-in Vim thuần bằng tay
Mặc định, thư mục `~/.vim` sẽ không có cấu trúc để lưu trữ Plug-in, chúng ta sẽ tạo các thư mục lưu trữ tên là `my-plusins` hoặc bất kỳ tên nào bạn muốn.
```bash
$ mkdir -p ~/.vim/pack/my-plugins
```
Trong thư mục này, cần thêm một thư mục `start` nữa để giữ các plugin. Vim sẽ chọn bất kỳ gói nào được thêm vào thư mục này và tự động tải các plugin.

Thêm thư mục khác `opt` có thể được tạo để chứa các gói không được tải tự động. Các gói được thêm vào thư mục `opt` có thể được tải bằng cách sử dụng

```bash
:packadd packagename
```
Điều này có thể hữu ích cho việc gỡ lỗi hoặc thêm một plugin đặc biệt.

## Bố cục thư mục

```bash
.vim/pack/my-plugins/start/foobar/plugin/foo.vim    	  " always loaded, defines commands
.vim/pack/my-plugins/start/foobar/plugin/bar.vim    	  " always loaded, defines commands
.vim/pack/my-plugins/start/foobar/autoload/foo.vim  	  " loaded when foo command used
.vim/pack/my-plugins/start/foobar/doc/foo.txt       	  " help for foo.vim
.vim/pack/my-plugins/start/foobar/doc/tags          	  " help tags
.vim/pack/my-plugins/opt/fooextra/plugin/extra.vim  	  " optional plugin, defines commands
.vim/pack/my-plugins/opt/fooextra/autoload/extra.vim      " loaded when extra command used
.vim/pack/my-plugins/opt/fooextra/doc/extra.txt  	  " help for extra.vim
.vim/pack/my-plugins/opt/fooextra/doc/tags  	          " help tags
```
Với `foobar` và `fooextra` là thên các plugins

## Quản lý packages
Chức năng mới trong vim không thêm bất cứ thứ gì để quản lý các plugin; nó chỉ tải chúng. Bạn quản lý plugin như thế nào là tùy thuộc vào bạn.

Ở dạng đơn giản nhất, bạn chỉ có thể di chuyển một plugin vào thư mục `start` và nó sẽ được tải tự động. Bạn quản lý nó như thế nào là tùy thuộc vào bạn.




Ví dụ khi cài NERDTree ( Sidebar chọn file cho Vim ), ta thực hiện:
```bash
$ git clone --depth 1 \
  https://github.com/preservim/nerdtree.git \
  ~/.vim/plugged/nerdtree
```
Nó có nghĩa là: clone plugin vào thư mục '~/.vim/pack/vendor/start/' với tên 'nerdtree'

## Tham khảo
https://shapeshed.com/vim-packages/
