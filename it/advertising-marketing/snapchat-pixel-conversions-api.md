---
title: "Snapchat Pixel & Conversions API - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Snapchat Pixel & Conversions API di MyPresta.eu."
sidebar:
  label: "Snapchat Pixel & Conversions API - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Snapchat Pixel & Conversions API su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/snapchat-pixel-conversions-api.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/snapchat-pixel-conversions-api/)
>
> ---


# Snapchat Pixel & Conversions API

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di Hosting**: Sono richieste estensioni PHP standard (cURL, JSON, OpenSSL). Queste sono tipicamente abilitate di default nella maggior parte degli ambienti di hosting moderni.

## 2. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale dove imposterai il tuo Snapchat Pixel e la Conversions API. Il modulo fornisce un'interfaccia user-friendly con varie sezioni per guidarti attraverso la configurazione.

#### **1. Impostazioni Generali e Modalità di Monitoraggio**

-   **Modalità di Monitoraggio:**

    *   **Cosa fa questa impostazione:** Determina come il tuo negozio invia i dati a Snapchat. Puoi scegliere tra lato client (Pixel), lato server (Conversions API) o un approccio ibrido.
    *   **Effetto della modifica di questa impostazione:**
        *   *Solo Pixel:* Solo lo Snap Pixel (codice JavaScript nel browser) traccerà gli eventi. Questo è più semplice ma più suscettibile agli ad blocker e alle restrizioni del browser.
        *   *Solo Conversions API:* Verrà utilizzato solo il monitoraggio lato server. Questo è più affidabile per la privacy e l'accuratezza dei dati ma richiede una robusta configurazione del server.
        *   *Ibrido (Consigliato):* Sia Pixel che CAPI tracceranno gli eventi. Il modulo deduplica automaticamente gli eventi utilizzando un `event_id` condiviso, garantendo una segnalazione accurata e massimizzando l'acquisizione dei dati. Questa è generalmente l'opzione più robusta e consigliata.
    *   **Valore consigliato:** `Ibrido`
    *   **Scenario / esempio del commerciante:** Se stai appena iniziando, "Solo Pixel" è veloce. Per una pubblicità seria, "Ibrido" ti offre il meglio di entrambi i mondi, assicurandoti di acquisire quanti più dati accurati possibile per l'ottimizzazione della campagna.
-   **ID Pixel Snap:**

    *   **Cosa fa questa impostazione:** Questo è il tuo identificatore unico per il tuo Snap Pixel. Indica a Snapchat a quale account pubblicitario associare gli eventi tracciati.
    *   **Effetto della modifica di questa impostazione:** Se errato o vuoto, non si verificherà alcun monitoraggio lato client e i tuoi annunci Snapchat non saranno in grado di tracciare i visitatori del sito web o le conversioni.
    *   **Valore consigliato:** Il tuo ID Pixel Snap (es. `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`). Puoi trovarlo nel tuo Snapchat Ads Manager.
    *   **Scenario / esempio del commerciante:** Hai creato un account pubblicitario su Snapchat e devi collegare il tuo negozio ad esso. Inserisci qui l'ID Pixel fornito da Snapchat.
-   **Token API Conversioni:**

    *   **Cosa fa questa impostazione:** Questo è un token sicuro che consente al tuo server di inviare dati direttamente alla Conversions API di Snapchat. Autentica le tue richieste lato server.
    *   **Effetto della modifica di questa impostazione:** Se errato o vuoto, non si verificherà alcun monitoraggio lato server. Ciò significa che perdi i vantaggi di maggiore affidabilità e privacy della CAPI.
    *   **Valore consigliato:** Il tuo Token API Conversioni. Lo generi nel tuo Snapchat Ads Manager.
    *   **Scenario / esempio del commerciante:** Per garantire che i tuoi dati di acquisto vengano inviati in modo affidabile a Snapchat anche se un cliente utilizza un ad blocker, dovrai configurare e inserire qui il tuo token CAPI.

#### **2. Monitoraggio Eventi e Qualità dei Dati**

-   **Abilita Corrispondenza Avanzata:**

    *   **Cosa fa questa impostazione:** Consente al modulo di inviare dati aggiuntivi sui clienti (come email, numero di telefono, nome) a Snapchat, con hash sicuro, per migliorare la corrispondenza degli eventi e la costruzione del pubblico.
    *   **Effetto della modifica di questa impostazione:**
        *   *Abilitato:* Snapchat può abbinare in modo più accurato i visitatori del sito web ai loro profili Snapchat, migliorando il targeting del pubblico e l'attribuzione degli annunci.
        *   *Disabilitato:* Vengono inviati meno dati, riducendo potenzialmente l'accuratezza della corrispondenza del pubblico e l'ottimizzazione della campagna.
    *   **Valore consigliato:** `SÌ` (a meno che tu non abbia severe preoccupazioni sulla privacy che prevalgono sui benefici).
    *   **Scenario / esempio del commerciante:** Vuoi che Snapchat sia il più efficace possibile nel trovare clienti simili a quelli esistenti. Abilitare questa opzione aiuta Snapchat a identificare gli utenti in modo più preciso.
-   **Integrazione Gestione Consenso:**

    *   **Cosa fa questa impostazione:** Si integra con i moduli di consenso ai cookie più diffusi (es. moduli GDPR) per garantire che il monitoraggio di Snapchat avvenga solo dopo che un cliente ha dato il suo esplicito consenso.
    *   **Effetto della modifica di questa impostazione:**
        *   *Abilitato:* Il modulo attenderà il consenso prima di inizializzare lo Snap Pixel o inviare eventi CAPI che richiedono dati utente.
        *   *Disabilitato:* Il monitoraggio avverrà indipendentemente dal consenso dell'utente, il che potrebbe portare a problemi di conformità alla privacy in alcune regioni.
    *   **Valore consigliato:** `SÌ` (altamente raccomandato per GDPR, CCPA e altre normative sulla privacy).
    *   **Scenario / esempio del commerciante:** Il tuo negozio opera nell'UE e deve essere conforme al GDPR. Abilitare questa opzione garantisce che tu tracci solo gli utenti che hanno accettato la tua politica sui cookie.
