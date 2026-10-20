---
title: "Gift Cards - vendi codici voucher - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Gift Cards - vendi codici voucher di MyPresta.eu."
sidebar:
  label: "Gift Cards - vendi codici voucher - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Gift Cards - sell voucher codes su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/gift-cards-sell-voucher-codes.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/gift-cards-sell-voucher-codes/)
>
> ---


# Gift Cards - vendi codici voucher

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Sono richieste estensioni PHP standard (cURL, JSON, OpenSSL), che sono tipicamente disponibili sulla maggior parte degli ambienti di web hosting moderni.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

Il modulo "Gift Cards - vendi codici voucher" offre diverse schermate di configurazione per gestire efficacemente le tue carte regalo.

### 2.1 Pagina di configurazione principale del modulo (Back Office > Moduli > Gestione moduli > Configura Gift Cards - vendi codici voucher)

Questa è la schermata di configurazione principale del modulo, dove imposti il comportamento generale e accedi ad altre sezioni di gestione.

- **Cosa fa questa impostazione:** Questa sezione contiene tipicamente le impostazioni globali per il modulo, come l'abilitazione/disabilitazione di funzionalità, il collegamento ad altre schermate di gestione e potenzialmente l'impostazione di comportamenti predefiniti per le carte regalo.
- **Effetto della modifica di questa impostazione:** Le modifiche qui influenzeranno il modo in cui le carte regalo vengono visualizzate, acquistate e gestite in tutto il tuo negozio.
- **Valore consigliato:** Rivedi attentamente ogni opzione. In generale, abilita le funzionalità che intendi utilizzare e segui le raccomandazioni predefinite del modulo a meno che tu non abbia una ragione specifica per modificarle.
- **Scenario / esempio per il commerciante:** Potresti trovare qui un'impostazione per abilitare un link dedicato "Carte Regalo" nel piè di pagina del tuo negozio. Abilitandolo, sarebbe più facile per i clienti trovare e acquistare carte regalo.

### 2.2 Gestione gruppi di carte regalo (Back Office > Gift Cards > Gruppi di carte regalo)

Questa schermata ti permette di definire diverse categorie o gruppi per le tue carte regalo. Pensali come modelli o tipi di carte regalo che vuoi offrire.

- **Nome schermata e posizione nel menu:** **Back Office > Gift Cards > Gruppi di carte regalo**
- **Azioni e impostazioni disponibili:**
  - **Tabella di elenco:** Mostra tutti i gruppi di carte regalo esistenti. Vedrai colonne come Nome gruppo, Valore, Stato (attivo/inattivo) e azioni (Modifica, Elimina).
  - **Aggiungi nuovo gruppo di carte regalo:** Clicca questo pulsante per creare un nuovo tipo di carta regalo.
    - **Nome gruppo:** (es. "Carta regalo compleanno", "Voucher Natale", "Carta regalo per ogni occasione")
      - *Cosa fa questa impostazione:* Questo è il nome interno per il tuo gruppo di carte regalo. Ti aiuta a organizzare e identificare diversi tipi di carte regalo nel back office.
      - *Effetto della modifica di questa impostazione:* Influisce solo sull'organizzazione del tuo back office.
      - *Valore consigliato:* Descrittivo e chiaro.
    - **Valore:** (es. "25.00", "50.00", "100.00")
      - *Cosa fa questa impostazione:* Definisce il valore monetario della carta regalo in questo gruppo.
      - *Effetto della modifica di questa impostazione:* Questo è l'importo che i clienti pagheranno e che i destinatari riceveranno come credito.
      - *Valore consigliato:* Denominazioni comuni e attraenti per il tuo mercato di riferimento.
    - **Attivo:** (Interruttore Sì/No)
      - *Cosa fa questa impostazione:* Controlla se le carte regalo di questo gruppo sono disponibili per l'acquisto nel tuo negozio.
      - *Effetto della modifica di questa impostazione:*
        - *Quando abilitato:* I clienti possono vedere e acquistare carte regalo di questo valore.
        - *Quando disabilitato:* Le carte regalo di questo valore sono nascoste dal front office e non possono essere acquistate.
      - *Valore consigliato:* SÌ per le carte regalo attive che vuoi vendere.
    - **Altri campi:** Possono includere opzioni per il periodo di validità, l'acquisto minimo per il riscatto o restrizioni specifiche sui prodotti.
      - *Cosa fa questa impostazione:* Questi campi ti permettono di affinare le condizioni in base alle quali la carta regalo può essere utilizzata.
      - *Effetto della modifica di questa impostazione:* Impatta direttamente l'usabilità e le restrizioni della carta regalo per il destinatario.
      - *Valore consigliato:* Imposta in base alla tua politica aziendale (es. validità 1 anno, nessun acquisto minimo).
