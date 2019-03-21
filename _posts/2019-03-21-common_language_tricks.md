---
layout: post
title: 常用语法（持续更新）
date: 2019-03-21
categories: language tricks
tags: Docker
---


## Docker

### 常用命令

```python
# 列出本地镜像
docker images
# 列出容器
docker container ls

# 上传镜像
docker login --username=dockerliang
docker build -t dockerliang/ali-xqx-gpu:v1.0 .
docker push dockerliang/myubuntu
# 下载
docker pull ubuntu:16.04
# 运行
docker run -it --rm ubuntu:16.04 bash

# 镜像重命名
sudo docker tag dianchi_train:0413 caffe2_template:train

# 进入运行中的镜像
sudo docker ps
sudo docker exec -it 7eddfd /bin/bash

# 保存
sudo docker save 6bde8d8dbb2d > leqidianchi_v3.tar
sudo docker load --input leqidianchi_v3.tar
```

### 运行脚本示例

```python
# -e 环境参数
sudo nvidia-docker run -it --rm \
-e CUDA_VISIBLE_DEVICES=1 \
-p 5000:5000 \
-v /home/xinqixiang/ali-xqx-for-docker/ali-xqx-code/data:/ali-xqx-code/data \
-v /home/xinqixiang/ali-xqx-for-docker/ali-xqx-code/models:/ali-xqx-code/models \
hongpu/ali-xqx-gpu:v1.0 \
/bin/bash /ali-xqx-code/run.sh
```

### 修改保存镜像

```python
# 1. 进入镜像：
sudo docker run -it ubuntu:16.04 /bin/bash
# 2. 进行改动，记住id
# 3. 退出
# 4. 保存
sudo docker commit -m “some commit” bdd5b0be0713 ubuntu_new:16.04
```

### Dockerfile示例

```python
FROM uhub.service.ucloud.cn/uaishare/gpu_uaitrain_ubuntu-14.04_python-2.7.6_caffe-py-faster-rcnn:v1.0
COPY for-docker/ /ali-xqx-code/
RUN pip install --requirement /ali-xqx-code/web_demo_yumi/requirements.txt
```

## Git

[参考地址](https://git-scm.com/book/zh/v1/自定义-Git-配置-Git)
[参考地址](https://code.aliyun.com/help/ssh/README)

### 配置

```bash
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@e.com

ssh-keygen -t rsa -C "liangxw1990@gmail.com"
cat ~/.ssh/id_rsa.pub
```

### 常用配置

```bash
# 拉取所有分支
git pull origin

# 新建分支
git branch BRANCH_NAME

# 查看当前分支
git branch

# 查看所有分支
git branch -a

# 切换分支
git checkout BRANCH_NAME
```

## 正则表达式

```python
# 找出所有的数字
a = int(''.join(re.findall(r"\d+\:?\d*", c)))

# 找出所有的非数字
b = re.findall(r"\D+\:?\D*", c)
```
