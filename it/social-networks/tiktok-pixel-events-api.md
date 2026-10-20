---
title: "TikTok Pixel / Events API - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop TikTok Pixel / Events API di MyPresta.eu."
sidebar:
  label: "TikTok Pixel / Events API - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo TikTok Pixel / Events API su MyPresta.eu](https://mypresta.eu/modules/social-networks/tiktok-pixel-events-api.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/tiktok-pixel-events-api/)
>
> ---


# TikTok Pixel / Events API

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono necessarie per il corretto funzionamento del modulo, specialmente per l'Events API (tracciamento lato server). Queste sono tipicamente disponibili sulla maggior parte degli ambienti di hosting moderni.

## 2. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)

Questa è l'area di configurazione principale dove imposterai il tuo TikTok Pixel e l'Events API. Le impostazioni sono progettate per essere intuitive, guidandoti attraverso il processo di connessione del tuo negozio a TikTok Ads.

#### **Impostazioni Generali**

- **ID Pixel TikTok:**

  - **Cosa fa questa impostazione:** Questo è il tuo identificatore unico fornito da TikTok Ads Manager. Indica a TikTok a quale account pubblicitario appartengono i dati del tuo sito web.
  - **Effetto della modifica di questa impostazione:**
    - *Quando inserito:* Il modulo inizierà a inviare dati al tuo TikTok Pixel specificato.
    - *Quando lasciato vuoto:* Nessun dato verrà inviato a TikTok tramite il Pixel, e il modulo non funzionerà per il tracciamento lato browser.
  - **Valore consigliato:** Il tuo ID Pixel TikTok valido.
  - **Scenario / esempio del commerciante:** Crei un account TikTok Ad e imposti un Pixel. TikTok ti fornisce un ID numerico (es. `1234567890`). Inserisci questo ID qui per collegare il tuo negozio al tuo account TikTok.
- **Token di Accesso TikTok (per Events API):**

  - **Cosa fa questa impostazione:** Questo è un token sicuro generato nel tuo TikTok Ads Manager che autorizza il tuo negozio PrestaShop a inviare dati direttamente ai server di TikTok tramite l'Events API. È cruciale per il tracciamento lato server.
  - **Effetto della modifica di questa impostazione:**
    - *Quando inserito:* Abilita il tracciamento lato server (Events API), che è più affidabile e meno influenzato dagli ad blocker.
    - *Quando lasciato vuoto:* Il tracciamento lato server sarà disabilitato.
  - **Valore consigliato:** Il tuo Token di Accesso TikTok Events API valido.
  - **Scenario / esempio del commerciante:** Per migliorare l'accuratezza dei dati e bypassare le limitazioni del browser, decidi di utilizzare l'Events API. Generi un Token di Accesso in TikTok Ads Manager e lo incolli qui.
- **Modalità di Tracciamento:**

  - **Cosa fa questa impostazione:** Determina come i dati vengono inviati a TikTok. Puoi scegliere tra Pixel (lato browser), Events API (lato server) o Modalità Duale (entrambi).
  - **Effetto della modifica di questa impostazione:**
    - *Solo Pixel:* Solo il tracciamento lato browser è attivo.
    - *Solo Events API:* Solo il tracciamento lato server è attivo.
    - *Modalità Duale (Consigliata):* Sia Pixel che Events API sono attivi. Il modulo utilizza in modo intelligente un `event_id` condiviso per deduplicare gli eventi in TikTok, garantendo l'accuratezza.
  - **Valore consigliato:** `Modalità Duale` per la massima accuratezza dei dati e resilienza contro gli ad blocker.
  - **Scenario / esempio del commerciante:** Desideri il tracciamento più affidabile possibile. Selezioni "Modalità Duale" in modo che se un cliente utilizza un ad blocker, l'Events API lato server possa comunque catturare la conversione, e TikTok non la conterà due volte se entrambi i metodi hanno successo.
- **Abilita Modalità Debug:**

  - **Cosa fa questa impostazione:** Attiva una modalità speciale che visualizza informazioni dettagliate sugli eventi TikTok inviati, direttamente nella console per sviluppatori del tuo browser. Questo è inestimabile per la risoluzione dei problemi.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Sviluppatori e utenti avanzati possono vedere esattamente quali dati vengono inviati a TikTok in tempo reale, aiutando a verificare la corretta configurazione.
    - *Quando disabilitato:* Nessuna informazione di debug viene visualizzata.
  - **Valore consigliato:** `No` per i negozi in produzione. Abilitare temporaneamente solo per test e debug.
  - **Scenario / esempio del commerciante:** Hai appena installato il modulo e vuoi assicurarti che gli eventi `AddToCart` vengano attivati correttamente. Abiliti la modalità debug, aggiungi un articolo al carrello e controlli la console del tuo browser per i dati dell'evento TikTok.

#### **Impostazioni Avanzate**

