## ✍️ Kiểm tra LM35

```c
/#include <Wire.h>
#include <LiquidCrystal_I2C.h>
LiquidCrystal_I2C lcd(0x27, 16, 2); // Địa chỉ I2C của màn hình LCD
const int lm35Pin1 = A0; // Chân nối cảm biến LM35 thứ nhất
const int lm35Pin2 = A1; // Chân nối cảm biến LM35 thứ hai
void setup() {
Serial.begin(9600);
lcd.init(); // Khởi động màn hình LCD
lcd.backlight(); // Bật đèn nền cho màn hình LCD
lcd.clear(); // Xóa màn hình LCD
}
void loop() {
float sum1 = 0, sum2 = 0;
int readings = 50; // Số lần đọc để lấy trung bình
// Đọc từng cảm biến LM35 và tính tổng
for (int i = 0; i < readings; i++) {
sum1 += analogRead(lm35Pin1) * 0.488; // Chuyển đổi giá trị analog sang nhiệt độ (0.488 mV đối với mỗi đơn vị analog)
sum2 += analogRead(lm35Pin2) * 0.488;
delay(10); // Đợi 10ms trước khi đọc lại
}
// Tính trung bình
float temp1 = sum1 / readings;
float temp2 = sum2 / readings;
// Hiển thị nhiệt độ lên màn hình LCD
lcd.setCursor(0, 0);
lcd.print("Temp1: ");
lcd.print(temp1);
lcd.print(" C");
lcd.setCursor(0, 1);
lcd.print("Temp2: ");
lcd.print(temp2);
lcd.print(" C");
}
```

**Kết Quả:**

![alt text](image.png)

Từ hình ảnh trên, kết quả ESP32 hoạt động tốt
