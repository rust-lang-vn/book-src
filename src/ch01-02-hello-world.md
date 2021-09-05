## Hello, World!

Bây giờ bạn đã cài đặt Rust, hãy viết chương trình Rust đầu tiên của bạn.Truyền thống khi học một ngôn ngữ mới là viết
một chương trình nhỏ in dòng chữ `Hello, world!` ra màn hình, vì vậy chúng ta cũng sẽ làm như vậy ở đây!

> Ghi chú: Cuốn sách này giả định rằng bạn đã biết cơ bản với command line. Rust không đưa ra yêu cầu cụ thể về chỉnh
> sửa hoặc công cụ của bạn hoặc nơi bạn code, vì vậy nếu bạn thích sử dụng môi trường phát triển tích hợp (IDE) thay vì
> command line, hãy sử dụng IDE yêu thích của bạn.

### Tạo thư mục project

Bạn sẽ bắt đầu bằng cách tạo một thư mục để lưu trữ mã Rust của mình. Rust không quan trọng bạn lưu code ở đâu, nhưng
đối với các bài tập và dự án trong cuốn sách này, chúng tôi khuyên bạn nên tạo một thư mục *projects* trong thư mục
chính và giữ tất cả các dự án của bạn ở đó.

Mở một terminal và nhập các lệnh sau để tạo thư mục *projects* và thư mục cho project “Hello, world!” nằm trong thư
mục *projects*.

Cho Linux, macOS, và PowerShell trên Windows, nhập vào:

```console
$ mkdir ~/projects
$ cd ~/projects
$ mkdir hello_world
$ cd hello_world
```

Cho Windows CMD, nhập vào:

```cmd
> mkdir "%USERPROFILE%\projects"
> cd /d "%USERPROFILE%\projects"
> mkdir hello_world
> cd hello_world
```

### Viết và chạy một chương trình Rust

Tiếp theo, tạo một tệp nguồn mới và gọi nó là *main.rs*. Các tệp Rust luôn kết thúc bằng phần mở rộng *.rs*. Nếu bạn
đang sử dụng nhiều từ trong tên tệp của mình, hãy sử dụng dấu gạch dưới để phân tách chúng. Ví dụ: sử dụng
*hello_world.rs* thay vì *helloworld.rs*.

Bây giờ, hãy mở tệp *main.rs* bạn vừa tạo và nhập mã trong Listing 1-1.

<span class="filename">Filename: main.rs</span>

```rust
fn main() {
    println!("Hello, world!");
}
```

<span class="caption">Listing 1-1: Một chương trình in `Hello, world!`</span>

Lưu tệp và quay lại cửa sổ terminal của bạn. Trên Linux hoặc macOS, hãy nhập các lệnh sau để biên dịch và chạy tệp:

```console
$ rustc main.rs
$ ./main
Hello, world!
```

Trên Windows, nhập lệnh `.\main.exe` thay vì `./main`:

```powershell
> rustc main.rs
> .\main.exe
Hello, world!
```

Bất kể hệ điều hành của bạn là gì, chuỗi `Hello, world!` sẽ được in ra trên terminal. Nếu bạn không thấy output này, hãy
quay lại mục [“Troubleshooting”][troubleshooting]<!-- ignore --> của phần Installation để biết cách nhận trợ giúp.

Nếu dòng chữ `Hello, world!` được in, xin chúc mừng! Bạn đã chính thức viết một chương trình Rust. Điều đó khiến bạn trở
thành một lập trình viên Rust — xin chào mừng!

### Cấu trúc của một chương trình Rust

Hãy cùng xem xét chi tiết những gì vừa xảy ra trong chương trình “Hello, world!” của bạn. Đây là phần đầu tiên của câu
đố:

```rust
fn main() {}
```

Các dòng này xác định một hàm trong Rust. Hàm `main` rất đặc biệt: nó luôn là mã đầu tiên chạy trong mọi chương trình
Rust. Dòng đầu tiên khai báo một hàm có tên là `main` không có tham số và không trả về gì. Nếu có các tham số, chúng sẽ
nằm trong dấu ngoặc đơn, `()`.

Ngoài ra, hãy lưu ý rằng thân hàm được bọc trong dấu ngoặc nhọn, `{}`. Rust yêu cầu chúng bao quanh tất cả thân hàm. Bạn
nên đặt dấu ngoặc nhọn mở trên cùng dòng với khai báo hàm, thêm một khoảng trắng ở giữa.

Nếu bạn muốn tuân theo một phong cách chuẩn trong các dự án Rust, bạn có thể sử dụng công cụ định dạng tự động có tên
là `rustfmt` để định dạng mã của bạn theo một phong cách cụ thể. Nhóm Rust đã bao gồm công cụ này với bản phân phối Rust
tiêu chuẩn, giống như `rustc`, vì vậy nó đã được cài đặt trên máy tính của bạn! Kiểm tra tài liệu trực tuyến để biết
thêm chi tiết.

