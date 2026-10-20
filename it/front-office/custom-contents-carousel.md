---
title: "Carosello di contenuti personalizzati - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Carosello di contenuti personalizzati di MyPresta.eu."
sidebar:
  label: "Carosello di contenuti personalizzati - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Custom contents carousel su MyPresta.eu](https://mypresta.eu/modules/front-office-features/custom-contents-carousel.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/custom-contents-carousel/)
>
> ---


# Carosello di contenuti personalizzati

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server oltre a un ambiente di hosting PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

Il modulo "Carosello di contenuti personalizzati" organizza le sue impostazioni su diverse schermate nel tuo Back Office di PrestaShop. Per prima cosa configurerai le impostazioni globali, quindi creerai "Gruppi" (che sono i tuoi caroselli) e infine aggiungerai "Elementi" (le singole slide) a ciascun gruppo.

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Carosello di contenuti personalizzati)

Questa è la schermata di configurazione principale per il modulo, accessibile immediatamente dopo l'installazione o cliccando su "Configura" dal Gestore moduli.

-   **Cosa fa questa impostazione:** Questa schermata gestisce principalmente le impostazioni generali del modulo e i controlli degli aggiornamenti.
-   **Effetto della modifica di questa impostazione:**
    *   `mypresta_updates`, `update_`, `updatev_`: Queste sono impostazioni interne utilizzate dai moduli MyPresta.eu per gestire gli aggiornamenti e i controlli di versione. Non influenzano direttamente la visualizzazione del front-office ma assicurano che il tuo modulo rimanga aggiornato.
    *   `CCAROUSEL_LIGHTSLIDER`: Questa impostazione probabilmente controlla l'attivazione della libreria JavaScript LightSlider, che alimenta la funzionalità del carosello.
        *   *Quando abilitato (SÌ)*: La libreria LightSlider verrà caricata sul tuo front office, consentendo ai caroselli di funzionare correttamente.
        *   *Quando disabilitato (NO)*: La libreria LightSlider potrebbe non caricarsi, potenzialmente interrompendo la visualizzazione e la funzionalità del carosello.
-   **Valore consigliato:**
    *   `CCAROUSEL_LIGHTSLIDER`: **SÌ** (Abilitato). Questo è cruciale per il funzionamento del carosello.
    *   Altre impostazioni: Lasciare come predefinito.
-   **Scenario/esempio del commerciante:** Hai appena installato il modulo e vuoi assicurarti che tutti gli script necessari siano caricati. Verificheresti che `CCAROUSEL_LIGHTSLIDER` sia abilitato. Se dovessi riscontrare problemi con il carosello che non scorre, questo sarebbe uno dei primi posti da controllare.

### 2.2 Schermata di amministrazione dedicata: Gruppi di contenuti personalizzati (Back Office > Moduli > Carosello di contenuti personalizzati > Gruppi di contenuti personalizzati)

Questa schermata ti consente di creare e gestire i tuoi singoli caroselli. Ogni "gruppo" rappresenta un carosello distinto che puoi poi popolare con slide.

-   **Nome schermata e posizione nel menu:** Lo troverai sotto **Moduli > Carosello di contenuti personalizzati > Gruppi di contenuti personalizzati** nel menu del tuo Back Office di PrestaShop.
-   **Azioni e impostazioni disponibili:**
    *   **Vista a griglia**: Visualizza un elenco di tutti i tuoi gruppi di caroselli esistenti. Puoi vedere i loro nomi, lo stato (attivo/inattivo) e le azioni.
    *   **Aggiungi nuovo gruppo**: Clicca sul pulsante "Aggiungi nuovo" per creare un carosello completamente nuovo.
    *   **Modifica/Elimina gruppo**: Per ogni gruppo, avrai opzioni per modificarne le impostazioni (es. nome, opzioni di visualizzazione) o eliminarlo completamente.
    *   **Attiva/Disattiva stato**: Attiva o disattiva rapidamente un gruppo di caroselli senza eliminarlo. Un gruppo inattivo non apparirà sul tuo front office.
