## ⏱️ Module I2C LCD

![](https://components101.com/sites/default/files/components/I2C-Serial-Interface-Adapter-Module.jpg)

LCD có quá nhiều nhiều chân gây khó khăn trong quá trình đấu nối và chiếm dụng nhiều chân trên vi điều khiển.
Module I2C LCD ra đời và giải quyết vấn để.
Thay vì phải mất 6 chân vi điều khiển để kết nối với LCD 16×2 (RS, EN, D7, D6, D5 và D4) thì module IC2 bạn chỉ cần tốn 2 chân (SCL, SDA) để kết nối. Module I2C hỗ trợ các loại LCD sử dụng driver HD44780(LCD 16×2, LCD 20×4, …) và tương thích với hầu hết các vi điều khiển hiện nay.

- Thông số kỹ thuật :
  - Điện áp hoạt động: 2.5-6V DC.
  - Hỗ trợ màn hình: LCD1602,1604,2004 (driver HD44780).
  - Giao tiếp: I2C.
  - Địa chỉ mặc định: 0X27 (có thể điều chỉnh bằng ngắn mạch chân A0/A1/A2).

Sơ đồ chân:
| Module I2C LCD 16×2 | Arduino UNO |
| ------------------- | ----------- |
| GND                 | GND         |
| VCC                 | 5V          |
| SDA                 | A4/SDA      |
| SCL                 | A5/SCL      |
