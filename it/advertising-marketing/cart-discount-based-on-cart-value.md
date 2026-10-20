---
title: "Sconto carrello basato sul valore del carrello - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Sconto carrello basato sul valore del carrello' di MyPresta.eu."
sidebar:
  label: "Sconto carrello basato sul valore del carrello - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Cart discount based on cart value su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/cart-discount-based-on-cart-value.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/cart-discount-based-on-cart-value/)
>
> ---


# Sconto carrello basato sul valore del carrello

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Sono richieste estensioni PHP standard (cURL, JSON, OpenSSL), che sono tipicamente disponibili sulla maggior parte degli ambienti di hosting compatibili con PrestaShop.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata principale dove controlli il comportamento generale e le impostazioni del tuo programma di sconti sul carrello.

-   **Attiva programma**

    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare l'intero programma di sconti sul carrello.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* Il modulo controllerà attivamente i valori del carrello e applicherà gli sconti secondo le regole definite.
        -   *Quando disabilitato (NO):* Nessuno sconto sul carrello verrà applicato e nessun messaggio correlato apparirà sulla pagina del carrello, indipendentemente dalle altre impostazioni.
    -   **Valore consigliato:** SÌ (una volta configurate le regole di sconto).
    -   **Scenario / esempio del commerciante:** Potresti disabilitarlo temporaneamente durante una vendita speciale in cui si applicano altre regole di sconto, o se hai bisogno di eseguire manutenzione.
-   **Disabilita programma sconti carrello per gruppi di clienti selezionati**

    -   **Cosa fa questa impostazione:** Ti permette di impedire a specifici gruppi di clienti (es. grossisti, VIP o ospiti) di ricevere questi sconti basati sul valore del carrello.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando selezionato:* I clienti appartenenti ai gruppi scelti non riceveranno alcuno sconto da questo modulo, anche se il valore del loro carrello soddisfa i criteri.
        -   *Quando non selezionato:* Tutti i gruppi di clienti sono idonei per gli sconti.
    -   **Valore consigliato:** Dipende dalla tua strategia aziendale. Se hai prezzi speciali per determinati gruppi, potresti escluderli.
    -   **Scenario / esempio del commerciante:** Hai un gruppo di clienti "Grossisti" che riceve già prezzi speciali. Selezioneresti questo gruppo qui per evitare di accumulare sconti.
-   **Tipo di prezzo**

    -   **Cosa fa questa impostazione:** Determina se il valore del carrello per il calcolo dello sconto deve includere o escludere le tasse.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su "Prezzo con IVA":* Lo sconto viene calcolato in base al valore totale del carrello *inclusivo* di IVA/tasse.
        -   *Quando impostato su "Prezzo senza IVA":* Lo sconto viene calcolato in base al valore totale del carrello *esclusivo* di IVA/tasse.
    -   **Valore consigliato:** "Prezzo con IVA" per la maggior parte dei negozi B2C, "Prezzo senza IVA" per i negozi B2B o se il tuo prezzo primario è al netto delle tasse.
    -   **Scenario / esempio del commerciante:** Se i tuoi clienti sono abituati a vedere i prezzi con IVA, calcolare lo sconto in base al "Prezzo con IVA" risulterà più naturale e trasparente per loro.
-   **Escludi prodotti con sconto**

    -   **Cosa fa questa impostazione:** Controlla se i prodotti già in saldo o con un prezzo specifico (es. da una regola di catalogo) devono contribuire al valore del carrello per il calcolo dello sconto.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* I prodotti già scontati verranno ignorati nel calcolo del valore totale del carrello per lo sconto a livelli.
        -   *Quando disabilitato (NO):* Tutti i prodotti nel carrello, indipendentemente dal fatto che siano già scontati, contribuiranno al valore del carrello per lo sconto a livelli.
    -   **Valore consigliato:** SÌ, per prevenire "doppi sconti" e proteggere i tuoi margini.
    -   **Scenario / esempio del commerciante:** Stai facendo una vendita del 20% su specifiche magliette. Se un cliente acquista una maglietta e altri articoli, e questa impostazione è SÌ, il valore della maglietta non lo aiuterà a raggiungere il livello di sconto successivo del carrello.
