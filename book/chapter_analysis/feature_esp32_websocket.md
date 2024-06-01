## 🖥️ Tính Năng

Hệ thống tản nhiệt sử dụng React Native, WebSocket và ESP32 cung cấp nhiều tính năng hữu ích cho việc theo dõi và quản lý nhiệt độ hệ thống. Dưới đây là mô tả chi tiết về các tính năng chính:

- Giám sát nhiệt độ:

  - Theo dõi thời gian thực: Hệ thống liên tục thu thập dữ liệu nhiệt độ từ cảm biến được kết nối với ESP32 và hiển thị giá trị hiện tại trên giao diện người dùng React Native.
  - Biểu đồ: Hệ thống có thể hiển thị biểu đồ nhiệt độ theo thời gian, giúp người dùng dễ dàng hình dung xu hướng thay đổi nhiệt độ và xác định các điểm nóng tiềm ẩn.
  - Cảnh báo: Người dùng có thể cài đặt ngưỡng nhiệt độ cảnh báo và nhận thông báo khi nhiệt độ vượt quá ngưỡng cho phép.
  - Lịch sử: Hệ thống có thể lưu trữ dữ liệu nhiệt độ theo thời gian, cho phép người dùng truy cập và phân tích dữ liệu trong quá khứ.

- Điều khiển quạt:

  - Bật/tắt thủ công: Người dùng có thể bật hoặc tắt quạt tản nhiệt thủ công từ giao diện React Native.
  - Điều khiển tự động: Hệ thống có thể tự động điều khiển quạt dựa trên dữ liệu nhiệt độ. Ví dụ: quạt có thể tự động bật khi nhiệt độ vượt quá ngưỡng nhất định hoặc chạy với tốc độ khác nhau tùy thuộc vào mức độ nóng của hệ thống.
  - Tùy chỉnh: Người dùng có thể tùy chỉnh các quy tắc điều khiển quạt tự động để phù hợp với nhu cầu cụ thể của mình.

- Quản lý hệ thống:

  - Giám sát nhiều thiết bị: Hệ thống có thể hỗ trợ nhiều cảm biến nhiệt độ và quạt tản nhiệt, cho phép người dùng theo dõi và quản lý nhiệt độ của nhiều hệ thống khác nhau từ một giao diện duy nhất.
  - Cập nhật phần mềm: Hệ thống có thể được cập nhật phần mềm từ xa để bổ sung các tính năng mới và sửa lỗi.
  - Quản lý người dùng: Hệ thống có thể hỗ trợ quản lý người dùng với các cấp quyền khác nhau, cho phép kiểm soát truy cập vào các tính năng cụ thể.

- Bảo mật:

  - Xác thực: Hệ thống có thể sử dụng các phương thức xác thực để đảm bảo chỉ những người dùng được ủy quyền mới có thể truy cập.
  - Mã hóa: Hệ thống có thể sử dụng mã hóa để bảo vệ dữ liệu được truyền giữa các thành phần.
  - Kiểm soát truy cập: Hệ thống có thể sử dụng kiểm soát truy cập để hạn chế quyền truy cập vào các tính năng cụ thể dựa trên vai trò của người dùng.

- Khả năng mở rộng:

  - Hỗ trợ nhiều thiết bị: Hệ thống có thể được mở rộng để hỗ trợ thêm nhiều cảm biến nhiệt độ và quạt tản nhiệt.
  - Tích hợp với hệ thống khác: Hệ thống có thể được tích hợp với các hệ thống khác, chẳng hạn như hệ thống giám sát nhà thông minh hoặc hệ thống quản lý trung tâm dữ liệu.
