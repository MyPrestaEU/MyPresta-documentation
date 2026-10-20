---
title: "Export Products Pro - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Export Products Pro di MyPresta.eu."
sidebar:
  label: "Export Products Pro - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Export Products Pro su MyPresta.eu](https://mypresta.eu/modules/administration-tools/export-products-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/export-products-pro/)
>
> ---


# Export Products Pro

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per il funzionamento generale di PrestaShop, ma questo modulo non ha requisiti esotici specifici al di là di un ambiente di hosting PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Export Products Pro)

Questa è la schermata di configurazione principale dove definisci il comportamento generale e le impostazioni per le tue esportazioni di prodotti.

#### Impostazioni Generali

-   **Formato di esportazione**:

    -   **Cosa fa questa impostazione:** Determina il formato del file per i tuoi dati esportati.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su CSV:* Il modulo genererà un file Comma Separated Values, ampiamente compatibile con software di fogli di calcolo come Excel, Google Sheets o LibreOffice Calc. Questo è il formato più comune e versatile.
        -   *Quando impostato su XML:* Il modulo genererà un file Extensible Markup Language, spesso utilizzato per uno scambio di dati più strutturato tra sistemi o per feed di prodotti specifici (es. Google Shopping).
    -   **Valore consigliato:** CSV per uso generale e analisi con fogli di calcolo. XML se hai un sistema specifico che lo richiede.
    -   **Scenario / esempio per il commerciante:** Se vuoi aprire i dati in Excel per analizzare i prezzi, scegli CSV. Se stai creando un feed per un'applicazione di terze parti che specifica XML, scegli XML.
-   **Delimitatore**:

    -   **Cosa fa questa impostazione:** Questo carattere separa le diverse colonne (campi) nel tuo file CSV.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su virgola (,):* Ogni pezzo di dato in una riga sarà separato da una virgola. Questo è standard per molti sistemi.
        -   *Quando impostato su punto e virgola (;):* Ogni pezzo di dato sarà separato da un punto e virgola. Questo è comune in alcune regioni europee o quando le virgole potrebbero apparire all'interno dei tuoi dati di prodotto (es. nelle descrizioni), causando problemi di parsing.
    -   **Valore consigliato:** Virgola (`,`) per la maggior parte dei casi. Se il tuo software di fogli di calcolo ha difficoltà ad aprire correttamente il CSV, prova il punto e virgola (`;`).
    -   **Scenario / esempio per il commerciante:** Se apri il tuo CSV in Excel e tutti i dati appaiono in una colonna, prova a cambiare il delimitatore in punto e virgola e a riesportare.
-   **Esporta solo prodotti attivi**:

    -   **Cosa fa questa impostazione:** Controlla se solo i prodotti attualmente visibili e acquistabili nel tuo negozio sono inclusi nell'esportazione.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (Sì):* Verranno esportati solo i prodotti con lo "Stato" impostato su "Online" o "Attivo" nel back office di PrestaShop. Questo è utile per l'inventario corrente.
        -   *Quando disabilitato (No):* Verranno esportati tutti i prodotti, inclusi quelli contrassegnati come inattivi o disabilitati. Questo è utile per un backup completo del catalogo o per un audit.
    -   **Valore consigliato:** Sì, per la maggior parte delle esportazioni operative.
    -   **Scenario / esempio per il commerciante:** Se stai generando un feed di prodotti per Google Shopping, vuoi solo prodotti attivi, quindi abilita questa opzione. Se stai facendo un backup completo dei dati, disabilitala.
-   **Esporta solo prodotti in stock**:

    -   **Cosa fa questa impostazione:** Filtra l'esportazione per includere solo i prodotti che attualmente hanno una quantità maggiore di zero.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (Sì):* Verranno esportati solo i prodotti attualmente in stock.
        -   *Quando disabilitato (No):* Verranno esportati i prodotti indipendentemente dal loro livello di stock (in stock o esauriti).
    -   **Valore consigliato:** Sì, se stai creando un feed per le vendite o la disponibilità attuale.
    -   **Scenario / esempio per il commerciante:** Se stai inviando un elenco di prodotti disponibili a un dropshipper, abilita questa opzione. Se hai bisogno di vedere tutti i prodotti, inclusi quelli che devi riordinare, disabilitala.
