### gitbook初始化
- 全局安装GitBook
```js
npm install -g gitbook-cli
```
- 创建一个笔记文件夹
```
mkdir my-note
```
- 然后执行以下命令
```
cd my-note
gitbook init
```
- 这样可以生成以下两个文件
  * README.md 的内容会显示在书皮上
  * SUMMARY.md 是目录
- 启动服务器，查看和编辑书籍
```
gitbook serve
```
- 这样，可以启动一个服务器，然后到 localhost:4000 端口，就可以看到这本书了。
