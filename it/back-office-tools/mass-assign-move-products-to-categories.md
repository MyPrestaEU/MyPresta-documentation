---
title: "Assegnazione/spostamento massivo di prodotti a categorie - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Assegnazione/spostamento massivo di prodotti a categorie' di MyPresta.eu."
sidebar:
  label: "Assegnazione/spostamento massivo di prodotti a categorie - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Mass assign / move products to categories su MyPresta.eu](https://mypresta.eu/modules/administration-tools/mass-assign-move-products-to-categories.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/mass-assign-move-products-to-categories/)
>
> ---


# Assegnazione/spostamento massivo di prodotti a categorie

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 9.x, 8.x, 1.7.x, 1.6.x, 1.5.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Non sono richieste configurazioni speciali del server oltre a un ambiente di hosting PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

Il modulo "Assegnazione/spostamento massivo di prodotti a categorie" fornisce un'interfaccia simile a una procedura guidata per accompagnarti nel processo di gestione massiva delle categorie di prodotti.

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Gestione moduli > Configura "Assegnazione/spostamento massivo di prodotti a categorie")

Dopo aver cliccato su "Configura", verrai indirizzato alla pagina di configurazione principale del modulo, che funge da procedura guidata passo-passo.

#### Passaggio 1: Seleziona i prodotti da gestire

Questa sezione ti consente di definire quali prodotti desideri modificare.

- **Cosa fa questa impostazione:** Questo è il primo passo cruciale in cui identifichi il gruppo di prodotti che saranno interessati dall'azione di massa.
- **Effetto della modifica di questa impostazione:** I prodotti che selezioni qui saranno gli unici elaborati nei passaggi successivi.
- **Valore consigliato:** Utilizza la barra di ricerca per trovare prodotti per nome. Puoi aggiungere più prodotti all'elenco.
- **Scenario/esempio del commerciante:**
  - *Scenario 1: Prodotti specifici:* Vuoi spostare "Prodotto A", "Prodotto B" e "Prodotto C" in una nuova categoria. Cercheresti ogni prodotto e li aggiungeresti all'elenco.
  - *Scenario 2: Prodotti da una categoria esistente:* Vuoi spostare tutti i prodotti attualmente nella tua categoria "Vecchia Collezione" in una nuova categoria "Articoli Archiviati". Per prima cosa selezioneresti tutti i prodotti da "Vecchia Collezione" qui.

#### Passaggio 2: Seleziona le categorie a cui assegnare/spostare i prodotti

Questa sezione ti consente di scegliere le categorie di destinazione per i prodotti selezionati.

- **Cosa fa questa impostazione:** Qui, specifichi le categorie in cui i prodotti del Passaggio 1 verranno assegnati o spostati.
- **Effetto della modifica di questa impostazione:** I prodotti selezionati verranno collegati a queste categorie.
- **Valore consigliato:** Utilizza l'albero delle categorie per selezionare una o più categorie di destinazione.
- **Scenario/esempio del commerciante:**
  - *Scenario 1: Assegna a una nuova categoria:* Hai selezionato 5 prodotti nel Passaggio 1. Ora selezioni "Nuovi Arrivi" e "Bestseller" qui. I 5 prodotti verranno assegnati sia a "Nuovi Arrivi" che a "Bestseller".
  - *Scenario 2: Sposta in una singola categoria:* Hai selezionato 10 prodotti. Selezioni "Saldi Stagionali" qui. A seconda della tua scelta nel Passaggio 3, questi prodotti verranno aggiunti a "Saldi Stagionali" o spostati esclusivamente in essa.

#### Passaggio 3: Cosa fare con i prodotti selezionati?

Questo è il passaggio più critico, che determina la natura dell'azione di massa.

