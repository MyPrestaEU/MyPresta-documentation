---
title: "Products Notepad - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Products Notepad di MyPresta.eu."
sidebar:
  label: "Products Notepad - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Products Notepad su MyPresta.eu](https://mypresta.eu/modules/front-office-features/products-notepad.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/products-notepad/)
>
> ---


# Products Notepad

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per il funzionamento generale di PrestaShop. Non sono necessarie estensioni aggiuntive specifiche per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo "Products Notepad" in Gestione moduli. Questo ti porterà alla schermata di configurazione principale.

#### Impostazioni generali

-   **Cosa fa questa impostazione:** Questa sezione controlla il comportamento principale e la visualizzazione del modulo Products Notepad sul tuo negozio.

    -   **Ricorda prodotti nel blocco note:**

        -   **Cosa fa questa impostazione:** Determina se i prodotti che un cliente aggiunge al suo blocco note vengono ricordati tra diverse sessioni di navigazione o se il blocco note viene cancellato quando chiudono il browser.
        -   **Effetto della modifica di questa impostazione:**
            -   *Se abilitato (SÌ):* I prodotti aggiunti al blocco note persisteranno anche se il cliente lascia il tuo sito e torna più tardi (ad esempio, il giorno dopo). Questo utilizza i cookie del browser per memorizzare il contenuto del blocco note.
            -   *Se disabilitato (NO):* Il blocco note verrà cancellato quando il cliente chiude il browser o cancella i cookie. Ogni nuova sessione inizierà con un blocco note vuoto.
        -   **Valore consigliato:** **SÌ**. Questo offre un'esperienza cliente molto migliore, poiché consente ai clienti di costruire un elenco nel tempo senza perdere i loro progressi.
        -   **Scenario / esempio per il commerciante:** Un cliente aggiunge diversi articoli al suo blocco note lunedì. Se "Ricorda prodotti" è SÌ, può tornare mercoledì e trovare la sua lista intatta. Se NO, la lista sarebbe vuota.
    -   **Limita il numero di prodotti nel blocco note:**

        -   **Cosa fa questa impostazione:** Consente di impostare un numero massimo di prodotti che un cliente può salvare nel suo blocco note.
        -   **Effetto della modifica di questa impostazione:**
            -   *Se abilitato (SÌ):* Il blocco note consentirà solo un numero specificato di prodotti. Una volta raggiunto il limite, i clienti non potranno aggiungere altri prodotti finché non ne rimuovono quelli esistenti.
            -   *Se disabilitato (NO):* I clienti possono aggiungere un numero illimitato di prodotti al loro blocco note.
        -   **Valore consigliato:** **NO** (a meno che tu non abbia un motivo specifico per limitarlo, come problemi di prestazioni con elenchi estremamente lunghi). Consentire un numero illimitato di articoli offre ai clienti la massima flessibilità.
        -   **Scenario / esempio per il commerciante:** Se abiliti questa opzione e imposti il limite a 10, un cliente che tenta di aggiungere un 11° prodotto riceverà un messaggio che indica che il blocco note è pieno.
    -   **Valore limite:** (Appare solo se "Limita il numero di prodotti nel blocco note" è impostato su SÌ)

        -   **Cosa fa questa impostazione:** Specifica il numero massimo esatto di prodotti consentiti nel blocco note.
        -   **Effetto della modifica di questa impostazione:** Imposta il limite numerico per il blocco note.
        -   **Valore consigliato:** Se scegli di limitare, un numero ragionevole come **20-50** è spesso sufficiente, bilanciando la flessibilità del cliente con le potenziali prestazioni.
        -   **Scenario / esempio per il commerciante:** Se "Limita il numero di prodotti" è SÌ e "Valore limite" è 25, i clienti possono salvare fino a 25 prodotti.

#### Impostazioni di visualizzazione

