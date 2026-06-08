# Figma Hub - 原型代码管理

管理和分发 Figma 插件原型代码的统一平台。每个项目包含可直接在 Figma 中运行的 Scripter 插件代码，自动生成完整交互原型。

## 使用方法

### 1. 在线查看

访问 [Figma Hub 主页](https://smith12138.github.io/html-pages/figma/) 查看所有项目，点击项目卡片可查看详情并一键复制代码。

### 2. 在 Figma 中运行

1. 打开 Figma 设计文件（浏览器版或桌面版均可）
2. 主菜单 → **Plugins** → 搜索 **Scripter** → 运行
3. 在 Scripter 编辑器中点击 **"+"** 新建脚本
4. **Cmd+A** 全选 → **Cmd+V** 粘贴代码
5. 点击右上角 **▶** 运行按钮

运行后原型页面会自动生成在 Figma 画布上。

### 3. 首次使用 Scripter

如果你的 Figma 中没有安装过 Scripter 插件：

1. 进入 Figma → 主菜单 → **Plugins** → **Manage plugins**
2. 搜索 **Scripter**（作者：Rasmus）
3. 点击安装
4. 安装后即可在 Plugins 菜单中找到并运行

## 目录结构

```
figma/
├── index.html              # Figma Hub 主页面
├── README.md               # 本文档
└── {项目名}/
    ├── meta.json            # 项目元信息（名称、描述、页面列表等）
    └── prototype.js         # Figma Scripter 插件代码
```

## 添加新项目

1. 在 `figma/` 下创建项目目录，如 `figma/MyProject/`
2. 将 Scripter 代码保存为 `prototype.js`
3. 创建 `meta.json` 描述项目信息：

```json
{
  "name": "项目名称",
  "description": "项目描述",
  "color": "#7c3aed",
  "version": "1.0.0",
  "date": "2026-06-08",
  "screens": 5,
  "screenList": ["页面1", "页面2", "页面3", "页面4", "页面5"],
  "file": "prototype.js",
  "tags": ["标签1", "标签2"]
}
```

4. 在 `index.html` 的 `knownProjects` 数组中添加项目目录名

## 当前项目

| 项目 | 描述 | 页面数 | 日期 |
|------|------|--------|------|
| SaleSmartly | 跨境全渠道私域沟通SaaS平台 - 完整前后台原型 | 12 | 2026-06-08 |

## 技术说明

- 原型代码基于 [Figma Plugin API](https://www.figma.com/plugin-docs/) 编写
- 通过 [Scripter](https://www.figma.com/community/plugin/757836922707087381) 社区插件执行
- 代码使用 Inter 字体族（Figma 内置支持）
- 每个页面为独立的 1440×900 Frame，自动网格排列在画布上
