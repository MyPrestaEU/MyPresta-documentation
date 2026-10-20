---
title: "Limita il numero di ordini consentiti - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Limita il numero di ordini consentiti di MyPresta.eu."
sidebar:
  label: "Limita il numero di ordini consentiti - Manuale del commerciante e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Limit number of allowed orders su MyPresta.eu](https://mypresta.eu/modules/ordering-process/limit-number-of-allowed-orders.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/limit-number-of-allowed-orders/)
>
> ---


# Limita il numero di ordini consentiti

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono generalmente sufficienti.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale del modulo, dove definisci i limiti globali per i tuoi clienti.

-   **Cosa fa questa impostazione:** Questa è l'impostazione principale del modulo. Definisce il numero massimo di ordini che *qualsiasi* cliente può effettuare nel tuo negozio prima di essere impedito di effettuarne altri.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su un numero specifico (es. 3):* Qualsiasi cliente che ha effettuato con successo 3 ordini non sarà più in grado di effettuare un 4° ordine. Vedrà un messaggio che gli impedirà di completare il checkout.
    -   *Quando impostato su 0 o lasciato vuoto:* Il modulo sarà effettivamente disabilitato per i limiti globali, il che significa che i clienti possono effettuare un numero illimitato di ordini (a meno che non siano impostati limiti specifici per i clienti, vedi sezione 4.2).
-   **Valore consigliato:** Inizia con un valore che si allinei al tuo obiettivo aziendale (es. 1 per una promozione rigorosa "uno per cliente", 5 per un limite generale). Se desideri limitare solo clienti specifici, puoi lasciare questo campo vuoto e utilizzare la schermata di gestione clienti dedicata.
-   **Scenario / esempio del commerciante:** Stai gestendo una vendita flash per un prodotto molto richiesto e vuoi assicurarti che ogni cliente abbia solo una possibilità di acquistare. Imposteresti questo valore su `1`.

### 2.2 Schermata di amministrazione dedicata: Limiti di ordine del cliente (Back Office > Moduli > Limita il numero di ordini consentiti > Limiti di ordine del cliente)

Questa schermata ti consente di gestire i limiti di ordine individuali per clienti specifici, sovrascrivendo il limite globale impostato nella sezione 4.1.

-   **Nome schermata e posizione nel menu:** Puoi accedere a questa schermata navigando su **Moduli > Gestione moduli**, trovando "Limita il numero di ordini consentiti", cliccando su "Configura" e quindi cercando una scheda o un link etichettato "Limiti di ordine del cliente" o simile. In alternativa, potrebbe apparire direttamente nel tuo menu principale di PrestaShop sotto una nuova voce creata dal modulo (es. **Clienti > Limiti di ordine del cliente**).
-   **Azioni e impostazioni disponibili:**

    -   **Ricerca/Selezione cliente:** In genere troverai una barra di ricerca o un menu a discesa per selezionare un cliente esistente dal tuo negozio.
    -   **Imposta limite individuale:** Una volta selezionato un cliente, puoi inserire un numero specifico di ordini consentiti per *quel particolare cliente*.
    -   **Visualizza/Modifica limiti esistenti:** Una tabella o un elenco visualizzerà tutti i clienti per i quali hai impostato limiti personalizzati, insieme al loro limite attuale ed eventualmente al loro conteggio ordini attuale. Puoi modificare o eliminare queste voci.
    -   **Visualizzazione valuta:** Il modulo potrebbe visualizzare informazioni sulla valuta (es. `PS_CURRENCY_DEFAULT`) nel contesto degli ordini dei clienti, sebbene i limiti stessi siano conteggi numerici di ordini, non valori monetari.
