---
title: "Carrello a barra laterale scorrevole - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Carrello a barra laterale scorrevole di MyPresta.eu."
sidebar:
  label: "Carrello a barra laterale scorrevole - Manuale del commerciante e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Sliding sidebar cart su MyPresta.eu](https://mypresta.eu/modules/front-office-features/sliding-sidebar-cart.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/sliding-sidebar-cart/)
>
> ---


# Carrello a barra laterale scorrevole

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Panoramica completa della configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo aver installato il modulo, clicca su "Configura" per accedere alle sue impostazioni. Questa pagina ti consente di controllare esattamente quali informazioni vengono visualizzate all'interno del carrello a barra laterale scorrevole.

- **Visualizza immagine prodotto**

  - **Cosa fa questa impostazione:** Controlla se l'immagine in miniatura di ogni prodotto nel carrello viene mostrata nella barra laterale.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato ("Sì"):* Una piccola immagine di ogni prodotto apparirà accanto al suo nome nella barra laterale, rendendo più facile per i clienti identificare visivamente gli articoli.
    - *Quando disabilitato ("No"):* Verranno mostrati solo il nome del prodotto e altri dettagli testuali, risparmiando spazio ma potenzialmente rendendo il carrello meno coinvolgente visivamente.
  - **Valore consigliato:** "Sì"
  - **Scenario / esempio del commerciante:** L'abilitazione di questa opzione aiuta i clienti a confermare rapidamente di aver aggiunto l'articolo corretto, particolarmente utile per i negozi con molti prodotti o varianti dal nome simile.
- **Visualizza nome prodotto**

  - **Cosa fa questa impostazione:** Determina se il nome di ogni prodotto è visibile nel carrello scorrevole.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato ("Sì"):* Verrà visualizzato il nome completo di ogni prodotto.
    - *Quando disabilitato ("No"):* I nomi dei prodotti verranno nascosti. Questo non è generalmente raccomandato in quanto rende il carrello difficile da capire.
  - **Valore consigliato:** "Sì"
  - **Scenario / esempio del commerciante:** Questa è un'informazione fondamentale. Tienila sempre su "Sì" in modo che i clienti sappiano esattamente cosa c'è nel loro carrello.
- **Visualizza valori attributi prodotto**

  - **Cosa fa questa impostazione:** Se i tuoi prodotti hanno attributi (come taglia, colore, materiale), questa impostazione controlla se gli attributi selezionati vengono mostrati per ogni prodotto nel carrello.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato ("Sì"):* Per un prodotto come "T-Shirt (Taglia: M, Colore: Blu)", verrà visualizzato "Taglia: M, Colore: Blu".
    - *Quando disabilitato ("No"):* Verrà mostrato solo "T-Shirt", potenzialmente confondendo i clienti sulla variante esatta che hanno aggiunto.
  - **Valore consigliato:** "Sì" (specialmente per i negozi che vendono prodotti configurabili)
  - **Scenario / esempio del commerciante:** Cruciale per i negozi che vendono abbigliamento, elettronica con diverse specifiche o qualsiasi prodotto con più opzioni. Aiuta i clienti a verificare di aver selezionato la variante giusta.
- **Visualizza prezzo prodotto**

  - **Cosa fa questa impostazione:** Controlla se il prezzo individuale di ogni prodotto nel carrello viene visualizzato.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato ("Sì"):* Il prezzo unitario per ogni articolo sarà visibile.
    - *Quando disabilitato ("No"):* I prezzi dei singoli prodotti saranno nascosti, sebbene il valore totale del carrello sarà comunque mostrato.
  - **Valore consigliato:** "Sì"
  - **Scenario / esempio del commerciante:** La trasparenza è fondamentale. Mostrare i prezzi individuali aiuta i clienti a comprendere la ripartizione dei costi e conferma le loro selezioni.
