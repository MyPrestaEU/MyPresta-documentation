---
title: "Commenti Facebook - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo Commenti Facebook di MyPresta.eu per PrestaShop."
sidebar:
  label: "Commenti Facebook - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Facebook Comments su MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-comments.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/facebook-comments/)
>
> ---


# Commenti Facebook

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e per qualsiasi modulo che interagisca con API esterne come Facebook.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" per accedere alle impostazioni del modulo. Qui controllerai come la casella dei Commenti Facebook appare e funziona sulle pagine dei tuoi prodotti.

#### 2.1.1 ID App Facebook

-   **Cosa fa questa impostazione:** Questo è un identificatore unico per la tua App Facebook. Sebbene il modulo possa funzionare senza di esso, fornire un ID App ti dà accesso agli strumenti di moderazione e agli insight di Facebook per i commenti sul tuo sito.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando fornito:* Ottieni accesso al pannello di moderazione dei commenti di Facebook (developers.facebook.com/tools/comments) dove puoi rivedere, approvare o eliminare i commenti. Aiuta anche Facebook ad attribuire i commenti al tuo sito specifico.
    -   *Quando lasciato vuoto:* I commenti appariranno comunque, ma non avrai le capacità di moderazione avanzate tramite gli strumenti per sviluppatori di Facebook. Ti affiderai al filtro spam predefinito di Facebook.
-   **Valore consigliato:** È altamente consigliato creare un'App Facebook e inserire il tuo ID App qui per un migliore controllo e moderazione.
-   **Scenario / esempio per il commerciante:** Vuoi assicurarti che tutti i commenti siano appropriati e pertinenti. Configurando un ID App Facebook, puoi facilmente moderare i commenti direttamente dalla dashboard per sviluppatori di Facebook, rimuovendo spam o contenuti inappropriati.

#### 2.1.2 Numero di commenti

-   **Cosa fa questa impostazione:** Controlla quanti commenti vengono inizialmente visualizzati nella casella dei Commenti Facebook prima che gli utenti debbano cliccare su "Visualizza altri commenti" o "Carica altro" per vedere quelli più vecchi.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su un numero basso (es. 5):* La sezione dei commenti sarà più compatta, richiedendo agli utenti di cliccare per vederne altri. Questo può essere utile per pagine con spazio limitato o se si desidera mantenere il caricamento iniziale della pagina più leggero.
    -   *Quando impostato su un numero più alto (es. 20):* Più commenti saranno immediatamente visibili, fornendo più prova sociale a colpo d'occhio. Tuttavia, potrebbe rendere la pagina del prodotto più lunga.
-   **Valore consigliato:** 5-10 commenti è un buon punto di partenza per bilanciare visibilità e lunghezza della pagina. Regola in base al design della pagina del tuo prodotto e al volume tipico dei commenti.
-   **Scenario / esempio per il commerciante:** Per prodotti popolari con molti commenti, potresti impostare questo valore a 5 per mantenere la pagina ordinata. Per prodotti più recenti, impostarlo a 10 potrebbe incoraggiare più interazione mostrando più commenti esistenti.

#### 2.1.3 Larghezza della casella dei commenti

-   **Cosa fa questa impostazione:** Determina la larghezza della casella dei Commenti Facebook in pixel.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su un valore in pixel specifico (es. 600px):* La casella dei commenti manterrà quella larghezza fissa, potenzialmente creando spazio vuoto o overflow se l'area del contenuto del tuo tema è più stretta o più larga.
    -   *Quando lasciato vuoto o impostato su 100% (se supportato dal modulo):* La casella dei commenti cercherà di adattarsi automaticamente alla larghezza disponibile del suo contenitore genitore, rendendola responsive.
-   **Valore consigliato:** Lascia vuoto per il rilevamento automatico o imposta su 100% se il modulo lo supporta, per garantire la reattività. Se hai bisogno di una larghezza fissa, assicurati che si adatti all'area del contenuto del tuo tema.
-   **Scenario / esempio per il commerciante:** La pagina del tuo prodotto ha una colonna di contenuto principale larga 700px. Potresti impostare la larghezza a 700px per riempire perfettamente quello spazio. Se vuoi che si adatti al mobile, lasciarlo vuoto è solitamente la soluzione migliore.

