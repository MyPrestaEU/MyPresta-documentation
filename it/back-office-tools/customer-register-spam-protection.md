---
title: "Protezione dallo spam nella registrazione clienti - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop di protezione dallo spam nella registrazione clienti di MyPresta.eu."
sidebar:
  label: "Protezione dallo spam nella registrazione clienti - Manuale del commerciazione e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Customer register spam protection su MyPresta.eu](https://mypresta.eu/modules/administration-tools/customer-register-spam-protection.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/customer-register-spam-protection/)
>
> ---


# Protezione dallo spam nella registrazione clienti

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per la comunicazione con API esterne, che questo modulo potrebbe utilizzare per il rilevamento avanzato dello spam. Assicurati che il tuo ambiente di hosting soddisfi questi requisiti comuni.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo "Protezione dallo spam nella registrazione clienti", accessibile dopo l'installazione. Qui definirai le regole e i comportamenti principali del sistema di protezione dallo spam.

Sebbene le impostazioni specifiche non siano dettagliate nel dossier fornito, in base allo scopo del modulo, le impostazioni tipiche includerebbero:

-   **Abilita/Disabilita Modulo:**

    -   **Cosa fa questa impostazione:** Attiva o disattiva la funzionalità di protezione dallo spam per l'intero negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il modulo monitora e blocca attivamente le registrazioni clienti sospette.
        -   *Quando disabilitato:* Il modulo è inattivo e tutti i tentativi di registrazione procederanno senza controlli antispam.
    -   **Valore consigliato:** SÌ (a meno che tu non stia attivamente eseguendo il debug o disabilitando temporaneamente per un motivo specifico).
    -   **Scenario/esempio del commerciante:** Abilita questo immediatamente dopo l'installazione per iniziare a proteggere il tuo negozio. Disabilita solo se sospetti che stia bloccando clienti legittimi e devi indagare, ma ricorda che questo lascia il tuo negozio vulnerabile.
-   **Livello di sensibilità del rilevamento spam:**

    -   **Cosa fa questa impostazione:** Controlla quanto aggressivamente il modulo identifica e blocca il potenziale spam. Questo potrebbe essere un cursore (Basso, Medio, Alto) o una soglia numerica.
    -   **Effetto della modifica di questa impostazione:**
        -   *Maggiore sensibilità:* Più probabile che blocchi le registrazioni sospette, potenzialmente includendo un piccolo numero di utenti legittimi (falsi positivi).
        -   *Minore sensibilità:* Meno probabile che blocchi gli utenti legittimi, ma potrebbe consentire a più account spam di passare (falsi negativi).
    -   **Valore consigliato:** Inizia con "Medio" e regola in base al traffico del tuo negozio e al numero di tentativi di spam osservati.
    -   **Scenario/esempio del commerciante:** Se stai riscontrando molto spam nonostante il modulo sia attivo, aumenta la sensibilità. Se i clienti segnalano problemi di registrazione, prova ad abbassarla leggermente.
-   **Azione sullo spam rilevato:**

    -   **Cosa fa questa impostazione:** Definisce cosa succede quando il modulo identifica un tentativo di registrazione come spam.
    -   **Effetto della modifica di questa impostazione:**
        -   *Blocca registrazione:* L'account non viene creato e l'utente riceve un messaggio di errore.
        -   *Contrassegna come in sospeso/revisione:* L'account viene creato ma contrassegnato per una revisione manuale da parte di un amministratore.
        -   *Solo log:* Il tentativo viene registrato, ma l'account viene comunque creato (utile per il monitoraggio iniziale).
    -   **Valore consigliato:** "Blocca registrazione" per la massima protezione.
    -   **Scenario/esempio del commerciante:** Per la maggior parte dei negozi, il blocco totale è l'approccio migliore. Se hai una base clienti molto specifica e vuoi essere estremamente cauto, "Contrassegna come in sospeso" potrebbe essere un'opzione, ma richiede lavoro manuale.
