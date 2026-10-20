---
title: "Funzionalità delle combinazioni di prodotto - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Funzionalità delle combinazioni di prodotto' di MyPresta.eu."
sidebar:
  label: "Funzionalità delle combinazioni di prodotto - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Product combination features su MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-combination-features.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/product-combination-features/)
>
> ---


# Funzionalità delle combinazioni di prodotto

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo "Funzionalità delle combinazioni di prodotto". Puoi accedervi navigando su **Moduli > Gestione moduli**, cercando "Funzionalità delle combinazioni di prodotto" e facendo clic su "Configura".

#### **Attiva le funzionalità per le combinazioni**

-   **Cosa fa questa impostazione:** Questo è l'interruttore principale per abilitare o disabilitare la funzionalità principale di assegnazione di funzionalità uniche alle combinazioni di prodotto.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* Vedrai una nuova sezione nelle tue pagine di modifica del prodotto (sotto la scheda "Moduli") dove puoi assegnare funzionalità specifiche e i loro valori a ogni combinazione. Quando i clienti selezionano una combinazione nel front office, la scheda tecnica del prodotto si aggiornerà dinamicamente per mostrare queste funzionalità specifiche della combinazione.
    -   *Quando disabilitato:* La sezione di gestione delle funzionalità della combinazione non apparirà nelle pagine di modifica del prodotto e il front office tornerà a mostrare solo le funzionalità del prodotto principale, indipendentemente dalla combinazione selezionata.
-   **Valore consigliato:** **Abilitato** (se desideri utilizzare la funzione principale del modulo).
-   **Scenario / esempio del commerciante:** Se vendi magliette e desideri "Materiale: 100% Cotone" per la maglietta bianca e "Materiale: 50% Cotone, 50% Poliestere" per la maglietta grigia, *devi* abilitare questa opzione.

#### **Classe CSS della scheda tecnica**

-   **Cosa fa questa impostazione:** Questo ti consente di specificare una classe CSS o un ID di elemento HTML che il modulo dovrebbe prendere di mira quando aggiorna la sezione delle funzionalità nella pagina del prodotto. Questo è fondamentale affinché il modulo identifichi correttamente dove visualizzare le funzionalità specifiche della combinazione nel tuo tema.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato correttamente:* Il modulo troverà l'elemento specificato e inserirà o aggiornerà dinamicamente le funzionalità della combinazione al suo interno.
    -   *Quando impostato in modo errato o lasciato vuoto:* Le funzionalità della combinazione potrebbero non apparire nel front office, o potrebbero apparire in una posizione inaspettata, poiché il modulo non saprà dove posizionarle.
-   **Valore consigliato:** Questo dipende interamente dal tuo tema PrestaShop. Una classe comune è `.product-features` o `.data-sheet`. Potrebbe essere necessario ispezionare l'HTML della pagina del tuo prodotto per trovare il selettore corretto. In caso di dubbi, consulta lo sviluppatore del tuo tema o un webmaster.
-   **Scenario / esempio del commerciante:** Il tuo tema visualizza le funzionalità del prodotto all'interno di un `div` con la classe `product-specifications`. Inseriresti `.product-specifications` qui.

#### **Flusso di lavoro**

-   **Cosa fa questa impostazione:** Questo controlla come il modulo gestisce le funzionalità quando viene selezionata una combinazione.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su "Aggiungi":* Le funzionalità specifiche della combinazione verranno *aggiunte* alle funzionalità del prodotto principale. Quindi, vedrai sia le funzionalità generali del prodotto che le funzionalità uniche della combinazione.
    -   *Quando impostato su "Sostituisci":* Le funzionalità specifiche della combinazione *sostituiranno* le funzionalità del prodotto principale. Verranno mostrate solo le funzionalità pertinenti alla combinazione selezionata.
