---
title: "Unisci Prodotti - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Unisci Prodotti di MyPresta.eu."
sidebar:
  label: "Unisci Prodotti - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Merge Products su MyPresta.eu](https://mypresta.eu/modules/administration-tools/merge-products.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/merge-products/)
>
> ---


# Unisci Prodotti

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di Hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

Il modulo Unisci Prodotti offre una schermata di amministrazione dedicata per gestire il processo di unione, accessibile dal tuo back office di PrestaShop.

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)

Quando clicchi per la prima volta su "Configura" dopo l'installazione, verrai portato a una pagina simile a una dashboard. Questa pagina serve principalmente come punto di ingresso allo strumento di unione principale.

- **Cosa fa questa schermata:** Questa pagina di configurazione iniziale fornisce una breve panoramica e un link diretto allo strumento principale "Unisci Prodotti". Non contiene impostazioni specifiche, ma ti guida a dove avviene l'effettiva unione.
- **Effetto della modifica di questa impostazione:** Non ci sono impostazioni dirette da modificare su questa schermata iniziale.
- **Valore consigliato:** N/A
- **Scenario / esempio del commerciante:** Questo è il tuo punto di partenza. Da qui, cliccherai un pulsante o un link per accedere alla funzionalità principale del modulo.

### 2.2 Schermata Amministrativa Dedicata: Strumento Unisci Prodotti (Back Office > Catalogo > Unisci Prodotti)

Questa è l'interfaccia principale dove eseguirai tutte le operazioni di unione dei prodotti. Puoi trovarla navigando su **Catalogo > Unisci Prodotti** nel menu del tuo back office di PrestaShop.

Questa schermata è divisa in diverse sezioni per guidarti attraverso il processo di unione:

#### Passaggio 1: Seleziona Prodotto Master

- **Cosa fa questa sezione:** Qui, definisci il prodotto "master". Questo è il prodotto in cui tutti gli altri prodotti "sorgente" selezionati verranno uniti, diventando le sue combinazioni.
- **Campo di input: "Cerca un prodotto"**
  - **Cosa fa questa impostazione:** Ti permette di cercare un prodotto esistente nel tuo catalogo per designarlo come prodotto master. Puoi cercare per nome prodotto, ID, EAN o riferimento.
  - **Effetto della modifica di questa impostazione:** Mentre digiti, apparirà un elenco di completamento automatico. Selezionando un prodotto, l'area "Prodotto Master" verrà popolata con i suoi dettagli. Questo prodotto sarà la base per le nuove combinazioni.
  - **Valore consigliato:** Scegli il prodotto che meglio rappresenta l'elenco consolidato. Ad esempio, se stai unendo "Maglietta Rossa S", "Maglietta Rossa M", "Maglietta Rossa L" in uno solo, potresti scegliere "Maglietta Rossa S" come master, e gli altri diventeranno le sue combinazioni.
  - **Scenario / esempio del commerciante:** Hai "iPhone 13 (Nuovo)" e "iPhone 13 (Ricondizionato)" come prodotti separati. Cercheresti e selezioneresti "iPhone 13 (Nuovo)" come tuo prodotto master.

#### Passaggio 2: Seleziona Prodotti Sorgente

- **Cosa fa questa sezione:** Qui, selezioni i prodotti che verranno convertiti in combinazioni e aggiunti al prodotto master.
- **Campo di input: "Cerca prodotti da unire"**
  - **Cosa fa questa impostazione:** Simile alla ricerca del prodotto master, questo campo ti permette di trovare e selezionare più prodotti che diventeranno combinazioni.
  - **Effetto della modifica di questa impostazione:** Ogni prodotto selezionato viene aggiunto a un elenco sottostante. Questi sono i prodotti i cui dati (prezzo, stock, attributi) verranno trasferiti al prodotto master come nuove combinazioni.
  - **Valore consigliato:** Seleziona tutti i prodotti che sono varianti del tuo prodotto master scelto e che dovrebbero essere consolidati.
  - **Scenario / esempio del commerciante:** Seguendo l'esempio dell'iPhone, cercheresti e selezioneresti "iPhone 13 (Ricondizionato)" qui. Se avessi anche "iPhone 13 (Usato - Grado A)", lo selezioneresti anche.

