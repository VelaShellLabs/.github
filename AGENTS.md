# AGENTS.md

> 给 AI 代理与新加入者的操作约定。**动手之前先读完本文件,以及它指向的文档。**

## 一、开工前必读:velashell-docs

VelaShell 生态的**全部文档**集中在一个仓库:
**[VelaShellLabs/velashell-docs](https://github.com/VelaShellLabs/velashell-docs)**。
本仓库**不放** `docs/`、`docs-en/` —— 设计手册、开发规范与开发文档都在那边。

**在动任何代码之前**,先把下表中与你要改的部分相关的几篇读掉。跳过这一步直接改,
结果通常是两种:与既有设计冲突,或者重复实现一个已经存在的能力。

| 位置 | 内容 |
| --- | --- |
| [`zh/host/`](https://github.com/VelaShellLabs/velashell-docs/tree/main/zh/host) | 宿主分层架构与依赖方向、工程化重构蓝图、交互与界面规格、快捷键参考、设置项审计,以及 SFTP / FTP / Telnet / 串口 / Redis / S3 / 系统密钥链等可行性调研 |
| [`zh/plugins/`](https://github.com/VelaShellLabs/velashell-docs/tree/main/zh/plugins) | 插件系统设计蓝图 01–15(进程模型、IPC 协议、权限系统、UI 扩展、威胁模型、路线图)与[进度总览 STATUS](https://github.com/VelaShellLabs/velashell-docs/blob/main/zh/plugins/STATUS.md) |
| [`zh/sdk/`](https://github.com/VelaShellLabs/velashell-docs/tree/main/zh/sdk) | 插件契约 SDK 参考、SDK 仓库的发版流程 |
| [`zh/cli/`](https://github.com/VelaShellLabs/velashell-docs/tree/main/zh/cli) | `vela-plugin` 命令行手册、CLI 仓库的发版流程 |
| [`zh/templates/`](https://github.com/VelaShellLabs/velashell-docs/tree/main/zh/templates) | 插件开发指南、打包与发布、模板仓库的发版流程 |

英文镜像在 [`en/`](https://github.com/VelaShellLabs/velashell-docs/tree/main/en),与 `zh/` 同构。
[仓库首页](https://github.com/VelaShellLabs/velashell-docs)有按「我想做什么」组织的快速入口表。

## 二、涉及文档的改动一律同步到 velashell-docs

**这是本文件最重要的一条。**

- 本仓库里**不新建** `docs/`、`docs-en/` 或任何成体系的文档目录。要写文档,去 velashell-docs 开 PR。
- 改了代码,而**行为、接口、配置项、命令行、构建流程或版本纪律**与现有文档对不上时,
  必须**同时**在 velashell-docs 提一个 PR 把文档改过来。两个 PR 在正文里互相引用,一起合。
  只改代码不改文档,等于让文档开始骗人 —— 而文档是别人照抄的。
- velashell-docs 的 `zh/` 与 `en/` 是**互为镜像**的两棵树,文件一一对应。改了中文就要改英文,
  反之亦然。漏一边,两棵树就开始漂。
- velashell-docs 内部的互相引用**一律走相对路径**(如 `../templates/dev-guide.md`),
  不要写回 GitHub 绝对 URL —— 文档集中到一个仓库,消掉的正是那种一改路径就断的跨仓库链接。
- **例外**:留在代码仓库里的少数几份文件不适用上述规则,因为它们服务的是「在这个仓库里写代码」
  这件事,搬走只会离使用场景更远。各仓库的例外清单见下面第三节。

## 三、本仓库:.github(组织资料)

VelaShellLabs 的组织资料仓库。**不放代码。**

`profile/README.md` 由 GitHub 渲染在组织主页 <https://github.com/VelaShellLabs> 上 ——
这是组织页放介绍的唯一机制。改介绍就改它,推上来即生效。

### 改它的时候注意

- 中英双语同页(组织页不支持语言切换),**改一边要改另一边**,两份内容保持对应。
- 里面的仓库导航表要与组织下的实际仓库一致:新增或归档仓库时同步这张表。
- 事实(定位、平台、许可、渠道)以各仓库 README 与
  [velashell-docs](https://github.com/VelaShellLabs/velashell-docs) 为准,不要在这里另立一套说法。
- 组织页比单个仓库的 README 更容易被当成对外承诺,**保留「仍在活跃开发中」这类限定语**,
  不要把话说满。

若日后加 `.github/FUNDING.yml`,它会成为**全组织仓库的 Sponsor 按钮默认值**
(各仓库自带的同名文件优先)。

### 留在本仓库的文档

`README.md`(说明本仓库是干什么的)、`profile/README.md`(组织主页内容)。
