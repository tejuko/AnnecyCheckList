# Paklijst Annecy 2026 — online zetten (GitHub Pages)

Deze map is een complete, **installeerbare offline web-app**. Zet 'm gratis online via
GitHub Pages, dan hebben jij en Liam een echte link die je op elke telefoon/pc kunt openen
en op je startscherm kunt zetten.

## Wat zit erin
- `index.html` — de paklijst-app zelf
- `manifest.webmanifest` — maakt 'm installeerbaar (naam, kleuren, icoon)
- `sw.js` — service worker; zorgt dat de lijst offline werkt na één keer openen
- `icon-192.png`, `icon-512.png`, `icon-512-maskable.png`, `apple-touch-icon.png`, `favicon-64.png` — app-icoontjes

---

## Stap voor stap online zetten

1. Ga naar **github.com** en log in (of maak gratis een account).
2. Klik rechtsboven op **+ → New repository**.
   - **Repository name**: bijv. `paklijst-annecy`
   - Zet 'm op **Public** (Pages is gratis bij een openbare repo; een paklijst is niet gevoelig).
   - Klik **Create repository**.
3. Op de nieuwe repo-pagina: klik op **uploading an existing file**
   (of: **Add file → Upload files**).
4. **Sleep alle bestanden uit deze map** (`annecy-paklijst`) in het uploadvak —
   dus `index.html`, `manifest.webmanifest`, `sw.js` én alle `.png`-bestanden.
   > Belangrijk: sleep de **bestanden zelf**, niet de map eromheen.
5. Klik onderaan op **Commit changes**.
6. Ga naar **Settings** (tabje boven in de repo) → in het linkermenu **Pages**.
7. Bij **Build and deployment → Source**: kies **Deploy from a branch**.
   Bij **Branch** kies **main** en map **/ (root)** → **Save**.
8. Wacht ~1 minuut en ververs de Pages-pagina. Bovenaan verschijnt je link:
   **`https://<jouw-gebruikersnaam>.github.io/paklijst-annecy/`**

Klaar! Deel die link met Liam. 🎉

---

## Op je telefoon zetten (offline app)
Open de link op je telefoon en:
- **iPhone (Safari)**: deelknop (het vierkantje met pijltje) → **Zet op beginscherm**.
- **Android (Chrome)**: menu (⋮) → **App installeren** / **Toevoegen aan startscherm**.

Daarna werkt de lijst ook **zonder internet** en opent hij als een echte app.

---

## Live sync tussen apparaten
De lijst synchroniseert automatisch via een gratis Firebase Realtime Database.
Wat jij of Liam aan-/afvinkt, bewerkt of versleept, verschijnt binnen enkele seconden
op het andere apparaat. In de balk zie je een **"Gesynchroniseerd"**-lampje; ben je
even offline, dan wordt alles lokaal bewaard en bijgewerkt zodra je weer verbinding hebt.

De sync-instelling staat in `index.html` (`const SYNC_URL = ...`). Zet je die leeg,
dan werkt de app puur lokaal (per apparaat) verder.
- **Later iets aanpassen?** Vervang `index.html` in de repo (Add file → Upload files) en
  open daarna `sw.js`, verhoog het versienummer één stap (`annecy-paklijst-v1` → `-v2`),
  en commit. Zo krijgen jullie de nieuwe versie automatisch binnen.
