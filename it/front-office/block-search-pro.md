---
title: "Block Search Pro - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Block Search Pro di MyPresta.eu."
sidebar:
  label: "Block Search Pro - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Block Search Pro su MyPresta.eu](https://mypresta.eu/modules/front-office-features/block-search-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/block-search-pro/)
>
> ---


# Block Search Pro

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server oltre a un ambiente di hosting PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Block Search Pro)

Questa è la schermata di configurazione principale dove controlli come il modulo Block Search Pro si comporta e appare sul tuo storefront.

#### 2.1.1 Impostazioni generali

**1. Abilita ricerca AJAX**

-   **Cosa fa questa impostazione:** Controlla se i risultati della ricerca appaiono istantaneamente mentre il cliente digita (AJAX) o se devono premere Invio/cliccare il pulsante di ricerca per vedere i risultati.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Mentre i clienti digitano nella barra di ricerca, apparirà un elenco a discesa di prodotti corrispondenti in tempo reale sotto il campo di ricerca. Questo fornisce un feedback immediato e velocizza il processo di ricerca.
    -   *Quando disabilitato (NO):* I clienti devono digitare la loro query di ricerca completa e poi premere Invio o cliccare il pulsante di ricerca per essere reindirizzati alla pagina dei risultati di ricerca.
-   **Valore consigliato:** SÌ. Questo migliora significativamente l'esperienza utente offrendo gratificazione istantanea e riducendo i passaggi per trovare un prodotto.
-   **Scenario/esempio per il commerciante:** Un cliente digita "vestito" e vede immediatamente apparire suggerimenti come "Vestito da festa rosso", "Vestito lungo estivo" e "Vestito da cocktail nero", permettendogli di cliccare direttamente su una pagina prodotto senza aspettare.

**2. Ricerca istantanea**

-   **Cosa fa questa impostazione:** Simile alla ricerca AJAX, si riferisce specificamente alla visualizzazione "istantanea" dei risultati di ricerca sulla pagina dei risultati di ricerca stessa, che si aggiorna man mano che l'utente affina la sua query. (Nota: in molte versioni moderne di PrestaShop, la "ricerca AJAX" spesso include il menu a discesa istantaneo, mentre la "Ricerca istantanea" potrebbe riferirsi al comportamento sulla pagina dei risultati di ricerca effettiva).
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Se un cliente si trova sulla pagina dei risultati di ricerca e modifica la sua query di ricerca nella barra di ricerca, i risultati su quella pagina si aggiorneranno istantaneamente senza un ricaricamento completo della pagina.
    -   *Quando disabilitato (NO):* Il cliente dovrebbe inviare nuovamente la query di ricerca modificata affinché la pagina dei risultati si aggiorni.
-   **Valore consigliato:** SÌ. Questo fornisce un'esperienza di ricerca più dinamica e reattiva.
-   **Scenario/esempio per il commerciante:** Un cliente cerca "scarpe", arriva sulla pagina dei risultati di ricerca, quindi digita "rosse" nella barra di ricerca su quella pagina. Con la ricerca istantanea, i risultati si filtrano immediatamente per mostrare solo scarpe rosse.

**3. Consenti di inviare la ricerca con input di parola chiave di ricerca vuoto**

-   **Cosa fa questa impostazione:** Determina se un cliente può cliccare il pulsante di ricerca o premere Invio senza digitare alcuna parola chiave.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Se un cliente clicca su cerca con un input vuoto, verrà indirizzato alla pagina generale dei risultati di ricerca, che potrebbe visualizzare tutti i prodotti o un messaggio predefinito a seconda del tuo tema. Questo può talvolta essere utilizzato per sfogliare tutti i prodotti.
    -   *Quando disabilitato (NO):* Il pulsante di ricerca sarà inattivo o visualizzerà un messaggio di errore se il campo di input è vuoto, costringendo il cliente a digitare una parola chiave prima di cercare.
-   **Valore consigliato:** NO. Generalmente, è meglio guidare i clienti a inserire una query per evitare confusione o pagine di risultati di ricerca vuote.
-   **Scenario/esempio per il commerciante:** Se un cliente clicca accidentalmente su cerca senza digitare, disabilitando questa opzione si evita che finisca su una pagina vuota potenzialmente confusa.

**4. Lunghezza minima della parola (in caratteri)**

