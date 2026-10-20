---
title: "Sostituisci aggiungi al carrello con link a pagina - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Sostituisci aggiungi al carrello con link a pagina' di MyPresta.eu."
sidebar:
  label: "Sostituisci aggiungi al carrello con link a pagina - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Replace add to cart with link to page su MyPresta.eu](https://mypresta.eu/modules/front-office-features/replace-add-to-cart-with-link-to-page.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/replace-add-to-cart-with-link-to-page/)
>
> ---


# Sostituisci aggiungi al carrello con link a pagina

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata principale dove controlli il comportamento globale del modulo.

- **Abilitato**

  - **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare la funzionalità del modulo in tutto il tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il modulo inizierà a sostituire i pulsanti "Aggiungi al carrello" con link personalizzati in base alle tue impostazioni specifiche del prodotto e ad altre configurazioni globali.
    - *Quando disabilitato:* Il modulo sarà inattivo e tutti i pulsanti "Aggiungi al carrello" torneranno al loro comportamento predefinito di PrestaShop.
  - **Valore consigliato:** SÌ (per attivare il modulo).
  - **Scenario / esempio del commerciante:** Se stai testando il modulo o desideri disabilitare temporaneamente la sua funzionalità senza disinstallarlo, puoi impostarlo su NO. Per un uso attivo, dovrebbe essere SÌ.
- **Testo del pulsante**

  - **Cosa fa questa impostazione:** Definisce il testo che apparirà sul pulsante personalizzato, sostituendo "Aggiungi al carrello". Questo testo può essere tradotto in diverse lingue.
  - **Effetto della modifica di questa impostazione:** Il testo sul pulsante cambierà al valore specificato.
  - **Valore consigliato:** Qualcosa di descrittivo come "Scopri di più", "Richiedi preventivo", "Visualizza dettagli" o "Visita il sito del partner".
  - **Scenario / esempio del commerciante:** Se stai collegando a un sito esterno per maggiori informazioni, potresti impostarlo su "Scopri di più". Se stai indirizzando i clienti a un modulo di preventivo, "Richiedi preventivo" sarebbe appropriato.
- **Nascondi campo quantità**

  - **Cosa fa questa impostazione:** Controlla se il campo di input della quantità (dove i clienti selezionano quanti articoli aggiungere) è visibile sulle pagine prodotto quando il modulo è attivo.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il selettore di quantità verrà nascosto, poiché non è rilevante quando il pulsante reindirizza invece di aggiungere al carrello.
    - *Quando disabilitato:* Il selettore di quantità rimarrà visibile, il che potrebbe essere confuso se il pulsante non aggiunge al carrello.
  - **Valore consigliato:** SÌ.
  - **Scenario / esempio del commerciante:** Poiché il pulsante non aggiunge più al carrello, di solito non è necessario un campo quantità. Nasconderlo semplifica l'interfaccia ed evita confusione.
- **Classe CSS del pulsante aggiungi al carrello sulla pagina prodotto**

  - **Cosa fa questa impostazione:** Ti consente di specificare una classe CSS personalizzata per il pulsante di sostituzione sulla pagina prodotto. Questo è utile per stilizzare il pulsante in modo che corrisponda al tuo tema o per farlo risaltare.
  - **Effetto della modifica di questa impostazione:** Il pulsante erediterà gli stili definiti da questa classe CSS nel foglio di stile del tuo tema.
  - **Valore consigliato:** Lascia vuoto se lo stile predefinito del pulsante del tuo tema è accettabile, oppure usa una classe come `btn btn-primary` o `my-custom-button` se hai stili specifici.
  - **Scenario / esempio del commerciante:** Se il tuo tema usa `btn-success` per i pulsanti di azione principali, potresti inserire `btn-success` qui per rendere il tuo pulsante personalizzato verde e prominente.