-   **Effetto delle modifiche:**

    -   *Aggiunta di un nuovo limite cliente:* Il cliente selezionato sarà ora limitato dal numero specifico di ordini che hai impostato per lui, sovrascrivendo il limite globale (se impostato).
    -   *Modifica di un limite cliente esistente:* Il conteggio degli ordini consentiti del cliente verrà aggiornato immediatamente.
    -   *Eliminazione di un limite cliente:* Il cliente tornerà a essere governato dal limite d'ordine globale (se impostato), o non avrà alcun limite se nessun limite globale è attivo.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

    1.  **Identifica esigenze specifiche:** Determina se determinati clienti VIP, clienti problematici o clienti che partecipano a programmi speciali richiedono limiti d'ordine unici.
    2.  **Cerca e aggiungi:** Utilizza la funzionalità di ricerca per trovare il cliente.
    3.  **Applica limite:** Inserisci il numero massimo di ordini desiderato per quel cliente.
    4.  **Monitora:** Rivedi periodicamente l'elenco dei clienti con limiti personalizzati per assicurarti che le impostazioni siano ancora appropriate.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | **Numero massimo di ordini consentiti (Globale)** | 0 (Illimitato) / La tua esigenza aziendale | Imposta un numero massimo di ordini a livello di negozio per *tutti* i clienti. Impedisce il checkout se superato. |
| Limiti di ordine del cliente | **Ricerca e selezione cliente** | N/A | Consente di trovare e selezionare clienti specifici per applicare limiti individuali. |
| Limiti di ordine del cliente | **Limite di ordine del singolo cliente** | N/A | Sovrascrive il limite globale per un cliente specifico. Impedisce il checkout per quel cliente se il suo limite individuale viene superato. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei clienti sono ancora in grado di effettuare ordini illimitati, anche dopo aver impostato un limite globale. Cosa c'è che non va?**
R:

1.  **Controlla l'impostazione:** Ricontrolla di aver salvato l'impostazione "Numero massimo di ordini consentiti (Globale)" nella pagina di configurazione principale del modulo.
2.  **Svuota la cache:** PrestaShop utilizza la cache. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti). Questo assicura che le tue nuove impostazioni vengano applicate immediatamente.
3.  **Stato del modulo:** Assicurati che il modulo sia abilitato in **Moduli > Gestione moduli**.
4.  **Sovrascritture specifiche del cliente:** Controlla la schermata "Limiti di ordine del cliente". Se un cliente specifico ha un limite individuale impostato su `0` o un numero molto alto, questo sovrascriverà il limite globale per loro.

**D: Posso impostare un limite per un cliente in base al *valore* dei suoi ordini, non solo al conteggio?**
R: Questo modulo limita specificamente il *numero* di ordini. Attualmente non supporta la limitazione basata sul valore monetario. Per limiti basati sul valore, avresti bisogno di un diverso tipo di modulo o di uno sviluppo personalizzato.

**D: Cosa succede quando un cliente raggiunge il suo limite? Cosa vede?**
R: Quando un cliente tenta di effettuare un ordine che supererebbe il suo limite, il modulo impedirà che l'ordine venga finalizzato. Tipicamente, un messaggio chiaro verrà visualizzato nella pagina di checkout o nel carrello, informandolo che ha raggiunto il numero massimo di ordini consentiti e non può procedere. La formulazione esatta potrebbe dipendere dalla tua versione di PrestaShop e dal tema.

**D: Questo modulo influisce sugli ordini passati?**
R: No, questo modulo influisce solo sugli ordini *futuri*. Conta gli ordini riusciti esistenti per determinare se un nuovo tentativo di ordine supererebbe il limite, ma non modifica o annulla alcun ordine precedentemente effettuato.

**D: Voglio rimuovere temporaneamente un limite per un cliente specifico. Come faccio?**
R: Vai alla schermata "Limiti di ordine del cliente". Trova il cliente, modifica il suo limite individuale e impostalo su `0` (per illimitato) o un numero molto alto. Ricorda di salvare le modifiche. Puoi sempre riapplicare un limite più severo in seguito.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Limita il numero di ordini consentiti" segue un'architettura standard dei moduli PrestaShop, sfruttando gli hook per l'integrazione e un AdminController per la gestione dei limiti specifici dei clienti. Opera principalmente controllando la cronologia degli ordini dei clienti rispetto ai limiti configurati durante il processo di convalida dell'ordine. Il modulo si basa sul sistema di configurazione di PrestaShop per le impostazioni globali e su una tabella di database personalizzata per i limiti individuali dei clienti.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Questo modulo non utilizza controller front-office dedicati. La sua logica per il controllo dei limiti è integrata direttamente nel processo d'ordine di PrestaShop tramite hook.
-   **Controller Admin Back-Office**:
    -   `controllers/admin/AdminLimitOrdersUserController.php`
        -   **Nome classe**: `AdminLimitOrdersUserController` (estende `ModuleAdminController`)
        -   **Responsabilità**: Questo controller gestisce i limiti d'ordine personalizzati per i singoli clienti. Fornisce un'interfaccia standard PrestaShop `list` e `form` per aggiungere, modificare ed eliminare i limiti d'ordine specifici del cliente. Interagisce con l'ObjectModel `LimitOrdersUser` (sebbene non sia stato identificato alcun file `classes/` esplicito, è implicito dal nome e dalla funzione del controller). Probabilmente utilizza `PS_CURRENCY_DEFAULT` per visualizzare il contesto della valuta, sebbene i limiti stessi siano numerici.
        -   **Nome scheda**: Probabilmente "Limiti di ordine del cliente" o simile, accessibile dalla pagina di configurazione del modulo o da una voce di menu dedicata.
    -   `controllers/admin/index.php`
        -   **Nome classe**: (Non una classe, tipicamente un file vuoto o un reindirizzamento per sicurezza)
        -   **Responsabilità**: Questo file è solitamente un segnaposto o una misura di sicurezza per prevenire l'elenco diretto delle directory. Non contiene logica di controller attiva.

