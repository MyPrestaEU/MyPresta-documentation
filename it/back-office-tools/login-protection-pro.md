---
title: "Login protection pro - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Login protection pro di MyPresta.eu."
sidebar:
  label: "Login protection pro - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Login protection pro su MyPresta.eu](https://mypresta.eu/modules/administration-tools/login-protection-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/login-protection-pro/)
>
> ---


# Login protection pro

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale dove definisci le regole fondamentali per la protezione dell'accesso.

-   **Posizione del menu:** Back Office > Moduli > Gestione moduli > Login protection pro > Configura

#### Impostazioni e Opzioni:

1.  **Abilita protezione accesso:**

    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per il modulo. Attiva o disattiva l'intero sistema di protezione dell'accesso.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il modulo inizierà a monitorare i tentativi di accesso, applicando le regole che imposti di seguito.
        -   *Quando disabilitato:* Il modulo sarà inattivo e nessun tentativo di accesso verrà monitorato o bloccato. Il tuo negozio si affiderà alla sicurezza predefinita di PrestaShop, che non include la protezione contro la forza bruta.
    -   **Valore consigliato:** **SÌ**
    -   **Scenario / esempio per il commerciante:** Mantieni sempre abilitato per garantire che il tuo negozio sia protetto. Disabilita solo per debug specifici se istruito dal supporto.
2.  **Tentativi falliti massimi:**

    -   **Cosa fa questa impostazione:** Definisce il numero massimo di tentativi di accesso errati consentiti da un singolo indirizzo IP entro un periodo di tempo specifico (definito da "Finestra temporale tentativi") prima che quell'IP venga temporaneamente bloccato.
    -   **Effetto della modifica di questa impostazione:**
        -   *Impostando un numero inferiore (ad esempio, 3):* Rende la protezione più aggressiva, bloccando gli IP sospetti più velocemente. Questo potrebbe bloccare accidentalmente utenti legittimi che dimenticano la password più volte.
        -   *Impostando un numero superiore (ad esempio, 10):* Rende la protezione meno aggressiva, consentendo più tentativi falliti. Questo riduce la possibilità di bloccare utenti legittimi ma offre agli hacker più tentativi.
    -   **Valore consigliato:** **5**
    -   **Scenario / esempio per il commerciante:** Se noti che molti clienti legittimi vengono bloccati, potresti aumentarlo. Se vedi molti tentativi di forza bruta nei tuoi log, potresti diminuirlo. 5 è un buon equilibrio.
3.  **Finestra temporale tentativi (minuti):**

    -   **Cosa fa questa impostazione:** Specifica la durata (in minuti) durante la quale il conteggio dei "Tentativi falliti massimi" è attivo. Se un IP effettua `Tentativi falliti massimi` entro questa finestra, viene bloccato. Dopo questa finestra, il conteggio si resetta.
    -   **Effetto della modifica di questa impostazione:**
        -   *Impostando una finestra più breve (ad esempio, 5 minuti):* Un IP deve effettuare i `Tentativi falliti massimi` molto rapidamente per essere bloccato. Questo è utile per attacchi rapidi a forza bruta.
        -   *Impostando una finestra più lunga (ad esempio, 60 minuti):* Un IP può effettuare `Tentativi falliti massimi` per un periodo più lungo per essere bloccato. Questo cattura attacchi più lenti e distribuiti ma potrebbe anche bloccare utenti legittimi che tentano di accedere, si distraggono e riprovano più tardi.
    -   **Valore consigliato:** **15**
    -   **Scenario / esempio per il commerciante:** Una finestra di 15 minuti è solitamente sufficiente per catturare attacchi automatizzati senza penalizzare indebitamente un utente umano che potrebbe cercare di ricordare la propria password per alcuni minuti.
