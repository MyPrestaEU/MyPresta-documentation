---
title: "Connessione Amazon (registrazione + login) - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Connessione Amazon (registrazione + login) di MyPresta.eu."
sidebar:
  label: "Connessione Amazon (registrazione + login) - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Amazon connect (register + login) su MyPresta.eu](https://mypresta.eu/modules/social-networks/amazon-connect-register-login.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/amazon-connect-register-login/)
>
> ---


# Connessione Amazon (registrazione + login)

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per una comunicazione API sicura.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo di accesso Amazon, dove collegherai il tuo negozio PrestaShop al tuo account sviluppatore Amazon.

- **aml\_ClientID (ID Cliente Amazon)**
  - **Cosa fa questa impostazione:** Questo è un identificatore univoco fornito da Amazon quando registri la tua applicazione (il tuo negozio PrestaShop) con il loro servizio Login with Amazon. Indica ad Amazon quale applicazione sta richiedendo l'autenticazione dell'utente.
  - **Effetto della modifica di questa impostazione:**
    - *Se inserito correttamente:* Il tuo pulsante "Accedi con Amazon" funzionerà correttamente, consentendo ai clienti di autenticarsi tramite il loro account Amazon.
    - *Se errato o vuoto:* Il pulsante "Accedi con Amazon" non funzionerà, o i clienti incontreranno un errore quando cercheranno di usarlo.
  - **Valore consigliato:** L'ID Cliente ottenuto dalla tua Console Sviluppatore Amazon. Questo campo non può essere lasciato vuoto affinché il modulo funzioni.
  - **Scenario / esempio del commerciante:** Hai registrato il tuo negozio PrestaShop come applicazione sulla Console Sviluppatore Amazon. Amazon ti fornisce un "ID Cliente" (es. `amzn1.oauth-client.xxxxxxxxxxxxxxxxxxxxxxxxxxxx`). Devi copiare e incollare questo ID esatto in questo campo.
- **aml\_ClientSecret (Segreto Cliente Amazon)**
  - **Cosa fa questa impostazione:** Questa è una chiave confidenziale anch'essa fornita da Amazon, utilizzata in combinazione con l'ID Cliente per autenticare in modo sicuro la tua applicazione con i server di Amazon. Garantisce che solo la tua applicazione legittima possa richiedere i dati dell'utente.
  - **Effetto della modifica di questa impostazione:**
    - *Se inserito correttamente:* Il tuo modulo può comunicare in modo sicuro con l'API di Amazon per verificare le identità degli utenti.
    - *Se errato o vuoto:* Il processo di autenticazione fallirà, poiché il tuo negozio non può identificarsi in modo sicuro ad Amazon.
  - **Valore consigliato:** Il Segreto Cliente ottenuto dalla tua Console Sviluppatore Amazon. Questo campo non può essere lasciato vuoto affinché il modulo funzioni.
  - **Scenario / esempio del commerciante:** Insieme all'ID Cliente, Amazon ti fornisce anche un "Segreto Cliente" (es. `yyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyy`). Questo segreto deve essere mantenuto confidenziale e inserito accuratamente qui.
- **aml\_RedirectURI (URI di reindirizzamento Amazon)**
  - **Cosa fa questa impostazione:** Questo è l'URL sul tuo negozio PrestaShop dove Amazon reindirizzerà il browser dell'utente *dopo* che questi avrà effettuato l'accesso o autorizzato la tua applicazione sul sito di Amazon. È cruciale per il flusso sicuro del processo di autenticazione.
  - **Effetto della modifica di questa impostazione:**
    - *Se configurato correttamente su entrambi i lati (modulo e Console Sviluppatore Amazon):* Gli utenti vengono reindirizzati senza problemi al tuo negozio dopo l'accesso ad Amazon.
    - *Se errato:* Gli utenti incontreranno un errore dopo aver effettuato l'accesso con Amazon, o non verranno reindirizzati correttamente al tuo negozio. Questo URI deve essere registrato anche nelle impostazioni della tua Console Sviluppatore Amazon per la tua applicazione.
  - **Valore consigliato:** Questo dovrebbe essere tipicamente generato automaticamente dal modulo o essere un URL specifico come `https://iltuonegozio.com/module/amlogin/ajax_amlogin` (verifica il percorso esatto fornito dal modulo o dalla documentazione di Amazon). Assicurati che corrisponda all'URI che hai registrato nella tua Console Sviluppatore Amazon.
  - **Scenario / esempio del commerciante:** Quando configuri la tua applicazione sulla Console Sviluppatore Amazon, ti verrà chiesto di inserire gli "URL di ritorno consentiti". Devi inserire l'URL esatto che questo modulo utilizza per il reindirizzamento (es. `https://www.iltuonegozio.com/module/amlogin/ajax_amlogin`).