-   **Cosa fa questa impostazione:** Imposta il numero minimo di caratteri che un cliente deve digitare prima che la funzione di ricerca (inclusa la ricerca AJAX/istantanea) inizi a cercare risultati.
-   **Effetto della modifica di questa impostazione:**
    -   *Impostato su 3:* I clienti devono digitare almeno tre caratteri (es. "ros") prima che appaiano suggerimenti di ricerca o che una ricerca possa essere inviata.
    -   *Impostato su 1:* Anche un singolo carattere (es. "a") attiverà la ricerca.
-   **Valore consigliato:** 3. Questo bilancia reattività e pertinenza. Un valore troppo basso (es. 1-2 caratteri) può generare troppi suggerimenti irrilevanti, mentre un valore troppo alto potrebbe frustrare gli utenti.
-   **Scenario/esempio per il commerciante:** Se impostato su 3, digitando "sc" non verranno mostrati risultati, ma digitando "sca" inizieranno a comparire suggerimenti per "scarpe", "sciarpe", ecc.

#### 2.1.2 Opzioni di filtro della ricerca

**5. Seleziona categorie**

-   **Cosa fa questa impostazione:** Ti consente di limitare la ricerca solo a specifiche categorie di prodotti. Il modulo restituirà solo risultati dalle categorie che selezioni qui.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando sono selezionate categorie specifiche:* La ricerca cercherà prodotti solo all'interno delle categorie scelte. I prodotti nelle categorie non selezionate non appariranno nei risultati di ricerca, anche se corrispondono alla parola chiave.
    -   *Quando non sono selezionate categorie:* La ricerca cercherà per impostazione predefinita in tutte le categorie del tuo negozio.
-   **Valore consigliato:** Seleziona le categorie se vuoi guidare i clienti a tipi di prodotti specifici, oppure lascia vuoto se vuoi una ricerca ampia.
-   **Scenario/esempio per il commerciante:** Se vendi sia abbigliamento che elettronica, ma vuoi che la barra di ricerca nell'intestazione trovi solo abbigliamento, selezioneresti qui solo le tue categorie di abbigliamento.

**6. Cerca nelle sottocategorie**

-   **Cosa fa questa impostazione:** Questa opzione funziona in combinazione con "Seleziona categorie". Determina se la ricerca deve includere anche i prodotti all'interno delle sottocategorie delle categorie padre selezionate.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Se selezioni "Elettronica" come categoria, la ricerca cercherà anche all'interno di "Laptop", "Smartphone" e qualsiasi altra sottocategoria di "Elettronica".
    -   *Quando disabilitato (NO):* La ricerca cercherà solo i prodotti direttamente assegnati alle categorie padre selezionate, ignorando le loro sottocategorie.
-   **Valore consigliato:** SÌ. La maggior parte dei commercianti desidera che le ricerche siano complete all'interno di un albero di categorie scelto.
-   **Scenario/esempio per il commerciante:** Se selezioni "Abbigliamento" e abiliti "Cerca nelle sottocategorie", una ricerca per "camicia" troverà camicie in "T-shirt da uomo", "Camicette da donna", ecc.

**7. Produttori**

-   **Cosa fa questa impostazione:** Ti consente di limitare la ricerca solo ai prodotti di specifici produttori.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando sono selezionati produttori specifici:* La ricerca restituirà solo prodotti realizzati dai produttori scelti. I prodotti di produttori non selezionati non appariranno.
    -   *Quando non sono selezionati produttori:* La ricerca cercherà per impostazione predefinita in tutti i produttori del tuo negozio.
-   **Valore consigliato:** Seleziona i produttori se vuoi offrire una ricerca specifica per marchio, oppure lascia vuoto per una ricerca generale.
-   **Scenario/esempio per il commerciante:** Se hai un blocco di ricerca dedicato per "Marchi Premium", potresti selezionare qui solo i produttori di fascia alta.

#### 2.1.3 Impostazioni di visualizzazione

**8. Dimensione del blocco di ricerca**

-   **Cosa fa questa impostazione:** Controlla la larghezza visiva del campo di input di ricerca in pixel.
-   **Effetto della modifica di questa impostazione:**
    -   *Impostato su 280px:* La barra di ricerca sarà larga 280 pixel.
    -   *Impostato su 100% (o lasciato vuoto per il rilevamento automatico):* La barra di ricerca si adatterà allo spazio disponibile, spesso riempiendo il suo contenitore.
-   **Valore consigliato:** Lascia vuoto per il rilevamento automatico o imposta una percentuale (es. 100%) per garantire la reattività. Se hai bisogno di una larghezza fissa per motivi di design, specifica un valore in pixel.
-   **Scenario/esempio per il commerciante:** Se il tuo tema ha un'intestazione molto stretta, potresti dover regolare questo valore per assicurarti che la barra di ricerca si adatti senza rompere il layout. Per la maggior parte dei temi moderni, lasciare che il tema gestisca la larghezza è la soluzione migliore.

