---
title: "Geolocation pro - valuta e lingua per paese - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Geolocation pro - valuta e lingua per paese di MyPresta.eu."
sidebar:
  label: "Geolocation pro - valuta e lingua per paese - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Geolocation pro - currency and language by country su MyPresta.eu](https://mypresta.eu/modules/front-office-features/geolocation-pro-currency-and-language-by-country.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/geolocation-pro-currency-and-language-by-country/)
>
> ---


# Geolocation pro - valuta e lingua per paese

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste e solitamente disponibili sulla maggior parte degli ambienti di hosting.

## 2. Guida completa alla configurazione (ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Geolocation pro - valuta e lingua per paese)

Questa è la schermata di configurazione principale dove abiliti o disabiliti la funzionalità principale del modulo e accedi agli strumenti diagnostici.

-   **Abilita Geolocation Pro:**

    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per l'intero modulo.
    -   **Effetto del cambiamento di questa impostazione:**
        -   *Quando abilitato:* Il modulo rileverà attivamente le posizioni dei clienti e applicherà le tue regole di valuta e lingua definite.
        -   *Quando disabilitato:* Il modulo sarà inattivo e il tuo negozio tornerà alle sue impostazioni predefinite di valuta e lingua per tutti i visitatori, indipendentemente dalla loro posizione.
    -   **Valore consigliato:** SÌ (per utilizzare le funzionalità del modulo).
    -   **Scenario / esempio del commerciante:** Hai finito di impostare tutte le tue regole e sei pronto a pubblicare esperienze personalizzate. Abilita questo interruttore. Se hai bisogno di disabilitare temporaneamente la funzione per manutenzione, disattivala.
