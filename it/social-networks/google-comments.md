---
title: "Commenti Google+ - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Commenti Google+ di MyPresta.eu."
sidebar:
  label: "Commenti Google+ - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Google+ Comments su MyPresta.eu](https://mypresta.eu/modules/social-networks/google-comments.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/google-comments/)
>
> ---


# Commenti Google+

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo Commenti Google+. Qui troverai tutte le impostazioni per controllare come i commenti appaiono e funzionano nel tuo negozio.

**Accesso:** Naviga su **Moduli > Gestione moduli**, cerca "Commenti Google+", e clicca su **"Configura"**.

#### Impostazioni e Opzioni

1. **Visualizza Commenti Google+ sulla Pagina Prodotto**

   - **Cosa fa questa impostazione:** Questo interruttore controlla se la sezione dei commenti di Google+ viene mostrata sulle tue pagine prodotto.
   - **Effetto della modifica di questa impostazione:**
     - *Quando abilitato (SÌ):* La sezione dei commenti di Google+ apparirà su tutte le tue pagine prodotto, consentendo ai clienti di visualizzare e aggiungere commenti.
     - *Quando disabilitato (NO):* La sezione dei commenti di Google+ sarà nascosta da tutte le pagine prodotto.
   - **Valore consigliato:** SÌ (se vuoi utilizzare la funzione di commento).
   - **Scenario / esempio del commerciante:** Se vuoi incoraggiare l'interazione con i clienti e sfruttare i contenuti generati dagli utenti, abilita questa opzione. Se preferisci un sistema di commenti diverso o nessun commento, disabilitala.
2. **Scegli Hook per Commenti Google+**

   - **Cosa fa questa impostazione:** Questo menu a discesa ti consente di selezionare dove sulla pagina prodotto (o altre pagine) verrà visualizzato il blocco dei commenti di Google+. Gli hook sono posizioni specifiche nel tuo tema PrestaShop dove i moduli possono iniettare contenuto.
   - **Effetto della modifica di questa impostazione:**
     - *Selezionando `displayProductExtraContent` (o un hook simile per la pagina prodotto):* I commenti appariranno all'interno dell'area del contenuto principale della pagina prodotto, tipicamente sotto la descrizione del prodotto o le schede. Questo è il posizionamento più comune e consigliato.
     - *Selezionando `displayLeftColumn` o `displayRightColumn`:* Il blocco dei commenti apparirà nella barra laterale sinistra o destra del tuo negozio (se il tuo tema le ha e sono attive sulle pagine prodotto). Questo generalmente non è l'ideale per una sezione di commenti completa.
     - *Selezionando `displayFooter`:* Il blocco dei commenti apparirà nella sezione del footer del tuo negozio. Anche in questo caso, non è l'ideale per commenti specifici del prodotto.
   - **Valore consigliato:** `displayProductExtraContent` o un hook simile che posiziona i commenti direttamente nell'area del contenuto della pagina prodotto. Il nome esatto dell'hook potrebbe variare leggermente tra le versioni di PrestaShop o i temi, ma punta a uno che si integri bene con i dettagli del prodotto.
   - **Scenario / esempio del commerciante:** Vuoi che i commenti siano facilmente visibili quando un cliente sta esaminando un prodotto. Scegliere `displayProductExtraContent` assicura che faccia parte del flusso di informazioni principali del prodotto.
3. **Larghezza del Blocco Commenti Google+ (in pixel)**

   - **Cosa fa questa impostazione:** Questo campo di input ti consente di definire la larghezza fissa della sezione dei commenti di Google+ in pixel.
   - **Effetto della modifica di questa impostazione:**
     - *Impostando un valore in pixel specifico (es. `600`):* Il blocco dei commenti cercherà sempre di renderizzarsi a quella larghezza esatta. Se lo schermo è più piccolo, potrebbe andare in overflow o causare problemi di layout.
     - *Lasciando vuoto o impostando a `100%` (se consentito dal modulo, anche se tipicamente si aspettano pixel):* Il modulo potrebbe tentare di auto-regolarsi, ma per i commenti di Google+, spesso è prevista una larghezza fissa in pixel.
   - **Valore consigliato:** Un valore che si adatta bene all'area del contenuto principale della tua pagina prodotto, tipicamente da `600` a `800` pixel, a seconda del layout del tuo tema. Potrebbe essere necessario sperimentare per trovare la migliore vestibilità.
   - **Scenario / esempio del commerciante:** L'area del contenuto della tua pagina prodotto è larga 700px. Impostando questo a `650`px assicuri che il blocco dei commenti si adatti bene senza rompere il layout.