#### 2.1.4 Altre impostazioni

**9. Impostazioni di aggiornamento live MyPresta.eu (mypresta\_updates, update\_, updatev\_)**

-   **Cosa fa questa impostazione:** Queste sono impostazioni interne relative al sistema di aggiornamento dei moduli di MyPresta.eu. Consentono al modulo di verificare e notificarti le nuove versioni.
-   **Effetto della modifica di questa impostazione:** Queste non sono configurabili dall'utente direttamente tramite l'interfaccia, ma sono gestite dal modulo stesso. Assicurarsi che il tuo negozio abbia accesso a Internet in uscita consente a questi controlli di funzionare.
-   **Valore consigliato:** Queste sono interne e non dovrebbero essere modificate manualmente.
-   **Scenario/esempio per il commerciante:** Riceverai una notifica nel tuo back office PrestaShop se è disponibile una nuova versione di Block Search Pro, assicurandoti di poter mantenere il tuo modulo aggiornato con le ultime funzionalità e correzioni di sicurezza.

**10. PS\_LANG\_DEFAULT, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG**

-   **Cosa fa questa impostazione:** Queste sono variabili di configurazione standard di PrestaShop relative alla lingua predefinita del tuo negozio e se i dipendenti possono cambiare la lingua dei moduli nel back office. Il modulo le utilizza per assicurarsi di essere visualizzato correttamente nella lingua attiva del back office.
-   **Effetto della modifica di questa impostazione:** Queste sono impostazioni globali di PrestaShop e non sono direttamente controllate da Block Search Pro. Il modulo le legge semplicemente per adattare la sua visualizzazione.
-   **Valore consigliato:** Gestito dalla tua configurazione generale di PrestaShop.
-   **Scenario/esempio per il commerciante:** Se il tuo back office è impostato su francese, le etichette di configurazione del modulo appariranno in francese (se le traduzioni sono disponibili).

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Abilita ricerca AJAX | SÌ | Mostra suggerimenti di prodotti istantanei mentre il cliente digita. |
| Configurazione modulo | Ricerca istantanea | SÌ | Aggiorna istantaneamente la pagina dei risultati di ricerca al cambio della query. |
| Configurazione modulo | Consenti di inviare la ricerca con input di parola chiave di ricerca vuoto | NO | Impedisce la ricerca con un campo di input vuoto. |
| Configurazione modulo | Lunghezza minima della parola (in caratteri) | 3 | Caratteri minimi richiesti per attivare la ricerca. |
| Configurazione modulo | Seleziona categorie | Lascia vuoto (cerca tutto) | Limita la ricerca alle categorie scelte. |
| Configurazione modulo | Cerca nelle sottocategorie | SÌ | Include le sottocategorie quando sono selezionate le categorie padre. |
| Configurazione modulo | Produttori | Lascia vuoto (cerca tutto) | Limita la ricerca ai produttori scelti. |
| Configurazione modulo | Dimensione del blocco di ricerca | Lascia vuoto (rilevamento automatico) | Larghezza visiva del campo di input di ricerca. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D1: I miei risultati di ricerca non mostrano prodotti che so esistere. Cosa c'è che non va?**
R1: Controlla le impostazioni "Seleziona categorie" e "Produttori" nella configurazione del modulo. Se hai limitato la ricerca a determinate categorie o produttori, i prodotti al di fuori di tali selezioni non appariranno. Inoltre, assicurati che i tuoi prodotti siano attivi e visibili nelle categorie selezionate.

**D2: La ricerca istantanea (AJAX) non funziona o i suggerimenti a discesa non appaiono.**
R2:
\* **Abilita ricerca AJAX:** Assicurati che "Abilita ricerca AJAX" sia impostato su SÌ nella configurazione del modulo.
\* **Lunghezza minima della parola:** Controlla "Lunghezza minima della parola". Se è impostata troppo alta, i suggerimenti non appariranno finché non vengono digitati abbastanza caratteri.
\* **Svuota cache:** Vai su **Parametri avanzati > Prestazioni** e svuota la cache di PrestaShop (cache Smarty, cache del filesystem).
\* **Conflitti con il tema:** A volte, temi personalizzati o altri moduli possono entrare in conflitto con la funzionalità AJAX. Disabilita temporaneamente altri moduli o passa al tema PrestaShop predefinito per diagnosticare.
\* **Errori JavaScript:** Apri la console per sviluppatori del tuo browser (F12) e controlla eventuali errori JavaScript. Se vedi errori, contatta il supporto MyPresta.eu.

