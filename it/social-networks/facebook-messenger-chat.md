---
title: "Chat di Facebook Messenger - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Chat di Facebook Messenger di MyPresta.eu."
sidebar:
  label: "Chat di Facebook Messenger - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Facebook Messenger chat su MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-messenger-chat.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/facebook-messenger-chat/)
>
> ---


# Chat di Facebook Messenger

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e sono solitamente disponibili su tutti gli ambienti di hosting moderni. Nessuna estensione speciale è necessaria per questo modulo oltre ai requisiti standard di PrestaShop.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il tuo modulo Chat di Facebook Messenger. Qui troverai tutte le opzioni per personalizzare l'aspetto e il funzionamento della chat nel tuo negozio.

- **Cosa fa questa impostazione:** Questa è un'impostazione generale per i moduli MyPresta.eu per verificare la disponibilità di aggiornamenti.
- **Effetto della modifica di questa impostazione:**
  - *Quando abilitato (On):* Il modulo verificherà periodicamente MyPresta.eu per nuove versioni.
  - *Quando disabilitato (Off):* Il modulo non verificherà la disponibilità di aggiornamenti.
- **Valore consigliato:** **On** (È sempre bene rimanere aggiornati per sicurezza e nuove funzionalità).
- **Scenario / esempio del commerciante:** Mantenere questa impostazione su "On" ti assicura di essere avvisato quando è disponibile una nuova versione con correzioni di bug o nuove funzionalità, aiutando il tuo negozio a rimanere aggiornato e sicuro.

---

- **Cosa fa questa impostazione:** Questa opzione ti consente di scegliere tra due tipi di integrazione della chat di Facebook: una semplice chat della Pagina Facebook o la più avanzata chat di Facebook Messenger.
- **Effetto della modifica di questa impostazione:**
  - *Quando impostato su "Chat della Pagina Facebook":* Apparirà un widget di chat più semplice, principalmente per l'invio di messaggi alla tua Pagina Facebook.
  - *Quando impostato su "Chat di Facebook Messenger":* Apparirà il widget di chat completo di Facebook Messenger, offrendo un'esperienza di conversazione più ricca, inclusi messaggi di benvenuto e potenzialmente funzionalità più avanzate da Facebook.
- **Valore consigliato:** **Chat di Facebook Messenger** (Offre una migliore esperienza utente e più funzionalità).
- **Scenario / esempio del commerciante:** Se desideri l'esperienza Messenger completa e interattiva con messaggi di benvenuto, scegli "Chat di Facebook Messenger". Se preferisci un mittente di messaggi molto semplice e leggero, "Chat della Pagina Facebook" potrebbe essere sufficiente.

---

- **Cosa fa questa impostazione:** Questa impostazione aiuta a migliorare i punteggi di performance del tuo negozio su strumenti come Google PageSpeed Insights impedendo alla chat di Facebook di caricarsi immediatamente, il che a volte può bloccare il rendering della tua pagina.
- **Effetto della modifica di questa impostazione:**
  - *Quando abilitato (On):* Lo script della chat di Facebook si caricherà con un leggero ritardo o in modo non bloccante, il che può migliorare i tuoi punteggi di Google PageSpeed.
  - *Quando disabilitato (Off):* Lo script della chat di Facebook si caricherà normalmente, il che potrebbe influire leggermente sulle metriche di performance del caricamento della pagina.
- **Valore consigliato:** **On** (Consigliato per una migliore SEO e esperienza utente).
- **Scenario / esempio del commerciante:** Se sei preoccupato per le metriche di performance del tuo negozio e vuoi assicurarti che la chat non le influenzi negativamente, abilita questa opzione.

---

- **Cosa fa questa impostazione:** Controlla se l'SDK (Software Development Kit) dell'applicazione Facebook è incluso nel tuo sito web. L'SDK è necessario per la piena funzionalità della chat di Facebook Messenger, in particolare per funzionalità come l'identificazione degli utenti loggati.
- **Effetto della modifica di questa impostazione:**
  - *Quando abilitato (On):* L'SDK di Facebook verrà caricato, abilitando tutte le funzionalità della chat di Messenger.
  - *Quando disabilitato (Off):* Alcune funzionalità avanzate di Messenger, in particolare quelle relative all'identificazione dell'utente e ai saluti personalizzati, potrebbero non funzionare correttamente.
