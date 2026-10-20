---
title: "Ricerca mirata - Manuale per il commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Ricerca mirata di MyPresta.eu."
sidebar:
  label: "Ricerca mirata - Manuale per il commerciante e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Target search su MyPresta.eu](https://mypresta.eu/modules/front-office-features/target-search.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/target-search/)
>
> ---


# Ricerca mirata

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Non sono richieste configurazioni server insolite.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo "Ricerca mirata" per accedere alle sue impostazioni. Qui è dove definisci esattamente dove il motore di ricerca dovrebbe cercare le parole chiave.

La pagina di configurazione presenterà una serie di caselle di controllo, ognuna corrispondente a un'area specifica dei dati del tuo prodotto.

- **Cosa fa questa impostazione:** Ogni casella di controllo ti consente di abilitare o disabilitare la ricerca all'interno di un particolare campo delle informazioni del tuo prodotto.
- **Effetto della modifica di questa impostazione:**
  - *Se selezionata (abilitata):* Il motore di ricerca di PrestaShop includerà i dati da questo campo specifico durante l'elaborazione delle query dei clienti. Ad esempio, se "Nome prodotto" è selezionato, una ricerca per "vestito" troverà prodotti con "vestito" nel loro nome.
  - *Se deselezionata (disabilitata):* Il motore di ricerca di PrestaShop *ignorerà* i dati da questo campo. Se "Descrizione prodotto" è deselezionata, un prodotto non apparirà nei risultati di ricerca se il termine di ricerca si trova solo all'interno della sua descrizione.
- **Valore consigliato:** Questo dipende interamente dal tuo catalogo prodotti e da come vuoi che i clienti trovino i prodotti. Un buon punto di partenza è abilitare i campi più critici e poi affinare in base ai test.
- **Scenario / esempio del commerciante:**
  - **Scenario 1: Prodotti altamente specifici (es. parti elettroniche, libri per ISBN):** Potresti voler cercare solo in "Nome prodotto", "Riferimento" e "EAN13/JAN". Ciò garantisce che i clienti trovino corrispondenze esatte rapidamente, evitando risultati irrilevanti da lunghe descrizioni.
  - **Scenario 2: Moda o articoli per la casa (es. "vestito rosso"):** Potresti abilitare "Nome prodotto", "Descrizione breve", "Descrizione lunga" e "Tag". Ciò consente ai clienti di trovare prodotti in base a termini più ampi, colori o stili menzionati ovunque nei dettagli del prodotto.
  - **Scenario 3: Prodotti di marca:** Abilita "Nome produttore" in modo che i clienti possano facilmente trovare tutti i prodotti di una marca specifica digitando il nome della marca nella barra di ricerca.

Ecco una ripartizione delle impostazioni tipiche che troverai:

| Impostazione / Opzione | Scopo e impatto | Valore consigliato | Scenario del commerciante |
| --- | --- | --- | --- |
| **Cerca nel nome del prodotto** | Se abilitato, le query di ricerca corrisponderanno al nome del prodotto. | **SÌ** | Essenziale per la maggior parte dei negozi. I clienti spesso cercano per nome del prodotto. |
| **Cerca nella descrizione breve del prodotto** | Se abilitato, le query di ricerca corrisponderanno alla descrizione breve del prodotto. | **SÌ** | Utile per trovare prodotti in base a caratteristiche chiave o riassunti. |
| **Cerca nella descrizione lunga del prodotto** | Se abilitato, le query di ricerca corrisponderanno alla descrizione completa e dettagliata del prodotto. | **SÌ / NO** | **SÌ** per ricerche ampie (moda, articoli per la casa). **NO** per articoli molto specifici (elettronica, parti) per evitare rumore. |
| **Cerca nel riferimento del prodotto** | Se abilitato, le query di ricerca corrisponderanno al numero di riferimento interno del prodotto. | **SÌ / NO** | **SÌ** per B2B, prodotti tecnici, o se i clienti conoscono i numeri di parte. **NO** se i riferimenti sono solo interni. |
| **Cerca in EAN13/JAN del prodotto** | Se abilitato, le query di ricerca corrisponderanno al codice a barre EAN13 o JAN del prodotto. | **SÌ / NO** | **SÌ** per negozi dove i clienti potrebbero cercare per codice a barre (es. libri, generi alimentari). |
| **Cerca in UPC del prodotto** | Se abilitato, le query di ricerca corrisponderanno al codice a barre UPC del prodotto. | **SÌ / NO** | Simile a EAN13/JAN, per le regioni che utilizzano UPC. |
| **Cerca nei tag del prodotto** | Se abilitato, le query di ricerca corrisponderanno a qualsiasi tag assegnato al prodotto. | **SÌ** | Ottimo per migliorare la rilevabilità con parole chiave non presenti nei nomi/descrizioni. |
| **Cerca nel nome del produttore** | Se abilitato, le query di ricerca corrisponderanno al nome del produttore del prodotto. | **SÌ** | Cruciale se i clienti cercano spesso marchi specifici. |
| **Cerca nel nome del fornitore** | Se abilitato, le query di ricerca corrisponderanno al nome del fornitore del prodotto. | **NO / SÌ** | **NO** per la maggior parte dei negozi B2C. **SÌ** per B2B o negozi specializzati dove il fornitore è rilevante per i clienti. |
| **Cerca nel nome della categoria** | Se abilitato, le query di ricerca corrisponderanno al nome delle categorie a cui appartiene il prodotto. | **SÌ** | Aiuta i clienti a trovare prodotti per nome di categoria (es. "vestiti" per trovare prodotti nella categoria "Vestiti"). |
| **Cerca nel valore della caratteristica** | Se abilitato, le query di ricerca corrisponderanno ai valori delle caratteristiche del prodotto (es. "rosso" per una caratteristica "Colore"). | **SÌ** | Altamente raccomandato per negozi con ricche caratteristiche di prodotto (es. colore, taglia, materiale). |

