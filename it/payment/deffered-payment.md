---
title: "Pagamento Differito - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Pagamento Differito di MyPresta.eu."
sidebar:
  label: "Pagamento Differito - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Deffered Payment su MyPresta.eu](https://mypresta.eu/modules/payment-process/deffered-payment.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/payment/deffered-payment/)
>
> ---


# Pagamento Differito

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono in genere richieste per PrestaShop stesso e generalmente sufficienti per questo modulo. Non sono necessarie estensioni insolite.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Pagamento Differito)

Questa è la schermata di configurazione principale in cui definisci il comportamento principale del modulo Pagamento Differito.

-   **Posizione del menu:** Back Office > Moduli > Gestione moduli > Cerca "Pagamento Differito" > Clicca su "Configura"

#### Impostazioni Generali

| Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- |
| **Abilita Pagamento Differito** | SÌ | **Cosa fa questa impostazione:** Questo è l'interruttore principale per il modulo. **Effetto della modifica di questa impostazione:** *Quando abilitato:* L'opzione Pagamento Differito sarà disponibile al checkout per i clienti idonei. *Quando disabilitato:* L'opzione Pagamento Differito sarà nascosta a tutti i clienti, indipendentemente dalle altre impostazioni. **Valore consigliato:** SÌ (per utilizzare il modulo). **Scenario del commerciante:** Abilitalo quando sei pronto a offrire questo metodo di pagamento. |
| **Gruppi di Clienti Consentiti** | (Seleziona i gruppi pertinenti) | **Cosa fa questa impostazione:** Determina quali gruppi di clienti possono vedere e utilizzare l'opzione Pagamento Differito. **Effetto della modifica di questa impostazione:** *Quando selezionato:* Solo i clienti appartenenti ai gruppi scelti vedranno Pagamento Differito al checkout. *Quando non selezionato:* I clienti nei gruppi non selezionati non vedranno questa opzione. **Valore consigliato:** Seleziona gruppi specifici (ad esempio, "Grossisti", "Clienti VIP"). Evita "Tutti i clienti" a meno che tu non intenda offrire il pagamento differito a tutti. **Scenario del commerciante:** Hai un gruppo "Clienti B2B". Seleziona solo questo gruppo in modo che solo i tuoi clienti aziendali possano utilizzare il pagamento differito. |
| **Giorni di Scadenza del Pagamento** | 30 | **Cosa fa questa impostazione:** Definisce il numero di giorni dopo l'effettuazione di un ordine entro cui il pagamento è dovuto. **Effetto della modifica di questa impostazione:** Questo valore verrà utilizzato per calcolare la data di scadenza del pagamento visualizzata al cliente e per il tracciamento interno. **Valore consigliato:** 30 (comune per termini net-30), 7, 14, 60, ecc., a seconda della tua politica aziendale. **Scenario del commerciante:** Imposta a 30 per termini di pagamento "Net 30". |
| **Totale Minimo Ordine per Pagamento Differito** | 0.00 | **Cosa fa questa impostazione:** Imposta un valore minimo dell'ordine (nella tua valuta predefinita) che un ordine deve raggiungere per qualificarsi per il pagamento differito. **Effetto della modifica di questa impostazione:** *Se il totale dell'ordine è inferiore a questo valore:* Il Pagamento Differito non sarà disponibile, anche per i gruppi di clienti idonei. *Se il totale dell'ordine è superiore o uguale a questo valore:* Il Pagamento Differito sarà disponibile (se altre condizioni sono soddisfatte). **Valore consigliato:** 0.00 (nessun minimo) o un valore specifico (ad esempio, 100.00 per B2B). **Scenario del commerciante:** Vuoi offrire il pagamento differito solo per ordini di grandi dimensioni, quindi lo imposti a 500.00. |
| **Stato Ordine per Pagamento Differito** | In attesa di pagamento differito | **Cosa fa questa impostazione:** Specifica lo stato iniziale dell'ordine che verrà assegnato agli ordini effettuati utilizzando il metodo di Pagamento Differito. **Effetto della modifica di questa impostazione:** Questo stato sarà visibile nella tua lista ordini del Back Office e al cliente nella sua cronologia ordini. Ti aiuta a identificare rapidamente gli ordini in attesa di pagamento. **Valore consigliato:** Crea uno stato specifico come "In attesa di pagamento differito" o "Pagamento dovuto" in **Stati Ordine** (Back Office > Parametri Negozio > Impostazioni Ordine > Stati) e selezionalo qui. **Scenario del commerciante:** Vuoi uno stato chiaro per differenziare questi ordini da "In attesa di bonifico bancario" o "Pagamento accettato". |
| **URL Cron Job** | (URL visualizzato) | **Cosa fa questa impostazione:** Questo URL viene utilizzato per attivare attività automatizzate relative ai pagamenti differiti (ad esempio, controllo delle date di scadenza, invio di promemoria, se tali funzionalità sono implementate o estese). **Effetto della modifica di questa impostazione:** Questo è un campo di sola lettura. Dovresti impostare un cron job sul tuo server per visitare regolarmente questo URL (ad esempio, una volta al giorno). **Valore consigliato:** Copia questo URL e aggiungilo allo scheduler dei cron job del tuo server. **Scenario del commerciante:** Vuoi automatizzare eventuali processi in background che il modulo potrebbe avere, come l'aggiornamento degli stati degli ordini o l'invio di notifiche. |

