---
title: "Allegati solo per utenti registrati - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Allegati solo per utenti registrati di MyPresta.eu."
sidebar:
  label: "Allegati solo per utenti registrati - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Attachments for logged users only su MyPresta.eu](https://mypresta.eu/modules/front-office-features/attachments-for-logged-users-only.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/attachments-for-logged-users-only/)
>
> ---


# Allegati solo per utenti registrati

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono generalmente sufficienti. Di solito non sono necessarie configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo aver installato il modulo, clicca su "Configura" per accedere alle sue impostazioni. Questa è la schermata principale in cui controlli il comportamento del modulo.

#### **Attiva funzionalità**

- **Cosa fa questa impostazione:** Questo è l'interruttore principale per il modulo. Determina se la funzionalità di restrizione degli allegati è attiva o inattiva sul tuo negozio.
- **Effetto della modifica di questa impostazione:**
  - *Quando abilitato ("Abilitato"):* Il modulo limiterà attivamente i download degli allegati dei prodotti solo ai clienti registrati. Gli utenti non registrati non potranno scaricare gli allegati.
  - *Quando disabilitato ("Disabilitato"):* Il modulo sarà inattivo. Gli allegati dei prodotti si comporteranno come fanno per impostazione predefinita in PrestaShop, il che significa che chiunque (registrato o ospite) può scaricarli.
- **Valore consigliato:** "Abilitato" se desideri limitare i download degli allegati.
- **Scenario/esempio del commerciante:** Se desideri iniziare a richiedere ai clienti di accedere per scaricare i manuali, imposta questo valore su "Abilitato". Se stai testando o desideri ripristinare temporaneamente il comportamento predefinito di PrestaShop, impostalo su "Disabilitato".

#### **Download solo per clienti**

- **Cosa fa questa impostazione:** Questa impostazione affina la "Attiva funzionalità" consentendoti di specificare *quali* clienti possono scaricare allegati in base alla loro cronologia ordini.
- **Effetto della modifica di questa impostazione:**
  - *Quando abilitato:* Solo i clienti che hanno effettuato l'accesso E hanno almeno un ordine con uno stato selezionato (vedi "Seleziona stati ordine" di seguito) potranno scaricare gli allegati. Questo aggiunge un ulteriore livello di esclusività.
  - *Quando disabilitato:* Qualsiasi cliente registrato (indipendentemente dalla sua cronologia ordini) potrà scaricare gli allegati, a condizione che la "Attiva funzionalità" sia abilitata.
- **Valore consigliato:** "Disabilitato" per la maggior parte dei casi, consentendo a qualsiasi cliente registrato di scaricare. "Abilitato" se desideri offrire allegati come vantaggio per i clienti *paganti*.
- **Scenario/esempio del commerciante:** Vendi software e desideri fornire aggiornamenti o guide premium solo ai clienti che hanno effettivamente acquistato il software. Abiliteresti questa impostazione e selezioneresti "Pagamento accettato" nell'opzione "Seleziona stati ordine".

#### **Seleziona stati ordine**

- **Cosa fa questa impostazione:** Questa opzione appare solo se "Download solo per clienti" è abilitato. Ti consente di scegliere quali stati dell'ordine qualificano un cliente per scaricare allegati. Un cliente deve avere almeno un ordine con uno degli stati selezionati per ottenere l'accesso.
- **Effetto della modifica di questa impostazione:**
  - *Quando uno o più stati sono selezionati:* Solo i clienti registrati con un ordine corrispondente a uno di questi stati possono scaricare allegati.
  - *Quando non sono selezionati stati (e "Download solo per clienti" è abilitato):* Questa configurazione potrebbe portare a nessun cliente in grado di scaricare, poiché non sono definiti stati dell'ordine qualificanti. È fondamentale selezionare almeno uno stato se si abilita "Download solo per clienti".