-   **Escludi prodotti dal produttore**

    -   **Cosa fa questa impostazione:** Ti permette di specificare determinati produttori i cui prodotti non devono contribuire al valore del carrello quando si calcola lo sconto a livelli.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando selezionato:* I prodotti dei produttori scelti verranno ignorati nel calcolo del valore totale del carrello per lo sconto a livelli.
        -   *Quando non selezionato:* Tutti i prodotti, indipendentemente dal produttore, contribuiscono al valore del carrello.
    -   **Valore consigliato:** Lasciare vuoto a meno che tu non abbia accordi specifici o prodotti a basso margine da determinati produttori.
    -   **Scenario / esempio del commerciante:** Vendi prodotti di un marchio premium che ha regole di prezzo rigide e non può essere incluso negli sconti generali. Selezioneresti quel produttore qui.
-   **Escludi prodotti scontati dal valore dello sconto**

    -   **Cosa fa questa impostazione:** Determina se il *valore* dei prodotti già scontati deve essere escluso dall'*importo* dello sconto sul carrello applicato. Questa è una distinzione sottile ma importante rispetto a "Escludi prodotti con sconto".
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* Se viene applicato uno sconto del 5% sul carrello, e alcuni prodotti nel carrello sono già scontati, il 5% si applicherà solo agli articoli non scontati.
        -   *Quando disabilitato (NO):* Lo sconto del 5% sul carrello si applicherà all'*intero* valore del carrello, anche se alcuni articoli al suo interno sono già scontati.
    -   **Valore consigliato:** SÌ, per proteggere i margini e prevenire sconti eccessivi su articoli già ridotti.
    -   **Scenario / esempio del commerciante:** Un cliente ha un carrello da €100, con un articolo da €20 già scontato del 10%. Se si applica uno sconto del 5% sul carrello e questa impostazione è SÌ, il 5% si applicherà solo agli articoli non scontati del valore di €80.
-   **Escludi carrello con codice voucher**

    -   **Cosa fa questa impostazione:** Impedisce che gli sconti basati sul valore del carrello del modulo vengano applicati se un cliente ha già inserito un codice voucher (coupon) separato nel suo carrello.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* Se un cliente utilizza un codice voucher, lo sconto automatico sul carrello del modulo non verrà applicato, evitando sconti cumulativi.
        -   *Quando disabilitato (NO):* Lo sconto del modulo si applicherà anche se è presente un codice voucher, potenzialmente cumulando gli sconti.
    -   **Valore consigliato:** SÌ, per prevenire sconti eccessivi e mantenere il controllo sulle tue promozioni.
    -   **Scenario / esempio del commerciante:** Stai conducendo una campagna email speciale con un voucher unico del 10% di sconto. Vuoi che i clienti scelgano tra quel voucher o lo sconto a livelli sul carrello, non entrambi.
-   **Mostra informazioni programma sconti sulla pagina del carrello**

    -   **Cosa fa questa impostazione:** Controlla se i messaggi sul programma di sconti sul carrello (es. "Spendi X in più per Y% di sconto!") vengono visualizzati sulla pagina del carrello.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* Messaggi informativi appariranno sulla pagina del carrello, guidando i clienti verso una spesa maggiore.
        -   *Quando disabilitato (NO):* Nessun messaggio relativo agli sconti di questo modulo verrà mostrato sulla pagina del carrello. Lo sconto si applicherà comunque se attivo, ma senza la messaggistica promozionale.
    -   **Valore consigliato:** SÌ, poiché questa è una caratteristica chiave per incoraggiare un AOV più elevato.
    -   **Scenario / esempio del commerciante:** Vuoi incoraggiare attivamente i clienti a raggiungere il livello di sconto successivo. Abilitando questa opzione mostrerai loro esattamente quanto devono spendere in più.
