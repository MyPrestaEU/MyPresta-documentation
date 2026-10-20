---
title: "Prodotti Correlati Pro - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Prodotti Correlati Pro di MyPresta.eu."
sidebar:
  label: "Prodotti Correlati Pro - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Related Products Pro su MyPresta.eu](https://mypresta.eu/modules/front-office-features/related-products-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/related-products-pro/)
>
> ---


# Prodotti Correlati Pro

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste e di solito sono abilitate per impostazione predefinita sulla maggior parte degli ambienti di hosting.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Gestione moduli > Prodotti Correlati Pro > Configura)

Questa è la schermata di configurazione principale dove gestirai tutti gli aspetti dei tuoi elenchi di prodotti correlati. L'interfaccia è progettata per essere intuitiva, permettendoti di creare, modificare e assegnare prodotti correlati con facilità.

La pagina di configurazione presenterà tipicamente un elenco dei tuoi blocchi di prodotti correlati esistenti (se presenti) e le opzioni per crearne di nuovi o gestire le impostazioni globali.

#### **Elementi principali dell'interfaccia:**

-   **Elenco dei blocchi di prodotti correlati esistenti:** Questa tabella mostrerà tutti gli elenchi di prodotti correlati che hai creato. Per ogni elenco, vedrai dettagli come il suo nome, i prodotti a cui è assegnato e le opzioni per modificarlo o eliminarlo.
-   **Pulsante "Aggiungi nuovo blocco di prodotti correlati":** Clicca qui per creare un nuovo set di prodotti correlati.
-   **Impostazioni globali / Preferenze:** (Se disponibili) Queste impostazioni potrebbero controllare le opzioni di visualizzazione generali o i comportamenti predefiniti per tutti i blocchi di prodotti correlati.

#### **Quando si aggiunge/modifica un blocco di prodotti correlati:**

Quando clicchi per aggiungere un nuovo blocco o modificarne uno esistente, vedrai tipicamente un modulo con le seguenti impostazioni:

1.  **Nome del blocco:**

    -   **Cosa fa questa impostazione:** Questo è il nome interno per il tuo elenco di prodotti correlati, visibile solo nel Back Office. Ti aiuta a identificare diversi elenchi.
    -   **Effetto della modifica di questa impostazione:** Cambia l'etichetta per questo specifico blocco di prodotti correlati nel tuo pannello di amministrazione.
    -   **Valore consigliato:** Usa un nome descrittivo, ad esempio, "Prodotto X - Articoli Complementari", "Categoria Y - Bestseller".
    -   **Scenario / esempio per il commerciante:** Potresti nominare un elenco "Abiti estivi - Sandali abbinati" per trovarlo facilmente in seguito.
2.  **Posizione di visualizzazione (Hook):**

    -   **Cosa fa questa impostazione:** Determina dove sulla pagina del prodotto apparirà questo specifico blocco di prodotti correlati. Selezioni un "hook" di PrestaShop che è un'area di visualizzazione designata.
    -   **Effetto della modifica di questa impostazione:** I prodotti correlati si sposteranno nella posizione scelta sulla pagina del prodotto del front office.
    -   **Valore consigliato:** Sperimenta con diversi hook in base al tuo tema. Le scelte comuni includono `displayProductExtraContent` (spesso vicino alla descrizione del prodotto), `displayProductFooter` (nella parte inferiore della pagina del prodotto) o `displayRightColumnProduct` (se il tuo tema ha una colonna destra sulle pagine dei prodotti).
    -   **Scenario / esempio per il commerciante:** Se vuoi che i prodotti correlati appaiano appena sotto l'immagine e la descrizione principali del prodotto, potresti scegliere `displayProductExtraContent`. Se li preferisci nella parte inferiore della pagina, `displayProductFooter` sarebbe migliore.
