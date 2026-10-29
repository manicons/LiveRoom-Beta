# LiveRoom — Privacy Notice / Informativa Privacy

Version / Versione: 2026-10-29 · Applies to app / Si applica all'app: **1.0.0-beta.2 (versionCode 2)**

How to read this notice: where we describe a retention period or practice we separate **adopted policy** (what the controllers have decided), **measure in place** (verified in the app/server code) and **measure still to be implemented**. Nothing is presented as in place unless it is.

Come leggere questa informativa: quando descriviamo un periodo di conservazione o una prassi distinguiamo **politica adottata** (decisa dai contitolari), **misura già attuata** (verificata nel codice di app/server) e **misura ancora da implementare**. Nulla è presentato come attuato se non lo è.

---

## English

### 1. Who is responsible (joint controllers)

LiveRoom is jointly developed and operated by **Matteo Manicone** and **Alessandro Cugnasco**. They jointly determine the purposes and means of the processing described here and act as **joint controllers** under Article 26 of Regulation (EU) 2016/679 (GDPR).

Privacy contact (common to both): **liveroom.beta.support@gmail.com**.

**Essence of the arrangement (Art. 26(2))**: the two controllers decide the purposes and means of LiveRoom together; privacy requests are handled jointly through the common contact above; each of them is responsible, together with the other, for this notice, for the security of the service and for answering requests, as allocated between them. Whatever the allocation, you may exercise your rights against either of them.

### 2. What this notice covers

The official LiveRoom Android app (1.0.0-beta.2), the LiveRoom signaling and activation service, and the support channels below. It does not cover other apps, your phone's operating system, or the other participant's device.

LiveRoom is a free Public Beta, intended for people aged **16 or over** (a choice of the service). This is an information notice; the app does not ask for a "consent" to use it, and nothing in it is a promise of anonymity.

### 3. Conversation content (text and photos)

- **Text** you type is sent to the other participant through a WebRTC DataChannel as you type. With the official app it is not sent to, and not stored by, the LiveRoom backend. The app keeps no conversation history.
- **Photos** you send also travel through a WebRTC DataChannel. Received photos are held in memory by the app and are not saved to the gallery by the app.
- **Encryption**: WebRTC DataChannels are encrypted in transit (DTLS). When a direct connection fails, a TURN relay can forward this encrypted traffic. We make no stronger claim.
- **Limits**: the other participant's device receives your content in readable form and can screenshot, photograph or record it. A direct connection reveals your IP address to the other participant. What you type may also pass through your own keyboard app; the live input asks the keyboard not to use autocorrect or personalised learning, but a keyboard may ignore that request.

### 4. Photo handling on your device

1. You choose a photo from the gallery or take one with the camera through the Android picker.
2. The picker creates a **temporary copy in the app's private cache**. The app reads it into memory and then **deletes that copy** (only files it received from the picker in its own cache; never your original gallery photo). This is best effort: if Android terminates the app at the wrong moment, a copy can remain until Android or you clear the app cache.
3. In memory, the app removes metadata from JPEG photos (EXIF including GPS and device/date data, thumbnail, XMP, IPTC, comments, trailing data) and may keep a minimal orientation value. Other formats are re-encoded to JPEG. If a clean JPEG cannot be produced, nothing is sent.
4. Metadata removal does not change what the picture shows.
5. If you use the camera, the camera app or phone may keep its own copy; that is outside LiveRoom.

This is based on the app's source code and automated tests; the private cache of the installed release app has not been inspected directly.

### 5. Data processed outside conversations

