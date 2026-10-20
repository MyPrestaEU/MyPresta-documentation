---
title: "Invia email con voucher - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Invia email con voucher di MyPresta.eu."
sidebar:
  label: "Invia email con voucher - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Send email with voucher su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/send-email-with-voucher.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/send-email-with-voucher/)
>
> ---


# Invia email con voucher

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e sono solitamente disponibili su qualsiasi ambiente di hosting moderno.

## 2. Panoramica completa della configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Invia email con voucher)

Questa è la schermata di configurazione principale dove gestisci le impostazioni per l'invio delle tue email con voucher.

#### **Sezione Gestore Modelli Email**

Questa sezione è dove definisci il contenuto e l'aspetto delle email che conterranno i tuoi codici voucher.

-   **Cosa fa questa sezione:** Questo potente strumento ti consente di creare, modificare e gestire diversi modelli di email. Ogni modello può avere la propria riga dell'oggetto e il proprio contenuto del corpo, rendendo facile inviare vari tipi di offerte voucher (ad esempio, "Sconto di Benvenuto", "Regalo di Compleanno", "Offerta Carrello Abbandonato").
-   **Effetto della modifica delle impostazioni:**
    -   *Creazione di un nuovo modello:* Definisci un nuovo design di email e una riga dell'oggetto che potrai selezionare in seguito quando invii i voucher.
    -   *Modifica di un modello esistente:* Le modifiche all'oggetto o al contenuto si applicheranno a tutte le future email inviate utilizzando quel modello specifico.
    -   *Eliminazione di un modello:* Il modello non sarà più disponibile per la selezione.
-   **Flusso di lavoro consigliato:** Inizia creando alcuni modelli standard per le tue campagne voucher più comuni. Ad esempio, un modello "Benvenuto" per i nuovi clienti, un modello "Fedeltà" per gli acquirenti abituali e un modello "Offerta Speciale" per le promozioni.

#### **Sezione Motore Voucher**

Questa sezione è dove effettivamente generi e invii i codici voucher.

-   **Cosa fa questa sezione:** Questa è la funzionalità principale per creare regole di sconto (voucher) e inviarle a indirizzi email specifici. Puoi definire il tipo di sconto (percentuale, importo fisso), il valore, le condizioni (acquisto minimo, prodotti specifici) e il periodo di validità.
-   **Effetto della modifica delle impostazioni:**
    -   *Creazione di un nuovo voucher:* Viene creata una nuova regola di sconto nel tuo catalogo PrestaShop e viene generato un codice unico.
    -   *Invio di un voucher:* Un'email contenente il codice unico e il contenuto del modello selezionato viene inviata al/ai destinatario/i specificato/i.
    -   *Associazione con un cliente:* Il voucher può essere collegato all'account di un cliente specifico, il che significa che solo quel cliente può usarlo.
-   **Flusso di lavoro consigliato:**
    1.  Innanzitutto, crea o seleziona un modello di email appropriato dalla sezione "Gestore Modelli Email".
    2.  Quindi, utilizza il "Motore Voucher" per definire i parametri del tuo sconto (ad esempio, 10% di sconto, valido per 30 giorni, acquisto minimo $50).
    3.  Specifica l'indirizzo/gli indirizzi email del destinatario.
    4.  Scegli se associare il voucher a un account cliente esistente.
    5.  Clicca su "Invia" per generare e spedire il voucher personalizzato.

#### **Impostazioni specifiche all'interno della pagina di configurazione**

Sebbene l'interfaccia principale del modulo sia attraverso le sezioni "Gestore Modelli Email" e "Motore Voucher", ci sono chiavi di configurazione sottostanti che controllano il comportamento predefinito. Queste sono spesso gestite implicitamente dall'interfaccia del modulo, ma è bene comprenderne lo scopo.

-   **Titolo email**

    -   **Cosa fa questa impostazione:** Questa è la riga dell'oggetto predefinita per le email inviate con i voucher, se non sovrascritta da un modello specifico.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su "Il tuo sconto speciale":* Le email avranno questa riga dell'oggetto per impostazione predefinita.
        -   *Quando modificato in "Offerta esclusiva da [Nome del tuo negozio]":* Tutte le nuove email (senza un modello specifico che lo sovrascriva) utilizzeranno questo nuovo oggetto.
    -   **Valore consigliato:** Qualcosa di chiaro e invitante, come "Il tuo voucher esclusivo da [Nome del tuo negozio]".
    -   **Scenario/esempio per il commerciante:** Vuoi che tutte le tue email con voucher abbiano un messaggio di marca coerente nella riga dell'oggetto.
