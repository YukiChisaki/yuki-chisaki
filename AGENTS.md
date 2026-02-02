# 项目概述

这是一个基于 VitePress 和 Teek 主题构建的个人博客项目。项目名称为 "Yuki Chisaki"，是一个轻量、简洁高效、灵活配置且易于扩展的静态站点。

## 项目类型

**代码项目** - VitePress 博客系统

## 核心技术栈

- **VitePress** (^1.6.3) - 静态站点生成器
- **VitePress Theme Teek** (^1.5.4) - VitePress 主题，提供博客风格功能
- **Vue** (^3.5.16) - 前端框架
- **TypeScript** - 类型安全的 JavaScript 超集
- **Sass** (^1.89.1) - CSS 预处理器
- **ECharts** (^5.6.0) - 图表库
- **VitePress Plugin LLMS** (^1.7.3) - Vite 插件

## 项目结构

```
D:\blog\yukichisaki\
├───AGENTS.md                          # 代理上下文文件（本文件）
└───vitepress-theme-teek-docs-template\
    ├───docs\                          # 文档根目录
    │   ├───.vitepress\                # VitePress 配置目录
    │   │   ├───config.ts              # VitePress 主配置文件
    │   │   ├───teekConfig.ts          # Teek 主题配置文件
    │   │   ├───theme\                 # 主题扩展目录
    │   │   │   ├───components\        # 自定义组件
    │   │   │   └───styles\            # 自定义样式
    │   │   └───cache\                 # VitePress 缓存目录
    │   ├───@pages\                    # 功能页面
    │   │   ├───archivesPage.md        # 归档页
    │   │   ├───articleOverviewPage.md # 清单页
    │   │   ├───categoriesPage.md      # 分类页
    │   │   ├───loginPage.md           # 登录页
    │   │   ├───riskLinkPage.md        # 风险链接提示页
    │   │   └───tagsPage.md            # 标签页
    │   ├───01.指南\                   # 使用指南文档
    │   │   ├───01.简介\               # 主题介绍
    │   │   ├───10.使用\               # 使用方法
    │   │   ├───20.相关\               # 相关内容
    │   │   └───40.开发\               # 开发指南
    │   ├───10.配置\                   # 配置文档
    │   │   └───01.主题配置\           # 主题配置说明
    │   ├───15.主题开发\               # 主题开发文档
    │   ├───blog\                      # 博客文章目录
    │   │   ├───about.md               # 关于页面
    │   │   ├───hello_blog.md          # 欢迎文章
    │   │   └───*.md                   # 其他博客文章
    │   └───public\                    # 静态资源目录
    │       ├───blog\                  # 博客背景图
    │       ├───login\                 # 登录页资源
    │       └───qrcode\                # 二维码图片
    ├───package.json                   # 项目依赖配置
    └───node_modules\                  # 依赖包目录
```

## 构建和运行

### 开发模式

启动本地开发服务器，支持热更新：

```powershell
# 进入项目目录
cd D:\blog\yukichisaki\vitepress-theme-teek-docs-template

# 使用 pnpm（推荐）
pnpm run docs:dev

# 或使用 npm
npm run docs:dev
```

开发服务器默认运行在 `http://localhost:5173`

### 生产构建

构建生产版本：

```powershell
# 使用 pnpm
pnpm run docs:build

# 或使用 npm
npm run docs:build
```

构建产物将生成在 `docs/.vitepress/dist` 目录

### 预览构建结果

预览生产构建：

```powershell
# 使用 pnpm
pnpm run docs:preview

# 或使用 npm
npm run docs:preview
```

## 开发约定

### 文件命名规范

- **博客文章**：使用有意义的文件名，如 `hello_blog.md`、`about.md`
- **文档页面**：按照功能分区命名，如 `01.简介`、`10.配置`、`15.主题开发`
- **配置文件**：使用 TypeScript 格式，如 `config.ts`、`teekConfig.ts`