-   **Esporta immagini prodotto**:

    -   **Cosa fa questa impostazione:** Determina se gli URL delle immagini dei tuoi prodotti sono inclusi nell'esportazione.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (Sì):* Il file CSV/XML conterrà colonne con gli URL delle immagini dei tuoi prodotti.
        -   *Quando disabilitato (No):* Gli URL delle immagini verranno omessi, con conseguente riduzione delle dimensioni del file se le immagini non sono necessarie.
    -   **Valore consigliato:** Sì, se hai bisogno di immagini per marketplace o cataloghi esterni.
    -   **Scenario / esempio per il commerciante:** Se stai aggiornando un catalogo prodotti su un'altra piattaforma che richiede gli URL delle immagini, abilita questa opzione.
-   **Esporta descrizione breve prodotto**:

    -   **Cosa fa questa impostazione:** Include la descrizione breve (riepilogo) dei tuoi prodotti nell'esportazione.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (Sì):* La descrizione breve per ogni prodotto sarà inclusa come colonna.
        -   *Quando disabilitato (No):* La descrizione breve verrà omessa.
    -   **Valore consigliato:** Sì, poiché le descrizioni brevi sono spesso utilizzate per gli elenchi di prodotti e i risultati di ricerca.
    -   **Scenario / esempio per il commerciante:** Se stai creando un feed di prodotti per un sito di confronto che visualizza descrizioni brevi, abilita questa opzione.
-   **Esporta descrizione prodotto**:

    -   **Cosa fa questa impostazione:** Include la descrizione completa e dettagliata dei tuoi prodotti nell'esportazione.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (Sì):* La descrizione completa del prodotto sarà inclusa come colonna.
        -   *Quando disabilitato (No):* La descrizione completa verrà omessa.
    -   **Valore consigliato:** Sì, per un'esportazione completa dei dati.
    -   **Scenario / esempio per il commerciante:** Se stai migrando il tuo negozio a una nuova piattaforma e hai bisogno di tutto il contenuto del prodotto, abilita questa opzione.
-   **Ricorda impostazioni**:

    -   **Cosa fa questa impostazione:** Se abilitata, il modulo salverà le tue ultime impostazioni di esportazione utilizzate (filtri, campi selezionati) per la tua prossima esportazione.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (Sì):* Il modulo pre-compilerà il modulo di esportazione con le tue scelte precedenti, risparmiando tempo per le esportazioni ripetitive.
        -   *Quando disabilitato (No):* Il modulo di esportazione si resetterà sempre alle impostazioni predefinite ogni volta che lo visiterai.
    -   **Valore consigliato:** Sì, se esegui frequentemente esportazioni simili.
    -   **Scenario / esempio per il commerciante:** Se esporti regolarmente un elenco di prodotti attivi e in stock con campi specifici, abilitare questa opzione renderà il tuo flusso di lavoro più veloce.

#### Opzioni di Filtro

-   **Esporta prodotti dalla categoria**:

    -   **Cosa fa questa impostazione:** Ti consente di selezionare categorie di prodotti specifiche da includere nella tua esportazione.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando vengono selezionate categorie specifiche:* Verranno esportati solo i prodotti appartenenti a tali categorie.
        -   *Quando non vengono selezionate categorie (o vengono selezionate tutte):* Tutti i prodotti, indipendentemente dalla categoria, verranno considerati per l'esportazione (soggetti ad altri filtri).
    -   **Valore consigliato:** Seleziona categorie specifiche se hai bisogno di un'esportazione mirata; altrimenti, lascia deselezionato per un catalogo completo.
    -   **Scenario / esempio per il commerciante:** Se vuoi esportare solo prodotti dalla tua categoria "Elettronica", selezionala qui.
-   **Esporta solo categorie principali**:

    -   **Cosa fa questa impostazione:** Se hai selezionato delle categorie, questa opzione affina ulteriormente se i prodotti delle sottocategorie sono inclusi.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (Sì):* Verranno esportati solo i prodotti direttamente assegnati alle categorie principali selezionate. I prodotti nelle loro sottocategorie saranno esclusi.
        -   *Quando disabilitato (No):* Verranno esportati i prodotti dalle categorie principali selezionate E tutte le loro sottocategorie.
    -   **Valore consigliato:** No, per la maggior parte dei casi, poiché di solito si desiderano anche i prodotti delle sottocategorie. Abilita solo se hai un motivo specifico per escludere i prodotti delle sottocategorie.
    -   **Scenario / esempio per il commerciante:** Se hai "Abbigliamento" come categoria principale e "T-shirt" come sottocategoria, abilitando questa opzione esporteresti i prodotti direttamente in "Abbigliamento" ma non quelli in "T-shirt".
