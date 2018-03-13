# wepyLearn

### 安装（更新） wepy 命令行工具
```
npm install wepy-cli -g
```

### 安装依赖
```
npm install wepy-cli -g
```

### 开发实时编译
```
wepy build --watch
```

## 目录结构
```
├── dist                   微信开发者工具指定的目录（该目录由WePY的build指令自动编译生成，请不要直接修改该目录下的文件）
├── node_modules           
├── src                    代码编写的目录（该目录为使用WePY后的开发目录）
|   ├── components         WePY组件目录（组件不属于完整页面，仅供完整页面或其他组件引用）
|   |   ├── com_a.wpy      可复用的WePY组件a
|   |   └── com_b.wpy      可复用的WePY组件b
|   ├── pages              WePY页面目录（属于完整页面）
|   |   ├── index.wpy      index页面（经build后，会在dist目录下的pages目录生成index.js、index.json、index.wxml和index.wxss文件）
|   |   └── other.wpy      other页面（经build后，会在dist目录下的pages目录生成other.js、other.json、other.wxml和other.wxss文件）
|   └── app.wpy            小程序配置项（全局数据、样式、声明钩子等；经build后，会在dist目录下生成app.js、app.json和app.wxss文件）
└── package.json           项目的package配置
```

## 重要提醒

1. 使用`微信开发者工具`-->`添加项目`，`项目目录`请选择`dist`目录。

2. `微信开发者工具`-->`项目`-->关闭`ES6转ES5`。 **重要：漏掉此项会运行报错。**

3. `微信开发者工具`-->`项目`-->`关闭上传代码时样式自动补全`。 **重要：某些情况下漏掉此项也会运行报错。**

4. `微信开发者工具`-->`项目`-->`关闭代码压缩上传`。 **重要：开启后，会导致真机computed, props.sync 等等属性失效。**（注：压缩功能可使用WePY提供的build指令代替，详见后文相关介绍以及Demo项目根目录中的`wepy.config.js`和`package.json`文件。）

5. 本地项目根目录运行`wepy build --watch`，开启实时编译。（注：如果同时在`微信开发者工具`-->`设置`-->`编辑器`中勾选了`文件保存`时自动编译小程序，将可以`实时预览`，非常方便。）