---
title: "Invia una copia delle email (BCC) - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Invia una copia delle email (BCC) di MyPresta.eu."
sidebar:
  label: "Invia una copia delle email (BCC)"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Send a copy of emails (BCC) su MyPresta.eu](https://mypresta.eu/modules/administration-tools/send-a-copy-of-emails-bcc.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/send-a-copy-of-emails-bcc/)
>
> ---


# Invia una copia delle email (BCC)

## 1. Requisiti e Compatibilità
- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Non sono solitamente necessarie configurazioni speciali del server.

## 2. Panoramica completa della configurazione (ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)
Dopo l'installazione, cliccando su "Configura" verrai indirizzato alla pagina di configurazione principale del modulo.

#### **Aggiornamenti MyPresta.eu e Controllo Versione**
Nella parte superiore della pagina di configurazione, vedrai tipicamente le impostazioni relative agli aggiornamenti di MyPresta.eu. Queste sono standard per i moduli MyPresta.eu e ti aiutano a mantenere il tuo modulo aggiornato.

-   **Cosa fa questa impostazione:** Questi campi (spesso etichettati `mypresta_updates`, `update_`, `updatev_`) sono utilizzati dal modulo per verificare la disponibilità di nuove versioni da MyPresta.eu e informarti se è necessario un aggiornamento. Sono solitamente precompilati o gestiti automaticamente.
-   **Effetto della modifica di questa impostazione:**
    -   *Se abilitato/attivo:* Il modulo può controllare periodicamente gli aggiornamenti, notificandoti nel back office di PrestaShop se è disponibile una nuova versione.
    -   *Se disabilitato/inattivo:* Potresti non ricevere notifiche automatiche sugli aggiornamenti del modulo, richiedendo controlli manuali.
-   **Valore consigliato:** Lascia queste impostazioni così come sono, solitamente abilitate o gestite automaticamente, per assicurarti di essere sempre informato sulle ultime versioni del modulo e sulle correzioni di sicurezza.
-   **Scenario / esempio del commerciante:** Vuoi essere avvisato quando viene rilasciata una nuova versione del modulo che include nuove funzionalità o correzioni di bug, quindi mantieni attivi questi controlli di aggiornamento.

#### **Impostazioni principali del modulo**
Sotto le impostazioni di aggiornamento, troverai le opzioni di configurazione principali per la funzionalità email BCC.

-   **Indirizzo email per BCC:**
    -   **Cosa fa questa impostazione:** Questa è l'impostazione più cruciale. Definisce l'indirizzo email a cui verranno inviate tutte le copie BCC selezionate.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su un indirizzo email valido:* Tutte le email selezionate nell'elenco sottostante avranno una copia conoscenza nascosta inviata a questo indirizzo.
        -   *Quando lasciato vuoto o impostato su un indirizzo non valido:* Non verranno inviate copie BCC, anche se le email sono selezionate nell'elenco.
    -   **Valore consigliato:** Un indirizzo email dedicato per l'archiviazione (ad es. `archive@tuonegozio.com`, `supporto@tuonegozio.com`, o la tua email amministrativa personale).
    -   **Scenario / esempio del commerciante:** Vuoi che tutte le conferme d'ordine vengano copiate nella casella di posta del tuo team di assistenza clienti, `supporto@tuonegozio.com`, quindi inserisci questo indirizzo qui.

-   **Seleziona email da BCC:**
    -   **Cosa fa questa impostazione:** Questa sezione presenta un elenco di tutti i modelli di email (tipi di email) che il tuo negozio PrestaShop può inviare. Puoi selezionare quali tipi specifici di email vuoi inviare in BCC.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando un tipo di email è selezionato:* Una copia BCC di quel tipo specifico di email verrà inviata all'"Indirizzo email per BCC" ogni volta che il tuo negozio la invia.
        -   *Quando un tipo di email non è selezionato:* Non verrà inviata alcuna copia BCC per quel tipo specifico di email.
    -   **Valore consigliato:** Seleziona solo i tipi di email che sono critici per la tua tenuta dei registri o le tue esigenze operative. Un eccessivo invio in BCC può intasare una casella di posta. Le scelte comuni includono:
        -   `order_conf` (Conferma d'ordine)
        -   `shipped` (Ordine spedito)
        -   `contact_form` (Invio modulo di contatto)
        -   `password` (Reimpostazione password)
        -   `account` (Creazione nuovo account)
    -   **Scenario / esempio del commerciante:** Vuoi tenere un registro di tutti i nuovi ordini e le richieste dei clienti. Selezioneresti `order_conf` e `contact_form` dall'elenco.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### **Gestione BCC email (Back Office > Parametri Avanzati > BCC email)**
Questo modulo crea una voce di menu dedicata nel tuo back office di PrestaShop sotto "Parametri Avanzati" (o simile, a seconda della versione di PrestaShop) denominata "BCC email". Questa schermata è gestita da `AdminMailBccController`.

-   **Nome schermata e posizione menu:** **Parametri Avanzati > BCC email**
-   **Azioni e impostazioni disponibili:** Questa schermata presenta tipicamente una griglia (elenco) di tutti i tipi di email che hai configurato per essere inviati in BCC, insieme all'indirizzo email BCC. Funge da interfaccia di riepilogo e gestione per le tue impostazioni BCC.
    -   Potresti vedere colonne come:
        -   **ID:** Identificatore interno per la regola BCC.
        -   **Modello email:** Il nome del modello di email (ad es. `order_conf`).
        -   **Email BCC:** L'indirizzo email a cui viene inviata la copia.
        -   **Abilitato:** Un interruttore per abilitare o disabilitare rapidamente il BCC per quel tipo specifico di email.
        -   **Azioni:** Pulsanti per modificare o eliminare la regola BCC (anche se spesso la pagina di configurazione principale del modulo viene utilizzata per la selezione in blocco).
-   **Effetto delle modifiche:**
    -   *Abilitazione/Disabilitazione di una regola:* Controlla direttamente se una copia BCC viene inviata per quel tipo specifico di email.
    -   *Modifica di una regola:* Consente di modificare l'indirizzo email BCC per un tipo specifico di email (se il modulo supporta indirizzi BCC per email, altrimenti rifletterà l'impostazione globale).
    -   *Eliminazione di una regola:* Rimuove l'impostazione BCC per quel tipo di email.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Utilizza questa schermata per rivedere rapidamente quali email vengono inviate in BCC e per apportare rapide modifiche di abilitazione/disabilitazione senza tornare alla configurazione principale del modulo. Per aggiungere nuovi tipi di email o modificare l'indirizzo BCC principale, la pagina di configurazione principale del modulo è solitamente più efficiente.

#### **index.php (bccmail/controllers/admin/index.php)**
Questo file è una pratica standard di PrestaShop per la protezione delle directory dei controller admin e tipicamente non presenta una schermata o opzioni di configurazione direttamente all'utente. Di solito contiene un semplice `header('Location: ../../index.php?controller=AdminHome');` o simile per reindirizzare l'accesso non autorizzato, impedendo la navigazione diretta della directory. I commercianti non interagiranno con questo file.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
|---|---|---|---|
| **Pagina di configurazione del modulo** | Aggiornamenti MyPresta.eu | Abilitato | Ti tiene informato sugli aggiornamenti del modulo. |
| | **Indirizzo email per BCC** | La tua email amministrativa / `archive@tuonegozio.com` | L'email di destinazione per tutte le copie BCC. Critico per l'archiviazione. |
| | **Seleziona email da BCC** | `order_conf`, `contact_form`, `shipped` | Scegli quali tipi specifici di email copiare. Previene l'intasamento della casella di posta. |
| **Parametri Avanzati > BCC email** | Elenco modelli email | Varia in base alla selezione | Panoramica e attivazione rapida per i tipi di email BCC configurati. |
| | Interruttore Abilitato | Abilitato | Attiva/disattiva rapidamente il BCC per un tipo specifico di email. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho configurato il modulo, ma non ricevo email BCC. Cosa dovrei controllare?**
R:
1.  **Ricontrolla l'indirizzo email BCC:** Vai su **Moduli > Gestione moduli > Configura** per "Invia una copia delle email (BCC)" e assicurati che l'"Indirizzo email per BCC" sia scritto correttamente e sia valido.
2.  **Verifica i tipi di email selezionati:** Assicurati che i tipi specifici di email che ti aspetti vengano copiati (ad es. `order_conf`) siano effettivamente selezionati nella configurazione del modulo.
3.  **Controlla la cartella spam:** Le email BCC potrebbero finire nella cartella spam o posta indesiderata della casella di posta del destinatario BCC.
4.  **Impostazioni email di PrestaShop:** Assicurati che le impostazioni email generali del tuo negozio PrestaShop (**Parametri Avanzati > E-mail**) siano configurate correttamente e che il tuo negozio possa inviare email in generale. Prova a inviare un'email di prova da PrestaShop.
5.  **Svuota la cache:** A volte, la cache di PrestaShop può impedire che le modifiche abbiano effetto immediatamente. Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti).

