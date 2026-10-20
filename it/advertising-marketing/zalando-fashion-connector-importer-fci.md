---
title: "Zalando Fashion Connector Importer (FCI) - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Zalando Fashion Connector Importer (FCI) di MyPresta.eu."
sidebar:
  label: "Zalando Fashion Connector Importer (FCI) - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Zalando Fashion Connector Importer (FCI) su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/zalando-fashion-connector-importer-fci.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/zalando-fashion-connector-importer-fci/)
>
> ---


# Zalando Fashion Connector Importer (FCI)

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per la maggior parte dei moduli PrestaShop e sono solitamente disponibili su qualsiasi ambiente di hosting moderno.

## 2. Panoramica completa della configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Zalando Fashion Connector Importer (FCI))

Questa è la schermata di configurazione principale dove imposti i parametri di base per il tuo feed Zalando.

-   **Cosa fa questa impostazione:** Questa sezione ti consente di definire le informazioni principali che saranno incluse nel tuo feed di prodotti Zalando.
-   **Effetto della modifica di questa impostazione:** I valori che imposti qui influenzeranno direttamente i dati che Zalando riceve sui tuoi prodotti, influenzando il modo in cui vengono visualizzati e gestiti sulla loro piattaforma.

| Impostazione / Opzione | Cosa fa questa impostazione | Effetto della modifica di questa impostazione | Valore consigliato | Scenario / esempio del commerciante |
| :---------------------- | :-------------------------- | :------------------------------------------ | :---------------- | :---------------------------------- |
| **Negozio** | Specifica il nome del tuo negozio come dovrebbe apparire su Zalando. Questo aiuta Zalando a identificare il tuo specifico punto vendita. | *Se impostato:* Il nome del tuo negozio specificato sarà incluso nel feed di prodotti. *Se lasciato vuoto:* Zalando potrebbe utilizzare un identificatore predefinito o rifiutare il feed se il nome del negozio è obbligatorio. | Il nome effettivo del tuo negozio (es. "La Mia Boutique di Moda") | Se hai più negozi fisici o marchi, questo aiuta Zalando a differenziare il tuo inventario. |
| **EAN (European Article Number)** | Determina se l'EAN (codice a barre) dei tuoi prodotti deve essere incluso nel feed. Gli EAN sono cruciali per l'identificazione del prodotto. | *Se abilitato:* Gli EAN faranno parte del feed, consentendo a Zalando di abbinare accuratamente i tuoi prodotti. *Se disabilitato:* I prodotti potrebbero non essere identificati correttamente o potrebbero essere rifiutati da Zalando se l'EAN è un campo obbligatorio. | SÌ | Essenziale per la maggior parte degli elenchi di prodotti, specialmente nella moda, per garantire un'identificazione univoca. |
| **Prezzo** | Controlla se il prezzo di vendita del prodotto è incluso nel feed. | *Se abilitato:* Il prezzo di vendita corrente dal tuo negozio PrestaShop verrà inviato a Zalando. *Se disabilitato:* Zalando non riceverà aggiornamenti sui prezzi, portando potenzialmente a prezzi obsoleti sulla loro piattaforma. | SÌ | Cruciale per garantire che i clienti vedano il prezzo corretto su Zalando. |
| **Prezzo al dettaglio** | Determina se il prezzo al dettaglio originale (spesso il prezzo "barrato" per gli sconti) è incluso. | *Se abilitato:* Il prezzo originale verrà inviato, consentendo a Zalando di visualizzare risparmi o promozioni. *Se disabilitato:* Verrà inviato solo il prezzo di vendita corrente, nascondendo potenzialmente le informazioni sugli sconti. | SÌ (se utilizzi i prezzi al dettaglio per le promozioni) | Se fai saldi, includere il prezzo al dettaglio aiuta a evidenziare lo sconto ai clienti su Zalando. |
| **Quantità** | Specifica se la quantità di stock corrente dei tuoi prodotti è inclusa nel feed. | *Se abilitato:* I livelli di stock dei tuoi prodotti verranno aggiornati su Zalando, prevenendo l'overselling. *Se disabilitato:* Zalando non riceverà aggiornamenti sullo stock, portando a potenziali discrepanze e insoddisfazione del cliente se un articolo è esaurito. | SÌ | Assolutamente critico per evitare di vendere prodotti che non hai più disponibili. |
| **Nome del prodotto** | Controlla se il nome del prodotto è incluso nel feed. | *Se abilitato:* Il nome del prodotto dal tuo negozio PrestaShop verrà inviato a Zalando. *Se disabilitato:* I prodotti potrebbero essere elencati senza nomi o rifiutati se questo è un campo obbligatorio. | SÌ | Essenziale per i clienti per identificare e cercare i tuoi prodotti su Zalando. |
| **ID Cliente (zf\_client)** | Il tuo identificatore cliente univoco fornito da Zalando per l'accesso API. | *Se inserito correttamente:* Consente al modulo di autenticarsi con i sistemi di Zalando. *Se errato o vuoto:* La generazione e gli aggiornamenti del feed falliranno. | L'ID fornito da Zalando | Devi ottenerlo dal tuo account manager di Zalando Connected Retail. |
| **Chiave API (zf\_api)** | La tua chiave API univoca fornita da Zalando per una comunicazione sicura. | *Se inserito correttamente:* Abilita il trasferimento sicuro dei dati tra il tuo negozio e Zalando. *Se errato o vuoto:* La generazione e gli aggiornamenti del feed falliranno a causa di problemi di autenticazione. | La chiave fornita da Zalando | Questa è una credenziale di sicurezza; mantienila riservata e ottienila da Zalando. |

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### 2.2.1 Configurazione esportazione prodotti (Back Office > Zalando FCI > Esporta prodotti)

