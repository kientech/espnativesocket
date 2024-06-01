# 🫵 Promises

## Promise

Chúng ta, con người, cam kết hoặc nhận được một lời hứa để thực hiện một số hoạt động vào một thời điểm nào đó. Nếu chúng ta giữ lời hứa, chúng ta làm cho người khác hạnh phúc nhưng nếu chúng ta không giữ lời hứa, điều đó có thể dẫn đến sự không hài lòng. Promise trong JavaScript có điểm chung với các ví dụ trên.

Promise là một cách để xử lý các hoạt động bất đồng bộ trong JavaScript. Nó cho phép xử lý với giá trị thành công cuối cùng hoặc lý do thất bại của một hành động bất đồng bộ. Điều này cho phép các phương thức bất đồng bộ trả về giá trị giống như các phương thức đồng bộ: thay vì trả về giá trị cuối cùng ngay lập tức, phương thức bất đồng bộ trả về một promise để cung cấp giá trị vào một thời điểm nào đó trong tương lai.

Một Promise có một trong các trạng thái sau:

- pending: trạng thái ban đầu, chưa được thực hiện hoặc bị từ chối.
- fulfilled: có nghĩa là hoạt động đã hoàn thành thành công.
- rejected: có nghĩa là hoạt động đã thất bại.

Một promise đang chờ có thể được thực hiện với một giá trị, hoặc bị từ chối với một lý do (lỗi). Khi một trong các tùy chọn này xảy ra, các trình xử lý kết nối bởi phương thức then của promise được gọi. (Nếu promise đã được thực hiện hoặc bị từ chối khi một trình xử lý tương ứng được gắn vào, trình xử lý sẽ được gọi, vì vậy không có điều kiện cạnh tranh giữa một hoạt động bất đồng bộ hoàn thành và các trình xử lý của nó được gắn vào.)

Vì các phương thức Promise.prototype.then() và Promise.prototype.catch() trả về promise, chúng có thể được liên kết với nhau.

## Callbacks

Để hiểu rõ về promise, hãy hiểu về callback trước. Hãy xem các ví dụ callback sau. Từ các đoạn mã sau, bạn sẽ nhận thấy sự khác biệt giữa callback và promise.

- callback
  Hãy xem một hàm callback có thể có hai tham số. Tham số đầu tiên là err và tham số thứ hai là result. Nếu tham số err là false, sẽ không có lỗi, nếu không, nó sẽ trả về một lỗi.

Trong trường hợp này, err có một giá trị và nó sẽ trả về khối lỗi.

```js
//Callback
const doSomething = (callback) => {
  setTimeout(() => {
    const skills = ["HTML", "CSS", "JS"];
    callback("It did not go well", skills);
  }, 2000);
};

const callback = (err, result) => {
  if (err) {
    return console.log(err);
  }
  return console.log(result);
};

doSomething(callback);
```

```sh
// sau 2 giây nó sẽ in ra
It did not go well
```

Trong trường hợp này, err là false và nó sẽ trả về khối else là result.

```js
const doSomething = (callback) => {
  setTimeout(() => {
    const skills = ["HTML", "CSS", "JS"];
    callback(false, skills);
  }, 2000);
};

doSomething((err, result) => {
  if (err) {
    return console.log(err);
  }
  return console.log(result);
});
```

```sh
// sau 2 giây nó sẽ in ra kỹ năng
["HTML", "CSS", "JS"]
```

### Promise constructor

Chúng ta có thể tạo một promise bằng cách sử dụng constructor Promise. Chúng ta có thể tạo một promise mới bằng từ khóa `new` theo sau là từ khóa `Promise` và theo sau là một dấu ngoặc đơn. Bên trong dấu ngoặc đơn, nó nhận một hàm `callback`. Hàm callback promise có hai tham số là _`resolve`_ và _`reject`_.

```js
// cú pháp
const promise = new Promise((resolve, reject) => {
  resolve("success");
  reject("failure");
});
```

```js
// Promise
const doPromise = new Promise((resolve, reject) => {
  setTimeout(() => {
    const skills = ["HTML", "CSS", "JS"];
    if (skills.length > 0) {
      resolve(skills);
    } else {
     reject("Có điều gì đó không đúng");
    }
  }, 2000);
});

doPromise
  .then((result) => {
    console.log(result);
  })
  .catch((error) => console.log(error));
```

```sh
["HTML", "CSS", "JS"]
```

Promise trên đã được giải quyết với resolve. Hãy xem một ví dụ khác khi promise được giải quyết với reject.

```js
// Promise
const doPromise = new Promise((resolve, reject) => {
  setTimeout(() => {
    const skills = ["HTML", "CSS", "JS"];
    if (skills.includes("Node")) {
      resolve("lập trình viên fullstack");
    } else {
      reject("Có điều gì đó không đúng");
    }
  }, 2000);
});

doPromise
  .then((result) => {
    console.log(result);
  })
  .catch((error) => console.error(error));
```

```sh
Có điều gì đó không đúng
```

## Fetch API

Fetch API cung cấp một giao diện để truy xuất tài nguyên (bao gồm cả qua mạng). Nó sẽ quen thuộc với bất kỳ ai đã sử dụng XMLHttpRequest, nhưng API mới cung cấp một bộ tính năng mạnh mẽ và linh hoạt hơn. Trong thách thức này, chúng ta sẽ sử dụng fetch để yêu cầu url và API. Ngoài ra, hãy xem các trường hợp sử dụng promise trong việc truy cập tài nguyên mạng bằng Fetch API.

```js
const url = "https://restcountries.com/v2/all"; // api quốc gia
fetch(url)
  .then((response) => response.json()) // truy cập dữ liệu API dưới dạng JSON
  .then((data) => {
    // lấy dữ liệu
    console.log(data);
  })
  .catch((error) => console.error(error)); // xử lý lỗi nếu có điều gì đó sai
```

## Async và Await

Async và await là một cách duyên dáng để xử lý promise. Nó dễ hiểu và dễ viết.

```js
const square = async function (n) {
  return n * n;
};

square(2);
```

```sh
Promise {<resolved>: 4}
```

Từ "async" phía trước một hàm có nghĩa là hàm đó sẽ trả về một promise. Hàm vuông trên thay vì giá trị, nó trả về một promise.

Làm thế nào để truy cập giá trị từ promise? Để truy cập giá trị từ promise, chúng ta sử dụng từ khóa "await".

```js
const square = async function (n) {
  return n * n;
};
const value = await square(2);
console.log(value);
```

```sh
4
```

Bây giờ, như bạn có thể thấy từ ví dụ trên, việc viết "async" phía trước một hàm tạo ra một promise và để có được giá trị từ một promise, chúng ta sử dụng await. Async và await đi đôi với nhau, một không thể tồn tại mà không có cái kia.

Hãy lấy dữ liệu API bằng cả hai phương thức promise và async và await.

- promise

```js
const url = "https://restcountries.com/v2/all";
fetch(url)
  .then((response) => response.json())
  .then((data) => {
    console.log(data);
  })
  .catch((error) => console.error(error));
```

- async và await

```js
const fetchData = async () => {
  try {
    const response = await fetch(url);
    const countries = await response.json();
    console.log(countries);
  } catch (err) {
    console.error(err);
  }
};
console.log("===== async và await");
fetchData();
```


