---
title: "MyQuill - Quill editor - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop MyQuill - Quill editor di MyPresta.eu."
sidebar:
  label: "MyQuill - Quill editor"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo MyQuill - Quill editor su MyPresta.eu](https://mypresta.eu/modules/administration-tools/myquill-quill-editor.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/myquill-quill-editor/)
>
> ---


# MyQuill - Quill editor

## 1. Requisiti e Compatibilità
- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti e solitamente abilitate per impostazione predefinita sulla maggior parte degli ambienti di hosting.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)
Dopo l'installazione, cliccando su "Configura" verrai indirizzato alla schermata di configurazione principale di MyQuill. Qui è dove controlli il comportamento dell'editor Quill nel tuo Back Office.

#### **Scheda Impostazioni Generali**

**1. Abilita Editor MyQuill**
-   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare l'editor MyQuill.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* L'editor Quill sostituirà l'editor TinyMCE predefinito in tutte le aree supportate del tuo Back Office PrestaShop (es. descrizioni prodotti, pagine CMS, descrizioni categorie).
    -   *Quando disabilitato (NO):* L'editor TinyMCE predefinito verrà ripristinato e le funzionalità di MyQuill non saranno disponibili.
-   **Valore consigliato:** **SÌ** (per utilizzare le funzionalità del modulo).
-   **Scenario / esempio per il commerciante:** Se desideri tornare temporaneamente a TinyMCE per test di compatibilità con un altro modulo, disabiliteresti MyQuill qui. Altrimenti, mantienilo abilitato per godere dell'editor avanzato.

**2. Carica Editor Quill nel Front Office**
-   **Cosa fa questa impostazione:** Determina se le risorse necessarie dell'editor Quill (CSS, JS) vengono caricate nel front office del tuo negozio. Questo è solitamente necessario solo se hai un tema personalizzato o un altro modulo che utilizza Quill nel front end.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* I file core di Quill saranno inclusi nelle pagine pubbliche del tuo negozio. Questo potrebbe aumentare leggermente il tempo di caricamento della pagina ma è necessario se visualizzi contenuti generati da Quill che richiedono il suo stile o funzionalità specifici nel front end.
    -   *Quando disabilitato (NO):* I file core di Quill *non* verranno caricati nel front office, risparmiando larghezza di banda e potenzialmente migliorando la velocità di caricamento della pagina.
-   **Valore consigliato:** **NO** (a meno che tu non abbia un motivo specifico per caricarlo, come una funzionalità del tema personalizzato).
-   **Scenario / esempio per il commerciante:** Se stai utilizzando un tema personalizzato che visualizza contenuti interattivi (come fisarmoniche o schede) creati con MyQuill, e questi elementi non vengono renderizzati correttamente, abilitare questa opzione potrebbe risolvere il problema. Per la maggior parte dei negozi, non è necessario.

**3. Carica Editor Quill nel Back Office**
-   **Cosa fa questa impostazione:** Controlla se le risorse dell'editor Quill vengono caricate nel tuo Back Office PrestaShop. Questo è essenziale per il funzionamento del modulo.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* L'editor Quill si caricherà e funzionerà correttamente nel tuo Back Office.
    -   *Quando disabilitato (NO):* L'editor Quill non si caricherà e probabilmente vedrai un'area editor vuota o il TinyMCE predefinito. Questo disabilita di fatto la funzionalità core del modulo nel Back Office.
-   **Valore consigliato:** **SÌ** (Questo deve essere abilitato affinché il modulo funzioni).
-   **Scenario / esempio per il commerciante:** Dovresti sempre mantenerlo abilitato. Disabilitarlo ti impedirebbe di utilizzare le funzionalità di MyQuill nel pannello di amministrazione.

**4. Altezza Editor (in pixel)**
-   **Cosa fa questa impostazione:** Imposta l'altezza predefinita dell'area di input dell'editor Quill in pixel.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su un valore più alto (es. 500px):* L'editor apparirà più alto, dandoti più spazio verticale per visualizzare e modificare i tuoi contenuti senza scorrere.
    -   *Quando impostato su un valore più basso (es. 200px):* L'editor sarà più corto, il che potrebbe essere utile per sezioni di contenuto più brevi ma potrebbe richiedere più scorrimento per descrizioni più lunghe.
