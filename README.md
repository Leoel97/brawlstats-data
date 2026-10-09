# BRAWLSTATS BUILD DATA

Questo è il dataset ufficiale delle build di **BrawlStats**.  
Massimo ogni 6 ore o subito con il pull-to-refresh nella lista, l'app scarica `builds.json` da qui.

## :memo: Come aggiornare le build
1. Modifica `builds.json`.
2. Aggiorna **`updatedAt`** con la data di oggi (`AAAA-MM-GG`).
3. Controlla che il JSON sia valido (eventuali errori di sintassi).

> **L'app usa sempre il dataset con la data più recente tra questo e quello già scaricato in app.**  
> **Se il file è rotto l'app lo ignora e continua a usare l'ultimo scaricato e valido.**

## :open_file_folder: Struttura delle build nel JSON
- `brawlers` → chiave = id del brawler
  - `overview`: `role`, `difficulty`, `tier`, `tierNote`, `summary`, `tips`
  - `builds`: `title`, `when`, `gadget` / `starPower` → (`name`, `note`, `alt` → (`name`, `note`)), `gears` / `altGears` → (`gear`, `note`)
  - `modes`: `id`, `note`
  - `teammates`: `id`, `note`
  - `matchups`: `strong` / `weak` → (`id`, `note`)
<br></br>
```
"brawlers": {  
   "16000000": {  
      "overview": {
         "role": "Danni ravvicinati",  
         "difficulty": 1,  
         "tier": "D",  
         "tierNote": "In Ranked è sotto la media...",  
         "summary": "Shelly fa tanti danni solo da...",  
         "tips": [  
            "Non sparare da lontano: i danni dipendono...",  
            "Aspetta nei cespugli con la super carica...",  
            "Turbostivali ricarica tutte le munizioni..."  
         ]  
      },  
      "builds": [
         {
            "title": "Standard",
            "when": "La scelta di base per il Ranked...",
            "gadget": {
               "name": "Fast Forward",
               "note": "Uno scatto mirato che ricarica...",
               "alt": {
                  "name": "Clay Pigeons",
                  "note": "Sulle mappe aperte o contro chi..."
               }
            },
            "starPower": {
               "name": "Band-Aid",
               "note": "Quando scendi sotto il 40% di salute...",
               "alt": {
                  "name": "Shell Shock",
                  "note": "Contro tank e assassini che scappano..."
               }
            },
            "gears": [
               {
                  "gear": "shield",
                  "note": "Assorbe i colpi mentre accorci la..."
               },
               {
                  "gear": "damage",
                  "note": "+15% di danni sotto metà vita..."
               }
            ],
            "altGears": [
               {
                  "gear": "speed",
                  "note": "Sulle mappe piene di cespugli..."
               },
               {
                  "gear": "gadgetCooldown",
                  "note": "Se vuoi usare Turbostivali..."
               }
            ]
         }
      ],
      "modes": [
         {
            "id": 48000005,
            "note": "La sua modalità migliore in..."
         },
         {
            "id": 48000009,
            "note": "Cespugli e super carica..."
         }
      ],
      "teammates": [
         {
            "id": 16000047,
            "note": "Il compagno con più vantaggio..."
         },
         {
            "id": 16000065,
            "note": "Copre da lontano le corsie..."
         }
      ],
      "matchups": {
         "strong": [
            {
               "id": 16000002,
               "note": "Per fare danni deve venirle..."
            },
            {
               "id": 16000024,
               "note": "Tank da mischia: la super..."
            }
         ],
         "weak": [
            {
               "id": 16000109,
               "note": "Il suo matchup peggiore..."
            },
            {
               "id": 16000014,
               "note": "Ti tiene lontana con frecce..."
            }
         ]
      }
   }
}
```
