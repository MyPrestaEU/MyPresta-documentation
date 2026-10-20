---
title: "Mostra tag nella pagina prodotto - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Mostra tag nella pagina prodotto' di MyPresta.eu."
sidebar:
  label: "Mostra tag nella pagina prodotto - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Show tags on product page su MyPresta.eu](https://mypresta.eu/modules/front-office-features/show-tags-on-product-page.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/show-tags-on-product-page/)
>
> ---


# Mostra tag nella pagina prodotto

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL) tipicamente presenti in qualsiasi ambiente di hosting PrestaShop moderno.

## 2. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)

Questo modulo presenta una pagina di configurazione semplice, che ti consente di abilitare o disabilitare rapidamente la sua funzionalità e scegliere dove i tag appariranno nelle tue pagine prodotto.

**Accesso:** Naviga su **Moduli > Gestione moduli**, cerca "Mostra tag nella pagina prodotto" e clicca su "Configura".

#### **Abilita / Disabilita Modulo**

- **Cosa fa questa impostazione:** Questo è l'interruttore principale per la funzionalità del modulo.
- **Effetto della modifica di questa impostazione:**
  - *Quando abilitato:* Il modulo inizierà a visualizzare i tag del prodotto nelle pagine prodotto del tuo front office in base all'hook scelto.
  - *Quando disabilitato:* Il modulo smetterà di visualizzare i tag del prodotto. Tutte le altre impostazioni verranno salvate ma saranno inattive.
- **Valore consigliato:** SÌ
- **Scenario / esempio del commerciante:** Vuoi testare il modulo o nascondere temporaneamente i tag durante una riprogettazione del sito. Lo disabiliteresti e poi lo riabiliteresti quando pronto.

#### **Seleziona Hook per Visualizzare i Tag**

- **Cosa fa questa impostazione:** Questa impostazione cruciale determina *dove* nella pagina del prodotto verranno visualizzati i tag. PrestaShop utilizza gli "hook" come punti specifici nel codice della pagina dove i moduli possono inserire il loro contenuto.
- **Effetto della modifica di questa impostazione:**
  - *Se impostato su `displayProductButtons` (PrestaShop 1.7+):* I tag appariranno tipicamente vicino al pulsante "Aggiungi al carrello" o ad altri pulsanti di azione del prodotto. Questa è spesso una posizione prominente ed efficace.
  - *Se impostato su `displayProductExtraContent` (PrestaShop 1.7+):* I tag appariranno in una sezione dedicata per contenuti extra del prodotto, spesso sotto le informazioni principali del prodotto o all'interno di una scheda.
  - *Se impostato su `displayFooterProduct` (PrestaShop 1.7+):* I tag appariranno nella parte inferiore della pagina del prodotto, spesso sopra il footer dell'intero sito web.
  - *Se impostato su `displayLeftColumnProduct` (PrestaShop 1.7+):* I tag appariranno nella colonna sinistra specificamente nella pagina del prodotto.
  - *Se impostato su `displayRightColumnProduct` (PrestaShop 1.7+):* I tag appariranno nella colonna destra specificamente nella pagina del prodotto.
  - *Altri hook (ad esempio, `displayProductTab`, `displayProductTabContent`, `displayFooter`):* La posizione esatta dipenderà dall'implementazione di questi hook da parte del tuo tema. `displayFooter` posizionerebbe i tag nel footer generale del sito web, che di solito non è specifico del prodotto.
- **Valore consigliato:** `displayProductButtons` o `displayProductExtraContent` sono generalmente i più efficaci per visibilità e contesto. Sperimenta per vedere cosa si adatta meglio al tuo tema.
- **Scenario / esempio del commerciante:** Vuoi che i tag siano altamente visibili per incoraggiare la scoperta immediata di prodotti simili, quindi scegli `displayProductButtons`. Se preferisci che siano meno invasivi e parte di informazioni supplementari, `displayProductExtraContent` potrebbe essere migliore.

