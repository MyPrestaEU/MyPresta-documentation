---
title: "Immagini prodotto nelle schede prodotto - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Immagini prodotto nelle schede prodotto' di MyPresta.eu."
sidebar:
  label: "Immagini prodotto nelle schede prodotto - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Product pictures on product listings su MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-pictures-on-product-listings.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/product-pictures-on-product-listings/)
>
> ---


# Immagini prodotto nelle schede prodotto

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono richieste per PrestaShop stesso e generalmente disponibili su tutti gli ambienti di hosting moderni.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo "Immagini prodotto nelle schede prodotto". Puoi accedervi navigando su **Moduli > Gestione moduli** e cliccando su "Configura" accanto al nome del modulo.

#### **Posizione del modulo**

-   **Cosa fa questa impostazione:** Determina dove appariranno le immagini aggiuntive del prodotto rispetto all'immagine principale del prodotto nelle pagine di elenco.
-   **Effetto della modifica di questa impostazione:**
    -   *displayProductAdditionalInfo:* Le immagini appariranno in un hook comune spesso utilizzato per dettagli extra del prodotto.
    -   *displayAfterProductThumbs:* Le immagini appariranno immediatamente dopo le miniature dell'immagine principale del prodotto (se il tuo tema le visualizza).
    -   *displayFooterProduct:* Le immagini appariranno nella sezione del piè di pagina del blocco prodotto nella pagina di elenco.
    -   *displayProductDeliveryTime:* Le immagini appariranno vicino alle informazioni sul tempo di consegna (se il tuo tema le visualizza).
    -   *displayHeader:* Questa è una posizione meno comune per le immagini del prodotto nelle pagine di elenco e potrebbe richiedere uno stile personalizzato per apparire bene.
    -   *displayProductListReviews:* Le immagini appariranno vicino alle stelle o al conteggio delle recensioni del prodotto (se il tuo tema le visualizza).
-   **Valore consigliato:** Sperimenta prima con `displayProductAdditionalInfo` o `displayAfterProductThumbs`, poiché queste sono tipicamente buone posizioni visive.
-   **Scenario / esempio del commerciante:** Se il tuo tema ha un layout pulito e desideri che le immagini siano sottilmente integrate sotto l'immagine principale, `displayProductAdditionalInfo` potrebbe essere la scelta migliore. Se desideri che si distinguano di più, `displayFooterProduct` potrebbe funzionare.

#### **Design del modulo**

-   **Cosa fa questa impostazione:** Ti consente di scegliere tra diversi stili visivi per l'output del modulo, influenzando principalmente il modo in cui vengono presentate le miniature.
-   **Effetto della modifica di questa impostazione:**
    -   *Tema classico:* Applica uno stile spesso compatibile con temi PrestaShop più vecchi o temi che imitano l'aspetto classico.
    -   *Universale:* Applica un design più moderno e reattivo che mira a funzionare bene su una più ampia gamma di temi contemporanei.
-   **Valore consigliato:** `Universale` per la maggior parte dei negozi PrestaShop moderni (1.7.x, 8.x, 9.x). Usa `Tema classico` se hai un tema più vecchio o altamente personalizzato che non rende `Universale` correttamente.
-   **Scenario / esempio del commerciante:** Se il tuo negozio utilizza un tema PrestaShop 8 predefinito, `Universale` si integrerà probabilmente senza problemi. Se sei su PrestaShop 1.6 con un tema personalizzato, `Tema classico` potrebbe essere una scommessa più sicura.

#### **Metodo di visualizzazione**

