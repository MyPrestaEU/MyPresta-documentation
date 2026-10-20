---
title: "Competenza Clienti - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Competenza Clienti di MyPresta.eu."
sidebar:
  label: "Competenza Clienti - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Customers Expertise su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/customers-expertise.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/customers-expertise/)
>
> ---


# Competenza Clienti

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e sono solitamente presenti in qualsiasi ambiente di hosting moderno. Nessun requisito di hosting speciale oltre a una configurazione PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Competenza Clienti)

Questa è la schermata di configurazione principale dove definisci i tuoi obiettivi, i loro criteri e le ricompense. La configurazione del modulo è gestita tramite un'interfaccia dedicata che ti consente di aggiungere, modificare e rimuovere gli obiettivi.

**Nome schermata e posizione menu:**
Puoi accedere a questa schermata navigando su **Moduli > Gestione moduli**, cercando "Competenza Clienti" e cliccando sul pulsante "Configura".

**Azioni e impostazioni disponibili:**
La pagina di configurazione presenterà un elenco dei tuoi obiettivi attualmente definiti. Tipicamente troverai opzioni per:

-   **Aggiungi nuovo obiettivo:** Un pulsante o un link per creare un nuovo obiettivo.
-   **Modifica obiettivo esistente:** Un'icona (ad esempio, matita) accanto a ciascun obiettivo nell'elenco per modificarne le impostazioni.
-   **Elimina obiettivo:** Un'icona (ad esempio, cestino) accanto a ciascun obiettivo per rimuoverlo.

Quando aggiungi o modifichi un obiettivo, tipicamente incontrerai le seguenti impostazioni:

#### **Dettagli obiettivo**

-   **Nome obiettivo:**

    -   **Cosa fa questa impostazione:** Questo è il titolo dell'obiettivo che i tuoi clienti vedranno (ad esempio, "Primo acquirente", "Maestro delle recensioni", "Acquirente VIP").
    -   **Effetto della modifica di questa impostazione:** Questo nome viene visualizzato nella sezione "I miei obiettivi" del cliente. Un nome chiaro e accattivante incoraggia il coinvolgimento.
    -   **Valore consigliato:** Qualcosa di descrittivo e motivante.
    -   **Scenario / esempio commerciante:** "Eroe del primo ordine" per il primo acquisto di un cliente.
-   **Descrizione obiettivo:**

    -   **Cosa fa questa impostazione:** Una breve spiegazione di cosa riguarda l'obiettivo e come guadagnarlo. Questo aiuta i clienti a comprendere l'obiettivo.
    -   **Effetto della modifica di questa impostazione:** Questa descrizione appare accanto al nome. Una buona descrizione chiarisce i criteri dell'obiettivo.
    -   **Valore consigliato:** Conciso e incoraggiante.
    -   **Scenario / esempio commerciante:** "Fai il tuo primissimo acquisto nel nostro negozio per guadagnare questo badge!"
-   **Immagine/Icona obiettivo:**

    -   **Cosa fa questa impostazione:** Ti consente di caricare una rappresentazione visiva (badge, icona) per l'obiettivo.
    -   **Effetto della modifica di questa impostazione:** Questa immagine viene visualizzata accanto al nome dell'obiettivo, rendendolo visivamente accattivante e riconoscibile.
    -   **Valore consigliato:** Un'immagine unica e di alta qualità che rifletta il tema dell'obiettivo.
    -   **Scenario / esempio commerciante:** Un'icona a "stella" per un obiettivo "Miglior recensore".
-   **Attivo / Abilitato:**

    -   **Cosa fa questa impostazione:** Un interruttore per abilitare o disabilitare l'obiettivo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* L'obiettivo è attivo, i clienti possono guadagnarlo e apparirà nel loro elenco di obiettivi.
        -   *Quando disabilitato:* L'obiettivo è nascosto, i clienti non possono guadagnarlo e non apparirà nel front office. Utile per obiettivi stagionali o quelli che stai ancora preparando.
    -   **Valore consigliato:** SÌ per obiettivi attivi.
    -   **Scenario / esempio commerciante:** Disabilita un obiettivo "Acquirente di Natale" dopo la stagione delle vacanze.

#### **Criteri obiettivo (Come guadagnarlo)**

Questo è il cuore del modulo, dove definisci le condizioni che un cliente deve soddisfare. Il modulo probabilmente offre vari tipi di criteri. Esempi comuni includono:

-   **Numero di ordini:**

    -   **Cosa fa questa impostazione:** Il cliente deve effettuare un numero specificato di ordini.
    -   **Effetto della modifica di questa impostazione:** Determina quanti ordini riusciti sono richiesti.
    -   **Valore consigliato:** Inizia con numeri bassi per gli obiettivi iniziali (ad esempio, 1, 3) e aumenta per i livelli superiori.
    -   **Scenario / esempio commerciante:** Imposta su "1" per "Primo acquirente", "5" per "Cliente fedele".
-   **Importo totale speso:**

    -   **Cosa fa questa impostazione:** La spesa cumulativa del cliente su tutti gli ordini deve raggiungere un certo importo.
    -   **Effetto della modifica di questa impostazione:** Definisce la soglia monetaria.
    -   **Valore consigliato:** Adatta al tuo valore medio dell'ordine e ai segmenti di clientela.
    -   **Scenario / esempio commerciante:** Imposta su "€100" per "Spender Bronzo", "€500" per "Spender Argento".
-   **Numero di prodotti acquistati:**

    -   **Cosa fa questa impostazione:** Il cliente deve acquistare una quantità totale specifica di prodotti (su tutti gli ordini).
    -   **Effetto della modifica di questa impostazione:** Imposta la soglia di quantità.
    -   **Valore consigliato:** Utile per incoraggiare acquisti in blocco o provare prodotti diversi.
    -   **Scenario / esempio commerciante:** Imposta su "10" per "Collezionista di prodotti".
-   **Numero di recensioni prodotto:**

    -   **Cosa fa questa impostazione:** Il cliente deve inviare un certo numero di recensioni prodotto approvate.
    -   **Effetto della modifica di questa impostazione:** Incoraggia i contenuti generati dagli utenti e la prova sociale.
    -   **Valore consigliato:** Imposta su "1" per "Primo recensore", "5" per "Maestro delle recensioni".
    -   **Scenario / esempio commerciante:** Ricompensa i clienti per aver contribuito con feedback preziosi.
-   **Acquisto di prodotto/categoria specifico:**

    -   **Cosa fa questa impostazione:** Il cliente deve acquistare un prodotto da una categoria specifica o un prodotto specifico.
    -   **Effetto della modifica di questa impostazione:** Promuove articoli o categorie specifici.
    -   **Valore consigliato:** Utilizza per lanci di nuovi prodotti o inventario a lento movimento.
    -   **Scenario / esempio commerciante:** "Acquistato un articolo della nuova collezione" per l'acquisto da una categoria "Nuovi arrivi".

#### **Ricompensa obiettivo (Buono sconto)**

-   **Tipo di buono:**

    -   **Cosa fa questa impostazione:** Definisce il tipo di codice sconto che il cliente riceve (ad esempio, percentuale, importo fisso, spedizione gratuita).
    -   **Effetto della modifica di questa impostazione:** Determina la natura della ricompensa.
    -   **Valore consigliato:** Gli sconti percentuali sono spesso popolari, ma gli importi fissi possono essere buoni per acquisti più piccoli.
    -   **Scenario / esempio commerciante:** "Sconto percentuale" per il 10% di sconto sul prossimo ordine.
-   **Valore del buono:**

    -   **Cosa fa questa impostazione:** Il valore effettivo dello sconto (ad esempio, "10" per il 10%, "€5" per un importo fisso).
    -   **Effetto della modifica di questa impostazione:** Incide direttamente sull'incentivo per il cliente.
    -   **Valore consigliato:** Bilancia la generosità con i tuoi margini di profitto.
    -   **Scenario / esempio commerciante:** "15" per uno sconto del 15%.
-   **Periodo di validità del buono (Giorni):**

    -   **Cosa fa questa impostazione:** Quanti giorni il buono generato è valido dal momento in cui il cliente lo richiede.
    -   **Effetto della modifica di questa impostazione:** Crea urgenza per il cliente di utilizzare il buono.
    -   **Valore consigliato:** 7-30 giorni è comune. Troppo breve può frustrare, troppo lungo riduce l'urgenza.
    -   **Scenario / esempio commerciante:** Imposta su "14" giorni per incoraggiare un rapido acquisto ripetuto.
