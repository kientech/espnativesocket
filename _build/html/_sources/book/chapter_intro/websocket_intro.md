## 🚀 WebSocket 

### Websocket là gì?

✍️ WebSocket là một công nghệ giao tiếp hai chiều (full-duplex) giữa máy khách (client) và máy chủ (server) trên mạng. Nó cho phép truyền dữ liệu theo thời gian thực và liên tục giữa hai đầu điểm mà không cần phải tạo ra các yêu cầu HTTP mới mỗi lần như trong mô hình truyền thống. Thay vì sử dụng giao thức HTTP, WebSocket sử dụng một giao thức riêng, giúp tối ưu hóa việc truyền dữ liệu và giảm thiểu độ trễ.

WebSocket hoạt động bằng cách thiết lập một kết nối TCP được duy trì liên tục giữa client và server. Khi kết nối này được thiết lập, cả hai bên có thể gửi và nhận dữ liệu một cách đồng thời và liên tục mà không cần phải chờ đợi cho các yêu cầu và phản hồi HTTP mới.

### Tại sao Websocket được sử dụng trong dự án này?

- **Kết nối hai chiều liên tục** WebSocket cho phép truyền dữ liệu từ cả client và server một cách đồng thời và liên tục. Điều này mang lại sự tương tác mạnh mẽ và thời gian thực trong các ứng dụng như trò chơi trực tuyến, ứng dụng chat, hoặc hệ thống giám sát.

- **Thời gian thực và độ trễ thấp:** Với khả năng truyền dữ liệu ngay lập tức mà không cần phải chờ đợi cho các yêu cầu và phản hồi HTTP mới, WebSocket là lựa chọn hàng đầu cho các ứng dụng cần độ trễ thấp và cập nhật dữ liệu thời gian thực như hệ thống giao dịch chứng khoán hoặc theo dõi vị trí của các phương tiện giao thông công cộng.

- **Tiết kiệm băng thông và tài nguyên:** WebSocket giảm thiểu lượng dữ liệu truyền qua mạng bởi vì không cần phải gửi lại các tiêu đề HTTP cho mỗi thông điệp. Điều này giúp giảm tải cho máy chủ và cải thiện hiệu suất của ứng dụng, đặc biệt là khi có hàng trăm hoặc hàng nghìn kết nối cùng lúc.

- **Tích hợp dễ dàng:** WebSocket được hỗ trợ trên hầu hết các trình duyệt hiện đại và có sẵn trong nhiều thư viện và framework phổ biến như Socket.IO, WebSocket API trong JavaScript, hay các thư viện WebSocket cho Python và Java. Điều này làm cho việc tích hợp vào dự án trở nên dễ dàng và linh hoạt.

- **Bảo mật cao:** WebSocket hỗ trợ các phương thức bảo mật như TLS/SSL, giúp bảo vệ dữ liệu truyền qua kết nối giữa client và server.

WebSocket là một công nghệ mạnh mẽ cho phép truyền dữ liệu theo thời gian thực và tương tác hai chiều giữa client và server một cách hiệu quả và linh hoạt. Sử dụng WebSocket trong dự án giúp cải thiện trải nghiệm người dùng, tăng cường tính tương tác và giảm thiểu độ trễ, đồng thời cũng giảm tải cho máy chủ và tối ưu hóa hiệu suất của ứng dụng.
