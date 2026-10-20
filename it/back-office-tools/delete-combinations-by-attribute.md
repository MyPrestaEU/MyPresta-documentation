---
title: "Elimina combinazioni per attributo - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Elimina combinazioni per attributo' di MyPresta.eu."
sidebar:
  label: "Elimina combinazioni per attributo - Manuale del commerciante e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Delete combinations by attribute su MyPresta.eu](https://mypresta.eu/modules/administration-tools/delete-combinations-by-attribute.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/delete-combinations-by-attribute/)
>
> ---


# Elimina combinazioni per attributo

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono generalmente sufficienti. Nessun requisito di hosting speciale oltre a una configurazione PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale e unica per il modulo "Elimina combinazioni per attributo". Qui troverai tutti gli strumenti per selezionare ed eliminare le combinazioni.

#### **Sezione superiore: Aggiornamenti e informazioni sul modulo**

Questa sezione visualizza tipicamente informazioni sugli aggiornamenti e le versioni del modulo da MyPresta.eu.

- **Cosa fa questa impostazione:** Fornisce informazioni sugli aggiornamenti disponibili per il modulo, assicurandoti di utilizzare la versione più recente per correzioni di bug e nuove funzionalità.
- **Effetto della modifica di questa impostazione:** Questi sono campi informativi e non hanno impostazioni dirette che puoi modificare. Visualizzano semplicemente i dati.
- **Valore consigliato:** Mantieni il tuo modulo aggiornato all'ultima versione.
- **Scenario / esempio del commerciante:** Vedi una notifica che è disponibile una nuova versione `1.3.1`. Dovresti quindi scaricarla da MyPresta.eu e aggiornare il modulo.

#### **Opzioni di configurazione principali**

1. **Valore attributo**

   - **Cosa fa questa impostazione:** Questo è il filtro primario. Ti consente di selezionare un valore di attributo specifico (ad esempio, "Rosso", "Piccolo", "Cotone") che desideri eliminare. Il modulo cercherà tutte le combinazioni di prodotti che includono questo valore di attributo selezionato.
   - **Effetto della modifica di questa impostazione:**
     - *Quando viene selezionato un valore:* Il modulo identificherà tutte le combinazioni nel tuo negozio che utilizzano questo valore di attributo specifico.
     - *Quando non viene selezionato alcun valore:* Non puoi procedere con il processo di eliminazione poiché il modulo non sa quali combinazioni eliminare.
   - **Valore consigliato:** Seleziona il valore di attributo esatto per il quale desideri rimuovere le combinazioni.
   - **Scenario / esempio del commerciante:** Hai interrotto tutti i prodotti di colore "Arancione". Selezioneresti "Arancione" da questo menu a discesa per eliminare tutte le combinazioni con "Arancione" come uno dei loro attributi.
2. **Quantità**

   - **Cosa fa questa impostazione:** Ti consente di filtrare le combinazioni in base alla loro quantità di magazzino attuale. Puoi scegliere di eliminare le combinazioni solo se la loro quantità è inferiore, uguale o superiore a un numero specificato.
   - **Effetto della modifica di questa impostazione:**
     - *Quando "Cosa fare" è impostato su "minore di" e "Quantità" è 5:* Solo le combinazioni con una quantità di magazzino di 4 o meno verranno considerate per l'eliminazione.
     - *Quando "Cosa fare" è impostato su "uguale a" e "Quantità" è 0:* Solo le combinazioni con esattamente 0 scorte verranno considerate.
   - **Valore consigliato:** Spesso usato con "uguale a" e "0" per pulire le combinazioni esaurite.
   - **Scenario / esempio del commerciante:** Vuoi rimuovere tutte le combinazioni di prodotti "Arancione" che sono attualmente esaurite. Selezioneresti "Arancione" in "Valore attributo", quindi imposteresti "Cosa fare" su "uguale a" e "Quantità" su "0".
3. **Cosa fare (con Quantità)**

   - **Cosa fa questa impostazione:** Questo menu a discesa funziona in combinazione con il campo "Quantità" per definire la condizione per il filtro delle scorte. Le opzioni includono tipicamente "minore di", "uguale a", "maggiore di".
   - **Effetto della modifica di questa impostazione:** Modifica la logica di confronto per il filtro "Quantità".
   - **Valore consigliato:** "uguale a" è comune per eliminare gli articoli esauriti.
   - **Scenario / esempio del commerciante:** Per rimuovere combinazioni con scorte molto basse, potresti scegliere "minore di" e impostare "Quantità" su "3".
