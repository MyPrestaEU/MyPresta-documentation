---
title: "Connessione tramite login PayPal - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop di connessione tramite login PayPal di MyPresta.eu."
sidebar:
  label: "Connessione tramite login PayPal - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo PayPal login connect su MyPresta.eu](https://mypresta.eu/modules/social-networks/paypal-login-connect.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/paypal-login-connect/)
>
> ---


# Connessione tramite login PayPal

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, fai clic su "Configura" accanto al modulo "Connessione tramite login PayPal" per accedere alle sue impostazioni.

#### **Credenziali API PayPal**

Queste impostazioni collegano il tuo negozio al tuo account sviluppatore PayPal, consentendo al modulo di autenticare gli utenti in modo sicuro.

- **Cosa fa questa impostazione:** Questi campi richiedono il tuo ID Cliente e il Segreto Cliente univoci ottenuti dal tuo account Sviluppatore PayPal. Queste credenziali sono vitali affinché il tuo negozio possa comunicare con il servizio di accesso di PayPal.
- **Effetto della modifica di questa impostazione:**
  - *Se inseriti correttamente:* Il pulsante "Accedi con PayPal" funzionerà, consentendo ai clienti di accedere.
  - *Se errati o vuoti:* Il modulo non sarà in grado di connettersi a PayPal e la funzione di accesso fallirà o non apparirà.
- **Valore consigliato:** Inserisci l'ID Cliente e il Segreto Cliente esatti forniti da PayPal.
- **Scenario/esempio per il commerciante:** Hai creato un account Sviluppatore PayPal e configurato un'app "Accedi con PayPal". PayPal ti fornisce un ID Cliente (una lunga stringa di caratteri) e un Segreto Cliente (un'altra lunga stringa sicura). Li copi e incolli nei rispettivi campi qui.

#### **Abilita login PayPal**

Questo è l'interruttore principale per la funzionalità del modulo.

- **Cosa fa questa impostazione:** Controlla se la funzione "Accedi con PayPal" è attiva e visibile sul tuo negozio.
- **Effetto della modifica di questa impostazione:**
  - *Se abilitato (SÌ):* I pulsanti di accesso PayPal appariranno nelle posizioni selezionate e la funzionalità sarà attiva.
  - *Se disabilitato (NO):* I pulsanti di accesso PayPal saranno nascosti e i clienti non potranno utilizzare questa funzione.
- **Valore consigliato:** SÌ
- **Scenario/esempio per il commerciante:** Hai finito di configurare il modulo e vuoi renderlo attivo per i tuoi clienti. Imposti questo valore su SÌ. Se hai bisogno di disabilitarlo temporaneamente per manutenzione, puoi impostarlo su NO.

#### **Mostra pulsante in**

Questa sezione ti consente di scegliere dove apparirà il pulsante "Accedi con PayPal" nel tuo negozio.

- **Cosa fa questa impostazione:** Determina le posizioni specifiche (hook) in cui il pulsante di accesso PayPal verrà visualizzato nel tuo front office.
- **Effetto della modifica di questa impostazione:**
  - *Quando una posizione è selezionata:* Il pulsante di accesso PayPal apparirà in quell'area specifica del tuo negozio.
  - *Quando una posizione non è selezionata:* Il pulsante non verrà visualizzato in quell'area.
- **Valore consigliato:** Seleziona le posizioni più rilevanti per l'accesso/registrazione del cliente, come `displayNav` (navigazione superiore), `displayCustomerLoginFormAfter` (dopo il modulo di accesso standard) e `createAccountForm` (nella pagina di registrazione).
- **Scenario/esempio per il commerciante:** Vuoi che il pulsante sia facilmente accessibile nell'intestazione e nella pagina di accesso principale. Selezioneresti `displayNav` e `displayCustomerLoginFormAfter`. Se il tuo tema ha un accesso pop-up personalizzato, potresti anche selezionare `displayPopUpLogin`.

#### **Stile pulsante**

Personalizza l'aspetto visivo del pulsante di accesso PayPal.

