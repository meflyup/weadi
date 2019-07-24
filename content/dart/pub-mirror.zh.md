---
title: "dart pub 库镜像设置"
date: 2019-07-23T21:10:11+08:00
draft: false
weight: 2
---

### 设置dart pub 镜像
由于不知名原因，从 https://pub.dev/ 进行pub get 常常掉线。故可以设置一个清华的镜像
- windows环境
  设置环境变量
  ![](/images/PUB_HOST_URL.png)
```
PUB_HOSTED_URL="https://mirrors.tuna.tsinghua.edu.cn/dart-pub/"
```
