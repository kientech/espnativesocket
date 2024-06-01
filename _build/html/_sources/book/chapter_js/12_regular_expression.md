## 🕐 Biểu Thức Chính Quy

Biểu thức chính quy (regular expression, regex) là một công cụ mạnh mẽ trong JavaScript (và nhiều ngôn ngữ lập trình khác) để tìm kiếm và thao tác chuỗi. Biểu thức chính quy cung cấp một cách linh hoạt và hiệu quả để kiểm tra xem chuỗi có khớp với một mẫu cụ thể hay không, và để thực hiện các thao tác như tìm kiếm, thay thế và tách chuỗi.

### Tạo biểu thức chính quy

Có hai cách để tạo biểu thức chính quy trong JavaScript:

Sử dụng cặp dấu gạch chéo `/pattern/flags`

Sử dụng hàm tạo `RegExp(pattern, flags)`

```javascript
let regex1 = /abc/; // Biểu thức chính quy đơn giản
let regex2 = new RegExp("abc"); // Sử dụng hàm tạo

let regex3 = /abc/i; // Biểu thức chính quy với cờ (flag) 'i' (không phân biệt chữ hoa chữ thường)
let regex4 = new RegExp("abc", "i"); // Tương tự
```

### Các ký tự và mẫu cơ bản

#### Ký tự đặc biệt

- `.` Khớp với bất kỳ ký tự nào, trừ ký tự xuống dòng (\n).
- `\d`: Khớp với bất kỳ chữ số nào (0-9).
- `\D`: Khớp với bất kỳ ký tự nào không phải là chữ số.
- `\w`: Khớp với bất kỳ ký tự chữ cái, chữ số hoặc dấu gạch dưới.
- `\W`: Khớp với bất kỳ ký tự nào không phải là chữ cái, chữ số hoặc dấu gạch dưới.
- `\s`: Khớp với bất kỳ khoảng trắng nào (space, tab, newline).
- `\S`: Khớp với bất kỳ ký tự nào không phải là khoảng trắng.

#### Ký tự đặc biệt cho số lượng

- `*`: Khớp với ký tự trước đó 0 hoặc nhiều lần.
- `+`: Khớp với ký tự trước đó 1 hoặc nhiều lần.
- `?`: Khớp với ký tự trước đó 0 hoặc 1 lần. - `{n}`: Khớp với ký tự trước đó chính xác n lần.
- `{n,}`: Khớp với ký tự trước đó ít nhất n lần.
- `{n,m}`: Khớp với ký tự trước đó ít nhất n lần và nhiều nhất m lần.

#### Ký tự đặc biệt khác

- `^`: Khớp với vị trí bắt đầu của chuỗi.
- `$`: Khớp với vị trí kết thúc của chuỗi.
- `[]`: Khớp với bất kỳ ký tự nào trong dấu ngoặc vuông.
- `[^]`: Khớp với bất kỳ ký tự nào không nằm trong dấu ngoặc vuông.
- `|`: Biểu diễn phép OR (hoặc).
- `()`: Nhóm các ký tự lại với nhau.

### Ví dụ sử dụng biểu thức chính quy

#### Kiểm tra khớp chuỗi

```javascript
let regex = /hello/;
let str = "hello world";
console.log(regex.test(str)); // true
```

#### Tìm kiếm và khớp chuỗi

```javascript
let regex = /\d+/;
let str = "There are 123 apples";
let result = str.match(regex);
console.log(result); // ['123']
```

#### Thay thế chuỗi

```javascript
let regex = /apples/;
let str = "I have apples";
let newStr = str.replace(regex, "oranges");
console.log(newStr); // "I have oranges"
```

#### Tách chuỗi

```javascript
let regex = /\s+/;
let str = "split by spaces";
let result = str.split(regex);
console.log(result); // ['split', 'by', 'spaces']
```

### Các cờ (flags) trong biểu thức chính quy

- `g` (global): Khớp với tất cả các kết quả trong chuỗi, không chỉ cái đầu tiên.
- `i` (ignoreCase): Không phân biệt chữ hoa chữ thường.
- `m` (multiline): Khớp với vị trí bắt đầu và kết thúc ở mỗi dòng, không chỉ toàn bộ chuỗi.

```javascript
let regex = /hello/gi;
let str = "Hello HELLO hello";
let result = str.match(regex);
console.log(result); // ['Hello', 'HELLO', 'hello']
```

### Ví dụ nâng cao

#### Kiểm tra địa chỉ email hợp lệ

```javascript
let emailRegex = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
let email1 = "test@example.com";
let email2 = "invalid-email@";
console.log(emailRegex.test(email1)); // true
console.log(emailRegex.test(email2)); // false
```

#### Tìm và thay thế tất cả các số trong chuỗi

```javascript
let regex = /\d+/g;
let str = "The numbers are 12, 34, and 56.";
let newStr = str.replace(regex, "NUMBER");
console.log(newStr); // "The numbers are NUMBER, NUMBER, and NUMBER."
```

Biểu thức chính quy là một công cụ rất hữu ích và mạnh mẽ để làm việc với chuỗi trong JavaScript. Việc hiểu và sử dụng thành thạo biểu thức chính quy sẽ giúp bạn thực hiện các thao tác phức tạp với chuỗi một cách hiệu quả và nhanh chóng.
