---
title: "Microsoft Advertising UET Tag & Conversions API - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Microsoft Advertising UET Tag & Conversions API di MyPresta.eu."
sidebar:
  label: "Microsoft Advertising UET Tag & Conversions API - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Microsoft Advertising UET Tag & Conversions API su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/microsoft-advertising-uet-tag-conversions-api.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/microsoft-advertising-uet-tag-conversions-api/)
>
> ---


# Microsoft Advertising UET Tag & Conversions API

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard come cURL, JSON e OpenSSL sono richieste per il corretto funzionamento del modulo, specialmente per le funzionalità dell'API delle Conversioni. Queste sono tipicamente abilitate per impostazione predefinita sulla maggior parte degli ambienti di hosting moderni.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questo è l'hub principale per la configurazione del tracciamento di Microsoft Advertising. Troverai una serie di schede e impostazioni progettate per guidarti attraverso il processo.

#### Scheda di configurazione principale (Vista iniziale)

-   **Cosa fa questa impostazione:** Questa scheda fornisce tipicamente una panoramica e opzioni di configurazione iniziali, spesso includendo una procedura guidata per semplificare la configurazione iniziale.
-   **Effetto della modifica di questa impostazione:** Completare la procedura guidata o inserire i dettagli iniziali abiliterà la funzionalità di tracciamento di base e preparerà il modulo per impostazioni più avanzate.
-   **Valore consigliato:** Segui attentamente i passaggi della procedura guidata.
-   **Scenario / esempio del commerciante:** Quando installi il modulo per la prima volta, la procedura guidata ti chiederà il tuo ID Tag UET e ti guiderà nella scelta del metodo di tracciamento (Tag UET, API delle Conversioni o entrambi).

#### ID Tag UET

-   **Cosa fa questa impostazione:** Questo è il tuo identificatore univoco fornito da Microsoft Advertising. Indica a Microsoft a quale account associare i dati di tracciamento.
-   **Effetto della modifica di questa impostazione:**
    -   *Se inserito correttamente:* Il modulo incorporerà il Tag UET nel tuo negozio, consentendo a Microsoft Advertising di tracciare il comportamento dell'utente.
    -   *Se lasciato vuoto o errato:* Non avverrà alcun tracciamento del Tag UET e le tue campagne Microsoft Advertising non riceveranno dati di conversione dal front-office.
-   **Valore consigliato:** Il tuo ID Tag UET esatto dal tuo account Microsoft Advertising.
-   **Scenario / esempio del commerciante:** Hai creato un account Microsoft Advertising e configurato un Tag UET. Copi l'ID (es. `12345678`) e lo incolli qui.

#### Modalità di tracciamento (Tag UET, API delle Conversioni o Entrambi)

-   **Cosa fa questa impostazione:** Determina come i dati di conversione vengono inviati a Microsoft Advertising.
    -   **Solo Tag UET:** Tracciamento tradizionale lato client tramite JavaScript nel browser del cliente.
    -   **Solo API delle Conversioni:** Tracciamento lato server, inviando i dati direttamente dal tuo server PrestaShop a Microsoft. Più resistente alle impostazioni di privacy del browser.
    -   **Entrambi (Ibrido):** Utilizza sia il Tag UET che l'API delle Conversioni, con un meccanismo per deduplicare gli eventi, garantendo un conteggio accurato anche se entrambi i metodi segnalano la stessa conversione.
-   **Effetto della modifica di questa impostazione:**
    -   *Solo Tag UET:* Si basa esclusivamente sul tracciamento basato su browser, che può essere influenzato da ad blocker o impostazioni di privacy.
    -   *Solo API delle Conversioni:* Fornisce un tracciamento più robusto, ma richiede una configurazione lato server e potrebbe non catturare tutti gli eventi lato client (come le visualizzazioni di pagina) con la stessa facilità.
    -   *Entrambi (Ibrido):* Offre il tracciamento più completo e affidabile, combinando i punti di forza di entrambi i metodi e prevenendo conversioni duplicate.
-   **Valore consigliato:** **Entrambi (Ibrido)** è generalmente raccomandato per la massima accuratezza e resilienza.
-   **Scenario / esempio del commerciante:** Desideri i dati più accurati possibile, quindi selezioni "Entrambi (Ibrido)" per garantire che le conversioni vengano tracciate anche se un cliente utilizza un ad blocker.

#### Token di accesso all'API delle Conversioni

