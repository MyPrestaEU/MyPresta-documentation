---
title: "Html box - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Html box di MyPresta.eu."
sidebar:
  label: "Html box - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Html box su MyPresta.eu](https://mypresta.eu/modules/front-office-features/html-box.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/html-box/)
>
> ---


# Html box

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per un'installazione PrestaShop e sono sufficienti per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Html box)

Questa è la schermata di configurazione principale dove definisci il contenuto per le tue Html box e dove appaiono.

#### Impostazioni generali

- **Abilita SSL (https) per questo modulo?** (`htmlbox_ssl`)

  - **Cosa fa questa impostazione:** Determina se il contenuto del modulo deve essere caricato in modo sicuro tramite HTTPS.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (SÌ):* Assicura che qualsiasi contenuto generato da questo modulo sia servito tramite HTTPS, prevenendo avvisi di "contenuto misto" nei browser se il tuo negozio utilizza SSL.
    - *Quando disabilitato (NO):* Il contenuto potrebbe essere servito tramite HTTP, il che può causare avvisi di sicurezza sui negozi abilitati HTTPS.
  - **Valore consigliato:** **SÌ**
  - **Scenario / esempio per il commerciante:** Se il tuo negozio utilizza HTTPS (cosa che dovrebbe fare!), abilitare questa opzione assicura che il tuo contenuto personalizzato non attivi avvisi di sicurezza per i tuoi clienti.
- **Disabilita l'editor TinyMCE?** (`htmlbox_disabletiny`)

  - **Cosa fa questa impostazione:** Controlla se l'editor di testo ricco (TinyMCE) viene utilizzato per inserire il tuo contenuto HTML.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (SÌ):* Vedrai un'area di testo semplice per inserire il tuo HTML, JavaScript o CSS. Questo è utile se stai incollando codice complesso che TinyMCE potrebbe tentare di "pulire" o se preferisci scrivere HTML grezzo.
    - *Quando disabilitato (NO):* Avrai un editor di testo ricco e facile da usare, simile a un elaboratore di testi, che ti consente di formattare il testo, aggiungere immagini e creare collegamenti senza scrivere HTML direttamente.
  - **Valore consigliato:** **NO** (a meno che tu non sia uno sviluppatore o stia incollando codice complesso).
  - **Scenario / esempio per il commerciante:** Se vuoi aggiungere rapidamente un annuncio di testo in grassetto, lascialo disabilitato. Se stai incollando un codice widget di Facebook, abilitalo per impedire all'editor di alterare il tuo codice.
- **Mostra solo ai clienti loggati?** (`htmlbox_logged`)

  - **Cosa fa questa impostazione:** Limita la visibilità del contenuto dell'Html box solo ai clienti che hanno effettuato l'accesso ai loro account.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (SÌ):* Solo i clienti registrati e loggati vedranno il contenuto dell'Html box.
    - *Quando disabilitato (NO):* Tutti i visitatori, loggati o meno, vedranno il contenuto.
  - **Valore consigliato:** **NO** (a meno che tu non abbia contenuti specifici per gli utenti loggati).
  - **Scenario / esempio per il commerciante:** Potresti abilitare questa opzione se desideri visualizzare un messaggio speciale del programma fedeltà o offerte esclusive visibili solo alla tua base di clienti esistente.
- **Mostra solo ai clienti NON loggati?** (`htmlbox_unlogged`)

  - **Cosa fa questa impostazione:** Limita la visibilità del contenuto dell'Html box solo ai clienti che *non* hanno effettuato l'accesso ai loro account.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (SÌ):* Solo i visitatori che non hanno effettuato l'accesso vedranno il contenuto dell'Html box.
    - *Quando disabilitato (NO):* Tutti i visitatori, loggati o meno, vedranno il contenuto.
  - **Valore consigliato:** **NO** (a meno che tu non abbia contenuti specifici per gli ospiti).
  - **Scenario / esempio per il commerciante:** Potresti abilitare questa opzione per visualizzare un messaggio "Accedi o Registrati per offerte esclusive" per incoraggiare nuove iscrizioni o clienti di ritorno ad accedere.

#### Campi di contenuto dell'Html Box