-   **Importo minimo ordine per il buono:**

    -   **Cosa fa questa impostazione:** Se il buono richiede un valore minimo di acquisto per essere utilizzato.
    -   **Effetto della modifica di questa impostazione:** Aiuta a proteggere i tuoi margini e incoraggia i clienti a spendere di più.
    -   **Valore consigliato:** Imposta un minimo ragionevole che incoraggi un upsell senza essere proibitivo.
    -   **Scenario / esempio commerciante:** "€30" di ordine minimo per uno sconto di €5.
-   **Prefisso del buono:**

    -   **Cosa fa questa impostazione:** Un prefisso personalizzato per i codici sconto generati (ad esempio, "OBIETTIVO-", "BADGE-").
    -   **Effetto della modifica di questa impostazione:** Ti aiuta a identificare la fonte dei codici sconto nei tuoi rapporti di vendita PrestaShop.
    -   **Valore consigliato:** Un prefisso breve e memorabile.
    -   **Scenario / esempio commerciante:** "ESPERTO-" in modo da sapere che il buono proviene dal modulo Competenza Clienti.

**Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

1.  **Pianifica i tuoi obiettivi:** Prima di creare, decidi quali comportamenti vuoi premiare e quanti livelli di obiettivi vuoi.
2.  **Inizia in modo semplice:** Inizia con 2-3 obiettivi di base (ad esempio, primo ordine, spesa totale, numero di recensioni) per sondare il terreno.
3.  **Crea ogni obiettivo:** Segui il processo "Aggiungi nuovo obiettivo", definendo attentamente criteri e ricompense.
4.  **Monitora il coinvolgimento dei clienti:** Controlla le tue vendite e gli account dei clienti per vedere come i clienti interagiscono con gli obiettivi.
5.  **Regola ed espandi:** In base alle prestazioni, affina gli obiettivi esistenti o introduci nuovi obiettivi più complessi.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Pagina di configurazione del modulo** | Nome obiettivo | Descrittivo | Titolo visualizzato al cliente. |
| | Descrizione obiettivo | Informativo | Spiega come guadagnare l'obiettivo. |
| | Immagine/Icona obiettivo | Immagine unica | Rappresentazione visiva per il badge. |
| | Attivo / Abilitato | SÌ | Attiva/disattiva la visibilità e l'idoneità dell'obiettivo. |
| | **Criteri: Numero di ordini** | 1, 3, 5 | Il cliente deve effettuare X ordini. |
| | **Criteri: Importo totale speso** | €50, €100, €500 | La spesa totale del cliente deve raggiungere X. |
| | **Criteri: Numero di prodotti acquistati** | 5, 10, 20 | Il cliente deve acquistare X prodotti totali. |
| | **Criteri: Numero di recensioni prodotto** | 1, 3, 5 | Il cliente deve inviare X recensioni approvate. |
| | **Criteri: Acquisto di prodotto/categoria specifico** | (Seleziona prodotto/categoria) | Il cliente deve acquistare da un prodotto/categoria specifico. |
| | **Ricompensa: Tipo di buono** | Percentuale | Tipo di sconto (%, fisso, spedizione gratuita). |
| | **Ricompensa: Valore del buono** | 10 (per %) | L'importo dello sconto. |
| | **Ricompensa: Periodo di validità del buono (Giorni)** | 14-30 | Quanto tempo il buono è valido dopo la richiesta. |
| | **Ricompensa: Importo minimo ordine per il buono** | (Opzionale) | Valore minimo del carrello richiesto per utilizzare il buono. |
| | **Ricompensa: Prefisso del buono** | ESPERTO- | Prefisso personalizzato per i codici sconto generati. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei clienti non vedono la sezione degli obiettivi nel loro account.**
R: Innanzitutto, assicurati che il modulo "Competenza Clienti" sia installato e abilitato nel tuo Back Office. Controlla la configurazione del modulo per assicurarti di aver creato almeno un obiettivo e di averlo impostato su "Attivo". Inoltre, verifica che il file `customer-account.tpl` del tuo tema (o equivalente) sia correttamente agganciato per visualizzare il link del modulo. Se hai un tema personalizzato, potresti aver bisogno di un webmaster per assicurarti che l'hook sia renderizzato.

**D: I clienti stanno guadagnando obiettivi ma non ricevono codici sconto.**
R: Vai alla configurazione del modulo e modifica l'obiettivo specifico. Ricontrolla che un "Tipo di buono" e un "Valore del buono" siano correttamente definiti per la ricompensa. Assicurati che non ci siano errori di battitura o impostazioni errate nei parametri del buono. Inoltre, controlla le tue "Regole carrello" di PrestaShop (o "Sconti" nelle versioni precedenti) per vedere se i buoni generati vi appaiono.

