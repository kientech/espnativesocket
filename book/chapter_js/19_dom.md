## 🎬 DOM

### Mô hình Đối tượng Tài liệu (DOM) - Ngày 1

Tài liệu HTML được cấu trúc như một Đối tượng JavaScript. Mỗi phần tử HTML có các thuộc tính khác nhau giúp thao tác với nó. Có thể lấy, tạo, thêm hoặc xóa các phần tử HTML bằng JavaScript. Kiểm tra các ví dụ dưới đây. Việc chọn phần tử HTML bằng JavaScript tương tự như việc chọn bằng CSS. Để chọn một phần tử HTML, chúng ta sử dụng tên thẻ, id, tên lớp hoặc các thuộc tính khác.

#### Lấy Phần Tử

Chúng ta có thể truy cập hoặc lấy các phần tử đã được tạo sẵn bằng JavaScript. Để truy cập hoặc lấy các phần tử, chúng ta sử dụng các phương thức khác nhau. Mã dưới đây có bốn phần tử _h1_. Hãy xem các phương pháp khác nhau để truy cập các phần tử _h1_.

```html
<!DOCTYPE html>
<html lang="vi">
  <head>
    <title>Mô hình Đối tượng Tài liệu</title>
  </head>
  <body>
    <h1 class="title" id="first-title">Tiêu đề Thứ Nhất</h1>
    <h1 class="title" id="second-title">Tiêu đề Thứ Hai</h1>
    <h1 class="title" id="third-title">Tiêu đề Thứ Ba</h1>
    <h1></h1>
  </body>
</html>
```

##### Lấy phần tử bằng tên thẻ

**_getElementsByTagName()_**: nhận một chuỗi tên thẻ làm tham số và phương thức này trả về một đối tượng HTMLCollection. Một HTMLCollection là một đối tượng giống như mảng của các phần tử HTML. Thuộc tính độ dài cung cấp kích thước của bộ sưu tập. Khi nào chúng ta sử dụng phương thức này, chúng ta truy cập các phần tử cá nhân bằng cách sử dụng chỉ mục hoặc sau khi lặp qua từng mục cá nhân. Một HTMLCollection không hỗ trợ tất cả các phương thức của mảng, do đó chúng ta nên sử dụng vòng lặp for thông thường thay vì forEach.

```js
// cú pháp
document.getElementsByTagName("tenthẻ");
```

```js
const allTitles = document.getElementsByTagName("h1");

console.log(allTitles); // HTMLCollections
console.log(allTitles.length); // 4

for (let i = 0; i < allTitles.length; i++) {
  console.log(allTitles[i]); // in từng phần tử trong HTMLCollection
}
```

##### Lấy phần tử bằng tên lớp

Phương thức **_getElementsByClassName()_** trả về một đối tượng HTMLCollection. Một HTMLCollection là một danh sách giống mảng của các phần tử HTML. Thuộc tính độ dài cung cấp kích thước của bộ sưu tập. Có thể lặp qua tất cả các phần tử HTMLCollection. Xem ví dụ dưới đây.

```js
// cú pháp
document.getElementsByClassName("tên lớp");
```

```js
const allTitles = document.getElementsByClassName("title");

console.log(allTitles); // HTMLCollections
console.log(allTitles.length); // 4

for (let i = 0; i < allTitles.length; i++) {
  console.log(allTitles[i]); // in từng phần tử trong HTMLCollection
}
```

##### Lấy một phần tử bằng id

**_getElementById()_** chỉ định một phần tử HTML duy nhất. Chúng ta truyền id mà không có # như một đối số.

```js
// cú pháp
document.getElementById("id");
```

```js
let firstTitle = document.getElementById("first-title");
console.log(firstTitle); // <h1>Tiêu đề Thứ Nhất</h1>
```

##### Lấy phần tử bằng cách sử dụng phương thức querySelector

Phương thức _document.querySelector_ có thể chọn một phần tử HTML hoặc các phần tử HTML theo tên thẻ, theo id hoặc theo tên lớp.

**_querySelector_**: có thể được sử dụng để chọn phần tử HTML theo tên thẻ, id hoặc lớp. Nếu sử dụng tên thẻ, nó chỉ chọn phần tử đầu tiên.

```js
let firstTitle = document.querySelector("h1"); // chọn phần tử h1 đầu tiên có sẵn
let firstTitle = document.querySelector("#first-title"); // chọn id với first-title
let firstTitle = document.querySelector(".title"); // chọn phần tử đầu tiên có sẵn với lớp title
```