#### Prodotti Target (Idoneità Prodotti Specifici)

Questa sezione ti consente di limitare il pagamento differito a prodotti o categorie specifici.

| Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- |
| **Applica solo a prodotti specifici** | NO | **Cosa fa questa impostazione:** Determina se l'opzione di pagamento differito è limitata agli ordini contenenti solo prodotti specifici. **Effetto della modifica di questa impostazione:** *Quando abilitato:* L'opzione "Pagamento Differito" apparirà al checkout solo se *tutti* i prodotti nel carrello sono nella tua lista approvata. *Quando disabilitato:* Il modulo si applicherà in base ai gruppi di clienti e al totale minimo dell'ordine, indipendentemente dai prodotti specifici. **Valore consigliato:** NO (per uso generale) o SÌ (per scenari altamente specifici). **Scenario del commerciante:** Offri il pagamento differito solo per i tuoi prodotti "Servizi Premium" di alto valore. Abiliti questa opzione e aggiungi quei prodotti di seguito. |
| **Prodotti consentiti per il pagamento differito** | (Vuoto) | **Cosa fa questa impostazione:** Se "Applica solo a prodotti specifici" è abilitato, questo campo ti consente di cercare e aggiungere prodotti specifici. **Effetto della modifica di questa impostazione:** Solo gli ordini contenenti questi prodotti (e nessun altro) saranno idonei per il pagamento differito. **Valore consigliato:** Aggiungi prodotti pertinenti se "Applica solo a prodotti specifici" è SÌ. **Scenario del commerciante:** Aggiungi "Prodotto A" e "Prodotto B". Se il carrello di un cliente contiene "Prodotto A" e "Prodotto C", il pagamento differito non sarà disponibile. Se contiene solo "Prodotto A", lo sarà. |

### 2.2 Schermate di Amministrazione Dedicate e Viste Controller

Il modulo aggiunge diverse nuove sezioni al menu del tuo Back Office di PrestaShop per gestire i pagamenti differiti.

#### 2.2.1 Utenti Pagamento Differito (Back Office > Pagamento Differito > Utenti Pagamento Differito)

Questa schermata ti consente di gestire i permessi dei singoli clienti per il pagamento differito, sovrascrivendo o integrando le impostazioni dei gruppi di clienti.

-   **Nome schermata e posizione del menu:** Back Office > Pagamento Differito > Utenti Pagamento Differito
-   **Azioni e impostazioni disponibili:**
    *   **Tabella di elenco:** Visualizza un elenco di clienti a cui è stato specificamente concesso o negato l'accesso al pagamento differito.
    *   **Aggiungi nuovo / Modifica utente:**
        *   **Ricerca cliente:** Trova un cliente specifico per nome o email.
        *   **Abilita Pagamento Differito:** Interruttore SÌ/NO per concedere o revocare l'accesso al pagamento differito per questo singolo cliente.
        *   **Giorni di Scadenza del Pagamento (Sovrascrittura):** Opzionalmente imposta un numero personalizzato di giorni di scadenza del pagamento per questo cliente specifico, sovrascrivendo l'impostazione globale.
        *   **Limite di Credito:** Imposta un importo massimo in sospeso (nella tua valuta predefinita, basato su `PS_CURRENCY_DEFAULT`) che questo cliente può avere su ordini con pagamento differito.
    *   **Effetto delle modifiche:**
        *   L'aggiunta di un cliente e l'abilitazione del pagamento differito gli concede l'accesso, anche se il suo gruppo non è selezionato nella configurazione principale del modulo.
        *   La disabilitazione per un cliente revoca il suo accesso, anche se il suo gruppo è selezionato.
        *   I giorni di scadenza personalizzati e i limiti di credito si applicano solo a quel cliente specifico.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Usa questa sezione per concedere termini di pagamento differito speciali a singoli clienti VIP o per bloccare clienti problematici.
    2.  Rivedi regolarmente i limiti di credito per gli utenti di pagamento differito ad alto volume.