-   **Cosa fa questa impostazione:** Controlla quali immagini aggiuntive vengono visualizzate per ogni prodotto nella pagina di elenco.
-   **Effetto della modifica di questa impostazione:**
    -   *Immagini per combinazioni di colori:* Visualizza solo le immagini specificamente collegate agli attributi di colore di un prodotto. Utile per la moda o prodotti con varianti di colore distinte.
    -   *Immagini per ogni combinazione:* Visualizza le immagini per tutte le combinazioni di prodotto (ad esempio, taglia, colore, materiale). Questo può portare a molte immagini se hai molte combinazioni.
    -   *Tutte le immagini del prodotto:* Visualizza tutte le immagini associate al prodotto, indipendentemente dalla combinazione. Questa è l'opzione più completa.
-   **Valore consigliato:** `Tutte le immagini del prodotto` per la maggior parte dei prodotti generici. `Immagini per combinazioni di colori` se i tuoi prodotti si basano fortemente su variazioni di colore e desideri mantenere il numero di immagini gestibile.
-   **Scenario / esempio del commerciante:** Per un negozio di abbigliamento, selezionando `Immagini per combinazioni di colori` verrebbero mostrati tutti i colori disponibili per una specifica t-shirt. Per un negozio di mobili, `Tutte le immagini del prodotto` mostrerebbe diverse angolazioni e primi piani di un divano.

#### **Solo in magazzino**

-   **Cosa fa questa impostazione:** Questa opzione filtra le immagini visualizzate in base alla disponibilità di magazzino del prodotto.
-   **Effetto della modifica di questa impostazione:**
    -   *Abilitato:* Visualizza solo le immagini per le combinazioni di prodotto attualmente in magazzino. Se un colore specifico è esaurito, le sue immagini associate non appariranno.
    -   *Disabilitato:* Visualizza tutte le immagini selezionate, indipendentemente dallo stato del magazzino.
-   **Valore consigliato:** `Abilitato` per evitare di mostrare ai clienti immagini di prodotti che non possono acquistare immediatamente, il che può portare a frustrazione.
-   **Scenario / esempio del commerciante:** Se vendi scarpe e una particolare combinazione taglia/colore è esaurita, abilitando questa opzione si impedisce ai clienti di vedere le immagini di quella specifica variante, guidandoli verso le opzioni disponibili.

#### **Visualizza caselle colore invece di immagini**

-   **Cosa fa questa impostazione:** Invece di mostrare piccole miniature di immagini, questa opzione visualizza campioni di colore (caselle) per le combinazioni di prodotto.
-   **Effetto della modifica di questa impostazione:**
    -   *Abilitato:* Sostituisce le miniature delle immagini con piccole caselle di colore, tipicamente utilizzando il colore definito per l'attributo del prodotto.
    -   *Disabilitato:* Visualizza le miniature delle immagini reali.
-   **Valore consigliato:** `Disabilitato` se desideri mostrare immagini reali del prodotto. `Abilitato` se i tuoi prodotti hanno attributi di colore chiari e preferisci un aspetto più pulito e compatto per la selezione del colore.
-   **Scenario / esempio del commerciante:** Per un negozio di vernici, abilitando questa opzione verrebbero mostrati piccoli quadrati colorati che rappresentano diversi colori di vernice, il che è più efficiente che mostrare una piccola immagine di ogni colore.

#### **Contenitore principale del prodotto nell'elenco dei prodotti**

-   **Cosa fa questa impostazione:** Questa è un'impostazione tecnica per aiutare il modulo a identificare il contenitore principale per ogni prodotto nelle tue pagine di elenco. Richiede un selettore CSS.
-   **Effetto della modifica di questa impostazione:** Se impostato in modo errato, il modulo potrebbe non essere in grado di trovare dove iniettare le immagini aggiuntive, o potrebbe iniettarle nel posto sbagliato.
-   **Valore consigliato:** Questo dipende interamente dal tuo tema. I valori comuni sono `.product-miniature`, `.product-container` o `.ajax_block_product`. Potrebbe essere necessario ispezionare l'HTML del tuo tema per trovare il selettore corretto.
-   **Scenario / esempio del commerciante:** Se il tuo tema utilizza `<div class="product-item">` per ogni prodotto, dovresti inserire `.product-item` qui.

