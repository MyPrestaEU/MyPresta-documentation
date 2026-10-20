---
title: "Prima e dopo - strumento di confronto immagini - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Before & after - pictures diff tool' di MyPresta.eu."
sidebar:
  label: "Prima e dopo - strumento di confronto immagini - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Before & after - pictures diff tool su MyPresta.eu](https://mypresta.eu/modules/front-office-features/before-after-pictures-diff-tool.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/before-after-pictures-diff-tool/)
>
> ---


# Prima e dopo - strumento di confronto immagini

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo "Prima e dopo - strumento di confronto immagini" per accedere alle sue impostazioni principali.

#### Impostazioni Generali

-   **Cosa fa questa impostazione:** Questa sezione controlla l'attivazione generale e la modalità operativa del modulo.
-   **Effetto della modifica di questa impostazione:**
    -   *Abilitato:* Il modulo sarà attivo in tutto il tuo negozio. Lo strumento di confronto immagini "Prima e Dopo" sarà disponibile sulle pagine prodotto dove hai configurato le immagini.
    -   *Disabilitato:* Il modulo sarà inattivo. Lo strumento di confronto immagini "Prima e Dopo" non apparirà su nessuna pagina prodotto, anche se hai configurato le immagini per esse.
    -   *Modalità test:* Questa opzione è tipicamente utilizzata per ambienti di sviluppo o di staging. Quando abilitata, il modulo potrebbe visualizzare informazioni di debug aggiuntive o operare in condizioni specifiche non adatte per un negozio di produzione live. Generalmente non è raccomandata per negozi live a meno che non sia esplicitamente indicato dal supporto.
-   **Valore raccomandato:** "Abilitato" per un negozio live. "Disabilitato" se vuoi nascondere temporaneamente la funzionalità senza disinstallare il modulo.
-   **Scenario / esempio del commerciante:** Se stai lanciando una nuova linea di prodotti che si basa fortemente su trasformazioni visive (es. scarpe dipinte su misura), imposteresti questo su "Abilitato" per mostrare il lavoro. Se stai eseguendo manutenzione o non vuoi che la funzionalità sia attiva per un periodo, la imposteresti su "Disabilitato".

#### Impostazioni Lingua (Implicite)

Sebbene non sia esplicitamente elencata come impostazione, il modulo rispetterà le impostazioni di lingua predefinite del tuo PrestaShop per il Back Office.

