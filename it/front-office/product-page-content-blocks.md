---
title: "Blocchi di contenuto della pagina prodotto - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Blocchi di contenuto della pagina prodotto' di MyPresta.eu."
sidebar:
  label: "Blocchi di contenuto della pagina prodotto - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Product page content blocks su MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-content-blocks.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/product-page-content-blocks/)
>
> ---


# Blocchi di contenuto della pagina prodotto

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per un'installazione PrestaShop e questo modulo non introduce requisiti specifici aggiuntivi oltre a questi.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

Il modulo "Blocchi di contenuto della pagina prodotto" opera principalmente tramite una scheda dedicata nella pagina di modifica di ogni prodotto, piuttosto che una singola schermata di configurazione globale. Tuttavia, esiste una pagina di configurazione principale del modulo per la configurazione iniziale e un controller AJAX per la gestione dei blocchi.

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Quando installi il modulo per la prima volta e fai clic su "Configura", verrai indirizzato alla sua pagina di configurazione principale. Questa pagina gestisce tipicamente la configurazione iniziale o le impostazioni globali, se presenti.

-   **Cosa fa questa impostazione:** Questa pagina funge da punto di ingresso per il modulo. Sebbene la funzionalità principale di creazione dei blocchi sia svolta sulle pagine dei prodotti, questa schermata potrebbe offrire impostazioni generali o una rapida panoramica.
-   **Effetto della modifica di questa impostazione:** Qualsiasi impostazione qui si applicherebbe globalmente al comportamento del modulo su tutte le pagine dei prodotti, come l'abilitazione/disabilitazione completa del modulo o l'impostazione di comportamenti predefiniti.
-   **Valore consigliato:** Seguire le istruzioni sullo schermo. Se non ci sono impostazioni specifiche, questa pagina si limiterà a confermare che il modulo è installato e pronto per l'uso.
-   **Scenario / esempio del commerciante:** Potresti trovare qui un interruttore per "Abilita/Disabilita Modulo" che disattiverebbe tutti i blocchi di contenuto personalizzati nel tuo negozio senza disinstallare il modulo.

### 2.2 Schermate di amministrazione dedicate e viste del controller

L'interazione principale con questo modulo avviene nella pagina di modifica del prodotto.

#### 2.2.1 Pagina di modifica del prodotto (Catalogo > Prodotti > Modifica un prodotto)

Dopo aver installato il modulo, quando modifichi un prodotto nel back office di PrestaShop, troverai una nuova scheda dedicata a "Blocchi di contenuto della pagina prodotto" (o nome simile).