Questi campi sono dove inserisci il contenuto HTML, JavaScript o CSS effettivo per ogni hook specifico. Ogni campo corrisponde a una posizione diversa nel tuo negozio.

- **HTML per l'intestazione (displayTop, displayNav1, displayNav2)** (`htmlbox_header`)

  - **Cosa fa questa impostazione:** Questo è il contenuto che apparirà nella sezione dell'intestazione del tuo negozio. A seconda del tuo tema, potrebbe essere `displayTop`, `displayNav1` o `displayNav2`.
  - **Effetto della modifica di questa impostazione:** Il contenuto che inserisci qui sarà visibile nella parte superiore del tuo sito web.
  - **Valore consigliato:** Lascia vuoto se non necessario.
  - **Scenario / esempio per il commerciante:** Un banner di annuncio a livello di sito ("Spedizione gratuita su tutti gli ordini superiori a $50!"), una piccola barra di icone dei social media o una barra di ricerca personalizzata.
- **HTML per la colonna superiore (displayTopColumn)** (`htmlbox_top`)

  - **Cosa fa questa impostazione:** Questo contenuto appare appena sotto l'intestazione, spesso estendendosi per l'intera larghezza dell'area del contenuto principale.
  - **Effetto della modifica di questa impostazione:** Il contenuto che inserisci qui sarà visualizzato in modo prominente nella parte superiore dell'area del contenuto principale, tipicamente sopra gli elenchi dei prodotti principali o il contenuto della homepage.
  - **Valore consigliato:** Lascia vuoto se non necessario.
  - **Scenario / esempio per il commerciante:** Un grande banner promozionale per una vendita stagionale, uno slider di prodotti in evidenza o un'introduzione video al tuo brand.
- **HTML per la colonna sinistra (displayLeftColumn)** (`htmlbox_leftcol`)

  - **Cosa fa questa impostazione:** Questo contenuto appare nella barra laterale sinistra del tuo negozio (se il tuo tema ne ha una ed è abilitata).
  - **Effetto della modifica di questa impostazione:** Il contenuto che inserisci qui sarà visualizzato nella colonna sinistra, insieme ad altri moduli come filtri di categoria o navigazione.
  - **Valore consigliato:** Lascia vuoto se non necessario.
  - **Scenario / esempio per il commerciante:** Un elenco "Acquista per marca", un modulo di iscrizione alla newsletter, una piccola pubblicità per una categoria di prodotti specifica o una Facebook Like Box.
- **HTML per la colonna destra (displayRightColumn)** (`htmlbox_rightcol`)

  - **Cosa fa questa impostazione:** Questo contenuto appare nella barra laterale destra del tuo negozio (se il tuo tema ne ha una ed è abilitata).
  - **Effetto della modifica di questa impostazione:** Il contenuto che inserisci qui sarà visualizzato nella colonna destra, in modo simile alla colonna sinistra.
  - **Valore consigliato:** Lascia vuoto se non necessario.
  - **Scenario / esempio per il commerciante:** Un elenco "Bestseller", un blocco di contatto del servizio clienti, un feed di Pinterest o una sezione "Prodotti visualizzati di recente".
- **HTML per il piè di pagina (displayFooter)** (`htmlbox_footercol`)

  - **Cosa fa questa impostazione:** Questo contenuto appare nella sezione del piè di pagina in fondo a ogni pagina.
  - **Effetto della modifica di questa impostazione:** Il contenuto che inserisci qui sarà visibile nella parte inferiore del tuo sito web.
  - **Valore consigliato:** Lascia vuoto se non necessario.
  - **Scenario / esempio per il commerciante:** Loghi dei metodi di pagamento, sigilli di fiducia, una breve descrizione "Chi siamo", collegamenti ai social media o un avviso di copyright personalizzato.
- **HTML per la homepage (displayHome)** (`htmlbox_homecol`)

  - **Cosa fa questa impostazione:** Questo contenuto viene visualizzato specificamente sulla homepage del tuo negozio.
  - **Effetto della modifica di questa impostazione:** Il contenuto che inserisci qui sarà una parte centrale del layout della tua homepage.
  - **Valore consigliato:** Lascia vuoto se non necessario.
  - **Scenario / esempio per il commerciante:** Una griglia di categorie in evidenza, una sezione "Perché acquistare da noi", testimonianze dei clienti o un grande pulsante di invito all'azione.
