## ⏳ OOP 

### Giới thiệu về OOP trong JavaScript

Lập trình hướng đối tượng (Object-Oriented Programming - OOP) là một mô hình lập trình dựa trên khái niệm "đối tượng", trong đó mỗi đối tượng là một thực thể chứa dữ liệu (thuộc tính) và các phương thức (hành vi). JavaScript, mặc dù là ngôn ngữ lập trình hướng prototype, vẫn hỗ trợ mạnh mẽ cho OOP.

### Các khái niệm cơ bản trong OOP

1. **Lớp (Class)**: Là bản thiết kế cho đối tượng, mô tả các thuộc tính và phương thức của đối tượng.
2. **Đối tượng (Object)**: Là thể hiện cụ thể của lớp.
3. **Thuộc tính (Property)**: Là biến lưu trữ dữ liệu của đối tượng.
4. **Phương thức (Method)**: Là hàm thể hiện hành vi của đối tượng.
5. **Kế thừa (Inheritance)**: Là khả năng một lớp con kế thừa các thuộc tính và phương thức từ lớp cha.
6. **Đa hình (Polymorphism)**: Là khả năng các đối tượng có thể được xử lý theo nhiều cách khác nhau tùy thuộc vào lớp của chúng.
7. **Đóng gói (Encapsulation)**: Là việc che giấu dữ liệu của đối tượng, chỉ cho phép truy cập và sửa đổi thông qua các phương thức công khai.

### Tạo lớp và đối tượng trong JavaScript

#### Sử dụng ES6 Classes

```javascript
// Định nghĩa lớp Người (Person)
class Person {
    // Hàm khởi tạo
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }

    // Phương thức giới thiệu
    introduce() {
        console.log(`Xin chào, tôi là ${this.name} và tôi ${this.age} tuổi.`);
    }
}

// Tạo đối tượng
const person1 = new Person('Nam', 25);
person1.introduce();  // Output: Xin chào, tôi là Nam và tôi 25 tuổi.
```

#### Kế thừa trong JavaScript

```javascript
// Định nghĩa lớp SinhVien (Student) kế thừa từ lớp Người (Person)
class Student extends Person {
    constructor(name, age, studentID) {
        // Gọi hàm khởi tạo của lớp cha
        super(name, age);
        this.studentID = studentID;
    }

    // Phương thức giới thiệu (ghi đè phương thức của lớp cha)
    introduce() {
        console.log(`Xin chào, tôi là ${this.name}, tôi ${this.age} tuổi và mã sinh viên của tôi là ${this.studentID}.`);
    }
}

// Tạo đối tượng
const student1 = new Student('Linh', 20, 'SV123456');
student1.introduce();  // Output: Xin chào, tôi là Linh, tôi 20 tuổi và mã sinh viên của tôi là SV123456.
```

### Tính đa hình và đóng gói

#### Đa hình (Polymorphism)

```javascript
// Định nghĩa lớp GiáoVien (Teacher) kế thừa từ lớp Người (Person)
class Teacher extends Person {
    constructor(name, age, subject) {
        super(name, age);
        this.subject = subject;
    }

    // Phương thức giới thiệu (ghi đè phương thức của lớp cha)
    introduce() {
        console.log(`Xin chào, tôi là ${this.name}, tôi dạy môn ${this.subject}.`);
    }
}

// Hàm giới thiệu (sử dụng đa hình)
function introducePerson(person) {
    person.introduce();
}

const teacher1 = new Teacher('Hải', 30, 'Toán');
introducePerson(person1);   // Output: Xin chào, tôi là Nam và tôi 25 tuổi.
introducePerson(student1);  // Output: Xin chào, tôi là Linh, tôi 20 tuổi và mã sinh viên của tôi là SV123456.
introducePerson(teacher1);  // Output: Xin chào, tôi là Hải, tôi dạy môn Toán.
```

#### Đóng gói (Encapsulation)

```javascript
// Định nghĩa lớp BankAccount (Tài khoản ngân hàng)
class BankAccount {
    // Hàm khởi tạo
    constructor(owner, balance) {
        this.owner = owner;
        this._balance = balance;  // Thuộc tính đóng gói
    }

    // Phương thức lấy số dư
    getBalance() {
        return this._balance;
    }

    // Phương thức gửi tiền
    deposit(amount) {
        if (amount > 0) {
            this._balance += amount;
            console.log(`Đã gửi ${amount} vào tài khoản. Số dư mới: ${this._balance}`);
        } else {
            console.log('Số tiền gửi phải lớn hơn 0');
        }
    }

    // Phương thức rút tiền
    withdraw(amount) {
        if (amount > 0 && amount <= this._balance) {
            this._balance -= amount;
            console.log(`Đã rút ${amount} từ tài khoản. Số dư còn lại: ${this._balance}`);
        } else {
            console.log('Số tiền rút không hợp lệ');
        }
    }
}

// Tạo đối tượng
const myAccount = new BankAccount('An', 1000);
console.log(myAccount.getBalance());  // Output: 1000
myAccount.deposit(500);  // Output: Đã gửi 500 vào tài khoản. Số dư mới: 1500
myAccount.withdraw(300);  // Output: Đã rút 300 từ tài khoản. Số dư còn lại: 1200
myAccount.withdraw(2000);  // Output: Số tiền rút không hợp lệ
```

### Kết luận

Lập trình hướng đối tượng trong JavaScript giúp cho việc thiết kế và quản lý mã nguồn trở nên dễ dàng hơn bằng cách tổ chức mã theo các đối tượng và lớp. Việc sử dụng các khái niệm như kế thừa, đa hình, và đóng gói giúp tăng tính tái sử dụng và bảo trì của mã nguồn. Hãy thực hành và áp dụng OOP trong các dự án của bạn để thấy rõ những lợi ích mà nó mang lại.