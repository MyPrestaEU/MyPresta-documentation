---
title: "Servizi d'Ordine Opzionali Condizionali - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Servizi d'Ordine Opzionali Condizionali di MyPresta.eu."
sidebar:
  label: "Servizi d'Ordine Opzionali Condizionali - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Conditional Optional Order Services su MyPresta.eu](https://mypresta.eu/modules/ordering-process/conditional-optional-order-services.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/conditional-optional-order-services/)
>
> ---


# Servizi d'Ordine Opzionali Condizionali

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Sono richieste estensioni PHP standard (cURL, JSON, OpenSSL), che sono tipicamente disponibili sulla maggior parte degli ambienti di hosting moderni.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

Il modulo "Servizi d'Ordine Opzionali Condizionali" offre un potente set di strumenti per gestire i tuoi servizi opzionali. Interagirai principalmente con il modulo tramite le sue voci di menu dedicate nel tuo Back Office di PrestaShop.

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata iniziale che vedi dopo aver installato il modulo o aver cliccato su "Configura" dal Gestore moduli. Fornisce un modo rapido per abilitare o disabilitare la funzionalità principale del modulo.

- **Nome impostazione:** Abilita Servizi d'Ordine Opzionali Condizionali
- **Cosa fa questa impostazione:** Questo è l'interruttore principale per l'intero modulo. Quando abilitato, la logica del modulo verrà eseguita e i tuoi servizi definiti verranno offerti ai clienti in base alle tue politiche. Quando disabilitato, nessun servizio verrà offerto e il modulo sarà effettivamente inattivo sul tuo front-office.
- **Effetto della modifica di questa impostazione:**
  - *Quando abilitato:* Il modulo inizierà a valutare le tue politiche di servizio e a visualizzare i servizi pertinenti ai clienti nel front-office (ad esempio, la pagina di checkout).
  - *Quando disabilitato:* Tutti i servizi condizionali saranno nascosti ai clienti e la logica del modulo non verrà eseguita.
- **Valore consigliato:** **SÌ** (Abilitato) una volta configurate le tue politiche.
- **Scenario / esempio del commerciante:** Hai appena installato il modulo e sei pronto per iniziare a definire i tuoi servizi. Abiliteresti questa impostazione per rendere i tuoi servizi visibili ai clienti una volta configurati. Se hai bisogno di interrompere temporaneamente l'offerta di tutti i servizi (ad esempio, durante la manutenzione o un periodo di vacanza), puoi disabilitarlo rapidamente qui senza eliminare le tue politiche.

### 2.2 Schermate di amministrazione dedicate e viste del controller

Dopo la configurazione iniziale, troverai nuove voci di menu sotto **Vendi > Servizi d'Ordine** (o una posizione simile, a seconda della tua versione e tema di PrestaShop).

#### 2.2.1 Politiche (Back Office > Vendi > Servizi d'Ordine > Politiche)

Qui è dove definisci e gestisci tutti i tuoi servizi d'ordine opzionali condizionali. Ogni "Politica" rappresenta un servizio specifico che desideri offrire, insieme alle regole che determinano quando e a chi viene offerto.