- **HTML per il corpo (displayBody)** (`htmlbox_body`)

  - **Cosa fa questa impostazione:** Questo contenuto viene iniettato nel tag `<body>` del tuo HTML, tipicamente alla fine prima del tag di chiusura `</body>`. Viene spesso utilizzato per script globali o elementi che devono essere disponibili su tutto il sito ma non sono visivamente legati a una sezione specifica.
  - **Effetto della modifica di questa impostazione:** Il contenuto sarà presente su ogni pagina del tuo negozio, ma il suo posizionamento visivo potrebbe dipendere dal CSS del tuo tema. È eccellente per codici di tracciamento o pop-up.
  - **Valore consigliato:** Lascia vuoto se non necessario.
  - **Scenario / esempio per il commerciante:** Codice di tracciamento di Google Analytics, Facebook Pixel, un banner globale per il consenso ai cookie (se non gestito da un altro modulo) o uno script per il widget di chat.

#### Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Abilita SSL (https) per questo modulo? | SÌ | Assicura che il contenuto sia caricato in modo sicuro, prevenendo avvisi di contenuto misto. |
| Configurazione modulo | Disabilita l'editor TinyMCE? | NO | Controlla l'editor di testo ricco per l'input del contenuto. Abilita per codice grezzo. |
| Configurazione modulo | Mostra solo ai clienti loggati? | NO | Limita la visibilità del contenuto agli utenti loggati. |
| Configurazione modulo | Mostra solo ai clienti NON loggati? | NO | Limita la visibilità del contenuto agli utenti ospiti. |
| Configurazione modulo | HTML per l'intestazione | Vuoto | Contenuto personalizzato nell'area dell'intestazione (es. annunci, banner superiori). |
| Configurazione modulo | HTML per la colonna superiore | Vuoto | Contenuto personalizzato sotto l'intestazione, spesso a tutta larghezza (es. promozioni principali). |
| Configurazione modulo | HTML per la colonna sinistra | Vuoto | Contenuto personalizzato nella barra laterale sinistra (es. feed social, newsletter). |
| Configurazione modulo | HTML per la colonna destra | Vuoto | Contenuto personalizzato nella barra laterale destra (es. bestseller, servizio clienti). |
| Configurazione modulo | HTML per il piè di pagina | Vuoto | Contenuto personalizzato nel piè di pagina (es. loghi di pagamento, sigilli di fiducia). |
| Configurazione modulo | HTML per la homepage | Vuoto | Contenuto personalizzato specificamente sulla homepage (es. prodotti in evidenza). |
| Configurazione modulo | HTML per il corpo | Vuoto | Contenuto/script globale iniettato nel `<body>` (es. analytics, widget di chat). |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D: Il mio HTML personalizzato non viene visualizzato o appare danneggiato.**
R:

1. **Controlla l'Hook:** Assicurati di aver inserito il contenuto nel campo corretto dell'Html box per la posizione desiderata (ad esempio, `HTML per la homepage` per la homepage).
2. **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** nel tuo Back Office di PrestaShop e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). PrestaShop spesso memorizza il contenuto nella cache e le nuove impostazioni del modulo potrebbero non apparire immediatamente.
3. **Ispeziona l'HTML:** Se ti senti a tuo agio, usa gli strumenti per sviluppatori del tuo browser (F12) per ispezionare l'area in cui dovrebbe trovarsi il contenuto. Cerca errori nella console o verifica se il tuo HTML è presente ma stilizzato in modo errato.
4. **Interferenza di TinyMCE:** Se stai incollando codice complesso (specialmente JavaScript o iframe), prova ad abilitare "Disabilita l'editor TinyMCE?" per assicurarti che l'editor non stia rimuovendo o alterando il tuo codice.

**D: Il contenuto appare, ma non ha un bell'aspetto su mobile.**
R: Il modulo stesso è responsive, ma il *contenuto che aggiungi* deve essere anch'esso responsive.

