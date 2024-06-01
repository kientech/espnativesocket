## 😃 JSON

#### JSON

JSON là viết tắt của JavaScript Object Notation. Cú pháp JSON được lấy từ cú pháp đối tượng JavaScript, nhưng định dạng JSON chỉ là văn bản hoặc chuỗi. JSON là một định dạng dữ liệu nhẹ để lưu trữ và truyền tải dữ liệu. JSON thường được sử dụng khi dữ liệu được gửi từ máy chủ đến máy khách. JSON là một lựa chọn thay thế dễ sử dụng hơn so với XML.

**Ví dụ:**

```js
{
"users":[
  {
    "firstName":"Asabeneh",
    "lastName":"Yetayeh",
    "age":250,
    "email":"asab@asb.com"
  },
  {
    "firstName":"Alex",
    "lastName":"James",
    "age":25,
    "email":"alex@alex.com"
  },
  {
    "firstName":"Lidiya",
    "lastName":"Tekle",
    "age":28,
    "email":"lidiya@lidiya.com"
  }
]
}
```

Ví dụ JSON trên không khác nhiều so với một đối tượng bình thường. Vậy sự khác biệt là gì? Sự khác biệt là khóa của một đối tượng JSON phải được đặt trong dấu ngoặc kép hoặc phải là một chuỗi. Đối tượng JavaScript và JSON rất giống nhau đến nỗi chúng ta có thể chuyển đổi giữa JSON và đối tượng dễ dàng.

Hãy xem chi tiết ví dụ trên, nó bắt đầu với dấu ngoặc nhọn. Bên trong dấu ngoặc nhọn, có một khóa "users" chứa một mảng. Trong mảng này, chúng ta có các đối tượng khác nhau và mỗi đối tượng có các khóa, mỗi khóa phải được đặt trong dấu ngoặc kép. Ví dụ, chúng ta sử dụng "firstName" thay vì chỉ đơn giản là firstName, trong khi trong đối tượng chúng ta sử dụng các khóa mà không cần dấu ngoặc kép. Đây là sự khác biệt chính giữa một đối tượng và JSON. Hãy xem thêm một số ví dụ về JSON.

**Ví dụ:**

```js
{
    "Alex": {
        "email": "alex@alex.com",
        "skills": [
            "HTML",
            "CSS",
            "JavaScript"
        ],
        "age": 20,
        "isLoggedIn": false,
        "points": 30
    },
    "Asab": {
        "email": "asab@asab.com",
        "skills": [
            "HTML",
            "CSS",
            "JavaScript",
            "Redux",
            "MongoDB",
            "Express",
            "React",
            "Node"
        ],
        "age": 25,
        "isLoggedIn": false,
        "points": 50
    },
    "Brook": {
        "email": "daniel@daniel.com",
        "skills": [
            "HTML",
            "CSS",
            "JavaScript",
            "React",
            "Redux"
        ],
        "age": 30,
        "isLoggedIn": true,
        "points": 50
    },
    "Daniel": {
        "email": "daniel@alex.com",
        "skills": [
            "HTML",
            "CSS",
            "JavaScript",
            "Python"
        ],
        "age": 20,
        "isLoggedIn": false,
        "points": 40
    },
    "John": {
        "email": "john@john.com",
        "skills": [
            "HTML",
            "CSS",
            "JavaScript",
            "React",
            "Redux",
            "Node.js"
        ],
        "age": 20,
        "isLoggedIn": true,
        "points": 50
    },
    "Thomas": {
        "email": "thomas@thomas.com",
        "skills": [
            "HTML",
            "CSS",
            "JavaScript",
            "React"
        ],
        "age": 20,
        "isLoggedIn": false,
        "points": 40
    },
    "Paul": {
        "email": "paul@paul.com",
        "skills": [
            "HTML",
            "CSS",
            "JavaScript",
            "MongoDB",
            "Express",
            "React",
            "Node"
        ],
        "age": 20,
        "isLoggedIn": false,
        "points": 40
    }
}
```

#### Chuyển đổi JSON thành Đối tượng JavaScript

Phần lớn chúng ta lấy dữ liệu JSON từ phản hồi HTTP hoặc từ một tệp, nhưng chúng ta có thể lưu trữ JSON dưới dạng chuỗi và chuyển đổi nó thành đối tượng để minh họa. Trong JavaScript, từ khóa _JSON_ có các phương thức _parse()_ và _stringify()_. Khi muốn chuyển đổi JSON thành đối tượng, chúng ta sử dụng _JSON.parse()_. Khi muốn chuyển đổi đối tượng thành JSON, chúng ta sử dụng _JSON.stringify()_.

