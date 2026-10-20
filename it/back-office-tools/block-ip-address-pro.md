---
title: "Block IP address Pro - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Block IP address Pro di MyPresta.eu."
sidebar:
  label: "Block IP address Pro"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Block IP address Pro su MyPresta.eu](https://mypresta.eu/modules/administration-tools/block-ip-address-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/block-ip-address-pro/)
>
> ---


# Block IP address Pro

## 1. Requisiti e Compatibilità
- **Versioni PrestaShop supportate**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL) tipicamente disponibili su qualsiasi ambiente di hosting web moderno.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Block IP address Pro)

Questa è la schermata di configurazione principale per il modulo, dove definisci il comportamento globale per i visitatori bloccati.

-   **Posizione del menu:** Back Office > Moduli > Gestione moduli > Block IP address Pro > Configura

#### Impostazioni e Opzioni:

1.  **Visualizza notifiche di aggiornamento**
    -   **Cosa fa questa impostazione:** Controlla se ricevi notifiche nel tuo back office di PrestaShop quando è disponibile una nuova versione del modulo "Block IP address Pro".
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Vedrai avvisi o messaggi nel tuo pannello di amministrazione se viene rilasciato un aggiornamento, aiutandoti a mantenere il tuo modulo aggiornato.
        -   *Quando disabilitato:* Non riceverai queste notifiche e dovrai controllare manualmente gli aggiornamenti su MyPresta.eu.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio del commerciante:** Mantenere questa opzione abilitata ti assicura di essere sempre a conoscenza di nuove funzionalità, correzioni di bug o miglioramenti della sicurezza per il modulo.

2.  **Messaggio per utenti bloccati (`banippro_msg`)**
    -   **Cosa fa questa impostazione:** Questo è il messaggio personalizzato che verrà visualizzato agli utenti il cui indirizzo IP è stato bloccato, *se* scegli di non reindirizzarli.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando compilato:* Gli utenti bloccati vedranno questo testo specifico su una pagina vuota invece del contenuto del tuo negozio.
        -   *Quando vuoto:* Se anche il reindirizzamento è disabilitato, gli utenti bloccati potrebbero vedere un errore generico o una pagina vuota senza un messaggio specifico.
    -   **Valore consigliato:** "L'accesso a questo negozio è stato negato per il tuo indirizzo IP." (o un messaggio simile, educato ma fermo).
    -   **Scenario / esempio del commerciante:** Potresti voler visualizzare "Siamo spiacenti, ma l'accesso dalla tua posizione è stato limitato a causa di attività insolite." per informare l'utente senza fornire troppi dettagli.

