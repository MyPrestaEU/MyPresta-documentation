---
title: "Slider ultimi ordini - Manuale commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Slider ultimi ordini di MyPresta.eu."
sidebar:
  label: "Slider ultimi ordini - Manuale commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Last orders slider su MyPresta.eu](https://mypresta.eu/modules/front-office-features/last-orders-slider.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/last-orders-slider/)
>
> ---


# Slider ultimi ordini

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.6+, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti e di solito sono abilitate per impostazione predefinita sulla maggior parte degli ambienti di hosting compatibili con PrestaShop.

## 2. Panoramica completa della configurazione (ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo "Slider ultimi ordini". Puoi accedervi navigando su **Moduli > Gestione moduli** e cliccando su "Configura" accanto al modulo "Slider ultimi ordini".

#### Impostazioni generali

-   **Cosa fa questa impostazione:** Questa sezione controlla il comportamento fondamentale e l'aspetto del tuo slider ordini.
-   **Effetto della modifica di questa impostazione:** La regolazione di queste impostazioni avrà un impatto diretto su come appare lo slider, dove appare e quali informazioni visualizza ai tuoi clienti.

| Impostazione / Opzione | Cosa fa questa impostazione | Effetto della modifica di questa impostazione | Valore consigliato | Scenario / esempio per il commerciante |
| --- | --- | --- | --- | --- |
| **Abilita modulo** | Attiva o disattiva l'intera funzionalità dello slider. | *Quando abilitato:* Lo slider apparirà nel tuo front office in base ad altre impostazioni. *Quando disabilitato:* Lo slider non sarà visibile ai clienti. | SÌ | Vuoi nascondere temporaneamente lo slider per manutenzione o una campagna speciale. |
| **Numero di ordini da visualizzare** | Determina quanti ordini recenti lo slider scorrerà. | *Se impostato su 5:* Lo slider mostrerà le informazioni per i 5 ordini più recenti. *Se impostato su 10:* Mostrerà 10. | 5-10 (a seconda del volume degli ordini) | Se hai un volume molto alto di ordini, mostrarne di più potrebbe essere eccessivo. Se hai meno ordini, mostrarne di più assicura che ci sia sempre contenuto. |
| **Stati degli ordini da visualizzare** | Seleziona quali stati degli ordini (ad esempio, "Pagamento accettato", "Consegnato") sono considerati "ordini recenti" per lo slider. | *Quando è selezionato "Pagamento accettato":* Appariranno solo gli ordini che hanno raggiunto questo stato. *Quando è selezionato "Annullato":* Potrebbero apparire ordini annullati (non raccomandato per la prova sociale). | "Pagamento accettato", "Elaborazione in corso", "Consegnato" | Vuoi mostrare solo gli ordini che sono confermati e in fase di elaborazione o che sono stati consegnati con successo, per costruire fiducia positiva. |
| **Visualizza nome cliente** | Controlla se vengono mostrati il nome e l'iniziale del cognome del cliente. | *Quando abilitato:* "John D. da New York..." *Quando disabilitato:* "Qualcuno da New York..." | SÌ | Mostrare un nome parziale aggiunge un tocco personale e rende gli ordini più reali, migliorando la prova sociale. |
| **Visualizza città cliente** | Controlla se viene mostrata la città del cliente. | *Quando abilitato:* "...da New York ha appena comprato..." *Quando disabilitato:* "...ha appena effettuato un ordine." | SÌ | Mostrare la città aggiunge un livello di autenticità e può risuonare con i clienti locali. |
| **Visualizza nome prodotto** | Controlla se viene mostrato il nome del prodotto acquistato. | *Quando abilitato:* "...ha appena comprato una T-Shirt." *Quando disabilitato:* "...ha appena effettuato un ordine." | SÌ | Mostrare il nome del prodotto rende l'acquisto più tangibile e può evidenziare gli articoli popolari. |
| **Visualizza immagine prodotto** | Controlla se viene mostrata una piccola immagine del prodotto acquistato. | *Quando abilitato:* Una piccola miniatura del prodotto apparirà accanto al testo. *Quando disabilitato:* Verrà visualizzato solo il testo. | SÌ | Le immagini sono coinvolgenti. Un'immagine del prodotto rende lo slider più attraente e informativo. |
| **Velocità animazione (millisecondi)** | Imposta la velocità con cui lo slider passa da un ordine all'altro. | *Valore inferiore (ad esempio, 3000):* Transizioni più veloci, gli ordini cambiano ogni 3 secondi. *Valore superiore (ad esempio, 8000):* Transizioni più lente, gli ordini cambiano ogni 8 secondi. | 5000 (5 secondi) | Una velocità moderata mantiene lo slider dinamico senza essere troppo veloce da leggere o troppo lento da aggiornare. |
| **Colore testo** | Imposta il colore del testo visualizzato nello slider. | *Se impostato su #000000 (nero):* Il testo sarà nero. *Se impostato su #FF0000 (rosso):* Il testo sarà rosso. | #FFFFFF (bianco) o un colore che contrasti con il tuo sfondo | Scegli un colore che risalti rispetto al colore di sfondo scelto e che si abbini all'estetica del tuo marchio. |
| **Colore sfondo** | Imposta il colore di sfondo della barra dello slider. | *Se impostato su #FFFFFF (bianco):* Lo sfondo dello slider sarà bianco. *Se impostato su #000000 (nero):* Lo sfondo dello slider sarà nero. | #000000 (nero) o un colore che contrasti con il tuo tema | Scegli un colore che renda lo slider visibile e che completi il design del tuo negozio. |
| **Hook per visualizzare lo slider** | Seleziona dove nel tuo tema PrestaShop apparirà lo slider. | *Quando è selezionato "displayTop":* Lo slider appare vicino alla parte superiore del tuo negozio. *Quando è selezionato "displayFooter":* Lo slider appare in basso. | displayTop o displayNavFullWidth | Scegli una posizione prominente dove i clienti lo vedranno facilmente senza ostruire contenuti critici. |

