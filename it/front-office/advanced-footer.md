---
title: "Advanced Footer - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Advanced Footer di MyPresta.eu."
sidebar:
  label: "Advanced Footer - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Advanced Footer su MyPresta.eu](https://mypresta.eu/modules/front-office-features/advanced-footer.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/advanced-footer/)
>
> ---


# Advanced Footer

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Nessun requisito server insolito.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata principale dove definirai l'aspetto del tuo piè di pagina avanzato.

-   **Posizione del menu:** Back Office > Moduli > Gestione moduli > Cerca "Advanced Footer" > Clicca su "Configura".

#### **Impostazioni e Opzioni:**

1.  **Larghezza del piè di pagina (`advf_f_width`)**

    -   **Cosa fa questa impostazione:** Controlla la larghezza complessiva dell'area del tuo piè di pagina personalizzato. Puoi impostarla su un valore fisso in pixel o su una percentuale.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se impostato su un valore fisso in pixel (es. `1200px`):* Il piè di pagina avrà sempre quella larghezza esatta, centrato sulla pagina. Su schermi molto ampi, potrebbe esserci spazio vuoto ai lati. Su schermi più stretti, potrebbe introdurre barre di scorrimento orizzontale se il valore è troppo grande.
        -   *Se impostato su una percentuale (es. `100%`):* Il piè di pagina si estenderà per riempire la larghezza disponibile dello schermo, adattandosi dinamicamente. Questo è generalmente raccomandato per design responsive.
    -   **Valore consigliato:** `100%` per un piè di pagina a larghezza intera e responsive, o `1200px` se l'area del contenuto principale del tuo negozio ha una larghezza fissa e desideri che il piè di pagina corrisponda.
    -   **Scenario / esempio per il commerciante:** Se l'area del contenuto principale del tuo negozio è larga 1200px, impostare la larghezza del piè di pagina a `1200px` lo farà allineare perfettamente, creando un design coeso. Se desideri che il piè di pagina si estenda sempre per l'intera finestra del browser, `100%` è la scelta giusta.
2.  **Altezza del piè di pagina (`advf_f_height`)**

    -   **Cosa fa questa impostazione:** Definisce l'altezza minima dell'area del tuo piè di pagina. Se il tuo contenuto è più alto di questo, il piè di pagina si espanderà automaticamente.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se impostato su un valore specifico in pixel (es. `280px`):* Il piè di pagina sarà sempre almeno di questa altezza. Questo può essere utile per mantenere una presenza visiva coerente anche se alcune pagine hanno meno contenuto nel piè di pagina.
        -   *Se lasciato vuoto o impostato su `auto` (se disponibile):* L'altezza del piè di pagina sarà determinata esclusivamente dal suo contenuto.
    -   **Valore consigliato:** `280px` o `300px` è un buon punto di partenza per dare al tuo piè di pagina una presenza sostanziale. Puoi regolarlo in base alla quantità di contenuto che intendi inserire.
    -   **Scenario / esempio per il commerciante:** Desideri che il tuo piè di pagina occupi sempre uno spazio evidente nella parte inferiore della pagina, anche se hai solo pochi link. Impostare un'altezza minima assicura che non appaia troppo sottile.
3.  **Colore di sfondo del piè di pagina (`advf_f_bg`)**

    -   **Cosa fa questa impostazione:** Ti permette di scegliere un colore di sfondo solido per l'intera area del tuo piè di pagina.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se impostato su un colore (es. `#333333` per grigio scuro):* Lo sfondo del piè di pagina visualizzerà questo colore.
        -   *Se lasciato vuoto:* Il piè di pagina potrebbe ereditare uno sfondo dal tuo tema o essere trasparente.
    -   **Valore consigliato:** Un colore che si abbini al branding del tuo negozio. I colori più scuri (come grigio scuro o nero) sono comuni per i piè di pagina, ma anche un colore più chiaro può funzionare a seconda del tuo design.
    -   **Scenario / esempio per il commerciante:** Il tuo marchio utilizza una specifica tonalità di blu. Puoi impostare lo sfondo del piè di pagina su questo blu per rafforzare l'identità del tuo marchio.
