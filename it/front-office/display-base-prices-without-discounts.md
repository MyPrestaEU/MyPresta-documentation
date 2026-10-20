---
title: "Visualizza prezzi base (senza sconti) - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Visualizza prezzi base (senza sconti)' di MyPresta.eu."
sidebar:
  label: "Visualizza prezzi base (senza sconti) - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Display base prices (without discounts) su MyPresta.eu](https://mypresta.eu/modules/front-office-features/display-base-prices-without-discounts.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/display-base-prices-without-discounts/)
>
> ---


# Visualizza prezzi base (senza sconti)

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono generalmente sufficienti. Non sono necessarie configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al nome del modulo per accedere alle sue impostazioni. Questa è la schermata principale in cui controlli come e dove vengono visualizzati i prezzi base.

| Impostazione / Opzione | Cosa fa questa impostazione | Effetto della modifica di questa impostazione | Valore consigliato | Scenario / esempio commerciante |
| --- | --- | --- | --- | --- |
| **Abilita modulo** | Questo è l'interruttore principale per attivare o disattivare la funzionalità del modulo. | *Quando abilitato:* Il modulo inizierà a visualizzare i prezzi base nel tuo front-office in base ad altre impostazioni. *Quando disabilitato:* Il modulo smetterà di visualizzare i prezzi base e il tuo negozio tornerà a mostrare solo i prezzi correnti. | SÌ | Hai appena installato il modulo e vuoi attivare le sue funzionalità. |
| **Visualizza nella pagina prodotto** | Controlla se il prezzo base viene mostrato nelle singole pagine di dettaglio del prodotto. | *Quando abilitato:* Il prezzo originale apparirà accanto al prezzo scontato nella pagina di ogni prodotto. *Quando disabilitato:* Il prezzo base non verrà mostrato nelle pagine prodotto, anche se abilitato altrove. | SÌ | Vuoi che i clienti che visualizzano un prodotto specifico vedano chiaramente i risparmi. |
| **Visualizza nelle pagine di categoria** | Controlla se il prezzo base viene mostrato nelle pagine di elenco prodotti (es. pagine di categoria, risultati di ricerca). | *Quando abilitato:* Il prezzo originale apparirà accanto al prezzo scontato per ogni prodotto elencato nelle categorie, nei risultati di ricerca, ecc. *Quando disabilitato:* Il prezzo base non verrà mostrato nelle pagine di elenco prodotti. | SÌ | Vuoi che i clienti che navigano nelle categorie identifichino rapidamente gli articoli scontati e i loro risparmi. |
| **Visualizza nel riepilogo del carrello** | Controlla se il prezzo base viene mostrato nel riepilogo del carrello. | *Quando abilitato:* Il prezzo originale sarà visibile per ogni prodotto nel carrello del cliente, rafforzando il risparmio totale. *Quando disabilitato:* Nel carrello verrà mostrato solo il prezzo corrente, scontato. | NO (o SÌ, a seconda del tema) | Vuoi ricordare ai clienti il loro risparmio totale prima che procedano al checkout. Tuttavia, alcuni temi potrebbero non avere un'area di visualizzazione adatta, oppure potrebbe ingombrare il carrello. Testare accuratamente. |
| **CSS personalizzato per il prezzo base** | Ti consente di aggiungere regole CSS personalizzate per stilizzare il prezzo base visualizzato. | *Quando compilato con CSS:* Il prezzo base verrà stilizzato in base al tuo input (es. dimensione del carattere, colore, barratura). *Quando vuoto:* Il modulo utilizzerà la sua stilizzazione predefinita o erediterà gli stili dal tuo tema. | `text-decoration: line-through; color: #999; font-size: 0.9em;` | Vuoi che il prezzo base sia grigio e barrato per differenziarlo chiaramente dal prezzo corrente. |
| **Posizione del prezzo base** | Determina dove viene iniettato il prezzo base rispetto al prezzo corrente. | *Opzioni: Prima del prezzo corrente, Dopo il prezzo corrente.* *Quando impostato su 'Prima':* Il prezzo base apparirà a sinistra del prezzo corrente. *Quando impostato su 'Dopo':* Il prezzo base apparirà a destra del prezzo corrente. | Prima del prezzo corrente | Vuoi che il cliente veda prima il prezzo originale, poi il nuovo prezzo più basso. |

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Abilita modulo | SÌ | Attiva/disattiva la funzionalità principale del modulo. |
| Configurazione modulo | Visualizza nella pagina prodotto | SÌ | Mostra il prezzo base nelle singole pagine prodotto. |
| Configurazione modulo | Visualizza nelle pagine di categoria | SÌ | Mostra il prezzo base nelle pagine di elenco prodotti (categorie, ricerca). |
| Configurazione modulo | Visualizza nel riepilogo del carrello | NO (o SÌ, testare) | Mostra il prezzo base nel carrello. |
| Configurazione modulo | CSS personalizzato per il prezzo base | `text-decoration: line-through; color: #999; font-size: 0.9em;` | Personalizza lo stile visivo del prezzo base. |
| Configurazione modulo | Posizione del prezzo base | Prima del prezzo corrente | Controlla il posizionamento rispetto al prezzo corrente. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I prezzi base non vengono visualizzati nel mio negozio, anche se il modulo è abilitato.**
R:

