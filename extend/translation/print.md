# ReactToPrint - 浏览器打印 react 组件

> 原文：https://github.com/gregnb/react-to-print

你已经创建了一个 React 组件,并希望用户能打印出该组件内容。这个包的目的是通过弹出一个新的带有 css 样式的打印窗口来解决这个问题。

### 安装

```code
yarn add react-to-print
```

```code
npm install react-to-print --save
```

### 使用

- 通过 class components

```jsx
import React from "react";
import ReactToPrint from "react-to-print";

class ComponentToPrint extends React.Component {
  render() {
    return (
      <table>
        <thead>
          <th>column 1</th>
          <th>column 2</th>
          <th>column 3</th>
        </thead>
        <tbody>
          <tr>
            <td>data 1</td>
            <td>data 2</td>
            <td>data 3</td>
          </tr>
          <tr>
            <td>data 1</td>
            <td>data 2</td>
            <td>data 3</td>
          </tr>
          <tr>
            <td>data 1</td>
            <td>data 2</td>
            <td>data 3</td>
          </tr>
        </tbody>
      </table>
    );
  }
}

class Example extends React.Component {
  render() {
    return (
      <div>
        <ReactToPrint
          trigger={() => <a href="#">Print this out!</a>}
          content={() => this.componentRef}
        />
        <ComponentToPrint ref={el => (this.componentRef = el)} />
      </div>
    );
  }
}
```

- 通过 hooks

```jsx
import React, { useRef } from "react";
import ReactToPrint from "react-to-print";

class ComponentToPrint extends React.Component {
  render() {
    return (
      <table>
        <thead>
          <th>column 1</th>
          <th>column 2</th>
          <th>column 3</th>
        </thead>
        <tbody>
          <tr>
            <td>data 1</td>
            <td>data 2</td>
            <td>data 3</td>
          </tr>
          <tr>
            <td>data 1</td>
            <td>data 2</td>
            <td>data 3</td>
          </tr>
          <tr>
            <td>data 1</td>
            <td>data 2</td>
            <td>data 3</td>
          </tr>
        </tbody>
      </table>
    );
  }
}

const Example = () => {
  const componentRef = useRef();
  return (
    <div>
      <ReactToPrint
        trigger={() => <button>Print this out!</button>}
        content={() => componentRef.current}
      />
      <ComponentToPrint ref={componentRef} />
    </div>
  );
};
```

### 本地运行

node > 10

### API

#### &lt;ReactToPrint />

该组件接受以下参数（注意：`?`表示可选参数）：

|           Name           | Type                                             | Description                                                                                                                                                                                      |
| :----------------------: | :----------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|      **`trigger`**       | `function`                                       | 返回 React 组件或 HTML 元素的函数                                                                                                                                                                |
|      **`content`**       | `function`                                       | 返回组件引用值的函数。然后将该参考值的内容用于打印                                                                                                                                               |
|     **`copyStyles`**     | `boolean?`                                       | 将所有`<style>` and `<link type="stylesheet" />`标签从<head>父窗口内部复制到打印窗口。（默认值：`true`）                                                                                         |
| **`onBeforeGetContent`** | `function?`                                      | 在库收集页面内容之前触发的回调函数。返回 void 或 Promise。可用于在打印之前更改页面上的内容。                                                                                                     |
|   **`onBeforePrint`**    | `function?`                                      | 打印前触发的回调功能。返回 void 或 Promise。注意：此功能在打印之前立即运行，但在收集页面内容之后才运行。要在打印之前修改内容，请`onBeforeGetContent`改用。                                       |
|    **`onAfterPrint`**    | `function?`                                      | 打印后触发的回调功能                                                                                                                                                                             |
|    **`onPrintError`**    | `function(errorLocation: string, error: Error)?` | 如果打印错误严重到无法继续打印，将调用的回调函数。目前仅限于`onBeforeGetContent`或`onBeforePrint`中捕获 Promise reject。使用它尝试再次打印。`errorLocation`会告诉您 Promise 在哪个回调中被拒绝。 |
|  **`removeAfterPrint`**  | `boolean?`                                       | 执行操作后，卸下打印 iframe。默认为`false`。                                                                                                                                                     |
|     **`pageStyle`**      | `string?`                                        | 覆盖默认的打印窗口样式                                                                                                                                                                           |
|     **`bodyClass`**      | `string?`                                        | 传递给打印窗口主体的类                                                                                                                                                                           |
