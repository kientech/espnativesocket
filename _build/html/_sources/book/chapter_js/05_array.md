## 🚎 Array

Trong JavaScript, mảng (Array) là một cấu trúc dữ liệu dùng để lưu trữ danh sách các phần tử. Mỗi phần tử có một chỉ số (index) xác định, bắt đầu từ 0. Mảng có thể chứa các giá trị khác nhau, chẳng hạn như số, chuỗi, đối tượng, và thậm chí là các mảng khác.

### Khởi tạo mảng

Bạn có thể khởi tạo mảng bằng cách sử dụng cú pháp dấu ngoặc vuông [] hoặc từ khóa new Array().

```javascript
let emptyArray = [];
let numberArray = [1, 2, 3, 4, 5];
let mixedArray = [1, "two", { key: "value" }, [3, 4]];
let anotherArray = new Array(5); // Tạo mảng với độ dài 5
```

### Các phương thức và thuộc tính của mảng

`length`
Thuộc tính length trả về số lượng phần tử trong mảng.

```javascipt
console.log(numberArray.length); // 5
```

`push(element)`
Thêm một hoặc nhiều phần tử vào cuối mảng và trả về độ dài mới của mảng.

```javascript
numberArray.push(6);
console.log(numberArray); // [1, 2, 3, 4, 5, 6]
```

`pop()`
Xóa phần tử cuối cùng khỏi mảng và trả về phần tử đó.

```javscript
let lastElement = numberArray.pop();
console.log(lastElement); // 6
console.log(numberArray); // [1, 2, 3, 4, 5]
```

`unshift(element)`
Thêm một hoặc nhiều phần tử vào đầu mảng và trả về độ dài mới của mảng.

```javascript
numberArray.unshift(0);
console.log(numberArray); // [0, 1, 2, 3, 4, 5]
```

`shift()`
Xóa phần tử đầu tiên khỏi mảng và trả về phần tử đó.

```javascript
let firstElement = numberArray.shift();
console.log(firstElement); // 0
console.log(numberArray); // [1, 2, 3, 4, 5]
```

`indexOf(element)`
Trả về chỉ số của phần tử đầu tiên tìm thấy trong mảng, hoặc -1 nếu không tìm thấy.

```javascript
console.log(numberArray.indexOf(3)); // 2
console.log(numberArray.indexOf(6)); // -1
```

`splice(start, deleteCount, item1, item2, ...)`
Thay đổi nội dung của mảng bằng cách xóa hoặc thay thế các phần tử hiện có và/hoặc thêm các phần tử mới.

```javascript
numberArray.splice(2, 1, "three"); // Xóa 1 phần tử tại vị trí 2 và thêm 'three'
console.log(numberArray); // [1, 2, 'three', 4, 5]
```

`slice(start, end)`
Trả về một mảng mới chứa các phần tử từ chỉ số start đến chỉ số end (không bao gồm end).

```javascript
let newArray = numberArray.slice(1, 3);
console.log(newArray); // [2, 'three']
```

`forEach(callback)`
Thực thi một hàm cho mỗi phần tử của mảng.

```javascript
numberArray.forEach(function (element) {
  console.log(element);
});
// Output: 1, 2, 'three', 4, 5
```

`map(callback)`
Tạo một mảng mới với các kết quả của việc gọi một hàm cho mỗi phần tử trong mảng.

```javascrpit
let squaredArray = numberArray.map(function(element) {
return typeof element === 'number' ? element \* element : element;
});
console.log(squaredArray); // [1, 4, 'three', 16, 25]
```

`filter(callback)`
Tạo một mảng mới với tất cả các phần tử của mảng hiện tại mà hàm callback trả về true.

```javscript
let numberOnlyArray = numberArray.filter(function(element) {
return typeof element === 'number';
});
console.log(numberOnlyArray); // [1, 2, 4, 5]
```

`reduce(callback, initialValue)`
Áp dụng một hàm lên các phần tử của mảng (từ trái sang phải) để giảm mảng thành một giá trị duy nhất.

```javascript
let sum = numberArray.reduce(function (accumulator, currentValue) {
  return typeof currentValue === "number"
    ? accumulator + currentValue
    : accumulator;
}, 0);
console.log(sum); // 12
```

### Ví dụ tổng hợp sử dụng mảng

```javascript
let fruits = ["Apple", "Banana", "Cherry"];

fruits.push("Date");
console.log(fruits); // ['Apple', 'Banana', 'Cherry', 'Date']

fruits.pop();
console.log(fruits); // ['Apple', 'Banana', 'Cherry']

fruits.unshift("Elderberry");
console.log(fruits); // ['Elderberry', 'Apple', 'Banana', 'Cherry']

fruits.shift();
console.log(fruits); // ['Apple', 'Banana', 'Cherry']

console.log(fruits.indexOf("Banana")); // 1

fruits.splice(1, 1, "Blueberry");
console.log(fruits); // ['Apple', 'Blueberry', 'Cherry']

let newFruits = fruits.slice(1, 3);
console.log(newFruits); // ['Blueberry', 'Cherry']

fruits.forEach(function (fruit) {
  console.log(fruit);
});
// Output: Apple, Blueberry, Cherry

let upperFruits = fruits.map(function (fruit) {
  return fruit.toUpperCase();
});
console.log(upperFruits); // ['APPLE', 'BLUEBERRY', 'CHERRY']

let berryFruits = fruits.filter(function (fruit) {
  return fruit.includes("berry");
});
console.log(berryFruits); // ['Blueberry']

let concatenatedFruits = fruits.reduce(function (acc, fruit) {
  return acc + fruit + " ";
}, "");
console.log(concatenatedFruits); // 'Apple Blueberry Cherry '
```

Mảng là một cấu trúc dữ liệu linh hoạt và mạnh mẽ trong JavaScript. Việc hiểu và sử dụng các phương thức khác nhau của mảng sẽ giúp bạn quản lý và thao tác dữ liệu hiệu quả hơn trong quá trình phát triển ứng dụng.