1.  **Controlla le impostazioni del modulo:** Assicurati che "Abilita modulo" e le opzioni di visualizzazione specifiche (es. "Visualizza nella pagina prodotto") siano impostate su SÌ.
2.  **Svuota la cache di PrestaShop:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" in alto a destra. Spesso è necessario svuotare la cache di Smarty affinché le modifiche al template appaiano.
3.  **Verifica la presenza di sconti:** Assicurati che i prodotti che stai testando abbiano effettivamente sconti attivi (regole di prezzo del catalogo, prezzi specifici o riduzioni percentuali) applicati. Il modulo mostra un prezzo base solo se c'è una differenza.
4.  **Compatibilità del tema:** Alcuni temi altamente personalizzati potrebbero sovrascrivere le funzioni di visualizzazione del prezzo di base di PrestaShop. Se il problema persiste, contatta il supporto MyPresta.eu.

**D: Il prezzo base viene visualizzato, ma non si adatta bene al mio tema (colore, dimensione sbagliati, ecc.).**
R: Utilizza l'impostazione "CSS personalizzato per il prezzo base" nella configurazione del modulo. Puoi aggiungere regole CSS per abbinare il design del tuo tema. Ad esempio, per renderlo grigio e barrato: `text-decoration: line-through; color: #999; font-size: 0.9em;`. Se non sei sicuro del CSS, uno sviluppatore web può aiutarti.

**D: Questo modulo rallenterà il mio negozio?**
R: Il modulo è progettato per essere leggero. Principalmente sovrascrive una classe core di PrestaShop (`Product.php`) per recuperare il prezzo base e inietta un piccolo template. L'impatto sulle prestazioni dovrebbe essere trascurabile. Assicurati sempre che la cache di PrestaShop sia abilitata per una velocità ottimale.

**D: Questo modulo funziona con negozi multilingue?**
R: Sì, il modulo funziona con le funzionalità multilingue di PrestaShop. I prezzi vengono visualizzati nella valuta e nel formato della lingua/paese attivo.

**D: Vedo un errore "Conflitto di override" dopo aver installato il modulo.**
R: Questo modulo sovrascrive la classe `Product.php`. Se un altro modulo tenta di sovrascrivere la stessa classe, potresti riscontrare un conflitto. PrestaShop 1.7+ ha una migliore gestione degli override, ma i conflitti possono comunque verificarsi. Dovrai disabilitare uno dei moduli in conflitto o unire manualmente gli override (richiede conoscenze da sviluppatore). Contatta il supporto MyPresta.eu per assistenza.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Visualizza prezzi base (senza sconti)" opera principalmente sovrascrivendo la classe `Product` core per introdurre un metodo per recuperare il prezzo base del prodotto senza riduzioni. Utilizza quindi un template Smarty per visualizzare questo prezzo nel front office, iniettato tramite un meccanismo di hook personalizzato. La configurazione del modulo è gestita tramite un metodo `getContent()` standard di PrestaShop nel file principale del modulo.

### 4.2 Controller (`controllers/`)

Questo modulo non introduce alcun controller front-office o back-office personalizzato. La sua funzionalità è integrata direttamente nei meccanismi di visualizzazione dei prezzi esistenti di PrestaShop e tramite un override.

### 4.3 Classi e modelli core (`classes/`)

