---
title: "Anteprima Rapida Ordine - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Anteprima Rapida Ordine di MyPresta.eu."
sidebar:
  label: "Anteprima Rapida Ordine - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Quick Order Preview su MyPresta.eu](https://mypresta.eu/modules/administration-tools/quick-order-preview.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/quick-order-preview/)
>
> ---


# Anteprima Rapida Ordine

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 9.x, 8.x, 1.7.7.x - 1.7.8.x, 1.7.0.0 - 1.7.6.x, 1.6.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo "Anteprima Rapida Ordine". Questo ti porterà alla sua schermata di configurazione principale.

Non ci sono opzioni di configurazione specifiche su questa schermata per il modulo "Anteprima Rapida Ordine". Il modulo funziona immediatamente migliorando la funzionalità della pagina "Ordini" esistente. La sua funzione principale è quella di iniettare il JavaScript e i template necessari per abilitare la funzione di anteprima rapida direttamente nella tua lista ordini.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### AdminPreviewOrderController (Back Office > Ordini > Lista Ordini)

Questo modulo non aggiunge una nuova voce di menu al tuo back office PrestaShop. Invece, migliora la pagina esistente della lista **"Ordini"** (che si trova sotto **Back Office > Ordini > Ordini**).

- **Nome schermata e posizione nel menu:** Accedi a questa funzionalità migliorata navigando su **Ordini > Ordini** nel tuo back office PrestaShop.
- **Azioni e impostazioni disponibili:**
  - **Funzionalità di anteprima rapida:** Quando sei sulla pagina della lista "Ordini", clicca semplicemente su qualsiasi riga dell'ordine. Invece di essere reindirizzato alla pagina completa dei dettagli dell'ordine, il modulo espanderà la riga dell'ordine per visualizzare le informazioni chiave direttamente sotto di essa. Questo include:
    - **Indirizzo del cliente:** Indirizzi di fatturazione e spedizione.
    - **Prodotti ordinati:** Un elenco degli articoli acquistati, incluse quantità e prezzi.
    - **Nota del cliente:** Se il cliente ha lasciato una nota durante il checkout, sarà visibile qui.
  - **Pulsante "Visualizza Ordine":** All'interno dell'anteprima espansa, troverai comunque un pulsante "Visualizza Ordine" (o un link simile) che ti permette di navigare alla pagina completa e tradizionale dei dettagli dell'ordine se hai bisogno di eseguire azioni come cambiare lo stato dell'ordine, aggiungere prodotti o generare fatture.
  - **Salvataggio nota cliente:** Il modulo include anche la funzionalità per salvare le note del cliente direttamente da questa anteprima rapida. Questo è gestito dallo script `save-customer-note.js`.
- **Effetto delle modifiche:**
  - Cliccando su una riga dell'ordine ora si attiva la visualizzazione delle sue informazioni dettagliate direttamente sulla pagina della lista degli ordini.
  - Puoi rivedere rapidamente i dati essenziali dell'ordine senza lasciare la lista principale, accelerando significativamente il tuo flusso di lavoro di elaborazione degli ordini.
  - La possibilità di salvare le note del cliente direttamente dall'anteprima semplifica la comunicazione e la tenuta dei registri.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1. Vai su **Ordini > Ordini**.
  2. Per controllare rapidamente cosa ha ordinato un cliente o il suo indirizzo di spedizione, clicca semplicemente sulla riga dell'ordine nella lista.
  3. I dettagli si espanderanno sotto l'ordine. Rivedi le informazioni.
  4. Se hai bisogno di cambiare lo stato dell'ordine, stampare una fattura o eseguire altre azioni avanzate, clicca sul pulsante "Visualizza Ordine" all'interno dell'anteprima espansa per andare alla pagina completa dei dettagli dell'ordine.
  5. Se hai bisogno di aggiungere una nota rapida sul cliente o sull'ordine, usa il campo della nota del cliente all'interno dell'anteprima e salvala.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Lista Ordini | Clicca Riga Ordine | N/A | Espande i dettagli dell'ordine (prodotti, indirizzi, note) direttamente sulla pagina della lista, risparmiando tempo di navigazione. |
| Lista Ordini | Campo Nota Cliente | N/A | Permette di salvare le note direttamente dall'anteprima rapida. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I dettagli dell'ordine non si espandono quando clicco su una riga dell'ordine. Cosa c'è che non va?**
R:

1. **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" in alto a destra. A volte, i vecchi file di cache impediscono il caricamento dei nuovi script del modulo.
2. **Modulo abilitato:** Assicurati che il modulo "Anteprima Rapida Ordine" sia abilitato in **Moduli > Gestione moduli**.
3. **Compatibilità del tema:** Sebbene il modulo sia progettato per essere compatibile, temi molto pesantemente personalizzati potrebbero a volte interferire. Controlla la console per sviluppatori del tuo browser (F12) per errori JavaScript. Se vedi errori relativi al modulo, contatta il supporto MyPresta.eu.
4. **Versione PrestaShop:** Assicurati di aver scaricato e installato la versione corretta del modulo per la tua specifica installazione di PrestaShop.

**D: Posso personalizzare quali informazioni vengono mostrate nell'anteprima rapida?**
R: Il modulo visualizza informazioni essenziali come prodotti e indirizzi. La personalizzazione dei campi visualizzati richiederebbe la modifica diretta dei file di template del modulo (`address.tpl`, `products.tpl`). Questo è un compito a livello di sviluppatore.

**D: Questo modulo influisce sulle prestazioni del mio negozio?**
R: No, il modulo è progettato per essere leggero. Carica contenuti aggiuntivi solo quando clicchi esplicitamente su una riga dell'ordine nel back office. Non aggiunge alcun sovraccarico al tuo front office o alla navigazione generale del back office.

**D: Sto usando una versione precedente di PrestaShop 1.6, funzionerà?**
R: Sì, il modulo è compatibile con PrestaShop 1.6.x. Assicurati di scaricare il pacchetto corretto per la tua versione di PrestaShop dal tuo account MyPresta.eu.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Anteprima Rapida Ordine" (`qov`) è principalmente un modulo di miglioramento del Back Office. Sfrutta il meccanismo di override di `AdminController` di PrestaShop e il templating Smarty per iniettare contenuto dinamico nella lista "Ordini" esistente. Utilizza JavaScript per gestire le richieste AJAX e la manipolazione del DOM per espandere/comprimere i dettagli dell'ordine. Il modulo non introduce nuove tabelle di database o complesse strutture `ObjectModel`, concentrandosi invece sull'aumento della funzionalità esistente di PrestaShop.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**: Nessuno. Questo modulo è puramente uno strumento di Back Office.
- **Controller Admin Back-Office**:

  - `qov/controllers/admin/AdminPreviewOrder.php`
    - **Nome classe e classe genitore**: `AdminPreviewOrderController` estende `AdminOrdersController`.
    - **Responsabilità**: Questo controller sovrascrive il `AdminOrdersController` predefinito per iniettare il JavaScript necessario e potenzialmente modificare il metodo `renderList()` per includere la funzionalità di anteprima rapida. È responsabile della gestione delle richieste AJAX che recuperano i dettagli dell'ordine (prodotti, indirizzi) quando si clicca su una riga dell'ordine e del rendering dei template `address.tpl` e `products.tpl` con i dati recuperati. Gestisce anche la chiave di configurazione `QOV_TRACKING_EMAIL`, sebbene il suo uso diretto non sia evidente dalle informazioni fornite.

### 4.3 Classi e modelli principali (`classes/`)

Nessuno. Il modulo non definisce classi `ObjectModel` personalizzate o complesse classi di logica di business. Interagisce principalmente con le classi core esistenti di PrestaShop come `Order`, `Address`, `Product`, ecc., tramite il suo controller.

### 4.4 Risorse JavaScript (`views/js/`)

- `qov/views/js/177-expand-all-imm.js`

  - **Ambito**: Back-office (lista Ordini, PrestaShop 1.7.7+).
  - **Descrizione**: Questo script probabilmente gestisce l'espansione immediata di tutti i dettagli dell'ordine nella pagina della lista degli ordini, possibilmente per una vista o un'azione specifica. Collegherebbe gli eventi di clic alle righe degli ordini e attiverebbe le chiamate AJAX per recuperare e visualizzare i dettagli per più ordini contemporaneamente.
- `qov/views/js/177-expand-all.js`

  - **Ambito**: Back-office (lista Ordini, PrestaShop 1.7.7+).
  - **Descrizione**: Simile a `177-expand-all-imm.js`, questo script è responsabile della funzionalità "espandi tutto". Ascolterebbe un trigger specifico (ad esempio, un clic su un pulsante) per espandere tutti i dettagli dell'ordine visibili sulla pagina corrente, effettuando richieste AJAX per ogni ordine.