| Data | Where | Purpose | Notes |
|---|---|---|---|
| **Installation identifier** (random UUID) | Created on your device after the privacy overview; Android secure storage; sent to the activation service on activation and licence checks; stored with the licence | Link a licence to an installation; verify it | Not a traditional account. Removed from the device on uninstall or data clearing. Retention: section 8 |
| **Activation code** | Entered by you; sent to the activation service; stored server-side as a hash | Redeem a licence | Valid for 5 minutes before redemption |
| **Licence record** | Server: installation identifier, activation and expiry times (12 months, or permanent), revoked flag, last verification time, link to the code record. Device: expiry date | Operate access to the beta | The app re-checks the licence when it opens or resumes; if the server is unreachable it keeps its local state |
| **Administrative audit records** | Server database | Administration and security (record of operator actions such as creating, revoking or cleaning up codes) | Fields: time, action type, target type and identifier, an operator fingerprint, a details record |
| **Signaling data** (room code, invite token, SDP and ICE messages) | Relayed in real time by the signaling service | Set up the connection | SDP/ICE can include IP addresses and network details. Room state is kept in server memory only |
| **Network address (IP)** | Seen by the tunnelling service in front of the server, by STUN and TURN providers and, in a direct connection, by the other participant | Make the connection work; security | The server application is designed not to store IP addresses: it derives a short-lived pseudonymous key (rotating every 5 minutes), kept in memory for rate limiting and used in logs instead of the IP |
| **Configuration request** | At startup the app requests its configuration from the LiveRoom service (same address as signaling and activation); cached on the device | Keep server and ICE settings current | Normal web-request data (IP, user agent) is visible to the tunnelling service |
| **Local settings** | Device: configuration cache, "privacy overview seen" flag, installation identifier, licence expiry | App operation | No conversation history. The app includes no analytics, advertising or crash-reporting libraries |

Android permissions: internet, network state, change of network state, audio settings and (up to Android 11) Bluetooth, which come with the WebRTC library, and camera (requested when you choose to take a photo). The app does not request microphone, location, contacts or storage permissions.

### 6. Purposes and legal bases

| Purpose | Legal basis (GDPR Art. 6) |
|---|---|
| Provide the service you request: activation, licences where applicable, setting up the connection | 6(1)(b) |
| Security, abuse prevention and administrative records | 6(1)(f) legitimate interest, after assessing that it is necessary and does not override your rights; you may object (section 9) |
| Support requests | 6(1)(b) when about the service you use; otherwise 6(1)(f) |
| Legal obligations, only where actually applicable | 6(1)(c) |

We consider storing the installation identifier on your device strictly necessary to provide the service you request, which we assess also under Art. 122 of the Italian Privacy Code and the ePrivacy rules; no separate consent is requested for it.

LiveRoom is not designed for advertising, profiling or analysing conversation content.

### 7. Recipients, external services and transfers

We state only what is documented. "Not stated" means the provider's public documents that we reviewed (October 2026) do not say.

| Provider | What it does for LiveRoom | Role and documented facts |
|---|---|---|
| **LiveRoom service** | Signaling, activation, licences | Run by the joint controllers on infrastructure they operate; the server application writes logs only to standard output with sensitive values redacted |
| **zrok public share (zrok.io), NetFoundry, Inc.** (Charlotte, North Carolina, USA) | Tunnels requests from the app to the LiveRoom service (`liveroom.shares.zrok.io`) | A public share passes through the provider's public frontend, so we assume it can technically observe these requests (activation codes, installation identifiers, SDP/ICE; never conversation content) and may log technical data. NetFoundry's privacy policy states that it may transfer personal information across borders and does not describe zrok data handling, retention or its legal role: **not stated** |
| **Metered** (Next Path Software Consulting Inc., Ontario, Canada) | TURN relay, used only when a direct connection is not possible | Describes itself as data **processor** in its published data-processing agreement; states relayed media is not inspected, stored or recorded; logs connection metadata including IP addresses and ports for 30 days; relies on EU adequacy for Canada; sub-processors worldwide (e.g. AWS, Google Cloud, Hetzner); region restriction possible |
| **Google STUN** (`stun.l.google.com`) | Helps your device discover its public network address | Google's general privacy policy does not mention STUN servers specifically: **not stated**. Google Ireland Limited is the controller for Google services in the EEA |
| **GitHub** (GitHub, Inc. / GitHub B.V.) | Distribution of APK and documents | Controller of its own service data; certified to the EU-US Data Privacy Framework and uses standard contractual clauses; logs IP and usage data; retention periods **not stated** |
| **Discord** (Discord Netherlands BV for EEA users; Discord Inc., USA) | Community and the `#request-code` channel | Controller; uses standard contractual clauses and states compliance with the EU-US Data Privacy Framework; message retention refers to a separate policy |
| **Gmail** (Google) | Support mailbox liveroom.beta.support@gmail.com | A consumer Gmail account, under Google's terms; Google is the controller of its service data |

