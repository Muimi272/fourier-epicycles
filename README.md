# 离散傅里叶外轮环画板

单文件静态站点：在画布上涂鸦，用离散傅里叶变换把轨迹还原成外轮环动画。

## 本地预览

用浏览器打开 `public/index.html`，无需构建。

## Cloudflare 部署

静态资源在 `public/`，**没有构建步骤**。

### 若控制台里有 Deploy command（Workers / 新版界面）

日志里如果出现 `Executing user deploy command: npx wrangler deploy`，保持：

- **Deploy command**：`npx wrangler deploy`
- 不要留空，也不要改成 `wrangler pages deploy`

仓库里的 `wrangler.toml` 已声明 `[assets].directory = "./public"`，这条命令会直接上传静态文件。

### 若是经典 Pages（Build command + Output directory）

- **Framework preset**：`None`
- **Build command**：留空（不要填 `npx wrangler deploy`）
- **Build output directory**：`public`

`npx wrangler deploy` 是 Workers 部署命令。在经典 Pages 项目上跑它会报 *Missing entry-point to Worker script*。

自定义域名在项目的 **Custom domains** 里添加。
