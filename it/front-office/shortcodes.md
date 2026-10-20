---
title: "Shortcodes - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Shortcodes di MyPresta.eu."
sidebar:
  label: "Shortcodes"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Shortcodes su MyPresta.eu](https://mypresta.eu/modules/front-office-features/shortcodes.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/shortcodes/)
>
> ---


# Shortcodes

## 1. Requisiti e Compatibilità
- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per un'installazione PrestaShop e sono sufficienti per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)
Dopo aver installato il modulo, naviga su **Moduli > Gestione moduli** e cerca "Shortcodes". Clicca sul pulsante "Configura" per accedere alle sue impostazioni.

La pagina di configurazione del modulo Shortcodes è semplice e si concentra su un'unica, cruciale impostazione:

#### Disabilita tutti gli shortcode
-   **Cosa fa questa impostazione:** Questo è un interruttore principale che controlla se il modulo elabora e sostituisce gli shortcode su tutto il tuo sito web.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (impostato su "Sì"):* Il modulo scansionerà attivamente i tuoi contenuti e i file del tema alla ricerca di shortcode riconosciuti (ad esempio, `[products]`, `[categories]`, `[html]`) e li sostituirà con il contenuto dinamico corrispondente. Questa è la modalità operativa prevista per il modulo.
    -   *Quando disabilitato (impostato su "No"):* Il modulo smetterà di elaborare tutti gli shortcode. Qualsiasi shortcode che hai inserito nei tuoi contenuti o nei file del tema apparirà semplicemente come testo normale (ad esempio, `[products]` sarà visibile come `[products]` ai tuoi clienti) e non verrà sostituito da contenuto dinamico.
-   **Valore consigliato:** **Sì**
-   **Scenario / esempio per il commerciante:**
    -   Imposteresti questo su "Sì" per attivare la funzionalità shortcode e visualizzare il tuo contenuto dinamico.
    -   Potresti temporaneamente impostarlo su "No" se stai debuggando un problema, eseguendo la manutenzione o se desideri disabilitare tutti i contenuti dinamici generati dagli shortcode in tutto il tuo negozio senza disinstallare il modulo. Ricorda di salvare le modifiche dopo aver attivato questa impostazione.

:::tip
Dopo aver modificato qualsiasi impostazione, clicca sempre sul pulsante "Salva" per applicare le tue modifiche.
:::

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
|---|---|---|---|
| Pagina di configurazione del modulo | Disabilita tutti gli shortcode | Sì | Controlla se il modulo elabora e sostituisce gli shortcode con contenuto dinamico. Imposta su "Sì" per attivare, "No" per disabilitare. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei shortcode vengono visualizzati come testo normale (ad esempio, `[products]`) invece di contenuti dinamici. Cosa c'è che non va?**
**R1:**
1.  **Verifica lo stato del modulo:** Vai su **Moduli > Gestione moduli** e assicurati che il modulo "Shortcodes" sia installato e abilitato.
2.  **Verifica la configurazione del modulo:** Vai alla pagina di configurazione del modulo e assicurati che "Disabilita tutti gli shortcode" sia impostato su **"Sì"**.
3.  **Svuota la cache:** A volte la cache di PrestaShop può impedire che le modifiche appaiano immediatamente. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti).
4.  **Sintassi corretta dello shortcode:** Ricontrolla di aver digitato lo shortcode esattamente come richiesto, incluse le parentesi quadre `[]` e qualsiasi parametro (ad esempio, `[products type="new"]`). Qualsiasi errore di battitura impedirà che venga elaborato.

**D2: Il contenuto dinamico (ad esempio, il carosello di prodotti) non è stilizzato correttamente o appare danneggiato nel mio tema.**
**R2:**
Questo di solito indica un conflitto CSS o uno stile mancante specifico per il tuo tema.
1.  **Compatibilità del tema:** Sebbene il modulo fornisca uno stile di base, i temi personalizzati potrebbero sovrascrivere o mancare di stili per alcuni elementi.
2.  **Assistenza dello sviluppatore:** Potrebbe essere necessario un web developer per ispezionare la pagina utilizzando gli strumenti di sviluppo del browser (F12) per identificare i conflitti CSS e aggiungere regole CSS personalizzate al tuo tema per garantire che l'output dello shortcode si integri visivamente. Il file CSS del modulo (`cmsproductspro.css`) può essere un punto di partenza per riferimento.

**D3: Posso usare gli shortcode nei negozi multilingue?**
**R3:** Sì, gli shortcode stessi sono agnostici rispetto alla lingua. Il contenuto che generano (ad esempio, nomi di prodotti, descrizioni) verrà automaticamente visualizzato nella lingua selezionata dal cliente, a condizione che i tuoi prodotti e categorie abbiano traduzioni per quella lingua. Quando inserisci shortcode nelle pagine CMS o nelle descrizioni dei prodotti, assicurati di modificare il contenuto per la lingua corretta nel back office.

