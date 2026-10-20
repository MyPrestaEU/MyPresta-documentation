---
title: "Dividi carrello in spedizioni separate - Manuale del commerciante e guida alla configurazione"
description: ""
sidebar:
  label: "Dividi carrello in spedizioni separate - Manuale del commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Split cart into separate shipments su MyPresta.eu](https://mypresta.eu/modules/ordering-process/split-cart-into-separate-shipments.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/split-cart-into-separate-shipments/)
>
> ---


# Dividi carrello in spedizioni separate

## 1. Guida completa alla configurazione (ogni impostazione raggruppata per schermata)

Il modulo "Dividi carrello in spedizioni separate" introduce diverse nuove potenti schermate e opzioni nel tuo Back Office di PrestaShop.

### 1.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Dividi carrello in spedizioni separate)

Questa è la pagina di configurazione principale a cui accedi immediatamente dopo l'installazione o cliccando su "Configura" dal Gestore moduli. Contiene le impostazioni generali per il comportamento del modulo.

-   **Abilita Modulo:**

    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare la funzionalità del modulo in tutto il tuo negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il modulo dividerà attivamente i carrelli secondo le tue regole durante il checkout.
        -   *Quando disabilitato:* La logica di divisione del modulo verrà bypassata e PrestaShop tornerà al suo comportamento predefinito di spedizione singola.
    -   **Valore consigliato:** SÌ (una volta configurate le tue regole).
    -   **Scenario / esempio del commerciante:** Potresti disabilitarlo temporaneamente se stai eseguendo la manutenzione o risolvendo problemi in altre parti del tuo processo di checkout.
-   **Modalità Debug:**

    -   **Cosa fa questa impostazione:** Attiva una modalità speciale che può visualizzare informazioni tecniche aggiuntive o log per aiutare a identificare i problemi.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Potrebbe mostrare messaggi di errore o passaggi di elaborazione dettagliati sul front office (visibili ai clienti) o nella console per sviluppatori del tuo browser. Questo è utile per gli sviluppatori.
        -   *Quando disabilitato:* Il modulo opera silenziosamente, senza visualizzare informazioni di debug.
    -   **Valore consigliato:** NO (disabilitare sempre in un negozio di produzione live).
    -   **Scenario / esempio del commerciante:** Se stai lavorando con uno sviluppatore per capire perché un carrello specifico non si sta dividendo come previsto, potrebbero chiederti di abilitarlo temporaneamente.
-   **Visualizza riepilogo divisione nella pagina di conferma dell'ordine:**

    -   **Cosa fa questa impostazione:** Controlla se i clienti vedono un riepilogo di come il loro ordine è stato diviso in diverse spedizioni nella pagina finale di conferma dell'ordine.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I clienti vedranno una chiara ripartizione di quali articoli sono andati in quale gruppo di spedizione e il corriere scelto per ciascuno, confermando le loro selezioni.
        -   *Quando disabilitato:* La pagina di conferma dell'ordine mostrerà un riepilogo standard senza le informazioni dettagliate sulla divisione.
    -   **Valore consigliato:** SÌ.
    -   **Scenario / esempio del commerciante:** L'abilitazione di questa opzione migliora la trasparenza e rassicura i clienti che le loro specifiche scelte di spedizione per ogni pacco sono state correttamente applicate.
-   **Consenti al cliente di scegliere i punti di ritiro (se applicabile):**

    -   **Cosa fa questa impostazione:** Se hai corrieri che offrono la consegna presso punti di ritiro (ad esempio, Mondial Relay, Colissimo Point Relais), questa impostazione consente ai clienti di selezionare una posizione di ritiro specifica per ogni gruppo di spedizione pertinente.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Per i corrieri configurati con punti di ritiro, i clienti vedranno un'opzione per scegliere una posizione di ritiro durante il checkout per la spedizione corrispondente.
        -   *Quando disabilitato:* I clienti potranno selezionare solo la consegna a domicilio o altre opzioni di spedizione standard, anche se i corrieri supportano i punti di ritiro.
    -   **Valore consigliato:** SÌ (se utilizzi corrieri con punti di ritiro).
    -   **Scenario / esempio del commerciante:** Se offri Mondial Relay, l'abilitazione di questa opzione consente ai clienti di farsi consegnare un articolo pesante in un comodo punto di ritiro vicino a casa o al lavoro, migliorando la loro esperienza.

### 1.2 Schermate di amministrazione dedicate: Regole di spedizione (Back Office > Spedizione > Regole di divisione spedizione)

Questa schermata è dove definisci la logica per come gli articoli del tuo carrello dovrebbero essere raggruppati in spedizioni separate. È il cuore della funzionalità del modulo.

-   **Nome schermata e posizione menu:** **Regole di divisione spedizione** (si trova sotto **Spedizione** nel menu del tuo Back Office di PrestaShop).
-   **Azioni e impostazioni disponibili:**
    -   **Tabella elenco regole:** Visualizza tutte le tue regole di raggruppamento definite. Ogni regola ha un nome, uno stato (attivo/inattivo), una priorità e un riepilogo delle sue condizioni e azioni.
    -   **Pulsante "Aggiungi nuova regola":** Cliccando su questo puoi creare una nuova regola.
    -   **Azioni di modifica/eliminazione:** Per ogni regola nell'elenco, puoi modificarne i dettagli o eliminarla.
    -   **Interruttore Abilita/Disabilita:** Attiva o disattiva rapidamente una regola senza eliminarla.
    -   **Riordino con trascinamento:** Le regole vengono elaborate in ordine di priorità. Puoi trascinare e rilasciare le regole per modificarne l'ordine di esecuzione. Le regole con priorità più alta vengono elaborate per prime.
