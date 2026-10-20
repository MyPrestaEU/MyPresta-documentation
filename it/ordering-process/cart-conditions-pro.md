---
title: "Cart conditions pro - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Cart conditions pro di MyPresta.eu."
sidebar:
  label: "Cart conditions pro - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Cart conditions pro su MyPresta.eu](https://mypresta.eu/modules/ordering-process/cart-conditions-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/cart-conditions-pro/)
>
> ---


# Cart conditions pro

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e sono sufficienti per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Cart conditions pro)

Questa è la schermata di configurazione principale del modulo, dove imposti i comportamenti globali e accedi alle aree di gestione delle condizioni specifiche.

-   **Cosa fa questa impostazione:** Controlla il comportamento generale del modulo e fornisce collegamenti rapidi per gestire le tue condizioni.
-   **Effetto della modifica di questa impostazione:** Determina quanto ampiamente si applicano le condizioni e come vengono gestiti alcuni casi limite.

#### Impostazioni generali

1.  **Escludi clienti dalle condizioni**

    -   **Cosa fa questa impostazione:** Ti consente di specificare determinati gruppi di clienti o singoli clienti che saranno esenti da qualsiasi condizione del carrello che imposti.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (e clienti/gruppi selezionati):* I clienti/gruppi selezionati potranno sempre procedere al checkout, indipendentemente dal fatto che il loro carrello soddisfi le condizioni.
        -   *Quando disabilitato (o nessun cliente/gruppo selezionato):* Tutti i clienti saranno soggetti alle condizioni del carrello.
    -   **Valore consigliato:** "Disattivato" per impostazione predefinita, a meno che tu non abbia clienti B2B specifici o VIP che desideri esentare.
    -   **Scenario / esempio del commerciante:** Hai un gruppo di clienti all'ingrosso che riceve sempre un trattamento speciale e non dovrebbe essere limitato dai valori minimi d'ordine.
2.  **Escludi prodotti dalle condizioni**

    -   **Cosa fa questa impostazione:** Ti consente di specificare determinati prodotti che non verranno conteggiati o influenzati da alcuna condizione del carrello. Questo è utile per regali gratuiti, campioni o articoli promozionali specifici.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (e prodotti selezionati):* I prodotti selezionati verranno ignorati durante la valutazione delle condizioni del carrello. Ad esempio, se hai una condizione "minimo 3 articoli" e un cliente ha 2 articoli regolari + 1 articolo escluso, la condizione potrebbe comunque fallire.
        -   *Quando disabilitato (o nessun prodotto selezionato):* Tutti i prodotti nel carrello verranno considerati durante la valutazione delle condizioni.
    -   **Valore consigliato:** "Disattivato" per impostazione predefinita. Abilita solo se hai prodotti specifici che dovrebbero essere esenti dalle condizioni.
    -   **Scenario / esempio del commerciante:** Offri un prodotto campione gratuito con ogni ordine. Non vuoi che questo campione venga conteggiato per una condizione di quantità minima di prodotto.
3.  **Blocca l'ordine di prodotti con data di disponibilità variabile**

    -   **Cosa fa questa impostazione:** Questa opzione si rivolge specificamente ai prodotti che hanno date di disponibilità diverse (ad esempio, articoli in pre-ordine con date di rilascio scaglionate). Se abilitata, impedisce ai clienti di ordinare un mix di prodotti immediatamente disponibili e prodotti disponibili in futuro nello stesso carrello.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando "Attivato":* Se il carrello di un cliente contiene prodotti con date di disponibilità diverse, il checkout verrà bloccato. Dovrebbero effettuare ordini separati per gli articoli con disponibilità diversa.
        -   *Quando "Disattivato":* I clienti possono ordinare prodotti con varie date di disponibilità in un unico carrello.
    -   **Valore consigliato:** "Disattivato" a meno che tu non abbia ragioni logistiche specifiche per separare gli ordini in base alla disponibilità.
    -   **Scenario / esempio del commerciante:** Vendi sia articoli in magazzino che articoli in pre-ordine. Per semplificare la spedizione ed evitare di trattenere gli ordini, desideri che i clienti effettuino ordini separati per gli articoli in pre-ordine.

#### Collegamenti per la gestione delle condizioni

Sotto le impostazioni generali, troverai i collegamenti per gestire diversi tipi di condizioni. Questi collegamenti ti porteranno a schermate di amministrazione dedicate.

