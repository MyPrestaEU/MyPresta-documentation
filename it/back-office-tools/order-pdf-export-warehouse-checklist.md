---
title: "Esportazione PDF Ordini & Lista di Controllo Magazzino - Manuale Commerciante & Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Esportazione PDF Ordini & Lista di Controllo Magazzino di MyPresta.eu."
sidebar:
  label: "Esportazione PDF Ordini & Lista di Controllo Magazzino - Manuale Commerciante & Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Order PDF Export & Warehouse Checklist su MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-pdf-export-warehouse-checklist.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/order-pdf-export-warehouse-checklist/)
>
> ---


# Esportazione PDF Ordini & Lista di Controllo Magazzino

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Sono richieste estensioni PHP standard (cURL, JSON, OpenSSL), che sono tipicamente disponibili sulla maggior parte degli ambienti di hosting compatibili con PrestaShop.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Per accedere a questa schermata, naviga su **Moduli > Gestione moduli**, cerca "Esportazione PDF Ordini & Lista di Controllo Magazzino" e clicca su "Configura".

#### **Modello PDF**

- **Cosa fa questa impostazione:** Ti permette di scegliere il design visivo e il layout per i documenti PDF generati dal modulo. Puoi selezionare tra una varietà di modelli predefiniti.
- **Effetto della modifica di questa impostazione:**
  - *Se impostato su 'Pulito':* I tuoi PDF avranno un aspetto minimalista e moderno.
  - *Se impostato su 'Magazzino Grande':* Il PDF sarà ottimizzato per l'uso in magazzino, potenzialmente con caratteri più grandi e sezioni chiare per il prelievo.
  - *Se impostato su 'Retro':* I tuoi PDF adotteranno un design di ispirazione vintage.
- **Valore consigliato:** Inizia con 'Pulito' o 'Magazzino Grande' a seconda del tuo caso d'uso principale (bolla di accompagnamento per il cliente vs. lista di prelievo interna). Sperimenta per trovare la soluzione migliore per il tuo brand e le tue esigenze operative.
- **Scenario / esempio del commerciante:** Se desideri che le tue bolle di accompagnamento riflettano un'immagine di brand moderna e professionale, potresti scegliere 'Pulito' o 'Serif Elegante'. Se il tuo obiettivo principale è fornire una lista di prelievo altamente leggibile per il personale del magazzino, 'Magazzino Grande' potrebbe essere più adatto.

#### **Abilita aggiornamenti MyPresta.eu** (`mypresta_updates`)

- **Cosa fa questa impostazione:** Controlla se il modulo può verificare e notificarti gli aggiornamenti disponibili da MyPresta.eu.
- **Effetto della modifica di questa impostazione:**
  - *Se abilitato (Sì):* Il modulo controllerà periodicamente la presenza di nuove versioni, assicurandoti di rimanere aggiornato con le ultime funzionalità, correzioni di bug e miglioramenti di compatibilità. Potresti vedere notifiche nel tuo back office di PrestaShop quando è disponibile un aggiornamento.
  - *Se disabilitato (No):* Il modulo non controllerà gli aggiornamenti. Dovrai controllare manualmente il tuo account MyPresta.eu per nuove versioni.
- **Valore consigliato:** **Sì**. Mantenere i moduli aggiornati è fondamentale per la sicurezza, le prestazioni e la compatibilità con le nuove versioni di PrestaShop.
- **Scenario / esempio del commerciante:** Abilitare questa opzione ti assicura di utilizzare sempre la versione più stabile e ricca di funzionalità del modulo senza dover controllare costantemente manualmente.

#### **Versione aggiornamento** (`update_`) e **Valore versione aggiornamento** (`updatev_`)

- **Cosa fanno queste impostazioni:** Queste sono impostazioni interne utilizzate dal modulo per gestire il suo meccanismo di aggiornamento. Memorizzano informazioni sull'ultima versione disponibile o sulla versione attualmente installata.
- **Effetto della modifica di questa impostazione:** Queste **non devono essere modificate manualmente** dal commerciante. Alterarle potrebbe interferire con la capacità del modulo di controllare e applicare correttamente gli aggiornamenti.
- **Valore consigliato:** Lascia queste impostazioni così come sono. Sono gestite automaticamente dal modulo.
- **Scenario / esempio del commerciante:** Tipicamente non interagirai con queste impostazioni. Fanno parte della logica di aggiornamento interna del modulo.

