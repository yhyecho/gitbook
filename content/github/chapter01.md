### 备份原始文档到github
- 新建content文件夹,并将README.md, SUMMARY.md和自己建立的md文件拷贝进该文件夹
- 进入my-note文件夹，并将该文件夹进行npm项目初始化
```
cd my-note
npm init -y
```
- 用vim编辑器打开package.json,添加如下脚本
```
"scripts": {
  "start": "gitbook serve ./content ./gh-pages",
  "build": "gitbook build ./content ./gh-pages",
  "deploy": "node ./scripts/deploy-gh-pages.js",
  "publish": "npm run build && npm run deploy",  
  "port": "lsof -i :35729"
},
```
> npm start 作用：执行gitbook命令编译content文件夹中的内容到gh-pages文件夹中，并本地运行
> npm build 作用：编译content文件夹中的内容到gh-pages文件夹中                         
> npm deploy 作用：部署gh-pages中的文件到gh-pages分支中                           
> npm publish 作用：编译并部署gitbook生成的文档到gh-pages分支

- 用vim编辑.gitignore文件(添加需要被忽略的文件和文件夹)
```
gh-pages
.DS_Store
_book
```
- 到github上创建公开仓库gitbook,拿到仓库地址并和本地进行关联
```
git init // git目录初始化
git remote add origin git@github.com:yhyecho/gitbook.git // 本地和远程仓库建立关联关系
git add . // 添加当前目录下的没有被ignore的文件进版本控制区
git commit -m 'git init commit' // 提交版本
git push -u origin master // 发布版本到github
```
- 执行npm start命令
执行该命令后会发现当前目录生成了一个gh-pages文件夹
> 该文件夹中的内容是content文件夹经过gitbook命令编译后得到的静态html文件
