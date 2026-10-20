---
title: "Pinterest Tag & Conversions API - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Pinterest Tag & Conversions API di MyPresta.eu."
sidebar:
  label: "Pinterest Tag & Conversions API - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Pinterest Tag & Conversions API su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/pinterest-tag-conversions-api.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/pinterest-tag-conversions-api/)
>
> ---


# Pinterest Tag & Conversions API

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di Hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL). Il tuo server deve essere in grado di effettuare richieste HTTP in uscita agli endpoint API di Pinterest.

## 2. Panoramica Completa della Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)

Questo è il centro principale per impostare il tuo tracciamento Pinterest. Troverai varie sezioni e schede per gestire il tuo Pinterest Tag, Conversions API e la qualità dei dati.

#### Impostazioni Generali e Modalità di Tracciamento

-   **ID Tag Pinterest (Obbligatorio)**

    -   **Cosa fa questa impostazione:** Questo è il tuo identificatore univoco fornito da Pinterest. Indica a Pinterest a quale account pubblicitario appartengono i dati del tuo sito web.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando inserito:* Consente al modulo di inviare dati al tuo account pubblicitario Pinterest. Senza di esso, nessun tracciamento può avvenire.
        -   *Quando vuoto:* Il modulo non può inviare alcun dato a Pinterest.
    -   **Valore consigliato:** Il tuo ID Tag Pinterest. Puoi trovarlo nel tuo Pinterest Ads Manager sotto "Annunci" > "Conversioni" > "Pinterest Tag".
    -   **Scenario / esempio del commerciante:** Hai appena creato un account Pinterest Ads e devi collegare il tuo negozio ad esso. Copia l'ID Tag da Pinterest e incollalo qui.
-   **Modalità di Tracciamento**

    -   **Cosa fa questa impostazione:** Determina come il tuo negozio invia i dati a Pinterest. Puoi scegliere tra il tradizionale Pinterest Tag (lato browser), la più robusta Conversions API (lato server) o una combinazione di entrambi.
    -   **Effetto della modifica di questa impostazione:**
        -   *Pinterest Tag (lato browser):* I dati vengono inviati direttamente dal browser del cliente. Questo è più semplice ma può essere influenzato da ad blocker o impostazioni sulla privacy del browser.
        -   *Conversions API (lato server):* I dati vengono inviati direttamente dal tuo server PrestaShop a Pinterest. Questo è più affidabile e meno soggetto a blocchi, offrendo una migliore accuratezza dei dati.
        -   *Entrambi (Ibrido con Deduplicazione):* I dati vengono inviati tramite entrambi i metodi. Il modulo aggiunge automaticamente un `event_id` univoco a ogni evento, consentendo a Pinterest di identificare e ignorare gli eventi duplicati, garantendo la massima copertura dei dati senza sovracontare.
    -   **Valore consigliato:** **Entrambi (Ibrido con Deduplicazione)** per il tracciamento più affidabile e completo.
    -   **Scenario / esempio del commerciante:** Vuoi assicurarti che le tue campagne Pinterest siano il più accurate possibile, anche con l'aumento delle misure di privacy. Scegliere "Entrambi" offre il meglio di entrambi i mondi.

#### Impostazioni Conversions API (CAPI) (Visibili se è selezionata la modalità CAPI o Entrambi)

-   **Token di Accesso Conversions API (Obbligatorio per CAPI)**

    -   **Cosa fa questa impostazione:** Questo è un token sicuro che autentica il tuo server quando invia dati direttamente alla Conversions API di Pinterest. È come una password per il tuo server per comunicare con Pinterest.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando inserito:* Consente al tuo server di inviare dati tramite la Conversions API.
        -   *Quando vuoto:* Il tracciamento della Conversions API non funzionerà, anche se selezionato come modalità di tracciamento.
    -   **Valore consigliato:** Il tuo Token di Accesso Conversions API di Pinterest. Generalo nel tuo Pinterest Ads Manager sotto "Annunci" > "Conversioni" > "Conversions API".
    -   **Scenario / esempio del commerciante:** Hai deciso di utilizzare la Conversions API per un tracciamento più affidabile. Genererai questo token in Pinterest e lo incollerai qui.
-   **Abilita Corrispondenza Migliorata per CAPI**

    -   **Cosa fa questa impostazione:** Quando abilitata, il modulo invia informazioni aggiuntive sul cliente (come email, numero di telefono, nome, indirizzo – tutti hash per la privacy) con gli eventi della Conversions API. Questo aiuta Pinterest a far corrispondere gli eventi a utenti specifici in modo più accurato, anche se non sono loggati su Pinterest.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitata:* Migliora l'accuratezza della corrispondenza degli eventi su Pinterest, portando a una migliore targetizzazione del pubblico e ottimizzazione delle campagne.
        -   *Quando disabilitata:* Vengono inviati solo dati di eventi di base, riducendo potenzialmente l'accuratezza della corrispondenza.
    -   **Valore consigliato:** **SÌ**. Questo migliora significativamente la qualità dei dati e le prestazioni degli annunci.
    -   **Scenario / esempio del commerciante:** Vuoi assicurarti che Pinterest possa attribuire accuratamente le vendite ai tuoi annunci, anche se i clienti utilizzano dispositivi o browser diversi. La Corrispondenza Migliorata aiuta a colmare queste lacune.