-   **Gestisci condizioni (Generale):** Qui definisci condizioni ampie basate su associazioni di prodotti, categorie o altre regole generali.
-   **Gestisci condizioni per paese:** Definisci condizioni che si applicano solo ai clienti di paesi specifici.
-   **Gestisci condizioni di quantità:** Imposta quantità minime o massime di prodotti/categorie richieste nel carrello.
-   **Gestisci condizioni di valore:** Imposta valori totali minimi o massimi del carrello richiesti.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### 2.2.1 AdminCartConditionController (Back Office > Moduli > Cart conditions pro > Gestisci condizioni)

Questa schermata ti consente di definire condizioni generali, spesso basate su associazioni di prodotti o categorie.

-   **Nome schermata e posizione nel menu:** "Gestisci condizioni" (accessibile dalla pagina di configurazione principale del modulo).
-   **Azioni e impostazioni disponibili:**
    -   **Tabella di elenco:** Visualizza tutte le condizioni generali esistenti con i loro nomi, prodotti/categorie associati e stato.
    -   **Pulsante Aggiungi nuova condizione:** Ti consente di creare una nuova condizione.
        -   **Nome condizione:** Un nome descrittivo per il tuo riferimento interno.
        -   **Prodotti/Categorie:** Seleziona prodotti specifici o intere categorie che devono essere presenti (o non presenti) nel carrello.
        -   **Gruppi di clienti:** Applica questa condizione solo a gruppi di clienti specifici.
        -   **Quantità minima/massima:** Definisci un intervallo per il numero di prodotti/categorie selezionati.
        -   **Valore minimo/massimo:** Definisci un intervallo per il valore totale dei prodotti/categorie selezionati.
        -   **Messaggio:** Il messaggio visualizzato al cliente se la condizione non è soddisfatta.
        -   **Attivo:** Abilita o disabilita la condizione.
    -   **Pulsanti Modifica/Elimina:** Modifica o rimuovi le condizioni esistenti.
-   **Effetto delle modifiche:**
    -   L'aggiunta di una nuova condizione applica immediatamente quella regola ai carrelli dei clienti.
    -   La modifica di una condizione aggiorna i suoi criteri e il messaggio.
    -   L'eliminazione di una condizione rimuove la restrizione.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Rivedi regolarmente le tue condizioni, specialmente dopo aver aggiunto nuovi prodotti, categorie o aver eseguito promozioni, per assicurarti che siano allineate con la tua attuale strategia di vendita.

#### 2.2.2 AdminCartAssociationsConditionController (Back Office > Moduli > Cart conditions pro > Gestisci condizioni > (Condizione specifica) > Associazioni)

Questa schermata viene tipicamente acceduta quando si modifica una condizione generale e consente di specificare quali prodotti o categorie sono *associati* a tale condizione.

-   **Nome schermata e posizione nel menu:** Accessibile modificando una condizione da "Gestisci condizioni".
-   **Azioni e impostazioni disponibili:**
    -   **Cerca e seleziona prodotti/categorie:** Strumenti per trovare e aggiungere prodotti specifici o intere categorie che fanno parte di questa condizione.
    -   **Elenco prodotti/categorie selezionati:** Mostra tutti gli articoli attualmente associati alla condizione.
    -   **Pulsante Rimuovi:** Rimuovi un elemento dall'associazione.
-   **Effetto delle modifiche:** Influisce direttamente su quali prodotti o categorie vengono valutati dalla condizione padre. Ad esempio, se una condizione afferma "Il carrello deve contenere almeno 2 articoli della categoria 'Elettronica'", questa schermata è dove definisci quali prodotti appartengono a quella categoria "Elettronica" per questa specifica condizione.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Quando crei o aggiorni una condizione, assicurati che tutti i prodotti e le categorie pertinenti siano correttamente associati.

#### 2.2.3 AdminCartCountryConditionController (Back Office > Moduli > Cart conditions pro > Gestisci condizioni per paese)

Questa schermata ti consente di definire condizioni specifiche per il paese di spedizione del cliente.

