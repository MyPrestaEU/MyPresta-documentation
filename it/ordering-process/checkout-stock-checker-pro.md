---
title: "Checkout stock checker PRO - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Checkout stock checker PRO di MyPresta.eu."
sidebar:
  label: "Checkout stock checker PRO"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Checkout stock checker PRO su MyPresta.eu](https://mypresta.eu/modules/ordering-process/checkout-stock-checker-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/checkout-stock-checker-pro/)
>
> ---


# Checkout stock checker PRO

## 1. Requisiti e Compatibilità

-   **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
-   **Compatibilità PHP**: PHP 5.6 - 8.5
-   **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti e disponibili sulla maggior parte degli ambienti di hosting moderni.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)
Dopo l'installazione, cliccando su "Configura" verrai indirizzato alla schermata di configurazione principale e unica per il modulo "Checkout stock checker PRO". Questa schermata ti consente di abilitare o disabilitare la funzionalità principale del modulo.

#### **Abilita / Disabilita Modulo**
-   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare la funzionalità di controllo delle scorte.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Il modulo controllerà attivamente i livelli di stock dei prodotti appena prima che un ordine venga effettuato. Se un articolo è esaurito, il cliente verrà reindirizzato al carrello con una notifica.
    -   *Quando disabilitato (NO):* Il modulo sarà inattivo. I controlli delle scorte non verranno eseguiti e i clienti potrebbero essere in grado di effettuare ordini per articoli esauriti, affidandosi esclusivamente al comportamento predefinito di gestione delle scorte di PrestaShop (che di solito controlla solo quando si aggiunge al carrello, non al momento dell'ordine finale).
-   **Valore consigliato:** **SÌ**. Per beneficiare appieno dello scopo del modulo, dovrebbe essere sempre abilitato.
-   **Scenario / esempio per il commerciante:** Hai appena installato il modulo e vuoi iniziare a prevenire ordini con articoli esauriti. Imposteresti questo valore su "SÌ". Se hai bisogno di disabilitare temporaneamente la funzione per manutenzione o test, lo imposteresti su "NO".

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Pagina di configurazione del modulo | Abilita / Disabilita Modulo | SÌ | Controlla se il modulo verifica attivamente le scorte prima dell'effettuazione dell'ordine. Impedisce ordini per articoli esauriti quando abilitato. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Il modulo è abilitato, ma i clienti continuano a effettuare ordini per articoli esauriti. Cosa c'è che non va?**
R:
1.  **Svuota la cache:** Per prima cosa, prova a svuotare la cache di PrestaShop. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" in alto a destra.
2.  **Controlla lo stato del modulo:** Ricontrolla che il modulo sia effettivamente abilitato nella sua pagina di configurazione.
3.  **Conflitti con il tema:** Alcuni temi altamente personalizzati o altri moduli che modificano il checkout potrebbero interferire. Passa temporaneamente al tema predefinito di PrestaShop (Classic) e testa di nuovo. Se funziona, il problema è probabilmente un conflitto con il tema e potresti aver bisogno di uno sviluppatore per indagare.
4.  **Versione di PrestaShop:** Assicurati di aver scaricato la versione corretta del modulo per la tua specifica installazione di PrestaShop.

**D: I miei clienti vengono reindirizzati al carrello, ma il messaggio di notifica non viene visualizzato o è mal formattato.**
R:
1.  **Svuota la cache:** Come sempre, svuota la cache di PrestaShop.
2.  **Stile del tema:** Il messaggio di notifica utilizza le classi di avviso standard di PrestaShop. Se il tuo tema ha personalizzato pesantemente o rimosso questi stili, il messaggio potrebbe essere invisibile o formattato in modo errato. Un webmaster può ispezionare l'HTML e il CSS per assicurarsi che il messaggio sia presente e stilizzato correttamente.
3.  **File del modulo:** Assicurati che tutti i file del modulo siano stati caricati correttamente. A volte, caricamenti incompleti possono portare alla mancanza di file di template per le notifiche.

**D: Questo modulo funziona con negozi multilingue?**
R: Sì, il modulo utilizza i meccanismi di traduzione standard di PrestaShop. I messaggi di notifica visualizzati ai clienti possono essere tradotti in tutte le lingue configurate nel tuo negozio. Puoi gestire queste traduzioni in **Internazionale > Traduzioni > Traduzioni dei moduli installati**.

**D: Questo modulo rallenterà il mio processo di checkout?**
R: Il controllo delle scorte eseguito dal modulo è molto veloce, aggiungendo tipicamente solo millisecondi al processo di checkout. Si tratta di una query diretta al database per i livelli di stock, che è altamente ottimizzata. L'impatto sulle prestazioni è trascurabile e ampiamente superato dai vantaggi di prevenire ordini con articoli esauriti.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)
Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura
Il modulo "Checkout stock checker PRO" (`csc`) è progettato per integrarsi perfettamente nel flusso di checkout di PrestaShop. Opera principalmente agganciandosi alla fase finale del processo di effettuazione dell'ordine, sfruttando un front controller per eseguire una verifica delle scorte basata su AJAX. Questo approccio garantisce che il controllo delle scorte venga eseguito in tempo reale appena prima che l'ordine venga commesso nel database, prevenendo condizioni di gara in cui le scorte potrebbero cambiare tra la revisione del carrello e la conferma finale dell'ordine. Il modulo aderisce al pattern MVC di PrestaShop per la sua interazione front-end e configurazione.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office
-   `csc/controllers/front/AjaxCheck.php`
    *   **Nome classe e classe genitore:** `CscAjaxCheckModuleFrontController` che estende `ModuleFrontController`.
    *   **Responsabilità:** Questo controller è il cuore della funzionalità del modulo. È responsabile della gestione della richiesta AJAX avviata dalla pagina di checkout del front-office. Dopo aver ricevuto la richiesta, itera attraverso i prodotti nel carrello del cliente, controlla i loro livelli di stock attuali rispetto alle quantità richieste e restituisce una risposta JSON che indica se tutti gli articoli sono in stock o quali articoli sono esauriti. Non renderizza una pagina completa ma fornisce dati affinché il JavaScript possa agire.
-   `csc/controllers/front/index.php`
    *   **Nome classe e classe genitore:** Questo è un file `index.php` standard vuoto, tipicamente incluso nelle directory dei moduli PrestaShop per prevenire la visualizzazione diretta delle directory. Non contiene una classe o una logica specifica.

#### Controller Admin Back-Office
Il modulo non utilizza alcun controller Admin personalizzato. La sua configurazione è gestita direttamente all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)
Il modulo non definisce alcuna classe `ObjectModel` personalizzata o classi di logica di business dedicate all'interno della directory `classes/`. Tutta la logica principale è incapsulata all'interno del file principale del modulo (`ajax_csc.php`) e del front controller `AjaxCheck`.