Some of these providers process data outside the European Economic Area. Safeguards are those the providers document (adequacy decisions, standard contractual clauses, Data Privacy Framework). We have not independently audited them.

### 8. Retention

Conversation text and photos are not stored by the LiveRoom backend, and the app keeps no history. Photo temporary copies: section 4.

| Data | Adopted policy (objective) | Status |
|---|---|---|
| Room state | Memory only, for as long as the room exists | **In place** (verified in server code) |
| Licence record and linked activation-code record and installation identifier | For the duration of the licence/relationship plus 12 months after it ends; a permanent licence is kept while active | **Still to be implemented**: the application contains no function that deletes licence records; an authorised deletion procedure will be set up |
| Administrative audit records | At most 12 months | **Still to be implemented**: the audit table has no deletion function; an authorised deletion procedure will be set up |
| Unredeemed activation codes | Checked and cleaned up at least monthly | **Partly in place**: a cleanup routine exists (removes expired non-revoked codes older than 7 days and revoked codes older than 30 days) but it is triggered manually by an administrator; no automatic schedule is present in the code, and monthly execution has not been verified |
| Logs under LiveRoom's direct control | At most 7 days | **Not yet confirmed**: the server application writes logs only to standard output (redacted); how long they remain depends on the operating-system journal settings, which have not been verified or configured to this limit |
| Support emails | At most 12 months | **Still to be implemented**: no automated deletion; manual process to be set up |
| Discord request messages | No specific period adopted | Handled under Discord's policies |
| Provider logs (zrok, TURN, STUN, GitHub, Discord, Google) | Not controlled by LiveRoom | Only what providers document: Metered states 30 days for relay connection metadata; other periods **not stated** in the documents we reviewed |

### 9. Your rights and how to use them

Where GDPR applies you can ask for access, rectification, erasure, restriction, portability, and object to processing based on legitimate interest. Write to **liveroom.beta.support@gmail.com**; you may also address either joint controller. Requests are handled jointly and we normally reply within one month. To find a record we may ask you for the activation code you used or other details; we never ask for conversation content, and we do not hold any. Erasing a licence record also ends the licence.

You can lodge a complaint with the Italian data protection authority (Garante per la protezione dei dati personali, www.garanteprivacy.it).

### 10. Age

LiveRoom Public Beta is intended for people aged 16 or over. If we learn that a younger person uses it, we will delete the related licence record on request.

### 11. Security

WebRTC encryption in transit; hashed activation codes; secure storage of the installation identifier on Android; rate limiting using pseudonymous keys; redaction of sensitive values in server logs; restricted administrative access. No system is perfectly secure.

### 12. Changes

When the app or services change, we publish the updated notice with its date and communicate significant changes to users appropriately (for example on the Discord server).

---

## Italiano

### 1. Chi è responsabile (contitolari)

LiveRoom è sviluppato e gestito congiuntamente da **Matteo Manicone** e **Alessandro Cugnasco**. I due determinano insieme finalità e mezzi del trattamento descritto e operano quali **contitolari del trattamento** ai sensi dell'art. 26 del Regolamento (UE) 2016/679 (GDPR).

Contatto privacy (comune): **liveroom.beta.support@gmail.com**.

**Contenuto essenziale dell'accordo (art. 26, par. 2)**: i due contitolari decidono insieme finalità e mezzi di LiveRoom; le richieste privacy sono gestite congiuntamente tramite il contatto comune; ciascuno è responsabile, insieme all'altro, di questa informativa, della sicurezza del servizio e delle risposte alle richieste, secondo la ripartizione tra loro. Indipendentemente dalla ripartizione, puoi esercitare i tuoi diritti nei confronti di ciascuno.

### 2. Ambito

L'app Android ufficiale LiveRoom (1.0.0-beta.2), il servizio di signaling e attivazione LiveRoom e i canali di assistenza sotto indicati. Non riguarda altre app, il sistema operativo del telefono né il dispositivo dell'altro partecipante.

LiveRoom è una Beta Pubblica gratuita, destinata a persone di **almeno 16 anni** (scelta del servizio). Questa è un'informativa; l'app non chiede un "consenso" per usarla e nulla in essa è una promessa di anonimato.

### 3. Contenuto delle conversazioni (testo e foto)

