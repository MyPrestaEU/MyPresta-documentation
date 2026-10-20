---
title: "Condivisione prodotto Facebook + codice sconto - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Condivisione prodotto Facebook + codice sconto' di MyPresta.eu."
sidebar:
  label: "Condivisione prodotto Facebook + codice sconto"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Facebook product share + discount code su MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-product-share-discount-code.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/facebook-product-share-discount-code/)
>
> ---


# Condivisione prodotto Facebook + codice sconto

## 1. Requisiti e Compatibilità
-   **Versioni PrestaShop supportate**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x
-   **Compatibilità PHP**: PHP 5.6 - 8.5
-   **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop e sono solitamente disponibili nella maggior parte degli ambienti di hosting.

## 2. Panoramica completa della configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)
Dopo l'installazione, vai su **Moduli > Gestione moduli** e clicca su "Configura" accanto a "Condivisione prodotto Facebook + codice sconto". Questa schermata ti consente di controllare la funzionalità e l'aspetto principali del modulo.

#### **Impostazioni generali**

-   **Abilita / Disabilita Modulo:**
    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per l'intero modulo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il pulsante di condivisione di Facebook apparirà sulle pagine prodotto e la funzionalità del codice sconto sarà attiva.
        -   *Quando disabilitato:* Il modulo sarà completamente inattivo. Il pulsante di condivisione non apparirà e non verranno generati codici sconto.
    -   **Valore consigliato:** SÌ (per attivare le funzionalità del modulo).
    -   **Scenario / esempio per il commerciante:** Se stai configurando il modulo per la prima volta o eseguendo la manutenzione, potresti disabilitarlo temporaneamente. Una volta pronto, abilitalo per iniziare a generare condivisioni e sconti.

-   **ID App Facebook:**
    -   **Cosa fa questa impostazione:** Questo campo richiede il tuo ID applicazione Facebook unico. Questo ID è cruciale affinché Facebook identifichi correttamente il tuo sito web e tracci le condivisioni. Devi creare un'App Facebook sulla piattaforma per sviluppatori di Facebook (developers.facebook.com) per ottenere questo ID.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando inserito correttamente:* Il modulo comunicherà correttamente con Facebook, consentendo il tracciamento delle condivisioni e il funzionamento del meccanismo di sconto.
        -   *Quando errato o vuoto:* La funzionalità di condivisione di Facebook potrebbe non funzionare, o le condivisioni potrebbero non essere tracciate, impedendo l'emissione di codici sconto.
    -   **Valore consigliato:** Il tuo ID App Facebook valido (es. `123456789012345`).
    -   **Scenario / esempio per il commerciante:** Hai creato un'App Facebook per il tuo negozio. Copia l'ID App dalla tua dashboard per sviluppatori di Facebook e incollalo qui. Questa è una configurazione una tantum.

-   **Tipo di sconto:**
    -   **Cosa fa questa impostazione:** Determina il tipo di sconto che i clienti ricevono dopo la condivisione.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su "Percentuale":* Il codice sconto offrirà una percentuale di sconto sul totale dell'ordine (es. 10% di sconto).
        -   *Quando impostato su "Importo":* Il codice sconto offrirà un valore monetario fisso di sconto sul totale dell'ordine (es. 5€ di sconto).
    -   **Valore consigliato:** "Percentuale" o "Importo" in base alla tua strategia di marketing.
    -   **Scenario / esempio per il commerciante:** Se vuoi incoraggiare ordini più grandi, uno sconto percentuale potrebbe essere più attraente. Per acquisti più piccoli e frequenti, un importo fisso potrebbe essere più efficace.

-   **Valore sconto:**
    -   **Cosa fa questa impostazione:** Specifica il valore effettivo dello sconto.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se "Tipo di sconto" è Percentuale:* Inserisci il valore percentuale (es. `10` per 10%).
        -   *Se "Tipo di sconto" è Importo:* Inserisci il valore monetario (es. `5.00` per 5€).
    -   **Valore consigliato:** Un valore che sia attraente per i clienti ma anche redditizio per la tua attività (es. `10` per il 10% di sconto, o `5.00` per 5€ di sconto).
    -   **Scenario / esempio per il commerciante:** Decidi di offrire uno sconto del 15% per la condivisione. Imposteresti "Tipo di sconto" su "Percentuale" e "Valore sconto" su `15`.

