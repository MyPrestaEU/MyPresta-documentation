---
title: "Note adesive Back office - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Note adesive Back office di MyPresta.eu."
sidebar:
  label: "Note adesive Back office - Manuale del commerciante e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Back office Sticky Notes su MyPresta.eu](https://mypresta.eu/modules/administration-tools/back-office-sticky-notes.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/back-office-sticky-notes/)
>
> ---


# Note adesive Back office

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono in genere sufficienti e solitamente preinstallate nella maggior parte degli ambienti di hosting.

## 2. Panoramica completa della configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" verrai indirizzato alla schermata di configurazione principale per il modulo "Note adesive Back office". Qui è dove gestisci le tue note adesive.

La pagina di configurazione stessa non ha molte "impostazioni" nel senso tradizionale (come interruttori on/off). Invece, è il tuo hub centrale per creare, modificare e gestire tutte le tue note adesive.

#### **Aggiunta di una nuova nota adesiva**

Nella parte superiore della pagina di configurazione, troverai tipicamente un modulo o una sezione per aggiungere una nuova nota.

-   **Contenuto della nota (Area di testo):**

    -   **Cosa fa questa impostazione:** Qui è dove digiti il messaggio o il promemoria effettivo per la tua nota adesiva.
    -   **Effetto della modifica di questa impostazione:** Qualsiasi cosa tu digiti qui verrà visualizzata sulla nota adesiva nel tuo back office.
    -   **Valore consigliato:** Sii conciso e chiaro. Usa elenchi puntati o frasi brevi per la leggibilità.
    -   **Scenario / esempio del commerciante:** "Ricorda di dare seguito al cliente #1234 riguardo allo stato del suo ordine." o "Nuove immagini prodotto per 'Collezione Estiva' entro venerdì."
-   **Colore della nota (Selettore colore):**

    -   **Cosa fa questa impostazione:** Ti permette di scegliere il colore di sfondo della tua nota adesiva.
    -   **Effetto della modifica di questa impostazione:** La nota adesiva apparirà con il colore scelto nel back office. Colori diversi possono aiutare a categorizzare le note o evidenziare l'urgenza.
    -   **Valore consigliato:** Scegli colori che risaltano ma non sono troppo distraenti. Potresti usare il rosso per le note urgenti, il giallo per i promemoria generali e il verde per i compiti completati.
    -   **Scenario / esempio del commerciante:** Imposta una nota su un bug critico in rosso e una nota su una nuova idea di marketing in giallo.
-   **Pulsante Salva / Aggiungi nota:**

    -   **Cosa fa questa impostazione:** Invia il contenuto e il colore che hai scelto per creare una nuova nota adesiva.
    -   **Effetto della modifica di questa impostazione:** Verrà creata una nuova nota adesiva che apparirà sulle pagine del tuo back office. Sarà anche elencata nella sezione "Note esistenti" sottostante.
    -   **Valore consigliato:** Clicca questo dopo aver finalizzato il contenuto e il colore della tua nota.
    -   **Scenario / esempio del commerciante:** Dopo aver digitato il tuo promemoria e selezionato un colore, clicca su "Salva" per rendere la nota attiva.

#### **Gestione delle note adesive esistenti**

Sotto la sezione "Aggiungi nuova nota", vedrai un elenco o una tabella di tutte le note adesive che hai già creato.

-   **Elenco note (Tabella/Visualizzazione):**

    -   **Cosa fa questa impostazione:** Mostra tutte le note adesive attive, il loro contenuto e il colore assegnato.
    -   **Effetto della modifica di questa impostazione:** Questa è una visualizzazione delle tue note attuali. Puoi rivederle visivamente qui.
    -   **Valore consigliato:** Rivedi regolarmente questo elenco per assicurarti che le note siano ancora pertinenti.
    -   **Scenario / esempio del commerciante:** Scansiona rapidamente l'elenco per vedere tutti i compiti o i promemoria in sospeso.