### 2.2 Schermate di amministrazione dedicate e viste del controller

Il modulo aggiunge nuove voci di menu sotto **Ordini** nel tuo Back Office di PrestaShop, permettendoti di gestire le categorie e gli elementi della tua lista di controllo magazzino.

#### **Nome schermata: Categorie lista di controllo**

- **Posizione menu:** Back Office > Ordini > **Categorie lista di controllo**
- **Azioni e impostazioni disponibili:** Questa schermata ti permette di creare, modificare ed eliminare categorie per la tua lista di controllo magazzino. Pensa alle categorie come raggruppamenti logici per gli elementi della tua lista di controllo (es. "Qualità imballaggio", "Verifica prodotto", "Documenti di spedizione").
  - **Aggiunta di una nuova categoria:** Clicca su "Aggiungi nuova categoria" per definire un nuovo gruppo. Tipicamente fornirai un nome per la categoria (es. "Ispezione prodotto").
  - **Modifica/Eliminazione categorie:** Puoi modificare le categorie esistenti o rimuoverle se non sono più necessarie.
- **Effetto delle modifiche:**
  - *Aggiunta di una categoria:* Crea una nuova sezione sotto la quale potrai in seguito aggiungere elementi specifici della lista di controllo.
  - *Modifica di una categoria:* Cambia il nome o le proprietà di una categoria esistente.
  - *Eliminazione di una categoria:* Rimuove la categoria e tutti gli elementi della lista di controllo associati dal sistema. Questa non apparirà più sui tuoi PDF generati.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1. Inizia definendo categorie ampie che riflettano il tuo processo di magazzino. Ad esempio: "Accuratezza ordine", "Integrità imballaggio", "Documentazione".
  2. Assicurati che i nomi delle categorie siano chiari e descrittivi per il tuo personale.

#### **Nome schermata: Elementi lista di controllo**

- **Posizione menu:** Back Office > Ordini > **Elementi lista di controllo**
- **Azioni e impostazioni disponibili:** Questa schermata è dove definisci gli elementi effettivi che appariranno nella tua lista di controllo magazzino all'interno del PDF. Ogni elemento può essere assegnato a una categoria che hai creato in precedenza.
  - **Aggiunta di un nuovo elemento:** Clicca su "Aggiungi nuovo elemento". Specificherai:
    - **Nome:** Il testo dell'elemento della lista di controllo (es. "Tutti gli articoli presenti e contabilizzati?").
    - **Categoria:** Assegnalo a una delle categorie che hai definito (es. "Accuratezza ordine").
    - **Attivo:** Se questo elemento deve apparire nella lista di controllo.
  - **Modifica/Eliminazione elementi:** Modifica o rimuovi singoli elementi della lista di controllo.
- **Effetto delle modifiche:**
  - *Aggiunta di un elemento:* Il nuovo elemento apparirà nella lista di controllo PDF generata sotto la sua categoria assegnata.
  - *Modifica di un elemento:* Cambia il testo o la categoria di un elemento della lista di controllo esistente.
  - *Eliminazione di un elemento:* Rimuove l'elemento dalla lista di controllo sui PDF.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1. Una volta impostate le categorie, popolarle con elementi specifici e attuabili della lista di controllo.
  2. Esempi: "Quantità prodotto corrisponde all'ordine?", "Articoli fragili adeguatamente ammortizzati?", "Etichetta di spedizione corretta?", "Fattura inclusa?".
  3. Rivedi e aggiorna regolarmente gli elementi della tua lista di controllo per riflettere i cambiamenti nei tuoi prodotti, imballaggi o procedure di spedizione.

#### **Nome schermata: Lista ordini (con pulsante Esporta)**

