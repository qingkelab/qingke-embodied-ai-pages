# qingke-embodied-ai-pages

青稞社区具身智能技术文章的**公开发布仓库**。这里只放已经定稿、可以公开的静态 HTML。

## 结构

```
index.html                    文章入口页
article/001/index.html        第一篇：具身智能这三年，到底变了什么？
article/002/index.html        第二篇：VLA 是怎么成为具身智能主线的？
article/002/images/           第二篇配图（PNG，用于正文引用）
article/003/                  预留
.github/workflows/pages.yml   GitHub Pages 部署
.nojekyll                     关闭 Jekyll，按原始静态文件发布
```

## 约定

- **本仓库不放研究材料。** 研究简报、证据矩阵、来源库、研究日志、稿件的 Markdown 与 SVG 源文件，一律保留在私有仓库，不进这里；**只有发布用的渲染产物（HTML 与 PNG 配图）进来**。
- **图片按文章就近存放**：新文章的配图放 `article/<三位序号>/images/`，正文引用本站绝对地址
  （`https://qingkelab.github.io/qingke-embodied-ai-pages/article/<序号>/images/<file>.png`）。
  历史图片仍指向 `https://qingkeai.online/upload/`。
- 每篇文章放在 `article/<三位序号>/index.html`，正文用自包含的内联样式，便于单独打开与后续迁移。
- 新增文章后在根 `index.html` 加一张卡片。

## 新增文章的同步流程

本仓库是**公开发布仓库**，只承载发布产物。私有研究仓库（`qingkelab/qingke-embodied-ai`）里
一篇文章进入 `release/<article-dir>/article-final.html` 之后，必须同步到本仓库：

1. 建立 `article/<三位序号>/index.html`，内容**直接取自**私有仓库的 `release/<article-dir>/article-final.html`，
   **不允许重新改写正文**（应为逐字节一致）。
2. 有发布图片时，图片放 `article/<三位序号>/images/`，正文中的图片 URL 写成
   `https://qingkelab.github.io/qingke-embodied-ai-pages/article/<序号>/images/<file>.png`。
3. 在根 `index.html` 增加该文章的入口卡片。
4. 走**独立 branch → PR → merge**，不直接 push `main`，不 force push。
5. 合并后验证：页面存在、与私有 release HTML 内容一致、首页有入口、图片路径可访问、
   Pages URL 可访问、上一篇文章未被改动。

**禁止同步**：`drafts`、`briefs`、`sources`、`fact-check`、`editorial-notes`、`issues`、
SVG 源文件及其他研究内部材料。本仓库只放 HTML、发布图片与必要的站点静态文件。

## 部署

推送到 `main` 即触发 `.github/workflows/pages.yml`，使用 GitHub 官方 Pages actions 发布整个仓库根目录。

- 站点地址：`https://qingkelab.github.io/qingke-embodied-ai-pages/`
- 第一篇：`https://qingkelab.github.io/qingke-embodied-ai-pages/article/001/`
