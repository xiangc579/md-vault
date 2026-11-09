# MD-Vault

<p align="center">
  <strong>为纯文本与 Markdown 极客而生的零依赖、本地优先密码管理看板，原生支持 2FA 动态口令计算与一键复制。</strong>
</p>

<p align="center">
  <a href="README.md">English</a> •
  <a href="README_ZH.md">简体中文</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/License-MIT-blue.svg" alt="License: MIT">
  <img src="https://img.shields.io/badge/Zero-Dependencies-success.svg" alt="Zero Dependencies">
  <img src="https://img.shields.io/badge/Architecture-Single--File%20HTML-orange.svg" alt="Single File HTML">
  <img src="https://img.shields.io/badge/Privacy-100%25%20Air--Gapped-red.svg" alt="100% Air-Gapped">
  <img src="https://img.shields.io/badge/Local--First-Plain--Text-purple.svg" alt="Local-First Plain-Text">
</p>

---

## 💡 产品哲学与设计理念

市面上绝大多数密码管理器都是臃肿、依赖中心化云端、基于订阅制收费的“黑盒”应用。你的核心资产被锁定在厂商私有的数据库格式中；一旦服务商宕机、涨价或修改条款，你将彻底陷入被动。

**MD-Vault 选择了另一条截然不同的极客道路：**

- **纯文本信仰（Plain-Text First）**：单一事实来源（Single Source of Truth）就是保存在你本地磁盘上的标准 `.md` 文件。无论何时何地，你都可以脱离任何前端工具，直接使用 VS Code、Obsidian、Typora、Vim 甚至命令行 `cat` / `grep` 查看、编辑和审计全部密码。
- **零供应商锁定（Zero Vendor Lock-in）**：没有私有加密格式绑架、无需数据库引擎、告别任何 SaaS 平台订阅费。
- **100% 物理气隙安全（Air-Gapped Ready）**：MD-Vault 全系统仅由一个独立的单文件 HTML 构成。**无需任何构建工具（Zero Build）、无需 `npm install`、无需 Node.js 后端**。所有 AST 解析与 TOTP 运算均在浏览器本地内存中瞬时完成，**全过程零外部网络请求**。

---

## ✨ 核心特性

### 1. 🔑 Markdown 原生 2FA 动态口令引擎
无需再频繁在密码文件和手机身份验证器之间切换！MD-Vault 在标准 Markdown 语法中优雅扩展了 ````totp` 代码块：

````markdown
- **2FA 动态口令**:
```totp
HXDMVJECJJWSRB3HWIZR4IFUGFTMXBOZ
```
````

- **在普通文本编辑器中**：它依然是一行清晰人类可读的 Base32 密钥字符串或 `otpauth://` URI。
- **在 MD-Vault 渲染器中**：它会自动激活为**实时 30 秒倒计时跳动的动态验证码组件**。采用等宽字体（Tabular Nums）防止秒数刷新抖动，小于 5 秒时智能变红预警；点击右侧复制按钮即可直接复制最新的 6 位验证码（自动剔除空格）。

### 2. 🗂️ AST 驱动的高密度紧凑卡片排版
原生 Markdown 在查看长列表或表格时往往需要无休止地垂直翻页，阅读效率极低。MD-Vault 利用 AST 语法树智能重组列表与代码块，生成规整优雅的**紧凑卡片网格**（`104px` 标签列 + 自适应内容列）。在常规桌面屏幕上一屏可并排容纳 4～6 个平台，字号清晰不缩小。

### 3. ⚡ 全要素即点即拷（Click-to-Copy）
- **单行密码与多行恢复码**：独立代码块承载，点击右侧图标一秒复制，提供优雅的勾选反馈。
- **动态验证码**：一键捕获当前有效窗口内的最新动态口令。
- **行内标识码**：点击账号、AccessKey ID、服务器 IP 等任意 `code` 标签文本即可直接复制。

### 4. 🔍 键盘优先与前端毫秒级检索
- 在页面任意位置按下 <kbd>/</kbd> 键，焦点瞬间激活至搜索框。
- 纯前端毫秒级快速过滤：支持对平台名、账号、分类标签的多维度检索。
- 左侧侧边栏根据 Markdown 的 `#` 和 `##` 自动生成动态树状大纲，随搜索实时折叠/展开。

### 5. 📂 极简多源数据导入
- **静默自动加载**：默认在启动时自动读取同目录下的 `PASSWORD_TEMPLATE.md`。
- **本地文件选择**：右上角提供文件选择按钮，支持随时在工作、私人、客户密码库之间自由切换。
- **桌面拖拽即读**：直接把桌面上的任意 `.md` 文件拖拽扔进浏览器窗口，瞬间完成解析与卡片重构。

---

## 🚀 快速上手

无需安装任何运行时环境，无 Docker 依赖，无构建过程。

### 方式一：本地直接双击打开（最简单）
1. 克隆或下载本仓库源码：
   ```bash
   git clone https://github.com/xiangc579/md-vault.git
   cd md-vault
   ```
2. 直接双击 `index.html`，在任意现代浏览器（Chrome、Firefox、Safari、Edge）中打开即可。
3. 把你的 `.md` 密码文件拖进页面尽享体验！

### 方式二：本地轻量 HTTP 托管（推荐，支持静默自动拉取）
受现代浏览器对本地 `file://` 协议的安全同源策略（CORS）限制，通过简易 HTTP 服务器托管可获得完整的自动读取体验：