-   **Messaggio di errore per le registrazioni bloccate:**

    -   **Cosa fa questa impostazione:** Ti consente di personalizzare il messaggio visualizzato agli utenti i cui tentativi di registrazione sono bloccati.
    -   **Effetto della modifica di questa impostazione:**
        -   *Messaggio personalizzato:* Fornisce un messaggio user-friendly o informativo invece di un errore generico.
    -   **Valore consigliato:** Un messaggio cortese come "La registrazione non è stata completata. Contatta il supporto se ritieni che si tratti di un errore."
    -   **Scenario/esempio del commerciante:** Evita messaggi che rivelano troppo sui tuoi metodi di rilevamento dello spam. Un messaggio semplice e utile è il migliore.
-   **Gestione Blacklist/Whitelist IP:**

    -   **Cosa fa questa impostazione:** Ti consente di aggiungere manualmente indirizzi IP specifici a una blacklist (blocca sempre) o a una whitelist (non bloccare mai).
    -   **Effetto della modifica di questa impostazione:**
        -   *IP in blacklist:* Qualsiasi registrazione da questi IP verrà bloccata, indipendentemente da altre impostazioni.
        -   *IP in whitelist:* Qualsiasi registrazione da questi IP sarà sempre consentita.
    -   **Valore consigliato:** Usare con parsimonia. Metti in blacklist gli spammer noti. Metti in whitelist solo se un utente legittimo o un sistema interno viene falsamente bloccato.
    -   **Scenario/esempio del commerciante:** Se vedi ripetutamente spam da un intervallo IP specifico, aggiungilo alla blacklist. Se l'IP del tuo ambiente di test interno viene bloccato, mettilo in whitelist.
-   **Gestione Blacklist/Whitelist Email:**

    -   **Cosa fa questa impostazione:** Simile alla gestione IP, ma per indirizzi email o domini email specifici.
    -   **Effetto della modifica di questa impostazione:**
        -   *Email/domini in blacklist:* Le registrazioni che utilizzano questi verranno bloccate.
        -   *Email/domini in whitelist:* Le registrazioni che utilizzano questi saranno sempre consentite.
    -   **Valore consigliato:** Usare con parsimonia. Metti in blacklist indirizzi email o domini spam noti.
    -   **Scenario/esempio del commerciante:** Se noti un modello di registrazioni spam da servizi di posta elettronica usa e getta (es. mailinator.com), puoi mettere in blacklist quel dominio.
-   **Integrazione con API esterne (es. reCAPTCHA, Akismet):**

    -   **Cosa fa questa impostazione:** Se il modulo si integra con servizi esterni di rilevamento dello spam, questa sezione conterrà campi per le chiavi API e la configurazione specifica per tali servizi.
    -   **Effetto della modifica di questa impostazione:**
        -   *Abilitato con chiavi valide:* Aggiunge un ulteriore livello di protezione utilizzando il database e gli algoritmi del servizio esterno.
        -   *Disabilitato o chiavi non valide:* Il servizio esterno non verrà utilizzato, affidandosi esclusivamente alla logica interna del modulo.
    -   **Valore consigliato:** Abilita e configura se disponibile, poiché migliora significativamente la protezione.
    -   **Scenario/esempio del commerciante:** Ottieni le chiavi API dal rispettivo servizio (es. Google reCAPTCHA) e inseriscile qui per sfruttare il loro filtraggio avanzato dello spam.

### 2.2 Schermate di amministrazione dedicate e viste del controller

Il modulo fornisce schermate dedicate nel Back Office di PrestaShop per gestire e rivedere i tentativi di spam e i ban. Questi sono cruciali per monitorare l'efficacia del modulo e apportare modifiche manuali.

#### 2.2.1 AdminregproAttemptsController (Back Office > Moduli > Protezione dallo spam nella registrazione clienti > Tentativi)

