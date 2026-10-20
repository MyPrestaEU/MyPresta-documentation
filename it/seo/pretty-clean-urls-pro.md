---
title: "Pretty / Clean URLs PRO - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Pretty / Clean URLs PRO di MyPresta.eu."
sidebar:
  label: "Pretty / Clean URLs PRO - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Pretty / Clean URLs PRO su MyPresta.eu](https://mypresta.eu/modules/seo/pretty-clean-urls-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/seo/pretty-clean-urls-pro/)
>
> ---


# Pretty / Clean URLs PRO

## 1. Requisiti e Compatibilità

-   **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.0.0 - 1.7.4.x, 1.7.5.0 - 1.7.7.x, 1.7.8.x, 8.x, 9.x
-   **Compatibilità PHP**: PHP 5.6 - 8.5
-   **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL). Il tuo server deve anche avere `mod_rewrite` abilitato per Apache o funzionalità equivalenti di riscrittura URL per Nginx, che è standard per la maggior parte delle installazioni PrestaShop.
-   **URL Amichevoli di PrestaShop**: L'opzione nativa "URL amichevoli" di PrestaShop (che si trova in **Parametri negozio > SEO e URL**) *deve essere abilitata* affinché questo modulo funzioni correttamente. Questo modulo migliora la funzionalità nativa di PrestaShop, non la sostituisce.

## 2. Guida Completa alla Configurazione

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" verrai indirizzato alla pagina di configurazione principale per "Pretty / Clean URLs PRO". Qui è dove controlli il comportamento principale del modulo.

**Impostazioni Generali**

-   **Abilita URL Amichevoli:**
    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per il modulo. Controlla se il modulo genera e utilizza attivamente URL puliti in tutto il tuo negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il modulo inizierà a generare e reindirizzare a URL puliti per tutti i tipi di pagina supportati (prodotti, categorie, CMS, ecc.).
        -   *Quando disabilitato:* Il modulo sarà inattivo e PrestaShop tornerà alla sua struttura URL predefinita (che potrebbe includere ID).
    -   **Valore consigliato:** **SÌ** (Questa è la funzione principale del modulo).
    -   **Scenario / esempio per il commerciante:** Hai appena installato il modulo e vuoi attivare i suoi benefici SEO. Abiliteresti questa impostazione. Se hai bisogno di risolvere temporaneamente un problema o tornare al comportamento predefinito di PrestaShop, potresti disabilitarlo.
