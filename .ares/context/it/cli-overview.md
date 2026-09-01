# Panoramica CLI — `@ares/web-crawler`

## Stato: nessuna CLI

Il modulo `@ares/web-crawler` **non espone alcuna CLI**:

- Il campo `bin` non è presente in `package.json`.
- Non esistono cartelle `bin/` o script eseguibili da terminale.

È una **libreria importabile** via `import` (ESM).

## Script npm disponibili

```bash
yarn workspace @ares/web-crawler test
```

- `test` — segnaposto: `echo "Error: no test specified" && exit 1` (nessuna suite reale).

## API esportate (non CLI)

- `@ares/web-crawler` — esporta `{ crawler }`, la classe `Crawler`.
  - `new Crawler(urlFilters)`
  - `crawlUrl(url)`
  - `getUrlTypeFromResponse(url, method, headers, payload)`
  - `crawlHTML(...)`, `crawlCSS(...)`
  - `analyzeMLElement(...)`, `analyzeLinkerTags(...)`

Questi simboli vengono consumati via import nel codice applicativo, non da terminale.