-   **Cosa fa questa impostazione:** Questo è un token sicuro generato nel tuo account Microsoft Advertising, che autorizza il tuo negozio PrestaShop a inviare dati direttamente ai server di Microsoft tramite l'API delle Conversioni.
-   **Effetto della modifica di questa impostazione:**
    -   *Se inserito correttamente:* Abilita il tracciamento lato server per l'API delle Conversioni.
    -   *Se lasciato vuoto o errato:* L'API delle Conversioni non funzionerà e i dati di conversione lato server non verranno inviati.
-   **Valore consigliato:** Il tuo Token di accesso all'API delle Conversioni esatto dal tuo account Microsoft Advertising.
-   **Scenario / esempio del commerciante:** Hai generato un Token di accesso nel tuo account Microsoft Advertising (es. sotto "Strumenti" > "Monitoraggio conversioni" > "API delle Conversioni"). Incolli questa lunga stringa di caratteri qui.

#### Abilita conversioni avanzate

-   **Cosa fa questa impostazione:** Quando abilitata, questa funzione invia dati cliente hash (come gli indirizzi email) insieme agli eventi di conversione. Questo aiuta Microsoft a far corrispondere le conversioni in modo più accurato, specialmente quando i cookie sono limitati, migliorando le prestazioni della tua campagna.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* Corrispondenza delle conversioni più accurata, che può portare a una migliore ottimizzazione delle tue campagne pubblicitarie.
    -   *Quando disabilitato:* Le conversioni si basano esclusivamente su metodi di tracciamento standard, che potrebbero essere meno accurati in alcuni ambienti browser focalizzati sulla privacy.
-   **Valore consigliato:** **SÌ** (Abilitato), poiché migliora significativamente la corrispondenza dei dati.
-   **Scenario / esempio del commerciante:** Vuoi fornire a Microsoft Advertising i migliori dati possibili per ottimizzare le tue campagne, quindi abiliti le Conversioni Avanzate.

#### Integrazione con la gestione del consenso

-   **Cosa fa questa impostazione:** Questo modulo può integrarsi con i moduli di consenso ai cookie esistenti (come i moduli GDPR) per garantire che il Tag UET si attivi solo dopo che un cliente ha dato il proprio consenso.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato e integrato:* Il Tag UET rispetterà le scelte di consenso del cliente. Se un cliente rifiuta i cookie di tracciamento, il Tag UET non verrà caricato.
    -   *Quando disabilitato o non integrato:* Il Tag UET potrebbe caricarsi indipendentemente dal consenso, potenzialmente portando a problemi di conformità.
-   **Valore consigliato:** **SÌ** (Abilitato) se utilizzi un modulo di consenso ai cookie e devi rispettare le normative sulla privacy (es. GDPR, CCPA).
-   **Scenario / esempio del commerciante:** Il tuo negozio utilizza un modulo GDPR. Abiliti questa impostazione per garantire che il tuo tracciamento di Microsoft Advertising sia conforme alle leggi sulla privacy.

#### Modalità Debug

-   **Cosa fa questa impostazione:** Attiva una modalità speciale che visualizza informazioni dettagliate sul Tag UET e sugli eventi dell'API delle Conversioni direttamente sulle tue pagine del front-office (visibile solo a te, all'amministratore o a specifici indirizzi IP). Questo è prezioso per verificare che il tracciamento sia configurato correttamente.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* Vedrai un overlay di debug o messaggi nella console sul front-office del tuo negozio, che mostrano quali eventi vengono tracciati e quali dati vengono inviati.
    -   *Quando disabilitato:* Il modulo opera silenziosamente, senza informazioni di debug visibili.
-   **Valore consigliato:** **NO** (Disabilitato) per i negozi in produzione. **SÌ** (Abilitato) temporaneamente durante la configurazione e la risoluzione dei problemi.
-   **Scenario / esempio del commerciante:** Hai appena installato il modulo e vuoi confermare che gli eventi "Aggiungi al carrello" vengano inviati correttamente. Abiliti la Modalità Debug, aggiungi un prodotto al carrello e controlli l'output di debug.

#### Mappatura eventi (Avanzato)

-   **Cosa fa questa impostazione:** Ti consente di personalizzare come specifiche azioni di PrestaShop (es. "Prodotto aggiunto al carrello") vengono mappate ai nomi degli eventi di Microsoft Advertising (es. "add\_to\_cart"). Puoi anche definire parametri personalizzati da inviare con ogni evento.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando configurato:* Assicura che i tuoi eventi siano correttamente categorizzati e arricchiti con dati pertinenti in Microsoft Advertising.
    -   *Quando configurato in modo errato:* Gli eventi potrebbero non essere tracciati, o i dati inviati potrebbero essere inaccurati, portando a una scarsa ottimizzazione della campagna.