Questa schermata, accessibile tramite il menu del back office di PrestaShop, è dove definisci i parametri dettagliati per la generazione del tuo feed di prodotti per Zalando. Consente di ottimizzare quali dati sono inclusi e come sono formattati.

-   **Nome schermata e posizione nel menu:** **Zalando FCI > Esporta prodotti** (Questo apparirà come una nuova voce di menu nella navigazione del tuo Back Office di PrestaShop).
-   **Azioni e impostazioni disponibili:** Questa schermata presenta un modulo con numerose opzioni per personalizzare l'esportazione dei tuoi prodotti. Troverai campi per la selezione di negozi, valute, attributi di prodotto e opzioni di filtro.
-   **Effetto delle modifiche:** Le modifiche qui influiscono direttamente sul contenuto e sulla struttura del file di feed di prodotti generato. Impostazioni errate possono portare al rifiuto del tuo feed da parte di Zalando o alla visualizzazione di informazioni errate sui prodotti.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Inizialmente, configura attentamente tutte le impostazioni in base alle specifiche di Zalando e alle esigenze del tuo negozio.
    2.  Genera un feed di prova e convalidalo con Zalando (se possibile) per assicurarti che tutti i dati siano corretti.
    3.  Una volta configurato, utilizzerai principalmente questa schermata per generare il feed manualmente quando necessario, oppure imposterai un cron job (un'attività pianificata) per automatizzare la generazione del feed in base a queste impostazioni.

| Impostazione / Opzione | Cosa fa questa impostazione | Effetto della modifica di questa impostazione | Valore consigliato | Scenario / esempio del commerciante |
| :---------------------- | :-------------------------- | :------------------------------------------ | :---------------- | :---------------------------------- |
| **Ricorda impostazioni (zf\_remember\_settings)** | Se abilitato, il modulo ricorderà le tue ultime impostazioni di esportazione scelte per comodità. | *Se abilitato:* Le tue selezioni in questa pagina persisteranno per le esportazioni future. *Se disabilitato:* Le impostazioni torneranno ai valori predefiniti ogni volta che visiti la pagina. | SÌ | Risparmia tempo se generi frequentemente feed con gli stessi parametri. |
| **Formato file di esportazione (zf\_export\_file\_format)** | Seleziona il formato di output per il file di feed di prodotti (es. CSV, XML). | *Se impostato:* Il file generato sarà nel formato scelto. *Se errato:* Zalando potrebbe non essere in grado di elaborare il file. | Controlla i requisiti di Zalando (solitamente CSV o XML) | Zalando specificherà il formato richiesto per il loro sistema di importazione. |
| **Tipo di esportazione (zf\_export\_type)** | Definisce quale tipo di prodotti esportare (es. tutti i prodotti, solo attivi, solo categorie specifiche). | *Se impostato:* Verranno inclusi solo i prodotti che corrispondono ai criteri. *Se errato:* Potresti esportare troppi o troppo pochi prodotti. | Tutti i prodotti attivi, o secondo l'onboarding di Zalando | Se desideri elencare solo un sottoinsieme del tuo catalogo su Zalando. |
| **Negozio (zf\_export\_store)** | Ti consente di selezionare da quale negozio PrestaShop (in una configurazione multi-negozio) esportare i prodotti. | *Se selezionato:* Verranno esportati i prodotti da quel negozio specifico. *Se errato:* Potrebbero essere inclusi prodotti dal negozio sbagliato. | Il tuo negozio principale, o il negozio rilevante per Zalando | Per i commercianti che gestiscono più negozi distinti da un'unica installazione PrestaShop. |
| **Delimitatore (zf\_export\_delimiter)** | Specifica il carattere utilizzato per separare i campi dati nel file di esportazione (es. virgola, punto e virgola). | *Se impostato:* Verrà utilizzato il delimitatore scelto. *Se errato:* Il file sarà illeggibile da Zalando. | Controlla i requisiti di Zalando (spesso virgola o punto e virgola) | Cruciale per i file CSV per garantire che i dati vengano analizzati correttamente. |
| **Valuta (zf\_export\_currency)** | Seleziona la valuta per i prezzi dei prodotti nel file di esportazione. | *Se selezionato:* I prezzi verranno convertiti o visualizzati in questa valuta. *Se errato:* Zalando potrebbe visualizzare prezzi errati o rifiutare il feed. | La valuta richiesta da Zalando (es. EUR) | Se il tuo negozio opera in più valute, assicurati di esportare in quella che Zalando si aspetta. |
| **Formato nome prodotto (zf\_export\_product\_name\_format)** | Definisce come vengono formattati i nomi dei prodotti (es. includere produttore, attributi). | *Se impostato:* I nomi dei prodotti seguiranno questo formato. *Se errato:* I nomi potrebbero essere poco chiari o non soddisfare le linee guida di Zalando. | Secondo le raccomandazioni di Zalando per chiarezza | Per garantire che i nomi dei prodotti siano informativi e coerenti su Zalando. |
| **Includi IVA (zf\_export\_tax)** | Determina se i prezzi dei prodotti nel feed devono includere l'IVA. | *Se abilitato:* I prezzi saranno comprensivi di IVA. *Se disabilitato:* I prezzi saranno esclusivi di IVA. | Controlla i requisiti di Zalando per la visualizzazione dei prezzi | Importante per la conformità fiscale e la corretta visualizzazione dei prezzi su Zalando. |
| **Esporta prezzi per paese (zf\_export\_country\_prices)** | Se abilitato, verranno inclusi i prezzi specifici per i diversi paesi (se configurati in PrestaShop). | *Se abilitato:* Verranno esportati i prezzi specifici per paese. *Se disabilitato:* Verranno esportati solo i prezzi predefiniti. | SÌ (se hai prezzi specifici per paese) | Per i venditori internazionali con strategie di prezzo variabili per regione. |
| **Paese predefinito (PS\_COUNTRY\_DEFAULT)** | Il paese predefinito per il tuo negozio PrestaShop, utilizzato come fallback per alcune impostazioni. | *Se impostato:* Fornisce un paese di base per i calcoli di prezzo e IVA. | Il paese principale del tuo negozio | Garantisce un comportamento predefinito coerente per le impostazioni internazionali. |
| **Esporta solo prodotti attivi (zf\_export\_active)** | Se abilitato, verranno esportati solo i prodotti attualmente contrassegnati come "attivi" in PrestaShop. | *Se abilitato:* Vengono inviati solo i prodotti disponibili. *Se disabilitato:* Potrebbero essere inclusi prodotti inattivi, portando a errori su Zalando. | SÌ | Impedisce di elencare prodotti che non desideri vendere o che non sono più disponibili. |
| **Esporta produttori (zf\_export\_manufacturers)** | Se abilitato, le informazioni sul produttore verranno incluse nel feed. | *Se abilitato:* I dati del produttore vengono inviati. *Se disabilitato:* I dati del produttore vengono omessi. | SÌ | Utile per i clienti per filtrare per marchio su Zalando. |
| **Esporta fornitori (zf\_export\_suppliers)** | Se abilitato, le informazioni sul fornitore verranno incluse nel feed. | *Se abilitato:* I dati del fornitore vengono inviati. *Se disabilitato:* I dati del fornitore vengono omessi. | NO (a meno che non sia richiesto da Zalando) | Meno comune per i feed rivolti ai clienti, più per il tracciamento interno. |
| **Esporta categoria (zf\_export\_category)** | Se abilitato, le informazioni sulla categoria del prodotto verranno incluse. | *Se abilitato:* I dati della categoria vengono inviati. *Se disabilitato:* I dati della categoria vengono omessi. | SÌ | Aiuta Zalando a categorizzare correttamente i tuoi prodotti e facilita la navigazione del cliente. |
| **Esporta solo prodotti in stock (zf\_export\_instock)** | Se abilitato, verranno esportati solo i prodotti con stock disponibile. | *Se abilitato:* Vengono inviati solo i prodotti che puoi evadere. *Se disabilitato:* Potrebbero essere inclusi prodotti esauriti, portando a problemi di overselling. | SÌ | Cruciale per prevenire la delusione del cliente a causa di articoli non disponibili. |
| **Escludi prezzo massimo (zf\_export\_exclude\_price\_max)** | Se abilitato, i prodotti al di sopra di una certa soglia di prezzo verranno esclusi dal feed. | *Se abilitato:* I prodotti che superano il prezzo massimo non verranno esportati. *Se disabilitato:* Tutti i prodotti, indipendentemente dal prezzo, vengono esportati. | NO (a meno che tu non abbia articoli specifici di alto valore da escludere) | Utile se Zalando ha limiti di prezzo o se desideri vendere solo determinate fasce di prezzo sulla loro piattaforma. |
| **Valore prezzo massimo da escludere (zf\_export\_exclude\_price\_max\_v)** | Il valore di prezzo massimo per l'impostazione "Escludi prezzo massimo". | *Se impostato:* Definisce il limite di prezzo superiore per i prodotti esportati. | Lascia vuoto se non escludi per prezzo massimo | Se desideri vendere solo articoli sotto i 500€ su Zalando, imposta questo valore a 500. |

#### 2.2.2 Schermata Admin Index (Back Office > Zalando FCI > Index)

Questa schermata funge probabilmente da pagina di destinazione o da semplice vista di gestione per il modulo, visualizzando potenzialmente informazioni o fornendo collegamenti rapidi.

-   **Nome schermata e posizione nel menu:** **Zalando FCI > Index** (Questo apparirà come una nuova voce di menu nella navigazione del tuo Back Office di PrestaShop, spesso la prima voce sotto il menu principale del modulo).
-   **Azioni e impostazioni disponibili:** Questa schermata visualizza tipicamente una griglia o un semplice pannello informativo. Potrebbe mostrare l'ultima data di esportazione, un link per generare il feed o lo stato generale del modulo. Di solito non è una schermata per una configurazione dettagliata, ma piuttosto per una panoramica o azioni rapide.
-   **Effetto delle modifiche:** Di solito non ci sono "impostazioni" dirette da modificare in questa schermata. Il suo scopo è più informativo o navigazionale.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Utilizza questo come punto di ingresso rapido al modulo, per controllare lo stato della tua ultima esportazione o per navigare alla schermata "Esporta prodotti" per una configurazione dettagliata e la generazione del feed.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| :---------------- | :---------------------- | :---------------------- | :-------------- |
| **Configurazione modulo** | Negozio | Il nome del tuo negozio | Identifica il tuo negozio su Zalando. |
| **Configurazione modulo** | EAN | SÌ | Essenziale per l'identificazione del prodotto. |
| **Configurazione modulo** | Prezzo | SÌ | Garantisce prezzi corretti su Zalando. |
| **Configurazione modulo** | Prezzo al dettaglio | SÌ (se usato) | Visualizza il prezzo originale per le promozioni. |
| **Configurazione modulo** | Quantità | SÌ | Critico per livelli di stock accurati, previene l'overselling. |
| **Configurazione modulo** | Nome del prodotto | SÌ | Essenziale per l'identificazione e la ricerca del prodotto. |
| **Configurazione modulo** | ID Cliente (zf\_client) | Fornito da Zalando | Autentica con l'API di Zalando. |
| **Configurazione modulo** | Chiave API (zf\_api) | Fornita da Zalando | Protegge la comunicazione con l'API di Zalando. |
| **Esporta prodotti** | Ricorda impostazioni | SÌ | Risparmia tempo preservando le scelte di esportazione. |
| **Esporta prodotti** | Formato file di esportazione | Controlla i requisiti di Zalando | Definisce il tipo di file di output. |
| **Esporta prodotti** | Tipo di esportazione | Tutti i prodotti attivi | Controlla quali prodotti sono inclusi. |
| **Esporta prodotti** | Negozio | Il tuo negozio principale | Seleziona i prodotti da un negozio specifico (multi-negozio). |
| **Esporta prodotti** | Delimitatore | Controlla i requisiti di Zalando | Separa i campi nei file CSV. |
| **Esporta prodotti** | Valuta | Richiesta da Zalando (es. EUR) | Imposta la valuta per i prezzi esportati. |
| **Esporta prodotti** | Formato nome prodotto | Secondo le raccomandazioni di Zalando | Formatta i nomi dei prodotti per chiarezza. |
| **Esporta prodotti** | Includi IVA | Controlla i requisiti di Zalando | Determina se i prezzi sono comprensivi di IVA. |
| **Esporta prodotti** | Esporta prezzi per paese | SÌ (se applicabile) | Include prezzi specifici per paese. |
| **Esporta prodotti** | Paese predefinito | Il paese principale del tuo negozio | Fallback per le impostazioni relative al paese. |
| **Esporta prodotti** | Esporta solo prodotti attivi | SÌ | Impedisce l'elenco di prodotti inattivi. |
| **Esporta prodotti** | Esporta produttori | SÌ | Include informazioni sul marchio. |
| **Esporta prodotti** | Esporta fornitori | NO (a meno che non sia richiesto) | Include informazioni sul fornitore. |
| **Esporta prodotti** | Esporta categoria | SÌ | Aiuta Zalando a categorizzare i prodotti. |
| **Esporta prodotti** | Esporta solo prodotti in stock | SÌ | Impedisce l'elenco di articoli esauriti. |
| **Esporta prodotti** | Escludi prezzo massimo | NO (a meno che non sia necessario) | Esclude i prodotti al di sopra di un prezzo impostato. |
| **Esporta prodotti** | Valore prezzo massimo da escludere | Lascia vuoto se non escludi | Imposta il prezzo massimo per l'esclusione. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei prodotti non compaiono su Zalando, o il feed viene rifiutato. Cosa dovrei controllare per primo?**
R1:

-   **Controlla la configurazione del modulo:** Vai su **Moduli > Gestione moduli > Zalando Fashion Connector Importer (FCI) > Configura**. Assicurati che il tuo "ID Cliente" e la "Chiave API" siano inseriti correttamente come fornito da Zalando.
-   **Controlla le impostazioni di esportazione:** Naviga su **Zalando FCI > Esporta prodotti**. Verifica che il "Formato file di esportazione" e il "Delimitatore" corrispondano ai requisiti esatti di Zalando. Inoltre, assicurati che "Esporta solo prodotti attivi" e "Esporta solo prodotti in stock" siano abilitati se desideri inviare solo gli articoli disponibili.
-   **Convalida i dati del prodotto:** Assicurati che i tuoi prodotti in PrestaShop abbiano EAN, nomi, prezzi e quantità di stock validi. Dati mancanti o non validi sono una causa comune di rifiuti.
-   **Svuota la cache:** A volte, i dati vecchi possono persistere. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti).