-   **Mostra banner con scelta del paese:**

    -   **Cosa fa questa impostazione:** Determina se appare un piccolo banner o pop-up per informare i clienti sul paese rilevato e offrire loro la possibilità di cambiarlo.
    -   **Effetto del cambiamento di questa impostazione:**
        -   *Quando abilitato:* Apparirà un banner (solitamente nella parte superiore o inferiore dello schermo) che mostra il paese rilevato e potenzialmente consente al cliente di sovrascrivere manualmente la posizione, la valuta o la lingua rilevate. Questo può essere utile per i clienti che utilizzano VPN o che preferiscono le impostazioni di una regione diversa.
        -   *Quando disabilitato:* Non verrà mostrato alcun banner. Il modulo applicherà silenziosamente le regole basate sul rilevamento IP.
    -   **Valore consigliato:** SÌ (inizialmente, per dare ai clienti il controllo, poi considera NO se preferisci un'esperienza completamente fluida e ti fidi del rilevamento IP).
    -   **Scenario / esempio del commerciante:** Un cliente dagli USA sta visitando il tuo negozio e il modulo rileva correttamente la sua posizione. Se questa impostazione è abilitata, un banner potrebbe dire "Stai navigando dagli Stati Uniti. [Cambia paese?]" Questo gli dà la possibilità di correggerlo se sta usando una VPN o preferisce fare acquisti da una regione diversa.
-   **Diagnostica e Strumenti:**

    -   **Cosa fa questa impostazione:** Questa sezione fornisce strumenti per testare la funzionalità del modulo e verificare il rilevamento IP. Non è un'impostazione da modificare, ma un'utilità.
    -   **Effetto del cambiamento di questa impostazione:** Cliccando sugli strumenti diagnostici si apriranno nuove viste o pop-up che mostrano informazioni sul tuo attuale indirizzo IP, paese rilevato e come il modulo applicherebbe le regole.
    -   **Valore consigliato:** Usalo ogni volta che stai impostando nuove regole o risolvendo problemi.
    -   **Scenario / esempio del commerciante:** Hai creato una regola per la Germania. Puoi usare lo strumento diagnostico per simulare una visita dalla Germania e vedere se la valuta e la lingua corrette vengono applicate, assicurandoti che le tue regole funzionino come previsto.

### 2.2 Schermata amministrativa dedicata: Regole Geo (Back Office > Moduli > Geolocation pro > Regole Geo)

Questa schermata ti consente di definire e gestire le regole principali per valuta e lingua in base al paese.

-   **Nome schermata e posizione menu:** **Back Office > Moduli > Geolocation pro - valuta e lingua per paese > Regole Geo** (o percorso simile sotto la voce di menu principale del modulo).
-   **Azioni e impostazioni disponibili:**
    -   **Tabella di elenco:** Visualizza tutte le tue regole geo esistenti, mostrando il paese, la valuta assegnata e la lingua assegnata.
    -   **Aggiungi nuova regola geo:** Un pulsante per creare una nuova regola.
    -   **Azioni Modifica/Elimina:** Icone accanto a ogni regola per modificarla o rimuoverla.
-   **Effetto dei cambiamenti:**
    -   **Aggiunta di una nuova regola:** Quando aggiungi una regola (es. per "Germania" per usare "EUR" e "Tedesco"), qualsiasi visitatore rilevato come proveniente dalla Germania avrà automaticamente la sua valuta e lingua impostate su questi valori.
    -   **Modifica di una regola:** La modifica di una regola esistente cambierà istantaneamente il comportamento del modulo per i visitatori di quel paese specifico.
    -   **Eliminazione di una regola:** La rimozione di una regola significa che i visitatori di quel paese non avranno più una valuta o una lingua specifica applicata da questo modulo e torneranno alle impostazioni predefinite del tuo negozio.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  **Identifica i paesi target:** Decidi quali paesi vuoi targettizzare con valute e lingue specifiche.
    2.  **Assicurati che valute/lingue siano abilitate:** Assicurati che le valute e le lingue che vuoi assegnare siano già abilitate nel tuo negozio PrestaShop (Back Office > Internazionale > Valute / Lingue).
    3.  **Crea regole:** Per ogni paese, clicca su "Aggiungi nuova regola geo", seleziona il paese dal menu a discesa, quindi seleziona la valuta e la lingua desiderate. Salva la regola.
    4.  **Testa con la diagnostica:** Usa gli strumenti diagnostici del modulo per verificare che le tue regole funzionino come previsto.

### 2.3 Schermata amministrativa dedicata: Regole Lingua (Back Office > Moduli > Geolocation pro > Regole Lingua)

Questa schermata sembra essere un'interfaccia duplicata o alternativa per la gestione delle regole specifiche per la lingua, offrendo potenzialmente un controllo più granulare o una vista diversa. Data la descrizione del modulo, la schermata "Regole Geo" è probabilmente l'interfaccia principale per le assegnazioni basate sul paese. Questa schermata potrebbe essere per override più avanzati, specifici per la lingua, non direttamente legati a un paese.

-   **Nome schermata e posizione menu:** **Back Office > Moduli > Geolocation pro - valuta e lingua per paese > Regole Lingua** (o percorso simile).
-   **Azioni e impostazioni disponibili:**
    -   **Tabella di elenco:** Mostra le regole lingua esistenti.
    -   **Aggiungi nuova regola lingua:** Pulsante per creare una nuova regola.
    -   **Azioni Modifica/Elimina:** Icone per modificare o rimuovere le regole.
-   **Effetto dei cambiamenti:** Queste regole probabilmente sovrascriverebbero o completerebbero le regole basate sul paese per la lingua. Ad esempio, potresti avere una regola generale per "Inglese" per tutti i paesi non specificati, e poi usare questa schermata per eccezioni o comportamenti linguistici specifici.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Usa questa schermata se hai bisogno di gestire le impostazioni della lingua indipendentemente dalle regole geo specifiche per il paese, o se incontri scenari in cui una regola del paese non è sufficiente per la gestione della lingua. Altrimenti, concentrati sulla schermata "Regole Geo".

### 2.4 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Configurazione Modulo** | Abilita Geolocation Pro | SÌ | Interruttore principale per la funzionalità del modulo. SÌ attiva il rilevamento di valuta/lingua basato sul paese. |
| | Mostra banner con scelta del paese | SÌ | Visualizza un banner che informa i clienti del paese rilevato e consente l'override manuale. |
| | Diagnostica e Strumenti | N/A | Utilità per testare il rilevamento IP e l'applicazione delle regole. |
| **Regole Geo** | Aggiungi/Modifica Regola Geo (Paese, Valuta, Lingua) | N/A | Definisce quale valuta e lingua vengono impostate automaticamente per i visitatori di un paese specifico. |
| **Regole Lingua** | Aggiungi/Modifica Regola Lingua | N/A | (Potenzialmente) Definisce override di lingua o comportamenti linguistici specifici, possibilmente indipendenti dal paese. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei clienti continuano a vedere la valuta/lingua sbagliata anche dopo aver impostato le regole. Cosa c'è che non va?**
R1:

-   **Il modulo è abilitato?** Ricontrolla l'impostazione "Abilita Geolocation Pro" nella pagina di configurazione principale.
-   **Le tue regole sono corrette?** Vai su "Regole Geo" e assicurati che il paese, la valuta e la lingua siano assegnati correttamente.
-   **Le valute/lingue sono abilitate in PrestaShop?** Assicurati che le valute e le lingue che stai cercando di assegnare siano attive nel tuo PrestaShop (Internazionale > Valute / Lingue).
-   **Svuota la cache del tuo browser:** A volte il tuo browser potrebbe memorizzare in cache vecchie impostazioni. Chiedi ai clienti di svuotare la cache del loro browser o di provare una finestra in incognito.
-   **Svuota la cache di PrestaShop:** Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota la cache" in alto a destra.
-   **Testa con la Diagnostica:** Usa gli strumenti diagnostici integrati del modulo per simulare una visita da un paese specifico e vedere quale valuta/lingua applica. Questo aiuta a individuare se il problema è nel rilevamento o nell'applicazione delle regole.

**D2: Il modulo rileva il paese sbagliato per alcuni clienti. Perché?**
R2:

-   **VPN e Proxy:** I clienti che utilizzano Virtual Private Networks (VPN) o server proxy appariranno come se stessero navigando dalla posizione della loro VPN/proxy, non dalla loro effettiva posizione fisica. Il modulo si basa sul rilevamento dell'indirizzo IP, che può essere falsificato.
-   **Accuratezza del database IP:** I database di geolocalizzazione sono generalmente molto accurati ma non perfetti al 100%. Alcuni intervalli IP potrebbero essere identificati erroneamente.
-   **"Mostra banner con scelta del paese":** Se questa impostazione è abilitata, i clienti possono correggere manualmente il paese rilevato, che è la soluzione migliore per questi casi limite.

**D3: Come faccio ad aggiungere una nuova valuta o lingua al mio negozio in modo da poterla usare in una regola geo?**
R3:

-   **Aggiungere una Valuta:** Vai su **Internazionale > Valute** nel tuo Back Office di PrestaShop. Clicca su "Aggiungi nuova valuta", compila i dettagli e abilitala.
-   **Aggiungere una Lingua:** Vai su **Internazionale > Lingue** nel tuo Back Office di PrestaShop. Clicca su "Aggiungi nuova lingua", compila i dettagli e abilitala. Ricorda di installare anche i pacchetti lingua e di tradurre i tuoi contenuti per la nuova lingua.

**D4: Questo modulo rallenterà il mio sito web?**
R4: Il modulo esegue una rapida ricerca IP e applicazione delle regole, che è generalmente molto veloce e ottimizzata. Non dovrebbe influire in modo significativo sulla velocità di caricamento del tuo sito web. Se riscontri problemi di prestazioni, assicurati che la cache di PrestaShop sia abilitata e regolarmente svuotata.

**D5: Voglio stilizzare il banner di scelta del paese per abbinarlo al mio tema. Come posso farlo?**
R5: Il banner utilizza classi CSS specifiche. Sebbene la modifica diretta dei file del modulo non sia raccomandata (poiché gli aggiornamenti li sovrascriverebbero), uno sviluppatore web può utilizzare il file CSS personalizzato del tuo tema per sovrascrivere gli stili predefiniti. Dovrebbe ispezionare il banner utilizzando gli strumenti per sviluppatori del browser per identificare i selettori CSS pertinenti (es. classi come `.progeo-banner`, `.progeo-choice`) e quindi applicare i propri stili.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Geolocation pro - valuta e lingua per paese" (`progeo`) è progettato per integrarsi profondamente con le funzionalità di internazionalizzazione principali di PrestaShop. Sfrutta principalmente gli override per modificare il modo in cui PrestaShop determina la `Configuration`, `Currency` e `Language` attive in base all'indirizzo IP del visitatore. Segue una struttura standard del modulo PrestaShop, utilizzando controller front-office e admin, classi personalizzate (specialmente per le entità `ObjectModel`) e template Smarty sia per la configurazione che per la visualizzazione front-office (es. il banner di scelta del paese). La logica principale del modulo risiede nel suo `index.php` (file principale del modulo) e nelle classi core sovrascritte.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

-   `progeo/controllers/front/choice.php`
    -   **Nome classe e classe padre:** `ProgeoChoiceModuleFrontController` estende `ModuleFrontController`.
    -   **Responsabilità:** Questo controller gestisce le richieste AJAX relative al banner di scelta del paese. Quando un cliente interagisce con il banner (es. seleziona un paese, una valuta o una lingua diversa), questo controller elabora la richiesta, aggiorna le variabili di sessione o i cookie e potenzialmente reindirizza l'utente per applicare le nuove impostazioni. È cruciale per l'aspetto interattivo del banner.
-   `progeo/controllers/front/index.php`
    -   **Nome classe e classe padre:** `ProgeoIndexModuleFrontController` estende `ModuleFrontController`.
    -   **Responsabilità:** Questo controller potrebbe fungere da fallback o da semplice punto di ingresso per le azioni del modulo front-office, sebbene `choice.php` sia più specifico per l'interattività del banner. In molti moduli, `index.php` in `controllers/front` è un segnaposto o gestisce richieste front-office molto basilari e non specifiche.

#### Controller Admin Back-Office

-   `progeo/controllers/admin/AdminGeorulesController.php`
    -   **Nome tab e entità gestita:** "Regole Geo" (sotto il menu principale del modulo). Gestisce le entità `Georule`.
    -   **Responsabilità:** Questo è il controller principale per la gestione delle assegnazioni di valuta e lingua specifiche per paese. Fornisce l'interfaccia CRUD (Create, Read, Update, Delete) per i record `ps_progeo_georule`, consentendo agli amministratori di definire quale valuta e lingua dovrebbero essere attive per i visitatori di paesi specifici. Estende `AdminController` e utilizza `HelperList` per la griglia e `HelperForm` per i moduli di aggiunta/modifica.
-   `progeo/controllers/admin/AdminLangrules.php`
    -   **Nome tab e entità gestita:** "Regole Lingua" (sotto il menu principale del modulo). Gestisce le entità `Langrule`.
    -   **Responsabilità:** Questo controller gestisce le regole specifiche per la lingua. Fornisce un'interfaccia CRUD per i record `ps_progeo_langrule`. È probabilmente utilizzato per un controllo più granulare della lingua, potenzialmente sovrascrivendo o completando la lingua impostata in `AdminGeorulesController`.
-   `progeo/controllers/admin/AdminLangrulesController.php`
    -   **Nome tab e entità gestita:** "Regole Lingua" (sotto il menu principale del modulo). Gestisce le entità `Langrule`.
    -   **Responsabilità:** Questo sembra essere un duplicato o un'implementazione alternativa di `AdminLangrules.php`. In un tipico modulo PrestaShop, `AdminLangrulesController.php` sarebbe la convenzione di denominazione standard. Gli sviluppatori dovrebbero verificare quale file viene effettivamente utilizzato dalla registrazione del menu del modulo.
-   `progeo/controllers/admin/index.php`
    -   **Nome tab e entità gestita:** Non una tab diretta, ma un segnaposto standard.
    -   **Responsabilità:** Questo file è spesso presente nelle directory `controllers/admin` ma tipicamente vuoto o contiene misure di sicurezza di base (es. `die('Forbidden');`). Non gestisce un'entità specifica né fornisce un'interfaccia utente.

### 4.3 Classi e Modelli Core (`classes/`)

Il modulo utilizza gli override per iniettare la sua logica nel comportamento core di PrestaShop.

-   `progeo/override/classes/Configuration.php`
    -   **Responsabilità:** Sovrascrive la classe core `Configuration`. Questo è fondamentale affinché il modulo possa modificare i valori di configurazione globali (come `PS_CURRENCY_DEFAULT` o `PS_LANG_DEFAULT`) al volo in base alla geolocalizzazione, senza modificare effettivamente i valori del database per altri visitatori. Assicura che quando PrestaShop richiede un valore di configurazione, il modulo possa intercettarlo e restituirne uno localizzato.
-   `progeo/override/classes/Currency.php`
    -   **Responsabilità:** Sovrascrive la classe core `Currency`. Questo override consente al modulo di manipolare quale valuta è considerata "attiva" o "predefinita" per il visitatore corrente, garantendo che i prezzi siano visualizzati correttamente in base alla regola geo.
-   `progeo/override/classes/Language.php`
    -   **Responsabilità:** Sovrascrive la classe core `Language`. Similmente a `Currency.php`, questo override consente al modulo di impostare la lingua attiva per il visitatore corrente in base alla geolocalizzazione, garantendo che il contenuto sia visualizzato nella lingua corretta.
-   `progeo/override/classes/index.php`
    -   **Responsabilità:** File `index.php` standard vuoto per la sicurezza in una directory.
-   `progeo/override/classes/_Configuration.php`
    -   **Responsabilità:** Questo nome di file suggerisce un potenziale backup o una versione precedente dell'override di `Configuration`. In un ambiente di produzione, dovrebbe essere attivo un solo override di `Configuration.php`. Gli sviluppatori dovrebbero verificare il processo di installazione del modulo per assicurarsi che venga utilizzato l'override corretto.

### 4.4 Risorse JavaScript (`views/js/`)

-   `progeo/views/js/banner.js`
    -   **Ambito:** Front-office.
    -   **Responsabilità:** Questo script gestisce il banner interattivo di scelta del paese.
        -   **Listener di eventi:** Collega eventi agli elementi all'interno del banner (es. eventi click sui pulsanti "cambia paese", cambiamenti nelle caselle di selezione per valuta/lingua).
        -   **Chiamate AJAX:** Effettua richieste AJAX a `ProgeoChoiceModuleFrontController` (es. `choice.php`) per aggiornare il paese, la valuta o la lingua selezionati dall'utente.
        -   **Manipolazione del DOM:** Mostra/nasconde il banner, aggiorna il contenuto del testo in base alle selezioni dell'utente e potenzialmente reindirizza il browser dopo che è stata fatta una scelta.
        -   **Cookie/Archiviazione locale:** Può memorizzare le preferenze dell'utente nei cookie o nell'archiviazione locale per ricordare la loro scelta tra le sessioni.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `progeo/views/css/admin.css`
    -   **Ambito:** Stilizzazione del modulo admin del back-office.
    -   **Responsabilità:** Fornisce una stilizzazione specifica per le pagine di configurazione del modulo e i controller admin (es. `AdminGeorulesController`, `AdminLangrulesController`). Questo assicura un aspetto e una sensazione coerenti all'interno del back office di PrestaShop e migliora l'usabilità dei moduli e delle liste del modulo.
-   `progeo/views/css/banner.css`
    -   **Ambito:** Stilizzazione del cliente front-office.
    -   **Responsabilità:** Stilizza il banner di scelta del paese che appare nel front office. Definisce la posizione, i colori, i font, la reattività e la presentazione visiva complessiva del banner. Gli sviluppatori possono sovrascrivere questi stili nel CSS personalizzato del loro tema per integrare il banner senza soluzione di continuità con il design del negozio. I selettori chiave potrebbero includere `.progeo-banner`, `.progeo-choice-form`, ecc.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**:
    -   `progeo/views/displayHeader.tpl`: Questo template è probabilmente agganciato a `displayHeader` (o `actionFrontControllerSetMedia`) per includere i file CSS e JS necessari per il banner front-office, o per iniettare variabili JavaScript iniziali.
-   **Template admin (`views/templates/admin/`)**:
    -   `progeo/views/advert.tpl`: Probabilmente utilizzato per visualizzare messaggi promozionali o link ad altri moduli MyPresta.eu all'interno della configurazione del modulo.
    -   `progeo/views/banner.tpl`: Questo template è probabilmente utilizzato all'interno della configurazione del modulo per visualizzare in anteprima o gestire le impostazioni relative al banner front-office.
    -   `progeo/views/currenciesForm.tpl`: Template per la gestione delle impostazioni relative alla valuta, possibilmente all'interno della configurazione principale o di una schermata admin dedicata.
    -   `progeo/views/diagnostics-layer1.tpl`, `progeo/views/diagnostics-layer2.tpl`, `progeo/views/diagnostics-overview.tpl`, `progeo/views/diagnostics-result.tpl`, `progeo/views/diagnostics.tpl`: Questi template sono utilizzati per renderizzare i vari strumenti diagnostici e il loro output, aiutando l'amministratore a risolvere i problemi di rilevamento IP e applicazione delle regole.
    -   `progeo/views/languagesForm.tpl`: Template per la gestione delle impostazioni relative alla lingua, simile a `currenciesForm.tpl`.
    -   `progeo/views/tabs.tpl`: Utilizzato per renderizzare le schede di navigazione all'interno dell'interfaccia di configurazione del modulo, consentendo all'amministratore di passare tra diverse sezioni di impostazioni (es. "Regole Geo", "Regole Lingua", "Configurazione").
    -   `progeo/views/tools-hint.tpl`, `progeo/views/tools.tpl`: Template per la visualizzazione di suggerimenti o strumenti generali all'interno dell'interfaccia back-office del modulo.
-   **Template front-office (`views/templates/front/`)**:
    -   `progeo/views/banner.tpl`: Questo è il template effettivo per il banner di scelta del paese del front-office, renderizzato al cliente. Contiene la struttura HTML per visualizzare il paese, la valuta, la lingua rilevati e le opzioni per la selezione manuale.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**:

    -   `ps_progeo_georule`: Memorizza le regole principali di geolocalizzazione.
        -   `id_progeo_georule` (Chiave primaria)
        -   `id_country` (Chiave esterna a `ps_country`)
        -   `id_currency` (Chiave esterna a `ps_currency`)
        -   `id_lang` (Chiave esterna a `ps_lang`)
    -   `ps_progeo_langrule`: Memorizza le regole specifiche per la lingua (i dettagli dipenderebbero dalla sua implementazione specifica, ma probabilmente una struttura simile per gli override della lingua).
        -   `id_progeo_langrule` (Chiave primaria)
        -   `id_lang` (Chiave esterna a `ps_lang`)
        -   (Potenzialmente altri campi per comportamenti linguistici specifici)
    -   Record di configurazione in `ps_configuration`:
        -   `PROGEO_ENABLED`: (1 o 0) Interruttore principale per il modulo.
        -   `PROGEO_SHOW_BANNER`: (1 o 0) Se visualizzare il banner di scelta del paese.
        -   (Altre chiavi di configurazione come definite in `getContent()` e `install()`)
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina front-office. | Per includere risorse CSS e JavaScript (`banner.css`, `banner.js`) per il banner front-office, e potenzialmente per iniettare variabili JavaScript iniziali o renderizzare il banner stesso. |
| `actionFrontControllerSetMedia` | Eseguito quando un controller front-office sta impostando le sue risorse multimediali. | Simile a `displayHeader`, utilizzato per aggiungere file CSS e JS condizionalmente o in un modo più moderno di PrestaShop. |
| `actionModuleInstall` | Durante l'installazione del modulo. | Per creare tabelle del database (`ps_progeo_georule`, `ps_progeo_langrule`), registrare hook e impostare valori di configurazione predefiniti. |
| `actionModuleUninstall` | Durante la disinstallazione del modulo. | Per rimuovere tabelle del database, annullare la registrazione degli hook e pulire i valori di configurazione. |
| `displayBackOfficeHeader` | Nella sezione `<head>` di ogni pagina back-office. | Per includere `admin.css` per le pagine di configurazione del modulo e potenzialmente JavaScript specifico per l'amministrazione. |
| `actionAdminControllerSetMedia` | Eseguito quando un controller admin sta impostando le sue risorse multimediali. | Simile a `displayBackOfficeHeader`, per aggiungere CSS e JS admin. |
| `actionDispatcherBefore` | Prima che il dispatcher elabori una richiesta. | Cruciale per la logica principale del modulo: per rilevare l'IP del visitatore, applicare la regola geo e impostare la valuta e la lingua corrette del `Context` *prima* che PrestaShop renderizzi la pagina. È qui che gli override vengono effettivamente attivati. |
| `displayBanner` (Hook personalizzato) | Potenzialmente un hook personalizzato per il rendering del banner front-office. | Se `displayBanner` è un hook personalizzato, il modulo si registrerebbe per renderizzare `banner.tpl` in questa posizione specifica. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo "Geolocation pro - valuta e lingua per paese", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a garantire che il tuo modulo funzioni in modo ottimale e si integri perfettamente con il tuo negozio PrestaShop.