-   **Valore consigliato:** Utilizza le mappature predefinite a meno che tu non abbia un motivo specifico per modificarle in base alla tua configurazione di Microsoft Advertising.
-   **Scenario / esempio del commerciante:** Vuoi inviare il marchio del prodotto come parametro personalizzato con ogni evento "view\_item". Configureresti questa mappatura qui.

#### Domini di collegamento (Avanzato)

-   **Cosa fa questa impostazione:** Se hai più sottodomini o siti web correlati che condividono lo stesso Tag UET, questa impostazione aiuta a garantire che le sessioni utente siano correttamente collegate tra questi domini.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando configurato:* Consente un tracciamento senza interruzioni dei percorsi utente su più domini sotto il tuo controllo.
    -   *Quando non configurato (e necessario):* Le sessioni utente potrebbero essere interrotte, portando a un'attribuzione delle conversioni inaccurata.
-   **Valore consigliato:** Lascia vuoto a meno che tu non gestisca più sottodomini o siti correlati che necessitano di tracciamento cross-domain.
-   **Scenario / esempio del commerciante:** Hai il tuo negozio principale su `shop.example.com` e un blog su `blog.example.com`, entrambi che utilizzano lo stesso Tag UET. Aggiungeresti `blog.example.com` all'elenco dei domini di collegamento.

#### Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione principale | ID Tag UET | Il tuo ID Tag | Abilita il tracciamento del Tag UET. Essenziale per i dati lato client. |
| Configurazione principale | Modalità di tracciamento | Entrambi (Ibrido) | Seleziona Tag UET, API delle Conversioni o entrambi per la trasmissione dei dati. Ibrido è il più robusto. |
| Configurazione principale | Token di accesso all'API delle Conversioni | Il tuo Token di accesso | Autorizza l'invio di dati lato server a Microsoft. |
| Configurazione principale | Abilita conversioni avanzate | SÌ | Migliora l'accuratezza della corrispondenza delle conversioni inviando dati cliente hash. |
| Configurazione principale | Integrazione con la gestione del consenso | SÌ (se applicabile) | Assicura che il Tag UET rispetti le scelte di privacy del cliente (GDPR, CCPA). |
| Configurazione principale | Modalità Debug | NO (SÌ per i test) | Visualizza i dati di tracciamento sul front-office per la verifica. |
| Configurazione principale | Mappatura eventi | Predefinito | Personalizza come le azioni di PrestaShop si mappano agli eventi di Microsoft. |
| Configurazione principale | Domini di collegamento | Vuoto (se non necessario) | Abilita il tracciamento cross-domain per siti web correlati. |

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### 2.2.1 AdminMybingAjaxController (Back Office > Moduli > Microsoft Advertising UET Tag & Conversions API > Statistiche in tempo reale / Punteggio di salute / Dottore / Qualità dei dati)

Questo controller alimenta le sezioni dinamiche e interattive della configurazione del modulo, fornendo approfondimenti in tempo reale e strumenti diagnostici. Non navigherai a una voce di menu separata per questo, ma interagirai con schede specifiche all'interno della configurazione principale del modulo.

-   **Nome schermata e posizione menu:** Queste sono tipicamente sotto-schede all'interno della pagina di configurazione principale del modulo (es. "Statistiche in tempo reale", "Punteggio di salute", "Coach qualità dati", "Dottore catalogo").
-   **Azioni e impostazioni disponibili:**
    -   **Statistiche in tempo reale:** Visualizza gli eventi recenti inviati a Microsoft Advertising, mostrando visualizzazioni di pagina, aggiunte al carrello, acquisti, ecc., quasi in tempo reale. Questo ti aiuta a confermare che gli eventi si stanno attivando correttamente.
    -   **Punteggio di salute:** Analizza la tua configurazione di tracciamento e fornisce un punteggio basato sulle migliori pratiche, evidenziando potenziali problemi o aree di miglioramento.
    -   **Coach qualità dati:** Offre raccomandazioni specifiche per migliorare la qualità e la completezza dei dati che stai inviando a Microsoft, specialmente per le Conversioni Avanzate.
    -   **Dottore catalogo:** Aiuta a diagnosticare problemi con i dati dei tuoi prodotti che potrebbero influenzare la pubblicità del feed di prodotti o il remarketing dinamico.
-   **Effetto delle modifiche:** L'interazione con queste schermate fornisce principalmente informazioni e feedback diagnostici. Non ci sono "impostazioni" dirette da modificare qui, ma le intuizioni acquisite informeranno gli aggiustamenti che potresti apportare nella configurazione principale o nel tuo catalogo prodotti.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    -   Controlla regolarmente le **Statistiche in tempo reale** dopo aver apportato modifiche o lanciato nuove campagne per assicurarti che gli eventi vengano tracciati.
    -   Rivedi periodicamente il **Punteggio di salute** e il **Coach qualità dati** per raccomandazioni per ottimizzare la tua configurazione di tracciamento.
    -   Se riscontri problemi con gli annunci relativi ai prodotti, consulta il **Dottore catalogo**.