3.  **Prodotti da visualizzare:**

    -   **Cosa fa questa impostazione:** Qui definisci *quali* prodotti verranno mostrati in questo blocco di prodotti correlati. Tipicamente avrai diverse opzioni:
        -   **Prodotti specifici (Selezione manuale):**
            -   **Cosa fa:** Ti consente di cercare e selezionare manualmente singoli prodotti da includere nell'elenco.
            -   **Effetto:** Appariranno solo i prodotti che scegli esplicitamente.
            -   **Consigliato:** Usa per raccomandazioni altamente curate.
            -   **Scenario:** Per una fotocamera specifica, potresti selezionare manualmente un treppiede, una borsa per fotocamera e un obiettivo extra.
        -   **Prodotti da categorie selezionate:**
            -   **Cosa fa:** Visualizza i prodotti da una o più categorie che selezioni.
            -   **Effetto:** L'elenco mostrerà dinamicamente i prodotti di quelle categorie.
            -   **Consigliato:** Ottimo per mostrare articoli correlati all'interno di una linea di prodotti o di un reparto.
            -   **Scenario:** Per una "Camicia da uomo", potresti selezionare le categorie "Pantaloni da uomo" e "Accessori da uomo".
        -   **Nuovi prodotti:**
            -   **Cosa fa:** Visualizza automaticamente i prodotti più recenti aggiunti al tuo negozio.
            -   **Effetto:** L'elenco mostrerà sempre le tue ultime aggiunte.
            -   **Consigliato:** Ottimo per promuovere i nuovi arrivi.
            -   **Scenario:** Usa questo blocco per evidenziare la tua ultima collezione di gioielli.
        -   **Bestseller:**
            -   **Cosa fa:** Visualizza automaticamente i prodotti più venduti del tuo negozio.
            -   **Effetto:** L'elenco si aggiornerà dinamicamente per mostrare i tuoi articoli più popolari.
            -   **Consigliato:** Eccellente per la prova sociale e la promozione di articoli popolari.
            -   **Scenario:** Mostra gli articoli "I clienti hanno anche acquistato" in base alla popolarità complessiva del negozio.
    -   **Numero di prodotti da visualizzare:**
        -   **Cosa fa:** Controlla quanti prodotti correlati vengono mostrati nel blocco.
        -   **Effetto:** Limita i prodotti visibili.
        -   **Consigliato:** 4-8 prodotti per un aspetto pulito, a seconda del tuo layout.
        -   **Scenario:** Visualizza 5 articoli correlati per mantenere la sezione concisa.
4.  **Assegna ai prodotti:**

    -   **Cosa fa questa impostazione:** Questo è cruciale – determina *su quali pagine prodotto* apparirà questo specifico blocco di prodotti correlati.
    -   **Effetto della modifica di questa impostazione:** Il blocco di prodotti correlati sarà visibile solo sulle pagine prodotto che selezioni qui.
    -   **Valore consigliato:** Puoi assegnarlo a:
        -   **Tutti i prodotti:** Se si tratta di un blocco generale "Bestseller" o "Nuovi arrivi".
        -   **Prodotti specifici (Selezione manuale):** Per raccomandazioni altamente mirate.
        -   **Prodotti da categorie selezionate:** Per applicare il blocco a un'intera gamma di categorie.
    -   **Scenario / esempio per il commerciante:** Crei un elenco di "Accessori iPhone". Assegneresti quindi questo blocco solo alle pagine dei tuoi prodotti iPhone. Oppure, crei un blocco "Articoli in saldo estivo" e lo assegni a tutti i prodotti all'interno della tua categoria "Collezione estiva".
5.  **Tipo di visualizzazione / Modello:**

    -   **Cosa fa questa impostazione:** Ti consente di scegliere il layout visivo o il modello per come vengono visualizzati i prodotti correlati (ad esempio, griglia, carosello, elenco, tabella). Il modulo include spesso vari modelli, alcuni dei quali potrebbero essere ottimizzati per temi specifici (come i temi Panda, Warehouse, Zone).
    -   **Effetto della modifica di questa impostazione:** Cambia la presentazione visiva dei prodotti correlati nel front office.
    -   **Valore consigliato:** Sperimenta per trovare la migliore corrispondenza per il tuo tema e l'hook scelto. Un carosello è spesso buono per risparmiare spazio, mentre una griglia potrebbe essere migliore per una sezione dedicata.
    -   **Scenario / esempio per il commerciante:** Se desideri una visualizzazione elegante e salvaspazio, potresti scegliere un modello "carosello". Se hai molto spazio e vuoi mostrare più dettagli, una "griglia" o una "tabella" potrebbero essere migliori. Alcuni modelli potrebbero essere specificamente denominati per temi popolari (ad esempio, `panda-blocksProductsCart.tpl`) per garantire una migliore integrazione.
