---
title: "Prodotti nelle pagine CMS - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Prodotti nelle pagine CMS di MyPresta.eu."
sidebar:
  label: "Prodotti nelle pagine CMS - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Products on CMS pages su MyPresta.eu](https://mypresta.eu/modules/front-office-features/products-on-cms-pages.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/products-on-cms-pages/)
>
> ---


# Prodotti nelle pagine CMS

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste da PrestaShop stesso e sono sufficienti per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo "Prodotti nelle pagine CMS" in Gestione moduli. Vedrai la schermata di configurazione principale.

#### **Nascondi prodotti e shortcode**

- **Cosa fa questa impostazione:** Questa impostazione controlla se il modulo elabora e visualizza i prodotti dagli shortcode che hai inserito nelle tue pagine CMS. Influisce anche sulla visibilità degli shortcode stessi per i clienti se il modulo non li sta elaborando.
- **Effetto della modifica di questa impostazione:**
  - *Quando abilitato (SÌ):* Il modulo *non* elaborerà gli shortcode. Invece di visualizzare gli elenchi di prodotti, gli shortcode (ad esempio, `[products ids="1,2,3"]`) saranno nascosti alla vista del cliente nel front office. Questo è utile se vuoi disabilitare temporaneamente la visualizzazione dei prodotti senza rimuovere gli shortcode dal contenuto del tuo CMS.
  - *Quando disabilitato (NO):* Il modulo cercherà attivamente ed elaborerà gli shortcode nelle tue pagine CMS. Li sostituirà con gli elenchi di prodotti corrispondenti, rendendo i tuoi prodotti visibili ai clienti.
- **Valore consigliato:** **NO** (a meno che tu non voglia specificamente nascondere gli elenchi di prodotti e gli shortcode).
- **Scenario / esempio del commerciante:**
  - Hai impostato diverse pagine CMS con shortcode di prodotto per una promozione stagionale. Quando la promozione termina, invece di modificare manualmente ogni pagina CMS per rimuovere gli shortcode, puoi semplicemente abilitare "Nascondi prodotti e shortcode" per nascondere istantaneamente tutti gli elenchi di prodotti da quelle pagine. Quando inizia la prossima promozione, lo disabiliti di nuovo.

### 2.2 Come usare gli shortcode nelle tue pagine CMS

Questo modulo non ha schermate di amministrazione dedicate oltre alla configurazione principale. La sua funzionalità principale è controllata da "shortcode" che inserisci direttamente nel contenuto della tua pagina CMS.

**Per aggiungere prodotti a una pagina CMS:**

1.  Naviga su **Parametri negozio > Pagine CMS** nel tuo Back Office di PrestaShop.
2.  Modifica una pagina CMS esistente o creane una nuova.
3.  Nell'editor di contenuto principale (solitamente un editor di testo ricco come TinyMCE), puoi digitare o incollare gli shortcode.

**Shortcode disponibili:**

-   **Visualizza prodotti specifici per ID:**

    -   `[products ids="1,2,3,4"]`
    -   **Scopo:** Questo shortcode ti consente di visualizzare un elenco di prodotti specifici tramite i loro numeri ID univoci. Puoi trovare gli ID dei prodotti nel tuo Back Office sotto **Catalogo > Prodotti**.
    -   **Esempio:** Se vuoi mostrare il Prodotto A (ID 1), il Prodotto B (ID 2) e il Prodotto C (ID 3), useresti `[products ids="1,2,3"]`.
-   **Visualizza prodotti da una categoria specifica:**

    -   `[products category="5"]`
    -   **Scopo:** Questo shortcode visualizza tutti i prodotti appartenenti a una categoria specifica. Puoi trovare gli ID delle categorie nel tuo Back Office sotto **Catalogo > Categorie** modificando una categoria e guardando l'URL o la colonna "ID" nell'elenco delle categorie.
    -   **Esempio:** Per mostrare tutti i prodotti della tua categoria "Elettronica" (supponendo che il suo ID sia 5), useresti `[products category="5"]`.
-   **Visualizza prodotti da un produttore/marchio specifico:**

    -   `[products manufacturer="1"]`
    -   **Scopo:** Questo shortcode visualizza tutti i prodotti associati a un particolare produttore o marchio. Gli ID dei produttori possono essere trovati sotto **Catalogo > Marchi e fornitori > Marchi**.
    -   **Esempio:** Per visualizzare tutti i prodotti di "Apple" (supponendo che il suo ID sia 1), useresti `[products manufacturer="1"]`.
