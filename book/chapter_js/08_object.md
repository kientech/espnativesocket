## 📒 Object

Trong JavaScript, đối tượng (object) là một cấu trúc dữ liệu quan trọng được sử dụng để lưu trữ và thao tác dữ liệu dưới dạng các cặp khóa-giá trị (key-value). Mỗi khóa là một chuỗi (string) và giá trị có thể là bất kỳ kiểu dữ liệu nào, bao gồm các đối tượng khác, hàm, mảng, và các giá trị nguyên thủy như số, chuỗi, boolean.

### Khởi tạo đối tượng

Có nhiều cách để tạo đối tượng trong JavaScript:

`Sử dụng cặp dấu ngoặc nhọn {}`

```javascript
let person = {
  name: "John",
  age: 30,
  job: "Developer",
};
```

`Sử dụng từ khóa new Object()`

```javscript
let car = new Object();
car.make = 'Toyota';
car.model = 'Corolla';
car.year = 2020;
```

### Truy cập và thay đổi thuộc tính

Bạn có thể truy cập và thay đổi các thuộc tính của đối tượng bằng cách sử dụng dấu chấm (.) hoặc dấu ngoặc vuông ([]).

`Truy cập thuộc tính`

```javscript
console.log(person.name); // 'John'
console.log(car['model']); // 'Corolla'
```

`Thay đổi thuộc tính`

```javascript
person.age = 31;
car["year"] = 2021;
```

`Thêm thuộc tính mới`

```javascript
person.email = "john@example.com";
car.color = "blue";
```

`Xóa thuộc tính`
Bạn có thể xóa một thuộc tính khỏi đối tượng bằng từ khóa delete.

```javascript
delete person.job;
delete car.color;
```

Duyệt qua các thuộc tính của đối tượng
Sử dụng vòng lặp `for...in` để duyệt qua các thuộc tính của đối tượng.

```javascript
for (let key in person) {
  if (person.hasOwnProperty(key)) {
    console.log(`${key}: ${person[key]}`);
  }
}
// Output: name: John, age: 31, email: john@example.com
```

### Các phương thức của đối tượng

`Object.keys(obj)`
Trả về một mảng chứa tất cả các khóa của đối tượng.

```javascript
console.log(Object.keys(person)); // ['name', 'age', 'email']
Object.values(obj);
```

`Trả về một mảng chứa tất cả các giá trị của đối tượng.`

```javascript
console.log(Object.values(person)); // ['John', 31, 'john@example.com']
```

`Object.entries(obj)`
Trả về một mảng các cặp [key, value].

```javascript
console.log(Object.entries(person)); // [['name', 'John'], ['age', 31], ['email', 'john@example.com']]
```

`Đối tượng lồng nhau (Nested Objects)`
Đối tượng có thể chứa các đối tượng khác, cho phép bạn tạo ra các cấu trúc dữ liệu phức tạp.

```javascríp
let company = {
name: 'TechCorp',
employees: [
{ name: 'Alice', role: 'Engineer' },
{ name: 'Bob', role: 'Designer' }
],
address: {
street: '123 Tech Lane',
city: 'Innovate City',
zip: '12345'
}
};

console.log(company.name); // 'TechCorp'
console.log(company.employees[0].name); // 'Alice'
console.log(company.address.city); // 'Innovate City'
```

### Ví dụ tổng hợp sử dụng đối tượng

```javascript
let library = {
  books: [
    { title: "JavaScript: The Good Parts", author: "Douglas Crockford" },
    { title: "You Don’t Know JS", author: "Kyle Simpson" },
  ],
  addBook: function (book) {
    this.books.push(book);
  },
  listBooks: function () {
    this.books.forEach((book) => {
      console.log(`${book.title} by ${book.author}`);
    });
  },
};

library.addBook({ title: "Eloquent JavaScript", author: "Marijn Haverbeke" });
library.listBooks();
// Output:
// JavaScript: The Good Parts by Douglas Crockford
// You Don’t Know JS by Kyle Simpson
// Eloquent JavaScript by Marijn Haverbeke
```

Đối tượng trong JavaScript là một công cụ mạnh mẽ cho phép bạn lưu trữ, truy cập và thao tác dữ liệu theo cách có cấu trúc và có tổ chức. Việc hiểu cách sử dụng các đối tượng và các phương thức của chúng là một phần quan trọng trong việc trở thành một lập trình viên JavaScript thành thạo.
