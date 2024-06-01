## 🗣️ Phương Thức Giao Tiếp

### SPI (Serial Peripheral Interface)

**Đặc điểm:**

- Giao tiếp đồng bộ, tức là dữ liệu được truyền theo nhịp clock.
- Sử dụng ba hoặc bốn dây để kết nối thiết bị: MOSI (Master Out Slave In), MISO (Master In Slave Out), SCK (Serial Clock), và tùy chọn là SS (Slave Select).
- Có thể kết nối nhiều thiết bị Slave với một thiết bị Master.
- Tốc độ truyền dữ liệu nhanh hơn I2C.

**Hoạt động:**

- Master chọn một thiết bị Slave bằng cách thực hiện logic thấp (thông thường) trên tín hiệu SS.
- Dữ liệu được truyền đi từ Master đến Slave qua MOSI và từ Slave đến Master qua MISO, đồng bộ với tín hiệu clock từ SCK.
- Các truyền thông thường bắt đầu bằng một tín hiệu đồng bộ, sau đó dữ liệu được truyền qua các dây tương ứng.

### I2C (Inter-Integrated Circuit)

**Đặc điểm:**

- Giao tiếp đồng bộ, được điều khiển bởi một tín hiệu clock.
- Sử dụng hai dây: SDA (Serial Data) và SCL (Serial Clock).
- Có khả năng kết nối nhiều thiết bị với cùng một dây dữ liệu và dây clock.
- Tốc độ truyền dữ liệu thấp hơn so với SPI.

**Hoạt động:**

- Mỗi thiết bị trên bus I2C có một địa chỉ duy nhất.
- Trong quá trình truyền dữ liệu, Master tạo và điều khiển tín hiệu clock, còn Slave chỉ trả lời khi được yêu cầu.
- Master gửi địa chỉ của Slave cùng với lệnh (đọc hoặc ghi) qua dây SDA, và Slave trả lời xác nhận.
- Dữ liệu được truyền qua dây SDA theo chỉ đạo của tín hiệu clock từ SCL.

### Wi-Fi

Wi-Fi là công nghệ không dây cho phép kết nối thiết bị với mạng Internet hoặc LAN qua sóng radio. Nó có tốc độ và phạm vi kết nối khác nhau, hỗ trợ bảo mật và sử dụng trên nhiều loại thiết bị. Các thiết bị Wi-Fi phát sóng và nhận tín hiệu để kết nối, sau đó mã hóa dữ liệu để bảo vệ an toàn thông tin truyền qua mạng.
