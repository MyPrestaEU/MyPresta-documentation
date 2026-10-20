---
title: "Amazon Ads Tag Conversions API - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Amazon Ads Tag Conversions API di MyPresta.eu."
sidebar:
  label: "Amazon Ads Tag Conversions API - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Amazon Ads Tag Conversions API su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/amazon-ads-tag-conversions-api.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/amazon-ads-tag-conversions-api/)
>
> ---


# Amazon Ads Tag Conversions API

## 1. Requisiti e Compatibilità

-   **Versioni PrestaShop Supportate**: PrestaShop 1.7.x, 8.x, 9.x
-   **Compatibilità PHP**: PHP 7.1 - 8.5
-   **Requisiti di Hosting**: Sono richieste estensioni PHP standard (cURL, JSON, OpenSSL) affinché il modulo funzioni correttamente, specialmente per la Conversions API (CAPI) che si basa su una comunicazione sicura server-to-server. Il tuo ambiente di hosting dovrebbe anche consentire connessioni in uscita agli endpoint API di Amazon.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

Questa sezione ti guida attraverso ogni impostazione del modulo "Amazon Ads Tag Conversions API".

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale dove imposterai il tracciamento degli annunci Amazon.

**Accesso:** Naviga su **Moduli > Gestione moduli**, quindi trova "Amazon Ads Tag Conversions API" e clicca su **Configura**.

#### **Selezione della Modalità di Tracciamento**

Questa sezione determina come il tuo negozio invia i dati ad Amazon.

-   **Cosa fa questa impostazione:** Ti permette di scegliere tra tre metodi principali per inviare i dati di conversione ad Amazon: Amazon Ads Tag (lato client), Conversions API (lato server) o una combinazione di entrambi.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su "Amazon Ads Tag (Lato Client)":* Il modulo si baserà principalmente sul tag JavaScript posizionato nel browser del cliente per inviare i dati. Questo è suscettibile agli ad blocker.
    -   *Quando impostato su "Conversions API (Lato Server)":* Il modulo invierà i dati direttamente dal tuo server PrestaShop ai server di Amazon. Questo è più affidabile e bypassa gli ad blocker.
    -   *Quando impostato su "Modalità Duale (Ibrida)":* Il modulo invierà i dati utilizzando sia l'Amazon Ads Tag che la Conversions API. Questo fornisce la massima resilienza e accuratezza dei dati.
-   **Valore consigliato:** **"Modalità Duale (Ibrida)"** per il tracciamento più robusto e accurato. Se sei molto preoccupato per la privacy e vuoi minimizzare gli script lato client, "Conversions API (Lato Server)" è una valida alternativa.
-   **Scenario / esempio per il commerciante:** Se hai notato una discrepanza tra le conversioni riportate dai tuoi annunci Amazon e le tue vendite effettive su PrestaShop, il passaggio a "Modalità Duale" o "Conversions API" può migliorare significativamente l'accuratezza recuperando le conversioni perse a causa degli ad blocker.

#### **ID Tag Amazon Ads**

-   **Cosa fa questa impostazione:** Questo è il tuo identificatore univoco fornito da Amazon Ads per il tuo tag di tracciamento. Indica ad Amazon a quale account attribuire i dati di conversione.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando viene inserito un ID valido:* L'Amazon Ads Tag (se abilitato nella tua modalità di tracciamento) invierà correttamente i dati al tuo account Amazon Ads.
    -   *Quando lasciato vuoto o viene inserito un ID non valido:* Il tracciamento lato client non funzionerà e i dati non verranno inviati al tuo account Amazon Ads tramite il tag.
-   **Valore consigliato:** Il tuo specifico ID Tag Amazon Ads. Puoi trovarlo nel tuo account Amazon Ads sotto "Gestione Eventi" o "Pubblico".
-   **Scenario / esempio per il commerciante:** Hai appena configurato una nuova campagna Amazon Ads. Inserire l'ID Tag corretto qui è il primo passo per assicurarti che le prestazioni della tua campagna siano tracciate.

#### **Token di Accesso API di Conversione Amazon**

-   **Cosa fa questa impostazione:** Questo è un token sicuro fornito da Amazon Ads che autentica il tuo server quando invia dati tramite l'API di Conversione. Garantisce che solo le fonti autorizzate possano inviare dati al tuo account Amazon Ads.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando viene inserito un token valido:* Il tuo server PrestaShop può inviare in modo sicuro i dati di conversione direttamente ad Amazon tramite l'API di Conversione (se abilitata nella tua modalità di tracciamento).
    -   *Quando lasciato vuoto o viene inserito un token non valido:* Il tracciamento lato server tramite l'API di Conversione non funzionerà e i dati non verranno inviati al tuo account Amazon Ads tramite CAPI.
-   **Valore consigliato:** Il tuo specifico Token di Accesso API di Conversione Amazon. Questo viene generato nel tuo account Amazon Ads, tipicamente sotto "Gestione Eventi" o "Sorgenti Dati". Tratta questo token come una password; mantienilo sicuro.
-   **Scenario / esempio per il commerciante:** Vuoi migliorare l'affidabilità del tuo tracciamento delle conversioni utilizzando l'API di Conversione. Dopo aver generato il token in Amazon Ads, incollalo qui per abilitare la trasmissione dei dati lato server.

#### **Abilita Modalità Debug**