4.  **Durata del ban (minuti):**

    -   **Cosa fa questa impostazione:** Determina per quanto tempo un indirizzo IP rimane bloccato una volta superati i `Tentativi falliti massimi` entro la `Finestra temporale tentativi`.
    -   **Effetto della modifica di questa impostazione:**
        -   *Impostando una durata più breve (ad esempio, 30 minuti):* L'IP viene sbloccato prima. Questo è meno dirompente per gli utenti legittimi che potrebbero essere stati bloccati accidentalmente ma offre agli hacker un nuovo tentativo più rapido.
        -   *Impostando una durata più lunga (ad esempio, 1440 minuti = 24 ore):* L'IP rimane bloccato per un periodo significativo. Questo è molto efficace contro gli attacchi automatizzati ma può essere frustrante per gli utenti legittimi che vengono bloccati.
    -   **Valore consigliato:** **60** (1 ora)
    -   **Scenario / esempio per il commerciante:** Un ban di 60 minuti è solitamente sufficiente per scoraggiare i bot automatizzati, poiché probabilmente si sposteranno. Per un umano, fornisce un ragionevole periodo di raffreddamento.
5.  **Proteggi accesso amministratore:**

    -   **Cosa fa questa impostazione:** Questo interruttore applica specificamente le regole di protezione dell'accesso alla pagina di accesso del Back Office di PrestaShop (pannello di amministrazione).
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* La tua pagina di accesso amministratore è protetta. Se un attaccante tenta di indovinare la tua password amministratore troppe volte, il suo IP verrà bloccato.
        -   *Quando disabilitato:* Vengono monitorati solo i tentativi di accesso dei clienti. La tua pagina di accesso amministratore rimane vulnerabile agli attacchi a forza bruta.
    -   **Valore consigliato:** **SÌ**
    -   **Scenario / esempio per il commerciante:** È assolutamente fondamentale proteggere il tuo accesso amministratore, poiché l'accesso non autorizzato qui può compromettere l'intero negozio. Mantieni sempre abilitato.
6.  **Proteggi accesso cliente:**

    -   **Cosa fa questa impostazione:** Questo interruttore applica specificamente le regole di protezione dell'accesso alla pagina di accesso del cliente (front office).
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I tentativi di accesso dei clienti sono protetti. Se un attaccante tenta di indovinare le password dei clienti, il suo IP verrà bloccato.
        -   *Quando disabilitato:* Vengono monitorati solo i tentativi di accesso amministratore. Gli account dei clienti rimangono vulnerabili agli attacchi a forza bruta.
    -   **Valore consigliato:** **SÌ**
    -   **Scenario / esempio per il commerciante:** Proteggere gli account dei clienti è vitale per la sicurezza dei dati e per mantenere la fiducia dei clienti. Mantieni sempre abilitato.

#### Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Abilita protezione accesso | SÌ | Interruttore principale per la funzionalità del modulo. **Sempre SÌ.** |
| Configurazione modulo | Tentativi falliti massimi | 5 | Numero di accessi errati prima che un IP venga bloccato. |
| Configurazione modulo | Finestra temporale tentativi (minuti) | 15 | Durata su cui vengono contati i tentativi falliti. |
| Configurazione modulo | Durata del ban (minuti) | 60 | Per quanto tempo un IP bloccato rimane bannato. |
| Configurazione modulo | Proteggi accesso amministratore | SÌ | Applica la protezione all'accesso del Back Office. **Sempre SÌ.** |
| Configurazione modulo | Proteggi accesso cliente | SÌ | Applica la protezione all'accesso del cliente del Front Office. **Sempre SÌ.** |

### 2.2 Schermate di amministrazione dedicate e viste del controller

Il modulo fornisce due schermate dedicate nel tuo Back Office di PrestaShop per gestire e rivedere i tentativi di accesso e i ban.

#### 2.2.1 AdminLproAttemptsController: Registro tentativi di accesso

Questa schermata ti permette di visualizzare un registro dettagliato di tutti i tentativi di accesso falliti registrati dal modulo.