- **Classe CSS quantità**

  - **Cosa fa questa impostazione:** Ti consente di specificare una classe CSS per il campo di input della quantità sulla pagina prodotto. Questo è principalmente per la stilizzazione avanzata o se hai bisogno di mirare al campo quantità con CSS personalizzato.
  - **Effetto della modifica di questa impostazione:** Il campo di input della quantità riceverà questa classe CSS.
  - **Valore consigliato:** Lascia vuoto a meno che tu non abbia una specifica esigenza di stile.
  - **Scenario / esempio del commerciante:** Uno sviluppatore potrebbe usarlo per applicare una larghezza o una spaziatura specifica al campo quantità se non è nascosto.
- **Applica modulo all'elenco dei prodotti**

  - **Cosa fa questa impostazione:** Determina se la funzionalità del modulo (sostituire "Aggiungi al carrello" con un link personalizzato) si applica anche ai pulsanti prodotto visualizzati negli elenchi (es. pagine di categoria, risultati di ricerca, prodotti in evidenza nella homepage).
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I pulsanti "Aggiungi al carrello" negli elenchi prodotti verranno anch'essi sostituiti dal link personalizzato.
    - *Quando disabilitato:* Solo il pulsante "Aggiungi al carrello" della pagina prodotto sarà interessato; i pulsanti degli elenchi prodotti manterranno il loro comportamento predefinito.
  - **Valore consigliato:** SÌ, per coerenza in tutto il tuo negozio, specialmente se il link personalizzato è una parte critica del tuo imbuto di vendita.
  - **Scenario / esempio del commerciante:** Se tutti i prodotti che richiedono questo link personalizzato sono servizi che necessitano di un preventivo, vorresti che questo fosse abilitato in modo che i clienti non cerchino di "aggiungere al carrello" da una pagina di categoria.
- **Classe CSS dell'elemento con prodotto**

  - **Cosa fa questa impostazione:** Questa è un'impostazione tecnica per aiutare il modulo a identificare il contenitore principale per un prodotto in una visualizzazione elenco. È fondamentale che il modulo trovi e modifichi correttamente il pulsante "Aggiungi al carrello" all'interno di ogni elemento prodotto.
  - **Effetto della modifica di questa impostazione:** Se errata, il modulo potrebbe non riuscire ad applicare le sue modifiche agli elementi dell'elenco prodotti.
  - **Valore consigliato:** Questo dipende molto dal tema. I valori comuni includono `product-miniature`, `product-container`, `product-item`. Potrebbe essere necessario ispezionare l'HTML del tuo tema per trovare la classe corretta.
  - **Scenario / esempio del commerciante:** Se il tuo tema usa `<div class="product-card">` per ogni prodotto in un elenco, dovresti inserire `product-card` qui.
- **Classe CSS di** (Questo probabilmente si riferisce al pulsante "Aggiungi al carrello" stesso all'interno di un elemento dell'elenco prodotti)

  - **Cosa fa questa impostazione:** Specifica la classe CSS del pulsante "Aggiungi al carrello" all'interno degli elementi dell'elenco prodotti. Questo aiuta il modulo a mirare al pulsante corretto per la sostituzione.
  - **Effetto della modifica di questa impostazione:** Se errata, il modulo potrebbe non sostituire il pulsante "Aggiungi al carrello" negli elenchi prodotti.
  - **Valore consigliato:** Questo dipende molto dal tema. I valori comuni includono `add-to-cart`, `product-add-to-cart`, `btn-primary`. Ispeziona l'HTML del tuo tema.
  - **Scenario / esempio del commerciante:** Se il pulsante "Aggiungi al carrello" del tuo tema negli elenchi ha la classe `btn-add-to-cart`, dovresti inserirla qui.
- **Classe CSS dell'input quantità nell'elenco dei prodotti**

  - **Cosa fa questa impostazione:** Simile all'impostazione della pagina prodotto, questa ti consente di specificare la classe CSS per il campo di input della quantità quando i prodotti sono visualizzati in un elenco. Questo viene utilizzato per nasconderlo se `Nascondi campo quantità` è abilitato.
  - **Effetto della modifica di questa impostazione:** Se errata, il campo quantità potrebbe rimanere visibile negli elenchi prodotti anche se hai scelto di nasconderlo.
  - **Valore consigliato:** Lascia vuoto a meno che tu non abbia una specifica esigenza di stile o se il campo quantità non viene nascosto correttamente. Ispeziona l'HTML del tuo tema.
  - **Scenario / esempio del commerciante:** Se il tuo tema usa `product-quantity-input` per il campo quantità negli elenchi, dovresti inserirlo qui.