#### **Titolo per il Blocco Tag**

- **Cosa fa questa impostazione:** Ti consente di impostare un titolo personalizzato che apparirà sopra l'elenco dei tag nella pagina del prodotto.
- **Effetto della modifica di questa impostazione:**
  - *Quando viene inserito un titolo (ad esempio, "Tag Prodotto", "Parole Chiave Correlate"):* Questo titolo verrà visualizzato sopra l'elenco dei tag, fornendo un'intestazione chiara per i tuoi clienti.
  - *Quando lasciato vuoto:* Nessun titolo verrà visualizzato, e apparirà solo l'elenco dei tag.
- **Valore consigliato:** "Tag Prodotto" o "Parole Chiave"
- **Scenario / esempio del commerciante:** Vuoi etichettare chiaramente la sezione in modo che i clienti ne comprendano lo scopo. Impostare il titolo su "Tag Correlati" aiuta a guidare la loro interazione.

### 2.2 Tabella di Riferimento Rapido della Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Abilita Modulo | SÌ | Attiva/disattiva la funzionalità di visualizzazione dei tag del modulo. |
| Configurazione Modulo | Seleziona Hook per Visualizzare i Tag | `displayProductButtons` o `displayProductExtraContent` | Determina la posizione esatta dei tag nella pagina del prodotto. |
| Configurazione Modulo | Titolo per il Blocco Tag | "Tag Prodotto" | Imposta un'intestazione per i tag visualizzati, migliorando la chiarezza per i clienti. |

## 3. Risoluzione dei Problemi del Commerciante e Domande Frequenti (FAQ)

**D1: Ho installato e configurato il modulo, ma i tag non vengono visualizzati nelle mie pagine prodotto. Cosa c'è che non va?**
**R1:**

- **Verifica lo Stato del Modulo:** Assicurati che il modulo sia "Abilitato" nella sua configurazione.
- **Svuota la Cache:** Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti). PrestaShop spesso memorizza i contenuti nella cache e il nuovo output del modulo potrebbe non apparire finché la cache non viene svuotata.
- **Verifica i Tag del Prodotto:** Assicurati che il prodotto specifico che stai visualizzando abbia effettivamente dei tag assegnati. Modifica il prodotto nel Back Office e controlla la scheda "SEO" o "Tag".
- **Compatibilità del Tema:** Alcuni temi altamente personalizzati potrebbero sovrascrivere gli hook standard di PrestaShop o avere layout unici. Prova a passare temporaneamente al tema predefinito di PrestaShop (ad esempio, Classic) per vedere se i tag appaiono. Se lo fanno, il tuo tema personalizzato potrebbe richiedere una piccola modifica (vedi Q3).
- **Selezione dell'Hook:** Ricontrolla di aver selezionato un hook appropriato nella configurazione del modulo. Alcuni hook potrebbero non essere renderizzati dal tuo tema in una posizione visibile.

**D2: I tag vengono visualizzati, ma sembrano semplici o non corrispondono allo stile del mio tema.**
**R2:**

- Il modulo fornisce uno stile di base. Se vuoi che corrispondano perfettamente al tuo tema, dovrai aggiungere CSS personalizzato.
- **Come farlo:**
  1. Ispeziona i tag nella pagina del tuo prodotto usando gli strumenti per sviluppatori del tuo browser (clic destro, poi "Ispeziona").
  2. Identifica le classi CSS utilizzate dai tag (ad esempio, `ptags_block`, `ptags_item`).
  3. Aggiungi regole CSS personalizzate al file `custom.css` del tuo tema (se ne ha uno) o direttamente nel file `ptags.css` del modulo (anche se modificare direttamente i file del modulo non è consigliato poiché gli aggiornamenti li sovrascriveranno).
  - **Esempio CSS:**

    ```
    .ptags\_block { margin-top: 20px; padding: 15px; border: 1px solid #eee; background-color: #f9f9f9;}.ptags\_block h3 { font-size: 18px; color: #333; margin-bottom: 10px;}.ptags\_item { display: inline-block; margin-right: 8px; margin-bottom: 8px;}.ptags\_item a { background-color: #007bff; color: white; padding: 5px 10px; border-radius: 3px; text-decoration: none; font-size: 14px;}.ptags\_item a:hover { background-color: #0056b3;}
    ```