#### **CSS immagine di copertina del prodotto**

-   **Cosa fa questa impostazione:** Questa è un'impostazione tecnica per aiutare il modulo a identificare l'elemento immagine principale del prodotto all'interno di ogni contenitore di prodotto. Richiede un selettore CSS.
-   **Effetto della modifica di questa impostazione:** Se impostato in modo errato, il modulo non sarà in grado di cambiare l'immagine principale del prodotto quando viene cliccata/passata con il mouse una miniatura.
-   **Valore consigliato:** Questo dipende dal tuo tema. I valori comuni sono `.product-thumbnail`, `.img-fluid` o `img.replace-me`. Potrebbe essere necessario ispezionare l'HTML del tuo tema.
-   **Scenario / esempio del commerciante:** Se l'immagine principale del prodotto del tuo tema ha la classe `product-image-thumb`, dovresti inserire `.product-image-thumb` qui.

#### **CSS ancora immagine di copertina del prodotto**

-   **Cosa fa questa impostazione:** Questa è un'impostazione tecnica per aiutare il modulo a identificare il link (tag `<a>`) che avvolge l'immagine principale del prodotto. Questo è importante per garantire che il link funzioni ancora correttamente dopo il cambio di immagine.
-   **Effetto della modifica di questa impostazione:** Se impostato in modo errato, cliccando sull'immagine principale del prodotto potrebbe non portare alla pagina del prodotto, o il cambio di immagine potrebbe fallire.
-   **Valore consigliato:** Questo dipende dal tuo tema. I valori comuni sono `.product-thumbnail a`, `.product-image a` o `a.product-cover`. Potrebbe essere necessario ispezionare l'HTML del tuo tema.
-   **Scenario / esempio del commerciante:** Se il tuo tema avvolge l'immagine principale del prodotto in `<a class="product-link">`, dovresti inserire `a.product-link` qui.

#### **Ancora titolo prodotto**

-   **Cosa fa questa impostazione:** Questa è un'impostazione tecnica per identificare il link (tag `<a>`) attorno al titolo del prodotto.
-   **Effetto della modifica di questa impostazione:** Questa impostazione aiuta il modulo a garantire che il link del titolo del prodotto rimanga funzionale e punti correttamente alla pagina del prodotto.
-   **Valore consigliato:** Questo dipende dal tuo tema. I valori comuni sono `.product-title a`, `.product-name a` o `h3 a`. Potrebbe essere necessario ispezionare l'HTML del tuo tema.
-   **Scenario / esempio del commerciante:** Se i titoli dei tuoi prodotti sono avvolti in `<h3 class="product-name"><a href="...">`, dovresti inserire `h3.product-name a` qui.

#### **Classe aggiuntiva per l'ancora miniatura**

-   **Cosa fa questa impostazione:** Ti consente di aggiungere una classe CSS extra ai tag `<a>` delle immagini in miniatura visualizzate dal modulo. Questo è utile per lo stile personalizzato.
-   **Effetto della modifica di questa impostazione:** La classe specificata verrà aggiunta all'HTML dei link delle immagini in miniatura, consentendoti di indirizzarli con regole CSS personalizzate nel tuo tema.
-   **Valore consigliato:** Lascia vuoto a meno che tu non abbia requisiti specifici di stile personalizzato.
-   **Scenario / esempio del commerciante:** Se desideri aggiungere un bordo speciale alle tue immagini in miniatura, potresti inserire `my-custom-miniature-class` qui, quindi aggiungere CSS come `.my-custom-miniature-class img { border: 1px solid blue; }` al tuo tema.

#### **Metodo di cambio immagine**

