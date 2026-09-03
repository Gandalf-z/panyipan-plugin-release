# 安全说明

`panyipan-plugin-release` 是公开分发仓库。

## 请不要公开提交

如需反馈问题，请不要在 Issue、PR、截图或日志中公开：

- API Key、Token、Cookie、授权码、邀请码；
- Cloudflare / GitHub / DeepSeek 等账号凭据；
- 证券账号、手机号、身份证号等个人信息；
- 完整持仓、成交、复盘账本等你不希望公开的交易资料；
- 本机绝对路径中包含的个人目录信息。

## 发行安全边界

正式发布给测试用户的 GitHub Release 只允许包含：

- `main.js`
- `manifest.json`
- `styles.css`
- 由上述三文件重新封装的故障备用 ZIP

发行工作流必须从上游源码重新构建并执行安全检查，不从用户 Vault、本机数据目录或 Test Backend 数据目录取文件。