- **Effetto delle modifiche:** La creazione di nuovi gruppi ti consente di offrire varie denominazioni di carte regalo. La modifica dei gruppi cambia il valore o la disponibilità dei tipi di carte regalo esistenti. L'eliminazione di un gruppo rimuove l'opzione di acquistare quel tipo specifico di carta regalo.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1. Inizia creando alcuni valori comuni di carte regalo (es. 25€, 50€, 100€).
  2. Man mano che la tua attività cresce o per promozioni stagionali, aggiungi nuovi gruppi con valori diversi o periodi di validità specifici.
  3. Disattiva i gruppi che non desideri più vendere, piuttosto che eliminarli, per preservare i dati storici.

### 2.3 Cronologia carte regalo (Back Office > Gift Cards > Cronologia carte regalo)

Questa schermata fornisce una panoramica completa di tutte le carte regalo acquistate e del loro stato attuale.

- **Nome schermata e posizione nel menu:** **Back Office > Gift Cards > Cronologia carte regalo**
- **Azioni e impostazioni disponibili:**
  - **Tabella di elenco:** Visualizza un elenco di tutti i buoni regalo generati. Le colonne tipicamente includono:
    - **Codice Voucher:** Il codice unico associato alla carta regalo.
    - **Valore Originale:** Il valore iniziale della carta regalo.
    - **Saldo Attuale:** Il saldo rimanente sulla carta regalo (se parzialmente utilizzata).
    - **Email Destinatario:** L'indirizzo email della persona che ha ricevuto la carta regalo.
    - **Nome Mittente:** Il nome della persona che ha acquistato la carta regalo.
    - **ID Ordine:** L'ID dell'ordine tramite il quale è stata acquistata la carta regalo.
    - **Stato:** (es. "In sospeso", "Attivo", "Utilizzato", "Scaduto").
    - **Azioni:** Possono includere opzioni per visualizzare i dettagli dell'ordine, reinviare l'email della carta regalo o regolare manualmente il saldo (usare con cautela).
  - **Ricerca e Filtro:** Strumenti per trovare carte regalo specifiche per codice, email, ID ordine o stato.
- **Effetto delle modifiche:** Questa schermata è principalmente per il monitoraggio e la gestione. Puoi tracciare l'utilizzo delle carte regalo, identificare i saldi in sospeso e assistere i clienti con le loro richieste relative alle carte regalo.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1. Controlla regolarmente questa sezione per monitorare le vendite e il riscatto delle carte regalo.
  2. Utilizza la funzione di ricerca per trovare rapidamente una carta regalo se un cliente ha una domanda sul suo saldo o stato.
  3. Se un cliente segnala di non aver ricevuto l'email della carta regalo, puoi verificarne lo stato e potenzialmente reinviarla da qui.

### 2.4 Gestione voucher carte regalo (Back Office > Gift Cards > Voucher carte regalo)

Questa schermata è dedicata alla gestione dei singoli codici voucher generati per ogni acquisto di carta regalo.

- **Nome schermata e posizione nel menu:** **Back Office > Gift Cards > Voucher carte regalo**
- **Azioni e impostazioni disponibili:**
  - **Tabella di elenco:** Mostra i singoli codici voucher regalo. Le colonne potrebbero includere:
    - **Codice Voucher:** Il codice unico.
    - **Gruppo Carta Regalo Associato:** A quale tipo di carta regalo appartiene questo voucher.
    - **Valore:** Il valore di questo specifico voucher.
    - **Cliente:** Il cliente associato al voucher (mittente o destinatario).
    - **Data Aggiunta/Generata:** Quando il voucher è stato creato.
    - **Stato:** (es. "Attivo", "Utilizzato", "Scaduto").
    - **Azioni:** Opzioni per visualizzare i dettagli, modificare (es. cambiare stato, estendere validità) o eliminare (usare con estrema cautela poiché ciò rimuove il voucher).