### 4.3 Classi e modelli principali (`classes/`)

Sulla base delle informazioni fornite, non sono state identificate classi personalizzate esplicite nella directory `classes/`. Tuttavia, `AdminLimitOrdersUserController` implica fortemente l'esistenza di una classe `ObjectModel`, probabilmente denominata `LimitOrdersUser`, che si mapperebbe a una tabella di database personalizzata (es. `ps_limitorders_user`). Questo `ObjectModel` definirebbe campi come `id_customer` e `max_orders`.

### 4.4 Risorse JavaScript (`views/js/`)

-   `lib/searchTool/views/js/autocomplete.js`
    -   **Ambito**: Probabilmente Back-office.
    -   **Scopo**: Fornisce funzionalità di completamento automatico, probabilmente per la ricerca e la selezione di clienti all'interno del modulo `AdminLimitOrdersUserController` durante l'impostazione dei limiti individuali. Si legherebbe ai campi di input, invierebbe richieste AJAX a un controller backend (possibilmente lo stesso `AdminLimitOrdersUserController` o un endpoint AJAX dedicato) e visualizzerebbe suggerimenti.
-   `views/js/limitorders.js`
    -   **Ambito**: Potenzialmente sia Front-office (per la visualizzazione dei messaggi) che Back-office (per la funzionalità generale del modulo).
    -   **Scopo**: Questo file conterrebbe la logica JavaScript principale per il modulo. Nel Back-office, potrebbe gestire le convalide dei moduli o gli elementi UI dinamici nelle pagine di configurazione. Nel Front-office, se sono necessari messaggi o interazioni dinamiche quando un cliente raggiunge il suo limite (es. un popup modale, aggiornamento dinamico del carrello), questo script gestirebbe ciò.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `lib/searchTool/views/css/autocomplete.css`
    -   **Ambito**: Stile di amministrazione del Back-office.
    -   **Scopo**: Stila il menu a discesa di completamento automatico e i campi di input utilizzati nel pannello di amministrazione, garantendo un'esperienza di ricerca coerente e user-friendly per i clienti.
-   `views/css/limitorders.css`
    -   **Ambito**: Sia Front-office che Back-office.
    -   **Scopo**: Contiene lo stile generale per tutti gli elementi visibili introdotti dal modulo. Nel Back-office, stilerebbe i moduli di configurazione e le tabelle. Nel Front-office, stilerebbe i messaggi visualizzati ai clienti quando raggiungono il loro limite d'ordine, assicurando che si integrino bene con il tema del negozio.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template degli hook (`views/templates/hook/`)**:
    -   Questo modulo non elenca esplicitamente i template nella directory `hook/`, ma la sua funzionalità implica che si aggancerebbe a `displayShoppingCart` o `displayShoppingCartFooter` per mostrare i messaggi.
-   **Template di amministrazione (`views/templates/admin/`)**:
    -   I template per `AdminLimitOrdersUserController` (es. `list.tpl`, `form.tpl`) risiederebbero qui, definendo la struttura dell'interfaccia di gestione dei limiti del cliente.
