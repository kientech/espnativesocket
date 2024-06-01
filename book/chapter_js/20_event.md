# 🎨 Sự kiện


### Sự Kiện

Các sự kiện HTML phổ biến: onclick, onchange, onmouseover, onmouseout, onkeydown, onkeyup, onload. Chúng ta có thể thêm phương thức sự kiện cho bất kỳ đối tượng DOM nào. Chúng ta sử dụng phương thức **_addEventListener()_** để lắng nghe các loại sự kiện khác nhau trên các phần tử HTML. Phương thức _addEventListener()_ nhận hai đối số, một sự kiện và một hàm gọi lại.

```js
selectedElement.addEventListener("sự_kiện", function (e) {
  // các hoạt động bạn muốn thực hiện sau sự kiện sẽ được thực hiện ở đây
});
// hoặc

selectedElement.addEventListener("sự_kiện", (e) => {
  // các hoạt động bạn muốn thực hiện sau sự kiện sẽ được thực hiện ở đây
});
```

#### Nhấp Chuột

Để gắn một sự kiện cho một phần tử, trước tiên chúng ta chọn phần tử đó sau đó gắn phương thức addEventListener. Sự kiện nhận loại sự kiện và hàm gọi lại là đối số.

Dưới đây là một ví dụ về sự kiện loại nhấp chuột.

**Ví dụ: nhấp chuột**

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Document Object Model</title>
  </head>

  <body>
    <button>Click Me</button>

    <script>
      const button = document.querySelector("button");
      button.addEventListener("click", (e) => {
        console.log("e cung cấp đối tượng sự kiện:", e);
        console.log("e.target cung cấp phần tử đã chọn: ", e.target);
        console.log(
          "e.target.textContent cung cấp nội dung của phần tử đã chọn: ",
          e.target.textContent
        );
      });
    </script>
  </body>
</html>
```

Một sự kiện cũng có thể được gắn trực tiếp vào phần tử HTML dưới dạng mã kịch bản trong dòng.

**Ví dụ: onclick**

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Document Object Model</title>
  </head>

  <body>
    <button onclick="clickMe()">Click Me</button>
    <script>
      const clickMe = () => {
        alert("Chúng ta có thể gắn sự kiện trên phần tử HTML");
      };
    </script>
  </body>
</html>
```

#### Nhấp Đúp Chuột

Để gắn một sự kiện cho một phần tử, trước tiên chúng ta chọn phần tử đó sau đó gắn phương thức addEventListener. sự kiện nhận loại sự kiện và hàm gọi lại là đối số.

Dưới đây là một ví dụ về sự kiện loại nhấp chuột.
**Ví dụ: dblclick**

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Document Object Model</title>
  </head>

  <body>
    <button>Click Me</button>
    <script>
      const button = document.querySelector("button");
      button.addEventListener("dblclick", (e) => {
        console.log("e cung cấp đối tượng sự kiện:", e);
        console.log("e.target cung cấp phần tử đã chọn: ", e.target);
        console.log(
          "e.target.textContent cung cấp nội dung của phần tử đã chọn: ",
          e.target.textContent
        );
      });
    </script>
  </body>
</html>
```

#### Rê Chuột vào

Để gắn một sự kiện cho một phần tử, trước tiên chúng ta chọn phần tử đó sau đó gắn phương thức addEventListener. sự kiện nhận loại sự kiện và hàm gọi lại là đối số.

Dưới đây là một ví dụ về sự kiện loại nhấp chuột.

**Ví dụ: mouseenter**

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Document Object Model</title>
  </head>

  <body>
    <button>Click Me</button>
    <script>
      const button = document.querySelector("button");
      button.addEventListener("mouseenter", (e) => {
        console.log("e cung cấp đối tượng sự kiện:", e);
        console.log("e.target cung cấp phần tử đã chọn: ", e.target);
        console.log(
          "e.target.textContent cung cấp nội dung của phần tử đã chọn: ",
          e.target.textContent
        );
      });
    </script>
  </body>
</html>
```

Bây giờ bạn đã quen với phương thức addEventListen và cách gắn sự kiện. Có nhiều loại sự kiện. Nhưng trong thách thức này, chúng ta sẽ tập trung vào các sự kiện quan trọng phổ biến nhất.
Danh sách các sự kiện:

- click - khi phần tử được nhấp chuột
- dblclick - khi phần tử được nhấp đúp chuột
- mouseenter - khi con trỏ chuột nhập vào phần tử
- mouseleave - khi con trỏ chuột rời khỏi phần tử
- mousemove - khi con trỏ chuột di chuyển trên phần tử
- mouseover - khi con trỏ chuột di chuyển trên phần tử
- mouseout - khi con trỏ chuột rời khỏi phần tử
- input - khi giá trị được nhập vào trường input
- change - khi giá trị thay đổi trên trường input
- blur - khi phần tử không được tập trung
- keydown - khi một phím được nhấn xuống
- keyup - khi một phím được nhả ra
- keypress - khi chúng ta nhấn vào bất kỳ phím nào
- onload - khi trình duyệt đã hoàn thành tải một trang

Thử các loại sự kiện trên bằng cách thay đổi loại sự kiện trong đoạn mã mẫu ở trên.

### Lấy giá trị từ một phần tử input

Chúng ta thường điền các biểu mẫu và biểu mẫu chấp nhận dữ liệu. Các trường biểu mẫu được tạo bằng cách sử dụng phần tử input HTML. Hãy xây dựng một ứng dụng nhỏ cho phép chúng ta tính chỉ số khối cơ thể của một người bằng cách sử dụng hai trường input, một nút và một thẻ p.

### Giá trị đầu vào

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Document Object Model:30 Ngày JavaScript</title>
  </head>

  <body>
    <h1>Máy Tính Chỉ Số Khối Cơ Thể</h1>

    <input type="text" id="mass" placeholder="Khối lượng trong Kilogram" />
    <input type="text" id="height" placeholder="Chiều cao trong mét" />
    <button>Tính chỉ số BMI</button>

    <script>
      const mass = document.querySelector("#mass");
      const height = document.querySelector("#height");
      const button = document.querySelector("button");

      let bmi;
      button.addEventListener("click", () => {
        bmi = mass.value / height.value ** 2;
        alert(`Chỉ số BMI của bạn là ${bmi.toFixed(2)}`);
        console.log(bmi);
      });
    </script>
  </body>
</html>
```

#### Sự kiện đầu vào và thay đổi

Trong ví dụ trên, chúng ta đã quản lý để lấy giá trị đầu vào từ hai trường nhập bằng cách nhấn nút. Nhưng nếu chúng ta muốn lấy giá trị mà không cần nhấp vào nút. Chúng ta có thể sử dụng sự kiện _change_ hoặc _input_ để lấy dữ liệu ngay lập tức từ trường nhập khi trường nhập đang được tập trung. Hãy xem cách chúng ta sẽ xử lý điều đó.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Document Object Model:30 Ngày JavaScript</title>
  </head>

  <body>
    <h1>Ràng Buộc Dữ Liệu bằng sự kiện input hoặc change</h1>

    <input type="text" placeholder="nói điều gì đó" />
    <p></p>

    <script>
      const input = document.querySelector("input");
      const p = document.querySelector("p");

      input.addEventListener("input", (e) => {
        p.textContent = e.target.value;
      });
    </script>
  </body>
</html>
```

#### Sự kiện mất trọng tâm (blur)

Ngược lại với _input_ hoặc _change_, sự kiện _blur_ xảy ra khi trường nhập không được tập trung.

```js
<!DOCTYPE html>
<html>

<head>
    <title>Document Object Model:30 Ngày JavaScript</title>
</head>

<body>
    <h1>Đưa ra phản hồi bằng sự kiện blur</h1>

    <input type="text" id="mass" placeholder="nói điều gì đó" />
    <p></p>

    <script>
        const input = document.querySelector('input')
        const p = document.querySelector('p')

        input.addEventListener('blur', (e) => {
            p.textContent = 'Trường này là bắt buộc'
            p.style.color = 'red'

        })
    </script>
</body>

</html>
```

#### sự kiện keypress, keydow và keyup

Chúng ta có thể truy cập tất cả các số key của bàn phím bằng cách sử dụng các loại sự kiện khác nhau. Hãy sử dụng keypress và lấy mã phím của mỗi phím trên bàn phím.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Document Object Model:30 Ngày JavaScript</title>
  </head>

  <body>
    <h1>Các sự kiện phím: Nhấn vào bất kỳ phím nào</h1>

    <script>
      document.body.addEventListener("keypress", (e) => {
        alert(e.keyCode);
      });
    </script>
  </body>
</html>
```

---
