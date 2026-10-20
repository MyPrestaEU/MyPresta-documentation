---
title: "Homepage Products Pro - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Homepage Products Pro di MyPresta.eu."
sidebar:
  label: "Homepage Products Pro - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Homepage Products Pro su MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-products-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/homepage-products-pro/)
>
> ---


# Homepage Products Pro

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" verrai indirizzato alla pagina delle impostazioni principali per "Homepage Products Pro". Qui controllerai il comportamento globale e le funzionalità dei tuoi blocchi di prodotti.

#### Impostazioni Generali

- **Abilita schede interne**

  - **Cosa fa questa impostazione:** Controlla se il modulo può creare le proprie schede personalizzate sulla homepage, simili alle schede predefinite di PrestaShop "Prodotti Popolari" o "Nuovi Prodotti".
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (Sì):* Sarai in grado di creare nuovi blocchi di prodotti che appaiono come schede cliccabili sulla tua homepage, consentendo ai clienti di passare tra diverse collezioni di prodotti.
    - *Quando disabilitato (No):* Il modulo visualizzerà i blocchi di prodotti solo come sezioni autonome (ad esempio, caroselli orizzontali o blocchi di colonne), senza l'interfaccia a schede.
  - **Valore consigliato:** **Sì** (per sfruttare tutta la potenza del modulo per contenuti dinamici della homepage).
  - **Scenario / esempio del commerciante:** Vuoi mostrare "Nuovi Arrivi", "Bestseller" e "Scelte Stagionali" tutti sulla tua homepage senza renderla troppo lunga. L'abilitazione delle schede interne ti consente di inserire ciascuno di questi nella propria scheda.
- **Usa editor di testo ricco**

  - **Cosa fa questa impostazione:** Determina se un editor visivo (WYSIWYG) è disponibile quando crei o modifichi descrizioni o titoli di blocchi di prodotti, rendendo più facile formattare il testo.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (Sì):* Avrai un editor intuitivo (come TinyMCE) con opzioni di formattazione (grassetto, corsivo, link, ecc.) per i campi di testo all'interno del modulo.
    - *Quando disabilitato (No):* Avrai un campo di input di testo semplice, che ti richiederà di usare HTML di base se desideri qualsiasi formattazione.
  - **Valore consigliato:** **Sì** (per una più facile creazione di contenuti e un migliore controllo visivo).
  - **Scenario / esempio del commerciante:** Vuoi aggiungere una breve introduzione stilizzata sopra un blocco di prodotti, come "Scopri la nostra collezione **esclusiva**!". L'editor di testo ricco rende questo semplice.
- **Carica lightslider**

  - **Cosa fa questa impostazione:** Controlla se il modulo carica la libreria JavaScript LightSlider, che viene utilizzata per creare caroselli e slider di contenuti reattivi.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (Sì):* La libreria LightSlider verrà caricata, consentendo ai tuoi blocchi di prodotti di essere visualizzati come caroselli interattivi e abilitati al tocco. Questo è tipicamente richiesto per gli effetti visivi del modulo.
    - *Quando disabilitato (No):* La libreria LightSlider non verrà caricata. Se il tuo tema o un altro modulo fornisce funzionalità di carosello simili, potresti disabilitare questo per evitare conflitti o caricamenti ridondanti. Tuttavia, se non è presente un'altra soluzione di carosello, i tuoi blocchi di prodotti potrebbero essere visualizzati come griglie o elenchi statici.
  - **Valore consigliato:** **Sì** (a meno che tu non abbia una ragione specifica o un conflitto, poiché è essenziale per le funzionalità di carosello del modulo).
  - **Scenario / esempio del commerciante:** Vuoi che il tuo blocco "Nuovi Prodotti" sia un carosello elegante e scorrevole orizzontalmente. Questa impostazione assicura che lo script necessario sia caricato per quella funzionalità.
- **Abilita analisi**

  - **Cosa fa questa impostazione:** Attiva o disattiva il tracciamento interno del modulo delle prestazioni dei blocchi di prodotti, come visualizzazioni e clic.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (Abilitato):* Il modulo raccoglierà dati su quante volte i tuoi blocchi di prodotti vengono visualizzati e cliccati, fornendo approfondimenti sulla loro efficacia.
    - *Quando disabilitato (Disabilitato):* Nessun dato sulle prestazioni verrà raccolto o visualizzato all'interno della dashboard del modulo.
  - **Valore consigliato:** **Abilitato** (per ottenere preziose informazioni su quali blocchi di prodotti stanno performando meglio).
  - **Scenario / esempio del commerciante:** Vuoi sapere se il tuo blocco "Bestseller" sta ottenendo più engagement del tuo blocco "In Saldo". L'abilitazione dell'analisi fornisce questi dati.
- **Periodo di analisi**

  - **Cosa fa questa impostazione:** Definisce l'intervallo di tempo per il quale verranno visualizzati i dati di analisi interni del modulo.
  - **Effetto della modifica di questa impostazione:** Modifica l'intervallo di dati mostrato nei rapporti di analisi.
  - **Opzioni:** Ultimi 7 giorni, Ultimi 30 giorni, Ultimi 90 giorni, Ultimi 180 giorni, Ultimi 365 giorni.
  - **Valore consigliato:** **Ultimi 30 giorni** (un buon equilibrio per le tendenze recenti, ma regola in base alle tue esigenze di reporting).
  - **Scenario / esempio del commerciante:** Vuoi rivedere le prestazioni dei tuoi blocchi di prodotti della homepage nell'ultimo mese per vedere se una promozione recente ha avuto un impatto.
