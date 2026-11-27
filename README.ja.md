<div align="center">

<img src="app-icon.png" alt="SideInstaller" width="120" />

# SideInstaller

**iPhone に SideStore と LiveContainer を直接インストール — パソコンは不要です。**

[![Install](https://img.shields.io/badge/Install-SideInstaller-2ea44f?style=for-the-badge)](https://sideinstaller.net/)
[![Version](https://img.shields.io/badge/version-2.2.0-2669ed?style=for-the-badge)](CHANGELOG.md)
[![Platform](https://img.shields.io/badge/platform-iOS-lightgrey?style=for-the-badge&logo=apple)](#必要なもの)
[![License](https://img.shields.io/badge/license-Custom-orange?style=for-the-badge)](LICENSE.md)

🌐 **Language / 语言:** [English](README.md) · [简体中文](README.zh-CN.md) · [Español](README.es.md) · [Italiano](README.it.md) · [Tiếng Việt](README.vi.md) · [Français](README.fr.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Português](README.pt-BR.md) · [Türkçe](README.tr.md)

</div>

---

> [!CAUTION]
> **SideInstaller は公式の入手元からのみインストールしてください。**
>
> このプロジェクトはオープンソースです。つまり、誰でもコードを fork し、あなたの Apple ID とパスワードを自分のサーバーに送信する認証情報窃取ツールを仕込み、再ビルドして同じ名前とアイコンで配布できてしまいます。悪意のある fork は、外見上、本物のアプリと見分けがつきません。
>
> 私が公開しているビルドは**以下のものだけ**です。
> - **Web サイト:** https://sideinstaller.net/
> - **リポジトリ:** https://github.com/FrizzleM/SideInstaller
>
> どんなに公式に見えても、他の Web サイト、AltStore のソース、Telegram チャンネル、Discord サーバー、アプリリポジトリ、ミラーから SideInstaller をインストールしないでください。私のビルドを明示的な同意なしに再配布することも[ライセンス](LICENSE.md)で禁じられています。
>
> "sideinstaller.com" という偽サイトがあります。このサイトは**公式ではなく**、マルウェアを配布している可能性があります。**上記の公式の入手元**からのみダウンロードしてください。

> [!NOTE]
> **この fork について — ドキュメントのみの翻訳です。** この fork は、この手順書を翻訳して分かりやすくするためだけに存在します。アプリのバイナリは**一切ビルドも配布もせず**、すべてのダウンロードリンクは上記の公式の入手元を指しています。ここにあるアプリのソースコードは未変更です。実際のアプリは必ず https://sideinstaller.net/ から入手してください。fork、ミラー、再ビルドされた IPA からは入手しないでください。

---

## このページの内容

- [SideInstaller とは](#sideinstaller-とは)
- [必要なもの](#必要なもの)
- [使い方](#使い方)
  - [方法 A — siboot (iOS 27 以降、パソコン不要)](#方法-a--siboot-ios-27-以降パソコン不要)
  - [方法 B — エンタープライズ証明書 (古い iOS)](#方法-b--エンタープライズ証明書-古い-ios)
  - [リンク](#リンク)
  - [ショートカット](#ショートカット)
- [互換性](#互換性)
  - [iOS 26.4 から 26.x: リモートペアリングファイル](#ios-264-から-26x-リモートペアリングファイル)
- [SideInstaller は安全ですか？](#sideinstaller-は安全ですか)
- [プロジェクトの構成](#プロジェクトの構成)
- [プロジェクトへの貢献](#プロジェクトへの貢献)
- [ライセンス](#ライセンス)

---

## SideInstaller とは

SideStore と LiveContainer は、現在 iOS でサイドロードを行うための最良の手段です。しかし、大きな問題がひとつあります。インストールにはパソコンが必要で、多くの人はパソコンを持っていないということです。そこで私は、パソコンなしでこれらを iPhone に直接インストールできる、無料でオープンソースの iOS アプリ、SideInstaller を作りました。

SideInstaller は、設定のすべての処理をデバイス上で行います。通常ならパソコンに接続してデスクトップツールを実行しなければならないペアリング、プロビジョニング、インストールの各手順を、iPhone 上のひとつのアプリだけでこなします。完了すると、自分のアプリをサイドロードできる、完全に動作する SideStore と LiveContainer の環境が手に入ります。

すべてがシンプルになるよう作られています。複雑な設定も、コマンドラインも、仕組みを理解する必要もありません。アプリを開いていくつかの手順に従うだけで、あとはアプリがすべてやってくれます。サイドロードしてみたいけれど Mac も PC も持っていないという人にとって、最大の障壁が取り除かれます。

オープンソースなので、私の言葉をそのまま信じる必要もありません。コードは誰でも読んで監査でき、コントリビューションもできるため、デバイス上で何が動いているのかを正確に確認できます。

## 必要なもの

はじめる前に、以下を用意してください。

- **iPhone または iPad**（**iOS 27 以降**）。iOS 17.4 以降ではパソコンで作成したペアリングファイルが必要で、iOS 26.4 以降は[リモートペアリングファイル](#ios-264-から-26x-リモートペアリングファイル)が必要です。[互換性](#互換性)の表もご覧ください。
- **Wi-Fi**（初回のみ）。
- **デベロッパモード**がオンになっていること（siboot の方法の場合）。
- **Apple アカウントの認証情報** — アプリへの署名にのみデバイス上で使用され、収集されることはありません。

## 使い方

インストール方法は 2 通りあります。お使いの iOS バージョンに合った方法を選んでください。

| 状況 | 方法 | パソコンは必要？ |
| --- | --- | --- |
| iOS 27 以降 | [方法 A — siboot](#方法-a--siboot-ios-27-以降パソコン不要)（推奨） | いいえ |
| iOS 17.4 ～ 26.7、または siboot が使えない場合 | [方法 B — エンタープライズ証明書](#方法-b--エンタープライズ証明書-古い-ios) | はい、初回のみ |

### 方法 A — siboot (iOS 27 以降、パソコン不要)

[siboot](https://github.com/FrizzleM/siboot) を使うと、iPhone 自身から SideInstaller をインストールできます。自分の Apple アカウントで署名されるため、パソコンも証明書も不要です。**iOS 27 以降**、**Wi-Fi**、**デベロッパモードがオン**であることが必要です。Web サイトの [sideinstaller.net](https://sideinstaller.net/) に、手順 1〜3 が図で示されています。

#### 手順 1 — 無料アプリ 3 つをインストール

App Store から次の 3 つすべてをインストールします。

- [rootshell](https://apps.apple.com/app/rootshell-local-terminal-ssh/id6755794662)
- [Open Minis](https://apps.apple.com/app/id6759188481)
- [LocalDevVPN](https://apps.apple.com/app/id6755608044)

#### 手順 2 — rootshell でペアリング

1. rootshell で **設定 › Location Diary Mode › Session Only** をオンにします。
2. **Local Shell** をタップし、右上の **Open** をタップします。
3. 次のコマンドを**1 行ずつ**実行します。

   ```sh
   curl -fsSLO https://raw.githubusercontent.com/FrizzleM/siboot/main/rootshell/bin/siboot-pair.wasm
   ifconfig en0 > ifconfig.txt
   ./siboot-pair.wasm
   ```

4. **設定 › プライバシーとセキュリティ › デベロッパモード**を開き、一番下までスクロールして
   **siboot とペアリング** をタップし、パスコードと rootshell に表示されたコードを入力します。
5. **rootshell を起動したままにしてください** — 閉じないでください。

#### 手順 3 — Open Minis からインストール

1. **LocalDevVPN** に接続します。
2. **Open Minis** で右上のコンソールアイコンをタップし、**Shell Terminal** をタップします。
3. 次を実行します。

   ```sh
   wget -qO- https://raw.githubusercontent.com/FrizzleM/siboot/main/minis/install.sh | sh
   ```

4. rootshell に表示された転送コードを入力します。**初回のみ**です。以降は siboot が保存した
   ペアリングファイルを使います。
5. Apple アカウントの**メールアドレス**、**パスワード**、**確認コード**を入力します。
6. **完了と表示されるまで Minis を開いたままにしてください**。初回は、
   **設定 › 一般 › VPN とデバイス管理**で Apple アカウントを信頼します。

#### 手順 4 — SideInstaller を開く

**LocalDevVPN が接続された状態**で、Apple アカウントでサインインし、**SideStore をインストール** または
**SideStore + LiveContainer をインストール** をタップします。完了です。

> **ペアリング後：** Open Minis で `siboot developer-mode` を実行すると、iPhone に「設定」でデベロッパモードのスイッチを表示するよう求めます。`--turn-on` を付けるとオンにできます。
> 詳しくは[こちら](https://github.com/FrizzleM/siboot/blob/main/minis/README.md#developer-mode)をご覧ください。

### 方法 B — エンタープライズ証明書 (古い iOS)

iOS 27 より前のバージョン、または siboot が使えない場合は、[sideinstaller.net/#legacy](https://sideinstaller.net/#legacy) にあるエンタープライズ証明書のいずれかで SideInstaller をインストールし、
上記の**手順 4**から続けてください。（古い iOS ではペアリングファイルも必要です — [互換性](#互換性)をご覧ください。）

### リンク

SideInstaller は 3 種類の `sideinstaller://` リンクを開き、どのリンクでも処理の前に確認します。

| リンク | 動作 |
| --- | --- |
| `sideinstaller://install?url=<percent-encoded https link to an .ipa>` | IPA をカスタム .ipa としてダウンロードし、インストールします。Web サイトからのワンタップインストール用です。 |
| `sideinstaller://pairingFile?data=<base64 pairing file>` | ペアリングファイルをインポートします。`sidestore://pairing?urlname=sideinstaller` で要求すると SideStore がファイルを送り返します。「ペアリングファイル」カードの **SideStore から取得** がこれを行います。 |
| `sideinstaller://certificate?data=<base64 PKCS#12>&password=<password>` | Apple がその証明書を Apple ID の証明書一覧に表示するようになったら、それ以降 SideInstaller にその証明書で署名させます。 |

**SideStore の証明書を使う**（「既に証明書が存在します」のポップアップと「証明書」ページ）は、
`sidestore://certificate?callback_template=sideinstaller://certificate?data=$(BASE64_CERT)&password=$(PASSWORD)`
（パーセントエンコード）で SideStore 自身の証明書を要求します。これにより、無料の Apple ID の 1 つの証明書を両方のアプリで使えます。この返信だけは再確認しません。SideStore が書き出すかどうかを既に尋ねているためです。

Discord や多くのチャットアプリでは `https://` リンクしかタップ可能にならないため、インストールリンクを投稿するには
`https://sideinstaller.net/open.html?url=<percent-encoded https link to an .ipa>` を使ってください。このページは
IPA のダウンロード元を表示して `sideinstaller://install` に渡し、iOS が自動でアプリを開かない場合のための
ボタンもあります。

### ショートカット

SideInstaller のツールは「ショートカット」アプリのアクションなので、ショートカット、オートメーション、
アクションボタン、Siri から実行できます。

- **位置情報の偽装:** Set Location（地図で選んだ場所、住所、別のアクションから取得した位置）、Set Location to Coordinates、Set Location to Saved Place、Reset Location、Get Spoofed Location、Is Location Spoofed、Play GPX Route、Travel to Place（OpenStreetMap で計画したルートを、徒歩・自転車・車で各道路の制限速度に従って移動）、Stop Route、Save Place、Delete Saved Place。
- **サイドロード済みアプリ:** Get Sideloaded Apps（それぞれの有効期限と残り日数が表示されます）、Refresh All Apps、Refresh App。
- **インストール:** Install App（SideStore、LiveContainer + SideStore、Madeira、AltStore。安定版または Nightly）、Install IPA、Install IPA from URL。これらは SideInstaller を開きます。インストールの途中で確認が必要になることがあるためです。
- **ペアリングとその他:** Get Pairing File、Import Pairing File、Install Pairing File into Apps、Show Developer Mode in Settings、Is LocalDevVPN Connected、Connect LocalDevVPN、Get Activity Log。

ほかのアクションは、アプリ自身のページと同じく LocalDevVPN 経由でバックグラウンドで動作するため、
トンネルが接続されている必要があります。実行前に接続してください（ショートカットの Set VPN アクションでも接続できます）。あるいは SideInstaller の **必要なときに LocalDevVPN を開始** をオンにすると、接続のため SideInstaller での続行が求められます。ショートカットで設定した位置情報は、Reset Location されるまで維持されます。アプリ内で設定したときと同じく、SideInstaller がバックグラウンドで動作し続けて維持します。Siri は “Spoof my location to *saved place* with SideInstaller”、“Reset my location with SideInstaller”、 “Refresh my apps with SideInstaller” を認識します。アクション名は英語で、実行時のメッセージは SideInstaller の言語で表示されます。

## 互換性

| iOS | 互換性 |
| --- | --- |
| 27+ | ✅ はい — siboot ならパソコン不要 |
| 26.4 ～ 26.7 | ⚠️ はい、ただし[リモートペアリングファイルが必要](#ios-264-から-26x-リモートペアリングファイル)で、そのにはパソコンが必要です |
| 17.4 ～ 26.3 | ⚠️ はい、ただし[ペアリングファイルが必要](https://docs.sidestore.io/docs/advanced/alternative#pairing)で、そのにはパソコンが必要です |
| <17.4 | ❌ いいえ |

### iOS 26.4 から 26.x: リモートペアリングファイル

iOS 26.4 以降では、lockdown 形式のペアリングファイル（jitterbugpair、`pymobiledevice3 lockdown pair`、idevice_pair の **Lockdown** で作ったもの）は、LocalDevVPN を経由して接続した瞬間に iPhone に切断されます。そのため、どんなに新しい形式でも iPhone 上では使えません。リモートペアリング（RPPairing）ファイルは今でも動作します。

1. Mac、Windows パソコン、または Linux コンピュータで [idevice_pair](https://github.com/jkcoxson/idevice_pair/releases/latest) を開き、iPhone を接続します。求められたら **信頼** をタップします。
2. iPhone を選択し、**Remote pairing** を選んで **Create** をクリックし、完了まで iPhone のロックを解除したままにします。
3. **Save to file…** をクリックし、AirDrop、iCloud Drive、またはケーブルでファイルを iPhone に送ります。
4. SideInstaller で **ペアリングファイルをインポート**（または **置き換え**）をタップし、そのファイルを選びます。

[iLoader](https://github.com/nab138/iloader) から書き出したペアリングファイル（**Manage Pairing File** ›
**Export**）は両方の形式を含んでいるため、こちらも使えます。

## SideInstaller は安全ですか？

SideInstaller は安全性とプライバシーを念頭に作られています。アプリは完全にローカルで動作し、オープンソースなので、誰でもその動作を正確に確認できます。

**Apple の認証情報がデバイスから外に出ることはありません。** アプリへの署名とインストールにのみデバイス上で使用され、送信・記録・収集されることは一切ありません。

**サーバーなし、解析なし、アカウントなし。** 収集されるものはなく、登録するものもありません。

**完全に監査可能。** すべての行をソースコードで確認できます。

> [!WARNING]
> 上記はすべて**この**リポジトリと、ここから公開されたビルドに当てはまります。fork、再署名された IPA、
> 或いは他の場所で見つけたコピーには当ては**かりません**。そうしたものは、入力した Apple ID を盗むように
> 改変されている可能性があります。https://sideinstaller.net/ 以外から入手した場合は、
> 認証情報を預けないでください。

## プロジェクトの構成

| パス | 内容 |
| :-- | :-- |
| `ios-app/` | SwiftUI アプリ — UI、インストールエンジン、証明書の処理、翻訳 |
| `ios-live-activity/` | ペアリングコードを Dynamic Island とロック画面に表示するウィジェット拡張 |
| `ios-tests/` | アプリのユニットテスト（`SideInstallerTests`） |
| `rust-core/` | `SideInstallerFFI.xcframework` にコンパイルされる Rust コア |
| `scripts/` | ビルド、チェック、リリース用のスクリプト |
| `.github/` | プルリクエストのチェック、未署名 IPA のビルド、リリースとしての公開、署名者への受け渡しを行うワークフロー |

署名済みビルドとインストールページは [FrizzleM/SideInstaller-Signed](https://github.com/FrizzleM/SideInstaller-Signed) にあります。ここでは、各リリースの IPA をすべての証明書で署名し、署名済み IPA を独自のリリースに添付して [sideinstaller.net](https://sideinstaller.net/) をデプロイします。どちらのリポジトリにも IPA はコミットされません。

siboot は SideInstaller を[iPhone 自身からインストールする](#使い方)仕組みで、
[FrizzleM/siboot](https://github.com/FrizzleM/siboot) にあります。ここでは、1 つのコミットに固定されたサブモジュールを通して、このリポジトリに同梱された Rust crates と rust-core の `apple_session.rs` と `error_text.rs` をビルドします。そのため、ここでの変更は、その固定が更新されない限り siboot には反映されません。

## プロジェクトへの貢献

Issue とプルリクエストは歓迎します。バグを報告する場合は、iOS のバージョン、アプリのバージョン、失敗した手順を記載してください。

すべてのプルリクエストは `checks` ワークフローでチェックされます。Rust のテストと clippy、アプリのユニットテストを伴うシミュレータビルド、そして翻訳（アプリに文字列を追加した場合、各 `ios-app/*Strings.swift` にエントリが必要です）です。同じチェックは Mac 上でも `scripts/test-rust.sh`、`scripts/check-ios.sh`（Xcode プロジェクトを生成するため、クリーンなクローンで実行してください）、`scripts/check_translations.py` で実行できます。

## ライセンス

[LICENSE.md](LICENSE.md) をご覧ください。簡単に言えば、**ソースコード**は、出典を明記し、非営利目的であれば読む、変更する、共有することができます。公式ビルド（IPA）の再配布や、プロジェクトをいかなる形式で収益化することにも書面による許可が必要です。

<div align="center">

**SideInstaller — [FrizzleM](https://github.com/FrizzleM) 制作** · この fork のドキュメント翻訳はコミュニティの貢献によるものです。アプリの著作権は FrizzleM にあります。

</div>