-   **Esporta prodotti dal produttore**:

    -   **Cosa fa questa impostazione:** Ti consente di filtrare i prodotti in base al loro produttore assegnato.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando vengono selezionati produttori specifici:* Verranno esportati solo i prodotti di tali produttori.
        -   *Quando non vengono selezionati produttori (o vengono selezionati tutti):* Verranno considerati i prodotti di tutti i produttori.
    -   **Valore consigliato:** Seleziona produttori specifici per esportazioni mirate.
    -   **Scenario / esempio per il commerciante:** Se devi inviare un elenco di prodotti a un marchio specifico per la revisione, seleziona il loro produttore qui.
-   **Esporta prodotti dal fornitore**:

    -   **Cosa fa questa impostazione:** Ti consente di filtrare i prodotti in base al loro fornitore assegnato.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando vengono selezionati fornitori specifici:* Verranno esportati solo i prodotti di tali fornitori.
        -   *Quando non vengono selezionati fornitori (o vengono selezionati tutti):* Verranno considerati i prodotti di tutti i fornitori.
    -   **Valore consigliato:** Seleziona fornitori specifici per esportazioni mirate.
    -   **Scenario / esempio per il commerciante:** Se devi fornire un elenco di prodotti che hai in magazzino da un particolare fornitore, selezionalo qui.

### 2.2 Schermata Amministrativa Dedicata: Dashboard Export Products Pro (Back Office > Catalogo > Export Products Pro)

Questa è l'interfaccia principale per avviare e gestire le esportazioni dei tuoi prodotti.

-   **Nome schermata e posizione menu:** **Catalogo > Export Products Pro**
-   **Azioni e impostazioni disponibili:**
    -   **Pulsante Esporta:** Questo è il pulsante di azione principale. Cliccandoci si avvierà il processo di esportazione in base alle impostazioni che hai configurato in questa pagina.
    -   **Selezione campi:** Sotto le impostazioni generali, troverai un elenco completo di tutti i campi prodotto e combinazione disponibili. Puoi selezionare o deselezionare individualmente quali campi desideri includere nella tua esportazione.
        -   **Campi prodotto:** Include dettagli standard del prodotto come ID, nome, riferimento, EAN13, UPC, prezzo, quantità, peso, descrizioni, ecc.
        -   **Campi combinazione:** Se i tuoi prodotti hanno combinazioni (es. taglia, colore), vedrai campi specifici per le combinazioni come "ID Combinazione", "Attributo (Nome:Tipo:Posizione)", "Valore (Valore:Posizione)", "Impatto sul prezzo", "Impatto sul peso", "Predefinito (0 = No, 1 = Sì)", "Data disponibilità combinazione".
    -   **Effetto delle modifiche:**
        -   **Selezione/Deselezione campi:** Solo i campi selezionati appariranno come colonne nel tuo file CSV/XML esportato. Questo ti consente di creare esportazioni altamente personalizzate, includendo solo i dati di cui hai bisogno e omettendo informazioni non necessarie.
    -   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
        1.  Naviga su **Catalogo > Export Products Pro**.
        2.  Rivedi le "Impostazioni Generali" e le "Opzioni di Filtro" nella parte superiore della pagina. Regolale in base alla necessità di prodotti attivi, prodotti in stock, categorie specifiche, produttori o fornitori.
        3.  Seleziona attentamente i "Campi prodotto" e i "Campi combinazione" che desideri includere nella tua esportazione. Se non sei sicuro, è spesso più sicuro selezionare più campi inizialmente e poi rimuovere le colonne indesiderate nel tuo software di fogli di calcolo.
        4.  Clicca sul pulsante "Esporta". Il modulo genererà e ti chiederà di scaricare il file CSV o XML.
        5.  Apri il file scaricato nel tuo software di fogli di calcolo preferito (es. Excel, Google Sheets) per verificare i dati e il formato.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Configurazione Modulo** | Formato di esportazione | CSV | Determina il tipo di file di output (CSV o XML). |
