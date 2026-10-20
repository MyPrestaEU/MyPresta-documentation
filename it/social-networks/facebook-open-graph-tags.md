---
title: "Facebook Open Graph Tags - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Facebook Open Graph Tags di MyPresta.eu."
sidebar:
  label: "Facebook Open Graph Tags - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Facebook Open Graph Tags su MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-open-graph-tags.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/facebook-open-graph-tags/)
>
> ---


# Facebook Open Graph Tags

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.3.x, 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti e di solito sono abilitate per impostazione predefinita nella maggior parte degli ambienti di hosting.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Facebook Open Graph Tags)

Questa è la schermata di configurazione principale dove controlli il comportamento centrale del modulo.

| Impostazione / Opzione | Cosa fa questa impostazione | Effetto della modifica di questa impostazione | Valore consigliato | Scenario / esempio per il commerciante |
| --- | --- | --- | --- | --- |
| **Abilita Open Graph Tags** | Questo interruttore principale controlla se il modulo genera o meno tag Open Graph. | *Quando abilitato:* Il modulo inietterà i tag Open Graph necessari nella sezione `<head>` HTML del tuo negozio, consentendo a Facebook di visualizzare anteprime ricche. *Quando disabilitato:* Nessun tag Open Graph verrà generato da questo modulo, e Facebook cercherà di indovinare il contenuto, spesso risultando in anteprime scadenti o mancanti. | **SÌ** | Vuoi che le condivisioni dei tuoi prodotti abbiano un aspetto professionale su Facebook. |
| **ID App Facebook** | Il tuo identificatore univoco per la tua applicazione Facebook. Questo collega le condivisioni del tuo sito web alla tua App Facebook, consentendo approfondimenti e analisi. | *Quando fornito:* Facebook può attribuire le condivisioni alla tua app, fornendoti analisi su come i tuoi contenuti si comportano sulla loro piattaforma. *Quando lasciato vuoto:* Le condivisioni funzioneranno comunque, ma non otterrai approfondimenti dettagliati tramite gli strumenti per sviluppatori di Facebook. | **Il tuo ID App Facebook** (se ne hai uno) | Vuoi monitorare le prestazioni dei tuoi contenuti condivisi su Facebook utilizzando Facebook Insights. Se non ne hai uno, puoi lasciarlo vuoto. |
| **ID Amministratore Facebook** | L'ID Utente Facebook dell'amministratore(i) della tua Pagina o App Facebook. Questo aiuta Facebook a capire chi gestisce il contenuto. | *Quando fornito:* Facebook sa chi è l'autore/amministratore del contenuto, il che può essere utile per la moderazione o per specifiche funzionalità di Facebook. *Quando lasciato vuoto:* Nessun amministratore specifico sarà collegato. | **Il tuo ID Utente Facebook** (se applicabile) | Vuoi collegare il tuo profilo Facebook personale come amministratore per il contenuto condiviso. |
| **Immagine predefinita per la Homepage** | Questa impostazione ti consente di specificare un'immagine di fallback che Facebook utilizzerà quando la tua homepage viene condivisa, specialmente se la tua homepage non ha un'immagine prominente. | *Quando un'immagine viene caricata:* Questa immagine verrà utilizzata come `og:image` quando la homepage del tuo negozio viene condivisa su Facebook. *Quando lasciato vuoto:* Facebook cercherà di trovare un'immagine sulla tua homepage, che potrebbe non essere sempre l'ideale (es. un piccolo logo o banner). | **Carica il logo principale del tuo negozio o un'immagine banner accattivante.** | La tua homepage è principalmente testuale e desideri che un'immagine specifica e attraente appaia quando qualcuno condivide l'URL principale del tuo negozio. |
| **Titolo predefinito per la Homepage** | Il titolo che Facebook visualizzerà quando la homepage del tuo negozio viene condivisa. | *Quando fornito:* Questo titolo verrà utilizzato come `og:title` per le condivisioni della tua homepage. *Quando lasciato vuoto:* Facebook probabilmente utilizzerà il meta titolo predefinito del tuo negozio, che potrebbe non essere ottimizzato per la condivisione sociale. | **Nome del tuo negozio - Slogan** (es. "Il Mio Negozio Fantastico - Scopri Prodotti Unici!") | Vuoi che un titolo accattivante e brandizzato appaia quando l'URL principale del tuo negozio viene condiviso. |
| **Descrizione predefinita per la Homepage** | La descrizione che Facebook visualizzerà quando la homepage del tuo negozio viene condivisa. | *Quando fornito:* Questa descrizione verrà utilizzata come `og:description` per le condivisioni della tua homepage. *Quando lasciato vuoto:* Facebook probabilmente utilizzerà la meta descrizione predefinita del tuo negozio, che potrebbe non essere ottimizzata per la condivisione sociale. | **Un riassunto conciso e coinvolgente del tuo negozio.** (es. "Acquista le ultime tendenze in moda ed elettronica. Spedizione veloce in tutto il mondo!") | Vuoi controllare il messaggio che appare quando la homepage del tuo negozio viene condivisa, invogliando gli utenti a cliccare. |

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### 2.2.1 AdminOpenGraphController (Back Office > Parametri Avanzati > Open Graph Tags)