**D2: I prezzi o i livelli di stock su Zalando non si aggiornano correttamente.**
R2:

-   **Controlla la frequenza di esportazione:** Con quale frequenza stai generando il feed? Se lo fai manualmente, devi farlo regolarmente. Se hai impostato un cron job, assicurati che sia in esecuzione alla frequenza desiderata (es. ogni ora).
-   **Configurazione del modulo:** Ricontrolla che "Prezzo" e "Quantità" siano abilitati nella schermata di configurazione principale del modulo.
-   **Tempo di elaborazione di Zalando:** Ricorda che anche dopo aver generato e inviato il feed, i sistemi di Zalando hanno bisogno di tempo per elaborare e aggiornare i dati. Questo a volte può richiedere da pochi minuti a diverse ore a seconda del loro carico.

**D3: Ho un tema personalizzato e l'interfaccia di amministrazione del modulo sembra un po' strana.**
R3:

-   L'interfaccia di amministrazione del modulo utilizza lo stile standard di PrestaShop, ma possono verificarsi piccole incongruenze visive con temi di back-office altamente personalizzati. Questo di solito non influisce sulla funzionalità.
-   Se è un problema significativo, contatta il supporto MyPresta.eu. Per piccole modifiche, uno sviluppatore web può spesso regolare il file `zalandofci/views/admin-theme.css` o aggiungere CSS personalizzato al back office del tuo PrestaShop.