- `qov/views/js/177orders-multiple.js`

  - **Ambito**: Back-office (lista Ordini, PrestaShop 1.7.7+).
  - **Descrizione**: Questo è lo script principale che abilita la funzionalità di anteprima rapida. Collega gli eventi di clic alle singole righe degli ordini nella lista `AdminOrders`. Quando si clicca su una riga dell'ordine, impedisce la navigazione predefinita alla pagina completa dell'ordine. Invece, effettua una richiesta AJAX a `AdminPreviewOrderController` (o un endpoint simile) per recuperare i prodotti, gli indirizzi e altri dettagli dell'ordine. Quindi inietta dinamicamente l'HTML renderizzato (da `address.tpl` e `products.tpl`) in una nuova riga o in una sezione espansa sotto la riga dell'ordine cliccata. Gestisce anche la compressione dei dettagli quando la riga viene cliccata di nuovo.
- `qov/views/js/save-customer-note.js`

  - **Ambito**: Back-office (lista Ordini, specificamente all'interno dell'anteprima rapida).
  - **Descrizione**: Questo script gestisce la funzionalità per salvare le note del cliente direttamente dall'anteprima rapida dell'ordine. Si lega ai campi di input o ai pulsanti all'interno dei dettagli dell'ordine espansi. Quando una nota viene inserita o aggiornata, invia una richiesta AJAX a un endpoint del back-office (probabilmente `AdminPreviewOrderController` o il `AdminOrdersController` predefinito con un'azione specifica) per rendere persistente la nota nel database, tipicamente nella tabella `ps_order_note` o simile.

### 4.5 Fogli di stile CSS (`views/css/`)

Nessuno. Il modulo non include file CSS personalizzati. Probabilmente si basa sullo stile esistente del back-office di PrestaShop o su stili in linea per i dettagli dell'ordine espansi. Gli sviluppatori che desiderano stilizzare l'anteprima dovrebbero mirare agli elementi HTML iniettati dinamicamente.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template Admin (`views/templates/admin/`)**:
  - `qov/views/templates/admin/address.tpl`
    - **Descrizione**: Questo template viene utilizzato per renderizzare i dettagli dell'indirizzo di fatturazione e spedizione del cliente all'interno dell'anteprima rapida dell'ordine. Riceve i dati dell'indirizzo da `AdminPreviewOrderController` e li formatta per la visualizzazione.
  - `qov/views/templates/admin/products.tpl`
    - **Descrizione**: Questo template è responsabile del rendering dell'elenco dei prodotti ordinati dal cliente all'interno dell'anteprima rapida dell'ordine. Riceve i dati del prodotto (nome, quantità, prezzo, ecc.) e li visualizza in un formato chiaro, tabellare o di elenco.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Il modulo non crea tabelle di database personalizzate. Legge e potenzialmente scrive (per le note del cliente) nelle tabelle standard di PrestaShop come `ps_orders`, `ps_order_detail`, `ps_address`, `ps_customer` e `ps_order_note`.
  - I valori di configurazione sono memorizzati in `ps_configuration`, in particolare `QOV_TRACKING_EMAIL`.
- **Tabella degli hook registrati**:
  Il modulo non registra esplicitamente alcun hook front-office (come `displayHeader`, `displayRightColumn`, `displayProduct`, `displayFooter`) in quanto è un modulo back-office. La sua funzionalità viene principalmente iniettata sovrascrivendo `AdminOrdersController` e modificando il suo metodo `renderList()` o iniettando contenuto tramite JavaScript nella pagina "Ordini" esistente del Back Office.

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Eseguito quando un Admin Controller imposta le sue risorse multimediali. | Utilizzato da `AdminPreviewOrderController` per mettere in coda i suoi file JavaScript (`177-expand-all-imm.js`, `177-expand-all.js`, `177orders-multiple.js`, `save-customer-note.js`) per la pagina `AdminOrders`. |
| `displayAdminOrder` | Eseguito sulla pagina Admin Order. | Sebbene non sia esplicitamente elencato come hook, la funzionalità principale del modulo è ottenuta sovrascrivendo `AdminOrdersController` e modificando il suo metodo `renderList()` o iniettando contenuto tramite JavaScript nella lista degli ordini esistente. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo "Anteprima Rapida Ordine", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi domanda o problema tu possa incontrare.
