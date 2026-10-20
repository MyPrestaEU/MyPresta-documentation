---
title: "Homefeatured multi slider - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Homefeatured multi slider di MyPresta.eu."
sidebar:
  label: "Homefeatured multi slider - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Homefeatured multi slider su MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/homefeatured-multi-slider.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/sliders-slideshows/homefeatured-multi-slider/)
>
> ---


# Homefeatured multi slider

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per il corretto funzionamento di un negozio PrestaShop. Questo modulo non ha requisiti di hosting insoliti o specifici oltre a un ambiente PrestaShop standard.

## 2. Panoramica completa della configurazione (Ogni impostazione raggruppata per schermata)

Il modulo "Homefeatured multi slider" offre due aree principali per la configurazione: la pagina di configurazione principale del modulo per le impostazioni generali e una schermata di amministrazione dedicata per la gestione degli slider di prodotti e delle categorie.

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata principale in cui imposterai il comportamento generale e l'aspetto del tuo slider di prodotti multi-featured. Per accedervi, vai su **Moduli > Gestione moduli**, trova "Homefeatured multi slider" e clicca su "Configura".

#### Scheda Impostazioni Generali

| Impostazione / Opzione | Cosa fa questa impostazione | Effetto della modifica di questa impostazione | Valore consigliato | Scenario / esempio per il commerciante |
| --- | --- | --- | --- | --- |
| **Visualizza nell'Hook** | Determina dove apparirà lo slider sul tuo sito web. | *Se impostato su `displayHome` (o hook di contenuto principale simile):* Lo slider sarà una caratteristica prominente sulla tua homepage. *Se impostato su `displayLeftColumn` o `displayRightColumn`:* Lo slider apparirà nelle barre laterali, solitamente più piccolo. *Se impostato su `displayFooter`:* Lo slider sarà nella parte inferiore delle tue pagine. | `displayHome` per uno slider prominente sulla homepage. | Vuoi che i tuoi prodotti principali in evidenza siano la prima cosa che i clienti vedono sulla tua homepage. |
| **Numero di prodotti da visualizzare** | Controlla quanti prodotti sono visibili nello slider in un dato momento. | *Se impostato su `4`:* Quattro prodotti verranno mostrati affiancati (se lo spazio lo consente). *Se impostato su `1`:* Sarà visibile solo un prodotto, spesso con immagini più grandi. | `4` o `5` per la maggior parte dei temi, a seconda delle dimensioni delle immagini dei tuoi prodotti e del design. | Hai immagini di prodotti grandi e vuoi mostrare meno articoli alla volta per maggiori dettagli, oppure hai immagini piccole e vuoi mostrarne di più. |
| **Velocità dello Slider (ms)** | Imposta la velocità con cui lo slider effettua le transizioni tra prodotti o diapositive. Misurato in millisecondi (1000ms = 1 secondo). | *Se impostato su `500`:* Le transizioni sono molto veloci. *Se impostato su `5000`:* Le transizioni sono lente, dando ai clienti più tempo per visualizzare ogni prodotto. | Da `3000` (3 secondi) a `5000` (5 secondi) per un'esperienza di visualizzazione confortevole. | Vuoi una visualizzazione dinamica e veloce dei prodotti, o un'esperienza di navigazione più rilassata e contemplativa. |
| **Autoplay Slider** | Determina se lo slider ruota automaticamente i prodotti senza interazione dell'utente. | *Se abilitato (SÌ):* Lo slider si sposterà automaticamente al prodotto successivo dopo la "Velocità dello Slider" impostata. *Se disabilitato (NO):* Lo slider cambierà diapositive solo quando il cliente clicca sulle frecce di navigazione. | `SÌ` per mantenere il contenuto dinamico e coinvolgente. | Vuoi assicurarti che tutti i prodotti in evidenza ottengano visibilità anche se i clienti non cliccano attivamente. |
| **Mostra Frecce di Navigazione** | Controlla la visibilità delle frecce "avanti" e "indietro" sullo slider. | *Se abilitato (SÌ):* Le frecce appaiono ai lati dello slider, consentendo la navigazione manuale. *Se disabilitato (NO):* I clienti devono fare affidamento sull'autoplay o su altri metodi di navigazione (se disponibili). | `SÌ` per un migliore controllo utente e accessibilità. | Vuoi che i clienti possano sfogliare facilmente i prodotti al proprio ritmo. |
| **Mostra Punti di Paginazione** | Controlla la visibilità di piccoli punti o indicatori, solitamente nella parte inferiore dello slider, che rappresentano ogni diapositiva. | *Se abilitato (SÌ):* Appaiono i punti, mostrando la posizione corrente della diapositiva e consentendo di saltare direttamente a diapositive specifiche. *Se disabilitato (NO):* I punti sono nascosti. | `SÌ` per un migliore orientamento dell'utente e accesso diretto alle diapositive. | Vuoi che i clienti sappiano quante diapositive ci sono e possano saltare direttamente a una specifica. |
| **Larghezza Immagine Prodotto (px)** | Imposta la larghezza delle immagini dei prodotti all'interno dello slider. | *Se impostato su `200`:* Le immagini saranno larghe 200 pixel. *Se impostato su `300`:* Le immagini saranno larghe 300 pixel. Questo influisce sulla dimensione complessiva e sul layout dello slider. | Da `250` a `350` pixel, a seconda del design del tuo tema e del "Numero di prodotti da visualizzare". | Le tue immagini di prodotti sono ad alta risoluzione e vuoi che appaiano più grandi, oppure le hai bisogno più piccole per adattare più prodotti. |
| **Altezza Immagine Prodotto (px)** | Imposta l'altezza delle immagini dei prodotti all'interno dello slider. | *Se impostato su `200`:* Le immagini saranno alte 200 pixel. *Se impostato su `300`:* Le immagini saranno alte 300 pixel. Questo funziona in combinazione con la larghezza per mantenere il rapporto d'aspetto o ritagliare. | Da `250` a `350` pixel, corrispondente alla larghezza scelta per immagini quadrate, o regolato per ritratto/paesaggio. | Hai immagini di prodotti con rapporti d'aspetto variabili e vuoi standardizzare la loro altezza di visualizzazione. |
| **Colore di Sfondo** | Ti permette di impostare un colore di sfondo personalizzato per l'intero blocco dello slider. | *Se impostato su `#FFFFFF` (bianco):* Lo sfondo dello slider sarà bianco. *Se impostato su `#F0F0F0` (grigio chiaro):* Lo sfondo sarà grigio chiaro. | Lascia vuoto per trasparente o usa un colore che si abbini al tuo tema. | Vuoi che lo slider risalti con un colore di sfondo distinto, o si integri perfettamente con lo sfondo della tua pagina. |
| **Colore Testo** | Imposta il colore per i nomi dei prodotti e altro testo all'interno dello slider. | *Se impostato su `#000000` (nero):* Il testo sarà nero. *Se impostato su `#333333` (grigio scuro):* Il testo sarà grigio scuro. | Un colore che fornisca un buon contrasto con il colore di sfondo scelto. | Devi assicurarti che i nomi dei prodotti siano facilmente leggibili sullo sfondo dello slider. |
| **Colore Prezzo** | Imposta il colore per i prezzi dei prodotti visualizzati nello slider. | *Se impostato su `#FF0000` (rosso):* I prezzi saranno rossi, spesso usati per le vendite. *Se impostato su `#008000` (verde):* I prezzi saranno verdi. | Un colore che faccia risaltare i prezzi, spesso il colore accentato del tuo marchio o un colore standard per i prezzi. | Vuoi che i prezzi siano altamente visibili e attirino l'attenzione. |