-   **Nome schermata e posizione nel menu:** "Gestisci condizioni per paese" (accessibile dalla pagina di configurazione principale del modulo).
-   **Azioni e impostazioni disponibili:**
    -   **Tabella di elenco:** Visualizza le condizioni esistenti specifiche per paese.
    -   **Pulsante Aggiungi nuova condizione:**
        -   **Paese:** Seleziona il paese di destinazione.
        -   **Quantità minima/massima:** Per tutti i prodotti nel carrello, o prodotti/categorie specifici.
        -   **Valore minimo/massimo:** Per il valore totale del carrello.
        -   **Messaggio:** Il messaggio visualizzato se la condizione non è soddisfatta.
        -   **Attivo:** Abilita o disabilita.
-   **Effetto delle modifiche:** Applica regole specifiche del carrello solo ai clienti il cui indirizzo di spedizione si trova nel paese selezionato.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Utile per negozi internazionali con costi di spedizione, regolamenti doganali o strategie di mercato variabili per paese.

#### 2.2.4 AdminCartQuantityConditionController (Back Office > Moduli > Cart conditions pro > Gestisci condizioni di quantità)

Questa schermata si concentra sulle condizioni relative al numero totale di articoli nel carrello, o alla quantità di articoli/categorie specifici.

-   **Nome schermata e posizione nel menu:** "Gestisci condizioni di quantità" (accessibile dalla pagina di configurazione principale del modulo).
-   **Azioni e impostazioni disponibili:**
    -   **Tabella di elenco:** Mostra tutte le condizioni basate sulla quantità.
    -   **Pulsante Aggiungi nuova condizione:**
        -   **Nome condizione:**
        -   **Quantità totale minima/massima:** Per l'intero carrello.
        -   **Quantità minima/massima di prodotti/categorie specifici:** Seleziona gli articoli e imposta le regole di quantità per essi.
        -   **Gruppi di clienti:** Applica a gruppi specifici.
        -   **Messaggio:**
        -   **Attivo:**
-   **Effetto delle modifiche:** Applica regole basate sul conteggio degli articoli nel carrello, che possono essere utilizzate per incoraggiare acquisti all'ingrosso o gestire l'inventario.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Utilizza questo per promozioni "compra X ottieni Y", quantità minima d'ordine (MOQ) per l'ingrosso, o per assicurarti che i clienti raggiungano una certa soglia per la spedizione gratuita.

#### 2.2.5 AdminCartValueConditionController (Back Office > Moduli > Cart conditions pro > Gestisci condizioni di valore)

Questa schermata serve per impostare condizioni basate sul valore monetario totale del carrello del cliente.

-   **Nome schermata e posizione nel menu:** "Gestisci condizioni di valore" (accessibile dalla pagina di configurazione principale del modulo).
-   **Azioni e impostazioni disponibili:**
    -   **Tabella di elenco:** Visualizza le condizioni esistenti basate sul valore.
    -   **Pulsante Aggiungi nuova condizione:**
        -   **Nome condizione:**
        -   **Valore totale carrello minimo/massimo:** Imposta un intervallo per il valore dell'intero carrello.
        -   **Gruppi di clienti:**
        -   **Messaggio:**
        -   **Attivo:**
-   **Effetto delle modifiche:** Applica regole basate sul valore monetario del carrello, influenzando direttamente il valore medio dell'ordine.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Ideale per impostare un valore minimo d'ordine per la spedizione gratuita, o un valore minimo d'ordine generale per garantire la redditività.

#### 2.2.6 index.php (cartcon/controllers/admin/index.php)