-   **Importo minimo per lo sconto:**
    -   **Cosa fa questa impostazione:** Imposta un totale minimo dell'ordine (prima della spedizione) che un cliente deve raggiungere per utilizzare il codice sconto generato.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando viene inserito un valore (es. `50.00`):* Il codice sconto sarà valido solo se il totale del carrello del cliente è uguale o superiore a questo importo.
        -   *Quando lasciato vuoto o impostato su `0`:* Il codice sconto può essere utilizzato su qualsiasi ordine, indipendentemente dal suo valore totale.
    -   **Valore consigliato:** Un valore che incoraggi i clienti ad aggiungere più articoli al carrello, o `0` se non vuoi alcun minimo.
    -   **Scenario / esempio per il commerciante:** Per impedire ai clienti di utilizzare uno sconto del 10% su un articolo da 1€, potresti impostare un importo minimo di `25.00€`.

-   **Validità codice sconto (in giorni):**
    -   **Cosa fa questa impostazione:** Definisce quanti giorni sarà valido il codice sconto generato dal momento in cui viene emesso.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando viene inserito un valore (es. `7`):* Il codice sconto scadrà dopo 7 giorni, creando un senso di urgenza.
        -   *Quando lasciato vuoto o impostato su `0`:* Il codice sconto non avrà una data di scadenza (non consigliato, in quanto riduce l'urgenza).
    -   **Valore consigliato:** Da `7` a `30` giorni per incoraggiare un uso tempestivo.
    -   **Scenario / esempio per il commerciante:** Vuoi che i clienti utilizzino il loro sconto rapidamente. Impostando questo valore su `7` giorni li spingerà a effettuare un acquisto entro una settimana.

-   **Prefisso codice sconto:**
    -   **Cosa fa questa impostazione:** Ti consente di aggiungere un prefisso personalizzato a tutti i codici sconto generati. Questo ti aiuta a identificare i codici generati da questo modulo nella gestione degli sconti di PrestaShop.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando viene inserito un prefisso (es. `FBSHARE-`):* Tutti i codici generati inizieranno con questo prefisso (es. `FBSHARE-XYZ123`).
        -   *Quando lasciato vuoto:* I codici verranno generati senza un prefisso specifico.
    -   **Valore consigliato:** Un prefisso breve e descrittivo (es. `FB-`, `SHARE-`, `SOCIAL-`).
    -   **Scenario / esempio per il commerciante:** Per tracciare facilmente il successo della tua campagna di condivisione su Facebook, potresti usare `FB2023-` come prefisso.

-   **Visualizza pulsante di condivisione su:**
    -   **Cosa fa questa impostazione:** Determina dove apparirà il pulsante di condivisione di Facebook sulle tue pagine prodotto. Questa è tipicamente una selezione a discesa o a radio button.
    -   **Effetto della modifica di questa impostazione:**
        -   *Header:* Il pulsante appare nell'intestazione del negozio (meno comune per le condivisioni specifiche del prodotto).
        -   *Colonne (Sinistra/Destra):* Il pulsante appare in una delle colonne laterali.
        -   *Pagina prodotto (Contenuto principale):* Il pulsante appare all'interno dell'area principale delle informazioni sul prodotto (più comune e consigliato).
        -   *Footer:* Il pulsante appare nel piè di pagina del negozio.
    -   **Valore consigliato:** "Pagina prodotto (Contenuto principale)" per la massima visibilità e pertinenza.
    -   **Scenario / esempio per il commerciante:** Vuoi che il pulsante di condivisione sia facilmente visibile proprio accanto all'immagine e alla descrizione del prodotto. Selezionando "Pagina prodotto (Contenuto principale)" lo garantisci.

-   **Testo per il pulsante di condivisione:**
    -   **Cosa fa questa impostazione:** Ti consente di personalizzare il testo visualizzato sul pulsante di condivisione di Facebook.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando viene inserito del testo (es. "Condividi e ottieni sconto!"):* Il pulsante visualizzerà il tuo testo personalizzato.
        -   *Quando lasciato vuoto:* Verrà utilizzato un testo predefinito (es. "Condividi su Facebook").
    -   **Valore consigliato:** Testo chiaro e orientato all'azione che evidenzi il vantaggio (es. "Condividi per uno sconto!", "Ottieni X% di sconto - Condividi ora!").
    -   **Scenario / esempio per il commerciante:** Per invogliare i clienti, potresti cambiare il testo del pulsante in "Condividi e sblocca il tuo sconto!".

-   **Titolo messaggio popup:**
    -   **Cosa fa questa impostazione:** Imposta il titolo della finestra popup che appare dopo una condivisione riuscita, mostrando il codice sconto.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando viene inserito un titolo (es. "Congratulazioni!"):* Il popup mostrerà il tuo titolo personalizzato.
        -   *Quando lasciato vuoto:* Verrà utilizzato un titolo predefinito.
    -   **Valore consigliato:** Un titolo accogliente e congratulatorio (es. "Il tuo codice sconto!", "Grazie per aver condiviso!").
    -   **Scenario / esempio per il commerciante:** Vuoi far sentire il cliente ricompensato, quindi imposti il titolo su "Ecco il tuo sconto esclusivo!".

-   **Contenuto messaggio popup:**
    -   **Cosa fa questa impostazione:** Ti consente di personalizzare il contenuto del testo principale all'interno del popup del codice sconto. Puoi includere istruzioni o messaggi aggiuntivi.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando viene inserito del contenuto:* Il popup visualizzerà il tuo messaggio personalizzato.
        -   *Quando lasciato vuoto:* Verrà utilizzato un messaggio predefinito.
    -   **Valore consigliato:** Un messaggio chiaro che istruisca il cliente a copiare il codice e come usarlo (es. "Copia questo codice e applicalo al checkout per ricevere il tuo sconto.").
    -   **Scenario / esempio per il commerciante:** Vuoi ricordare ai clienti dove usare il codice: "Grazie per aver condiviso! Usa il codice qui sotto al checkout per i tuoi risparmi."

#### **Impostazioni avanzate (se disponibili)**

-   **Foglio di stile CSS per pulsante/popup:**
    -   **Cosa fa questa impostazione:** Ti consente di selezionare o inserire CSS personalizzato per stilizzare il pulsante di condivisione e/o il popup di sconto per abbinarli meglio al tuo tema.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando viene applicato CSS personalizzato:* L'aspetto visivo (colori, font, dimensioni) del pulsante e del popup cambierà in base ai tuoi stili.
        -   *Quando viene utilizzato il valore predefinito:* Il modulo utilizzerà la sua stilizzazione integrata.
    -   **Valore consigliato:** Lasciare vuoto inizialmente, quindi personalizzare se la stilizzazione predefinita non corrisponde al tuo brand.
    -   **Scenario / esempio per il commerciante:** Il tuo negozio utilizza una specifica tonalità di blu per i pulsanti. Puoi aggiungere una regola CSS qui per cambiare il colore di sfondo del pulsante di condivisione a quella tonalità.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Configurazione modulo | Abilita / Disabilita Modulo | SÌ | Attiva/disattiva tutte le funzionalità del modulo. |
| | ID App Facebook | Il tuo ID App | Collega il tuo negozio alla tua App Facebook per il tracciamento delle condivisioni. |
| | Tipo di sconto | Percentuale | Definisce se lo sconto è una percentuale o un importo fisso. |
| | Valore sconto | es. 10 (per 10%) | Il valore effettivo dello sconto offerto. |
| | Importo minimo per lo sconto | 0 (nessun minimo) | Imposta un valore minimo dell'ordine per l'utilizzo del codice sconto. |
| | Validità codice sconto (in giorni) | 7-30 giorni | Imposta un periodo di scadenza per i codici sconto generati. |
| | Prefisso codice sconto | FB- | Aggiunge un prefisso personalizzato ai codici generati per una facile identificazione. |
| | Visualizza pulsante di condivisione su | Pagina prodotto (Contenuto principale) | Controlla il posizionamento del pulsante di condivisione sulle pagine prodotto. |
| | Testo per il pulsante di condivisione | Condividi per uno sconto! | Personalizza il testo visualizzato sul pulsante di condivisione. |
| | Titolo messaggio popup | Il tuo codice sconto! | Imposta il titolo del popup del codice sconto. |
| | Contenuto messaggio popup | Copia questo codice... | Personalizza il messaggio principale all'interno del popup del codice sconto. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D1: Il pulsante di condivisione di Facebook non appare sulle mie pagine prodotto.**
**R1:**
*   **Controlla lo stato del modulo:** Assicurati che il modulo sia abilitato nelle impostazioni di configurazione.
*   **Verifica l'ID App Facebook:** Ricontrolla che il tuo ID App Facebook sia inserito correttamente nella configurazione del modulo. Un ID errato o mancante impedirà il caricamento del pulsante.
*   **Controlla il posizionamento del pulsante:** Conferma che l'impostazione "Visualizza pulsante di condivisione su" sia scelta correttamente (es. "Pagina prodotto (Contenuto principale)"). Se il tuo tema ha hook fortemente personalizzati, potresti dover provare posizionamenti diversi o consultare uno sviluppatore.
*   **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** nel tuo Back Office di PrestaShop e svuota la cache di Smarty e tutte le cache. A volte, i vecchi file di cache impediscono la visualizzazione di nuovi elementi del modulo.

**D2: I clienti condividono, ma non ricevono un codice sconto.**
**R2:**
*   **ID App Facebook:** Questa è la causa più comune. Il modulo si basa sull'ID App Facebook per tracciare le condivisioni riuscite. Assicurati che sia corretto e che la tua App Facebook sia configurata correttamente (es. l'URL del sito web è stato aggiunto).
*   **Permessi/Privacy di Facebook:** A volte, le impostazioni sulla privacy di Facebook di un cliente o i blocchi pubblicitari del browser possono interferire con il tracciamento delle condivisioni. Questo è meno comune ma può accadere.
*   **Configurazione del modulo:** Rivedi tutte le impostazioni relative allo sconto (Tipo di sconto, Valore, Validità). Assicurati che siano impostate su valori validi.
*   **Impostazioni voucher PrestaShop:** Assicurati che le impostazioni generali dei voucher/regole del carrello del tuo negozio PrestaShop non impediscano la creazione di nuovi codici (es. numero massimo di voucher raggiunto, anche se questo è raro).

