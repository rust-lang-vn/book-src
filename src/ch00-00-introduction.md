# Giới thiệu

> Ghi chú: Ấn bản này của cuốn sách giống với [Ngôn ngữ Lập trình Rust][nsprust]
> có sẵn ở định dạng in và sách điện tử từ [No Starch Press][nsp].

[nsprust]: https://nostarch.com/rust

[nsp]: https://nostarch.com/

Chào mừng đến với *Ngôn ngữ Lập trình Rust*, một cuốn sách giới thiệu về Rust. Ngôn ngữ lập trình Rust giúp bạn viết
phần mềm nhanh hơn, đáng tin cậy hơn. Công thái học high-level và kiểm soát low-level thường mâu thuẫn với nhau trong
thiết kế ngôn ngữ lập trình; Rust thách thức xung đột đó. Thông qua việc cân bằng giữa năng lực kỹ thuật mạnh mẽ và trải
nghiệm tuyệt vời dành cho nhà phát triển, Rust cung cấp cho bạn tùy chọn kiểm soát các chi tiết low-level (chẳng hạn như
sử dụng bộ nhớ) mà không gặp phải các rắc rối như vậy theo cách truyền thống.

## Rust dành cho ai

Rust là lý tưởng cho nhiều người vì nhiều lý do. Hãy xem xét một số điều quan trọng nhất.

### Nhóm các nhà phát triển

Rust đang chứng tỏ là một công cụ hiệu quả để cộng tác giữa các nhóm lớn các nhà phát triển với các mức độ khác nhau về
kiến thức lập trình hệ thống. Mã low-level dễ mắc phải nhiều lỗi tinh vi, mà ở hầu hết các ngôn ngữ khác chỉ có thể mắc
phải thông qua thử nghiệm rộng rãi và xem xét mã cẩn thận bởi các nhà phát triển có kinh nghiệm. Trong Rust, trình biên
dịch đóng vai trò người gác cổng bằng cách từ chối biên dịch mã với những lỗi khó nắm bắt này, bao gồm cả lỗi đồng
thời (concurrency). Bằng cách làm việc cùng với trình biên dịch, nhóm có thể dành thời gian tập trung vào logic của
chương trình hơn là tìm kiếm các lỗi.

Rust cũng mang lại các công cụ dành cho nhà phát triển hiện đại vào thế giới lập trình hệ thống:

* Cargo, công cụ xây dựng và quản lý gói phụ thuộc đi kèm, giúp việc thêm, biên dịch và quản lý các gói phụ thuộc trở
  nên dễ dàng và nhất quán trên toàn hệ sinh thái Rust.
* Rustfmt đảm bảo một phong cách mã hóa nhất quán giữa các nhà phát triển.
* Máy chủ ngôn ngữ Rust hỗ trợ tích hợp Môi trường phát triển tích hợp (IDE) để hoàn thành mã và thông báo lỗi nội
  tuyến.

Bằng cách sử dụng các công cụ này và các công cụ khác trong hệ sinh thái Rust, các nhà phát triển có thể làm việc hiệu
quả trong khi viết mã systems-level.

### Sinh viên

Rust dành cho sinh viên và những người quan tâm đến việc tìm hiểu về các khái niệm hệ thống. Sử dụng Rust, nhiều người
đã học về các chủ đề như phát triển hệ điều hành. Cộng đồng rất hoan nghênh và sẵn lòng trả lời các câu hỏi của sinh
viên. Thông qua những nỗ lực như cuốn sách này, nhóm Rust muốn làm cho các khái niệm hệ thống trở nên dễ tiếp cận hơn
với nhiều người hơn, đặc biệt là những người mới lập trình.

### Công ty

Hàng trăm công ty lớn nhỏ sử dụng Rust trong sản xuất cho nhiều nhiệm vụ khác nhau. Các tác vụ đó bao gồm các công cụ
dòng lệnh (command line), dịch vụ web, công cụ DevOps, thiết bị nhúng (embedded devices), phân tích và chuyển mã âm
thanh và video, tiền điện tử (cryptocurrencies), tin sinh học (bioinformatics), công cụ tìm kiếm (search engines), ứng
dụng Internet of Things (IoT), máy học (machine learning) và thậm chí là các phần chính của trình duyệt web Firefox.

### Nhà phát triển mã nguồn mở

Rust dành cho những người muốn xây dựng ngôn ngữ lập trình Rust, cộng đồng, công cụ dành cho nhà phát triển và thư viện.
Chúng tôi mong muốn bạn đóng góp cho ngôn ngữ Rust.

### Những người coi trọng tốc độ và sự ổn định

