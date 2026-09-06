# 盘一盘

> 盘市场，也盘自己。

**盘一盘**是面向 A 股主动交易者的个人研究与复盘工具。

这个仓库只承担盘一盘 Obsidian 插件的公开分发，不是业务源码仓库。

## 普通 Test 用户

首次安装使用测试邀请或当前下载入口提供的 **盘一盘 Test 安装包**。完成首次安装后，后续版本优先直接在盘一盘中处理：

**盘一盘 → 工具箱 → 版本与更新 → 更新到新版本**

内置 Test 更新通道通过盘一盘 Test 服务检查和下载经过完整性校验的三文件更新，不要求用户登录 GitHub，也不要求配置 GitHub Token 或安装 BRAT。

如果更新服务暂时不可用，当前已安装版本仍可继续使用；稍后重新检查即可。

## BRAT：高级测试与备用方式

BRAT 继续保留给开发者、高级测试者和故障排查使用，但不再是普通 Test 用户的必需依赖。

安装 BRAT 后可以添加：

```text
Gandalf-z/panyipan-plugin-release
```

也可以尝试：

[在 Obsidian 中打开 BRAT](obsidian://show-plugin?id=obsidian42-brat)

[通过 BRAT 添加盘一盘](obsidian://brat?plugin=Gandalf-z/panyipan-plugin-release)

> BRAT 界面的 “Beta plugin” 是第三方工具自己的功能名称，不代表盘一盘的产品状态。

## Release 与 Test 更新通道

每个 Test Release 只发布：

- `main.js`
- `manifest.json`
- `styles.css`
- 一个仅用于故障备用的 ZIP

根目录的 `latest-test.json` 是机器读取的 Test 通道指针，只包含当前版本、上游源码 commit、三文件大小与 SHA-256，不包含插件源码、用户数据或凭据。盘一盘 Backend 会验证并缓存这些发行资产，再向普通 Test 客户端提供更新；客户端不直接依赖 GitHub API 配额。

## 手动恢复

手动覆盖仅作为故障备用方式。需要人工恢复时，只替换插件目录中的：

```text
main.js
manifest.json
styles.css
```

不要通过删除整个插件目录来处理普通版本升级。

## 隐私与安全

本仓库不保存个人交易资料、复盘账本、本地工作区数据，也不包含服务端凭据、授权私钥或运维 Secret。

---

**盘一盘 · 盘市场，也盘自己**
