---
title: "Passo dopo passo - categorie - Manuale del commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Passo dopo passo - categorie di MyPresta.eu."
sidebar:
  label: "Passo dopo passo - categorie - Manuale del commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Step by step - categories su MyPresta.eu](https://mypresta.eu/modules/front-office-features/step-by-step-categories.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/step-by-step-categories/)
>
> ---


# Passo dopo passo - categorie

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Nessun requisito speciale del server oltre a un ambiente di hosting PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" si accederà alla schermata di configurazione principale per "Passo dopo passo - categorie". Qui è dove si controlla il comportamento e l'aspetto del modulo sul tuo negozio.

| Impostazione / Opzione | Cosa fa questa impostazione | Effetto della modifica di questa impostazione | Valore consigliato | Scenario / esempio del commerciante |
| --- | --- | --- | --- | --- |
| **Visualizza blocco nell'intestazione** | Controlla se la navigazione per categorie passo dopo passo appare nella sezione dell'intestazione del tuo negozio. | *Quando abilitato:* I menu a discesa delle categorie saranno visibili nella parte superiore del tuo sito web, spesso vicino al logo o alla navigazione principale. Ciò fornisce un accesso immediato al filtro per categorie. *Quando disabilitato:* Il blocco non apparirà nell'intestazione. | **SÌ** (se desideri una navigazione prominente) | Vuoi che i clienti trovino facilmente i prodotti da qualsiasi pagina, quindi posizionarlo nell'intestazione lo rende sempre accessibile. |
| **Visualizza blocco nella colonna sinistra** | Controlla se la navigazione per categorie passo dopo passo appare nella barra laterale sinistra del tuo negozio. | *Quando abilitato:* I menu a discesa delle categorie saranno visibili nella colonna sinistra del tuo sito web (se il tuo tema supporta una colonna sinistra). Questo è un posizionamento tradizionale per i filtri per categorie. *Quando disabilitato:* Il blocco non apparirà nella colonna sinistra. | **SÌ** (se il tuo tema ha una colonna sinistra e desideri la navigazione nella barra laterale) | Il tuo tema ha una barra laterale sinistra e preferisci mantenere gli elementi di navigazione organizzati lì, in modo simile a un albero di categorie standard. |
| **Visualizza blocco nella colonna destra** | Controlla se la navigazione per categorie passo dopo passo appare nella barra laterale destra del tuo negozio. | *Quando abilitato:* I menu a discesa delle categorie saranno visibili nella colonna destra del tuo sito web (se il tuo tema supporta una colonna destra). *Quando disabilitato:* Il blocco non apparirà nella colonna destra. | **NO** (a meno che il tuo tema non utilizzi specificamente una colonna destra per la navigazione) | Il tuo tema utilizza la colonna destra per informazioni supplementari e desideri posizionare la navigazione per categorie lì invece che a sinistra. |
| **Visualizza blocco nel piè di pagina** | Controlla se la navigazione per categorie passo dopo passo appare nella sezione del piè di pagina del tuo negozio. | *Quando abilitato:* I menu a discesa delle categorie saranno visibili nella parte inferiore del tuo sito web. Questo è meno comune per la navigazione primaria ma può essere utile per l'accesso secondario. *Quando disabilitato:* Il blocco non apparirà nel piè di pagina. | **NO** (a meno che per specifiche ragioni di design) | Hai un'intestazione e delle colonne molto minimaliste e vuoi offrire la navigazione per categorie nel piè di pagina come alternativa per gli utenti che scorrono verso il basso. |
| **Visualizza blocco nella pagina prodotto** | Controlla se la navigazione per categorie passo dopo passo appare nelle singole pagine prodotto. | *Quando abilitato:* I menu a discesa delle categorie saranno visibili nelle pagine dei dettagli del prodotto. Questo può aiutare i clienti a esplorare altre categorie o prodotti correlati. *Quando disabilitato:* Il blocco non apparirà nelle pagine prodotto. | **NO** (a meno che tu non abbia una necessità specifica) | Vuoi incoraggiare i clienti che visualizzano un prodotto a passare facilmente ad altre categorie senza lasciare la pagina del prodotto, magari per confrontare gli articoli. |
| **Mostra pulsante "Vai"** | Determina se un pulsante "Vai" o "Cerca" viene visualizzato accanto all'ultimo menu a discesa delle categorie. | *Quando abilitato:* Apparirà un pulsante. I clienti devono fare clic su questo pulsante per essere reindirizzati alla pagina della categoria selezionata. *Quando disabilitato:* I clienti vengono automaticamente reindirizzati alla pagina della categoria selezionata non appena effettuano la selezione finale nell'ultimo menu a discesa. | **SÌ** (per un maggiore controllo) | Vuoi che i clienti confermino la loro selezione di categoria prima di essere reindirizzati, dando loro la possibilità di rivedere la loro scelta. |
| **Numero di menu a discesa** | Imposta il numero massimo di livelli di categoria (profondità) che verranno visualizzati come menu a discesa. | *Quando impostato su 1:* Verranno visualizzate solo le categorie di primo livello in un unico menu a discesa. *Quando impostato su 3:* Verranno visualizzati fino a tre livelli di categorie (es. Categoria principale > Sottocategoria 1 > Sottocategoria 2) in menu a discesa separati. | **3** (o in base alla profondità delle tue categorie) | Il tuo negozio ha categorie annidate fino a 3 o 4 livelli di profondità e vuoi che i clienti possano approfondire in modo efficiente. |
| **Categoria radice** | Specifica il punto di partenza per la navigazione per categorie. Verranno visualizzate solo le categorie all'interno di questa radice. | *Quando impostato su "Home":* Tutte le categorie a partire dalla cima del tuo catalogo saranno disponibili. *Quando impostato su "Elettronica":* Verranno mostrate nei menu a discesa solo le categorie sotto "Elettronica" (es. "Laptop", "Smartphone"). | **Home** (a meno che tu non voglia limitare la navigazione) | Vuoi offrire la navigazione passo dopo passo solo per una parte specifica del tuo catalogo, come "Abbigliamento", ed escludere altre sezioni come "Casa e Giardino". |

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Visualizza blocco nell'intestazione | SÌ | Mostra i menu a discesa delle categorie nell'intestazione del negozio per una navigazione prominente. |
| Configurazione modulo | Visualizza blocco nella colonna sinistra | SÌ | Mostra i menu a discesa delle categorie nella barra laterale sinistra per la navigazione tradizionale. |
| Configurazione modulo | Visualizza blocco nella colonna destra | NO | Mostra i menu a discesa delle categorie nella barra laterale destra. |
| Configurazione modulo | Visualizza blocco nel piè di pagina | NO | Mostra i menu a discesa delle categorie nel piè di pagina del negozio. |
| Configurazione modulo | Visualizza blocco nella pagina prodotto | NO | Mostra i menu a discesa delle categorie nelle pagine dei dettagli del prodotto. |
| Configurazione modulo | Mostra pulsante "Vai" | SÌ | Richiede ai clienti di fare clic su un pulsante per navigare alla categoria selezionata. |
| Configurazione modulo | Numero di menu a discesa | 3 | Imposta la profondità massima dei livelli di categoria visualizzati. |
| Configurazione modulo | Categoria radice | Home | Definisce il punto di partenza per la navigazione per categorie. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Il modulo è installato, ma non vedo i menu a discesa nel mio negozio.**
R1:

- **Controlla la configurazione:** Vai su **Moduli > Gestione moduli > Passo dopo passo - categorie > Configura**. Assicurati che almeno un'opzione "Visualizza blocco in..." (es. "Visualizza blocco nell'intestazione", "Visualizza blocco nella colonna sinistra") sia impostata su **SÌ**.
- **Svuota la cache:** PrestaShop spesso memorizza i contenuti nella cache. Vai su **Parametri avanzati > Prestazioni** e fai clic su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti).
- **Compatibilità del tema:** Alcuni temi altamente personalizzati potrebbero richiedere piccole modifiche. Se svuotare la cache non aiuta, prova a passare temporaneamente al tema PrestaShop predefinito per vedere se il modulo appare. Se lo fa, il tuo tema potrebbe sovrascrivere le posizioni degli hook standard.

**D2: I menu a discesa appaiono, ma non si aggiornano quando seleziono una categoria.**
R2:

- **Problemi AJAX:** Questo di solito indica un errore JavaScript. Apri la console per sviluppatori del tuo browser (F12) e controlla eventuali errori nella scheda "Console".
- **JavaScript in conflitto:** Un altro modulo o il JavaScript del tuo tema potrebbero interferire. Prova a disabilitare altri moduli del front-office uno per uno per identificare i conflitti.
- **File del modulo:** Assicurati che tutti i file del modulo siano stati caricati correttamente e non siano danneggiati. Ricaricare il modulo potrebbe risolvere il problema.

**D3: Come posso modificare lo stile (colori, caratteri, dimensioni) dei menu a discesa?**
R3:

- Il modulo utilizza CSS standard. Avrai bisogno di conoscenze CSS di base o di un webmaster.
- I file CSS del modulo (es. `sbs-block.css`, `sbs-header.css`) definiscono gli stili predefiniti.
- **Migliore pratica:** NON modificare direttamente i file CSS del modulo, poiché le tue modifiche andranno perse durante gli aggiornamenti. Invece, usa il file CSS personalizzato del tuo tema (spesso trovato in `themes/yourtheme/assets/css/custom.css` o simile) per sovrascrivere gli stili del modulo. Usa l'ispettore del tuo browser (F12) per identificare le classi CSS utilizzate dai menu a discesa.

**D4: Le mie categorie sono molto profonde, ma vedo solo pochi menu a discesa.**
R4:

- **Impostazione "Numero di menu a discesa":** Vai su **Moduli > Gestione moduli > Passo dopo passo - categorie > Configura** e regola l'impostazione "Numero di menu a discesa". Aumenta questo valore per corrispondere alla profondità massima delle categorie che desideri visualizzare. Ricorda che visualizzare troppi menu a discesa potrebbe ingombrare l'interfaccia.

**D5: Il modulo mostra categorie che non voglio includere nella navigazione passo dopo passo.**
R5:

- **Impostazione "Categoria radice":** Nella configurazione del modulo, usa l'impostazione "Categoria radice". Seleziona una categoria padre specifica da cui desideri che inizi la navigazione passo dopo passo. Verranno visualizzate solo le categorie e le sottocategorie sotto la radice scelta.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Passo dopo passo - categorie" è principalmente una funzionalità di front-office che sfrutta l'architettura dei moduli di PrestaShop. Utilizza una classe `Module` standard per l'installazione e la configurazione, e classi `ModuleFrontController` per gestire le richieste AJAX per il caricamento dinamico delle categorie. Non introduce classi `ObjectModel` o tabelle di database personalizzate, basandosi sull'oggetto `Category` nativo di PrestaShop per i dati. Il modulo utilizza ampiamente i template Smarty per il rendering e JavaScript per la funzionalità AJAX interattiva.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**:
  - `controllers/front/ajaxload.php`
    - Nome classe: `StepbystepAjaxloadModuleFrontController`
    - Classe padre: `ModuleFrontController`
    - Responsabilità: Questo controller è il cuore della funzionalità AJAX. Risponde alle richieste dal JavaScript del front-office per recuperare le sottocategorie in base a un ID di categoria padre. Tipicamente restituisce dati JSON contenenti nomi e ID di categoria per popolare i menu a discesa successivi.
  - `controllers/front/index.php`
    - Nome classe: `StepbystepIndexModuleFrontController`
    - Classe padre: `ModuleFrontController`
    - Responsabilità: Questo controller probabilmente funge da punto di ingresso predefinito o fallback per il routing del front-office del modulo, sebbene la sua funzione principale possa essere minima data la natura basata su AJAX. Potrebbe gestire la logica di visualizzazione iniziale o il reindirizzamento se il modulo dovesse avere una pagina dedicata.
  - `controllers/front/tree.php`
    - Nome classe: `StepbystepTreeModuleFrontController`
    - Classe padre: `ModuleFrontController`
    - Responsabilità: Questo controller potrebbe essere responsabile del rendering di una struttura completa dell'albero delle categorie, potenzialmente per il debug o un metodo di visualizzazione alternativo, sebbene la caratteristica principale del modulo siano i menu a discesa. Potrebbe anche essere utilizzato per generare i dati iniziali per il primo menu a discesa.

### 4.3 Classi e modelli principali (`classes/`)

Il modulo non contiene classi personalizzate nella directory `classes/`. Utilizza direttamente la classe `Category` di PrestaShop e altre funzioni di supporto per recuperare i dati delle categorie.

### 4.4 Risorse JavaScript (`views/js/`)

- `stepbystep/js/advajax.js`
  - Scopo: Front-office
  - Questo è il file JavaScript principale responsabile del comportamento interattivo del modulo.
  - Collega i listener di eventi agli elementi `<select>` dei menu a discesa delle categorie.
  - Quando viene effettuata una selezione in un menu a discesa, attiva una richiesta AJAX (probabilmente a `ajaxload.php`) per recuperare il livello successivo di sottocategorie.
  - Crea e popola dinamicamente i menu a discesa successivi con i dati ricevuti.
  - Gestisce il reindirizzamento alla pagina della categoria finale quando viene effettuata una selezione o viene cliccato il pulsante "Vai".
  - Gestisce la visibilità e lo stato dei menu a discesa in base all'interazione dell'utente e alla configurazione del modulo (es. "Numero di menu a discesa").

### 4.5 Fogli di stile CSS (`views/css/`)

