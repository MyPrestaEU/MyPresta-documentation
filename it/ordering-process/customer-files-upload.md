---
title: "Caricamento File Cliente - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Caricamento File Cliente di MyPresta.eu."
sidebar:
  label: "Caricamento File Cliente - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Customer Files Upload su MyPresta.eu](https://mypresta.eu/modules/ordering-process/customer-files-upload.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/customer-files-upload/)
>
> ---


# Caricamento File Cliente

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste da PrestaShop stesso e sono sufficienti per questo modulo. Assicurati che il tuo server abbia spazio su disco sufficiente per archiviare i file caricati.

## 2. Panoramica Completa della Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo, accessibile dopo l'installazione o cliccando su "Configura" dal Gestore Moduli.

- **Abilita Modulo:**

  - **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare la funzionalità del modulo in tutto il tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Tutte le funzionalità di caricamento file, la gestione dei file del cliente e gli strumenti del back-office diventano attivi.
    - *Quando disabilitato:* Le funzionalità del modulo sono completamente disattivate e non appariranno moduli di caricamento o sezioni "I Miei File".
  - **Valore consigliato:** SÌ
  - **Scenario / esempio del commerciante:** Se stai configurando il modulo per la prima volta o eseguendo la manutenzione, potresti disabilitarlo temporaneamente. Altrimenti, mantienilo abilitato per offrire il servizio di caricamento file.
- **Consenti caricamenti sulla Pagina Prodotto:**

  - **Cosa fa questa impostazione:** Controlla se i clienti possono caricare file direttamente dalla pagina di un prodotto.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Un modulo di caricamento apparirà sulle pagine prodotto, consentendo ai clienti di allegare file prima di aggiungere il prodotto al carrello.
    - *Quando disabilitato:* Nessun modulo di caricamento sarà visibile sulle pagine prodotto.
  - **Valore consigliato:** SÌ (se i tuoi prodotti richiedono file di personalizzazione pre-acquisto)
  - **Scenario / esempio del commerciante:** Se vendi tazze personalizzate, abilitando questa opzione i clienti possono caricare la loro foto direttamente sulla pagina del prodotto della tazza.
