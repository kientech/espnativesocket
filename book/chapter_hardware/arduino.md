## 💎 Arduino Uno R3

![](https://lh3.googleusercontent.com/proxy/4fQ9s-WpLxZoNDwj6rdHP9GpiCXxn44ECngSlj6OqALFL5e2TDA1WbAgsGKr8Pu10WpNNlfBqURBb5mytg11Fhdzhn-2VjczQRhQdy9RhfcoeFFBNYkK29-Ox_YwFmv_XmB8X9Qc)

Arduino Uno R3 là một bảng mạch vi điều khiển nguồn mở dựa trên vi điều khiển Microchip ATmega328 được phát triển bởi Arduino. Bảng mạch được trang bị các bộ chân đầu vào/ đầu ra Digital và Analog có thể giao tiếp với các bảng mạch mở rộng khác nhau.

| Thông số                      | Giá trị                                         |
| ----------------------------- | ----------------------------------------------- |
| Vi điều khiển                 | ATmega328 họ 8bit                               |
| Điện áp hoạt động             | 5V DC (chỉ được cấp qua cổng USB)               |
| Tần số hoạt động              | 16 MHz                                          |
| Dòng tiêu thụ                 | khoảng 30mA                                     |
| Điện áp vào khuyên dùng       | 7-12V DC                                        |
| Điện áp vào giới hạn          | 6-20V DC                                        |
| Số chân Digital I/O           | 14 (6 chân hardware PWM)                        |
| Số chân Analog                | 6 (độ phân giải 10bit)                          |
| Dòng tối đa trên mỗi chân I/O | 30 mA                                           |
| Dòng ra tối đa (5V)           | 500 mA                                          |
| Dòng ra tối đa (3.3V)         | 50 mA                                           |
| Bộ nhớ flash                  | 32 KB (ATmega328) với 0.5KB dùng bởi bootloader |
| SRAM                          | 2 KB (ATmega328)                                |
| EEPROM                        | 1 KB (ATmega328)                                |

- Một số lưu ý khi dùng arduino:
  - Arduino UNO không có bảo vệ cắm ngược nguồn vào. Phải hết sức cẩn thận, kiểm tra các cực âm dương của nguồn trước khi cấp cho Arduino UNO.
  - Các chân 3.3V và 5V trên Arduino là các chân dùng để cấp nguồn ra cho các thiết bị khác, không phải là các chân cấp nguồn vào.
  - Cấp nguồn ngoài không qua cổng USB cho Arduino UNO với điện áp dưới 6V có thể làm hỏng board.
  - Cấp điện áp trên 13V vào chân RESET trên board có thể làm hỏng vi điều khiển ATmega328.
  - Cường độ dòng điện vào/ra ở tất cả các chân Digital và Analog của Arduino UNO nếu vượt quá 200mA sẽ làm hỏng vi điều khiển.
  - Cấp điệp áp trên 5.5V vào các chân Digital hoặc Analog của Arduino UNO sẽ làm hỏng vi điều khiển.
  - Cường độ dòng điện qua một chân Digital hoặc Analog bất kì của Arduino UNO vượt quá 40mA sẽ làm hỏng vi điều khiển.