**D: Le immagini degli obiettivi non vengono visualizzate correttamente.**
R: Questo di solito indica un problema con il caricamento dell'immagine o i permessi dei file. Assicurati che il file immagine che hai caricato sia in un formato web standard (JPG, PNG, GIF) e non troppo grande. Controlla i permessi dei file del tuo server per la directory delle immagini del modulo (ad esempio, `modules/customersexpertise/img/`) per assicurarti che PrestaShop possa scrivere e leggere i file lì. Anche la pulizia della cache di PrestaShop (Parametri avanzati > Prestazioni) può aiutare.

**D: Posso tradurre i nomi e le descrizioni degli obiettivi in più lingue?**
R: Sì, come la maggior parte dei moduli PrestaShop, i campi di testo per i nomi e le descrizioni degli obiettivi dovrebbero supportare l'input multilingue. Quando modifichi un obiettivo, cerca le bandiere delle lingue accanto ai campi di input, che ti consentono di fornire traduzioni per ogni lingua installata nel tuo negozio.

**D: Cosa succede se un cliente guadagna un obiettivo ma in seguito lo disabilito?**
R: Se un obiettivo viene disabilitato, i nuovi clienti non potranno più guadagnarlo e di solito verrà nascosto dal front office. I clienti che lo hanno già guadagnato di solito manterranno il loro status guadagnato e tutti i buoni associati che hanno richiesto prima che l'obiettivo fosse disabilitato. Tuttavia, non potranno richiedere nuovamente i buoni se l'obiettivo viene riabilitato e ne hanno già uno.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster che lavorano con il modulo Competenza Clienti.

### 4.1 Panoramica dell'architettura

Il modulo Competenza Clienti segue un'architettura standard per i moduli PrestaShop, sfruttando principalmente i controller frontali per le interazioni rivolte al cliente e la classe principale del modulo per la configurazione e la gestione degli hook. Integra la logica di gamification monitorando le azioni del cliente (ordini, recensioni) e generando dinamicamente oggetti `CartRule` (buono) di PrestaShop come ricompense. La logica principale del modulo risiede nel suo file PHP principale e nei controller frontali dedicati, con i template Smarty che gestiscono il livello di presentazione.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

Questi controller gestiscono la logica e la visualizzazione rivolte al cliente per gli obiettivi e le funzionalità correlate.

-   `controllers/front/achievements.php`

    -   **Nome classe e classe genitore:** `CustomersExpertiseAchievementsModuleFrontController` che estende `ModuleFrontController`.
    -   **Responsabilità:** Questo è il controller principale per la visualizzazione degli obiettivi di un cliente. Recupera tutti gli obiettivi definiti, controlla l'idoneità e lo stato di guadagno del cliente corrente per ciascuno e prepara i dati per il template `achievements.tpl`. Probabilmente gestisce la logica per la richiesta dei buoni una volta che un obiettivo è stato guadagnato.
    -   **Percorsi:** Tipicamente accessibile tramite un URL come `tuonegozio.com/module/customersexpertise/achievements`.
-   `controllers/front/affiliationlink.php`

    -   **Nome classe e classe genitore:** `CustomersExpertiseAffiliationlinkModuleFrontController` che estende `ModuleFrontController`.
    -   **Responsabilità:** Sebbene la descrizione del modulo non menzioni esplicitamente l'affiliazione, questo controller suggerisce una potenziale funzionalità per i clienti di generare e gestire link di affiliazione, possibilmente come ricompensa per un obiettivo o come funzionalità autonoma. Gestirebbe la visualizzazione e la generazione di tali link.
    -   **Percorsi:** Probabilmente `tuonegozio.com/module/customersexpertise/affiliationlink`.
-   `controllers/front/index.php`

    -   **Nome classe e classe genitore:** `CustomersExpertiseIndexModuleFrontController` che estende `ModuleFrontController`.
    -   **Responsabilità:** Spesso funge da controller frontale predefinito o di fallback. Potrebbe reindirizzare al controller `achievements` o visualizzare una pagina di destinazione generale per il modulo se non viene richiesta alcuna azione specifica.
    -   **Percorsi:** `tuonegozio.com/module/customersexpertise/index` o `tuonegozio.com/module/customersexpertise`.