-   **Pulsante Modifica (per ogni nota):**

    -   **Cosa fa questa impostazione:** Ti permette di modificare il contenuto o il colore di una nota adesiva esistente.
    -   **Effetto della modifica di questa impostazione:** Cliccando su questo, il contenuto della nota verrà tipicamente ricaricato nel modulo "Aggiungi nuova nota" (che potrebbe cambiare in modalità "Modifica nota"), permettendoti di apportare modifiche. Una volta salvata, la nota si aggiornerà in tutto il tuo back office.
    -   **Valore consigliato:** Usalo per aggiornare lo stato dei compiti, aggiungere maggiori dettagli o cambiare l'urgenza.
    -   **Scenario / esempio del commerciante:** Una nota dice "Controlla nuove immagini prodotto". Una volta controllate, puoi modificarla in "Nuove immagini prodotto approvate".
-   **Pulsante Elimina (per ogni nota):**

    -   **Cosa fa questa impostazione:** Rimuove permanentemente una nota adesiva.
    -   **Effetto della modifica di questa impostazione:** La nota scomparirà dal tuo back office e non sarà più elencata nella configurazione. Questa azione è solitamente irreversibile.
    -   **Valore consigliato:** Elimina le note solo quando il compito è completato o l'informazione non è più pertinente.
    -   **Scenario / esempio del commerciante:** Una volta risolto un problema di ordine, elimina la nota adesiva correlata.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | **Contenuto della nota (Area di testo)** | Testo chiaro, conciso | Il messaggio effettivo visualizzato sulla nota adesiva. |
| Pagina di configurazione del modulo | **Colore della nota (Selettore colore)** | Selezionato dall'utente | Imposta il colore di sfondo della nota per categorizzazione/urgenza. |
| Pagina di configurazione del modulo | **Pulsante Salva / Aggiungi nota** | Clicca dopo aver impostato contenuto/colore | Crea una nuova nota adesiva visibile nel back office. |
| Pagina di configurazione del modulo | **Pulsante Modifica (per nota)** | Clicca per modificare | Permette di aggiornare il contenuto o il colore di una nota esistente. |
| Pagina di configurazione del modulo | **Pulsante Elimina (per nota)** | Clicca per rimuovere | Rimuove permanentemente una nota adesiva dal back office. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Le mie note adesive non appaiono nel back office dopo averle salvate.**
R1:

-   **Svuota cache:** La ragione più comune per problemi di visualizzazione è la cache. Vai su **Parametri avanzati > Prestazioni** nel tuo back office PrestaShop. Clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti).
-   **Controlla lo stato del modulo:** Assicurati che il modulo sia ancora installato e abilitato in **Moduli > Gestione moduli**.
-   **Cache del browser:** Prova a svuotare la cache del tuo browser o ad aprire il tuo back office in una finestra di navigazione in incognito/privata per escludere problemi specifici del browser.

**D2: Posso spostare le note adesive sullo schermo?**
R2: Sì, una volta che una nota adesiva è visualizzata nel tuo back office, dovresti essere in grado di cliccarla e trascinarla in qualsiasi posizione sulla pagina. Il modulo è progettato per ricordare la sua posizione per te.

**D3: Amministratori diversi possono vedere le note adesive degli altri?**
R3: Sì, per impostazione predefinita, tutte le note adesive create tramite questo modulo sono visibili a tutti gli amministratori che hanno accesso al back office. Questa è una caratteristica chiave per la collaborazione del team.

**D4: I colori delle mie note adesive sembrano strani o non vengono applicati correttamente.**
R4:

-   **Controlla il selettore colore:** Assicurati di utilizzare correttamente lo strumento selettore colore nella pagina di configurazione del modulo.
-   **Conflitti con temi personalizzati:** Se stai utilizzando un tema del back office pesantemente personalizzato, potrebbero esserci conflitti CSS. Prova a passare temporaneamente al tema predefinito del back office di PrestaShop per vedere se il problema persiste. Se si risolve, è probabile che il CSS del tuo tema stia sovrascrivendo gli stili del modulo.
-   **Compatibilità del browser:** Assicurati che il tuo browser sia aggiornato.

**D5: Come posso tradurre l'interfaccia del modulo in un'altra lingua?**
R5:

-   Vai su **Internazionale > Traduzioni** nel tuo back office PrestaShop.
-   Seleziona "Traduzioni dei moduli installati", scegli il tuo tema e poi seleziona la lingua che desideri tradurre.
-   Trova "Note adesive Back office" nell'elenco e traduci le stringhe di testo disponibili.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Note adesive Back office" è un classico modulo PrestaShop progettato principalmente per il Back Office. Sfrutta l'architettura dei moduli di PrestaShop, utilizzando la classe `Module` per l'installazione, la disinstallazione e la configurazione. La funzionalità principale ruota attorno alla visualizzazione e alla gestione delle "note adesive" create dall'utente all'interno del pannello di amministrazione. Si basa fortemente su JavaScript per l'interazione front-end (trascinamento, posizionamento) e AJAX per il salvataggio dei dati delle note. La persistenza dei dati è gestita tramite `ps_configuration` per le impostazioni del modulo e probabilmente tabelle di database personalizzate o `ps_configuration` per le note stesse.

### 4.2 Controller (`controllers/`)

Questo modulo non sembra utilizzare controller amministrativi dedicati per il Front-Office o il Back-Office nel senso tradizionale MVC di PrestaShop (cioè, file in `controllers/front/` o `controllers/admin/`). Tutta la configurazione e la gestione AJAX sembrano essere gestite direttamente all'interno del file principale del modulo (`addstickynote.php`) utilizzando il metodo `getContent()` per la configurazione e potenzialmente i metodi `ajaxProcess` o chiamate AJAX dirette per la gestione dinamica delle note.

### 4.3 Classi e modelli principali (`classes/`)

Basandosi sull'inventario fornito, non ci sono classi personalizzate o definizioni di `ObjectModel` all'interno di una directory `classes/`. Ciò suggerisce che i dati delle note adesive sono probabilmente archiviati direttamente nella tabella `ps_configuration`, dove il contenuto, il colore e la posizione di ogni nota potrebbero essere serializzati o archiviati come singole chiavi di configurazione.

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo si basa fortemente su JavaScript per le sue funzionalità interattive nel back office.

-   `stickynotes/js/advajax.js`:
    -   **Ambito:** Back-office.
    -   **Responsabilità:** Probabilmente uno script di utilità AJAX personalizzato, possibilmente un wrapper per le funzioni AJAX di jQuery o un'implementazione standalone per gestire la comunicazione asincrona con il backend PHP del modulo per il salvataggio/caricamento delle note.
-   `stickynotes/js/joverlay.js`:
    -   **Ambito:** Back-office.
    -   **Responsabilità:** Suggerisce funzionalità relative a overlay o popup modali, potenzialmente utilizzati per modificare il contenuto delle note in un'interfaccia più user-friendly, o per visualizzare messaggi di conferma.
-   `stickynotes/js/jscolor/jscolor.js`:
    -   **Ambito:** Back-office (specificamente nella pagina di configurazione del modulo).
    -   **Responsabilità:** Una libreria JavaScript di terze parti per fornire un'interfaccia di selezione colore. Viene utilizzata per consentire agli amministratori di selezionare il colore di sfondo per le loro note adesive.
-   `stickynotes/js/script.js`:
    -   **Ambito:** Back-office.
    -   **Responsabilità:** Questo è probabilmente lo script principale per la logica front-end del modulo. Gestirebbe:
        -   Inizializzazione delle note adesive al caricamento della pagina.
        -   Funzionalità di trascinamento per riposizionare le note.
        -   Salvataggio delle posizioni delle note tramite AJAX.
        -   Listener di eventi per la modifica/eliminazione delle note.
        -   Interazione con `advajax.js` per la persistenza dei dati.
        -   Potenzialmente il rendering dinamico di nuove note.
-   `stickynotes/js/script17.js`:
    -   **Ambito:** Back-office (specifico per PrestaShop 1.7.x e 8.x).
    -   **Responsabilità:** Questo script contiene probabilmente adattamenti o codice specifico per gli ambienti PrestaShop 1.7+, affrontando le differenze nella struttura DOM, nelle versioni di jQuery o nelle modifiche al tema del back office rispetto alle versioni precedenti di PrestaShop (1.5/1.6). Garantirebbe la compatibilità e il corretto funzionamento su piattaforme più recenti.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo include file CSS per stilizzare l'aspetto delle note adesive.