-   **Cosa fa questa impostazione:** Attiva una modalità speciale che visualizza informazioni dettagliate sui dati inviati ad Amazon, visibili solo a te (o a chiunque abbia gli strumenti per sviluppatori aperti) nella console del browser. Questo è prezioso per la risoluzione dei problemi.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* Vedrai log della console e potenzialmente overlay sullo schermo (a seconda dell'implementazione specifica del debug) che mostrano quali eventi vengono attivati e quali dati vengono inviati ad Amazon. Questo non è visibile ai clienti normali.
    -   *Quando disabilitato:* Non verranno visualizzate informazioni di debug.
-   **Valore consigliato:** **"NO"** per i negozi in produzione. Abilita temporaneamente solo durante la configurazione o la risoluzione dei problemi.
-   **Scenario / esempio per il commerciante:** Hai configurato il modulo, ma le conversioni non vengono visualizzate nel tuo account Amazon Ads. L'abilitazione della modalità debug può aiutarti a vedere se gli eventi vengono attivati correttamente sul tuo sito web e se il payload dei dati sembra accurato.

#### **Integrazione Gestione Consenso**

-   **Cosa fa questa impostazione:** Permette al modulo di integrarsi con la soluzione di consenso ai cookie del tuo negozio. Ciò garantisce che il tracciamento di Amazon Ads si attivi solo dopo che un cliente ha dato il suo esplicito consenso, rispettando le normative sulla privacy come il GDPR o il CCPA.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato e integrato con un modulo di consenso:* L'Amazon Ads Tag (lato client) caricherà e attiverà gli eventi solo se il cliente ha accettato i cookie di tracciamento. La CAPI lato server potrebbe comunque inviare dati anonimi o attendere il consenso a seconda della tua configurazione specifica e delle politiche sulla privacy.
    -   *Quando disabilitato:* Il modulo tenterà di tracciare gli eventi senza controlli espliciti del consenso, il che potrebbe non essere conforme alle leggi sulla privacy in alcune regioni.
-   **Valore consigliato:** **"SÌ"** se il tuo negozio opera in regioni con leggi sulla privacy severe (es. UE, California) e utilizzi un modulo di consenso ai cookie.
-   **Scenario / esempio per il commerciante:** Il tuo negozio serve clienti in Europa e utilizzi un banner per i cookie conforme al GDPR. L'abilitazione di questa impostazione garantisce che il tuo tracciamento di Amazon Ads rispetti le scelte di privacy dei clienti.

#### **Impostazioni Avanzate (es. Data Layer, Mappatura Eventi, Risoluzione ID Prodotto)**

Il modulo può includere impostazioni avanzate che consentono una messa a punto della raccolta e trasmissione dei dati. Queste sono tipicamente per utenti più tecnici o scenari specifici.

-   **Tracciamento Data Layer:**
    -   **Cosa fa questa impostazione:** Determina se il modulo deve utilizzare un "data layer" standardizzato per raccogliere informazioni dal tuo negozio. Questo è spesso utilizzato per la compatibilità con altri strumenti di tracciamento o implementazioni personalizzate.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il modulo cercherà e invierà dati a un oggetto JavaScript `dataLayer`, che può essere utile per il debug o l'integrazione con Google Tag Manager.
        -   *Quando disabilitato:* Il modulo raccoglierà i dati direttamente dalle variabili interne di PrestaShop.
    -   **Valore consigliato:** **"SÌ"** se stai utilizzando Google Tag Manager o altri strumenti che si basano su un data layer. Altrimenti, "NO" di solito va bene.
-   **Mappatura Eventi:**
    -   **Cosa fa questa impostazione:** Ti permette di personalizzare come specifiche azioni di PrestaShop (es. "aggiungi al carrello") vengono mappate ai nomi degli eventi di Amazon Ads.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando personalizzato:* Puoi inviare nomi di eventi diversi ad Amazon rispetto a quelli predefiniti del modulo, il che potrebbe essere utile per configurazioni specifiche di campagne Amazon Ads.
        -   *Quando predefinito:* Il modulo utilizza la sua mappatura predefinita.
    -   **Valore consigliato:** Lasciare predefinito a meno che tu non abbia un motivo specifico per cambiarlo in base alla documentazione di Amazon Ads.
-   **Risoluzione ID Prodotto:**
    -   **Cosa fa questa impostazione:** Definisce quale identificatore di prodotto (es. ID Prodotto, EAN, UPC, SKU) il modulo deve inviare ad Amazon per gli eventi correlati al prodotto.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su ID Prodotto:* Amazon riceverà l'ID prodotto interno di PrestaShop.
        -   *Quando impostato su EAN/UPC/SKU:* Amazon riceverà l'identificatore di prodotto corrispondente. Questo è cruciale per abbinare i prodotti nel tuo catalogo prodotti Amazon.
    -   **Valore consigliato:** Scegli l'identificatore che corrisponde più coerentemente agli ID prodotto che utilizzi nei tuoi feed di prodotti Amazon o nel catalogo. **EAN/UPC** è spesso preferito per i prodotti al dettaglio.
-   **Domini di collegamento (Linker Domains):**
    -   **Cosa fa questa impostazione:** Specifica domini aggiuntivi che dovrebbero essere inclusi nel tracciamento cross-domain. Questo è importante se il tuo processo di checkout o altre parti del percorso del cliente coinvolgono più domini (es. un sottodominio separato per un blog o un gateway di pagamento che reindirizza).
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando configurato:* L'Amazon Ads Tag può mantenere la continuità del tracciamento tra diversi domini, prevenendo la perdita di attribuzione.
        -   *Quando non configurato per più domini:* Le conversioni potrebbero essere attribuite erroneamente o perse se il cliente naviga tra i domini durante il suo percorso.
    -   **Valore consigliato:** Aggiungi tutti i domini o sottodomini che fanno parte del percorso del tuo cliente.
-   **Helper Valuta:**
    -   **Cosa fa questa impostazione:** Assicura che i valori di valuta inviati ad Amazon siano formattati correttamente e corrispondano alla valuta utilizzata nel tuo account Amazon Ads.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando configurato correttamente:* Amazon riceve valori di valuta accurati.
        -   *Quando configurato in modo errato:* I valori di valuta potrebbero essere interpretati erroneamente da Amazon, portando a report errati.
    -   **Valore consigliato:** Assicurati che questo si allinei con la valuta principale del tuo negozio e la valuta del tuo account Amazon Ads.

### 2.2 Schermate di amministrazione dedicate e viste del controller

Il modulo fornisce diverse schermate dedicate per aiutarti a monitorare e ottimizzare il tracciamento degli annunci Amazon. Queste sono tipicamente accessibili tramite schede o sottosezioni all'interno della configurazione principale del modulo.

#### **4.2.1 Statistiche in Tempo Reale**

-   **Nome schermata e posizione nel menu:** Solitamente una scheda all'interno della configurazione principale del modulo (es. "Statistiche in Tempo Reale").
-   **Azioni e impostazioni disponibili:** Questa schermata visualizza dati in tempo reale o quasi in tempo reale sugli eventi inviati ad Amazon. Potrebbe mostrare:
    -   Eventi recenti (es. PageView, AddToCart, Purchase) con timestamp.
    -   Tipi di eventi e la loro frequenza.
    -   Punteggi di qualità dei dati.
    -   Visualizzazioni dell'attività di tracciamento.
-   **Effetto delle modifiche:** Questa è una schermata di reporting; non ci sono impostazioni dirette da modificare qui. Riflette i dati inviati in base alla tua configurazione principale.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Controlla regolarmente questa schermata per assicurarti che gli eventi vengano attivati come previsto, specialmente dopo aver apportato modifiche al tuo negozio o lanciato nuove campagne. È la tua prima linea di difesa per identificare i problemi di tracciamento.

#### **4.2.2 Punteggio di Salute e Radar di Recupero**

-   **Nome schermata e posizione nel menu:** Spesso una scheda all'interno della configurazione principale del modulo (es. "Punteggio di Salute" o "Diagnostica").
-   **Azioni e impostazioni disponibili:** Questa sezione fornisce un punteggio di salute generale per il tracciamento degli annunci Amazon e identifica potenziali problemi o conversioni "perse". Potrebbe includere:
    -   Un punteggio percentuale che indica la salute del tracciamento.
    -   Raccomandazioni per migliorare la qualità dei dati.
    -   Un "Radar di Recupero" che mostra le conversioni stimate che potrebbero essere state perse a causa di ad blocker o altri problemi, e come CAPI sta aiutando a recuperarle.
    -   Avvisi su ID Tag mancanti, Token di Accesso o problemi di consenso.
-   **Effetto delle modifiche:** Come le Statistiche in Tempo Reale, questa è principalmente una schermata di reporting e diagnostica. Le azioni che intraprendi in base alle sue raccomandazioni (es. aggiornare un ID Tag mancante) miglioreranno il tuo tracciamento.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Rivedi periodicamente il tuo Punteggio di Salute. Un punteggio basso o un "Radar di Recupero" attivo indicano aree in cui il tuo tracciamento potrebbe essere migliorato, portando potenzialmente a migliori prestazioni degli annunci.

#### **4.2.3 Coach Qualità Dati / Dottore Catalogo**

-   **Nome schermata e posizione nel menu:** Potenzialmente una scheda all'interno della configurazione principale del modulo (es. "Qualità Dati" o "Dottore Catalogo").
-   **Azioni e impostazioni disponibili:** Questi strumenti ti aiutano a garantire che i dati che stai inviando ad Amazon siano di alta qualità e formattati correttamente. Potrebbero:
    -   Controllare problemi comuni dei dati (es. ID prodotto mancanti, formati di valuta errati).
    -   Fornire suggerimenti per migliorare i dati del tuo catalogo prodotti per soddisfare meglio i requisiti di Amazon.
    -   Evidenziare discrepanze tra dati lato client e lato server.
-   **Effetto delle modifiche:** Questa schermata fornisce informazioni utili. Affrontare i problemi evidenziati qui (es. aggiornare gli EAN dei prodotti nel tuo catalogo PrestaShop) migliorerà direttamente la qualità e le capacità di corrispondenza dei tuoi dati di conversione in Amazon Ads.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Se stai riscontrando problemi con la corrispondenza dei prodotti in Amazon Ads o vedi avvisi nel tuo Punteggio di Salute, consulta questi strumenti per affinare i tuoi dati.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Principale | **Modalità di Tracciamento** | Modalità Duale (Ibrida) | Determina se il tracciamento è lato client, lato server o entrambi. La Modalità Duale offre la massima resilienza. |
| Configurazione Principale | **ID Tag Amazon Ads** | Il tuo ID Tag Amazon | Essenziale per il tracciamento lato client. Collega i dati al tuo account Amazon Ads. |
| Configurazione Principale | **Token di Accesso API di Conversione Amazon** | Il tuo Token di Accesso CAPI | Essenziale per il tracciamento lato server. Autentica il tuo server con Amazon. |
| Configurazione Principale | **Abilita Modalità Debug** | NO | Visualizza i dati di tracciamento nella console del browser per la risoluzione dei problemi. Disabilita sui negozi live. |
| Configurazione Principale | **Integrazione Gestione Consenso** | SÌ (se applicabile) | Assicura che il tracciamento rispetti la privacy del cliente e il consenso ai cookie. |
| Configurazione Principale | **Tracciamento Data Layer** | SÌ (se si usa GTM) | Utilizza un data layer per la raccolta degli eventi, utile per GTM o integrazioni personalizzate. |
| Configurazione Principale | **Risoluzione ID Prodotto** | EAN/UPC | Definisce quale identificatore di prodotto viene inviato ad Amazon per la corrispondenza. Cruciale per la corrispondenza del catalogo. |
| Configurazione Principale | **Domini di collegamento** | Vuoto (aggiungi se necessario) | Mantiene il tracciamento su più domini nel percorso del cliente. |
| Statistiche in Tempo Reale | (Solo Report) | N/A | Mostra i dati degli eventi in tempo reale, aiutandoti a verificare che il tracciamento sia attivo. |
| Punteggio di Salute | (Solo Report) | N/A | Fornisce una valutazione generale della salute del tuo tracciamento e identifica i problemi. |
| Qualità Dati | (Solo Report) | N/A | Aiuta a identificare e risolvere i problemi di qualità dei dati nel tuo catalogo prodotti per una migliore corrispondenza con Amazon. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Le mie conversioni di Amazon Ads non corrispondono alle mie vendite PrestaShop. Cosa devo fare?**
R1: Questo è un problema comune, spesso dovuto agli ad blocker.
\* **Controlla la Modalità di Tracciamento:** Assicurati di utilizzare "Modalità Duale (Ibrida)" o "Conversions API (Lato Server)" nelle impostazioni del modulo. Questo è il modo più efficace per recuperare le conversioni perse.
\* **Verifica ID/Token:** Ricontrolla che il tuo ID Tag Amazon Ads e il Token di Accesso API di Conversione siano inseriti correttamente nella configurazione del modulo.
\* **Usa la Modalità Debug:** Abilita temporaneamente la "Modalità Debug" ed effettua un acquisto di prova. Controlla la console del tuo browser e le "Statistiche in Tempo Reale" del modulo per vedere se gli eventi vengono attivati.
\* **Svuota la Cache:** Vai su **Parametri Avanzati > Prestazioni** nel back office di PrestaShop e svuota la cache di Smarty e le altre cache. A volte il vecchio codice del modulo può persistere.

**D2: Vedo avvisi su "Qualità dei Dati" o "ID Prodotto Mancanti" nel Punteggio di Salute del modulo. Come posso risolvere?**
R2: Amazon si affida a dati di prodotto di alta qualità per una corrispondenza accurata.
\* **Risoluzione ID Prodotto:** Nella configurazione del modulo, assicurati che l'impostazione "Risoluzione ID Prodotto" (es. EAN, UPC, SKU) corrisponda all'identificatore principale utilizzato nel tuo feed di prodotti Amazon.
\* **Aggiorna i Dati del Prodotto:** Vai su **Catalogo > Prodotti** nel back office di PrestaShop. Modifica i prodotti segnalati dal "Coach Qualità Dati" e assicurati che abbiano EAN, UPC o SKU completi e accurati come richiesto.
\* **Coerenza:** Assicurati che gli identificatori di prodotto nel tuo negozio PrestaShop siano coerenti con quelli che fornisci ad Amazon nei tuoi feed di prodotti.

**D3: Il mio sito web utilizza un banner per il consenso ai cookie. Questo modulo rispetterà le scelte dei clienti?**
R3: Sì, se configurato correttamente.
\* **Abilita l'Integrazione del Consenso:** Nella configurazione del modulo, assicurati che "Integrazione Gestione Consenso" sia abilitata.
\* **Compatibilità Modulo Cookie:** Questo modulo è progettato per integrarsi con i moduli di consenso ai cookie standard di PrestaShop. Se utilizzi una soluzione personalizzata, potresti dover assicurarti che attivi correttamente gli eventi `prestashop.on('updateProduct', ...)` o simili a cui i moduli sono in ascolto per le modifiche del consenso.
\* **CAPI vs. Tag:** Ricorda che l'API di Conversione (lato server) è meno influenzata dai banner di consenso lato client rispetto all'Amazon Ads Tag (lato client), poiché invia i dati direttamente dal tuo server. Tuttavia, è comunque buona pratica inviare informazioni di identificazione personale (PII) tramite CAPI solo dopo il consenso.

**D4: Il modulo sembra rallentare il mio sito. Cosa posso fare?**
R4: Questo modulo è ottimizzato per le prestazioni, ma ecco alcuni controlli:
\* **Disabilita la Modalità Debug:** Assicurati che la "Modalità Debug" sia disabilitata sul tuo negozio live, poiché aggiunge un logging extra alla console.
\* **Prestazioni del Server:** L'API di Conversione (CAPI) effettua chiamate server-to-server. Sebbene generalmente veloci, assicurati che il tuo server di hosting abbia risorse adeguate e una connessione internet stabile.
\* **Altri Moduli:** Controlla se altri moduli di tracciamento o pubblicitari pesanti sono in esecuzione contemporaneamente. Troppi script lato client possono influire sulle prestazioni.
\* **Svuota la Cache:** Svuota sempre la cache di PrestaShop dopo aver apportato modifiche alla configurazione.

**D5: Ricevo un messaggio di errore quando cerco di salvare la configurazione del modulo.**
R5:
\* **Controlla i Permessi:** Assicurati che la cartella del modulo (`/modules/myamazon/`) e le sue sottocartelle abbiano i permessi di scrittura corretti (solitamente 755 per le cartelle, 644 per i file).
\* **Log del Server:** Controlla i log degli errori PHP del tuo server per informazioni più dettagliate sull'errore. Questo può essere spesso trovato nel tuo pannello di controllo dell'hosting o contattando il tuo host.
\* **Modalità Debug di PrestaShop:** Abilita temporaneamente la modalità debug di PrestaShop (in `config/defines.inc.php`, cambia `define('_PS_MODE_DEV_', false);` in `define('_PS_MODE_DEV_', true);`) per vedere messaggi di errore più dettagliati sullo schermo.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

Questa sezione fornisce un'analisi approfondita della struttura tecnica del modulo "Amazon Ads Tag Conversions API", destinata a sviluppatori e webmaster.

### 4.1 Panoramica dell'Architettura

Il modulo `myamazon` è costruito seguendo il pattern MVC (Model-View-Controller) di PrestaShop, con una forte enfasi sulla modularità e sul tracciamento basato su eventi. Sfrutta sia meccanismi lato client (Amazon Ads Tag) che lato server (Conversions API), spesso in un approccio ibrido.

Componenti architettonici chiave:

-   **Classe Principale del Modulo (`myamazon/index.php`):** Gestisce l'installazione, la disinstallazione, la registrazione degli hook e il metodo `getContent()` primario per la configurazione del back-office.
-   **Controller:** Controller frontali dedicati per le interazioni AJAX e controller admin per la gestione delle impostazioni del modulo e delle viste diagnostiche.
-   **Classi Core (`classes/`):** Un robusto set di classi gestisce vari aspetti:
    -   **Logica di Tracciamento:** `MyamazonAatTracker.php` (lato client), `MyamazonCapiTracker.php` (lato server), `MyamazonHybridTracker.php` (modalità duale), `MyamazonTrackerFactory.php` (istanze dei tracker).
    -   **Gestione Dati:** `MyamazonUserData.php` (dati cliente), `MyamazonEventMap.php` (traduzione eventi), `MyamazonProductIdResolver.php` (logica ID prodotto), `MyamazonCurrencyHelper.php`.
    -   **Client API:** `MyamazonCapiClient.php` (gestisce la comunicazione con Amazon CAPI).
    -   **Diagnostica e Salute:** `MyamazonHealthScore.php`, `MyamazonCatalogDoctor.php`, `MyamazonDataQualityCoach.php`, `MyamazonLiveStats.php`.
    -   **Consenso:** `MyamazonConsent.php` (si integra con i meccanismi di consenso).
-   **Hook:** Ampio utilizzo degli hook di PrestaShop per iniettare JavaScript, catturare eventi e inviare dati in punti critici del percorso del cliente.
-   **Template Smarty:** Utilizzati per il rendering sia delle viste di configurazione del back-office che degli script di tracciamento del front-office.
-   **JavaScript:** Gestisce l'iniezione del tag lato client, l'ascolto degli eventi e le interazioni del data layer.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

-   `controllers/front/ajax.php`
    -   **Nome Classe:** `MyamazonAjaxModuleFrontController` (estende `ModuleFrontController`)
    -   **Responsabilità:** Gestisce le richieste asincrone (AJAX) dal front-office. Questo è tipicamente utilizzato per l'invio di eventi lato server tramite CAPI che non possono essere eseguiti direttamente nel browser (es. eventi post-acquisto dove il browser potrebbe essere chiuso, o eventi che richiedono l'elaborazione dei dati lato server). Riceve i dati da JavaScript lato client e li invia a `MyamazonCapiTracker`.
