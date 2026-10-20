---
title: "Commenti Prodotto - Rich snippet recensioni - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Commenti Prodotto - Rich snippet recensioni di MyPresta.eu."
sidebar:
  label: "Commenti Prodotto - Rich snippet recensioni - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Product Comments - Reviews rich snippet su MyPresta.eu](https://mypresta.eu/modules/seo/product-comments-reviews-rich-snippet.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/seo/product-comments-reviews-rich-snippet/)
>
> ---


# Commenti Prodotto - Rich snippet recensioni

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).
- **Dipendenza**: Questo modulo estende la funzionalità del **modulo gratuito Commenti Prodotto di PrestaShop**. Devi avere il modulo ufficiale Commenti Prodotto di PrestaShop installato e attivo affinché questo modulo funzioni correttamente.

## 2. Panoramica completa della configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questo modulo ha una pagina di configurazione semplice, focalizzata principalmente sull'abilitazione o disabilitazione della sua funzionalità principale e sulla selezione di dove i dati del rich snippet devono essere iniettati.

**Per accedere:** Vai su **Moduli > Gestione moduli**, cerca "Commenti Prodotto - Rich snippet recensioni" e clicca su "Configura".

#### **Abilita / Disabilita Rich Snippet**

-   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare la funzionalità principale del modulo. Quando abilitato, il modulo inizierà ad aggiungere i dati strutturati necessari alle tue pagine prodotto.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* Il modulo inietterà il codice rich snippet nelle tue pagine prodotto, consentendo a Google di visualizzare le valutazioni a stelle e i conteggi delle recensioni nei risultati di ricerca.
    -   *Quando disabilitato:* Il modulo smetterà di iniettare il codice rich snippet. Le tue inserzioni di prodotti nei risultati di ricerca di Google torneranno al testo standard, senza stelle o conteggi di recensioni.
-   **Valore consigliato:** **SÌ** (Abilitato). Lo scopo principale di questo modulo è visualizzare i rich snippet, quindi dovrebbe essere quasi sempre abilitato.
-   **Scenario / esempio del commerciante:** Se stai testando il modulo o desideri temporaneamente nascondere i dati delle recensioni dai risultati di ricerca (es. durante una revisione importante del sito), potresti disabilitarlo. Altrimenti, mantienilo abilitato per massimizzare la visibilità.

#### **Visualizza Rich Snippet nell'Hook**

-   **Cosa fa questa impostazione:** Questa opzione ti consente di scegliere *dove* sulla tua pagina prodotto il modulo dovrebbe iniettare i dati strutturati. Sebbene i dati siano invisibili al cliente, il loro posizionamento può talvolta influire sulla compatibilità con temi o altri moduli.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su 'Header':* I dati del rich snippet verranno posizionati all'interno della sezione `<head>` dell'HTML della tua pagina prodotto. Questa è generalmente la posizione più comune e consigliata per i dati strutturati.
    -   *Quando impostato su 'Prodotto':* I dati del rich snippet verranno posizionati all'interno dell'area del contenuto principale del prodotto.
    -   *Quando impostato su 'Colonne':* I dati del rich snippet verranno posizionati all'interno di una delle colonne laterali del tuo negozio (sinistra o destra, a seconda del layout del tuo tema).
    -   *Quando impostato su 'Footer':* I dati del rich snippet verranno posizionati all'interno della sezione `<footer>` dell'HTML della tua pagina prodotto.
-   **Valore consigliato:** **Header**. Questa è la posizione più standard e robusta per i dati strutturati, poiché viene elaborata precocemente dai crawler dei motori di ricerca ed è meno probabile che entri in conflitto con elementi visivi o altri script sulla tua pagina.
-   **Scenario / esempio del commerciante:** Se riscontri problemi imprevisti con il layout della tua pagina prodotto o altri moduli dopo aver abilitato i rich snippet, potresti provare a cambiare questo hook in 'Prodotto' o 'Footer' come passaggio di risoluzione dei problemi. Tuttavia, 'Header' è di solito la scelta più sicura.