**Nota importante:** Dopo aver apportato modifiche a queste impostazioni, clicca sempre sul pulsante "Salva". È anche una buona pratica svuotare la cache di PrestaShop (Parametri avanzati > Prestazioni) e testare la funzionalità di ricerca sul tuo front office per assicurarti che le modifiche abbiano avuto effetto come previsto.

### 2.2 Schermate di amministrazione dedicate e viste del controller

Questo modulo non introduce nuove schermate di amministrazione dedicate o controller personalizzati. Tutta la configurazione è gestita direttamente all'interno della pagina di configurazione standard del modulo.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | Cerca nel nome del prodotto | SÌ | Includi i nomi dei prodotti nella ricerca. |
| Pagina di configurazione del modulo | Cerca nella descrizione breve del prodotto | SÌ | Includi le descrizioni brevi nella ricerca. |
| Pagina di configurazione del modulo | Cerca nella descrizione lunga del prodotto | SÌ / NO | Includi le descrizioni complete. |
| Pagina di configurazione del modulo | Cerca nel riferimento del prodotto | SÌ / NO | Includi i numeri di riferimento del prodotto. |
| Pagina di configurazione del modulo | Cerca in EAN13/JAN del prodotto | SÌ / NO | Includi i codici a barre EAN13/JAN. |
| Pagina di configurazione del modulo | Cerca in UPC del prodotto | SÌ / NO | Includi i codici a barre UPC. |
| Pagina di configurazione del modulo | Cerca nei tag del prodotto | SÌ | Includi i tag del prodotto. |
| Pagina di configurazione del modulo | Cerca nel nome del produttore | SÌ | Includi i nomi dei produttori. |
| Pagina di configurazione del modulo | Cerca nel nome del fornitore | NO / SÌ | Includi i nomi dei fornitori. |
| Pagina di configurazione del modulo | Cerca nel nome della categoria | SÌ | Includi i nomi delle categorie. |
| Pagina di configurazione del modulo | Cerca nel valore della caratteristica | SÌ | Includi i valori delle caratteristiche del prodotto. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho modificato le impostazioni, ma i risultati di ricerca non sono cambiati. Cosa c'è che non va?**
R: PrestaShop utilizza la cache per velocizzare il tuo negozio. Dopo aver modificato le impostazioni del modulo, spesso è necessario svuotare la cache.

- **Soluzione:** Vai su **Parametri avanzati > Prestazioni** nel tuo Back Office di PrestaShop. Clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti). Quindi, testa nuovamente la tua ricerca.

**D2: La barra di ricerca del mio tema personalizzato ha un aspetto diverso. Questo modulo funzionerà comunque?**
R: Sì, il modulo "Ricerca mirata" principalmente sovrascrive la *logica* di come PrestaShop elabora le query di ricerca, non l'aspetto visivo della barra di ricerca stessa. Dovrebbe funzionare senza problemi con la maggior parte dei temi personalizzati.

- **Soluzione:** Se riscontri problemi visivi imprevisti o la ricerca non sembra funzionare, potrebbe trattarsi di un raro conflitto con il modello di ricerca personalizzato del tuo tema. Contatta il supporto MyPresta.eu con i dettagli del tuo tema.