#### Privacy dei Dati e Consenso

-   **Integra con Modulo di Consenso ai Cookie**
    -   **Cosa fa questa impostazione:** Se utilizzi un modulo di consenso ai cookie separato (ad esempio, un modulo di conformità GDPR), abilitando questa opzione si garantisce che il tracciamento di Pinterest si attivi solo dopo che il cliente ha dato il proprio consenso.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitata:* Il tracciamento di Pinterest rispetterà le scelte di consenso del cliente dal tuo modulo cookie. Se il consenso viene negato, nessun dato di Pinterest viene inviato.
        -   *Quando disabilitata:* Il tracciamento di Pinterest si attiverà indipendentemente da altre impostazioni di consenso ai cookie, portando potenzialmente a problemi di conformità.
    -   **Valore consigliato:** **SÌ** se utilizzi un modulo di consenso ai cookie. **NO** se non ne utilizzi uno o gestisci il consenso manualmente.
    -   **Scenario / esempio del commerciante:** Il tuo negozio deve essere conforme al GDPR. Abilitando questa opzione, ti assicuri che il tracciamento di Pinterest aderisca alle preferenze di privacy dei tuoi clienti.

#### Impostazioni Avanzate e Debugging

-   **Abilita Modalità Debug**

    -   **Cosa fa questa impostazione:** Attiva una modalità speciale che visualizza informazioni dettagliate sugli eventi Pinterest inviati, direttamente nella console per sviluppatori del tuo browser. Questo è utile per verificare che il tuo tracciamento funzioni correttamente.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitata:* Sviluppatori e webmaster possono vedere i dati degli eventi Pinterest in tempo reale nella console del browser. Questo **non dovrebbe mai** essere abilitato su un negozio di produzione live per la visualizzazione pubblica generale.
        -   *Quando disabilitata:* Nessuna informazione di debug viene mostrata.
    -   **Valore consigliato:** **NO** per un negozio di produzione live. **SÌ** solo durante la configurazione e il test.
    -   **Scenario / esempio del commerciante:** Hai appena installato il modulo e vuoi confermare che gli eventi "Aggiungi al carrello" si attivino correttamente. Abiliti la modalità debug, aggiungi un prodotto al carrello e controlli la console del browser per i dati dell'evento.
-   **Domini Linker (per il tracciamento cross-domain)**

    -   **Cosa fa questa impostazione:** Se il tuo negozio utilizza più sottodomini o reindirizza a un altro dominio durante il processo di checkout (ad esempio, un dominio di gateway di pagamento separato), puoi elencare tali domini qui. Questo aiuta Pinterest ad attribuire correttamente le azioni tra diversi domini.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando i domini sono elencati:* Pinterest può mantenere la continuità del tracciamento tra questi domini, prevenendo la perdita di dati.
        -   *Quando vuoto:* Il tracciamento potrebbe interrompersi se i clienti navigano tra diversi domini durante il loro percorso, portando a dati incompleti.
    -   **Valore consigliato:** Lascia vuoto a meno che tu non abbia specifiche esigenze di tracciamento cross-domain. In tal caso, inserisci ogni dominio su una nuova riga.
    -   **Scenario / esempio del commerciante:** Il tuo negozio principale è `shop.example.com`, ma il tuo blog è `blog.example.com` e vuoi tracciare gli utenti che visitano entrambi. Aggiungeresti `blog.example.com` qui.

#### Qualità dei Dati e Punteggio di Salute (Sezioni Informative)

Queste sezioni forniscono approfondimenti sulla tua configurazione di tracciamento e non sono impostazioni di configurazione dirette, ma piuttosto report generati dal modulo.

-   **Punteggio di Salute**: Mostra un punteggio complessivo che indica la qualità e la completezza della tua configurazione di tracciamento Pinterest. Un punteggio più alto significa dati più affidabili.
-   **Dottore del Catalogo**: Aiuta a identificare potenziali problemi con i dati del tuo catalogo prodotti che potrebbero influire sulla capacità di Pinterest di abbinare i prodotti per gli annunci dinamici.
-   **Coach della Qualità dei Dati**: Fornisce raccomandazioni e avvisi sui dati dei tuoi eventi, come parametri mancanti o formattazione errata, per aiutarti a migliorare l'accuratezza.
-   **Statistiche in Tempo Reale**: Visualizza gli eventi recenti inviati a Pinterest, consentendoti di monitorare l'attività in tempo reale.
-   **Eventi Recenti**: Un registro degli eventi più recenti elaborati dal modulo.

### 2.2 Schermate Amministrative Dedicate e Viste del Controller

#### 2.2.1 AdminMypinterestAjaxController (Back Office > Moduli > Pinterest Tag & Conversions API > Statistiche in Tempo Reale / Punteggio di Salute / Coach della Qualità dei Dati)

Questo controller alimenta le sezioni dinamiche e interattive all'interno della pagina di configurazione principale del modulo, in particolare per funzionalità come Statistiche in Tempo Reale, Punteggio di Salute e Coach della Qualità dei Dati.

