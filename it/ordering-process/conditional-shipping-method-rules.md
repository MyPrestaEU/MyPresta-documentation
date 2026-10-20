---
title: "Regole Condizionali Metodi di Spedizione - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Regole Condizionali Metodi di Spedizione di MyPresta.eu."
sidebar:
  label: "Regole Condizionali Metodi di Spedizione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Conditional Shipping Method Rules su MyPresta.eu](https://mypresta.eu/modules/ordering-process/conditional-shipping-method-rules.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/conditional-shipping-method-rules/)
>
> ---


# Regole Condizionali Metodi di Spedizione

## 1. Requisiti e Compatibilità

-   **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
-   **Compatibilità PHP**: PHP 7.1 - 8.5
-   **Requisiti di Hosting**: Sono richieste estensioni PHP standard (cURL, JSON, OpenSSL), che sono tipicamente disponibili sulla maggior parte degli ambienti di hosting PrestaShop moderni.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)
Puoi accedere a questa schermata navigando su **Moduli > Gestione moduli**, cercando "Regole Condizionali Metodi di Spedizione" e cliccando su "Configura".

Questa pagina fornisce le impostazioni generali per il comportamento del modulo.

-   **Abilita Modulo:**
    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare l'intera funzionalità del modulo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Tutte le tue regole di spedizione definite saranno attive e influenzeranno i metodi di spedizione visualizzati al checkout.
        -   *Quando disabilitato:* Il modulo sarà inattivo e si applicherà la selezione predefinita del metodo di spedizione di PrestaShop, ignorando tutte le tue regole personalizzate.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio del commerciante:** Potresti disabilitarlo temporaneamente durante la manutenzione o se hai bisogno di ripristinare rapidamente il comportamento di spedizione predefinito. Per il normale funzionamento, mantienilo abilitato.

-   **Strategia di Unione per Regole Multiple:**
    -   **Cosa fa questa impostazione:** Determina come il modulo combina i risultati di più regole attive quando si applicano allo stesso metodo di spedizione.
    -   **Effetto della modifica di questa impostazione:**
        -   *Opzione A (Prioritizza "MOSTRA"):* Se *qualsiasi* regola attiva dice "MOSTRA" un corriere, verrà mostrato, anche se altre regole dicono di "NASCONDERLO". Questa è una strategia più permissiva.
        -   *Opzione B (Prioritizza "NASCONDI"):* Se *qualsiasi* regola attiva dice "NASCONDI" un corriere, verrà nascosto, anche se altre regole dicono di "MOSTRARLO". Questa è una strategia più restrittiva.
        -   *Opzione C (Strategia di Unione Personalizzata 1):* [Spiegazione dettagliata della logica specifica, ad esempio, "Mostra solo se TUTTE le regole applicabili dicono MOSTRA"]
        -   *Opzione D (Strategia di Unione Personalizzata 2):* [Spiegazione dettagliata della logica specifica]
        -   *Opzione E (Strategia di Unione Personalizzata 3):* [Spiegazione dettagliata della logica specifica]
    -   **Valore consigliato:** Prioritizza "NASCONDI" (per sicurezza, garantendo che non vengano mostrati corrieri indesiderati). Tuttavia, questo dipende fortemente dalla tua specifica configurazione delle regole.
    -   **Scenario / esempio del commerciante:** Se hai una regola per "MOSTRARE" la spedizione gratuita per ordini superiori a 100€, ma un'altra regola per "NASCONDERE" la spedizione gratuita per un prodotto specifico, la strategia di unione determina quale regola vince. "Prioritizza NASCONDI" nasconderebbe la spedizione gratuita per quel prodotto, anche se l'ordine è superiore a 100€.