6.  **Impostazioni carosello (se applicabile):**

    -   **Cosa fa questa impostazione:** Se scegli un tipo di visualizzazione carosello, potresti avere opzioni aggiuntive come:
        -   **Riproduzione automatica:** Se il carosello scorre automaticamente.
        -   **Loop:** Se il carosello si ripete dall'inizio dopo l'ultimo elemento.
        -   **Articoli per visualizzazione:** Quanti prodotti sono visibili contemporaneamente nel carosello.
        -   **Frecce/punti di navigazione:** Se mostrare i controlli per lo scorrimento manuale.
    -   **Effetto della modifica di questa impostazione:** Controlla il comportamento e l'aspetto del carosello di prodotti.
    -   **Valore consigliato:** La riproduzione automatica può essere coinvolgente ma può anche essere distraente. Considera il tuo pubblico. 3-5 articoli per visualizzazione è un buon equilibrio comune.
    -   **Scenario / esempio per il commerciante:** Vuoi un carosello sottile che scorra automaticamente ogni 5 secondi, mostrando 4 prodotti alla volta, con frecce di navigazione per gli utenti che desiderano sfogliare manualmente.

#### **Salvataggio delle modifiche:**

Ricorda sempre di cliccare sul pulsante "Salva" o "Aggiorna" dopo aver apportato modifiche a un blocco di prodotti correlati per assicurarti che le tue impostazioni vengano applicate.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Pagina di configurazione del modulo** | **Nome del blocco** | Descrittivo (es. "Prodotto X - Cross-Sell") | Etichetta interna per identificare il blocco di prodotti correlati nel Back Office. |
| | **Posizione di visualizzazione (Hook)** | `displayProductExtraContent` o `displayProductFooter` | Determina dove appare il blocco nella pagina del prodotto del front-office. |
| | **Prodotti da visualizzare: Prodotti specifici** | Selezione manuale | Mostra solo prodotti selezionati manualmente. Ideale per raccomandazioni altamente curate. |
| | **Prodotti da visualizzare: Da categorie selezionate** | Seleziona categorie pertinenti | Mostra dinamicamente prodotti dalle categorie scelte. Ottimo per linee di prodotti correlate. |
| | **Prodotti da visualizzare: Nuovi prodotti** | Popolato automaticamente | Mostra automaticamente gli ultimi prodotti nel tuo negozio. Ottimo per i nuovi arrivi. |
| | **Prodotti da visualizzare: Bestseller** | Popolato automaticamente | Mostra automaticamente i prodotti più venduti del tuo negozio. Eccellente per la prova sociale. |
| | **Numero di prodotti da visualizzare** | 4-8 | Limita il numero di prodotti mostrati nel blocco per un layout pulito. |
| | **Assegna ai prodotti: Tutti i prodotti** | N/A | Visualizza il blocco su ogni pagina prodotto. Usa per raccomandazioni generali. |
| | **Assegna ai prodotti: Prodotti specifici** | Selezione manuale | Visualizza il blocco solo sulle pagine prodotto selezionate. Per cross-sell mirati. |
| | **Assegna ai prodotti: Da categorie selezionate** | Seleziona categorie pertinenti | Visualizza il blocco sulle pagine prodotto all'interno delle categorie scelte. |
| | **Tipo di visualizzazione / Modello** | `accessories.tpl` o specifico del tema | Controlla il layout visivo (griglia, carosello, elenco). Scegli in base al tema e all'hook. |
| | **Impostazioni carosello (Riproduzione automatica, Loop, Articoli per visualizzazione, Navigazione)** | Varia, spesso abilitato | Controlla il comportamento delle visualizzazioni carosello. Regola per l'esperienza utente. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D1: I miei prodotti correlati non vengono visualizzati nel front office.**

