---
title: "Presta Speed Cache - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione passo-passo e riferimento per sviluppatori per il modulo Presta Speed Cache di PrestaShop di MyPresta.eu."
sidebar:
  label: "Presta Speed Cache - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Presta Speed Cache su MyPresta.eu](https://mypresta.eu/modules/administration-tools/presta-speed-cache.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/presta-speed-cache/)
>
> ---


# Presta Speed Cache

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5 (Il modulo è progettato per funzionare in questo intervallo, garantendo ampia compatibilità e supportando le ultime versioni stabili di PHP.)
- **Requisiti di hosting**: Sono richieste estensioni PHP standard come cURL, JSON e OpenSSL, che sono tipicamente disponibili sulla maggior parte degli ambienti di hosting moderni. Per metodi di caching avanzati come Redis o Memcached, questi servizi devono essere installati e configurati sul tuo server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è l'area di configurazione principale per Presta Speed Cache. Troverai varie impostazioni per ottimizzare il funzionamento della cache del tuo negozio.

#### Scheda Impostazioni generali

- **Abilita cache:**

  - **Cosa fa questa impostazione:** Questo è l'interruttore principale per il modulo. Attiva o disattiva la funzionalità di caching per l'intero negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il modulo inizierà a memorizzare nella cache le pagine e a servirle rapidamente. Le prestazioni del tuo negozio miglioreranno significativamente.
    - *Quando disabilitato:* Il modulo smetterà di memorizzare nella cache e il tuo negozio tornerà alla sua velocità predefinita di PrestaShop, che è tipicamente più lenta.
  - **Valore consigliato:** **SÌ**. Questa è la funzione principale del modulo.
  - **Scenario / esempio del commerciante:** Hai appena installato il modulo e vuoi attivare i vantaggi di velocità. Imposta questo su SÌ. Se stai risolvendo un problema con un altro modulo e sospetti che la cache possa interferire, potresti disabilitarla temporaneamente.
- **Durata cache (minuti):**

  - **Cosa fa questa impostazione:** Determina per quanto tempo una pagina memorizzata nella cache rimane valida prima che il modulo la consideri "obsoleta" e la ricostruisca.
  - **Effetto della modifica di questa impostazione:**
    - *Valore più alto (es. 1440 per 24 ore):* Le pagine vengono servite dalla cache per più tempo, riducendo il carico del server ma potenzialmente mostrando contenuti leggermente obsoleti se si apportano modifiche frequenti (es. aggiornamenti di prezzo).
    - *Valore più basso (es. 60 per 1 ora):* Le pagine vengono ricostruite più spesso, garantendo contenuti più freschi ma aumentando leggermente il carico del server.
  - **Valore consigliato:** Inizia con **1440** (24 ore). Regola in base alla frequenza con cui i dati dei tuoi prodotti cambiano.
  - **Scenario / esempio del commerciante:** Se aggiorni prezzi o descrizioni dei prodotti quotidianamente, una durata di 24 ore va bene. Se esegui vendite flash con modifiche di prezzo orarie, potresti ridurla a 60 o 120 minuti, o affidarti alle funzionalità di invalidazione automatica.
- **Metodo di archiviazione cache:**

  - **Cosa fa questa impostazione:** Seleziona dove vengono memorizzate le pagine nella cache. Metodi diversi offrono vari livelli di prestazioni e richiedono configurazioni server specifiche.
  - **Effetto della modifica di questa impostazione:**
    - *File System (predefinito):* Memorizza le pagine nella cache come file sul disco del tuo server. Il più facile da configurare, buono per la maggior parte dei negozi.
    - *Redis:* Memorizza la cache in memoria utilizzando il server Redis. Molto più veloce del file system, ideale per negozi ad alto traffico. Richiede che Redis sia installato e configurato sul tuo server.
    - *Memcached:* Memorizza la cache in memoria utilizzando il server Memcached. Simile a Redis nei vantaggi prestazionali, richiede anche la configurazione del server.
  - **Valore consigliato:** Inizia con **File System**. Se hai un negozio ad alto traffico e il tuo hosting lo supporta, considera **Redis** o **Memcached** per le massime prestazioni.
  - **Scenario / esempio del commerciante:** Il tuo negozio sta crescendo rapidamente e stai riscontrando rallentamenti occasionali. Il tuo host offre Redis. Il passaggio a Redis può migliorare drasticamente le prestazioni.
- **Escludi URL dalla cache:**

  - **Cosa fa questa impostazione:** Ti consente di specificare determinate pagine o sezioni del tuo negozio che *non* dovrebbero mai essere memorizzate nella cache. Questo è utile per pagine con contenuti altamente dinamici o sensibili.
  - **Effetto della modifica di questa impostazione:**
    - *Aggiungendo URL:* Quelle pagine verranno sempre generate fresche da PrestaShop, garantendo che il loro contenuto sia sempre aggiornato ma sacrificando la velocità per quelle pagine specifiche.
    - *Lasciando vuoto:* Tutte le pagine idonee verranno memorizzate nella cache.
  - **Valore consigliato:** Lascia vuoto a meno che tu non abbia esigenze specifiche. Usa con cautela.
  - **Scenario / esempio del commerciante:** Hai una pagina personalizzata "Richiesta di preventivo" che genera moduli unici basati sull'input dell'utente, o una pagina con aggiornamenti di stock in tempo reale da un'API esterna. Aggiungeresti `/module/yourmodule/quotepage` o `/stock-updates` a questo elenco.
- **Warm-up cache:**

  - **Cosa fa questa impostazione:** "Visita" automaticamente le pagine del tuo negozio in background per pre-riempire la cache, garantendo che anche il primo visitatore di una pagina sperimenti i vantaggi della velocità.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* La tua cache verrà popolata proattivamente, portando a tempi di caricamento più rapidi per tutti i visitatori, anche quelli che visitano una pagina per la prima volta dopo l'invalidazione della cache. Questo può aumentare leggermente il carico del server durante il processo di warm-up.
    - *Quando disabilitato:* Le pagine verranno memorizzate nella cache solo dopo la prima visita del cliente.
  - **Valore consigliato:** **SÌ**. Questo garantisce i massimi vantaggi di velocità per tutti gli utenti.
  - **Scenario / esempio del commerciante:** Hai appena svuotato la cache o aggiornato molti prodotti. L'abilitazione del warm-up garantirà che il tuo negozio sia veloce per i clienti immediatamente, invece di aspettare che visitino prima ogni pagina.
