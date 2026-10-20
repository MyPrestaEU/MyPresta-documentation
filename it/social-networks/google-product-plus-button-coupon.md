---
title: "Pulsante Google product plus + coupon - Manuale del commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Pulsante Google product plus + coupon di MyPresta.eu."
sidebar:
  label: "Pulsante Google product plus + coupon - Manuale del commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Google product plus button + coupon su MyPresta.eu](https://mypresta.eu/modules/social-networks/google-product-plus-button-coupon.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/google-product-plus-button-coupon/)
>
> ---


# Pulsante Google product plus + coupon

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e per qualsiasi modulo che interagisca con API esterne.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo "Pulsante Google product plus + coupon". Qui troverai tutte le impostazioni per controllare come appare il pulsante Google +1 e come vengono generati i coupon.

#### **Impostazioni generali**

- **Update\_ / Updatev\_ (Impostazioni interne)**

  - **Cosa fa questa impostazione:** Queste sono impostazioni interne del modulo utilizzate per tenere traccia degli aggiornamenti e del versioning. Non sono destinate all'interazione diretta del commerciante.
  - **Effetto della modifica di questa impostazione:** Non dovresti **mai** modificare manualmente questi valori. Farlo potrebbe interferire con gli aggiornamenti del modulo o i processi interni.
  - **Valore consigliato:** Lasciare così com'è.
  - **Scenario / esempio del commerciante:** Queste impostazioni assicurano che il tuo modulo possa essere aggiornato correttamente quando MyPresta.eu rilascia nuove versioni.
- **Codice Voucher (gc\_voucher)**

  - **Cosa fa questa impostazione:** Questa è la **percentuale di sconto** che verrà applicata al coupon generato per i clienti che cliccano sul pulsante +1.
  - **Effetto della modifica di questa impostazione:**
    - *Se impostato su `10` (per 10%):* I clienti che mettono +1 a un prodotto riceveranno un coupon per il 10% di sconto sul loro prossimo acquisto.
    - *Se impostato su `0` o lasciato vuoto:* Non verrà applicato alcuno sconto, rendendo il coupon essenzialmente inutile.
  - **Valore consigliato:** Una percentuale di sconto ragionevole, ad esempio `5`, `10` o `15`.
  - **Scenario / esempio del commerciante:** Vuoi offrire uno sconto del 10% per incoraggiare la condivisione sociale. Inseriresti `10` qui.
- **Mostra Prezzi (gc\_show\_prices)**

  - **Cosa fa questa impostazione:** Determina se i prezzi originali e scontati vengono visualizzati insieme all'offerta del coupon.
  - **Effetto della modifica di questa impostazione:**
    - *Se abilitato (Sì):* Il cliente vedrà il prezzo originale e il prezzo dopo l'applicazione dello sconto, rendendo più chiaro il valore del coupon.
    - *Se disabilitato (No):* Verrà mostrato solo il codice coupon, senza espliciti confronti di prezzo.
  - **Valore consigliato:** `Sì`. Mostrare la differenza di prezzo spesso aumenta il valore percepito del coupon.
  - **Scenario / esempio del commerciante:** Un cliente vede un prodotto a $100. Se "Mostra Prezzi" è abilitato e il coupon è del 10%, vedrà "$100 -> $90 con coupon", il che è più convincente.
- **Mostra Totale (gc\_show\_total)**

  - **Cosa fa questa impostazione:** Controlla se il valore totale dell'ordine (dopo lo sconto) viene visualizzato con il coupon. Questo è solitamente rilevante se il coupon si applica all'intero carrello.
  - **Effetto della modifica di questa impostazione:**
    - *Se abilitato (Sì):* Il cliente potrebbe vedere un valore totale stimato dell'ordine con lo sconto applicato.
    - *Se disabilitato (No):* L'attenzione rimane sul prezzo del prodotto o sul codice coupon stesso.
  - **Valore consigliato:** `Sì`, soprattutto se il coupon è valido per l'intero carrello, poiché aiuta il cliente a visualizzare i propri risparmi.
  - **Scenario / esempio del commerciante:** Se il coupon si applica all'intero carrello, mostrare un potenziale risparmio totale può incoraggiare un acquisto più grande.