- Il **testo** che scrivi viene inviato all'altro partecipante tramite un DataChannel WebRTC mentre digiti. Con l'app ufficiale non viene inviato né conservato dal backend LiveRoom. L'app non conserva cronologia.
- Anche le **foto** viaggiano tramite DataChannel WebRTC. Le foto ricevute restano in memoria e l'app non le salva nella galleria.
- **Cifratura**: i DataChannel WebRTC sono cifrati durante il trasporto (DTLS). Se la connessione diretta fallisce, un relay TURN può inoltrare questo traffico cifrato. Non facciamo affermazioni più forti.
- **Limiti**: il dispositivo dell'altro partecipante riceve il contenuto in chiaro e può fare screenshot, fotografarlo o registrarlo. Una connessione diretta rivela il tuo indirizzo IP all'altro partecipante. Ciò che scrivi può passare dalla tua tastiera; il campo live chiede alla tastiera di non usare correzione automatica e apprendimento personalizzato, ma una tastiera può ignorare la richiesta.

### 4. Gestione delle foto sul dispositivo

1. Scegli una foto dalla galleria o ne scatti una con la fotocamera tramite il selettore di Android.
2. Il selettore crea una **copia temporanea nella cache privata dell'app**. L'app la legge in memoria e poi **elimina quella copia** (solo file ricevuti dal selettore nella propria cache; mai la foto originale in galleria). È un'operazione al meglio delle possibilità: se Android termina l'app nel momento sbagliato, una copia può restare finché Android o l'utente non svuota la cache dell'app.
3. In memoria l'app rimuove i metadati dalle foto JPEG (EXIF inclusi GPS e dati di dispositivo/data, miniatura, XMP, IPTC, commenti, dati finali) e può mantenere un valore minimo di orientamento. Gli altri formati vengono ricodificati in JPEG. Se non si ottiene un JPEG pulito, non viene inviato nulla.
4. La rimozione dei metadati non cambia ciò che la foto mostra.
5. Se usi la fotocamera, l'app fotocamera o il telefono possono conservare una copia propria: è fuori da LiveRoom.

Quanto sopra si basa sul codice sorgente e sui test automatici; la cache privata dell'app release installata non è stata ispezionata direttamente.

### 5. Dati trattati al di fuori delle conversazioni