**D4: Come si imposta un cron job per automatizzare la generazione del feed?**
R4:

-   I passaggi esatti dipendono dal tuo provider di hosting. In genere troverai una sezione "Cron Jobs" o "Attività pianificate" nel tuo pannello di controllo dell'hosting (es. cPanel, Plesk).
-   Avrai bisogno dell'URL che attiva la generazione del feed. Questo URL è solitamente fornito nella pagina di configurazione "Esporta prodotti" del modulo dopo aver salvato le impostazioni, oppure può essere costruito utilizzando il percorso del front controller (es. `iltuonegozio.com/module/zalandofci/feed`).
-   Imposta il cron job per eseguire questo URL all'intervallo desiderato (es. `wget -q -O /dev/null "http://iltuonegozio.com/module/zalandofci/feed"`). Se non sei sicuro, consulta la documentazione o il supporto del tuo provider di hosting.

**D5: Il modulo è installato, ma non vedo "Zalando FCI" nel mio menu del Back Office.**
A5:

-   **Svuota la cache di PrestaShop:** Vai su **Parametri avanzati > Prestazioni** e svuota la cache. A volte il menu non si aggiorna immediatamente dopo l'installazione del modulo.
-   **Controlla lo stato del modulo:** Vai su **Moduli > Gestione moduli** e cerca "Zalando Fashion Connector Importer (FCI)". Assicurati che sia elencato come "Installato" e "Abilitato".
-   **Permessi:** In rari casi, i permessi dei dipendenti potrebbero limitare la visibilità del menu. Controlla **Amministrazione > Permessi** per il tuo profilo dipendente.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo Zalando Fashion Connector Importer (FCI) segue un'architettura standard per i moduli PrestaShop, sfruttando i principi MVC ove applicabile. Si concentra principalmente sull'esportazione dei dati, utilizzando una combinazione di controller front-office e admin. La logica principale risiede nel file del modulo principale e nei controller admin per la configurazione e la generazione del feed. Non sembra utilizzare classi `ObjectModel` personalizzate, ma interroga direttamente il database di PrestaShop per i dati dei prodotti. La funzione principale del modulo è generare un feed di dati, che viene tipicamente consumato da un sistema esterno (Zalando) tramite un'attività pianificata (cron job) che richiama un front controller.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