- **Cosa fa questa impostazione:** Ti consente di selezionare tra diversi stili predefiniti per il pulsante "Accedi con PayPal" per abbinarlo al design del tuo negozio o alle linee guida del marchio PayPal.
- **Effetto della modifica di questa impostazione:** Modifica l'aspetto visivo (ad esempio, colore, dimensione, testo) dei pulsanti di accesso PayPal in tutto il tuo negozio.
- **Valore consigliato:** Scegli uno stile che si integri al meglio con il design del tuo negozio pur rimanendo chiaramente identificabile come pulsante PayPal.
- **Scenario/esempio per il commerciante:** Il tuo negozio utilizza un tema scuro, quindi potresti scegliere un pulsante PayPal bianco con testo scuro per un migliore contrasto. Oppure potresti preferire il pulsante PayPal blu standard per la massima riconoscibilità del marchio.

#### **URL di reindirizzamento dopo l'accesso**

Specifica dove vengono inviati i clienti dopo aver effettuato l'accesso con PayPal.

- **Cosa fa questa impostazione:** Definisce la pagina a cui un cliente viene reindirizzato immediatamente dopo aver autenticato con successo con PayPal e essere tornato al tuo negozio.
- **Effetto della modifica di questa impostazione:**
  - *Se impostato su "Il mio account":* I clienti atterrano sulla loro dashboard personale dell'account.
  - *Se impostato su "Homepage":* I clienti vengono riportati alla pagina principale del tuo negozio.
  - *Se impostato su "Pagina precedente":* I clienti vengono riportati alla pagina in cui si trovavano prima di avviare l'accesso.
- **Valore consigliato:** "Pagina precedente" o "Il mio account" per un'esperienza senza interruzioni. "Pagina precedente" è spesso preferita durante il checkout.
- **Scenario/esempio per il commerciante:** Un cliente si trova su una pagina prodotto e fa clic su "Accedi con PayPal". Se è selezionata "Pagina precedente", tornerà a quella pagina prodotto. Se si trovava nel processo di checkout, tornerebbe al passaggio di checkout.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | ID Cliente PayPal | (Vuoto) / Il tuo ID Cliente PayPal | Identificatore univoco per la tua app PayPal. **Richiesto per il funzionamento del modulo.** |
| Configurazione modulo | Segreto Cliente PayPal | (Vuoto) / Il tuo Segreto Cliente PayPal | Chiave segreta per la tua app PayPal. **Richiesto per il funzionamento del modulo.** |
| Configurazione modulo | Abilita login PayPal | SÌ | Interruttore principale per attivare/disattivare la funzione di login PayPal. |
| Configurazione modulo | Mostra pulsante in: displayNav | SÌ | Mostra il pulsante nella barra di navigazione principale. |
| Configurazione modulo | Mostra pulsante in: displayCustomerLoginFormAfter | SÌ | Mostra il pulsante dopo il modulo di login standard. |
| Configurazione modulo | Mostra pulsante in: createAccountForm | SÌ | Mostra il pulsante nella pagina di registrazione del cliente. |
| Configurazione modulo | Mostra pulsante in: displayFooter | NO | Mostra il pulsante nel piè di pagina del negozio. |
| Configurazione modulo | Mostra pulsante in: displayHome | NO | Mostra il pulsante nella homepage. |
| Configurazione modulo | Mostra pulsante in: displayLeftColumn | NO | Mostra il pulsante nella colonna sinistra. |
| Configurazione modulo | Mostra pulsante in: displayNav1 | NO | Mostra il pulsante in un hook di navigazione alternativo (dipendente dal tema). |
| Configurazione modulo | Mostra pulsante in: displayNav2 | NO | Mostra il pulsante in un altro hook di navigazione alternativo (dipendente dal tema). |
| Configurazione modulo | Mostra pulsante in: displayPopUpLogin | SÌ | Mostra il pulsante nei moduli di login pop-up (se il tuo tema li utilizza). |
| Configurazione modulo | Mostra pulsante in: displayRightColumn | NO | Mostra il pulsante nella colonna destra. |
| Configurazione modulo | Mostra pulsante in: displayTop | NO | Mostra il pulsante nella sezione superiore della pagina (dipendente dal tema). |
| Configurazione modulo | Mostra pulsante in: header | NO | Mostra il pulsante nella sezione HTML `<head>` (meno comune per i pulsanti visibili). |
| Configurazione modulo | Mostra pulsante in: shoppingCart | NO | Mostra il pulsante all'interno del riepilogo del carrello. |
| Configurazione modulo | Mostra pulsante in: shoppingCartExtra | NO | Mostra il pulsante in una sezione extra del carrello (dipendente dal tema). |
| Configurazione modulo | Stile pulsante | (Stile PayPal predefinito) | Aspetto visivo del pulsante di login PayPal. |
| Configurazione modulo | URL di reindirizzamento dopo l'accesso | Pagina precedente | Pagina di destinazione dopo l'accesso PayPal riuscito. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Il pulsante di accesso PayPal non viene visualizzato nel mio negozio.**
R:

1.  **Controlla "Abilita login PayPal":** Assicurati che questa impostazione sia impostata su SÌ nella configurazione del modulo.
2.  **Verifica le impostazioni "Mostra pulsante in":** Assicurati di aver selezionato almeno un hook (ad esempio, `displayNav`, `displayCustomerLoginFormAfter`) dove desideri che il pulsante appaia.
3.  **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e svuota la cache di PrestaShop (cache Smarty, cache del filesystem). Potrebbe essere necessario svuotare anche la cache del browser.
4.  **Compatibilità del tema:** Alcuni temi altamente personalizzati potrebbero richiedere piccole modifiche. Se il pulsante non appare ancora, contatta il supporto MyPresta.eu.

**D: Quando faccio clic sul pulsante PayPal, non succede nulla o ricevo un errore.**
R:

1.  **Controlla le credenziali API:** Ricontrolla il tuo ID Cliente PayPal e il Segreto Cliente nella configurazione del modulo. Anche un singolo carattere errato impedirà la connessione.
2.  **Configurazione dell'app PayPal:** Assicurati che la tua app "Accedi con PayPal" nel tuo account Sviluppatore PayPal sia configurata correttamente, in particolare l'"URL di ritorno" o "URI di reindirizzamento" che dovrebbe puntare alla pagina di autenticazione del tuo negozio (ad esempio, `https://iltuonegozio.com/authentication?paypal_login=1`).
3.  **Compatibilità PHP:** Verifica che la versione PHP del tuo server rientri nell'intervallo supportato (PHP 5.6 - 8.5).

**D: I miei clienti vengono reindirizzati alla pagina sbagliata dopo l'accesso.**
R:

1.  **Controlla "URL di reindirizzamento dopo l'accesso":** Rivedi questa impostazione nella configurazione del modulo. Seleziona l'opzione desiderata (ad esempio, "Il mio account", "Pagina precedente").
2.  **Svuota la cache:** Dopo aver modificato questa impostazione, svuota la cache di PrestaShop e del browser.

**D: Posso cambiare il testo sul pulsante di accesso PayPal?**
R: Il modulo utilizza tipicamente il branding standard di PayPal per il testo e lo stile del pulsante. La modifica diretta del testo di solito non è un'opzione all'interno della configurazione del modulo stesso, poiché è progettato per aderire alle linee guida di PayPal. Se hai bisogno di testo personalizzato, ciò richiederebbe override a livello di tema o personalizzazione del modulo (vedi Guida per gli sviluppatori).

