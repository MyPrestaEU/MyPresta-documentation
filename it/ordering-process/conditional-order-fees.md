---
title: "Commissioni Condizionali sull'Ordine - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Commissioni Condizionali sull'Ordine di MyPresta.eu."
sidebar:
  label: "Commissioni Condizionali sull'Ordine - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Conditional Order Fees su MyPresta.eu](https://mypresta.eu/modules/ordering-process/conditional-order-fees.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/conditional-order-fees/)
>
> ---


# Commissioni Condizionali sull'Ordine

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL) tipicamente disponibili sulla maggior parte degli ambienti di hosting compatibili con PrestaShop.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Commissioni Condizionali sull'Ordine)

Questa è la schermata di configurazione principale dove abiliti o disabiliti il modulo e imposti il "prodotto" fondamentale che rappresenta le tue commissioni.

- **Posizione del menu:** Back Office > Moduli > Gestione moduli > Commissioni Condizionali sull'Ordine > Configura

#### Impostazioni Generali

- **Abilita Modulo:**

  - **Cosa fa questa impostazione:** Questo è l'interruttore principale per l'intero modulo.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il modulo valuterà attivamente le tue politiche di commissione definite e applicherà le commissioni ai carrelli che soddisfano le condizioni.
    - *Quando disabilitato:* Nessuna commissione verrà applicata da questo modulo, indipendentemente dalle impostazioni della tua politica.
  - **Valore consigliato:** SÌ (una volta configurate le tue politiche).
  - **Scenario / esempio del commerciante:** Hai finito di impostare tutte le tue politiche di commissione e sei pronto per andare online. Abilita questo per iniziare ad addebitare le commissioni. Se hai bisogno di interrompere temporaneamente tutte le commissioni per manutenzione o una promozione, disabilitalo.
- **ID Prodotto Commissione:**

  - **Cosa fa questa impostazione:** Questa impostazione cruciale collega le tue commissioni a un prodotto specifico e nascosto nel tuo catalogo. PrestaShop ha bisogno di un "prodotto" per rappresentare qualsiasi articolo aggiunto al carrello, anche se si tratta di un servizio o di una commissione. Questo modulo crea un prodotto speciale e non visibile per questo scopo durante l'installazione.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su un ID Prodotto valido:* Il modulo utilizzerà questo prodotto per rappresentare la commissione nel carrello, nel checkout e nei dettagli dell'ordine. Il nome del prodotto verrà sostituito dall'etichetta personalizzata della commissione e il suo prezzo verrà sovrascritto dalla commissione calcolata.
    - *Quando impostato su un ID Prodotto non valido o inesistente:* Il modulo non sarà in grado di aggiungere commissioni al carrello, poiché non avrà un prodotto "segnaposto" valido da utilizzare.
  - **Valore consigliato:** Utilizza l'ID del prodotto speciale "Commissione Condizionale sull'Ordine" creato dal modulo durante l'installazione. Puoi trovare questo ID cercando "Commissione Condizionale sull'Ordine" nel tuo elenco Prodotti (anche se di solito è nascosto dal front office). Il modulo spesso lo precompila per te.
  - **Scenario / esempio del commerciante:** Il modulo crea automaticamente un prodotto chiamato "Commissione Condizionale sull'Ordine" (o simile) e imposta il suo ID qui. Generalmente non dovresti cambiarlo a meno che tu non voglia intenzionalmente utilizzare un prodotto diverso come segnaposto della commissione (cosa non consigliata per la maggior parte degli utenti).

### 2.2 Schermate di amministrazione dedicate e viste del controller

Il modulo fornisce sezioni dedicate nel tuo Back Office di PrestaShop per gestire le tue politiche di commissione e rivedere la loro applicazione.

#### 2.2.1 Dashboard Commissioni Condizionali sull'Ordine (Back Office > Commissioni Condizionali sull'Ordine > Dashboard)

Questa schermata fornisce una panoramica dell'attività del tuo modulo, inclusa una sintesi delle commissioni applicate e un rapido accesso alla gestione delle politiche.

- **Nome schermata e posizione del menu:** **Commissioni Condizionali sull'Ordine > Dashboard** (si trova sotto la voce di menu principale "Commissioni Condizionali sull'Ordine" nella barra laterale sinistra).
- **Azioni e impostazioni disponibili:**
  - **Statistiche di riepilogo:** Visualizza metriche chiave come il totale delle commissioni raccolte, il numero di ordini con commissioni e la commissione media per ordine. Questo ti aiuta a comprendere l'impatto delle tue politiche di commissione.
  - **Commissioni recenti applicate:** Un elenco rapido degli ordini più recenti in cui è stata applicata una commissione condizionale, inclusi l'ID dell'ordine, il cliente e l'importo della commissione.
  - **Link rapidi:** Link diretti a "Gestisci politiche" e "Visualizza registro di controllo".
