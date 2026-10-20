---
title: "Menu orizzontale superiore con dropdown - Manuale per il commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Menu orizzontale superiore con dropdown' di MyPresta.eu."
sidebar:
  label: "Menu orizzontale superiore con dropdown - Manuale per il commerciante e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Top horizontal menu with dropdowns su MyPresta.eu](https://mypresta.eu/modules/front-office-features/top-horizontal-menu-with-dropdowns.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/top-horizontal-menu-with-dropdowns/)
>
> ---


# Menu orizzontale superiore con dropdown

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste da PrestaShop stesso e dovrebbero essere disponibili su qualsiasi ambiente di hosting compatibile.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" per accedere alle impostazioni del modulo. Questa schermata ti permette di gestire gli elementi che appaiono nel tuo menu orizzontale superiore e di configurare la barra di ricerca.

La pagina di configurazione è divisa in due sezioni principali: **Voci di menu** e **Barra di ricerca**.

#### 2.1.1 Gestione delle voci di menu

Questa sezione ti permette di definire quali elementi appaiono nel tuo menu di navigazione principale. Puoi aggiungere link a categorie, pagine CMS, produttori, fornitori o URL personalizzati.

-   **Aggiunta di una nuova voce di menu:**

    -   **Etichetta:** Questo è il testo che verrà visualizzato nel tuo menu (ad esempio, "Nuovi arrivi", "Collezione estiva", "Chi siamo"). Puoi inserire etichette diverse per ogni lingua supportata dal tuo negozio.
        -   *Effetto del cambiamento:* Modifica direttamente il testo visibile della voce di menu per i clienti.
        -   *Valore consigliato:* Testo chiaro, conciso e descrittivo che rappresenti accuratamente la destinazione del link.
        -   *Scenario del commerciante:* Vuoi aggiungere un link alla tua pagina "Contattaci". Inseriresti "Contattaci" qui.
    -   **Link:** Questo è l'URL a cui punterà la voce di menu. Puoi selezionare da un elenco di categorie esistenti, pagine CMS, produttori o fornitori, oppure inserire un URL personalizzato.
        -   *Effetto del cambiamento:* Determina dove viene portato il cliente quando clicca su questa voce di menu.
        -   *Valore consigliato:* Assicurati sempre che il link sia valido e punti alla pagina corretta. Per le pagine interne, usa gli strumenti di selezione forniti. Per i link esterni, assicurati che l'URL completo (ad esempio, `https://example.com/blog`) sia inserito.
        -   *Scenario del commerciante:* Vuoi collegarti alla tua categoria "T-Shirt". Selezioneresti "T-Shirt" dal menu a discesa delle categorie. Se vuoi collegarti a un blog esterno, digiteresti l'URL completo del blog.
    -   **Nuova finestra:** Un interruttore (Sì/No) che determina se il link si apre in una nuova scheda o finestra del browser.
        -   *Quando abilitato (Sì):* Il link si aprirà in una nuova scheda, mantenendo aperta la pagina corrente del tuo negozio nella scheda originale.
        -   *Quando disabilitato (No):* Il link si aprirà nella stessa scheda, allontanando il cliente dalla pagina corrente.
        -   *Valore consigliato:* "Sì" per i link esterni (ad esempio, un blog, un profilo sui social media) per mantenere i clienti sul tuo negozio. "No" per i link interni (categorie, prodotti, pagine CMS) per mantenere un flusso di navigazione naturale all'interno del tuo sito.
        -   *Scenario del commerciante:* Ti stai collegando alla tua pagina Facebook. Imposta "Nuova finestra" su "Sì" in modo che i clienti possano facilmente tornare al tuo negozio.
