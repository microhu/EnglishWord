# 单词记忆应用部署说明（网页版）

目标：发布到一个固定网址，平板可直接访问；你每次改代码后重新发布，平板端自动同步最新版本。

## 推荐方案：Vercel（最省事）

### 一次性初始化
1. 把当前目录推到 GitHub 仓库（例如 `english-word-app`）。
2. 打开 Vercel 后台并选择 `Add New Project`。
3. 选择该 GitHub 仓库导入。
4. Framework 选择 `Other`（静态站点）。
5. 不需要额外构建命令，直接 `Deploy`。

### 日常更新（后续每次改 bug）
1. 本地改完文件后，提交并 push 到 GitHub。
2. Vercel 会自动触发新部署。
3. 平板刷新页面即可拿到最新版本。

## 备选方案：Cloudflare Pages
1. Cloudflare Pages 连接 GitHub 仓库并导入。
2. 构建类型选静态站点（无需构建命令）。
3. 每次 push 后自动部署。

## 已做的同步优化
- `vercel.json`：关闭 `index.html` 缓存，避免平板拿旧页面。
- `_headers`：为支持该规则的平台设置 `no-cache` 响应头。

## 给平板使用建议
1. 用浏览器打开部署后的网址。
2. 加到主屏幕（像 App 一样打开）。
3. 若偶发旧缓存，刷新一次即可。
