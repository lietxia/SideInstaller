<div align="center">

<img src="app-icon.png" alt="SideInstaller" width="120" />

<a id="doc-h1" name="doc-h1"></a>
# SideInstaller

**直接在 iPhone 上安装 SideStore 和 LiveContainer —— 无需电脑。**

[![Install](https://img.shields.io/badge/Install-SideInstaller-2ea44f?style=for-the-badge)](https://sideinstaller.net/)
[![Version](https://img.shields.io/badge/version-2.2.0-2669ed?style=for-the-badge)](CHANGELOG.md)
[![Platform](https://img.shields.io/badge/platform-iOS-lightgrey?style=for-the-badge&logo=apple)](#doc-h4)
[![License](https://img.shields.io/badge/license-Custom-orange?style=for-the-badge)](LICENSE.md)

🌐 **Language / 语言:** [English](README.md) · [简体中文](README.zh-CN.md) · [Español](README.es.md) · [Italiano](README.it.md) · [Tiếng Việt](README.vi.md) · [Français](README.fr.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Português](README.pt-BR.md) · [Türkçe](README.tr.md)

</div>

---

> [!CAUTION]
> **只从官方来源安装 SideInstaller。**
>
> 本项目是开源的，这意味着任何人都可以 fork 代码、插入窃取凭据的程序，把你的 Apple ID 和密码上传到他们自己的服务器，重新构建，并以相同的名称和图标重新分发。恶意的 fork 从外观上看与真正的应用完全一样。
>
> 我发布的**唯一**构建版本是：
> - **网站：** https://sideinstaller.net/
> - **代码仓库：** https://github.com/FrizzleM/SideInstaller
>
> 无论看起来多么官方，都不要从任何其他网站、AltStore 源、Telegram 频道、Discord 服务器、应用仓库或镜像安装 SideInstaller。未经明确同意重新分发我的构建版本也违反[许可协议](LICENSE.md)。
>
> 有一个假冒网站叫“sideinstaller.com”。这个网站**不合法**，很可能提供恶意软件。请务必只从上面列出的**官方来源**下载。

> [!NOTE]
> **关于这个 fork —— 仅翻译文档。** 这个 fork 的存在只是单纯为了翻译和澄清这些说明。它不构建也不发布**任何应用二进制文件**；每个下载链接仍然指向上面的官方来源。这里的应用源代码未经修改。请始终从 https://sideinstaller.net/ 获取真正的应用 —— 绝不要从 fork、镜像或重新签名的 IPA 获取。

---

<a id="doc-h2" name="doc-h2"></a>
## 本页目录

- [它是什么](#doc-h3)
- [要求](#doc-h4)
- [如何使用](#doc-h5)
  - [方法 A —— siboot（iOS 27+，无需电脑）](#doc-h6)
  - [方法 B —— 企业证书（较旧的 iOS）](#doc-h11)
  - [链接](#doc-h12)
  - [快捷指令](#doc-h13)
- [兼容性](#doc-h14)
  - [iOS 26.4 至 26.x：远程配对文件](#doc-h15)
- [SideInstaller 安全吗？](#doc-h16)
- [项目结构](#doc-h17)
- [参与贡献](#doc-h18)
- [许可协议](#doc-h19)

---

<a id="doc-h3" name="doc-h3"></a>
## 它是什么

SideStore 和 LiveContainer 目前是在 iOS 上侧载的最佳方式。然而有一个大问题：安装它们需要电脑，而很多人并没有电脑。这就是我制作 SideInstaller 的原因 —— 它是一款免费的开源 iOS 应用，可以直接在你的 iPhone 上安装它们，无需电脑。

SideInstaller 在设备上完成整个设置流程。它负责配对、描述文件和安装步骤 —— 这些步骤通常迫使你插上电脑并运行桌面工具 —— 全部由手机本身上的一个应用完成。完成后，你会得到一套完整可用的 SideStore 和 LiveContainer，随时可以侧载自己的应用。

整个设计以简单为目标。没有复杂的配置，没有命令行，也不需要理解任何底层机制。你只需打开应用，按照几个步骤操作，剩下的交给它完成。对于任何曾经想侧载却没有 Mac 或电脑的人来说，这消除了入门的最大障碍。

而且因为它是开源的，你不必只听我的一面之词。完整代码可供任何人阅读、审计或贡献，因此你可以确切地看到设备上运行的是什么。

<a id="doc-h4" name="doc-h4"></a>
## 要求

开始之前，请确保你具备：

- **iPhone 或 iPad**，运行 **iOS 27 及以上** —— 在 iOS 17.4+ 上需要一台电脑上制作的配对文件；从 iOS 26.4 起需要[远程配对文件](#doc-h15)。参见[兼容性表格](#doc-h14)。
- **Wi-Fi**（仅首次需要）。
- **开发者模式**已打开（使用 siboot 方法时）。
- **你的 Apple 账户凭据** —— 仅用于在设备上为应用签名；绝不会收集。

<a id="doc-h5" name="doc-h5"></a>
## 如何使用

有两种安装方法。请选择与你的 iOS 版本相符的一种：

| 你的情况 | 方法 | 需要电脑吗？ |
| --- | --- | --- |
| iOS 27 或更高版本 | [方法 A —— siboot](#doc-h6)（推荐） | 不需要 |
| iOS 17.4 – 26.7，或 siboot 对你不适用 | [方法 B —— 企业证书](#doc-h11) | 需要，仅一次 |

<a id="doc-h6" name="doc-h6"></a>
### 方法 A —— siboot（iOS 27+，无需电脑）

[siboot](https://github.com/FrizzleM/siboot) 从 iPhone 本身安装 SideInstaller，并使用你自己的 Apple 账户签名：无需电脑，也无需证书。你需要 **iOS 27 或更高版本**、**Wi-Fi** 以及**已打开开发者模式**。网站 [sideinstaller.net](https://sideinstaller.net/) 以图示展示了第 1 至第 3 步。

<a id="doc-h7" name="doc-h7"></a>
#### 第 1 步 —— 安装三个免费应用

从 App Store 安装全部三个：

- [rootshell](https://apps.apple.com/app/rootshell-local-terminal-ssh/id6755794662)
- [Open Minis](https://apps.apple.com/app/id6759188481)
- [LocalDevVPN](https://apps.apple.com/app/id6755608044)

<a id="doc-h8" name="doc-h8"></a>
#### 第 2 步 —— 在 rootshell 中配对

1. 在 rootshell 中，打开 **设置 › 位置日记模式 › 仅会话**。
2. 点按 **Local Shell**，然后点按右上角的 **打开**。
3. **一次一行**运行以下命令：

   ```sh
   curl -fsSLO https://raw.githubusercontent.com/FrizzleM/siboot/main/rootshell/bin/siboot-pair.wasm
   ifconfig en0 > ifconfig.txt
   ./siboot-pair.wasm
   ```

4. 打开 **设置 › 隐私与安全性 › 开发者模式**，滚动到底部，点按 **与 siboot 配对**，然后输入你的密码和 rootshell 显示的验证码。
5. **保持 rootshell 运行** —— 不要关闭它。

<a id="doc-h9" name="doc-h9"></a>
#### 第 3 步 —— 从 Open Minis 安装

1. 连接 **LocalDevVPN**。
2. 在 **Open Minis** 中，点按右上角的控制台图标，然后点按 **Shell Terminal**。
3. 运行：

   ```sh
   wget -qO- https://raw.githubusercontent.com/FrizzleM/siboot/main/minis/install.sh | sh
   ```

4. 输入 rootshell 显示的传输码 —— **仅第一次**；之后 siboot 会使用它保存的配对文件。
5. 输入你的 Apple 账户**电子邮件**、**密码**和**验证码**。
6. **保持 Minis 打开**，直到它显示完成。首次使用时，请在 **设置 › 通用 › VPN 与设备管理** 中信任你的 Apple 账户。

<a id="doc-h10" name="doc-h10"></a>
#### 第 4 步 —— 打开 SideInstaller

在 **LocalDevVPN 已连接**的情况下，使用你的 Apple 账户登录，然后点按 **安装 SideStore** 或 **安装 SideStore + LiveContainer**。完成。

> **配对后：** 在 Open Minis 中运行 `siboot developer-mode` 会要求 iPhone 在设置中显示开发者模式开关；加上 `--turn-on` 即可将它打开。详见[详细说明](https://github.com/FrizzleM/siboot/blob/main/minis/README.md#developer-mode)。

<a id="doc-h11" name="doc-h11"></a>
### 方法 B —— 企业证书（较旧的 iOS）

在 iOS 27 之前的版本上，或如果 siboot 对你不适用，请使用 [sideinstaller.net/#legacy](https://sideinstaller.net/#legacy) 上的企业证书之一安装 SideInstaller，然后从上面的**第 4 步**继续。（较旧版本还需要配对文件 —— 参见[兼容性](#doc-h14)。）

<a id="doc-h12" name="doc-h12"></a>
### 链接

SideInstaller 可以打开三种 `sideinstaller://` 链接，并且在执行其中任何一种之前都会询问：

| 链接 | 作用 |
| --- | --- |
| `sideinstaller://install?url=<percent-encoded https link to an .ipa>` | 将 IPA 作为自定义 .ipa 下载并安装 —— 用于从网站一键安装。 |
| `sideinstaller://pairingFile?data=<base64 pairing file>` | 导入配对文件。当收到 `sidestore://pairing?urlname=sideinstaller` 请求时，SideStore 会回传一个配对文件 —— 这就是配对文件卡片上的 **从 SideStore 获取** 所做的事。 |
| `sideinstaller://certificate?data=<base64 PKCS#12>&password=<password>` | 让 SideInstaller 从那时起使用该证书签名，前提是 Apple 已将它列入你 Apple ID 的证书列表。 |

**使用 SideStore 的证书**（在“已存在签名证书”弹窗和证书页面上）会通过 `sidestore://certificate?callback_template=sideinstaller://certificate?data=$(BASE64_CERT)&password=$(PASSWORD)`（经过百分号编码）向 SideStore 请求它自己的证书，这样免费 Apple ID 的一个证书就能同时供两个应用使用。该回复是唯一不会再次询问的链接：SideStore 刚刚已经询问过是否导出它。

Discord 和大多数聊天应用只会让 `https://` 链接可点按，因此要在其中发布安装链接，请使用 `https://sideinstaller.net/open.html?url=<percent-encoded https link to an .ipa>`。该页面会显示 IPA 从何处下载，并将其交给 `sideinstaller://install`，同时提供一个按钮，供 iOS 没有自动打开应用时使用。

<a id="doc-h13" name="doc-h13"></a>
### 快捷指令

SideInstaller 的工具是“快捷指令”应用中的操作，因此快捷指令、自动化、操作按钮或 Siri 都可以运行它们：

- **位置模拟：** Set Location（地图上选取的地点、地址，或来自另一个操作的位置）、Set Location to Coordinates、Set Location to Saved Place、Reset Location、Get Spoofed Location、Is Location Spoofed、Play GPX Route、Travel to Place（在 OpenStreetMap 上规划的路线，按步行、骑行或驾车以及各条道路的限速行进）、Stop Route、Save Place 和 Delete Saved Place。
- **侧载应用：** Get Sideloaded Apps（每个都显示到期日期和剩余天数）、Refresh All Apps 和 Refresh App。
- **安装：** Install App（SideStore、LiveContainer + SideStore、Madeira 或 AltStore，稳定版或 nightly）、Install IPA 和 Install IPA from URL。这些操作会打开 SideInstaller，因为安装过程中可能需要在其中停下来询问。
- **配对及其他：** Get Pairing File、Import Pairing File、Install Pairing File into Apps、Show Developer Mode in Settings、Is LocalDevVPN Connected、Connect LocalDevVPN 和 Get Activity Log。

其余操作在后台运行，与应用自身页面一样走 LocalDevVPN，因此必须开启该隧道：在运行它们之前先连接它（“快捷指令”的 Set VPN 操作可以做到），或者打开 **需要时打开 LocalDevVPN**，此时该操作会请求在 SideInstaller 中继续以连接它。通过快捷指令设置的位置会一直保持，直到执行 Reset Location：SideInstaller 会继续在后台运行以维持该位置，就像你在应用中设置位置一样。Siri 能识别“用 SideInstaller 将我的位置模拟到*已存储的地点*”、“用 SideInstaller 重置我的位置”和“用 SideInstaller 续签我的应用”。这些操作的名称是英文；运行时它们所说的内容则是 SideInstaller 的语言。

<a id="doc-h14" name="doc-h14"></a>
## 兼容性

| iOS | 是否兼容？ |
| --- | --- |
| 27+ | ✅ 是 —— 使用 siboot 无需电脑 |
| 26.4 – 26.7 | ⚠️ 是，但[需要远程配对文件](#doc-h15)，这需要电脑 |
| 17.4 – 26.3 | ⚠️ 是，但[需要配对文件](https://docs.sidestore.io/docs/advanced/alternative#pairing)，这需要电脑 |
| <17.4 | ❌ 否 |

<a id="doc-h15" name="doc-h15"></a>
### iOS 26.4 至 26.x：远程配对文件

从 iOS 26.4 起，当 lockdown 配对文件（来自 jitterbugpair、`pymobiledevice3 lockdown pair` 或 idevice_pair 的 **Lockdown**）通过 LocalDevVPN 连接时，iPhone 会立即断开连接，因此它们再也无法在 iPhone 上使用，无论文件有多新。远程配对（RPPairing）文件仍然可用：

1. 在 Mac、Windows 电脑或 Linux 电脑上，打开 [idevice_pair](https://github.com/jkcoxson/idevice_pair/releases/latest) 并插上 iPhone。如有提示，请点按 **信任**。
2. 选择这台 iPhone，选择 **Remote pairing**，点击 **Create**，并保持 iPhone 解锁直到完成。
3. 点击 **Save to file…**，通过隔空投送、iCloud 云盘或数据线将文件发送到 iPhone。
4. 在 SideInstaller 中，点按 **导入配对文件**（或 **更换**）并选择它。

从 [iLoader](https://github.com/nab138/iloader) 导出的配对文件（**管理配对文件** › **导出**）同时包含两种类型，同样可用。

<a id="doc-h16" name="doc-h16"></a>
## SideInstaller 安全吗？

SideInstaller 以安全和隐私为设计出发点。该应用完全本地运行且开源，任何人都可以检查它到底做了什么。

**你的 Apple 凭据绝不会离开你的设备。** 它们只在本地用于签名和安装你的应用，绝不会以任何方式传输、记录或收集。

**没有服务器、没有分析、没有账户。** 不收集任何内容，也没有什么可注册的。

**完全可审计。** 每一行都可以在源代码中核实。

> [!WARNING]
> 以上所有内容对**这个**代码仓库以及从它发布的构建版本都是真实的。它**不**适用于你在别处找到的 fork、重新签名的 IPA 或副本 —— 那些可能被修改以窃取你输入的 Apple ID。如果不是从 https://sideinstaller.net/ 获取的，就不要把你的凭据交给它。

<a id="doc-h17" name="doc-h17"></a>
## 项目结构

| 路径 | 内容 |
| :-- | :-- |
| `ios-app/` | SwiftUI 应用 —— 界面、安装引擎、证书处理、翻译 |
| `ios-live-activity/` | 在灵动岛和锁屏上绘制配对码的小组件扩展 |
| `ios-tests/` | 应用的单元测试（`SideInstallerTests`） |
| `rust-core/` | 编译进 `SideInstallerFFI.xcframework` 的 Rust 核心 |
| `scripts/` | 构建、检查和发布脚本 |
| `.github/` | 用于检查拉取请求、构建未签名 IPA、将其发布为发行版并交给签名者的工作流 |

已签名的构建版本和安装页面位于 [FrizzleM/SideInstaller-Signed](https://github.com/FrizzleM/SideInstaller-Signed)：它用每个证书为每次发行版的 IPA 签名，将签名后的 IPA 附到自己的发行版上，并部署 [sideinstaller.net](https://sideinstaller.net/)。两个代码仓库中都不会提交任何 IPA。

siboot 负责[从 iPhone 本身](#doc-h5)安装 SideInstaller，它位于 [FrizzleM/siboot](https://github.com/FrizzleM/siboot)。它通过一个锁定到某个提交的子模块，构建这个仓库中自带的 crate 以及 rust-core 的 `apple_session.rs` 和 `error_text.rs`，因此这里的更改只有在那个指针移动后才会传到 siboot。

<a id="doc-h18" name="doc-h18"></a>
## 参与贡献

欢迎提交 Issue 和拉取请求。如果你要报告错误，请附上你的 iOS 版本、应用版本以及失败发生的步骤。

每个拉取请求都会由 `checks` 工作流检查：Rust 测试和 clippy、带应用单元测试的模拟器构建，以及翻译（应用中添加的字符串需要在每个 `ios-app/*Strings.swift` 中有对应条目）。同样的检查可以在 Mac 上用 `scripts/test-rust.sh`、`scripts/check-ios.sh`（在干净的克隆中运行，因为它会生成 Xcode 项目）和 `scripts/check_translations.py` 执行。

<a id="doc-h19" name="doc-h19"></a>
## 许可协议

参见 [LICENSE.md](LICENSE.md)。简而言之：你可以出于非商业目的，在署名的前提下阅读、修改和分享**源代码**。重新分发官方构建版本（IPA）或以任何形式将本项目商业化都需要书面许可。

<div align="center">

**SideInstaller 由 [FrizzleM](https://github.com/FrizzleM) 开发** · 本 fork 中的文档翻译为社区贡献；应用版权仍归 FrizzleM 所有。

</div>
