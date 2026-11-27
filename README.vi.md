<div align="center">

<img src="app-icon.png" alt="SideInstaller" width="120" />

<a id="doc-h1" name="doc-h1"></a>
# SideInstaller

**Cài đặt SideStore và LiveContainer ngay trên iPhone của bạn — không cần máy tính.**

[![Install](https://img.shields.io/badge/Install-SideInstaller-2ea44f?style=for-the-badge)](https://sideinstaller.net/)
[![Version](https://img.shields.io/badge/version-2.2.0-2669ed?style=for-the-badge)](CHANGELOG.md)
[![Platform](https://img.shields.io/badge/platform-iOS-lightgrey?style=for-the-badge&logo=apple)](#doc-h4)
[![License](https://img.shields.io/badge/license-Custom-orange?style=for-the-badge)](LICENSE.md)

🌐 **Language / 语言:** [English](README.md) · [简体中文](README.zh-CN.md) · [Español](README.es.md) · [Italiano](README.it.md) · [Tiếng Việt](README.vi.md) · [Français](README.fr.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Português](README.pt-BR.md) · [Türkçe](README.tr.md)

</div>

---

> [!CAUTION]
> **Chỉ cài đặt SideInstaller từ nguồn chính thức.**
>
> Dự án này là mã nguồn mở, nghĩa là bất kỳ ai cũng có thể fork mã, chèn mã đánh cắp thông tin
> đăng nhập để tải Apple ID và mật khẩu của bạn lên máy chủ của riêng họ, dựng lại rồi phát hành lại với
> cùng tên và biểu tượng. Một fork độc hại trông bên ngoài giống hệt ứng dụng thật.
>
> **Những** bản dựng duy nhất tôi phát hành là:
> - **Trang web:** https://sideinstaller.net/
> - **Kho mã:** https://github.com/FrizzleM/SideInstaller
>
> Đừng cài SideInstaller từ bất kỳ trang web, nguồn AltStore, kênh Telegram, máy chủ Discord,
> kho ứng dụng hay bản mirror nào khác, dù trông có vẻ chính thức đến đâu. Việc phát hành lại các bản dựng của tôi mà không có sự đồng ý rõ ràng cũng bị
> [giấy phép](LICENSE.md) cấm.
>
> Có một trang web giả mạo tên là "sideinstaller.com". Trang này **không hợp lệ** và rất có thể đang phát tán phần mềm độc hại. Hãy đảm bảo
> bạn chỉ tải từ **nguồn chính thức** được liệt kê ở trên.

> [!NOTE]
> **Về fork này — chỉ là tài liệu.** Fork này chỉ tồn tại để dịch và làm rõ các
> hướng dẫn này. Nó không build hay phát hành **bản nhị phân ứng dụng nào**; mọi liên kết tải xuống vẫn trỏ tới
> các nguồn chính thức ở trên. Mã nguồn ứng dụng ở đây không bị sửa đổi. Luôn lấy ứng dụng thật từ
> https://sideinstaller.net/ — không bao giờ từ fork, mirror hay IPA được dựng lại.

---

<a id="doc-h2" name="doc-h2"></a>
## Nội dung trang này

- [SideInstaller là gì](#doc-h3)
- [Yêu cầu](#doc-h4)
- [Cách sử dụng](#doc-h5)
  - [Phương pháp A — siboot (iOS 27+, không cần PC)](#doc-h6)
  - [Phương pháp B — chứng chỉ doanh nghiệp (iOS cũ hơn)](#doc-h11)
  - [Liên kết](#doc-h12)
  - [Phím tắt](#doc-h13)
- [Khả năng tương thích](#doc-h14)
  - [iOS 26.4 đến 26.x: tệp ghép nối từ xa](#doc-h15)
- [SideInstaller có an toàn không?](#doc-h16)
- [Cấu trúc dự án](#doc-h17)
- [Đóng góp](#doc-h18)
- [Giấy phép](#doc-h19)

---

<a id="doc-h3" name="doc-h3"></a>
## SideInstaller là gì

SideStore và LiveContainer hiện là cách tốt nhất để sideload trên iOS. Tuy nhiên, có một
vấn đề lớn: cài đặt chúng cần một máy tính, mà nhiều người không có. Đó là lý do tôi tạo SideInstaller,
một ứng dụng iOS miễn phí và mã nguồn mở cài đặt chúng trực tiếp trên iPhone của bạn, không cần máy tính.

SideInstaller lo toàn bộ quá trình thiết lập ngay trên thiết bị. Ứng dụng đảm nhận các bước ghép nối, cấp phép và
cài đặt mà thông thường bắt buộc bạn phải cắm vào máy tính và chạy các công cụ trên máy tính để bàn — tất cả từ một
ứng dụng chạy ngay trên điện thoại. Khi hoàn tất, bạn có bản thiết lập SideStore và LiveContainer hoạt động đầy đủ,
sẵn sàng để sideload các ứng dụng của riêng bạn.

Mọi thứ được xây dựng để đơn giản. Không có cấu hình phức tạp, không dùng dòng lệnh, và không cần
hiểu cách hoạt động của các cơ chế bên trong. Bạn chỉ mở ứng dụng, làm theo vài bước rồi để
ứng dụng lo phần còn lại. Với bất kỳ ai từng muốn sideload nhưng không có Mac hay PC, đây là cách
xoá bỏ rào cản lớn nhất để bắt đầu.

Và vì là mã nguồn mở, bạn không phải chỉ tin lời tôi. Toàn bộ mã nguồn đều có sẵn cho
bất kỳ ai đọc, kiểm tra hoặc đóng góp, nên bạn có thể thấy chính xác thứ đang chạy trên thiết bị của mình.

<a id="doc-h4" name="doc-h4"></a>
## Yêu cầu

Trước khi bắt đầu, hãy đảm bảo bạn có:

- **iPhone hoặc iPad** chạy **iOS 27+** — trên iOS 17.4+ cần có tệp ghép nối tạo trên máy tính; từ
  iOS 26.4 cần [tệp ghép nối từ xa](#doc-h15). Xem
  [bảng tương thích](#doc-h14).
- **Wi-Fi** (chỉ lần đầu).
- **Chế độ nhà phát triển** đã bật (đối với phương pháp siboot).
- **Thông tin tài khoản Apple của bạn** — chỉ dùng trên thiết bị để ký ứng dụng; không bao giờ bị thu thập.

<a id="doc-h5" name="doc-h5"></a>
## Cách sử dụng

Có hai phương pháp cài đặt. Hãy chọn phương pháp phù hợp với phiên bản iOS của bạn:

| Tình huống của bạn | Phương pháp | Cần PC? |
| --- | --- | --- |
| iOS 27 trở lên | [Phương pháp A — siboot](#doc-h6) (khuyến nghị) | Không |
| iOS 17.4 – 26.7, hoặc siboot không hoạt động với bạn | [Phương pháp B — chứng chỉ doanh nghiệp](#doc-h11) | Có, một lần |

<a id="doc-h6" name="doc-h6"></a>
### Phương pháp A — siboot (iOS 27+, không cần PC)

[siboot](https://github.com/FrizzleM/siboot) cài SideInstaller ngay từ iPhone, được ký bằng
tài khoản Apple của chính bạn: không cần máy tính cũng không cần chứng chỉ. Bạn cần **iOS 27 trở lên**,
**Wi-Fi** và **Chế độ nhà phát triển đang bật**. Trang web [sideinstaller.net](https://sideinstaller.net/) trình bày trực quan
các bước 1 đến 3.

<a id="doc-h7" name="doc-h7"></a>
#### Bước 1 — Cài ba ứng dụng miễn phí

Cài cả ba từ App Store:

- [rootshell](https://apps.apple.com/app/rootshell-local-terminal-ssh/id6755794662)
- [Open Minis](https://apps.apple.com/app/id6759188481)
- [LocalDevVPN](https://apps.apple.com/app/id6755608044)

<a id="doc-h8" name="doc-h8"></a>
#### Bước 2 — Ghép nối trong rootshell

1. Trong rootshell, bật **Cài đặt › Nhật ký vị trí › Chỉ phiên**.
2. Nhấn **Local Shell**, rồi nhấn **Open** ở góc trên bên phải.
3. Chạy các lệnh sau **từng dòng một**:

   ```sh
   curl -fsSLO https://raw.githubusercontent.com/FrizzleM/siboot/main/rootshell/bin/siboot-pair.wasm
   ifconfig en0 > ifconfig.txt
   ./siboot-pair.wasm
   ```

4. Mở **Cài đặt › Quyền riêng tư & Bảo mật › Chế độ nhà phát triển**, cuộn xuống cuối, nhấn
   **Ghép nối với siboot**, rồi nhập mật mã và mã mà rootshell hiển thị.
5. **Giữ rootshell chạy** — đừng đóng ứng dụng.

<a id="doc-h9" name="doc-h9"></a>
#### Bước 3 — Cài từ Open Minis

1. Kết nối **LocalDevVPN**.
2. Trong **Open Minis**, nhấn biểu tượng bảng điều khiển ở góc trên bên phải, rồi nhấn **Shell Terminal**.
3. Chạy:

   ```sh
   wget -qO- https://raw.githubusercontent.com/FrizzleM/siboot/main/minis/install.sh | sh
   ```

4. Nhập mã chuyển tiếp mà rootshell hiển thị — **chỉ lần đầu**; sau đó, siboot dùng tệp ghép nối
   đã lưu.
5. Nhập **email**, **mật khẩu** và **mã xác minh** của tài khoản Apple.
6. **Giữ Minis mở** cho đến khi báo hoàn tất. Lần đầu, hãy tin cậy tài khoản Apple của bạn trong
   **Cài đặt › Cài đặt chung › VPN & Quản lý thiết bị**.

<a id="doc-h10" name="doc-h10"></a>
#### Bước 4 — Mở SideInstaller

Khi **LocalDevVPN đã kết nối**, đăng nhập bằng tài khoản Apple của bạn và nhấn **Cài đặt SideStore** hoặc
**Cài đặt SideStore + LiveContainer**. Xong.

> **Sau khi ghép nối:** chạy `siboot developer-mode` trong Open Minis yêu cầu iPhone hiển thị công tắc Chế độ nhà phát triển
> trong Cài đặt; thêm `--turn-on` để bật nó. Xem
> [chi tiết](https://github.com/FrizzleM/siboot/blob/main/minis/README.md#developer-mode).

<a id="doc-h11" name="doc-h11"></a>
### Phương pháp B — chứng chỉ doanh nghiệp (iOS cũ hơn)

Trên các phiên bản iOS trước 27, hoặc nếu siboot không hoạt động với bạn, hãy cài SideInstaller bằng một trong các
chứng chỉ doanh nghiệp tại [sideinstaller.net/#legacy](https://sideinstaller.net/#legacy), rồi tiếp tục
từ **Bước 4** ở trên. (Các phiên bản cũ cũng cần tệp ghép nối — xem [Khả năng tương thích](#doc-h14).)

<a id="doc-h12" name="doc-h12"></a>
### Liên kết

SideInstaller mở ba loại liên kết `sideinstaller://` và luôn hỏi trước khi thực hiện bất kỳ liên kết nào:

| Liên kết | Chức năng |
| --- | --- |
| `sideinstaller://install?url=<percent-encoded https link to an .ipa>` | Tải IPA về dưới dạng .ipa tùy chọn rồi cài đặt — dành cho cài đặt một chạm từ trang web. |
| `sideinstaller://pairingFile?data=<base64 pairing file>` | Nhập tệp ghép nối. SideStore gửi lại một tệp khi được yêu cầu qua `sidestore://pairing?urlname=sideinstaller` — đó là việc **Lấy từ SideStore** trên thẻ Tệp ghép nối. |
| `sideinstaller://certificate?data=<base64 PKCS#12>&password=<password>` | Khiến SideInstaller ký bằng chứng chỉ đó từ nay về sau, sau khi Apple liệt kê chứng chỉ đó trong các chứng chỉ của Apple ID của bạn. |

**Dùng chứng chỉ của SideStore** (trong hộp thoại "Đã có một chứng chỉ" và trên trang Chứng chỉ)
yêu cầu SideStore gửi chứng chỉ của nó qua
`sidestore://certificate?callback_template=sideinstaller://certificate?data=$(BASE64_CERT)&password=$(PASSWORD)`
(đã mã hóa phần trăm), để một chứng chỉ của Apple ID miễn phí phục vụ cả hai ứng dụng. Phản hồi đó là liên kết duy nhất
không hỏi lại: SideStore vừa hỏi xem có xuất chứng chỉ hay không.

Discord và hầu hết các ứng dụng trò chuyện chỉ cho liên kết `https://` có thể nhấn, nên để đăng liên kết cài đặt ở đó hãy dùng
`https://sideinstaller.net/open.html?url=<percent-encoded https link to an .ipa>`. Trang đó hiển thị
nguồn tải IPA và chuyển nó cho `sideinstaller://install`, kèm một nút bấm cho trường hợp iOS
không tự mở ứng dụng.

<a id="doc-h13" name="doc-h13"></a>
### Phím tắt

Các công cụ của SideInstaller là các action trong ứng dụng Phím tắt, nên một phím tắt, một tự động hóa,
nút Action hay Siri đều có thể chạy chúng:

- **Giả lập vị trí:** Set Location (một địa điểm chọn trên bản đồ, một địa chỉ hoặc một vị trí từ
  action khác), Set Location to Coordinates, Set Location to Saved Place, Reset Location, Get
  Spoofed Location, Is Location Spoofed, Play GPX Route, Travel to Place (một lộ trình lập trên
  OpenStreetMap, đi bộ, đạp xe hoặc lái xe theo giới hạn tốc độ của từng con đường), Stop Route, Save Place và
  Delete Saved Place.
- **Ứng dụng sideload:** Get Sideloaded Apps (mỗi ứng dụng kèm ngày hết hạn và số ngày còn lại),
  Refresh All Apps và Refresh App.
- **Cài đặt:** Install App (SideStore, LiveContainer + SideStore, Madeira hoặc AltStore, bản ổn định hoặc
  nightly), Install IPA và Install IPA from URL. Các action này mở SideInstaller, vì quá trình cài đặt có thể
  dừng lại để yêu cầu điều gì đó.
- **Ghép nối và các tính năng khác:** Get Pairing File, Import Pairing File, Install Pairing File into Apps,
  Show Developer Mode in Settings, Is LocalDevVPN Connected, Connect LocalDevVPN và Get Activity
  Log.

Các action còn lại chạy ở chế độ nền, qua LocalDevVPN như các trang của chính ứng dụng, nên đường hầm của nó phải
hoạt động: hãy kết nối trước khi chạy (action Set VPN của Phím tắt có thể làm việc đó), hoặc bật
**Khởi động LocalDevVPN khi cần**,
rồi action sẽ yêu cầu tiếp tục trong SideInstaller để kết nối. Vị trí được đặt từ một phím tắt giữ nguyên cho đến khi Reset Location:
SideInstaller tiếp tục chạy nền để giữ vị trí đó, giống như khi bạn đặt trong ứng dụng. Siri hiểu các câu "Spoof my location to *saved place* with
SideInstaller", "Reset my location with SideInstaller" và "Refresh my apps with SideInstaller".
Tên các action bằng tiếng Anh; lời chúng nói khi chạy thì theo ngôn ngữ của SideInstaller.

<a id="doc-h14" name="doc-h14"></a>
## Khả năng tương thích

| iOS | Có tương thích không? |
| --- | --- |
| 27+ | ✅ Có — không cần PC với siboot |
| 26.4 – 26.7 | ⚠️ Có, nhưng [cần tệp ghép nối từ xa](#doc-h15) và việc đó cần PC |
| 17.4 – 26.3 | ⚠️ Có, nhưng [cần tệp ghép nối](https://docs.sidestore.io/docs/advanced/alternative#pairing) và việc đó cần PC |
| <17.4 | ❌ Không |

<a id="doc-h15" name="doc-h15"></a>
### iOS 26.4 đến 26.x: tệp ghép nối từ xa

Từ iOS 26.4, iPhone ngắt kết nối với các tệp ghép nối lockdown (từ jitterbugpair,
`pymobiledevice3 lockdown pair` hoặc **Lockdown** của idevice_pair) ngay khi chúng đi qua
LocalDevVPN, nên không thể dùng các tệp đó trên iPhone nữa, dù mới đến đâu. Tệp ghép nối từ xa (RPPairing)
vẫn hoạt động:

1. Trên Mac, PC Windows hoặc máy Linux, mở [idevice_pair](https://github.com/jkcoxson/idevice_pair/releases/latest)
   rồi cắm iPhone vào. Nhấn **Trust** nếu được hỏi.
2. Chọn iPhone, chọn **Remote pairing**, bấm **Create** và giữ iPhone mở khóa cho đến
   khi xong.
3. Bấm **Save to file…** rồi gửi tệp sang iPhone qua AirDrop, iCloud Drive hoặc cáp.
4. Trong SideInstaller, nhấn **Nhập tệp ghép nối** (hoặc **Thay**) rồi chọn tệp.

Một tệp ghép nối xuất từ [iLoader](https://github.com/nab138/iloader) (**Manage Pairing File** ›
**Export**) chứa cả hai loại và cũng dùng được.

<a id="doc-h16" name="doc-h16"></a>
## SideInstaller có an toàn không?

SideInstaller được xây dựng với sự an toàn và quyền riêng tư trong tâm. Ứng dụng hoàn toàn chạy cục bộ và là mã nguồn mở,
nên bất kỳ ai cũng có thể kiểm tra chính xác những gì nó làm.

**Thông tin đăng nhập Apple của bạn không bao giờ rời khỏi thiết bị.** Chỉ được dùng cục bộ, để ký và cài đặt
ứng dụng của bạn, và không bao giờ được truyền đi, ghi nhật ký hay thu thập dưới bất kỳ hình thức nào.

**Không có máy chủ, không có phân tích, không cần tài khoản.** Không có gì được thu thập và không có gì để đăng ký.

**Hoàn toàn có thể kiểm chứng.** Mọi dòng mã đều có thể được xác minh trong mã nguồn.

> [!WARNING]
> Tất cả những điều trên đúng với **kho lưu trữ này** và các bản dựng được phát hành từ đó. Đó **không** phải là sự đảm bảo
> áp dụng cho các fork, IPA ký lại hay bản sao bạn tìm thấy ở nơi khác — những bản đó có thể bị sửa để đánh cắp
> Apple ID bạn nhập vào. Nếu bạn không lấy từ
> https://sideinstaller.net/, đừng tin tưởng nó với
> thông tin đăng nhập của bạn.

<a id="doc-h17" name="doc-h17"></a>
## Cấu trúc dự án

| Đường dẫn | Nội dung |
| :-- | :-- |
| `ios-app/` | Ứng dụng SwiftUI — giao diện, cơ chế cài đặt, xử lý chứng chỉ, bản dịch |
| `ios-live-activity/` | Tiện ích vẽ mã ghép nối trong Dynamic Island và trên Màn hình khóa |
| `ios-tests/` | Các bài kiểm tra đơn vị của ứng dụng (`SideInstallerTests`) |
| `rust-core/` | Lõi Rust được biên dịch thành `SideInstallerFFI.xcframework` |
| `scripts/` | Tập lệnh build, kiểm tra và phát hành |
| `.github/` | Các workflow kiểm tra pull request, build IPA chưa ký, phát hành IPA đó dưới dạng release và chuyển cho bên ký |

Các bản dựng đã ký và trang cài đặt nằm trong [FrizzleM/SideInstaller-Signed](https://github.com/FrizzleM/SideInstaller-Signed):
kho này ký IPA của mỗi bản phát hành bằng từng chứng chỉ, đính kèm các IPA đã ký vào một release của riêng nó và
triển khai [sideinstaller.net](https://sideinstaller.net/). Không IPA nào được commit vào một trong hai kho.

siboot, công cụ cài SideInstaller [ngay từ iPhone](#doc-h5),
nằm trong [FrizzleM/siboot](https://github.com/FrizzleM/siboot). Nó build các crate được vendored trong kho này
và `apple_session.rs` cùng `error_text.rs` của rust-core thông qua một submodule khóa ở một commit cụ thể, nên một thay đổi
ở đây chỉ tới siboot khi khóa đó được cập nhật.

<a id="doc-h18" name="doc-h18"></a>
## Đóng góp

Rất hoan nghênh các issue và pull request. Nếu bạn báo lỗi, hãy kèm phiên bản iOS, phiên bản ứng dụng
và bước mà lỗi xảy ra.

Mọi pull request đều được workflow `checks` kiểm tra: các bài test và clippy của Rust, bản dựng simulator kèm
các bài test đơn vị của ứng dụng, và bản dịch (một chuỗi thêm vào ứng dụng cần có mục trong từng
`ios-app/*Strings.swift`). Các kiểm tra tương tự chạy trên Mac với `scripts/test-rust.sh`,
`scripts/check-ios.sh` (trong một bản clone sạch, vì tập lệnh này tạo dự án Xcode) và
`scripts/check_translations.py`.

<a id="doc-h19" name="doc-h19"></a>
## Giấy phép

Xem [LICENSE.md](LICENSE.md). Tóm lại: bạn có thể đọc, sửa và chia sẻ **mã nguồn**, kèm ghi nhận tác giả,
cho mục đích phi thương mại. Phát hành lại các bản dựng chính thức (IPA) hay kiếm tiền từ dự án dưới bất kỳ
hình thức nào đều cần sự cho phép bằng văn bản.

<div align="center">

**SideInstaller bởi [FrizzleM](https://github.com/FrizzleM)** · Bản dịch tài liệu trong fork này là đóng góp của cộng đồng; ứng dụng vẫn thuộc © FrizzleM.

</div>