**_querySelectorAll_**: có thể được sử dụng để chọn các phần tử html theo tên thẻ hoặc lớp của nó. Nó trả về một nodeList là một đối tượng giống mảng hỗ trợ các phương thức mảng. Chúng ta có thể sử dụng **_for loop_** hoặc **_forEach_** để lặp qua từng phần tử nodeList.

```js
const allTitles = document.querySelectorAll('h1') # chọn tất cả các phần tử h1 có sẵn trong trang

console.log(allTitles.length) // 4
for (let i = 0; i < allTitles.length; i++) {
  console.log(allTitles[i])
}

allTitles.forEach(title => console.log(title))
const allTitles```js
= document.querySelectorAll('.title') // tương tự khi chọn bằng lớp
```

### Thêm thuộc tính

Một thuộc tính được thêm vào thẻ mở của HTML để cung cấp thông tin bổ sung về phần tử. Các thuộc tính HTML phổ biến: id, class, src, style, href, disabled, title, alt. Hãy thêm id và class cho tiêu đề thứ tư.

```js
const titles = document.querySelectorAll("h1");
titles[3].className = "title";
titles[3].id = "fourth-title";
```

#### Thêm thuộc tính bằng cách sử dụng setAttribute

Phương thức **_setAttribute()_** đặt bất kỳ thuộc tính html nào. Nó nhận hai tham số là loại thuộc tính và tên của thuộc tính. Hãy thêm các thuộc tính class và id cho tiêu đề thứ tư.

```js
const titles = document.querySelectorAll("h1");
titles[3].setAttribute("class", "title");
titles[3].setAttribute("id", "fourth-title");
```

#### Thêm thuộc tính mà không sử dụng setAttribute

Chúng ta có thể sử dụng phương pháp thiết lập thuộc tính đối tượng bình thường để đặt một thuộc tính nhưng điều này không thể hoạt động cho tất cả các phần tử. Một số thuộc tính là thuộc tính đối tượng DOM và chúng có thể được đặt trực tiếp. Ví dụ: id và class

```js
//cách khác để đặt thuộc tính
titles[3].className = "title";
titles[3].id = "fourth-title";
```

#### Thêm class bằng classList

Phương thức classList là một phương pháp tốt để thêm lớp bổ sung. Nó không ghi đè lớp ban đầu nếu một lớp tồn tại mà nó thêm lớp bổ sung cho phần tử.

```js
//cách khác để đặt thuộc tính: thêm lớp, không ghi đè
titles[3].classList.add("title", "header-title");
```

#### Xóa class bằng remove

Tương tự như việc thêm, chúng ta cũng có thể xóa lớp khỏi một phần tử. Chúng ta có thể xóa một lớp cụ thể khỏi một phần tử.

```js
//cách khác để đặt thuộc tính: thêm lớp, không ghi đè
titles[3].classList.remove("title", "header-title");
```

### Thêm Văn Bản vào Phần Tử HTML

Một HTML được xây dựng bởi một thẻ mở, một thẻ đóng và một nội dung văn bản. Chúng ta có thể thêm nội dung văn bản bằng thuộc tính _textContent_ hoặc \*innerHTML.

#### Thêm nội dung văn bản bằng textContent

Thuộc tính _textContent_ được sử dụng để thêm văn bản vào một phần tử HTML.

```js
const titles = document.querySelectorAll("h1");
titles[3].textContent = "Tiêu đề Thứ Tư";
```

#### Thêm Nội Dung Văn Bản bằng innerHTML

Nhiều người thường nhầm lẫn giữa _textContent_ và _innerHTML_. _textContent_ được sử dụng để thêm văn bản vào một phần tử HTML, tuy nhiên _innerHTML_ có thể thêm một phần tử HTML hoặc các phần tử là con.

##### Nội dung Văn Bản

Chúng ta gán thuộc tính đối tượng _textContent_ cho một văn bản

```js
const titles = document.querySelectorAll("h1");
titles[3].textContent = "Tiêu đề Thứ Tư";
```

##### Inner HTML

Chúng ta sử dụng thuộc tính innerHTML khi chúng ta muốn thay thế hoặc thêm một nội dung con hoàn toàn mới cho một phần tử cha.
Giá trị chúng ta gán sẽ là một chuỗi của các phần tử HTML.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>JavaScript cho Mọi Người:DOM</title>
  </head>
  <body>
    <div class="wrapper">
      <h1>Những Thách Thức của Asabeneh Yetayeh trong năm 2020</h1>
      <h2>Thách Thức 30 Ngày Của JavaScript</h2>
      <ul></ul>
    </div>
    <script>
      const lists = `
    <li>Thách Thức 30 Ngày của Python Đã Hoàn Thành</li>
            <li>Thách Thức 30 Ngày của JavaScript Đang Tiếp Tục</li>
            <li>Thách Thức 30 Ngày của React Sắp Tới</li>
            <li>Thách Thức 30 Ngày của FullStack Sắp Tới</li>
            <li>Thách Thức 30 Ngày của Data Analysis Sắp Tới</li>
            <li>Thách Thức 30 Ngày của React Native Sắp Tới</li>
            <li>Thách Thức 30 Ngày của Machine Learning Sắp Tới</li>`;
      const ul = document.querySelector("ul");
      ul.innerHTML = lists;
    </script>
  </body>
</html>
```