4. **Elenco codici di riferimento**

   - **Cosa fa questa impostazione:** Questo campo ti consente di specificare un elenco di codici di riferimento del prodotto (SKU) da includere o escludere dal processo di eliminazione. Questo è utile se vuoi influenzare solo un sottoinsieme di prodotti.
   - **Effetto della modifica di questa impostazione:**
     - *Quando "Campo codice" è "Riferimento" e "Cosa fare" è "includi":* Solo le combinazioni appartenenti a prodotti con questi codici di riferimento specifici verranno influenzate.
     - *Quando "Campo codice" è "Riferimento" e "Cosa fare" è "escludi":* Le combinazioni appartenenti a prodotti con questi codici di riferimento specifici verranno saltate.
   - **Valore consigliato:** Usalo per restringere l'ambito dell'eliminazione a prodotti specifici. Inserisci un codice per riga.
   - **Scenario / esempio del commerciante:** Vuoi rimuovere le combinazioni "Arancione" solo dai prodotti con codici di riferimento `PROD-A`, `PROD-B` e `PROD-C`. Inseriresti questi codici, selezioneresti "Riferimento" per "Campo codice" e "includi" per "Cosa fare".
5. **Campo codice**

   - **Cosa fa questa impostazione:** Definisce a quale campo identificativo del prodotto si riferisce l'"Elenco codici". Le opzioni sono tipicamente "Riferimento" (SKU) o "EAN13" (Codice a barre).
   - **Effetto della modifica di questa impostazione:** Cambia il modo in cui il modulo interpreta i codici inseriti in "Elenco codici".
   - **Valore consigliato:** "Riferimento" per SKU interni, "EAN13" per codici a barre.
   - **Scenario / esempio del commerciante:** Se il tuo elenco contiene codici a barre EAN13, seleziona "EAN13" qui.
6. **Elenco codici (Cosa fare)**

   - **Cosa fa questa impostazione:** Determina se l'"Elenco codici di riferimento" (o codici EAN) deve essere *incluso* nel processo di eliminazione (elimina solo da questi prodotti) o *escluso* (elimina da tutti i prodotti TRANNE questi).
   - **Effetto della modifica di questa impostazione:** Controlla l'ambito dei prodotti interessati dall'eliminazione.
   - **Valore consigliato:** "includi" per eliminazioni mirate, "escludi" per eliminazioni ampie con eccezioni.
   - **Scenario / esempio del commerciante:** Vuoi eliminare le combinazioni "Arancione" da tutti i prodotti *eccetto* il tuo best-seller `BESTSELLER-01`. Inseriresti `BESTSELLER-01` nell'"Elenco codici" e selezioneresti "escludi" qui.
7. **Prodotto**

   - **Cosa fa questa impostazione:** Ti consente di selezionare un prodotto specifico per nome. Se selezionato, l'eliminazione si applicherà *solo* alle combinazioni di questo singolo prodotto, sovrascrivendo qualsiasi altro filtro a livello di prodotto.
   - **Effetto della modifica di questa impostazione:**
     - *Quando viene selezionato un prodotto:* Il modulo elaborerà solo le combinazioni appartenenti a questo prodotto specifico.
     - *Quando lasciato vuoto:* Il modulo applicherà i criteri di eliminazione a tutti i prodotti del tuo negozio (soggetti ad altri filtri come "Elenco codici di riferimento").
   - **Valore consigliato:** Usalo per eliminazioni altamente mirate su un singolo prodotto.
   - **Scenario / esempio del commerciante:** Vuoi rimuovere le combinazioni "Arancione" solo dal tuo prodotto "Vestito estivo". Selezioneresti "Vestito estivo" qui.

#### **Pulsante di azione**

- **Pulsante "Elimina combinazioni selezionate"**
  - **Cosa fa questo pulsante:** Questo è il pulsante di azione che, quando cliccato, esegue il processo di eliminazione in base a tutti i criteri che hai impostato sopra.
  - **Effetto del clic su questo pulsante:** **Questa azione è irreversibile!** Tutte le combinazioni di prodotti che corrispondono al "Valore attributo" selezionato, ai filtri "Quantità" e ai filtri "Prodotto" o "Riferimento/EAN" verranno eliminate permanentemente dal tuo database. Ciò include le loro scorte associate, immagini e prezzi specifici.
  - **Valore consigliato:** **ESEGUI SEMPRE un backup completo del database prima di cliccare su questo pulsante.** Ricontrolla attentamente tutte le tue impostazioni.
  - **Scenario / esempio del commerciante:** Dopo aver selezionato attentamente "Colore: Arancione", impostato "Quantità: uguale a 0" e confermato il backup, clicchi su questo pulsante per rimuovere tutte le combinazioni arancioni esaurite.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | **Valore attributo** | *Seleziona valore specifico* | Filtro primario: Elimina le combinazioni contenenti questo valore di attributo. |
