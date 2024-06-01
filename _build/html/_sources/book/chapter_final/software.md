## 📱 Phần Mềm

Để thuận tiện cho việc quản lý và điều khiển các thiết bị Iots, nhóm em xây dựng một ứng dụng điện thoại để dễ dàng theo dõi sự hoạt động của từng thiết bị. 

#### Video Hướng Dẫn Xây Dựng Phần Mềm với React Native và TailwindCSS
<iframe width="766" height="543" src="https://www.youtube.com/embed/rHwufwg7wp0" title="SmartCool IoT App with React Native and Websocket | Mobile App Development | KienTech" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

#### Chức Năng Của Từng Thành Phần

```jsx
import {
  View,
  Text,
  Image,
  SafeAreaView,
  TouchableOpacity,
  Alert,
  ScrollView,
} from "react-native";
import React, { useRef } from "react";
import {
  ArrowDownIcon,
  Bars3CenterLeftIcon,
  BoltIcon,
  LightBulbIcon,
} from "react-native-heroicons/solid";
import { storeColors } from "../theme";
import SensorInfo from "../components/SensorInfo";
import ModeApp from "../components/ModeApp";
import ButtonSwitch from "../components/ButtonSwitch";
import { useState } from "react";
import WebSocket from "react-native-websocket";
```

- `import { View, Text, Image, SafeAreaView, TouchableOpacity, Alert, ScrollView } from "react-native";` : Nhập các thành phần giao diện từ thư viện React Native như View, Text, Image, SafeAreaView, TouchableOpacity, Alert, ScrollView.
- `import React, { useRef } from "react";` : Nhập thư viện React và hàm `useRef` từ React.
- `import { ... } from "react-native-heroicons/solid";` : Nhập các biểu tượng từ thư viện `react-native-heroicons/solid`.
- `import { storeColors } from "../theme";` : Nhập màu sắc được định nghĩa trong tệp `theme`.
- `import SensorInfo from "../components/SensorInfo";` : Nhập thành phần `SensorInfo` từ thư mục components.
- `import ModeApp from "../components/ModeApp";` : Nhập thành phần `ModeApp` từ thư mục components.
- `import ButtonSwitch from "../components/ButtonSwitch";` : Nhập thành phần `ButtonSwitch` từ thư mục components.
- `import { useState } from "react";` : Nhập hàm `useState` từ React.
- `import WebSocket from "react-native-websocket";` : Nhập thành phần `WebSocket` từ thư viện `react-native-websocket`.

```jsx
// const SERVER_URL = "ws://192.168.1.9:8080";
const SERVER_URL = "ws://server-iot-54eb32613657.herokuapp.com/";
const HomeScreen = () => {
  const [isSwitchEnableFan, setIsSwitchEnableFan] = useState(false);
  const [isSwitchEnableLed, setIsSwitchEnableLed] = useState(false);
  const [sensorData, setSensorData] = useState({
    temperature: 0,
    humidity: 0,
  });
  const [onFan, setOnFan] = useState("Off");
  const [onLed, setOnLed] = useState("Off");
  const websocketRef = useRef(null);
```

- `const SERVER_URL = "ws://192.168.1.9:8080";` : Định nghĩa URL của WebSocket server.
- `const HomeScreen = () => { ... }` : Định nghĩa hàm `HomeScreen`, đây là một thành phần giao diện.
- `const [isSwitchEnableFan, setIsSwitchEnableFan] = useState(false);` : Khai báo trạng thái và hàm cập nhật trạng thái của công tắc quạt, ban đầu là `false`.
- `const [isSwitchEnableLed, setIsSwitchEnableLed] = useState(false);` : Khai báo trạng thái và hàm cập nhật trạng thái của công tắc đèn LED, ban đầu là `false`.
- `const [sensorData, setSensorData] = useState({ temperature: 0, humidity: 0 });` : Khai báo trạng thái và hàm cập nhật trạng thái của dữ liệu cảm biến (nhiệt độ và độ ẩm), ban đầu là `{ temperature: 0, humidity: 0 }`.
- `const [onFan, setOnFan] = useState("Off");` : Khai báo trạng thái và hàm cập nhật trạng thái của quạt, ban đầu là "Off".
- `const [onLed, setOnLed] = useState("Off");` : Khai báo trạng thái và hàm cập nhật trạng thái của đèn LED, ban đầu là "Off".
- `const websocketRef = useRef(null);` : Khai báo một `ref` để lưu trữ tham chiếu đến WebSocket.

```jsx
const onMessage = (event) => {
  const data = JSON.parse(event.data);
  setSensorData(data);
};

const handleOnError = (error) => {
  console.log("🚀 ~ handleOnError ~ error:", error);
};
```

- `const onMessage = (event) => { ... };` : Định nghĩa hàm `onMessage` để xử lý dữ liệu nhận được từ WebSocket, chuyển đổi dữ liệu từ chuỗi JSON và cập nhật trạng thái `sensorData`.
- `const handleOnError = (error) => { ... };` : Định nghĩa hàm `handleOnError` để xử lý lỗi của WebSocket và in lỗi ra console.

```jsx
const toggleSwitchFan = () => {
  if (websocketRef.current) {
    const message = {
      type: "fanControl",
      status: !isSwitchEnableFan ? "on" : "off",
    };
    websocketRef.current.send(JSON.stringify(message));
  }
  const newState = !isSwitchEnableFan;
  setIsSwitchEnableFan(newState);
  setOnFan(newState ? "On" : "Off");
};
```

