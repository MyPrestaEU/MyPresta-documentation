---
title: "Compari.ro - email di sondaggio programma acquisto fidato - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Compari.ro - email di sondaggio programma acquisto fidato di MyPresta.eu."
sidebar:
  label: "Compari.ro - email di sondaggio programma acquisto fidato - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Compari.ro - trusted purchase program survey emails su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/compariro-trusted-purchase-program-survey-emails.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/compariro-trusted-purchase-program-survey-emails/)
>
> ---


# Compari.ro - email di sondaggio programma acquisto fidato

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e sono sufficienti per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale e unica per il modulo Compari.ro. Puoi accedervi navigando su **Moduli > Gestione moduli**, cercando "Compari.ro" e cliccando sul pulsante "Configura".

#### **1. Compari.ro WebApiKey**

-   **Cosa fa questa impostazione:** Questo è il tuo identificatore unico fornito da Compari.ro che collega il tuo negozio PrestaShop al tuo account commerciante Compari.ro. È essenziale affinché il "Programma Acquisto Fidato" attribuisca correttamente le richieste di sondaggio al tuo negozio.
-   **Effetto della modifica di questa impostazione:**
    -   *Se inserito correttamente:* Il modulo sarà in grado di inviare i dati dell'ordine a Compari.ro, consentendo loro di inviare email di sondaggio ai tuoi clienti.
    -   *Se errato o vuoto:* L'integrazione fallirà e Compari.ro non riceverà le informazioni sull'ordine, il che significa che non verranno inviate email di sondaggio.
-   **Valore consigliato:** Inserisci l'esatto WebApiKey fornito da Compari.ro.
-   **Scenario / esempio commerciante:** Ti sei registrato al "Programma Acquisto Fidato" di Compari.ro e hai ricevuto un'email con la tua chiave API. Devi copiare e incollare questa chiave qui affinché l'integrazione funzioni.

#### **2. Identificatore prodotto (feed ITEM\_ID)**

-   **Cosa fa questa impostazione:** Questa impostazione definisce quale identificatore di prodotto dal tuo negozio PrestaShop deve essere utilizzato come `ITEM_ID` quando si inviano informazioni sul prodotto a Compari.ro. Questo è fondamentale per abbinare i prodotti nel tuo feed Compari.ro con i prodotti nei tuoi ordini.
-   **Effetto della modifica di questa impostazione:**
    -   *Se impostato su `id_product` (predefinito):* Verrà utilizzato l'ID interno del prodotto PrestaShop. Questa è generalmente l'opzione più sicura se non hai un identificatore personalizzato specifico.
    -   *Se impostato su `reference`:* Verrà utilizzato il codice di riferimento del prodotto. Scegli questa opzione se il tuo feed di prodotti Compari.ro utilizza il riferimento del prodotto come `ITEM_ID`.
    -   *Se impostato su `ean13`:* Verrà utilizzato il codice a barre EAN-13 del prodotto. Scegli questa opzione se il tuo feed di prodotti Compari.ro utilizza EAN-13 come `ITEM_ID`.
    -   *Se impostato su `upc`:* Verrà utilizzato il codice UPC del prodotto. Scegli questa opzione se il tuo feed di prodotti Compari.ro utilizza UPC come `ITEM_ID`.
-   **Valore consigliato:** `id_product` (a meno che il tuo feed di prodotti Compari.ro non utilizzi esplicitamente `reference`, `ean13` o `upc` come `ITEM_ID`).
-   **Scenario / esempio commerciante:** Il tuo feed di prodotti Compari.ro utilizza il codice a barre EAN-13 unico per ogni prodotto. Selezioneresti `ean13` qui per assicurarti che Compari.ro possa identificare correttamente i prodotti acquistati dai tuoi clienti.

#### **3. Richiedi consenso del cliente**

-   **Cosa fa questa impostazione:** Questa opzione determina se i tuoi clienti devono accettare esplicitamente di partecipare al programma di sondaggio Compari.ro durante il checkout. Questo è importante per la conformità al GDPR e per rispettare le preferenze sulla privacy dei clienti.
-   **Effetto della modifica di questa impostazione:**
    -   *Se abilitato (impostato su "Sì"):* Apparirà una casella di controllo durante il processo di checkout (ad esempio, sulla pagina di pagamento o nel riepilogo del checkout). I clienti devono spuntare questa casella per consentire l'invio dei dati del loro ordine a Compari.ro per scopi di sondaggio. Se non acconsentono, non verrà inviata alcuna email di sondaggio per il loro ordine.
    -   *Se disabilitato (impostato su "No"):* Non verrà visualizzata alcuna casella di controllo per il consenso. I dati dell'ordine verranno inviati a Compari.ro per tutti gli ordini, supponendo che il `WebApiKey` sia corretto.
-   **Valore consigliato:** "Sì" se operi in regioni con leggi severe sulla privacy dei dati (come il GDPR) o se vuoi dare ai clienti il pieno controllo sulla condivisione dei loro dati. "No" se hai stabilito che il consenso esplicito non è richiesto per il tuo specifico contesto legale o se vuoi massimizzare la partecipazione al sondaggio.
-   **Scenario / esempio commerciante:** Per conformarti alle normative GDPR, abiliti questa impostazione. Durante il checkout, i clienti vedono una casella di controllo "Accetto di partecipare al sondaggio del Programma Acquisto Fidato Compari.ro". Solo i clienti che spuntano questa casella riceveranno un'email di sondaggio.