### 2.2 Schermate di amministrazione dedicate e viste del controller

Questo modulo include una sezione dedicata nel tuo Back Office di PrestaShop per gestire le categorie dei tuoi prodotti in evidenza e assegnare loro i prodotti.

#### Nome schermata e posizione del menu: "Multi Featured Slider"

Puoi trovare questa sezione navigando su:
**Moduli > Gestione moduli > Homefeatured multi slider > Configura**
Nella pagina di configurazione, vedrai una scheda o un link che porta all'interfaccia di gestione "Multi Featured Slider". In PrestaShop 1.7+, questo potrebbe apparire come una nuova voce di menu sotto "Catalogo" o "Moduli" se il modulo registra la propria scheda.

Questa schermata è gestita dal `AdminprosliderController` (situato in `multihomefeatured/controllers/admin/adminproslider.php`).

**Azioni e impostazioni disponibili:**

Questa schermata presenta tipicamente un elenco delle tue "categorie di prodotti in evidenza" create (riferite come "opinion" nel codice sottostante, ma che fungono funzionalmente da categorie per il tuo slider).

-   **Tabella di elenco:** Vedrai una tabella che elenca tutte le categorie personalizzate che hai creato per i tuoi prodotti in evidenza. Ogni riga probabilmente mostrerà:

    -   **# (ID):** Un identificatore unico per la categoria.
    -   **Nome Categoria:** Il nome che hai dato a questo gruppo di prodotti in evidenza (es. "Bestseller", "Nuovi Arrivi").
    -   **Stato:** Se la categoria è attiva (visibile nello slider) o inattiva.
    -   **Azioni:** Pulsanti per "Modifica" (modificare il nome della categoria, lo stato e assegnare prodotti) o "Elimina" la categoria.
