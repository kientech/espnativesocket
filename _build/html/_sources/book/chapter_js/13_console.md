## 💻 Console

Trong JavaScript, console là một đối tượng cung cấp nhiều phương thức để ghi thông tin ra bảng điều khiển (`console`). Điều này rất hữu ích cho việc gỡ lỗi (debugging) và kiểm tra các giá trị trong quá trình phát triển ứng dụng. Dưới đây là một số phương thức phổ biến của đối tượng `console`.

`console.log()`

Phương thức `console.log()` được sử dụng để ghi thông tin chung ra console.

```javascript
console.log("Hello, World!");
console.log(42);
console.log({ name: "Alice", age: 30 });
```

`console.error()`

Phương thức `console.error()` được sử dụng để ghi thông tin lỗi ra console. Thông thường, thông tin lỗi sẽ được hiển thị dưới dạng màu đỏ trong nhiều trình duyệt.

```javascript
console.error("This is an error message");
console.error(new Error("Something went wrong"));
```

`console.warn()`

Phương thức `console.warn()` được sử dụng để ghi cảnh báo ra console. Thông thường, thông tin cảnh báo sẽ được hiển thị dưới dạng màu vàng trong nhiều trình duyệt.

```javascript
console.warn("This is a warning message");
```

`console.info()`

Phương thức `console.info()` được sử dụng để ghi thông tin ra console. Nó tương tự như console.log(), nhưng có thể được định dạng khác nhau trong một số trình duyệt.

```javascript
console.info("This is an informational message");
```

`console.debug()`

Phương thức `console.debug()` được sử dụng để ghi thông tin gỡ lỗi ra console. Trong một số trình duyệt, thông tin này có thể được hiển thị khác với console.log().

```javascript
console.debug("This is a debug message");
```

`console.table()`

Phương thức `console.table()` được sử dụng để hiển thị dữ liệu dưới dạng bảng. Nó rất hữu ích để hiển thị mảng hoặc đối tượng theo cách dễ đọc.

```javascript
let people = [
  { name: "Alice", age: 30 },
  { name: "Bob", age: 25 },
  { name: "Charlie", age: 35 },
];
console.table(people);
```

`console.time() và console.timeEnd()`

Phương thức `console.time() và console.timeEnd()` được sử dụng để đo thời gian thực hiện của một đoạn mã.

```javascript
console.time("myTimer");
for (let i = 0; i < 1000000; i++) {
  // Some time-consuming operations
}
console.timeEnd("myTimer"); // Outputs the time taken to execute the loop
```

`console.group() và console.groupEnd()`

Phương thức `console.group() và console.groupEnd()` được sử dụng để nhóm các thông báo console. Điều này giúp tổ chức thông tin ghi ra console một cách rõ ràng hơn.

```javascript
console.group("Group 1");
console.log("Message 1");
console.log("Message 2");
console.groupEnd();

console.group("Group 2");
console.log("Message 3");
console.log("Message 4");
console.groupEnd();
```

`console.assert()`

Phương thức `console.assert()` được sử dụng để ghi thông báo lỗi nếu một biểu thức được đánh giá là sai.

```javascript
let x = 5;
console.assert(x === 10, "x is not 10");
```

`console.clear()`

Phương thức `console.clear()` được sử dụng để xóa tất cả các thông báo hiện tại trong console.

```javsscript
console.clear();
```

`console.trace()`

Phương thức `console.trace()` được sử dụng để ghi dấu vết (trace) ngăn xếp (stack trace) tại thời điểm nó được gọi.

```javascript
function foo() {
  function bar() {
    console.trace("Trace message");
  }
  bar();
}
foo();
```

Sử dụng các phương thức này sẽ giúp bạn dễ dàng theo dõi và kiểm soát quá trình thực thi mã của mình, từ đó phát hiện và sửa lỗi nhanh chóng và hiệu quả.
