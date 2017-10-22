# Git

## 什么是Git?
  - Git是一款源代码管理工具(版本控制工具)
    - 我们写的代码需要使用Git进行管理。
  - 源代码有必要管理起吗？
  - 有必要，因为人工的去处理不同的版本，做相应备份会很麻烦。
  - Git是linux之父当年为了维护linux---linus之前也是手动维护合并把文件发给Linus
  - linus自己写了一个版本管理的工具(Git)

## Git安装
    - 根据自己电脑的位数进行安装(以64位为例)
        - 安装这个文件：Git-2.8.4-64-bit.exe

##### 安装32位

<img src="./media/01安装32位.png">

##### 安装64位

<img src="./media/02安装64位.png">

~~~
 右键查看是否安装成功
~~~

<img src="./media/03查看是否安装.png">

## 初始化Git仓储/(仓库)

- 这个仓库会存放，git对我们项目代码进行备份的文件

- 在项目目录右键打开 git bash

  <img src="./media/04强制自习git01.jpg">

- 命令

  ~~~	
  git init 回车
  ~~~

   <img src="./media/05强制自习git02.jpg">

  ​


## 自报家门(配置个人信息)
- 就是在git中设置当前使用的用户是谁
- 每一次备份都会把当前备份者的信息存储起来
- 命令: 
    + 配置用户名:`git config --global user.name "xiaoming"`

      <img src="media/06强制自习git03.jpg">

    + 只要是符合邮箱的格式即可

    + 配置邮箱:  `git config --global user.email "xm@sina.com"`

      <img src="./media/07强制自习git04.jpg">


## 把大象放到冰箱要几步
1. 打开冰箱门

2. 放大象

3. 关上冰箱

   <img src="./media/大象.jpg">

   ​

## 把代码存储到.git仓储中
- 1.把代码放到仓储的门口（暂存区）
    + `git add ./readme.md` 所指定的文件放到大门口
    + `git add ./` 把所有的修改的文件添加到大门口
- 2.把仓储门口的代码放到里面的房间中去
    + `git commit -m "这是对这次添加的东西的说明" `

<img src="./media/08强制自习git05.jpg">

## 查看当前的状态

- 可以用来查看当前代码有没有被放到仓储中去

- 命令: `git status`

  <img src="./media/09强制自习git06.jpg">

## 查看日志
- `git log` 查看历史提交的日志
- `git log --oneline` 可以看到简洁版的日志

## 回退到指定的版本

- `git reset --hard [版本号]`
    + 可以通过版本号精确的回退到某一次提交时的状态

- `git reflog`
  + 可以看到每一次切换版本的记录:可以看到所有提交的版本号

### GitHub 
- https://github.com
- 不是git,只是一个网站
- 只不过这个网站提供了允许别通过git上传代码的功能

### 提交代码到github(当作git服务器来用)
- `git push [地址] master`
 + 示例: `git push https://github.com/huoqishi/test112.git master`
 + 会把当前分支的内容上传到远程的master分支上

- `git pull [地址] master`
 + 示例: `git pull https://github.com/huoqishi/test112.git master`
 + 会把远程分支的数据得到:(*注意本地-要初始一个仓储!*)

- `git clone [地址]`
 + 会得到远程仓储相同的数据,如果多次执行会覆盖本地内容。

## ssh方式上传代码
- 不需要输入用户名和密码，就可以验证上传者的身份
- 公钥 私钥,两者之间是有关联的。
- 生成公钥,和私钥
    + `ssh-keygen -t rsa`

    + 在电脑C:\Users\用户名\.ssh文件夹下

        ​

        + id_rsa.pub 公钥

        + id_rsa 私钥

          <img src="./media/10强制自习git07.jpg">

        + 将公钥打开，复制里面的内容

        + 打开gitHub找到个人用户头像中的Settings

        + 找到右侧SSH and GPG keys

          <img src="./media/github.png">

        + 创建一个New SSH key,将复制的公钥添加进去