Questo file è una pratica standard di PrestaShop per prevenire l'elenco delle directory e non rappresenta una schermata configurabile. Contiene semplicemente `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../"); exit;` per reindirizzare se qualcuno tenta di accedere direttamente alla directory.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Configurazione modulo** | Escludi clienti dalle condizioni | Off | Esenta clienti/gruppi specifici da tutte le condizioni. |
| | Escludi prodotti dalle condizioni | Off | Esenta prodotti specifici da tutte le condizioni. |
| | Blocca l'ordine di prodotti con data di disponibilità variabile | Off | Impedisce ordini misti di articoli in magazzino e in pre-ordine. |
| **Gestisci condizioni** | Nome condizione | Definito dall'utente | Etichetta interna per la condizione. |
| | Prodotti/Categorie | Definito dall'utente | Seleziona articoli/categorie richiesti o limitati. |
| | Gruppi di clienti | Tutti | Applica la condizione a segmenti di clienti specifici. |
| | Quantità Min/Max | Definito dall'utente | Imposta l'intervallo di quantità per gli articoli/categorie selezionati. |
| | Valore Min/Max | Definito dall'utente | Imposta l'intervallo di valore per gli articoli/categorie selezionati. |
| | Messaggio | Definito dall'utente | Messaggio rivolto al cliente quando la condizione non è soddisfatta. |
| | Attivo | Sì | Abilita/disabilita la condizione. |
| **Gestisci condizioni per paese** | Paese | Definito dall'utente | Target di paesi specifici per le condizioni. |
| | Quantità Min/Max | Definito dall'utente | Intervallo di quantità per i carrelli dal paese selezionato. |
| | Valore Min/Max | Definito dall'utente | Intervallo di valore per i carrelli dal paese selezionato. |
| | Messaggio | Definito dall'utente | Messaggio al cliente per fallimento specifico del paese. |
| | Attivo | Sì | Abilita/disabilita la condizione per paese. |
| **Gestisci condizioni di quantità** | Nome condizione | Definito dall'utente | Etichetta interna per la condizione di quantità. |
| | Quantità totale Min/Max | Definito dall'utente | Intervallo di quantità per l'intero carrello. |
| | Quantità Min/Max di prodotti/categorie specifici | Definito dall'utente | Intervallo di quantità per gli articoli/categorie selezionati. |
| | Gruppi di clienti | Tutti | Applica a segmenti di clienti specifici. |
| | Messaggio | Definito dall'utente | Messaggio al cliente per fallimento di quantità. |
| | Attivo | Sì | Abilita/disabilita la condizione di quantità. |
| **Gestisci condizioni di valore** | Nome condizione | Definito dall'utente | Etichetta interna per la condizione di valore. |
| | Valore totale carrello Min/Max | Definito dall'utente | Intervallo di valore per l'intero carrello. |
| | Gruppi di clienti | Tutti | Applica a segmenti di clienti specifici. |
| | Messaggio | Definito dall'utente | Messaggio al cliente per fallimento di valore. |
| | Attivo | Sì | Abilita/disabilita la condizione di valore. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Le mie condizioni sono impostate, ma non sembrano funzionare nel front office. Cosa c'è che non va?**
**R1:**

-   **Controlla lo stato della condizione:** Assicurati che l'interruttore "Attivo" per ogni condizione che hai impostato sia su "Sì".
-   **Svuota la cache:** PrestaShop spesso memorizza i contenuti nella cache. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti).
-   **Posizione del modulo:** Verifica che il modulo sia agganciato correttamente. Gli hook `displayShoppingCart` e `displayPaymentTop` sono cruciali. Se il tuo tema ha hook personalizzati, potresti aver bisogno dell'assistenza di uno sviluppatore.
-   **Gruppi di clienti:** Ricontrolla se le condizioni sono applicate ai gruppi di clienti corretti e se il tuo cliente di prova appartiene a quel gruppo.
-   **ID prodotto/categoria:** Quando selezioni prodotti o categorie, assicurati di aver scelto quelli corretti. A volte nomi simili possono causare confusione.

**D2: Il messaggio visualizzato ai clienti non è chiaro o non si adatta bene al mio tema.**
**R2:**

-   **Modifica messaggio:** Vai alla condizione specifica (ad esempio, Gestisci condizioni di valore, quindi modifica la condizione) e aggiorna il campo "Messaggio" con un testo più chiaro e utile.
-   **Stile del tema:** L'aspetto visivo (font, colore, dimensione) del messaggio è controllato dal CSS del tuo tema PrestaShop. Se hai bisogno di modificare lo stile, dovrai consultare un web designer o uno sviluppatore per aggiungere regole CSS personalizzate al tuo tema. I file CSS del modulo (`cartcon.css`) forniscono lo stile di base.

**D3: Posso impostare condizioni diverse per lingue/paesi diversi?**
**R3:**

