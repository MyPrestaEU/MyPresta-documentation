---
title: "Tabella combinazioni pagina prodotto - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Tabella combinazioni pagina prodotto' di MyPresta.eu."
sidebar:
  label: "Tabella combinazioni pagina prodotto - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Product page combinations table su MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-combinations-table.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/product-page-combinations-table/)
>
> ---


# Tabella combinazioni pagina prodotto

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale dove controlli come la tabella delle combinazioni appare e si comporta sulle tue pagine prodotto.

#### Impostazioni Generali

-   **Attiva la funzione filtri**

    -   **Cosa fa questa impostazione:** Abilita o disabilita un sistema di filtraggio sopra la tabella delle combinazioni, permettendo ai clienti di restringere rapidamente le opzioni in base a valori di attributo specifici (es. "Mostra solo magliette Rosse").
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Una barra dei filtri apparirà sopra la tabella, rendendo più facile per i clienti trovare combinazioni specifiche in elenchi lunghi.
        -   *Quando disabilitato:* Nessuna barra dei filtri sarà mostrata, e tutte le combinazioni saranno visualizzate senza opzioni di filtraggio.
    -   **Valore consigliato:** SÌ (se hai molte combinazioni per prodotto, o se i clienti cercano spesso attributi specifici).
    -   **Scenario / esempio per il commerciante:** Un negozio di abbigliamento con decine di taglie e colori per una singola maglietta. I filtri aiutano i clienti a trovare rapidamente le magliette "Blu Grande".
-   **Evidenzia il miglior prezzo**

    -   **Cosa fa questa impostazione:** Enfatizza visivamente la combinazione con il prezzo più basso nella tabella, attirando l'attenzione del cliente sull'opzione più conveniente.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* La riga corrispondente alla combinazione più economica sarà evidenziata (es. con un colore di sfondo diverso).
        -   *Quando disabilitato:* Nessuna evidenziazione speciale per il prezzo più basso.
    -   **Valore consigliato:** SÌ (può incoraggiare gli acquisti evidenziando il valore).
    -   **Scenario / esempio per il commerciante:** Un prodotto con vari bundle o configurazioni in cui una combinazione offre un affare significativamente migliore.
-   **Visualizza colonna risparmi**

    -   **Cosa fa questa impostazione:** Aggiunge una colonna extra alla tabella che mostra l'importo o la percentuale che un cliente risparmia acquistando una combinazione specifica, particolarmente utile con sconti sulla quantità o prezzi speciali.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Apparirà una colonna "Risparmi", mostrando lo sconto per ogni combinazione, se applicabile.
        -   *Quando disabilitato:* Questa colonna non sarà mostrata.
    -   **Valore consigliato:** SÌ (se offri frequentemente sconti o hai prezzi basati sulla quantità).
    -   **Scenario / esempio per il commerciante:** Vendere un prodotto con un prezzo base, ma alcune combinazioni (es. una combinazione "bundle") hanno un prezzo ridotto, e vuoi mostrare il risparmio.
-   **Suggerimento soglia sconto quantità**

    -   **Cosa fa questa impostazione:** Visualizza un piccolo tooltip o messaggio che indica la quantità richiesta per sbloccare uno sconto specifico, incoraggiando i clienti ad acquistare di più.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Quando un cliente passa il mouse o interagisce con un campo quantità, potrebbe apparire un suggerimento che mostra "Acquista 5 per il 10% di sconto!".
        -   *Quando disabilitato:* Nessun suggerimento di questo tipo sarà visualizzato.
    -   **Valore consigliato:** SÌ (se utilizzi la funzione sconti sulla quantità di PrestaShop).
    -   **Scenario / esempio per il commerciante:** Un negozio che vende forniture per ufficio dove l'acquisto di 10 penne ottiene uno sconto del 5%, e questo suggerimento ricorda al cliente.
-   **Layout a schede mobile**

    -   **Cosa fa questa impostazione:** Determina come la tabella delle combinazioni viene visualizzata sui dispositivi mobili. Invece di una tabella larga, può passare a un layout "a schede" più user-friendly.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Sugli smartphone, ogni combinazione sarà presentata come una scheda separata, impilata verticalmente, rendendola più facile da leggere e interagire.
        -   *Quando disabilitato:* Il modulo tenterà di visualizzare la tabella completa, il che potrebbe richiedere lo scorrimento orizzontale su mobile, potenzialmente ostacolando l'usabilità.
    -   **Valore consigliato:** SÌ (cruciale per la reattività mobile e una buona esperienza utente).
    -   **Scenario / esempio per il commerciante:** Un cliente che naviga nel tuo negozio dal suo telefono. Il layout a schede assicura che possa facilmente vedere e selezionare le combinazioni senza zoom o scorrimento eccessivo.
-   **Ordine delle colonne**

    -   **Cosa fa questa impostazione:** Ti permette di personalizzare la sequenza delle colonne (es. Immagine, Riferimento, Prezzo, Quantità) nella tabella delle combinazioni.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando modificato:* Le colonne si riorganizzeranno nella tabella del front-office secondo l'ordine specificato.
    -   **Valore consigliato:** Organizza le colonne in un ordine intuitivo che abbia senso per i tuoi prodotti (es. Immagine, Attributi, Prezzo, Quantità, Aggiungi al carrello).
    -   **Scenario / esempio per il commerciante:** Per un negozio di moda, potresti volere "Immagine" per prima, poi "Colore", poi "Taglia", poi "Prezzo". Per l'elettronica, "Riferimento" potrebbe essere più importante.