-   **Nome schermata e posizione nel menu:** **Catalogo > Prodotti > [Seleziona/Modifica un prodotto] > scheda "Blocchi di contenuto della pagina prodotto"**
-   **Azioni e impostazioni disponibili:**

    -   **Aggiunta di un nuovo blocco:** Di solito vedrai un pulsante come "Aggiungi nuovo blocco" o un'interfaccia simile per creare un nuovo blocco di contenuto per il prodotto corrente.
        -   **Cosa fa questa impostazione:** Consente di definire un nuovo pezzo di contenuto.
        -   **Effetto della modifica di questa impostazione:** Verrà creato e memorizzato un nuovo blocco di contenuto per questo prodotto specifico.
        -   **Scenario / esempio del commerciante:** Vuoi aggiungere un tutorial video per un prodotto complesso. Fai clic su "Aggiungi nuovo blocco".
    -   **Editor di contenuti:** Per ogni blocco, avrai un editor di testo ricco (WYSIWYG) dove puoi inserire testo, immagini, video o persino HTML personalizzato.
        -   **Cosa fa questa impostazione:** Definisce il contenuto effettivo che verrà visualizzato.
        -   **Effetto della modifica di questa impostazione:** Il contenuto che inserisci qui verrà renderizzato nel front office.
        -   **Scenario / esempio del commerciante:** Digiti "Guarda il nostro video di unboxing!" e incorpori un link a un video di YouTube.
    -   **Selezione dell'hook:** Un menu a discesa o un elenco di hook PrestaShop disponibili (`displayHeader`, `displayFooterProduct`, `displayRightColumnProduct`, ecc.).
        -   **Cosa fa questa impostazione:** Determina la posizione esatta in cui il tuo blocco di contenuto apparirà nella pagina del prodotto.
        -   **Effetto della modifica di questa impostazione:** Il blocco verrà renderizzato nella posizione dell'hook selezionato.
        -   **Valore consigliato:** Scegli l'hook che meglio si adatta allo scopo del contenuto. Per i dettagli specifici del prodotto, `displayProductAdditionalInfo` o `displayFooterProduct` sono comuni. Per gli elementi di fiducia, `displayReassurance`.
        -   **Scenario / esempio del commerciante:** Vuoi che un badge di fiducia appaia vicino al pulsante "aggiungi al carrello", quindi selezioni `displayReassurance`.
    -   **Stato del blocco (Abilitato/Disabilitato):** Un interruttore per attivare o disattivare il blocco.
        -   **Cosa fa questa impostazione:** Controlla se il blocco è visibile nel front office.
        -   **Effetto della modifica di questa impostazione:**
            -   *Quando abilitato:* Il blocco apparirà nella pagina del prodotto.
            -   *Quando disabilitato:* Il blocco sarà nascosto ma non eliminato, consentendoti di riattivarlo in seguito.
        -   **Valore consigliato:** Abilita i blocchi che vuoi mostrare, disabilita quelli che vuoi nascondere temporaneamente.
        -   **Scenario / esempio del commerciante:** Hai un blocco promozionale stagionale che vuoi nascondere dopo la fine della stagione, ma potresti riutilizzare l'anno prossimo.
    -   **Ordine/Posizione:** Spesso un'interfaccia drag-and-drop o un campo di input per impostare l'ordine di visualizzazione se più blocchi si trovano nello stesso hook.
        -   **Cosa fa questa impostazione:** Determina la sequenza dei blocchi all'interno di un singolo hook.
        -   **Effetto della modifica di questa impostazione:** I blocchi appariranno nell'ordine specificato.
        -   **Scenario / esempio del commerciante:** Hai tre badge di fiducia in `displayReassurance` e vuoi che il badge "Spedizione gratuita" appaia per primo.
    -   **Modifica/Eliminazione blocchi:** Pulsanti per modificare i blocchi esistenti o rimuoverli completamente.
        -   **Cosa fa questa impostazione:** Consente di aggiornare il contenuto, l'hook o lo stato, o di rimuovere permanentemente un blocco.
        -   **Effetto della modifica di questa impostazione:** Aggiorna o rimuove il blocco dalla pagina del prodotto.
        -   **Scenario / esempio del commerciante:** La descrizione di un prodotto è cambiata, quindi modifichi il contenuto di un blocco correlato.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

    1.  Vai su **Catalogo > Prodotti** e seleziona il prodotto che desideri migliorare.
    2.  Fai clic sulla scheda "Blocchi di contenuto della pagina prodotto".
    3.  Fai clic su "Aggiungi nuovo blocco" per creare una nuova sezione di contenuto.
    4.  Inserisci il tuo contenuto utilizzando l'editor di testo ricco.
    5.  Seleziona l'hook appropriato per dove vuoi che il contenuto appaia.
    6.  Assicurati che il blocco sia abilitato.
    7.  Salva le modifiche per il prodotto.
    8.  Ripeti per altri prodotti secondo necessità. Controlla regolarmente le tue pagine prodotto per assicurarti che i blocchi vengano visualizzati come previsto.

#### 2.2.2 AdminMegablocksAjaxController (megablocks/controllers/admin/AdminMegablocksAjax.php)

Questo controller non è direttamente accessibile dai commercianti tramite una voce di menu. Invece, gestisce le operazioni in background (richieste AJAX) quando interagisci con la scheda "Blocchi di contenuto della pagina prodotto" nella pagina di modifica del prodotto. Ad esempio, quando salvi un nuovo blocco, ne modifichi uno esistente o ne cambi l'ordine, questo controller elabora tali richieste senza richiedere un ricaricamento completo della pagina.

