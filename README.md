# brawlstats-data

Dataset delle build per l'app **BrawlStats**. L'app scarica `builds.json` da qui
(al massimo ogni 6 ore, o subito con il pull-to-refresh nella lista).

## Come aggiornare
1. Modifica `builds.json` (anche dal sito di GitHub: apri il file → matita → "Commit changes").
2. **Aggiorna `updatedAt`** con la data di oggi (`AAAA-MM-GG`): l'app usa sempre
   il dataset con la data più recente tra questo e quello incluso nell'APK.
3. Controlla che il JSON sia valido (GitHub segnala gli errori di sintassi in anteprima).
   Se il file è rotto l'app lo ignora e continua a usare l'ultimo valido.

## Struttura (versione 2)
- `brawlers` → chiave = id del brawler (es. `16000000` = Shelly)
  - `overview`: `role`, `difficulty` (1–3), `tier`, `tierNote`, `summary`, `tips` (lista)
  - `builds`: `title`, `when`, `gadget` / `starPower` (`name` inglese dell'API, `note`,
    `alt` con `name` e `note`), `gears` e `altGears` (`gear`, `note`)
  - `modes`: `id` modalità (48000000 Arraffagemme, …2 Rapina, …3 Taglia, …5 Footbrawl,
    …6 Sopravvivenza solo, …9 in due, …17 Zona calda, …20 K.O., …24 Duelli)
  - `teammates`, `matchups.strong`, `matchups.weak`: `id` brawler + `note`

Chiavi degli equipaggiamenti: damage, shield, health, speed, vision, reload,
superCharge, gadgetCooldown, petPower, superRange.
