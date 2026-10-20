---
title: "Slider prodotti venduti di recente - Manuale per il commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Slider prodotti venduti di recente di MyPresta.eu."
sidebar:
  label: "Slider prodotti venduti di recente - Manuale per il commerciazione e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Recently sold products slider su MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/recently-sold-products-slider.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/sliders-slideshows/recently-sold-products-slider/)
>
> ---


# Slider prodotti venduti di recente

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per un'installazione PrestaShop e sono sufficienti per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo "Slider prodotti venduti di recente". Qui puoi personalizzare l'aspetto, il comportamento e il contenuto del tuo slider di prodotti.

#### **Colore di sfondo (rsps\_c\_bg)**

-   **Cosa fa questa impostazione:** Controlla il colore di sfondo dell'intero blocco dello slider.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su un colore (es. #FFFFFF per il bianco):* Lo sfondo dello slider verrà visualizzato in quel colore specifico, aiutandolo a fondersi o a distinguersi dal tuo tema.
    -   *Quando lasciato vuoto o non valido:* Lo slider potrebbe ereditare gli stili di sfondo dal tuo tema, o impostare un valore predefinito su uno sfondo trasparente.
-   **Valore consigliato:** Scegli un colore che si abbini al design del tuo negozio. Spesso, un colore tenue o uno che si abbini all'intestazione/piè di pagina è la scelta migliore.
-   **Scenario/esempio per il commerciante:** Se il tuo negozio ha un'intestazione scura, impostare questo colore su un grigio scuro o nero potrebbe far sembrare lo slider integrato. Se vuoi che risalti, un colore contrastante potrebbe funzionare.

#### **Colore del bordo (rsps\_c\_border)**

-   **Cosa fa questa impostazione:** Definisce il colore del bordo attorno all'intero blocco dello slider.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su un colore (es. #CCCCCC per il grigio chiaro):* Apparirà un bordo di quel colore attorno allo slider.
    -   *Quando lasciato vuoto o non valido:* Nessun bordo esplicito verrà applicato dal modulo, anche se il tuo tema potrebbe comunque aggiungerne uno.
-   **Valore consigliato:** Spesso, un bordo sottile che si abbini agli altri bordi del tuo tema o un bordo trasparente è la scelta migliore.
-   **Scenario/esempio per il commerciante:** Se il tuo sito utilizza bordi grigi sottili per altri elementi, impostare questo colore sullo stesso grigio manterrà la coerenza.

#### **Colore del carattere (rsps\_c\_font)**

-   **Cosa fa questa impostazione:** Imposta il colore del testo (nomi dei prodotti) visualizzato all'interno dello slider.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su un colore (es. #333333 per il grigio scuro):* I nomi dei prodotti appariranno nel colore scelto.
    -   *Quando lasciato vuoto o non valido:* Il colore del testo potrebbe impostare un valore predefinito sul colore del carattere generale del tuo tema.
-   **Valore consigliato:** Scegli un colore che fornisca un buon contrasto con il colore di sfondo dello slider per una migliore leggibilità.
-   **Scenario/esempio per il commerciante:** Se lo sfondo dello slider è scuro, sarà necessario un colore del carattere chiaro (come bianco o grigio chiaro) per la leggibilità.

#### **Spaziatura interna dello slider (rsps\_s\_padding)**

-   **Cosa fa questa impostazione:** Controlla la spaziatura interna (padding) tra il contenuto (testo) e i bordi del blocco dello slider.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su un valore (es. "10px"):* Il testo avrà 10 pixel di spazio su tutti i lati dal bordo dello slider.
    -   *Quando impostato su "0px" o vuoto:* Il testo si posizionerà direttamente contro i bordi dello slider.
-   **Valore consigliato:** "5px" o "10px" per dare al testo un po' di respiro e migliorare l'estetica.
-   **Scenario/esempio per il commerciante:** Se il tuo testo sembra troppo compresso, aumentare la spaziatura interna aggiungerà più spazio attorno ad esso, rendendolo più pulito.

#### **Dimensione del carattere dello slider (rsps\_s\_font)**

