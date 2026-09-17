# qingke-embodied-ai-pages

青稞社区具身智能技术文章的**公开发布仓库**。这里只放已经定稿、可以公开的静态 HTML。

## 结构

```
index.html                    文章入口页
article/001/index.html        第一篇：具身智能这三年，到底变了什么？
article/002/                  预留
article/003/                  预留
.github/workflows/pages.yml   GitHub Pages 部署
.nojekyll                     关闭 Jekyll，按原始静态文件发布
```

## 约定

- **本仓库不放研究材料。** 研究简报、证据矩阵、来源库、研究日志、稿件的 Markdown 与 SVG 源文件，一律保留在私有仓库，不进这里。
- **图片走公开地址**，不复制私有仓库里的源文件。当前使用 `https://qingkeai.online/upload/`。
- 每篇文章放在 `article/<三位序号>/index.html`，正文用自包含的内联样式，便于单独打开与后续迁移。
- 新增文章后在根 `index.html` 加一张卡片。

## 部署

推送到 `main` 即触发 `.github/workflows/pages.yml`，使用 GitHub 官方 Pages actions 发布整个仓库根目录。

- 站点地址：`https://qingkelab.github.io/qingke-embodied-ai-pages/`
- 第一篇：`https://qingkelab.github.io/qingke-embodied-ai-pages/article/001/`
