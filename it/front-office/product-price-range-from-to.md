---
title: "Intervallo di prezzo del prodotto - da / a - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Intervallo di prezzo del prodotto - da / a' di MyPresta.eu."
sidebar:
  label: "Intervallo di prezzo del prodotto - da / a - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Product price range - from / to su MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-price-range-from-to.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/product-price-range-from-to/)
>
> ---


# Intervallo di prezzo del prodotto - da / a

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti per i moduli PrestaShop. Nessun requisito di hosting speciale oltre a un ambiente standard compatibile con PrestaShop.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo aver installato il modulo, naviga su **Moduli > Gestione moduli** e clicca su "Configura" accanto a "Intervallo di prezzo del prodotto - da / a". Ti verrà presentata la schermata di configurazione principale.

#### Impostazioni generali

Questa sezione controlla il comportamento principale del modulo.

- **Visualizza intervallo di prezzo nell'elenco prodotti:**

  - **Cosa fa questa impostazione:** Questo interruttore determina se l'intervallo "da [prezzo più basso] a [prezzo più alto]" viene mostrato nelle pagine che elencano più prodotti, come le pagine di categoria, i risultati di ricerca o i moduli come "Nuovi prodotti" o "Prodotti in evidenza".
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (SÌ):* I prodotti con combinazioni e prezzi variabili visualizzeranno un intervallo di prezzo su tutte le pagine di elenco prodotti.
    - *Quando disabilitato (NO):* Verrà mostrato solo un singolo prezzo (solitamente il prezzo base o il prezzo della combinazione più bassa) sulle pagine di elenco prodotti, secondo il comportamento predefinito di PrestaShop.
  - **Valore consigliato:** SÌ
  - **Scenario / esempio del commerciante:** Se vendi magliette che costano €10 per la taglia piccola e €15 per la taglia grande, abilitando questa opzione verrà mostrato "da €10.00 a €15.00" sulla pagina della categoria delle magliette, offrendo ai clienti una rapida panoramica delle opzioni di prezzo.
- **Visualizza intervallo di prezzo sulla pagina del prodotto:**

  - **Cosa fa questa impostazione:** Questo interruttore controlla se l'intervallo di prezzo viene visualizzato sulla pagina del singolo prodotto stesso, tipicamente vicino al prezzo principale del prodotto.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (SÌ):* La pagina del prodotto mostrerà l'intervallo di prezzo per i prodotti con combinazioni, informando il cliente delle variazioni di prezzo prima che selezioni le opzioni.
    - *Quando disabilitato (NO):* La pagina del prodotto mostrerà solo un singolo prezzo (solitamente il prezzo base o il prezzo della combinazione più bassa), secondo il comportamento predefinito di PrestaShop.
  - **Valore consigliato:** SÌ
  - **Scenario / esempio del commerciante:** Sulla pagina del prodotto per un computer personalizzato, abilitando questa opzione verrà mostrato "da €800.00 a €2500.00" prima che il cliente inizi a selezionare CPU, RAM e opzioni di archiviazione, stabilendo chiare aspettative.
- **Considera gli sconti quantità:**

  - **Cosa fa questa impostazione:** Questa impostazione cruciale determina se il modulo deve considerare eventuali riduzioni di prezzo basate sulla quantità (prezzi specifici per quantità) quando calcola il prezzo *più basso* nell'intervallo.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (SÌ):* Il modulo calcolerà il prezzo più basso possibile, inclusi eventuali sconti quantità, per la parte "da" dell'intervallo. Ad esempio, se un prodotto costa €10, ma €8 se acquisti 10 unità, il prezzo "da" sarà €8.
    - *Quando disabilitato (NO):* Gli sconti quantità verranno ignorati e il prezzo "da" sarà basato esclusivamente sul prezzo della combinazione più bassa senza considerare i risparmi sull'acquisto all'ingrosso.
  - **Valore consigliato:** SÌ (per garantire che venga visualizzato il prezzo più basso più attraente e accurato).
  - **Scenario / esempio del commerciante:** Se vendi penne a €1 l'una, ma le offri a €0.80 se acquistate in confezioni da 100, abilitando questa opzione ti assicurerai che il prezzo "da" nell'elenco dei prodotti rifletta €0.80, facendo apparire il prodotto ancora più conveniente.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Visualizza intervallo di prezzo nell'elenco prodotti | SÌ | Mostra il prezzo "da/a" sulle pagine di categoria, ricerca e elenco. |