- **Mostra Prodotti (gc\_show\_products)**

  - **Cosa fa questa impostazione:** Determina se i prodotti specifici a cui si applica il coupon vengono elencati quando il coupon viene visualizzato.
  - **Effetto della modifica di questa impostazione:**
    - *Se abilitato (Sì):* Il messaggio del coupon potrebbe dichiarare esplicitamente "Questo coupon si applica a [Nome Prodotto]".
    - *Se disabilitato (No):* Il coupon viene presentato in modo più generale, o si potrebbe presumere che si applichi al prodotto appena messo +1.
  - **Valore consigliato:** `Sì`, per chiarezza, a meno che il tuo coupon non sia sempre valido per tutto il negozio.
  - **Scenario / esempio del commerciante:** Se il tuo coupon è solo per il prodotto a cui il cliente ha messo +1, mostrare il nome del prodotto chiarisce il suo utilizzo.
- **Mostra URL Prodotto (gc\_show\_product\_url)**

  - **Cosa fa questa impostazione:** Controlla se l'URL del prodotto a cui è stato messo +1 è incluso nella visualizzazione del coupon.
  - **Effetto della modifica di questa impostazione:**
    - *Se abilitato (Sì):* Il cliente vede un link diretto alla pagina del prodotto, il che può essere utile se si allontana.
    - *Se disabilitato (No):* L'URL viene omesso.
  - **Valore consigliato:** `Sì`, per una migliore esperienza utente e navigazione.
  - **Scenario / esempio del commerciante:** Un cliente ottiene un coupon, quindi chiude il pop-up. Avere l'URL del prodotto lo aiuta a tornare rapidamente al prodotto a cui era interessato.
- **Ultima Scheda (gc\_lasttab)**

  - **Cosa fa questa impostazione:** Questa impostazione probabilmente controlla in quale scheda o sezione della pagina del prodotto appariranno il pulsante Google +1 e le informazioni sul coupon, se il tuo tema utilizza un'area di descrizione del prodotto a schede.
  - **Effetto della modifica di questa impostazione:**
    - *Se impostato su `1` (o valore simile):* Il contenuto del modulo apparirà nell'ultima scheda della pagina del prodotto.
    - *Se impostato su `0` (o valore simile):* Il contenuto del modulo apparirà nella prima scheda o in una posizione predefinita.
  - **Valore consigliato:** Sperimenta con `1` per vedere se si adatta al layout del tuo tema. Se il tuo tema non utilizza schede, questa impostazione potrebbe non avere alcun effetto visibile.
  - **Scenario / esempio del commerciante:** La tua pagina prodotto ha le schede "Descrizione", "Scheda tecnica" e "Recensioni". Impostando questo su `1` potresti posizionare il pulsante +1 e il coupon in una nuova scheda "Condivisione sociale" o alla fine della scheda "Descrizione".
- **Posizione (gc\_position)**

  - **Cosa fa questa impostazione:** Determina l'area generale della pagina del prodotto in cui verranno visualizzati il pulsante Google +1 e l'offerta del coupon. Questo si mappa al sistema di hook di PrestaShop.
  - **Effetto della modifica di questa impostazione:**
    - *Modificando il valore:* Sposta il contenuto del modulo in diverse posizioni sulla pagina del prodotto (es. sopra "Aggiungi al carrello", sotto la descrizione, in una colonna laterale).
  - **Valore consigliato:** `displayproductActions` o `displayproductFooter` sono posizioni comuni ed efficaci. Testa diverse posizioni per vedere cosa si integra meglio con il tuo tema ed è più visibile ai clienti.
  - **Scenario / esempio del commerciante:** Vuoi che il pulsante +1 sia molto prominente, quindi scegli `displayproductActions` per posizionarlo vicino al pulsante "Aggiungi al carrello".