-   **Visualizza nuovi prodotti:**

    -   `[products new="5"]`
    -   **Scopo:** Questo shortcode visualizza i prodotti aggiunti più di recente al tuo negozio. Il numero "5" indica quanti nuovi prodotti vuoi mostrare.
    -   **Esempio:** Per mostrare i 5 prodotti più recenti, usa `[products new="5"]`.
-   **Visualizza prodotti più venduti:**

    -   `[products bestseller="5"]`
    -   **Scopo:** Questo shortcode visualizza i tuoi prodotti più venduti. Il numero "5" indica quanti prodotti più venduti vuoi mostrare.
    -   **Esempio:** Per mostrare i tuoi 5 prodotti più venduti, usa `[products bestseller="5"]`.
-   **Visualizza prodotti in saldo:**

    -   `[products sale="5"]`
    -   **Scopo:** Questo shortcode visualizza i prodotti attualmente in saldo. Il numero "5" indica quanti prodotti in saldo vuoi mostrare.
    -   **Esempio:** Per mostrare 5 prodotti attualmente scontati, usa `[products sale="5"]`.
-   **Visualizza prodotti in evidenza (dalla homepage):**

    -   `[products featured="5"]`
    -   **Scopo:** Questo shortcode visualizza i prodotti contrassegnati come "in evidenza" sulla tua homepage (solitamente controllati dal modulo "Prodotti in evidenza"). Il numero "5" indica quanti prodotti in evidenza vuoi mostrare.
    -   **Esempio:** Per mostrare 5 dei tuoi prodotti in evidenza, usa `[products featured="5"]`.

**Note importanti:**

-   Puoi combinare shortcode sulla stessa pagina, ma ogni shortcode genererà il proprio elenco di prodotti.
-   Assicurati che non ci siano spazi extra o errori di battitura all'interno delle parentesi quadre `[]` dello shortcode.
-   Dopo aver aggiunto gli shortcode, salva la tua pagina CMS. I prodotti appariranno automaticamente nel front office (a meno che tu non abbia abilitato "Nascondi prodotti e shortcode" nella configurazione del modulo).

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Nascondi prodotti e shortcode | NO | Controlla se gli elenchi di prodotti dagli shortcode vengono visualizzati (NO) o nascosti (SÌ) nelle pagine CMS. |
| Editor pagina CMS | `[products ids="1,2,3"]` | N/A | Visualizza prodotti specifici tramite i loro ID. |
| Editor pagina CMS | `[products category="5"]` | N/A | Visualizza tutti i prodotti da una categoria specifica. |
| Editor pagina CMS | `[products manufacturer="1"]` | N/A | Visualizza tutti i prodotti da un produttore specifico. |
| Editor pagina CMS | `[products new="5"]` | N/A | Visualizza i 5 prodotti più recenti. |
| Editor pagina CMS | `[products bestseller="5"]` | N/A | Visualizza i 5 prodotti più venduti. |
| Editor pagina CMS | `[products sale="5"]` | N/A | Visualizza i 5 prodotti attualmente in saldo. |
| Editor pagina CMS | `[products featured="5"]` | N/A | Visualizza i 5 prodotti in evidenza dalla homepage. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei prodotti non vengono visualizzati sulla pagina CMS, ma gli shortcode sono visibili.**
R: Controlla la pagina di configurazione del modulo (**Moduli > Gestione moduli > Configura** per "Prodotti nelle pagine CMS"). Assicurati che "Nascondi prodotti e shortcode" sia impostato su **NO**. Se è impostato su SÌ, il modulo nasconderà i prodotti e gli shortcode stessi. Inoltre, ricontrolla la sintassi del tuo shortcode per eventuali errori di battitura o virgolette mancanti.

