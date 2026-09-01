# Dipendenze aReS — `@ares/web-crawler`

## Dipendenze da altri moduli `@ares/*`

### `@ares/web-ui` (dipendenza runtime obbligatoria)

Ragione: il crawler usa i parsing HTML/DOM di `@ares/web-ui`. In particolare, `crawler.js` importa `parseUrl` e `parseCode` da `@ares/web-ui/ml.js` per caricare e analizzare le pagine HTML recuperate (accesso a `jdom.window.aReS.$`).

### `@ares/core` (dipendenza transitiva/de facto)

Ragione: `crawler.js` importa `findPropValueByAlias` da `@ares/core/objects.js` per risolvere i filtri URL per alias. Pur non essendo dichiarato in `package.json` tra le dipendenze dirette, viene usato direttamente (via risoluzione workspace).

## Dipendenze NPM (non aReS)

- `axios` — richieste HTTP.
- `request` — richieste HTTP legacy.
- `cheerio` / `css-select` — parsing e selezione HTML/CSS.
- `selenium-webdriver` — automazione browser per pagine scriptate.

## Chi dipende da `@ares/web-crawler`

I moduli che dichiarano `@ares/web-crawler` come dipendenza:

- `@ares/language-interpreter`
- `w3schools-crawler`

Questi moduli usano il crawler per acquisire contenuti testuali/lessicali da pagine web.