| Configurazione modulo | **Quantità** | *0 o numero desiderato* | Filtra le combinazioni in base alla loro quantità di magazzino. |
| Configurazione modulo | **Cosa fare (con Quantità)** | *uguale a* | Definisce la logica di confronto per il filtro "Quantità" (minore di, uguale a, maggiore di). |
| Configurazione modulo | **Elenco codici di riferimento** | *Vuoto o codici specifici* | Elenco di codici di riferimento (SKU) o EAN del prodotto da includere/escludere. Uno per riga. |
| Configurazione modulo | **Campo codice** | *Riferimento* | Specifica se l'"Elenco codici" si riferisce a "Riferimento" o "EAN13". |
| Configurazione modulo | **Elenco codici (Cosa fare)** | *includi* | Determina se i codici elencati sono inclusi o esclusi dall'eliminazione. |
| Configurazione modulo | **Prodotto** | *Vuoto o nome prodotto specifico* | Mira l'eliminazione a un singolo prodotto, sovrascrivendo altri filtri di prodotto. |
| Configurazione modulo | **Elimina combinazioni selezionate** | **Clicca con cautela!** | Esegue l'eliminazione irreversibile delle combinazioni in base a tutti i criteri. **Prima il backup!** |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho cliccato su "Elimina" ma non è successo nulla, o non tutte le combinazioni sono state eliminate.**
R:

- **Controlla i tuoi filtri:** Ricontrolla tutte le tue impostazioni: "Valore attributo", condizioni "Quantità", "Elenco codici" (includi/escludi) e selezione "Prodotto". Anche una piccola discrepanza può impedire che le combinazioni vengano eliminate.
- **Svuota la cache:** A volte la cache di PrestaShop può causare problemi di visualizzazione. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache".
- **Conflitti tra moduli:** Un altro modulo potrebbe interferire. Prova a disabilitare altri moduli uno per uno (specialmente quelli relativi alla gestione dei prodotti o delle combinazioni) per vedere se il problema si risolve.

**D: Ho eliminato accidentalmente combinazioni che non intendevo eliminare. Posso recuperarle?**
R: **No, non direttamente tramite il modulo.** Ecco perché un backup è fondamentale. Se hai un backup recente del database, puoi ripristinare il tuo negozio allo stato in cui si trovava prima dell'eliminazione. Se non hai un backup, dovrai ricreare manualmente le combinazioni.

**D: Il valore dell'attributo che voglio eliminare non compare nel menu a discesa.**
R:

- **Controlla se esiste:** Assicurati che il valore dell'attributo esista effettivamente nel tuo catalogo PrestaShop e sia assegnato ad almeno un prodotto. Vai su **Catalogo > Attributi e funzionalità** per verificarlo.
- **Lingua:** Assicurati di visualizzare il Back Office nella lingua corretta se il nome del valore dell'attributo dipende dalla lingua.

**D: Posso eliminare combinazioni in base alle funzionalità invece che agli attributi?**
R: No, questo modulo è specificamente progettato per funzionare con **attributi e valori di attributo**. Le funzionalità sono un concetto diverso in PrestaShop e non sono supportate da questo modulo per l'eliminazione.

**D: L'eliminazione delle combinazioni eliminerà anche le immagini associate o i prezzi specifici?**
R: Sì, quando una combinazione viene eliminata, tutti i dati direttamente collegati a quella specifica combinazione (come la sua immagine unica, le regole di prezzo specifiche per quella combinazione e la sua quantità di magazzino) verranno anch'essi rimossi. L'immagine principale del prodotto e i prezzi specifici generali del prodotto rimarranno.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo `delcombs` è un modulo PrestaShop semplice, focalizzato principalmente sulla funzionalità del Back Office. Aderisce alla struttura del modulo PrestaShop, utilizzando la classe `Module` per l'installazione, la disinstallazione e la configurazione. La sua logica principale risiede nel metodo `getContent()` del file principale del modulo, dove gestisce l'invio del modulo, la convalida dei dati e l'esecuzione delle operazioni del database per eliminare le combinazioni di prodotti. Non introduce controller front-office personalizzati o ObjectModels complessi, affidandosi invece a query dirette al database e alle classi `Product` e `Combination` del core di PrestaShop per la manipolazione dei dati.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**: Nessuno. Tutte le funzionalità sono confinate al Back Office.
- **Controller Admin Back-Office**: Nessuno. La logica di configurazione ed elaborazione del modulo è gestita all'interno del metodo `getContent()` della classe principale del modulo, che viene renderizzata come parte della pagina di configurazione standard del modulo.

### 4.3 Classi e modelli principali (`classes/`)

Il modulo non definisce alcuna classe personalizzata nella directory `classes/`. Interagisce direttamente con le classi `Product` e `Combination` del core di PrestaShop ed esegue query dirette al database per l'efficienza nelle operazioni di eliminazione di massa.