| Configurazione modulo | Visualizza intervallo di prezzo sulla pagina del prodotto | SÌ | Mostra il prezzo "da/a" sulla pagina dei dettagli del singolo prodotto. |
| Configurazione modulo | Considera gli sconti quantità | SÌ | Include le riduzioni di prezzo basate sulla quantità nel calcolo del prezzo più basso nell'intervallo. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: L'intervallo di prezzo non viene visualizzato sulle mie pagine/elenchi di prodotti.**
R:

1. **Controlla la configurazione del modulo:** Vai su **Moduli > Gestione moduli > Intervallo di prezzo del prodotto - da / a > Configura**. Assicurati che "Visualizza intervallo di prezzo nell'elenco prodotti" e "Visualizza intervallo di prezzo sulla pagina del prodotto" siano entrambi impostati su **SÌ**.
2. **Svuota la cache:** PrestaShop utilizza la cache. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti).
3. **Combinazioni di prodotti:** Il prodotto ha effettivamente combinazioni con prezzi *diversi*? Se tutte le combinazioni hanno lo stesso prezzo, il modulo probabilmente visualizzerà un singolo prezzo poiché non c'è un intervallo da mostrare.
4. **Compatibilità del tema:** Sebbene il modulo sia progettato per un'ampia compatibilità, temi molto pesantemente personalizzati potrebbero richiedere piccole modifiche. Se il problema persiste dopo aver controllato quanto sopra, contatta il supporto MyPresta.eu.

**D2: Il prezzo "da" non sembra includere i miei sconti quantità.**
R:

1. **Controlla la configurazione del modulo:** Vai su **Moduli > Gestione moduli > Intervallo di prezzo del prodotto - da / a > Configura**. Assicurati che "Considera gli sconti quantità" sia impostato su **SÌ**.
2. **Verifica gli sconti quantità:** Ricontrolla che i tuoi sconti quantità (prezzi specifici) siano configurati correttamente per il prodotto e le sue combinazioni nel back office di PrestaShop.
3. **Svuota la cache:** Svuota sempre la cache di PrestaShop dopo aver apportato modifiche alla configurazione.

**D3: L'intervallo di prezzo sembra un po' strano o disallineato con il design del mio tema.**
R:
Il modulo cerca di integrarsi perfettamente, ma ogni tema è unico.

1. **Svuota la cache:** A volte i problemi di stile sono dovuti a vecchi file memorizzati nella cache.
2. **CSS personalizzato:** Potrebbe essere necessario aggiungere del CSS personalizzato al tuo tema per regolare l'aspetto. Le classi CSS del modulo sono solitamente ben definite (vedi Sezione 7.5). Un webmaster può aiutarti a mirare queste classi per abbinarle al tuo tema.
3. **Contatta il supporto:** Se non ti senti a tuo agio con il CSS, il supporto MyPresta.eu può spesso fornire indicazioni o piccoli frammenti CSS per aiutarti.

**D4: Questo modulo rallenterà il mio negozio?**
R:
Il modulo è ottimizzato per le prestazioni. Calcola i prezzi in modo efficiente. Sebbene qualsiasi modulo aggiunga un piccolo overhead, questo è progettato per essere leggero. Se noti rallentamenti significativi, assicurati che il tuo server soddisfi le specifiche consigliate di PrestaShop e che altri moduli non stiano causando conflitti. Svuotare regolarmente la cache aiuta anche.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo "Intervallo di prezzo del prodotto - da / a" (`prange`) è un modulo PrestaShop standard che segue il modello MVC. Opera principalmente agganciandosi a vari punti di visualizzazione (`displayProductPriceBlock`, `displayProductListReviews`, ecc.) per iniettare il suo intervallo di prezzo calcolato. La logica principale risiede nel file `index.php`, che funge da punto di ingresso del modulo e gestisce la configurazione, l'installazione e la registrazione degli hook. Sfrutta le classi `Product` e `SpecificPrice` di PrestaShop per calcolare l'intervallo di prezzo, inclusi gli sconti quantità.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller front-office o back-office personalizzati. Tutta la logica è incapsulata all'interno della classe principale del modulo ed eseguita tramite hook.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non definisce classi personalizzate né estende `ObjectModel`. Tutte le manipolazioni dei dati e i calcoli dei prezzi necessari vengono eseguiti utilizzando le classi native `Product` e `SpecificPrice` di PrestaShop all'interno del file principale del modulo.

