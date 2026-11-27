<div align="center">

<img src="app-icon.png" alt="SideInstaller" width="120" />

# SideInstaller

**Installez SideStore et LiveContainer directement sur votre iPhone — aucun PC requis.**

[![Install](https://img.shields.io/badge/Install-SideInstaller-2ea44f?style=for-the-badge)](https://sideinstaller.net/)
[![Version](https://img.shields.io/badge/version-2.2.0-2669ed?style=for-the-badge)](CHANGELOG.md)
[![Platform](https://img.shields.io/badge/platform-iOS-lightgrey?style=for-the-badge&logo=apple)](#configuration-requise)
[![License](https://img.shields.io/badge/license-Custom-orange?style=for-the-badge)](LICENSE.md)

🌐 **Language / 语言:** [English](README.md) · [简体中文](README.zh-CN.md) · [Español](README.es.md) · [Italiano](README.it.md) · [Tiếng Việt](README.vi.md) · [Français](README.fr.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Português](README.pt-BR.md) · [Türkçe](README.tr.md)

</div>

---

> [!CAUTION]
> **N'installez SideInstaller que depuis la source officielle.**
>
> Ce projet est open source, ce qui signifie que n'importe qui peut forker le code, y insérer un
> voleur d'identifiants qui envoie votre Apple ID et votre mot de passe à son propre serveur, le
> reconstruire et le redistribuer sous le même nom et la même icône. De l'extérieur, un fork
> malveillant est identique à la vraie app.
>
> Les **seules** versions que je publie sont :
> - **Site web :** https://sideinstaller.net/
> - **Dépôt :** https://github.com/FrizzleM/SideInstaller
>
> N'installez pas SideInstaller depuis un autre site, une source AltStore, un canal Telegram, un
> serveur Discord, un dépôt d'apps ou un miroir, quelle que soit son apparence officielle. La
> redistribution de mes versions sans consentement explicite est également interdite par la
> [licence](LICENSE.md).
>
> Il existe un faux site appelé « sideinstaller.com ». Ce site n'est **pas légitime** et propose
> probablement des logiciels malveillants. Assurez-vous de ne télécharger que depuis les
> **sources officielles** citées ci-dessus.

> [!NOTE]
> **À propos de ce fork — documentation uniquement.** Ce fork n'existe que pour traduire et clarifier ces
> instructions. Il ne compile et ne fournit **aucune version de l'app** ; tous les liens de
> téléchargement pointent toujours vers les sources officielles ci-dessus. Le code source de l'app
> présent ici n'est pas modifié. Obtenez toujours la véritable app sur https://sideinstaller.net/ —
> jamais depuis un fork, un miroir ou un IPA reconstruit.

---

## Sur cette page

- [Qu'est-ce que c'est](#quest-ce-que-cest)
- [Configuration requise](#configuration-requise)
- [Comment l'utiliser](#comment-lutiliser)
  - [Méthode A — siboot](#méthode-a--siboot-ios-27-sans-pc)
  - [Méthode B — certificat d'entreprise](#méthode-b--certificat-dentreprise-ios-plus-ancien)
  - [Liens](#liens)
  - [Raccourcis](#raccourcis)
- [Compatibilité](#compatibilité)
  - [iOS 26.4 à 26.x : un fichier de jumelage à distance](#ios-264-à-26x--un-fichier-de-jumelage-à-distance)
- [SideInstaller est-il sûr?](#sideinstaller-est-il-sûr)
- [Structure du projet](#structure-du-projet)
- [Contribuer](#contribuer)
- [Licence](#licence)

---

## Qu'est-ce que c'est

SideStore et LiveContainer sont actuellement la meilleure façon de sideloader sur iOS. Mais il y a
un gros problème : leur installation nécessite un PC, ce dont beaucoup de gens ne disposent pas.
C'est pourquoi j'ai créé SideInstaller, une app iOS gratuite et open source qui les installe
directement sur votre iPhone, sans PC.

SideInstaller gère tout le processus de configuration sur l'appareil. Il s'occupe du jumelage, du
provisionnement et de l'installation — ces étapes qui, normalement, vous obligent à brancher un
ordinateur et à utiliser des outils de bureau — le tout depuis une seule app exécutée sur le
téléphone lui-même. Une fois terminé, vous obtenez une configuration SideStore et LiveContainer
parfaitement fonctionnelle pour sideloader vos propres apps.

Tout est conçu pour être simple. Pas de configuration compliquée, pas de ligne de commande, et
aucun besoin de comprendre le fonctionnement des mécanismes sous-jacents. Il suffit d'ouvrir
l'app, de suivre quelques étapes et de laisser le reste faire. Pour quiconque a toujours voulu
sideloader sans posséder de Mac ni de PC, cela lève le plus gros obstacle pour se lancer.

Et comme c'est open source, vous n'avez pas à me croire sur parole. Le code complet est accessible
à tous pour être lu, audité ou amélioré : vous voyez exactement ce qui s'exécute sur votre appareil.

## Configuration requise

Avant de commencer, assurez-vous d'avoir :

- **Un iPhone ou un iPad** sous **iOS 27 ou version ultérieure** — sous iOS 17.4 et versions
  ultérieures avec un fichier de jumelage créé sur un ordinateur ; depuis iOS 26.4, un
  [fichier de jumelage à distance](#ios-264-à-26x--un-fichier-de-jumelage-à-distance) est nécessaire.
  Consultez le [tableau de compatibilité](#compatibilité).
- **Le Wi-Fi** (uniquement la première fois).
- **Le Mode développeur** activé (pour la méthode siboot).
- **Vos identifiants de compte Apple** — utilisés uniquement sur l'appareil pour signer les apps ;
  jamais collectés.

## Comment l'utiliser

Il existe deux méthodes d'installation. Choisissez celle qui correspond à votre version d'iOS :

| Votre situation | Méthode | PC nécessaire ? |
| --- | --- | --- |
| iOS 27 ou version ultérieure | [Méthode A — siboot](#méthode-a--siboot-ios-27-sans-pc) (recommandée) | Non |
| iOS 17.4 – 26.7, ou si siboot ne fonctionne pas chez vous | [Méthode B — certificat d'entreprise](#méthode-b--certificat-dentreprise-ios-plus-ancien) | Oui, une fois |

### Méthode A — siboot (iOS 27+, sans PC)

[siboot](https://github.com/FrizzleM/siboot) installe SideInstaller depuis l'iPhone lui-même, signé
avec votre propre compte Apple : ni ordinateur ni certificat. Il vous faut **iOS 27 ou une version
ultérieure**, le **Wi-Fi** et le **Mode développeur activé**. Le site
[sideinstaller.net](https://sideinstaller.net/) montre les étapes 1 à 3 en images.

#### Étape 1 — Installer trois apps gratuites

Installez les trois depuis l'App Store :

- [rootshell](https://apps.apple.com/app/rootshell-local-terminal-ssh/id6755794662)
- [Open Minis](https://apps.apple.com/app/id6759188481)
- [LocalDevVPN](https://apps.apple.com/app/id6755608044)

#### Étape 2 — Jumeler dans rootshell

1. Dans rootshell, activez **Réglages › Mode journal de position › Session uniquement**.
2. Appuyez sur **Local Shell**, puis sur **Open** en haut à droite.
3. Exécutez ces commandes **une ligne à la fois** :

   ```sh
   curl -fsSLO https://raw.githubusercontent.com/FrizzleM/siboot/main/rootshell/bin/siboot-pair.wasm
   ```

   ```sh
   ifconfig en0 > ifconfig.txt
   ```

   ```sh
   ./siboot-pair.wasm
   ```

4. Ouvrez **Réglages › Confidentialité et sécurité › Mode développeur**, faites défiler jusqu'en
   bas, appuyez sur **Jumeler avec siboot**, puis saisissez votre code de verrouillage et le code
   qu'affiche rootshell.
5. **Laissez rootshell ouvert** — ne le fermez pas.

#### Étape 3 — Installer depuis Open Minis

1. Connectez **LocalDevVPN**.
2. Dans **Open Minis**, appuyez sur l'icône de la console en haut à droite, puis sur
   **Shell Terminal**.
3. Exécutez :

   ```sh
   wget -qO- https://raw.githubusercontent.com/FrizzleM/siboot/main/minis/install.sh | sh
   ```

4. Saisissez le code de transfert qu'affiche rootshell — **uniquement la première fois** ; ensuite,
   siboot utilise le fichier de jumelage qu'il a enregistré.
5. Saisissez l'**e-mail**, le **mot de passe** et le **code de vérification** de votre compte Apple.
6. **Laissez Minis ouvert** jusqu'à ce qu'il indique avoir terminé. La première fois, faites
   confiance à votre compte Apple dans **Réglages › Général › VPN et gestion des appareils**.

#### Étape 4 — Ouvrir SideInstaller

**LocalDevVPN restant connecté**, connectez-vous avec votre compte Apple et appuyez sur
**Installer SideStore** ou sur **Installer SideStore + LiveContainer**. C'est terminé.

> **Après le jumelage :** exécuter `siboot developer-mode` dans Open Minis demande à l'iPhone
> d'afficher l'interrupteur Mode développeur dans les Réglages ; ajoutez `--turn-on` pour l'activer.
> Voir les [détails](https://github.com/FrizzleM/siboot/blob/main/minis/README.md#developer-mode).

### Méthode B — certificat d'entreprise (iOS plus ancien)

Sur les versions d'iOS antérieures à 27, ou si siboot ne fonctionne pas chez vous, installez
SideInstaller avec l'un des certificats d'entreprise proposés sur
[sideinstaller.net/#legacy](https://sideinstaller.net/#legacy), puis reprenez à l'**étape 4** ci-dessus.
(Les versions plus anciennes nécessitent également un fichier de jumelage — voir
[Compatibilité](#compatibilité).)

### Liens

SideInstaller reconnaît trois types de liens `sideinstaller://` et demande confirmation avant
d'agir sur l'un d'eux :

| Lien | Ce qu'il fait |
| --- | --- |
| `sideinstaller://install?url=<percent-encoded https link to an .ipa>` | Télécharge l'IPA en tant que .ipa personnalisé et l'installe — pour les installations en un seul appui depuis un site web. |
| `sideinstaller://pairingFile?data=<base64 pairing file>` | Importe un fichier de jumelage. SideStore en renvoie un lorsqu'on le lui demande avec `sidestore://pairing?urlname=sideinstaller` — c'est ce que fait **Le récupérer depuis SideStore** sur la carte « Fichier de jumelage ». |
| `sideinstaller://certificate?data=<base64 PKCS#12>&password=<password>` | Fait signer les apps par SideInstaller avec ce certificat à partir de ce moment, une fois qu'Apple l'a répertorié parmi les certificats de votre Apple ID. |

**Utiliser le certificat de SideStore** (dans la fenêtre « Un certificat existe déjà » et sur la
page Certificats) demande à SideStore le sien avec
`sidestore://certificate?callback_template=sideinstaller://certificate?data=$(BASE64_CERT)&password=$(PASSWORD)`
(encodé en pourcentage), afin qu'un certificat d'Apple ID gratuit serve aux deux apps. Cette
réponse est le seul lien qui ne redemande pas confirmation : SideStore vient justement de demander
s'il fallait l'exporter.

Discord et la plupart des apps de messagerie ne rendent cliquables que les liens `https://` ; pour
y publier un lien d'installation, utilisez donc
`https://sideinstaller.net/open.html?url=<percent-encoded https link to an .ipa>`. Cette page
indique d'où l'IPA est téléchargé et le transmet à `sideinstaller://install`, avec un bouton pour
le cas où iOS n'ouvre pas l'app tout seul.

### Raccourcis

Les outils de SideInstaller sont des actions de l'app Raccourcis : un raccourci, une automatisation,
le bouton Action ou Siri peuvent donc les exécuter :

- **Simulation de position :** Set Location (un lieu choisi sur la carte, une adresse ou un
  emplacement fourni par une autre action), Set Location to Coordinates, Set Location to Saved
  Place, Reset Location, Get Spoofed Location, Is Location Spoofed, Play GPX Route, Travel to Place
  (un itinéraire planifié sur OpenStreetMap, parcouru à pied, à vélo ou en voiture à la limite de
  vitesse de chaque route), Stop Route, Save Place et Delete Saved Place.
- **Apps sideloadées :** Get Sideloaded Apps (chacune avec sa date d'expiration et le nombre de
  jours restants), Refresh All Apps et Refresh App.
- **Installation :** Install App (SideStore, LiveContainer + SideStore, Madeira ou AltStore, stable
  ou nightly), Install IPA et Install IPA from URL. Ces actions ouvrent SideInstaller, car une
  installation peut s'arrêter pour y demander quelque chose.
- **Jumelage et autres :** Get Pairing File, Import Pairing File, Install Pairing File into Apps,
  Show Developer Mode in Settings, Is LocalDevVPN Connected, Connect LocalDevVPN et Get Activity
  Log.

Les autres s'exécutent en arrière-plan, via LocalDevVPN comme les propres pages de l'app : son
tunnel doit donc être actif. Connectez-le avant de les lancer (l'action Set VPN de Raccourcis peut
le faire), ou activez **Lancer LocalDevVPN au besoin** : l'action demande alors de continuer dans
SideInstaller pour le connecter. Une position définie par un raccourci reste en vigueur jusqu'à
Reset Location : SideInstaller continue de s'exécuter en arrière-plan pour la maintenir, comme
lorsque vous en définissez une dans l'app. Siri connaît « Spoof my location to *saved place* with
SideInstaller », « Reset my location with SideInstaller » et « Refresh my apps with SideInstaller ».
Les noms des actions sont en anglais ; ce qu'elles annoncent lorsqu'elles s'exécutent est dans la
langue de SideInstaller.

## Compatibilité

| iOS | Compatible ? |
| --- | --- |
| 27+ | ✅ Oui — aucun PC nécessaire avec siboot |
| 26.4 – 26.7 | ⚠️ Oui, mais [un fichier de jumelage à distance est nécessaire](#ios-264-à-26x--un-fichier-de-jumelage-à-distance), et cela demande un PC |
| 17.4 – 26.3 | ⚠️ Oui, mais [un fichier de jumelage est nécessaire](https://docs.sidestore.io/docs/advanced/alternative#pairing), et cela demande un PC |
| <17.4 | ❌ Non |

### iOS 26.4 à 26.x : un fichier de jumelage à distance

Depuis iOS 26.4, l'iPhone coupe la connexion avec les fichiers de jumelage lockdown (ceux de
jitterbugpair, de `pymobiledevice3 lockdown pair` ou l'option **Lockdown** d'idevice_pair) dès
qu'ils passent par LocalDevVPN : ils ne peuvent donc plus être utilisés sur l'iPhone, quel que
soit leur âge. Un fichier de jumelage à distance (RPPairing) fonctionne toujours :

1. Sur un Mac, un PC Windows ou un ordinateur Linux, ouvrez
   [idevice_pair](https://github.com/jkcoxson/idevice_pair/releases/latest) et branchez l'iPhone.
   Appuyez sur **Trust** s'il le demande.
2. Sélectionnez l'iPhone, choisissez **Remote pairing**, cliquez sur **Create** et gardez
   l'iPhone déverrouillé jusqu'à la fin.
3. Cliquez sur **Save to file…** et envoyez le fichier à l'iPhone par AirDrop, iCloud Drive ou un
   câble.
4. Dans SideInstaller, appuyez sur **Importer le fichier de jumelage** (ou sur **Remplacer**) et
   choisissez-le.

Un fichier de jumelage exporté depuis [iLoader](https://github.com/nab138/iloader)
(**Manage Pairing File** › **Export**) contient les deux types et fonctionne également.

## SideInstaller est-il sûr?

SideInstaller est conçu avec la sécurité et la confidentialité à l'esprit. L'app est entièrement
locale et open source, ce qui signifie que n'importe qui peut vérifier exactement ce qu'elle fait.

**Vos identifiants Apple ne quittent jamais votre appareil.** Ils sont utilisés localement,
uniquement pour signer et installer vos apps, et ne sont jamais transmis, journalisés ni collectés.

**Aucun serveur, aucune analytique, aucun compte.** Rien n'est collecté et il n'y a rien à quoi
s'inscrire.

**Entièrement auditable.** Chaque ligne peut être vérifiée dans le code source.

> [!WARNING]
> Tout ce qui précède est vrai pour **ce** dépôt et les versions publiées depuis celui-ci. Ce n'est
> **pas** une garantie qui s'applique aux forks, aux IPA re-signés ou aux copies trouvées ailleurs :
> ceux-ci peuvent être modifiés pour voler l'Apple ID que vous y saisissez. Si vous ne l'avez pas
> obtenu sur https://sideinstaller.net/, ne lui confiez pas vos identifiants.

## Structure du projet

| Chemin | Contenu |
| :-- | :-- |
| `ios-app/` | L'app SwiftUI — interface, moteur d'installation, gestion des certificats, traductions |
| `ios-live-activity/` | L'extension de widget qui affiche le code de jumelage dans l'île dynamique et sur l'écran verrouillé |
| `ios-tests/` | Les tests unitaires de l'app (`SideInstallerTests`) |
| `rust-core/` | Le noyau Rust compilé dans `SideInstallerFFI.xcframework` |
| `scripts/` | Scripts de compilation, de vérification et de publication |
| `.github/` | Workflows qui vérifient les pull requests, compilent l'IPA non signée, la publient comme version et la transmettent au signataire |

Les versions signées et la page d'installation se trouvent dans
[FrizzleM/SideInstaller-Signed](https://github.com/FrizzleM/SideInstaller-Signed) : chaque version
voit son IPA signé avec tous les certificats, les IPA signés sont joints à une version propre au
dépôt et [sideinstaller.net](https://sideinstaller.net/) est déployé. Aucun IPA n'est jamais
enregistré dans l'un ou l'autre des dépôts.

siboot, qui installe SideInstaller [depuis l'iPhone lui-même](#comment-lutiliser), se trouve dans
[FrizzleM/siboot](https://github.com/FrizzleM/siboot). Il compile les crates fournis dans ce dépôt
ainsi que `apple_session.rs` et `error_text.rs` de rust-core par l'intermédiaire d'un sous-module
épinglé à un commit : un changement ici n'atteint siboot que lorsque cette référence est mise à jour.

## Contribuer

Les issues et les pull requests sont les bienvenues. Si vous signalez un bug, indiquez votre version
d'iOS, la version de l'app et l'étape à laquelle l'échec est survenu.

Chaque pull request est vérifiée par le workflow `checks` : les tests Rust et clippy, une
compilation sur simulateur avec les tests unitaires de l'app, et les traductions (une chaîne ajoutée
à l'app doit avoir une entrée dans chaque `ios-app/*Strings.swift`). Les mêmes vérifications
s'exécutent sur un Mac avec `scripts/test-rust.sh`, `scripts/check-ios.sh` (dans un clone propre,
puisqu'il génère le projet Xcode) et `scripts/check_translations.py`.

## Licence

Voir [LICENSE.md](LICENSE.md). En résumé : vous pouvez lire, modifier et partager le **code
source**, avec attribution, à des fins non commerciales. Redistribuer les versions officielles
(IPA) ou monétiser le projet sous quelque forme que ce soit nécessite une autorisation écrite.

<div align="center">

**SideInstaller par [FrizzleM](https://github.com/FrizzleM)** · Les traductions de la documentation
dans ce fork sont des contributions de la communauté ; l'app reste © FrizzleM.

</div>
