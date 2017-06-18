### 发布gitbook到gh-pages分支
- 新建并切换到gh-pages分支
```
git checkout -b gh-pages
```
- 拷贝gh-pages中的所有文件到git控制的根目录，也就是我们这的my-note目录
- 提交所有更改到gh-pages分支上
```
git add .
git commit -m 'gh-pages init'
git push -u origin gh-pages
```
- 访问自己的项目主页查看，发布情况
```
https://yhyecho.github.io/gitbook/
```
- 切换回master分支，进行文档的继续编辑
git checkout master
