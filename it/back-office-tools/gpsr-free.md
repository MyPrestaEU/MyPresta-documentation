---
title: "GPSR Free - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop GPSR Free di MyPresta.eu."
sidebar:
  label: "GPSR Free"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo GPSR Free su MyPresta.eu](https://mypresta.eu/modules/administration-tools/gpsr-free.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/gpsr-free/)
>
> ---


# GPSR Free

## 1. Requisiti e Compatibilità
-   **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
-   **Compatibilità PHP**: PHP 7.1 - 8.5
-   **Requisiti di hosting**: Sono richieste estensioni PHP standard (cURL, JSON, OpenSSL), che sono tipicamente disponibili sulla maggior parte degli ambienti di hosting compatibili con PrestaShop.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > GPSR Free)

Questa è la schermata di configurazione principale per il modulo GPSR Free, accessibile immediatamente dopo l'installazione o cliccando su "Configura" dal Gestione moduli.

-   **Cosa fa questa impostazione:** Questo interruttore controlla se il blocco di informazioni GPSR viene visualizzato sulle pagine dei tuoi prodotti nel front office.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (Sì):* Il blocco di informazioni GPSR, contenente i dettagli del produttore, della persona responsabile e degli avvisi, apparirà sulle pagine dei prodotti dove hai mappato le informazioni pertinenti.
    -   *Quando disabilitato (No):* Il blocco di informazioni GPSR sarà nascosto da tutte le pagine dei prodotti, indipendentemente da qualsiasi mappatura che hai configurato.
-   **Valore consigliato:** **Sì**. Per conformarsi al GPSR e visualizzare le informazioni, questo dovrebbe essere abilitato.
-   **Scenario / esempio del commerciante:** Se stai configurando attivamente i tuoi dati GPSR e vuoi che siano visibili ai clienti, abilita questa opzione. Se sei ancora in fase di configurazione dei dati o vuoi temporaneamente nascondere il blocco (ad esempio, durante una riprogettazione del sito), puoi disabilitarlo.

### 2.2 Schermate di amministrazione dedicate e viste del controller

Il modulo GPSR Free aggiunge diverse nuove voci di menu sotto una sezione principale "GPSR Free" nel tuo Back Office di PrestaShop. Queste schermate ti consentono di gestire le varie informazioni richieste per la conformità al GPSR.

#### 2.2.1 Dashboard GPSR Free (Back Office > GPSR Free > Dashboard)
Questa schermata funge da punto di ingresso principale per l'amministrazione dedicata del modulo. Tipicamente fornisce una panoramica o collegamenti rapidi alle altre sezioni di gestione.

-   **Azioni e impostazioni disponibili:** Questa vista di solito presenta un'interfaccia simile a una dashboard, potenzialmente mostrando statistiche o collegamenti rapidi per gestire Produttori, Entità, Avvisi e Mappe prodotto.
-   **Effetto delle modifiche:** Questa schermata stessa non ha impostazioni dirette che modificano il comportamento del front-office, ma è il tuo hub di navigazione per tutta la gestione dei dati GPSR.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Inizia qui per avere una panoramica, quindi naviga nelle sezioni specifiche (Produttori, Entità, Avvisi, Mappa prodotto) per aggiungere o modificare i dati.

#### 2.2.2 Produttori (Back Office > GPSR Free > Produttori)
Questa schermata ti consente di definire e gestire i produttori dei tuoi prodotti.

-   **Azioni e impostazioni disponibili:**
    -   **Tabella di elenco:** Visualizza tutti i produttori che hai aggiunto, con colonne per nome, indirizzo e azioni come "Modifica" o "Elimina".
    -   **Pulsante "Aggiungi nuovo produttore":** Cliccando su questo si apre un modulo per creare una nuova voce di produttore.
    -   **Campi del modulo (per aggiungere/modificare un produttore):**
        -   **Nome:** Il nome ufficiale del produttore.
        -   **Indirizzo:** L'indirizzo postale completo del produttore.
        -   **È produttore UE?**: Un interruttore per indicare se questo produttore ha sede all'interno dell'Unione Europea. Questo è cruciale per determinare se una "Persona responsabile nell'UE" deve essere assegnata.