-   **Gestione delle voci di menu esistenti:**

    -   Il modulo visualizza un elenco delle tue voci di menu attuali. Puoi trascinare e rilasciare gli elementi per riordinarli, il che influisce direttamente sul loro ordine di visualizzazione nel front office.
    -   Puoi cliccare su "Modifica" per modificare l'etichetta, il link o l'impostazione della nuova finestra di un elemento esistente.
    -   Puoi cliccare su "Elimina" per rimuovere un elemento dal menu.
        -   *Effetto dei cambiamenti:* Riordinare, modificare o eliminare gli elementi aggiorna immediatamente la struttura e l'aspetto del menu sul tuo negozio live.
        -   *Flusso di lavoro consigliato:* Rivedi regolarmente la struttura del tuo menu per assicurarti che sia logica e aggiornata. Dai priorità a categorie o promozioni importanti posizionandole prima nel menu.

#### 2.1.2 Configurazione della barra di ricerca

Questa sezione controlla la visibilità della barra di ricerca all'interno del tuo menu superiore.

-   **Barra di ricerca:** Un interruttore (Abilitato/Disabilitato) per mostrare o nascondere la barra di ricerca.
    -   *Quando abilitato (Abilitato):* Un campo di input di ricerca apparirà all'interno o vicino al tuo menu orizzontale superiore, consentendo ai clienti di cercare rapidamente i prodotti.
    -   *Quando disabilitato (Disabilitato):* La barra di ricerca sarà nascosta dall'area del menu superiore.
    -   *Valore consigliato:* "Abilitato". Una barra di ricerca è uno strumento di navigazione cruciale per la maggior parte dei negozi di e-commerce, specialmente quelli con un ampio catalogo di prodotti. Migliora significativamente l'esperienza utente.
    -   *Scenario del commerciante:* Vuoi che i clienti trovino facilmente i prodotti digitando parole chiave. Abilita questa impostazione. Se il tuo negozio è molto piccolo con solo pochi prodotti, potresti considerare di disabilitarla per risparmiare spazio, ma questo non è generalmente consigliato.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | **Voci di menu** |  |  |
|  | Etichetta | N/A | Testo visualizzato per la voce di menu. |
|  | Link | N/A | URL a cui punta la voce di menu. |
|  | Nuova finestra | No (per link interni), Sì (per link esterni) | Determina se il link si apre in una nuova scheda. |
|  | Riordino | N/A | Modifica l'ordine di visualizzazione delle voci di menu. |
|  | Modifica/Elimina | N/A | Modifica o rimuove le voci di menu esistenti. |
| Pagina di configurazione del modulo | **Barra di ricerca** | Abilitato | Mostra/nasconde il campo di input di ricerca nel menu superiore. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Le modifiche al mio menu non vengono visualizzate nel front office.**
R: Dopo aver apportato modifiche nella configurazione del modulo, potrebbe essere necessario svuotare la cache di PrestaShop.
-   Vai su **Parametri avanzati > Prestazioni**.
-   Clicca sul pulsante "Svuota la cache" nell'angolo in alto a destra.
-   Inoltre, svuota la cache del tuo browser (Ctrl+F5 o Cmd+R) per assicurarti di visualizzare l'ultima versione del tuo sito.

**D2: I dropdown hanno un aspetto strano o non appaiono correttamente con il mio tema personalizzato.**
R: Questo modulo modifica il menu superiore standard di PrestaShop. I temi personalizzati spesso hanno il proprio CSS specifico (stile) per il menu.
-   **Soluzione:** Il modulo include il proprio CSS per abilitare i dropdown. Il CSS del tuo tema potrebbe sovrascriverlo o entrare in conflitto. Potrebbe essere necessario un web developer per ispezionare il CSS e regolare gli stili del tuo tema o gli stili del modulo per garantire la compatibilità.
-   **Controllo temporaneo:** Prova a passare temporaneamente al tema predefinito di PrestaShop (ad esempio, Classic) per vedere se i dropdown funzionano lì. Se lo fanno, conferma un conflitto CSS legato al tema.

