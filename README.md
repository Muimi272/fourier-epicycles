# 离散傅里叶外轮环画板

单文件静态站点：在画布上涂鸦，用离散傅里叶变换把轨迹还原成外轮环动画。

## 本地预览

用浏览器打开 `public/index.html`，无需构建。

## Cloudflare Pages

仓库已按 Pages 静态站点整理：入口是 `public/index.html`，无需安装依赖、无需构建命令。

### 控制台连接 GitHub

1. 打开 [Cloudflare Dashboard](https://dash.cloudflare.com/) → **Workers & Pages** → **Create** → **Pages** → **Connect to Git**。
2. 选择仓库 `Muimi272/fourier-epicycles`，分支 `main`。
3. 构建设置：
   - **Framework preset**：`None`
   - **Build command**：留空
   - **Build output directory**：`public`
   - **Root directory**：留空（仓库根目录）
4. 保存并部署。之后推送到 `main` 会自动发布。

自定义域名在该 Pages 项目的 **Custom domains** 里添加即可。

### 命令行（可选）

已登录 Wrangler 时，在仓库根目录执行：

```bash
npx wrangler pages deploy public --project-name fourier-epicycles
```

`wrangler.toml` 里的 `pages_build_output_dir = "public"` 与上述输出目录一致。
