---
title: "tinyMCE pro - editor di testo avanzato - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop tinyMCE pro - editor di testo avanzato di MyPresta.eu."
sidebar:
  label: "tinyMCE pro - editor di testo avanzato - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo tinyMCE pro - extended rich text editor su MyPresta.eu](https://mypresta.eu/modules/administration-tools/tinymce-pro-extended-rich-text-editor.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/tinymce-pro-extended-rich-text-editor/)
>
> ---


# tinyMCE pro - editor di testo avanzato

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server oltre a un ambiente di hosting PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" per accedere alle impostazioni principali del modulo. Questa schermata ti consente di abilitare o disabilitare l'editor avanzato e di gestire le sue funzionalità principali.

La pagina di configurazione per "tinyMCE pro" è progettata per essere semplice, poiché il modulo funziona principalmente sostituendo e migliorando l'editor esistente senza ampie impostazioni rivolte all'utente oltre alla sua attivazione.

-   **Cosa fa questa impostazione:** Questo modulo funziona principalmente sostituendo l'editor predefinito di PrestaShop con una versione migliorata di tinyMCE. La pagina di configurazione conterrà tipicamente un interruttore "Abilita/Disabilita" per il modulo stesso, e potenzialmente opzioni per controllare a quali aree specifiche del back office l'editor avanzato dovrebbe applicarsi.
-   **Effetto della modifica di questa impostazione:**

    -   *Quando abilitato:* L'editor di testo standard, spesso limitato, in aree come le descrizioni dei prodotti, le pagine CMS e le descrizioni delle categorie verrà sostituito dall'editor "tinyMCE pro". Questo nuovo editor presenterà una barra degli strumenti più ricca con opzioni per le icone Font Awesome, l'incorporamento di video di YouTube, l'accettazione di codice HTML/JavaScript avanzato e altro ancora.
    -   *Quando disabilitato:* Il modulo cesserà di funzionare e PrestaShop tornerà al suo editor di testo predefinito. Tutte le funzionalità avanzate fornite da "tinyMCE pro" non saranno più disponibili.