-   **Valore consigliato:** **300px** (o regola in base alle tue preferenze per la lunghezza tipica del contenuto).
-   **Scenario / esempio per il commerciante:** Se scrivi frequentemente descrizioni di prodotti molto lunghe, aumentare questo valore a 400px o 500px potrebbe rendere la tua esperienza di editing più confortevole. Per titoli di pagine CMS brevi, un'altezza minore potrebbe andare bene.

**5. Opzioni Barra degli Strumenti Editor**
-   **Cosa fa questa impostazione:** Ti permette di personalizzare quali strumenti appaiono nella barra degli strumenti dell'editor Quill. Puoi selezionare o deselezionare vari pulsanti e funzionalità.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando le opzioni sono selezionate:* I pulsanti corrispondenti (es. grassetto, corsivo, immagine, video, tabella) appariranno nella barra degli strumenti dell'editor, rendendo quelle funzioni disponibili per te.
    -   *Quando le opzioni sono deselezionate:* I pulsanti corrispondenti saranno nascosti dalla barra degli strumenti, impedendone l'uso.
-   **Valore consigliato:** Abilita tutte le opzioni inizialmente, quindi deseleziona gli strumenti che sei certo non userai mai per semplificare la barra degli strumenti.
-   **Scenario / esempio per il commerciante:** Se non prevedi mai di incorporare video, potresti deselezionare l'opzione "YouTube/Vimeo" per ridurre l'ingombro nella barra degli strumenti. Se vuoi assicurarti che il tuo team utilizzi solo la formattazione di base, potresti limitare significativamente le opzioni.

**6. Cartella Caricamento Immagini**
-   **Cosa fa questa impostazione:** Specifica la cartella predefinita sul tuo server dove verranno archiviate le immagini caricate tramite l'editor Quill.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su un percorso specifico (es. `/img/cms/`):* Tutte le immagini caricate tramite l'editor andranno in quella cartella.
    -   *Quando lasciato come predefinito (solitamente `/img/cms/` o simile):* Le immagini verranno archiviate nella directory standard delle immagini CMS di PrestaShop.
-   **Valore consigliato:** Lascia come predefinito (`/img/cms/`) a meno che tu non abbia una specifica esigenza organizzativa per cambiarlo.
-   **Scenario / esempio per il commerciante:** Se vuoi mantenere le immagini specifiche del prodotto separate dalle immagini delle pagine CMS, potresti creare una nuova cartella (es. `/img/products_quill/`) e impostare questa opzione di conseguenza. Assicurati che la cartella esista e abbia i permessi di scrittura.

**7. Abilita Generazione Link SEO**
-   **Cosa fa questa impostazione:** Attiva una funzionalità che ti aiuta a creare link SEO-friendly all'interno dei tuoi contenuti.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Lo strumento link in Quill offrirà opzioni per generare link puliti e descrittivi, potenzialmente utilizzando i nomi di prodotti o categorie come testo del link.
    -   *Quando disabilitato (NO):* Lo strumento link si comporterà come un inseritore di link standard senza miglioramenti SEO specifici.
-   **Valore consigliato:** **SÌ** (per beneficiare di un migliore linking interno per il SEO).
-   **Scenario / esempio per il commerciante:** Quando si collega a un prodotto, invece di incollare semplicemente l'URL, questa funzione potrebbe aiutarti a generare automaticamente un link con il nome del prodotto come testo di ancoraggio, il che è migliore per il SEO.

**8. Abilita Incorporamento YouTube/Vimeo**
-   **Cosa fa questa impostazione:** Ti permette di incorporare video da YouTube e Vimeo direttamente nei tuoi contenuti utilizzando l'editor Quill.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Apparirà un pulsante o un'opzione dedicata nella barra degli strumenti per incollare facilmente gli URL dei video e incorporarli.
    -   *Quando disabilitato (NO):* Non potrai utilizzare lo strumento dedicato per l'incorporamento di video.