4.  **Colore del testo del piè di pagina (`advf_f_color`)**

    -   **Cosa fa questa impostazione:** Imposta il colore predefinito per tutto il testo all'interno del tuo piè di pagina, inclusi i link.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se impostato su un colore (es. `#ffffff` per bianco):* Tutto il testo nel piè di pagina apparirà in questo colore.
        -   *Se lasciato vuoto:* Il colore del testo potrebbe ereditare dalle impostazioni predefinite del tuo tema, che potrebbero non essere leggibili contro lo sfondo del piè di pagina scelto.
    -   **Valore consigliato:** Un colore che fornisca un buon contrasto con il `Colore di sfondo del piè di pagina` scelto. Se il tuo sfondo è scuro, scegli un colore del testo chiaro (es. bianco, grigio chiaro). Se il tuo sfondo è chiaro, scegli un colore del testo scuro.
    -   **Scenario / esempio per il commerciante:** Hai uno sfondo del piè di pagina grigio scuro. Impostare il colore del testo su bianco (`#ffffff`) assicura che tutti i tuoi link e le informazioni siano facilmente leggibili.
5.  **Colore al passaggio del mouse sui link del piè di pagina (`advf_f_color_hover`)**

    -   **Cosa fa questa impostazione:** Definisce il colore in cui i link nel tuo piè di pagina cambieranno quando un cliente ci passa sopra con il mouse.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se impostato su un colore (es. `#cccccc` per grigio chiaro):* I link cambieranno visivamente a questo colore al passaggio del mouse, fornendo feedback all'utente che l'elemento è interattivo.
        -   *Se lasciato vuoto:* I link potrebbero non avere un effetto al passaggio del mouse, o potrebbero ereditare un colore predefinito al passaggio del mouse dal tuo tema, che potrebbe non corrispondere al design del tuo piè di pagina.
    -   **Valore consigliato:** Una tonalità leggermente diversa del tuo `Colore del testo del piè di pagina` o un colore accentato dalla palette del tuo marchio. Dovrebbe essere evidente ma non stridente.
    -   **Scenario / esempio per il commerciante:** I tuoi link nel piè di pagina sono bianchi. Impostare il colore al passaggio del mouse su un blu chiaro (`#ADD8E6`) fornisce un'interazione sottile e brandizzata quando i clienti ci passano sopra con il mouse.
6.  **URL immagine di sfondo del piè di pagina (`advf_f_bg_url`)**

    -   **Cosa fa questa impostazione:** Ti permette di usare un'immagine come sfondo per il tuo piè di pagina invece o in aggiunta a un colore solido. Devi fornire l'URL completo dell'immagine.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se viene fornito un URL valido:* L'immagine apparirà come sfondo del piè di pagina. Il `Colore di sfondo del piè di pagina` sarà visibile se l'immagine è trasparente o se l'immagine non copre l'intero piè di pagina.
        -   *Se lasciato vuoto:* Non verrà utilizzata alcuna immagine di sfondo.
    -   **Valore consigliato:** Lasciare vuoto a meno che tu non abbia un'immagine di sfondo specifica e ottimizzata. Se utilizzata, assicurati che l'immagine sia leggera e pertinente.
    -   **Scenario / esempio per il commerciante:** Hai un'immagine con una texture sottile che vuoi usare come sfondo per il tuo piè di pagina per aggiungere profondità visiva. Dovresti caricare questa immagine sul tuo server e incollare il suo URL qui.