-   **Rimuovi ID dagli URL:**
    -   **Cosa fa questa impostazione:** Questa opzione controlla specificamente se l'ID numerico (ad esempio, `123` in `iltuonegozio.com/123-il-mio-prodotto`) viene rimosso dagli URL.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Gli URL saranno più brevi e puliti, come `iltuonegozio.com/il-mio-prodotto`. Questo è generalmente migliore per la SEO e l'estetica.
        -   *Quando disabilitato:* Gli URL saranno comunque "pretty" ma manterranno l'ID, ad esempio, `iltuonegozio.com/123-il-mio-prodotto`. Questo potrebbe essere utile se hai sistemi esterni che si basano sulla presenza dell'ID nell'URL, anche se è meno comune.
    -   **Valore consigliato:** **SÌ** (Per il massimo beneficio SEO e un'estetica pulita).
    -   **Scenario / esempio per il commerciante:** Vuoi gli URL più puliti possibili per una migliore indicizzazione sui motori di ricerca e leggibilità per l'utente. Abiliteresti questa opzione.
-   **Reindirizzamento automatico 301:**
    -   **Cosa fa questa impostazione:** Questa impostazione critica indica al modulo di creare automaticamente reindirizzamenti permanenti 301 dagli URL vecchi, basati su ID, ai nuovi URL puliti.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Qualsiasi visitatore o bot di motore di ricerca che tenta di accedere a un vecchio URL (ad esempio, uno che è stato indicizzato prima che il modulo fosse attivo) verrà reindirizzato senza problemi al nuovo URL pulito. Questo previene errori 404 e preserva il tuo valore SEO.
        -   *Quando disabilitato:* I vecchi URL porteranno a errori 404 "Pagina non trovata", il che è negativo per l'esperienza utente e può danneggiare gravemente la tua SEO.
    -   **Valore consigliato:** **SÌ** (Assolutamente essenziale per mantenere la SEO e l'esperienza utente durante e dopo la transizione a URL puliti).
    -   **Scenario / esempio per il commerciante:** Hai appena attivato il modulo su un negozio esistente con molte pagine indicizzate. L'abilitazione di questa opzione garantisce che tutti i tuoi vecchi link continuino a funzionare e trasmettano il loro valore SEO ai nuovi link.
-   **Forza barra finale:**
    -   **Cosa fa questa impostazione:** Determina se una barra finale (`/`) viene sempre aggiunta alla fine dei tuoi URL (ad esempio, `iltuonegozio.com/categoria/` vs. `iltuonegozio.com/categoria`).
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Tutti gli URL generati termineranno con una barra. Questo può aiutare con la coerenza degli URL e alcuni strumenti SEO lo preferiscono.
        -   *Quando disabilitato:* Gli URL non termineranno necessariamente con una barra, a seconda del comportamento predefinito di PrestaShop per quel tipo di pagina.
    -   **Valore consigliato:** **SÌ** (Per coerenza e per evitare potenziali problemi di contenuto duplicato se i motori di ricerca trattano `url` e `url/` come pagine diverse).
    -   **Scenario / esempio per il commerciante:** Vuoi assicurarti che tutti gli URL delle tue categorie e pagine CMS terminino costantemente con una barra per una migliore gestione SEO e per prevenire potenziali problemi di contenuto duplicato.
-   **Rimuovi estensione .html:**
    -   **Cosa fa questa impostazione:** Questa opzione controlla se l'estensione `.html` viene rimossa dagli URL delle pagine prodotto e CMS.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Gli URL saranno ancora più brevi, ad esempio, `iltuonegozio.com/il-mio-prodotto` invece di `iltuonegozio.com/il-mio-prodotto.html`. Questo è generalmente preferito per il design web moderno e la SEO.
        -   *Quando disabilitato:* Gli URL delle pagine prodotto e CMS manterranno l'estensione `.html`.
    -   **Valore consigliato:** **SÌ** (Per la struttura URL più pulita e moderna).
    -   **Scenario / esempio per il commerciante:** Vuoi che le tue pagine prodotto appaiano come `iltuonegozio.com/il-mio-prodotto` invece di `iltuonegozio.com/il-mio-prodotto.html` per un aspetto più elegante e una migliore SEO.

**Pulsante Salva:**

-   Clicca sempre sul pulsante "Salva" dopo aver apportato modifiche per applicarle al tuo negozio.

### 2.2 Schermate di Amministrazione Dedicate e Viste Controller

Questo modulo funziona principalmente sovrascrivendo le classi e i controller principali di PrestaShop per modificare la generazione e il routing degli URL. Sebbene non introduca una nuova voce di menu dedicata nel Back Office per la gestione di un elenco di "URL Amichevoli", si integra direttamente con le funzionalità esistenti di PrestaShop.

**Integrazione con AdminProductsController (Back Office > Catalogo > Prodotti)**

-   **Nome schermata e posizione menu:** **Catalogo > Prodotti**
-   **Azioni e impostazioni disponibili:**
    -   Quando modifichi o crei un prodotto, il modulo influenza il comportamento del campo "URL amichevole". Invece di richiedere la rimozione manuale degli ID o di garantire una struttura pulita, la logica del modulo genererà e suggerirà automaticamente un URL pulito e senza ID basato sul nome del prodotto e sulle impostazioni del modulo.
    -   Il modulo garantisce che quando salvi un prodotto, il suo URL venga generato in base alle tue impostazioni "Pretty / Clean URLs PRO" (ad esempio, senza ID, senza estensione `.html` se configurato).
-   **Effetto delle modifiche:**
    -   Quando salvi un prodotto, l'URL generato e utilizzato da PrestaShop rifletterà la struttura URL pulita definita nella configurazione del modulo.
    -   Se modifichi il nome di un prodotto, il modulo ti aiuterà a garantire che l'URL amichevole venga aggiornato in modo pulito.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    -   Continua a gestire i tuoi prodotti come al solito in **Catalogo > Prodotti**. Il modulo lavora in background per garantire che gli URL siano ottimizzati.
    -   Quando crei o modifichi prodotti, assicurati che i nomi dei tuoi prodotti siano descrittivi, poiché questi vengono utilizzati per generare gli URL amichevoli.
    -   Puoi comunque regolare manualmente il campo "URL amichevole" per un prodotto se hai bisogno di un URL specifico, ma la logica del modulo guiderà la generazione iniziale.

**Altri Controller di Amministrazione (Integrazione Implicita)**

Il modulo influisce implicitamente anche su altre aree in cui vengono generati gli URL, come:

-   **Catalogo > Categorie**: Quando si creano o modificano categorie.
-   **Catalogo > Produttori**: Quando si creano o modificano produttori.
-   **Catalogo > Fornitori**: Quando si creano o modificano fornitori.
-   **Design > Pagine (CMS)**: Quando si creano o modificano pagine CMS.

In tutti questi casi, il modulo garantisce che gli URL amichevoli generati da PrestaShop aderiscano alle impostazioni "Pretty / Clean URLs PRO", rimuovendo ID ed estensioni come configurato.

### 2.3 Integrazione delle Impostazioni SEO e URL di PrestaShop

Il modulo "Pretty / Clean URLs PRO" dalla versione 2.8.3 e successive ha una propria sezione dedicata per la definizione degli schemi URL, rendendo non necessario configurare manualmente queste impostazioni nella sezione nativa di PrestaShop **Parametri negozio > SEO e URL**. Tuttavia, è fondamentale comprendere l'interazione.

:::caution Nota importante
Mentre il modulo gestisce lo schema URL, l'opzione nativa di PrestaShop **URL amichevole** in **Parametri negozio > SEO e URL** *deve essere abilitata* affinché il modulo funzioni. Il modulo migliora questa funzionalità principale di PrestaShop.
:::

**Schema degli URL (Gestito dal Modulo)**

Storicamente, gli utenti di PrestaShop definivano i pattern URL (rotte) per prodotti, categorie, pagine CMS, ecc., nella sezione **Parametri negozio > SEO e URL**. Il modulo "Pretty / Clean URLs PRO" ora si assume questa responsabilità, consentendoti di configurarli direttamente dalla sua pagina di configurazione.

Il modulo garantisce che le rotte siano impostate per rimuovere `{id}` dagli URL, il che è essenziale per URL veramente puliti. Se, per qualsiasi motivo, scopri che le rotte in **Parametri negozio > SEO e URL** contengono ancora `{id}` dopo aver installato e configurato il modulo, ciò potrebbe indicare un problema con le sovrascritture del modulo (vedi Sezione 6 per la risoluzione dei problemi).

Per riferimento, ecco le strutture di rotta consigliate che il modulo mira a implementare:

| Tipo di rotta       | Valore PrestaShop predefinito (Esempio) | Valore desiderato dal modulo (Pulito) |
| :------------------ | :-------------------------------------- | :------------------------------------ |
| Rotta al prodotto   | `{category:/}{id}-{rewrite}{-:ean13}.html` | `{category:/}{rewrite}.html` (o `{rewrite}.html`) |
| Rotta alla categoria | `{id}-{rewrite}`                        | `{parent_categories:/}{rewrite}/` (o `{rewrite}/`) |
| Rotta al fornitore  | `{id}__{rewrite}`                       | `supplier/{rewrite}/`                 |
| Rotta al produttore | `{id}_{rewrite}`                        | `manufacturer/{rewrite}/`             |
| Rotta alla pagina CMS | `content/{id}-{rewrite}`                | `info/{rewrite}.html`                 |
| Rotta alla pagina categoria CMS | `content/category/{id}-{rewrite}` | `info/{rewrite}`                      |

:::tip Ambiente Multistore
Se stai utilizzando un Multistore PrestaShop, ricorda di verificare e, se necessario, regolare le impostazioni dello schema URL per ogni singolo negozio. Puoi selezionare il negozio che desideri configurare dal menu contestuale del negozio nel tuo Back Office.
:::

### 2.4 Tabella di Riferimento Rapido per la Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Config. Modulo | Abilita URL Amichevoli | SÌ | Attiva/disattiva la funzionalità principale del modulo. |
| Config. Modulo | Rimuovi ID dagli URL | SÌ | Rimuove gli ID numerici dagli URL (es. `123-prodotto` diventa `prodotto`). |
| Config. Modulo | Reindirizzamento automatico 301 | SÌ | Reindirizza i vecchi URL basati su ID ai nuovi URL puliti, preservando la SEO. |
| Config. Modulo | Forza barra finale | SÌ | Assicura che tutti gli URL terminino con `/` per coerenza e SEO. |
| Config. Modulo | Rimuovi estensione .html | SÌ | Rimuove `.html` dagli URL delle pagine prodotto/CMS per link più puliti. |
| Catalogo > Prodotti (Modifica) | Campo URL amichevole | Generato automaticamente | Il modulo influenza la generazione automatica di URL puliti per i prodotti. |
| Catalogo > Categorie (Modifica) | Campo URL amichevole | Generato automaticamente | Il modulo influenza la generazione automatica di URL puliti per le categorie. |
| Design > Pagine (Modifica) | Campo URL amichevole | Generato automaticamente | Il modulo influenza la generazione automatica di URL puliti per le pagine CMS. |
| Parametri negozio > SEO e URL | URL amichevole | SÌ | **CRITICO:** Deve essere abilitato affinché il modulo funzioni. |

## 3. Risoluzione dei Problemi per il Commerciante e Domande Frequenti (FAQ)

**D1: Dopo l'installazione, i miei URL hanno ancora lo stesso aspetto, o ricevo errori 404.**

-   **R:** Innanzitutto, assicurati che "Abilita URL Amichevoli" sia impostato su SÌ nella configurazione del modulo.
-   In secondo luogo, vai su **Parametri avanzati > Prestazioni** nel tuo Back Office di PrestaShop e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti).
-   In terzo luogo, assicurati che l'opzione nativa "URL amichevole" di PrestaShop sia abilitata in **Parametri negozio > SEO e URL**. Questo modulo migliora la funzionalità nativa degli URL amichevoli di PrestaShop, non la sostituisce completamente.
-   Infine, controlla il file `.htaccess` del tuo server (se usi Apache) o la configurazione di Nginx. Il modulo si basa sulla riscrittura URL lato server (mod\_rewrite per Apache) per funzionare correttamente. Se non sei sicuro, contatta il tuo provider di hosting.

**D2: Il mio tema personalizzato presenta strani problemi di visualizzazione dopo aver abilitato il modulo.**

-   **R:** Questo modulo influisce principalmente sulla generazione e sul reindirizzamento degli URL, non sulla visualizzazione visiva. È improbabile che causi direttamente problemi di visualizzazione del tema. Tuttavia, se hai svuotato la cache, il CSS o il JS del tuo tema potrebbero dover essere ricaricati. Prova a svuotare la cache del tuo browser. Se il problema persiste, potrebbe essere un conflitto con un altro modulo o una modifica personalizzata del tema. Disabilita temporaneamente "Pretty / Clean URLs PRO" per vedere se il problema si risolve. In tal caso, contatta il supporto MyPresta.eu.

**D3: Questo modulo funzionerà con i miei URL personalizzati o reindirizzamenti esistenti?**

-   **R:** Il modulo si concentra sulla generazione di URL puliti per le entità principali di PrestaShop (prodotti, categorie, CMS, ecc.). Se hai creato manualmente reindirizzamenti personalizzati o URL amichevoli specifici al di fuori del sistema standard di PrestaShop, il reindirizzamento automatico 301 del modulo darà priorità ai propri URL puliti generati. È generalmente meglio lasciare che il modulo gestisca tutti gli URL delle entità principali per coerenza. Se hai reindirizzamenti personalizzati molto specifici, potresti dover testare come interagiscono.

**D4: Ho cambiato il nome di un prodotto, ma l'URL non si è aggiornato automaticamente.**

-   **R:** Quando modifichi il nome di un prodotto, PrestaShop di solito suggerisce un nuovo URL amichevole. Devi salvare esplicitamente il prodotto affinché le modifiche abbiano effetto e affinché il modulo elabori il nuovo URL. Se il campo URL amichevole non si aggiorna automaticamente, potresti dover cliccare manualmente su "Genera URL" accanto al campo URL amichevole nella pagina di modifica del prodotto, quindi salvare il prodotto. Il modulo garantirà quindi che questo nuovo URL sia pulito e gestirà il reindirizzamento dal vecchio.

**D5: Questo modulo influisce sui miei URL multilingue?**

-   **R:** No, li migliora! Il modulo funziona con le capacità multilingue di PrestaShop. Genererà URL puliti per ogni lingua, rispettando il codice della lingua nell'URL (ad esempio, `/en/my-product` e `/fr/mon-produit`). Assicurati che i nomi dei tuoi prodotti, categorie e pagine CMS siano tradotti per ogni lingua per ottenere i migliori URL amichevoli.

**D6: Vedo un messaggio di errore "la parola chiave {id} è richiesta per la rotta (...)" quando cerco di salvare gli schemi URL.**

-   **R:** Questo errore si verifica tipicamente se le sovrascritture del modulo (una parte fondamentale della sua funzionalità) non sono installate correttamente o sono disabilitate nel tuo negozio PrestaShop. Il modulo si basa su queste sovrascritture per modificare il comportamento di routing URL predefinito di PrestaShop, consentendogli di rimuovere l'`{id}` dalle rotte.
    -   **Soluzione:**
        1.  **Controlla le sovrascritture:** Assicurati che il sistema di sovrascritture di PrestaShop sia abilitato. Di solito puoi trovare questa impostazione in **Parametri avanzati > Prestazioni**. Cerca un'opzione relativa a "Disabilita moduli non PrestaShop" o "Disabilita sovrascritture" e assicurati che sia impostata su "No".
        2.  **Reinstalla il modulo:** A volte, la reinstallazione del modulo può risolvere i problemi di sovrascrittura. Disinstalla il modulo, svuota la cache di PrestaShop e quindi reinstallalo.
        3.  **Controllo manuale delle sovrascritture:** Verifica che i file di sovrascrittura del modulo siano presenti nelle tue directory `override/classes/` e `override/controllers/` (ad esempio, `override/classes/Dispatcher.php`, `override/controllers/front/ProductController.php`). Se mancano, indica un problema di installazione.
    -   Se il problema persiste, contatta il supporto MyPresta.eu.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'Architettura

Il modulo "Pretty / Clean URLs PRO" opera sovrascrivendo le classi principali di PrestaShop, in particolare `Dispatcher` e `Link`, per modificare il modo in cui gli URL vengono generati e analizzati. Intercetta la logica predefinita di routing e generazione degli URL per rimuovere ID ed estensioni in base alle sue impostazioni di configurazione. Il modulo sfrutta il sistema di sovrascrittura di PrestaShop (`/override/`) per iniettare la sua logica personalizzata senza modificare direttamente i file core, garantendo la compatibilità con gli aggiornamenti. Include anche una sovrascrittura del controller di amministrazione per `AdminProductsController` per garantire che la generazione degli URL amichevoli nel back office si allinei con le impostazioni del modulo.

### 4.2 Controller (`controllers/`)

Il modulo utilizza principalmente sovrascritture del controller front-office per modificare la generazione e il routing degli URL.

-   **Controller Front-Office**:

    -   `purls/override/controllers/front/CartController.php`
        -   **Nome classe e classe padre**: `CartController` (sovrascrive `CartControllerCore`)
        -   **Responsabilità**: Modifica la generazione degli URL per i link relativi al carrello per garantire che siano puliti e senza ID, ove applicabile.
    -   `purls/override/controllers/front/CmsController.php`
        -   **Nome classe e classe padre**: `CmsController` (sovrascrive `CmsControllerCore`)
        -   **Responsabilità**: Modifica la generazione degli URL per le pagine CMS, rimuovendo ID ed estensioni `.html` come configurato.
    -   `purls/override/controllers/front/listing/CategoryController.php`
        -   **Nome classe e classe padre**: `CategoryController` (sovrascrive `CategoryControllerCore`)
        -   **Responsabilità**: Modifica la generazione degli URL per le pagine di categoria, rimuovendo ID e garantendo URL puliti.
    -   `purls/override/controllers/front/listing/index.php`
        -   **Nome classe e classe padre**: Non è un controller diretto, probabilmente un file vuoto o un segnaposto. L'autoloader di PrestaShop potrebbe rilevare altri file in questa directory.
        -   **Responsabilità**: Nessuna responsabilità diretta; serve come marcatore di directory.
    -   `purls/override/controllers/front/listing/ManufacturerController.php`
        -   **Nome classe e classe padre**: `ManufacturerController` (sovrascrive `ManufacturerControllerCore`)
        -   **Responsabilità**: Modifica la generazione degli URL per le pagine del produttore, rimuovendo ID e garantendo URL puliti.
    -   `purls/override/controllers/front/listing/SupplierController.php`
        -   **Nome classe e classe padre**: `SupplierController` (sovrascrive `SupplierControllerCore`)
        -   **Responsabilità**: Modifica la generazione degli URL per le pagine del fornitore, rimuovendo ID e garantendo URL puliti.
    -   `purls/override/controllers/front/ProductController.php`
        -   **Nome classe e classe padre**: `ProductController` (sovrascrive `ProductControllerCore`)
        -   **Responsabilità**: Modifica la generazione degli URL per le pagine prodotto, rimuovendo ID ed estensioni `.html` come configurato.
-   **Controller di Amministrazione Back-Office**:

    -   `purls/override/controllers/admin/AdminProductsController.php`
        -   **Nome classe e classe padre**: `AdminProductsController` (sovrascrive `AdminProductsControllerCore`)
        -   **Responsabilità**: Si integra con l'interfaccia di gestione dei prodotti per garantire che quando gli URL amichevoli vengono generati o aggiornati nel back office, aderiscano alle impostazioni del modulo (ad esempio, rimuovendo gli ID). Probabilmente modifica il metodo `generateFriendlyUrl` o una logica simile.

### 4.3 Classi Core e Modelli (`classes/`)

La logica principale del modulo risiede nelle sue sovrascritture di classe, che sono fondamentali per il modo in cui PrestaShop gestisce gli URL.

-   `purls/override/classes/Dispatcher.php`
    -   **Nome classe e classe padre**: `Dispatcher` (sovrascrive `DispatcherCore`)
    -   **Interazione con il database**: Nessuna diretta, ma interagisce con `ps_configuration` per le impostazioni del modulo.
    -   **Metodi pubblici chiave e logica di business**: Questa classe è responsabile del routing delle richieste in entrata al controller corretto e della generazione degli URL. La sovrascrittura probabilmente modifica metodi come `getFriendlyUrl` o `createUrl` per rimuovere ID ed estensioni e per gestire la logica di reindirizzamento 301 per i vecchi URL. È il punto centrale per l'analisi e la generazione degli URL.
-   `purls/override/classes/Link.php`
    -   **Nome classe e classe padre**: `Link` (sovrascrive `LinkCore`)
    -   **Interazione con il database**: Nessuna diretta, ma interagisce con `ps_configuration` per le impostazioni del modulo.
    -   **Metodi pubblici chiave e logica di business**: La classe `Link` viene utilizzata in tutto PrestaShop per costruire URL per varie entità (prodotti, categorie, CMS, ecc.). La sovrascrittura in questo modulo modifica metodi come `getProductLink`, `getCategoryLink`, `getCMSLink`, ecc., per generare URL puliti, senza ID e senza estensioni `.html` come da configurazione del modulo. Funziona in combinazione con la sovrascrittura di `Dispatcher` per garantire una generazione coerente degli URL.

### 4.4 Risorse JavaScript (`views/js/`)

-   `purls/views/js/purls.js`
    -   **Ambito**: Back-office (probabilmente nelle pagine di modifica di prodotti/categorie/CMS).
    -   **Dettagli**: Questo script contiene probabilmente la logica lato client per migliorare il processo di generazione degli URL amichevoli all'interno del Back Office di PrestaShop. Potrebbe:
        -   Ascoltare i cambiamenti nei nomi di prodotti/categorie/CMS e aggiornare automaticamente il campo "URL amichevole" in base alle impostazioni del modulo.
        -   Fornire feedback o convalida in tempo reale per gli URL generati.
        -   Potenzialmente interagire con chiamate AJAX al server per ottenere URL amichevoli suggeriti.
        -   Garantire che il pulsante "Genera URL" (se presente) attivi la logica del modulo.

### 4.5 Fogli di Stile CSS (`views/css/`)

Nessun file CSS personalizzato è stato trovato nell'archivio del modulo, indicando che il modulo non introduce nuovi elementi visivi che richiedono uno stile specifico. Si basa sullo stile predefinito del Back Office di PrestaShop per la sua pagina di configurazione.

### 4.6 Struttura del Template Smarty (`views/templates/`)

-   **Template di amministrazione (`views/templates/admin/`)**:
    -   `purls/views/purls.tpl`
        -   **Ambito**: Back-office, pagina di configurazione del modulo.
        -   **Dettagli**: Questo template renderizza il modulo di configurazione principale per il modulo "Pretty / Clean URLs PRO". Contiene la struttura HTML per tutte le impostazioni descritte nella Sezione 4.1, inclusi gli interruttori per abilitare/disabilitare le funzionalità e il pulsante "Salva". Utilizza gli helper e lo stile standard dei moduli di PrestaShop.

### 4.7 Schema del Database e Mappa degli Hook

-   **Tabelle del database**:

    -   Il modulo non crea tabelle SQL personalizzate.
    -   Memorizza le sue impostazioni di configurazione nella tabella standard `ps_configuration` di PrestaShop. Le chiavi di configurazione seguirebbero tipicamente un pattern come `PURLS_ENABLE`, `PURLS_REMOVE_IDS`, `PURLS_301_REDIRECT`, ecc.
-   **Tabella degli Hook Registrati**:
    Il modulo opera principalmente tramite sovrascritture di classe piuttosto che tramite registrazione diretta di hook per la sua funzionalità principale. Tuttavia, potrebbe interagire implicitamente con hook che attivano la generazione o il reindirizzamento degli URL.

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| :-------- | :------------------ | :------------ |
| `displayHeader` | Ad ogni caricamento di pagina nel front office, all'interno della sezione `<head>`. | Sebbene non registri direttamente un elemento visivo, le sovrascritture di `Dispatcher` e `Link` del modulo sono attive durante il rendering della pagina, influenzando qualsiasi URL generato nell'intestazione (ad esempio, URL canonici, selettori di lingua). |
| `actionDispatcherBefore` | Prima che il dispatcher elabori la richiesta. | La sovrascrittura di `Dispatcher` è attiva in questa fase, consentendo al modulo di intercettare e modificare la logica di analisi e routing degli URL prima che PrestaShop determini quale controller caricare. Questo è cruciale per la gestione dei reindirizzamenti 301 da vecchi URL. |
| `actionDispatcherAfter` | Dopo che il dispatcher ha elaborato la richiesta. | La sovrascrittura di `Dispatcher` può essere attiva anche qui, potenzialmente per la post-elaborazione o la registrazione relativa alla gestione degli URL. |
| `actionProductUpdate` / `actionProductAdd` | Dopo che un prodotto viene aggiornato o aggiunto nel Back Office. | La sovrascrittura di `AdminProductsController` garantisce che quando un prodotto viene salvato, il suo URL amichevole venga generato in base alle impostazioni del modulo. Questa è un'interazione implicita piuttosto che una registrazione diretta di hook da parte del modulo stesso. |
| `actionCategoryUpdate` / `actionCategoryAdd` | Dopo che una categoria viene aggiornata o aggiunta nel Back Office. | Similmente ai prodotti, il modulo garantisce URL puliti per le categorie. |
| `actionCmsUpdate` / `actionCmsAdd` | Dopo che una pagina CMS viene aggiornata o aggiunta nel Back Office. | Similmente ai prodotti, il modulo garantisce URL puliti per le pagine CMS. |

## 5. Supporto Ufficiale e Risorse

Per aggiornamenti ufficiali, supporto tecnico e qualsiasi domanda relativa al modulo "Pretty / Clean URLs PRO", fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda possiate avere.