```bash
# 使用 Python 3
python3 -m http.server 8080

# 或使用 Node.js
npx serve .
```
浏览器访问 `http://localhost:8080` 即可。

---

## 📝 Markdown 编写规范 (Schema)

MD-Vault 遵循层级明晰的文档规范：

```markdown
# 我的核心密码库

## GitHub (主账号)
- **平台网址**: https://github.com/login
- **登录账号**: `developer@example.com`
- **标签分类**: `#核心` `#开发`
- **登录密码**:
```text
K8#mP$9xL2@qW7!zR
```
- **2FA 动态口令**:
```totp
JBSWY3DPEHPK3PXP
```
- **备用恢复码**:
```text
3a1b-4c2d
9e8f-7g6h
```
- **备注说明**: 绑定了公司双币信用卡；SSH Key 位于 `~/.ssh/id_ed25519.pub`。

---

## 亚马逊云 AWS
### 生产机 Root
- **控制台地址**: https://signin.aws.amazon.com/console
- **账号 ID**: `123456789012`
- **登录密码**:
```text
Srv_Production_9921#Root
```

### 运维部署子账号
- **子账号名称**: `ops-deployer`
- **AccessKey ID**: `AKIAIOSFODNN7EXAMPLE`
```

### 标题与元素映射表

| 语法层级 | 语义定义 | MD-Vault 渲染器处理方式 |
| :--- | :--- | :--- |
| `# 标题`（第一行） | 密码金库总标题 | 渲染为页面顶部大标题与 `<title>` 网页标签 |
| `# 大类分类` | 业务/领域分组 | 渲染为左侧大纲分组标题与右侧区域小标签 |
| `## 平台名称` | 独立平台或应用 | 自动组装为独立的紧凑信息卡片（Card） |
| `### 角色/子账号` | 平台内部的多重身份 | 渲染为卡片内部的次级虚线分隔子标题 |
| `- **标签名**: 值` | 键值字段行 | 格式化为左侧固定 `104px` 标签 + 右侧内容自适应 |
| ````totp ... ```` | 2FA TOTP 密钥 | 实时 30 秒倒计时动态验证码组件 |
| ````text ... ```` | 敏感密码或恢复码 | 独立纯色背景密码盒，支持一键复制 |
| `` `行内代码` `` | 账号、IP、短标识 | 点击即自动复制的代码标签 |

已内置开箱即用的脱敏范例模板：
- [PASSWORD_TEMPLATE.md](PASSWORD_TEMPLATE.md) (英文标准版)
- [PASSWORD_TEMPLATE_ZH.md](PASSWORD_TEMPLATE_ZH.md) (中文标准版)

---

## 🔒 安全运维与最佳实践建议 (OpSec)

> [!IMPORTANT]
> MD-Vault 将密码以纯文本 Markdown 格式存储。虽然这赋予了你对数据的完全主权与零锁定，但在实际使用中建议遵循以下安全规范：

1. **务必使用私有仓库管理**：  
   如果使用 Git 托管密码本，**严禁推送到任何公共公共公开仓库（Public Repo）**！请使用 GitHub Private Repo 或自建的私有 Gitea / GitLab。
2. **配合透明加解密工作流（可选进阶）**：  
   对于极度敏感的环境，可搭配业界成熟的透明加解密方案：
   - **`git-crypt`**：在 Git commit 时自动加密为二进制，在本地 checkout 时自动解密为明文 Markdown。
   - **`age` / `gpg`**：静态归档时加密存储，查看前解密至临时文件或内存中：
     ```bash
     age -d -i ~/.ssh/id_ed25519 vault.md.age > vault.md
     ```
3. **物理气隙离线运行（Air-Gapped）**：  
   由于 `index.html` 不包含任何跨域网络请求，你可以将它拷贝至完全断网的离线保密笔记本或内网 NAS 共享中放心运行。

---

## 🛠️ 技术规格与设计规范

- **核心架构**：原生 HTML5 + 现代化 CSS3（Flex/Grid）+ 原生 ES2022。
- **字体排印**：正文使用 `Mulish`（中文回退 `PingFang SC`）；敏感密钥使用 `JetBrains Mono`（启用 `tabular-nums` 等宽数字排版）。
- **AST 解析**：基于 `markdown-it` 语法树，重载 Fence 规则实现卡片重组。
- **TOTP 算法**：纯前端实现的 RFC 6238 规范算法引擎。
- **零构建（Zero Build）**：不依赖任何打包工具，打开即用。

完整的设计哲学与配色 Token 规范可参阅 [DESIGN.md](DESIGN.md)。

---

## 🗺️ 后续路线图 (Roadmap)

- [x] AST 语法树智能卡片重组
- [x] 原生 2FA 动态口令 30 秒倒计时与一键复制
- [x] 全键盘搜索交互（快捷键 `/`）
- [x] 桌面文件拖拽即读
- [x] 中英文双语标准脱敏模板
- [ ] 可选的前端 AES-GCM 客户端访问主密码保护层
- [ ] Obsidian 社区插件封装
- [ ] Raycast 快速凭证检索扩展

---

## 📄 开源许可证

本项目基于 [MIT License](LICENSE) 开源协议分发，允许任何形式的个人与商业二次修改及自由使用。
