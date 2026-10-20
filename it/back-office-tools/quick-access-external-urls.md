---
title: "Accesso Rapido - URL esterni - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Accesso Rapido - URL esterni di MyPresta.eu."
sidebar:
  label: "Accesso Rapido - URL esterni - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Quick Access - external urls su MyPresta.eu](https://mypresta.eu/modules/administration-tools/quick-access-external-urls.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/quick-access-external-urls/)
>
> ---


# Accesso Rapido - URL esterni

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Panoramica completa della configurazione (ogni impostazione raggruppata per schermata)

Questo modulo si integra direttamente con il sistema di gestione dell'Accesso Rapido esistente di PrestaShop. Non esiste una schermata di configurazione separata per il modulo stesso. Invece, modifica il comportamento della funzione "Accesso Rapido" predefinita nel tuo Back Office.

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Quando clicchi su "Configura" per il modulo "Accesso Rapido - URL esterni", vedrai tipicamente una semplice conferma che il modulo è installato e attivo. Non ci sono impostazioni specifiche da regolare in questa pagina, poiché il modulo funziona sovrascrivendo il comportamento principale di PrestaShop.

### 2.2 Schermate di amministrazione dedicate e viste del controller

La funzionalità del modulo è gestita tramite il menu standard di Accesso Rapido di PrestaShop.

**Nome schermata e posizione menu:**