#### 2.2.2 Registro Attività Pagamento Differito (Back Office > Pagamento Differito > Registro Attività)

Questa schermata fornisce una cronologia delle azioni e degli eventi relativi ai pagamenti differiti.

-   **Nome schermata e posizione del menu:** Back Office > Pagamento Differito > Registro Attività
-   **Azioni e impostazioni disponibili:**
    *   **Tabella di elenco:** Visualizza un registro degli eventi, che potrebbe includere:
        *   Quando è stato effettuato un ordine con pagamento differito.
        *   Quando un pagamento è stato contrassegnato come ricevuto.
        *   Modifiche alle impostazioni degli utenti di pagamento differito.
        *   Esecuzioni di cron job.
    *   **Colonne:** In genere include Data/Ora, Tipo di Evento, Ordine/Cliente Correlato, Descrizione.
-   **Effetto delle modifiche:** Questo è un registro di sola lettura. Non puoi modificare direttamente le voci qui, ma fornisce preziose informazioni per l'audit e la risoluzione dei problemi.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Controlla periodicamente il registro per monitorare l'attività di pagamento differito e assicurarti che tutto funzioni senza intoppi.
    2.  Usalo per indagare su eventuali problemi segnalati dai clienti riguardo ai loro ordini con pagamento differito.

#### 2.2.3 Dashboard (Back Office > Pagamento Differito > Dashboard)

Questa schermata (probabilmente rappresentata da `defpay/controllers/admin/index.php`) fornirebbe in genere una panoramica o un riepilogo delle attività di pagamento differito.

-   **Nome schermata e posizione del menu:** Back Office > Pagamento Differito > Dashboard (o voce di menu principale "Pagamento Differito")
-   **Azioni e impostazioni disponibili:**
    *   **Vista Griglia / Gestione:** Questa schermata probabilmente presenta statistiche chiave, pagamenti in sospeso, pagamenti scaduti o un rapido riepilogo degli ordini con pagamento differito. Potrebbe offrire filtri o funzionalità di ricerca.
-   **Effetto delle modifiche:** Questa è principalmente una dashboard informativa. Qualsiasi azione intrapresa (ad esempio, contrassegnare un ordine come pagato) reindirizzerebbe in genere alla pagina dell'ordine specifico o a un'altra schermata di gestione.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Usala come panoramica principale per identificare rapidamente gli ordini che richiedono attenzione (ad esempio, date di scadenza imminenti, pagamenti scaduti).
    2.  Monitora lo stato generale del tuo sistema di pagamento differito.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
|---|---|---|---|
| **Configurazione Modulo** | Abilita Pagamento Differito | SÌ | Interruttore principale per il metodo di pagamento. |
| | Gruppi di Clienti Consentiti | (Seleziona i gruppi pertinenti) | Limita l'accesso a segmenti di clienti specifici. |
| | Giorni di Scadenza del Pagamento | 30 | Imposta il termine di pagamento predefinito in giorni. |
| | Totale Minimo Ordine per Pagamento Differito | 0.00 | Valore minimo del carrello per l'idoneità al pagamento differito. |
| | Stato Ordine per Pagamento Differito | In attesa di pagamento differito | Stato iniziale per gli ordini effettuati con questo metodo. |
| | URL Cron Job | (URL visualizzato) | URL per le attività di automazione lato server. |
| | Applica solo a prodotti specifici | NO | Limita il pagamento differito a prodotti specifici. |
| | Prodotti consentiti per il pagamento differito | (Vuoto) | Elenco di prodotti idonei se "Applica solo a prodotti specifici" è SÌ. |
| **Utenti Pagamento Differito** | Ricerca Cliente | N/A | Trova e gestisci l'accesso dei singoli clienti. |
| | Abilita Pagamento Differito (per utente) | SÌ/NO | Sovrascrittura individuale per l'accesso al pagamento differito. |
| | Giorni di Scadenza del Pagamento (Sovrascrittura) | (Vuoto per globale) | Termini di pagamento personalizzati per un cliente specifico. |
| | Limite di Credito | (Vuoto per nessun limite) | Importo massimo in sospeso per un cliente specifico. |
| **Registro Attività** | N/A | N/A | Registro di sola lettura degli eventi di pagamento differito. |
| **Dashboard** | N/A | N/A | Panoramica degli ordini con pagamento differito e delle statistiche. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Perché il Pagamento Differito non viene visualizzato per i miei clienti al checkout?**
R:

1.  **Il modulo è abilitato?** Controlla "Abilita Pagamento Differito" nella configurazione del modulo.
2.  **I gruppi di clienti sono corretti?** Assicurati che il cliente sia loggato e appartenga a uno dei "Gruppi di Clienti Consentiti" selezionati nelle impostazioni del modulo.
3.  **Totale Minimo Ordine:** Il totale del carrello è superiore al "Totale Minimo Ordine per Pagamento Differito"?
4.  **Prodotti Specifici:** Se "Applica solo a prodotti specifici" è abilitato, il carrello contiene *solo* prodotti dalla tua lista approvata?
5.  **Impostazioni Utente Individuali:** Controlla "Utenti Pagamento Differito" per vedere se il cliente è stato disabilitato individualmente o ha delle sovrascritture specifiche.
6.  **Cache:** Svuota la cache di PrestaShop (Parametri Avanzati > Prestazioni) e la cache del tuo browser.

**D: Come posso cambiare lo stato dell'ordine una volta ricevuto un pagamento differito?**
R: Dovrai aggiornare manualmente lo stato dell'ordine nel Back Office di PrestaShop. Vai su **Ordini > Ordini**, trova l'ordine pertinente e cambia il suo stato da "In attesa di pagamento differito" (o qualsiasi cosa tu abbia configurato) a "Pagamento accettato" o "Consegnato" a seconda dei casi.

**D: Posso impostare giorni di scadenza del pagamento diversi per clienti diversi?**
R: Sì! Usa la schermata "Utenti Pagamento Differito". Puoi cercare un cliente specifico e impostare un "Giorni di Scadenza del Pagamento (Sovrascrittura)" personalizzato per lui, che avrà la precedenza sull'impostazione globale.

**D: A cosa serve l'URL del Cron Job e devo configurarlo?**
R: L'URL del Cron Job serve per le attività automatizzate che il modulo potrebbe eseguire in background (ad esempio, controllo dei pagamenti scaduti, invio di notifiche, se implementato). Sebbene il modulo possa funzionare senza di esso per l'elaborazione di base dei pagamenti, è altamente consigliato configurarlo sul tuo server per garantire che tutte le funzionalità automatizzate funzionino correttamente. Il tuo host web o uno sviluppatore possono aiutarti a configurare un cron job per visitare questo URL quotidianamente.

**D: Il modulo è installato, ma non vedo la voce di menu "Pagamento Differito" nel Back Office.**
R:

1.  **Permessi:** Controlla i permessi del tuo dipendente (Parametri Avanzati > Team > Dipendenti > Modifica il tuo profilo > scheda Permessi). Assicurati di avere accesso al modulo "Pagamento Differito" e ai suoi controller di amministrazione associati.
2.  **Cache:** Svuota la cache di PrestaShop (Parametri Avanzati > Prestazioni).

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce un'analisi approfondita della struttura tecnica del modulo Pagamento Differito per sviluppatori e webmaster.

### 4.1 Panoramica dell'Architettura

Il modulo Pagamento Differito segue il modello MVC (Model-View-Controller) standard di PrestaShop. Si integra come modulo di pagamento, estendendo `PaymentModule` e fornendo controller amministrativi personalizzati per la gestione degli utenti e dei log dei pagamenti differiti. Sfrutta il sistema di configurazione di PrestaShop per le impostazioni e gli hook per la visualizzazione nel front-office e l'integrazione degli ordini nel back-office. Il modulo introduce tabelle di database personalizzate (`defpay_log`, `defpayuser`) per archiviare dati specifici sui pagamenti differiti.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

