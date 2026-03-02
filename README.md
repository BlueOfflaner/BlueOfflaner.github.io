# Hexo 个人博客

这个仓库是一个基于 Hexo 搭建的个人博客，主题为 Butterfly，使用 GitHub Actions 自动部署到 GitHub Pages。

## 本地开发

```bash
npm install
npm run server
```

本地预览地址：`http://localhost:4000`。

## 构建静态文件

```bash
npm run build
```

构建结果会输出到 `public/` 目录。

## GitHub Pages 部署

1. 确认 `_config.yml` 配置正确：
   - `url: https://blueofflaner.github.io`
   - `root: /`
2. 推送到 `main` 分支。
3. 在 GitHub 仓库设置中将 Pages 的 Source 设置为 `GitHub Actions`。

工作流文件位于 `.github/workflows/deploy-pages.yml`。

## 文章与图片规范

本项目已启用 `post_asset_folder: true`，每篇文章可使用独立资源目录管理图片。

### 新建文章

```bash
npx hexo new post "my-post-title"
```

会生成：

- `source/_posts/my-post-title.md`
- `source/_posts/my-post-title/`（文章资源目录）

### 图片存放规则

1. 图片只放在文章同名资源目录下：
   - `source/_posts/my-post-title/`
2. 文件名统一使用小写 kebab-case：
   - `cover.webp`
   - `architecture-diagram.webp`
   - `result-v1.png`
3. Markdown 中使用相对路径引用图片：
   - `![封面](./cover.webp)`
4. 每篇文章只保留一张封面图，文件名固定为 `cover.webp`。

### 图片格式与尺寸规则

1. 截图或照片优先使用 `webp`。
2. 仅在需要透明背景或高精度线条图时使用 `png`。
3. 建议最大宽度：
   - 封面图：`1600px`
   - 文内图片：`1200px`
4. 建议目标体积：
   - 封面图：`<= 300 KB`
   - 文内图片：`<= 200 KB`

### 发布前检查清单

1. 运行 `npm run server`，确认所有图片能正常加载。
2. 运行 `npm run build`，确认没有图片链接失效。
3. 提交时将 Markdown 文件和对应图片资源一起提交。