#### **Visualizza Rich Snippet Brevi (solo stelle)**

-   **Cosa fa questa impostazione:** Questa opzione ti consente di scegliere tra la visualizzazione del rich snippet completo (stelle + conteggio recensioni) o una versione "breve" che mostra solo le stelle, senza il numero di recensioni.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* Google visualizzerà solo la valutazione a stelle (es. ”★★★★★ 4.5”) nei risultati di ricerca, omettendo la parte "(X recensioni)".
    -   *Quando disabilitato:* Google visualizzerà sia la valutazione a stelle che il numero di recensioni (es. ”★★★★★ 4.5 (12 recensioni)”).
-   **Valore consigliato:** **NO** (Disabilitato). Visualizzare sia le stelle che il conteggio delle recensioni fornisce informazioni più complete e spesso costruisce più fiducia, specialmente se hai un numero elevato di recensioni.
-   **Scenario / esempio del commerciante:** Se hai pochissime recensioni su molti prodotti e ritieni che visualizzare "1 recensione" possa sembrare meno impressionante rispetto alle sole stelle, potresti abilitare questa opzione. Tuttavia, per la maggior parte dei negozi con un numero sano di recensioni, mostrare il conteggio è vantaggioso.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Abilita / Disabilita Rich Snippet | SÌ (Abilitato) | Attiva/disattiva l'iniezione del codice rich snippet per i risultati di ricerca di Google. |
| Configurazione modulo | Visualizza Rich Snippet nell'Hook | Header | Determina dove il codice rich snippet invisibile viene posizionato sulla pagina prodotto. 'Header' è generalmente il migliore per la compatibilità. |
| Configurazione modulo | Visualizza Rich Snippet Brevi (solo stelle) | NO (Disabilitato) | Controlla se nei risultati di ricerca di Google vengono mostrate solo le stelle o le stelle + il conteggio delle recensioni. Si consiglia di mostrare entrambi. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho installato il modulo, ma non vedo le stelle nei risultati di ricerca di Google. Cosa c'è che non va?**
R: Diversi fattori potrebbero essere in gioco:
1.  **Tempo di scansione di Google:** Ci vuole tempo perché Google esegua nuovamente la scansione del tuo sito web e aggiorni il suo indice. Questo può variare da pochi giorni a qualche settimana, specialmente per nuove pagine o modifiche significative.
2.  **Cache:** Svuota la cache di PrestaShop (Parametri avanzati > Prestazioni > Svuota cache) dopo la configurazione.
3.  **Google Search Console:** Controlla la tua Google Search Console per "Snippet di recensioni" sotto "Miglioramenti". Se ci sono errori, Google potrebbe non visualizzare gli snippet.
4.  **Nessuna recensione:** Assicurati che il prodotto abbia effettivamente recensioni approvate nel tuo negozio. Google non visualizzerà le stelle se non ci sono recensioni.
5.  **Modulo Commenti Prodotto:** Verifica che il modulo ufficiale Commenti Prodotto di PrestaShop sia installato e attivo. Questo modulo si basa su di esso.
6.  **Discrezione di Google:** Sebbene il modulo fornisca i dati, Google decide in ultima analisi se visualizzare i rich snippet. Potrebbe scegliere di non visualizzarli se ritiene il contenuto irrilevante o di bassa qualità.

**D: La mia pagina prodotto appare danneggiata dopo l'installazione del modulo.**
R: Questo è altamente improbabile poiché il modulo inietta solo dati strutturati invisibili. Tuttavia, se dovesse accadere:
1.  **Disabilita il modulo:** Vai su Gestione moduli e disabilita "Commenti Prodotto - Rich snippet recensioni". Se la pagina torna alla normalità, allora il modulo potrebbe essere la causa.
2.  **Modifica l'impostazione "Visualizza Rich Snippet nell'Hook":** Prova a cambiare l'hook da 'Header' a 'Prodotto' o 'Footer'. A volte, possono verificarsi conflitti di tema con posizionamenti specifici degli hook.
3.  **Svuota la cache:** Svuota sempre la cache di PrestaShop dopo aver apportato modifiche.