3.  **Reindirizza utenti bloccati (`banippro_redirect`)**
    -   **Cosa fa questa impostazione:** Determina se agli utenti bloccati viene mostrato un messaggio o se vengono inviati automaticamente a una pagina web diversa.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Gli utenti bloccati verranno immediatamente reindirizzati all'URL specificato nell'impostazione "URL di reindirizzamento".
        -   *Quando disabilitato:* Gli utenti bloccati vedranno il "Messaggio per utenti bloccati" che hai definito.
    -   **Valore consigliato:** SÌ (Il reindirizzamento è spesso un'esperienza utente più pulita rispetto a una pagina vuota con un messaggio).
    -   **Scenario / esempio del commerciante:** Se vuoi allontanare completamente gli spammer dal tuo sito, o indirizzare un cliente problematico a una pagina di servizio clienti, abilita questa opzione.

4.  **URL di reindirizzamento (`banippro_url`)**
    -   **Cosa fa questa impostazione:** L'indirizzo web specifico (URL) a cui gli utenti bloccati verranno reindirizzati se l'impostazione "Reindirizza utenti bloccati" è abilitata.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando compilato con un URL valido:* Gli utenti bloccati verranno inviati a questa pagina esatta.
        -   *Quando vuoto:* Se il reindirizzamento è abilitato ma non viene fornito alcun URL, il comportamento del modulo potrebbe essere imprevedibile, o potrebbe tornare a mostrare il messaggio.
    -   **Valore consigliato:** L'URL della homepage del tuo negozio (es. `https://www.iltuonegozio.com/`), o una pagina specifica "Contattaci", o anche un sito esterno come Google.
    -   **Scenario / esempio del commerciante:** Potresti reindirizzarli a `https://www.iltuonegozio.com/contattaci` se vuoi che ti contattino, o a `https://www.google.com` per rimuoverli semplicemente dal tuo sito.

#### Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
|---|---|---|---|
| Configurazione modulo | Visualizza notifiche di aggiornamento | SÌ | Mostra avvisi per nuove versioni del modulo. |
| Configurazione modulo | Messaggio per utenti bloccati | "L'accesso a questo negozio è stato negato per il tuo indirizzo IP." | Testo visualizzato agli utenti bloccati se non reindirizzati. |
| Configurazione modulo | Reindirizza utenti bloccati | SÌ | Se abilitato, invia gli utenti bloccati a un URL specificato. |
| Configurazione modulo | URL di reindirizzamento | URL della homepage del tuo negozio | La destinazione per gli utenti bloccati reindirizzati. |

### 2.2 Schermata di amministrazione dedicata: Gestione indirizzi IP (Back Office > Moduli > Block IP address Pro > Gestisci indirizzi IP)

Questa è la schermata di gestione principale in cui aggiungi, modifichi, attivi e disattivi specifici indirizzi IP da bloccare.

-   **Posizione del menu:** Dopo aver installato il modulo, una nuova voce di menu apparirà sotto **Moduli > Block IP address Pro** (o simile, a seconda della versione di PrestaShop e della registrazione del menu del modulo). Clicca su "Gestisci indirizzi IP" o "Banna indirizzi IP".

#### Azioni e Impostazioni disponibili:

1.  **Tabella di elenco indirizzi IP:**
    -   Questa tabella visualizza tutti gli indirizzi IP che hai configurato per il blocco.
    -   **Colonne:**
        -   **ID:** Identificatore univoco per la voce IP bloccata.
        -   **Indirizzo IP:** L'indirizzo IP effettivo che viene bloccato (es. `192.168.1.1`, `203.0.113.45`).
        -   **Numero di visualizzazioni:** Una statistica che mostra quante volte questo specifico indirizzo IP ha tentato di accedere al tuo negozio ed è stato bloccato. Questo è prezioso per identificare minacce persistenti.
        -   **Commento:** La tua nota interna sul motivo per cui questo IP è stato bloccato (es. "Bot spammer", "Scraping concorrente", "Cliente problematico").
        -   **Attivo:** Un interruttore (On/Off) per abilitare o disabilitare rapidamente il blocco per questo specifico IP senza eliminare la voce.
        -   **Azioni:** Pulsanti per "Modifica" o "Elimina" singole voci IP.

2.  **Aggiunta di un nuovo indirizzo IP:**
    -   Clicca sul pulsante "Aggiungi nuovo indirizzo IP" (o simile, di solito un'icona più o un pulsante "Aggiungi nuovo" in alto a destra della tabella).
    -   **Campi del modulo:**
        -   **IP:** Inserisci l'indirizzo IP esatto che desideri bloccare.
        -   **Commento:** Aggiungi una nota descrittiva per il tuo riferimento (es. "Fonte di spam nota dalle analisi", "Cliente 'Mario Rossi' che causa problemi").
        -   **Attivo:** Scegli "On" per attivare immediatamente il blocco, o "Off" per salvare la voce ma mantenerla inattiva per ora.
    -   **Salva:** Clicca su "Salva" per aggiungere il nuovo IP alla tua lista di blocco.

3.  **Modifica di un indirizzo IP esistente:**
    -   Clicca sull'icona "Modifica" accanto a un indirizzo IP nella tabella di elenco.
    -   Puoi modificare lo stato "IP", "Commento" e "Attivo".
    -   **Salva:** Clicca su "Salva" per applicare le modifiche.

4.  **Eliminazione di un indirizzo IP:**
    -   Clicca sull'icona "Elimina" accanto a un indirizzo IP.
    -   Conferma l'eliminazione. Questo rimuoverà permanentemente l'IP dalla tua lista di blocco.

#### Effetto delle modifiche:
-   **Aggiunta di un IP:** Una volta salvato e attivo, qualsiasi visitatore che tenti di accedere al tuo negozio da quell'indirizzo IP verrà immediatamente bloccato o reindirizzato in base alla configurazione globale del tuo modulo.
-   **Modifica di un IP:** Le modifiche all'indirizzo IP, al commento o allo stato attivo avranno effetto immediatamente.
-   **Disattivazione di un IP:** L'indirizzo IP rimane nella tua lista, ma i visitatori da quell'IP non verranno più bloccati. Questo è utile per blocchi temporanei o se un IP è stato bloccato per errore.
-   **Eliminazione di un IP:** L'IP viene rimosso permanentemente dalla lista di blocco e i visitatori da quell'IP riacquisteranno pieno accesso al tuo negozio.

#### Flusso di lavoro consigliato per la gestione quotidiana del negozio:
1.  **Monitora le analisi:** Controlla regolarmente le analisi del tuo sito web per modelli di traffico sospetti, alti tassi di rimbalzo da IP specifici o attività insolite.
2.  **Identifica gli IP problematici:** Se trovi un indirizzo IP che causa costantemente problemi (es. ripetuti tentativi di accesso falliti, scraping eccessivo di pagine, commenti spam), annotalo.
3.  **Aggiungi alla lista di blocco:** Vai alla schermata "Gestisci indirizzi IP", clicca su "Aggiungi nuovo indirizzo IP", inserisci l'IP, aggiungi un commento descrittivo e impostalo su "On".
4.  **Rivedi le statistiche:** Controlla periodicamente la colonna "Numero di visualizzazioni" per gli IP bloccati. Numeri elevati indicano tentativi persistenti, confermando l'efficacia del tuo blocco.
5.  **Gestisci e perfeziona:** Se un indirizzo IP non è più una minaccia, puoi disattivarlo (impostare "Attivo" su "Off") o eliminarlo completamente.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
|---|---|---|---|
| Gestione indirizzi IP | Aggiungi nuovo IP | N/A | Aggiunge un nuovo indirizzo IP alla lista di blocco. |
| Gestione indirizzi IP | Indirizzo IP (Campo) | N/A | L'IP specifico da bloccare. |
| Gestione indirizzi IP | Commento (Campo) | N/A | La tua nota interna per l'IP bloccato. |
| Gestione indirizzi IP | Attivo (Toggle) | On | Abilita/disabilita il blocco per un IP specifico. |
| Gestione indirizzi IP | Numero di visualizzazioni (Colonna) | 0 | Traccia quante volte un IP è stato bloccato. |
| Gestione indirizzi IP | Azioni Modifica / Elimina | N/A | Modifica o rimuovi le voci IP bloccate esistenti. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho bloccato un IP, ma l'utente può ancora accedere al mio negozio. Cosa c'è che non va?**
R:
1.  **Controlla lo stato "Attivo":** Assicurati che l'interruttore "Attivo" per quell'IP specifico nella schermata "Gestisci indirizzi IP" sia impostato su "On".
2.  **Svuota la cache:** PrestaShop utilizza la cache. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" per le versioni precedenti). Questo assicura che le impostazioni del modulo vengano ricaricate.
3.  **Verifica l'indirizzo IP:** Ricontrolla di aver inserito l'indirizzo IP corretto. A volte gli IP dinamici cambiano, o potresti avere un problema di proxy/CDN.
4.  **Cache del browser:** Chiedi all'utente bloccato di svuotare la cache del browser o di provare ad accedere da una finestra in incognito.

**D: Il mio cliente legittimo è bloccato! Come risolvo questo problema?**
R:
1.  **Identifica il loro IP:** Chiedi al cliente il suo attuale indirizzo IP (possono trovarlo cercando "qual è il mio IP" su Google).
2.  **Controlla la tua lista di blocco:** Vai su **Moduli > Block IP address Pro > Gestisci indirizzi IP** e cerca il loro IP.
3.  **Disattiva o Elimina:** Se trovato, imposta l'interruttore "Attivo" su "Off" per quella voce o eliminala completamente.
4.  **Svuota la cache:** Ricorda di svuotare la cache di PrestaShop in seguito.

**D: Posso bloccare un intervallo di indirizzi IP invece di uno solo?**
R: La versione attuale del modulo supporta il blocco di singoli indirizzi IP. Per bloccare intervalli, dovresti inserire ogni IP all'interno dell'intervallo individualmente, o considerare il blocco IP a livello di server se hai accesso al firewall del tuo server (ad esempio, tramite regole `.htaccess`).

**D: Cosa succede se abilito il reindirizzamento ma non fornisco un URL di reindirizzamento?**
R: Se "Reindirizza utenti bloccati" è abilitato ma "URL di reindirizzamento" è vuoto, il comportamento del modulo potrebbe essere incoerente. È buona pratica fornire sempre un URL valido se il reindirizzamento è attivo. Se non vuoi reindirizzare, disabilita l'opzione "Reindirizza utenti bloccati" e usa invece il messaggio personalizzato.

**D: Questo modulo rallenterà il mio negozio?**
R: No, il modulo è progettato per essere molto leggero ed efficiente. Controlla l'indirizzo IP del visitatore molto presto nel processo di caricamento di PrestaShop. Se un IP è bloccato, la richiesta viene terminata o reindirizzata rapidamente, spesso *prima* che il tuo negozio inizi a caricare il suo contenuto completo, il che può effettivamente *migliorare* le prestazioni riducendo il carico indesiderato del server.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce un'analisi tecnica approfondita del modulo "Block IP address Pro" per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura
Il modulo "Block IP address Pro" segue un'architettura standard dei moduli PrestaShop, sfruttando principalmente la classe `Module` per l'installazione/disinstallazione e la configurazione, e `AdminController` per la gestione del back-office. Utilizza una tabella di database personalizzata per archiviare gli indirizzi IP bloccati e si aggancia all'hook `actionFrontControllerAfterInit` per eseguire il controllo IP il prima possibile nel ciclo di vita della richiesta.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:
    Il modulo non ha controller front-office dedicati. La logica di blocco IP è gestita direttamente all'interno del file principale del modulo (`banippro.php`) tramite un hook, garantendo un'esecuzione precoce.

-   **Controller Admin Back-Office**:
    1.  `banippro/controllers/admin/AdminBanIpProController.php`
        *   **Nome classe e classe genitore:** `AdminBanIpProController` estende `ModuleAdminController`.
        *   **Responsabilità:** Questo controller è responsabile della gestione dell'elenco degli indirizzi IP bloccati nel Back Office di PrestaShop. Fornisce l'interfaccia CRUD (Create, Read, Update, Delete) standard per l'entità `BanIpPro`. Gestisce:
            *   La visualizzazione dell'elenco degli IP bloccati con i loro dettagli (IP, visualizzazioni, commento, stato attivo).
            *   L'aggiunta di nuovi indirizzi IP alla lista di blocco.
            *   La modifica delle voci degli indirizzi IP esistenti.
            *   L'eliminazione degli indirizzi IP dalla lista di blocco.
            *   La gestione dell'interruttore di stato "Attivo" per ogni IP.
            *   I metodi `initContent()`, `renderList()`, `renderForm()` sono tipicamente sovrascritti qui per personalizzare la visualizzazione e i moduli.
            *   Mappa alla tabella del database `ban` (o simile, come definito dal modello `BanIpPro` se esistesse).

    2.  `banippro/controllers/admin/index.php`
        *   **Responsabilità:** Questo è un file `index.php` vuoto standard spesso presente nelle sottodirectory dei moduli PrestaShop. Il suo scopo principale è impedire l'elenco delle directory sui server web per motivi di sicurezza. Non contiene alcuna logica funzionale per il modulo.

### 4.3 Classi e modelli principali (`classes/`)
La descrizione del modulo indica l'assenza di classi personalizzate nella directory `classes/`. L'entità `BanIpPro` (per gli IP bloccati) è probabilmente gestita direttamente all'interno di `AdminBanIpProController` e del file principale `banippro.php`, potenzialmente utilizzando una semplice interazione con la classe `Db` o una struttura di array interna se non completamente conforme a `ObjectModel`. Se fosse stato utilizzato un `ObjectModel`, sarebbe stato tipicamente chiamato `BanIpPro` e risiederebbe in `classes/BanIpPro.php`.

Dato che `AdminBanIpProController` gestisce un'entità "ban", ciò implica una struttura dati sottostante. Se non un `ObjectModel` dedicato, si tratterebbe di query dirette al database.

### 4.4 Risorse JavaScript (`views/js/`)
La descrizione del modulo indica l'assenza di file JavaScript personalizzati. Qualsiasi elemento interattivo nel back office (come interruttori o convalida dei moduli) è probabilmente gestito dal JS principale di PrestaShop o da script inline all'interno dei template.

### 4.5 Fogli di stile CSS (`views/css/`)
La descrizione del modulo indica l'assenza di file CSS personalizzati. Lo stile per la configurazione del back-office e le schermate di gestione IP si baserà interamente sul CSS del tema predefinito del back-office di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)
La descrizione del modulo indica l'assenza di file di template personalizzati.
-   **Template degli hook**: Il comportamento front-office del modulo (blocco/reindirizzamento) è gestito programmaticamente nell'hook, non tramite un template.
-   **Template admin**: Il modulo di configurazione per `getContent()` e le viste elenco/modulo per `AdminBanIpProController` sono probabilmente renderizzati utilizzando le classi helper predefinite di PrestaShop (`HelperForm`, `HelperList`) che generano direttamente HTML, o si basano su template inline molto minimali, se presenti.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**:
    Il modulo crea almeno una tabella personalizzata durante l'installazione per archiviare gli indirizzi IP bloccati.
    -   `ps_banippro` (o simile, ad esempio, `ps_ban_ip_pro`):
        *   `id_banippro` (Chiave primaria, INT)
        *   `ip_address` (VARCHAR, memorizza l'indirizzo IP da bloccare)
        *   `comment` (TEXT, per note dell'amministratore)
        *   `views` (INT, contatore di quante volte questo IP è stato bloccato)
        *   `active` (TINYINT(1), 0 o 1, per abilitare/disabilitare il blocco)

    Le impostazioni di configurazione (`mypresta_updates`, `banippro_msg`, `banippro_redirect`, `banippro_url`) sono memorizzate nella tabella `ps_configuration`.

-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
|---|---|---|
| `actionFrontControllerAfterInit` | Eseguito dopo l'inizializzazione del controller frontale ma prima che venga renderizzato qualsiasi contenuto. | **CRITICO:** Qui il modulo esegue la sua funzione principale: controllare l'IP del visitatore rispetto alla lista bloccata. Se viene trovata una corrispondenza, visualizza il messaggio personalizzato o esegue un reindirizzamento, interrompendo efficacemente l'ulteriore esecuzione della pagina. |
| `displayHome` | Renderizza il contenuto sulla homepage. | Probabilmente utilizzato per le notifiche di aggiornamento o altri contenuti specifici del modulo se il modulo avesse un componente front-office. Nel contesto di questo modulo, potrebbe essere un hook legacy o utilizzato per logiche molto specifiche e non bloccanti. |
| `home` | Alias per `displayHome` in alcuni contesti. | Come `displayHome`. |
| `header` | Renderizza il contenuto all'interno della sezione `<head>` dell'HTML. | Utilizzato per aggiungere CSS, JavaScript o meta tag. In questo modulo, potrebbe essere utilizzato per le notifiche di aggiornamento o per garantire il caricamento anticipato di script/stili, se necessario. |
| `actionAdminControllerSetMedia` | Eseguito quando un controller admin sta impostando i suoi media (CSS/JS). | Utilizzato dal modulo per aggiungere eventuali file CSS o JavaScript specifici richiesti per le sue pagine di configurazione del back-office (ad esempio, per `AdminBanIpProController`). |
| `ActionAdminControllerSetMedia` | (Duplicato del precedente, differenza di maiuscole/minuscole) | Come `actionAdminControllerSetMedia`. Gli hook di PrestaShop sono generalmente case-insensitive, ma i moduli a volte li registrano entrambi per compatibilità. |
| `displayHeader` | Renderizza il contenuto all'interno della sezione `<header>` dell'HTML (spesso nel `<body>` prima del contenuto principale). | Simile a `header`, ma tipicamente per elementi visibili. In questo modulo, è meno probabile che abbia un impatto diretto sul front-office data la sua natura di blocco. |

## 5. Supporto ufficiale e aggiornamenti
Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto professionale, fai riferimento al tuo account cliente su MyPresta.eu. Il nostro team è dedicato a fornire assistenza tempestiva e a garantire che il tuo modulo funzioni senza problemi.
-   **MyPresta.eu Cronologia ordini e download:** [https://mypresta.eu/my-account/orders/](https://mypresta.eu/my-account/orders/)
-   **MyPresta.eu Contatto supporto:** [https://mypresta.eu/contact](https://mypresta.eu/contact)