-   **Valore consigliato:** **Sostituisci** per la maggior parte dei casi, poiché fornisce le informazioni più precise. Scegli "Aggiungi" se hai funzionalità generali che si applicano a tutte le combinazioni, più quelle specifiche.
-   **Scenario / esempio del commerciante:**
    -   *Sostituisci:* Per un laptop, potresti voler che "Processore: i7", "RAM: 16GB" sostituiscano completamente "Processore: i5", "RAM: 8GB" quando un cliente seleziona la combinazione i7/16GB.
    -   *Aggiungi:* Per una maglietta, potresti voler sempre mostrare "Marca: MyBrand" (funzionalità generale), ma poi *aggiungere* "Materiale: Cotone Biologico" quando viene scelta una combinazione specifica.

#### **Attiva le descrizioni per le combinazioni**

-   **Cosa fa questa impostazione:** Questo abilita o disabilita la possibilità di assegnare descrizioni uniche a ogni combinazione di prodotto.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* Un nuovo campo apparirà nelle tue pagine di modifica del prodotto (sotto la scheda "Moduli") che ti consentirà di inserire una descrizione specifica per ogni combinazione. Quando i clienti selezionano una combinazione, questa descrizione sostituirà dinamicamente la descrizione del prodotto principale.
    -   *Quando disabilitato:* Il campo di descrizione della combinazione non apparirà e il front office mostrerà sempre la descrizione del prodotto principale.
-   **Valore consigliato:** **Abilitato** (se hai bisogno di descrizioni specifiche della combinazione).
-   **Scenario / esempio del commerciante:** Vendi gioielli personalizzati. Un prodotto "Anello d'argento" potrebbe avere una combinazione "Incisione: Sì". Potresti usare una descrizione della combinazione per spiegare il processo di incisione e i limiti di caratteri, il che non è rilevante per la combinazione "Incisione: No".

#### **Descrizione della classe CSS / ID oggetto**

-   **Cosa fa questa impostazione:** Simile alla "Classe CSS della scheda tecnica", questo indica al modulo quale elemento HTML nella pagina del tuo prodotto contiene la descrizione del prodotto principale che dovrebbe essere sostituita dalla descrizione specifica della combinazione.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato correttamente:* Il modulo troverà l'elemento specificato e aggiornerà dinamicamente il suo contenuto con la descrizione della combinazione.
    -   *Quando impostato in modo errato o lasciato vuoto:* La descrizione della combinazione potrebbe non apparire, o potrebbe apparire in un luogo inaspettato.
-   **Valore consigliato:** Questo dipende dal tuo tema. I selettori comuni sono `.product-description`, `#description_short` o `#product-description-short`. Dovrai ispezionare l'HTML della pagina del tuo prodotto.
-   **Scenario / esempio del commerciante:** Il tuo tema utilizza un `div` con l'ID `product-description-full` per la descrizione principale. Inseriresti `#product-description-full` qui.

#### **Attiva il meta titolo per le combinazioni**

-   **Cosa fa questa impostazione:** Questo abilita o disabilita la possibilità di impostare un meta titolo unico per ogni combinazione di prodotto. Questo meta titolo è ciò che appare nella scheda del browser ed è utilizzato dai motori di ricerca.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* Un nuovo campo apparirà nelle tue pagine di modifica del prodotto (sotto la scheda "Moduli") che ti consentirà di inserire un meta titolo specifico per ogni combinazione. Quando un cliente seleziona una combinazione, il titolo della scheda del browser si aggiornerà dinamicamente.
    -   *Quando disabilitato:* Il campo del meta titolo della combinazione non apparirà e la scheda del browser mostrerà sempre il meta titolo del prodotto principale.
-   **Valore consigliato:** **Abilitato** (se desideri migliorare la SEO per combinazioni specifiche o fornire titoli di schede del browser più chiari).
-   **Scenario / esempio del commerciante:** Per un prodotto "Smartphone", potresti avere una combinazione "Colore: Blu, Archiviazione: 128GB". Potresti impostare il suo meta titolo su "Smartphone Blu 128GB - [Nome del tuo negozio]" per una migliore visibilità sui motori di ricerca.

#### **Modalità titolo predefinita**