- **Numero di Mi Piace (gc\_nblikes)**

  - **Cosa fa questa impostazione:** Questa impostazione probabilmente controlla il numero minimo di +1 richiesti prima che venga emesso un coupon, oppure potrebbe essere un'impostazione di visualizzazione per il conteggio dei +1. Data la funzionalità principale del modulo, è più probabile che sia correlata al trigger del coupon.
  - **Effetto della modifica di questa impostazione:**
    - *Se impostato su `1` (o `0`):* Un coupon viene emesso immediatamente dopo un singolo +1.
    - *Se impostato su `5`:* Un coupon potrebbe essere emesso solo dopo 5 +1 unici (meno probabile data la natura della ricompensa istantanea, ma possibile per una funzione "coupon di gruppo"). Più probabilmente, controlla la visualizzazione del conteggio dei +1.
  - **Valore consigliato:** `1` (o `0` se significa "mostra sempre"). La forza del modulo è la gratificazione istantanea.
  - **Scenario / esempio del commerciante:** Vuoi che ogni cliente che mette +1 riceva un coupon, quindi imposti questo su `1`.
- **Stile Pulsante (gc\_button\_style)**

  - **Cosa fa questa impostazione:** Ti consente di scegliere lo stile visivo o la dimensione del pulsante Google +1.
  - **Effetto della modifica di questa impostazione:**
    - *Modificando il valore:* Altera l'aspetto del pulsante +1 (es. piccolo, medio, grande, alto, con o senza conteggio).
  - **Valore consigliato:** Scegli uno stile che sia visibile ma non disturbi il design della tua pagina prodotto. "Medio" o "Standard" sono solitamente buoni punti di partenza.
  - **Scenario / esempio del commerciante:** La tua pagina prodotto ha spazio limitato, quindi scegli uno stile di pulsante "piccolo".
- **Modalità Condivisione (gcshare\_mode)**

  - **Cosa fa questa impostazione:** Questa impostazione probabilmente controlla come funziona la funzionalità di condivisione, offrendo eventualmente diversi modi per il cliente di condividere o interagire con la piattaforma Google+.
  - **Effetto della modifica di questa impostazione:**
    - *Modificando il valore:* Potrebbe alterare il comportamento del pop-up o la specifica finestra di dialogo di condivisione di Google+ che appare.
  - **Valore consigliato:** Lasciare il valore predefinito a meno che tu non abbia un motivo specifico per cambiarlo e comprenda le implicazioni per l'integrazione di Google+.
  - **Scenario / esempio del commerciante:** Potresti sperimentare diverse modalità se ritieni che l'esperienza di condivisione predefinita non sia ottimale per i tuoi clienti.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Codice Voucher (gc\_voucher) | 10 | Percentuale di sconto per il coupon generato. |
| Configurazione Modulo | Mostra Prezzi (gc\_show\_prices) | Sì | Visualizza prezzi originali e scontati con coupon. |
| Configurazione Modulo | Mostra Totale (gc\_show\_total) | Sì | Visualizza il valore totale stimato dell'ordine con sconto. |
| Configurazione Modulo | Mostra Prodotti (gc\_show\_products) | Sì | Elenca i prodotti specifici a cui si applica il coupon. |
| Configurazione Modulo | Mostra URL Prodotto (gc\_show\_product\_url) | Sì | Include l'URL del prodotto nella visualizzazione del coupon. |
| Configurazione Modulo | Ultima Scheda (gc\_lasttab) | 1 (o dipendente dal tema) | Posizione nelle schede della pagina prodotto (se applicabile). |
| Configurazione Modulo | Posizione (gc\_position) | displayproductActions / displayproductFooter | Posizionamento generale del pulsante e del coupon sulla pagina prodotto. |
| Configurazione Modulo | Numero di Mi Piace (gc\_nblikes) | 1 | Minimo +1 per il coupon (probabilmente 1 per ricompensa istantanea). |
| Configurazione Modulo | Stile Pulsante (gc\_button\_style) | Standard / Medio | Dimensione e stile visivo del pulsante Google +1. |
| Configurazione Modulo | Modalità Condivisione (gcshare\_mode) | Predefinito | Controlla l'interazione di condivisione di Google+. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

-   **D: Il pulsante Google +1 non appare sulle mie pagine prodotto.**

    -   **R:** Per prima cosa, controlla l'impostazione "Posizione (gc\_position)" nella configurazione del modulo. Assicurati di aver selezionato un hook che sia effettivamente renderizzato dal tuo tema sulla pagina prodotto. Alcuni temi personalizzati potrebbero non implementare tutti gli hook standard di PrestaShop.
    -   **R:** Svuota la cache di PrestaShop (Parametri avanzati > Prestazioni > Svuota cache).
    -   **R:** Controlla la presenza di errori JavaScript nella console per sviluppatori del tuo browser (F12). Conflitti con altri moduli o script del tema possono talvolta impedire il caricamento dei pulsanti.
    -   **R:** Assicurati che il modulo sia abilitato in Gestione moduli.