-   **Nome Schermata e Posizione Menu:** Questi non sono elementi di menu autonomi, ma piuttosto pannelli interattivi all'interno della pagina di configurazione principale del modulo (Back Office > Moduli > Gestione moduli > Configura "Pinterest Tag & Conversions API").
-   **Azioni e Impostazioni Disponibili:** Questo controller gestisce le richieste AJAX per recuperare e visualizzare dati e report in tempo reale.
    -   **Statistiche in Tempo Reale**: Mostra un feed in tempo reale di eventi (es. PageView, AddToCart, Purchase) mentre vengono inviati a Pinterest, inclusa l'indicazione se sono stati inviati tramite Tag, CAPI o entrambi. Questo ti consente di verificare rapidamente che gli eventi si attivino.
    -   **Punteggio di Salute**: Visualizza un riepilogo della salute della tua configurazione di tracciamento, evidenziando le aree di miglioramento (es. token CAPI mancante, bassa qualità di corrispondenza degli eventi).
    -   **Coach della Qualità dei Dati**: Offre raccomandazioni specifiche per migliorare la qualità dei dati inviati a Pinterest, come garantire che tutti i parametri richiesti siano inclusi per ogni tipo di evento.
    -   **Dottore del Catalogo**: Analizza il feed del tuo catalogo prodotti (se ne utilizzi uno per Pinterest) e segnala potenziali problemi che potrebbero ostacolare gli annunci dinamici dei prodotti.
-   **Effetto delle modifiche:** L'interazione con questi pannelli (es. aggiornamento delle Statistiche in Tempo Reale) attiva chiamate AJAX che recuperano i dati più recenti dal tuo server o dall'API di Pinterest, fornendo approfondimenti aggiornati senza ricaricare l'intera pagina.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Controlla regolarmente il Punteggio di Salute e il Coach della Qualità dei Dati per assicurarti che il tuo tracciamento rimanga ottimale. Utilizza le Statistiche in Tempo Reale durante i test o dopo aver apportato modifiche per verificare che gli eventi si attivino correttamente.

#### 2.2.2 index.php (mypinterest/controllers/admin/index.php)

Questo file è un segnaposto e tipicamente serve come misura di sicurezza per prevenire la visualizzazione diretta delle directory nelle cartelle di amministrazione di PrestaShop. Non rappresenta una schermata configurabile o un'entità gestita in sé.

### 2.3 Tabella di Riferimento Rapido della Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | ID Tag Pinterest | Il tuo ID Tag | Collega il tuo negozio al tuo account pubblicitario Pinterest per il tracciamento. |
| Configurazione Modulo | Modalità di Tracciamento | Entrambi (Ibrido) | Invia dati tramite browser (Tag) e server (CAPI) per la massima affidabilità. |
| Configurazione Modulo | Token di Accesso Conversions API | Il tuo Token CAPI | Autentica l'invio di dati lato server a Pinterest. |
| Configurazione Modulo | Abilita Corrispondenza Migliorata per CAPI | SÌ | Migliora l'accuratezza della corrispondenza degli eventi su Pinterest per una migliore targetizzazione. |
| Configurazione Modulo | Integra con Modulo di Consenso ai Cookie | SÌ (se applicabile) | Garantisce che il tracciamento di Pinterest rispetti le scelte di privacy del cliente. |
| Configurazione Modulo | Abilita Modalità Debug | NO (su negozio live) | Mostra informazioni di tracciamento dettagliate nella console del browser per i test. |
| Configurazione Modulo | Domini Linker | Vuoto (a meno che non sia necessario) | Mantiene la continuità del tracciamento tra più domini correlati. |
| Pannello Statistiche in Tempo Reale | N/A | N/A | Visualizza gli eventi Pinterest in tempo reale per la verifica. |
| Pannello Punteggio di Salute | N/A | N/A | Fornisce una valutazione complessiva della qualità della tua configurazione di tracciamento. |
| Pannello Coach della Qualità dei Dati | N/A | N/A | Offre raccomandazioni per migliorare l'accuratezza dei dati degli eventi. |
| Pannello Dottore del Catalogo | N/A | N/A | Identifica i problemi nel tuo catalogo prodotti per gli annunci Pinterest. |

## 3. Risoluzione dei Problemi per il Commerciante e Domande Frequenti (FAQ)

**D1: Ho installato il modulo, ma non vedo dati nel mio Pinterest Ads Manager. Cosa devo fare?**
R1: Innanzitutto, ricontrolla che il tuo **ID Tag Pinterest** e il **Token di Accesso Conversions API** (se usi CAPI) siano stati inseriti correttamente nella configurazione del modulo. Assicurati che non ci siano errori di battitura. Successivamente, svuota la cache di PrestaShop (**Parametri Avanzati > Prestazioni > Svuota cache**). Poi, visita il front office del tuo negozio ed esegui alcune azioni (visualizza un prodotto, aggiungi al carrello, completa un acquisto di prova). Se hai abilitato la "Modalità Debug" nel modulo, controlla la console per sviluppatori del tuo browser per gli eventi Pinterest. Se ancora non vedi dati, verifica la configurazione del tuo Pinterest Ads Manager e assicurati che il tuo account sia attivo.