**D: I miei prodotti non vengono visualizzati, e nemmeno gli shortcode (solo spazio vuoto).**
R: Questo di solito significa che il modulo è attivo e sta cercando di elaborare gli shortcode, ma sta riscontrando un problema.
1.  **Svuota la cache di PrestaShop:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" in alto a destra.
2.  **Controlla gli ID prodotto/ID categoria:** Assicurati che gli ID che stai utilizzando in `[products ids="..."]`, `[products category="..."]` o `[products manufacturer="..."]` siano corretti e corrispondano a prodotti/categorie/produttori esistenti e attivi nel tuo negozio.
3.  **Visibilità del prodotto:** Assicurati che i prodotti che stai cercando di visualizzare siano attivi e visibili nel tuo negozio (non disabilitati, esauriti se la gestione delle scorte è rigorosa o impostati su "nascosto").

**D: I prodotti appaiono, ma non hanno un bell'aspetto con lo stile del mio tema.**
R: Il modulo utilizza uno stile di base, ma il CSS del tuo tema potrebbe sovrascrivere o entrare in conflitto con esso.
1.  **Personalizzazione del tema:** La maggior parte dei temi ha opzioni per CSS personalizzati. Tu o il tuo webmaster potete aggiungere regole CSS personalizzate per mirare agli elenchi di prodotti generati da questo modulo.
2.  **Contatta lo sviluppatore del tema:** Se non sei sicuro, contatta lo sviluppatore del tuo tema per consigli su come stilizzare al meglio le griglie dei prodotti.
3.  **Contatta il supporto MyPresta.eu:** Se sospetti un problema di stile specifico del modulo, contatta il supporto MyPresta.eu.

**D: Posso usare più shortcode sulla stessa pagina CMS?**
R: Sì, puoi usare tutti gli shortcode diversi che vuoi su una singola pagina CMS. Ogni shortcode genererà il proprio elenco separato di prodotti.

**D: Questo modulo supporta i negozi multilingue?**
R: Sì, il modulo funziona con le capacità multilingue di PrestaShop. I nomi e le descrizioni dei prodotti visualizzati saranno nella lingua selezionata dal cliente, proprio come nelle normali pagine di prodotto o categoria. Gli shortcode stessi (`[products ids="..."]`) rimangono gli stessi in tutte le lingue.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Prodotti nelle pagine CMS" funziona principalmente sovrascrivendo il core `CmsController` per intercettare ed elaborare il contenuto prima che venga renderizzato all'utente. Utilizza espressioni regolari per trovare shortcode specifici all'interno del contenuto della pagina CMS e li sostituisce con elenchi di prodotti generati dinamicamente. I dati del prodotto vengono recuperati utilizzando i metodi `Product::getProducts` e `Product::getProductsProperties` di PrestaShop, quindi renderizzati tramite i template Smarty.

### 4.2 Controller (`controllers/`)

Questo modulo utilizza un override per estendere la funzionalità core di PrestaShop.

-   **Controller Front-Office**:

    -   `cmsproducts/override/controllers/front/CmsController.php`
        -   **Nome classe e classe genitore**: `CmsController` (sovrascrive `CmsControllerCore`)
        -   **Responsabilità**: Questo è il cuore della funzionalità del modulo. Sovrascrive il metodo `initContent()` del `CmsController` standard. All'interno di `initContent()`, recupera il contenuto della pagina CMS, lo scansiona per gli shortcode definiti (ad esempio, `[products ids="..."]`), elabora questi shortcode recuperando i dati del prodotto pertinenti e quindi sostituisce gli shortcode con l'HTML del prodotto renderizzato prima che il contenuto della pagina venga visualizzato. Assicura anche che il CSS del modulo sia caricato.
    -   `cmsproducts/override/controllers/front/index.php`
        -   **Nome classe e classe genitore**: N/A (file vuoto)
        -   **Responsabilità**: Questo è un file `index.php` vuoto standard posizionato nelle sottodirectory per prevenire l'elenco delle directory, una pratica di sicurezza comune. Non ha alcun impatto funzionale sulla logica del modulo.
-   **Controller Admin Back-Office**: Nessuno. La configurazione del modulo è gestita direttamente all'interno del metodo `getContent()` della classe principale del modulo.

### 4.3 Classi e modelli core (`classes/`)

Non sono presenti classi personalizzate o definizioni di `ObjectModel` in questo modulo. Sfrutta le classi core esistenti di PrestaShop come `Product`, `Category`, `Manufacturer`, `Context`, `Tools` e `Configuration`.