7.  **Posizione immagine di sfondo del piè di pagina (`advf_f_bg_pos`)**

    -   **Cosa fa questa impostazione:** Controlla come un'immagine di sfondo (se impostata) è posizionata all'interno dell'area del piè di pagina. I valori comuni includono `center center`, `top left`, `bottom right`, ecc.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se impostato su `center center`:* L'immagine sarà centrata orizzontalmente e verticalmente.
        -   *Se impostato su `top left`:* L'immagine inizierà dall'angolo in alto a sinistra.
    -   **Valore consigliato:** `center center` per la maggior parte delle immagini, o `top left` se la tua immagine è un motivo destinato a iniziare dall'angolo.
    -   **Scenario / esempio per il commerciante:** La tua immagine di sfondo è un piccolo logo che vuoi che appaia una volta al centro del piè di pagina. Imposteresti questo su `center center`.
8.  **Ripetizione immagine di sfondo del piè di pagina (`advf_f_bg_repeat`)**

    -   **Cosa fa questa impostazione:** Determina se e come un'immagine di sfondo (se impostata) deve ripetersi per riempire l'area del piè di pagina.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se impostato su `repeat`:* L'immagine si ripeterà orizzontalmente e verticalmente.
        -   *Se impostato su `no-repeat`:* L'immagine apparirà solo una volta.
        -   *Se impostato su `repeat-x`:* L'immagine si ripeterà solo orizzontalmente.
        -   *Se impostato su `repeat-y`:* L'immagine si ripeterà solo verticalmente.
    -   **Valore consigliato:** `no-repeat` per immagini singole (come un logo), o `repeat` se la tua immagine è un piccolo motivo progettato per ripetersi.
    -   **Scenario / esempio per il commerciante:** Hai un'immagine di un piccolo motivo senza soluzione di continuità. Impostando questo su `repeat` farà sì che copra l'intera area del piè di pagina con quel motivo. Se è un singolo elemento decorativo, `no-repeat` è meglio.

#### Tabella di riferimento rapido per la configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Larghezza piè di pagina (`advf_f_width`) | `100%` | Imposta la larghezza complessiva del piè di pagina. `100%` per larghezza intera responsive, `1200px` per larghezza fissa. |
| Configurazione modulo | Altezza piè di pagina (`advf_f_height`) | `280px` | Definisce l'altezza minima del piè di pagina. Assicura una presenza visiva coerente. |
| Configurazione modulo | Colore sfondo piè di pagina (`advf_f_bg`) | (Colore del tuo marchio) | Imposta il colore di sfondo solido per il piè di pagina. Cruciale per il branding e il contrasto. |
| Configurazione modulo | Colore testo piè di pagina (`advf_f_color`) | (Colore contrastante) | Imposta il colore predefinito del testo nel piè di pagina. Assicura la leggibilità rispetto allo sfondo. |
| Configurazione modulo | Colore link al passaggio del mouse (`advf_f_color_hover`) | (Accento sottile) | Definisce il colore dei link al passaggio del mouse. Migliora il feedback dell'interazione utente. |
| Configurazione modulo | URL immagine sfondo piè di pagina (`advf_f_bg_url`) | Lasciare vuoto | URL di un'immagine da usare come sfondo del piè di pagina. Aggiunge texture visiva o branding. |
| Configurazione modulo | Posizione immagine sfondo piè di pagina (`advf_f_bg_pos`) | `center center` | Come è posizionata l'immagine di sfondo. `center center` per la maggior parte delle immagini singole. |
| Configurazione modulo | Ripetizione immagine sfondo piè di pagina (`advf_f_bg_repeat`) | `no-repeat` | Come l'immagine di sfondo si ripete. `no-repeat` per immagini singole, `repeat` per motivi. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Le modifiche al mio piè di pagina non vengono visualizzate nel front office.**
**R1:** Questo è solitamente un problema di caching.
\* Vai su **Parametri avanzati > Prestazioni** nel Back Office di PrestaShop.
\* Clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti).
\* Se utilizzi un modulo di caching di terze parti o caching a livello di server (come Varnish), svuota anche quelle cache.
\* Inoltre, prova a svuotare la cache del tuo browser (Ctrl+F5 o Cmd+Shift+R).