-   **Clicca e cambia combinazione**

    -   **Cosa fa questa impostazione:** Controlla se cliccando su una riga di combinazione nella tabella si aggiornano automaticamente l'immagine principale del prodotto, il prezzo e altri dettagli sulla pagina del prodotto per riflettere quella specifica combinazione.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Cliccando su una riga si aggiornerà dinamicamente la visualizzazione principale del prodotto, dando al cliente una conferma visiva della sua selezione.
        -   *Quando disabilitato:* La visualizzazione principale del prodotto non cambierà quando si clicca su una riga; solo il campo quantità e il pulsante Aggiungi al carrello per quella riga saranno attivi.
    -   **Valore consigliato:** SÌ (migliora l'esperienza utente fornendo feedback visivo).
    -   **Scenario / esempio per il commerciante:** Un cliente clicca su una combinazione "Rosso, Grande", e l'immagine principale del prodotto passa immediatamente alla versione rossa del prodotto.

#### Impostazioni Immagine

-   **Visualizza immagine**

    -   **Cosa fa questa impostazione:** Determina se un'immagine in miniatura per ogni combinazione deve essere mostrata nella tabella.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Apparirà una colonna immagine, mostrando l'immagine specifica associata a ogni combinazione (se disponibile).
        -   *Quando disabilitato:* Nessuna colonna immagine sarà visualizzata.
    -   **Valore consigliato:** SÌ (le immagini sono potenti per la selezione del prodotto).
    -   **Scenario / esempio per il commerciante:** Un negozio di abbigliamento dove ogni variazione di colore ha un'immagine distinta.
-   **Visualizza colonna immagine se c'è almeno una combinazione con immagine**

    -   **Cosa fa questa impostazione:** Controlla la visibilità della colonna immagine in base al fatto che una combinazione abbia effettivamente un'immagine specifica assegnata.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Se anche una sola combinazione ha un'immagine, la colonna immagine apparirà per tutte le combinazioni (mostrando l'immagine predefinita del prodotto per quelle senza immagini di combinazione specifiche).
        -   *Quando disabilitato:* La colonna immagine apparirà solo se *tutte* le combinazioni hanno immagini specifiche, o potrebbe non apparire affatto se si utilizza anche "Usa immagine predefinita del prodotto" con attenzione.
    -   **Valore consigliato:** SÌ (previene una colonna immagine vuota se solo poche combinazioni hanno immagini).
    -   **Scenario / esempio per il commerciante:** Hai 20 combinazioni, ma solo 5 hanno immagini uniche. Questo assicura che la colonna immagine appaia comunque, utilizzando l'immagine principale del prodotto per le altre 15.
-   **Usa immagine predefinita del prodotto**

    -   **Cosa fa questa impostazione:** Se una combinazione specifica non ha una propria immagine, questa impostazione determina se l'immagine principale del prodotto deve essere utilizzata come fallback.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Le combinazioni senza immagini specifiche visualizzeranno l'immagine principale del prodotto.
        -   *Quando disabilitato:* Le combinazioni senza immagini specifiche mostreranno un segnaposto o nessuna immagine.
    -   **Valore consigliato:** SÌ (assicura che tutte le combinazioni abbiano una rappresentazione visiva).
    -   **Scenario / esempio per il commerciante:** Un prodotto con molte varianti di taglia ma solo un'immagine per colore. Questo assicura che tutte le taglie di un colore specifico mostrino l'immagine del colore corretto.
-   **Abilita zoom fancybox**

    -   **Cosa fa questa impostazione:** Permette ai clienti di cliccare sulle immagini delle combinazioni nella tabella per visualizzare una versione più grande e ingrandita in un pop-up (Fancybox).
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Cliccando su un'immagine di combinazione si aprirà in un pop-up Fancybox.
        -   *Quando disabilitato:* Le immagini non saranno cliccabili per lo zoom.
    -   **Valore consigliato:** SÌ (migliora l'esperienza di visualizzazione delle immagini).
    -   **Scenario / esempio per il commerciante:** Un cliente vuole vedere più da vicino la texture o il dettaglio di una specifica variazione di colore.
-   **Tipo di immagine da visualizzare**

    -   **Cosa fa questa impostazione:** Seleziona la dimensione/tipo di immagine (es. `small_default`, `medium_default`) da visualizzare come miniature nella tabella delle combinazioni.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando modificato:* La dimensione delle immagini nella tabella si aggiornerà al tipo di immagine selezionato.
    -   **Valore consigliato:** `small_default` o `medium_default` (scegliere uno che si adatti bene al layout della tabella senza essere troppo grande o troppo piccolo).
    -   **Scenario / esempio per il commerciante:** Vuoi che le immagini nella tabella siano leggermente più grandi del minuscolo `small_default` ma non grandi come `large_default`.
-   **Tipo di immagine utilizzato per ingrandire la miniatura**

    -   **Cosa fa questa impostazione:** Seleziona la dimensione/tipo di immagine da utilizzare quando la funzione di zoom Fancybox è attivata.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando modificato:* L'immagine visualizzata nel pop-up Fancybox sarà della dimensione selezionata.
    -   **Valore consigliato:** `large_default` o `thickbox_default` (scegliere il tipo di immagine più grande e di alta qualità per lo zoom).
    -   **Scenario / esempio per il commerciante:** Un cliente ingrandisce un'immagine e si aspetta di vedere una versione ad alta risoluzione.

#### Impostazioni di visualizzazione degli attributi

-   **Metodo di visualizzazione degli attributi**

    -   **Cosa fa questa impostazione:** Controlla come i nomi degli attributi (es. "Taglia", "Colore") vengono visualizzati nell'intestazione della tabella.
    -   **Effetto della modifica di questa impostazione:**
        -   *Opzioni (es. "Nome completo", "Nome breve", "ID"):* Cambia il modo in cui appaiono le intestazioni degli attributi.
    -   **Valore consigliato:** "Nome completo" (più descrittivo per i clienti).
    -   **Scenario / esempio per il commerciante:** Vuoi che "Taglia" appaia come "Taglia" non "S" o "ID: 1".
-   **Associazioni attributi con negozio (multistore)**

    -   **Cosa fa questa impostazione:** In un ambiente multistore, questo ti permette di specificare quali gruppi di attributi sono rilevanti per quali negozi, impedendo la visualizzazione di attributi irrilevanti.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando configurato:* Solo gli attributi associati al contesto del negozio corrente saranno visualizzati nella tabella.
    -   **Valore consigliato:** Configurare attentamente se gestisci un multistore con cataloghi di prodotti diversi.
    -   **Scenario / esempio per il commerciante:** Il Negozio A vende vestiti (Taglia, Colore), il Negozio B vende elettronica (Archiviazione, RAM). Questo impedisce che "Archiviazione" appaia nella tabella delle combinazioni del Negozio A.
-   **Includi etichetta al nome dell'attributo**

    -   **Cosa fa questa impostazione:** Aggiunge il nome del gruppo di attributi come prefisso al valore dell'attributo (es. "Taglia: S", "Colore: Rosso").
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I valori degli attributi saranno più descrittivi.
        -   *Quando disabilitato:* Verrà mostrato solo il valore dell'attributo (es. "S", "Rosso").
    -   **Valore consigliato:** SÌ (migliora la chiarezza, specialmente se i valori degli attributi non sono autoesplicativi).
    -   **Scenario / esempio per il commerciante:** Un prodotto ha un valore di attributo "Standard". È una taglia standard, un colore standard o una finitura standard? "Finitura: Standard" lo chiarisce.
-   **Attributo colore**

    -   **Cosa fa questa impostazione:** Ti permette di specificare quale gruppo di attributi rappresenta il "colore" nel tuo negozio. Questo è importante affinché il modulo visualizzi correttamente i campioni di colore o la logica specifica del colore.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando selezionato:* Il modulo tratterà i valori di questo gruppo di attributi come colori, potenzialmente visualizzandoli come campioni di colore invece che come testo.
    -   **Valore consigliato:** Seleziona il tuo gruppo di attributi "Colore" principale.
    -   **Scenario / esempio per il commerciante:** Hai un gruppo di attributi chiamato "Colore" con valori come "Rosso", "Blu", "Verde". Selezionando questo gruppo si assicura che questi vengano visualizzati come veri e propri campioni di colore.

#### Opzioni di visualizzazione

-   **Nascondi intestazione tabella**

    -   **Cosa fa questa impostazione:** Rimuove la riga di intestazione dalla tabella delle combinazioni (es. "Immagine | Taglia | Colore | Prezzo | Quantità").
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* La tabella inizierà direttamente con le righe delle combinazioni, senza titoli di colonna.
        -   *Quando disabilitato:* La riga di intestazione sarà visibile.
    -   **Valore consigliato:** NO (le intestazioni sono solitamente importanti per la chiarezza, a meno che la tua tabella non sia molto semplice e autoesplicativa).
    -   **Scenario / esempio per il commerciante:** Per un prodotto molto semplice con un solo attributo (es. "Dimensione confezione"), potresti nascondere l'intestazione se il contenuto della colonna è ovvio.
-   **Nascondi combinazioni esaurite**

    -   **Cosa fa questa impostazione:** Impedisce che le combinazioni attualmente esaurite vengano visualizzate nella tabella.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Saranno visibili solo le combinazioni in stock, riducendo il disordine e prevenendo la frustrazione del cliente.
        -   *Quando disabilitato:* Le combinazioni esaurite saranno comunque mostrate, spesso con un'etichetta "Esaurito" o un pulsante "Aggiungi al carrello" disabilitato.
    -   **Valore consigliato:** SÌ (generalmente migliore per l'esperienza utente, a meno che tu non voglia mostrare tutte le opzioni per preordini o notifiche di riassortimento).
    -   **Scenario / esempio per il commerciante:** Un modello di scarpa popolare ha esaurito la taglia 10. Nasconderlo impedisce ai clienti di provare a selezionarlo.
-   **Nascondi combinazioni con prezzo = 0**

    -   **Cosa fa questa impostazione:** Esclude dalla visualizzazione nella tabella le combinazioni che hanno un prezzo pari a zero.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Le combinazioni con prezzo zero non appariranno.
        -   *Quando disabilitato:* Le combinazioni con prezzo zero saranno elencate.
    -   **Valore consigliato:** SÌ (a meno che tu non offra intenzionalmente combinazioni gratuite, il che è raro).
    -   **Scenario / esempio per il commerciante:** A volte, a causa di una configurazione errata, una combinazione potrebbe avere un prezzo pari a zero. Nasconderle previene la confusione.
-   **Mostra solo combinazioni con immagini**

    -   **Cosa fa questa impostazione:** Filtra la tabella per visualizzare solo le combinazioni a cui è stata assegnata un'immagine specifica.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Saranno elencate solo le combinazioni con immagini uniche.
        -   *Quando disabilitato:* Tutte le combinazioni saranno mostrate, indipendentemente dal fatto che abbiano un'immagine specifica.
    -   **Valore consigliato:** NO (di solito è meglio mostrare tutte le combinazioni, utilizzando immagini predefinite se necessario, a meno che la differenziazione visiva non sia fondamentale).
    -   **Scenario / esempio per il commerciante:** Se vuoi mostrare solo le combinazioni che hanno differenze visive distinte e non hai caricato immagini per tutte.
-   **Visualizza prezzo**

    -   **Cosa fa questa impostazione:** Controlla se il prezzo per ogni combinazione viene mostrato nella tabella.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Sarà visibile una colonna "Prezzo".
        -   *Quando disabilitato:* La colonna del prezzo sarà nascosta.
    -   **Valore consigliato:** SÌ (il prezzo è un fattore critico per i clienti).
    -   **Scenario / esempio per il commerciante:** Un cliente vuole confrontare i prezzi tra diverse taglie o materiali di un prodotto.
-   **Visualizza prezzo unitario**

    -   **Cosa fa questa impostazione:** Mostra il prezzo unitario (es. prezzo al kg, al litro) per ogni combinazione, se applicabile.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Apparirà una colonna aggiuntiva "Prezzo unitario".
        -   *Quando disabilitato:* Questa colonna non sarà mostrata.
    -   **Valore consigliato:** SÌ (se i tuoi prodotti sono venduti a peso/volume e il prezzo unitario è rilevante).
    -   **Scenario / esempio per il commerciante:** Vendere chicchi di caffè in diverse dimensioni di sacchetto, e i clienti vogliono confrontare il prezzo per 100g.
-   **Visualizza prezzo solo per clienti loggati**

    -   **Cosa fa questa impostazione:** Nasconde i prezzi delle combinazioni ai visitatori che non sono loggati nei loro account cliente.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Gli ospiti non vedranno i prezzi; potrebbero vedere un messaggio che li invita a loggarsi.
        -   *Quando disabilitato:* I prezzi sono visibili a tutti.
    -   **Valore consigliato:** NO (a meno che tu non gestisca un negozio B2B o abbia strategie di prezzo specifiche che richiedono il login).
    -   **Scenario / esempio per il commerciante:** Un negozio all'ingrosso dove i prezzi sono negoziati o specifici per account aziendali registrati.
-   **Mostra etichetta IVA**

    -   **Cosa fa questa impostazione:** Visualizza un'etichetta che indica se i prezzi mostrati sono inclusivi o esclusivi di IVA (es. "IVA incl.", "IVA escl.").
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Lo stato dell'IVA sarà chiaramente indicato accanto ai prezzi.
        -   *Quando disabilitato:* Nessuna etichetta IVA sarà mostrata.
    -   **Valore consigliato:** SÌ (migliora la trasparenza e rispetta i requisiti legali in molte regioni).
    -   **Scenario / esempio per il commerciante:** I clienti in Europa si aspettano di vedere prezzi "IVA incl.", mentre i clienti B2B potrebbero preferire "IVA escl.".

#### Altre chiavi di configurazione (Avanzate/Interne)

Queste impostazioni sono tipicamente gestite dal modulo internamente o sono meno frequentemente modificate dai commercianti.

-   `mypresta_updates`, `update_`, `updatev_`: Chiavi interne per gli aggiornamenti del modulo e il tracciamento della versione.
-   `ctp_position`: Controlla la posizione dell'hook in cui viene visualizzata la tabella.
-   `ctp_lasttab`: Relativo alla visualizzazione della tabella in una scheda prodotto.
-   `ctp_reference`, `ctp_ean`, `ctp_mpn`: Controllano la visualizzazione delle colonne Riferimento, EAN13/JAN e MPN.
-   `ctp_cname`: Controlla la visualizzazione del nome della combinazione.
-   `ctp_atc`, `ctp_atcq`: Controllano il pulsante "Aggiungi al carrello" e il campo quantità.
-   `ctp_ajax`: Determina se AJAX viene utilizzato per l'aggiunta al carrello.
-   `ctp_sort`: Opzioni di ordinamento per le combinazioni all'interno della tabella.
-   `ctp_quantity`, `ctp_quantity_sum`: Visualizzazione della quantità di stock e della somma delle quantità.
-   `ctp_availability`, `ctp_availability_d`: Visualizzazione dello stato di disponibilità e della data.
-   `ctp_imagetype`, `ctp_imagetype_zoom`, `ctp_grid_imagetype`, `ctp_grid_defimg`: Impostazioni del tipo di immagine (coperte sopra).
-   `ctp_attributes_method`: Metodo di visualizzazione degli attributi (coperto sopra).
-   `ctp_prices_tax`: Impostazioni di visualizzazione dell'IVA (coperte sopra).
-   `ctp_color_method`: Come vengono visualizzati gli attributi di colore (es. campioni).
-   `ctp_hide_default`, `ctp_hide_r`: Nascondi combinazione predefinita, nascondi combinazioni con prezzo zero (coperte sopra).
-   `ctp_where`, `ctp_tabtype`: Posizionamento della tabella (hook, tipo di scheda).
-   `ctp_quantity_pm`: Pulsanti più/meno per l'input della quantità.
-   `ctp_view_mode`: Modalità di visualizzazione generale della tabella (tabella, griglia, ecc.).
-   `ctp_grid_row_attr`, `ctp_grid_col_attr`: Impostazioni per il layout a griglia (quali attributi formano righe/colonne).

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### AdminCombinationstabSearchController (Back Office > Moduli > Tabella combinazioni pagina prodotto > Cerca)

Questo controller fornisce un'interfaccia dedicata all'interno del back office di PrestaShop, probabilmente per la gestione o la ricerca di combinazioni, potenzialmente su più prodotti, o per una configurazione avanzata relativa alla visualizzazione delle combinazioni.

-   **Nome schermata e posizione menu:** Troverai tipicamente una nuova voce di menu sotto **Moduli > Tabella combinazioni pagina prodotto** (o simile, a seconda della versione di PrestaShop) etichettata "Cerca" o "Ricerca combinazioni".
-   **Azioni e impostazioni disponibili:** Questa schermata presenta probabilmente una griglia o una vista di gestione delle combinazioni di prodotto. Potrebbe permetterti di:
    -   Cercare combinazioni specifiche per attributi, riferimento, EAN o nome prodotto.
    -   Visualizzare i dettagli delle combinazioni, come stock, prezzo e prodotto associato.
    -   Potenzialmente eseguire azioni in blocco come l'aggiornamento dello stock o del prezzo per più combinazioni (anche se questo è spesso gestito dalla pagina prodotto principale di PrestaShop).
    -   Questa schermata è principalmente per *gestire* e *visualizzare* i dati delle combinazioni in modo strutturato, separatamente dalla pagina di modifica del prodotto principale.
-   **Effetto delle modifiche:** Eventuali modifiche apportate qui (se la modifica è abilitata) aggiornerebbero direttamente i dati delle combinazioni nel tuo database PrestaShop, influenzando prezzi, stock e disponibilità nel front office.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Utilizza questa schermata per controllare rapidamente i dati delle combinazioni, trovare combinazioni specifiche o verificare i livelli di stock senza navigare alle singole pagine prodotto. È uno strumento potente per i negozi con un ampio catalogo di prodotti e combinazioni.

#### index.php (combinationstab/controllers/admin/index.php)

Questo file funge tipicamente da segnaposto o da reindirizzamento per il controller amministrativo principale del modulo. Potrebbe semplicemente caricare `AdminCombinationstabSearchController` o presentare una pagina di atterraggio di base per la sezione amministrativa del modulo. Di solito non ha impostazioni configurabili dirette ma agisce come punto di ingresso.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Configurazione Modulo** | Attiva la funzione filtri | SÌ | Abilita i filtri attributi per la tabella delle combinazioni. |
| | Evidenzia il miglior prezzo | SÌ | Evidenzia visivamente la combinazione con il prezzo più basso. |
| | Visualizza colonna risparmi | SÌ | Mostra l'importo/percentuale di sconto in una colonna dedicata. |
| | Suggerimento soglia sconto quantità | SÌ | Visualizza suggerimenti per sconti basati sulla quantità. |
| | Layout a schede mobile | SÌ | Ottimizza la visualizzazione della tabella per i dispositivi mobili. |
| | Ordine delle colonne | Personalizzabile | Definisce la sequenza delle colonne nella tabella. |
| | Clicca e cambia combinazione | SÌ | Aggiorna l'immagine/dettagli principali del prodotto al clic sulla riga. |
| | Visualizza immagine | SÌ | Mostra le immagini delle combinazioni nella tabella. |
| | Visualizza colonna immagine se c'è almeno una combinazione con immagine | SÌ | Assicura che la colonna immagine appaia se una combinazione ha un'immagine. |
| | Usa immagine predefinita del prodotto | SÌ | Fallback all'immagine principale del prodotto se la combinazione non ha un'immagine specifica. |
| | Abilita zoom fancybox | SÌ | Permette lo zoom delle immagini delle combinazioni. |
| | Tipo di immagine da visualizzare | `medium_default` | Imposta la dimensione della miniatura nella tabella. |
| | Tipo di immagine utilizzato per ingrandire la miniatura | `large_default` | Imposta la dimensione dell'immagine di zoom. |
| | Metodo di visualizzazione degli attributi | Nome completo | Come vengono etichettate le intestazioni degli attributi (es. "Taglia"). |
| | Associazioni attributi con negozio (multistore) | Configura secondo necessità | Filtra gli attributi per negozio in multistore. |
| | Includi etichetta al nome dell'attributo | SÌ | Aggiunge il nome del gruppo di attributi al valore (es. "Taglia: S"). |
| | Attributo colore | Seleziona il tuo attributo Colore | Identifica l'attributo colore per una visualizzazione speciale. |
| | Nascondi intestazione tabella | NO | Mantiene visibili i titoli delle colonne per chiarezza. |
| | Nascondi combinazioni esaurite | SÌ | Rimuove le combinazioni non disponibili dalla tabella. |
| | Nascondi combinazioni con prezzo = 0 | SÌ | Rimuove le combinazioni con prezzo zero. |
| | Mostra solo combinazioni con immagini | NO | Visualizza tutte le combinazioni, utilizzando immagini predefinite se necessario. |
| | Visualizza prezzo | SÌ | Mostra il prezzo per ogni combinazione. |
| | Visualizza prezzo unitario | SÌ (se applicabile) | Mostra il prezzo per unità (es. al kg). |
| | Visualizza prezzo solo per clienti loggati | NO | Rende i prezzi visibili a tutti i visitatori. |
| | Mostra etichetta IVA | SÌ | Indica se i prezzi sono IVA inclusa/esclusa. |
| **AdminCombinationstabSearchController** | Griglia / Vista di gestione | N/A | Cerca, visualizza e potenzialmente gestisci le combinazioni tra i prodotti. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: La tabella delle combinazioni non viene visualizzata sulla mia pagina prodotto.**
R1:

-   **Controlla la posizione del modulo:** Vai su **Design > Posizioni** (o **Moduli > Posizioni** nelle versioni precedenti di PrestaShop) nel tuo Back Office. Cerca il modulo "Tabella combinazioni pagina prodotto". Assicurati che sia agganciato a un hook di visualizzazione pertinente come `displayProductFooter`, `displayProductExtraContent` o `displayProductTabContent`. Se non lo è, clicca su "Trapianta un modulo" e aggiungilo all'hook desiderato.
-   **Configurazione del modulo:** Ricontrolla la pagina di configurazione del modulo per assicurarti che sia abilitato e non nascosto da altre impostazioni (es. "Nascondi combinazioni con prezzo = 0" potrebbe nasconderle tutte se tutte sono zero).
-   **Il prodotto ha combinazioni:** Assicurati che il prodotto che stai visualizzando abbia effettivamente combinazioni definite nelle sue impostazioni prodotto.
-   **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache". A volte, il vecchio contenuto della cache impedisce la visualizzazione di nuovi moduli.

**D2: Le immagini delle mie combinazioni non appaiono o hanno la dimensione sbagliata.**
R2:

-   **Impostazioni immagine:** Rivedi le impostazioni "Tipo di immagine da visualizzare" e "Tipo di immagine utilizzato per ingrandire la miniatura" nella configurazione del modulo. Assicurati di aver selezionato tipi di immagine appropriati che esistono nel tuo tema PrestaShop.
-   **Immagini combinazione caricate:** Verifica di aver effettivamente caricato immagini specifiche per le tue combinazioni di prodotto nella scheda "Combinazioni" del prodotto nel Back Office. In caso contrario, il modulo utilizzerà l'immagine principale del prodotto (se "Usa immagine predefinita del prodotto" è abilitato).
-   **Rigenera miniature:** Se hai modificato i tipi di immagine o caricato nuove immagini, vai su **Design > Impostazioni immagini** (o **Preferenze > Immagini**) e clicca su "Rigenera miniature" per i tipi di immagine pertinenti (es. `medium_default`, `large_default`).

**D3: La tabella appare strana o disallineata sul mio tema personalizzato.**
R3:

-   **Conflitti CSS:** I temi personalizzati a volte hanno stili CSS in conflitto. Questo modulo cerca di essere compatibile, ma potrebbero essere necessarie piccole modifiche.
-   **Contatta il supporto:** Se hai familiarità con il CSS, puoi ispezionare gli elementi utilizzando gli strumenti di sviluppo del tuo browser e provare a sovrascrivere gli stili in conflitto. Altrimenti, contatta il supporto MyPresta.eu con i dettagli del tuo tema e uno screenshot; spesso possono fornire una soluzione rapida.
-   **Aggiornamenti del modulo:** Assicurati di utilizzare l'ultima versione del modulo, poiché i miglioramenti di compatibilità sono spesso inclusi negli aggiornamenti.

**D4: I prezzi non vengono visualizzati correttamente o sono nascosti.**
R4:

-   **Impostazioni di visualizzazione del prezzo:** Controlla "Visualizza prezzo" e "Visualizza prezzo solo per clienti loggati" nella configurazione del modulo. Se quest'ultima è abilitata, assicurati di essere loggato come cliente per vedere i prezzi.
-   **Prezzi core di PrestaShop:** Verifica che i prezzi per le tue combinazioni siano impostati correttamente nella scheda "Combinazioni" del prodotto.
-   **Impostazioni IVA:** Controlla "Mostra etichetta IVA" e le tue impostazioni generali IVA di PrestaShop (**Internazionale > Tasse**) per assicurarti che i prezzi siano calcolati e visualizzati come previsto (IVA incl./escl.).

**D5: Come posso cambiare l'ordine degli attributi nella tabella?**
R5:

-   L'impostazione "Ordine delle colonne" del modulo ti permette di riorganizzare le colonne. Per l'ordine degli attributi stessi (es. "Taglia" prima di "Colore"), questo è tipicamente gestito nel core di PrestaShop: **Catalogo > Attributi e Caratteristiche > Attributi** e **Gruppi di attributi**. L'ordine che imposti lì di solito influenza il modo in cui appaiono nella tabella del modulo.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Tabella combinazioni pagina prodotto" (`combinationstab`) segue un'architettura standard dei moduli PrestaShop, sfruttando pesantemente gli hook per la visualizzazione nel front-office e i controller admin personalizzati per la configurazione avanzata e la gestione dei dati. Si integra profondamente con i dati core di prodotto e combinazione di PrestaShop, rendendo dinamicamente tabelle o griglie HTML utilizzando i template Smarty. AJAX viene utilizzato per funzionalità come "Aggiungi al carrello" e il cambio di combinazione per un'esperienza utente fluida. Il modulo non introduce classi `ObjectModel` personalizzate ma lavora direttamente con gli oggetti `Product` e `Combination` esistenti.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

Questi controller gestiscono richieste AJAX specifiche o funzionalità dedicate del front-office.

-   `controllers/front/BackInStock.php`
    -   **Nome classe e classe genitore:** `CombinationstabBackInStockModuleFrontController` estende `ModuleFrontController`.
    -   **Responsabilità:** Probabilmente gestisce le richieste AJAX relative alle notifiche "di nuovo disponibile" per combinazioni specifiche. Questo potrebbe comportare l'invio di un modulo per registrarsi alle notifiche quando una combinazione esaurita diventa disponibile.
-   `controllers/front/CsvImport.php`
    -   **Nome classe e classe genitore:** `CombinationstabCsvImportModuleFrontController` estende `ModuleFrontController`.
    -   **Responsabilità:** Suggerisce funzionalità per l'importazione di dati di combinazione tramite CSV dal front-office, possibilmente per gruppi di utenti specifici o scenari B2B. Questo comporterebbe l'analisi di file CSV e l'aggiornamento delle combinazioni di prodotto.
-   `controllers/front/Export.php`
    -   **Nome classe e classe genitore:** `CombinationstabExportModuleFrontController` estende `ModuleFrontController`.
    -   **Responsabilità:** Fornisce funzionalità per esportare i dati delle combinazioni, potenzialmente per prodotti specifici o set filtrati, probabilmente in formato CSV o simile. Utile per B2B o analisi dei dati.
-   `controllers/front/index.php`
    -   **Nome classe e classe genitore:** `CombinationstabIndexModuleFrontController` estende `ModuleFrontController`.
    -   **Responsabilità:** Spesso un segnaposto o un dispatcher predefinito. Potrebbe gestire richieste AJAX generali relative alla tabella delle combinazioni che non rientrano in controller più specifici, o semplicemente reindirizzare.
-   `controllers/front/PriceCalculator.php`
    -   **Nome classe e classe genitore:** `CombinationstabPriceCalculatorModuleFrontController` estende `ModuleFrontController`.
    -   **Responsabilità:** Gestisce le richieste AJAX per calcolare e restituire dinamicamente i prezzi per le combinazioni, particolarmente rilevante per sconti sulla quantità o regole di prezzo complesse, garantendo aggiornamenti dei prezzi in tempo reale senza ricaricare la pagina.
-   `controllers/front/Reorder.php`
    -   **Nome classe e classe genitore:** `CombinationstabReorderModuleFrontController` estende `ModuleFrontController`.
    -   **Responsabilità:** Probabilmente facilita il riordino di combinazioni precedentemente acquistate, potenzialmente dalla pagina dell'account di un cliente o da un elenco dedicato di "riordino".
-   `controllers/front/Wishlist.php`
    -   **Nome classe e classe genitore:** `CombinationstabWishlistModuleFrontController` estende `ModuleFrontController`.
    -   **Responsabilità:** Gestisce le interazioni AJAX con una funzione wishlist integrata nella tabella delle combinazioni, consentendo ai clienti di aggiungere combinazioni specifiche alla loro wishlist.

#### Controller Admin Back-Office

Questi controller forniscono l'interfaccia amministrativa per il modulo.

-   `controllers/admin/AdminCombinationstabSearchController.php`
    -   **Nome scheda ed entità gestita:** "Ricerca combinazioni" (o simile, accessibile tramite il menu del modulo). Gestisce le combinazioni di `Product`.
    -   **Responsabilità:** Implementa un'interfaccia di ricerca e gestione per le combinazioni di prodotto. Questo controller probabilmente utilizza un `HelperList` o `HelperForm` per visualizzare una griglia filtrabile e ordinabile di combinazioni, consentendo agli amministratori di trovare e potenzialmente modificare rapidamente i dati delle combinazioni (es. stock, prezzo, riferimento) senza navigare alle singole pagine prodotto. Potrebbe anche gestire azioni in blocco.
-   `controllers/admin/index.php`
    -   **Nome scheda ed entità gestita:** N/A (punto di ingresso).
    -   **Responsabilità:** Un pattern comune per le directory dei controller admin. Questo file funge tipicamente da punto di ingresso predefinito o da reindirizzamento al controller principale `AdminCombinationstabSearchController`. Di solito non contiene logica diretta ma assicura che la voce di menu admin punti a un controller valido.

### 4.3 Classi e Modelli Core (`classes/`)

Il dossier del modulo indica l'assenza di classi personalizzate nella directory `classes/`. Ciò suggerisce che il modulo estende principalmente le funzionalità e gli oggetti core esistenti di PrestaShop (`Product`, `Combination`, `Attribute`, `AttributeGroup`) piuttosto che introdurre nuovi modelli di dati. Tutta la logica di business è probabilmente incapsulata nel file principale `combinationstab.php` e nei suoi controller.

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo utilizza una varietà di file JavaScript per fornire funzionalità dinamiche nel front-office e nel back-office.

-   `combinationstab/js/admin.js`
    -   **Ambito:** Back-office.
    -   **Dettagli:** Gestisce la logica JavaScript per le pagine di amministrazione del modulo, incluse le interazioni con i moduli, le chiamate AJAX per gli aggiornamenti di configurazione e potenzialmente gli elementi dinamici all'interno dell'interfaccia di `AdminCombinationstabSearchController`.
-   `combinationstab/js/atc.js`
    -   **Ambito:** Front-office.
    -   **Dettagli:** Gestisce la funzionalità "Aggiungi al carrello" per la tabella delle combinazioni. Collega gli eventi di clic ai pulsanti "Aggiungi al carrello", gestisce gli input di quantità e invia richieste AJAX al controller del carrello di PrestaShop per aggiungere le combinazioni selezionate (potenzialmente più di una alla volta) senza ricaricare la pagina.
-   `combinationstab/js/combinationstab-switch.js`
    -   **Ambito:** Front-office.
    -   **Dettagli:** Implementa la funzione "Clicca e cambia combinazione". Ascolta i clic sulle righe delle combinazioni nella tabella e aggiorna dinamicamente l'immagine principale del prodotto, il prezzo e altri dettagli del prodotto sulla pagina per riflettere la combinazione selezionata.
-   `combinationstab/js/combinationstab.js`
    -   **Ambito:** Front-office.
    -   **Dettagli:** Il file JavaScript principale del front-office per la tabella delle combinazioni. Inizializza la tabella, gestisce le interazioni generali, potenzialmente gestisce la visualizzazione dello stock, della disponibilità e degli aggiornamenti dei prezzi in base all'input o alle selezioni dell'utente.
-   `combinationstab/js/ctp-extras.js`
    -   **Ambito:** Front-office.
    -   **Dettagli:** Contiene funzionalità JavaScript aggiuntive, non core, per la tabella delle combinazioni, come la visualizzazione di tooltip, piccoli miglioramenti dell'interfaccia utente o interazioni specifiche non coperte dagli script principali.
-   `combinationstab/js/ctp-filters.js`
    -   **Ambito:** Front-office.
    -   **Dettagli:** Implementa la logica di filtraggio per la tabella delle combinazioni. Ascolta i cambiamenti nei menu a discesa o nei campi di input dei filtri, nasconde/mostra dinamicamente le righe della tabella in base ai valori degli attributi selezionati e aggiorna le combinazioni visibili.
-   `combinationstab/js/ctp-mobile.js`
    -   **Ambito:** Front-office.
    -   **Dettagli:** Gestisce il comportamento responsivo della tabella delle combinazioni, implementando in particolare la funzione "Layout a schede mobile". Rileva le dimensioni dello schermo e trasforma la tabella in un layout basato su schede per una migliore usabilità mobile.
-   `combinationstab/js/ctp-wishlist-toast.js`
    -   **Ambito:** Front-office.
    -   **Dettagli:** Fornisce un feedback visivo (es. una notifica toast) quando una combinazione viene aggiunta a una wishlist, migliorando l'esperienza utente.
-   `combinationstab/lib/searchTool/views/js/autocomplete.js`
    -   **Ambito:** Back-office (probabilmente).
    -   **Dettagli:** Fornisce la funzionalità di completamento automatico, probabilmente per i campi di ricerca di prodotti o combinazioni all'interno delle interfacce di amministrazione del modulo (es. `AdminCombinationstabSearchController`).
-   `combinationstab/views/js/wishlist.js`
    -   **Ambito:** Front-office.
    -   **Dettagli:** JavaScript dedicato per l'integrazione della wishlist, gestendo le chiamate AJAX per aggiungere/rimuovere elementi dalla wishlist direttamente dalla tabella delle combinazioni.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo include diversi file CSS sia per lo stile del front-office che per l'amministrazione del back-office.

-   `combinationstab/css/admin.css`
    -   **Ambito:** Stile del modulo di amministrazione del back-office.
    -   **Dettagli:** Stila la pagina di configurazione del modulo e qualsiasi interfaccia di amministrazione personalizzata (come `AdminCombinationstabSearchController`), garantendo un aspetto coerente all'interno del back office di PrestaShop.
-   `combinationstab/css/combinationstab.css`
    -   **Ambito:** Stile del cliente del front-office.
    -   **Dettagli:** Contiene lo stile principale per la tabella delle combinazioni, inclusi il layout della tabella, la spaziatura delle celle, l'allineamento del testo e la reattività di base.
-   `combinationstab/css.css`
    -   **Ambito:** Stile del cliente del front-office.
    -   **Dettagli:** Potenzialmente un foglio di stile più vecchio o supplementare per il front-office, o override specifici.
-   `combinationstab/lib/searchTool/views/css/autocomplete.css`
    -   **Ambito:** Back-office (probabilmente).
    -   **Dettagli:** Stili per i campi di ricerca con completamento automatico utilizzati nel pannello di amministrazione.
-   `combinationstab/views/css/ctp-admin.css`
    -   **Ambito:** Stile del modulo di amministrazione del back-office.
    -   **Dettagli:** Stile amministrativo aggiuntivo o specifico, potenzialmente per nuove funzionalità o override di `admin.css`.
-   `combinationstab/views/css/wishlist.css`
    -   **Ambito:** Stile del cliente del front-office.
    -   **Dettagli:** Stili per il pulsante della wishlist e qualsiasi elemento associato all'interno della tabella delle combinazioni.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo utilizza i template Smarty per il rendering di tutte le sue viste del front-office e del back-office.

#### Template degli hook (`views/templates/hook/`)

Questi template sono progettati per essere renderizzati quando vengono eseguiti specifici hook di PrestaShop.

-   `views/templates/hook/columns/cells.tpl`
    -   **Hook:** Probabilmente renderizzato all'interno del template principale della tabella delle combinazioni.
    -   **Output:** Definisce la struttura e il contenuto delle singole celle di dati all'interno delle righe della tabella (es. visualizzazione dei valori degli attributi, prezzo, input della quantità).
-   `views/templates/hook/columns/headers.tpl`
    -   **Hook:** Probabilmente renderizzato all'interno del template principale della tabella delle combinazioni.
    -   **Output:** Definisce le celle di intestazione per la tabella delle combinazioni, visualizzando i titoli delle colonne come "Immagine", "Taglia", "Prezzo".
-   `views/templates/hook/columns/_wishlist_btn.tpl`
    -   **Hook:** Integrato nelle righe delle combinazioni.
    -   **Output:** Rende il pulsante o l'icona "Aggiungi alla wishlist" per ogni combinazione nella tabella.
-   `views/templates/hook/customer_account.tpl`
    -   **Hook:** `displayCustomerAccount`
    -   **Output:** Aggiunge un link o un blocco alla pagina dell'account del cliente, potenzialmente per accedere a elenchi di riordino, dati esportati o gestione della wishlist.
-   `views/templates/hook/grid/_axis_label.tpl`
    -   **Hook:** Utilizzato internamente quando `ctp_view_mode` è impostato su un layout a griglia.
    -   **Output:** Rende le etichette per gli assi (righe/colonne) di una visualizzazione di combinazione in stile griglia.
-   `views/templates/hook/grid/_cell.tpl`
    -   **Hook:** Utilizzato internamente quando `ctp_view_mode` è impostato su un layout a griglia.
    -   **Output:** Rende le singole celle all'interno di una visualizzazione di combinazione in stile griglia, contenente i dettagli della combinazione.
-   `views/templates/hook/productfooter.tpl`
    -   **Hook:** `displayProductFooter`
    -   **Output:** Il template principale per il rendering della tabella delle combinazioni quando posizionata sotto il contenuto principale del prodotto. Questo è spesso il posizionamento predefinito o più comune.
-   `views/templates/hook/productfooter_grid.tpl`
    -   **Hook:** `displayProductFooter` (condizionale sulla modalità di visualizzazione).
    -   **Output:** Un template alternativo per `displayProductFooter` specificamente per il rendering delle combinazioni in un layout a griglia invece di una tabella tradizionale.
-   `views/templates/hook/quickViewScripts.tpl`
    -   **Hook:** Potenzialmente `displayHeader` o `actionFrontControllerSetMedia` (per i modali di visualizzazione rapida).
    -   **Output:** Include il JavaScript necessario o inizializza la funzionalità del modulo specificamente per i modali di visualizzazione rapida del prodotto, garantendo che la tabella delle combinazioni funzioni all'interno di questi pop-up.
-   `views/templates/hook/tab.tpl`
    -   **Hook:** `displayProductTabContent` (o simile per le schede prodotto).
    -   **Output:** Rende la tabella delle combinazioni all'interno di una scheda prodotto dedicata sulla pagina del prodotto.
-   `views/templates/hook/volume_discounts.tpl`
    -   **Hook:** Integrato nelle righe delle combinazioni o come tooltip.
    -   **Output:** Visualizza informazioni sugli sconti sulla quantità per combinazioni specifiche.
-   `views/templates/hook/_filters.tpl`
    -   **Hook:** Renderizzato sopra la tabella delle combinazioni.
    -   **Output:** Rende l'interfaccia di filtraggio degli attributi per la tabella delle combinazioni.
-   `views/templates/hook/_toolbar.tpl`
    -   **Hook:** Renderizzato sopra la tabella delle combinazioni.
    -   **Output:** Rende una barra degli strumenti, potenzialmente contenente filtri, ricerca o altri elementi interattivi per la tabella delle combinazioni.

#### Template di amministrazione (`views/templates/admin/`)

Questi template vengono utilizzati per la configurazione del back-office del modulo e le schermate di gestione.

-   `views/templates/admin/b2b.tpl`
    -   **Output:** Template per impostazioni o funzionalità specifiche B2B all'interno del pannello di amministrazione.
-   `views/templates/admin/b2b_groups.tpl`
    -   **Output:** Template per la gestione dei gruppi di clienti B2B o delle loro impostazioni specifiche di prezzo/visibilità.
-   `views/templates/admin/column_editor.tpl`
    -   **Output:** Fornisce un'interfaccia per gli amministratori per personalizzare l'ordine e la visibilità delle colonne nella tabella delle combinazioni del front-office.
-   `views/templates/admin/getCombinations.tpl`
    -   **Output:** Utilizzato da `AdminCombinationstabSearchController` per visualizzare un elenco o una griglia di combinazioni.
-   `views/templates/admin/getProducts.tpl`
    -   **Output:** Utilizzato da `AdminCombinationstabSearchController` o altri strumenti di amministrazione per visualizzare un elenco di prodotti.
-   `views/templates/admin/grid_block_editor.tpl`
    -   **Output:** Interfaccia per la configurazione della visualizzazione a griglia delle combinazioni, potenzialmente definendo quali attributi formano righe e colonne.
-   `views/templates/admin/menu.tpl`
    -   **Output:** Rende le voci di sottomenu del modulo all'interno del back office di PrestaShop.
-   `views/templates/admin/overrides_entity.tpl`
    -   **Output:** Template per la gestione degli override specifici dell'entità (es. impostazioni specifiche del prodotto per la tabella).
-   `views/templates/admin/overrides_fields.tpl`
    -   **Output:** Template per la gestione degli override specifici del campo.
-   `views/templates/admin/overrides_list.tpl`
    -   **Output:** Template per elencare e gestire i vari override configurati per il modulo.
-   `views/templates/admin/presets.tpl`
    -   **Output:** Interfaccia per salvare e caricare preset di configurazione per la tabella delle combinazioni.
-   `views/templates/admin/selectedProducts.tpl`
    -   **Output:** Visualizza un elenco di prodotti che sono stati selezionati per configurazioni o override specifici del modulo.
-   `views/templates/admin/subtabs.tpl`
    -   **Output:** Rende le schede di sotto-navigazione all'interno dell'interfaccia di configurazione del modulo.
-   `views/templates/admin/tabs.tpl`
    -   **Output:** Rende le schede di navigazione principali per la configurazione del modulo.
-   `views/templates/admin/tabstype.tpl`
    -   **Output:** Opzioni di configurazione relative a come la tabella delle combinazioni viene visualizzata all'interno delle schede prodotto.

#### Template del front-office (`views/templates/front/`)

-   `views/templates/front/wishlist.tpl`
    -   **Output:** Rende l'interfaccia della wishlist del front-office, potenzialmente una pagina dedicata o un modale, mostrando gli elementi aggiunti alla wishlist tramite la tabella delle combinazioni.

#### Altri template

-   `combinationstab/lib/searchTool/views/scripts.tpl`
    -   **Output:** Include snippet JavaScript o inizializza script per la funzionalità dello strumento di ricerca.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

Il dossier del modulo indica l'assenza di file SQL personalizzati. Ciò implica che il modulo utilizza principalmente la tabella `ps_configuration` di PrestaShop per memorizzare le sue impostazioni e si basa sulle tabelle core esistenti come `ps_product_attribute`, `ps_product_attribute_combination`, `ps_product_attribute_shop`, `ps_stock_available`, ecc., per i dati delle combinazioni.

-   **`ps_configuration`**: Memorizza tutte le impostazioni del modulo (es. `CTP_POSITION`, `CTP_IMAGE`, `CTP_PRICE_LOGGED`, `CTP_MOBILE_CARD_LAYOUT`).

#### Tabella degli hook registrati

Il modulo si registra a vari hook di PrestaShop per iniettare il suo contenuto e la sua funzionalità.

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `ActionAdminControllerSetMedia` | Quando un controller admin viene inizializzato e i media (JS/CSS) sono impostati. | Inietta JS/CSS specifici del modulo nel Back Office. |
| `displayRightColumn` | Rende il contenuto nella colonna destra del front office. | Visualizza la tabella delle combinazioni nella colonna destra (meno comune per le tabelle). |
| `displayProductFooter` | Rende il contenuto sotto le informazioni principali del prodotto nella pagina del prodotto. | Hook primario per la visualizzazione della tabella delle combinazioni sotto il prodotto. |
| `displayHeader` | Rende il contenuto nella sezione `<head>` del front office. | Inietta JS/CSS specifici del modulo, meta tag o altri elementi head per la funzionalità del front-office. |
| `displayProductExtraContent` | Rende blocchi di contenuto aggiuntivi nella pagina del prodotto. | Fornisce flessibilità per posizionare la tabella delle combinazioni in un blocco di contenuto personalizzato. |
| `displayRightColumnProduct` | Rende il contenuto nella colonna destra specificamente nella pagina del prodotto. | Simile a `displayRightColumn` ma mirato alle pagine prodotto. |
| `displayCustomerAccount` | Rende il contenuto nella pagina dell'account del cliente. | Aggiunge link o informazioni relative a riordini, wishlist o esportazioni. |
| `actionUpdateQuantity` | Dopo l'aggiornamento della quantità (stock) di un prodotto. | Potenzialmente attiva aggiornamenti alla visualizzazione della tabella delle combinazioni (es. stato "esaurito"). |
| `displayProductListFunctionalButtons` | Rende i pulsanti negli elenchi di prodotti (es. pagine di categoria). | Potrebbe aggiungere pulsanti di visualizzazione rapida o confronto relativi alle combinazioni. |
| `displayExtraLeft` | Rende il contenuto in una colonna sinistra extra (se il tema lo supporta). | Un'altra opzione di posizionamento per la tabella delle combinazioni. |
| `CombinationsTable` | **Hook personalizzato** | Un hook personalizzato definito dal modulo stesso, che consente ad altri moduli o temi di integrarsi o sovrascrivere il suo output della tabella. |
| `displayLeftColumnProduct` | Rende il contenuto nella colonna sinistra specificamente nella pagina del prodotto. | Simile a `displayRightColumnProduct` ma per la colonna sinistra. |
| `displayProductTabContent` | Rende il contenuto all'interno di una scheda prodotto. | Visualizza la tabella delle combinazioni in una scheda prodotto dedicata. |
| `displayCombinationsTable` | **Hook personalizzato** | Un altro hook personalizzato, probabilmente per il rendering principale della tabella delle combinazioni, offrendo un'alternativa a `displayProductFooter`. |
| `displayProductActions` | Rende il contenuto vicino al pulsante "Aggiungi al carrello" nella pagina del prodotto. | Potrebbe essere utilizzato per un selettore di combinazioni compatto o pulsanti di aggiunta rapida. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, il supporto tecnico e qualsiasi domanda relativa al modulo "Tabella combinazioni pagina prodotto", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è pronto ad assistervi.