### 4.4 Risorse JavaScript (`views/js/`)

- **`prange/views/js/prange-hide-p.js`**
  - **Ambito:** Front-office (Pagina del prodotto)
  - **Scopo:** Questo script probabilmente contiene la logica per nascondere o modificare la visualizzazione predefinita del prezzo del prodotto sulla pagina del singolo prodotto quando l'intervallo di prezzo del modulo è attivo. Potrebbe ascoltare i cambiamenti del DOM o gli eventi di caricamento della pagina per garantire che l'intervallo del modulo sia il prezzo principale mostrato.
- **`prange/views/js/prange-hide-pl.js`**
  - **Ambito:** Front-office (Pagine di elenco prodotti)
  - **Scopo:** Simile a `prange-hide-p.js`, ma si rivolge specificamente alle pagine di elenco prodotti (categorie, risultati di ricerca). È progettato per nascondere o regolare la visualizzazione del prezzo singolo predefinito su queste pagine per fare spazio all'intervallo di prezzo del modulo.
- **`prange/views/js/prange.js`**
  - **Ambito:** Front-office
  - **Scopo:** Questo è probabilmente il file JavaScript principale per il modulo. Potrebbe contenere:
    - Logica per aggiornare dinamicamente l'intervallo di prezzo se gli attributi del prodotto vengono modificati tramite AJAX (ad esempio, selezionando una combinazione).
    - Listener di eventi per gli eventi `prestashop.on` relativi agli aggiornamenti dei dati del prodotto.
    - Qualsiasi rendering o manipolazione lato client richiesta per la visualizzazione dell'intervallo di prezzo.

### 4.5 Fogli di stile CSS (`views/css/`)

- **`prange/views/css/prange.css`**
  - **Ambito:** Stile del cliente del front-office.
  - **Componenti e contenitori principali dell'interfaccia utente che stilizza:** Questo foglio di stile fornisce la presentazione visiva predefinita per il testo dell'intervallo di prezzo. Definisce gli stili per il contenitore che contiene il testo "da/a", le dimensioni dei caratteri, i colori, i margini e potenzialmente le regolazioni reattive.
  - **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere:** Gli sviluppatori dovrebbero ispezionare l'HTML renderizzato per identificare le classi specifiche (ad esempio, `.prange-price-range`, `.prange-from`, `.prange-to`) utilizzate dal modulo. Queste possono quindi essere mirate nel `custom.css` o `theme.css` di un tema personalizzato per regolare l'aspetto.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template degli hook (`views/templates/hook/`)**: Questo modulo non definisce esplicitamente template in una sottodirectory `hook/` in base all'inventario fornito, ma i template elencati di seguito vengono effettivamente renderizzati tramite hook.