-   **Condizioni specifiche per paese:** Sì, usa la schermata "Gestisci condizioni per paese" per impostare regole che si applicano solo ai clienti di paesi specifici.
-   **Messaggi multilingue:** Quando modifichi una condizione, il campo "Messaggio" di solito ha un selettore di lingua (un'icona a bandiera). Cliccaci sopra per fornire traduzioni per il tuo messaggio in tutte le lingue attive del tuo negozio.

**D4: Voglio escludere un prodotto specifico da TUTTE le condizioni. Come faccio?**
**R4:**

-   Nella pagina di configurazione principale del modulo (Back Office > Moduli > Configura > Cart conditions pro), usa l'impostazione "Escludi prodotti dalle condizioni". Puoi cercare e selezionare i prodotti specifici che desideri esentare.

**D5: Il modulo sta bloccando il checkout, ma non riesco a trovare quale condizione lo stia causando.**
**R5:**

-   **Rivedi tutte le condizioni:** Esamina "Gestisci condizioni", "Gestisci condizioni per paese", "Gestisci condizioni di quantità" e "Gestisci condizioni di valore" una per una. Controlla lo stato "Attivo" di ciascuna e rivedi i loro criteri.
-   **Testa sistematicamente:** Se hai molte condizioni, prova a disabilitarle una per una (o a gruppi) e a testare il carrello finché non identifichi il colpevole. Quindi, riabilita e regola la condizione problematica.
-   **Controlla il gruppo di clienti:** Assicurati che il tuo cliente di prova non faccia parte di un gruppo di clienti escluso.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Cart conditions pro" segue il modello MVC (Model-View-Controller) standard di PrestaShop, estendendo principalmente `Module` per la sua configurazione principale e `AdminController` per le interfacce di gestione dedicate. Sfrutta il sistema di hook di PrestaShop per iniettare logica e visualizzare messaggi in punti critici del front-office (carrello, pagamento) e utilizza `ObjectModel` implicitamente per gestire le sue varie entità di condizione. Il modulo si basa su tabelle di database personalizzate per memorizzare le sue complesse regole di condizione.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

Il modulo non sembra avere controller frontali dedicati nell'inventario fornito. La logica e la visualizzazione del front-office sono probabilmente gestite direttamente tramite il file principale del modulo `cartcon.php` tramite callback degli hook.

#### Controller Admin Back-Office

Tutti i controller admin estendono `ModuleAdminController` (o `AdminController` nelle versioni precedenti di PrestaShop) e sono responsabili della gestione dei vari tipi di condizioni.

-   `cartcon/controllers/admin/AdminCartAssociationsConditionController.php`

    -   **Nome classe:** `AdminCartAssociationsConditionController`
    -   **Classe padre:** `ModuleAdminController`
    -   **Responsabilità:** Gestisce le associazioni (prodotti, categorie) collegate a una specifica condizione generale del carrello. Questo controller fornisce l'interfaccia per la ricerca e la selezione di prodotti/categorie che fanno parte dei criteri di una condizione. Interagisce con la tabella `cartcon_ass`.
-   `cartcon/controllers/admin/AdminCartConditionController.php`

    -   **Nome classe:** `AdminCartConditionController`
    -   **Classe padre:** `ModuleAdminController`
    -   **Responsabilità:** Gestisce le condizioni principali e generali del carrello. Questa è l'interfaccia principale per la creazione, la modifica e l'eliminazione di condizioni basate sulla presenza, quantità o valore di prodotti/categorie. Interagisce con la tabella `cartcon`.
-   `cartcon/controllers/admin/AdminCartCountryConditionController.php`

    -   **Nome classe:** `AdminCartCountryConditionController`
    -   **Classe padre:** `ModuleAdminController`
    -   **Responsabilità:** Gestisce le condizioni del carrello specificamente legate ai paesi dei clienti. Consente di definire regole che si applicano solo quando il paese di spedizione del cliente corrisponde a un paese specificato. Interagisce con la tabella `cartcon_country`.
-   `cartcon/controllers/admin/AdminCartQuantityConditionController.php`

    -   **Nome classe:** `AdminCartQuantityConditionController`
    -   **Classe padre:** `ModuleAdminController`
    -   **Responsabilità:** Gestisce le condizioni basate sulla quantità totale di articoli nel carrello o sulla quantità di prodotti/categorie specifici. Interagisce con la tabella `cartcon_quantity`.
-   `cartcon/controllers/admin/AdminCartValueConditionController.php`

    -   **Nome classe:** `AdminCartValueConditionController`
    -   **Classe padre:** `ModuleAdminController`
    -   **Responsabilità:** Gestisce le condizioni basate sul valore monetario totale del carrello. Interagisce con la tabella `cartcon_value`.
-   `cartcon/controllers/admin/index.php`

    -   **Responsabilità:** File di sicurezza standard di PrestaShop per prevenire l'elenco delle directory. Reindirizza alla directory padre.

### 4.3 Classi e modelli principali (`classes/`)

L'inventario fornito non elenca file espliciti in una directory `classes/`. Ciò suggerisce che la logica principale del modulo e le definizioni di `ObjectModel` (se presenti) sono incorporate nel file principale `cartcon.php` o nei file del controller admin stessi, il che è un modello comune per moduli più semplici o versioni precedenti di PrestaShop. Se vengono utilizzati `ObjectModel`, i loro array `$definition` si troverebbero all'interno del rispettivo controller o della classe del modulo principale.

### 4.4 Risorse JavaScript (`views/js/`)

-   `cartcon/lib/searchTool/views/js/autocomplete.js`

    -   **Ambito:** Back-office.
    -   **Responsabilità:** Fornisce la funzionalità di completamento automatico per la ricerca di prodotti, categorie o clienti all'interno dei moduli di amministrazione (ad esempio, durante l'impostazione di esclusioni o associazioni di condizioni). Probabilmente si lega ai campi di input, invia richieste AJAX a un endpoint di ricerca e visualizza suggerimenti.