#### 2.2.2 index.php (Back Office > Moduli > Microsoft Advertising UET Tag & Conversions API)

Questo si riferisce al punto di ingresso principale per l'interfaccia di back-office del modulo, che è la pagina di configurazione stessa. Tutte le impostazioni descritte nella sezione 4.1 sono gestite tramite questa vista principale. Non esiste una schermata "index.php" separata a cui navigare oltre la configurazione iniziale del modulo.

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Le mie conversioni non vengono visualizzate in Microsoft Advertising. Cosa devo fare?**
R:

1.  **Controlla ID Tag UET e Token di accesso:** Ricontrolla che il tuo ID Tag UET e il Token di accesso all'API delle Conversioni siano stati inseriti correttamente nella configurazione del modulo. Anche un singolo errore di battitura può impedire il tracciamento.
2.  **Verifica la modalità di tracciamento:** Assicurati che la tua "Modalità di tracciamento" sia impostata su "Entrambi (Ibrido)" per la massima affidabilità.
3.  **Abilita la modalità Debug:** Attiva la "Modalità Debug" nelle impostazioni del modulo ed effettua un acquisto di prova nel tuo negozio. Cerca l'overlay di debug o i messaggi della console per vedere se gli eventi si stanno attivando.
4.  **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** nel tuo Back Office di PrestaShop e svuota la cache di Smarty e qualsiasi altra cache. A volte le vecchie impostazioni possono persistere.
5.  **Controlla l'account Microsoft Advertising:** Accedi al tuo account Microsoft Advertising e controlla lo stato del Tag UET e la configurazione degli obiettivi di conversione. Assicurati che i tuoi obiettivi di conversione siano configurati correttamente per corrispondere agli eventi inviati dal modulo (es. "Acquisto").

**D: Il modulo dice "Integrazione con la gestione del consenso" è abilitata, ma non ho un modulo GDPR. È un problema?**
R: Se non hai un modulo di consenso ai cookie dedicato installato e configurato, questa impostazione non avrà alcun effetto pratico. Il modulo assumerà il consenso per impostazione predefinita. Tuttavia, per la conformità legale (es. GDPR, CCPA), è altamente consigliato utilizzare un modulo di consenso ai cookie appropriato. Se ne installi uno in seguito, questo modulo si integrerà automaticamente con esso.

**D: Il mio tema personalizzato sembra un po' strano dopo l'installazione del modulo, o vedo una pagina bianca.**
R: Questo modulo funziona principalmente in background e non dovrebbe influenzare l'aspetto visivo del tuo tema.

1.  **Svuota la cache:** La soluzione più comune per i problemi di visualizzazione dopo l'installazione del modulo è svuotare la cache di PrestaShop (**Parametri avanzati > Prestazioni**).
2.  **Verifica la presenza di conflitti:** Se il problema persiste, disabilita temporaneamente altri moduli installati di recente per verificare la presenza di conflitti.
3.  **Errori PHP:** Se vedi una pagina bianca, abilita la segnalazione degli errori PHP sul tuo server (o controlla i log degli errori del tuo server) per identificare eventuali errori critici.
    Se il problema persiste, contatta il supporto MyPresta.eu con i dettagli del tuo tema e di eventuali messaggi di errore.

**D: Come traduco i testi del modulo in altre lingue?**
R:

1.  Vai su **Internazionale > Traduzioni** nel tuo Back Office di PrestaShop.
2.  Seleziona "Traduzioni dei moduli installati" come tipo di traduzione.
3.  Scegli il tuo tema, la lingua che desideri tradurre e quindi seleziona "Microsoft Advertising UET Tag & Conversions API" dall'elenco dei moduli.
4.  Potrai quindi tradurre qualsiasi stringa visibile utilizzata dal modulo.

**D: Perché il "Coach qualità dati" o il "Punteggio di salute" mostrano avvisi?**
R: Questi strumenti sono progettati per aiutarti a ottimizzare il tuo tracciamento. Gli avvisi spesso indicano:

-   **Dati di conversione avanzati mancanti:** Assicurati che i dati del cliente (come l'email) siano disponibili e vengano inviati.
-   **Problemi con i dati del prodotto:** Il tuo catalogo prodotti potrebbe avere GTIN, MPN o altri identificatori mancanti cruciali per la pubblicità del feed di prodotti.
-   **Basso volume di eventi:** Se il tuo negozio ha pochissimo traffico, gli strumenti potrebbero non avere abbastanza dati per fornire un'analisi completa.
    Affronta le raccomandazioni specifiche fornite dagli strumenti per migliorare la qualità dei tuoi dati e la salute del tracciamento.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo `Microsoft Advertising UET Tag & Conversions API` (`mybing`) è costruito seguendo il pattern MVC (Model-View-Controller) di PrestaShop, con una forte enfasi sulla modularità e l'estensibilità. Utilizza un pattern factory per l'istanziazione del tracker (`MybingTrackerFactory`) per supportare diverse modalità di tracciamento (UET, CAPI, Ibrido) e sfrutta un robusto sistema di eventi (`MybingEvents`) per catturare varie azioni di e-commerce. La qualità dei dati e la diagnostica sono gestite da classi dedicate (`MybingHealthScore`, `MybingDataQualityCoach`, `MybingCatalogDoctor`). Il modulo si integra con il sistema di hook di PrestaShop per l'iniezione di eventi nel front-office e utilizza controller admin dedicati per la sua configurazione avanzata e gli strumenti diagnostici.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

-   `mybing/controllers/front/ajax.php`
    -   **Nome classe:** `MybingAjaxModuleFrontController` (estende `ModuleFrontController`)
    -   **Responsabilità:** Gestisce le richieste AJAX dal front-office, principalmente per l'invio di eventi lato client o dati che non possono essere gestiti direttamente dal tag UET (es. per l'integrazione della gestione del consenso, o la raccolta di dati specifici prima di un reindirizzamento di pagina). Potrebbe anche essere utilizzato per l'invio di eventi CAPI che vengono attivati lato client ma necessitano di elaborazione lato server.
-   `mybing/controllers/front/cron.php`
    -   **Nome classe:** `MybingCronModuleFrontController` (estende `ModuleFrontController`)
    -   **Responsabilità:** Fornisce un endpoint per un cron job. Questo è tipicamente utilizzato per attività lato server che devono essere eseguite periodicamente, come l'invio di eventi API delle Conversioni differiti, la sincronizzazione dei dati o l'esecuzione di attività di manutenzione relative alla funzionalità del modulo.
-   `mybing/controllers/front/index.php`
    -   **Nome classe:** `MybingIndexModuleFrontController` (estende `ModuleFrontController`)
    -   **Responsabilità:** Un controller frontale generico, spesso utilizzato come fallback o per interazioni semplici e non AJAX del front-office. In questo modulo, potrebbe essere utilizzato per reindirizzamenti specifici o per gestire le richieste iniziali relative alla configurazione del tracciamento.

#### Controller Admin Back-Office

-   `mybing/controllers/admin/AdminMybingAjaxController.php`
    -   **Nome classe:** `AdminMybingAjaxController` (estende `AdminController`)
    -   **Nome scheda:** Non una scheda autonoma, ma un endpoint AJAX per la configurazione principale del modulo.
    -   **Entità gestita:** Gestisce il caricamento e l'elaborazione dinamica dei dati per le schede diagnostiche e statistiche del modulo (Statistiche in tempo reale, Punteggio di salute, Coach qualità dati, Dottore catalogo). Elabora le richieste per i log degli eventi, i controlli di salute e i rapporti sulla qualità dei dati, restituendo risposte JSON al JavaScript dell'amministratore.
-   `mybing/controllers/admin/index.php`
    -   **Nome classe:** `AdminMybingIndexController` (estende `AdminController`)
    -   **Nome scheda:** Non una scheda autonoma. Questo è un segnaposto o un controller admin generico che potrebbe essere utilizzato per reindirizzamenti o azioni interne specifiche all'interno dell'interfaccia admin del modulo, ma la configurazione principale è gestita dal metodo `getContent()` della classe principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

