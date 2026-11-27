<div align="center">

<img src="app-icon.png" alt="SideInstaller" width="120" />

<a id="doc-h1" name="doc-h1"></a>
# SideInstaller

**Installa SideStore e LiveContainer direttamente sul tuo iPhone — senza PC.**

[![Install](https://img.shields.io/badge/Install-SideInstaller-2ea44f?style=for-the-badge)](https://sideinstaller.net/)
[![Version](https://img.shields.io/badge/version-2.2.0-2669ed?style=for-the-badge)](CHANGELOG.md)
[![Platform](https://img.shields.io/badge/platform-iOS-lightgrey?style=for-the-badge&logo=apple)](#doc-h4)
[![License](https://img.shields.io/badge/license-Custom-orange?style=for-the-badge)](LICENSE.md)

🌐 **Language / 语言:** [English](README.md) · [简体中文](README.zh-CN.md) · [Español](README.es.md) · [Italiano](README.it.md) · [Tiếng Việt](README.vi.md) · [Français](README.fr.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Português](README.pt-BR.md) · [Türkçe](README.tr.md)

</div>

---

> [!CAUTION]
> **Installa SideInstaller solo dalla fonte ufficiale.**
>
> Questo progetto è open source, il che significa che chiunque può forkare il codice, inserire un
> ladro di credenziali che carica il tuo Apple ID e la tua password su un proprio server,
> ricompilarlo e redistribuirlo con lo stesso nome e la stessa icona. Un fork malevolo appare
> identico alla vera app dall'esterno.
>
> Le **uniche** build che pubblico sono:
> - **Sito web:** https://sideinstaller.net/
> - **Repository:** https://github.com/FrizzleM/SideInstaller
>
> Non installare SideInstaller da nessun altro sito, sorgente AltStore, canale Telegram, server Discord,
> repo di app o mirror, per quanto ufficiale possa sembrare. Anche redistribuire le mie build senza consenso esplicito è vietato
> dalla [licenza](LICENSE.md).
>
> Esiste un sito fasullo chiamato "sideinstaller.com". Questo sito **non è legittimo** e molto probabilmente fornisce malware. Assicurati
> di scaricare solo dalle **fonti ufficiali** elencate sopra.

> [!NOTE]
> **Info su questo fork — solo documentazione.** Questo fork esiste solo per tradurre e chiarire queste
> istruzioni. Non compila e non distribuisce **nessun binario dell'app**; ogni link di download punta ancora
> alle fonti ufficiali sopra. Il codice sorgente dell'app qui è invariato. Prendi sempre l'app vera da
> https://sideinstaller.net/ — mai da un fork, un mirror o un IPA ricompilato.

---

<a id="doc-h2" name="doc-h2"></a>
## In questa pagina

- [Che cos'è](#doc-h3)
- [Requisiti](#doc-h4)
- [Come usarlo](#doc-h5)
  - [Metodo A — siboot (iOS 27+, senza PC)](#doc-h6)
  - [Metodo B — certificato enterprise (iOS precedenti)](#doc-h11)
  - [Link](#doc-h12)
  - [Comandi Rapidi](#doc-h13)
- [Compatibilità](#doc-h14)
  - [iOS 26.4 a 26.x: un file di abbinamento remoto](#doc-h15)
- [SideInstaller è sicuro?](#doc-h16)
- [Struttura del progetto](#doc-h17)
- [Contribuire](#doc-h18)
- [Licenza](#doc-h19)

---

<a id="doc-h3" name="doc-h3"></a>
## Che cos'è

SideStore e LiveContainer sono attualmente il modo migliore per fare sideloading su iOS. Però c'è un grande problema: installarli richiede un PC, che molte persone non hanno. Per questo ho creato SideInstaller, un'app iOS gratuita e open source che li installa direttamente sul tuo iPhone, senza bisogno di un PC.

SideInstaller gestisce l'intera configurazione direttamente sul dispositivo. Si occupa dell'abbinamento, del provisioning e dell'installazione — i passaggi che normalmente ti costringono a collegare un computer e usare strumenti desktop — tutto da una sola app che gira sul telefono stesso. Quando ha finito, ottieni un SideStore e un LiveContainer perfettamente funzionanti, pronti per fare sideloading delle tue app.

Il tutto è pensato per essere semplice. Nessuna configurazione complicata, nessuna riga di comando e nessun bisogno di capire come funzioni la macchina sottostante. Ti limiti ad aprire l'app, seguire qualche passaggio e la lasci fare il resto. Per chiunque abbia sempre voluto fare sideloading senza avere un Mac o un PC, questo elimina il maggiore ostacolo per iniziare.

E siccome è open source, non devi fidarti solo della mia parola. Il codice completo è disponibile perché chiunque lo legga, lo verifichi o contribuisca, così puoi vedere esattamente cosa gira sul tuo dispositivo.

<a id="doc-h4" name="doc-h4"></a>
## Requisiti

Prima di iniziare, assicurati di avere:

- **Un iPhone o un iPad** con **iOS 27+** — su iOS 17.4+ con un file di abbinamento creato su un computer; da iOS 26.4 serve un [file di abbinamento remoto](#doc-h15). Vedi la [tabella di compatibilità](#doc-h14).
- **Wi-Fi** (solo la prima volta).
- **Modalità sviluppatore** attiva (per il metodo siboot).
- **Le tue credenziali Apple** — usate solo sul dispositivo per firmare le app; mai raccolte.

<a id="doc-h5" name="doc-h5"></a>
## Come usarlo

Esistono due metodi di installazione. Scegli quello che corrisponde alla tua versione di iOS:

| La tua situazione | Metodo | Serve un PC? |
| --- | --- | --- |
| iOS 27 o successivo | [Metodo A — siboot](#doc-h6) (consigliato) | No |
| iOS 17.4 – 26.7, oppure siboot non funziona per te | [Metodo B — certificato enterprise](#doc-h11) | Sì, una volta sola |

<a id="doc-h6" name="doc-h6"></a>
### Metodo A — siboot (iOS 27+, senza PC)

[siboot](https://github.com/FrizzleM/siboot) installa SideInstaller dall'iPhone stesso, firmato con il tuo account Apple: nessun computer e nessun certificato. Serve **iOS 27 o successivo**, il **Wi-Fi** e la **Modalità sviluppatore attiva**. Il sito [sideinstaller.net](https://sideinstaller.net/) mostra i passaggi da 1 a 3 in modo visivo.

<a id="doc-h7" name="doc-h7"></a>
#### Passaggio 1 — Installa tre app gratuite

Installa tutte e tre dall'App Store:

- [rootshell](https://apps.apple.com/app/rootshell-local-terminal-ssh/id6755794662)
- [Open Minis](https://apps.apple.com/app/id6759188481)
- [LocalDevVPN](https://apps.apple.com/app/id6755608044)

<a id="doc-h8" name="doc-h8"></a>
#### Passaggio 2 — Esegui l'abbinamento in rootshell

1. In rootshell, attiva **Impostazioni › Modalità Diario posizioni › Solo sessione**.
2. Tocca **Local Shell**, poi **Open** in alto a destra.
3. Esegui questi comandi **uno alla volta**:

   ```sh
   curl -fsSLO https://raw.githubusercontent.com/FrizzleM/siboot/main/rootshell/bin/siboot-pair.wasm
   ifconfig en0 > ifconfig.txt
   ./siboot-pair.wasm
   ```

4. Apri **Impostazioni › Privacy e sicurezza › Modalità sviluppatore**, scorri fino in fondo, tocca
   **Abbina a siboot**, poi inserisci il codice di sblocco e il codice mostrato da rootshell.
5. **Lascia rootshell in esecuzione**: non chiuderlo.

<a id="doc-h9" name="doc-h9"></a>
#### Passaggio 3 — Installa da Open Minis

1. Connetti **LocalDevVPN**.
2. In **Open Minis**, tocca l'icona della console in alto a destra, poi **Shell Terminal**.
3. Esegui:

   ```sh
   wget -qO- https://raw.githubusercontent.com/FrizzleM/siboot/main/minis/install.sh | sh
   ```

4. Inserisci il codice di trasferimento mostrato da rootshell — **solo la prima volta**; dopo, siboot usa il
   file di abbinamento che ha salvato.
5. Inserisci l'**email**, la **password** e il **codice di verifica** del tuo account Apple.
6. **Lascia Minis aperto** finché non dice che ha finito. La prima volta, autorizza il tuo account Apple in
   **Impostazioni › Generali › VPN e gestione dispositivi**.

<a id="doc-h10" name="doc-h10"></a>
#### Passaggio 4 — Apri SideInstaller

Con **LocalDevVPN connesso**, accedi con il tuo account Apple e tocca **Installa SideStore** o
**Installa SideStore + LiveContainer**. Fatto.

> **Dopo l'abbinamento:** eseguire `siboot developer-mode` in Open Minis chiede all'iPhone di mostrare
> l'interruttore della Modalità sviluppatore in Impostazioni; aggiungi `--turn-on` per attivarlo. Vedi i
> [dettagli](https://github.com/FrizzleM/siboot/blob/main/minis/README.md#developer-mode).

<a id="doc-h11" name="doc-h11"></a>
### Metodo B — certificato enterprise (iOS precedenti)

Su versioni di iOS precedenti alla 27, oppure se siboot non funziona per te, installa SideInstaller con uno dei
certificati enterprise su [sideinstaller.net/#legacy](https://sideinstaller.net/#legacy), poi continua dal
**passaggio 4** qui sopra. (Le versioni precedenti richiedono anche un file di abbinamento — vedi [Compatibilità](#doc-h14).)

<a id="doc-h12" name="doc-h12"></a>
### Link

SideInstaller apre tre tipi di link `sideinstaller://` e chiede conferma prima di agire su ciascuno:

| Link | Cosa fa |
| --- | --- |
| `sideinstaller://install?url=<percent-encoded https link to an .ipa>` | Scarica l'IPA come .ipa personalizzato e lo installa — per installazioni con un tocco da un sito web. |
| `sideinstaller://pairingFile?data=<base64 pairing file>` | Importa un file di abbinamento. SideStore ne rimanda uno quando richiesto con `sidestore://pairing?urlname=sideinstaller` — è quello che fa **Prendilo da SideStore** nella scheda File di abbinamento. |
| `sideinstaller://certificate?data=<base64 PKCS#12>&password=<password>` | Fa firmare a SideInstaller con quel certificato da quel momento in poi, una volta che Apple lo elenca tra i certificati del tuo Apple ID. |

**Usa il certificato di SideStore** (nel popup "Esiste già un certificato" e nella pagina Certificati)
chiede a SideStore il proprio con
`sidestore://certificate?callback_template=sideinstaller://certificate?data=$(BASE64_CERT)&password=$(PASSWORD)`
(codificato in percentuale), così il certificato di un Apple ID gratuito serve a entrambe le app. Questa risposta è l'unico link
che non chiede un'altra conferma: SideStore ha appena chiesto se esportarlo.

Discord e la maggior parte delle app di chat rendono toccabili solo i link `https://`, quindi per pubblicare lì
un link di installazione usa
`https://sideinstaller.net/open.html?url=<percent-encoded https link to an .ipa>`. Quella pagina mostra
da dove viene scaricato l'IPA e lo passa a `sideinstaller://install`, con un pulsante per quando iOS
non apre l'app da solo.

<a id="doc-h13" name="doc-h13"></a>
### Comandi Rapidi

Gli strumenti di SideInstaller sono azioni nell'app Comandi Rapidi, quindi una scorciatoia, un'automazione,
il pulsante Azione o Siri possono eseguirle:

- **Simulazione posizione:** Set Location (un luogo scelto sulla mappa, un indirizzo o una posizione da
  un'altra azione), Set Location to Coordinates, Set Location to Saved Place, Reset Location, Get
  Spoofed Location, Is Location Spoofed, Play GPX Route, Travel to Place (un percorso pianificato su
  OpenStreetMap, da percorrere a piedi, in bici o in auto al limite di velocità di ogni strada), Stop Route,
  Save Place e Delete Saved Place.
- **App sideloadate:** Get Sideloaded Apps (ognuna con il giorno di scadenza e i giorni rimasti),
  Refresh All Apps e Refresh App.
- **Installazione:** Install App (SideStore, LiveContainer + SideStore, Madeira o AltStore, stabile o
  nightly), Install IPA e Install IPA from URL. Queste aprono SideInstaller, perché un'installazione può
  fermarsi a chiedere qualcosa lì.
- **Abbinamento e il resto:** Get Pairing File, Import Pairing File, Install Pairing File into Apps,
  Show Developer Mode in Settings, Is LocalDevVPN Connected, Connect LocalDevVPN e Get Activity
  Log.

Le altre azioni girano in background, tramite LocalDevVPN come le pagine stesse dell'app, quindi il tunnel
deve essere attivo: connettila prima (può farlo l'azione VPN di Comandi Rapidi), oppure attiva
**Avvia LocalDevVPN quando serve**, e l'azione chiederà di continuare in SideInstaller per connetterla.
Una posizione impostata da una scorciatoia resta impostata fino a Reset Location: SideInstaller continua a
girare in background per mantenerla, come quando ne imposti una dall'app. Siri riconosce "Spoof my location
to *saved place* with SideInstaller", "Reset my location with SideInstaller" e "Refresh my apps with
SideInstaller". I nomi delle azioni sono in inglese; ciò che dicono quando girano è nella lingua di SideInstaller.

<a id="doc-h14" name="doc-h14"></a>
## Compatibilità

| iOS | È compatibile? |
| --- | --- |
| 27+ | ✅ Sì — con siboot non serve un PC |
| 26.4 – 26.7 | ⚠️ Sì, ma [serve un file di abbinamento remoto](#doc-h15), e quindi un PC |
| 17.4 – 26.3 | ⚠️ Sì, ma [serve un file di abbinamento](https://docs.sidestore.io/docs/advanced/alternative#pairing), e quindi un PC |
| <17.4 | ❌ No |

<a id="doc-h15" name="doc-h15"></a>
### iOS 26.4 a 26.x: un file di abbinamento remoto

Da iOS 26.4 in poi, l'iPhone chiude la connessione con i file di abbinamento lockdown (di jitterbugpair,
`pymobiledevice3 lockdown pair` o **Lockdown** di idevice_pair) appena passano da LocalDevVPN, quindi non
possono più essere usati sull'iPhone, per quanto nuovi. Un file di abbinamento remoto (RPPairing) funziona
ancora:

1. Su un Mac, un PC Windows o un computer Linux, apri [idevice_pair](https://github.com/jkcoxson/idevice_pair/releases/latest)
   e collega l'iPhone. Tocca **Autorizza** se te lo chiede.
2. Seleziona l'iPhone, scegli **Remote pairing**, fai clic su **Create** e tieni l'iPhone sbloccato fino
   al termine.
3. Fai clic su **Save to file…** e invia il file all'iPhone con AirDrop, iCloud Drive o un cavo.
4. In SideInstaller, tocca **Importa il file di abbinamento** (oppure **Sostituisci**) e sceglilo.

Un file di abbinamento esportato da [iLoader](https://github.com/nab138/iloader) (**Manage Pairing File** ›
**Export**) contiene entrambi i tipi e funziona ugualmente.

<a id="doc-h16" name="doc-h16"></a>
## SideInstaller è sicuro?

SideInstaller è realizzato pensando alla sicurezza e alla privacy. L'app è completamente locale e open source,
quindi chiunque può verificare esattamente cosa fa.

**Le tue credenziali Apple non lasciano mai il dispositivo.** Vengono usate localmente, solo per firmare e
installare le tue app, e non vengono mai trasmesse, registrate o raccolte in alcun modo.

**Nessun server, nessuna analisi, nessun account.** Non viene raccolto nulla e non c'è niente a cui iscriversi.

**Interamente verificabile.** Ogni riga può essere controllata nel codice sorgente.

> [!WARNING]
> Tutto quanto sopra è vero per **questo** repository e per le build pubblicate da qui. **Non** è una
> garanzia che valga per fork, IPA rifirmati o copie trovate altrove: possono essere modificati per rubare
> l'Apple ID che inserisci. Se non l'hai presa da
> https://sideinstaller.net/, non affidargli le tue
> credenziali.

<a id="doc-h17" name="doc-h17"></a>
## Struttura del progetto

| Percorso | Contenuto |
| :-- | :-- |
| `ios-app/` | L'app SwiftUI — interfaccia, motore di installazione, gestione dei certificati, traduzioni |
| `ios-live-activity/` | L'estensione widget che mostra il codice di abbinamento nella Dynamic Island e sulla schermata di blocco |
| `ios-tests/` | I test unitari dell'app (`SideInstallerTests`) |
| `rust-core/` | Il core Rust compilato in `SideInstallerFFI.xcframework` |
| `scripts/` | Script di build, controllo e rilascio |
| `.github/` | Workflow che verificano le pull request, compilano l'IPA non firmata, la pubblicano come release e la passano al firmatario |

Le build firmate e la pagina di installazione si trovano in [FrizzleM/SideInstaller-Signed](https://github.com/FrizzleM/SideInstaller-Signed):
firma l'IPA di ogni release con ogni certificato, allega le IPA firmate a una release propria e distribuisce
[sideinstaller.net](https://sideinstaller.net/). Nessuna IPA viene mai inclusa nei repository.

siboot, che installa SideInstaller [dall'iPhone stesso](#doc-h5),
si trova in [FrizzleM/siboot](https://github.com/FrizzleM/siboot). Compila le crate vendored di questo
repository e `apple_session.rs` e `error_text.rs` di rust-core tramite un submodule fissato a un commit,
quindi una modifica qui arriva a siboot solo quando quel riferimento si aggiorna.

<a id="doc-h18" name="doc-h18"></a>
## Contribuire

Segnalazioni e pull request sono benvenute. Se segnali un bug, indicare la tua versione di iOS, la versione
dell'app e il passaggio in cui si è verificato.

Ogni pull request viene verificata dal workflow `checks`: i test e clippy di Rust, una build per simulatore
con i test unitari dell'app e le traduzioni (una stringa aggiunta all'app deve avere una voce in ogni
`ios-app/*Strings.swift`). Gli stessi controlli girano su un Mac con `scripts/test-rust.sh`,
`scripts/check-ios.sh` (in un clone pulito, perché genera il progetto Xcode) e
`scripts/check_translations.py`.

<a id="doc-h19" name="doc-h19"></a>
## Licenza

Vedi [LICENSE.md](LICENSE.md). In breve: puoi leggere, modificare e condividere il **codice sorgente**, con
attribuzione, per scopi non commerciali. Redistribuire le build ufficiali (IPA) o monetizzare il progetto in
qualsiasi forma richiede il permesso scritto.

<div align="center">

**SideInstaller di [FrizzleM](https://github.com/FrizzleM)** · Le traduzioni della documentazione in questo fork sono contributi della comunità; l'app resta © FrizzleM.

</div>
