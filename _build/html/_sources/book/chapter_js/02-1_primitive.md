## Kiểu Dữ Liệu Nguyên Thuỷ

Trong JavaScript, các kiểu dữ liệu nguyên thủy là các kiểu dữ liệu cơ bản không phải là đối tượng và không có phương thức. Trong bài viết này, chúng ta sẽ khám phá và hiểu rõ hơn về các kiểu dữ liệu nguyên thủy trong JavaScript.

### Number 
Kiểu dữ liệu `Number` trong JavaScript được sử dụng để biểu diễn các giá trị số, bao gồm cả số nguyên và số thực.

```javascript
let age = 25; // Số nguyên
let pi = 3.14; // Số thực
```

### String
Chuỗi là một chuỗi các ký tự trong JavaScript, được bao quanh bởi dấu ngoặc đơn ('') hoặc dấu nháy kép ("") hoặc dấu backtick (``).

```javascript
let message = "Hello, world!";
let name = 'SmartCooling';
let project = `esp32 react native and websocket`
```


### Boolean
Kiểu dữ liệu Boolean chỉ có hai giá trị: true hoặc false. Được sử dụng để biểu diễn trạng thái logic
```javascript
let isTrue = true;
let isFalse = false;
```

### Null và Undefined
null và undefined là hai giá trị đặc biệt trong JavaScript. Null được sử dụng để chỉ định rằng một biến không có giá trị hoặc tham chiếu đến bất kỳ đối tượng nào. Undefined được sử dụng khi một biến đã được khai báo nhưng chưa được gán giá trị.

```javascript
let nullValue = null;
let undefinedValue;
```

### Symbol
Symbol là một kiểu dữ liệu mới được giới thiệu trong ES6, được sử dụng để tạo ra các giá trị không thể thay đổi và không trùng lặp

```javascript
let sym1 = Symbol("sym");
let sym2 = Symbol("sym");
console.log(sym1 === sym2); // false
```
Trong JavaScript, các kiểu dữ liệu nguyên thủy được truyền theo giá trị, nghĩa là khi bạn sao chép một biến, bạn sẽ sao chép giá trị của nó. Hiểu rõ về các kiểu dữ liệu nguyên thủy là quan trọng để làm việc hiệu quả với dữ liệu trong chương trình JavaScript của bạn.