- **Effetto delle modifiche:** Questa schermata consente un controllo granulare sui singoli voucher delle carte regalo. Puoi attivare/disattivare manualmente i voucher, estenderne la validità o persino modificarne il valore se necessario (es. per problemi di servizio clienti).
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1. Utilizza questa schermata per attività di gestione avanzate, come l'emissione manuale di una carta regalo come gesto di buona volontà o la risoluzione di problemi specifici dei clienti relativi a un voucher.
  2. Sii cauto quando modifichi o elimini i voucher, poiché ciò influisce direttamente sul credito del cliente.
  3. Questa schermata fornisce una visione dettagliata del ciclo di vita di ogni voucher.

### 2.5 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Configurazione Modulo** | *Impostazioni Generali* | Varia | Comportamento globale del modulo, opzioni di visualizzazione e collegamenti ad altre aree di gestione. |
| **Gruppi di Carte Regalo** | **Nome Gruppo** | Descrittivo | Nome interno per il tipo di carta regalo. |
|  | **Valore** | Denominazioni comuni (es. 25€, 50€) | Valore monetario della carta regalo. |
|  | **Attivo** | SÌ | Controlla la visibilità e la possibilità di acquisto del tipo di carta regalo. |
|  | *Periodo di Validità* | Secondo la politica | Definisce per quanto tempo la carta regalo è valida dopo l'acquisto. |
|  | *Acquisto Min. per Riscatto* | Secondo la politica | Imposta un valore minimo dell'ordine per l'utilizzo della carta regalo. |
| **Cronologia Carte Regalo** | *Codice Voucher* | N/A | Identificatore unico per ogni carta regalo acquistata. |
|  | *Saldo Attuale* | N/A | Credito rimanente sulla carta regalo. |
|  | *Stato* | N/A | Traccia il ciclo di vita della carta regalo (Attivo, Usato, Scaduto). |
| **Voucher Carte Regalo** | *Codice Voucher* | N/A | Identificatore unico per ogni voucher generato. |
|  | *Stato* | N/A | Traccia lo stato del singolo voucher. |
|  | *Azioni Modifica/Elimina* | Usare con cautela | Consente la modifica o la rimozione manuale dei singoli voucher. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei clienti non riescono a trovare le carte regalo nel mio negozio.**

- **R:** Innanzitutto, assicurati che i "Gruppi di carte regalo" che hai creato siano contrassegnati come "Attivi" nel Back Office sotto **Gift Cards > Gruppi di carte regalo**. In secondo luogo, controlla la pagina di configurazione principale del tuo modulo (Moduli > Gestione moduli > Configura Gift Cards - vendi codici voucher) per le opzioni di visualizzazione dei link nell'intestazione, nel piè di pagina o nelle colonne. Se il tuo tema ha una gestione personalizzata del menu, potresti dover aggiungere manualmente un link alla pagina delle carte regalo (solitamente accessibile tramite un URL amichevole come `iltuonegozio.com/regali`).

**D2: Un cliente ha acquistato una carta regalo, ma il destinatario non ha ricevuto l'email.**

- **R:** Vai su **Gift Cards > Cronologia carte regalo** nel tuo Back Office. Trova la carta regalo specifica tramite ID ordine o email del mittente/destinatario. Controlla il suo stato – dovrebbe essere "Attivo" o "In sospeso" se non ancora utilizzata. Cerca un'opzione per "Reinvia email" per quel voucher specifico. Inoltre, consiglia al cliente di controllare la cartella spam/posta indesiderata. Assicurati che le impostazioni email del tuo negozio (Parametri avanzati > E-mail) siano configurate correttamente e che il tuo server possa inviare email in modo affidabile.

**D3: Lo sconto della carta regalo non viene applicato al checkout.**

- **R:** Verifica quanto segue:
  1. **Inserimento codice:** Assicurati che il cliente stia inserendo il codice della carta regalo corretto e completo, senza errori di battitura o spazi extra.
  2. **Validità:** Controlla lo stato della carta regalo in **Gift Cards > Cronologia carte regalo** o **Gift Cards > Voucher carte regalo**. È "Attiva"? È scaduta? C'è un saldo residuo?
  3. **Acquisto minimo:** La carta regalo ha un requisito di acquisto minimo che il totale del carrello attuale non soddisfa?
  4. **Restrizioni sui prodotti:** Ci sono categorie di prodotti o prodotti specifici esclusi dall'uso della carta regalo? (Questo sarebbe configurato nelle impostazioni del Gruppo di carte regalo).
  5. **Cache:** A volte, la pulizia della cache di PrestaShop (Parametri avanzati > Prestazioni) può risolvere problemi di visualizzazione o funzionalità.