- **Gestione del Consenso (GDPR/CCPA):**

  - **Cosa fa questa impostazione:** Si integra con la soluzione di consenso ai cookie del tuo negozio (se disponibile) per garantire che il tracciamento TikTok si attivi solo dopo che un cliente ha dato il proprio consenso.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il TikTok Pixel/Events API si caricherà e invierà dati solo se il cliente ha accettato i cookie.
    - *Quando disabilitato:* Il tracciamento avverrà indipendentemente dal consenso ai cookie, il che potrebbe non essere conforme alle normative sulla privacy come GDPR o CCPA.
  - **Valore consigliato:** `Sì` se il tuo negozio opera in regioni con leggi sulla privacy severe (es. UE, California).
  - **Scenario / esempio del commerciante:** Il tuo negozio serve clienti nell'Unione Europea. Per conformarti al GDPR, abiliti questa impostazione, assicurando che il tracciamento TikTok rispetti le scelte di privacy dell'utente.
- **Tipo di ID Prodotto:**

  - **Cosa fa questa impostazione:** Determina quale identificatore di prodotto (ID) viene inviato a TikTok. Le opzioni includono tipicamente l'ID prodotto interno di PrestaShop, EAN13, UPC o un riferimento personalizzato. Questo è cruciale per abbinare i prodotti nel tuo Catalogo Prodotti TikTok.
  - **Effetto della modifica di questa impostazione:**
    - *Modifica del tipo:* Assicura che gli ID prodotto inviati a TikTok corrispondano agli ID utilizzati nel tuo Catalogo Prodotti TikTok, abilitando annunci di prodotti dinamici.
  - **Valore consigliato:** Scegli il tipo di ID che utilizzi nel tuo Catalogo Prodotti TikTok. Spesso, l'`ID Prodotto` di PrestaShop o `EAN13` sono scelte comuni.
  - **Scenario / esempio del commerciante:** Hai caricato un catalogo prodotti su TikTok utilizzando i codici EAN13 dei tuoi prodotti. Selezioni `EAN13` qui per assicurarti che TikTok possa identificare correttamente quali prodotti i clienti stanno visualizzando o acquistando.
- **Domini Linker (per il tracciamento cross-domain):**

  - **Cosa fa questa impostazione:** Ti consente di specificare nomi di dominio aggiuntivi se il percorso del tuo cliente coinvolge più domini (es. un negozio principale e un blog separato su un dominio diverso). Questo aiuta TikTok a tracciare gli utenti senza interruzioni tra questi domini.
  - **Effetto della modifica di questa impostazione:**
    - *Quando vengono aggiunti domini:* TikTok può mantenere la coerenza del tracciamento degli utenti tra i domini elencati.
    - *Quando lasciato vuoto:* Il tracciamento potrebbe interrompersi se i clienti navigano tra diversi domini che fanno parte della tua attività.
  - **Valore consigliato:** Aggiungi eventuali sottodomini o domini collegati pertinenti che i tuoi clienti potrebbero visitare.
  - **Scenario / esempio del commerciante:** Il tuo negozio principale è `ilmionegozio.com`, ma hai un blog su `blog.ilmionegozio.com` dove colleghi ai prodotti. L'aggiunta di `blog.ilmionegozio.com` qui assicura che TikTok possa tracciare gli utenti dal blog al tuo negozio.

#### **Qualità dei Dati e Punteggio di Salute**

Questa sezione fornisce approfondimenti sulle prestazioni e l'accuratezza del tuo tracciamento TikTok.

- **Punteggio di Salute:**

  - **Cosa fa:** Visualizza un punteggio che indica la salute generale e l'accuratezza della tua trasmissione di dati a TikTok. Un punteggio più alto significa una migliore qualità dei dati.
  - **Effetto:** Ti aiuta a identificare rapidamente se ci sono problemi con la configurazione del tuo tracciamento che potrebbero influire sulle prestazioni degli annunci.
  - **Consigliato:** Punta a un punteggio elevato. Il modulo fornirà raccomandazioni se il punteggio è basso.
- **Recovery Radar:**

  - **Cosa fa:** Monitora i carrelli abbandonati e fornisce approfondimenti sulle potenziali vendite perse, aiutandoti a identificare opportunità per campagne di retargeting.
  - **Effetto:** Ti offre una rapida panoramica di quanti carrelli vengono avviati rispetto a quelli completati, evidenziando le aree di miglioramento nel tuo processo di checkout o nella strategia di retargeting.
- **Statistiche in Tempo Reale:**

  - **Cosa fa:** Mostra dati in tempo reale sugli eventi inviati a TikTok, permettendoti di vedere se gli eventi vengono attivati come previsto.
  - **Effetto:** Fornisce un feedback immediato durante i test e il monitoraggio continuo, confermando che il tuo tracciamento è attivo e accurato.

### 2.2 Schermate di Amministrazione Dedicate e Viste Controller

Il modulo estende il Back Office di PrestaShop con diverse schermate dedicate per aiutarti a gestire e monitorare la tua integrazione TikTok. Queste sono tipicamente accessibili dalla pagina di configurazione del modulo tramite schede o voci di menu dedicate.

#### **AdminMytiktokAjaxController (Operazioni Ajax)**