**D3: Il popup del codice sconto ha un aspetto strano o non corrisponde al design del mio negozio.**
**R3:**
*   **Conflitti di tema:** Il tuo tema PrestaShop personalizzato potrebbe avere stili CSS in conflitto.
*   **CSS del modulo:** Il modulo include il proprio CSS. Puoi provare a sovrascriverlo.
*   **Soluzione:** Nella configurazione del modulo, cerca le opzioni "CSS personalizzato" o "Foglio di stile". Potrebbe essere necessario aggiungere regole CSS personalizzate lì per regolare l'aspetto del popup. Se non hai familiarità con il CSS, un webmaster o uno sviluppatore può aiutarti. Svuotare la cache del browser può anche a volte risolvere piccoli problemi di visualizzazione.

**D4: Posso tradurre il testo del pulsante e i messaggi popup in altre lingue?**
**R4:** Sì, il sistema di traduzione di PrestaShop supporta le traduzioni dei moduli.
*   Vai su **Internazionale > Traduzioni** nel tuo Back Office.
*   Seleziona "Traduzioni dei moduli installati", scegli il tuo tema e poi seleziona la tua lingua.
*   Trova il modulo "Condivisione prodotto Facebook + codice sconto" e potrai tradurre tutti i testi visibili all'utente, inclusi il testo del pulsante e i messaggi popup.

