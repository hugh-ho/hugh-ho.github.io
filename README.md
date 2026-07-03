# Jekyll 博客

这是我的个人博客，使用 Jekyll 构建，托管在 GitHub Pages 上。

## 目录结构

```
.
├── _config.yml          # 站点配置文件
├── _includes/           # 包含文件（头部、页脚等）
├── _layouts/            # 布局模板
├── _posts/              # 博客文章
├── _sass/               # Sass 样式（可选）
├── assets/              # 静态资源
├── Gemfile              # Ruby 依赖
├── index.md             # 首页
└── about.md             # 关于页面
```

## 本地开发

### 安装依赖

```bash
bundle install
```

### 本地预览

```bash
bundle exec jekyll serve
```

访问 http://localhost:4000

### 实时重载

```bash
bundle exec jekyll serve --livereload
```

## 写作

### 创建新文章

在 `_posts` 目录下创建文件，文件名格式：`YYYY-MM-DD-title.md`

```markdown
---
layout: post
title: "文章标题"
date: 2026-07-03 22:30:00 +0800
categories: 分类
tags: [标签1, 标签2]
---

文章内容...
```

## 部署

推送到 GitHub 后，GitHub Pages 会自动构建和部署。

```bash
git add .
git commit -m "更新博客"
git push origin main
```

## 配置

编辑 `_config.yml` 修改：
- 网站标题和描述
- 社交媒体链接
- 分页设置
- 插件配置

## 主题

当前使用 `minima` 主题（Jekyll 默认）。可在 `_config.yml` 中修改为其他 GitHub Pages 支持的主题：

- `minima` - 默认主题
- `jekyll-theme-cayman`
- `jekyll-theme-slate`
- 更多主题：https://pages.github.com/themes/

## 功能

- ✅ Markdown 写作
- ✅ 代码高亮
- ✅ RSS 订阅
- ✅ SEO 优化
- ✅ 响应式设计

## 参考

- [Jekyll 官方文档](https://jekyllrb.com/docs/)
- [GitHub Pages](https://pages.github.com/)
- [Markdown 语法](https://www.markdownguide.org/)
