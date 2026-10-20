---
title: "Pagine prodotto protette da password - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Pagine prodotto protette da password di MyPresta.eu."
sidebar:
  label: "Pagine prodotto protette da password"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Password protected product pages su MyPresta.eu](https://mypresta.eu/modules/front-office-features/password-protected-product-pages.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/password-protected-product-pages/)
>
> ---


# Pagine prodotto protette da password

## 1. Requisiti e Compatibilità
- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)
Questa è la schermata di configurazione principale per il modulo, accessibile cliccando su "Configura" dopo l'installazione o dal Gestore moduli.

- **Cosa fa questa impostazione:** Questa schermata contiene tipicamente le impostazioni generali per il modulo, anche se per "Pagine prodotto protette da password", la gestione primaria delle password per prodotti specifici è gestita in una schermata di amministrazione dedicata (vedi 4.2). Questa schermata potrebbe offrire opzioni per l'aspetto della pagina di inserimento della password o il comportamento generale del modulo.
- **Effetto della modifica di questa impostazione:** Qualsiasi modifica qui influenzerebbe il modo in cui il meccanismo di protezione della password si comporta globalmente, o l'aspetto predefinito del modulo di inserimento della password.
- **Valore consigliato:** I valori predefiniti sono solitamente un buon punto di partenza.
- **Scenario / esempio del commerciante:** Se c'è un'opzione per personalizzare il messaggio mostrato sulla pagina della password, potresti cambiarlo da "Inserisci password" a "Inserisci il tuo codice di accesso VIP".

### 2.2 Schermata di amministrazione dedicata: Password prodotto (Back Office > Catalogo > Password prodotto)
Questa è la schermata più importante per gestire quali prodotti sono protetti da password e quali sono queste password. Troverai questa nuova voce di menu sotto **Catalogo** nel tuo Back Office di PrestaShop.