**D4: Posso personalizzare il modello di email per le carte regalo?**

- **R:** Sì, il modulo include un gestore di modelli di email. Dovresti trovare opzioni all'interno della configurazione del modulo o una sezione dedicata (ad esempio, sotto **Gift Cards > Modelli email**) per modificare il contenuto e l'aspetto dell'email inviata ai destinatari delle carte regalo. Ciò ti consente di personalizzare l'email con il tuo marchio e includere istruzioni o messaggi specifici.

**D5: Cosa succede se il totale dell'ordine di un cliente è inferiore al valore della carta regalo?**

- **R:** Il modulo è progettato per gestire questa situazione. Se il totale dell'ordine è inferiore al valore della carta regalo, il saldo rimanente dovrebbe rimanere sulla carta regalo, consentendo al destinatario di utilizzarlo per acquisti futuri fino a quando il saldo non sarà esaurito o la carta non scadrà. Puoi verificare il saldo rimanente nella sezione **Gift Cards > Cronologia carte regalo**.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Gift Cards - vendi codici voucher" segue un modello MVC (Model-View-Controller) standard di PrestaShop, sebbene non definisca esplicitamente classi `ObjectModel` personalizzate nella directory `classes/`. Invece, sfrutta la funzionalità `CartRule` (voucher) di PrestaShop e estende le capacità di amministrazione tramite `AdminController` dedicati per la gestione di gruppi di carte regalo, cronologia e singoli voucher. L'interazione con il front-office è gestita da `ModuleFrontController`, principalmente per la visualizzazione delle carte regalo e la gestione degli account utente. Il modulo si basa fortemente sul sistema di configurazione di PrestaShop (`Configuration::get()`) per le sue impostazioni e si integra con vari hook per visualizzare contenuti e gestire i processi d'ordine.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

- `controllers/front/gifts.php`
  - **Nome classe e classe genitore**: `GiftcertificateGiftsModuleFrontController` che estende `ModuleFrontController`
  - **Responsabilità**: Questo controller è responsabile della visualizzazione della pagina principale delle carte regalo nel front office. Recupera i gruppi di carte regalo disponibili e li renderizza utilizzando il template `gifts.tpl`, consentendo ai clienti di sfogliare e selezionare le carte regalo per l'acquisto.
- `controllers/front/index.php`
  - **Nome classe e classe genitore**: `GiftcertificateIndexModuleFrontController` che estende `ModuleFrontController`
  - **Responsabilità**: Questo è un controller segnaposto o di fallback, spesso utilizzato per reindirizzare o gestire il routing del modulo base. In molti casi, potrebbe semplicemente reindirizzare al controller `gifts.php` o servire da base per altre azioni del front-office.

#### Controller Admin Back-Office

- `controllers/admin/AdminGiftcertificateGroupController.php`
  - **Nome Tab e Entità Gestita**: "Gruppi di carte regalo" (sotto il menu principale "Gift Cards"). Gestisce le entità `gift_group`.
  - **Responsabilità**: Questo controller fornisce l'interfaccia per creare, modificare ed eliminare gruppi di carte regalo. Gestisce l'invio del modulo per definire valori, nomi e altre impostazioni specifiche del gruppo per le carte regalo. Utilizza `HelperList` e `HelperForm` di PrestaShop per il rendering della griglia e dei moduli.
- `controllers/admin/AdminGiftcertificateHistoryController.php`
  - **Nome Tab e Entità Gestita**: "Cronologia carte regalo" (sotto il menu principale "Gift Cards"). Gestisce le entità `giftcertlist`.
  - **Responsabilità**: Questo controller visualizza una panoramica storica di tutte le carte regalo acquistate. Elenca codici voucher, valori, destinatari e stati. Consente agli amministratori di tracciare l'utilizzo delle carte regalo e potenzialmente di reinviare le email. Utilizza `HelperList` di PrestaShop per la visualizzazione a griglia e interagisce con chiavi di configurazione come `mowner`, `PS_SHOP_EMAIL`, `PS_SHOP_NAME` per le azioni relative alle email.