-   `controllers/front/index.php`
    -   **Nome Classe:** `MyamazonIndexModuleFrontController` (estende `ModuleFrontController`)
    -   **Responsabilità:** Questo controller potrebbe servire come fallback o come semplice punto di ingresso, sebbene il suo caso d'uso primario potrebbe essere minimo se `ajax.php` gestisce la maggior parte delle interazioni front-end. Potrebbe essere utilizzato per reindirizzamenti specifici o semplici visualizzazioni di dati se necessario, ma spesso serve come segnaposto.

#### Controller Admin Back-Office

-   `controllers/admin/AdminMyamazonAjaxController.php`
    -   **Nome Classe:** `AdminMyamazonAjaxController` (estende `ModuleAdminController`)
    -   **Nome Tab:** Non direttamente una tab di menu, ma un endpoint AJAX per l'interfaccia admin.
    -   **Responsabilità:** Gestisce le richieste AJAX provenienti dalle pagine di configurazione del back-office del modulo. Ciò include il recupero dei dati per le statistiche in tempo reale, i punteggi di salute o l'esecuzione di controlli in background (es. validazione del token API) senza ricaricare l'intera pagina. Interagisce con classi come `MyamazonLiveStats`, `MyamazonHealthScore` e `MyamazonCapiClient`.