-   **Nome schermata e posizione nel menu:** Back Office > Moduli > Login Protection Pro > **Tentativi di accesso** (o simile, a seconda della versione di PrestaShop e della personalizzazione del menu).
-   **Azioni e impostazioni disponibili:**
    -   **Tabella di elenco:** Vedrai una tabella che mostra:
        -   **Indirizzo IP:** L'indirizzo IP da cui ha avuto origine il tentativo fallito.
        -   **Ora del tentativo:** La data e l'ora esatte del tentativo fallito.
        -   **Tipo di accesso:** Se si trattava di un tentativo di accesso 'Amministratore' o 'Cliente'.
        -   **Nome utente/Email:** Il nome utente o l'indirizzo email che è stato tentato.
        -   **Stato:** Indica se il tentativo ha portato a un ban o è stato solo un tentativo fallito.
    -   **Filtro e ordinamento:** Puoi tipicamente filtrare per indirizzo IP, tipo di accesso o intervallo di date per trovare tentativi specifici.
    -   **Nessuna azione diretta:** Questa schermata è principalmente per il monitoraggio e la revisione. Non puoi bannare o sbloccare direttamente gli IP da qui, ma ti aiuta a identificare schemi sospetti.
-   **Effetto delle modifiche:** La visualizzazione di questo registro ti aiuta a comprendere la frequenza e la fonte degli attacchi. Se noti un particolare indirizzo IP che effettua molti tentativi, puoi aggiungerlo manualmente all'elenco dei ban tramite la schermata "IP bannati".
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Controlla regolarmente questo registro, specialmente se sospetti un attacco o se i clienti segnalano problemi di accesso. Cerca schemi di tentativi falliti ripetuti dallo stesso IP o intervallo di IP.

#### 2.2.2 AdminLproBansController: Gestione IP bannati

Questa schermata ti permette di visualizzare, aggiungere e rimuovere indirizzi IP dall'elenco dei ban del modulo.

-   **Nome schermata e posizione nel menu:** Back Office > Moduli > Login Protection Pro > **IP bannati** (o simile, a seconda della versione di PrestaShop e della personalizzazione del menu).
-   **Azioni e impostazioni disponibili:**
    -   **Tabella di elenco:** Mostra tutti gli indirizzi IP attualmente bannati, inclusi:
        -   **Indirizzo IP:** L'IP bloccato.
        -   **Motivo del ban:** (Se applicabile, ad esempio, "Ban automatico a causa di tentativi falliti").
        -   **Ora di inizio del ban:** Quando il ban è stato avviato.
        -   **Ora di fine del ban:** Quando il ban è previsto per scadere (se temporaneo).
        -   **Azioni:** Di solito include un'opzione per "Eliminare" o "Sbloccare" un IP specifico.
    -   **Pulsante "Aggiungi nuovo IP":** Ti permette di aggiungere manualmente un indirizzo IP all'elenco dei ban. Questo è utile se identifichi un IP malevolo dai log del tuo server o dalla schermata "Tentativi di accesso" che non è ancora stato bannato automaticamente.
        -   Quando aggiungi, potresti essere in grado di specificare l'IP, un motivo e un tempo di scadenza opzionale per il ban.
-   **Effetto delle modifiche:**
    -   *Aggiunta di un IP:* Blocca immediatamente tutti i tentativi di accesso da quell'indirizzo IP per la durata specificata (o permanentemente se non è impostata alcuna durata).
    -   *Rimozione di un IP:* Sblocca l'indirizzo IP, consentendo nuovamente i tentativi di accesso da esso. Usa questa opzione con cautela, assicurandoti di non sbloccare un attaccante noto.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    -   Rivedi periodicamente questo elenco.
    -   Se un cliente legittimo segnala di non riuscire ad accedere e hai confermato il suo indirizzo IP (ad esempio, chiedendogli di visitare un sito "qual è il mio IP"), potresti sbloccare temporaneamente il suo IP qui.
    -   Se identifichi una minaccia persistente, puoi aggiungere manualmente il suo IP per assicurarti che rimanga bloccato.

#### 2.2.3 index.php (lpro/controllers/admin/index.php)