- **Valore consigliato:** Se "Download solo per clienti" è abilitato, seleziona stati pertinenti come "Pagamento accettato", "Consegnato" o "Spedito" per concedere l'accesso ai clienti che hanno completato con successo un ordine.
- **Scenario/esempio del commerciante:** Se desideri concedere l'accesso agli allegati solo ai clienti i cui ordini sono stati pagati ed elaborati con successo, selezioneresti "Pagamento accettato" e "Consegnato". Ciò impedisce ai clienti con ordini in sospeso o annullati di accedere ai file.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Attiva funzionalità | Abilitato | Interruttore principale per abilitare/disabilitare la restrizione degli allegati. |
| Configurazione modulo | Download solo per clienti | Disabilitato | Se abilitato, solo i clienti registrati con stati d'ordine specifici possono scaricare. |
| Configurazione modulo | Seleziona stati ordine | (Nessuno selezionato) | Se "Download solo per clienti" è attivo, seleziona gli stati d'ordine che concedono l'accesso al download. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei allegati sono ancora scaricabili da tutti, anche dopo aver abilitato il modulo. Cosa c'è che non va?**
R:

1. **Controlla "Attiva funzionalità":** Assicurati che l'impostazione "Attiva funzionalità" nella pagina di configurazione del modulo sia impostata su "Abilitato".
2. **Svuota la cache:** PrestaShop utilizza la cache. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). Questo spesso risolve i problemi di visualizzazione dopo le modifiche alla configurazione del modulo.
3. **Posizione del modulo:** Assicurati che il modulo sia agganciato correttamente. Sebbene il modulo lo gestisca automaticamente, a volte possono verificarsi conflitti con il tema.

**D: Ho abilitato "Download solo per clienti" e selezionato gli stati dell'ordine, ma i miei clienti registrati non riescono ancora a scaricare.**
R:

1. **Verifica lo stato dell'ordine:** Ricontrolla che il cliente che sta cercando di scaricare abbia effettivamente un ordine con uno degli stati *esatti* che hai selezionato in "Seleziona stati ordine".
2. **Accesso del cliente:** Conferma che il cliente sia effettivamente loggato nel proprio account.
3. **Cache:** Svuota la cache di PrestaShop (Parametri avanzati > Prestazioni).

**D: Come traduco i messaggi mostrati agli utenti non registrati?**
R: Il modulo dovrebbe integrarsi con il sistema di traduzione di PrestaShop.

1. Vai su **Internazionale > Traduzioni**.
2. Seleziona "Traduzioni dei moduli installati".
3. Scegli il tuo tema, la tua lingua e quindi il modulo "Allegati solo per utenti registrati".
4. Dovresti trovare le stringhe di testo pertinenti da tradurre lì.

**D: Questo modulo funzionerà con il mio tema personalizzato?**
R: Sì, il modulo è progettato per funzionare con i meccanismi di allegati standard di PrestaShop. Intercetta principalmente la richiesta di download piuttosto che modificare pesantemente la visualizzazione visiva degli allegati. Tuttavia, se il tuo tema personalizzato sovrascrive completamente il modo in cui gli allegati vengono visualizzati o collegati, potrebbero essere necessarie piccole modifiche. Testa sempre accuratamente dopo l'installazione.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Allegati solo per utenti registrati" opera principalmente sovrascrivendo il `AttachmentController` predefinito per intercettare le richieste di download. Sfrutta il sistema di hook di PrestaShop (`displayHeader`, `header`) per iniettare JavaScript e CSS necessari, e la sua logica principale risiede nel file `atlogged.php`, gestendo la configurazione e l'override principale. Il modulo utilizza una semplice struttura di configurazione memorizzata in `ps_configuration` e include controller front-office per interazioni AJAX e potenziale logica di fallback.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

