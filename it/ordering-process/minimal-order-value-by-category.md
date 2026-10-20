---
title: "Valore minimo ordine per categoria - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Valore minimo ordine per categoria' di MyPresta.eu."
sidebar:
  label: "Valore minimo ordine per categoria - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Minimal order value by category su MyPresta.eu](https://mypresta.eu/modules/ordering-process/minimal-order-value-by-category.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/minimal-order-value-by-category/)
>
> ---


# Valore minimo ordine per categoria

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e sono solitamente disponibili per impostazione predefinita sulla maggior parte degli ambienti di hosting.

## 2. Panoramica Completa della Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo, accessibile immediatamente dopo l'installazione o cliccando su "Configura" dal Gestore Moduli.

- **Cosa fa questa impostazione:** Questa schermata serve principalmente come punto di ingresso. Sebbene la logica principale del modulo sia gestita tramite una schermata di amministrazione dedicata, questa pagina di configurazione iniziale assicura che il modulo sia installato correttamente e fornisce un link o un reindirizzamento all'interfaccia di gestione principale.
- **Effetto della modifica di questa impostazione:** Tipicamente, questa schermata non ha interruttori diretti o campi di input per il commerciante. Il suo scopo principale è confermare lo stato del modulo e guidarti al passaggio successivo.
- **Valore consigliato:** Nessun valore diretto da impostare qui. Assicurati solo che il modulo sia abilitato.
- **Scenario / esempio del commerciante:** Dopo l'installazione, atterrerai qui. Potresti vedere un messaggio che conferma l'installazione e un pulsante o un link a "Gestisci Valori Minimi Ordine" o simile, che ti porterà alla schermata `AdminMobcController` dedicata.

### 2.2 Schermata Admin Dedicata: Gestione Valore Minimo Ordine per Categoria (Back Office > Moduli > Valore minimo ordine per categoria)