#### Passaggio 3: Configura Opzioni di Unione

Questa sezione contiene impostazioni critiche che controllano come viene eseguita l'operazione di unione.

- **Opzione: Modalità di Unione**

  - **Cosa fa questa impostazione:** Determina come vengono gestiti gli attributi dei prodotti sorgente durante la creazione delle combinazioni.
  - **Effetto della modifica di questa impostazione:**
    - *Aggiungi un nuovo gruppo di attributi:* Il modulo creerà un nuovo gruppo di attributi (es. "Condizione") e un attributo per ogni prodotto sorgente (es. "Nuovo", "Ricondizionato", "Usato"). Questo è l'ideale quando i prodotti sorgente differiscono per una caratteristica non già coperta da attributi esistenti.
    - *Usa gruppo di attributi esistente:* Se i tuoi prodotti sorgente condividono già un gruppo di attributi comune (es. "Taglia" o "Colore") e vuoi unirli in base a quello, puoi selezionarlo. Questo è meno comune per l'unione di prodotti completamente separati, ma utile per consolidare varianti all'interno di una struttura di attributi esistente.
  - **Valore consigliato:** **"Aggiungi un nuovo gruppo di attributi"** è generalmente consigliato per unire prodotti distinti, in quanto fornisce un modo chiaro per differenziare le nuove combinazioni.
  - **Scenario / esempio del commerciante:** Stai unendo "Prodotto X - Nuovo" e "Prodotto X - Usato". Selezionando "Aggiungi un nuovo gruppo di attributi" verrà creato un gruppo di attributi "Condizione" con attributi "Nuovo" e "Usato" per le combinazioni.
- **Campo di input: Nome Nuovo Gruppo Attributi (visibile solo se è selezionato "Aggiungi un nuovo gruppo di attributi")**

  - **Cosa fa questa impostazione:** Specifica il nome per il nuovo gruppo di attributi che verrà creato per differenziare le combinazioni unite.
  - **Effetto della modifica di questa impostazione:** Questo nome apparirà sulla tua pagina prodotto (es. "Condizione", "Grado", "Versione").
  - **Valore consigliato:** Un nome descrittivo come "Condizione", "Stato", "Tipo" o "Grado".
  - **Scenario / esempio del commerciante:** Se stai unendo prodotti "Nuovo" e "Usato", potresti inserire "Condizione".
- **Opzione: Regola Prodotto Master**

  - **Cosa fa questa impostazione:** Definisce come viene trattato il prodotto master stesso durante l'unione.
  - **Effetto della modifica di questa impostazione:**
    - *Mantieni come prodotto master:* Il prodotto master rimane come prodotto predefinito e i prodotti sorgente diventano le sue combinazioni. Le sue combinazioni esistenti (se presenti) vengono preservate.
    - *Converti in combinazione:* Il prodotto master stesso viene anch'esso convertito in una combinazione sotto la sua stessa scheda. Questo è utile se vuoi che tutte le varianti, incluso il master originale, siano selezionabili tramite il nuovo gruppo di attributi.
  - **Valore consigliato:** **"Mantieni come prodotto master"** è spesso sufficiente. Scegli "Converti in combinazione" se vuoi che lo stato originale del prodotto master sia esplicitamente selezionabile come combinazione.
  - **Scenario / esempio del commerciante:** Se "iPhone 13 (Nuovo)" è il tuo master e unisci "iPhone 13 (Ricondizionato)" in esso, "Mantieni come prodotto master" significa che "iPhone 13 (Nuovo)" è il predefinito. Se scegli "Converti in combinazione", allora "Nuovo" diventerebbe un'opzione selezionabile insieme a "Ricondizionato".