-   **Contenuti personalizzati aggiuntivi**

    -   **Cosa fa questa impostazione:** Ti permette di aggiungere testo personalizzato, HTML o persino immagini che verranno visualizzati insieme alle informazioni del programma di sconti sulla pagina del carrello. Questo contenuto può essere tradotto in diverse lingue.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando viene inserito del contenuto:* Il tuo messaggio personalizzato apparirà sulla pagina del carrello, migliorando il messaggio promozionale.
        -   *Quando lasciato vuoto:* Nessun contenuto personalizzato aggiuntivo verrà visualizzato.
    -   **Valore consigliato:** Usalo per aggiungere un invito all'azione convincente o spiegare i vantaggi del programma di sconti.
    -   **Scenario / esempio del commerciante:** Potresti aggiungere "Non perdere i risparmi! Più acquisti, più risparmi!" o un link ai tuoi termini e condizioni per gli sconti.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### 2.2.1 AdminCdisListController (Back Office > Moduli > Sconto carrello basato sul valore del carrello > pulsante "Configura", quindi naviga alla scheda "Sconti" o simile)

Questa schermata è dove definisci e gestisci le tue regole di sconto effettive. Di solito si accede dopo aver cliccato su "Configura" sul modulo e poi navigando a una scheda o un link specifico per "Sconti" o "Regole".

-   **Nome schermata e posizione nel menu:** Questa schermata è solitamente accessibile tramite una scheda o un link dedicato all'interno della pagina di configurazione principale del modulo, spesso etichettata "Sconti", "Regole" o "Gestisci Sconti".
-   **Azioni e impostazioni disponibili:**
    -   **Griglia / Vista di gestione:** Vedrai una tabella che elenca tutte le tue regole di sconto definite. Ogni riga rappresenta una regola con colonne come:
        -   **Valore minimo del carrello:** La soglia che il carrello deve raggiungere.
        -   **Tipo di sconto:** Se è una percentuale o un importo fisso.
        -   **Valore dello sconto:** La percentuale (es. 5) o l'importo fisso (es. 10.00).
        -   **Attivo:** Se la regola è attualmente abilitata.
        -   **Azioni:** Pulsanti per "Modifica" o "Elimina" singole regole.
    -   **Pulsante Aggiungi nuova regola:** Un pulsante (es. "Aggiungi nuova regola di sconto") per creare una nuova condizione di sconto. Cliccandolo, si aprirà un modulo per definire una nuova regola.
    -   **Modulo Modifica regola:** Quando aggiungi o modifichi una regola, troverai tipicamente campi per:
        -   **Valore minimo del carrello:** (es. 500) - Il valore totale minimo del carrello affinché questo sconto si applichi.
        -   **Tipo di sconto:** (es. Percentuale, Importo fisso) - Scegli come viene calcolato lo sconto.
        -   **Valore dello sconto:** (es. 5 per 5%, o 10.00 per €10) - Lo sconto effettivo da applicare.
        -   **Attivo:** (Interruttore Sì/No) - Per abilitare o disabilitare questa specifica regola senza eliminarla.
        -   **Priorità:** (es. 1, 2, 3) - Se più regole potrebbero applicarsi (es. il valore del carrello è €1000, e hai regole per €500 e €1000), la priorità determina quale ha la precedenza. Numeri più bassi di solito significano priorità più alta.
