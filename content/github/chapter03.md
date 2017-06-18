### 使用脚本自动化部署gitbook到gh-pages
- 手动部署gitbook的步骤
 - 第一步：运行 npm run build ，来把 md 文件翻译成 html 放到 gh-pages 文件夹
 - 第二步，拷贝 gh-pages 中的所有文件，到本仓库的 gh-pages 分支，然后上传
 - 第三步，以后每次修改完都需要拷贝到 gh-pages 分支，很麻烦

- 安装gh-pages包
```
cd my-note/
npm i --save gh-pages
```
- 然后创建 my-note/scripts/deploy-gh-pages.js               

  ```js
  'use strict';

  var ghpages = require('gh-pages');

  main();

  function main() {
      ghpages.publish('./gh-pages', console.error.bind(console));
  }
  ```
- 这样，每次文稿有了修改后，运行
```
npm run publish
```
- 就可以把文稿部署到
```
https://yhyecho.github.io/gitbook/
```

- 编辑.gitignore文件添加忽略node_modules文件夹
```
vim .gitignore
node_modules
```
- 重新做版本提交到远程仓库
```
git add .
git commit -m 'add auto deploy-gh-pages script'
git push
```