- `controllers/admin/AdminGiftcertificateVoucherController.php`
  - **Nome Tab e Entità Gestita**: "Voucher carte regalo" (sotto il menu principale "Gift Cards"). Gestisce le entità `gift_voucher`.
  - **Responsabilità**: Questo controller fornisce una gestione dettagliata per i singoli codici voucher delle carte regalo. Consente agli amministratori di visualizzare, modificare (es. cambiare stato, estendere la validità) o eliminare voucher specifici. Utilizza `HelperList` e `HelperForm` di PrestaShop per la gestione dei singoli record dei voucher.
- `controllers/admin/index.php`
  - **Nome Tab e Entità Gestita**: N/A
  - **Responsabilità**: Questo file serve tipicamente come misura di sicurezza per prevenire l'elenco diretto delle directory o l'accesso. Di solito contiene un semplice `header('Location: ../../../index.php'); exit;` o simile per reindirizzare all'amministrazione principale di PrestaShop.

### 4.3 Classi e modelli principali (`classes/`)

Il dossier del modulo indica l'assenza di classi personalizzate nella directory `classes/`. Ciò suggerisce che il modulo:

1. Manipola direttamente le tabelle del database utilizzando `Db::getInstance()` senza `ObjectModel`.
2. Si basa sulla classe `CartRule` (voucher) di PrestaShop per la logica effettiva del voucher, e i suoi controller di amministrazione gestiscono l'aspetto della "carta regalo" come un wrapper attorno alla creazione e gestione di `CartRule`.
3. Il file principale del modulo (`ajax_giftcertificate.php`) o le sue librerie incluse contengono la logica principale e la gestione dei dati.

### 4.4 Risorse JavaScript (`views/js/`)

- `giftcertificate/js/script.js`
  - **Ambito**: Probabilmente Front-office o funzionalità generale del modulo.
  - **Dettagli**: Contiene JavaScript generale per il modulo, potenzialmente gestendo richieste AJAX per aggiungere carte regalo al carrello, aggiornamenti dinamici sulla pagina delle carte regalo o convalide dei moduli front-end.
- `giftcertificate/lib/emailTemplatesManager/js/emailTemplatesManager.js`
  - **Ambito**: Back-office (Admin).
  - **Dettagli**: Gestisce la funzionalità per la modifica e la creazione di modelli di email all'interno della configurazione del modulo. Ciò includerebbe la gestione degli invii di moduli, le chiamate AJAX per il salvataggio dei modelli e potenzialmente le integrazioni con editor di testo avanzati.
- `giftcertificate/lib/pdfTemplatesManager/js/pdfTemplatesManager.js`
  - **Ambito**: Back-office (Admin).
  - **Dettagli**: Simile al gestore di modelli di email, ma per i modelli PDF, probabilmente utilizzato per generare carte regalo stampabili. Gestisce le interazioni con i moduli, il salvataggio dei design dei modelli PDF e la funzionalità di anteprima.
- `giftcertificate/lib/searchTool/views/js/autocomplete.js`
  - **Ambito**: Back-office (Admin).
  - **Dettagli**: Fornisce la funzionalità di completamento automatico per i campi di ricerca all'interno dei controller di amministrazione, come la ricerca di clienti o prodotti durante la creazione/modifica di carte regalo o voucher.
- `giftcertificate/lib/voucherengine/script.js`
  - **Ambito**: Probabilmente Front-office o funzionalità generale del modulo.
  - **Dettagli**: Contiene JavaScript specifico per la logica di generazione e riscatto dei voucher, potenzialmente interagendo con il carrello o il processo di checkout per applicare gli sconti delle carte regalo.

### 4.5 Fogli di stile CSS (`views/css/`)

- `giftcertificate/css.css`
  - **Ambito**: Generale, potrebbe essere front-office o back-office.
  - **Dettagli**: Contiene lo stile principale per gli elementi del modulo, potenzialmente includendo il layout generale, gli stili dei pulsanti o i componenti comuni.
- `giftcertificate/lib/emailTemplatesManager/css/emailTemplatesManager.css`
  - **Ambito**: Back-office (Admin).
  - **Dettagli**: Stili per l'interfaccia di gestione dei modelli di email, garantendo un aspetto coerente all'interno del back office di PrestaShop.
- `giftcertificate/lib/pdfTemplatesManager/css/pdfTemplatesManager.css`
  - **Ambito**: Back-office (Admin).
  - **Dettagli**: Stili per l'interfaccia di gestione dei modelli PDF, simile al gestore di modelli di email.
- `giftcertificate/lib/searchTool/views/css/autocomplete.css`
  - **Ambito**: Back-office (Admin).
  - **Dettagli**: Stili per i risultati di ricerca con completamento automatico e i campi di input.