-   **Aggiungi Nuova Categoria:** Ci sarà un pulsante (es. "Aggiungi Nuova Categoria" o "Aggiungi Nuovo") per creare un nuovo gruppo di prodotti in evidenza. Quando aggiungi o modifichi una categoria, tipicamente troverai:

    -   **Nome Categoria:** Un campo di input per definire il nome della tua categoria di prodotti in evidenza (es. "Offerte Stagionali", "Preferiti dei Clienti").
    -   **Interruttore Attivo/Inattivo:** Un interruttore per abilitare o disabilitare la visualizzazione di questa specifica categoria nello slider del front-office.
    -   **Assegnazione Prodotto:** Questa è la funzionalità principale. Probabilmente vedrai una barra di ricerca o un elenco di prodotti disponibili. Puoi cercare prodotti e aggiungerli a questa specifica categoria in evidenza. I prodotti possono solitamente essere riordinati all'interno della categoria.

**Effetto delle modifiche:**

-   **Aggiunta di una Nuova Categoria:** Crea una nuova scheda o sezione nello slider del tuo front-office. Puoi quindi popolarla con prodotti specifici.
-   **Modifica di una Categoria:**
    -   La modifica del **Nome Categoria** aggiorna l'etichetta visualizzata ai clienti nello slider.
    -   L'attivazione/disattivazione di **Attivo/Inattivo** mostra o nasconde immediatamente l'intera categoria e i suoi prodotti dallo slider del front-office.
    -   **Aggiunta/Rimozione Prodotti:** Aggiorna direttamente quali prodotti appaiono in quella specifica categoria dello slider.
    -   **Riordinamento Prodotti:** Modifica la sequenza in cui i prodotti appaiono all'interno dello slider di quella categoria.
-   **Eliminazione di una Categoria:** Rimuove permanentemente la categoria e tutti i suoi prodotti assegnati dallo slider. I prodotti stessi non vengono eliminati dal tuo negozio.

**Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