**D2: Il mio Pinterest Tag sembra essere bloccato dagli ad blocker. Come posso assicurarmi che i miei dati vengano comunque raccolti?**
R2: Questo è esattamente il motivo per cui la Conversions API (CAPI) è così importante! Assicurati che la tua "Modalità di Tracciamento" sia impostata su **"Entrambi (Ibrido con Deduplicazione)"**. In questo modo, anche se il Pinterest Tag lato browser viene bloccato, il tuo server PrestaShop invierà comunque i dati dell'evento direttamente a Pinterest tramite la Conversions API, garantendo che il tuo tracciamento rimanga robusto.

**D3: Come gestisce questo modulo la privacy dei clienti e il GDPR/CCPA?**
R3: Il modulo include un'opzione per **"Integrare con Modulo di Consenso ai Cookie"**. Se hai un modulo di consenso ai cookie separato installato (cosa altamente raccomandata per la conformità alla privacy), abilita questa impostazione. Il tracciamento di Pinterest si attiverà quindi solo dopo che il cliente avrà dato il proprio consenso tramite la tua soluzione di consenso esistente. Il modulo esegue anche l'hashing dei dati sensibili dei clienti prima di inviarli tramite Corrispondenza Migliorata per CAPI, aggiungendo un ulteriore livello di privacy.

**D4: Vedo un "Punteggio di Salute" basso o avvisi nel "Coach della Qualità dei Dati". Cosa significano?**
R4: Queste sezioni sono progettate per aiutarti a ottimizzare il tuo tracciamento. Un Punteggio di Salute basso o avvisi di solito indicano che alcuni parametri di dati potrebbero essere mancanti o formattati in modo errato, o che la tua configurazione non è completamente ottimizzata (ad esempio, CAPI non abilitata). Rivedi le raccomandazioni specifiche fornite nei pannelli "Coach della Qualità dei Dati" e "Dottore del Catalogo". Ti guideranno su come migliorare la qualità dei tuoi dati, il che influisce direttamente sull'efficacia dei tuoi annunci Pinterest.

**D5: Questo modulo rallenterà il mio sito web?**
R5: Il modulo è progettato per essere altamente ottimizzato. Il Pinterest Tag lato browser viene caricato in modo asincrono, il che significa che non blocca il caricamento della tua pagina. Le chiamate alla Conversions API lato server avvengono in background e non influiscono sui tempi di caricamento della pagina del front office. Non dovresti riscontrare rallentamenti evidenti a causa di questo modulo.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

### 4.1 Panoramica dell'Architettura

Il modulo `Pinterest Tag & Conversions API` (`mypinterest`) implementa una strategia di tracciamento ibrida per Pinterest, combinando il tradizionale Pinterest Tag lato browser con la Conversions API (CAPI) lato server. Segue il pattern MVC di PrestaShop ove applicabile, sfruttando gli hook per l'iniezione di eventi nel front-office e controller admin dedicati per la configurazione e la reportistica dei dati. I componenti architettonici chiave includono:

-   **Factory del Tracker**: Istanzia dinamicamente il meccanismo di tracciamento appropriato (Tag, CAPI o Ibrido) in base alla configurazione del modulo.
-   **Mappatura degli Eventi**: Traduce gli eventi interni di PrestaShop (es. `actionCartSave`, `actionValidateOrder`) nei nomi e parametri standard degli eventi di Pinterest.
-   **Strumenti di Qualità dei Dati**: Classi dedicate per il punteggio di salute, la diagnostica del catalogo e il coaching sulla qualità dei dati, fornendo approfondimenti utili nel back office.
-   **Gestione del Consenso**: Integrazione con moduli di consenso ai cookie di terze parti per garantire la conformità GDPR/CCPA.
-   **Statistiche in Tempo Reale**: Monitoraggio degli eventi in tempo reale tramite AJAX per il debug e la verifica.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

-   `controllers/front/ajax.php`
    -   **Nome classe e classe genitore**: `MypinterestAjaxModuleFrontController` estende `ModuleFrontController`.
    -   **Responsabilità**: Gestisce le richieste AJAX dal front office, principalmente per l'invio di eventi lato server (CAPI) che sono attivati da azioni lato client ma devono essere elaborati in modo sicuro sul server. Questo può includere eventi difficili da tracciare puramente lato client o per scopi di deduplicazione. Probabilmente riceve i dati dell'evento da `mypinterest.js` e li invia al client CAPI.
-   `controllers/front/cron.php`
    -   **Nome classe e classe genitore**: `MypinterestCronModuleFrontController` estende `ModuleFrontController`.
    -   **Responsabilità**: Fornisce un endpoint per un cron job. Questo potrebbe essere utilizzato per attività come l'invio di eventi CAPI differiti, la sincronizzazione dei cataloghi prodotti o l'esecuzione di controlli periodici sulla qualità dei dati senza interazione diretta dell'utente.
-   `controllers/front/index.php`
    -   **Nome classe e classe genitore**: `MypinterestIndexModuleFrontController` estende `ModuleFrontController`.
    -   **Responsabilità**: Un controller frontale segnaposto, tipicamente utilizzato per prevenire la visualizzazione diretta delle directory o come fallback per rotte specifiche del modulo che non si adattano ad altri controller. In questo modulo, probabilmente serve a uno scopo minimo o reindirizza.

