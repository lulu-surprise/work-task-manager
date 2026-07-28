# 工作任务管理器

一个支持多用户的任务、日历和笔记管理工具。前端托管于 GitHub Pages，用户认证和数据存储使用 Supabase。

## 首次配置

1. 在 Supabase 创建项目。
2. 打开 SQL Editor，执行 `supabase-schema.sql`。
3. 打开 Project Settings → API，把 Project URL 和 anon/public key 填入 `supabase-config.js`。
4. Authentication → URL Configuration 中添加 GitHub Pages 地址作为 Site URL 和 Redirect URL。
5. 如需手机号注册，在 Authentication → Sign In / Providers → Phone 中配置短信服务商（如 Twilio），启用 Phone 和 phone confirmations。
6. 将代码推送到 GitHub 的 `main` 分支。
7. GitHub 仓库 Settings → Pages → Source 选择 GitHub Actions。

## 本地使用

直接打开 `index.html`。未配置 Supabase 时，登录页会提示云端服务尚未配置。

## 数据安全

- 浏览器中只使用 Supabase anon/public key，这是公开客户端配置。
- 不要把 `service_role` key、数据库密码或 GitHub Token 写入仓库。
- `user_data` 已启用 Row Level Security，每个登录用户只能读取和修改自己的数据。

## 日常更新

修改 `index.html` 后提交并推送到 `main` 分支，GitHub Actions 会自动重新部署。
