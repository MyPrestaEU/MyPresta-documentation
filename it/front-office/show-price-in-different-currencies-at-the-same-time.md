---
title: "Mostra il prezzo in diverse valute contemporaneamente - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Mostra il prezzo in diverse valute contemporaneamente' di MyPresta.eu."
sidebar:
  label: "Mostra il prezzo in diverse valute contemporaneamente - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Show price in different currencies at the same time su MyPresta.eu](https://mypresta.eu/modules/front-office-features/show-price-in-different-currencies-at-the-same-time.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/show-price-in-different-currencies-at-the-same-time/)
>
> ---


# Mostra il prezzo in diverse valute contemporaneamente

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per un'installazione PrestaShop e sono sufficienti per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo "Mostra il prezzo in diverse valute contemporaneamente". Puoi accedervi navigando su **Moduli > Gestione moduli** e facendo clic su "Configura" accanto al nome del modulo.

La pagina di configurazione presenterà una serie di opzioni per controllare come e dove vengono visualizzati i prezzi in più valute.

#### Impostazioni generali

-   **Abilita visualizzazione prezzo in più valute:**

    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare la funzionalità principale del modulo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il modulo inizierà a visualizzare i prezzi in più valute in base alle altre impostazioni.
        -   *Quando disabilitato:* Il modulo cesserà di funzionare e verrà mostrato solo il prezzo nella valuta principale.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio del commerciante:** Se stai configurando il modulo per la prima volta o eseguendo la manutenzione, potresti disabilitarlo temporaneamente. Per il normale funzionamento, dovrebbe essere sempre abilitato.
-   **Seleziona valute da visualizzare:**

    -   **Cosa fa questa impostazione:** Ti consente di scegliere quali valute aggiuntive, oltre a quella principale, desideri mostrare i prezzi. In genere vedrai un elenco di tutte le valute attive nel tuo negozio PrestaShop.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando selezionato:* I prezzi verranno visualizzati nelle valute scelte.
        -   *Quando non selezionato:* I prezzi non verranno mostrati in quella specifica valuta.
    -   **Valore consigliato:** Seleziona tutte le valute pertinenti ai tuoi mercati internazionali di riferimento.
    -   **Scenario / esempio del commerciante:** Se vendi a clienti nella zona euro, negli Stati Uniti e nel Regno Unito, selezioneresti EUR, USD e GBP.
-   **Visualizza nelle pagine di elenco prodotti (categorie, risultati di ricerca, ecc.):**

    -   **Cosa fa questa impostazione:** Controlla se i prezzi in più valute appaiono nelle pagine che elencano più prodotti (ad esempio, pagine di categoria, risultati di ricerca, pagine del produttore).
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I prezzi in più valute saranno visibili sotto il prezzo principale sulle schede prodotto.
        -   *Quando disabilitato:* I prezzi in più valute appariranno solo nella pagina dei dettagli del singolo prodotto.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio del commerciante:** L'abilitazione di questa opzione fornisce una chiarezza immediata dei prezzi mentre i clienti navigano, aiutandoli a confrontare rapidamente i prodotti nella loro valuta preferita.
-   **Visualizza nella pagina dei dettagli del prodotto:**

    -   **Cosa fa questa impostazione:** Controlla se i prezzi in più valute appaiono nella pagina del singolo prodotto.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I prezzi in più valute saranno visibili vicino al prezzo principale nella pagina del prodotto.
        -   *Quando disabilitato:* I prezzi in più valute non verranno mostrati nella pagina del prodotto.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio del commerciante:** Questo è cruciale per i clienti che prendono una decisione finale, specialmente quando considerano combinazioni di prodotti o sconti quantità, poiché il modulo garantisce che anche questi prezzi dinamici vengano convertiti.
