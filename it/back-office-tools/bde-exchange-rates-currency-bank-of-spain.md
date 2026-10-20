---
title: "BdE Tassi di Cambio & Valuta (Banca di Spagna) - Manuale Commerciante & Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop BdE Tassi di Cambio & Valuta (Banca di Spagna) di MyPresta.eu."
sidebar:
  label: "BdE Tassi di Cambio & Valuta (Banca di Spagna) - Manuale Commerciante & Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo BdE Exchange Rates & Currency (Bank of Spain) su MyPresta.eu](https://mypresta.eu/modules/administration-tools/bde-exchange-rates-currency-bank-of-spain.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/bde-exchange-rates-currency-bank-of-spain/)
>
> ---


# BdE Tassi di Cambio & Valuta (Banca di Spagna)

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Estensioni PHP standard come cURL (per il recupero di dati esterni), JSON (per l'elaborazione dei dati) e OpenSSL (per connessioni sicure) sono tipicamente richieste e sono standard sulla maggior parte degli ambienti di hosting moderni.

## 2. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" verrai indirizzato alla pagina delle impostazioni principali del modulo "BdE Tassi di Cambio & Valuta (Banca di Spagna)". Qui è dove controlli come il modulo recupera e applica i tassi di cambio.

#### **Aggiornamenti Live MyPresta.eu**

- **Cosa fa questa impostazione:** Questa sezione ti permette di gestire la connessione del modulo a MyPresta.eu per aggiornamenti automatici e supporto.
- **Effetto della modifica di questa impostazione:**
  - *Inserendo il tuo ID ordine MyPresta.eu e l'email:* Abilita il modulo a controllare nuove versioni e ricevere aggiornamenti direttamente da MyPresta.eu. Questo assicura che tu abbia sempre le ultime funzionalità e correzioni di bug.
  - *Lasciandolo vuoto:* Il modulo non sarà in grado di controllare gli aggiornamenti automatici. Dovresti scaricare e installare manualmente le nuove versioni dal tuo account MyPresta.eu.
- **Valore consigliato:** Inserisci sempre il tuo ID ordine MyPresta.eu e l'indirizzo email associato al tuo acquisto. Questo è cruciale per ricevere aggiornamenti e supporto tempestivi.
- **Scenario / esempio commerciante:** Hai acquistato il modulo usando `tua.email@example.com` e il tuo ID ordine era `MP12345`. Inserendo questi dettagli qui, sarai avvisato direttamente nel tuo back office PrestaShop quando viene rilasciata una nuova versione del modulo, e potrai aggiornare con un solo clic.

#### **URL del CRON Job**

- **Cosa fa questa impostazione:** Visualizza un URL unico che puoi utilizzare per impostare un "CRON job" sul tuo server. Un CRON job è un'attività pianificata che esegue automaticamente un comando o un URL specifico a intervalli regolari (es. una volta al giorno).
- **Effetto della modifica di questa impostazione:**
  - *Impostando un CRON job con questo URL:* Il modulo recupererà automaticamente gli ultimi tassi di cambio dalla Banca di Spagna alla frequenza che definisci (es. giornalmente). Questo assicura che i tuoi tassi di valuta siano sempre aggiornati senza alcun intervento manuale.
  - *Non impostando un CRON job:* I tassi di cambio non verranno aggiornati automaticamente. Dovresti visitare manualmente questo URL nel tuo browser ogni volta che desideri aggiornare i tassi, il che è altamente impraticabile e vanifica lo scopo dell'automazione.
- **Valore consigliato:** Copia questo URL e imposta un CRON job giornaliero sul tuo server di hosting. La maggior parte dei pannelli di controllo di hosting (come cPanel, Plesk) ha una sezione "Cron Jobs" dove puoi facilmente aggiungere questo URL per eseguirlo una volta ogni 24 ore.
- **Scenario / esempio commerciante:** Vuoi che i tuoi tassi di cambio Euro si aggiornino ogni mattina alle 3:00. Copi l'URL CRON fornito, vai al tuo pannello di controllo di hosting, crei un nuovo CRON job, incolli l'URL e lo imposti per l'esecuzione giornaliera alle 3:00. Da quel momento in poi, i tuoi tassi verranno aggiornati automaticamente.

#### **Margine di Adeguamento (%)**

- **Cosa fa questa impostazione:** Ti permette di aggiungere una piccola percentuale di margine ai tassi di cambio recuperati. Questo può essere utile per coprire potenziali commissioni di transazione, costi di conversione valuta, o semplicemente per darti un piccolo cuscinetto.
- **Effetto della modifica di questa impostazione:**
  - *Impostando una percentuale positiva (es. 2%):* Il modulo aumenterà il tasso di cambio ufficiale di quella percentuale. Ad esempio, se il tasso ufficiale è 1 EUR = 1.10 USD, e imposti un margine del 2%, il modulo userà 1 EUR = 1.122 USD (1.10 * 1.02). Ciò significa che i prodotti prezzati in EUR appariranno leggermente più costosi quando convertiti in USD.
  - *Impostando 0% (predefinito):* Il modulo utilizzerà i tassi di cambio ufficiali esatti senza alcuna regolazione.
- **Valore consigliato:** 0% a meno che tu non abbia ragioni commerciali specifiche (come la copertura delle commissioni bancarie) per aggiungere un margine. La trasparenza è spesso la migliore per la fiducia del cliente.
- **Scenario / esempio commerciante:** Il tuo gateway di pagamento addebita una commissione dell'1,5% per le conversioni di valuta internazionali. Per compensare questo, potresti impostare il Margine di Adeguamento all'1,5%. Questo assicura che i tuoi prezzi convertiti tengano leggermente conto di questo costo.

#### **Aggiorna Tassi di Valuta**

- **Cosa fa questa impostazione:** Questo è un pulsante di attivazione manuale per recuperare e aggiornare immediatamente tutti i tassi di cambio dalla Banca di Spagna.
- **Effetto della modifica di questa impostazione:**
  - *Cliccando il pulsante:* Il modulo si connetterà istantaneamente alla Banca di Spagna, recupererà gli ultimi tassi e li aggiornerà nel tuo negozio PrestaShop. Questo è utile per test o per un aggiornamento immediato al di fuori del tuo programma CRON job.
- **Valore consigliato:** Usa questo pulsante per i test di configurazione iniziale o se hai bisogno di un aggiornamento immediato. Per gli aggiornamenti regolari, affidati al CRON job.
- **Scenario / esempio commerciante:** Hai appena installato il modulo e vuoi verificare che funzioni correttamente e recuperi gli ultimi tassi. Clicchi questo pulsante per vedere l'effetto immediato.

### 2.2 Tabella di Riferimento Rapido della Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | ID Ordine MyPresta.eu | Il tuo ID Ordine | Abilita gli aggiornamenti automatici del modulo e il supporto. |
| Configurazione Modulo | Email MyPresta.eu | La tua Email | Abilita gli aggiornamenti automatici del modulo e il supporto. |
| Configurazione Modulo | URL del CRON Job | (URL Unico) | Imposta un CRON job giornaliero con questo URL per aggiornamenti automatici dei tassi. |
| Configurazione Modulo | Margine di Adeguamento (%) | 0% | Aggiunge un buffer percentuale ai tassi di cambio (es. per commissioni). |
| Configurazione Modulo | Aggiorna Tassi di Valuta | Clicca per attivare | Recupera e aggiorna manualmente i tassi di cambio immediatamente. |

## 3. Risoluzione dei Problemi del Commerciante e Domande Frequenti (FAQ)

**D: I miei tassi di valuta non si aggiornano automaticamente.**
R:

1. **Controlla la configurazione del tuo CRON job:** Ricontrolla di aver impostato correttamente il CRON job sul tuo server di hosting utilizzando l'URL esatto fornito nella configurazione del modulo. Assicurati che sia programmato per essere eseguito almeno una volta al giorno.
2. **Verifica l'esecuzione del CRON job:** Alcuni pannelli di hosting forniscono log per l'esecuzione dei CRON job. Controlla questi log per vedere se il CRON job è effettivamente in esecuzione e se ci sono errori.
3. **Connettività del server:** Assicurati che il tuo server abbia accesso in uscita a siti web esterni (specificamente all'API della Banca di Spagna). A volte i firewall possono bloccarlo. Contatta il tuo provider di hosting se sospetti che questo sia il problema.
4. **Configurazione del modulo:** Assicurati che i tuoi dettagli MyPresta.eu siano inseriti correttamente per potenziali problemi di aggiornamento.

**D: I prezzi in EUR sembrano leggermente sbagliati, anche dopo un aggiornamento.**
R:

1. **Controlla il Margine di Adeguamento:** Rivedi l'impostazione "Margine di Adeguamento (%)" nella configurazione del modulo. Se è impostato su un valore maggiore di 0, i tuoi prezzi verranno adeguati di quella percentuale. Impostalo su 0% se desideri tassi ufficiali esatti.
2. **Arrotondamento PrestaShop:** PrestaShop ha le sue regole di arrotondamento per i prezzi. Assicurati che le tue impostazioni di valuta in **Internazionale > Valute** siano configurate con la precisione decimale desiderata.
3. **Cache:** Svuota la cache di PrestaShop (Parametri Avanzati > Prestazioni) e la cache del tuo browser.

**D: Cosa succede nei giorni festivi o nei fine settimana quando la Banca di Spagna non pubblica nuovi tassi?**
R: Il modulo è progettato per gestire questo in modo intelligente. Se i nuovi tassi non sono disponibili per un dato giorno, continuerà a utilizzare gli ultimi tassi recuperati con successo. Una volta pubblicati i nuovi tassi, il modulo li aggiornerà alla sua prossima esecuzione programmata.

**D: Posso usare questo modulo con altri moduli di valuta?**
R: Questo modulo si concentra specificamente sul recupero e l'applicazione dei tassi ufficiali della Banca di Spagna. Generalmente funziona bene insieme alle funzionalità multi-valuta native di PrestaShop. Tuttavia, se hai altri moduli che *tentano anche* di recuperare o sovrascrivere i tassi di cambio da fonti diverse, potrebbero esserci conflitti. È meglio utilizzare una fonte primaria per gli aggiornamenti dei tassi di cambio per evitare incongruenze.

**D: Vedo una sezione "Aggiornamenti MyPresta.eu". A cosa serve?**
R: Questa sezione ti permette di inserire il tuo ID ordine MyPresta.eu e l'email. Questo abilita il modulo a controllare nuove versioni e ricevere aggiornamenti direttamente da MyPresta.eu, assicurandoti di avere sempre le ultime funzionalità e correzioni di bug. È altamente consigliato compilarla.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

### 4.1 Panoramica dell'Architettura

Il modulo `BdE Exchange Rates & Currency` è un modulo PrestaShop leggero progettato principalmente per integrarsi con l'API ufficiale dei tassi di cambio della Banca di Spagna. Segue una struttura standard dei moduli PrestaShop, sfruttando la classe `Module` per l'installazione e la configurazione, e `ModuleFrontController` per la gestione delle richieste CRON job. La sua funzionalità principale ruota attorno al recupero di dati esterni, alla loro analisi e all'aggiornamento dei tassi di cambio nativi della `Currency` di PrestaShop.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

- **`controllers/front/cronjob.php`**
  - **Nome classe e classe padre:** `BderatesCronjobModuleFrontController` che estende `ModuleFrontController`.
  - **Responsabilità:** Questo controller è il punto di ingresso per il CRON job programmato. Quando viene richiamato, avvia il processo di recupero degli ultimi tassi di cambio dalla Banca di Spagna. Gestisce la richiesta API, analizza la risposta e aggiorna i tassi di cambio per le valute configurate in PrestaShop. È progettato per essere chiamato esternamente da uno scheduler CRON lato server e tipicamente restituisce un semplice messaggio di successo/fallimento.
- **`controllers/front/index.php`**
  - **Nome classe e classe padre:** `BderatesIndexModuleFrontController` che estende `ModuleFrontController`.
  - **Responsabilità:** Questo è un controller segnaposto, spesso incluso nei moduli ma non attivamente utilizzato nella funzionalità principale di questo modulo specifico. Potrebbe essere presente per scopi di routing o come punto di ingresso predefinito, ma la logica primaria per gli aggiornamenti dei tassi è all'interno di `cronjob.php`.

#### Controller Amministrativi Back-Office

Questo modulo non implementa alcun controller amministrativo Back-Office personalizzato. Tutta la configurazione è gestita tramite il metodo `getContent()` del modulo principale.

### 4.3 Classi Core e Modelli (`classes/`)

Questo modulo non definisce alcuna classe personalizzata o `ObjectModel` nella directory `classes/`. Interagisce direttamente con la classe `Currency` di PrestaShop per aggiornare i tassi di cambio.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo non include alcun file JavaScript personalizzato.

### 4.5 Fogli di Stile CSS (`views/css/`)

Questo modulo non include alcun file CSS personalizzato.

### 4.6 Struttura del Template Smarty (`views/templates/`)

#### Template Admin (`views/templates/admin/`)

- **`views/templates/admin/admin.tpl`**
  - **Scopo:** Questo template viene utilizzato per renderizzare il modulo di configurazione del modulo nel Back Office di PrestaShop. Visualizza i campi di input per gli aggiornamenti MyPresta.eu, l'URL del CRON job, l'adeguamento del margine e il pulsante di aggiornamento manuale.
  - **Contesto:** Renderizzato dal metodo `getContent()` del file del modulo principale `bderates.php`.
  - **Elementi chiave:** Elementi del modulo per le impostazioni `mypresta_updates`, `update_`, `updatev_`, `currency_`.

### 4.7 Schema del Database e Mappa degli Hook

#### Tabelle del Database

Questo modulo non crea alcuna tabella SQL personalizzata. Memorizza le sue impostazioni di configurazione direttamente nella tabella `ps_configuration` di PrestaShop utilizzando chiavi come:

- `BDERATES_MYPRESTA_ID`
- `BDERATES_MYPRESTA_EMAIL`
- `BDERATES_MARGIN`
- `BDERATES_LAST_UPDATE`

#### Tabella degli Hook Registrati

| Nome Hook | Tempistica di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Non attivamente utilizzato per l'output visivo da questo modulo, ma spesso registrato dai moduli per la configurazione generale o il caricamento di risorse. |
| `displayRightColumn` | Nella colonna destra delle pagine del front-office. | Non attivamente utilizzato per l'output visivo da questo modulo. |
| `displayLeftColumn` | Nella colonna sinistra delle pagine del front-office. | Non attivamente utilizzato per l'output visivo da questo modulo. |
| `displayFooter` | Nella sezione footer di ogni pagina del front-office. | Non attivamente utilizzato per l'output visivo da questo modulo. |
| `displayProductAdditionalInfo` | Sulla pagina del prodotto, sotto le informazioni principali del prodotto. | Non attivamente utilizzato per l'output visivo da questo modulo. |
| `actionUpdateCurrency` | Attivato dopo l'aggiornamento del tasso di cambio di una valuta. | Questo modulo *attiva* questo hook quando aggiorna i tassi di valuta, consentendo ad altri moduli di reagire al cambiamento. |
| `actionCronJob` | Un hook personalizzato spesso utilizzato dai moduli per registrare le loro attività CRON. | Il controller `cronjob.php` del modulo è il meccanismo primario per gli aggiornamenti programmati, ma questo hook potrebbe essere registrato per compatibilità o espansioni future. |

## 5. Supporto Ufficiale e Aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e le ultime versioni del modulo "BdE Tassi di Cambio & Valuta (Banca di Spagna)", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assistere con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e all'integrazione del modulo.