-   **Cosa fa questa impostazione:** Determina la dimensione del carattere utilizzato per i nomi dei prodotti nello slider.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su un valore (es. "14px"):* Il testo verrà visualizzato con quella specifica dimensione in pixel.
    -   *Quando lasciato vuoto o non valido:* La dimensione del carattere potrebbe impostare un valore predefinito sulla dimensione del carattere generale del tuo tema.
-   **Valore consigliato:** "14px" o "16px" per una buona leggibilità senza essere troppo grande o troppo piccolo.
-   **Scenario/esempio per il commerciante:** Se lo slider si trova in una posizione prominente come l'intestazione, un carattere leggermente più grande potrebbe essere appropriato. Per una barra laterale, un carattere più piccolo potrebbe adattarsi meglio.

#### **Bordo dello slider (rsps\_s\_border)**

-   **Cosa fa questa impostazione:** Definisce lo spessore e lo stile del bordo attorno al *contenuto interno* dello slider (l'area di testo scorrevole stessa), distinto dal bordo complessivo del blocco.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su un valore (es. "1px solid #CCCCCC"):* Apparirà un bordo grigio chiaro solido di 1 pixel attorno al testo scorrevole.
    -   *Quando lasciato vuoto o non valido:* Nessun bordo interno esplicito verrà applicato.
-   **Valore consigliato:** "0px" o "none" se desideri solo il bordo esterno del blocco. Se desideri una sottile separazione, "1px solid #EEEEEE" può funzionare.
-   **Scenario/esempio per il commerciante:** Potresti usarlo per creare una casella visiva distinta per il testo scorrevole all'interno dell'area più grande dello slider.

#### **Direzione del movimento (rsps\_m\_dir)**

-   **Cosa fa questa impostazione:** Controlla la direzione in cui i nomi dei prodotti scorrono all'interno dello slider.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su "left":* Il testo scorrerà da destra a sinistra.
    -   *Quando impostato su "right":* Il testo scorrerà da sinistra a destra.
-   **Valore consigliato:** "left" è una direzione di lettura comune e naturale per il testo scorrevole.
-   **Scenario/esempio per il commerciante:** La maggior parte degli utenti è abituata al testo che scorre a sinistra, quindi attenersi a "left" offre spesso la migliore esperienza utente.

#### **Ritardo del movimento (rsps\_m\_delay)**

-   **Cosa fa questa impostazione:** Determina la velocità dell'animazione di scorrimento. Questo è tipicamente misurato in millisecondi.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su un valore inferiore (es. "50"):* Il testo scorrerà più velocemente.
    -   *Quando impostato su un valore superiore (es. "100"):* Il testo scorrerà più lentamente.
-   **Valore consigliato:** "70" a "100" fornisce una velocità fluida e leggibile senza essere troppo veloce o troppo lenta.
-   **Scenario/esempio per il commerciante:** Se il testo è troppo veloce, i clienti non riescono a leggerlo. Se è troppo lento, potrebbe non attirare l'attenzione. Sperimenta per trovare un equilibrio.

#### **Posizione dello slider (rsps\_position)**

-   **Cosa fa questa impostazione:** Ti consente di selezionare l'hook di PrestaShop in cui lo slider verrà visualizzato nel tuo negozio.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su `displayHome`:* Lo slider apparirà sulla homepage del tuo negozio.
    -   *Quando impostato su `displayHeader`:* Lo slider apparirà nella sezione dell'intestazione di tutte le pagine.
    -   *Quando impostato su `displayFooter`:* Lo slider apparirà nella sezione del piè di pagina di tutte le pagine.
    -   *Altre opzioni (es. `displayLeftColumn`, `displayRightColumn`, `displayTop`):* Lo slider apparirà nella rispettiva colonna o sezione superiore.
-   **Valore consigliato:** `displayHeader` o `displayHome` per la massima visibilità, o `displayFooter` per un approccio più sottile.
-   **Scenario/esempio per il commerciante:** Se vuoi che ogni visitatore veda immediatamente le vendite recenti, scegli `displayHeader`. Se vuoi che faccia parte del contenuto della tua homepage, scegli `displayHome`.

#### **Numero di prodotti (rsps\_nb)**

-   **Cosa fa questa impostazione:** Specifica quanti prodotti venduti di recente devono essere recuperati e visualizzati nello slider.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su un numero inferiore (es. "5"):* Verranno mostrate solo le 5 vendite più recenti.
    -   *Quando impostato su un numero superiore (es. "20"):* Fino a 20 vendite recenti verranno incluse nell'elenco scorrevole.
-   **Valore consigliato:** "10" a "15" per garantire una buona varietà di prodotti senza rendere l'elenco eccessivamente lungo.
-   **Scenario/esempio per il commerciante:** Se il tuo negozio ha molte vendite, un numero più alto fornisce più prova sociale. Se le vendite sono meno frequenti, un numero inferiore potrebbe essere sufficiente.

#### **Ordina per (rsps\_order)**

-   **Cosa fa questa impostazione:** Determina i criteri di ordinamento per i prodotti visualizzati nello slider.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su "date\_add":* I prodotti verranno ordinati in base alla data in cui sono stati aggiunti all'ordine (i più recenti per primi).
    -   *Quando impostato su "product\_name":* I prodotti verranno ordinati alfabeticamente per nome.
    -   *Quando impostato su "price":* I prodotti verranno ordinati per prezzo.
-   **Valore consigliato:** "date\_add" per mostrare veramente gli articoli "venduti di recente".
-   **Scenario/esempio per il commerciante:** Per riflettere accuratamente gli acquisti recenti, l'ordinamento per `date_add` è la scelta più logica.

#### **Diversità (rsps\_diversity)**

-   **Cosa fa questa impostazione:** Questa impostazione controlla se lo slider deve mostrare prodotti unici o consentire che lo stesso prodotto appaia più volte se è stato venduto di recente.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (es. "Sì" o "1"):* Se lo stesso prodotto è stato venduto più volte, apparirà solo una volta nell'elenco dei prodotti da visualizzare, garantendo una maggiore varietà di articoli.
    -   *Quando disabilitato (es. "No" o "0"):* Lo stesso prodotto potrebbe apparire più volte nello slider se faceva parte di diversi ordini recenti.
-   **Valore consigliato:** "Sì" (o "1") per mostrare una gamma più ampia del tuo catalogo e impedire che lo slider diventi ripetitivo.
-   **Scenario/esempio per il commerciante:** Se vendi un articolo molto popolare, disabilitare la diversità potrebbe significare che lo slider mostra solo quell'articolo ripetutamente. Abilitandolo si assicura che altri prodotti abbiano la possibilità di essere visti.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | **Colore di sfondo** (rsps\_c\_bg) | `#FFFFFF` (Bianco) | Imposta il colore di sfondo del blocco dello slider. |
| Configurazione modulo | **Colore del bordo** (rsps\_c\_border) | `#CCCCCC` (Grigio chiaro) | Imposta il colore del bordo attorno al blocco dello slider. |
| Configurazione modulo | **Colore del carattere** (rsps\_c\_font) | `#333333` (Grigio scuro) | Imposta il colore del testo dei nomi dei prodotti. |
| Configurazione modulo | **Spaziatura interna dello slider** (rsps\_s\_padding) | `10px` | Spaziatura interna attorno al testo all'interno dello slider. |
| Configurazione modulo | **Dimensione del carattere dello slider** (rsps\_s\_font) | `14px` | Dimensione del carattere per i nomi dei prodotti. |
| Configurazione modulo | **Bordo dello slider** (rsps\_s\_border) | `0px` | Bordo attorno all'area di testo scorrevole stessa. |
| Configurazione modulo | **Direzione del movimento** (rsps\_m\_dir) | `left` | Direzione dell'animazione di scorrimento (sinistra o destra). |
| Configurazione modulo | **Ritardo del movimento** (rsps\_m\_delay) | `70` | Velocità dell'animazione di scorrimento (inferiore = più veloce). |
| Configurazione modulo | **Posizione dello slider** (rsps\_position) | `displayHeader` | Hook di PrestaShop in cui verrà visualizzato lo slider. |
| Configurazione modulo | **Numero di prodotti** (rsps\_nb) | `10` | Numero massimo di prodotti venduti di recente da mostrare. |
| Configurazione modulo | **Ordina per** (rsps\_order) | `date_add` | Criteri di ordinamento per i prodotti visualizzati. |
| Configurazione modulo | **Diversità** (rsps\_diversity) | `Sì` (1) | Assicura che vengano mostrati prodotti unici (previene la ripetizione). |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho configurato il modulo, ma lo slider non appare nel mio negozio.**
**R1:**

-   **Controlla la posizione dell'hook:** Vai su **Design > Posizioni** nel tuo Back Office di PrestaShop. Cerca l'hook che hai selezionato nell'impostazione "Posizione dello slider" del modulo (es. `displayHeader`, `displayHome`). Assicurati che il modulo "Slider prodotti venduti di recente" sia elencato e abilitato in quell'hook. In caso contrario, potresti dover "Trapiantare un modulo" nell'hook corretto.
-   **Svuota la cache:** PrestaShop spesso memorizza i contenuti nella cache. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" in alto a destra.
-   **Modulo abilitato:** Ricontrolla che il modulo sia abilitato in **Moduli > Gestione moduli**.
-   **Vendite recenti:** Assicurati di avere effettivamente vendite recenti nel tuo negozio. Il modulo si basa sui dati degli ordini esistenti.

**D2: Lo slider viene visualizzato, ma i colori o le dimensioni dei caratteri non sono quelli che ho impostato.**
**R2:**

-   **Svuota la cache:** Questa è la ragione più comune per i problemi di stile. Svuota la cache di PrestaShop (**Parametri avanzati > Prestazioni**) e la cache del tuo browser (Ctrl+F5 o Cmd+R).
-   **Sovrascritture del tema:** Il tuo tema PrestaShop potrebbe avere il proprio CSS che sta sovrascrivendo gli stili del modulo. Potrebbe essere necessario ispezionare l'elemento utilizzando gli strumenti di sviluppo del tuo browser (F12) per vedere quali regole CSS vengono applicate. Se si tratta di un conflitto del tema, potrebbe essere necessario aggiungere CSS personalizzato al tuo tema per forzare gli stili del modulo.
-   **Input corretto:** Assicurati di utilizzare codici colore CSS validi (es. `#RRGGBB` o `rgba(R,G,B,A)`) e valori in pixel (es. `14px`) nella configurazione del modulo.

**D3: Il testo scorre troppo velocemente/lentamente, o è difficile da leggere.**
**R3:**

-   **Ritardo del movimento:** Regola l'impostazione "Ritardo del movimento". Un numero più alto lo rende più lento, un numero più basso lo rende più veloce. Sperimenta finché non trovi una velocità di lettura confortevole.
-   **Dimensione del carattere e contrasto:** Assicurati che la "Dimensione del carattere dello slider" sia adeguata e che il tuo "Colore del carattere" abbia un buon contrasto con il tuo "Colore di sfondo".
-   **Numero di prodotti:** Se hai troppi prodotti e una velocità molto elevata, potrebbe essere eccessivo. Riduci il "Numero di prodotti" o rallenta il "Ritardo del movimento".

**D4: Posso tradurre il testo "Qualcuno ha appena acquistato..." in altre lingue?**
**R4:** Sì, i moduli PrestaShop sono tipicamente traducibili.

-   Vai su **Internazionale > Traduzioni** nel tuo Back Office.
-   Seleziona "Traduzioni dei moduli installati" per il "Tipo di traduzione".
-   Scegli il tuo tema.
-   Seleziona la lingua che desideri tradurre.
-   Trova il modulo "Slider prodotti venduti di recente" nell'elenco e dovresti essere in grado di modificare le stringhe traducibili.

**D5: Lo slider appare bene su desktop ma è rotto o mal formattato su mobile.**
**R5:**

-   **Svuota la cache:** Inizia sempre svuotando la cache di PrestaShop e del browser.
-   **Reattività del tema:** Sebbene il modulo stesso sia progettato per essere reattivo, possono verificarsi conflitti con il CSS reattivo specifico del tuo tema.
-   **Controlla spaziatura interna/bordi:** Un'eccessiva spaziatura interna o bordi potrebbero spingere il contenuto fuori dalla vista su schermi più piccoli. Prova a ridurre temporaneamente "Spaziatura interna dello slider" o "Bordo dello slider" per vedere se risolve il problema.
-   **Ispeziona su mobile:** Utilizza gli strumenti di sviluppo del tuo browser (F12) e passa alla visualizzazione mobile, oppure testa direttamente su un dispositivo mobile, per diagnosticare problemi specifici di layout. Potrebbe essere necessario un CSS personalizzato nel tuo tema per adattarsi al mobile se esiste un conflitto.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata del modulo "Slider prodotti venduti di recente" per sviluppatori, webmaster e agenzie tecniche.

### 4.1 Panoramica dell'architettura

Il modulo "Slider prodotti venduti di recente" (`recentlysoldproducts`) segue un'architettura standard dei moduli PrestaShop. È un modulo a file singolo (`recentlysoldproducts.php`) che estende `Module`, gestendo la propria installazione, disinstallazione, configurazione (`getContent()`) e visualizzazione front-office tramite hook. Sfrutta la classe `Configuration` di PrestaShop per l'archiviazione delle impostazioni e Smarty per la creazione di modelli. La funzionalità front-office è principalmente guidata da JavaScript per l'animazione di scorrimento e lo stile.

### 4.2 Controller (`controllers/`)

Questo modulo **non** contiene alcun controller amministrativo Front-Office o Back-Office dedicato. Tutta la configurazione è gestita all'interno del metodo `getContent()` del file principale del modulo e il rendering front-office è gestito direttamente tramite gli hook di PrestaShop.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo **non** contiene classi personalizzate o definizioni di `ObjectModel` in una directory `classes/`. Interroga direttamente il database di PrestaShop per le informazioni su ordini e prodotti all'interno del file principale del modulo.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`recentlysoldproducts/jscolor/jscolor.js`**

    -   **Ambito:** Back-office (utilizzato in `getContent()` per i selettori di colore).
    -   **Descrizione:** Questa è una libreria JavaScript di terze parti che fornisce un'interfaccia di selezione del colore user-friendly per i campi di input. È integrata nel modulo di configurazione del modulo per consentire ai commercianti di selezionare facilmente i colori per lo sfondo, il bordo e il carattere dello slider. Tipicamente funziona aggiungendo una classe (es. `jscolor`) a un campo di input, che lo trasforma in un selettore di colore.
-   **`recentlysoldproducts/js/script.js`**

    -   **Ambito:** Front-office.
    -   **Descrizione:** Questo file contiene probabilmente la logica principale per l'animazione di scorrimento dello slider. Tipicamente:
        -   Seleziona l'elemento contenitore dello slider (es. per ID o classe).
        -   Inizializza le variabili per la direzione del movimento, la velocità e il contenuto.
        -   Implementa un ciclo di animazione di scorrimento continuo, potenzialmente utilizzando `setInterval` o `requestAnimationFrame`.
        -   Gestisce la clonazione degli elementi per creare un effetto di loop infinito.
        -   Si adatta alla reattività o alle pause al passaggio del mouse.
-   **`recentlysoldproducts/recentlysoldproducts.js`**

    -   **Ambito:** Front-office.
    -   **Descrizione:** Questo file potrebbe contenere JavaScript aggiuntivo per il front-office specifico per l'inizializzazione o l'interazione del modulo. Potrebbe essere responsabile di:
        -   Caricare dinamicamente il contenuto dello slider (anche se in questo modulo, è probabile che venga renderizzato da Smarty).
        -   Impostare i listener di eventi (es. per mettere in pausa lo slider al passaggio del mouse).
        -   Assicurarsi che lo slider si inizializzi correttamente dopo che il DOM è pronto.
        -   Potenzialmente gestire AJAX se il modulo dovesse recuperare dati in modo asincrono (anche se non esplicitamente indicato dalla struttura del modulo).

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`recentlysoldproducts/css.css`**

    -   **Ambito:** Front-office.
    -   **Descrizione:** Questo è probabilmente il foglio di stile principale per la visualizzazione front-office dello slider. Definirebbe:
        -   Layout e posizionamento del contenitore dello slider.
        -   Stili di base per gli elementi di testo scorrevoli (es. `font-size`, `color`, `padding`).
        -   Stili per lo sfondo e i bordi basati sulla configurazione del modulo.
        -   Potenziali aggiustamenti reattivi per diverse dimensioni dello schermo.
        -   Selettori chiave: `.recentlysoldproducts_block`, `.recentlysoldproducts_item`, ecc.
-   **`recentlysoldproducts/recentlysoldproducts.css`**

    -   **Ambito:** Front-office.
    -   **Descrizione:** Questo file potrebbe contenere regole di stile aggiuntive o specifiche, potenzialmente per effetti visivi più avanzati o per sovrascrivere gli stili predefiniti del tema. Dato il nome, potrebbe anche essere un file ridondante o legacy, o contenere stili più specifici per il meccanismo di scorrimento stesso, distinti dallo stile generale del blocco in `css.css`. Gli sviluppatori dovrebbero verificare la presenza di regole sovrapposte e potenziali conflitti.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **`recentlysoldproducts/views/front/rsps.tpl`**
    -   **Ambito:** Front-office (template hook).
    -   **Descrizione:** Questo è il file di template principale responsabile del rendering della struttura HTML dello slider dei prodotti venduti di recente.
    -   **Renderizzato negli hook:** `rightColumn`, `displayrightColumn`, `home`, `top`, `displayleftColumn`, `footer`, `displayhome`, `displayheader`, `displaytop`, `displayfooter`, `header`, `leftColumn`.
    -   **Contenuto:** Riceve dati (es. un elenco di prodotti venduti di recente, impostazioni di configurazione del modulo) dai metodi `hookDisplay*` in `recentlysoldproducts.php`. Quindi itera attraverso l'elenco dei prodotti per generare il testo scorrevole, applicando stili o classi in linea in base alle impostazioni di configurazione del modulo (colori, dimensioni dei caratteri, spaziatura interna, ecc.). Conterrà il wrapper HTML principale per lo slider e le singole voci di prodotto.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Questo modulo non crea tabelle di database personalizzate.
    -   Memorizza le sue impostazioni di configurazione nella tabella `ps_configuration` di PrestaShop. Le chiavi utilizzate sono:
        -   `RSPS_C_BG`
        -   `RSPS_C_BORDER`
        -   `RSPS_C_FONT`
        -   `RSPS_S_PADDING`
        -   `RSPS_S_FONT`
        -   `RSPS_S_BORDER`
        -   `RSPS_M_DIR`
        -   `RSPS_M_DELAY`
        -   `RSPS_POSITION`
        -   `RSPS_NB`
        -   `RSPS_ORDER`
        -   `RSPS_DIVERSITY`
    -   Interroga le tabelle PrestaShop esistenti, principalmente `ps_orders`, `ps_order_detail`, `ps_product_lang` e `ps_product` per recuperare le informazioni sui prodotti venduti di recente.
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempistica e posizione dell'esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Registra risorse CSS/JS e potenzialmente renderizza un elemento nascosto per l'inizializzazione JS. |
| `header` | Alias per `displayHeader` nelle versioni precedenti di PrestaShop. | Come `displayHeader`. |
| `displayHome` | Sulla homepage, di solito nell'area del contenuto principale. | Renderizza il blocco dello slider sulla homepage del negozio. |
| `home` | Alias per `displayHome` nelle versioni precedenti di PrestaShop. | Come `displayHome`. |
| `displayTop` | Nella sezione superiore della pagina, spesso sotto l'intestazione. | Renderizza il blocco dello slider nell'area del contenuto superiore. |
| `top` | Alias per `displayTop` nelle versioni precedenti di PrestaShop. | Come `displayTop`. |
| `displayLeftColumn` | Nella barra laterale sinistra delle pagine applicabili. | Renderizza il blocco dello slider nella colonna sinistra. |
| `leftColumn` | Alias per `displayLeftColumn` nelle versioni precedenti di PrestaShop. | Come `displayLeftColumn`. |
| `displayRightColumn` | Nella barra laterale destra delle pagine applicabili. | Renderizza il blocco dello slider nella colonna destra. |
| `rightColumn` | Alias per `displayRightColumn` nelle versioni precedenti di PrestaShop. | Come `displayRightColumn`. |
| `displayFooter` | Nella sezione del piè di pagina di ogni pagina. | Renderizza il blocco dello slider nel piè di pagina. |
| `footer` | Alias per `displayFooter` nelle versioni precedenti di PrestaShop. | Come `displayFooter`. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Slider prodotti venduti di recente", fai riferimento al tuo account cliente su MyPresta.eu. Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere.
