---
title: "HTML Box Pro - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop HTML Box Pro di MyPresta.eu."
sidebar:
  label: "HTML Box Pro - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo HTML Box Pro su MyPresta.eu](https://mypresta.eu/modules/front-office-features/html-box-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/html-box-pro/)
>
> ---


# HTML Box Pro

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste da PrestaShop stesso e sono sufficienti per questo modulo.

## 2. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura > HTML Box Pro)

Questa è la schermata principale dove gestisci tutti i tuoi HTML Box. Il modulo presenta un elenco di box esistenti e opzioni per aggiungerne di nuovi o modificare le impostazioni globali.

#### Sezione Impostazioni Globali

Nella parte superiore della pagina di configurazione, troverai alcune impostazioni globali che influenzano il funzionamento del modulo.

-   **Usa modulo interno**

    -   **Cosa fa questa impostazione:** Questa è un'impostazione legacy che tipicamente si riferisce al meccanismo di aggiornamento interno del modulo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato ("Sì"):* Il modulo potrebbe utilizzare i propri metodi interni per controllare gli aggiornamenti.
        -   *Quando disabilitato ("No"):* Il modulo si baserà sui meccanismi di aggiornamento standard di PrestaShop o sugli aggiornamenti manuali.
    -   **Valore consigliato:** "Sì" (a meno che non si riscontrino problemi, quindi provare "No").
    -   **Scenario / esempio per il commerciante:** Generalmente, lascialo su "Sì". Se riscontri problemi con gli aggiornamenti o le notifiche del modulo, il tuo webmaster potrebbe suggerire di disattivarlo.
-   **Impedisci la rimozione degli URL dalle immagini**

    -   **Cosa fa questa impostazione:** Quando utilizzi l'editor TinyMCE integrato (l'editor di testo ricco) per aggiungere immagini, a volte può rimuovere automaticamente il percorso URL completo, specialmente se copi-incolli il contenuto. Questa impostazione previene tale comportamento.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato ("Sì"):* Gli URL delle immagini che inserisci nel contenuto dell'HTML box verranno conservati esattamente come li hai inseriti, prevenendo link di immagini interrotti.
        -   *Quando disabilitato ("No"):* L'editor potrebbe modificare o rimuovere parti degli URL delle immagini, potenzialmente portando a immagini che non vengono visualizzate correttamente.
    -   **Valore consigliato:** "Sì"
    -   **Scenario / esempio per il commerciante:** Se stai aggiungendo immagini da fonti esterne (es. un CDN o un altro sito web) o anche immagini interne con percorsi assoluti, abilitando questa opzione ti assicuri che le tue immagini vengano sempre visualizzate.
-   **Non caricare le librerie tinyMCE**

    -   **Cosa fa questa impostazione:** TinyMCE è l'editor di testo ricco che ti consente di formattare facilmente il testo, aggiungere immagini e creare tabelle senza scrivere direttamente codice HTML. Questa impostazione controlla se il modulo carica la propria versione dell'editor TinyMCE.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato ("Sì"):* Il modulo NON caricherà il suo editor TinyMCE. Questo può essere utile se il tuo tema o un altro modulo carica già TinyMCE, prevenendo conflitti o caricamenti duplicati. Tuttavia, perderai l'editor visuale per i tuoi HTML box e dovrai scrivere HTML grezzo.
        -   *Quando disabilitato ("No"):* Il modulo caricherà il suo editor TinyMCE, fornendoti un'interfaccia user-friendly per creare e modificare il contenuto del tuo HTML box.
    -   **Valore consigliato:** "No" (a meno che tu non sia uno sviluppatore e preferisca scrivere HTML grezzo, o se riscontri conflitti con altre istanze di TinyMCE).
    -   **Scenario / esempio per il commerciante:** Se vuoi usare l'editor visuale per aggiungere facilmente testo, grassetto, corsivo, immagini e link senza conoscere l'HTML, mantieni questa opzione su "No". Se stai riscontrando comportamenti strani con l'editor o errori nella console, uno sviluppatore potrebbe suggerire di attivarla per la risoluzione dei problemi.

#### Sezione Gestione HTML Box