-   **Formato di visualizzazione del prezzo:**

    -   **Cosa fa questa impostazione:** Definisce come vengono formattati i prezzi in valuta aggiuntiva (ad esempio, con o senza simbolo di valuta, numero di cifre decimali). Questo di solito sfrutta la formattazione nativa della valuta di PrestaShop.
    -   **Effetto della modifica di questa impostazione:** Modifica la presentazione visiva dei prezzi convertiti.
    -   **Valore consigliato:** Utilizza un formato chiaro e coerente con gli standard internazionali per ogni valuta (ad esempio, "$100.00 USD" o "€100,00").
    -   **Scenario / esempio del commerciante:** Potresti scegliere di visualizzare "USD 100.00" invece di "$100.00" per evitare confusione con altre valute denominate in dollari.
-   **Posizione dei prezzi aggiuntivi:**

    -   **Cosa fa questa impostazione:** Determina dove vengono posizionati i prezzi in valuta aggiuntiva rispetto al prezzo principale del prodotto. Le opzioni potrebbero includere "Sotto il prezzo principale", "Accanto al prezzo principale" o "In un blocco separato".
    -   **Effetto della modifica di questa impostazione:** Altera il layout visivo dei prezzi sulle pagine dei tuoi prodotti.
    -   **Valore consigliato:** "Sotto il prezzo principale" è spesso il più chiaro e meno invasivo.
    -   **Scenario / esempio del commerciante:** Se il layout della pagina del tuo prodotto è molto compatto, posizionare i prezzi sotto potrebbe essere meglio che accanto, per evitare l'affollamento.