**D2: Il piè di pagina appare diverso sui dispositivi mobili rispetto al desktop.**
**R2:** Questo è previsto e di solito è un bene! I temi PrestaShop moderni sono responsive, il che significa che adattano il layout per diverse dimensioni dello schermo. Le impostazioni del modulo (come `Larghezza piè di pagina: 100%`) sono progettate per funzionare con questo. Se elementi specifici appaiono rotti, potrebbe essere un conflitto con il CSS del tuo tema.
\* **Risoluzione dei problemi:** Controlla il CSS specifico per dispositivi mobili del tuo tema. Se hai aggiunto contenuto HTML personalizzato al piè di pagina, assicurati che anche quel contenuto sia responsive. Potrebbe essere necessario un webmaster per ispezionare il CSS.

**D3: Come faccio ad aggiungere contenuto effettivo (link, testo, immagini) a questo piè di pagina avanzato?**
**R3:** Questo modulo fornisce principalmente il framework di *stile* (sfondo, colori, dimensioni) per il tuo piè di pagina. Il *contenuto* del piè di pagina è tipicamente gestito dagli hook del piè di pagina del tuo tema PrestaShop (come `displayFooter`) o da altri moduli progettati per blocchi di contenuto (es. un modulo di blocco HTML personalizzato, o il modulo Link List integrato di PrestaShop).
\* **Soluzione:** Dopo aver configurato lo stile dell'Advanced Footer, dovrai utilizzare le opzioni del tuo tema o altri moduli di contenuto per popolare l'hook `displayFooter` con i link, il testo e le immagini desiderati. Il modulo Advanced Footer applicherà quindi il suo stile a quel contenuto.