-   **Nome schermata e posizione nel menu:** Non direttamente accessibile. Opera dietro le quinte nella pagina di modifica del prodotto.
-   **Azioni e impostazioni disponibili:** Gestisce la creazione, l'aggiornamento, l'eliminazione e il riordino dei blocchi di contenuto per i singoli prodotti.
-   **Effetto delle modifiche:** Assicura che le modifiche ai blocchi di contenuto nella pagina di modifica del prodotto vengano salvate nel database e riflesse nel front office.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Interagisci con questo controller implicitamente utilizzando la scheda "Blocchi di contenuto della pagina prodotto" nella pagina di modifica del prodotto. Non è richiesta alcuna interazione diretta.

#### 2.2.3 index.php (megablocks/controllers/admin/index.php)

Questo file è una pratica standard di PrestaShop per la protezione delle directory dei controller di amministrazione e tipicamente contiene solo un'istruzione `die('Access Denied');`. Non rappresenta una schermata funzionale o un'area di configurazione per il commerciante.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Pagina di configurazione del modulo** | (Impostazioni globali, se presenti) | (Secondo le impostazioni predefinite del modulo) | Configurazione iniziale, abilitazione/disabilitazione globale o comportamento generale del modulo. |
| **Pagina di modifica del prodotto (Scheda)** | Aggiungi nuovo blocco | N/A | Crea un nuovo blocco di contenuto per il prodotto corrente. |
| | Editor di contenuti | Vuoto | Definisce il contenuto HTML/testo del blocco. |
| | Selezione hook | Varia (es. `displayFooterProduct`) | Determina la posizione di visualizzazione nella pagina del prodotto. |
| | Stato del blocco | Abilitato | Controlla la visibilità del blocco nel front office. |
| | Ordine/Posizione | 1 (o il successivo disponibile) | Imposta la sequenza di visualizzazione dei blocchi all'interno di un hook. |
| | Modifica/Elimina blocco | N/A | Modifica o rimuove i blocchi di contenuto esistenti. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Il mio nuovo blocco di contenuto non viene visualizzato nella pagina del prodotto. Cosa devo fare?**
**R1:**

1.  **Controlla lo stato del blocco:** Vai alla pagina di modifica del prodotto, naviga nella scheda "Blocchi di contenuto della pagina prodotto" e assicurati che il blocco che hai creato sia impostato su "Abilitato".
2.  **Svuota la cache:** PrestaShop utilizza la cache per velocizzare il tuo negozio. Vai su **Parametri avanzati > Prestazioni** e fai clic su "Svuota cache" (o "Svuota cache Smarty" se disponibile).
3.  **Verifica la selezione dell'hook:** Ricontrolla di aver selezionato un hook che è effettivamente renderizzato dal tuo tema nella pagina del prodotto. Alcuni temi potrebbero non utilizzare tutti gli hook standard di PrestaShop.
4.  **Compatibilità del tema:** Se il tuo tema è pesantemente personalizzato, potrebbe sovrascrivere i posizionamenti standard degli hook. Contatta lo sviluppatore del tuo tema o un webmaster per confermare la struttura degli hook del tema.

**D2: Il blocco di contenuto appare strano o senza stile nella mia pagina prodotto.**
**R2:**

1.  **Controlla il tuo contenuto:** Se hai aggiunto HTML personalizzato o copiato contenuto da un'altra fonte, potrebbe contenere stili in conflitto. Prova a incollare il tuo contenuto prima in un editor di testo semplice per rimuovere qualsiasi formattazione nascosta, quindi incollalo di nuovo nell'editor del modulo.
2.  **CSS del modulo:** Il modulo include alcuni CSS di base. Se il tuo tema ha uno stile molto specifico, potrebbe sovrascrivere o entrare in conflitto con gli stili del modulo.
3.  **Stile del tema personalizzato:** Per uno stile avanzato, potresti aver bisogno di un webmaster per aggiungere regole CSS personalizzate al foglio di stile del tuo tema per far sì che il blocco corrisponda al design del tuo negozio. Possono mirare agli elementi HTML specifici generati dal modulo.

