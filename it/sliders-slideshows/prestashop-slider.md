---
title: "Prestashop Slider - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Prestashop Slider di MyPresta.eu."
sidebar:
  label: "Prestashop Slider - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Prestashop Slider su MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/prestashop-slider.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/sliders-slideshows/prestashop-slider/)
>
> ---


# Prestashop Slider

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti e di solito preinstallate nella maggior parte degli ambienti di web hosting.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questo è il pannello di controllo principale per il tuo Prestashop Slider. Qui definirai l'aspetto, la sensazione e il contenuto dei tuoi slider.

#### **Impostazioni generali**

- **Cosa fa questa impostazione:** Queste impostazioni controllano il comportamento generale e l'aspetto del tuo slider.
- **Effetto della modifica di questa impostazione:**
  - *Larghezza dello slider:* Definisce quanto sarà largo lo slider. Può essere un valore fisso in pixel o una percentuale per la reattività.
  - *Altezza dello slider:* Definisce l'altezza dello slider.
  - *Tipo di animazione:* Seleziona uno dei 40 effetti di transizione disponibili tra le diapositive.
  - *Velocità dell'animazione:* Controlla la velocità con cui avviene la transizione tra le diapositive.
  - *Intervallo tra le diapositive:* Imposta la durata di visualizzazione di ciascuna diapositiva prima di passare automaticamente alla successiva.
  - *Frecce di navigazione:* Abilita/disabilita le frecce sinistra/destra per la navigazione manuale delle diapositive.
  - *Punti/Pallini di navigazione:* Abilita/disabilita i piccoli punti solitamente presenti nella parte inferiore dello slider per la selezione diretta delle diapositive.
  - *Miniature:* Abilita/disabilita piccole immagini di anteprima di ciascuna diapositiva, spesso visualizzate sotto lo slider principale.
  - *Anteprima miniatura:* Se le miniature sono abilitate, questa impostazione controlla se appare un'anteprima più grande al passaggio del mouse su una miniatura.
  - *Visualizzazione didascalia:* Controlla se e come vengono mostrate le didascalie di testo associate a ciascuna diapositiva.
- **Valore consigliato:**
  - *Larghezza dello slider:* `100%` per uno slider a larghezza intera e reattivo, o un valore specifico in pixel come `1140px` per adattarsi all'area del contenuto principale del tuo tema.
  - *Altezza dello slider:* Inizia con `400px` e regola in base al rapporto d'aspetto dell'immagine e al design.
  - *Tipo di animazione:* Sperimenta! `fade` o `slice` sono buoni punti di partenza per un aspetto pulito.
  - *Velocità dell'animazione:* `800` (millisecondi) per una transizione fluida.
  - *Intervallo tra le diapositive:* `5000` (5 secondi) è un buon equilibrio per consentire agli utenti di leggere il contenuto senza sentirsi affrettati.
  - *Frecce di navigazione:* `SÌ` per un migliore controllo da parte dell'utente.
  - *Punti/Pallini di navigazione:* `SÌ` per una facile panoramica e navigazione.
  - *Miniature:* `NO` inizialmente, abilita se hai molte diapositive e desideri un indice visivo.
  - *Anteprima miniatura:* `SÌ` se le miniature sono abilitate.
  - *Visualizzazione didascalia:* `SÌ` se prevedi di aggiungere testo alle tue diapositive.
- **Scenario / esempio per il commerciante:** Vuoi un banner a larghezza intera sulla tua homepage che ruoti tra tre nuove linee di prodotti. Imposteresti la larghezza su `100%`, sceglieresti un'animazione `fade` e imposteresti un intervallo di `5 secondi`. Abiliteresti le frecce di navigazione e i punti in modo che i clienti possano navigare manualmente se lo desiderano.

#### **Sezione Gestione diapositive**

- **Cosa fa questa impostazione:** Questa sezione ti consente di aggiungere, modificare e rimuovere singole diapositive dal tuo slider. Ogni diapositiva è composta da un'immagine e dalle impostazioni associate.
- **Effetto della modifica di questa impostazione:**
  - *Aggiunta di una nuova diapositiva:* Una nuova immagine verrà aggiunta alla rotazione del tuo slider. Caricherai un'immagine, definirai il suo link, la didascalia e potenzialmente un'animazione unica.
  - *Modifica di una diapositiva esistente:* Puoi cambiare l'immagine, il suo link di destinazione, il testo della didascalia o il tipo di animazione individuale per quella specifica diapositiva.
  - *Eliminazione di una diapositiva:* La diapositiva selezionata verrà rimossa dal tuo slider.
  - *Riordinamento delle diapositive:* Puoi trascinare e rilasciare le diapositive per cambiare l'ordine in cui appaiono nella rotazione.