- `atlogged/controllers/front/index.php`

  - **Nome classe:** `AtloggedIndexModuleFrontController` (probabilmente, basato sulla convenzione di denominazione dei file)
  - **Classe genitore:** `ModuleFrontController`
  - **Responsabilità:** Questo controller potrebbe fungere da punto di ingresso generale per azioni front-office specifiche del modulo, gestendo potenzialmente reindirizzamenti o visualizzando messaggi quando un download di allegato è limitato. Potrebbe anche essere un segnaposto o utilizzato per un routing specifico.
- `atlogged/controllers/front/popuploader.php`

  - **Nome classe:** `AtloggedPopuploaderModuleFrontController`
  - **Classe genitore:** `ModuleFrontController`
  - **Responsabilità:** Questo controller probabilmente gestisce le richieste AJAX relative alla visualizzazione di un prompt di accesso/registrazione o di un messaggio specifico quando un utente tenta di scaricare un allegato limitato. Potrebbe renderizzare un piccolo template (es. `atlogged-ajax.tpl`) con il contenuto appropriato.
- `atlogged/override/controllers/front/AttachmentController.php`

  - **Nome classe:** `AttachmentController` (sovrascrive la classe core)
  - **Classe genitore:** `AttachmentControllerCore`
  - **Responsabilità:** Questa è la parte più critica della logica front-office del modulo. Sovrascrive direttamente il `AttachmentController` core di PrestaShop. La sua funzione principale è:
    1. Controllare se il modulo è abilitato (`ATLOGGED_ON`).
    2. Verificare se l'utente corrente ha effettuato l'accesso.
    3. Se `ATLOGGED_C_ON` (Download solo per clienti) è abilitato, controlla ulteriormente la cronologia degli ordini dell'utente rispetto agli `atlogged_ostates` configurati.
    4. Se l'utente non soddisfa i criteri, impedisce il processo di download predefinito dell'allegato e invece reindirizza l'utente o attiva un'azione specifica del modulo (es. mostrando un prompt di accesso tramite AJAX).
- `atlogged/override/controllers/front/index.php`

  - **Nome classe:** `IndexController` (sovrascrive la classe core)
  - **Classe genitore:** `IndexControllerCore`
  - **Responsabilità:** Sovrascrivere l'`IndexController` è meno comune per la logica specifica degli allegati. Questo potrebbe essere utilizzato per:
    1. Controlli globali o reindirizzamenti relativi al modulo sulla homepage.
    2. Garantire che determinate risorse specifiche del modulo (JS/CSS) siano caricate globalmente.
    3. Potenziale gestione di un reindirizzamento alla pagina di accesso se un link di allegato viene acceduto direttamente senza essere loggati dal contesto della homepage.

#### Controller Admin Back-Office

- Nessuno identificato. La configurazione del modulo è gestita direttamente all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e modelli core (`classes/`)

- Nessuno identificato. Il modulo non sembra definire classi `ObjectModel` personalizzate. Probabilmente funziona direttamente con gli oggetti core esistenti di PrestaShop (es. `Customer`, `Order`, `Attachment`) e i valori di configurazione.

### 4.4 Risorse JavaScript (`views/js/`)

- `atlogged/views/js/atlogged.js`
  - **Ambito:** Front-office.
  - **Dettagli:** Questo script è probabilmente responsabile di:
    1. Intercettare i clic sui link di download degli allegati (tag `<a>` con classi o attributi dati specifici).
    2. Effettuare chiamate AJAX ai controller front-office `popuploader.php` o `index.php` quando un download limitato viene tentato da un utente non qualificato.
    3. Visualizzare popup modali o messaggi (es. "Accedi per scaricare") in base alla risposta AJAX.
    4. Potenziale reindirizzamento degli utenti alla pagina di accesso se la risposta AJAX lo impone.
    5. Garantire che l'esperienza utente sia fluida quando l'accesso è negato.

### 4.5 Fogli di stile CSS (`views/css/`)