**D3: Questo modulo influisce sull'ottimizzazione per i motori di ricerca (SEO)?**
R: Direttamente, no. Questo modulo migliora l'esperienza di ricerca *interna* per i tuoi clienti sul tuo sito web. Non influisce direttamente su come i motori di ricerca esterni (come Google) eseguono la scansione o classificano il tuo sito. Tuttavia, migliorando l'esperienza di ricerca sul sito, puoi ridurre la frequenza di rimbalzo e aumentare il tempo trascorso sul sito, che sono segnali positivi per la SEO.

**D4: Posso tradurre le impostazioni o i messaggi del modulo?**
R: Il modulo "Ricerca mirata" funziona principalmente in background e non introduce nuovo testo nel front-office che necessiti di traduzione. Le opzioni di configurazione nel back office sono tipicamente in inglese. Se venisse introdotto nuovo testo, lo tradurresti tramite **Internazionale > Traduzioni** nel tuo Back Office di PrestaShop, selezionando "Traduzioni dei moduli installati" e quindi il modulo "Ricerca mirata".

**D5: E se volessi cercare in un campo non elencato nelle impostazioni del modulo?**
R: Il modulo fornisce opzioni per i campi prodotto più comuni e di maggiore impatto. Se hai un campo personalizzato molto specifico che devi includere nella ricerca, ciò richiederebbe uno sviluppo personalizzato.

- **Soluzione:** Contatta il supporto MyPresta.eu o uno sviluppatore PrestaShop per discutere modifiche personalizzate.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Ricerca mirata" opera principalmente sovrascrivendo la classe core `Search` di PrestaShop. Ciò gli consente di intercettare e modificare la logica di query di ricerca predefinita prima che raggiunga il database. Il modulo sfrutta il sistema di override di PrestaShop per iniettare i suoi parametri di ricerca personalizzati in base alla configurazione del commerciante. È un modulo leggero, che si concentra sulla modifica del comportamento core esistente piuttosto che sull'introduzione di nuove entità o controller complessi.

### 4.2 Controller (`controllers/`)

Questo modulo non introduce alcun controller amministrativo Front-Office o Back-Office personalizzato. La sua funzionalità è integrata sovrascrivendo una classe core e tramite il `getContent()` standard del modulo per la configurazione.

### 4.3 Classi e modelli core (`classes/`)

Il cuore della funzionalità di questo modulo risiede nella sua sovrascrittura della classe `Search`.

- **`targetsearch/override/classes/index.php`**:

  - Questo è un file `index.php` standard vuoto, tipicamente posizionato nelle directory per prevenire l'elenco delle directory per motivi di sicurezza. Non contiene alcun codice funzionale.
- **`targetsearch/override/classes/Search.php`**:

  - **Nome classe**: `Search` (sovrascrive la classe core `classes/Search.php`)
  - **Classe padre**: `SearchCore`
  - **Responsabilità**: Questa classe è responsabile della modifica del metodo `search` della classe core `Search`. Legge le impostazioni di configurazione memorizzate in `ps_configuration` (es. `TARGETSEARCH_PRODUCT_NAME`, `TARGETSEARCH_DESCRIPTION`, ecc.) e regola dinamicamente la query SQL utilizzata per la ricerca dei prodotti.
  - **Metodi pubblici chiave**:
    - `search($id_lang, $expr, $page_number = 1, $page_size = 10, $order_by = 'position', $order_way = 'desc', $ajax = false, $use_cookie = true, Context $context = null)`: Questo metodo viene sovrascritto per iniettare le condizioni di ricerca personalizzate. Costruisce la clausola `WHERE` della query SQL in base agli obiettivi di ricerca abilitati. Controlla `Configuration::get('TARGETSEARCH_...')` per ogni obiettivo (nome prodotto, descrizione, riferimento, EAN13, UPC, tag, produttore, fornitore, categoria, valore caratteristica) e aggiunge le corrispondenti condizioni `LIKE` alla query.
  - **Interazione con il database**: Non interagisce con tabelle di database personalizzate. Modifica la query che interagisce con le tabelle standard di PrestaShop per prodotti, categorie, produttori, fornitori e caratteristiche.
  - **`$definition`**: Non applicabile in quanto sovrascrive una classe core e non definisce un nuovo `ObjectModel`.

### 4.4 Risorse JavaScript (`views/js/`)