1. **Usa HTML/CSS responsive:** Se stai scrivendo HTML personalizzato, assicurati di utilizzare principi di design responsive (ad esempio, `max-width: 100%` per le immagini, media query CSS).
2. **Widget di terze parti:** Se stai incorporando un widget (come Facebook o Twitter), controlla se il fornitore del widget offre codici di incorporamento o impostazioni responsive.
3. **Contenuto semplice:** Per contenuti mobili critici, mantienilo semplice: testo normale, immagini piccole e chiare chiamate all'azione.

**D: Ho aggiunto JavaScript, ma non viene eseguito.**
R:

1. **Posizionamento:** Il JavaScript aggiunto al campo `HTML per il corpo` è generalmente il posto più sicuro per gli script globali, poiché viene caricato alla fine della pagina.
2. **Errori di sintassi:** Controlla il tuo codice JavaScript per eventuali errori di sintassi. Un singolo errore può impedire l'esecuzione dell'intero script.
3. **Conflitti jQuery:** Se il tuo script si basa su jQuery, assicurati che sia caricato correttamente e che non ci siano conflitti con la versione di jQuery di PrestaShop. Potrebbe essere necessario racchiudere il tuo codice in `(function($){ /* il tuo codice */ })(jQuery);` o usare `jQuery.noConflict();`.
4. **Script esterni:** Se stai collegando un file `.js` esterno, assicurati che l'URL sia corretto e accessibile.

**D: Come posso tradurre il contenuto delle mie Html box per diverse lingue?**
R: La versione attuale del modulo non offre campi multilingue integrati per ogni Html box. Per ottenere contenuti multilingue, hai due opzioni principali:

1. **Rilevamento manuale della lingua (Avanzato):** Puoi incorporare una logica condizionale all'interno del contenuto della tua Html box utilizzando variabili Smarty (se il tuo tema consente l'elaborazione Smarty negli hook) o JavaScript per rilevare la lingua corrente e visualizzare contenuti diversi. Questa è una soluzione più avanzata.
   *Esempio (Smarty):*

   ```
   {if $language.iso\_code == 'en'} <p>Welcome to our English store!</p>{elseif $language.iso\_code == 'fr'} <p>Bienvenue dans notre boutique française !</p>{/if}
   ```
2. **Moduli separati (Soluzione alternativa):** Per contenuti critici, potresti considerare di installare istanze separate del modulo "Html box" (se consentito dallo sviluppatore del modulo o duplicando il modulo) e assegnare ciascuna a una lingua specifica, quindi gestire la loro visualizzazione tramite le posizioni dei moduli di PrestaShop. Questa è una soluzione alternativa più complessa.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster che lavorano con il modulo Html box.

### 4.1 Panoramica dell'architettura

Il modulo `Html box` è un modulo PrestaShop semplice progettato principalmente per iniettare contenuto HTML/JS/CSS personalizzato in vari hook del front-office. Segue una classica struttura di modulo PrestaShop, sfruttando la classe `Module` per l'installazione, la disinstallazione e la configurazione, e utilizzando i metodi `hook` per renderizzare il contenuto nel front office. La configurazione è gestita tramite il metodo `getContent()`, che renderizza un modulo di configurazione PrestaShop standard. Il modulo memorizza il suo contenuto direttamente nella tabella `ps_configuration`.

### 4.2 Controller (`controllers/`)

Questo modulo **non** contiene alcun controller amministrativo Front-Office o Back-Office personalizzato. Tutte le funzionalità, inclusa la configurazione e il rendering del front-office, sono gestite direttamente all'interno del file principale del modulo `htmlbox.php`.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo **non** definisce alcuna classe personalizzata o istanza di `ObjectModel`. Tutti i dati sono memorizzati come valori di configurazione.

### 4.4 Risorse JavaScript (`views/js/`)