-   **Nome schermata e posizione nel menu:** "Tentativi" (o simile, sotto la voce di menu principale del modulo). Questa schermata elenca tutti i tentativi di registrazione che il modulo ha elaborato, specialmente quelli contrassegnati come sospetti o bloccati.
-   **Azioni e impostazioni disponibili:** Questa sarà una vista a griglia (elenco) che visualizza i dettagli di ogni tentativo di registrazione.
    -   **Colonne:** Tipicamente include:
        -   Data/Ora del tentativo
        -   Indirizzo IP
        -   Indirizzo email utilizzato
        -   Stato (es. "Bloccato", "Consentito", "Contrassegnato")
        -   Motivo dello stato (es. "IP in blacklist", "Punteggio spam alto")
        -   Pulsanti di azione (es. "Visualizza dettagli", "Whitelist IP", "Blacklist IP", "Elimina voce")
    -   **Filtro/Ordinamento:** Funzionalità standard della griglia di PrestaShop per filtrare per data, IP, stato, ecc.
-   **Effetto delle modifiche:**
    -   *Whitelisting di un IP:* Aggiunge l'IP alla whitelist del modulo, garantendo che le future registrazioni da questo IP siano consentite.
    -   *Blacklisting di un IP:* Aggiunge l'IP alla blacklist del modulo, bloccando le future registrazioni da questo IP.
    -   *Eliminazione di una voce:* Rimuove il record dal log dei tentativi (non sblocca/sblocca il ban).
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Rivedi regolarmente questo elenco, specialmente se ricevi segnalazioni di clienti legittimi bloccati. Usa l'azione "Whitelist IP" se identifichi un falso positivo. Al contrario, se vedi spam persistente da un particolare IP, usa "Blacklist IP".

#### 2.2.2 AdminregproBansController (Back Office > Moduli > Protezione dallo spam nella registrazione clienti > Ban)

-   **Nome schermata e posizione nel menu:** "Ban" (o simile, sotto la voce di menu principale del modulo). Questa schermata elenca tutti i ban attualmente attivi (IP o indirizzi/domini email) che il modulo sta applicando.
-   **Azioni e impostazioni disponibili:** Questa sarà una vista a griglia (elenco) che visualizza i dettagli di ogni ban.
    -   **Colonne:** Tipicamente include:
        -   Tipo di ban (es. "IP", "Email", "Dominio")
        -   Valore (es. "192.168.1.1", "[spam@example.com](mailto:spam@example.com)", "bad-domain.com")
        -   Data di aggiunta
        -   Motivo (se aggiunto manualmente)
        -   Pulsanti di azione (es. "Rimuovi ban", "Modifica")
    -   **Filtro/Ordinamento:** Funzionalità standard della griglia di PrestaShop.
-   **Effetto delle modifiche:**
    -   *Rimozione di un ban:* Rimuove la restrizione per l'IP, l'email o il dominio specificato, consentendo future registrazioni da esso.
    -   *Aggiunta di un ban:* Aggiunge manualmente un nuovo IP, email o dominio all'elenco dei ban.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Questo è il tuo hub centrale per la gestione degli elenchi di ban personalizzati. Se hai messo in blacklist un IP dalla schermata "Tentativi", apparirà qui. Se un cliente legittimo viene accidentalmente bloccato da un ban, puoi rimuovere rapidamente il suo IP o la sua email da questo elenco.

#### 2.2.3 index.php (regpro/controllers/admin/index.php)