-   **Effetto delle modifiche:**
    -   **Aggiunta di una regola:** Una nuova condizione di sconto diventa attiva nel tuo negozio, applicandosi automaticamente ai carrelli dei clienti che soddisfano i criteri.
    -   **Modifica di una regola:** Modifica una condizione di sconto esistente, cambiandone la soglia, il valore o lo stato attivo.
    -   **Eliminazione di una regola:** Rimuove permanentemente una condizione di sconto, e non verrà più applicata ai carrelli.
    -   **Attivazione/Disattivazione:** Attiva o disattiva la disponibilità di una specifica regola di sconto senza rimuoverne la configurazione.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Inizia pianificando i tuoi livelli di sconto (es. €250 per 2%, €500 per 5%, €1000 per 10%).
    2.  Clicca su "Aggiungi nuova regola di sconto" per ogni livello.
    3.  Inserisci il "Valore minimo del carrello", seleziona il "Tipo di sconto" (solitamente Percentuale) e inserisci il "Valore dello sconto".
    4.  Assicurati che "Attivo" sia impostato su SÌ.
    5.  Imposta le priorità se hai intervalli sovrapposti (es. una regola per >€500 e un'altra per >€1000, assicurati che la regola per €1000 abbia una priorità più alta se vuoi che si applichi invece della regola per €500 quando il carrello supera €1000). Il modulo di solito gestisce questo applicando lo sconto di valore più alto per il livello più alto raggiunto.
    6.  Rivedi regolarmente le tue regole di sconto, specialmente prima di grandi vendite o periodi promozionali, per assicurarti che siano allineate con la tua attuale strategia di marketing.

#### 2.2.2 index.php (cartdiscount/controllers/admin/index.php)

Questo file è un segnaposto e tipicamente contiene solo un'istruzione di sicurezza `die()` per impedire l'accesso diretto alla directory. Non rappresenta una schermata configurabile o una vista di gestione delle entità per il commerciante.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Pagina di configurazione del modulo** | Attiva programma | SÌ | Interruttore principale per l'intero programma di sconti. |
| | Disabilita programma sconti carrello per gruppi di clienti selezionati | (Nessuno selezionato) | Esclude i gruppi di clienti scelti dal ricevere sconti. |
| | Tipo di prezzo | Prezzo con IVA | Determina se il valore del carrello include o esclude l'IVA per il calcolo. |
| | Escludi prodotti con sconto | SÌ | Impedisce ai prodotti già scontati di contribuire alla soglia del valore del carrello. |
| | Escludi prodotti dal produttore | (Nessuno selezionato) | Ignora i prodotti dei produttori selezionati per il calcolo del valore del carrello. |
| | Escludi prodotti scontati dal valore dello sconto | SÌ | Assicura che lo sconto sul carrello si applichi solo agli articoli non scontati nel carrello. |
| | Escludi carrello con codice voucher | SÌ | Impedisce gli sconti del modulo se viene utilizzato un codice voucher separato. |
| | Mostra informazioni programma sconti sulla pagina del carrello | SÌ | Visualizza messaggi promozionali sulla pagina del carrello. |
| | Contenuti personalizzati aggiuntivi | (Vuoto) | Aggiunge testo/HTML personalizzato alle informazioni sullo sconto della pagina del carrello. |
| **AdminCdisListController (Elenco sconti)** | Valore minimo del carrello | (Definito dal commerciante) | La soglia totale del carrello per attivare uno sconto. |
| | Tipo di sconto | Percentuale | Come viene calcolato lo sconto (percentuale o importo fisso). |
| | Valore dello sconto | (Definito dal commerciante) | L'importo effettivo dello sconto (es. 5 per 5%, 10.00 per €10). |
| | Attivo | SÌ | Abilita o disabilita una specifica regola di sconto. |
| | Priorità | (Auto/Definita dal commerciante) | Determina quale regola si applica se vengono soddisfatte più soglie. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei sconti non vengono applicati, anche se ho impostato le regole. Cosa c'è che non va?**
R:

1.  **Controlla "Attiva programma":** Assicurati che l'interruttore principale nella pagina di configurazione del modulo sia impostato su SÌ.
2.  **Controlla lo stato "Attivo" della singola regola:** Assicurati che ogni regola di sconto che hai creato in AdminCdisListController sia anch'essa impostata su SÌ.
3.  **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). PrestaShop spesso memorizza nella cache le impostazioni dei moduli.
4.  **Controlla i Gruppi Clienti:** Verifica che il gruppo di clienti con cui stai testando non sia escluso sotto "Disabilita programma sconti carrello per gruppi di clienti selezionati".
5.  **Soglia Valore Carrello:** Ricontrolla che il valore del tuo carrello soddisfi effettivamente il "Valore minimo del carrello" affinché lo sconto si attivi.