**D: Questo modulo influisce sulla velocità di caricamento del mio sito web?**
R: No, l'impatto sulla velocità di caricamento è trascurabile. Il modulo aggiunge solo un piccolo blocco di testo (dati strutturati) all'HTML della tua pagina, che è molto leggero e viene elaborato rapidamente da browser e motori di ricerca.

**D: Posso personalizzare l'aspetto delle stelle nei risultati di ricerca di Google?**
R: No, l'aspetto delle stelle e del conteggio delle recensioni nei risultati di ricerca di Google è interamente controllato dall'interfaccia di Google. Questo modulo fornisce i dati; Google li renderizza. Non puoi cambiare il colore, la dimensione o lo stile delle stelle nei risultati di ricerca.

**D: Questo modulo funzionerà con temi personalizzati?**
R: Sì, questo modulo è progettato per funzionare indipendentemente dallo stile visivo del tuo tema. Inietta dati strutturati nell'HTML, che è una pratica standard. Finché il tuo tema personalizzato implementa correttamente il sistema di hook di PrestaShop, il modulo dovrebbe funzionare senza problemi.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce un'analisi approfondita dell'architettura tecnica del modulo "Commenti Prodotto - Rich snippet recensioni", destinata a sviluppatori, webmaster e agenzie tecniche.

### 4.1 Panoramica dell'architettura

Il modulo `prrs` (Product Reviews Rich Snippet) è un modulo PrestaShop leggero progettato per iniettare dati strutturati `AggregateRating` di Schema.org nelle pagine prodotto. Sfrutta i dati esistenti dal modulo ufficiale `productcomments`. Il modulo opera principalmente agganciandosi a un punto di visualizzazione (configurabile dal commerciante) e renderizzando un template Smarty contenente i dati strutturati JSON-LD. Segue una struttura standard del modulo PrestaShop, con una classe modulo principale e alcune risorse di supporto.

### 4.2 Controller (`controllers/`)

Questo modulo non contiene alcun controller Front-Office o Back-Office personalizzato. Tutta la logica è gestita all'interno del file principale del modulo `index.php` e dei suoi template associati.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non definisce alcuna classe personalizzata né estende `ObjectModel`. Si basa principalmente sulle funzionalità core esistenti di PrestaShop e sui dati del modulo `productcomments`.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`prrs/lib/searchTool/views/js/autocomplete.js`**
    -   **Ambito:** Back-office (probabilmente per uno strumento di ricerca interno, sebbene non direttamente utilizzato dalla funzionalità rich snippet principale del modulo).
    -   **Responsabilità:** Questo script sembra far parte di un'utilità generica di completamento automatico. Probabilmente gestisce le richieste AJAX per i suggerimenti di ricerca, aggiorna i campi di input e gestisce la visualizzazione dei risultati di ricerca in un menu a discesa. Data la funzione principale del modulo, questo potrebbe essere un residuo o una dipendenza da una libreria condivisa. Non è direttamente coinvolto nella generazione del rich snippet.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`prrs/lib/searchTool/views/css/autocomplete.css`**
    -   **Ambito:** Back-office.
    -   **Responsabilità:** Fornisce lo stile per lo strumento di ricerca con completamento automatico menzionato sopra. Ciò includerebbe stili per l'input di ricerca, i suggerimenti a discesa, i risultati evidenziati, ecc. Non rilevante per la visualizzazione front-office.
-   **`prrs/views/css/prrs.css`**
    -   **Ambito:** Front-office.
    -   **Responsabilità:** Questo foglio di stile è probabilmente minimale o vuoto, poiché la funzione principale del modulo è iniettare dati strutturati invisibili. Se contiene stili, sarebbero per elementi molto sottili e non intrusivi, o potenzialmente per un fallback visivo se i dati strutturati stessi avessero un componente visibile (cosa che tipicamente non accade per i rich snippet). Gli sviluppatori dovrebbero controllare questo file per qualsiasi output visivo inaspettato.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **`prrs/lib/searchTool/views/scripts.tpl`**
    -   **Ambito:** Back-office.
    -   **Scopo:** Questo template probabilmente include il JavaScript per lo strumento di ricerca con completamento automatico (`autocomplete.js`) e potenzialmente altri script correlati o configurazioni di script inline. Verrebbe renderizzato in un contesto di amministrazione.
