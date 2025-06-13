# 🌬️ espnativesocket

**espnativesocket** là dự án xây dựng hệ thống giám sát và điều khiển tản nhiệt thời gian thực, sử dụng **ESP32** làm thiết bị nhúng và **React Native** làm ứng dụng di động. Giao tiếp giữa thiết bị và ứng dụng được thực hiện thông qua **WebSocket**, giúp truyền tải dữ liệu nhanh chóng, hai chiều và ổn định.

## 🚀 Tính năng chính

* 📡 Giao tiếp **ESP32 ↔ React Native** thông qua WebSocket.
* 📱 Ứng dụng di động hiển thị dữ liệu cảm biến (nhiệt độ, độ ẩm...).
* ⚙️ Điều khiển tốc độ quạt, trạng thái thiết bị từ xa.
* 🔄 Giao tiếp **real-time**, không cần polling.
* 🔐 Mã hóa WebSocket (có thể mở rộng HTTPS hoặc WSS).
* 🛠️ Mở rộng cho hệ thống IoT giám sát nhiệt độ quy mô lớn.

## 🧱 Kiến trúc hệ thống

```plaintext
+------------------+       WebSocket       +--------------------+
|  React Native App|  <------------------> |      ESP32         |
| (Client)         |                       | (WebSocket Server) |
+------------------+                       +--------------------+
```

## 📦 Thành phần dự án

* `esp32/`: mã nguồn cho ESP32, sử dụng Arduino framework.
* `app/`: mã nguồn ứng dụng React Native.
* `docs/`: tài liệu hướng dẫn, sơ đồ hệ thống.

## 🛠️ Yêu cầu hệ thống

### Cho ESP32

* ESP32 Dev Board (ví dụ: ESP32-WROOM-32)
* Arduino IDE hoặc PlatformIO
* Thư viện:

  * `WebSockets`
  * `WiFi`
  * `DHT` (nếu có cảm biến nhiệt độ)

### Cho App React Native

* Node.js >= 16.x
* React Native CLI hoặc Expo
* Thư viện:

  * `react-native-websocket`
  * `react-native-chart-kit` (tuỳ chọn)
  * `axios` (nếu cần gọi API)

## ⚙️ Cài đặt

### ESP32

1. Cấu hình WiFi và cổng WebSocket trong file `main.ino`:

   ```cpp
   const char* ssid = "YourSSID";
   const char* password = "YourPassword";
   WebSocketsServer webSocket = WebSocketsServer(81);
   ```

2. Upload code vào board bằng Arduino IDE hoặc PlatformIO.

### App React Native

```bash
cd app
npm install
npx react-native run-android # hoặc run-ios
```

Cập nhật địa chỉ IP ESP32 trong file cấu hình App.

## 🧪 Kiểm thử

* Mở App và kết nối tới ESP32 qua IP nội mạng.
* Theo dõi dữ liệu nhiệt độ thời gian thực.
* Thay đổi tốc độ quạt và xác nhận phản hồi từ ESP32.

## 📚 Tài liệu

* [Sơ đồ khối hệ thống](docs/system-architecture.md)
* [Cách ESP32 tạo WebSocket server](docs/esp32-websocket.md)
* [Hướng dẫn build App React Native](docs/react-native-setup.md)

## 📌 Lưu ý

* Thiết bị và điện thoại phải chung mạng LAN.
* IP của ESP32 có thể thay đổi theo mạng – nên dùng mDNS hoặc gán IP tĩnh.
---