-   **Effetto delle modifiche:** L'aggiunta o la modifica dei produttori qui crea o aggiorna l'elenco centrale dei produttori che puoi quindi associare ai tuoi prodotti. Queste informazioni verranno visualizzate sulle pagine dei prodotti se mappate.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Prima di mappare i prodotti, assicurati che tutti i produttori dei tuoi prodotti siano elencati qui con dettagli accurati. Se una nuova linea di prodotti proviene da un nuovo produttore, aggiungila qui per prima.

#### 2.2.3 Persone responsabili nell'UE (Back Office > GPSR Free > Persone responsabili nell'UE)
Questa schermata serve per gestire le "Persone responsabili nell'UE" (anche denominate "Entità" nella denominazione interna del modulo) che sono designate per i prodotti fabbricati al di fuori dell'UE.

-   **Azioni e impostazioni disponibili:**
    -   **Tabella di elenco:** Mostra tutte le Persone responsabili nell'UE definite, con il loro nome, indirizzo e azioni.
    -   **Pulsante "Aggiungi nuova persona responsabile nell'UE":** Apre un modulo per aggiungere una nuova persona responsabile.
    -   **Campi del modulo (per aggiungere/modificare una persona responsabile nell'UE):**
        -   **Nome:** Il nome della persona o entità responsabile nell'UE (ad esempio, importatore, rappresentante autorizzato).
        -   **Indirizzo:** L'indirizzo postale completo della persona responsabile nell'UE all'interno dell'UE.
-   **Effetto delle modifiche:** Questo crea o aggiorna l'elenco delle Persone responsabili nell'UE che possono essere collegate a produttori non UE o direttamente ai prodotti. Queste informazioni vengono visualizzate sulle pagine dei prodotti quando applicabile.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Se importi prodotti da fuori l'UE, assicurati di aver inserito qui i dettagli corretti della Persona responsabile nell'UE.

#### 2.2.4 Avvisi (Back Office > GPSR Free > Avvisi)
Questa schermata ti consente di creare e gestire avvisi o disclaimer di sicurezza personalizzati.

-   **Azioni e impostazioni disponibili:**
    -   **Tabella di elenco:** Visualizza tutti gli avvisi creati, con il loro testo e le azioni.
    -   **Pulsante "Aggiungi nuovo avviso":** Apre un modulo per creare un nuovo avviso.
    -   **Campi del modulo (per aggiungere/modificare un avviso):**
        -   **Testo dell'avviso:** Il testo effettivo dell'avviso o istruzione di sicurezza. Questo campo è solitamente multilingue, consentendoti di fornire traduzioni per ogni lingua abilitata nel tuo negozio (controllato da `PS_LANG_DEFAULT`).
-   **Effetto delle modifiche:** L'aggiunta o la modifica degli avvisi qui crea o aggiorna il pool di avvisi che puoi associare ai prodotti. Gli avvisi selezionati appariranno sulla pagina del prodotto.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Crea avvisi generici che si applicano a più prodotti (ad esempio, "Tenere fuori dalla portata dei bambini", "Leggere le istruzioni prima dell'uso"). Puoi quindi selezionarli facilmente per i singoli prodotti.

#### 2.2.5 Mappa prodotto (Back Office > GPSR Free > Mappa prodotto)
Questa è la schermata più critica in cui colleghi i tuoi prodotti ai produttori, alle persone responsabili nell'UE e agli avvisi che hai definito.

-   **Azioni e impostazioni disponibili:**
    -   **Tabella di elenco:** Mostra le mappature dei prodotti esistenti, tipicamente visualizzando il nome del prodotto, il produttore associato, la persona responsabile nell'UE e gli avvisi.
    -   **Pulsante "Aggiungi nuova mappa prodotto":** Apre un modulo per creare una nuova mappatura.
    -   **Campi del modulo (per aggiungere/modificare una mappa prodotto):**
        -   **Ricerca prodotto:** Un campo per cercare e selezionare il prodotto specifico che desideri mappare.
        -   **Produttore:** Un elenco a discesa per selezionare uno dei produttori che hai definito nella sezione "Produttori".
        -   **Persona responsabile nell'UE:** Un elenco a discesa per selezionare una delle Persone responsabili nell'UE che hai definito. Questo campo potrebbe essere obbligatorio o apparire solo se il produttore selezionato *non* è un produttore UE.
        -   **Avvisi:** Una casella di selezione multipla o una lista di controllo per scegliere uno o più avvisi dalla sezione "Avvisi" da associare a questo prodotto.
-   **Effetto delle modifiche:** Quando salvi una mappa prodotto, il produttore selezionato, la persona responsabile nell'UE (se applicabile) e gli avvisi verranno visualizzati sulla pagina del prodotto del front-office per quel prodotto specifico, a condizione che l'impostazione "Abilita blocco GPSR" sia attiva.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Dopo aver configurato i tuoi produttori, le persone responsabili nell'UE e gli avvisi, esamina il tuo catalogo prodotti e mappa ogni prodotto pertinente qui. È qui che le informazioni GPSR si uniscono per la visualizzazione.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
|---|---|---|---|
| Configurazione modulo | Abilita blocco GPSR | Sì | Controlla la visibilità del blocco di informazioni GPSR sulle pagine dei prodotti. |
| Produttori | Nome | N/A | Nome ufficiale del produttore del prodotto. |
| Produttori | Indirizzo | N/A | Indirizzo postale completo del produttore. |
| Produttori | È produttore UE? | Sì | Indica se il produttore ha sede nell'UE, influenzando la necessità di una Persona responsabile nell'UE. |
| Persone responsabili nell'UE | Nome | N/A | Nome della Persona/Entità responsabile nell'UE designata. |
| Persone responsabili nell'UE | Indirizzo | N/A | Indirizzo postale completo della Persona responsabile nell'UE all'interno dell'UE. |
| Avvisi | Testo dell'avviso | N/A | Il testo effettivo dell'avviso o istruzione di sicurezza (multilingue). |
| Mappa prodotto | Prodotto | N/A | Seleziona il prodotto a cui verranno mappate le informazioni GPSR. |
| Mappa prodotto | Produttore | N/A | Associa un produttore definito al prodotto selezionato. |
| Mappa prodotto | Persona responsabile nell'UE | N/A | Associa una Persona responsabile nell'UE definita al prodotto selezionato (se il produttore non è UE). |
| Mappa prodotto | Avvisi | N/A | Seleziona uno o più avvisi definiti da visualizzare per il prodotto. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho configurato tutto, ma il blocco GPSR non viene visualizzato sulle pagine dei miei prodotti.**
R:
1.  **Controlla "Abilita blocco GPSR":** Vai su **Moduli > Gestione moduli > GPSR Free > Configura** e assicurati che l'impostazione "Abilita blocco GPSR" sia impostata su "Sì".
2.  **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). A volte, la cache di PrestaShop impedisce la visualizzazione immediata di nuovi contenuti.
3.  **Mappatura del prodotto:** Ricontrolla che il prodotto specifico che stai visualizzando sia stato mappato in **GPSR Free > Mappa prodotto** con un produttore e almeno un avviso/entità.
4.  **Compatibilità del tema:** Sebbene il modulo cerchi di essere compatibile con la maggior parte dei temi, temi molto personalizzati potrebbero richiedere piccole modifiche. Se il blocco è completamente mancante dopo aver controllato quanto sopra, contatta il supporto MyPresta.eu.