- **Nascondi tooltip sul pulsante**

  - **Cosa fa questa impostazione:** Controlla se il tooltip predefinito di PrestaShop (spesso che mostra "Aggiungi al carrello" o simile) appare quando si passa il mouse sul pulsante personalizzato.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il tooltip verrà nascosto, prevenendo messaggi potenzialmente confusi.
    - *Quando disabilitato:* Il tooltip predefinito potrebbe comunque apparire, il che potrebbe entrare in conflitto con lo scopo del pulsante personalizzato.
  - **Valore consigliato:** SÌ.
  - **Scenario / esempio del commerciante:** Se il tuo pulsante personalizzato dice "Richiedi preventivo", non vuoi che appaia un tooltip che dice "Aggiungi al carrello". Nasconderlo garantisce un messaggio chiaro.
- **Aggiungi rel="nofollow"**

  - **Cosa fa questa impostazione:** Aggiunge l'attributo `rel="nofollow"` al link personalizzato. Questo indica ai motori di ricerca di non seguire il link e di non passare alcun "link juice" alla destinazione.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il link avrà `rel="nofollow"`, utile per i link esterni che non vuoi sostenere o per i link interni non critici per la SEO (es. pagine di login).
    - *Quando disabilitato:* Il link sarà un link standard seguito.
  - **Valore consigliato:** SÌ per i link esterni, specialmente i link di affiliazione o i link a siti che non controlli completamente. NO per i link interni all'interno del tuo sito che vuoi che i motori di ricerca scansionino.
  - **Scenario / esempio del commerciante:** Se stai collegando al sito web di un partner affiliato, abilitare `nofollow` è una buona pratica per evitare potenziali penalità SEO e per indicare chiaramente che si tratta di un link sponsorizzato o esterno.
- **Apri link in nuova finestra (scheda)**

  - **Cosa fa questa impostazione:** Determina se il link personalizzato si apre nella stessa scheda del browser o in una nuova.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il link si aprirà in una nuova scheda del browser, mantenendo la pagina del tuo negozio aperta nella scheda originale.
    - *Quando disabilitato:* Il link si aprirà nella stessa scheda, allontanando il cliente dal tuo negozio.
  - **Valore consigliato:** SÌ per i link esterni, per mantenere i clienti sul tuo sito. NO per i link interni dove vuoi che il cliente navighi all'interno del tuo negozio.
  - **Scenario / esempio del commerciante:** Se stai indirizzando i clienti a un sito partner esterno, l'apertura in una nuova scheda è generalmente migliore in modo che possano facilmente tornare alla pagina del tuo prodotto.
- **Visibilità del modulo per i prodotti selezionati**

  - **Cosa fa questa impostazione:** Questa è un'impostazione cruciale che definisce *quali* prodotti avranno il loro pulsante "Aggiungi al carrello" sostituito. Funziona in combinazione con le impostazioni specifiche del prodotto che troverai nella pagina di modifica di ogni prodotto.
  - **Effetto della modifica di questa impostazione:**
    - *Abilitato:* Il modulo si applicherà solo ai prodotti per i quali hai esplicitamente definito un URL personalizzato nelle loro impostazioni prodotto.
    - *Disabilitato:* Il modulo non si applicherà a nessun prodotto, indipendentemente dalle loro impostazioni individuali.
  - **Valore consigliato:** Abilitato. Questo ti consente di applicare selettivamente la funzione di link personalizzato a prodotti specifici.
  - **Scenario / esempio del commerciante:** Vuoi sostituire il pulsante "Aggiungi al carrello" solo per i tuoi mobili su misura, non per gli accessori standard. Abiliteresti questa impostazione, quindi andresti a ogni prodotto di arredamento e imposteresti il suo URL personalizzato.

