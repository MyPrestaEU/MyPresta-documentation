---
title: "Ricerca prodotti ajax nel Back office - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Ricerca prodotti ajax nel Back office' di MyPresta.eu."
sidebar:
  label: "Ricerca prodotti ajax nel Back office - Manuale del commerciante e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Back office ajax product search su MyPresta.eu](https://mypresta.eu/modules/administration-tools/back-office-ajax-product-search.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/back-office-ajax-product-search/)
>
> ---


# Ricerca prodotti ajax nel Back office

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e sono solitamente disponibili in qualsiasi ambiente di hosting moderno.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questo modulo è progettato per essere altamente efficiente e in gran parte "impostalo e dimenticalo". Si integra perfettamente nel tuo back office senza richiedere configurazioni complesse.

Quando clicchi su "Configura" dopo l'installazione, troverai tipicamente un'interfaccia semplice, spesso senza impostazioni specifiche da regolare. La funzionalità principale del modulo (ricerca prodotti AJAX con autocomplete) è abilitata per impostazione predefinita all'installazione.

- **Cosa fa questa schermata:** Questa è l'area di configurazione principale per il modulo. Tuttavia, per "Ricerca prodotti ajax nel Back office", la sua funzione principale è confermare che il modulo è installato e attivo.
- **Effetto della modifica delle impostazioni:** Poiché non ci sono impostazioni specifiche configurabili dall'utente esposte in questa schermata, il modulo opererà con il suo comportamento predefinito e ottimizzato.
- **Valore consigliato:** Di solito non sono richieste azioni specifiche qui. Il modulo è progettato per funzionare immediatamente.
- **Scenario / esempio del commerciante:** Dopo l'installazione, naviga semplicemente a qualsiasi pagina del back office. Dovresti notare che quando inizi a digitare in un campo di ricerca prodotti, i suggerimenti appaiono istantaneamente e cliccandoci sopra ti portano direttamente alla pagina di modifica del prodotto.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | (Nessuna impostazione specifica) | N/A | Il modulo migliora automaticamente la ricerca prodotti del back office con la funzionalità di autocomplete AJAX all'installazione. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho installato il modulo, ma la barra di ricerca non sembra funzionare in modo diverso.**
R:

1. **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" nell'angolo in alto a destra. A volte, la cache di PrestaShop deve essere svuotata affinché le nuove risorse del modulo (come JavaScript e CSS) vengano caricate correttamente.
2. **Cache del browser:** Prova a svuotare la cache del tuo browser o a testare in una finestra di navigazione in incognito/privata.
3. **Stato del modulo:** Assicurati che il modulo sia abilitato in **Moduli > Gestione moduli**.
4. **Compatibilità del tema:** Sebbene raro per i moduli del back office, un tema di amministrazione pesantemente personalizzato potrebbe interferire. Se il problema persiste, contatta il supporto MyPresta.eu.

**D: Questo modulo rallenterà il mio back office?**
R: No, anzi. Utilizzando AJAX, il modulo esegue le ricerche in background senza ricaricamenti completi della pagina, il che è intrinsecamente più veloce ed efficiente rispetto ai metodi di ricerca tradizionali. È progettato per migliorare le prestazioni, non ostacolarle.

**D: Questo modulo influisce sulla ricerca nel front-office per i clienti?**
R: No, questo modulo è strettamente per il back office di PrestaShop. Non ha alcun impatto sul tuo negozio rivolto ai clienti o sulla sua funzionalità di ricerca.

**D: Posso configurare il numero di risultati di ricerca mostrati?**
R: Questo modulo è progettato per la semplicità e la funzionalità out-of-the-box. Tipicamente non offre opzioni configurabili per il numero di risultati. Il comportamento predefinito è solitamente ottimizzato per una buona esperienza utente.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo `Ricerca prodotti ajax nel Back office` (boproductfinder) è un modulo PrestaShop leggero focalizzato principalmente sul miglioramento dell'esperienza utente all'interno del back office. Realizza la sua funzionalità iniettando asset JavaScript e CSS personalizzati nell'intestazione del back office, sfruttando il sistema di hook di PrestaShop. La logica principale risiede nel JavaScript lato client, che intercetta l'input dell'utente in specifici campi di ricerca ed esegue richieste AJAX agli endpoint di ricerca prodotti integrati di PrestaShop, quindi visualizza i risultati utilizzando un'interfaccia utente di autocomplete. Non introduce nuove tabelle di database o logica complessa lato server oltre a quanto PrestaShop già fornisce per la ricerca prodotti.

### 4.2 Controller (`controllers/`)