-   `defpay/controllers/front/cron.php`
    *   **Nome Classe:** `DefPayCronModuleFrontController` (estende `ModuleFrontController`)
    *   **Responsabilità:** Gestisce l'esecuzione delle attività del cron job. Questo controller è accessibile tramite l'`URL Cron Job` fornito nella configurazione del modulo. È progettato per essere chiamato periodicamente da uno scheduler cron lato server per eseguire operazioni in background come il controllo delle date di scadenza dei pagamenti, l'aggiornamento degli stati degli ordini o l'attivazione di notifiche.
-   `defpay/controllers/front/index.php`
    *   **Nome Classe:** `DefPayIndexModuleFrontController` (estende `ModuleFrontController`)
    *   **Responsabilità:** Un segnaposto o un controller frontale predefinito. Spesso utilizzato per il routing di base del modulo o se il modulo necessita di un punto di ingresso front-office predefinito che non corrisponde direttamente a un'azione specifica. In questo modulo, potrebbe non avere una funzione diretta rivolta all'utente.
-   `defpay/controllers/front/statement.php`
    *   **Nome Classe:** `DefPayStatementModuleFrontController` (estende `ModuleFrontController`)
    *   **Responsabilità:** Probabilmente gestisce la visualizzazione o la generazione di estratti conto di pagamento differito per i clienti. Potrebbe essere una pagina nell'area dell'account cliente che mostra i pagamenti in sospeso o un link per scaricare una fattura.
-   `defpay/controllers/front/validation.php`
    *   **Nome Classe:** `DefPayValidationModuleFrontController` (estende `ModuleFrontController`)
    *   **Responsabilità:** Il controller principale di validazione del pagamento. Quando un cliente seleziona "Pagamento Differito" al checkout e conferma l'ordine, questo controller elabora l'ordine, imposta lo stato dell'ordine appropriato e reindirizza il cliente alla pagina di conferma dell'ordine.

#### Controller Amministrativi Back-Office

-   `defpay/controllers/admin/AdminDefPayActivityLog.php`
    *   **Nome Classe:** `AdminDefPayActivityLogController` (estende `ModuleAdminController`)
    *   **Nome Tab:** `Registro Attività Pagamento Differito`
    *   **Entità Gestita:** `defpay_log` (tabella di database personalizzata)
    *   **Responsabilità:** Fornisce un'interfaccia di gestione dell'elenco per la tabella `defpay_log`. Visualizza una cronologia degli eventi relativi ai pagamenti differiti, come l'effettuazione degli ordini, le modifiche di stato o le azioni del cron job.
-   `defpay/controllers/admin/AdminDefPayUsers.php`
    *   **Nome Classe:** `AdminDefPayUsersController` (estende `ModuleAdminController`)
    *   **Nome Tab:** `Utenti Pagamento Differito`
    *   **Entità Gestita:** `defpayuser` (tabella di database personalizzata)
    *   **Responsabilità:** Gestisce le impostazioni individuali dei clienti per il pagamento differito. Consente agli amministratori di abilitare/disabilitare il pagamento differito per clienti specifici, impostare giorni di scadenza personalizzati e definire limiti di credito. Interagisce con la tabella `ps_currency` (tramite `PS_CURRENCY_DEFAULT`) per la valuta del limite di credito.
-   `defpay/controllers/admin/index.php`
    *   **Nome Classe:** `AdminDefPayDashboardController` (probabilmente, estende `ModuleAdminController`)
    *   **Nome Tab:** `Dashboard Pagamento Differito` (o voce di menu principale)
    *   **Entità Gestita:** Nessuna singola entità diretta; aggrega i dati.
    *   **Responsabilità:** Funge da dashboard principale o panoramica per il modulo Pagamento Differito nel Back Office. Probabilmente visualizza statistiche chiave, riepiloghi dei pagamenti in sospeso/scaduti e collegamenti rapidi ad altre sezioni di gestione.

### 4.3 Classi e Modelli Core (`classes/`)

Le informazioni sul modulo fornite non indicano classi personalizzate nella directory `classes/`. Ciò suggerisce che la logica principale del modulo, incluse le definizioni di `ObjectModel` per `defpay_log` e `defpayuser`, potrebbe essere direttamente incorporata nel file principale `defpay/cronjob.php` o all'interno dei controller amministrativi stessi. Questo è un approccio meno comune ma a volte utilizzato per moduli più semplici.

