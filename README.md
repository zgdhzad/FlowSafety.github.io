# FlowSafety 网站（site）

此目录包含可直接部署的静态站点文件（HTML/CSS/图片）。

## 本地预览

在项目根或进入 `site` 目录后，可使用轻量 HTTP 服务器预览：

```bash
cd site
python3 -m http.server 8000
# 然后在浏览器打开 http://localhost:8000
```

## GitHub Pages（自动化）

仓库已包含 GitHub Actions 工作流：`.github/workflows/deploy_site.yml`。
当你将代码推送到 `main` 分支时，工作流会把 `site/` 目录的内容发布到 `gh-pages` 分支，从而启用 GitHub Pages。

如果你希望使用仓库设置直接选择 Pages 源：
- 在 GitHub 仓库 Settings → Pages 中选择 `gh-pages` 分支作为发布来源。

如需自定义域名，请在仓库设置中配置 Pages 或将 `CNAME` 文件放入 `site/` 目录并提交。

## Netlify 部署

已包含 `netlify.toml`（位于此目录），可直接将此仓库连接到 Netlify：

- 在 Netlify 仪表盘中选择“New site from Git” → 连接你的仓库
- 构建命令：留空（或填入你的构建命令，如果有）
- 发布目录（Publish directory）：`site`

或可直接将 `site/` 目录 Drag & Drop 到 Netlify 的 Sites 页面完成部署。

## 关于 `.nojekyll`

本目录包含 `.nojekyll` 文件，用于防止 GitHub Pages/Netlify 使用 Jekyll 处理，从而保留下划线文件名与原始结构。

## 重要文件

- `netlify.toml`：Netlify 配置，指定发布目录
- `.nojekyll`：禁用 Jekyll 处理
- `.github/workflows/deploy_site.yml`：GitHub Actions 自动部署工作流（位于仓库根）

需要我帮你执行 `git commit` 与 `git push` 吗？如果需要，请确认远程分支（默认 `main`）。