##### JSON.parse()

```js
JSON.parse(json[, reviver])
// json hoặc văn bản, dữ liệu
// reviver là một hàm gọi lại tùy chọn
/* JSON.parse(json, (key, value) => {

})
*/
```

```js
const usersText = `{
"users":[
  {
    "firstName":"Asabeneh",
    "lastName":"Yetayeh",
    "age":250,
    "email":"asab@asb.com"
  },
  {
    "firstName":"Alex",
    "lastName":"James",
    "age":25,
    "email":"alex@alex.com"
  },
  {
  "firstName":"Lidiya",
  "lastName":"Tekle",
  "age":28,
  "email":"lidiya@lidiya.com"
  }
]
}`

const usersObj = JSON.parse(usersText, undefined, 4)
console.log(usersObj)
```

#### Sử dụng hàm reviver với JSON.parse()

Để sử dụng hàm reviver như một bộ định dạng, chúng ta đặt các khóa muốn định dạng trước tên và giá trị họ. Giả sử chúng ta quan tâm đến việc định dạng firstName và lastName của dữ liệu JSON.

```js
const usersText = `{
"users":[
  {
    "firstName":"Asabeneh",
    "lastName":"Yetayeh",
    "age":250,
    "email":"asab@asb.com"
  },
  {
    "firstName":"Alex",
    "lastName":"James",
    "age":25,
    "email":"alex@alex.com"
  },
  {
    "firstName":"Lidiya",
    "lastName":"Tekle",
    "age":28,
    "email":"lidiya@lidiya.com"
  }
]
}`

const usersObj = JSON.parse(usersText, (key, value) => {
  let newValue =
    typeof value == 'string' && key != 'email' ? value.toUpperCase() : value
  return newValue
})
console.log(usersObj)
```

Phương thức _JSON.parse()_ rất tiện dụng. Bạn không cần phải truyền tham số tùy chọn, chỉ cần sử dụng với tham số bắt buộc và bạn sẽ đạt được nhiều kết quả.

#### Chuyển đổi Đối tượng thành JSON

Khi muốn chuyển đổi đối tượng thành JSON, chúng ta sử dụng _JSON.stringify()_. Phương thức stringify nhận một tham số bắt buộc và hai tham số tùy chọn. Replacer được sử dụng như một bộ lọc và space là các dấu cách. Nếu không muốn lọc ra bất kỳ khóa nào từ đối tượng, chúng ta có thể chỉ cần truyền undefined.

```js
JSON.stringify(obj, replacer, space)
// json hoặc văn bản, dữ liệu
// replacer là một hàm gọi lại tùy chọn
```

Hãy chuyển đổi đối tượng sau thành chuỗi. Đầu tiên, hãy giữ tất cả các khóa và cũng hãy có 4 dấu cách để thụt đầu dòng.

```js
const users = {
  Alex: {
    email: 'alex@alex.com',
    skills: ['HTML', 'CSS', 'JavaScript'],
    age: 20,
    isLoggedIn: false,
    points: 30
  },
  Asab: {
    email: 'asab@asab.com',
    skills: [
      'HTML',
      'CSS',
      'JavaScript',
      'Redux',
      'MongoDB',
      'Express',
      'React',
      'Node'
    ],
    age: 25,
    isLoggedIn: false,
    points: 50
  },
  Brook: {
    email: 'daniel@daniel.com',
    skills: ['HTML', 'CSS', 'JavaScript', 'React', 'Redux'],
    age: 30,
    isLoggedIn: true,
    points: 50
  },
  Daniel: {
    email: 'daniel@alex.com',
    skills: ['HTML', 'CSS', 'JavaScript', 'Python'],
    age: 20,
    isLoggedIn: false,
    points: 40
  },
  John: {
    email: 'john@john.com',
    skills: ['HTML', 'CSS', 'JavaScript', 'React', 'Redux', 'Node.js'],
    age: 20,
    isLoggedIn: true,
    points: 50
  },
  Thomas: {
    email: 'thomas@thomas.com',
    skills: ['HTML', 'CSS', 'JavaScript', 'React'],
    age: 20,
    isLoggedIn: false,
    points: 40
  },
 