-   **Valore consigliato:** **Abilitato**. Per beneficiare delle funzionalità del modulo, dovrebbe essere sempre abilitato.
-   **Scenario / esempio per il commerciante:** Stai modificando la descrizione di un prodotto per un nuovo articolo. Con "tinyMCE pro" abilitato, puoi facilmente aggiungere un video di YouTube che mostra il prodotto, includere icone Font Awesome per le funzionalità (ad esempio, un'icona di spunta per "Disponibile"), e utilizzare la formattazione avanzata per creare un layout visivamente accattivante, tutto direttamente all'interno dell'editor. Se disabilitato, saresti limitato alla formattazione di testo di base.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | **Stato del modulo (Abilita/Disabilita)** | Abilitato | Controlla se l'editor tinyMCE avanzato sostituisce l'editor PrestaShop predefinito nel back office. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D1: Ho abilitato il modulo, ma l'editor ha ancora lo stesso aspetto. Cosa devo fare?**
**R1:** Dopo aver abilitato qualsiasi modulo che modifica il back office, è buona pratica svuotare la cache del browser e la cache Smarty di PrestaShop.
-   **Cache del browser:** Aggiorna la pagina del browser (Ctrl+F5 o Cmd+Shift+R).
-   **Cache di PrestaShop:** Vai su **Parametri avanzati > Prestazioni** nel back office di PrestaShop. Clicca sul pulsante "Svuota la cache" nell'angolo in alto a destra.

**D2: Alcune delle nuove funzionalità dell'editor (come le icone Font Awesome) non vengono visualizzate correttamente nel mio front office.**
**R2:** Questo di solito indica un conflitto con il CSS o JavaScript del tuo tema personalizzato.
-   **Verifica i conflitti:** Passa temporaneamente al tema PrestaShop predefinito (Classic o Hummingbird) e verifica se le funzionalità vengono visualizzate correttamente. Se lo fanno, il problema è con il tuo tema personalizzato.
-   **Personalizzazione del tema:** Il tuo tema potrebbe sovrascrivere o non includere il CSS/JS necessario per questi elementi. Potrebbe essere necessario consultare lo sviluppatore del tuo tema o un webmaster per integrare correttamente le risorse front-office del modulo nel tuo tema.

**D3: Posso usare questo editor per tutte le lingue del mio negozio?**
**R3:** Sì, l'editor tinyMCE è progettato per funzionare senza problemi con le capacità multilingue di PrestaShop. Quando cambi lingua nel back office, l'editor sarà comunque disponibile per inserire contenuti nella lingua selezionata. Il modulo include anche file di lingua per molti dei suoi plugin (ad esempio, Font Awesome, PowerPaste), garantendo un'esperienza localizzata dove disponibile.

**D4: Vedo un errore dopo aver installato il modulo, o il mio back office è lento.**
**R4:**
-   **Controlla i log degli errori del server:** Il primo passo è sempre controllare i log degli errori PHP del tuo server. Questi log spesso forniscono dettagli specifici su cosa è andato storto.
-   **Disabilita altri moduli:** Disabilita temporaneamente altri moduli installati di recente o complessi per escludere conflitti.
-   **Versione PHP:** Assicurati che la tua versione PHP rientri nell'intervallo supportato (PHP 7.1 - 8.5). Una versione PHP incompatibile può causare vari problemi.
-   **Contatta il supporto:** Se il problema persiste, raccogli eventuali messaggi di errore e contatta il supporto MyPresta.eu per assistenza.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo `tinyMCE pro` funziona principalmente sovrascrivendo la classe `Validate` predefinita di PrestaShop per garantire la compatibilità con il contenuto HTML esteso generato dall'editor tinyMCE migliorato. Inietta la propria versione della libreria tinyMCE e una moltitudine di plugin nel back office, sostituendo efficacemente l'editor standard. La logica principale del modulo risiede in `index.php`, che gestisce l'installazione, la disinstallazione e il modulo di configurazione. Sfrutta il sistema di hook di PrestaShop per caricare le sue risorse e inizializzare l'editor dove necessario.

### 4.2 Controller (`controllers/`)

Questo modulo non introduce alcun controller front-office o back-office personalizzato. La sua funzionalità è principalmente integrata tramite il file principale del modulo (`index.php`) e sovrascrivendo le classi core di PrestaShop.

### 4.3 Classi e Modelli Core (`classes/`)

-   **`tinymcepro/override/classes/index.php`**: Questo file è tipicamente un segnaposto vuoto per prevenire l'elenco delle directory, una pratica di sicurezza comune. Non contiene alcuna definizione di classe funzionale.
-   **`tinymcepro/override/classes/Validate.php`**:
    -   **Scopo**: Questa è una sovrascrittura cruciale. La classe `Validate` di PrestaShop è responsabile della sanificazione e della validazione di vari input, incluso il contenuto HTML. Il metodo `isCleanHtml()` predefinito può essere eccessivamente restrittivo per contenuti ricchi, rimuovendo elementi HTML5 validi, attributi o JavaScript che l'editor tinyMCE esteso potrebbe generare.
    -   **Logica di sovrascrittura**: Questa sovrascrittura probabilmente modifica o estende il metodo `isCleanHtml()` (o metodi di validazione correlati) per consentire una gamma più ampia di HTML, attributi e potenzialmente script/stili incorporati, garantendo che il contenuto generato da tinyMCE pro non venga rimosso o considerato non valido dalla validazione core di PrestaShop.
    -   **Impatto**: Gli sviluppatori dovrebbero essere consapevoli che questa sovrascrittura modifica il comportamento di validazione core. Se sono presenti regole di validazione personalizzate o altri moduli si basano su `isCleanHtml()` rigoroso, potrebbero sorgere conflitti.

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo include una vasta gamma di file JavaScript, principalmente per la libreria core di tinyMCE e i suoi numerosi plugin.

-   **`tinymcepro/js/accordion.js`**: Probabilmente uno script personalizzato per gestire la funzionalità a fisarmonica nel front-office, possibilmente correlato al plugin tinyMCE `bootstrapaccordion`.
-   **`tinymcepro/js/alerts.js`**: Script personalizzato per la gestione dei messaggi di avviso, potenzialmente legato a un plugin di avviso Bootstrap.
-   **`tinymcepro/js/fancybox.js`**: Integrazione della libreria Fancybox per lightbox, probabilmente utilizzata per la visualizzazione di immagini o media all'interno dell'output dell'editor.
-   **`tinymcepro/js/readmore.js`**: Script per implementare la funzionalità "leggi di più", che comprime sezioni di contenuto lunghe.
-   **`tinymcepro/js/tinymce-cmscategory.js`**: Script di inizializzazione o configurazione specifico per tinyMCE quando utilizzato nei campi di descrizione di CMS o categoria.
-   **`tinymcepro/lib/htmlTemplatesManager/js/htmlTemplatesManager.js`**: JavaScript core per il plugin HTML Templates Manager, che consente la creazione, la modifica e l'inserimento di frammenti HTML predefiniti.
-   **`tinymcepro/lib/plugins/bootstrapaccordion/plugin.js`**: Plugin tinyMCE per l'inserimento e la gestione di fisarmoniche in stile Bootstrap.
-   **`tinymcepro/lib/plugins/codesample/plugin.js`**: Plugin tinyMCE per l'inserimento e l'evidenziazione della sintassi di esempi di codice. Include `prism.css` per lo stile.
-   **`tinymcepro/lib/plugins/editattributes/plugin.js`**: Plugin tinyMCE per modificare facilmente gli attributi HTML degli elementi selezionati.
-   **`tinymcepro/lib/plugins/fontawesome/langs/*.js`**: File di lingua per il plugin tinyMCE Font Awesome.
-   **`tinymcepro/lib/plugins/lineheight/index.js`, `langs/de.js`, `plugin.js`**: Plugin tinyMCE per controllare l'altezza della linea del testo.
-   **`tinymcepro/lib/plugins/paragraph/*.js`**: Un plugin complesso per la gestione degli stili di paragrafo e potenzialmente la visualizzazione di elementi a blocco. Include diversi script di utilità interni.
-   **`tinymcepro/lib/plugins/powerpaste/*.js`**: Plugin tinyMCE avanzato per la pulizia e la sanificazione del contenuto incollato da Microsoft Word, Google Docs, ecc. Include molti file di lingua.
-   **`tinymcepro/lib/plugins/smileys/plugin.js`**: Plugin tinyMCE per l'inserimento di emoji/smiley.
-   **`tinymcepro/lib/plugins/youtube/includes/youtube.js`, `plugin.js`**: Plugin tinyMCE per l'incorporamento di video di YouTube.
-   **`tinymcepro/lib/tinymce.inc.js`**: Probabilmente il file della libreria core principale di tinyMCE, o un file di build/configurazione personalizzato per l'editor.
-   **`tinymcepro/lib/tinymce_loader.js`**: Script responsabile del caricamento e dell'inizializzazione delle istanze dell'editor tinyMCE nel back office di PrestaShop.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`tinymcepro/css/tinymcepro.css`**: Stili personalizzati generali per il modulo, potenzialmente per la sua pagina di configurazione o elementi del front-office.
-   **`tinymcepro/css.css`**: Un altro foglio di stile generale, possibilmente per versioni precedenti di PrestaShop o elementi UI specifici.
-   **`tinymcepro/lib/editor.css`**: CSS core per l'editor tinyMCE stesso, che definisce il suo aspetto all'interno del back office.
-   **`tinymcepro/lib/htmlTemplatesManager/css/htmlTemplatesManager.css`**: Stili per l'interfaccia di HTML Templates Manager.
-   **`tinymcepro/lib/iconset.css`**: Probabilmente contiene stili per icone personalizzate utilizzate all'interno dell'editor o del modulo.
-   **`tinymcepro/lib/plugins/bs_alert/assets/css/bootstrap.css`, `plugin.css`**: CSS di Bootstrap e stili specifici del plugin per il plugin tinyMCE Bootstrap Alert.
-   **`tinymcepro/lib/plugins/bs_images/assets/css/bootstrap.css`, `plugin.css`**: CSS di Bootstrap e stili specifici del plugin per il plugin tinyMCE Bootstrap Images.
-   **`tinymcepro/lib/plugins/codesample/css/prism.css`**: Foglio di stile per l'evidenziazione della sintassi utilizzato dal plugin `codesample`.
-   **`tinymcepro/lib/plugins/powerpaste/css/editorcss.css`**: Stili specifici per il plugin PowerPaste, potenzialmente per il feedback visivo durante l'incollaggio.
-   **`tinymcepro/lib/plugins/tinyplusBootstrapTools/flat-blue.css`, `res-show-blocks-style.css`**: Stili aggiuntivi relativi a Bootstrap o alla visualizzazione dei blocchi, possibilmente per temi o strumenti specifici dell'editor.
-   **`tinymcepro/lib/plugins/youtube/includes/youtube.css`**: Stili per la funzionalità di incorporamento video di YouTube.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **`tinymcepro/header.tpl`**: Questo template è probabilmente agganciato a `displayHeader` per caricare le risorse CSS e JavaScript necessarie per il modulo, sia nel back office (per l'editor stesso) che potenzialmente nel front office (per il contenuto renderizzato come fisarmoniche o fancybox).
-   **`tinymcepro/lib/htmlTemplatesManager/views/buttonManager.tpl`**: Template per il pulsante o l'interfaccia che apre l'HTML Templates Manager.
-   **`tinymcepro/lib/htmlTemplatesManager/views/createTemplateForm.tpl`**: Template del modulo per la creazione di nuovi modelli HTML.
-   **`tinymcepro/lib/htmlTemplatesManager/views/editTemplateForm.tpl`**: Template del modulo per la modifica di modelli HTML esistenti.
-   **`tinymcepro/lib/htmlTemplatesManager/views/mainForm.tpl`**: Il template dell'interfaccia principale per l'HTML Templates Manager.
-   **`tinymcepro/lib/htmlTemplatesManager/views/selectInput.tpl`**: Un template riutilizzabile per un input a discesa di selezione all'interno del gestore di modelli.
-   **`tinymcepro/views/admin/fonts.tpl`**: Template relativo alla selezione o visualizzazione dei font, possibilmente per l'integrazione di font personalizzati all'interno dell'editor.
-   **`tinymcepro/views/admin/form.tpl`**: Il template del modulo di configurazione principale per il modulo, renderizzato tramite `getContent()` in `index.php`.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**: Questo modulo non sembra creare tabelle SQL personalizzate. Le sue impostazioni di configurazione sono memorizzate in `ps_configuration` (ad esempio, `PS_TINYMCEPRO_ENABLED`). I modelli HTML creati tramite `htmlTemplatesManager` potrebbero essere memorizzati in una tabella personalizzata o serializzati anche in `ps_configuration`, sebbene non sia presente alcun file SQL esplicito, suggerendo una creazione dinamica o una memorizzazione della configurazione.
-   **Tabella degli hook registrati**:

| Nome dell'Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayBackOfficeHeader` | Renderizza nella sezione `<head>` del back office di PrestaShop. | Inietta i file CSS e JavaScript necessari affinché l'editor tinyMCE e i suoi plugin funzionino. Qui vengono caricate la libreria core di tinyMCE e i suoi script di inizializzazione. |
| `actionAdminControllerSetMedia` | Eseguito quando un controller amministrativo imposta le sue risorse multimediali. | Consente al modulo di aggiungere i suoi file JS/CSS specifici alla pagina amministrativa corrente, garantendo che l'editor tinyMCE venga caricato solo sulle pagine in cui è necessario (ad esempio, modifica prodotto, modifica pagina CMS). |
| `actionGetContentEditor` | (Se hook personalizzato) | Questo hook verrebbe utilizzato per sostituire l'istanza dell'editor predefinita con l'editor tinyMCE migliorato del modulo. |
| `displayHeader` | Renderizza nella sezione `<head>` del front office. | Potenzialmente carica risorse specifiche del front office (come `accordion.js`, `fancybox.js`, `tinymcepro.css`) se il contenuto generato dall'editor richiede stili o JavaScript speciali per essere visualizzato correttamente (ad esempio, fisarmoniche, lightbox). |
| `displayRightColumn` | Renderizza nella colonna destra del front office. | (Improbabile che venga utilizzato direttamente per la funzionalità dell'editor, ma potrebbe essere utilizzato per visualizzare contenuti *creati* dall'editor se il modulo avesse un widget front-office). |
| `displayLeftColumn` | Renderizza nella colonna sinistra del front office. | (Simile a `displayRightColumn`). |
| `displayFooter` | Renderizza nel footer del front office. | Potrebbe essere utilizzato per caricare JavaScript o CSS non critici per la visualizzazione del front office. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e qualsiasi ulteriore assistenza con il modulo "tinyMCE pro - editor di testo avanzato", fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per aiutarvi con l'installazione, la configurazione e la risoluzione dei problemi.
"""