**D: Posso inviare copie BCC a più indirizzi email?**
R: La configurazione principale del modulo consente un solo indirizzo email BCC principale. Se hai bisogno di inviare copie a più indirizzi, hai due opzioni:
1.  Imposta l'indirizzo email BCC su una lista di distribuzione o un indirizzo email di gruppo che inoltra a più destinatari.
2.  Configura una regola email nella casella di posta del destinatario BCC per inoltrare automaticamente le copie ad altri indirizzi in base al mittente o all'oggetto.

**D: Questo modulo rallenterà il mio negozio o l'invio di email?**
R: L'impatto sulle prestazioni è generalmente trascurabile. L'invio di una copia BCC aggiuntiva è un'operazione molto piccola per il server di posta. Il modulo utilizza il meccanismo di invio email standard di PrestaShop, aggiungendo semplicemente un destinatario extra.

**D: Il mio tema personalizzato ha modelli di email personalizzati. Questo modulo funzionerà comunque?**
R: Sì, il modulo si aggancia alla classe `Mail` principale di PrestaShop, che è responsabile dell'invio di tutte le email, indipendentemente dal fatto che utilizzino modelli predefiniti o personalizzati. Finché PrestaShop invia l'email, questo modulo può inviarla in BCC.

**D: Come traduco l'interfaccia del modulo in un'altra lingua?**
R: Vai su **Internazionale > Traduzioni** nel tuo back office di PrestaShop. Seleziona "Traduzioni dei moduli installati", scegli il tuo tema e poi seleziona "Invia una copia delle email (BCC)". Potrai quindi tradurre qualsiasi stringa visualizzata dal modulo nel back office.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

