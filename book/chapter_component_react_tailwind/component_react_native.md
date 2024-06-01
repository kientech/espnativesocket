## 😊 Thành Phần

### **React Native Overview**

React Native là một framework phổ biến cho việc phát triển ứng dụng di động sử dụng JavaScript và React. Trong React Native, bạn sẽ làm việc với các thành phần (components) để xây dựng giao diện người dùng của ứng dụng.

### **View Component**

- **Mô Tả:** Thành phần `View` là thành phần chính để tạo ra bố cục (layout) trong React Native.
- **Tương Đương HTML:** `<div>`
- **Sử Dụng:** `View` được sử dụng để nhóm và chứa các thành phần khác.

```jsx
import React from "react";
import { View, StyleSheet } from "react-native";

const ExampleView = () => {
  return <View style={styles.container}>{/* Nội dung của View */}</View>;
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: "center",
    alignItems: "center",
  },
});

export default ExampleView;
```

### **Text Component**

- **Mô Tả:** Thành phần `Text` được sử dụng để hiển thị văn bản trong ứng dụng.
- **Tương Đương HTML:** `<span>` hoặc `<p>`
- **Sử Dụng:** Bạn có thể áp dụng các kiểu dáng và thuộc tính văn bản cho `Text`.

```jsx
import React from "react";
import { Text, StyleSheet } from "react-native";

const ExampleText = () => {
  return <Text style={styles.text}>Hello, World!</Text>;
};

const styles = StyleSheet.create({
  text: {
    fontSize: 20,
    fontWeight: "bold",
    color: "blue",
  },
});

export default ExampleText;
```

### **Image Component**

- **Mô Tả:** Thành phần `Image` cho phép hiển thị hình ảnh trong ứng dụng.
- **Tương Đương HTML:** `<img>`
- **Sử Dụng:** Bạn có thể tải hình ảnh từ nguồn cục bộ hoặc từ URL.

```jsx
import React from "react";
import { Image } from "react-native";

const ExampleImage = () => {
  return (
    <Image
      source={require("./path/to/image.png")}
      style={{ width: 200, height: 200 }}
    />
  );
};

export default ExampleImage;
```

### **TextInput Component**

- **Mô Tả:** Thành phần `TextInput` cho phép người dùng nhập văn bản.
- **Tương Đương HTML:** `<input>`
- **Sử Dụng:** Bạn có thể kiểm soát các sự kiện như việc nhập liệu hoặc thay đổi trong `TextInput`.

```jsx
import React, { useState } from "react";
import { TextInput } from "react-native";

const ExampleTextInput = () => {
  const [text, setText] = useState("");

  return (
    <TextInput
      placeholder="Enter your text here"
      onChangeText={setText}
      value={text}
    />
  );
};

export default ExampleTextInput;
```

### **ScrollView Component**

- **Mô Tả:** Thành phần `ScrollView` cho phép cuộn nội dung khi nội dung vượt quá kích thước màn hình.
- **Tương Đương HTML:** Sử dụng CSS `overflow: scroll`
- **Sử Dụng:** `ScrollView` hữu ích khi bạn muốn hiển thị nội dung dài hoặc có thể cuộn.

```jsx
import React from "react";
import { ScrollView, Text } from "react-native";

const ExampleScrollView = () => {
  return (
    <ScrollView>
      <Text style={{ fontSize: 24 }}>Content 1</Text>
      <Text style={{ fontSize: 24 }}>Content 2</Text>
      <Text style={{ fontSize: 24 }}>Content 3</Text>
      {/* Thêm nhiều nội dung khác vào đây */}
    </ScrollView>
  );
};

export default ExampleScrollView;
```

### **TouchableOpacity Component**

- **Mô Tả:** Thành phần `TouchableOpacity` cho phép bạn thêm các hành động khi người dùng chạm vào nó.
- **Tương Đương HTML:** Sử dụng các sự kiện như `onClick`
- **Sử Dụng:** Khi người dùng chạm vào `TouchableOpacity`, bạn có thể thực hiện các hành động như chuyển hướng hoặc thay đổi trạng thái.

```jsx
import React from "react";
import { TouchableOpacity, Text, Alert } from "react-native";

const ExampleTouchableOpacity = () => {
  const handlePress = () => {
    Alert.alert("Button pressed!");
  };

  return (
    <TouchableOpacity onPress={handlePress}>
      <Text>Press Me</Text>
    </TouchableOpacity>
  );
};

export default ExampleTouchableOpacity;
```

### **FlatList Component**

- **Mô Tả:** Thành phần `FlatList` cho phép hiển thị danh sách dữ liệu có thể cuộn.
- **Tương Đương HTML:** Sử dụng `map` để render danh sách
- **Sử Dụng:** `FlatList` hữu ích khi bạn cần hiển thị một danh sách lớn của các mục dữ liệu.

```jsx
import React from "react";
import { FlatList, Text } from "react-native";

const ExampleFlatList = () => {
  const data = [
    { key: "Item 1" },
    { key: "Item 2" },
    { key: "Item 3" },
    // Thêm nhiều dữ liệu khác vào đây
  ];

  return (
    <FlatList data={data} renderItem={({ item }) => <Text>{item.key}</Text>} />
  );
};

export default ExampleFlatList;
```

### **StyleSheet**

- **Mô Tả:** `StyleSheet` là một đối tượng dùng để định nghĩa các kiểu dáng cho các thành phần giao diện.
- **Tương Đương HTML:** Sử dụng CSS để thiết lập kiểu dáng
- **Sử Dụng:** Bạn có thể sử dụng `StyleSheet` để tạo kiểu dáng cho các thành phần trong React Native.

---

Những thành phần này là những thành phần cơ bản nhưng rất quan trọng trong việc phát triển ứng dụng React Native. Bạn có thể kết hợp chúng để xây dựng các giao diện phức tạp và linh hoạt cho ứng dụng của mình.