- **Effetto delle modifiche:** Questa schermata è principalmente per il monitoraggio e la navigazione. Non vengono apportate modifiche dirette qui, ma riflette l'impatto delle tue politiche di commissione.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Controlla periodicamente questa dashboard per monitorare le prestazioni delle tue politiche di commissione e assicurarti che funzionino come previsto.

#### 2.2.2 Gestisci politiche di commissione (Back Office > Commissioni Condizionali sull'Ordine > Politiche)

Qui è dove definisci, modifichi e gestisci tutte le tue regole di commissione condizionali. Ogni "politica" è un insieme di condizioni che, quando soddisfatte, applicheranno una commissione specifica.

- **Nome schermata e posizione del menu:** **Commissioni Condizionali sull'Ordine > Politiche** (si trova sotto la voce di menu principale "Commissioni Condizionali sull'Ordine" nella barra laterale sinistra).
- **Azioni e impostazioni disponibili:**
  - **Elenco politiche:** Una tabella che mostra tutte le tue politiche di commissione esistenti, inclusi il loro nome, stato (abilitato/disabilitato), priorità e l'importo/tipo della commissione.
  - **Aggiungi nuova politica:** Clicca sul pulsante "Aggiungi nuova politica" per creare una nuova regola di commissione.
    - **Nome politica:** Un nome descrittivo per il tuo riferimento interno (ad esempio, "Commissione di gestione piccolo ordine", "Supplemento imballaggio fragile").
    - **Stato:** Abilita o disabilita la politica.
    - **Priorità:** Se più politiche potessero applicarsi allo stesso carrello, quella con la priorità più alta (numero più basso) verrà valutata per prima. Se "Interrompi l'elaborazione di ulteriori regole" è abilitato, si applicherà solo la regola corrispondente con la priorità più alta.
    - **Tipo di commissione:**
      - **Importo fisso:** Un valore monetario specifico (ad esempio, 5,00 €).
      - **Percentuale del totale carrello:** Una percentuale del subtotale del carrello (ad esempio, 2%).
      - **Percentuale dei prodotti nel carrello:** Una percentuale del prezzo totale dei prodotti nel carrello (escluse spedizione/tasse).
    - **Valore commissione:** L'importo o la percentuale effettivi in base al tipo di commissione selezionato.
    - **Etichetta commissione (multilingua):** Il testo che i clienti vedranno nel loro carrello e nel riepilogo dell'ordine (ad esempio, "Commissione di gestione", "Costo del servizio"). Questo può essere tradotto per diverse lingue.
    - **Costruttore di condizioni:** Questo è il cuore della politica. Puoi costruire regole complesse utilizzando gruppi "AND" / "OR", combinando condizioni come:
      - Valore del carrello (totale, subtotale, quantità)
      - Gruppo di clienti
      - Paese, stato o zona
      - Corriere
      - Prodotti specifici nel carrello (per ID, categoria, produttore, fornitore)
      - Metodo di pagamento
      - E altro ancora…
    - **Interrompi l'elaborazione di ulteriori regole:** Se abilitato, una volta che questa politica si applica, nessun'altra politica con priorità inferiore verrà valutata per lo stesso carrello.
  - **Modifica/Elimina politiche:** Modifica le politiche esistenti o rimuovile.
  - **Duplica politica:** Crea rapidamente una nuova politica basata su una esistente, risparmiando tempo nella creazione di regole simili.
- **Effetto delle modifiche:** L'aggiunta, la modifica o l'eliminazione delle politiche influisce direttamente su quali commissioni vengono applicate ai carrelli dei clienti e in quali circostanze. Politiche configurate in modo errato possono portare a addebiti inaspettati o mancati ricavi.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1.  Inizia definendo i tuoi scenari di commissione più comuni.
  2.  Utilizza il pulsante "Aggiungi nuova politica" per creare ogni regola.
  3.  Costruisci attentamente le tue condizioni utilizzando il costruttore. Testa accuratamente utilizzando il simulatore (se disponibile, vedi registro di controllo) per assicurarti che funzionino come previsto.
  4.  Imposta priorità appropriate, specialmente se hai condizioni sovrapposte.
  5.  Rivedi e aggiorna regolarmente le politiche man mano che le tue esigenze aziendali o le promozioni cambiano.

#### 2.2.3 Registro di controllo (Back Office > Commissioni Condizionali sull'Ordine > Registro di controllo)