Rust dành cho những người khao khát tốc độ và sự ổn định trong một ngôn ngữ. Về tốc độ, nghĩa là tốc độ của các chương
trình mà bạn có thể tạo bằng Rust và tốc độ mà Rust cho phép bạn viết chúng. Các kiểm tra của trình biên dịch Rust đảm
bảo tính ổn định thông qua việc bổ sung tính năng và tái cấu trúc. Điều này trái ngược với mã kế thừa mỏng manh trong
các ngôn ngữ không có các kiểm tra này, mà các nhà phát triển thường ngại sửa đổi. Bằng cách cố gắng tạo ra các tính
năng trừu tượng (abstractions) không tốn chi phí, các tính năng higher-level có thể biên dịch thành mã lower-level nhanh
như mã được viết thủ công, Rust cũng cố gắng làm cho mã an toàn trở thành mã nhanh.

Ngôn ngữ Rust hy vọng sẽ hỗ trợ nhiều người dùng khác nữa; những người được đề cập ở đây chỉ là một số bên liên quan lớn
nhất. Nhìn chung, tham vọng lớn nhất của Rust là loại bỏ sự đánh đổi mà các lập trình viên đã chấp nhận trong nhiều thập
kỷ bằng cách cung cấp sự an toàn *và* năng suất, tốc độ *và* công thái học. Hãy thử Rust và xem các lựa chọn của nó có
phù hợp với bạn không.

## Cuốn sách này dành cho ai

Cuốn sách này giả định rằng bạn đã viết mã bằng một ngôn ngữ lập trình khác nhưng không đưa ra bất kỳ cụ thể về ngôn ngữ
lập trình nào. Chúng tôi đã cố gắng làm cho tài liệu có thể tiếp cận rộng rãi với những người từ nhiều nền tảng lập
trình khác nhau. Chúng tôi không dành nhiều thời gian để nói về lập trình *là gì* hoặc cách nghĩ về nó. Nếu bạn là người
mới hoàn toàn học lập trình, bạn sẽ học tập tốt hơn bằng cách đọc một cuốn sách cung cấp cụ thể phần giới thiệu về lập
trình.

## Sử dụng cuốn sách này thế nào

Nhìn chung, cuốn sách này giả định rằng bạn đang đọc nó theo trình tự từ trước ra sau. Các chương sau xây dựng dựa trên
các khái niệm trong các chương trước đó và các chương trước đó có thể không đi sâu vào chi tiết về một chủ đề; chúng ta
thường xem lại chủ đề trong chương sau.

Bạn sẽ tìm thấy hai loại chương trong cuốn sách này: chương khái niệm và chương dự án. Trong các chương khái niệm, bạn
sẽ tìm hiểu về một khía cạnh của Rust. Trong các chương của dự án, chúng ta sẽ cùng nhau xây dựng các chương trình nhỏ,
áp dụng những gì bạn đã học được cho đến nay. Chương 2, 12 và 20 là các chương của dự án; phần còn lại là các chương
khái niệm.

Chương 1 giải thích cách cài đặt Rust, cách viết chương trình “Hello, world!” và cách sử dụng Cargo, công cụ xây dựng và
quản lý gói của Rust. Chương 2 là phần giới thiệu thực hành về ngôn ngữ Rust. Ở đây chúng tôi đề cập đến các khái niệm ở
cấp độ cao và các chương sau sẽ cung cấp thêm chi tiết. Nếu bạn muốn thử tay ngay lập tức, thì Chương 2 chính là nơi
dành cho điều đó. Lúc đầu, bạn thậm chí có thể muốn bỏ qua Chương 3, bao gồm các tính năng của Rust tương tự như các
ngôn ngữ lập trình khác và đi thẳng đến Chương 4 để tìm hiểu về hệ thống sở hữu (ownership) của Rust. Tuy nhiên, nếu bạn
là một người học đặc biệt tỉ mỉ, thích tìm hiểu mọi chi tiết trước khi chuyển sang phần tiếp theo, bạn có thể bỏ qua
Chương 2 và chuyển thẳng sang Chương 3, quay lại Chương 2 khi bạn muốn làm việc trên dự án áp dụng các chi tiết bạn đã
học.

Chương 5 thảo luận về các cấu trúc (structs) và phương thức (methods), và Chương 6 bao gồm các enums, các biểu
thức `match` và cấu trúc luồng điều khiển `if let`. Bạn sẽ sử dụng cấu trúc và enum để tạo các loại tùy chỉnh trong
Rust.

Trong Chương 7, bạn sẽ tìm hiểu về hệ thống module của Rust và về các quy tắc bảo mật để tổ chức mã của bạn và
Application Programming Interface (API) công khai của nó. Chương 8 thảo luận về một số cấu trúc dữ liệu thu thập phổ
biến mà thư viện chuẩn cung cấp, chẳng hạn như vectors, strings và hash maps. Chương 9 khám phá triết lý và kỹ thuật xử
lý lỗi của Rust.