Questo file serve tipicamente come segnaposto o reindirizzatore all'interno della directory dei controller di amministrazione. In PrestaShop, i file `index.php` all'interno delle directory dei controller spesso impediscono la visualizzazione diretta della directory o fungono da punto di ingresso predefinito se non viene richiesto un controller specifico. Non rappresenta una schermata configurabile o un'entità gestita di per sé.

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei clienti si lamentano di non riuscire ad accedere, ma stanno usando la password corretta. Cosa devo fare?**
R1: Questo è probabilmente dovuto al modulo che blocca il loro indirizzo IP dopo troppi tentativi falliti (forse da una sessione precedente o da una rete condivisa).
1.  Chiedi al cliente il suo attuale indirizzo IP (può trovarlo cercando "qual è il mio IP" su Google).
2.  Vai su **Back Office > Moduli > Login Protection Pro > IP bannati**.
3.  Cerca il suo indirizzo IP nell'elenco.
4.  Se trovato, elimina/sblocca il suo IP.
5.  Consiglia al cliente di provare ad accedere di nuovo. Potresti anche suggerirgli di reimpostare la password.

**D2: Sono bloccato fuori dal mio pannello di amministrazione! Come posso riottenere l'accesso?**
R2: Questo può accadere se hai effettuato troppi tentativi falliti.
1.  Se hai accesso FTP al tuo negozio, puoi disabilitare temporaneamente il modulo. Vai su `modules/lpro/` e rinomina il file `index.php` (ad esempio, in `index.php.bak`). Questo disabiliterà il modulo.
2.  Accedi al tuo pannello di amministrazione.
3.  Vai su **Moduli > Gestione moduli**, trova "Login protection pro" e clicca su "Configura".
4.  Vai su **IP bannati** e rimuovi il tuo indirizzo IP dall'elenco.
5.  Rinomina `index.php.bak` in `index.php` nella directory `modules/lpro/`.
6.  Riabilita il modulo se lo hai disabilitato nel gestore moduli.
7.  Regola le impostazioni `Tentativi falliti massimi` o `Durata del ban` se ti trovi spesso bloccato.

**D3: Il modulo non sembra bloccare alcun IP, anche dopo molti tentativi falliti. Cosa potrebbe esserci di sbagliato?**
R3:
1.  **Controlla "Abilita protezione accesso":** Assicurati che l'interruttore principale nella configurazione del modulo sia impostato su **SÌ**.
2.  **Controlla "Proteggi accesso amministratore" / "Proteggi accesso cliente":** Assicurati che la protezione pertinente (amministratore o cliente) sia abilitata.
3.  **Rivedi le impostazioni:** Verifica che `Tentativi falliti massimi`, `Finestra temporale tentativi` e `Durata del ban` siano impostati su valori ragionevoli. Se la `Finestra temporale tentativi` è troppo breve, o `Tentativi falliti massimi` è troppo alto, potrebbe essere necessario un attacco molto aggressivo per attivare un ban.
4.  **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache". A volte, le impostazioni del modulo non vengono applicate immediatamente a causa della cache.
5.  **Controlla i log del server:** I log di accesso del server del tuo provider di hosting potrebbero mostrare se il modulo sta riscontrando errori PHP.

**D4: Questo modulo rallenterà il mio negozio?**
R4: Il modulo è progettato per essere leggero. Esegue controlli solo durante i tentativi di accesso, che sono relativamente poco frequenti rispetto alle visualizzazioni di pagina. L'impatto sulle prestazioni dovrebbe essere trascurabile. Se noti un rallentamento, assicurati che la tua installazione di PrestaShop e il server soddisfino i requisiti minimi.