1.  **Pianifica le tue categorie:** Prima di creare, decidi i gruppi logici per i tuoi prodotti in evidenza (es. "Nuovi Arrivi", "In Offerta", "Bestseller", "Scelte Stagionali").
2.  **Crea Categorie:** Usa il pulsante "Aggiungi Nuovo" per creare ogni categoria, dandole un nome chiaro e descrittivo.
3.  **Assegna Prodotti:** Per ogni categoria, usa l'interfaccia di assegnazione prodotti per cercare e aggiungere i prodotti pertinenti. Assicurati di salvare le modifiche.
4.  **Ordina Prodotti:** Disponi i prodotti all'interno di ogni categoria nell'ordine in cui desideri che appaiano.
5.  **Rivedi e Attiva:** Una volta soddisfatto, assicurati che la categoria sia impostata su "Attiva".
6.  **Controlla il Front-Office:** Verifica sempre le modifiche sul tuo negozio live per assicurarti che lo slider appaia e funzioni come previsto.
7.  **Aggiornamenti Regolari:** Aggiorna periodicamente le tue categorie in evidenza con nuovi prodotti, articoli stagionali o articoli che desideri promuovere. Rimuovi gli articoli più vecchi o esauriti per mantenere lo slider fresco e pertinente.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Pagina Configurazione Modulo** | Visualizza nell'Hook | `displayHome` | Controlla dove appare lo slider (homepage, colonne, footer). |
|  | Numero di prodotti da visualizzare | `4` | Quanti prodotti sono visibili contemporaneamente nello slider. |
|  | Velocità dello Slider (ms) | `3000` - `5000` | Velocità delle transizioni automatiche delle diapositive. |
|  | Autoplay Slider | `SÌ` | Lo slider ruota automaticamente i prodotti. |
|  | Mostra Frecce di Navigazione | `SÌ` | Visualizza le frecce per la navigazione manuale. |
|  | Mostra Punti di Paginazione | `SÌ` | Visualizza i punti per l'indicazione delle diapositive e l'accesso diretto. |
|  | Larghezza Immagine Prodotto (px) | `250` - `350` | Imposta la larghezza delle immagini dei prodotti nello slider. |
|  | Altezza Immagine Prodotto (px) | `250` - `350` | Imposta l'altezza delle immagini dei prodotti nello slider. |
|  | Colore di Sfondo | Lascia vuoto / Abbinato al tema | Imposta il colore di sfondo del blocco dello slider. |
|  | Colore Testo | Abbinato al tema / `#333333` | Imposta il colore per i nomi e le descrizioni dei prodotti. |
|  | Colore Prezzo | Abbinato al tema / Colore accento | Imposta il colore per i prezzi dei prodotti. |
| **Schermata Admin "Multi Featured Slider"** | Aggiungi/Modifica Nome Categoria | Nome descrittivo (es. "Bestseller") | Crea/modifica una scheda/sezione nello slider. |
|  | Stato Categoria (Attivo/Inattivo) | `Attivo` | Mostra o nasconde un'intera categoria di prodotti in evidenza. |
|  | Assegna Prodotti alla Categoria | N/A | Seleziona quali prodotti appaiono in una specifica categoria dello slider. |
|  | Riordina Prodotti | N/A | Modifica l'ordine di visualizzazione dei prodotti all'interno di una categoria. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Il mio slider non appare sulla homepage dopo la configurazione.**

-   **R:** Per prima cosa, controlla se il modulo è abilitato e configurato per essere visualizzato nell'hook corretto (es. `displayHome`) nella pagina di configurazione principale del modulo. In secondo luogo, assicurati di aver creato almeno una categoria "Multi Featured Slider" e di averle assegnato dei prodotti, e che la categoria sia impostata su "Attiva" nella schermata di amministrazione dedicata. Infine, svuota la cache di PrestaShop (**Parametri Avanzati > Prestazioni > Svuota cache**).

**D2: Lo slider appare rotto o disallineato nel mio negozio.**

-   **R:** Questo è spesso un conflitto CSS con il tuo tema.
    1.  **Controlla le Dimensioni dell'Immagine:** Vai alla pagina di configurazione del modulo e verifica le impostazioni "Larghezza Immagine Prodotto" e "Altezza Immagine Prodotto". Assicurati che siano appropriate per il tuo tema e il numero di prodotti che desideri visualizzare.
    2.  **Sovrascritture del Tema:** Il tuo tema potrebbe avere stili in conflitto. Prova a passare temporaneamente al tema PrestaShop predefinito per vedere se il problema persiste. Se si risolve, è probabile che il CSS del tuo tema stia sovrascrivendo gli stili del modulo. Potrebbe essere necessario un web developer per creare una sovrascrittura CSS personalizzata nel file `custom.css` del tuo tema.
    3.  **Svuota Cache:** Svuota sempre la cache del tuo browser e la cache Smarty di PrestaShop dopo aver apportato modifiche relative al design.

**D3: Come posso cambiare l'ordine dei prodotti all'interno di una categoria dello slider?**

-   **R:** Vai alla schermata di amministrazione dedicata "Multi Featured Slider". Modifica la categoria specifica che desideri riordinare. All'interno dell'interfaccia di assegnazione prodotti, dovresti essere in grado di trascinare e rilasciare i prodotti per cambiarne l'ordine, oppure potrebbero esserci frecce su/giù accanto a ciascun prodotto. Ricorda di salvare le modifiche.

**D4: Posso tradurre i nomi delle categorie per diverse lingue?**

-   **R:** Sì, i moduli PrestaShop tipicamente supportano l'input multilingue per campi come i nomi delle categorie. Quando stai modificando un nome di categoria nella schermata di amministrazione "Multi Featured Slider", cerca un selettore di lingua (solitamente un'icona a bandiera) accanto al campo di input. Cliccaci sopra per inserire il nome per ogni lingua installata.

**D5: Lo slider è troppo veloce/lento, o l'autoplay non funziona.**