#### Controller Admin Back-Office

-   `controllers/admin/AdminMypinterestAjaxController.php`
    -   **Nome classe e classe genitore**: `AdminMypinterestAjaxController` estende `ModuleAdminController`.
    -   **Nome scheda ed entità gestita**: Questo controller non è esposto direttamente come scheda di menu ma funge da endpoint AJAX per la pagina di configurazione del modulo. Gestisce le richieste di dati dinamici visualizzati nei pannelli "Statistiche in Tempo Reale", "Punteggio di Salute", "Coach della Qualità dei Dati" e "Dottore del Catalogo" all'interno della configurazione principale del modulo. Recupera log di eventi in tempo reale, metriche di salute e report diagnostici.
-   `controllers/admin/index.php`
    -   **Nome classe e classe genitore**: Non un controller funzionale.
    -   **Nome scheda ed entità gestita**: Questo è un segnaposto di sicurezza, che impedisce la visualizzazione delle directory.

### 4.3 Classi e Modelli Core (`classes/`)

-   `classes/autoload.php`: File di autoload standard di PrestaShop, che garantisce il corretto caricamento delle classi del modulo.
-   `classes/MypinterestCapiClient.php`:
    -   **Tabella database**: Nessuna direttamente.
    -   **Estende**: Nessun `ObjectModel`.
    -   **Metodi pubblici chiave**: Gestisce le richieste HTTP effettive all'endpoint della Conversions API di Pinterest. Incapsula la logica per la costruzione dei payload CAPI, inclusi dati evento, dati utente e token di accesso.
-   `classes/MypinterestCapiTracker.php`:
    -   **Tabella database**: Nessuna.
    -   **Estende**: Implementa `MypinterestTrackerInterface`.
    -   **Metodi pubblici chiave**: Gestisce la logica per il tracciamento degli eventi specificamente tramite la Conversions API. Formatta i dati per CAPI, gestisce la deduplicazione degli eventi (`event_id`) e delega l'invio a `MypinterestCapiClient`.
-   `classes/MypinterestCatalogDoctor.php`:
    -   **Tabella database**: Nessuna.
    -   **Estende**: Nessun `ObjectModel`.
    -   **Metodi pubblici chiave**: Contiene la logica per analizzare i dati dei prodotti (es. da feed di prodotti o oggetti `Product`) e identificare potenziali problemi che potrebbero influire sulla capacità di Pinterest di abbinare i prodotti per gli annunci dinamici. Fornisce report diagnostici.
-   `classes/MypinterestConsent.php`:
    -   **Tabella database**: Nessuna.
    -   **Estende**: Nessun `ObjectModel`.
    -   **Metodi pubblici chiave**: Gestisce l'integrazione con moduli di consenso ai cookie di terze parti. Controlla lo stato del consenso dell'utente e determina se il tracciamento di Pinterest deve essere abilitato o disabilitato in base al consenso.
-   `classes/MypinterestCurrencyHelper.php`:
    -   **Tabella database**: Nessuna.
    -   **Estende**: Nessun `ObjectModel`.
    -   **Metodi pubblici chiave**: Classe di utilità per la gestione della formattazione e conversione delle valute, garantendo che gli eventi Pinterest inviino i valori delle valute nel formato corretto.
-   `classes/MypinterestDataQualityCoach.php`:
    -   **Tabella database**: Nessuna.
    -   **Estende**: Nessun `ObjectModel`.
    -   **Metodi pubblici chiave**: Analizza la qualità dei dati degli eventi inviati (es. presenza di parametri richiesti, tipi di dati corretti) e fornisce raccomandazioni per il miglioramento.
-   `classes/MypinterestEventId.php`:
    -   **Tabella database**: Nessuna.
    -   **Estende**: Nessun `ObjectModel`.
    -   **Metodi pubblici chiave**: Genera e gestisce valori `event_id` univoci per la deduplicazione degli eventi, cruciale per il tracciamento ibrido.
-   `classes/MypinterestEventMap.php`:
    -   **Tabella database**: Nessuna.
    -   **Estende**: Nessun `ObjectModel`.
    -   **Metodi pubblici chiave**: Definisce la mappatura tra azioni/dati di PrestaShop e i nomi degli eventi standard di Pinterest e i loro parametri richiesti/raccomandati.
-   `classes/MypinterestEvents.php`:
    -   **Tabella database**: Nessuna.
    -   **Estende**: Nessun `ObjectModel`.
    -   **Metodi pubblici chiave**: Centralizza la logica per l'attivazione e la gestione di vari eventi Pinterest (PageView, AddToCart, Purchase, ecc.) in tutto il modulo.
-   `classes/MypinterestHealthScore.php`:
    -   **Tabella database**: Nessuna.
    -   **Estende**: Nessun `ObjectModel`.
    -   **Metodi pubblici chiave**: Calcola un "punteggio di salute" complessivo per la configurazione del tracciamento Pinterest basato su vari fattori come la presenza del token CAPI, la modalità di tracciamento e la qualità dei dati.