**D: Questo modulo funziona con negozi multilingue?**
R: Sì, il modulo è progettato per essere compatibile con le funzionalità multilingue di PrestaShop. L'interfaccia di accesso PayPal stessa è gestita da PayPal, che di solito si adatta alla lingua del browser dell'utente. Eventuali testi specifici del modulo (se presenti) possono essere tradotti tramite **Internazionale > Traduzioni** nel back office di PrestaShop.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Connessione tramite login PayPal" (`plogin`) è un modulo PrestaShop standard implementato principalmente all'interno del suo file `index.php` principale, che funge da punto di ingresso del modulo e gestore della configurazione. Sfrutta il sistema di hook di PrestaShop per iniettare il pulsante "Accedi con PayPal" in varie posizioni del front-office. Il modulo gestisce il flusso OAuth 2.0 con PayPal per l'autenticazione dell'utente, creando un account cliente se non esiste e effettuando l'accesso dell'utente. Non introduce tabelle di database personalizzate o strutture `ObjectModel` complesse, basandosi sulle classi native `Customer` e `Configuration` di PrestaShop.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller dedicati per il front-office o il back-office nella directory `controllers/`. Tutta la logica del front-office relativa al callback di PayPal è gestita direttamente all'interno del file `index.php` (la classe principale del modulo) tramite parametri `$_GET`, e la configurazione del back-office è gestita tramite il metodo `getContent()` della classe principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non contiene classi o modelli personalizzati in una directory `classes/`. Tutta la logica principale, inclusa l'interazione API e la gestione dei clienti, è incapsulata all'interno della classe principale `plogin` definita in `index.php`.

### 4.4 Risorse JavaScript (`views/js/`)

- **`plogin/js/plogin.js`**
  - **Ambito:** Front-office.
  - **Scopo:** Questo script probabilmente gestisce l'interazione lato client per il pulsante di accesso PayPal. Ciò potrebbe includere:
    - Apertura della finestra di autenticazione PayPal come pop-up.
    - Gestione del reindirizzamento dopo l'autenticazione PayPal.
    - Potenziale gestione delle richieste AJAX per lo stato di accesso o il rendering dinamico del pulsante.
    - Collegamento degli eventi di clic ai pulsanti di accesso PayPal.
    - Garanzia della funzionalità del pulsante su diversi browser e dispositivi.

### 4.5 Fogli di stile CSS (`views/css/`)

- **`plogin/css.css`**

  - **Ambito:** Front-office.
  - **Scopo:** Questo foglio di stile probabilmente contiene lo stile generale per il pulsante di accesso PayPal e qualsiasi elemento associato. Potrebbe definire layout di base, spaziatura interna, margini e stili di carattere.
  - **Selettori chiave:** Gli sviluppatori possono ispezionare questo file per i nomi delle classi (ad esempio, `.paypal-login-button`, `.plogin-container`) per sovrascrivere gli stili nel `custom.css` o `theme.css` del loro tema.
- **`plogin/css/plogin.css`**

  - **Ambito:** Front-office.
  - **Scopo:** Simile a `css.css`, questo file fornisce uno stile aggiuntivo o più specifico per il pulsante di accesso PayPal, includendo potenzialmente diversi stili di pulsante basati sulla configurazione, effetti hover o aggiustamenti reattivi.
  - **Selettori chiave:** Cerca classi di pulsanti specifiche (ad esempio, `.plogin-btn-blue`, `.plogin-btn-white`) per mirare e personalizzare.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo utilizza un set completo di template Smarty per iniettare il pulsante di accesso PayPal in vari hook di PrestaShop.

