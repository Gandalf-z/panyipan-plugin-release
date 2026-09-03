# AGENTS.md

本文件作用于整个 `panyipan-plugin-release` 仓库。

## 仓库角色

这里是 **盘一盘 Obsidian 插件的公开分发面**，不是开发源码仓库。

它只负责：

- GitHub Releases；
- BRAT 安装与更新；
- 最小安装说明；
- 与发行相关的自动化和安全门禁。

盘一盘业务源码、Backend、测试、架构与产品实现的事实源在上游源码仓库；不要在本仓库复制或重新实现。

## 强制边界

1. 不提交 Backend、开发脚本、测试夹具、用户账本、市场数据、日志或本机运行状态。
2. 不提交 DeepSeek Key、Cloudflare 凭据、GitHub Token、授权 Secret、邀请码或任何真实凭据。
3. `main.js`、`manifest.json`、`styles.css` 只作为 GitHub Release 资产发布；默认分支不长期保存构建产物。
4. Test 发行必须由发行工作流从上游源码构建，不允许手工修改构建后的 `main.js`。
5. 当前工程环境名称是 `dev / test / prod`；不要重新引入“Beta / 内测”作为盘一盘产品状态。BRAT 自身界面的 “Beta plugin” 只是第三方工具名称。
6. Test Release 必须锁定 Test Endpoint；不得把 Prod Endpoint 或本机 Endpoint 错发给测试用户。
7. Release tag、Release name 与 Release 内 `manifest.json.version` 必须一致，并使用 SemVer。
8. 发布前必须通过三文件白名单、Secret / 本机路径扫描、JavaScript 语法检查与 Endpoint 检查。

## Git 与文档

- 有实质变更时使用主题分支和 PR；不要把维护规则散落成第二套文档体系。
- Git history / PR 记录“过去发生了什么”；README 与本文件只维护“现在真实是什么”。
- 不额外维护手工 commit log / changelog，除非未来仓库明确建立唯一权威的版本日志机制。

## 发布原则

正常 Test 发布由 `.github/workflows/publish-test-plugin.yml` 完成。

跨仓库凭据只允许存在于 GitHub Actions Secret 中；工作流必须使用最小权限，并且不得把凭据、上游私有文件或完整源码打印到日志。