-   `classes/MypinterestHybridTracker.php`:
    -   **Tabella database**: Nessuna.
    -   **Estende**: Implementa `MypinterestTrackerInterface`.
    -   **Metodi pubblici chiave**: Orchestra il tracciamento quando è selezionata la modalità "Entrambi". Chiama sia `MypinterestTagTracker` che `MypinterestCapiTracker`, garantendo che `event_id` sia coerente per la deduplicazione.
-   `classes/MypinterestLiveStats.php`:
    -   **Tabella database**: Memorizza i log degli eventi recenti (es. in `ps_configuration` o una tabella personalizzata).
    -   **Estende**: Nessun `ObjectModel`.
    -   **Metodi pubblici chiave**: Registra e recupera gli eventi Pinterest recenti per la visualizzazione nel pannello "Statistiche in Tempo Reale" nel back office.
-   `classes/MypinterestProductIdResolver.php`:
    -   **Tabella database**: Nessuna.
    -   **Estende**: Nessun `ObjectModel`.
    -   **Metodi pubblici chiave**: Aiuta a risolvere e formattare gli ID prodotto per soddisfare i requisiti del catalogo di Pinterest, garantendo una corrispondenza accurata dei prodotti per gli annunci dinamici.
-   `classes/MypinterestPropertyRules.php`:
    -   **Tabella database**: Nessuna.
    -   **Estende**: Nessun `ObjectModel`.
    -   **Metodi pubblici chiave**: Definisce regole e convalide per le proprietà degli eventi Pinterest, garantendo che i dati inviati a Pinterest aderiscano alle loro specifiche.
-   `classes/MypinterestTagTracker.php`:
    -   **Tabella database**: Nessuna.
    -   **Estende**: Implementa `MypinterestTrackerInterface`.
    -   **Metodi pubblici chiave**: Gestisce la logica per l'iniezione dello script del Pinterest Tag lato browser e l'attivazione degli eventi tramite chiamate `pintrk()`.
-   `classes/MypinterestTrackerFactory.php`:
    -   **Tabella database**: Nessuna.
    -   **Estende**: Nessun `ObjectModel`.
    -   **Metodi pubblici chiave**: Una classe con pattern factory responsabile della creazione e restituzione dell'istanza del tracker corretta (`MypinterestTagTracker`, `MypinterestCapiTracker` o `MypinterestHybridTracker`) in base alla configurazione del modulo.
-   `classes/MypinterestTrackerInterface.php`:
    -   **Tabella database**: Nessuna.
    -   **Estende**: Nessun `ObjectModel`.
    -   **Metodi pubblici chiave**: Definisce l'interfaccia comune per tutti i tracker Pinterest, garantendo coerenza nel modo in cui gli eventi vengono gestiti indipendentemente dal metodo di tracciamento sottostante.
-   `classes/MypinterestUserData.php`:
    -   **Tabella database**: Nessuna.
    -   **Estende**: Nessun `ObjectModel`.
    -   **Metodi pubblici chiave**: Raccoglie e formatta i dati del cliente (email, telefono, indirizzo, ecc.) per la "Corrispondenza Migliorata", assicurandosi che siano hash e conformi ai requisiti di Pinterest.

### 4.4 Risorse JavaScript (`views/js/`)

-   `mypinterest/views/js/mypinterest-admin.js`:
    -   **Ambito**: Back-office.
    -   **Descrizione**: Contiene JavaScript per l'interfaccia di amministrazione del modulo. Gestisce le chiamate AJAX a `AdminMypinterestAjaxController` per recuperare statistiche in tempo reale, punteggi di salute e altri contenuti dinamici. Gestisce le interazioni dell'interfaccia utente nella pagina di configurazione.
-   `mypinterest/views/js/mypinterest-debug.js`:
    -   **Ambito**: Front-office.
    -   **Descrizione**: Caricato quando la "Modalità Debug" è abilitata. Fornisce la registrazione nella console e sovrapposizioni visive per visualizzare i dati degli eventi Pinterest mentre vengono inviati, aiutando nella risoluzione dei problemi e nella verifica.
-   `mypinterest/views/js/mypinterest-ghost.js`:
    -   **Ambito**: Front-office.
    -   **Descrizione**: Potenzialmente correlato al tracciamento "ghost" o differito, o un meccanismo di fallback per eventi che potrebbero non attivarsi immediatamente. Potrebbe essere utilizzato per tipi di eventi specifici o ritardi legati al consenso.
-   `mypinterest/views/js/mypinterest-live.js`:
    -   **Ambito**: Back-office.
    -   **Descrizione**: Specificamente per il pannello "Statistiche in Tempo Reale". Gestisce l'aggiornamento in tempo reale dei log degli eventi, interrogando il server tramite AJAX per visualizzare gli eventi Pinterest recenti.
-   `mypinterest/views/js/mypinterest-tcf.js`:
    -   **Ambito**: Front-office.
    -   **Descrizione**: Gestisce l'integrazione con moduli di consenso ai cookie compatibili con il Transparency and Consent Framework (TCF). Ascolta gli eventi di consenso e abilita/disabilita il tracciamento di Pinterest di conseguenza.
-   `mypinterest/views/js/mypinterest-wizard.js`:
    -   **Ambito**: Back-office.
    -   **Descrizione**: Alimenta la funzionalità della procedura guidata di configurazione all'interno della configurazione del modulo. Guida il commerciante attraverso i passaggi di configurazione iniziali, convalidando gli input e fornendo feedback.