- **Back Office > Amministrazione > Accesso Rapido** (o **Configura > Parametri Avanzati > Accesso Rapido** nelle versioni precedenti di PrestaShop 1.7.x).
- Puoi anche accedervi direttamente dal menu di Accesso Rapido stesso (l'icona a forma di orologio in alto nel tuo Back Office), cliccando su "Gestisci Accesso Rapido".

**Azioni e impostazioni disponibili:**
In questa schermata, vedrai un elenco dei tuoi link di Accesso Rapido esistenti.

- **Aggiungere un nuovo link di Accesso Rapido:**

  1. Clicca sul pulsante **"Aggiungi nuovo accesso rapido"** (o simile, di solito un'icona più).
  2. Vedrai un modulo con campi come:
     - **Nome:** Il testo che apparirà nel tuo menu di Accesso Rapido (ad esempio, "Portale Spedizioni DHL", "Dashboard Stripe", "Google Analytics").
     - **URL:** Questo è il campo cruciale. **Con questo modulo installato, ora puoi inserire QUALSIASI URL valido qui, inclusi i siti web esterni.** Ad esempio:
       - `https://www.dhl.com/global-en/home/tracking.html`
       - `https://dashboard.stripe.com/`
       - `https://analytics.google.com/`
       - `https://mypresta.eu/`
     - **Apri in una nuova finestra:** (Consigliato: SÌ) Questa opzione determina se il link si apre in una nuova scheda/finestra del browser.
       - *Quando abilitato:* Il link esterno si aprirà in una nuova scheda, mantenendo il Back Office di PrestaShop aperto nella scheda corrente. Questo è generalmente consigliato per i link esterni per evitare di navigare lontano dal pannello di amministrazione.
       - *Quando disabilitato:* Il link si aprirà nella stessa scheda, sostituendo la vista del Back Office di PrestaShop.
  3. Clicca su **"Salva"**.
- **Modificare un link di Accesso Rapido esistente:**

  1. Trova il link nell'elenco e clicca sull'icona "Modifica" (matita).
  2. Modifica il Nome o l'URL come necessario.
  3. Clicca su "Salva".
- **Eliminare un link di Accesso Rapido:**

  1. Trova il link nell'elenco e clicca sull'icona "Elimina" (cestino).
  2. Conferma l'eliminazione.

**Effetto delle modifiche:**

- Qualsiasi link di Accesso Rapido che aggiungi, modifichi o elimini in questa schermata si rifletterà immediatamente nel menu di Accesso Rapido (l'icona dell'orologio) nella parte superiore del Back Office di PrestaShop.
- Quando clicchi su un link di Accesso Rapido che punta a un URL esterno, il tuo browser navigherà a quel sito esterno (nella stessa scheda o in una nuova, a seconda dell'impostazione "Apri in una nuova finestra").

**Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

1. **Identifica gli strumenti esterni utilizzati frequentemente:** Pensa ai siti web che visiti quotidianamente o settimanalmente per gestire il tuo negozio (ad esempio, spedizioni, pagamenti, marketing, supporto, portali dei fornitori).
2. **Aggiungili all'Accesso Rapido:** Vai su **Amministrazione > Accesso Rapido** e aggiungi ogni URL esterno con un nome chiaro e descrittivo.
3. **Abilita "Apri in una nuova finestra":** Per tutti i link esterni, imposta "Apri in una nuova finestra" su SÌ. Ciò garantisce che il Back Office di PrestaShop rimanga aperto e accessibile.
4. **Organizza per il tuo team:** Se hai più utenti amministratori, considera quali link rapidi sarebbero più utili per ogni ruolo.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Back Office > Amministrazione > Accesso Rapido** | **Nome** | Definito dall'utente | Testo visualizzato nel menu di Accesso Rapido. |
|  | **URL** | Definito dall'utente (URL esterno) | L'indirizzo web a cui punta il link. **Questo modulo abilita gli URL esterni qui.** |
|  | **Apri in una nuova finestra** | SÌ (per link esterni) | Determina se il link si apre in una nuova scheda/finestra del browser. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho installato il modulo, ma non riesco ancora ad aggiungere URL esterni all'Accesso Rapido. Cosa c'è che non va?**
R1:

- **Svuota la cache:** Dopo l'installazione, svuota sempre la cache di PrestaShop. Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota la cache" in alto a destra.
- **Controlla lo stato del modulo:** Assicurati che il modulo sia abilitato. Vai su **Moduli > Gestione moduli**, cerca "Accesso Rapido - URL esterni" e verifica che sia attivo.
- **Verifica l'installazione:** A volte, un'installazione può fallire silenziosamente. Prova a disinstallare e reinstallare il modulo.
- **Cache del browser:** Svuota la cache e i cookie del tuo browser, oppure prova ad accedere al Back Office in una finestra in incognito/privata.

**D2: I miei link di Accesso Rapido si aprono nella stessa scheda, anche per i siti esterni. Come posso risolvere questo problema?**
R2:

- Quando aggiungi o modifichi un link di Accesso Rapido, assicurati che l'opzione **"Apri in una nuova finestra"** sia impostata su **SÌ**. Questa impostazione controlla se il link si apre in una nuova scheda o in quella corrente.

**D3: Questo modulo influirà sulle prestazioni o sulla SEO del mio negozio?**
R3:

- No. Questo modulo opera interamente all'interno del Back Office di PrestaShop. Non aggiunge alcun codice, stile o funzionalità al front office del tuo negozio (ciò che vedono i clienti). Pertanto, non ha alcun impatto sulla velocità di caricamento del tuo negozio, sulla SEO o sull'esperienza del cliente.

**D4: Ho aggiunto molti link di Accesso Rapido. Posso organizzarli?**
R4:

- La funzione di Accesso Rapido predefinita di PrestaShop non offre un'organizzazione avanzata come cartelle o categorie. Tuttavia, puoi controllare l'ordine dei link trascinandoli e rilasciandoli nella pagina **Amministrazione > Accesso Rapido**. Puoi anche usare nomi descrittivi per renderli facili da identificare.

**D5: Cosa succede se disinstallo questo modulo? I miei link di Accesso Rapido esterni scompariranno?**
R5:

- Se disinstalli questo modulo, la possibilità di aggiungere *nuovi* URL esterni verrà rimossa. Gli URL esterni esistenti che hai aggiunto mentre il modulo era attivo *potrebbero* continuare a funzionare, ma la convalida principale di PrestaShop potrebbe impedirne la modifica o causare problemi. È meglio mantenere il modulo installato se fai affidamento sui link di Accesso Rapido esterni.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Accesso Rapido - URL esterni" (`qae`) raggiunge la sua funzionalità sovrascrivendo le classi e i controller principali di PrestaShop. In particolare, si rivolge all'`ObjectModel` `QuickAccess` e all'`AdminQuickAccessesController` per rimuovere la convalida che limita gli URL di Accesso Rapido ai percorsi interni del Back Office. Questo è un modello di override comune di PrestaShop.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**: Questo modulo non include alcun controller front-office poiché la sua funzionalità è esclusivamente per il Back Office.
- **Controller Admin Back-Office**:

  - **`qae/override/controllers/admin/AdminQuickAccessesController.php`**
    - **Nome classe**: `AdminQuickAccessesController` (sovrascrive il core `AdminQuickAccessesController`)
    - **Classe genitore**: `AdminController`
    - **Responsabilità**: Questa sovrascrittura è cruciale. L'`AdminQuickAccessesController` originale contiene la logica per convalidare il campo `url` di una voce di Accesso Rapido, assicurandosi che sia un percorso interno del Back Office di PrestaShop. Questa sovrascrittura modifica o rimuove tale convalida, consentendo di salvare URL esterni. Gli sviluppatori dovrebbero ispezionare i metodi `postProcess()` o `renderForm()` per le modifiche specifiche relative alla convalida dell'URL.

### 4.3 Classi e modelli principali (`classes/`)

- **`qae/override/classes/index.php`**

  - Questo è tipicamente un file vuoto o un file contenente solo `<?php exit; ?>` per impedire l'elenco diretto delle directory. È una misura di sicurezza e non fa parte della logica principale del modulo.
- **`qae/override/classes/Link.php`**

  - **Nome classe**: `Link` (sovrascrive la classe `Link` principale)
  - **Classe genitore**: `LinkCore`
  - **Responsabilità**: La classe `Link` è responsabile della generazione di URL in PrestaShop. Sebbene la modifica principale per gli URL esterni sia in `QuickAccess` e `AdminQuickAccessesController`, potrebbe essere presente un override di `Link` per garantire che qualsiasi metodo di generazione o convalida di URL interni su cui `QuickAccess` si basa sia compatibile con la nuova autorizzazione di URL esterni, o per prevenire effetti collaterali indesiderati. Gli sviluppatori dovrebbero cercare modifiche nei metodi relativi alla convalida o alla sanificazione degli URL.
- **`qae/override/classes/QuickAccess.php`**

  - **Nome classe**: `QuickAccess` (sovrascrive l'`ObjectModel` `QuickAccess` principale)
  - **Classe genitore**: `ObjectModel`
  - **Tabella database**: `ps_quick_access`
  - **Campi `$definition`**: Questa classe definisce la struttura di una voce di Accesso Rapido, inclusi `id_quick_access`, `name`, `url` e `new_window`.
  - **Metodi pubblici chiave e logica di business**: Questa sovrascrittura è fondamentale. L'`ObjectModel` `QuickAccess` originale probabilmente include regole di convalida per il campo `url` all'interno dei suoi metodi `validateFields()` o `add()`/`update()`. Questa sovrascrittura rimuove o allenta tali regole di convalida, consentendo al campo `url` di memorizzare qualsiasi stringa, inclusi gli URL esterni, senza attivare errori di convalida.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo non include alcun file JavaScript personalizzato. Le modifiche sono puramente lato server (override PHP).

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo non include alcun file CSS personalizzato. La presentazione visiva del menu di Accesso Rapido è gestita dal tema predefinito del Back Office di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

Questo modulo non include alcun file di template Smarty personalizzato. Sfrutta i template esistenti del Back Office di PrestaShop per il rendering della pagina di gestione dell'Accesso Rapido e del menu di Accesso Rapido stesso.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Questo modulo non crea nuove tabelle del database. Modifica il comportamento di come i dati vengono archiviati e convalidati per la tabella `ps_quick_access` esistente.
  - I record di configurazione non sono archiviati in `ps_configuration` da questo modulo, poiché si basa principalmente su override di classi/controller.
- **Tabella degli hook registrati**:
  Questo modulo non registra alcun hook specifico nel senso tradizionale (ad esempio, `displayHeader`, `actionValidateOrder`). La sua funzionalità è implementata tramite il sistema di override di PrestaShop, che modifica direttamente le classi e i controller principali piuttosto che iniettare codice tramite hook.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Accesso Rapido - URL esterni", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema tecnico o domanda tu possa avere.
"""