-   `controllers/front/voucher.php`

    -   **Nome classe e classe genitore:** `CustomersExpertiseVoucherModuleFrontController` che estende `ModuleFrontController`.
    -   **Responsabilità:** Questo controller è probabilmente responsabile del processo effettivo di generazione e assegnazione di un buono sconto a un cliente una volta che questi richiede un obiettivo guadagnato. Interagirebbe con l'oggetto `CartRule` di PrestaShop per creare il buono e potenzialmente aggiornare lo stato dell'obiettivo del cliente.
    -   **Percorsi:** Potrebbe essere un endpoint AJAX o un URL diretto per la richiesta di buoni, ad esempio `tuonegozio.com/module/customersexpertise/voucher`.

#### Controller Admin Back-Office

Il modulo non sembra avere controller Admin personalizzati dedicati. La configurazione è gestita tramite il metodo `getContent()` della classe principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

L'inventario fornito non indica classi personalizzate all'interno della directory `classes/`. Ciò suggerisce che la logica principale del modulo, le definizioni degli obiettivi e il tracciamento dei clienti sono probabilmente gestiti direttamente all'interno del file principale del modulo (`ajax_customersexpertise.php`) e potenzialmente sfruttando le classi `ObjectModel` esistenti di PrestaShop come `Customer`, `Order`, `Product` e `CartRule`.

Il modulo gestirebbe internamente i dati degli obiettivi, possibilmente:

-   Memorizzando le definizioni degli obiettivi (nome, descrizione, criteri, ricompensa) nella tabella `ps_configuration` come array serializzati o JSON.
-   Memorizzando lo stato degli obiettivi del cliente (guadagnato, buono richiesto) in una tabella personalizzata creata durante l'installazione o anche all'interno dei campi meta di `ps_configuration` o `ps_customer`.

### 4.4 Risorse JavaScript (`views/js/`)

