---
title: 使用 Nvidia 的 Cuda 引擎对图片和视频进行处理
icon: github
---

> Author: Cola 
> Time: 2023.1.29 9:20 AM
> To: 使用 Nvidia 的 Cuda 引擎对图片和视频进行处理

---

> 该技术采用的是 由南阳理工大学的 S-LAB 实验室开发的开源项目 [CodeFormer](https://github.com/sczhou/CodeFormer) 。
>
> 可以实现：
>
> - 照片修复
> - 视频修复

# Features

> - [x] 大致结构
> - [ ] 上传

## 一、CodeFormer 的安装

> - [ ] Python 环境的安装
> - [ ] PyTorch 的安装
> - [ ] 依赖安装

### 1.1 Python 环境的安装

> 进入 [Python 官网]( https://www.python.org/) 下载 Python 安装包
>
> 步骤：
>
> 1. 下载安装包
> 2. 添加环境变量
> 3. 完成

![image-20230129123112081](/image-20230129123112081.png)

> 将 Python 添加到环境变量后选择自定义安装

![image-20230129123249428](/image-20230129123249428.png)

> 确保全部勾选

![image-20230129123300913](/image-20230129123300913.png)

> 默认

![image-20230129123311459](/image-20230129123311459.png)

> 完成安装

![image-20230129123407548](/image-20230129123407548.png)

### 1.2 PyTorch 的安装

> 进入 [PyTorch 官网]( https://pytorch.org/) 下载 PyTorch 安装包

> 选择相应的配置进行安装

![image-20230129124539150](/image-20230129124539150.png)

> CUDA 的版本可通过终端输入 `nvidia-smi` 来获取

![image-20230129124621922](/image-20230129124621922.png)

### 1.3 依赖安装

> 在项目目录中输入： `pip3 install -r requirements.txt` 进行依赖的安装

![image-20230129124935292](/image-20230129124935292.png)

### 1.4 构建工程

> 在项目目录中输入：`python basicsr/setup.py develop` 进行工程的构建、

### 1.5 安装训练模型

> CodeFormer 为我们提供了两种训练模型：
>
> - facelib pretrained models
> - CodeFormer pretrained models

#### 1.5.1 facelib pretrained models 模型的安装

> 在项目目录下输入 `python scripts/download_pretrained_models.py facelib`

#### 1.5.2 CodeFormer pretrained models 模型的安装

> 在项目目录下 `python scripts/download_pretrained_models.py CodeFormer`

## 二、CodeFormer 的使用

> - [ ] 图像处理
> - [ ] 视频处理

### 2.1 图像处理

> - [ ] 简单图片的处理
> - [ ] 复杂图片的处理

#### 2.1.1 简单图片的处理

> 该方案适用于单个人脸的处理 命令为 `python inference_codeformer.py -w 0.5 --has_aligned --input_path [image folder]|[image path]`

#### 2.1.2 复杂图片的处理

> 该方案适用于多个人脸的处理 命令为 `python inference_codeformer.py -w 0.7 --input_path [image folder]|[image path]`

### 2.2 视频处理

> - [ ] 视频的处理

#### 2.2.1 视频的处理

> 首先安装 `conda install -c conda-forge ffmpeg`
>
> 其次开始使用：`python inference_codeformer.py --bg_upsampler realesrgan --face_upsample -w 1.0 --input_path [video path]`