- `atlogged/views/css/atlogged.css`
  - **Ambito:** Styling del cliente front-office.
  - **Dettagli:** Questo foglio di stile fornisce lo styling necessario per qualsiasi elemento personalizzato introdotto dal modulo, come:
    1. Styling per il modale o la casella di messaggio del prompt di accesso/registrazione.
    2. Regolazioni all'aspetto del link dell'allegato se sono disabilitati o visivamente alterati quando limitati.
  - **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere:** Gli sviluppatori dovrebbero ispezionare l'output HTML generato dai template del modulo (es. `atlogged-ajax.tpl`) per identificare classi specifiche (es. `.atlogged-modal`, `.atlogged-message`, `.atlogged-login-button`) per l'integrazione e la personalizzazione del tema.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template amministrativi (`views/templates/admin/`)**:

  - `atlogged/views/templates/admin/orderstates.tpl`
    - **Scopo:** Questo template viene utilizzato all'interno del metodo `getContent()` del modulo nel Back Office. Renderizza l'elenco degli stati dell'ordine (`atlogged_ostates`) per l'opzione di configurazione "Seleziona stati ordine", tipicamente come un menu a discesa a selezione multipla o un elenco di checkbox.
- **Template front-office (`views/templates/front/`)**:

  - `atlogged/views/templates/front/atlogged-ajax.tpl`
    - **Scopo:** Questo template è probabilmente renderizzato dal controller front `popuploader.php` in risposta a una richiesta AJAX. Contiene il contenuto HTML per il messaggio visualizzato agli utenti che non possono scaricare un allegato (es. "Accedi per continuare", con link per l'accesso/registrazione).
  - `atlogged/views/templates/front/atlogged.tpl`
    - **Scopo:** Questo template potrebbe essere incluso tramite un hook (es. `displayHeader`) o direttamente da un controller front. Potrebbe contenere:
      1. Elementi nascosti o attributi dati utilizzati da `atlogged.js`.
      2. Impostazioni iniziali o variabili di configurazione per JavaScript.
      3. Messaggi di fallback o elementi sempre presenti ma visualizzati condizionalmente da JS.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Il modulo non crea tabelle SQL personalizzate.
  - I record di configurazione sono memorizzati nella tabella `ps_configuration`:
    - `ATLOGGED_ON`: Memorizza il valore booleano per l'impostazione "Attiva funzionalità".
    - `ATLOGGED_C_ON`: Memorizza il valore booleano per l'impostazione "Download solo per clienti".
    - `atlogged_ostates`: Memorizza un array serializzato o una stringa separata da virgole di ID di stato dell'ordine selezionati per l'impostazione "Seleziona stati ordine".
    - `mypresta_updates`, `update_`, `updatev_`: Utilizzati per i controlli di aggiornamento del modulo da MyPresta.eu.
    - `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Una chiave di configurazione core di PrestaShop, probabilmente acceduta per il contesto linguistico nel Back Office.
- **Tabella degli hook registrati**:

  | Nome hook | Tempo di esecuzione | Scopo tecnico |
  | --- | --- | --- |
  | `displayHeader` | Nella sezione `<head>` di ogni pagina front-office. | Utilizzato per iniettare `atlogged.js` e `atlogged.css` nella pagina, garantendo che la logica lato client e lo styling del modulo siano caricati. |
  | `header` | Alias per `displayHeader` in alcune versioni/contesti di PrestaShop. | Stesso scopo di `displayHeader`. |
  | `actionFrontControllerSetMedia` | Quando un controller front sta impostando le sue risorse multimediali. | Potrebbe essere utilizzato per caricare JS/CSS condizionalmente solo su pagine specifiche (es. pagine prodotto) per l'ottimizzazione delle prestazioni. |
  | `actionDispatcherBefore` | Prima che un controller front venga inviato. | Potenzialmente utilizzato dall'override di `AttachmentController` per intercettare la richiesta di download molto presto. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto tecnico dedicato per il modulo "Allegati solo per utenti registrati", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è pronto ad assisterti per qualsiasi domanda o problema tu possa incontrare.