- **Visualizza pulsante di accesso Amazon nell'intestazione**
  - **Cosa fa questa impostazione:** Controlla se il pulsante "Accedi con Amazon" appare nella sezione dell'intestazione del tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Se abilitato:* Il pulsante sarà visibile nell'intestazione, offrendo accesso immediato all'accesso Amazon.
    - *Se disabilitato:* Il pulsante non apparirà nell'intestazione.
  - **Valore consigliato:** SÌ, per la massima visibilità e facilità di accesso.
  - **Scenario / esempio del commerciante:** Vuoi che i clienti vedano l'opzione di accesso Amazon non appena arrivano sul tuo sito, quindi la abiliti.
- **Visualizza pulsante di accesso Amazon nella colonna sinistra**
  - **Cosa fa questa impostazione:** Controlla se il pulsante "Accedi con Amazon" appare nella colonna laterale sinistra del tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Se abilitato:* Il pulsante sarà visibile nella colonna sinistra, spesso accanto ad altri blocchi di navigazione o account.
    - *Se disabilitato:* Il pulsante non apparirà nella colonna sinistra.
  - **Valore consigliato:** SÌ, se il tuo tema utilizza una colonna sinistra e desideri una visibilità persistente.
  - **Scenario / esempio del commerciante:** Il tuo negozio ha una colonna sinistra prominente e vuoi offrire l'opzione di accesso Amazon lì mentre i clienti navigano tra le categorie.
- **Visualizza pulsante di accesso Amazon nella colonna destra**
  - **Cosa fa questa impostazione:** Controlla se il pulsante "Accedi con Amazon" appare nella colonna laterale destra del tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Se abilitato:* Il pulsante sarà visibile nella colonna destra.
    - *Se disabilitato:* Il pulsante non apparirà nella colonna destra.
  - **Valore consigliato:** SÌ, se il tuo tema utilizza una colonna destra e desideri una visibilità persistente.
  - **Scenario / esempio del commerciante:** Similmente alla colonna sinistra, se il tuo tema utilizza una colonna destra, potresti posizionare il pulsante lì per visibilità.
- **Visualizza pulsante di accesso Amazon nella pagina del prodotto**
  - **Cosa fa questa impostazione:** Controlla se il pulsante "Accedi con Amazon" appare sulle singole pagine di dettaglio del prodotto.
  - **Effetto della modifica di questa impostazione:**
    - *Se abilitato:* Il pulsante sarà mostrato sulle pagine dei prodotti, potenzialmente vicino al pulsante "Aggiungi al carrello" o alla descrizione del prodotto.
    - *Se disabilitato:* Il pulsante non apparirà sulle pagine dei prodotti.
  - **Valore consigliato:** SÌ, in quanto può incoraggiare l'accesso o la registrazione immediata prima di aggiungere al carrello.
  - **Scenario / esempio del commerciante:** Un cliente sta visualizzando un prodotto e decide di volerlo acquistare. Vedere il pulsante di accesso Amazon gli consente di accedere o creare rapidamente un account prima di procedere al checkout.
- **Visualizza pulsante di accesso Amazon nel piè di pagina**
  - **Cosa fa questa impostazione:** Controlla se il pulsante "Accedi con Amazon" appare nella sezione del piè di pagina del tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Se abilitato:* Il pulsante sarà visibile nel piè di pagina, fornendo un punto di accesso alternativo.
    - *Se disabilitato:* Il pulsante non apparirà nel piè di pagina.
  - **Valore consigliato:** NO, a meno che tu non abbia una ragione di design specifica. Altre posizioni offrono una migliore visibilità.
  - **Scenario / esempio del commerciante:** Vuoi offrire l'opzione di accesso Amazon ma preferisci che non sia troppo prominente, quindi la posizioni nel piè di pagina.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | `aml_ClientID` | Il tuo ID Cliente Amazon | Identificatore univoco per la tua applicazione con Amazon. **Richiesto per la funzionalità.** |