**D3: Il blocco di ricerca ha un aspetto strano o non si adatta al mio tema.**
R3:
\* **Dimensione del blocco di ricerca:** Regola l'impostazione "Dimensione del blocco di ricerca" nella configurazione del modulo. Prova a lasciarla vuota per il rilevamento automatico o impostala su una percentuale (es. 100%).
\* **Conflitti CSS:** Il CSS del tuo tema potrebbe sovrascrivere gli stili del modulo. Questo di solito richiede a un webmaster di ispezionare il CSS.
\* **Posizionamento dell'hook:** Assicurati che il modulo sia agganciato in una posizione appropriata (es. `displayTop`) che abbia spazio sufficiente nel tuo tema. Puoi gestire le posizioni dei moduli sotto **Design > Posizioni**.

**D4: Come posso tradurre il testo del blocco di ricerca (es. "Cerca nel nostro catalogo")?**
R4:
\* Vai su **Internazionale > Traduzioni** nel tuo back office PrestaShop.
\* Seleziona "Traduzioni dei moduli installati", scegli il tuo tema e poi seleziona la tua lingua.
\* Trova il modulo "Block Search Pro" nell'elenco e potrai modificare le stringhe di testo lì.

**D5: Voglio posizionare il blocco di ricerca in una posizione diversa sul mio sito.**
R5:
\* Naviga su **Design > Posizioni** (o **Moduli > Posizioni** nelle versioni precedenti di PS).
\* Trova il modulo "Block Search Pro" nell'elenco dei moduli.
\* Puoi "trapiantare" (agganciare) il modulo a diversi hook disponibili come `displayHeader`, `displayTop`, `displayLeftColumn`, `displayRightColumn` o `displayNav`. Trascina e rilascia per cambiare l'ordine all'interno di un hook.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata del modulo Block Search Pro per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo Block Search Pro estende la funzionalità di ricerca principale di PrestaShop sovrascrivendo la classe `Search`, consentendogli di iniettare una logica di filtro personalizzata (categorie, produttori) nella query di ricerca. Sfrutta i modelli MVC standard di PrestaShop per la sua visualizzazione front-office (hook, template) e la configurazione back-office (metodo `getContent()` nel file principale del modulo). La funzionalità AJAX è gestita tramite un file JavaScript dedicato che interagisce con il meccanismo di ricerca principale di PrestaShop.

### 4.2 Controller (`controllers/`)

Questo modulo non introduce controller Front-Office o Back-Office Admin personalizzati. La sua funzionalità front-office è gestita principalmente dalla classe `Search` sovrascritta e dalla sua visualizzazione tramite hook del modulo. La configurazione back-office è gestita direttamente all'interno del metodo `getContent()` del file del modulo `blocksearchpro.php`.

### 4.3 Classi e modelli principali (`classes/`)

-   **`blocksearchpro/override/classes/index.php`**:

    -   Questo è un file `index.php` vuoto standard, tipicamente posizionato nelle directory per prevenire l'elenco delle directory. Non ha alcun impatto funzionale sulla logica del modulo.