Questa è l'interfaccia di gestione principale dove definisci e controlli tutti i tuoi valori minimi d'ordine specifici per categoria. Tipicamente troverai una nuova voce di menu sotto "Moduli" o "Catalogo" (a seconda della tua versione di PrestaShop e dell'hook del modulo) denominata "Valore minimo ordine per categoria" o simile.

**Nome Schermata e Posizione Menu:**
Troverai questa schermata navigando su **Moduli > Valore minimo ordine per categoria** nel menu del tuo Back Office PrestaShop.

**Azioni e Impostazioni Disponibili:**
Questa schermata presenta un elenco (griglia) di tutte le tue regole di valore minimo d'ordine attualmente definite. Per ogni regola, vedrai tipicamente:

- **Nome Categoria:** Il nome della categoria PrestaShop a cui si applica la regola.
- **Valore Minimo:** L'importo minimo d'ordine richiesto per i prodotti all'interno di quella categoria.
- **Valuta:** La valuta in cui è impostato il valore minimo (solitamente la valuta predefinita del tuo negozio, ad esempio, USD, EUR).
- **Azioni:** Pulsanti per "Modifica" o "Elimina" una regola esistente.

Troverai anche un pulsante, solitamente in alto a destra, per **"Aggiungi Nuova Regola"** o **"Aggiungi Nuovo Valore Minimo Ordine"**. Cliccando su questo si aprirà un modulo dove potrai:

1. **Seleziona Categoria:**

   - **Cosa fa questa impostazione:** Ti consente di scegliere a quale categoria PrestaShop esistente si applicherà questa regola di valore minimo d'ordine.
   - **Effetto della modifica di questa impostazione:** La selezione di una categoria collega la regola a tutti i prodotti all'interno di quella categoria (e delle sue sottocategorie, a seconda della logica del modulo).
   - **Valore consigliato:** Seleziona la categoria specifica a cui desideri applicare il valore minimo d'ordine.
   - **Scenario / esempio del commerciante:** Vuoi impostare un minimo per la tua categoria "Ingrosso". Selezioneresti "Ingrosso" dal menu a discesa.
2. **Valore Minimo Ordine:**

   - **Cosa fa questa impostazione:** Definisce l'importo monetario che i clienti devono spendere per i prodotti *all'interno della categoria selezionata* prima di poter procedere con l'ordine.
   - **Effetto della modifica di questa impostazione:**
     - *Quando impostato su un valore (ad esempio, 50.00):* I clienti devono avere almeno 50.00 unità della tua valuta predefinita di prodotti dalla categoria selezionata nel loro carrello. In caso contrario, verranno bloccati al checkout con un messaggio.
     - *Quando lasciato vuoto o impostato su 0:* Questa regola sarebbe effettivamente disabilitata per la categoria, consentendo qualsiasi valore. Tuttavia, è meglio eliminare la regola se non ne hai bisogno.
   - **Valore consigliato:** Un valore numerico positivo che riflette il tuo minimo desiderato (ad esempio, `25.00`, `100.00`).
   - **Scenario / esempio del commerciante:** Per la tua categoria "Ingrosso", imposti questo a `100.00`. Un cliente con 90€ di prodotti all'ingrosso non può effettuare il checkout finché non aggiunge altri 10€.
3. **Pulsante Salva:**

   - **Cosa fa:** Applica le modifiche o crea la nuova regola.
   - **Effetto:** La nuova regola sarà attiva immediatamente e il sistema inizierà a far rispettare il valore minimo dell'ordine per la categoria selezionata.

**Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

1. **Rivedi le regole esistenti:** Controlla periodicamente il tuo elenco di regole per assicurarti che siano ancora pertinenti alla tua strategia aziendale.
2. **Aggiungi nuove regole:** Se introduci nuove categorie di prodotti che richiedono minimi specifici (ad esempio, una nuova linea B2B), aggiungi una regola per esse.
3. **Modifica le regole esistenti:** Regola i valori minimi in base alle modifiche dei prezzi dei prodotti, alle condizioni di mercato o alle strategie promozionali.
4. **Elimina le regole obsolete:** Rimuovi le regole per le categorie che non richiedono più un minimo o sono state interrotte.

### 2.3 Tabella di Riferimento Rapido della Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Pagina di Configurazione del Modulo | (Nessuna impostazione diretta) | N/A | Punto di ingresso al modulo; conferma l'installazione e indirizza alla schermata di gestione. |
| Gestione Valore Minimo Ordine per Categoria | Aggiungi Nuova Regola / Modifica Regola > Seleziona Categoria | N/A | Collega un valore minimo d'ordine a una specifica categoria di prodotti PrestaShop. |
| Gestione Valore Minimo Ordine per Categoria | Aggiungi Nuova Regola / Modifica Regola > Valore Minimo Ordine | Il tuo minimo desiderato (es. `50.00`) | Imposta l'importo monetario richiesto per i prodotti all'interno della categoria scelta. |

## 3. Risoluzione dei Problemi del Commerciante e Domande Frequenti (FAQ)

**D1: Ho impostato un valore minimo, ma non funziona. I clienti possono ancora effettuare il checkout con meno.**
R:

- **Controlla lo Stato del Modulo:** Assicurati che il modulo sia abilitato in **Moduli > Gestione moduli**.
- **Verifica la Configurazione della Regola:** Vai su **Moduli > Valore minimo ordine per categoria** e conferma che la regola per la categoria specifica sia attiva, abbia un valore maggiore di zero e sia correttamente assegnata alla categoria desiderata.
- **Svuota la Cache:** A volte la cache di PrestaShop può impedire che le modifiche appaiano immediatamente. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti).
- **Assegnazione Categoria Prodotto:** Ricontrolla che i prodotti in questione siano effettivamente assegnati alla categoria per la quale hai impostato il minimo.

**D2: Il messaggio visualizzato ai clienti non è chiaro o non corrisponde alla lingua del mio negozio.**
R:

- **Traduzioni del Modulo:** Il modulo dovrebbe supportare il sistema di traduzione di PrestaShop. Vai su **Internazionale > Traduzioni**, seleziona "Traduzioni dei moduli installati", scegli il tuo tema e poi seleziona "Valore minimo ordine per categoria". Puoi quindi personalizzare i messaggi di avviso per renderli più specifici o tradurli in altre lingue.
- **Stile del Tema Personalizzato:** Se il messaggio appare ma sembra fuori posto, il CSS del tuo tema potrebbe sovrascrivere gli stili del modulo. Un webmaster può aiutarti a regolare il file `mobc.css` o aggiungere CSS personalizzato al tuo tema per garantire una visualizzazione corretta.

