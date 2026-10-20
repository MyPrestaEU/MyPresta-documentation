---
title: "Regole Condizionali Metodi di Pagamento - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Regole Condizionali Metodi di Pagamento di MyPresta.eu."
sidebar:
  label: "Regole Condizionali Metodi di Pagamento - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Conditional Payment Method Rules su MyPresta.eu](https://mypresta.eu/modules/payment-process/conditional-payment-method-rules.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/payment/conditional-payment-method-rules/)
>
> ---


# Regole Condizionali Metodi di Pagamento

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

La configurazione del modulo è gestita principalmente tramite schermate di amministrazione dedicate, che ti consentono di creare e gestire le tue politiche sui metodi di pagamento.

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questo è il punto di ingresso principale per il modulo. Dopo l'installazione, cliccando su "Configura" verrai indirizzato a una dashboard o a una pagina di impostazioni generali.

#### Impostazioni generali e Dashboard

Questa schermata fornisce una panoramica dello stato del tuo modulo e un accesso rapido alle funzionalità chiave.

-   **Cosa fa questa schermata:** Visualizza un riepilogo delle tue politiche attive, delle voci recenti del registro di controllo e dei collegamenti rapidi per gestire le politiche o visualizzare il registro di controllo. È il tuo hub centrale per monitorare l'attività del modulo.
-   **Effetto della modifica delle impostazioni:** Questa schermata fornisce principalmente informazioni e navigazione. Qualsiasi modifica apportata qui (es. abilitazione/disabilitazione di una politica) avrà un impatto diretto su come i metodi di pagamento vengono visualizzati al checkout.
-   **Valore consigliato:** Tieni d'occhio la dashboard per eventuali conflitti di politiche o comportamenti imprevisti.

### 2.2 Schermate di amministrazione dedicate e viste del controller

Il modulo introduce diverse nuove voci di menu nella sezione "Pagamento" del tuo Back Office di PrestaShop.

#### 2.2.1 Politiche dei metodi di pagamento (Back Office > Pagamento > Regole Metodi di Pagamento > Politiche)

Qui è dove definisci e gestisci tutte le tue regole per mostrare o nascondere i metodi di pagamento.

-   **Nome schermata e posizione menu:** **Pagamento > Regole Metodi di Pagamento > Politiche**
-   **Azioni e impostazioni disponibili:**

    -   **Elenco politiche:** Una tabella che mostra tutte le politiche create, il loro stato (abilitato/disabilitato) e i metodi di pagamento che influenzano.
    -   **Aggiungi nuova politica:** Clicca questo pulsante per creare una nuova regola.
    -   **Modifica/Elimina politica:** Gestisci le singole politiche dall'elenco.
    -   **Duplica politica:** Crea rapidamente una copia di una politica esistente per modificarla.
    -   **Abilita/Disabilita politica:** Attiva/disattiva lo stato attivo di una politica senza eliminarla.
    -   **Importa/Esporta politiche (JSON):** Esegui il backup delle tue politiche o trasferiscile tra negozi.
