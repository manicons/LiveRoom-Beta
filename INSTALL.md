# LiveRoom — Android Installation / Installazione Android

**Version / Versione: 1.0.0-beta.2 (versionCode 2)** · Android 7.0+ (API 24)

---

## English

### Requirements

- Android 7.0 (API 24) or newer
- Internet connection
- An activation code (see [README](README.md))

### Install

1. Open the official Releases page:
   https://github.com/manicons/LiveRoom-Beta/releases
2. Download `LiveRoom-1.0.0-beta.2.apk` and its `.sha256` file from the
   latest release.
3. **Verify the download** (see below).
4. Open the APK on your phone.
5. If Android asks, allow installation from the app you used to open the
   file (browser or file manager).
6. Confirm the installation and open LiveRoom.
7. Turn the "install unknown apps" permission off again afterwards.

On first launch the app shows a short privacy overview before it creates its
installation identifier. You can reopen it later from the activation,
consent and home screens.

### Update from an earlier beta — do NOT uninstall

Install the new APK **over** the existing app. Do not uninstall first.

- The new APK has the same package name (`com.liveroom.app`) and the same
  signing certificate, and a higher version code, so Android installs it as
  an update.
- Your installation identifier and licence are kept on the device.
- Uninstalling removes the app's local data, including the installation
  identifier and licence record. After a reinstall you may need a new
  activation code.
- If Android refuses with a signature conflict, the installed copy was not
  signed with the official certificate (for example a test build). Contact
  support before uninstalling anything.

### Verify the APK

Only download LiveRoom from the official repository above.

Expected values for **1.0.0-beta.2**:

| | |
|---|---|
| File | `LiveRoom-1.0.0-beta.2.apk` |
| Size | 88,149,220 bytes |
| SHA-256 | `c58c1e2aa38e4252c6aeb1e828cef648f4620c05e8867740baca2fb89649116c` |
| Signing certificate SHA-256 | `70edc7a0a286d91a1dceefdc7bb773cad89805783eb1eaa22d7567370e3c8a48` |

Windows (PowerShell):

```powershell
Get-FileHash .\LiveRoom-1.0.0-beta.2.apk -Algorithm SHA256
```

Linux / macOS:

```bash
sha256sum LiveRoom-1.0.0-beta.2.apk
```

The result must match exactly. If it does not, delete the file and do not
install it. Advanced users can also check the signing certificate with the
Android SDK tool `apksigner verify --print-certs`.

### Permissions

The app asks Android for network access, and for camera access only when
you choose to take a photo. Photos from the gallery are chosen through the
Android system picker.

### Activation code and support

Request a free beta code in the `#request-code` channel on Discord:
https://discord.gg/ACPENuHcVJ · Email: liveroom.beta.support@gmail.com

Privacy: see the [Privacy Notice](PRIVACY.md).

Never share activation codes or private conversations publicly.

---

## Italiano

### Requisiti

- Android 7.0 (API 24) o superiore
- Connessione Internet
- Un codice di attivazione (vedi [README](README.md))

### Installazione

1. Apri la pagina Releases ufficiale:
   https://github.com/manicons/LiveRoom-Beta/releases
2. Scarica `LiveRoom-1.0.0-beta.2.apk` e il relativo file `.sha256`
   dall'ultima release.
3. **Verifica il download** (vedi sotto).
4. Apri l'APK sul telefono.
5. Se Android lo richiede, autorizza l'installazione dall'app con cui hai
   aperto il file (browser o gestore file).
6. Conferma l'installazione e apri LiveRoom.
7. Disattiva di nuovo il permesso "installa app sconosciute".

Al primo avvio l'app mostra una breve panoramica sulla privacy prima di creare
l'identificativo di installazione. Puoi riaprirla dalle schermate di
attivazione, consenso e home.

### Aggiornamento da una beta precedente — NON disinstallare

Installa la nuova APK **sopra** l'app esistente. Non disinstallare prima.

- La nuova APK ha lo stesso nome pacchetto (`com.liveroom.app`), lo stesso
  certificato di firma e un codice di versione più alto: Android la installa
  come aggiornamento.
- Identificativo di installazione e licenza restano sul dispositivo.
- La disinstallazione elimina i dati locali dell'app, compresi identificativo
  di installazione e record della licenza. Dopo una reinstallazione potresti
  aver bisogno di un nuovo codice di attivazione.
- Se Android segnala un conflitto di firma, la copia installata non è firmata
  con il certificato ufficiale (per esempio una build di prova). Contatta
  l'assistenza prima di disinstallare.

### Verifica dell'APK

Scarica LiveRoom solo dal repository ufficiale indicato sopra.

Valori attesi per **1.0.0-beta.2**:

| | |
|---|---|
| File | `LiveRoom-1.0.0-beta.2.apk` |
| Dimensione | 88.149.220 byte |
| SHA-256 | `c58c1e2aa38e4252c6aeb1e828cef648f4620c05e8867740baca2fb89649116c` |
| SHA-256 del certificato di firma | `70edc7a0a286d91a1dceefdc7bb773cad89805783eb1eaa22d7567370e3c8a48` |

Windows (PowerShell):

```powershell
Get-FileHash .\LiveRoom-1.0.0-beta.2.apk -Algorithm SHA256
```

Linux / macOS:

```bash
sha256sum LiveRoom-1.0.0-beta.2.apk
```

Il risultato deve coincidere esattamente. Se non coincide, elimina il file e
non installarlo. Gli utenti esperti possono controllare anche il certificato
con lo strumento Android SDK `apksigner verify --print-certs`.

### Permessi

L'app chiede ad Android l'accesso alla rete e, solo quando scegli di scattare
una foto, alla fotocamera. Le foto dalla galleria si scelgono con il
selettore di sistema di Android.

### Codice di attivazione e assistenza

Richiedi un codice beta gratuito nel canale `#request-code` su Discord:
https://discord.gg/ACPENuHcVJ · Email: liveroom.beta.support@gmail.com

Privacy: consulta l'[Informativa Privacy](PRIVACY.md).

Non pubblicare codici di attivazione o conversazioni private.

---

Copyright (c) 2026 LiveRoom. All rights reserved.