Questa schermata ti consente di gestire tag Open Graph specifici per singole pagine o di sovrascrivere il comportamento predefinito. Mentre il modulo genera automaticamente i tag per prodotti e categorie, questa sezione è utile per pagine personalizzate o per una messa a punto.

- **Nome schermata e posizione menu:** Puoi accedere a questa schermata navigando su **Parametri Avanzati > Open Graph Tags** nel tuo Back Office di PrestaShop.
- **Azioni e impostazioni disponibili:** Questa schermata presenta tipicamente una griglia (elenco) di configurazioni di tag Open Graph personalizzate che hai aggiunto. Troverai opzioni per:
  - **Aggiungi nuovo:** Crea un nuovo set di tag Open Graph personalizzato per un URL specifico.
  - **Modifica:** Modifica un set di tag personalizzato esistente.
  - **Elimina:** Rimuovi un set di tag personalizzato.
  - **Colonne della griglia:** Di solito visualizza l'URL, il titolo, la descrizione e l'immagine associati al tag personalizzato.
- **Effetto delle modifiche:**
  - **Aggiunta di una nuova voce:** Quando aggiungi una nuova voce per un URL specifico (ad esempio, una pagina CMS personalizzata o l'URL di un post del blog), il modulo utilizzerà il titolo, la descrizione e l'immagine che fornisci qui invece di provare a generarli automaticamente quando quell'URL specifico viene condiviso su Facebook.
  - **Modifica di una voce:** Aggiorna l'anteprima sociale per quell'URL specifico.
  - **Eliminazione di una voce:** Ripristina il comportamento per quell'URL alla generazione automatica del modulo o alle impostazioni predefinite della homepage.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1. **Identifica le pagine che necessitano di anteprime personalizzate:** Per la maggior parte dei prodotti e delle categorie, il modulo funziona automaticamente. Tuttavia, per le pagine CMS personalizzate (ad esempio, "Chi siamo", "Contattaci", post del blog se hai un blog integrato), potresti volere anteprime specifiche e coinvolgenti.
  2. **Clicca su "Aggiungi nuovo"** per creare una nuova voce.
  3. **Inserisci l'URL esatto** della pagina che desideri personalizzare.
  4. **Fornisci un Titolo, una Descrizione accattivanti e carica un'Immagine pertinente** per quella pagina specifica.
  5. **Salva** le modifiche.
  6. **Testa:** Utilizza il [Sharing Debugger](https://developers.facebook.com/tools/debug/) di Facebook per verificare l'aspetto della tua pagina dopo aver apportato modifiche.

#### 2.2.2 index.php (opengraph/controllers/admin/index.php)

Questo file è un punto di ingresso standard del controller di PrestaShop e non rappresenta una schermata distinta e configurabile per i commercianti. Viene tipicamente utilizzato per il routing o l'amministrazione di base del modulo, non per la gestione di contenuti o impostazioni specifiche. Tutte le configurazioni rivolte al commerciante sono gestite tramite la pagina di configurazione principale del modulo o `AdminOpenGraphController`.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Configurazione Modulo** | Abilita Open Graph Tags | SÌ | Interruttore principale per la funzionalità del modulo. |
|  | ID App Facebook | (Il tuo ID App) / Vuoto | Collega le condivisioni alla tua App Facebook per l'analisi. |
|  | ID Amministratore Facebook | (Il tuo ID Utente) / Vuoto | Identifica l'amministratore del contenuto su Facebook. |
|  | Immagine predefinita per la Homepage | Carica il tuo logo | Immagine di fallback per le condivisioni della homepage. |
|  | Titolo predefinito per la Homepage | Nome del tuo negozio | Titolo per le condivisioni della homepage. |
|  | Descrizione predefinita per la Homepage | Slogan del negozio | Descrizione per le condivisioni della homepage. |
| **Parametri Avanzati > Open Graph Tags** | Aggiungi/Modifica/Elimina Tag Personalizzati | N/A | Sovrascrivi i tag generati automaticamente per URL specifici con titoli, descrizioni e immagini personalizzati. |

## 3. Risoluzione dei problemi per i commercianti e domande frequenti (FAQ)

**D: Le mie condivisioni su Facebook hanno ancora un aspetto scadente, anche dopo aver installato il modulo. Cosa c'è che non va?**
R:

1.  **Verifica l'attivazione del modulo:** Assicurati che "Abilita Open Graph Tags" sia impostato su SÌ nella configurazione del modulo.
2.  **Svuota la cache di PrestaShop:** Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti). Questo è fondamentale affinché le modifiche abbiano effetto.
3.  **Usa il Facebook Sharing Debugger:** Questo è il tuo migliore amico! Vai su [developers.facebook.com/tools/debug/](https://developers.facebook.com/tools/debug/), incolla l'URL che stai cercando di condividere e clicca su "Debug". Ti mostrerà esattamente quali tag Facebook sta vedendo e se ci sono errori. Potrebbe essere necessario cliccare su "Scrape Again" per forzare Facebook a rileggere la tua pagina dopo aver apportato modifiche.
4.  **Verifica la presenza di conflitti:** Un altro modulo o il tuo tema potrebbero aggiungere tag Open Graph in conflitto. Il debugger spesso evidenzierà i tag duplicati.

**D: L'immagine per le mie condivisioni di prodotti è sbagliata o mancante.**
R:

1.  **Immagine del prodotto:** Assicurati che il tuo prodotto abbia un'immagine principale assegnata nelle sue impostazioni.
2.  **Dimensione dell'immagine:** Sebbene Facebook possa ridimensionare, immagini molto piccole o con un rapporto d'aspetto insolito potrebbero essere ignorate. Punta ad almeno 600x315 pixel, idealmente 1200x628 per una visualizzazione ottimale.
3.  **Cache:** Svuota la cache di PrestaShop e usa il Facebook Sharing Debugger per "Scrape Again".

**D: Come ottengo un ID App Facebook o un ID Amministratore?**
R:

1.  **ID App Facebook:** Vai su [developers.facebook.com](https://developers.facebook.com/), accedi e crea una nuova App. Segui i passaggi per ottenere il tuo ID App. È una stringa numerica.
2.  **ID Amministratore Facebook:** Questo è il tuo ID Utente Facebook personale. Puoi trovarlo andando sul tuo profilo Facebook, cliccando sulla tua immagine del profilo e guardando l'URL nel tuo browser (es. `facebook.com/profile.php?id=IL_TUO_USER_ID`).

**D: Questo modulo funziona con temi personalizzati?**
R: Sì, il modulo inietta i tag direttamente nella sezione `<head>` del tuo HTML, che è una pratica standard e dovrebbe funzionare con qualsiasi tema PrestaShop ben codificato. Se riscontri problemi, di solito si tratta di un problema di cache o di un conflitto con un altro modulo.

**D: La mia pagina personalizzata (ad esempio, un post del blog) non mostra l'anteprima corretta.**
R: Utilizza la sezione **Parametri Avanzati > Open Graph Tags** nel Back Office. Aggiungi una nuova voce per l'URL esatto della tua pagina personalizzata e specifica manualmente il titolo, la descrizione e l'immagine desiderati. Ricorda di svuotare la cache e di utilizzare il Facebook Sharing Debugger in seguito.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Facebook Open Graph Tags" è progettato per integrarsi perfettamente con la funzionalità principale di PrestaShop, principalmente sfruttando gli hook per iniettare i meta tag Open Graph nella sezione `<head>` HTML di varie pagine del front-office. Segue una struttura standard del modulo PrestaShop, utilizzando una classe modulo principale, un controller amministrativo per la gestione dei tag personalizzati e i template Smarty per il rendering. Il modulo non introduce schemi di database complessi o modelli di oggetti personalizzati per la sua funzione primaria, ma utilizza `Configuration` per le sue impostazioni principali e potenzialmente una tabella personalizzata per `og_tags` gestita da `AdminOpenGraphController`.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Questo modulo non contiene controller front-office dedicati. Tutta la logica front-office per la generazione dei tag è gestita direttamente all'interno della classe modulo principale (`index.php`) tramite listener di hook.
-   **Controller Admin Back-Office**:

    -   `opengraph/controllers/admin/AdminOpenGraphController.php`
        -   **Nome classe e classe genitore**: `AdminOpenGraphController` estende `ModuleAdminController`.
        -   **Nome tab e entità gestita**: Questo controller gestisce un'entità personalizzata, probabilmente `og_tags`, che memorizza le configurazioni Open Graph personalizzate per URL specifici. Crea una nuova voce di menu sotto "Parametri Avanzati" (o simile) nel Back Office.
        -   **Responsabilità**: Fornisce un'interfaccia CRUD (Create, Read, Update, Delete) standard di PrestaShop per la gestione dei set di tag Open Graph personalizzati. Gestisce la visualizzazione di un elenco di tag personalizzati (utilizzando `renderList()`) e il modulo per aggiungerli/modificarli (utilizzando `renderForm()`). Elabora le sottomissioni del modulo e interagisce con il database per archiviare e recuperare i dati `og_tags`.
    -   `opengraph/controllers/admin/index.php`
        -   **Nome classe e classe genitore**: Questo è tipicamente un file `index.php` vuoto all'interno di una directory di controller, che funge da misura di sicurezza per prevenire l'elenco diretto delle directory. Non contiene alcuna classe o logica funzionale.

### 4.3 Classi e modelli principali (`classes/`)

Il dossier del modulo non indica classi personalizzate nella directory `classes/`. La logica principale per la generazione dei tag Open Graph è probabilmente contenuta nel file principale del modulo (`opengraph/index.php`), e `AdminOpenGraphController` gestirebbe le interazioni con una tabella di database personalizzata direttamente o tramite un semplice `ObjectModel` se ne fosse definito uno internamente.

Se una tabella personalizzata `og_tags` è gestita da `AdminOpenGraphController`, è altamente probabile che `AdminOpenGraphController` stesso definisca le proprietà `$this->table` e `$this->className`, e potenzialmente una semplice definizione di `ObjectModel` per `og_tags` sia dichiarata all'interno del file principale del modulo o del controller stesso, anche se non in un file `classes/` separato.

### 4.4 Risorse JavaScript (`views/js/`)

Il dossier del modulo non indica file JavaScript personalizzati. Qualsiasi comportamento dinamico o interazione AJAX sarebbe gestito dal JS principale di PrestaShop o non è presente in questo modulo.

### 4.5 Fogli di stile CSS (`views/css/`)

Il dossier del modulo non indica file CSS personalizzati. Il modulo si basa sullo stile predefinito del Back Office di PrestaShop per i suoi moduli di configurazione e qualsiasi output del front-office è puramente meta tag, non elementi visivi.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**:

    -   `opengraph/views/templates/front/hook/header.tpl`:
        -   **Hook**: Probabilmente `displayHeader` o `actionFrontControllerSetMedia`.
        -   **Scopo**: Questo è il template principale responsabile del rendering dei tag `<meta>` Open Graph effettivi all'interno della sezione `<head>` delle pagine del front-office. Riceve variabili (es. `og_title`, `og_description`, `og_image`, `og_url`, `og_type`, `og_app_id`, `og_admin_id`) dal metodo `hookDisplayHeader` (o simile) del modulo e produce i corrispondenti meta tag HTML.
    -   `opengraph/views/templates/hook/form.tpl`:
        -   **Hook**: Questo template è probabilmente utilizzato internamente da `AdminOpenGraphController` per il rendering dei campi del modulo quando si aggiunge o si modifica una voce di tag Open Graph personalizzata. Non è un template hook del front-office.
        -   **Scopo**: Definisce la struttura e i campi di input per il modulo di configurazione dei tag Open Graph personalizzati nel Back Office.
    -   `opengraph/views/templates/hook/script.tpl`:
        -   **Hook**: Potrebbe essere `displayHeader` o `actionFrontControllerSetMedia`.
        -   **Scopo**: Questo template potrebbe essere utilizzato per produrre qualsiasi JavaScript inline relativo a Open Graph, come l'inizializzazione dell'SDK di Facebook o il tracciamento di eventi specifici, sebbene il dossier non indichi file JS, quindi potrebbe essere per uno script molto minimale o un segnaposto.
-   **Template admin (`views/templates/admin/`)**: Non esplicitamente elencati, ma `form.tpl` e potenzialmente un `list.tpl` sarebbero utilizzati da `AdminOpenGraphController` per le sue viste.
-   **Template front-office (`views/templates/front/`)**:

    -   `opengraph/views/templates/front/hook/header.tpl` è l'unico template front-office identificato, specificamente per l'iniezione di hook.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   `ps_configuration`: Memorizza le impostazioni principali del modulo (es. `PS_OG_ENABLED`, `PS_OG_APP_ID`, `PS_OG_ADMIN_ID`, `PS_OG_HOME_IMAGE`, `PS_OG_HOME_TITLE`, `PS_OG_HOME_DESCRIPTION`).
    -   `ps_og_tags` (o simile, gestita da `AdminOpenGraphController`): Una tabella personalizzata per memorizzare le sovrascritture dei tag Open Graph definite dall'utente per URL specifici.
        -   Campi probabili: `id_og_tag`, `url`, `title`, `description`, `image`, `date_add`, `date_upd`.
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Rende il contenuto all'interno della sezione `<head>` di tutte le pagine del front-office. | Hook primario per l'iniezione di meta tag Open Graph (`og:title`, `og:description`, `og:image`, `og:url`, `og:type`, ecc.) nell'HTML. |
| `actionFrontControllerSetMedia` | Eseguito dopo che il controller frontale ha impostato i suoi media (CSS/JS). | Potrebbe essere utilizzato come hook alternativo o aggiuntivo per iniettare meta tag o script correlati, specialmente in PrestaShop 1.7+. |
| `displayBackOfficeHeader` | Rende il contenuto all'interno della sezione `<head>` delle pagine del Back Office. | Utilizzato per includere qualsiasi CSS o JS necessario per le pagine di configurazione del modulo nel Back Office. |
| `actionAdminControllerSetMedia` | Eseguito dopo che un controller admin ha impostato i suoi media. | Simile a `displayBackOfficeHeader` ma più specifico per i controller admin, per caricare risorse per `AdminOpenGraphController`. |
| `moduleRoutes` (PrestaShop 1.7+) | Consente ai moduli di definire route personalizzate. | Non esplicitamente utilizzato per la funzione principale di questo modulo, ma potrebbe essere presente per future estensioni o gestione specifica degli URL. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e per accedere alle ultime versioni del modulo "Facebook Open Graph Tags", visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e all'integrazione del modulo.
