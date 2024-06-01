## 🧨 Xử Lý Lỗi

Xử Lý Lỗi Trong JavaScript
JavaScript là một ngôn ngữ kiểu lỏng (loosely-typed), do đó, đôi khi bạn sẽ gặp lỗi khi chạy nếu cố gắng truy cập vào một biến không xác định hoặc gọi một hàm không được định nghĩa. Tương tự như Python hay Java, JavaScript cung cấp cơ chế xử lý lỗi thông qua các khối try-catch-finally.

### Cấu Trúc try-catch-finally

Cấu trúc try-catch-finally bao gồm ba phần chính:

- **try**: Chứa đoạn mã có thể gây ra lỗi. Khối try cho phép định nghĩa một khối mã để kiểm tra lỗi khi thực thi.
- **catch**: Được kích hoạt khi có lỗi xảy ra trong khối try. Khối catch có thể có tham số để nhận thông tin lỗi, thường được đặt tên là e, err hoặc error.
- **finally**: Được thực thi bất kể lỗi có xảy ra hay không. Khối finally có thể được sử dụng để hoàn thành các tác vụ còn lại hoặc đặt lại các biến đã thay đổi trước khi lỗi xảy ra.

Ví dụ:

```javascript
try {
  let lastName = "Yetayeh";
  let fullName = fistName + " " + lastName; // fistName chưa được định nghĩa
} catch (err) {
  console.log(err);
}
```

Kết quả:

```javascript
ReferenceError: fistName is not defined
    at <anonymous>:4:20
```

### Thêm Khối finally

```javascript
try {
  let lastName = "Yetayeh";
  let fullName = fistName + " " + lastName;
} catch (err) {
  console.error(err); // Có thể sử dụng console.log() hoặc console.error()
} finally {
  console.log("Dù thế nào đi nữa thì dòng này vẫn sẽ được thực thi");
}
```

Kết quả:

```javascript
ReferenceError: fistName is not defined
    at <anonymous>:4:20
Dù thế nào đi nữa thì dòng này vẫn sẽ được thực thi
```

### Sử Dụng Tham Số Trong Khối catch

Tham số của khối catch là một đối tượng chứa thông tin về lỗi, với các thuộc tính name và message.

```javascript
try {
  let lastName = "Yetayeh";
  let fullName = fistName + " " + lastName;
} catch (err) {
  console.log("Tên lỗi:", err.name);
  console.log("Thông báo lỗi:", err.message);
} finally {
  console.log("Dù sao tôi vẫn sẽ được thực thi");
}
```

Kết quả:

```javascript
Tên lỗi: ReferenceError
Thông báo lỗi: fistName is not defined
Dù sao tôi vẫn sẽ được thực thi
```

### Tạo Lỗi Tùy Chỉnh Với throw

Câu lệnh throw cho phép tạo ra lỗi tùy chỉnh. Bạn có thể ném ra một chuỗi, số, boolean hoặc đối tượng.

```javascript
throw "Error2"; // Ném ra một lỗi với giá trị chuỗi
throw 42; // Ném ra một lỗi với giá trị số
throw true; // Ném ra một lỗi với giá trị boolean
throw new Error("Required"); // Ném ra một đối tượng lỗi với thông điệp Required
```

Ví Dụ Về Hàm Tạo Lỗi Tùy Chỉnh

```javascript
const throwErrorExampleFun = () => {
  let message;
  let x = prompt("Nhập một số: ");
  try {
    if (x == "") throw "trống";
    if (isNaN(x)) throw "không phải số";
    x = Number(x);
    if (x < 5) throw "quá thấp";
    if (x > 10) throw "quá cao";
  } catch (err) {
    console.log(err);
  }
};
throwErrorExampleFun();
```
