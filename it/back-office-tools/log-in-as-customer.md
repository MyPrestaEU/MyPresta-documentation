---
title: "Accedi come cliente - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Accedi come cliente di MyPresta.eu."
sidebar:
  label: "Accedi come cliente - Manuale del commerciante e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Log in as customer su MyPresta.eu](https://mypresta.eu/modules/administration-tools/log-in-as-customer.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/log-in-as-customer/)
>
> ---


# Accedi come cliente

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono generalmente sufficienti. Di solito non sono necessarie configurazioni speciali del server.

## 2. Panoramica completa della configurazione (ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Il modulo "Accedi come cliente" ha una configurazione molto semplice. Dopo l'installazione, quando clicchi su "Configura", verrai portato a una schermata semplice.

**Nome schermata e posizione menu:** Back Office > Moduli > Gestione moduli > Accedi come cliente > Configura

Su questa schermata, troverai tipicamente una semplice conferma che il modulo è installato e pronto. La funzionalità principale di questo modulo è integrata direttamente nella tua lista clienti, piuttosto che richiedere impostazioni estese su una pagina di configurazione dedicata.

-   **Cosa fa questa schermata:** Questa pagina conferma l'installazione del modulo e fornisce informazioni di base o collegamenti rapidi. Per "Accedi come cliente", il suo scopo principale è confermare che il modulo è attivo e pronto all'uso.
-   **Effetto della modifica delle impostazioni:** Non ci sono impostazioni complesse da modificare qui. La funzionalità del modulo è attivata al momento dell'installazione.
-   **Valore consigliato:** Nessun valore specifico da impostare. Assicurati solo che il modulo sia installato e abilitato.
-   **Scenario / esempio del commerciante:** Dopo l'installazione, vedrai un messaggio che conferma che il modulo è attivo. Puoi quindi procedere direttamente alla sezione Clienti del tuo Back Office per utilizzare le sue funzionalità.

### 2.2 Utilizzo della funzionalità "Accedi come cliente"

La funzionalità principale di questo modulo è accessibile direttamente dalla tua lista clienti di PrestaShop.

**Nome schermata e posizione menu:** Back Office > Clienti > Clienti

1.  **Naviga a Clienti:** Nel tuo Back Office di PrestaShop, vai al menu **Clienti** e poi clicca su **Clienti**.
2.  **Individua il cliente:** Trova il cliente con cui desideri accedere nella lista clienti. Puoi utilizzare le opzioni di ricerca e filtro per individuarlo rapidamente.
3.  **Clicca sul pulsante "Accedi come cliente":** Per ogni cliente nella lista, ora vedrai un pulsante aggiuntivo (spesso un'icona come una persona o una chiave, o un pulsante di testo) nella colonna "Azioni". Questo pulsante è aggiunto dal modulo "Accedi come cliente".
    -   **Cosa fa questo pulsante:** Quando clicchi su questo pulsante, il modulo esegue un processo di accesso sicuro. Ti disconnette dal tuo account amministratore (temporaneamente) e poi ti connette come il cliente selezionato.
    -   **Effetto del clic su questo pulsante:** Verrai immediatamente reindirizzato al front office del tuo negozio. Vedrai il negozio esattamente come lo vede quel cliente, inclusi il suo carrello attivo, la cronologia degli ordini, gli indirizzi e qualsiasi contenuto o prezzo personalizzato.
    -   **Scenario / esempio del commerciante:** Un cliente segnala un problema nell'aggiungere un prodotto specifico al carrello. Vai su "Clienti", trovi il suo nome, clicchi su "Accedi come cliente" e vieni immediatamente portato al front office come lui. Puoi quindi provare ad aggiungere il prodotto tu stesso, risolvere il problema o verificare il contenuto del suo carrello.
4.  **Disconnessione come cliente:** Per tornare alla tua sessione di amministratore del Back Office, semplicemente disconnettiti dal front office (come se fossi un cliente normale). Questo terminerà la sessione del cliente e potrai quindi accedere nuovamente al tuo Back Office.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | (Nessuna impostazione diretta) | N/A | Conferma l'installazione e la prontezza del modulo. |
| Lista clienti (Back Office) | Pulsante "Accedi come cliente" | N/A | Consente l'accesso istantaneo al front office come cliente selezionato per la risoluzione dei problemi e i test. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho installato il modulo, ma non vedo il pulsante "Accedi come cliente" nella lista clienti.**
R:

1.  **Svuota cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti).
2.  **Stato del modulo:** Assicurati che il modulo sia abilitato. Vai su **Moduli > Gestione moduli**, cerca "Accedi come cliente" e verifica che sia attivo.
3.  **Compatibilità del tema:** Sebbene raro, alcuni temi pesantemente personalizzati potrebbero interferire con la visualizzazione di nuovi pulsanti. Se il problema persiste, contatta il supporto MyPresta.eu.
4.  **Versione PrestaShop:** Assicurati di aver scaricato la versione corretta del modulo per la tua installazione di PrestaShop.