-   **Cosa fa questa impostazione:** Questa sezione controlla dove appare il blocco Products Notepad nel front office del tuo negozio.

    -   **Visualizza nella colonna sinistra:**

        -   **Cosa fa questa impostazione:** Controlla se il blocco di riepilogo del blocco note viene mostrato nella colonna sinistra del tuo negozio.
        -   **Effetto della modifica di questa impostazione:**
            -   *Se abilitato (SÌ):* Il blocco note apparirà nella colonna sinistra nelle pagine che hanno una colonna sinistra (ad esempio, pagine di categoria, pagine di prodotto, pagine CMS).
            -   *Se disabilitato (NO):* Il blocco note non verrà mostrato nella colonna sinistra.
        -   **Valore consigliato:** **SÌ** (o colonna destra), poiché le colonne sono un luogo comune per tali blocchi di utilità.
        -   **Scenario / esempio per il commerciante:** Un cliente che naviga in una pagina di categoria vedrà il riepilogo del suo blocco note nella barra laterale sinistra, rendendolo facilmente accessibile.
    -   **Visualizza nella colonna destra:**

        -   **Cosa fa questa impostazione:** Controlla se il blocco di riepilogo del blocco note viene mostrato nella colonna destra del tuo negozio.
        -   **Effetto della modifica di questa impostazione:**
            -   *Se abilitato (SÌ):* Il blocco note apparirà nella colonna destra nelle pagine che hanno una colonna destra.
            -   *Se disabilitato (NO):* Il blocco note non verrà mostrato nella colonna destra.
        -   **Valore consigliato:** **SÌ** (o colonna sinistra). Scegli uno o entrambi in base al layout del tuo tema e agli altri moduli che hai.
        -   **Scenario / esempio per il commerciante:** Se il tuo tema utilizza la colonna destra per le promozioni, potresti posizionare il blocco note lì per mantenere la colonna sinistra libera per la navigazione.
    -   **Visualizza nel piè di pagina:**

        -   **Cosa fa questa impostazione:** Controlla se il blocco di riepilogo del blocco note viene mostrato nella sezione del piè di pagina del tuo negozio.
        -   **Effetto della modifica di questa impostazione:**
            -   *Se abilitato (SÌ):* Il blocco note apparirà nella parte inferiore di ogni pagina, tipicamente come parte del contenuto generale del piè di pagina.
            -   *Se disabilitato (NO):* Il blocco note non verrà mostrato nel piè di pagina.
        -   **Valore consigliato:** **NO** (a meno che il tuo tema non abbia una sezione piè di pagina molto prominente per i blocchi di utilità). Le colonne sono generalmente più visibili per questo tipo di funzionalità.
        -   **Scenario / esempio per il commerciante:** Se il tuo piè di pagina è già affollato di link e informazioni legali, aggiungere il blocco note lì potrebbe renderlo meno evidente.
    -   **Visualizza nell'intestazione:**

        -   **Cosa fa questa impostazione:** Controlla se il blocco di riepilogo del blocco note viene mostrato nella sezione dell'intestazione del tuo negozio.
        -   **Effetto della modifica di questa impostazione:**
            -   *Se abilitato (SÌ):* Il blocco note apparirà nella parte superiore di ogni pagina, spesso vicino ai link del carrello o dell'account.
            -   *Se disabilitato (NO):* Il blocco note non verrà mostrato nell'intestazione.
        -   **Valore consigliato:** **NO** (a meno che il tuo tema non abbia ampio spazio e un design specifico per questo). Le intestazioni sono spesso riservate alla navigazione critica e al carrello.
        -   **Scenario / esempio per il commerciante:** Un'icona compatta nell'intestazione potrebbe funzionare, ma un blocco completo potrebbe ingombrare l'intestazione.
    -   **Visualizza nella pagina del prodotto:**

        -   **Cosa fa questa impostazione:** Controlla se il pulsante "Aggiungi al blocco note" e potenzialmente un piccolo riepilogo del blocco note vengono visualizzati direttamente sulle singole pagine dei prodotti.
        -   **Effetto della modifica di questa impostazione:**
            -   *Se abilitato (SÌ):* I clienti vedranno il pulsante "Aggiungi al blocco note" su ogni pagina del prodotto, rendendo facile salvare gli articoli durante la navigazione.
            -   *Se disabilitato (NO):* Il pulsante "Aggiungi al blocco note" non apparirà nelle pagine dei prodotti, rendendo la funzionalità meno accessibile.
        -   **Valore consigliato:** **SÌ**. Questa è una posizione cruciale affinché la funzionalità sia efficace.
        -   **Scenario / esempio per il commerciante:** Un cliente che visualizza un prodotto può aggiungerlo immediatamente al suo blocco note per un confronto successivo con altri prodotti.

#### Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Ricorda prodotti nel blocco note | SÌ | Mantiene gli elementi del blocco note salvati tra le sessioni per una migliore UX. |
| Configurazione modulo | Limita il numero di prodotti nel blocco note | NO | Consente prodotti illimitati nel blocco note, massimizzando la scelta del cliente. |
| Configurazione modulo | Valore limite | (N/A se il limite è NO) | Imposta il numero massimo di prodotti se la limitazione è abilitata. |
| Configurazione modulo | Visualizza nella colonna sinistra | SÌ | Mostra il riepilogo del blocco note nella barra laterale sinistra. |
| Configurazione modulo | Visualizza nella colonna destra | SÌ | Mostra il riepilogo del blocco note nella barra laterale destra. |
| Configurazione modulo | Visualizza nel piè di pagina | NO | Evita di ingombrare il piè di pagina, meno visibile. |
| Configurazione modulo | Visualizza nell'intestazione | NO | Evita di ingombrare l'intestazione, meno visibile. |
| Configurazione modulo | Visualizza nella pagina del prodotto | SÌ | Essenziale per i clienti per aggiungere facilmente prodotti al blocco note. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Il blocco note non viene visualizzato nel mio negozio. Cosa devo fare?**
R1: Innanzitutto, controlla la configurazione del modulo nel tuo Back Office (**Moduli > Gestione moduli > Products Notepad > Configura**). Assicurati che almeno un'opzione di visualizzazione (ad esempio, "Visualizza nella colonna sinistra" o "Visualizza nella pagina del prodotto") sia impostata su SÌ. Se non viene ancora visualizzato, prova a svuotare la cache di PrestaShop (**Parametri avanzati > Prestazioni > Svuota cache**). A volte, i conflitti di tema possono anche impedire la visualizzazione dei moduli; prova a passare temporaneamente al tema PrestaShop predefinito per escludere questa possibilità.

**D2: I prodotti non vengono ricordati nel blocco note dopo che un cliente chiude il browser.**
R2: Vai alla pagina di configurazione del modulo (**Moduli > Gestione moduli > Products Notepad > Configura**) e assicurati che l'impostazione "Ricorda prodotti nel blocco note" sia impostata su **SÌ**. Questa opzione utilizza i cookie del browser per memorizzare il contenuto del blocco note, quindi assicurati che i clienti non abbiano disabilitato i cookie nel loro browser.

**D3: Il pulsante "Aggiungi al blocco note" appare strano o non è stilizzato correttamente nelle mie pagine di prodotto.**
R3: Questo è spesso un conflitto CSS con il tuo tema personalizzato. Il modulo fornisce il proprio stile di base, ma gli stili del tuo tema potrebbero sovrascriverlo. Puoi:
1.  Contattare lo sviluppatore del tuo tema per assistenza.
2.  Utilizzare l'Editor di temi live di PrestaShop (se disponibile nella tua versione) o gli strumenti per sviluppatori del browser (F12) per ispezionare il pulsante e applicare override CSS personalizzati nel file `custom.css` del tuo tema.
3.  Contattare il supporto MyPresta.eu per assistenza.

**D4: I clienti possono condividere il loro blocco note con altri?**
R4: No, questo modulo è progettato per l'uso individuale del cliente e non include funzionalità di condivisione. È un aiuto personale per la navigazione, non una lista dei desideri collaborativa.

**D5: Il blocco note funzionerà con negozi multilingue?**
R5: Sì, il modulo è progettato per essere compatibile con le funzionalità multilingue di PrestaShop. Qualsiasi testo visualizzato dal modulo (come etichette dei pulsanti o titoli dei blocchi) può essere tradotto tramite l'interfaccia di traduzione di PrestaShop (**Internazionale > Traduzioni > Traduzioni dei moduli installati**).

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo Products Notepad è un modulo PrestaShop standard che segue un modello simile a MVC. Utilizza principalmente controller frontali per le interazioni AJAX e il rendering, e i template Smarty per la sua visualizzazione nel front-office. Si basa sui cookie del browser per la persistenza se configurato per ricordare i prodotti. La logica principale del modulo risiede in `notepad.php` e nei suoi controller frontali associati.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `controllers/front/ajaxload.php`
        -   **Nome classe e classe padre**: `NotepadAjaxloadModuleFrontController` che estende `ModuleFrontController`.
        -   **Responsabilità**: Questo controller gestisce tutte le richieste AJAX relative alla funzionalità del blocco note. È responsabile dell'aggiunta di prodotti al blocco note, della loro rimozione e del potenziale aggiornamento della visualizzazione del blocco note. Elabora i dati inviati tramite POST o GET e restituisce risposte JSON al JavaScript del front-end.
    -   `controllers/front/index.php`
        -   **Nome classe e classe padre**: `NotepadIndexModuleFrontController` che estende `ModuleFrontController`.
        -   **Responsabilità**: Questo controller funge probabilmente da fallback o da pagina dedicata per il blocco note se è implementata una visualizzazione a pagina intera. Data la natura AJAX primaria del modulo, questo potrebbe essere un punto di ingresso meno frequentemente utilizzato, che potrebbe reindirizzare o renderizzare una visualizzazione completa del blocco note.
