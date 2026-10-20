---
title: "Allegati email - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Allegati email di MyPresta.eu."
sidebar:
  label: "Allegati email - Manuale del commerciante e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Email attachments su MyPresta.eu](https://mypresta.eu/modules/administration-tools/email-attachments.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/email-attachments/)
>
> ---


# Allegati email

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Non sono richieste configurazioni server insolite.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

Il modulo "Allegati email" offre un processo di configurazione semplice, principalmente tramite una schermata di amministrazione dedicata dove gestisci i tuoi allegati e li colleghi a specifici modelli di email.

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Quando clicchi per la prima volta su "Configura" dopo l'installazione, verrai indirizzato alla pagina di configurazione principale del modulo. Questa pagina serve principalmente come punto di ingresso e potrebbe contenere informazioni generali o un link alla schermata di gestione degli allegati dedicata.

-   **Cosa fa questa schermata:** Questa schermata iniziale fornisce una breve panoramica del modulo e di solito ti indirizza all'interfaccia principale per la gestione degli allegati email. Potrebbe anche contenere impostazioni generali se il modulo ne avesse, ma per questo modulo, la funzionalità principale è gestita in un controller amministrativo separato.
-   **Effetto della modifica delle impostazioni:** Qualsiasi impostazione qui influenzerebbe il comportamento generale del modulo. Tuttavia, per "Allegati email", l'azione principale è navigare alla pagina di gestione "Allegati email" dedicata.
-   **Valore consigliato:** Segui le istruzioni sullo schermo, che di solito prevedono di cliccare un pulsante o un link per procedere all'area di gestione degli allegati.

### 2.2 Schermata amministrativa dedicata: Allegati email (Back Office > Moduli > Allegati email)

Questo è l'hub principale per la gestione di tutti i tuoi allegati email. Di solito troverai una nuova voce di menu sotto **Moduli** o **Parametri negozio** (a seconda della tua versione di PrestaShop e del design del modulo) denominata "Allegati email" o simile.