- **Opzione: Azione Prodotto Sorgente**

  - **Cosa fa questa impostazione:** Determina cosa succede ai prodotti sorgente originali dopo che sono stati uniti al prodotto master come combinazioni.
  - **Effetto della modifica di questa impostazione:**
    - *Disattiva:* Le pagine dei prodotti sorgente originali verranno disabilitate, rendendole inaccessibili ai clienti. Questa è generalmente l'opzione più sicura.
    - *Elimina:* Le pagine dei prodotti sorgente originali verranno rimosse permanentemente dal tuo catalogo. Usa con cautela, poiché questa azione è irreversibile.
    - *Non fare nulla:* Le pagine dei prodotti sorgente originali rimangono attive. Questo è generalmente sconsigliato in quanto può portare a contenuti duplicati e confusione.
  - **Valore consigliato:** **"Disattiva"** è la scelta più sicura e comune. Se sei sicuro della tua unione e dei reindirizzamenti, "Elimina" può pulire il tuo catalogo, ma assicurati di avere dei backup.
  - **Scenario / esempio del commerciante:** Dopo aver unito "iPhone 13 (Ricondizionato)" in "iPhone 13 (Nuovo)", in genere sceglieresti "Disattiva" per impedire ai clienti di trovare la vecchia pagina del prodotto "Ricondizionato".
- **Opzione: Crea Reindirizzamenti 301**

  - **Cosa fa questa impostazione:** Se abilitata, il modulo creerà reindirizzamenti permanenti (301) dai vecchi URL dei prodotti sorgente al nuovo URL del prodotto master.
  - **Effetto della modifica di questa impostazione:**
    - *Abilitato:* Qualsiasi cliente o motore di ricerca che tenti di accedere a un vecchio URL di un prodotto sorgente verrà automaticamente inviato alla pagina del prodotto master. Questo è cruciale per la SEO, preservando l'equità dei link e prevenendo link interrotti.
    - *Disabilitato:* I vecchi URL dei prodotti sorgente porteranno a un errore "pagina non trovata" se il prodotto sorgente è disattivato o eliminato.
  - **Valore consigliato:** **SÌ (Abilitato)**. Questo è altamente raccomandato per la SEO e l'esperienza utente.
  - **Scenario / esempio del commerciante:** Un cliente ha aggiunto ai preferiti la vecchia pagina "iPhone 13 (Ricondizionato)". Con i reindirizzamenti abilitati, atterrerà automaticamente sulla pagina master "iPhone 13".
- **Opzione: Dimensione Batch**

  - **Cosa fa questa impostazione:** Controlla quanti prodotti vengono elaborati in un singolo batch durante l'operazione di unione. Questa è un'impostazione tecnica per prevenire timeout del server per unioni di grandi dimensioni.
  - **Effetto della modifica di questa impostazione:** Un numero inferiore riduce il carico del server ma rende il processo più lungo. Un numero superiore lo velocizza ma potrebbe causare problemi su hosting meno potenti.
  - **Valore consigliato:** Lascia il valore predefinito a meno che non si verifichino timeout. In tal caso, prova a ridurlo.
  - **Scenario / esempio del commerciante:** Se stai unendo centinaia di prodotti e il processo fallisce, ridurre la dimensione del batch potrebbe aiutare.
- **Opzione: Solo Prodotti Attivi**

  - **Cosa fa questa impostazione:** Se abilitata, solo i prodotti sorgente attivi verranno considerati per l'unione.
  - **Effetto della modifica di questa impostazione:**
    - *Abilitato:* Impedisce che i prodotti inattivi vengano uniti, il che può semplificare il processo ed evitare di creare combinazioni per prodotti che non intendi vendere.
    - *Disabilitato:* Tutti i prodotti, attivi o inattivi, possono essere uniti.
  - **Valore consigliato:** **SÌ (Abilitato)**, a meno che tu non abbia specificamente bisogno di unire prodotti inattivi.
  - **Scenario / esempio del commerciante:** Vuoi unire solo i prodotti attualmente visibili e acquistabili nel tuo negozio.
- **Opzione: Escludi Pacchetti**

  - **Cosa fa questa impostazione:** Se abilitata, i prodotti configurati come "pacchetti" (bundle di altri prodotti) verranno esclusi dalla selezione dei prodotti sorgente.
  - **Effetto della modifica di questa impostazione:** Previene l'unione accidentale di pacchetti di prodotti, che hanno relazioni complesse e potrebbero non comportarsi come previsto quando convertiti in combinazioni.
  - **Valore consigliato:** **SÌ (Abilitato)**. L'unione di pacchetti può portare a comportamenti inaspettati.
  - **Scenario / esempio del commerciante:** Hai un pacchetto "Kit di Avvio". Non vuoi che questo venga unito come combinazione in un altro prodotto.