**D4: Ho aggiunto uno shortcode a una nuova pagina CMS, ma non appare nel front office.**
**R4:**
1.  **Stato della pagina:** Assicurati che la tua pagina CMS sia abilitata e visibile nel tuo menu di navigazione o collegata da un'altra pagina.
2.  **Cache:** Svuota la cache di PrestaShop (**Parametri avanzati > Prestazioni**).
3.  **Posizionamento dello shortcode:** Verifica che lo shortcode sia posizionato in un'area di contenuto che sia effettivamente renderizzata dal tuo tema per quella pagina CMS. Alcuni temi potrebbero avere blocchi di contenuto specifici.

**D5: Quali shortcode sono disponibili e quali parametri posso usare?**
**R5:** La documentazione del modulo (questa guida) o la pagina di configurazione del modulo (se li elenca) dovrebbero dettagliare gli shortcode disponibili. Gli shortcode comuni includono:
-   `[products]` (per vari elenchi di prodotti come nuovi, best-seller, ID specifici)
-   `[categories]` (per visualizzare elenchi di categorie)
-   `[html]` (per incorporare HTML personalizzato)
-   `[imageManufacturer]` (per visualizzare immagini del produttore)
Dovrai fare riferimento all'implementazione specifica del modulo per i parametri esatti (ad esempio, `limit`, `carousel`, `id`, `type`).

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica per sviluppatori e webmaster che desiderano comprendere, eseguire il debug o estendere il modulo Shortcodes.

### 4.1 Panoramica dell'architettura
Il modulo Shortcodes (`cmsproductspro`) opera principalmente come filtro di contenuto. Si aggancia al processo di rendering dell'output di PrestaShop per intercettare il contenuto HTML prima che venga inviato al browser. Utilizza quindi espressioni regolari per trovare e sostituire modelli di shortcode predefiniti con contenuto HTML generato dinamicamente. La configurazione del modulo è minima, concentrandosi su un interruttore globale di abilitazione/disabilitazione. La logica di generazione del contenuto è incapsulata all'interno della classe principale del modulo, sfruttando le funzionalità core di PrestaShop per il recupero dei dati (prodotti, categorie, produttori).

### 4.2 Controller (`controllers/`)
Questo modulo **non** contiene alcun controller amministrativo Front-Office o Back-Office personalizzato. Tutta la logica di configurazione ed elaborazione del contenuto è gestita all'interno del file principale del modulo (`cmsproductspro.php`).

### 4.3 Classi e modelli core (`classes/`)
Questo modulo **non** definisce alcuna classe personalizzata o `ObjectModel` in una directory `classes/`. Tutta la logica core risiede all'interno del file `cmsproductspro.php`.

### 4.4 Risorse JavaScript (`views/js/`)
Questo modulo **non** contiene alcun file JavaScript personalizzato. Qualsiasi comportamento dinamico (come i caroselli) si baserebbe tipicamente su librerie JavaScript esistenti fornite da PrestaShop o dal tema (ad esempio, Owl Carousel, Slick Carousel) se l'output dello shortcode include tali componenti.

### 4.5 Fogli di stile CSS (`views/css/`)
-   **`cmsproductspro/cmsproductspro.css`**
    *   **Scopo:** Stile del front-office per il cliente.
    *   **Componenti e contenitori UI principali che stilizza:** Questo foglio di stile fornisce uno stile di base per l'output HTML generato dagli shortcode. Questo include:
        *   Griglie e caroselli di prodotti (ad esempio, `.cmsproductspro-products-grid`, `.cmsproductspro-carousel`).
        *   Singoli articoli di prodotto (ad esempio, `.cmsproductspro-product-item`, `.cmsproductspro-product-image`, `.cmsproductspro-product-name`, `.cmsproductspro-product-price`).
        *   Elenchi di categorie (ad esempio, `.cmsproductspro-categories-list`, `.cmsproductspro-category-item`).
        *   Immagini del produttore (ad esempio, `.cmsproductspro-manufacturer-image`).
        *   Layout generale e reattività per questi elementi.
    *   **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere:** Gli sviluppatori possono mirare a classi come `.cmsproductspro-products-grid`, `.cmsproductspro-product-item`, `.cmsproductspro-product-name`, `.cmsproductspro-product-price`, `.cmsproductspro-categories-list`, `.cmsproductspro-category-item`, `.cmsproductspro-manufacturer-image` per personalizzare l'aspetto del contenuto generato dallo shortcode all'interno del loro tema.

