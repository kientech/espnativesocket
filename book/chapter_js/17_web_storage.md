# 👩 Bộ Nhớ Web

## Bộ Nhớ Web HTML5

Bộ nhớ Web (sessionStorage và localStorage) là một API HTML5 mới cung cấp những lợi ích quan trọng so với cookie truyền thống. Trước HTML5, dữ liệu ứng dụng phải được lưu trữ trong cookie, được bao gồm trong mỗi yêu cầu đến máy chủ. Bộ nhớ Web an toàn hơn và cho phép lưu trữ một lượng lớn dữ liệu cục bộ mà không ảnh hưởng đến hiệu suất của trang web. Giới hạn lưu trữ dữ liệu của cookie trong nhiều trình duyệt web là khoảng 4 KB mỗi cookie. Bộ nhớ Web có thể lưu trữ dữ liệu lớn hơn nhiều (ít nhất là 5MB) và không bao giờ được chuyển đến máy chủ. Tất cả các trang từ cùng một nguồn có thể lưu trữ và truy cập cùng một dữ liệu.

Dữ liệu được lưu trữ có thể được truy cập bằng JavaScript, giúp bạn tận dụng khả năng lập trình phía client để thực hiện nhiều điều truyền thống liên quan đến lập trình phía máy chủ và cơ sở dữ liệu quan hệ. Có hai đối tượng Bộ Nhớ Web:

- sessionStorage
- localStorage

localStorage tương tự như sessionStorage, ngoại trừ việc dữ liệu được lưu trữ trong localStorage không có thời gian hết hạn, dữ liệu được lưu trữ trong sessionStorage sẽ bị xóa khi phiên trang kết thúc — tức là khi trang được đóng.

Cần lưu ý rằng dữ liệu được lưu trữ trong cả localStorage hoặc sessionStorage đều đặc thù cho giao thức của trang.

Các khóa và giá trị luôn là chuỗi (lưu ý rằng, như với đối tượng, các khóa số nguyên sẽ tự động được chuyển đổi thành chuỗi).

![web_storage](../images/web_storage.png)

### sessionStorage

sessionStorage chỉ khả dụng trong tab trình duyệt hoặc phiên cửa sổ. Nó được thiết kế để lưu trữ dữ liệu trong một phiên trang web duy nhất. Điều này có nghĩa là nếu cửa sổ bị đóng, dữ liệu phiên sẽ bị xóa. Vì sessionStorage và localStorage có các phương thức tương tự, chúng ta sẽ tập trung vào localStorage.

### localStorage

HTML5 localStorage là một phần của API bộ nhớ web được sử dụng để lưu trữ dữ liệu trên trình duyệt mà không có ngày hết hạn. Dữ liệu sẽ có sẵn trên trình duyệt ngay cả khi trình duyệt bị đóng. localStorage được giữ ngay cả giữa các phiên trình duyệt. Điều này có nghĩa là dữ liệu vẫn có sẵn khi trình duyệt bị đóng và mở lại, và cũng ngay lập tức giữa các tab và cửa sổ.

Dữ liệu Bộ Nhớ Web, trong cả hai trường hợp, không khả dụng giữa các trình duyệt khác nhau. Ví dụ, các đối tượng lưu trữ được tạo trong Firefox không thể truy cập trong Internet Explorer, giống như cookie. Có năm phương thức để làm việc trên bộ nhớ cục bộ: _setItem(), getItem(), removeItem(), clear(), key()_

### Trường Hợp Sử Dụng Bộ Nhớ Web

Một số trường hợp sử dụng Bộ Nhớ Web là

- lưu trữ dữ liệu tạm thời
- lưu các sản phẩm mà người dùng đặt trong giỏ hàng của họ
- dữ liệu có thể được làm sẵn giữa các yêu cầu trang, nhiều tab trình duyệt và cũng giữa các phiên trình duyệt sử dụng localStorage
- có thể được sử dụng hoàn toàn offline sử dụng localStorage
- Bộ Nhớ Web có thể là một chiến thắng hiệu suất lớn khi một số dữ liệu tĩnh được lưu trữ trên client để giảm số lượng yêu cầu tiếp theo. Ngay cả hình ảnh cũng có thể được lưu trữ dưới dạng chuỗi sử dụng mã hóa Base64.
- có thể được sử dụng cho phương thức xác thực người dùng

Đối với các ví dụ được đề cập ở trên, có ý nghĩa sử dụng localStorage. Bạn có thể thắc mắc, vậy khi nào nên sử dụng sessionStorage.

Trong những trường hợp chúng ta muốn xóa dữ liệu ngay khi cửa sổ bị đóng. Hoặc, có thể, nếu chúng ta không muốn ứng dụng can thiệp vào cùng ứng dụng được mở trong một cửa sổ khác. Những tình huống này được phục vụ tốt nhất với sessionStorage.

Bây giờ, chúng ta hãy xem cách sử dụng các API Bộ Nhớ Web này.

## Đối Tượng Bộ Nhớ Web HTML5

Bộ nhớ web HTML cung cấp hai đối tượng để lưu trữ dữ liệu trên client:

- window.localStorage - lưu trữ dữ liệu không có ngày hết hạn
- window.sessionStorage - lưu trữ dữ liệu cho một phiên (dữ liệu sẽ mất khi tab trình duyệt bị đóng)