-   `mypinterest/views/js/mypinterest.js`:
    -   **Ambito**: Front-office.
    -   **Descrizione**: Il principale JavaScript del front-office per il Pinterest Tag. Inietta la libreria `pintrk()`, inizializza il Pinterest Tag e attiva eventi standard (PageView, AddToCart, Checkout, Purchase) basati su eventi DOM o hook JavaScript di PrestaShop. È anche responsabile della generazione di `event_id` per la deduplicazione e potenzialmente dell'invio di chiamate AJAX a `controllers/front/ajax.php` per gli eventi CAPI.

### 4.5 Fogli di Stile CSS (`views/css/`)

-   `mypinterest/views/css/mypinterest-admin.css`:
    -   **Ambito**: Stile del modulo di amministrazione del back-office.
    -   **Descrizione**: Stili per la pagina di configurazione del modulo, inclusi il layout delle schede, i campi di input, i pulsanti e i pannelli dinamici per Statistiche in Tempo Reale, Punteggio di Salute, ecc.
    -   **Selettori di classe CSS chiave**: `.mypinterest-config`, `.mypinterest-tab-content`, `.mypinterest-health-score`, `.mypinterest-live-stats`.
-   `mypinterest/views/css/mypinterest-debug.css`:
    -   **Ambito**: Stile del cliente del front-office (solo quando la modalità debug è attiva).
    -   **Descrizione**: Fornisce lo stile per l'overlay di debug o l'output della console, rendendo le informazioni di debug più leggibili per gli sviluppatori.

### 4.6 Struttura del Template Smarty (`views/templates/`)

#### Template degli Hook (`views/templates/hook/`)

-   `mypinterest/views/templates/hook/capi-pageview.tpl`:
    -   **Hook**: Probabilmente `displayHeader` o `displayFooter`.
    -   **Output**: Renderizza un elemento nascosto o un piccolo script per attivare un evento PageView lato server tramite CAPI, spesso utilizzato per il tracciamento del caricamento iniziale della pagina o come fallback.
-   `mypinterest/views/templates/hook/debug.tpl`:
    -   **Hook**: `displayHeader` o `displayFooter` (renderizzato condizionalmente).
    -   **Output**: Inietta lo script `mypinterest-debug.js` e potenzialmente una struttura HTML di overlay di debug quando la modalità debug è attiva.
-   `mypinterest/views/templates/hook/displayOrderConfirmation.tpl`:
    -   **Hook**: `displayOrderConfirmation`.
    -   **Output**: Renderizza lo script dell'evento "Acquisto" di Pinterest, inclusi i dettagli dell'ordine (valore, valuta, ID ordine, prodotti) sia per il Pinterest Tag che per CAPI (tramite chiamata AJAX).
-   `mypinterest/views/templates/hook/ghost.tpl`:
    -   **Hook**: `displayHeader` o `displayFooter`.
    -   **Output**: Potenzialmente correlato allo script `mypinterest-ghost.js`, utilizzato per meccanismi di tracciamento specifici, possibilmente differiti o in background.
-   `mypinterest/views/templates/hook/header.tpl`:
    -   **Hook**: `displayHeader`.
    -   **Output**: Inietta il codice base principale del Pinterest Tag (`pintrk()`) e lo script `mypinterest.js`. Inizializza il Pinterest Tag con l'ID Tag e potenzialmente attiva l'evento "PageView" iniziale.
-   `mypinterest/views/templates/hook/payment.tpl`:
    -   **Hook**: `displayPayment` o `displayPaymentTop`.
    -   **Output**: Potrebbe essere utilizzato per tracciare l'inizio del processo di checkout o la selezione di un metodo di pagamento, attivando potenzialmente un evento "Checkout" o "InitiateCheckout".
-   `mypinterest/views/templates/hook/product-details.tpl`:
    -   **Hook**: `displayProductButtons` o `displayFooterProduct`.
    -   **Output**: Renderizza JavaScript per tracciare gli eventi "ViewContent" quando viene caricata una pagina prodotto, inclusi ID prodotto, nome, prezzo e categoria. Probabilmente include anche la logica per gli eventi "Aggiungi al carrello".

#### Template Admin (`views/templates/admin/`)

