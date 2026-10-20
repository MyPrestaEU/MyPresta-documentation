---
title: "Condivisione carrello Facebook + coupon voucher - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Condivisione carrello Facebook + coupon voucher' di MyPresta.eu."
sidebar:
  label: "Condivisione carrello Facebook + coupon voucher"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Facebook cart share + voucher coupon su MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-cart-share-voucher-coupon.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/facebook-cart-share-voucher-coupon/)
>
> ---


# Condivisione carrello Facebook + coupon voucher

## 1. Requisiti e compatibilità
- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop e le interazioni con l'API di Facebook.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)
Questa è la schermata di configurazione principale per il modulo "Condivisione carrello Facebook + coupon voucher". La troverai navigando su **Moduli > Gestione moduli**, cercando "Condivisione carrello Facebook + coupon voucher" e cliccando su "Configura".

#### **Impostazioni generali**

-   **ID App Facebook (cshare_appid / cshare_app_id)**
    -   **Cosa fa questa impostazione:** Questo è un identificatore unico per la tua applicazione Facebook, necessario affinché il modulo possa interagire con l'API di Facebook. Devi creare un'App Facebook sulla piattaforma Facebook Developers (developers.facebook.com) per ottenere questo ID.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se impostato correttamente:* Il modulo può connettersi con successo a Facebook, consentendo ai clienti di condividere i loro carrelli e al tuo negozio di tracciare queste condivisioni.
        -   *Se lasciato vuoto o impostato in modo errato:* La funzionalità di condivisione di Facebook non funzionerà e i clienti non potranno condividere i loro carrelli.
    -   **Valore consigliato:** Il tuo ID App Facebook unico.
    -   **Scenario / esempio del commerciante:** Hai registrato il tuo negozio PrestaShop come app su Facebook Developers e hai ricevuto un ID App come `123456789012345`. Inserisci questo ID qui.

-   **Visualizza pulsante di condivisione su (cshare_lasttab)**
    -   **Cosa fa questa impostazione:** Determina dove apparirà il pulsante "Condividi carrello su Facebook" nel front office del tuo negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se impostato su "Pagina del carrello":* Il pulsante appare sulla pagina in cui i clienti rivedono il contenuto del loro carrello prima di procedere al checkout.
        -   *Se impostato su "Pagina di conferma dell'ordine":* Il pulsante appare dopo che il cliente ha effettuato un ordine con successo.
        -   *Se impostato su "Entrambi":* Il pulsante appare su entrambe le pagine.
    -   **Valore consigliato:** "Entrambi" per massimizzare la visibilità e le opportunità di condivisione.
    -   **Scenario / esempio del commerciante:** Vuoi incoraggiare la condivisione sia prima che dopo un acquisto, quindi selezioni "Entrambi".

-   **Stile pulsante di condivisione Facebook (cshare_button_style)**
    -   **Cosa fa questa impostazione:** Ti permette di scegliere lo stile visivo del pulsante di condivisione di Facebook.
    -   **Effetto della modifica di questa impostazione:** Cambia l'aspetto del pulsante di condivisione per adattarlo meglio al design del tuo negozio o alla tua preferenza per un pulsante più grande/più piccolo.
    -   **Valore consigliato:** Sperimenta per trovare ciò che si adatta meglio al tuo tema.
    -   **Scenario / esempio del commerciante:** Il tuo tema ha un design minimalista, quindi potresti scegliere un pulsante di condivisione semplice, basato su testo, piuttosto che uno grande e grafico.

#### **Impostazioni voucher**

-   **Abilita generazione voucher (cshare_voucher)**
    -   **Cosa fa questa impostazione:** Attiva o disattiva la generazione e l'offerta di un voucher sconto al cliente dopo che ha condiviso con successo il suo carrello su Facebook.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Un codice voucher unico viene creato e visualizzato al cliente dopo la condivisione.
        -   *Quando disabilitato:* Nessun voucher viene generato o offerto, rimuovendo l'incentivo diretto alla condivisione.
    -   **Valore consigliato:** "SÌ" per sfruttare l'incentivo alla condivisione e aumentare le conversioni.
    -   **Scenario / esempio del commerciante:** Vuoi premiare i clienti per la condivisione e incoraggiare acquisti ripetuti, quindi abiliti questa opzione.