**D3: I tag appaiono, ma sono in una posizione scomoda, o li voglio in un punto molto specifico non elencato nelle opzioni dell'hook.**
**R3:**

- Il modulo si basa sugli hook standard di PrestaShop. Se hai bisogno di un posizionamento altamente specifico e non standard, di solito richiede la modifica del tema.
- **Soluzione:** Tu o il tuo sviluppatore web dovreste inserire manualmente la funzione di visualizzazione del modulo nel file template della pagina prodotto del vostro tema (`product.tpl` o `product-details.tpl` nella cartella del vostro tema).
  - Trova la posizione esatta nel file `.tpl` del tuo tema dove vuoi che appaiano i tag.
  - Inserisci il seguente codice Smarty: `{hook h='displayProductTags' product=$product}` (Nota: `displayProductTags` è un nome di hook personalizzato che dovresti registrare nel modulo, oppure puoi usare `displayProductButtons` se è quello che hai configurato).
  - In alternativa, puoi chiamare direttamente il modulo: `{Module::getInstanceByName('ptags')->hookDisplayProductTags(['product' => $product])}`. Questo è più diretto ma meno flessibile rispetto all'uso di un hook.
- **Importante:** Questo richiede una conoscenza di base dello sviluppo di temi PrestaShop.

**D4: Questo modulo rallenterà il mio negozio?**
**R4:**

- No, questo modulo è molto leggero. Esegue una semplice query al database per recuperare i tag associati al prodotto corrente. Questa operazione è altamente ottimizzata dal core di PrestaShop e non avrà un impatto significativo sui tempi di caricamento della pagina.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

### 4.1 Panoramica dell'Architettura

Il modulo "Mostra tag nella pagina prodotto" (`ptags`) è un modulo PrestaShop semplice progettato per estendere la funzionalità del front-office. Segue una classica architettura del modulo PrestaShop, sfruttando principalmente la classe `Module` e i suoi metodi `install()`, `uninstall()` e `hook`. Non introduce controller, modelli o JavaScript complessi personalizzati. La sua funzione principale è recuperare i tag del prodotto e renderli tramite un template Smarty in un hook del front-office scelto.

### 4.2 Controller (`controllers/`)

Questo modulo **non** contiene alcun controller Front-Office o Back-Office personalizzato. Tutta la logica è incapsulata all'interno della classe principale del modulo (`ptags/index.php`) ed eseguita tramite il sistema di hook di PrestaShop.

### 4.3 Classi e Modelli Core (`classes/`)

Questo modulo **non** introduce classi personalizzate o definizioni di `ObjectModel`. Utilizza direttamente le classi core `Tag` e `Product` di PrestaShop per recuperare i dati necessari.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo **non** contiene alcun file JavaScript personalizzato. La sua funzionalità è puramente il rendering HTML lato server.

### 4.5 Fogli di Stile CSS (`views/css/`)

- **Percorso del file**: `ptags/views/css/ptags.css`
- **Ambito**: Styling del front-office per il cliente.
- **Componenti UI principali e contenitori che stilizza**: Questo foglio di stile fornisce uno styling di base per il blocco contenente i tag del prodotto e i singoli link dei tag.
- **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere nel loro tema**:
  - `.ptags_block`: Stila il blocco contenitore principale per i tag.
  - `.ptags_block h3`: Stila il titolo del blocco dei tag.
  - `.ptags_item`: Stila ogni singolo elemento tag (ad esempio, `display: inline-block`, margini).
  - `.ptags_item a`: Stila i link dei tag cliccabili (ad esempio, sfondo, colore, padding, border-radius).

