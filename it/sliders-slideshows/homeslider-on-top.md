---
title: "Homeslider on top - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Homeslider on top di MyPresta.eu."
sidebar:
  label: "Homeslider on top - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Homeslider on top su MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/homeslider-on-top.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/sliders-slideshows/homeslider-on-top/)
>
> ---


# Homeslider on top

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per un'installazione PrestaShop e supporteranno questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

Questo modulo è progettato per essere estremamente semplice, agendo principalmente come un "ponte" per consentire la visualizzazione dello *slider di immagini predefinito di PrestaShop* in una nuova posizione. Pertanto, la sua schermata di configurazione è minimale. Le immagini dello slider, i link e le impostazioni (come velocità, pausa al passaggio del mouse, ecc.) sono gestiti tramite il modulo standard "Slider di immagini" di PrestaShop.

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo aver installato "Homeslider on top", vai su **Moduli > Gestione moduli**, cerca "Homeslider on top" e clicca su "Configura".

Troverai tipicamente un'interfaccia di configurazione molto semplice, focalizzata principalmente sull'abilitazione o disabilitazione della funzionalità principale del modulo.

- **Cosa fa questa impostazione:** Questa impostazione controlla se il modulo "Homeslider on top" è attivo e sta tentando di visualizzare il tuo slider di immagini nella posizione superiore designata.
- **Effetto della modifica di questa impostazione:**
  - *Quando abilitato:* Il modulo registrerà i suoi hook e tenterà di renderizzare lo slider di immagini predefinito di PrestaShop nella parte superiore del tuo negozio.
  - *Quando disabilitato:* Il modulo cesserà di funzionare e lo slider di immagini non apparirà nella posizione superiore (tornerà al suo posizionamento predefinito se il modulo standard Slider di immagini è ancora attivo e agganciato altrove).
- **Valore consigliato:** **SÌ** (Abilitato) se vuoi che il tuo slider appaia in alto.
- **Scenario / esempio del commerciante:** Hai appena lanciato una nuova collezione e vuoi metterla in evidenza con un grande banner nella parte superiore del tuo sito. Abiliteresti questo modulo. Se in seguito decidi di preferire lo slider in una posizione diversa (ad esempio, sotto l'intestazione), potresti disabilitare questo modulo e riagganciare il modulo standard Slider di immagini altrove.

**Nota importante:** Questo modulo *non* gestisce le immagini o le impostazioni dello slider stesso. Per aggiungere, modificare o rimuovere diapositive, o per cambiare il comportamento dello slider (come velocità di transizione, riproduzione automatica, ecc.), devi andare alla configurazione del modulo **"Slider di immagini"** (spesso trovato sotto **Moduli > Gestione moduli**, cerca "Slider di immagini" o "ps\_imageslider").

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Modulo Abilitato/Disabilitato | Abilitato | Controlla se il modulo visualizza attivamente lo slider di immagini nella parte superiore del negozio. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Il mio slider non viene visualizzato affatto, anche dopo aver abilitato il modulo.**
R:

1.  **Controlla il modulo "Slider di immagini":** Assicurati che il *modulo predefinito di PrestaShop "Slider di immagini"* (spesso chiamato `ps_imageslider`) sia installato, abilitato e abbia delle diapositive configurate. Questo modulo "Homeslider on top" cambia solo la *posizione* di quello slider esistente.
2.  **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). A volte, PrestaShop ha bisogno di un aggiornamento della cache per riconoscere i nuovi posizionamenti dei moduli.
3.  **Compatibilità del tema:** Sebbene progettato per un'ampia compatibilità, alcuni temi pesantemente personalizzati potrebbero sovrascrivere i comportamenti predefiniti degli hook. Se i problemi persistono, contatta lo sviluppatore del tuo tema o il supporto MyPresta.eu.

**D: Lo slider viene visualizzato, ma sembra strano o disallineato.**
R:

1.  **Controlla le impostazioni dello "Slider di immagini":** Assicurati che le immagini che hai caricato nel *modulo predefinito di PrestaShop "Slider di immagini"* siano di dimensioni coerenti e di alta qualità.
2.  **Stile del tema:** Il CSS del tuo tema potrebbe essere in conflitto. Questo modulo gestisce principalmente il posizionamento. Se lo stile è sbagliato, è probabile che sia un problema CSS del tuo tema che interagisce con gli stili predefiniti dello slider. Potrebbe essere necessario un web developer per ispezionare il CSS.

**D: Come faccio a cambiare le immagini o la velocità dello slider?**
R: Questo modulo controlla solo il *posizionamento*. Per gestire il contenuto effettivo (immagini, link, descrizioni) e il comportamento (velocità, riproduzione automatica, pausa al passaggio del mouse) dello slider, devi andare alla configurazione del modulo **"Slider di immagini"** (il modulo standard di PrestaShop, solitamente trovato cercando "Slider di immagini" in **Moduli > Gestione moduli**).

