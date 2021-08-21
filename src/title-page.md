# Ngôn ngữ Lập trình Rust

*tạo bởi Steve Klabnik và Carol Nichols, với sự đóng góp từ Cộng đồng Rust*

Phiên bản này của văn bản giả định rằng bạn đang sử dụng Rust 1.54 hoặc cao hơn với `edition="2018"` trong *Cargo.toml*
của tất cả các dự án để sử dụng những thuật ngữ trong Rust 2018 Edition.
Xem [“Installation” section of Chapter 1][install]<!-- ignore --> để cài đặt và cập nhật Rust, và xem
thêm [Appendix E][editions]<!-- ignore --> để biết thông tin về các phiên bản.

2018 Edition của ngôn ngữ Rust bao gồm một số cải tiến giúm cho Rust tiện dụng và dễ học hơn. Phần lặp lại này của cuốn
sách có một số thay đổi để phản ánh những cải tiến đó:

- Chương 7, “Managing Growing Projects with Packages, Crates, and Modules,” đã được viết lại gần hết. Hệ thống module và
  cách những đường dẫn hoạt động trong 2018 Edition đã được thực hiện nhất quán hơn.
- Chương 10 có các phần mới với tiêu đề “Traits as Parameters” và “Returning Types that Implement Traits” dùng để giải
  thích cú pháp `impl Trait` mới.
- Chương 11 có một phần mới với tiêu đề “Using `Result<T, E>` in Tests” để biểu diễn cách viết test sử dụng toán tử `?`.
- Phần “Advanced Lifetimes” trong Chương 19 được loại bỏ vì các cải tiến của compiler đã làm cho những cấu trúc trong
  phần đó trở nên hiếm hơn.
- Phụ lục D trước đó, “Macros,” đã được mở rộng để bao gồm các thủ tục marco và được chuyển đến phần “Macros” trong
  Chương 19.
- Phụ lục A, “Keywords,” cũng giải thích tính năng mới raw identifiers cho phép mã được viết trong 2015 Edition và 2018
  Edition tương tác với nhau.
- Phụ lục D bây giờ có tiêu đề “Useful Development Tools” và bao gồm các công cụ được phát hành gần đây giúp bạn viết mã
  Rust.
- Chúng tôi đã sửa một số lỗi nhỏ và cách diễn đạt không chính xác trong suốt cuốn sách. Cảm ơn các độc giả đã báo cáo
  chúng!

Lưu ý rằng bất kỳ mã nào trong các lần lặp trước đó của *Ngôn ngữ Lập trình Rust* đã được biên dịch sẽ tiếp tục được
biên dịch mà không có `edition="2018"` trong *Cargo.toml* của dự án, ngay cả khi bạn cập nhật phiên bản trình biên dịch
Rust mà bạn đang sử dụng. Đó là đảm bảo khả năng tương thích ngược của Rust!

Định dạng HTML có sẵn online tại
[https://doc.rust-lang.org/stable/book/](https://doc.rust-lang.org/stable/book/)
và bản offline kèm theo các bản cài đặt của Rust được thực hiện bằng `rustup`; chạy `rustup docs --book` để mở.

Văn bản này có sẵn trong [paperback and ebook format from No Starch Press][nsprust].

[install]: ch01-01-installation.html

[editions]: appendix-05-editions.html

[nsprust]: https://nostarch.com/rust