-   `controllers/admin/index.php`
    -   **Nome Classe:** `AdminMyamazonIndexController` (estende `ModuleAdminController`)
    -   **Nome Tab:** Non una tab di menu diretta.
    -   **Responsabilità:** Simile a `index.php` del front-office, questo potrebbe essere un segnaposto o gestire interazioni admin molto specifiche e non AJAX. La logica di configurazione principale risiede nel metodo `getContent()` del modulo principale.

### 4.3 Classi Core e Modelli (`classes/`)

-   `classes/autoload.php`: File di autoload standard di PrestaShop.
-   `classes/index.php`: File segnaposto, comune nelle directory vuote.
-   `classes/MyamazonAatTracker.php`:
    -   **Responsabilità:** Implementa la logica per il tracciamento lato client di Amazon Ads Tag. Genera il JavaScript necessario per `aa.js` e invia gli eventi al data layer del browser o direttamente all'Amazon Ads Tag.
-   `classes/MyamazonCapiClient.php`:
    -   **Responsabilità:** Gestisce le richieste HTTP effettive agli endpoint dell'API di Conversione di Amazon. Incapsula la logica cURL o Guzzle (se utilizzata), l'autenticazione con il token di accesso e la gestione degli errori per la comunicazione server-to-server.
-   `classes/MyamazonCapiTracker.php`:
    -   **Responsabilità:** Implementa la logica per il tracciamento lato server dell'API di Conversione. Formatta i dati degli eventi secondo le specifiche CAPI di Amazon e utilizza `MyamazonCapiClient` per inviarli.