-   **R:** Regola l'impostazione "Velocità dello Slider (ms)" nella pagina di configurazione principale del modulo. Un numero più alto significa una transizione più lenta. Assicurati che "Autoplay Slider" sia impostato su `SÌ` se vuoi che ruoti automaticamente. Ricorda di salvare e svuotare la cache.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata del modulo "Homefeatured multi slider" per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo `Homefeatured multi slider` (nome interno `multihomefeatured`) segue un'architettura standard dei moduli PrestaShop, sfruttando il pattern MVC. Consiste principalmente in:

-   Un file del modulo principale (`ajax_multihomefeatured.php`) che gestisce l'installazione, la disinstallazione e il modulo di configurazione principale (`getContent()`).
-   Un front controller (`default.php`) per potenziali interazioni AJAX o logica di rendering specifica del front-office.
-   Un admin controller (`AdminprosliderController.php`) per gestire le "categorie di prodotti in evidenza" personalizzate (riferite come `opinion` nel contesto del database, ma che fungono funzionalmente da categorie).
-   Template Smarty per il rendering sia della configurazione del back-office che degli elementi dello slider del front-office.
-   JavaScript per la funzionalità dello slider e CSS per lo stile.

Il modulo non sembra utilizzare classi `ObjectModel` personalizzate basate sull'inventario fornito, suggerendo che potrebbe memorizzare le sue categorie personalizzate e le assegnazioni di prodotti direttamente in `ps_configuration` o in una tabella personalizzata gestita da `AdminprosliderController`.

### 4.2 Controller (`controllers/`)

#### Controller del Front-Office

-   `multihomefeatured/controllers/front/default.php`
    -   **Nome classe e classe genitore**: `MultihomefeaturedDefaultModuleFrontController` che estende `ModuleFrontController`.
    -   **Responsabilità**: Questo controller è probabilmente utilizzato per gestire richieste specifiche del front-office, potenzialmente per chiamate AJAX relative al contenuto dello slider, o per il rendering di una pagina autonoma se il modulo ne offrisse una. Data la funzione principale del modulo come slider, potrebbe gestire il caricamento dinamico dei contenuti o il recupero di dati specifici dei prodotti per lo slider.

#### Controller Admin del Back-Office