Se `defpay_log` e `defpayuser` sono effettivamente tabelle personalizzate, le loro definizioni `ObjectModel` (ad esempio, le classi `DefPayLog` e `DefPayUser`) si troverebbero tipicamente in `classes/`. In caso contrario, sono probabilmente definite inline o gestite direttamente tramite chiamate alla classe `Db`.

### 4.4 Risorse JavaScript (`views/js/`)

-   `defpay/lib/emailTemplatesManager/js/emailTemplatesManager.js`
    *   **Ambito:** Back-office.
    *   **Descrizione:** Probabilmente fornisce funzionalità per la gestione dei modelli di email all'interno della configurazione del modulo o di schermate amministrative specifiche. Ciò potrebbe includere campi modulo dinamici, anteprima dei modelli o salvataggio del contenuto dei modelli.
-   `defpay/lib/searchTool/views/js/autocomplete.js`
    *   **Ambito:** Back-office (ad esempio, `AdminDefPayUsers` per la ricerca clienti, o configurazione del modulo per la ricerca prodotti).
    *   **Descrizione:** Implementa una funzione di completamento automatico per gli input di ricerca, come la ricerca di clienti o prodotti. Ascolta l'input dell'utente, effettua chiamate AJAX per recuperare suggerimenti e li visualizza in un menu a discesa.
-   `defpay/tools/browser-demo-simulator.js`
    *   **Ambito:** Potenzialmente entrambi, ma più probabilmente per lo sviluppo/test.
    *   **Descrizione:** Uno script di utilità, possibilmente per simulare il comportamento del browser o le interazioni del modulo a scopo di test. Non tipicamente utilizzato in un ambiente di produzione.
-   `defpay/views/js/adminDefPayActivityPreview.js`
    *   **Ambito:** Back-office (`AdminDefPayActivityLog`).
    *   **Descrizione:** Fornisce funzionalità interattive per il registro attività, come l'espansione delle voci di registro, il filtraggio o l'anteprima dei dettagli di un'attività.
-   `defpay/views/js/adminDefPayCollections.js`
    *   **Ambito:** Back-office (probabilmente correlato alla gestione delle riscossioni dei pagamenti differiti).
    *   **Descrizione:** Implementa la logica JavaScript per un'interfaccia di gestione delle "riscossioni", che potrebbe comportare la marcatura dei pagamenti come ricevuti, l'invio di promemoria o la gestione degli account scaduti.
-   `defpay/views/js/adminDefPayDashboard.js`
    *   **Ambito:** Back-office (Dashboard).
    *   **Descrizione:** Alimenta gli elementi interattivi della dashboard dei pagamenti differiti, come grafici dinamici, filtraggio dei dati o aggiornamenti AJAX per le statistiche.
-   `defpay/views/js/adminDefPayPortfolio.js`
    *   **Ambito:** Back-office.
    *   **Descrizione:** Probabilmente correlato alla gestione di un "portafoglio" di account o ordini con pagamento differito, offrendo eventualmente filtraggio avanzato, reporting o azioni in blocco.
-   `defpay/views/js/defpay_target_products.js`
    *   **Ambito:** Back-office (Configurazione Modulo).
    *   **Descrizione:** Fornisce la funzionalità JavaScript per la sezione "Prodotti Target" nella configurazione del modulo, consentendo la ricerca, la selezione e la rimozione di prodotti per l'idoneità al pagamento differito.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `defpay/lib/emailTemplatesManager/css/emailTemplatesManager.css`
    *   **Ambito:** Back-office.
    *   **Descrizione:** Stili per l'interfaccia di gestione dei modelli di email, garantendo un aspetto coerente all'interno del pannello di amministrazione di PrestaShop.
-   `defpay/lib/searchTool/views/css/autocomplete.css`
    *   **Ambito:** Back-office.
    *   **Descrizione:** Stili per i suggerimenti di ricerca con completamento automatico, garantendo che siano visivamente distinti e facili da usare.
-   `defpay/views/css/admin_defpay.css`
    *   **Ambito:** Back-office.
    *   **Descrizione:** Stili generali per le schermate amministrative personalizzate del modulo (Dashboard, Utenti, Registro Attività), garantendo un design coerente all'interno del Back Office di PrestaShop.