-   **Cosa fa questa impostazione:** Controlla come cambia l'immagine principale del prodotto quando un cliente interagisce con le miniature aggiuntive.
-   **Effetto della modifica di questa impostazione:**
    -   *Al click:* L'immagine principale cambia solo quando un cliente clicca su una miniatura.
    -   *Al passaggio del mouse:* L'immagine principale cambia quando un cliente sposta il cursore del mouse su una miniatura (senza cliccare).
    -   *Slider:* Il modulo visualizza un piccolo slider con frecce di navigazione, consentendo ai clienti di scorrere le immagini. Questo spesso implica un comportamento "al click" per i controlli dello slider.
-   **Valore consigliato:** `Al passaggio del mouse` per un'esperienza rapida e interattiva. `Al click` se preferisci un'azione utente esplicita. `Slider` se hai molte immagini e desideri una presentazione più compatta.
-   **Scenario / esempio del commerciante:** Per un negozio di moda, `Al passaggio del mouse` consente ai clienti di visualizzare rapidamente diverse anteprime. Per un prodotto con molte immagini dettagliate, `Slider` può mantenere pulita la pagina di elenco pur offrendo pieno accesso a tutti gli elementi visivi.

#### **Immagini per combinazioni di colori (impostazione duplicata, probabilmente un bug o legacy)**

-   **Cosa fa questa impostazione:** Sembra essere un duplicato dell'impostazione "Metodo di visualizzazione", specificamente correlata alla visualizzazione di immagini per combinazioni di colori.
-   **Effetto della modifica di questa impostazione:** È meglio fare affidamento sull'impostazione "Metodo di visualizzazione" per questa funzionalità. Se questo è un controllo separato, potrebbe sovrascrivere o entrare in conflitto con l'impostazione "Metodo di visualizzazione".
-   **Valore consigliato:** Assicurare la coerenza con l'impostazione "Metodo di visualizzazione".
-   **Scenario / esempio del commerciante:** Se "Metodo di visualizzazione" è impostato su "Immagini per combinazioni di colori", anche questa impostazione dovrebbe essere abilitata o coerente.

#### **Immagini per ogni combinazione (impostazione duplicata, probabilmente un bug o legacy)**

-   **Cosa fa questa impostazione:** Similmente a quanto sopra, sembra essere un duplicato dell'impostazione "Metodo di visualizzazione", specificamente correlata alla visualizzazione di immagini per tutte le combinazioni.
-   **Effetto della modifica di questa impostazione:** È meglio fare affidamento sull'impostazione "Metodo di visualizzazione".
-   **Valore consigliato:** Assicurare la coerenza con l'impostazione "Metodo di visualizzazione".
-   **Scenario / esempio del commerciante:** Se "Metodo di visualizzazione" è impostato su "Immagini per ogni combinazione", anche questa impostazione dovrebbe essere abilitata o coerente.

#### **Tutte le immagini del prodotto (impostazione duplicata, probabilmente un bug o legacy)**

-   **Cosa fa questa impostazione:** Similmente a quanto sopra, sembra essere un duplicato dell'impostazione "Metodo di visualizzazione", specificamente correlata alla visualizzazione di tutte le immagini del prodotto.
-   **Effetto della modifica di questa impostazione:** È meglio fare affidamento sull'impostazione "Metodo di visualizzazione".
-   **Valore consigliato:** Assicurare la coerenza con l'impostazione "Metodo di visualizzazione".
-   **Scenario / esempio del commerciante:** Se "Metodo di visualizzazione" è impostato su "Tutte le immagini del prodotto", anche questa impostazione dovrebbe essere abilitata o coerente.

