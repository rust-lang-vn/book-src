## Hello, Cargo!

Cargo dùng để quản lý gói và hệ thống xây dựng của Rust. Hầu hết Rustaceans sử dụng công cụ này để quản lý các dự án
Rust của họ vì Cargo xử lý rất nhiều nhiệm vụ cho bạn, chẳng hạn như xây dựng mã của bạn, tải xuống các thư viện mà mã
của bạn phụ thuộc vào và xây dựng các thư viện đó. (Chúng tôi gọi các thư viện mà mã của bạn cần là *dependencies*.)

Các chương trình Rust đơn giản nhất, giống như cái mà chúng tôi đã viết cho đến nay, không có bất kỳ phụ thuộc nào. Vì
vậy, nếu chúng tôi đã xây dựng dự án “Hello, world!” với Cargo, nó sẽ chỉ sử dụng một phần của Cargo để xử lý việc xây
dựng mã của bạn. Khi bạn viết các chương trình Rust phức tạp hơn, bạn sẽ thêm các phần phụ thuộc và nếu bạn bắt đầu một
dự án bằng cách sử dụng Cargo, việc thêm các phần phụ thuộc sẽ dễ thực hiện hơn nhiều.

Bởi vì phần lớn các dự án Rust sử dụng Cargo, phần còn lại của cuốn sách này giả định rằng bạn cũng đang sử dụng Cargo.
Cargo được cài đặt cùng với Rust nếu bạn sử dụng trình cài đặt chính thức được thảo luận trong phần
[“Installation”][installation]<!-- ignore -->. Nếu bạn đã cài đặt Rust thông qua một số cách khác, hãy kiểm tra xem
Cargo đã được cài đặt chưa bằng cách nhập thông tin sau vào terminal của bạn:

```console
$ cargo --version
```

Nếu bạn thấy số phiên bản, bạn có nó! Nếu bạn gặp lỗi, chẳng hạn như `command not found`, hãy xem tài liệu về phương
pháp cài đặt của bạn để xác định cách cài đặt Cargo riêng biệt.

### Tạo một dự án với Cargo

Hãy tạo một dự án mới bằng cách sử dụng Cargo và xem nó khác như thế nào với dự án “Hello, world!” ban đầu của chúng
tôi. Trở lại thư mục *projects* của bạn (hoặc bất cứ nơi nào bạn quyết định lưu trữ mã của mình). Sau đó, trên bất kỳ hệ
điều hành nào, hãy chạy như sau:

```console
$ cargo new hello_cargo
$ cd hello_cargo
```

Lệnh đầu tiên tạo một thư mục mới có tên *hello_cargo*. Chúng tôi đã đặt tên cho dự án của mình là *hello_cargo* và
Cargo tạo các tệp của dự án trong một thư mục có cùng tên.

Vào thư mục *hello_cargo* và liệt kê các tệp. Bạn sẽ thấy rằng Cargo đã tạo hai tệp và một thư mục cho chúng tôi: tệp
Cargo.toml* và thư mục *src* có tệp *main.rs* bên trong.

Nó cũng đã khởi tạo kho lưu trữ Git mới cùng với tệp *.gitignore*. Các tệp Git sẽ không được tạo nếu bạn chạy
`cargo new` trong kho lưu trữ Git hiện có; bạn có thể ghi đè hành vi này bằng cách sử dụng `cargo new --vcs=git`.

> Ghi chú: Git là một hệ thống kiểm soát phiên bản (version control system) phổ biến. Bạn có thể thay đổi `cargo new`
> để sử dụng hệ thống kiểm soát phiên bản khác hoặc không bằng cách sử dụng cờ `--vcs`. Chạy `cargo new --help` để xem
> các tùy chọn có sẵn.

Mở *Cargo.toml* trong trình soạn thảo văn bản mà bạn chọn. Nó sẽ trông tương tự như mã trong Listing 1-2.

<span class="filename">Filename: Cargo.toml</span>

```toml
[package]
name = "hello_cargo"
version = "0.1.0"
edition = "2018"

[dependencies]
```

<span class="caption">Listing 1-2: Nội dung của *Cargo.toml* được tạo bởi `cargo new`</span>