#### Impostazioni specifiche del prodotto (Back Office > Catalogo > Prodotti > Modifica Prodotto > Scheda Moduli)

Una volta installato e abilitato il modulo, troverai nuove impostazioni durante la modifica dei singoli prodotti.

- **Campo URL prodotto**
  - **Cosa fa questa impostazione:** Qui inserisci l'URL specifico a cui il pulsante "Aggiungi al carrello" per *questo particolare prodotto* reindirizzerà.
  - **Effetto della modifica di questa impostazione:** Quando un cliente clicca sul pulsante personalizzato sulla pagina di questo prodotto (o in un elenco, se abilitato), verrà portato a questo URL.
  - **Valore consigliato:** Un URL completo e valido (es. `https://example.com/richiedi-un-preventivo` o `/contattaci`).
  - **Scenario / esempio del commerciante:** Per un prodotto "Servizio di progettazione personalizzata", potresti inserire `https://tuonegozio.com/contattaci?subject=Richiesta%20Progettazione%20Personalizzata` qui.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### AdminAtcurlSearchController (Back Office > Moduli > Sostituisci aggiungi al carrello con link a pagina > Configura > Scheda "Prodotti selezionati")

Questa schermata fornisce un modo centralizzato per gestire e visualizzare quali prodotti hanno URL personalizzati configurati.

- **Nome schermata e posizione nel menu:** Si accede a questa schermata navigando in **Moduli > Gestione moduli**, trovando "Sostituisci aggiungi al carrello con link a pagina", cliccando su "Configura" e quindi selezionando la scheda "Prodotti selezionati" (o simile, a seconda della versione del modulo).
- **Azioni e impostazioni disponibili:** Questa schermata di solito visualizza una griglia o un elenco di prodotti che attualmente hanno un URL personalizzato definito.
  - **Colonne:** Di solito vedrai colonne come ID prodotto, Nome prodotto e l'URL personalizzato.
  - **Ricerca/Filtro:** Potrebbero esserci opzioni di ricerca o filtro per trovare rapidamente prodotti specifici.
  - **Modifica/Elimina:** Potresti avere link diretti per modificare il prodotto (che ti porta alla pagina di modifica prodotto standard) o rimuovere l'URL personalizzato per un prodotto direttamente da questo elenco.
- **Effetto delle modifiche:**
  - La modifica di un URL qui (se è disponibile la modifica diretta) o tramite la pagina di modifica del prodotto cambierà immediatamente dove il pulsante reindirizza per quel prodotto.
  - La rimozione di un prodotto da questo elenco (o la cancellazione del suo URL personalizzato nella pagina di modifica del prodotto) ripristinerà il comportamento predefinito del pulsante "Aggiungi al carrello" di PrestaShop.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Utilizza questa schermata per verificare rapidamente quali prodotti stanno utilizzando la funzione di link personalizzato. Se devi aggiornare molti link di prodotto, questa vista ti aiuta a tenere traccia. Per aggiungere nuovi link, di solito è più efficiente andare direttamente alla pagina di modifica del prodotto.

#### index.php (atcurl/controllers/admin/index.php)