-   `multihomefeatured/controllers/admin/adminproslider.php`
    -   **Nome della scheda e entità gestita**: Questo controller gestisce le categorie personalizzate "Multi Featured Slider" e i prodotti ad esse associati. Probabilmente appare come una sotto-scheda o una voce dedicata all'interno del menu del Back Office di PrestaShop, spesso sotto "Catalogo" o "Moduli". L'entità gestita è concettualmente una "categoria di prodotti in evidenza", che il modulo internamente si riferisce come `opinion` nelle sue interazioni con il database.
    -   **Responsabilità**: Questo controller fornisce l'interfaccia CRUD (Create, Read, Update, Delete) per queste categorie personalizzate. Gestisce:
        -   L'elenco delle categorie esistenti.
        -   La visualizzazione di moduli per aggiungere nuove categorie.
        -   La visualizzazione di moduli per modificare categorie esistenti (inclusa l'assegnazione e il riordinamento dei prodotti).
        -   L'elaborazione delle sottomissioni dei moduli per la creazione/aggiornamento delle categorie.
        -   La gestione dell'eliminazione delle categorie.
        -   La gestione dell'associazione tra categorie e prodotti PrestaShop specifici.

### 4.3 Classi e Modelli Core (`classes/`)

Basandosi sull'inventario fornito, non ci sono classi PHP personalizzate esplicitamente elencate nella directory `classes/`. Ciò suggerisce che:

1.  Il modulo potrebbe essere più vecchio e manipolare direttamente le tabelle del database senza un `ObjectModel` dedicato.
2.  Il `AdminprosliderController` potrebbe gestire direttamente le interazioni con il database per la sua entità `opinion`.
3.  Il file del modulo principale (`ajax_multihomefeatured.php`) potrebbe contenere tutta la logica necessaria per la configurazione e la gestione di base dei dati.

Se i dati personalizzati (come le "categorie di prodotti in evidenza" e le loro assegnazioni di prodotti) sono memorizzati, sono o in `ps_configuration` (per semplici coppie chiave-valore) o in una tabella di database personalizzata che è gestita direttamente da `AdminprosliderController` senza una definizione formale di `ObjectModel` in `classes/`.

### 4.4 Risorse JavaScript (`views/js/`)

-   `multihomefeatured/js/jquery.catslider.16.js`
    -   **Ambito**: Front-office.
    -   **Descrizione**: Probabilmente una versione di un plugin jQuery per "category slider" o "content slider", specificamente adattato o destinato a PrestaShop 1.6.x. Gestirebbe l'animazione principale dello slider, la navigazione e la reattività.
-   `multihomefeatured/js/jquery.catslider.js`
    -   **Ambito**: Front-office.
    -   **Descrizione**: Simile al precedente, potenzialmente una versione più generica o per altre versioni di PrestaShop. Questo script inizializzerebbe lo slider, gestirebbe le transizioni, l'autoplay e l'interazione dell'utente (clic, swipe).
-   `multihomefeatured/js/jscolor/jscolor.js`
    -   **Ambito**: Back-office.
    -   **Descrizione**: Questa è una libreria JavaScript per un selettore di colori. Viene utilizzata nel modulo di configurazione del back-office per fornire un'interfaccia user-friendly per la selezione dei colori (es. per lo sfondo, il testo, i colori dei prezzi). Si lega a specifici campi di input per visualizzare il selettore di colori.
-   `multihomefeatured/js/modernizr.custom.63321.js`
    -   **Ambito**: Front-office.
    -   **Descrizione**: Modernizr è una libreria JavaScript che rileva le funzionalità HTML5 e CSS3 nel browser dell'utente. Viene spesso utilizzata per fornire il rilevamento delle funzionalità e meccanismi di fallback, garantendo che lo slider funzioni correttamente su diversi browser, specialmente quelli più vecchi che potrebbero mancare di determinate capacità di transizione o animazione CSS3.
-   `multihomefeatured/js/script.js`
    -   **Ambito**: Front-office e/o Back-office.
    -   **Descrizione**: Questo è probabilmente il file JavaScript personalizzato principale per il modulo. Contenerebbe:
        -   Logica di inizializzazione per il plugin `jquery.catslider`, passando le opzioni di configurazione dalle impostazioni del modulo.
        -   Listener di eventi per le frecce di navigazione, i punti di paginazione o le interazioni personalizzate.
        -   Potenzialmente chiamate AJAX al front controller `default.php` per il caricamento dinamico dei contenuti.
        -   Qualsiasi manipolazione DOM specifica o miglioramenti dell'interfaccia utente relativi allo slider.
        -   Nel back-office, potrebbe contenere script per la ricerca e l'assegnazione di prodotti all'interno dei moduli di `AdminprosliderController`.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `multihomefeatured/css/style.css`
    -   **Ambito**: Front-office.
    -   **Descrizione**: Questo è il foglio di stile principale per lo slider del front-office. Definisce l'aspetto visivo del contenitore dello slider, degli elementi del prodotto, delle frecce di navigazione, dei punti di paginazione, dei titoli dei prodotti, dei prezzi e di qualsiasi altro elemento visualizzato all'interno dello slider.
    -   **Selettori di classe CSS chiave**: Gli sviluppatori possono aspettarsi classi come `.multihomefeatured-slider`, `.slider-item`, `.product-image`, `.product-title`, `.product-price`, `.slider-nav-arrow`, `.slider-pagination` ecc., che possono essere sovrascritte nel file `custom.css` di un tema personalizzato o tramite il meccanismo di sovrascrittura del tema di PrestaShop.
-   `multihomefeatured/js/css/ui-lightness/jquery-ui-1.10.2.custom.css`
    -   **Ambito**: Back-office.
    -   **Descrizione**: Questo foglio di stile fa parte della libreria jQuery UI, in particolare il tema "UI-lightness". È probabilmente utilizzato nel back-office per lo stile di elementi come i selettori di data, le finestre di dialogo o altri componenti interattivi che potrebbero far parte dei moduli di `AdminprosliderController` (es. per l'autocomplete della ricerca prodotti, se implementato usando jQuery UI).

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template degli hook (`views/templates/hook/`)**:
    -   `multihomefeatured/header.tpl`
        -   **Hook**: Probabilmente `displayHeader` o `actionFrontControllerSetMedia`.
        -   **Output**: Include i file CSS e JavaScript specifici del modulo (`jquery.catslider.js`, `modernizr.custom.63321.js`, `style.css`, `script.js`) nella sezione `<head>` del front-office, assicurando che vengano caricati prima che lo slider venga renderizzato.
    -   `multihomefeatured/home.tpl`
        -   **Hook**: Configurabile (es. `displayHome`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`).
        -   **Output**: Questo è il template principale per la visualizzazione dello slider nel front-office. Contiene la struttura HTML per l'intero slider multi-categoria, incluse le schede per le diverse categorie e il contenitore per le diapositive dei prodotti. Itera attraverso le categorie e i prodotti configurati per costruire lo slider.
    -   `multihomefeatured/homeTab.tpl`
        -   **Hook**: Renderizzato internamente da `home.tpl`.
        -   **Output**: Questo template probabilmente renderizza una singola scheda o elemento di navigazione per una delle categorie di prodotti in evidenza (es. "Bestseller", "Nuovi Arrivi"). Fa parte della navigazione per passare tra i diversi slider di prodotti.
    -   `multihomefeatured/homeTabContents.tpl`
        -   **Hook**: Renderizzato internamente da `home.tpl`.
        -   **Output**: Questo template renderizza l'elenco effettivo dei prodotti per una singola categoria di prodotti in evidenza. Contiene il ciclo che visualizza le singole immagini dei prodotti, i nomi, i prezzi e potenzialmente i pulsanti "Aggiungi al carrello", tutto racchiuso nella struttura richiesta dal plugin `jquery.catslider`.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non definisce esplicitamente classi `ObjectModel` personalizzate, ma il `AdminprosliderController` gestisce un'entità denominata `opinion`. Ciò suggerisce fortemente che il modulo crea almeno una tabella personalizzata, probabilmente denominata `ps_multihomefeatured_opinion` (o simile, seguendo la convenzione del prefisso `ps_` di PrestaShop) per memorizzare:
        -   `id_multihomefeatured_opinion` (Chiave primaria)
        -   `name` (per il nome della categoria, potenzialmente multilingue)
        -   `active` (booleano per lo stato della categoria)
        -   Altri campi relativi alla configurazione della categoria.
    -   Inoltre, ci sarebbe una tabella di collegamento, ad esempio `ps_multihomefeatured_opinion_product`, per memorizzare la relazione molti-a-molti tra queste categorie e le voci `ps_product`, incluso un campo `position` per l'ordinamento.
    -   Le impostazioni di configurazione del modulo (come la velocità dello slider, le dimensioni dell'immagine, i colori) sono tipicamente memorizzate nella tabella `ps_configuration` con chiavi prefissate dal nome del modulo (es. `MULTIHOMEFEATURED_SLIDER_SPEED`).
-   **Tabella degli hook registrati**:

| Nome dell'Hook | Tempistica di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Inietta i file CSS e JavaScript del modulo per la funzionalità del front-office. |
| `displayHome` | Area del contenuto principale della homepage. | Renderizza lo slider di prodotti multi-categoria principale sulla homepage. |
| `displayLeftColumn` | Barra laterale sinistra delle pagine del front-office. | Renderizza una versione più piccola dello slider nella colonna sinistra. |
| `displayRightColumn` | Barra laterale destra delle pagine del front-office. | Renderizza una versione più piccola dello slider nella colonna destra. |
| `displayFooter` | Sezione inferiore di ogni pagina del front-office. | Renderizza lo slider nell'area del footer. |
| `displayProductExtraContent` (o hook simile della pagina prodotto) | Nella pagina del prodotto, sotto i dettagli del prodotto. | Potenzialmente utilizzato per visualizzare prodotti correlati in uno slider nelle pagine dei prodotti. |
| `actionFrontControllerSetMedia` | Prima che un front controller renderizzi il suo output. | Un modo più robusto per registrare risorse (CSS/JS) per pagine specifiche o globalmente. |
| `actionModuleInstall` | Durante l'installazione del modulo. | Crea tabelle del database, imposta valori di configurazione predefiniti, registra gli hook. |
| `actionModuleUninstall` | Durante la disinstallazione del modulo. | Pulisce le tabelle del database, rimuove i valori di configurazione, deregistra gli hook. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Homefeatured multi slider", si prega di fare riferimento al proprio account cliente su MyPresta.eu. È possibile scaricare le versioni più recenti del modulo dalla cronologia degli ordini. Per assistenza tecnica o richieste specifiche, si prega di contattare direttamente il supporto MyPresta.eu tramite il proprio account cliente.
"""