- **Ottimizzazione HTML:**

  - **Cosa fa questa impostazione:** Minifica l'output HTML delle tue pagine rimuovendo spazi, commenti e interruzioni di riga non necessari. Questo riduce le dimensioni del file della pagina, portando a download più veloci.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il codice HTML della tua pagina sarà più compatto, riducendo l'utilizzo della larghezza di banda e accelerando leggermente il rendering della pagina. Questo è generalmente sicuro.
    - *Quando disabilitato:* L'HTML verrà servito come generato da PrestaShop, senza minificazione.
  - **Valore consigliato:** **SÌ**. È un semplice e sicuro aumento delle prestazioni.
  - **Scenario / esempio del commerciante:** Vuoi spremere ogni bit di prestazioni dal tuo negozio. L'abilitazione di questa opzione renderà il tuo HTML più snello.

#### Scheda Blocchi dinamici

Questa sezione ti consente di definire parti della tua pagina che *non* dovrebbero essere memorizzate nella cache, ma invece caricate dinamicamente dopo che la pagina principale è stata caricata. Questo è fondamentale per contenuti personalizzati come il carrello, lo stato di accesso o output specifici di moduli.

- **Abilita blocchi dinamici:**

  - **Cosa fa questa impostazione:** Attiva la possibilità di definire aree specifiche della tua pagina che verranno caricate separatamente e dinamicamente, anche quando il resto della pagina viene servito dalla cache.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Puoi configurare moduli specifici o aree di contenuto per rimanere dinamici, garantendo che i contenuti personalizzati siano sempre freschi.
    - *Quando disabilitato:* Tutti i contenuti verranno memorizzati nella cache, portando potenzialmente a contenuti dinamici obsoleti (es. un carrello vuoto visualizzato anche se sono stati aggiunti articoli).
  - **Valore consigliato:** **SÌ**. Questo è essenziale per un negozio con cache funzionale.
  - **Scenario / esempio del commerciante:** Vuoi che il carrello del tuo cliente mostri sempre il numero corretto di articoli, anche se la pagina del prodotto è memorizzata nella cache.
- **Elenco moduli dinamici:**

  - **Cosa fa questa impostazione:** Questo è un elenco in cui selezioni quali moduli dovrebbero *sempre* essere renderizzati dinamicamente, anche se sono agganciati a una pagina memorizzata nella cache.
  - **Effetto della modifica di questa impostazione:**
    - *Aggiungendo un modulo:* L'output di quel modulo verrà recuperato fresco per ogni utente, garantendo che il suo contenuto sia sempre aggiornato (es. blocco carrello, blocco informazioni utente).
    - *Rimuovendo un modulo:* L'output del modulo verrà memorizzato nella cache insieme al resto della pagina, mostrando potenzialmente dati obsoleti.
  - **Valore consigliato:** Includi moduli come `ps_shoppingcart`, `ps_customeraccountlinks`, `ps_languageselector`, `ps_currencyselector` e qualsiasi altro modulo che visualizzi informazioni specifiche dell'utente o in tempo reale.
  - **Scenario / esempio del commerciante:** Installi un nuovo modulo "Live Chat" che deve visualizzare la disponibilità in tempo reale. Lo aggiungeresti a questo elenco per assicurarti che sia sempre dinamico.

#### Scheda Invalidation & Purge

Questa sezione gestisce come e quando la cache viene svuotata o aggiornata, garantendo che i tuoi clienti vedano sempre le ultime informazioni sui prodotti.

- **Invalidazione automatica della cache:**

  - **Cosa fa questa impostazione:** Quando abilitato, il modulo svuota automaticamente le pagine memorizzate nella cache pertinenti ogni volta che apporti modifiche nel back office di PrestaShop (es. aggiornamento di un prodotto, categoria o pagina CMS).
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Non devi svuotare manualmente la cache dopo ogni modifica. Il modulo svuota intelligentemente solo le pagine interessate, garantendo che i clienti vedano gli aggiornamenti rapidamente.
    - *Quando disabilitato:* Dovresti svuotare manualmente l'intera cache dopo ogni modifica significativa, oppure i clienti potrebbero vedere contenuti obsoleti fino alla scadenza della durata della cache.
  - **Valore consigliato:** **SÌ**. Questa è una funzionalità cruciale "imposta e dimentica" per la freschezza dei dati.
  - **Scenario / esempio del commerciante:** Aggiorni il prezzo di un prodotto. Con l'invalidazione automatica, la versione memorizzata nella cache di quella pagina prodotto (e potenzialmente delle sue pagine di categoria) viene svuotata, in modo che i clienti vedano immediatamente il nuovo prezzo.
- **Svuota cache all'aggiornamento del prodotto:**

  - **Cosa fa questa impostazione:** Controlla specificamente se la cache relativa a un prodotto viene svuotata quando quel prodotto viene aggiornato.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Assicura che qualsiasi pagina che visualizza il prodotto aggiornato (pagina prodotto, pagina categoria, risultati di ricerca) venga aggiornata nella cache.
    - *Quando disabilitato:* Gli aggiornamenti del prodotto potrebbero non riflettersi sulle pagine memorizzate nella cache fino alla scadenza della durata della cache o fino a quando non la svuoti manualmente.
  - **Valore consigliato:** **SÌ**. Essenziale per informazioni accurate sui prodotti.
  - **Scenario / esempio del commerciante:** Cambi l'immagine di un prodotto. Questa impostazione assicura che la nuova immagine appaia immediatamente sulla pagina del prodotto.
- **Svuota cache all'aggiornamento della categoria:**

  - **Cosa fa questa impostazione:** Controlla se la cache relativa a una categoria viene svuotata quando quella categoria viene aggiornata.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Assicura che le pagine di categoria e potenzialmente le pagine prodotto all'interno di quella categoria vengano aggiornate.
    - *Quando disabilitato:* Gli aggiornamenti di categoria (es. nome, descrizione, prodotti assegnati) potrebbero non riflettersi sulle pagine memorizzate nella cache.
  - **Valore consigliato:** **SÌ**. Importante per la navigazione e l'accuratezza del contenuto della categoria.
  - **Scenario / esempio del commerciante:** Rinomini una categoria. Questo assicura che il nuovo nome appaia nella tua navigazione e sulla pagina della categoria.
