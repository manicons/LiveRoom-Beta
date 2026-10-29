# LiveRoom — FAQ / Domande frequenti

**Public Beta 1.0.0-beta.2**

---

## English

### What is LiveRoom?

An Android app that lets two people communicate through live typing: text
appears for the other person while you write. There is no Send button.

### Is LiveRoom free?

Yes, during the Public Beta. Access conditions may change after the beta.

### Do I need an account?

No traditional account (no email or password). You do need an activation
code; the official app asks for it before it can be used. A code is valid for
5 minutes before redemption, then it expires. Current licences last 12 months
or are permanent, depending on the type assigned. Request a free beta code in
the `#request-code` channel of the official Discord server.

### Who can use LiveRoom?

The Public Beta is intended for people aged 16 or over.

### How many people can join a room?

A maximum of two participants.

### Are conversations saved?

The app keeps no conversation history: text and photos exist in the memory of
the two devices while the room is open. With the official app, text and photos
go directly between the two participants through a WebRTC DataChannel and are
not sent to the LiveRoom backend.

Some technical data does exist, separately from conversations: activation and
licence records, administrative records, and the connection-setup data
described below.

This cannot stop the other participant from taking a screenshot,
photographing the screen or otherwise saving what they see. Do not share
anything with someone you do not trust.

### What data does LiveRoom use?

- **Installation identifier**: a random ID created on your device after you
  read the in-app privacy overview. It is kept in Android secure storage and
  sent to the activation service to redeem and check your licence. It is not
  linked to a traditional account.
- **Activation and licence data**: the activation code you enter, the
  activation and expiry dates, and the licence status.
- **Connection setup (signaling)**: room code and the technical messages
  (SDP/ICE) that two devices need to connect. These can contain network
  addresses. They are relayed in real time and are not conversation content.
- **Network services**: a STUN service helps discover your network address, and a
  TURN relay may forward encrypted traffic if a direct connection fails.
- **On your device**: a cached copy of the app configuration, a flag that
  you have seen the privacy overview, the installation identifier and the
  licence expiry date. No conversation history.

LiveRoom is run by two joint controllers, Matteo Manicone and Alessandro
Cugnasco. Read the full [Privacy Notice](PRIVACY.md). We do not claim that no
personal data is processed.

### Is communication encrypted?

WebRTC DataChannels are encrypted in transit. When a direct connection is not
possible, a TURN relay can forward this encrypted traffic. We do not make
guarantees beyond this: for example, the other participant's device receives
the content in readable form, and in a direct connection the other
participant's device can see your network (IP) address.

### Can I send photos? What happens to them?

Yes, from the gallery or the camera, in a live session.

- Before sending, the app removes embedded metadata from JPEG photos (EXIF
  location, camera and date, thumbnail, XMP, IPTC, comments). A minimal
  orientation value may remain so the photo is not rotated. The visible
  content of the picture is not changed, so a face, a document or a place
  that appears in it is visible to the other person.
- Other formats are converted to JPEG first. If a clean JPEG cannot be
  produced, nothing is sent and the app shows an error.
- The Android picker creates a temporary copy of the photo in the app's
  private cache. The app deletes that copy right after reading the photo.
  This is best effort: if Android terminates the app at that moment, a copy
  can remain until Android or the user clears the app cache. The original in
  your gallery is never changed or deleted by the app.
- The app does not save received photos to your gallery. They are held in
  memory while shown.
- If you use the camera, your camera app or phone may keep its own copy of the
  picture. That is outside LiveRoom's control.

### Which Android versions are supported?

Android 7.0 (API 24) or newer.

### Where can I download LiveRoom?

Only from the official GitHub Releases page:
https://github.com/manicons/LiveRoom-Beta/releases

Check the SHA-256 checksum as described in [INSTALL.md](INSTALL.md). LiveRoom
is not distributed on Google Play during the Public Beta.

### How do I update? Should I uninstall first?

No. Install the new APK over the old one. Uninstalling removes the app's local
data (installation identifier and licence record) and you may need a new
activation code. See [INSTALL.md](INSTALL.md).

### What is the privacy overview I see at first launch?

A short, offline, bilingual notice shown before the app creates its
installation identifier or contacts the activation service. It is
information, not a consent request. You can reopen it from the activation,
consent and home screens.

### How do I request a beta code or report a problem?

Discord: https://discord.gg/ACPENuHcVJ (`#request-code` to request a code,
`#bugs` for problems)
Email: liveroom.beta.support@gmail.com

Never share activation codes, private conversations or sensitive logs in
public.

---

## Italiano

### Che cos'è LiveRoom?

Un'app Android che permette a due persone di comunicare scrivendo in tempo
reale: il testo compare all'altra persona mentre scrivi. Non c'è il pulsante
Invia.

### LiveRoom è gratuito?

Sì, durante la Beta Pubblica. Le condizioni di accesso potranno cambiare al
termine della beta.

### Serve un account?

Nessun account tradizionale (niente email o password). Serve però un codice di
attivazione; l'app ufficiale lo chiede prima di poter essere usata. Un codice è
valido 5 minuti prima del riscatto, poi scade. Le licenze attuali durano
12 mesi oppure sono permanenti, in base al tipo assegnato. Richiedi un codice
beta gratuito nel canale `#request-code` del server Discord ufficiale.

### Chi può usare LiveRoom?

