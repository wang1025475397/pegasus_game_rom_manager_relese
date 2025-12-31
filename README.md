# 天马前端游戏ROM管理器

## 简介

游戏ROM管理器是一个基于Python和PyQt5的桌面应用程序，用于管理和展示游戏ROM集合。该程序通过解析Pegasus前端的metadata.pegasus.txt文件来加载游戏信息，并关联媒体资源，提供直观的用户界面来浏览和管理游戏集合。

## 功能特性

1. 扫描指定目录及其子目录下的metadata.pegasus.txt文件
2. 解析元数据文件，提取游戏和平台信息
3. 关联游戏媒体资源（图片、视频等）
4. 检查ROM文件存在性状态
5. 提供三栏式用户界面展示平台、游戏列表和游戏详情
6. 不存在的ROM以红色显示
7. 支持多种元数据属性展示（开发商、发行商、类型、评分等）
8. 使用多线程扫描避免界面卡死

## 界面布局

程序采用三栏式布局：
- 左侧：平台列表
- 中间：游戏列表
- 右侧：游戏详情
![界面截图](界面截图.png)

## 使用方法

1. 运行程序

2. 在界面中选择包含游戏ROM的根目录（例如：F:\天马精简包\Roms）

3. 点击"扫描"按钮加载游戏数据

4. 在左侧平台列表中选择一个平台

5. 在中间游戏列表中选择一个游戏查看详细信息

## 目录结构要求

程序期望以下目录结构：

```
游戏根目录/
├── 平台1/
│   ├── metadata.pegasus.txt 或 metadata.txt
│   ├── media/ 或 .media/
│   │   ├── 游戏1封面.png
│   │   ├── 游戏1截图1.png
│   │   └── ...
│   ├── 游戏1.rom
│   └── 游戏2.rom
├── 平台2/
│   ├── metadata.pegasus.txt 或 metadata.txt
│   └── ...
└── ...
```

## 支持的元数据属性

### 平台属性
- `collection`: 平台名称
- `launcher`: 启动器路径

### 游戏属性
- `game`: 游戏标题
- `file`/`files`: ROM文件路径
- `developer`/`developers`: 开发商
- `publisher`/`publishers`: 发行商
- `genre`/`genres`: 游戏类型
- `players`: 玩家人数
- `releaseDate`: 发布日期
- `rating`: 评分
- `summary`: 简介
- `description`: 详细描述

### 媒体资源属性
- `boxFront`: 封面图片
- `screenshot`/`screenshots`: 截图
- `video`/`videos`: 视频

## 支持的媒体资源格式

- 图片：.png, .jpg, .jpeg, .gif, .bmp, .webp
- 视频：.mp4, .avi, .mkv, .webm, .mov

## 问题修复记录

### 界面显示问题
- 修复了界面只显示扫描目录，左中右三栏不显示的问题
- 优化了界面布局创建逻辑

### 程序卡死问题
- 修复了点击扫描按钮后程序卡死崩溃的问题
- 使用PyQt多线程机制避免主线程阻塞
- 添加了扫描过程中的状态提示和按钮状态管理


## 许可证

MIT License