-   **Creazione/Modifica di una politica:**
    Quando aggiungi o modifichi una politica, configurerai diversi aspetti chiave:

    1.  **Nome politica:**

        -   **Cosa fa questa impostazione:** Un nome descrittivo per la tua politica (es. "Nascondi contrassegno per ordini internazionali").
        -   **Effetto della modifica di questa impostazione:** Ti aiuta a identificare la politica nell'elenco.
        -   **Valore consigliato:** Rendilo chiaro e conciso.
        -   **Scenario commerciante:** Nominare una politica "Spedizione gratuita solo con PayPal" ne indica immediatamente lo scopo.
    2.  **Stato (Abilitato/Disabilitato):**

        -   **Cosa fa questa impostazione:** Controlla se la politica è attiva e applicata al checkout.
        -   **Effetto della modifica di questa impostazione:**
            -   *Quando abilitata:* Le regole all'interno di questa politica verranno valutate e influenzeranno la visibilità del metodo di pagamento.
            -   *Quando disabilitata:* La politica viene ignorata e le sue regole non hanno alcun effetto.
        -   **Valore consigliato:** Abilita le politiche solo quando sei sicuro che siano configurate correttamente.
        -   **Scenario commerciante:** Potresti disabilitare temporaneamente una politica durante una promozione o se stai risolvendo un problema.
    3.  **Metodi di pagamento interessati:**

        -   **Cosa fa questa impostazione:** Seleziona quali specifici metodi di pagamento questa politica controllerà.
        -   **Effetto della modifica di questa impostazione:** Solo i metodi di pagamento selezionati saranno soggetti alle regole di questa politica.
        -   **Valore consigliato:** Seleziona tutti i metodi di pagamento pertinenti a questa politica.
        -   **Scenario commerciante:** Se vuoi nascondere "Contrassegno" e "Bonifico bancario" in determinate condizioni, li selezioneresti entrambi qui.
    4.  **Tipo di politica (Mostra/Nascondi):**

        -   **Cosa fa questa impostazione:** Determina se le condizioni della politica *mostreranno* i metodi di pagamento selezionati o li *nasconderanno*.
        -   **Effetto della modifica di questa impostazione:**
            -   *Quando impostato su "Mostra":* I metodi di pagamento selezionati saranno visibili *solo* se TUTTE le condizioni di questa politica sono soddisfatte. Se le condizioni non sono soddisfatte, vengono nascosti.
            -   *Quando impostato su "Nascondi":* I metodi di pagamento selezionati verranno nascosti se TUTTE le condizioni di questa politica sono soddisfatte. Se le condizioni non sono soddisfatte, sono visibili.
        -   **Valore consigliato:** Scegli in base al tuo obiettivo principale. "Nascondi" è spesso più facile per restrizioni specifiche, mentre "Mostra" è buono per offerte esclusive.
        -   **Scenario commerciante:**
            -   *Nascondi:* "Nascondi Contrassegno se il totale del carrello supera i $500."
            -   *Mostra:* "Mostra 'Piano di rateizzazione' SOLO se il gruppo cliente è 'VIP' E il totale del carrello supera i $1000."
    5.  **Costruttore di condizioni:**

        -   **Cosa fa questa impostazione:** Questo è il cuore della tua politica. Costruisci regole complesse usando la logica "E" e "O" basata su vari criteri.
        -   **Effetto della modifica di questa impostazione:** Le condizioni che definisci qui determinano *quando* viene attivata l'azione "Mostra" o "Nascondi" della politica.
        -   **Condizioni disponibili (Esempi):**
            -   **Totale carrello:** Basato sul valore totale del carrello del cliente.
            -   **Gruppo cliente:** Basato sul gruppo a cui appartiene il cliente (es. Ospite, Cliente, VIP, Grossista).
            -   **Paese:** Basato sul paese di spedizione o fatturazione del cliente.
            -   **Corriere:** Basato sul corriere di spedizione selezionato.
            -   **Prodotti nel carrello:** Basato su prodotti, categorie, produttori o fornitori specifici nel carrello.
            -   **Valuta:** Basato sulla valuta utilizzata per l'ordine.
            -   **Peso:** Basato sul peso totale del carrello.
            -   **Data/Ora:** Basato su date o orari specifici (es. per promozioni).
            -   **Negozio:** Per configurazioni multi-negozio.
        -   **Valore consigliato:** Inizia con condizioni semplici e testa a fondo. Usa "E" per requisiti più stringenti e "O" per una maggiore applicabilità.
        -   **Scenario commerciante:**
            -   "Nascondi PayPal se (Paese È 'USA' E Totale carrello È MINORE DI $10) O (Gruppo cliente È 'Grossista')."
            -   "Mostra Bonifico bancario se (Gruppo cliente È 'B2B') E (Totale carrello È MAGGIORE DI $1000)."
    6.  **Messaggio di indisponibilità:**

        -   **Cosa fa questa impostazione:** Un messaggio personalizzato visualizzato al cliente se un metodo di pagamento è nascosto da questa politica.
        -   **Effetto della modifica di questa impostazione:** Fornisce una comunicazione chiara al cliente sul motivo per cui un'opzione di pagamento non è disponibile, prevenendo la confusione.
        -   **Valore consigliato:** Mantienilo educato e informativo (es. "Il contrassegno non è disponibile per ordini superiori a $500. Si prega di scegliere un altro metodo di pagamento.").
        -   **Scenario commerciante:** "Questo metodo di pagamento è disponibile solo per i clienti VIP." o "Si prega di selezionare un metodo di spedizione diverso per utilizzare questa opzione di pagamento."
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

    1.  **Identifica una necessità:** "Voglio smettere di offrire il contrassegno per ordini superiori a $200."
    2.  **Crea una nuova politica:** Chiamala "Limite contrassegno $200".
    3.  **Seleziona "Nascondi"** come tipo di politica.
    4.  **Seleziona "Contrassegno"** come metodo di pagamento interessato.
    5.  **Aggiungi una condizione:** "Totale carrello È MAGGIORE DI $200".
    6.  **Aggiungi un messaggio di indisponibilità:** "Il contrassegno non è disponibile per ordini superiori a $200. Si prega di scegliere un altro metodo di pagamento."
    7.  **Abilita e Salva.**
    8.  **Testa usando il Simulatore** (vedi sezione successiva).