### 4.4 Risorse JavaScript (`views/js/`)

- `delcombs/views/js/delcombs-admin.js`
  - **Ambito:** Back-office (pagina di configurazione del modulo).
  - **Scopo:** Questo script probabilmente gestisce il comportamento dinamico nel modulo di configurazione del modulo. Ciò potrebbe includere:
    - Chiamate AJAX per la ricerca di prodotti o attributi (ad esempio, per il campo di selezione "Prodotto").
    - Visualizzazione condizionale dei campi del modulo in base alle selezioni dell'utente (ad esempio, mostrare/nascondere i filtri di quantità).
    - Convalida dell'input prima dell'invio del modulo.
    - Finestre di dialogo di conferma prima di eseguire l'azione di eliminazione.
    - Interazioni con il `searchTool` (probabilmente un componente di ricerca personalizzato per prodotti/attributi).

### 4.5 Fogli di stile CSS (`views/css/`)

- `delcombs/views/css/delcombs-admin.css`
  - **Ambito:** Back-office (pagina di configurazione del modulo).
  - **Scopo:** Fornisce lo stile per gli elementi del modulo di configurazione del modulo, garantendo un'interfaccia coerente e user-friendly all'interno del Back Office di PrestaShop.
  - **Selettori di classe CSS chiave:** Probabilmente si rivolge a ID o classi specifici all'interno dell'output `getContent()` del modulo, come gruppi di moduli, campi di input e potenzialmente il componente `searchTool`. Gli sviluppatori possono sovrascrivere questi stili nei loro temi admin personalizzati o aggiungendo CSS con maggiore specificità.

### 4.6 Struttura del template Smarty (`views/templates/`)

- `delcombs/lib/searchTool/views/scripts.tpl`
  - **Ambito:** Back-office.
  - **Scopo:** Questo template probabilmente contiene codice JavaScript o variabili Smarty necessarie per un componente generico di ricerca utilizzato all'interno del modulo. Potrebbe inizializzare campi di ricerca, definire endpoint AJAX per query di ricerca o impostare la gestione dei dati lato client per i risultati della ricerca. Probabilmente è incluso dal template di configurazione principale.
- `delcombs/views/templates/admin/tabs.tpl`
  - **Ambito:** Back-office (pagina di configurazione del modulo).
  - **Scopo:** Questo è il template Smarty principale renderizzato dal metodo `getContent()` del modulo `delcombs`. Struttura l'intero modulo di configurazione, inclusi:
    - I vari campi di input (menu a discesa per gli attributi, aree di testo per i codici, input di quantità).
    - Il pulsante "Elimina combinazioni selezionate".
    - Eventuali messaggi informativi o avvisi.
    - Probabilmente include `scripts.tpl` per la funzionalità di ricerca.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Il modulo non crea tabelle di database personalizzate.
  - Opera direttamente sulle tabelle principali di PrestaShop, principalmente:
    - `ps_product_attribute` (tabella principale delle combinazioni)
    - `ps_product_attribute_combination` (collega le combinazioni ai valori degli attributi)
    - `ps_product_attribute_shop` (dati delle combinazioni specifici del negozio)
    - `ps_stock_available` (scorte per le combinazioni)
    - `ps_specific_price` (prezzi specifici per le combinazioni)
    - `ps_image` (immagini collegate alle combinazioni)
    - `ps_product` (per filtrare per ID prodotto, riferimento, EAN)
    - `ps_attribute_lang`, `ps_attribute_group_lang` (per visualizzare i nomi degli attributi nei menu a discesa)
  - Le impostazioni di configurazione sono memorizzate in `ps_configuration` con chiavi come `delcombs_attribute`, `delcombs_product`, `delcombs_qty_wtd`, `delcombs_qty`, `delcombs_ref_codes`, `delcombs_ref_type`, `delcombs_ean_codes`, `delcombs_ean_type`, `delcombs_ean_field`, `delcombs_product_mode`.
- **Tabella degli hook registrati**:
  Il modulo non registra alcun hook di visualizzazione front-office o back-office. La sua funzionalità è interamente contenuta nella sua pagina di configurazione.
  Potrebbe utilizzare hook di azione internamente (ad esempio, `actionProductUpdate` o `actionAttributeCombinationSave`) per svuotare la cache o reagire alle modifiche, ma questi non sono esplicitamente elencati come hook registrati per l'interazione con moduli esterni.
  La logica principale del modulo è attivata dall'invio del modulo all'interno del suo metodo `getContent()`, non da un hook standard di PrestaShop.

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e per scaricare le ultime versioni del modulo "Elimina combinazioni per attributo", visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e alla compatibilità del modulo.