-   **Controller Amministrazione Back-Office**: Nessuno. Tutta la configurazione è gestita tramite il metodo `getContent()` del modulo principale.

### 4.3 Classi e modelli principali (`classes/`)

Nessuna classe `ObjectModel` personalizzata è definita in questo modulo. I dati del prodotto sono probabilmente memorizzati direttamente nei cookie del browser o nelle variabili di sessione, recuperati ed elaborati dalla classe principale del modulo e dai controller frontali.

### 4.4 Risorse JavaScript (`views/js/`)

-   `admin.js`
    -   **Ambito**: Back-office.
    -   **Descrizione**: Questo script gestisce probabilmente le interazioni nella pagina di configurazione del modulo nel Back Office di PrestaShop. Potrebbe gestire la visibilità delle impostazioni (ad esempio, `notepad_limit_value` in base a `notepad_limit`), l'invio di moduli o la convalida.
-   `jscolor.js`
    -   **Ambito**: Back-office (probabilmente).
    -   **Descrizione**: Una libreria JavaScript di terze parti per i selettori di colore. Se il modulo avesse opzioni di personalizzazione del colore per la visualizzazione del blocco note, questo script fornirebbe l'interfaccia utente per la selezione dei colori nel pannello di amministrazione. (In base all'inventario, è presente ma potrebbe essere un residuo o per uso futuro se non sono attualmente esposte impostazioni di colore).
-   `lib/searchTool/views/js/autocomplete.js`
    -   **Ambito**: Front-office (potenzialmente Back-office se utilizzato per la selezione del prodotto).
    -   **Descrizione**: Questo script fornisce la funzionalità di completamento automatico, probabilmente per la ricerca di prodotti. Se il blocco note avesse una funzione per aggiungere prodotti tramite ricerca, o se facesse parte di una libreria più ampia di "strumenti di ricerca" inclusa con il modulo, questo gestirebbe le chiamate AJAX e la visualizzazione dei suggerimenti di ricerca.
-   `notepad.js`
    -   **Ambito**: Front-office.
    -   **Descrizione**: Questo è il JavaScript principale del front-office per la funzionalità del blocco note.
        -   **Listener di eventi**: Collega gli eventi di clic ai pulsanti "Aggiungi al blocco note" (ad esempio, nelle pagine dei prodotti, negli elenchi di prodotti), ai link/pulsanti "Rimuovi dal blocco note" all'interno del blocco note e potenzialmente all'intestazione del blocco note stesso per attivare la sua visibilità o navigare a una visualizzazione completa.
        -   **Chiamate AJAX**: Effettua richieste asincrone a `controllers/front/ajaxload.php` per aggiungere, rimuovere o recuperare i contenuti del blocco note.
        -   **Manipolazione DOM**: Aggiorna il blocco di visualizzazione del blocco note (ad esempio, conteggio dei prodotti, elenco dei prodotti), mostra messaggi di successo/errore e renderizza dinamicamente le voci dei prodotti all'interno del blocco note.
        -   **Gestione dei cookie**: Interagisce con i cookie del browser per memorizzare e recuperare gli ID dei prodotti del blocco note se l'opzione "Ricorda prodotti" è abilitata.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `css/admincss.css`
    -   **Ambito**: Stile del modulo di amministrazione del Back-office.
    -   **Descrizione**: Stili per la pagina di configurazione del modulo nel Back Office di PrestaShop, garantendo un aspetto coerente con il tema di amministrazione di PrestaShop.