-   **Tipo ID Prodotto per Corrispondenza Catalogo:**

    *   **Cosa fa questa impostazione:** Specifica quale identificatore di prodotto (es. ID Prodotto, Riferimento Prodotto, EAN/UPC) il modulo deve inviare a Snapchat per la corrispondenza del catalogo prodotti. Questo è cruciale per gli annunci dinamici di prodotti.
    *   **Effetto della modifica di questa impostazione:** Se il tipo di ID inviato dal modulo non corrisponde agli ID nel tuo Catalogo Prodotti Snapchat, i tuoi annunci dinamici non visualizzeranno i prodotti corretti.
    *   **Valore consigliato:** Scegli il tipo di ID che utilizzi in modo coerente nel tuo Catalogo Prodotti Snapchat. Spesso, `ID Prodotto` o `Riferimento Prodotto` sono buone scelte.
    *   **Scenario / esempio del commerciante:** Stai eseguendo annunci di retargeting dinamici su Snapchat. Se il tuo catalogo prodotti utilizza il "Riferimento Prodotto" come identificatore unico, devi selezionare "Riferimento Prodotto" qui affinché gli annunci mostrino i prodotti giusti ai clienti.
-   **Abilita Modalità Debug:**

    *   **Cosa fa questa impostazione:** Attiva una modalità speciale che visualizza informazioni dettagliate sugli eventi inviati a Snapchat direttamente nella console per sviluppatori del tuo browser.
    *   **Effetto della modifica di questa impostazione:**
        *   *Abilitato:* Vedrai un feedback in tempo reale su quali dati vengono inviati, aiutandoti a risolvere i problemi e verificare la tua configurazione. Questo è visibile solo a te (o a chiunque abbia gli strumenti per sviluppatori aperti).
        *   *Disabilitato:* Non vengono visualizzate informazioni di debug.
    *   **Valore consigliato:** `NO` per i negozi live. `SÌ` durante la configurazione iniziale e la risoluzione dei problemi.
    *   **Scenario / esempio del commerciante:** Dopo aver installato il modulo, vuoi confermare che gli eventi "Aggiungi al Carrello" vengono attivati correttamente. Abiliti la modalità debug, aggiungi un prodotto al carrello e controlli la console per i dettagli dell'evento.

#### **3. Funzionalità Avanzate**

-   **Ghost Collector (Corrispondenza ScCid):**

    *   **Cosa fa questa impostazione:** Migliora l'accuratezza della corrispondenza degli utenti tra diverse sessioni e dispositivi creando un identificatore unico e anonimo (ScCid) e memorizzandolo in un cookie di prima parte.
    *   **Effetto della modifica di questa impostazione:**
        *   *Abilitato:* Migliore attribuzione e costruzione del pubblico, specialmente in scenari in cui i cookie di terze parti sono limitati.
        *   *Disabilitato:* La capacità di Snapchat di tracciare gli utenti tra le sessioni potrebbe essere meno accurata.
    *   **Valore consigliato:** `SÌ`
    *   **Scenario / esempio del commerciante:** Un cliente visita il tuo negozio, se ne va e torna più tardi da un dispositivo diverso. Ghost Collector aiuta Snapchat a riconoscerli come lo stesso utente, migliorando i tuoi sforzi di retargeting.
-   **Domini Linker (Monitoraggio Cross-Dominio):**

    *   **Cosa fa questa impostazione:** Ti consente di specificare domini aggiuntivi (es. un blog separato, un sottodominio per prodotti specifici) dove desideri anche tracciare gli eventi Snapchat e collegare le sessioni utente.
    *   **Effetto della modifica di questa impostazione:**
        *   *Configurato:* Snapchat può tracciare il percorso di un utente senza soluzione di continuità tra il tuo negozio principale e i domini collegati specificati.
        *   *Vuoto:* Il monitoraggio è limitato solo al dominio del tuo negozio principale.
    *   **Valore consigliato:** Lascia vuoto a meno che tu non abbia più domini/sottodomini che necessitano di monitoraggio cross-dominio.
    *   **Scenario / esempio del commerciante:** Hai il tuo negozio principale su `miostore.com` e un blog separato su `blog.miostore.com`. Vuoi tracciare gli utenti che visitano entrambi. Aggiungeresti `blog.miostore.com` a questa impostazione.
-   **URL Cron Job per Sincronizzazione CAPI:**

    *   **Cosa fa questa impostazione:** Fornisce un URL unico che puoi impostare come cron job sul tuo server. Questo cron job invia periodicamente a Snapchat gli eventi lato server in coda, garantendo che i dati vengano consegnati anche in caso di problemi di rete temporanei.
    *   **Effetto della modifica di questa impostazione:** Questo è un campo di sola lettura. L'impostazione del cron job garantisce una consegna affidabile e asincrona degli eventi CAPI. Se non configurato, gli eventi CAPI potrebbero essere inviati solo in tempo reale o in base ad azioni utente specifiche, potenzialmente perdendo alcuni dati se l'invio in tempo reale fallisce.
    *   **Valore consigliato:** Imposta un cron job sul tuo server per eseguire questo URL ogni 5-15 minuti.
    *   **Scenario / esempio del commerciante:** Per garantire che tutti i tuoi dati di acquisto vengano inviati a Snapchat, anche se un cliente chiude il browser immediatamente dopo l'acquisto, imposti un cron job per elaborare regolarmente eventuali eventi CAPI in sospeso.

#### **4. Qualità dei Dati e Punteggio di Salute**

Questa sezione fornisce tipicamente informazioni e raccomandazioni di sola lettura basate sulla tua configurazione attuale e sugli eventi tracciati.

-   **Punteggio di Salute:**

    *   **Cosa fa questa impostazione:** Visualizza un punteggio complessivo che indica la qualità e la completezza della tua configurazione di monitoraggio Snapchat. Un punteggio più alto significa dati migliori.
    *   **Effetto della modifica di questa impostazione:** Questo è uno strumento diagnostico. Migliorare la tua configurazione (es. abilitando CAPI, corrispondenza avanzata) aumenterà questo punteggio.
    *   **Valore consigliato:** Punta al punteggio più alto possibile.
    *   **Scenario / esempio del commerciante:** Il tuo punteggio di salute è del 60%. Il modulo potrebbe suggerire di abilitare la Corrispondenza Avanzata per migliorarlo, indicando una potenziale area per una migliore qualità dei dati.