| | Delimitatore | Virgola (`,`) | Carattere che separa i campi nel CSV. Cambia se si verificano problemi di parsing. |
| | Esporta solo prodotti attivi | Sì | Include solo prodotti attivi. |
| | Esporta solo prodotti in stock | Sì | Include solo prodotti con quantità > 0. |
| | Esporta immagini prodotto | Sì | Include gli URL delle immagini nell'esportazione. |
| | Esporta descrizione breve prodotto | Sì | Include la descrizione breve del prodotto. |
| | Esporta descrizione prodotto | Sì | Include la descrizione completa del prodotto. |
| | Ricorda impostazioni | Sì | Salva le tue ultime scelte di esportazione per comodità. |
| | Esporta prodotti dalla categoria | (Nessuna selezionata) | Filtra l'esportazione per categorie selezionate. |
| | Esporta solo categorie principali | No | Se le categorie sono selezionate, include/esclude i prodotti delle sottocategorie. |
| | Esporta prodotti dal produttore | (Nessuno selezionato) | Filtra l'esportazione per produttori selezionati. |
| | Esporta prodotti dal fornitore | (Nessuno selezionato) | Filtra l'esportazione per fornitori selezionati. |
| **Dashboard Export Products Pro** | **Selezione campi** | Varia in base alle esigenze | Scegli attributi specifici di prodotto/combinazione da includere come colonne nel file di esportazione. |
| | Pulsante Esporta | N/A | Avvia l'esportazione del prodotto in base a tutte le impostazioni configurate. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Il mio file CSV esportato appare illeggibile o tutti i dati sono in una colonna quando lo apro in Excel.**
**R1:** Questo è solitamente un problema di delimitatore o di codifica dei caratteri.

-   **Soluzione 1 (Delimitatore):** Torna alla configurazione del modulo, cambia l'impostazione "Delimitatore" da virgola (`,`) a punto e virgola (`;`) e riesporta. Prova ad aprire il nuovo file.
-   **Soluzione 2 (Codifica):** Quando apri il CSV in Excel, usa l'opzione "Dati > Da testo/CSV". Nella procedura guidata di importazione, assicurati di selezionare l'opzione corretta "Origine file" o "Codifica" (solitamente `UTF-8`) e specifica il delimitatore corretto.

**D2: Alcuni prodotti mancano dalla mia esportazione, ma so che esistono nel mio negozio.**
**R2:** Controlla le impostazioni del filtro nella configurazione del modulo:

-   **Soluzione:** Assicurati che "Esporta solo prodotti attivi" e "Esporta solo prodotti in stock" siano impostati correttamente per le tue esigenze. Se hai selezionato categorie, produttori o fornitori specifici, ricontrolla che i prodotti mancanti rientrino in quei filtri. Se vuoi tutto, assicurati che nessun filtro sia selezionato.

**D3: Il processo di esportazione richiede molto tempo o va in timeout per cataloghi di grandi dimensioni.**
**R3:** L'esportazione di migliaia di prodotti può essere intensiva in termini di risorse.

-   **Soluzione 1:** Prova a esportare lotti più piccoli utilizzando i filtri "Esporta prodotti dalla categoria", "produttore" o "fornitore".
-   **Soluzione 2:** Se hai accesso alle impostazioni del tuo server, potresti dover aumentare temporaneamente `memory_limit` e `max_execution_time` di PHP nel tuo file `php.ini`. Contatta il tuo provider di hosting per assistenza.
-   **Soluzione 3:** Deseleziona i campi non necessari per ridurre la quantità di dati elaborati.

**D4: Come traduco le intestazioni di colonna nel file esportato?**
**R4:** Le intestazioni di colonna nel file esportato si basano generalmente sui nomi dei campi interni o sulle etichette predefinite di PrestaShop e non sono direttamente traducibili tramite l'interfaccia del modulo.

-   **Soluzione:** Il modo più semplice è aprire il file CSV esportato in un programma di fogli di calcolo (come Excel o Google Sheets) e rinominare manualmente le intestazioni di colonna nella lingua o terminologia desiderata. Salva il file con le nuove intestazioni.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

Questa sezione fornisce un'analisi approfondita della struttura tecnica del modulo Export Products Pro, destinata a sviluppatori, webmaster e agenzie tecniche.

### 4.1 Panoramica dell'Architettura