#### **4. Scrivi errori su log.txt**

-   **Cosa fa questa impostazione:** Questa è un'opzione di debug che controlla se il modulo registra eventuali errori riscontrati durante il suo funzionamento (ad esempio, problemi nell'invio di dati a Compari.ro) in un file `log.txt` all'interno della directory del modulo.
-   **Effetto della modifica di questa impostazione:**
    -   *Se abilitato (impostato su "Sì"):* Eventuali errori tecnici verranno scritti in `compari/log.txt`. Questo file può essere molto utile per il tuo webmaster o il supporto MyPresta.eu per diagnosticare i problemi.
    -   *Se disabilitato (impostato su "No"):* Gli errori non verranno esplicitamente registrati in un file. Questo è generalmente preferibile per i negozi di produzione live per evitare di generare file di log di grandi dimensioni, a meno che non si stia attivamente risolvendo un problema.
-   **Valore consigliato:** "No" per un negozio di produzione live. "Sì" se stai riscontrando problemi con l'integrazione e hai bisogno di eseguire il debug. Ricorda di disabilitarlo una volta risolto il problema.
-   **Scenario / esempio commerciante:** Hai configurato il modulo, ma i clienti non ricevono email di sondaggio. Abiliti "Scrivi errori su log.txt" e poi effettui un ordine di prova. Quindi controlli il file `log.txt` per indizi sul motivo per cui l'integrazione potrebbe fallire.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Compari.ro WebApiKey | La tua chiave API unica | Collega il tuo negozio a Compari.ro per l'automazione dei sondaggi. **Critico per la funzionalità.** |
| Configurazione modulo | Identificatore prodotto (feed ITEM\_ID) | `id_product` (o corrisponde al tuo feed) | Specifica quale ID prodotto (interno, riferimento, EAN, UPC) inviare a Compari.ro. |
| Configurazione modulo | Richiedi consenso del cliente | Sì (per GDPR) | Visualizza una casella di controllo per il consenso durante il checkout. Se non selezionata, non viene inviata alcuna email di sondaggio. |
| Configurazione modulo | Scrivi errori su log.txt | No (abilita per il debug) | Registra gli errori tecnici in `compari/log.txt` per la risoluzione dei problemi. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei clienti non ricevono email di sondaggio da Compari.ro, ma il modulo è configurato.**
R1:

-   **Controlla WebApiKey:** Ricontrolla che il tuo "Compari.ro WebApiKey" sia inserito correttamente ed esattamente come fornito da Compari.ro. Anche un singolo errore di battitura impedirà all'integrazione di funzionare.
-   **Controlla l'impostazione del consenso:** Se "Richiedi consenso del cliente" è impostato su "Sì", assicurati che i tuoi clienti di prova stiano effettivamente spuntando la casella di consenso durante il checkout.
-   **Controlla l'account Compari.ro:** Accedi al tuo account commerciante Compari.ro per vedere se ci sono messaggi di errore o se gli ordini vengono ricevuti dal tuo negozio.
-   **Abilita la registrazione:** Imposta "Scrivi errori su log.txt" su "Sì" nella configurazione del modulo, effettua un ordine di prova e quindi controlla il file `compari/log.txt` per eventuali messaggi di errore. Questo fornirà dettagli tecnici specifici.
-   **Svuota la cache:** A volte, la cache di PrestaShop può interferire. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache".

**D2: Ho abilitato "Richiedi consenso del cliente", ma non vedo una casella di controllo durante il checkout.**
R2:

-   **Compatibilità del tema:** Il modulo utilizza hook standard di PrestaShop (`displayGDPRConsent`, `displayPaymentTop`, `displayCheckoutSummaryTop`) per visualizzare la casella di controllo del consenso. Se il tuo tema personalizzato modifica pesantemente il processo di checkout, questi hook potrebbero non essere renderizzati, o lo stile potrebbe rendere la casella di controllo invisibile.
-   **Cache:** Svuota la cache di PrestaShop (**Parametri avanzati > Prestazioni**).
-   **Posizione del modulo:** Assicurati che il modulo non sia disabilitato per gli hook specifici che utilizza. Sebbene meno comune per una casella di controllo del consenso, vale la pena controllare in **Design > Posizioni**.

**D3: Cosa succede se un cliente cambia idea sul consenso dopo aver effettuato un ordine?**
R3: Il modulo elabora il consenso al momento dell'effettuazione dell'ordine. Se un cliente desidera revocare il consenso per futuri sondaggi, dovrebbe in genere gestire questo direttamente con Compari.ro o tramite gli strumenti generali di gestione dei dati GDPR del tuo negozio (se li hai). Il modulo stesso non offre un "annulla" diretto per gli ordini passati, ma si integra con gli hook GDPR di PrestaShop per la cancellazione e l'esportazione dei dati.