-   `mybing/classes/autoload.php`: File di autoload standard di PrestaShop, che garantisce il corretto caricamento delle classi del modulo.
-   `mybing/classes/index.php`: File segnaposto, spesso per prevenire l'elenco delle directory.
-   `mybing/classes/MybingCapiClient.php`: Gestisce la comunicazione con l'endpoint dell'API delle Conversioni di Microsoft Advertising. Incapsula le richieste HTTP, l'autenticazione (Token di accesso) e la formattazione dei dati per l'invio di eventi lato server.
-   `mybing/classes/MybingCapiTracker.php`: Implementa `MybingTrackerInterface` per il tracciamento lato server (API delle Conversioni). Responsabile della raccolta dei dati degli eventi, della loro preparazione per il client CAPI e del loro invio.
-   `mybing/classes/MybingCatalogDoctor.php`: Fornisce la logica diagnostica per l'analisi della qualità dei dati dei prodotti, identificando i problemi che potrebbero influenzare i feed di prodotti o il remarketing dinamico in Microsoft Advertising.
-   `mybing/classes/MybingConsent.php`: Gestisce l'integrazione con i moduli di consenso ai cookie. Determina se l'utente ha dato il consenso per il tracciamento e controlla di conseguenza l'attivazione del tag UET.
-   `mybing/classes/MybingCurrencyHelper.php`: Classe di utilità per la gestione delle conversioni e della formattazione delle valute, garantendo che i valori degli eventi vengano inviati correttamente a Microsoft Advertising.
-   `mybing/classes/MybingDataQualityCoach.php`: Analizza la qualità e la completezza dei dati inviati per gli eventi, specialmente per le Conversioni Avanzate, e fornisce raccomandazioni per il miglioramento.
-   `mybing/classes/MybingEventId.php`: Genera e gestisce ID evento univoci per la deduplicazione, cruciale per il tracciamento ibrido (UET + CAPI).
-   `mybing/classes/MybingEventMap.php`: Definisce la mappatura tra le azioni di PrestaShop (es. `actionCartSave`) e i nomi degli eventi di Microsoft Advertising (es. `add_to_cart`), inclusi i parametri personalizzati.
-   `mybing/classes/MybingEvents.php`: Classe centrale per la definizione e l'attivazione di tutti gli eventi di e-commerce tracciati (es. `PageView`, `AddToCart`, `Purchase`). Agisce come un dispatcher di eventi all'interno del modulo.
-   `mybing/classes/MybingHealthScore.php`: Calcola un "punteggio di salute" per la configurazione complessiva del tracciamento, valutando la configurazione, la qualità dei dati e l'attivazione degli eventi.
-   `mybing/classes/MybingHybridTracker.php`: Implementa `MybingTrackerInterface` per il tracciamento ibrido. Orchestra sia il tracciamento del Tag UET che dell'API delle Conversioni, garantendo la deduplicazione degli eventi utilizzando `event_id`.
-   `mybing/classes/MybingLiveStats.php`: Raccoglie e fornisce statistiche in tempo reale sugli eventi tracciati, visualizzate nell'interfaccia di amministrazione.
-   `mybing/classes/MybingProductIdResolver.php`: Aiuta a risolvere e formattare gli ID prodotto in base ai requisiti di Microsoft Advertising (es. GTIN, MPN, custom\_label).
-   `mybing/classes/MybingPropertyRules.php`: Definisce regole e logica per l'estrazione e la formattazione di varie proprietà degli eventi (es. prezzo del prodotto, quantità, categoria) per Microsoft Advertising.
-   `mybing/classes/MybingTrackerFactory.php`: Classe factory responsabile della creazione dell'istanza del tracker appropriata (`MybingUetTracker`, `MybingCapiTracker` o `MybingHybridTracker`) in base alla configurazione del modulo.
-   `mybing/classes/MybingTrackerInterface.php`: Definisce il contratto per tutte le classi tracker, garantendo un'interfaccia coerente per i metodi di tracciamento degli eventi.
-   `mybing/classes/MybingUetTracker.php`: Implementa `MybingTrackerInterface` per il tracciamento lato client (Tag UET). Responsabile della generazione del codice JavaScript da iniettare nel front-office.
-   `mybing/classes/MybingUserData.php`: Raccoglie e formatta i dati specifici dell'utente (es. email, telefono, indirizzo) per le Conversioni Avanzate, inclusa l'hashing.

### 4.4 Risorse JavaScript (`views/js/`)

-   `mybing/views/js/mybing-admin.js`: JavaScript del back-office per la funzionalità admin generale, le interazioni con i moduli e gli aggiornamenti dinamici all'interno della pagina di configurazione del modulo.
-   `mybing/views/js/mybing-debug.js`: JavaScript del front-office specifico per la modalità debug, che visualizza le informazioni di tracciamento e i payload degli eventi all'amministratore.
-   `mybing/views/js/mybing-ghost.js`: JavaScript del front-office, potenzialmente per la gestione di eventi "fantasma" o interazioni specifiche lato client che devono essere tracciate senza un'azione diretta dell'utente.
-   `mybing/views/js/mybing-live.js`: JavaScript del back-office per la scheda "Statistiche in tempo reale", che gestisce le richieste AJAX a `AdminMybingAjaxController` e aggiorna il feed degli eventi in tempo reale.
-   `mybing/views/js/mybing-tcf.js`: JavaScript del front-office per l'integrazione con Transparency and Consent Framework (TCF) o altre piattaforme di gestione del consenso, garantendo che il Tag UET si attivi solo con il consenso.
-   `mybing/views/js/mybing-wizard.js`: JavaScript del back-office per la procedura guidata di configurazione iniziale, che guida il commerciante attraverso i passaggi di configurazione.
-   `mybing/views/js/mybing.js`: File JavaScript principale del front-office. Contiene la logica principale per l'inizializzazione del Tag UET, la cattura degli eventi lato client (es. `add_to_cart`) e l'invio dei dati al Tag UET o al controller AJAX del modulo per l'elaborazione CAPI. Si lega a vari eventi DOM e agli eventi `prestashop.on` di PrestaShop.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `mybing/views/css/mybing-admin.css`: CSS del back-office per lo stile della pagina di configurazione del modulo, degli strumenti diagnostici e della procedura guidata, garantendo un'interfaccia di amministrazione coerente e user-friendly.
-   `mybing/views/css/mybing-debug.css`: CSS del front-office per lo stile dell'overlay di debug, rendendo le informazioni di tracciamento chiaramente visibili all'amministratore senza interrompere il design del negozio.