- **Cosa fa questa impostazione:** Questa selezione a pulsante radio determina se i prodotti vengono *assegnati* (aggiunti a nuove categorie mantenendo quelle esistenti) o *spostati* (rimossi dalle categorie esistenti e posizionati solo in quelle nuove).
- **Effetto della modifica di questa impostazione:**
  - **Assegna prodotti alle categorie selezionate:**
    - *Quando selezionato:* I prodotti scelti nel Passaggio 1 verranno *aggiunti* alle categorie selezionate nel Passaggio 2. Manterranno tutte le loro attuali associazioni di categoria. Questo è utile per elencare prodotti in più sezioni o aggiungerli a categorie promozionali senza interrompere il loro posizionamento primario.
    - *Scenario del commerciante:* Hai un prodotto in "Elettronica" e "Gadget". Vuoi aggiungerlo a "Offerte Festività" senza rimuoverlo da "Elettronica" o "Gadget". Selezioneresti "Assegna".
  - **Sposta prodotti nelle categorie selezionate (rimuovi dalle categorie attuali):**
    - *Quando selezionato:* I prodotti scelti nel Passaggio 1 verranno *rimossi* da tutte le categorie a cui sono attualmente assegnati, e quindi *solo* assegnati alle categorie selezionate nel Passaggio 2. Questa è una ricategorizzazione completa.
    - *Scenario del commerciante:* Hai un prodotto in "Vecchia Collezione" e "Articoli Fuori Produzione". Vuoi che appaia *solo* in "Prodotti Archiviati". Selezioneresti "Sposta".
- **Valore consigliato:** Questo dipende interamente dal tuo obiettivo specifico. Considera attentamente se vuoi *aggiungere* categorie o *sostituirle*.
- **Scenario/esempio del commerciante:**
  - *Assegna:* Stai organizzando una vendita "Black Friday". Selezioni tutti i prodotti in saldo e li "Assegni" alla categoria "Offerte Black Friday". Appaiono ancora nelle loro categorie originali (es. "T-shirt", "Laptop"), ma ora anche sotto "Offerte Black Friday".
  - *Sposta:* Hai deciso di ristrutturare la sezione "Abbigliamento Donna". Selezioni tutti i prodotti da "Vestiti" e "Gonne" e li "Sposti" in una nuova categoria "Fondi e Vestiti Donna". Non appariranno più nelle vecchie categorie "Vestiti" o "Gonne".

#### Pulsante "Esegui"

- **Cosa fa questa impostazione:** Questo pulsante avvia l'operazione di massa in base alle tue selezioni nei passaggi precedenti.
- **Effetto della modifica di questa impostazione:** Una volta cliccato, il modulo elaborerà tutti i prodotti selezionati in base all'azione scelta (assegna o sposta) e alle categorie di destinazione. Di solito apparirà un messaggio di conferma o di successo.
- **Valore consigliato:** Clicca su questo solo quando sei assolutamente sicuro delle tue selezioni.
- **Scenario/esempio del commerciante:** Dopo aver esaminato attentamente le selezioni di prodotti e categorie e aver confermato l'azione desiderata (assegna o sposta), clicca su "Esegui" per applicare le modifiche al catalogo prodotti del tuo negozio.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Principale | **Passaggio 1: Seleziona Prodotti** | N/A (input utente) | Definisce i prodotti specifici da influenzare dall'azione di massa. |
| Configurazione Principale | **Passaggio 2: Seleziona Categorie** | N/A (input utente) | Definisce le categorie di destinazione dove i prodotti verranno assegnati o spostati. |
| Configurazione Principale | **Passaggio 3: Cosa fare?** | N/A (scelta utente) | **Assegna:** Aggiunge prodotti a nuove categorie, mantenendo quelle esistenti. **Sposta:** Rimuove da tutte le categorie attuali, assegna solo a quelle nuove. |
| Configurazione Principale | **Pulsante Esegui** | N/A (azione utente) | Attiva l'operazione di assegnazione/spostamento massivo di categorie. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho cliccato su "Esegui", ma non è successo nulla, o non vedo le modifiche.**
R:

1. **Svuota la cache:** Dopo qualsiasi modifica significativa in PrestaShop, specialmente assegnazioni di categorie o prodotti, dovresti sempre svuotare la cache del tuo negozio. Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti).
2. **Controlla lo stato del prodotto:** Assicurati che i prodotti che stai cercando di assegnare/spostare siano attivi e visibili.
3. **Controlla lo stato della categoria:** Assicurati che le categorie di destinazione siano attive e visibili.
4. **Riesegui il modulo:** Torna al modulo, riseleziona i tuoi prodotti e categorie e riprova.

**D: I miei prodotti sono scomparsi dalle loro categorie originali dopo aver usato il modulo!**
R: Questo probabilmente significa che hai selezionato "Sposta prodotti nelle categorie selezionate (rimuovi dalle categorie attuali)" nel Passaggio 3. Questa opzione è progettata per *sostituire* le assegnazioni di categoria esistenti con quelle nuove. Se questo è stato involontario, dovrai riassegnare manualmente i prodotti alle loro categorie originali o utilizzare nuovamente il modulo con l'opzione "Assegna prodotti" per riaggiungerli. Controlla sempre due volte il Passaggio 3 prima di eseguire!