- `giftcertificate/lib/voucherengine/ps16.css`
  - **Ambito**: Front-office (specificamente per temi PrestaShop 1.6).
  - **Dettagli**: Contiene stili di compatibilità per i temi PrestaShop 1.6, affrontando potenziali differenze di layout o elementi per garantire la corretta visualizzazione dei componenti della carta regalo.
- `giftcertificate/views/css/giftcertificate.css`
  - **Ambito**: Front-office (rivolto al cliente).
  - **Dettagli**: Foglio di stile principale per la visualizzazione front-office delle carte regalo, inclusa la pagina dedicata alle carte regalo, gli elementi della pagina prodotto e potenzialmente lo stile della sezione "Il mio account". Gli sviluppatori possono sovrascrivere queste classi nel `custom.css` del loro tema o nel tema figlio.

### 4.6 Struttura del template Smarty (`views/templates/`)

#### Template hook (`views/templates/hook/`)

- `giftcertificate/views/templates/hook/displayAdminOrder.tpl`
  - **Hook**: `displayAdminOrder`
  - **Output**: Renderizza le informazioni relative alle carte regalo all'interno della pagina dei dettagli dell'ordine di PrestaShop nel Back Office. Questo potrebbe mostrare quali carte regalo sono state acquistate nell'ordine o quali carte regalo sono state utilizzate per pagare l'ordine.
- `giftcertificate/views/templates/hook/displayMyAccountBlock.tpl`
  - **Hook**: `displayMyAccountBlock` (PrestaShop 1.6)
  - **Output**: Aggiunge un link o un blocco alla pagina "Il mio account" del cliente, indirizzandolo alle sue carte regalo acquistate o alla cronologia delle carte regalo.
- `giftcertificate/views/templates/hook/my-account-16.tpl`
  - **Hook**: `displayCustomerAccount` (PrestaShop 1.6)
  - **Output**: Template specifico per aggiungere un link alla pagina "Il mio account" per i temi PrestaShop 1.6.
- `giftcertificate/views/templates/hook/my-account-17.tpl`
  - **Hook**: `displayCustomerAccount` (PrestaShop 1.7+)
  - **Output**: Template specifico per aggiungere un link alla pagina "Il mio account" per i temi PrestaShop 1.7 e più recenti.
- `giftcertificate/views/templates/hook/my-account.tpl`
  - **Hook**: `displayCustomerAccount` (Generale/Fallback)
  - **Output**: Un template generico per il link "Il mio account", potenzialmente utilizzato come fallback o per versioni precedenti.

#### Template Admin (`views/templates/admin/`)

- `giftcertificate/views/templates/admin/admin.tpl`
  - **Ambito**: Configurazione generale dell'amministrazione.
  - **Output**: Probabilmente il modulo di configurazione principale per il modulo, renderizzato tramite `getContent()` nel file principale del modulo. Potrebbe includere schede o sezioni per varie impostazioni.
- `giftcertificate/views/templates/admin/adminOrder.tpl`
  - **Ambito**: Vista ordine amministratore.
  - **Output**: Simile a `displayAdminOrder.tpl` ma potenzialmente per una vista più integrata all'interno di una pagina di ordine amministratore personalizzata, se il modulo la sovrascrive o la estende.
- `giftcertificate/views/templates/admin/list/list_action_email.tpl`
  - **Ambito**: Viste elenco amministratore (es. Cronologia carte regalo).
  - **Output**: Un pulsante o link di azione specifico per l'invio di email, tipicamente trovato nella colonna delle azioni di una tabella `HelperList`, che consente agli amministratori di reinviare le email delle carte regalo.

#### Template Front-office (`views/templates/front/`)

- `giftcertificate/views/templates/front/gifts.tpl`
  - **Ambito**: Pagina front-office dedicata.
  - **Output**: Il template principale per la visualizzazione dell'elenco delle carte regalo disponibili ai clienti, renderizzato da `GiftcertificateGiftsModuleFrontController`.

#### Template Libreria (`lib/`)

- `giftcertificate/lib/emailTemplatesManager/views/*.tpl`
  - **Ambito**: Back-office (Admin).
  - **Output**: Template per l'interfaccia di gestione dei modelli di email (es. `buttonManager.tpl`, `createTemplateForm.tpl`, `editTemplateForm.tpl`, `mainForm.tpl`, `selectInput.tpl`).