-   **`prrs/views/templates/prrs-json.tpl`**
    -   **Ambito:** Front-office (pagina prodotto).
    -   **Scopo:** Questo è il template principale responsabile della generazione dei dati strutturati JSON-LD per il rich snippet `AggregateRating`. Recupera dinamicamente la valutazione media del prodotto e il conteggio delle recensioni dal modulo `productcomments` e li formatta secondo le specifiche di Schema.org. Questo template viene renderizzato quando l'opzione "Visualizza Rich Snippet Brevi" è disabilitata.
    -   **Punti dati chiave:** `product.id_product`, `product.name`, `product.link_rewrite`, `product.link`, `product.cover.bySize.home_default.url`, `average_grade`, `nb_comments`.
-   **`prrs/views/templates/prrs.tpl`**
    -   **Ambito:** Front-office (pagina prodotto).
    -   **Scopo:** Questo template è probabilmente un wrapper o un'alternativa a `prrs-json.tpl`, potenzialmente utilizzato per versioni precedenti di PrestaShop o integrazioni di hook specifiche. Genera anche i dati del rich snippet. È importante verificare quale template viene utilizzato attivamente in base alla logica `getContent()` del modulo e alla registrazione dell'hook.
-   **`prrs/views/templates/shortprrs.tpl`**
    -   **Ambito:** Front-office (pagina prodotto).
    -   **Scopo:** Questo template genera uno snippet di dati strutturati JSON-LD semplificato, tipicamente includendo solo la valutazione media a stelle senza il conteggio esplicito delle recensioni. Viene renderizzato quando l'opzione "Visualizza Rich Snippet Brevi" è abilitata.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Questo modulo non crea tabelle di database personalizzate.
    -   Si basa sulla tabella `ps_configuration` per memorizzare le sue impostazioni (es. `PRRS_ENABLED`, `PRRS_HOOK`, `PRRS_SHORT`).
    -   Recupera i dati delle recensioni dalle tabelle create dal modulo ufficiale `productcomments` (es. `ps_product_comment`, `ps_product_comment_criterion`).
-   **Tabella degli hook registrati**:

| Nome dell'Hook | Tempistica / Contesto di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Renderizza all'interno della sezione `<head>` della pagina. | Inietta dati strutturati JSON-LD per i rich snippet all'inizio del caricamento della pagina. Configurabile tramite le impostazioni del modulo. |
| `displayProductAdditionalInfo` | Renderizza all'interno della pagina prodotto, tipicamente sotto i dettagli principali del prodotto. | Hook alternativo per iniettare dati strutturati JSON-LD. Configurabile tramite le impostazioni del modulo. |
| `displayLeftColumn` / `displayRightColumn` | Renderizza all'interno delle rispettive colonne laterali. | Meno comune, ma disponibile come hook alternativo per iniettare dati strutturati JSON-LD. Configurabile tramite le impostazioni del modulo. |
| `displayFooter` | Renderizza all'interno della sezione `<footer>` della pagina. | Hook alternativo per iniettare dati strutturati JSON-LD, tipicamente alla fine della pagina. Configurabile tramite le impostazioni del modulo. |
| `actionFrontControllerSetMedia` | Eseguito quando un controller front-office imposta le sue risorse multimediali. | Utilizzato per registrare file CSS e JavaScript per il front office. |
| `actionAdminControllerSetMedia` | Eseguito quando un controller admin imposta le sue risorse multimediali. | Utilizzato per registrare file CSS e JavaScript per il back office (es. `autocomplete.js`, `autocomplete.css`). |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda relativa al modulo "Commenti Prodotto - Rich snippet recensioni".