- **Svuota cache all'aggiornamento della pagina CMS:**

  - **Cosa fa questa impostazione:** Controlla se la cache relativa a una pagina CMS viene svuotata quando quella pagina viene aggiornata.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Assicura che le pagine CMS aggiornate (es. "Chi siamo", "Termini e condizioni") vengano immediatamente aggiornate.
    - *Quando disabilitato:* Gli aggiornamenti alle pagine CMS potrebbero non essere visibili ai clienti fino alla scadenza della cache.
  - **Valore consigliato:** **SÌ**. Importante per l'accuratezza del contenuto statico.
  - **Scenario / esempio del commerciante:** Aggiorni la tua pagina "Politica di spedizione". Questo assicura che i clienti vedano l'ultima versione.

#### Scheda Impostazioni avanzate

- **Abilita modalità debug:**

  - **Cosa fa questa impostazione:** Attiva una modalità speciale che visualizza informazioni sullo stato della cache direttamente sulle pagine del tuo front-office (visibile solo a te come amministratore).
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Vedrai una piccola sovrapposizione sulle pagine del tuo negozio che indica se la pagina è stata servita dalla cache, quando è stata memorizzata nella cache e altri dettagli diagnostici. Questo è prezioso per la risoluzione dei problemi.
    - *Quando disabilitato:* Nessuna informazione di debug viene mostrata.
  - **Valore consigliato:** **NO** per negozi in produzione. **SÌ** durante la configurazione o la risoluzione dei problemi.
  - **Scenario / esempio del commerciante:** Hai appena configurato il modulo e vuoi verificare che le pagine vengano effettivamente memorizzate nella cache correttamente. Abilita la modalità debug, naviga nel tuo negozio e controlla la sovrapposizione.
- **Abilita debug in tempo reale:**

  - **Cosa fa questa impostazione:** Fornisce una dashboard in tempo reale nel back office per monitorare gli hit della cache, i miss e altre metriche di performance.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Ottieni accesso a un potente strumento di monitoraggio per vedere quanto efficacemente sta funzionando la tua cache.
    - *Quando disabilitato:* Nessuna statistica della cache in tempo reale viene raccolta o visualizzata.
  - **Valore consigliato:** **SÌ** se vuoi monitorare attivamente le prestazioni. Può essere disabilitato se preferisci un overhead minimo.
  - **Scenario / esempio del commerciante:** Vuoi vedere l'impatto della tua strategia di caching nel tempo, osservando quante richieste vengono servite dalla cache rispetto a quelle generate fresche.
- **Abilita SWR (Stale-While-Revalidate):**

  - **Cosa fa questa impostazione:** Una strategia di caching avanzata in cui, se una pagina memorizzata nella cache è scaduta, il modulo serve immediatamente la versione *obsoleta* (scaduta) all'utente mentre contemporaneamente ricostruisce una versione fresca in background.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Gli utenti ottengono quasi sempre un caricamento istantaneo della pagina, anche se la cache è scaduta. La pagina potrebbe essere leggermente obsoleta per un momento, ma è incredibilmente veloce. La versione fresca sostituisce quella obsoleta per i visitatori successivi.
    - *Quando disabilitato:* Quando una pagina memorizzata nella cache scade, il visitatore successivo attenderà che la pagina venga ricostruita, il che può causare un leggero ritardo.
  - **Valore consigliato:** **SÌ**. Questo offre il miglior equilibrio tra velocità e freschezza per la maggior parte dei negozi.
  - **Scenario / esempio del commerciante:** Vuoi assicurarti che i tuoi clienti non sperimentino mai un caricamento lento, anche se la cache deve essere aggiornata. SWR offre questa esperienza "sempre veloce".
- **Cache per utenti loggati:**

  - **Cosa fa questa impostazione:** Determina se le pagine devono essere memorizzate nella cache anche per i clienti che hanno effettuato l'accesso ai loro account.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Anche gli utenti loggati beneficeranno delle pagine memorizzate nella cache, ma il modulo deve essere molto intelligente riguardo ai blocchi dinamici per garantire che i contenuti personalizzati (come i link "Il mio account", la cronologia ordini) rimangano corretti.
    - *Quando disabilitato:* Gli utenti loggati riceveranno sempre pagine fresche, non memorizzate nella cache. Questo garantisce una perfetta personalizzazione ma sacrifica la velocità per questi utenti.
  - **Valore consigliato:** **SÌ**, ma assicurati che i tuoi blocchi dinamici siano configurati correttamente per moduli come `ps_customeraccountlinks`.
  - **Scenario / esempio del commerciante:** Vuoi che anche i tuoi clienti di ritorno, loggati, godano di un'esperienza super-veloce, non solo gli ospiti.
- **Cache per dispositivi mobili:**

  - **Cosa fa questa impostazione:** Controlla se vengono generate e servite versioni separate delle pagine memorizzate nella cache per i dispositivi mobili.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il modulo creerà e servirà pagine memorizzate nella cache ottimizzate specificamente per gli utenti mobili, il che è cruciale se il tuo tema presenta differenze significative tra i layout desktop e mobile.
    - *Quando disabilitato:* Gli utenti mobili riceveranno la versione desktop memorizzata nella cache (se applicabile) o pagine non memorizzate nella cache, portando potenzialmente a contenuti più lenti o renderizzati in modo errato.
  - **Valore consigliato:** **SÌ** se il tuo tema è responsive e si rende in modo diverso per i dispositivi mobili.
  - **Scenario / esempio del commerciante:** Il tuo tema utilizza modelli o CSS diversi per i dispositivi mobili. La memorizzazione nella cache per i dispositivi mobili garantisce che ottengano la versione corretta e veloce.
- **Abilita Edge Purge (Varnish/CDN):**

  - **Cosa fa questa impostazione:** Si integra con sistemi di caching esterni come Varnish o Content Delivery Networks (CDN) per inviare richieste di svuotamento quando la cache di PrestaShop viene invalidata. Questo assicura che anche il CDN svuoti il suo vecchio contenuto.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il tuo CDN servirà sempre il contenuto più fresco dopo che hai apportato aggiornamenti, impedendo ai clienti di vedere vecchie versioni memorizzate dal CDN.
    - *Quando disabilitato:* Il tuo CDN potrebbe continuare a servire contenuti vecchi anche dopo che la cache di PrestaShop è stata svuotata, portando a incongruenze.
  - **Valore consigliato:** **SÌ** se stai utilizzando Varnish o un CDN (come Cloudflare, Akamai, ecc.) che supporta lo svuotamento della cache tramite API.
  - **Scenario / esempio del commerciante:** Utilizzi Cloudflare per le prestazioni. Quando aggiorni un prodotto, questa impostazione indica a Cloudflare di svuotare la sua cache per quel prodotto, in modo che tutti gli utenti vedano l'aggiornamento immediatamente.