- **Posizione menu:** Back Office > Ordini > **Ordini**
- **Azioni e impostazioni disponibili:** Questo modulo si integra direttamente nella tua lista ordini standard di PrestaShop. Troverai nuovi pulsanti o opzioni per generare PDF per singoli ordini o potenzialmente in blocco.
  - **Esportazione ordine individuale:** Quando visualizzi un ordine specifico nel Back Office, vedrai un nuovo pulsante (es. "Esporta PDF" o "Stampa lista di prelievo") che ti permette di generare il PDF personalizzato per quell'ordine.
  - **Esportazione ordini in blocco:** (A seconda della versione del modulo e della versione di PrestaShop) Potresti essere in grado di selezionare più ordini dalla lista ordini e generare PDF per tutti contemporaneamente.
- **Effetto delle modifiche:** Cliccando questi pulsanti scaricherai un documento PDF sul tuo computer, formattato secondo il modello scelto e includendo la tua lista di controllo personalizzata.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1. Dopo che un ordine è stato effettuato e convalidato, naviga alla lista Ordini.
  2. Apri l'ordine specifico che devi evadere.
  3. Clicca sul pulsante "Esporta PDF" per generare la lista di prelievo/bolla di accompagnamento con la lista di controllo.
  4. Stampa il PDF e consegnalo al tuo personale di magazzino per l'evasione.
  5. Il personale utilizza il PDF per prelevare gli articoli, verificare l'accuratezza utilizzando la lista di controllo e potenzialmente raccogliere firme prima dell'imballaggio.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Configurazione modulo** | Modello PDF | Pulito / Magazzino Grande | Seleziona il layout visivo e il design dei documenti PDF generati. |
| **Configurazione modulo** | Abilita aggiornamenti MyPresta.eu | Sì | Permette al modulo di controllare e notificare nuove versioni. |
| **Categorie lista di controllo** | Aggiungi/Modifica/Elimina Categoria | N/A | Gestisce i raggruppamenti logici per gli elementi della tua lista di controllo magazzino. |
| **Elementi lista di controllo** | Aggiungi/Modifica/Elimina Elemento | N/A | Definisce gli elementi specifici che appaiono nella tua lista di controllo magazzino all'interno del PDF. |
| **Lista ordini / Vista ordine** | Pulsante Esporta PDF | N/A | Genera un documento PDF per l'ordine/gli ordini selezionato/i utilizzando il modello e la lista di controllo configurati. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Il PDF appare strano o presenta problemi di formattazione. Cosa devo fare?**
R:

1.  **Svuota la cache di Smarty:** Vai su **Parametri avanzati > Prestazioni** nel tuo Back Office di PrestaShop. Scorri fino a "Cache" e clicca su "Svuota la cache". A volte, i vecchi file di template possono causare problemi di visualizzazione.
2.  **Prova un modello PDF diverso:** Nella configurazione del modulo, prova a selezionare un "Modello PDF" diverso per vedere se il problema è specifico di un layout.
3.  **Verifica la presenza di conflitti con il tema:** Se stai utilizzando un tema molto personalizzato, potrebbe avere CSS o JS che interferiscono. Passa temporaneamente al tema predefinito di PrestaShop (es. Classic) e riprova. Se funziona, il tuo tema potrebbe richiedere delle modifiche.
4.  **Contatta il supporto:** Se i problemi persistono, raccogli screenshot e dettagli, quindi contatta il supporto MyPresta.eu.

**D: I miei elementi personalizzati della lista di controllo non appaiono sul PDF.**
R:

1.  **Controlla "Categorie lista di controllo":** Assicurati di aver creato categorie sotto **Ordini > Categorie lista di controllo**.
2.  **Controlla "Elementi lista di controllo":** Verifica di aver aggiunto elementi sotto **Ordini > Elementi lista di controllo** e che siano assegnati a una categoria attiva. Inoltre, assicurati che l'interruttore "Attivo" per ogni elemento sia impostato su "Sì".
3.  **Configurazione del modulo:** Assicurati che il modulo sia configurato e salvato correttamente.

**D: Non vedo il pulsante "Esporta PDF" sulle mie pagine degli ordini.**
R:

1.  **Modulo installato e abilitato:** Ricontrolla che il modulo sia installato e abilitato in **Moduli > Gestione moduli**.
2.  **Permessi:** Assicurati che il tuo profilo dipendente abbia i permessi necessari per accedere e utilizzare questo modulo. Vai su **Parametri avanzati > Team > Profili** e controlla i permessi per il profilo assegnato al tuo account dipendente.
3.  **Versione PrestaShop:** Conferma che la tua versione di PrestaShop sia compatibile (1.7.x, 8.x, 9.x).
4.  **Svuota la cache:** Svuota la cache di PrestaShop (**Parametri avanzati > Prestazioni**).

**D: Posso personalizzare ulteriormente i modelli PDF (es. aggiungere il mio logo, cambiare i font)?**
R: Sì, ma questo richiede conoscenze tecniche. Il modulo fornisce diversi modelli, ma per una personalizzazione profonda (come aggiungere il tuo logo specifico, cambiare i font o alterare il layout oltre a quanto offerto dalle impostazioni del modulo), dovresti:

1.  **Identificare il file del modello:** Individua il file `.tpl` per il modello PDF scelto all'interno della directory `pdf/en/` del modulo.
2.  **Modificare il modello:** Questo comporta la modifica del codice del template Smarty e potenzialmente HTML/CSS. Questo è un compito per un webmaster o uno sviluppatore.
3.  **Considerare un modello personalizzato:** Per modifiche significative, è spesso meglio creare un nuovo modello personalizzato piuttosto che modificare i file principali del modulo, per garantire che le tue modifiche non vengano sovrascritte durante gli aggiornamenti del modulo.

**D: Il modulo non controlla gli aggiornamenti.**
R:

1.  **Abilita il controllo degli aggiornamenti:** Vai alla pagina di configurazione del modulo (**Moduli > Gestione moduli > Configura** per "Esportazione PDF Ordini & Lista di Controllo Magazzino") e assicurati che "Abilita aggiornamenti MyPresta.eu" sia impostato su "Sì".
2.  **Connettività del server:** Assicurati che il tuo server abbia accesso a Internet in uscita per connettersi ai server di aggiornamento di MyPresta.eu. Ciò potrebbe comportare il controllo delle impostazioni del firewall o delle configurazioni proxy con il tuo provider di hosting.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata del modulo "Esportazione PDF Ordini & Lista di Controllo Magazzino" per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo segue un modello MVC (Model-View-Controller) standard di PrestaShop, estendendo principalmente `Module` per la sua funzionalità principale e `AdminController` per le sue schermate di gestione del Back Office. Sfrutta `ObjectModel` per la gestione di entità di database personalizzate (categorie ed elementi della lista di controllo). La generazione di PDF è gestita da una classe dedicata (`OrderPdfGenerator`) che utilizza i template Smarty per il rendering del contenuto PDF, probabilmente integrandosi con una libreria come Dompdf o TCPDF (anche se la libreria specifica non è esplicitamente indicata, la struttura `.tpl` suggerisce un motore di rendering). Gli hook vengono utilizzati per integrare la funzionalità del modulo nel Back Office di PrestaShop, in particolare per aggiungere pulsanti di esportazione PDF alle pagine degli ordini.

### 4.2 Controller (`controllers/`)

#### Controller di amministrazione del Back-Office

- `orderexportpdf/controllers/admin/AdminOrderExportChecklistCategoriesController.php`

  - **Nome classe:** `AdminOrderExportChecklistCategoriesController`
  - **Classe genitore:** `ModuleAdminController`
  - **Responsabilità:** Gestisce le operazioni CRUD (Create, Read, Update, Delete) per gli oggetti `OrderExportChecklistCategory`. Fornisce l'interfaccia del Back Office per elencare, aggiungere, modificare ed eliminare le categorie della lista di controllo. Questo controller è mappato alla voce di menu "Categorie lista di controllo" sotto "Ordini".
  - **Nome scheda:** Categorie lista di controllo
  - **Entità gestita:** `OrderExportChecklistCategory` (mappata alla tabella `ps_orderexport_checklist_cat`).