- **Template degli hook (`views/templates/hook/`)**:
  - `plogin/createAccountForm.tpl`: Rende il pulsante PayPal nel modulo di registrazione del cliente.
  - `plogin/displayCustomerLoginFormAfter.tpl`: Rende il pulsante PayPal dopo il modulo di accesso standard del cliente.
  - `plogin/displayFooter.tpl`: Rende il pulsante PayPal nel piè di pagina del negozio.
  - `plogin/displayHome.tpl`: Rende il pulsante PayPal nella homepage.
  - `plogin/displayleftColumn.tpl`: Rende il pulsante PayPal nella colonna sinistra.
  - `plogin/displayNav.tpl`: Rende il pulsante PayPal nella barra di navigazione principale (hook comune per i collegamenti superiori).
  - `plogin/displayNav1.tpl`: Rende il pulsante PayPal in un hook di navigazione alternativo (dipendente dal tema).
  - `plogin/displayNav2.tpl`: Rende il pulsante PayPal in un altro hook di navigazione alternativo (dipendente dal tema).
  - `plogin/displayPopUpLogin.tpl`: Rende il pulsante PayPal all'interno di un modulo di accesso pop-up (se utilizzato dal tema).
  - `plogin/displayrightColumn.tpl`: Rende il pulsante PayPal nella colonna destra.
  - `plogin/displayTop.tpl`: Rende il pulsante PayPal nella sezione superiore della pagina (dipendente dal tema).
  - `plogin/header.tpl`: Questo template è probabilmente utilizzato per includere risorse CSS/JS nella sezione `<head>` quando viene utilizzato l'hook `displayHeader`, piuttosto che visualizzare un pulsante visibile.
  - `plogin/shoppingCart.tpl`: Rende il pulsante PayPal all'interno del riepilogo del carrello.
  - `plogin/shoppingCartExtra.tpl`: Rende il pulsante PayPal in una sezione extra del carrello (dipendente dal tema).
  - `plogin/top.tpl`: Simile a `displayTop`, per la sezione superiore della pagina.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Il modulo non crea tabelle SQL personalizzate.
  - Le impostazioni di configurazione (ID Cliente, Segreto Cliente, stato abilitato, hook selezionati, URL di reindirizzamento, stile del pulsante) sono memorizzate nella tabella `ps_configuration` di PrestaShop, tipicamente con chiavi prefissate da `PLOGIN_` (ad esempio, `PLOGIN_CLIENT_ID`, `PLOGIN_ENABLED`).
- **Tabella degli hook registrati**:

| Nome dell'hook | Tempistica / Posizione di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Per includere risorse CSS e JavaScript a livello globale per il modulo. |
| `displayNav` | Nella barra di navigazione principale, di solito nella parte superiore della pagina. | Visualizza il pulsante di accesso PayPal in un'area di navigazione prominente. |
| `displayNav1` | Hook di navigazione alternativo (dipendente dal tema). | Fornisce flessibilità per i temi con più aree di navigazione. |
| `displayNav2` | Un altro hook di navigazione alternativo (dipendente dal tema). | Fornisce flessibilità per i temi con più aree di navigazione. |
| `displayTop` | Nella sezione superiore della pagina, sopra il contenuto principale. | Visualizza il pulsante di accesso PayPal nella barra superiore. |
| `displayLeftColumn` | Nella barra laterale sinistra delle pagine che ne hanno una. | Visualizza il pulsante di accesso PayPal nella colonna sinistra. |
| `displayRightColumn` | Nella barra laterale destra delle pagine che ne hanno una. | Visualizza il pulsante di accesso PayPal nella colonna destra. |
| `displayFooter` | Nella sezione del piè di pagina del negozio. | Visualizza il pulsante di accesso PayPal nel piè di pagina. |
| `displayHome` | Nella homepage del negozio. | Visualizza il pulsante di accesso PayPal nella pagina di atterraggio principale. |
| `displayCustomerLoginFormAfter` | Dopo il modulo di accesso standard nella pagina di autenticazione. | Fornisce l'opzione di accesso PayPal come alternativa a email/password. |
| `createAccountForm` | Nella pagina di registrazione del cliente. | Offre PayPal come metodo di registrazione rapido. |
| `displayPopUpLogin` | All'interno di un modale di accesso pop-up (se implementato dal tema). | Si integra con i moderni pop-up di accesso del tema. |
| `shoppingCart` | All'interno del blocco di riepilogo del carrello. | Offre l'accesso/registrazione durante la fase di revisione del carrello. |
| `shoppingCartExtra` | In una sezione extra del carrello (dipendente dal tema). | Fornisce ulteriore flessibilità di posizionamento all'interno del carrello. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo "Connessione tramite login PayPal", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema tecnico o domanda relativa alla funzionalità del modulo.