Thuộc tính innerHTML cũng cho phép chúng ta loại bỏ tất cả các phần tử con của một phần tử cha. Thay vì sử dụng removeChild() tôi khuyên bạn nên sử dụng phương pháp sau.

```html
<!DOCTYPE html>
<html lang```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>JavaScript for Everyone: DOM</title>
  </head>
  <body>
    <div class="wrapper">
      <h1>Thách Thức của Asabeneh Yetayeh trong năm 2020</h1>
      <h2>Thách Thức 30 Ngày Của JavaScript</h2>
      <ul>
        <li>Thách Thức 30 Ngày của Python Đã Hoàn Thành</li>
        <li>Thách Thức 30 Ngày của JavaScript Đang Tiếp Tục</li>
        <li>Thách Thức 30 Ngày của React Sắp Tới</li>
        <li>Thách Thức 30 Ngày của FullStack Sắp Tới</li>
        <li>Thách Thức 30 Ngày của Data Analysis Sắp Tới</li>
        <li>Thách Thức 30 Ngày của React Native Sắp Tới</li>
        <li>Thách Thức 30 Ngày của Machine Learning Sắp Tới</li>
      </ul>
    </div>
    <script>
      const ul = document.querySelector("ul");
      ul.innerHTML = "";
    </script>
  </body>
</html>
```

### Thêm kiểu dáng

#### Thêm Màu Sắc

Hãy thêm một số kiểu dáng cho các tiêu đề của chúng ta. Nếu phần tử có chỉ số chẵn, chúng ta sẽ đặt màu xanh lá cây, ngược lại đặt màu đỏ.

```js
const titles = document.querySelectorAll("h1");
titles.forEach((title, i) => {
  title.style.fontSize = "24px"; // tất cả các tiêu đề sẽ có kích thước font 24px
  if (i % 2 === 0) {
    title.style.color = "green";
  } else {
    title.style.color = "red";
  }
});
```

#### Thêm Màu Nền

Hãy thêm một số kiểu dáng cho các tiêu đề của chúng ta. Nếu phần tử có chỉ số chẵn, chúng ta sẽ đặt màu nền xanh lá cây, ngược lại đặt màu nền đỏ.

```js
const titles = document.querySelectorAll("h1");
titles.forEach((title, i) => {
  title.style.fontSize = "24px"; // tất cả các tiêu đề sẽ có kích thước font 24px
  if (i % 2 === 0) {
    title.style.backgroundColor = "green";
  } else {
    title.style.backgroundColor = "red";
  }
});
```

#### Thêm Kích Thước Font

Hãy thêm một số kiểu dáng cho các tiêu đề của chúng ta. Nếu phần tử có chỉ số chẵn, chúng ta sẽ đặt kích thước font là 20px, ngược lại là 30px.

```js
const titles = document.querySelectorAll("h1");
titles.forEach((title, i) => {
  title.style.fontSize = "24px"; // tất cả các tiêu đề sẽ có kích thước font 24px
  if (i % 2 === 0) {
    title.style.fontSize = "20px";
  } else {
    title.style.fontSize = "30px";
  }
});
```

Như bạn đã nhận thấy, các thuộc tính của css khi sử dụng trong JavaScript sẽ là dạng camelCase. Các thuộc tính CSS sau khi chúng ta sử dụng trong JavaScript sẽ được viết hoa chữ cái đầu tiên. Ví dụ: background-color sẽ thành backgroundColor, font-size sẽ thành fontSize, font-family sẽ thành fontFamily, margin-bottom sẽ thành marginBottom.

---

 Bạn đã học DOM và bây giờ bạn có khả năng xây dựng và phát triển ứng dụng.