Questi controller sono accessibili dall'URL del front-office e sono tipicamente utilizzati per generare il feed di prodotti, spesso attivato da un cron job.

-   `controllers/front/feed.php`
    -   **Nome classe e classe genitore**: `ZalandofciFeedModuleFrontController` che estende `ModuleFrontController`.
    -   **Responsabilità**: Questo è l'endpoint principale per la generazione del feed di prodotti. Risponde alle richieste (tipicamente da cron job) e genera dinamicamente i dati dei prodotti in base alla configurazione del modulo. Probabilmente recupera le informazioni sui prodotti (EAN, prezzo, quantità, nome) e le formatta nell'output specificato (es. CSV, XML) per Zalando. Questo controller non renderizza una pagina visiva ma produce dati grezzi.
-   `controllers/front/index.php`
    -   **Nome classe e classe genitore**: `ZalandofciIndexModuleFrontController` che estende `ModuleFrontController`.
    -   **Responsabilità**: Questo controller funge probabilmente da fallback o da semplice punto di ingresso, potenzialmente reindirizzando o visualizzando un messaggio minimo. In molti moduli, un front controller `index.php` è presente per prevenire l'elenco delle directory o fornire un'azione predefinita se non viene richiesta alcuna azione specifica.

#### Controller Admin Back-Office