#### Scheda Strumenti

Questa scheda fornisce azioni manuali per la gestione della cache.

- **Svuota tutta la cache:**

  - **Cosa fa questa impostazione:** Questo pulsante elimina immediatamente tutte le pagine memorizzate nella cache generate da Presta Speed Cache.
  - **Effetto della modifica di questa impostazione:** Tutto il contenuto memorizzato nella cache viene rimosso. La prossima volta che una pagina viene visitata, verrà generata fresca da PrestaShop e quindi nuovamente memorizzata nella cache. Questo rallenterà temporaneamente il tuo sito fino a quando la cache non si ricostruirà.
  - **Valore consigliato:** Usa solo quando necessario (es. dopo un importante aggiornamento del tema, installazione di un modulo, o se sospetti problemi di cache).
  - **Scenario / esempio del commerciante:** Hai apportato ampie modifiche al CSS del tuo tema e vuoi assicurarti che tutti i visitatori vedano immediatamente il nuovo design. Clicca su "Svuota tutta la cache".
- **Esegui warm-up cache:**

  - **Cosa fa questa impostazione:** Attiva manualmente il processo di warm-up della cache, che visita le pagine del tuo negozio per pre-popolare la cache.
  - **Effetto della modifica di questa impostazione:** Il modulo inizierà a generare versioni memorizzate nella cache delle tue pagine in background. Questo può richiedere del tempo a seconda delle dimensioni del tuo negozio e può consumare risorse del server durante il processo.
  - **Valore consigliato:** Usa dopo aver svuotato la cache o dopo importanti importazioni di prodotti/categorie per ricostruire rapidamente la cache.
  - **Scenario / esempio del commerciante:** Hai appena svuotato la cache e vuoi che il tuo negozio sia veloce per i clienti il più rapidamente possibile.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### 2.2.1 Gestione cache (Back Office > Presta Speed Cache > Gestione cache)

Questa schermata fornisce una panoramica dettagliata e un'interfaccia di gestione per le tue pagine memorizzate nella cache.

- **Nome schermata e posizione menu:** Puoi trovarlo navigando su **Presta Speed Cache** nel menu principale del back office di PrestaShop, quindi selezionando **Gestione cache**.
- **Azioni e impostazioni disponibili:**
  - **Griglia elenco cache:** Questa tabella visualizza un elenco di pagine attualmente memorizzate nella cache, inclusi dettagli come l'URL, l'ultima volta che è stata memorizzata nella cache, le sue dimensioni e il suo stato attuale (es. attiva, scaduta).
  - **Filtra e cerca:** Puoi filtrare l'elenco per URL, stato o altri criteri per trovare voci specifiche della cache.
  - **Svuota cache selezionata:** Ti consente di selezionare pagine specifiche memorizzate nella cache dall'elenco e svuotarle individualmente.
  - **Svuota tutta la cache (pulsante):** Un pulsante prominente per svuotare l'intera cache, simile a quello sulla pagina di configurazione principale.
  - **Esegui warm-up (pulsante):** Un pulsante prominente per avviare manualmente il processo di warm-up della cache.
- **Effetto delle modifiche:**
  - *Svuotamento di singole voci:* Solo le pagine selezionate verranno rimosse dalla cache, consentendo loro di essere ricostruite alla visita successiva. Questo è utile per aggiornamenti mirati senza influenzare l'intero negozio.
  - *Svuotamento di tutta la cache:* Reimposta l'intera cache, costringendo tutte le pagine a essere ricostruite.
  - *Esecuzione del warm-up:* Riempie proattivamente la cache, garantendo un caricamento più rapido per i visitatori successivi.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Utilizza questa schermata per monitorare la tua cache, identificare eventuali pagine che potrebbero non essere memorizzate nella cache correttamente o per eseguire svuotamenti mirati della cache se hai apportato un aggiornamento molto specifico che l'invalidazione automatica potrebbe aver perso.

#### 2.2.2 Dashboard (Back Office > Presta Speed Cache > Dashboard)

Questa schermata fornisce una panoramica visiva delle prestazioni e delle statistiche della tua cache.

- **Nome schermata e posizione menu:** Puoi trovarlo navigando su **Presta Speed Cache** nel menu principale del back office di PrestaShop, quindi selezionando **Dashboard**.
- **Azioni e impostazioni disponibili:**
  - **Metriche di performance:** Visualizza grafici e statistiche su hit della cache, miss della cache, tempi medi di caricamento delle pagine (con e senza cache) e altri indicatori di performance rilevanti.
  - **Stato di salute della cache:** Fornisce una rapida panoramica dello stato di salute del sistema di cache, indicando se ci sono problemi o se sta funzionando in modo ottimale.
  - **Eventi di invalidazione recenti:** Mostra un log degli eventi di invalidazione della cache recenti, aiutandoti a tenere traccia di quando e perché parti della tua cache sono state svuotate.