- **Nome schermata e Posizione menu:** Questo controller gestisce principalmente le richieste AJAX in background dalla pagina di configurazione del modulo. Non navigherai direttamente a una "schermata" per questo, ma alimenta gli aggiornamenti dinamici e il recupero dei dati all'interno delle schede di configurazione principali del modulo (es. Statistiche in Tempo Reale, Punteggio di Salute, Log Eventi).
- **Azioni e Impostazioni Disponibili:** Elabora le richieste per:
  - Recupero dei dati degli eventi in tempo reale.
  - Aggiornamento dei punteggi di salute.
  - Recupero delle informazioni diagnostiche.
  - Salvataggio di parti specifiche della configurazione senza un ricaricamento completo della pagina.
- **Effetto delle modifiche:** Le interazioni sulla pagina di configurazione principale del modulo (come l'aggiornamento delle statistiche in tempo reale o l'esecuzione di diagnostica) attivano questo controller per recuperare e visualizzare i dati pertinenti.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Interagisci con questo indirettamente utilizzando i vari strumenti diagnostici e di monitoraggio forniti nella pagina di configurazione principale del modulo.

#### **index.php (Punto di Ingresso Principale del Modulo)**

- **Nome schermata e Posizione menu:** Questo è il punto di ingresso principale per la configurazione del modulo, accessibile tramite **Back Office > Moduli > Gestione moduli > Configura (per TikTok Pixel / Events API)**.
- **Azioni e Impostazioni Disponibili:** Questa schermata presenta tutte le impostazioni generali e avanzate descritte nella sezione 4.1, organizzate in schede o sezioni logiche. Ospita anche i vari strumenti diagnostici come Punteggio di Salute, Statistiche in Tempo Reale e Recovery Radar.
- **Effetto delle modifiche:** Qualsiasi modifica salvata su questa schermata influisce direttamente sul funzionamento del tuo TikTok Pixel e dell'Events API sul tuo storefront.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1. **Configurazione Iniziale:** Configura il tuo ID Pixel, il Token di Accesso e la Modalità di Tracciamento.
  2. **Monitoraggio Regolare:** Controlla periodicamente le schede "Punteggio di Salute" e "Statistiche in Tempo Reale" per garantire la qualità dei dati e l'attivazione degli eventi.
  3. **Risoluzione dei Problemi:** Utilizza la "Modalità Debug" (temporaneamente) e le "Statistiche in Tempo Reale" per diagnosticare eventuali problemi di tracciamento.
  4. **Ottimizzazione:** Rivedi gli approfondimenti del "Recovery Radar" per informare le tue strategie di retargeting.

### 2.3 Tabella di Riferimento Rapido della Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | ID Pixel TikTok | Il tuo ID Pixel | Collega il tuo negozio al tuo account TikTok Ad per il tracciamento del browser. |
| Configurazione Modulo | Token di Accesso TikTok | Il tuo Token di Accesso | Autorizza il tracciamento lato server tramite Events API. |
| Configurazione Modulo | Modalità di Tracciamento | Modalità Duale | Determina se Pixel, Events API o entrambi vengono utilizzati per il tracciamento. La modalità duale è consigliata per l'accuratezza. |
| Configurazione Modulo | Abilita Modalità Debug | No (per la produzione) | Mostra dati dettagliati degli eventi nella console del browser per la risoluzione dei problemi. |
| Configurazione Modulo | Gestione del Consenso | Sì (per GDPR/CCPA) | Assicura che il tracciamento rispetti il consenso ai cookie dell'utente. |
| Configurazione Modulo | Tipo di ID Prodotto | Corrispondente al tuo Catalogo | Seleziona l'identificatore di prodotto inviato a TikTok per la corrispondenza del catalogo. |
| Configurazione Modulo | Domini Linker | Vuoto (aggiungi se necessario) | Consente il tracciamento cross-domain per strutture di siti complesse. |
| Configurazione Modulo | Punteggio di Salute | Punteggio elevato | Indica la qualità complessiva dei dati e l'accuratezza del tracciamento. |
| Configurazione Modulo | Recovery Radar | Monitora | Approfondimenti sui carrelli abbandonati per il retargeting. |
| Configurazione Modulo | Statistiche in Tempo Reale | Monitora | Vista in tempo reale degli eventi inviati a TikTok. |

## 3. Risoluzione dei Problemi del Commerciante e Domande Frequenti (FAQ)

**D1: Ho installato il modulo, ma non vedo alcun dato nel mio TikTok Ads Manager. Cosa devo fare?**

- **R:** Innanzitutto, ricontrolla che il tuo **ID Pixel TikTok** e il **Token di Accesso** siano stati inseriti correttamente nella configurazione del modulo. Assicurati che non ci siano errori di battitura.
- Successivamente, verifica che la tua **Modalità di Tracciamento** sia impostata su "Modalità Duale" o "Pixel" (se stai utilizzando solo il Pixel).
- Abilita la **Modalità Debug** nelle impostazioni del modulo, quindi visita il front office del tuo negozio, esegui alcune azioni (come visualizzare un prodotto, aggiungerlo al carrello) e controlla la console per sviluppatori del tuo browser (solitamente F12 > scheda Console) per i messaggi degli eventi TikTok.
- Infine, svuota la cache di PrestaShop (**Parametri Avanzati > Prestazioni > Svuota cache**).