| Pagina di configurazione del modulo | `aml_ClientSecret` | Il tuo Segreto Cliente Amazon | Chiave confidenziale per l'autenticazione sicura con Amazon. **Richiesto per la funzionalità.** |
| Pagina di configurazione del modulo | `aml_RedirectURI` | Generato automaticamente / URL specifico | URL dove Amazon reindirizza gli utenti dopo l'accesso. **Deve corrispondere alla Console Sviluppatore Amazon.** |
| Pagina di configurazione del modulo | Visualizza nell'intestazione | SÌ | Mostra il pulsante nell'intestazione del negozio. |
| Pagina di configurazione del modulo | Visualizza nella colonna sinistra | SÌ | Mostra il pulsante nella barra laterale sinistra. |
| Pagina di configurazione del modulo | Visualizza nella colonna destra | SÌ | Mostra il pulsante nella barra laterale destra. |
| Pagina di configurazione del modulo | Visualizza nella pagina del prodotto | SÌ | Mostra il pulsante sulle singole pagine dei prodotti. |
| Pagina di configurazione del modulo | Visualizza nel piè di pagina | NO | Mostra il pulsante nel piè di pagina del negozio. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Il pulsante di accesso Amazon appare, ma non succede nulla quando ci clicco, oppure ricevo un errore.**
R: Questo di solito indica un problema con il tuo `aml_ClientID`, `aml_ClientSecret` o `aml_RedirectURI`.
- **Controllo 1:** Ricontrolla di aver copiato l'ID Cliente e il Segreto Cliente esattamente dalla tua Console Sviluppatore Amazon nella configurazione del modulo. Anche un singolo errore di carattere causerà un fallimento.
- **Controllo 2:** Verifica che l'`aml_RedirectURI` nella configurazione del modulo corrisponda esattamente a uno degli "URL di ritorno consentiti" che hai registrato nella tua Console Sviluppatore Amazon per la tua applicazione. Presta attenzione a `http` vs `https` e alle barre finali.
- **Controllo 3:** Svuota la cache di PrestaShop (Parametri avanzati > Prestazioni > Svuota cache) e la cache del tuo browser.

**D: I miei clienti vengono reindirizzati ad Amazon, ma poi ricevono un errore o non vengono rimandati al mio negozio.**
R: Questo è quasi certamente un disallineamento di `aml_RedirectURI`. Vai alla tua Console Sviluppatore Amazon, trova la tua applicazione e assicurati che l'elenco degli "URL di ritorno consentiti" contenga l'URL *esatto* che il tuo modulo PrestaShop è configurato per utilizzare. Deve essere una corrispondenza esatta, inclusi `http/https` e qualsiasi sottodirectory.

**D: Il pulsante di accesso Amazon non appare nelle posizioni che ho abilitato.**
R:
- **Controllo 1:** Assicurati che il modulo sia abilitato e configurato correttamente nel Back Office.
- **Controllo 2:** Svuota la cache di PrestaShop (Parametri avanzati > Prestazioni > Svuota cache). A volte, le modifiche al template non si riflettono immediatamente.
- **Controllo 3:** Il tuo tema potrebbe sovrascrivere gli hook standard di PrestaShop. Se il pulsante non appare ancora, potresti aver bisogno di uno sviluppatore web per inserire manualmente la chiamata all'hook del modulo nei file `.tpl` del tuo tema (vedi Sezione 7.6 per i template pertinenti).

**D: Questo modulo funziona con negozi multilingue?**
R: Sì, il modulo dovrebbe ereditare le capacità multilingue di PrestaShop per qualsiasi testo visualizzi. Il processo di accesso ad Amazon stesso è gestito da Amazon e si adatterà tipicamente alle impostazioni della lingua dell'account Amazon dell'utente.