- **Opzione: Escludi Prodotti Virtuali**

  - **Cosa fa questa impostazione:** Se abilitata, i prodotti virtuali (es. file scaricabili, servizi) verranno esclusi dalla selezione dei prodotti sorgente.
  - **Effetto della modifica di questa impostazione:** Previene l'unione accidentale di prodotti virtuali, che tipicamente non hanno attributi fisici o stock e potrebbero non essere adatti alla conversione in combinazioni.
  - **Valore consigliato:** **SÌ (Abilitato)**. I prodotti virtuali di solito non sono buoni candidati per l'unione in combinazioni di prodotti fisici.
  - **Scenario / esempio del commerciante:** Vendi un e-book scaricabile. Non vuoi che questo venga unito come combinazione in un prodotto libro fisico.
- **Opzione: Dimensione Minima Gruppo**

  - **Cosa fa questa impostazione:** Imposta un numero minimo di prodotti sorgente richiesti per formare un nuovo gruppo di attributi.
  - **Effetto della modifica di questa impostazione:** Questa è una salvaguardia. Se selezioni "Aggiungi un nuovo gruppo di attributi" ma unisci solo un prodotto sorgente, questa impostazione può impedire la creazione di un gruppo di attributi non necessario con una sola opzione.
  - **Valore consigliato:** Lascia il valore predefinito (solitamente 2).
  - **Scenario / esempio del commerciante:** Se selezioni accidentalmente un solo prodotto sorgente, questo può impedire al modulo di creare un gruppo di attributi con una sola opzione, il che è ridondante.
- **Opzione: Gruppo Attributi da Usare (visibile solo se è selezionato "Usa gruppo di attributi esistente")**

  - **Cosa fa questa impostazione:** Ti permette di selezionare un gruppo di attributi esistente dal tuo negozio per categorizzare le nuove combinazioni.
  - **Effetto della modifica di questa impostazione:** Il modulo tenterà di mappare i prodotti sorgente agli attributi all'interno di questo gruppo scelto. Ciò richiede un'attenta pianificazione per garantire che i tuoi prodotti sorgente si adattino logicamente alla struttura degli attributi esistente.
  - **Valore consigliato:** Usa solo se hai uno scenario molto specifico in cui i prodotti sorgente sono già varianti di un attributo esistente. Altrimenti, "Aggiungi un nuovo gruppo di attributi" è più sicuro.
  - **Scenario / esempio del commerciante:** Hai prodotti "Camicia - Blu" e "Camicia - Rossa" come prodotti separati, e vuoi unirli in un prodotto master "Camicia", usando il gruppo di attributi "Colore" esistente.

#### Passaggio 4: Rivedi e Unisci

- **Pulsante: "Unisci Prodotti"**
  - **Cosa fa questo pulsante:** Avvia il processo di unione effettivo in base alle tue selezioni e configurazioni.
  - **Effetto del clic:** Il modulo elaborerà i prodotti sorgente selezionati, li convertirà in combinazioni, li assegnerà al prodotto master, aggiornerà stock e prezzi ed eseguirà reindirizzamenti/disattivazioni come configurato. Verrà visualizzata una barra di avanzamento o un messaggio di successo.
  - **Azione consigliata:** Rivedi attentamente tutte le tue selezioni prima di cliccare. Assicurati di avere un backup del tuo negozio.
  - **Scenario / esempio del commerciante:** Dopo aver selezionato "iPhone 13 (Nuovo)" come master, "iPhone 13 (Ricondizionato)" come sorgente, impostato "Condizione" come nuovo gruppo di attributi e abilitato i reindirizzamenti 301, clicchi su "Unisci Prodotti" per eseguire il consolidamento.