**D2: Il mio Punteggio di Salute TikTok è basso. Come posso migliorarlo?**

- **R:** Un Punteggio di Salute basso spesso indica problemi con la qualità dei dati o la consegna degli eventi.
- **Verifica la presenza di dati mancanti:** Assicurati che tutte le informazioni richieste sui prodotti (prezzo, valuta, nome) siano complete per i tuoi prodotti.
- **Verifica il consenso:** Se hai abilitato la "Gestione del Consenso", assicurati che il tuo banner di consenso ai cookie funzioni correttamente e che gli utenti accettino i cookie.
- **Rivedi le Statistiche in Tempo Reale:** Cerca eventuali errori o eventi mancanti nella sezione "Statistiche in Tempo Reale" del modulo.
- Il modulo stesso spesso fornisce raccomandazioni specifiche all'interno della sezione Punteggio di Salute per guidarti.

**D3: Questo modulo rallenterà il mio sito web?**

- **R:** Il modulo è progettato per essere leggero ed efficiente. Il tracciamento Pixel lato browser potrebbe aggiungere un piccolo, trascurabile carico, simile a qualsiasi altro script di analisi. L'Events API lato server non ha praticamente alcun impatto sui tempi di caricamento del front office poiché i dati vengono inviati direttamente dal tuo server. Si consiglia di utilizzare la "Modalità Duale" per prestazioni ottimali e accuratezza dei dati.

**D4: Ho un tema personalizzato. Il modulo funzionerà correttamente?**

- **R:** Sì, il modulo è progettato per integrarsi perfettamente con i temi standard di PrestaShop e la maggior parte dei temi personalizzati. Utilizza il sistema di hook ufficiale di PrestaShop per iniettare i suoi script e il codice di tracciamento.
- Se riscontri problemi con un tema altamente personalizzato, specialmente se altera in modo significativo i template core di PrestaShop per le pagine dei prodotti o il checkout, potresti dover consultare uno sviluppatore per assicurarti che gli hook siano ancora presenti e renderizzati correttamente.

**D5: Come gestisce il modulo i negozi multi-lingua e multi-valuta?**

- **R:** Il modulo è costruito per essere completamente compatibile con le funzionalità multi-lingua e multi-valuta di PrestaShop. Rileva automaticamente la lingua e la valuta attive sul front office e invia queste informazioni a TikTok, garantendo che i dati degli eventi siano accurati e localizzati. I nomi e i valori dei prodotti verranno inviati nel contesto della lingua e della valuta selezionate dal cliente.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

Questa sezione fornisce un'analisi approfondita della struttura tecnica del modulo TikTok Pixel / Events API, destinata a sviluppatori, webmaster e agenzie tecniche.

### 4.1 Panoramica dell'Architettura

Il modulo `mytiktok` segue un'architettura standard dei moduli PrestaShop, sfruttando il pattern MVC dove appropriato. Funziona principalmente come tracker di eventi, iniettando JavaScript per il tracciamento lato client (Pixel) e utilizzando la logica lato server per l'Events API. I componenti chiave includono:

- **Classe Principale del Modulo (`index.php`):** Gestisce installazione, disinstallazione, configurazione e registrazione degli hook.
- **Controller:** Controller frontali per richieste AJAX e controller admin per la gestione del back-office.
- **Classi Core:** Un robusto set di classi (`classes/`) per la gestione della comunicazione API, la mappatura degli eventi, la qualità dei dati, il consenso e varie strategie di tracciamento (Pixel, CAPI, Hybrid).
- **Template:** Template Smarty sia per l'iniezione di hook nel front-office che per le viste di configurazione del back-office.
- **Assets:** JS e CSS dedicati per le interfacce di amministrazione e il debug/tracciamento del front-office.

Il modulo implementa un `MytiktokTrackerInterface` e utilizza un `MytiktokTrackerFactory` per astrarre diverse modalità di tracciamento (Pixel, CAPI, Hybrid), promuovendo un design pulito ed estensibile. Include anche sofisticati strumenti di monitoraggio della qualità dei dati e della salute.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

- `mytiktok/controllers/front/ajax.php`
  - **Nome classe e classe genitore:** `MytiktokAjaxModuleFrontController` estende `ModuleFrontController`.
  - **Responsabilità:** Gestisce le richieste asincrone dal front-office, principalmente per il tracciamento degli eventi lato server (Events API) o la raccolta di dati che non richiedono un ricaricamento completo della pagina. Potrebbe elaborare i dati inviati da JavaScript e inoltrarli all'Events API di TikTok.