Il modulo `Export Products Pro` segue il modello MVC standard di PrestaShop, concentrandosi principalmente sulla funzionalità di back-office. Sfrutta i Controller Admin per la sua interfaccia utente e classi personalizzate per la gestione dei dati e la generazione dei feed. La logica centrale del modulo risiede nel suo file principale `exportproducts.php` e nel `AdminExportProductsController` che gestisce il processo di esportazione e la configurazione. Utilizza `ObjectModel` per i suoi dati personalizzati, se presenti, sebbene in questo caso interagisca principalmente con i dati di prodotto core di PrestaShop.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

-   `controllers/front/feed.php`
    -   **Nome classe e classe padre:** `ExportProductsFeedModuleFrontController` che estende `ModuleFrontController`.
    -   **Responsabilità:** Questo controller è probabilmente responsabile della generazione di un feed di prodotti (ad esempio, XML o CSV) che può essere accessibile direttamente tramite un URL. Gestirebbe la logica per interrogare i prodotti in base a parametri specifici e produrli nel formato scelto. Questo potrebbe essere utilizzato per la generazione automatica di feed per servizi esterni.
-   `controllers/front/index.php`
    -   **Nome classe e classe padre:** `ExportProductsIndexModuleFrontController` che estende `ModuleFrontController`.
    -   **Responsabilità:** Questo controller potrebbe fungere da punto di ingresso predefinito o da fallback per le richieste front-office relative al modulo. Data la funzione primaria del modulo, potrebbe reindirizzare o visualizzare un semplice messaggio, oppure potrebbe essere un segnaposto per future funzionalità front-office.

#### Controller Admin Back-Office

-   `controllers/admin/AdminExportProducts.php`
    -   **Nome tab e entità gestita:** Questo controller gestisce la dashboard principale "Export Products Pro" nel Back Office di PrestaShop, accessibile tramite **Catalogo > Export Products Pro**. Non gestisce una singola entità `ObjectModel` nel senso tradizionale, ma piuttosto orchestra il processo di esportazione dei prodotti.
    -   **Responsabilità:**
        -   Visualizza il modulo di configurazione per le impostazioni di esportazione (filtri, formato, delimitatore, ecc.).
        -   Gestisce la richiesta POST quando si clicca sul pulsante "Esporta".
        -   Elabora i campi prodotto e combinazione selezionati.
        -   Interroga il database di PrestaShop per i dati di prodotto e combinazione in base ai filtri applicati.
        -   Genera il contenuto del file CSV o XML.
        -   Avvia il download del file nel browser dell'utente.
        -   Gestisce la funzionalità `ep_remember_settings` per persistere le scelte dell'utente.
-   `controllers/admin/index.php`
    -   **Responsabilità:** Questo è tipicamente un file vuoto o un file contenente una semplice istruzione `die('No direct script access');`, che funge da misura di sicurezza per impedire l'accesso diretto alla directory `controllers/admin`. Non contiene logica di controller attiva.

### 4.3 Classi Core e Modelli (`classes/`)

-   `classes/ExportProductsFeed.php`
    -   **Con quale tabella del database interagisce:** Questa classe probabilmente interagisce con varie tabelle core di PrestaShop come `ps_product`, `ps_product_lang`, `ps_product_shop`, `ps_category_product`, `ps_manufacturer`, `ps_supplier`, `ps_image`, `ps_product_attribute`, `ps_product_attribute_combination`, `ps_attribute`, `ps_attribute_lang`, `ps_attribute_group`, `ps_attribute_group_lang`, ecc.
    -   **Se estende `ObjectModel` e definizione dei campi `$definition`:** È improbabile che estenda direttamente `ObjectModel`, poiché il suo ruolo primario è *interrogare* ed *elaborare* i dati di prodotto esistenti piuttosto che gestire una nuova entità di database. Contenerebbe metodi per recuperare i dati di prodotto con varie join (categorie, produttori, fornitori, immagini, descrizioni).
    -   **Metodi pubblici chiave e logica di business incapsulata:**
        -   Metodi per recuperare i dati di prodotto con varie join (categorie, produttori, fornitori, immagini, descrizioni).
        -   Metodi per gestire le combinazioni di prodotti e i loro attributi specifici.
        -   Logica per applicare filtri (attivi, in stock, categoria, produttore, fornitore).
        -   Metodi per formattare i dati in strutture CSV o XML.
        -   Potenzialmente metodi per gestire grandi set di dati per prevenire l'esaurimento della memoria.
-   `classes/index.php`
    -   **Responsabilità:** Simile a `controllers/admin/index.php`, questo è un file di sicurezza per impedire l'elenco diretto delle directory o l'esecuzione di file all'interno della directory `classes/`.