- **Nome schermata e posizione menu:** Politiche (Sotto **Vendi > Servizi d'Ordine** nel menu principale di PrestaShop).
- **Azioni e impostazioni disponibili:**

  - **Elenco politiche:** Una tabella che mostra tutte le politiche create, il loro nome, stato (attivo/inattivo) e altre informazioni chiave.
  - **Aggiungi nuova politica:** Clicca su questo pulsante per creare un nuovo servizio opzionale.
  - **Modifica politica:** Clicca sull'icona "Modifica" accanto a una politica esistente per modificarne i dettagli, le condizioni e le regole.
  - **Duplica politica:** Una funzione molto utile! Clicca sull'icona "Duplica" per creare una copia esatta di una politica esistente. Questo ti fa risparmiare tempo se devi creare servizi simili.
  - **Elimina politica:** Rimuovi una politica in modo permanente.
  - **Azioni di massa:** Seleziona più politiche ed esegui azioni come "Abilita", "Disabilita" o "Elimina" contemporaneamente.
- **Quando aggiungi/modifica una Politica, configurerai:**

  - **Informazioni generali:**
    - **Nome:** Un nome interno chiaro per la tua politica (ad esempio, "Servizio Confezione Regalo", "Assicurazione Spedizione Express").
    - **Stato:** Abilita o disabilita questa politica specifica. Una politica inattiva non verrà mai mostrata ai clienti.
    - **Descrizione:** Il testo che i clienti vedranno per spiegare il servizio. Sii conciso ed evidenzia i vantaggi.
    - **Prezzo:** Il costo di questo servizio opzionale. Questo verrà aggiunto al carrello del cliente se selezionato.
    - **Regola fiscale:** Seleziona la regola fiscale applicabile per questo servizio (ad esempio, "Aliquota standard", "Aliquota ridotta").
    - **Immagine/Icona:** Carica un'immagine o un'icona per rappresentare visivamente il servizio ai clienti. Questo lo rende più accattivante e facile da identificare.
  - **Condizioni:** Questo è il cuore della potenza del modulo. Qui costruisci regole utilizzando un costruttore di condizioni visivo per determinare *quando* questo servizio dovrebbe essere offerto.
    - Puoi combinare più condizioni usando la logica "AND" o "OR".
    - **Esempi di condizioni:**
      - **Valore del carrello:** Offri il servizio solo se il totale del carrello è superiore/inferiore a un certo importo.
      - **Prodotto nel carrello:** Offri il servizio solo se prodotti specifici o prodotti di determinate categorie/produttori sono nel carrello.
      - **Gruppo clienti:** Offri il servizio solo a gruppi di clienti specifici (ad esempio, "Grossisti", "Clienti VIP").
      - **Corriere di spedizione:** Offri il servizio solo se è selezionato un corriere di spedizione specifico.
      - **Intervallo di date:** Offri il servizio solo durante un periodo promozionale specifico.
      - **Paese/Zona:** Offri il servizio solo ai clienti di determinati paesi o zone di spedizione.
  - **Impostazioni di visualizzazione:** Controlla come il servizio appare nel front-office.
    - **Posizione:** Se vengono offerti più servizi, puoi impostare il loro ordine di visualizzazione.
    - **Visibilità:** Dove esattamente nel processo di checkout appare il servizio.
- **Effetto delle modifiche:**

  - L'aggiunta di una nuova politica rende un nuovo servizio opzionale disponibile per la visualizzazione ai clienti, soggetto alle sue condizioni.
  - La modifica di una politica cambia il suo nome, prezzo, descrizione, immagine o le condizioni in base alle quali viene offerta. Queste modifiche si riflettono immediatamente nel front-office.
  - L'abilitazione/disabilitazione di una politica controlla la sua visibilità ai clienti.
  - L'eliminazione di una politica la rimuove completamente e non verrà più offerta.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

  1. Inizia definendo i tuoi servizi più comuni (ad esempio, confezione regalo, assicurazione).
  2. Usa il costruttore di condizioni per rendere questi servizi altamente pertinenti. Ad esempio, la confezione regalo potrebbe essere offerta solo per prodotti fisici, non per download digitali.
  3. Rivedi regolarmente le tue politiche, specialmente prima di promozioni o saldi stagionali, per assicurarti che siano attive e configurate correttamente.
  4. Utilizza la funzione "Duplica" per creare rapidamente varianti di servizi esistenti (ad esempio, "Confezione Regalo Premium" vs. "Confezione Regalo Standard").

#### 2.2.2 Registro di controllo (Back Office > Vendi > Servizi d'Ordine > Registro di controllo)

Questa schermata fornisce una cronologia dettagliata di tutte le azioni relative alle politiche e ai servizi del modulo. È uno strumento prezioso per tenere traccia delle modifiche e risolvere i problemi.

- **Nome schermata e posizione menu:** Registro di controllo (Sotto **Vendi > Servizi d'Ordine** nel menu principale di PrestaShop).
- **Azioni e impostazioni disponibili:**
  - **Elenco log:** Una tabella che mostra un elenco cronologico di eventi.
  - **Le colonne tipicamente includono:**
    - **Data:** Quando si è verificato l'evento.
    - **Dipendente:** Quale utente del Back Office ha eseguito l'azione.
    - **Azione:** Quale azione è stata intrapresa (ad esempio, "Politica aggiunta", "Politica modificata", "Politica eliminata", "Modulo abilitato/disabilitato").
    - **Dettagli:** Informazioni specifiche sulla modifica (ad esempio, quale politica è stata interessata, quali valori sono stati modificati).
  - **Filtro/Ricerca:** Strumenti per filtrare il log per data, dipendente o tipo di azione per trovare eventi specifici.
- **Effetto delle modifiche:** Questa schermata è solo per la visualizzazione; non puoi apportare modifiche dirette qui. Serve come registro di tutte le modifiche apportate alla configurazione e alle politiche del modulo.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  - Utilizza il registro di controllo per tenere traccia di chi ha apportato modifiche alle tue politiche di servizio, specialmente in ambienti multiutente.
  - Se un servizio non appare come previsto, controlla il registro di controllo per vedere se una politica è stata accidentalmente disabilitata o modificata.
  - Monitora eventuali comportamenti inaspettati del modulo registrati nei log.

#### 2.2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Configurazione modulo** | Abilita Servizi d'Ordine Opzionali Condizionali | SÌ (dopo la configurazione) | Interruttore principale per la funzionalità front-office del modulo. |
| **Politiche (Elenco)** | Aggiungi nuova politica | N/A | Crea un nuovo servizio opzionale con le proprie regole e prezzi. |
| **Politiche (Elenco)** | Modifica politica | N/A | Modifica i dettagli, le condizioni o la visualizzazione di un servizio esistente. |
| **Politiche (Elenco)** | Duplica politica | N/A | Crea rapidamente una copia di una politica esistente per risparmiare tempo. |
| **Politiche (Elenco)** | Elimina politica | N/A | Rimuovi permanentemente un servizio opzionale. |
| **Politiche (Modulo di modifica)** | Nome | Nome descrittivo | Identificatore interno per il servizio. |
| **Politiche (Modulo di modifica)** | Stato | Abilitato | Controlla se questo servizio specifico è attivo e visibile ai clienti. |
| **Politiche (Modulo di modifica)** | Descrizione | Spiegazione chiara | Testo visualizzato ai clienti sul servizio. |
| **Politiche (Modulo di modifica)** | Prezzo | 0.00 (imposta valore) | Costo aggiunto al carrello se il servizio è selezionato. |
| **Politiche (Modulo di modifica)** | Regola fiscale | Regola fiscale predefinita | Imposta la tassa applicabile per il servizio. |
| **Politiche (Modulo di modifica)** | Immagine/Icona | Immagine caricata | Rappresentazione visiva del servizio per i clienti. |
| **Politiche (Modulo di modifica)** | Condizioni (Costruttore) | Regole personalizzate | Definisce *quando* e *a chi* viene offerto il servizio (ad esempio, valore del carrello, prodotto nel carrello, gruppo clienti). |
| **Politiche (Modulo di modifica)** | Posizione | Auto (imposta valore) | Ordine di visualizzazione se vengono offerti più servizi. |
| **Registro di controllo** | (Tutte le voci) | N/A | Fornisce un registro storico di tutte le modifiche apportate alle impostazioni e alle politiche del modulo. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei servizi opzionali non vengono visualizzati nella pagina di checkout. Cosa devo controllare?**
R1:

1.  **Modulo abilitato?** Vai su **Moduli > Gestione moduli**, trova "Servizi d'Ordine Opzionali Condizionali" e assicurati che sia abilitato.
2.  **Stato della politica?** Vai su **Vendi > Servizi d'Ordine > Politiche**. Assicurati che la politica specifica che ti aspetti di vedere sia "Attiva".
3.  **Condizioni della politica soddisfatte?** Questa è la ragione più comune. Rivedi attentamente le condizioni che hai impostato per la politica. Il tuo carrello di prova attuale soddisfa *tutte* le condizioni "AND" e *una qualsiasi* delle condizioni "OR"? Ad esempio, se hai impostato "Totale carrello > 50 €" e il tuo carrello è di 45 €, il servizio non verrà visualizzato.
4.  **Cache?** Svuota la cache di PrestaShop in **Parametri avanzati > Prestazioni**. A volte, i dati della cache obsoleti possono impedire la visualizzazione delle nuove configurazioni del modulo.
5.  **Compatibilità del tema?** Sebbene il modulo sia progettato per un'ampia compatibilità, temi molto personalizzati potrebbero richiedere piccole modifiche. Controlla la console per sviluppatori del tuo browser per errori JavaScript.

**D2: Il prezzo del mio servizio non viene aggiunto correttamente al totale del carrello.**
R2:

1.  **Prezzo della politica impostato?** Ricontrolla il campo "Prezzo" nella configurazione della tua politica.
2.  **Regola fiscale applicata?** Assicurati che la "Regola fiscale" corretta sia selezionata per il servizio. Il prezzo finale include le tasse in base a questa regola.
3.  **Valuta?** Verifica che il prezzo sia impostato nella valuta predefinita del tuo negozio o che le impostazioni multi-valuta siano gestite correttamente da PrestaShop.

**D3: Come posso tradurre i nomi e le descrizioni dei servizi in altre lingue?**
R3:

1.  Vai su **Internazionale > Traduzioni** nel tuo Back Office di PrestaShop.
2.  Seleziona "Traduzioni dei moduli installati", scegli il tuo tema e poi seleziona la tua lingua.
3.  Trova il modulo "Servizi d'Ordine Opzionali Condizionali". Dovresti essere in grado di tradurre i nomi e le descrizioni delle tue politiche direttamente all'interno dei moduli di configurazione del modulo, poiché sono solitamente memorizzati come campi traducibili. In caso contrario, appariranno qui.

**D4: Posso cambiare l'ordine in cui i servizi appaiono nella pagina di checkout?**
R4: Sì, all'interno della configurazione di ogni politica, dovrebbe esserci un'impostazione "Posizione". Puoi impostare un valore numerico (ad esempio, 10, 20, 30) per controllare l'ordine di visualizzazione. I numeri più bassi appaiono per primi.

**D5: Il modulo sta causando un problema visivo o un conflitto con un altro modulo.**
R5:

1.  **Isola il problema:** Disabilita temporaneamente altri moduli installati o aggiornati di recente per vedere se il conflitto scompare.
2.  **Cerca errori:** Usa la console per sviluppatori del tuo browser (F12) per cercare errori JavaScript o CSS.
3.  **Contatta il supporto:** Se non riesci a risolverlo, fornisci al supporto MyPresta.eu i dettagli del problema, la tua versione di PrestaShop e qualsiasi altro modulo che sospetti possa essere in conflitto.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce un'analisi approfondita della struttura tecnica del modulo "Servizi d'Ordine Opzionali Condizionali", destinata a sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo segue un robusto modello MVC (Model-View-Controller) tipico dei moduli PrestaShop. Si basa fortemente sul sistema di hook di PrestaShop per iniettare la sua funzionalità in vari punti del front-office (checkout, pagina prodotto) e del back-office (vista ordini admin, configurazione modulo).
I componenti architettonici chiave includono:

- **Politiche (`conorderservicesPolicy`):** L'entità principale che rappresenta un servizio opzionale, che estende `ObjectModel`.
- **Condizioni (`conorderservicesCondition`, `conorderservicesConditionGroup`, `conorderservicesConditionTree`):** Un sistema sofisticato per la costruzione di regole complesse per determinare l'idoneità del servizio.
- **Motore (`conorderservicesEngine`):** La classe centrale responsabile della valutazione delle condizioni e della determinazione dei servizi da presentare al cliente.
- **Registro di controllo (`conorderservicesAuditLog`):** Registra tutte le azioni significative all'interno del modulo per la tracciabilità.
- **Livello di compatibilità (`conorderservicesCompatibility`):** Gestisce le differenze tra PrestaShop 1.7, 8 e 9.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

- `conorderservices/controllers/front/ajax.php`
  - **Nome classe:** `ConorderservicesAjaxModuleFrontController` (estende `ModuleFrontController`)
  - **Responsabilità:** Gestisce le richieste AJAX dal front-office, principalmente per aggiornare dinamicamente le selezioni di servizio o ricalcolare i totali del carrello quando un servizio viene aggiunto/rimosso dal cliente. Probabilmente invia al `conorderservicesEngine` per eseguire i calcoli e restituisce risposte JSON.
- `conorderservices/controllers/front/index.php`
  - **Nome classe:** `ConorderservicesIndexModuleFrontController` (estende `ModuleFrontController`)
  - **Responsabilità:** Un controller segnaposto o di fallback. Spesso utilizzato per l'accesso diretto al modulo, se necessario, sebbene la maggior parte dell'interazione front-office avvenga tramite hook o AJAX.

#### Controller Admin Back-Office

- `conorderservices/controllers/admin/AdminconorderservicesAuditLog.php`
  - **Nome classe:** `AdminconorderservicesAuditLogController` (estende `ModuleAdminController`)
  - **Nome scheda:** Registro di controllo (sotto "Vendi > Servizi d'Ordine")
  - **Entità gestita:** `conorderservicesAuditLog`
  - **Responsabilità:** Gestisce la visualizzazione e il filtraggio delle voci del registro di controllo. Utilizza `HelperList` di PrestaShop per renderizzare la tabella del log.
- `conorderservices/controllers/admin/AdminconorderservicesPolicies.php`
  - **Nome classe:** `AdminconorderservicesPoliciesController` (estende `ModuleAdminController`)
  - **Nome scheda:** Politiche (sotto "Vendi > Servizi d'Ordine")
  - **Entità gestita:** `conorderservicesPolicy`
  - **Responsabilità:** Il controller principale per la gestione delle politiche dei servizi opzionali. Gestisce l'elenco, l'aggiunta, la modifica, la duplicazione e l'eliminazione degli oggetti `conorderservicesPolicy`. Utilizza `HelperList` per l'elenco delle politiche e `HelperForm` per i moduli di aggiunta/modifica delle politiche, incluso il complesso costruttore di condizioni.
- `conorderservices/controllers/admin/index.php`
  - **Nome classe:** `AdminconorderservicesIndexController` (estende `ModuleAdminController`)
  - **Nome scheda:** (Probabilmente il punto di ingresso principale "Servizi d'Ordine")
  - **Entità gestita:** Nessuna direttamente, spesso reindirizza a `AdminconorderservicesPolicies` o visualizza una dashboard.
  - **Responsabilità:** Serve come punto di ingresso principale per la sezione amministrativa del modulo, potenzialmente visualizzando una dashboard o reindirizzando all'elenco delle politiche.

### 4.3 Classi e modelli principali (`classes/`)

- `conorderservices/classes/conorderservicesAdmin.php`
  - **Scopo:** Classe utility per funzioni specifiche dell'amministrazione, potenzialmente gestione dei permessi, generazione di menu o attività amministrative comuni.
- `conorderservices/classes/conorderservicesAuditLog.php`
  - **Estende:** `ObjectModel`
  - **Tabella database:** `ps_conorderservices_log`
  - **Campi `$definition`:** `id_conorderservices_log`, `id_employee`, `action`, `details`, `date_add`
  - **Scopo:** Rappresenta una voce nel registro di controllo del modulo. Fornisce metodi per aggiungere nuove voci di log.
- `conorderservices/classes/conorderservicesCartState.php`
  - **Scopo:** Gestisce e persiste lo stato dei servizi opzionali selezionati all'interno del carrello del cliente. Probabilmente interagisce con `Context::getContext()->cart` e memorizza le selezioni di servizio.
- `conorderservices/classes/conorderservicesCompatibility.php`
  - **Scopo:** Fornisce un livello di astrazione per funzioni o comportamenti specifici della versione di PrestaShop, garantendo che il modulo funzioni su 1.7, 8 e 9.
- `conorderservices/classes/conorderservicesCondition.php`
  - **Estende:** `ObjectModel` (probabilmente, o una classe base per le condizioni)
  - **Tabella database:** `ps_conorderservices_condition`
  - **Campi `$definition`:** `id_conorderservices_condition`, `id_conorderservices_condition_group`, `type`, `operator`, `value`
  - **Scopo:** Rappresenta una singola condizione all'interno di un gruppo di condizioni (ad esempio, "Totale carrello" "è maggiore di" "100").
- `conorderservices/classes/conorderservicesConditionEvaluator.php`
  - **Scopo:** Il motore logico per valutare un set di condizioni rispetto al carrello, al cliente e al contesto del prodotto attuali. Determina se le condizioni di una politica sono soddisfatte.
- `conorderservices/classes/conorderservicesConditionGroup.php`
  - **Estende:** `ObjectModel` (probabilmente)
  - **Tabella database:** `ps_conorderservices_condition_group`
  - **Campi `$definition`:** `id_conorderservices_condition_group`, `id_conorderservices_policy`, `logic_operator` (AND/OR)
  - **Scopo:** Raggruppa più oggetti `conorderservicesCondition` insieme, definendo la relazione logica tra di essi (AND/OR).
- `conorderservices/classes/conorderservicesConditionTree.php`
  - **Scopo:** Gestisce la struttura gerarchica dei gruppi di condizioni e delle singole condizioni, consentendo la costruzione di regole complesse.
- `conorderservices/classes/conorderservicesContext.php`
  - **Scopo:** Un wrapper o un'estensione della classe `Context` di PrestaShop, che fornisce dati di contesto specifici del modulo (ad esempio, carrello corrente, cliente, lingua) per la valutazione delle condizioni.
- `conorderservices/classes/conorderservicesDashboard.php`
  - **Scopo:** Fornisce dati e logica per la vista dashboard del modulo (se presente), potenzialmente mostrando analisi o statistiche rapide.
- `conorderservices/classes/conorderservicesEngine.php`
  - **Scopo:** L'unità di elaborazione centrale del modulo. Recupera le politiche attive, le passa al `ConditionEvaluator` e determina quali servizi sono idonei per il carrello corrente. Gestisce anche l'aggiunta/rimozione di prodotti di servizio dal carrello.
- `conorderservices/classes/conorderservicesListRenderer.php`
  - **Scopo:** Classe helper per il rendering di elenchi nel Back Office, potenzialmente estendendo `HelperList` o fornendo una logica di rendering personalizzata.
- `conorderservices/classes/conorderservicesLog.php`
  - **Scopo:** Alias o implementazione specifica per la registrazione, possibilmente distinta da `conorderservicesAuditLog` per diversi tipi di registrazione.
- `conorderservices/classes/conorderservicesPolicy.php`
  - **Estende:** `ObjectModel`
  - **Tabella database:** `ps_conorderservices_policy`
  - **Campi `$definition`:** `id_conorderservices_policy`, `name`, `description`, `price`, `id_tax_rule`, `image`, `active`, `position`, `date_add`, `date_upd` (e campi `_lang` per `name`, `description` traducibili).
  - **Scopo:** Il modello principale per un servizio opzionale. Memorizza tutta la configurazione per un servizio, inclusi i suoi dettagli, prezzo, immagine e gruppi di condizioni associati.
- `conorderservices/classes/conorderservicesPolicyDuplicator.php`
  - **Scopo:** Gestisce la logica per la duplicazione di un'intera politica, incluse le sue condizioni e i dati associati.
- `conorderservices/classes/conorderservicesPreset.php`
  - **Scopo:** Probabilmente fornisce set predefiniti di condizioni o politiche che possono essere rapidamente caricati dal commerciante.
- `conorderservices/classes/conorderservicesRule.php`
  - **Scopo:** Un termine più generico per una condizione o un set di condizioni. Potrebbe essere una classe base astratta o un tipo specifico di regola.
- `conorderservices/classes/ConorderservicesRuleImage.php`
  - **Scopo:** Gestisce le immagini/icone associate a politiche o regole.
- `conorderservices/classes/ConorderservicesServiceProduct.php`
  - **Estende:** `Product` (o un wrapper attorno ad esso)
  - **Scopo:** Rappresenta il "prodotto virtuale" che viene aggiunto al carrello quando un cliente seleziona un servizio opzionale. Assicura che il servizio si comporti come un prodotto normale per l'elaborazione del carrello e dell'ordine.
- `conorderservices/classes/conorderservicesTreeRepository.php`
  - **Scopo:** Gestisce l'archiviazione e il recupero della struttura dell'albero delle condizioni.
- `conorderservices/classes/index.php`
  - **Scopo:** File vuoto standard per impedire l'elenco delle directory.
- `conorderservices/classes/load.php`
  - **Scopo:** File di caricamento automatico o un file che include altre definizioni di classe.

### 4.4 Risorse JavaScript (`views/js/`)

- `conorderservices/lib/searchTool/views/js/autocomplete.js`
  - **Ambito:** Back-office (per la selezione di prodotti/categorie nel costruttore di condizioni)
  - **Dettagli:** Fornisce la funzionalità di completamento automatico per i campi di input, probabilmente utilizzata quando si selezionano prodotti, categorie o produttori all'interno del costruttore di condizioni.
- `conorderservices/lib/searchTool/views/views/js/autocomplete.js`
  - **Ambito:** Back-office (ridondante o specifico per una diversa vista dello strumento di ricerca)
  - **Dettagli:** Simile a quanto sopra, probabilmente un duplicato o una versione specifica dello script di completamento automatico.
- `conorderservices/views/js/adminConditionBuilder.js`
  - **Ambito:** Back-office (AdminconorderservicesPoliciesController)
  - **Dettagli:** JS principale per il costruttore di condizioni visivo. Gestisce l'aggiunta/rimozione di condizioni e gruppi di condizioni, la gestione degli operatori logici (AND/OR) e l'aggiornamento dell'interfaccia utente in base all'input dell'utente.
- `conorderservices/views/js/adminconorderservicesDashboard.js`
  - **Ambito:** Back-office (AdminconorderservicesIndexController o vista Dashboard)
  - **Dettagli:** Script per elementi interattivi sulla dashboard del modulo, come grafici, statistiche o collegamenti rapidi.
- `conorderservices/views/js/adminconorderservicesSearchTool.js`
  - **Ambito:** Back-office (AdminconorderservicesPoliciesController)
  - **Dettagli:** Integra lo strumento di ricerca (completamento automatico) con il costruttore di condizioni, consentendo agli amministratori di trovare e selezionare facilmente entità (prodotti, categorie, ecc.) per le condizioni.
- `conorderservices/views/js/adminconorderservicesSimulator.js`
  - **Ambito:** Back-office (AdminconorderservicesPoliciesController - probabilmente una scheda o un modale dedicato)
  - **Dettagli:** Fornisce funzionalità per un simulatore di politiche, consentendo agli amministratori di testare le condizioni con dati di carrello fittizi per vedere quali servizi verrebbero offerti.
- `conorderservices/views/js/adminPolicyRuleImage.js`
  - **Ambito:** Back-office (AdminconorderservicesPoliciesController)
  - **Dettagli:** Gestisce la funzionalità di caricamento e anteprima delle immagini per le icone/immagini delle politiche.
- `conorderservices/views/js/adminPolicyRules.js`
  - **Ambito:** Back-office (AdminconorderservicesPoliciesController)
  - **Dettagli:** Script generali per la gestione delle regole delle politiche, potenzialmente inclusi il riordino tramite drag-and-drop o altre interazioni dell'interfaccia utente nella pagina di modifica della politica.
- `conorderservices/views/js/adminSettingsOfferDisplay.js`
  - **Ambito:** Back-office (Configurazione principale del modulo o Modifica politica)
  - **Dettagli:** Script relativi alla configurazione di come e dove i servizi opzionali vengono visualizzati nel front-office.
- `conorderservices/views/js/checkout.js`
  - **Ambito:** Front-office (pagina di checkout)
  - **Dettagli:** Questo è lo script critico del front-office. Ascolta le interazioni dell'utente (ad esempio, selezionando/deselezionando un servizio), invia richieste AJAX a `ajax.php` per aggiornare il carrello e aggiorna dinamicamente il riepilogo e il totale del carrello nella pagina di checkout. Probabilmente si lega agli eventi `prestashop.on` per gli aggiornamenti del carrello.

### 4.5 Fogli di stile CSS (`views/css/`)

- `conorderservices/lib/searchTool/views/css/autocomplete.css`
  - **Ambito:** Back-office
  - **Dettagli:** Stili per i menu a discesa di completamento automatico e i campi di input utilizzati nello strumento di ricerca dell'amministrazione.
- `conorderservices/lib/searchTool/views/views/css/autocomplete.css`
  - **Ambito:** Back-office (ridondante o specifico per una diversa vista dello strumento di ricerca)
  - **Dettagli:** Simile a quanto sopra, probabilmente un duplicato o una versione specifica degli stili di completamento automatico.
- `conorderservices/views/css/admin_conorderservices.css`
  - **Ambito:** Back-office
  - **Dettagli:** Stili generali per le pagine di amministrazione del modulo, inclusi l'elenco delle politiche, il costruttore di condizioni e il registro di controllo. Contiene stili per elementi di modulo, tabelle e componenti UI personalizzati.
- `conorderservices/views/css/front.css`
  - **Ambito:** Front-office
  - **Dettagli:** Stili per come i servizi opzionali vengono visualizzati nella pagina di checkout. Include stili per il blocco del servizio, le singole righe del servizio, le caselle di controllo, i prezzi e le icone. Gli sviluppatori possono sovrascrivere queste classi nel `custom.css` o `theme.css` del loro tema.

### 4.6 Struttura del template Smarty (`views/templates/`)

#### Template hook (`views/templates/hook/`)

- `conorderservices/views/templates/hook/admin_order.tpl`
  - **Hook:** `displayAdminOrder`
  - **Output:** Visualizza informazioni sui servizi opzionali selezionati all'interno della vista degli ordini del Back Office di PrestaShop. Ciò consente agli amministratori di vedere quali servizi sono stati acquistati con un ordine.
- `conorderservices/views/templates/hook/checkout_services.tpl`
  - **Hook:** `displayShoppingCart`, `displayShoppingCartFooter` (o hook di checkout simili)
  - **Output:** Il template principale per il rendering dell'elenco dei servizi opzionali disponibili nella pagina di checkout del front-office. Itera attraverso le politiche idonee e le visualizza.
- `conorderservices/views/templates/hook/partials/checkout_offer_row.tpl`
  - **Hook:** Incluso da `checkout_services.tpl`
  - **Output:** Renderizza una singola riga o scheda per un servizio opzionale all'interno dell'elenco di checkout, inclusi il suo nome, descrizione, prezzo e input di selezione (ad esempio, casella di controllo).

#### Template admin (`views/templates/admin/`)

- `conorderservices/views/templates/admin/auditPreview.tpl`
  - **Scopo:** Renderizza una vista dettagliata o un'anteprima di una voce del registro di controllo.
- `conorderservices/views/templates/admin/dashboard.tpl`
  - **Scopo:** Il template principale per la dashboard del modulo nel Back Office, che potenzialmente visualizza analisi o informazioni di riepilogo.
- `conorderservices/views/templates/admin/helpers/list/list_action_duplicate.tpl`
  - **Scopo:** Template personalizzato per il pulsante di azione "Duplica" nelle viste `HelperList` (specificamente per le politiche).
- `conorderservices/views/templates/admin/policiesPreview.tpl`
  - **Scopo:** Renderizza un'anteprima di una politica, potenzialmente utilizzata in un simulatore o in una vista rapida.
- `conorderservices/views/templates/admin/policyConditionBuilder.tpl`
  - **Scopo:** Il template per l'interfaccia del costruttore di condizioni visivo all'interno del modulo di modifica della politica. Questo è un template complesso che aggiunge/rimuove dinamicamente gruppi di condizioni e singole condizioni.
- `conorderservices/views/templates/admin/policyRuleCard.tpl`
  - **Scopo:** Renderizza una singola regola o gruppo di condizioni come una scheda all'interno del costruttore di condizioni, rendendola visivamente distinta.
- `conorderservices/views/templates/admin/policyRulesTable.tpl`
  - **Scopo:** Renderizza una struttura simile a una tabella per la visualizzazione delle regole, possibilmente un'alternativa o un componente all'interno del costruttore di condizioni.
- `conorderservices/views/templates/admin/scopeSelector.tpl`
  - **Scopo:** Template per la selezione dell'ambito di una condizione (ad esempio, prodotto, categoria, cliente).

#### Template di libreria (`conorderservices/lib/searchTool/views/`)

- `conorderservices/lib/searchTool/views/helpers.tpl`
  - **Scopo:** Template helper per lo strumento di ricerca, possibilmente per il rendering dei risultati di ricerca o dei campi di input.
- `conorderservices/lib/searchTool/views/scripts.tpl`
  - **Scopo:** Include JavaScript per lo strumento di ricerca.
- `conorderservices/lib/searchTool/views/views/scripts.tpl`
  - **Scopo:** Duplicato o versione specifica degli script dello strumento di ricerca.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

- `ps_conorderservices_policy`
  - Memorizza le informazioni principali della politica: `id_conorderservices_policy`, `name`, `description`, `price`, `id_tax_rule`, `image`, `active`, `position`, `date_add`, `date_upd`.
  - Include anche campi specifici per la lingua per `name` e `description` (ad esempio, `ps_conorderservices_policy_lang`).
- `ps_conorderservices_condition_group`
  - Memorizza i gruppi di condizioni: `id_conorderservices_condition_group`, `id_conorderservices_policy`, `logic_operator` (AND/OR).
- `ps_conorderservices_condition`
  - Memorizza le singole condizioni: `id_conorderservices_condition`, `id_conorderservices_condition_group`, `type`, `operator`, `value`.
- `ps_conorderservices_log`
  - Memorizza le voci del registro di controllo: `id_conorderservices_log`, `id_employee`, `action`, `details`, `date_add`.
- `ps_conorderservices_cart_state` (probabilmente)
  - Memorizza quali servizi sono selezionati per un dato carrello: `id_cart`, `id_conorderservices_policy`, `date_add`.
- `ps_configuration`
  - `CONORDERSERVICES_ENABLED`: Memorizza lo stato di abilitazione/disabilitazione principale del modulo.
  - `PS_CURRENCY_DEFAULT`: Utilizzato per visualizzare i prezzi nell'amministrazione.

#### Tabella degli hook registrati

| Nome hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `ActionObjectProductInCartDeleteBefore` | Prima che un prodotto venga eliminato dal carrello. | Assicura che se un prodotto richiesto per un servizio viene rimosso, anche il servizio venga rimosso o rivalutato. |
| `actionPresentCart` | Quando i dati del carrello vengono presentati (ad esempio, nella pagina di checkout). | Inietta l'elenco dei servizi opzionali idonei nei dati di presentazione del carrello. |
| `ActionAdminControllerSetMedia` | Quando un controller admin viene caricato e i suoi media (JS/CSS) vengono impostati. | Inietta JS e CSS specifici del modulo per le pagine del Back Office (politiche, registro di controllo, costruttore di condizioni). |
| `ActionPresentProductListing` | Quando i dati del prodotto vengono presentati in un elenco (ad esempio, pagina di categoria). | Potenzialmente utilizzato per visualizzare indicatori di disponibilità del servizio negli elenchi di prodotti. |
| `ActionValidateOrderBefore` | Prima che un ordine venga convalidato. | Esegue controlli finali sui servizi selezionati, assicura che siano ancora validi e li aggiunge come dettagli dell'ordine. |
| `ActionGetProductPropertiesAfter` | Dopo che le proprietà del prodotto sono state recuperate. | Potenzialmente modifica le proprietà del prodotto se un servizio le influenza (ad esempio, aggiungendo un prodotto virtuale per il servizio). |
| `DisplayAdminOrder` | Nella pagina dei dettagli dell'ordine del Back Office. | Visualizza i servizi opzionali selezionati associati all'ordine. |
| `ActionFrontControllerInitAfter` | Dopo l'inizializzazione di un controller front. | Inizializza il contesto o la logica front-office specifici del modulo. |
| `ActionPresentProduct` | Quando i dati di un singolo prodotto vengono presentati (ad esempio, pagina del prodotto). | Potenzialmente utilizzato per visualizzare indicatori di disponibilità del servizio nelle pagine dei prodotti. |
| `ActionPresentCartProduct` | Quando un prodotto nel carrello viene presentato. | Modifica la presentazione dei prodotti del carrello se i servizi sono ad essi allegati. |
| `ActionProductPriceCalculation` | Durante il calcolo del prezzo del prodotto. | Assicura che i prezzi dei servizi siano correttamente inclusi nel totale. |
| `DisplayShoppingCart` | Nella pagina del carrello. | Visualizza il blocco dei servizi opzionali. |
| `DisplayShoppingCartFooter` | Nel piè di pagina della pagina del carrello. | Posizionamento alternativo o aggiuntivo per il blocco dei servizi opzionali. |
| `ActionCartSave` | Dopo il salvataggio di un carrello. | Persiste lo stato dei servizi opzionali selezionati nel carrello. |
| `ActionValidateOrder` | Dopo che un ordine è stato convalidato. | Finalizza l'ordine con i servizi selezionati, potenzialmente aggiornando l'inventario o attivando azioni di follow-up. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Servizi d'Ordine Opzionali Condizionali", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda riguardante la funzionalità e la compatibilità del modulo.