### 4.6 Struttura del template Smarty (`views/templates/`)
Il modulo utilizza diversi template Smarty per renderizzare il contenuto dinamico per vari shortcode. Questi template si trovano in `views/templates/`.

-   **Template hook (`views/templates/hook/`)**: Questo modulo non utilizza esplicitamente una sottodirectory `hook/` per i suoi template. I template si trovano direttamente in `views/templates/` e vengono renderizzati in base allo shortcode rilevato.

-   **Template admin (`views/templates/admin/`)**: Questo modulo non contiene alcun template admin specifico oltre al modulo di configurazione standard gestito da `getContent()`.

-   **Template front-office (`views/templates/front/`)**:
    *   **`cmsproductspro/categories.tpl`**:
        *   **Scopo:** Renderizza un elenco di categorie, tipicamente utilizzato da uno shortcode `[categories]`.
        *   **Variabili:** Si aspetta variabili come `$categories` (un array di oggetti categoria), `$display_subcategories`, `$image` ecc.
        *   **Output:** Genera HTML per una griglia o un elenco di categorie, potenzialmente con immagini e link.
    *   **`cmsproductspro/html.tpl`**:
        *   **Scopo:** Renderizza contenuto HTML grezzo, utilizzato da uno shortcode `[html]`.
        *   **Variabili:** Si aspetta una variabile `$content` contenente la stringa HTML da visualizzare.
        *   **Output:** Visualizza direttamente il contenuto HTML fornito.
    *   **`cmsproductspro/imageManufacturer.tpl`**:
        *   **Scopo:** Visualizza l'immagine di un produttore, utilizzata da uno shortcode `[imageManufacturer]`.
        *   **Variabili:** Si aspetta `$manufacturer` (un oggetto con i dettagli del produttore, incluso il percorso dell'immagine) e potenzialmente `$link` per la pagina del produttore.
        *   **Output:** Genera un tag `<img>` per il logo del produttore, spesso racchiuso in un link.
    *   **`cmsproductspro/productGallery.tpl`**:
        *   **Scopo:** Renderizza una galleria di prodotti, potenzialmente con layout o funzionalità specifiche. Questo potrebbe essere un template di visualizzazione prodotti più generico.
        *   **Variabili:** Si aspetta `$products` (un array di oggetti prodotto) e altre opzioni di visualizzazione.
        *   **Output:** Struttura HTML per una galleria di prodotti.
    *   **`cmsproductspro/products-carousel.tpl`**:
        *   **Scopo:** Renderizza un elenco di prodotti specificamente progettato per essere utilizzato all'interno di un componente carosello.
        *   **Variabili:** Si aspetta `$products` (array di oggetti prodotto) e potenzialmente opzioni specifiche del carosello.
        *   **Output:** Struttura HTML per un elenco di prodotti, spesso con classi adatte a una libreria JavaScript per caroselli.
    *   **`cmsproductspro/products.tpl`**:
        *   **Scopo:** Renderizza un elenco o una griglia generale di prodotti, utilizzato da uno shortcode `[products]`.
        *   **Variabili:** Si aspetta `$products` (array di oggetti prodotto) e altre opzioni di visualizzazione come `$grid_class`, `$item_class`.
        *   **Output:** Struttura HTML per una griglia o un elenco di prodotti.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**: Questo modulo **non** crea alcuna tabella del database personalizzata. La sua configurazione è memorizzata nella tabella `ps_configuration` utilizzando chiavi come `CMSPRODUCTSPRO_HIDE` (per l'impostazione "Disabilita tutti gli shortcode").

-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempistica di esecuzione | Scopo tecnico |
|---|---|---|
| `actionOutputHTMLBefore` | Eseguito appena prima che l'output HTML finale venga inviato al browser. | Questo è l'hook principale in cui il modulo intercetta l'intero contenuto della pagina, scansiona gli shortcode ed esegue le sostituzioni. |
| `displayHeader` | Eseguito nella sezione `<head>` dell'HTML. | Utilizzato per includere i file CSS necessari (`cmsproductspro.css`) per il contenuto generato dallo shortcode. |
| `actionAjaxDieProductControllerdisplayAjaxQuickviewBefore` | Eseguito prima del metodo `displayAjaxQuickview` in `ProductController` (per i modali di visualizzazione rapida). | Questo hook assicura che gli shortcode vengano elaborati e sostituiti anche all'interno del contenuto caricato tramite AJAX per le visualizzazioni rapide dei prodotti, mantenendo la coerenza. |

## 5. Supporto ufficiale e aggiornamenti
Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Shortcodes", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e compatibilità del modulo.