-   **Valore consigliato:** **SÌ** (se prevedi di utilizzare video nei tuoi contenuti).
-   **Scenario / esempio per il commerciante:** Puoi facilmente aggiungere un video dimostrativo del prodotto a una descrizione del prodotto o un video sulla storia del marchio alla tua pagina "Chi siamo".

**9. Abilita Tabelle**
-   **Cosa fa questa impostazione:** Aggiunge la funzionalità per creare e modificare tabelle HTML all'interno dell'editor Quill.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Uno strumento di creazione tabelle sarà disponibile nella barra degli strumenti, permettendoti di inserire e gestire tabelle (aggiungere righe/colonne, unire celle, ecc.).
    -   *Quando disabilitato (NO):* Lo strumento tabella sarà nascosto.
-   **Valore consigliato:** **SÌ** (le tabelle sono utili per visualizzare dati strutturati come specifiche o confronti).
-   **Scenario / esempio per il commerciante:** Utilizza le tabelle per visualizzare le specifiche del prodotto, i grafici di confronto o le informazioni sulle tariffe di spedizione su una pagina CMS.

**10. Abilita Pulsanti Bootstrap**
-   **Cosa fa questa impostazione:** Fornisce uno strumento per inserire facilmente pulsanti in stile Bootstrap nei tuoi contenuti, che possono essere utilizzati per le call to action.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Apparirà uno strumento pulsante, che ti permetterà di scegliere stili di pulsante (primary, secondary, success, ecc.) e collegarli.
    -   *Quando disabilitato (NO):* Lo strumento pulsante sarà nascosto.
-   **Valore consigliato:** **SÌ** (per chiare call to action).
-   **Scenario / esempio per il commerciante:** Aggiungi un pulsante "Acquista ora" a un banner promozionale su una pagina CMS o un pulsante "Scarica PDF" alle specifiche tecniche di un prodotto.

**11. Abilita Schede**
-   **Cosa fa questa impostazione:** Ti permette di creare sezioni di contenuto a schede, utili per organizzare grandi quantità di informazioni in modo compatto.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Sarà disponibile uno strumento di creazione schede, che ti permetterà di definire titoli e contenuti per ogni scheda.
    -   *Quando disabilitato (NO):* Lo strumento schede sarà nascosto.
-   **Valore consigliato:** **SÌ** (per una migliore organizzazione dei contenuti).
-   **Scenario / esempio per il commerciante:** Su una pagina prodotto, usa le schede per "Descrizione", "Specifiche", "Recensioni" e "Informazioni sulla spedizione" per mantenere la pagina pulita.

**12. Abilita Gallerie**
-   **Cosa fa questa impostazione:** Integra una funzionalità per creare semplici gallerie di immagini all'interno dei tuoi contenuti.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Apparirà uno strumento galleria, che ti permetterà di selezionare più immagini e organizzarle in una galleria.
    -   *Quando disabilitato (NO):* Lo strumento galleria sarà nascosto.
-   **Valore consigliato:** **SÌ** (per display di immagini visivamente accattivanti).
-   **Scenario / esempio per il commerciante:** Mostra più angolazioni di un prodotto o una collezione di immagini lifestyle su una pagina CMS.

**13. Abilita FAQ (Fisarmonica)**
-   **Cosa fa questa impostazione:** Aggiunge uno strumento per creare sezioni FAQ interattive utilizzando un formato a fisarmonica (espandibile/collassabile).
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Sarà disponibile uno strumento FAQ, che ti permetterà di aggiungere coppie domanda-risposta che gli utenti possono espandere o collassare.
    -   *Quando disabilitato (NO):* Lo strumento FAQ sarà nascosto.
-   **Valore consigliato:** **SÌ** (eccellente per pagine di supporto o FAQ sui prodotti).
-   **Scenario / esempio per il commerciante:** Crea una pagina CMS dedicata alle "Domande Frequenti" o aggiungi una piccola sezione FAQ a una pagina prodotto per rispondere alle domande comuni dei clienti.

