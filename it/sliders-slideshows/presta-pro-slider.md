---
title: "Presta Pro Slider - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo Presta Pro Slider di MyPresta.eu."
sidebar:
  label: "Presta Pro Slider - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Presta Pro Slider su MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/presta-pro-slider.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/sliders-slideshows/presta-pro-slider/)
>
> ---


# Presta Pro Slider

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Non sono richieste configurazioni server insolite.

## 2. Panoramica completa della configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Presta Pro Slider)

Questa è la schermata di configurazione principale dove gestisci le impostazioni generali del tuo slider e aggiungi/modifica le singole slide.

#### Impostazioni generali dello slider

-   **Cosa fa questa impostazione:** Queste impostazioni controllano l'aspetto generale e il comportamento del tuo slider, come le sue dimensioni, la velocità di animazione e dove appare sul tuo sito.
-   **Effetto della modifica di questa impostazione:** La regolazione di questi valori avrà un impatto diretto su come lo slider appare e funziona per i tuoi clienti.

| Impostazione / Opzione | Cosa fa | Effetto della modifica | Valore consigliato | Scenario / Esempio per il commerciante |
| --- | --- | --- | --- | --- |
| **Larghezza Slider (px)** | Imposta la larghezza totale dello slider in pixel. | *Se impostato a 1000:* Lo slider sarà largo 1000 pixel. *Se impostato a 500:* Lo slider sarà largo 500 pixel. | `100%` (per larghezza intera) o un valore in pixel specifico come `1170` (comune per aree di contenuto). | Vuoi che il tuo slider occupi l'intera area di contenuto della tua homepage, che è larga 1170px. Inseriresti `1170`. Se vuoi che sia reattivo e occupi tutta la larghezza disponibile, usa `100%`. |
| **Altezza Slider (px)** | Imposta l'altezza totale dello slider in pixel. | *Se impostato a 400:* Lo slider sarà alto 400 pixel. *Se impostato a 250:* Lo slider sarà alto 250 pixel. | `350` - `500` (a seconda del contenuto dell'immagine). | Hai immagini banner di alta qualità che rendono al meglio con una certa altezza. Imposteresti questo valore a `450` per assicurarti che le tue immagini siano visualizzate senza essere troppo allungate o compresse. |
| **Velocità Animazione (ms)** | Controlla la velocità di transizione tra le slide, in millisecondi. | *Se impostato a 500:* Le slide passano rapidamente (0,5 secondi). *Se impostato a 2000:* Le slide passano lentamente (2 secondi). | `1000` (1 secondo) | Vuoi una transizione fluida e evidente tra le tue slide promozionali, ma non così lenta da annoiare i clienti. Impostarlo a `1000` offre un buon equilibrio. |
| **Autoplay** | Determina se lo slider avanza automaticamente alla slide successiva. | *Se abilitato (SÌ):* Le slide cambieranno automaticamente dopo un ritardo impostato. *Se disabilitato (NO):* Le slide cambieranno solo quando un cliente clicca sulle frecce di navigazione o sui punti. | `SÌ` | Vuoi che le tue promozioni principali scorrano automaticamente sulla homepage senza interazione del cliente. |
| **Velocità Autoplay (ms)** | Se Autoplay è abilitato, imposta il ritardo prima che appaia la slide successiva, in millisecondi. | *Se impostato a 5000:* Ogni slide viene visualizzata per 5 secondi. *Se impostato a 3000:* Ogni slide viene visualizzata per 3 secondi. | `5000` (5 secondi) | Hai molto testo sulle tue slide e vuoi dare ai clienti abbastanza tempo per leggerlo prima che appaia la slide successiva. Impostarlo a `7000` (7 secondi) sarebbe appropriato. |
| **Visualizza su Hook** | Seleziona l'hook di PrestaShop dove lo slider verrà visualizzato. | *Se impostato su `displayHeader`*: Lo slider appare nella parte superiore di ogni pagina. *Se impostato su `displayLeftColumn`*: Lo slider appare nella barra laterale sinistra. | `displayHome` (se disponibile, altrimenti `displayHeader` o `displayTop`) | Vuoi che lo slider sia una caratteristica prominente sulla tua homepage. Selezioneresti `displayHome` o `displayTop`. Se lo vuoi sulle pagine prodotto, potresti selezionare `displayProductFooter`. |
| **Colore Sfondo** | Imposta il colore di sfondo del contenitore dello slider. | *Se impostato a #FFFFFF:* Lo sfondo sarà bianco. *Se impostato a #000000:* Lo sfondo sarà nero. | `Lascia vuoto` (per trasparente) o un colore che si abbini al tuo tema. | Il tuo tema ha uno sfondo chiaro e vuoi che lo slider si integri perfettamente. Imposteresti questo valore a `#FFFFFF`. |
| **Colore Testo** | Imposta il colore predefinito per il testo all'interno dello slider (didascalie, descrizioni). | *Se impostato a #000000:* Il testo sarà nero. *Se impostato a #FF0000:* Il testo sarà rosso. | `#333333` (grigio scuro) | Le immagini del tuo slider sono luminose e hai bisogno di testo scuro per garantire la leggibilità. Imposteresti questo valore a `#333333`. |