Sotto le impostazioni globali, troverai una tabella che elenca tutti i tuoi HTML box creati. Da qui, puoi aggiungere nuovi box, modificarne di esistenti o eliminarli.

-   **Aggiungi nuovo HTML Box** (Pulsante)

    -   **Cosa fa:** Cliccando questo pulsante si accede a un nuovo modulo dove è possibile definire un HTML box completamente nuovo.
    -   **Effetto:** Apre il modulo "Aggiungi nuovo HTML Box".
-   **Modifica** (Icona accanto a ogni box)

    -   **Cosa fa:** Ti consente di modificare le impostazioni e il contenuto di un HTML box esistente.
    -   **Effetto:** Apre il modulo "Modifica HTML Box", precompilato con le impostazioni attuali del box.
-   **Elimina** (Icona accanto a ogni box)

    -   **Cosa fa:** Rimuove permanentemente un HTML box dal tuo negozio.
    -   **Effetto:** L'HTML box non apparirà più nel tuo front office. Questa azione è irreversibile.
    -   **Valore consigliato:** Elimina solo i box di cui non hai più bisogno.

#### Modulo Aggiungi/Modifica HTML Box

Quando clicchi su "Aggiungi nuovo HTML Box" o "Modifica" uno esistente, vedrai un modulo con i seguenti campi:

-   **Nome**

    -   **Cosa fa questa impostazione:** Questo è un nome interno per il tuo HTML box, visibile solo nel Back Office. Ti aiuta a identificare i diversi box.
    -   **Effetto della modifica di questa impostazione:** Modifica l'etichetta per questo box nell'elenco di configurazione del tuo modulo. Nessun effetto sul front office.
    -   **Valore consigliato:** Un nome descrittivo (es. "Banner Homepage - Saldi Estivi", "Badge di Fiducia Pagina Prodotto", "Info Contatto Footer").
    -   **Scenario / esempio per il commerciante:** Nominare chiaramente i tuoi box ti aiuta a trovarli e gestirli rapidamente, specialmente man mano che il tuo negozio cresce e aggiungi più contenuti personalizzati.
-   **Negozio** (Visibile solo in ambienti multi-negozio)

    -   **Cosa fa questa impostazione:** Se gestisci più negozi da una singola installazione PrestaShop, questo ti consente di specificare su quale/i negozio/i questo HTML box dovrebbe apparire.
    -   **Effetto della modifica di questa impostazione:** L'HTML box verrà visualizzato solo sui negozi selezionati.
    -   **Valore consigliato:** Seleziona i negozi specifici dove il contenuto è rilevante.
    -   **Scenario / esempio per il commerciante:** Potresti avere un banner promozionale diverso per il tuo negozio francese rispetto a quello tedesco.
-   **Posizione**

    -   **Cosa fa questa impostazione:** Questa è l'impostazione più cruciale, che determina *dove* nel tuo negozio apparirà l'HTML box. È un elenco a discesa di tutti gli hook PrestaShop disponibili.
    -   **Effetto della modifica di questa impostazione:** Il contenuto del tuo HTML box verrà renderizzato nella posizione dell'hook selezionato.
    -   **Valore consigliato:** Scegli l'hook che meglio si adatta allo scopo del contenuto (es. `displayHeader` per un banner superiore, `displayLeftColumn` per un blocco laterale).
    -   **Scenario / esempio per il commerciante:** Se vuoi aggiungere un messaggio "Spedizione Gratuita" sopra le descrizioni dei tuoi prodotti, selezioneresti `displayProductAdditionalInfo`.
-   **Attivo**

    -   **Cosa fa questa impostazione:** Controlla se l'HTML box è attualmente visibile nel tuo negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato ("Sì"):* L'HTML box verrà visualizzato nel tuo front office.
        -   *Quando disabilitato ("No"):* L'HTML box verrà nascosto, ma il suo contenuto e le impostazioni vengono salvati, permettendoti di riattivarlo in seguito.
    -   **Valore consigliato:** "Sì" per contenuti attivi, "No" per contenuti che vuoi nascondere temporaneamente o preparare per un uso futuro.
    -   **Scenario / esempio per il commerciante:** Puoi preparare un box promozionale natalizio in anticipo, mantenerlo "No", e poi attivarlo quando arriva il momento, senza doverlo ricreare.