- **Template di amministrazione (`views/templates/admin/`)**: Questo modulo non ha template di amministrazione personalizzati oltre al modulo `getContent()` standard.
- **Template del front-office (`views/templates/front/`)**:
  - **`prange/views/templates/prange-oneprice.tpl`**
    - **Scopo:** Questo template è probabilmente utilizzato quando un prodotto *non* ha combinazioni con prezzi variabili, o quando il modulo determina che dovrebbe essere visualizzato solo un singolo prezzo (ad esempio, se i prezzi "da" e "a" sono identici). Garantisce una formattazione coerente anche per i prodotti a prezzo singolo se il modulo è attivo.
    - **Renderizzato tramite:** Probabilmente agganciato a `displayProductPriceBlock` o simili.
  - **`prange/views/templates/prange.tpl`**
    - **Scopo:** Questo è il template principale per visualizzare l'effettivo intervallo "da [prezzo più basso] a [prezzo più alto]". Riceve i prezzi più bassi e più alti calcolati dalla logica PHP del modulo e li formatta per la visualizzazione.
    - **Renderizzato tramite:** Questo template verrà renderizzato quando il modulo si aggancia a `displayProductPriceBlock` (per la pagina del prodotto) e potenzialmente ad altri hook per le pagine di elenco prodotti (ad esempio, `displayProductListReviews`, `displayProductPriceBlock` nel contesto dell'elenco prodotti, o sovrascrivendo i template principali).

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Questo modulo non crea tabelle SQL personalizzate.
  - Memorizza le sue impostazioni di configurazione (ad esempio, `PRANGE_DISPLAY_LIST`, `PRANGE_DISPLAY_PRODUCT`, `PRANGE_QUANTITY_DISCOUNT`) nella tabella standard `ps_configuration`.
- **Tabella degli hook registrati**:

| Nome dell'Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Utilizzato per includere i file CSS (`prange.css`) e JavaScript (`prange.js`, `prange-hide-p.js`, `prange-hide-pl.js`) del modulo per lo stile e la funzionalità del front-office. |
| `displayProductPriceBlock` | Renderizza il contenuto all'interno del blocco del prezzo del prodotto sulle pagine dei prodotti e potenzialmente negli elenchi dei prodotti. | Questo è l'hook principale per iniettare l'intervallo di prezzo calcolato nella visualizzazione del prezzo del prodotto. Il modulo probabilmente controlla il parametro `type` di questo hook per determinare il contesto (pagina del prodotto vs. elenco). |
| `displayProductListReviews` | Renderizza il contenuto vicino alle recensioni dei prodotti nelle pagine di elenco prodotti. | Sebbene sia chiamato per le recensioni, questo hook è spesso utilizzato dai moduli per iniettare informazioni aggiuntive (come gli intervalli di prezzo) negli elementi dell'elenco prodotti. |
| `displayProductExtraContent` | Renderizza blocchi di contenuto extra sulla pagina del prodotto. | Potrebbe essere utilizzato come posizione alternativa o supplementare per l'intervallo di prezzo sulla pagina del prodotto. |
| `displayAfterProductThumbs` | Renderizza il contenuto dopo le immagini in miniatura del prodotto sulla pagina del prodotto. | Un'altra potenziale posizione per visualizzare l'intervallo di prezzo sulla pagina del prodotto. |
| `displayProductButtons` | Renderizza il contenuto vicino ai pulsanti di azione del prodotto (ad esempio, Aggiungi al carrello). | Meno probabile per l'intervallo di prezzo, ma possibile per informazioni contestuali. |
| `displayFooterProduct` | Renderizza il contenuto nella sezione del piè di pagina della pagina del prodotto. | Una posizione di fallback o alternativa per l'intervallo di prezzo sulla pagina del prodotto. |
| `displayProductAdditionalInfo` | Renderizza informazioni aggiuntive sulla pagina del prodotto. | Un hook comune per iniettare dettagli personalizzati del prodotto. |
| `displayProductPrice` | Renderizza il prezzo del prodotto stesso. | Questo hook è spesso sovrascritto o esteso da moduli che modificano la visualizzazione del prezzo. |
| `actionProductUpdate` | Eseguito dopo l'aggiornamento di un prodotto nel back office. | Potrebbe essere utilizzato per svuotare le cache specifiche del modulo o reindicizzare gli intervalli di prezzo se il modulo mantenesse la propria cache. |
| `actionProductAdd` | Eseguito dopo l'aggiunta di un nuovo prodotto. | Simile a `actionProductUpdate`. |
| `actionProductDelete` | Eseguito dopo l'eliminazione di un prodotto. | Simile a `actionProductUpdate`. |

*Nota: Gli hook esatti utilizzati possono variare leggermente tra le versioni del modulo e le versioni di PrestaShop. L'elenco sopra rappresenta gli hook comuni per la funzionalità di questo modulo in base alla sua descrizione.*

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, correzioni di bug e supporto dedicato agli sviluppatori per il modulo "Intervallo di prezzo del prodotto - da / a", fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Assicurarsi di utilizzare l'ultima versione del modulo per prestazioni e compatibilità ottimali con il proprio negozio PrestaShop.