-   `customersexpertise/lib/voucherengine/script.js`
    -   **Ambito:** Probabilmente Front-office.
    -   **Dettagli:** Questo script è probabilmente responsabile del miglioramento dell'esperienza utente sulla pagina degli obiettivi del cliente. Potrebbe gestire:
        -   Richieste AJAX per la richiesta di buoni (ad esempio, quando un cliente clicca su un pulsante "Richiedi buono").
        -   Aggiornamenti dinamici della pagina dopo che un buono è stato richiesto (ad esempio, mostrando il codice del buono, contrassegnando l'obiettivo come richiesto).
        -   Validazione lato client o elementi interattivi relativi alle funzionalità di gamification.
        -   Potenzialmente, potrebbe interagire con il controller frontale `voucher.php`.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `customersexpertise/css/customersexpertise.css`

    -   **Ambito:** Stile del cliente Front-office.
    -   **Dettagli:** Questo è il foglio di stile principale per i componenti front-office del modulo. Definisce l'aspetto visivo dell'elenco degli obiettivi, delle singole schede degli obiettivi, della visualizzazione dei buoni e di qualsiasi altro elemento dell'interfaccia utente presentato al cliente.
    -   **Selettori di classe CSS chiave:** Gli sviluppatori possono aspettarsi classi come `.customersexpertise-achievements`, `.achievement-item`, `.achievement-badge`, `.voucher-code`, ecc., che possono essere sovrascritte nel `custom.css` o `theme.css` di un tema personalizzato per corrispondere al branding del negozio.
-   `customersexpertise/lib/voucherengine/ps16.css`

    -   **Ambito:** Stile del cliente Front-office, specificamente per la compatibilità con PrestaShop 1.6.
    -   **Dettagli:** Questo foglio di stile probabilmente contiene override specifici o stili aggiuntivi per garantire che la visualizzazione front-office del modulo sia corretta e visivamente coerente con i temi di PrestaShop 1.6. Potrebbe affrontare differenze di layout o stili specifici degli elementi che sono cambiati tra le versioni di PrestaShop. Per le versioni più recenti di PrestaShop (1.7, 8.x, 9.x), questo file potrebbe essere caricato condizionatamente o i suoi stili potrebbero essere meno rilevanti, affidandosi maggiormente a `customersexpertise.css`.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template Front-office (`views/templates/front/`)**:

    -   `customersexpertise/views/templates/front/achievements.tpl`
        -   **Scopo:** Questo è il template principale per la visualizzazione della pagina degli obiettivi del cliente. Itera attraverso i dati degli obiettivi passati dal controller `achievements.php`, mostrando i badge guadagnati, i criteri per quelli non guadagnati e le opzioni per richiedere i buoni.
    -   `customersexpertise/views/templates/front/affiliation-link.tpl`
        -   **Scopo:** Se il controller `affiliationlink.php` è attivo, questo template renderizzerebbe l'interfaccia per i clienti per visualizzare o generare i loro link di affiliazione.
    -   `customersexpertise/views/templates/front/voucher.tpl`
        -   **Scopo:** Questo template potrebbe essere utilizzato per visualizzare un singolo codice buono o un messaggio di conferma dopo che un buono è stato richiesto, potenzialmente come parte di una risposta AJAX o di una pagina dedicata.
-   **Template Hook (`views/templates/hook/`)**:

    -   `customersexpertise/views/templates/hook/customer-account.tpl`
        -   **Hook:** `displayCustomerAccount` (o simile, a seconda della versione di PrestaShop).
        -   **Scopo:** Questo template renderizza il link o il blocco che appare nella dashboard "Il mio account" del cliente, indirizzandolo alla pagina "I miei obiettivi". È fondamentale per la scopribilità delle funzionalità del modulo da parte del cliente.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    La descrizione del modulo e l'inventario dei file non elencano esplicitamente file SQL personalizzati per la creazione di tabelle. Ciò suggerisce che il modulo potrebbe archiviare i suoi dati in uno dei seguenti modi:

    -   **`ps_configuration`**: Le definizioni degli obiettivi (criteri, ricompense) potrebbero essere archiviate come array serializzati o stringhe JSON nella tabella `ps_configuration`, utilizzando chiavi di configurazione uniche (ad esempio, `CUSTOMERS_EXPERTISE_ACHIEVEMENTS`).
    -   **Tabelle PrestaShop esistenti**: Lo stato degli obiettivi del cliente (quali obiettivi ha guadagnato, quali buoni ha richiesto) potrebbe essere archiviato in un campo personalizzato aggiunto alle tabelle `ps_customer` o `ps_customer_group`, o in una tabella personalizzata creata dinamicamente dal metodo `install()` del modulo senza un file `.sql` dedicato.
    -   **`ps_cart_rule`**: Il modulo interagisce direttamente con il sistema `CartRule` (buono sconto) di PrestaShop per generare ricompense.
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di tutte le pagine del front-office. | Per includere risorse CSS e JavaScript a livello globale, o per aggiungere meta tag. |
| `displayLeftColumn` / `displayRightColumn` | Nella colonna sinistra/destra delle pagine del front-office. | Per visualizzare un piccolo blocco promozionale o un link alla pagina degli obiettivi. |
| `displayProductButtons` / `displayProductExtraContent` (o hook simili della pagina prodotto) | Sulla pagina del prodotto. | Potenzialmente per tracciare visualizzazioni/acquisti di prodotti per i criteri degli obiettivi, o per suggerire la gamification. |
| `displayFooter` | Nel piè di pagina di tutte le pagine del front-office. | Per visualizzare un link alla pagina degli obiettivi o una promozione generale sulla gamification. |
| `displayCustomerAccount` | Nella dashboard "Il mio account" del cliente. | **CRITICO:** Per aggiungere il link "I miei obiettivi" per i clienti. |
| `actionValidateOrder` | Dopo che l'ordine di un cliente è stato convalidato con successo. | **CRITICO:** Per verificare se l'ordine soddisfa i criteri di un obiettivo (ad esempio, primo ordine, spesa totale, acquisto di prodotti) e assegnare gli obiettivi. |
| `actionObjectProductAddAfter` / `actionObjectProductUpdateAfter` | Dopo che un prodotto viene aggiunto o aggiornato. | Meno probabile, ma potrebbe essere utilizzato per aggiornare i criteri degli obiettivi se si riferiscono agli attributi del prodotto. |
| `actionObjectCustomerAddAfter` | Dopo che un nuovo cliente si registra. | Per inizializzare il tracciamento degli obiettivi per i nuovi clienti. |
| `actionObjectReviewAddAfter` (o simile per i moduli di recensione) | Dopo che un cliente invia una recensione del prodotto. | **CRITICO:** Per verificare se la recensione soddisfa i criteri di un obiettivo (ad esempio, numero di recensioni). |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo Competenza Clienti, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a garantire che il modulo funzioni in modo ottimale con il tuo negozio PrestaShop.