**D3: Posso usare questo modulo per negozi multilingue?**
**R3:** Sì, tipicamente i blocchi di contenuto creati con questo modulo supporteranno la funzionalità multilingue di PrestaShop. Quando modifichi un blocco, dovresti vedere le schede delle lingue (es. Inglese, Francese, Spagnolo) accanto all'editor di contenuti. Puoi inserire contenuti diversi per ogni lingua, assicurandoti che i tuoi blocchi siano localizzati per i tuoi clienti internazionali.

**D4: Voglio visualizzare lo stesso blocco su più pagine prodotto. Devo crearlo ripetutamente?**
**R4:** Questo modulo è progettato per contenuti *specifici del prodotto*. Se hai bisogno dello *stesso identico* blocco di contenuto su molti prodotti, dovresti attualmente crearlo per ogni prodotto. Per contenuti veramente globali che appaiono su *tutte* le pagine prodotto (o tutte le pagine di un certo tipo), un diverso tipo di modulo (es. un modulo di blocco HTML personalizzato che si aggancia globalmente) potrebbe essere più efficiente. Tuttavia, la forza di questo modulo è la sua capacità di personalizzare il contenuto per prodotto.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce un'analisi approfondita della struttura tecnica del modulo "Blocchi di contenuto della pagina prodotto" per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo "Blocchi di contenuto della pagina prodotto" (`megablocks`) segue un'architettura standard dei moduli PrestaShop, sfruttando principalmente la classe `Module` per l'installazione e la registrazione degli hook. La sua funzionalità principale ruota attorno alla gestione dei blocchi di contenuto specifici del prodotto, che vengono memorizzati in una tabella di database personalizzata. Il modulo estende la funzionalità del back-office di PrestaShop iniettando una scheda personalizzata nella pagina di modifica del prodotto, gestita da un controller AJAX. La visualizzazione nel front-office è ottenuta agganciandosi a vari hook `display*` nella pagina del prodotto e renderizzando specifici template Smarty.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Questo modulo non contiene alcun controller front-office dedicato. Tutto il rendering del contenuto del front-office è gestito direttamente tramite hook registrati all'interno del file principale del modulo `index.php`, che poi renderizza template specifici.
-   **Controller Admin Back-Office**:

    -   `megablocks/controllers/admin/AdminMegablocksAjax.php`
        -   **Nome classe e classe padre**: `AdminMegablocksAjaxController` che estende `ModuleAdminController`.
        -   **Responsabilità**: Questo controller gestisce tutte le richieste AJAX originate dalla scheda "Blocchi di contenuto della pagina prodotto" nella pagina di modifica del prodotto. È responsabile di:
            -   Creazione di nuovi blocchi di contenuto.
            -   Aggiornamento di blocchi di contenuto esistenti (contenuto, hook, stato, posizione).
            -   Eliminazione di blocchi di contenuto.
            -   Recupero dei dati dei blocchi di contenuto per un prodotto specifico.
            -   Non ha una voce di menu diretta ma viene invocato tramite chiamate JavaScript dalla pagina di modifica del prodotto.
    -   `megablocks/controllers/admin/index.php`
        -   **Nome classe e classe padre**: Non è un controller funzionale.
        -   **Responsabilità**: Questo è un file di sicurezza, standard nelle directory admin di PrestaShop, contenente `die('Access Denied');` per impedire la visualizzazione diretta della directory o l'accesso.

### 4.3 Classi e modelli principali (`classes/`)

Il dossier del modulo non indica classi personalizzate nella directory `classes/`. Ciò implica che la gestione dei dati del modulo (ad esempio, il salvataggio e il recupero dei blocchi di contenuto) è probabilmente gestita direttamente all'interno del file principale `megablocks/index.php`, potenzialmente utilizzando `Db::getInstance()` per interazioni dirette con il database o una semplice struttura di array per la configurazione. Se viene utilizzata una tabella di database personalizzata, il suo schema e i metodi di interazione sarebbero definiti all'interno del file principale del modulo.

