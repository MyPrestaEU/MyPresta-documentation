---
title: "Colonna Fattura Elenco Ordini & Ricerca - Manuale Commerciante & Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Colonna Fattura Elenco Ordini & Ricerca di MyPresta.eu."
sidebar:
  label: "Colonna Fattura Elenco Ordini & Ricerca - Manuale Commerciante & Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Order List Invoice Column & Search su MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-list-invoice-column-search.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/order-list-invoice-column-search/)
>
> ---


# Colonna Fattura Elenco Ordini & Ricerca

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Nessun requisito di hosting speciale oltre a una configurazione PrestaShop standard.

## 2. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al nome del modulo "Colonna Fattura Elenco Ordini & Ricerca". Questo modulo ha una configurazione molto semplice e diretta, poiché la sua funzionalità principale è quella di migliorare l'elenco degli ordini esistente.

La pagina di configurazione per "Colonna Fattura Elenco Ordini & Ricerca" è semplice. Serve principalmente ad abilitare o disabilitare la funzionalità del modulo.

- **Nome Impostazione:** Abilita Colonna Fattura & Ricerca
- **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare le funzionalità del modulo. Quando abilitato, il modulo aggiungerà la colonna "Numero Fattura" all'elenco degli ordini e integrerà la funzionalità di ricerca. Quando disabilitato, l'elenco degli ordini tornerà al suo aspetto predefinito di PrestaShop.
- **Effetto della modifica di questa impostazione:**
  - *Quando abilitato (SÌ):* Una nuova colonna intitolata "Numero Fattura" apparirà nel tuo Back Office sotto **Ordini > Ordini**. Questa colonna visualizzerà il numero di fattura per ogni ordine (se è stata generata una fattura). Inoltre, la barra di ricerca nella pagina Ordini ti consentirà ora di cercare per numero di fattura.
  - *Quando disabilitato (NO):* La colonna "Numero Fattura" verrà rimossa dall'elenco degli ordini e la possibilità di cercare per numero di fattura verrà disattivata. L'elenco degli ordini apparirà esattamente come prima di installare questo modulo.
- **Valore consigliato:** **SÌ**. Per beneficiare delle funzionalità del modulo, dovresti abilitarlo.
- **Scenario / esempio per il commerciante:** Se desideri trovare rapidamente tutti gli ordini relativi a una fattura specifica (es. "INV00123"), abiliteresti questa impostazione. Quindi, navigheresti su **Ordini > Ordini**, digiteresti "INV00123" nella barra di ricerca e il sistema filtrerebbe l'elenco per mostrare solo quell'ordine. Se lo disabiliti, dovresti cliccare manualmente su ogni ordine per controllare il suo numero di fattura, il che richiede molto tempo.

### 2.2 Tabella di Riferimento Rapido della Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Abilita Colonna Fattura & Ricerca | SÌ | Attiva/disattiva la colonna fattura e la funzionalità di ricerca nell'elenco Ordini nel Back Office. |

## 3. Risoluzione dei Problemi del Commerciante e Domande Frequenti (FAQ)

**D: Ho abilitato il modulo, ma non vedo la colonna "Numero Fattura" o la ricerca non funziona.**
R:

1.  **Svuota Cache:** Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota la cache" nell'angolo in alto a destra. A volte PrestaShop ha bisogno di un aggiornamento della cache per visualizzare nuovi elementi.
2.  **Controlla lo Stato del Modulo:** Ricontrolla che il modulo sia effettivamente "Abilitato" nella sua pagina di configurazione.
3.  **Versione PrestaShop:** Assicurati che la tua versione di PrestaShop sia compatibile con il modulo (1.7.x, 8.x, 9.x).
4.  **Cache del Browser:** Prova a svuotare la cache del tuo browser o a utilizzare una finestra in incognito per escludere problemi specifici del browser.

**D: I numeri di fattura mostrano "N/D" o sono vuoti per alcuni ordini.**
R: Ciò significa tipicamente che una fattura non è ancora stata generata per quegli ordini specifici in PrestaShop. Il modulo visualizza il numero di fattura solo se esiste nel database di PrestaShop. Dovrai generare manualmente la fattura per quegli ordini tramite il processo di gestione degli ordini standard di PrestaShop.