-   `classes/MyamazonCatalogDoctor.php`:
    -   **Responsabilità:** Analizza i dati del catalogo prodotti del negozio per potenziali problemi che potrebbero influire sulla corrispondenza dei prodotti Amazon (es. EAN mancanti, SKU errati). Fornisce feedback diagnostico per l'interfaccia admin.
-   `classes/MyamazonConsent.php`:
    -   **Responsabilità:** Gestisce l'integrazione del consenso ai cookie. Controlla lo stato del consenso del cliente e abilita/disabilita condizionalmente gli script di tracciamento lato client. Si integra con l'evento `prestashop.on('updateProduct', ...)` di PrestaShop per le modifiche del consenso.
-   `classes/MyamazonCurrencyHelper.php`:
    -   **Responsabilità:** Fornisce metodi di utilità per formattare correttamente i valori di valuta per Amazon Ads, gestendo decimali e codici di valuta.
-   `classes/MyamazonDataLayerTracker.php`:
    -   **Responsabilità:** Gestisce l'invio dei dati degli eventi a un oggetto JavaScript `dataLayer`, spesso utilizzato per la compatibilità con Google Tag Manager o altri consumatori di data layer.
-   `classes/MyamazonDataQualityCoach.php`:
    -   **Responsabilità:** Fornisce approfondimenti e raccomandazioni per migliorare la qualità complessiva dei dati inviati ad Amazon, coprendo aspetti che vanno oltre i soli ID prodotto.