4. **Numero di Commenti da Visualizzare**

   - **Cosa fa questa impostazione:** Questo campo di input controlla quanti commenti vengono inizialmente caricati e visualizzati nella sezione dei commenti di Google+. Di solito, più commenti possono essere caricati dall'utente cliccando un pulsante "Carica altro" fornito da Google.
   - **Effetto della modifica di questa impostazione:**
     - *Impostando un numero basso (es. `5`):* Verranno mostrati inizialmente solo pochi commenti, rendendo il caricamento della pagina più veloce e meno ingombra. Gli utenti dovranno cliccare per vedere di più.
     - *Impostando un numero alto (es. `20`):* Più commenti saranno immediatamente visibili, il che può essere positivo per prodotti molto commentati ma potrebbe rendere la pagina più lunga.
   - **Valore consigliato:** Da `5` a `10`. Questo fornisce un buon equilibrio tra mostrare engagement e mantenere la pagina concisa.
   - **Scenario / esempio del commerciante:** Hai molti commenti su prodotti popolari. Impostando questo a `7` mostra un engagement sufficiente senza sopraffare il cliente con uno scorrimento molto lungo.

#### Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Visualizza Commenti Google+ sulla Pagina Prodotto | SÌ | Abilita/disabilita la sezione commenti sulle pagine prodotto. |
| Configurazione Modulo | Scegli Hook per Commenti Google+ | `displayProductExtraContent` | Determina dove appare il blocco commenti sulla pagina. |
| Configurazione Modulo | Larghezza del Blocco Commenti Google+ (in pixel) | `600` - `800` | Imposta la larghezza fissa della sezione commenti. Regola per adattarsi al tuo tema. |
| Configurazione Modulo | Numero di Commenti da Visualizzare | `5` - `10` | Controlla quanti commenti sono inizialmente visibili. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: La sezione commenti non appare sulle mie pagine prodotto dopo l'installazione.**
R:

1. **Controlla la configurazione del modulo:** Vai su **Moduli > Gestione moduli > Commenti Google+ > Configura**. Assicurati che "Visualizza Commenti Google+ sulla Pagina Prodotto" sia impostato su SÌ.
2. **Verifica la selezione dell'hook:** Assicurati che "Scegli Hook per Commenti Google+" sia impostato su un hook pertinente alla pagina prodotto come `displayProductExtraContent`. Se il tuo tema utilizza un hook personalizzato per il contenuto del prodotto, potresti dover selezionarlo o consultare lo sviluppatore del tuo tema.
3. **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty"). A volte, la cache di PrestaShop impedisce la visualizzazione immediata dei nuovi contenuti del modulo.
4. **Compatibilità del tema:** Alcuni temi altamente personalizzati potrebbero sovrascrivere gli hook standard di PrestaShop. Se il problema persiste, contatta lo sviluppatore del tuo tema o il supporto MyPresta.eu.

**D: La sezione commenti sembra troppo larga/stretta o rompe il mio layout.**
R:

1. **Regola l'impostazione della larghezza:** Nella configurazione del modulo, modifica l'impostazione "Larghezza del Blocco Commenti Google+ (in pixel)". Sperimenta con valori diversi (es. 600, 700, 800) finché non si adatta al layout della tua pagina prodotto.
2. **Controlla il CSS del tema:** Se la regolazione della larghezza non aiuta, il CSS del tuo tema potrebbe interferire. Potrebbe essere necessario un webmaster per ispezionare l'elemento e aggiungere CSS personalizzato al tuo tema per garantire una visualizzazione corretta.

**D: Posso moderare i commenti prima che appaiano?**
R: Il modulo Commenti Google+ utilizza il sistema di commenti di Google. Le capacità di moderazione sono tipicamente gestite all'interno della piattaforma Google stessa, non direttamente all'interno di PrestaShop. Dovresti controllare le politiche e gli strumenti di Google per la moderazione dei commenti relativi ai widget incorporati.

**D: I miei clienti hanno difficoltà a pubblicare commenti.**
R:

1. **Requisito dell'account Google:** Ricorda ai clienti che devono essere loggati con un account Google per pubblicare commenti.
2. **Problemi del browser:** Consiglia ai clienti di provare un browser diverso o di svuotare la cache e i cookie del loro browser.
3. **Stato del servizio Google:** Occasionalmente, i servizi Google potrebbero subire interruzioni temporanee. Controlla le pagine di stato di Google se molti utenti segnalano problemi contemporaneamente.

**D: Questo modulo funziona ancora da quando Google+ è stato chiuso?**
R: Sebbene Google+ come social network sia stato deprecato, Google fornisce ancora widget di commento incorporati che sfruttano gli account Google. Questo modulo si integra con quell'infrastruttura di commento di Google sottostante. Potrebbe non fornire il "boost SEO" diretto dai "+1" come faceva una volta, ma funziona ancora come un sistema di commenti basato su Google.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica per sviluppatori e webmaster che lavorano con il modulo Commenti Google+.

### 4.1 Panoramica dell'architettura