- **Effetto delle modifiche:** Questa schermata è principalmente per il monitoraggio e la reportistica. Non vengono apportate modifiche dirette alla configurazione della cache qui, ma ti aiuta a capire l'impatto delle tue impostazioni.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Controlla regolarmente la dashboard per assicurarti che la tua cache stia funzionando come previsto. Cerca tassi di hit della cache elevati e tempi di caricamento bassi. Se vedi un calo improvviso degli hit della cache o un aumento dei tempi di caricamento, potrebbe indicare un problema di configurazione o un problema con il tuo server.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Configurazione modulo** | Abilita cache | SÌ | Interruttore principale per la cache. SÌ = negozio più veloce. |
|  | Durata cache (minuti) | 1440 (24 ore) | Per quanto tempo una pagina rimane nella cache. Più alto = meno carico server, potenzialmente contenuto più vecchio. |
|  | Metodo di archiviazione cache | File System | Dove viene memorizzata la cache. File System (facile), Redis/Memcached (più veloce, richiede configurazione server). |
|  | Escludi URL dalla cache | Vuoto | URL che non dovrebbero mai essere memorizzati nella cache (es. pagine altamente dinamiche). |
|  | Warm-up cache | SÌ | Costruisce proattivamente la cache in background. SÌ = più veloce per i primi visitatori. |
|  | Ottimizzazione HTML | SÌ | Minifica l'HTML per dimensioni di pagina più piccole. SÌ = leggero aumento di velocità. |
|  | Abilita blocchi dinamici | SÌ | Consente a contenuti specifici (carrello, login) di rimanere dinamici. SÌ = essenziale per contenuti personalizzati. |
|  | Elenco moduli dinamici | `ps_shoppingcart`, `ps_customeraccountlinks`, ecc. | Moduli che dovrebbero essere sempre dinamici. |
|  | Invalidazione automatica della cache | SÌ | Svuota la cache pertinente alle modifiche del back office. SÌ = contenuto fresco senza intervento manuale. |
|  | Svuota cache all'aggiornamento del prodotto | SÌ | Svuota la cache relativa al prodotto quando i prodotti vengono aggiornati. |
|  | Svuota cache all'aggiornamento della categoria | SÌ | Svuota la cache relativa alla categoria quando le categorie vengono aggiornate. |
|  | Svuota cache all'aggiornamento della pagina CMS | SÌ | Svuota la cache relativa alla pagina CMS quando le pagine CMS vengono aggiornate. |
|  | Abilita modalità debug | NO (SÌ per la risoluzione dei problemi) | Mostra informazioni sulla cache nel front office. |
|  | Abilita debug in tempo reale | SÌ | Fornisce statistiche sulla cache in tempo reale nel BO. |
|  | Abilita SWR (Stale-While-Revalidate) | SÌ | Serve cache obsoleta mentre ricostruisce quella fresca. SÌ = sempre veloce. |
|  | Cache per utenti loggati | SÌ | Memorizza nella cache le pagine per gli utenti loggati. |
|  | Cache per dispositivi mobili | SÌ | Memorizza nella cache versioni separate per i dispositivi mobili. |
|  | Abilita Edge Purge (Varnish/CDN) | NO (SÌ se si usa CDN) | Si integra con CDN/Varnish esterni per lo svuotamento della cache. |
|  | Svuota tutta la cache (pulsante) | Usa quando necessario | Svuota l'intera cache manualmente. |
|  | Esegui warm-up cache (pulsante) | Usa quando necessario | Attiva manualmente la pre-popolazione della cache. |
| **Schermata Gestione cache** | Griglia elenco cache | N/A | Visualizza e consente la gestione delle singole pagine memorizzate nella cache. |
|  | Svuota cache selezionata | N/A | Svuota voci specifiche della cache. |
| **Schermata Dashboard** | Metriche di performance | N/A | Visualizza hit, miss e tempi di caricamento della cache. |
|  | Stato di salute della cache | N/A | Mostra lo stato di salute generale del sistema di caching. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Il mio negozio appare rotto o mostra contenuti vecchi dopo aver abilitato la cache. Cosa devo fare?**
R: Per prima cosa, prova a svuotare l'intera cache utilizzando il pulsante "Svuota tutta la cache" nella configurazione del modulo o nella schermata "Gestione cache". Inoltre, svuota la cache del tuo browser. Se il problema persiste, controlla il tuo "Elenco moduli dinamici" per assicurarti che tutti i moduli che visualizzano contenuti personalizzati o in tempo reale siano inclusi. Disabilita temporaneamente "Ottimizzazione HTML" per vedere se sta causando conflitti.

**D: Il mio carrello non si aggiorna correttamente, o gli utenti a volte appaiono disconnessi.**
R: Questo è quasi sempre dovuto al fatto che il contenuto dinamico non è stato correttamente escluso dalla cache. Vai alla scheda "Blocchi dinamici" e assicurati che moduli come `ps_shoppingcart`, `ps_customeraccountlinks`, `ps_languageselector` e `ps_currencyselector` siano aggiunti all'"Elenco moduli dinamici". Se hai altri moduli personalizzati che visualizzano dati specifici dell'utente, aggiungili anche tu.

**D: Il mio sito web è ancora lento, anche con il modulo abilitato.**
R:

1.  **Controlla la modalità Debug:** Abilita la "Modalità Debug" (nelle Impostazioni avanzate) e naviga nel tuo front office. Mostra che le pagine vengono servite dalla cache ("Cache HIT")? Se vedi "Cache MISS", le pagine non vengono memorizzate nella cache.
2.  **Verifica il tasso di hit della cache:** Controlla la "Dashboard" per il tuo tasso di hit della cache. Se è basso, rivedi le impostazioni "Durata cache" ed "Escludi URL".
3.  **Risorse del server:** Sebbene la cache riduca il carico, il tuo server ha comunque bisogno di risorse adeguate. Controlla il tuo piano di hosting e i log del server per altri colli di bottiglia.
4.  **Altre ottimizzazioni:** La cache è una parte della velocità. Assicurati che le tue immagini siano ottimizzate, che il tuo tema sia efficiente e che non stai eseguendo troppi moduli pesanti e non ottimizzati.

**D: Come mi assicuro che il mio negozio multilingue o multivaluta funzioni correttamente con la cache?**
R: Presta Speed Cache è progettato per gestire negozi multilingue e multivaluta generando voci di cache separate per ogni combinazione. Assicurati che i tuoi moduli di selezione della lingua e della valuta siano aggiunti all'"Elenco moduli dinamici". Se noti problemi, abilita "Cache per utenti loggati" e "Cache per dispositivi mobili" se applicabile, poiché questi possono anche influenzare il modo in cui vengono memorizzate nella cache le diverse versioni delle pagine.

**D: Ho aggiornato un prodotto, ma le vecchie informazioni sono ancora visualizzate nel front office.**
R:

1.  **Invalidazione automatica:** Assicurati che "Invalidazione automatica della cache" e "Svuota cache all'aggiornamento del prodotto" siano abilitati nella scheda "Invalidazione e svuotamento".
2.  **Svuotamento manuale:** Se le impostazioni sono corrette, prova a svuotare manualmente la cache per quella specifica pagina prodotto dalla schermata "Gestione cache", o svuota l'intera cache.
3.  **CDN/Varnish:** Se utilizzi un CDN o Varnish, assicurati che "Abilita Edge Purge" sia configurato correttamente, poiché il tuo CDN potrebbe servire una vecchia versione.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Presta Speed Cache è una soluzione di caching altamente ottimizzata per PrestaShop, che impiega un'architettura sofisticata per offrire velocità senza compromettere i contenuti dinamici. Sfrutta il pattern MVC di PrestaShop sovrascrivendo le classi principali (`Controller`, `FrontController`, `Dispatcher`, `Hook`) per intercettare richieste e risposte, servendo HTML memorizzato nella cache quando disponibile. Utilizza un motore di archiviazione flessibile (File, Redis, Memcached) e implementa funzionalità avanzate come SWR (Stale-While-Revalidate), rendering di blocchi dinamici tramite AJAX e invalidazione intelligente della cache. Il design del modulo si concentra su un overhead minimo e la massima compatibilità, fornendo un livello di caching robusto ed estensibile.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