#### **Tabella di riferimento rapido della configurazione**

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Posizione del modulo | `displayProductAdditionalInfo` | Determina dove appaiono le immagini aggiuntive nelle schede prodotto. |
| Configurazione modulo | Design del modulo | `Universale` | Imposta lo stile visivo per le miniature delle immagini (Classico vs. Moderno). |
| Configurazione modulo | Metodo di visualizzazione | `Tutte le immagini del prodotto` | Controlla quali immagini vengono mostrate (combinazioni di colori, tutte le combinazioni o tutte le immagini del prodotto). |
| Configurazione modulo | Solo in magazzino | `Abilitato` | Filtra le immagini per mostrare solo quelle per le combinazioni di prodotto in magazzino. |
| Configurazione modulo | Visualizza caselle colore invece di immagini | `Disabilitato` | Sostituisce le miniature delle immagini con campioni di colore se abilitato. |
| Configurazione modulo | Contenitore principale del prodotto nell'elenco dei prodotti | `.product-miniature` (o specifico del tema) | Selettore CSS per il blocco principale del prodotto nelle pagine di elenco. |
| Configurazione modulo | CSS immagine di copertina del prodotto | `.product-thumbnail` (o specifico del tema) | Selettore CSS per l'elemento immagine principale del prodotto. |
| Configurazione modulo | CSS ancora immagine di copertina del prodotto | `.product-thumbnail a` (o specifico del tema) | Selettore CSS per il link che avvolge l'immagine principale del prodotto. |
| Configurazione modulo | Ancora titolo prodotto | `h3 a` (o specifico del tema) | Selettore CSS per il link che avvolge il titolo del prodotto. |
| Configurazione modulo | Classe aggiuntiva per l'ancora miniatura | Lascia vuoto | Aggiunge una classe CSS personalizzata ai link delle immagini in miniatura per lo stile. |
| Configurazione modulo | Metodo di cambio immagine | `Al passaggio del mouse` | Definisce come cambia l'immagine principale (click, passaggio del mouse o slider). |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Le immagini aggiuntive non vengono visualizzate nelle mie schede prodotto.**

-   **R:** Innanzitutto, controlla la configurazione del tuo modulo:
    -   Assicurati che "Posizione del modulo" sia impostato su un hook che il tuo tema effettivamente renderizza (ad esempio, `displayProductAdditionalInfo`). Se il tuo tema è fortemente personalizzato, potresti dover provare diverse posizioni o consultare uno sviluppatore.
    -   Verifica le impostazioni "Contenitore principale del prodotto nell'elenco dei prodotti", "CSS immagine di copertina del prodotto", "CSS ancora immagine di copertina del prodotto" e "Ancora titolo prodotto". Questi sono selettori CSS cruciali che devono corrispondere alla struttura HTML del tuo tema. Usa gli strumenti per sviluppatori del tuo browser (F12) per ispezionare gli elementi nella tua pagina di categoria e trovare le classi/ID corretti.
    -   Assicurati che i prodotti abbiano effettivamente più immagini caricate nelle loro impostazioni di prodotto nel Back Office.
-   **R:** Svuota la cache di PrestaShop: Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" in alto a destra. Inoltre, svuota la cache del tuo browser.

**D2: Le immagini appaiono, ma non cambiano quando passo il mouse/clicco.**

-   **R:** Questo di solito indica un problema con i selettori CSS per l'immagine principale del prodotto o il suo contenitore.
    -   Ricontrolla "CSS immagine di copertina del prodotto" e "CSS ancora immagine di copertina del prodotto". Questi devono puntare accuratamente all'immagine principale e al suo link di avvolgimento.
    -   Assicurati che non ci siano errori JavaScript nella tua pagina che potrebbero impedire l'esecuzione dello script del modulo. Controlla la console per sviluppatori del tuo browser (F12 > scheda Console).
    -   Se hai altri moduli che modificano le schede prodotto, potrebbe esserci un conflitto. Prova a disabilitare temporaneamente altri moduli del front-office per isolare il problema.

**D3: Le immagini appaiono distorte o lo stile è sbagliato.**

-   **R:**
    -   Prova a cambiare l'impostazione "Design del modulo" tra `Tema classico` e `Universale` per vedere se uno si integra meglio con il tuo tema.
    -   Il tuo tema potrebbe avere regole CSS in conflitto. Puoi usare l'impostazione "Classe aggiuntiva per l'ancora miniatura" per aggiungere una classe personalizzata, quindi usare CSS personalizzato nel tuo tema per sovrascrivere gli stili in conflitto.
    -   Assicurati che le immagini dei prodotti caricate siano di qualità e rapporto d'aspetto coerenti.