**D: Quando clicco sul pulsante, vengo reindirizzato al front office, ma non sono loggato come cliente.**
R:

1.  **Cookie del browser:** Assicurati che il tuo browser accetti i cookie. Prova a cancellare la cache e i cookie del tuo browser, quindi riprova.
2.  **Configurazione della sessione:** Controlla il file `config/defines.inc.php` del tuo PrestaShop per le impostazioni `_PS_COOKIE_DOMAIN_` e `_PS_COOKIE_PATH_`. Assicurati che siano configurate correttamente per il tuo dominio.
3.  **Configurazione del server:** Verifica che le impostazioni della sessione PHP del tuo server siano standard e non eccessivamente restrittive.

**D: Posso accedere come cliente e poi eseguire azioni come effettuare un ordine per loro?**
R: Sì, puoi. Tuttavia, esercita estrema cautela. Ottieni sempre un permesso esplicito dal cliente prima di eseguire qualsiasi azione per suo conto, specialmente effettuare ordini o modificare dati personali. È generalmente buona pratica utilizzare questa funzione per la visualizzazione e la risoluzione dei problemi, non per apportare modifiche senza consenso.

**D: È sicuro usare questo modulo? Memorizza le password dei clienti?**
R: Il modulo non memorizza né accede alle password dei clienti. Utilizza la gestione interna delle sessioni di PrestaShop per simulare un accesso cliente, in modo simile a come funziona la funzionalità "Password dimenticata" di PrestaShop generando una sessione temporanea sicura. È progettato per essere sicuro.

**D: Cosa succede se accedo come cliente e poi chiudo il browser senza disconnettermi?**
R: La sessione del cliente scadrà alla fine in base alle impostazioni di timeout della sessione del tuo PrestaShop. Per tornare al tuo pannello di amministrazione, dovrai semplicemente navigare all'URL del tuo Back Office e accedere nuovamente come amministratore.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Accedi come cliente" (`lac`) è un modulo PrestaShop leggero, principalmente focalizzato sull'estensione della funzionalità della lista clienti del Back Office. Sfrutta le classi `Customer` e `Context` del core di PrestaShop per gestire le sessioni utente e il reindirizzamento. Il modulo inietta JavaScript nel Back Office per aggiungere il pulsante "Accedi come cliente" e utilizza un front controller dedicato per gestire il processo di accesso sicuro e il reindirizzamento al front office. Segue un'architettura standard dei moduli PrestaShop, integrandosi senza problemi senza tabelle di database personalizzate o modelli di oggetti complessi.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `lac/controllers/front/index.php`
        -   **Nome classe**: `LacIndexModuleFrontController` (probabilmente, basato sulla convenzione di denominazione dei file)
        -   **Classe genitore**: `ModuleFrontController`
        -   **Responsabilità**: Questo controller probabilmente funge da punto di atterraggio o da fallback. Dato il controller `login.php`, `index.php` potrebbe essere meno critico o gestire la configurazione iniziale/reindirizzamento se `login.php` è il gestore delle azioni primario. Potrebbe anche essere un segnaposto.
    -   `lac/controllers/front/login.php`
        -   **Nome classe**: `LacLoginModuleFrontController` (probabilmente)
        -   **Classe genitore**: `ModuleFrontController`
        -   **Responsabilità**: Questo è il controller principale per la funzionalità "Accedi come cliente".
            -   Riceve l'ID del cliente tramite un parametro GET o POST dal Back Office.
            -   Esegue i passaggi necessari per disconnettere la sessione dell'amministratore corrente.
            -   Quindi accede in modo sicuro al cliente specificato manipolando gli oggetti `Context` e `Customer` (ad esempio, `Context::getContext()->customer = new Customer($id_customer); Context::getContext()->cookie->id_customer = $id_customer;`).
            -   Quindi reindirizza il browser alla homepage del front office o a una pagina specifica relativa al cliente (`my-account`, `history`, ecc.).
-   **Controller Admin Back-Office**:

    -   Nessuno. Il modulo si integra direttamente nella vista del controller `AdminCustomers` esistente tramite hook e JavaScript.

### 4.3 Classi e modelli principali (`classes/`)

-   Nessuno. Questo modulo non introduce classi `ObjectModel` personalizzate o tabelle di database. Opera direttamente sugli oggetti `Customer` e `Context` nativi di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

Questi file JavaScript sono responsabili dell'iniezione del pulsante "Accedi come cliente" nella lista clienti del Back Office e della gestione dell'evento click per avviare il processo di accesso. I diversi nomi dei file suggeriscono aggiustamenti di compatibilità per varie versioni di PrestaShop.