-   **Solo su pagine sicure (SSL)**

    -   **Cosa fa questa impostazione:** Limita la visualizzazione dell'HTML box alle pagine caricate tramite HTTPS (connessione sicura).
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato ("Sì"):* Il box apparirà solo su pagine con `https://` nell'URL.
        -   *Quando disabilitato ("No"):* Il box apparirà sia su pagine sicure (HTTPS) che non sicure (HTTP) (se il tuo negozio utilizza ancora HTTP, cosa non raccomandata).
    -   **Valore consigliato:** "Sì" se il contenuto contiene informazioni sensibili o se vuoi assicurarti che si carichi solo su pagine sicure. Generalmente, tutti i negozi moderni dovrebbero essere completamente HTTPS, quindi questo potrebbe non essere strettamente necessario, ma aggiunge un ulteriore livello di controllo.
    -   **Scenario / esempio per il commerciante:** Se il tuo HTML box contiene un badge di pagamento o un sigillo di sicurezza, potresti voler assicurarti che appaia solo su pagine sicure per rafforzare la fiducia.
-   **Solo sulla homepage**

    -   **Cosa fa questa impostazione:** Limita la visualizzazione dell'HTML box solo alla homepage del tuo negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato ("Sì"):* Il box apparirà solo quando i clienti visitano la tua homepage principale.
        -   *Quando disabilitato ("No"):* Il box apparirà su tutte le pagine dove la sua "Posizione" (hook) selezionata è disponibile.
    -   **Valore consigliato:** "No" a meno che il contenuto non sia specificamente progettato per la homepage.
    -   **Scenario / esempio per il commerciante:** Un grande banner promozionale per una vendita a livello di sito sarebbe tipicamente impostato su "Sì" per questa opzione se lo si desidera solo sulla homepage, o "No" se lo si desidera nell'intestazione su ogni pagina.