-   **Effetto delle modifiche:**
    -   **Aggiunta/Modifica regole:** Influisce direttamente su come i carrelli vengono divisi durante il checkout. Una regola ben definita può garantire che prodotti specifici vengano sempre spediti separatamente o insieme.
    -   **Abilitazione/Disabilitazione regole:** Controlla se la logica di una regola viene applicata.
    -   **Modifica priorità:** Determina quale regola ha la precedenza se più regole potrebbero applicarsi allo stesso prodotto. Le regole con priorità più alta (che appaiono più in alto nell'elenco) vengono valutate per prime.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  **Identifica le esigenze di raggruppamento:** Pensa ai tuoi prodotti. Hai articoli di grandi dimensioni, articoli fragili, articoli da diversi magazzini o articoli che richiedono una gestione speciale?
    2.  **Crea regole:** Per ogni esigenza di raggruppamento, crea una nuova regola.
        -   **Condizioni:** Definisci *quando* la regola si applica. Questo potrebbe basarsi su:
            -   **Prodotto:** Prodotti specifici, categorie, produttori, fornitori o caratteristiche del prodotto.
            -   **Carrello:** Valore totale del carrello, numero di articoli, gruppi di clienti specifici.
            -   **Spedizione:** Corrieri o zone specifiche.
        -   **Azioni:** Definisci *cosa* fa la regola. Questo potrebbe essere:
            -   **Forza spedizione separata:** Inserisci sempre gli articoli corrispondenti nel proprio gruppo di spedizione.
            -   **Forza stessa spedizione:** Assicurati che gli articoli corrispondenti rimangano sempre insieme in un'unica spedizione.
            -   **Escludi dall'elaborazione delle regole:** Impedisci ad altre regole di influenzare questi articoli.
    3.  **Imposta la priorità:** Organizza le tue regole dalla più specifica (ad esempio, "Vetri fragili spediti sempre da soli") alla più generale (ad esempio, "Tutti gli articoli di grandi dimensioni spediti separatamente").
    4.  **Testa accuratamente:** Utilizza un account cliente di prova per aggiungere varie combinazioni di prodotti al carrello e verifica che la divisione funzioni come previsto durante il checkout.

### 1.3 Schermate di amministrazione dedicate: Gruppi di spedizione (Back Office > Spedizione > Divisioni spedizione)

Questa schermata fornisce una panoramica di come gli ordini sono stati divisi dal modulo dopo essere stati effettuati. È uno strumento di reporting e gestione.

-   **Nome schermata e posizione menu:** **Divisioni spedizione** (si trova sotto **Spedizione** nel menu del tuo Back Office di PrestaShop).
-   **Azioni e impostazioni disponibili:**
    -   **Tabella elenco divisioni:** Mostra un elenco di tutti gli ordini che sono stati divisi dal modulo.
    -   **Riferimento ordine:** Collega direttamente all'ordine PrestaShop originale.
    -   **Dettagli gruppo di spedizione:** Fornisce informazioni su ogni singolo gruppo di spedizione all'interno di un ordine, inclusi i prodotti che contiene, il corriere scelto e il suo stato.
    -   **Visualizza dettagli divisione:** Ti consente di approfondire una divisione specifica per vedere informazioni più granulari.
-   **Effetto delle modifiche:** Questa schermata è principalmente per la visualizzazione e l'audit. Non modifichi direttamente qui come verranno divisi i carrelli futuri. Eventuali modifiche apportate (ad esempio, l'aggiornamento di un corriere per una divisione specifica) verrebbero in genere effettuate all'interno della visualizzazione principale dell'ordine di PrestaShop, e questo modulo rifletterebbe tali modifiche.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    -   **Monitora gli ordini divisi:** Controlla regolarmente questa schermata per capire come le tue regole stanno funzionando nella pratica.
    -   **Risoluzione dei problemi:** Se un cliente ha una domanda sulla sua spedizione, questa schermata può aiutarti a vedere rapidamente come il suo ordine è stato elaborato in diverse spedizioni.
    -   **Integrazione con la gestione degli ordini:** Sebbene il modulo crei ordini PrestaShop standard, questa schermata offre una visione consolidata della logica di divisione applicata a ciascun ordine.

### 1.4 Schermate di amministrazione dedicate: Dashboard (Back Office > Spedizione > Dashboard divisione spedizione)

Questa schermata fornisce una rapida panoramica e statistiche relative all'attività del modulo.

-   **Nome schermata e posizione menu:** **Dashboard divisione spedizione** (si trova sotto **Spedizione** nel menu del tuo Back Office di PrestaShop).
-   **Azioni e impostazioni disponibili:**
    -   **Striscia KPI:** Indicatori chiave di prestazione (KPI) come ordini totali divisi, spedizioni medie per ordine o ricavi totali di spedizione da ordini divisi.
    -   **Grafici e diagrammi:** Rappresentazioni visive delle tendenze, come il numero di ordini divisi nel tempo, le regole di divisione più comuni utilizzate o i corrieri più popolari per le spedizioni divise.
    -   **Divisioni recenti:** Un elenco rapido degli ordini divisi più di recente.
-   **Effetto delle modifiche:** Questa è una dashboard di reporting. Non vengono apportate modifiche dirette al comportamento del modulo qui. Ti aiuta a comprendere l'impatto e l'utilizzo del modulo.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    -   **Monitoraggio delle prestazioni:** Utilizza questa dashboard per valutare l'efficacia delle tue regole di divisione e identificare eventuali schemi o anomalie.
    -   **Pianificazione strategica:** I dati possono informare le decisioni sulle strategie di spedizione, le partnership con i corrieri o gli aggiustamenti del catalogo prodotti.