-   `defpay/views/css/defpay.css`
    *   **Ambito:** Front-office.
    *   **Descrizione:** Stili generali per i componenti front-office del modulo, come la visualizzazione dell'opzione di pagamento nella pagina di checkout o nelle sezioni dell'account cliente.
-   `defpay/views/css/statement-document.css`
    *   **Ambito:** Front-office (per stampa/PDF).
    *   **Descrizione:** Stili specifici per la versione stampabile o PDF di un estratto conto di pagamento differito, ottimizzati per il layout del documento.
-   `defpay/views/css/statement.css`
    *   **Ambito:** Front-office.
    *   **Descrizione:** Stili per la visualizzazione su schermo degli estratti conto di pagamento differito nell'area dell'account cliente.

### 4.6 Struttura dei template Smarty (`views/templates/`)

#### Template Hook (`views/templates/hook/`)

-   `defpay/views/templates/hook/confirmation.tpl`
    *   **Hook:** `displayOrderConfirmation` (o simile).
    *   **Output:** Contenuto visualizzato nella pagina di conferma dell'ordine dopo che un ordine con pagamento differito è stato effettuato, informando il cliente sui termini di pagamento.
-   `defpay/views/templates/hook/displayAdminOrder16.tpl`
    *   **Hook:** `displayAdminOrder` (PrestaShop 1.6).
    *   **Output:** Aggiunge un blocco di informazioni o azioni relative al pagamento differito nella pagina dei dettagli dell'ordine nel Back Office di PrestaShop 1.6.
-   `defpay/views/templates/hook/displayAdminOrder17.tpl`
    *   **Hook:** `displayAdminOrder` (PrestaShop 1.7+).
    *   **Output:** Simile a `displayAdminOrder16.tpl`, ma adattato per la pagina dei dettagli dell'ordine del Back Office di PrestaShop 1.7+, mostrando lo stato del pagamento differito, la data di scadenza e possibilmente azioni di riscossione del pagamento.
-   `defpay/views/templates/hook/displayCustomerAccount.tpl`
    *   **Hook:** `displayCustomerAccount` o `displayMyAccountBlock`.
    *   **Output:** Aggiunge un link o un blocco alla pagina "Il mio account" del cliente, potenzialmente collegando al suo estratto conto o alla cronologia dei pagamenti differiti.
-   `defpay/views/templates/hook/displayOrderDetail.tpl`
    *   **Hook:** `displayOrderDetail` (front-office).
    *   **Output:** Visualizza informazioni specifiche sul pagamento differito (ad esempio, data di scadenza, stato del pagamento) all'interno della pagina dei dettagli dell'ordine del cliente nel front-office.
-   `defpay/views/templates/hook/payment.tpl`
    *   **Hook:** `displayPayment` (o `paymentOptions` per PS 1.7+).
    *   **Output:** Renderizza l'opzione "Pagamento Differito" nella pagina di selezione del pagamento al checkout.

#### Template Admin (`views/templates/admin/`)

-   `defpay/views/templates/admin/cron_setup.tpl`
    *   **Scopo:** Probabilmente utilizzato all'interno della pagina di configurazione principale del modulo (`getContent()`) per visualizzare l'URL del Cron Job e le istruzioni.
-   `defpay/views/templates/admin/defpay_target_products.tpl`
    *   **Scopo:** Renderizza l'interfaccia per la selezione di prodotti specifici idonei per il pagamento differito all'interno della configurazione del modulo.

#### Template Front-office (`views/templates/front/`)

-   `defpay/views/templates/front/statement_preview.tpl`
    *   **Scopo:** Visualizza un'anteprima di un estratto conto di pagamento differito al cliente nel front office.
-   `defpay/views/templates/front/validation.tpl`
    *   **Scopo:** Il template renderizzato dal controller frontale `validation.php`, tipicamente un messaggio di conferma o un riepilogo dopo che un ordine con pagamento differito è stato effettuato con successo.

#### Template PDF (`views/templates/pdf/`)

-   `defpay/views/templates/pdf/statement.tpl`
    *   **Scopo:** Template utilizzato per generare una versione PDF di un estratto conto o fattura di pagamento differito.

#### Template Libreria (`defpay/lib/emailTemplatesManager/views/` & `defpay/lib/searchTool/views/`)

