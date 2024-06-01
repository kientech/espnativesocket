## 💡 Các Toán Tử

JavaScript cung cấp nhiều loại toán tử khác nhau để thao tác với dữ liệu. Dưới đây là hướng dẫn chi tiết về các loại toán tử này.

### Toán Tử Số Học (Arithmetic Operators)

| Toán tử | Mô tả              | Ví dụ    |
| ------- | ------------------ | -------- |
| `+`     | Cộng               | `5 + 2`  |
| `-`     | Trừ                | `5 - 2`  |
| `*`     | Nhân               | `5 * 2`  |
| `/`     | Chia               | `5 / 2`  |
| `%`     | Chia lấy dư        | `5 % 2`  |
| `++`    | Tăng thêm 1 đơn vị | `i++`    |
| `--`    | Giảm 1 đơn vị      | `i--`    |
| `**`    | Lũy thừa           | `5 ** 2` |

```javascript
let a = 5;
let b = 2;
console.log(a + b); // 7
console.log(a - b); // 3
console.log(a * b); // 10
console.log(a / b); // 2.5
console.log(a % b); // 1
console.log(a ** b); // 25
```

### Toán Tử Gán (Assignment Operators)

| Toán tử | Mô tả              | Ví dụ      |
| ------- | ------------------ | ---------- |
| `=`     | Gán                | `x = y `   |
| `+=`    | Cộng và gán        | `x += y `  |
| `-=`    | Trừ và gán         | `x -= y `  |
| `*=`    | Nhân và gán        | `x *= y `  |
| `/=`    | Chia và gán        | `x /= y `  |
| `%=`    | Chia lấy dư và gán | `x %= y `  |
| `**=`   | Lũy thừa và gán    | `x **= y ` |

```javascript
let x = 10;
x += 5; // x = x + 5
console.log(x); // 15
x -= 2; // x = x - 2
console.log(x); // 13
x *= 3; // x = x * 3
console.log(x); // 39
```

### Toán Tử So Sánh (Comparison Operators)

| Toán tử | Mô tả                                   | Ví dụ       |
| ------- | --------------------------------------- | ----------- |
| `==`    | So sánh bằng                            | `5 == 5`    |
| `===`   | So sánh bằng (cả giá trị và kiểu)       | `5 === '5'` |
| `!=`    | So sánh không bằng                      | `5 != 3`    |
| `!==`   | So sánh không bằng (cả giá trị và kiểu) | `5 !== '5'` |
| `>`     | Lớn hơn                                 | `5 > 2`     |
| `<`     | Nhỏ hơn                                 | `5 < 8 `    |
| `>=`    | Lớn hơn hoặc bằng                       | `5 >= 5`    |
| `<=`    | Nhỏ hơn hoặc bằng                       | `5 <= 8`    |

```javascript
let a = 5;
let b = "5";
console.log(a == b); // true
console.log(a === b); // false
console.log(a != b); // false
console.log(a !== b); // true
console.log(a > 3); // true
console.log(a < 10); // true
console.log(a >= 5); // true
console.log(a <= 8); // true
```

### Toán Tử Logic (Logical Operators)

| Toán tử | Mô tả          | Ví dụ           |
| ------- | -------------- | --------------- |
| `&&`    | Và (AND)       | `true && false` |
| `!`     | Phủ định (NOT) | `!true`         |
| `⎮⎮`    | Hoặc (OR)      | `true ⎮⎮ false` |

```javascript
let a = true;
let b = false;
console.log(a && b); // false
console.log(a || b); // true
console.log(!a); // false
console.log(!b); // true
```

### Kết Luận

Như vậy, JavaScript cung cấp một loạt các toán tử mạnh mẽ và đa dạng để thao tác với dữ liệu. Hiểu rõ cách sử dụng các toán tử này sẽ giúp bạn viết mã JavaScript hiệu quả hơn và dễ bảo trì hơn.
