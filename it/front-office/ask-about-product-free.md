---
title: "Chiedi informazioni sul prodotto gratuito - Manuale del commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Chiedi informazioni sul prodotto gratuito di MyPresta.eu."
sidebar:
  label: "Chiedi informazioni sul prodotto gratuito - Manuale del commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Ask about product free su MyPresta.eu](https://mypresta.eu/modules/front-office-features/ask-about-product-free.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/ask-about-product-free/)
>
> ---


# Chiedi informazioni sul prodotto gratuito

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo "Chiedi informazioni sul prodotto gratuito", dove controlli il suo comportamento e aspetto.

-   **Posizione del menu:** Back Office > Moduli > Gestione moduli > "Chiedi informazioni sul prodotto gratuito" > Configura

#### Impostazioni e opzioni:

1.  **Visualizza riepilogo prodotto all'interno del popup**

    -   **Cosa fa questa impostazione:** Controlla se un piccolo riepilogo del prodotto (come il suo nome e immagine) viene mostrato all'interno del modulo popup "Chiedi informazioni sul prodotto".
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (Sì):* Il modulo popup includerà una breve panoramica del prodotto su cui il cliente sta chiedendo informazioni. Questo aiuta il cliente a confermare che sta chiedendo informazioni sull'articolo corretto e fornisce contesto per te quando ricevi l'email.
        -   *Quando disabilitato (No):* Il modulo popup conterrà solo i campi per il nome del cliente, l'email e la domanda, senza alcun riepilogo specifico del prodotto.
    -   **Valore consigliato:** **Sì**.
    -   **Scenario/esempio del commerciante:** Abilitare questa opzione aiuta a evitare confusione. Un cliente potrebbe avere più schede aperte e dimenticare su quale prodotto sta chiedendo informazioni. Il riepilogo lo conferma per lui e per te.
2.  **Abilitato**

    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare l'intera funzionalità "Chiedi informazioni sul prodotto" sul tuo negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (Sì):* Il pulsante "Chiedi informazioni sul prodotto" apparirà sulle pagine dei prodotti e il modulo popup sarà funzionante.
        -   *Quando disabilitato (No):* Il pulsante "Chiedi informazioni sul prodotto" sarà nascosto dalle pagine dei prodotti e i clienti non potranno utilizzare questa funzionalità.
    -   **Valore consigliato:** **Sì** (per utilizzare il modulo).
    -   **Scenario/esempio del commerciante:** Potresti disabilitarlo temporaneamente se stai eseguendo manutenzione o se preferisci gestire tutte le richieste tramite un canale diverso per un certo periodo.