Questi controller gestiscono specifiche richieste AJAX o attività in background relative alla cache.

- `prestaspeedcache/controllers/front/api.php`
  - **Nome classe e classe genitore:** `PrestaSpeedCacheApiModuleFrontController` estende `ModuleFrontController`.
  - **Responsabilità:** Gestisce le richieste API, principalmente per il recupero di contenuti dinamici. Quando viene servita una pagina memorizzata nella cache e contiene blocchi dinamici, questo controller è responsabile della consegna dell'HTML fresco per tali blocchi tramite AJAX. Riceve parametri che identificano il modulo e l'hook, renderizza il modulo e restituisce l'HTML.
- `prestaspeedcache/controllers/front/cron.php`
  - **Nome classe e classe genitore:** `PrestaSpeedCacheCronModuleFrontController` estende `ModuleFrontController`.
  - **Responsabilità:** Progettato per essere chiamato da un cron job lato server. Attiva attività in background come il warm-up della cache, l'elaborazione della coda di invalidazione e altre operazioni di manutenzione. Questo alleggerisce l'elaborazione pesante dalle richieste degli utenti.
- `prestaspeedcache/controllers/front/dynamic.php`
  - **Nome classe e classe genitore:** `PrestaSpeedCacheDynamicModuleFrontController` estende `ModuleFrontController`.
  - **Responsabilità:** Simile a `api.php`, questo controller gestisce specificamente le richieste per i blocchi di contenuto dinamici che vengono caricati in modo asincrono nelle pagine memorizzate nella cache. Assicura che gli elementi personalizzati come il carrello o le informazioni utente siano sempre aggiornati.
- `prestaspeedcache/controllers/front/index.php`
  - **Nome classe e classe genitore:** `PrestaSpeedCacheIndexModuleFrontController` estende `ModuleFrontController`.
  - **Responsabilità:** Un controller frontale segnaposto o di fallback. In molti moduli, `index.php` in `controllers/front` funge da punto di ingresso predefinito se nessun altro controller specifico viene abbinato. Potrebbe gestire il routing di base a livello di modulo o semplicemente reindirizzare.

#### Controller Admin Back-Office

Questi controller gestiscono la configurazione e i dati del modulo all'interno del Back Office di PrestaShop.

- `prestaspeedcache/controllers/admin/AdminPrestaSpeedCacheController.php`
  - **Nome classe e classe genitore:** `AdminPrestaSpeedCacheController` estende `ModuleAdminController`.
  - **Nome scheda ed entità gestita:** Questo è il controller amministrativo principale per il modulo, che gestisce le voci della cache e fornisce le viste "Gestione cache" e "Dashboard". Gestisce l'elenco, il filtraggio e l'eliminazione delle voci della cache. Non gestisce direttamente un'entità `ObjectModel` specifica ma interagisce con `PscCacheRepository` per le operazioni di cache.
- `prestaspeedcache/controllers/admin/index.php`
  - **Nome classe e classe genitore:** `AdminPrestaSpeedCacheIndexController` estende `ModuleAdminController`.
  - **Nome scheda ed entità gestita:** Simile a `index.php` del front-office, questo è probabilmente un segnaposto o un controller predefinito per la sezione amministrativa del modulo, garantendo un punto di ingresso valido se non viene richiesta alcuna azione specifica.

### 4.3 Classi e modelli principali (`classes/`)

La directory `classes/` del modulo contiene la logica principale, i servizi e le strutture dati.

- `prestaspeedcache/classes/PscAdminChips.php`: Gestisce i componenti dell'interfaccia utente per l'interfaccia di amministrazione.
- `prestaspeedcache/classes/PscAfterDefaults.php`: Gestisce le impostazioni predefinite o le configurazioni post-installazione.
- `prestaspeedcache/classes/PscAutoload.php`: Autoloader personalizzato per le classi del modulo.
- `prestaspeedcache/classes/PscCacheEngine.php`: Il motore di caching principale, che orchestra le operazioni di cache.
- `prestaspeedcache/classes/PscCacheInvalidator.php`: Gestisce la logica per l'invalidazione delle pagine memorizzate nella cache in base alle azioni del back office.
- `prestaspeedcache/classes/PscCacheKey.php`: Genera chiavi uniche per le voci memorizzate nella cache in base all'URL, al contesto, ecc.
- `prestaspeedcache/classes/PscCacheLock.php`: Implementa meccanismi di blocco per prevenire condizioni di gara durante la generazione della cache.
- `prestaspeedcache/classes/PscCacheRepository.php`: Gestisce l'interazione con l'archivio della cache, fornendo un livello di astrazione.
- `prestaspeedcache/classes/PscCacheStorage.php`: Classe base astratta o interfaccia per le implementazioni di archiviazione della cache.
- `prestaspeedcache/classes/PscCacheTags.php`: Gestisce i tag della cache per un'invalidazione granulare (es. tutte le pagine relative all'ID prodotto 123).
- `prestaspeedcache/classes/PscConfig.php`: Gestisce le impostazioni di configurazione del modulo (legge e scrive su `ps_configuration`).
- `prestaspeedcache/classes/PscDynamicBlocks.php`: Logica per identificare e gestire i blocchi di contenuto dinamici.
- `prestaspeedcache/classes/PscDynamicModules.php`: Gestisce l'elenco dei moduli il cui output dovrebbe essere sempre dinamico.
- `prestaspeedcache/classes/PscEdgePurge.php`: Gestisce l'integrazione con sistemi di caching esterni (Varnish, CDN) per lo svuotamento.
- `prestaspeedcache/classes/PscFrontAssign.php`: Gestisce le assegnazioni di variabili Smarty per i template del front-office.
- `prestaspeedcache/classes/PscFrontDebug.php`: Logica per la visualizzazione delle informazioni di debug nel front office.
- `prestaspeedcache/classes/PscHealth.php`: Fornisce metodi per controllare la salute e lo stato del sistema di caching.
- `prestaspeedcache/classes/PscHtmlOptimizer.php`: Implementa la logica di minificazione HTML.
- `prestaspeedcache/classes/PscHttpProbe.php`: Utilizzato per richieste HTTP interne, ad esempio per il warm-up della cache.
- `prestaspeedcache/classes/PscInstaller.php`: Gestisce le routine di installazione e disinstallazione del modulo (tabelle del database, hook, impostazioni di configurazione predefinite).
- `prestaspeedcache/classes/PscInvalidationQueue.php`: Gestisce una coda di pagine da invalidare, spesso elaborata da cron.
- `prestaspeedcache/classes/PscLiveDebug.php`: Fornisce funzionalità di debug e monitoraggio in tempo reale.
- `prestaspeedcache/classes/PscMetrics.php`: Raccoglie e riporta le metriche di performance per la dashboard.
- `prestaspeedcache/classes/PscOps.php`: Metodi di utilità operativa generale.
- `prestaspeedcache/classes/PscPresets.php`: Gestisce configurazioni di caching predefinite o preset.
- `prestaspeedcache/classes/PscRequestGuard.php`: Protegge da richieste dannose o garantisce una corretta gestione delle richieste.
- `prestaspeedcache/classes/PscTiming.php`: Utilità per misurare i tempi di esecuzione.
- `prestaspeedcache/classes/PscTranslate.php`: Gestisce le traduzioni del modulo.
- `prestaspeedcache/classes/PscWarmup.php`: Implementa la logica di warm-up della cache.
- `prestaspeedcache/classes/PscWizard.php`: Guida gli utenti attraverso la configurazione iniziale.
- `prestaspeedcache/classes/storage/PscFileStorage.php`: Implementazione concreta per l'archiviazione della cache basata su file.
- `prestaspeedcache/classes/storage/PscMemcachedStorage.php`: Implementazione concreta per l'archiviazione della cache Memcached.
- `prestaspeedcache/classes/storage/PscRedisStorage.php`: Implementazione concreta per l'archiviazione della cache Redis.
- `prestaspeedcache/classes/storage/PscStorageFactory.php`: Pattern factory per la creazione di istanze di archiviazione della cache appropriate.
- `prestaspeedcache/classes/storage/PscStorageInterface.php`: Interfaccia che definisce i metodi per le implementazioni di archiviazione della cache.