#### Tabella di Riferimento Rapido della Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Strumento Unisci Prodotti** | **Ricerca Prodotto Master** | N/A | Seleziona il prodotto principale a cui gli altri verranno uniti. |
|  | **Ricerca Prodotti Sorgente** | N/A | Seleziona i prodotti da convertire in combinazioni sotto il master. |
|  | **Modalità di Unione** | Aggiungi un nuovo gruppo di attributi | Determina se viene creato un nuovo gruppo di attributi o se ne viene usato uno esistente per le combinazioni. |
|  | **Nome Nuovo Gruppo Attributi** | Nome descrittivo (es. "Condizione") | Nome per il gruppo di attributi creato per differenziare le combinazioni unite. |
|  | **Regola Prodotto Master** | Mantieni come prodotto master | Definisce se il prodotto master stesso diventa una combinazione o rimane il predefinito. |
|  | **Azione Prodotto Sorgente** | Disattiva | Cosa succede alle pagine dei prodotti sorgente originali dopo l'unione (Disattiva, Elimina, Non fare nulla). |
|  | **Crea Reindirizzamenti 301** | SÌ | Crea reindirizzamenti permanenti dai vecchi URL sorgente al nuovo URL master. Cruciale per la SEO. |
|  | **Dimensione Batch** | Predefinito (es. 10) | Numero di prodotti elaborati per batch. Regola per le prestazioni del server. |
|  | **Solo Prodotti Attivi** | SÌ | Limita la selezione dei prodotti sorgente ai soli prodotti attivi. |
|  | **Escludi Pacchetti** | SÌ | Impedisce che i pacchetti di prodotti vengano selezionati come prodotti sorgente. |
|  | **Escludi Prodotti Virtuali** | SÌ | Impedisce che i prodotti virtuali vengano selezionati come prodotti sorgente. |
|  | **Dimensione Minima Gruppo** | Predefinito (es. 2) | Numero minimo di prodotti sorgente per creare un nuovo gruppo di attributi. |
|  | **Gruppo Attributi da Usare** | N/A (solo se modalità "Usa esistente...") | Seleziona un gruppo di attributi esistente per la mappatura delle combinazioni. |
|  | **Pulsante Unisci Prodotti** | Clicca dopo la revisione | Esegue l'operazione di unione. |

## 3. Risoluzione dei Problemi del Commerciante e Domande Frequenti (FAQ)

**D1: Dopo l'unione, non vedo le nuove combinazioni sulla mia pagina prodotto.**
R1: Innanzitutto, svuota la cache di PrestaShop. Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota la cache" in alto a destra. Se il problema persiste, controlla il prodotto master nel tuo Back Office per assicurarti che le combinazioni siano state create correttamente e siano attive. Inoltre, verifica che il gruppo di attributi creato dal modulo sia abilitato e associato al prodotto master.

**D2: I miei vecchi URL dei prodotti mostrano errori "Pagina non trovata".**
R2: Questo di solito significa che i reindirizzamenti 301 non sono stati creati o non funzionano.
1. Torna allo strumento "Unisci Prodotti" (**Catalogo > Unisci Prodotti**).
2. Controlla se l'opzione "Crea Reindirizzamenti 301" era abilitata durante l'unione. In caso contrario, dovrai impostare manualmente i reindirizzamenti o riunire (dopo aver ripristinato un backup se hai eliminato i prodotti sorgente).
3. Assicurati che il file `.htaccess` del tuo server sia configurato correttamente per gestire gli URL amichevoli e i reindirizzamenti di PrestaShop. A volte, le configurazioni del server possono interferire.

**D3: Il modulo sembra bloccarsi o andare in timeout durante il processo di unione.**
R3: Questo può accadere con un gran numero di prodotti o su server con risorse limitate.
1. Prova a ridurre l'impostazione **"Dimensione Batch"** nella sezione "Configura Opzioni di Unione" del modulo. Una dimensione di batch più piccola (es. 5 o 10) elaborerà meno prodotti alla volta, riducendo il carico del server.
2. Controlla le impostazioni PHP `max_execution_time` e `memory_limit` del tuo server. Potrebbe essere necessario aumentare temporaneamente questi valori (contatta il tuo provider di hosting se non sei sicuro).

**D4: Posso annullare un'operazione di unione?**
R4: Il modulo non ha un pulsante "annulla". Ecco perché i **backup sono assolutamente critici**. Se devi annullare, devi ripristinare il tuo negozio da un backup effettuato *prima* dell'unione. Se hai solo disattivato i prodotti sorgente e non li hai eliminati, potresti riattivarli manualmente ed eliminare le combinazioni appena create dal prodotto master, ma questo è un processo manuale complesso.