#### Sezione Gestione Slide

Questa sezione ti permette di aggiungere, modificare ed eliminare le singole slide che compongono la tua presentazione.

-   **Pulsante Aggiungi Nuova Slide:** Clicca qui per aprire un modulo per creare una nuova slide.
-   **Elenco Slide Esistenti:** Visualizza una tabella di tutte le tue slide attualmente attive, solitamente con opzioni per modificarle o eliminarle.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### AdminprosliderController (Back Office > Moduli > Presta Pro Slider > Configura > "Aggiungi Nuova Slide" o "Modifica" una slide esistente)

Questa schermata appare quando clicchi su "Aggiungi Nuova Slide" o sull'icona "Modifica" accanto a una slide esistente nella configurazione principale. Ti permette di definire il contenuto e il comportamento di ogni singola slide.

-   **Nome schermata e posizione menu:** Accessibile dalla pagina di configurazione principale del modulo cliccando su "Aggiungi Nuova Slide" o sull'icona di modifica per una slide esistente.
-   **Azioni e impostazioni disponibili:** Questo modulo ti permette di inserire tutti i dettagli per una singola slide.

| Impostazione / Opzione | Cosa fa | Effetto della modifica | Valore consigliato | Scenario / Esempio per il commerciante |
| --- | --- | --- | --- | --- |
| **Titolo Slide (Didascalia)** | L'intestazione principale o il testo breve visualizzato sulla slide. | Questo testo apparirà in modo prominente sulla tua slide, solitamente con un carattere più grande. | Mantienilo conciso e d'impatto. | "Saldi Estivi!" o "Nuovi Arrivi" |
| **Descrizione Slide** | Testo più lungo che fornisce maggiori dettagli sul contenuto della slide. | Questo testo apparirà sotto il titolo, offrendo maggiori informazioni al cliente. | Fornisci abbastanza dettagli senza essere eccessivo. | "Fino al 50% di sconto su tutti i costumi da bagno per un periodo limitato!" |
| **Immagine Slide** | L'immagine di sfondo principale per questa specifica slide. | Questa immagine sarà il fulcro visivo della tua slide. | Immagine di alta qualità, pertinente e con buona risoluzione. | Una foto accattivante di una modella che indossa un nuovo vestito per una promozione di moda. |
| **URL Link** | L'indirizzo web (URL) a cui i clienti verranno indirizzati quando cliccano su questa slide. | *Se impostato:* Cliccando sulla slide il cliente viene portato a questo URL. *Se vuoto:* La slide non sarà cliccabile. | Un URL valido a un prodotto, categoria o pagina informativa. | Link alla tua pagina della categoria "Nuovi Arrivi": `https://tuonegozio.com/nuovi-arrivi` |
| **Apri in Nuova Finestra** | Determina se l'URL del link si apre in una nuova scheda/finestra del browser. | *Se abilitato (SÌ):* Il link si apre in una nuova scheda, mantenendo il tuo negozio aperto nella scheda originale. *Se disabilitato (NO):* Il link si apre nella stessa scheda, navigando via dalla tua pagina attuale. | `SÌ` (generalmente consigliato per link esterni o promozioni) | Stai collegando a un post di blog esterno o a un profilo di social media. Abiliteresti questa opzione per mantenere i tuoi clienti sul tuo negozio PrestaShop. |
| **Attivo** | Controlla se questa slide è attualmente visibile nello slider. | *Se abilitato (SÌ):* La slide farà parte della presentazione. *Se disabilitato (NO):* La slide sarà nascosta ma non eliminata, permettendoti di riattivarla in seguito. | `SÌ` per promozioni attive. | Hai una promozione stagionale che è finita, ma potresti riproporla l'anno prossimo. La imposteresti su `NO` invece di eliminarla. |
| **Ordine / Posizione** | Imposta l'ordine di visualizzazione di questa slide rispetto alle altre. | Le slide con numeri inferiori appaiono prima nella sequenza. | `1`, `2`, `3`, ecc., nell'ordine desiderato. | Vuoi che la tua slide "Saldi Estivi" appaia per prima, seguita da "Nuovi Arrivi". Imposteresti "Saldi Estivi" a `1` e "Nuovi Arrivi" a `2`. |