-   **Template Front-office (`views/templates/front/`)**:
    -   `views/templates/front/displayShoppingCart.tpl`
        -   **Scopo**: Questo template è probabilmente renderizzato quando il modulo si aggancia a `displayShoppingCart`. Contenerebbe la logica per visualizzare un messaggio al cliente *all'interno del suo carrello* se ha raggiunto il suo limite d'ordine, impedendogli di procedere al checkout.
    -   `views/templates/front/displayShoppingCartEmpty.tpl`
        -   **Scopo**: Questo template potrebbe essere utilizzato in uno scenario specifico in cui il modulo deve visualizzare un messaggio relativo ai limiti d'ordine anche quando il carrello è vuoto, o come visualizzazione di messaggio di fallback/alternativa. Il suo caso d'uso esatto dipenderebbe dalla logica interna del modulo per i diversi stati.
-   `lib/searchTool/views/scripts.tpl`
    -   **Scopo**: Questo template probabilmente include i file JavaScript e CSS necessari per i componenti `autocomplete.js` e `autocomplete.css`, assicurando che vengano caricati correttamente nel Back-office.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    -   `ps_configuration`: Memorizza il numero massimo globale di ordini consentiti (es. `LIMITORDERS_MAX_ORDERS`).
    -   `ps_limitorders_user`: (Tabella personalizzata implicita) Memorizza i limiti di ordine individuali dei clienti.
        -   `id_limitorders_user` (Chiave primaria)
        -   `id_customer` (Chiave esterna a `ps_customer`)
        -   `max_orders` (INT, il numero massimo di ordini consentiti per questo cliente specifico)
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Renderizza nella sezione `<head>` di tutte le pagine del front-office. | Potenzialmente per il caricamento di risorse CSS/JS del front-office o per controlli preliminari. |
| `displayRightColumn` / `displayLeftColumn` | Renderizza nella colonna destra/sinistra delle pagine del front-office. | Potrebbe essere utilizzato per visualizzare un messaggio sottile sui limiti d'ordine, sebbene meno probabile per questo modulo. |
| `displayProductButtons` / `displayProductExtraContent` | Renderizza nella pagina del prodotto. | Potrebbe essere utilizzato per visualizzare un messaggio se un cliente ha raggiunto il suo limite e non può aggiungere al carrello. |
| `displayShoppingCart` | Renderizza all'interno del riepilogo del carrello. | **CRITICO:** Probabilmente utilizzato per visualizzare messaggi al cliente se ha raggiunto il suo limite d'ordine, impedendo il checkout. |
| `displayShoppingCartFooter` | Renderizza sotto il riepilogo del carrello. | Simile a `displayShoppingCart`, per la visualizzazione di messaggi o avvisi. |
| `displayFooter` | Renderizza nel piè di pagina di tutte le pagine del front-office. | Meno probabile per la funzionalità principale, eventualmente per informazioni generali sul modulo o script. |
| `actionValidateOrder` | Eseguito *dopo* che un ordine è stato convalidato e salvato nel database. | **CRITICO:** Questo hook è essenziale affinché il modulo incrementi il conteggio degli ordini per un cliente e potenzialmente aggiorni il suo stato se ha raggiunto il suo limite. |
| `actionBeforeCartUpdateQuantity` | Eseguito prima che la quantità di un prodotto venga aggiornata nel carrello. | Potrebbe essere utilizzato per eseguire un controllo preliminare sui limiti prima di consentire l'aggiunta/aggiornamento di un articolo. |
| `actionFrontControllerSetMedia` | Consente di aggiungere CSS/JS alle pagine del front-office. | Utilizzato per caricare `limitorders.js` e `limitorders.css` nelle pagine del front-office pertinenti. |
| `actionAdminControllerSetMedia` | Consente di aggiungere CSS/JS alle pagine del back-office. | Utilizzato per caricare CSS/JS specifici dell'amministrazione per le schermate di configurazione e `AdminLimitOrdersUserController`. |
| `displayBackOfficeHeader` | Renderizza nella sezione `<head>` di tutte le pagine del back-office. | Per il caricamento di CSS/JS specifici dell'amministrazione o la visualizzazione di avvisi di amministrazione. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo "Limita il numero di ordini consentiti", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a garantire che il tuo modulo funzioni perfettamente e ti aiuti a raggiungere i tuoi obiettivi di e-commerce.