Questa sezione fornisce un'analisi approfondita dell'implementazione tecnica del modulo "Invia una copia delle email (BCC)" per sviluppatori e webmaster.

### 4.1 Panoramica dell'Architettura
Il modulo "Invia una copia delle email (BCC)" (`bccmail`) funziona principalmente sovrascrivendo la classe `Mail` principale di PrestaShop. Questa è una tecnica comune e potente in PrestaShop per modificare il comportamento del core senza modificare direttamente i file del core. Sovrascrivendo `Mail.php`, il modulo intercetta tutte le operazioni di invio email e inietta la funzionalità BCC in base alla sua configurazione. Segue una struttura standard del modulo PrestaShop con un file di modulo principale, controller admin per la configurazione e una classe di override.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Questo modulo non ha controller front-office dedicati poiché la sua funzionalità è interamente back-office e lato server.

-   **Controller Admin Back-Office**:
    *   `bccmail/controllers/admin/AdminMailBcc.php`
        *   **Nome classe e classe genitore:** `AdminMailBccController` estende `ModuleAdminController`.
        *   **Nome tab e entità gestita:** Questo controller gestisce la tab "BCC email" sotto "Parametri Avanzati". È responsabile della visualizzazione e della gestione dell'elenco dei tipi di email BCC configurati. Probabilmente utilizza `HelperList` o `HelperView` di PrestaShop per renderizzare una griglia di oggetti `MailBcc` (o una rappresentazione della configurazione del modulo).
        *   **Responsabilità:** Gestisce la visualizzazione del riepilogo della configurazione BCC, consentendo potenzialmente l'attivazione/disattivazione o l'eliminazione di singole regole. Interagisce con i dati di configurazione del modulo (probabilmente archiviati in `ps_configuration` o in una tabella personalizzata se sono necessari dati più complessi per regola BCC).
    *   `bccmail/controllers/admin/index.php`
        *   **Nome classe e classe genitore:** Non è una classe, ma un file di sicurezza.
        *   **Responsabilità:** Questo file è una misura di sicurezza standard di PrestaShop. Tipicamente contiene `header('Location: ../../index.php?controller=AdminHome');` o simile per impedire l'elenco diretto delle directory e l'accesso non autorizzato alla directory `controllers/admin`. Non fornisce alcuna logica funzionale per il modulo stesso.

