---
title: "Pagina prodotto come homepage del negozio - Manuale commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Pagina prodotto come homepage del negozio' di MyPresta.eu."
sidebar:
  label: "Pagina prodotto come homepage del negozio - Manuale commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Product page as shop homepage su MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-as-shop-homepage.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/product-page-as-shop-homepage/)
>
> ---


# Pagina prodotto come homepage del negozio

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Panoramica completa della configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo "Pagina prodotto come homepage del negozio". Vedrai una singola e semplice opzione di configurazione.

- **Nome impostazione:** Prodotto da visualizzare sulla homepage
  - **Cosa fa questa impostazione:** Questa è l'impostazione più cruciale. Ti permette di selezionare esattamente quale prodotto dal tuo catalogo diventerà la nuova homepage del tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Quando un prodotto è selezionato:* L'URL principale del tuo negozio visualizzerà la pagina prodotto completa del prodotto scelto.
    - *Quando nessun prodotto è selezionato (o il modulo è disabilitato):* Il tuo negozio tornerà al suo comportamento predefinito della homepage (ad esempio, visualizzando prodotti in evidenza, categorie o una pagina CMS personalizzata).
  - **Valore consigliato:** Seleziona il prodotto che vuoi mettere più in evidenza. Usa la barra di ricerca per trovare rapidamente il prodotto desiderato.
  - **Scenario / esempio del commerciante:** Hai appena lanciato un nuovo gadget rivoluzionario. Vuoi che ogni visitatore del tuo negozio veda questo prodotto per primo. Digiteresti il nome del prodotto (ad esempio, "Super Gadget X") nella casella di ricerca, lo selezioneresti dal menu a discesa e salveresti. Ora, chiunque visiti `www.iltuonegozio.com` atterrerà direttamente sulla pagina prodotto "Super Gadget X".

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | Prodotto da visualizzare sulla homepage | (Nessuno selezionato inizialmente) / Seleziona il tuo prodotto chiave | Definisce quale pagina prodotto sostituirà la homepage predefinita del tuo negozio. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: La mia homepage mostra ancora il vecchio contenuto dopo aver configurato il modulo. Cosa devo fare?**
R: Questo è solitamente un problema di cache.
1.  Vai su **Parametri avanzati > Prestazioni** nel tuo Back Office di PrestaShop.
2.  Clicca su "Svuota la cache" nell'angolo in alto a destra.
3.  Inoltre, svuota la cache e i cookie del tuo browser, quindi prova ad accedere di nuovo al tuo negozio.

**D: Posso cambiare facilmente il prodotto in evidenza?**
R: Sì! Basta tornare su **Moduli > Gestione moduli**, trovare "Pagina prodotto come homepage del negozio", cliccare su "Configura" e selezionare un prodotto diverso dal menu a discesa. Salva le modifiche e svuota la cache.

**D: Cosa succede se il prodotto selezionato è esaurito o disabilitato?**
R: Se il prodotto selezionato è esaurito, la sua pagina prodotto verrà comunque visualizzata, ma il pulsante "Aggiungi al carrello" potrebbe essere disabilitato o mostrare un messaggio "Esaurito", a seconda delle impostazioni di inventario di PrestaShop. Se il prodotto è completamente disabilitato, PrestaShop potrebbe mostrare un errore "Pagina non trovata" o tornare alla homepage predefinita. Assicurati sempre che il prodotto selezionato sia attivo e disponibile.

**D: Questo modulo influisce sul mio SEO?**
R: Quando imposti una pagina prodotto come homepage, l'URL principale del tuo negozio (`www.iltuonegozio.com`) servirà ora il contenuto di quella pagina prodotto. I motori di ricerca indicizzeranno questo contenuto per il tuo dominio principale. Se in precedenza avevi una homepage ricca e ottimizzata per le parole chiave, potresti notare un cambiamento nel modo in cui il tuo dominio principale si classifica. Assicurati che la pagina prodotto scelta sia ben ottimizzata per il SEO (titolo, descrizione, immagini, contenuto).

**D: Posso usarlo con un tema personalizzato?**
R: Sì, il modulo funziona sovrascrivendo il modo in cui PrestaShop gestisce il `Dispatcher.php` per l'`IndexController`. Dovrebbe essere compatibile con la maggior parte dei temi personalizzati poiché sfrutta il rendering standard della pagina prodotto di PrestaShop. Se riscontri problemi di stile, è probabile che siano correlati al CSS del tuo tema, non alla funzionalità principale del modulo.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Pagina prodotto come homepage del negozio" opera sovrascrivendo i controller frontali principali di PrestaShop per reindirizzare il comportamento predefinito della homepage (`IndexController`). Invece di caricare il template standard della homepage, forza il `ProductController` a renderizzare la pagina per un ID prodotto specifico, rendendo di fatto una pagina prodotto la pagina di destinazione predefinita per l'URL radice del negozio. Questo viene ottenuto attraverso una serie di override nella directory `override/`.

### 4.2 Controller (`controllers/`)

Questo modulo utilizza principalmente override per modificare il comportamento del controller.