**D: Lo sconto viene applicato, ma il messaggio sulla pagina del carrello non compare.**
R:

1.  **Controlla "Mostra informazioni programma sconti sulla pagina del carrello":** Assicurati che questa impostazione sia abilitata (SÌ) nella pagina di configurazione principale del modulo.
2.  **Compatibilità del tema:** Il tuo tema personalizzato potrebbe sovrascrivere la visualizzazione standard del carrello. Controlla se l'hook `displayShoppingCartFooter` è correttamente implementato nel file `shopping-cart.tpl` del tuo tema o file equivalente. In caso contrario, uno sviluppatore potrebbe dover aggiungere manualmente l'hook.
3.  **Svuota la cache:** Svuota sempre la cache di PrestaShop dopo aver apportato modifiche alla configurazione.

**D: Il valore dello sconto sembra errato, o non si applica a tutti gli articoli.**
R:

1.  **"Tipo di prezzo":** Verifica se hai selezionato "Prezzo con IVA" o "Prezzo senza IVA" per il calcolo.
2.  **"Escludi prodotti con sconto":** Se abilitato, i prodotti già in saldo non contribuiranno alla soglia.
3.  **"Escludi prodotti scontati dal valore dello sconto":** Se abilitato, lo sconto percentuale si applicherà solo agli articoli non scontati nel carrello. Rivedi queste impostazioni per assicurarti che corrispondano al comportamento desiderato.
4.  **"Escludi carrello con codice voucher":** Se un cliente ha applicato un voucher separato, e questa impostazione è SÌ, lo sconto del modulo non verrà applicato.

**D: Come posso tradurre il contenuto personalizzato che ho aggiunto?**
R:

1.  Vai su **Internazionale > Traduzioni** nel tuo Back Office di PrestaShop.
2.  Seleziona "Traduzioni dei moduli installati", scegli il tuo tema e poi seleziona la lingua che vuoi tradurre.
3.  Trova il modulo "Sconto carrello basato sul valore del carrello". Dovresti vedere i campi per tradurre i "Contenuti personalizzati aggiuntivi" per ogni lingua.

**D: Vedo un errore dopo aver aggiornato PrestaShop o un altro modulo.**
R:

1.  **Controlla la versione del modulo:** Assicurati di utilizzare l'ultima versione del modulo "Sconto carrello basato sul valore del carrello" compatibile con la tua versione di PrestaShop. Scarica il file ZIP corretto da MyPresta.eu.
2.  **Compatibilità PHP:** Verifica che la versione PHP del tuo server rientri nell'intervallo supportato dal modulo (PHP 5.6 - 8.5).
3.  **Disabilita gli override (per gli sviluppatori):** Se sospetti un conflitto, disabilita temporaneamente gli override in **Parametri avanzati > Prestazioni** (imposta "Disabilita moduli non PrestaShop" su SÌ, quindi svuota la cache). Se il problema si risolve, è probabile che si tratti di un conflitto di override. Riabilita e consulta uno sviluppatore.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Sconto carrello basato sul valore del carrello" estende le funzionalità principali di PrestaShop `Cart` e `CartRule` tramite override per applicare dinamicamente gli sconti. Sfrutta un Controller Admin dedicato (`AdminCdisListController`) per la gestione delle regole di sconto memorizzate in una tabella di database personalizzata. L'integrazione front-office è ottenuta principalmente tramite hook per visualizzare messaggi informativi e garantire l'applicazione dello sconto durante i processi di carrello e checkout.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Nessuno esplicitamente definito nella directory `controllers/front/` del modulo. La logica front-office per l'applicazione dello sconto è gestita tramite override e hook.
-   **Controller Admin Back-Office**:

    -   `cartdiscount/controllers/admin/AdminCdisList.php`
        -   **Nome classe e classe genitore:** `AdminCdisListController` estende `ModuleAdminController`.
        -   **Nome scheda ed entità gestita:** Gestisce l'elenco e i moduli per le entità `Cdis` (Sconto Carrello). Questo controller fornisce l'interfaccia per creare, modificare ed eliminare le regole di sconto a livelli. Definisce la vista elenco (`renderList()`) e la vista modulo (`renderForm()`) per le regole di sconto.
    -   `cartdiscount/controllers/admin/index.php`
        -   **Nome classe e classe genitore:** N/A (file di sicurezza).
        -   **Responsabilità:** Contiene un'istruzione `die('No direct script access allowed');` per impedire l'accesso diretto alla directory, una pratica di sicurezza standard di PrestaShop.

