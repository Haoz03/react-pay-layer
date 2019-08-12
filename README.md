# vue-pay-layer

移动端 React 支付密码弹窗插件

### demo 地址

[demo 演示地址](https://Haoz03.github.io/react-pay-layer-demo/build/)

### 动态图演示

![演示动图](https://haoz03.github.io/react-pay-layer-demo/build/demo.gif)

### 插件的安装

```
npm install react-pay-layer
```

#### 在组件中使用

```js
import ReactPayLayer from "react-pay-layer";
<ReactPayLayer
  onRef={this.onRef}
  handleClose={this.handleClose}
  forgetClickEvent={this.forgetClickEvent}
  inputEnd={this.inputEnd}
/>;
```

### API

| 参数            | 说明                   | 类型   |     默认值     |
| --------------- | :--------------------- | :----- | :------------: |
| title           | 弹框标题               | String | 请输入支付密码 |
| passwordLength  | 密码位数               | Number |       6        |
| loadingText     | 正在支付文字提示       | String |  正在支付...   |
| successText     | 支付成功文字提示       | String |    支付成功    |
| successDuration | 支付成功提示时长（ms） | Number |      2000      |

### Event

| 事件名         | 说明                   | 参数 |
| :------------- | :--------------------- | :--- |
| inputEnd       | 密码输入完的回调函数   | -    |
| close          | 点击弹窗关闭的回调函数 | -    |
| forgetPassword | 点击忘记密码得回调函数 | -    |

### inputEnd 回调参数

| 参数名 | 说明     | 类型   |
| ------ | :------- | :----- |
| result | 支付密码 | String |

### 插件内部方法

| 方法名  | 说明                                                                            | 参数                         |
| :------ | :------------------------------------------------------------------------------ | :--------------------------- |
| success | 通知插件支付结果成功，该方法返回 promise，可在.then()方法中进行成功后的回调函数 | -                            |
| fail    | 密码弹窗关闭后的回调函数                                                        | String（可传入错误提示内容） |

#### 用法示例：

支付结果成功：

```javascript
this.payLayer.success().then(res => {
  console.log("支付成功");
});
```

支付结果失败：

```javascript
this.payLayer.fail("可以自定义错误提示，默认：支付密码错误");
```