### 4.4 Risorse JavaScript (`views/js/`)

-   `megablocks/js/script.js`
    -   **Ambito**: Probabilmente front-office.
    -   **Dettagli**: Questo script conterrebbe qualsiasi logica lato client richiesta per la visualizzazione front-office dei blocchi di contenuto. Ciò potrebbe includere semplici animazioni, aggiustamenti reattivi o interazioni se i blocchi contengono elementi dinamici.
-   `megablocks/views/admin/megablocks.js`
    -   **Ambito**: Back-office (Pagina di modifica del prodotto).
    -   **Dettagli**: Questo è il file JavaScript principale per la gestione dei blocchi di contenuto nel back office. È responsabile di:
        -   Inizializzazione della scheda "Blocchi di contenuto della pagina prodotto" nella pagina di modifica del prodotto.
        -   Gestione degli eventi di clic per i pulsanti "Aggiungi nuovo blocco", "Modifica" ed "Elimina".
        -   Gestione dell'editor di testo ricco (ad esempio, integrazione TinyMCE o CKEditor) per l'input del contenuto.
        -   Invio di richieste AJAX a `AdminMegablocksAjaxController` per la creazione, l'aggiornamento e l'eliminazione dei blocchi.
        -   Aggiornamento dinamico dell'interfaccia utente in base alle risposte AJAX (ad esempio, aggiunta di un nuovo blocco all'elenco, rimozione di un blocco eliminato).
        -   Implementazione della funzionalità di trascinamento e rilascio per il riordino dei blocchi.
-   `megablocks/views/fancybox/script.js`
    -   **Ambito**: Back-office (Pagina di modifica del prodotto).
    -   **Dettagli**: Questo script probabilmente si integra con o implementa una "Fancybox" (o una libreria modale/lightbox simile) per visualizzare i moduli "Aggiungi nuovo blocco" o "Modifica blocco" in una finestra popup. Gestirebbe l'apertura/chiusura del modale, il caricamento del contenuto al suo interno e l'invio dei dati del modulo.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `megablocks/views/admin/megablocks.css`
    -   **Ambito**: Stile del modulo di amministrazione del back-office.
    -   **Dettagli**: Contiene regole CSS specifiche per lo stile della scheda "Blocchi di contenuto della pagina prodotto", l'elenco dei blocchi, i moduli di aggiunta/modifica e qualsiasi elemento UI personalizzato all'interno del back office di PrestaShop.
    -   **Selettori di classe CSS chiave**: Gli sviluppatori possono ispezionare l'HTML generato nella pagina di modifica del prodotto per identificare classi specifiche (ad esempio, `.megablocks-list`, `.megablock-item`, `.megablock-form`) da sovrascrivere o estendere nel loro tema admin personalizzato o nelle sovrascritture del modulo.
