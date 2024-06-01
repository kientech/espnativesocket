## Tạo Một Dự Án Node.js và Tệp `server.js`

1. **Cài đặt Node.js**:
   - Đầu tiên, cài đặt [Node.js](https://nodejs.org/) trên máy tính của bạn nếu chưa có.

2. **Tạo Thư Mục Dự Án**:
   - Mở terminal hoặc command prompt và di chuyển đến thư mục nơi bạn muốn tạo dự án Node.js của mình.

3. **Khởi Tạo Một Dự Án Node.js**:
   - Chạy lệnh sau để khởi tạo một dự án Node.js mới:
     ```
     npm init -y
     ```

4. **Cài Đặt Các Module Cần Thiết (Nếu Cần)**:
   - Tùy thuộc vào yêu cầu cụ thể của dự án, bạn có thể cần cài đặt các module bổ sung. Ví dụ:
     ```
     npm install express
     ```

5. **Tạo Tệp `server.js`**:
   - Tạo một tệp mới trong thư mục dự án của bạn và đặt tên là `server.js`.

   - Dưới đây là một ví dụ đơn giản:
     ```javascript
     const express = require('express');
     const app = express();
     const port = 3000;

     app.get('/', (req, res) => {
       res.send('Hello World!');
     });

     app.listen(port, () => {
       console.log(`Server is running on http://localhost:${port}`);
     });
     ```

6. **Chạy Máy Chủ Node.js**:
   - Để chạy máy chủ Node.js của bạn, mở terminal hoặc command prompt, điều hướng đến thư mục dự án và chạy lệnh:
     ```
     node server.js
     ```
   - Bây giờ bạn có thể truy cập vào máy chủ của mình thông qua trình duyệt web tại `http://localhost:3000`.