-   `css/css.css`
    -   **Ambito**: Stile del cliente del Front-office.
    -   **Descrizione**: Contiene gli stili principali per il blocco di visualizzazione del blocco note, il pulsante "Aggiungi al blocco note" e qualsiasi elemento associato nel negozio.
    -   **Selettori di classi CSS chiave**: Gli sviluppatori possono ispezionare l'HTML generato per classi come `.notepad-block`, `.add-to-notepad`, `.notepad-product-item` per sovrascrivere gli stili nel file `custom.css` o `theme.css` del loro tema.
-   `lib/searchTool/views/css/autocomplete.css`
    -   **Ambito**: Front-office (o Back-office se lo strumento di ricerca è utilizzato lì).
    -   **Descrizione**: Stili per il menu a discesa dei risultati di ricerca con completamento automatico, se lo script `autocomplete.js` è attivamente utilizzato per una funzione di ricerca prodotti all'interno del modulo.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**:
    -   `extraleft.tpl`
        -   **Hook**: Probabilmente `displayLeftColumn` o simile.
        -   **Scopo**: Renderizza il blocco di riepilogo principale del blocco note che appare nella colonna sinistra. Questo mostra tipicamente un titolo, il numero di articoli e un breve elenco o un link al blocco note completo.
    -   `notepad.tpl`
        -   **Hook**: Questo potrebbe essere un template generale incluso da altri template o direttamente agganciato a `displayRightColumn`, `displayFooter` o `displayHeader` a seconda della configurazione. Contiene probabilmente la struttura principale per il blocco note.
-   **Template di amministrazione (`views/templates/admin/`)**: Nessuno esplicitamente elencato, la configurazione è probabilmente gestita direttamente da `notepad.php` che renderizza gli elementi del modulo.
-   **Template Front-office (`views/templates/front/`)**:
    -   `views/addToCart.tpl`
        -   **Scopo**: Questo template viene renderizzato nelle pagine dei prodotti (e potenzialmente negli elenchi di prodotti) per visualizzare il pulsante "Aggiungi al blocco note". È probabilmente agganciato a `displayProductButtons` o `displayProductActions`.
    -   `views/selectedProducts.tpl`
        -   **Scopo**: Questo template viene utilizzato per visualizzare l'elenco dettagliato dei prodotti all'interno del blocco note, sia in un popup, in una pagina dedicata o all'interno del blocco di colonna espanso. Itera sui prodotti salvati nel blocco note e visualizza la loro immagine, nome, prezzo e un'opzione "rimuovi".
    -   `lib/searchTool/views/scripts.tpl`
        -   **Scopo**: Questo template include probabilmente il JavaScript e il CSS necessari per la libreria `searchTool`, come `autocomplete.js` e `autocomplete.css`, se il modulo utilizza una funzione di ricerca. Sarebbe agganciato a `displayHeader` o `displayFooter` per caricare queste risorse.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**: Il modulo non sembra creare tabelle SQL personalizzate. Gli ID dei prodotti e i dati correlati per il blocco note sono gestiti lato client, principalmente tramite cookie del browser o variabili di sessione. Le impostazioni di configurazione sono memorizzate in `ps_configuration` (ad esempio, `NOTEPAD_REMEMBER`, `NOTEPAD_LIMIT`, `NOTEPAD_LIMIT_VALUE`).
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Per caricare le risorse CSS e JS del modulo (ad esempio, `notepad.js`, `css.css`) e potenzialmente renderizzare un riepilogo compatto del blocco note se configurato. |
| `displayLeftColumn` | Nella barra laterale sinistra delle pagine che ne hanno una. | Per visualizzare il blocco di riepilogo principale del blocco note (`extraleft.tpl`). |
| `displayRightColumn` | Nella barra laterale destra delle pagine che ne hanno una. | Per visualizzare il blocco di riepilogo principale del blocco note (`notepad.tpl` o simile). |
| `displayFooter` | Nella sezione del piè di pagina di ogni pagina. | Per visualizzare il blocco di riepilogo del blocco note se configurato, o per caricare JS differito. |
| `displayProductButtons` / `displayProductActions` (o hook simile della pagina prodotto) | Nella pagina del prodotto, vicino al pulsante "Aggiungi al carrello". | Per renderizzare il pulsante "Aggiungi al blocco note" (`views/addToCart.tpl`). |
| `actionFrontControllerSetMedia` | Prima che il controller frontale renderizzi il suo output. | Per registrare i file CSS e JS del modulo per un caricamento ottimale. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo Products Notepad, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e alla compatibilità del modulo.