- **Abilita cache blocco**

  - **Cosa fa questa impostazione:** Attiva un meccanismo di caching per i blocchi di prodotti generati dal modulo. Il caching memorizza una versione temporanea del blocco, in modo che non debba essere ricostruito ogni volta che un cliente visita la pagina.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (Sì):* I blocchi di prodotti si caricheranno più velocemente per i clienti, poiché il server serve una versione in cache. Questo può migliorare significativamente i tempi di caricamento della pagina e le prestazioni del server, specialmente nei negozi ad alto traffico.
    - *Quando disabilitato (No):* I blocchi di prodotti verranno generati dinamicamente ad ogni caricamento della pagina, il che può essere più lento ma garantisce che vengano sempre visualizzati i dati di prodotto più recenti (ad esempio, livelli di stock, prezzi).
  - **Valore consigliato:** **Sì** (per i benefici in termini di prestazioni, a meno che tu non abbia dati di prodotto che cambiano molto rapidamente e che devono essere in tempo reale).
  - **Scenario / esempio del commerciante:** La tua homepage sta ricevendo molto traffico e vuoi assicurarti che si carichi il più rapidamente possibile. L'abilitazione della cache accelererà la visualizzazione dei tuoi blocchi di prodotti.
- **Cache TTL (secondi)**

  - **Cosa fa questa impostazione:** Definisce per quanto tempo (in secondi) una versione in cache di un blocco di prodotti rimane valida prima di essere aggiornata. (TTL sta per "Time To Live").
  - **Effetto della modifica di questa impostazione:**
    - *Valore più alto:* I blocchi vengono memorizzati nella cache più a lungo, portando a migliori prestazioni ma potenzialmente mostrando informazioni sui prodotti leggermente obsolete (ad esempio, se un prezzo cambia, potrebbe non aggiornarsi sulla homepage fino alla scadenza della cache).
    - *Valore più basso:* I blocchi vengono aggiornati più frequentemente, garantendo informazioni più aggiornate ma con un guadagno di prestazioni leggermente inferiore.
  - **Valore consigliato:** **3600** (1 ora) o **7200** (2 ore) è un buon punto di partenza. Regola in base alla frequenza con cui i tuoi dati di prodotto cambiano e quanto sono critici gli aggiornamenti in tempo reale.
  - **Scenario / esempio del commerciante:** Hai una vendita flash in cui i prezzi cambiano ogni ora. Potresti impostare il Cache TTL a 3600 secondi (1 ora) per assicurarti che i prezzi si aggiornino relativamente rapidamente sulla homepage.
- **Rilevamento automatico tema**

  - **Cosa fa questa impostazione:** Tenta di rilevare automaticamente il tuo tema PrestaShop attivo per applicare stili e override di template appropriati per una migliore integrazione visiva.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (Sì):* Il modulo cerca di adattare il suo output per corrispondere alla struttura e allo stile del tuo tema, potenzialmente utilizzando template specifici del tema (ad esempio, `firezy-products17.tpl`). Questo spesso si traduce in un aspetto più uniforme.
    - *Quando disabilitato (No):* Il modulo utilizzerà i suoi template e stili predefiniti e generici, che potrebbero non corrispondere perfettamente al design del tuo tema. Potrebbe essere necessario selezionare manualmente un tema o applicare CSS personalizzati.
  - **Valore consigliato:** **Sì** (per la migliore integrazione visiva out-of-the-box).
  - **Scenario / esempio del commerciante:** Hai installato il modulo e i blocchi di prodotti non sembrano del tutto corretti con il tuo tema personalizzato. L'abilitazione di questa opzione potrebbe risolvere automaticamente lo stile.

#### Impostazioni Nascoste/Avanzate (Chiavi di Configurazione Interne)

Queste non sono tipicamente esposte direttamente come impostazioni rivolte all'utente, ma sono valori di configurazione che il modulo utilizza internamente. Sono elencate qui per completezza e comprensione da parte degli sviluppatori.