**D5: Cosa succede se il mio tema personalizzato non visualizza correttamente il nuovo gruppo di attributi?**
R5: Il modulo crea gruppi di attributi e combinazioni standard di PrestaShop. Se il tuo tema non li visualizza correttamente, è probabile che sia un problema di CSS o di template Smarty all'interno del tuo tema.
1. Controlla se i temi PrestaShop predefiniti (es. Classic) visualizzano correttamente le combinazioni. Se lo fanno, il problema è con il tuo tema personalizzato.
2. Potrebbe essere necessario consultare uno sviluppatore web per regolare il file `product.tpl` del tuo tema o il CSS associato per renderizzare correttamente i nuovi selettori di attributi.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'Architettura

Il modulo `Unisci Prodotti` segue un pattern MVC standard di PrestaShop per i suoi componenti di Back Office. Sfrutta `ObjectModel` di PrestaShop per la manipolazione dei dati (anche se interagisce principalmente con gli oggetti `Product` e `Combination` direttamente piuttosto che con modelli personalizzati specifici del modulo). La logica principale per trovare, costruire e unire prodotti e le loro combinazioni è incapsulata in classi di servizio dedicate. Il modulo utilizza un Controller Admin personalizzato per la sua interfaccia principale, fornendo una griglia e un modulo user-friendly per il processo di unione. Implementa anche un meccanismo di logging per tracciare le operazioni di unione.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**: Nessuno. Il modulo è puramente uno strumento di amministrazione del Back-Office.
- **Controller Admin Back-Office**:

  - `controllers/admin/AdminMyMergeProductsController.php`

    - **Nome Classe**: `AdminMyMergeProductsController`
    - **Classe Padre**: `ModuleAdminController`
    - **Responsabilità**: Questo è il controller primario per l'interfaccia amministrativa del modulo. Gestisce la visualizzazione dello strumento di unione, inclusa la ricerca prodotti (autocomplete), le opzioni di configurazione e l'avvio del processo di unione. Orchestra le chiamate alle classi di servizio principali (`MmpFinder`, `MmpMergeEngine`, `MmpLogger`, `MmpRedirector`) per eseguire l'effettiva unione. Gestisce l'invio del modulo e visualizza il feedback all'utente.
    - **Nome Tab**: "Unisci Prodotti" (sotto il menu Catalogo)
    - **Entità Gestita**: Prodotti e le loro combinazioni, attributi.
  - `controllers/admin/index.php`

    - **Nome Classe**: N/A (file vuoto)
    - **Classe Padre**: N/A
    - **Responsabilità**: Questo è un file `index.php` vuoto standard, spesso posizionato nelle directory per prevenire l'elenco delle directory sui server web. Non ha alcun ruolo funzionale nella logica del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

- `classes/index.php`

  - **Responsabilità**: File `index.php` vuoto standard per prevenire l'elenco delle directory.
- `classes/MmpCombinationBuilder.php`

  - **Nome Classe**: `MmpCombinationBuilder`
  - **Classe Padre**: Nessuna (classe di servizio standalone)
  - **Responsabilità**: Questa classe è responsabile della logica intricata di creazione di nuove combinazioni di prodotti basate sui prodotti sorgente. Gestisce:
    - La mappatura dei dati del prodotto sorgente (prezzo, quantità, EAN, riferimento) alle nuove combinazioni.
    - La creazione di nuovi attributi e gruppi di attributi se `MMP_MERGE_MODE` è impostato su "Aggiungi un nuovo gruppo di attributi".
    - L'assegnazione di attributi esistenti alle nuove combinazioni.
    - La gestione delle immagini per le combinazioni.
    - L'assicurazione che le regole di stock e prezzo siano correttamente applicate alle nuove combinazioni.
- `classes/MmpFinder.php`

  - **Nome Classe**: `MmpFinder`
  - **Classe Padre**: Nessuna (classe di servizio standalone)
  - **Responsabilità**: Fornisce metodi per la ricerca e il recupero di prodotti basati su vari criteri (ID, nome, EAN, riferimento). Questa classe è utilizzata da `AdminMyMergeProductsController` per la funzionalità di ricerca con completamento automatico sia per i prodotti master che per quelli sorgente. Filtra anche i prodotti in base alla configurazione del modulo (es. `MMP_ACTIVE_ONLY`, `MMP_EXCLUDE_PACKS`, `MMP_EXCLUDE_VIRTUAL`).
