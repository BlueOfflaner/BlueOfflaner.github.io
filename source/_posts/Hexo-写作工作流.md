---
title: Hexo 写作工作流
date: 2026-03-03 00:41:07
categories:
  - 技术
tags:
  - Hexo
  - 写作
  - 效率
description: 从写作、预览到发布的完整 Hexo 日常工作流。
---

这篇文章记录我目前的博客更新流程，尽量做到低摩擦发布。

## 1. 写作

```bash
npx hexo new post "文章标题"
```

在 `source/_posts/` 中完成内容，优先保证结构清晰和可读性。

## 2. 本地预览

```bash
npx hexo server
```

预览时重点检查:

- 标题层级是否合理
- 代码块高亮是否正确
- 移动端排版是否正常

## 3. 生成与发布

```bash
npx hexo clean && npx hexo generate
```

提交到 GitHub 后由 Actions 自动部署到 GitHub Pages，实现稳定的持续发布。
