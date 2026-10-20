---
title: "Rimuovi codice ISO lingua dagli URL - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Rimuovi codice ISO lingua dagli URL' di MyPresta.eu."
sidebar:
  label: "Rimuovi codice ISO lingua dagli URL - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Remove language ISO code from urls su MyPresta.eu](https://mypresta.eu/modules/seo/remove-language-iso-code-from-urls.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/seo/remove-language-iso-code-from-urls/)
>
> ---


# Rimuovi codice ISO lingua dagli URL

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server oltre a quelle richieste da PrestaShop stesso.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al nome del modulo "Rimuovi codice ISO lingua dagli URL" per accedere alle sue impostazioni.

La pagina di configurazione di questo modulo è intenzionalmente semplice, poiché la sua funzione principale è diretta.

**Nome schermata:** Configurazione Rimuovi codice ISO lingua dagli URL
**Posizione menu:** Back Office > Moduli > Gestione moduli > Rimuovi codice ISO lingua dagli URL > Configura

Su questa schermata, troverai tipicamente una singola, cruciale impostazione:

- **Nome impostazione:** Abilita / Disabilita modulo
  - **Cosa fa questa impostazione:** Questo è l'interruttore principale per la funzionalità del modulo. Controlla se il modulo rimuove attivamente il codice ISO della lingua dagli URL della tua lingua predefinita o meno.
  - **Effetto della modifica di questa impostazione:**
    - **Quando abilitato (SÌ):** Il modulo diventerà attivo. Per la lingua predefinita del tuo negozio, il codice ISO della lingua (es. `/it/` se l'italiano è predefinito) verrà rimosso da tutti gli URL generati. Gli URL per le altre lingue rimarranno invariati.
    - **Quando disabilitato (NO):** Il modulo sarà inattivo. Tutti gli URL, inclusi quelli per la tua lingua predefinita, continueranno a visualizzare il codice ISO della lingua (es. `/it/`, `/fr/`).
  - **Valore consigliato:** **SÌ**. Lo scopo principale dell'installazione di questo modulo è utilizzare la sua funzionalità, quindi abilitarlo è la raccomandazione standard.
  - **Scenario / esempio del commerciante:**
    - Hai appena installato il modulo e vuoi che i tuoi URL in italiano (predefinito) appaiano come `www.iltuonegozio.com/il-mio-prodotto`. Imposteresti questo su **SÌ**.
    - Se in seguito decidi di preferire che il codice ISO della lingua sia presente in tutti gli URL per qualche motivo (es. un cambiamento specifico nella strategia SEO), potresti impostare questo su **NO** per ripristinare il comportamento senza disinstallare il modulo.

**Nota importante dopo la configurazione:**
Dopo aver abilitato o disabilitato il modulo, è altamente consigliato:

1. **Svuotare la cache di PrestaShop:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" in alto a destra.
2. **Rigenerare il tuo file `.htaccess`:** Vai su **Parametri negozio > Traffico & SEO**, scorri fino alla sezione "Imposta URL" e clicca su "Salva" (anche se non modifichi nulla). Questo assicura che le regole di riscrittura degli URL siano correttamente aggiornate.
3. **Testare i tuoi URL:** Naviga nel tuo negozio nella tua lingua predefinita e verifica che il codice ISO della lingua sia effettivamente rimosso dagli URL. Inoltre, testa altre lingue per assicurarti che i loro URL contengano ancora il codice ISO.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Abilita / Disabilita modulo | SÌ | Controlla se il modulo rimuove il codice ISO della lingua dagli URL della lingua predefinita. **SÌ** per URL più puliti, **NO** per mantenere i codici ISO per tutte le lingue. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho abilitato il modulo, ma il codice ISO della lingua è ancora visibile negli URL della mia lingua predefinita. Cosa devo fare?**
R: Questo è solitamente un problema di cache o di `.htaccess` non rigenerato.
1. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache".
2. Vai su **Parametri negozio > Traffico & SEO**, scorri fino a "Imposta URL" e clicca su "Salva".
3. Controlla anche la cache del tuo browser, o prova a navigare in una finestra in incognito/privata.

**D: Questo modulo influenzerà gli URL delle mie lingue non predefinite?**
R: No, il modulo è specificamente progettato per rimuovere il codice ISO della lingua solo per la tua lingua *predefinita*. Tutte le altre versioni linguistiche continueranno a visualizzare i rispettivi codici ISO (es. `/fr/`, `/de/`).

**D: Questo modulo danneggerà la mia SEO esistente o creerà errori 404 per i vecchi URL?**
R: Il modulo funziona sovrascrivendo la generazione e la gestione degli URL di base di PrestaShop. Dovrebbe gestire i reindirizzamenti internamente. Tuttavia, per la massima sicurezza, specialmente su negozi consolidati, è sempre una buona idea:
1. **Eseguire il backup del database e dei file** prima dell'installazione.
2. **Testare accuratamente** prima su un ambiente di staging.
3. Dopo l'abilitazione, monitorare i log di accesso del server e Google Search Console per eventuali errori 404. Se ne trovi, potresti dover aggiungere manualmente reindirizzamenti 301 per specifici vecchi URL alle loro nuove versioni più pulite nel tuo file `.htaccess`, anche se questo è raramente necessario con questo modulo.

**D: Il mio tema personalizzato presenta alcuni problemi dopo l'installazione del modulo. Cosa potrebbe esserci di sbagliato?**
R: Questo modulo influisce principalmente sulla generazione e sul routing degli URL, non sulla visualizzazione visiva. È improbabile che causi direttamente problemi al tema. Tuttavia, se il tuo tema ha strutture URL molto specifiche e hardcoded o si basa su JavaScript che analizza gli URL in modo insolito, c'è una piccolissima possibilità di conflitto.
\* Per prima cosa, svuota la cache di Smarty (**Parametri avanzati > Prestazioni**).
\* Se il problema persiste, disabilita temporaneamente il modulo per vedere se il problema scompare. Se lo fa, contatta il supporto MyPresta.eu con i dettagli del problema.

**D: Questo modulo supporta tutte le lingue installate in PrestaShop?**
R: Sì, supporta tutte le lingue. Identifica la tua lingua *predefinita* e rimuove il suo codice ISO, lasciando intatti i codici ISO per tutte le altre lingue installate.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce un'analisi approfondita dell'implementazione tecnica del modulo "Rimuovi codice ISO lingua dagli URL", destinata a sviluppatori, webmaster e agenzie tecniche.

### 4.1 Panoramica dell'architettura

Il modulo "Rimuovi codice ISO lingua dagli URL" raggiunge la sua funzionalità sovrascrivendo le classi core di PrestaShop responsabili della generazione degli URL (`Link`) e della gestione degli URL (`Dispatcher`). Ciò gli consente di intercettare e modificare il modo in cui gli URL vengono costruiti e interpretati da PrestaShop, mirando specificamente alla rimozione del codice ISO della lingua per la lingua predefinita. Sfrutta il sistema di override di PrestaShop per iniettare la sua logica personalizzata senza modificare direttamente i file core.

### 4.2 Controller (`controllers/`)

Questo modulo non introduce alcun controller front-office o back-office personalizzato. La sua logica è implementata principalmente tramite override di classe.

### 4.3 Classi e modelli core (`classes/`)

La funzionalità principale del modulo risiede nei suoi override di classe. Questi file sono posizionati in `removeiso/override/classes/` per garantire che il sistema di override di PrestaShop li rilevi.

- **`removeiso/override/classes/Dispatcher.php`**
  - **Nome classe:** `Dispatcher` (sovrascrive la classe `Dispatcher` core di PrestaShop)
  - **Classe genitore:** `DispatcherCore`
  - **Responsabilità:** Questo override è cruciale per il modo in cui PrestaShop *interpreta* gli URL in entrata. Modifica il metodo `dispatch()` (o un metodo correlato) per instradare correttamente le richieste che non contengono più il codice ISO della lingua predefinita. Quando arriva un URL come `www.iltuonegozio.com/il-mio-prodotto`, questo `Dispatcher` sovrascritto assicura che PrestaShop lo comprenda come appartenente alla lingua predefinita, anche senza il segmento `/it/`. Probabilmente gestisce anche la logica per garantire che se l'ISO della lingua predefinita *è* presente (es. `www.iltuonegozio.com/it/il-mio-prodotto`), venga reindirizzato all'URL più pulito.
- **`removeiso/override/classes/Link.php`**
  - **Nome classe:** `Link` (sovrascrive la classe `Link` core di PrestaShop)
  - **Classe genitore:** `LinkCore`
  - **Responsabilità:** Questo override è responsabile del modo in cui PrestaShop *genera* gli URL in uscita. Modifica metodi come `getLanguageLink()`, `getProductLink()`, `getCategoryLink()`, ecc., per impedire l'inclusione del codice ISO della lingua quando la lingua di destinazione è la lingua predefinita del negozio. Ciò garantisce che tutti i collegamenti generati da PrestaShop (es. nei template, nei moduli) per la lingua predefinita siano puliti.
- **`removeiso/override/classes/Tools.php`**
  - **Nome classe:** `Tools` (sovrascrive la classe `Tools` core di PrestaShop)
  - **Classe genitore:** `ToolsCore`
  - **Responsabilità:** La classe `Tools` contiene molte funzioni di utilità. Questo override potrebbe essere utilizzato per modificare il modo in cui vengono gestiti alcuni parametri globali o stringhe relative agli URL, possibilmente in combinazione con gli override di `Dispatcher` e `Link` per garantire la coerenza tra le varie attività di manipolazione degli URL. Potrebbe, ad esempio, influenzare il modo in cui `$_SERVER['REQUEST_URI']` viene interpretato o come `Tools::redirect()` si comporta in scenari specifici relativi ai codici lingua.
- **`removeiso/override/classes/index.php`**
  - **Nome classe:** N/A (file vuoto)
  - **Classe genitore:** N/A
  - **Responsabilità:** Questa è una pratica di sicurezza standard nei moduli PrestaShop per prevenire l'elenco delle directory se il file `index.php` viene acceduto direttamente. Non contiene codice eseguibile.

### 4.4 Risorse JavaScript (`views/js/`)

- **`removeiso/views/js/removeiso.js`**
  - **Ambito:** Back-office (probabilmente caricato sulla pagina di configurazione del modulo).
  - **Responsabilità:** Data la funzione del modulo, questo file JS è probabilmente minimale. Potrebbe contenere:
    - Semplici listener di eventi per il modulo di configurazione (es. un clic sul pulsante "Salva").
    - Chiamate AJAX per salvare le impostazioni di configurazione se il modulo utilizza l'invio asincrono.
    - Miglioramenti UI di base o convalida per il singolo interruttore "Abilita/Disabilita".
    - Non sembra avere alcuna responsabilità front-office o logica client-side complessa relativa alla manipolazione degli URL, poiché questa è gestita lato server dagli override PHP.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo non include alcun file CSS personalizzato. Ciò indica che la sua interfaccia di configurazione si basa sullo stile predefinito del Back Office di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **`removeiso/views/templates/admin/removeiso.tpl`**
  - **Ambito:** Template di amministrazione per la pagina di configurazione del modulo.
  - **Responsabilità:** Questo template renderizza il modulo di configurazione del modulo nel Back Office di PrestaShop. Conterrà la struttura HTML per l'interruttore "Abilita / Disabilita modulo" e gli elementi standard del modulo di PrestaShop (es. pulsante `submit`, messaggi `alert`). Viene tipicamente renderizzato dal metodo `getContent()` della classe principale del modulo.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:
  - Questo modulo non crea tabelle del database personalizzate.
  - Le sue impostazioni di configurazione (es. lo stato "Abilita/Disabilita") sono memorizzate nella tabella `ps_configuration`, utilizzando chiavi tipicamente prefissate con `REMOVEISO_` o simili (es. `PS_REMOVEISO_ENABLED`).
- **Tabella degli hook registrati**:
  Questo modulo non si registra esplicitamente a molti hook standard di PrestaShop per la sua funzionalità principale, poiché il suo meccanismo primario è l'override di classe. Il metodo `install()` del modulo potrebbe registrarsi a `actionModuleInstall` o `actionModuleUninstall` per la pulizia, ma il suo comportamento in fase di esecuzione è guidato dalle classi sovrascritte.

| Nome Hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Renderizza il contenuto nella sezione `<head>` delle pagine front-office. | Sebbene non direttamente utilizzato per la sua logica URL principale, un modulo potrebbe agganciarsi qui per caricare JS/CSS o eseguire controlli iniziali. (Non direttamente utilizzato da questo modulo per la sua funzione principale). |
| `displayRightColumn` / `displayLeftColumn` | Renderizza il contenuto nelle colonne laterali. | (Non direttamente utilizzato da questo modulo). |
| `displayProduct` | Renderizza il contenuto nella pagina del prodotto. | (Non direttamente utilizzato da questo modulo). |
| `displayFooter` | Renderizza il contenuto nella sezione del piè di pagina. | (Non direttamente utilizzato da questo modulo). |
| `actionDispatcherBefore` | Prima che il dispatcher elabori la richiesta. | La classe `Dispatcher` sovrascritta gestisce implicitamente questo, ma un modulo potrebbe anche usare questo hook per la logica di pre-dispatch. |
| `actionDispatcherAfter` | Dopo che il dispatcher ha elaborato la richiesta. | (Non direttamente utilizzato da questo modulo). |
| `actionModuleInstall` | Eseguito quando il modulo è installato. | Per eseguire attività di configurazione come la registrazione di override, l'aggiunta di configurazione a `ps_configuration`. |
| `actionModuleUninstall` | Eseguito quando il modulo è disinstallato. | Per eseguire attività di pulizia come la rimozione di override, l'eliminazione della configurazione da `ps_configuration`. |

Il cuore del funzionamento di questo modulo sono i suoi override di classe, che vengono caricati automaticamente dal sistema di autoloader di PrestaShop quando il modulo è abilitato, piuttosto che fare affidamento su registrazioni esplicite di hook per la sua manipolazione principale degli URL.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Rimuovi codice ISO lingua dagli URL", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema tecnico o domanda tu possa avere riguardo alla funzionalità del modulo.