### 4.6 Struttura del template Smarty (`views/templates/`)

#### Template per hook (`views/templates/hook/`)

-   `mybing/views/templates/hook/capi-pageview.tpl`: Renderizza un elemento o script nascosto per attivare un evento PageView lato server tramite CAPI, spesso utilizzato quando il tag UET potrebbe essere bloccato.
-   `mybing/views/templates/hook/debug.tpl`: Renderizza la struttura HTML per l'overlay di debug del front-office, visualizzando i dati degli eventi.
-   `mybing/views/templates/hook/displayOrderConfirmation.tpl`: Iniettato nell'hook `displayOrderConfirmation`. Renderizza lo script dell'evento di acquisto del Tag UET e/o attiva l'evento di acquisto CAPI dopo un ordine riuscito.
-   `mybing/views/templates/hook/ghost.tpl`: Renderizza uno script o un elemento nascosto per il tracciamento "fantasma", potenzialmente per eventi in background specifici o raccolta di dati.
-   `mybing/views/templates/hook/header.tpl`: Iniettato nell'hook `displayHeader`. Renderizza lo script base principale del Tag UET, l'integrazione della gestione del consenso e gli eventi PageView iniziali.
-   `mybing/views/templates/hook/payment.tpl`: Potenzialmente utilizzato per tracciare eventi relativi alla selezione o all'avvio del metodo di pagamento, sebbene `displayOrderConfirmation` sia più comune per l'acquisto finale.
-   `mybing/views/templates/hook/product-details.tpl`: Iniettato in un hook della pagina prodotto (es. `displayProductButtons` o `displayProductExtraContent`). Renderizza script per eventi `view_item` e listener di eventi `add_to_cart`.

#### Template per admin (`views/templates/admin/`)

-   `mybing/views/templates/admin/consent-guide.tpl`: Visualizza indicazioni e informazioni relative all'integrazione della gestione del consenso.
-   `mybing/views/templates/admin/doctor.tpl`: Renderizza l'interfaccia per lo strumento diagnostico "Dottore catalogo".
-   `mybing/views/templates/admin/dq.tpl`: Renderizza l'interfaccia per le raccomandazioni del "Coach qualità dati".
-   `mybing/views/templates/admin/health.tpl`: Renderizza l'interfaccia per la panoramica del "Punteggio di salute".
-   `mybing/views/templates/admin/linker-domains.tpl`: Renderizza il campo di input e la spiegazione per la configurazione dei domini di collegamento.
-   `mybing/views/templates/admin/live-maintain.tpl`: Renderizza un messaggio di manutenzione o lo stato per la funzionalità delle statistiche in tempo reale.
-   `mybing/views/templates/admin/live.tpl`: Renderizza l'interfaccia per le "Statistiche in tempo reale", visualizzando gli eventi recenti.
-   `mybing/views/templates/admin/mode-context.tpl`: Fornisce informazioni contestuali sulla modalità di tracciamento scelta.
-   `mybing/views/templates/admin/mode-note-both.tpl`: Visualizza una nota o una spiegazione specifica quando è selezionata la modalità "Entrambi (Ibrido)".
-   `mybing/views/templates/admin/mode-note-capi.tpl`: Visualizza una nota o una spiegazione specifica quando è selezionata la modalità "Solo API delle Conversioni".
-   `mybing/views/templates/admin/mode-note-uet.tpl`: Visualizza una nota o una spiegazione specifica quando è selezionata la modalità "Solo Tag UET".
-   `mybing/views/templates/admin/mode-picker.tpl`: Renderizza i pulsanti radio o il menu a discesa per la selezione della modalità di tracciamento.
-   `mybing/views/templates/admin/properties-list.tpl`: Renderizza un elenco o una tabella delle proprietà degli eventi e dei loro valori per la configurazione o la visualizzazione.
-   `mybing/views/templates/admin/recent-events.tpl`: Renderizza una tabella o un elenco di eventi tracciati di recente, spesso parte delle "Statistiche in tempo reale".
-   `mybing/views/templates/admin/tabs.tpl`: Renderizza la struttura di navigazione a schede per la pagina di configurazione del modulo (es. Generale, Statistiche in tempo reale, Punteggio di salute).
-   `mybing/views/templates/admin/tag-chips.tpl`: Renderizza "chip" visivi o indicatori per gli ID Tag UET configurati.
-   `mybing/views/templates/admin/tag-ids.tpl`: Renderizza il campo di input per gli ID Tag UET.
-   `mybing/views/templates/admin/wizard.tpl`: Renderizza l'interfaccia passo-passo per la procedura guidata di configurazione iniziale.

