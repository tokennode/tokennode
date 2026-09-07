# TokenNode

TokenNode 是一个分布式 AI 算力共享网络：把闲置设备（手机 / 电脑 / 服务器）接入网络成为**分享节点**，分享算力赚取积分；积分可划转为**使用者额度**，经 OpenAI 兼容入口调用全网模型。

- **先分享，再使用**：激活入网后节点自动开始分享免费模型赚取积分，积分可划转为使用额度。
- **邀请码入网**：安装后凭邀请码完成激活注册，首次注册赠 **10000 积分**（公测期间限量发放，见下文）。
- **一个控制台**：每个节点自带 Web 控制台（本机 UI），状态 / 模型 / 积分 / 邀请一目了然。

> 本仓库只发布安装包与更新（[Releases](https://github.com/tokennode/tokennode/releases)），**不包含源码**。

## 下载安装

从 [Releases](https://github.com/tokennode/tokennode/releases/latest) 下载对应平台产物（文件名含平台与版本号；tag 号 `vNNN` 为全网统一版本锚）：

| 平台 | 产物 | 说明 |
|---|---|---|
| Android（arm64 手机/盒子） | `tokennode-android-*.apk` | 侧载安装，见下文引导 |
| Windows 桌面 | `tokennode-desktop-*-setup.exe` | NSIS 安装包，内嵌节点 |
| Linux 服务器（amd64） | `relay-linux-amd64-*.tar.gz` | 解压即用（含组网组件） |
| Windows 命令行（amd64） | `relay-windows-amd64-*.zip` | 解压即用（含组网组件） |

### 激活入网（需要邀请码）

所有平台首次启动都会进入**入网引导**，粘贴邀请码即完成激活注册：

- 注册同时建立你的**分享账户**与**使用账户**，并赠送 10000 积分（≈100 次免费模型调用）；
- 激活后节点自动开始分享免费模型持续赚积分，积分可在控制台划转为使用额度；
- **公测期间邀请码通过官方渠道限量发放**（渠道确定后在此公布）；
- 现有用户可在自己控制台的「邀请」页按档位生成邀请码，邀请朋友加入。

### Android

1. 下载 APK 并点击安装；系统提示「未知来源」时允许安装（各品牌路径略有差异）。
2. 首次启动进入入网引导：粘贴邀请码完成激活注册，通知栏常驻分享节点服务。
3. Play Protect 可能提示「不认识的应用」——本应用不在应用商店分发，属预期告警；选择「仍然安装 / 更多详情 → 安装」。

### Windows 桌面

1. 运行 `tokennode-desktop-*-setup.exe` 安装。
2. SmartScreen 可能拦截未签名安装包：点击「更多信息」→「仍要运行」。
3. 启动 TokenNode，首次进入入网引导：粘贴邀请码完成激活注册；控制台随装即用，数据目录在用户目录下（`TokenNode\`）。

### Linux / Windows 服务器（relay 裸二进制）

```bash
# Linux amd64：从 Releases 页下载对应版本的 relay-linux-amd64-*.tar.gz 后：
tar xzf relay-linux-amd64-*.tar.gz
cd relay && ./relay
```

包内 `relay` 与组网组件同目录，是完整拷贝单元；`VERSION` 文件标注核版本，供排障核对。建议用 systemd / 任务计划托管常驻。启动后访问本机控制台 UI，首次进入入网引导：粘贴邀请码完成激活注册。

### 命令行用户（dsh 插件）

Claude Code 场景的模型代理插件经 npm 分发：

```bash
npm install -g @dsh-external/dsh-relay@latest
```

## 检查更新

节点控制台顶部在检测到新版本时会出现「🔄 有新版本」提示，点击直达下载页；也可以随时来 [Releases](https://github.com/tokennode/tokennode/releases/latest) 手动更新（Android 覆盖安装即升级，桌面重跑安装包）。

## 安全须知

- 节点的**配置文件等同密钥**：包含身份标识与额度账户，泄露等于交出账户，请勿分享 / 上传。
- 安装包未做代码签名（SmartScreen / Play Protect 会告警），每个 Release 附全部产物的 SHA-256 校验值，可自行核对。

## 反馈

问题 / 建议 / 安装失败都欢迎提 [Issues](https://github.com/tokennode/tokennode/issues)，附上平台、版本号（控制台顶栏可见）与现象即可。

## 许可

安装包按 [LICENSE](./LICENSE)（专有许可）提供：可免费安装使用，禁止再分发与逆向工程。转发请直接分享本仓库链接。