-   **Regalo voucher (cshare_gift)**
    -   **Cosa fa questa impostazione:** Definisce il tipo e il valore del voucher sconto che i clienti ricevono. Questo corrisponde alle impostazioni "Tipo di sconto" e "Valore" quando si crea una nuova regola carrello in PrestaShop.
    -   **Effetto della modifica di questa impostazione:**
        -   *Importo fisso:* Il cliente riceve uno sconto monetario specifico (es. 5€ di sconto).
        -   *Percentuale:* Il cliente riceve uno sconto percentuale (es. 10% di sconto).
        -   *Spedizione gratuita:* Il cliente riceve la spedizione gratuita sul suo prossimo ordine.
    -   **Valore consigliato:** Un valore sufficientemente attraente per incentivare la condivisione ma anche sostenibile per la tua attività.
    -   **Scenario / esempio del commerciante:** Decidi di offrire un "10% di sconto" per incoraggiare nuovi acquisti, quindi selezioni "Percentuale" e imposti il valore nel campo successivo.

-   **Valore voucher (cshare_image)**
    -   **Cosa fa questa impostazione:** Imposta il valore specifico per il voucher, a seconda del tipo di "Regalo voucher" scelto.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se è stato scelto "Importo fisso":* Questo sarà l'esatto valore monetario dello sconto.
        -   *Se è stato scelto "Percentuale":* Questa sarà la percentuale dello sconto.
    -   **Valore consigliato:** Uno sconto convincente (es. 5, 10, 15 per percentuale; 5, 10, 20 per importo fisso).
    -   **Scenario / esempio del commerciante:** Hai scelto "Percentuale" per "Regalo voucher", quindi qui inserisci "10" per uno sconto del 10%.

#### **Impostazioni contenuto condiviso**

Queste impostazioni controllano quali informazioni sul carrello del cliente sono incluse nel post di Facebook quando lo condividono.

-   **Mostra prezzi (cshare_show_prices)**
    -   **Cosa fa questa impostazione:** Determina se i prezzi individuali dei prodotti nel carrello vengono visualizzati nel post di condivisione di Facebook.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Ogni prodotto elencato nel carrello condiviso mostrerà il suo prezzo.
        -   *Quando disabilitato:* I prezzi dei prodotti verranno omessi dal post condiviso.
    -   **Valore consigliato:** "SÌ" per fornire trasparenza e incoraggiare i clic, a meno che la tua strategia di prezzo non richieda diversamente.
    -   **Scenario / esempio del commerciante:** Vuoi che i potenziali clienti vedano il valore degli articoli, quindi abiliti "Mostra prezzi".

-   **Mostra totale (cshare_show_total)**
    -   **Cosa fa questa impostazione:** Determina se il valore totale del carrello della spesa viene visualizzato nel post di condivisione di Facebook.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Verrà mostrato il prezzo totale di tutti gli articoli nel carrello.
        -   *Quando disabilitato:* Il totale del carrello non sarà incluso nel post.
    -   **Valore consigliato:** "SÌ" per fornire una chiara panoramica del valore del carrello.
    -   **Scenario / esempio del commerciante:** Un cliente ha un carrello del valore di 250€ e vuoi che i suoi amici vedano questo acquisto significativo, quindi abiliti "Mostra totale".