- `stepbystep/css/sbs-block.css`
  - Scopo: Stile del cliente del front-office
  - Stila l'aspetto generale del blocco categorie passo dopo passo, inclusi padding, margini e layout complessivo quando posizionato in colonne o altre posizioni simili a blocchi.
  - Selettori chiave: `.sbs-block`, `.sbs-category-select-wrapper`
- `stepbystep/css/sbs-header.css`
  - Scopo: Stile del cliente del front-office
  - Stila specificamente il modulo quando è agganciato alla posizione `displayHeader`, potenzialmente adattandosi ai layout dell'intestazione (es. visualizzazione in linea, larghezze specifiche).
  - Selettori chiave: `.sbs-header-container`
- `stepbystep/css/sbs-top.css`
  - Scopo: Stile del cliente del front-office
  - Probabilmente stila il modulo quando è agganciato a `displayTop` o posizioni simili nella parte superiore della pagina, simile a `sbs-header.css` ma per contesti visivi diversi.
  - Selettori chiave: `.sbs-top-container`
- `stepbystep/css.css`
  - Scopo: Stile del cliente del front-office
  - Un foglio di stile generale che potrebbe contenere stili comuni applicabili a tutti i posizionamenti o stili di fallback.
  - Selettori chiave: `.sbs-select`, `.sbs-go-button`

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template hook (`views/templates/hook/`)**:

  - `block.tpl`: Questo template è probabilmente utilizzato quando il modulo è agganciato a `displayLeftColumn` o `displayRightColumn`. Renderizza i menu a discesa passo dopo passo all'interno di una struttura di blocco standard di PrestaShop.
  - `blockSbs.tpl`: Questo potrebbe essere un template di blocco alternativo o più generico, potenzialmente utilizzato per altri hook di colonna o posizionamenti personalizzati specifici.
  - `displaySearch.tpl`: Questo template potrebbe essere destinato all'integrazione vicino a una barra di ricerca o come parte di un hook correlato alla ricerca, fornendo i menu a discesa come strumento di affinamento della ricerca.
  - `header.tpl`: Questo template è utilizzato quando il modulo è agganciato a `displayHeader`. Renderizza i menu a discesa all'interno della sezione dell'intestazione del negozio.
  - `top.tpl`: Questo template è utilizzato quando il modulo è agganciato a `displayTop`. Simile a `header.tpl`, ma per l'hook `displayTop`, che è spesso utilizzato per la barra di navigazione principale.
- **Template di amministrazione (`views/templates/admin/`)**: Nessuno identificato. La configurazione è gestita direttamente in `getContent()`.
- **Template front-office (`views/templates/front/`)**: Nessuno identificato come pagine autonome.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**: Il modulo non crea tabelle SQL personalizzate. Memorizza le sue impostazioni di configurazione nella tabella `ps_configuration` di PrestaShop utilizzando chiavi come `STEPMYSTEP_HEADER`, `STEPMYSTEP_LEFT`, `STEPMYSTEP_RIGHT`, `STEPMYSTEP_FOOTER`, `STEPMYSTEP_PRODUCT`, `STEPMYSTEP_GO_BUTTON`, `STEPMYSTEP_DROPDOWNS`, `STEPMYSTEP_ROOT_CATEGORY`.
- **Tabella degli hook registrati**:

| Nome dell'hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Renderizza il contenuto all'interno della sezione `<head>` dell'HTML, o all'inizio del `<body>` prima di altro contenuto. | Inietta risorse CSS/JS e potenzialmente la struttura HTML del modulo se configurato per la visualizzazione nell'intestazione. |
| `displayLeftColumn` | Renderizza il contenuto nella barra laterale sinistra del negozio. | Visualizza i menu a discesa delle categorie passo dopo passo nella colonna sinistra. |
| `displayRightColumn` | Renderizza il contenuto nella barra laterale destra del negozio. | Visualizza i menu a discesa delle categorie passo dopo passo nella colonna destra. |
| `displayFooter` | Renderizza il contenuto nella sezione del piè di pagina del negozio. | Visualizza i menu a discesa delle categorie passo dopo passo nel piè di pagina. |
| `displayProductAdditionalInfo` (o hook simile per la pagina prodotto) | Renderizza il contenuto nella pagina del prodotto, spesso sotto la descrizione del prodotto o in un blocco specifico. | Visualizza i menu a discesa delle categorie passo dopo passo nelle pagine dei prodotti. |
| `displayTop` | Renderizza il contenuto nella sezione superiore della pagina, tipicamente sopra o all'interno della navigazione principale. | Visualizza i menu a discesa delle categorie passo dopo passo nella barra superiore. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Passo dopo passo - categorie", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda.
