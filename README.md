# SelfCare Extract — Downloads

Aplikacion lokal për kontabilistë që sinkronizon automatikisht të dhënat
nga **eFiskalizimi.tatime.gov.al** dhe i bashkon në një workbook të vetëm
Excel për çdo biznes.

## Shkarkim

➡️ **[Versioni më i fundit (Releases)](https://github.com/kevindalevin/selfcare-extract-downloads/releases/latest)**

| Platforma | File |
|-----------|------|
| **Mac (Apple Silicon — M1/M2/M3/M4)** | `SelfCare Extract-…-arm64.dmg` |
| **Mac (Intel)** | `SelfCare Extract-…-x64.dmg` (pa `-arm64`) |
| **Windows** | _Vjen së shpejti_ |

## Instalimi (Mac)

1. Shkarko `.dmg`-në që përshtat me Mac-un tënd
2. Hape file-in dhe **tërhiq SelfCare Extract** te folderi **Applications**
3. Hape **Applications** te Finder
4. **Hera e parë**: macOS do të thotë "Apple cannot check this app for malicious software"
   - **Right-click** te **SelfCare Extract** → **Open** → **Open anyway**
   - Kjo bëhet vetëm një herë; pas kësaj hapet me dyklik
5. Aplikacioni hapet me ikonë në Dock dhe një dritare ku menaxhohen klientët

## Si funksionon

1. Shto klientët (NIPT + emër) te lista
2. Kliko **Sync** → hapet Chromium → loguohu te eAlbania me kredencialet e atij klienti
3. Pas ~1 min, app-i ka shkarkuar dhe bashkuar të gjitha të dhënat e biznesit
4. Workbook-u final ruhet te `~/Documents/SelfCareData/<NIPT>-<emër>/<datë>/`

App-i nuk dërgon asnjë të dhënë në cloud. Gjithçka rri lokal.

## Çfarë sinkronizon

- Operatorët
- Lista e produkteve
- Transaksionet e shitjeve / blerjeve
- Faturat e fiskalizuara
- Deklaratat doganore (importet)
- Pasqyra mujore TVSH
- Gjendja e arkës (depozitat / tërheqjet / bilanci)
- _Opsional_: PDF i çdo fature shitje/blerje
- _Opsional_: Pasqyra mujore — detail (deklarata TVSH formë + libri shitjeve/blerjeve)

## Sigurisht

- **Nuk dërgohet asnjë e dhënë diku tjetër** — vetëm midis Mac-it tënd dhe SelfCare-it zyrtar
- Cookies dhe sesionet ruhen lokalisht në folderin e app-it për çdo klient veç e veç
- Nuk ka autentikim cloud, nuk ka API keys, nuk ka shërbim third-party

## Mbështetje

Probleme ose pyetje: hap një issue te ky repo ose kontakto me autorin.

Source: [github.com/kevindalevin/selfcare-extract](https://github.com/kevindalevin/selfcare-extract) (privat)

---

Build me [Electron](https://www.electronjs.org/) +
[Playwright](https://playwright.dev/) + [ExcelJS](https://github.com/exceljs/exceljs).