-   **Mostra prodotti (cshare_show_products)**
    -   **Cosa fa questa impostazione:** Determina se i nomi e le quantità dei singoli prodotti nel carrello vengono elencati nel post di condivisione di Facebook.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Un elenco di prodotti (es. "T-Shirt x1, Jeans x1") apparirà nel post.
        -   *Quando disabilitato:* Apparirà solo un messaggio generico sulla condivisione del carrello, senza dettagli specifici del prodotto.
    -   **Valore consigliato:** "SÌ" per mostrare gli articoli specifici e generare interesse.
    -   **Scenario / esempio del commerciante:** Vuoi evidenziare i prodotti specifici che un cliente sta acquistando, quindi abiliti "Mostra prodotti".

-   **Mostra URL prodotto (cshare_show_product_url)**
    -   **Cosa fa questa impostazione:** Determina se i link diretti alle singole pagine prodotto sono inclusi nel post di condivisione di Facebook.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Ogni prodotto elencato avrà un link cliccabile alla sua pagina sul tuo negozio.
        -   *Quando disabilitato:* I nomi dei prodotti verranno visualizzati ma senza link diretti.
    -   **Valore consigliato:** "SÌ" per indirizzare il traffico direttamente alle pagine dei prodotti.
    -   **Scenario / esempio del commerciante:** Vuoi che gli amici del condivisore possano facilmente cliccare e visualizzare i prodotti, quindi abiliti "Mostra URL prodotto".

#### **Impostazioni avanzate**

-   **Forza HTTPS (cshare_http)**
    -   **Cosa fa questa impostazione:** Assicura che tutti gli URL generati per la condivisione su Facebook utilizzino HTTPS, anche se la configurazione del tuo PrestaShop potrebbe a volte predefinire HTTP. Questo è cruciale per la sicurezza e i requisiti di Facebook.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Tutti i link condivisi saranno sicuri (HTTPS).
        -   *Quando disabilitato:* I link potrebbero a volte essere HTTP, il che può causare problemi con l'API di Facebook e avvisi di sicurezza.
    -   **Valore consigliato:** "SÌ" se il tuo negozio utilizza HTTPS (cosa che dovrebbe fare!).
    -   **Scenario / esempio del commerciante:** Il tuo intero negozio funziona su HTTPS, quindi abiliti questa opzione per garantire coerenza ed evitare avvisi del browser.

-   **Nome negozio PrestaShop (PS_SHOP_NAME)**
    -   **Cosa fa questa impostazione:** Questo campo di solito recupera il nome del tuo negozio dalle impostazioni generali di PrestaShop. Viene utilizzato nel post di Facebook condiviso.
    -   **Effetto della modifica di questa impostazione:** Assicura che il nome corretto del negozio venga visualizzato nel post di Facebook.
    -   **Valore consigliato:** Lasciare come predefinito (dovrebbe popolarsi automaticamente dalla tua configurazione PrestaShop).
    -   **Scenario / esempio del commerciante:** Il tuo negozio si chiama "Il Mio Fantastico Negozio" e questo campo visualizza correttamente "Il Mio Fantastico Negozio".

-   **Email negozio PrestaShop (PS_SHOP_EMAIL)**
    -   **Cosa fa questa impostazione:** Questo campo di solito recupera l'email di contatto del tuo negozio dalle impostazioni generali di PrestaShop. Potrebbe essere utilizzato per operazioni interne del modulo o nel contenuto generato.
    -   **Effetto della modifica di questa impostazione:** Assicura che l'email corretta venga utilizzata se il modulo deve farvi riferimento.
    -   **Valore consigliato:** Lasciare come predefinito (dovrebbe popolarsi automaticamente dalla tua configurazione PrestaShop).
    -   **Scenario / esempio del commerciante:** L'email di contatto del tuo negozio è `info@ilmiofantasticonegozio.com` e questo campo la visualizza correttamente.

-   **Tasse PrestaShop (PS_TAX)**
    -   **Cosa fa questa impostazione:** Questo campo di solito recupera l'impostazione fiscale predefinita del tuo negozio. Potrebbe essere utilizzato per calcolare correttamente i prezzi nel contenuto condiviso.
    -   **Effetto della modifica di questa impostazione:** Assicura che le considerazioni fiscali siano gestite correttamente se i prezzi vengono visualizzati.
    -   **Valore consigliato:** Lasciare come predefinito (dovrebbe popolarsi automaticamente dalla tua configurazione PrestaShop).
    -   **Scenario / esempio del commerciante:** Il tuo negozio opera con un'IVA del 20% e questo campo lo riflette.