#### 2.2.2 Registro di controllo (Back Office > Pagamento > Regole Metodi di Pagamento > Registro di controllo)

Questa schermata fornisce una cronologia dettagliata di come sono state applicate le tue regole di pagamento.

-   **Nome schermata e posizione menu:** **Pagamento > Regole Metodi di Pagamento > Registro di controllo**
-   **Azioni e impostazioni disponibili:**
    -   **Elenco registri:** Una tabella che mostra ogni istanza in cui la visibilità di un metodo di pagamento è stata influenzata da una politica.
    -   **Dettagli:** Visualizza informazioni specifiche su ogni voce di registro, inclusi il cliente, i dettagli del carrello, le politiche valutate e il risultato finale (quali metodi di pagamento sono stati mostrati/nascosti).
    -   **Filtro:** Filtra le voci di registro per data, cliente, politica o metodo di pagamento per trovare rapidamente eventi specifici.
-   **Effetto delle modifiche:** Questa schermata è per la visualizzazione e il controllo. Non puoi apportare modifiche qui, ma è inestimabile per capire perché certi metodi di pagamento sono stati o non sono stati mostrati a un cliente.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Controlla regolarmente il registro di controllo se ricevi richieste dai clienti su metodi di pagamento mancanti o se sospetti che una politica non funzioni come previsto. È il tuo strumento di debug.

#### 2.2.3 Simulatore (Back Office > Pagamento > Regole Metodi di Pagamento > Simulatore)

Il simulatore è uno strumento potente per testare le tue politiche senza effettuare un ordine reale.

-   **Nome schermata e posizione menu:** **Pagamento > Regole Metodi di Pagamento > Simulatore**
-   **Azioni e impostazioni disponibili:**
    -   **Campi di input:** Inserisci vari criteri come gruppo cliente, paese, corriere, totale carrello e persino aggiungi prodotti specifici a un carrello simulato.
    -   **Pulsante Simula:** Clicca per vedere quali metodi di pagamento sarebbero disponibili in base ai criteri inseriti e alle politiche attive.
    -   **Visualizzazione risultati:** Mostra un elenco di metodi di pagamento disponibili e non disponibili, insieme ai motivi (quali politiche li hanno causati a essere nascosti/mostrati).