### 4.3 Classi e Modelli Core (`classes/`)

-   `bccmail/override/classes/Mail.php`
    *   **Con quale tabella del database interagisce:** Interagisce indirettamente con `ps_configuration` per recuperare le impostazioni del modulo (indirizzo email BCC e modelli di email selezionati).
    *   **Se estende `ObjectModel`:** No, sovrascrive la classe `Mail` principale.
    *   **Metodi pubblici chiave e logica di business incapsulata:**
        *   Questo file contiene la logica principale per intercettare l'invio di email. Sovrascrive il metodo `send()` (o un metodo simile) della classe `Mail` originale.
        *   All'interno del metodo `send()` sovrascritto, farà quanto segue:
            1.  Recuperare la configurazione del modulo: l'indirizzo email BCC globale e l'elenco dei modelli di email selezionati per BCC.
            2.  Verificare se l'email corrente in fase di invio (identificata dal nome del suo modello, ad es. `order_conf`) è nell'elenco dei modelli BCC selezionati.
            3.  Se viene trovata una corrispondenza, modifica le intestazioni o i parametri dell'email per includere l'indirizzo email BCC configurato prima di chiamare il metodo `Mail::send()` del genitore per inviare l'email.
        *   Questo assicura che il destinatario BCC venga aggiunto all'elenco di copia conoscenza nascosta dell'email, rendendolo invisibile ai destinatari primari.

-   `bccmail/override/classes/index.php`
    *   **Responsabilità:** Simile a `controllers/admin/index.php`, questo è un file di sicurezza per impedire l'elenco diretto delle directory della directory `override/classes`. Tipicamente contiene un tag PHP vuoto o un reindirizzamento.

### 4.4 Risorse JavaScript (`views/js/`)

-   `bccmail/views/templates/admin/js/bccmail.js`
    *   **Ambito:** Back-office.
    *   **Quali listener di eventi lega:** Questo script è probabilmente utilizzato nella pagina di configurazione del modulo o nella schermata `AdminMailBccController`. Potrebbe legare listener per:
        *   Eventi di invio del modulo per gestire il salvataggio della configurazione.
        *   Modifiche delle checkbox per la selezione dei modelli di email da inviare in BCC.
        *   Validazione del campo di input per l'indirizzo email BCC.
        *   Chiamate AJAX per aggiornare le impostazioni dinamicamente senza un ricaricamento completo della pagina.
    *   **Quali manipolazioni del DOM, popup modali, animazioni o chiamate a SDK di terze parti esegue:** Potrebbe eseguire semplici manipolazioni del DOM come mostrare/nascondere elementi in base alle selezioni, visualizzare messaggi di successo/errore o una convalida di base del modulo. È improbabile che coinvolga animazioni complesse o SDK di terze parti per la funzionalità di questo modulo.

