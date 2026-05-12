# SelfCare Extract — Downloads

Aplikacion lokal për kontabilistë që sinkronizon automatikisht të dhënat
nga **eFiskalizimi.tatime.gov.al** dhe i bashkon në një workbook të vetëm
Excel për çdo biznes.

## Shkarkim

➡️ **[Versioni më i fundit (Releases)](https://github.com/kevindalevin/selfcare-extract-downloads/releases/latest)**

| Platforma | File |
|-----------|------|
| **Mac (Apple Silicon — M1/M2/M3/M4/M5)** | `SelfCare.Extract-X.X.X-arm64.dmg` |
| **Mac (Intel)** | `SelfCare.Extract-X.X.X-x64.dmg` |
| **Windows 10 / 11** | `SelfCare.Extract.Setup.X.X.X.exe` |

---

## ⚠ Para se të instalosh: paralajmërime sigurie

App-i **nuk është code-signed** me certifikatë komerciale (Apple Developer ID / Windows Code Signing Cert kushtojnë $99–500/vit). Si rrjedhim, **macOS dhe Windows do shfaqin një paralajmërim te hapja e parë** — kjo është normale për software të zhvilluar privat dhe **nuk do thotë që app-i është i dëmtuar**.

Hapat më poshtë e bypass-ojnë në mënyrë të sigurt. **Vetëm një herë** për çdo version të instaluar.

---

## Instalimi (Mac)

### Hapi 1 — Shkarko + zvarrit te Applications

1. Shkarko `.dmg`-në e duhur (`arm64` për M-series, `x64` për Intel).
2. Hap DMG-në (double-click).
3. **Zvarrit ikonën SelfCare Extract te folderi Applications.**

### Hapi 2 — Hapja e parë

1. Te **Finder → Applications**, double-click **SelfCare Extract**.

2. macOS do shfaqë:
   > *"SelfCare Extract" is damaged and can't be opened. You should move it to the Trash.*

   > **Klikoni `Cancel`** (jo "Move to Trash" — ikona është e padëmtuar, ky mesazh është mashtrues nga Apple për app të pa-signed).

3. Hapni **System Settings → Privacy & Security**.

4. Scroll poshtë te seksioni **Security**. Pas "Allow applications from", do shihet:
   > *"SelfCare Extract" was blocked from use because it is not from an identified developer.*  [**Open Anyway**]

5. Kliko **`Open Anyway`** → fut admin password.

6. App-i hapet. **Hapjet e ardhshme do hapen normalisht pa paralajmërim.**

### Nëse "Open Anyway" nuk shfaqet (fallback me Terminal)

Disa Mac me macOS Sequoia 15+ mund të kenë sjellje më të rreptë. Nëse butoni nuk del te Privacy & Security:

1. Hap **Terminal** (Cmd+Space → "Terminal" → Enter).
2. Kopjo dhe ngjit këto dy komanda (do kërkohet admin password):

   ```bash
   sudo xattr -cr "/Applications/SelfCare Extract.app"
   sudo codesign --force --deep --sign - "/Applications/SelfCare Extract.app"
   ```

3. Hap app-in nga Applications.

---

## Instalimi (Windows 10 / 11)

### Hapi 1 — Shkarko instaluesin

Shkarko `SelfCare.Extract.Setup.X.X.X.exe` (i njëjti file për Win64 dhe Win arm64).

### Hapi 2 — Ekzekuto instaluesin

1. Double-click te file-i.

2. Mund të shfaqet **SmartScreen warning**:
   > *Windows protected your PC*
   > *Microsoft Defender SmartScreen prevented an unrecognized app from starting.*

3. Kliko linkun **`More info`** te dritarja → del butoni **`Run anyway`**.

4. Kliko **`Run anyway`** → instaluesi nis.

5. Ndiq hapat (Next → Install). App-i hapet automatikisht ose nga **Start Menu → SelfCare Extract**.

---

## Si funksionon

1. **Shto klientët** (NIPT + emër) te lista.
2. Kliko **Sync** te një klient → hapet Chromium → loguhesh te eAlbania me kredencialet e atij klienti.
3. Pas ~1-2 minutash, app-i ka shkarkuar dhe bashkuar të gjitha të dhënat e biznesit.
4. Workbook-u final ruhet te:
   - **Mac:** `~/Documents/SelfCareData/<NIPT>-<emër>/<datë>/`
   - **Windows:** `C:\Users\<user>\Documents\SelfCareData\<NIPT>-<emër>\<datë>\`

App-i **nuk dërgon asnjë të dhënë në cloud**. Gjithçka rri lokalisht.

---

## Çfarë sinkronizon

- Operatorët
- Lista e produkteve
- Transaksionet e shitjeve / blerjeve
- Faturat e fiskalizuara
- Deklaratat doganore (importet)
- Pasqyra mujore TVSH
- Gjendja e arkës (depozitat / tërheqjet / bilanci)
- *Opsional:* PDF i çdo fature shitje/blerje
- *Opsional:* Pasqyra mujore — detail (deklarata TVSH formë + libri shitjeve/blerjeve)

---

## Sigurisht

- **Nuk dërgohet asnjë e dhënë diku tjetër** — vetëm midis kompjuterit tënd dhe SelfCare-it zyrtar.
- Cookies dhe sesionet ruhen lokalisht në folderin e app-it për çdo klient veç e veç.
- Nuk ka autentikim cloud, nuk ka API keys, nuk ka shërbim third-party.

---

## Pse shfaqen paralajmërimet e sigurisë?

Sistemet operative moderne (macOS Gatekeeper + Windows SmartScreen) tregojnë paralajmërim për çdo app të shkarkuar nga interneti që **nuk është nënshkruar me certifikatë komerciale**. Këto certifikata thjesht identifikojnë botuesin te OS-i — nuk garantojnë sigurinë e kodit. Kur certifikatat të aktivizohen për këtë projekt, paralajmërimet do zhduken.

---

## Mbështetje

Probleme ose pyetje: hap një issue te ky repo ose kontakto: **seo@vesasolutions.com**

Source: [github.com/kevindalevin/selfcare-extract](https://github.com/kevindalevin/selfcare-extract) (privat)

---

Build me [Electron](https://www.electronjs.org/) +
[Playwright](https://playwright.dev/) + [ExcelJS](https://github.com/exceljs/exceljs).
