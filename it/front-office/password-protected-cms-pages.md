---
title: "Pagine CMS protette da password - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Pagine CMS protette da password di MyPresta.eu."
sidebar:
  label: "Pagine CMS protette da password - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Password protected CMS pages su MyPresta.eu](https://mypresta.eu/modules/front-office-features/password-protected-cms-pages.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/password-protected-cms-pages/)
>
> ---


# Pagine CMS protette da password

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" sul modulo verrai indirizzato alla sua schermata di configurazione principale. Questa schermata serve principalmente come punto di ingresso all'area di gestione dedicata per le tue pagine CMS protette da password.

- **Cosa fa questa schermata:** Questa pagina di solito fornisce una breve panoramica o un link diretto all'interfaccia di gestione principale dove configurerai e gestirai effettivamente le tue pagine CMS protette da password. Potrebbe anche contenere impostazioni generali se il modulo ne avesse, ma per questo modulo, la funzionalità principale è gestita in una sezione separata.
- **Effetto della modifica delle impostazioni:** Qualsiasi impostazione qui influirebbe direttamente sul comportamento o sull'aspetto globale del modulo.
- **Valore consigliato:** Segui le istruzioni sullo schermo, di solito cliccando un pulsante per procedere alla gestione delle pagine CMS.
- **Scenario/esempio del commerciante:** Hai appena installato il modulo. Probabilmente vedrai un pulsante come "Gestisci pagine CMS protette" o "Configura password CMS". Cliccando su questo verrai indirizzato alla schermata dedicata per iniziare a proteggere le tue pagine.

### 2.2 Schermata di amministrazione dedicata: Gestisci pagine CMS protette (Back Office > Moduli > Pagine CMS protette da password > Configura > [Link alla gestione])

Questa è la schermata principale in cui gestirai quali pagine CMS sono protette e quali sono le loro password. Accedi a questa schermata solitamente cliccando su un link o un pulsante dalla pagina di configurazione principale del modulo.

- **Nome schermata e posizione nel menu:** Troverai tipicamente una nuova voce di menu sotto **Moduli > Gestione moduli > Pagine CMS protette da password > Configura**, che ti indirizzerà all'interfaccia di gestione. L'URL potrebbe assomigliare a `admin/index.php?controller=AdminPcmsController`.
- **Azioni e impostazioni disponibili:**
  - **Tabella di elenco:** Questa schermata visualizzerà una tabella che elenca tutte le tue pagine CMS esistenti. Per ogni pagina, vedrai il suo nome, ID e se è attualmente protetta.
  - **Aggiungi/Modifica protezione:** Per ogni pagina CMS nell'elenco, troverai tipicamente un pulsante/icona "Modifica" o "Configura". Cliccando su questo si aprirà un modulo in cui puoi:
    - **Abilita/Disabilita protezione:** Un semplice interruttore (Sì/No) per attivare o disattivare la protezione con password per quella specifica pagina CMS.
      - *Quando abilitata:* La pagina richiederà una password per visualizzare il suo contenuto nel front office.
      - *Quando disabilitata:* La pagina sarà pubblicamente accessibile come una pagina CMS standard.
      - *Valore consigliato:* "Sì" per le pagine che vuoi proteggere, "No" per le pagine pubbliche.
      - *Scenario del commerciante:* Vuoi proteggere la tua pagina "Offerte VIP", quindi abiliti la protezione.
    - **Imposta password:** Un campo di input in cui definisci la password per quella specifica pagina CMS.
      - *Effetto della modifica:* Questa è la password esatta che i clienti dovranno inserire per visualizzare la pagina.
      - *Valore consigliato:* Scegli una password forte e unica per ogni pagina protetta.
      - *Scenario del commerciante:* Imposti "MIOSEGRETO" come password per la tua pagina "Offerte VIP".
  - **Azioni di massa:** A seconda della versione del modulo, potrebbero esserci opzioni per abilitare/disabilitare la protezione per più pagine contemporaneamente, anche se la gestione individuale delle pagine è più comune per le impostazioni della password.
- **Effetto delle modifiche:**
  - Quando abiliti la protezione e imposti una password per una pagina CMS, quella pagina diventa immediatamente protetta da password nel tuo front office. I clienti che visitano il suo URL vedranno la richiesta della password.
  - La disabilitazione della protezione rende la pagina nuovamente visibile pubblicamente.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1. Decidi quali pagine CMS devono essere private o esclusive.
  2. Naviga a questa schermata "Gestisci pagine CMS protette".
  3. Trova la pagina CMS desiderata nell'elenco.
  4. Clicca su "Modifica" o sull'azione equivalente per quella pagina.
  5. Abilita l'interruttore di protezione con password.
  6. Inserisci una password forte e unica.
  7. Salva le modifiche.
  8. Comunica la password al tuo pubblico di destinazione.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Gestisci pagine CMS protette** | Abilita/Disabilita protezione | No / Sì (secondo necessità) | Controlla se una specifica pagina CMS richiede una password per essere visualizzata. |