- `orderexportpdf/controllers/admin/AdminOrderExportChecklistElementsController.php`

  - **Nome classe:** `AdminOrderExportChecklistElementsController`
  - **Classe genitore:** `ModuleAdminController`
  - **Responsabilità:** Gestisce le operazioni CRUD per gli oggetti `OrderExportChecklistElement`. Fornisce l'interfaccia del Back Office per elencare, aggiungere, modificare ed eliminare singoli elementi della lista di controllo, consentendo l'assegnazione a categorie. Questo controller è mappato alla voce di menu "Elementi lista di controllo" sotto "Ordini".
  - **Nome scheda:** Elementi lista di controllo
  - **Entità gestita:** `OrderExportChecklistElement` (mappata alla tabella `ps_orderexport_checklist_elem`).
- `orderexportpdf/controllers/admin/index.php`

  - **Responsabilità:** Questo è tipicamente un file vuoto o un file contenente un'istruzione di sicurezza `die()` per prevenire la visualizzazione diretta della directory. Non contiene logica del controller.

### 4.3 Classi e modelli principali (`classes/`)

- `orderexportpdf/classes/index.php`

  - **Responsabilità:** File di sicurezza standard di PrestaShop, di solito contiene `<?php exit;` per prevenire la visualizzazione della directory.
- `orderexportpdf/classes/OrderExport.php`

  - **Nome classe:** `OrderExport`
  - **Classe genitore:** `Object` (probabilmente, o una classe base personalizzata)
  - **Responsabilità:** Questa classe probabilmente contiene metodi helper o logica principale relativa al processo generale di esportazione degli ordini, gestendo possibilmente il recupero dei dati, la formattazione o l'interazione con la classe di generazione PDF. Potrebbe non essere un `ObjectModel` ma una classe di utilità.
- `orderexportpdf/classes/OrderExportChecklistCategory.php`

  - **Nome classe:** `OrderExportChecklistCategory`
  - **Classe genitore:** `ObjectModel`
  - **Tabella database:** `ps_orderexport_checklist_cat`
  - **Campi `$definition`:** Definisce la struttura di una categoria della lista di controllo, inclusi campi come `id_orderexport_checklist_cat`, `name` (multilingua), `active`, `position`.
  - **Metodi pubblici chiave:** Metodi `ObjectModel` standard (`add`, `update`, `delete`, `getFields`, `validateFields`, `validateController`). Può includere metodi per recuperare tutte le categorie attive o le categorie per ID.
- `orderexportpdf/classes/OrderExportChecklistElement.php`

  - **Nome classe:** `OrderExportChecklistElement`
  - **Classe genitore:** `ObjectModel`
  - **Tabella database:** `ps_orderexport_checklist_elem`
  - **Campi `$definition`:** Definisce la struttura di un elemento della lista di controllo, inclusi campi come `id_orderexport_checklist_elem`, `id_orderexport_checklist_cat` (chiave esterna), `name` (multilingua), `active`, `position`.
  - **Metodi pubblici chiave:** Metodi `ObjectModel` standard. Può includere metodi per recuperare elementi per categoria o tutti gli elementi attivi.
- `orderexportpdf/classes/OrderPdfGenerator.php`

  - **Nome classe:** `OrderPdfGenerator`
  - **Classe genitore:** Probabilmente `Object` o una classe base personalizzata.
  - **Responsabilità:** Questa è la classe principale responsabile della generazione dei documenti PDF. Prende un ID ordine, il template selezionato e i dati della lista di controllo, quindi renderizza il contenuto in formato PDF. Probabilmente utilizza internamente una libreria PDF di terze parti (es. Dompdf, mPDF).
  - **Metodi pubblici chiave:** `generatePdf($orderId, $templateName, $checklistData)`, `renderTemplate($templatePath, $data)`, `downloadPdf()`.

### 4.4 Risorse JavaScript (`views/js/`)

- `orderexportpdf/lib/pdfTemplatesManager/js/pdfTemplatesManager.js`

  - **Ambito:** Back-office.
  - **Responsabilità:** Probabilmente gestisce la gestione dinamica dei modelli PDF all'interno dell'interfaccia di configurazione del modulo. Ciò potrebbe includere chiamate AJAX per salvare le impostazioni del modello, visualizzare in anteprima i modelli o passare tra diverse opzioni di modello.