#### Override

Il modulo utilizza gli override per integrarsi profondamente con il comportamento principale di PrestaShop.

- `prestaspeedcache/override/classes/controller/Controller.php`: Sovrascrive la classe base `Controller`, consentendo al modulo di intercettare il processo di rendering sia per il front che per il back office, potenzialmente iniettando logica di caching o marcatori di blocchi dinamici.
- `prestaspeedcache/override/classes/controller/FrontController.php`: Sovrascrive `FrontController` per gestire specificamente le richieste di pagine del front-office, consentendo al modulo di servire contenuti memorizzati nella cache o preparare le pagine per la memorizzazione nella cache.
- `prestaspeedcache/override/classes/Dispatcher.php`: Sovrascrive il `Dispatcher` per controllare come gli URL vengono instradati ed elaborati, potenzialmente reindirizzando a contenuti memorizzati nella cache o attivando la generazione della cache.
- `prestaspeedcache/override/classes/Hook.php`: Sovrascrive la classe `Hook` per consentire il rendering dinamico dei moduli all'interno delle pagine memorizzate nella cache, garantendo che specifici hook vengano sempre eseguiti freschi.

### 4.4 Risorse JavaScript (`views/js/`)

Questi script migliorano l'esperienza utente sia nel front che nel back office.

- `prestaspeedcache/views/js/admin.js`:
  - **Ambito:** Back-office.
  - **Dettagli:** Gestisce gli elementi interattivi nella configurazione amministrativa del modulo, come il cambio di scheda, l'invio di moduli, le chiamate AJAX per svuotare la cache, eseguire il warm-up e gli aggiornamenti dinamici alla dashboard o all'elenco della cache.
- `prestaspeedcache/views/js/after/lang-currency.js`:
  - **Ambito:** Front-office.
  - **Dettagli:** Probabilmente un piccolo script eseguito dopo il caricamento della pagina principale, specificamente progettato per garantire che i selettori di lingua e valuta (che sono spesso dinamici) funzionino correttamente in un contesto di pagina memorizzata nella cache. Potrebbe reinizializzare il loro comportamento o assicurare che il loro stato sia coerente.
- `prestaspeedcache/views/js/dynamic.js`:
  - **Ambito:** Front-office.
  - **Dettagli:** Questo è uno script critico per i blocchi dinamici. Identifica i segnaposto per i contenuti dinamici all'interno di una pagina memorizzata nella cache, effettua richieste AJAX (ai controller `api.php` o `dynamic.php`) per recuperare l'HTML fresco per tali blocchi e quindi inietta il contenuto nel DOM. Assicura che elementi come il carrello, lo stato di accesso, ecc., siano sempre aggiornati.
- `prestaspeedcache/views/js/fo_debug.js`:
  - **Ambito:** Front-office (solo per amministratori quando la modalità debug è abilitata).
  - **Dettagli:** Visualizza l'overlay di debug della cache nel front office. Recupera le informazioni sullo stato della cache (hit/miss, timestamp, ecc.) e le renderizza in un elemento visibile e non intrusivo per gli amministratori.
- `prestaspeedcache/views/js/psc-dom-mock.js`:
  - **Ambito:** Front-office.
  - **Dettagli:** Potenzialmente uno script di utilità che fornisce un leggero livello di manipolazione o mocking del DOM, possibilmente utilizzato durante il processo di iniezione di blocchi dinamici per garantire la compatibilità o ottimizzare il rendering.

### 4.5 Fogli di stile CSS (`views/css/`)

- `prestaspeedcache/views/css/admin.css`:
  - **Ambito:** Stile del modulo di amministrazione del back-office.
  - **Dettagli:** Stila le pagine di configurazione del modulo, la dashboard e le griglie di gestione della cache. Garantisce un'interfaccia coerente e user-friendly all'interno del back office di PrestaShop.
  - **Selettori di classe CSS chiave:** `prestaspeedcache-dashboard`, `prestaspeedcache-config-form`, `prestaspeedcache-table`, `psc-debug-overlay`.

### 4.6 Struttura dei template Smarty (`views/templates/`)

#### Template Admin (`views/templates/admin/`)

Questi template sono utilizzati per l'interfaccia del back-office del modulo.

