# sx-react-keyboard

React H5 密码键盘

## install

```
yarn add sx-react-keyboard
or
npm i sx-react-keyboard
```

#### 引入插件

```javascript
import React, { useRef } from 'react';
import Keyboard from 'sx-react-keyboard';
```

#### 基本用法

```javascript
const keyboardRef = useRef(null);
// 打开键盘
keyboardRef.current.show();
// 关闭键盘
keyboardRef.current.hide();

<Keyboard
	ref={keyboardRef}
	type="letter"
	length={6}
	encrypt="md5"
	publicKey=""
	privateKey=""
	onFinish={vlaue => {
		console.log('密码是', vlaue);
	}}
/>;
```

### API

| 参数       | 说明                                                       | 类型   | 默认值 |
| ---------- | :--------------------------------------------------------- | :----- | :----: |
| type       | 键盘类型，num: 纯数字键盘； letter: 数字、字母、字符键盘； | String |  num   |
| length     | 密码的位数，4 位密码 6 位密码 18 位以内的密码              | Number |   6    |
| ref        | 获取当前实例                                               | ref    |   -    |
| encrypt    | 加密方式，ras、md5 加密方式, ras 时必须传公钥 publicKey    | String | String |
| publicKey  | 公钥，encrypt="rsa"时必传                                  | String |        |
| privateKey | 私钥，公钥加密后使用 privateKey 私钥解密                   | String |        |
| duration   | 支付成功提示的显示时间                                     | Number |  500   |

### Event

| 事件名   | 说明                 | 参数 |
| :------- | :------------------- | :--- |
| onFinish | 密码输入完成后的回调 | -    |
