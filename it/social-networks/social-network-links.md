---
title: "Link ai Social Network - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Link ai Social Network di MyPresta.eu."
sidebar:
  label: "Link ai Social Network - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Social Network Links su MyPresta.eu](https://mypresta.eu/modules/social-networks/social-network-links.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/social-network-links/)
>
> ---


# Link ai Social Network

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti e solitamente preinstallate sulla maggior parte degli ambienti di web hosting.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Link ai Social Network)

Questa è la schermata di configurazione principale e unica per il modulo "Link ai Social Network". Qui definirai quali social network visualizzare e dove appariranno nel tuo negozio.

**Accesso:** Naviga su **Moduli > Gestione moduli**, cerca "Link ai Social Network" e clicca su "Configura".

#### **Impostazioni Generali**

- **URL Facebook:**

  - **Cosa fa questa impostazione:** Qui inserisci l'indirizzo web completo (URL) della tua pagina Facebook.
  - **Effetto della modifica di questa impostazione:**
    - *Se compilato:* Un'icona di Facebook apparirà nel blocco del modulo, collegandosi direttamente all'URL fornito.
    - *Se vuoto:* Nessuna icona di Facebook verrà visualizzata.
  - **Valore consigliato:** L'URL della tua pagina Facebook ufficiale (es. `https://www.facebook.com/nomedeltuonegozio`).
  - **Scenario / esempio per il commerciante:** Se la tua pagina Facebook è `https://www.facebook.com/IlMioFantasticoNegozio`, inserisci quell'URL qui. I clienti che cliccano sull'icona di Facebook verranno indirizzati alla tua pagina.
- **URL Twitter:**

  - **Cosa fa questa impostazione:** Inserisci l'indirizzo web completo (URL) del tuo profilo Twitter.
  - **Effetto della modifica di questa impostazione:**
    - *Se compilato:* Un'icona di Twitter apparirà, collegandosi al tuo profilo Twitter.
    - *Se vuoto:* Nessuna icona di Twitter verrà visualizzata.
  - **Valore consigliato:** L'URL del tuo profilo Twitter ufficiale (es. `https://twitter.com/nomedeltuonegozio`).
  - **Scenario / esempio per il commerciante:** Se il tuo handle Twitter è `@IlMioFantasticoNegozio`, il tuo URL potrebbe essere `https://twitter.com/IlMioFantasticoNegozio`.
- **URL YouTube:**

  - **Cosa fa questa impostazione:** Inserisci l'indirizzo web completo (URL) del tuo canale YouTube.
  - **Effetto della modifica di questa impostazione:**
    - *Se compilato:* Un'icona di YouTube apparirà, collegandosi al tuo canale.
    - *Se vuoto:* Nessuna icona di YouTube verrà visualizzata.
  - **Valore consigliato:** L'URL del tuo canale YouTube ufficiale (es. `https://www.youtube.com/channel/iltuoidcanale`).
  - **Scenario / esempio per il commerciante:** Se hai video di recensioni di prodotti o tutorial su YouTube, collega il tuo canale qui.
- **URL Google+:**

  - **Cosa fa questa impostazione:** Inserisci l'indirizzo web completo (URL) del tuo profilo o pagina Google+.
  - **Effetto della modifica di questa impostazione:**
    - *Se compilato:* Un'icona di Google+ apparirà, collegandosi al tuo profilo.
    - *Se vuoto:* Nessuna icona di Google+ verrà visualizzata.
  - **Valore consigliato:** L'URL del tuo profilo/pagina Google+ ufficiale (es. `https://plus.google.com/+IlNomeDelTuoNegozio`).
  - **Scenario / esempio per il commerciante:** Sebbene Google+ sia in gran parte deprecato, se mantieni ancora una presenza o hai contenuti legacy, puoi collegarlo qui. Altrimenti, lascialo vuoto.
- **URL RSS:**

  - **Cosa fa questa impostazione:** Inserisci l'indirizzo web completo (URL) del tuo feed RSS. Questo è tipicamente usato per blog o sezioni di notizie per consentire agli utenti di iscriversi agli aggiornamenti.
  - **Effetto della modifica di questa impostazione:**
    - *Se compilato:* Un'icona RSS apparirà, collegandosi al tuo feed.
    - *Se vuoto:* Nessuna icona RSS verrà visualizzata.
  - **Valore consigliato:** Se il tuo negozio ha un blog o una sezione di notizie con un feed RSS, inserisci il suo URL (es. `https://iltuonegozio.com/blog/feed`). Altrimenti, lascialo vuoto.
  - **Scenario / esempio per il commerciante:** Se pubblichi regolarmente post di blog sui tuoi prodotti o sul settore, fornire un feed RSS consente ai clienti esperti di tecnologia di ricevere aggiornamenti direttamente.