- `prestaspeedcache/views/templates/admin/cache_list.tpl`: Renderizza la tabella e l'interfaccia per elencare e gestire le pagine memorizzate nella cache.
- `prestaspeedcache/views/templates/admin/configure.tpl`: Il modulo di configurazione principale per il modulo, contenente tutte le impostazioni descritte nella Sezione 4.1.
- `prestaspeedcache/views/templates/admin/dashboard.tpl`: Visualizza le metriche di performance, i grafici e lo stato di salute della cache.
- `prestaspeedcache/views/templates/admin/dynamic_modules.tpl`: L'interfaccia per selezionare e gestire i moduli che dovrebbero essere renderizzati dinamicamente.
- `prestaspeedcache/views/templates/admin/live_debug.tpl`: Renderizza il pannello di informazioni di debug in tempo reale nel back office.
- `prestaspeedcache/views/templates/admin/ops.tpl`: Probabilmente contiene template per strumenti o azioni operative (es. svuotamento manuale della cache, warm-up).
- `prestaspeedcache/views/templates/admin/tabs.tpl`: Renderizza la struttura di navigazione a schede per le pagine di configurazione del modulo.
- `prestaspeedcache/views/templates/admin/wizard.tpl`: Template per la procedura guidata di configurazione iniziale, che guida gli utenti attraverso la configurazione di base.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

Il modulo utilizza principalmente la tabella `ps_configuration` di PrestaShop per le sue impostazioni. Per l'archiviazione della cache, utilizza il file system o servizi esterni (Redis/Memcached). Potrebbe creare tabelle personalizzate per:

- `ps_prestaspeedcache_cache_tags`: Memorizza le relazioni tra le pagine memorizzate nella cache e i loro tag associati (es. ID prodotto, ID categoria) per un'invalidazione efficiente.
- `ps_prestaspeedcache_invalidation_queue`: Memorizza un elenco di pagine o tag che devono essere invalidati, elaborati in modo asincrono.
- `ps_prestaspeedcache_metrics`: Memorizza le metriche di performance per la dashboard.

#### Tabella degli hook registrati

Il modulo registra vari hook per integrarsi con il ciclo di vita di PrestaShop.

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Prima che il contenuto della pagina venga renderizzato nell'intestazione. | Iniezione di JavaScript del front-office (es. `dynamic.js`, `fo_debug.js`), impostazione del contesto iniziale della cache. |
| `displayFooter` | Prima del tag di chiusura `</body>`. | Iniezione di script aggiuntivi, informazioni di debug o finalizzazione delle operazioni di cache. |
| `displayLeftColumn` | Nella colonna sinistra del tema. | Potenzialmente utilizzato per il rendering dinamico del modulo se un modulo nella colonna sinistra è contrassegnato come dinamico. |
| `displayRightColumn` | Nella colonna destra del tema. | Potenzialmente utilizzato per il rendering dinamico del modulo se un modulo nella colonna destra è contrassegnato come dinamico. |
| `displayProductAdditionalInfo` | Nella pagina del prodotto, sotto la descrizione del prodotto. | Se un modulo agganciato qui è dinamico, il suo contenuto verrà recuperato separatamente. |
| `actionFrontControllerSetMedia` | Dopo che i media (JS/CSS) sono stati impostati dal controller frontale. | Aggiunta di JS/CSS specifici del modulo alla pagina. |
| `actionFrontControllerInit` | All'inizio dell'esecuzione di un controller frontale. | Intercettazione delle richieste per verificare la presenza di contenuti memorizzati nella cache o preparare la memorizzazione nella cache. |
| `actionDispatcherBefore` | Prima che il dispatcher elabori la richiesta. | Intercettazione anticipata per servire contenuti memorizzati nella cache o bypassare il dispatching. |
| `actionDispatcherAfter` | Dopo che il dispatcher ha elaborato la richiesta. | Finalizzazione della generazione della cache per la pagina corrente. |
| `actionObjectUpdate` | Quando qualsiasi `ObjectModel` viene aggiornato (es. Prodotto, Categoria, CMS). | Attivazione dell'invalidazione della cache per le pagine interessate. |
| `actionObjectAdd` | Quando qualsiasi `ObjectModel` viene aggiunto. | Attivazione dell'invalidazione della cache per le pagine potenzialmente interessate. |
| `actionObjectDelete` | Quando qualsiasi `ObjectModel` viene eliminato. | Attivazione dell'invalidazione della cache per le pagine interessate. |
| `actionProductUpdate` | Specifico per gli aggiornamenti dei prodotti. | Invalidazione granulare della cache per le pagine dei prodotti. |
| `actionCategoryUpdate` | Specifico per gli aggiornamenti delle categorie. | Invalidazione granulare della cache per le pagine delle categorie. |
| `actionCmsUpdate` | Specifico per gli aggiornamenti delle pagine CMS. | Invalidazione granulare della cache per le pagine CMS. |
| `actionClearCache` | Quando la cache nativa di PrestaShop viene svuotata. | Sincronizzazione dello svuotamento della cache del modulo con quello di PrestaShop. |
| `actionModuleInstall` | Quando un modulo viene installato. | Potenzialmente svuotamento della cache o aggiornamento dell'elenco dei moduli dinamici. |
| `actionModuleUninstall` | Quando un modulo viene disinstallato. | Svuotamento della cache o rimozione del modulo dall'elenco dinamico. |
| `actionAdminControllerSetMedia` | Nei controller di amministrazione, dopo che i media sono stati impostati. | Iniezione di JS/CSS specifici dell'amministrazione. |
| `actionAdminControllerPreProcess` | Prima che un controller di amministrazione elabori la sua richiesta. | Impostazione del contesto di amministrazione per il modulo. |
| `actionAdminControllerPostProcess` | Dopo che un controller di amministrazione elabora la sua richiesta. | Gestione della post-elaborazione per le azioni di amministrazione. |
| `actionOutputHTMLBefore` | Prima che l'output HTML finale venga inviato al browser. | Esecuzione dell'ottimizzazione HTML (minificazione). |
| `actionOutputHTMLAfter` | Dopo che l'output HTML finale è stato inviato. | Finalizzazione dell'archiviazione della cache. |
| `actionAjaxDie` | Quando una richiesta AJAX chiama `die()`. | Garanzia di una corretta gestione della cache per le risposte AJAX. |
| `actionGetContent` | Per la pagina di configurazione principale del modulo. | Rendering del modulo di configurazione del modulo. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a fornire assistenza completa per garantire che il modulo Presta Speed Cache funzioni in modo ottimale.
