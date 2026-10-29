# LiveRoom — Changelog / Registro modifiche

## v1.0.0-beta.2 (versionCode 2) — Public Beta

### English

**Privacy and transparency**

- New first-launch privacy overview (English/Italian, works offline). It is
  shown before the app creates its random installation identifier or contacts
  the activation service, and can be reopened from the activation, consent
  and home screens. It is an information notice, not a consent request.
- Photos: embedded metadata (EXIF location/camera/date, thumbnail, XMP, IPTC,
  comments) is now removed from every JPEG before it is sent. A minimal
  orientation value may be kept so the picture is not rotated. Photos in other
  formats are re-encoded to JPEG first; if a clean JPEG cannot be produced,
  nothing is sent and an error is shown.
- The temporary copy that the Android photo picker creates in the app's
  private cache is deleted by the app right after the photo is read (best
  effort; a copy can remain if Android terminates the app at that moment).
- Corrected in-app wording that overstated what the app does ("no data
  stored" style messages). The app keeps no conversation history, but
  technical activation data exists separately.
- The live typing field no longer asks the keyboard for autocorrect or
  personalised learning.

**Other**

- Version 1.0.0-beta.2, versionCode 2. Same package name and signing
  certificate as beta.1: install over the existing app, do not uninstall.
- No change to licences, activation rules or the connection protocol.
- Public documentation: a full Privacy Notice (PRIVACY.md) is published with
  this release.

### Italiano

**Privacy e trasparenza**

- Nuova panoramica sulla privacy al primo avvio (inglese/italiano, funziona
  offline). Viene mostrata prima che l'app crei l'identificativo di
  installazione casuale o contatti il servizio di attivazione, e si può
  riaprire dalle schermate di attivazione, consenso e home. È
  un'informativa, non una richiesta di consenso.
- Foto: i metadati incorporati (posizione/fotocamera/data EXIF, miniatura,
  XMP, IPTC, commenti) vengono ora rimossi da ogni JPEG prima dell'invio. Può
  restare un valore minimo di orientamento per non ruotare l'immagine. Le foto
  in altri formati vengono prima ricodificate in JPEG; se non si ottiene un
  JPEG pulito, non viene inviato nulla e compare un errore.
- La copia temporanea creata dal selettore foto di Android nella cache privata
  dell'app viene eliminata dall'app subito dopo la lettura della foto (al
  meglio delle possibilità; una copia può restare se Android termina l'app in
  quel momento).
- Corretti i testi dell'app che promettevano più di quanto l'app garantisce
  (messaggi del tipo "nessun dato memorizzato"). L'app non conserva
  cronologia delle conversazioni, ma esistono separatamente dati tecnici di
  attivazione.
- Il campo di scrittura live non richiede più alla tastiera correzione
  automatica e apprendimento personalizzato.

**Altro**

- Versione 1.0.0-beta.2, versionCode 2. Stesso nome pacchetto e stesso
  certificato di firma della beta.1: installa sopra l'app esistente, non
  disinstallare.
- Nessuna modifica a licenze, regole di attivazione o protocollo di
  connessione.
- Documentazione pubblica: con questa release è pubblicata l'Informativa
  Privacy completa (PRIVACY.md).

---

## v1.0.0-beta.1 — internal preparation / preparazione interna

Not published as a public release. / Non pubblicata come release pubblica.

- Initial build for public-beta preparation: live typing over WebRTC, two
  participants per room, photo sharing, Android 7.0+ (API 24).
- Build interna per la preparazione della beta pubblica: scrittura live
  tramite WebRTC, due partecipanti per stanza, condivisione foto,
  Android 7.0+ (API 24).

---

Copyright (c) 2026 LiveRoom. All rights reserved.