-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  **Pianifica le tue promozioni:** Decidi quali prodotti, categorie o messaggi vuoi evidenziare.
    2.  **Prepara le tue immagini:** Assicurati di avere immagini di alta qualità che si adattino alle dimensioni dello slider.
    3.  **Aggiungi nuove slide:** Usa il pulsante "Aggiungi Nuova Slide" per creare nuovi contenuti. Inserisci tutti i dettagli, inclusi titolo, descrizione, immagine e link.
    4.  **Ordina le tue slide:** Regola l'"Ordine / Posizione" per controllare la sequenza.
    5.  **Attiva/Disattiva:** Usa l'interruttore "Attivo" per gestire la visibilità senza eliminare i contenuti.
    6.  **Controlla sul front-office:** Controlla sempre il tuo slider sul negozio live per assicurarti che appaia e funzioni come previsto.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Configurazione Modulo** | Larghezza Slider (px) | `100%` o `1170` | Imposta la dimensione orizzontale dello slider. |
| | Altezza Slider (px) | `350` - `500` | Imposta la dimensione verticale dello slider. |
| | Velocità Animazione (ms) | `1000` | Controlla la velocità di transizione delle slide. |
| | Autoplay | `SÌ` | Fa avanzare automaticamente le slide. |
| | Velocità Autoplay (ms) | `5000` | Ritardo tra i cambi automatici delle slide. |
| | Visualizza su Hook | `displayHome` / `displayHeader` | Dove lo slider appare nel tuo negozio. |
| | Colore Sfondo | `Lascia vuoto` / `#FFFFFF` | Colore di sfondo dell'area dello slider. |
| | Colore Testo | `#333333` | Colore predefinito del testo per didascalie/descrizioni. |
| **Aggiungi/Modifica Slide** | Titolo Slide (Didascalia) | Conciso e d'impatto | Intestazione principale per la slide. |
| | Descrizione Slide | Informativa | Testo dettagliato per la slide. |
| | Immagine Slide | Immagine di alta qualità | Sfondo visivo per la slide. |
| | URL Link | URL valido | Destinazione quando si clicca sulla slide. |
| | Apri in Nuova Finestra | `SÌ` | Apre il link in una nuova scheda del browser. |
| | Attivo | `SÌ` | Attiva/disattiva la visibilità della slide. |
| | Ordine / Posizione | `1, 2, 3...` | Determina la sequenza delle slide. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Il mio slider non viene visualizzato nel front office, oppure viene visualizzato nel posto sbagliato.**

-   **R:** Innanzitutto, controlla l'impostazione "Visualizza su Hook" nella configurazione del modulo. Assicurati di aver selezionato l'hook corretto (es. `displayHeader`, `displayTop`, `displayHome`). Se il tuo tema ha nomi di hook personalizzati o non supporta esplicitamente un hook standard in quella posizione, lo slider potrebbe non apparire.
-   **R:** Inoltre, verifica che le singole slide siano contrassegnate come "Attive" nelle loro impostazioni. Se nessuna slide è attiva, non verrà visualizzato nulla.
-   **R:** Infine, svuota la cache di PrestaShop. Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota cache" in alto a destra. A volte, le modifiche non appaiono finché la cache non viene aggiornata.

**D2: Le immagini del mio slider appaiono sfocate o allungate.**