-   `lac/views/js/16customers.js`
    -   **Ambito**: Back-office (lista `AdminCustomers` di PrestaShop 1.6.x).
    -   **Funzionalità**: Questo script si rivolge alla tabella della lista clienti in PrestaShop 1.6.x. Probabilmente utilizza selettori jQuery per trovare la colonna "Azioni" per ogni riga del cliente e aggiunge un nuovo pulsante o link. Il gestore del click per questo pulsante costruirà quindi un URL che punta al front controller del modulo (`lac/controllers/front/login.php`) con l'ID del cliente e reindirizzerà il browser.
-   `lac/views/js/176orders.js`
    -   **Ambito**: Back-office (vista ordini di PrestaShop 1.7.6.x).
    -   **Funzionalità**: Questo script potrebbe essere destinato ad aggiungere un pulsante "Accedi come cliente" direttamente dalla vista ordini in 1.7.6.x, consentendo un accesso rapido al cliente associato a un ordine specifico. Estrarrebbe l'ID del cliente dalla pagina dei dettagli dell'ordine e lo utilizzerebbe per il reindirizzamento all'accesso.
-   `lac/views/js/177orders.js`
    -   **Ambito**: Back-office (vista ordini di PrestaShop 1.7.7.x+).
    -   **Funzionalità**: Simile a `176orders.js`, ma adattato per potenziali modifiche DOM o diverse strutture di tabella in PrestaShop 1.7.7.x e versioni successive della vista ordini.
-   `lac/views/js/17carts.js`
    -   **Ambito**: Back-office (vista carrello di PrestaShop 1.7.x).
    -   **Funzionalità**: Questo script probabilmente aggiunge il pulsante "Accedi come cliente" alla pagina dei dettagli del carrello del Back Office, consentendo a un amministratore di accedere come il cliente associato a un carrello specifico.
-   `lac/views/js/17customersview.js`
    -   **Ambito**: Back-office (lista `AdminCustomers` di PrestaShop 1.7.x, 8.x, 9.x).
    -   **Funzionalità**: Questo è lo script principale per l'iniezione del pulsante nella lista clienti per le versioni moderne di PrestaShop. Si rivolgerà alla lista `AdminCustomers`, identificherà l'ID del cliente per ogni riga e aggiungerà il pulsante di azione "Accedi come cliente". Utilizza la delega degli eventi per gestire i click su questi pulsanti aggiunti dinamicamente, costruendo l'URL appropriato per il controller `lac/controllers/front/login.php`.

### 4.5 Fogli di stile CSS (`views/css/`)

-   Nessuno. Il modulo non include file CSS personalizzati. Probabilmente si basa sullo stile predefinito di PrestaShop per i pulsanti o utilizza stili in linea se necessario, oppure il pulsante è stilizzato dal tema del Back Office stesso.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   Nessuno. Il modulo non utilizza template Smarty personalizzati. La sua integrazione nel Back Office avviene puramente tramite iniezione JavaScript, e l'accesso al front-office è gestito tramite reindirizzamento diretto dal controller.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    -   Il modulo non crea tabelle di database personalizzate. Memorizza la sua configurazione (se presente, anche se nessuna è stata esplicitamente identificata oltre allo stato base del modulo) nella tabella standard `ps_configuration`.
-   **Tabella degli hook registrati**:

| Nome dell'Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayBackOfficeHeader` | Eseguito nella sezione `<head>` di ogni pagina del Back Office. | Utilizzato per includere i file JavaScript necessari (`16customers.js`, `17customersview.js`, ecc.) nel Back Office, specificamente quando il controller `AdminCustomers` è attivo. Questo assicura che il pulsante "Accedi come cliente" venga aggiunto alla lista clienti. |
| `displayAdminCustomers` | Eseguito sulla pagina del controller `AdminCustomers`. | Questo hook è specificamente progettato per i moduli per aggiungere contenuto o azioni alla lista clienti. Il modulo potrebbe utilizzare questo hook per renderizzare un piccolo template o iniettare direttamente JavaScript per aggiungere il pulsante. |
| `actionAdminControllerSetMedia` | Eseguito quando un controller del Back Office sta impostando i suoi media (JS/CSS). | Un hook più robusto per aggiungere JS/CSS condizionalmente in base al controller attivo. Il modulo lo userebbe per caricare i suoi file JS specifici solo quando si trova sulle pagine `AdminCustomers` o `AdminOrders`. |
| `displayAdminOrder` | Eseguito sulla pagina del controller `AdminOrders`. | Se il modulo aggiunge un pulsante "Accedi come cliente" alla vista ordini (come suggerito da `176orders.js`, `177orders.js`), questo hook verrebbe utilizzato per iniettare il JavaScript o l'HTML del pulsante necessario. |
| `displayAdminCarts` | Eseguito sulla pagina del controller `AdminCarts`. | Se il modulo aggiunge un pulsante "Accedi come cliente" alla vista carrello (come suggerito da `17carts.js`), questo hook verrebbe utilizzato. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Accedi come cliente", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema tecnico o domanda tu possa avere.