#### 2.1.1 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Abilita modulo | SÌ | Attiva/disattiva lo slider. |
| Configurazione modulo | Numero di ordini da visualizzare | 5-10 | Controlla quanti ordini recenti vengono mostrati. |
| Configurazione modulo | Stati degli ordini da visualizzare | Pagamento accettato, Elaborazione, Consegnato | Filtra gli ordini in base al loro stato per la visualizzazione. |
| Configurazione modulo | Visualizza nome cliente | SÌ | Mostra il nome e l'iniziale del cognome del cliente. |
| Configurazione modulo | Visualizza città cliente | SÌ | Mostra la città del cliente. |
| Configurazione modulo | Visualizza nome prodotto | SÌ | Mostra il nome del prodotto acquistato. |
| Configurazione modulo | Visualizza immagine prodotto | SÌ | Mostra una piccola immagine del prodotto acquistato. |
| Configurazione modulo | Velocità animazione (millisecondi) | 5000 | Imposta la velocità di transizione tra gli ordini. |
| Configurazione modulo | Colore testo | #FFFFFF (bianco) | Definisce il colore del testo nello slider. |
| Configurazione modulo | Colore sfondo | #000000 (nero) | Definisce il colore di sfondo dello slider. |
| Configurazione modulo | Hook per visualizzare lo slider | displayTop / displayNavFullWidth | Determina la posizione dello slider nel tuo tema. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D1: Lo slider non appare nel mio negozio. Cosa devo fare?**
R:

-   **Controlla lo stato del modulo:** Vai su **Moduli > Gestione moduli** e assicurati che "Slider ultimi ordini" sia installato e abilitato.
-   **Verifica la selezione dell'hook:** Nella configurazione del modulo, ricontrolla di aver selezionato un "Hook per visualizzare lo slider" valido (ad esempio, `displayTop`, `displayNavFullWidth`). Alcuni hook potrebbero non essere presenti o attivi in tutti i temi.
-   **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). A volte, la cache di PrestaShop impedisce la visualizzazione immediata di nuovi contenuti.
-   **Controlla gli stati degli ordini:** Assicurati di aver selezionato almeno uno "Stato degli ordini da visualizzare" che abbia ordini recenti associati. Se nessun ordine corrisponde agli stati selezionati, lo slider sarà vuoto.
-   **Compatibilità del tema:** Sebbene il modulo sia progettato per un'ampia compatibilità, temi molto personalizzati potrebbero richiedere piccole modifiche. Se tutto il resto fallisce, contatta il supporto MyPresta.eu.

**D2: Lo slider viene visualizzato, ma i colori non corrispondono al mio tema.**
R:

-   **Regola i colori nella configurazione:** Vai alla pagina di configurazione del modulo. Utilizza le impostazioni "Colore testo" e "Colore sfondo" per selezionare colori che completino il design del tuo negozio. Puoi utilizzare uno strumento di selezione colori (disponibile online o come estensioni del browser) per trovare i codici esadecimali esatti dal tuo tema.
-   **CSS personalizzato (Avanzato):** Se le opzioni di colore del modulo non sono sufficienti, il tuo webmaster può aggiungere regole CSS personalizzate al foglio di stile del tuo tema per sovrascrivere gli stili predefiniti del modulo. (Vedi Sezione 7.5 per i dettagli per gli sviluppatori).