- **Valore consigliato:** **On** (Richiesto per la piena funzionalità della chat di Messenger).
- **Scenario / esempio del commerciante:** Se vuoi che la chat riconosca se un cliente è loggato a Facebook e visualizzi un saluto personalizzato, devi abilitare questa opzione.

---

- **Cosa fa questa impostazione:** Questo è il tuo identificatore univoco per la tua applicazione Facebook. Devi creare un'App Facebook sul sito web per sviluppatori di Facebook per ottenere questo ID. Collega il tuo sito web alla tua Pagina Facebook per funzionalità avanzate di Messenger.
- **Effetto della modifica di questa impostazione:**
  - *Quando inserito correttamente:* Abilita la piena funzionalità della chat di Facebook Messenger, inclusi saluti personalizzati e potenzialmente un'identificazione utente più accurata.
  - *Quando errato o vuoto:* La chat di Messenger potrebbe non funzionare correttamente o affatto.
- **Valore consigliato:** Il tuo **ID App Facebook** effettivo. (Lascia vuoto se "Includi SDK applicazione Facebook" è Off).
- **Scenario / esempio del commerciante:** Per utilizzare le funzionalità avanzate della chat di Messenger, dovrai andare su [developers.facebook.com](https://developers.facebook.com/), creare un'app, collegarla alla tua Pagina Facebook e quindi copiare l'ID dell'App qui.

---

- **Cosa fa questa impostazione:** Questa ti consente di specificare la lingua per l'interfaccia della chat di Facebook Messenger.
- **Effetto della modifica di questa impostazione:**
  - *Quando viene selezionato un codice lingua:* Il widget della chat visualizzerà il testo (come "Inviaci un messaggio") nella lingua scelta.
  - *Quando lasciato vuoto o errato:* La chat potrebbe impostare la lingua predefinita su inglese o sulla lingua del browser.
- **Valore consigliato:** Seleziona la lingua principale del tuo negozio, ad esempio, `en_US` per l'inglese (Stati Uniti), `fr_FR` per il francese (Francia), `es_ES` per lo spagnolo (Spagna).
- **Scenario / esempio del commerciante:** Se il tuo negozio serve principalmente clienti in Germania, impostando questo su `de_DE` ti assicurerai che l'interfaccia della chat sia in tedesco, rendendola più user-friendly per i tuoi clienti locali.

---

- **Cosa fa questa impostazione:** Questo è l'URL della tua Fan Page di Facebook. È fondamentale in quanto indica al widget della chat dove inviare i messaggi.
- **Effetto della modifica di questa impostazione:**
  - *Quando inserito correttamente:* I messaggi inviati tramite il widget della chat andranno direttamente alla casella di posta della tua Pagina Facebook.
  - *Quando errato o vuoto:* Il widget della chat non sarà in grado di connettersi alla tua pagina e i messaggi non verranno consegnati.
- **Valore consigliato:** L'URL completo della tua Fan Page di Facebook, ad esempio, `https://www.facebook.com/MyPresta.eu`.
- **Scenario / esempio del commerciante:** Se la tua Pagina Facebook è `https://www.facebook.com/MyAwesomeStore/`, dovresti inserire quell'URL qui in modo che i clienti possano raggiungerti.

---

- **Cosa fa questa impostazione:** Questo è il messaggio iniziale visualizzato ai clienti che sono già loggati a Facebook quando aprono la chat.
- **Effetto della modifica di questa impostazione:**
  - *Quando impostato:* I clienti loggati vedranno questo saluto personalizzato, rendendo l'interazione più accogliente.
  - *Quando vuoto:* Potrebbe essere utilizzato un saluto predefinito di Facebook, o non apparirà alcun saluto.
- **Valore consigliato:** Un saluto amichevole e conciso, ad esempio, "Ciao [Nome Cliente], come possiamo aiutarti oggi?"
- **Scenario / esempio del commerciante:** Potresti impostare questo su "Bentornato! Come possiamo aiutarti con i tuoi acquisti oggi?" per far sentire i clienti di ritorno apprezzati.

---

- **Cosa fa questa impostazione:** Questo è il messaggio iniziale visualizzato ai clienti che NON sono loggati a Facebook quando aprono la chat.
- **Effetto della modifica di questa impostazione:**
  - *Quando impostato:* I clienti non loggati vedranno questo saluto, incoraggiandoli ad avviare una conversazione.
  - *Quando vuoto:* Potrebbe essere utilizzato un saluto predefinito di Facebook, o non apparirà alcun saluto.
- **Valore consigliato:** Un messaggio chiaro e invitante, ad esempio, "Ciao! Siamo qui per aiutarti. Chiedici qualsiasi cosa!"
- **Scenario / esempio del commerciante:** Per i nuovi visitatori, potresti usare "Ciao! Hai una domanda sui nostri prodotti? Chatta con noi!"

---

- **Cosa fa questa impostazione:** Questo è l'ID numerico della tua Pagina Facebook. Puoi trovarlo nella sezione "Informazioni" della tua Pagina Facebook o utilizzando uno strumento di ricerca ID Pagina Facebook. È essenziale per collegare il widget della chat alla tua pagina specifica.
- **Effetto della modifica di questa impostazione:**
  - *Quando inserito correttamente:* Il widget della chat identificherà e si connetterà correttamente alla tua Pagina Facebook.
  - *Quando errato o vuoto:* Il widget della chat non funzionerà, poiché non saprà a quale pagina connettersi.
- **Valore consigliato:** Il tuo **ID Pagina Facebook** effettivo.
- **Scenario / esempio del commerciante:** Se il tuo ID Pagina Facebook è `123456789012345`, dovresti inserire quel numero qui. Questo è distinto dall'ID App.

---

- **Cosa fa questa impostazione:** Controlla la posizione del widget della chat sul tuo sito web.
- **Effetto della modifica di questa impostazione:**
  - *Quando impostato su "Sinistra":* L'icona/pannello della chat apparirà sul lato inferiore sinistro dello schermo.
  - *Quando impostato su "Destra":* L'icona/pannello della chat apparirà sul lato inferiore destro dello schermo.
- **Valore consigliato:** **Destra** (Questa è una posizione comune e spesso meno invasiva, poiché molti siti web hanno navigazione o altri elementi a sinistra).
- **Scenario / esempio del commerciante:** Se la navigazione principale del tuo sito web o un banner cruciale si trova a sinistra, sceglieresti "Destra" per evitare di oscurarlo.

---

- **Cosa fa questa impostazione:** Questo è il testo che appare come titolo della finestra di chat o del pannello scorrevole prima che inizi una conversazione.
- **Effetto della modifica di questa impostazione:**
  - *Quando impostato:* I clienti vedranno questo titolo, indicando chiaramente a cosa serve la chat.
  - *Quando vuoto:* Potrebbe essere utilizzato un titolo predefinito, o non apparirà alcun titolo, il che può essere confuso.
- **Valore consigliato:** Un titolo chiaro e invitante, ad esempio, "Chatta con noi!", "Supporto Clienti" o "Domande?".
- **Scenario / esempio del commerciante:** Impostando questo su "Hai bisogno di aiuto?" rende chiaro ai clienti che possono ottenere assistenza tramite la chat.

---

- **Cosa fa questa impostazione:** Questa ti consente di personalizzare il colore del testo all'interno del widget della chat di Facebook.
- **Effetto della modifica di questa impostazione:**
  - *Quando viene inserito un codice colore:* Il testo nel widget della chat verrà visualizzato nel colore scelto.
  - *Quando vuoto:* Verrà utilizzato il colore del testo predefinito di Facebook Messenger.
- **Valore consigliato:** Scegli un colore che contrasti bene con il colore di sfondo e si abbini al tuo brand. Usa un codice colore esadecimale (es. `#FFFFFF` per il bianco, `#000000` per il nero).
- **Scenario / esempio del commerciante:** Se i colori del tuo brand sono blu scuro e bianco, potresti impostare il colore del carattere su `#FFFFFF` (bianco) se il colore di sfondo è blu scuro.

---

- **Cosa fa questa impostazione:** Questa ti consente di personalizzare il colore di sfondo del widget della chat di Facebook.
- **Effetto della modifica di questa impostazione:**
  - *Quando viene inserito un codice colore:* Lo sfondo del widget della chat verrà visualizzato nel colore scelto.
  - *Quando vuoto:* Verrà utilizzato il colore di sfondo predefinito di Facebook Messenger.
- **Valore consigliato:** Scegli un colore che si integri con il design del tuo negozio. Usa un codice colore esadecimale (es. `#F0F2F5` per il grigio chiaro, `#3B5998` per il blu di Facebook).
- **Scenario / esempio del commerciante:** Per integrare la chat senza soluzione di continuità con il design del tuo negozio, potresti impostare il colore di sfondo su un grigio tenue o un colore della tua palette di brand.

---

- **Cosa fa questa impostazione:** Questa ti consente di personalizzare il colore principale di accento della chat di Facebook Messenger, come il pulsante di invio o gli elementi attivi.
- **Effetto della modifica di questa impostazione:**
  - *Quando viene inserito un codice colore:* Gli elementi interattivi chiave nel widget della chat verranno visualizzati nel colore scelto.
  - *Quando vuoto:* Verrà utilizzato il colore di accento predefinito di Facebook Messenger (tipicamente il blu di Facebook).
- **Valore consigliato:** Scegli un colore che si allinei con il colore di accento primario o secondario del tuo brand. Usa un codice colore esadecimale (es. `#1877F2` per il blu di Facebook, o il colore della call-to-action del tuo brand).
- **Scenario / esempio del commerciante:** Se i pulsanti di call-to-action del tuo negozio sono verdi, impostando questo su un verde simile (`#28A745`) farà sì che il widget della chat si senta più integrato con il tuo sito.

---

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Aggiornamenti MyPresta.eu | On | Abilita i controlli degli aggiornamenti del modulo per sicurezza e funzionalità. |
| Configurazione Modulo | Tipo di chat | Chat di Facebook Messenger | Seleziona tra la chat base della Pagina Facebook e l'esperienza Messenger completa. |
| Configurazione Modulo | Disabilita chat per Google Insights | On | Migliora i punteggi di PageSpeed ritardando il caricamento dello script della chat. |
| Configurazione Modulo | Includi SDK applicazione Facebook | On | Abilita funzionalità avanzate di Messenger come i saluti personalizzati. |
| Configurazione Modulo | Il tuo ID APP | Il tuo ID App Facebook | Collega il tuo sito web alla tua App Facebook per la piena funzionalità di Messenger. |
| Configurazione Modulo | Codici lingua APP Facebook | `en_US` (o la lingua del tuo negozio) | Imposta la lingua per l'interfaccia della chat. |
| Configurazione Modulo | URL della fanpage di Facebook (ricevitore messaggi) | URL della tua Pagina Facebook | Invia i messaggi dei clienti alla casella di posta della tua Pagina Facebook. |
| Configurazione Modulo | Messaggio di benvenuto per loggati | "Ciao [Nome Cliente], come possiamo aiutarti oggi?" | Saluto personalizzato per gli utenti Facebook loggati. |
| Configurazione Modulo | Messaggio di benvenuto per non loggati | "Ciao! Siamo qui per aiutarti. Chiedici qualsiasi cosa!" | Messaggio invitante per gli utenti non loggati a Facebook. |
| Configurazione Modulo | Il tuo ID pagina Facebook | Il tuo ID Pagina Facebook | Identifica la tua specifica Pagina Facebook per la connessione della chat. |
| Configurazione Modulo | Dove visualizzare? | Destra | Posiziona il widget della chat sul lato sinistro o destro dello schermo. |
| Configurazione Modulo | Titolo del pannello scorrevole | "Chatta con noi!" | Testo visualizzato come titolo della finestra di chat. |
| Configurazione Modulo | Colore carattere chat Facebook | `#000000` (nero) o il colore del tuo brand | Personalizza il colore del testo all'interno del widget della chat. |
| Configurazione Modulo | Colore sfondo chat Facebook | `#F0F2F5` (grigio chiaro) o il colore del tuo brand | Personalizza il colore di sfondo del widget della chat. |
| Configurazione Modulo | Colore Facebook Messenger | `#1877F2` (blu Facebook) o il colore del tuo brand | Personalizza il colore di accento degli elementi interattivi della chat. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Il widget della chat non appare nel mio negozio. Cosa devo fare?**
R:

1.  **Controlla lo stato del modulo:** Vai su **Moduli > Gestione moduli** e assicurati che il modulo "Chat di Facebook Messenger" sia installato e abilitato.
2.  **Verifica la configurazione:** Ricontrolla tutte le impostazioni nella pagina di configurazione del modulo, in particolare "Il tuo ID APP", "URL della fanpage di Facebook" e "Il tuo ID pagina Facebook". Anche un singolo carattere errato può impedirne il funzionamento.
3.  **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). A volte, i vecchi file di cache impediscono la visualizzazione dei nuovi moduli.
4.  **Compatibilità del tema:** Se stai utilizzando un tema altamente personalizzato, potrebbe esserci un conflitto. Passa temporaneamente al tema PrestaShop predefinito per vedere se la chat appare. Se lo fa, il tuo tema potrebbe richiedere una piccola modifica.