-   `megablocks/views/css/milligram.css`
    -   **Ambito**: Potenzialmente sia front-office che back-office, o specificamente per i moduli modali.
    -   **Dettagli**: Milligram è un framework CSS minimalista. La sua inclusione suggerisce che il modulo potrebbe usarlo per uno stile di base e pulito dei suoi blocchi di contenuto generati nel front-office, o per i moduli modali nel back-office (ad esempio, il contenuto di Fancybox). Fornisce una base leggera per tipografia, moduli e layout a griglia.
    -   **Selettori di classe CSS chiave**: Sarebbero presenti classi Milligram standard (ad esempio, `.container`, `.row`, `.column`, `.button`, `.input`). Gli sviluppatori possono sovrascrivere queste o aggiungere stili più specifici nel CSS del loro tema.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template degli hook (`views/templates/front/`)**: Questi template vengono inclusi dinamicamente dal modulo quando un blocco di contenuto è configurato per un hook specifico. Ogni file `megablock-*.tpl` funge probabilmente da wrapper o da template standard per il rendering del contenuto di un singolo blocco. Il contenuto effettivo (HTML) definito dal commerciante viene solitamente passato come variabile Smarty e renderizzato direttamente.

    -   `megablocks/views/front/megablock-actionProductOutOfStock.tpl`: Renderizza il contenuto quando un prodotto è esaurito.
    -   `megablocks/views/front/megablock-displayAfterProductThumbs.tpl`: Renderizza il contenuto dopo le immagini/miniature del prodotto.
    -   `megablocks/views/front/megablock-displayBeforeBodyClosingTag.tpl`: Renderizza il contenuto appena prima del tag `</body>`.
    -   `megablocks/views/front/megablock-displayFooter.tpl`: Renderizza il contenuto nel footer generale del sito.
    -   `megablocks/views/front/megablock-displayFooterBefore.tpl`: Renderizza il contenuto prima del footer generale del sito.
    -   `megablocks/views/front/megablock-displayFooterProduct.tpl`: Renderizza il contenuto nell'area del footer specifica del prodotto.
    -   `megablocks/views/front/megablock-displayHeader.tpl`: Renderizza il contenuto nell'header generale del sito.
    -   `megablocks/views/front/megablock-displayLeftColumnProduct.tpl`: Renderizza il contenuto nella colonna sinistra della pagina del prodotto.
    -   `megablocks/views/front/megablock-displayNav1.tpl`: Renderizza il contenuto nella prima area di navigazione.
    -   `megablocks/views/front/megablock-displayNav2.tpl`: Renderizza il contenuto nella seconda area di navigazione.
    -   `megablocks/views/front/megablock-displayProductAdditionalInfo.tpl`: Renderizza il contenuto nella sezione delle informazioni aggiuntive del prodotto.
    -   `megablocks/views/front/megablock-displayProductPriceBlock.tpl`: Renderizza il contenuto vicino al blocco del prezzo del prodotto.
    -   `megablocks/views/front/megablock-displayReassurance.tpl`: Renderizza il contenuto nel blocco di rassicurazione (ad esempio, badge di fiducia).
    -   `megablocks/views/front/megablock-displayRightColumnProduct.tpl`: Renderizza il contenuto nella colonna destra della pagina del prodotto.
    -   `megablocks/views/front/megablock-displayTop.tpl`: Renderizza il contenuto nella sezione superiore della pagina.
-   **Template di amministrazione (`views/templates/admin/`)**:

    -   `megablocks/views/admin/li_megablock.tpl`: Questo template è probabilmente utilizzato per renderizzare un singolo elemento nell'elenco dei blocchi di contenuto nella pagina di modifica del prodotto. Visualizzerebbe il titolo del blocco, l'hook selezionato, lo stato e i pulsanti di modifica/eliminazione.
    -   `megablocks/views/admin/tabs.tpl`: Questo template probabilmente definisce la struttura della scheda "Blocchi di contenuto della pagina prodotto" stessa, inclusi il pulsante "Aggiungi nuovo blocco" e il contenitore per l'elenco dei blocchi.