Questi controller gestiscono la configurazione del modulo e le impostazioni di esportazione dei prodotti all'interno del Back Office di PrestaShop.

-   `controllers/admin/AdminExportProductsFci.php`
    -   **Nome scheda ed entità gestita**: "Esporta prodotti" sotto il menu "Zalando FCI". Questo controller gestisce la configurazione dettagliata dell'esportazione dei prodotti.
    -   **Responsabilità**: Questo controller gestisce la visualizzazione e l'invio del modulo di esportazione dei prodotti. Recupera le impostazioni di configurazione (es. `zf_export_file_format`, `zf_export_type`, `zf_export_currency`, `zf_export_tax`, `zf_export_active`, ecc.) da `ps_configuration`, elabora l'input dell'utente e attiva la logica effettiva di recupero e formattazione dei dati dei prodotti per la generazione del feed. Probabilmente utilizza i metodi di `AdminController` per il rendering del modulo (`renderForm`) e il salvataggio (`postProcess`).
-   `controllers/admin/index.php`
    -   **Nome scheda ed entità gestita**: "Index" sotto il menu "Zalando FCI".
    -   **Responsabilità**: Simile alla sua controparte front-office, questo controller admin funge probabilmente da pagina di destinazione o da semplice panoramica. Potrebbe visualizzare informazioni generali sul modulo, collegamenti rapidi ad altre pagine admin o un messaggio di stato. Non è tipicamente coinvolto nella gestione complessa dei dati, ma piuttosto nella navigazione e nella visualizzazione delle informazioni.