| Dato | Dove | Finalità | Note |
|---|---|---|---|
| **Identificativo di installazione** (UUID casuale) | Creato sul dispositivo dopo la panoramica sulla privacy; archivio sicuro di Android; inviato al servizio di attivazione per attivazione e verifiche; conservato con la licenza | Collegare una licenza a un'installazione; verificarla | Non è un account tradizionale. Rimosso dal dispositivo con disinstallazione o cancellazione dei dati. Conservazione: sezione 8 |
| **Codice di attivazione** | Inserito da te; inviato al servizio di attivazione; lato server conservato come hash | Riscattare una licenza | Valido 5 minuti prima del riscatto |
| **Record della licenza** | Server: identificativo di installazione, date di attivazione e scadenza (12 mesi, o permanente), flag di revoca, ultima verifica, collegamento al record del codice. Dispositivo: data di scadenza | Gestire l'accesso alla beta | L'app ricontrolla la licenza quando si apre o riprende; se il server non è raggiungibile mantiene lo stato locale |
| **Registri amministrativi (audit)** | Database del server | Amministrazione e sicurezza (azioni dell'operatore come creare, revocare o ripulire codici) | Campi: data, tipo di azione, tipo e identificativo del bersaglio, impronta dell'operatore, record di dettagli |
| **Dati di signaling** (codice stanza, token d'invito, messaggi SDP e ICE) | Inoltrati in tempo reale dal servizio di signaling | Instaurare la connessione | SDP/ICE possono contenere indirizzi IP e dettagli di rete. Lo stato delle stanze resta solo nella memoria del server |
| **Indirizzo di rete (IP)** | Visto dal servizio di tunnel davanti al server, dai fornitori STUN e TURN e, in connessione diretta, dall'altro partecipante | Far funzionare la connessione; sicurezza | L'applicazione server è progettata per non memorizzare gli IP: ricava una chiave pseudonima di breve durata (cambia ogni 5 minuti), tenuta in memoria per il rate limiting e usata nei log al posto dell'IP |
| **Richiesta di configurazione** | All'avvio l'app richiede la configurazione al servizio LiveRoom (stesso indirizzo di signaling e attivazione); in cache sul dispositivo | Mantenere aggiornate le impostazioni di server e ICE | I dati normali di una richiesta web (IP, user agent) sono visibili al servizio di tunnel |
| **Impostazioni locali** | Dispositivo: cache di configurazione, indicatore "panoramica privacy vista", identificativo di installazione, scadenza licenza | Funzionamento dell'app | Nessuna cronologia. L'app non include librerie di analytics, pubblicità o crash reporting |

Permessi Android: internet, stato della rete, modifica dello stato della rete, impostazioni audio e (fino ad Android 11) Bluetooth, che arrivano con la libreria WebRTC, e fotocamera (richiesta quando scegli di scattare una foto). L'app non richiede permessi per microfono, posizione, contatti o archiviazione.

### 6. Finalità e basi giuridiche

| Finalità | Base giuridica (GDPR art. 6) |
|---|---|
| Erogare il servizio richiesto: attivazione, licenze ove applicabili, instaurazione della connessione | 6(1)(b) |
| Sicurezza, prevenzione abusi e registri amministrativi | 6(1)(f) legittimo interesse, dopo aver valutato che è necessario e non prevale sui tuoi diritti; puoi opporti (sezione 9) |
| Richieste di assistenza | 6(1)(b) se riguardano il servizio che usi; altrimenti 6(1)(f) |
| Obblighi di legge, solo se effettivamente applicabili | 6(1)(c) |

Riteniamo che la memorizzazione dell'identificativo di installazione sul tuo dispositivo sia strettamente necessaria per fornire il servizio richiesto, valutazione che facciamo anche rispetto all'art. 122 del Codice Privacy e alle norme e-Privacy; per questo non è richiesto un consenso separato.

LiveRoom non è progettato per pubblicità, profilazione o analisi del contenuto delle conversazioni.

### 7. Destinatari, servizi esterni e trasferimenti

Indichiamo solo ciò che è documentato. "Non indicato" significa che i documenti pubblici del fornitore che abbiamo esaminato (ottobre 2026) non lo dicono.

| Fornitore | Cosa fa per LiveRoom | Ruolo e fatti documentati |
|---|---|---|
| **Servizio LiveRoom** | Signaling, attivazione, licenze | Gestito dai contitolari su infrastruttura che amministrano; l'applicazione server scrive i log solo sullo standard output, con valori sensibili oscurati |
| **zrok public share (zrok.io), NetFoundry, Inc.** (Charlotte, Carolina del Nord, USA) | Instrada le richieste dell'app al servizio LiveRoom (`liveroom.shares.zrok.io`) | Una public share passa dal frontend pubblico del fornitore, quindi presumiamo che possa osservare tecnicamente queste richieste (codici di attivazione, identificativi di installazione, SDP/ICE; mai il contenuto delle conversazioni) e registrare dati tecnici. L'informativa di NetFoundry dice che può trasferire dati personali oltre confine e non descrive il trattamento dei dati di zrok, la conservazione né il suo ruolo giuridico: **non indicato** |
| **Metered** (Next Path Software Consulting Inc., Ontario, Canada) | Relay TURN, usato solo se la connessione diretta non è possibile | Si definisce **responsabile del trattamento** nel proprio accordo di trattamento pubblicato; dichiara che i contenuti inoltrati non sono ispezionati, conservati o registrati; registra metadati di connessione inclusi IP e porte per 30 giorni; per il Canada si basa sulle decisioni di adeguatezza UE; sub-responsabili in tutto il mondo (es. AWS, Google Cloud, Hetzner); possibile limitare le regioni |
| **Google STUN** (`stun.l.google.com`) | Aiuta il dispositivo a scoprire il proprio indirizzo di rete pubblico | L'informativa generale di Google non cita specificamente i server STUN: **non indicato**. Google Ireland Limited è titolare dei servizi Google nello SEE |
| **GitHub** (GitHub, Inc. / GitHub B.V.) | Distribuzione di APK e documenti | Titolare dei dati del proprio servizio; certificato EU-US Data Privacy Framework e usa clausole contrattuali tipo; registra IP e dati d'uso; tempi di conservazione **non indicati** |
| **Discord** (Discord Netherlands BV per utenti SEE; Discord Inc., USA) | Community e canale `#request-code` | Titolare; usa clausole contrattuali tipo e dichiara conformità al EU-US Data Privacy Framework; per i messaggi rimanda a una policy di conservazione separata |
| **Gmail** (Google) | Casella di assistenza liveroom.beta.support@gmail.com | Account Gmail consumer, secondo i termini di Google; Google è titolare dei dati del proprio servizio |

Alcuni fornitori trattano dati fuori dallo Spazio economico europeo. Le garanzie sono quelle documentate dai fornitori (decisioni di adeguatezza, clausole contrattuali tipo, Data Privacy Framework). Non le abbiamo verificate in modo indipendente.

### 8. Conservazione

Testo e foto delle conversazioni non sono conservati dal backend LiveRoom e l'app non conserva cronologia. Copie temporanee delle foto: sezione 4.

| Dato | Politica adottata (obiettivo) | Stato |
|---|---|---|
| Stato delle stanze | Solo in memoria, finché la stanza esiste | **Attuata** (verificata nel codice del server) |
| Record della licenza, record del codice collegato e identificativo di installazione | Durata della licenza/rapporto + 12 mesi dalla cessazione; una licenza permanente è conservata finché è attiva | **Ancora da implementare**: l'applicazione non contiene funzioni che cancellino i record delle licenze; sarà predisposta una procedura di cancellazione autorizzata |
| Registri amministrativi | Massimo 12 mesi | **Ancora da implementare**: la tabella di audit non ha funzioni di cancellazione; sarà predisposta una procedura di cancellazione autorizzata |
| Codici di attivazione inutilizzati | Verifica e pulizia almeno mensile | **Parzialmente attuata**: esiste una routine di pulizia (rimuove codici scaduti non revocati da oltre 7 giorni e revocati da oltre 30 giorni) ma è avviata manualmente da un amministratore; nel codice non c'è una pianificazione automatica e l'esecuzione mensile non è stata verificata |
| Log sotto il controllo diretto di LiveRoom | Massimo 7 giorni | **Non ancora confermata**: l'applicazione server scrive i log solo sullo standard output (oscurati); la durata dipende dalle impostazioni del journal del sistema operativo, che non sono state verificate né configurate su questo limite |
| Email di assistenza | Massimo 12 mesi | **Ancora da implementare**: nessuna cancellazione automatica; sarà predisposto un processo manuale |
| Messaggi di richiesta su Discord | Nessun periodo specifico adottato | Gestiti secondo le policy di Discord |
| Log dei fornitori (zrok, TURN, STUN, GitHub, Discord, Google) | Non controllati da LiveRoom | Solo ciò che i fornitori documentano: Metered dichiara 30 giorni per i metadati di connessione del relay; altri periodi **non indicati** nei documenti esaminati |

### 9. I tuoi diritti e come esercitarli

Dove si applica il GDPR puoi chiedere accesso, rettifica, cancellazione, limitazione, portabilità e opporti al trattamento basato sul legittimo interesse. Scrivi a **liveroom.beta.support@gmail.com**; puoi anche rivolgerti a ciascuno dei contitolari. Le richieste sono gestite congiuntamente e rispondiamo ordinariamente entro un mese. Per trovare un record potremmo chiederti il codice di attivazione usato o altri dettagli; non chiediamo mai il contenuto delle conversazioni, e non lo conserviamo. La cancellazione del record di una licenza pone fine anche alla licenza.

Puoi presentare reclamo al Garante per la protezione dei dati personali (www.garanteprivacy.it).

### 10. Età

LiveRoom Public Beta è destinata a persone di almeno 16 anni. Se veniamo a sapere che una persona più giovane lo usa, su richiesta cancelliamo il relativo record di licenza.

### 11. Sicurezza

Cifratura WebRTC durante il trasporto; codici di attivazione conservati come hash; archivio sicuro Android per l'identificativo di installazione; rate limiting con chiavi pseudonime; oscuramento dei valori sensibili nei log del server; accesso amministrativo ristretto. Nessun sistema è perfettamente sicuro.

### 12. Modifiche

Quando cambiano app o servizi pubblichiamo l'informativa aggiornata con la data e comunichiamo in modo appropriato le modifiche rilevanti agli utenti (per esempio sul server Discord).

---

Copyright (c) 2026 LiveRoom. All rights reserved.