#### Template per front-office (`views/templates/front/`)

-   Nessun template di pagina standalone dedicato identificato. Il rendering del front-office è gestito principalmente tramite template di hook.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

Il modulo non crea esplicitamente tabelle SQL personalizzate in base all'inventario fornito. I record di configurazione sono archiviati nella tabella `ps_configuration` di PrestaShop, utilizzando chiavi con prefisso `MYBING_` (es. `MYBING_UET_ID`, `MYBING_CAPI_TOKEN`, `MYBING_TRACKING_MODE`).

#### Tabella degli hook registrati

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Inietta il JavaScript base del Tag UET, inizializza la gestione del consenso e attiva gli eventi `PageView`. |
| `displayOrderConfirmation` | Nella pagina di conferma dell'ordine dopo un acquisto riuscito. | Attiva gli eventi `Purchase` sia per il Tag UET che per l'API delle Conversioni, inclusi i dettagli dell'ordine. |
| `actionFrontControllerSetMedia` | Quando un controller frontale imposta le sue risorse multimediali. | Inietta JavaScript e CSS specifici del modulo nel front-office. |
| `actionCartSave` | Quando un prodotto viene aggiunto o rimosso dal carrello. | Attiva gli eventi `AddToCart` o `RemoveFromCart`. |
| `actionProductAdd` | Quando un prodotto viene aggiunto al carrello (specifico per alcuni temi/moduli). | Hook alternativo o supplementare per gli eventi `AddToCart`. |
| `actionProductUpdate` | Quando un prodotto viene aggiornato nel Back Office. | Potenzialmente utilizzato dal `Catalog Doctor` per rivalutare la qualità dei dati del prodotto. |
| `actionObjectProductUpdateAfter` | Dopo l'aggiornamento di un `ObjectModel` prodotto. | Simile a `actionProductUpdate`, per controlli di qualità dei dati o invalidazione della cache. |
| `actionObjectOrderAddAfter` | Dopo l'aggiunta di un `ObjectModel` ordine. | Attiva gli eventi `Purchase` lato server tramite l'API delle Conversioni, garantendo un tracciamento robusto. |
| `actionObjectOrderUpdateAfter` | Dopo l'aggiornamento di un `ObjectModel` ordine. | Potenzialmente per il tracciamento delle modifiche dello stato dell'ordine (es. rimborso, annullamento) se configurato in Microsoft Ads. |
| `displayProductExtraContent` | Nella pagina del prodotto, spesso sotto il contenuto principale. | Può essere utilizzato per iniettare script di tracciamento specifici del prodotto o dati per gli eventi `ViewItem`. |
| `displayFooter` | Alla fine della sezione `<body>` di ogni pagina del front-office. | Può essere utilizzato per il caricamento differito di script o elementi di tracciamento aggiuntivi. |
| `actionAdminControllerSetMedia` | Quando un controller admin imposta le sue risorse multimediali. | Inietta JavaScript e CSS specifici del modulo nel Back Office per la pagina di configurazione. |
| `actionAdminMybingAjaxController` | Hook personalizzato per `AdminMybingAjaxController` per gestire azioni AJAX specifiche. | Utilizzato internamente per aggiornamenti dinamici e recupero dati nelle schede diagnostiche del modulo. |
| `actionModuleInstall` | Durante l'installazione del modulo. | Esegue la configurazione iniziale, crea voci di configurazione e registra gli hook. |
| `actionModuleUninstall` | Durante la disinstallazione del modulo. | Pulisce le voci di configurazione e annulla la registrazione degli hook. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale per gli sviluppatori, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema tecnico o domanda relativa alla funzionalità del modulo.