-   **R:** Questo di solito accade se le immagini caricate non corrispondono alle impostazioni di "Larghezza Slider" e "Altezza Slider", o se sono a bassa risoluzione.
-   **R:** **Soluzione:** Assicurati che le tue immagini siano ad alta risoluzione e idealmente abbiano lo stesso rapporto di aspetto delle dimensioni dello slider configurate. Ad esempio, se il tuo slider è largo 1200px e alto 400px, prova a caricare immagini che siano almeno 1200px per 400px. Potrebbe essere necessario ridimensionare o ritagliare le immagini prima di caricarle.

**D3: Il testo sulle mie slide è difficile da leggere.**

-   **R:** Questo è spesso un problema di contrasto tra l'"Immagine Slide" e il "Colore Testo" che hai scelto.
-   **R:** **Soluzione:**
    1.  Regola il "Colore Testo" nella configurazione principale del modulo a un colore che contrasti bene con le tue immagini (es. testo bianco su immagini scure, testo nero su immagini chiare).
    2.  Considera l'aggiunta di una sottile sovrapposizione alle tue immagini (potrebbe essere necessario un editor grafico per questo) per scurirle o schiarirle leggermente, rendendo il testo più evidente.
    3.  Mantieni il "Titolo Slide" e la "Descrizione Slide" concisi. Meno testo è spesso più facile da leggere rapidamente.

**D4: Come traduco i titoli e le descrizioni delle slide in diverse lingue?**

-   **R:** Quando modifichi una slide, dovresti vedere le schede di selezione della lingua accanto ai campi "Titolo Slide" e "Descrizione Slide" (se il tuo negozio PrestaShop ha più lingue abilitate).
-   **R:** **Soluzione:** Clicca sull'icona della bandiera o sulla scheda della lingua per ogni lingua che desideri tradurre, quindi inserisci il testo corrispondente per quella lingua. Ricorda di salvare le modifiche.

**D5: Le animazioni dello slider sono troppo veloci/lente, o l'autoplay non funziona.**

-   **R:** Controlla le impostazioni "Velocità Animazione (ms)", "Autoplay" e "Velocità Autoplay (ms)" nella configurazione principale del modulo.
-   **R:** **Soluzione:**
    -   Aumenta la "Velocità Animazione" per transizioni più lente, diminuiscila per transizioni più veloci.
    -   Assicurati che "Autoplay" sia impostato su `SÌ` se vuoi che le slide avanzino automaticamente.
    -   Regola la "Velocità Autoplay" per controllare quanto tempo viene visualizzata ogni slide prima di passare alla successiva. Ricorda che questi valori sono in millisecondi (1000ms = 1 secondo).

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo Presta Pro Slider segue un'architettura standard per i moduli PrestaShop, sfruttando il pattern MVC dove appropriato. Utilizza principalmente un singolo file di modulo principale (`ajax_proslider.php`) per la sua logica e configurazione di base, un controller amministrativo per la gestione delle slide e template front-office per il rendering dello slider. Si basa su jQuery e Modernizr per le sue animazioni e lo stile front-end. I dati delle slide sono archiviati direttamente nella tabella `ps_configuration` di PrestaShop, piuttosto che in un `ObjectModel` dedicato e una tabella di database personalizzata.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `controllers/front/default.php`
        -   **Nome classe e classe genitore**: `ProsliderDefaultModuleFrontController` che estende `ModuleFrontController`.
        -   **Responsabilità**: Questo controller è probabilmente destinato a una rotta predefinita o a un'azione specifica del front-office, sebbene il suo scopo esatto possa essere minimo dato che il modulo si aggancia principalmente ad aree di template esistenti. Gestirebbe le richieste a `tuonegozio.com/module/proslider/default` e potrebbe essere utilizzato per chiamate AJAX o per il rendering di una pagina autonoma se il modulo ne avesse una. Nel contesto di questo modulo, potrebbe essere un segnaposto o utilizzato per il recupero di dati specifici se il contenuto dello slider fosse caricato dinamicamente.
-   **Controller Admin Back-Office**:

    -   `controllers/admin/adminproslider.php`
        -   **Nome classe e classe genitore**: `AdminprosliderController` che estende `ModuleAdminController`.
        -   **Nome tab e entità gestita**: Questo controller gestisce le "slide" o "opinioni" (secondo il dossier, sebbene "opinione" sembri un errore di battitura e dovrebbe probabilmente essere "slide" o "proslider\_item" se fosse un ObjectModel). Fornisce l'interfaccia per aggiungere, modificare ed eliminare singole slide. Gestisce l'invio del modulo per i dettagli delle slide (titolo, descrizione, immagine, link, ecc.) e aggiorna la tabella `ps_configuration` o una tabella personalizzata se presente.