- `update_`, `mypresta_updates`: Relativo ai controlli di aggiornamento del modulo e alle notifiche da MyPresta.eu.
- `hpp_analytics_enabled`: Corrisponde all'impostazione "Abilita analisi".
- `hpp_cache_enabled`: Corrisponde all'impostazione "Abilita cache blocco".
- `hpp_cache_ttl`: Corrisponde all'impostazione "Cache TTL (secondi)".
- `hpp_theme_auto_detect`: Corrisponde all'impostazione "Rilevamento automatico tema".
- `hpp_analytics_period`: Corrisponde all'impostazione "Periodo di analisi".
- `hpp_carousel_native`: Probabilmente un flag interno per il tipo di carosello, possibilmente correlato a LightSlider.
- `PS_NB_DAYS_NEW_PRODUCT`: Impostazione predefinita di PrestaShop per quanti giorni un prodotto è considerato "nuovo". Il modulo potrebbe usarlo per i blocchi "Nuovi Prodotti".
- `PS_CURRENCY_DEFAULT`: ID della valuta predefinita di PrestaShop.
- `hpp_internal_tabs`: Corrisponde all'impostazione "Abilita schede interne".
- `hpp_bxslider`: Una libreria di carosello più vecchia, possibilmente un'impostazione legacy o un fallback.
- `PS_LANG_DEFAULT`: ID della lingua predefinita di PrestaShop.
- `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Impostazione di PrestaShop per consentire ai dipendenti di cambiare la lingua del modulo.
- `hpp_rich_text`: Corrisponde all'impostazione "Usa editor di testo ricco".
- `hpp_theme`: Memorizza il nome del tema rilevato o selezionato manualmente.
- `hpp_customtplpath`: Consente di specificare un percorso personalizzato per i template, utile per l'integrazione avanzata del tema.

### 2.2 Schermate di Amministrazione Dedicate e Viste Controller

Il modulo "Homepage Products Pro" estende il Back Office di PrestaShop aggiungendo una sezione dedicata per la gestione dei tuoi blocchi di prodotti.

- **Nome Schermata e Posizione Menu:**

  - Troverai una nuova voce di menu, tipicamente sotto **Moduli > Homepage Products Pro** o un nome simile, che ti condurrà alla dashboard del modulo.
  - Questa dashboard è dove crei, modifichi, elimini e organizzi i tuoi blocchi di prodotti.
- **Azioni e Impostazioni Disponibili:**

  - **Tabella Elenco Blocchi Prodotto:** Questa vista principale mostrerà un elenco di tutti i blocchi di prodotti che hai creato. Ogni voce mostrerà:
    - **Nome:** Il nome interno che hai dato al blocco (es. "Bestseller Homepage").
    - **Titolo:** Il titolo pubblico visualizzato ai clienti (es. "Le Nostre Scelte Migliori!").
    - **Hook:** Dove viene visualizzato il blocco (es. `displayHome`, `displayHomeTabContent`, `displayLeftColumn`).
    - **Stato:** Se il blocco è abilitato o disabilitato.
    - **Posizione:** L'ordine in cui i blocchi appaiono all'interno dello stesso hook.
    - **Azioni:** Pulsanti per **Modifica**, **Duplica** o **Elimina** il blocco.
  - **Pulsante "Aggiungi Nuovo Blocco":** Cliccando su questo si aprirà un modulo per creare un nuovo blocco di prodotti.
  - **Modulo "Modifica Blocco":** Quando aggiungi o modifichi un blocco, tipicamente configurerai:
    - **Nome Blocco:** Un identificatore interno (es. "CollezioneEstiva2023").
    - **Titolo Visualizzato:** Il titolo che i clienti vedono (es. "Collezione Estiva").
    - **Descrizione:** Un breve testo che appare sopra i prodotti (editor di testo ricco disponibile se abilitato).
    - **Selezione Hook:** Scegli dove appare il blocco (es. `displayHome`, `displayHomeTabContent` per le schede, `displayLeftColumn`).
    - **Selezione Prodotto:** Questo è cruciale. Definisci *quali* prodotti appaiono nel blocco. Le opzioni tipicamente includono:
      - **Prodotti Specifici:** Seleziona manualmente singoli prodotti utilizzando uno strumento di ricerca.
      - **Prodotti da Categoria:** Seleziona una o più categorie, e il modulo visualizzerà i prodotti da esse.
      - **Nuovi Prodotti:** Visualizza automaticamente gli ultimi prodotti aggiunti al tuo negozio.
      - **Bestseller:** Visualizza automaticamente i prodotti più venduti del tuo negozio.
      - **Prodotti in Saldo:** Visualizza automaticamente i prodotti attualmente in saldo.
      - **Prodotti in Evidenza:** Prodotti contrassegnati come in evidenza.
    - **Numero di Prodotti da Visualizzare:** Limita quanti prodotti vengono mostrati.
    - **Tipo di Visualizzazione:** Scegli tra un carosello/slider o una griglia/elenco statico.
    - **Impostazioni Carosello:** Se si utilizza un carosello, impostazioni per elementi per diapositiva, riproduzione automatica, frecce di navigazione, ecc.
    - **Selettore Visibilità/Pubblico:** Definisci chi vede il blocco (es. tutti i clienti, gruppi di clienti specifici, paesi specifici).
    - **Specificità della Lingua:** Configura titoli e descrizioni per diverse lingue.
    - **Stato:** Abilita/Disabilita il singolo blocco.
    - **Posizione:** Imposta l'ordine di visualizzazione rispetto ad altri blocchi nello stesso hook.
- **Effetto delle modifiche:**

  - **Aggiunta di un Nuovo Blocco:** Un nuovo display di prodotti apparirà nel tuo front-office nell'hook scelto, mostrando i prodotti selezionati in base alle tue impostazioni.
  - **Modifica di un Blocco:** Le modifiche a titoli, descrizioni, selezione prodotti, tipo di visualizzazione o impostazioni si rifletteranno immediatamente nel front-office (soggetto al TTL della cache se la cache è abilitata).
  - **Eliminazione di un Blocco:** Il display dei prodotti verrà rimosso dal tuo front-office.
  - **Modifica della Posizione:** L'ordine dei blocchi all'interno di un hook specifico si aggiornerà nel front-office.
  - **Abilitazione/Disabilitazione:** Attiva/disattiva la visibilità del blocco nel tuo negozio.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

  1. **Pianifica il layout della tua homepage:** Decidi quali tipi di prodotti vuoi evidenziare (nuovi, bestseller, categorie specifiche, promozioni).
  2. **Crea nuovi blocchi:** Per ogni sezione pianificata, vai alla dashboard del modulo e clicca su "Aggiungi Nuovo Blocco".
  3. **Configura ogni blocco:**
     - Assegna un nome interno chiaro (es. "HP_NuoviArrivi").
     - Scrivi un titolo e una descrizione accattivanti.
     - Seleziona l'hook appropriato (es. `displayHome` per il contenuto principale, `displayHomeTabContent` per le schede).
     - Scegli il tuo metodo di selezione dei prodotti (manuale, categoria, nuovi, ecc.).
     - Regola le impostazioni di visualizzazione e carosello.
     - Imposta la posizione per controllarne l'ordine.
  4. **Rivedi nel front-office:** Controlla sempre la homepage del tuo negozio dopo aver apportato modifiche per assicurarti che tutto appaia e funzioni come previsto.
  5. **Monitora le analisi:** Controlla regolarmente le analisi del modulo (se abilitate) per capire quali blocchi stanno performando bene e adatta la tua strategia di conseguenza.
  6. **Mantieni e aggiorna:** Man mano che arrivano nuovi prodotti o cambiano le promozioni, aggiorna i tuoi blocchi esistenti o creane di nuovi per mantenere la tua homepage fresca e pertinente.

### 2.3 Tabella di Riferimento Rapido della Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Config. Principale | Abilita schede interne | Sì | Consente la creazione di schede prodotto sulla homepage. |
| Config. Principale | Usa editor di testo ricco | Sì | Fornisce un editor visivo per i campi di testo. |
| Config. Principale | Carica lightslider | Sì | Abilita caroselli/slider di prodotti. |
| Config. Principale | Abilita analisi | Abilitato | Traccia visualizzazioni e clic per i blocchi di prodotti. |
| Config. Principale | Periodo di analisi | Ultimi 30 giorni | Imposta l'intervallo di tempo per i rapporti di analisi. |
| Config. Principale | Abilita cache blocco | Sì | Migliora la velocità di caricamento della pagina memorizzando i blocchi nella cache. |
| Config. Principale | Cache TTL (secondi) | 3600 (1 ora) | Per quanto tempo i blocchi in cache rimangono validi. |
| Config. Principale | Rilevamento automatico tema | Sì | Adatta l'output del modulo al tuo tema. |
| Gestione Blocchi | Nome Blocco | N/A (Definito dall'utente) | Identificatore interno per il tuo blocco di prodotti. |
| Gestione Blocchi | Titolo Visualizzato | N/A (Definito dall'utente) | Titolo pubblico mostrato ai clienti. |
| Gestione Blocchi | Descrizione | N/A (Definito dall'utente) | Testo visualizzato sopra il blocco di prodotti. |
| Gestione Blocchi | Selezione Hook | `displayHome` / `displayHomeTabContent` | Determina dove appare il blocco nel negozio. |
| Gestione Blocchi | Selezione Prodotto | N/A (Definito dall'utente) | Definisce quali prodotti vengono mostrati (manuale, categoria, nuovi, bestseller, ecc.). |
| Gestione Blocchi | Numero di Prodotti | N/A (Definito dall'utente) | Limita la quantità di prodotti visualizzati. |
| Gestione Blocchi | Tipo di Visualizzazione | Carosello / Griglia | Come i prodotti sono presentati visivamente. |
| Gestione Blocchi | Visibilità/Pubblico | Tutti i Clienti | Limita la visibilità del blocco a gruppi/paesi specifici. |
| Gestione Blocchi | Stato | Abilitato | Attiva/disattiva la visibilità del blocco nel front-office. |
| Gestione Blocchi | Posizione | N/A (Definito dall'utente) | Imposta l'ordine di visualizzazione dei blocchi all'interno di un hook. |

## 3. Risoluzione dei Problemi del Commerciante e Domande Frequenti (FAQ)

**D1: I miei blocchi di prodotti non vengono visualizzati sulla homepage, o sembrano rotti.**

- **R:**
  1. **Controlla lo Stato del Modulo:** Assicurati che il modulo "Homepage Products Pro" sia abilitato in **Moduli > Gestione moduli**.
  2. **Controlla lo Stato del Blocco:** Vai alla dashboard di configurazione del modulo e verifica che i blocchi di prodotti specifici che hai creato siano "Abilitati".
  3. **Selezione Hook:** Ricontrolla di aver assegnato i blocchi agli hook front-office corretti (ad esempio, `displayHome` per il contenuto principale, `displayHomeTabContent` per le schede, `displayLeftColumn` per le colonne).
  4. **Cancella Cache:** Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota la cache". A volte, il vecchio contenuto in cache impedisce la visualizzazione del nuovo output del modulo.
  5. **Compatibilità del Tema:** Se hai un tema personalizzato, prova ad abilitare "Rilevamento automatico tema" nella configurazione principale del modulo. Se i problemi persistono, il tuo tema potrebbe richiedere piccole modifiche CSS (vedi D3).

**D2: I miei blocchi di prodotti vengono visualizzati, ma i prodotti non si aggiornano (ad esempio, vecchi prezzi, articoli esauriti ancora visibili).**

- **R:** Questo è di solito un problema di cache.
  1. **Cache del Modulo:** Nella configurazione principale del modulo, controlla "Abilita cache blocco" e "Cache TTL (secondi)". Se la cache è abilitata, il blocco potrebbe mostrare una versione più vecchia e in cache. Puoi disabilitare temporaneamente la cache, salvare, quindi riabilitarla, o semplicemente attendere la scadenza del TTL.
  2. **Cache di PrestaShop:** Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota la cache". Questo cancella tutte le cache a livello di PrestaShop.
  3. **Cache del Browser:** Cancella la cache e i cookie del tuo browser, o visualizza il tuo sito in una finestra in incognito/privata per assicurarti di non vedere una versione memorizzata localmente.

**D3: I blocchi di prodotti appaiono, ma lo stile è sbagliato (ad esempio, font errati, elementi disallineati, carosello rotto).**

- **R:**
  1. **Rilevamento Automatico Tema:** Nella configurazione principale del modulo, assicurati che "Rilevamento automatico tema" sia abilitato. Questo aiuta il modulo a utilizzare lo stile specifico del tema.
  2. **Carica LightSlider:** Se i caroselli sono rotti, assicurati che "Carica lightslider" sia abilitato nella configurazione del modulo.
  3. **Conflitti del Tema:** I temi personalizzati a volte hanno CSS o JavaScript in conflitto. Se sospetti questo, prova a passare temporaneamente a un tema PrestaShop predefinito (come Classic) per vedere se il problema si risolve. Se lo fa, il tuo tema personalizzato necessita di modifiche.
  4. **CSS Personalizzato:** Potrebbe essere necessario aggiungere CSS personalizzato al foglio di stile del tuo tema per sovrascrivere gli stili predefiniti del modulo e abbinarli al tuo tema. Uno sviluppatore web può aiutarti in questo.

**D4: Ho creato un nuovo blocco di prodotti, ma non appare come scheda sulla homepage.**

- **R:**
  1. **Abilita Schede Interne:** Nella configurazione principale del modulo, assicurati che "Abilita schede interne" sia impostato su "Sì".
  2. **Hook Corretto:** Assicurati che la **Selezione Hook** del blocco di prodotti sia impostata su `displayHomeTabContent`. I blocchi impostati su `displayHome` o colonne non appariranno come schede.
  3. **Posizionamento:** Controlla la posizione dei tuoi blocchi a schede. Se sono molto in basso nell'ordine, potrebbero non apparire se altri moduli occupano spazio.

**D5: Il mio editor di testo ricco non funziona, o non riesco a formattare il testo.**

- **R:**
  1. **Abilita Editor di Testo Ricco:** Nella configurazione principale del modulo, assicurati che "Usa editor di testo ricco" sia impostato su "Sì".
  2. **Problemi del Browser:** Prova un browser web diverso o cancella la cache del tuo browser attuale.
  3. **Conflitti JavaScript:** Occasionalmente, altri moduli o script del tema possono interferire con l'editor di testo ricco. Se il problema persiste, consulta uno sviluppatore.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

Questa sezione fornisce un'analisi approfondita dell'architettura tecnica e della codebase del modulo "Homepage Products Pro", progettata per sviluppatori, webmaster e agenzie tecniche.

### 4.1 Panoramica dell'Architettura

Il modulo "Homepage Products Pro" (`hpp`) segue un'architettura standard dei moduli PrestaShop, sfruttando principalmente gli hook per la visualizzazione nel front-office e un metodo `getContent()` per la sua configurazione nel back-office. Implementa una dashboard personalizzata per la gestione dei blocchi di prodotti, che vengono memorizzati come valori di configurazione o potenzialmente in tabelle di database personalizzate (sebbene non siano state identificate classi `ObjectModel` esplicite nell'inventario fornito, i dati complessi sono spesso serializzati in `ps_configuration` o gestiti tramite classi helper). Il modulo si basa fortemente sui template Smarty per il rendering dei suoi vari blocchi di prodotti e delle interfacce di amministrazione. Integra librerie esterne come LightSlider per i caroselli e TinyMCE per l'editing di testo ricco. I meccanismi di analisi e caching sono integrati per prestazioni e approfondimenti.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

- `hpp/controllers/front/index.php`
  - **Nome Classe:** `HppIndexModuleFrontController` (probabilmente, basato sulla convenzione del nome del file)
  - **Classe Padre:** `ModuleFrontController`
  - **Responsabilità:** Questo controller funge probabilmente da punto di ingresso generale per le azioni del modulo nel front-office che non rientrano in categorie AJAX o di tracciamento specifiche. Potrebbe gestire il caricamento iniziale dei dati o il rendering di tipi di blocco specifici se non interamente basato su hook.
- `hpp/controllers/front/lazyblock.php`
  - **Nome Classe:** `HppLazyblockModuleFrontController`
  - **Classe Padre:** `ModuleFrontController`
  - **Responsabilità:** Questo controller è progettato per gestire le richieste AJAX per il caricamento pigro dei blocchi di prodotti. Quando un utente scorre verso il basso o interagisce con una scheda, questo controller verrebbe chiamato per recuperare i dati del prodotto e renderizzare l'HTML per un blocco specifico, migliorando i tempi di caricamento iniziale della pagina. Probabilmente accetta parametri come ID blocco, numero di pagina o criteri di filtro.
- `hpp/controllers/front/track.php`
  - **Nome Classe:** `HppTrackModuleFrontController`
  - **Classe Padre:** `ModuleFrontController`
  - **Responsabilità:** Questo controller è responsabile della gestione delle richieste di tracciamento delle analisi. Quando un blocco di prodotti viene visualizzato o un prodotto all'interno di un blocco viene cliccato, una richiesta viene inviata a questo controller per registrare l'evento, contribuendo ai dati di analisi interni del modulo.

#### Controller Amministrazione Back-Office

Nessun file `AdminController` dedicato è stato identificato nell'inventario fornito. Ciò suggerisce che la gestione del back-office del modulo (creazione/modifica di blocchi di prodotti) è gestita direttamente all'interno del metodo `getContent()` del file `hpp.php`, potenzialmente utilizzando le classi `HelperForm` e `HelperList` di PrestaShop, o un approccio di rendering personalizzato all'interno della pagina di configurazione principale del modulo.

### 4.3 Classi Core e Modelli (`classes/`)

Nessuna classe PHP personalizzata che estende `ObjectModel` o altre funzionalità core è stata esplicitamente elencata nella directory `classes/`. Ciò implica che:

- I dati complessi (come le configurazioni dei singoli blocchi di prodotti) sono probabilmente memorizzati come array serializzati o stringhe JSON all'interno della tabella `ps_configuration`, gestiti direttamente dal file del modulo `hpp.php`.
- In alternativa, il modulo potrebbe utilizzare un approccio più procedurale o fare affidamento su classi helper definite direttamente all'interno di `hpp.php` o delle sue librerie incluse.
- La directory `lib/` contiene varie classi helper e librerie esterne (ad esempio, `searchTool`, `smartyTemplatesManager`, `src`). Queste sono probabilmente utilizzate per funzionalità specifiche come la ricerca di prodotti, la gestione dei template o l'implementazione del carosello, piuttosto che definire entità aziendali core.

### 4.4 Risorse JavaScript (`views/js/`)

- `hpp/js/script.js`
  - **Ambito:** Front-office.
  - **Dettagli:** Contiene probabilmente la logica principale del front-office per l'inizializzazione dei caroselli di prodotti (LightSlider), la gestione del cambio di scheda e le interazioni generali dell'interfaccia utente relative ai blocchi di prodotti. Potrebbe anche contenere la logica per il caricamento pigro o il tracciamento analitico di base.
- `hpp/js/tinymce16-force-urls.inc.js`
  - **Ambito:** Back-office.
  - **Dettagli:** Uno script specifico per l'editor di testo ricco TinyMCE, probabilmente per garantire che gli URL siano gestiti e formattati correttamente all'interno dell'editor, specialmente nei contesti di PrestaShop 1.6 più vecchi.
- `hpp/lib/searchTool/views/js/autocomplete.js`
  - **Ambito:** Back-office.
  - **Dettagli:** Fornisce la funzionalità JavaScript per un input di ricerca con autocompletamento, utilizzato quando si selezionano prodotti specifici per un blocco di prodotti nella configurazione del back-office. Probabilmente effettua chiamate AJAX per recuperare suggerimenti di prodotti.
- `hpp/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`
  - **Ambito:** Back-office.
  - **Dettagli:** Gestisce la creazione dinamica, la modifica e la selezione dei template Smarty all'interno dell'interfaccia del back-office, probabilmente per utenti avanzati per personalizzare i layout dei blocchi.
- `hpp/lib/src/js/lightslider.js`
  - **Ambito:** Front-office.
  - **Dettagli:** La libreria LightSlider core, responsabile della creazione di caroselli di contenuti reattivi e abilitati al tocco per i blocchi di prodotti. Gestisce le transizioni delle diapositive, la navigazione e la reattività.
- `hpp/views/js/admin-audience-picker.js`
  - **Ambito:** Back-office.
  - **Dettagli:** Fornisce la logica interattiva per l'interfaccia "Selettore Pubblico" nel back-office, consentendo agli amministratori di selezionare gruppi di clienti o paesi specifici per la visibilità del blocco.
- `hpp/views/js/adminHppDashboard.js`
  - **Ambito:** Back-office.
  - **Dettagli:** Il JavaScript principale per la dashboard del back-office del modulo, che gestisce interazioni come l'aggiunta/modifica di blocchi, il riordino tramite drag-and-drop e la gestione generale dell'interfaccia utente.
- `hpp/views/js/adminHppDashboardDemo.js`
  - **Ambito:** Back-office.
  - **Dettagli:** Contiene probabilmente JavaScript specifico per la demo della dashboard del back-office, possibilmente per la configurazione iniziale o per mostrare le funzionalità, e potrebbe non essere attivo in un ambiente di produzione.
- `hpp/views/js/hpp-analytics.js`
  - **Ambito:** Front-office.
  - **Dettagli:** Gestisce il lato front-office del tracciamento delle analisi, inviando dati (ad esempio, visualizzazioni di blocchi, clic sui prodotti) al controller `track.php` tramite AJAX.
- `hpp/views/js/hpp-lazyload.js`
  - **Ambito:** Front-office.
  - **Dettagli:** Implementa il caricamento pigro per i blocchi di prodotti o il loro contenuto, effettuando chiamate AJAX a `lazyblock.php` quando i blocchi entrano nel viewport o le schede vengono attivate.

### 4.5 Fogli di Stile CSS (`views/css/`)

- `hpp/css/global.css`
  - **Ambito:** Front-office.
  - **Dettagli:** Contiene stili generali e globali per l'output del modulo nel front-office, garantendo una coerenza visiva di base.
- `hpp/css/homefeaturedslider.css`
  - **Ambito:** Front-office.
  - **Dettagli:** Stili specifici per il componente slider in evidenza della homepage, probabilmente per versioni precedenti di PrestaShop o implementazioni specifiche di caroselli.
- `hpp/css/hpp.css`
  - **Ambito:** Front-office.
  - **Dettagli:** Il foglio di stile principale del front-office per il modulo, che definisce l'aspetto dei blocchi di prodotti, delle griglie e dei caroselli.
- `hpp/css/internal-tabs.css`
  - **Ambito:** Front-office.
  - **Dettagli:** Stili specifici per l'interfaccia a schede interne sulla homepage, inclusa la navigazione delle schede e le aree di contenuto.
- `hpp/css.css`
  - **Ambito:** Front-office.
  - **Dettagli:** Potenziale foglio di stile generale legacy o aggiuntivo.
- `hpp/lib/searchTool/views/css/autocomplete.css`
  - **Ambito:** Back-office.
  - **Dettagli:** Stili per l'input di ricerca con autocompletamento utilizzato nel back-office per la selezione dei prodotti.
- `hpp/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`
  - **Ambito:** Back-office.
  - **Dettagli:** Stili per l'interfaccia del gestore di template Smarty nel back-office.
- `hpp/lib/src/css/lightslider.css`
  - **Ambito:** Front-office.
  - **Dettagli:** Il CSS core per la libreria LightSlider, che fornisce lo stile di base per il componente carosello.
- `hpp/views/css/admin-audience-picker.css`
  - **Ambito:** Back-office.
  - **Dettagli:** Stili per l'interfaccia del selettore del pubblico nel back-office.
- `hpp/views/css/admin-searchtool.css`
  - **Ambito:** Back-office.
  - **Dettagli:** Stili aggiuntivi per lo strumento di ricerca nel pannello di amministrazione.
- `hpp/views/css/admin_hpp.css`
  - **Ambito:** Back-office.
  - **Dettagli:** Il foglio di stile primario per la configurazione e la dashboard del back-office del modulo.
- `hpp/views/templates/admin/css/css.css`
  - **Ambito:** Back-office.
  - **Dettagli:** Un foglio di stile specificamente situato all'interno della directory dei template di amministrazione, probabilmente per esigenze di stile molto specifiche all'interno di quei template.

### 4.6 Struttura dei Template Smarty (`views/templates/`)

#### Template Hook (`views/templates/hook/`)

Questi template vengono renderizzati quando il modulo è agganciato a posizioni specifiche nel front-office. Molti sono override specifici del tema.

- `hpp/views/templates/hook/column17.tpl`
  - **Hook:** `displayLeftColumn`, `displayRightColumn` (PrestaShop 1.7.x+).
  - **Output:** Renderizza un blocco di prodotti progettato per le colonne sinistra o destra, tipicamente un elenco verticale o una piccola griglia.
- `hpp/views/templates/hook/firezy-column17.tpl`
  - **Hook:** `displayLeftColumn`, `displayRightColumn` (PrestaShop 1.7.x+ per il tema Firezy).
  - **Output:** Override specifico del tema per i blocchi di prodotti in colonna, personalizzato per il tema Firezy.
- `hpp/views/templates/hook/firezy-homeTab.tpl`
  - **Hook:** `displayHomeTab` (per il tema Firezy).
  - **Output:** Renderizza il link di navigazione della scheda (ad esempio, "Collezione Estiva") per il tema Firezy.
- `hpp/views/templates/hook/firezy-homeTabContent.tpl`
  - **Hook:** `displayHomeTabContent` (per il tema Firezy).
  - **Output:** Renderizza il contenuto (il blocco di prodotti stesso) che appare quando una scheda specifica è attiva, personalizzato per il tema Firezy.
- `hpp/views/templates/hook/firezy-internal-tabs.tpl`
  - **Hook:** `displayHome` (per il tema Firezy).
  - **Output:** Renderizza l'intera interfaccia a schede interna (sia la navigazione che il wrapper del contenuto) per il tema Firezy.
- `hpp/views/templates/hook/firezy-products17.tpl`
  - **Hook:** `displayHome` (per il tema Firezy).
  - **Output:** Renderizza un blocco di prodotti generale (carosello o griglia) per l'area del contenuto principale della homepage, personalizzato per il tema Firezy.
- `hpp/views/templates/hook/homeTab.tpl`
  - **Hook:** `displayHomeTab`.
  - **Output:** Renderizza il link di navigazione generico della scheda.
- `hpp/views/templates/hook/homeTabContent.tpl`
  - **Hook:** `displayHomeTabContent`.
  - **Output:** Renderizza il contenuto generico per un blocco di prodotti a schede.
- `hpp/views/templates/hook/hummingbird-column17.tpl`, `hummingbird-homeTab.tpl`, `hummingbird-homeTabContent.tpl`, `hummingbird-internal-tabs.tpl`, `hummingbird-products17.tpl`
  - **Hook:** Simile a Firezy, questi sono override specifici del tema per il tema Hummingbird, fornendo layout personalizzati per colonne, navigazione a schede, contenuto delle schede, wrapper delle schede interne e blocchi di prodotti generali.
- `hpp/views/templates/hook/internal-tabs.tpl`
  - **Hook:** `displayHome`.
  - **Output:** Renderizza l'interfaccia a schede interna generica (navigazione e wrapper del contenuto).
- `hpp/views/templates/hook/products17.tpl`
  - **Hook:** `displayHome`, `displayTopColumn`.
  - **Output:** Renderizza un blocco di prodotti generico (carosello o griglia) per l'area del contenuto principale della homepage o della colonna superiore (PrestaShop 1.7.x+).
- `hpp/views/templates/hook/warehouse-column17.tpl`, `warehouse-homeTab.tpl`, `warehouse-homeTabContent.tpl`, `warehouse-internal-tabs.tpl`, `warehouse-products17.tpl`
  - **Hook:** Simile a Firezy e Hummingbird, questi sono override specifici del tema per il tema Warehouse, fornendo layout personalizzati per colonne, navigazione a schede, contenuto delle schede, wrapper delle schede interne e blocchi di prodotti generali.

#### Template Admin (`views/templates/admin/`)

Questi template sono utilizzati per l'interfaccia del back-office del modulo.

- `hpp/views/templates/admin/audience-picker.tpl`
  - **Output:** Renderizza l'HTML per l'interfaccia di selezione del gruppo di clienti e del paese.
- `hpp/views/templates/admin/country-priority-picker.tpl`
  - **Output:** Renderizza l'HTML per la selezione e la prioritizzazione dei paesi.
- `hpp/views/templates/admin/menu.tpl`
  - **Output:** Renderizza il menu o la navigazione specifica del modulo all'interno della sua dashboard del back-office.
- `hpp/views/templates/admin/scripts.tpl`
  - **Output:** Include file JavaScript o script inline specificamente per l'interfaccia di amministrazione.
- `hpp/views/templates/admin/ul-li.tpl`
  - **Output:** Un template di elenco generico, possibilmente utilizzato per visualizzare elenchi di elementi o opzioni all'interno dei moduli di amministrazione.

#### Template Libreria (`hpp/lib/`)

Questi template fanno parte di librerie integrate.

- `hpp/lib/searchTool/views/scripts.tpl`
  - **Output:** Include file JavaScript o script inline per la funzionalità dello strumento di ricerca.
- `hpp/lib/smartyTemplatesManager/tpl/example.tpl`
  - **Output:** Un template di esempio per il Smarty Templates Manager, probabilmente per dimostrazione o come base.
- `hpp/lib/smartyTemplatesManager/views/buttonManager.tpl`
  - **Output:** Renderizza pulsanti o controlli per la gestione dei template.
- `hpp/lib/smartyTemplatesManager/views/createTemplateForm.tpl`
  - **Output:** Renderizza il modulo per la creazione di nuovi template personalizzati.
- `hpp/lib/smartyTemplatesManager/views/editTemplateForm.tpl`
  - **Output:** Renderizza il modulo per la modifica di template personalizzati esistenti.
- `hpp/lib/smartyTemplatesManager/views/mainForm.tpl`
  - **Output:** Il modulo principale per l'interfaccia del Smarty Templates Manager.
- `hpp/lib/smartyTemplatesManager/views/selectInput.tpl`
  - **Output:** Renderizza un campo di input select/dropdown generico.

### 4.7 Schema del Database e Mappa degli Hook

#### Tabelle del Database

Nessun file SQL personalizzato (`.sql`) è stato identificato e nessuna classe `ObjectModel` è stata elencata. Ciò suggerisce fortemente che il modulo memorizza i suoi dati di configurazione e le definizioni dei blocchi di prodotti principalmente all'interno della tabella `ps_configuration` di PrestaShop.

- **`ps_configuration`**: Questa tabella conterrà voci con chiavi come `HPP_ANALYTICS_ENABLED`, `HPP_CACHE_TTL`, `HPP_BLOCKS_DATA` (o simili, dove `HPP_BLOCKS_DATA` conterrebbe un array serializzato o una stringa JSON di tutte le configurazioni dei blocchi di prodotti).

#### Tabella degli Hook Registrati

Il modulo si registra a vari hook di PrestaShop per iniettare il suo contenuto e la sua funzionalità.

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Inietta risorse CSS e JS (ad esempio, LightSlider, `hpp.css`, `script.js`). |
| `actionFrontControllerSetMedia` | Prima che un controller front-office renderizzi il suo output. | Aggiunge risorse CSS/JS specifiche condizionalmente in base alla pagina o al controller. |
| `displayHome` | Area del contenuto principale della homepage. | Renderizza blocchi di prodotti generali (caroselli, griglie) direttamente sulla homepage. |
| `displayHomeTab` | All'interno dell'area di navigazione delle schede della homepage. | Renderizza i link di navigazione per le schede di prodotti personalizzate. |
| `displayHomeTabContent` | All'interno dell'area del contenuto delle schede della homepage. | Renderizza i blocchi di prodotti effettivi che appaiono quando una scheda personalizzata è attiva. |
| `displayLeftColumn` | Nella colonna sinistra delle pagine in cui è attiva. | Renderizza blocchi di prodotti verticali nella sidebar sinistra. |
| `displayRightColumn` | Nella colonna destra delle pagine in cui è attiva. | Renderizza blocchi di prodotti verticali nella sidebar destra. |
| `displayTopColumn` | Nell'area del contenuto superiore, solitamente sotto l'header. | Renderizza blocchi di prodotti nella sezione superiore della homepage. |
| `displayBackOfficeHeader` | Nella sezione `<head>` di ogni pagina del back-office. | Inietta risorse CSS e JS per le pagine di configurazione del back-office del modulo. |
| `actionAdminControllerSetMedia` | Prima che un controller admin renderizzi il suo output. | Aggiunge risorse CSS/JS specifiche per le pagine admin del modulo. |
| `actionProductUpdate` | Dopo che un prodotto viene aggiornato nel back-office. | Potenzialmente svuota la cache per i blocchi contenenti questo prodotto, o re-indicizza i dati del prodotto. |
| `actionProductDelete` | Dopo che un prodotto viene eliminato nel back-office. | Potenzialmente svuota la cache per i blocchi contenenti questo prodotto, o lo rimuove dalle configurazioni dei blocchi. |
| `actionCategoryUpdate` | Dopo che una categoria viene aggiornata nel back-office. | Potenzialmente svuota la cache per i blocchi che visualizzano prodotti da questa categoria. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Homepage Products Pro", fai riferimento al tuo account cliente su MyPresta.eu. Il nostro team di supporto dedicato è disponibile per assisterti con qualsiasi problema tecnico o domanda tu possa avere.

- **MyPresta.eu Cronologia Ordini e Download:** <https://mypresta.eu/my-account/orders/>
- **MyPresta.eu Contatto Supporto:** <https://mypresta.eu/contact>