- **Valore consigliato:** Utilizza sempre immagini di alta qualità e ottimizzate che siano coerenti in dimensioni e rapporto d'aspetto per un aspetto professionale.
- **Scenario / esempio per il commerciante:** Stai lanciando una nuova collezione estiva. Aggiungeresti tre diapositive: una per gli abiti, una per i costumi da bagno e una per gli accessori. Ogni diapositiva presenterebbe un'immagine principale, una didascalia come "Acquista subito gli abiti estivi!" e un link diretto alla rispettiva pagina di categoria. Potresti dare alla diapositiva dei costumi da bagno un'animazione "cubo" per un tocco giocoso, mentre le altre usano "fade".

#### **Selezione Hook**

- **Cosa fa questa impostazione:** Ti consente di scegliere dove nel tuo negozio PrestaShop verrà visualizzato lo slider.
- **Effetto della modifica di questa impostazione:** Selezionando un hook (ad esempio, `displayHeader`, `displayLeftColumn`), il modulo inietterà il codice dello slider in quell'area specifica del tuo tema.
- **Valore consigliato:**
  - Per un banner prominente a larghezza intera: `displayHeader` o un hook personalizzato fornito dal tuo tema per i banner superiori.
  - Per uno slider più piccolo e contestuale: `displayLeftColumn` o `displayRightColumn`.
  - Per slider specifici per prodotto: `displayProductExtraContent` o `displayProductButtons`.
- **Scenario / esempio per il commerciante:** Vuoi che il tuo slider promozionale principale appaia subito sotto il menu principale del tuo sito web. Selezioneresti l'hook `displayHeader` (o un hook simile specifico del tema, se disponibile). Se volessi uno slider più piccolo che mostri "prodotti correlati" sul lato, sceglieresti `displayLeftColumn`.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Larghezza slider | `100%` / `1140px` | Imposta la dimensione orizzontale dello slider. |
| Configurazione modulo | Altezza slider | `400px` | Imposta la dimensione verticale dello slider. |
| Configurazione modulo | Tipo di animazione | `fade` / `slice` | Definisce la transizione visiva tra le diapositive (40 opzioni). |
| Configurazione modulo | Velocità animazione | `800` (ms) | Quanto velocemente avviene la transizione dell'animazione. |
| Configurazione modulo | Intervallo diapositive | `5000` (ms) | Quanto a lungo ogni diapositiva è visibile prima di cambiare. |
| Configurazione modulo | Frecce di navigazione | `SÌ` | Visualizza frecce sinistra/destra per la navigazione manuale. |
| Configurazione modulo | Punti/Pallini di navigazione | `SÌ` | Visualizza punti/pallini per la selezione diretta delle diapositive. |
| Configurazione modulo | Miniature | `NO` | Visualizza piccole immagini di anteprima di ogni diapositiva. |
| Configurazione modulo | Anteprima miniatura | `SÌ` | Mostra un'anteprima più grande al passaggio del mouse sulla miniatura (se abilitato). |
| Configurazione modulo | Visualizzazione didascalia | `SÌ` | Controlla la visibilità delle didascalie di testo sulle diapositive. |
| Configurazione modulo | Aggiungi/Modifica diapositiva | N/A | Carica immagine, imposta link, didascalia e animazione individuale. |
| Configurazione modulo | Selezione Hook | `displayHeader` | Determina dove lo slider appare nel tuo negozio. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D: Il mio slider non viene visualizzato dopo la configurazione. Cosa devo fare?**
R:

1.  **Verifica la selezione dell'Hook:** Torna alla configurazione del modulo e assicurati di aver selezionato almeno un hook (ad esempio, `displayHeader`).
2.  **Svuota la cache:** PrestaShop spesso memorizza i contenuti nella cache. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti).
3.  **Verifica i conflitti:** Disabilita temporaneamente altri moduli che potrebbero utilizzare lo stesso hook o modificare le stesse aree della pagina (specialmente altri moduli slider).
4.  **Compatibilità del tema:** Alcuni temi altamente personalizzati potrebbero richiedere piccole modifiche. Se il problema persiste, contatta il supporto MyPresta.eu con i dettagli del tuo tema.

**D: Le mie immagini appaiono sfocate o allungate nello slider.**
R: Questo di solito significa che le tue immagini non hanno le dimensioni o la risoluzione corrette per le impostazioni del tuo slider.

