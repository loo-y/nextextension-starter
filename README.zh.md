[English](./README.md)


# NextExtension-Starter
这是一个基于 Nextjs 的 chrome 插件 starter。插件 manifest 版本为 v3。

## 使用说明
### 修改文件
|代码目录|生成文件|
|--|--|
|[```app/(pages)/options```](./app/(pages)/options/)|options.html|
|[```app/(pages)/popup```](./app/(pages)/popup/)|popup.html|
|[```app/scripts/content```](./app/scripts/content)|content-script.js|
|[```app/scripts/inject```](./app/scripts/inject)|inject-script.js|


### 如何打包
1. 安装
    ```bash
    npm i
    ```
2. 打包
    ```bash
    npm run build:extension
    ```

### NPM Script 说明
- **```pack:extensionscript```:** 用于生成实际的 content-script.js 和 inject-script.js

- **```afterbuild```:** 用于将打包后的 html 文件中的 inline script 抽离出来以 src 的方式引入。这是由于 chrome 插件不需要内置 html 使用 inline script

- **```zip:extension```:** 生成插件的打包文件，方便分发，也可将 zip 文件防止在项目 release

### 配置说明
- **```extension.next.config.js```:** 插件实际的 next 配置，另外保留原有的 ```next.config.js``` 便于本地 ```npm run dev``` 时调试 html 的样式

- **```extension.webpack.config.js```:** 对应 npm script 为 ```pack:extensionscript```, 用于两个 script 文件的打包，也可以自行增加其他 script
