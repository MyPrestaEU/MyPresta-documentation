---
title: "Google Login Connect - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Google Login Connect di MyPresta.eu."
sidebar:
  label: "Google Login Connect"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Google Login Connect su MyPresta.eu](https://mypresta.eu/modules/social-networks/google-login-connect.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/google-login-connect/)
>
> ---


# Google Login Connect

## 1. Requisiti e Compatibilità

-   **Versioni PrestaShop supportate**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **Compatibilità PHP**: PHP 5.6 - 8.5
-   **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono in genere richieste per una comunicazione sicura con l'API di Google.

## 2. Panoramica completa della configurazione (ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Google Login Connect)

Questa è la schermata di configurazione principale in cui imposterai le tue credenziali API di Google e deciderai dove appare il pulsante "Accedi con Google" nel tuo negozio.

#### **Credenziali API di Google**

Prima di configurare il modulo, devi creare un progetto API di Google e ottenere il tuo ID client. Questo è fondamentale affinché il modulo possa comunicare in modo sicuro con Google.

**Come ottenere il tuo ID client Google:**
1.  Vai alla [Google Cloud Console](https://console.cloud.google.com/).
2.  Crea un nuovo progetto o selezionane uno esistente.
3.  Vai su **API e servizi > Credenziali**.
4.  Fai clic su **"Crea credenziali"** e scegli **"ID client OAuth"**.
5.  Seleziona **"Applicazione web"** come tipo di applicazione.
6.  Sotto **"Origini JavaScript autorizzate"**, aggiungi l'URL del tuo negozio (ad esempio, `https://www.iltuonegozio.com`).
7.  Sotto **"URI di reindirizzamento autorizzati"**, aggiungi l'URL del tuo negozio seguito dal percorso di callback del modulo (ad esempio, `https://www.iltuonegozio.com/module/glogin/index`).
8.  Dopo la creazione, Google ti fornirà un **ID client**. Copia questo valore.

-   **ID client Google (ggl_appid)**
    -   **Cosa fa questa impostazione:** Questo è l'identificatore univoco per la tua applicazione (il tuo negozio PrestaShop) che Google utilizza per riconoscere le tue richieste di accesso. È essenziale affinché la funzionalità "Accedi con Google" funzioni.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se inserito correttamente:* I tuoi pulsanti di accesso Google funzioneranno, consentendo ai clienti di autenticarsi tramite Google.
        -   *Se errato o vuoto:* I pulsanti di accesso Google non funzioneranno, o i clienti incontreranno errori quando tenteranno di accedere con Google.
    -   **Valore consigliato:** L'ID client ottenuto dalla tua Google Cloud Console.
    -   **Scenario/esempio del commerciante:** Hai appena creato il tuo progetto API di Google e hai ricevuto `1234567890-abcdefg.apps.googleusercontent.com`. Devi incollare questa stringa esatta qui.

#### **Impostazioni account cliente**

-   **Gruppo clienti per utenti Google (glogin_groupid)**
    -   **Cosa fa questa impostazione:** Determina a quale gruppo di clienti verranno assegnati automaticamente i nuovi utenti che si registrano tramite Google.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se impostato su "Cliente" (predefinito):* I nuovi utenti Google saranno clienti standard.
        -   *Se impostato su "Visitatore" o un altro gruppo personalizzato:* I nuovi utenti Google verranno assegnati a quel gruppo specifico, influenzando potenzialmente il loro accesso a sconti, prezzi speciali o contenuti.
    -   **Valore consigliato:** "Cliente" (o il tuo gruppo clienti predefinito).
    -   **Scenario/esempio del commerciante:** Vuoi che tutte le nuove registrazioni Google facciano parte del tuo gruppo "Clienti all'ingrosso" per concedere loro automaticamente i prezzi B2B. Selezioneresti "Clienti all'ingrosso" dal menu a discesa.

-   **Invia email di benvenuto ai nuovi utenti Google (glogin_semail)**
    -   **Cosa fa questa impostazione:** Controlla se PrestaShop invia un'email di benvenuto standard ai clienti che si registrano utilizzando il proprio account Google.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se abilitato (SÌ):* I nuovi utenti Google riceveranno l'email di benvenuto standard di PrestaShop, confermando la creazione del loro account.
        -   *Se disabilitato (NO):* I nuovi utenti Google non riceveranno un'email di benvenuto.
    -   **Valore consigliato:** SÌ (per confermare la creazione dell'account e fornire una buona prima impressione).
    -   **Scenario/esempio del commerciante:** Vuoi assicurarti che i nuovi clienti si sentano benvenuti e che i dettagli del loro account siano confermati, quindi abiliti questa opzione.

#### **Opzioni di visualizzazione**

-   **Stile del pulsante di accesso Google (glogin_button_style)**
    -   **Cosa fa questa impostazione:** Ti consente di scegliere lo stile visivo del pulsante "Accedi con Google". Le opzioni includono in genere diverse dimensioni, forme o schemi di colore forniti da Google.
    -   **Effetto della modifica di questa impostazione:** Modifica l'aspetto di tutti i pulsanti di accesso Google nel tuo negozio.
    -   **Valore consigliato:** Scegli lo stile che meglio si adatta al design del tuo negozio.
    -   **Scenario/esempio del commerciante:** Il tuo tema utilizza pulsanti grandi e arrotondati. Selezioneresti uno stile di pulsante che corrisponda a questa estetica per coerenza.

-   **Visualizza il pulsante di accesso Google in pop-up (ggl_popuplogin)**
    -   **Cosa fa questa impostazione:** Se abilitato, quando un cliente fa clic su un link di accesso, apparirà una finestra pop-up con l'opzione di accesso Google, invece di reindirizzarli a una pagina di accesso completa.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se abilitato (SÌ):* Fornisce un'esperienza di accesso più rapida e meno invasiva tramite un pop-up modale.
        -   *Se disabilitato (NO):* I clienti verranno reindirizzati alla pagina di accesso standard.
    -   **Valore consigliato:** SÌ (per un'esperienza utente moderna e senza interruzioni).
    -   **Scenario/esempio del commerciante:** Vuoi mantenere i clienti sulla pagina corrente il più possibile, quindi abiliti l'accesso pop-up.

#### **Posizionamento del pulsante (Selezione hook)**

Queste impostazioni controllano dove appare il pulsante "Accedi con Google" nel tuo negozio. Puoi abilitare o disabilitare il pulsante per vari hook di visualizzazione di PrestaShop.

-   **Visualizza nell'intestazione (ggl_top)**
    -   **Cosa fa questa impostazione:** Controlla la visibilità del pulsante di accesso Google nella sezione dell'intestazione del tuo negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Abilitato:* Il pulsante appare nell'intestazione (ad esempio, vicino a "Il mio account" o "Accedi").
        -   *Disabilitato:* Il pulsante è nascosto dall'intestazione.
    -   **Valore consigliato:** SÌ (per un facile accesso da qualsiasi pagina).

-   **Visualizza nella barra di navigazione (ggl_displayNav, ggl_displayNav1, ggl_displayNav2)**
    -   **Cosa fanno queste impostazioni:** Controllano la visibilità del pulsante di accesso Google in diverse posizioni della barra di navigazione, a seconda della tua versione di PrestaShop e del tema. `displayNav` è comune per i temi più vecchi, mentre `displayNav1` e `displayNav2` sono spesso utilizzati in PrestaShop 1.7+ per la navigazione in cima alla pagina.
    -   **Effetto della modifica di questa impostazione:**
        -   *Abilitato:* Il pulsante appare nella barra di navigazione selezionata.
        -   *Disabilitato:* Il pulsante è nascosto da quella barra di navigazione.
    -   **Valore consigliato:** Abilita uno o due che si adattano meglio al tuo tema, evitando la ridondanza.

-   **Visualizza nel carrello (ggl_shoppingCart, ggl_shoppingCartExtra)**
    -   **Cosa fanno queste impostazioni:** Controllano la visibilità del pulsante di accesso Google nella pagina del carrello. `ggl_shoppingCart` è in genere per il contenuto principale del carrello, mentre `ggl_shoppingCartExtra` potrebbe essere per blocchi o riepiloghi aggiuntivi.
    -   **Effetto della modifica di questa impostazione:**
        -   *Abilitato:* Il pulsante appare nella pagina del carrello, consentendo un accesso rapido prima del checkout.
        -   *Disabilitato:* Il pulsante è nascosto dalla pagina del carrello.
    -   **Valore consigliato:** SÌ (per incoraggiare l'accesso rapido e ridurre l'abbandono).

-   **Visualizza nella colonna sinistra (ggl_leftcolumn)**
    -   **Cosa fa questa impostazione:** Controlla la visibilità del pulsante di accesso Google nella barra laterale sinistra del tuo negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Abilitato:* Il pulsante appare nella colonna sinistra.
        -   *Disabilitato:* Il pulsante è nascosto dalla colonna sinistra.
    -   **Valore consigliato:** SÌ (se il tuo tema utilizza una colonna sinistra e desideri un posizionamento prominente).

-   **Visualizza nella colonna destra (ggl_rightoclumn)**
    -   **Cosa fa questa impostazione:** Controlla la visibilità del pulsante di accesso Google nella barra laterale destra del tuo negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Abilitato:* Il pulsante appare nella colonna destra.
        -   *Disabilitato:* Il pulsante è nascosto dalla colonna destra.
    -   **Valore consigliato:** SÌ (se il tuo tema utilizza una colonna destra e desideri un posizionamento prominente).

-   **Visualizza nella homepage (ggl_home)**
    -   **Cosa fa questa impostazione:** Controlla la visibilità del pulsante di accesso Google nella homepage del tuo negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Abilitato:* Il pulsante appare nella homepage.
        -   *Disabilitato:* Il pulsante è nascosto dalla homepage.
    -   **Valore consigliato:** SÌ (per la massima visibilità e un accesso rapido per i nuovi visitatori).

-   **Visualizza dopo il modulo di accesso cliente (ggl_displayCustomerLoginFormAfter)**
    -   **Cosa fa questa impostazione:** Controlla la visibilità del pulsante di accesso Google direttamente dopo il modulo di accesso cliente standard di PrestaShop (ad esempio, nella pagina `/my-account`).
    -   **Effetto della modifica di questa impostazione:**
        -   *Abilitato:* Il pulsante appare sotto il modulo di accesso tradizionale.
        -   *Disabilitato:* Il pulsante è nascosto da questa posizione.
    -   **Valore consigliato:** SÌ (questa è una posizione primaria per i pulsanti di accesso social).

-   **Visualizza nel modulo di creazione account (ggl_createAccountForm, ggl_createAccountTop)**
    -   **Cosa fanno queste impostazioni:** Controllano la visibilità del pulsante di accesso Google nella pagina di creazione dell'account cliente. `ggl_createAccountForm` lo posiziona tipicamente all'interno o vicino al modulo, mentre `ggl_createAccountTop` lo posiziona nella parte superiore della pagina di creazione dell'account.
    -   **Effetto della modifica di questa impostazione:**
        -   *Abilitato:* Il pulsante appare nella pagina di creazione dell'account, offrendo una rapida alternativa di registrazione.
        -   *Disabilitato:* Il pulsante è nascosto da questa pagina.
    -   **Valore consigliato:** SÌ (per semplificare la registrazione di nuovi clienti).

-   **Visualizza nella colonna superiore (ggl_topColumn)**
    -   **Cosa fa questa impostazione:** Controlla la visibilità del pulsante di accesso Google nell'hook `displayTopColumn`, spesso utilizzato per banner o contenuti appena sotto l'intestazione.
    -   **Effetto della modifica di questa impostazione:**
        -   *Abilitato:* Il pulsante appare nella colonna superiore.
        -   *Disabilitato:* Il pulsante è nascosto dalla colonna superiore.
    -   **Valore consigliato:** Considera in base al layout del tuo tema; spesso meno critico rispetto ad altre posizioni.

-   **Visualizza informazioni personali in alto (ggl_displayPersonalInformationTop)**
    -   **Cosa fa questa impostazione:** Controlla la visibilità del pulsante di accesso Google nella pagina "Le mie informazioni personali", di solito quando un cliente è già loggato. Questo potrebbe essere meno comune per un pulsante di accesso ma potrebbe essere utilizzato per il collegamento dell'account.
    -   **Effetto della modifica di questa impostazione:**
        -   *Abilitato:* Il pulsante appare nella pagina delle informazioni personali.
        -   *Disabilitato:* Il pulsante è nascosto da questa pagina.
    -   **Valore consigliato:** NO (tipicamente non un punto di accesso primario).

#### **Altre impostazioni (Interne/Legacy)**

-   **mypresta_updates, update_, updatev_**: Queste sono impostazioni interne utilizzate da MyPresta.eu per i controlli degli aggiornamenti del modulo e la gestione delle versioni. Non dovresti modificarle.
-   **PS_CUSTOMER_GROUP, PS_CUSTOMER_CREATION_EMAIL, PS_CART_FOLLOWING**: Queste sono variabili di configurazione standard di PrestaShop a cui il modulo potrebbe fare riferimento ma che in genere non consente la modifica diretta tramite la sua interfaccia. Riflettono le impostazioni principali del tuo negozio.
-   **glogin_identity**: Questo è probabilmente un identificatore interno utilizzato dal modulo. Non modificare.
-   **ggl_**: Qualsiasi altra impostazione che inizia con `ggl_` e non è esplicitamente elencata sopra è probabilmente un flag interno o un'opzione legacy. È meglio lasciarle ai loro valori predefiniti a meno che non sia diversamente indicato dal supporto.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
|---|---|---|---|
| Configurazione modulo | ID client Google | Il tuo ID client Google | Essenziale per la funzionalità di accesso Google. |
| Configurazione modulo | Gruppo clienti per utenti Google | Cliente | Assegna i nuovi utenti Google a un gruppo clienti specifico. |
| Configurazione modulo | Invia email di benvenuto ai nuovi utenti Google | SÌ | Invia un'email di benvenuto alle nuove registrazioni Google. |
| Configurazione modulo | Stile del pulsante di accesso Google | (Scegli il migliore) | Modifica l'aspetto visivo del pulsante. |
| Configurazione modulo | Visualizza il pulsante di accesso Google in pop-up | SÌ | Abilita l'accesso pop-up per una UX più fluida. |
| Configurazione modulo | Visualizza nell'intestazione (ggl_top) | SÌ | Mostra il pulsante nell'intestazione del negozio. |
| Configurazione modulo | Visualizza nella barra di navigazione (ggl_displayNav, ggl_displayNav1, ggl_displayNav2) | SÌ (se necessario) | Mostra il pulsante in varie barre di navigazione. |
| Configurazione modulo | Visualizza nel carrello (ggl_shoppingCart, ggl_shoppingCartExtra) | SÌ | Mostra il pulsante nella pagina del carrello. |
| Configurazione modulo | Visualizza nella colonna sinistra (ggl_leftcolumn) | SÌ (se applicabile) | Mostra il pulsante nella barra laterale sinistra. |
| Configurazione modulo | Visualizza nella colonna destra (ggl_rightoclumn) | SÌ (se applicabile) | Mostra il pulsante nella barra laterale destra. |
| Configurazione modulo | Visualizza nella homepage (ggl_home) | SÌ | Mostra il pulsante nella homepage del negozio. |
| Configurazione modulo | Visualizza dopo il modulo di accesso cliente (ggl_displayCustomerLoginFormAfter) | SÌ | Mostra il pulsante sotto il modulo di accesso standard. |
| Configurazione modulo | Visualizza nel modulo di creazione account (ggl_createAccountForm, ggl_createAccountTop) | SÌ | Mostra il pulsante nella pagina di creazione dell'account. |
| Configurazione modulo | Visualizza nella colonna superiore (ggl_topColumn) | NO (o se necessario) | Mostra il pulsante nell'hook della colonna superiore. |
| Configurazione modulo | Visualizza informazioni personali in alto (ggl_displayPersonalInformationTop) | NO | Mostra il pulsante nella pagina delle informazioni personali (meno comune). |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Il pulsante di accesso Google appare, ma non succede nulla quando ci clicco, oppure ricevo un errore.**
R: Questo è quasi sempre un problema con il tuo ID client Google o gli URI di reindirizzamento autorizzati nella tua Google Cloud Console.
    *   **Controlla l'ID client:** Ricontrolla che l'`ID client Google` inserito nella configurazione del modulo sia esattamente quello fornito da Google, senza spazi aggiuntivi.
    *   **Controlla gli URI di reindirizzamento autorizzati:** Nella tua Google Cloud Console, assicurati di aver aggiunto `https://www.iltuonegozio.com/module/glogin/index` (sostituisci `iltuonegozio.com` con il tuo dominio effettivo) all'elenco degli "URI di reindirizzamento autorizzati". Deve essere una corrispondenza esatta, incluso `https://` se il tuo negozio utilizza SSL.
    *   **Controlla le origini JavaScript autorizzate:** Assicurati anche che l'URL principale del tuo negozio (ad esempio, `https://www.iltuonegozio.com`) sia elencato sotto "Origini JavaScript autorizzate".

**D: I nuovi clienti si stanno registrando con Google, ma non ricevono un'email di benvenuto.**
R: Controlla l'impostazione "Invia email di benvenuto ai nuovi utenti Google" nella configurazione del modulo. Assicurati che sia impostata su "SÌ". Inoltre, verifica che le impostazioni generali di posta elettronica del tuo negozio PrestaShop siano configurate correttamente e che altre email transazionali (come le conferme d'ordine) vengano inviate con successo.

**D: Il pulsante di accesso Google non appare in una posizione specifica (ad esempio, l'intestazione) anche se l'ho abilitato.**
R:
    *   **Svuota la cache:** Per prima cosa, svuota la cache di PrestaShop (**Parametri avanzati > Prestazioni > Svuota la cache**).
    *   **Posizione del modulo:** Vai su **Design > Posizioni** (o **Moduli > Posizioni** nelle versioni precedenti). Cerca il modulo `glogin`. Assicurati che sia agganciato a `displayHeader`, `displayNav` o altri hook pertinenti che hai abilitato. A volte, i temi potrebbero sovrascrivere i comportamenti predefiniti degli hook.
    *   **Conflitti con il tema:** Il tuo tema potrebbe avere modelli personalizzati che non richiamano esplicitamente tutti gli hook standard di PrestaShop. Se il pulsante non appare dopo aver svuotato la cache e controllato le posizioni del modulo, potrebbe essere necessario che un webmaster ispezioni i file `.tpl` del tuo tema.

**D: I clienti possono collegare un account PrestaShop esistente al loro account Google?**
R: Questo modulo facilita principalmente le nuove registrazioni e gli accessi. Se un cliente accede con Google e un account con quell'email esiste già nel tuo negozio PrestaShop, il modulo li accederà tipicamente al loro account esistente. Di solito non offre una funzione separata di "collega account esistente" dopo l'accesso, ma corrisponde intelligentemente per email.

**D: Voglio cambiare il testo o l'aspetto del pulsante oltre le opzioni del modulo.**
R: Il modulo fornisce stili di pulsante Google standard. Per una personalizzazione avanzata (ad esempio, cambiare testo, aggiungere icone personalizzate), avresti bisogno di CSS personalizzato e potenzialmente modifiche JavaScript, che dovrebbero essere gestite da uno sviluppatore web.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster che lavorano con il modulo Google Login Connect.

### 4.1 Panoramica dell'architettura
Il modulo `Google Login Connect` segue un'architettura standard per i moduli PrestaShop, sfruttando principalmente i controller frontali per la gestione del callback OAuth 2.0 e vari hook di visualizzazione per l'iniezione dei pulsanti. Si basa sulla classe `Configuration` di PrestaShop per l'archiviazione delle impostazioni e su `Customer` `ObjectModel` per la gestione degli utenti. Il modulo si integra con l'API JavaScript di Google per l'autenticazione lato client, che quindi invia il token a un controller frontale del modulo per la verifica lato server e la creazione della sessione utente.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:
    *   `glogin/controllers/front/index.php`
        *   **Nome classe e classe padre**: `GloginIndexModuleFrontController` estende `ModuleFrontController`
        *   **Responsabilità**: Questo è l'endpoint di callback primario per il flusso OAuth 2.0 di Google. Dopo che un utente si autentica con Google, Google reindirizza a questo controller. Riceve il token ID di Google, lo verifica, estrae le informazioni dell'utente (email, nome) e quindi accede a un cliente PrestaShop esistente o ne crea uno nuovo. Gestisce la gestione della sessione e reindirizza l'utente al negozio.
    *   `glogin/controllers/front/loginloader.php`
        *   **Nome classe e classe padre**: `GloginLoginloaderModuleFrontController` estende `ModuleFrontController`
        *   **Responsabilità**: Questo controller probabilmente serve un piccolo pezzo di JavaScript o inizializza il client API di Google sulle pagine in cui viene visualizzato il pulsante di accesso. Potrebbe essere utilizzato per caricare dinamicamente la Google Platform Library (`platform.js`) o per fornire variabili di configurazione (come `ggl_appid`) al JavaScript front-end.

-   **Controller di amministrazione Back-Office**:
    *   Nessuno. Tutta la configurazione è gestita tramite il metodo `getContent()` del modulo principale.

### 4.3 Classi e modelli principali (`classes/`)
-   Non sono definite classi `ObjectModel` personalizzate all'interno della directory `classes/`. Il modulo interagisce direttamente con la classe `Customer` `ObjectModel` e `Configuration` di PrestaShop.
-   Il file del modulo principale `glogin/glogin.php` funge da classe principale, estendendo `Module` e contenendo tutta la logica di installazione, disinstallazione e configurazione.

### 4.4 Risorse JavaScript (`views/js/`)

-   `glogin/views/js/glogin.js`
    *   **Ambito**: Front-office.
    *   **Responsabilità**: Questo script è responsabile dell'inizializzazione della libreria client Google Sign-In. Probabilmente include:
        *   Caricamento della Google Platform Library (`https://apis.google.com/js/platform.js`).
        *   Rendering del pulsante "Accedi con Google" utilizzando `gapi.signin2.render()`.
        *   Gestione della funzione di callback `onSignIn`, che viene attivata dopo un accesso Google riuscito. Questo callback estrae il token ID e lo invia tramite AJAX al controller frontale del modulo (`index.php`) per l'elaborazione lato server.
        *   Potenzialmente gestisce la funzionalità di accesso pop-up (`ggl_popuplogin`), visualizzando dinamicamente il pulsante Google all'interno di un modale.
        *   Listener di eventi per i clic sui pulsanti di accesso Google.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `glogin/css.css`
    *   **Ambito**: Front-office.
    *   **Responsabilità**: Stile generale per i pulsanti di accesso Google e potenzialmente qualsiasi contenitore o pop-up personalizzato introdotto dal modulo. Può contenere regolazioni di layout di base.
-   `glogin/views/css/glogin.css`
    *   **Ambito**: Front-office.
    *   **Responsabilità**: Simile a `css.css`, probabilmente contiene lo stile principale per i pulsanti di accesso Google, assicurando che siano correttamente allineati e dimensionati all'interno di vari temi PrestaShop.
-   `glogin/views/css/glogin17-new.css`
    *   **Ambito**: Front-office.
    *   **Responsabilità**: Regole CSS specifiche adattate per i temi PrestaShop 1.7+, che affrontano potenziali differenze di layout o override di stile richiesti per le versioni più recenti. Ciò potrebbe includere regolazioni Flexbox o Grid.
-   `glogin/views/css/glogin17.css`
    *   **Ambito**: Front-office.
    *   **Responsabilità**: Un altro foglio di stile specifico per PrestaShop 1.7.x, che potenzialmente contiene stili aggiuntivi o alternativi rispetto a `glogin17-new.css`, a seconda dell'esatta struttura del tema.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo sfrutta numerosi template per iniettare il pulsante di accesso Google in vari hook di PrestaShop. La maggior parte di questi template conterrà una chiamata alla logica di rendering del pulsante Google Sign-In (ad esempio, `<div class="g-signin2" data-onsuccess="onSignIn"></div>`) e potenzialmente del codice HTML circostante per lo stile.

-   **Template degli hook (`views/templates/hook/`)**:
    *   `glogin/views/templates/createAccountForm.tpl`: Renderizza il pulsante Google all'interno del modulo di creazione dell'account cliente.
    *   `glogin/views/templates/createAccountTop.tpl`: Renderizza il pulsante Google nella parte superiore della pagina di creazione dell'account.
    *   `glogin/views/templates/dashboardZoneOne.tpl`: Renderizza il pulsante Google nell'hook `dashboardZoneOne` (meno comune per l'accesso, eventualmente per l'integrazione della dashboard di amministrazione o un tema specifico).
    *   `glogin/views/templates/displayCustomerLoginFormAfter.tpl`: Renderizza il pulsante Google direttamente dopo il modulo di accesso cliente standard.
    *   `glogin/views/templates/displayNav.tpl`: Renderizza il pulsante Google nell'hook `displayNav` (spesso navigazione superiore).
    *   `glogin/views/templates/displayNav1.tpl`: Renderizza il pulsante Google nell'hook `displayNav1` (navigazione PrestaShop 1.7+).
    *   `glogin/views/templates/displayNav2.tpl`: Renderizza il pulsante Google nell'hook `displayNav2` (navigazione PrestaShop 1.7+).
    *   `glogin/views/templates/displayPopUpLogin.tpl`: Contiene la struttura HTML per il modale di accesso pop-up, incluso il pulsante Google.
    *   `glogin/views/templates/footer.tpl`: Renderizza il pulsante Google nell'hook `displayFooter`.
    *   `glogin/views/templates/glogin.tpl`: Un template generico, probabilmente utilizzato come fallback o per la logica di rendering interna.
    *   `glogin/views/templates/header.tpl`: Renderizza il pulsante Google nell'hook `displayHeader`.
    *   `glogin/views/templates/home.tpl`: Renderizza il pulsante Google nell'hook `displayHome`.
    *   `glogin/views/templates/leftcolumn.tpl`: Renderizza il pulsante Google nell'hook `displayLeftColumn`.
    *   `glogin/views/templates/rightcolumn.tpl`: Renderizza il pulsante Google nell'hook `displayRightColumn`.
    *   `glogin/views/templates/shoppingCart.tpl`: Renderizza il pulsante Google nell'hook `displayShoppingCart`.
    *   `glogin/views/templates/shoppingCartExtra.tpl`: Renderizza il pulsante Google nell'hook `displayShoppingCartExtra`.
    *   `glogin/views/templates/top.tpl`: Renderizza il pulsante Google nell'hook `displayTop`.
    *   `glogin/views/templates/topColumn.tpl`: Renderizza il pulsante Google nell'hook `displayTopColumn`.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    *   Il modulo non crea tabelle SQL personalizzate.
    *   Le impostazioni di configurazione sono archiviate nella tabella `ps_configuration` utilizzando chiavi come `GLOGIN_GROUPID`, `GLOGIN_SEMAIL`, `GGL_APPID`, `GGL_POPUP_LOGIN`, `GGL_BUTTON_STYLE` e vari flag `GGL_DISPLAY[HOOK_NAME]`.

-   **Tabella degli hook registrati**:

| Nome hook | Tempistica di esecuzione | Scopo tecnico |
|---|---|---|
| `displayHeader` | Nella sezione `<head>` o all'inizio del `<body>` | Inietta CSS, JS e potenzialmente il pulsante Google nell'intestazione. |
| `displayFooter` | Alla fine del `<body>` | Inietta il pulsante Google nel piè di pagina. |
| `displayHome` | Nell'area del contenuto della homepage | Inietta il pulsante Google nella homepage. |
| `displayShoppingCart` | Nella pagina del carrello | Inietta il pulsante Google nella pagina del carrello. |
| `displayRightColumn` | Nella barra laterale destra | Inietta il pulsante Google nella colonna destra. |
| `displayCustomerLoginFormAfter` | Dopo il modulo di accesso cliente standard | Inietta il pulsante Google per l'accesso alternativo. |
| `displayNav` | Nella barra di navigazione principale (temi più vecchi) | Inietta il pulsante Google nella navigazione. |
| `displayCreateAccountTop` | Nella parte superiore della pagina di creazione dell'account | Inietta il pulsante Google per la registrazione rapida. |
| `displayTop` | Nella sezione superiore della pagina (spesso sopra l'intestazione) | Inietta il pulsante Google nella sezione superiore. |
| `displayNav2` | In una barra di navigazione secondaria (PS 1.7+) | Inietta il pulsante Google nella navigazione. |
| `displayShoppingCartExtra` | Area di contenuto aggiuntiva nella pagina del carrello | Inietta il pulsante Google nella pagina del carrello. |
| `displayTopColumn` | Nell'area del contenuto sotto l'intestazione (spesso per banner) | Inietta il pulsante Google nella colonna superiore. |
| `displayNav1` | In una barra di navigazione primaria (PS 1.7+) | Inietta il pulsante Google nella navigazione. |
| `dashboardZoneOne` | Nella prima zona della dashboard di amministrazione | Potenzialmente per informazioni lato amministratore o un pulsante specifico. |
| `displayLeftColumn` | Nella barra laterale sinistra | Inietta il pulsante Google nella colonna sinistra. |

## 5. Supporto ufficiale e aggiornamenti
Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Assicurati di utilizzare l'ultima versione compatibile del modulo per il tuo negozio PrestaShop.