- `orderexportpdf/views/js/order-list-legacy.js`

  - **Ambito:** Back-office (per PrestaShop 1.7.x o versioni precedenti che utilizzano JS legacy).
  - **Responsabilità:** Integra la funzionalità del pulsante di esportazione PDF nella vista della lista ordini del Back Office di PrestaShop per le versioni precedenti di PrestaShop. Collega gli eventi di click ai pulsanti, potenzialmente effettua chiamate AJAX per attivare la generazione del PDF e gestisce il download del PDF generato.
- `orderexportpdf/views/js/order-list-modern.js`

  - **Ambito:** Back-office (per PrestaShop 8.x, 9.x o versioni più recenti che utilizzano JS moderno).
  - **Responsabilità:** Simile a `order-list-legacy.js`, ma adattato per le nuove interfacce del Back Office di PrestaShop e potenzialmente utilizzando pratiche JavaScript moderne (es. ES6, risorse compilate con Webpack). Assicura che il pulsante di esportazione PDF sia visualizzato correttamente e funzionale nelle pagine della lista ordini e della vista ordine individuale.

### 4.5 Fogli di stile CSS (`views/css/`)

- `orderexportpdf/lib/pdfTemplatesManager/css/pdfTemplatesManager.css`

  - **Ambito:** Stile del modulo di amministrazione del Back-office.
  - **Responsabilità:** Fornisce lo stile per l'interfaccia di configurazione del modulo, in particolare per la sezione del gestore dei modelli PDF. Questo potrebbe includere stili per pulsanti, menu a discesa, aree di anteprima o elementi del modulo relativi alla selezione del modello.
- `orderexportpdf/views/css/order-export.css`

  - **Ambito:** Stile del modulo di amministrazione del Back-office.
  - **Responsabilità:** Stile generale per i componenti del Back Office del modulo, come le schermate di gestione delle categorie e degli elementi della lista di controllo, o potenzialmente lo stile per i pulsanti aggiunti alle pagine degli ordini.
  - **Selettori di classe CSS chiave:** Gli sviluppatori possono ispezionare l'HTML generato per classi come `.orderexportpdf-button`, `.orderexport-checklist-table`, ecc., per sovrascrivere gli stili nel loro tema amministrativo personalizzato.

### 4.6 Struttura del template Smarty (`views/templates/`)

#### Template hook (`views/templates/hook/`)

- `orderexportpdf/lib/pdfTemplatesManager/views/buttonManager.tpl`

  - **Hook:** Probabilmente renderizzato in un hook all'interno della configurazione del modulo o di una pagina di amministrazione degli ordini per visualizzare pulsanti relativi alla gestione dei modelli (es. "Gestisci modelli", "Crea nuovo modello").
  - **Output:** HTML per pulsanti o link per gestire i modelli PDF.
- `orderexportpdf/lib/pdfTemplatesManager/views/createTemplateForm.tpl`

  - **Hook:** Interno al gestore dei template del modulo, visualizzato quando si crea un nuovo template PDF.
  - **Output:** Modulo HTML per definire le proprietà di un nuovo template PDF.
- `orderexportpdf/lib/pdfTemplatesManager/views/editTemplateForm.tpl`

  - **Hook:** Interno al gestore dei template del modulo, visualizzato quando si modifica un template PDF esistente.
  - **Output:** Modulo HTML per modificare le proprietà di un template PDF esistente.
- `orderexportpdf/lib/pdfTemplatesManager/views/mainForm.tpl`

  - **Hook:** Il modulo di configurazione principale per il modulo (es. metodo `getContent()`).
  - **Output:** Il modulo HTML principale contenente il menu a discesa di selezione del "Modello PDF" e altre impostazioni a livello di modulo.
- `orderexportpdf/lib/pdfTemplatesManager/views/selectInput.tpl`

  - **Hook:** Un template parziale riutilizzabile, probabilmente incluso in `mainForm.tpl` o altri moduli, per renderizzare un input a discesa (`<select>`) per la scelta dei template.
  - **Output:** HTML per un elemento `<select>` popolato con i template PDF disponibili.