**D4: Vedo un file `log.txt` che sta diventando molto grande. Cosa devo fare?**
R4: Se non stai attivamente risolvendo un problema, imposta l'opzione "Scrivi errori su log.txt" su "No" nella configurazione del modulo. Questo impedirà al modulo di scrivere ulteriori voci nel file di log. Puoi quindi eliminare in sicurezza il file `log.txt` per liberare spazio.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo `Compari` è un modulo PrestaShop semplice, focalizzato principalmente sull'integrazione con un'API esterna (Compari.ro) basata su eventi d'ordine. Segue una struttura standard del modulo PrestaShop, sfruttando gli hook per iniettare contenuti (consenso GDPR) e attivare azioni (invio di dati d'ordine). Non introduce controller personalizzati o ObjectModels complessi, affidandosi ai dati `Order` e `Customer` del core di PrestaShop. La logica principale risiede nel file `compari.php`, che gestisce la configurazione, l'installazione e i callback degli hook.

### 4.2 Controller (`controllers/`)

-   Questo modulo **non** contiene alcun controller amministrativo Front-Office o Back-Office personalizzato. Tutta la logica è gestita all'interno del file principale `compari.php` tramite hook.

### 4.3 Classi e modelli principali (`classes/`)

-   Questo modulo **non** contiene classi o ObjectModels personalizzati nella directory `classes/`. Tutta la gestione dei dati viene eseguita direttamente all'interno del file `compari.php` utilizzando le entità `Order`, `Customer` e `Product` del core di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

-   Questo modulo **non** contiene file JavaScript personalizzati.

### 4.5 Fogli di stile CSS (`views/css/`)

-   Questo modulo **non** contiene file CSS personalizzati. Lo stile per la casella di controllo del consenso dovrebbe essere ereditato dal tema o gestito dallo stile del modulo GDPR del core di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template degli hook (`views/templates/hook/`)**:
    -   `compari/views/templates/hook/consent.tpl`:
        -   **Hook:** `displayGDPRConsent`, `displayPaymentTop`, `displayCheckoutSummaryTop`
        -   **Scopo:** Rende la casella di controllo del consenso GDPR e il testo associato, consentendo ai clienti di aderire o meno al programma di sondaggio Compari.ro. Questo template viene reso solo se la configurazione `COMPARI_CONSENT` è abilitata.
        -   **Output:** Un campo di input checkbox con un'etichetta.
    -   `compari/views/templates/hook/displayOrderConfirmation.tpl`:
        -   **Hook:** `displayOrderConfirmation`
        -   **Scopo:** Questo template è incluso nell'hook `displayOrderConfirmation`. Sebbene sia un file di template, il suo ruolo principale qui è quello di attivare la logica di backend all'interno di `hookDisplayOrderConfirmation` in `compari.php` per inviare i dati dell'ordine a Compari.ro. Non produce contenuto visibile all'utente.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il modulo **non** crea tabelle SQL personalizzate.
    -   Memorizza le sue impostazioni di configurazione nella tabella `ps_configuration`:
        -   `COMPARI_FILE_LOG`: Memorizza il valore booleano per la registrazione degli errori.
        -   `COMPARI_ID`: Memorizza il WebApiKey di Compari.ro.
        -   `COMPARI_PRODUCT_ID`: Memorizza il tipo di identificatore di prodotto selezionato (ad esempio, `id_product`, `reference`).
        -   `COMPARI_CONSENT`: Memorizza il valore booleano per la richiesta del consenso del cliente.
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `install()` | Durante l'installazione del modulo | Imposta i valori di configurazione predefiniti, registra gli hook. |
| `uninstall()` | Durante la disinstallazione del modulo | Elimina i valori di configurazione, annulla la registrazione degli hook. |
| `hookDisplayGDPRConsent` | Rende sulle pagine in cui viene raccolto il consenso GDPR (ad esempio, checkout) | Visualizza la casella di controllo del consenso per la partecipazione al sondaggio Compari.ro. |
| `hookActionDeleteGDPRCustomer` | Quando un cliente richiede la cancellazione dei dati GDPR | Gestisce la cancellazione di eventuali dati cliente relativi a Compari.ro (anche se nessuno è memorizzato direttamente dal modulo, è un hook di conformità). |
| `hookActionExportGDPRData` | Quando un cliente richiede l'esportazione dei dati GDPR | Gestisce l'esportazione di eventuali dati cliente relativi a Compari.ro (nessuno memorizzato direttamente). |
| `hookDisplayOrderConfirmation` | Sulla pagina di conferma dell'ordine dopo un acquisto riuscito | Attiva l'invio dei dati dell'ordine a Compari.ro se il consenso è dato (o non richiesto). |
| `hookDisplayPaymentTop` | Parte superiore del passaggio di pagamento nel checkout | Hook alternativo per visualizzare la casella di controllo del consenso. |
| `hookDisplayCheckoutSummaryTop` | Parte superiore del passaggio di riepilogo del checkout | Hook alternativo per visualizzare la casella di controllo del consenso. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Compari.ro - email di sondaggio programma acquisto fidato", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema tecnico o domanda tu possa avere.