-   `classes/MyamazonEventId.php`:
    -   **Responsabilità:** Genera ID evento univoci per ogni evento, cruciale per la deduplicazione quando si utilizza il tracciamento in modalità duale (assicurando che Amazon non conti lo stesso evento due volte da lato client e lato server).
-   `classes/MyamazonEventMap.php`:
    -   **Responsabilità:** Definisce la mappatura tra gli eventi interni di PrestaShop (es. `actionCartSave`) e i nomi degli eventi standard di Amazon Ads (es. `AddToCart`). Consente la personalizzazione di queste mappature.
-   `classes/MyamazonEvents.php`:
    -   **Responsabilità:** Una classe centrale o una raccolta di metodi per attivare e gestire vari eventi di Amazon Ads (es. `PageView`, `ViewContent`, `AddToCart`, `Purchase`).
-   `classes/MyamazonHealthScore.php`:
    -   **Responsabilità:** Calcola e presenta un "punteggio di salute" complessivo per il tracciamento del modulo, identificando problemi di configurazione, dati mancanti o potenziali lacune di tracciamento.
-   `classes/MyamazonHybridTracker.php`:
    -   **Responsabilità:** Orchestra il tracciamento in modalità duale, combinando `MyamazonAatTracker` e `MyamazonCapiTracker` per inviare eventi tramite metodi sia lato client che lato server, gestendo la deduplicazione.
-   `classes/MyamazonLiveStats.php`:
    -   **Responsabilità:** Raccoglie ed elabora dati di eventi in tempo reale o quasi in tempo reale per la visualizzazione nella vista "Statistiche in Tempo Reale" del back-office.
-   `classes/MyamazonProductIdResolver.php`:
    -   **Responsabilità:** Determina quale identificatore di prodotto (ID, EAN, UPC, SKU) deve essere utilizzato quando si inviano dati di prodotto ad Amazon, in base alla configurazione del modulo.
-   `classes/MyamazonPropertyRules.php`:
    -   **Responsabilità:** Definisce regole e convalide per le proprietà degli eventi, garantendo che i dati inviati ad Amazon aderiscano alle loro specifiche API.
-   `classes/MyamazonTrackerFactory.php`:
    -   **Responsabilità:** Una classe factory pattern responsabile dell'istanza del tracker corretto (`AatTracker`, `CapiTracker` o `HybridTracker`) in base alla configurazione del modulo.
-   `classes/MyamazonTrackerInterface.php`:
    -   **Responsabilità:** Definisce un'interfaccia comune per tutte le classi tracker (`AatTracker`, `CapiTracker`, `HybridTracker`), assicurando che implementino un set coerente di metodi per il tracciamento degli eventi.
-   `classes/MyamazonUserData.php`:
    -   **Responsabilità:** Raccoglie e formatta i dati relativi al cliente (es. email, telefono, indirizzo) per l'inclusione negli eventi di Amazon Ads, specialmente per l'API di Conversione dove le PII possono essere hashate e inviate.

### 4.4 Risorse JavaScript (`views/js/`)

-   `views/js/myamazon-admin.js`:
    -   **Ambito:** Back-office.
    -   **Dettagli:** Gestisce gli elementi interattivi nelle pagine di configurazione del modulo, come il cambio di scheda, le chiamate AJAX per le statistiche in tempo reale, la validazione dei moduli e gli aggiornamenti dinamici degli strumenti diagnostici.
-   `views/js/myamazon-debug.js`:
    -   **Ambito:** Front-office (caricato condizionalmente quando la modalità debug è attiva).
    -   **Dettagli:** Fornisce un logging verboso alla console del browser, mostrando gli eventi attivati, i payload dei dati e lo stato delle chiamate Amazon Ads Tag e CAPI. Può includere overlay visivi per un debug rapido.
-   `views/js/myamazon-ghost.js`:
    -   **Ambito:** Front-office.
    -   **Dettagli:** Probabilmente correlato a meccanismi di tracciamento "fantasma" o in background, potenzialmente per catturare eventi che altrimenti potrebbero essere persi o per specifiche dilazioni legate al consenso.