- `mytiktok/controllers/front/index.php`
  - **Nome classe e classe genitore:** `MytiktokIndexModuleFrontController` estende `ModuleFrontController`.
  - **Responsabilità:** Questo controller potrebbe servire come fallback o come endpoint specifico per determinate interazioni del front-office, sebbene `ajax.php` sia tipicamente più attivo per la gestione degli eventi. Potrebbe essere utilizzato per reindirizzamenti specifici o inizializzazioni se necessario.

#### Controller Admin Back-Office

- `mytiktok/controllers/admin/AdminMytiktokAjaxController.php`
  - **Nome classe e classe genitore:** `AdminMytiktokAjaxController` estende `ModuleAdminController`.
  - **Nome scheda ed entità gestita:** Questo controller non è direttamente accessibile come scheda di menu. Gestisce le richieste AJAX originate dalla pagina di configurazione principale del modulo (`index.php`) nel back office. È responsabile degli aggiornamenti dinamici, del recupero delle statistiche in tempo reale, dei punteggi di salute, dei log degli eventi e di altri dati diagnostici senza richiedere un aggiornamento completo della pagina.
- `mytiktok/controllers/admin/index.php`
  - **Nome classe e classe genitore:** `AdminMytiktokController` estende `ModuleAdminController`.
  - **Nome scheda ed entità gestita:** Questo è il controller admin principale per la configurazione del modulo. È il controller a cui `index.php` (il file principale del modulo) invia quando si clicca sul pulsante "Configura". Gestisce la visualizzazione di tutti i moduli di configurazione, le schede (es. Impostazioni Generali, Qualità dei Dati, Statistiche in Tempo Reale) e gestisce il salvataggio delle impostazioni del modulo.

### 4.3 Classi Core e Modelli (`classes/`)

- `mytiktok/classes/autoload.php`: File di autoload standard di PrestaShop, che assicura il corretto caricamento delle classi del modulo.
- `mytiktok/classes/index.php`: File vuoto, spesso utilizzato per prevenire l'elenco delle directory.
- `mytiktok/classes/MytiktokCapiClient.php`:
  - **Tabella database:** Nessuna direttamente.
  - **Estende ObjectModel:** No.
  - **Metodi pubblici chiave:** Gestisce la comunicazione con l'Events API di TikTok (CAPI). Contiene metodi per l'invio di dati di eventi, la gestione dell'autenticazione con il Token di Accesso e la gestione delle risposte API.
- `mytiktok/classes/MytiktokCapiTracker.php`:
  - **Tabella database:** Nessuna direttamente.
  - **Estende ObjectModel:** No.
  - **Metodi pubblici chiave:** Implementa `MytiktokTrackerInterface`. Responsabile della preparazione e dell'invio di eventi lato server a TikTok tramite `MytiktokCapiClient`.
- `mytiktok/classes/MytiktokCatalogDoctor.php`:
  - **Tabella database:** Nessuna direttamente.
  - **Estende ObjectModel:** No.
  - **Metodi pubblici chiave:** Fornisce strumenti diagnostici e raccomandazioni relative ai dati del catalogo prodotti, garantendo che gli ID prodotto e gli attributi siano formattati correttamente per TikTok.
- `mytiktok/classes/MytiktokConsent.php`:
  - **Tabella database:** Nessuna direttamente.
  - **Estende ObjectModel:** No.
  - **Metodi pubblici chiave:** Gestisce la logica del consenso ai cookie, integrandosi con i meccanismi di consenso di PrestaShop o moduli di consenso personalizzati per garantire la conformità GDPR/CCPA.
- `mytiktok/classes/MytiktokCurrencyHelper.php`:
  - **Tabella database:** Nessuna direttamente.
  - **Estende ObjectModel:** No.
  - **Metodi pubblici chiave:** Classe utility per la gestione della formattazione e delle conversioni di valuta, garantendo che i valori degli eventi vengano inviati a TikTok nel formato e nella valuta corretti.
- `mytiktok/classes/MytiktokDataQualityCoach.php`:
  - **Tabella database:** Nessuna direttamente.
  - **Estende ObjectModel:** No.
  - **Metodi pubblici chiave:** Analizza la qualità e la completezza dei dati inviati a TikTok, fornendo approfondimenti e suggerimenti per il miglioramento.
- `mytiktok/classes/MytiktokEventId.php`:
  - **Tabella database:** Nessuna direttamente.
  - **Estende ObjectModel:** No.
  - **Metodi pubblici chiave:** Genera e gestisce valori `event_id` unici per gli eventi, cruciali per la deduplicazione nel tracciamento in modalità duale.
- `mytiktok/classes/MytiktokEventMap.php`:
  - **Tabella database:** Nessuna direttamente.
  - **Estende ObjectModel:** No.
  - **Metodi pubblici chiave:** Mappa le azioni e i dati di PrestaShop ai nomi e alle proprietà degli eventi standard di TikTok (es. `ViewContent`, `AddToCart`, `CompletePayment`).
- `mytiktok/classes/MytiktokEvents.php`:
  - **Tabella database:** Nessuna direttamente.
  - **Estende ObjectModel:** No.
  - **Metodi pubblici chiave:** Classe centrale per l'attivazione e la gestione di vari eventi TikTok basati sulle azioni dell'utente in PrestaShop.