-   **Template Fancybox (`views/fancybox/`)**: Questi template vengono utilizzati per i moduli modali (Fancybox) nel back office.

    -   `megablocks/views/fancybox/edit.tpl`: Il template del modulo per la modifica di un blocco di contenuto esistente.
    -   `megablocks/views/fancybox/heading.tpl`: Un template per l'intestazione o il titolo del modale Fancybox.
    -   `megablocks/views/fancybox/new.tpl`: Il template del modulo per la creazione di un nuovo blocco di contenuto.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il modulo probabilmente crea una tabella di database personalizzata, ad esempio `ps_megablocks` (o simile), per memorizzare i blocchi di contenuto.
    -   Questa tabella conterrebbe tipicamente campi come:
        -   `id_megablock`: Chiave primaria.
        -   `id_product`: Chiave esterna che si collega a `ps_product`.
        -   `hook_name`: Il nome dell'hook di PrestaShop in cui viene visualizzato il blocco (ad esempio, `displayFooterProduct`).
        -   `position`: L'ordine del blocco all'interno del suo hook.
        -   `active`: Booleano (0 o 1) per lo stato del blocco.
        -   `content`: Il contenuto HTML effettivo del blocco (probabilmente un campo `TEXT` o `LONGTEXT`).
        -   `content_lang`: Se il contenuto è multilingue, questa potrebbe essere una tabella separata (`ps_megablocks_lang`) o gestita tramite dati serializzati in `content`.
    -   I record di configurazione sono memorizzati in `ps_configuration` per le impostazioni globali del modulo (ad esempio, `MEGABLOCKS_ENABLED`).
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| :--- | :--- | :--- |
| `displayHeader` | Renderizza il contenuto nella sezione `<head>` del documento HTML. | N/A | Principalmente per includere CSS, JavaScript, meta tag o altri elementi che influenzano il comportamento tecnico della pagina o lo stile globale. |
| `displayNav1` | Renderizza il contenuto nella prima area di navigazione. | N/A | Tipicamente per visualizzare elementi come selettori di valuta, selettori di lingua o collegamenti rapidi. |
| `displayNav2` | Renderizza il contenuto nella seconda area di navigazione. | N/A | Spesso utilizzato per collegamenti all'account cliente, informazioni di contatto o altri elementi di navigazione secondaria. |
| `displayTop` | Renderizza il contenuto nella sezione superiore della pagina, di solito sotto l'intestazione ma sopra il contenuto principale. | N/A | Ideale per banner, barre di ricerca o annunci importanti. |
| `displayLeftColumnProduct` | Renderizza il contenuto nella barra laterale sinistra della pagina del prodotto. | N/A | Adatto per filtri di prodotto, categorie correlate o blocchi promozionali specifici del prodotto. |
| `displayRightColumnProduct` | Renderizza il contenuto nella barra laterale destra della pagina del prodotto. | N/A | Simile alla colonna sinistra, può essere utilizzato per cross-sell, informazioni sul servizio clienti o badge di fiducia. |
| `displayAfterProductThumbs` | Renderizza il contenuto immediatamente dopo le miniature delle immagini del prodotto. | N/A | Ottimo per brevi punti salienti del prodotto, brevi video o richiami a caratteristiche specifiche. |
| `displayProductAdditionalInfo` | Renderizza il contenuto all'interno del blocco di informazioni principali del prodotto, spesso vicino alla descrizione o alle caratteristiche. | N/A | Eccellente per specifiche dettagliate, istruzioni per l'uso o proposte di vendita uniche. |
| `displayProductPriceBlock` | Renderizza il contenuto vicino alla visualizzazione del prezzo del prodotto. | N/A | Utile per visualizzare opzioni di finanziamento, garanzie di prezzo o messaggi di sconto speciali. |
| `displayReassurance` | Renderizza il contenuto nel blocco di rassicurazione del prodotto, tipicamente vicino al pulsante "aggiungi al carrello". | N/A | Perfetto per badge di fiducia, informazioni sulla consegna, politiche di reso o icone di pagamento sicuro. |
| `displayFooterProduct` | Renderizza il contenuto nell'area del footer specifica del prodotto, di solito sotto i dettagli principali del prodotto. | N/A | Può essere utilizzato per dettagli estesi del prodotto, FAQ o recensioni dei clienti. |
| `actionProductOutOfStock` | Viene eseguito quando un prodotto esaurisce le scorte. | N/A | Consente di visualizzare messaggi o moduli specifici per prodotti esauriti. |
| `displayFooterBefore` | Renderizza il contenuto appena prima del footer principale del sito. | N/A | Adatto per promozioni dell'ultimo minuto o chiamate all'azione prima del footer. |
| `displayFooter` | Renderizza il contenuto nel footer generale del sito. | N/A | Per informazioni a livello di sito, ma può essere personalizzato per prodotto per elementi di footer unici. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Blocchi di contenuto della pagina prodotto", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda possiate avere riguardo alla funzionalità del modulo e all'integrazione con il vostro negozio PrestaShop.