- **`htmlbox/tinymce16.inc.js`**
  - **Ambito:** Back-office (specificamente la pagina di configurazione del modulo).
  - **Scopo:** Questo file è responsabile dell'inizializzazione e della configurazione dell'editor di testo ricco TinyMCE all'interno del modulo di configurazione. Trasforma gli elementi `<textarea>` standard in un editor WYSIWYG facile da usare, consentendo ai commercianti di formattare il testo, inserire immagini e gestire il contenuto HTML senza codifica diretta. Probabilmente include impostazioni personalizzate per integrare TinyMCE con il file manager di PrestaShop per il caricamento delle immagini.
  - **Note per gli sviluppatori:** Se `htmlbox_disabletiny` è abilitato, questo script non verrà caricato o la sua funzionalità verrà bypassata. Gli sviluppatori che desiderano personalizzare l'esperienza di TinyMCE (ad esempio, aggiungendo pulsanti personalizzati, modificando il layout della barra degli strumenti) dovrebbero modificare questo file o sovrascrivere il suo caricamento/configurazione.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo **non** include alcun file CSS personalizzato. Qualsiasi stile per il contenuto HTML iniettato deve essere fornito all'interno del contenuto HTML stesso (stili inline o tag `<style>`) o dal tema PrestaShop attivo.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **`views/templates/hook/html.tpl`**
  - **Ambito:** Front-office.
  - **Rendering dell'Hook:** Questo è il file di template principale utilizzato dal modulo per renderizzare il contenuto HTML personalizzato in tutti gli hook del front-office registrati.
  - **Contenuto:** Probabilmente contiene una struttura semplice per l'output della variabile `$html_content`, che viene passata dai metodi hook del modulo.
  - **Note per gli sviluppatori:** Questo template è minimale. Il contenuto effettivo viene caricato dinamicamente dalla tabella `ps_configuration` in base all'hook. Gli sviluppatori possono sovrascrivere questo template nel loro tema (ad esempio, `themes/yourtheme/modules/htmlbox/html.tpl`) per racchiudere il contenuto in `div` personalizzati, aggiungere classi specifiche o applicare logica condizionale, sebbene la maggior parte della personalizzazione verrà eseguita direttamente nel contenuto dell'Html box stesso.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:
  Il modulo non crea tabelle di database personalizzate. Tutta la configurazione e il contenuto sono memorizzati nella tabella standard di PrestaShop `ps_configuration` utilizzando le seguenti chiavi:

  - `mypresta_updates`
  - `update_`
  - `updatev_`
  - `htmlbox_header`
  - `htmlbox_top`
  - `htmlbox_leftcol`
  - `htmlbox_rightcol`
  - `htmlbox_footercol`
  - `htmlbox_homecol`
  - `htmlbox_body`
  - `htmlbox_ssl`
  - `htmlbox_origtiny`
  - `htmlbox_disabletiny`
  - `htmlbox_home`
  - `htmlbox_hook`
  - `htmlbox_logged`
  - `htmlbox_unlogged`
- **Tabella degli hook registrati**:

| Nome dell'Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Principalmente per aggiungere meta tag, collegamenti CSS o JavaScript che devono essere caricati presto. |
| `displayTop` | Sezione superiore della pagina, tipicamente sopra il contenuto principale. | Contenuto generale per la parte superiore della pagina, spesso dipendente dal tema. |
| `displayNav1` | Barra di navigazione, spesso la barra superiore con collegamenti rapidi. | Contenuto per la prima barra di navigazione. |
| `displayNav2` | Barra di navigazione secondaria, spesso sotto `displayNav1`. | Contenuto per la seconda barra di navigazione. |
| `displayTopColumn` | Area a tutta larghezza sotto l'intestazione, sopra il contenuto principale. | Area di contenuto prominente, spesso utilizzata per banner o slider. |
| `displayLeftColumn` | Barra laterale sinistra nelle pagine in cui è abilitata. | Contenuto per la barra laterale sinistra (es. filtri, categorie, blocchi personalizzati). |
| `displayRightColumn` | Barra laterale destra nelle pagine in cui è abilitata. | Contenuto per la barra laterale destra (es. annunci, widget social). |
| `displayHome` | Area del contenuto principale della homepage. | Contenuto specifico per la homepage. |
| `displayFooter` | Sezione inferiore di ogni pagina. | Contenuto per il piè di pagina (es. copyright, loghi di pagamento, collegamenti). |
| `displayBody` | Alla fine del tag `<body>`. | Ideale per JavaScript globale (es. analytics, widget di chat) o elementi che dovrebbero essere caricati per ultimi. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). MyPresta.eu fornisce supporto dedicato per tutti i suoi moduli.