| | Password per pagina CMS | (Vuoto) / Password forte e unica | La stringa esatta che i clienti devono inserire per accedere al contenuto protetto. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D: Ho impostato una password, ma la pagina è ancora visibile senza di essa. Cosa c'è che non va?**
R:

1. **Verifica se la protezione è abilitata:** Vai alla schermata "Gestisci pagine CMS protette" e assicurati che l'interruttore "Abilita protezione" per quella specifica pagina CMS sia impostato su "Sì".
2. **Svuota la cache del tuo browser:** Il tuo browser potrebbe mostrarti una versione memorizzata nella cache della pagina. Prova a svuotare la cache del tuo browser o ad aprire la pagina in una finestra in incognito/privata.
3. **Svuota la cache di PrestaShop:** Vai su **Parametri avanzati > Prestazioni** nel tuo Back Office e clicca su "Svuota la cache" nell'angolo in alto a destra. Questo assicura che PrestaShop stia servendo la configurazione più recente.

**D: Posso avere password diverse per diverse pagine CMS?**
R: Sì! Questo modulo è progettato proprio per questo. Ogni pagina CMS può avere la propria password unica, permettendoti di creare più livelli di contenuto protetto.

**D: Cosa succede se un cliente inserisce la password sbagliata?**
R: Il modulo visualizzerà un messaggio di errore (es. "Password errata. Riprova.") e il modulo di input della password riapparirà, consentendo al cliente di reinserire la password.

**D: Posso personalizzare l'aspetto del modulo di input della password?**
R: Il modulo utilizza uno stile di base per il modulo della password. Per una personalizzazione avanzata, avresti bisogno di un webmaster o di uno sviluppatore per modificare il file CSS del modulo (`css.css`) o sovrascrivere il suo template (`cms.tpl`).

**D: Ho aggiornato il mio tema PrestaShop e ora il modulo della password ha un aspetto strano. Cosa devo fare?**
R: I temi personalizzati a volte hanno un proprio stile che può entrare in conflitto con la visualizzazione dei moduli.

1. **Svuota la cache di PrestaShop:** Prova sempre prima questo (**Parametri avanzati > Prestazioni > Svuota la cache**).
2. **Contatta lo sviluppatore del tuo tema:** Potrebbero avere istruzioni specifiche per la compatibilità dei moduli.
3. **Consulta un webmaster:** Uno sviluppatore può ispezionare il CSS e l'HTML per identificare e risolvere i conflitti di stile.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Pagine CMS protette da password" (`passcms`) funziona principalmente sovrascrivendo il `CmsController` principale per intercettare le richieste di pagine CMS. Quando viene richiesta una pagina CMS protetta, verifica la presenza di una password valida nella sessione. Se non viene trovata una password valida, renderizza un modulo di input della password invece del contenuto effettivo del CMS. Il modulo utilizza un Controller Admin dedicato (`AdminPcmsController`) per gestire le impostazioni della password per ogni pagina CMS.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**:

  - `passcms/override/controllers/front/CmsController.php`
    - **Nome classe e classe genitore**: `CmsController` (sovrascrive il `CmsController` principale)
    - **Responsabilità**: Questo è il cuore della funzionalità del front-office. Intercetta il metodo `initContent()` del `CmsController` originale. Verifica se la pagina CMS richiesta (identificata da `id_cms`) è configurata come protetta da password. Se lo è, e non c'è una password valida nella sessione, renderizza il template `cms.tpl` con il modulo di input della password. Gestisce anche la richiesta POST per l'invio della password, convalidandola rispetto alla password memorizzata e impostando una variabile di sessione in caso di successo.
  - `passcms/override/controllers/front/index.php`
    - **Nome classe e classe genitore**: Non una classe, tipicamente un file vuoto o una misura di sicurezza di base per prevenire l'elenco diretto delle directory.
    - **Responsabilità**: Pratica standard di PrestaShop per le directory `override`.