Questo file è un segnaposto e in genere non rappresenta una schermata di amministrazione rivolta all'utente. In PrestaShop, i file `index.php` all'interno delle directory dei controller sono spesso utilizzati per impedire l'elenco diretto delle directory o per includere altri file. Non è una schermata di configurazione per i commercianti.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Pagina di configurazione del modulo** | Abilitato | SÌ | Interruttore principale per attivare/disattivare la funzionalità del modulo. |
|  | Testo del pulsante | "Scopri di più" (esempio) | Testo visualizzato sul pulsante personalizzato. |
|  | Nascondi campo quantità | SÌ | Nasconde il selettore di quantità sulle pagine prodotto. |
|  | Classe CSS del pulsante aggiungi al carrello sulla pagina prodotto | (Vuoto / Dipendente dal tema) | Classe CSS personalizzata per il pulsante sulle pagine prodotto. |
|  | Classe CSS quantità | (Vuoto) | Classe CSS personalizzata per l'input quantità sulle pagine prodotto. |
|  | Applica modulo all'elenco dei prodotti | SÌ | Estende la funzionalità del modulo alle pagine di elenco prodotti. |
|  | Classe CSS dell'elemento con prodotto | `product-miniature` (esempio) | Aiuta il modulo a identificare i contenitori dei prodotti negli elenchi. |
|  | Classe CSS di (pulsante Aggiungi al carrello nell'elenco) | `add-to-cart` (esempio) | Aiuta il modulo a identificare i pulsanti "Aggiungi al carrello" negli elenchi. |
|  | Classe CSS dell'input quantità nell'elenco dei prodotti | (Vuoto) | Classe CSS personalizzata per l'input quantità negli elenchi prodotti. |
|  | Nascondi tooltip sul pulsante | SÌ | Impedisce il tooltip predefinito "Aggiungi al carrello" sul pulsante personalizzato. |
|  | Aggiungi rel="nofollow" | SÌ (per esterni) / NO (per interni) | Aggiunge l'attributo `nofollow` al link personalizzato. |
|  | Apri link in nuova finestra (scheda) | SÌ (per esterni) / NO (per interni) | Apre il link personalizzato in una nuova scheda del browser. |
|  | Visibilità del modulo per i prodotti selezionati | Abilitato | Attiva la configurazione URL specifica del prodotto. |
| **Pagina di modifica prodotto (Scheda Moduli)** | Campo URL prodotto | (URL personalizzato) | Definisce l'URL di reindirizzamento specifico per *questo* prodotto. |
| **AdminAtcurlSearchController** | Griglia di prodotti con URL personalizzati | N/A | Vista centralizzata per gestire i prodotti con link personalizzati. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Il mio pulsante "Aggiungi al carrello" non cambia, anche dopo aver configurato un URL.**
R1:

- **Verifica lo stato del modulo:** Innanzitutto, assicurati che l'interruttore "Abilitato" nella pagina di configurazione principale del modulo sia impostato su SÌ.
- **Verifica la visibilità del prodotto:** Assicurati che "Visibilità del modulo per i prodotti selezionati" sia impostato su "Abilitato" nella pagina di configurazione del modulo.
- **Verifica l'URL del prodotto:** Verifica di aver inserito un URL valido nel "Campo URL prodotto" per il prodotto specifico che stai testando (nella pagina di modifica del prodotto sotto la scheda "Moduli").
- **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti). A volte PrestaShop memorizza nella cache contenuti vecchi.
- **Compatibilità del tema:** Il tuo tema potrebbe utilizzare classi CSS non standard per il suo pulsante "Aggiungi al carrello" o per i contenitori dei prodotti. Controlla le impostazioni "Classe CSS dell'elemento con prodotto" e "Classe CSS di" nella pagina di configurazione del modulo. Potrebbe essere necessario utilizzare gli strumenti per sviluppatori del tuo browser (F12) per ispezionare l'HTML e trovare le classi corrette.

**D2: Il campo quantità è ancora visibile, anche se ho selezionato di nasconderlo.**
R2:

- **Controlla "Nascondi campo quantità":** Assicurati che questa impostazione sia abilitata nella pagina di configurazione del modulo.
- **Controlla "Classe CSS dell'input quantità":** Se il tuo tema utilizza una classe non standard per l'input quantità, il modulo potrebbe non essere in grado di trovarlo e nasconderlo. Utilizza gli strumenti per sviluppatori del tuo browser per ispezionare il campo di input della quantità e inserisci la sua classe CSS nell'impostazione "Classe CSS quantità" (per la pagina prodotto) e "Classe CSS dell'input quantità nell'elenco dei prodotti" (per gli elenchi prodotti).
- **Svuota la cache:** Svuota sempre la cache di PrestaShop dopo aver apportato modifiche alla configurazione.