#### **Impostazioni di Visualizzazione**

- **Visualizza nell'intestazione:**

  - **Cosa fa questa impostazione:** Controlla se il blocco dei link ai social network appare nella sezione dell'intestazione del tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Se abilitato (Sì):* Il blocco dei link social sarà visibile nella parte superiore del tuo sito web.
    - *Se disabilitato (No):* Il blocco non apparirà nell'intestazione.
  - **Valore consigliato:** **Sì**, se desideri un'alta visibilità per i tuoi link social.
  - **Scenario / esempio per il commerciante:** Abilita questa opzione se vuoi che i clienti vedano immediatamente la tua presenza social appena arrivano sul tuo sito.
- **Visualizza nella colonna sinistra:**

  - **Cosa fa questa impostazione:** Controlla se il blocco dei link ai social network appare nella barra laterale sinistra del tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Se abilitato (Sì):* Il blocco dei link social sarà visibile nella colonna sinistra (se il tuo tema ne ha una).
    - *Se disabilitato (No):* Il blocco non apparirà nella colonna sinistra.
  - **Valore consigliato:** **No**, a meno che tu non abbia una ragione specifica per posizionarlo lì e il tuo tema supporti una colonna sinistra. Spesso, la colonna destra o il piè di pagina sono preferiti.
  - **Scenario / esempio per il commerciante:** Se il tuo tema ha una colonna sinistra prominente e vuoi mantenere i link visibili mentre i clienti sfogliano le categorie, abilita questa opzione.
- **Visualizza nella colonna destra:**

  - **Cosa fa questa impostazione:** Controlla se il blocco dei link ai social network appare nella barra laterale destra del tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Se abilitato (Sì):* Il blocco dei link social sarà visibile nella colonna destra (se il tuo tema ne ha una).
    - *Se disabilitato (No):* Il blocco non apparirà nella colonna destra.
  - **Valore consigliato:** **Sì**, se vuoi visualizzare i link in una barra laterale.
  - **Scenario / esempio per il commerciante:** Una buona opzione per mantenere i link social visibili senza ingombrare troppo l'intestazione o il piè di pagina.
- **Visualizza nel piè di pagina:**

  - **Cosa fa questa impostazione:** Controlla se il blocco dei link ai social network appare nella sezione del piè di pagina del tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Se abilitato (Sì):* Il blocco dei link social sarà visibile nella parte inferiore del tuo sito web.
    - *Se disabilitato (No):* Il blocco non apparirà nel piè di pagina.
  - **Valore consigliato:** **Sì**, poiché il piè di pagina è un luogo standard e atteso per i link ai social media.
  - **Scenario / esempio per il commerciante:** Abilita questa opzione per fornire una posizione coerente per i link social che i clienti spesso cercano in fondo a una pagina.
- **Visualizza nella pagina prodotto:**

  - **Cosa fa questa impostazione:** Controlla se il blocco dei link ai social network appare sulle singole pagine prodotto.
  - **Effetto della modifica di questa impostazione:**
    - *Se abilitato (Sì):* Il blocco dei link social sarà visibile su ogni pagina di dettaglio del prodotto.
    - *Se disabilitato (No):* Il blocco non apparirà sulle pagine prodotto.
  - **Valore consigliato:** **Sì**, se vuoi incoraggiare la condivisione social o il follow direttamente dalle pagine prodotto.
  - **Scenario / esempio per il commerciante:** Se vuoi che i clienti trovino facilmente i tuoi social media mentre stanno considerando un acquisto, abilita questa opzione.

#### 2.1.1 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | URL Facebook | Vuoto / URL della tua pagina Facebook | Link al tuo profilo Facebook. Vuoto = nessuna icona. |
| Configurazione Modulo | URL Twitter | Vuoto / URL del tuo profilo Twitter | Link al tuo profilo Twitter. Vuoto = nessuna icona. |
| Configurazione Modulo | URL YouTube | Vuoto / URL del tuo canale YouTube | Link al tuo canale YouTube. Vuoto = nessuna icona. |
| Configurazione Modulo | URL Google+ | Vuoto / URL del tuo profilo Google+ | Link al tuo profilo Google+. Vuoto = nessuna icona. |
| Configurazione Modulo | URL RSS | Vuoto / URL del tuo feed RSS | Link al tuo feed RSS. Vuoto = nessuna icona. |
| Configurazione Modulo | Visualizza nell'intestazione | No / Sì | Mostra i link social nell'intestazione del negozio. |
| Configurazione Modulo | Visualizza nella colonna sinistra | No / No | Mostra i link social nella barra laterale sinistra. |
| Configurazione Modulo | Visualizza nella colonna destra | No / Sì | Mostra i link social nella barra laterale destra. |
| Configurazione Modulo | Visualizza nel piè di pagina | No / Sì | Mostra i link social nel piè di pagina del negozio. |
| Configurazione Modulo | Visualizza nella pagina prodotto | No / Sì | Mostra i link social sulle singole pagine prodotto. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