Questi template fanno parte di librerie incorporate all'interno del modulo:

-   `defpay/lib/emailTemplatesManager/views/buttonManager.tpl`
-   `defpay/lib/emailTemplatesManager/views/createTemplateForm.tpl`
-   `defpay/lib/emailTemplatesManager/views/editTemplateForm.tpl`
-   `defpay/lib/emailTemplatesManager/views/mainForm.tpl`
-   `defpay/lib/emailTemplatesManager/views/selectInput.tpl`
    *   **Scopo:** Questi template vengono utilizzati per renderizzare i vari componenti dell'interfaccia di gestione dei modelli di email nel Back Office.
-   `defpay/lib/searchTool/views/scripts.tpl`
    *   **Scopo:** Probabilmente include l'inizializzazione o la configurazione JavaScript per lo strumento di ricerca con completamento automatico.

### 4.7 Schema del Database e Mappa degli Hook

#### Tabelle del Database

-   `ps_defpay_log` (o `defpay_log`):
    *   Memorizza le voci del registro attività relative ai pagamenti differiti.
    *   I campi probabilmente includono: `id_defpay_log`, `id_order`, `id_customer`, `event_type`, `description`, `date_add`.
-   `ps_defpayuser` (o `defpayuser`):
    *   Memorizza le impostazioni individuali di pagamento differito per i clienti.
    *   I campi probabilmente includono: `id_defpayuser`, `id_customer`, `deferred_payment_enabled` (booleano), `payment_due_days_override` (int), `credit_limit` (decimale), `date_add`, `date_upd`.
-   `ps_configuration`:
    *   Le impostazioni del modulo sono memorizzate qui con chiavi come `DEFPAY_ENABLED`, `DEFPAY_GROUPS`, `DEFPAY_DUE_DAYS`, `DEFPAY_MIN_TOTAL`, `DEFPAY_ORDER_STATUS`, `DEFPAY_CRON_URL`, `DEFPAY_TARGET_PRODUCTS_ENABLED`, `DEFPAY_TARGET_PRODUCTS_LIST`.

#### Tabella degli Hook Registrati

| Nome Hook | Tempistica di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayPayment` (PS 1.6) | Nel passaggio di selezione del pagamento al checkout. | Renderizza l'opzione "Pagamento Differito". |
| `paymentOptions` (PS 1.7+) | Nel passaggio di selezione del pagamento al checkout. | Renderizza l'opzione "Pagamento Differito" (hook moderno). |
| `displayOrderConfirmation` | Dopo che un ordine è stato effettuato con successo. | Visualizza i dettagli del pagamento differito nella pagina di conferma. |
| `displayCustomerAccount` / `displayMyAccountBlock` | Nella pagina "Il mio account" del cliente. | Aggiunge un link agli estratti conto o alla cronologia dei pagamenti differiti. |
| `displayOrderDetail` | Nella pagina dei dettagli dell'ordine del cliente nel front-office. | Mostra informazioni specifiche sul pagamento differito per un ordine. |
| `displayAdminOrder` (PS 1.6) | Nella pagina dei dettagli dell'ordine nel Back Office (PS 1.6). | Inietta lo stato del pagamento differito e gli strumenti di gestione. |
| `displayAdminOrder` (PS 1.7+) | Nella pagina dei dettagli dell'ordine nel Back Office (PS 1.7+). | Inietta lo stato del pagamento differito e gli strumenti di gestione. |
| `actionValidateOrder` | Dopo che un ordine è stato convalidato con successo. | Utilizzato per eseguire azioni come l'impostazione dello stato iniziale dell'ordine con pagamento differito, la registrazione dell'evento o la creazione di una voce `defpayuser` se necessario. |
| `actionOrderStatusUpdate` | Quando lo stato di un ordine viene modificato. | Può essere utilizzato per attivare azioni basate su modifiche di stato (ad esempio, pagamento ricevuto, scaduto). |
| `actionFrontControllerSetMedia` | Prima che un controller frontale renderizzi il suo output. | Utilizzato per mettere in coda risorse CSS e JS del front-office. |
| `actionAdminControllerSetMedia` | Prima che un controller amministrativo renderizzi il suo output. | Utilizzato per mettere in coda risorse CSS e JS del back-office. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, accedi al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Lì troverai i tuoi moduli acquistati e l'accesso ai nostri canali di supporto.