### 4.4 Risorse JavaScript (`views/js/`)

L'inventario del modulo fornito non indica file JavaScript personalizzati (`[]`). Ciò suggerisce che il front-end del modulo (configurazione del Back Office) si basa interamente sulle librerie JavaScript native di PrestaShop (ad esempio, jQuery, JS core di PrestaShop) per la gestione dei moduli, oppure la sua interfaccia è abbastanza semplice da non richiedere interazioni complesse lato client oltre alle normali sottomissioni di moduli.

### 4.5 Fogli di Stile CSS (`views/css/`)

L'inventario del modulo fornito non indica file CSS personalizzati (`[]`). Ciò implica che l'interfaccia del Back Office del modulo utilizza lo stile predefinito del back-office di PrestaShop, garantendo un aspetto coerente senza introdurre stili personalizzati.

### 4.6 Struttura del Template Smarty (`views/templates/`)

-   **`exportproducts/script.tpl`**
    -   **Ambito:** Probabilmente un template generico utilizzato per incorporare piccoli snippet JavaScript o variabili di configurazione direttamente nell'HTML, possibilmente agganciato a `displayHeader` o `displayBackOfficeHeader` se deve essere eseguito su pagine specifiche. Dato che non ci sono file JS, questo potrebbe contenere JS inline per la validazione del modulo o il comportamento dinamico.
-   **`exportproducts/views/templates/admin/dashboard.tpl`**
    -   **Ambito:** Template amministrativo.
    -   **Scopo:** Questo è il template principale per `AdminExportProductsController`. Renderizza l'intero modulo di configurazione dell'esportazione, incluse le impostazioni generali, le opzioni di filtro e l'ampio elenco di campi prodotto e combinazione che il commerciante può selezionare per l'esportazione. Contiene anche il pulsante "Esporta".
-   **`exportproducts/views/templates/admin/form_header.tpl`**
    -   **Ambito:** Template amministrativo.
    -   **Scopo:** Questo template probabilmente renderizza una sezione di intestazione comune per i moduli di configurazione amministrativi, potenzialmente includendo il titolo del modulo, la descrizione e forse del testo introduttivo o dei link. È progettato per essere incluso nella parte superiore di altri template amministrativi (come `dashboard.tpl`) per coerenza.

### 4.7 Schema del Database e Mappa degli Hook

-   **Tabelle del Database**:

    -   Il modulo non sembra creare le proprie tabelle di database personalizzate.
    -   Memorizza le sue impostazioni di configurazione (ad esempio, `ep_export_format`, `ep_export_active`, `ep_remember_settings`, `ep_export_categories_onlycats`, ecc.) nella tabella standard di PrestaShop `ps_configuration`. Queste chiavi sono prefissate con `ep_` per "Export Products".
    -   Legge principalmente i dati dalle tabelle core di PrestaShop: `ps_product`, `ps_product_lang`, `ps_product_shop`, `ps_category_product`, `ps_manufacturer`, `ps_supplier`, `ps_image`, `ps_product_attribute`, `ps_product_attribute_combination`, `ps_attribute`, `ps_attribute_lang`, `ps_attribute_group`, `ps_attribute_group_lang`, ecc.
-   **Tabella degli Hook Registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayModuleRoutes` | Durante la generazione delle rotte per i moduli. | Consente al modulo di registrare URL amichevoli personalizzati per i suoi controller front-office (ad esempio, `/feed` per `feed.php`). |
| `moduleRoutes` | Durante la generazione delle rotte per i moduli. | Simile a `displayModuleRoutes`, utilizzato per definire pattern URL personalizzati e associarli ai controller del modulo. |
| `displayBackOfficeHeader` | Renderizza il contenuto nella sezione `<head>` del Back Office. | Potenzialmente utilizzato per includere `script.tpl` per JS o CSS inline, o per aggiungere meta tag o variabili JS specifiche necessarie all'interfaccia amministrativa. |
| `actionAdminControllerSetMedia` | Prima che un Controller Admin renderizzi la sua pagina. | Utilizzato per registrare file CSS e JavaScript per il Back Office, assicurando che vengano caricati solo quando necessario. (Sebbene non siano elencati file JS/CSS, questo hook sarebbe il posto standard se fossero presenti). |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo **Export Products Pro**, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a garantire il buon funzionamento e il continuo miglioramento dei nostri moduli.