**D3: Come posso tradurre le etichette delle voci del mio menu in altre lingue?**
R: Quando aggiungi o modifichi una voce di menu, vedrai un selettore di lingua accanto al campo "Etichetta".
-   Clicca sull'icona della bandiera per passare a una lingua diversa.
-   Inserisci l'etichetta tradotta per quella lingua specifica.
-   Ripeti per tutte le lingue supportate dal tuo negozio.

**D4: Posso avere più livelli di dropdown (ad esempio, Categoria > Sottocategoria > Sotto-sottocategoria)?**
R: Il modulo migliora il menu standard di PrestaShop, che tipicamente supporta uno o due livelli di dropdown in modo efficace. Sebbene sia tecnicamente possibile annidare gli elementi, troppi livelli possono diventare ingombranti per gli utenti.
-   **Migliore pratica:** Punta a un massimo di due livelli (voce principale > voci dropdown). Per gerarchie più profonde, considera l'utilizzo di pagine di destinazione delle categorie o della navigazione a faccette sulle pagine delle categorie piuttosto che menu dropdown eccessivamente complessi.

**D5: La barra di ricerca è abilitata, ma non viene visualizzata.**
R:
-   Innanzitutto, assicurati che l'impostazione "Barra di ricerca" nella configurazione del modulo sia effettivamente "Abilitata".
-   In secondo luogo, controlla se il tuo tema ha un hook o uno stile specifico per la barra di ricerca nell'intestazione. Alcuni temi potrebbero posizionare la barra di ricerca in una posizione diversa o richiedere una configurazione specifica all'interno del tema stesso.
-   Se il problema persiste, svuota la cache (come descritto nella D1).

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata del modulo "Menu orizzontale superiore con dropdown" per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo `blocktopdropdownmenu` è progettato come un modulo PrestaShop standard, estendendo principalmente la funzionalità del modulo core `blocktopmenu` (o il suo equivalente nelle versioni più recenti di PS) iniettando JavaScript e CSS personalizzati per abilitare il comportamento dropdown. Segue un classico pattern MVC di PrestaShop per la sua configurazione, utilizzando `getContent()` per il form del back-office e registrando hook per la visualizzazione del front-office. Non introduce nuove tabelle di database o complesse strutture `ObjectModel`, ma si basa sui valori di `Configuration` per memorizzare le sue impostazioni e sfrutta le entità PrestaShop esistenti (Categorie, CMS, ecc.) per i link delle voci di menu.

### 4.2 Controller (`controllers/`)

Questo modulo non introduce alcun controller Front-Office o Back-Office Admin personalizzato. Tutta la configurazione è gestita all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e modelli core (`classes/`)

Questo modulo non introduce alcuna classe PHP personalizzata o definizioni `ObjectModel` nella directory `classes/`. Tutta la logica è contenuta all'interno del file principale `blocktopdropdownmenu.php`.

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo si basa fortemente su JavaScript per creare la funzionalità del menu a discesa.