**D: Questo modulo rallenterà il mio Back Office?**
R: No, il modulo è progettato per essere leggero ed efficiente. Estende principalmente una funzionalità esistente di PrestaShop (l'elenco degli ordini) piuttosto che aggiungere nuovi processi pesanti. Il suo impatto sulle prestazioni dovrebbe essere trascurabile.

**D: Posso personalizzare la posizione della colonna "Numero Fattura"?**
R: Il modulo posiziona la colonna in una posizione logica all'interno dell'elenco degli ordini. La personalizzazione diretta dell'ordine delle colonne non è una funzionalità integrata di questo modulo. Per modifiche avanzate del layout, di solito sarebbe necessario uno sviluppo di temi personalizzati o un altro modulo specializzato.

**D: Questo modulo crea nuove fatture?**
R: No, questo modulo non genera fatture. Visualizza e consente solo la ricerca per numeri di fattura che sono già stati generati dalla funzionalità principale di PrestaShop.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

### 4.1 Panoramica dell'Architettura

Il modulo "Colonna Fattura Elenco Ordini & Ricerca" (`olistinv`) è un classico modulo PrestaShop che estende la funzionalità principale agganciandosi ai punti di visualizzazione e azione esistenti all'interno del Back Office. Modifica principalmente la vista elenco del controller `AdminOrders` per aggiungere una nuova colonna e migliora le capacità di ricerca senza introdurre nuove tabelle di database o complesse interazioni con il front-office. La sua semplicità risiede nello sfruttare il sistema di hook di PrestaShop e nell'override della logica del template dove necessario.

### 4.2 Controller (`controllers/`)

Questo modulo non introduce alcun controller front-office o back-office personalizzato. Tutta la sua logica è contenuta nel file principale del modulo, `olistinv/index.php`, ed eseguita tramite hook.

### 4.3 Classi e Modelli Core (`classes/`)

Questo modulo non definisce alcuna classe personalizzata o `ObjectModel`. Interagisce direttamente con le classi core e le strutture di database esistenti di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo non include alcun file JavaScript personalizzato. La funzionalità di ricerca è integrata modificando il comportamento del modulo di ricerca esistente, che è gestito dal JS core di PrestaShop.

### 4.5 Fogli di Stile CSS (`views/css/`)

Questo modulo non include alcun file CSS personalizzato. La nuova colonna erediterà lo stile delle tabelle esistenti del Back Office di PrestaShop.

### 4.6 Struttura del Template Smarty (`views/templates/`)

Questo modulo non include alcun file di template Smarty personalizzato. Raggiunge la sua funzionalità iniettando dinamicamente il contenuto nei template PrestaShop esistenti tramite hook, in particolare modificando la visualizzazione dell'elenco `AdminOrders`.

### 4.7 Schema del Database e Mappa degli Hook

- **Tabelle del Database**: Questo modulo non crea nuove tabelle del database. Legge dalla tabella `ps_orders` (in particolare il campo `invoice_number`) e potenzialmente da `ps_order_invoice` per i dettagli della fattura, e memorizza la sua configurazione in `ps_configuration`.
- **Tabella degli Hook Registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayAdminOrderListHeader` | Renderizza prima dell'intestazione della tabella dell'elenco ordini nel Back Office. | Utilizzato per aggiungere l'intestazione della colonna "Numero Fattura" all'elenco ordini. |
| `displayAdminOrderList` | Renderizza per ogni riga (ordine) nella tabella dell'elenco ordini nel Back Office. | Utilizzato per visualizzare il numero di fattura effettivo per ogni ordine nella colonna appena aggiunta. |
| `actionAdminOrdersListingFieldsModifier` | Modifica l'array di campi utilizzato per costruire la query e la visualizzazione dell'elenco ordini. | Utilizzato per aggiungere il campo `invoice_number` all'elenco dei campi ricercabili e visualizzabili per il controller `AdminOrders`. Questo è cruciale sia per la visualizzazione della colonna che per l'abilitazione della ricerca. |
| `actionAdminOrdersFilterModifier` | Modifica la query di filtro per l'elenco ordini. | Utilizzato per estendere la funzionalità di ricerca per includere il campo `invoice_number` quando viene inviata una query di ricerca. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Colonna Fattura Elenco Ordini & Ricerca", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda riguardante la funzionalità del modulo.