**D3: Lo slider è vuoto o non si aggiorna con i nuovi ordini.**
R:

-   **Stati degli ordini:** Assicurati che l'impostazione "Stati degli ordini da visualizzare" includa gli stati dei tuoi ordini più recenti (ad esempio, "Pagamento accettato", "Consegnato"). Se i tuoi ordini recenti si trovano in uno stato non selezionato, non appariranno.
-   **Ordini recenti:** Il modulo visualizza gli ordini *recenti*. Se il tuo negozio non ha avuto ordini per un po', o se il "Numero di ordini da visualizzare" è impostato troppo basso, potrebbe apparire vuoto.
-   **Cache:** Ancora una volta, svuotare la cache di PrestaShop (**Parametri avanzati > Prestazioni**) può aiutare a garantire che il modulo recuperi i dati più recenti.

**D4: Come posso tradurre il testo nello slider in altre lingue?**
R:

-   **Strumento di traduzione di PrestaShop:** Vai su **Internazionale > Traduzioni**.
-   Seleziona "Traduzioni dei moduli installati", scegli il tuo tema e poi seleziona la tua lingua.
-   Trova il modulo "Slider ultimi ordini" nell'elenco. Potrai tradurre qualsiasi stringa hardcoded (come "ha appena comprato" o "da") che il modulo utilizza.
-   **Contenuto dinamico:** I nomi dei clienti, le città e i nomi dei prodotti vengono estratti direttamente dai dati del tuo negozio e appariranno nella lingua in cui sono stati inseriti o configurati nel tuo catalogo prodotti.

**D5: Lo slider è troppo veloce/lento o mostra troppi/pochi ordini.**
R:

-   **Velocità animazione:** Regola l'impostazione "Velocità animazione (millisecondi)" nella configurazione del modulo. Un numero più alto significa transizioni più lente.
-   **Numero di ordini:** Modifica l'impostazione "Numero di ordini da visualizzare" per controllare quanti ordini unici vengono ciclati. Sperimenta con questi valori per trovare l'equilibrio perfetto per il traffico e il volume degli ordini del tuo negozio.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce un'analisi tecnica approfondita del modulo "Slider ultimi ordini", destinata a sviluppatori, webmaster e agenzie tecniche.

### 4.1 Panoramica dell'architettura

Il modulo "Slider ultimi ordini" (`lastord`) è un modulo PrestaShop standard progettato principalmente per visualizzare contenuti dinamici nel front office. Sfrutta il sistema di hook di PrestaShop per iniettare il suo contenuto in varie parti del tema. La logica principale risiede nel file principale del modulo (`index.php`), che gestisce la configurazione, il recupero dei dati e il rendering del template. Non introduce controller personalizzati o ObjectModels complessi, affidandosi invece a query dirette al database (tramite `Db::getInstance()`) per recuperare i dati degli ordini e ai template Smarty per la presentazione. Lo stile è gestito tramite un file CSS dedicato.

### 4.2 Controller (`controllers/`)

