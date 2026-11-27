<div align="center">

<img src="app-icon.png" alt="SideInstaller" width="120" />

# SideInstaller

**Instale o SideStore e o LiveContainer diretamente no seu iPhone — sem precisar de PC.**

[![Install](https://img.shields.io/badge/Install-SideInstaller-2ea44f?style=for-the-badge)](https://sideinstaller.net/)
[![Version](https://img.shields.io/badge/version-2.2.0-2669ed?style=for-the-badge)](CHANGELOG.md)
[![Platform](https://img.shields.io/badge/platform-iOS-lightgrey?style=for-the-badge&logo=apple)](#requisitos)
[![License](https://img.shields.io/badge/license-Custom-orange?style=for-the-badge)](LICENSE.md)

🌐 **Language / 语言:** [English](README.md) · [简体中文](README.zh-CN.md) · [Español](README.es.md) · [Italiano](README.it.md) · [Tiếng Việt](README.vi.md) · [Français](README.fr.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Português](README.pt-BR.md) · [Türkçe](README.tr.md)

</div>

---

> [!CAUTION]
> **Instale o SideInstaller apenas pela fonte oficial.**
>
> Este projeto é de código aberto, o que significa que qualquer pessoa pode bifurcar o código, inserir um ladrão de credenciais que
> envia seu Apple ID e sua senha para o próprio servidor, recompilá-lo e redistribuí-lo com o mesmo
> nome e ícone. Uma bifurcação maliciosa é idêntica ao app real por fora.
>
> As **únicas** versões que publico são:
> - **Site:** https://sideinstaller.net/
> - **Repositório:** https://github.com/FrizzleM/SideInstaller
>
> Não instale o SideInstaller de nenhum outro site, fonte do AltStore, canal do Telegram, servidor do Discord,
> repositório de apps ou espelho, não importa quão oficial pareça. Redistribuir minhas versões sem consentimento explícito também é proibido pela
> [licença](LICENSE.md).
>
> Existe um site falso chamado "sideinstaller.com". Esse site **não é legítimo** e provavelmente fornece malware. Certifique-se de
> baixar apenas das **fontes oficiais** listadas acima.

> [!NOTE]
> **Sobre esta bifurcação — apenas documentação.** Esta bifurcação existe somente para traduzir e esclarecer estas
> instruções. Ela não compila nem distribui **nenhum binário do app**; todos os links de download ainda apontam para as
> fontes oficiais acima. O código-fonte do app aqui está inalterado. Sempre baixe o app real em
> https://sideinstaller.net/ — nunca de uma bifurcação, espelho ou IPA recompilado.

---

## Nesta página

- [O que é](#o-que-é)
- [Requisitos](#requisitos)
- [Como usar](#como-usar)
  - [Método A — siboot (iOS 27+, sem PC)](#método-a--siboot-ios-27-sem-pc)
  - [Método B — certificado corporativo (iOS mais antigo)](#método-b--certificado-corporativo-ios-mais-antigo)
  - [Links](#links)
  - [Atalhos](#atalhos)
- [Compatibilidade](#compatibilidade)
  - [iOS 26.4 a 26.x: um arquivo de pareamento remoto](#ios-264-a-26x-um-arquivo-de-pareamento-remoto)
- [O SideInstaller é seguro?](#o-sideinstaller-é-seguro)
- [Estrutura do projeto](#estrutura-do-projeto)
- [Como contribuir](#como-contribuir)
- [Licença](#licença)

---

## O que é

O SideStore e o LiveContainer são atualmente a melhor forma de fazer sideload no iOS. Mas há um grande
problema: instalá-los exige um PC, que muitas pessoas não têm. Foi por isso que criei o SideInstaller,
um app iOS gratuito e de código aberto que os instala diretamente no seu iPhone, sem precisar de PC.

O SideInstaller cuida de todo o processo de configuração no próprio dispositivo. Ele faz o pareamento, o
provisionamento e a instalação — etapas que normalmente obrigam você a conectar a um computador e usar
ferramentas de desktop — tudo em um único app rodando no telefone. Quando termina, você tem uma
instalação completa e funcional do SideStore e do LiveContainer, pronta para fazer sideload dos seus próprios apps.

Tudo foi feito para ser simples. Não há configuração complicada, nem linha de comando, nem necessidade
de entender como funciona a engrenagem por trás disso. Basta abrir o app, seguir alguns passos e deixar
que ele faça o resto. Para quem sempre quis fazer sideload mas não tinha um Mac ou PC, isso remove a
maior barreira para começar.

E, como é código aberto, você não precisa acreditar apenas na minha palavra. O código completo está
disponível para qualquer pessoa ler, auditar ou contribuir, para que você veja exatamente o que está
rodando no seu dispositivo.

## Requisitos

Antes de começar, certifique-se de ter:

- **Um iPhone ou iPad** com **iOS 27+** — no iOS 17.4+ com um arquivo de pareamento feito num computador; a partir do
  iOS 26.4, é necessário um [arquivo de pareamento remoto](#ios-264-a-26x-um-arquivo-de-pareamento-remoto). Veja a
  [tabela de compatibilidade](#compatibilidade).
- **Wi-Fi** (apenas na primeira vez).
- **Modo de Desenvolvedor** ativado (para o método siboot).
- **Suas credenciais da conta Apple** — usadas apenas no dispositivo para assinar apps; nunca coletadas.

## Como usar

Há dois métodos de instalação. Escolha o que corresponde à sua versão do iOS:

| Sua situação | Método | Precisa de PC? |
| --- | --- | --- |
| iOS 27 ou posterior | [Método A — siboot](#método-a--siboot-ios-27-sem-pc) (recomendado) | Não |
| iOS 17.4 – 26.7, ou o siboot não funciona para você | [Método B — certificado corporativo](#método-b--certificado-corporativo-ios-mais-antigo) | Sim, uma vez |

### Método A — siboot (iOS 27+, sem PC)

O [siboot](https://github.com/FrizzleM/siboot) instala o SideInstaller a partir do próprio iPhone, assinado
com sua conta Apple: sem computador e sem certificado. Você precisa do **iOS 27 ou posterior**, de **Wi-Fi** e do
**Modo de Desenvolvedor ativado**. O site [sideinstaller.net](https://sideinstaller.net/) mostra as etapas 1 a 3
visualmente.

#### Etapa 1 — Instale três apps gratuitos

Instale os três pela App Store:

- [rootshell](https://apps.apple.com/app/rootshell-local-terminal-ssh/id6755794662)
- [Open Minis](https://apps.apple.com/app/id6759188481)
- [LocalDevVPN](https://apps.apple.com/app/id6755608044)

#### Etapa 2 — Faça o pareamento no rootshell

1. No rootshell, ative **Ajustes › Location Diary Mode › Session Only**.
2. Toque em **Local Shell** e depois em **Open**, no canto superior direito.
3. Execute estes comandos **uma linha por vez**:

   ```sh
   curl -fsSLO https://raw.githubusercontent.com/FrizzleM/siboot/main/rootshell/bin/siboot-pair.wasm
   ```

   ```sh
   ifconfig en0 > ifconfig.txt
   ```

   ```sh
   ./siboot-pair.wasm
   ```

4. Abra **Ajustes › Privacidade e Segurança › Modo de Desenvolvedor**, role até o fim, toque em
   **Parear com o siboot** e digite sua senha do dispositivo e o código que o rootshell mostra.
5. **Deixe o rootshell rodando** — não o feche.

#### Etapa 3 — Instale pelo Open Minis

1. Conecte o **LocalDevVPN**.
2. No **Open Minis**, toque no ícone do console no canto superior direito e depois em **Shell Terminal**.
3. Execute:

   ```sh
   wget -qO- https://raw.githubusercontent.com/FrizzleM/siboot/main/minis/install.sh | sh
   ```

4. Digite o código de transferência que o rootshell mostra — **apenas na primeira vez**; depois disso, o siboot usa o
   arquivo de pareamento que salvou.
5. Digite o **e-mail**, a **senha** e o **código de verificação** da sua conta Apple.
6. **Mantenha o Minis aberto** até ele dizer que terminou. Na primeira vez, confie na sua conta Apple em
   **Ajustes › Geral › VPN e Gerenciamento de Dispositivo**.

#### Etapa 4 — Abra o SideInstaller

Com o **LocalDevVPN conectado**, entre com sua conta Apple e toque em **Instalar o SideStore** ou em
**Instalar o SideStore + LiveContainer**. Pronto.

> **Depois do pareamento:** executar `siboot developer-mode` no Open Minis pede ao iPhone que mostre a chave do Modo de
> Desenvolvedor nos Ajustes; adicione `--turn-on` para ativá-la. Veja os
> [detalhes](https://github.com/FrizzleM/siboot/blob/main/minis/README.md#developer-mode).

### Método B — certificado corporativo (iOS mais antigo)

Em versões do iOS anteriores à 27, ou se o siboot não funcionar para você, instale o SideInstaller com um dos
certificados corporativos em [sideinstaller.net/#legacy](https://sideinstaller.net/#legacy) e continue a partir da
**Etapa 4** acima. (Versões mais antigas também precisam de um arquivo de pareamento — veja [Compatibilidade](#compatibilidade).)

### Links

O SideInstaller abre três tipos de link `sideinstaller://` e pede confirmação antes de agir sobre qualquer um deles:

| Link | O que ele faz |
| --- | --- |
| `sideinstaller://install?url=<percent-encoded https link to an .ipa>` | Baixa o IPA como .ipa personalizado e o instala — para instalações com um toque a partir de um site. |
| `sideinstaller://pairingFile?data=<base64 pairing file>` | Importa um arquivo de pareamento. O SideStore devolve um quando solicitado com `sidestore://pairing?urlname=sideinstaller` — é o que **Obter do SideStore** no cartão Arquivo de pareamento faz. |
| `sideinstaller://certificate?data=<base64 PKCS#12>&password=<password>` | Faz o SideInstaller assinar com esse certificado a partir de então, assim que a Apple o listar entre os certificados do seu Apple ID. |

**Usar o certificado do SideStore** (no pop-up "Já existe um certificado" e na página Certificados) pede ao SideStore o próprio com
`sidestore://certificate?callback_template=sideinstaller://certificate?data=$(BASE64_CERT)&password=$(PASSWORD)`
(codificado em porcentagem), para que o único certificado de um Apple ID gratuito sirva aos dois apps. Essa resposta é o único link que
não pede confirmação de novo: o SideStore acabou de perguntar se poderia exportá-lo.

O Discord e a maioria dos apps de conversa só tornam links `https://` tocáveis, então, para postar um link de instalação lá, use
`https://sideinstaller.net/open.html?url=<percent-encoded https link to an .ipa>`. Essa página mostra de onde o IPA é
baixado e o entrega a `sideinstaller://install`, com um botão para quando o iOS não abrir o app sozinho.

### Atalhos

As ferramentas do SideInstaller são ações no app Atalhos, para que um atalho, uma automação, o botão de Ação ou a Siri possam
executá-las:

- **Simulação de localização:** Set Location (um lugar escolhido no mapa, um endereço ou uma localização de outra
  ação), Set Location to Coordinates, Set Location to Saved Place, Reset Location, Get Spoofed Location, Is Location
  Spoofed, Play GPX Route, Travel to Place (uma rota planejada no OpenStreetMap, percorrida a pé, de bicicleta ou de
  carro no limite de velocidade de cada rua), Stop Route, Save Place e Delete Saved Place.
- **Apps instalados por sideload:** Get Sideloaded Apps (cada um com o dia em que expira e os dias restantes),
  Refresh All Apps e Refresh App.
- **Instalação:** Install App (SideStore, LiveContainer + SideStore, Madeira ou AltStore, estável ou nightly),
  Install IPA e Install IPA from URL. Elas abrem o SideInstaller, pois uma instalação pode parar para pedir algo lá.
- **Pareamento e outros:** Get Pairing File, Import Pairing File, Install Pairing File into Apps, Show Developer Mode in
  Settings, Is LocalDevVPN Connected, Connect LocalDevVPN e Get Activity Log.

As outras ações rodam em segundo plano, pelo LocalDevVPN, como as próprias páginas do app, então o túnel precisa
estar ativo: conecte-o antes delas (a ação Set VPN dos Atalhos pode fazer isso) ou ative **Iniciar o LocalDevVPN quando
for preciso**, e a ação pede para continuar no SideInstaller a fim de conectá-lo. Uma localização definida por um
atalho permanece até Reset Location: o SideInstaller continua rodando em segundo plano para mantê-la, como quando você
define uma no app. A Siri reconhece "Spoof my location to *saved place* with SideInstaller", "Reset my location with
SideInstaller" e "Refresh my apps with SideInstaller". Os nomes das ações são em inglês; o que elas dizem ao serem
executadas está no idioma do SideInstaller.

## Compatibilidade

| iOS | É compatível? |
| --- | --- |
| 27+ | ✅ Sim — sem PC com o siboot |
| 26.4 – 26.7 | ⚠️ Sim, mas [é necessário um arquivo de pareamento remoto](#ios-264-a-26x-um-arquivo-de-pareamento-remoto), o que exige um PC |
| 17.4 – 26.3 | ⚠️ Sim, mas [é necessário um arquivo de pareamento](https://docs.sidestore.io/docs/advanced/alternative#pairing), o que exige um PC |
| <17.4 | ❌ Não |

### iOS 26.4 a 26.x: um arquivo de pareamento remoto

A partir do iOS 26.4, o iPhone derruba a conexão com arquivos de pareamento lockdown (do jitterbugpair,
`pymobiledevice3 lockdown pair` ou do **Lockdown** do idevice_pair) assim que eles se conectam pelo
LocalDevVPN, então não podem mais ser usados no iPhone, por mais novos que sejam. Um arquivo de pareamento
remoto (RPPairing) ainda funciona:

1. Num Mac, PC com Windows ou computador Linux, abra [idevice_pair](https://github.com/jkcoxson/idevice_pair/releases/latest)
   e conecte o iPhone. Toque em **Confiar** se ele pedir.
2. Selecione o iPhone, escolha **Remote pairing**, clique em **Create** e mantenha o iPhone desbloqueado até
   terminar.
3. Clique em **Save to file…** e envie o arquivo ao iPhone por AirDrop, iCloud Drive ou cabo.
4. No SideInstaller, toque em **Importar arquivo de pareamento** (ou em **Substituir**) e escolha-o.

Um arquivo de pareamento exportado do [iLoader](https://github.com/nab138/iloader) (**Manage Pairing File** ›
**Export**) contém os dois tipos e também funciona.

## O SideInstaller é seguro?

O SideInstaller foi criado com segurança e privacidade em mente. O app é totalmente local e de código aberto, o que
significa que qualquer pessoa pode inspecionar exatamente o que ele faz.

**Suas credenciais da Apple nunca saem do seu dispositivo.** Elas são usadas localmente, apenas para assinar e
instalar seus apps, e nunca são transmitidas, registradas em log ou coletadas de qualquer forma.

**Sem servidor, sem analytics, sem conta.** Nada é coletado e não há nada para se cadastrar.

**Totalmente auditável.** Cada linha pode ser verificada no código-fonte.

> [!WARNING]
> Tudo acima é verdadeiro para **este** repositório e para as versões publicadas a partir dele. **Não** é uma garantia
> que se aplica a bifurcações, IPAs reassinados ou cópias que você encontrar em outro lugar; eles podem ser modificados
> para roubar o Apple ID que você digitar neles. Se você não baixou de
> https://sideinstaller.net/, não confie nele suas
> credenciais.

## Estrutura do projeto

| Caminho | O que contém |
| :-- | :-- |
| `ios-app/` | O app SwiftUI — interface, motor de instalação, tratamento de certificados e traduções |
| `ios-live-activity/` | A extensão do widget que desenha o código de pareamento na Dynamic Island e na Tela de Bloqueio |
| `ios-tests/` | Os testes unitários do app (`SideInstallerTests`) |
| `rust-core/` | O núcleo em Rust compilado em `SideInstallerFFI.xcframework` |
| `scripts/` | Scripts de compilação, verificação e lançamento |
| `.github/` | Fluxos de trabalho que verificam pull requests, compilam o IPA não assinado, publicam-no como uma versão e o entregam ao assinador |

As versões assinadas e a página de instalação ficam em [FrizzleM/SideInstaller-Signed](https://github.com/FrizzleM/SideInstaller-Signed):
ela assina o IPA de cada versão com todos os certificados, anexa os IPAs assinados a uma versão própria e
publica [sideinstaller.net](https://sideinstaller.net/). Nenhum IPA é enviado para nenhum dos dois repositórios.

O siboot, que instala o SideInstaller [pelo próprio iPhone](#como-usar),
fica em [FrizzleM/siboot](https://github.com/FrizzleM/siboot). Ele compila os crates vendorizados deste repositório
e o `apple_session.rs` e o `error_text.rs` do rust-core por meio de um submódulo fixado em um commit, então uma
alteração aqui só chega ao siboot quando essa fixação muda.

## Como contribuir

Issues e pull requests são bem-vindos. Se você estiver relatando um bug, inclua sua versão do iOS, a versão do app
e a etapa em que falhou.

Todo pull request é verificado pelo fluxo `checks`: os testes do Rust e o clippy, uma compilação para simulador com
os testes unitários do app e as traduções (uma string adicionada ao app precisa de uma entrada em cada
`ios-app/*Strings.swift`). As mesmas verificações rodam num Mac com `scripts/test-rust.sh`,
`scripts/check-ios.sh` (num clone limpo, já que ele gera o projeto Xcode) e
`scripts/check_translations.py`.

## Licença

Veja [LICENSE.md](LICENSE.md). Em resumo: você pode ler, modificar e compartilhar o **código-fonte**, com
atribuição, para fins não comerciais. Redistribuir as versões oficiais (IPAs) ou monetizar o projeto de qualquer
forma exige permissão por escrito.

<div align="center">

**SideInstaller por [FrizzleM](https://github.com/FrizzleM)** · As traduções da documentação nesta bifurcação são contribuições da comunidade; o app permanece © FrizzleM.

</div>