-   **D: I clienti cliccano +1 ma non ricevono un coupon.**

    -   **R:** Verifica che l'impostazione "Codice Voucher (gc\_voucher)" abbia una percentuale di sconto valida (es. `10` per 10%). Se è `0` o vuota, non verrà generato alcun coupon efficace.
    -   **R:** Controlla l'impostazione "Numero di Mi Piace (gc\_nblikes)". Se è impostata su un valore maggiore di 1, il coupon non verrà emesso finché non viene raggiunta quella soglia. Per i coupon istantanei, dovrebbe essere 1.
    -   **R:** Assicurati che non ci siano errori lato server che impediscono la generazione del coupon. Controlla i log degli errori di PrestaShop (Parametri avanzati > Log).
-   **D: Il pulsante appare strano o è disallineato sul mio sito mobile.**

    -   **R:** Questo è spesso un conflitto CSS con il tuo tema. Il modulo include il proprio CSS, ma gli stili del tuo tema potrebbero sovrascriverlo o entrarvi in conflitto. Potrebbe essere necessario un web developer per ispezionare il CSS e apportare piccole modifiche.
    -   **R:** Prova diverse opzioni di "Stile Pulsante (gc\_button\_style)" per vedere se una dimensione diversa viene renderizzata meglio.
-   **D: Posso personalizzare il messaggio del coupon o la validità?**

    -   **R:** La configurazione del modulo controlla principalmente la percentuale di sconto e le opzioni di visualizzazione. Per regole avanzate sui coupon (es. acquisto minimo, categorie specifiche, periodo di validità), dovresti tipicamente gestirle all'interno delle sezioni native di PrestaShop "Regole prezzi catalogo" o "Regole carrello" (Sconti), e il modulo genererebbe un codice che aderisce a tali regole se applicabile, oppure potresti dover creare manualmente una regola specifica che corrisponda al coupon generato dal modulo. Il modulo stesso genera uno sconto percentuale di base.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce un'analisi tecnica approfondita del modulo "Pulsante Google product plus + coupon" per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo segue un'architettura standard di PrestaShop, sfruttando principalmente la classe `Module` e i suoi metodi `install()`, `uninstall()` e `getContent()`. Si integra con il front-office tramite vari hook di visualizzazione per iniettare il pulsante Google +1 e la logica del coupon associata. La generazione e la visualizzazione del coupon sono gestite dinamicamente utilizzando JavaScript e i template Smarty. Non ci sono classi `ObjectModel` personalizzate o controller Admin dedicati oltre alla configurazione principale del modulo.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Nessuno. Tutte le funzionalità del front-office sono gestite tramite hook del modulo e rendering diretto dei template.
-   **Controller Admin Back-Office**: Nessuno. La configurazione è interamente all'interno del metodo `getContent()` del modulo principale.

### 4.3 Classi e modelli principali (`classes/`)

-   Nessuna classe personalizzata o definizione `ObjectModel` è presente nella directory `classes/`. Tutta la logica principale risiede in `googlecoupon/googlecoupon.php`.

### 4.4 Risorse JavaScript (`views/js/`)

-   `googlecoupon/lib/voucherengine/script.js`
    -   **Ambito:** Front-office.
    -   **Responsabilità:** Questo script è probabilmente responsabile della logica principale della generazione e visualizzazione del coupon. Ascolterebbe l'evento di clic del pulsante Google +1, attiverebbe il processo di generazione del coupon (possibilmente tramite una chiamata AJAX al file principale del modulo o una funzione JavaScript diretta) e quindi visualizzerebbe il codice coupon all'utente. Potrebbe anche gestire l'interazione con l'API di Google+ (anche se le API di Google+ sono state in gran parte deprecate o integrate in altri servizi).