**D5: Cosa succede se un cliente condivide un prodotto più volte? Ottiene più sconti?**
**R5:** Il modulo è progettato per emettere un codice sconto unico per ogni *evento di condivisione riuscito* per un dato utente. Tuttavia, a seconda dell'implementazione esatta, un utente potrebbe essere in grado di condividere prodotti diversi e ricevere più codici. È generalmente buona pratica incoraggiare condivisioni uniche per ricompense uniche. Se vuoi limitarlo a un codice per cliente indipendentemente dalle condivisioni, potresti aver bisogno di uno sviluppo personalizzato o di gestire manualmente i voucher generati.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)
Questa sezione fornisce un'analisi approfondita della struttura tecnica del modulo "Condivisione prodotto Facebook + codice sconto" per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura
Il modulo segue un'architettura standard dei moduli PrestaShop, sfruttando principalmente la classe `Module` per l'installazione, la disinstallazione e la configurazione. Si integra con il front-office tramite hook per visualizzare il pulsante di condivisione e utilizza AJAX per gestire la generazione del codice sconto post-condivisione. La logica principale per la creazione del voucher è probabilmente incapsulata all'interno della classe principale del modulo o di un helper.

### 4.2 Controller (`controllers/`)
Questo modulo non sembra utilizzare file `ModuleFrontController` o `AdminController` dedicati nella directory `controllers/` in base all'inventario fornito. Le interazioni AJAX del front-office sono probabilmente gestite direttamente all'interno del file principale del modulo (`ajax_productlike.php`) o tramite un dispatcher AJAX generico di PrestaShop.