-   `views/js/myamazon-live.js`:
    -   **Ambito:** Back-office.
    -   **Dettagli:** Alimenta la dashboard "Statistiche in Tempo Reale", effettuando richieste AJAX a `AdminMyamazonAjaxController` per recuperare e visualizzare i dati degli eventi in tempo reale.
-   `views/js/myamazon-tcf.js`:
    -   **Ambito:** Front-office.
    -   **Dettagli:** Si integra con le soluzioni di consenso ai cookie conformi al Transparency and Consent Framework (TCF), garantendo che il tracciamento lato client aderisca alle preferenze di consenso dell'utente.
-   `views/js/myamazon-wizard.js`:
    -   **Ambito:** Back-office.
    -   **Dettagli:** Fornisce passaggi interattivi per la procedura guidata di configurazione iniziale, guidando il commerciante attraverso la configurazione essenziale.
-   `views/js/myamazon.js`:
    -   **Ambito:** Front-office.
    -   **Dettagli:** Il principale JavaScript lato client per il modulo. Inietta l'Amazon Ads Tag (script `aa.js`), ascolta vari eventi DOM (es. `click` sui pulsanti aggiungi al carrello), cattura dati dalla pagina, invia eventi al data layer e potenzialmente effettua chiamate AJAX a `MyamazonAjaxModuleFrontController` per l'elaborazione lato server. Gestisce anche la logica di deduplicazione degli eventi.

### 4.5 Fogli di Stile CSS (`views/css/`)

-   `myamazon/opis/sugestie/style1.css`, `myamazon/opis/sugestie/style2.css`, `myamazon/opis/sugestie/sugestie/style1.css`, `myamazon/opis/sugestie/sugestie/style2.css`, `myamazon/opis/sugestie/sugestie/tailwind-new-7.css`, `myamazon/opis/sugestie/tailwind-new-7.css`:
    -   **Ambito:** Back-office.
    -   **Dettagli:** Questi file sembrano essere correlati a un framework UI personalizzato o allo stile per suggerimenti/hint all'interno della configurazione del back-office, possibilmente per una configurazione guidata o un feedback diagnostico. `tailwind-new-7.css` suggerisce l'uso di Tailwind CSS per uno stile utility-first.
-   `views/css/myamazon-admin.css`:
    -   **Ambito:** Stile del modulo admin del back-office.
    -   **Dettagli:** Fornisce uno stile specifico per i moduli di configurazione del modulo, le schede, i pannelli diagnostici e altri elementi UI personalizzati all'interno del back office di PrestaShop.
-   `views/css/myamazon-debug.css`:
    -   **Ambito:** Front-office (caricato condizionalmente).
    -   **Dettagli:** Stili per l'overlay di debug o i messaggi della console, assicurando che siano leggibili e distinti quando la modalità debug è attiva.

### 4.6 Struttura del Template Smarty (`views/templates/`)

#### Template Hook (`views/templates/hook/`)

-   `views/templates/hook/capi-pageview.tpl`:
    -   **Hook:** `displayHeader` (o simile).
    -   **Output:** Inietta i dati dell'evento PageView lato server (CAPI), potenzialmente come input nascosto o variabile JavaScript, per essere raccolti dal controller `ajax.php` per l'invio lato server.
-   `views/templates/hook/debug.tpl`:
    -   **Hook:** `displayHeader` (condizionalmente).
    -   **Output:** Inietta lo script `myamazon-debug.js` e le eventuali variabili di debug iniziali necessarie quando la modalità debug è abilitata.
-   `views/templates/hook/displayOrderConfirmation.tpl`:
    -   **Hook:** `displayOrderConfirmation`.
    -   **Output:** Renderizza i dati critici dell'evento "Purchase", inclusi i dettagli dell'ordine, i prodotti e le informazioni del cliente, per la trasmissione sia lato client che lato server CAPI. Qui viene catturato il valore di conversione.
-   `views/templates/hook/ghost.tpl`:
    -   **Hook:** `displayHeader` (o simile).
    -   **Output:** Correlato al meccanismo di tracciamento "fantasma", potenzialmente per il caricamento differito o per una logica specifica legata al consenso.
-   `views/templates/hook/header.tpl`:
    -   **Hook:** `displayHeader`.
    -   **Output:** Il template principale per iniettare l'Amazon Ads Tag (script `aa.js`), `myamazon.js` e le variabili di configurazione iniziali nella sezione `<head>` di ogni pagina.
-   `views/templates/hook/payment.tpl`:
    -   **Hook:** `displayPaymentTop` (o simile).
    -   **Output:** Può essere utilizzato per tracciare eventi "InitiateCheckout" o altri eventi correlati al pagamento prima della conferma finale dell'ordine.
-   `views/templates/hook/product-details.tpl`:
    -   **Hook:** `displayProductButtons` o `displayProductExtraContent`.
    -   **Output:** Inietta JavaScript per tracciare gli eventi "ViewContent" quando viene caricata una pagina prodotto, catturando dati specifici del prodotto.

#### Template Admin (`views/templates/admin/`)

