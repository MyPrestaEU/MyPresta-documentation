---
title: "Sticky Cart Bar FREE - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Sticky Cart Bar FREE di MyPresta.eu."
sidebar:
  label: "Sticky Cart Bar FREE - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Sticky Cart Bar FREE su MyPresta.eu](https://mypresta.eu/modules/front-office-features/sticky-cart-bar-free.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/sticky-cart-bar-free/)
>
> ---


# Sticky Cart Bar FREE

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Sticky Cart Bar FREE)

Questa è la schermata di configurazione principale dove controlli come la barra del carrello "sticky" si comporta e appare sulle tue pagine prodotto.

#### **Abilita Sticky Cart Bar**

- **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare l'intera funzionalità della barra del carrello "sticky" per il tuo negozio.
- **Effetto della modifica di questa impostazione:**
  - *Quando abilitato (SÌ):* La barra del carrello "sticky" apparirà sulle pagine prodotto secondo le tue altre impostazioni quando i clienti scorrono oltre il pulsante principale "Aggiungi al carrello".
  - *Quando disabilitato (NO):* La barra del carrello "sticky" non apparirà su nessuna pagina prodotto, disattivando di fatto il modulo.
- **Valore consigliato:** SÌ (per utilizzare i vantaggi del modulo).
- **Scenario / esempio del commerciante:** Se stai testando il modulo o vuoi disabilitarlo temporaneamente senza disinstallarlo, impostalo su NO. Per il funzionamento in tempo reale, dovrebbe essere SÌ.

#### **Posizione della Sticky Cart Bar**

- **Cosa fa questa impostazione:** Determina dove la barra "sticky" si "attaccherà" sullo schermo del cliente – in alto o in basso.
- **Effetto della modifica di questa impostazione:**
  - *Quando impostato su "In alto":* La barra "sticky" apparirà nella parte superiore della finestra del browser, sotto l'intestazione.
  - *Quando impostato su "In basso":* La barra "sticky" apparirà nella parte inferiore della finestra del browser, sopra il piè di pagina.
- **Valore consigliato:** "In basso" (spesso meno invasivo, in quanto non copre la navigazione principale o il logo). Tuttavia, "In alto" può essere più prominente. Prova entrambi per vedere cosa funziona meglio per il tuo tema e il tuo pubblico.
- **Scenario / esempio del commerciante:** Se il tuo negozio ha un'intestazione molto trafficata o un menu fisso in alto, posizionare la barra "sticky" "In basso" potrebbe prevenire l'ingombro visivo. Se desideri la massima visibilità per il pulsante "Aggiungi al carrello", "In alto" potrebbe essere preferibile.

#### **Visualizza su dispositivi mobili**

- **Cosa fa questa impostazione:** Controlla se la barra del carrello "sticky" viene mostrata ai clienti che navigano nel tuo negozio su smartphone o altri dispositivi mobili.
- **Effetto della modifica di questa impostazione:**
  - *Quando abilitato (SÌ):* La barra del carrello "sticky" sarà attiva e visibile sulle pagine prodotto mobili.
  - *Quando disabilitato (NO):* La barra del carrello "sticky" non apparirà sui dispositivi mobili, solo su desktop/tablet.
- **Valore consigliato:** SÌ (Gli utenti mobili scorrono molto, e questa funzione è molto vantaggiosa per loro).
- **Scenario / esempio del commerciante:** Dato lo spazio limitato dello schermo sui dispositivi mobili, mantenere visibile il pulsante "Aggiungi al carrello" è ancora più critico. Disabilitalo solo se riscontri specifici conflitti di layout con il tuo tema mobile.

#### **Visualizza su dispositivi desktop**

- **Cosa fa questa impostazione:** Controlla se la barra del carrello "sticky" viene mostrata ai clienti che navigano nel tuo negozio su computer desktop o schermi tablet più grandi.
- **Effetto della modifica di questa impostazione:**
  - *Quando abilitato (SÌ):* La barra del carrello "sticky" sarà attiva e visibile sulle pagine prodotto desktop.
  - *Quando disabilitato (NO):* La barra del carrello "sticky" non apparirà sui dispositivi desktop, solo su mobile (se abilitato).
- **Valore consigliato:** SÌ (Anche su desktop, le pagine prodotto lunghe beneficiano di questa funzione).
- **Scenario / esempio del commerciante:** La maggior parte dei negozi vorrà che questa opzione sia abilitata per tutti i tipi di dispositivi per massimizzare il potenziale di conversione.

#### **Nascondi pulsante originale "Aggiungi al carrello"**