**D4: Sto usando un tema personalizzato e il modulo non sembra funzionare affatto.**

-   **R:** I temi personalizzati spesso utilizzano strutture HTML e classi CSS diverse dai temi PrestaShop predefiniti.
    -   Sarà quasi certamente necessario regolare i selettori CSS per "Contenitore principale del prodotto nell'elenco dei prodotti", "CSS immagine di copertina del prodotto", "CSS ancora immagine di copertina del prodotto" e "Ancora titolo prodotto" per corrispondere al markup specifico del tuo tema. Questo di solito richiede una conoscenza di base dell'ispezione HTML/CSS utilizzando gli strumenti per sviluppatori del browser.
    -   Il tuo tema personalizzato potrebbe non richiamare gli hook standard di PrestaShop utilizzati dal modulo. Potrebbe essere necessario aggiungere manualmente le chiamate agli hook del modulo ai file `.tpl` del tuo tema (consulta lo sviluppatore del tuo tema o uno sviluppatore PrestaShop per questo).

**D5: Il modulo rallenta la velocità di caricamento della mia pagina.**

-   **R:** Sebbene il modulo sia ottimizzato, la visualizzazione di molte immagini aggiuntive può naturalmente aumentare il tempo di caricamento della pagina.
    -   Assicurati che le immagini dei tuoi prodotti siano ottimizzate per il web (compresse, dimensioni appropriate).
    -   Considera l'utilizzo dell'opzione "Solo in magazzino" per ridurre il numero di immagini caricate per gli articoli esauriti.
    -   Se hai molte immagini per prodotto, considera l'utilizzo del metodo `Slider`, che spesso carica le immagini in modo più efficiente o in modo lazy.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce un'analisi approfondita della struttura tecnica del modulo "Immagini prodotto nelle schede prodotto", destinata a sviluppatori, webmaster e agenzie tecniche.

### 4.1 Panoramica dell'architettura

Il modulo `productlistpics` è principalmente un modulo di funzionalità front-office progettato per iniettare funzionalità aggiuntive di immagini prodotto nei modelli di elenco prodotti esistenti. Sfrutta il sistema di hook di PrestaShop per renderizzare il suo contenuto e utilizza JavaScript per gestire il cambio dinamico delle immagini (hover/click) o la funzionalità slider. La configurazione è gestita tramite il metodo standard `getContent()` nella classe principale del modulo, memorizzando le impostazioni in `ps_configuration`. Il modulo non introduce tabelle di database personalizzate o complesse entità `ObjectModel`.

### 4.2 Controller (`controllers/`)

Questo modulo **non** contiene alcun controller amministrativo Front-Office o Back-Office personalizzato. Tutta la logica è incapsulata all'interno della classe principale del modulo e dei suoi modelli e risorse associati.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo **non** contiene classi personalizzate o entità `ObjectModel` nella directory `classes/`. Tutta la logica principale risiede in `productlistpics.php`.

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo include diversi file JavaScript, principalmente per la gestione del cambio di immagine e della funzionalità slider.

-   `productlistpics/js/owl-carousel/owl.carousel.js`:
    -   **Ambito:** Front-office.
    -   **Descrizione:** Questa è la libreria principale di Owl Carousel, un popolare plugin jQuery touch-enabled per caroselli reattivi. Fornisce la funzionalità fondamentale per la creazione di slider di immagini.
-   `productlistpics/js/owl-carousel/owl.run.js`:
    -   **Ambito:** Front-office.
    -   **Descrizione:** Questo script contiene probabilmente il codice di inizializzazione e configurazione per le istanze di Owl Carousel utilizzate dal modulo. Imposta il comportamento dello slider, la reattività e le opzioni di navigazione in base alle impostazioni del modulo.