-   `cartcon/views/js/cartcon.js`

    -   **Ambito:** Front-office e potenzialmente Back-office.
    -   **Responsabilità:**
        -   **Front-office:** Gestisce la visualizzazione dinamica dei messaggi delle condizioni del carrello, disabilitando/abilitando il pulsante "Procedi al checkout" in base alle risposte AJAX dal server relative alla validità del carrello. Potrebbe ascoltare gli aggiornamenti del carrello (`prestashop.on('updateCart', ...)` o eventi simili) per rivalutare le condizioni.
        -   **Back-office:** Potrebbe contenere la logica per la convalida dei moduli, la visibilità dinamica dei campi o altri miglioramenti dell'interfaccia utente specifici per le pagine di configurazione del modulo.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `cartcon/lib/searchTool/views/css/autocomplete.css`

    -   **Ambito:** Back-office.
    -   **Responsabilità:** Stila i menu a discesa dei suggerimenti di completamento automatico e i campi di input di ricerca utilizzati nei moduli di amministrazione, garantendo un'esperienza di ricerca coerente e user-friendly.
-   `cartcon/views/css/cartcon.css`

    -   **Ambito:** Front-office e Back-office.
    -   **Responsabilità:**
        -   **Front-office:** Stila i messaggi di notifica visualizzati sulla pagina del carrello, sulla pagina di pagamento o sulla pagina del prodotto quando le condizioni non sono soddisfatte. Definisce l'aspetto delle caselle di avviso, del testo e potenzialmente dello stato disabilitato del pulsante di checkout.
        -   **Back-office:** Fornisce lo stile per i moduli di configurazione del modulo e le tabelle di elenco, assicurando che si integrino bene con il tema del back office di PrestaShop.
    -   **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere:** Cerca classi come `.cartcon-alert`, `.cartcon-message`, `.cartcon-disabled-button` o simili all'interno di questo file per mirare e personalizzare l'output del front-office del modulo.

### 4.6 Struttura del template Smarty (`views/templates/`)

#### Template degli hook (`views/templates/hook/`)

La logica di visualizzazione del front-office del modulo è probabilmente incorporata direttamente nei metodi hook del file principale `cartcon.php`, che poi renderizzano questi template.

-   `cartcon/views/templates/front/displayShoppingCart.tpl`

    -   **Renderizzato nell'hook:** `displayShoppingCart`
    -   **Scopo:** Visualizza i messaggi delle condizioni del carrello e potenzialmente disabilita il pulsante di checkout nella pagina principale del carrello se le condizioni non sono soddisfatte. Riceve variabili dal metodo `hookDisplayShoppingCart` del modulo, indicando la validità del carrello e il messaggio da visualizzare.
-   `cartcon/views/templates/front/displayShoppingCartEmpty.tpl`

    -   **Renderizzato nell'hook:** Potenzialmente `displayShoppingCart` o un hook correlato quando il carrello è vuoto.
    -   **Scopo:** Fornisce un template specifico per la visualizzazione di messaggi o contenuti alternativi quando il carrello è vuoto, potenzialmente correlati ai requisiti minimi d'ordine.