**D: Il testo dell'avviso o i dettagli del produttore non vengono visualizzati nella lingua corretta.**
R:
1.  **Controlla le traduzioni:** Quando modifichi un avviso o un produttore, assicurati di aver fornito le traduzioni per tutte le lingue attive nel tuo negozio. Cerca le schede della lingua accanto ai campi di input.
2.  **Lingua predefinita:** Il modulo utilizza la lingua predefinita di PrestaShop (`PS_LANG_DEFAULT`) se manca una traduzione specifica. Assicurati che la tua lingua predefinita sia impostata correttamente in **Internazionale > Localizzazione**.

**D: Come posso rimuovere i dati di esempio installati con il modulo?**
R: Puoi andare in ogni rispettiva schermata di gestione (**GPSR Free > Produttori**, **GPSR Free > Persone responsabili nell'UE**, **GPSR Free > Avvisi**, **GPSR Free > Mappa prodotto**) e utilizzare l'azione "Elimina" per ogni voce di esempio.

**D: Posso personalizzare l'aspetto del blocco GPSR?**
R: Sì, il modulo include un file `front.css`. Per modifiche di stile di base (colori, font, spaziatura), puoi spesso sovrascrivere questi stili nel file CSS personalizzato del tuo tema senza modificare direttamente il modulo. Per modifiche di layout più avanzate, potresti dover modificare il template `product-footer.tpl`. (Vedi Sezione 7 per i dettagli dello sviluppatore).

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura
Il modulo GPSR Free segue il modello MVC (Model-View-Controller) di PrestaShop. Utilizza Controller Admin personalizzati per la gestione dei dati relativi al GPSR (Produttori, Entità, Avvisi, Mappe prodotto) e sfrutta l'`ObjectModel` di PrestaShop per la persistenza dei dati. La visualizzazione nel front-office è gestita tramite un template hook. Il modulo utilizza un pattern repository (`GpsrFreeRepository`) per le interazioni con il database, promuovendo un codice più pulito e la separazione delle preoccupazioni.

### 4.2 Controller (`controllers/`)

Il modulo utilizza principalmente i Controller Admin del Back-Office per la gestione dei dati. Non ci sono controller dedicati al front-office poiché la visualizzazione nel front-office è gestita direttamente tramite hook.

-   **Controller Admin del Back-Office**:
    -   `controllers/admin/AdminGpsrFreeController.php`
        -   **Nome classe:** `AdminGpsrFreeController` (estende `ModuleAdminController`)
        -   **Nome scheda:** GPSR Free (voce principale della dashboard)
        -   **Responsabilità:** Serve come punto di ingresso principale per l'amministrazione del modulo, probabilmente visualizzando una dashboard o collegamenti ad altre schermate di gestione specifiche. Non gestisce un'entità specifica ma orchestra l'accesso ad altri controller.
    -   `controllers/admin/AdminGpsrFreeEntitiesController.php`
        -   **Nome classe:** `AdminGpsrFreeEntitiesController` (estende `ModuleAdminController`)
        -   **Nome scheda:** Persone responsabili nell'UE
        -   **Entità gestita:** `GpsrFreeEntity` (mappa alla tabella `ps_gpsrfree_entity`)
        -   **Responsabilità:** Gestisce la creazione, la modifica, l'elenco e l'eliminazione delle Persone responsabili nell'UE (entità). Fornisce una vista elenco e modulo standard di PrestaShop per questi dati.
    -   `controllers/admin/AdminGpsrFreeManufacturersController.php`
        -   **Nome classe:** `AdminGpsrFreeManufacturersController` (estende `ModuleAdminController`)
        -   **Nome scheda:** Produttori
        -   **Entità gestita:** `GpsrFreeManufacturer` (mappa alla tabella `ps_gpsrfree_manufacturer`)
        -   **Responsabilità:** Gestisce la creazione, la modifica, l'elenco e l'eliminazione dei produttori di prodotti. Include la logica per `is_eu_manufacturer`.
    -   `controllers/admin/AdminGpsrFreeMapController.php`
        -   **Nome classe:** `AdminGpsrFreeMapController` (estende `ModuleAdminController`)
        -   **Nome scheda:** Mappa prodotto
        -   **Entità gestita:** `GpsrFreeProductMap` (mappa alla tabella `ps_gpsrfree_product_map`)
        -   **Responsabilità:** Gestisce la mappatura tra prodotti, produttori, persone responsabili nell'UE e avvisi. Questo controller gestisce le complesse relazioni tra i diversi tipi di dati GPSR.
    -   `controllers/admin/AdminGpsrFreeWarningsController.php`
        -   **Nome classe:** `AdminGpsrFreeWarningsController` (estende `ModuleAdminController`)
        -   **Nome scheda:** Avvisi
        -   **Entità gestita:** `GpsrFreeWarning` (mappa alla tabella `ps_gpsrfree_warning`)
        -   **Responsabilità:** Gestisce la creazione, la modifica, l'elenco e l'eliminazione degli avvisi di sicurezza. Supporta campi multilingue.
    -   `controllers/admin/GpsrFreeAdminController.php`
        -   **Nome classe:** `GpsrFreeAdminController` (estende `ModuleAdminController`)
        -   **Nome scheda:** (Probabilmente un controller base o astratto per altri controller admin, o un punto di ingresso più vecchio/ridondante)
        -   **Responsabilità:** Dato il suo nome generico, potrebbe servire come classe base per altri controller admin nel modulo, fornendo metodi o proprietà comuni, oppure potrebbe essere un punto di ingresso legacy.
    -   `controllers/admin/index.php`
        -   **Nome classe:** N/A
        -   **Responsabilità:** File di sicurezza standard di PrestaShop per prevenire la visualizzazione diretta della directory.

### 4.3 Classi e modelli principali (`classes/`)

-   `classes/GpsrFreeAdminUi.php`
    -   **Nome classe:** `GpsrFreeAdminUi`
    -   **Responsabilità:** Probabilmente una classe helper per generare o gestire elementi UI all'interno del Back Office, come campi modulo, configurazioni di elenchi o componenti comuni dell'interfaccia di amministrazione. Aiuta a standardizzare l'aspetto delle schermate di amministrazione del modulo.
-   `classes/GpsrFreeEntity.php`
    -   **Nome classe:** `GpsrFreeEntity` (estende `ObjectModel`)
    -   **Tabella database:** `ps_gpsrfree_entity`
    -   **Campi `$definition`:** Definisce campi come `name`, `address`.
    -   **Metodi pubblici chiave:** Metodi `ObjectModel` standard per le operazioni CRUD. Rappresenta una Persona responsabile nell'UE.
-   `classes/GpsrFreeManufacturer.php`
    -   **Nome classe:** `GpsrFreeManufacturer` (estende `ObjectModel`)
    -   **Tabella database:** `ps_gpsrfree_manufacturer`
    -   **Campi `$definition`:** Definisce campi come `name`, `address`, `is_eu_manufacturer`.
    -   **Metodi pubblici chiave:** Metodi `ObjectModel` standard per le operazioni CRUD. Rappresenta un produttore di prodotti.
-   `classes/GpsrFreeProductMap.php`
    -   **Nome classe:** `GpsrFreeProductMap` (estende `ObjectModel`)
    -   **Tabella database:** `ps_gpsrfree_product_map`
    -   **Campi `$definition`:** Definisce campi come `id_product`, `id_manufacturer`, `id_entity`, `id_warning`. Questa tabella probabilmente memorizza le relazioni molti-a-molti o le mappature dirette.
    -   **Metodi pubblici chiave:** Metodi `ObjectModel` standard per le operazioni CRUD. Gestisce i collegamenti tra prodotti e dati GPSR.
-   `classes/GpsrFreeRepository.php`
    -   **Nome classe:** `GpsrFreeRepository`
    -   **Responsabilità:** Implementa il pattern repository. Questa classe è responsabile di tutte le interazioni dirette con il database, astraendole da controller e modelli. Contiene metodi per recuperare, inserire, aggiornare ed eliminare dati relativi al GPSR, spesso utilizzando la classe `Db` di PrestaShop. Contiene metodi come `getMappedProductData($id_product)`.
-   `classes/GpsrFreeWarning.php`
    -   **Nome classe:** `GpsrFreeWarning` (estende `ObjectModel`)
    -   **Tabella database:** `ps_gpsrfree_warning`
    -   **Campi `$definition`:** Definisce campi come `text` (multilingue).
    -   **Metodi pubblici chiave:** Metodi `ObjectModel` standard per le operazioni CRUD. Rappresenta un avviso di sicurezza.
-   `classes/index.php`
    -   **Nome classe:** N/A
    -   **Responsabilità:** File di sicurezza standard di PrestaShop per prevenire la visualizzazione diretta della directory.

### 4.4 Risorse JavaScript (`views/js/`)
L'inventario fornito indica che non sono inclusi file JavaScript personalizzati nel modulo. Ciò suggerisce che il modulo si basa principalmente sulle funzionalità JavaScript integrate di PrestaShop per i suoi moduli di amministrazione e potenzialmente minime interazioni nel front-office, o che qualsiasi comportamento dinamico è gestito lato server.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `views/css/admin.css`
    -   **Ambito:** Stile dei moduli di amministrazione del Back-office.
    -   **Principali componenti UI e contenitori che stilizza:** Probabilmente fornisce uno stile specifico per le pagine di amministrazione personalizzate del modulo, come tabelle di elenco, elementi di modulo o widget della dashboard, per garantire un aspetto coerente all'interno del Back Office di PrestaShop.
    -   **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere:** Qualsiasi classe personalizzata utilizzata nei template di amministrazione del modulo (ad esempio, `.gpsrfree-admin-panel`, `.gpsrfree-table`).
-   `views/css/front.css`
    -   **Ambito:** Stile per i clienti del Front-office.
    -   **Principali componenti UI e contenitori che stilizza:** Stilizza il blocco di informazioni GPSR visualizzato sulle pagine dei prodotti. Questo includerebbe lo stile per il contenitore del blocco, le intestazioni, i dettagli del produttore, i dettagli della persona responsabile nell'UE e gli elenchi di avvisi.
    -   **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere:** Classi come `.gpsrfree-block`, `.gpsrfree-manufacturer`, `.gpsrfree-entity`, `.gpsrfree-warnings`, ecc. Gli sviluppatori possono mirare a queste classi nel file `custom.css` o `theme.css` del loro tema per abbinare il branding del negozio.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**:
    -   `views/templates/hook/product-footer.tpl`
        -   **Hook:** `displayFooterProduct` (e potenzialmente `displayProductButtons` o simili, sebbene `displayFooterProduct` sia esplicitamente elencato).
        -   **Output del blocco visivo:** Questo template è responsabile del rendering dell'intero blocco di informazioni GPSR sulla pagina del prodotto. Conterrà la logica per visualizzare i dettagli del produttore, i dettagli della persona responsabile nell'UE (se applicabile) e un elenco di avvisi associati, basati sui dati recuperati dal `GpsrFreeRepository` per il prodotto corrente.
-   **Template admin (`views/templates/admin/`)**:
    -   `views/templates/admin/configure.tpl`
        -   **Hook:** Renderizzato dal metodo `getContent()` del file principale del modulo `gpsrfree.php`.
        -   **Output del blocco visivo:** Questo template renderizza il modulo di configurazione principale del modulo nel Back Office, in particolare l'interruttore "Abilita blocco GPSR". Potrebbe anche contenere collegamenti o testo introduttivo per la navigazione verso i controller admin dedicati.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    -   `ps_gpsrfree_entity`: Memorizza le informazioni sulle Persone responsabili nell'UE (id, nome, indirizzo).
    -   `ps_gpsrfree_manufacturer`: Memorizza le informazioni sui produttori di prodotti (id, nome, indirizzo, is_eu_manufacturer).
    -   `ps_gpsrfree_product_map`: Memorizza le relazioni di mappatura tra prodotti, produttori, persone responsabili nell'UE e avvisi (id_product, id_manufacturer, id_entity, id_warning). Questa tabella probabilmente gestisce relazioni molti-a-molti memorizzando più voci per un singolo prodotto se ha più avvisi.
    -   `ps_gpsrfree_warning`: Memorizza il testo degli avvisi di sicurezza (id, text - multilingue).
    -   `ps_configuration`: Le impostazioni del modulo come `GPSRFREE_ENABLED` sono memorizzate qui.

-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempistica di esecuzione | Scopo tecnico |
|---|---|---|
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Potenzialmente utilizzato per caricare CSS del front-office (`front.css`) o JavaScript (se presente) globalmente. |
| `displayFooterProduct` | In fondo alla pagina del prodotto, tipicamente sotto il contenuto principale del prodotto. | Hook principale per il rendering del blocco di informazioni GPSR (`product-footer.tpl`) sulla pagina del prodotto. |
| `displayBackOfficeHeader` | Nella sezione `<head>` di ogni pagina del Back Office. | Utilizzato per caricare CSS del Back Office (`admin.css`) o JavaScript per le schermate di amministrazione del modulo. |
| `displayAdminProductsExtra` | (Implicito, spesso usato per aggiungere schede/sezioni alla pagina di modifica del prodotto) | Sebbene non esplicitamente elencato come registrato, i moduli spesso usano questo o hook simili per integrarsi con la pagina di modifica del prodotto se la mappatura è stata fatta direttamente lì. Dato `AdminGpsrFreeMapController`, è probabile che sia una schermata separata. |
| `actionValidateOrder` | Dopo che un ordine è stato convalidato con successo. | (Non esplicitamente elencato come registrato, ma comune per i moduli che interagiscono con gli ordini. Se presente, sarebbe per l'elaborazione dei dati GPSR relativi all'ordine, cosa non indicata dalla descrizione del modulo.) |

*Nota: Il dossier del modulo elencava `DisplayHeader`, `DisplayFooterProduct`, `displayHeader`, `DisplayBackOfficeHeader`, `displayFooterProduct`, `displayBackOfficeHeader`. Questi sono duplicati a causa della sensibilità alle maiuscole/minuscole, ma funzionalmente si riferiscono agli stessi hook.*

## 5. Supporto ufficiale e aggiornamenti
Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo GPSR Free, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e compatibilità del modulo.
