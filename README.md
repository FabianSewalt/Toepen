# Toepen scorebord — installeerbare web-app (PWA)

Deze map is een complete, statische web-app. Eén keer online zetten en daarna
installeer je hem op je telefoon als echte app met eigen icoontje. Werkt daarna
ook offline; scores worden lokaal op je telefoon bewaard.

## Stap 1 — Online zetten (kies één optie)

**Optie A: Netlify Drop (makkelijkst, 2 minuten, gratis)**
1. Ga naar https://app.netlify.com/drop
2. Sleep deze hele map (of de zip, uitgepakt) het venster in
3. Je krijgt direct een URL zoals `https://iets-willekeurigs.netlify.app`

**Optie B: GitHub Pages (gratis)**
1. Maak een nieuwe repository en upload alle bestanden uit deze map naar de root
2. Settings → Pages → Source: "Deploy from a branch" → branch `main`, map `/ (root)`
3. Na een minuut staat de app op `https://<gebruikersnaam>.github.io/<repo>/`

**Optie C: Eigen server / Raspberry Pi**
Zet de bestanden achter een webserver (nginx, Caddy, `python3 -m http.server`).
Let op: voor echte installatie + offline gebruik eist de browser **https**.
Over gewoon http werkt de app wel, maar dan alleen als browsertab/snelkoppeling.
Caddy regelt https automatisch als je een domeinnaam hebt.

## Stap 2 — Installeren op je telefoon

**iPhone (Safari):** open de URL → deelknop (vierkant met pijl) → **Zet op
beginscherm**. De app opent daarna fullscreen, zonder browserbalk.

**Android (Chrome):** open de URL → menu (⋮) → **App installeren** (of
"Toevoegen aan startscherm").

## Goed om te weten

- Scores staan in de lokale opslag van de telefoon zelf — iedere telefoon heeft
  dus z'n eigen scorebord, en na opnieuw openen staat alles er nog.
- Nieuwe versie uitbrengen = de bestanden opnieuw uploaden. Verhoog dan in
  `sw.js` het versienummer (`toepen-v1` → `toepen-v2`), anders blijft de oude
  versie uit de cache komen.
- `app.js` is de gebundelde app (React zit erin), de broncode staat in het
  Claude-gesprek als `toep-scorebord.jsx`.