-   `productlistpics/js/plp-replacement.js`:
    -   **Ambito:** Front-office.
    -   **Descrizione:** Questo script è probabilmente responsabile della logica principale per la sostituzione dell'immagine principale del prodotto quando si interagisce con una miniatura. Ascolta gli eventi (click/hover) sulle miniature generate e aggiorna gli attributi `src` e `srcset` dell'immagine principale del prodotto, potenzialmente aggiornando anche l'`href` del tag `<a>` dell'immagine principale.
-   `productlistpics/js/productlistpics-mouseover.js`:
    -   **Ambito:** Front-office.
    -   **Descrizione:** Questo script implementa specificamente il metodo di cambio immagine "Al passaggio del mouse". Collega i listener di eventi `mouseover` e `mouseout` alle ancore delle immagini in miniatura per attivare la sostituzione dell'immagine principale.
-   `productlistpics/js/productlistpics.js`:
    -   **Ambito:** Front-office.
    -   **Descrizione:** Questo è probabilmente il punto di ingresso JavaScript principale del modulo per il front-office. Potrebbe gestire il metodo di cambio immagine "Al click", la manipolazione generale del DOM relativa all'iniezione delle miniature e potenzialmente l'orchestrazione del caricamento di altri script in base alla configurazione.
-   `productlistpics/js/slider-productlistpics-mouseover.js`:
    -   **Ambito:** Front-office.
    -   **Descrizione:** Questo script combina la funzionalità slider con il cambio di immagine basato sul passaggio del mouse. Probabilmente inizializzerà Owl Carousel e quindi aggiungerà listener di passaggio del mouse agli elementi dello slider per aggiornare l'immagine principale del prodotto.
-   `productlistpics/js/slider-productlistpics.js`:
    -   **Ambito:** Front-office.
    -   **Descrizione:** Questo script integra lo slider Owl Carousel con il cambio di immagine basato sul click. Inizializza lo slider e gestisce i click sugli elementi dello slider per aggiornare l'immagine principale del prodotto.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo include diversi file CSS per lo stile degli elementi iniettati e di Owl Carousel.

-   `productlistpics/css.css`:
    -   **Ambito:** Front-office.
    -   **Descrizione:** Stile generale per gli elementi del modulo, come il contenitore per le immagini aggiuntive, il dimensionamento delle miniature e il layout di base.
-   `productlistpics/js/owl-carousel/owl.carousel.css`:
    -   **Ambito:** Front-office.
    -   **Descrizione:** Stili di base per il plugin Owl Carousel, che definiscono la struttura e l'aspetto predefinito dello slider.
-   `productlistpics/js/owl-carousel/owl.theme.css`:
    -   **Ambito:** Front-office.
    -   **Descrizione:** Tema predefinito per Owl Carousel, che fornisce uno stile visivo per i pulsanti di navigazione, i punti e l'estetica generale dello slider.
-   `productlistpics/js/owl-carousel/owl.transitions.css`:
    -   **Ambito:** Front-office.
    -   **Descrizione:** CSS per vari effetti di transizione utilizzati da Owl Carousel (ad esempio, dissolvenza, scorrimento).
-   `productlistpics/productlistpics-classic.css`:
    -   **Ambito:** Front-office.
    -   **Descrizione:** Regole di stile specifiche applicate quando l'opzione di design "Tema classico" è selezionata nella configurazione del modulo. Questo si rivolge a temi PrestaShop più vecchi o temi che imitano l'aspetto classico.
-   `productlistpics/productlistpics.css`:
    -   **Ambito:** Front-office.
    -   **Descrizione:** Stile principale per il modulo, probabilmente contenente regole per l'opzione di design "Universale" e override o miglioramenti generali.

**Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere:**