3.  **Conforme al GDPR**

    -   **Cosa fa questa impostazione:** Attiva una casella di controllo sul modulo "Chiedi informazioni sul prodotto", richiedendo ai clienti di accettare esplicitamente la tua politica sulla privacy prima di inviare la loro domanda. Questo aiuta il tuo negozio a rispettare il GDPR e altre normative sulla protezione dei dati.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (Sì):* Sul modulo apparirà una casella di controllo obbligatoria, che di solito recita qualcosa come "Accetto la politica sulla privacy". Il cliente deve spuntare questa casella per inviare la sua domanda.
        -   *Quando disabilitato (No):* La casella di controllo della politica sulla privacy non verrà visualizzata e i clienti potranno inviare le loro domande senza consenso esplicito.
    -   **Valore consigliato:** **Sì**.
    -   **Scenario/esempio del commerciante:** Se il tuo negozio opera in regioni con leggi severe sulla protezione dei dati (come l'UE), abilitare questa opzione è fondamentale per la conformità legale.
4.  **Pagina della politica sulla privacy**

    -   **Cosa fa questa impostazione:** Se "Conforme al GDPR" è abilitato, questa impostazione ti consente di selezionare quale pagina CMS (Content Management System) del tuo negozio sarà collegata come tua politica sulla privacy.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando viene selezionata una pagina:* Il testo "Accetto la politica sulla privacy" nel modulo popup includerà un link cliccabile alla pagina CMS scelta, consentendo ai clienti di rivedere facilmente la tua politica.
        -   *Quando non viene selezionata alcuna pagina (o GDPR Compliant è No):* Non verrà fornito alcun link, o la funzionalità GDPR non sarà attiva.
    -   **Valore consigliato:** Seleziona la pagina ufficiale della politica sulla privacy del tuo negozio.
    -   **Scenario/esempio del commerciante:** Devi avere una pagina CMS dedicata che descriva le tue pratiche di gestione dei dati. Questa impostazione garantisce che i clienti possano accedervi facilmente.
5.  **Titolo dell'email**

    -   **Cosa fa questa impostazione:** Definisce l'oggetto dell'email che ricevi quando un cliente invia una domanda tramite il modulo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su un titolo specifico (es. "Nuova domanda sul prodotto"):* Tutte le email in arrivo da questo modulo utilizzeranno questa riga dell'oggetto, rendendole facili da identificare nella tua casella di posta.
        -   *Quando lasciato predefinito:* Il modulo utilizzerà la sua riga dell'oggetto predefinita, che potrebbe essere meno descrittiva.
    -   **Valore consigliato:** Qualcosa di chiaro e descrittivo, come "Nuova domanda sul prodotto da [Nome del tuo negozio]".
    -   **Scenario/esempio del commerciante:** Un oggetto chiaro ti aiuta a dare priorità e a rispondere rapidamente alle richieste dei clienti, soprattutto se ricevi molte email ogni giorno.
6.  **Destinatario dell'email dal modulo**

    -   **Cosa fa questa impostazione:** Specifica l'indirizzo/gli indirizzi email a cui verranno inviate le domande dei clienti inviate tramite il modulo "Chiedi informazioni sul prodotto".
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando vengono inseriti uno o più indirizzi email (separati da virgole):* Il modulo invierà tutte le richieste dei clienti a questi indirizzi specificati.
        -   *Quando lasciato vuoto:* Il modulo potrebbe impostare come predefinito l'email di contatto principale del negozio, oppure la funzione potrebbe non funzionare correttamente.
    -   **Valore consigliato:** Il tuo indirizzo email del servizio clienti (es. `support@tuonegozio.com`) o un'email dedicata per le richieste sui prodotti. Puoi aggiungere più email separate da virgole se più membri del team devono riceverle.
    -   **Scenario/esempio del commerciante:** Indirizzare queste email al team giusto garantisce risposte rapide, migliorando la soddisfazione del cliente.
7.  **Protezione ReCaptcha (v2)**

    -   **Cosa fa questa impostazione:** Integra Google reCAPTCHA v2 (la casella di controllo "Non sono un robot") nel modulo "Chiedi informazioni sul prodotto" per proteggere da spam e invii automatizzati.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (Sì):* La casella di controllo reCAPTCHA apparirà sul modulo, richiedendo ai clienti di superare la sfida prima di inviare.
        -   *Quando disabilitato (No):* Il modulo non avrà la protezione reCAPTCHA, rendendolo potenzialmente vulnerabile ai bot di spam.
    -   **Valore consigliato:** **Sì**.
    -   **Scenario/esempio del commerciante:** Se stai ricevendo molte richieste di spam tramite il modulo, abilitare reCAPTCHA è essenziale per filtrare i messaggi illegittimi.
8.  **Chiave del sito reCaptcha**

    -   **Cosa fa questa impostazione:** Questa è la chiave pubblica fornita da Google reCAPTCHA che consente al tuo sito web di visualizzare il widget reCAPTCHA. Ottieni questa chiave quando registri il tuo sito con Google reCAPTCHA.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando inserita correttamente:* Il widget reCAPTCHA verrà visualizzato e funzionerà correttamente sul tuo modulo.
        -   *Quando errata o vuota:* reCAPTCHA non funzionerà e potresti vedere un messaggio di errore o il modulo non verrà inviato.
    -   **Valore consigliato:** La chiave del sito ottenuta dal tuo account Google reCAPTCHA.
    -   **Scenario/esempio del commerciante:** Devi registrare il tuo dominio con Google reCAPTCHA (v2) per ottenere sia una chiave del sito che una chiave segreta.
9.  **Chiave segreta reCaptcha**

    -   **Cosa fa questa impostazione:** Questa è la chiave privata fornita da Google reCAPTCHA che consente al tuo server di verificare la risposta reCAPTCHA. Viene utilizzata per la convalida lato server.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando inserita correttamente:* Il tuo server può verificare con successo se un cliente ha superato la sfida reCAPTCHA.
        -   *Quando errata o vuota:* Anche se il widget reCAPTCHA viene visualizzato, l'invio del modulo fallirà la convalida e la domanda non verrà inviata.
    -   **Valore consigliato:** La chiave segreta ottenuta dal tuo account Google reCAPTCHA.
    -   **Scenario/esempio del commerciante:** Questa chiave è cruciale per l'aspetto di sicurezza di reCAPTCHA, garantendo che vengano elaborate solo le sottomissioni legittime.

#### Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Visualizza riepilogo prodotto all'interno del popup | Sì | Mostra i dettagli del prodotto nel popup per chiarezza. |
| Configurazione modulo | Abilitato | Sì | Attiva/disattiva la funzione "Chiedi informazioni sul prodotto". |
| Configurazione modulo | Conforme al GDPR | Sì | Aggiunge una casella di controllo per l'accordo sulla politica sulla privacy al modulo. |
| Configurazione modulo | Pagina della politica sulla privacy | Seleziona la tua pagina CMS della politica sulla privacy | Collega alla politica sulla privacy del tuo negozio per il GDPR. |
| Configurazione modulo | Titolo dell'email | "Nuova domanda sul prodotto da [Nome del tuo negozio]" | Imposta l'oggetto per le email di domanda in arrivo. |
| Configurazione modulo | Destinatario dell'email dal modulo | La tua email del servizio clienti (es. `support@tuonegozio.com`) | Specifica dove vengono inviate le domande dei clienti. |
| Configurazione modulo | Protezione ReCaptcha (v2) | Sì | Abilita Google reCAPTCHA per prevenire lo spam. |
| Configurazione modulo | Chiave del sito reCaptcha | La tua chiave del sito Google reCAPTCHA | Chiave pubblica per la visualizzazione del widget reCAPTCHA. |
| Configurazione modulo | Chiave segreta reCaptcha | La tua chiave segreta Google reCAPTCHA | Chiave privata per la convalida reCAPTCHA lato server. |

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### AdminAapfreeQuestionController (Back Office > Chiedi informazioni sul prodotto > Domande)

Questa schermata di amministrazione dedicata ti consente di visualizzare e gestire tutte le domande inviate tramite il modulo "Chiedi informazioni sul prodotto".

-   **Nome schermata e posizione del menu:** Back Office > **Chiedi informazioni sul prodotto** (nuova voce di menu) > **Domande**
-   **Azioni e impostazioni disponibili:**
    -   **Tabella di elenco:** Questa schermata visualizza una tabella di tutte le domande inviate. Ogni riga tipicamente mostra:
        -   **ID:** Identificatore univoco per la domanda.
        -   **Nome cliente:** Il nome fornito dal cliente.
        -   **Email cliente:** L'indirizzo email fornito dal cliente.
        -   **Nome prodotto:** Il nome del prodotto a cui si riferisce la domanda.
        -   **Domanda:** Un estratto o il testo completo della domanda del cliente.
        -   **Data aggiunta:** Quando la domanda è stata inviata.
        -   **Stato:** (es. Nuovo, Risposto, In sospeso) - *Nota: il dossier del modulo non indica esplicitamente un campo stato, ma è una caratteristica comune per tali elenchi. Se non presente, elencherà semplicemente tutte le domande.*
    -   **Visualizza dettagli:** Di solito puoi cliccare su una domanda nell'elenco per visualizzarne i dettagli completi, incluso il testo completo della domanda ed eventualmente il link del prodotto.
    -   **Elimina:** Opzioni per eliminare singole domande o potenzialmente eliminare in blocco le domande selezionate.
-   **Effetto delle modifiche:**
    -   **Visualizzazione delle domande:** Ti consente di rivedere tutte le richieste dei clienti in un'unica posizione centralizzata all'interno del tuo back office PrestaShop, anche se le ricevi anche via email.
    -   **Eliminazione delle domande:** Rimuove il record della domanda dal tuo database. Questo è utile per ripulire le richieste vecchie o irrilevanti.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Controlla regolarmente questo elenco "Domande" (o la tua casella di posta elettronica, come configurato) per nuove richieste.
    2.  Dai priorità e rispondi prontamente alle domande per mantenere un buon servizio clienti.
    3.  Dopo aver risposto, potresti eliminare la domanda da questo elenco per mantenerlo in ordine, o se il modulo lo supporta, contrassegnarla come "Risposta".

#### index.php (aapfree/controllers/admin/index.php)

Questo file è tipicamente un segnaposto o un reindirizzamento all'interno della directory `controllers/admin` e non rappresenta una schermata distinta e configurabile per il commerciante. È una pratica standard di PrestaShop avere un `index.php` nelle sottodirectory per impedire l'elenco delle directory, oppure potrebbe contenere una logica di routing di base. Non gestisce una tabella o un'entità specifica per l'interazione diretta del commerciante.

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Il pulsante "Chiedi informazioni sul prodotto" non viene visualizzato sulle mie pagine prodotto.**

-   **R:** Innanzitutto, verifica se il modulo è "Abilitato" nelle sue impostazioni di configurazione (Back Office > Moduli > Gestione moduli > Chiedi informazioni sul prodotto gratuito > Configura). Se lo è, prova a svuotare la cache di PrestaShop (Parametri avanzati > Prestazioni > Svuota cache). A volte, conflitti di tema o specifiche strutture di tema personalizzate possono impedire la visualizzazione del pulsante. Se è ancora mancante, contatta il tuo webmaster o il supporto MyPresta.eu.

**D2: Non ricevo email quando i clienti inviano domande.**

-   **R:**
    1.  Verifica l'impostazione "Destinatario dell'email dal modulo" nella configurazione del modulo. Assicurati che l'indirizzo/gli indirizzi email siano corretti e separati da virgole se ce ne sono più.
    2.  Controlla la cartella spam/posta indesiderata nella casella di posta del destinatario.
    3.  Assicurati che le impostazioni email del tuo negozio siano configurate correttamente in PrestaShop (Parametri avanzati > E-mail). Prova a inviare un'email generica da PrestaShop per confermare che il tuo server di posta funziona.
    4.  Se ReCAPTCHA è abilitato, assicurati che sia la "Chiave del sito reCaptcha" che la "Chiave segreta reCaptcha" siano inserite correttamente. Chiavi errate impediranno gli invii.

**D3: Il reCAPTCHA non funziona o visualizzo un messaggio di errore.**

-   **R:** Questo di solito significa che le tue chiavi reCAPTCHA sono errate o non configurate correttamente con Google.
    1.  Vai alla console di amministrazione di Google reCAPTCHA e assicurati che il tuo dominio sia correttamente registrato per reCAPTCHA v2.
    2.  Copia la "Chiave del sito" e la "Chiave segreta" esattamente come fornite da Google e incollale nei campi di configurazione del modulo.
    3.  Svuota la cache di PrestaShop dopo aver apportato modifiche.

**D4: Come posso cambiare il testo sul pulsante "Chiedi informazioni sul prodotto" o sul modulo popup?**

-   **R:** Puoi tradurre le stringhe di testo del modulo direttamente all'interno di PrestaShop. Vai su **Internazionale > Traduzioni**, seleziona "Traduzioni dei moduli installati", scegli il tuo tema e poi seleziona "Chiedi informazioni sul prodotto gratuito". Troverai tutte le stringhe traducibili lì, incluse le etichette dei pulsanti, le etichette dei campi del modulo e i messaggi di conferma.

**D5: Il popup appare strano o non viene visualizzato correttamente sul mio telefono cellulare.**

-   **R:** Sebbene il modulo sia progettato per essere reattivo, i temi personalizzati a volte possono sovrascrivere o entrare in conflitto con il suo stile.
    1.  Svuota la cache del browser e la cache di PrestaShop.
    2.  Se il problema persiste, è probabile che si tratti di un conflitto CSS con il tuo tema. Il tuo webmaster o uno sviluppatore dovrebbe ispezionare la pagina utilizzando gli strumenti di sviluppo del browser per identificare e risolvere il conflitto CSS.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Chiedi informazioni sul prodotto gratuito" segue un modello MVC (Model-View-Controller) standard di PrestaShop, concentrandosi principalmente sull'interazione front-office e sull'amministrazione back-office delle domande inviate. Sfrutta il sistema di hook di PrestaShop per l'integrazione nelle pagine dei prodotti e utilizza controller frontali dedicati per le richieste AJAX e l'invio di moduli. Il componente back-office fornisce una semplice interfaccia di gestione degli elenchi per le domande.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `controllers/front/index.php`
        -   **Nome classe e classe padre:** `AapfreeIndexModuleFrontController` che estende `ModuleFrontController`.
        -   **Responsabilità:** Questo controller probabilmente gestisce la logica di visualizzazione iniziale per il componente front-office del modulo, possibilmente renderizzando il pulsante o preparando i dati per il popup. Potrebbe anche fungere da catch-all per le rotte front-office specifiche del modulo.
    -   `controllers/front/question.php`
        -   **Nome classe e classe padre:** `AapfreeQuestionModuleFrontController` che estende `ModuleFrontController`.
        -   **Responsabilità:** Questo è il controller principale per la gestione dell'invio del modulo "Chiedi informazioni sul prodotto". Riceve i dati POST dal modulo popup, convalida gli input (incluso reCAPTCHA se abilitato), elabora la domanda, invia l'email ai destinatari configurati e memorizza la domanda nel database. Restituisce risposte JSON per le richieste AJAX (es. messaggi di successo/errore).
-   **Controller Admin Back-Office**:

    -   `controllers/admin/AdminAapfreeQuestion.php`
        -   **Nome classe e classe padre:** `AdminAapfreeQuestionController` che estende `ModuleAdminController`.
        -   **Nome scheda ed entità gestita:** Questo controller crea e gestisce la scheda "Domande" sotto il menu "Chiedi informazioni sul prodotto" nel Back Office di PrestaShop. È responsabile della visualizzazione di un elenco (griglia) di tutte le domande inviate, consentendo agli amministratori di visualizzare i dettagli ed eliminare le voci. Interagisce con l'`ObjectModel` `AapfreeQuestion` (se esiste, altrimenti direttamente con il database).
    -   `controllers/admin/index.php`
        -   **Nome classe e classe padre:** Non un controller funzionale nel senso tradizionale.
        -   **Nome scheda ed entità gestita:** Questo file è una misura di sicurezza standard di PrestaShop per impedire l'elenco delle directory. Tipicamente contiene un semplice `header('Location: ../../index.php?controller=AdminHome');` o un reindirizzamento simile, o semplicemente `<?php exit;`. Non gestisce alcuna entità specifica né fornisce una schermata configurabile.

### 4.3 Classi e modelli principali (`classes/`)

Il dossier del modulo indica l'assenza di classi personalizzate nella directory `classes/`. Ciò suggerisce che il modulo potrebbe gestire le interazioni con il database direttamente all'interno dei suoi controller o del file principale del modulo, oppure potrebbe utilizzare un `ObjectModel` generico per `aapfreequestion` se è implicitamente definito.

-   **Modello implicito (probabile):** Dato che `AdminAapfreeQuestionController` gestisce una tabella, esiste un modello `AapfreeQuestion` implicito, anche se non esplicitamente in `classes/`. Questo modello verrebbe mappato alla tabella del database `_aapfree_question`.
    -   **Tabella del database:** `ps_aapfree_question` (o simile, basato sul prefisso del modulo).
    -   **Estende `ObjectModel`:** Sì, implicitamente.
    -   **Campi `$definition` (previsti):** `id_aapfree_question`, `id_product`, `customer_name`, `customer_email`, `question_text`, `date_add`.

### 4.4 Risorse JavaScript (`views/js/`)

-   `aapfree/views/aapfree.js`
    -   **Ambito:** Front-office.
    -   **Listener di eventi:**
        -   Collega gli eventi di clic al pulsante "Chiedi informazioni sul prodotto" (`.aapfree-button`).
        -   Collega gli eventi di invio al modulo "Chiedi informazioni sul prodotto" all'interno del popup (`#aapfree-form`).
        -   Gestisce gli eventi relativi al widget reCAPTCHA (se abilitato).
    -   **Manipolazione del DOM:**
        -   Apre e chiude il popup modale (`#aapfree-modal`).
        -   Popola i dati di riepilogo del prodotto nel popup.
        -   Visualizza messaggi di successo o di errore all'utente dopo l'invio del modulo.
        -   Gestisce gli stati dei campi del modulo (es. disabilitazione del pulsante di invio durante AJAX).
    -   **Chiamate AJAX:**
        -   Invia i dati del modulo a `AapfreeQuestionModuleFrontController` (es. `index.php?fc=module&module=aapfree&controller=question`).
        -   Elabora le risposte JSON dal server.
    -   **Chiamate SDK esterne:** Inizializza e renderizza il widget Google reCAPTCHA v2 se `aapfree_recaptcha` è abilitato, utilizzando `aapfree_recaptcha_sitekey`.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `aapfree/views/aapfree.css`
    -   **Ambito:** Stile del cliente front-office.
    -   **Componenti UI principali e contenitori che stilizza:**
        -   Il pulsante "Chiedi informazioni sul prodotto" (`.aapfree-button`).
        -   Il contenitore del popup modale (`#aapfree-modal`).
        -   Gli elementi del modulo all'interno del popup (campi di input, aree di testo, etichette, caselle di controllo).
        -   Visualizzazione dei messaggi di successo e di errore.
        -   Regolazioni responsive per diverse dimensioni dello schermo.
    -   **Selettori di classi CSS chiave che gli sviluppatori possono sovrascrivere:** `.aapfree-button`, `.aapfree-modal`, `.aapfree-modal-content`, `.aapfree-form-group`, `.aapfree-product-summary`, `.aapfree-success-message`, `.aapfree-error-message`. Gli sviluppatori possono sovrascrivere questi stili nel `custom.css` del loro tema o utilizzando le funzionalità di personalizzazione del tema di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**:
    -   `aapfree/views/aapfree-extra.tpl`
        -   **Hook:** `displayProductAdditionalInfo` (o hook simile per la pagina del prodotto come `displayProductButtons`, `displayProductActions`).
        -   **Output del blocco visivo:** Questo template è responsabile del rendering del pulsante "Chiedi informazioni sul prodotto" sulla pagina del prodotto. Contiene anche la struttura HTML per il modulo popup modale, che è inizialmente nascosto e mostrato tramite JavaScript. Include segnaposto per il riepilogo del prodotto, i campi del modulo, la casella di controllo GDPR e reCAPTCHA.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   `ps_aapfree_question`:
        -   `id_aapfree_question` (INT, PRIMARY KEY, AUTO\_INCREMENT)
        -   `id_product` (INT, Chiave esterna a `ps_product`)
        -   `customer_name` (VARCHAR)
        -   `customer_email` (VARCHAR)
        -   `question_text` (TEXT)
        -   `date_add` (DATETIME)
        -   (Potenzialmente altri campi come `ip_address`, `status`, `id_customer` se implementati)
    -   **Record di configurazione (in `ps_configuration`):**
        -   `AAPFREE_TITLE`: Oggetto dell'email.
        -   `AAPFREE_GDPR`: Stato di conformità GDPR (0/1).
        -   `AAPFREE_GDPRCMS`: ID della pagina CMS per la politica sulla privacy.
        -   `AAPFREE_SUMMARY`: Stato di visualizzazione del riepilogo del prodotto (0/1).
        -   `AAPFREE_RECAPTCHA`: Stato di protezione reCAPTCHA (0/1).
        -   `AAPFREE_RECAPTCHA_SITEKEY`: Chiave del sito Google reCAPTCHA.
        -   `AAPFREE_RECAPTCHA_SECRETKEY`: Chiave segreta Google reCAPTCHA.
        -   `AAPFREE_EMAILSLIST`: Elenco di email dei destinatari separate da virgole.
-   **Tabella degli hook registrati**:

| Nome hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayProductAdditionalInfo` | Nelle pagine dei prodotti, tipicamente sotto la descrizione o il prezzo del prodotto. | Renderizza il pulsante "Chiedi informazioni sul prodotto" e la struttura del popup modale nascosto. |
| `actionAdminControllerSetMedia` | Quando un controller admin carica le sue risorse (CSS/JS). | Inietta CSS (`aapfree.css`) e JavaScript (`aapfree.js`) specifici del modulo nel Back Office per `AdminAapfreeQuestionController`. |
| `displayHeader` | Nella sezione `<head>` di ogni pagina front-office. | Potenzialmente utilizzato per caricare variabili JavaScript globali, CSS o lo script API di Google reCAPTCHA se reCAPTCHA è abilitato. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo "Chiedi informazioni sul prodotto gratuito", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team è dedicato a garantire il buon funzionamento e il continuo miglioramento del tuo modulo.