-   **Cosa fa questa impostazione:** Questo definisce come viene costruito il meta titolo della combinazione se non ne imposti uno esplicitamente per una combinazione, o se desideri combinare il titolo del prodotto con gli attributi della combinazione.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su "Nome prodotto + nome combinazione":* Il meta titolo sarà il nome del prodotto principale seguito dai nomi degli attributi della combinazione selezionata (ad esempio, "T-Shirt - Rosso, Grande").
    -   *Quando impostato su "Nome combinazione + nome prodotto":* Il meta titolo sarà i nomi degli attributi della combinazione selezionata seguiti dal nome del prodotto principale (ad esempio, "Rosso, Grande - T-Shirt").
    -   *Quando impostato su "Nome combinazione":* Verranno utilizzati solo i nomi degli attributi della combinazione (ad esempio, "Rosso, Grande").
    -   *Quando impostato su "Nome prodotto":* Il meta titolo sarà sempre il nome del prodotto principale, ignorando le combinazioni.
-   **Valore consigliato:** **"Nome prodotto + nome combinazione"** o **"Nome combinazione + nome prodotto"** per un buon equilibrio tra identità del prodotto e specificità della combinazione.
-   **Scenario / esempio del commerciante:** Vendi scarpe. Se un cliente seleziona "Taglia 10, Colore Nero" e viene scelto "Nome prodotto + nome combinazione", il titolo diventa "Scarpe da corsa - Taglia 10, Nero".

#### **Separatore del titolo**

-   **Cosa fa questa impostazione:** Questo ti consente di definire il carattere o la stringa utilizzati per separare le diverse parti del meta titolo generato dinamicamente (ad esempio, tra il nome del prodotto e il nome della combinazione).
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su "-":* Il titolo potrebbe apparire come "Nome Prodotto - Combinazione".
    -   *Quando impostato su "|":* Il titolo potrebbe apparire come "Nome Prodotto | Combinazione".
    -   *Quando lasciato vuoto:* Le parti del titolo potrebbero unirsi senza un separatore chiaro.
-   **Valore consigliato:** **-** (trattino) o **|** (barra verticale) sono separatori comuni e chiari.
-   **Scenario / esempio del commerciante:** Se la tua modalità titolo predefinita è "Nome prodotto + nome combinazione" e il separatore è impostato su "|", un titolo potrebbe diventare "La mia fantastica T-Shirt | Rosso, Grande".

### 2.2 Schermate di amministrazione dedicate e viste del controller

Questo modulo non crea schermate di amministrazione di alto livello dedicate. Si integra invece direttamente nella **Pagina di modifica del prodotto** esistente nel tuo Back Office di PrestaShop.

-   **Nome schermata e posizione del menu:**

    -   Naviga su **Catalogo > Prodotti**.
    -   Modifica un prodotto esistente o creane uno nuovo.
    -   All'interno della pagina di modifica del prodotto, fai clic sulla scheda **"Moduli"**.
    -   Troverai una nuova sezione intitolata **"Funzionalità delle combinazioni di prodotto"** (o simile, a seconda della versione/traduzioni del modulo).