### 4.4 Risorse JavaScript (`views/js/`)
-   `csc/views/js/csc.js`
    *   **Ambito:** Front-office.
    *   **Dettagli:** Questo file JavaScript è responsabile dell'avvio del controllo delle scorte AJAX. Tipicamente si aggancia all'evento di click del pulsante finale "Effettua ordine" (o equivalente invio di modulo) sulla pagina di checkout. Prima di consentire l'invio del modulo, invia una richiesta AJAX al front controller `AjaxCheck`. In base alla risposta JSON, consente il completamento del checkout o impedisce l'invio, reindirizza l'utente al carrello e visualizza il messaggio di errore appropriato. Utilizza jQuery standard o gli eventi JavaScript nativi di PrestaShop (`prestashop.on`) per raggiungere questo obiettivo.

### 4.5 Fogli di stile CSS (`views/css/`)
-   `csc/views/css/csc.css`
    *   **Ambito:** Stile del cliente front-office.
    *   **Dettagli:** Questo foglio di stile fornisce uno stile di base per i messaggi di notifica visualizzati sulla pagina del carrello quando i prodotti risultano esauriti. Probabilmente si rivolge a classi CSS specifiche aggiunte agli elementi `div` di notifica.
    *   **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere:** Gli sviluppatori possono ispezionare l'output HTML del messaggio di notifica per identificare le classi specifiche (ad esempio, `.alert-danger`, `.csc-notification`, ecc.) e sovrascriverle nel `custom.css` o `theme.css` del loro tema per adattarle al branding del loro negozio.