**D: I miei messaggi di benvenuto non vengono visualizzati, o la chat non riconosce gli utenti loggati.**
R:

1.  **Abilita SDK:** Assicurati che "Includi SDK applicazione Facebook" sia impostato su **On**.
2.  **Fornisci ID APP:** Assicurati che "Il tuo ID APP" sia inserito correttamente. Devi creare un'App Facebook e collegarla alla tua pagina per ottenerlo.
3.  **Accesso a Facebook:** Il cliente deve essere loggato a Facebook nel proprio browser affinché il saluto personalizzato funzioni.

**D: Il widget della chat sembra fuori posto o non si abbina al design del mio negozio.**
R:

1.  **Usa le impostazioni colore:** Vai alla configurazione del modulo e regola "Colore carattere chat Facebook", "Colore sfondo chat Facebook" e "Colore Facebook Messenger" per abbinarli alla palette del tuo brand.
2.  **Posizionamento:** Sperimenta con l'impostazione "Dove visualizzare?" (Sinistra/Destra) per trovare la posizione meno invasiva per il tuo sito.

**D: Come trovo il mio ID Pagina Facebook e l'ID App?**
R:

-   **ID Pagina Facebook:** Vai alla tua Pagina Facebook, clicca su "Informazioni" nel menu a sinistra. Scorri verso il basso e dovresti vedere "ID Pagina".
-   **ID App Facebook:** Devi creare un account sviluppatore Facebook e quindi creare una nuova App. Una volta creata, l'ID App sarà visibile nella tua Dashboard App. Assicurati di collegare questa App alla tua Pagina Facebook.

