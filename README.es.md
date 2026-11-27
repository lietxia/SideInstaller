<div align="center">

<img src="app-icon.png" alt="SideInstaller" width="120" />

# SideInstaller

**Instala SideStore y LiveContainer directamente en tu iPhone — sin necesidad de PC.**

[![Install](https://img.shields.io/badge/Install-SideInstaller-2ea44f?style=for-the-badge)](https://sideinstaller.net/)
[![Version](https://img.shields.io/badge/version-2.2.0-2669ed?style=for-the-badge)](CHANGELOG.md)
[![Platform](https://img.shields.io/badge/platform-iOS-lightgrey?style=for-the-badge&logo=apple)](#requisitos)
[![License](https://img.shields.io/badge/license-Custom-orange?style=for-the-badge)](LICENSE.md)

🌐 **Language / 语言:** [English](README.md) · [简体中文](README.zh-CN.md) · [Español](README.es.md) · [Italiano](README.it.md) · [Tiếng Việt](README.vi.md) · [Français](README.fr.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Português](README.pt-BR.md) · [Türkçe](README.tr.md)

</div>

---

> [!CAUTION]
> **Instala SideInstaller solo desde la fuente oficial.**
>
> Este proyecto es de código abierto, lo que significa que cualquiera puede bifurcar el código, insertar un ladrón de credenciales que
> sube tu Apple ID y tu contraseña a su propio servidor, recompilarlo y redistribuirlo bajo el mismo
> nombre e icono. Un fork malicioso es idéntico a la app real por fuera.
>
> Las **únicas** compilaciones que publico son:
> - **Sitio web:** https://sideinstaller.net/
> - **Repositorio:** https://github.com/FrizzleM/SideInstaller
>
> No instales SideInstaller desde ningún otro sitio, fuente de AltStore, canal de Telegram, servidor de Discord,
> repositorio de apps o espejo, por muy oficial que parezca. La redistribución de mis compilaciones sin consentimiento explícito también está prohibida por
> la [licencia](LICENSE.md).
>
> Existe un sitio falso llamado "sideinstaller.com". Este sitio **no es legítimo** y probablemente ofrece malware. Asegúrate de descargar
> solo desde las **fuentes oficiales** indicadas arriba.

> [!NOTE]
> **Sobre este fork: solo documentación.** Este fork existe únicamente para traducir y aclarar estas
> instrucciones. No compila ni distribuye **ningún binario de la app**; todos los enlaces de descarga siguen apuntando a las
> fuentes oficiales de arriba. El código fuente de la app aquí está sin modificar. Consigue siempre la app real en
> https://sideinstaller.net/ — nunca desde un fork, un espejo ni un IPA recompilado.

---

## En esta página

- [Qué es](#qué-es)
- [Requisitos](#requisitos)
- [Cómo usarlo](#cómo-usarlo)
  - [Método A — siboot (iOS 27+, sin PC)](#método-a--siboot-ios-27-sin-pc)
  - [Método B — certificado empresarial (iOS antiguos)](#método-b--certificado-empresarial-ios-antiguos)
  - [Enlaces](#enlaces)
  - [Atajos](#atajos)
- [Compatibilidad](#compatibilidad)
  - [iOS 26.4 a 26.x: un archivo de emparejamiento remoto](#ios-264-a-26x-un-archivo-de-emparejamiento-remoto)
- [¿Es SideInstaller seguro?](#es-sideinstaller-seguro)
- [Estructura del proyecto](#estructura-del-proyecto)
- [Contribuir](#contribuir)
- [Licencia](#licencia)

---

## Qué es

SideStore y LiveContainer son actualmente la mejor forma de hacer sideload en iOS. Sin embargo, hay un gran
problema: instalarlos requiere un PC, del que mucha gente no dispone. Por eso creé SideInstaller,
una app de iOS gratuita y de código abierto que los instala directamente en tu iPhone, sin necesidad de PC.

SideInstaller se encarga de todo el proceso de configuración en el propio dispositivo. Se ocupa del emparejamiento,
el aprovisionamiento y la instalación, esos pasos que normalmente te obligan a conectar un ordenador y ejecutar
herramientas de escritorio, todo desde una sola app que se ejecuta en el teléfono. Cuando termina, obtienes una
configuración de SideStore y LiveContainer totalmente funcional, lista para hacer sideload de tus propias apps.

Todo está diseñado para ser sencillo. No hay configuraciones complicadas, ni línea de comandos, ni necesidad de
entender cómo funciona la maquinaria subyacente. Solo abres la app, sigues unos pocos pasos y dejas que
haga el resto. Para quienes siempre han querido hacer sideload pero no tenían Mac ni PC, esto elimina la
mayor barrera para empezar.

Y como es de código abierto, no tienes que fiarte solo de mi palabra. El código completo está disponible para
que cualquiera lo lea, lo audite o contribuya, así que puedes ver exactamente qué se ejecuta en tu dispositivo.

## Requisitos

Antes de empezar, asegúrate de tener:

- **Un iPhone o iPad** con **iOS 27 o posterior**; en iOS 17.4 o posterior con un archivo de emparejamiento creado en un ordenador; a partir de
  iOS 26.4 hace falta un [archivo de emparejamiento remoto](#ios-264-a-26x-un-archivo-de-emparejamiento-remoto). Consulta la
  [tabla de compatibilidad](#compatibilidad).
- **Wi-Fi** (solo la primera vez).
- **Modo desarrollador** activado (para el método siboot).
- **Tus credenciales de Apple** — se usan solo en el dispositivo para firmar apps; nunca se recopilan.

## Cómo usarlo

Hay dos métodos de instalación. Elige el que corresponda a tu versión de iOS:

| Tu situación | Método | ¿Necesita PC? |
| --- | --- | --- |
| iOS 27 o posterior | [Método A — siboot](#método-a--siboot-ios-27-sin-pc) (recomendado) | No |
| iOS 17.4 – 26.7, o si siboot no funciona para ti | [Método B — certificado empresarial](#método-b--certificado-empresarial-ios-antiguos) | Sí, una vez |

### Método A — siboot (iOS 27+, sin PC)

[siboot](https://github.com/FrizzleM/siboot) instala SideInstaller desde el propio iPhone, firmado
con tu propia cuenta Apple: sin ordenador y sin certificado. Necesitas **iOS 27 o posterior**, **Wi-Fi** y el
**Modo desarrollador activado**. El sitio web [sideinstaller.net](https://sideinstaller.net/) muestra los pasos 1 a 3
de forma visual.

#### Paso 1 — Instalar tres apps gratuitas

Instala las tres desde la App Store:

- [rootshell](https://apps.apple.com/app/rootshell-local-terminal-ssh/id6755794662)
- [Open Minis](https://apps.apple.com/app/id6759188481)
- [LocalDevVPN](https://apps.apple.com/app/id6755608044)

#### Paso 2 — Emparejar en rootshell

1. En rootshell, activa **Ajustes › Modo diario de ubicación › Solo sesión**.
2. Toca **Local Shell** y luego **Open** en la esquina superior derecha.
3. Ejecuta estos comandos **uno a la vez**:

   ```sh
   curl -fsSLO https://raw.githubusercontent.com/FrizzleM/siboot/main/rootshell/bin/siboot-pair.wasm
   ```

   ```sh
   ifconfig en0 > ifconfig.txt
   ```

   ```sh
   ./siboot-pair.wasm
   ```

4. Abre **Ajustes › Privacidad y seguridad › Modo desarrollador**, desplázate al final, toca
   **Pair with siboot** y luego introduce tu código de acceso y el código que muestra rootshell.
5. **Deja rootshell en ejecución**: no lo cierres.

#### Paso 3 — Instalar desde Open Minis

1. Conecta **LocalDevVPN**.
2. En **Open Minis**, toca el icono de consola en la esquina superior derecha y luego **Shell Terminal**.
3. Ejecuta:

   ```sh
   wget -qO- https://raw.githubusercontent.com/FrizzleM/siboot/main/minis/install.sh | sh
   ```

4. Introduce el código de transferencia que muestra rootshell: **solo la primera vez**; después, siboot usa el archivo de
   emparejamiento que guardó.
5. Introduce el **correo electrónico**, la **contraseña** y el **código de verificación** de tu cuenta Apple.
6. **Mantén Minis abierta** hasta que indique que ha terminado. La primera vez, confía en tu cuenta Apple en
   **Ajustes › General › VPN y gestión de dispositivos**.

#### Paso 4 — Abrir SideInstaller

Con **LocalDevVPN conectada**, inicia sesión con tu cuenta Apple y toca **Instalar SideStore** o
**Instalar SideStore + LiveContainer**. Listo.

> **Tras el emparejamiento:** ejecutar `siboot developer-mode` en Open Minis pide al iPhone que muestre el
> interruptor del Modo desarrollador en Ajustes; añade `--turn-on` para activarlo. Consulta los
> [detalles](https://github.com/FrizzleM/siboot/blob/main/minis/README.md#developer-mode).

### Método B — certificado empresarial (iOS antiguos)

En versiones de iOS anteriores a 27, o si siboot no funciona para ti, instala SideInstaller con uno de los
certificados empresariales de [sideinstaller.net/#legacy](https://sideinstaller.net/#legacy) y continúa desde el
**paso 4** anterior. (Las versiones antiguas también necesitan un archivo de emparejamiento: consulta [Compatibilidad](#compatibilidad).)

### Enlaces

SideInstaller abre tres tipos de enlace `sideinstaller://` y pide confirmación antes de actuar sobre cualquiera de ellos:

| Enlace | Qué hace |
| --- | --- |
| `sideinstaller://install?url=<percent-encoded https link to an .ipa>` | Descarga el IPA como .ipa personalizado y lo instala: para instalaciones con un solo toque desde un sitio web. |
| `sideinstaller://pairingFile?data=<base64 pairing file>` | Importa un archivo de emparejamiento. SideStore devuelve uno cuando se le pide con `sidestore://pairing?urlname=sideinstaller`: eso es lo que hace **Obtenerlo de SideStore** en la tarjeta Archivo de emparejamiento. |
| `sideinstaller://certificate?data=<base64 PKCS#12>&password=<password>` | Hace que SideInstaller firme con ese certificado a partir de entonces, una vez Apple lo incluya entre los certificados de tu Apple ID. |

**Usar el certificado de SideStore** (en el aviso “Ya existe un certificado” y en la página Certificados)
pide a SideStore el suyo con
`sidestore://certificate?callback_template=sideinstaller://certificate?data=$(BASE64_CERT)&password=$(PASSWORD)`
(codificado en porcentaje), para que el único certificado de un Apple ID gratuito sirva a ambas apps. Esa respuesta es el único enlace que
no vuelve a pedir confirmación: SideStore acaba de preguntar si quieres exportarlo.

Discord y la mayoría de las apps de chat solo hacen interactivos los enlaces `https://`, así que para publicar
allí un enlace de instalación usa `https://sideinstaller.net/open.html?url=<percent-encoded https link to an .ipa>`.
Esa página muestra desde dónde se descarga el IPA y se lo pasa a `sideinstaller://install`, con un botón para cuando
iOS no abre la app por sí solo.

### Atajos

Las herramientas de SideInstaller son acciones de la app Atajos, así que un atajo, una automatización,
el botón Acciones o Siri pueden ejecutarlas:

- **Simulación de ubicación:** Set Location (un lugar elegido en el mapa, una dirección o una ubicación de
  otra acción), Set Location to Coordinates, Set Location to Saved Place, Reset Location, Get
  Spoofed Location, Is Location Spoofed, Play GPX Route, Travel to Place (una ruta planificada sobre
  OpenStreetMap, recorrida a pie, en bici o en coche a la velocidad límite de cada vía), Stop Route, Save Place y
  Delete Saved Place.
- **Apps sideloadeadas:** Get Sideloaded Apps (cada una con el día en que caduca y los días que quedan),
  Refresh All Apps y Refresh App.
- **Instalación:** Install App (SideStore, LiveContainer + SideStore, Madeira o AltStore, estable o nightly),
  Install IPA e Install IPA from URL. Estas abren SideInstaller, ya que una instalación puede detenerse a pedir
  algo allí.
- **Emparejamiento y demás:** Get Pairing File, Import Pairing File, Install Pairing File into Apps,
  Show Developer Mode in Settings, Is LocalDevVPN Connected, Connect LocalDevVPN y Get Activity
  Log.

Las demás se ejecutan en segundo plano, a través de LocalDevVPN como las propias páginas de la app, así que
su túnel debe estar activo: conéctalo antes de ellas (la acción Set VPN de Atajos puede hacerlo) o activa
**Iniciar LocalDevVPN cuando haga falta**, y la acción pedirá continuar en SideInstaller para conectarlo. Una ubicación
fijada desde un atajo se mantiene hasta Reset Location: SideInstaller sigue ejecutándose en segundo plano para
conservarla, igual que cuando fijas una desde la app. Siri entiende «Spoof my location to *saved place* with
SideInstaller», «Reset my location with SideInstaller» y «Refresh my apps with SideInstaller». Los nombres de
las acciones están en inglés; lo que dicen al ejecutarse está en el idioma de SideInstaller.

## Compatibilidad

| iOS | ¿Es compatible? |
| --- | --- |
| 27+ | ✅ Sí: sin PC con siboot |
| 26.4 – 26.7 | ⚠️ Sí, pero [hace falta un archivo de emparejamiento remoto](#ios-264-a-26x-un-archivo-de-emparejamiento-remoto) y eso requiere un PC |
| 17.4 – 26.3 | ⚠️ Sí, pero [hace falta un archivo de emparejamiento](https://docs.sidestore.io/docs/advanced/alternative#pairing) y eso requiere un PC |
| <17.4 | ❌ No |

### iOS 26.4 a 26.x: un archivo de emparejamiento remoto

Desde iOS 26.4, el iPhone corta la conexión con los archivos de emparejamiento lockdown (de jitterbugpair,
`pymobiledevice3 lockdown pair` o el **Lockdown** de idevice_pair) en cuanto se conectan a través de
LocalDevVPN, así que ya no se pueden usar en el iPhone, por muy nuevos que sean. Un archivo de emparejamiento
remoto (RPPairing) sigue funcionando:

1. En un Mac, un PC con Windows o Linux, abre [idevice_pair](https://github.com/jkcoxson/idevice_pair/releases/latest)
   y conecta el iPhone. Toca **Confiar** si te lo pide.
2. Selecciona el iPhone, elige **Remote pairing**, haz clic en **Create** y mantén el iPhone desbloqueado hasta
   que termine.
3. Haz clic en **Save to file…** y envía el archivo al iPhone por AirDrop, iCloud Drive o cable.
4. En SideInstaller, toca **Importar archivo de emparejamiento** (o **Sustituir**) y elígelo.

Un archivo de emparejamiento exportado desde [iLoader](https://github.com/nab138/iloader) (**Manage Pairing File** ›
**Export**) también sirve.

## ¿Es SideInstaller seguro?

SideInstaller está creado pensando en la seguridad y la privacidad. La app funciona por completo en local
y es de código abierto, así que cualquiera puede comprobar exactamente qué hace.

**Tus credenciales de Apple nunca salen de tu dispositivo.** Se usan en local, solo para firmar e instalar tus
apps, y nunca se transmiten, se registran ni se recopilan de ninguna forma.

**Sin servidor, sin analítica, sin cuenta.** No se recopila nada y no hay nada que registrar.

**Totalmente auditable.** Cada línea se puede verificar en el código fuente.

> [!WARNING]
> Todo lo anterior es cierto para **este** repositorio y las compilaciones publicadas desde él. **No** es una garantía
> que se aplique a forks, IPAs refirmados ni copias que encuentres en otro sitio; esos pueden modificarse para robar el
> Apple ID que introduzcas en ellos. Si no lo has conseguido en
> https://sideinstaller.net/, no le confíes tus
> credenciales.

## Estructura del proyecto

| Ruta | Qué contiene |
| :-- | :-- |
| `ios-app/` | La app SwiftUI: interfaz, motor de instalación, gestión de certificados y traducciones |
| `ios-live-activity/` | La extensión del widget que dibuja el código de emparejamiento en la Dynamic Island y en la pantalla de bloqueo |
| `ios-tests/` | Las pruebas unitarias de la app (`SideInstallerTests`) |
| `rust-core/` | El núcleo en Rust compilado en `SideInstallerFFI.xcframework` |
| `scripts/` | Scripts de compilación, comprobación y lanzamiento |
| `.github/` | Flujos que revisan las pull requests, compilan el IPA sin firmar, lo publican como versión y se lo entregan al firmante |

Las compilaciones firmadas y la página de instalación están en [FrizzleM/SideInstaller-Signed](https://github.com/FrizzleM/SideInstaller-Signed):
firman el IPA de cada versión con todos los certificados, adjuntan los IPA firmados a una versión propia y despliegan
[sideinstaller.net](https://sideinstaller.net/). Ningún IPA se incluye nunca en ninguno de los dos repositorios.

siboot, que instala SideInstaller [desde el propio iPhone](#cómo-usarlo),
está en [FrizzleM/siboot](https://github.com/FrizzleM/siboot). Compila los crates incluidos en este repositorio
y el `apple_session.rs` y `error_text.rs` de rust-core a través de un submódulo fijado en un commit, de modo que
un cambio aquí solo llega a siboot cuando cambia esa fijación.

## Contribuir

Se agradecen issues y pull requests. Si informas de un error, incluye tu versión de iOS, la versión de la app
y el paso en que falló.

Todas las pull requests se comprueban con el flujo `checks`: las pruebas y clippy de Rust, una compilación de
simulador con las pruebas unitarias de la app y las traducciones (una cadena añadida a la app necesita una entrada
en cada `ios-app/*Strings.swift`). Las mismas comprobaciones se ejecutan en un Mac con `scripts/test-rust.sh`,
`scripts/check-ios.sh` (en un clon limpio, ya que genera el proyecto de Xcode) y
`scripts/check_translations.py`.

## Licencia

Consulta [LICENSE.md](LICENSE.md). En resumen: puedes leer, modificar y compartir el **código fuente**, con
atribución y para fines no comerciales. La redistribución de las compilaciones oficiales (IPA) o la monetización
del proyecto de cualquier forma requiere permiso por escrito.

<div align="center">

**SideInstaller de [FrizzleM](https://github.com/FrizzleM)** · Las traducciones de la documentación en este fork son contribuciones de la comunidad; la app sigue siendo © FrizzleM.

</div>