- **Controller Front-Office**:
  - `homepageproduct/override/controllers/front/index.php`
    - Questo file è un segnaposto o un override più vecchio. Nelle versioni moderne di PrestaShop, l'`IndexController` viene tipicamente sovrascritto direttamente. La sua presenza suggerisce un meccanismo di compatibilità o un approccio più vecchio.
  - `homepageproduct/override/controllers/front/IndexController.php`
    - **Nome classe e classe padre:** `IndexController` (sovrascrive `IndexControllerCore`)
    - **Responsabilità:** Questo è l'override principale. Quando si accede all'URL radice del negozio, PrestaShop normalmente invia `IndexController`. Questo override intercetta tale invio. Controlla la configurazione del modulo per un ID `homepageproduct_product`. Se un ID prodotto è impostato, reindirizza o inoltra internamente la richiesta al `ProductController` per quel prodotto specifico, rendendo di fatto la pagina prodotto invece della homepage predefinita. Assicura che il contesto del controller corrente sia correttamente impostato su `ProductController` e che i dati del prodotto siano caricati.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo utilizza override per modificare il comportamento delle classi principali, in particolare quelle relative alla gestione dei controller.

- `homepageproduct/override/classes/controller/FrontController.php`
  - **Nome classe e classe padre:** `FrontController` (sovrascrive `FrontControllerCore`)
  - **Responsabilità:** Questo override contiene probabilmente la logica per garantire che l'override di `IndexController` funzioni correttamente all'interno del processo di invio di `FrontController`. Potrebbe regolare il modo in cui il controller viene inizializzato o come i template vengono assegnati quando la homepage viene servita come pagina prodotto.
- `homepageproduct/override/classes/controller/index.php`
  - Simile a `override/controllers/front/index.php`, questo sembra essere un segnaposto o un meccanismo di override più vecchio.
- `homepageproduct/override/classes/index.php`
  - Un altro segnaposto o override più vecchio.

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo non include alcun file JavaScript personalizzato. Tutta l'interattività front-office per la pagina prodotto proviene dal JS della pagina prodotto principale di PrestaShop.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo non include alcun file CSS personalizzato. Lo stile della pagina prodotto è interamente gestito dal tema PrestaShop attivo.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo non introduce nuovi template front-office per la visualizzazione. Riutilizza i template esistenti delle pagine prodotto di PrestaShop.

- **Template di amministrazione (`views/templates/admin/`)**:
  - `homepageproduct/lib/searchTool/views/scripts.tpl`
    - Questo template è probabilmente utilizzato all'interno del metodo `getContent()` del modulo nel back office. Probabilmente contiene logica JavaScript o Smarty per renderizzare il campo di input di ricerca prodotto, consentendo all'amministratore di trovare e selezionare facilmente un prodotto per nome o ID per la homepage. Potrebbe includere chiamate AJAX a `AdminProducts` o controller simili per suggerimenti di prodotti.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Il modulo non crea tabelle di database personalizzate.
  - Memorizza la sua configurazione nella tabella `ps_configuration`:
    - `homepageproduct_product`: Memorizza l'ID del prodotto selezionato per essere la homepage.
    - `mypresta_updates`, `update_`, `updatev_`: Utilizzati per i controlli di aggiornamento del modulo da parte di MyPresta.eu.
    - `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Una chiave di configurazione standard di PrestaShop, non direttamente gestita da questo modulo ma potenzialmente accessibile.
- **Tabella degli hook registrati**:
  Il modulo non registra esplicitamente nuovi hook di visualizzazione. La sua funzionalità è ottenuta tramite override del controller. Tuttavia, poiché renderizza una pagina prodotto standard, tutti gli hook normalmente presenti su una pagina prodotto (ad esempio, `displayHeader`, `displayProductButtons`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, `displayProductExtraContent`, `actionValidateOrder`) verranno eseguiti come se fosse una normale pagina prodotto.

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Prima del contenuto della pagina | Per includere CSS, JS, meta tag. |
| `displayLeftColumn` | Colonna sinistra della pagina prodotto | Visualizzazione di blocchi come categorie, filtri. |
| `displayRightColumn` | Colonna destra della pagina prodotto | Visualizzazione di blocchi come carrello, contenuto personalizzato. |
| `displayFooter` | In fondo alla pagina | Per includere JS, contenuto del piè di pagina. |
| `displayProductButtons` | Vicino al pulsante "Aggiungi al carrello" | Aggiunta di pulsanti o azioni personalizzate sulla pagina prodotto. |
| `displayProductExtraContent` | Sotto la descrizione del prodotto | Aggiunta di schede o contenuti extra alla pagina prodotto. |
| `actionValidateOrder` | Dopo la convalida di un ordine | Per l'elaborazione post-ordine (ad esempio, tracciamento). |
| *(Qualsiasi altro hook normalmente presente su una pagina prodotto)* | Varia | Esecuzione standard degli hook della pagina prodotto di PrestaShop. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo "Pagina prodotto come homepage del negozio", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a garantire il buon funzionamento e il continuo miglioramento dei nostri moduli.