#### **Impostazioni interne del modulo (di solito lasciare come predefinite)**

-   **Aggiornamenti MyPresta.eu (mypresta_updates, update_, updatev_)**
    -   **Cosa fa questa impostazione:** Queste sono impostazioni interne utilizzate dai moduli MyPresta.eu per verificare gli aggiornamenti e garantire la compatibilità.
    -   **Effetto della modifica di questa impostazione:** La modifica di queste potrebbe interferire con la capacità del modulo di ricevere aggiornamenti o di funzionare correttamente.
    -   **Valore consigliato:** Lasciare come predefinito.
    -   **Scenario / esempio del commerciante:** Generalmente non è necessario interagire con queste.

-   **Inizializzazione Facebook (cshare_fbinit)**
    -   **Cosa fa questa impostazione:** Un flag interno che indica se l'SDK di Facebook è stato inizializzato.
    -   **Effetto della modifica di questa impostazione:** La modifica di questa potrebbe impedire il caricamento corretto della funzionalità di condivisione di Facebook.
    -   **Valore consigliato:** Lasciare come predefinito.
    -   **Scenario / esempio del commerciante:** Questa è un'impostazione tecnica non destinata all'interazione del commerciante.

### 2.2 Schermate di amministrazione dedicate e viste del controller
Questo modulo non introduce schermate o controller di amministrazione personalizzati dedicati oltre alla sua pagina di configurazione principale. Tutte le impostazioni sono gestite direttamente all'interno dell'interfaccia di configurazione standard del modulo.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
|---|---|---|---|
| Configurazione modulo | ID App Facebook | Il tuo ID App unico | Essenziale per la connessione API di Facebook; la condivisione non funzionerà senza di esso. |
| Configurazione modulo | Visualizza pulsante di condivisione su | Entrambi | Controlla dove appare il pulsante di condivisione (Carrello, Conferma ordine o entrambi). |
| Configurazione modulo | Stile pulsante di condivisione Facebook | (Varia) | Cambia l'aspetto visivo del pulsante di condivisione. |
| Configurazione modulo | Abilita generazione voucher | SÌ | Attiva/disattiva la creazione e la visualizzazione di un voucher sconto dopo la condivisione. |
| Configurazione modulo | Regalo voucher | Percentuale / Importo fisso | Definisce il tipo di sconto (es. 10% di sconto, 5€ di sconto, Spedizione gratuita). |
| Configurazione modulo | Valore voucher | (Il tuo valore desiderato) | Imposta il valore specifico per il tipo di regalo voucher scelto. |
| Configurazione modulo | Mostra prezzi | SÌ | Include i prezzi dei singoli prodotti nel post di condivisione di Facebook. |
| Configurazione modulo | Mostra totale | SÌ | Include il valore totale del carrello nel post di condivisione di Facebook. |
| Configurazione modulo | Mostra prodotti | SÌ | Elenca i nomi e le quantità dei singoli prodotti nel post di condivisione di Facebook. |
| Configurazione modulo | Mostra URL prodotto | SÌ | Aggiunge link diretti alle pagine dei prodotti nel post di condivisione di Facebook. |
| Configurazione modulo | Forza HTTPS | SÌ | Assicura che tutti i link condivisi siano sicuri (HTTPS). |
| Configurazione modulo | Nome negozio PrestaShop | (Popolato automaticamente) | Visualizza il nome del tuo negozio nel post di Facebook. |
| Configurazione modulo | Email negozio PrestaShop | (Popolato automaticamente) | Email di contatto del negozio. |
| Configurazione modulo | Tasse PrestaShop | (Popolato automaticamente) | Impostazione fiscale predefinita del negozio. |
| Configurazione modulo | Aggiornamenti MyPresta.eu | (Interno) | Impostazioni interne per gli aggiornamenti del modulo. |
| Configurazione modulo | Inizializzazione Facebook | (Interno) | Flag interno per l'inizializzazione dell'SDK di Facebook. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Il pulsante di condivisione di Facebook non appare sulla mia pagina del carrello/conferma ordine.**
*   **R:** Innanzitutto, controlla la configurazione del modulo nel tuo Back Office (**Moduli > Gestione moduli > Configura Condivisione carrello Facebook + coupon voucher**). Assicurati che "Visualizza pulsante di condivisione su" sia impostato correttamente (es. "Pagina del carrello", "Pagina di conferma dell'ordine" o "Entrambi"). Inoltre, verifica che il tuo ID App Facebook sia inserito correttamente. Se non appare ancora, svuota la cache di PrestaShop (**Parametri avanzati > Prestazioni > Svuota cache**).