#### **Pulsante Salva**
-   **Cosa fa:** Dopo aver apportato modifiche alle impostazioni in questa pagina, **devi** cliccare sul pulsante "Salva" per applicarle.
-   **Effetto del clic:** Le tue modifiche verranno memorizzate nel database e l'editor Quill rifletterà queste nuove impostazioni la prossima volta che lo aprirai nel Back Office.
-   **Azione consigliata:** Clicca sempre su "Salva" dopo aver modificato qualsiasi impostazione.

### 2.2 Schermate di amministrazione dedicate e viste del controller

MyQuill si integra principalmente direttamente nelle schermate di modifica dei contenuti esistenti di PrestaShop (come i moduli di modifica di prodotti, categorie e pagine CMS). Non introduce nuove voci di menu di primo livello o schermate dedicate di gestione dei dati per i propri contenuti. I controller "AdminMyquillAjaxController" e "index.php" sono componenti interni che gestiscono le operazioni in background del modulo, come il caricamento di immagini o il caricamento dinamico di contenuti per le funzionalità dell'editor.

Pertanto, non esiste una schermata "AdminMyquill" separata da gestire. Tutta l'interazione avviene direttamente all'interno dei moduli di modifica dei contenuti dove Quill sostituisce TinyMCE.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
|---|---|---|---|
| **Pagina di configurazione del modulo** | Abilita Editor MyQuill | SÌ | Attiva/disattiva l'editor Quill nel BO. |
| | Carica Editor Quill nel Front Office | NO | Carica le risorse di Quill nel FO (solo se necessario per tema/modulo). |
| | Carica Editor Quill nel Back Office | SÌ | Carica le risorse di Quill nel BO (essenziale per la funzione del modulo). |
| | Altezza Editor (in pixel) | 300px | Imposta la dimensione verticale della finestra dell'editor. |
| | Opzioni Barra degli Strumenti Editor | Tutte abilitate | Personalizza quali strumenti appaiono nella barra degli strumenti dell'editor. |
| | Cartella Caricamento Immagini | `/img/cms/` | Specifica dove vengono archiviate le immagini caricate. |
| | Abilita Generazione Link SEO | SÌ | Aggiunge funzionalità per la creazione di link SEO-friendly. |
| | Abilita Incorporamento YouTube/Vimeo | SÌ | Permette di incorporare video da YouTube/Vimeo. |
| | Abilita Tabelle | SÌ | Aggiunge funzionalità per creare e modificare tabelle HTML. |
| | Abilita Pulsanti Bootstrap | SÌ | Fornisce uno strumento per inserire pulsanti in stile Bootstrap. |
| | Abilita Schede | SÌ | Permette di creare sezioni di contenuto a schede. |
| | Abilita Gallerie | SÌ | Integra una funzionalità per creare gallerie di immagini. |
| | Abilita FAQ (Fisarmonica) | SÌ | Aggiunge uno strumento per creare sezioni FAQ interattive. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Dopo aver installato MyQuill, l'area dell'editor è vuota o mostra ancora TinyMCE.**
*   **R:** Innanzitutto, assicurati che "Abilita Editor MyQuill" e "Carica Editor Quill nel Back Office" siano entrambi impostati su **SÌ** nella configurazione del modulo. In secondo luogo, svuota la cache di PrestaShop: vai su **Parametri Avanzati > Prestazioni**, quindi clicca su "Svuota la cache" nell'angolo in alto a destra. Inoltre, svuota la cache del tuo browser.

**D2: Le mie immagini non vengono caricate o non riesco a vederle dopo il caricamento.**
*   **R:** Controlla l'impostazione "Cartella Caricamento Immagini" nella configurazione di MyQuill. Assicurati che la cartella specificata esista sul tuo server (es. `/img/cms/`) e abbia i permessi di scrittura corretti (solitamente 755 o 775). Se la cartella non esiste, creala tramite FTP/SFTP.

**D3: Alcuni pulsanti della barra degli strumenti (es. Tabelle, Video) mancano dall'editor.**
*   **R:** Vai alla pagina di configurazione di MyQuill e controlla la sezione "Opzioni Barra degli Strumenti Editor". Assicurati che le funzionalità specifiche che desideri utilizzare (es. "Abilita Tabelle", "Abilita Incorporamento YouTube/Vimeo") siano impostate su **SÌ**. Salva le modifiche e svuota la cache.

