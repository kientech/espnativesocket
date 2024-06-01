## 🧐 Hàm

Trong lập trình, hàm là một khối mã được đặt tên, có thể được gọi và thực thi một số công việc cụ thể. Hàm giúp bạn tái sử dụng mã, làm cho mã của bạn dễ đọc hơn và dễ bảo trì hơn. Trong JavaScript, hàm là một phần quan trọng của ngôn ngữ và có thể được sử dụng một cách linh hoạt để giải quyết các vấn đề khác nhau.

### Cú pháp

```javascript
function tên_hàm(tham_số1, tham_số2, ...) {
    // Khối mã của hàm
    return giá_trị; // không bắt buộc
}
```

### Các loại hàm

#### Hàm có tham số

```javascritp
function greet(name) {
    console.log("Xin chào, " + name + "!");
}
greet("Alice"); // Xuất: Xin chào, Alice!
```

#### Hàm có giá trị trả về

```javascript
function add(a, b) {
  return a + b;
}
let result = add(3, 4); // result = 7
```

#### Hàm không có tham số

```javascript
function sayHello() {
  console.log("Xin chào!");
}
sayHello(); // Xuất: Xin chào!
```

#### Hàm nặc danh (Anonymous function):

```javascript
let greet = function (name) {
  console.log("Xin chào, " + name + "!");
};
greet("Bob"); // Xuất: Xin chào, Bob!
```
