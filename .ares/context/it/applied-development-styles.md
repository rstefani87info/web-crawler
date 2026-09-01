# Stili di sviluppo applicati — `@ares/web-crawler`

## Standard di programmazione

- JavaScript ESM (`"type": "module"`); package `main: index.js`.
- Moduli "flat" nella root: `index.js` (barrel) e `crawler.js` (implementazione della classe `Crawler`).
- Pattern basato su classi con callback/configurazione (`urlFilters`).
- Documentazione in `.ares/docs/{it,en}` e package context in `.ares/context/`.
- Script `test` presente ma non implementato (restituisce errore).

## Albero del repository

```text
web-crawler/
├── index.js            # barrel: esporta la classe crawler
├── crawler.js          # implementazione classe Crawler
├── package.json        # manifest, scripts
├── README.md           # documentazione
├── .gitignore          # regole di esclusione
├── .ares/
│   ├── context/        # documenti di contesto (questo file)
│   └── docs/
│       ├── it/
│       └── en/
```

## Generato automaticamente vs scritto a mano

### GENERATO / NON versionabile (non riscrivere a mano)

- `.git/` — metadati Git.
- `node_modules/` — dipendenze installate.
- (non presenti in questo modulo: `dist/`, `build/`, `.cache/`, `current-schemas.json`).

### MANUALE / autoriale (da NON rigenerare né sovrascrivere)

- `index.js`, `crawler.js` — codice sorgente scritto a mano.
- `package.json`, `README.md`, `.gitignore` — configurazione e documentazione autoriale.
- `.ares/docs/` e `.ares/context/` — documentazione redatta manualmente.

> Vincolo: i file in `.ares/context/` (inclusi quelli in `it/`) sono documenti scritti a mano; non devono essere rigenerati o sovrascritti da strumenti automatici.