**D: Posso annullare un'assegnazione/spostamento di massa?**
R: Il modulo non ha un pulsante "annulla". Questo è il motivo per cui è fondamentale **eseguire sempre il backup del database prima di eseguire qualsiasi azione di massa** sul tuo negozio. Se hai commesso un errore, ripristinare un backup è il modo più sicuro per annullare. Altrimenti, dovrai correggere manualmente le assegnazioni di categoria o utilizzare nuovamente il modulo per riassegnare i prodotti secondo necessità.

**D: La ricerca prodotti non trova i miei prodotti.**
R:

1. **Controlla l'ortografia:** Assicurati di digitare correttamente il nome del prodotto.
2. **Stato del prodotto:** Assicurati che il prodotto sia attivo nel tuo catalogo.
3. **Svuota la cache del browser:** A volte la cache del browser può interferire con le funzioni di ricerca AJAX. Prova a svuotare la cache del tuo browser o a utilizzare una finestra in incognito.

**D: Questo modulo influisce sulla categoria predefinita di un prodotto?**
R: Il modulo gestisce principalmente le categorie *associate*. Sebbene lo spostamento di un prodotto possa implicitamente cambiare la sua categoria predefinita se la vecchia predefinita viene rimossa e viene assegnata solo una nuova categoria, è buona pratica verificare e impostare manualmente la categoria predefinita nella pagina di modifica del prodotto se hai requisiti SEO o di navigazione specifici per la categoria predefinita.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

Questa sezione fornisce una panoramica tecnica per sviluppatori e webmaster che desiderano comprendere, eseguire il debug o estendere il modulo "Assegnazione/spostamento massivo di prodotti a categorie".

### 4.1 Panoramica dell'Architettura

Il modulo `masspc` (Mass Product Categories) è un modulo PrestaShop standard che opera principalmente nel Back Office. Sfrutta AJAX per la ricerca di prodotti e la selezione di categorie, fornendo un'esperienza utente simile a una procedura guidata. La logica principale per la manipolazione di prodotti e categorie è gestita all'interno della classe principale del modulo, che estende `Module`. Non introduce classi `ObjectModel` personalizzate o Controller Admin dedicati oltre alla sua pagina di configurazione principale.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza Controller Admin dedicati per il Front-Office o il Back-Office nella directory `controllers/`. Tutta la logica è gestita direttamente all'interno del file principale del modulo `masspc.php` (o `ajax_products_list.php` come da dossier, che è una convenzione di denominazione insolita per il file principale del modulo ma implica che gestisce la logica principale e le richieste AJAX).

### 4.3 Classi e Modelli Core (`classes/`)

Questo modulo non introduce classi o modelli personalizzati in una directory `classes/`. Tutta la logica principale è incapsulata all'interno del file principale del modulo. La manipolazione dei dati di prodotto e categoria si basa sulle classi `ObjectModel` native di PrestaShop `Product` e `Category` e sui loro metodi associati (ad esempio, `Product::updateCategories()`).

### 4.4 Risorse JavaScript (`views/js/`)

