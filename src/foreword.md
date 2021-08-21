# Lời tựa

Nó không phải lúc nào cũng rõ ràng như vậy, nhưng ngôn ngữ lập trình Rust về cơ bản là về *trao quyền*: cho dù bây giờ
bạn đang viết loại mã nào, Rust cho phép bạn vươn xa hơn, tự tin lập trình trong nhiều lĩnh vực hơn những gì bạn đã làm
trước đây.

Ví dụ, công việc “systems-level” xử lý các chi tiết low-level về quản lý bộ nhớ (memory management), biểu diễn dữ liệu
(data representation) và đồng thời (concurrency). Theo truyền thống, lĩnh vực lập trình này được coi là phức tạp, chỉ
một số ít người được tuyển chọn đã phải dành những năm học hỏi để tránh những cạm bẫy khét tiếng của nó. Và ngay cả
những người thực hành nó cũng làm như vậy một cách thận trọng, kẻo mã của họ có thể bị khai thác (exploits), gián đoạn
(crashes), hoặc xáo trộn (corruption).

Rust phá vỡ những rào cản này bằng cách loại bỏ những cạm bẫy cũ và cung cấp một bộ công cụ thân thiện, được trao chuốt
để giúp bạn trong suốt chặng đường. Các lập trình viên khi cần phải “nhúng tay vào” kiểm soát lower-level có thể làm như
vậy với Rust, mà không phải chịu rủi ro thông thường về sự cố hoặc lỗ hổng bảo mật và không cần phải học những điểm tốt
của một chuỗi công cụ hay thay đổi. Tốt hơn nữa, ngôn ngữ được thiết kế để hướng dẫn bạn một cách tự nhiên đến mã đáng
tin cậy, hiệu quả về tốc độ và sử dụng bộ nhớ.

Các lập trình viên đang làm việc với mã low-level có thể sử dụng Rust để nâng cao tham vọng của họ. Ví dụ, giới thiệu về
song song (parallelism) trong Rust là một hoạt động có rủi ro tương đối thấp: trình biên dịch sẽ bắt các lỗi cổ điển cho
bạn. Và bạn có thể xử lý các tối ưu hóa tích cực hơn trong mã của mình với sự tự tin rằng bạn sẽ không vô tình tạo ra
các sự cố hoặc lỗ hổng bảo mật.

Nhưng Rust không giới hạn trong việc lập trình hệ thống low-level. Nó đủ khả năng và tiện dụng để làm cho các ứng dụng
CLI, máy chủ web và nhiều loại mã khác khá dễ viết — bạn sẽ tìm thấy các ví dụ đơn giản về cả hai điều này ở phần sau
của cuốn sách. Làm việc với Rust cho phép bạn xây dựng các kỹ năng chuyển từ miền này sang miền khác; bạn có thể học
Rust bằng cách viết một ứng dụng web, sau đó áp dụng những kỹ năng tương tự để nhắm mục tiêu Raspberry Pi của bạn.

Cuốn sách này hoàn toàn khai thác tiềm năng của Rust để trao quyền cho người dùng. Đó là một văn bản thân thiện và dễ
tiếp cận nhằm giúp bạn nâng cao không chỉ kiến thức về Rust mà còn cả khả năng tiếp cận và sự tự tin của bạn với tư cách
là một lập trình viên nói chung. Vì vậy, hãy tham gia, sẵn sàng học hỏi — và chào mừng bạn đến với cộng đồng Rust!

— Nicholas Matsakis và Aaron Turon