### 4.3 Classi e modelli principali (`classes/`)
In base all'inventario fornito, non ci sono classi `ObjectModel` personalizzate definite in una directory `classes/`. Il modulo probabilmente gestisce la sua configurazione direttamente tramite `Configuration::get()` e `Configuration::updateValue()` e crea oggetti `CartRule` di PrestaShop per gli sconti.

### 4.4 Risorse JavaScript (`views/js/`)
Il modulo include diversi file JavaScript, indicando la logica lato client per l'interazione con Facebook e la visualizzazione del popup.

-   `productlike/js/productlike.js`:
    *   **Ambito:** Front-office.
    *   **Responsabilità:** Probabilmente gestisce la logica principale per avviare la finestra di dialogo di condivisione di Facebook, ascoltare l'evento di completamento della condivisione dall'SDK di Facebook e quindi effettuare una chiamata AJAX al backend del negozio PrestaShop per richiedere il codice sconto. Gestirebbe anche la visualizzazione del popup del codice sconto.
    *   **Funzionalità chiave:** Inizializzazione dell'SDK di Facebook, chiamate al metodo `FB.ui` per la condivisione, richieste AJAX al backend del modulo, manipolazione del DOM per la visualizzazione del popup.

-   `productlike/js/script.js`:
    *   **Ambito:** Front-office.
    *   **Responsabilità:** Questo potrebbe essere uno script di utilità generale o un fallback/alternativa a `productlike.js`. Potrebbe contenere listener di eventi per il clic sul pulsante di condivisione, o gestire la logica di visualizzazione/nascondimento per il popup dello sconto.
    *   **Funzionalità chiave:** Binding di eventi, potenzialmente semplici animazioni o manipolazione del DOM.

-   `productlike/lib/voucherengine/script.js`:
    *   **Ambito:** Front-office.
    *   **Responsabilità:** Suggerisce uno script dedicato per la visualizzazione e l'interazione del voucher. Questo potrebbe gestire la copia del codice voucher negli appunti, la chiusura del popup o altri elementi dell'interfaccia utente relativi allo sconto.
    *   **Funzionalità chiave:** Interazione con l'API degli appunti, eventi di chiusura del popup, feedback dell'interfaccia utente.

### 4.5 Fogli di stile CSS (`views/css/`)
Il modulo utilizza diversi file CSS per stilizzare i suoi componenti del front-office.

-   `productlike/css/css.css`:
    *   **Ambito:** Stilizzazione del cliente del front-office.
    *   **Responsabilità:** Contiene stili generali per il pulsante di condivisione di Facebook e potenzialmente il popup del codice sconto.
    *   **Selettori chiave:** `.productlike-button`, `.productlike-popup`, `.productlike-voucher-code`. Gli sviluppatori possono sovrascriverli nel `custom.css` del loro tema o utilizzando l'input CSS personalizzato del modulo, se disponibile.

-   `productlike/css.css`:
    *   **Ambito:** Stilizzazione del cliente del front-office.
    *   **Responsabilità:** Potenzialmente un foglio di stile più vecchio o alternativo, o stili specifici per alcuni elementi non coperti da `css.css`.
    *   **Selettori chiave:** Simili a `css.css`, a seconda del suo contenuto.