### 4.3 Classi e modelli principali (`classes/`)

Il dossier del modulo indica l'assenza di classi o modelli personalizzati nella directory `classes/`. Ciò suggerisce che il modulo interagisce direttamente con le classi `ObjectModel` principali di PrestaShop `Product` e `ProductSupplier` (o simili) e la classe `Configuration` per le impostazioni. Il recupero dei dati è probabilmente gestito direttamente all'interno dei controller o del file del modulo principale utilizzando `Db::getInstance()->executeS()` o oggetti `DbQuery`.

### 4.4 Risorse JavaScript (`views/js/`)

Il dossier del modulo indica l'assenza di file JavaScript personalizzati. Ciò implica che la configurazione e la funzionalità del modulo sono principalmente basate sul lato server, con interazioni front-end dinamiche minime o nulle nel Back Office o nel Front Office che richiedano JS personalizzato.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `zalandofci/views/admin-theme.css`
    -   **Ambito**: Stile del modulo di amministrazione del Back Office.
    -   **Principali componenti UI e contenitori che stilizza**: Questo foglio di stile è responsabile della presentazione visiva dei moduli di configurazione del modulo e potenzialmente di eventuali griglie personalizzate o pannelli informativi all'interno del Back Office di PrestaShop. Assicura che l'interfaccia del modulo si integri visivamente con il tema di amministrazione di PrestaShop.
    -   **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere**: Gli sviluppatori possono ispezionare le pagine di amministrazione del modulo per identificare classi specifiche (es. `.zalandofci-form`, `.zalandofci-panel`, `.zalandofci-alert`) e sovrascriverle nel loro tema di amministrazione personalizzato o aggiungendo CSS tramite un hook `displayBackOfficeHeader`.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**:
    -   Il dossier del modulo non elenca esplicitamente i template all'interno di una sottodirectory `hook/`, ma registra hook come `displayHeader`, `displayRightColumn`, `displayProduct`, `displayFooter`. Se fosse previsto un output visivo per questi hook, i template risiederebbero tipicamente qui. Dato lo scopo del modulo (feed di dati backend), è probabile che questi hook siano utilizzati per scopi tecnici (es. aggiunta di JS/CSS, o non utilizzati affatto per l'output visivo).