-   **R:** Innanzitutto, assicurati che il modulo sia abilitato e configurato. Controlla di aver effettivamente *assegnato* il blocco di prodotti correlati ai prodotti o alle categorie specifiche che stai visualizzando. Inoltre, verifica che la "Posizione di visualizzazione (Hook)" che hai selezionato sia effettivamente renderizzata dal tuo tema sulla pagina del prodotto. Infine, svuota la cache di PrestaShop (Parametri avanzati > Prestazioni > Svuota cache).

**D2: I prodotti correlati hanno un aspetto strano o non si adattano al design del mio tema.**

-   **R:** Questo è spesso un conflitto di stile con il tuo tema personalizzato.
    -   **Soluzione 1:** Prova diverse opzioni di "Tipo di visualizzazione / Modello" nella configurazione del modulo. Alcuni modelli sono progettati per temi popolari specifici (ad esempio, `panda-blocksProductsCart.tpl`).
    -   **Soluzione 2:** Svuota la cache del tuo browser e la cache Smarty di PrestaShop (Parametri avanzati > Prestazioni).
    -   **Soluzione 3:** Se il problema persiste, potrebbe richiedere aggiustamenti CSS personalizzati. Questo è un compito per un webmaster o uno sviluppatore (vedi Sezione 7.5).

**D3: Posso avere più blocchi di prodotti correlati sulla stessa pagina prodotto?**

-   **R:** Sì! Il modulo è progettato per questo. Puoi creare diversi blocchi di prodotti correlati distinti, ognuno con i propri prodotti, tipo di visualizzazione e posizione assegnata (hook). Assicurati solo di posizionarli in hook diversi per evitare sovrapposizioni.

**D4: Come traduco il testo del modulo (ad esempio, "Prodotti Correlati") in altre lingue?**

-   **R:** Vai su **Internazionale > Traduzioni** nel tuo Back Office di PrestaShop. Seleziona "Traduzioni dei moduli installati", scegli il tuo tema e quindi seleziona "Prodotti Correlati Pro" dal menu a discesa del modulo. Potrai quindi modificare le stringhe di testo per ogni lingua.

**D5: Il carosello non funziona o i prodotti sono impilati verticalmente.**

-   **R:** Questo di solito indica un conflitto JavaScript o una libreria JS mancante.
    -   **Soluzione 1:** Assicurati che il tuo tema sia aggiornato.
    -   **Soluzione 2:** Svuota la cache di PrestaShop e la cache del browser.
    -   **Soluzione 3:** Controlla gli errori della console negli strumenti per sviluppatori del tuo browser (F12). Se vedi errori JavaScript, potrebbe indicare un conflitto con un altro modulo o il tuo tema. Ciò richiederebbe l'intervento di uno sviluppatore.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce un'analisi tecnica approfondita del modulo "Prodotti Correlati Pro" per sviluppatori, webmaster e agenzie tecniche.

### 4.1 Panoramica dell'architettura

Il modulo "Prodotti Correlati Pro" (`ppb`) segue un'architettura standard dei moduli PrestaShop, sfruttando principalmente la classe `Module` per la sua funzionalità principale. Si concentra sull'estensione dell'esperienza della pagina prodotto del front-office iniettando elenchi di prodotti personalizzati in vari hook di visualizzazione. Il modulo gestisce la sua configurazione e i dati dei prodotti correlati direttamente all'interno del metodo `getContent()` del file `index.php`, che gestisce sia il rendering del modulo che la persistenza dei dati. Utilizza un sistema di templating personalizzato per una visualizzazione flessibile del front-office, inclusi modelli specifici per temi popolari. Gli asset JavaScript e CSS vengono caricati condizionalmente per migliorare l'interfaccia utente e fornire la funzionalità del carosello.

### 4.2 Controller (`controllers/`)

