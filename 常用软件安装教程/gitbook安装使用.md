# gitbook安装使用

## 1. gitbook软件的本地安装

GitBook是一个能将使用 Markdown 语法，快速制作成各种格式电子书的工具。它是一个基于 [Node](https://so.csdn.net/so/search?q=Node&spm=1001.2101.3001.7020).js 的命令行工具，可以用来制作精美的电子书。首先我们得下载Nodejs并安装

>注意: 截止到目前的 Gitbook V3.2.3版本，需要使用NodeJs的v10+版本，否则会产生各种报错。
>
>这里建议下载`v10.23.1`版本，官网最新版本我试了也是不行的。Node.js的版本最终使用的是v12.22.10

### 1.1  安装Nodejs

Node.js下载地址：https://nodejs.org/zh-cn/download/releases/

里面有压缩包格式的，也有安装包格式的。使用压缩包格式的解压之后不用安装，**但是要自己配置环境变量**。使用安装包格式的安装过程中会帮我们配置环境变量。我是windows系统，下载msi格式的安装包安装。安装过程是傻瓜式安装，下一步就好。

NodeJs都会默认安装npm(包管理工具),所以不需要单独安装npm。

安装结束后，检查环境变量是否正确配置：

<div align=left>
<img src=F:\BaiduNetdiskWorkspace\MyGitBook\常用软件安装教程\img\01.png />
</div>

### 1.2 安装GitBook

接下来使用`npm`命令安装`gitbook-cli`。它是在同一系统上安装和使用多个版本的GitBook的实用程序。它将自动安装所需版本的GitBook程序。（可能需要一些时间，耐心等待就行）

```bash
npm install gitbook-cli -g
```

查看是否安装成功

```bash
gitbook -V
```

<div align=left>
<img src=F:\BaiduNetdiskWorkspace\MyGitBook\常用软件安装教程\img\02.png />
</div>

### 1.3 GitBook基本使用

```bash
gitbook init #初始化命令
gitbook serve #启动服务
gitbook install #安装插件
gitbook build #在本地生成电子书html文件
```

使用gitbook init命令会生成 ReadMe.md 和 Summary.md两个文件。Summary.md是目录文件，ReadMe.md是描述文件
之后编写Summary.md文件
```md
* [Notes](README.md)
* [1.计算机基础](计算机基础/ReadMe.md)
    * [1.1 计算机组成原理 ](计算机基础/计算机组成原理.md)
    * [1.2 Linux常用命令](计算机基础/Linux常用命令.md)
* [2. 数据结构与算法](数据结构与算法/ReadMe.md)
* [3. 常用软件安装教程](常用软件安装教程/ReadMe.md)
    * [3.1 gitbook安装使用](常用软件安装教程/gitbook安装使用.md)
```
编写完成之后，使用gitbook init生成目录中的文件，或者自己手动创建也可以。

完成编写之后使用 gitbook build 命令或者 gitbook serve命令生成电子书。

## 2. gitbook结合github

上述的gitbook生成的电子书要不是在我们本地，要么是本机电脑起的服务，如果电脑关闭了就访问不到了。使用github结合gitbook能够将我们的电子书发布到网上，知道域名就可以随时访问。

步骤如下：
1. 在github上创建一个仓库，将写的内容通过git上传到仓库中
2. 在gitbook网站上注册一个账号，并创建一个orgnization
3. 在gitbook上同步github(同步某个仓库的某个分支)
4. 然后在gitbook上发布电子书，就可以得到一个域名，任何地方都可以访问了

以后如果我们在本地有修改，上传到github上，内容也会自动同步到gitbook网站上，只要重新发布修改的内容就会更新电子书。