- `classes/MmpLogger.php`

  - **Nome Classe**: `MmpLogger`
  - **Classe Padre**: Nessuna (classe di servizio standalone)
  - **Responsabilità**: Gestisce la registrazione delle operazioni di unione. Registra i dettagli di ogni unione, inclusi il prodotto master, i prodotti sorgente e le impostazioni di configurazione utilizzate. Questo è cruciale per il debug e l'audit. Probabilmente memorizza i log in una tabella di database personalizzata o in un file.
- `classes/MmpMergeEngine.php`

  - **Nome Classe**: `MmpMergeEngine`
  - **Classe Padre**: Nessuna (classe di servizio standalone)
  - **Responsabilità**: Questo è l'orchestratore centrale per il processo di unione. Prende il prodotto master e i prodotti sorgente, insieme alle impostazioni di configurazione, e coordina le azioni:
    - Chiama `MmpCombinationBuilder` per creare combinazioni.
    - Aggiorna il prodotto master.
    - Gestisce l'`MMP_SOURCE_ACTION` (disattiva o elimina i prodotti sorgente).
    - Gestisce l'elaborazione batch (`MMP_BATCH_SIZE`).
    - Interagisce con `MmpRedirector` per i reindirizzamenti 301.
    - Utilizza `MmpLogger` per registrare l'operazione.
- `classes/MmpRedirector.php`

  - **Nome Classe**: `MmpRedirector`
  - **Classe Padre**: Nessuna (classe di servizio standalone)
  - **Responsabilità**: Gestisce la creazione di reindirizzamenti 301. Quando `MMP_REDIRECT` è abilitato, questa classe crea voci nella tabella `ps_product_redirect` di PrestaShop (o meccanismo simile) per reindirizzare i vecchi URL dei prodotti sorgente al nuovo URL del prodotto master.

### 4.4 Risorse JavaScript (`views/js/`)

- `lib/searchTool/views/js/autocomplete.js`

  - **Ambito**: Back-office.
  - **Responsabilità**: Fornisce la logica JavaScript per i campi di ricerca con completamento automatico dei prodotti utilizzati in `AdminMyMergeProductsController`. Probabilmente utilizza AJAX per interrogare `MmpFinder` per suggerimenti di prodotti mentre l'utente digita, visualizzando i risultati in un menu a discesa. Gestisce la selezione e il popolamento dei rispettivi campi prodotto.
- `views/js/admin.js`

  - **Ambito**: Back-office.
  - **Responsabilità**: Contiene funzionalità JavaScript generali per l'interfaccia amministrativa del modulo. Questo potrebbe includere:
    - Visualizzazione condizionale dei campi di configurazione (es. `Nome Nuovo Gruppo Attributi` visibile solo se è selezionato "Aggiungi un nuovo gruppo di attributi").
    - Validazione del modulo.
    - Chiamate AJAX per avviare il processo di unione e visualizzare l'avanzamento.
    - Listener di eventi per pulsanti e modifiche del modulo.

### 4.5 Fogli di Stile CSS (`views/css/`)

- `lib/searchTool/views/css/autocomplete.css`

  - **Ambito**: Stile amministrativo del Back-office.
  - **Responsabilità**: Stila il menu a discesa di completamento automatico e i campi di input di ricerca, assicurando che siano visivamente coerenti e user-friendly all'interno del Back Office di PrestaShop.
- `views/css/admin.css`

  - **Ambito**: Stile amministrativo del Back-office.
  - **Responsabilità**: Fornisce uno stile specifico per l'interfaccia di `AdminMyMergeProductsController`, inclusa la disposizione delle sezioni, lo stile degli elenchi di prodotti e miglioramenti visivi generali per la pagina di configurazione del modulo.

### 4.6 Struttura del Template Smarty (`views/templates/`)

- `lib/searchTool/views/scripts.tpl`

  - **Ambito**: Back-office.
  - **Responsabilità**: Questo template probabilmente include il JavaScript e il CSS necessari per lo strumento di ricerca con completamento automatico, assicurando che sia caricato nelle pagine amministrative pertinenti. Potrebbe contenere tag `script` e `link`.