-   **Template admin (`views/templates/admin/`)**:
    -   `zalandofci/views/how-it-works.tpl`
        -   **Scopo**: Questo template probabilmente fornisce contenuto informativo all'interno del Back Office, possibilmente nella pagina di configurazione principale o nella schermata "Index", spiegando come funziona il modulo o fornendo istruzioni di configurazione.
    -   `zalandofci/views/returnAlert.tpl`
        -   **Scopo**: Questo template è probabilmente utilizzato per visualizzare messaggi di successo o di errore (avvisi) all'interno del Back Office dopo un'azione (es. salvataggio della configurazione, generazione di un feed).
    -   `zalandofci/views/script.tpl`
        -   **Scopo**: Questo template potrebbe contenere codice JavaScript inline o essere utilizzato per includere file JS esterni condizionalmente all'interno del Back Office. Potrebbe essere utilizzato per un comportamento dinamico del modulo o per attivare azioni specifiche.
-   **Template front-office (`views/templates/front/`)**:
    -   Il dossier del modulo non elenca alcun template specifico per il front-office, rafforzando l'idea che il modulo non abbia una presenza visiva diretta sul lato rivolto al cliente del negozio.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non sembra creare tabelle SQL personalizzate durante l'installazione (metodo `install()`).
    -   Tutte le impostazioni di configurazione specifiche del modulo (es. `zf_client`, `zf_api`, `zf_export_file_format`, `zf_remember_settings`, ecc.) sono memorizzate nella tabella standard `ps_configuration` di PrestaShop. Queste chiavi sono prefissate con `zf_` o `PS_` (per le impostazioni principali di PrestaShop utilizzate dal modulo).
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| :---------------------- | :------------------------ | :------------------------------------------ |
| `displayHeader` | Renderizza nella sezione `<head>` di tutte le pagine del front-office. | Potenzialmente utilizzato per includere CSS o JS specifici del modulo, sebbene non siano elencati JS/CSS personalizzati per il front-office. Potrebbe anche essere utilizzato per meta tag o altri elementi non visivi. |
| `displayRightColumn` | Renderizza nella colonna destra delle pagine che ne hanno una. | Improbabile che venga utilizzato per l'output visivo dato lo scopo del modulo. Potrebbe essere un hook legacy o utilizzato per un'iniezione di dati molto specifica e non visiva. |
| `displayProduct` | Renderizza nella pagina del prodotto. | Improbabile che venga utilizzato per l'output visivo. Potrebbe essere utilizzato per aggiungere attributi di dati nascosti agli elementi del prodotto per script esterni, sebbene non sia elencato JS personalizzato. |
| `displayFooter` | Renderizza nella sezione del footer di tutte le pagine del front-office. | Simile a `displayHeader`, potrebbe essere utilizzato per includere JS/CSS o altri elementi non visivi alla fine del caricamento della pagina. |
| `actionAdminControllerSetMedia` | Eseguito quando un controller admin sta impostando i suoi media (JS/CSS). | Utilizzato da `AdminExportProductsFci` per caricare `zalandofci/views/admin-theme.css` per i suoi moduli di configurazione. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e per scaricare le ultime versioni del modulo Zalando Fashion Connector Importer (FCI), visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda riguardante la funzionalità e l'integrazione del modulo.