**D: Questo modulo rallenterà il mio sito web?**
R: L'SDK di Facebook a volte può influire sui tempi di caricamento della pagina. Tuttavia, il modulo include un'opzione "Disabilita chat per Google Insights". L'abilitazione di questa opzione può aiutare a mitigare gli impatti sulle prestazioni caricando lo script in modo non bloccante, migliorando i tuoi punteggi di PageSpeed.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo `Chat di Facebook Messenger` (`fbchat`) è un modulo PrestaShop standard che segue un modello simile a MVC all'interno dell'ambito del modulo. Sfrutta principalmente il sistema di hook di PrestaShop per iniettare JavaScript e HTML nel front-office. La configurazione è gestita tramite il metodo `getContent()` nella classe principale del modulo, memorizzando le impostazioni in `ps_configuration`. Il modulo si integra direttamente con l'SDK della piattaforma Facebook Messenger, basandosi su risorse esterne di Facebook per la sua funzionalità principale.

### 4.2 Controller (`controllers/`)

Questo modulo **non** contiene alcun controller Front-Office o Back-Office Admin personalizzato. Tutta la logica è gestita all'interno del file principale del modulo (`fbchat.php`) e iniettata tramite hook.

### 4.3 Classi e Modelli Core (`classes/`)

Questo modulo **non** definisce alcuna classe personalizzata o istanza di `ObjectModel` nella directory `classes/`. Tutta la gestione dei dati viene eseguita direttamente tramite la classe `Configuration` per le impostazioni.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`fbchat/jscolor/jscolor.js`**

    -   **Ambito:** Back-office (pagina di configurazione Admin).
    -   **Scopo:** Questa è una libreria JavaScript di terze parti per un selettore di colori. Viene utilizzata nella pagina di configurazione del modulo per fornire un'interfaccia user-friendly per la selezione dei colori per il widget della chat (es. colore del carattere, colore di sfondo).
    -   **Interazione:** Collega la funzionalità del selettore di colori a specifici campi di input nel modulo di amministrazione.