- `views/templates/admin/configure_shell.tpl`

  - **Ambito**: Amministrazione Back-office.
  - **Responsabilità**: Questo template funge da wrapper o shell per il contenuto principale della configurazione del modulo. Potrebbe includere elementi comuni di intestazione/piè di pagina, navigazione o struttura generale del layout per le pagine amministrative del modulo. Probabilmente include `dashboard.tpl`.
- `views/templates/admin/dashboard.tpl`

  - **Ambito**: Amministrazione Back-office.
  - **Responsabilità**: Questo è il template principale per la vista `AdminMyMergeProductsController`. Renderizza l'intera interfaccia dello strumento di unione, inclusi:
    - L'area di selezione del prodotto master.
    - L'area di selezione dei prodotti sorgente.
    - Il modulo delle opzioni di configurazione dell'unione (con tutte le impostazioni come `MMP_MERGE_MODE`, `MMP_REDIRECT`, ecc.).
    - Il pulsante "Unisci Prodotti".
    - Eventuali messaggi di stato o indicatori di avanzamento durante l'unione.

### 4.7 Schema del Database e Mappa degli Hook

- **Tabelle del Database**:

  - Il modulo interagisce principalmente con le tabelle core esistenti di PrestaShop:
    - `ps_product`: Per recuperare le informazioni sui prodotti e aggiornare lo stato dei prodotti (attivo/inattivo).
    - `ps_product_attribute`: Per creare e gestire le combinazioni di prodotti.
    - `ps_product_attribute_shop`: Per i dati delle combinazioni specifici del negozio.
    - `ps_product_attribute_combination`: Collega le combinazioni agli attributi.
    - `ps_attribute_group`, `ps_attribute_group_lang`, `ps_attribute_group_shop`: Per creare nuovi gruppi di attributi.
    - `ps_attribute`, `ps_attribute_lang`, `ps_attribute_shop`: Per creare nuovi attributi.
    - `ps_stock_available`: Per aggiornare le quantità di stock per le combinazioni.
    - `ps_product_lang`: Per i nomi e le descrizioni dei prodotti.
    - `ps_product_shop`: Per i dati dei prodotti specifici del negozio.
    - `ps_url_rewrite`: Per gestire gli URL amichevoli.
    - `ps_configuration`: Memorizza le impostazioni di configurazione del modulo (es. `MMP_MERGE_MODE`, `MMP_MASTER_RULE`, `MMP_SOURCE_ACTION`, `MMP_REDIRECT`, `MMP_BATCH_SIZE`, `MMP_ACTIVE_ONLY`, `MMP_EXCLUDE_PACKS`, `MMP_EXCLUDE_VIRTUAL`, `MMP_MIN_GROUP`, `MMP_ATTRIBUTE_GROUP`, `MMP_ATTRIBUTE_GROUP_NAME`).
  - Il modulo potrebbe creare una tabella personalizzata per la registrazione delle operazioni di unione (es. `ps_mmp_log` o simile), anche se questo non è esplicitamente dettagliato nell'inventario fornito. Se esiste, memorizzerebbe i record di ogni evento di unione.
  - Per i reindirizzamenti 301, probabilmente utilizza la tabella `ps_product_redirect` di PrestaShop (o un meccanismo simile se il modulo implementa il proprio gestore di reindirizzamenti).
- **Tabella degli Hook Registrati**:
  Il modulo non registra esplicitamente alcun hook front-office (come `displayHeader`, `displayProductButtons`, ecc.) in quanto è uno strumento di back-office. La sua interazione principale con il sistema di hook di PrestaShop sarebbe per:

  - `actionAdminControllerSetMedia`: Per caricare i suoi file CSS e JS specifici nel Back Office.
  - `actionProductUpdate` / `actionProductAdd` / `actionProductDelete`: Sebbene non esplicitamente elencata, la logica interna del modulo per la modifica dei prodotti potrebbe attivare questi hook core di PrestaShop, ai quali altri moduli potrebbero essere in ascolto.
  - `actionObjectProductAddAfter`, `actionObjectProductUpdateAfter`, `actionObjectProductDeleteAfter`: Hook di ObjectModel che verrebbero attivati quando il modulo crea, aggiorna o elimina oggetti `Product` o `ProductAttribute`.

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Unisci Prodotti", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema tecnico o domanda tu possa avere riguardo alla funzionalità del modulo.