Il registro di controllo fornisce una cronologia dettagliata di ogni istanza in cui il modulo ha valutato un carrello e ha applicato (o non ha applicato) una commissione. Questo è prezioso per la risoluzione dei problemi e per capire perché determinate commissioni sono state o non sono state addebitate.

- **Nome schermata e posizione del menu:** **Commissioni Condizionali sull'Ordine > Registro di controllo** (si trova sotto la voce di menu principale "Commissioni Condizionali sull'Ordine" nella barra laterale sinistra).
- **Azioni e impostazioni disponibili:**
  - **Voci di registro:** Una tabella che mostra ogni evento di valutazione, inclusi:
    - Data e ora
    - Cliente (se loggato)
    - ID carrello
    - Politica applicata (se presente)
    - Importo commissione (se applicata)
    - Stato (ad esempio, "Commissione applicata", "Nessuna commissione applicata", "Politica non soddisfatta")
  - **Vista dettagliata:** Clicca su una voce di registro per vedere una ripartizione completa di come le condizioni sono state valutate per quel carrello specifico, mostrando quali condizioni sono state superate e quali fallite. Questo è come un "simulatore" per eventi passati.
  - **Filtro e ricerca:** Filtra le voci di registro per data, cliente, ID carrello o politica per trovare rapidamente eventi specifici.
- **Effetto delle modifiche:** Questa schermata è per la revisione e il debug. Non vengono apportate modifiche dirette qui, ma fornisce informazioni critiche sul comportamento del modulo.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1.  Se un cliente segnala una commissione inaspettata o l'assenza di una commissione attesa, utilizza il registro di controllo per indagare.
  2.  Filtra per nome del cliente o ID del carrello per vedere esattamente quali politiche sono state valutate e perché.
  3.  Utilizza la vista dettagliata per individuare quale condizione specifica ha causato il superamento o il fallimento di una politica.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Configurazione Modulo** | Abilita Modulo | SÌ | Interruttore principale per attivare/disattivare tutte le funzionalità del modulo. |
|  | ID Prodotto Commissione | ID generato automaticamente | Collega le commissioni a un prodotto nascosto per il sistema del carrello di PrestaShop. Non modificare se non istruito. |
| **Politiche** | Nome Politica | N/A | Etichetta interna per la tua regola di commissione. |
|  | Stato | Abilitato | Attiva/disattiva una singola politica di commissione. |
|  | Priorità | 1 (numero più basso = priorità più alta) | Determina l'ordine di valutazione se più politiche potrebbero applicarsi. |
|  | Tipo di Commissione | Importo Fisso | Scegli come viene calcolata la commissione (fissa, % del carrello, % dei prodotti). |
|  | Valore Commissione | 0.00 | L'importo o la percentuale della commissione. |
|  | Etichetta Commissione | "Commissione di gestione" (esempio) | Testo visibile al cliente per la commissione nel carrello/ordine. |
|  | Costruttore di Condizioni | N/A | Definisci i criteri specifici (carrello, cliente, prodotto, ecc.) per l'applicazione della commissione. |
|  | Interrompi l'elaborazione di ulteriori regole | No | Se abilitato, impedisce l'applicazione di politiche con priorità inferiore una volta che questa corrisponde. |
| **Registro di Controllo** | (Tutte le voci) | N/A | Fornisce una cronologia dettagliata delle valutazioni delle commissioni per la risoluzione dei problemi e il monitoraggio. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho impostato una politica, ma la commissione non compare nel carrello.**
R1:

-   **Controlla lo stato del modulo:** Assicurati che l'impostazione "Abilita Modulo" nella pagina di configurazione principale sia impostata su SÌ.
-   **Controlla lo stato della politica:** Assicurati che la politica specifica che ti aspetti si applichi sia "Abilitata" nell'elenco delle politiche.
-   **Rivedi le condizioni:** Ricontrolla le condizioni della tua politica. Sono tutte realmente soddisfatte dal carrello attuale? Utilizza il Registro di controllo (Commissioni Condizionali sull'Ordine > Registro di controllo) per vedere come le tue condizioni sono state valutate per un carrello di prova.
-   **ID Prodotto Commissione:** Verifica che l' "ID Prodotto Commissione" nella pagina di configurazione principale sia corretto e punti al prodotto speciale creato dal modulo.
-   **Cache:** Svuota la cache di PrestaShop (Parametri Avanzati > Prestazioni) e la cache del tuo browser.

**D2: La commissione compare, ma l'etichetta o l'importo sono sbagliati.**
R2:

-   **Impostazioni della politica:** Vai alla politica specifica in "Commissioni Condizionali sull'Ordine > Politiche" e verifica le impostazioni "Valore Commissione" e "Etichetta Commissione". Assicurati che l'etichetta sia tradotta correttamente per la lingua che stai testando.
-   **Politiche multiple:** Se più politiche potrebbero potenzialmente applicarsi, controlla la loro "Priorità" e l'impostazione "Interrompi l'elaborazione di ulteriori regole". Una politica con priorità più alta potrebbe essere applicata invece di quella che ti aspetti.

**D3: Posso tradurre l'etichetta della commissione per diverse lingue?**
R3: Sì! Quando modifichi una politica, il campo "Etichetta Commissione" avrà tipicamente un selettore di lingua (un'icona a bandiera). Clicca su questo per inserire le traduzioni per ogni lingua installata nel tuo negozio.

**D4: Cosa succede se elimino il "Prodotto Commissione" che il modulo utilizza?**
R4: Se elimini il prodotto specificato nell'impostazione "ID Prodotto Commissione", il modulo non sarà più in grado di aggiungere commissioni al carrello. È fondamentale non eliminare questo prodotto. Se viene accidentalmente eliminato, potrebbe essere necessario reinstallare il modulo (che lo ricreerà) o creare manualmente un nuovo prodotto nascosto e aggiornare l'impostazione "ID Prodotto Commissione".

**D5: Il modulo sembra rallentare il mio processo di checkout.**
R5: Sebbene il modulo sia ottimizzato per le prestazioni, politiche complesse con molte condizioni, specialmente quelle che coinvolgono controlli estesi sui prodotti, possono aggiungere un leggero overhead.

-   **Semplifica le condizioni:** Rivedi le tue politiche. È possibile semplificare o combinare alcune condizioni?
-   **Prioritizza:** Utilizza le impostazioni "Priorità" e "Interrompi l'elaborazione di ulteriori regole" in modo efficace per ridurre al minimo il numero di politiche che devono essere completamente valutate per un dato carrello.
-   **Risorse del server:** Assicurati che il tuo ambiente di hosting soddisfi le specifiche consigliate da PrestaShop.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo Commissioni Condizionali sull'Ordine è costruito seguendo il modello MVC di PrestaShop, sfruttando pesantemente `ObjectModel` per la persistenza dei dati e una robusta architettura basata su eventi tramite gli hook di PrestaShop. Introduce un sofisticato motore di valutazione delle condizioni, consentendo una logica `AND`/`OR` complessa e annidata per determinare l'applicabilità delle commissioni. Il modulo si integra perfettamente nel flusso di elaborazione del carrello e dell'ordine aggiungendo dinamicamente un "prodotto virtuale" al carrello quando le condizioni sono soddisfatte. Le interfacce di amministrazione sono costruite utilizzando i componenti `AdminController` e `HelperList`/`HelperForm` di PrestaShop, con JavaScript personalizzato per il costruttore di condizioni e il simulatore.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

- `conorderfee/controllers/front/index.php`
  - **Nome classe:** `ConorderfeeIndexModuleFrontController` (estende `ModuleFrontController`)
  - **Responsabilità:** Questo controller probabilmente funge da fallback o da semplice punto di ingresso, ma la logica principale per l'applicazione delle commissioni è gestita principalmente tramite hook, non tramite rotte dirette del front-controller. Potrebbe essere utilizzato per informazioni di base sul modulo o reindirizzamento se acceduto direttamente.

#### Controller di amministrazione Back-Office

- `conorderfee/controllers/admin/AdminconorderfeeAuditLog.php`
  - **Nome classe:** `AdminconorderfeeAuditLogController` (estende `ModuleAdminController`)
  - **Nome scheda:** Commissioni Condizionali sull'Ordine > Registro di controllo
  - **Entità gestita:** `ConorderfeeLog` (ORM per la tabella `ps_conorderfee_log`).
  - **Responsabilità:** Gestisce la visualizzazione e il filtraggio del registro di controllo delle commissioni. Utilizza `HelperList` per renderizzare la tabella delle voci di registro e fornisce viste dettagliate per le singole voci di registro, mostrando il processo di valutazione delle condizioni.
- `conorderfee/controllers/admin/AdminconorderfeePolicies.php`
  - **Nome classe:** `AdminconorderfeePoliciesController` (estende `ModuleAdminController`)
  - **Nome scheda:** Commissioni Condizionali sull'Ordine > Politiche
  - **Entità gestita:** `ConorderfeePolicy` (ORM per la tabella `ps_conorderfee_policy`).
  - **Responsabilità:** Gestisce la creazione, la modifica, la duplicazione e l'eliminazione delle politiche di commissione. Utilizza `HelperList` per la panoramica delle politiche e `HelperForm` per il modulo di creazione/modifica delle politiche, che include la complessa interfaccia del costruttore di condizioni.
- `conorderfee/controllers/admin/index.php`
  - **Nome classe:** `ConorderfeeIndexModuleAdminController` (estende `ModuleAdminController`)
  - **Nome scheda:** Commissioni Condizionali sull'Ordine > Dashboard
  - **Entità gestita:** N/A (vista dashboard)
  - **Responsabilità:** Funge da dashboard principale per il modulo nel back office, visualizzando statistiche e collegamenti rapidi. È il controller predefinito caricato quando si fa clic sulla voce di menu principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

- `conorderfee/classes/ConorderfeeAdmin.php`
  - **Responsabilità:** Classe di utilità per funzionalità specifiche dell'amministrazione, potenzialmente gestendo la registrazione del menu, la gestione delle schede e gli helper generali relativi all'amministrazione.
- `conorderfee/classes/ConorderfeeAuditLog.php`
  - **Tabella database:** `ps_conorderfee_log`
  - **Estende ObjectModel:** Sì.
  - **Campi `$definition`:** `id_conorderfee_log`, `id_cart`, `id_order`, `id_customer`, `id_conorderfee_policy`, `fee_amount`, `fee_label`, `conditions_snapshot`, `evaluation_result`, `date_add`.
  - **Metodi pubblici chiave:** Metodi per salvare le voci di registro, recuperare i dati del registro e potenzialmente formattare i dettagli del registro per la visualizzazione.
- `conorderfee/classes/ConorderfeeCartState.php`
  - **Responsabilità:** Una classe helper per incapsulare lo stato attuale del carrello e il contesto correlato (cliente, indirizzo, corriere, ecc.) per la valutazione delle condizioni. Fornisce metodi per recuperare varie proprietà del carrello necessarie dalle condizioni.
- `conorderfee/classes/ConorderfeeCompatibility.php`
  - **Responsabilità:** Gestisce i livelli di compatibilità per diverse versioni di PrestaShop (ad esempio, 1.7 vs. 8.x vs. 9.x) per garantire che il modulo funzioni correttamente su tutte le versioni supportate.
- `conorderfee/classes/ConorderfeeCondition.php`
  - **Tabella database:** `ps_conorderfee_condition`
  - **Estende ObjectModel:** Sì.
  - **Campi `$definition`:** `id_conorderfee_condition`, `id_conorderfee_condition_group`, `type`, `operator`, `value`, `is_inverted`.
  - **Metodi pubblici chiave:** Rappresenta una singola condizione all'interno di una politica (ad esempio, "Totale carrello > 100"). Metodi per salvare, caricare e potenzialmente convalidare i dati delle condizioni.
- `conorderfee/classes/ConorderfeeConditionEvaluator.php`
  - **Responsabilità:** Il motore logico principale per valutare un `ConorderfeeConditionTree` rispetto a un `ConorderfeeCartState`. Elabora ricorsivamente gruppi di condizioni e singole condizioni per determinare se una politica si applica.
- `conorderfee/classes/ConorderfeeConditionGroup.php`
  - **Tabella database:** `ps_conorderfee_condition_group`
  - **Estende ObjectModel:** Sì.
  - **Campi `$definition`:** `id_conorderfee_condition_group`, `id_conorderfee_policy`, `id_parent_group`, `operator` (`AND`/`OR`).
  - **Metodi pubblici chiave:** Rappresenta un gruppo di condizioni (ad esempio, "Condizione A AND (Condizione B OR Condizione C)"). Gestisce le sue condizioni figlie e i sottogruppi.
- `conorderfee/classes/ConorderfeeConditionTree.php`
  - **Responsabilità:** Rappresenta la struttura gerarchica delle condizioni per una politica (gruppo radice, sottogruppi, singole condizioni). Utilizzato da `ConorderfeeConditionEvaluator`.
- `conorderfee/classes/ConorderfeeContext.php`
  - **Responsabilità:** Un wrapper attorno all'oggetto `Context` di PrestaShop, potenzialmente aggiungendo dati di contesto specifici del modulo o semplificando l'accesso a elementi di contesto comuni.
- `conorderfee/classes/ConorderfeeDashboard.php`
  - **Responsabilità:** Fornisce dati e logica per la vista dashboard del modulo, recuperando statistiche e voci di registro recenti.
- `conorderfee/classes/ConorderfeeEngine.php`
  - **Responsabilità:** L'orchestratore centrale per la logica front-office del modulo. Si aggancia a vari eventi di PrestaShop, recupera le politiche attive, utilizza `ConorderfeeConditionEvaluator` per controllare le condizioni e aggiunge il prodotto commissione al carrello se applicabile.
- `conorderfee/classes/ConorderfeeFeeProduct.php`
  - **Responsabilità:** Gestisce lo speciale "prodotto commissione" che rappresenta l'addebito condizionale nel carrello. Gestisce la sua creazione durante l'installazione e assicura che sia configurato correttamente come prodotto virtuale e non visibile.
- `conorderfee/classes/ConorderfeeListRenderer.php`
  - **Responsabilità:** Una classe helper per il rendering di elenchi nel back office, potenzialmente estendendo `HelperList` o fornendo una logica di rendering di colonne personalizzata.
- `conorderfee/classes/ConorderfeeLog.php`
  - **Tabella database:** `ps_conorderfee_log` (stessa di `ConorderfeeAuditLog`, probabilmente un alias o una classe base)
  - **Estende ObjectModel:** Sì.
  - **Campi `$definition`:** Uguali a `ConorderfeeAuditLog`.
  - **Metodi pubblici chiave:** Metodi per la registrazione degli eventi, la memorizzazione dei risultati della valutazione e il recupero dei dati del registro.
- `conorderfee/classes/ConorderfeePolicy.php`
  - **Tabella database:** `ps_conorderfee_policy`
  - **Estende ObjectModel:** Sì.
  - **Campi `$definition`:** `id_conorderfee_policy`, `name`, `active`, `priority`, `fee_type`, `fee_value`, `fee_label`, `stop_further_rules`, `date_add`, `date_upd`.
  - **Metodi pubblici chiave:** Rappresenta una politica di commissione completa. Metodi per salvare, caricare e gestire i suoi `ConorderfeeConditionGroup` associati.
- `conorderfee/classes/ConorderfeePolicyDuplicator.php`
  - **Responsabilità:** Gestisce la logica per la duplicazione di una politica di commissione esistente, incluse tutte le sue condizioni e gruppi associati, per semplificare la creazione delle politiche.
- `conorderfee/classes/ConorderfeePreset.php`
  - **Responsabilità:** Gestisce i tipi di condizione e gli operatori predefiniti per il costruttore di condizioni (ad esempio, "Totale carrello", "Gruppo clienti", "è maggiore di", "è uno di").
- `conorderfee/classes/ConorderfeeRule.php`
  - **Responsabilità:** Probabilmente una classe astratta o base per la definizione di regole, o un tipo specifico di regola all'interno del costruttore di condizioni.
- `conorderfee/classes/ConorderfeeTreeRepository.php`
  - **Responsabilità:** Gestisce la persistenza e il recupero della struttura dell'albero delle condizioni (politiche, gruppi, condizioni) dal database.
- `conorderfee/classes/index.php`
  - **Responsabilità:** File vuoto, tipicamente utilizzato per prevenire l'elenco delle directory.

### 4.4 Risorse JavaScript (`views/js/`)

- `conorderfee/lib/searchTool/views/js/autocomplete.js`
  - **Ambito:** Back-office.
  - **Descrizione:** Fornisce la funzionalità di completamento automatico per gli input di ricerca, probabilmente utilizzato per selezionare prodotti, categorie, clienti, ecc., all'interno del costruttore di condizioni.
- `conorderfee/lib/searchTool/views/views/js/autocomplete.js`
  - **Ambito:** Back-office.
  - **Descrizione:** Duplicato del precedente, probabilmente un errore di percorso o un file legacy.
- `conorderfee/views/js/adminConditionBuilder.js`
  - **Ambito:** Back-office (`AdminconorderfeePoliciesController`).
  - **Descrizione:** Il JavaScript principale per l'interfaccia interattiva del costruttore di condizioni. Gestisce l'aggiunta/rimozione di condizioni e gruppi, la gestione della logica `AND`/`OR`, il caricamento dinamico dei tipi di condizione e degli operatori e l'aggiornamento dell'interfaccia utente in base all'input dell'utente.
- `conorderfee/views/js/adminConorderfeeDashboard.js`
  - **Ambito:** Back-office (`AdminconorderfeeDashboardController`).
  - **Descrizione:** JavaScript per la dashboard, potenzialmente gestendo aggiornamenti AJAX per statistiche, rendering di grafici o elementi interattivi sulla dashboard.
- `conorderfee/views/js/adminConorderfeeSearchTool.js`
  - **Ambito:** Back-office.
  - **Descrizione:** Integra lo strumento di ricerca con completamento automatico (da `lib/searchTool`) in vari moduli di amministrazione, in particolare per la selezione di entità nelle condizioni.
- `conorderfee/views/js/adminConorderfeeSimulator.js`
  - **Ambito:** Back-office (probabilmente nella pagina di modifica della politica o nel registro di controllo).
  - **Descrizione:** Fornisce uno strumento di valutazione delle condizioni in tempo reale o simulato nel back office, consentendo agli amministratori di testare le politiche rispetto a scenari di carrello ipotetici senza effettuare un ordine reale.
- `conorderfee/views/js/adminPolicyRules.js`
  - **Ambito:** Back-office (`AdminconorderfeePoliciesController`).
  - **Descrizione:** Gestisce le interazioni JavaScript generali nell'elenco delle politiche e nelle pagine di modifica, come l'abilitazione/disabilitazione delle politiche, la gestione della duplicazione e la gestione del modulo generale della politica.
- `conorderfee/views/js/checkout.js`
  - **Ambito:** Front-office.
  - **Descrizione:** Questo script probabilmente monitora le modifiche nel carrello durante il processo di checkout (ad esempio, aggiornamenti di quantità, selezione del corriere) e attiva chiamate AJAX per rivalutare le commissioni, garantendo che il totale del carrello sia sempre accurato. Potrebbe anche aggiornare la visualizzazione della voce di commissione.

### 4.5 Fogli di stile CSS (`views/css/`)

- `conorderfee/lib/searchTool/views/css/autocomplete.css`
  - **Ambito:** Back-office (Admin).
  - **Descrizione:** Stili per i campi di input di ricerca con completamento automatico e i loro suggerimenti a discesa.
- `conorderfee/lib/searchTool/views/views/css/autocomplete.css`
  - **Ambito:** Back-office (Admin).
  - **Descrizione:** Duplicato del precedente, probabilmente un errore di percorso o un file legacy.
- `conorderfee/views/css/admin_conorderfee.css`
  - **Ambito:** Back-office (Admin).
  - **Descrizione:** Stile generale per le interfacce di back-office del modulo, inclusi la dashboard, l'elenco delle politiche, il registro di controllo e in particolare il complesso costruttore di condizioni, garantendo un layout coerente e facile da usare.
- `conorderfee/views/css/front.css`
  - **Ambito:** Front-office (Cliente).
  - **Descrizione:** Stile minimale per come la voce di commissione appare nel riepilogo del carrello e nelle pagine di checkout, garantendo che si integri visivamente con il tema del negozio.

### 4.6 Struttura del template Smarty (`views/templates/`)

#### Template hook (`views/templates/hook/`)

- `conorderfee/views/templates/hook/admin_order.tpl`
  - **Hook:** `displayAdminOrder`
  - **Output:** Visualizza le informazioni sulle commissioni condizionali applicate all'interno della vista dell'ordine del Back Office di PrestaShop, consentendo agli amministratori di vedere quali politiche sono state applicate a un ordine specifico.

#### Template Admin (`views/templates/admin/`)

- `conorderfee/lib/searchTool/views/scripts.tpl`
  - **Output:** Include il JavaScript e il CSS necessari per lo strumento di ricerca nel back office.
- `conorderfee/lib/searchTool/views/views/scripts.tpl`
  - **Output:** Duplicato del precedente, probabilmente un errore di percorso o un file legacy.
- `conorderfee/views/templates/admin/auditPreview.tpl`
  - **Output:** Renderizza la vista dettagliata di una singola voce del registro di controllo, mostrando l'intero processo di valutazione delle condizioni.
- `conorderfee/views/templates/admin/dashboard.tpl`
  - **Output:** La vista dashboard principale per il modulo, che visualizza statistiche e collegamenti rapidi.
- `conorderfee/views/templates/admin/helpers/list/list_action_duplicate.tpl`
  - **Output:** Template personalizzato per il pulsante di azione "duplica" nelle viste `HelperList`, specificamente per le politiche.
- `conorderfee/views/templates/admin/policiesPreview.tpl`
  - **Output:** Renderizza un'anteprima o un riepilogo di una politica, potenzialmente utilizzato all'interno del registro di controllo o di un simulatore.
- `conorderfee/views/templates/admin/policyConditionBuilder.tpl`
  - **Output:** La complessa struttura HTML per l'interfaccia interattiva del costruttore di condizioni utilizzata durante la creazione o la modifica di una politica.
- `conorderfee/views/templates/admin/policyRuleCard.tpl`
  - **Output:** Renderizza una singola regola o condizione all'interno del costruttore di condizioni, tipicamente una scheda o un blocco visivo.
- `conorderfee/views/templates/admin/policyRulesTable.tpl`
  - **Output:** Renderizza la tabella delle politiche nella vista elenco `AdminconorderfeePolicies`.
- `conorderfee/views/templates/admin/scopeSelector.tpl`
  - **Output:** Un template per la selezione dell'ambito di una condizione (ad esempio, "Carrello", "Prodotto", "Cliente"), utilizzato all'interno del costruttore di condizioni.

#### Template Front-office (`views/templates/front/`)

- `conorderfee/controllers/front/index.php` (Nessun file .tpl specifico elencato, probabilmente gestisce l'output direttamente o reindirizza)

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

- `ps_conorderfee_policy`: Memorizza le definizioni principali delle politiche di commissione (nome, stato attivo, tipo di commissione, valore, etichetta, priorità).
- `ps_conorderfee_condition_group`: Memorizza la struttura gerarchica dei gruppi di condizioni (logica AND/OR) all'interno di ogni politica.
- `ps_conorderfee_condition`: Memorizza le singole condizioni (tipo, operatore, valore) collegate ai gruppi di condizioni.
- `ps_conorderfee_log`: Memorizza una traccia di controllo di ogni volta che una commissione è stata valutata, inclusi i dettagli del carrello, la politica applicata, l'importo della commissione e un'istantanea del risultato della valutazione.
- `ps_configuration`: Memorizza i valori di configurazione specifici del modulo come `CONORDERFEE_ENABLED` e `CONORDERFEE_FEE_PRODUCT_ID`.

#### Tabella degli hook registrati

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Non esplicitamente elencato nelle informazioni del modulo, ma spesso utilizzato per caricare CSS/JS del front-office. |
| `displayBeforeCarrier` | Prima della selezione del corriere nella pagina di checkout. | Potenzialmente utilizzato per rivalutare le commissioni se la selezione del corriere influisce sulle condizioni. |
| `actionObjectProductInCartDeleteBefore` | Prima che un prodotto venga rimosso dal carrello. | Rivaluta le commissioni per adattarle se il prodotto rimosso faceva parte di una condizione. |
| `actionPresentCart` | Quando i dati del carrello vengono presentati al front office. | **CRITICO:** Hook principale per iniettare la voce di commissione nel riepilogo del carrello. |
| `actionAdminControllerSetMedia` | Quando un controller di amministrazione viene caricato, prima del suo contenuto. | Carica CSS e JavaScript del back-office per le interfacce di amministrazione del modulo. |
| `actionPresentProductListing` | Quando vengono presentati gli elenchi di prodotti. | Non direttamente correlato alle commissioni, ma potrebbe essere utilizzato per indicatori di commissione specifici del prodotto. |
| `actionValidateOrderBefore` | Poco prima che un ordine venga convalidato. | Controllo finale e applicazione delle commissioni per garantire che il totale dell'ordine sia corretto. |
| `actionGetProductPropertiesAfter` | Dopo che le proprietà del prodotto sono state recuperate. | Potenzialmente utilizzato per identificare prodotti specifici che attivano le commissioni. |
| `displayAdminOrder` | Nella pagina dei dettagli dell'ordine del Back Office. | Visualizza le informazioni sulle commissioni applicate per un ordine specifico. |
| `actionFrontControllerInitAfter` | Dopo che un front controller è stato inizializzato. | Inizializzazione generale del front-office, potenzialmente impostando il contesto per la valutazione delle commissioni. |
| `actionPresentProduct` | Quando viene presentato un singolo prodotto. | Simile a `actionPresentProductListing`. |
| `actionPresentCartProduct` | Quando un prodotto nel carrello viene presentato. | Consente la modifica dei dati del prodotto del carrello, potenzialmente per la visualizzazione relativa alle commissioni. |
| `actionProductPriceCalculation` | Durante il calcolo del prezzo del prodotto. | Assicura che il prezzo del prodotto commissione sia correttamente sovrascritto dalla commissione calcolata. |
| `actionFrontControllerSetVariables` | Prima che le variabili Smarty vengano assegnate in un front controller. | Passa i dati relativi alle commissioni ai template del front-office. |
| `actionCartSave` | Dopo che un carrello è stato salvato (ad esempio, cambio quantità, aggiunta/rimozione prodotto). | **CRITICO:** Attiva la logica principale di valutazione delle commissioni ogni volta che il contenuto del carrello cambia. |
| `actionValidateOrder` | Dopo che un ordine è stato convalidato con successo. | Registra l'applicazione finale della commissione e la associa al nuovo ID dell'ordine. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, correzioni di bug e supporto dedicato agli sviluppatori, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Assicurati di scaricare sempre l'ultima versione compatibile con la tua installazione di PrestaShop.