- `giftcertificate/lib/helpers/views/orderStates.tpl`
  - **Ambito**: Back-office (Admin).
  - **Output**: Un template di aiuto, probabilmente per visualizzare o selezionare gli stati degli ordini all'interno delle configurazioni o dei moduli del modulo.
- `giftcertificate/lib/pdfTemplatesManager/views/*.tpl`
  - **Ambito**: Back-office (Admin).
  - **Output**: Template per l'interfaccia di gestione dei modelli PDF (es. `buttonManager.tpl`, `createTemplateForm.tpl`, `editTemplateForm.tpl`, `mainForm.tpl`, `selectInput.tpl`).
- `giftcertificate/lib/searchTool/views/scripts.tpl`
  - **Ambito**: Back-office (Admin).
  - **Output**: Contiene logica JavaScript o Smarty relativa allo strumento di ricerca, potenzialmente inclusi script di inizializzazione per il completamento automatico.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

Il modulo probabilmente crea tabelle personalizzate per gestire i suoi dati, sebbene non siano state trovate definizioni esplicite di `ObjectModel` in `classes/`. Basandosi sui Controller Admin, sono implicite le seguenti tabelle:

- `ps_gift_group`: Memorizza le definizioni per i gruppi di carte regalo (es. valore, nome, validità, restrizioni).
- `ps_giftcertlist`: Memorizza la cronologia delle carte regalo acquistate, inclusi i loro codici unici, il valore iniziale, il saldo attuale, il destinatario, il mittente e l'ordine associato.
- `ps_gift_voucher`: Memorizza i dettagli dei singoli codici voucher, potenzialmente collegandosi a `ps_cart_rule` se sfrutta il sistema di voucher nativo di PrestaShop.

I record di configurazione memorizzati in `ps_configuration` includerebbero:

- Impostazioni specifiche del modulo configurate tramite `getContent()`, come ID dei modelli di email, ID dei modelli PDF, opzioni di visualizzazione, ecc.
- `mowner`, `PS_SHOP_EMAIL`, `PS_SHOP_NAME` sono configurazioni core di PrestaShop utilizzate dal modulo per l'invio di email.

#### Tabella degli hook registrati

| Nome Hook | Tempistica di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Inietta asset CSS/JS, meta tag o dati specifici del modulo. |
| `displayLeftColumn` / `displayRightColumn` | Nella colonna sinistra/destra del front office. | Visualizza un blocco per la promozione delle carte regalo o un link alla pagina delle carte regalo. |
| `displayProductAdditionalInfo` / `displayProductButtons` | Sulla pagina del prodotto. | Potenzialmente visualizza un pulsante "Acquista una carta regalo" o informazioni correlate. |
| `displayFooter` | Nella sezione del piè di pagina di ogni pagina. | Aggiungi un link alla pagina delle carte regalo. |
| `displayCustomerAccount` | Sulla pagina "Il mio account" del cliente. | Aggiungi un link alla cronologia/dettagli delle carte regalo del cliente. |
| `displayMyAccountBlock` | Sulla pagina "Il mio account" del cliente (specifico per PrestaShop 1.6). | Aggiungi un link alla cronologia/dettagli delle carte regalo del cliente. |
| `actionValidateOrder` | Dopo che un ordine è stato validato con successo. | Attiva la generazione e l'invio dei voucher delle carte regalo quando viene acquistato un prodotto carta regalo. Aggiorna la cronologia delle carte regalo. |
| `displayAdminOrder` | Sulla pagina dei dettagli dell'ordine del Back Office. | Visualizza le informazioni della carta regalo relative all'ordine (acquistate o utilizzate). |
| `actionOrderStatusUpdate` | Quando lo stato di un ordine cambia. | Potenzialmente attiva/disattiva le carte regalo in base allo stato dell'ordine (es. attiva al "Pagamento Accettato"). |
| `actionFrontControllerSetMedia` | Prima che un controller front-end renderizzi il suo template. | Carica asset CSS e JavaScript specifici del front-office. |
| `actionAdminControllerSetMedia` | Prima che un controller admin renderizzi il suo template. | Carica asset CSS e JavaScript specifici del back-office. |

## 5. Supporto Ufficiale e Aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e per assicurarti di utilizzare la versione più recente e sicura del modulo "Gift Cards - vendi codici voucher", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a fornire assistenza tempestiva e miglioramenti continui ai nostri moduli.
"""