Tệp này ở định dạng [*TOML*](https://toml.io)<!-- ignore --> (*Tom’s Obvious, Minimal Language*), là định dạng cấu hình
của Cargo.

Dòng đầu tiên, `[package]`, là phần tiêu đề cho biết rằng các câu lệnh sau đang cấu hình một package. Khi chúng tôi thêm
nhiều thông tin vào tệp này, chúng tôi sẽ thêm các phần khác.

Ba dòng tiếp theo đặt thông tin cấu hình mà Cargo cần để biên dịch chương trình của bạn: tên, phiên bản và phiên bản
Rust để sử dụng. Chúng ta sẽ nói về khóa `edition` trong [Appendix E][appendix-e]<!-- ignore -->.

Dòng cuối cùng, `[dependencies]`, là phần bắt đầu để bạn liệt kê bất kỳ sự phụ thuộc nào trong dự án của bạn. Trong
Rust, các package của mã được gọi là *crates*. Chúng tôi sẽ không cần bất kỳ crates nào khác cho dự án này, nhưng chúng
tôi sẽ thực hiện dự án đầu tiên trong Chương 2, vì vậy chúng tôi sẽ sử dụng phần phụ thuộc này sau đó.

Bây giờ hãy mở *src/main.rs* và xem:

<span class="filename">Filename: src/main.rs</span>

```rust
fn main() {
    println!("Hello, world!");
}
```

Cargo đã tạo ra một chương trình “Hello, world!” dành cho bạn, giống như cái chúng tôi đã viết trong Listing 1-1! Cho
đến nay, sự khác biệt giữa dự án trước đây của chúng tôi và dự án mà Cargo tạo ra là Cargo đặt mã trong thư mục *src*
và chúng tôi có tệp cấu hình *Cargo.toml* trong thư mục trên cùng.

Cargo hy vọng các tệp nguồn của bạn sẽ nằm trong thư mục *src*. Thư mục dự án cấp cao nhất chỉ dành cho các tệp README,
thông tin giấy phép, tệp cấu hình và bất kỳ thứ gì khác không liên quan đến mã của bạn. Sử dụng Cargo giúp bạn tổ chức
các dự án của mình. Có một nơi cho mọi thứ và mọi thứ đều ở đúng vị trí của nó.

Nếu bạn bắt đầu một dự án không sử dụng Cargo, như chúng tôi đã làm với dự án “Hello, world!”, bạn có thể chuyển đổi nó
thành một dự án sử dụng Cargo. Di chuyển mã dự án vào thư mục *src* và tạo tệp *Cargo.toml* thích hợp.

### Xây dựng và chạy một dự án Cargo

Bây giờ, hãy xem điều gì khác biệt khi chúng tôi xây dựng và chạy chương trình “Hello, world!” với Cargo! Từ thư mục
*hello_cargo* của bạn, hãy xây dựng dự án của bạn bằng cách nhập lệnh sau:

```console
$ cargo build
   Compiling hello_cargo v0.1.0 (file:///projects/hello_cargo)
    Finished dev [unoptimized + debuginfo] target(s) in 2.85 secs
```

Lệnh này tạo một tệp thực thi trong *target/debug/hello_cargo* (hoặc *target\debug\hello_cargo.exe* trên Windows) chứ
không phải trong thư mục hiện tại của bạn. Bạn có thể chạy tệp thực thi bằng lệnh này:

```console
$ ./target/debug/hello_cargo # or .\target\debug\hello_cargo.exe on Windows
Hello, world!
```

Nếu mọi việc suôn sẻ, dòng chữ `Hello, world!` sẽ được in ra terminal. Chạy `cargo build` lần đầu tiên cũng khiến Cargo
tạo một tệp mới ở cấp cao nhất: *Cargo.lock*. Tệp này theo dõi các phiên bản chính xác của các dependency trong dự án
của bạn. Dự án này không có phần phụ thuộc, vì vậy tệp hơi thưa thớt. Bạn sẽ không cần phải thay đổi tệp này theo cách
thủ công; Cargo quản lý nội dung của nó cho bạn.

Chúng tôi vừa xây dựng một dự án với `cargo build` và chạy nó với `./target/debug/hello_cargo`, nhưng chúng tôi cũng có
thể sử dụng `cargo run` để biên dịch mã và sau đó chạy kết quả thực thi tất cả trong một lệnh:

```console
$ cargo run
    Finished dev [unoptimized + debuginfo] target(s) in 0.0 secs
     Running `target/debug/hello_cargo`
Hello, world!
```

Lưu ý rằng lần này chúng tôi không thấy đầu ra cho biết Cargo đang biên dịch `hello_cargo`. Cargo phát hiện ra rằng các
tệp không thay đổi, vì vậy nó chỉ chạy tệp nhị phân. Nếu bạn đã sửa đổi mã nguồn của mình, Cargo sẽ xây dựng lại dự án
trước khi chạy nó và bạn sẽ thấy đầu ra này:

```console
$ cargo run
   Compiling hello_cargo v0.1.0 (file:///projects/hello_cargo)
    Finished dev [unoptimized + debuginfo] target(s) in 0.33 secs
     Running `target/debug/hello_cargo`
Hello, world!
```

Cargo cũng cung cấp một lệnh gọi là `cargo check`. Lệnh này nhanh chóng kiểm tra mã của bạn để đảm bảo rằng nó được biên
dịch nhưng không tạo ra tệp thực thi:

```console
$ cargo check
   Checking hello_cargo v0.1.0 (file:///projects/hello_cargo)
    Finished dev [unoptimized + debuginfo] target(s) in 0.32 secs
```

Tại sao bạn không muốn một tệp thực thi? Thông thường, `cargo check` nhanh hơn nhiều so với `cargo build`, bởi vì nó bỏ
qua bước tạo tệp thực thi. Nếu bạn liên tục kiểm tra công việc của mình trong khi viết mã, thì việc sử dụng
`cargo check` sẽ đẩy nhanh quá trình! Do đó, nhiều Rustaceans chạy `cargo check` định kỳ khi họ viết chương trình của
mình để đảm bảo rằng nó được biên dịch. Sau đó, họ chạy `cargo build` khi họ sẵn sàng sử dụng tệp thực thi.

Hãy tóm tắt lại những gì chúng ta đã học được cho đến nay về Cargo:

* Chúng ta có thể xây dựng một dự án bằng cách sử dụng `cargo build`.
* Chúng ta có thể xây dựng và chạy một dự án trong một bước bằng cách sử dụng `cargo run`.
* Chúng ta có thể xây dựng một dự án mà không cần tạo ra một tệp nhị phân để kiểm tra lỗi bằng cách sử
  dụng `cargo check`.
* Thay vì lưu kết quả của việc xây dựng trong cùng thư mục với mã, Cargo lưu trữ nó trong thư mục *target/debug*.

Một lợi thế bổ sung của việc sử dụng Cargo là các lệnh đều giống nhau cho dù bạn đang làm việc trên hệ điều hành nào. Vì
vậy, tại thời điểm này, chúng tôi sẽ không cung cấp hướng dẫn cụ thể cho Linux và macOS so với Windows.

### Xây dựng bản phát hành

Khi dự án của bạn cuối cùng đã sẵn sàng để phát hành, bạn có thể sử dụng `cargo build --release` để biên dịch nó với các
tối ưu hóa. Lệnh này sẽ tạo một tệp thực thi trong *target/release* thay vì *target/debug*. Các tối ưu hóa làm cho mã
Rust của bạn chạy nhanh hơn, nhưng việc bật chúng sẽ kéo dài thời gian biên dịch chương trình của bạn. Đây là lý do tại
sao có hai hồ sơ khác nhau: một hồ sơ dành cho phát triển, khi bạn muốn xây dựng lại nhanh chóng và thường xuyên, và hồ
sơ khác để xây dựng chương trình cuối cùng mà bạn sẽ cung cấp cho người dùng sẽ không được tạo lại nhiều lần và sẽ chạy
nhanh nhất có thể. Nếu bạn đang đo benchmark cho thời gian chạy mã của mình, hãy đảm bảo chạy `cargo build --release` và
benchmark với tệp thực thi trong *target/release*.

### Cargo như quy ước

Với các dự án đơn giản, Cargo không mang lại nhiều giá trị so với chỉ sử dụng `rustc`, nhưng nó sẽ chứng minh giá trị
của nó khi các chương trình của bạn trở nên phức tạp hơn. Với các dự án phức tạp bao gồm nhiều crates, việc để Cargo
điều phối việc xây dựng sẽ dễ dàng hơn nhiều.

Mặc dù dự án `hello_cargo` rất đơn giản, nhưng nó hiện sử dụng phần lớn công cụ thực sự mà bạn sẽ sử dụng trong phần còn
lại của sự nghiệp Rust của mình. Trên thực tế, để làm việc trên bất kỳ dự án hiện có nào, bạn có thể sử dụng các lệnh
sau để kiểm tra mã bằng Git, thay đổi thành thư mục của dự án đó và xây dựng:

```console
$ git clone example.org/someproject
$ cd someproject
$ cargo build
```

Để biết thêm thông tin về Cargo, hãy xem [its documentation].

[its documentation]: https://doc.rust-lang.org/cargo/

## Tổng kết

Bạn đã có một khởi đầu tuyệt vời trên hành trình Rust của mình! Trong chương này, bạn đã học cách:

* Cài đặt phiên bản ổn định mới nhất của Rust bằng cách sử dụng `rustup`
* Cập nhật lên phiên bản Rust mới hơn
* Mở tài liệu được cài đặt ở local
* Viết và chạy một chương trình “Hello, world!” bằng cách sử dụng trực tiếp `rustc`
* Tạo và chạy một dự án mới bằng cách sử dụng các quy ước của Cargo

Đây là thời điểm tuyệt vời để xây dựng một chương trình quan trọng hơn để làm quen với việc đọc và viết mã Rust. Vì vậy,
trong Chương 2, chúng tôi sẽ xây dựng một chương trình trò chơi đoán (guessing game). Nếu bạn muốn bắt đầu bằng cách tìm
hiểu các khái niệm lập trình phổ biến hoạt động như thế nào trong Rust, hãy xem Chương 3 và sau đó quay lại Chương 2.

[installation]: ch01-01-installation.html#cài-đặt

[appendix-e]: appendix-05-editions.html