**D5: Come traduco i messaggi del modulo in altre lingue?**
R5: Sebbene questo modulo funzioni principalmente in background, eventuali messaggi potenziali nel front-office (come "Troppi tentativi falliti") o etichette nel back-office possono essere tradotti:
1.  Vai su **Internazionale > Traduzioni** nel tuo Back Office di PrestaShop.
2.  Seleziona "Traduzioni dei moduli installati".
3.  Scegli il tuo tema.
4.  Seleziona la lingua che desideri tradurre.
5.  Trova il modulo "Login protection pro" e traduci le stringhe di testo pertinenti.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce un'analisi approfondita della struttura tecnica del modulo "Login protection pro" per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo `Login protection pro` segue un'architettura standard per i moduli PrestaShop, sfruttando principalmente i Controller Admin per la sua interfaccia di gestione e gli hook per la sua funzionalità principale. Non introduce controller front-office complessi o classi `ObjectModel` personalizzate, affidandosi invece alla classe `Configuration` di PrestaShop per le impostazioni e all'interazione diretta con il database per la registrazione dei tentativi e la gestione dei ban. La logica del modulo per il rilevamento e il blocco dei tentativi viene iniettata tramite gli hook di PrestaShop, in particolare attorno al processo di autenticazione.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

Il modulo **non** contiene alcun controller front-office dedicato. Tutta la logica relativa al front-office (monitoraggio dei tentativi di accesso dei clienti) è gestita direttamente all'interno del file principale del modulo (`lpro/index.php`) agganciandosi al processo di autenticazione di PrestaShop.

#### Controller Admin Back-Office

Il modulo fornisce controller admin dedicati per la gestione dei tentativi di accesso e dei ban.

-   **`controllers/admin/AdminLproAttempts.php`**

    -   **Nome classe:** `AdminLproAttemptsController` (estende `ModuleAdminController`)
    -   **Responsabilità:** Questo controller è responsabile della visualizzazione di un elenco di tutti i tentativi di accesso falliti registrati. Fornisce una vista a griglia di sola lettura dei dati `lattempt`, consentendo agli amministratori di monitorare attività sospette. Tipicamente utilizza `HelperList` per il rendering della tabella.
    -   **Entità gestita:** `lattempt` (rappresenta un record di tentativo di accesso fallito).
    -   **Nome scheda:** Tentativi di accesso (visibile sotto la voce di menu principale del modulo).
-   **`controllers/admin/AdminLproBans.php`**

    -   **Nome classe:** `AdminLproBansController` (estende `ModuleAdminController`)
    -   **Responsabilità:** Questo controller gestisce l'elenco degli indirizzi IP bannati. Fornisce una vista a griglia dei dati `lban` e consente agli amministratori di aggiungere nuovi ban, modificare quelli esistenti ed eliminare (sbloccare) gli IP. Probabilmente utilizza `HelperList` per la tabella e `HelperForm` per i moduli di aggiunta/modifica.
    -   **Entità gestita:** `lban` (rappresenta un record di indirizzo IP bannato).
    -   **Nome scheda:** IP bannati (visibile sotto la voce di menu principale del modulo).
-   **`controllers/admin/index.php`**

    -   **Percorso file esatto:** `lpro/controllers/admin/index.php`
    -   **Nome classe e classe genitore:** Non è un file di classe.
    -   **Responsabilità:** Questo è un file segnaposto standard di PrestaShop. Il suo scopo principale è impedire la visualizzazione della directory se la configurazione del server web lo consente, e a volte può contenere un semplice reindirizzamento o un controllo di sicurezza. Non contiene alcuna logica funzionale per il modulo stesso.

### 4.3 Classi e Modelli Core (`classes/`)