- **`masspc/lib/searchTool/views/js/autocomplete.js`**
  - **Ambito:** Back-office (utilizzato all'interno della pagina di configurazione del modulo).
  - **Descrizione:** Questo script probabilmente fornisce la funzionalità principale per una funzione di ricerca con completamento automatico basata su AJAX, in particolare per trovare prodotti per nome. Ascolta l'input dell'utente in un campo di ricerca, invia richieste AJAX al backend del modulo (probabilmente `ajax_products_list.php` stesso o un metodo al suo interno) e visualizza i suggerimenti. Gestisce la selezione dei prodotti e l'aggiunta all'elenco per l'elaborazione.
- **`masspc/views/js/jquery.autocomplete.js`**
  - **Ambito:** Back-office (utilizzato all'interno della pagina di configurazione del modulo).
  - **Descrizione:** Questo sembra essere un plugin jQuery o uno script personalizzato che implementa o migliora la funzionalità di completamento automatico. Potrebbe essere una dipendenza per `autocomplete.js` o un'implementazione alternativa/più vecchia. Gestirebbe il rendering visivo dei suggerimenti di completamento automatico e l'interazione quando un utente seleziona un elemento.

### 4.5 Fogli di Stile CSS (`views/css/`)

- **`masspc/lib/searchTool/views/css/autocomplete.css`**
  - **Ambito:** Back-office (stili la pagina di configurazione del modulo).
  - **Descrizione:** Questo foglio di stile fornisce lo stile visivo per l'input di ricerca con completamento automatico, il menu a discesa dei suggerimenti e potenzialmente l'elenco dei prodotti selezionati all'interno dell'interfaccia di configurazione del modulo. Gli sviluppatori possono sovrascrivere questi stili nel loro tema admin personalizzato o aggiungendo regole CSS più specifiche.

### 4.6 Struttura del Template Smarty (`views/templates/`)

- **`masspc/lib/searchTool/views/scripts.tpl`**
  - **Ambito:** Back-office (incluso nella pagina di configurazione del modulo).
  - **Descrizione:** Questo template probabilmente include codice JavaScript o link a file JS (`autocomplete.js`, `jquery.autocomplete.js`) e potenzialmente file CSS (`autocomplete.css`) richiesti per l'interfaccia di ricerca e selezione dei prodotti. Viene tipicamente utilizzato per iniettare risorse nell' `<head>` o `<body>` della pagina admin.
- **`masspc/views/templates/admin/cselection.tpl`**
  - **Ambito:** Back-office (pagina di configurazione admin).
  - **Descrizione:** Questo template renderizza la sezione "Passaggio 2: Seleziona le categorie a cui assegnare/spostare i prodotti" del modulo. Visualizza la struttura ad albero delle categorie, consentendo all'amministratore di selezionare le categorie di destinazione. Probabilmente utilizza una struttura ricorsiva per visualizzare categorie padre e figlio.
- **`masspc/views/templates/admin/target_products.tpl`**
  - **Ambito:** Back-office (pagina di configurazione admin).
  - **Descrizione:** Questo template renderizza la sezione "Passaggio 1: Seleziona i prodotti da gestire". Include il campo di input per la ricerca prodotti (dove opera `autocomplete.js`) e visualizza l'elenco dei prodotti che sono stati selezionati per l'azione di massa.
- **`masspc/views/templates/admin/wtd.tpl`**
  - **Ambito:** Back-office (pagina di configurazione admin).
  - **Descrizione:** Questo template renderizza la sezione "Passaggio 3: Cosa fare con i prodotti selezionati?". Contiene i pulsanti radio per "Assegna prodotti alle categorie selezionate" e "Sposta prodotti nelle categorie selezionate", insieme alle loro descrizioni.
- **`masspc/views/templates/hook/form.tpl`**
  - **Ambito:** Back-office (pagina di configurazione admin).
  - **Descrizione:** Questo è probabilmente il template wrapper principale per il modulo di configurazione del modulo, che include gli altri template `admin/` (`target_products.tpl`, `cselection.tpl`, `wtd.tpl`) per costruire l'interfaccia completa della procedura guidata. Contenerebbe la struttura generale del modulo e il pulsante "Esegui".

### 4.7 Schema del Database e Mappa degli Hook

- **Tabelle del Database**:
  - Questo modulo non crea tabelle di database personalizzate. Interagisce direttamente con le tabelle core di PrestaShop:
    - `ps_product_category`: Per la gestione delle associazioni prodotto-categoria.
    - `ps_product_shop`: Per i dati specifici del negozio relativi al prodotto, inclusa la categoria predefinita.
    - `ps_category`: Per il recupero dei nomi e della struttura delle categorie.
    - `ps_product`: Per il recupero dei nomi e dei dettagli dei prodotti per la ricerca.
- **Tabella degli Hook Registrati**:
  - La funzionalità principale del modulo è accessibile tramite la sua pagina di configurazione, non tramite hook del front-office.
  - Probabilmente utilizza l'hook `displayBackOfficeHeader` per iniettare le sue risorse CSS e JavaScript nell'intestazione del Back Office.

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayBackOfficeHeader` | Renderizza nell' `<head>` delle pagine del Back Office. | Inietta file CSS e JavaScript specifici del modulo per la pagina di configurazione. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Assegnazione/spostamento massivo di prodotti a categorie", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda possiate avere riguardo alla funzionalità e compatibilità del modulo.