**D3: Il modulo funziona sulle pagine prodotto ma non sulle pagine di categoria/elenco.**
R3:

- **Controlla "Applica modulo all'elenco dei prodotti":** Assicurati che questa impostazione sia abilitata nella pagina di configurazione del modulo.
- **Controlla le classi CSS per gli elenchi:** Il modulo deve sapere come il tuo tema struttura gli elenchi di prodotti. Verifica che le impostazioni "Classe CSS dell'elemento con prodotto" e "Classe CSS di" (per il pulsante) siano corrette per il tuo tema. Queste sono spesso diverse dalle classi della pagina prodotto. Utilizza gli strumenti per sviluppatori del browser per ispezionare gli elementi su una pagina di categoria.
- **Svuota la cache:** Svuota la cache di PrestaShop.

**D4: Il mio pulsante personalizzato non ha l'aspetto giusto (colore, dimensione sbagliati, ecc.).**
R4:

- **Classe CSS per lo stile:** Utilizza l'impostazione "Classe CSS del pulsante aggiungi al carrello sulla pagina prodotto". Inserisci una classe CSS che esiste già nel tuo tema e fornisce lo stile desiderato (es. `btn btn-primary`, `btn-success`).
- **CSS personalizzato:** Se hai bisogno di uno stile unico, dovrai aggiungere CSS personalizzato al tuo tema. Puoi mirare al pulsante utilizzando la classe che hai impostato nella configurazione del modulo, o ispezionando il suo HTML. Ad esempio:

  ```
  .my-custom-button-class { background-color: #ff6600; color: white; border-radius: 5px; padding: 10px 20px;}
  ```

  Aggiungi questo CSS al file CSS personalizzato del tuo tema o tramite un modulo CSS personalizzato.
- **Svuota la cache:** Svuota la cache di PrestaShop.

**D5: Come traduco il testo del pulsante in altre lingue?**
R5:

- Vai su **Internazionale > Traduzioni** nel tuo Back Office di PrestaShop.
- Seleziona "Traduzioni dei moduli installati", scegli il tuo tema e quindi seleziona la lingua che desideri tradurre.
- Trova il modulo "Sostituisci aggiungi al carrello con link a pagina". Vedrai il campo "Testo del pulsante" lì, che ti consente di inserire le traduzioni per ogni lingua.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Sostituisci aggiungi al carrello con link a pagina" (`atcurl`) è un modulo PrestaShop standard che segue un modello simile a MVC. Estende principalmente la funzionalità esistente di PrestaShop tramite hook per modificare la visualizzazione front-office delle pagine prodotto e degli elenchi prodotti. La configurazione è gestita tramite il metodo `getContent()` del modulo principale e memorizzata in `ps_configuration`. Gli URL specifici del prodotto sono memorizzati come `Product::specific_fields` o potenzialmente in una tabella personalizzata, con un Controller Admin (`AdminAtcurlSearchController`) che fornisce un'interfaccia di gestione. JavaScript è ampiamente utilizzato per sostituire dinamicamente i pulsanti e nascondere gli elementi nel front-office.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**: Questo modulo non contiene controller front-office dedicati. Tutte le modifiche front-office sono gestite tramite hook e JavaScript.
- **Controller Admin Back-Office**:

  - `atcurl/controllers/admin/AdminAtcurlSearchController.php`
    - **Nome classe e classe padre:** `AdminAtcurlSearchController` estende `ModuleAdminController`.
    - **Nome scheda ed entità gestita:** Questo controller è probabilmente responsabile della visualizzazione di una griglia o di un elenco di prodotti che hanno un URL personalizzato configurato dal modulo. Fornisce una vista centralizzata per la gestione di queste associazioni di prodotti, consentendo potenzialmente modifiche rapide o rimozioni dell'URL personalizzato. Non gestisce un `ObjectModel` dedicato ma interagisce con i dati del prodotto e la configurazione del modulo.
  - `atcurl/controllers/admin/index.php`
    - Questo è un file segnaposto standard di PrestaShop, che in genere contiene `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../../../"); exit;` per impedire l'elenco diretto delle directory e reindirizzare al pannello di amministrazione principale. Non fornisce alcuna logica di controller funzionale.