-   **File modello email**

    -   **Cosa fa questa impostazione:** Si riferisce al file modello email predefinito utilizzato per l'invio dei voucher. La sezione "Gestore Modelli Email" fornisce un modo più intuitivo per gestire e selezionare i modelli.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su `voucher_email.html`:* Il modulo utilizzerà questo file specifico per il corpo dell'email se non viene selezionato nessun altro modello.
    -   **Valore consigliato:** Utilizza l'interfaccia del "Gestore Modelli Email" per creare e selezionare i modelli, poiché è più flessibile e non richiede la manipolazione diretta dei file.
    -   **Scenario/esempio per il commerciante:** Hai un file modello email HTML personalizzato che desideri utilizzare come base per tutte le tue email con voucher.

#### **Altre chiavi di configurazione (Interne)**

Queste sono chiavi di configurazione interne di PrestaShop che il modulo potrebbe richiamare per le sue operazioni, ma che in genere non configurerai direttamente all'interno dell'interfaccia del modulo.

-   `PS_SHOP_EMAIL`: L'indirizzo email principale del tuo negozio. Utilizzato come email del mittente per i voucher.
-   `PS_SHOP_NAME`: Il nome del tuo negozio. Utilizzato negli oggetti o nei corpi delle email.
-   `PS_LANG_DEFAULT`: La lingua predefinita del tuo negozio.
-   `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Impostazione relativa alla lingua del dipendente nel back office.
-   `mypresta_updates`, `update_`, `updatev_`: Chiavi interne utilizzate dai moduli MyPresta.eu per i controlli degli aggiornamenti e la gestione delle versioni.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | **Gestore Modelli Email** | N/A (crea secondo necessità) | Crea e gestisci modelli di email personalizzati per le email con voucher. |
| Pagina di configurazione del modulo | **Motore Voucher** | N/A (crea secondo necessità) | Genera codici voucher unici con regole specifiche e inviali via email. |
| Pagina di configurazione del modulo | Titolo email | "Il tuo sconto speciale" (esempio) | Riga dell'oggetto predefinita per le email con voucher. |
| Pagina di configurazione del modulo | File modello email | `voucher_email.html` (esempio) | File HTML predefinito utilizzato per il contenuto dell'email. Utilizza il Gestore Modelli Email per un controllo migliore. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei clienti non ricevono le email con i voucher. Cosa devo controllare?**
R:

1.  **Controlla le impostazioni email del tuo negozio:** Vai su **Parametri avanzati > E-mail** nel tuo back office PrestaShop. Assicurati che la tua configurazione email (SMTP o PHP mail) sia corretta e prova a inviare un'email generica.
2.  **Cartelle spam:** Chiedi ai tuoi clienti di controllare le loro cartelle spam o posta indesiderata.
3.  **Contenuto del modello email:** Assicurati che i tuoi modelli email non siano troppo "spammy" (ad esempio, uso eccessivo di lettere maiuscole, troppi punti esclamativi).
4.  **Log del modulo:** Controlla se il modulo fornisce log o messaggi di errore durante il processo di invio. (Questo potrebbe richiedere l'assistenza di uno sviluppatore).

**D: Il codice voucher è stato inviato, ma il cliente dice che non funziona.**
R:

1.  **Controlla la validità del voucher:** Nel tuo back office PrestaShop, vai su **Catalogo > Sconti > Regole carrello**. Trova il codice voucher e controlla le sue date di validità, l'importo minimo, le restrizioni per il cliente e se è già stato utilizzato.
2.  **Associazione cliente:** Se il voucher è stato associato a un cliente specifico, assicurati che il cliente sia loggato nell'account corretto quando tenta di usarlo.
3.  **Errori di battitura:** Chiedi al cliente di ricontrollare eventuali errori di battitura durante l'inserimento del codice.

**D: Posso inviare lo stesso codice voucher a più clienti?**
R: Sì, puoi generare un singolo codice voucher e inviarlo a più indirizzi email. Tuttavia, per un migliore tracciamento e per prevenire l'abuso, è generalmente consigliabile generare codici unici per ogni destinatario, specialmente per le offerte personalizzate. Il "Motore Voucher" del modulo è progettato per generare codici unici.

**D: Come posso personalizzare l'aspetto dei modelli email?**
R: Utilizza la sezione "Gestore Modelli Email" all'interno della configurazione del modulo. Fornisce un'interfaccia per modificare l'oggetto e il corpo dei tuoi modelli email. Per una personalizzazione HTML/CSS avanzata, potresti dover modificare i file modello sottostanti (vedi Sezione 7 per gli sviluppatori).

**D: Il modulo non viene visualizzato correttamente dopo l'installazione, o vedo una pagina bianca.**
R:

1.  **Svuota la cache di Smarty:** Vai su **Parametri avanzati > Prestazioni** nel tuo back office PrestaShop. Imposta "Compilazione dei template" su "Ricompila i template se i file sono stati aggiornati" e "Cache" su "No". Quindi, clicca su "Svuota cache" in alto a destra. Dopo aver controllato, puoi ripristinare "Cache" su "Sì" e "Compilazione dei template" su "Non ricompilare mai..." per le prestazioni.
2.  **Controlla la versione di PHP:** Assicurati che la tua versione di PHP rientri nell'intervallo supportato (PHP 5.6 - 8.5).
3.  **Log degli errori del server:** Controlla i log degli errori PHP del tuo server per eventuali messaggi di errore specifici. Questo di solito richiede l'accesso al pannello di controllo del tuo hosting.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Invia email con voucher" segue un'architettura standard dei moduli PrestaShop, sfruttando principalmente la classe `Module` per la sua funzionalità principale e la configurazione. Integra JavaScript e CSS personalizzati per la sua interfaccia di back-office, in particolare per la gestione dei modelli di email e gli strumenti di generazione dei voucher. Il modulo non introduce controller front-office personalizzati o entità `ObjectModel` complesse, ma piuttosto interagisce con le classi `CartRule` (sconto) e `Mail` integrate di PrestaShop.

### 4.2 Controller (`controllers/`)

Questo modulo non contiene controller front-office o back-office personalizzati nella directory `controllers/`. Tutta la logica amministrativa e la configurazione sono gestite all'interno del metodo `getContent()` del file principale del modulo (`sendvouchers.php`).

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non definisce classi o modelli personalizzati all'interno di una directory `classes/`. Si basa sulle classi principali di PrestaShop, come `CartRule` per la gestione degli sconti e `Mail` per l'invio di email.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`sendvouchers/lib/emailTemplatesManager/js/emailTemplatesManager.js`**

    -   **Ambito:** Back-office (pagina di configurazione del modulo).
    -   **Responsabilità:** Gestisce gli elementi interattivi dell'interfaccia di creazione, modifica ed eliminazione dei modelli di email. Questo script probabilmente gestisce le chiamate AJAX per salvare/aggiornare i dati del modello, renderizza dinamicamente i moduli e gestisce le interazioni dell'utente all'interno della sezione "Gestore Modelli Email". Potrebbe utilizzare jQuery per la manipolazione del DOM e il binding degli eventi.
-   **`sendvouchers/lib/voucherengine/script.js`**

    -   **Ambito:** Back-office (pagina di configurazione del modulo).
    -   **Responsabilità:** Alimenta la sezione "Motore Voucher". Questo script è responsabile della gestione della generazione dei codici voucher, dell'impostazione delle regole di sconto (ad esempio, percentuale, importo fisso, condizioni), della selezione dei modelli di email e dell'avvio del processo di invio dei voucher. Probabilmente esegue la convalida lato client e le richieste AJAX al metodo `getContent()` del modulo per l'elaborazione lato server.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`sendvouchers/lib/emailTemplatesManager/css/emailTemplatesManager.css`**

    -   **Ambito:** Styling del modulo di amministrazione del back-office.
    -   **Responsabilità:** Fornisce lo styling per l'interfaccia del "Gestore Modelli Email", inclusi i moduli per la creazione/modifica dei modelli, i pulsanti e potenzialmente le visualizzazioni elenco.
    -   **Selettori di classe CSS chiave:** Gli sviluppatori possono ispezionare l'output HTML del modulo nel back office per identificare classi specifiche (ad esempio, `.email-template-form`, `.template-list-item`) per sovrascrivere nei loro temi di amministrazione personalizzati o tramite `override.css`.
-   **`sendvouchers/lib/voucherengine/ps16.css`**

    -   **Ambito:** Styling del modulo di amministrazione del back-office, specificamente per la compatibilità con PrestaShop 1.6.
    -   **Responsabilità:** Fornisce lo styling per la sezione "Motore Voucher", potenzialmente includendo layout di moduli, campi di input e pulsanti, con aggiustamenti per adattarsi al tema del back-office di PrestaShop 1.6. Questo file potrebbe anche essere caricato su versioni PS più recenti per la retrocompatibilità, ma il suo scopo principale è per PS 1.6.
    -   **Selettori di classe CSS chiave:** Similmente a `emailTemplatesManager.css`, gli sviluppatori dovrebbero ispezionare l'HTML generato per selettori specifici da mirare per le sovrascritture.

### 4.6 Struttura del template Smarty (`views/templates/`)

Tutti i template si trovano nella directory `sendvouchers/lib/emailTemplatesManager/views/`, indicando che sono utilizzati principalmente per il rendering dell'interfaccia di back-office del gestore dei template email.

-   **`sendvouchers/lib/emailTemplatesManager/views/buttonManager.tpl`**

    -   **Ambito:** Template di amministrazione.
    -   **Scopo:** Probabilmente renderizza pulsanti o controlli relativi alla gestione dei template email (ad esempio, "Aggiungi nuovo template", "Gestisci template").
-   **`sendvouchers/lib/emailTemplatesManager/views/createTemplateForm.tpl`**

    -   **Ambito:** Template di amministrazione.
    -   **Scopo:** Renderizza il modulo HTML per la creazione di un nuovo template email, inclusi i campi per l'oggetto, il corpo e potenzialmente la selezione della lingua.
-   **`sendvouchers/lib/emailTemplatesManager/views/editTemplateForm.tpl`**

    -   **Ambito:** Template di amministrazione.
    -   **Scopo:** Renderizza il modulo HTML per la modifica di un template email esistente, pre-popolando i campi con i dati del template corrente.
-   **`sendvouchers/lib/emailTemplatesManager/views/mainForm.tpl`**

    -   **Ambito:** Template di amministrazione.
    -   **Scopo:** Questo è probabilmente il template wrapper principale per la sezione "Gestore Modelli Email", che orchestra la visualizzazione dell'elenco dei template, del modulo di creazione e del modulo di modifica.
-   **`sendvouchers/lib/emailTemplatesManager/views/selectInput.tpl`**

    -   **Ambito:** Template di amministrazione.
    -   **Scopo:** Un frammento di template riutilizzabile per il rendering di un campo di input HTML `<select>`, possibilmente per la selezione della lingua o la scelta di un template esistente.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non crea esplicitamente tabelle SQL personalizzate durante `install()`.
    -   Memorizza le sue impostazioni di configurazione (come `sendvouchersTemplate`, `sendvouchersTitle`) nella tabella `ps_configuration` di PrestaShop.
    -   Interagisce con le tabelle principali `ps_cart_rule` e `ps_cart_rule_lang` di PrestaShop durante la creazione e la gestione dei voucher di sconto.
-   **Tabella degli hook registrati**:
    La funzionalità principale del modulo viene eseguita tramite il suo metodo `getContent()` nel back office. Sebbene la descrizione del modulo menzioni "Front-Office Hooks: Header, Columns, Product, or Footer", l'inventario del codice fornito non mostra file di template corrispondenti o metodi `hook` espliciti in `sendvouchers.php` che renderizzerebbero il contenuto in questi hook del front-office. Ciò suggerisce che se vengono registrati hook del front-office, sono per l'elaborazione interna (ad esempio, `actionFrontControllerSetMedia` per il caricamento delle risorse) o sono residui di versioni precedenti e non sono attivamente utilizzati per visualizzare contenuti visivi.

    La funzionalità principale di invio di email con voucher viene attivata dall'azione dell'utente nel back office, non dal caricamento delle pagine del front-office.

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayBackOfficeHeader` | Ad ogni caricamento della pagina del back-office. | Potenzialmente utilizzato per caricare CSS/JS specifici del modulo per la sua pagina di configurazione. |
| `moduleRoutes` | Durante l'inizializzazione del routing URL. | (Se implementato) Per definire URL amichevoli personalizzati per le pagine del modulo. (Non esplicitamente rilevato in questo modulo). |
| `actionAdminControllerSetMedia` | Quando viene caricato un controller di amministrazione. | Per aggiungere file JavaScript e CSS specifici del modulo alla pagina di configurazione del back-office. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e per scaricare le ultime versioni del modulo "Invia email con voucher", visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e compatibilità del modulo.