### 4.3 Classi e modelli principali (`classes/`)

Il modulo si basa fortemente sugli override per iniettare la sua logica nelle classi principali di PrestaShop.

-   `cartdiscount/override/classes/Cart.php`
    -   **Classe originale:** `Cart`
    -   **Responsabilità:** Questo override è cruciale. Estende la classe `Cart` per modificare il modo in cui vengono calcolati i totali del carrello, in particolare per applicare gli sconti dinamici in base alle regole del modulo. Probabilmente intercetta metodi come `getProducts()`, `getProductsTotal()` o `getPackageShippingCost()` per regolare i prezzi prima che vengano finalizzati. Contiene anche la logica per determinare se uno sconto deve essere applicato in base al valore corrente del carrello e alle regole configurate.
-   `cartdiscount/override/classes/CartRule.php`
    -   **Classe originale:** `CartRule`
    -   **Responsabilità:** Questo override probabilmente estende la classe `CartRule` per consentire al modulo di creare e gestire i propri oggetti `CartRule` interni in modo dinamico. Quando il modulo applica uno sconto, ciò avviene spesso creando un `CartRule` temporaneo o specifico che riflette lo sconto calcolato, che viene quindi applicato al carrello. Questo override garantisce compatibilità e corretta gestione di queste regole generate dinamicamente.
-   `cartdiscount/override/classes/index.php`
    -   **Responsabilità:** File di sicurezza, `die('No direct script access allowed');`.
-   `cartdiscount/override/classes/order/index.php`
    -   **Responsabilità:** File di sicurezza, `die('No direct script access allowed');`.
-   `cartdiscount/override/classes/order/Order.php`
    -   **Classe originale:** `Order`
    -   **Responsabilità:** Questo override assicura che gli sconti applicati dal modulo vengano correttamente trasferiti e memorizzati quando viene effettuato un ordine. Potrebbe modificare i metodi relativi alla creazione dell'ordine o al calcolo del totale per riflettere le regole del carrello applicate.

### 4.4 Risorse JavaScript (`views/js/`)

-   `cartdiscount/views/admin/js/cdis.js`
    -   **Ambito:** Back-office.
    -   **Responsabilità:** Questo script probabilmente gestisce le interazioni lato client per `AdminCdisListController`. Questo potrebbe includere:
        -   Chiamate AJAX per salvare/aggiornare le regole di sconto.
        -   Validazione del modulo per il modulo "Aggiungi/Modifica regola di sconto".
        -   Aggiornamenti dinamici dell'interfaccia utente o interazioni all'interno della griglia di gestione delle regole di sconto.
        -   Potenzialmente, la gestione di "Escludi prodotti dal produttore" o altri campi di selezione dinamici.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `cartdiscount/views/admin/css/cdis.css`
    -   **Ambito:** Styling del modulo di amministrazione del back-office.
    -   **Responsabilità:** Fornisce uno styling specifico per l'interfaccia `AdminCdisListController`, garantendo che i moduli e gli elenchi di gestione delle regole di sconto siano ben presentati e coerenti con l'interfaccia utente del back-office di PrestaShop.
    -   **Selettori di classe CSS chiave:** Gli sviluppatori possono ispezionare l'HTML generato da `AdminCdisListController` per trovare classi specifiche (es. `.cdis-form`, `.cdis-list-table`) da sovrascrivere se è necessario uno styling amministrativo personalizzato.