### 4.4 Risorse JavaScript (`views/js/`)

Nessun file JavaScript personalizzato è incluso in questo modulo. Tutte le funzionalità sono gestite lato server tramite PHP.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo include due file CSS per lo stile degli elenchi di prodotti. Questi vengono caricati tramite l'hook `actionAdminControllerSetMedia` (per il contesto del back-office, anche se l'override gestisce il caricamento del front-office).

-   `cmsproducts/cmsproducts.css`
    -   **Ambito**: Stile del cliente front-office.
    -   **Componenti UI principali e contenitori che stilizza**: Contiene lo stile generale per la griglia/elenco di prodotti generato dagli shortcode. Questo includerebbe stili per i contenitori dei prodotti, immagini, nomi, prezzi e potenzialmente pulsanti "Aggiungi al carrello" per garantire un aspetto coerente.
    -   **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere**: Probabilmente mira a classi come `.cmsproducts-product-list`, `.cmsproducts-product-item`, `.cmsproducts-product-image`, `.cmsproducts-product-name`, `.cmsproducts-product-price`.
-   `cmsproducts/css.css`
    -   **Ambito**: Stile del cliente front-office.
    -   **Componenti UI principali e contenitori che stilizza**: Simile a `cmsproducts.css`, questo file probabilmente fornisce regole di stile aggiuntive o specifiche per la visualizzazione del prodotto, potenzialmente per la reattività o per specifiche regolazioni del layout.
    -   **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere**: Simile a `cmsproducts.css`.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo utilizza i template Smarty per renderizzare gli elenchi di prodotti.

-   **Template hook (`views/templates/hook/`)**: Nessuno esplicitamente definito come template hook. I template vengono renderizzati direttamente dall'override di `CmsController`.
-   **Template admin (`views/templates/admin/`)**: Nessuno.
-   **Template front-office (`views/templates/front/`)**:
    -   `cmsproducts/html.tpl`
        -   **Scopo**: Questo template probabilmente funge da wrapper o da contenitore generale per gli elenchi di prodotti. Potrebbe includere una struttura HTML di base che circonda gli elementi del prodotto.
    -   `cmsproducts/products-carousel.tpl`
        -   **Scopo**: Questo template è progettato per renderizzare i prodotti in un formato carosello o slider. Contenerebbe la struttura HTML necessaria e potenzialmente l'inizializzazione JavaScript per un carosello di prodotti. Questo template è probabilmente utilizzato quando un parametro shortcode specifico o un'impostazione del modulo (non esposta nella configurazione attuale) implica una visualizzazione a carosello.
    -   `cmsproducts/products.tpl`
        -   **Scopo**: Questo è il template principale per renderizzare una griglia o un elenco standard di prodotti. Itera attraverso i dati del prodotto passati dal controller PHP e visualizza i dettagli dei singoli prodotti (immagine, nome, prezzo, pulsante aggiungi al carrello, ecc.). Questo è il template più comunemente usato per gli shortcode `[products ...]`.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**: Questo modulo non crea tabelle del database personalizzate. Memorizza le sue impostazioni di configurazione nella tabella standard `ps_configuration`.
    -   Voci `ps_configuration`:
        -   `mypresta_updates`: Memorizza le informazioni relative agli aggiornamenti del modulo da MyPresta.eu.
        -   `cmsproducts_hide`: Memorizza il valore dell'impostazione "Nascondi prodotti e shortcode" (1 per abilitato/SÌ, 0 per disabilitato/NO).
-   **Tabella degli hook registrati**:

| Nome hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Eseguito quando un Controller Admin imposta le sue risorse multimediali. | Sebbene elencato, il caricamento CSS primario per il front office è gestito dall'override di `CmsController`. Questo hook potrebbe essere utilizzato per un potenziale stile lato admin futuro o se il modulo avesse un controller admin. |

La funzionalità principale di elaborazione degli shortcode e rendering dei prodotti è ottenuta tramite l'override di `CmsController`, che manipola direttamente il contenuto prima della visualizzazione, piuttosto che affidarsi a un hook specifico del front-office per l'iniezione del contenuto.

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e per accedere alle ultime versioni del modulo "Prodotti nelle pagine CMS", visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assistere commercianti e sviluppatori con qualsiasi domanda o problema relativo al modulo.
