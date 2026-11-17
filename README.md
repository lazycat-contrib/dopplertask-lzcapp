# DopplerTask 懒猫微服打包（LPK）

[DopplerTask](https://github.com/dopplertask/dopplertask)（MIT）的懒猫微服 LPK 打包仓库。DopplerTask 是面向 AI 智能体的开源自动化控制层：智能体从 81 个现成步骤（Slack、Jira、Stripe、Claude 等）起草工作流，人工审批每次变更，每次运行都有记录，支持 MCP。

本仓库为**镜像模式**打包：直接复用上游官方镜像 `docker.io/dopplertask/dopplertask`，由 GitHub Actions（[ca-x/lazycat-github-action](https://github.com/ca-x/lazycat-github-action)）每日跟随上游 stable tag（`X.Y.Z`）自动复制镜像并发布到喵喵商店。不存储上游源码。

## 首次使用

1. 打开应用，在提示处输入**访问口令**（Person Token，见安装时的部署参数说明，由平台稳定密钥生成）。应用已设为管理员入口（admin_only）。
2. 让 AI 智能体接入：把 MCP 地址 `https://<应用域名>/mcp` 与访问口令填进智能体配置，智能体起草的工作流会在编辑器里等你审批。
3. 数据（H2 数据库、加密密钥）持久化在应用数据目录 `/lzcapp/var/data`；凭据加密密钥由平台稳定生成，迁移微服时需同步迁移。

## 说明

- `min_os_version: 1.5.0`（LPK v2）
- 图标来自上游 `docs/images/dopplertask_logo.png`，缩放为 512x512
- 请勿在应用内自更新，版本跟随由 CI 维护