Il modulo non sembra utilizzare classi `ModuleFrontController` o `AdminController` dedicate. Tutto il rendering del front-office è gestito tramite hook e la configurazione del back-office è gestita all'interno del metodo `getContent()` del file `index.php` principale.

### 4.3 Classi e modelli principali (`classes/`)

Il modulo non definisce classi personalizzate che estendono `ObjectModel` in una directory `classes/` dedicata. La persistenza dei dati per le configurazioni dei prodotti correlati è probabilmente gestita direttamente tramite `Configuration::updateValue()` o tabelle di database personalizzate gestite all'interno del file `index.php` principale.

### 4.4 Asset JavaScript (`views/js/`)

-   **`ppb/lib/searchTool/views/js/autocomplete.js`**:
    -   **Ambito:** Back-office.
    -   **Responsabilità:** Fornisce la funzionalità di completamento automatico per i campi di selezione del prodotto all'interno dei moduli di configurazione del modulo, probabilmente per la selezione manuale di prodotti specifici da includere o assegnare. Ascolta l'input dell'utente nei campi di testo e suggerisce prodotti in base a corrispondenze parziali.
-   **`ppb/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`**:
    -   **Ambito:** Back-office.
    -   **Responsabilità:** Probabilmente parte di un'utilità generica per la gestione dei modelli Smarty all'interno dell'interfaccia di amministrazione. Potrebbe gestire il caricamento dinamico, il salvataggio o l'anteprima del codice del modello, possibilmente utilizzato per la creazione di modelli personalizzati o funzionalità di modifica all'interno del modulo.
-   **`ppb/lib/src/js/lightslider.js`**:
    -   **Ambito:** Front-office.
    -   **Responsabilità:** Questa è una libreria di terze parti per la creazione di caroselli di contenuti reattivi. Si lega a specifici elementi HTML (probabilmente `<ul>` o `<div>` con una classe designata) per trasformarli in uno slider. Gestisce eventi touch/swipe, navigazione, riproduzione automatica e regolazioni reattive.
-   **`ppb/views/admin/ppb.js`**:
    -   **Ambito:** Back-office.
    -   **Responsabilità:** Contiene la logica JavaScript principale per la pagina di configurazione del Back Office del modulo. Ciò includerebbe listener di eventi per l'invio di moduli, aggiornamenti dinamici delle impostazioni in base alle scelte dell'utente (ad esempio, mostrare/nascondere le opzioni del carosello), chiamate AJAX per il salvataggio dei dati e potenzialmente la gestione dell'elenco dei blocchi di prodotti correlati.
-   **`ppb/views/admin/ppb8.js`**:
    -   **Ambito:** Back-office.
    -   **Responsabilità:** Simile a `ppb.js`, ma probabilmente contiene adattamenti specifici o funzionalità aggiuntive per gli ambienti PrestaShop 8.x, affrontando modifiche API o differenze UI nelle versioni più recenti di PrestaShop.
-   **`ppb/views/js/accessories.js`**:
    -   **Ambito:** Front-office.
    -   **Responsabilità:** Contiene JavaScript specifico del front-office per i blocchi di prodotti correlati. Ciò potrebbe includere la logica di inizializzazione per il carosello `lightslider.js`, la gestione dei clic sui prodotti o qualsiasi interazione dinamica all'interno degli elenchi di prodotti correlati visualizzati.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`ppb/css.css`**:
    -   **Ambito:** Sia Front-office che Back-office.
    -   **Responsabilità:** Stile generale a livello di modulo. Potrebbe contenere stili di base per i blocchi di prodotti correlati o elementi comuni utilizzati in tutto il modulo.
-   **`ppb/lib/searchTool/views/css/autocomplete.css`**:
    -   **Ambito:** Back-office.
    -   **Responsabilità:** Stili per i menu a discesa di completamento automatico e i campi di input utilizzati nello strumento di selezione del prodotto dell'amministratore.
-   **`ppb/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`**:
    -   **Ambito:** Back-office.
    -   **Responsabilità:** Stile per l'interfaccia di gestione dei modelli Smarty all'interno della configurazione del modulo.