Il modulo `Commenti Google+` è un modulo PrestaShop semplice implementato principalmente nel suo file PHP principale (`google-comments.php`). Sfrutta la classe `Module` di PrestaShop e la classe `Configuration` per gestire le impostazioni. La sua funzionalità principale consiste nell'iniettare uno snippet JavaScript fornito da Google nel front-office, che poi renderizza il widget dei commenti. Non ci sono controller personalizzati, modelli o interazioni AJAX complesse all'interno del modulo stesso; si basa fortemente sullo script esterno di Google per la sua funzionalità front-end.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**: Nessuno. La visualizzazione front-office del modulo è gestita agganciandosi agli hook di visualizzazione standard di PrestaShop e renderizzando un template Smarty contenente il codice di incorporamento dei commenti di Google.
- **Controller Admin Back-Office**: Nessuno. Tutta la configurazione è gestita tramite il metodo `getContent()` nel file principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

- Nessuna classe personalizzata o definizione di `ObjectModel` è presente in questo modulo. Tutti i dati sono archiviati direttamente nella tabella `ps_configuration` di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

- Nessun file JavaScript personalizzato è incluso in questo modulo. La funzionalità del modulo si basa interamente sulla libreria JavaScript esterna di Google che incorpora.

### 4.5 Fogli di stile CSS (`views/css/`)

- Nessun file CSS personalizzato è incluso in questo modulo. Lo stile del widget dei commenti di Google è controllato dagli stili incorporati di Google. Qualsiasi stile personalizzato dovrebbe mirare all'iframe/elementi Google generati tramite override del tema (il che può essere difficile a causa delle restrizioni degli iframe cross-domain).

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo utilizza un singolo template Smarty per renderizzare il widget dei commenti di Google.

- **Template degli hook (`views/templates/hook/`)**:
  - `googlecomments.tpl`: Questo template viene renderizzato quando il modulo è agganciato. Contiene la struttura HTML per il widget dei commenti di Google, inclusi l'elemento `<div>` con gli attributi `data-href`, `data-width` e `data-num-comments`, e il tag `script` per caricare l'SDK JavaScript della piattaforma Google.
    - **Scopo:** Incorporare il widget dei commenti di Google nel front-office.
    - **Variabili utilizzate:**
      - `{$link->getModuleLink('googlecomments', 'ajax', array(), true)|escape:'htmlall':'UTF-8'}`: Questo è probabilmente un residuo o un segnaposto poiché il modulo non utilizza un controller AJAX. L'attributo `data-href` per i commenti di Google tipicamente punta all'URL canonico della pagina in cui vengono visualizzati i commenti (ad esempio, l'URL della pagina prodotto).
      - `{Configuration::get('GOOGLE_COMMENTS_WIDTH')}`: Recupera la larghezza configurata per il blocco dei commenti.
      - `{Configuration::get('GOOGLE_COMMENTS_NUM')}`: Recupera il numero di commenti da visualizzare configurato.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:
  Il modulo non crea tabelle di database personalizzate. Tutte le sue impostazioni di configurazione sono archiviate nella tabella `ps_configuration`:

  - `GOOGLE_COMMENTS_ENABLED`: Memorizza `1` (abilitato) o `0` (disabilitato) per la visualizzazione dei commenti.
  - `GOOGLE_COMMENTS_HOOK`: Memorizza il nome dell'hook selezionato (es. `displayProductExtraContent`).
  - `GOOGLE_COMMENTS_WIDTH`: Memorizza la larghezza del blocco commenti in pixel.
  - `GOOGLE_COMMENTS_NUM`: Memorizza il numero di commenti da visualizzare.
- **Tabella degli hook registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Utilizzato per registrare risorse (anche se questo modulo non lo usa per questo, è un hook comune). |
| `displayProductExtraContent` | All'interno dell'area del contenuto principale di una pagina prodotto, spesso in una scheda o sotto la descrizione. | **Hook primario per la visualizzazione del blocco commenti sulle pagine prodotto.** |
| `displayLeftColumn` | Nella barra laterale sinistra del negozio. | Hook opzionale per la visualizzazione del blocco commenti (meno comune per commenti completi). |
| `displayRightColumn` | Nella barra laterale destra del negozio. | Hook opzionale per la visualizzazione del blocco commenti (meno comune per commenti completi). |
| `displayFooter` | Nella sezione del footer del negozio. | Hook opzionale per la visualizzazione del blocco commenti (meno comune per commenti completi). |
| `actionFrontControllerSetMedia` | Prima che il front controller renderizzi la pagina, consentendo ai moduli di aggiungere JS/CSS. | Utilizzato per aggiungere l'SDK JavaScript della piattaforma Google alla pagina. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo Commenti Google+, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a fornire assistenza e garantire il buon funzionamento dei vostri moduli.