-   **Contenuti** (Questo è l'editor di contenuto principale)

    -   **Cosa fa questa impostazione:** Qui inserisci il codice HTML, JavaScript o CSS effettivo che verrà visualizzato. Utilizza l'editor di testo ricco TinyMCE (se non disabilitato globalmente) per una facile creazione di contenuti.
    -   **Effetto della modifica di questa impostazione:** Il contenuto che inserisci qui verrà renderizzato nel tuo front office nell'hook selezionato.
    -   **Valore consigliato:** Inserisci il contenuto desiderato. Puoi usare:
        -   Testo semplice
        -   HTML (es. `<p>Ciao Mondo!</p>`, tag `<img>`, link `<a>`)
        -   CSS (racchiuso in tag `<style>`, es. `<style>.my-class { color: red; }</style>`)
        -   JavaScript (racchiuso in tag `<script>`, es. `<script>alert('Benvenuto!');</script>`)
    -   **Scenario / esempio per il commerciante:**
        -   *HTML:* Aggiungere un'immagine banner personalizzata: `<img src="https://iltuonegozio.com/img/cms/banner.jpg" alt="Saldi Estivi" style="width:100%;">`
        -   *JavaScript:* Incorporare un codice di tracciamento di Google Analytics: `<script> (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){ (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o), m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m) })(window,document,'script','//www.google-analytics.com/analytics.js','ga'); ga('create', 'UA-XXXXX-Y', 'auto'); ga('send', 'pageview'); </script>`
        -   *CSS:* Cambiare il colore di un elemento specifico: `<style> #header .logo { border: 2px solid blue; } </style>`

#### 2.1.1 Tabella di Riferimento Rapido alla Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Pagina Config. Principale | Usa modulo interno | Sì | Controlla il meccanismo di aggiornamento interno. |
| Pagina Config. Principale | Impedisci la rimozione degli URL dalle immagini | Sì | Assicura che gli URL delle immagini siano preservati nell'editor. |
| Pagina Config. Principale | Non caricare le librerie tinyMCE | No | Abilita l'editor visuale per una facile creazione di contenuti. |
| Modulo Aggiungi/Modifica | Nome | Nome Descrittivo | Etichetta interna per l'HTML box. |
| Modulo Aggiungi/Modifica | Negozio | Tutti i Negozi | Seleziona quali negozi visualizzano il contenuto (multi-negozio). |
| Modulo Aggiungi/Modifica | Posizione | (Scegli Hook) | Determina dove il contenuto appare nel front office. |
| Modulo Aggiungi/Modifica | Attivo | Sì | Attiva/disattiva la visibilità dell'HTML box nel front office. |
| Modulo Aggiungi/Modifica | Solo su pagine sicure (SSL) | No (o Sì se critico) | Limita la visualizzazione alle pagine HTTPS. |
| Modulo Aggiungi/Modifica | Solo sulla homepage | No | Limita la visualizzazione solo alla homepage. |
| Modulo Aggiungi/Modifica | Contenuti | (Il tuo HTML/JS/CSS) | Il contenuto effettivo da visualizzare. |

## 3. Risoluzione dei Problemi per il Commerciante e Domande Frequenti (FAQ)

**D1: Il mio HTML box non viene visualizzato nel front office. Cosa devo controllare?**
R1:

-   **È Attivo?** Vai alla configurazione del modulo e assicurati che l'interruttore "Attivo" per il tuo box sia impostato su "Sì".
-   **Posizione (Hook) Corretta?** Ricontrolla di aver selezionato la "Posizione" (hook) corretta dove ti aspetti che il contenuto appaia. Alcuni hook sono specifici per determinate pagine (es. `displayProductAdditionalInfo` solo sulle pagine prodotto).
-   **Solo Homepage?** Se hai impostato "Solo sulla homepage" su "Sì", apparirà solo sulla tua homepage principale.
-   **Solo SSL?** Se "Solo su pagine sicure (SSL)" è "Sì", assicurati di visualizzare una pagina HTTPS.
-   **Cache:** Svuota la cache di PrestaShop (Parametri Avanzati > Prestazioni > Svuota cache) e la cache del tuo browser.
-   **Errori di Contenuto:** Se il tuo contenuto HTML/JS/CSS presenta errori, potrebbe impedire il rendering del box. Prova un semplice testo "Ciao Mondo" per testare.

**D2: L'editor TinyMCE (editor visuale) non funziona o ha un aspetto strano.**
R2:

-   **Impostazione "Non caricare le librerie tinyMCE":** Assicurati che sia impostata su "No" nelle impostazioni globali del modulo se vuoi usare l'editor visuale.
-   **Conflitti con il Tema:** A volte, temi personalizzati o altri moduli possono interferire con TinyMCE. Prova a disabilitare temporaneamente altri moduli per vedere se il problema si risolve.
-   **Problemi del Browser:** Prova un browser diverso o svuota la cache e i cookie del tuo browser.

**D3: Le mie immagini o i miei link sono rotti dopo aver salvato il contenuto dell'HTML box.**
R3:

-   **Impostazione "Impedisci la rimozione degli URL dalle immagini":** Assicurati che sia impostata su "Sì" nelle impostazioni globali del modulo.
-   **Percorsi Assoluti vs. Relativi:** Usa sempre URL assoluti (che iniziano con `http://` o `https://`) per immagini e link, specialmente se sono esterni o se vuoi che funzionino in modo coerente su tutto il tuo sito.
-   **Controlla l'HTML:** Ispeziona il codice HTML generato nell'editor (di solito un pulsante "Codice sorgente") per assicurarti che i tuoi attributi `src` e `href` siano corretti.

**D4: Come traduco il contenuto dei miei HTML box per diverse lingue?**
R4:

-   HTML Box Pro supporta contenuti multilingue. Quando modifichi un HTML box, vedrai delle schede linguistiche (es. Inglese, Francese, Spagnolo) accanto al campo "Contenuti".
-   Clicca su ogni scheda linguistica e inserisci il contenuto tradotto per quella lingua specifica. Il modulo visualizzerà automaticamente la versione linguistica corretta ai tuoi clienti in base alla lingua del negozio selezionata.

**D5: Il contenuto appare bene su desktop ma è distorto su mobile.**
R5:

-   **Design Responsive:** Assicurati che il contenuto HTML che stai aggiungendo sia progettato per essere responsive. Utilizza proprietà CSS come `max-width: 100%; height: auto;` per le immagini e considera l'uso di media query CSS all'interno dei tuoi tag `<style>` per layout più complessi.
-   **Responsiveness del Tema:** Sebbene il modulo stesso sia responsive, se il tuo HTML personalizzato non lo è, potrebbe rompere il layout. Testa accuratamente su diversi dispositivi.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

### 4.1 Panoramica dell'Architettura

Il modulo HTML Box Pro segue un'architettura standard per i moduli PrestaShop, sfruttando principalmente la classe `Module` per la sua funzionalità principale e `getContent()` per la configurazione del Back Office. Registra dinamicamente gli hook e renderizza il contenuto in base alla configurazione memorizzata. Il modulo utilizza una libreria `SmartyTemplatesManager` personalizzata per la gestione dei suoi moduli e template del Back Office, fornendo un'interfaccia utente coerente per l'aggiunta e la modifica degli HTML box. Il contenuto è memorizzato nella tabella `ps_configuration`, con ogni HTML box rappresentato da una chiave di configurazione unica.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller dedicati per il front-office o il back-office nelle directory `controllers/front` o `controllers/admin`. Tutta la logica del Back Office è gestita all'interno del metodo `getContent()` del file `htmlboxpro.php`, che renderizza i moduli e elabora le sottomissioni. Il rendering del contenuto del front-office è gestito direttamente tramite l'esecuzione degli hook all'interno del file principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

Il modulo non definisce classi `ObjectModel` personalizzate o altre classi core in una directory `classes/`. Tutta la gestione dei dati e la logica di business sono incapsulate all'interno del file principale del modulo `htmlboxpro.php`. Le configurazioni degli HTML box sono memorizzate direttamente nella tabella `ps_configuration`, con chiavi come `hbp_name_X`, `hbp_content_X_Y`, `hbp_hook_X`, ecc., dove `X` è l'ID del box e `Y` è l'ID della lingua.

### 4.4 Risorse JavaScript (`views/js/`)

-   `htmlboxpro/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`
    -   **Ambito:** Back-office.
    -   **Responsabilità:** Fornisce funzionalità JavaScript per la libreria `SmartyTemplatesManager`, che viene utilizzata per renderizzare e gestire i moduli di configurazione del modulo (es. aggiunta/modifica di HTML box). Questo include elementi di modulo dinamici, interazioni AJAX per il salvataggio/caricamento dei dati del template e potenzialmente la gestione delle schede.
-   `htmlboxpro/views/js/script.js`
    -   **Ambito:** Back-office.
    -   **Responsabilità:** Contiene JavaScript specifico del modulo per la pagina di configurazione del Back Office. Questo potrebbe includere listener di eventi per le sottomissioni dei moduli, aggiornamenti dinamici all'elenco degli HTML box o altri miglioramenti dell'interfaccia utente specifici per HTML Box Pro.
-   `htmlboxpro/views/js/tinymce16-force-urls.inc.js`
    -   **Ambito:** Back-office.
    -   **Responsabilità:** Questo script viene caricato quando l'opzione "Impedisci la rimozione degli URL dalle immagini" è abilitata. Contiene la configurazione e i plugin di TinyMCE specificamente progettati per impedire all'editor di rimuovere o modificare URL assoluti, in particolare per le immagini. Assicura che gli attributi `src` rimangano intatti.
-   `htmlboxpro/views/js/tinymce16.inc.js`
    -   **Ambito:** Back-office.
    -   **Responsabilità:** Questo script contiene l'inizializzazione e la configurazione core dell'editor TinyMCE per il modulo. Definisce la barra degli strumenti, i plugin e il comportamento generale dell'editor durante la modifica del contenuto dell'HTML box. Viene caricato quando l'opzione "Non caricare le librerie tinyMCE" è disabilitata.

### 4.5 Fogli di Stile CSS (`views/css/`)

-   `htmlboxpro/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`
    -   **Ambito:** Styling del modulo di amministrazione del Back-office.
    -   **Responsabilità:** Fornisce lo styling per i componenti dell'interfaccia utente della libreria `SmartyTemplatesManager`, garantendo un aspetto coerente per i moduli di configurazione del modulo all'interno del Back Office di PrestaShop.
-   `htmlboxpro/views/css/styles.css`
    -   **Ambito:** Styling del modulo di amministrazione del Back-office.
    -   **Responsabilità:** Contiene regole CSS specifiche del modulo per la pagina di configurazione di HTML Box Pro, come lo styling per l'elenco degli HTML box, i pulsanti o altri elementi personalizzati all'interno dell'interfaccia di amministrazione del modulo.

### 4.6 Struttura dei Template Smarty (`views/templates/`)

Il modulo utilizza ampiamente i template Smarty per la sua interfaccia Back Office.

-   **Template degli hook (`htmlboxpro/`)**:
    -   `htmlboxpro/html.tpl`: Questo è il template principale del front-office. È responsabile del rendering del contenuto effettivo dell'HTML box (`{$htmlboxpro_content}`) all'interno dell'hook selezionato nel front office.
-   **Template di amministrazione (`views/templates/admin/`)**:
    -   `htmlboxpro/views/templates/admin/_configure/helpers/form/form.tpl`: Questo template è probabilmente un override o un template specifico utilizzato dal modulo di configurazione del modulo, che potrebbe personalizzare il modo in cui `HelperForm` standard di PrestaShop renderizza i suoi campi, specialmente per l'editor TinyMCE.
-   **Template di amministrazione (`views/templates/`)**:
    -   `htmlboxpro/views/custom_hook_info.tpl`: Probabilmente visualizza informazioni o istruzioni relative agli hook personalizzati.
    -   `htmlboxpro/views/form-add-new.tpl`: Template per il modulo "Aggiungi nuovo HTML Box".
    -   `htmlboxpro/views/form-edit.tpl`: Template per il modulo "Modifica HTML Box".
    -   `htmlboxpro/views/messages.tpl`: Utilizzato per visualizzare messaggi di successo, errore o informativi nel Back Office.
    -   `htmlboxpro/views/scripts.tpl`: Probabilmente include risorse JavaScript e CSS per la pagina di configurazione del Back Office.
-   **Template della Libreria SmartyTemplatesManager (`htmlboxpro/lib/smartyTemplatesManager/tpl/`, `htmlboxpro/lib/smartyTemplatesManager/views/`)**:
    -   `htmlboxpro/lib/smartyTemplatesManager/tpl/example.tpl`: Un template di esempio, probabilmente per scopi di sviluppo o dimostrativi all'interno della libreria.
    -   `htmlboxpro/lib/smartyTemplatesManager/views/buttonManager.tpl`: Renderizza pulsanti o link di azione all'interno dell'interfaccia `SmartyTemplatesManager`.
    -   `htmlboxpro/lib/smartyTemplatesManager/views/createTemplateForm.tpl`: Utilizzato per creare nuovi template/elementi nel contesto di `SmartyTemplatesManager`.
    -   `htmlboxpro/lib/smartyTemplatesManager/views/editTemplateForm.tpl`: Utilizzato per modificare template/elementi esistenti nel contesto di `SmartyTemplatesManager`.
    -   `htmlboxpro/lib/smartyTemplatesManager/views/mainForm.tpl`: Il wrapper o la struttura principale per i moduli gestiti da `SmartyTemplatesManager`.
    -   `htmlboxpro/lib/smartyTemplatesManager/views/selectInput.tpl`: Un template generico per il rendering di un input a discesa di selezione.
    -   `htmlboxpro/lib/searchTool/views/scripts.tpl`: Probabilmente include risorse JavaScript e CSS per un componente di ricerca all'interno del Back Office.

### 4.7 Schema del Database e Mappa degli Hook

-   **Tabelle del Database**:

    -   Il modulo non crea tabelle SQL personalizzate. Tutta la configurazione per gli HTML box è memorizzata nella tabella standard di PrestaShop `ps_configuration`.
    -   Le chiavi di configurazione seguono un modello come:
        -   `HBP_NAME_{ID}`: Nome dell'HTML box.
        -   `HBP_CONTENT_{ID}_{LANG_ID}`: Il contenuto HTML/JS/CSS effettivo per un box e una lingua specifici.
        -   `HBP_HOOK_{ID}`: Il nome dell'hook in cui viene visualizzato il box.
        -   `HBP_ACTIVE_{ID}`: Booleano (0/1) che indica se il box è attivo.
        -   `HBP_SSL_{ID}`: Booleano (0/1) che indica se è solo su pagine SSL.
        -   `HBP_HOMEPAGE_{ID}`: Booleano (0/1) che indica se è solo sulla homepage.
        -   `HBP_SHOP_{ID}`: Elenco di ID negozio separati da virgole (per multi-negozio).
        -   `HBP_LAST_ID`: Memorizza l'ultimo ID utilizzato per un HTML box per generare ID unici.
        -   `HBP_NOTINYJS`: Impostazione globale per "Non caricare le librerie tinyMCE".
        -   `HBP_FORCEURLS`: Impostazione globale per "Impedisci la rimozione degli URL dalle immagini".
        -   Altre chiavi come `MYPRESTA_UPDATES`, `UPDATE_HTMLBOXPRO`, `UPDATEV_HTMLBOXPRO` per la gestione degli aggiornamenti.
-   **Tabella degli Hook Registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayAfterCarrier` | Dopo la selezione del corriere nel checkout. | Visualizza contenuti relativi alle opzioni di spedizione o ai passaggi finali. |
| `displayFooterBefore` | Prima del contenuto principale del piè di pagina. | Aggiunge contenuto sopra il piè di pagina standard. |
| `displayLeftColumn` | Nella barra laterale sinistra delle pagine applicabili. | Visualizza blocchi della barra laterale (es. categorie, filtri, informazioni personalizzate). |
| `displayCustomerAccountForm` | All'interno del modulo di creazione/modifica dell'account cliente. | Aggiunge campi personalizzati o informazioni relative agli account cliente. |
| `displayRightColumnProduct` | Nella barra laterale destra delle pagine prodotto. | Visualizza contenuti della barra laterale specifici del prodotto (es. prodotti correlati, badge di fiducia). |
| `displayBanner` | Nella parte superiore della pagina, tipicamente per un banner a livello di sito. | Visualizza banner promozionali o annunci. |
| `actionAdminControllerSetMedia` | Quando un controller di amministrazione imposta i suoi media (CSS/JS). | Inietta CSS/JS personalizzato nel Back Office (utilizzato dal modulo per le proprie risorse di amministrazione). |
| `displayOrderConfirmation` | Nella pagina di conferma dell'ordine dopo un acquisto riuscito. | Visualizza messaggi di ringraziamento, informazioni di tracciamento o upsell. |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Ideale per iniettare meta tag, script di tracciamento o CSS/JS globali. |
| `displayCartExtraProductActions` | All'interno del riepilogo del carrello, vicino alle azioni del prodotto. | Aggiunge contenuto relativo agli articoli del carrello (es. upsell, cross-sell, informazioni sulla spedizione). |
| `displayFooter` | Nella sezione principale del piè di pagina del negozio. | Aggiunge contenuto generale del piè di pagina, link o informazioni sul copyright. |
| `displayPaymentByBinaries` | Durante il processo di selezione del pagamento. | Visualizza informazioni relative al pagamento o sigilli di fiducia. |
| `displayCustomerLoginFormAfter` | Dopo il modulo di accesso del cliente. | Aggiunge contenuto sotto il modulo di accesso (es. link "password dimenticata", inviti alla registrazione). |
| `displayReassurance` | All'interno del blocco di rassicurazione del prodotto (spesso sotto l'immagine del prodotto). | Visualizza elementi di fiducia come spedizione gratuita, pagamento sicuro, resi facili. |
| `displayProductAdditionalInfo` | Sotto la descrizione del prodotto o il blocco di informazioni principali. | Aggiunge dettagli extra del prodotto, guide alle taglie o contenuti personalizzati. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, accedi al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è pronto ad assisterti con qualsiasi problema o domanda riguardante il modulo HTML Box Pro.