-   `googlecoupon/trusted.js`
    -   **Ambito:** Front-office.
    -   **Responsabilità:** Lo scopo di questo script è meno chiaro dal solo nome, ma potrebbe essere correlato a garantire l'integrità dell'azione +1, al tracciamento o all'integrazione con altri servizi affidabili. Potrebbe anche essere un residuo di vecchie integrazioni API di Google+.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `googlecoupon/css.css`
    -   **Ambito:** Front-office.
    -   **Responsabilità:** Fornisce lo stile principale per il pulsante Google +1, l'area di visualizzazione del coupon e qualsiasi pop-up o notifica associata.
    -   **Selettori di classe CSS chiave:** Gli sviluppatori dovrebbero ispezionare questo file per identificare classi specifiche (es. `.googlecoupon-button-container`, `.googlecoupon-voucher-display`, `.googlecoupon-modal`) che possono essere sovrascritte nel `custom.css` o `theme.css` di un tema personalizzato per adattarsi al branding del negozio.
-   `googlecoupon/css/css.css`
    -   **Ambito:** Front-office.
    -   **Responsabilità:** Questo sembra essere un foglio di stile duplicato o alternativo. È importante verificare se entrambi vengono caricati o se uno è un fallback. Probabilmente conterrebbe regole di stile simili a `googlecoupon/css.css`.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**: Nessuno esplicitamente elencato, ma `share.tpl` probabilmente serve a questo scopo.
-   **Template Admin (`views/templates/admin/`)**: Nessuno.
-   **Template Front-office (`views/templates/front/`)**: Nessuno esplicitamente elencato, ma `share.tpl` è il template chiave del front-office.
    -   `googlecoupon/share.tpl`
        -   **Ambito:** Front-office.
        -   **Scopo:** Questo template è responsabile del rendering del pulsante Google +1 e del contenitore in cui verranno visualizzate le informazioni sul coupon. Verrà iniettato nei vari hook del front-office configurati nel modulo. Probabilmente contiene segnaposto per lo script di Google+ e il codice coupon generato dinamicamente.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non sembra creare tabelle SQL personalizzate.
    -   Le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` utilizzando chiavi come `GC_VOUCHER`, `GC_SHOW_PRICES`, `GC_SHOW_TOTAL`, `GC_SHOW_PRODUCTS`, `GC_SHOW_PRODUCT_URL`, `GC_LASTTAB`, `GC_POSITION`, `GC_NBLIKES`, `GC_BUTTON_STYLE`, `GCSHARE_MODE`.
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayproductActions` | Sulla pagina prodotto, tipicamente vicino al pulsante "Aggiungi al carrello". | Inietta il pulsante Google +1 e la visualizzazione del coupon in un'area prominente. |
| `displayproductFooter` | Sulla pagina prodotto, in fondo al blocco informazioni prodotto. | Inietta il pulsante Google +1 e la visualizzazione del coupon dopo i dettagli principali del prodotto. |
| `productFooter` | Sulla pagina prodotto, simile a `displayproductFooter`, spesso utilizzato per contenuti aggiuntivi. | Posizionamento alternativo per il pulsante Google +1 e la visualizzazione del coupon. |
| `extraLeft` | Sulla pagina prodotto, nella colonna sinistra (se abilitata dal tema). | Posiziona il contenuto del modulo nella sidebar sinistra. |
| `productActions` | Sulla pagina prodotto, specificamente intorno ai selettori "Aggiungi al carrello" e quantità. | Posizionamento alternativo per il pulsante Google +1 e la visualizzazione del coupon, spesso molto prominente. |
| `displayextraleft` | Sulla pagina prodotto, nella colonna sinistra. | Simile a `extraLeft`, per iniettare contenuto nella sidebar sinistra. |
| `extraRight` | Sulla pagina prodotto, nella colonna destra (se abilitata dal tema). | Posiziona il contenuto del modulo nella sidebar destra. |
| `displayextraright` | Sulla pagina prodotto, nella colonna destra. | Simile a `extraRight`, per iniettare contenuto nella sidebar destra. |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Utilizzato per includere i file CSS e JavaScript necessari per il modulo. |
| `header` | Nella sezione `<head>` di ogni pagina (versioni precedenti di PrestaShop). | Simile a `displayHeader`, per includere risorse. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e per scaricare le ultime versioni del modulo "Pulsante Google product plus + coupon", accedi al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere.