-   **`PS_LANG_DEFAULT`**: Questa impostazione core di PrestaShop determina la lingua predefinita per il tuo negozio.
-   **`PS_BO_ALLOW_EMPLOYEE_FORM_LANG`**: Questa impostazione core di PrestaShop consente ai dipendenti di scegliere la loro lingua preferita per i moduli.
-   **Effetto della modifica di questa impostazione:** Queste impostazioni core di PrestaShop assicurano che qualsiasi testo o etichetta fornita dal modulo nel Back Office (es. sulla pagina di modifica del prodotto per aggiungere immagini prima/dopo) sia visualizzata nella lingua corretta per l'amministratore.
-   **Valore raccomandato:** Assicurati che il tuo `PS_LANG_DEFAULT` sia impostato sulla lingua principale del tuo negozio. Se hai un team multilingue, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` dovrebbe essere abilitato.

#### Impostazioni di Aggiornamento (Implicite)

Il modulo include anche impostazioni interne relative agli aggiornamenti da MyPresta.eu. Queste sono solitamente gestite automaticamente.

-   **`mypresta_updates`, `update_`, `updatev_`**: Queste sono chiavi di configurazione interne utilizzate dai moduli MyPresta.eu per controllare e gestire gli aggiornamenti. Generalmente non è necessario interagire con queste.
-   **Effetto della modifica di questa impostazione:** Modificarle direttamente potrebbe interferire con la capacità del modulo di ricevere aggiornamenti importanti e correzioni di bug.
-   **Valore raccomandato:** Lasciare queste impostazioni intatte.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### Pagina di modifica del prodotto (Back Office > Catalogo > Prodotti > Modifica Prodotto)

Questo modulo si integra direttamente nell'interfaccia standard di modifica del prodotto di PrestaShop.

-   **Nome schermata e posizione nel menu:** Per accedervi, naviga su **Catalogo > Prodotti**, quindi clicca su "Modifica" su qualsiasi prodotto.
-   **Azioni e impostazioni disponibili:** All'interno della pagina di modifica del prodotto, troverai una nuova sezione o scheda specifica per "Prima e dopo - strumento di confronto immagini". Qui potrai:
    -   **Carica immagine "Prima":** Seleziona e carica l'immagine dello stato iniziale del tuo prodotto.
    -   **Carica immagine "Dopo":** Seleziona e carica l'immagine dello stato finale del tuo prodotto.
    -   **Salva:** Dopo aver caricato, ricorda di salvare il prodotto per applicare le modifiche.
-   **Effetto delle modifiche:**
    -   *Aggiunta di immagini:* Una volta caricate sia un'immagine "Prima" che un'immagine "Dopo" per un prodotto specifico e salvate, lo slider di confronto interattivo apparirà automaticamente sulla pagina front-office di quel prodotto.
    -   *Rimozione di immagini:* Se rimuovi una o entrambe le immagini, lo slider di confronto non verrà più visualizzato per quel prodotto.
    -   *Aggiornamento di immagini:* La sostituzione delle immagini aggiornerà lo slider sul front office.
-   **Flusso di lavoro raccomandato per la gestione quotidiana del negozio:**
    1.  Quando aggiungi un nuovo prodotto che beneficia di un confronto prima/dopo, crea prima il prodotto come al solito.
    2.  Naviga alla sua pagina di modifica.
    3.  Individua la sezione "Prima e dopo".
    4.  Carica le tue immagini "prima" e "dopo". Assicurati che abbiano dimensioni simili per il miglior effetto visivo.
    5.  Salva il prodotto.
    6.  Controlla la pagina del prodotto sul front office per confermare che lo slider funzioni come previsto.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Raccomandato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Stato Modulo | Abilitato | Attiva/disattiva l'intera funzionalità del modulo. |
| Pagina di Modifica Prodotto | Carica immagine "Prima" | N/A | Definisce l'immagine dello stato iniziale per il confronto. |
| Pagina di Modifica Prodotto | Carica immagine "Dopo" | N/A | Definisce l'immagine dello stato finale per il confronto. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D1: Lo slider "Prima e Dopo" non appare sulla pagina del mio prodotto.**
R1:

-   **Controlla lo stato del modulo:** Vai su **Moduli > Gestione moduli** e assicurati che "Prima e dopo - strumento di confronto immagini" sia "Abilitato".
-   **Controlla le immagini del prodotto:** Modifica il prodotto specifico (**Catalogo > Prodotti > Modifica**) e verifica che sia stata caricata e salvata un'immagine "Prima" e un'immagine "Dopo" nella sezione del modulo.
-   **Svuota la cache:** A volte, la cache di PrestaShop può impedire la visualizzazione di nuovi contenuti. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache".
-   **Compatibilità del tema:** Sebbene il modulo sia progettato per essere compatibile, alcuni temi altamente personalizzati potrebbero richiedere piccole modifiche CSS. Se i passaggi precedenti non funzionano, contatta il supporto MyPresta.eu.

**D2: Le immagini appaiono distorte o disallineate nello slider.**
R2:

-   **Dimensioni delle immagini:** Per ottenere i migliori risultati, assicurati che le tue immagini "Prima" e "Dopo" abbiano esattamente le stesse dimensioni (larghezza e altezza). Se differiscono significativamente, lo slider potrebbe avere difficoltà ad allinearle perfettamente.
-   **Qualità delle immagini:** Utilizza immagini di alta qualità. Le immagini a bassa risoluzione potrebbero apparire pixelate quando ridimensionate.

**D3: Posso usare questo modulo per prodotti con più varianti (combinazioni)?**
R3: Il modulo attualmente ti consente di impostare un'immagine "Prima" e un'immagine "Dopo" per prodotto, non per combinazione. Se le tue varianti hanno stati prima/dopo diversi, potresti dover creare prodotti separati o utilizzare le immagini principali del prodotto per il confronto.

**D4: Come traduco il testo del modulo (se presente) in altre lingue?**
R4: Qualsiasi etichetta di testo introdotta dal modulo nel Back Office (es. "Carica immagine Prima") può essere tipicamente tradotta tramite il sistema di traduzione integrato di PrestaShop. Vai su **Internazionale > Traduzioni**, seleziona "Traduzioni dei moduli installati", scegli il tuo tema e poi trova il modulo "Prima e dopo - strumento di confronto immagini" per modificare le sue traduzioni.

**D5: Lo slider funziona, ma non si adatta bene al design del mio tema.**
R5: Questo spesso dipende dallo stile CSS. Il tuo tema potrebbe avere stili in conflitto. Puoi provare a ispezionare l'elemento utilizzando gli strumenti per sviluppatori del tuo browser per identificare il CSS in conflitto. Per una personalizzazione più avanzata, potresti aver bisogno di uno sviluppatore web o contattare il supporto MyPresta.eu per indicazioni su come sovrascrivere gli stili predefiniti del modulo.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

### 4.1 Panoramica dell'Architettura

Il modulo "Prima e dopo - strumento di confronto immagini" è un modulo PrestaShop standard che segue un modello simile a MVC. Estende principalmente la classe `Module`, si integra con la pagina di amministrazione del prodotto tramite hook e inietta i suoi asset e template front-office nel footer della pagina del prodotto. Sfrutta plugin jQuery esterni (`jquery.event.move.js`, `jquery.twentytwenty.js`) per la funzionalità dello slider interattivo.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller front-office o back-office dedicati. Tutta la logica è gestita all'interno della classe principale del modulo e tramite hook.

### 4.3 Classi Core e Modelli (`classes/`)

Questo modulo non definisce classi personalizzate o `ObjectModel`. Memorizza la sua configurazione direttamente in `ps_configuration` e i percorsi delle immagini specifiche del prodotto come attributi del prodotto o valori di configurazione, gestiti tramite l'hook `displayAdminProductsExtra`.

### 4.4 Asset JavaScript (`views/js/`)

Il modulo include diversi file JavaScript, principalmente per lo slider di confronto immagini "TwentyTwenty". Questi vengono caricati nel front-office.

-   **`beforeafter/js/jquery.event.move.js`**
    -   **Ambito:** Front-office.
    -   **Scopo:** Un plugin jQuery leggero che fornisce la gestione degli eventi touch e mouse per il trascinamento degli elementi. È una dipendenza per `jquery.twentytwenty.js`.
    -   **Dettagli:** Lega eventi come `move`, `movestart`, `moveend` per abilitare la funzionalità di trascinamento.
-   **`beforeafter/js/jquery.twentytwenty.js`**
    -   **Ambito:** Front-office.
    -   **Scopo:** Il plugin jQuery core che implementa lo slider di confronto immagini "TwentyTwenty".
    -   **Dettagli:** Inizializza lo slider su elementi specificati, gestisce il rendering visivo delle immagini prima/dopo e gestisce il divisore interattivo basato su `jquery.event.move.js`. Tipicamente si rivolge a un contenitore con due tag `img` al suo interno.
-   **`beforeafter/js/twentytwenty.js`**
    -   **Ambito:** Front-office.
    -   **Scopo:** Questo file contiene probabilmente la logica di inizializzazione specifica del modulo per il plugin `jquery.twentytwenty.js`, applicandolo agli elementi corretti sulla pagina del prodotto.
    -   **Dettagli:** Conterrà selettori jQuery per identificare l'elemento `div` che racchiude le immagini prima/dopo e chiamerà il metodo `.twentytwenty()` su di esso, potenzialmente con opzioni di configurazione.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo include file CSS per stilizzare lo slider di confronto immagini e i suoi componenti.

-   **`beforeafter/css/foundation.css`**
    -   **Ambito:** Front-office.
    -   **Scopo:** Questo file contiene probabilmente stili di reset o fondamentali di base, forse un sottoinsieme del framework Zurb Foundation, per garantire un rendering coerente degli elementi dello slider. Potrebbe definire stili di griglia, tipografia o moduli di base che il modulo utilizza.
    -   **Selettori chiave:** Potrebbe includere stili generali per `div`, `img`, `button` o classi specifiche come `.row`, `.column`.
-   **`beforeafter/css/twentytwenty.css`**
    -   **Ambito:** Front-office.
    -   **Scopo:** Contiene lo stile specifico richiesto per lo slider di confronto immagini "TwentyTwenty" stesso.
    -   **Selettori chiave:** Definisce l'aspetto del contenitore dello slider, della maniglia del divisore, dell'overlay e del posizionamento delle immagini "prima" e "dopo". Esempi: `.twentytwenty-container`, `.twentytwenty-overlay`, `.twentytwenty-handle`, `.twentytwenty-before`, `.twentytwenty-after`. Gli sviluppatori possono sovrascrivere queste classi nel `custom.css` o `theme.css` del loro tema per adattarle al design del loro negozio.

### 4.6 Struttura del Template Smarty (`views/templates/`)

-   **Template degli hook (`views/templates/hook/`)**:
    -   `beforeafter/views/templates/front/hook/displayFooter.tpl`
        -   **Hook:** `displayFooter` (o potenzialmente `displayFooterProduct` a seconda della logica interna).
        -   **Scopo:** Questo template è responsabile del rendering della struttura HTML effettiva per lo slider di confronto immagini "Prima e Dopo" nel front office. Conterrà gli elementi `div` che il JavaScript targetizzerà per inizializzare il plugin `twentytwenty`, inclusi i tag `img` per le immagini "prima" e "dopo". Probabilmente include anche il caricamento degli asset JavaScript e CSS necessari.
    -   `beforeafter/views/templates/front/hook/displayFooterCms.tpl`
        -   **Hook:** Probabilmente `displayFooter` o `displayFooterProduct` ma potenzialmente con logica condizionale per le pagine CMS.
        -   **Scopo:** Questo template potrebbe essere un fallback o un'alternativa per il rendering dello slider sulle pagine CMS, sebbene la descrizione del modulo si concentri sulle pagine prodotto. Il suo contenuto sarebbe simile a `displayFooter.tpl`.
-   **Template di amministrazione (`views/templates/admin/`)**:
    -   `beforeafter/views/templates/admin/displayAdminProductsExtra.tpl`
        -   **Hook:** `displayAdminProductsExtra`
        -   **Scopo:** Questo template renderizza i campi di input personalizzati e i moduli di caricamento all'interno della pagina di modifica del prodotto di PrestaShop nel Back Office. Fornisce l'interfaccia per gli amministratori per caricare e gestire le immagini "Prima" e "Dopo" per ogni prodotto. Conterrà elementi di modulo (es. `input type="file"`) e potenzialmente visualizzerà le miniature delle immagini già caricate.

### 4.7 Schema del Database e Mappa degli Hook

-   **Tabelle del Database**:

    -   Il modulo non crea tabelle SQL personalizzate.
    -   Memorizza le sue impostazioni di configurazione (come `BA_TEST`) nella tabella `ps_configuration`.
    -   I percorsi delle immagini "prima" e "dopo" specifiche del prodotto sono probabilmente memorizzati come valori di configurazione o attributi specifici del prodotto, gestiti tramite l'hook `displayAdminProductsExtra` e i metodi `install()` e `uninstall()` del modulo.
-   **Tabella degli Hook Registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `actionProductUpdate` | Dopo l'aggiornamento di un prodotto nel Back Office. | Utilizzato per salvare i percorsi delle immagini "prima" e "dopo" caricate tramite la pagina di modifica del prodotto. |
| `displayFooterProduct` | Renderizza il contenuto nella sezione footer della pagina del prodotto. | Utilizzato per visualizzare lo slider di confronto immagini "Prima e Dopo" sulla pagina del prodotto del front-office. |
| `displayAdminProductsExtra` | Renderizza contenuto aggiuntivo nella pagina di modifica del prodotto nel Back Office. | Utilizzato per iniettare i campi del modulo personalizzati per il caricamento delle immagini "prima" e "dopo" nell'interfaccia di amministrazione del prodotto. |
| `actionAdminControllerSetMedia` | Prima che un controller admin renderizzi la sua vista, consentendo ai moduli di aggiungere JS/CSS. | Utilizzato per caricare i file JavaScript (`jquery.event.move.js`, `jquery.twentytwenty.js`, `twentytwenty.js`) e CSS (`foundation.css`, `twentytwenty.css`) necessari per il modulo nel Back Office (se necessario per la pagina del prodotto admin) e potenzialmente nel front office. |
| `displayHeader` | Renderizza il contenuto nella sezione `<head>` delle pagine del front-office. | Utilizzato per caricare i file JavaScript e CSS necessari per lo slider "Prima e Dopo" nel front office, assicurando che siano disponibili prima che l'hook `displayFooterProduct` renderizzi l'HTML dello slider. |

## 5. Supporto Ufficiale e Aggiornamenti

Per supporto ufficiale, aggiornamenti e qualsiasi ulteriore assistenza con il modulo "Prima e dopo - strumento di confronto immagini", si prega di fare riferimento al proprio account cliente MyPresta.eu. È possibile trovare le ultime versioni del modulo, la documentazione e contattare il nostro team di supporto direttamente tramite il sito web MyPresta.eu.
