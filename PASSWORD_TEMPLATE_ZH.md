# 密码管理索引表 (Password Vault Template)

> **使用说明**：
> 1. 本文档采用标准 Markdown 语法维护，每个二级标题（`##`）代表一个独立平台或应用。
> 2. 所有需要**一键复制**的内容（密码、Token、API Key、2FA 密钥、助记词）均置于独立的代码块中，便于在配套的 Web 渲染器（`index.html`）中一键复制。
> 3. 代码块标记为 ````totp` 的条目会在配套的 `index.html` 渲染器中自动计算为**30秒倒计时动态验证码**，点击即可直接复制最新动态口令。

---

## 📑 平台快速导航目录 (Table of Contents)

- [一、 核心生态与多媒体账号](#一-核心生态与多媒体账号)
  - [Apple ID (个人与开发者)](#apple-id-个人与开发者)
  - [Google 账号体系](#google-账号体系)
  - [微软 (Microsoft 365)](#微软-microsoft-365)
- [二、 邮件与通讯基础设施](#二-邮件与通讯基础设施)
  - [Proton Mail (加密邮箱与助记词)](#proton-mail-加密邮箱与助记词)
  - [企业邮箱 / 邮件网关](#企业邮箱--邮件网关)
- [三、 云计算与开发基础设施](#三-云计算与开发基础设施)
  - [GitHub (代码托管与 2FA)](#github-代码托管与-2fa)
  - [云服务器 / ECS (Root 凭据与 AccessKey)](#云服务器--ecs-root-凭据与-accesskey)
  - [Cloudflare (CDN 与安全)](#cloudflare-cdn-与安全)
- [四、 商业、支付与自由职业](#四-商业支付与自由职业)
  - [微信支付 (商户平台)](#微信支付-商户平台)
  - [支付宝 (商家平台)](#支付宝-商家平台)
  - [企业网银 (招商银行 / U-Key)](#企业网银-招商银行--u-key)
- [五、 企业资质与政务平台](#五-企业资质与政务平台)
  - [电子税务局 (企业税务申报)](#电子税务局-企业税务申报)
  - [公安部互联网安全服务平台 (公安备案)](#公安部互联网安全服务平台-公安备案)
- [六、 品牌推广与内容社区](#六-品牌推广与内容社区)
  - [X / Twitter (海外社媒)](#x--twitter-海外社媒)
  - [稀土掘金 (开发者技术社区)](#稀土掘金-开发者技术社区)
  - [小红书 (创作者平台)](#小红书-创作者平台)
- [七、 社群通讯与宣发运营支撑](#七-社群通讯与宣发运营支撑)
  - [Telegram (个人号与通知机器人)](#telegram-个人号与通知机器人)
  - [Discord (社群与开发者交流)](#discord-社群与开发者交流)

---

# 一、 核心生态与多媒体账号

## Apple ID (个人与开发者)

### 个人主账号
- **平台网址**: https://account.apple.com/account
- **登录账号**: `personal@example.com`
- **登录密码**:
```text
ApplePass#2026!Sec
```

### 开发者账号 (Apple Developer)
- **控制台**: https://developer.apple.com/account
- **App Store Connect**: https://appstoreconnect.apple.com
- **登录账号**: `developer@company.com`
- **已开通服务**: Certificates, Identifiers & Profiles (DeviceCheck)

---

## Google 账号体系
- **登录入口**: https://accounts.google.com
- **主登录账号**: `main.account@gmail.com`
- **辅助安全邮箱**: `backup.recovery@example.com`
- **绑定安全手机**: `+86 13800000000`
- **2FA 动态口令 (TOTP 密钥)**:
```totp
HXDMVJECJJWSRB3HWIZR4IFUGFTMXBOZ
```
- **GCP 账单登记地址**:
```text
1600 Amphitheatre Parkway
Mountain View, CA 94043
United States
```

---

## 微软 (Microsoft 365)
- **服务类型**: Microsoft 365 商业订阅
- **登录账号**: `admin@tenant.onmicrosoft.com`
- **登录密码**:
```text
Ms365#Admin!Passwd
```

---

# 二、 邮件与通讯基础设施

## Proton Mail (加密邮箱与助记词)
- **平台网址**: https://proton.me/
- **登录邮箱**: `core_ops@proton.me`
- **登录密码**:
```text
Proton#Vault!2026
```
- **账户恢复助记词 (12 Words)**:
```text
abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon about
```

---

## 企业邮箱 / 邮件网关
- **平台网址**: https://mail.company.com/
- **登录邮箱**: `service@company.com`
- **授权密码 / API Key**:
```text
re_8xDTynvW_xxxxxxxxxxxx
```
- **SMTP 服务器**: `smtp.resend.com:587`

---

# 三、 云计算与开发基础设施

## GitHub (代码托管与 2FA)
- **平台网址**: https://github.com/login
- **登录账号**: `developer@example.com`
- **登录密码**:
```text
K8#mP$9xL2@qW7!zR
```
- **2FA 动态口令 (TOTP 密钥)**:
```totp
JBSWY3DPEHPK3PXP
```
- **2FA 备用恢复码 (Recovery Codes)**:
```text
3a1b-4c2d
9e8f-7g6h
5i4j-3k2l
1m0n-9o8p
```
- **SSH Key 公钥路径**: `~/.ssh/id_ed25519.pub`

---

## 云服务器 / ECS (Root 凭据与 AccessKey)
- **主机公网 IP**: `198.51.100.245:22`
- **登录用户**: `root`
- **SSH 密码**:
```text
Srv_Production_9921#Root
```
- **AccessKey ID**: `LTAI5tExampleKeyID123`
- **AccessKey Secret**:
```text
ExampleSecretKeyString998877665544332211
```

---

## Cloudflare (CDN 与安全)
- **控制台**: https://dash.cloudflare.com/
- **登录账号**: `ops@example.com`
- **Turnstile 站点 Key (Site Key)**:
```text
0x4AAAAAAABBBBBBBCCCCDDD
```
- **Turnstile 密钥 (Secret Key)**:
```text
0x4AAAAAAABBBBBBBCCCCDDD-SecretKeyExample
```

---

# 四、 商业、支付与自由职业

## 微信支付 (商户平台)
- **商户平台**: https://pay.weixin.qq.com/
- **商户号 (MCH ID)**: `1900000109`
- **操作员账号**: `admin@1900000109`
- **操作密码**:
```text
654321
```

---

## 支付宝 (商家平台)
- **商家中心**: https://b.alipay.com
- **超级管理员账号**: `business@example.com`
- **登录密码**:
```text
AliPay#Login!2026
```
- **支付密码 (6 位)**:
```text
889900
```

---

## 企业网银 (招商银行 / U-Key)
- **客户端版本**: PC 桌面专业版
- **登录账号**: `6225880100000000`
- **用户识别码**: `USER0001`
- **查询密码 (纯数字)**:
```text
829103
```
- **U-Key 交易密码**:
```text
918273
```
- **备注说明**: 需配合物理 Type-C U-Key 硬件使用。

---

# 五、 企业资质与政务平台

## 电子税务局 (企业税务申报)
- **纳税人识别号**: `91110000000000001X`
- **办税人员手机**: `13800000000`
- **扣缴申报密码**:
```text
Tax#2026!Passwd
```

---

## 公安部互联网安全服务平台 (公安备案)
- **平台网址**: 全国公安机关互联网站安全管理服务平台
- **统一社会信用代码**: `91110000000000001X`
- **负责人手机**: `13800000000`

---

# 六、 品牌推广与内容社区

## X / Twitter (海外社媒)
- **平台网址**: https://x.com/
- **用户账号 / 句柄**: `@company_official`
- **登录方式**: Google 授权登录
- **绑定安全邮箱**: `social@example.com`

---

## 稀土掘金 (开发者技术社区)
- **平台网址**: https://juejin.cn
- **登录手机**: `13800000000`
- **专栏定位**: 团队技术博客与产品动态

---

## 小红书 (创作者平台)
- **创作者后台**: https://creator.xiaohongshu.com/
- **绑定手机**: `13800000000`
- **登录方式**: 手机扫码登录
- **创作者空间名称**: 独立开发工作台

---

# 七、 社群通讯与宣发运营支撑

## Telegram (个人号与通知机器人)
- **绑定邮箱**: `telegram_user@proton.me`
- **两步验证密码 (2FA)**:
```text
Tg#Secure2026!
```
- **密码提示 (Hint)**:
```text
MyFavoritePetName
```

### 通知机器人 (Notification Bot)
- **Bot 名称**: `app_notify_bot`
- **HTTP API Token**:
```text
1234567890:ABCdefGHIjklMNOpqrSTUvwxYZ
```
- **Chat ID**: `987654321`

---

## Discord (社群与开发者交流)
- **平台网址**: https://discord.com/
- **登录邮箱**: `discord@example.com`
- **绑定手机**: `+44 7700 900123`
- **登录密码**:
```text
Discord#2026!Pass
```