Hầu hết các trình duyệt hiện đại đều hỗ trợ Bộ Nhớ Web, tuy nhiên, nên kiểm tra hỗ trợ trình duyệt cho localStorage và sessionStorage. Hãy cùng xem các phương thức có sẵn cho các đối tượng Bộ Nhớ Web.

Các đối tượng Bộ Nhớ Web:

- _localStorage_ - để hiển thị đối tượng localStorage
- _localStorage.clear()_ - để xóa mọi thứ trong bộ nhớ cục bộ
- _localStorage.setItem()_ - để lưu trữ dữ liệu trong localStorage. Nó nhận các tham số là khóa và giá trị.
- _localStorage.getItem()_ - để hiển thị dữ liệu được lưu trữ trong localStorage. Nó nhận một khóa làm tham số.
- _localStorage.removeItem()_ - để xóa mục đã lưu trữ khỏi localStorage. Nó nhận khóa làm tham số.
- _localStorage.key()_ - để hiển thị một dữ liệu được lưu trữ trong localStorage. Nó nhận chỉ mục làm tham số.

![local_storage](../images/local_storage.png)

### Lưu trữ mục vào localStorage

Khi chúng ta lưu trữ dữ liệu vào localStorage, nó sẽ được lưu trữ dưới dạng chuỗi. Nếu chúng ta lưu trữ một mảng hoặc một đối tượng, chúng ta nên chuyển nó thành chuỗi trước để giữ nguyên định dạng nếu không chúng ta sẽ mất cấu trúc mảng hoặc đối tượng của dữ liệu gốc.

Chúng ta lưu trữ dữ liệu trong localStorage bằng phương thức _localStorage.setItem_.

```js
//cú pháp
localStorage.setItem('key', 'value')
```

- Lưu trữ chuỗi trong localStorage

```js
localStorage.setItem('firstName', 'Asabeneh') // vì giá trị là chuỗi nên chúng ta không cần chuyển nó thành chuỗi
console.log(localStorage)
```

```sh
Storage {firstName: 'Asabeneh', length: 1}
```

- Lưu trữ số trong localStorage

```js
localStorage.setItem('age', 200)
console.log(localStorage)
```

```sh
 Storage {age: '200', firstName: 'Asabeneh', length: 2}
```

- Lưu trữ một mảng trong localStorage. Nếu chúng ta lưu trữ một mảng, một đối tượng hoặc mảng đối tượng, chúng ta nên chuyển đổi đối tượng thành chuỗi trước. Xem ví dụ dưới đây.

```js
const skills = ['HTML', 'CSS', 'JS', 'React']
//Mảng kỹ năng phải được chuyển đổi thành chuỗi trước để giữ nguyên định dạng.
const skillsJSON = JSON.stringify(skills, undefined, 4)
localStorage.setItem('skills', skillsJSON)
console.log(localStorage)
```

```sh
Storage {age: '200', firstName: 'Asabeneh', skills: 'HTML,CSS,JS,React', length: 3}
```

```js
let skills = [
  { tech: 'HTML', level: 10 },
  { tech: 'CSS', level: 9 },
  { tech: 'JS', level: 8 },
  { tech: 'React', level: 9 },
  { tech: 'Redux', level: 10 },
  { tech: 'Node', level: 8 },
  { tech: 'MongoDB', level: 8 }
]

let skillJSON = JSON.stringify(skills)
localStorage.setItem('skills', skillJSON)
```

- Lưu trữ một đối tượng trong localStorage. Trước khi lưu trữ đối tượng vào localStorage, đối tượng phải được chuyển đổi thành chuỗi.

```js
const user = {
  firstName: 'Asabeneh',
  age: 250,
  skills: ['HTML', 'CSS', 'JS', 'React']
}

const userText = JSON.stringify(user, undefined, 4)
localStorage.setItem('user', userText)
```

### Lấy mục từ localStorage

Chúng ta lấy dữ liệu từ bộ nhớ cục bộ bằng phương thức _localStorage.getItem()_.

```js
//cú pháp
localStorage.getItem('key')
```

```js
let firstName = localStorage.getItem('firstName')
let age = localStorage.getItem('age')
let skills = localStorage.getItem('skills')
console.log(firstName, age, skills)
```

```sh
 'Asabeneh', '200', '['HTML','CSS','JS','React']'
```

Như bạn có thể thấy, kỹ năng đang ở định dạng chuỗi. Hãy sử dụng JSON.parse() để phân tích nó thành mảng bình thường.

```js
let skills = localStorage.getItem('skills')
let skillsObj = JSON.parse(skills, undefined, 4)
console.log(skillsObj)
```

```sh
['HTML','CSS','JS','React']
``

`

### Xóa bộ nhớ cục bộ

Phương thức clear sẽ xóa mọi thứ được lưu trữ trong bộ nhớ cục bộ

```js
localStorage.clear()
```

Bây giờ, bạn đã biết về Bộ Nhớ Web và bạn biết cách lưu trữ dữ liệu nhỏ trên trình duyệt của khách hàng. Bạn đã tiến thêm 17 bước trên con đường đến sự vĩ đại. Bây giờ hãy làm một số bài tập cho trí óc và cơ bắp của bạn.