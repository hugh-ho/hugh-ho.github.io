# 博客维护约束

## 项目信息

- **名称**: 时间的朋友
- **副标题**: 时间看得见，知识会沉淀
- **技术栈**: Jekyll + GitHub Pages
- **主题**: minima
- **URL**: https://hugh-ho.github.io

## 目录结构

```
.
├── _config.yml          # 站点配置（一般不动）
├── _category/           # 分类定义文件
│   └── 随笔.md
├── _layouts/            # 布局模板
│   ├── category.html    # 分类页面布局
│   ├── home.html        # 首页布局
│   └── post.html        # 文章布局
├── _posts/              # 博客文章
├── categories.md        # 分类列表页
├── about.md             # 关于页面
├── index.md             # 首页
├── Gemfile              # 依赖
└── README.md
```

## 核心约束

### 1. 用户操作范围
- 用户只会在 `_posts/` 目录新增文章
- 文章可能使用新的 `categories`

### 2. Agent 自动处理（重要）

当用户新增带有**新分类**的文章时，**必须**自动执行以下操作：

#### 2.1 创建分类定义文件

在 `_category/` 目录下创建 `{分类名}.md`：

```markdown
---
layout: category
category: 分类名
permalink: /categories/分类名/
---
```

**示例**：如果文章有 `categories: 技术`，则创建 `_category/技术.md`

#### 2.2 文件名处理规则
- 直接使用分类名作为文件名（如 `技术.md`、`学习笔记.md`）
- 保持原有中文名称，不要转拼音
- 如果有多个分类，为每个新分类创建文件

### 3. 禁止操作

**不要**修改以下文件，除非用户明确要求：
- `_config.yml`
- `_layouts/` 下的布局文件
- `categories.md`
- `about.md`
- `index.md`
- `Gemfile`

### 4. 文章格式检查

确保新增文章包含正确的 front matter：

```yaml
---
layout: post
title: "文章标题"
date: YYYY-MM-DD HH:MM:SS +0800
categories: 分类名
tags: [标签1, 标签2]  # 可选
---
```

### 5. 工作流程

```
用户要求新增文章
    ↓
1. 创建文章文件 _posts/YYYY-MM-DD-title.md
    ↓
2. 检查文章中的 categories
    ↓
3. 对于每个新分类：
   - 检查 _category/ 目录是否已存在该分类文件
   - 如果不存在，创建 _category/{分类名}.md
    ↓
4. git add + commit + push
```

## 示例场景

### 场景1：新增文章使用现有分类
- 文章: `categories: 随笔`
- 操作: 只需创建文章，无需其他操作（因为 `_category/随笔.md` 已存在）

### 场景2：新增文章使用新分类
- 文章: `categories: 技术`
- 操作:
  1. 创建文章 `_posts/2026-07-04-xxx.md`
  2. 创建 `_category/技术.md`
  3. 提交并推送

### 场景3：新增文章使用多个新分类
- 文章: `categories: [技术, 学习笔记]`
- 操作:
  1. 创建文章
  2. 创建 `_category/技术.md`
  3. 创建 `_category/学习笔记.md`
  4. 提交并推送

## 配置信息（参考）

- email: maidongcao.up@gmail.com
- twitter_username: maidongcao
- github_username: hugh-ho
- theme: minima

---

**注意**: 每次处理用户请求前，先阅读此文件了解约束。