- `mytiktok/classes/MytiktokHealthScore.php`:
  - **Tabella database:** Nessuna direttamente.
  - **Estende ObjectModel:** No.
  - **Metodi pubblici chiave:** Calcola e visualizza il punteggio di salute complessivo dell'integrazione TikTok basato sulla qualità dei dati, la consegna degli eventi e la configurazione.
- `mytiktok/classes/MytiktokHybridTracker.php`:
  - **Tabella database:** Nessuna direttamente.
  - **Estende ObjectModel:** No.
  - **Metodi pubblici chiave:** Implementa `MytiktokTrackerInterface`. Orchestra il tracciamento in modalità duale, inviando eventi tramite Pixel e CAPI con deduplicazione dell'`event_id`.
- `mytiktok/classes/MytiktokLiveStats.php`:
  - **Tabella database:** Nessuna direttamente.
  - **Estende ObjectModel:** No.
  - **Metodi pubblici chiave:** Raccoglie e visualizza statistiche in tempo reale degli eventi inviati a TikTok per scopi di monitoraggio.
- `mytiktok/classes/MytiktokPixelTracker.php`:
  - **Tabella database:** Nessuna direttamente.
  - **Estende ObjectModel:** No.
  - **Metodi pubblici chiave:** Implementa `MytiktokTrackerInterface`. Responsabile dell'iniezione e della gestione degli eventi TikTok Pixel lato browser.
- `mytiktok/classes/MytiktokProductIdResolver.php`:
  - **Tabella database:** Nessuna direttamente.
  - **Estende ObjectModel:** No.
  - **Metodi pubblici chiave:** Risolve l'ID prodotto corretto in base alla configurazione del modulo (es. ID PrestaShop, EAN13, UPC) per l'invio a TikTok.
- `mytiktok/classes/MytiktokPropertyRules.php`:
  - **Tabella database:** Nessuna direttamente.
  - **Estende ObjectModel:** No.
  - **Metodi pubblici chiave:** Definisce e applica regole per le proprietà degli eventi, garantendo che i dati inviati a TikTok aderiscano alle sue specifiche.
- `mytiktok/classes/MytiktokTrackerFactory.php`:
  - **Tabella database:** Nessuna direttamente.
  - **Estende ObjectModel:** No.
  - **Metodi pubblici chiave:** Pattern factory per istanziare la classe tracker corretta (`MytiktokPixelTracker`, `MytiktokCapiTracker` o `MytiktokHybridTracker`) in base alla configurazione della "Modalità di Tracciamento" del modulo.
- `mytiktok/classes/MytiktokTrackerInterface.php`:
  - **Tabella database:** Nessuna direttamente.
  - **Estende ObjectModel:** No.
  - **Metodi pubblici chiave:** Definisce il contratto per tutte le classi tracker, garantendo un'interfaccia coerente per l'invio degli eventi.
- `mytiktok/classes/MytiktokTrans.php`:
  - **Tabella database:** Nessuna direttamente.
  - **Estende ObjectModel:** No.
  - **Metodi pubblici chiave:** Classe utility per la gestione delle traduzioni del modulo.
- `mytiktok/classes/MytiktokUserData.php`:
  - **Tabella database:** Nessuna direttamente.
  - **Estende ObjectModel:** No.
  - **Metodi pubblici chiave:** Raccoglie e formatta i dati utente (es. email, telefono, indirizzo IP) per una corrispondenza migliorata nell'Events API di TikTok.

### 4.4 Assets JavaScript (`views/js/`)

- `mytiktok/views/js/mytiktok-admin.js`:
  - **Ambito:** Back-office.
  - **Descrizione:** Gestisce gli elementi interattivi e le chiamate AJAX all'interno delle pagine di amministrazione del modulo. Questo include la gestione delle schede, l'aggiornamento delle statistiche in tempo reale, la gestione dell'invio dei moduli e i passaggi della procedura guidata.
- `mytiktok/views/js/mytiktok-debug.js`:
  - **Ambito:** Front-office (quando la modalità debug è abilitata).
  - **Descrizione:** Inietta informazioni di debug nella console del browser, registrando gli eventi TikTok, le loro proprietà e potenziali problemi. Essenziale per verificare la corretta attivazione degli eventi.
- `mytiktok/views/js/mytiktok-ghost.js`:
  - **Ambito:** Front-office.
  - **Descrizione:** Potrebbe gestire meccanismi di tracciamento "fantasma" o nascosti, possibilmente correlati all'avvio di eventi lato server o a specifiche interazioni utente che devono essere catturate senza interazione diretta con il pixel.
- `mytiktok/views/js/mytiktok-live.js`:
  - **Ambito:** Back-office.
  - **Descrizione:** Alimenta la funzionalità "Statistiche in Tempo Reale" nel pannello di amministrazione, recuperando e visualizzando periodicamente i dati degli eventi in tempo reale.