**D: Posso personalizzare l'aspetto del pulsante di accesso Amazon?**
R: Il modulo utilizza gli asset standard del pulsante di accesso Amazon. Sebbene tu non possa modificare il design del pulsante Amazon principale (secondo le linee guida del marchio Amazon), puoi utilizzare CSS personalizzati (vedi Sezione 7.5) per regolare il suo posizionamento, i margini o il contenitore attorno ad esso per adattarlo meglio al tuo tema.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Connessione Amazon (registrazione + login)" integra il servizio Login with Amazon (LWA) di Amazon in PrestaShop. Opera principalmente come un modulo PrestaShop standard, sfruttando gli hook per visualizzare il pulsante di accesso in varie posizioni del front-office. La logica principale per la gestione del flusso OAuth 2.0 di Amazon (reindirizzamento ad Amazon, ricezione del codice di autorizzazione, scambio con un token di accesso e recupero dei dati del profilo utente) è incapsulata all'interno del file principale del modulo e del suo controller AJAX associato. I dati utente ricevuti da Amazon vengono quindi utilizzati per accedere a un cliente PrestaShop esistente o crearne uno nuovo.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller front-end o admin dedicati nella directory `controllers/`. Tutte le richieste AJAX del front-office e la configurazione principale del modulo sono gestite dal file principale del modulo (`amlogin/ajax_amlogin.php`) che funge da pseudo-controller per le azioni AJAX.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non contiene classi o modelli personalizzati in una directory `classes/` dedicata. La logica principale risiede all'interno del file principale del modulo `amlogin/ajax_amlogin.php`.

### 4.4 Risorse JavaScript (`views/js/`)

- `amlogin/js/amlogin.js`
  - **Ambito:** Front-office.
  - **Descrizione:** Questo script è responsabile dell'inizializzazione dell'SDK di accesso Amazon, della gestione degli eventi di clic sul pulsante di accesso Amazon e della gestione del flusso OAuth 2.0. Probabilmente utilizza il metodo `amazon.Login.authorize` per avviare il processo di accesso e gestisce il callback da Amazon. Effettuerà quindi una chiamata AJAX al backend del modulo per elaborare i dati utente di Amazon e accedere al cliente in PrestaShop. Potrebbe anche aggiornare l'interfaccia utente (ad esempio, mostrare lo stato di accesso) dopo un'autenticazione riuscita.

### 4.5 Fogli di stile CSS (`views/css/`)

- `amlogin/css.css`
  - **Ambito:** Front-office.
  - **Descrizione:** Stile generale per il pulsante di accesso Amazon e qualsiasi elemento UI associato. Questo potrebbe contenere regolazioni di layout di base, padding o margini.
- `amlogin/css/amlogin.css`
  - **Ambito:** Front-office.
  - **Descrizione:** Stile specifico per il pulsante di accesso Amazon, potenzialmente inclusi aggiustamenti reattivi o override specifici del tema per PrestaShop 1.6.
- `amlogin/css/amlogin17.css`
  - **Ambito:** Front-office.
  - **Descrizione:** Stile specifico adattato per i temi PrestaShop 1.7, che affronta potenziali differenze nelle strutture dei temi predefiniti o nei framework CSS (ad esempio, Bootstrap 4 vs. Bootstrap 3). Gli sviluppatori possono sovrascrivere questi stili nel `custom.css` del loro tema o creando un tema figlio.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo utilizza un set completo di template Smarty per renderizzare il pulsante di accesso Amazon attraverso vari hook di PrestaShop.