### 4.3 Classi e Modelli Core (`classes/`)

Il dossier del modulo indica l'assenza di classi o modelli personalizzati nella directory `classes/`. Ciò suggerisce che il modulo memorizza i suoi dati direttamente nella tabella `ps_configuration` utilizzando array serializzati o singole chiavi di configurazione per ogni slide, oppure potrebbe utilizzare un approccio più semplice, non-ORM, all'interno di `AdminprosliderController` per gestire i dati. Se utilizzasse `ObjectModel`, ci sarebbe una classe definita qui (es. `ProsliderSlide.php`).

### 4.4 Risorse JavaScript (`views/js/`)

-   `proslider/js/jquery.cslider.js`
    -   **Ambito**: Front-office.
    -   **Descrizione**: Questo è probabilmente il plugin jQuery principale responsabile della funzionalità dello slider animato. Gestisce le transizioni delle slide, la logica di autoplay, i controlli di navigazione e la reattività. Gli sviluppatori dovrebbero consultare questo file per comprendere i tipi di animazione dello slider e le opzioni disponibili.
-   `proslider/js/jscolor/jscolor.js`
    -   **Ambito**: Back-office.
    -   **Descrizione**: Una libreria JavaScript per un widget di selezione colori. Viene utilizzata nei moduli di configurazione del back-office del modulo per consentire ai commercianti di selezionare facilmente i colori di sfondo e del testo per lo slider.
-   `proslider/js/modernizr.custom.28468.js`
    -   **Ambito**: Front-office.
    -   **Descrizione**: Modernizr è una libreria JavaScript che rileva le funzionalità HTML5 e CSS3 nel browser dell'utente. Questa specifica build personalizzata è probabilmente utilizzata da `jquery.cslider.js` per fornire il rilevamento delle funzionalità e potenzialmente meccanismi di fallback per i browser più vecchi, garantendo animazioni fluide e compatibilità.
-   `proslider/js/script.js`
    -   **Ambito**: Front-office.
    -   **Descrizione**: Questo è il file JavaScript personalizzato principale del modulo. Inizializza il plugin `jquery.cslider.js` con le impostazioni specifiche configurate nel back office (larghezza, altezza, velocità, autoplay, ecc.). Collega i listener di eventi per la navigazione dello slider (se sono implementati controlli personalizzati) e assicura che lo slider funzioni correttamente nell'ambiente PrestaShop.
-   `proslider/tinymce16.inc.js`
    -   **Ambito**: Back-office.
    -   **Descrizione**: Questo file è un include per l'editor di testo ricco TinyMCE, specificamente configurato per PrestaShop 1.6.x. Viene utilizzato nei moduli del back-office per i campi "Descrizione Slide", consentendo ai commercianti di formattare il testo con HTML. Per PrestaShop 1.7.x e 8.x, potrebbe essere utilizzata l'integrazione nativa di TinyMCE di PrestaShop, oppure questo file potrebbe essere ancora caricato per compatibilità.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `proslider/css/style2.css`
    -   **Ambito**: Stile front-office per il cliente.
    -   **Descrizione**: Questo è il foglio di stile principale per lo slider front-end. Definisce l'aspetto visivo del contenitore dello slider, delle singole slide, delle didascalie, delle descrizioni, delle frecce di navigazione e dei punti di paginazione.
    -   **Selettori di classe CSS chiave**: Gli sviluppatori possono ispezionare questo file per classi come `.cs-slider`, `.cs-wrapper`, `.cs-bg`, `.cs-caption`, `.cs-description`, `.cs-nav`, `.cs-dots` per sovrascrivere o estendere lo stile nel CSS personalizzato del loro tema.
