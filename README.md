# 仓库描述

> 基于开源项目MediaCrawler开发的小红书爬虫，仅供学习交流。

## 项目初始化👏

### 1. 安装Poetry项目管理工具

请以[Poetry官方文档](https://python-poetry.org/docs/)为准。

#### 安装pipx

```shell
py -m pip install --user pipx
```

#### 安装poetry

```shell
pipx install poetry
```

### 2. 克隆本仓库

```shell
git clone git@github.com:McDj26/RED_crawler.git
```

### 3. 配置虚拟环境

<small>*若熟悉如何配置满足条件的环境，可以跳过该步骤。*</small>

此处以使用 `miniconda` 与vscode的 `Python` 插件为例。

#### 创建Python3.8环境

打开 `conda` 或 `miniconda` 控制台，创建名为 `py3_8` 的虚拟环境。

```shell
conda create -n py3_8 python=3.8
```

#### 配置项目虚拟环境

打开vscode，在顶栏通过选项 `File -> Open Folder` 打开文件夹目录，选择 `RED_crawler` 文件夹作为工作目录，然后在侧边栏找到插件图标。*（若无图标则请安装Python插件）*

![alt text](<img/1.png>)

在 `GLOBAL ENVIRONMENTS` 中找到 `py3_8`，选择 `Set as active workspace interpreter`（图中⭐号）

![alt text](<img/2.png>)

### 4. 安装项目依赖

在顶栏通过选项 `Terminal -> New Terminal` 打开新的控制台，通过下面的命令安装项目依赖。

```shell
poetry check
```

安装依赖完成后能看到 `All set!` 的提示。

### 5. 安装playwright浏览器驱动

```shell
playwright install
```

## 项目规范说明🙏

### 项目结构

源代码放在 `redcrawler` 文件夹中。

```txt
redcrawler
| -- crawler.py
| -- predictor.py
| -- models
|    | -- model.pth
poetry.lock
pyproject.toml
```

### 添加项目依赖

与Cargo包管理器的 `cargo add` 类似，除了普通pypi包外，还支持其它poetry项目，项目依赖信息保存在 `pyproject.toml` 文件中。

```shell
poetry add package
```

### 构建项目

```shell
poetry build
```

该命令会将项目打包到 `dist` 文件夹下，包括一个 `.tar.gz` 文件和 `.whl` 文件，与其它pypi包相同，可以通过这两个文件进行安装本项目，也可以编辑 `pyproject.toml` 使用github仓库地址将本项目加入依赖项。

```toml
[tool.poetry.dependencies]
redcrawler = {git = "git@github.com:McDj26/RED_crawler.git", branch = "main"}
```

修改后需要执行命令锁定依赖版本。

```shell
poetry lock
```

### 旋转验证码预测模型使用

#### 1. 下载模型文件*.pth

#### 2. 模型文件保存至redcrawler/models文件夹

#### 3. 通过接口使用预测模型

```py
from predictor import predict
predict(background_image, center_image)
```
#   w e i b o C r a w l e r  
 #   w e i b o C r a w l e r  
 "# weiboCrawler" 