- **Visualizza campo di input quantità**

  - **Cosa fa questa impostazione:** Consente ai clienti di modificare la quantità di un articolo direttamente all'interno del carrello a barra laterale utilizzando un campo di input.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato ("Sì"):* Un campo di input numerico (es. "1", "2", "3") apparirà accanto a ogni prodotto, consentendo ai clienti di digitare una nuova quantità o utilizzare i pulsanti di incremento/decremento.
    - *Quando disabilitato ("No"):* I clienti non possono modificare le quantità nella barra laterale; dovrebbero andare alla pagina completa del carrello per farlo.
  - **Valore consigliato:** "Sì"
  - **Scenario / esempio del commerciante:** Questo migliora significativamente l'usabilità. Un cliente che ha accidentalmente aggiunto 2 articoli invece di 1 può correggerlo istantaneamente senza lasciare la pagina corrente, riducendo la frustrazione e il potenziale abbandono del carrello.
- **Visualizza pulsante rimuovi**

  - **Cosa fa questa impostazione:** Aggiunge un pulsante (solitamente una "X" o un'icona del cestino) accanto a ogni prodotto, consentendo ai clienti di rimuoverlo dal carrello.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato ("Sì"):* I clienti possono facilmente eliminare gli articoli indesiderati dal carrello direttamente dalla barra laterale.
    - *Quando disabilitato ("No"):* I clienti non possono rimuovere articoli dalla barra laterale; dovrebbero andare alla pagina completa del carrello.
  - **Valore consigliato:** "Sì"
  - **Scenario / esempio del commerciante:** Essenziale per un'esperienza di acquisto flessibile. Se un cliente cambia idea su un articolo, può rimuoverlo istantaneamente, impedendogli di abbandonare l'intero carrello a causa di un prodotto indesiderato.
- **Visualizza costo di spedizione**

  - **Cosa fa questa impostazione:** Mostra una stima o il costo di spedizione effettivo all'interno del riepilogo del carrello a barra laterale.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato ("Sì"):* Il costo di spedizione stimato o calcolato verrà visualizzato nel riepilogo del carrello.
    - *Quando disabilitato ("No"):* I costi di spedizione non verranno mostrati nella barra laterale, solo nel carrello completo o nella pagina di checkout.
  - **Valore consigliato:** "Sì" (se il calcolo della spedizione è accurato fin dall'inizio)
  - **Scenario / esempio del commerciante:** La trasparenza sui costi di spedizione in anticipo può prevenire lo "shock del prezzo" al checkout, che è una delle principali cause di abbandono del carrello. Se la tua spedizione è complessa o dipende fortemente dall'indirizzo del cliente, potresti considerare di lasciarla "No" per evitare stime fuorvianti.
- **Visualizza subtotale (valore totale prodotti)**

  - **Cosa fa questa impostazione:** Mostra il valore totale di tutti i prodotti nel carrello, *prima* che vengano applicati spedizione, tasse o sconti.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato ("Sì"):* Verrà visualizzata la somma di tutti i prezzi dei prodotti.
    - *Quando disabilitato ("No"):* Questa specifica riga del subtotale verrà nascosta.
  - **Valore consigliato:** "Sì"
  - **Scenario / esempio del commerciante:** Fornisce una chiara ripartizione per il cliente, aiutandolo a comprendere il costo degli articoli stessi separatamente da altri addebiti.
- **Visualizza tasse subtotale**

  - **Cosa fa questa impostazione:** Mostra l'importo totale delle tasse applicate ai prodotti nel carrello.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato ("Sì"):* L'importo totale delle tasse verrà visualizzato nel riepilogo del carrello.
    - *Quando disabilitato ("No"):* I dettagli delle tasse non verranno mostrati nella barra laterale.
  - **Valore consigliato:** "Sì" (specialmente nelle regioni in cui la trasparenza fiscale è legalmente richiesta o attesa dai clienti)
  - **Scenario / esempio del commerciante:** Importante per la trasparenza, in particolare nei paesi in cui l'IVA o l'imposta sulle vendite è una componente significativa del prezzo finale. Aiuta i clienti a comprendere la ripartizione completa dei costi prima di procedere al checkout.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Visualizza immagine prodotto | Sì | Mostra miniature dei prodotti per l'identificazione visiva. |
| Configurazione modulo | Visualizza nome prodotto | Sì | Mostra il nome di ogni prodotto nel carrello. |
| Configurazione modulo | Visualizza valori attributi prodotto | Sì | Mostra gli attributi selezionati (taglia, colore) per i prodotti configurabili. |
| Configurazione modulo | Visualizza prezzo prodotto | Sì | Mostra il prezzo individuale di ogni prodotto. |
| Configurazione modulo | Visualizza campo di input quantità | Sì | Consente ai clienti di modificare le quantità dei prodotti direttamente nella barra laterale. |
| Configurazione modulo | Visualizza pulsante rimuovi | Sì | Consente ai clienti di rimuovere i prodotti dal carrello direttamente nella barra laterale. |
| Configurazione modulo | Visualizza costo di spedizione | Sì | Mostra il costo di spedizione stimato/effettivo nel riepilogo. |
| Configurazione modulo | Visualizza subtotale (valore totale prodotti) | Sì | Mostra il valore totale dei prodotti prima di spedizione/tasse. |
| Configurazione modulo | Visualizza tasse subtotale | Sì | Mostra l'importo totale delle tasse applicate ai prodotti. |

## 3. Risoluzione dei problemi del commerciante e Domande frequenti (FAQ)

**D1: La barra laterale non scorre quando aggiungo un prodotto al carrello.**
R1:

-   **Verifica lo stato del modulo:** Assicurati che il modulo "Carrello a barra laterale scorrevole" sia installato e abilitato in **Moduli > Gestione moduli**.
-   **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). A volte, i vecchi file di cache impediscono il caricamento delle nuove funzionalità del modulo.
-   **Conflitti con il tema:** Il tuo tema potrebbe avere una propria conferma "aggiungi al carrello" o JavaScript che entra in conflitto con questo modulo. Passa temporaneamente al tema PrestaShop predefinito (Classic) per vedere se la barra laterale funziona. Se funziona, il problema è con il JavaScript o il CSS del tuo tema personalizzato. Potrebbe essere necessario un sviluppatore per indagare.
-   **Errori JavaScript:** Apri la console per sviluppatori del tuo browser (solitamente F12) e controlla eventuali errori JavaScript quando aggiungi un prodotto. Questi errori possono impedire la comparsa della barra laterale.

**D2: La barra laterale appare, ma lo stile sembra sbagliato (colori, font o layout errati).**
R2:

-   **Conflitti CSS del tema:** Questo è quasi sempre un conflitto CSS con il tuo tema PrestaShop attivo. I fogli di stile del tuo tema potrebbero sovrascrivere gli stili del modulo.
-   **Soluzione:** Probabilmente avrai bisogno di un webmaster o di uno sviluppatore per ispezionare il CSS utilizzando gli strumenti per sviluppatori del browser. Possono identificare gli stili in conflitto e aggiungere CSS personalizzato al tuo tema (o al file CSS personalizzato del modulo, se disponibile) per garantire che la barra laterale venga visualizzata correttamente.

**D3: Le quantità o i prezzi non si aggiornano correttamente quando li modifico nella barra laterale.**
R3:

-   **Svuota la cache:** Ancora una volta, prova a svuotare la cache di PrestaShop (**Parametri avanzati > Prestazioni**).
-   **Problemi AJAX:** Il modulo utilizza AJAX per aggiornare il carrello. Se ci sono errori lato server o conflitti JavaScript che impediscono il completamento delle chiamate AJAX, gli aggiornamenti non verranno registrati. Controlla la console per sviluppatori del tuo browser per errori di rete o errori JavaScript quando provi a modificare le quantità.
-   **Configurazione del modulo:** Ricontrolla che "Visualizza campo di input quantità" sia abilitato nella configurazione del modulo.

**D4: Come posso tradurre il testo nella barra laterale in altre lingue?**
R4:

-   **Sistema di traduzione di PrestaShop:** Vai su **Internazionale > Traduzioni** nel tuo Back Office.
-   **Tipo di traduzione:** Seleziona "Traduzioni dei moduli installati".
-   **Seleziona modulo:** Scegli "Carrello a barra laterale scorrevole" dal menu a discesa dei moduli.
-   **Seleziona lingua:** Scegli la lingua che desideri tradurre.
-   **Traduci:** Vedrai un elenco di stringhe traducibili dal modulo. Inserisci le tue traduzioni e salva.

**D5: Posso cambiare il lato da cui scorre la barra laterale (sinistra vs. destra)?**
R5:

-   Il comportamento predefinito del modulo è tipicamente quello di scorrere da destra. La modifica di questo richiederebbe modifiche CSS personalizzate, poiché è controllato dai file `sidcart.css` e `sidcart-right.css`. Uno sviluppatore potrebbe regolare le proprietà CSS (ad esempio, `right: 0` a `left: 0`) e potenzialmente la logica di animazione per ottenere questo risultato.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Carrello a barra laterale scorrevole" (`sidcart`) segue un'architettura standard dei moduli PrestaShop, concentrandosi principalmente sui miglioramenti del front-office. Sfrutta il sistema di hook di PrestaShop per iniettare la sua funzionalità e i suoi template nel negozio. La logica principale per l'interazione del carrello (aggiunta, aggiornamento, rimozione di prodotti) è gestita tramite un controller frontale AJAX, garantendo un'esperienza utente dinamica e non intrusiva. La configurazione è gestita tramite il metodo `getContent()` della classe principale del modulo, memorizzando le impostazioni in `ps_configuration`.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `controllers/front/ajax.php`
        -   **Nome classe e classe padre**: `SidcartAjaxModuleFrontController` estende `ModuleFrontController`.
        -   **Responsabilità**: Questo controller è responsabile della gestione di tutte le richieste AJAX relative al carrello scorrevole. Quando un utente aggiunge un prodotto, aggiorna una quantità o rimuove un articolo dalla barra laterale, il JavaScript invia una richiesta a questo controller. Elabora la modifica del carrello utilizzando la classe `Cart` principale di PrestaShop e quindi restituisce un riepilogo del carrello aggiornato (solitamente frammenti HTML o dati JSON) al JavaScript del front-end, che poi aggiorna il contenuto della barra laterale. Ciò garantisce aggiornamenti in tempo reale senza ricaricamenti completi della pagina.
-   **Controller Amministrativi Back-Office**: Nessuno. Tutta la configurazione è gestita all'interno del metodo `getContent()` del modulo principale.

### 4.3 Classi e modelli principali (`classes/`)

Il modulo non definisce alcuna classe `ObjectModel` personalizzata o classi dedicate nella directory `classes/`. La sua logica principale risiede nel file `sidcart.php` e nel controller frontale `ajax.php`, interagendo direttamente con le classi native `Cart` e `Product` di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

-   `sidcart/views/js/sidcart.js`
    -   **Ambito**: Front-office.
    -   **Dettagli**: Questo è il file JavaScript principale per il modulo.
        -   Ascolta gli eventi "aggiungi al carrello" (ad esempio, clic su pulsanti con classi specifiche come `.add-to-cart`).
        -   Intercetta il comportamento predefinito "aggiungi al carrello" e invece attiva la barra laterale scorrevole.
        -   Gestisce la comunicazione AJAX con `controllers/front/ajax.php` per aggiornare il contenuto del carrello.
        -   Gestisce la visualizzazione e l'animazione della barra laterale (scorrimento in entrata/uscita).
        -   Associa i listener di eventi per le modifiche di quantità e i pulsanti di rimozione all'interno della barra laterale stessa, inviando ulteriori richieste AJAX per aggiornare il carrello.
        -   Probabilmente utilizza `jQuery` per la manipolazione del DOM e le chiamate AJAX, comune in PrestaShop 1.7.x e 8.x.
        -   Potrebbe anche ascoltare `prestashop.on('updateCart', ...)` o eventi simili per garantire che la barra laterale rifletta le modifiche apportate da altri moduli o dalla funzionalità principale di PrestaShop.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `sidcart/views/css/sidcart-right.css`

    -   **Ambito**: Stile del cliente del front-office.
    -   **Dettagli**: Questo foglio di stile definisce l'aspetto visivo e il posizionamento della barra laterale scorrevole quando appare dal lato destro dello schermo.
        -   Include regole per la larghezza, lo sfondo, lo z-index e la posizione `right` iniziale della barra laterale (ad esempio, `right: -300px;` per nasconderla).
        -   Definisce le proprietà di transizione per animazioni di scorrimento fluide (ad esempio, `transition: right 0.3s ease-in-out;`).
        -   Stila l'overlay che appare dietro la barra laterale quando è aperta.
        -   Contiene regole specifiche per la reattività mobile, regolando la larghezza o la posizione della barra laterale su schermi più piccoli.
        -   **Selettori di classe CSS chiave**: `.sidcart-wrapper`, `.sidcart-content`, `.sidcart-overlay`, `.sidcart-open`.
-   `sidcart/views/css/sidcart.css`

    -   **Ambito**: Stile del cliente del front-office.
    -   **Dettagli**: Questo foglio di stile contiene regole di stile generali per gli elementi *all'interno* del carrello scorrevole, indipendentemente dal fatto che scorra da sinistra o da destra.
        -   Stila gli elementi dell'elenco prodotti (`.sidcart-product-line`).
        -   Stila le immagini dei prodotti, i nomi, i prezzi, gli attributi, i campi di input della quantità e i pulsanti di rimozione.
        -   Stila le sezioni di riepilogo del carrello (subtotale, spedizione, totale).
        -   Stila i pulsanti "Continua lo shopping" e "Procedi al checkout".
        -   **Selettori di classe CSS chiave**: `.sidcart-product-image`, `.sidcart-product-name`, `.sidcart-product-price`, `.sidcart-qty-input`, `.sidcart-remove-button`, `.sidcart-summary`, `.sidcart-buttons`.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**:

    -   `sidcart/views/templates/hook/product-line.tpl`
        -   **Hook**: Questo template non è direttamente agganciato ma viene renderizzato dinamicamente dal controller AJAX (`ajax.php`) per rappresentare una singola voce di prodotto all'interno del carrello scorrevole.
        -   **Output**: Renderizza l'HTML per un prodotto, inclusa la sua immagine, nome, attributi, prezzo, input quantità e pulsante di rimozione, in base alle impostazioni di configurazione del modulo.
    -   `sidcart/views/templates/hook/sidcart.tpl`
        -   **Hook**: Questo template è probabilmente renderizzato dall'hook `displayHeader` o `displayNav2` (o simile) per iniettare la struttura principale della barra laterale scorrevole nella pagina. Potrebbe essere inizialmente nascosto e poi rivelato da JavaScript.
        -   **Output**: Contiene la struttura HTML principale per l'intera barra laterale scorrevole, inclusi il contenitore, l'area dell'elenco prodotti, il riepilogo del carrello e i pulsanti di azione. Funge da wrapper per il contenuto `product-line.tpl` caricato dinamicamente.
-   **Template amministrativi (`views/templates/admin/`)**: Nessuno.
-   **Template front-office (`views/templates/front/`)**:

    -   `sidcart/views/templates/modal.tpl`
        -   **Hook**: Questo template è probabilmente un fallback o una struttura alternativa per una visualizzazione simile a una modale, oppure potrebbe essere utilizzato per una parte specifica della barra laterale (ad esempio, un messaggio di conferma). Data la descrizione del modulo, è meno probabile che sia il pannello scorrevole primario stesso, ma potrebbe essere un componente al suo interno o un template legacy.
        -   **Output**: Renderizza una struttura modale o popup generica. Gli sviluppatori dovrebbero verificarne l'utilizzo effettivo all'interno della logica `sidcart.js` o `ajax.php`.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**:
    Il modulo non crea tabelle SQL personalizzate. Tutte le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` di PrestaShop utilizzando chiavi come `sc_ajaxInfo`, `sc_continueshopping`, `sc_pimage`, `sc_total`, `sc_subtotals_tax`, `sc_subtotals`, `sc_shipping`, `sc_remove`, `sc_qty_change`, `sc_price`, `sc_pname`, `sc_attributes`.
-   **Tabella degli hook registrati**:

| Nome Hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Utilizzato per includere i file CSS e JavaScript del modulo (`sidcart.css`, `sidcart-right.css`, `sidcart.js`) e potenzialmente per iniettare la struttura HTML iniziale e nascosta della barra laterale. |
| `actionAdminControllerSetMedia` | Quando un controller amministrativo viene inizializzato e le sue risorse multimediali vengono impostate. | Utilizzato per includere eventuali CSS/JS necessari per la pagina di configurazione del modulo nel Back Office. |
| `displayNav2` | Nella barra di navigazione, tipicamente vicino all'icona del carrello. | Utilizzato per iniettare un piccolo riepilogo del carrello (ad esempio, numero di articoli, prezzo totale) o per allegare il listener di eventi all'icona del carrello esistente che attiva la barra laterale. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Carrello a barra laterale scorrevole", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda possiate avere riguardo alla funzionalità e compatibilità del modulo.