**D2: Quando i clienti cliccano sul pulsante di condivisione, non succede nulla o ricevono un errore.**
*   **R:** Questo quasi sempre indica un problema con il tuo ID App Facebook o la configurazione dell'App Facebook stessa.
    1.  **Ricontrolla il tuo ID App Facebook:** Assicurati che sia inserito correttamente nella configurazione del modulo.
    2.  **Verifica le impostazioni dell'App Facebook:** Accedi a [developers.facebook.com](https://developers.facebook.com/). Assicurati che la tua app sia "Live" (non in modalità di sviluppo). Controlla la sezione "Impostazioni > Base" della tua app: i campi "Domini app" e "Sito web" devono elencare accuratamente il dominio del tuo negozio (es. `iltuonegozio.com` e `https://www.iltuonegozio.com`).
    3.  **Forza HTTPS:** Assicurati che l'opzione "Forza HTTPS" nella configurazione del modulo sia impostata su "SÌ" se il tuo negozio utilizza HTTPS.

**D3: I voucher non vengono generati dopo una condivisione riuscita.**
*   **R:**
    1.  **Controlla "Abilita generazione voucher":** Nella configurazione del modulo, assicurati che questa impostazione sia su "SÌ".
    2.  **Regalo voucher e valore:** Assicurati di aver selezionato un tipo di "Regalo voucher" (es. Percentuale, Importo fisso) e di aver inserito un "Valore voucher" valido.
    3.  **Limiti regole carrello PrestaShop:** PrestaShop ha limiti sul numero di regole carrello. Sebbene improbabile per questo modulo, se hai un volume estremamente elevato di condivisioni, assicurati che il tuo server possa gestire la creazione di nuove regole carrello.
    4.  **Log degli errori:** Controlla i log degli errori di PrestaShop (solitamente in `var/logs/` o `app/logs/` per PS 1.7+) per eventuali errori correlati durante il processo di generazione del voucher.