-   **`ppb/lib/src/css/lightslider.css`**:
    -   **Ambito:** Front-office.
    -   **Responsabilità:** Stile principale per il carosello `lightslider.js`, che definisce la sua struttura, le frecce di navigazione, i punti e il comportamento reattivo. Gli sviluppatori possono sovrascrivere questi stili per adattarli al loro tema.
-   **`ppb/views/admin/ppb.css`**:
    -   **Ambito:** Back-office.
    -   **Responsabilità:** Stile specifico per la pagina di configurazione del modulo nel pannello di amministrazione di PrestaShop, garantendo una buona integrazione con l'interfaccia utente del back-office di PrestaShop.
-   **`ppb/views/css/ppb-table.css`**:
    -   **Ambito:** Front-office.
    -   **Responsabilità:** Stile per gli elenchi di prodotti correlati visualizzati in formato tabella, probabilmente utilizzato per modelli specifici di "elenco-tabella".
-   **`ppb/views/css/ppb.css`**:
    -   **Ambito:** Front-office.
    -   **Responsabilità:** Stile principale del front-office per i blocchi di prodotti correlati, inclusi i layout delle schede prodotto, la spaziatura e l'aspetto generale.
-   **`ppb/views/css/ppbcarousell.css`**:
    -   **Ambito:** Front-office.
    -   **Responsabilità:** Stile aggiuntivo o specifico per la visualizzazione a carosello dei prodotti correlati, potenzialmente sovrascrivendo o estendendo `lightslider.css` per un'estetica personalizzata del modulo.
-   **`ppb/views/css/ppb_custom.css`**:
    -   **Ambito:** Front-office.
    -   **Responsabilità:** Probabilmente destinato a CSS personalizzati definiti dall'utente o a sovrascritture specifiche del tema per regolare l'aspetto dei blocchi di prodotti correlati senza modificare i file principali del modulo.

### 4.6 Struttura del modello Smarty (`views/templates/`)

Il modulo fornisce un ricco set di modelli, molti dei quali sono personalizzati per hook specifici e temi PrestaShop popolari.

-   **`ppb/lib/searchTool/views/scripts.tpl`**:

    -   **Ambito:** Back-office.
    -   **Scopo:** Contiene l'inizializzazione o la configurazione JavaScript per lo strumento di ricerca con completamento automatico utilizzato nell'amministrazione.
-   **`ppb/lib/smartyTemplatesManager/tpl/example.tpl`**:

    -   **Ambito:** Back-office.
    -   **Scopo:** Un modello di esempio, probabilmente utilizzato come riferimento o per dimostrare le capacità del gestore di modelli Smarty.
-   **`ppb/lib/smartyTemplatesManager/views/buttonManager.tpl`**:

    -   **Ambito:** Back-office.
    -   **Scopo:** Renderizza pulsanti o controlli per la gestione dei modelli all'interno dell'interfaccia di amministrazione.
-   **`ppb/lib/smartyTemplatesManager/views/createTemplateForm.tpl`**:

    -   **Ambito:** Back-office.
    -   **Scopo:** Renderizza il modulo per la creazione di nuovi modelli di visualizzazione personalizzati per i prodotti correlati.
-   **`ppb/lib/smartyTemplatesManager/views/editTemplateForm.tpl`**:

    -   **Ambito:** Back-office.
    -   **Scopo:** Renderizza il modulo per la modifica di modelli di visualizzazione personalizzati esistenti.
-   **`ppb/lib/smartyTemplatesManager/views/mainForm.tpl`**:

    -   **Ambito:** Back-office.
    -   **Scopo:** Il modulo principale per il gestore di modelli Smarty, probabilmente elenca i modelli e fornisce opzioni.
-   **`ppb/lib/smartyTemplatesManager/views/selectInput.tpl`**:

    -   **Ambito:** Back-office.
    -   **Scopo:** Renderizza un input a discesa di selezione, possibilmente utilizzato per scegliere modelli o altre opzioni.
