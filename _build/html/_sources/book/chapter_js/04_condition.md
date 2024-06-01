## 🤔 Câu Điều Kiện

Trong lập trình, việc thực hiện các hành động dựa trên điều kiện là điều rất phổ biến. Điều này có thể là xem xét các tình huống khác nhau, xử lý dữ liệu đầu vào khác nhau, hoặc điều chỉnh luồng của chương trình theo cách cụ thể. Trong JavaScript, chúng ta có các câu lệnh điều kiện mạnh mẽ để thực hiện những công việc này. Trong hướng dẫn này, chúng ta sẽ tìm hiểu về cú pháp và cách sử dụng của các câu lệnh điều kiện trong JavaScript, cùng với các ví dụ minh họa.

### Câu lệnh điều kiện if...else:

Câu lệnh này được sử dụng khi bạn muốn thực thi một khối mã nếu điều kiện là true và một khối mã khác nếu điều kiện là false.
**Cú pháp:**

```javascript
if (điều_kiện) {
  // Thực thi khi điều_kiện là true
} else {
  // Thực thi khi điều_kiện là false
}
```

**Ví dụ:**

````javascript
let age = 20;

if (age >= 18) {
    console.log("Bạn đã đủ tuổi để vào quán bar.");
} else {
    console.log("Bạn chưa đủ tuổi để vào quán bar.");
}```


````

### Câu lệnh điều kiện if...else if...else:

Câu lệnh này cho phép bạn kiểm tra nhiều điều kiện và thực thi các khối mã khác nhau tùy thuộc vào điều kiện nào được đáp ứng đầu tiên.

**Cú pháp:**

```javascript
if (điều_kiện1) {
  // Thực thi khi điều_kiện1 là true
} else if (điều_kiện2) {
  // Thực thi khi điều_kiện1 là false và điều_kiện2 là true
} else {
  // Thực thi khi cả điều_kiện1 và điều_kiện2 đều là false
}
```

**Ví dụ:**

```javascript
let score = 75;

if (score >= 90) {
  console.log("Xuất sắc!");
} else if (score >= 70) {
  console.log("Tốt!");
} else if (score >= 50) {
  console.log("Trung bình!");
} else {
  console.log("Yếu!");
}
```

### Câu lệnh điều kiện switch:

Câu lệnh switch được sử dụng để kiểm tra nhiều giá trị khác nhau của một biến và thực thi các khối mã tương ứng với từng giá trị.

Cú pháp:

```javascript
switch (biến) {
  case giá_trị1:
    // Thực thi khi biến có giá trị bằng giá_trị1
    break;
  case giá_trị2:
    // Thực thi khi biến có giá trị bằng giá_trị2
    break;
  default:
  // Thực thi khi biến không bằng bất kỳ giá trị nào trong các case trên
}
```

Ví dụ:

```javascript
let day = 3;
let dayName;

switch (day) {
  case 1:
    dayName = "Thứ Hai";
    break;
  case 2:
    dayName = "Thứ Ba";
    break;
  case 3:
    dayName = "Thứ Tư";
    break;
  case 4:
    dayName = "Thứ Năm";
    break;
  case 5:
    dayName = "Thứ Sáu";
    break;
  case 6:
    dayName = "Thứ Bảy";
    break;
  case 7:
    dayName = "Chủ Nhật";
    break;
  default:
    dayName = "Không xác định";
}
console.log("Hôm nay là: " + dayName);
```

### Toán tử ba ngôi (Ternary Operator)
Toán tử ba ngôi cung cấp một cách ngắn gọn để viết câu lệnh điều kiện if...else.

**Cú pháp:**
```javascript
biểu_thức ? giá_trị1 : giá_trị2;
```

**Ví dụ**
```javascript
let isAdult = age >= 18 ? "Đủ tuổi vào rạp xem phim" : "Chưa đủ tuổi vào rạp xem phim";
console.log(isAdult);
```

Các câu lệnh điều kiện trong JavaScript là công cụ mạnh mẽ để kiểm soát luồng của chương trình và thực hiện các hành động logic.