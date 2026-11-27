<div align="center">

<img src="app-icon.png" alt="SideInstaller" width="120" />

# SideInstaller

**PC 없이 iPhone에 SideStore와 LiveContainer를 바로 설치하세요.**

[![Install](https://img.shields.io/badge/Install-SideInstaller-2ea44f?style=for-the-badge)](https://sideinstaller.net/)
[![Version](https://img.shields.io/badge/version-2.2.0-2669ed?style=for-the-badge)](CHANGELOG.md)
[![Platform](https://img.shields.io/badge/platform-iOS-lightgrey?style=for-the-badge&logo=apple)](#요구-사항)
[![License](https://img.shields.io/badge/license-Custom-orange?style=for-the-badge)](LICENSE.md)

🌐 **Language / 语言:** [English](README.md) · [简体中文](README.zh-CN.md) · [Español](README.es.md) · [Italiano](README.it.md) · [Tiếng Việt](README.vi.md) · [Français](README.fr.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Português](README.pt-BR.md) · [Türkçe](README.tr.md)

</div>

---

> [!CAUTION]
> **SideInstaller는 반드시 공식 출처에서만 설치하세요.**
>
> 이 프로젝트는 오픈 소스이므로 누구나 코드를 포크해 Apple ID와 암호를 자기 서버로 업로드하는 자격 증명 탈취 코드를 삽입하고, 다시 빌드해 같은 이름과 아이콘으로 배포할 수 있습니다. 악의적인 포크는 겉모습만 봐서는 진짜 앱과 똑같습니다.
>
> 제가 게시하는 빌드는 **다음뿐입니다**:
> - **웹사이트:** https://sideinstaller.net/
> - **저장소:** https://github.com/FrizzleM/SideInstaller
>
> 아무리 공식적으로 보여도 다른 사이트, AltStore 소스, Telegram 채널, Discord 서버, 앱 저장소 또는 미러에서 SideInstaller를 설치하지 마세요. 명시적인 동의 없이 제 빌드를 재배포하는 것도 [라이선스](LICENSE.md)에 따라 금지됩니다.
>
> "sideinstaller.com"이라는 가짜 사이트가 있습니다. 이 사이트는 **정식이 아니며** 악성코드를 제공할 가능성이 큽니다. 반드시 위에 나열된 **공식 출처**에서만 다운로드하세요.

> [!NOTE]
> **이 포크에 대해 — 문서 번역 전용.** 이 포크는 이 안내문을 번역하고 명확하게 하기 위해서만 존재합니다. 앱 바이너리는 **전혀 빌드하거나 배포하지 않으며**, 모든 다운로드 링크는 여전히 위의 공식 출처를 가리킵니다. 여기에 있는 앱 소스 코드는 수정되지 않았습니다. 실제 앱은 항상 https://sideinstaller.net/ 에서 받으세요. 포크, 미러 또는 재서명한 IPA에서는 절대 받지 마세요.

---

## 이 페이지에서

- [어떤 앱인가요](#어떤-앱인가요)
- [요구 사항](#요구-사항)
- [사용 방법](#사용-방법)
  - [방법 A — siboot (iOS 27 이상, PC 불필요)](#방법-a--siboot-ios-27-이상-pc-불필요)
  - [방법 B — 기업 인증서 (구버전 iOS)](#방법-b--기업-인증서-구버전-ios)
  - [링크](#링크)
  - [단축어](#단축어)
- [호환성](#호환성)
  - [iOS 26.4에서 26.x까지: 원격 페어링 파일](#ios-264에서-26x까지-원격-페어링-파일)
- [SideInstaller는 안전한가요?](#sideinstaller는-안전한가요)
- [프로젝트 구조](#프로젝트-구조)
- [기여하기](#기여하기)
- [라이선스](#라이선스)

---

## 어떤 앱인가요

SideStore와 LiveContainer는 현재 iOS에서 사이드로드하는 가장 좋은 방법입니다. 그러나 큰 문제가 하나 있습니다. 설치하려면 PC가 필요하고, 많은 사람이 PC를 가지고 있지 않다는 점입니다. 그래서 PC 없이 iPhone에 두 앱을 바로 설치해 주는 무료 오픈 소스 iOS 앱, SideInstaller를 만들었습니다.

SideInstaller는 설치 과정을 모두 기기 안에서 처리합니다. 평소라면 컴퓨터에 연결해 데스크톱 도구를 실행해야 하는 페어링, 프로비저닝, 설치 단계를 휴대폰에서 실행되는 앱 하나로 모두 해결합니다. 끝나면 직접 만든 앱을 사이드로드할 수 있도록 완전히 작동하는 SideStore와 LiveContainer 환경이 준비됩니다.

전체를 단순하게 만들었습니다. 복잡한 설정도, 명령줄도, 내부 동작 원리를 이해할 필요도 없습니다. 앱을 열고 몇 단계를 따라 한 뒤 나머지는 앱에 맡기면 됩니다. Mac이나 PC 없이 사이드로드를 하고 싶었지만 시작할 수 없었던 사람에게 가장 큰 장벽을 없애 줍니다.

오픈 소스이므로 제 말을 그대로 믿을 필요도 없습니다. 전체 코드를 누구나 읽고 감사하거나 기여할 수 있어, 기기에서 정확히 무엇이 실행되는지 확인할 수 있습니다.

## 요구 사항

시작하기 전에 다음을 준비하세요:

- **iPhone 또는 iPad** (iOS 27 이상) — iOS 17.4 이상에서는 컴퓨터에서 만든 페어링 파일이 있으면 사용할 수 있고, iOS 26.4부터는 [원격 페어링 파일](#ios-264에서-26x까지-원격-페어링-파일)이 필요합니다. [호환성 표](#호환성)를 참고하세요.
- **Wi-Fi** (처음 한 번만 필요).
- **개발자 모드** 켜기 (siboot 방식).
- **Apple 계정 자격 증명** — 앱 서명에만 기기 안에서 사용하며, 수집하지 않습니다.

## 사용 방법

두 가지 설치 방법이 있습니다. iOS 버전에 맞는 방법을 선택하세요:

| 상황 | 방법 | PC 필요? |
| --- | --- | --- |
| iOS 27 이상 | [방법 A — siboot](#방법-a--siboot-ios-27-이상-pc-불필요) (권장) | 아니요 |
| iOS 17.4 – 26.7, 또는 siboot이 작동하지 않는 경우 | [방법 B — 기업 인증서](#방법-b--기업-인증서-구버전-ios) | 예, 한 번만 |

### 방법 A — siboot (iOS 27 이상, PC 불필요)

[siboot](https://github.com/FrizzleM/siboot)은 iPhone 자체에서 SideInstaller를 설치하며, 사용자의 Apple 계정으로 서명합니다. 컴퓨터도 인증서도 필요 없습니다. **iOS 27 이상**, **Wi-Fi**, **개발자 모드 켜짐**이 필요합니다. [sideinstaller.net](https://sideinstaller.net/) 웹사이트에서 1~3단계를 화면으로 보여 줍니다.

#### 1단계 — 무료 앱 3개 설치

App Store에서 세 앱을 모두 설치하세요:

- [rootshell](https://apps.apple.com/app/rootshell-local-terminal-ssh/id6755794662)
- [Open Minis](https://apps.apple.com/app/id6759188481)
- [LocalDevVPN](https://apps.apple.com/app/id6755608044)

#### 2단계 — rootshell에서 페어링

1. rootshell에서 **설정 › 위치 일기 모드 › 세션 전용**을 켜세요.
2. **Local Shell**을 탭한 다음 오른쪽 위의 **Open**을 탭하세요.
3. 다음 명령을 **한 줄씩** 실행하세요:

   ```sh
   curl -fsSLO https://raw.githubusercontent.com/FrizzleM/siboot/main/rootshell/bin/siboot-pair.wasm
   ```

   ```sh
   ifconfig en0 > ifconfig.txt
   ```

   ```sh
   ./siboot-pair.wasm
   ```

4. **설정 › 개인정보 보호 및 보안 › 개발자 모드**를 열고 맨 아래로 스크롤한 뒤 **siboot과 페어링**을 탭하고, 암호와 rootshell이 표시하는 코드를 입력하세요.
5. **rootshell을 실행한 상태로 두세요** — 닫지 마세요.

#### 3단계 — Open Minis에서 설치

1. **LocalDevVPN**을 연결하세요.
2. **Open Minis**에서 오른쪽 위의 콘솔 아이콘을 탭한 다음 **Shell Terminal**을 탭하세요.
3. 다음을 실행하세요:

   ```sh
   wget -qO- https://raw.githubusercontent.com/FrizzleM/siboot/main/minis/install.sh | sh
   ```

4. rootshell이 표시하는 전송 코드를 입력하세요. **처음 한 번만** 필요하며, 그 이후에는 siboot이 저장한 페어링 파일을 사용합니다.
5. Apple 계정의 **이메일**, **암호**, **인증 코드**를 입력하세요.
6. 완료되었다고 표시될 때까지 **Minis를 열어 두세요**. 처음에는 **설정 › 일반 › VPN 및 기기 관리**에서 Apple 계정을 신뢰하세요.

#### 4단계 — SideInstaller 열기

**LocalDevVPN이 연결된 상태에서** Apple 계정으로 로그인하고 **SideStore 설치** 또는 **SideStore + LiveContainer 설치**를 탭하세요. 끝입니다.

> **페어링 후:** Open Minis에서 `siboot developer-mode`를 실행하면 iPhone이 설정에 개발자 모드 스위치를 표시하도록 요청하며, `--turn-on`을 추가하면 켜집니다. 자세한 내용은 [관련 문서](https://github.com/FrizzleM/siboot/blob/main/minis/README.md#developer-mode)를 참고하세요.

### 방법 B — 기업 인증서 (구버전 iOS)

iOS 27 이전 버전이거나 siboot이 작동하지 않는 경우, [sideinstaller.net/#legacy](https://sideinstaller.net/#legacy)의 기업 인증서 중 하나로 SideInstaller를 설치한 뒤 위의 **4단계**부터 진행하세요. (구버전에서는 페어링 파일도 필요합니다 — [호환성](#호환성) 참고.)

### 링크

SideInstaller는 세 가지 종류의 `sideinstaller://` 링크를 열며, 어떤 링크든 실행하기 전에 확인을 요청합니다:

| 링크 | 동작 |
| --- | --- |
| `sideinstaller://install?url=<percent-encoded https link to an .ipa>` | IPA를 사용자 지정 .ipa로 다운로드해 설치합니다. 웹사이트에서 한 번의 탭으로 설치할 때 사용합니다. |
| `sideinstaller://pairingFile?data=<base64 pairing file>` | 페어링 파일을 가져옵니다. `sidestore://pairing?urlname=sideinstaller`로 요청하면 SideStore가 페어링 파일을 돌려보냅니다. 페어링 파일 카드의 **SideStore에서 가져오기**가 바로 이 동작을 합니다. |
| `sideinstaller://certificate?data=<base64 PKCS#12>&password=<password>` | Apple이 해당 인증서를 Apple ID의 인증서 목록에 표시하면, 이후부터 SideInstaller가 그 인증서로 서명하도록 합니다. |

**SideStore의 인증서 사용**("인증서가 이미 있습니다" 팝업과 인증서 페이지)은 다음과 같이 SideStore에 자체 인증서를 요청합니다: `sidestore://certificate?callback_template=sideinstaller://certificate?data=$(BASE64_CERT)&password=$(PASSWORD)` (퍼센트 인코딩). 따라서 무료 Apple ID의 인증서 하나로 두 앱 모두 서명할 수 있습니다. 이 응답 링크만 다시 확인을 요청하지 않습니다. SideStore가 방금 내보낼지 물었기 때문입니다.

Discord와 대부분의 채팅 앱은 `https://` 링크만 탭할 수 있으므로, 설치 링크를 올리려면 `https://sideinstaller.net/open.html?url=<percent-encoded https link to an .ipa>`를 사용하세요. 이 페이지는 IPA의 다운로드 출처를 보여 주고 `sideinstaller://install`로 전달하며, iOS가 앱을 자동으로 열지 않을 때 누를 수 있는 버튼도 있습니다.

### 단축어

SideInstaller의 도구는 단축어 앱의 동작이므로 단축어, 자동화, 동작 버튼 또는 Siri로 실행할 수 있습니다:

- **위치 변경:** Set Location(지도에서 고른 장소, 주소 또는 다른 동작의 위치), Set Location to Coordinates, Set Location to Saved Place, Reset Location, Get Spoofed Location, Is Location Spoofed, Play GPX Route, Travel to Place(OpenStreetMap으로 계획한 경로를 각 도로의 제한 속도로 걷거나, 자전거 또는 자동차로 이동), Stop Route, Save Place, Delete Saved Place.
- **사이드로드한 앱:** Get Sideloaded Apps(각 앱의 만료일과 남은 일수 표시), Refresh All Apps, Refresh App.
- **설치:** Install App(SideStore, LiveContainer + SideStore, Madeira 또는 AltStore, stable 또는 nightly), Install IPA, Install IPA from URL. 설치 도중 SideInstaller에서 확인이 필요할 수 있으므로 이 동작들은 SideInstaller를 엽니다.
- **페어링 및 기타:** Get Pairing File, Import Pairing File, Install Pairing File into Apps, Show Developer Mode in Settings, Is LocalDevVPN Connected, Connect LocalDevVPN, Get Activity Log.

나머지 동작은 앱 자체 화면과 마찬가지로 LocalDevVPN을 통해 백그라운드에서 실행되므로 터널이 연결되어 있어야 합니다. 먼저 연결하세요(단축어의 Set VPN 동작으로 가능). 또는 **필요할 때 LocalDevVPN 시작**을 켜면 동작이 SideInstaller로 이동해 연결을 요청합니다. 단축어로 설정한 위치는 Reset Location을 누를 때까지 유지됩니다. 앱에서 위치를 설정할 때처럼 SideInstaller가 백그라운드에서 계속 실행되며 위치를 유지합니다. Siri는 "Spoof my location to *saved place* with SideInstaller", "Reset my location with SideInstaller", "Refresh my apps with SideInstaller"를 인식합니다. 동작 이름은 영어이고, 실행할 때 표시되는 문구는 SideInstaller의 언어입니다.

## 호환성

| iOS | 호환되나요? |
| --- | --- |
| 27 이상 | ✅ 예 — siboot을 사용하면 PC가 필요 없습니다 |
| 26.4 – 26.7 | ⚠️ 예, 하지만 [원격 페어링 파일이 필요](#ios-264에서-26x까지-원격-페어링-파일)하며 PC가 필요합니다 |
| 17.4 – 26.3 | ⚠️ 예, 하지만 [페어링 파일이 필요](https://docs.sidestore.io/docs/advanced/alternative#pairing)하며 PC가 필요합니다 |
| 17.4 미만 | ❌ 아니요 |

### iOS 26.4에서 26.x까지: 원격 페어링 파일

iOS 26.4부터 iPhone은 lockdown 페어링 파일(jitterbugpair, `pymobiledevice3 lockdown pair` 또는 idevice_pair의 **Lockdown**으로 만든 파일)이 LocalDevVPN을 통해 연결되자마자 연결을 끊습니다. 따라서 아무리 새로 만들어도 iPhone에서 사용할 수 없습니다. 원격 페어링(RPPairing) 파일은 계속 작동합니다:

1. Mac, Windows PC 또는 Linux 컴퓨터에서 [idevice_pair](https://github.com/jkcoxson/idevice_pair/releases/latest)를 열고 iPhone을 연결하세요. 요청이 표시되면 **Trust**를 탭하세요.
2. iPhone을 선택하고 **Remote pairing**을 고른 다음 **Create**를 클릭하세요. 완료될 때까지 iPhone의 잠금을 해제한 상태로 두세요.
3. **Save to file…**을 클릭하고 AirDrop, iCloud Drive 또는 케이블로 iPhone에 파일을 보내세요.
4. SideInstaller에서 **페어링 파일 가져오기**(또는 **교체**)를 탭한 뒤 해당 파일을 선택하세요.

[iLoader](https://github.com/nab138/iloader)에서 내보낸 페어링 파일(**Manage Pairing File** › **Export**)도 두 종류를 모두 포함하고 있으며 작동합니다.

## SideInstaller는 안전한가요?

SideInstaller는 안전과 개인정보 보호를 염두에 두고 만들었습니다. 앱은 전적으로 로컬에서 작동하고 오픈 소스이므로 누구나 정확히 무엇을 하는지 살펴볼 수 있습니다.

**Apple 자격 증명은 기기에서 나가지 않습니다.** 앱 서명과 설치에만 로컬로 사용되며, 전송되거나 기록되거나 수집되지 않습니다.

**서버 없음, 분석 없음, 계정 없음.** 수집되는 것은 없으며 가입할 것도 없습니다.

**완전히 감사 가능.** 모든 코드를 소스에서 확인할 수 있습니다.

> [!WARNING]
> 위의 모든 내용은 **이** 저장소와 여기서 게시한 빌드에 해당합니다. 포크, 재서명한 IPA 또는 다른 곳에서 찾은 사본에 적용되는 보장이 **아닙니다**. 그런 앱은 입력한 Apple ID를 훔치도록 수정되었을 수 있습니다. https://sideinstaller.net/ 에서 받지 않았다면 자격 증명을 맡기지 마세요.

## 프로젝트 구조

| 경로 | 내용 |
| :-- | :-- |
| `ios-app/` | SwiftUI 앱 — UI, 설치 엔진, 인증서 처리, 번역 |
| `ios-live-activity/` | 페어링 코드를 다이내믹 아일랜드와 잠금 화면에 표시하는 위젯 확장 |
| `ios-tests/` | 앱의 단위 테스트(`SideInstallerTests`) |
| `rust-core/` | `SideInstallerFFI.xcframework`로 컴파일되는 Rust 코어 |
| `scripts/` | 빌드, 검사, 릴리즈 스크립트 |
| `.github/` | 풀 리퀘스트 검사, 서명되지 않은 IPA 빌드, 릴리즈 게시 및 서명자에게 전달하는 워크플로 |

서명된 빌드와 설치 페이지는 [FrizzleM/SideInstaller-Signed](https://github.com/FrizzleM/SideInstaller-Signed)에 있습니다: 이 저장소는 각 릴리즈의 IPA를 모든 인증서로 서명하고 서명된 IPA를 자체 릴리즈에 첨부하며 [sideinstaller.net](https://sideinstaller.net/)을 배포합니다. 두 저장소 모두 IPA를 커밋하지 않습니다.

[iPhone 자체에서 SideInstaller를 설치하는](#사용-방법) siboot은 [FrizzleM/siboot](https://github.com/FrizzleM/siboot)에 있습니다. 이 저장소에 포함된 crates와 rust-core의 `apple_session.rs`, `error_text.rs`를 특정 커밋에 고정된 서브모듈을 통해 빌드하므로, 여기서 변경한 내용은 그 고정 커밋이 움직일 때만 siboot에 반영됩니다.

## 기여하기

이슈와 풀 리퀘스트를 환영합니다. 버그를 신고할 때는 iOS 버전, 앱 버전, 실패한 단계를 함께 적어 주세요.

모든 풀 리퀘스트는 `checks` 워크플로로 검사됩니다: Rust 테스트와 clippy, 앱 단위 테스트를 포함한 시뮬레이터 빌드, 번역 검사(앱에 문자열을 추가하면 각 `ios-app/*Strings.swift`에 항목이 있어야 함). 같은 검사를 Mac에서 `scripts/test-rust.sh`, `scripts/check-ios.sh`(Xcode 프로젝트를 생성하므로 깨끗한 클론에서 실행하세요), `scripts/check_translations.py`로 실행할 수 있습니다.

## 라이선스

[LICENSE.md](LICENSE.md)를 참고하세요. 요약하면 출처를 밝히고 비상업적 목적으로 **소스**를 읽고, 수정하고, 공유할 수 있습니다. 공식 빌드(IPAs)를 재배포하거나 어떤 형태로든 프로젝트를 수익화하려면 서면 허가가 필요합니다.

<div align="center">

**SideInstaller by [FrizzleM](https://github.com/FrizzleM)** · 이 포크의 문서 번역은 커뮤니티 기여이며, 앱은 © FrizzleM입니다.

</div>