-   **`fbchat/js/fbchat.js`**

    -   **Ambito:** Front-office.
    -   **Scopo:** Questo JavaScript personalizzato gestisce il caricamento dinamico e l'inizializzazione del widget della chat di Facebook Messenger. Contiene la logica per caricare condizionatamente l'SDK di Facebook e la chat di Messenger in base alle impostazioni del modulo e potenzialmente ai flag di ottimizzazione delle prestazioni.
    -   **Interazione:**
        -   Controlla la configurazione `fbchat_hack` per determinare se il caricamento ritardato per Google Insights è abilitato.
        -   Crea e aggiunge dinamicamente lo script SDK di Facebook (`sdk.js`) al `<body>` se `fbchat_appsdk` è abilitato.
        -   Inizializza il plugin `FB.CustomerChat` con parametri recuperati dalla configurazione del modulo (es. `page_id`, `app_id`, `theme_color`, `logged_in_greeting`, `logged_out_greeting`, `locale`).
        -   Gestisce il posizionamento del widget della chat in base a `fbchat_side`.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`fbchat/css.css`**

    -   **Ambito:** Back-office (pagina di configurazione Admin).
    -   **Scopo:** Contiene stili specifici per il modulo di configurazione del modulo nel Back Office di PrestaShop. Questo potrebbe includere stili per campi di input, pulsanti o elementi di layout personalizzati all'interno dell'output di `getContent()`.
    -   **Selettori chiave:** Probabilmente si rivolge a elementi all'interno del modulo di configurazione del modulo.