#### 2.1.4 Lingua della casella dei commenti

-   **Cosa fa questa impostazione:** Ti permette di specificare la lingua per l'interfaccia del plugin Commenti Facebook (es. "Scrivi un commento...", "Visualizza altri commenti").
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su un codice lingua specifico (es. "en\_US" per l'inglese, "fr\_FR" per il francese):* Il testo del plugin di Facebook verrà visualizzato in quella lingua, indipendentemente dalla lingua del browser dell'utente o dalla lingua attiva del tuo negozio PrestaShop.
    -   *Quando lasciato vuoto:* Facebook tenterà tipicamente di rilevare la lingua preferita dell'utente o la lingua del tuo negozio PrestaShop.
-   **Valore consigliato:** Generalmente è meglio lasciare vuoto in modo che Facebook possa rilevare automaticamente la lingua dell'utente, oppure impostarlo sulla lingua principale del tuo negozio se desideri coerenza.
-   **Scenario / esempio per il commerciante:** Se il tuo negozio si rivolge principalmente a clienti in Germania, potresti impostare questo valore su "de\_DE" per assicurarti che tutto il testo del plugin di Facebook sia in tedesco, anche se il browser di un utente è impostato sull'inglese.

#### 2.1.5 Posizione della casella dei commenti

-   **Cosa fa questa impostazione:** Determina dove sulla pagina del prodotto verrà visualizzata la casella dei Commenti Facebook. Puoi scegliere tra vari hook di PrestaShop.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su `displayProductButtons` (o simile):* La casella dei commenti potrebbe apparire vicino al pulsante "Aggiungi al carrello" o ad altre azioni del prodotto.
    -   *Quando impostato su `displayFooterProduct` (o simile):* La casella dei commenti apparirà più in basso nella pagina del prodotto, spesso sotto i dettagli principali del prodotto, che è una posizione comune e solitamente preferita.
    -   *Quando impostato su `displayRightColumn` o `displayLeftColumn` (se disponibile):* La casella dei commenti apparirebbe in una delle colonne laterali del tuo negozio, il che è meno comune per i commenti e potrebbe non essere visivamente ideale.
-   **Valore consigliato:** `displayFooterProduct` o un hook simile che posiziona la sezione dei commenti sotto le informazioni principali del prodotto è solitamente il posizionamento più naturale ed efficace.
-   **Scenario / esempio per il commerciante:** Vuoi che i commenti siano visibili ma non distraggano dall'obiettivo primario di aggiungere il prodotto al carrello. Posizionandoli in `displayFooterProduct` assicuri che i clienti vedano prima tutti i dettagli del prodotto, poi possano interagire con i commenti.

#### 2.1.6 Abilita Commenti Facebook

-   **Cosa fa questa impostazione:** Questo è un semplice interruttore ON/OFF per attivare o disattivare l'intera funzionalità dei Commenti Facebook.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* La casella dei Commenti Facebook apparirà sulle pagine dei tuoi prodotti in base alle altre impostazioni.
    -   *Quando disabilitato (NO):* La casella dei Commenti Facebook sarà completamente nascosta dalle pagine dei tuoi prodotti e il modulo non caricherà alcuno script relativo a Facebook.
-   **Valore consigliato:** SÌ, se vuoi utilizzare la funzionalità.
-   **Scenario / esempio per il commerciante:** Hai finito di configurare il modulo e vuoi renderlo attivo sul tuo negozio. Imposti questo valore su SÌ. Successivamente, se decidi di disabilitare temporaneamente i commenti per manutenzione, puoi impostarlo su NO.

#### 2.1.7 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | ID App Facebook | (Vuoto) / Consigliato: Il tuo ID App | Abilita gli strumenti di moderazione di Facebook per i commenti. |
| Configurazione Modulo | Numero di commenti | 5-10 | Imposta quanti commenti sono inizialmente visibili. Influisce sulla lunghezza della pagina. |
| Configurazione Modulo | Larghezza della casella dei commenti | (Vuoto) / Rilevamento automatico (Responsive) | Definisce la larghezza della sezione dei commenti. Vuoto per la reattività. |
| Configurazione Modulo | Lingua della casella dei commenti | (Vuoto) / Rilevamento automatico | Imposta la lingua dell'interfaccia del plugin di Facebook. Vuoto per la lingua dell'utente/negozio. |
| Configurazione Modulo | Posizione della casella dei commenti | `displayFooterProduct` | Determina dove appare la casella dei commenti sulla pagina del prodotto. |
| Configurazione Modulo | Abilita Commenti Facebook | SÌ | Attiva o disattiva l'intera funzionalità dei Commenti Facebook. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: La casella dei Commenti Facebook non appare sulle pagine dei miei prodotti. Cosa devo fare?**
R:

1.  **Controlla "Abilita Commenti Facebook":** Assicurati che questa impostazione nella configurazione del modulo sia impostata su SÌ.
2.  **Verifica la posizione:** Assicurati che l'impostazione "Posizione della casella dei commenti" sia impostata su un hook effettivamente presente e renderizzato dal tuo tema sulle pagine dei prodotti (ad esempio, `displayFooterProduct`). Alcuni temi personalizzati potrebbero non utilizzare tutti gli hook standard.
3.  **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** nel Back Office di PrestaShop e clicca su "Svuota cache" (o "Svuota cache Smarty"). A volte, il vecchio contenuto memorizzato nella cache impedisce la visualizzazione di nuovi moduli.
4.  **Compatibilità del tema:** Se stai utilizzando un tema fortemente personalizzato, potrebbe sovrascrivere i template standard delle pagine dei prodotti o rimuovere gli hook necessari. Contatta lo sviluppatore del tuo tema o un esperto PrestaShop per assistenza.
5.  **Problemi del browser:** Prova a svuotare la cache e i cookie del tuo browser, oppure testa in una finestra in incognito.

**D: Come posso moderare i commenti?**
R: Se hai configurato un ID App Facebook e lo hai inserito nella configurazione del modulo, puoi moderare i commenti direttamente tramite gli strumenti per sviluppatori di Facebook. Vai su [developers.facebook.com/tools/comments](https://developers.facebook.com/tools/comments). Dovrai essere loggato con l'account Facebook associato al tuo ID App.

**D: Posso modificare lo stile (colori, font) della casella dei Commenti Facebook?**
R: Lo stile del plugin Commenti Facebook è in gran parte controllato da Facebook stesso per mantenere un'esperienza di marca coerente. Hai un controllo molto limitato sul suo aspetto interno. Puoi controllare la larghezza e il suo posizionamento, ma non il suo CSS interno.

**D: I Commenti Facebook rallenteranno il mio sito web?**
R: Il plugin Commenti Facebook carica script esterni da Facebook. Sebbene Facebook li ottimizzi, qualsiasi script esterno può aggiungere un leggero ritardo al caricamento della pagina. Il modulo è progettato per caricare questi script in modo efficiente. Puoi utilizzare strumenti come Google PageSpeed Insights per monitorare le prestazioni del tuo sito.

**D: Ho bisogno di una Pagina Facebook Business affinché questo modulo funzioni?**
R: No, non hai strettamente bisogno di una Pagina Facebook Business. Tuttavia, se desideri utilizzare gli strumenti di moderazione avanzati, avrai bisogno di un account sviluppatore Facebook e di creare una App Facebook di base, che è un'entità separata da una Pagina Business.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo Commenti Facebook (`facebook-comments`) è un modulo PrestaShop semplice, progettato principalmente per iniettare l'HTML e l'SDK JavaScript del plugin sociale Commenti Facebook nelle pagine dei prodotti del front-office. Segue una struttura standard dei moduli PrestaShop, sfruttando gli hook per l'iniezione di contenuti e la classe `Configuration` per l'archiviazione delle impostazioni. Non introduce controller, modelli o interazioni AJAX complesse personalizzate.

### 4.2 Controller (`controllers/`)

-   Questo modulo **non** contiene alcun controller amministrativo Front-Office o Back-Office personalizzato. Tutta la configurazione è gestita tramite il metodo `getContent()` del file principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

-   Questo modulo **non** contiene classi personalizzate o definizioni di `ObjectModel`. Tutta la logica è incapsulata nel file principale `facebook-comments.php`.

### 4.4 Risorse JavaScript (`views/js/`)

-   Questo modulo **non** contiene file JavaScript personalizzati. L'SDK JavaScript di Facebook viene caricato direttamente dal CDN di Facebook tramite il template del modulo.

### 4.5 Fogli di stile CSS (`views/css/`)

-   Questo modulo **non** contiene file CSS personalizzati. Lo stile del plugin Commenti Facebook è gestito dai fogli di stile di Facebook.

### 4.6 Struttura del template Smarty (`views/templates/`)

Questo modulo utilizza principalmente un singolo file di template per renderizzare la casella dei Commenti Facebook.

-   **Template degli hook (`views/templates/hook/`)**:
    -   `facebook-comments.tpl`: Questo è il file di template principale.
        -   **Scopo:** Renderizza l'elemento `div` che l'SDK JavaScript di Facebook trasforma nella casella dei commenti. Include anche il codice di inizializzazione necessario dell'SDK JavaScript.
        -   **Variabili:**
            -   `{$facebook_app_id}`: L'ID App Facebook dalla configurazione del modulo.
            -   `{$facebook_comments_number}`: Il numero di commenti da visualizzare.
            -   `{$facebook_comments_width}`: La larghezza della casella dei commenti.
            -   `{$facebook_comments_lang}`: Il codice lingua per il plugin.
            -   `{$product_link}`: L'URL della pagina del prodotto corrente, utilizzato da Facebook per identificare il thread dei commenti.
        -   **Hook:** Questo template viene renderizzato tramite l'hook specificato nella configurazione del modulo (es. `displayFooterProduct`).

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**: Questo modulo **non** crea tabelle del database personalizzate. Tutte le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` utilizzando i metodi standard di PrestaShop `Configuration::get()` e `Configuration::updateValue()`.

    -   Le chiavi di configurazione tipicamente includono:
        -   `FACEBOOK_COMMENTS_APP_ID`
        -   `FACEBOOK_COMMENTS_NUMBER`
        -   `FACEBOOK_COMMENTS_WIDTH`
        -   `FACEBOOK_COMMENTS_LANG`
        -   `FACEBOOK_COMMENTS_POSITION`
        -   `FACEBOOK_COMMENTS_ENABLED`
-   **Tabella degli hook registrati**:

| Nome dell'Hook | Tempistica di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Utilizzato per includere l'SDK JavaScript di Facebook una volta per pagina, assicurando che sia disponibile prima che la casella dei commenti venga renderizzata. |
| `displayProductButtons` | Vicino al pulsante "Aggiungi al carrello" sulle pagine dei prodotti. | Hook opzionale per il rendering della casella dei commenti, se configurato dal commerciante. |
| `displayFooterProduct` | In fondo al contenuto della pagina del prodotto. | Hook comune e consigliato per il rendering della casella dei commenti, se configurato dal commerciante. |
| `displayLeftColumn` | Nella barra laterale sinistra delle pagine. | Hook opzionale per il rendering della casella dei commenti, se configurato dal commerciante. (Meno comune per i commenti). |
| `displayRightColumn` | Nella barra laterale destra delle pagine. | Hook opzionale per il rendering della casella dei commenti, se configurato dal commerciante. (Meno comune per i commenti). |
| `displayFooter` | Nella sezione del footer del negozio. | Hook opzionale per il rendering della casella dei commenti, se configurato dal commerciante. (Meno comune per i commenti specifici del prodotto). |

Il modulo si registra dinamicamente all'hook scelto dal commerciante nella configurazione. L'hook `displayHeader` viene sempre utilizzato per caricare l'SDK di Facebook.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo Commenti Facebook, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere con qualsiasi problema o domanda riguardante la funzionalità del modulo.