**D4: Il contenuto condiviso su Facebook non appare correttamente (es. prezzi mancanti, immagine sbagliata).**
*   **R:**
    1.  **Impostazioni del modulo:** Rivedi le "Impostazioni contenuto condiviso" nella configurazione del modulo (Mostra prezzi, Mostra totale, Mostra prodotti, Mostra URL prodotto). Assicurati che siano tutte impostate su "SÌ" se desideri il massimo dettaglio.
    2.  **Facebook Open Graph:** Facebook utilizza i tag Open Graph (OG) dalle tue pagine prodotto per generare anteprime. Assicurati che il tuo tema PrestaShop e altri moduli stiano generando correttamente questi tag OG (specialmente `og:image`, `og:title`, `og:description`). Puoi utilizzare il [Sharing Debugger](https://developers.facebook.com/tools/debug/) di Facebook per vedere come Facebook scansiona i tuoi URL.
    3.  **Cache:** Svuota la cache di PrestaShop e la cache del tuo browser. Facebook memorizza anche il contenuto condiviso nella cache, quindi usa il Sharing Debugger per "Scansiona di nuovo" se hai apportato modifiche.

**D5: Il modulo non si adatta bene al mio tema personalizzato.**
*   **R:** Il modulo utilizza il proprio CSS (`css.css`, `ps16.css`). Il tuo tema personalizzato potrebbe sovrascrivere o entrare in conflitto con questi stili.
    1.  **Ispeziona elemento:** Utilizza gli strumenti per sviluppatori del tuo browser (F12) per ispezionare il pulsante di condivisione e la visualizzazione del voucher. Identifica le classi CSS applicate dal modulo e dal tuo tema.
    2.  **CSS personalizzato:** Puoi aggiungere CSS personalizzato al file `custom.css` del tuo tema (o equivalente) per sovrascrivere gli stili del modulo e farlo corrispondere meglio al tuo tema. Punta alle classi specifiche del modulo per evitare di influenzare altre parti del tuo negozio.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura
Il modulo "Condivisione carrello Facebook + coupon voucher" segue un'architettura standard per i moduli PrestaShop, sfruttando principalmente la classe `Module` e `ModuleFrontController` per le interazioni front-office. Si integra con l'SDK JavaScript di Facebook per la funzionalità di condivisione e utilizza l'oggetto `CartRule` di PrestaShop per la generazione dei voucher. La configurazione è gestita tramite il metodo `getContent()` nel file principale del modulo, memorizzando le impostazioni in `ps_configuration`.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:
    *   `cartshare/controllers/front/cartshare.php`
        *   **Nome classe e classe genitore:** `CartshareCartshareModuleFrontController` estende `ModuleFrontController`.
        *   **Responsabilità:** Questo controller è probabilmente responsabile della gestione del callback AJAX da Facebook dopo una condivisione, o del rendering della pagina dedicata alla condivisione del carrello se il modulo ne ha una. Elaborerebbe l'evento di condivisione e attiverebbe la logica di generazione del voucher. Potrebbe anche essere responsabile del rendering del template `cartsharepage.tpl`.
    *   `cartshare/controllers/front/index.php`
        *   **Nome classe e classe genitore:** Questo è tipicamente un file vuoto o un semplice reindirizzamento per prevenire l'elenco delle directory, comune nei moduli PrestaShop. Non contiene una classe controller specifica.
        *   **Responsabilità:** Misura di sicurezza per prevenire l'accesso diretto alla directory `front`.

-   **Controller Admin Back-Office**:
    *   Nessuno. Tutta l'amministrazione è gestita tramite il metodo `getContent()` della classe principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)
Questo modulo non sembra definire classi personalizzate o `ObjectModel` all'interno della directory `classes/`. La sua logica principale per la generazione dei voucher probabilmente interagisce direttamente con la classe `CartRule` di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

-   `cartshare/lib/voucherengine/script.js`
    *   **Ambito:** Front-office.
    *   **Dettagli:** Questo script è cruciale per l'interazione lato client. Probabilmente inizializza l'SDK JavaScript di Facebook utilizzando il `cshare_appid` dalla configurazione del modulo. Collega i listener di eventi al pulsante "Condividi su Facebook", gestisce la finestra di dialogo di condivisione di Facebook e, in caso di condivisione riuscita, effettua una chiamata AJAX al controller frontale `cartshare.php` per attivare la generazione del voucher e visualizzare il codice voucher all'utente. Potrebbe anche gestire la visualizzazione dinamica del codice voucher sulla pagina.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `cartshare/css.css`
    *   **Ambito:** Front-office.
    *   **Dettagli:** Contiene lo stile generale per gli elementi del modulo, come il pulsante di condivisione, l'area di visualizzazione del voucher e qualsiasi altro componente dell'interfaccia utente introdotto dal modulo.
-   `cartshare/lib/voucherengine/ps16.css`
    *   **Ambito:** Front-office.
    *   **Dettagli:** Contiene probabilmente aggiustamenti di stile specifici o sovrascritture personalizzate per i temi di PrestaShop 1.6, garantendo compatibilità e rendering corretto sulle versioni precedenti.
-   `cartshare/views/css/css/css.css`
    *   **Ambito:** Front-office.
    *   **Dettagli:** Questo percorso sembra ridondante (`css/css/`). È possibile che sia un duplicato o una versione precedente di `cartshare/css.css`, o che contenga uno stile molto specifico per determinati elementi. Gli sviluppatori dovrebbero verificarne il contenuto per comprenderne lo scopo.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**:
    *   `cartshare/views/templates/hook/header.tpl`
        *   **Hook:** `displayHeader`
        *   **Output:** Questo template è responsabile dell'inclusione del codice di inizializzazione dell'SDK JavaScript di Facebook e potenzialmente dei file JavaScript (`script.js`) e CSS principali del modulo. Assicura che l'API di Facebook sia pronta prima che il pulsante di condivisione venga renderizzato.
    *   `cartshare/views/templates/hook/share.tpl`
        *   **Hook:** `displayShoppingcart`, `displayOrderConfirmation` (a seconda della configurazione del modulo)
        *   **Output:** Renderizza il pulsante "Condividi carrello su Facebook" e il contenitore per la visualizzazione del codice voucher dopo una condivisione riuscita. Questo è il componente visivo principale con cui i clienti interagiscono.

-   **Template front-office (`views/templates/front/`)**:
    *   `cartshare/views/templates/front/cartsharepage.tpl`
        *   **Scopo:** Questo template è probabilmente renderizzato da `CartshareCartshareModuleFrontController` e potrebbe essere una pagina dedicata o una vista parziale per visualizzare il contenuto del carrello da condividere, o il codice voucher.
    *   `cartshare/views/templates/front/facebook-share-contents.tpl`
        *   **Scopo:** Questo template genera dinamicamente il contenuto che verrà passato alla finestra di dialogo di condivisione di Facebook. Costruisce il titolo, la descrizione, l'immagine e gli URL in base al carrello del cliente e alle impostazioni di configurazione del modulo (es. `cshare_show_prices`, `cshare_show_products`).
    *   `cartshare/views/templates/front/shopping-cart.tpl`
        *   **Scopo:** Questo template potrebbe essere un override o un blocco aggiuntivo specificamente progettato per essere incluso all'interno della pagina standard del carrello di PrestaShop, potenzialmente per renderizzare il pulsante di condivisione o altri contenuti specifici del modulo direttamente all'interno del riepilogo del carrello.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    *   Questo modulo non crea tabelle SQL personalizzate.
    *   Le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration`, utilizzando chiavi come `CSHARE_APPID`, `CSHARE_VOUCHER`, `CSHARE_SHOW_PRICES`, ecc.
    *   I voucher sono generati come voci `CartRule` standard di PrestaShop, memorizzate in `ps_cart_rule` e tabelle correlate.

-   **Tabella degli hook registrati**:

| Nome hook | Tempistica di esecuzione | Scopo tecnico |
|---|---|---|
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Inizializza l'SDK di Facebook, carica le risorse JS/CSS del modulo. |
| `displayShoppingcart` | Nella pagina di riepilogo del carrello. | Renderizza il pulsante "Condividi carrello su Facebook" e l'area di visualizzazione del voucher. |
| `displayOrderConfirmation` | Nella pagina di conferma dell'ordine dopo un acquisto riuscito. | Renderizza il pulsante "Condividi carrello su Facebook" e l'area di visualizzazione del voucher. |
| `displayShoppingCart` | (Duplicato di `displayShoppingcart` nelle informazioni del modulo, probabilmente si riferisce allo stesso hook) | Renderizza il pulsante "Condividi carrello su Facebook" e l'area di visualizzazione del voucher. |

## 5. Supporto ufficiale e aggiornamenti
Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo "Condivisione carrello Facebook + coupon voucher", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a garantire che il modulo funzioni in modo ottimale con il tuo negozio PrestaShop.