- `mytiktok/views/js/mytiktok-tcf.js`:
  - **Ambito:** Front-office.
  - **Descrizione:** Si integra con il Transparency and Consent Framework (TCF) o altre soluzioni di consenso ai cookie per gestire il consenso dell'utente prima di inizializzare il TikTok Pixel.
- `mytiktok/views/js/mytiktok-wizard.js`:
  - **Ambito:** Back-office.
  - **Descrizione:** Gestisce la procedura guidata di configurazione passo-passo per la configurazione iniziale del modulo, guidando il commerciante attraverso le impostazioni essenziali.
- `mytiktok/views/js/mytiktok.js`:
  - **Ambito:** Front-office.
  - **Descrizione:** Il file JavaScript principale del front-office. Inizializza il TikTok Pixel, attiva eventi standard (PageView, ViewContent, AddToCart, InitiateCheckout) e raccoglie i dati necessari dal DOM da inviare a TikTok. Gestisce anche la generazione dell'`event_id` per la deduplicazione.

### 4.5 Fogli di Stile CSS (`views/css/`)

- `mytiktok/views/css/mytiktok-admin.css`:
  - **Ambito:** Styling del modulo di amministrazione del back-office.
  - **Descrizione:** Stila la pagina di configurazione del modulo, incluse schede, campi di input, pulsanti e visualizzazioni diagnostiche (Punteggio di Salute, Statistiche in Tempo Reale, ecc.) per garantire un'interfaccia coerente e user-friendly all'interno del back office di PrestaShop.
- `mytiktok/views/css/mytiktok-debug.css`:
  - **Ambito:** Styling del cliente del front-office (solo quando la modalità debug è attiva).
  - **Descrizione:** Fornisce uno styling minimo per eventuali elementi di debug visivi che potrebbero apparire sul front office quando la modalità debug è abilitata (es. una piccola sovrapposizione o banner che indica lo stato di debug).

### 4.6 Struttura dei Template Smarty (`views/templates/`)

#### Template Hook (`views/templates/hook/`)

- `mytiktok/views/templates/hook/capi-pageview.tpl`:
  - **Hook:** Potenzialmente `displayHeader` o `displayBeforeBodyClosingTag`.
  - **Output:** Renderizza l'evento `PageView` lato server per l'Events API. Questo template potrebbe contenere campi nascosti o strutture di dati utilizzate dalla logica lato server per avviare l'evento CAPI PageView.
- `mytiktok/views/templates/hook/debug.tpl`:
  - **Hook:** `displayHeader` o `displayBeforeBodyClosingTag`.
  - **Output:** Renderizza un piccolo blocco HTML o tag script per scopi di debug, spesso includendo `mytiktok-debug.js` e dati di debug iniziali.
- `mytiktok/views/templates/hook/displayOrderConfirmation.tpl`:
  - **Hook:** `displayOrderConfirmation`.
  - **Output:** Renderizza i dati dell'evento `CompletePayment`, inclusi valore dell'ordine, valuta e dettagli del prodotto, da inviare a TikTok Pixel e/o Events API dopo un acquisto riuscito.
- `mytiktok/views/templates/hook/ghost.tpl`:
  - **Hook:** Vari hook del front-office.
  - **Output:** Renderizza elementi o script nascosti per il tracciamento "fantasma", potenzialmente correlati a trigger di eventi lato server o raccolta avanzata di dati.
- `mytiktok/views/templates/hook/header.tpl`:
  - **Hook:** `displayHeader`.
  - **Output:** Inietta il codice base principale del TikTok Pixel, `mytiktok.js`, e le variabili di configurazione iniziali nella sezione `<head>` di tutte le pagine del front-office. Qui viene inizializzato il Pixel.
- `mytiktok/views/templates/hook/payment.tpl`:
  - **Hook:** Potenzialmente `displayPaymentTop` o `displayPaymentOptions`.
  - **Output:** Potrebbe renderizzare i dati dell'evento `InitiateCheckout` o script correlati quando un cliente raggiunge il passaggio di selezione del pagamento durante il checkout.
- `mytiktok/views/templates/hook/product-details.tpl`:
  - **Hook:** `displayProductAdditionalInfo` o hook simile della pagina prodotto.
  - **Output:** Renderizza i dati dell'evento `ViewContent`, inclusi ID prodotto, nome, prezzo e categoria, per il prodotto attualmente visualizzato.

#### Template Admin (`views/templates/admin/`)

