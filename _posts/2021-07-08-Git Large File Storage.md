---
layout:     post
title:      Git Large File Storage
subtitle:   使用 git-lfs 上传大文件
date:       2021-07-08
author:     ED
header-img: img/post-bg-debug.png
catalog: true
tags:
	- Git
---

# Git Large File Storage

### 关于

向 GitHub 推送大于 Git 推送限制的文件, 我这边的限制是 100MB 所以只要大于100MB 的都需要使用该工具上传 然后再提交 GitHub

### 安装

- 运行 ```brew install git-lfs``` 安装

- 验证是否安装成功
  
  ```$ git lfs install ```
  
  ``` > Git LFS initialized.```

### 使用

```git lfs track 文件名```

```git add .gitattributes```

``` git commit -m "add model file"```

```git push```

就可以成功将大文件上传至git, git项目中实际添加的是大文件索引, 实际的文件上传至

### 参考链接

[GitHub Docs](https://docs.github.com/cn/github/managing-large-files/versioning-large-files/installing-git-large-file-storage)