-   **`fbchat/css/fbchat_left.css`**

    -   **Ambito:** Front-office.
    -   **Scopo:** Fornisce regolazioni di stile per il widget della chat di Facebook Messenger quando la sua posizione è impostata sul lato "Sinistra" dello schermo. Questo potrebbe includere proprietà CSS `right` o `left` per controllare la sua posizione fissa.
    -   **Selettori chiave:** Si rivolge al contenitore principale della chat o al suo wrapper per garantire il corretto allineamento a sinistra.
-   **`fbchat/css/fbchat_right.css`**

    -   **Ambito:** Front-office.
    -   **Scopo:** Fornisce regolazioni di stile per il widget della chat di Facebook Messenger quando la sua posizione è impostata sul lato "Destra" dello schermo. Questo potrebbe includere proprietà CSS `right` o `left` per controllare la sua posizione fissa.
    -   **Selettori chiave:** Si rivolge al contenitore principale della chat o al suo wrapper per garantire il corretto allineamento a destra.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **`fbchat/admin-script.tpl`**

    -   **Ambito:** Back-office (pagina di configurazione Admin).
    -   **Scopo:** Questo template è probabilmente utilizzato per iniettare codice JavaScript (es. per l'inizializzazione del selettore di colori da `jscolor.js`) o stili specifici nella pagina di configurazione del modulo. Viene renderizzato all'interno del metodo `getContent()`.
    -   **Variabili:** Può ricevere variabili di configurazione per impostare dinamicamente i valori iniziali del selettore di colori.
-   **`fbchat/fbchat.tpl`**

    -   **Ambito:** Front-office.
    -   **Scopo:** Questo è il template principale del front-office responsabile del rendering della struttura HTML necessaria e dell'inizializzazione JavaScript per il widget della chat di Facebook Messenger. È tipicamente agganciato a `displayFooter` o `displayHeader`.
    -   **Variabili:** Riceve tutte le variabili di configurazione necessarie dai metodi `hookDisplayFooter` o `hookDisplayHeader` del modulo, come `fbchat_fanid`, `fbchat_appid`, `fbchat_theme`, `fbchat_bg`, `fbchat_color`, `fbchat_langarray`, `fbchat_hello_logged`, `fbchat_hello_unlogged`, `fbchat_hack`, `fbchat_appsdk`, `fbchat_type`, `fbchat_side`.
    -   **Output:** Genera l'elemento `<div class="fb-customerchat">` e il tag `<script>` per l'inizializzazione dell'SDK di Facebook.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**:

    -   Questo modulo non crea tabelle SQL personalizzate.
    -   Tutte le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` utilizzando chiavi come `mypresta_updates`, `fbchat_theme`, `fbchat_bg`, `fbchat_color`, `fbchat_fanpage`, `fbchat_positions`, `fbchat_hack`, `fbchat_appsdk`, `fbchat_type`, `fbchat_fanid`, `fbchat_appid`, `fbchat_title`, `fbchat_langarray`, `fbchat_hello_logged`, `fbchat_hello_unlogged`, `fbchat_side`.
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Eseguito nella sezione `<head>` di ogni pagina del front-office. | Utilizzato per includere file CSS (`fbchat_left.css`, `fbchat_right.css`) ed eventualmente alcuni JavaScript iniziali se necessari all'inizio del caricamento della pagina. |
| `displayFooter` | Eseguito appena prima del tag di chiusura `</body>` di ogni pagina del front-office. | Questo è l'hook principale per il rendering del template `fbchat.tpl`, che include l'HTML della chat di Facebook Messenger e inizializza lo script `fbchat.js`. Posizionarlo qui assicura che il contenuto principale della pagina si carichi per primo, migliorando le prestazioni percepite. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e le ultime versioni del modulo "Chat di Facebook Messenger", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda relativa alla funzionalità o all'integrazione del modulo.