**D3: Posso impostare minimi diversi per diversi gruppi di clienti (ad esempio, al dettaglio vs. all'ingrosso)?**
R: La versione attuale del modulo "Valore minimo ordine per categoria" si concentra sui minimi a livello di categoria, non su quelli specifici per gruppo di clienti. Se hai bisogno di questa funzionalità avanzata, potresti dover utilizzare categorie separate per diversi gruppi di clienti (ad esempio, "Prodotti all'ingrosso" vs. "Prodotti al dettaglio") e applicare regole a quelle categorie distinte.

**D4: Cosa succede se un prodotto si trova in più categorie e solo una ha un minimo?**
R: Il modulo calcola il valore totale dei prodotti all'interno di *ogni* categoria che ha una regola di minimo. Se un prodotto si trova nella Categoria A (nessun minimo) e nella Categoria B (minimo 50€), il suo valore contribuirà al totale della Categoria B se aggiunto al carrello. Il cliente deve soddisfare il minimo per la Categoria B in base alla somma di tutti i prodotti nel carrello che appartengono alla Categoria B.

**D5: Ho eliminato una categoria, ma la regola ad essa associata è ancora visibile nella configurazione del modulo.**
R: Se elimini una categoria direttamente dal menu Catalogo di PrestaShop, la regola del modulo associata a quella categoria potrebbe diventare orfana. Dovresti andare manualmente su **Moduli > Valore minimo ordine per categoria** ed eliminare la regola corrispondente dall'elenco per mantenere pulita la tua configurazione.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'Architettura

Il modulo "Valore minimo ordine per categoria" (`mobc`) segue un modello MVC standard di PrestaShop. Estende principalmente `Module` per la sua funzionalità principale e `AdminController` per la sua interfaccia di gestione del back-office. Le interazioni del front-office sono gestite tramite `ModuleFrontController` per le richieste AJAX e il rendering dei template. Il modulo non utilizza classi `ObjectModel` personalizzate ma si basa sulle entità `Category` e `Product` del core di PrestaShop per il recupero dei dati. La configurazione è memorizzata in `ps_configuration` e in una tabella di database personalizzata per le mappature categoria-valore.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**:

  - `controllers/front/ajax.php`
    - **Nome Classe:** `MobcAjaxModuleFrontController` (estende `ModuleFrontController`)
    - **Responsabilità:** Gestisce le richieste AJAX dal front-office, principalmente per controllare il contenuto del carrello rispetto ai valori minimi d'ordine definiti per categoria. Probabilmente riceve i dati del carrello e restituisce una risposta JSON che indica se i minimi sono soddisfatti e, in caso contrario, quali categorie sono carenti e di quanto. Questo è cruciale per la validazione in tempo reale sulla pagina del carrello senza ricariche complete della pagina.
  - `controllers/front/index.php`
    - **Nome Classe:** `MobcIndexModuleFrontController` (estende `ModuleFrontController`)
    - **Responsabilità:** Questo controller potrebbe servire come fallback o un semplice punto di ingresso, ma data la funzionalità del modulo, il suo ruolo principale è probabilmente minimo, possibilmente reindirizzando o servendo una pagina base se acceduto direttamente. La logica principale del front-office è prevista in `ajax.php`.
- **Controller Admin Back-Office**:

  - `controllers/admin/AdminMobc.php`
    - **Nome Classe:** `AdminMobcController` (estende `ModuleAdminController`)
    - **Nome Tab:** Valore minimo ordine per categoria (o simile, tipicamente sotto "Moduli" o "Catalogo").
    - **Entità Gestita:** Gestisce l'entità `mobc` personalizzata, che rappresenta le mappature categoria-valore minimo.
    - **Responsabilità:** Fornisce l'interfaccia CRUD (Create, Read, Update, Delete) per la gestione delle regole di valore minimo d'ordine. Gestisce l'elenco delle regole esistenti in una griglia, la visualizzazione di moduli per l'aggiunta/modifica delle regole (selezione delle categorie, inserimento dei valori minimi) e l'elaborazione delle sottomissioni dei moduli. Interagisce con la tabella del database del modulo per le voci `mobc`.
  - `controllers/admin/index.php`
    - **Nome Classe:** `AdminMobcIndexController` (estende `ModuleAdminController`)
    - **Responsabilità:** Simile a `index.php` del front-office, questo potrebbe essere un segnaposto o un semplice reindirizzatore. La logica principale dell'amministrazione risiede in `AdminMobc.php`.

### 4.3 Classi Core e Modelli (`classes/`)

Il dossier del modulo non indica classi personalizzate nella directory `classes/`. Ciò suggerisce che la gestione dei dati del modulo per le mappature categoria-valore viene eseguita direttamente all'interno di `AdminMobcController` o `index.php` (file principale del modulo) utilizzando `Db::getInstance()` o estendendo un `ObjectModel` generico all'interno del file principale `mobc.php` stesso senza creare un file di classe dedicato.

Dato che `AdminMobcController` gestisce un'entità "mobc", è altamente probabile che `AdminMobcController` definisca direttamente `$this->object` e `$this->fields_list`, oppure che ci sia una definizione implicita di `ObjectModel` all'interno del file `mobc.php` principale che il controller sfrutta.

### 4.4 Risorse JavaScript (`views/js/`)

- `mobc/views/js/mobc.js`
  - **Ambito:** Front-office.
  - **Responsabilità:** Questo script è cruciale per la validazione in tempo reale del carrello. Probabilmente:
    - Collega i listener di eventi alle modifiche della quantità del carrello, alle rimozioni di prodotti o ai caricamenti di pagina sulla pagina del carrello.
    - Attiva chiamate AJAX a `controllers/front/ajax.php` per inviare i dati del carrello corrente.
    - Riceve la risposta JSON dal controller AJAX.
    - Aggiorna dinamicamente il DOM sulla pagina del carrello per visualizzare messaggi di avviso se i minimi non sono soddisfatti.
    - Disabilita/abilita il pulsante di checkout in base al risultato della validazione.
    - Può includere logica per la visualizzazione di messaggi pop-up o l'evidenziazione di categorie problematiche.

### 4.5 Fogli di Stile CSS (`views/css/`)

- `mobc/views/css/mobc.css`
  - **Ambito:** Stile del cliente del front-office.
  - **Componenti UI principali e contenitori che stilizza:** Questo foglio di stile è responsabile della presentazione visiva dei messaggi di avviso visualizzati sulla pagina del carrello. Definirà gli stili per:
    - Contenitori che ospitano i messaggi di avviso (ad esempio, `div.mobc-warning-message`).
    - Elementi di testo all'interno degli avvisi (ad esempio, `span.mobc-category-name`, `span.mobc-remaining-amount`).
    - Potenzialmente lo stile per il pulsante di checkout disabilitato o altri segnali visivi.
  - **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere nel loro tema:** Gli sviluppatori possono ispezionare l'HTML generato sulla pagina del carrello per identificare i nomi di classe specifici (ad esempio, `.mobc-alert`, `.mobc-error-list`, `.mobc-checkout-blocked`) e sovrascriverli nel `custom.css` o `theme.css` del loro tema per adattarli al branding del negozio.

### 4.6 Struttura del Template Smarty (`views/templates/`)

- **Template hook (`views/templates/hook/`)**:
  - `mobc/views/templates/front/displayShoppingCart.tpl`
    - **Hook:** Questo template è probabilmente renderizzato in un hook sulla pagina del carrello, come `displayShoppingCartFooter` o `displayShoppingCartExtraContent`.
    - **Output Blocco Visivo:** Emette la struttura HTML per i messaggi di avviso che informano i clienti sui valori minimi d'ordine non soddisfatti per le categorie. Questo template conterrà segnaposto per i nomi delle categorie, gli importi richiesti e l'importo rimanente necessario, che vengono popolati dal JavaScript e dal controller AJAX.

### 4.7 Schema del Database e Mappa degli Hook

- **Tabelle del Database**:

  - `ps_mobc_category_value` (o simile, basato sull'entità di `AdminMobcController`): Questa tabella personalizzata memorizza la mappatura tra gli ID delle categorie e i rispettivi valori minimi d'ordine.
    - `id_mobc_category_value` (Chiave Primaria, INT)
    - `id_category` (INT, Chiave Esterna a `ps_category.id_category`)
    - `min_value` (DECIMAL, memorizza l'importo monetario minimo)
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)
  - `ps_configuration`: Tabella di configurazione standard di PrestaShop. Il modulo potrebbe memorizzare le sue impostazioni generali (se presenti, anche se nessuna esplicitamente rilevata) qui, prefissate con `MOBC_`.
- **Tabella degli Hook Registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Per includere `mobc.css` e `mobc.js` per la funzionalità del front-office. |
| `displayShoppingCart` | Sulla pagina del carrello, tipicamente prima o dopo il riepilogo del carrello. | Per renderizzare `displayShoppingCart.tpl` per la visualizzazione dei messaggi di avviso. |
| `actionCartSave` | Dopo che un carrello viene salvato (ad esempio, prodotto aggiunto/rimosso, quantità modificata). | Per attivare la logica del modulo per rivalutare i minimi di categoria e potenzialmente aggiornare lo stato del carrello o le variabili di sessione. |
| `actionFrontControllerSetMedia` | Prima che un controller front-office renda il suo output, consentendo ai moduli di aggiungere JS/CSS. | Per registrare file JavaScript e CSS specifici del modulo per il front-office. |
| `actionAdminControllerSetMedia` | Prima che un controller admin renda il suo output. | Per registrare file JavaScript e CSS specifici del modulo per il back-office (ad esempio, per `AdminMobcController`). |
| `displayAdminProductsExtra` (o simile) | Sulla pagina di modifica del prodotto nel back office. | Potenzialmente per visualizzare informazioni sui minimi di categoria relativi al prodotto corrente, anche se non esplicitamente confermato dal dossier. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Valore minimo ordine per categoria", si prega di fare riferimento al proprio account cliente su MyPresta.eu. Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda riguardante la funzionalità e la configurazione del modulo.