- `const toggleSwitchFan = () => { ... };` : Định nghĩa hàm `toggleSwitchFan` để bật/tắt quạt.
- `if (websocketRef.current) { ... }` : Kiểm tra xem WebSocket có đang hoạt động hay không.
- `const message = { type: "fanControl", status: !isSwitchEnableFan ? "on" : "off" };` : Tạo tin nhắn điều khiển quạt dựa trên trạng thái hiện tại.
- `websocketRef.current.send(JSON.stringify(message));` : Gửi tin nhắn qua WebSocket.
- `const newState = !isSwitchEnableFan;` : Đảo trạng thái của công tắc quạt.
- `setIsSwitchEnableFan(newState);` : Cập nhật trạng thái công tắc quạt.
- `setOnFan(newState ? "On" : "Off");` : Cập nhật trạng thái hiển thị của quạt.

```jsx
const toggleSwitchLed = () => {
  if (websocketRef.current) {
    const message = {
      type: "ledControl",
      status: !isSwitchEnableLed ? "on" : "off",
    };
    websocketRef.current.send(JSON.stringify(message));
  }
  const newState = !isSwitchEnableLed;
  setIsSwitchEnableLed(newState);
  setOnLed(newState ? "On" : "Off");
};
```

- Tương tự `toggleSwitchFan`, hàm `toggleSwitchLed` thực hiện bật/tắt đèn LED.

```jsx
  return (
    <SafeAreaView>
      <View className="p-4">
        <View className="flex-row justify-between items-center">
          <Bars3CenterLeftIcon size={25} color={storeColors.textBlack} />
          <View className="flex-row justify-center items-center">
            <Text>My home</Text>
            <ArrowDownIcon size={15} color={storeColors.textBlack} />
          </View>
          <TouchableOpacity onPress={() => Alert.alert("Go to Profile Screen")}>
            <Image
              source={require("../assets/images/avatar.jpg")}
              className="w-8 h-8 rounded-full"
            />
          </TouchableOpacity>
        </View>
      </View>

      <ScrollView>
        <WebSocket ref={websocketRef} url={SERVER_URL} />

        <View className="mt-4 mx-4">
          <View className="flex-row item-center justify-between gap-2">
            <SensorInfo
              title="Temperature"
              source={require("../assets/icons/temperature.png")}
              value="0"
            />
            <SensorInfo
              title="Humidity"
              source={require("../assets/icons/humidity.png")}
              value="0"
            />
            <SensorInfo
              title="Co2"
              source={require("../assets/icons/cloud.png")}
              value="0"
            />
          </View>
```

- `return ( ... )` : Trả về giao diện của `HomeScreen`.
- `SafeAreaView` : Đảm bảo rằng nội dung nằm trong khu vực an toàn của màn hình.
- `View` : Một thành phần để bố trí các phần tử con.
- `Bars3CenterLeftIcon`, `ArrowDownIcon` : Các biểu tượng được hiển thị trong giao diện.
- `TouchableOpacity` : Một thành phần có thể nhấn được.
- `Image` : Hiển thị hình ảnh đại diện.
- `ScrollView` : Cho phép cuộn nội dung.
- `WebSocket ref={websocketRef} url={SERVER_URL}` : Thiết lập kết nối WebSocket với URL đã định nghĩa.
- `SensorInfo` : Hiển thị thông tin cảm biến (nhiệt độ, độ ẩm, CO2).

```jsx
<View className="flex-row justify-between items-center flex-1 w-full mt-4">
  <View className="my-2">
    <ModeApp
      icon={<LightBulbIcon size={15} color={storeColors.textBlack} />}
      text="Light mode"
      onPress={() => Alert.alert(`Light mode`)}
    />
    <ModeApp
      icon={<LightBulbIcon size={15} color={storeColors.textBlack} />}
      text="Dark mode"
      onPress={() => Alert.alert(`Dark mode`)}
    />
  </View>

  <View className="my-2">
    <ModeApp
      icon={<LightBulbIcon size={15} color={storeColors.textBlack} />}
      text="Sunline mode"
    />
    <ModeApp
      icon={<LightBulbIcon size={15} color={storeColors.textBlack} />}
      text="Light mode"
    />
  </View>
</View>
```

- `ModeApp` : Hiển thị các chế độ ánh sáng khác nhau (Light mode, Dark mode, Sunline mode) với biểu tượng và chức năng `onPress`.

```jsx
<View className="my-6 rounded-2xl bg-blue-400">
  <View className="px-4 py-5">
    <TouchableOpacity className="flex-row items-center">
      <View className="bg-white p-3 rounded-full">
        <BoltIcon />
      </View>
      <View className="ml-5">
        <Text className="text-white font-bold py-1">2.45kWh</Text>
        <Text className="text-white">Power usage today</Text>
      </View>
    </TouchableOpacity>
  </View>
</View>
```

- Hiển thị thông tin về lượng điện năng tiêu thụ hôm nay với biểu tượng và văn bản.

```jsx
          <View>
            <View className="flex">
              <ButtonSwitch
                title="Fan"
                state={onFan}
                source={require("../assets/icons/fan.png")}
                value={isSwitchEnableFan}
                onValueChange={toggleSwitchFan}
              />
              <ButtonSwitch
                title="Light"
                state={onLed}
                source={require("../assets/icons/led.png")}
                value={isSwitchEnableLed}
                onValueChange={toggleSwitchLed}
              />
            </View>
          </View>
        </View>
      </ScrollView>
    </SafeAreaView>
  );
};

export default HomeScreen;
```

- `ButtonSwitch` : Thành phần để bật/tắt quạt và đèn LED với biểu tượng, trạng thái và hàm thay đổi giá trị.

- `export default HomeScreen;` : Xuất thành phần `HomeScreen` để sử dụng ở nơi khác.