-   `cartdiscount/views/css/cartdiscount.css`
    -   **Ambito:** Styling del cliente front-office.
    -   **Responsabilità:** Stila i messaggi informativi visualizzati sulla pagina del carrello (es. "Spendi X in più per Y% di sconto!").
    -   **Selettori di classe CSS chiave:** Probabilmente si rivolge agli elementi all'interno del template `myDiscount.tpl` (es. `.cartdiscount-info`, `.cartdiscount-message`, `.cartdiscount-progress`). Gli sviluppatori possono sovrascrivere queste classi nel file `custom.css` del loro tema o equivalente per adattarle al branding del negozio.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**:
    -   `cartdiscount/views/templates/hook/myDiscount.tpl`
        -   **Hook:** `displayShoppingCartFooter` (e potenzialmente altri come `displayHeader` per l'inclusione di JS/CSS).
        -   **Blocco visivo:** Questo template è responsabile del rendering dei messaggi dinamici sulla pagina del carrello. Visualizza informazioni sul valore attuale del carrello, lo sconto applicato e quanto il cliente deve spendere in più per raggiungere il livello di sconto successivo. Rende anche i "Contenuti personalizzati aggiuntivi" se configurati.
-   **Template admin (`views/templates/admin/`)**:
    -   `AdminCdisListController` utilizzerà i template admin standard di PrestaShop per il rendering delle sue viste elenco e modulo, solitamente trovati in `_partials` o `helpers/list/list_header.tpl`, `helpers/form/form.tpl`, ecc., che fanno parte del core di PrestaShop. Il modulo stesso potrebbe non avere file `.tpl` personalizzati in `views/templates/admin/` ma si basa sul controller per passare i dati agli helper principali.
-   **Template front-office (`views/templates/front/`)**: Nessuno esplicitamente definito.
-   `cartdiscount/lib/searchTool/views/scripts.tpl`
    -   **Ambito:** Probabilmente utilizzato per includere risorse JavaScript o CSS per un componente strumento di ricerca all'interno della configurazione del modulo o di una funzionalità specifica. Il suo utilizzo esatto dipenderebbe dall'implementazione dello strumento di ricerca (es. per selezionare i produttori da escludere).

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   `ps_cdis`: Questa tabella personalizzata memorizza le regole di sconto effettive definite dal commerciante (valore minimo del carrello, tipo di sconto, valore dello sconto, stato attivo, priorità).
    -   `ps_configuration`: Le impostazioni del modulo come `CDIS_ACTIVE`, `CDIS_PRICETYPE`, `CDIS_GROUPSNOT`, `CDIS_EXMANUFACTURER`, `CDIS_SHOWINFO_CART`, `CDIS_EXSPECIFIC`, `CDIS_ORDERCOUPON`, `cdis_contents` (per contenuti personalizzati) e `mypresta_updates` sono memorizzate qui.
-   **Tabella degli hook registrati**:

| Nome dell'Hook | Tempistica di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina front-office. | Utilizzato per includere CSS (`cartdiscount.css`) e potenzialmente JavaScript front-office del modulo, garantendo che stili e script siano caricati per la pagina del carrello. |
| `ActionAdminControllerSetMedia` | Quando un Controller Admin viene inizializzato e i suoi media (JS/CSS) vengono impostati. | Utilizzato per includere CSS (`cdis.css`) e JavaScript (`cdis.js`) back-office del modulo per `AdminCdisListController`, garantendo una corretta stilizzazione e funzionalità dell'interfaccia di amministrazione. |
| `displayShoppingCartFooter` | In fondo alla pagina di riepilogo del carrello. | Rende il template `myDiscount.tpl`, visualizzando messaggi informativi sul programma di sconti, i risparmi attuali e i prossimi livelli di sconto al cliente. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Sconto carrello basato sul valore del carrello", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda possiate avere riguardo alla funzionalità e compatibilità del modulo.