-   **Effetto delle modifiche:**
    *   **Aggiunta di un nuovo gruppo**: Crea un nuovo contenitore carosello vuoto. Dovrai quindi aggiungervi elementi (slide).
    *   **Modifica di un gruppo**: Ti consente di cambiare il nome del carosello, le sue impostazioni di visualizzazione (es. riproduzione automatica, velocità, numero di slide visibili) e la sua posizione.
    *   **Attivazione/Disattivazione**: Controlla se il carosello è visibile ai tuoi clienti sul front office.
    *   **Eliminazione di un gruppo**: Rimuove permanentemente il carosello e tutti i suoi elementi (slide) associati.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Inizia creando un nuovo gruppo per ogni carosello che desideri visualizzare (es. "Carosello banner homepage", "Slider nuovi arrivi").
    2.  Dai a ogni gruppo un nome chiaro e descrittivo.
    3.  Configura le impostazioni di visualizzazione del gruppo (es. riproduzione automatica, loop, pausa al passaggio del mouse) per corrispondere all'esperienza utente desiderata.
    4.  Una volta creato il gruppo, procedi alla schermata "Elementi di contenuti personalizzati" per aggiungervi le slide.

### 2.3 Schermata di amministrazione dedicata: Elementi di contenuti personalizzati (Back Office > Moduli > Carosello di contenuti personalizzati > Elementi di contenuti personalizzati)

Questa schermata è dove gestisci le singole slide (elementi) all'interno dei tuoi caroselli. Ogni elemento può essere un'immagine, un video, un testo o un contenuto incorporato.

-   **Nome schermata e posizione nel menu:** Lo troverai sotto **Moduli > Carosello di contenuti personalizzati > Elementi di contenuti personalizzati** nel menu del tuo Back Office di PrestaShop.
-   **Azioni e impostazioni disponibili:**
    *   **Vista a griglia**: Elenca tutte le singole slide, mostrando a quale gruppo appartengono, il loro tipo di contenuto e lo stato.
    *   **Aggiungi nuovo elemento**: Clicca su "Aggiungi nuovo" per creare una nuova slide. Sceglierai quindi il gruppo a cui appartiene e ne definirai il contenuto.
    *   **Modifica/Elimina elemento**: Modifica il contenuto, il link o l'ordine di visualizzazione di una slide esistente, oppure rimuovila.
    *   **Attiva/Disattiva stato**: Attiva o disattiva le singole slide. Una slide inattiva non apparirà nel suo carosello.
    *   **Riordinamento trascina e rilascia**: Cambia facilmente l'ordine di visualizzazione delle slide all'interno di un gruppo.
-   **Effetto delle modifiche:**
    *   **Aggiunta di un nuovo elemento**: Crea una nuova slide. Specificherai il suo contenuto (caricamento immagine, URL video, testo, HTML), un link e lo assegnerai a uno dei tuoi gruppi di caroselli esistenti.
    *   **Modifica di un elemento**: Ti consente di aggiornare il contenuto, cambiare il link, modificare l'immagine o regolare la sua posizione all'interno del carosello.
    *   **Attivazione/Disattivazione**: Controlla se una specifica slide è visibile all'interno del suo carosello.
    *   **Eliminazione di un elemento**: Rimuove permanentemente la slide dal suo carosello.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Seleziona il gruppo di caroselli a cui vuoi aggiungere slide (se ne hai più di uno).
    2.  Clicca su "Aggiungi nuovo elemento" e scegli il tipo di contenuto (immagine, video, testo, HTML).
    3.  Carica la tua immagine, incolla l'URL del tuo video o inserisci il tuo testo/HTML.
    4.  Aggiungi un link pertinente se la slide deve indirizzare i clienti a un prodotto, una categoria o una pagina esterna.
    5.  Imposta l'ordine di visualizzazione.
    6.  Ripeti per tutte le slide del tuo carosello.
    7.  Usa la funzione trascina e rilascia per affinare l'ordine delle tue slide.

### 2.4 Schermata di amministrazione dedicata: `index.php` (`ccarousel/controllers/admin/index.php`)

Questo file è una pratica standard di PrestaShop per la protezione delle directory di amministrazione. Tipicamente contiene una semplice istruzione `die('No direct script access allowed');` e non presenta una schermata configurabile o un'entità gestita di per sé. È una misura di sicurezza, non un'interfaccia di configurazione.

