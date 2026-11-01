# LiveRoom — Public Beta

**Live typing. No send button. Just two people.**

## Download Android & iPhone

**Android - Public Beta 2**

[Download Android APK](https://github.com/manicons/LiveRoom-Beta/releases/tag/v1.0.0-beta.2)

Android 7.0+ (API 24). Signed APK.

**iPhone - Experimental iOS Beta**

[Download iPhone IPA](https://github.com/manicons/LiveRoom-Beta/releases/download/v1.0.0-beta.2/LiveRoom-iOS-Release-unsigned.ipa)

**iPhone installation guides / Guide installazione iPhone**

- [Italiano - Guida PDF](https://github.com/manicons/LiveRoom-Beta/releases/download/v1.0.0-beta.2/LiveRoom_Guida_iPhone_IT_aggiornata.pdf)
- [English - PDF Guide](https://github.com/manicons/LiveRoom-Beta/releases/download/v1.0.0-beta.2/LiveRoom_iPhone_Installation_Guide_EN_updated.pdf)

**EN:** The iOS IPA is unsigned and requires signing before installation. LiveContainer has been tested successfully on iPhone. SideStore instructions are included but have not yet been verified with this IPA.

**IT:** L'IPA iOS non e firmata e richiede una procedura di firma prima dell'installazione. LiveContainer e stato testato con successo su iPhone. La procedura SideStore e documentata ma non ancora verificata con questa IPA.

Both platforms are free during public beta. Ages 16+.

---

**Android:** 1.0.0-beta.2 (versionCode 2) - Android 7.0+ | **iOS:** Experimental unsigned IPA (build 2)

---

## 🇬🇧 English

LiveRoom is available for Android and iPhone (experimental iOS beta). It lets two people share text in real time,
while they type. There is no Send button.

### Features

- Live typing shared as you write, without pressing Send
- Maximum 2 participants per room
- Text and photos are exchanged directly between the two devices
  through a WebRTC DataChannel
- Photo sharing from the gallery or the camera
- No conversation history: content is not saved by the app
- Direct peer-to-peer connection, or a TURN relay when a direct
  connection is not possible

### How your conversation travels

- Text and photos are exchanged between the two participants through a
  WebRTC DataChannel, which is encrypted in transit.
- With the official app, the LiveRoom backend does not receive the content
  of your conversations.
- The backend is used for signaling (setting up the connection), for
  technical activation data, and, when needed, a TURN relay can forward the
  encrypted traffic.
- Before a JPEG photo is sent, the app removes embedded metadata (such as
  EXIF location, camera and date information). The picture itself is
  unchanged, so anything visible in it is visible to the other participant.
- These statements concern LiveRoom's own services. They cannot prevent the
  other participant from taking a screenshot, photographing the screen or
  saving content on their own device.

See the [FAQ](FAQ.md) for details.

### Access and activation

- LiveRoom is **free during the Public Beta** testing period. Access
  conditions may change after the beta.
- LiveRoom Public Beta is intended for people aged 16 or over.
- No traditional account is required. The official app asks for an
  activation code before it can be used.
- An activation code must be redeemed within **5 minutes**; after that it
  expires and you need a new one.
- Current licences last **12 months** or are **permanent**, depending on the
  type assigned.
- Request a free beta code in the `#request-code` channel of the official
  Discord server.
- The app creates a random installation identifier on your device after you
  have read the in-app privacy overview. It is used for activation and licence
  checks (see the [FAQ](FAQ.md)).

### Download

Official Android APK files are distributed **only** through
[GitHub Releases](https://github.com/manicons/LiveRoom-Beta/releases)
of this repository. Each release includes a SHA-256 checksum.

Minimum requirement: Android 7.0 (API 24).

See the [Installation Guide](INSTALL.md) — including how to update without
uninstalling.

### Community and support

- Discord: https://discord.gg/ACPENuHcVJ
- Support: liveroom.beta.support@gmail.com

---

## 🇮🇹 Italiano

LiveRoom è disponibile su Android e iPhone (beta iOS sperimentale) e permette a due persone di condividere testo
in tempo reale, mentre scrivono. Non c'è il pulsante Invia.

### Funzionalità

- Scrittura condivisa mentre si digita, senza premere Invia
- Massimo 2 partecipanti per stanza
- Testo e foto passano direttamente tra i due dispositivi
  tramite un DataChannel WebRTC
- Condivisione di foto dalla galleria o dalla fotocamera
- Nessuna cronologia delle conversazioni: l'app non salva i contenuti
- Connessione diretta peer-to-peer, oppure relay TURN quando la connessione
  diretta non è possibile

### Come viaggia la tua conversazione

- Testo e foto vengono scambiati tra i due partecipanti tramite un
  DataChannel WebRTC, cifrato durante il trasporto.
- Con l'app ufficiale, il backend di LiveRoom non riceve il contenuto delle
  conversazioni.
- Il backend è usato per il signaling (instaurazione della connessione) e per
  i dati tecnici di attivazione; quando serve, un relay TURN può inoltrare il
  traffico cifrato.
- Prima dell'invio di una foto JPEG, l'app rimuove i metadati incorporati
  (per esempio posizione EXIF, informazioni su fotocamera e data). L'immagine
  non cambia: ciò che vi è visibile resta visibile all'altro partecipante.
- Queste affermazioni riguardano i servizi di LiveRoom. Non possono impedire
  all'altro partecipante di fare uno screenshot, fotografare lo schermo o
  salvare i contenuti sul proprio dispositivo.

Maggiori dettagli nelle [FAQ](FAQ.md).

### Accesso e attivazione

- LiveRoom è **gratuito durante la Beta Pubblica**. Le condizioni di accesso
  potranno cambiare al termine della beta.
- LiveRoom Public Beta è destinata a persone di almeno 16 anni.
- Non serve un account tradizionale. L'app ufficiale chiede un codice di
  attivazione prima di poter essere usata.
- Un codice di attivazione va riscattato entro **5 minuti**; dopo scade e ne
  serve uno nuovo.
- Le licenze attuali durano **12 mesi** oppure sono **permanenti**, in base al
  tipo assegnato.
- Richiedi un codice beta gratuito nel canale `#request-code` del server
  Discord ufficiale.
- L'app crea sul tuo dispositivo un identificativo di installazione casuale
  dopo che hai letto la panoramica sulla privacy nell'app. Serve per
  l'attivazione e i controlli della licenza (vedi le [FAQ](FAQ.md)).

### Download

Le APK Android ufficiali sono distribuite **solo** tramite le
[GitHub Releases](https://github.com/manicons/LiveRoom-Beta/releases)
di questo repository. Ogni release include un checksum SHA-256.

Requisito minimo: Android 7.0 (API 24).

Consulta la [Guida di installazione](INSTALL.md), compreso come aggiornare
senza disinstallare.

### Community e assistenza

- Discord: https://discord.gg/ACPENuHcVJ
- Assistenza: liveroom.beta.support@gmail.com

---

## Documentation / Documentazione

- [Installation / Installazione](INSTALL.md)
- [FAQ](FAQ.md)
- [Privacy Notice / Informativa Privacy](PRIVACY.md)
- [Changelog](CHANGELOG.md)

## Source code / Codice sorgente

This repository contains public documentation and official binary
distributions only. The Flutter and Node.js source code is private.

Questo repository contiene esclusivamente documentazione pubblica e
distribuzioni binarie ufficiali. Il codice sorgente Flutter e Node.js è privato.

Copyright (c) 2026 LiveRoom. All rights reserved.
