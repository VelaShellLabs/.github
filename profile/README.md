<div align="center">

<img src="https://joesdu.github.io/VelaShell/assets/velashell.png" width="96" alt="VelaShell">

# VelaShell

**以终端为帆,驶向远方主机** · /ˈveɪlə ʃɛl/

[官网](https://joesdu.github.io/VelaShell/) ·
[主程序](https://github.com/joesdu/VelaShell) ·
[文档](https://github.com/VelaShellLabs/velashell-docs) ·
[插件商店](https://market.easilynet.top)

</div>

---

## 中文

VelaShell 是一款为运维与开发者打造的**现代化跨平台 SSH / SFTP / FTP 终端客户端**,
用 .NET 11 与 Avalonia 构建,支持 Windows、Linux 与 macOS(x64 / arm64)。
内置自研 VT 终端引擎、跳板机(ProxyJump)与网络代理、端口转发隧道、
自研 VelaDock 可拖拽分屏、资源监视与路由追踪,还带一套**双模插件系统**
(进程内 / 独立进程)与第一方 AI 助手插件。会话数据经嵌入式 SonnetDB 加密持久化。

本组织放的是**插件生态与文档**;主程序在 [joesdu/VelaShell](https://github.com/joesdu/VelaShell)。

### 仓库导航

| 仓库 | 内容 |
| --- | --- |
| [velashell-docs](https://github.com/VelaShellLabs/velashell-docs) | **全部文档**:宿主设计、插件系统蓝图、SDK / CLI / 模板手册([中文](https://github.com/VelaShellLabs/velashell-docs/tree/main/zh) · [English](https://github.com/VelaShellLabs/velashell-docs/tree/main/en)) |
| [velashell-plugin-sdk](https://github.com/VelaShellLabs/velashell-plugin-sdk) | 插件契约 SDK:`VelaShell.PluginSdk`、`.Testing` |
| [velashell-plugin-cli](https://github.com/VelaShellLabs/velashell-plugin-cli) | `vela-plugin` 命令行与 `VelaShell.PluginSdk.Build` |
| [velashell-plugin-templates](https://github.com/VelaShellLabs/velashell-plugin-templates) | `dotnet new velaplugin` 模板 |
| [velashell-plugins](https://github.com/VelaShellLabs/velashell-plugins) | 第一方插件:Redis / S3 / Telnet / 串口 |
| [velashell-markets](https://github.com/VelaShellLabs/velashell-markets) | 插件商店:上传、审核、检索与分发 |
| [VelaShell.Plugin.DockerPanel](https://github.com/VelaShellLabs/VelaShell.Plugin.DockerPanel) | Docker / Compose 管理面板插件 |

### 写一个插件

```bash
dotnet new install VelaShell.Plugin.Templates
dotnet new velaplugin-ui -n MyPlugin --publisher acme
dotnet build -t:PackVpx            # 出 bin/vpx/*.vpx
```

生成的工程只引用一个 NuGet 包,契约程序集、与宿主版本一致的 Avalonia、清单校验与打包器
都随它到位。从这里开始读:[开发指南](https://github.com/VelaShellLabs/velashell-docs/blob/main/zh/templates/dev-guide.md) →
[CLI 手册](https://github.com/VelaShellLabs/velashell-docs/blob/main/zh/cli/cli.md) →
[打包与发布](https://github.com/VelaShellLabs/velashell-docs/blob/main/zh/templates/publishing.md)。

### 许可与联系

主程序与插件生态为 **AGPL-3.0 / 商业双许可**。
商业授权咨询、安全漏洞报告:<dygood@outlook.com>
(安全问题请**不要**开公开 Issue,按各仓库 `SECURITY.md` 的流程私下报告)。

> 项目仍在活跃开发中,功能与界面可能在版本之间变动。

---

## English

VelaShell is a **modern cross-platform SSH / SFTP / FTP terminal client** for ops and
developers, built on .NET 11 and Avalonia for Windows, Linux and macOS (x64 / arm64).
It ships an in-house VT terminal engine, jump hosts (ProxyJump) and network proxies,
port-forwarding tunnels, the in-house VelaDock drag-and-drop split-pane workspace,
resource monitoring and traceroute — plus a **dual-mode plugin system** (in-process or
isolated process) and a first-party AI assistant plugin. Session data is persisted
encrypted in the embedded SonnetDB.

This organisation hosts the **plugin ecosystem and documentation**; the application
itself lives at [joesdu/VelaShell](https://github.com/joesdu/VelaShell).

### Repositories

| Repository | Contents |
| --- | --- |
| [velashell-docs](https://github.com/VelaShellLabs/velashell-docs) | **All documentation**: host design, plugin blueprint, SDK / CLI / template manuals ([English](https://github.com/VelaShellLabs/velashell-docs/tree/main/en) · [中文](https://github.com/VelaShellLabs/velashell-docs/tree/main/zh)) |
| [velashell-plugin-sdk](https://github.com/VelaShellLabs/velashell-plugin-sdk) | The plugin contract SDK: `VelaShell.PluginSdk`, `.Testing` |
| [velashell-plugin-cli](https://github.com/VelaShellLabs/velashell-plugin-cli) | The `vela-plugin` CLI and `VelaShell.PluginSdk.Build` |
| [velashell-plugin-templates](https://github.com/VelaShellLabs/velashell-plugin-templates) | The `dotnet new velaplugin` templates |
| [velashell-plugins](https://github.com/VelaShellLabs/velashell-plugins) | First-party plugins: Redis / S3 / Telnet / serial |
| [velashell-markets](https://github.com/VelaShellLabs/velashell-markets) | The plugin marketplace: upload, review, search, distribution |
| [VelaShell.Plugin.DockerPanel](https://github.com/VelaShellLabs/VelaShell.Plugin.DockerPanel) | A Docker / Compose management panel plugin |

### Write a plugin

```bash
dotnet new install VelaShell.Plugin.Templates
dotnet new velaplugin-ui -n MyPlugin --publisher acme
dotnet build -t:PackVpx            # produces bin/vpx/*.vpx
```

The generated project references a single NuGet package — the contract assembly, a
host-matched Avalonia, manifest validation and the packer all come with it. Start here:
[dev guide](https://github.com/VelaShellLabs/velashell-docs/blob/main/en/templates/dev-guide.md) →
[CLI manual](https://github.com/VelaShellLabs/velashell-docs/blob/main/en/cli/cli.md) →
[publishing](https://github.com/VelaShellLabs/velashell-docs/blob/main/en/templates/publishing.md).

### Licence and contact

The application and the plugin ecosystem are **dual-licensed AGPL-3.0 / commercial**.
Commercial licensing and security reports: <dygood@outlook.com>
(please do **not** open a public issue for security problems — follow the `SECURITY.md`
process in the relevant repository).

> Under active development; features and UI may change between releases.