Questo modulo **non** utilizza controller amministrativi personalizzati per il Front-Office o il Back-Office. Tutta la configurazione è gestita tramite il metodo `getContent()` all'interno del file principale del modulo, e il rendering del front-office viene eseguito direttamente tramite i metodi hook.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo **non** definisce classi o ObjectModels personalizzati all'interno della directory `classes/`. Tutti il recupero dei dati e la logica di business sono incapsulati all'interno della classe `Lastord` in `index.php`.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo **non** include file JavaScript personalizzati. La funzionalità di animazione e slider è probabilmente gestita da animazioni CSS o da uno script inline molto leggero all'interno del template, o da una libreria di terze parti già caricata da PrestaShop.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`lastord/views/css/lastord.css`**
    -   **Scopo:** Stile del front-office per il cliente.
    -   **Componenti UI principali e contenitori che stilizza:** Questo foglio di stile è responsabile dell'aspetto visivo della barra dello slider degli ordini stessa, inclusi il suo posizionamento, lo sfondo, gli stili del testo e potenzialmente le proprietà di animazione.
    -   **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere nel loro tema:**
        -   `.lastord_wrapper`: Il contenitore principale per l'intero slider.
        -   `.lastord_item`: Singolo elemento dell'ordine all'interno dello slider.
        -   `.lastord_text`: Il contenuto testuale (cliente, prodotto, città).
        -   `.lastord_image`: Il contenitore dell'immagine del prodotto.
        -   Regole `@keyframes` (se definite per l'animazione).
        Gli sviluppatori possono sovrascrivere questi selettori nel file `custom.css` o `theme.css` del loro tema per soddisfare i loro specifici requisiti di design.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**:

    -   **`lastord/views/templates/hook/lo_orders.tpl`**
        -   **Hook:** Questo è il template primario renderizzato dai metodi `hook` del modulo (ad esempio, `hookDisplayTop`, `hookDisplayNavFullWidth`, `hookDisplayFooter`, ecc.).
        -   **Scopo:** Contiene la struttura HTML per il wrapper dello slider e itera attraverso la variabile `$orders` (passata dalla logica PHP del modulo) per visualizzare ogni ordine recente. Include la logica condizionale per mostrare/nascondere il nome del cliente, la città, il nome del prodotto e l'immagine in base alla configurazione del modulo. Applica anche stili inline per i colori del testo e dello sfondo.
    -   **`lastord/views/templates/hook/displayBanner.tpl`**
        -   **Hook:** `displayBanner`
        -   **Scopo:** Questo template funge probabilmente da wrapper o punto di inclusione diretto per `lo_orders.tpl` quando il modulo è agganciato a `displayBanner`. Assicura che il contenuto dello slider sia renderizzato correttamente all'interno di questo hook specifico.
    -   **`lastord/views/templates/hook/displayNavFullWidth.tpl`**
        -   **Hook:** `displayNavFullWidth`
        -   **Scopo:** Simile a `displayBanner.tpl`, questo template viene utilizzato per renderizzare il contenuto di `lo_orders.tpl` quando il modulo è agganciato a `displayNavFullWidth`.
    -   **`lastord/views/templates/hook/displayTop.tpl`**
        -   **Hook:** `displayTop`
        -   **Scopo:** Questo template viene utilizzato per renderizzare il contenuto di `lo_orders.tpl` quando il modulo è agganciato a `displayTop`.
-   **Template amministrativi (`views/templates/admin/`)**:

    -   **`lastord/views/templates/admin/orderstates.tpl`**
        -   **Scopo:** Questo template viene utilizzato all'interno del metodo `getContent()` del modulo per renderizzare l'elenco delle caselle di controllo degli stati degli ordini nella pagina di configurazione del back-office. Itera attraverso gli stati degli ordini disponibili e li visualizza con il loro stato di selezione corrente.
-   **Template front-office (`views/templates/front/`)**: Nessuno identificato.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Questo modulo non crea tabelle SQL personalizzate.
    -   Memorizza le sue impostazioni di configurazione nella tabella `ps_configuration` utilizzando chiavi come `LASTORD_ENABLED`, `LASTORD_ORDERS_COUNT`, `LASTORD_ORDER_STATES`, `LASTORD_DISPLAY_NAME`, `LASTORD_DISPLAY_CITY`, `LASTORD_DISPLAY_PRODUCT`, `LASTORD_DISPLAY_IMAGE`, `LASTORD_ANIMATION_SPEED`, `LASTORD_TEXT_COLOR`, `LASTORD_BACKGROUND_COLOR`, `LASTORD_HOOK`.
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` del front office. | Utilizzato per registrare risorse (CSS) ed eventualmente JavaScript inline. |
| `displayTop` | Tipicamente nella parte superiore della pagina, sotto l'header. | Renderizza lo slider in una posizione superiore prominente. |
| `displayNavFullWidth` | Spesso una sezione a larghezza intera sopra o sotto la navigazione principale. | Renderizza lo slider in un'area di navigazione a larghezza intera. |
| `displayBanner` | Un hook comune per i banner, spesso nella parte superiore. | Renderizza lo slider come un banner. |
| `displayLeftColumn` | Nella barra laterale sinistra. | Renderizza lo slider nella colonna sinistra. |
| `displayRightColumn` | Nella barra laterale destra. | Renderizza lo slider nella colonna destra. |
| `displayFooter` | Nella sezione del footer della pagina. | Renderizza lo slider nella parte inferiore della pagina. |
| `displayProductButtons` | Nella pagina del prodotto, vicino al pulsante "aggiungi al carrello". | Renderizza lo slider nella pagina del prodotto per focalizzare la conversione. |
| `displayFooterProduct` | Nella sezione del footer della pagina del prodotto. | Renderizza lo slider nella parte inferiore della pagina del prodotto. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Slider ultimi ordini", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema tecnico o domanda tu possa avere riguardo alla funzionalità e all'integrazione del modulo.