La Beta Pubblica è destinata a persone di almeno 16 anni.

### Quante persone possono entrare in una stanza?

Massimo due partecipanti.

### Le conversazioni vengono salvate?

L'app non conserva cronologia: testo e foto esistono nella memoria dei due
dispositivi finché la stanza è aperta. Con l'app ufficiale, testo e foto
passano direttamente tra i due partecipanti tramite un DataChannel WebRTC e
non vengono inviati al backend di LiveRoom.

Esistono però alcuni dati tecnici, separati dalle conversazioni: record di
attivazione e licenza, registri amministrativi e i dati di impostazione della
connessione descritti sotto.

Questo non può impedire all'altro partecipante di fare uno screenshot,
fotografare lo schermo o salvare in altro modo ciò che vede. Non condividere
nulla con chi non ritieni affidabile.

### Quali dati usa LiveRoom?

- **Identificativo di installazione**: un ID casuale creato sul tuo
  dispositivo dopo che hai letto la panoramica sulla privacy nell'app. È
  conservato nell'archivio sicuro di Android e inviato al servizio di
  attivazione per riscattare e controllare la licenza. Non è collegato a un
  account tradizionale.
- **Dati di attivazione e licenza**: il codice che inserisci, le date di
  attivazione e scadenza, lo stato della licenza.
- **Impostazione della connessione (signaling)**: codice stanza e messaggi
  tecnici (SDP/ICE) necessari ai due dispositivi per connettersi. Possono
  contenere indirizzi di rete. Sono inoltrati in tempo reale e non sono
  contenuto delle conversazioni.
- **Servizi di rete**: un servizio STUN aiuta a scoprire il tuo indirizzo di rete e un relay TURN può
  inoltrare traffico cifrato se la connessione diretta non riesce.
- **Sul tuo dispositivo**: una copia in cache della configurazione dell'app,
  un indicatore che hai visto la panoramica sulla privacy, l'identificativo di
  installazione e la data di scadenza della licenza. Nessuna cronologia delle
  conversazioni.

LiveRoom è gestito da due contitolari, Matteo Manicone e Alessandro
Cugnasco. Leggi l'[Informativa Privacy](PRIVACY.md) completa. Non affermiamo
che non venga trattato alcun dato personale.

### La comunicazione è cifrata?

I DataChannel WebRTC sono cifrati durante il trasporto. Quando la connessione
diretta non è possibile, un relay TURN può inoltrare questo traffico cifrato.
Non diamo garanzie oltre questo: per esempio, il dispositivo dell'altro
partecipante riceve il contenuto in chiaro e, in una connessione diretta, può
vedere il tuo indirizzo di rete (IP).

### Posso inviare foto? Che fine fanno?

Sì, dalla galleria o dalla fotocamera, durante una sessione live.

- Prima dell'invio, l'app rimuove i metadati incorporati dalle foto JPEG
  (posizione, fotocamera e data EXIF, miniatura, XMP, IPTC, commenti). Può
  restare un valore minimo di orientamento per non ruotare la foto. Il
  contenuto visibile dell'immagine non cambia: un volto, un documento o un
  luogo che compare è visibile all'altra persona.
- Gli altri formati vengono prima convertiti in JPEG. Se non si ottiene un
  JPEG pulito, non viene inviato nulla e l'app mostra un errore.
- Il selettore di Android crea una copia temporanea della foto nella cache
  privata dell'app. L'app elimina quella copia subito dopo aver letto la foto.
  È un'operazione al meglio delle possibilità: se Android termina l'app in
  quel momento, una copia può restare finché Android o l'utente non svuota la
  cache. L'originale nella tua galleria non viene mai modificato né
  eliminato dall'app.
- L'app non salva le foto ricevute nella tua galleria. Restano in memoria
  finché sono mostrate.
- Se usi la fotocamera, l'app fotocamera o il telefono potrebbero conservare
  una propria copia dello scatto. Questo è fuori dal controllo di LiveRoom.

### Quali versioni Android sono supportate?

Android 7.0 (API 24) o superiore.

### Dove posso scaricare LiveRoom?

Solo dalla pagina GitHub Releases ufficiale:
https://github.com/manicons/LiveRoom-Beta/releases

Controlla il checksum SHA-256 come indicato in [INSTALL.md](INSTALL.md).
Durante la Beta Pubblica LiveRoom non è distribuito su Google Play.

### Come aggiorno? Devo disinstallare prima?

No. Installa la nuova APK sopra la vecchia. La disinstallazione elimina i dati
locali dell'app (identificativo di installazione e record della licenza) e
potresti aver bisogno di un nuovo codice di attivazione. Vedi
[INSTALL.md](INSTALL.md).

### Che cos'è la panoramica sulla privacy del primo avvio?

Una breve informativa offline e bilingue mostrata prima che l'app crei
l'identificativo di installazione o contatti il servizio di attivazione. È
un'informazione, non una richiesta di consenso. Puoi riaprirla dalle
schermate di attivazione, consenso e home.

### Come richiedo un codice o segnalo un problema?

Discord: https://discord.gg/ACPENuHcVJ (`#request-code` per richiedere un
codice, `#bugs` per i problemi)
Email: liveroom.beta.support@gmail.com

Non pubblicare codici di attivazione, conversazioni private o log sensibili.

---

Copyright (c) 2026 LiveRoom. All rights reserved.