**Posizione del menu:** Back Office > Moduli > Allegati email (o simile, controlla il tuo menu amministrativo dopo l'installazione)

#### Panoramica della schermata di gestione "Allegati email"

Questa schermata presenterà un elenco (una "griglia" o "tabella") di tutti gli allegati email che hai configurato. Da qui, puoi:

-   **Aggiungi nuovo allegato:** Crea una nuova regola di allegato.
-   **Modifica allegato esistente:** Modifica le impostazioni per un allegato che hai già creato.
-   **Elimina allegato:** Rimuovi una regola di allegato.

#### Aggiunta/Modifica di un allegato email

Quando clicchi su "Aggiungi nuovo allegato" o "Modifica" uno esistente, ti verrà presentato un modulo per definire le proprietà dell'allegato.

**Campi e opzioni del modulo:**

1.  **Nome allegato:**

    *   **Cosa fa questa impostazione:** Questo è un nome interno per il tuo riferimento nel Back Office. Ti aiuta a identificare facilmente la regola dell'allegato.
    *   **Effetto della modifica di questa impostazione:** Modifica solo l'etichetta che vedi nell'elenco amministrativo. Non influisce sul nome del file visto dal cliente.
    *   **Valore consigliato:** Un nome descrittivo, ad esempio, "Guida di Benvenuto PDF", "Termini e Condizioni Conferma Ordine", "Manuale Prodotto per Nuovi Ordini".
    *   **Scenario del commerciante:** Hai più allegati per scopi diversi; un nome chiaro ti aiuta a distinguerli.
2.  **Seleziona modello(i) email:**

    *   **Cosa fa questa impostazione:** Questa impostazione cruciale determina *a quale* email(s) di PrestaShop verrà aggiunto questo allegato. Di solito vedrai un elenco di tutti i modelli di email standard di PrestaShop (ad esempio, `account`, `order_conf`, `shipped`, `contact_form`). Puoi selezionare uno o più modelli.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando selezionato:* L'allegato verrà incluso in ogni email inviata utilizzando il/i modello/i scelto/i.
        *   *Quando deselezionato:* L'allegato non verrà incluso nelle email che utilizzano quel modello.
    *   **Valore consigliato:** Seleziona solo i modelli di email pertinenti. Ad esempio, una "Guida di Benvenuto" dovrebbe essere allegata solo all'email `account` (creazione account cliente).
    *   **Scenario del commerciante:** Vuoi allegare un PDF "Politica di Reso" alle email `order_conf` (conferma d'ordine) e `shipped` (notifica di spedizione).
3.  **Tipo di allegato:**

    *   **Cosa fa questa impostazione:** Questo definisce la fonte del tuo file allegato. Il modulo offre diverse opzioni:
        *   **Carica file:** Allega un file esistente dal tuo computer.
        *   **Genera PDF da pagina CMS:** Crea un PDF da una delle tue pagine CMS PrestaShop esistenti.
        *   **Crea PDF da editor di testo ricco:** Progetta contenuti PDF personalizzati direttamente all'interno del modulo utilizzando un editor visuale.
    *   **Effetto della modifica di questa impostazione:** Determina la prossima serie di opzioni che vedrai per specificare il contenuto dell'allegato.
    *   **Valore consigliato:** Scegli il tipo che meglio si adatta alla tua fonte di contenuto.
    *   **Scenario del commerciante:** Hai un "Garanzia.pdf" pre-fatto (Carica file), oppure vuoi convertire la tua pagina CMS "Chi siamo" in un PDF (Genera PDF da pagina CMS), oppure devi scrivere un PDF "Offerta speciale" personalizzato (Crea PDF da editor di testo ricco).

    **Sotto-impostazioni basate sul tipo di allegato:**

    *   **Se è selezionato "Carica file":**

        *   **Campo di caricamento file:**
            *   **Cosa fa questa impostazione:** Ti consente di sfogliare il tuo computer e caricare un file (ad esempio, PDF, JPG, DOCX).
            *   **Effetto della modifica di questa impostazione:** Il file selezionato verrà memorizzato sul tuo server e utilizzato come allegato.
            *   **Valore consigliato:** Carica un file che non sia eccessivamente grande per evitare problemi di consegna delle email. I PDF sono generalmente preferiti per i documenti.
            *   **Scenario del commerciante:** Allegare il PDF "Termini e Condizioni" della tua azienda.
    *   **Se è selezionato "Genera PDF da pagina CMS":**

        *   **Seleziona pagina CMS:**
            *   **Cosa fa questa impostazione:** Fornisce un elenco a discesa di tutte le tue pagine CMS PrestaShop attive.
            *   **Effetto della modifica di questa impostazione:** Il contenuto della pagina CMS scelta verrà convertito in un PDF e allegato.
            *   **Valore consigliato:** Seleziona una pagina CMS con contenuto adatto a un documento PDF (ad esempio, "Chi siamo", "Informativa sulla privacy").
            *   **Scenario del commerciante:** Allegare automaticamente la tua pagina CMS "Politica di reso" come PDF alle email pertinenti.
    *   **Se è selezionato "Crea PDF da editor di testo ricco":**

        *   **Editor di testo ricco (WYSIWYG):**
            *   **Cosa fa questa impostazione:** Un editor visuale dove puoi digitare e formattare contenuti personalizzati, aggiungere immagini, link, ecc. Questo contenuto verrà quindi convertito in un PDF.
            *   **Effetto della modifica di questa impostazione:** Il contenuto che crei qui formerà il corpo del PDF allegato.
            *   **Valore consigliato:** Usalo per contenuti dinamici o unici che non esistono come file o pagina CMS. Mantieni il design semplice per i migliori risultati di conversione PDF.
            *   **Scenario del commerciante:** Creare un messaggio "Grazie" personalizzato con un codice sconto come allegato PDF.
4.  **Nome file allegato (come visto dal cliente):**

    *   **Cosa fa questa impostazione:** Questo è il nome del file che il cliente vedrà nel suo client di posta elettronica quando riceverà l'allegato.
    *   **Effetto della modifica di questa impostazione:** Cambia il modo in cui il file appare nella casella di posta del cliente.
    *   **Valore consigliato:** Un nome file chiaro, descrittivo e professionale (ad esempio, `La-Tua-Conferma-Ordine.pdf`, `Informazioni-Garanzia.pdf`). Includi l'estensione del file (ad esempio, `.pdf`).
    *   **Scenario del commerciante:** Hai caricato `my_internal_doc_v2.pdf`, ma vuoi che il cliente veda `Guida-Prodotto.pdf`.
5.  **Attivo:**

    *   **Cosa fa questa impostazione:** Un semplice interruttore ON/OFF per abilitare o disabilitare questa specifica regola di allegato.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* La regola dell'allegato è attiva e verrà applicata alle email selezionate.
        *   *Quando disabilitato:* La regola dell'allegato è inattiva e non aggiungerà file alle email.
    *   **Valore consigliato:** Imposta su "SÌ" quando vuoi che l'allegato venga inviato.
    *   **Scenario del commerciante:** Stai testando un allegato e vuoi disabilitarlo temporaneamente senza eliminare la configurazione.

#### 2.2.1 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Allegati email (Controller Admin)** | Nome allegato | Testo descrittivo | Etichetta interna per una facile identificazione nel BO. |
| | Seleziona modello(i) email | Modelli specifici (es. `order_conf`) | Determina quali email ricevono l'allegato. |
| | Tipo di allegato | Varia (Carica file, Pagina CMS, Testo ricco) | Definisce la fonte del contenuto dell'allegato. |
| | *Se Carica file:* Campo di caricamento file | N/A | Carica un file esistente dal tuo computer. |
| | *Se Genera PDF da pagina CMS:* Seleziona pagina CMS | Pagina CMS specifica | Converte il contenuto della pagina CMS scelta in PDF. |
| | *Se Crea PDF da editor di testo ricco:* Editor di testo ricco | Contenuto personalizzato | Crea un PDF dal contenuto inserito nell'editor. |
| | Nome file allegato | Nome file descrittivo (es. `documento.pdf`) | Il nome che i clienti vedono nel loro client di posta elettronica. |
| | Attivo | SÌ | Abilita/disabilita la regola dell'allegato. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei allegati non vengono inviati, o i clienti segnalano di non riceverli.**

-   **R:** Innanzitutto, controlla se la regola dell'allegato è "Attiva" nella configurazione del modulo.
-   **R:** Assicurati di aver selezionato il/i modello/i di email corretto/i per l'allegato. Prova a inviare tu stesso una di quelle email (ad esempio, effettua un ordine di prova, crea un nuovo account cliente).
-   **R:** Controlla le impostazioni email di PrestaShop (Parametri negozio > Email) per assicurarti che le email vengano inviate correttamente in generale. Prova a inviare un'email di prova da PrestaShop.
-   **R:** Il file allegato potrebbe essere troppo grande, causando il rifiuto dell'email da parte dei provider di posta elettronica. Prova una dimensione del file più piccola.
-   **R:** Svuota la cache di PrestaShop (Parametri avanzati > Prestazioni > Svuota cache).

**D2: Il PDF generato dalla mia pagina CMS ha un aspetto strano o presenta problemi di formattazione.**

-   **R:** La generazione di PDF da HTML a volte può essere complicata. Assicurati che il contenuto della tua pagina CMS sia HTML pulito senza JavaScript complessi o elementi altamente dinamici.
-   **R:** Prova a semplificare il layout della tua pagina CMS. Evita CSS eccessivamente complessi o immagini molto larghe che potrebbero non adattarsi bene a una pagina PDF standard.
-   **R:** Se i problemi persistono, considera di creare un file PDF dedicato esternamente e di utilizzare l'opzione "Carica file".

**D3: Posso allegare file diversi in base al prodotto ordinato o al gruppo di clienti?**

-   **R:** Questo modulo, nella sua configurazione standard, allega file a *tutte* le email di un tipo selezionato, indipendentemente dal prodotto specifico o dal gruppo di clienti. Per allegati condizionali più avanzati, potrebbe essere necessario uno sviluppo personalizzato o un modulo più specializzato.

**D4: Come traduco il contenuto di un PDF creato con l'Editor di testo ricco per diverse lingue?**

-   **R:** Quando usi l'Editor di testo ricco, dovresti vedere le schede delle lingue (ad esempio, inglese, francese, spagnolo) se il tuo negozio PrestaShop supporta più lingue. Dovrai inserire e formattare il contenuto per ogni lingua separatamente all'interno dell'editor. Il modulo allegherà quindi la versione linguistica corretta in base alla lingua selezionata dal cliente.

**D5: Dove vengono archiviati i file caricati sul mio server?**

-   **R:** I file caricati vengono tipicamente archiviati all'interno della directory del modulo o in una cartella di caricamento designata all'interno del modulo. Generalmente non è necessario interagire direttamente con questi file tramite FTP, poiché il modulo li gestisce.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster che lavorano con il modulo "Allegati email".

### 4.1 Panoramica dell'architettura

Il modulo "Allegati email" (`mattach`) estende la funzionalità email principale di PrestaShop sovrascrivendo la classe `Mail`. Ciò gli consente di iniettare allegati personalizzati nelle email in uscita senza modificare direttamente i file core. Segue un modello MVC standard di PrestaShop per la sua interfaccia di gestione del Back Office, utilizzando un `AdminController` per gestire le entità `mailfile` che rappresentano le configurazioni degli allegati. La generazione di PDF è gestita internamente, convertendo il contenuto CMS o l'input dell'editor di testo ricco.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    *   Questo modulo **non** contiene alcun controller front-office dedicato. Tutte le sue operazioni vengono eseguite nel Back Office o sovrascrivendo le classi core durante l'invio delle email.
-   **Controller Admin Back-Office**:

    *   `mattach/controllers/admin/AdminMailAttachments.php`

        *   **Nome classe**: `AdminMailAttachmentsController`
        *   **Classe genitore**: `ModuleAdminController`
        *   **Responsabilità**: Questo è il controller principale per la gestione delle regole degli allegati email. Gestisce le operazioni CRUD (Create, Read, Update, Delete) per l'entità `mailfile`. Visualizza un elenco di allegati configurati, fornisce moduli per aggiungerli/modificarli e gestisce i caricamenti di file, la selezione di pagine CMS e il contenuto dell'editor di testo ricco per la generazione di PDF. Utilizza `HelperList` di PrestaShop per la visualizzazione a griglia e `HelperForm` per i moduli di aggiunta/modifica.
        *   **Tabella / Entità gestita**: `mailfile` (tabella personalizzata per i dati del modulo).
        *   **Chiavi di configurazione associate**: `PS_LANG_DEFAULT` (utilizzata per i campi multilingue).
    *   `mattach/controllers/admin/index.php`

        *   **Nome classe**: (Nessuna classe esplicita, tipicamente un segnaposto o un reindirizzamento)
        *   **Responsabilità**: Questo file è spesso una misura di sicurezza (per prevenire l'elenco diretto delle directory) o un semplice reindirizzamento all'interno della struttura amministrativa di PrestaShop. Non contiene logica di controller attiva per la funzionalità del modulo.

### 4.3 Classi e modelli core (`classes/`)

-   `mattach/override/classes/index.php`

    *   **Responsabilità**: File di sicurezza standard di PrestaShop per prevenire l'elenco delle directory.
-   `mattach/override/classes/Mail.php`

    *   **Nome classe**: `Mail` (sovrascrive la classe `Mail` core di PrestaShop)
    *   **Classe genitore**: `MailCore`
    *   **Responsabilità**: Questa è la parte più critica della funzionalità del modulo. Sovrascrivendo la classe `Mail`, il modulo intercetta il metodo `send()`. All'interno del metodo `send()` sovrascritto, controlla se sono configurate regole di allegato per il modello di email specifico che viene inviato. Se vengono trovate corrispondenze, recupera i dati dell'allegato (percorso del file caricato, contenuto PDF generato), crea gli oggetti `Swift_Attachment` necessari e li aggiunge all'email prima che venga inviata. Ciò garantisce che gli allegati siano inclusi senza problemi in tutte le email in uscita pertinenti.
    *   **Interazione con il database**: Interagisce con la tabella `mailfile` personalizzata del modulo per recuperare le configurazioni degli allegati.
    *   **Metodi pubblici chiave**: Sovrascrive `send()` per iniettare la logica degli allegati.

### 4.4 Risorse JavaScript (`views/js/`)

-   `mattach/views/templates/admin/js/mattach.js`
    *   **Ambito**: Back-office (AdminMailAttachmentsController).
    *   **Funzionalità**: Questo script probabilmente gestisce il comportamento dinamico del modulo di configurazione degli allegati. Ciò potrebbe includere:
        *   Mostrare/nascondere campi di input specifici in base al "Tipo di allegato" selezionato (ad esempio, mostrare il campo di caricamento file solo quando è selezionato "Carica file").
        *   Chiamate AJAX per recuperare elenchi di pagine CMS o altri dati dinamici.
        *   Inizializzazione dell'editor di testo ricco (ad esempio, TinyMCE o CKEditor) per l'opzione "Crea PDF da editor di testo ricco".
        *   Validazione lato client o miglioramenti dell'interfaccia utente per l'interfaccia di gestione degli allegati.

### 4.5 Fogli di stile CSS (`views/css/`)

-   Questo modulo **non** sembra contenere alcun file CSS personalizzato nell'inventario fornito. Probabilmente si basa sullo stile predefinito del Back Office di PrestaShop per i suoi moduli di configurazione e elenchi.

### 4.6 Struttura del modello Smarty (`views/templates/`)

-   **Modelli di hook (`views/templates/hook/`)**:

    *   Questo modulo **non** contiene alcun modello di hook specifico nell'inventario fornito. Il suo impatto sul front-office è esclusivamente tramite allegati email, non elementi visivi.
-   **Modelli amministrativi (`views/templates/admin/`)**:

    *   `mattach/views/templates/admin/orderstates.tpl`
        *   **Scopo**: Il nome di questo modello suggerisce che potrebbe essere utilizzato per visualizzare o gestire gli stati degli ordini in relazione agli allegati, o forse per selezionare gli stati degli ordini per allegati condizionali (anche se la descrizione del modulo non menziona esplicitamente questa funzionalità avanzata). Potrebbe far parte del modulo `AdminMailAttachmentsController`, potenzialmente per selezionare quali modifiche dello stato dell'ordine attivano un'email con un allegato.
    *   `mattach/lib/searchTool/views/scripts.tpl`
        *   **Scopo**: Questo modello probabilmente contiene logica JavaScript o Smarty relativa a uno strumento di ricerca o filtro utilizzato all'interno dell'interfaccia amministrativa, possibilmente per la ricerca tra modelli di email o pagine CMS. È un modello di utilità per migliorare l'interfaccia utente amministrativa.
-   **Modelli front-office (`views/templates/front/`)**:

    *   Questo modulo **non** contiene alcun modello front-office.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    *   `ps_mailfile`: Questa è la tabella personalizzata principale creata dal modulo per archiviare ogni configurazione di allegato email.
        *   `id_mailfile`: Chiave primaria.
        *   `name`: Nome interno della regola dell'allegato.
        *   `file_name`: Il nome effettivo del file (o nome generato) dell'allegato.
        *   `file_path`: Percorso del file caricato o dove il PDF generato è temporaneamente archiviato.
        *   `file_type`: Tipo di allegato (ad esempio, 'upload', 'cms', 'editor').
        *   `id_cms`: Se `file_type` è 'cms', memorizza l'ID della pagina CMS.
        *   `content`: Se `file_type` è 'editor', memorizza il contenuto di testo ricco (multilingue).
        *   `mail_templates`: Un array serializzato o una stringa separata da virgole di nomi di modelli di email (ad esempio, `account`, `order_conf`) a cui si applica questo allegato.
        *   `active`: Booleano (0 o 1) che indica se la regola dell'allegato è attiva.
    *   `ps_mailfile_lang`: Tabella complementare per campi multilingue come `content` (se `file_type` è 'editor').
        *   `id_mailfile`: Chiave esterna a `ps_mailfile`.
        *   `id_lang`: ID della lingua.
        *   `content`: Contenuto di testo ricco tradotto.
-   **Tabella degli hook registrati**:

    *   Il modulo opera principalmente sovrascrivendo la classe `Mail` core, che è un metodo più diretto e potente rispetto all'affidarsi esclusivamente agli hook per la modifica delle email. Sebbene possa registrare alcuni hook standard per l'installazione/disinstallazione del modulo o l'integrazione del menu del Back Office, la sua logica di iniezione degli allegati core si trova nell'override di `Mail`.
    *   **Metodo `install()`**:
        *   Registra il modulo nel menu del Back Office.
        *   Crea le tabelle del database `ps_mailfile` e `ps_mailfile_lang`.
        *   Installa l'override della classe `Mail`.
    *   **Metodo `uninstall()`**:
        *   Rimuove il modulo dal menu del Back Office.
        *   Elimina le tabelle del database `ps_mailfile` e `ps_mailfile_lang`.
        *   Disinstalla l'override della classe `Mail`.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Allegati email", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda riguardante la funzionalità e la configurazione del modulo.
