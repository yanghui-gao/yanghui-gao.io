---
layout:     post
title:       [!] CDN: trunk Repo update failed
subtitle:   cocoapods那些事
date:       2019-12-27
author:     BY
header-img: img/error-bg-ED.jpg
catalog: true
tags:
    - iOS
    - cocoapods
    - 问题记录
---

## [!] CDN: trunk Repo update failed: 

##### 问题版本
`cocoapods version: 1.8.4`
##### 问题表象: 
 `pod install`  `pod update` 时报错 `trunk Repo update failed`
##### 问题原因:
从cocoapods 1.7.2版本开始 cocoapods开始尝试添加CDN支持,但并未设置为默认配置,直到1.8.0版本正式将CDN作为默认源,出现这个问题是因为CDN节点访问失败导致的。
##### 问题解决:
既然是访问节点失败导致的, 2种解决办法 

方案一 不访问CDN节点继续使用`master repo`(不推荐) :
  
  Podfile文件中设置源为：
 `source 'https://github.com/CocoaPods/Specs.git'` 可以解决 `pod install 或 pod update`

方案二 解决CDN节点访问失败(推荐):

- 2.1: 修改hosts文件 `sudo vim /etc/hosts` 添加 `199.232.28.133 raw.githubusercontent.com` 即可解决CDN访问失败的问题
- 2.2: 终端代理
- 2.3: 不断重试

`tip: `

- 如果你使用到了私有库要添加 `source 'https://cdn.cocoapods.org/'`
- podfile大小写敏感

#### 总结
由于CDN的不确定性如果你希望可以稳定处理cocopods那就使用第一种方案,如果方案二可以顺利执行的话 你可以尝试 删除master repo `pod repo remove master`这样可以为你节省大于1GB的磁盘空间,同时可以体验到不错的下载速度(),但是由于各地CDN节点的不同是否真正提高效率还得实践出真理。不用安装庞大的master repo也是真的香。
## 参考资源
[官方地址](https://blog.cocoapods.org/CocoaPods-1.7.2/)

[github_issues_9303](https://github.com/CocoaPods/CocoaPods/issues/9303)