- **Controller Admin Back-Office**:

  - `passcms/controllers/admin/AdminPcmsController.php`
    - **Nome tab e entità gestita**: Gestisce le impostazioni di protezione con password per le singole pagine CMS. Questo controller estende `ModuleAdminController` e fornisce l'interfaccia per elencare le pagine CMS e configurare le loro password. Gestisce le operazioni CRUD per l'entità `pcms` (anche se non è elencato un `ObjectModel` esplicito, probabilmente interagisce direttamente con `ps_configuration` o una tabella personalizzata per l'archiviazione delle password). Renderizza la vista a griglia delle pagine CMS e il modulo per la modifica delle impostazioni della password.
  - `passcms/controllers/admin/index.php`
    - **Nome classe e classe genitore**: Non una classe, tipicamente un file vuoto o una misura di sicurezza di base per prevenire l'elenco diretto delle directory.
    - **Responsabilità**: Pratica standard di PrestaShop per le directory dei controller.

### 4.3 Classi e Modelli Core (`classes/`)

Il dossier del modulo non indica classi personalizzate nella directory `classes/`. Ciò suggerisce che il modulo probabilmente memorizza la sua configurazione direttamente nella tabella `ps_configuration`, utilizzando chiavi come `PCMS_PASSWORD_ID_CMS_X` dove `X` è l'`id_cms`, oppure potrebbe utilizzare una tabella personalizzata gestita direttamente da `AdminPcmsController` senza un `ObjectModel` dedicato.

### 4.4 Risorse JavaScript (`views/js/`)

Il dossier del modulo non indica file JavaScript personalizzati. L'invio della password è probabilmente gestito tramite un modulo HTML POST standard o un semplice JS inline se è presente un comportamento dinamico.

### 4.5 Fogli di stile CSS (`views/css/`)

- `passcms/css.css`
  - **Ambito**: Stile del front-office per il cliente.
  - **Componenti UI principali e contenitori che stilizza**: Questo file contiene lo stile di base per il modulo di input della password visualizzato sulle pagine CMS protette. Probabilmente si rivolge a elementi come il contenitore del modulo, il campo di input e il pulsante di invio.
  - **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere**: Gli sviluppatori possono ispezionare l'HTML renderizzato del modulo della password per identificare classi specifiche (es. `.passcms-form`, `.passcms-input`, `.passcms-button`, `.passcms-error`) e sovrascriverle nel `custom.css` o `theme.css` del loro tema per abbinarle al branding del negozio.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template Admin (`views/templates/admin/`)**:

  - `passcms/admin.tpl`
    - **Scopo**: Questo template è probabilmente utilizzato per la pagina di configurazione principale del modulo, fornendo il punto di ingresso o informazioni generali, potenzialmente collegandosi all'interfaccia di gestione di `AdminPcmsController`.
  - `passcms/views/templates/admin/script.tpl`
    - **Scopo**: Questo template potrebbe contenere JavaScript inline o variabili Smarty che vengono renderizzate nel Back Office per `AdminPcmsController` per gestire il comportamento dinamico o il passaggio di dati.
- **Template Front-office (`views/templates/front/`)**:

  - `passcms/views/templates/front/cms.tpl`
    - **Scopo**: Questo è il template cruciale renderizzato dal `CmsController` sovrascritto quando una pagina CMS protetta viene acceduta senza una password valida. Contiene la struttura HTML per il modulo di input della password, inclusi il campo di input, il pulsante di invio e eventuali messaggi di errore.

### 4.7 Schema del database e Mappa degli hook

- **Tabelle del database**:

  - Il modulo non crea esplicitamente una tabella SQL personalizzata in base al dossier. È altamente probabile che le impostazioni della password per ogni pagina CMS siano memorizzate nella tabella `ps_configuration` utilizzando chiavi di configurazione uniche, ad esempio `PCMS_PASSWORD_ID_CMS_X` dove `X` è l'`id_cms`.
  - `ps_configuration`: Memorizza i valori di configurazione del modulo, inclusi potenzialmente le password per ogni pagina CMS.
- **Tabella degli hook registrati**:
  Il modulo opera principalmente tramite override del controller piuttosto che tramite hook tradizionali per la sua funzionalità principale. Tuttavia, potrebbe registrare alcuni hook standard per l'integrazione o la visualizzazione generale del modulo.

  | Nome Hook | Tempo di esecuzione | Scopo tecnico |
  | --- | --- | --- |
  | `displayBackOfficeHeader` | Renderizza nella sezione `<head>` delle pagine del Back Office. | Utilizzato per includere CSS (`css.css`) o JS per l'interfaccia di `AdminPcmsController`. |
  | `displayHeader` | Renderizza nella sezione `<head>` delle pagine del front-office. | Potrebbe essere utilizzato per includere CSS (`css.css`) o JS del front-office se necessario a livello globale, anche se è più probabile che venga caricato condizionalmente dall'override di `CmsController`. |
  | `actionFrontControllerSetMedia` | Eseguito quando un controller front-end imposta le sue risorse multimediali. | Alternativa a `displayHeader` per caricare condizionalmente le risorse in base al controller corrente. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Pagine CMS protette da password", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu). Il nostro team di supporto è disponibile per assistere con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e compatibilità del modulo.
"""
