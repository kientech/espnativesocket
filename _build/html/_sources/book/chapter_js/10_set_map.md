## 🤗 Set và Map

Trong JavaScript, `Set` và `Map` là hai cấu trúc dữ liệu mới được giới thiệu trong ECMAScript 6 (ES6). Chúng cung cấp các phương thức để lưu trữ dữ liệu theo cách khác biệt so với các mảng hoặc đối tượng thông thường. Dưới đây là giải thích chi tiết về Set và Map cũng như cách sử dụng chúng:

### Set

#### Khởi tạo Set

Bạn có thể khởi tạo một Set bằng cách sử dụng từ khóa new Set(). Có thể tạo một Set trống hoặc khởi tạo Set với một mảng các giá trị ban đầu.

```javascript
let mySet = new Set();
let anotherSet = new Set([1, 2, 3, 4, 5]);
```

#### Các phương thức và thuộc tính của `Set`

`add(value)`
Thêm một giá trị vào Set. Nếu giá trị đã tồn tại, nó sẽ không được thêm vào.

```javascript
mySet.add(1);
mySet.add(2);
mySet.add(2); // Không thêm lại giá trị 2 vì đã tồn tại
```

`delete(value)`
Xóa một giá trị khỏi Set. Trả về true nếu giá trị tồn tại và bị xóa, false nếu giá trị không tồn tại.

```javascript
mySet.delete(1); // Trả về true
mySet.delete(3); // Trả về false vì 3 không tồn tại trong Set
```

`has(value)`
Kiểm tra xem Set có chứa giá trị đó không. Trả về true nếu giá trị tồn tại, false nếu không.

```javascript
mySet.has(1); // Trả về false vì giá trị 1 đã bị xóa
mySet.has(2); // Trả về true
```

`clear()`
Xóa tất cả các phần tử khỏi Set.

```javascript
mySet.clear();
console.log(mySet.size); // Trả về 0
```

`size`
Trả về số lượng phần tử trong Set.

```javascript
console.log(mySet.size); // Trả về số lượng phần tử trong Set
```

#### Ví dụ sử dụng Set

```javascript
let numbers = new Set([1, 2, 3, 4, 5]);

numbers.add(6);
console.log(numbers.size); // 6

numbers.delete(3);
console.log(numbers.has(3)); // false

for (let num of numbers) {
  console.log(num);
}
// Output: 1, 2, 4, 5, 6

numbers.clear();
console.log(numbers.size); // 0
```


### Map
#### Khởi tạo Map
Có thể khởi tạo một Map bằng cách sử dụng từ khóa new Map(). Có thể tạo một Map trống hoặc khởi tạo Map với một mảng các cặp khóa-giá trị ban đầu.

```javascript
let myMap = new Map();
let anotherMap = new Map([['key1', 'value1'], ['key2', 'value2']]);
```

#### Các phương thức và thuộc tính của Map
`set(key, value)`
Thêm hoặc cập nhật một cặp khóa-giá trị trong Map.

```javascript
myMap.set('Alice', '123-456-789');
myMap.set('Bob', '987-654-321');
```
`get(key)`
Trả về giá trị tương ứng với khóa đã cho. Nếu khóa không tồn tại, trả về undefined.

```javascript
console.log(myMap.get('Alice')); // '123-456-789'
console.log(myMap.get('Charlie')); // undefined
```
`delete(key)`
Xóa một cặp khóa-giá trị khỏi Map. Trả về true nếu cặp khóa-giá trị tồn tại và bị xóa, false nếu khóa không tồn tại.

```javascript
myMap.delete('Alice'); // Trả về true
myMap.delete('Charlie'); // Trả về false
```
`has(key)`
Kiểm tra xem Map có chứa khóa đó không. Trả về true nếu khóa tồn tại, false nếu không.

```javascript
console.log(myMap.has('Bob')); // true
console.log(myMap.has('Charlie')); // false
```
`clear()`
Xóa tất cả các cặp khóa-giá trị khỏi Map.

```javascript
myMap.clear();
console.log(myMap.size); // Trả về 0
```
`size`
Trả về số lượng cặp khóa-giá trị trong Map.

```javascript
console.log(myMap.size); // Trả về số lượng cặp khóa-giá trị trong Map
```
#### Ví dụ sử dụng Map

```javascript
let contacts = new Map([
    ['Alice', '123-456-789'],
    ['Bob', '987-654-321'],
    ['Charlie', '555-555-555']
]);

contacts.set('David', '444-444-444');
console.log(contacts.get('Alice')); // '123-456-789'

contacts.delete('Charlie');
console.log(contacts.has('Charlie')); // false

for (let [key, value] of contacts) {
    console.log(`${key}: ${value}`);
}
// Output: Alice: 123-456-789, Bob: 987-654-321, David: 444-444-444

contacts.clear();
console.log(contacts.size); // 0
```

### So sánh Set và Map
- `Set` chỉ lưu trữ các giá trị duy nhất. Dùng khi bạn cần một tập hợp các giá trị không trùng lặp.
- `Map` lưu trữ các cặp khóa-giá trị, cho phép tra cứu nhanh giá trị dựa trên khóa. Dùng khi bạn cần ánh xạ các khóa duy nhất tới các giá trị.
Cả Set và Map đều là những cấu trúc dữ liệu mạnh mẽ, cung cấp các phương thức hữu ích để quản lý và thao tác dữ liệu hiệu quả. Chúng mang lại sự linh hoạt và tối ưu hơn trong việc xử lý các tập hợp dữ liệu phức tạp so với các cấu trúc dữ liệu truyền thống như mảng và đối tượng.