-   `proslider/js/css/ui-lightness/jquery-ui-1.10.2.custom.css`
    -   **Ambito**: Stile del modulo di amministrazione del back-office.
    -   **Descrizione**: Questa è una build personalizzata del framework CSS di jQuery UI, specificamente per il tema "UI-lightness". È probabilmente utilizzata per stilizzare gli elementi all'interno dei moduli di configurazione del back-office del modulo, come i selettori di data (se presenti), i pulsanti o altri widget UI che potrebbero far parte dell'interfaccia di gestione delle slide.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template Hook (`views/templates/hook/`)**:

    -   `proslider/header.tpl`
        -   **Hook**: Probabilmente destinato a `displayHeader` o `displayTop`.
        -   **Output**: Questo template conterrebbe la struttura HTML principale per lo slider, inclusi gli elementi `div` a cui `jquery.cslider.js` si rivolge, e potenzialmente il ciclo per renderizzare le singole slide basate sui dati passati dal modulo. Potrebbe anche includere gli include JS e CSS necessari.
    -   `proslider/top.tpl`
        -   **Hook**: Probabilmente destinato a `displayTop` o `displayNav`.
        -   **Output**: Simile a `header.tpl`, questo renderizzerebbe lo slider nella sezione superiore del negozio, spesso sotto la navigazione principale.
    -   `proslider/views/templates/hook/left-column.tpl`
        -   **Hook**: `displayLeftColumn` o `displayRightColumn`.
        -   **Output**: Questo template renderizza una versione potenzialmente più piccola o stilizzata diversamente dello slider specificamente per le colonne laterali del negozio.
-   **Template Admin (`views/templates/admin/`)**:

    -   `proslider/views/templates/front/form.tpl`
        -   **Hook**: Questo percorso suggerisce che si tratta di un template front-office, ma il contesto di `AdminprosliderController` implica che potrebbe essere utilizzato per il *modulo* per aggiungere/modificare slide all'interno dell'amministrazione. Questo è un pattern comune in cui un modulo potrebbe riutilizzare un template "form" sia per l'inserimento dati front-end (se applicabile) che back-end.
        -   **Output**: Questo template definirebbe la struttura del modulo HTML per aggiungere o modificare una singola slide, inclusi i campi di input per titolo, descrizione, caricamento immagine, URL, stato attivo e posizione.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il dossier del modulo indica l'assenza di file SQL personalizzati. Ciò suggerisce fortemente che il modulo memorizza la sua configurazione e i dati delle slide direttamente nella tabella `ps_configuration` di PrestaShop. I dati di ogni slide (titolo, descrizione, immagine, link, ecc.) sarebbero probabilmente serializzati in una singola chiave di configurazione, o più chiavi per slide, ad esempio `PROSLIDER_SLIDE_1_TITLE`, `PROSLIDER_SLIDE_1_IMAGE`, ecc. Questo approccio è più semplice ma meno scalabile rispetto all'utilizzo di un `ObjectModel` dedicato.
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Iniezione di risorse CSS/JS e potenzialmente della struttura HTML principale dello slider. |
| `displayTop` | Tipicamente sotto la navigazione principale, sopra il contenuto. | Visualizzazione dello slider principale in una posizione prominente in alto. |
| `displayHome` | Nell'area del contenuto della homepage. | Visualizzazione dello slider come caratteristica centrale della homepage. |
| `displayLeftColumn` | Nella barra laterale sinistra delle pagine che ne hanno una. | Visualizzazione di uno slider più piccolo e contestuale nella colonna sinistra. |
| `displayRightColumn` | Nella barra laterale destra delle pagine che ne hanno una. | Visualizzazione di uno slider più piccolo e contestuale nella colonna destra. |
| `displayProductFooter` | Nella parte inferiore delle pagine prodotto. | Visualizzazione di uno slider correlato al prodotto (es. accessori, articoli correlati). |
| `displayFooter` | Nella sezione del piè di pagina di ogni pagina. | Visualizzazione di uno slider per promozioni secondarie o contenuti del brand. |
| `actionFrontControllerSetMedia` | Prima che un controller front-end renderizzi il suo output, dopo che i media sono stati impostati. | Registrazione di file CSS e JavaScript specifici del modulo per le pagine del front-office. |
| `actionAdminControllerSetMedia` | Prima che un controller admin renderizzi il suo output, dopo che i media sono stati impostati. | Registrazione di file CSS e JavaScript specifici del modulo per le pagine del back-office (es. per il selettore colori o TinyMCE). |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a fornire assistenza e garantire il buon funzionamento del tuo modulo Presta Pro Slider.