### 4.3 Classi e modelli principali (`classes/`)

Il modulo non sembra definire classi personalizzate o `ObjectModel` nella directory `classes/`. Gli URL specifici del prodotto sono probabilmente memorizzati come `Product::specific_fields` o direttamente all'interno della tabella `ps_configuration`, con chiave l'ID del prodotto, o potenzialmente un campo personalizzato aggiunto all'entità del prodotto.

### 4.4 Risorse JavaScript (`views/js/`)

- `atcurl/lib/js/admin/atcurl177.js`
  - **Ambito:** Back-office (Admin).
  - **Responsabilità:** Probabilmente gestisce la logica specifica della pagina di configurazione del modulo o di `AdminAtcurlSearchController` per le versioni di PrestaShop 1.7.7+. Questo potrebbe includere chiamate AJAX per il salvataggio delle impostazioni, aggiornamenti dinamici dell'interfaccia utente o interazioni con lo strumento di ricerca/selezione del prodotto.
- `atcurl/lib/js/front/atcurl-list-177.js`
  - **Ambito:** Front-office.
  - **Responsabilità:** Si rivolge specificamente alle pagine di elenco prodotti (categoria, ricerca, blocchi della homepage). Ascolta i cambiamenti del DOM (ad esempio, quando i prodotti vengono caricati tramite AJAX) e sostituisce dinamicamente i pulsanti "Aggiungi al carrello" con il link personalizzato, nasconde i campi quantità e applica classi CSS personalizzate come configurato. È personalizzato per i temi di PrestaShop 1.7.7+.
- `atcurl/lib/js/front/atcurl177.js`
  - **Ambito:** Front-office.
  - **Responsabilità:** Si rivolge principalmente alla singola pagina prodotto. Identifica il pulsante "Aggiungi al carrello", lo sostituisce con il link personalizzato, nasconde l'input della quantità e applica gli attributi `nofollow` o `target="_blank"` in base alle impostazioni del modulo. Gestisce anche la visualizzazione dei tooltip. Personalizzato per i temi di PrestaShop 1.7.7+.
- `atcurl/lib/searchTool/views/js/autocomplete.js`
  - **Ambito:** Back-office (Admin).
  - **Responsabilità:** Fornisce la funzionalità di autocompletamento, probabilmente per la selezione dei prodotti nella configurazione del modulo o nella griglia `AdminAtcurlSearchController`. Questo aiuta gli amministratori a trovare e associare rapidamente i prodotti con URL personalizzati.

### 4.5 Fogli di stile CSS (`views/css/`)

- `atcurl/lib/searchTool/views/css/autocomplete.css`
  - **Ambito:** Back-office (Admin).
  - **Responsabilità:** Stila il menu a discesa di autocompletamento e gli elementi dell'interfaccia utente correlati utilizzati nello strumento di ricerca amministrativo, garantendo che si integri visivamente con il tema del Back Office di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template hook (`views/templates/hook/`)**:

  - `atcurl/views/hook/displayProductAdditionalInfo.tpl`
    - **Hook:** `displayProductAdditionalInfo`
    - **Scopo:** Questo template è probabilmente renderizzato sulla pagina prodotto, fornendo il contenitore o l'HTML effettivo del pulsante personalizzato che sostituisce il pulsante standard "Aggiungi al carrello". Contenerebbe la logica per visualizzare il testo e il link del pulsante personalizzato.
  - `atcurl/views/hook/displayProductListReviews.tpl`
    - **Hook:** `displayProductListReviews` (Questo nome di hook è insolito per la sostituzione di pulsanti e potrebbe essere un errore di battitura o un modo indiretto per iniettare JS/CSS per gli elenchi di prodotti. È più comune usare `displayProductListFunctionalButtons` o `displayProductActions` per le modifiche dei pulsanti negli elenchi).
    - **Scopo:** Se utilizzato, questo template iniettarebbe JavaScript o un elemento nascosto negli elementi dell'elenco prodotti, che lo script `atcurl-list-177.js` utilizzerebbe quindi per eseguire la sostituzione del pulsante. È meno probabile che contenga direttamente l'HTML del pulsante.