-   **`ppb/views/templates/admin/tabs.tpl`**:

    -   **Ambito:** Back-office.
    -   **Scopo:** Renderizza la struttura di navigazione a schede per la pagina di configurazione del modulo, se utilizza più schede per diverse impostazioni.
-   **Modelli di hook (`views/templates/hook/`)**: Questi modelli vengono renderizzati nella pagina del prodotto del front-office tramite vari hook di PrestaShop. Molti sono specifici del tema per garantire un'integrazione ottimale.

    -   **`accessories.tpl`**:
        -   **Hook:** Configurabile, spesso `displayProductExtraContent` o `displayProductFooter`.
        -   **Output:** Un modello generico per la visualizzazione di prodotti correlati, tipicamente in una griglia o un carosello.
    -   **`blocksProductsCart.tpl`**:
        -   **Hook:** Configurabile, spesso `displayProductExtraContent` o `displayProductFooter`.
        -   **Output:** Un blocco di prodotti, potenzialmente stilizzato per un aspetto simile al carrello o per raccomandazioni generali di prodotti.
    -   **`blocksProductsOrder.tpl`**:
        -   **Hook:** Configurabile.
        -   **Output:** Simile a `blocksProductsCart.tpl`, ma potrebbe essere stilizzato per un contesto o un layout diverso.
    -   **`custom-pictures-only.tpl`**:
        -   **Hook:** Configurabile.
        -   **Output:** Una visualizzazione minimalista che mostra solo le immagini dei prodotti, ideale per spazi compatti o navigazione visiva.
    -   **`panda-blocksProductsCart.tpl`**, **`panda-blocksProductsOrder.tpl`**, **`panda-ProductExtraContent.tpl`**, **`panda-productFooter.tpl`**, **`panda-productTab.tpl`**, **`panda-productTabContent.tpl`**:
        -   **Hook:** Configurabile, progettato per il tema Panda.
        -   **Output:** Modelli specifici del tema che garantiscono un'integrazione e uno stile senza soluzione di continuità con il linguaggio di design del tema Panda. Renderizzeranno i prodotti correlati all'interno delle aree specificate del tema Panda (ad esempio, contenuto extra del prodotto, piè di pagina o schede dedicate).
    -   **`ProductExtraContent.tpl`**:
        -   **Hook:** `displayProductExtraContent`.
        -   **Output:** Renderizza i prodotti correlati all'interno dell'hook `displayProductExtraContent`, tipicamente un'area prominente vicino ai dettagli principali del prodotto.
    -   **`productFooter.tpl`**:
        -   **Hook:** `displayProductFooter`.
        -   **Output:** Renderizza i prodotti correlati nella parte inferiore della pagina del prodotto.
    -   **`productTab.tpl`**:
        -   **Hook:** Configurabile, spesso `displayProductButtons` o `displayProductExtraContent` (per aggiungere una nuova scheda).
        -   **Output:** Renderizza l'*intestazione della scheda* per una scheda "Prodotti Correlati" dedicata sulla pagina del prodotto.
    -   **`productTabContent.tpl`**:
        -   **Hook:** Configurabile, spesso `displayProductContent` o `displayProductExtraContent` (per aggiungere contenuto per una nuova scheda).
        -   **Output:** Renderizza il *contenuto* per una scheda "Prodotti Correlati" dedicata, che appare quando si clicca sull'intestazione `productTab.tpl`.
    -   **`table-list.tpl`**:
        -   **Hook:** Configurabile.
        -   **Output:** Visualizza i prodotti correlati in formato tabellare, potenzialmente utile per confrontare le caratteristiche o per un elenco più strutturato.
    -   **`warehouse-blocksProductsCart.tpl`**, **`warehouse-blocksProductsOrder.tpl`**, ecc. (tutti i modelli con prefisso `warehouse-`):
        -   **Hook:** Configurabile, progettato per il tema Warehouse.
        -   **Output:** Modelli specifici del tema Warehouse, che garantiscono una corretta integrazione di stile e layout.
    -   **`zone-blocksProductsCart.tpl`**, **`zone-blocksProductsOrder.tpl`**, ecc. (tutti i modelli con prefisso `zone-`):
        -   **Hook:** Configurabile, progettato per il tema Zone.
        -   **Output:** Modelli specifici del tema Zone, che garantiscono una corretta integrazione di stile e layout.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**: Il modulo probabilmente memorizza i suoi dati di configurazione (definizioni dei blocchi di prodotti correlati, prodotti assegnati, impostazioni di visualizzazione) in tabelle di database personalizzate create durante l'installazione, oppure potrebbe fare molto affidamento su `ps_configuration` per impostazioni più semplici. Data la complessità di più elenchi di prodotti correlati, le tabelle personalizzate sono più probabili. Gli sviluppatori dovrebbero ispezionare il metodo `install()` in `ppb/index.php` per le chiamate `Db::getInstance()->execute()` per identificare la creazione delle tabelle.

    -   **Tabelle probabili (ipotetiche basate sulla funzionalità):**
        -   `ps_ppb_blocks`: Memorizza la definizione principale di ogni blocco di prodotti correlati (ID, nome, hook, tipo di visualizzazione, ecc.).
        -   `ps_ppb_block_products`: Una tabella molti-a-molti che collega i blocchi di prodotti correlati ai prodotti che dovrebbero visualizzare.
        -   `ps_ppb_block_assignments`: Una tabella molti-a-molti che collega i blocchi di prodotti correlati alle pagine prodotto su cui dovrebbero apparire.
        -   `ps_ppb_block_categories`: Una tabella per memorizzare le assegnazioni di categoria per la selezione o l'assegnazione dinamica dei prodotti.
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Utilizzato per caricare asset CSS e JavaScript (ad esempio, `lightslider.js`, `ppb.css`) condizionalmente solo sulle pagine prodotto o globalmente. |
| `displayRightColumnProduct` | Nella colonna destra della pagina del prodotto. | Renderizza i blocchi di prodotti correlati nella barra laterale destra. |
| `displayLeftColumnProduct` | Nella colonna sinistra della pagina del prodotto. | Renderizza i blocchi di prodotti correlati nella barra laterale sinistra. |
| `displayProductExtraContent` | Un hook flessibile spesso trovato vicino alla descrizione/immagine del prodotto. | Un hook comune e altamente raccomandato per iniettare blocchi di prodotti correlati direttamente nell'area del contenuto principale. |
| `displayProductFooter` | Nella parte inferiore della pagina del prodotto, prima del piè di pagina generale. | Renderizza i blocchi di prodotti correlati in una sezione dedicata alla fine del contenuto della pagina del prodotto. |
| `displayProductButtons` | Vicino al pulsante "Aggiungi al carrello" o alle azioni del prodotto. | Potrebbe essere utilizzato per aggiungere un'intestazione di scheda "Prodotti correlati". |
| `displayProductContent` | All'interno dell'area del contenuto principale del prodotto. | Potrebbe essere utilizzato per renderizzare il contenuto di una scheda "Prodotti correlati". |
| `displayFooter` | Nel piè di pagina globale del negozio. | Meno comune per i prodotti correlati, ma possibile per raccomandazioni molto ampie. |
| `actionProductUpdate` | Dopo l'aggiornamento di un prodotto nel Back Office. | Potenzialmente utilizzato per svuotare la cache o re-indicizzare i dati dei prodotti correlati se vengono utilizzati elenchi dinamici. |
| `actionProductDelete` | Dopo l'eliminazione di un prodotto. | Per ripulire eventuali assegnazioni di prodotti correlati che coinvolgono il prodotto eliminato. |
| `actionCategoryUpdate` | Dopo l'aggiornamento di una categoria. | Per rivalutare gli elenchi di prodotti correlati che dipendono dalle selezioni di categoria. |
| `actionCategoryDelete` | Dopo l'eliminazione di una categoria. | Per ripulire le assegnazioni di prodotti correlati che coinvolgono la categoria eliminata. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, accedi al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda relativa al modulo "Prodotti Correlati Pro".
