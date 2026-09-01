# Obiettivi del modulo `@ares/web-crawler`

## Introduzione

`@ares/web-crawler` offre un modo semplice per **crawlare un sito web**. Il modulo implementa una classe `Crawler` che, dato un URL e dei filtri di configurazione (selettori, callback), recupera la pagina, ne determina il tipo di contenuto e la attraversa ricorsivamente (HTML, link, risorse, sitemap), chiamando hook personalizzati.

È scritto in ESM (`"type": "module"`) e non espone binari: è una libreria consumata via import.

## Scopo principale

- Scaricare e analizzare pagine web (HTTP/HTML) in modo configurabile.
- Traversare automaticamente i link (`href`/`src`) e le sitemap partendo da un URL radice.
- Supportare analisi guidata da filtri per URL (selettori CSS, callback `onload`, `onError`, `onCrawlError`, `onUnsupportedExtension`).

## Obiettivi

- Fornire un crawler riutilizzabile orientato ai contenuti, con API semplici (`crawlUrl`, `getUrlTypeFromResponse`).
- Supportare diversi tipi di contenuto tramite metodi `crawl<EXT>` (es. `crawlHTML`, `crawlCSS`).
- Integrarsi con `@ares/web-ui` per il parsing HTML/DOM (`parseUrl`, `parseCode`) e con `@ares/core` per le utility sugli oggetti.

## Responsabilità

- Determinare il tipo di risposta da un URL (`getUrlTypeFromResponse`).
- Eseguire il crawl ricorsivo (`crawlUrl`) rispettando i filtri e la mappa degli URL visitati.
- Analizzare elementi DOM (`analyzeMLElement`, `analyzeMLElementChild`) e link (`analyzeLinkerTags`).
- Fornire hook di estensione per selettori e callback specifici.

## Cosa il modulo NON fa

- Non aggrega contenuti in un lessico (compito di `wikipedia-crawler`).
- Non è un parser Wikizionario (compito di `@ares/wikitionary-parser`) né un generatore di tipi da Wikidata (compito di `@ares/wiki-data-parser`).
- Non espone una CLI interna propria: la classe è esportata come libreria.