- `mytiktok/views/templates/admin/consent-guide.tpl`: Visualizza la guida alla configurazione del consenso ai cookie.
- `mytiktok/views/templates/admin/doctor.tpl`: Renderizza l'interfaccia diagnostica del "Catalog Doctor".
- `mytiktok/views/templates/admin/dq.tpl`: Visualizza approfondimenti e raccomandazioni sulla qualità dei dati.
- `mytiktok/views/templates/admin/health.tpl`: Renderizza la dashboard del "Punteggio di Salute".
- `mytiktok/views/templates/admin/linker-domains.tpl`: Campo modulo per la configurazione dei domini linker.
- `mytiktok/views/templates/admin/live-maintain.tpl`: Segnaposto o vista di manutenzione per le statistiche in tempo reale.
- `mytiktok/views/templates/admin/live.tpl`: Visualizza la dashboard delle "Statistiche in Tempo Reale".
- `mytiktok/views/templates/admin/mode-context.tpl`: Informazioni contestuali sulla modalità di tracciamento selezionata.
- `mytiktok/views/templates/admin/mode-note-both.tpl`: Nota/spiegazione per il tracciamento in "Modalità Duale".
- `mytiktok/views/templates/admin/mode-note-capi.tpl`: Nota/spiegazione per il tracciamento "Solo Events API".
- `mytiktok/views/templates/admin/mode-note-pixel.tpl`: Nota/spiegazione per il tracciamento "Solo Pixel".
- `mytiktok/views/templates/admin/mode-picker.tpl`: L'interfaccia per la selezione della modalità di tracciamento (Pixel, CAPI, Dual).
- `mytiktok/views/templates/admin/properties-list.tpl`: Visualizza un elenco di proprietà degli eventi.
- `mytiktok/views/templates/admin/recent-events.tpl`: Mostra un log degli eventi recenti inviati.
- `mytiktok/views/templates/admin/tabs.tpl`: Struttura per l'interfaccia a schede nella pagina di configurazione del modulo.
- `mytiktok/views/templates/admin/tag-chips.tpl`: Componenti visivi per la visualizzazione di tag o ID.
- `mytiktok/views/templates/admin/tag-ids.tpl`: Campi di input per l'ID Pixel TikTok e il Token di Accesso.
- `mytiktok/views/templates/admin/wizard.tpl`: L'interfaccia della procedura guidata di configurazione passo-passo.

#### Template Front-office (`views/templates/front/`)

- Non sono elencati template di pagina standalone dedicati, poiché il modulo inietta principalmente script e dati tramite hook.

### 4.7 Schema del Database e Mappa degli Hook

#### Tabelle del Database

Il modulo memorizza principalmente le sue impostazioni di configurazione nella tabella `ps_configuration` di PrestaShop.

- `ps_configuration`: Memorizza coppie chiave-valore per le impostazioni del modulo, come `MYTIKTOK_PIXEL_ID`, `MYTIKTOK_ACCESS_TOKEN`, `MYTIKTOK_TRACKING_MODE`, ecc.

#### Tabella degli Hook Registrati

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Inizializza il codice base del TikTok Pixel, carica `mytiktok.js` e imposta le variabili di configurazione globali. |
| `displayBeforeBodyClosingTag` | Poco prima del tag `</body>`. | Potrebbe iniettare script o dati aggiuntivi che devono essere eseguiti dopo il caricamento del DOM, o per eventi CAPI PageView. |
| `displayProductAdditionalInfo` | Sulla pagina del prodotto, tipicamente vicino ai dettagli del prodotto. | Attiva l'evento `ViewContent`, passando dati specifici del prodotto a TikTok. |
| `displayShoppingCartFooter` | Sulla pagina del carrello, solitamente sotto il riepilogo del carrello. | Attiva l'evento `AddToCart` (se non già gestito da AJAX) e potenzialmente `InitiateCheckout`. |
| `displayPaymentTop` | Nella parte superiore della pagina di selezione del pagamento durante il checkout. | Attiva l'evento `InitiateCheckout`. |
| `displayOrderConfirmation` | Sulla pagina di conferma dell'ordine dopo un acquisto riuscito. | Attiva l'evento cruciale `CompletePayment`, inviando i dettagli completi dell'ordine (valore, prodotti, valuta) a TikTok. |
| `actionFrontControllerSetMedia` | Quando un controller frontale imposta i suoi asset multimediali. | Inietta i file JS/CSS specifici del modulo nel front office. |
| `actionAdminControllerSetMedia` | Quando un controller admin imposta i suoi asset multimediali. | Inietta i file JS/CSS specifici del modulo nel back office. |
| `actionValidateOrder` | Dopo che un ordine è stato convalidato con successo. | Trigger lato server per l'evento `CompletePayment` tramite Events API, garantendo un tracciamento affidabile delle conversioni. |
| `actionCartSave` | Quando il carrello viene aggiornato (es. aggiungi/rimuovi prodotto). | Trigger lato server per gli eventi `AddToCart` o `RemoveFromCart` tramite Events API. |
| `actionProductUpdate` | Quando un prodotto viene aggiornato nel back office. | Potenzialmente utilizzato per la sincronizzazione del catalogo o i controlli di qualità dei dati. |
| `actionObjectProductAddAfter` | Dopo l'aggiunta di un nuovo prodotto. | Potenzialmente utilizzato per la sincronizzazione del catalogo o i controlli di qualità dei dati. |
| `actionObjectProductUpdateAfter` | Dopo l'aggiornamento di un prodotto. | Potenzialmente utilizzato per la sincronizzazione del catalogo o i controlli di qualità dei dati. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "TikTok Pixel / Events API", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto dedicato è disponibile per assisterti con qualsiasi problema tecnico o domanda relativa alla funzionalità del modulo.