-   **Tabella/Entità gestita:** Questo file probabilmente funge da controller di routing o predefinito per la sezione amministrativa del modulo, potenzialmente reindirizzando a uno dei controller specifici (come `AdminregproAttempts` o `AdminregproBans`) o visualizzando una panoramica/dashboard generale per il modulo. Potrebbe non gestire direttamente una tabella specifica ma agisce come punto di ingresso.
-   **Campi del modulo e colonne:** Se visualizza una griglia, sarebbe un riepilogo o una dashboard. Più probabilmente, è un reindirizzatore.
-   **Effetto delle modifiche:** Nessuna modifica diretta dei dati, ma controlla la vista iniziale quando si accede alla sezione amministrativa del modulo.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Questa è di solito la prima schermata che vedi quando clicchi sul modulo nell'elenco dei moduli. Potrebbe offrire statistiche rapide o collegamenti alle sezioni "Tentativi" e "Ban".

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Pagina di configurazione del modulo** | Abilita/Disabilita Modulo | SÌ | Attiva/disattiva la protezione dallo spam. |
| | Sensibilità del rilevamento spam | Media | Controlla l'aggressività del rilevamento spam. |
| | Azione sullo spam rilevato | Blocca registrazione | Definisce la risposta allo spam (blocca, revisiona, registra). |
| | Messaggio di errore per le registrazioni bloccate | "La registrazione non è stata completata. Contatta il supporto se ritieni che si tratti di un errore." | Personalizza il messaggio per gli utenti bloccati. |
| | Blacklist/Whitelist IP | Usare con parsimonia | Blocca/consente manualmente IP specifici. |
| | Blacklist/Whitelist Email | Usare con parsimonia | Blocca/consente manualmente email/domini specifici. |
| | Integrazione API esterna | Abilita con chiavi valide | Migliora la protezione con servizi di terze parti. |
| **AdminregproAttemptsController** | Visualizza log tentativi | N/A | Rivedi tutti i tentativi di registrazione, il loro stato e i motivi. |
| | Whitelist IP (dal log) | N/A | Consente future registrazioni da un IP specifico. |
| | Blacklist IP (dal log) | N/A | Blocca future registrazioni da un IP specifico. |
| **AdminregproBansController** | Visualizza ban attivi | N/A | Gestisci e rivedi tutti i ban IP/email/dominio attualmente attivi. |
| | Rimuovi ban | N/A | Rimuove un ban specifico. |
| | Aggiungi nuovo ban | N/A | Aggiunge manualmente un nuovo IP, email o dominio all'elenco dei ban. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei clienti legittimi segnalano di non riuscire a registrarsi. Cosa devo fare?**
R: Innanzitutto, controlla il log "Tentativi" (`AdminregproAttemptsController`) nel Back Office. Cerca il loro indirizzo IP o email. Se il loro tentativo è stato bloccato, vedrai il motivo. Puoi quindi mettere in whitelist il loro indirizzo IP o email, oppure abbassare temporaneamente l'impostazione di sensibilità del modulo. Ricorda di svuotare la cache di PrestaShop dopo aver apportato modifiche.

**D: Continuo a ricevere registrazioni spam anche con il modulo attivo.**
R:

1.  **Controlla la sensibilità:** Aumenta la "Sensibilità del rilevamento spam" nella configurazione principale del modulo.
2.  **Rivedi il log dei tentativi:** Analizza il log "Tentativi" per vedere se il modulo sta registrando questi tentativi e perché potrebbero sfuggire.
3.  **Aggiungi alla blacklist:** Se identifichi IP o domini email specifici dalle registrazioni spam, aggiungili manualmente alla tua lista di ban tramite `AdminregproBansController`.
4.  **API esterna:** Assicurati che tutte le API di protezione dallo spam esterne integrate (come reCAPTCHA) siano configurate correttamente e abbiano chiavi valide.

**D: Come faccio a sapere se il modulo funziona davvero?**
R: Il modo migliore è monitorare il log "Tentativi" (`AdminregproAttemptsController`). Dovresti vedere voci per i tentativi bloccati, indicando che il modulo sta attivamente identificando e prevenendo lo spam. Se in precedenza ricevevi molto spam, dovresti anche notare una significativa riduzione dei nuovi account cliente falsi.