Il modulo **non** contiene classi personalizzate nella directory `classes/`. Probabilmente gestisce le interazioni con il database direttamente all'interno del file principale del modulo (`lpro/index.php`) o dei suoi controller admin, utilizzando metodi standard di query del database di PrestaShop. Ciò implica che le entità `lattempt` e `lban` sono gestite senza classi `ObjectModel` dedicate, affidandosi a SQL diretto o chiamate a `Db::getInstance()`.

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo **non** contiene file JavaScript personalizzati. Ciò suggerisce che le sue interfacce di configurazione e gestione si basano interamente sulle librerie e sui comportamenti JavaScript predefiniti di PrestaShop (ad esempio, per l'invio di moduli, il filtraggio delle tabelle).

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo **non** contiene file CSS personalizzati. Ciò indica che le sue interfacce di Back Office (configurazione, log dei tentativi, elenchi di ban) ereditano lo stile direttamente dal tema del Back Office di PrestaShop, garantendo un aspetto coerente senza introdurre elementi visivi personalizzati.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template Admin (`views/templates/admin/`)**:
    -   **`lpro/views/templates/admin/main.tpl`**:
        -   **Scopo:** Questo template è probabilmente utilizzato per la pagina di configurazione principale del modulo, renderizzata dal metodo `getContent()` in `lpro/index.php`. Contiene la struttura HTML per le impostazioni descritte nella sezione 4.1 (Abilita protezione accesso, Tentativi falliti massimi, ecc.). Tipicamente includerebbe elementi di modulo (interruttori, campi di input) e potenzialmente collegamenti ai controller `AdminLproAttempts` e `AdminLproBans`.

### 4.7 Schema del database e Mappa degli hook

#### Tabelle del database

Il modulo crea tabelle di database personalizzate durante il suo metodo `install()` (definito in `lpro/index.php`).

-   **`ps_lpro_attempt`**:
    -   **Scopo:** Memorizza i record di tutti i tentativi di accesso falliti.
    -   **Campi probabili:**
        -   `id_lpro_attempt` (Chiave primaria)
        -   `ip_address` (VARCHAR): L'indirizzo IP del tentativo fallito.
        -   `attempt_time` (DATETIME): Timestamp del tentativo.
        -   `login_type` (VARCHAR): 'admin' o 'customer'.
        -   `username` (VARCHAR): Il nome utente/email tentato.
        -   `is_banned` (TINYINT): Flag che indica se questo tentativo ha portato a un ban.
-   **`ps_lpro_ban`**:
    -   **Scopo:** Memorizza i record dei ban IP attualmente attivi.
    -   **Campi probabili:**
        -   `id_lpro_ban` (Chiave primaria)
        -   `ip_address` (VARCHAR): L'indirizzo IP bannato.
        -   `ban_start_time` (DATETIME): Quando è iniziato il ban.
        -   `ban_end_time` (DATETIME): Quando il ban è previsto per scadere (NULL per i ban permanenti).
        -   `reason` (TEXT): Motivo opzionale del ban.
        -   `is_permanent` (TINYINT): Flag per i ban permanenti.

#### Tabella degli hook registrati

Il modulo registra gli hook per intercettare i tentativi di accesso e applicare la sua logica di protezione.

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionAuthentication` | Dopo che un cliente tenta di accedere (front office). | Controlla se il tentativo di accesso del cliente è riuscito o fallito. Se fallito, registra il tentativo e controlla le condizioni di ban. |
| `actionAdminLoginController` | Dopo che un amministratore tenta di accedere (back office). | Controlla se il tentativo di accesso dell'amministratore è riuscito o fallito. Se fallito, registra il tentativo e controlla le condizioni di ban. |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Potenzialmente utilizzato per includere CSS/JS (anche se nessuno è presente) o per controlli precoci, anche se meno probabile per la logica principale. Più spesso per l'inizializzazione generale del modulo. |
| `displayRightColumn` | Nella colonna destra delle pagine del front-office. | Non direttamente rilevante per la logica di sicurezza. Se utilizzato, sarebbe per visualizzare un messaggio o un blocco, il che è improbabile per questo modulo. |
| `displayLeftColumn` | Nella colonna sinistra delle pagine del front-office. | Come `displayRightColumn`. |
| `displayFooter` | Nel piè di pagina di ogni pagina del front-office. | Non direttamente rilevante per la logica di sicurezza. |
| `displayProductExtraContent` | Nella pagina del prodotto, all'interno della sezione "contenuto extra". | Non direttamente rilevante per la logica di sicurezza. |

**Nota sugli Hook:** La logica principale per il rilevamento e il blocco dei tentativi risiederà principalmente all'interno degli hook `actionAuthentication` e `actionAdminLoginController`. Altri hook `display` sono probabilmente registrati per impostazione predefinita ma non utilizzati attivamente per la funzionalità di sicurezza principale del modulo.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, accedi al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo al modulo "Login protection pro".