**D: Posso avere due slider, uno in alto e uno nella posizione predefinita?**
R: Questo modulo sposta specificamente lo slider di immagini *predefinito* di PrestaShop in alto. Se desideri un secondo slider indipendente, avresti bisogno di un modulo diverso progettato per quello scopo.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica per sviluppatori e webmaster che desiderano comprendere, personalizzare o risolvere i problemi del modulo "Homeslider on top".

### 4.1 Panoramica dell'architettura

Il modulo "Homeslider on top" è un modulo PrestaShop leggero progettato principalmente per alterare la posizione di visualizzazione del modulo `ps_imageslider` principale. Lo fa annullando la registrazione di `ps_imageslider` dai suoi hook predefiniti (come `displayHome`) e registrandolo nuovamente a un hook più prominente, tipicamente `displayHeader`. Non introduce nuove tabelle di database, classi complesse o risorse estese per il front-office, rendendolo un "gestore di hook" semplice ma efficace per la funzionalità dello slider esistente.

### 4.2 Controller (`controllers/`)

Questo modulo non introduce alcun controller Front-Office o Back-Office personalizzato. Tutta la configurazione è gestita direttamente all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non introduce classi o modelli personalizzati. Opera interagendo con le funzioni di gestione dei moduli principali di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo non include alcun file JavaScript personalizzato. Il JavaScript per la funzionalità dello slider è fornito dal modulo `ps_imageslider` stesso.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo non include alcun file CSS personalizzato. Lo stile per lo slider è fornito dal modulo `ps_imageslider` e/o dal tema PrestaShop attivo.

### 4.6 Struttura del template Smarty (`views/templates/`)

Questo modulo non include alcun file di template Smarty personalizzato. Si basa sui template forniti dal modulo `ps_imageslider`.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**: Questo modulo non crea tabelle di database personalizzate. La sua configurazione è memorizzata in `ps_configuration` utilizzando chiavi di configurazione standard di PrestaShop.
- **Tabella degli hook registrati**:

| Nome dell'Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `install()` | Durante l'installazione del modulo | Registra il modulo a `displayHeader` e potenzialmente annulla la registrazione di `ps_imageslider` da `displayHome` o altri hook predefiniti. |
| `uninstall()` | Durante la disinstallazione del modulo | Annulla la registrazione del modulo da `displayHeader` e potenzialmente registra nuovamente `ps_imageslider` ai suoi hook predefiniti. |
| `displayHeader` | Renderizza il contenuto all'interno della sezione `<head>` o nella parte superiore del `<body>` | Questo è l'hook principale in cui il modulo tenta di renderizzare il contenuto di `ps_imageslider`. |
| `hookDisplayHeader` | Quando `displayHeader` viene chiamato | Il metodo del modulo che viene eseguito quando `displayHeader` viene chiamato. Tipicamente chiama `Module::hookDisplayHome()` del modulo `ps_imageslider` per renderizzare il suo contenuto. |

La logica principale risiede nel file `homeslider-on-top.php`, in particolare all'interno dei metodi `install()`, `uninstall()` e `hookDisplayHeader()`. Il metodo `hookDisplayHeader()` è cruciale in quanto è responsabile del recupero e del rendering del contenuto del modulo `ps_imageslider` quando questo modulo è attivo.

**Logica chiave all'interno di `homeslider-on-top.php`:**

- **`__construct()`**: Imposta le informazioni di base del modulo.
- **`install()`**:
  - Chiama `parent::install()`.
  - Registra il modulo a `displayHeader`.
  - Fondamentalmente, spesso tenta di annullare la registrazione del modulo `ps_imageslider` da `displayHome` per prevenire la visualizzazione duplicata, e quindi registra `ps_imageslider` a `displayHeader` se non è già lì, o assicura che il suo contenuto sia renderizzato tramite il `hookDisplayHeader` di questo modulo.
- **`uninstall()`**:
  - Chiama `parent::uninstall()`.
  - Annulla la registrazione del modulo da `displayHeader`.
  - Registra nuovamente `ps_imageslider` a `displayHome` per ripristinare il comportamento predefinito.
- **`getContent()`**: Gestisce il modulo del form di configurazione del back-office (che di solito è molto semplice, spesso solo un interruttore di abilitazione/disabilitazione).
- **`hookDisplayHeader()`**:
  - Questo metodo viene eseguito quando l'hook `displayHeader` viene chiamato da PrestaShop.
  - Tipicamente controlla se il modulo `ps_imageslider` è installato e abilitato.
  - In tal caso, chiama direttamente il metodo `hookDisplayHome()` del modulo `ps_imageslider` per recuperare il suo contenuto renderizzato e restituirlo, "spostando" efficacemente l'output dello slider nella posizione `displayHeader`.

Gli sviluppatori che desiderano personalizzare questo modulo si concentrerebbero principalmente sul metodo `hookDisplayHeader()` se volessero alterare il modo in cui il contenuto di `ps_imageslider` viene recuperato o incapsulato, o sui metodi `install()`/`uninstall()` se avessero bisogno di cambiare gli hook specifici coinvolti.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Homeslider on top", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda possiate avere riguardo alla funzionalità e compatibilità del modulo.