**D4: Il contenuto creato con MyQuill (come schede o fisarmoniche) non viene visualizzato correttamente nel mio front office.**
*   **R:** Questo accade spesso se il tuo tema non include il CSS o JavaScript necessario per questi elementi interattivi. Prova ad abilitare "Carica Editor Quill nel Front Office" nella configurazione di MyQuill. Se il problema persiste, il tuo tema potrebbe richiedere specifiche librerie Bootstrap o JavaScript che non vengono caricate per impostazione predefinita o sono in conflitto. In questo caso, potresti aver bisogno di un webmaster per indagare.

**D5: Come faccio a tornare all'editor TinyMCE predefinito?**
*   **R:** Vai semplicemente su **Moduli > Gestione moduli**, trova "MyQuill - Quill editor" e clicca sul pulsante "Disabilita". Tutti i contenuti precedentemente creati con MyQuill saranno ancora presenti, ma l'interfaccia di editing tornerà a TinyMCE. Puoi riabilitare MyQuill in qualsiasi momento.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)
Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura
Il modulo MyQuill integra l'editor di testo ricco Quill.js nel Back Office di PrestaShop, sostituendo il TinyMCE predefinito. Lo fa agganciandosi a `displayBackOfficeHeader` per iniettare le sue risorse e quindi utilizzando JavaScript per mirare e inizializzare le istanze di Quill su elementi textarea pertinenti. Il modulo fornisce funzionalità avanzate come il caricamento di immagini, l'incorporamento di video e blocchi di contenuto personalizzati (tabelle, schede, gallerie, FAQ) estendendo la funzionalità di Quill e fornendo endpoint AJAX per operazioni lato server. Evita le sovrascritture del core, garantendo compatibilità e facile disinstallazione.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:
    Il modulo non include alcun controller front-office dedicato. Tutte le funzionalità front-office relative alla visualizzazione di contenuti generati da Quill sono gestite dal rendering del tema dei contenuti standard di PrestaShop (descrizioni prodotti, pagine CMS, ecc.) e dal caricamento opzionale delle risorse front-office di MyQuill tramite hook.

-   **Controller Admin Back-Office**:
    *   `controllers/admin/AdminMyquillAjaxController.php`
        *   **Nome classe e classe padre**: `AdminMyquillAjaxController` estende `ModuleAdminController`.
        *   **Responsabilità**: Questo controller gestisce le richieste AJAX provenienti dall'editor Quill nel Back Office. Il suo ruolo principale è gestire le operazioni lato server come il caricamento di immagini, assicurando che siano correttamente archiviate nella directory designata e restituendo l'URL per l'inserimento nell'editor. Potrebbe anche gestire altre richieste di dati dinamici per plugin specifici di Quill (es. recupero dati prodotto per link SEO).
    *   `controllers/admin/index.php`
        *   **Nome classe e classe padre**: Questo file contiene tipicamente una semplice istruzione `die('Access Denied');` o una misura di sicurezza simile.
        *   **Responsabilità**: È una pratica standard di PrestaShop includere un file `index.php` in ogni directory per prevenire l'elenco delle directory e l'accesso diretto. Non contiene alcuna logica funzionale del controller per il modulo.

### 4.3 Classi e modelli core (`classes/`)
Il modulo MyQuill non introduce alcuna classe `ObjectModel` personalizzata o tabelle di database. Opera principalmente sostituendo l'interfaccia dell'editor e memorizzando la sua configurazione in `ps_configuration`. Il contenuto creato con Quill viene memorizzato direttamente nei campi di contenuto esistenti di PrestaShop (es. `ps_product_lang.description`, `ps_cms_lang.content`) come HTML standard.

### 4.4 Risorse JavaScript (`views/js/`)

