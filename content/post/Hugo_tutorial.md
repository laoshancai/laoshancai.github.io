---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Hugo_tutorial"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2019-09-06T11:45:04+08:00
lastmod: 2019-09-06T11:45:04+08:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

# hugo + github + academic 搭建博客(实验室主页)



## **下载hugo**，并配置

1. 下载hugo，解压。
2. 将解压后的文件夹路径添加到环境变量(方便命令行调用)。



## github

1. [Fork](https://github.com/sourcethemes/academic-kickstart#fork-destination-box) the *Academic Kickstart* repository to create a new website(将academic模板fork到自己的github里)

2. 将远程仓库拉下来，在本地新建一个文件夹建立academic模板本地仓库。

   ```bash
   git clone https://github.com/yourusername/academic-kickstart-1.git My_Website
   ```

3. Initialize the theme(初始化主题)

   ```bash
   cd My_Website
   git submodule update --init --recursive
   ```



### hugo编译 & github部署



```bash
# 下面是hugo的一些命令行常用操作

# 生成站点
hugo new site 文件名称 (如blog)

# 生成文章
# 执行后，会自动在content/post下生成 test.md文件，打开可编辑内容，ps.文件头部的draft要改为false，这样部署后才能看到文章。
hugo new post/test.md

# (站点根目录下执行)执行后，站点根目录下会生成一个 public 文件夹，该文件下的内容即Hugo生成的整个静态网站。每次更新内容后，将 public 目录里所有文件 push到GitHub即可。
hugo


```



```bash
# 在github上新建repository(Creat a new repository),仓库名为username.github.io
# 将用作网页部署的仓库git clone 到本地，建立本地仓库，每次更新的文件都拖到这里push上去。
$ git clone https://github.com/laoshancai/laoshancai.github.io.git my_site

#origin一般是默认命名，可以自己定义名字
$ git remote add origin https://github.com/yourname/yourname.github.io.git (换成自己的)　　将本地目录链接到远程服务器的代码仓库

# 查看远程仓库情况
$ git remote -v 


#建好仓库后，每次更新完文件之后执行的操作。
$ git add -A

$ git commit -m "first commit"

$ git push -u origin master
```