-   **Aggiorna prezzi con combinazioni/sconti quantità:**

    -   **Cosa fa questa impostazione:** Garantisce che quando un cliente seleziona una combinazione di prodotto diversa (ad esempio, una taglia più grande con un prezzo diverso) o modifica la quantità (attivando uno sconto quantità), i prezzi in più valute visualizzati vengano aggiornati dinamicamente per riflettere il nuovo totale.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il modulo utilizzerà JavaScript per ricalcolare e visualizzare i prezzi convertiti corretti in tempo reale.
        -   *Quando disabilitato:* I prezzi aggiuntivi potrebbero non aggiornarsi, portando a informazioni errate per il cliente.
    -   **Valore consigliato:** SÌ (Cruciale per l'accuratezza e la fiducia del cliente).
    -   **Scenario / esempio del commerciante:** Un cliente seleziona una t-shirt "Large" (che costa di più) o aggiunge 10 articoli (attivando uno sconto all'ingrosso). Questa impostazione garantisce che vedano il prezzo convertito corretto per la t-shirt grande o il prezzo scontato all'ingrosso nelle valute scelte.

#### Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Abilita visualizzazione prezzo in più valute | SÌ | Attiva/disattiva la funzionalità principale del modulo. |
| Configurazione modulo | Seleziona valute da visualizzare | Seleziona valute pertinenti | Determina quali valute aggiuntive vengono mostrate. |
| Configurazione modulo | Visualizza nelle pagine di elenco prodotti | SÌ | Mostra i prezzi in più valute nelle pagine di categoria, ricerca, ecc. |
| Configurazione modulo | Visualizza nella pagina dei dettagli del prodotto | SÌ | Mostra i prezzi in più valute nelle singole pagine dei prodotti. |
| Configurazione modulo | Formato di visualizzazione del prezzo | Varia (usa i valori predefiniti di PrestaShop) | Controlla la formattazione visiva dei prezzi convertiti. |
| Configurazione modulo | Posizione dei prezzi aggiuntivi | Sotto il prezzo principale | Imposta il layout dei prezzi aggiuntivi rispetto al prezzo principale. |
| Configurazione modulo | Aggiorna prezzi con combinazioni/sconti quantità | SÌ | Garantisce aggiornamenti dinamici dei prezzi per combinazioni e sconti. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I prezzi in più valute non vengono visualizzati nel mio negozio.**
**R1:**

-   **Controlla lo stato del modulo:** Innanzitutto, assicurati che l'opzione "Abilita visualizzazione prezzo in più valute" sia impostata su SÌ nella configurazione del modulo.
-   **Valute selezionate:** Verifica di aver selezionato le valute specifiche che desideri visualizzare nelle impostazioni del modulo.
-   **Cache:** Svuota la cache di PrestaShop (Parametri avanzati > Prestazioni > Svuota cache) e la cache del tuo browser. A volte, i vecchi contenuti memorizzati nella cache impediscono la visualizzazione di nuovi moduli.
-   **Compatibilità del tema:** Se stai utilizzando un tema altamente personalizzato, potrebbe esserci un conflitto. Contatta il supporto MyPresta.eu con i dettagli del tuo tema.

**D2: I prezzi in altre valute non sono corretti o non si aggiornano.**
**R2:**

-   **Tassi di cambio:** Assicurati che i tassi di cambio di PrestaShop siano aggiornati. Vai su **Internazionale > Valute** nel tuo Back Office e controlla i tassi di cambio per ogni valuta. Di solito puoi aggiornarli automaticamente o manualmente.
-   **Impostazione di aggiornamento dinamico:** Assicurati che "Aggiorna prezzi con combinazioni/sconti quantità" sia abilitato nella configurazione del modulo se ti aspetti che i prezzi cambino con le opzioni del prodotto.
-   **Cache:** Svuota tutte le cache (PrestaShop e browser) dopo aver aggiornato i tassi di cambio.

**D3: I prezzi in più valute sembrano strani o non sono stilizzati correttamente nel mio tema.**
**R3:**

-   **Configurazione del modulo:** Controlla le impostazioni "Formato di visualizzazione del prezzo" e "Posizione dei prezzi aggiuntivi" nel modulo.
-   **CSS del tema:** Il CSS del tuo tema personalizzato potrebbe sovrascrivere lo stile predefinito del modulo. Questo di solito richiede a un webmaster o a uno sviluppatore di ispezionare il CSS. Spesso puoi aggiungere CSS personalizzato al tuo tema per regolare l'aspetto.
-   **Contatta il supporto:** Se non riesci a risolvere i problemi di stile, fornisci screenshot e l'URL del tuo negozio al supporto MyPresta.eu per assistenza.

**D4: Questo modulo rallenterà il mio negozio?**
**R4:** Il modulo è progettato per essere leggero. Recupera principalmente i tassi di cambio esistenti ed esegue semplici calcoli. Gli aggiornamenti dinamici per le combinazioni utilizzano JavaScript, che viene eseguito lato client. Nella maggior parte dei casi, qualsiasi impatto sulle prestazioni dovrebbe essere trascurabile. Assicurati che il tuo server soddisfi i requisiti minimi di PrestaShop per prestazioni ottimali.

**D5: Come traduco il testo del modulo (ad esempio, "Prezzo in USD")?**
**R5:** Puoi tradurre qualsiasi stringa di testo aggiunta dal modulo tramite l'interfaccia di traduzione di PrestaShop:

-   Naviga su **Internazionale > Traduzioni**.
-   Seleziona "Traduzioni dei moduli installati".
-   Scegli il tuo tema, la tua lingua e quindi seleziona il modulo "Mostra il prezzo in diverse valute contemporaneamente".
-   Potrai quindi modificare le traduzioni per qualsiasi frase introdotta dal modulo.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce un'analisi approfondita dell'architettura tecnica del modulo "Mostra il prezzo in diverse valute contemporaneamente", destinata a sviluppatori, webmaster e agenzie tecniche.

### 4.1 Panoramica dell'architettura

Il modulo `multiprice` (nome interno `ajax_multiprice`) è un modulo PrestaShop standard focalizzato principalmente sulla visualizzazione del front-office. Sfrutta il sistema di hook di PrestaShop per iniettare informazioni sui prezzi in più valute negli elenchi dei prodotti e nelle pagine dei dettagli del prodotto. La logica principale risiede nel file del modulo principale, gestendo la configurazione e la registrazione degli hook. JavaScript lato client viene utilizzato per gli aggiornamenti dinamici dei prezzi quando le combinazioni o le quantità dei prodotti cambiano, garantendo un'accuratezza in tempo reale senza ricariche complete della pagina. Non introduce tabelle di database personalizzate o ObjectModels complessi, basandosi invece sui meccanismi esistenti di PrestaShop per la valuta e i prezzi dei prodotti.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller Front-Office o Back-Office Admin personalizzati. Tutta la configurazione è gestita tramite il metodo `getContent()` nel file del modulo principale, e le interazioni del front-office sono gestite tramite hook e JavaScript lato client.

### 4.3 Classi e modelli principali (`classes/`)

Il modulo non definisce classi o ObjectModels personalizzati nella directory `classes/`. La sua logica è incapsulata nel file del modulo principale `ajax_multiprice.php`.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`multiprice/lib/searchTool/views/js/autocomplete.js`**

    -   **Ambito:** Potenzialmente Front-office (se utilizzato per una funzione di ricerca all'interno del modulo, sebbene non direttamente correlato alla visualizzazione principale dei prezzi multipli).
    -   **Responsabilità:** Questo file sembra far parte di una libreria generica di strumenti di ricerca con completamento automatico inclusa nel modulo. In genere gestirebbe le richieste AJAX per i suggerimenti di ricerca, si legherebbe ai campi di input e visualizzerebbe i risultati. La sua rilevanza diretta per la visualizzazione dei prezzi in più valute è probabilmente minima a meno che il modulo non integri una funzione di ricerca che visualizzi anche i prezzi.
    -   **Dettagli:** Si lega ai campi di input, ascolta gli eventi `keyup`, effettua chiamate AJAX a un endpoint backend (non definito nei controller di questo modulo, probabilmente un controller di ricerca generico di PrestaShop o un controller di uno strumento di ricerca incluso) e manipola il DOM per mostrare un elenco a discesa di suggerimenti.
-   **`multiprice/views/js/multiprice.js`**

    -   **Ambito:** Front-office.
    -   **Responsabilità:** Questo è il file JavaScript principale per la visualizzazione dei prezzi in più valute. È responsabile dell'aggiornamento dinamico dei prezzi visualizzati quando gli attributi del prodotto (combinazioni) o le quantità cambiano nella pagina del prodotto.
    -   **Dettagli:**
        -   Ascolta gli eventi `change` sui selettori di combinazione del prodotto (ad esempio, elementi `select` per gli attributi, pulsanti radio).
        -   Ascolta gli eventi `change` o `blur` sul campo di input della quantità.
        -   Si aggancia all'evento nativo di PrestaShop `prestashop.on('updatedProduct', ...)` (per PS 1.7+), che viene attivato quando i dati del prodotto (incluso il prezzo) vengono aggiornati dopo la selezione della combinazione.
        -   Recupera il nuovo prezzo base dai dati del prodotto aggiornati.
        -   Esegue calcoli lato client per convertire il nuovo prezzo base nelle valute aggiuntive configurate, utilizzando i tassi di cambio potenzialmente passati dal backend o memorizzati in una variabile JS globale.
        -   Aggiorna gli elementi DOM (`<span>`, `<div>`) in cui vengono visualizzati i prezzi in valuta aggiuntiva.
        -   Garantisce la corretta formattazione dei prezzi convertiti (simbolo di valuta, decimali).

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`multiprice/lib/searchTool/views/css/autocomplete.css`**

    -   **Ambito:** Front-office.
    -   **Responsabilità:** Stila il menu a discesa dei risultati della ricerca con completamento automatico, inclusi suggerimenti, evidenziazione e layout generale.
    -   **Selettori di classe CSS chiave:** Probabilmente si rivolge a classi come `.autocomplete-results`, `.autocomplete-item`, `.highlighted`. Gli sviluppatori possono sovrascriverli nel `custom.css` o `theme.css` del loro tema.
-   **`multiprice/views/css/multiprice.css`**

    -   **Ambito:** Styling del cliente del Front-office.
    -   **Responsabilità:** Fornisce lo stile predefinito per i blocchi di visualizzazione dei prezzi in più valute. Ciò include dimensioni dei caratteri, colori, margini e potenzialmente il layout (ad esempio, impilamento verticale dei prezzi).
    -   **Selettori di classe CSS chiave:** Si rivolgerà a classi specifiche aggiunte dai template del modulo (ad esempio, `.multiprice-container`, `.multiprice-currency-item`, `.multiprice-price`). Gli sviluppatori possono sovrascrivere questi selettori nel CSS del loro tema per adattarli al design del loro negozio.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **`multiprice/lib/searchTool/views/scripts.tpl`**

    -   **Ambito:** Front-office.
    -   **Scopo:** Questo template probabilmente include il JavaScript e il CSS per la funzionalità `autocomplete.js`. Verrebbe agganciato a `displayHeader` o `displayFooter` per garantire che le risorse necessarie vengano caricate.
-   **`multiprice/views/templates/multiprice-custom.tpl`**

    -   **Ambito:** Front-office (template hook).
    -   **Scopo:** Questo template è probabilmente un fallback o un template alternativo per visualizzare i prezzi in più valute, possibilmente per hook specifici o posizionamenti personalizzati. Contenerebbe la struttura HTML per renderizzare il prezzo principale e quindi iterare attraverso le valute aggiuntive per visualizzare i loro prezzi convertiti.
-   **`multiprice/views/templates/multiprice.tpl`**

    -   **Ambito:** Front-office (template hook).
    -   **Scopo:** Questo è il template principale responsabile del rendering del blocco dei prezzi in più valute. Viene iniettato negli elementi dell'elenco dei prodotti e nella pagina dei dettagli del prodotto tramite gli hook di PrestaShop. Riceve un array di valute e i loro prezzi convertiti e li formatta in base alla configurazione del modulo.
    -   **Variabili:** Si aspetta variabili come `$product_price`, `$additional_currencies` (un array di oggetti valuta con prezzi convertiti), `$currency_format`, ecc.
-   **`multiprice/views/templates/selectedProducts.tpl`**

    -   **Ambito:** Front-office.
    -   **Scopo:** Il nome di questo template suggerisce che potrebbe essere utilizzato in un contesto in cui viene visualizzato un elenco di prodotti selezionati, potenzialmente in un riepilogo del carrello, una pagina di confronto o un widget di selezione prodotti personalizzato. Itererebbe su una collezione di prodotti e visualizzerebbe i loro prezzi, potenzialmente con la funzione multi-valuta.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non crea tabelle SQL personalizzate.
    -   Memorizza le sue impostazioni di configurazione (ad esempio, stato abilitato, valute selezionate, opzioni di visualizzazione) nella tabella `ps_configuration`, utilizzando chiavi con prefisso `MULTIPRICE_` o simili.
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Per includere `multiprice.js` e `multiprice.css` (e potenzialmente le risorse `autocomplete`) nelle pagine del front-office. |
| `displayProductPriceBlock` (tipo `after_price`) | Dopo il blocco del prezzo principale nelle pagine dei prodotti. | Per iniettare il contenuto di `multiprice.tpl` o `multiprice-custom.tpl` che visualizza i prezzi in valuta aggiuntiva nella pagina dei dettagli del prodotto. |
| `displayProductListReviews` (o simile per l'elenco prodotti) | All'interno degli elementi dell'elenco prodotti (ad esempio, pagine di categoria). | Per iniettare il contenuto di `multiprice.tpl` o `multiprice-custom.tpl` che visualizza i prezzi in valuta aggiuntiva sotto il prezzo principale nelle pagine di elenco prodotti. L'hook esatto potrebbe variare a seconda della versione di PrestaShop e della struttura del tema (ad esempio, `displayProductPriceBlock` può essere utilizzato anche qui, o un hook personalizzato fornito dal tema). |
| `actionProductUpdate` (o simile) | Dopo l'aggiornamento di un prodotto nel back office. | (Meno probabile per questo modulo) Potrebbe essere utilizzato per svuotare la cache relativa ai prezzi dei prodotti, sebbene non strettamente necessario per la sua funzione principale. |
| `actionFrontControllerSetMedia` | Prima che un controller frontale renda il suo contenuto. | Per registrare file JavaScript e CSS per il front office, assicurando che vengano caricati correttamente. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e qualsiasi domanda relativa al modulo "Mostra il prezzo in diverse valute contemporaneamente", visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con l'installazione, la configurazione e qualsiasi problema tu possa incontrare.