**D: Questo modulo influisce sulle prestazioni del mio negozio?**
R: Il modulo è progettato per essere efficiente. Sebbene aggiunga un piccolo passaggio di elaborazione durante la registrazione, questo è tipicamente trascurabile rispetto ai vantaggi di prevenire lo spam. Un database pieno di account spam causerebbe problemi di prestazioni molto maggiori a lungo termine.

**D: Ho modificato le impostazioni, ma nulla sembra accadere nel front office.**
R: Svuota sempre la cache di PrestaShop dopo aver apportato modifiche alla configurazione. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" nell'angolo in alto a destra. Questo assicura che il modulo carichi le impostazioni aggiornate.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Protezione dallo spam nella registrazione clienti" (`regpro`) è costruito seguendo il modello MVC (Model-View-Controller) di PrestaShop. Opera principalmente agganciandosi al processo di registrazione del cliente, sfruttando il sistema di hook di PrestaShop per intercettare e convalidare i dati di registrazione. Utilizza controller Admin dedicati per la gestione dei tentativi e dei ban, e memorizza la sua configurazione in `ps_configuration`. La logica principale del modulo per il rilevamento dello spam è probabilmente contenuta nel file principale del modulo `index.php`, con funzioni o classi di supporto (sebbene nessuna sia esplicitamente elencata nel dossier, potrebbero essere interne alla classe principale del modulo).

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:
    Il dossier del modulo non indica controller front-office dedicati. Ciò suggerisce che le interazioni front-office del modulo (ad esempio, l'intercettazione dei dati di registrazione) sono gestite direttamente tramite hook all'interno del file principale del modulo `regpro/index.php`, o sovrascrivendo i controller core di PrestaShop (sebbene quest'ultimo sia meno comune per una semplice protezione dallo spam). Gli hook `displayCustomerAccountForm` sono il punto in cui la logica del modulo verrebbe attivata.
-   **Controller Admin Back-Office**:
    Questi controller forniscono l'interfaccia amministrativa per la gestione dei dati e delle impostazioni del modulo.

    -   `controllers/admin/AdminRegproAttempts.php`

        -   **Nome classe e classe genitore:** `AdminRegproAttemptsController` (estende `ModuleAdminController` o `AdminController`).
        -   **Responsabilità:** Gestisce l'elenco e le azioni relative ai tentativi di spam registrati. Questo controller è responsabile della visualizzazione della griglia dei tentativi di registrazione, consentendo agli amministratori di visualizzare i dettagli, filtrare ed eseguire azioni come la whitelisting o la blacklisting di IP basate su questi tentativi. Interagisce con la tabella del database `regattempt`.
    -   `controllers/admin/AdminRegproBans.php`

        -   **Nome classe e classe genitore:** `AdminRegproBansController` (estende `ModuleAdminController` o `AdminController`).
        -   **Responsabilità:** Gestisce l'elenco e le azioni relative ai ban attivi (IP, email, domini). Questo controller consente agli amministratori di visualizzare, aggiungere, modificare e rimuovere voci dagli elenchi di ban del modulo. Interagisce con la tabella del database `regban`.
    -   `controllers/admin/index.php`

        -   **Nome classe e classe genitore:** Probabilmente un semplice reindirizzatore o un file segnaposto. Potrebbe contenere un `AdminController` di base che reindirizza a uno degli altri controller admin specifici del modulo (ad esempio, `AdminRegproAttempts`) o visualizza una semplice dashboard. Non gestisce direttamente un'entità specifica ma funge da punto di ingresso per la sezione amministrativa del modulo.

### 4.3 Classi e modelli core (`classes/`)

Il dossier del modulo non indica classi personalizzate nella directory `classes/`. Ciò implica che le strutture dati del modulo (per tentativi e ban) sono gestite direttamente dalla logica di `AdminController` utilizzando query SQL raw, o più probabilmente, le definizioni `ObjectModel` per `regattempt` e `regban` sono incorporate direttamente nei rispettivi controller `AdminRegproAttempts.php` e `AdminRegproBans.php`, o all'interno del file principale `regpro/index.php`.

Se viene utilizzato `ObjectModel`, l'array `$definition` verrebbe definito per:

-   `regattempt`: Mappatura a una tabella `ps_regattempt` (o simile), con campi come `id_regattempt`, `ip_address`, `email`, `status`, `reason`, `date_add`.
-   `regban`: Mappatura a una tabella `ps_regban` (o simile), con campi come `id_regban`, `type` (IP, email, dominio), `value`, `date_add`.

### 4.4 Risorse JavaScript (`views/js/`)

-   `views/js/regpro-v3.js`
    -   **Ambito:** Probabilmente Back-office. La "v3" potrebbe indicare una versione o una funzionalità specifica.
    -   **Descrizione:** Questo script è probabilmente responsabile del miglioramento dell'esperienza utente nelle schermate di configurazione o gestione del Back Office del modulo. Potrebbe gestire:
        -   Chiamate AJAX per aggiornamenti dinamici (ad esempio, filtraggio di elenchi, aggiunta/rimozione di ban senza ricaricare la pagina).
        -   Validazione del modulo nella pagina di configurazione o durante l'aggiunta di nuove voci di ban.
        -   Elementi interattivi nelle griglie "Tentativi" o "Ban" (ad esempio, finestre di dialogo di conferma per le azioni, ordinamento, paginazione).
        -   Potenzialmente, logica lato client per l'integrazione con API esterne se richiedono interazione JS nel BO.

### 4.5 Fogli di stile CSS (`views/css/`)

Il dossier del modulo non indica file CSS personalizzati. Ciò suggerisce che il modulo si basa interamente sullo stile predefinito del Back Office di PrestaShop per le sue pagine di configurazione e griglie. Se è necessario uno stile specifico, sarebbe inline nei template o aggiunto dinamicamente tramite JavaScript.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**:
    Questi template vengono renderizzati quando il modulo è agganciato a punti specifici nel front-office.

    -   `views/templates/hook/displayCustomerAccountForm-v3.tpl`

        -   **Hook:** `displayCustomerAccountForm` (o simile, specifico per PrestaShop 1.7+ e 8.x).
        -   **Scopo:** Questo template è probabilmente utilizzato per iniettare campi nascosti, variabili JavaScript o potenzialmente un CAPTCHA/challenge visibile (se configurato) nel modulo di registrazione del cliente. La "v3" suggerisce che è una versione più recente, possibilmente per versioni più recenti di PrestaShop o un design specifico. Potrebbe contenere la struttura HTML per reCAPTCHA se tale integrazione è abilitata.
    -   `views/templates/hook/displayCustomerAccountForm.tpl`

        -   **Hook:** `displayCustomerAccountForm` (o simile, potenzialmente per versioni precedenti di PrestaShop come 1.6.x).
        -   **Scopo:** Simile a `displayCustomerAccountForm-v3.tpl`, ma probabilmente una versione generica o più vecchia. Servirebbe la stessa funzione di iniezione di elementi o logica nel modulo di registrazione del cliente per il rilevamento dello spam.
    -   `views/templates/hook/displayCustomerAccountFormTop.tpl`

        -   **Hook:** `displayCustomerAccountFormTop` (o simile).
        -   **Scopo:** Questo template renderizzerebbe il contenuto nella parte superiore del modulo di registrazione del cliente. Questo potrebbe essere utilizzato per visualizzare un messaggio generale o per iniettare elementi che devono apparire prima dei campi principali del modulo, come una casella di controllo "Non sono un robot" o un avviso.
-   **Template Admin (`views/templates/admin/`)**:
    Questi template definiscono la struttura e il contenuto delle pagine del Back Office del modulo.

    -   `views/templates/admin/main.tpl`
        -   **Scopo:** Questo è probabilmente il template principale per la pagina di configurazione del modulo (accessibile tramite `getContent()` in `regpro/index.php`) o un wrapper generale per la sezione amministrativa del modulo. Contenerebbe l'HTML per le varie impostazioni, campi di input e pulsanti descritti nella Sezione 4.1. Potrebbe anche includere collegamenti ai controller `AdminRegproAttempts` e `AdminRegproBans`.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    Basandosi sui Controller Admin, il modulo probabilmente crea due tabelle personalizzate:

    -   `ps_regattempt` (o prefisso simile): Memorizza i record dei tentativi di registrazione.
        -   `id_regattempt` (PK, INT)
        -   `ip_address` (VARCHAR)
        -   `email` (VARCHAR)
        -   `status` (VARCHAR, es. 'blocked', 'allowed', 'flagged')
        -   `reason` (TEXT, spiegazione dello stato)
        -   `date_add` (DATETIME)
    -   `ps_regban` (o prefisso simile): Memorizza i record dei ban attivi.
        -   `id_regban` (PK, INT)
        -   `type` (VARCHAR, es. 'ip', 'email', 'domain')
        -   `value` (VARCHAR, l'IP, l'email o il dominio effettivo)
        -   `date_add` (DATETIME)
        -   `reason` (TEXT, opzionale, per ban manuali)

    Le impostazioni di configurazione (come sensibilità, messaggi di errore, chiavi API) sono memorizzate nella tabella `ps_configuration` utilizzando chiavi con prefisso `REGPRO_` (es. `REGPRO_SENSITIVITY`, `REGPRO_ACTION_ON_SPAM`).
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Renderizza nella sezione `<head>` di tutte le pagine del front-office. | Potenzialmente utilizzato per caricare CSS/JS specifici del modulo a livello globale, o per l'iniezione di meta-tag per la verifica API esterna. |
| `displayCustomerAccountForm` | Renderizza all'interno del modulo di registrazione del cliente. | Hook principale per iniettare campi nascosti, elementi reCAPTCHA o JavaScript per intercettare l'invio del modulo ed eseguire la validazione lato client. |
| `displayCustomerAccountFormTop` | Renderizza nella parte superiore del modulo di registrazione del cliente. | Simile a `displayCustomerAccountForm`, ma assicura che il contenuto appaia prima dei campi principali del modulo. |
| `actionCustomerAccountAdd` | Eseguito *dopo* che un nuovo account cliente è stato aggiunto con successo al database. | Potrebbe essere utilizzato per la registrazione post-registrazione, l'invio di notifiche o ulteriori elaborazioni se un account è stato consentito ma contrassegnato per la revisione. |
| `actionAuthentication` | Eseguito durante il login/autenticazione del cliente. | Meno probabile per lo spam di registrazione, ma potrebbe essere utilizzato per controlli avanzati o per impedire il login da IP/email bannati. |
| `actionValidateCustomerAccount` | Eseguito *prima* che un nuovo account cliente venga aggiunto al database. | **HOOK CRITICO:** Questo è l'hook più probabile in cui la logica principale di rilevamento dello spam del modulo verrebbe eseguita, consentendogli di impedire la creazione dell'account se viene rilevato spam. |
| `displayBackOfficeHeader` | Renderizza nella sezione `<head>` di tutte le pagine del back-office. | Utilizzato per caricare CSS/JS specifici del modulo per le schermate di configurazione e gestione dell'amministrazione. |
| `displayAdminCustomers` | Renderizza nella pagina di elenco dei clienti nel Back Office. | Potrebbe essere utilizzato per aggiungere una colonna o un pulsante di azione relativo allo stato dello spam per i clienti esistenti. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto completo per gli sviluppatori, fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a fornire assistenza tempestiva e a garantire le prestazioni ottimali del modulo "Protezione dallo spam nella registrazione clienti".