Questo modulo non introduce alcun controller front-office o back-office personalizzato. Si basa sui controller PrestaShop esistenti per la gestione delle query di ricerca prodotti (ad esempio, i metodi AJAX di `AdminProductsController`).

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non introduce alcuna classe PHP personalizzata o definizioni di `ObjectModel`. La sua funzionalità è principalmente lato client.

### 4.4 Asset JavaScript (`views/js/`)

- **`boproductfinder/views/autocomplete.js`**
  - **Ambito**: Back-office.
  - **Descrizione**: Questo script probabilmente implementa o integra una libreria di autocomplete generica. Fornisce la funzionalità principale per visualizzare i suggerimenti mentre l'utente digita in un campo di input di testo. Gestisce il rendering dell'interfaccia utente dell'elenco di suggerimenti, la navigazione da tastiera all'interno dell'elenco e la selezione degli elementi. È un componente fondamentale per la ricerca interattiva del modulo.
- **`boproductfinder/views/boproductfinder.js`**
  - **Ambito**: Back-office.
  - **Descrizione**: Questo è lo script principale per il modulo.
  - **Listener di eventi**: Probabilmente si lega agli eventi `keyup` o `input` su specifici campi di input di ricerca prodotti all'interno del back office di PrestaShop (ad esempio, `input[name="product_search"]` o selettori simili).
  - **Chiamate AJAX**: Quando un utente digita, questo script attiva richieste AJAX all'API interna di ricerca prodotti di PrestaShop (ad esempio, `admin-ajax.php` o un'azione AJAX di un controller admin specifico per la ricerca prodotti). Invia la query di ricerca ed eventualmente altri parametri (ad esempio, `id_lang`).
  - **Manipolazione del DOM**: Riceve la risposta JSON dal server (contenente ID prodotto, nomi ed eventualmente link) e utilizza `autocomplete.js` (o logica simile) per visualizzare questi risultati in un elenco a discesa sotto il campo di ricerca.
  - **Navigazione**: Quando un suggerimento di prodotto viene cliccato o selezionato, questo script costruisce l'URL alla pagina di modifica del prodotto (ad esempio, `admin/index.php?controller=AdminProducts&id_product=X&updateproduct&token=Y`) e reindirizza il browser a quella pagina.

### 4.5 Fogli di stile CSS (`views/css/`)

- **`boproductfinder/views/autocomplete.css`**
  - **Ambito**: Stile del modulo di amministrazione del back office.
  - **Descrizione**: Questo foglio di stile fornisce lo stile visivo per l'elenco di suggerimenti di autocomplete.
  - **Componenti e contenitori principali dell'interfaccia utente che stilizza**:
    - Il contenitore a discesa per i risultati della ricerca.
    - Singoli elementi dell'elenco all'interno dei suggerimenti.
    - Evidenziazione per il suggerimento attualmente selezionato o su cui si passa il mouse.
    - Potenzialmente indicatori di caricamento o messaggi di "nessun risultato".
  - **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere**: Gli sviluppatori possono ispezionare l'HTML generato per classi come `.autocomplete-suggestions`, `.autocomplete-suggestion`, `.autocomplete-selected` per personalizzare l'aspetto nel loro tema di amministrazione.

### 4.6 Struttura del template Smarty (`views/templates/`)

Questo modulo non contiene alcun file di template Smarty personalizzato (`.tpl`). La sua funzionalità viene iniettata direttamente tramite asset JavaScript e CSS caricati tramite hook.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**: Questo modulo non crea alcuna tabella di database personalizzata. Si basa sulle tabelle esistenti di PrestaShop `ps_product`, `ps_product_lang` e tabelle correlate per i dati dei prodotti. La configurazione è memorizzata in `ps_configuration` se fossero presenti impostazioni, ma per questo modulo è tipicamente minima o inesistente.
- **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayBackOfficeHeader` | Eseguito nella sezione `<head>` di ogni pagina del back office. | Utilizzato per includere i file CSS e JavaScript del modulo (`autocomplete.css`, `autocomplete.js`, `boproductfinder.js`) per assicurarsi che siano caricati su tutte le pagine di amministrazione dove la funzionalità di ricerca potrebbe essere necessaria. |
| `actionAdminControllerSetMedia` | Eseguito quando un Controller Admin sta impostando i suoi asset multimediali. | Un hook alternativo o complementare a `displayBackOfficeHeader` per aggiungere file CSS e JS, garantendo la compatibilità tra diverse versioni di PrestaShop e temi del back office. Assicura che gli asset del modulo siano correttamente registrati e caricati. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Ricerca prodotti ajax nel Back office", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità o compatibilità del modulo.
"""