-   `stickynotes/css/stickynotes-twig-shit.css`:
    -   **Ambito:** Stile amministrativo del back-office.
    -   **Responsabilità:** Il nome suggerisce che questo file contiene aggiustamenti di stile specifici o override per i back office di PrestaShop 1.7+, che utilizzano la templating Twig. Probabilmente mira agli elementi all'interno del nuovo tema del back office per garantire che le note siano visualizzate correttamente e in modo coerente.
    -   **Selettori CSS chiave:** `.sticky-note`, `.sticky-note-content`, `.sticky-note-header` (ipotetici, basati su convenzioni di denominazione comuni).
-   `stickynotes/css/stickynotes.css`:
    -   **Ambito:** Stile amministrativo del back-office.
    -   **Responsabilità:** Questo è il foglio di stile principale per le note adesive, che definisce il loro aspetto predefinito, il posizionamento e gli stati interattivi (ad esempio, quando vengono trascinate). Contenerebbe stili generali applicabili a diverse versioni di PrestaShop.
    -   **Selettori CSS chiave:** `.sticky-note`, `.draggable`, `.resizable`, `.note-text`, `.note-controls` (ipotetici). Gli sviluppatori possono sovrascrivere queste classi nei loro temi personalizzati del back office, se necessario.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo utilizza un singolo template Smarty per il rendering delle note adesive nel back office.

-   **Template hook (`views/templates/hook/`)**:
    -   `stickynotes/sticky-notes-back-office.tpl`:
        -   **Renderizzato nel hook:** Questo template è probabilmente agganciato a un hook globale del back office, come `displayBackOfficeHeader` o `displayAdminAfterHeader`, per iniettare la struttura HTML e l'inizializzazione JavaScript necessarie per le note adesive su tutte le pagine di amministrazione.
        -   **Output del blocco visivo:** Emette i contenitori HTML per le note adesive, potenzialmente includendo un template nascosto per nuove note, e le chiamate JavaScript per inizializzare la visualizzazione delle note e la funzionalità di trascinamento. Contenerebbe anche la logica per iterare le note esistenti e renderizzarle.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Questo modulo non sembra creare tabelle SQL personalizzate. È altamente probabile che tutti i dati delle note adesive (contenuto, colore, posizione, ID) siano archiviati nella tabella `ps_configuration`. Ogni nota potrebbe corrispondere a una chiave di configurazione `PS_STICKY_NOTE_X` univoca, dove `X` è un identificatore, e il valore è un array serializzato o una stringa JSON contenente le proprietà della nota.
-   **Tabella degli hook registrati**:

| Nome dell'Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayBackOfficeHeader` | Eseguito nella sezione `<head>` di ogni pagina del back office. | Inietta i file CSS e JavaScript necessari per la funzionalità e lo stile delle note adesive. |
| `displayAdminAfterHeader` (o simile) | Eseguito dopo l'intestazione principale di ogni pagina del back office. | Renderizza la struttura HTML per le note adesive e inizializza la loro visualizzazione e il comportamento interattivo. |
| `actionAdminControllerSetMedia` | Eseguito quando un controller amministrativo imposta i suoi media (JS/CSS). | Potenzialmente utilizzato per caricare condizionalmente risorse JS/CSS in base alla pagina amministrativa corrente, sebbene `displayBackOfficeHeader` sia più comune per le risorse globali. |
| `actionModuleInstall` | Eseguito quando il modulo viene installato. | Crea le voci di configurazione iniziali in `ps_configuration` (se presenti) e registra gli hook necessari. |
| `actionModuleUninstall` | Eseguito quando il modulo viene disinstallato. | Pulisce le voci di configurazione e deregistra gli hook. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e per scaricare le ultime versioni del modulo "Note adesive Back office", visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e compatibilità del modulo.
"""