-   `views/js/myquill-admin.js`
    *   **Ambito**: Back-office.
    *   **Dettaglio**: Questo è il principale file JavaScript amministrativo. È responsabile dell'inizializzazione dell'editor Quill su tutti gli elementi textarea pertinenti all'interno del Back Office di PrestaShop. Legge le impostazioni di configurazione del modulo (altezza dell'editor, opzioni della barra degli strumenti, funzionalità abilitate) e costruisce dinamicamente l'istanza di Quill con i moduli e i gestori appropriati. Contiene anche la logica per integrare pulsanti personalizzati della barra degli strumenti e gestire le loro azioni (es. apertura di finestre di dialogo per il caricamento di immagini, inserimento di video incorporati).
-   `views/js/myquill-editor.js`
    *   **Ambito**: Back-office.
    *   **Dettaglio**: Questo file contiene probabilmente la libreria Quill.js stessa o personalizzazioni/estensioni specifiche dell'editor Quill di base. Definisce il comportamento fondamentale dell'editor, il rendering e l'API.
-   `views/js/myquill-front.js`
    *   **Ambito**: Front-office.
    *   **Dettaglio**: Questo script viene caricato condizionalmente nel front office se l'impostazione "Carica Editor Quill nel Front Office" è abilitata. Contiene il JavaScript necessario per rendere funzionali gli elementi interattivi creati con Quill (come schede, fisarmoniche, gallerie) sul lato cliente del negozio. Potrebbe includere listener per eventi di clic sulle intestazioni delle schede o sui titoli delle fisarmoniche per attivare la visibilità del contenuto.
-   `views/js/myquill-plugins.js`
    *   **Ambito**: Back-office.
    *   **Dettaglio**: Questo file incapsula la logica JavaScript per vari plugin ed estensioni personalizzati aggiunti a Quill da MyQuill. Ciò include l'implementazione per funzionalità come la gestione del caricamento di immagini, l'incorporamento di video, la creazione di tabelle, i pulsanti Bootstrap, le schede, le gallerie e le fisarmoniche FAQ. Definisce come vengono renderizzati questi "blot" personalizzati (termine di Quill per i blocchi di contenuto personalizzati) e come si comportano le loro azioni associate alla barra degli strumenti.
-   `views/js/myquill-pro.js`
    *   **Ambito**: Back-office.
    *   **Dettaglio**: Questo file contiene probabilmente funzionalità e miglioramenti avanzati o "pro" per l'editor Quill, potenzialmente basandosi su `myquill-plugins.js`. Potrebbe includere elementi UI più sofisticati, opzioni di formattazione aggiuntive o ulteriori integrazioni specifiche della versione MyPresta.eu del modulo.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `views/css/myquill-admin.css`
    *   **Ambito**: Stile del modulo di amministrazione del Back-office.
    *   **Dettaglio**: Contiene stili specifici per l'aspetto dell'editor Quill all'interno del Back Office di PrestaShop. Questo include lo stile per la barra degli strumenti, il contenitore dell'editor, le finestre di dialogo personalizzate e garantisce che l'editor si integri visivamente con il tema di amministrazione di PrestaShop.
-   `views/css/myquill-editor.css`
    *   **Ambito**: Stile del modulo di amministrazione del Back-office.
    *   **Dettaglio**: Questo file contiene probabilmente il CSS core per l'editor Quill stesso, definendo gli stili di base per la formattazione del testo, le citazioni, gli elenchi e altri elementi standard di Quill. Potrebbe anche includere stili per blot personalizzati (es. tabelle, pulsanti) quando renderizzati all'interno dell'editor.
-   `views/css/myquill-front.css`
    *   **Ambito**: Stile del cliente del Front-office.
    *   **Dettaglio**: Questo foglio di stile viene caricato condizionalmente nel front office se l'impostazione corrispondente è abilitata. Fornisce il CSS necessario per renderizzare correttamente gli elementi interattivi creati con MyQuill (come schede, fisarmoniche, gallerie) nel negozio rivolto al cliente. Gli sviluppatori possono sovrascrivere questi stili nel `custom.css` o `theme.css` del loro tema per adattarli al loro brand.