- **`targetsearch/targetsearch.js`**:
  - **Ambito**: Back-office (potenzialmente, ma tipicamente non utilizzato per la logica di ricerca front-office).
  - **Scopo**: Questo file è generalmente vuoto o contiene JavaScript minimo, spesso per interazioni UI di base sulla pagina di configurazione del modulo se fosse necessaria una logica client-side avanzata. Data la funzione principale del modulo è la logica di ricerca lato server, è improbabile che questo file contenga JS complesso relativo alla ricerca front-office. Potrebbe essere un segnaposto o per piccoli miglioramenti del modulo nel back-office.
  - **Event Listeners/Manipolazione DOM**: È improbabile che contenga significativi event listener front-office o manipolazione DOM relativi alla ricerca. Il suo ruolo principale sarebbe per la pagina di configurazione del modulo nel back office.

### 4.5 Fogli di stile CSS (`views/css/`)

- **`targetsearch/targetsearch.css`**:

  - **Ambito**: Back-office.
  - **Scopo**: Questo foglio di stile è tipicamente utilizzato per stilizzare la pagina di configurazione del modulo nel Back Office di PrestaShop, garantendo che abbia un aspetto coerente con il tema amministrativo. Potrebbe contenere stili per elementi del modulo, avvisi o aggiustamenti specifici del layout per le impostazioni del modulo.
  - **Selettori di classe CSS chiave**: Probabilmente si rivolge a classi amministrative standard di PrestaShop o ID/classi specifici all'interno dell'output `getContent()` del modulo.
- **`targetsearch/targetsearch15.css`**:

  - **Ambito**: Back-office (specificamente per PrestaShop 1.5.x).
  - **Scopo**: Questo file fornisce aggiustamenti di stile specifici per la pagina di configurazione del modulo quando in esecuzione su PrestaShop 1.5.x, tenendo conto delle differenze nella struttura e nel CSS del tema amministrativo.
  - **Selettori di classe CSS chiave**: Simili a `targetsearch.css` ma adattati per l'ambiente amministrativo di PS 1.5.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **`targetsearch/targetsearch-top.tpl`**:
  - **Ambito**: Front-office.
  - **Hook**: Questo template è probabilmente progettato per essere agganciato a `displayHeader` o `displayTop` (o hook simili che rendono il contenuto nell'area dell'intestazione).
  - **Scopo**: Sebbene la funzione principale del modulo sia la logica di ricerca, questo template potrebbe essere utilizzato per produrre un input nascosto, un piccolo script o un elemento visivo specifico relativo alla presenza del modulo, sebbene non sia strettamente necessario per l'override della ricerca stessa. Data la descrizione del modulo, è più probabile che questo template sia un segnaposto o per un componente visivo molto minore e non critico, poiché l'impatto principale del modulo è sui *risultati* della ricerca, non sull'*input* della ricerca. Potrebbe anche essere un residuo di una versione precedente o un template destinato a una funzionalità futura.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Il modulo non crea tabelle di database personalizzate.
  - Memorizza le sue impostazioni di configurazione nella tabella standard `ps_configuration` di PrestaShop.
    - Chiavi: `TARGETSEARCH_PRODUCT_NAME`, `TARGETSEARCH_DESCRIPTION`, `TARGETSEARCH_SHORT_DESCRIPTION`, `TARGETSEARCH_REFERENCE`, `TARGETSEARCH_EAN13`, `TARGETSEARCH_UPC`, `TARGETSEARCH_TAGS`, `TARGETSEARCH_MANUFACTURER`, `TARGETSEARCH_SUPPLIER`, `TARGETSEARCH_CATEGORY`, `TARGETSEARCH_FEATURE_VALUE`.
    - Valori: `1` (abilitato) o `0` (disabilitato).
- **Tabella degli hook registrati**:
  Il modulo registra hook standard principalmente per la sua installazione e disinstallazione, e potenzialmente per la visualizzazione della sua configurazione. La sua funzionalità principale è tramite override di classe, non direttamente tramite hook.

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `install` | Durante l'installazione del modulo. | Crea voci di configurazione in `ps_configuration` con valori predefiniti. |
| `uninstall` | Durante la disinstallazione del modulo. | Rimuove le voci di configurazione da `ps_configuration`. |
| `displayHeader` (o simile) | Rende il contenuto nella sezione `<head>` o nella parte superiore della pagina. | Potenzialmente utilizzato per includere `targetsearch.js` o `targetsearch.css` se contengono risorse front-office, o per rendere `targetsearch-top.tpl`. |
| `displayBackOfficeHeader` | Rende il contenuto nella sezione `<head>` del Back Office. | Utilizzato per includere `targetsearch.css` (e `targetsearch15.css` condizionalmente) per stilizzare la pagina di configurazione del modulo. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e qualsiasi ulteriore assistenza con il modulo "Ricerca mirata", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per aiutarti con qualsiasi problema o domanda tu possa avere.
"""