### 4.6 Struttura del Template Smarty (`views/templates/`)

- **Template degli hook (`views/templates/hook/`)**:
  - **Percorso del file**: `ptags/views/front/ptags.tpl`
  - **Renderizzato nell'hook**: Questo template viene renderizzato dai metodi `hook` del modulo (ad esempio, `hookDisplayProductButtons`, `hookDisplayProductExtraContent`, ecc., a seconda della configurazione).
  - **Output del blocco visivo**: Questo template è responsabile dell'output della struttura HTML per il blocco dei tag, inclusi il titolo opzionale e l'elenco dei link dei tag cliccabili. Itera attraverso la variabile `$tags` (un array di oggetti tag) passata dal metodo hook del modulo.

### 4.7 Schema del Database e Mappa degli Hook

- **Tabelle del Database**: Questo modulo non crea tabelle del database personalizzate. Si basa sulle tabelle esistenti di PrestaShop, principalmente `ps_tag`, `ps_product_tag` e `ps_lang` per i dati dei tag.

  - Le impostazioni di configurazione sono memorizzate in `ps_configuration` con chiavi come `PTAGS_ENABLED`, `PTAGS_HOOK`, `PTAGS_TITLE`.
- **Tabella degli Hook Registrati**:

  | Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
  | --- | --- | --- |
  | `displayHeader` | Nella sezione `<head>` di ogni pagina. | Utilizzato per caricare il foglio di stile CSS del modulo (`ptags.css`). |
  | `displayProductButtons` | Nella pagina del prodotto, tipicamente vicino al pulsante "Aggiungi al carrello". | Visualizza il blocco dei tag del prodotto. (PrestaShop 1.7+) |
  | `displayProductExtraContent` | Nella pagina del prodotto, in una sezione dedicata per contenuti extra. | Visualizza il blocco dei tag del prodotto. (PrestaShop 1.7+) |
  | `displayFooterProduct` | Nella parte inferiore del contenuto della pagina del prodotto. | Visualizza il blocco dei tag del prodotto. (PrestaShop 1.7+) |
  | `displayLeftColumnProduct` | Nella colonna sinistra specificamente nella pagina del prodotto. | Visualizza il blocco dei tag del prodotto. (PrestaShop 1.7+) |
  | `displayRightColumnProduct` | Nella colonna destra specificamente nella pagina del prodotto. | Visualizza il blocco dei tag del prodotto. (PrestaShop 1.7+) |
  | `displayProductTab` | Aggiunge una nuova scheda alla pagina del prodotto. | (Se configurato) Visualizza i tag del prodotto all'interno di una scheda. |
  | `displayProductTabContent` | Contenuto per una scheda della pagina del prodotto. | (Se configurato) Visualizza i tag del prodotto come contenuto per una scheda. |
  | `displayFooter` | Nel footer generale del sito web. | (Se configurato) Visualizza il blocco dei tag del prodotto nel footer globale. |
  | `displayLeftColumn` | Nella colonna sinistra delle pagine (non specifica del prodotto). | (Se configurato) Visualizza il blocco dei tag del prodotto nella colonna sinistra globale. |
  | `displayRightColumn` | Nella colonna destra delle pagine (non specifica del prodotto). | (Se configurato) Visualizza il blocco dei tag del prodotto nella colonna destra globale. |

  Il modulo si registra dinamicamente all'hook selezionato nella sua configurazione. Il file `index.php` contiene i metodi `hook[NomeHook]` che recuperano l'ID del prodotto, recuperano i tag associati e li passano a `ptags.tpl` per il rendering.

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Mostra tag nella pagina prodotto", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere commercianti e sviluppatori con qualsiasi problema o domanda relativa alla funzionalità e all'integrazione del modulo.