- **D: Le mie icone social non vengono visualizzate dopo la configurazione.**

  - **R:** Innanzitutto, ricontrolla di aver inserito gli URL completi per i tuoi social network nella configurazione del modulo. Inoltre, assicurati di aver selezionato almeno un'opzione "Visualizza in..." (es. "Visualizza nel piè di pagina" su Sì). Infine, svuota la cache di PrestaShop in **Parametri avanzati > Prestazioni** (clicca sul pulsante "Svuota cache"). A volte, anche la cache del tema può impedire che le modifiche appaiano immediatamente.
- **D: Le icone vengono visualizzate, ma sembrano disallineate o non corrispondono al mio tema.**

  - **R:** Il modulo fornisce uno stile di base. Se il tuo tema ha regole CSS molto specifiche, potrebbero sovrascrivere o entrare in conflitto con gli stili del modulo.
    - **Soluzione 1 (Base):** Prova a svuotare la cache del tuo browser (Ctrl+F5 o Cmd+R).
    - **Soluzione 2 (Avanzata):** Questo di solito richiede a un webmaster o sviluppatore di ispezionare il CSS del tuo tema e potenzialmente aggiungere regole CSS personalizzate al file `custom.css` del tuo tema per regolare l'aspetto. Il file CSS del modulo (`socialnetworklinks.css`) può essere un riferimento.
- **D: Posso aggiungere altri social network non elencati (es. Instagram, Pinterest)?**

  - **R:** La versione attuale del modulo supporta Facebook, Twitter, YouTube, Google+ e RSS. Per aggiungere altri network, sarebbe necessario uno sviluppo personalizzato per modificare il codice del modulo e aggiungere nuove icone e campi di input. In alternativa, cerca un modulo social media più completo se hai bisogno di una gamma più ampia di piattaforme.
- **D: I link si aprono nella stessa scheda, ma voglio che si aprano in una nuova scheda.**

  - **R:** Per impostazione predefinita, il modulo è progettato per aprire i link in una nuova scheda (`target="_blank"`). Se questo non accade, potrebbe essere dovuto a un conflitto con il JavaScript del tuo tema o a un browser più vecchio. Assicurati che il tuo PrestaShop e il browser siano aggiornati. Se il problema persiste, uno sviluppatore dovrebbe ispezionare l'HTML generato.
- **D: Ho abilitato "Visualizza nella colonna sinistra/destra", ma non appare nulla.**

  - **R:** Molti temi PrestaShop moderni sono progettati senza colonne tradizionali a sinistra o a destra su tutte le pagine, specialmente sulle pagine prodotto o sulla homepage. Se il tuo tema non renderizza queste colonne, il modulo non avrà un posto dove visualizzare il suo blocco. Controlla la documentazione del tuo tema o personalizza il suo layout per abilitare le colonne dove vuoi che il modulo appaia. Il piè di pagina e l'intestazione sono generalmente posizioni di visualizzazione più affidabili tra i temi.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Link ai Social Network" è un modulo PrestaShop semplice che segue un modello simile a MVC di base all'interno dell'ambito del modulo. Utilizza principalmente la classe `Module` per la sua funzionalità principale, configurazione e registrazione degli hook. Memorizza le sue impostazioni direttamente nella tabella `ps_configuration` di PrestaShop. La visualizzazione front-office del modulo è gestita tramite un singolo template Smarty renderizzato tramite vari hook di visualizzazione.

### 4.2 Controller (`controllers/`)

Questo modulo **non** contiene alcun controller Front-Office o Back-Office Admin personalizzato. Tutta la configurazione è gestita direttamente all'interno del metodo `getContent()` della classe principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

Questo modulo **non** contiene classi personalizzate o definizioni di `ObjectModel`. Tutta la logica è incapsulata all'interno della classe principale `SocialNetworkLinks`.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo **non** contiene alcun file JavaScript personalizzato. La funzionalità per l'apertura dei link in nuove schede è gestita direttamente nell'HTML del template utilizzando `target="_blank"`.

### 4.5 Fogli di stile CSS (`views/css/`)