-   `views/templates/admin/consent-guide.tpl`: Visualizza le linee guida su come integrarsi con i moduli di consenso ai cookie.
-   `views/templates/admin/doctor.tpl`: Renderizza la vista diagnostica "Dottore Catalogo", mostrando i problemi dei dati del prodotto.
-   `views/templates/admin/dq.tpl`: Renderizza la vista "Coach Qualità Dati", fornendo approfondimenti sulla qualità dei dati.
-   `views/templates/admin/health.tpl`: Visualizza il "Punteggio di Salute" complessivo e le diagnostiche correlate.
-   `views/templates/admin/linker-domains.tpl`: Renderizza il campo di input per la configurazione dei domini di collegamento.
-   `views/templates/admin/live-maintain.tpl`: Possibilmente una vista di manutenzione per le statistiche in tempo reale.
-   `views/templates/admin/live.tpl`: Renderizza la dashboard "Statistiche in Tempo Reale".
-   `views/templates/admin/mode-context.tpl`, `views/templates/admin/mode-note-aat.tpl`, `views/templates/admin/mode-note-both.tpl`, `views/templates/admin/mode-note-capi.tpl`, `views/templates/admin/mode-note-datalayer.tpl`, `views/templates/admin/mode-picker.tpl`: Questi template sono utilizzati per la sezione "Selezione della Modalità di Tracciamento", fornendo spiegazioni e il pulsante radio/dropdown per la scelta del metodo di tracciamento.
-   `views/templates/admin/properties-list.tpl`: Visualizza un elenco di proprietà degli eventi e i loro valori, possibilmente per il debug o la configurazione.
-   `views/templates/admin/recent-events.tpl`: Renderizza una tabella o un elenco di eventi tracciati di recente, parte delle "Statistiche in Tempo Reale".
-   `views/templates/admin/tabs.tpl`: Renderizza la struttura di navigazione a schede per la configurazione del back-office del modulo.
-   `views/templates/admin/tag-chips.tpl`: Visualizza "chip" o etichette visive per tag/token configurati.
-   `views/templates/admin/tag-ids.tpl`: Renderizza i campi di input per l'ID Tag Amazon Ads e il Token di Accesso CAPI.
-   `views/templates/admin/wizard.tpl`: Renderizza l'interfaccia della procedura guidata di configurazione iniziale.

### 4.7 Schema del Database e Mappa degli Hook

#### Tabelle del Database

Il modulo memorizza principalmente la sua configurazione nella tabella `ps_configuration` di PrestaShop.

-   `ps_configuration`: Memorizza coppie chiave-valore per le impostazioni del modulo (es. `MYAMAZON_TAG_ID`, `MYAMAZON_CAPI_TOKEN`, `MYAMAZON_TRACKING_MODE`).
    Nessuna tabella SQL personalizzata è esplicitamente creata da questo modulo in base all'inventario fornito.

#### Tabella degli Hook Registrati

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Inietta lo script Amazon Ads Tag (`aa.js`), `myamazon.js` e le variabili di configurazione iniziali. Utilizzato anche per `capi-pageview.tpl` e `debug.tpl`. |
| `displayOrderConfirmation` | Nella pagina di conferma dell'ordine dopo un acquisto riuscito. | Cattura e invia i dati dell'evento "Purchase", inclusi i dettagli dell'ordine e i prodotti, ad Amazon tramite metodi sia lato client che lato server. |
| `actionCartSave` | Quando un prodotto viene aggiunto o rimosso dal carrello, o la quantità del carrello cambia. | Attiva gli eventi "AddToCart" o "RemoveFromCart". |
| `actionProductAdd` | Quando un nuovo prodotto viene aggiunto al catalogo. | Potenzialmente utilizzato da `MyamazonCatalogDoctor` per controlli di qualità dei dati. |
| `actionProductUpdate` | Quando un prodotto esistente viene aggiornato nel catalogo. | Potenzialmente utilizzato da `MyamazonCatalogDoctor` per controlli di qualità dei dati. |
| `actionFrontControllerSetMedia` | Prima che un controller frontale renderizzi il suo template, consentendo l'aggiunta di JS/CSS. | Inietta file JS/CSS specifici del modulo (`myamazon.js`, `myamazon-debug.js`, ecc.) nel front office. |
| `actionAdminControllerSetMedia` | Prima che un controller admin renderizzi il suo template. | Inietta file JS/CSS specifici del modulo (`myamazon-admin.js`, `myamazon-admin.css`, ecc.) nel back office. |
| `actionValidateOrder` | Dopo che un ordine è stato validato e salvato nel database con successo. | Cruciale per l'invio dell'evento "Purchase" lato server tramite CAPI, garantendo che i dati vengano inviati anche se il cliente chiude il browser prima di raggiungere la pagina di conferma. |
| `displayProductButtons` / `displayProductExtraContent` | Nella pagina del prodotto, vicino al pulsante aggiungi al carrello o alla descrizione del prodotto. | Inietta JavaScript per tracciare gli eventi "ViewContent". |
| `displayPaymentTop` | Nella parte superiore della pagina di selezione del pagamento durante il checkout. | Potenzialmente utilizzato per tracciare gli eventi "InitiateCheckout". |
| `displayFooter` | Nella sezione footer di ogni pagina. | Meno comune per il tracciamento principale, ma potrebbe essere utilizzato per il caricamento differito di script o popup di consenso specifici. |
| `actionObjectCustomerAddAfter` | Dopo la creazione di un nuovo account cliente. | Potenzialmente utilizzato per inviare eventi "SignUp" o "Lead" ad Amazon. |
| `actionObjectCustomerUpdateAfter` | Dopo l'aggiornamento dei dettagli di un cliente. | Potrebbe essere utilizzato per aggiornare i dati del cliente per CAPI. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, si prega di fare riferimento al proprio account cliente su MyPresta.eu.

-   **Aggiornamenti Modulo:** Accedi al tuo account su [MyPresta.eu Cronologia Ordini e Download](https://mypresta.eu/my-account/orders/) per scaricare le versioni più recenti del modulo "Amazon Ads Tag Conversions API".
-   **Supporto Tecnico:** Se riscontri problemi o hai domande relative alla funzionalità, configurazione o integrazione del modulo, ti preghiamo di aprire un ticket di supporto tramite il tuo account cliente MyPresta.eu. Il nostro team di esperti è pronto ad assisterti.
"""