### 1.5 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Configurazione modulo** | Abilita modulo | SÌ | Interruttore principale per la funzionalità del modulo. |
| | Modalità debug | NO | Visualizza informazioni tecniche (solo per sviluppatori). |
| | Visualizza riepilogo divisione nella pagina di conferma dell'ordine | SÌ | Mostra ai clienti come è stato diviso il loro ordine. |
| | Consenti al cliente di scegliere i punti di ritiro | SÌ (se applicabile) | Abilita la selezione del punto di ritiro per i corrieri pertinenti. |
| **Regole di divisione spedizione** | Aggiungi/Modifica regola (Condizioni) | N/A | Definisce *quando* si applica una regola (ad es. per prodotto, categoria, valore carrello). |
| | Aggiungi/Modifica regola (Azioni) | N/A | Definisce *cosa* fa la regola (ad es. forza spedizione separata, forza stessa spedizione). |
| | Priorità regola | N/A | Determina l'ordine in cui le regole vengono elaborate (più alta = prima). |
| | Abilita/Disabilita regola | N/A | Attiva o disattiva una specifica regola di raggruppamento. |
| **Divisioni spedizione** | Visualizza ordini divisi | N/A | Fornisce un elenco e i dettagli di tutti gli ordini elaborati dal modulo. |
| **Dashboard divisione spedizione** | KPI, Grafici, Divisioni recenti | N/A | Offre una panoramica dell'attività e delle prestazioni del modulo. |

## 2. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

-   **D: Il mio carrello non si divide, o si divide in modo errato. Cosa devo fare?**

    -   **R:** Innanzitutto, controlla se il modulo è abilitato nella sua configurazione principale. Quindi, vai su **Spedizione > Regole di divisione spedizione** e rivedi le tue regole. Assicurati che siano attive e che le loro condizioni corrispondano correttamente ai prodotti nel tuo carrello di prova. Presta molta attenzione alla priorità delle regole: una regola più generale potrebbe sovrascrivere una più specifica. Se hai abilitato la "Modalità Debug" nella configurazione principale del modulo, controlla eventuali messaggi durante il checkout. Infine, svuota la cache di PrestaShop (**Parametri avanzati > Prestazioni > Svuota cache**).