### Frontmatter 配置

博客文章需要包含以下 frontmatter 字段：

```yaml
---
title: 文章标题
pubDate: 2025-10-19T00:00:00.000Z
categories:
  - 分类名称
description: 文章描述
slug: 文章别名
createTime: 2025/10/20 23:04:33
permalink: /blog/hello
---
```

### 目录组织

- **博客文章**：放在 `docs/blog/` 目录下
- **功能页面**：放在 `docs/@pages/` 目录下
- **文档内容**：按照功能分区组织在 `docs/` 下的对应目录

### 主题配置

- VitePress 配置：`docs/.vitepress/config.ts`
- Teek 主题配置：`docs/.vitepress/teekConfig.ts`

当前主题配置：
- `teekHome: false` - 关闭博客首页
- `vpHome: true` - 显示 VitePress 首页
- `sidebarTrigger: true` - 开启侧边栏折叠功能
- 作者信息：Teeker (https://github.com/Kele-Bingtang)

### 导航结构

主导航包含：
- 博客 (/blog/)
- 指南 (/01.指南/)
- 配置 (/10.配置/)
- 开发 (/15.主题开发/)
- 功能页（归档页、清单页、登录页、分类页、标签页）

### 技术要求

- Node.js 18.0.0 及以上版本
- 需要熟悉 VitePress 基本使用和默认主题配置
- 建议使用 pnpm 作为包管理器

### 样式规范

- 使用 Sass 编写自定义样式
- 主题样式文件：`docs/.vitepress/theme/styles/`
- 全局样式文件：`docs/.vitepress/theme/index.css`

### 组件开发

- 自定义组件放在 `docs/.vitepress/theme/components/` 目录
- 使用 Vue 3 Composition API
- 支持插槽（slots）进行二次开发

## 主要功能

### Teek 主题特性

1. **知识管理形态**
   - 结构化：自动生成侧边栏、目录页、索引页
   - 碎片化：博客功能，快速构建知识碎片
   - 体系化：支持文档风和博客风切换

2. **首页功能**
   - Banner 功能（3种风格）
   - 文章列表（列表/卡片模式）
   - 博客卡片栏（博主信息、精选文章、分类、标签等）
   - 全屏壁纸模式
   - 页脚（社交图标、版权信息等）

3. **文章页功能**
   - 文章信息（面包屑、作者、时间、标签、分类等）
   - 评论区（支持 Giscus、Twikoo、Waline、Artalk）
   - 代码块 UI 升级
   - 文章页风格书页化
   - 文章打赏
   - 文章分享

4. **功能页**
   - 分类页
   - 标签页
   - 归档页
   - 清单页
   - 登录页
   - 风险链接提示页

5. **Markdown 拓展**
   - 居中、居右容器
   - 卡片容器
   - Demo 容器
   - TODO 列表
   - Video 容器

## 开发注意事项

1. **路径配置**
   - Sitemap 主机名需要替换为实际域名：`config.ts:58`
   - 社交链接需要更新为实际链接：`config.ts:94`

2. **图片资源**
   - 博客背景图放在 `docs/public/blog/` 目录
   - 登录页资源放在 `docs/public/login/` 目录
   - 二维码图片放在 `docs/public/qrcode/` 目录

3. **主题更新**
   定期更新 Teek 主题版本：
   ```powershell
   pnpm add vitepress-theme-teek@latest -D
   ```

4. **版本控制**
   - 项目使用 Git 进行版本控制
   - 当前分支：AD（所有文件处于删除状态）
   - 需要重新初始化或恢复 Git 仓库

## 相关资源

- VitePress 中文文档：https://vitepress.dev/zh/
- Teek 主题仓库：https://github.com/Kele-Bingtang/vitepress-theme-teek
- Teek 文档模板：https://github.com/Kele-Bingtang/vitepress-theme-teek-docs-template
- Teek 官方文档：https://vp.teek.top