- `orderexportpdf/pdf/en/*.tpl` (es. `blue-line-dompdf.tpl`, `boxed-layout-dompdf.tpl`, `clean-dompdf.tpl`, `warehouse-big-dompdf.tpl`, ecc.)

  - **Hook:** Questi **non** sono template di hook di PrestaShop. Questi sono i veri **template di layout PDF** utilizzati da `OrderPdfGenerator` per renderizzare il contenuto della lista di prelievo/bolla di accompagnamento. Vengono scelti tramite la configurazione del modulo.
  - **Output:** Struttura HTML/CSS che verrà convertita in un documento PDF. Questi template contengono segnaposto per i dettagli dell'ordine, le liste dei prodotti, le informazioni del cliente e la lista di controllo personalizzata.
  - **Nota:** Il suffisso `dompdf` suggerisce l'uso della libreria Dompdf per la conversione da HTML a PDF.
- `orderexportpdf/pdf/fr/kids-play.tpl`

  - **Hook:** Simile ai template `en`, ma una versione specifica per il francese del layout PDF 'kids-play'. Questo indica il supporto multilingue per i template PDF.
- `orderexportpdf/pdf/en/order-export.tpl`

  - **Hook:** Questo potrebbe essere un template base generico o un template di fallback per la generazione del PDF.
  - **Output:** Una struttura generale per il PDF di esportazione dell'ordine.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

- `ps_orderexport_checklist_cat`: Memorizza le informazioni sulle categorie della lista di controllo personalizzata.

  - `id_orderexport_checklist_cat` (Chiave primaria, INT)
  - `name` (VARCHAR, Multilingua): Il nome della categoria della lista di controllo.
  - `active` (TINYINT): Se la categoria è attiva.
  - `position` (INT): Ordine di visualizzazione delle categorie.
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_orderexport_checklist_elem`: Memorizza le informazioni sui singoli elementi della lista di controllo.

  - `id_orderexport_checklist_elem` (Chiave primaria, INT)
  - `id_orderexport_checklist_cat` (Chiave esterna a `ps_orderexport_checklist_cat`, INT): La categoria a cui appartiene questo elemento.
  - `name` (VARCHAR, Multilingua): Il testo dell'elemento della lista di controllo.
  - `active` (TINYINT): Se l'elemento è attivo.
  - `position` (INT): Ordine di visualizzazione degli elementi all'interno di una categoria.
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_configuration`: Il modulo memorizza qui le sue impostazioni di configurazione principali.

  - `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: (Impostazione core di PrestaShop, non specifica del modulo)
  - `MYPRESTA_UPDATES`: (Impostazione del modulo) Memorizza lo stato del controllo degli aggiornamenti (1 per abilitato, 0 per disabilitato).
  - `UPDATE_`: (Impostazione del modulo) Tracciamento interno della versione di aggiornamento.
  - `UPDATEV_`: (Impostazione del modulo) Valore interno della versione di aggiornamento.
  - `ORDEREXPORTPDF_TEMPLATE`: (Impostazione del modulo) Memorizza il nome del modello PDF attualmente selezionato.

#### Tabella degli hook registrati

| Nome hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Eseguito quando un AdminController carica le sue risorse. | Inietta CSS (`order-export.css`, `pdfTemplatesManager.css`) e JavaScript (`order-list-legacy.js`, `order-list-modern.js`, `pdfTemplatesManager.js`) specifici del modulo nel Back Office, in particolare per le pagine degli ordini e la configurazione del modulo. |
| `displayAdminOrder` | Eseguito sulla pagina di visualizzazione dell'ordine individuale nel Back Office. | Renderizza il pulsante "Esporta PDF" o un widget simile nella pagina dei dettagli dell'ordine, consentendo la generazione di PDF per un singolo ordine. |
| `actionGetAdminOrderButtons` | Eseguito per consentire ai moduli di aggiungere pulsanti personalizzati alla vista dell'ordine di amministrazione. | Fornisce un meccanismo per iniettare pulsanti personalizzati (come "Esporta PDF") nella vista dell'ordine di PrestaShop 1.7+, garantendo la compatibilità con l'interfaccia utente moderna. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e per scaricare le ultime versioni del modulo "Esportazione PDF Ordini & Lista di Controllo Magazzino", visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità o alla configurazione del modulo.