### 2.5 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | `CCAROUSEL_LIGHTSLIDER` | SÌ | Abilita/disabilita la libreria JavaScript principale per la funzionalità del carosello. **Deve essere SÌ affinché i caroselli funzionino.** |
| Gruppi di Contenuti Personalizzati | Nome Gruppo | Definito dall'utente | Identifica il tuo carosello (es. "Banner Homepage"). |
| Gruppi di Contenuti Personalizzati | Stato | Abilitato | Controlla la visibilità dell'intero carosello sul front office. |
| Gruppi di Contenuti Personalizzati | Impostazioni Carosello | Definito dall'utente | Controlla riproduzione automatica, velocità, loop, navigazione, ecc., per ogni carosello. |
| Elementi di Contenuti Personalizzati | Contenuto Elemento | Definito dall'utente | Il contenuto effettivo della slide (immagine, video, testo, HTML). |
| Elementi di Contenuti Personalizzati | Link Elemento | URL opzionale | Dove la slide indirizza i clienti quando cliccata. |
| Elementi di Contenuti Personalizzati | Stato | Abilitato | Controlla la visibilità delle singole slide all'interno di un carosello. |
| Elementi di Contenuti Personalizzati | Posizione | Definito dall'utente | Determina l'ordine delle slide all'interno di un carosello. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Il mio carosello non viene visualizzato sulla homepage.**

-   **R:** Innanzitutto, verifica che il modulo "Carosello di contenuti personalizzati" sia abilitato in **Moduli > Gestione moduli**. Quindi, naviga su **Moduli > Carosello di contenuti personalizzati > Gruppi di contenuti personalizzati** e assicurati che il tuo gruppo di caroselli sia attivo (spunta verde). Infine, assicurati di avere almeno un "Elemento di contenuto personalizzato" attivo assegnato a quel gruppo. Inoltre, verifica che l'impostazione `CCAROUSEL_LIGHTSLIDER` nella pagina di configurazione principale del modulo sia abilitata.

**D2: Le immagini del mio carosello sono sfocate o distorte.**

-   **R:** Assicurati che le immagini che carichi siano di alta qualità e con dimensioni appropriate per lo spazio in cui viene visualizzato il carosello. Se il tuo tema ha raccomandazioni specifiche sulle dimensioni delle immagini per banner o slider, prova a rispettarle. Il modulo ridimensionerà le immagini, ma partire da un'immagine sorgente di buona qualità è fondamentale.

**D3: Il carosello non scorre o non si riproduce automaticamente.**

-   **R:** Questo è spesso un problema di JavaScript.
    1.  Vai su **Moduli > Configura > Carosello di contenuti personalizzati** e assicurati che `CCAROUSEL_LIGHTSLIDER` sia impostato su "SÌ".
    2.  Svuota la cache di PrestaShop (**Parametri avanzati > Prestazioni > Svuota cache**).
    3.  Svuota la cache del tuo browser.
    4.  Se il problema persiste, potrebbe esserci un conflitto JavaScript con un altro modulo o il tuo tema. Controlla la console per sviluppatori del tuo browser (F12) per eventuali errori JavaScript.

**D4: Come posso cambiare l'ordine delle slide nel mio carosello?**

-   **R:** Vai su **Moduli > Carosello di contenuti personalizzati > Elementi di contenuti personalizzati**. Dovresti vedere un elenco delle tue slide. Cerca una colonna con frecce o un'icona di trascinamento. Di solito puoi trascinare le righe per riordinarle, oppure potrebbe esserci un campo "Posizione" che puoi modificare. Ricorda di salvare le modifiche.

**D5: Posso avere più caroselli su pagine diverse?**

-   **R:** Il modulo utilizza principalmente l'hook `displayHome`, il che significa che è progettato per la homepage. Sebbene tu possa creare più *gruppi* (caroselli), tutti verranno tipicamente renderizzati nella stessa posizione agganciata. Per visualizzare caroselli su pagine diverse o in posizioni diverse, sarebbe necessaria un'integrazione personalizzata del tema o una registrazione aggiuntiva dell'hook (vedi Guida per sviluppatori).

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster che mantengono o estendono il modulo "Carosello di contenuti personalizzati".