- **Template degli hook (`views/templates/hook/`)**:
  - `amlogin/ajax-amlogin.tpl`: Probabilmente utilizzato per risposte AJAX o contenuti dinamici relativi al processo di accesso Amazon.
  - `amlogin/amlogin.tpl`: Un template generico per il pulsante di accesso Amazon, spesso incluso da altri template degli hook.
  - `amlogin/createAccountForm.tpl`: Renderizza il pulsante di accesso Amazon all'interno del modulo standard di creazione account di PrestaShop.
  - `amlogin/createAccountTop.tpl`: Renderizza il pulsante di accesso Amazon nella parte superiore della pagina di creazione account.
  - `amlogin/dashboardZoneOne.tpl`: Renderizza il pulsante di accesso Amazon nella prima zona della dashboard del cliente (ad esempio, `displayCustomerAccount`).
  - `amlogin/displayCustomerLoginFormAfter.tpl`: Renderizza il pulsante di accesso Amazon dopo il modulo di accesso cliente standard.
  - `amlogin/displayNav.tpl`: Renderizza il pulsante di accesso Amazon nella barra di navigazione (ad esempio, hook `displayNav`).
  - `amlogin/displayPopUpLogin.tpl`: Renderizza il pulsante di accesso Amazon all'interno di un modale di accesso pop-up (se implementato dal tema o dal modulo).
  - `amlogin/footer.tpl`: Renderizza il pulsante di accesso Amazon nel piè di pagina del negozio (hook `displayFooter`).
  - `amlogin/header.tpl`: Renderizza il pulsante di accesso Amazon nell'intestazione del negozio (hook `displayHeader`).
  - `amlogin/home.tpl`: Renderizza il pulsante di accesso Amazon nella homepage (hook `displayHome`).
  - `amlogin/leftcolumn.tpl`: Renderizza il pulsante di accesso Amazon nella barra laterale sinistra (hook `displayLeftColumn`).
  - `amlogin/rightcolumn.tpl`: Renderizza il pulsante di accesso Amazon nella barra laterale destra (hook `displayRightColumn`).
  - `amlogin/shoppingCart.tpl`: Renderizza il pulsante di accesso Amazon all'interno del riepilogo del carrello.
  - `amlogin/shoppingCartExtra.tpl`: Renderizza il pulsante di accesso Amazon in una sezione extra del carrello.
  - `amlogin/top.tpl`: Renderizza il pulsante di accesso Amazon nella sezione superiore della pagina (ad esempio, hook `displayTop`).
  - `amlogin/topColumn.tpl`: Renderizza il pulsante di accesso Amazon nell'area della colonna superiore (hook `displayTopColumn`).

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**: Questo modulo non sembra creare tabelle SQL personalizzate. Le impostazioni di configurazione (ID Cliente, Segreto Cliente, ecc.) sono memorizzate nella tabella `ps_configuration` utilizzando chiavi come `AML_CLIENT_ID`, `AML_CLIENT_SECRET`, `AML_REDIRECT_URI` e `AML_DISPLAY_HEADER`, ecc.
- **Tabella degli hook registrati**:

  | Nome dell'Hook | Tempo di Esecuzione | Scopo Tecnico |
  | --- | --- | --- |
  | `displayHeader` | Nella sezione `<head>` della pagina. | Inietta CSS, JS e potenzialmente il pulsante di accesso Amazon. |
  | `displayNav` | Nella barra di navigazione superiore. | Visualizza il pulsante di accesso Amazon nella navigazione. |
  | `displayLeftColumn` | Nella barra laterale sinistra. | Visualizza il pulsante di accesso Amazon nella colonna sinistra. |
  | `displayRightColumn` | Nella barra laterale destra. | Visualizza il pulsante di accesso Amazon nella colonna destra. |
  | `displayProductButtons` (o simile) | Nella pagina del prodotto, vicino ai pulsanti di azione. | Visualizza il pulsante di accesso Amazon nelle pagine dei prodotti. |
  | `displayFooter` | Nel piè di pagina del negozio. | Visualizza il pulsante di accesso Amazon nel piè di pagina. |
  | `displayCustomerAccount` | Nella dashboard dell'account del cliente. | Visualizza il pulsante di accesso Amazon nell'area dell'account cliente. |
  | `displayCustomerLoginFormAfter` | Dopo il modulo di accesso standard. | Integra il pulsante di accesso Amazon nella pagina di accesso. |
  | `displayBeforeBodyClosingTag` | Prima del tag `</body>`. | Potrebbe iniettare JavaScript per l'SDK Amazon o i pop-up. |
  | `displayShoppingCart` | Nella pagina di riepilogo del carrello. | Visualizza il pulsante di accesso Amazon nel carrello. |
  | `displayShoppingCartExtra` | Area di contenuto extra nel carrello. | Visualizza il pulsante di accesso Amazon in un'area aggiuntiva del carrello. |
  | `displayTop` | Parte superiore della pagina, sopra l'intestazione. | Visualizza il pulsante di accesso Amazon nella sezione più in alto. |
  | `displayTopColumn` | Nell'area della colonna superiore principale. | Visualizza il pulsante di accesso Amazon nella colonna superiore. |
  | `displayHome` | Nella homepage del negozio. | Visualizza il pulsante di accesso Amazon nella homepage. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il tuo modulo "Connessione Amazon (registrazione + login)", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a garantire che il tuo modulo funzioni perfettamente e si integri senza problemi con il tuo negozio PrestaShop.