1.  **Dimensioni coerenti:** Assicurati che tutte le immagini caricate per le tue diapositive abbiano la stessa larghezza e altezza.
2.  **Alta risoluzione:** Carica immagini con una risoluzione sufficiente. Se il tuo slider è largo `1140px`, le tue immagini dovrebbero essere larghe almeno `1140px`.
3.  **Rapporto d'aspetto:** Fai corrispondere il rapporto d'aspetto delle tue immagini alla larghezza e all'altezza configurate dello slider. Se il tuo slider è `1140x400px`, prova a utilizzare immagini con un rapporto d'aspetto simile di 114:40.

**D: Come posso tradurre le didascalie delle mie diapositive in diverse lingue?**
R: Il modulo dovrebbe supportare il sistema di traduzione standard di PrestaShop.

1.  Vai su **Internazionale > Traduzioni**.
2.  Seleziona "Traduzioni dei moduli installati", il tuo tema e la lingua in cui vuoi tradurre.
3.  Trova il modulo "Prestashop Slider" nell'elenco. Dovresti essere in grado di modificare le didascalie per ogni diapositiva direttamente lì. In caso contrario, il modulo potrebbe memorizzare le didascalie direttamente nel database, richiedendoti di modificare ogni diapositiva per ogni lingua nella configurazione del modulo.

**D: Lo slider appare bene su desktop ma è rotto su mobile.**
R:

1.  **Verifica la reattività:** Il modulo è progettato per essere reattivo. Assicurati che il tuo tema stesso sia reattivo.
2.  **Conflitti CSS:** Un altro modulo o il CSS del tuo tema potrebbero sovrascrivere gli stili reattivi dello slider. Utilizza gli strumenti per sviluppatori del tuo browser per ispezionare lo slider su mobile e cercare regole CSS in conflitto.
3.  **Dimensioni dell'immagine:** Immagini molto grandi a volte possono causare problemi su mobile. Assicurati che le immagini siano ottimizzate.

**D: Posso avere più slider su pagine diverse?**
R: La configurazione attuale del modulo gestisce tipicamente una singola istanza principale dello slider con il suo set di diapositive. Se hai bisogno di più slider *distinti* con contenuti e impostazioni diverse su pagine diverse, potresti dover duplicare il modulo (se il tuo tema lo consente) o utilizzare una soluzione slider più avanzata. Per questo modulo, configureresti uno slider e ne sceglieresti il posizionamento tramite gli hook.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce un'analisi approfondita della struttura tecnica del modulo Prestashop Slider, destinata a sviluppatori, webmaster e agenzie tecniche.

### 4.1 Panoramica dell'architettura

Il modulo `Prestashop Slider` (`pslider`) è un modulo PrestaShop standard che sfrutta principalmente la classe `Module`. Gestisce la sua configurazione e i dati delle diapositive direttamente all'interno della tabella `ps_configuration`. La visualizzazione nel front-office è gestita da template Smarty renderizzati tramite il sistema di hook di PrestaShop, iniettando asset JavaScript e CSS per la funzionalità dello slider. Il modulo utilizza il plugin jQuery `Skitter` per le sue capacità di animazione.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller Front-Office o Back-Office Admin personalizzati. Tutta la configurazione è gestita direttamente all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

Questo modulo non definisce classi personalizzate che estendono `ObjectModel`. Tutte le configurazioni e i dati delle diapositive sono memorizzati come array serializzati all'interno della tabella `ps_configuration`, gestiti direttamente dalla classe `Configuration`.

### 4.4 Asset JavaScript (`views/js/`)

Il modulo si basa sul plugin jQuery Skitter per la sua funzionalità di slider.

- `pslider/js/jquery.easing.1.3.js`:
  - **Ambito:** Front-office.
  - **Scopo:** Fornisce funzioni di easing avanzate per le animazioni jQuery, migliorando la fluidità visiva delle transizioni utilizzate dal plugin Skitter.
- `pslider/js/jquery.skitter.js`:
  - **Ambito:** Front-office.
  - **Scopo:** Questo è il plugin core dello slider Skitter. Inizializza lo slider, gestisce le transizioni delle diapositive, la navigazione e la reattività. Legge le opzioni di configurazione (tipo di animazione, velocità, intervallo, ecc.) dalle impostazioni del modulo e le applica all'istanza dello slider.
- `pslider/js/noconflict.js`:
  - **Ambito:** Front-office.
  - **Scopo:** Assicura che jQuery operi in modalità `noConflict()`, prevenendo conflitti con altre librerie JavaScript (come Prototype.js, che PrestaShop 1.6 e precedenti a volte utilizzava) che potrebbero anche usare l'alias `$`. Questo è cruciale per la compatibilità.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo include un singolo file CSS per lo stile dello slider Skitter.