- **`socialnetworklinks/css/socialnetworklinks.css`**
  - **Ambito:** Stile front-office per il cliente.
  - **Componenti UI principali e contenitori che stilizza:** Questo foglio di stile fornisce l'aspetto visivo di base per le icone dei social media, inclusa la loro dimensione, spaziatura e potenziali effetti hover. Si rivolge al blocco contenitore principale e ai singoli elementi dei link social.
  - **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere nel loro tema:**
    - `.socialnetworklinks_block`: Il contenitore principale per il blocco dei link social.
    - `.socialnetworklinks_block ul`: La lista non ordinata contenente le icone social.
    - `.socialnetworklinks_block li`: Elementi di lista individuali per ogni icona social.
    - `.socialnetworklinks_block li a`: Il tag `<a>` per ogni link social.
    - `.socialnetworklinks_block li a i`: L'elemento icona (es. Font Awesome o simile, a seconda del tema).
    - Classi specifiche per ogni social network (es. `.facebook`, `.twitter`, ecc.) potrebbero essere presenti o possono essere aggiunte per uno stile personalizzato per network.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template degli hook (`views/templates/hook/`)**:
  - **`socialnetworklinks/views/front/column.tpl`**:
    - **Hook(s) renderizzati in:** `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (o hook simile per la pagina prodotto a seconda della versione di PrestaShop e del tema).
    - **Output del blocco visivo:** Questo template renderizza la struttura HTML per il blocco dei link ai social network. Itera attraverso gli URL dei social network configurati e visualizza un'icona (tipicamente utilizzando una libreria di icone font come Font Awesome, che di solito è fornita dal tema o dal core di PrestaShop) per ogni link attivo. Ogni icona è racchiusa in un tag `<a>` con `target="_blank"` per aprire il link in una nuova scheda.
    - **Variabili disponibili:**
      - `$facebook_url`: L'URL di Facebook configurato.
      - `$twitter_url`: L'URL di Twitter configurato.
      - `$youtube_url`: L'URL di YouTube configurato.
      - `$google_url`: L'URL di Google+ configurato.
      - `$rss_url`: L'URL RSS configurato.
      - `$module_dir`: La directory base del modulo, utile per collegare le risorse del modulo (anche se non molto utilizzata in questo specifico template).

### 4.7 Schema del database e Mappa degli hook

- **Tabelle del database**:
  Il modulo non crea tabelle di database personalizzate. Tutte le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` utilizzando chiavi prefissate con `SOCIALNETWORKLINKS_`.

  - `PS_SOCIALNETWORKLINKS_FACEBOOK_URL`
  - `PS_SOCIALNETWORKLINKS_TWITTER_URL`
  - `PS_SOCIALNETWORKLINKS_YOUTUBE_URL`
  - `PS_SOCIALNETWORKLINKS_GOOGLE_URL`
  - `PS_SOCIALNETWORKLINKS_RSS_URL`
  - `PS_SOCIALNETWORKLINKS_DISPLAY_HEADER`
  - `PS_SOCIALNETWORKLINKS_DISPLAY_LEFT_COLUMN`
  - `PS_SOCIALNETWORKLINKS_DISPLAY_RIGHT_COLUMN`
  - `PS_SOCIALNETWORKLINKS_DISPLAY_FOOTER`
  - `PS_SOCIALNETWORKLINKS_DISPLAY_PRODUCT_PAGE`
- **Tabella degli hook registrati**:

| Nome dell'Hook | Tempistica di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Renderizza il contenuto all'interno della sezione `<head>` o nella parte superiore del `<body>`. | Utilizzato per visualizzare il blocco dei link social nell'intestazione del negozio. |
| `displayLeftColumn` | Renderizza il contenuto nella barra laterale sinistra. | Utilizzato per visualizzare il blocco dei link social nella colonna sinistra. |
| `displayRightColumn` | Renderizza il contenuto nella barra laterale destra. | Utilizzato per visualizzare il blocco dei link social nella colonna destra. |
| `displayFooter` | Renderizza il contenuto nel piè di pagina del negozio. | Utilizzato per visualizzare il blocco dei link social nel piè di pagina. |
| `displayProductButtons` (o hook simile per la pagina prodotto) | Renderizza il contenuto nella pagina prodotto, spesso vicino al pulsante "Aggiungi al carrello" o alla descrizione del prodotto. | Utilizzato per visualizzare il blocco dei link social sulle singole pagine prodotto. |
| `moduleRoutes` | (Gestito implicitamente da PrestaShop per la configurazione del modulo) | Non utilizzato direttamente per la visualizzazione front-office, ma parte del ciclo di vita del modulo. |
| `actionAdminControllerSetMedia` | (Gestito implicitamente da PrestaShop per la configurazione del modulo) | Utilizzato per caricare CSS/JS nel back office per la pagina di configurazione del modulo. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Link ai Social Network", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e compatibilità del modulo.