### 4.1 Panoramica dell'architettura

Il modulo "Carosello di contenuti personalizzati" segue un modello MVC (Model-View-Controller) standard di PrestaShop per i suoi componenti del Back Office. Sfrutta la classe `Module` di PrestaShop per la funzionalità principale e `AdminController` per la gestione dei gruppi e degli elementi di contenuto. La visualizzazione del front-office è gestita principalmente tramite un template Smarty agganciato a `displayHome`, con risorse JavaScript (LightSlider) e CSS caricate tramite `displayHeader`. La persistenza dei dati è gestita tramite classi `ObjectModel` personalizzate.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:
    Il modulo non contiene controller front-office dedicati. Tutto il rendering del front-office è gestito direttamente tramite la classe principale del modulo (`ccarousel.php`) registrando hook e renderizzando template.
-   **Controller Admin Back-Office**:

    *   `controllers/admin/AdminCustomContentsGroupsController.php`
        *   Nome classe: `AdminCustomContentsGroupsController`
        *   Classe padre: `ModuleAdminController`
        *   Responsabilità: Gestisce l'entità `gcarousel` (gruppi di caroselli). Questo controller gestisce l'elenco, l'aggiunta, la modifica e l'eliminazione dei gruppi di caroselli. Definisce i campi del modulo per la configurazione del gruppo (es. nome, stato, impostazioni del carosello come riproduzione automatica, velocità).
    *   `controllers/admin/AdminCustomContentsItemsController.php`
        *   Nome classe: `AdminCustomContentsItemsController`
        *   Classe padre: `ModuleAdminController`
        *   Responsabilità: Gestisce l'entità `gcitem` (singole slide/elementi del carosello). Questo controller gestisce l'elenco, l'aggiunta, la modifica e l'eliminazione delle slide. Definisce i campi del modulo per il contenuto della slide (caricamento immagine, URL video, testo/HTML, link, posizione, gruppo associato). Gestisce anche la funzionalità di riordinamento trascina e rilascia per le slide.
    *   `controllers/admin/index.php`
        *   Nome classe: N/A (semplice file PHP)
        *   Classe padre: N/A
        *   Responsabilità: Una misura di sicurezza per prevenire l'elenco diretto delle directory o l'accesso. Contiene `die('No direct script access allowed');`.

### 4.3 Classi e modelli principali (`classes/`)

Il dossier del modulo non indica classi personalizzate nella directory `classes/`. Ciò suggerisce che le definizioni di `ObjectModel` per `gcarousel` e `gcitem` sono probabilmente incorporate direttamente nel file principale del modulo (`ccarousel.php`) o all'interno dei rispettivi file `AdminController`.

-   **`gcarousel` (Modello Gruppo Carosello)**:

    *   Probabilmente estende `ObjectModel`.
    *   Interagisce con una tabella di database personalizzata (es. `ps_gcarousel`).
    *   I campi `$definition` includerebbero: `id_gcarousel`, `name`, `active`, `settings` (possibilmente un array serializzato o una stringa JSON per le opzioni di visualizzazione del carosello).
    *   Metodi chiave: `add()`, `update()`, `delete()`, `getGroups()`.