-   **Visualizza Messaggi Metodo di Spedizione Non Disponibile:**
    -   **Cosa fa questa impostazione:** Controlla se i clienti vedono una spiegazione quando un metodo di spedizione è nascosto da una regola.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Se un corriere è nascosto, verrà visualizzato un messaggio (che definisci per regola) al cliente, spiegando perché non è disponibile.
        -   *Quando disabilitato:* I corrieri nascosti scompariranno semplicemente dall'elenco senza alcuna spiegazione.
    -   **Valore consigliato:** SÌ (Migliora l'esperienza del cliente e riduce la confusione).
    -   **Scenario / esempio del commerciante:** Se "Spedizione Express" è nascosta perché il carrello del cliente contiene un "Articolo Fragile" che non può essere spedito tramite express, abilitando questa opzione verrà mostrato un messaggio come "La spedizione Express non è disponibile per articoli fragili."

-   **Conservazione Log di Audit (Giorni):**
    -   **Cosa fa questa impostazione:** Definisce per quanto tempo il modulo conserva i record delle valutazioni delle regole e dei loro risultati nel log di audit.
    -   **Effetto della modifica di questa impostazione:**
        -   *Impostando un numero (ad esempio, 30):* Il modulo eliminerà automaticamente le voci di log più vecchie di questo numero di giorni.
        -   *Impostando a 0 o vuoto:* Il modulo conserverà tutte le voci di log indefinitamente (può portare a un database di grandi dimensioni nel tempo).
    -   **Valore consigliato:** 30-90 giorni (sufficiente per la risoluzione dei problemi senza un'eccessiva crescita del database).
    -   **Scenario / esempio del commerciante:** Se un cliente si lamenta di non vedere un metodo di spedizione specifico, puoi controllare il log di audit per le valutazioni recenti. Mantenere i log per 30 giorni ti consente di indagare su problemi recenti senza archiviare anni di dati.

-   **Abilita Simulatore di Checkout:**
    -   **Cosa fa questa impostazione:** Attiva uno strumento nel back office che ti consente di testare le tue regole di spedizione simulando diversi scenari di clienti e carrelli.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* La scheda "Simulatore di Checkout" apparirà nella configurazione del modulo, fornendo un potente ambiente di test.
        -   *Quando disabilitato:* Il simulatore non sarà disponibile.
    -   **Valore consigliato:** SÌ (Essenziale per testare regole complesse prima della distribuzione).
    -   **Scenario / esempio del commerciante:** Prima di lanciare una nuova promozione di spedizione, puoi utilizzare il simulatore per assicurarti che le tue regole mostrino/nascondano correttamente la spedizione promozionale per vari valori del carrello, gruppi di clienti e indirizzi.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### 2.2.1 Politiche di Spedizione (Back Office > Moduli > Regole Condizionali Metodi di Spedizione > Politiche di Spedizione)
Questa è la schermata principale dove definisci e gestisci tutte le tue regole di spedizione.

-   **Nome schermata e posizione nel menu:** **Regole Condizionali Metodi di Spedizione > Politiche di Spedizione** (si trova nella sezione "Moduli" nel menu del back office di PrestaShop).
-   **Azioni e impostazioni disponibili:**
    -   **Elenco Politiche:** Una tabella che mostra tutte le politiche di spedizione create. Ogni politica ha un nome, uno stato (abilitata/disabilitata) e azioni.
    -   **Aggiungi Nuova Politica:** Un pulsante per creare una nuova politica di spedizione.
    -   **Modifica Politica:** Clicca su una politica esistente per modificarne le regole, le condizioni e le impostazioni.
    -   **Duplica Politica:** Crea rapidamente una copia di una politica esistente, utile per apportare piccole variazioni.
    -   **Abilita/Disabilita Politica:** Attiva o disattiva lo stato di una politica senza eliminarla.
    -   **Elimina Politica:** Rimuovi una politica in modo permanente.
    -   **Modulo di Configurazione Politica (quando si aggiunge/modifica):**
        -   **Nome Politica:** Un nome descrittivo per il tuo set di regole (ad esempio, "Spedizione Gratuita oltre 100€", "Restrizioni Spedizione Express").
        -   **Stato:** Abilita o disabilita questa specifica politica.
        -   **Priorità:** Se si applicano più politiche, questo determina l'ordine in cui vengono valutate. Numeri più bassi significano priorità più alta.
        -   **Corrieri Target:** Seleziona quali specifici corrieri di spedizione saranno interessati da questa politica.
        -   **Azione (MOSTRA/NASCONDI):** Scegli se questa politica deve *mostrare* i corrieri selezionati se le condizioni sono soddisfatte, o *nasconderli*.
        -   **Messaggio di Indisponibilità:** Se hai scelto "NASCONDI" e "Visualizza Messaggi Metodo di Spedizione Non Disponibile" è abilitato nella configurazione principale, questo è il messaggio che i clienti vedranno (multilingue).
        -   **Costruttore di Condizioni:** Qui definisci la parte "SE" della tua regola. Puoi aggiungere più gruppi di condizioni (logica E/O) basati su:
            -   Totale carrello, peso, quantità
            -   Prodotti o categorie specifiche nel carrello
            -   Gruppo di clienti, paese, stato, codice postale
            -   Data e ora
            -   E molti altri criteri.
-   **Effetto delle modifiche:**
    -   L'aggiunta, la modifica o l'eliminazione di politiche influisce direttamente sui metodi di spedizione presentati ai clienti al checkout, in base alle condizioni definite.
    -   La modifica dello stato di una politica (abilita/disabilita) attiva o disattiva immediatamente il suo effetto sul front office.
    -   La regolazione della priorità può risolvere i conflitti se più politiche si applicano allo stesso corriere.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  **Pianifica la tua regola:** Prima di creare, definisci chiaramente cosa vuoi ottenere (ad esempio, "Se totale carrello > 50€ E il cliente è negli USA, ALLORA MOSTRA 'Spedizione Standard'").
    2.  **Crea una nuova politica:** Dagli un nome chiaro.
    3.  **Seleziona Corrieri Target:** Scegli i corrieri che questa politica influenzerà.
    4.  **Imposta Azione:** Decidi se la politica deve MOSTRARE o NASCONDERE questi corrieri.
    5.  **Costruisci Condizioni:** Usa l'intuitivo costruttore di condizioni per impostare le tue istruzioni "SE". Usa "Aggiungi Gruppo di Condizioni" per la logica OR e "Aggiungi Condizione" all'interno di un gruppo per la logica AND.
    6.  **Testa con il Simulatore:** Fondamentale, usa il "Simulatore di Checkout" (vedi sezione successiva) per verificare che le tue regole funzionino come previsto per vari scenari.
    7.  **Abilita:** Una volta testata, abilita la politica.

#### 2.2.2 Log di Audit (Back Office > Moduli > Regole Condizionali Metodi di Spedizione > Log di Audit)
Questa schermata fornisce una cronologia di come le tue regole di spedizione sono state valutate.

-   **Nome schermata e posizione nel menu:** **Regole Condizionali Metodi di Spedizione > Log di Audit** (si trova nella sezione "Moduli" nel menu del back office di PrestaShop).
-   **Azioni e impostazioni disponibili:**
    -   **Tabella Log:** Un elenco dettagliato di ogni volta che il modulo ha valutato le regole di spedizione per il carrello di un cliente.
    -   **Colonne:** Include informazioni come:
        -   Data e ora della valutazione
        -   ID Cliente (se loggato)
        -   ID Carrello
        -   Politiche Applicate: Quali politiche sono state considerate.
        -   Esito: Quali corrieri sono stati mostrati/nascosti e perché.
        -   Snapshot Ordine: Un link per visualizzare lo stato esatto del carrello al momento della valutazione.
    -   **Filtro e Ordinamento:** Funzionalità standard delle liste di PrestaShop per filtrare per data, cliente o ID carrello.
-   **Effetto delle modifiche:** Questa è una schermata di sola lettura per il monitoraggio e la risoluzione dei problemi. Non puoi apportare modifiche dirette qui, ma i dati ti aiutano a capire come stanno funzionando le tue regole.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    -   Usa questo log per diagnosticare problemi segnalati dai clienti (ad esempio, "Non ho visto la spedizione gratuita"). Puoi trovare il loro ID carrello o ID cliente e vedere esattamente quali regole sono state applicate e qual è stato il risultato.
    -   Rivedi periodicamente il log per assicurarti che le regole si attivino come previsto, specialmente dopo aver apportato modifiche alle politiche.

#### 2.2.3 Simulatore di Checkout (Back Office > Moduli > Regole Condizionali Metodi di Spedizione > Simulatore di Checkout)
Questo potente strumento ti consente di testare le tue regole di spedizione senza effettuare un ordine reale.

-   **Nome schermata e posizione nel menu:** **Regole Condizionali Metodi di Spedizione > Simulatore di Checkout** (si trova nella sezione "Moduli" nel menu del back office di PrestaShop, visibile solo se "Abilita Simulatore di Checkout" è attivo nella configurazione principale).
-   **Azioni e impostazioni disponibili:**
    -   **Selezione Cliente:** Scegli un cliente esistente dal tuo negozio o simula un ospite.
    -   **Selezione Indirizzo:** Seleziona un indirizzo specifico per il cliente scelto o inserisci manualmente i dettagli dell'indirizzo.
    -   **Contenuto Carrello:** Aggiungi prodotti specifici, quantità e combinazioni per simulare il carrello di un cliente.
    -   **Pulsante Simula:** Clicca su questo per eseguire la simulazione.
    -   **Visualizzazione Risultati:** Mostra quali metodi di spedizione sarebbero disponibili (e quali sarebbero nascosti con i loro messaggi) per lo scenario simulato. Dettaglia anche quali politiche sono state applicate e perché.
-   **Effetto delle modifiche:** Questa schermata non modifica alcun dato del negozio in tempo reale. È puramente un ambiente di test.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    -   **Prima di attivare nuove politiche:** Testale sempre accuratamente qui.
    -   **Risoluzione dei problemi:** Ricrea un problema segnalato da un cliente simulando il suo carrello e indirizzo esatti per vedere perché un corriere è stato o non è stato mostrato.
    -   **Scenari Complessi:** Testa casi limite, come valori minimi/massimi dell'ordine, combinazioni di prodotti specifiche o diversi gruppi di clienti.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
|---|---|---|---|
| **Configurazione Modulo** | Abilita Modulo | SÌ | Interruttore principale per la funzionalità del modulo. |
| | Strategia di Unione per Regole Multiple | Prioritizza "NASCONDI" | Come vengono risolte le regole in conflitto (MOSTRA vs. NASCONDI). |
| | Visualizza Messaggi Metodo di Spedizione Non Disponibile | SÌ | Mostra spiegazioni per i corrieri nascosti ai clienti. |
| | Conservazione Log di Audit (Giorni) | 30-90 | Per quanto tempo vengono conservati i log di valutazione delle regole. |
| | Abilita Simulatore di Checkout | SÌ | Attiva lo strumento di test nel back office. |
| **Politiche di Spedizione** | Nome Politica | Nome Descrittivo | Identifica il set di regole. |
| | Stato | Abilitato | Attiva/disattiva questa specifica politica. |
| | Priorità | Numero inferiore = priorità più alta | Determina l'ordine di valutazione per le politiche in conflitto. |
| | Corrieri Target | Corrieri Specifici | Quali metodi di spedizione sono interessati da questa politica. |
| | Azione (MOSTRA/NASCONDI) | MOSTRA/NASCONDI | Se mostrare o nascondere i corrieri target se le condizioni sono soddisfatte. |
| | Messaggio di Indisponibilità | Testo Personalizzato (multilingue) | Messaggio mostrato quando il corriere è nascosto (se abilitato). |
| | Costruttore di Condizioni | Varia | Definisce i criteri "SE" per l'applicazione della politica. |
| **Log di Audit** | (Tutte le colonne) | N/A (Sola lettura) | Fornisce registrazioni storiche delle valutazioni delle regole per la risoluzione dei problemi. |
| **Simulatore di Checkout** | (Tutti i campi) | N/A (Strumento di test) | Consente di simulare scenari cliente/carrello per testare le regole. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Le mie regole non funzionano, o vedo opzioni di spedizione inaspettate. Cosa devo fare?**
R1:
1.  **Controlla lo Stato del Modulo:** Assicurati che l'impostazione "Abilita Modulo" nella pagina di configurazione principale sia impostata su SÌ.
2.  **Controlla lo Stato della Politica:** Vai su "Politiche di Spedizione" e verifica che le politiche specifiche che ti aspetti siano attive siano abilitate.
3.  **Svuota la Cache:** Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota la cache". A volte PrestaShop memorizza nella cache vecchie configurazioni.
4.  **Usa il Simulatore di Checkout:** Questo è il tuo migliore amico! Ricrea lo scenario esatto (cliente, indirizzo, contenuto del carrello) nel simulatore. Ti mostrerà esattamente quali regole sono state applicate e perché, aiutandoti a individuare il problema.
5.  **Rivedi il Log di Audit:** Se un cliente ha segnalato un problema, controlla il "Log di Audit" per il suo ID carrello/cliente per vedere come le regole sono state valutate per il suo ordine specifico.
6.  **Strategia di Unione:** Rivedi l'impostazione "Strategia di Unione per Regole Multiple". Se hai regole SHOW e HIDE in conflitto, questa impostazione determina il risultato.

**D2: Perché il mio "Messaggio di Indisponibilità" personalizzato non viene visualizzato?**
R2:
1.  **Abilita Visualizzazione Messaggi:** Nella pagina di configurazione principale del modulo, assicurati che "Visualizza Messaggi Metodo di Spedizione Non Disponibile" sia impostato su SÌ.
2.  **Azione della Politica:** Verifica che l'"Azione" della politica sia impostata su "NASCONDI" per il corriere target. I messaggi vengono visualizzati solo quando un corriere è nascosto.
3.  **Contenuto del Messaggio:** Assicurati di aver effettivamente inserito un messaggio nel campo "Messaggio di Indisponibilità" per la politica specifica e che sia tradotto per le lingue pertinenti.

**D3: Il modulo sta rallentando il mio checkout. È normale?**
R3: Il modulo è altamente ottimizzato, ma regole molto complesse (ad esempio, centinaia di condizioni, molte politiche) possono aggiungere un leggero overhead.
1.  **Semplifica le Regole:** Rivedi le tue politiche. Possono essere combinate o semplificate?
2.  **Prioritizza:** Assicurati che le tue regole più frequentemente attivate abbiano una priorità più alta (numero inferiore) in modo che vengano valutate per prime.
3.  **Dimensione del Database:** Controlla l'impostazione "Conservazione Log di Audit". Se impostata per conservare i log indefinitamente, una tabella di log molto grande può influire sulle prestazioni. Impostala su un numero ragionevole di giorni (ad esempio, 30-90).

**D4: Come posso assicurarmi che il mio tema personalizzato visualizzi correttamente le opzioni di spedizione?**
R4: Il modulo si integra con il processo di checkout standard di PrestaShop.
1.  **Hook Standard:** Il modulo utilizza gli hook standard di PrestaShop. Se il tuo tema personalizza pesantemente il checkout, assicurati che chiami ancora correttamente `displayCarrierList` o hook simili dove vengono renderizzate le opzioni di spedizione.
2.  **Conflitti CSS:** Se la visualizzazione sembra errata (ad esempio, i messaggi sono disallineati), potrebbe esserci un conflitto CSS con il tuo tema. Utilizza gli strumenti per sviluppatori del tuo browser (F12) per ispezionare gli elementi e identificare le regole CSS in conflitto. Potrebbe essere necessario aggiungere CSS personalizzato al tuo tema per sovrascrivere gli stili del modulo o del tema.
3.  **Contatta il Supporto:** Se stai utilizzando un tema altamente personalizzato e riscontri problemi di visualizzazione persistenti, fornisci i dettagli al supporto di MyPresta.eu.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

### 4.1 Panoramica dell'Architettura
Il modulo "Regole Condizionali Metodi di Spedizione" (`shipmethodrules`) è costruito seguendo il modello MVC (Model-View-Controller) di PrestaShop, sfruttando pesantemente `ObjectModel` per la persistenza dei dati e un motore di politiche personalizzato per la valutazione delle regole. Introduce diversi controller amministrativi personalizzati per la gestione delle politiche, la visualizzazione dei log di audit e la simulazione degli scenari di checkout. La logica centrale ruota attorno agli oggetti `ShipmethodrulesPolicy`, che incapsulano le entità `ShipmethodrulesConditionGroup` e `ShipmethodrulesCondition`, consentendo una complessa logica annidata AND/OR. Il `ShipmethodrulesEngine` è responsabile della valutazione di queste politiche rispetto a un dato `ShipmethodrulesContext` (che rappresenta il carrello, il cliente e l'indirizzo attuali) e della determinazione della visibilità dei corrieri di spedizione.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office
-   `controllers/front/index.php`:
    -   Nome classe: `ShipmethodrulesIndexModuleFrontController`
    -   Classe padre: `ModuleFrontController`
    -   Responsabilità: Probabilmente un segnaposto o un controller di base. In molti moduli, questo potrebbe gestire la configurazione iniziale o il reindirizzamento se è necessaria una pagina front-office dedicata. Per questo modulo, la logica primaria del front-office è integrata tramite hook nel processo di checkout.
-   `controllers/front/simulate.php`:
    -   Nome classe: `ShipmethodrulesSimulateModuleFrontController`
    -   Classe padre: `ModuleFrontController`
    -   Responsabilità: Gestisce le richieste AJAX relative al simulatore di checkout. Riceve i dati simulati del carrello, del cliente e dell'indirizzo, quindi utilizza il `ShipmethodrulesEngine` per valutare le politiche e restituisce la visibilità del corriere risultante.
-   `controllers/front/visibility.php`:
    -   Nome classe: `ShipmethodrulesVisibilityModuleFrontController`
    -   Classe padre: `ModuleFrontController`
    -   Responsabilità: Questo controller è cruciale per gli aggiornamenti in tempo reale sulla pagina di checkout. Risponde alle richieste AJAX (ad esempio, quando un cliente cambia indirizzo o contenuto del carrello) per rivalutare le regole di spedizione e restituire l'elenco aggiornato dei corrieri disponibili e dei loro messaggi associati.

#### Controller Admin Back-Office
-   `controllers/admin/AdminShipmethodrulesAuditLog.php`:
    -   Nome classe: `AdminShipmethodrulesAuditLogController`
    -   Classe padre: `ModuleAdminController`
    -   Nome scheda: "Log di Audit"
    -   Entità gestita: `ShipmethodrulesLog`
    -   Responsabilità: Gestisce la visualizzazione e il filtraggio della tabella `ps_shipmethodrules_log`. Fornisce una vista a griglia di tutte le valutazioni delle regole, inclusi i dettagli sul carrello, il cliente, le politiche applicate e il risultato finale (quali corrieri sono stati mostrati/nascosti).
-   `controllers/admin/AdminShipmethodrulesPolicies.php`:
    -   Nome classe: `AdminShipmethodrulesPoliciesController`
    -   Classe padre: `ModuleAdminController`
    -   Nome scheda: "Politiche di Spedizione"
    -   Entità gestita: `ShipmethodrulesPolicy`
    -   Responsabilità: Questo è il controller principale per la gestione delle politiche di spedizione. Gestisce l'elenco, l'aggiunta, la modifica, la duplicazione, l'abilitazione/disabilitazione e l'eliminazione degli oggetti `ShipmethodrulesPolicy`. Orchesta anche l'interfaccia del costruttore di condizioni.
-   `controllers/admin/index.php`:
    -   Nome classe: `ShipmethodrulesAdminController` (o simile, se è un controller di base per la sezione admin del modulo)
    -   Classe padre: `ModuleAdminController`
    -   Responsabilità: Spesso agisce come un dispatcher o un controller predefinito per la voce di menu principale dell'amministrazione del modulo, reindirizzando alla configurazione principale o all'elenco delle politiche.

### 4.3 Classi e Modelli Core (`classes/`)

-   `classes/ShipmethodrulesAdmin.php`: Probabilmente una classe helper per funzionalità comuni relative all'amministrazione o statistiche del dashboard.
-   `classes/ShipmethodrulesAuditLog.php`: Estende `ObjectModel`. Mappa alla tabella `ps_shipmethodrules_log`. Memorizza i dettagli di ogni evento di valutazione delle regole a fini di audit.
    -   Campi `$definition`: `id_cart`, `id_customer`, `id_address_delivery`, `policies_applied`, `carriers_visibility`, `timestamp`.
-   `classes/ShipmethodrulesCompatibility.php`: Fornisce metodi per gestire le differenze tra PrestaShop 1.7, 8 e 9, garantendo la compatibilità tra le versioni per le funzionalità principali (ad esempio, registrazione hook, accesso alla configurazione).
-   `classes/ShipmethodrulesCondition.php`: Estende `ObjectModel`. Rappresenta una singola condizione all'interno di un gruppo di condizioni (ad esempio, "Totale Carrello > 100€").
    -   Campi `$definition`: `id_shipmethodrules_condition_group`, `type`, `operator`, `value`, `id_product`, `id_category`, ecc.
-   `classes/ShipmethodrulesConditionEvaluator.php`: Contiene la logica per valutare una singola `ShipmethodrulesCondition` rispetto all'attuale `ShipmethodrulesContext`.
-   `classes/ShipmethodrulesConditionGroup.php`: Estende `ObjectModel`. Rappresenta un gruppo di condizioni collegate da un operatore AND. Più gruppi possono essere collegati da un operatore OR all'interno di una politica.
    -   Campi `$definition`: `id_shipmethodrules_policy`, `logic_operator` (implicitamente AND per le condizioni interne, OR per i gruppi).
-   `classes/ShipmethodrulesConditionTree.php`: Gestisce la struttura gerarchica delle condizioni e dei gruppi di condizioni per una politica, facilitandone l'archiviazione e il recupero.
-   `classes/ShipmethodrulesContext.php`: Un oggetto che incapsula tutti i dati rilevanti per la valutazione delle regole: `Cart`, `Customer`, `Address`, `Currency`, `Language` attuali, ecc. Questo fornisce un'interfaccia coerente per il `ShipmethodrulesEngine`.
-   `classes/ShipmethodrulesDashboard.php`: Classe helper per la generazione di statistiche o riepiloghi del dashboard relativi all'attività del modulo.
-   `classes/ShipmethodrulesEngine.php`: La classe centrale per la valutazione delle regole. Prende un `ShipmethodrulesContext` e un elenco di oggetti `ShipmethodrulesPolicy`, applica la strategia di unione configurata e restituisce lo stato di visibilità finale per ogni corriere.
-   `classes/ShipmethodrulesListRenderer.php`: Renderer personalizzato per gli elenchi di amministrazione, che potenzialmente aggiunge azioni specifiche (come la duplicazione) o la formattazione personalizzata delle colonne.
-   `classes/ShipmethodrulesLog.php`: Alias o implementazione specifica per `ShipmethodrulesAuditLog`.
-   `classes/ShipmethodrulesOrderSnapshot.php`: Cattura e memorizza uno snapshot dello stato di un ordine (carrello, cliente, indirizzo) al momento della valutazione delle regole, utile per il debug.
-   `classes/ShipmethodrulesPolicy.php`: Estende `ObjectModel`. Il modello principale per una regola di spedizione. Contiene il nome della politica, lo stato, la priorità, i corrieri target, l'azione (MOSTRA/NASCONDI), il messaggio di indisponibilità e una collezione di oggetti `ShipmethodrulesConditionGroup`.
    -   Campi `$definition`: `name`, `active`, `priority`, `action`, `unavailable_message`, `target_carriers`.
-   `classes/ShipmethodrulesPolicyDuplicator.php`: Gestisce la logica per la duplicazione di una `ShipmethodrulesPolicy`, inclusi tutti i suoi gruppi di condizioni e condizioni associate.
-   `classes/ShipmethodrulesPreset.php`: Probabilmente gestisce set predefiniti di condizioni o politiche che possono essere applicati rapidamente.
-   `classes/ShipmethodrulesRule.php`: Una rappresentazione più generica di una regola, possibilmente una classe base astratta o un'iterazione precedente di `ShipmethodrulesPolicy`.
-   `classes/ShipmethodrulesTreeRepository.php`: Gestisce la persistenza e il recupero della struttura ad albero delle condizioni.

### 4.4 Risorse JavaScript (`views/js/`)

-   `shipmethodrules/lib/searchTool/views/js/autocomplete.js`: Funzionalità di completamento automatico generica, probabilmente utilizzata per la ricerca di prodotti, categorie o clienti nel costruttore di condizioni.
-   `shipmethodrules/lib/searchTool/views/views/js/autocomplete.js`: Duplicato o istanza specifica dello script di completamento automatico.
-   `shipmethodrules/views/js/adminConditionBuilder.js`: Gestisce la creazione, modifica ed eliminazione dinamica di condizioni e gruppi di condizioni all'interno dell'interfaccia di modifica delle politiche. Gestisce l'interfaccia utente complessa per la costruzione delle regole.
-   `shipmethodrules/views/js/adminPolicyRules.js`: JS specifico per il controller `AdminShipmethodrulesPolicies`, che gestisce l'elenco delle politiche, le azioni di massa e potenzialmente le interazioni con il costruttore di condizioni.
-   `shipmethodrules/views/js/adminShipmethodrulesDashboard.js`: Script per eventuali widget del dashboard o statistiche visualizzate nella sezione di amministrazione del modulo.
-   `shipmethodrules/views/js/adminShipmethodrulesSearchTool.js`: Integra lo strumento di ricerca (completamento automatico) specificamente per i moduli di amministrazione del modulo.
-   `shipmethodrules/views/js/adminShipmethodrulesSimulator.js`: Alimenta l'interfaccia del "Simulatore di Checkout", gestendo l'input dell'utente per cliente, indirizzo e carrello, ed effettuando chiamate AJAX a `controllers/front/simulate.php`.
-   `shipmethodrules/views/js/checkout.js`: Script front-office iniettato nel processo di checkout. Ascolta i cambiamenti nel carrello o nell'indirizzo di consegna, quindi effettua chiamate AJAX a `controllers/front/visibility.php` per aggiornare dinamicamente i metodi di spedizione visualizzati.
-   `shipmethodrules/views/js/unavailableUi.js`: Gestisce la visualizzazione e lo stile dei messaggi di metodo di spedizione non disponibile nella pagina di checkout del front office.

### 4.5 Fogli di Stile CSS (`views/css/`)

-   `shipmethodrules/lib/searchTool/views/css/autocomplete.css`: Stili per lo strumento di ricerca con completamento automatico.
-   `shipmethodrules/lib/searchTool/views/views/css/autocomplete.css`: Duplicato o istanza specifica degli stili di completamento automatico.
-   `shipmethodrules/views/css/admin_order_snapshot.css`: Stili per la visualizzazione dei dettagli dello snapshot dell'ordine nel log di audit o nel simulatore.
-   `shipmethodrules/views/css/admin_shipmethodrules.css`: Stili generali per le interfacce di back-office del modulo, inclusi elenchi di politiche, costruttore di condizioni e simulatore.
-   `shipmethodrules/views/css/front.css`: Stili front-office per la visualizzazione di messaggi di metodo di spedizione non disponibile o per l'evidenziazione di opzioni di spedizione specifiche nella pagina di checkout.

### 4.6 Struttura del Template Smarty (`views/templates/`)

#### Template Hook (`views/templates/hook/`)
-   `shipmethodrules/views/templates/hook/carrier_guard.tpl`: Renderizza un input nascosto o uno script per "proteggere" da selezioni di corrieri non valide, assicurando che solo i corrieri consentiti possano essere inviati.
-   `shipmethodrules/views/templates/hook/carrier_list.tpl`: Sovrascrive o estende il template predefinito dell'elenco dei corrieri nel checkout per applicare le regole di visibilità e visualizzare i messaggi di indisponibilità. Qui viene effettivamente renderizzato l'elenco filtrato dei corrieri.

#### Template Admin (`views/templates/admin/`)
-   `shipmethodrules/views/templates/admin/auditPreview.tpl`: Template per la visualizzazione di un'anteprima dettagliata di una voce del log di audit.
-   `shipmethodrules/views/templates/admin/dashboard.tpl`: Template per la configurazione principale del modulo o la vista del dashboard.
-   `shipmethodrules/views/templates/admin/helpers/list/list_action_duplicate.tpl`: Template personalizzato per il pulsante di azione "duplica" negli elenchi di amministrazione (ad esempio, per le politiche).
-   `shipmethodrules/views/templates/admin/policiesPreview.tpl`: Template per la visualizzazione di un'anteprima di una politica di spedizione.
-   `shipmethodrules/views/templates/admin/policyConditionBuilder.tpl`: Il template complesso che renderizza l'interfaccia utente per la costruzione delle condizioni (menu a discesa, campi di input, logica AND/OR).
-   `shipmethodrules/views/templates/admin/policyRuleCard.tpl`: Renderizza una singola regola o politica come una scheda in una vista elenco.
-   `shipmethodrules/views/templates/admin/policyRulesTable.tpl`: Renderizza la tabella delle politiche di spedizione.
-   `shipmethodrules/views/templates/admin/scopeSelector.tpl`: Template per la selezione dell'ambito di una condizione (ad esempio, "Totale Carrello", "Gruppo Cliente").

#### Altri template
-   `shipmethodrules/lib/searchTool/views/scripts.tpl`: Include JavaScript per lo strumento di ricerca.
-   `shipmethodrules/lib/searchTool/views/views/scripts.tpl`: Duplicato o istanza specifica degli script dello strumento di ricerca.

### 4.7 Schema del Database e Mappa degli Hook

#### Tabelle del Database
-   `ps_shipmethodrules_policy`: Memorizza le definizioni principali delle politiche di spedizione (nome, stato attivo, priorità, azione, messaggio di indisponibilità, corrieri target).
-   `ps_shipmethodrules_condition_group`: Memorizza i gruppi di condizioni associati a una politica.
-   `ps_shipmethodrules_condition`: Memorizza le singole condizioni (tipo, operatore, valore, entità associate come ID prodotto/categoria).
-   `ps_shipmethodrules_log`: Memorizza le voci del log di audit delle valutazioni delle regole (ID carrello, ID cliente, timestamp, politiche applicate, visibilità dei corrieri).
-   `ps_shipmethodrules_order_snapshot`: Memorizza snapshot dettagliati dei dati del carrello/ordine per le voci del log di audit.

#### Tabella degli Hook Registrati

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
|---|---|---|
| `displayHeader` | Nella sezione `<head>` di tutte le pagine del front-office. | Inietta i file CSS e JS necessari per la funzionalità del front-office (ad esempio, `checkout.js`, `front.css`). |
| `displayCarrierList` | Nella pagina di checkout, dove sono elencati i metodi di spedizione. | L'hook principale per filtrare e renderizzare i metodi di spedizione disponibili in base alle politiche definite. |
| `actionCarrierProcess` | Dopo che un corriere è stato selezionato ma prima che l'ordine sia convalidato. | Agisce come una "guardia" per rivalutare il corriere selezionato rispetto alle regole, impedendo l'invio di una scelta non valida. |
| `actionValidateOrder` | Dopo che un ordine è stato convalidato con successo. | Potenzialmente registra il metodo di spedizione finale scelto e le regole applicate nel log di audit. |
| `actionAdminControllerSetMedia` | Nel back office, quando viene caricato un controller amministrativo. | Inietta CSS e JS per le interfacce di amministrazione del modulo (costruttore di politiche, simulatore, log di audit). |
| `actionObjectCarrierAddAfter` | Dopo l'aggiunta di un nuovo corriere. | Potenzialmente aggiorna i dati interni del modulo o le cache relative ai corrieri. |
| `actionObjectCarrierUpdateAfter` | Dopo l'aggiornamento di un corriere. | Potenzialmente aggiorna i dati interni del modulo o le cache relative ai corrieri. |
| `actionObjectCarrierDeleteAfter` | Dopo l'eliminazione di un corriere. | Pulisce eventuali riferimenti al corriere eliminato nelle politiche. |
| `displayBackOfficeHeader` | Nell'intestazione di tutte le pagine del back-office. | Inietta CSS/JS globali dell'amministrazione o script specifici per le pagine di amministrazione del modulo. |

## 5. Supporto Ufficiale e Aggiornamenti
Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Regole Condizionali Metodi di Spedizione", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere commercianti e sviluppatori con qualsiasi problema o domanda riguardante la funzionalità e l'integrazione del modulo.
