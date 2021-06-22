# mini-html-parser2

## 背景
fork项目阿里项目[mini-html-parser](https://github.com/ant-mini-program/mini-html-parser)，重新编译把依赖打包到一起。

## 版本
本版本0.3.x 对应官网0.3.0

## 安装

```
$ npm install @peacejj/mini-html-parser2 --save
```

## 使用

```js
// page.js
const html = `<div>
<span>test</span>
<div>
    <span>table test</span>
    <table>
        <thead>
            <tr>
                <th>title</th>
                <th>title</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td colspan="2">yy</td>
                <td>xx</td>
                <td>xx</td>
                <td>xx</td>
            </tr>
        </tbody>
    </table>
</div>
</div>`
import parse from '@peacejj/mini-html-parser2';

Page({
  data: {
    nodes: [],
  },
  onLoad() {
    parse(html, (err, nodes) => {
      if (!err) {
        this.setData({
          nodes,
        });
      }
    })
  },
})
```

```html
<!-- page.axml -->
<rich-text nodes="{{nodes}}" />
```

## 运行测试

```
$ npm run build
$ npm test
```