-   **Coach Qualità Dati:**

    *   **Cosa fa questa impostazione:** Offre raccomandazioni e avvisi specifici sulla tua configurazione di monitoraggio, come token CAPI mancanti, tipi di ID prodotto non configurati o potenziali problemi di consenso.
    *   **Effetto della modifica di questa impostazione:** Questo è uno strumento diagnostico. Affrontare le raccomandazioni migliorerà l'accuratezza del tuo monitoraggio.
    *   **Valore consigliato:** Rivedi e agisci su tutte le raccomandazioni.
    *   **Scenario / esempio del commerciante:** Il coach ti dice che il tuo "Tipo ID Prodotto" non corrisponde al tuo catalogo. Tornerai quindi alle impostazioni e lo regolerai.
-   **Dottore Catalogo:**

    *   **Cosa fa questa impostazione:** Ti aiuta a diagnosticare problemi relativi al tuo catalogo prodotti e a come viene abbinato agli eventi Snapchat. Controlla la coerenza negli identificatori di prodotto.
    *   **Effetto della modifica di questa impostazione:** Questo è uno strumento diagnostico. Risolvere i problemi qui garantisce che i tuoi annunci dinamici di prodotti funzionino correttamente.
    *   **Valore consigliato:** Usa questo strumento se riscontri problemi con gli annunci dinamici di prodotti che mostrano articoli errati.
    *   **Scenario / esempio del commerciante:** I tuoi annunci dinamici mostrano prodotti generici invece di quelli visualizzati dai clienti. Il Dottore Catalogo potrebbe rivelare che i tuoi ID prodotto sono incoerenti.

#### **5. Statistiche in Tempo Reale ed Eventi Recenti**

-   **Statistiche in Tempo Reale:**

    *   **Cosa fa questa impostazione:** Fornisce una panoramica in tempo reale degli eventi inviati a Snapchat (es. Visualizzazioni Pagina, Aggiungi al Carrello, Acquisti).
    *   **Effetto della modifica di questa impostazione:** Questo è uno strumento di monitoraggio. Ti aiuta a verificare rapidamente se gli eventi vengono attivati come previsto.
    *   **Valore consigliato:** Controlla regolarmente questa sezione per assicurarti che il tuo monitoraggio sia attivo.
    *   **Scenario / esempio del commerciante:** Lanci un nuovo prodotto e vuoi vedere se gli eventi "Visualizzazione Contenuto" vengono tracciati immediatamente. Controlli le statistiche in tempo reale.
-   **Registro Eventi Recenti:**

    *   **Cosa fa questa impostazione:** Mostra un registro degli eventi più recenti inviati a Snapchat, inclusi dettagli come tipo di evento, timestamp e se è stato inviato tramite Pixel o CAPI.
    *   **Effetto della modifica di questa impostazione:** Questo è uno strumento di registrazione dettagliato per la verifica e la risoluzione dei problemi.
    *   **Valore consigliato:** Usalo per approfondire eventi specifici se sospetti un problema.
    *   **Scenario / esempio del commerciante:** Un cliente segnala un problema con un acquisto e vuoi confermare se l'evento "Acquisto" è stato inviato con successo a Snapchat per quell'ordine.

### 2.2 Schermate di Amministrazione Dedicate e Viste Controller

#### **AdminMysnapapiAjaxController (Back Office > Moduli > Snapchat Pixel & Conversions API > [Chiamate AJAX Interne])**

Questo controller non è direttamente accessibile tramite una voce di menu ma gestisce le richieste AJAX in background dalla pagina di configurazione del modulo. È responsabile di:

-   **Nome Schermata e Posizione Menu:** Non direttamente visibile nel menu. Elabora le richieste avviate dalla pagina di configurazione principale del modulo.
-   **Azioni e Impostazioni Disponibili:** Gestisce il caricamento dinamico dei dati per le sezioni "Statistiche in Tempo Reale", "Eventi Recenti", "Punteggio di Salute", "Coach Qualità Dati" e "Dottore Catalogo". Gestisce anche il salvataggio di impostazioni di configurazione specifiche senza un ricaricamento completo della pagina.
-   **Effetto delle modifiche:** Quando interagisci con elementi dinamici nella pagina di configurazione principale (es. aggiornare le statistiche in tempo reale, salvare un'impostazione secondaria specifica), questo controller elabora la richiesta e aggiorna le informazioni visualizzate o salva i dati.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** I commercianti non interagiscono direttamente con questo controller. La sua funzionalità è incorporata nella pagina di configurazione principale del modulo.

#### **index.php (mysnapapi/controllers/admin/index.php)**

Questo file è un segnaposto e tipicamente non contiene funzionalità dirette o un'interfaccia utente. In PrestaShop, i file `index.php` all'interno delle directory dei controller spesso servono a prevenire l'elenco delle directory piuttosto che fornire una logica specifica del controller.

-   **Nome Schermata e Posizione Menu:** Non una schermata diretta.
-   **Azioni e Impostazioni Disponibili:** Nessuna.
-   **Effetto delle modifiche:** Nessuna interazione o effetto diretto per il commerciante.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Nessuna interazione richiesta.

### 2.3 Tabella di Riferimento Rapido della Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Pagina di Configurazione Modulo** | Modalità di Monitoraggio | Ibrido | Definisce come vengono inviati i dati (Pixel, CAPI o entrambi). Ibrido è il più robusto. |
| | ID Pixel Snap | Il tuo ID Pixel | ID unico per il monitoraggio lato client. Essenziale per Pixel. |
| | Token API Conversioni | Il tuo Token CAPI | Token sicuro per il monitoraggio lato server. Essenziale per CAPI. |
| | Abilita Corrispondenza Avanzata | SÌ | Migliora la corrispondenza utente per un migliore targeting degli annunci. |
| | Integrazione Gestione Consenso | SÌ | Garantisce la conformità alla privacy rispettando il consenso dell'utente. |
| | Tipo ID Prodotto per Corrispondenza Catalogo | ID Prodotto / Riferimento | Corrisponde agli identificatori di prodotto per gli annunci dinamici. |
| | Abilita Modalità Debug | NO (SÌ per la configurazione) | Visualizza le informazioni di monitoraggio nella console del browser per la risoluzione dei problemi. |
| | Ghost Collector (Corrispondenza ScCid) | SÌ | Migliora la corrispondenza utente tra sessioni/dispositivi. |
| | Domini Linker | Vuoto (o i tuoi domini) | Abilita il monitoraggio cross-dominio per più siti correlati. |
| | URL Cron Job per Sincronizzazione CAPI | (Sola lettura) | URL per la consegna degli eventi lato server, impostato come cron job. |
| | Punteggio di Salute | (Diagnostico) | Qualità complessiva della tua configurazione di monitoraggio. Punta a un punteggio elevato. |
| | Coach Qualità Dati | (Diagnostico) | Raccomandazioni specifiche per migliorare la qualità dei dati. |
| | Dottore Catalogo | (Diagnostico) | Diagnostica problemi con la corrispondenza del catalogo prodotti. |
| | Statistiche in Tempo Reale | (Monitoraggio) | Panoramica in tempo reale degli eventi tracciati. |
| | Registro Eventi Recenti | (Monitoraggio) | Registro dettagliato degli eventi recenti per la verifica. |

## 3. Risoluzione dei Problemi per il Commerciante e Domande Frequenti (FAQ)

**D1: I miei annunci Snapchat non mostrano conversioni, ma so che sto ottenendo vendite. Cosa c'è che non va?**
R1:

-   **Controlla ID Pixel e Token CAPI:** Ricontrolla che il tuo ID Pixel Snap e il Token API Conversioni siano stati inseriti correttamente nella configurazione del modulo. Anche un singolo errore di battitura impedirà il monitoraggio.
-   **Modalità di Monitoraggio:** Assicurati di utilizzare "Ibrido" o almeno "Solo Pixel" se ti aspetti un monitoraggio lato client.
-   **Modalità Debug:** Abilita la "Modalità Debug" nelle impostazioni del modulo e apri la console per sviluppatori del tuo browser (F12). Naviga nel tuo negozio ed esegui azioni (visualizza prodotto, aggiungi al carrello, completa un acquisto di prova). Cerca gli eventi Snapchat registrati nella console. Se non li vedi, c'è un problema di configurazione fondamentale.
-   **Svuota Cache:** Svuota sempre la cache di PrestaShop (Parametri Avanzati > Prestazioni) dopo aver apportato modifiche alla configurazione del modulo.
-   **Ad Blocker:** Testa con una finestra del browser in incognito/privata senza ad blocker abilitati, poiché possono interferire con il monitoraggio dei pixel.

**D2: Ho abilitato il modulo, ma sono preoccupato per la conformità GDPR/CCPA. Come aiuta questo modulo?**
R2:

-   Il modulo include un'impostazione **"Integrazione Gestione Consenso"**. Quando abilitata, si integrerà con la tua soluzione di consenso ai cookie esistente (es. un modulo GDPR). Ciò significa che il monitoraggio di Snapchat si attiverà solo *dopo* che un utente avrà dato il suo esplicito consenso tramite il banner di consenso del tuo negozio.
-   **Azione:** Assicurati che questa impostazione sia abilitata e che tu abbia un modulo di consenso ai cookie funzionante sul tuo negozio PrestaShop.

**D3: I miei annunci dinamici di prodotti su Snapchat mostrano i prodotti sbagliati o non funzionano affatto.**
R3:

-   **Tipo ID Prodotto:** Vai alla configurazione del modulo e verifica l'impostazione **"Tipo ID Prodotto per Corrispondenza Catalogo"**. Questo deve corrispondere esattamente all'identificatore unico che stai utilizzando nel tuo Catalogo Prodotti Snapchat (es. se il tuo catalogo usa `reference`, seleziona `Riferimento Prodotto` qui).
-   **Sincronizzazione Catalogo:** Assicurati che il tuo catalogo prodotti sia correttamente sincronizzato e aggiornato nel tuo Snapchat Ads Manager. Il modulo invia gli ID corretti, ma Snapchat deve avere quegli ID nel suo catalogo.
-   **Dottore Catalogo:** Utilizza lo strumento "Dottore Catalogo" all'interno della configurazione del modulo per diagnosticare potenziali incongruenze tra i dati dei prodotti del tuo negozio e ciò che Snapchat si aspetta.

**D4: Vedo eventi duplicati nel mio Snapchat Ads Manager (es. due eventi "Acquisto" per un ordine).**
R4:

-   Questo di solito accade se stai utilizzando sia Pixel che CAPI senza una corretta deduplicazione.
-   **Azione:** Assicurati che la tua "Modalità di Monitoraggio" sia impostata su **"Ibrido"**. Questo modulo è progettato per gestire automaticamente la deduplicazione degli eventi quando è in esecuzione in modalità Ibrida generando un `event_id` condiviso per gli eventi lato client e lato server. Se vedi duplicati, verifica che il modulo sia configurato correttamente per la modalità Ibrida e che nessun altro codice di monitoraggio Snapchat sia presente sul tuo sito.

**D5: Le sezioni "Statistiche in Tempo Reale" o "Punteggio di Salute" nella pagina di configurazione del modulo non si aggiornano o non mostrano dati.**
R5:

-   **Problemi AJAX:** Questo di solito indica un problema con la capacità del tuo server di elaborare le richieste AJAX o un errore JavaScript nel tuo back office.
-   **Console del Browser:** Apri la console per sviluppatori del tuo browser (F12) mentre sei nella pagina di configurazione del modulo e controlla eventuali messaggi di errore rossi nella scheda "Console".
-   **Log del Server:** Controlla i log degli errori PHP del tuo server per eventuali errori correlati.
-   **Modalità Debug PrestaShop:** Abilita temporaneamente la modalità debug di PrestaShop (Parametri Avanzati > Prestazioni > Modalità debug: SÌ) per vedere se compaiono errori più dettagliati.
-   **Contatta il Supporto:** Se non riesci a risolverlo, raccogli eventuali messaggi di errore e contatta il supporto MyPresta.eu.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'Architettura

Il modulo `Snapchat Pixel & Conversions API` (`mysnapapi`) implementa una robusta soluzione di monitoraggio che sfrutta sia il monitoraggio degli eventi lato client (Snap Pixel) che lato server (Conversions API - CAPI). Segue un approccio modulare e orientato agli oggetti, aderendo al pattern MVC di PrestaShop ove applicabile.

Componenti architettonici chiave:

-   **Monitoraggio Ibrido:** Il modulo supporta la modalità Solo Pixel, Solo CAPI e una modalità Ibrida consigliata. In modalità Ibrida, genera un `event_id` unico per ogni evento, condiviso tra i payload Pixel e CAPI per garantire la deduplicazione lato Snapchat.
-   **Mappatura Eventi:** Una mappatura completa delle azioni di PrestaShop (es. `actionCartSave`, `actionValidateOrder`) agli eventi Snapchat standard (`ADD_CART`, `PURCHASE`, `VIEW_CONTENT`, `PAGE_VIEW`).
-   **Gestione del Consenso:** Punti di integrazione per moduli di consenso popolari per garantire la conformità GDPR/CCPA.
-   **Strumenti di Qualità dei Dati:** Diagnostici integrati come Punteggio di Salute, Coach Qualità Dati e Dottore Catalogo per aiutare nella configurazione e nella risoluzione dei problemi.
-   **CAPI Asincrona:** Gli eventi CAPI sono spesso accodati e inviati in modo asincrono, in tempo reale o tramite un cron job, per migliorare le prestazioni e l'affidabilità.
-   **Dati di Prima Parte:** Utilizza un "Ghost Collector" per creare cookie di prima parte per la corrispondenza `ScCid`, migliorando l'identificazione dell'utente in un ambiente attento alla privacy.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

-   `mysnapapi/controllers/front/ajax.php`
    *   **Nome classe e classe padre:** `MysnapapiAjaxModuleFrontController` estende `ModuleFrontController`.
    *   **Responsabilità:** Gestisce varie richieste AJAX dal front-office, principalmente per la funzionalità "Ghost Collector" (ScCid). Potrebbe raccogliere dati utente anonimi o aggiornare i cookie di prima parte senza un ricaricamento completo della pagina.
-   `mysnapapi/controllers/front/cron.php`
    *   **Nome classe e classe padre:** `MysnapapiCronModuleFrontController` estende `ModuleFrontController`.
    *   **Responsabilità:** Questo controller è progettato per essere chiamato da un cron job esterno. Il suo ruolo principale è elaborare eventuali eventi lato server (CAPI) in coda che non sono stati inviati in tempo reale. Garantisce che tutti i dati CAPI vengano infine consegnati a Snapchat, migliorando l'affidabilità.
-   `mysnapapi/controllers/front/index.php`
    *   **Nome classe e classe padre:** `MysnapapiIndexModuleFrontController` estende `ModuleFrontController`.
    *   **Responsabilità:** Tipicamente un segnaposto o un punto di ingresso predefinito. Potrebbe gestire l'inizializzazione di base del modulo o reindirizzare se acceduto direttamente. Spesso, `index.php` in una directory di controller impedisce l'elenco delle directory.
-   `mysnapapi/controllers/front/sync.php`
    *   **Nome classe e classe padre:** `MysnapapiSyncModuleFrontController` estende `ModuleFrontController`.
    *   **Responsabilità:** Probabilmente gestisce attività specifiche di sincronizzazione dei dati, potenzialmente correlate agli aggiornamenti del catalogo prodotti o ad altri scambi di dati con l'API di Snapchat, separatamente dal monitoraggio degli eventi principale.

#### Controller Admin Back-Office

-   `mysnapapi/controllers/admin/AdminMysnapapiAjaxController.php`
    *   **Nome classe e classe padre:** `AdminMysnapapiAjaxController` estende `AdminController`.
    *   **Nome tab e entità gestita:** Non una tab di menu diretta. Questo controller gestisce le richieste AJAX originate dalla pagina di configurazione principale del modulo (metodo `getContent()` di `mysnapapi.php`). È responsabile del caricamento dinamico dei dati per i vari strumenti diagnostici (Statistiche Live, Punteggio di Salute, ecc.) e del salvataggio di impostazioni di configurazione specifiche senza un ricaricamento completo della pagina.
-   `mysnapapi/controllers/admin/index.php`
    *   **Nome classe e classe padre:** Non un controller funzionale.
    *   **Nome tab e entità gestita:** Segnaposto. Impedisce l'elenco delle directory.

### 4.3 Classi Core e Modelli (`classes/`)

-   `mysnapapi/classes/autoload.php`: File di autoload standard di PrestaShop.
-   `mysnapapi/classes/index.php`: Segnaposto per impedire l'elenco delle directory.
-   `mysnapapi/classes/MysnapapiCapiClient.php`:
    *   **Interagisce con:** Endpoint dell'API di Conversioni di Snapchat.
    *   **Estende ObjectModel:** No.
    *   **Metodi chiave:** Gestisce l'invio di eventi lato server a Snapchat. Incapsula la logica delle richieste API, l'autenticazione (utilizzando il token CAPI) e la gestione degli errori.
-   `mysnapapi/classes/MysnapapiCapiTracker.php`:
    *   **Interagisce con:** `ps_configuration` (per il token CAPI), `MysnapapiCapiClient`.
    *   **Estende ObjectModel:** No.
    *   **Metodi chiave:** Responsabile della preparazione e dell'invio dei dati degli eventi specificamente per la Conversions API. Formatta i payload degli eventi secondo le specifiche CAPI di Snapchat.
-   `mysnapapi/classes/MysnapapiCatalogDoctor.php`:
    *   **Interagisce con:** Dati del prodotto (da ObjectModels `Product` e `ProductSupplier`).
    *   **Estende ObjectModel:** No.
    *   **Metodi chiave:** Fornisce logica diagnostica per verificare la coerenza e i problemi relativi agli identificatori di prodotto utilizzati per la corrispondenza del catalogo (es. `id_product`, `reference`, `ean13`).
-   `mysnapapi/classes/MysnapapiConsent.php`:
    *   **Interagisce con:** `ps_configuration` (per le impostazioni di consenso), potenzialmente altri moduli di consenso.
    *   **Estende ObjectModel:** No.
    *   **Metodi chiave:** Gestisce lo stato del consenso. Controlla se il consenso dell'utente è richiesto e se è stato concesso prima di consentire l'attivazione di script di monitoraggio o eventi CAPI.
-   `mysnapapi/classes/MysnapapiCurrencyHelper.php`:
    *   **Interagisce con:** Classe `Currency` di PrestaShop.
    *   **Estende ObjectModel:** No.
    *   **Metodi chiave:** Fornisce funzioni di utilità per la gestione della formattazione e della conversione della valuta, garantendo che i valori degli eventi vengano inviati nel formato e nel codice valuta corretti a Snapchat.
-   `mysnapapi/classes/MysnapapiDataQualityCoach.php`:
    *   **Interagisce con:** Impostazioni di configurazione del modulo.
    *   **Estende ObjectModel:** No.
    *   **Metodi chiave:** Analizza la configurazione del modulo e fornisce raccomandazioni o avvisi per migliorare la qualità dei dati e l'efficacia del monitoraggio.
-   `mysnapapi/classes/MysnapapiEventId.php`:
    *   **Interagisce con:** Sessione, cookie.
    *   **Estende ObjectModel:** No.
    *   **Metodi chiave:** Genera e gestisce valori `event_id` unici per ogni evento tracciato. Cruciale per la deduplicazione quando si utilizza la modalità di monitoraggio Ibrida.
-   `mysnapapi/classes/MysnapapiEventMap.php`:
    *   **Interagisce con:** N/A.
    *   **Estende ObjectModel:** No.
    *   **Metodi chiave:** Definisce la mappatura tra gli eventi/dati interni di PrestaShop e i nomi e i parametri degli eventi standard di Snapchat.
-   `mysnapapi/classes/MysnapapiEvents.php`:
    *   **Interagisce con:** Varie classi core di PrestaShop (es. `Cart`, `Product`, `Order`).
    *   **Estende ObjectModel:** No.
    *   **Metodi chiave:** Classe centralizzata per la raccolta e la formattazione dei dati degli eventi (es. `PageView`, `ViewContent`, `AddToCart`, `Purchase`) dal contesto di PrestaShop in una struttura compatibile con Snapchat.
-   `mysnapapi/classes/MysnapapiHealthScore.php`:
    *   **Interagisce con:** Configurazione del modulo, potenzialmente dati di eventi live.
    *   **Estende ObjectModel:** No.
    *   **Metodi chiave:** Calcola un "punteggio di salute" complessivo per la configurazione del monitoraggio basato sulle opzioni configurate e sui problemi rilevati.
-   `mysnapapi/classes/MysnapapiHybridTracker.php`:
    *   **Interagisce con:** `MysnapapiPixelTracker`, `MysnapapiCapiTracker`, `MysnapapiEventId`.
    *   **Estende ObjectModel:** No.
    *   **Metodi chiave:** Orchestra il monitoraggio in modalità "Ibrida", garantendo che sia gli eventi Pixel che CAPI vengano inviati con lo stesso `event_id` per la deduplicazione.
-   `mysnapapi/classes/MysnapapiLiveStats.php`:
    *   **Interagisce con:** Potenzialmente un log temporaneo di eventi recenti o dati in tempo reale.
    *   **Estende ObjectModel:** No.
    *   **Metodi chiave:** Raccoglie e presenta statistiche in tempo reale sugli eventi tracciati per il pannello di amministrazione.
-   `mysnapapi/classes/MysnapapiPixelTracker.php`:
    *   **Interagisce con:** `ps_configuration` (per l'ID Pixel).
    *   **Estende ObjectModel:** No.
    *   **Metodi chiave:** Responsabile della generazione del codice JavaScript per lo Snap Pixel e dell'incorporazione nel front-office, inclusi i dati degli eventi.
-   `mysnapapi/classes/MysnapapiProductIdResolver.php`:
    *   **Interagisce con:** Dati del prodotto.
    *   **Estende ObjectModel:** No.
    *   **Metodi chiave:** Determina l'identificatore di prodotto corretto (es. `id_product`, `reference`, `ean13`) da utilizzare in base alla configurazione del modulo per la corrispondenza del catalogo.
-   `mysnapapi/classes/MysnapapiPropertyRules.php`:
    *   **Interagisce con:** N/A.
    *   **Estende ObjectModel:** No.
    *   **Metodi chiave:** Definisce regole e convalide per le proprietà degli eventi, garantendo che i dati inviati a Snapchat aderiscano alle loro specifiche API.
-   `mysnapapi/classes/MysnapapiTrackerFactory.php`:
    *   **Interagisce con:** Configurazione del modulo (modalità di monitoraggio).
    *   **Estende ObjectModel:** No.
    *   **Metodi chiave:** Pattern Factory per istanziare la classe tracker corretta (`MysnapapiPixelTracker`, `MysnapapiCapiTracker` o `MysnapapiHybridTracker`) in base alla modalità di monitoraggio configurata del modulo.
-   `mysnapapi/classes/MysnapapiTrackerInterface.php`:
    *   **Interagisce con:** N/A.
    *   **Estende ObjectModel:** No.
    *   **Metodi chiave:** Definisce un'interfaccia comune per tutte le classi tracker, garantendo firme di metodo coerenti per il monitoraggio degli eventi.
-   `mysnapapi/classes/MysnapapiUserData.php`:
    *   **Interagisce con:** Dati del cliente (da ObjectModel `Customer`), sessione, cookie.
    *   **Estende ObjectModel:** No.
    *   **Metodi chiave:** Raccoglie e formatta i dati specifici dell'utente (es. email, telefono, indirizzo IP, user agent) per la corrispondenza avanzata, garantendo che i dati siano hash e conformi.

### 4.4 Risorse JavaScript (`views/js/`)

-   `mysnapapi/tools/console-simulate-bo-ui.js`:
    *   **Ambito:** Back-office (strumento per sviluppatori).
    *   **Descrizione:** Uno script di utilità, probabilmente per lo sviluppo/debug, per simulare o interagire con l'interfaccia utente del Back Office dalla console del browser.
-   `mysnapapi/views/js/mp-collect.js`:
    *   **Ambito:** Front-office.
    *   **Descrizione:** Script di raccolta dati lato client core. Potrebbe ascoltare eventi DOM specifici o interazioni utente per attivare eventi Snap Pixel.
-   `mysnapapi/views/js/mp-consent.js`:
    *   **Ambito:** Front-office.
    *   **Descrizione:** Gestisce l'integrazione con i meccanismi di consenso ai cookie. Controlla lo stato del consenso e carica/inizializza condizionatamente lo Snap Pixel o il monitoraggio correlato. Potrebbe interagire con `prestashop.on('updateConsent')`.
-   `mysnapapi/views/js/mp-front.js`:
    *   **Ambito:** Front-office.
    *   **Descrizione:** JavaScript generale del front-office per il modulo. Questo probabilmente contiene la logica principale per inizializzare il codice base dello Snap Pixel, inviare eventi all'oggetto `snap` e gestire i trigger di eventi lato client.
-   `mysnapapi/views/js/mp-inspect.js`:
    *   **Ambito:** Front-office (modalità debug).
    *   **Descrizione:** Utilizzato quando la modalità debug è abilitata. Intercetta e visualizza gli eventi Snapchat nella console del browser, fornendo informazioni dettagliate sui dati inviati.
-   `mysnapapi/views/js/mysnapapi-admin.js`:
    *   **Ambito:** Back-office.
    *   **Descrizione:** JavaScript per l'interfaccia di amministrazione del modulo. Gestisce le interazioni con i moduli, le chiamate AJAX a `AdminMysnapapiAjaxController`, gli aggiornamenti dinamici delle sezioni diagnostiche (Statistiche Live, Punteggio di Salute) e i passaggi della procedura guidata.
-   `mysnapapi/views/js/mysnapapi-debug.js`:
    *   **Ambito:** Front-office (modalità debug).
    *   **Descrizione:** Simile a `mp-inspect.js`, fornisce utilità di debug aggiuntive o overlay visivi per gli sviluppatori per verificare il monitoraggio.
-   `mysnapapi/views/js/mysnapapi-ghost.js`:
    *   **Ambito:** Front-office.
    *   **Descrizione:** Implementa la funzionalità "Ghost Collector". Gestisce la creazione e la lettura di cookie di prima parte per la corrispondenza `ScCid` (Snapchat Click ID), migliorando l'identificazione dell'utente.
-   `mysnapapi/views/js/mysnapapi-live.js`:
    *   **Ambito:** Back-office.
    *   **Descrizione:** Alimenta la sezione "Statistiche in Tempo Reale" nel pannello di amministrazione, effettuando chiamate AJAX per recuperare e visualizzare i dati degli eventi in tempo reale.
-   `mysnapapi/views/js/mysnapapi-tcf.js`:
    *   **Ambito:** Front-office.
    *   **Descrizione:** Specificamente per l'integrazione con soluzioni di consenso conformi al Transparency and Consent Framework (TCF), garantendo che il monitoraggio di Snapchat aderisca ai segnali TCF.
-   `mysnapapi/views/js/mysnapapi-wizard.js`:
    *   **Ambito:** Back-office.
    *   **Descrizione:** Fornisce la logica interattiva per la procedura guidata di configurazione del modulo, guidando il commerciante attraverso i passaggi di configurazione iniziale.
-   `mysnapapi/views/js/mysnapapi.js`:
    *   **Ambito:** Front-office.
    *   **Descrizione:** Punto di ingresso principale o JavaScript di utilità generale per il front-office, che potenzialmente carica altri script o contiene funzioni globali specifiche del modulo.

### 4.5 Fogli di Stile CSS (`views/css/`)

-   `mysnapapi/views/css/mp-inspect.css`:
    *   **Ambito:** Front-office (modalità debug).
    *   **Descrizione:** Stili per l'overlay di debug o l'output della console quando `mp-inspect.js` è attivo.
-   `mysnapapi/views/css/mysnapapi-admin.css`:
    *   **Ambito:** Stile del modulo di amministrazione del Back-office.
    *   **Descrizione:** Stili per la pagina di configurazione del modulo, inclusi layout, pulsanti, sezioni diagnostiche (Punteggio di Salute, Coach Qualità Dati) e passaggi della procedura guidata.
-   `mysnapapi/views/css/mysnapapi-debug.css`:
    *   **Ambito:** Front-office (modalità debug).
    *   **Descrizione:** Stili aggiuntivi per gli elementi di debug, potenzialmente indicatori visivi o bordi per gli elementi tracciati.

### 4.6 Struttura del Template Smarty (`views/templates/`)

#### Template Hook (`views/templates/hook/`)

-   `mysnapapi/views/templates/hook/capi-pageview.tpl`:
    *   **Hook:** Potenzialmente `displayHeader` o `displayFooter` (contesto lato server).
    *   **Output:** Renderizza un elemento nascosto o una chiamata lato server per attivare un evento CAPI `PAGE_VIEW`, spesso usato come fallback o per il caricamento iniziale della pagina.
-   `mysnapapi/views/templates/hook/debug.tpl`:
    *   **Hook:** `displayHeader` o `displayFooter` (condizionale alla modalità debug).
    *   **Output:** Renderizza informazioni di debug o inizializza script di debug nel front-office.
-   `mysnapapi/views/templates/hook/displayOrderConfirmation.tpl`:
    *   **Hook:** `displayOrderConfirmation`.
    *   **Output:** Renderizza l'evento `PURCHASE` dello Snap Pixel e/o attiva l'evento CAPI `PURCHASE` nella pagina di conferma dell'ordine, passando i dettagli dell'ordine.
-   `mysnapapi/views/templates/hook/ghost.tpl`:
    *   **Hook:** `displayHeader` o `displayFooter`.
    *   **Output:** Renderizza il JavaScript per il "Ghost Collector" per gestire i cookie `ScCid`.
-   `mysnapapi/views/templates/hook/header.tpl`:
    *   **Hook:** `displayHeader`.
    *   **Output:** Il template principale per inizializzare il codice base dello Snap Pixel, l'oggetto `snap` e potenzialmente gli eventi `PAGE_VIEW`. Carica i file JavaScript necessari.
-   `mysnapapi/views/templates/hook/payment.tpl`:
    *   **Hook:** `displayPayment` o `displayPaymentTop`.
    *   **Output:** Renderizza `INITIATE_CHECKOUT` o altri eventi rilevanti durante la fase di selezione del pagamento del checkout.
-   `mysnapapi/views/templates/hook/product-details.tpl`:
    *   **Hook:** `displayProductButtons` o `displayFooterProduct`.
    *   **Output:** Renderizza l'evento `VIEW_CONTENT` dello Snap Pixel e l'evento `ADD_CART` (o JS correlato) nella pagina del prodotto, passando dati specifici del prodotto.

#### Template Admin (`views/templates/admin/`)

-   `mysnapapi/views/templates/admin/consent-guide.tpl`: Visualizza la guida sull'integrazione con la gestione del consenso.
-   `mysnapapi/views/templates/admin/doctor.tpl`: Renderizza l'interfaccia per lo strumento diagnostico "Dottore Catalogo".
-   `mysnapapi/views/templates/admin/dq.tpl`: Renderizza le raccomandazioni del "Coach Qualità Dati".
-   `mysnapapi/views/templates/admin/health.tpl`: Visualizza il "Punteggio di Salute" e le relative informazioni.
-   `mysnapapi/views/templates/admin/linker-domains.tpl`: Campo di input e spiegazione per il monitoraggio cross-dominio.
-   `mysnapapi/views/templates/admin/live-maintain.tpl`: Interfaccia per la manutenzione o la cancellazione delle statistiche in tempo reale.
-   `mysnapapi/views/templates/admin/live.tpl`: Visualizza la dashboard delle "Statistiche in Tempo Reale".
-   `mysnapapi/views/templates/admin/mode-context.tpl`: Fornisce contesto o spiegazione per la modalità di monitoraggio scelta.
-   `mysnapapi/views/templates/admin/mode-note-both.tpl`: Nota specifica per la modalità di monitoraggio "Ibrida".
-   `mysnapapi/views/templates/admin/mode-note-capi.tpl`: Nota specifica per la modalità di monitoraggio "Solo Conversions API".
-   `mysnapapi/views/templates/admin/mode-note-pixel.tpl`: Nota specifica per la modalità di monitoraggio "Solo Pixel".
-   `mysnapapi/views/templates/admin/mode-picker.tpl`: L'interfaccia di selezione per scegliere la modalità di monitoraggio.
-   `mysnapapi/views/templates/admin/properties-list.tpl`: Visualizza un elenco di proprietà degli eventi e le loro regole.
-   `mysnapapi/views/templates/admin/recent-events.tpl`: Tabella o elenco che visualizza gli eventi tracciati più recenti.
-   `mysnapapi/views/templates/admin/tabs.tpl`: Renderizza la struttura di navigazione a schede per la pagina di configurazione del modulo.
-   `mysnapapi/views/templates/admin/tag-chips.tpl`: Componenti visivi per la visualizzazione di tag o identificatori.
-   `mysnapapi/views/templates/admin/tag-ids.tpl`: Campi di input per ID Pixel e Token CAPI.
-   `mysnapapi/views/templates/admin/wizard.tpl`: Il template per la procedura guidata di configurazione passo-passo.

#### Template Front-office (`views/templates/front/`)

(Nessun template di pagina standalone dedicato, tutti i template del front-office sono basati su hook.)

### 4.7 Schema del Database e Mappa degli Hook

#### Tabelle del Database

Il modulo utilizza principalmente la tabella `ps_configuration` di PrestaShop per memorizzare le sue impostazioni.

-   `ps_configuration`: Memorizza coppie chiave-valore per le impostazioni del modulo (es. `MYSNAPAPI_PIXEL_ID`, `MYSNAPAPI_CAPI_TOKEN`, `MYSNAPAPI_TRACKING_MODE`).
-   Nessuna tabella SQL personalizzata è esplicitamente creata dal modulo in base all'inventario fornito. Gli eventi CAPI potrebbero essere temporaneamente accodati in memoria o in un sistema basato su file prima di essere inviati, piuttosto che in una tabella di database dedicata.

#### Tabella degli Hook Registrati

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Renderizza nella sezione `<head>` di ogni pagina del front-office. | Inizializza il codice base dello Snap Pixel, carica le risorse JS, attiva gli eventi `PAGE_VIEW` e configura `ScCid` (Ghost Collector). |
| `displayFooter` | Renderizza alla fine della sezione `<body>` di ogni pagina del front-office. | Può includere il caricamento differito di script, trigger di eventi aggiuntivi o la gestione di `ScCid`. |
| `displayProductButtons` | Nella pagina del prodotto, vicino al pulsante "Aggiungi al carrello". | Attiva gli eventi `VIEW_CONTENT` e potenzialmente `ADD_CART` con i dettagli del prodotto. |
| `displayFooterProduct` | Nella pagina del prodotto, nell'area del footer. | Posizione alternativa o aggiuntiva per gli eventi `VIEW_CONTENT` e `ADD_CART`. |
| `actionCartSave` | Eseguito ogni volta che un carrello viene modificato (aggiungi, aggiorna, rimuovi prodotto). | Attiva gli eventi `ADD_CART` o `REMOVE_FROM_CART`. |
| `actionValidateOrder` | Eseguito dopo che un ordine è stato effettuato con successo. | Attiva l'evento cruciale `PURCHASE`, inviando i dettagli completi dell'ordine (valore, valuta, prodotti). |
| `displayOrderConfirmation` | Nella pagina di conferma dell'ordine dopo un acquisto riuscito. | Renderizza l'evento `PURCHASE` lato client per lo Snap Pixel. |
| `displayPayment` | Prima della selezione del metodo di pagamento. | Attiva l'evento `INITIATE_CHECKOUT`. |
| `displayPaymentTop` | Nella parte superiore della pagina di selezione del pagamento. | Posizione alternativa o aggiuntiva per l'evento `INITIATE_CHECKOUT`. |
| `actionFrontControllerSetMedia` | Eseguito quando un controller front-office sta impostando le sue risorse multimediali. | Inietta file CSS e JavaScript specifici del modulo nel front-office. |
| `actionAdminControllerSetMedia` | Eseguito quando un controller admin sta impostando le sue risorse multimediali. | Inietta file CSS e JavaScript specifici del modulo nella pagina di configurazione del back-office. |
| `actionModuleInstall` | Eseguito quando il modulo viene installato. | Imposta i valori di configurazione predefiniti in `ps_configuration`. |
| `actionModuleUninstall` | Eseguito quando il modulo viene disinstallato. | Pulisce i valori di configurazione da `ps_configuration`. |

## 5. Supporto Ufficiale e Aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e le ultime versioni del modulo Snapchat Pixel & Conversions API, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assistere con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e all'integrazione del modulo.