- **Template admin (`views/templates/admin/`)**:

  - `atcurl/lib/searchTool/views/scripts.tpl`
    - **Scopo:** Questo template è probabilmente incluso nel Back Office per caricare il JavaScript necessario (`autocomplete.js`) e potenzialmente CSS (`autocomplete.css`) per lo strumento di ricerca/selezione del prodotto utilizzato nella configurazione del modulo o in `AdminAtcurlSearchController`.
  - `atcurl/views/tpl/selectedProducts.tpl`
    - **Scopo:** Questo template è utilizzato da `AdminAtcurlSearchController` per renderizzare la griglia o l'elenco dei prodotti che hanno URL personalizzati configurati. Definisce la struttura della tabella e come vengono visualizzate le informazioni di ogni prodotto (ID, nome, URL).
- **Template front-office (`views/templates/front/`)**: Nessuno esplicitamente elencato, poiché le modifiche front-office sono gestite principalmente da JS e template hook.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Il modulo non sembra creare tabelle SQL personalizzate.
  - **`ps_configuration`**: Memorizza le impostazioni globali del modulo (es. `ATC_URL_BUTTON_FRONT`, `ATC_URL_BUTTON_TEXT`, `ATC_URL_BLANK`, `ATC_URL_NOFOLLOW`, `ATC_HIDE_TOOLTIP`, `ATC_URL_PL`, `ATC_URL_visibility_rule`, `ATC_URL_BUTTON_QTY_HIDE`, `ATC_URL_visibility_products`, `ATC_URL_visibility_cat`).
  - **`ps_product_shop` / `ps_product_lang`**: Gli URL specifici del prodotto sono probabilmente memorizzati come un campo aggiuntivo associato al prodotto, potenzialmente utilizzando il meccanismo `specific_fields` di PrestaShop o aggiornando direttamente le proprietà del prodotto. Il metodo `install()` del modulo aggiungerebbe questo campo.
- **Tabella degli hook registrati**:

| Nome Hook | Ambito | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- | --- |
| `displayProductAdditionalInfo` | Front-Office | Sulla pagina prodotto, di solito sotto la descrizione del prodotto o il blocco prezzo. | Inietta l'HTML del pulsante personalizzato o un segnaposto per il JS da mirare. |
| `ActionAdminControllerSetMedia` | Back-Office | Quando un controller admin carica i suoi media (JS/CSS). | Carica JavaScript (`atcurl177.js`, `autocomplete.js`) e CSS (`autocomplete.css`) specifici dell'admin per la configurazione del modulo e la gestione dei prodotti. |
| `actionProductUpdate` | Back-Office | Dopo che un prodotto viene aggiornato/salvato nel Back Office. | Consente al modulo di salvare l'URL personalizzato associato al prodotto. |
| `displayHeader` | Front-Office | Nella sezione `<head>` di ogni pagina front-office. | Inietta JavaScript front-office (`atcurl177.js`, `atcurl-list-177.js`) e potenzialmente CSS inline o variabili di configurazione per gli script JS. |
| `displayProductListReviews` | Front-Office | All'interno degli elementi dell'elenco prodotti, spesso vicino al nome del prodotto o alla valutazione. | (Come notato sopra, questo hook è insolito per la sostituzione di pulsanti. È probabilmente usato per iniettare JS per l'elaborazione degli elementi dell'elenco, o potrebbe essere un hook legacy. Gli sviluppatori dovrebbero verificare il suo uso effettivo nel codice del modulo.) |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo "Sostituisci aggiungi al carrello con link a pagina", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team è dedicato a garantire che il modulo funzioni in modo ottimale con il tuo negozio PrestaShop.