-   **`blocksearchpro/override/classes/Search.php`**:

    -   **Nome classe**: `Search` (sovrascrive la classe `Search` principale)
    -   **Classe padre**: `SearchCore`
    -   **Responsabilità**: Questo è il file più critico. Sovrascrive la classe `Search` predefinita di PrestaShop, modificando specificamente il metodo `find()` (o metodi simili correlati alla ricerca) per incorporare la logica di filtro personalizzata del modulo.
        -   Legge i valori di configurazione (`bsp_cat_exc`, `bsp_subcat`, `bsp_cat`, `bsp_man`) dalla tabella `ps_configuration`.
        -   Modifica la query SQL utilizzata per la ricerca dei prodotti per includere clausole `WHERE` che filtrano per categorie e/o produttori selezionati.
        -   Garantisce che la ricerca rispetti l'impostazione "Cerca nelle sottocategorie" quando vengono applicati i filtri di categoria.
        -   Questa sovrascrittura è ciò che consente al modulo di iniettare le sue capacità di filtro direttamente nel meccanismo di ricerca principale di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`blocksearchpro/blocksearchpro.js`**:
    -   **Ambito**: Front-office.
    -   **Responsabilità**: Questo script migliora l'esperienza utente per il blocco di ricerca.
        -   Probabilmente lega i listener di eventi al campo di input di ricerca (es. `keyup`, `focus`, `blur`).
        -   Gestisce le richieste AJAX per i suggerimenti di ricerca istantanea, inviando il valore di input corrente all'endpoint AJAX di ricerca principale di PrestaShop.
        -   Elabora la risposta JSON dalla chiamata AJAX e popola dinamicamente l'elenco a discesa dei suggerimenti di prodotti sotto la barra di ricerca.
        -   Gestisce la visualizzazione e la nascondere dell'elenco dei suggerimenti, la navigazione da tastiera all'interno dei suggerimenti e gli eventi di clic sui suggerimenti per reindirizzare alle pagine dei prodotti.
        -   Potrebbe anche gestire la logica "Consenti di inviare la ricerca con input di parola chiave di ricerca vuoto" lato client.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`blocksearchpro/blocksearchpro.css`**:
    -   **Ambito**: Stile del cliente front-office.
    -   **Componenti UI principali e contenitori che stilizza**:
        -   Il campo di input di ricerca stesso (`#search_query_top`, `.search_query`).
        -   Il pulsante di ricerca (`#search_button`, `.button-search`).
        -   Il contenitore per i suggerimenti di ricerca AJAX (`.ac_results`, `.block_search_pro_results`).
        -   Singoli elementi di suggerimento all'interno del menu a discesa.
        -   Garantisce la reattività per varie dimensioni dello schermo.
    -   **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere**:
        -   `.block_search_pro` (contenitore principale)
        -   `.search_query` (campo di input)
        -   `.button-search` (pulsante di invio)
        -   `.ac_results` (contenitore dei risultati AJAX)
        -   `.ac_odd`, `.ac_even`, `.ac_over` (stile per gli elementi di suggerimento e gli stati di hover)
        -   Gli sviluppatori possono sovrascrivere questi stili nel `custom.css` del loro tema o creando un tema figlio.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template degli hook (`views/templates/hook/`)**:
    -   **`blocksearchpro/blocksearchpro-top.tpl`**:
        -   **Hook**: `displayTop`, `displayNav` (e potenzialmente `displayHeader` a seconda del tema).
        -   **Scopo**: Renderizza il campo di input di ricerca e il pulsante, tipicamente per la barra di ricerca dell'intestazione principale. Include la struttura HTML necessaria per il modulo di ricerca e il contenitore per i risultati AJAX.
    -   **`blocksearchpro/blocksearchpro.tpl`**:
        -   **Hook**: `displayLeftColumn`, `displayRightColumn`.
        -   **Scopo**: Renderizza un blocco di ricerca per le colonne laterali. Questo template potrebbe avere un layout o uno stile leggermente diverso rispetto alla barra di ricerca superiore, ottimizzato per spazi di colonna più stretti. Include anche il modulo di ricerca e il contenitore dei risultati AJAX.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Questo modulo non crea tabelle SQL personalizzate.
    -   Memorizza le sue impostazioni di configurazione nella tabella standard `ps_configuration` di PrestaShop.
    -   Chiavi di configurazione utilizzate: `mypresta_updates`, `update_`, `updatev_`, `PS_SEARCH_AJAX`, `bsp_cat_exc`, `PS_INSTANT_SEARCH`, `bsp_empty`, `PS_SEARCH_MINWORDLEN`, `bsp_subcat`, `bsp_cat`, `bsp_man`, `bsp_size`.
-   **Tabella degli hook registrati**:

| Nome dell'Hook | Tempistica di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Inietta le risorse CSS (`blocksearchpro.css`) e JavaScript (`blocksearchpro.js`) per la funzionalità front-office. |
| `displayTop` | Tipicamente nell'area dell'intestazione principale del negozio. | Renderizza il blocco di ricerca usando `blocksearchpro-top.tpl`. |
| `displayNav` | Spesso nella barra di navigazione superiore (sopra `displayTop`). | Renderizza il blocco di ricerca usando `blocksearchpro-top.tpl`. |
| `displayLeftColumn` | Nella barra laterale sinistra delle pagine che ne hanno una. | Renderizza il blocco di ricerca usando `blocksearchpro.tpl`. |
| `displayRightColumn` | Nella barra laterale destra delle pagine che ne hanno una. | Renderizza il blocco di ricerca usando `blocksearchpro.tpl`. |
| `actionValidateOrder` | Dopo che un ordine è stato convalidato con successo. | (Non direttamente utilizzato da questo modulo per la sua funzionalità di ricerca principale, ma un hook comune per altri moduli. Nessuna azione specifica qui per Block Search Pro.) |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e ulteriore assistenza con il modulo Block Search Pro, visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è pronto ad aiutarti con qualsiasi problema o domanda tu possa avere.
