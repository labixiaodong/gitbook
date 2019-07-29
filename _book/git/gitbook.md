#  结合 GitHub Pages 使用 GitBook

### 1、安装node.js

gitbook是Node.js环境下，用于构建电子书的工具，所以要先安装Node.js。

下载链接：https://nodejs.org/en/

![1564402040186](C:\Users\hfjy\AppData\Roaming\Typora\typora-user-images\1564402040186.png)

### 2、安装gitbook-cli

gitbook-cli 是gitbook的命令行工具，可在cmd中运行如下命令：

```
npm install -g gitbook-cli
```

执行下面命令，查看 `gitbook-cli` 的版本，以确定其是否成功安装。

```
$ gitbook -V
CLI version: 2.3.2
GitBook version: 3.2.3
```

### 3、构建电子书

#### 3.1 创建存储电子书所用的文件夹，并cd到该文件夹

```
$ mkdir book
$ cd book
```

#### 3.2 初始化电子书：

```
$ gitbook init
```

这时候会生成下面两个文件：

```
├── README.md
└── SUMMARY.md
```

#### 3.3 启动gitbook

```
$ gitbook serve
```

启动之后可打开浏览器，在[http://localhost:4000](http://localhost:4000/)，查看最终效果。

这一步会生成_book文件夹；

### 4、结合github Pages

GitHub Pages 是 GitHub 提供的静态网站托管服务。

GitHub 上的每个仓库都可以拥有一个 GitHub Pages，对应的 URL 如下：

```
https://<username>.github.io/<repository>/
```

其中，<username>是你的github用户名，<repository>是项目名称。

GitHub Pages 的静态资源支持下面 3 个来源：

-  `master` 分支
-  `master` 分支的 `/docs` 目录
-  `gh-pages` 分支

#### 4.1 新建github项目

新建github项目有两种方法，一种是在本地使用git命令行，一种是在github网页上新建：

##### 4.1.1 本地命令行新建

```python
git init
git remote add origin https://github.com/github账号/项目名(需与本地目录一致).git
```

##### 4.1.2 网页新建

![1564403114814](C:\Users\hfjy\AppData\Roaming\Typora\typora-user-images\1564403114814.png)

![1564403225830](C:\Users\hfjy\AppData\Roaming\Typora\typora-user-images\1564403225830.png)

并克隆到本地；

#### 4.2 把本地项目推到github

```python
git add .
git commit -m 'init' 
git push -u origin master
```

#### 4.3 将远程文件的推到其他分支

 `_book` 目录中包含静态电子书页面，执行下面命令，将 `_book` 目录推送到 GitHub 仓库的 `gh-pages` 分支，

便于他人访问；

```
$ git subtree push --prefix=_book origin gh-pages
```

### 5 更新gitbook

工具：markdown编辑器 [typora](https://typora.io/)

每次更新之后需要执行命令：

```
$ gitbook build
```

这一步是把更新的内容同步到_book文件夹中；

接着推到github:

```python
git add .
git commit -m 'aaa' 
git push
```

并推到gh-pages分支：

```
$ git subtree push --prefix=_book origin gh-pages
```