### 4.6 Struttura dei template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**: Nessuno esplicitamente elencato, suggerendo che l'interazione principale del modulo avviene tramite AJAX e reindirizzamento, con le notifiche renderizzate direttamente dal controller `AjaxCheck` o dal modulo principale.
-   **Template admin (`views/templates/admin/`)**: Nessuno, poiché la configurazione è gestita da `getContent()`.
-   **Template front-office (`views/templates/front/`)**:
    *   `csc/lib/searchTool/views/scripts.tpl`
        *   **Scopo:** Questo template probabilmente include il file JavaScript `csc.js` e potenzialmente passa variabili di configurazione dal back-end del modulo al JavaScript del front-end. È probabilmente agganciato a `displayHeader` o `displayFooter` per garantire che il JS sia caricato sulle pagine pertinenti (ad esempio, checkout).
    *   `csc/views/errors.tpl`
        *   **Scopo:** Questo template viene renderizzato quando il controllo delle scorte fallisce (cioè, gli articoli sono esauriti). Visualizza il messaggio di errore ed elenca i prodotti specifici che non sono più disponibili. Questo è il template responsabile della notifica visibile sulla pagina del carrello dopo il reindirizzamento.
    *   `csc/views/no-errors.tpl`
        *   **Scopo:** Questo template è probabilmente un segnaposto o un template che verrebbe renderizzato se non ci fossero errori, ma la funzione principale del modulo è quella di visualizzare gli errori. Potrebbe essere utilizzato per la logica interna o essere semplicemente un template vuoto.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**: Il modulo non crea tabelle del database personalizzate. Si basa interamente sulle tabelle esistenti di PrestaShop `ps_product`, `ps_stock_available` e `ps_configuration`. Le impostazioni di configurazione (come l'interruttore abilita/disabilita) sono memorizzate in `ps_configuration` utilizzando chiavi come `CSC_ENABLED`.

-   **Tabella degli hook registrati**:

| Nome dell'Hook | Tempistica di Esecuzione | Scopo Tecnico |
| :-------- | :--------------- | :---------------- |
| `displayHeader` | Renderizza il contenuto nella sezione `<head>` di ogni pagina. | Probabilmente utilizzato per includere lo script `csc.js` e il foglio di stile `csc.css`, assicurando che siano disponibili sulle pagine di checkout. |
| `displayFooter` | Renderizza il contenuto alla fine della sezione `<body>` di ogni pagina. | Hook alternativo a `displayHeader` per includere JS/CSS, spesso preferito per le prestazioni. |
| `displayProductButtons` | Renderizza il contenuto vicino ai pulsanti del prodotto (es. aggiungi al carrello). | *Non esplicitamente utilizzato per la funzionalità principale, ma potrebbe esserlo per funzionalità future o elementi UI minori.* |
| `displayRightColumn` | Renderizza il contenuto nella colonna destra del negozio. | *Non esplicitamente utilizzato per la funzionalità principale, ma potrebbe esserlo per funzionalità future o elementi UI minori.* |
| `actionFrontControllerSetMedia` | Eseguito quando un front controller imposta i suoi media (JS/CSS). | Un hook più mirato per aggiungere JS/CSS specificamente ai front controller pertinenti (es. pagine di checkout). |
| `actionBeforeUpdateQuantity` | Eseguito prima che la quantità di un prodotto venga aggiornata nel carrello. | *Non esplicitamente utilizzato per la funzionalità principale, ma potrebbe esserlo per funzionalità future o elementi UI minori.* |
| `actionCartSave` | Eseguito dopo il salvataggio di un carrello. | *Non esplicitamente utilizzato per la funzionalità principale, ma potrebbe esserlo per funzionalità future o elementi UI minori.* |
| `actionValidateOrder` | Eseguito dopo la convalida di un ordine. | *Cruciale per la logica del modulo.* Questo è il punto in cui il modulo interviene per eseguire il controllo finale delle scorte *prima* che l'ordine sia completamente commesso. Il JavaScript del modulo probabilmente impedisce l'invio del modulo che attiva questo hook se vengono riscontrati problemi di scorte. |

*Nota: Il meccanismo principale del modulo per il controllo delle scorte è tramite il suo front controller `AjaxCheck`, che viene attivato da JavaScript sulla pagina di checkout, piuttosto che basarsi esclusivamente sugli hook nativi di PrestaShop per il controllo delle scorte stesso. Gli hook sono utilizzati principalmente per il caricamento di risorse e potenzialmente per la visualizzazione di notifiche.*

## 5. Supporto Ufficiale e Aggiornamenti
Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Checkout stock checker PRO", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda relativa alla funzionalità e all'integrazione del modulo.