- **Nome schermata e posizione menu:** **Catalogo > Password prodotto**
- **Azioni e impostazioni disponibili:**
    -   **Tabella di elenco:** Questa schermata visualizza un elenco di tutti i prodotti che attualmente hanno una password assegnata. Tipicamente vedrai colonne come:
        -   **Nome prodotto:** Il nome del prodotto protetto.
        -   **ID prodotto:** L'identificatore univoco del prodotto.
        -   **Password:** La password richiesta per accedere alla pagina del prodotto.
        -   **Azioni:** Pulsanti per "Modifica" o "Elimina" la password per un prodotto specifico.
    -   **Aggiungi nuova password:** Ci sarà un pulsante (es. "Aggiungi nuova password prodotto" o un'icona più) per aggiungere una nuova voce di protezione password. Quando clicchi su questo, ti verrà tipicamente presentato un modulo:
        -   **Selettore prodotto:** Un campo per cercare e selezionare il prodotto che desideri proteggere. Questo potrebbe essere un campo di autocompletamento in cui digiti il nome del prodotto.
        -   **Campo password:** Un campo di input in cui definisci la password per quel prodotto specifico.
    -   **Modifica password:** Cliccando su "Modifica" accanto a una voce esistente ti consente di cambiare la password per quel prodotto o potenzialmente cambiare il prodotto associato.
    -   **Elimina password:** Cliccando su "Elimina" rimuove la protezione password da quel prodotto, rendendolo nuovamente accessibile pubblicamente.
- **Effetto delle modifiche:**
    -   **Aggiunta di una password:** La pagina del prodotto selezionato diventerà immediatamente protetta da password nel front office.
    -   **Modifica di una password:** I clienti dovranno utilizzare la nuova password per accedere alla pagina del prodotto.
    -   **Eliminazione di una password:** La pagina del prodotto tornerà ad essere accessibile pubblicamente senza alcun requisito di password.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Per proteggere un nuovo prodotto: Naviga su **Catalogo > Password prodotto**, clicca su "Aggiungi nuova password prodotto", seleziona il tuo prodotto e imposta una password forte e unica.
    2.  Per aggiornare una password: Trova il prodotto nell'elenco, clicca su "Modifica" e inserisci la nuova password.
    3.  Per rimuovere la protezione: Trova il prodotto nell'elenco e clicca su "Elimina".
    4.  Rivedi regolarmente i tuoi prodotti protetti per assicurarti che le password siano ancora pertinenti e sicure.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
|---|---|---|---|
| Pagina di configurazione del modulo | (Impostazioni generali, se presenti) | (Predefinito del modulo) | Comportamento globale o aspetto della pagina di inserimento della password. |
| Catalogo > Password prodotto | Aggiungi nuova password prodotto | N/A | Seleziona un prodotto e assegna una password per limitare l'accesso alla sua pagina. |
| Catalogo > Password prodotto | Modifica password prodotto | N/A | Modifica la password per un prodotto già protetto. |
| Catalogo > Password prodotto | Elimina password prodotto | N/A | Rimuovi la protezione con password, rendendo nuovamente pubblica la pagina del prodotto. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho impostato una password, ma la pagina del prodotto è ancora pubblica. Cosa c'è che non va?**
R1:
*   **Controlla l'inserimento della password:** Ricontrolla in **Catalogo > Password prodotto** che il prodotto sia elencato e la password sia impostata correttamente.
*   **Svuota la cache:** PrestaShop utilizza la cache. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" se disponibile). Questo assicura che il tuo negozio stia caricando l'ultima configurazione.
*   **Stato del modulo:** Assicurati che il modulo "Pagine prodotto protette da password" sia abilitato in **Moduli > Gestione moduli**.
*   **Stato del prodotto:** Assicurati che il prodotto stesso sia abilitato e visibile nel tuo catalogo.

**D2: Posso avere password diverse per prodotti diversi?**
R2: Sì, assolutamente! Il modulo è progettato per questo. Puoi assegnare una password unica a ogni singolo prodotto che desideri proteggere tramite la schermata **Catalogo > Password prodotto**.

**D3: Cosa succede se un cliente tenta di accedere a una pagina prodotto protetta direttamente tramite il suo URL senza la password?**
R3: Verrà reindirizzato alla pagina di inserimento della password. Non potrà visualizzare il contenuto del prodotto finché non inserirà la password corretta.

**D4: Come posso tradurre il testo sulla pagina di inserimento della password (es. "Inserisci password")?**
R4: Di solito puoi tradurre i testi del modulo tramite l'interfaccia di traduzione di PrestaShop. Vai su **Internazionale > Traduzioni**, seleziona "Traduzioni dei moduli installati", scegli il tuo tema e poi seleziona il modulo "Pagine prodotto protette da password". Dovresti trovare le stringhe di testo modificabili lì.

**D5: Questo modulo funzionerà con il mio tema personalizzato?**
R5: Il modulo è progettato per integrarsi perfettamente con i temi standard di PrestaShop. Tuttavia, i temi altamente personalizzati potrebbero richiedere piccole modifiche CSS per garantire che il modulo di inserimento della password abbia un aspetto perfetto. Se riscontri problemi di stile, consulta il tuo webmaster o lo sviluppatore del tema.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura
Il modulo "Pagine prodotto protette da password" opera principalmente sovrascrivendo il `ProductController` predefinito per intercettare le richieste di prodotti protetti. Utilizza un controller di amministrazione dedicato per gestire le associazioni prodotto-password, che vengono memorizzate nel database. La logica del front-office verifica la presenza di un cookie di sessione valido contenente la password per un dato prodotto prima di renderizzare la pagina del prodotto effettiva.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:
    *   `prodpswd/controllers/front/ProductPasswd.php`
        *   **Nome classe e classe genitore:** `ProductPasswdModuleFrontController` che estende `ModuleFrontController`.
        *   **Responsabilità:** Questo controller è probabilmente responsabile del rendering del modulo di input della password quando si accede a un prodotto protetto. Gestisce la richiesta POST quando un utente invia una password, la convalida rispetto alla password memorizzata per il prodotto e imposta una sessione o un cookie in caso di autenticazione riuscita per concedere l'accesso. Potrebbe anche gestire il reindirizzamento alla pagina del prodotto effettiva.
    *   `prodpswd/override/controllers/front/ProductController.php`
        *   **Nome classe e classe genitore:** `ProductController` (sovrascritto).
        *   **Responsabilità:** Questa è una sovrascrittura cruciale. Intercetta il metodo `init()` o `postProcess()` del `ProductController` principale. Prima che il contenuto standard della pagina del prodotto venga caricato, questa sovrascrittura verifica se il prodotto corrente è protetto da password e se l'utente ha già fornito la password corretta (ad esempio, tramite un cookie di sessione). Se il prodotto è protetto e non viene trovata una password valida, reindirizza l'utente al `ProductPasswdModuleFrontController` (o renderizza direttamente il suo template) per richiedere la password.

-   **Controller Amministrativi Back-Office**:
    *   `prodpswd/controllers/admin/AdminProdPasswordController.php`
        *   **Nome tab e entità gestita:** Accessibile tramite **Catalogo > Password prodotto**. Gestisce le entità `prodpassword` (ID prodotto e password associata).
        *   **Responsabilità:** Questo è un `AdminController` standard responsabile delle operazioni CRUD (Crea, Leggi, Aggiorna, Elimina) per le associazioni prodotto-password. Visualizza l'elenco dei prodotti protetti, consente agli amministratori di aggiungere nuove voci prodotto-password, modificare le password esistenti ed eliminarle. Probabilmente utilizza `HelperList` per la visualizzazione a griglia e `HelperForm` per i moduli di aggiunta/modifica.
    *   `prodpswd/controllers/admin/index.php`
        *   **Responsabilità:** Questo file è tipicamente un file `index.php` vuoto posizionato nelle sottodirectory dei moduli PrestaShop per impedire l'elenco delle directory, migliorando la sicurezza. Non contiene alcuna logica funzionale del controller.

### 4.3 Classi e Modelli Core (`classes/`)
Il dossier del modulo non indica classi personalizzate nella directory `classes/`. L'entità `prodpassword` è probabilmente gestita direttamente da `AdminProdPasswordController` utilizzando una semplice definizione di `ObjectModel` all'interno del file principale del modulo o del controller stesso, oppure potrebbe interagire direttamente con `Configuration` o una tabella personalizzata senza un `ObjectModel` dedicato. Data la gestione di una tabella `prodpassword` da parte di `AdminProdPasswordController`, è altamente probabile che esista un `ObjectModel` definito per essa, anche se non in una cartella `classes/` separata.

### 4.4 Risorse JavaScript (`views/js/`)
Il dossier del modulo non indica file JavaScript personalizzati. Il modulo della password del front-office e la griglia/modulo del back-office dovrebbero basarsi su JS standard di PrestaShop o semplici invii di moduli HTML.

### 4.5 Fogli di stile CSS (`views/css/`)
Il dossier del modulo non indica file CSS personalizzati. Lo stile per la pagina di inserimento della password nel front office e i moduli di amministrazione erediteranno probabilmente dal tema PrestaShop attivo e dagli stili del back office.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**:
    *   Non sono elencati template hook specifici, suggerendo che il modulo opera principalmente tramite override del controller e template front-office dedicati piuttosto che iniettare contenuto in hook standard.
-   **Template admin (`views/templates/admin/`)**:
    *   Non sono elencati template admin specifici. L'`AdminProdPasswordController` probabilmente utilizza i template standard `HelperList` e `HelperForm` di PrestaShop per la sua interfaccia.
-   **Template front-office (`views/templates/front/`)**:
    *   `prodpswd/views/templates/front/product.tpl`
        *   **Scopo:** Questo template è probabilmente il modulo di inserimento password personalizzato visualizzato ai clienti quando tentano di accedere a una pagina prodotto protetta. Contiene la struttura HTML per il campo di input della password, il pulsante di invio e qualsiasi messaggio di accompagnamento (ad esempio, "Inserisci la password per visualizzare questo prodotto").
    *   `prodpswd/lib/searchTool/views/scripts.tpl`
        *   **Scopo:** Questo template contiene probabilmente logica JavaScript o Smarty relativa a uno strumento di ricerca, possibilmente utilizzato all'interno della configurazione amministrativa per selezionare i prodotti da proteggere. Potrebbe includere chiamate AJAX o funzionalità di filtraggio dinamico per la selezione dei prodotti.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    *   `ps_prodpassword` (o simile): Questa tabella personalizzata dovrebbe memorizzare l'ID del prodotto (`id_product`) e la password associata (`password`) per ogni prodotto protetto. Viene creata durante il metodo `install()` del modulo.
    *   Record di configurazione in `ps_configuration`: Le impostazioni generali del modulo (se presenti) verrebbero memorizzate qui.

-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
|---|---|---|
| `actionFrontControllerSetMedia` | Prima del caricamento dei media (JS/CSS) di un controller frontale. | Potenzialmente per caricare JS/CSS personalizzati per il modulo password, anche se nessuno è elencato nel dossier. |
| `displayHeader` | Nella sezione `<head>` del front office. | Potrebbe essere utilizzato per meta tag o JS/CSS condizionali, ma non esplicitamente per il contenuto. |
| `displayRightColumn` | Nella colonna destra del front office. | Non direttamente utilizzato per la funzionalità principale del modulo. |
| `displayLeftColumn` | Nella colonna sinistra del front office. | Non direttamente utilizzato per la funzionalità principale del modulo. |
| `displayFooter` | Nel piè di pagina del front office. | Non direttamente utilizzato per la funzionalità principale del modulo. |
| `actionProductControllerSetMedia` | Dopo che il `ProductController` ha impostato i suoi media. | Potrebbe essere utilizzato per iniettare JS/CSS specifici per la pagina del prodotto, ma improbabile data la sovrascrittura. |
| `actionDispatcherBefore` | Prima che un controller frontale venga inviato. | L'`override/controllers/front/ProductController.php` agisce efficacemente in questa fase per le pagine dei prodotti. |
| `actionDispatcherAfter` | Dopo che un controller frontale è stato inviato. | Meno probabile per la funzionalità principale di questo modulo. |

Il meccanismo principale di questo modulo è l'override del `ProductController`, che agisce come un hook implicito, intercettando le richieste prima che gli hook standard vengano elaborati per il contenuto della pagina del prodotto.

## 5. Supporto Ufficiale e Aggiornamenti
Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Pagine prodotto protette da password", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda possiate avere.