-   **Azioni e impostazioni disponibili:**

    -   All'interno di questa sezione, vedrai un elenco di tutte le combinazioni configurate per il prodotto corrente.
    -   Per ogni combinazione, avrai campi per:
        -   **Assegna funzionalità:** Puoi selezionare funzionalità esistenti e i loro valori, o persino creare nuovi valori di funzionalità, specificamente per quella combinazione. Il modulo supporta multi-funzionalità, il che significa che una combinazione può avere diversi valori per la stessa funzionalità (ad esempio, "Materiale: Cotone, Materiale: Spandex").
        -   **Inserisci descrizione combinazione:** Sarà disponibile un editor di testo ricco (come l'editor di descrizione standard di PrestaShop) per inserire una descrizione unica per quella combinazione.
        -   **Inserisci meta titolo combinazione:** Un campo di testo per inserire un meta titolo unico per quella combinazione.
    -   **Salvataggio delle modifiche:** Ricorda di fare clic sul pulsante "Salva" principale per il prodotto per applicare tutte le modifiche specifiche della combinazione.
-   **Effetto delle modifiche:**

    -   Qualsiasi funzionalità, descrizione o meta titolo impostato qui verrà archiviato nel database e visualizzato dinamicamente nella pagina del prodotto del front office quando la combinazione corrispondente viene selezionata da un cliente.
    -   Se elimini una combinazione, anche le sue funzionalità, descrizioni e meta titoli associati verranno rimossi.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

    1.  Innanzitutto, crea il tuo prodotto e le sue combinazioni come al solito in PrestaShop (sotto la scheda "Combinazioni").
    2.  Una volta create le combinazioni, vai alla scheda **"Moduli"** nella pagina di modifica del prodotto.
    3.  Per ogni combinazione, assegna attentamente le funzionalità pertinenti, scrivi una descrizione specifica e imposta un meta titolo ottimizzato.
    4.  Salva il prodotto.
    5.  Testa sempre nel front office per assicurarti che le funzionalità, le descrizioni e i titoli si aggiornino correttamente quando vengono selezionate le combinazioni.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Attiva le funzionalità per le combinazioni | Abilitato | Interruttore principale per le funzionalità delle combinazioni. |
| Configurazione modulo | Classe CSS della scheda tecnica | `.product-features` (dipendente dal tema) | Selettore CSS per dove vengono visualizzate le funzionalità della combinazione. |
| Configurazione modulo | Flusso di lavoro | Sostituisci | Come le funzionalità della combinazione interagiscono con le funzionalità del prodotto principale (aggiungi o sostituisci). |
| Configurazione modulo | Attiva le descrizioni per le combinazioni | Abilitato | Interruttore principale per le descrizioni delle combinazioni. |
| Configurazione modulo | Descrizione della classe CSS / ID oggetto | `#product-description-short` (dipendente dal tema) | Selettore CSS per dove vengono visualizzate le descrizioni delle combinazioni. |
| Configurazione modulo | Attiva il meta titolo per le combinazioni | Abilitato | Interruttore principale per i meta titoli delle combinazioni. |
| Configurazione modulo | Modalità titolo predefinita | Nome prodotto + nome combinazione | Come vengono generati i meta titoli se non impostati esplicitamente. |
| Configurazione modulo | Separatore del titolo | `-` | Carattere utilizzato per separare le parti del meta titolo. |
| Pagina di modifica prodotto > Scheda Moduli | Assegna funzionalità per combinazione | N/A | Assegna funzionalità e valori unici a ogni combinazione. |
| Pagina di modifica prodotto > Scheda Moduli | Descrizione combinazione | N/A | Inserisci una descrizione unica in formato rich text per ogni combinazione. |
| Pagina di modifica prodotto > Scheda Moduli | Meta titolo combinazione | N/A | Inserisci un meta titolo unico per ogni combinazione. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Le mie funzionalità/descrizioni delle combinazioni non vengono visualizzate nella pagina del prodotto.**
R:

1.  **Controlla la configurazione del modulo:** Assicurati che "Attiva le funzionalità per le combinazioni" e/o "Attiva le descrizioni per le combinazioni" siano abilitate nella configurazione del modulo.
2.  **Verifica i selettori CSS:** Le impostazioni "Classe CSS della scheda tecnica" e "Descrizione della classe CSS / ID oggetto" sono cruciali. Devono corrispondere esattamente alla classe CSS o all'ID degli elementi nel tuo tema in cui vengono visualizzate le funzionalità/descrizione. Utilizza gli strumenti per sviluppatori del tuo browser (F12) per ispezionare la pagina del tuo prodotto e trovare i selettori corretti. In caso di dubbi, consulta lo sviluppatore del tuo tema.
3.  **Svuota la cache di PrestaShop:** Vai su **Parametri avanzati > Prestazioni** e fai clic su "Svuota la cache". A volte, il vecchio contenuto memorizzato nella cache impedisce la visualizzazione del nuovo output del modulo.
4.  **Controlla le impostazioni del prodotto:** Assicurati di aver effettivamente assegnato funzionalità/descrizioni alle combinazioni specifiche nella pagina di modifica del prodotto sotto la scheda "Moduli".

**D: Le funzionalità/descrizioni delle combinazioni appaiono, ma sembrano senza stile o fuori posto.**
R: Questo è solitamente un conflitto CSS con il tuo tema.

1.  **Ispeziona con gli strumenti del browser:** Usa F12 per vedere quali regole CSS vengono applicate all'output del modulo.
2.  **Regola la classe CSS:** Se l'output del modulo è racchiuso in un `div` generico, potrebbe essere necessario regolare la "Classe CSS della scheda tecnica" o "Descrizione della classe CSS / ID oggetto" a un contenitore più specifico che il tuo tema già stilizza.
3.  **CSS personalizzato:** Potrebbe essere necessario aggiungere CSS personalizzato al foglio di stile del tuo tema (o tramite un modulo CSS personalizzato) per stilizzare le funzionalità/descrizioni delle combinazioni in modo che corrispondano all'aspetto del tuo tema.

**D: I meta titoli delle mie combinazioni non cambiano nella scheda del browser.**
R:

1.  **Abilita l'impostazione:** Assicurati che "Attiva il meta titolo per le combinazioni" sia abilitato nella configurazione del modulo.
2.  **Imposta i titoli:** Assicurati di aver inserito meta titoli specifici per le tue combinazioni nella pagina di modifica del prodotto.
3.  **Comportamento del browser:** Alcuni browser potrebbero non aggiornare immediatamente il titolo della scheda per le schede già aperte. Prova ad aprire la pagina del prodotto in una nuova scheda o a svuotare la cache del browser.
4.  **Implicazioni SEO:** Sebbene il modulo aggiorni il titolo lato client, affinché i motori di ricerca possano rilevare questi titoli specifici della combinazione, devono essere in grado di eseguire la scansione e indicizzare il contenuto generato dinamicamente. Assicurati che il tuo sito sia scansionabile e considera se questi titoli dinamici sono veramente vantaggiosi per la tua strategia SEO rispetto ai titoli di prodotto statici.

**D: Posso usare questo modulo con negozi multi-lingua?**
R: Sì, il modulo supporta completamente il multi-lingua. Quando modifichi le funzionalità, le descrizioni o i meta titoli delle combinazioni nella pagina del prodotto, vedrai il selettore di lingua standard di PrestaShop, che ti consentirà di inserire contenuti per ogni lingua.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Funzionalità delle combinazioni di prodotto" (`combfeat`) estende la gestione dei prodotti di base di PrestaShop iniettando campi e logica personalizzati nella pagina di modifica del prodotto del Back Office e aggiornando dinamicamente il contenuto del Front Office in base alle combinazioni di prodotto selezionate. Sfrutta il sistema di hook di PrestaShop per integrarsi senza problemi senza modificare i file di base. Il modulo opera principalmente tramite JavaScript sul front-end per gli aggiornamenti dinamici e PHP sul back-end per la configurazione e la gestione dei dati. Non introduce nuove tabelle di database ma memorizza i suoi dati nelle strutture PrestaShop esistenti (probabilmente `ps_product_attribute_feature` per le funzionalità e `ps_product_attribute_lang` per descrizioni/titoli, o `ps_configuration` per le impostazioni del modulo).

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller Front-Office o Back-Office Admin dedicati. La sua logica per la visualizzazione e il salvataggio dei dati delle combinazioni è integrata direttamente nel file principale del modulo `combfeat.php` e tramite JavaScript.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non definisce classi personalizzate nella directory `classes/`. La sua logica principale è contenuta nel file principale `combfeat.php`, interagendo direttamente con gli `ObjectModel` `Product` e `Combination` (ProductAttribute) di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`combfeat/views/js/acplt.js`**

    -   **Ambito:** Probabilmente Back-office (pagina prodotto admin).
    -   **Responsabilità:** Questo script sembra essere una libreria di completamento automatico personalizzata o un componente utilizzato per selezionare funzionalità e i loro valori per le combinazioni. Gestirebbe le richieste AJAX per recuperare le funzionalità e i valori disponibili e gestirebbe l'interfaccia utente per aggiungerli/rimuoverli da una combinazione.
    -   **Interazioni chiave:** Listener di eventi per i campi di input, chiamate AJAX a un hook del modulo o a un controller admin per i dati, manipolazione del DOM per visualizzare suggerimenti e elementi selezionati.
-   **`combfeat/views/js/admin-combfeat.js`**

    -   **Ambito:** Back-office (pagina prodotto admin, scheda "Moduli").
    -   **Responsabilità:** Questo è lo script principale per la funzionalità del modulo all'interno della pagina di modifica del prodotto del Back Office di PrestaShop. Inizializza i campi delle funzionalità, della descrizione e del meta titolo della combinazione. Probabilmente ascolta le modifiche nella selezione della combinazione (se presenti) e gestisce la visualizzazione e il salvataggio dei dati per ogni combinazione.
    -   **Interazioni chiave:** Manipolazione del DOM per iniettare campi personalizzati, listener di eventi per le modifiche degli input, potenzialmente chiamate AJAX per salvare dati specifici della combinazione.
-   **`combfeat/views/js/combfeat-append.js`**

    -   **Ambito:** Front-office (pagina prodotto).
    -   **Responsabilità:** Questo script è specifico per l'opzione del flusso di lavoro "Aggiungi". Quando viene selezionata una combinazione, recupera dinamicamente e *aggiunge* le funzionalità specifiche della combinazione alle funzionalità del prodotto esistenti sul front-end.
    -   **Interazioni chiave:** Ascolta gli eventi `updateProduct` o simili (attivati dalla selezione della combinazione), chiamate AJAX per recuperare i dati della combinazione, manipolazione del DOM per aggiungere funzionalità all'elemento specificato da `combfeat_ds`.
-   **`combfeat/views/js/combfeat-title.js`**

    -   **Ambito:** Front-office (pagina prodotto).
    -   **Responsabilità:** Questo script gestisce l'aggiornamento dinamico del meta titolo del browser in base alla combinazione di prodotto selezionata.
    -   **Interazioni chiave:** Ascolta gli eventi `updateProduct` o simili, recupera il meta titolo della combinazione (personalizzato o generato in base alle impostazioni del modulo) e aggiorna `document.title`.
-   **`combfeat/views/js/combfeat.js`**

    -   **Ambito:** Front-office (pagina prodotto).
    -   **Responsabilità:** Questo è lo script principale del front-office per il modulo. Orchesta la visualizzazione dinamica delle funzionalità e delle descrizioni specifiche della combinazione. Probabilmente ascolta le modifiche nelle combinazioni di prodotto (ad esempio, la selezione degli attributi) e attiva gli aggiornamenti agli elementi DOM pertinenti. Questo script gestirebbe il flusso di lavoro "Sostituisci" per le funzionalità e l'aggiornamento della descrizione.
    -   **Interazioni chiave:** Ascolta gli eventi `updateProduct` o simili (ad esempio, `prestashop.on('updatedProduct', ...) `), chiamate AJAX per recuperare i dati della combinazione, manipolazione del DOM per aggiornare gli elementi specificati da `combfeat_ds` e `combfeat_description`.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`combfeat/views/css/combfeat.css`**
    -   **Ambito:** Sia Front-office che Back-office.
    -   **Responsabilità:** Fornisce uno stile di base per gli elementi iniettati dal modulo. Questo potrebbe includere lo stile per i campi di input delle funzionalità/descrizioni delle combinazioni nel Back Office, o per i blocchi di funzionalità/descrizioni aggiornati dinamicamente nel Front Office.
    -   **Selettori di classe CSS chiave:** Probabilmente si rivolge a classi utilizzate dai template e da JavaScript del modulo, come `.combfeat-feature-list`, `.combfeat-description-wrapper`, o stili specifici per il componente di completamento automatico. Gli sviluppatori potrebbero doverli sovrascrivere nel `custom.css` o `theme.css` del loro tema per una perfetta integrazione.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **`combfeat/views/templates/admin/combfeat.tpl`**

    -   **Ambito:** Template admin.
    -   **Responsabilità:** Questo template renderizza la sezione personalizzata all'interno della scheda "Moduli" nella pagina di modifica del prodotto nel Back Office. Visualizza l'interfaccia per la gestione delle funzionalità, delle descrizioni e dei meta titoli specifici della combinazione. Probabilmente itera attraverso tutte le combinazioni di prodotto e fornisce campi di input per ciascuna.
    -   **Elementi chiave:** Cicli per le combinazioni, campi di input per la selezione delle funzionalità (possibilmente utilizzando il componente `acplt.js`), editor di testo ricco per le descrizioni, input di testo per i meta titoli.
-   **`combfeat/views/templates/hook/product-details.tpl`**

    -   **Ambito:** Template hook del Front-office.
    -   **Responsabilità:** Questo template è probabilmente agganciato a `displayProductAdditionalInfo` o hook simili per renderizzare le funzionalità e/o la descrizione specifiche della combinazione nella pagina del prodotto del front office. Fornisce la struttura HTML che `combfeat.js` e `combfeat-append.js` popoleranno e aggiorneranno dinamicamente.
    -   **Elementi chiave:** Segnaposto (ad esempio, `div` vuoti con ID o classi specifici) dove le funzionalità e le descrizioni della combinazione verranno iniettate da JavaScript.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non crea nuove tabelle personalizzate. Probabilmente memorizza le funzionalità specifiche della combinazione estendendo la relazione `ps_product_attribute_feature` o simile, e le descrizioni/meta titoli della combinazione in `ps_product_attribute_lang` o una struttura simile, associandoli a `id_product_attribute` e `id_lang`.
    -   Le impostazioni di configurazione del modulo (`combfeat_ds`, `combfeat_description`, ecc.) sono memorizzate nella tabella `ps_configuration`.
-   **Tabella degli hook registrati**:

| Nome dell'hook | Ambito | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- | --- |
| `displayHeader` | Front-office | Nella sezione `<head>` di tutte le pagine del front-office. | Registra le risorse CSS e JS del front-office (`combfeat.css`, `combfeat.js`, `combfeat-append.js`, `combfeat-title.js`). |
| `DisplayHeader` | Front-office | Alias per `displayHeader`. | Uguale a `displayHeader`. |
| `displayProductAdditionalInfo` | Front-office | Nella pagina del prodotto, tipicamente sotto le informazioni principali del prodotto. | Renderizza il template `product-details.tpl`, fornendo un segnaposto per le funzionalità/descrizioni delle combinazioni. |
| `ActionAdminControllerSetMedia` | Back-office | Quando un controller admin viene caricato e le sue risorse multimediali sono impostate. | Registra le risorse CSS e JS del back-office (`combfeat.css`, `acplt.js`, `admin-combfeat.js`) per la pagina di modifica del prodotto. |
| `ActionProductUpdate` | Back-office | Dopo l'aggiornamento di un prodotto (incluse le combinazioni). | Potenzialmente utilizzato per salvare o sincronizzare i dati specifici della combinazione quando il modulo del prodotto viene inviato. |
| `actionProductUpdate` | Back-office | Alias per `ActionProductUpdate`. | Uguale a `ActionProductUpdate`. |
| `displayAdminProductsExtra` | Back-office | Nella pagina di modifica del prodotto, tipicamente come nuova scheda o sezione. | Renderizza il template `admin/combfeat.tpl`, creando la sezione "Funzionalità delle combinazioni di prodotto" sotto la scheda "Moduli". |
| `DisplayAdminProductsExtra` | Back-office | Alias per `displayAdminProductsExtra`. | Uguale a `displayAdminProductsExtra`. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Funzionalità delle combinazioni di prodotto", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e all'integrazione del modulo.