-   `.productlistpics-container`: Il wrapper principale per le immagini aggiuntive.
-   `.productlistpics-thumb`: Contenitori individuali delle miniature.
-   `.productlistpics-thumb img`: L'immagine effettiva all'interno della miniatura.
-   `.owl-carousel`, `.owl-item`, `.owl-nav`, `.owl-dots`: Selettori standard di Owl Carousel per la personalizzazione dello slider.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo utilizza i template Smarty per renderizzare il suo contenuto all'interno di vari hook di PrestaShop.

-   **Template degli hook (`views/templates/hook/`)**:
    -   `productlistpics/header.tpl`:
        -   **Hook:** `displayHeader` (o simile, tipicamente registrato in `install()`).
        -   **Output:** Questo template è responsabile dell'inclusione delle risorse CSS e JavaScript necessarie affinché il modulo funzioni nel front-office. Carica condizionalmente gli script in base al "Metodo di cambio immagine" scelto (ad esempio, `owl.carousel.js`, `productlistpics-mouseover.js`, `slider-productlistpics.js`).
    -   `productlistpics/html.tpl`:
        -   **Hook:** Questo è un template generico che potrebbe essere incluso da altri template o utilizzato per blocchi di contenuto specifici. Il suo utilizzo esatto dipende da come il file PHP principale del modulo renderizza il contenuto.
        -   **Output:** Contiene la struttura HTML per la visualizzazione delle immagini aggiuntive del prodotto, inclusi cicli per iterare le immagini e logica condizionale per la visualizzazione di caselle di colore o miniature di immagini.
    -   `productlistpics/productFooter.tpl`:
        -   **Hook:** `displayFooterProduct` (come configurato in "Posizione del modulo").
        -   **Output:** Renderizza le immagini aggiuntive del prodotto nella sezione del piè di pagina di un blocco prodotto nelle pagine di elenco. Probabilmente include `html.tpl` o logica simile.
    -   `productlistpics/productPage.tpl`:
        -   **Hook:** Questo template è probabilmente utilizzato per hook come `displayProductAdditionalInfo`, `displayAfterProductThumbs`, `displayProductDeliveryTime`, `displayProductListReviews` (come configurato in "Posizione del modulo").
        -   **Output:** Renderizza le immagini aggiuntive del prodotto all'interno dell'hook specificato per l'elenco prodotti. Contiene la logica principale per la generazione delle miniature delle immagini o delle caselle di colore e per l'impostazione degli attributi di dati necessari per l'interazione JavaScript.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    Il modulo **non** crea tabelle di database personalizzate. Tutte le sue impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` utilizzando chiavi come `PLP_TYPE`, `PLP_INSTOCK`, `PLP_METHOD`, `PLP_SWITCH`, `PLP_DESIGN`, `PLP_POSITION` e varie chiavi di selettore CSS (`pls_product_miniature`, `pls_product_miniature_img`, ecc.).
-   **Tabella degli hook registrati**:

| Nome dell'Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Inietta le risorse CSS e JavaScript richieste dal modulo. |
| `displayProductAdditionalInfo` | All'interno del blocco miniatura del prodotto, spesso sotto l'immagine principale o il titolo. | Renderizza le miniature/slider delle immagini aggiuntive del prodotto. |
| `displayAfterProductThumbs` | Dopo le miniature dell'immagine principale del prodotto (se presenti). | Renderizza le miniature/slider delle immagini aggiuntive del prodotto. |
| `displayFooterProduct` | Nell'area del piè di pagina di ogni blocco miniatura del prodotto. | Renderizza le miniature/slider delle immagini aggiuntive del prodotto. |
| `displayProductDeliveryTime` | Vicino alle informazioni sul tempo di consegna del prodotto nella miniatura del prodotto. | Renderizza le miniature/slider delle immagini aggiuntive del prodotto. |
| `displayProductListReviews` | Vicino alle stelle/conteggio delle recensioni del prodotto nella miniatura del prodotto. | Renderizza le miniature/slider delle immagini aggiuntive del prodotto. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Immagini prodotto nelle schede prodotto", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e compatibilità del modulo.