-   `mypinterest/views/templates/admin/consent-guide.tpl`: Visualizza informazioni e indicazioni sull'integrazione con i moduli di consenso ai cookie.
-   `mypinterest/views/templates/admin/doctor.tpl`: Renderizza il pannello "Dottore del Catalogo", mostrando le diagnostiche per i dati del catalogo prodotti.
-   `mypinterest/views/templates/admin/dq.tpl`: Renderizza il pannello "Coach della Qualità dei Dati", fornendo raccomandazioni per migliorare i dati degli eventi.
-   `mypinterest/views/templates/admin/health.tpl`: Renderizza il pannello "Punteggio di Salute", visualizzando la salute complessiva del tracciamento.
-   `mypinterest/views/templates/admin/linker-domains.tpl`: Template per il campo di input "Domini Linker".
-   `mypinterest/views/templates/admin/live-maintain.tpl`: Possibilmente un messaggio di manutenzione o stato per la funzione di statistiche in tempo reale.
-   `mypinterest/views/templates/admin/live.tpl`: Renderizza il pannello "Statistiche in Tempo Reale", visualizzando i log degli eventi in tempo reale.
-   `mypinterest/views/templates/admin/mode-context.tpl`: Fornisce informazioni contestuali sulla modalità di tracciamento selezionata.
-   `mypinterest/views/templates/admin/mode-note-both.tpl`: Nota/spiegazione specifica per la modalità di tracciamento "Entrambi (Ibrido)".
-   `mypinterest/views/templates/admin/mode-note-capi.tpl`: Nota/spiegazione specifica per la modalità di tracciamento "Conversions API".
-   `mypinterest/views/templates/admin/mode-note-tag.tpl`: Nota/spiegazione specifica per la modalità di tracciamento "Pinterest Tag".
-   `mypinterest/views/templates/admin/mode-picker.tpl`: Renderizza i pulsanti radio o il menu a discesa per la selezione della "Modalità di Tracciamento".
-   `mypinterest/views/templates/admin/properties-list.tpl`: Visualizza un elenco di proprietà degli eventi e il loro stato (es. richiesto, consigliato).
-   `mypinterest/views/templates/admin/recent-events.tpl`: Renderizza una tabella o un elenco di eventi recenti per il pannello "Statistiche in Tempo Reale".
-   `mypinterest/views/templates/admin/tabs.tpl`: Renderizza la struttura di navigazione a schede per la pagina di configurazione del modulo.
-   `mypinterest/views/templates/admin/tag-chips.tpl`: Probabilmente per visualizzare gli ID del Pinterest Tag in un formato "chip" visivamente accattivante.
-   `mypinterest/views/templates/admin/tag-ids.tpl`: Renderizza i campi di input per l'ID del Pinterest Tag e il Token di Accesso CAPI.
-   `mypinterest/views/templates/admin/wizard.tpl`: Renderizza l'interfaccia della procedura guidata di configurazione passo-passo.

#### Template Front-office (`views/templates/front/`)

-   `mypinterest/views/templates/front/index.tpl`: Un template segnaposto, probabilmente non utilizzato per il rendering diretto ma come predefinito per il `MypinterestIndexModuleFrontController`.

### 4.7 Schema del Database e Mappa degli Hook

-   **Tabelle del Database**:

    -   Il modulo utilizza principalmente `ps_configuration` per memorizzare le sue impostazioni (es. `MYPINTEREST_TAG_ID`, `MYPINTEREST_TRACKING_MODE`, `MYPINTEREST_CAPI_TOKEN`).
    -   Potrebbe anche utilizzare una tabella personalizzata (es. `ps_mypinterest_events_log`) per memorizzare i dati degli eventi recenti per la funzione "Statistiche in Tempo Reale", sebbene questi possano anche essere memorizzati in `ps_configuration` come dati serializzati. (Nessun file SQL esplicito trovato, quindi probabilmente `ps_configuration` o creazione dinamica della tabella).
-   **Tabella degli Hook Registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Inietta il JavaScript base del Pinterest Tag, `mypinterest.js`, e potenzialmente gli eventi PageView iniziali. |
| `displayOrderConfirmation` | Nella pagina di conferma dell'ordine dopo un acquisto riuscito. | Attiva l'evento "Acquisto", inviando dati dettagliati sull'ordine e sui prodotti a Pinterest. |
| `displayProductButtons` | Nella pagina del prodotto, vicino al pulsante "Aggiungi al carrello". | Inietta JavaScript per tracciare gli eventi "ViewContent" e "Aggiungi al carrello". |
| `displayFooter` | Alla fine della sezione `<body>` di ogni pagina. | Può essere utilizzato come posizione alternativa o aggiuntiva per l'iniezione di script, specialmente per eventi che non devono bloccare il rendering della pagina. |
| `actionCartSave` | Quando un carrello viene aggiornato (es. prodotto aggiunto/rimosso). | Attiva gli eventi "AddToCart" o "RemoveFromCart", spesso gestiti lato server tramite CAPI o lato client tramite AJAX. |
| `actionValidateOrder` | Dopo che un ordine è stato convalidato con successo. | Attiva l'evento "Acquisto" lato server tramite CAPI per la massima affidabilità, complementando l'evento `displayOrderConfirmation` lato client. |
| `actionFrontControllerSetMedia` | Quando un controller frontale sta impostando i suoi media (JS/CSS). | Consente al modulo di registrare i suoi file JavaScript e CSS del front-office. |
| `actionAdminControllerSetMedia` | Quando un controller admin sta impostando i suoi media (JS/CSS). | Consente al modulo di registrare i suoi file JavaScript e CSS del back-office. |
| `actionObjectProductUpdateAfter` / `actionObjectProductAddAfter` | Dopo che un prodotto è stato aggiornato o aggiunto. | Potenzialmente utilizzato per aggiornare i dati del catalogo prodotti o attivare la diagnostica del catalogo. |
| `actionObjectProductDeleteAfter` | Dopo che un prodotto è stato eliminato. | Potenzialmente utilizzato per aggiornare i dati del catalogo prodotti. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo Pinterest Tag & Conversions API, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema tecnico o domanda riguardante la funzionalità del modulo.
