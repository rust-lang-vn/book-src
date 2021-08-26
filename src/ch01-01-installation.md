## Cài đặt

Bước đầu tiên là cài đặt Rust. Chúng ta sẽ tải xuống Rust thông qua `rustup`, một công cụ command line để quản lý các
phiên bản Rust và các công cụ liên quan. Bạn sẽ cần kết nối Internet để tải xuống.

> Ghi chú: Nếu bạn không muốn sử dụng `rustup` vì lý do nào đó, vui lòng xem
> [Other Rust Installation Methods page][install] để có nhiều lựa chọn hơn.

[install]: https://forge.rust-lang.org/infra/other-installation-methods.html

Các bước sau cài đặt phiên bản ổn định mới nhất của trình biên dịch Rust. Tính ổn định của Rust đảm bảo rằng tất cả các
ví dụ trong cuốn sách biên dịch sẽ tiếp tục được biên dịch với các phiên bản Rust mới hơn. Đầu ra có thể hơi khác nhau
giữa các phiên bản, vì Rust thường cải thiện các thông báo và cảnh báo lỗi. Nói cách khác, bất kỳ phiên bản mới, ổn định
của Rust mà bạn cài đặt bằng các bước sẽ hoạt động như mong đợi với nội dung của cuốn sách này.

> ### Ký hiệu dòng lệnh
>
> Trong chương này và xuyên suốt cuốn sách, chúng tôi sẽ trình bày một số lệnh được sử dụng
> trong terminal. Các dòng mà bạn nên nhập vào terminal đều bắt đầu bằng `$`. Bạn
> không cần thiết phải gõ ký hiệu `$`; nó chỉ ra sự bắt đầu của mỗi
> lệnh. Các dòng không bắt đầu bằng `$` thường hiển thị đầu ra của
> lệnh trước đó. Ngoài ra, các ví dụ cụ thể về PowerShell sẽ sử dụng `>`
> thay thế cho `$`.

### Cài đặt `rustup` trên Linux hoặc macOS

Nếu bạn đang dùng Linux hoặc macOS, mở terminal và nhập lệnh sau:

```console
$ curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh
```

Lệnh tải xuống một tập lệnh và bắt đầu cài đặt công cụ `rustup`, để cài đặt phiên bản ổn định mới nhất của Rust. Bạn có
thể được nhắc nhập mật khẩu của mình. Nếu cài đặt thành công, dòng sau sẽ xuất hiện:

```text
Rust is installed now. Great!
```

Bạn cũng sẽ cần một trình liên kết (linker), đây là một chương trình mà Rust sử dụng để kết hợp các đầu ra đã biên dịch
của nó thành một tệp. Có khả năng là bạn đã có sẵn. Nếu bạn gặp lỗi trình liên kết, bạn nên cài đặt trình biên dịch C,
trình biên dịch này thường sẽ bao gồm trình liên kết. Trình biên dịch C cũng hữu ích vì một số gói Rust phổ biến phụ
thuộc vào mã C và sẽ cần trình biên dịch C.

Trên macOS, bạn có thể tải một trình biên dịch C bằng cách chạy:

```console
$ xcode-select --install
```

Người dùng Linux nói chung nên cài đặt GCC hoặc Clang, theo tài liệu của bản phân phối của chúng. Ví dụ: nếu bạn sử dụng
Ubuntu, bạn có thể cài đặt gói `build-essential`.

### Cài đặt `rustup` trên Windows

Trên Windows, đi đến [https://www.rust-lang.org/tools/install][install] và làm theo hướng dẫn để cài đặt Rust. Tại một
số thời điểm trong quá trình cài đặt, bạn sẽ nhận được thông báo giải thích rằng bạn cũng sẽ cần các công cụ xây dựng
C++ cho Visual Studio 2013 trở lên. Khi được hỏi workloads nào cần cài đặt, hãy đảm bảo rằng "C++ build tools"
được chọn và Windows 10 SDK cũng như bao gồm gói ngôn ngữ English.

[install]: https://www.rust-lang.org/tools/install

[visualstudio]: https://visualstudio.microsoft.com/visual-cpp-build-tools/

Phần còn lại của cuốn sách này sử dụng các lệnh hoạt động trong cả *cmd.exe* và PowerShell. Nếu có sự khác biệt cụ thể,
chúng tôi sẽ giải thích cách sử dụng.

### Cập nhật và Gỡ cài đặt

Sau khi bạn cài đặt Rust thông qua `rustup`, cập nhật lên phiên bản mới nhất rất dễ dàng. Từ trình shell của bạn, chạy
tập lệnh cập nhật sau:

```console
$ rustup update
```

Để gỡ cài đặt Rust và `rustup`, chạy tập lệnh gỡ cài đặt sau từ trình shell của bạn:

```console
$ rustup self uninstall
```

### Xử lý sự cố

Để kiểm tra xem bạn đã cài đặt Rust đúng cách hay chưa, hãy mở một trình shell và nhập dòng này:

```console
$ rustc --version
```

Bạn sẽ thấy số phiên bản, commit hash và ngày commit cho phiên bản ổn định mới nhất đã được phát hành ở định dạng sau:

```text
rustc x.y.z (abcabcabc yyyy-mm-dd)
```

Nếu bạn thấy thông tin này, bạn đã cài đặt Rust thành công! Nếu bạn không thấy thông tin này và bạn đang sử dụng
Windows, hãy kiểm tra xem Rust có trong biến hệ thống `%PATH%` của bạn. Nếu tất cả đều đúng và Rust vẫn không hoạt động,
có một số nơi bạn có thể nhận trợ giúp. Dễ nhất là kênh #beginners trên [the official Rust Discord][discord]. Ở đó, bạn
có thể trò chuyện với những người Rustaceans khác (biệt danh ngớ ngẩn mà chúng tôi tự gọi), những người có thể giúp bạn.
Các nguồn tài nguyên tuyệt vời khác bao gồm [the Users forum][users] và [Stack Overflow][stackoverflow].

[discord]: https://discord.gg/rust-lang

[users]: https://users.rust-lang.org/

[stackoverflow]: https://stackoverflow.com/questions/tagged/rust

### Tài liệu local

Quá trình cài đặt Rust cũng bao gồm một bản sao của tài liệu local, vì vậy bạn có thể đọc ngoại tuyến. Chạy `rustup doc`
để mở tài liệu local trong trình duyệt của bạn.

Bất cứ khi nào một loại hoặc chức năng được cung cấp bởi thư viện chuẩn và bạn không chắc chắn về chức năng hoặc cách sử
dụng nó, hãy sử dụng tài liệu về giao diện lập trình ứng dụng (API) để tìm hiểu!
