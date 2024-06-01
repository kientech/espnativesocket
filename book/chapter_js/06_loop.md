## 🔁 Vòng Lặp

Trong lập trình, vòng lặp là một cách tiện lợi để thực hiện một khối mã nhiều lần cho đến khi một điều kiện nhất định không còn đúng nữa. JavaScript cung cấp các cấu trúc vòng lặp để thực hiện công việc này, cho phép bạn lặp lại một phần mã hoặc một tập hợp mã nhiều lần một cách linh hoạt.

### Vòng lặp for

Vòng lặp for thường được sử dụng khi bạn biết trước số lần lặp cụ thể hoặc khi bạn muốn lặp lại qua các phần tử trong một mảng.
**Cú pháp**

```javascript
for (biểu_thức_khởi_đầu; điều_kiện; biểu_thức_tăng / giảm) {
  // Khối mã được thực thi
}
```

**Ví dụ**

```javascript
for (let i = 0; i < 5; i++) {
  console.log("Số thứ tự: " + i);
}
```

### Vòng lặp while

Vòng lặp while thực hiện một khối mã miễn là điều kiện là true. Nó thích hợp khi số lần lặp không xác định từ đầu.

**Cú pháp**

```javascript
while (điều_kiện) {
  // Khối mã được thực thi
}
```

**Ví dụ**:

```javascript
let count = 0;
while (count < 5) {
  console.log("Số thứ tự: " + count);
  count++;
}
```

### Vòng lặp do...while

Vòng lặp do...while thực hiện một khối mã ít nhất một lần trước khi kiểm tra điều kiện. Nó hữu ích khi bạn muốn đảm bảo rằng một khối mã được thực thi ít nhất một lần.

**Cú pháp:**

```javascript
do {
  // Khối mã được thực thi
} while (điều_kiện);
```

**Ví dụ**:

```javascript
let x = 5;
do {
  console.log("Số thứ tự: " + x);
  x++;
} while (x < 5);
```

Vòng lặp là một phần quan trọng của lập trình, cho phép bạn lặp lại một khối mã nhiều lần một cách hiệu quả. JavaScript cung cấp các cấu trúc vòng lặp phổ biến như for, while và do...while để giúp bạn thực hiện công việc lặp lại một cách dễ dàng và linh hoạt. Đảm bảo bạn hiểu và sử dụng chúng một cách hiệu quả trong mã của mình!