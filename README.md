# MD-Vault

<p align="center">
  <strong>A zero-dependency, local-first password dashboard built for Markdown lovers with native 2FA support.</strong>
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

## 💡 The Philosophy

Most modern password managers are heavy, subscription-based black boxes that lock your most sensitive credentials into proprietary cloud vaults. When service outages happen or companies change pricing, you are held hostage.

**MD-Vault takes a fundamentally different path:**

- **Your Data Belongs in Plain Text**: The single source of truth is a standard, clean `.md` file on your own drive. You can open, read, edit, or search it with VS Code, Obsidian, Typora, Vim, or terminal `grep` anytime—forever.
- **Zero Vendor Lock-in**: No proprietary encryption blobs, no database drivers, no SaaS subscriptions.
- **100% Air-Gapped by Design**: MD-Vault is a standalone, single-file HTML application. It requires **zero build tools, zero npm packages, and zero backend services**. Everything runs entirely inside your browser's local memory with **zero outgoing network calls**.

---

## ✨ Key Features

### 1. 🔑 Markdown-Native 2FA / TOTP Engine
Tired of switching between a password file and your phone authenticator? MD-Vault natively extends standard Markdown with the ````totp` code block:

````markdown
- **2FA One-Time Password**:
```totp
HXDMVJECJJWSRB3HWIZR4IFUGFTMXBOZ
```
````

- **In standard Markdown editors**: It remains a clean, human-readable Base32 secret string or `otpauth://` URI.
- **In MD-Vault**: It automatically springs to life as a **real-time 30-second countdown widget** with tabular monospace digits. Click once to copy the active 6-digit code (spaces automatically stripped).

### 2. 🗂️ AST-Driven Compact Card Layout
Long lists and tables in raw Markdown get tedious to scroll through. MD-Vault parses your Markdown AST and intelligently reconstructs headings, key-value rows, and code blocks into an ultra-compact **card grid** (`104px` label column + adaptive content). You can view 4 to 6 platforms side-by-side on a desktop screen without shrinking font sizes.

### 3. ⚡ Click-to-Copy Everything
- **Passwords & Multi-line Recovery Codes**: One-click copy with instant visual checkmark feedback.
- **Live 2FA Tokens**: Always copies the freshest live code.
- **Inline Identifiers**: Click on any inline code (`username`, `192.168.1.1`, `API_KEY`) to copy instantly.

### 4. 🔍 Instant Search & Keyboard Navigation
- Hit <kbd>/</kbd> anywhere to immediately focus the search bar.
- Sub-millisecond client-side filtering across platform names, usernames, and tags.
- Responsive left sidebar navigation auto-generated from your document's `#` and `##` headings.

### 5. 📂 Flexible Data Ingestion
- **Silent Auto-Load**: Automatically loads `PASSWORD_TEMPLATE.md` (or your custom file) on startup.
- **File Picker**: Switch between work, personal, and client vaults via the top-right button.
- **Drag-and-Drop**: Drop any `.md` file anywhere onto the browser window for instant rendering.

---

## 🚀 Quick Start

No installation, no Docker, and no Node.js required.

### Method 1: Direct Local Open (Fastest)
1. Clone or download this repository:
   ```bash
   git clone https://github.com/xiangc579/md-vault.git
   cd md-vault
   ```
2. Double-click `index.html` to open it directly in any modern browser (Chrome, Firefox, Safari, Edge).
3. Drag and drop your `.md` password file onto the page!

### Method 2: Serve Locally (Recommended for Auto-loading)
Due to browser CORS restrictions on `file://` fetch requests, serving via a lightweight HTTP server enables seamless auto-loading of your local Markdown file:

```bash
# Using Python 3
python3 -m http.server 8080

# Or using Node.js
npx serve .
```
Then visit `http://localhost:8080`.

---

## 📝 Document Syntax (Schema)

MD-Vault follows an intuitive, hierarchical Markdown structure:

```markdown
# My Secure Password Vault

## GitHub (Main Account)
- **Website**: https://github.com/login
- **Username**: `developer@example.com`
- **Tags**: `#core` `#dev`
- **Password**:
```text
K8#mP$9xL2@qW7!zR
```
- **2FA One-Time Password**:
```totp
JBSWY3DPEHPK3PXP
```
- **Backup Recovery Codes**:
```text
3a1b-4c2d
9e8f-7g6h
```
- **Notes**: Linked to company credit card; SSH key at `~/.ssh/id_ed25519.pub`.

---

## AWS Cloud
### Production Root
- **Host / URL**: https://signin.aws.amazon.com/console
- **Account ID**: `123456789012`
- **Password**:
```text
Srv_Production_9921#Root
```

### IAM Operator
- **Username**: `ops-deployer`
- **AccessKey ID**: `AKIAIOSFODNN7EXAMPLE`
```

### Hierarchy Rules

| Syntax | Semantic Meaning | MD-Vault Rendering Behavior |
| :--- | :--- | :--- |
| `# Title` (Line 1) | Document Title | Rendered as header title and `<title>` tag |
| `# Category` | High-level Category | Sidebar group title & card category badge |
| `## Platform` | Service / Platform | Reconstructed into an independent compact Card |
| `### Role` | Sub-account / Role | Nested sub-header inside the platform card |
| `- **Key**: Value` | Key-Value Row | Left-aligned bold label + right-aligned value |
| ````totp ... ```` | 2FA TOTP Secret | Real-time 30s countdown dynamic code widget |
| ````text ... ```` | Secret / Password | One-click copyable password box |
| `` `inline_code` `` | Short Identifier | Clickable copyable badge |

Ready-to-use templates are provided:
- [PASSWORD_TEMPLATE.md](PASSWORD_TEMPLATE.md) (English)
- [PASSWORD_TEMPLATE_ZH.md](PASSWORD_TEMPLATE_ZH.md) (简体中文)

---

## 🔒 Security Best Practices

> [!IMPORTANT]
> MD-Vault stores passwords in standard plain-text Markdown files. While this grants absolute ownership and zero lock-in, you should follow standard operational security (OpSec) measures.

1. **Keep Vaults in Private Repositories**:  
   If backing up via Git, **never push to a public repository**. Always keep your repository private or self-hosted (e.g. self-hosted Gitea / GitLab).
2. **Transparent File Encryption (Optional)**:  
   For zero-trust environments, combine your Markdown vault with transparent filesystem or Git encryption tools:
   - **`git-crypt`**: Transparently encrypts the `.md` file when committed and decrypts on checkout.
   - **`age` / `gpg`**: Decrypt into memory or temporary file before viewing:
     ```bash
     age -d -i ~/.ssh/id_ed25519 vault.md.age > vault.md
     ```
3. **Air-Gapped Operation**:  
   Since `index.html` has zero external network calls, you can safely run it on an offline, air-gapped laptop or securely across local network shares.

---

## 🛠️ Tech Stack & Design Spec

- **Core**: Vanilla HTML5, CSS3, ES2022.
- **Typography**: `Mulish` for gentle, readable sans-serif labels; `JetBrains Mono` with `tabular-nums` for crisp, non-jittering monospace secrets.
- **Parsing**: `markdown-it` AST renderer + custom token transformation rules.
- **2FA Engine**: Pure client-side `OTPAuth` RFC 6238 implementation.
- **Zero Build**: No bundlers, no transpilers, no dependencies to install.

For detailed design philosophy and tokens, see [DESIGN.md](DESIGN.md).

---

## 🗺️ Roadmap

- [x] AST-driven card reconstruction
- [x] Native TOTP countdown & 1-click copy
- [x] Full-text keyboard-driven search (`/`)
- [x] Drag-and-drop file ingestion
- [x] Dual-language standard templates (EN / ZH)
- [ ] Optional client-side AES-GCM password-protection layer
- [ ] Obsidian community plugin wrapper
- [ ] Raycast extension for quick credential lookup

---

## 📄 License

Distributed under the [MIT License](LICENSE). Free for personal and commercial use.