-   **D: Perché alcuni corrieri non vengono visualizzati per un gruppo di spedizione specifico?**

    -   **R:** Il modulo rispetta le restrizioni standard dei corrieri di PrestaShop. Controlla quanto segue:
        1.  **Zone del corriere:** Assicurati che il corriere sia abilitato per la zona di spedizione del cliente.
        2.  **Intervalli di peso/prezzo del corriere:** Verifica che il peso/prezzo totale del *singolo gruppo di spedizione* (non dell'intero carrello) rientri negli intervalli definiti dal corriere.
        3.  **Associazioni del corriere:** Assicurati che il corriere sia associato ai prodotti in quel gruppo di spedizione (se hai impostato restrizioni del corriere specifiche per prodotto).
        4.  **Compatibilità del modulo:** Alcuni moduli di spedizione di terze parti potrebbero avere una propria logica che entra in conflitto; verifica eventuali incompatibilità note o contatta il supporto.
-   **D: In che modo questo modulo influisce sui miei costi di spedizione esistenti e sulle regole di spedizione gratuita?**

    -   **R:** Il modulo aggrega i costi di spedizione. Se un carrello viene diviso in due spedizioni e ogni spedizione ha un costo di 10 €, il cliente vedrà un costo di spedizione totale di 20 €. Per la spedizione gratuita, le tue regole di spedizione gratuita esistenti (ad esempio, "spedizione gratuita oltre X €") si applicheranno a *ogni singolo gruppo di spedizione* se il modulo lo consente, o al *totale complessivo del carrello* a seconda di come sono configurate le tue regole e di come si integra il modulo. Potrebbe essere necessario modificare le tue regole di spedizione gratuita per tenere conto delle spedizioni divise.
-   **D: Posso tradurre i testi del modulo in altre lingue?**

    -   **R:** Sì, come la maggior parte dei moduli PrestaShop, puoi tradurre i suoi testi del front-office e del back-office. Vai su **Internazionale > Traduzioni**, seleziona "Traduzioni dei moduli installati", scegli il tuo tema, seleziona "Dividi carrello in spedizioni separate" e quindi scegli la lingua in cui vuoi tradurre.
-   **D: Dopo l'installazione, vedo una pagina bianca o un errore. Cosa c'è che non va?**

    -   **R:** Questo spesso indica un errore PHP.
        1.  **Controlla i log degli errori PHP:** Il pannello di controllo del tuo hosting web di solito fornisce l'accesso ai log degli errori PHP. Cerca voci recenti relative a PrestaShop.
        2.  **Abilita la modalità debug di PrestaShop:** Vai su `config/defines.inc.php` nella tua installazione di PrestaShop, trova `define('_PS_MODE_DEV_', false);` e cambia `false` in `true`. Questo visualizzerà l'errore sullo schermo.
        3.  **Compatibilità del modulo:** Assicurati di aver scaricato la versione corretta del modulo per la tua versione di PrestaShop (ad esempio, PS 8.x, 1.7.x).
        4.  **Contatta il supporto:** Se non riesci a risolverlo, fornisci il messaggio di errore al supporto MyPresta.eu.

## 3. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 3.1 Panoramica dell'architettura

Il modulo "Dividi carrello in spedizioni separate" (`multishipsplit`) è costruito seguendo il modello MVC (Model-View-Controller) di PrestaShop, con un uso significativo di hook e override per integrarsi profondamente nel processo di checkout. Introduce un robusto motore basato su regole per la divisione del carrello, consentendo condizioni e azioni complesse. La logica centrale ruota attorno alla suddivisione dell'oggetto `Cart` in più entità `MultishipShipmentGroup`, ciascuna rappresentante un pacchetto distinto con la propria selezione del corriere. Sfrutta `ObjectModel` per la gestione delle regole e dei dati divisi, e impiega una serie di classi di servizio per gestire la logica intricata di valutazione delle condizioni, costruzione delle azioni e presentazione del checkout. Gli override vengono utilizzati per modificare il comportamento principale di `Cart` e `PaymentModule` per supportare spedizioni multiple.

### 3.2 Controller (`controllers/`)

#### Controller Front-Office

-   `multishipsplit/controllers/front/groups.php`
    -   **Nome classe:** `MultishipsplitGroupsModuleFrontController` (estende `ModuleFrontController`)
    -   **Responsabilità:** Gestisce le richieste AJAX relative ai gruppi di spedizione durante il checkout. Ciò potrebbe includere l'aggiornamento delle selezioni del corriere per un gruppo specifico, il ricalcolo dei costi di spedizione o il recupero delle opzioni del punto di ritiro. Elabora i dati `POST` e restituisce risposte JSON alla pagina di checkout.
-   `multishipsplit/controllers/front/index.php`
    -   **Nome classe:** `MultishipsplitIndexModuleFrontController` (estende `ModuleFrontController`)
    -   **Responsabilità:** Un controller segnaposto o punto di ingresso. Potrebbe essere utilizzato per azioni front-office generali relative al modulo o reindirizzamenti, sebbene la sua funzione principale potrebbe essere minima se la maggior parte delle interazioni sono guidate da AJAX tramite `groups.php`.
-   `multishipsplit/controllers/front/pickup.php`
    -   **Nome classe:** `MultishipsplitPickupModuleFrontController` (estende `ModuleFrontController`)
    -   **Responsabilità:** Gestisce le interazioni AJAX specificamente per la selezione del punto di ritiro. Probabilmente gestisce le richieste per visualizzare i punti di ritiro disponibili per un dato corriere e indirizzo, e per salvare il punto di ritiro selezionato nel carrello o nella sessione.

#### Controller di amministrazione Back-Office

-   `multishipsplit/controllers/admin/AdminMultishipRules.php`
    -   **Nome classe:** `AdminMultishipRulesController` (estende `ModuleAdminController`)
    -   **Nome scheda:** "Regole di divisione spedizione"
    -   **Entità gestita:** `MultishipGroupingRule` (mappa alla tabella `mss_grouping_rule`)
    -   **Responsabilità:** Fornisce l'interfaccia CRUD (Crea, Leggi, Aggiorna, Elimina) per la gestione delle regole di raggruppamento delle spedizioni. Gestisce la visualizzazione dell'elenco delle regole, il modulo per l'aggiunta/modifica delle regole (inclusi i costruttori di condizioni e azioni) e il salvataggio/eliminazione dei dati delle regole.
-   `multishipsplit/controllers/admin/AdminMultishipSplits.php`
    -   **Nome classe:** `AdminMultishipSplitsController` (estende `ModuleAdminController`)
    -   **Nome scheda:** "Divisioni spedizione"
    -   **Entità gestita:** `MultishipSplitGroup` (mappa alla tabella `mss_split_group`)
    -   **Responsabilità:** Visualizza un elenco di tutti gli ordini che sono stati elaborati e divisi dal modulo. Fornisce una vista di sola lettura dei gruppi divisi all'interno di ciascun ordine, collegandosi all'ordine PrestaShop originale.
-   `multishipsplit/controllers/admin/index.php`
    -   **Nome classe:** `MultishipsplitIndexModuleAdminController` (estende `ModuleAdminController`)
    -   **Nome scheda:** "Dashboard divisione spedizione"
    -   **Entità gestita:** N/A (vista dashboard)
    -   **Responsabilità:** Funge da controller della dashboard, visualizzando KPI, grafici e ordini divisi recenti. Aggrega i dati dalle tabelle del modulo per fornire una panoramica della sua attività.

### 3.3 Classi e modelli principali (`classes/`)

-   `multishipsplit/classes/MultishipActionBuilder.php`
    -   **Responsabilità:** Una classe di servizio responsabile della costruzione e dell'interpretazione delle azioni definite all'interno di una `MultishipGroupingRule`. Traduce la configurazione dell'azione della regola in logica eseguibile.
-   `multishipsplit/classes/MultishipCartSlicer.php`
    -   **Responsabilità:** La classe centrale per la logica di divisione del carrello. Prende un oggetto `Cart` e, utilizzando le `MultishipGroupingRule` definite, divide i prodotti del carrello in un array di oggetti `MultishipShipmentGroup`.
-   `multishipsplit/classes/MultishipCheckoutPresenter.php`
    -   **Responsabilità:** Prepara i dati per la pagina di checkout del front-office. Prende i `MultishipShipmentGroup` e li formatta per la visualizzazione, inclusi i corrieri disponibili, i costi e le opzioni del punto di ritiro, per essere renderizzati dai template Smarty.
-   `multishipsplit/classes/MultishipCompatibility.php`
    -   **Responsabilità:** Gestisce i livelli di compatibilità per diverse versioni di PrestaShop o potenziali conflitti con altri moduli. Assicura che il modulo funzioni correttamente in vari ambienti.
-   `multishipsplit/classes/MultishipConditionBuilder.php`
    -   **Responsabilità:** Simile a `MultishipActionBuilder`, ma per le condizioni delle regole. Costruisce e interpreta le condizioni che determinano quando una `MultishipGroupingRule` deve essere applicata.
-   `multishipsplit/classes/MultishipConditionEvaluator.php`
    -   **Responsabilità:** Valuta un insieme di condizioni rispetto a un dato contesto (ad esempio, un prodotto, un carrello, un cliente) per determinare se una regola deve essere attivata.
-   `multishipsplit/classes/MultishipConditionTree.php`
    -   **Responsabilità:** Gestisce la struttura gerarchica delle condizioni (ad esempio, gruppi AND/OR) all'interno di una regola, consentendo espressioni logiche complesse.
-   `multishipsplit/classes/MultishipConfirmationPresenter.php`
    -   **Responsabilità:** Prepara i dati per la visualizzazione del riepilogo della divisione nella pagina di conferma dell'ordine.
-   `multishipsplit/classes/MultishipDashboardPresenter.php`
    -   **Responsabilità:** Raccoglie e formatta i dati per la dashboard del Back Office, inclusi KPI e dati dei grafici.
-   `multishipsplit/classes/MultishipGroupingEngine.php`
    -   **Responsabilità:** Orchestra l'intero processo di raggruppamento basato su regole. Recupera le regole attive, le applica sequenzialmente (in base alla priorità) al carrello e gestisce la creazione di `MultishipShipmentGroup`.
-   `multishipsplit/classes/MultishipGroupingRule.php`
    -   **Estende:** `ObjectModel`
    -   **Tabella database:** `mss_grouping_rule`
    -   **Campi `$definition`:** Memorizza la configurazione per ogni regola di divisione, inclusi il suo nome, la priorità, lo stato attivo e le condizioni e azioni serializzate.
    -   **Metodi pubblici chiave:** Metodi per salvare, caricare e gestire i dati delle regole.
-   `multishipsplit/classes/MultishipOrderLink.php`
    -   **Estende:** `ObjectModel`
    -   **Tabella database:** `mss_order_link`
    -   **Campi `$definition`:** Collega un `Order` di PrestaShop ai suoi `MultishipSplitGroup` corrispondenti, consentendo al modulo di tenere traccia di come un ordine è stato diviso.
    -   **Metodi pubblici chiave:** Metodi per creare e recuperare questi collegamenti.
-   `multishipsplit/classes/MultishipPaymentBridge.php`
    -   **Responsabilità:** Facilita il processo di pagamento quando un carrello è diviso. Assicura che l'importo totale dovuto per tutti i gruppi di spedizione sia correttamente passato al modulo di pagamento e che la conferma del pagamento aggiorni correttamente lo stato di tutti gli ordini associati.
-   `multishipsplit/classes/MultishipPayPlugRefundAdapter.php`
    -   **Responsabilità:** Fornisce un'integrazione specifica per il rimborso degli ordini divisi quando si utilizza il modulo di pagamento PayPlug. Ciò suggerisce che il modulo potrebbe avere adattatori simili per altri gateway di pagamento.
-   `multishipsplit/classes/MultishipPickupFactory.php`
    -   **Responsabilità:** Una classe factory per creare istanze di `MultishipPickupAdapterInterface` in base al corriere o al modulo in uso (ad esempio, per Mondial Relay, Colissimo).
-   `multishipsplit/classes/MultishipRefundLog.php`
    -   **Estende:** `ObjectModel`
    -   **Tabella database:** `mss_refund_log`
    -   **Campi `$definition`:** Registra le azioni di rimborso relative agli ordini divisi, particolarmente importante quando sono coinvolti rimborsi parziali o rimborsi su più ordini collegati.
-   `multishipsplit/classes/MultishipRuleContext.php`
    -   **Responsabilità:** Incapsula il contesto (ad esempio, carrello corrente, cliente, prodotto in fase di valutazione) per la valutazione delle regole, rendendo più facile passare i dati pertinenti ai valutatori delle condizioni.
-   `multishipsplit/classes/MultishipShipmentGroup.php`
    -   **Responsabilità:** Rappresenta una singola spedizione logica all'interno di un carrello diviso. Contiene una collezione di `MultishipShipmentProduct`, il corriere selezionato e i costi associati.
-   `multishipsplit/classes/MultishipShipmentProduct.php`
    -   **Responsabilità:** Rappresenta un articolo prodotto all'interno di un `MultishipShipmentGroup`, inclusa la sua quantità e gli attributi specifici rilevanti per quella spedizione.
-   `multishipsplit/classes/MultishipShippingCostAggregator.php`
    -   **Responsabilità:** Calcola il costo totale di spedizione sommando i costi di tutti i singoli `MultishipShipmentGroup`.
-   `multishipsplit/classes/MultishipSplitGroup.php`
    -   **Estende:** `ObjectModel`
    -   **Tabella database:** `mss_split_group`
    -   **Campi `$definition`:** Memorizza i dettagli su un gruppo di spedizione specifico che è stato creato come parte di un ordine diviso. Questo viene utilizzato per il tracciamento e la reportistica nel Back Office.
-   `multishipsplit/classes/MultishipSplitOrchestrator.php`
    -   **Responsabilità:** L'orchestratore di alto livello per l'intero processo di divisione, dalla suddivisione iniziale del carrello alla creazione dell'ordine e alla gestione del pagamento.
-   `multishipsplit/classes/Pickup/MultishipColissimoPickupAdapter.php`
    -   **Implementa:** `MultishipPickupAdapterInterface`
    -   **Responsabilità:** Fornisce una logica specifica per l'integrazione con i punti di ritiro Colissimo.
-   `multishipsplit/classes/Pickup/MultishipMondialRelayPickupAdapter.php`
    -   **Implementa:** `MultishipPickupAdapterInterface`
    -   **Responsabilità:** Fornisce una logica specifica per l'integrazione con i punti di ritiro Mondial Relay.
-   `multishipsplit/classes/Pickup/MultishipPickupAdapterInterface.php`
    -   **Responsabilità:** Definisce il contratto per tutti gli adattatori di integrazione dei punti di ritiro, garantendo un'interfaccia coerente per diversi corrieri.
-   `multishipsplit/override/classes/Cart.php`
    -   **Responsabilità:** Sovrascrive i metodi principali di `Cart` per intercettare e modificare il modo in cui i prodotti vengono aggiunti, rimossi e come vengono calcolati i costi di spedizione, consentendo alla logica di divisione del modulo di avere effetto. Questo è un override critico.
-   `multishipsplit/override/classes/PaymentModule.php`
    -   **Responsabilità:** Sovrascrive i metodi principali di `PaymentModule` per gestire il processo di pagamento per più ordini generati da un singolo carrello diviso. Assicura che un singolo pagamento copra tutti i sotto-ordini e che i loro stati siano correttamente aggiornati.

### 3.4 Risorse JavaScript (`views/js/`)

-   `multishipsplit/lib/searchTool/views/js/autocomplete.js`
    -   **Ambito:** Back-office.
    -   **Dettagli:** Fornisce la funzionalità di completamento automatico per gli input di ricerca, probabilmente utilizzata nel costruttore di regole per selezionare prodotti, categorie o altre entità.
-   `multishipsplit/lib/searchTool/views/views/js/autocomplete.js`
    -   **Ambito:** Back-office.
    -   **Dettagli:** Probabilmente un percorso duplicato o alternativo per lo script di completamento automatico, possibilmente per compatibilità o contesti di visualizzazione specifici.
-   `multishipsplit/views/js/adminActionBuilder.js`
    -   **Ambito:** Back-office (AdminMultishipRulesController).
    -   **Dettagli:** Gestisce l'interfaccia dinamica per la costruzione delle azioni delle regole (ad esempio, "Forza spedizione separata"). Gestisce l'aggiunta/rimozione dei tipi di azione e dei loro parametri associati.
-   `multishipsplit/views/js/adminConditionBuilder.js`
    -   **Ambito:** Back-office (AdminMultishipRulesController).
    -   **Dettagli:** Gestisce l'interfaccia dinamica per la costruzione delle condizioni delle regole. Consente agli amministratori di aggiungere più condizioni, raggrupparle con logica AND/OR e selezionare vari criteri (prodotto, categoria, ecc.).
-   `multishipsplit/views/js/adminMultishipSearchTool.js`
    -   **Ambito:** Back-office.
    -   **Dettagli:** Integra lo strumento di ricerca con completamento automatico nei moduli di amministrazione del modulo, in particolare per la selezione di prodotti, categorie o altre entità specifiche durante la definizione delle regole.
-   `multishipsplit/views/js/admin_dashboard.js`
    -   **Ambito:** Back-office (AdminMultishipIndexController).
    -   **Dettagli:** Gestisce gli elementi dinamici e il caricamento dei dati per la dashboard, potenzialmente inclusa la renderizzazione dei grafici (ad esempio, utilizzando Chart.js) e gli aggiornamenti dei KPI.
-   `multishipsplit/views/js/admin_rules.js`
    -   **Ambito:** Back-office (AdminMultishipRulesController).
    -   **Dettagli:** JavaScript generale per la pagina di gestione delle regole, inclusi il riordino delle regole tramite trascinamento, gli interruttori di abilitazione/disabilitazione e la gestione dell'invio dei moduli.
-   `multishipsplit/views/js/checkout.js`
    -   **Ambito:** Front-office (pagina di checkout).
    -   **Dettagli:** Questo è uno script critico per l'esperienza del front-office. Collega i listener di eventi alle modifiche della selezione del corriere per ogni gruppo di spedizione, invia richieste AJAX a `groups.php` o `pickup.php` per aggiornare i costi di spedizione o recuperare i punti di ritiro e aggiorna dinamicamente il riepilogo totale dell'ordine nella pagina di checkout. Probabilmente utilizza `prestashop.on` per eventi personalizzati.

### 3.5 Fogli di stile CSS (`views/css/`)

-   `multishipsplit/lib/searchTool/views/css/autocomplete.css`
    -   **Ambito:** Back-office.
    -   **Dettagli:** Stili per i menu a discesa di completamento automatico e i campi di input di ricerca utilizzati nei moduli di amministrazione.
-   `multishipsplit/lib/searchTool/views/views/css/autocomplete.css`
    -   **Ambito:** Back-office.
    -   **Dettagli:** Probabilmente un percorso duplicato o alternativo per gli stili di completamento automatico.
-   `multishipsplit/views/css/admin_condition_builder.css`
    -   **Ambito:** Back-office (AdminMultishipRulesController).
    -   **Dettagli:** Stila l'interfaccia dinamica per la costruzione delle condizioni all'interno del modulo di creazione/modifica delle regole, garantendo un layout chiaro e organizzato.
-   `multishipsplit/views/css/admin_dashboard.css`
    -   **Ambito:** Back-office (AdminMultishipIndexController).
    -   **Dettagli:** Stili per il layout della dashboard, i KPI, i grafici e la tabella delle divisioni recenti.
-   `multishipsplit/views/css/admin_order.css`
    -   **Ambito:** Back-office (pagina di visualizzazione dell'ordine).
    -   **Dettagli:** Stili per il widget personalizzato o le informazioni visualizzate all'interno della visualizzazione standard dell'ordine di PrestaShop, che mostrano come l'ordine è stato diviso.
-   `multishipsplit/views/css/admin_rules.css`
    -   **Ambito:** Back-office (AdminMultishipRulesController).
    -   **Dettagli:** Stili generali per la tabella di elenco delle regole, le azioni delle regole (abilita/disabilita) e il layout generale della pagina di gestione delle regole.
-   `multishipsplit/views/css/checkout.css`
    -   **Ambito:** Front-office (pagina di checkout).
    -   **Dettagli:** Stila la presentazione dei gruppi di spedizione divisi nella pagina di checkout, incluso il modo in cui i corrieri vengono visualizzati per ogni gruppo, il riepilogo dei costi e potenzialmente le interfacce di selezione del punto di ritiro. Gli sviluppatori possono sovrascrivere queste classi nel `custom.css` del loro tema o modificando i template del modulo.

### 3.6 Struttura del template Smarty (`views/templates/`)

#### Template hook (`views/templates/hook/`)

-   `multishipsplit/views/templates/hook/checkout_groups.tpl`
    -   **Hook:** Probabilmente `displayCarrierList` o un hook personalizzato iniettato nel passaggio di spedizione del checkout.
    -   **Output:** Il blocco visivo principale nella pagina di checkout che visualizza i prodotti raggruppati e consente ai clienti di selezionare un corriere per ogni singolo gruppo di spedizione. Qui avviene l'interazione principale del front-office.
-   `multishipsplit/views/templates/hook/order_confirmation_split.tpl`
    -   **Hook:** `displayOrderConfirmation` o un hook simile nella pagina di conferma dell'ordine.
    -   **Output:** Il riepilogo di come l'ordine è stato diviso, mostrando quali articoli erano in ogni spedizione e il corriere scelto, come configurato dall'impostazione "Visualizza riepilogo divisione nella pagina di conferma dell'ordine".
-   `multishipsplit/views/templates/hook/payment_top.tpl`
    -   **Hook:** `displayPaymentTop`
    -   **Output:** Potrebbe visualizzare un avviso o un messaggio informativo al cliente riguardo all'ordine diviso prima che proceda al pagamento, assicurandosi che comprenda che il costo totale include più spese di spedizione.

#### Template di amministrazione (`views/templates/admin/`)

-   `multishipsplit/lib/searchTool/views/scripts.tpl`
    -   **Output:** Blocco script Smarty per lo strumento di ricerca, probabilmente inclusi JavaScript e CSS.
-   `multishipsplit/lib/searchTool/views/views/scripts.tpl`
    -   **Output:** Percorso duplicato o alternativo per gli script dello strumento di ricerca.
-   `multishipsplit/views/templates/admin/actionBuilder.tpl`
    -   **Output:** La struttura HTML per l'interfaccia dinamica del costruttore di azioni all'interno del modulo di creazione/modifica delle regole.
-   `multishipsplit/views/templates/admin/dashboard_chart.tpl`
    -   **Output:** Template per il rendering di un grafico specifico nella dashboard, probabilmente utilizzando una libreria di grafici JavaScript.
-   `multishipsplit/views/templates/admin/dashboard_kpi_strip.tpl`
    -   **Output:** Template per la striscia degli indicatori chiave di prestazione (KPI) nella parte superiore della dashboard.
-   `multishipsplit/views/templates/admin/dashboard_recent_splits.tpl`
    -   **Output:** Template per la visualizzazione di un elenco di ordini divisi di recente nella dashboard.
-   `multishipsplit/views/templates/admin/dashboard_stats.tpl`
    -   **Output:** Blocco di statistiche generali nella dashboard.
-   `multishipsplit/views/templates/admin/menu.tpl`
    -   **Output:** Definisce le voci di menu personalizzate del modulo nella navigazione del Back Office di PrestaShop (ad esempio, sotto "Spedizione").
-   `multishipsplit/views/templates/admin/order_split_widget.tpl`
    -   **Output:** Un widget o blocco personalizzato visualizzato all'interno della pagina di dettaglio dell'ordine standard di PrestaShop nel Back Office, che fornisce un riepilogo di come quell'ordine specifico è stato diviso.
-   `multishipsplit/views/templates/admin/policyConditionBuilder.tpl`
    -   **Output:** La struttura HTML per l'interfaccia dinamica del costruttore di condizioni all'interno del modulo di creazione/modifica delle regole.
-   `multishipsplit/views/templates/admin/split_view.tpl`
    -   **Output:** Una vista dettagliata per un ordine diviso specifico, potenzialmente accessibile dall'elenco "Divisioni spedizione".

### 3.7 Schema del database e mappa degli hook

#### Tabelle del database

-   `ps_mss_grouping_rule`: Memorizza le definizioni di tutte le regole di raggruppamento delle spedizioni create dall'amministratore.
    -   `id_mss_grouping_rule` (PK)
    -   `name` (VARCHAR)
    -   `priority` (INT)
    -   `active` (TINYINT)
    -   `conditions` (TEXT - array serializzato/JSON di condizioni)
    -   `actions` (TEXT - array serializzato/JSON di azioni)
    -   `date_add` (DATETIME)
    -   `date_upd` (DATETIME)
-   `ps_mss_split_group`: Memorizza i dettagli di ogni singolo gruppo di spedizione creato per un ordine diviso.
    -   `id_mss_split_group` (PK)
    -   `id_order` (FK a `ps_orders`)
    -   `id_cart` (FK a `ps_cart`)
    -   `id_carrier` (FK a `ps_carrier`)
    -   `shipping_cost_tax_excl` (DECIMAL)
    -   `shipping_cost_tax_incl` (DECIMAL)
    -   `products` (TEXT - array serializzato di prodotti in questo gruppo)
    -   `pickup_point_data` (TEXT - dati serializzati per il punto di ritiro, se selezionato)
    -   `date_add` (DATETIME)
    -   `date_upd` (DATETIME)
-   `ps_mss_order_link`: Collega un singolo `id_order` di PrestaShop (l'ordine "padre") a più `id_order` (gli ordini "figli" creati per ogni spedizione divisa).
    -   `id_mss_order_link` (PK)
    -   `id_parent_order` (FK a `ps_orders`)
    -   `id_child_order` (FK a `ps_orders`)
    -   `id_mss_split_group` (FK a `ps_mss_split_group`)
    -   `date_add` (DATETIME)
-   `ps_mss_refund_log`: Registra gli eventi di rimborso relativi agli ordini divisi.
    -   `id_mss_refund_log` (PK)
    -   `id_order` (FK a `ps_orders`)
    -   `id_order_slip` (FK a `ps_order_slip`)
    -   `amount` (DECIMAL)
    -   `reason` (TEXT)
    -   `date_add` (DATETIME)
-   `ps_configuration`: Le impostazioni del modulo sono memorizzate qui con chiavi come `MULTISHIPSPLIT_ENABLED`, `MULTISHIPSPLIT_DEBUG_MODE`, ecc.

#### Tabella degli hook registrati

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di tutte le pagine del front-office. | Iniezione di risorse CSS e JS per la funzionalità del front-office (ad es. `checkout.js`, `checkout.css`). |
| `displayBackOfficeHeader` | Nella sezione `<head>` di tutte le pagine del back-office. | Iniezione di risorse CSS e JS per i controller di amministrazione (ad es. `admin_rules.js`, `admin_condition_builder.css`). |
| `displayAdminProductsExtra` | Nella pagina di modifica del prodotto nel Back Office. | Potrebbe aggiungere una scheda o una sezione per configurare regole di divisione specifiche del prodotto o override. |
| `actionCartSave` | Dopo che un carrello è stato salvato o aggiornato. | Intercetta le modifiche del carrello per attivare la logica di divisione e ricalcolare i gruppi di spedizione. |
| `actionValidateOrder` | Dopo che un ordine è stato convalidato con successo. | Elabora il carrello diviso in più ordini PrestaShop, li collega e memorizza i dati del gruppo diviso. |
| `actionOrderSlipAdd` | Quando viene aggiunto un buono d'ordine (rimborso). | Gestisce la logica di rimborso per gli ordini divisi, potenzialmente registrando rimborsi parziali su ordini collegati. |
| `displayCarrierList` | Nel passaggio di spedizione del checkout, dove vengono visualizzate le opzioni del corriere. | Sostituisce o aumenta l'elenco standard dei corrieri con l'interfaccia di selezione della spedizione raggruppata (`checkout_groups.tpl`). |
| `displayOrderConfirmation` | Nella pagina finale di conferma dell'ordine. | Visualizza il riepilogo dell'ordine diviso al cliente (`order_confirmation_split.tpl`). |
| `displayPaymentTop` | Prima della selezione del metodo di pagamento nella pagina di checkout. | Può visualizzare messaggi o riepiloghi importanti relativi ai costi di spedizione divisi (`payment_top.tpl`). |
| `displayAdminOrder` | Nella pagina dei dettagli dell'ordine nel Back Office. | Inietta il `order_split_widget.tpl` per mostrare come l'ordine specifico è stato diviso. |
| `actionObjectCartUpdateAfter` | Dopo che un oggetto Cart è stato aggiornato. | Simile a `actionCartSave`, assicura che la logica di divisione venga rivalutata. |
| `actionObjectOrderAddAfter` | Dopo che un nuovo oggetto Order è stato aggiunto. | Utilizzato per finalizzare il collegamento di ordini padre/figlio e i dati del gruppo diviso. |
| `actionObjectOrderUpdateAfter` | Dopo che un oggetto Order è stato aggiornato. | Potrebbe aggiornare gli stati del gruppo diviso o i dati correlati se un ordine viene modificato. |
| `actionFrontControllerSetMedia` | Prima che un controller front-office renda il suo contenuto. | Assicura che i JS/CSS necessari siano caricati per le pagine del front-office. |
| `actionAdminControllerSetMedia` | Prima che un controller admin renda il suo contenuto. | Assicura che i JS/CSS necessari siano caricati per le pagine del back-office. |
| `displayAdminStatsModules` | Nella pagina Moduli > Statistiche. | Potrebbe aggiungere statistiche specifiche del modulo alla dashboard di PrestaShop. |
| `displayDashboardTop` | Nella parte superiore della dashboard di PrestaShop. | Può visualizzare un riepilogo rapido o un avviso dal modulo. |
| `displayDashboardZoneOne` | Nella prima zona della dashboard di PrestaShop. | Può visualizzare un widget specifico del modulo nella dashboard. |
| `displayDashboardZoneTwo` | Nella seconda zona della dashboard di PrestaShop. | Può visualizzare un widget specifico del modulo nella dashboard. |

## 4. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, fai riferimento al tuo account cliente su MyPresta.eu.

-   **Aggiornamenti del modulo:** Accedi a [MyPresta.eu Cronologia ordini e download](https://mypresta.eu/my-account/orders/) per scaricare la versione più recente del modulo "Dividi carrello in spedizioni separate".
-   **Supporto tecnico:** Se riscontri problemi o hai domande non trattate in questa guida, apri un ticket di supporto tramite il tuo account cliente MyPresta.eu. Il nostro team è pronto ad assisterti.

## 5. ## Galleria

![Dashboard nella pagina di configurazione del modulo che mostra le statistiche del modulo](https://mypresta.eu/docs/images/docs/02-shipping-multi-carrier-order-split_1791740311.webp)
"""