-   `productlike/lib/voucherengine/ps16.css`:
    *   **Ambito:** Stilizzazione del cliente del front-office, specificamente per la compatibilità con PrestaShop 1.6.
    *   **Responsabilità:** Fornisce aggiustamenti di stile per garantire che il popup del voucher e il pulsante abbiano un aspetto corretto sui temi di PrestaShop 1.6, che potrebbero avere stili di elementi predefiniti diversi.
    *   **Selettori chiave:** Probabilmente mira agli elementi comuni dell'interfaccia utente di PrestaShop 1.6 per garantire la coerenza visiva.

### 4.6 Struttura del template Smarty (`views/templates/`)
Il modulo utilizza i template Smarty per il rendering dei suoi componenti del front-office.

-   **Template degli hook (`views/templates/hook/`)**:
    *   `productlike/header.tpl`:
        *   **Hook:** `displayHeader`
        *   **Scopo:** Questo template è probabilmente responsabile dell'inizializzazione dell'SDK JavaScript di Facebook, del caricamento dei file JavaScript necessari e potenzialmente del passaggio di variabili di configurazione (come l'ID App Facebook) dal backend del modulo al JavaScript del front-end. Assicura che l'API di Facebook sia pronta prima che il pulsante di condivisione venga renderizzato.
    *   `productlike/share.tpl`:
        *   **Hook:** `displayProductButtons`, `displayRightColumnProduct`, `displayLeftColumnProduct`, `displayFooterProduct` (o hook simili della pagina prodotto, a seconda della configurazione).
        *   **Scopo:** Renderizza il pulsante effettivo "Condividi su Facebook" sulla pagina prodotto. Conterrà la struttura HTML per il pulsante e potenzialmente un segnaposto per il popup del codice sconto, che viene poi popolato dinamicamente da JavaScript.

-   **Template di amministrazione (`views/templates/admin/`)**: Nessuno esplicitamente elencato, il che implica che la configurazione è gestita direttamente da `getContent()` nel file principale del modulo.

-   **Template del front-office (`views/templates/front/`)**: Nessuno esplicitamente elencato, poiché l'interazione principale avviene tramite hook e popup.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    *   Il modulo probabilmente non crea tabelle di database personalizzate.
    *   Le impostazioni di configurazione (ID App Facebook, valori di sconto, ecc.) sono memorizzate nella tabella `ps_configuration` utilizzando chiavi come `PRODUCTLIKE_FACEBOOK_APP_ID`, `PRODUCTLIKE_DISCOUNT_TYPE`, `PRODUCTLIKE_DISCOUNT_VALUE`, ecc.
    *   I codici sconto generati sono voci `CartRule` standard di PrestaShop, memorizzate in `ps_cart_rule` e tabelle correlate.

-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempistica di esecuzione | Scopo tecnico |
| :-------- | :--------------- | :---------------- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Inizializza l'SDK di Facebook, carica JS/CSS del modulo, passa variabili di configurazione. |
| `displayProductButtons` | Sulla pagina prodotto, tipicamente vicino al pulsante "Aggiungi al carrello". | Renderizza il pulsante di condivisione di Facebook. (Comune per PS 1.7+) |
| `displayRightColumnProduct` | Nella colonna destra della pagina prodotto. | Renderizza il pulsante di condivisione di Facebook (se configurato). |
| `displayLeftColumnProduct` | Nella colonna sinistra della pagina prodotto. | Renderizza il pulsante di condivisione di Facebook (se configurato). |
| `displayFooterProduct` | Nell'area del piè di pagina della pagina prodotto. | Renderizza il pulsante di condivisione di Facebook (se configurato). |
| `displayProductExtraContent` | Sulla pagina prodotto, per schede/blocchi di contenuto extra. | Hook alternativo per il posizionamento del pulsante (PS 1.7+). |
| `actionFrontControllerSetMedia` | Prima che il controller frontale renderizzi la pagina. | Registra i file JS e CSS del modulo. |
| `actionObjectCartRuleAddAfter` | Dopo che una nuova regola del carrello (voucher) è stata aggiunta. | Potenzialmente utilizzato per la registrazione o l'ulteriore elaborazione dei voucher generati. |

## 5. Supporto ufficiale e aggiornamenti
Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il tuo modulo "Condivisione prodotto Facebook + codice sconto", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team è dedicato a fornire assistenza e garantire che il tuo modulo funzioni in modo ottimale.
