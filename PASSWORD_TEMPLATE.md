# Password Vault Template

> **Instructions**:
> 1. This document uses standard Markdown syntax. Each second-level heading (`##`) represents an individual platform or application.
> 2. All sensitive credentials that require **one-click copying** (passwords, tokens, API keys, 2FA secrets, mnemonics) must be enclosed in standalone code blocks (` ```text ` or ` ```totp `) for instant copying in the companion Web renderer (`index.html`).
> 3. Code blocks tagged with ````totp` will be automatically calculated by the companion `index.html` renderer into **real-time 30-second countdown dynamic 2FA codes**. Click to copy the latest one-time password directly.

---

## 📑 Table of Contents

- [I. Core Ecosystem & Accounts](#i-core-ecosystem--accounts)
  - [Apple ID (Personal & Developer)](#apple-id-personal--developer)
  - [Google Account](#google-account)
  - [Microsoft (Microsoft 365)](#microsoft-microsoft-365)
- [II. Email & Communication Infrastructure](#ii-email--communication-infrastructure)
  - [Proton Mail (Encrypted Email & Mnemonic)](#proton-mail-encrypted-email--mnemonic)
  - [Business Email / SMTP Gateway](#business-email--smtp-gateway)
- [III. Cloud & DevOps Infrastructure](#iii-cloud--devops-infrastructure)
  - [GitHub (Code Hosting & 2FA)](#github-code-hosting--2fa)
  - [Cloud Server / VPS (Root Credentials & AccessKey)](#cloud-server--vps-root-credentials--accesskey)
  - [Cloudflare (CDN & Security)](#cloudflare-cdn--security)
- [IV. Commerce, Payments & Banking](#iv-commerce-payments--banking)
  - [Payment Gateway / WeChat Pay (Merchant Platform)](#payment-gateway--wechat-pay-merchant-platform)
  - [Merchant Center / Alipay (Business Account)](#merchant-center--alipay-business-account)
  - [Corporate NetBanking (Hardware U-Key / Token)](#corporate-netbanking-hardware-u-key--token)
- [V. Corporate Compliance & Government Portals](#v-corporate-compliance--government-portals)
  - [Tax Administration Portal (Corporate Tax Filing)](#tax-administration-portal-corporate-tax-filing)
  - [Internet Security & Compliance Filing (ICP / Cyber Bureau)](#internet-security--compliance-filing-icp--cyber-bureau)
- [VI. Brand Promotion & Content Communities](#vi-brand-promotion--content-communities)
  - [X / Twitter (Official Social Media)](#x--twitter-official-social-media)
  - [Developer Community (Juejin / Dev.to)](#developer-community-juejin--devto)
  - [Creator Platform (Xiaohongshu / Medium)](#creator-platform-xiaohongshu--medium)
- [VII. Community & Operations Support](#vii-community--operations-support)
  - [Telegram (Personal Account & Notification Bot)](#telegram-personal-account--notification-bot)
  - [Discord (Community & Developer Workspace)](#discord-community--developer-workspace)

---

# I. Core Ecosystem & Accounts

## Apple ID (Personal & Developer)

### Personal Apple ID
- **Website**: https://account.apple.com/account
- **Account / Email**: `personal@example.com`
- **Region**: US / Global
- **Password**:
```text
ApplePass#2026!Sec
```

### Apple Developer Account
- **Developer Portal**: https://developer.apple.com/account
- **App Store Connect**: https://appstoreconnect.apple.com
- **Account / Email**: `developer@company.com`
- **Enabled Services**: Certificates, Identifiers & Profiles (DeviceCheck)

---

## Google Account
- **Login Portal**: https://accounts.google.com
- **Primary Email**: `main.account@gmail.com`
- **Recovery Email**: `backup.recovery@example.com`
- **Recovery Phone**: `+1 (555) 019-2834`
- **2FA One-Time Password (TOTP Secret)**:
```totp
HXDMVJECJJWSRB3HWIZR4IFUGFTMXBOZ
```
- **GCP Billing Address**:
```text
1600 Amphitheatre Parkway
Mountain View, CA 94043
United States
```

---

## Microsoft (Microsoft 365)
- **Subscription Type**: Microsoft 365 Business Standard
- **Admin Account**: `admin@tenant.onmicrosoft.com`
- **Password**:
```text
Ms365#Admin!Passwd
```

---

# II. Email & Communication Infrastructure

## Proton Mail (Encrypted Email & Mnemonic)
- **Website**: https://proton.me/
- **Account / Email**: `core_ops@proton.me`
- **Password**:
```text
Proton#Vault!2026
```
- **Recovery Mnemonic Phrase (12 Words)**:
```text
abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon about
```

---

## Business Email / SMTP Gateway
- **Webmail Portal**: https://mail.company.com/
- **Email Address**: `service@company.com`
- **API Key / App Password**:
```text
re_8xDTynvW_xxxxxxxxxxxx
```
- **SMTP Server**: `smtp.resend.com:587`

---

# III. Cloud & DevOps Infrastructure

## GitHub (Code Hosting & 2FA)
- **Website**: https://github.com/login
- **Username / Email**: `developer@example.com`
- **Password**:
```text
K8#mP$9xL2@qW7!zR
```
- **2FA One-Time Password (TOTP Secret)**:
```totp
JBSWY3DPEHPK3PXP
```
- **2FA Recovery Codes**:
```text
3a1b-4c2d
9e8f-7g6h
5i4j-3k2l
1m0n-9o8p
```
- **SSH Public Key Path**: `~/.ssh/id_ed25519.pub`

---

## Cloud Server / VPS (Root Credentials & AccessKey)
- **Server Host / IP**: `198.51.100.245:22`
- **SSH User**: `root`
- **SSH Password**:
```text
Srv_Production_9921#Root
```
- **AccessKey ID**: `LTAI5tExampleKeyID123`
- **AccessKey Secret**:
```text
ExampleSecretKeyString998877665544332211
```

---

## Cloudflare (CDN & Security)
- **Dashboard**: https://dash.cloudflare.com/
- **Account / Email**: `ops@example.com`
- **Turnstile Site Key**:
```text
0x4AAAAAAABBBBBBBCCCCDDD
```
- **Turnstile Secret Key**:
```text
0x4AAAAAAABBBBBBBCCCCDDD-SecretKeyExample
```

---

# IV. Commerce, Payments & Banking

## Payment Gateway / WeChat Pay (Merchant Platform)
- **Merchant Dashboard**: https://pay.weixin.qq.com/
- **Merchant ID (MCH ID)**: `1900000109`
- **Operator Username**: `admin@1900000109`
- **Operation Password / PIN**:
```text
654321
```

---

## Merchant Center / Alipay (Business Account)
- **Business Center**: https://b.alipay.com
- **Super Admin Account**: `business@example.com`
- **Login Password**:
```text
AliPay#Login!2026
```
- **Payment PIN (6 digits)**:
```text
889900
```

---

## Corporate NetBanking (Hardware U-Key / Token)
- **Client Version**: Desktop Professional Suite
- **Account Number**: `6225880100000000`
- **User Identifier**: `USER0001`
- **Query PIN**:
```text
829103
```
- **Hardware U-Key Transaction PIN**:
```text
918273
```
- **Notes**: Requires physical Type-C hardware security token.

---

# V. Corporate Compliance & Government Portals

## Tax Administration Portal (Corporate Tax Filing)
- **Taxpayer Identification Number (TIN)**: `91110000000000001X`
- **Authorized Contact Phone**: `+86 13800000000`
- **Withholding / Tax Filing PIN**:
```text
Tax#2026!Passwd
```

---

## Internet Security & Compliance Filing (ICP / Cyber Bureau)
- **Portal Website**: National Cyber Security & Compliance Portal
- **Unified Social Credit Code**: `91110000000000001X`
- **Officer Phone**: `+86 13800000000`

---

# VI. Brand Promotion & Content Communities

## X / Twitter (Official Social Media)
- **Website**: https://x.com/
- **Official Handle**: `@company_official`
- **Authentication**: Google OAuth Single Sign-On
- **Bound Security Email**: `social@example.com`

---

## Developer Community (Juejin / Dev.to)
- **Website**: https://juejin.cn
- **Login Phone / ID**: `13800000000`
- **Channel Purpose**: Engineering blog & product changelogs

---

## Creator Platform (Xiaohongshu / Medium)
- **Creator Studio**: https://creator.xiaohongshu.com/
- **Bound Phone**: `13800000000`
- **Login Method**: Mobile QR Code Scan
- **Studio / Workspace Name**: Indie Developer Studio

---

# VII. Community & Operations Support

## Telegram (Personal Account & Notification Bot)
- **Bound Email**: `telegram_user@proton.me`
- **Two-Step Verification Password (2FA)**:
```text
Tg#Secure2026!
```
- **Password Hint**:
```text
MyFavoritePetName
```

### Notification Bot
- **Bot Name**: `app_notify_bot`
- **HTTP API Token**:
```text
1234567890:ABCdefGHIjklMNOpqrSTUvwxYZ
```
- **Chat ID**: `987654321`

---

## Discord (Community & Developer Workspace)
- **Website**: https://discord.com/
- **Account / Email**: `discord@example.com`
- **Bound Phone**: `+44 7700 900123`
- **Password**:
```text
Discord#2026!Pass
```
