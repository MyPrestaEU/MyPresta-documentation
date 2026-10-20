---
title: "Direttiva Omnibus - Addon Gratuito - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Direttiva Omnibus - Addon Gratuito di MyPresta.eu."
sidebar:
  label: "Direttiva Omnibus - Addon Gratuito - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Omnibus Directive - Free Addon su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/omnibus-directive-free-addon.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/omnibus-directive-free-addon/)
>
> ---


# Direttiva Omnibus - Addon Gratuito

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5 (Il modulo è progettato per essere compatibile con un'ampia gamma di versioni PHP, fino alle ultime versioni stabili supportate da PrestaShop 9.x)
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste da PrestaShop stesso e sono sufficienti per questo modulo. Non sono necessarie configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Per accedere alla configurazione del modulo, naviga su **Moduli > Gestione moduli**, cerca "Direttiva Omnibus - Addon Gratuito" e clicca sul pulsante "Configura".

#### Impostazioni Generali

- **Abilita conformità Direttiva Omnibus:**

  - **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare la funzionalità principale del modulo.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (SÌ):* Il modulo inizierà a tracciare i prezzi dei prodotti e visualizzerà il prezzo più basso degli ultimi 30 giorni sulle pagine prodotto quando uno sconto è attivo.
    - *Quando disabilitato (NO):* Il modulo smetterà di tracciare i prezzi e non visualizzerà alcuna informazione relativa alla Direttiva Omnibus sul tuo negozio.
  - **Valore consigliato:** SÌ (a meno che tu non venda a clienti dell'UE o lo stia disabilitando temporaneamente per manutenzione).
  - **Scenario / esempio per il commerciante:** Hai appena installato il modulo e vuoi assicurarti che il tuo negozio sia conforme. Imposteresti questo su SÌ. Se stai testando un nuovo tema e vuoi nascondere temporaneamente la visualizzazione, potresti impostarlo su NO.
- **Testo da visualizzare per il prezzo più basso:**

  - **Cosa fa questa impostazione:** Ti permette di personalizzare il testo che appare prima del prezzo più basso degli ultimi 30 giorni.
  - **Effetto della modifica di questa impostazione:**
    - *Quando modificato:* Il testo visualizzato ai clienti rifletterà il tuo messaggio personalizzato.
    - *Quando lasciato come predefinito:* Verrà utilizzato il testo predefinito (es. "Prezzo più basso negli ultimi 30 giorni:").
  - **Valore consigliato:** "Prezzo più basso negli ultimi 30 giorni:" o simile, garantendo chiarezza per i tuoi clienti.
  - **Scenario / esempio per il commerciante:** Potresti voler usare una frase leggermente diversa come "Il nostro prezzo più basso di recente è stato:" per adattarsi al tono del tuo marchio.
- **Visualizza sulla pagina prodotto (Selezione Hook):**

  - **Cosa fa questa impostazione:** Questa impostazione cruciale determina *dove* sulla tua pagina prodotto verranno visualizzate le informazioni sul prezzo più basso degli ultimi 30 giorni. Il modulo fornisce opzioni predefinite per strutture di temi comuni (Classic, Hummingbird) e un'opzione di hook personalizzato.
  - **Effetto della modifica di questa impostazione:**
    - *Quando è selezionato "Profilo Tema Classic":* Il modulo tenterà di iniettare la cronologia dei prezzi in una posizione adatta all'interno della struttura standard del tema Classic (es. `displayProductPriceBlock` o `displayProductButtons`).
    - *Quando è selezionato "Profilo Tema Hummingbird":* Il modulo tenterà di iniettare la cronologia dei prezzi in una posizione adatta all'interno della struttura standard del tema Hummingbird.
    - *Quando è selezionato "Hook Personalizzato":* Dovrai specificare manualmente un hook di PrestaShop dove il modulo dovrebbe visualizzare il suo contenuto. Ciò richiede alcune conoscenze tecniche o modifiche al tema.
  - **Valore consigliato:** Inizia con "Profilo Tema Classic" o "Profilo Tema Hummingbird" a seconda del tuo tema attivo. Se la visualizzazione non è soddisfacente, consulta un webmaster per l'integrazione di un "Hook Personalizzato".
  - **Scenario / esempio per il commerciante:** Se il tuo negozio utilizza il tema PrestaShop Classic predefinito, scegli "Profilo Tema Classic". Se hai aggiornato a PrestaShop 8.x e utilizzi il tema Hummingbird, seleziona "Profilo Tema Hummingbird". Se hai un tema altamente personalizzato, potresti dover utilizzare "Hook Personalizzato" e chiedere al tuo sviluppatore di aggiungere `{hook h='displayMyCustomOmnibusHook'}` al tuo template della pagina prodotto.
- **Nome Hook Personalizzato (se "Hook Personalizzato" è selezionato sopra):**

  - **Cosa fa questa impostazione:** Se hai scelto "Hook Personalizzato" nell'impostazione precedente, questo campo ti permette di specificare il nome esatto dell'hook dove il modulo dovrebbe renderizzare il suo contenuto.
  - **Effetto della modifica di questa impostazione:** Il modulo visualizzerà il suo contenuto solo se un hook con questo nome esatto è presente nel template della pagina prodotto del tuo tema.
  - **Valore consigliato:** Lascia vuoto a meno che tu non abbia selezionato "Hook Personalizzato" sopra e conosca il nome esatto dell'hook. Esempio: `displayProductExtraContent`.
  - **Scenario / esempio per il commerciante:** Il tuo webmaster ha modificato il template della tua pagina prodotto (`product.tpl`) per includere `{hook h='displayMyCustomOmnibusHook'}`. Dovresti quindi inserire `displayMyCustomOmnibusHook` in questo campo.

#### Gestione Dati

- **Cancella Dati Omnibus:**
  - **Cosa fa questa impostazione:** Questo pulsante ti permette di eliminare tutti i dati di cronologia dei prezzi precedentemente registrati e memorizzati dal modulo.
  - **Effetto della modifica di questa impostazione:** Cliccando questo pulsante verranno rimossi permanentemente tutti i record storici dei prezzi. Il modulo inizierà quindi a raccogliere nuovi dati dal momento in cui i prodotti vengono visualizzati o aggiornati.
  - **Valore consigliato:** Usare con cautela. Cancella i dati solo se hai bisogno di resettare la cronologia dei prezzi, ad esempio dopo una revisione importante del catalogo prodotti o se sospetti una corruzione dei dati.
  - **Scenario / esempio per il commerciante:** Hai importato un set completamente nuovo di prodotti con diverse strategie di prezzo e vuoi assicurarti che i dati Omnibus ricomincino da zero senza prezzi precedenti. Cliccheresti questo pulsante.

#### 2.1.1 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Abilita conformità Direttiva Omnibus | SÌ | Attiva/disattiva il tracciamento e la visualizzazione dei prezzi per la conformità UE. |
| Configurazione Modulo | Testo da visualizzare per il prezzo più basso | "Prezzo più basso negli ultimi 30 giorni:" | Personalizza il testo mostrato prima del prezzo storico. |
| Configurazione Modulo | Visualizza sulla pagina prodotto (Selezione Hook) | Profilo Classic/Hummingbird (in base al tema) | Determina dove appare la cronologia dei prezzi sulla pagina prodotto. |
| Configurazione Modulo | Nome Hook Personalizzato | (Vuoto) | Specifica un hook personalizzato per la visualizzazione se è selezionato "Hook Personalizzato". |
| Configurazione Modulo | Cancella Dati Omnibus | (Pulsante) | Elimina tutta la cronologia dei prezzi memorizzata, forzando un nuovo inizio. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D: Le informazioni sul prezzo più basso non vengono visualizzate sulle mie pagine prodotto.**
R:

1. **Controlla "Abilita conformità Direttiva Omnibus":** Assicurati che sia impostato su SÌ nella configurazione del modulo.
2. **Verifica "Visualizza sulla pagina prodotto (Selezione Hook)":** Prova a passare tra "Profilo Tema Classic" e "Profilo Tema Hummingbird" se non sei sicuro di quale si adatti meglio al tuo tema.
3. **Svuota la cache:** Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). A volte, le modifiche al tema o gli aggiornamenti del modulo richiedono un aggiornamento della cache.
4. **Verifica la presenza di sconti:** L'informazione appare solo quando un prodotto è effettivamente scontato. Assicurati che il prodotto che stai testando abbia un prezzo specifico attivo o una regola di prezzo del catalogo applicata.
5. **Tema personalizzato:** Se stai utilizzando un tema fortemente personalizzato, il modulo potrebbe non essere in grado di iniettare automaticamente il contenuto. Probabilmente dovrai utilizzare l'opzione "Hook Personalizzato" e far integrare il tuo webmaster nel file `product.tpl` del tuo tema.

**D: Il prezzo più basso visualizzato sembra errato o troppo alto/basso.**
R:

1. **Tempo di raccolta dati:** Il modulo ha bisogno di tempo per raccogliere i dati. Se lo hai appena installato, inizierà a tracciare i prezzi solo da quel momento. Ci vorranno 30 giorni per avere una cronologia completa di 30 giorni.
2. **Cancella Dati Omnibus:** Se sospetti che vengano utilizzati dati vecchi e errati, puoi cliccare sul pulsante "Cancella Dati Omnibus" nella configurazione del modulo. Tieni presente che questo eliminerà tutta la cronologia e il modulo inizierà a raccogliere i dati da zero.
3. **Combinazioni di prodotti/Valute:** Assicurati di guardare la combinazione e la valuta corrette. Il modulo traccia i prezzi per combinazione e valuta.

**D: Questo modulo rallenterà il mio negozio?**
R: Il modulo è progettato per essere leggero. Il tracciamento dei prezzi avviene in background o durante la visualizzazione dei prodotti, e la visualizzazione nel front office è un semplice output di testo. Qualsiasi impatto sulle prestazioni dovrebbe essere trascurabile.

**D: Come gestisce questo modulo i negozi multilingue?**
R: L'impostazione "Testo da visualizzare per il prezzo più basso" è traducibile. Puoi andare su **Internazionale > Traduzioni**, selezionare "Traduzioni dei moduli installati", scegliere il tuo tema e quindi selezionare il modulo "Direttiva Omnibus - Addon Gratuito" per tradurre il testo in tutte le tue lingue attive.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'Architettura

Il modulo "Direttiva Omnibus - Addon Gratuito" segue un'architettura standard per i moduli PrestaShop. La sua funzionalità principale risiede nel file `index.php`, che funge da punto di ingresso del modulo e gestisce l'installazione, la disinstallazione, la configurazione e la registrazione degli hook. La cronologia dei prezzi è gestita osservando le modifiche dei prezzi dei prodotti e memorizzandole, probabilmente in una tabella personalizzata o in `ps_configuration` (anche se il dossier indica nessun SQL personalizzato, implicando `ps_configuration` o generazione dinamica dei dati). La visualizzazione nel front-office è ottenuta agganciandosi ai punti di visualizzazione standard di PrestaShop, con logica specifica per i temi Classic e Hummingbird.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**: Nessuno esplicitamente definito nel dossier. La logica del front-office è probabilmente gestita direttamente all'interno dei metodi hook del file principale del modulo.
- **Controller Admin Back-Office**: Nessuno esplicitamente definito nel dossier. Tutta la configurazione del back-office è gestita tramite il metodo `getContent()` della classe principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

- Nessuno esplicitamente definito nel dossier. La logica del modulo, inclusi il tracciamento e l'archiviazione dei prezzi, è probabilmente incapsulata all'interno della classe `Omnifree` in `index.php`.
  - **Classe `Omnifree` (in `omnifree/index.php`)**:
    - Estende `Module`.
    - Gestisce l'installazione (`install()`) e la disinstallazione (`uninstall()`) del modulo.
    - Registra gli hook necessari (es. `displayHeader`, `displayProductPriceBlock`, `displayProductButtons`, `displayFooter`, `actionProductUpdate`, `actionProductSave`).
    - Gestisce le impostazioni di configurazione tramite `getContent()`.
    - Contiene metodi per il tracciamento e il recupero dei prezzi, probabilmente interagendo con `ps_configuration` per l'archiviazione dei prezzi storici o calcolandoli dinamicamente in base alla cronologia degli ordini.
    - Implementa i metodi hook (`hookDisplayHeader`, `hookDisplayProductPriceBlock`, `hookDisplayProductButtons`, `hookDisplayFooter`, ecc.) per iniettare contenuto nel front office.
    - Implementa gli hook di azione (`hookActionProductUpdate`, `hookActionProductSave`) per registrare le modifiche di prezzo.

### 4.4 Risorse JavaScript (`views/js/`)

- **`omnifree/views/js/admin-config.js`**:
  - **Ambito:** Back-office.
  - **Scopo:** Questo script probabilmente gestisce il comportamento dinamico della pagina di configurazione del modulo. Ciò potrebbe includere:
    - Mostrare/nascondere il campo di input "Nome Hook Personalizzato" in base al valore del menu a discesa "Visualizza sulla pagina prodotto (Selezione Hook)".
    - Chiamate AJAX per il pulsante "Cancella Dati Omnibus" per eseguire la pulizia dei dati senza un ricaricamento completo della pagina.
    - Validazione dell'input o altri elementi interattivi sul modulo di configurazione.
  - **Listener di eventi:** Probabilmente ascolta gli eventi `change` sui menu a discesa e gli eventi `click` sui pulsanti all'interno del modulo di configurazione del modulo.

### 4.5 Fogli di Stile CSS (`views/css/`)

- **`omnifree/views/css/admin-config.css`**:
  - **Ambito:** Stile del modulo di amministrazione del back-office.
  - **Scopo:** Fornisce uno stile specifico per gli elementi all'interno della pagina di configurazione del modulo nel back office di PrestaShop, garantendo un'interfaccia di amministrazione coerente e user-friendly.
  - **Selettori di classe CSS chiave:** Probabilmente si rivolge a ID o classi specifici all'interno del template `configure.tpl`.
- **`omnifree/views/css/omnibus-classic.css`**:
  - **Ambito:** Stile del cliente nel front-office (specificamente per il tema Classic).
  - **Scopo:** Contiene regole CSS per garantire che le informazioni sul prezzo più basso visualizzate siano correttamente stilizzate e posizionate all'interno del tema PrestaShop Classic, evitando conflitti e mantenendo l'armonia visiva.
  - **Selettori di classe CSS chiave:** Si rivolge a elementi come `.product-prices`, `.product-information` o classi personalizzate aggiunte dal modulo per la visualizzazione della cronologia dei prezzi.
- **`omnifree/views/css/omnibus-hummingbird.css`**:
  - **Ambito:** Stile del cliente nel front-office (specificamente per il tema Hummingbird).
  - **Scopo:** Fornisce regolazioni specifiche di stile e posizionamento per le informazioni sul prezzo più basso quando il tema Hummingbird (predefinito di PrestaShop 8.x) è attivo.
  - **Selettori di classe CSS chiave:** Si rivolge a elementi specifici della struttura della pagina prodotto del tema Hummingbird.
- **`omnifree/views/css/omnibus.css`**:
  - **Ambito:** Stile del cliente nel front-office (generale).
  - **Scopo:** Contiene regole CSS generali, agnostiche al tema, per la visualizzazione del prezzo più basso. Ciò potrebbe includere uno stile di carattere di base, colore o margine che si applica indipendentemente dal profilo del tema specifico scelto.
  - **Selettori di classe CSS chiave:** Classi generiche utilizzate in `omnibus.tpl`.

### 4.6 Struttura del Template Smarty (`views/templates/`)

- **Template Hook (`views/templates/hook/`)**:
  - **`omnifree/views/templates/hook/omnibus.tpl`**:
    - **Scopo:** Questo è il template primario del front-office responsabile del rendering delle informazioni sul prezzo più basso degli ultimi 30 giorni. Verrà renderizzato dai metodi hook del modulo (es. `hookDisplayProductPriceBlock`, `hookDisplayProductButtons` o un hook personalizzato).
    - **Variabili:** Probabilmente si aspetta variabili come `$lowest_price_30_days`, `$currency_symbol`, `$display_text` e potenzialmente `$product_id` o `$id_product_attribute`.
    - **Output:** Un piccolo snippet HTML contenente il testo configurato e il prezzo più basso formattato.
- **Template Admin (`views/templates/admin/`)**:
  - **`omnifree/views/templates/admin/configure.tpl`**:
    - **Scopo:** Questo template renderizza il modulo di configurazione principale per il modulo nel back office di PrestaShop. Include tutte le impostazioni descritte nella Sezione 4.1.
    - **Variabili:** Riceve i valori di configurazione da `getContent()` per pre-compilare i campi del modulo.
    - **Struttura:** Utilizza la struttura del modulo helper di PrestaShop (es. `AdminForm`) per creare i campi di input, gli interruttori e i pulsanti.
  - **`omnifree/views/templates/admin/pro-teaser.tpl`**:
    - **Scopo:** Questo template probabilmente visualizza contenuti promozionali o un "teaser" per una versione "Pro" o a pagamento del modulo Direttiva Omnibus di MyPresta.eu. Potrebbe evidenziare funzionalità aggiuntive disponibili nella versione premium.
    - **Posizionamento:** Probabilmente incluso all'interno di `configure.tpl` o visualizzato come blocco separato nella pagina di configurazione.

### 4.7 Schema del Database e Mappa degli Hook

- **Tabelle del Database**:
  - Il dossier indica nessun file SQL personalizzato. Ciò suggerisce che i dati della cronologia dei prezzi sono:
    1. Memorizzati direttamente in `ps_configuration` come array serializzati (meno efficiente per grandi dataset).
    2. Calcolati dinamicamente in base alle tabelle `ps_order_detail` e `ps_product_attribute_combination` (più complesso, ma evita tabelle personalizzate).
    3. Una tabella personalizzata viene creata programmaticamente all'interno di `install()` senza un file SQL separato. Data la natura di "Addon Gratuito", l'opzione 1 o 2 è più probabile per semplicità.
- **Tabella degli Hook Registrati**:

| Nome Hook | Ambito | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- | --- |
| `displayHeader` | Front-Office | Ad ogni caricamento di pagina nella sezione `<head>`. | Per caricare le risorse CSS/JS del modulo (es. `omnibus.css`, `omnibus-classic.css`, `omnibus-hummingbird.css`). |
| `displayProductPriceBlock` | Front-Office | Nelle pagine prodotto, tipicamente vicino al prezzo. | Uno degli hook primari per visualizzare le informazioni sul prezzo più basso nel tema Classic. |
| `displayProductButtons` | Front-Office | Nelle pagine prodotto, tipicamente vicino al pulsante "aggiungi al carrello". | Un altro potenziale hook per visualizzare le informazioni sul prezzo più basso nel tema Classic. |
| `displayFooter` | Front-Office | In fondo ad ogni pagina. | Meno probabile per la visualizzazione del prezzo, ma potrebbe essere utilizzato per messaggi generali di conformità o se un hook personalizzato è posizionato qui. |
| `actionProductUpdate` | Back-Office | Quando un prodotto viene aggiornato/salvato nel back office. | Per attivare il meccanismo di tracciamento dei prezzi e registrare il prezzo corrente del prodotto per la cronologia. |
| `actionProductSave` | Back-Office | Quando un prodotto viene salvato (nuovo o esistente) nel back office. | Simile a `actionProductUpdate`, assicura che le modifiche di prezzo vengano catturate. |
| `actionFrontControllerSetMedia` | Front-Office | Prima che un controller frontale renderizzi il suo output. | Per caricare condizionalmente CSS/JS specifici in base alla pagina o al tema corrente. |
| (Nome Hook Personalizzato) | Front-Office | Dove il commerciante posiziona `{hook h='CustomHookName'}` nel suo template. | Consente un posizionamento flessibile della visualizzazione del prezzo più basso per temi altamente personalizzati. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Direttiva Omnibus - Addon Gratuito", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu). Il nostro team di supporto è disponibile per assistere commercianti e sviluppatori con qualsiasi problema o domanda relativa alla funzionalità e all'integrazione del modulo.