-   **`baseprices/override/classes/index.php`**: Un file `index.php` vuoto standard per prevenire l'elenco delle directory.
-   **`baseprices/override/classes/Product.php`**:
    -   **Nome classe**: `Product` (sovrascrive la classe `Product` core)
    -   **Classe genitore**: `ProductCore`
    -   **Responsabilità**: Questo override è il cuore della funzionalità del modulo. Introduce un nuovo metodo, `getBasePrice()`, che calcola e restituisce il prezzo del prodotto *prima* che vengano applicati prezzi specifici, regole di prezzo del catalogo o riduzioni di gruppo. Questo metodo garantisce che il vero prezzo originale sia sempre disponibile per la visualizzazione. Tipicamente comporta l'aggiramento della logica di calcolo del prezzo standard che tiene conto degli sconti.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`baseprices/views/js/baseprices-admin.js`**:
    -   **Ambito**: Back-office (pagina di configurazione del modulo).
    -   **Responsabilità**: Questo script probabilmente gestisce qualsiasi comportamento dinamico o convalida nel modulo di configurazione del modulo. Ad esempio, potrebbe mostrare/nascondere le impostazioni in base ad altre selezioni o fornire feedback in tempo reale per il campo CSS personalizzato.
-   **`baseprices/views/js/baseprices.js`**:
    -   **Ambito**: Front-office.
    -   **Responsabilità**: Questo script è responsabile dell'iniezione dinamica del prezzo base nel DOM dove necessario, specialmente per i contenuti caricati tramite AJAX o quando gli attributi del prodotto cambiano (es. selezione di una combinazione diversa nella pagina del prodotto). Ascolta l'evento `updateProduct` di PrestaShop o eventi simili per aggiornare la visualizzazione del prezzo. Potrebbe anche gestire lo stile o l'attivazione/disattivazione della visibilità per l'elemento del prezzo base.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`baseprices/views/css/baseprices.css`**:
    -   **Ambito**: Stile del cliente front-office.
    -   **Componenti UI principali e contenitori che stilizza**: Questo foglio di stile fornisce la presentazione visiva predefinita per il prezzo base. Tipicamente include regole per:
        -   `span.base-price` o selettori simili.
        -   `text-decoration: line-through;` per barrare il prezzo.
        -   `color`, `font-size`, `margin`, `padding` per posizionare e stilizzare il prezzo base rispetto al prezzo corrente.
    -   **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere**: `span.base-price`, `div.product-price-and-shipping .base-price`, ecc. Gli sviluppatori possono mirare a queste classi nel CSS personalizzato del loro tema per sovrascrivere lo stile predefinito del modulo.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **`baseprices/views/templates/baseprices.tpl`**:
    -   **Ambito**: Front-office.
    -   **Responsabilità**: Questo template è l'output principale per la visualizzazione del prezzo base. È progettato per essere incluso o renderizzato ovunque venga mostrato il prezzo di un prodotto. Tipicamente riceve variabili come `$base_price` e `$current_price` e le formatta in base alle impostazioni del modulo (es. CSS personalizzato, posizione). Conterrà la struttura HTML (es. `<span class="base-price">...</span>`) a cui si rivolge il CSS.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**: Questo modulo non crea tabelle del database personalizzate. Le sue impostazioni di configurazione sono memorizzate nella tabella `ps_configuration`, utilizzando chiavi con prefisso `BASEPRICES_`.
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Utilizzato per caricare le risorse CSS e JavaScript del front-office del modulo. |
| `displayProductPriceBlock` | All'interno del blocco di visualizzazione del prezzo del prodotto nelle pagine prodotto e negli elenchi. | Il modulo probabilmente sfrutta questo hook (o hook simili relativi al prezzo) per iniettare il suo template `baseprices.tpl`, visualizzando il prezzo base accanto al prezzo corrente. |
| `actionProductUpdate` / `actionProductSave` | Dopo che un prodotto viene aggiornato o salvato nel Back Office. | Sebbene non esplicitamente elencati, i moduli che sovrascrivono `Product.php` potrebbero utilizzare tali hook per svuotare le cache o reindicizzare i dati del prodotto se necessario, sebbene la funzione principale di questo modulo sia solo di visualizzazione. |
| `actionFrontControllerSetMedia` | Prima che un controller frontale renderizzi il suo template. | Utilizzato per registrare i file JavaScript e CSS del front-office per la pagina corrente. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo "Visualizza prezzi base (senza sconti)", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere.
"""