-   **Effetto delle modifiche:** Questa schermata ti consente di sperimentare diversi scenari e vedere immediatamente l'impatto delle tue politiche. Non influisce sul tuo negozio live.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** *Usa sempre* il simulatore dopo aver creato o modificato una politica. Testa i casi limite e gli scenari comuni per assicurarti che le tue regole funzionino esattamente come previsto prima che vadano online.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Politiche (Aggiungi/Modifica)** | Nome politica | Nome descrittivo | Identificazione interna della regola. |
| | Stato | Abilitato | Attiva/disattiva la politica. |
| | Metodi di pagamento interessati | Seleziona i metodi pertinenti | Specifica quali gateway di pagamento questa politica controlla. |
| | Tipo di politica | Nascondi | Determina se le condizioni *nascondono* o *mostrano* i metodi selezionati. |
| | Costruttore di condizioni | Varia in base alla regola | Definisce i criteri (es. totale carrello, gruppo cliente) per l'applicazione della politica. |
| | Messaggio di indisponibilità | Testo chiaro e informativo | Messaggio mostrato ai clienti quando un metodo di pagamento è nascosto. |
| **Registro di controllo** | Voci di registro | N/A | Fornisce una cronologia delle valutazioni delle politiche. |
| | Filtri | N/A | Aiuta a cercare e analizzare eventi di registro specifici. |
| **Simulatore** | Input di simulazione | N/A | Consente di testare le politiche con vari scenari cliente/carrello. |
| | Risultati di simulazione | N/A | Mostra quali metodi di pagamento sarebbero disponibili/non disponibili per lo scenario simulato. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Un metodo di pagamento non viene visualizzato, ma non ho impostato alcuna politica per nasconderlo. Cosa c'è che non va?**
R: Innanzitutto, controlla il **Registro di controllo** del modulo per eventuali voci relative a quel metodo di pagamento e cliente. Il registro ti dirà se una politica *lo ha* nascosto. In caso contrario, il problema potrebbe essere al di fuori di questo modulo:
\* Il metodo di pagamento stesso è abilitato in **Pagamento > Metodi di pagamento**?
\* Ci sono restrizioni impostate direttamente sul modulo di pagamento (es. restrizioni per paese, valuta, gruppo all'interno della configurazione del modulo di pagamento stesso)?
\* Svuota la cache di PrestaShop (**Parametri avanzati > Prestazioni**).

**D: Le mie politiche non sembrano funzionare. Cosa devo fare?**
R:
1.  **Controlla lo stato della politica:** Assicurati che la politica sia "Abilitata" nella schermata **Politiche**.
2.  **Usa il Simulatore:** Vai su **Pagamento > Regole Metodi di Pagamento > Simulatore** e inserisci le condizioni esatte che stai testando. Guarda cosa prevede il simulatore. Questo è il modo più veloce per eseguire il debug delle tue condizioni.
3.  **Rivedi le condizioni:** Ricontrolla la tua logica "E" e "O". Una singola condizione errata può impedire l'attivazione dell'intera politica.
4.  **Controlla i metodi di pagamento interessati:** Assicurati che il metodo di pagamento che ti aspetti sia interessato sia effettivamente selezionato nella politica.
5.  **Svuota la cache:** Svuota sempre la cache di PrestaShop (**Parametri avanzati > Prestazioni**) dopo aver apportato modifiche significative alle impostazioni o alle politiche del modulo.

**D: Come gestisco più politiche che influenzano lo stesso metodo di pagamento?**
R: Il modulo valuta tutte le politiche attive.
\* Se più politiche "Nascondi" si applicano allo stesso metodo di pagamento e *una qualsiasi* di esse si attiva, il metodo di pagamento verrà nascosto.
\* Se più politiche "Mostra" si applicano allo stesso metodo di pagamento e *una qualsiasi* di esse si attiva, il metodo di pagamento verrà mostrato.
\* **Risoluzione dei conflitti:** Se una politica dice "Mostra" e un'altra dice "Nascondi" per lo stesso metodo di pagamento nelle stesse condizioni, il modulo ha una strategia di fusione definita (tipicamente, "Nascondi" ha la precedenza per garantire la sicurezza e prevenire disponibilità indesiderate). Usa il **Simulatore** e il **Registro di controllo** per comprendere l'esatto risultato delle politiche in conflitto.

**D: Posso tradurre il "Messaggio di indisponibilità" per diverse lingue?**
R: Sì, durante la modifica di una politica, il campo "Messaggio di indisponibilità" avrà tipicamente un selettore di lingua (un'icona a bandiera) accanto. Clicca sulla bandiera per inserire le traduzioni per ogni lingua abilitata nel tuo negozio.

**D: Il mio tema personalizzato non visualizza correttamente i messaggi di indisponibilità. Cosa posso fare?**
R: Questo di solito indica un conflitto CSS o un override di template mancante nel tuo tema.
\* **Controlla `front.css`:** Il modulo include il proprio `front.css` per lo styling di base. Il tuo tema potrebbe sovrascriverlo.
\* **Ispeziona elemento:** Usa gli strumenti per sviluppatori del tuo browser (F12) per ispezionare l'area in cui dovrebbe apparire il messaggio. Cerca regole CSS che potrebbero nasconderlo o posizionarlo in modo errato.
\* **Contatta lo sviluppatore del tema:** Se non ti senti a tuo agio con il CSS, contatta lo sviluppatore del tuo tema o un esperto PrestaShop per assistenza. Possono aiutarti a integrare lo styling del modulo con il tuo tema.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo Regole Condizionali Metodi di Pagamento segue un design pattern robusto e orientato agli oggetti all'interno del framework MVC di PrestaShop. Utilizza ampiamente `ObjectModel` per la gestione delle politiche e dei registri di controllo, una struttura `ConditionTree` dedicata per la valutazione di regole complesse e un `PaymethodrulesEngine` per applicare queste regole nella fase di checkout. Il modulo inietta la sua logica principalmente tramite hook, in particolare `actionPaymentOptionsModifier` (o simile per le versioni PS più vecchie) per manipolare l'elenco dei metodi di pagamento disponibili. I controller di amministrazione forniscono una ricca interfaccia utente per la gestione delle politiche, la simulazione e il controllo.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

-   `controllers/front/index.php`
    -   **Nome classe:** `PaymethodrulesIndexModuleFrontController` (o simile, tipicamente estende `ModuleFrontController`)
    -   **Responsabilità:** Questo controller potrebbe fungere da fallback o da semplice punto di ingresso, ma la logica principale per la modifica del metodo di pagamento è solitamente gestita tramite hook. Potrebbe essere utilizzato per specifiche richieste AJAX relative alla valutazione delle regole del front-office, se necessario, sebbene la valutazione primaria avvenga durante il rendering delle opzioni di pagamento.
-   `controllers/front/simulate.php`
    -   **Nome classe:** `PaymethodrulesSimulateModuleFrontController` (o simile, estende `ModuleFrontController`)
    -   **Responsabilità:** Sebbene il simulatore principale sia nel BO, un controller frontale potrebbe esistere per una simulazione front-end semplificata o per esporre i risultati della simulazione tramite AJAX a scopo di debug.

#### Controller di amministrazione Back-Office

-   `controllers/admin/AdminPaymethodrulesAuditLog.php`
    -   **Nome classe:** `AdminPaymethodrulesAuditLogController` (estende `ModuleAdminController`)
    -   **Nome scheda:** Regole Metodi di Pagamento -> Registro di controllo
    -   **Entità gestita:** `PaymethodrulesAuditLog` (mappata alla tabella `ps_paymethodrules_log`)
    -   **Responsabilità:** Gestisce la visualizzazione e il filtraggio delle voci del registro di controllo. Utilizza `HelperList` per renderizzare la vista a griglia e fornisce azioni per la visualizzazione dei dettagli del registro.
-   `controllers/admin/AdminPaymethodrulesPolicies.php`
    -   **Nome classe:** `AdminPaymethodrulesPoliciesController` (estende `ModuleAdminController`)
    -   **Nome scheda:** Regole Metodi di Pagamento -> Politiche
    -   **Entità gestita:** `PaymethodrulesPolicy` (mappata alla tabella `ps_paymethodrules_policy`)
    -   **Responsabilità:** Questo è il controller centrale per la gestione delle politiche di pagamento. Gestisce:
        -   Elenco delle politiche utilizzando `HelperList`.
        -   Aggiunta/modifica delle politiche utilizzando `HelperForm` con rendering di campi complessi per il costruttore di condizioni.
        -   Abilitazione/disabilitazione, duplicazione ed eliminazione delle politiche.
        -   Gestione dell'importazione/esportazione JSON delle politiche.
-   `controllers/admin/index.php`
    -   **Nome classe:** `AdminPaymethodrulesDashboardController` (o simile, estende `ModuleAdminController`)
    -   **Nome scheda:** Regole Metodi di Pagamento -> Dashboard (o link di configurazione del modulo principale)
    -   **Entità gestita:** N/A (vista dashboard)
    -   **Responsabilità:** Fornisce il punto di ingresso principale e la vista dashboard per il modulo nel Back Office. Aggrega informazioni da altri controller (es. conteggi delle politiche, voci di registro recenti) e fornisce la navigazione. Tipicamente utilizza i template Smarty per il rendering dei widget della dashboard.

### 4.3 Classi e modelli principali (`classes/`)

-   `classes/index.php`: File vuoto standard per prevenire l'elenco delle directory.
-   `classes/PaymethodrulesAdmin.php`: Probabilmente una classe helper per funzioni comuni relative all'amministrazione, come la registrazione del menu, la gestione delle schede o la logica di rendering dei moduli condivisa.
-   `classes/PaymethodrulesAuditLog.php`
    -   **Estende:** `ObjectModel`
    -   **Tabella database:** `ps_paymethodrules_log`
    -   **Campi `$definition`:** `id_paymethodrules_log`, `id_cart`, `id_customer`, `id_shop`, `context_data` (JSON), `policies_applied` (JSON), `payment_methods_before` (JSON), `payment_methods_after` (JSON), `date_add`.
    -   **Metodi pubblici chiave:** Metodi per la registrazione di eventi, il recupero di voci di registro e possibilmente la pulizia di vecchi registri.
-   `classes/PaymethodrulesCompatibility.php`: Gestisce i livelli di compatibilità per diverse versioni di PrestaShop (es. differenze nei nomi degli hook, nelle strutture degli oggetti o nelle funzioni `Tools`).
-   `classes/PaymethodrulesCondition.php`
    -   **Estende:** `ObjectModel` (o una classe base per le condizioni)
    -   **Tabella database:** `ps_paymethodrules_condition` (se le condizioni sono memorizzate individualmente)
    -   **Campi `$definition`:** `id_paymethodrules_condition`, `id_paymethodrules_policy`, `type`, `operator`, `value`, `id_parent_group`.
    -   **Metodi pubblici chiave:** Metodi per la definizione di tipi di condizione, operatori e valori. Parte della struttura dell'albero delle condizioni.
-   `classes/PaymethodrulesConditionEvaluator.php`: Contiene la logica principale per la valutazione di una singola `PaymethodrulesCondition` rispetto a un dato contesto (carrello, cliente, ecc.).
-   `classes/PaymethodrulesConditionGroup.php`
    -   **Estende:** `ObjectModel` (o una classe base per i gruppi di condizioni)
    -   **Tabella database:** `ps_paymethodrules_condition_group` (se i gruppi sono memorizzati individualmente)
    -   **Campi `$definition`:** `id_paymethodrules_condition_group`, `id_paymethodrules_policy`, `operator` (`AND`/`OR`), `id_parent_group`.
    -   **Metodi pubblici chiave:** Gestisce una collezione di condizioni o gruppi di condizioni nidificati, applicando la logica `AND`/`OR`.
-   `classes/PaymethodrulesConditionTree.php`: Rappresenta l'intera struttura gerarchica di condizioni e gruppi di condizioni per una politica. Fornisce metodi per costruire, attraversare e valutare l'albero.
-   `classes/PaymethodrulesContext.php`: Una classe utility che incapsula tutti i dati rilevanti necessari per la valutazione delle regole (carrello corrente, cliente, indirizzo, corriere, valuta, ecc.). Agisce come fornitore di dati per il `PaymethodrulesEngine`.
-   `classes/PaymethodrulesDashboard.php`: Classe helper per il recupero di dati e la preparazione di statistiche/riepiloghi per la vista dashboard del modulo.
-   `classes/PaymethodrulesEngine.php`: La classe centrale responsabile dell'orchestrazione della valutazione delle regole.
    -   **Metodi pubblici chiave:** `evaluatePolicies(PaymethodrulesContext $context, array $payment_options)`: Prende il contesto corrente e un elenco di opzioni di pagamento disponibili, applica tutte le politiche attive e restituisce l'elenco modificato. Utilizza `PaymethodrulesConditionTree` e `PaymethodrulesConditionEvaluator`.
-   `classes/PaymethodrulesListRenderer.php`: Un helper specializzato per il rendering di elenchi nel Back Office, potenzialmente estendendo `HelperList` o fornendo un rendering personalizzato delle colonne.
-   `classes/PaymethodrulesLog.php`: Alias o implementazione specifica per `PaymethodrulesAuditLog`.
-   `classes/PaymethodrulesPolicy.php`
    -   **Estende:** `ObjectModel`
    -   **Tabella database:** `ps_paymethodrules_policy`
    -   **Campi `$definition`:** `id_paymethodrules_policy`, `name`, `active`, `policy_type` (`show`/`hide`), `payment_methods` (array JSON di nomi di moduli), `unavailable_message` (multilingue), `conditions_tree` (rappresentazione JSON dell'albero delle condizioni), `date_add`, `date_upd`.
    -   **Metodi pubblici chiave:** Metodi per il salvataggio/caricamento dei dati della politica, il recupero delle condizioni associate e la fornitura di logica specifica della politica.
-   `classes/PaymethodrulesPolicyDuplicator.php`: Classe utility specifica per la duplicazione di oggetti `PaymethodrulesPolicy`, garantendo che tutte le condizioni e i gruppi associati vengano copiati correttamente.
-   `classes/PaymethodrulesPreset.php`: Probabilmente gestisce set predefiniti di condizioni o politiche che possono essere caricati rapidamente dal commerciante.
-   `classes/PaymethodrulesRule.php`: Potrebbe essere un nome più vecchio o alternativo per `PaymethodrulesCondition` o `PaymethodrulesPolicy`, o una classe base per i componenti delle regole.
-   `classes/PaymethodrulesTreeRepository.php`: Gestisce la persistenza e il recupero della struttura `PaymethodrulesConditionTree`, probabilmente convertendola da/a JSON per l'archiviazione nell'oggetto `PaymethodrulesPolicy`.

### 4.4 Risorse JavaScript (`views/js/`)

-   `paymethodrules/lib/searchTool/views/js/autocomplete.js`: Funzionalità di completamento automatico generica, probabilmente utilizzata per selezionare prodotti, categorie o altre entità all'interno del costruttore di condizioni.
-   `paymethodrules/lib/searchTool/views/views/js/autocomplete.js`: Duplicato o versione specifica dello script di completamento automatico.
-   `paymethodrules/views/js/adminConditionBuilder.js`:
    -   **Ambito:** Back-office (schermata di creazione/modifica della politica).
    -   **Funzionalità:** Gestisce la creazione, la modifica e l'eliminazione dinamica di condizioni e gruppi di condizioni all'interno del modulo della politica. Gestisce la logica "AND"/"OR", aggiunge nuove righe di condizione, gestisce le modifiche del tipo di condizione (es. mostrando diversi campi di input per "Totale carrello" vs. "Prodotto").
-   `paymethodrules/views/js/adminPaymethodrulesDashboard.js`:
    -   **Ambito:** Back-office (schermata Dashboard).
    -   **Funzionalità:** Potrebbe gestire chiamate AJAX per i widget della dashboard, aggiornare i dati o fornire elementi interattivi sulla dashboard.
-   `paymethodrules/views/js/adminPaymethodrulesSearchTool.js`:
    -   **Ambito:** Back-office (costruttore di condizioni).
    -   **Funzionalità:** Integra la libreria `autocomplete.js` per la ricerca e la selezione di entità (prodotti, categorie, clienti, corrieri) durante la costruzione delle condizioni.
-   `paymethodrules/views/js/adminPaymethodrulesSimulator.js`:
    -   **Ambito:** Back-office (schermata Simulatore).
    -   **Funzionalità:** Acquisisce l'input dell'utente per i criteri di simulazione, invia richieste AJAX al controller del simulatore e aggiorna dinamicamente la visualizzazione con la disponibilità simulata del metodo di pagamento.
-   `paymethodrules/views/js/adminPolicyRules.js`:
    -   **Ambito:** Back-office (elenco delle politiche e schermate di modifica).
    -   **Funzionalità:** JS generale per la gestione delle politiche, come la gestione degli interruttori di abilitazione/disabilitazione, le azioni di duplicazione e potenzialmente la logica di invio del modulo per i dettagli della politica.
-   `paymethodrules/views/js/checkout.js`:
    -   **Ambito:** Front-office (pagina di checkout).
    -   **Funzionalità:** Questo è cruciale. Ascolta i cambiamenti nel processo di checkout (es. selezione del metodo di spedizione, cambio di indirizzo, aggiornamento del carrello) e potrebbe attivare chiamate AJAX per rivalutare la disponibilità del metodo di pagamento o aggiornare dinamicamente la visualizzazione dei messaggi di indisponibilità. Assicura che le opzioni di pagamento siano sempre aggiornate.
-   `paymethodrules/views/js/unavailableUi.js`:
    -   **Ambito:** Front-office (pagina di checkout).
    -   **Funzionalità:** Gestisce la visualizzazione e lo styling del "messaggio di indisponibilità" per i metodi di pagamento nascosti. Potrebbe iniettare dinamicamente il messaggio, applicare classi CSS o gestire animazioni.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `paymethodrules/lib/searchTool/views/css/autocomplete.css`: Stili per lo strumento di ricerca con completamento automatico nel Back Office.
-   `paymethodrules/lib/searchTool/views/views/css/autocomplete.css`: Duplicato o versione specifica del CSS di completamento automatico.
-   `paymethodrules/views/css/admin_paymethodrules.css`:
    -   **Ambito:** Back-office (tutte le schermate di amministrazione del modulo).
    -   **Funzionalità:** Fornisce lo styling per l'elenco delle politiche, il costruttore di condizioni, la dashboard, il simulatore e il registro di controllo. Include stili per gli elementi del modulo, le tabelle e i componenti UI personalizzati specifici del modulo.
    -   **Selettori di classe CSS chiave:** `.paymethodrules-policy-card`, `.condition-group`, `.condition-row`, `.paymethodrules-dashboard-widget`.
-   `paymethodrules/views/css/front.css`:
    -   **Ambito:** Front-office (pagina di checkout).
    -   **Funzionalità:** Fornisce lo styling di base per i messaggi di metodo di pagamento non disponibile o qualsiasi indicazione visiva relativa alle opzioni di pagamento nascoste nella pagina di checkout.
    -   **Selettori di classe CSS chiave:** `.paymethodrules-unavailable-message`, `.paymethodrules-hidden-payment`.

### 4.6 Struttura del template Smarty (`views/templates/`)

#### Template degli hook (`views/templates/hook/`)

-   `paymethodrules/views/templates/hook/payment_top.tpl`:
    -   **Hook:** `displayPaymentTop` (o simile, a seconda della versione PS)
    -   **Blocco visivo:** Questo template potrebbe essere utilizzato per visualizzare un messaggio generale o informazioni relative alle regole di pagamento nella parte superiore della sezione di selezione del pagamento. Tuttavia, l'interazione principale è solitamente la modifica diretta dell'array delle opzioni di pagamento. Potrebbe anche essere utilizzato per iniettare gli script `checkout.js` e `unavailableUi.js`.

#### Template di amministrazione (`views/templates/admin/`)

-   `paymethodrules/lib/searchTool/views/scripts.tpl`: Include JS/CSS per lo strumento di ricerca nell'amministrazione.
-   `paymethodrules/lib/searchTool/views/views/scripts.tpl`: Duplicato o versione specifica degli script dello strumento di ricerca.
-   `paymethodrules/views/templates/admin/auditPreview.tpl`: Renderizza la vista dettagliata per una singola voce del registro di controllo, mostrando il contesto, le politiche applicate e le modifiche al metodo di pagamento.
-   `paymethodrules/views/templates/admin/dashboard.tpl`: Renderizza la dashboard principale del modulo, inclusi i widget per il riepilogo delle politiche, i registri recenti e i collegamenti rapidi.
-   `paymethodrules/views/templates/admin/helpers/list/list_action_duplicate.tpl`: Template personalizzato per il pulsante di azione "duplica" in `HelperList` per le politiche.
-   `paymethodrules/views/templates/admin/policiesPreview.tpl`: Potrebbe essere utilizzato per un'anteprima rapida delle regole di una politica senza entrare nel modulo di modifica completo, o per visualizzare i dettagli della politica nel registro di controllo.
-   `paymethodrules/views/templates/admin/policyConditionBuilder.tpl`: Il template principale per il rendering dell'interfaccia dinamica del costruttore di condizioni all'interno del modulo di aggiunta/modifica della politica. Include parziali per singole condizioni e gruppi.
-   `paymethodrules/views/templates/admin/policyRuleCard.tpl`: Renderizza una singola politica come una scheda o una riga in un elenco, potenzialmente utilizzata nella dashboard o in una vista semplificata della politica.
-   `paymethodrules/views/templates/admin/policyRulesTable.tpl`: Renderizza la tabella principale delle politiche nella schermata `AdminPaymethodrulesPolicies`.
-   `paymethodrules/views/templates/admin/scopeSelector.tpl`: Un template riutilizzabile per la selezione dell'ambito (es. negozio, lingua) all'interno dei moduli di amministrazione.

#### Template Front-office (`views/templates/front/`)

-   Non sono elencati template di pagina front-office dedicati, indicando che il modulo si integra principalmente nei template di checkout esistenti modificando i dati, piuttosto che renderizzare pagine completamente nuove.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

-   `ps_paymethodrules_policy`: Memorizza le definizioni principali delle politiche, inclusi nome, stato, metodi di pagamento interessati, tipo di politica, messaggi di indisponibilità (multilingue) e la rappresentazione JSON dell'albero delle condizioni.
-   `ps_paymethodrules_log`: Memorizza le voci del registro di controllo, inclusi `id_cart`, `id_customer`, `context_data`, `policies_applied`, `payment_methods_before`, `payment_methods_after` e `date_add`.
-   (Potenzialmente) `ps_paymethodrules_condition` e `ps_paymethodrules_condition_group` se l'albero delle condizioni è memorizzato in modo normalizzato piuttosto che interamente come JSON all'interno di `ps_paymethodrules_policy`. Il file `install.sql` lo confermerà.

#### Tabella degli hook registrati

| Nome hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionPaymentOptionsModifier` | Durante il processo di checkout, prima che vengano visualizzati i metodi di pagamento. | **Hook primario:** Il `PaymethodrulesEngine` del modulo viene invocato qui per filtrare e modificare l'array delle opzioni di pagamento disponibili in base alle politiche attive e al contesto del carrello corrente. |
| `displayBackOfficeHeader` | Ad ogni caricamento della pagina del Back Office. | Inietta CSS e JS specifici del modulo per i controller di amministrazione (es. `admin_paymethodrules.css`, `adminConditionBuilder.js`). |
| `displayHeader` | Ad ogni caricamento della pagina del front-office. | Inietta CSS e JS specifici del modulo per il front office (es. `front.css`, `checkout.js`, `unavailableUi.js`), in particolare nella pagina di checkout. |
| `moduleRoutes` | Durante la compilazione delle route di PrestaShop. | Registra route front-office e back-office personalizzate per i controller del modulo (es. `/module/paymethodrules/simulate`). |
| `actionAdminControllerSetMedia` | Quando viene caricato un controller di amministrazione. | Inietta CSS e JS specifici del modulo per il controller di amministrazione corrente, garantendo che le risorse siano caricate solo quando necessario. |
| `actionObject*AddAfter` / `actionObject*UpdateAfter` | Dopo che un oggetto (es. `Cart`, `Customer`) viene aggiunto o aggiornato. | Potenzialmente utilizzato per svuotare le cache interne o attivare una rivalutazione se il modulo mantiene dati memorizzati nella cache. |
| `displayAdminProductsExtra` (o simile) | Nella pagina di modifica del prodotto nel BO. | Potrebbe essere utilizzato per aggiungere condizioni specifiche del prodotto direttamente nella pagina del prodotto, sebbene non esplicitamente menzionato nell'elenco dei file. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Regole Condizionali Metodi di Pagamento", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assistere commercianti e sviluppatori con qualsiasi problema o domanda riguardante la funzionalità e l'integrazione del modulo.