- `pslider/css/skitter.styles.css`:
  - **Ambito:** Stile del cliente del front-office.
  - **Scopo:** Contiene tutti gli stili visivi predefiniti per lo slider Skitter, inclusi:
    - Layout del contenitore dello slider (`.box_skitter`).
    - Stile per gli elementi di navigazione (frecce, punti, miniature).
    - Aspetto predefinito delle didascalie.
    - Regolazioni reattive.
  - **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere:**
    - `.box_skitter`: Contenitore principale dello slider.
    - `.box_skitter ul`: Elenco delle diapositive.
    - `.box_skitter .info_slide`: Contenitore della didascalia.
    - `.box_skitter .nav_cont`: Contenitore della navigazione.
    - `.box_skitter .prev_button`, `.box_skitter .next_button`: Frecce di navigazione.
    - `.box_skitter .info_slide_dots`: Punti di navigazione.
    - `.box_skitter .box_thumbs`: Contenitore delle miniature.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo utilizza i template Smarty per renderizzare il suo contenuto nel front-office e parti della sua configurazione nel back-office.

- **Template degli hook (`views/templates/hook/`)**:

  - `pslider/header.tpl`: Questo template è probabilmente destinato ad essere agganciato a `displayHeader` o a un hook simile nella parte superiore della pagina. Contiene la struttura HTML principale per lo slider e spesso include il codice di inizializzazione JavaScript necessario per il plugin Skitter.
  - `pslider/top.tpl`: Simile a `header.tpl`, questo potrebbe essere utilizzato per un diverso hook di livello superiore, potenzialmente `displayTop` o un altro hook banner specifico del tema. Contenerebbe anche l'HTML e l'inizializzazione JS dello slider.
  - `pslider/views/templates/hook/left-column.tpl`: Questo template è specificamente progettato per il posizionamento nell'hook `displayLeftColumn`. Contenerebbe un'istanza più piccola, potenzialmente diversa, dello slider o un layout modificato adatto per una barra laterale.
- **Template di amministrazione (`views/templates/admin/`)**:

  - `pslider/views/templates/front/form.tpl`: Nonostante si trovi in `views/templates/front/`, questo file è effettivamente utilizzato per il modulo di configurazione del modulo nel Back Office. Definisce la struttura HTML per i campi delle impostazioni (larghezza, altezza, animazione, gestione delle diapositive, ecc.) con cui il commerciante interagisce. Questo viene renderizzato dal metodo `getContent()` in `ajax_pslider.php`.

### 4.7 Schema del database e Mappa degli hook

- **Tabelle del database**:

  - Il modulo non crea tabelle SQL personalizzate.
  - Tutte le impostazioni di configurazione e i dati delle diapositive (percorsi delle immagini, link, didascalie, tipi di animazione individuali) sono memorizzati come array serializzati all'interno della tabella `ps_configuration`. I nomi delle chiavi seguirebbero tipicamente un modello come `PSLIDER_WIDTH`, `PSLIDER_SLIDES`, ecc.
- **Tabella degli hook registrati**:

| Nome dell'Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Renderizza nella sezione `<head>` della pagina del front-office, o all'inizio del `<body>`. | Inietta asset CSS e JavaScript, e potenzialmente la struttura HTML principale dello slider. |
| `displayTop` | Renderizza nella parte superiore del contenuto della pagina, tipicamente sopra l'area del contenuto principale ma sotto l'header. | Visualizza il banner principale dello slider. |
| `displayLeftColumn` | Renderizza nella barra laterale sinistra della pagina del front-office. | Visualizza uno slider specifico per la barra laterale. |
| `displayRightColumn` | Renderizza nella barra laterale destra della pagina del front-office. | Visualizza uno slider specifico per la barra laterale. |
| `displayFooter` | Renderizza nella sezione del footer della pagina del front-office. | Visualizza uno slider specifico per il footer. |
| `displayProductExtraContent` | Renderizza nella pagina del prodotto, tipicamente sotto le informazioni principali del prodotto. | Visualizza slider relativi al prodotto (es. viste alternative, caratteristiche). |
| `displayProductButtons` | Renderizza vicino al pulsante "Aggiungi al carrello" nella pagina del prodotto. | Potrebbe essere utilizzato per piccoli slider contestuali relativi al prodotto. |
| `actionFrontControllerSetMedia` | Eseguito quando un controller frontale sta impostando i suoi asset multimediali. | Consente al modulo di registrare i suoi file JS e CSS in modo condizionale. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo Prestashop Slider, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda possiate avere.
"""