- **Cosa fa questa impostazione:** Questa opzione ti consente di nascondere il pulsante originale "Aggiungi al carrello" sulla pagina prodotto una volta che appare la barra "sticky".
- **Effetto della modifica di questa impostazione:**
  - *Quando abilitato (SÌ):* Quando la barra "sticky" è visibile, il pulsante originale "Aggiungi al carrello" sulla pagina prodotto sarà nascosto. Questo può ridurre la ridondanza visiva.
  - *Quando disabilitato (NO):* Sia il pulsante "Aggiungi al carrello" della barra "sticky" che il pulsante originale "Aggiungi al carrello" saranno visibili contemporaneamente (quando l'originale è in vista).
- **Valore consigliato:** NO (Generalmente, è più sicuro mantenere visibile il pulsante originale se è nella viewport, poiché alcuni clienti potrebbero preferirlo. Nasconderlo potrebbe causare confusione se la barra "sticky" scompare rapidamente).
- **Scenario / esempio del commerciante:** Se trovi i doppi pulsanti "Aggiungi al carrello" visivamente distraenti o confusi quando la barra "sticky" è attiva, potresti abilitare questa opzione. Altrimenti, lasciala disabilitata.

#### **Compatibilità tema**

- **Cosa fa questa impostazione:** Questa impostazione aiuta il modulo ad adattare il suo stile e comportamento a diversi temi PrestaShop, in particolare Classic e Hummingbird (il tema predefinito per PrestaShop 8+).
- **Effetto della modifica di questa impostazione:**
  - *Quando impostato su "Classic":* Il modulo caricherà CSS e JavaScript ottimizzati per il tema PrestaShop Classic e i temi basati su di esso.
  - *Quando impostato su "Hummingbird":* Il modulo caricherà CSS e JavaScript ottimizzati per il tema PrestaShop Hummingbird (PrestaShop 8.x e 9.x predefinito) e i temi basati su di esso.
- **Valore consigliato:** Seleziona il tema che il tuo negozio sta attualmente utilizzando. Se sei su PrestaShop 8.x o 9.x, è probabile che sia "Hummingbird". Se sei su PrestaShop 1.7.x e utilizzi il tema predefinito, è "Classic". Se utilizzi un tema personalizzato, prova entrambi per vedere quale si integra meglio.
- **Scenario / esempio del commerciante:** Se il tuo negozio è su PrestaShop 8.1 e selezioni "Classic", la barra "sticky" potrebbe non apparire o funzionare correttamente. Abbina sempre questa impostazione al tuo tema attivo.

#### **Anteprima versione Pro**

- **Cosa fa questa impostazione:** Questa sezione è un'area promozionale per il modulo "Sticky Cart Bar PRO", che offre funzionalità avanzate non disponibili nella versione FREE. Non influisce sulla funzionalità del modulo FREE.
- **Effetto della modifica di questa impostazione:** Nessun effetto diretto sul comportamento del modulo FREE. Fornisce informazioni sull'aggiornamento.
- **Valore consigliato:** N/A (Solo informativo).
- **Scenario / esempio del commerciante:** Se trovi il modulo FREE vantaggioso e hai bisogno di maggiore controllo sul targeting, sul design o su esclusioni di prodotti specifici, puoi rivedere le funzionalità della versione PRO qui.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Abilita Sticky Cart Bar | SÌ | Interruttore principale per il modulo. SÌ attiva la barra "sticky". |
| Configurazione modulo | Posizione della Sticky Cart Bar | In basso | Determina se la barra si attacca in alto o in basso nello schermo. |
| Configurazione modulo | Visualizza su dispositivi mobili | SÌ | Controlla la visibilità su smartphone/tablet. SÌ è consigliato. |
| Configurazione modulo | Visualizza su dispositivi desktop | SÌ | Controlla la visibilità sui computer desktop. SÌ è consigliato. |
| Configurazione modulo | Nascondi pulsante originale "Aggiungi al carrello" | NO | Nasconde il pulsante originale quando la barra "sticky" è attiva. NO è generalmente più sicuro. |
| Configurazione modulo | Compatibilità tema | Hummingbird (per PS 8/9) | Assicura lo stile e la funzionalità corretti per il tuo tema attivo. Abbina il tuo tema. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: La barra del carrello "sticky" non appare sulle mie pagine prodotto.**
R:

- **Controlla "Abilita Sticky Cart Bar"**: Assicurati che questa impostazione sia impostata su SÌ nella configurazione del modulo.
- **Controlla "Compatibilità tema"**: Assicurati di aver selezionato il tema corretto (Classic o Hummingbird) che corrisponde al tema attivo del tuo negozio. Una selezione errata può impedire il caricamento della barra.
- **Svuota la cache**: Vai su **Parametri avanzati > Prestazioni** nel tuo back office PrestaShop e clicca su "Svuota la cache" (o "Svuota la cache Smarty" nelle versioni precedenti). A volte, i vecchi file di cache impediscono la visualizzazione delle nuove modifiche del modulo.
- **Scorri oltre il pulsante originale**: Ricorda, la barra appare solo quando scorri oltre il pulsante originale "Aggiungi al carrello". Assicurati di scorrere abbastanza in basso nella pagina.
- **Controlla le impostazioni del dispositivo**: Assicurati che "Visualizza su dispositivi mobili" e/o "Visualizza su dispositivi desktop" siano abilitati per il dispositivo su cui stai testando.

**D2: La barra del carrello "sticky" appare strana o disallineata con il mio tema personalizzato.**
R:

- **Compatibilità tema**: Ricontrolla di aver selezionato l'opzione "Compatibilità tema" corretta nelle impostazioni del modulo. Se hai un tema altamente personalizzato, potrebbe comportarsi in modo diverso. Prova a passare tra "Classic" e "Hummingbird" per vedere se uno funziona meglio.
- **CSS personalizzato (necessario sviluppatore)**: Se il problema persiste, il tuo tema personalizzato potrebbe avere stili CSS in conflitto. Uno sviluppatore web può ispezionare la pagina utilizzando gli strumenti di sviluppo del browser e scrivere alcune righe di CSS personalizzato per regolare l'aspetto della barra "sticky". Questo di solito comporta l'override degli stili esistenti nel file `custom.css` del tuo tema.

**D3: Il pulsante "Aggiungi al carrello" nella barra "sticky" non funziona.**
R:

- **Svuota la cache**: Come per i problemi di visualizzazione, svuotare la cache di PrestaShop (**Parametri avanzati > Prestazioni**) può risolvere problemi relativi a JavaScript.
- **Compatibilità tema**: Assicurati che sia selezionato il tema corretto. Il JavaScript potrebbe non inizializzarsi correttamente se viene scelto il tema sbagliato.
- **Errori della console del browser (necessario sviluppatore)**: Chiedi al tuo sviluppatore web di controllare la console JavaScript del browser per eventuali errori. I conflitti con altri moduli o il JavaScript del tema a volte possono impedire il funzionamento del pulsante.

**D4: Posso personalizzare i colori o il contenuto della barra "sticky"?**
R:

- La versione FREE del modulo offre opzioni di stile limitate (principalmente l'adattamento al tuo tema). Per personalizzazioni avanzate come la modifica di colori, font, l'aggiunta di testo personalizzato o un controllo più granulare sulle informazioni visualizzate, dovresti tipicamente eseguire l'aggiornamento al modulo **Sticky Cart Bar PRO**.
- Per piccole modifiche visive nella versione FREE, uno sviluppatore web può utilizzare CSS personalizzato per sovrascrivere gli stili predefiniti.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo Sticky Cart Bar FREE segue un'architettura standard dei moduli PrestaShop, sfruttando principalmente la classe `Module` per l'installazione, la disinstallazione e la configurazione. Si integra con il front-office tramite hook, iniettando dinamicamente una barra "sticky" basata sul comportamento di scorrimento dell'utente. Il modulo utilizza una combinazione di template Smarty per la struttura, CSS per lo stile e JavaScript per la funzionalità "sticky" e l'interazione con il pulsante principale "Aggiungi al carrello". La compatibilità con diversi temi PrestaShop (Classic vs. Hummingbird) è gestita caricando risorse specifiche per il tema.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller Front-Office o Back-Office Admin personalizzati. Tutta la configurazione è gestita tramite il metodo `getContent()` del modulo principale.

### 4.3 Classi e modelli principali (`classes/`)

- `stickycartbarfree/classes/index.php`:
  - Questo è tipicamente un file vuoto utilizzato per prevenire l'elenco delle directory, una pratica di sicurezza comune nei moduli PrestaShop. Non contiene codice funzionale.
- `stickycartbarfree/classes/ScbfCompatibility.php`:
  - **Nome classe**: `ScbfCompatibility`
  - **Classe genitore**: Nessuna (classe utility standalone)
  - **Responsabilità**: Questa classe probabilmente contiene metodi helper statici per gestire le differenze di compatibilità tra varie versioni o temi di PrestaShop. Potrebbe astrarre le differenze nel modo in cui i dati del prodotto vengono recuperati o come le risorse vengono registrate, garantendo che il modulo funzioni in tutti gli ambienti supportati. Non interagisce direttamente con una tabella di database specifica, ma potrebbe interrogare `ps_configuration` per informazioni sul tema.
  - **Metodi pubblici chiave**: Probabilmente metodi statici per controllare il contesto del tema, la versione di PrestaShop o recuperare i valori di configurazione in modo compatibile.

### 4.4 Risorse JavaScript (`views/js/`)

- `stickycartbarfree/views/js/front.js`:
  - **Ambito**: Front-office.
  - **Descrizione**: Questo è il file JavaScript principale responsabile del comportamento "sticky" della barra del carrello.
  - **Funzionalità**:
    - **Listener di eventi**: Si lega all'evento `scroll` sulla finestra per rilevare quando l'utente scorre.
    - **Manipolazione del DOM**:
      - Calcola la posizione del pulsante originale "Aggiungi al carrello" (`#add_to_cart` o selettore simile).
      - Monitora la posizione di scorrimento rispetto al pulsante originale.
      - Aggiunge/rimuove una classe CSS (es. `is-visible`) al contenitore della barra del carrello "sticky" (`#sticky-cart-bar`) per mostrarla o nasconderla.
      - Potenzialmente nasconde il pulsante originale "Aggiungi al carrello" se l'impostazione del modulo corrispondente è abilitata.
    - **Interazione**: Gestisce i clic sul pulsante "Aggiungi al carrello" all'interno della barra "sticky", probabilmente mimando il comportamento del pulsante originale (es. invio del modulo prodotto, esecuzione di una chiamata AJAX per aggiungere al carrello).
    - **Reattività**: Può includere logica per rivalutare le posizioni sugli eventi `resize`.
    - **Eventi PrestaShop**: Probabilmente utilizza `prestashop.on('updateProduct', ...)` o eventi simili per aggiornare il contenuto della barra "sticky" (prezzo, quantità, attributi) quando le opzioni del prodotto vengono modificate sulla pagina.

### 4.5 Fogli di stile CSS (`views/css/`)

- `stickycartbarfree/views/css/admin-config.css`:
  - **Ambito**: Stile del modulo di amministrazione del Back-office.
  - **Descrizione**: Contiene stili specifici per la pagina di configurazione del modulo nel back office di PrestaShop, garantendo un'interfaccia di amministrazione coerente e facile da usare.
  - **Componenti UI principali**: Stili elementi del modulo, etichette, pulsanti e potenzialmente elementi di layout specifici all'interno dell'output di `getContent()`.
- `stickycartbarfree/views/css/admin-pro-teaser.css`:
  - **Ambito**: Stile del modulo di amministrazione del Back-office.
  - **Descrizione**: Stili per il contenuto promozionale relativo alla versione PRO del modulo visualizzato nella pagina di configurazione.
  - **Componenti UI principali**: Stili caselle teaser, pulsanti di aggiornamento, elenchi di funzionalità e immagini di anteprima per la versione PRO.
- `stickycartbarfree/views/css/front-classic.css`:
  - **Ambito**: Stile del cliente Front-office (tema Classic).
  - **Descrizione**: Fornisce regolazioni di stile specifiche per la barra del carrello "sticky" quando è selezionata l'opzione di compatibilità del tema "Classic". Ciò garantisce che la barra si integri visivamente con il design del tema Classic.
  - **Selettori di classe CSS chiave**: Mira agli elementi all'interno di `sticky-cart-bar` per corrispondere a font, colori, spaziatura e stili dei pulsanti del tema Classic.
- `stickycartbarfree/views/css/front-hummingbird.css`:
  - **Ambito**: Stile del cliente Front-office (tema Hummingbird).
  - **Descrizione**: Fornisce regolazioni di stile specifiche per la barra del carrello "sticky" quando è selezionata l'opzione di compatibilità del tema "Hummingbird". Ciò garantisce che la barra si integri visivamente con il tema predefinito di PrestaShop 8.x/9.x.
  - **Selettori di classe CSS chiave**: Mira agli elementi all'interno di `sticky-cart-bar` per corrispondere a font, colori, spaziatura e stili dei pulsanti del tema Hummingbird.
- `stickycartbarfree/views/css/front.css`:
  - **Ambito**: Stile del cliente Front-office (generale).
  - **Descrizione**: Contiene gli stili di base, comuni per la barra del carrello "sticky" che si applicano indipendentemente dalla compatibilità del tema selezionata. Ciò include il posizionamento, la visibilità e la reattività principali.
  - **Selettori di classe CSS chiave**: Definisce le proprietà di `#sticky-cart-bar` come `position: fixed`, `z-index`, `width`, `padding`, `background-color` e media query reattive.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template hook (`views/templates/hook/`)**:

  - `stickycartbarfree/views/templates/hook/sticky-cart-bar-classic.tpl`: Renderizzato quando è selezionata la compatibilità del tema "Classic". Contiene la struttura principale per la barra "sticky", adattata alle aspettative HTML e CSS del tema Classic.
  - `stickycartbarfree/views/templates/hook/sticky-cart-bar-hummingbird.tpl`: Renderizzato quando è selezionata la compatibilità del tema "Hummingbird". Contiene la struttura principale per la barra "sticky", adattata alle aspettative HTML e CSS del tema Hummingbird.
  - `stickycartbarfree/views/templates/hook/sticky-cart-bar-inner.tpl`: Questo template probabilmente contiene il contenuto principale della barra "sticky" (nome prodotto, prezzo, input quantità, pulsante aggiungi al carrello). È probabilmente incluso da `sticky-cart-bar-classic.tpl` e `sticky-cart-bar-hummingbird.tpl` per evitare la duplicazione del codice.
  - `stickycartbarfree/views/templates/hook/sticky-cart-bar.tpl`: Questo potrebbe essere un template wrapper o un fallback, oppure potrebbe essere il punto di ingresso principale che include condizionalmente `sticky-cart-bar-classic.tpl` o `sticky-cart-bar-hummingbird.tpl` in base alla configurazione.
  - **Scopo**: Questi template sono tipicamente agganciati a `displayFooter` o `displayBeforeBodyClosingTag` per garantire che l'HTML della barra "sticky" sia presente sulle pagine prodotto. Producono la struttura HTML per la barra "sticky", popolata con i dati del prodotto passati dal modulo.
- **Template admin (`views/templates/admin/`)**:

  - `stickycartbarfree/views/templates/admin/configure.tpl`: Questo è il template principale per la pagina di configurazione del modulo nel Back Office. Renderizza tutte le impostazioni, i campi di input e le opzioni definite nel metodo `getContent()` del modulo.
  - `stickycartbarfree/views/templates/admin/pro-teaser-intro.tpl`: Renderizza la parte introduttiva dell'anteprima della versione PRO nella pagina di configurazione.
  - `stickycartbarfree/views/templates/admin/pro-teaser-preview.tpl`: Renderizza un'anteprima o una rappresentazione visiva delle funzionalità della versione PRO.
  - `stickycartbarfree/views/templates/admin/pro-teaser.tpl`: Il template principale per la sezione dell'anteprima della versione PRO, probabilmente includendo i template di introduzione e anteprima.
  - **Scopo**: Questi template forniscono l'interfaccia utente per le impostazioni del modulo e il contenuto promozionale all'interno del Back Office di PrestaShop.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Questo modulo non crea tabelle SQL personalizzate.
  - Le impostazioni di configurazione sono memorizzate nella tabella standard `ps_configuration` di PrestaShop, con chiavi tipicamente prefissate da `SCBF_` (es. `SCBF_ENABLE`, `SCBF_POSITION`).
- **Tabella degli hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Utilizzato per registrare risorse CSS e JavaScript (`front.js`, `front.css`, CSS specifici del tema) per il front-office. |
| `displayFooter` | Prima del tag di chiusura `</body>` su ogni pagina. | Utilizzato per iniettare la struttura HTML principale della barra del carrello "sticky" (`sticky-cart-bar.tpl` o le sue varianti) nella pagina. |
| `actionFrontControllerSetMedia` | Dopo che i media (CSS/JS) sono stati impostati dal controller frontale. | Hook alternativo per la registrazione delle risorse, garantendo che vengano caricate correttamente. |
| `actionProductUpdate` | Dopo che un prodotto viene aggiornato nel back office. | (Probabilmente non utilizzato nella versione FREE, ma comune per i moduli che devono svuotare la cache o re-indicizzare i dati del prodotto). |
| `actionCartUpdateQuantity` | Quando la quantità di un prodotto viene aggiornata nel carrello. | (Probabilmente non utilizzato nella versione FREE, ma potrebbe essere utilizzato per aggiornare il selettore di quantità della barra "sticky" se fosse più interattivo). |
| `actionAjaxDieProduct` | Quando una richiesta AJAX relativa ai dati del prodotto fallisce. | (Potrebbe essere utilizzato per il debug o interazioni AJAX specifiche). |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e per esplorare le funzionalità avanzate disponibili nella versione PRO del modulo, visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda riguardante il modulo Sticky Cart Bar FREE.