### 4.5 Fogli di stile CSS (`views/css/`)
Il modulo non sembra includere alcun file CSS personalizzato nel suo archivio. Probabilmente si basa sullo stile predefinito del back-office di PrestaShop per i suoi moduli di configurazione e elenchi, o stili inline se assolutamente necessario.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**: Nessuno esplicitamente elencato, ma il modulo principale del modulo (`getContent()`) renderizzerebbe le sue impostazioni utilizzando un template Smarty, tipicamente situato in `views/templates/admin/configure.tpl` o simile, anche se non esplicitamente elencato nell'inventario come file separato.
-   **Template admin (`views/templates/admin/`)**:
    *   `bccmail/lib/searchTool/views/scripts.tpl`
        *   **Scopo:** Questo template è probabilmente parte di una libreria di aiuto o utilità all'interno del modulo (ad es. uno strumento di ricerca per i template email). Contenerebbe logica JavaScript o Smarty per renderizzare input di ricerca, filtrare elenchi o gestire il caricamento dinamico dei contenuti all'interno dell'interfaccia di amministrazione. Non è una pagina autonoma ma un componente.
-   **Template front-office (`views/templates/front/`)**: Nessuno. Il modulo non ha presenza nel front-office.

### 4.7 Schema del Database e Mappa degli Hook

-   **Tabelle del Database**:
    *   Il modulo memorizza principalmente la sua configurazione nella tabella `ps_configuration` di PrestaShop.
        *   Le chiavi di `PS_CONFIGURATION` includerebbero:
            *   `BCCMAIL_EMAIL_ADDRESS`: Memorizza l'indirizzo email principale per BCC.
            *   `BCCMAIL_SELECTED_TEMPLATES`: Memorizza un array serializzato o una stringa separata da virgole dei nomi dei modelli di email selezionati per BCC.
            *   `MYPRESTA_UPDATES`, `UPDATE_`, `UPDATEV_`: Per i controlli di aggiornamento del modulo.
    *   Nessuna tabella SQL personalizzata è esplicitamente creata da questo modulo in base all'inventario fornito.

-   **Tabella degli Hook Registrati**:
    Il modulo non registra alcun hook di visualizzazione standard (come `displayHeader`, `displayRightColumn`, `displayFooter`) in quanto non ha presenza nel front-office. La sua funzionalità principale si basa sulla sovrascrittura della classe `Mail` piuttosto che sull'utilizzo di hook tradizionali di PrestaShop per l'invio di email.

    Tuttavia, si "aggancia" implicitamente al processo di invio delle email tramite il suo override.
    *   **`actionEmailSend` (Implicito tramite override)**: Sebbene non sia un hook formalmente registrato, `override/classes/Mail.php` del modulo intercetta efficacemente il metodo `Mail::send()`, che è l'azione principale di invio di un'email. È qui che viene iniettata la logica BCC.
        *   **Tempo di esecuzione:** Ogni volta che `Mail::send()` viene chiamato da PrestaShop (ad es. alla conferma dell'ordine, alla registrazione del cliente, all'invio del modulo di contatto).
        *   **Scopo tecnico:** Aggiungere il destinatario BCC configurato all'email prima che venga inviata dal mailer di PrestaShop.

## 5. Supporto Ufficiale e Aggiornamenti
Per gli ultimi aggiornamenti del modulo, supporto tecnico e risorse aggiuntive, visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo al modulo "Invia una copia delle email (BCC)".