-   `cartcon/views/templates/front/productActions.tpl`

    -   **Renderizzato nell'hook:** `displayProductActions` (tipicamente vicino al pulsante "Aggiungi al carrello" nella pagina del prodotto).
    -   **Scopo:** Può essere utilizzato per visualizzare suggerimenti o avvisi sottili nella pagina del prodotto stessa se l'aggiunta del prodotto violerebbe una condizione del carrello o se il prodotto richiede l'acquisto di altri articoli con esso.

#### Template admin (`views/templates/admin/`)

-   `cartcon/lib/searchTool/views/scripts.tpl`

    -   **Scopo:** Probabilmente include dipendenze JavaScript o inizializza gli script di completamento automatico per i moduli di amministrazione.
-   `cartcon/views/templates/admin/AdminCartAssociationsCondition.tpl`

    -   **Scopo:** Il template principale per `AdminCartAssociationsConditionController`, che visualizza l'interfaccia per la gestione delle associazioni prodotto/categoria per una condizione. Questo includerebbe campi di ricerca, elenchi di elementi selezionati e pulsanti di salvataggio.
-   `cartcon/views/templates/admin/adminSearchCustomer.tpl`

    -   **Scopo:** Template per l'interfaccia di ricerca clienti, utilizzato quando si escludono clienti dalle condizioni.
-   `cartcon/views/templates/admin/script.tpl`

    -   **Scopo:** Template di script admin generale, che potenzialmente include JavaScript specifico del modulo o variabili di configurazione per il back office.
-   `cartcon/views/templates/admin/search-attribute-value-result.tpl`

    -   **Scopo:** Template per la visualizzazione dei risultati di una ricerca di attributi/valori all'interno del pannello di amministrazione, probabilmente utilizzato in combinazione con le ricerche di prodotti.
-   `cartcon/views/templates/admin/search-attribute-value.tpl`

    -   **Scopo:** Template per il campo di input di ricerca e gli elementi UI associati per la ricerca di attributi/valori di prodotto nell'amministrazione.
-   `cartcon/views/templates/admin/selectedProducts.tpl`

    -   **Scopo:** Template per la visualizzazione dell'elenco dei prodotti che sono stati selezionati e associati a una particolare condizione nei moduli di amministrazione.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

Il modulo crea tabelle personalizzate per memorizzare le sue varie condizioni e associazioni. Queste tabelle sono tipicamente prefissate con `ps_cartcon_` o `cartcon_`.

-   `ps_cartcon`: Memorizza le condizioni generali del carrello (nome, messaggio, stato attivo, ecc.).
-   `ps_cartcon_ass`: Memorizza le associazioni tra condizioni e prodotti/categorie specifici.
-   `ps_cartcon_country`: Memorizza le condizioni specifiche per paese.
-   `ps_cartcon_quantity`: Memorizza le condizioni basate sulla quantità.
-   `ps_cartcon_value`: Memorizza le condizioni basate sul valore.
-   `ps_configuration`: Le impostazioni del modulo come `CARTCON_CUSTOMERS`, `ccon_visibility_rule`, `CARTCON_FUTURE`, ecc., sono memorizzate qui.

#### Tabella degli hook registrati

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Utilizzato per caricare le risorse CSS e JavaScript del modulo sia per il front-office che per il back-office. |
| `displayPaymentTop` | Nella parte superiore della pagina di selezione del pagamento durante il checkout. | Critico per rivalutare le condizioni del carrello appena prima del pagamento e bloccare se necessario. |
| `displayShoppingCart` | Nella pagina principale del carrello. | Hook principale per visualizzare i messaggi delle condizioni e disabilitare il pulsante di checkout. |
| `actionAdminControllerSetMedia` | Quando un controller admin viene caricato e i suoi media (JS/CSS) vengono impostati. | Utilizzato per caricare risorse JS/CSS specifiche per le pagine di configurazione del back-office del modulo. |
| `displayProductActions` | Tipicamente vicino al pulsante "Aggiungi al carrello" nella pagina del prodotto. | Può essere utilizzato per visualizzare suggerimenti o avvisi sulle condizioni specifiche del prodotto. |
| `actionCartSave` | Dopo che un carrello viene salvato (ad esempio, prodotto aggiunto/rimosso, quantità modificata). | (Implicito/Probabile) Il modulo probabilmente utilizzerebbe un `actionCartSave` o un hook simile per attivare la rivalutazione delle condizioni del carrello lato server, che poi informa il JS del front-office. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo "Cart conditions pro", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a garantire che il modulo funzioni in modo ottimale con il tuo negozio PrestaShop.