- **Consenti caricamenti sulla Pagina del Carrello:**

  - **Cosa fa questa impostazione:** Determina se un'area di caricamento viene mostrata nella pagina di riepilogo del carrello.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I clienti possono caricare file generici relativi all'intero carrello o a elementi specifici prima di procedere al checkout.
    - *Quando disabilitato:* Nessun modulo di caricamento sarà visibile nella pagina del carrello.
  - **Valore consigliato:** SÌ (se i clienti potrebbero aver bisogno di fornire istruzioni generali sull'ordine o file per più articoli)
  - **Scenario / esempio del commerciante:** Un cliente che ordina più articoli personalizzati potrebbe caricare un singolo documento con istruzioni generali o una guida di branding per l'intero ordine.
- **Consenti caricamenti sulla Pagina di Conferma dell'Ordine:**

  - **Cosa fa questa impostazione:** Controlla se i clienti possono caricare file immediatamente dopo aver effettuato un ordine, nella schermata di conferma dell'ordine.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Un modulo di caricamento appare nella pagina "Conferma Ordine", consentendo ai clienti di allegare file al loro ordine appena effettuato.
    - *Quando disabilitato:* Nessun modulo di caricamento sarà visibile nella pagina di conferma dell'ordine.
  - **Valore consigliato:** SÌ (altamente raccomandato per la maggior parte dei casi d'uso)
  - **Scenario / esempio del commerciante:** Un cliente ha appena acquistato un banner personalizzato. Può caricare immediatamente il suo file di design ad alta risoluzione nella pagina di conferma senza navigare altrove.
- **Consenti caricamenti nell'Account Cliente (I Miei File e Cronologia Ordini):**

  - **Cosa fa questa impostazione:** Abilita la sezione "I Miei File" nell'account del cliente e consente i caricamenti nelle singole pagine di dettaglio dell'ordine all'interno della loro cronologia.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I clienti ottengono un'area dedicata "I Miei File" per gestire tutti i loro caricamenti e possono aggiungere file a ordini passati specifici.
    - *Quando disabilitato:* I clienti non possono gestire i file dal loro account e nessuna opzione di caricamento apparirà nelle pagine della cronologia ordini.
  - **Valore consigliato:** SÌ (fornisce la massima flessibilità e controllo al cliente)
  - **Scenario / esempio del commerciante:** Un cliente si rende conto di aver dimenticato di caricare un file di font specifico per il suo ordine di magliette personalizzate un giorno dopo. Può accedere al suo account, andare all'ordine e caricarlo.
- **Dimensione Massima File (MB):**

  - **Cosa fa questa impostazione:** Imposta il limite superiore per la dimensione di ogni singolo file che un cliente può caricare.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su un valore (ad esempio, 10):* Ai clienti verrà impedito di caricare file più grandi di 10 MB.
    - *Quando impostato su 0 o vuoto:* Il modulo si affiderà tipicamente ai limiti di caricamento PHP del tuo server, che potrebbero essere molto alti o molto bassi.
  - **Valore consigliato:** 5-20 MB (regola in base ai tipi di file tipici; ad esempio, le immagini ad alta risoluzione potrebbero richiedere di più).
  - **Scenario / esempio del commerciante:** Se ti aspetti che i clienti carichino foto ad alta risoluzione, potresti impostarlo a 20 MB. Se sono necessari solo piccoli documenti, 5 MB potrebbero essere sufficienti per risparmiare spazio sul server.
- **Tipi di File Consentiti (separati da virgola):**

  - **Cosa fa questa impostazione:** Specifica quali estensioni di file sono consentite per il caricamento.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su "jpg,png,pdf":* Solo i file con queste estensioni possono essere caricati. Qualsiasi altro tipo di file verrà rifiutato.
    - *Quando lasciato vuoto:* Tutti i tipi di file potrebbero essere consentiti (non raccomandato per la sicurezza).
  - **Valore consigliato:** Includi solo i tipi che ti aspetti (ad esempio, `jpg,jpeg,png,gif,pdf,doc,docx,xls,xlsx,txt,zip`). Evita i file eseguibili.
  - **Scenario / esempio del commerciante:** Se hai bisogno solo di file di design, potresti elencare `ai,eps,svg,psd,pdf,jpg,png`. Se hai bisogno di documenti, `doc,docx,pdf` sarebbe appropriato.
- **Forza Caricamento File per prodotti specifici (ID Prodotto):**

  - **Cosa fa questa impostazione:** Ti consente di rendere obbligatorio il caricamento di file per determinati prodotti. Inserisci gli ID prodotto separati da virgole.
  - **Effetto della modifica di questa impostazione:**
    - *Quando vengono inseriti gli ID prodotto:* Se un cliente tenta di aggiungere uno di questi prodotti al carrello o di procedere al checkout senza caricare un file, gli verrà richiesto di farlo.
    - *Quando lasciato vuoto:* Nessun prodotto avrà caricamenti di file obbligatori.
  - **Valore consigliato:** Utilizzare solo per i prodotti in cui un file è assolutamente essenziale per l'elaborazione dell'ordine.
  - **Scenario / esempio del commerciante:** Per un prodotto "Design Biglietto da Visita Personalizzato" (ID 123), potresti inserire `123`. Il cliente non può completare l'acquisto senza caricare il proprio logo o brief di design.
- **Notifica Email al Cliente al Caricamento File:**

  - **Cosa fa questa impostazione:** Controlla se viene inviata un'e-mail al cliente quando carica con successo un file.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il cliente riceve un'e-mail di conferma che il suo file è stato ricevuto.
    - *Quando disabilitato:* Nessuna notifica e-mail viene inviata al cliente.
  - **Valore consigliato:** SÌ (migliora la fiducia del cliente e fornisce conferma)
  - **Scenario / esempio del commerciante:** Un cliente carica una foto per un regalo personalizzato. Un'e-mail conferma il caricamento, rassicurandolo che il suo file è stato ricevuto correttamente.
- **Notifica Email all'Amministratore al Caricamento File:**

  - **Cosa fa questa impostazione:** Controlla se viene inviata un'e-mail all'amministratore/i del negozio quando un cliente carica un file.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* L'amministratore del negozio riceve un avviso e-mail, rendendolo consapevole dei nuovi file che richiedono attenzione.
    - *Quando disabilitato:* Nessuna notifica e-mail viene inviata all'amministratore.
  - **Valore consigliato:** SÌ (essenziale per l'elaborazione tempestiva degli ordini)
  - **Scenario / esempio del commerciante:** Un cliente carica un file di design. L'amministratore riceve un'e-mail, invitandolo a controllare l'ordine e iniziare a elaborare l'articolo personalizzato.
- **Visualizza Pulsante Carica in Header/Footer/Colonne:**

  - **Cosa fa questa impostazione:** Ti consente di scegliere dove appare un pulsante o un link generico "Carica File" nel tuo negozio (ad esempio, nell'intestazione, nel piè di pagina o nelle colonne laterali).
  - **Effetto della modifica di questa impostazione:**
    - *Quando viene selezionato un hook:* Un link o un pulsante apparirà in quella posizione, indirizzando i clienti alla loro sezione "I Miei File" o a una pagina di caricamento generale.
    - *Quando viene selezionato "Nessuno":* Nessun pulsante di caricamento generale verrà visualizzato al di fuori delle pagine prodotto/carrello/ordine.
  - **Valore consigliato:** Considera `displayHeader` o `displayFooter` per un facile accesso a "I Miei File" se ti aspetti caricamenti frequenti.
  - **Scenario / esempio del commerciante:** Posizionare un link "I Miei File" nel piè di pagina consente ai clienti di ritorno di accedere e gestire rapidamente i loro documenti caricati.

### 2.2 Schermate Amministrative Dedicate e Viste Controller

#### 2.2.1 Gestore File Cliente (Back Office > Moduli > Caricamento File Cliente > File Cliente)

Questa schermata fornisce un luogo centralizzato per te, il proprietario del negozio, per visualizzare e gestire tutti i file caricati dai tuoi clienti.

- **Nome Schermata e Posizione Menu:** Puoi trovarlo navigando su **Moduli > Gestione moduli**, trovando "Caricamento File Cliente" e cliccando su "Configura". All'interno della configurazione del modulo, dovrebbe esserci una scheda o un link etichettato "File Cliente" o "Gestisci File". In alternativa, potrebbe apparire direttamente sotto il menu "Moduli" come "File Cliente".
- **Azioni e Impostazioni Disponibili:**
  - **Tabella Elenco File:** Visualizza un elenco di tutti i file caricati, inclusi dettagli come:
    - **Nome File:** Il nome del file caricato.
    - **Cliente:** Il nome del cliente che ha caricato il file.
    - **ID Ordine:** Se il file è collegato a un ordine specifico.
    - **Prodotto:** Se il file è collegato a un prodotto specifico.
    - **Data Caricamento:** Quando il file è stato caricato.
    - **Dimensione:** La dimensione del file.
    - **Azioni:** Tipicamente include opzioni per **Scaricare** il file, **Visualizzare Dettagli** o **Eliminare** il file.
  - **Filtro e Ricerca:** Di solito puoi filtrare i file per cliente, ID ordine, prodotto o intervallo di date per trovare rapidamente caricamenti specifici.
  - **Azioni di Massa:** Opzioni per selezionare più file ed eseguire azioni come l'eliminazione di massa.
- **Effetto delle modifiche:**
  - **Scaricare un file:** Recupera il file caricato dal cliente sul tuo computer per l'elaborazione.
  - **Eliminare un file:** Rimuove permanentemente il file dal tuo server e dalla sezione "I Miei File" del cliente. Usare con cautela!
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Controlla regolarmente questa sezione per nuovi caricamenti, specialmente dopo aver ricevuto notifiche e-mail dall'amministratore. Scarica i file necessari per l'evasione degli ordini e rivedi ed elimina periodicamente i file vecchi o non necessari per liberare spazio sul server.

#### 2.2.2 Integrazione Pagina Dettagli Ordine (Back Office > Ordini > Ordini > Visualizza Ordine)

Il modulo si integra direttamente nelle tue pagine di dettaglio ordine PrestaShop esistenti.

- **Nome Schermata e Posizione Menu:** Quando visualizzi un ordine specifico nel tuo Back Office (ad esempio, **Ordini > Ordini**, quindi clicca su "Visualizza" accanto a un ordine).
- **Azioni e Impostazioni Disponibili:**
  - All'interno della pagina di dettaglio dell'ordine, apparirà una nuova sezione o scheda, specificamente per "File Cliente" o "File Caricati".
  - Questa sezione elencherà tutti i file che il cliente ha caricato per *quell'ordine specifico*.
  - Vedrai i nomi dei file, le date di caricamento e le opzioni per **Scaricare** ogni file.
  - Potrebbe esserci anche un'opzione per l'amministratore per **Caricare un file** per conto del cliente o per uso interno relativo all'ordine.
- **Effetto delle modifiche:**
  - **Scaricare file da qui:** Ti consente di accedere rapidamente ai file pertinenti all'ordine che stai attualmente visualizzando, semplificando l'elaborazione dell'ordine.
  - **Caricamento Amministratore:** Se disponibile, ti consente di aggiungere note interne o file relativi all'ordine direttamente all'elenco dei file dell'ordine.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Quando elabori un ordine che richiede file cliente, naviga alla pagina di dettaglio dell'ordine, individua la sezione "File Cliente" e scarica tutti i documenti necessari prima di iniziare la produzione o l'evasione.

### 2.3 Tabella di Riferimento Rapido della Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Configurazione Modulo** | Abilita Modulo | SÌ | Interruttore principale per la funzionalità del modulo. |
|  | Consenti caricamenti sulla Pagina Prodotto | SÌ (se necessario) | Mostra il modulo di caricamento sulle pagine prodotto. |
|  | Consenti caricamenti sulla Pagina del Carrello | SÌ (se necessario) | Mostra il modulo di caricamento sulla pagina del carrello. |
|  | Consenti caricamenti sulla Pagina di Conferma dell'Ordine | SÌ | Mostra il modulo di caricamento dopo l'effettuazione dell'ordine. |
|  | Consenti caricamenti nell'Account Cliente | SÌ | Abilita "I Miei File" e i caricamenti nella cronologia ordini. |
|  | Dimensione Massima File (MB) | 5-20 MB | Limita la dimensione del caricamento del singolo file. |
|  | Tipi di File Consentiti | `jpg,png,pdf,...` | Limita le estensioni dei file per sicurezza/pertinenza. |
|  | Forza Caricamento File per prodotti specifici (ID) | Vuoto (usa secondo necessità) | Rende il caricamento obbligatorio per i prodotti specificati. |
|  | Notifica Email al Cliente | SÌ | Invia e-mail di conferma al cliente al caricamento. |
|  | Notifica Email all'Amministratore | SÌ | Invia avviso e-mail all'amministratore al nuovo caricamento. |
|  | Visualizza Pulsante Carica in Header/Footer/Colonne | `displayFooter` (o secondo necessità) | Posiziona un link generico "Carica File" nell'hook selezionato. |
| **Gestore File Cliente** | Elenco File | N/A | Visualizza, filtra, scarica ed elimina tutti i file del cliente. |
|  | Azioni di Massa | N/A | Esegue azioni su più file selezionati. |
| **Pagina Dettagli Ordine** | Sezione File Cliente | N/A | Visualizza e scarica i file specifici dell'ordine corrente. |

## 3. Risoluzione dei Problemi del Commerciante e Domande Frequenti (FAQ)

**D1: I miei clienti non riescono a vedere i moduli di caricamento o la sezione "I Miei File".**
R:

- **Controlla lo Stato del Modulo:** Assicurati che il modulo sia abilitato in **Moduli > Gestione moduli**.
- **Controlla la Configurazione:** Vai alla pagina di configurazione del modulo e verifica che "Abilita Modulo" sia impostato su SÌ e che anche le posizioni di caricamento specifiche (Pagina Prodotto, Carrello, Account Cliente) siano abilitate.
- **Svuota Cache:** A volte la cache di PrestaShop può impedire che le modifiche appaiano immediatamente. Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota cache".
- **Compatibilità del Tema:** Se stai utilizzando un tema altamente personalizzato, potrebbe non agganciarsi correttamente ai punti di visualizzazione del modulo. Contatta il supporto MyPresta.eu o il tuo sviluppatore web.

**D2: I clienti ricevono un errore quando tentano di caricare file.**
R:

- **Controlla il Limite di Dimensione del File:** Verifica la "Dimensione Massima File (MB)" nella configurazione del modulo. Il file del cliente potrebbe essere troppo grande.
- **Controlla i Tipi di File Consentiti:** Assicurati che il tipo di file che il cliente sta tentando di caricare sia elencato nell'impostazione "Tipi di File Consentiti" (ad esempio, se sta caricando un file `.zip`, `zip` deve essere nell'elenco).
- **Limiti del Server:** Il tuo host web potrebbe avere limiti di caricamento PHP lato server (`upload_max_filesize`, `post_max_size`) che sono inferiori all'impostazione del tuo modulo. Potrebbe essere necessario contattare il tuo host o modificare il tuo file `php.ini`.

**D3: Non ricevo notifiche e-mail quando i clienti caricano file.**
R:

- **Controlla le Impostazioni di Notifica E-mail:** Nella configurazione del modulo, assicurati che "Notifica Email all'Amministratore al Caricamento File" sia impostato su SÌ.
- **Impostazioni E-mail di PrestaShop:** Verifica che le impostazioni e-mail del tuo negozio PrestaShop siano configurate correttamente e che inviino e-mail con successo (**Parametri Avanzati > E-mail**). Invia un'e-mail di prova da lì.
- **Cartella Spam:** Controlla la tua cartella spam o posta indesiderata per le notifiche.
- **Mailer del Server:** Assicurati che la funzione di posta del tuo server funzioni correttamente.

**D4: Come traduco il testo del modulo in altre lingue?**
R:

- Naviga su **Internazionale > Traduzioni** nel tuo Back Office di PrestaShop.
- Seleziona "Traduzioni dei moduli installati", scegli il tuo tema e quindi seleziona "Caricamento File Cliente" dal menu a discesa del modulo.
- Potrai quindi tradurre tutte le stringhe visibili utilizzate dal modulo.

**D5: Dove vengono archiviati i file caricati sul mio server?**
R: Il modulo di solito archivia i file in una cartella dedicata all'interno della tua installazione di PrestaShop, spesso denominata `upload` o `orderfiles_uploads` all'interno della directory del modulo o di una directory `upload` generale. Puoi accedervi tramite FTP/SFTP, ma è sempre meglio gestirli tramite l'interfaccia del Back Office per mantenere l'integrità del database.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

### 4.1 Panoramica dell'Architettura

Il modulo "Caricamento File Cliente" segue un'architettura standard per i moduli PrestaShop, sfruttando i principi MVC. Estende `Module` per la sua funzionalità e configurazione principali, utilizza `ModuleFrontController` per le interazioni front-office (caricamento, gestione file) e `AdminController` per la gestione back-office. I dati sono archiviati nel file system e potenzialmente collegati tramite `ps_configuration` per le impostazioni. Il modulo si basa fortemente sul sistema di hook di PrestaShop per iniettare la sua funzionalità in varie parti del negozio.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

- `controllers/front/customerfiles.php`
  - **Nome classe e classe genitore:** `CustomerfilesCustomerfilesModuleFrontController` estende `ModuleFrontController`
  - **Responsabilità:** Probabilmente gestisce la pagina principale "I Miei File" rivolta al cliente, visualizzando un elenco di file caricati e fornendo opzioni per la gestione. Recupererebbe i file associati al cliente loggato.
- `controllers/front/download.php`
  - **Nome classe e classe genitore:** `DownloadCustomerfilesModuleFrontController` estende `ModuleFrontController`
  - **Responsabilità:** Gestisce i download sicuri dei file. Prende un ID file o un percorso, verifica i permessi del cliente (se applicabile) e serve il file al browser, spesso forzando un download.
- `controllers/front/filesmanager.php`
  - **Nome classe e classe genitore:** `FilesmanagerCustomerfilesModuleFrontController` estende `ModuleFrontController`
  - **Responsabilità:** Potrebbe essere un'interfaccia generica di gestione file, potenzialmente utilizzata per chiamate AJAX relative a operazioni sui file (ad esempio, eliminazione di un file dalla vista del cliente).
- `controllers/front/index.php`
  - **Nome classe e classe genitore:** `IndexCustomerfilesModuleFrontController` estende `ModuleFrontController`
  - **Responsabilità:** Spesso un segnaposto o un controller di reindirizzamento. In alcuni moduli, potrebbe fungere da punto di ingresso predefinito o gestire il routing di base.
- `controllers/front/myfiles.php`
  - **Nome classe e classe genitore:** `MyfilesCustomerfilesModuleFrontController` estende `ModuleFrontController`
  - **Responsabilità:** Simile a `customerfiles.php`, questo probabilmente gestisce la sezione specifica "I Miei File" all'interno dell'account del cliente, visualizzando i suoi file caricati e potenzialmente un modulo di caricamento.
- `controllers/front/thumb.php`
  - **Nome classe e classe genitore:** `ThumbCustomerfilesModuleFrontController` estende `ModuleFrontController`
  - **Responsabilità:** Genera e serve miniature per i file immagine caricati, migliorando le prestazioni e la visualizzazione nelle pagine di elenco file.
- `controllers/front/upload.php`
  - **Nome classe e classe genitore:** `UploadCustomerfilesModuleFrontController` estende `ModuleFrontController`
  - **Responsabilità:** Il gestore principale del caricamento. Riceve i caricamenti di file (tramite AJAX o invio di moduli standard), convalida il tipo e la dimensione del file, sposta il file nella directory designata e registra le informazioni sul file nel database.

#### Controller Admin Back-Office

- `controllers/admin/customerFiles.php`
  - **Nome scheda e entità gestita:** "File Cliente" (o simile). Questo controller gestisce la vista a griglia principale di tutti i file caricati dal cliente nel Back Office. Fornisce funzionalità per elencare, filtrare, visualizzare i dettagli, scaricare ed eliminare i file.
  - **Chiavi di configurazione associate:** `PS_SHOP_EMAIL`, `PS_SHOP_NAME` (per le notifiche e-mail), `OF_CEMAIL_CUSTOMER`, `OF_CEMAIL_ATTACH` (probabilmente correlate alle impostazioni del modello e-mail per le notifiche ai clienti).
- `controllers/admin/index.php`
  - **Nome classe e classe genitore:** `IndexCustomerfilesModuleAdminController` estende `ModuleAdminController`
  - **Nome scheda e entità gestita:** Simile a `index.php` del front-office, questo potrebbe essere un segnaposto o un controller di reindirizzamento per la sezione amministrativa del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

L'inventario fornito indica l'assenza di classi personalizzate nella directory `classes/`. Ciò suggerisce che il modulo potrebbe utilizzare `ObjectModel` direttamente all'interno del file del modulo principale o dei controller amministrativi, oppure che si tratta di una struttura di modulo legacy in cui la gestione dei dati è incorporata. Se i dati sono archiviati in una tabella personalizzata, il metodo `install()` del modulo principale ne definirebbe lo schema.

### 4.4 Risorse JavaScript (`views/js/`)

- `js/jquery.form.js`
  - **Ambito:** Probabilmente Front-office e Back-office.
  - **Spiegazione:** Un plugin jQuery per inviare facilmente moduli tramite AJAX, inclusi i caricamenti di file. Gestisce le complessità di `multipart/form-data` e fornisce callback di progresso.
- `js/orders.js`
  - **Ambito:** Back-office (specificamente pagine di dettaglio ordine).
  - **Spiegazione:** Questo script probabilmente aggiunge funzionalità alla pagina di dettaglio ordine di PrestaShop, come la visualizzazione della sezione dei file caricati, la gestione dei download di file lato amministratore o potenzialmente la possibilità per gli amministratori di caricare file a un ordine.
- `js/script-customers.js`
  - **Ambito:** Front-office (pagine account cliente).
  - **Spiegazione:** Gestisce la logica lato client per la sezione "I Miei File" nell'account cliente, inclusa la visualizzazione degli elenchi di file, la gestione delle azioni di eliminazione e l'avvio di nuovi caricamenti.
- `js/script.js`
  - **Ambito:** Front-office (generale, prodotto, pagine carrello) e potenzialmente configurazione Back-office.
  - **Spiegazione:** Uno script generico per il modulo. Probabilmente inizializza i moduli di caricamento, gestisce la convalida dei file (dimensione, tipo) prima dell'invio, visualizza l'avanzamento del caricamento e gestisce le interazioni dell'interfaccia utente relative ai caricamenti di file in varie posizioni del front-office.

### 4.5 Fogli di Stile CSS (`views/css/`)

- `css/ajaxuploader.css`
  - **Ambito:** Front-office.
  - **Spiegazione:** Stili per l'interfaccia di caricamento file basata su AJAX, incluse barre di progresso, zone di trascinamento e rilascio ed elementi di input file.
- `css/backoffice.css`
  - **Ambito:** Back-office.
  - **Spiegazione:** Stili specifici per le pagine di amministrazione del modulo, come la griglia del "Gestore File Cliente", i moduli di configurazione e l'integrazione nella pagina di dettaglio dell'ordine.
- `css/orderfiles.css`
  - **Ambito:** Front-office.
  - **Spiegazione:** Stili generali per i componenti front-office del modulo, inclusi elenchi di file, pulsanti e messaggi visualizzati ai clienti.
- `css.css`
  - **Ambito:** Front-office.
  - **Spiegazione:** Potrebbe essere un foglio di stile legacy o generale, contenente potenzialmente stili core per gli elementi visivi del modulo.

### 4.6 Struttura del Modello Smarty (`views/templates/`)

#### Modelli Hook (`views/templates/hook/`)

- `displayProductPageUploadFormSmall.tpl`: Renderizza un modulo di caricamento compatto nella pagina del prodotto.
- `filesmanager-orderhistory.tpl`: Visualizza la sezione di gestione/caricamento file all'interno della pagina di dettaglio della cronologia ordini del cliente.
- `force-redirect.tpl`: Un modello di utilità, probabilmente per gestire i reindirizzamenti dopo determinate azioni o per visualizzare messaggi prima del reindirizzamento.
- `header.tpl`: Iniettato in `displayHeader`, tipicamente per caricare risorse CSS/JS o meta tag richiesti dal modulo.
- `my-account-17.tpl`: Renderizza il link o il blocco "I Miei File" nella dashboard dell'account cliente per PrestaShop 1.7.x e versioni successive.
- `my-account.tpl`: Renderizza il link o il blocco "I Miei File" nella dashboard dell'account cliente per le versioni precedenti di PrestaShop (1.5.x, 1.6.x).
- `orderConfirmation.tpl`: Visualizza il modulo di caricamento o l'elenco dei file nella pagina di conferma dell'ordine.
- `product-files-button.tpl`: Renderizza un pulsante o un link nella pagina del prodotto che potrebbe aprire un modale di caricamento o reindirizzare a una sezione di caricamento.
- `product-files.tpl`: Visualizza un elenco di file associati a un prodotto o un modulo di caricamento nella pagina del prodotto.
- `shopping-cart-force-files-alert.tpl`: Visualizza un avviso nel carrello se mancano file obbligatori per determinati prodotti.
- `shopping-cart-qty-infos-alert.tpl`: Potenzialmente correlato agli avvisi per i requisiti di file basati sulla quantità nel carrello.
- `shopping-cart.tpl`: Visualizza il modulo di caricamento o l'elenco dei file nella pagina di riepilogo del carrello.
- `tab.tpl`: Un modello di scheda generico, possibilmente utilizzato per visualizzare una scheda "File" nelle pagine dei prodotti o nell'account cliente.

#### Modelli Admin (`views/templates/admin/`)

- `admin.tpl`: Modello amministrativo generale, probabilmente per la pagina di configurazione principale del modulo o una dashboard.
- `adminOrderDetailUpload.tpl`: Integra la sezione di caricamento/gestione file nella pagina di dettaglio ordine di PrestaShop nel Back Office.
- `boscript.tpl`: Contiene JavaScript specifico per il Back Office, potenzialmente per l'inizializzazione di moduli o la gestione di AJAX nelle pagine amministrative.
- `bulk-delete-files.tpl`: Modello per una conferma o un'interfaccia di eliminazione di massa all'interno del gestore file amministrativo.
- `comments_cartfiles.tpl`: Visualizza commenti o note relative ai file caricati per un carrello specifico.
- `comments_orderfiles.tpl`: Visualizza commenti o note relative ai file caricati per un ordine specifico.
- `comments_productfiles.tpl`: Visualizza commenti o note relative ai file caricati per un prodotto specifico.
- `customerfilesmanager.tpl`: Il modello principale per la vista a griglia del "Gestore File Cliente" nel Back Office.
- `_configure/helpers/list/list_action_details.tpl`: Modello per un pulsante di azione "dettagli" in un helper di elenco.
- `_configure/helpers/list/list_content.tpl`: Modello per il contenuto principale di un helper di elenco (ad esempio, le righe dell'elenco dei file).
- `_configure/prestashopbug/helpers/list/*.tpl`: Questi modelli (`list.tpl`, `list_action_delete.tpl`, `list_action_details.tpl`, `list_content.tpl`, `list_footer.tpl`, `list_header.tpl`) suggeriscono un'implementazione personalizzata o sovrascritta dell'helper di elenco, possibilmente per affrontare esigenze di visualizzazione specifiche o bug nelle versioni precedenti di PrestaShop.

#### Modelli Front-office (`views/templates/front/`)

- `access-denied.tpl`: Visualizza un messaggio quando un cliente tenta di accedere a un file o a una pagina senza le autorizzazioni appropriate.
- `customerfilesmanager.tpl`: Il modello principale per la pagina "I Miei File" del cliente, che visualizza i suoi file caricati e le opzioni di gestione.
- `filesmanager.tpl`: Un modello generico di gestione file, potenzialmente utilizzato per vari scenari di elenco e caricamento file nel front-office.
- `my-files.tpl`: Un altro modello per la sezione "I Miei File" del cliente, probabilmente simile a `customerfilesmanager.tpl` o utilizzato in combinazione.

### 4.7 Schema del Database e Mappa degli Hook

- **Tabelle del Database**:

  - Il modulo probabilmente crea almeno una tabella personalizzata per archiviare i metadati sui file caricati. Una struttura di tabella tipica sarebbe `ps_orderfiles` (o simile), contenente campi come:
    - `id_order_file` (Chiave Primaria)
    - `id_customer` (Chiave esterna a `ps_customer`)
    - `id_order` (Chiave esterna a `ps_order`, nullable)
    - `id_product` (Chiave esterna a `ps_product`, nullable)
    - `filename` (Nome originale del file)
    - `filepath` (Percorso del file archiviato sul server)
    - `filesize` (Dimensione in byte)
    - `file_extension`
    - `date_add` (Timestamp del caricamento)
    - `comment` (Commento opzionale del cliente o dell'amministratore)
  - Le impostazioni di configurazione sono archiviate in `ps_configuration` con chiavi come `OF_CEMAIL_CUSTOMER`, `OF_CEMAIL_ATTACH` e altre impostazioni specifiche del modulo.
- **Tabella degli Hook Registrati**:

| Nome Hook | Tempistica di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Inietta CSS, JavaScript e potenzialmente meta tag per il modulo. |
| `displayProductAdditionalInfo` (o hook simile per pagina prodotto) | Nella pagina del prodotto, tipicamente sotto la descrizione del prodotto o il pulsante aggiungi al carrello. | Visualizza il modulo di caricamento o il pulsante specifico del prodotto. |
| `displayShoppingCartFooter` (o hook simile per pagina carrello) | Nella pagina di riepilogo del carrello. | Visualizza il modulo di caricamento o l'elenco dei file a livello di carrello. |
| `displayOrderConfirmation` | Nella pagina di conferma dell'ordine dopo un acquisto riuscito. | Visualizza il modulo di caricamento post-acquisto. |
| `displayCustomerAccount` | Nella dashboard "Il Mio Account" del cliente. | Aggiungi un link o un blocco alla sezione "I Miei File". |
| `displayMyAccountBlock` (PrestaShop 1.6.x) | Nella dashboard "Il Mio Account" del cliente. | Aggiungi un link o un blocco alla sezione "I Miei File". |
| `displayRightColumn` / `displayLeftColumn` | Nelle colonne laterali del negozio. | Visualizza un pulsante/link generico "Carica File" se configurato. |
| `displayFooter` | Nel piè di pagina di ogni pagina. | Visualizza un pulsante/link generico "Carica File" se configurato. |
| `actionValidateOrder` | Dopo che un ordine è stato convalidato con successo. | Potenzialmente utilizzato per collegare i file caricati all'ID ordine appena creato o per attivare le notifiche dell'amministratore. |
| `actionProductUpdate` / `actionProductAdd` | Quando un prodotto viene aggiornato o aggiunto. | Potrebbe essere utilizzato per gestire i requisiti di file specifici del prodotto o per pulire i file associati. |
| `actionCustomerAccountAdd` | Quando viene creato un nuovo account cliente. | (Meno probabile per questo modulo, ma possibile per la configurazione iniziale). |
| `actionAdminOrdersView` | Quando un amministratore visualizza un ordine nel Back Office. | Inietta la sezione di gestione file del modulo nella pagina di dettaglio dell'ordine. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo "Caricamento File Cliente", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a garantire che il tuo modulo funzioni perfettamente e ti aiuti a massimizzare il potenziale del tuo negozio.