-   `views/css/quill.snow.css`
    *   **Ambito**: Stile del modulo di amministrazione del Back-office.
    *   **Dettaglio**: Questo è il foglio di stile standard del tema "Snow" per Quill.js. Fornisce l'aspetto visivo predefinito per la barra degli strumenti e l'area del contenuto dell'editor Quill, incluse icone, stili dei pulsanti e formattazione di base. Questo è un componente core di Quill.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**:
    *   `bo-header.tpl`
        *   **Hook**: `displayBackOfficeHeader`
        *   **Output**: Questo template è responsabile dell'iniezione delle risorse CSS e JavaScript necessarie (Quill core, JS/CSS specifici del modulo) nella sezione `<head>` delle pagine del Back Office dove è necessario l'editor. Include dinamicamente i file in base alla configurazione del modulo.
-   **Template admin (`views/templates/admin/`)**:
    *   `configure.tpl`
        *   **Output**: Questo template renderizza il modulo di configurazione principale per il modulo MyQuill, accessibile tramite **Moduli > Gestione moduli > Configura**. Visualizza tutte le impostazioni descritte nella Sezione 4.1, inclusi interruttori, campi di input e il pulsante "Salva".
    *   `preview.tpl`
        *   **Output**: Questo template potrebbe essere utilizzato per una funzione di anteprima all'interno del Back Office, mostrando potenzialmente come il contenuto generato da Quill apparirebbe nel front end. Il suo utilizzo esatto dipenderebbe dall'implementazione interna del modulo per l'anteprima del contenuto.

-   **Template front-office (`views/templates/front/`)**:
    Il modulo non include alcun template front-office dedicato. Tutto il contenuto generato da Quill viene renderizzato all'interno dei template del tema PrestaShop esistenti (es. `product.tpl`, `cms.tpl`) inserendo l'output HTML grezzo dall'editor.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**:
    Il modulo MyQuill non crea alcuna tabella di database personalizzata. Tutte le sue impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` utilizzando chiavi tipicamente prefissate con `MYQUILL_`. Il contenuto creato con l'editor viene memorizzato nelle tabelle di contenuto standard di PrestaShop (es. `ps_product_lang`, `ps_cms_lang`).

-   **Tabella degli hook registrati**:

| Nome Hook | Momento di esecuzione | Scopo tecnico |
|---|---|---|
| `displayBackOfficeHeader` | Eseguito nell' `<head>` delle pagine del Back Office. | Inietta le risorse CSS e JavaScript di MyQuill (editor Quill, plugin, stili admin) nel Back Office per inizializzare l'editor. |
| `displayHeader` | Eseguito nell' `<head>` delle pagine del Front Office. | Inietta condizionalmente le risorse CSS e JavaScript del front-office di MyQuill se "Carica Editor Quill nel Front Office" è abilitato, per garantire che gli elementi interattivi (schede, fisarmoniche) funzionino correttamente. |
| `displayFooter` | Eseguito alla fine del `<body>` delle pagine del Front Office. | Potenzialmente utilizzato per iniettare script a caricamento tardivo o risorse aggiuntive per elementi interattivi del front-office, se non gestito da `displayHeader`. |
| `displayProductExtraContent` | Eseguito sulla pagina del prodotto. | Permette di iniettare blocchi di contenuto aggiuntivi sulla pagina del prodotto, potenzialmente utile per contenuti personalizzati generati da Quill se il modulo fosse esteso per gestire tali blocchi direttamente. (Meno probabile che venga utilizzato direttamente dalla funzione di sostituzione dell'editor core di MyQuill, ma disponibile per estensioni). |
| `displayLeftColumn` | Eseguito nella colonna sinistra delle pagine del Front Office. | Simile a `displayProductExtraContent`, fornisce un hook per iniettare contenuto nella colonna sinistra. |
| `displayRightColumn` | Eseguito nella colonna destra delle pagine del Front Office. | Simile a `displayProductExtraContent`, fornisce un hook per iniettare contenuto nella colonna destra. |

## 5. Supporto ufficiale e aggiornamenti
Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo MyQuill - Quill editor, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). È possibile scaricare le versioni più recenti dalla cronologia degli ordini e accedere alle risorse di supporto direttamente dal sito web di MyPresta.eu.