-   `blocktopdropdownmenu/js/blocktopdropdownmenu.js`
    -   **Ambito:** Front-office.
    -   **Responsabilità:** Questo è lo script di inizializzazione principale per il menu a discesa. Probabilmente contiene la logica per applicare il plugin Superfish (o una libreria dropdown simile) all'elemento di navigazione principale. Lega i listener di eventi per gli intenti di hover, gestisce l'espansione/compressione delle voci di menu e garantisce la reattività mobile (ad esempio, convertendo l'hover in tap per i dispositivi touch o integrandosi con un menu hamburger). Potrebbe anche contenere la logica per il comportamento della barra di ricerca se viene caricata o attivata dinamicamente.
-   `blocktopdropdownmenu/js/hoverIntent.js`
    -   **Ambito:** Front-office.
    -   **Responsabilità:** Un plugin jQuery che tenta di determinare l'intento dell'utente di passare il mouse su un elemento. Aiuta a prevenire l'attivazione accidentale dei dropdown introducendo un ritardo e controllando il movimento del mouse, rendendo il menu più fluido e meno "sfarfallante". Questa è tipicamente una dipendenza per Superfish.
-   `blocktopdropdownmenu/js/superfish-modified.js`
    -   **Ambito:** Front-office.
    -   **Responsabilità:** Questa è probabilmente una versione modificata del popolare plugin jQuery Superfish, progettato per creare menu a discesa multilivello. Gestisce i meccanismi principali di visualizzazione e nascondimento dei sottomenu al passaggio del mouse, gestendo le animazioni e potenzialmente aggiungendo funzionalità di accessibilità. Il suffisso "modified" suggerisce che potrebbe includere adattamenti personalizzati per la struttura DOM di PrestaShop o una specifica compatibilità con il tema.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo fornisce lo stile per presentare visivamente i menu a discesa.

-   `blocktopdropdownmenu/css/blocktopdropdownmenu.css`
    -   **Ambito:** Stile del cliente del front-office.
    -   **Responsabilità:** Contiene regole CSS personalizzate specifiche per questo modulo, potenzialmente sovrascrivendo gli stili predefiniti del tema o aggiungendo nuovi stili per elementi come la barra di ricerca, stati specifici delle voci di menu o regolazioni generali del layout per i dropdown.
    -   **Selettori di classe CSS chiave:** Gli sviluppatori dovrebbero ispezionare questo file per classi come `.sf-menu`, `.sf-menu li`, `.sf-menu li ul`, `.sf-menu li li`, ecc., che sono selettori Superfish comuni, così come qualsiasi classe personalizzata introdotta dal modulo.
-   `blocktopdropdownmenu/css/superfish-modified.css`
    -   **Ambito:** Stile del cliente del front-office.
    -   **Responsabilità:** Fornisce lo stile visivo di base per la struttura del menu a discesa Superfish. Questo include stili per la spaziatura delle voci di menu, i colori di sfondo, i colori del testo, gli effetti hover, gli indicatori delle frecce a discesa e il posizionamento dei pannelli a discesa. È cruciale per l'aspetto visivo del menu multilivello.
    -   **Selettori di classe CSS chiave:** Similmente a `blocktopdropdownmenu.css`, questo file conterrà i selettori Superfish core. Gli sviluppatori possono sovrascriverli nel `custom.css` o `theme.css` del loro tema per adattarli all'estetica del loro marchio.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   `blocktopdropdownmenu/blocktopdropdownmenu.tpl`
    -   **Ambito:** Template hook.
    -   **Hook:** `displayTop` (e potenzialmente `displayNav` se la struttura del tema lo consente).
    -   **Responsabilità:** Questo è il template principale del front-office responsabile del rendering della struttura HTML del menu orizzontale superiore, incluse le voci di menu principali e i loro dropdown annidati. Itera attraverso le voci di menu configurate nel back office e genera la struttura `<ul><li>` richiesta dal JavaScript Superfish. Include anche la logica per il rendering della barra di ricerca se abilitata.
-   `blocktopdropdownmenu/views/templates/admin/advert.tpl`
    -   **Ambito:** Template admin.
    -   **Responsabilità:** Probabilmente visualizza una pubblicità o un messaggio promozionale da MyPresta.eu all'interno della pagina di configurazione del modulo nel Back Office.
-   `blocktopdropdownmenu/views/templates/admin/_configure/helpers/form/form.tpl`
    -   **Ambito:** Template admin.
    -   **Responsabilità:** Questo template è un template helper standard di PrestaShop utilizzato per renderizzare il form di configurazione principale per il modulo. Definisce la struttura e i campi per la gestione delle voci di menu e l'impostazione della barra di ricerca, come configurato in `getContent()`.
-   `blocktopdropdownmenu/views/templates/admin/_configure/helpers/list/list_content.tpl`
    -   **Ambito:** Template admin.
    -   **Responsabilità:** Questo template è un template helper standard di PrestaShop utilizzato per renderizzare l'elenco delle voci di menu all'interno del form di configurazione, consentendo il riordino tramite drag-and-drop, la modifica e l'eliminazione.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Questo modulo non crea tabelle di database personalizzate.
    -   Le impostazioni di configurazione (ad esempio, `MOD_blocktopdropdownmenu_ITEMS`, `MOD_blocktopdropdownmenu_SEARCH`) sono memorizzate nella tabella `ps_configuration`. `MOD_blocktopdropdownmenu_ITEMS` memorizzerà un array serializzato o una stringa JSON che rappresenta la struttura del menu.
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Inietta risorse CSS e JavaScript (`blocktopdropdownmenu.js`, `hoverIntent.js`, `superfish-modified.js`, `blocktopdropdownmenu.css`, `superfish-modified.css`) richieste per la funzionalità dropdown. |
| `displayTop` | Tipicamente nell'area dell'intestazione principale del tema. | Renderizza la struttura HTML principale del menu orizzontale con dropdown e la barra di ricerca. |
| `displayNav` | Spesso nella barra di navigazione superiore (sopra `displayTop`). | Può essere utilizzato da alcuni temi per visualizzare il menu, o per elementi di navigazione aggiuntivi. Il modulo potrebbe registrarsi qui per una più ampia compatibilità con i temi. |
| `actionObjectProductUpdateAfter` | Dopo l'aggiornamento di un prodotto. | Potenzialmente utilizzato per svuotare la cache del modulo relativa ai link dei prodotti, garantendo che le voci di menu che si collegano ai prodotti siano aggiornate. |
| `actionObjectProductDeleteAfter` | Dopo l'eliminazione di un prodotto. | Potenzialmente utilizzato per svuotare la cache del modulo o rimuovere le voci di menu che si collegano al prodotto eliminato. |
| `actionObjectManufacturerAddAfter` | Dopo l'aggiunta di un produttore. | Potenzialmente utilizzato per svuotare la cache del modulo relativa ai link dei produttori. |
| `actionObjectManufacturerUpdateAfter` | Dopo l'aggiornamento di un produttore. | Potenzialmente utilizzato per svuotare la cache del modulo relativa ai link dei produttori. |
| `actionObjectManufacturerDeleteAfter` | Dopo l'eliminazione di un produttore. | Potenzialmente utilizzato per svuotare la cache del modulo o rimuovere le voci di menu che si collegano al produttore eliminato. |
| `actionObjectSupplierAddAfter` | Dopo l'aggiunta di un fornitore. | Potenzialmente utilizzato per svuotare la cache del modulo relativa ai link dei fornitori. |
| `actionObjectSupplierUpdateAfter` | Dopo l'aggiornamento di un fornitore. | Potenzialmente utilizzato per svuotare la cache del modulo relativa ai link dei fornitori. |
| `actionObjectSupplierDeleteAfter` | Dopo l'eliminazione di un fornitore. | Potenzialmente utilizzato per svuotare la cache del modulo o rimuovere le voci di menu che si collegano al fornitore eliminato. |
| `actionObjectCmsAddAfter` | Dopo l'aggiunta di una pagina CMS. | Potenzialmente utilizzato per svuotare la cache del modulo relativa ai link delle pagine CMS. |
| `actionObjectCmsUpdateAfter` | Dopo l'aggiornamento di una pagina CMS. | Potenzialmente utilizzato per svuotare la cache del modulo relativa ai link delle pagine CMS. |
| `actionObjectCmsDeleteAfter` | Dopo l'eliminazione di una pagina CMS. | Potenzialmente utilizzato per svuotare la cache del modulo o rimuovere le voci di menu che si collegano alla pagina CMS eliminata. |
| `actionShopDataDuplication` | Quando un negozio viene duplicato (in contesto multi-negozio). | Assicura che la configurazione del modulo (voci di menu, impostazione della barra di ricerca) sia correttamente duplicata per il nuovo negozio. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Menu orizzontale superiore con dropdown", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere commercianti e sviluppatori con qualsiasi problema o domanda relativa alla funzionalità e compatibilità del modulo.