Bên trong hàm `main` là đoạn mã sau:

```rust
    println!("Hello, world!");
```

Dòng này thực hiện tất cả công việc trong chương trình nhỏ này: nó in văn bản ra màn hình. Có bốn chi tiết quan trọng
cần lưu ý ở đây.

Đầu tiên, kiểu Rust là thụt lề với bốn dấu cách, không phải là một tab.

Thứ hai, `println!` gọi một macro Rust. Nếu nó được gọi là một hàm thay vào đó, nó sẽ được nhập là `println` (không có
dấu`!`). Chúng ta sẽ thảo luận chi tiết hơn về macro Rust trong Chương 19. Hiện tại, bạn chỉ cần biết rằng việc sử dụng
dấu `!` có nghĩa là bạn đang gọi một macro thay vì một hàm bình thường và macro không phải lúc nào cũng tuân theo các
quy tắc tương tự như các hàm.

Thứ ba, bạn thấy chuỗi `"Hello, world!"`. Chúng tôi chuyển chuỗi này làm đối số cho `println!`, và chuỗi được in ra màn
hình.

Thứ tư, chúng ta kết thúc dòng bằng dấu chấm phẩy (`;`), cho biết rằng biểu thức này đã kết thúc và biểu thức tiếp theo
đã sẵn sàng để bắt đầu. Hầu hết các dòng mã Rust đều kết thúc bằng dấu chấm phẩy.

### Biên dịch và chạy là các bước riêng biệt

Bạn vừa chạy một chương trình mới được tạo, vì vậy hãy kiểm tra từng bước trong quy trình.

Trước khi chạy chương trình Rust, bạn phải biên dịch nó bằng trình biên dịch Rust bằng cách nhập lệnh `rustc` và chuyển
cho nó tên tệp nguồn của bạn, như sau:

```console
$ rustc main.rs
```

Nếu bạn có nền tảng C hoặc C++, bạn sẽ nhận thấy rằng điều này tương tự như `gcc` hoặc` clang`. Sau khi biên dịch thành
công, Rust xuất ra một tệp thực thi nhị phân.

Trên Linux, macOS và PowerShell trên Windows, bạn có thể xem tệp thực thi bằng cách nhập lệnh `ls` vào trình shell của
mình. Trên Linux và macOS, bạn sẽ thấy hai tệp. Với PowerShell trên Windows, bạn sẽ thấy ba tệp giống nhau mà bạn sẽ
thấy khi sử dụng CMD.

```console
$ ls
main  main.rs
```

Với CMD trên Windows, bạn sẽ nhập như sau:

```cmd
> dir /B %= the /B option says to only show the file names =%
main.exe
main.pdb
main.rs
```

Điều này hiển thị tệp mã nguồn có phần mở rộng *.rs*, tệp thực thi (*main.exe* trên Windows, và *main* trên tất cả các
nền tảng khác) và khi sử dụng Windows, tệp chứa thông tin gỡ lỗi có phần mở rộng *.pdb*. Từ đây, bạn chạy tệp *main*
hoặc *main.exe*, như sau:

```console
$ ./main # or .\main.exe on Windows
```

Nếu *main.rs* là chương trình “Hello, world!”, dòng này sẽ in `Hello, world!` vào terminal của bạn.

Nếu bạn quen thuộc hơn với một ngôn ngữ động (dynamic), chẳng hạn như Ruby, Python hoặc JavaScript, bạn có thể không
quen với việc biên dịch và chạy chương trình dưới dạng các bước riêng biệt. Rust là một ngôn ngữ
*ahead-of-time compiled*, có nghĩa là bạn có thể biên dịch một chương trình và cung cấp chương trình thực thi cho người
khác và họ có thể chạy nó ngay cả khi chưa cài đặt Rust. Nếu bạn cung cấp cho ai đó tệp *.rb*, *.py* hoặc *.js*, họ cần
cài đặt triển khai Ruby, Python hoặc JavaScript (tương ứng). Nhưng trong các ngôn ngữ đó, bạn chỉ cần một lệnh để biên
dịch và chạy chương trình của mình. Mọi thứ đều là sự đánh đổi trong thiết kế ngôn ngữ.

Chỉ cần biên dịch với `rustc` là tốt cho các chương trình đơn giản, nhưng khi dự án của bạn phát triển, bạn sẽ muốn quản
lý tất cả các tùy chọn và giúp bạn dễ dàng chia sẻ mã của mình. Tiếp theo, chúng tôi sẽ giới thiệu cho bạn công cụ
Cargo, công cụ này sẽ giúp bạn viết các chương trình Rust thực tế.

[troubleshooting]: ch01-01-installation.html#xử-lý-sự-cố