-   **`gcitem` (Modello Elemento/Slide Carosello)**:

    *   Probabilmente estende `ObjectModel`.
    *   Interagisce con una tabella di database personalizzata (es. `ps_gcitem`).
    *   I campi `$definition` includerebbero: `id_gcitem`, `id_gcarousel` (chiave esterna), `position`, `active`, `type` (immagine, video, testo, html), `content` (percorso dell'immagine, URL video, testo), `link`, `title`, `description` (per il supporto multilingue).
    *   Metodi chiave: `add()`, `update()`, `delete()`, `getItemsByGroup()`, `updatePosition()`.

### 4.4 Risorse JavaScript (`views/js/`)

-   `ccarousel/lib/src/js/lightslider.js`
    *   Ambito: Front-office.
    *   Responsabilità: Questa è la libreria LightSlider principale. Inizializza e gestisce la funzionalità del carosello. Lega i listener di eventi per la navigazione (frecce, punti), gestisce i gesti touch/swipe, la riproduzione automatica, il looping e le regolazioni reattive. Il metodo `hookDisplayHeader` o `hookDisplayHome` del modulo tipicamente accoderebbe questo script, e quindi uno script inline o un file JS del modulo separato chiamerebbe `$('#your-carousel-selector').lightSlider({...});` per inizializzare caroselli specifici.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `ccarousel/css.css`
    *   Ambito: Front-office.
    *   Responsabilità: Probabilmente contiene stili personalizzati specifici per il modulo "Carosello di contenuti personalizzati", sovrascrivendo o estendendo gli stili base di LightSlider per adattarsi al tema predefinito di PrestaShop o fornire regolazioni visive specifiche del modulo.
-   `ccarousel/lib/src/css/ccarousel.css`
    *   Ambito: Front-office.
    *   Responsabilità: Potrebbe essere un foglio di stile di base per la struttura del modulo o un segnaposto. Dato il nome, è probabile che si tratti di uno stile specifico del modulo.
-   `ccarousel/lib/src/css/lightslider.css`
    *   Ambito: Front-office.
    *   Responsabilità: Il foglio di stile predefinito per la libreria LightSlider. Fornisce lo stile essenziale per il contenitore del carosello, le slide, le frecce di navigazione e i punti di paginazione. Gli sviluppatori possono sovrascrivere questi stili nel `custom.css` del loro tema o modificando `ccarousel/css.css`.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**:
    *   `ccarousel/views/templates/hook/ccarousel.tpl`
        *   Renderizzato in: `displayHome` (e potenzialmente altri hook se configurato nel modulo).
        *   Output: La struttura HTML per uno o più caroselli. Questo template itera attraverso i gruppi di caroselli e i loro elementi associati, generando gli elementi `<ul>` e `<li>` necessari che LightSlider si aspetta. Include tag immagine, incorporamenti video o contenuto HTML grezzo basato sul tipo di elemento, insieme ai link. Probabilmente contiene anche la chiamata di inizializzazione JavaScript per LightSlider, passando le opzioni di configurazione recuperate dalle impostazioni di `gcarousel`.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    *   `ps_gcarousel`: Memorizza le informazioni su ogni gruppo di caroselli.
        *   `id_gcarousel` (PK, INT)
        *   `name` (VARCHAR)
        *   `active` (TINYINT)
        *   `settings` (TEXT o JSON, per opzioni LightSlider serializzate)
        *   `date_add` (DATETIME)
        *   `date_upd` (DATETIME)
    *   `ps_gcitem`: Memorizza le informazioni su ogni singola slide/elemento.
        *   `id_gcitem` (PK, INT)
        *   `id_gcarousel` (FK a `ps_gcarousel`, INT)
        *   `position` (INT)
        *   `active` (TINYINT)
        *   `type` (VARCHAR, es. 'image', 'video', 'text', 'html')
        *   `content` (TEXT, memorizza percorso immagine, URL video o testo/HTML grezzo)
        *   `link` (VARCHAR)
        *   `title` (VARCHAR, per multilingua)
        *   `description` (TEXT, per multilingua)
        *   `date_add` (DATETIME)
        *   `date_upd` (DATETIME)
    *   `ps_configuration`: Memorizza i valori di configurazione specifici del modulo, come `CCAROUSEL_LIGHTSLIDER`, `MYPRESTA_UPDATES`, ecc.
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Accoda i file CSS (`lightslider.css`, `ccarousel.css`) e JavaScript (`lightslider.js`) necessari affinché il carosello funzioni e sia stilizzato correttamente. |
| `displayHome` | Nell'area principale dei contenuti della homepage. | Renderizza il template `ccarousel.tpl`, che genera la struttura HTML per i gruppi di caroselli attivi e i loro elementi, insieme allo script di inizializzazione di LightSlider. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e per assicurarti di utilizzare la versione più recente e sicura del modulo "Carosello di contenuti personalizzati", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda riguardante la funzionalità e la compatibilità del modulo.
"""