**D4: I colori che ho impostato non sembrano essere applicati a tutti gli elementi del mio piè di pagina.**
**R4:** Questo può accadere se il tuo tema ha regole CSS molto specifiche che sovrascrivono gli stili del modulo.
\* **Risoluzione dei problemi:** Il modulo applica uno stile generale al piè di pagina. Se il tuo tema ha regole più specifiche (es. per `ul li a` all'interno del piè di pagina), queste potrebbero avere la precedenza. Potrebbe essere necessario consultare un webmaster per aggiungere CSS personalizzato al tuo tema per sovrascrivere elementi specifici, o regolare le impostazioni del tuo tema se ha una sezione dedicata alla personalizzazione del piè di pagina.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo Advanced Footer è un modulo PrestaShop standard focalizzato principalmente sullo stile del front-office. Sfrutta il sistema di configurazione di PrestaShop (`Configuration::updateValue`) per memorizzare le sue impostazioni e si aggancia a `displayFooter` per iniettare il suo CSS e JavaScript personalizzati. Non introduce nuove tabelle di database o ObjectModels complessi, rendendolo leggero e focalizzato sul suo compito principale: la personalizzazione del piè di pagina. Il modulo utilizza un metodo `getContent()` per la sua configurazione nel back-office, rendendo un modulo PrestaShop standard.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Nessuno. Il modulo si aggancia direttamente a `displayFooter` e `footer` per renderizzare il suo contenuto e applicare gli stili.
-   **Controller Admin Back-Office**: Nessuno. Tutta la configurazione è gestita all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

-   Nessuna classe o ObjectModels personalizzati sono definiti nella directory `classes/`. Tutta la logica è contenuta nel file principale del modulo `advfooter.php`.

### 4.4 Risorse JavaScript (`views/js/`)

-   `advfooter/js/advajax.js`:
    -   **Ambito:** Back-office.
    -   **Responsabilità:** Probabilmente gestisce le richieste AJAX relative al salvataggio delle impostazioni di configurazione del modulo senza un ricaricamento completo della pagina, o fornisce feedback dinamico all'interno del modulo di configurazione.
-   `advfooter/js/foscript.js`:
    -   **Ambito:** Front-office.
    -   **Responsabilità:** Questo script conterrebbe qualsiasi logica lato client o comportamento dinamico specifico per il piè di pagina avanzato sul lato cliente. Questo potrebbe includere aggiustamenti responsive, effetti hover specifici non gestiti dal CSS, o interazioni con contenuti incorporati.
-   `advfooter/js/jscolor/jscolor.js`:
    -   **Ambito:** Back-office.
    -   **Responsabilità:** Questa è una libreria JavaScript di terze parti per fornire un widget di selezione colore nel Back Office. Viene utilizzata per consentire ai commercianti di selezionare visivamente i colori per lo sfondo, il testo e gli effetti hover.
-   `advfooter/js/script.js`:
    -   **Ambito:** Back-office.
    -   **Responsabilità:** Script generico per la pagina di configurazione del Back Office del modulo. Potrebbe inizializzare il selettore `jscolor`, gestire la validazione del modulo o altri miglioramenti dell'interfaccia utente per l'interfaccia di amministrazione.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `advfooter/css/fancybox.css`:
    -   **Ambito:** Front-office (potenzialmente, se il modulo utilizza Fancybox per qualsiasi contenuto o immagine incorporata).
    -   **Responsabilità:** Fornisce lo stile per la libreria lightbox Fancybox, comunemente utilizzata per visualizzare immagini, video o altri contenuti in un overlay modale. La sua presenza suggerisce che il modulo potrebbe supportare tale funzionalità, o è inclusa come utilità generale.
    -   **Selettori di classe CSS chiave:** `.fancybox-overlay`, `.fancybox-wrap`, `.fancybox-inner`, ecc. Gli sviluppatori possono sovrascriverli per personalizzare l'aspetto della lightbox.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template degli hook (`views/templates/hook/`)**:

    -   `advfooter/footer.tpl`:
        -   **Hook:** `displayFooter` (e potenzialmente `footer` per temi più vecchi).
        -   **Output:** Questo template è responsabile del rendering della struttura principale del piè di pagina avanzato. Probabilmente conterrà un elemento HTML `div` o `footer` con stili inline dinamici o attributi di classe popolati dalle impostazioni di configurazione del modulo (es. `width`, `height`, `background-color`, `background-image`, `color`). Agisce come contenitore per qualsiasi contenuto che altri moduli o il tema inseriscono nell'hook `displayFooter`.
-   **Template di amministrazione (`views/templates/admin/`)**: Nessuno. Il modulo di configurazione è probabilmente renderizzato direttamente all'interno di `getContent()` utilizzando `HelperForm` di PrestaShop o simili.
-   **Template Front-office (`views/templates/front/`)**: Nessuno.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non crea alcuna tabella SQL personalizzata.
    -   Le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` utilizzando le chiavi: `ADVF_F_WIDTH`, `ADVF_F_HEIGHT`, `ADVF_F_BG`, `ADVF_F_COLOR`, `ADVF_F_COLOR_HOVER`, `ADVF_F_BG_URL`, `ADVF_F_BG_POS`, `ADVF_F_BG_REPEAT`.
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Eseguito nella sezione `<head>` di ogni pagina. | Utilizzato per registrare risorse CSS e JavaScript (`foscript.js`, `fancybox.css`) per il front-office, e potenzialmente iniettare stili inline basati sulla configurazione del modulo. |
| `displayBackOfficeHeader` | Eseguito nella sezione `<head>` di ogni pagina del Back Office. | Utilizzato per registrare risorse CSS e JavaScript (`advajax.js`, `jscolor.js`, `script.js`) per la pagina di configurazione del modulo. |
| `displayFooter` | Eseguito nella parte inferiore della pagina, tipicamente prima del tag di chiusura `</body>`. | Renderizza il template `footer.tpl`, che applica lo stile personalizzato e funge da contenitore per il contenuto del piè di pagina. |
| `footer` | (PrestaShop 1.6 e precedenti, o per compatibilità con temi specifici) | Simile a `displayFooter`, utilizzato per renderizzare il contenuto del piè di pagina. Il modulo probabilmente si registra a entrambi per una maggiore compatibilità. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, accedi al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Lì troverai i tuoi moduli acquistati e l'accesso diretto alle risorse di supporto.
