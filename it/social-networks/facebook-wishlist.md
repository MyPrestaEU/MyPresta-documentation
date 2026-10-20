---
title: "Facebook Wishlist - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Facebook Wishlist di MyPresta.eu."
sidebar:
  label: "Facebook Wishlist - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Facebook Wishlist su MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-wishlist.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/facebook-wishlist/)
>
> ---


# Facebook Wishlist

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e sono solitamente disponibili per impostazione predefinita. Nessun requisito di hosting speciale oltre a una configurazione PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo Facebook Wishlist in Gestione moduli. Questo ti porterà alla schermata di configurazione principale.

#### **ID App Facebook**

-   **Cosa fa questa impostazione:** Questo è un identificatore univoco fornito da Facebook per la tua applicazione specifica (in questo caso, l'integrazione del tuo negozio PrestaShop con Facebook). Indica a Facebook quale app sta richiedendo l'azione della lista dei desideri.
-   **Effetto della modifica di questa impostazione:**
    -   *Se inserito correttamente:* Il pulsante "Aggiungi alla lista dei desideri di Facebook" funzionerà correttamente, consentendo di aggiungere prodotti alle timeline di Facebook.
    -   *Se errato o vuoto:* Il pulsante probabilmente non funzionerà, o Facebook visualizzerà un errore, impedendo ai clienti di aggiungere prodotti alle loro liste dei desideri.
-   **Valore consigliato:** Questo campo *deve* contenere il tuo ID App Facebook valido. Dovrai creare un'App Facebook sul sito web [Facebook per Sviluppatori](https://developers.facebook.com/) per ottenere questo ID.
-   **Scenario / esempio del commerciante:** Hai creato un'App Facebook per il tuo negozio e Facebook ti ha dato un ID App come `123456789012345`. Inseriresti questo numero esatto qui. Senza di esso, Facebook non saprà quale negozio sta cercando di condividere contenuti.

#### **Segreto App Facebook**

-   **Cosa fa questa impostazione:** Questa è una chiave segreta associata al tuo ID App Facebook. Viene utilizzata per la comunicazione sicura tra il tuo negozio PrestaShop e i server di Facebook. Aiuta a verificare che le richieste provengano dalla tua applicazione legittima.
-   **Effetto della modifica di questa impostazione:**
    -   *Se inserito correttamente:* La comunicazione sicura è stabilita e il modulo funziona come previsto.
    -   *Se errato o vuoto:* La comunicazione con Facebook potrebbe fallire, portando a errori o funzionalità della lista dei desideri non funzionanti.
-   **Valore consigliato:** Questo campo *deve* contenere il tuo Segreto App Facebook valido. Come l'ID App, lo ottieni dalle impostazioni della tua App Facebook sul sito web [Facebook per Sviluppatori](https://developers.facebook.com/). Mantieni questo segreto al sicuro e non condividerlo mai pubblicamente.
-   **Scenario / esempio del commerciante:** Dopo aver creato la tua App Facebook, troverai sia l'ID App che il Segreto App nella dashboard della tua app. Il segreto potrebbe assomigliare a una lunga stringa di lettere e numeri (ad esempio, `abcdef1234567890abcdef1234567890`). Inseriscilo esattamente come fornito da Facebook.

#### **URL Pagina Facebook**

-   **Cosa fa questa impostazione:** Questo ti consente di collegare la Pagina Facebook ufficiale del tuo negozio alla funzionalità della lista dei desideri. Quando i clienti interagiscono con la lista dei desideri, a volte può fare riferimento o collegarsi alla tua Pagina Facebook principale.
-   **Effetto della modifica di questa impostazione:**
    -   *Se inserito correttamente:* Migliora la visibilità del marchio su Facebook e fornisce un link diretto alla tua pagina ufficiale.
    -   *Se errato o vuoto:* Il modulo funzionerà comunque, ma potresti perdere l'opportunità di indirizzare gli utenti alla tua presenza principale su Facebook.
-   **Valore consigliato:** Inserisci l'URL completo della Pagina Facebook ufficiale del tuo negozio (ad esempio, `https://www.facebook.com/NomeDelTuoNegozio`). Se non hai una pagina ufficiale, puoi lasciarlo vuoto.
-   **Scenario / esempio del commerciante:** Il tuo negozio ha una Pagina Facebook all'indirizzo `https://www.facebook.com/MyPrestaEu`. Inserire questo URL qui assicura che qualsiasi condivisione sociale relativa alla lista dei desideri possa potenzialmente indirizzare gli utenti alla tua pagina principale del marchio su Facebook.

#### **Posizione del pulsante**

-   **Cosa fa questa impostazione:** Questo controlla dove appare il pulsante "Aggiungi alla lista dei desideri di Facebook" sulle tue pagine prodotto.
-   **Effetto della modifica di questa impostazione:**
    -   *Se impostato su 'Pagina prodotto':* Il pulsante verrà visualizzato in modo prominente nella pagina dei dettagli del prodotto, tipicamente vicino al pulsante "Aggiungi al carrello". Questa è la posizione più comune e consigliata.
    -   *Se impostato su altre opzioni (ad esempio, 'Intestazione', 'Colonne', 'Piè di pagina'):* Il modulo potrebbe tentare di visualizzare il pulsante in queste aree, ma la sua funzionalità è principalmente legata a informazioni specifiche sul prodotto, rendendo 'Pagina prodotto' la scelta più logica. Altre posizioni potrebbero non visualizzare il pulsante o potrebbero non funzionare correttamente senza un contesto di prodotto specifico.
-   **Valore consigliato:** **Pagina prodotto**. Questo assicura che il pulsante sia visibile quando i clienti stanno visualizzando attivamente un prodotto che potrebbero voler aggiungere alla lista dei desideri.
-   **Scenario / esempio del commerciante:** Vuoi che i clienti trovino facilmente il pulsante della lista dei desideri proprio quando stanno considerando di acquistare un prodotto. Impostando questo su 'Pagina prodotto' lo posiziona logicamente accanto ad altre azioni relative all'acquisto.

#### **Mostra pulsante sulla pagina prodotto**

-   **Cosa fa questa impostazione:** Questo è un semplice interruttore ON/OFF per abilitare o disabilitare la visualizzazione del pulsante "Aggiungi alla lista dei desideri di Facebook" sulle tue pagine prodotto.
-   **Effetto della modifica di questa impostazione:**
    -   *Se abilitato (SÌ):* Il pulsante sarà visibile e funzionante su tutte le pagine prodotto.
    -   *Se disabilitato (NO):* Il pulsante sarà nascosto e i clienti non potranno aggiungere prodotti alle loro liste dei desideri di Facebook tramite il tuo negozio.
-   **Valore consigliato:** **SÌ**. Per utilizzare la funzionalità principale del modulo, questo dovrebbe essere sempre abilitato.
-   **Scenario / esempio del commerciante:** Hai completato tutta la configurazione e vuoi che i tuoi clienti inizino a utilizzare la funzione. Imposteresti questo su SÌ. Se vuoi temporaneamente nascondere la funzione per manutenzione o una campagna, potresti impostarla su NO.

#### **Mostra pulsante sulla pagina categoria**

-   **Cosa fa questa impostazione:** Questo controlla se il pulsante "Aggiungi alla lista dei desideri di Facebook" appare negli elenchi di prodotti all'interno delle pagine di categoria.
-   **Effetto della modifica di questa impostazione:**
    -   *Se abilitato (SÌ):* Un pulsante della lista dei desideri apparirà accanto a ogni prodotto nelle pagine di categoria e di elenco. Questo può essere utile per una rapida aggiunta alla lista dei desideri, ma potrebbe ingombrare il layout a seconda del tuo tema.
    -   *Se disabilitato (NO):* Il pulsante apparirà solo sulle singole pagine prodotto, mantenendo le pagine di categoria più pulite.
-   **Valore consigliato:** **NO**. Sebbene potenzialmente utile, la visualizzazione del pulsante sulle pagine di categoria a volte può portare a un'esperienza utente meno ottimale o a un disordine visivo. È generalmente più efficace sulla pagina prodotto dedicata.
-   **Scenario / esempio del commerciante:** Hai un design della pagina di categoria molto pulito e vuoi ridurre al minimo le distrazioni. Imposteresti questo su NO, assicurando che l'azione della lista dei desideri sia disponibile solo quando un cliente è concentrato su un singolo prodotto.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | ID App Facebook | Il tuo ID App Facebook | Identificatore univoco per l'integrazione Facebook del tuo negozio. **Critico per la funzionalità.** |
| Configurazione Modulo | Segreto App Facebook | Il tuo Segreto App Facebook | Chiave sicura per la comunicazione con Facebook. **Critico per la funzionalità.** |
| Configurazione Modulo | URL Pagina Facebook | `https://www.facebook.com/NomeDelTuoNegozio` (se applicabile) | Collega alla tua Pagina Facebook ufficiale, migliorando la visibilità del marchio. |
| Configurazione Modulo | Posizione del pulsante | Pagina prodotto | Determina dove appare il pulsante della lista dei desideri. **Pagina prodotto è consigliata.** |
| Configurazione Modulo | Mostra pulsante sulla pagina prodotto | SÌ | Abilita/disabilita il pulsante sulle singole pagine prodotto. **Consigliato: SÌ.** |
| Configurazione Modulo | Mostra pulsante sulla pagina categoria | NO | Abilita/disabilita il pulsante negli elenchi di prodotti nelle pagine di categoria. **Consigliato: NO.** |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Il pulsante "Aggiungi alla lista dei desideri di Facebook" non appare sulle mie pagine prodotto.**
R:

-   **Controlla lo stato del modulo:** Assicurati che il modulo sia installato e abilitato in **Moduli > Gestione moduli**.
-   **Impostazioni di configurazione:** Vai alla pagina di configurazione del modulo e verifica che "Mostra pulsante sulla pagina prodotto" sia impostato su **SÌ**.
-   **ID/Segreto App Facebook:** Ricontrolla che il tuo ID App Facebook e il Segreto App siano inseriti correttamente. Credenziali errate impediranno il caricamento o il funzionamento del pulsante.
-   **Compatibilità del tema:** Alcuni temi altamente personalizzati potrebbero richiedere piccole modifiche. Se il pulsante non appare ancora, prova a passare temporaneamente al tema PrestaShop predefinito (Classic) per escludere un conflitto con il tema. Se appare su Classic, il tuo sviluppatore del tema potrebbe doverlo integrare.
-   **Svuota la cache:** Svuota sempre la cache di PrestaShop (**Parametri avanzati > Prestazioni**) e la cache del tuo browser dopo aver apportato modifiche alla configurazione.

**D2: Il pulsante appare, ma non succede nulla quando lo clicco, o ricevo un errore di Facebook.**
R:

-   **ID/Segreto App Facebook:** Questo è quasi sempre dovuto a un ID App Facebook o a un Segreto App errati o mancanti. Rivedi le impostazioni della tua app su Facebook per Sviluppatori e assicurati che i valori siano copiati con precisione.
-   **Impostazioni App Facebook:** Sulla piattaforma Facebook per Sviluppatori, assicurati che la tua app sia "Live" (non in modalità sviluppo) e che la piattaforma "Sito web" sia aggiunta con l'URL del tuo negozio configurato correttamente.
-   **Whitelisting del dominio:** Nelle impostazioni della tua App Facebook, sotto "Impostazioni > Base", assicurati che il dominio del tuo sito web sia elencato nel campo "Domini App".
-   **Tag Open Graph:** Il modulo si basa sui meta tag Open Graph predefiniti di PrestaShop per le informazioni sui prodotti. Assicurati che il tuo negozio PrestaShop li generi correttamente (puoi controllare il codice sorgente della tua pagina prodotto per i tag `<meta property="og:..."`).

**D3: Come ottengo un ID App Facebook e un Segreto App?**
R:

1.  Vai su [Facebook per Sviluppatori](https://developers.facebook.com/) e accedi con il tuo account Facebook.
2.  Clicca su "Le mie app" > "Crea app".
3.  Scegli il tipo di app (ad esempio, "Consumatore" o "Business") e segui le istruzioni per dare un nome alla tua app.
4.  Una volta creata, naviga su "Impostazioni > Base" nella dashboard della tua nuova app.
5.  Troverai il tuo **ID App** e il **Segreto App** lì.
6.  Assicurati di aggiungere il dominio del tuo sito web (ad esempio, `iltuonegozio.com`) al campo "Domini App" e salva le modifiche.
7.  Aggiungi una piattaforma "Sito web" alla tua app e inserisci l'URL del tuo sito.
8.  Infine, assicurati che la tua app sia impostata in modalità "Live" (di solito c'è un interruttore nella parte superiore della dashboard).

**D4: Questo modulo rallenterà il mio sito web?**
R: Il modulo stesso è molto leggero. L'interazione principale è un piccolo pulsante e un pop-up ospitato da Facebook, che carica i contenuti direttamente dai server di Facebook. Qualsiasi rallentamento percepito è più probabilmente correlato ai tempi di caricamento di Facebook o a problemi generali di prestazioni del sito web piuttosto che al modulo stesso.

**D5: Posso personalizzare l'aspetto del pulsante?**
R: Il modulo utilizza tipicamente lo stile standard dei pulsanti di Facebook o si integra con gli stili dei pulsanti esistenti del tuo tema. Sebbene non ci sia un'impostazione diretta nel modulo per cambiarne l'aspetto, uno sviluppatore web può personalizzarlo usando CSS, mirando alle specifiche classi o ID CSS dell'elemento del pulsante.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo Facebook Wishlist (`facebook-wishlist`) è un modulo PrestaShop semplice progettato principalmente per iniettare la funzionalità "Aggiungi alla lista dei desideri" basata su Open Graph nel front-office. Sfrutta il sistema di hook di PrestaShop per renderizzare il suo pulsante sulle pagine prodotto e si basa sull'SDK JavaScript di Facebook e sul protocollo Open Graph per la sua funzionalità principale. La configurazione del modulo è gestita tramite il metodo standard `getContent()` nel file principale del modulo, memorizzando le impostazioni in `ps_configuration`.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller front-office o back-office personalizzati. Tutta la logica è incapsulata nel file principale del modulo e nella sua configurazione.

### 4.3 Classi e Modelli Core (`classes/`)

Questo modulo non definisce classi o `ObjectModel` personalizzati. Tutta la configurazione è gestita tramite `Configuration::get()` e `Configuration::updateValue()`.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo non include file JavaScript personalizzati. Si basa sull'SDK JavaScript di Facebook, che viene tipicamente caricato in modo asincrono e gestito da Facebook stesso una volta che i meta tag Open Graph e l'ID App corretti sono presenti.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo non include file CSS personalizzati. L'aspetto del pulsante è gestito dallo stile predefinito di Facebook per i suoi plugin sociali o eredita gli stili dal tema PrestaShop attivo.

### 4.6 Struttura del template Smarty (`views/templates/`)

Questo modulo non contiene una directory `views/templates`. L'HTML del pulsante è probabilmente generato direttamente all'interno dei metodi hook del file principale del modulo.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**:
    Questo modulo non crea tabelle di database personalizzate. Tutte le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` utilizzando chiavi come `FACEBOOK_WISHLIST_APP_ID`, `FACEBOOK_WISHLIST_APP_SECRET`, `FACEBOOK_WISHLIST_PAGE_URL`, `FACEBOOK_WISHLIST_BUTTON_POSITION`, `FACEBOOK_WISHLIST_SHOW_PRODUCT_PAGE` e `FACEBOOK_WISHLIST_SHOW_CATEGORY_PAGE`.
-   **Tabella degli hook registrati**:
    Il modulo registra e utilizza i seguenti hook di PrestaShop:

    | Nome dell'Hook | Tempistica di Esecuzione | Scopo Tecnico |
    | --- | --- | --- |
    | `displayHeader` | Nella sezione `<head>` di ogni pagina. | Utilizzato per iniettare il codice di inizializzazione dell'SDK JavaScript di Facebook e i meta tag Open Graph (se non già presenti dal core di PrestaShop). Questo è cruciale affinché Facebook riconosca il tuo sito e la tua app. |
    | `displayProductButtons` | Sulla pagina prodotto, tipicamente vicino al pulsante "Aggiungi al carrello". | Renderizza il pulsante "Aggiungi alla lista dei desideri di Facebook". Questo è l'hook principale per la visualizzazione front-office del modulo. |
    | `displayProductListFunctionalButtons` | Sulle pagine di categoria/elenco, accanto a ogni prodotto. | Renderizza il pulsante "Aggiungi alla lista dei desideri di Facebook" per i prodotti negli elenchi, se abilitato nella configurazione. |
    | `displayFooter` | Nel piè di pagina di ogni pagina. | Potenzialmente utilizzato per il caricamento di script aggiuntivi o il posizionamento di pulsanti di fallback, sebbene `displayProductButtons` sia quello principale. |
    | `displayLeftColumn` | Nella colonna sinistra delle pagine. | Posizione alternativa per il pulsante, se configurato. |
    | `displayRightColumn` | Nella colonna destra delle pagine. | Posizione alternativa per il pulsante, se configurato. |

    La funzionalità principale del modulo si basa sull'hook `displayHeader` per garantire che l'SDK di Facebook sia caricato e sull'hook `displayProductButtons` (o `displayProductListFunctionalButtons`) per renderizzare il pulsante interattivo. Il pulsante stesso, quando cliccato, attiva l'azione Open Graph di Facebook `og:product:wishlist`, che richiede la presenza di specifici meta tag Open Graph (come `og:title`, `og:description`, `og:image`, `og:url`, `og:type=product`) nell'HTML della pagina prodotto. PrestaShop genera tipicamente questi tag per impostazione predefinita.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo Facebook Wishlist, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e all'integrazione del modulo.