Chương 10 đào sâu về generics, traits và lifetimes, cung cấp cho bạn sức mạnh để xác định mã áp dụng cho nhiều loại.
Chương 11 là tất cả về testing, mà ngay cả với các đảm bảo an toàn của Rust là cần thiết để đảm bảo logic của chương
trình của bạn là chính xác. Trong Chương 12, chúng tôi sẽ xây dựng triển khai của riêng mình về một tập hợp con chức
năng từ công cụ dòng lệnh `grep` để tìm kiếm văn bản trong tệp. Đối với điều này, chúng tôi sẽ sử dụng nhiều khái niệm
mà chúng tôi đã thảo luận trong các chương trước.

Chương 13 khám phá các bao đóng (closures) và trình vòng lặp (iterators): các tính năng của Rust đến từ các ngôn ngữ lập
trình chức năng (functional programming). Trong Chương 14, chúng ta sẽ xem xét Cargo sâu hơn và thảo luận về các phương
pháp hay nhất để chia sẻ thư viện của bạn với những người khác. Chương 15 thảo luận về các con trỏ thông minh (smart
pointers) mà thư viện chuẩn cung cấp và các đặc điểm kích hoạt chức năng của chúng.

Trong Chương 16, chúng ta sẽ đi qua các mô hình lập trình đồng thời khác nhau và nói về cách Rust giúp bạn lập trình
theo nhiều chuỗi một cách dễ dàng. Chương 17 xem xét cách thành ngữ Rust so sánh với các nguyên tắc lập trình hướng đối
tượng (OOP) mà bạn có thể quen thuộc.

Chương 18 là một tài liệu tham khảo về mô hình và mô hình kết hợp, đó là cách mạnh mẽ của diễn đạt ý tưởng xuyên suốt
chương trình Rust. Chương 19 bao gồm một loạt các chủ đề nâng cao được quan tâm, bao gồm Rust không an toàn (unsafe),
macro, và nhiều hơn nữa về lifetimes, traits, types, functions và closures.

Trong Chương 20, chúng tôi sẽ hoàn thành một dự án, trong đó chúng tôi sẽ triển khai một máy chủ web đa luồng low-level!

Cuối cùng, một số phụ lục chứa thông tin hữu ích về ngôn ngữ ở định dạng giống tham khảo hơn. Phụ lục A bao gồm các từ
khóa của Rust, Phụ lục B bao gồm các toán tử và ký hiệu của Rust, Phụ lục C bao gồm các đặc điểm có thể dẫn xuất được
cung cấp bởi thư viện tiêu chuẩn, Phụ lục D bao gồm một số công cụ phát triển hữu ích và Phụ lục E giải thích các phiên
bản Rust.

Không có cách nào sai khi đọc cuốn sách này: nếu bạn muốn bỏ qua, hãy tiếp tục!
Bạn có thể phải quay lại các chương trước đó nếu bạn gặp bất kỳ sự nhầm lẫn nào. Nhưng hãy làm bất cứ điều gì có ích cho
bạn.

<span id="ferris"></span>

Một phần quan trọng của quá trình học Rust là học cách đọc các thông báo lỗi mà trình biên dịch hiển thị: những thông
báo này sẽ hướng dẫn bạn cách làm việc với mã. Do đó, chúng tôi sẽ cung cấp nhiều ví dụ không biên dịch cùng với thông
báo lỗi mà trình biên dịch sẽ hiển thị cho bạn trong từng tình huống. Nghĩa là nếu bạn nhập và chạy một ví dụ ngẫu
nhiên, nó có thể không biên dịch! Đảm bảo rằng bạn đọc văn bản xung quanh để xem liệu ví dụ bạn đang cố chạy có bị lỗi
hay không. Ferris cũng sẽ giúp bạn phân biệt mã không hoạt động:

| Ferris                                                                                                           | Ý nghĩa                                          |
|------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|
| <img src="img/ferris/does_not_compile.svg" class="ferris-explain" alt="Ferris with a question mark"/>            | Mã này không biên dịch!                          |
| <img src="img/ferris/panics.svg" class="ferris-explain" alt="Ferris throwing up their hands"/>                   | Mã này hoảng loạn (panics)!                      |
| <img src="img/ferris/not_desired_behavior.svg" class="ferris-explain" alt="Ferris with one claw up, shrugging"/> | Mã này không tạo ra hành vi mong muốn.           |

Trong hầu hết các tình huống, chúng tôi sẽ dẫn bạn đến phiên bản chính xác của bất kỳ mã nào không biên dịch.

## Mã nguồn

Có thể tìm thấy các tệp nguồn mà cuốn sách này được tạo từ
[GitHub][book].

[book]: https://github.com/rust-lang-vn/book-src/tree/vi-translation/src
