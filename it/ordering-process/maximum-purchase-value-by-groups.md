---
title: "Valore massimo di acquisto per gruppi - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Valore massimo di acquisto per gruppi di MyPresta.eu."
sidebar:
  label: "Valore massimo di acquisto per gruppi - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Maximum purchase value by groups su MyPresta.eu](https://mypresta.eu/modules/ordering-process/maximum-purchase-value-by-groups.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/maximum-purchase-value-by-groups/)
>
> ---


# Valore massimo di acquisto per gruppi

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo aver installato il modulo, vai su **Moduli > Gestione moduli** e cerca "Valore massimo di acquisto per gruppi". Clicca sul pulsante "Configura" per accedere alle sue impostazioni.

La pagina di configurazione mostrerà un elenco di tutti i tuoi gruppi di clienti, permettendoti di impostare un valore massimo di acquisto per ciascuno.

#### **Impostazione: Valore massimo di acquisto per [Nome Gruppo Cliente]**

-   **Cosa fa questa impostazione:** Questo campo di input ti consente di definire il valore totale massimo dell'ordine (includendo o escludendo l'IVA, a seconda dell'impostazione "Applica IVA al valore massimo di acquisto") che i clienti appartenenti a un gruppo specifico possono effettuare.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando viene inserito un valore (es. 500):* Ai clienti di questo gruppo verrà impedito di completare un ordine se il totale del loro carrello supera questo importo. Un messaggio di avviso apparirà nel carrello e nel checkout.
    -   *Quando lasciato vuoto o impostato su 0:* Non ci sarà alcun limite di valore massimo di acquisto per questo specifico gruppo di clienti. Possono ordinare qualsiasi importo.
-   **Valore consigliato:** Questo dipende interamente dal tuo modello di business e dalla segmentazione dei clienti.
    -   Per i **Gruppi all'ingrosso**, potresti impostare un limite elevato (es. 5000) o lasciarlo vuoto se ti fidi di loro.
    -   Per i **Gruppi di nuovi clienti**, potresti impostare un limite inferiore (es. 200) per gestire il rischio.
    -   Per i **Gruppi di clienti predefiniti**, potresti lasciarlo vuoto a meno che tu non abbia un motivo specifico per limitare i clienti generici.
-   **Scenario / esempio del commerciante:** Hai un gruppo "Ingrosso Livello 1". Vuoi assicurarti che nessun singolo ordine da questo gruppo superi €10.000 senza previa approvazione. Inseriresti `10000` nel campo accanto a "Ingrosso Livello 1". Se un cliente di questo gruppo tenta di ordinare €10.001, verrà bloccato.

#### **Impostazione: Applica IVA al valore massimo di acquisto**

-   **Cosa fa questa impostazione:** Questo interruttore determina se il valore massimo di acquisto che imposti per ogni gruppo deve essere calcolato in base al totale del carrello *includendo* le tasse o *escludendo* le tasse.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Il modulo confronterà il totale del carrello del cliente *includendo tutte le tasse applicabili* con il valore massimo che hai definito. Questo è generalmente il modo in cui i clienti percepiscono il loro costo totale.
    -   *Quando disabilitato (NO):* Il modulo confronterà il totale del carrello del cliente *escludendo le tasse* con il valore massimo che hai definito. Questo potrebbe essere utile se la tua contabilità interna o gli accordi all'ingrosso si basano su valori al netto delle tasse.
-   **Valore consigliato:** **SÌ**. La maggior parte dei commercianti e dei clienti pensa in termini di prezzo finale, inclusa l'IVA. Abilitare questa opzione garantisce che il limite si applichi all'importo effettivo che il cliente pagherà.
-   **Scenario / esempio del commerciante:** Hai impostato un valore massimo di €500 per un gruppo.
    -   Se "Applica IVA" è SÌ: Un cliente con un totale carrello di €450 (prodotti) + €50 (IVA) = €500 sarà consentito. Un carrello di €460 (prodotti) + €50 (IVA) = €510 sarà bloccato.
    -   Se "Applica IVA" è NO: Un cliente con un totale carrello di €500 (prodotti) + €50 (IVA) = €550 sarà consentito perché il totale dei prodotti è esattamente €500.

#### **Impostazione: Mostra messaggio sulle limitazioni**

-   **Cosa fa questa impostazione:** Questo interruttore controlla se il messaggio informativo sul superamento del valore massimo di acquisto viene mostrato al cliente nel front-office.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* I clienti vedranno un messaggio chiaro e intuitivo sulle pagine del carrello e del checkout se il totale del loro ordine supera il limite per il loro gruppo. Questo li aiuta a capire perché non possono procedere.
    -   *Quando disabilitato (NO):* La limitazione sarà comunque applicata (ai clienti verrà impedito di ordinare), ma non verrà visualizzato alcun messaggio esplicito. Ciò può portare a confusione e a una scarsa esperienza del cliente, poiché non sapranno *perché* non possono completare l'ordine.
-   **Valore consigliato:** **SÌ**. Informa sempre i tuoi clienti in modo chiaro. Nascondere il messaggio porterà solo a frustrazione e ticket di supporto.
-   **Scenario / esempio del commerciante:** Un cliente tenta di ordinare troppo. Se questa opzione è abilitata, vedrà "Il tuo ordine supera il valore massimo consentito per il tuo gruppo di clienti (€500). Riduci il totale del carrello per procedere." Se disabilitata, vedrà solo un errore o il pulsante "Procedi al checkout" rimarrà inattivo senza spiegazioni.

#### **Impostazione: Messaggio da visualizzare**

-   **Cosa fa questa impostazione:** Questa area di testo ti consente di personalizzare il messaggio che i clienti vedono quando superano il valore massimo di acquisto del loro gruppo. Puoi renderlo più specifico per il branding o le politiche del tuo negozio.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando viene inserito un messaggio personalizzato:* Questo messaggio verrà visualizzato ai clienti invece del messaggio predefinito del modulo. Puoi usare HTML per la formattazione di base.
    -   *Quando lasciato vuoto:* Il modulo visualizzerà un messaggio predefinito e generico (ad esempio, "Il tuo ordine supera il valore massimo consentito per il tuo gruppo di clienti.").
-   **Valore consigliato:** Personalizzalo per essere amichevole e utile. Includi segnaposto come `{max_value}` e `{currency_sign}` se il modulo li supporta (controlla il comportamento effettivo del modulo, poiché questo modulo specifico potrebbe non utilizzare direttamente i segnaposto ma piuttosto inserire dinamicamente il valore). Un buon valore predefinito è spesso sufficiente.
-   **Scenario / esempio del commerciante:** Invece di un messaggio generico, potresti voler dire: "Gentile cliente, il totale del tuo ordine attuale supera il valore massimo di acquisto consentito di {max\_value} {currency\_sign} per il tuo tipo di account. Ti preghiamo di modificare il tuo carrello o di contattare il nostro team di vendita per ordini più grandi."

Ricorda di cliccare sul pulsante **"Salva"** in fondo alla pagina di configurazione dopo aver apportato qualsiasi modifica.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Valore massimo di acquisto per [Nome Gruppo] | Vuoto / Varia | Imposta il limite di spesa superiore per un gruppo di clienti specifico. Vuoto significa nessun limite. |
| Configurazione modulo | Applica IVA al valore massimo di acquisto | SÌ | Determina se il limite si applica al totale del carrello con o senza tasse. Consigliato: SÌ (prezzo finale). |
| Configurazione modulo | Mostra messaggio sulle limitazioni | SÌ | Controlla se i clienti vedono una spiegazione quando bloccati. Consigliato: SÌ (per chiarezza). |
| Configurazione modulo | Messaggio da visualizzare | Messaggio predefinito | Personalizza il messaggio di avviso mostrato ai clienti. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho impostato un limite, ma i clienti possono comunque ordinare di più. Cosa c'è che non va?**
R:

1.  **Controlla il gruppo del cliente:** Assicurati che il cliente con cui stai testando appartenga effettivamente al gruppo per il quale hai impostato il limite.
2.  **Impostazione "Applica IVA":** Ricontrolla se l'impostazione "Applica IVA al valore massimo di acquisto" è configurata correttamente. Se il tuo limite è 500 ed è impostato su "NO" (escludi IVA), un cliente potrebbe essere in grado di ordinare 500 in prodotti + IVA, il che sembra superare 500.
3.  **Modulo abilitato:** Assicurati che il modulo sia effettivamente abilitato nel tuo Gestore moduli.
4.  **Cache:** Svuota la cache di PrestaShop (Parametri avanzati > Prestazioni > Svuota cache) e la cache del tuo browser.

**D: Il messaggio sulla limitazione non viene visualizzato, ma i clienti sono comunque bloccati.**
R: Controlla l'impostazione "Mostra messaggio sulle limitazioni" nella configurazione del modulo. Assicurati che sia impostata su "SÌ". Se è impostata su "NO", il modulo applicherà il limite silenziosamente, il che può essere confuso per i clienti.

**D: Posso impostare messaggi diversi per diversi gruppi di clienti?**
R: No, il modulo attualmente utilizza una singola impostazione "Messaggio da visualizzare" che si applica a tutti i gruppi. Se hai bisogno di messaggi specifici per gruppo, ciò richiederebbe uno sviluppo personalizzato.

**D: Questo modulo influisce su sconti o costi di spedizione?**
R: Il modulo di solito valuta il *totale finale del carrello* al momento del checkout, che di solito include sconti, costi di spedizione e tasse (a seconda dell'impostazione "Applica IVA"). Quindi, il limite si applica all'importo finale che il cliente è tenuto a pagare.

**D: Il mio tema personalizzato non visualizza correttamente il messaggio.**
R: Questo può accadere se il tuo tema ha modelli di carrello o checkout altamente personalizzati.

1.  **Svuota la cache di Smarty:** Vai su **Parametri avanzati > Prestazioni**, imposta "Compilazione dei template" su "Forza compilazione" e "Cache" su "No", quindi svuota la cache. Prova di nuovo. Ripristina le impostazioni in seguito.
2.  **Conflitto CSS:** Il CSS del tuo tema potrebbe sovrascrivere lo stile del modulo. Potrebbe essere necessario un web developer per ispezionare l'elemento e applicare CSS personalizzati per garantire che il messaggio sia visibile e stilizzato correttamente.
3.  **Problema di hook:** Assicurati che il tuo tema chiami correttamente gli hook standard di PrestaShop in cui il modulo inietta il suo contenuto (ad esempio, `displayShoppingCart`, `displayPaymentTop`).

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo `Valore massimo di acquisto per gruppi` (`cgmaxa`) è un modulo PrestaShop standard che implementa il pattern MVC. Opera principalmente agganciandosi a eventi chiave del front-office durante il processo di carrello e checkout per convalidare il totale corrente del carrello rispetto ai limiti specifici del gruppo memorizzati nella tabella `ps_configuration`. Utilizza un controller frontale per le richieste AJAX per fornire feedback dinamico e una classe di modulo principale per la configurazione e la registrazione degli hook.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

-   `cgmaxa/controllers/front/ajax.php`
    -   **Nome classe**: `CgmaxaAjaxModuleFrontController` (estende `ModuleFrontController`)
    -   **Responsabilità**: Questo controller gestisce le richieste AJAX dal front-office, probabilmente per la convalida in tempo reale del totale del carrello man mano che gli articoli vengono aggiunti/rimossi o durante le fasi di checkout. Tipicamente riceverebbe i dati del carrello, eseguirebbe il controllo del limite e restituirebbe una risposta JSON che indica se il limite è superato e il messaggio pertinente.
-   `cgmaxa/controllers/front/index.php`
    -   **Nome classe**: `CgmaxaIndexModuleFrontController` (estende `ModuleFrontController`)
    -   **Responsabilità**: Questo controller potrebbe essere un segnaposto o utilizzato per un routing specifico che non rientra nella spedizione principale del modulo. Dato il suo nome, potrebbe potenzialmente essere un punto di ingresso predefinito o gestire interazioni front-office non AJAX se il modulo avesse una pagina dedicata, sebbene la sua funzione primaria per questo modulo sia probabilmente minima o per fallback.

#### Controller Admin Back-Office

Questo modulo non sembra utilizzare alcun controller admin dedicato. Tutta la configurazione è gestita direttamente all'interno del metodo `getContent()` del modulo principale.

### 4.3 Classi e Modelli Core (`classes/`)

Questo modulo non sembra definire alcuna classe personalizzata o `ObjectModel` in una directory `classes/`. Tutta la logica è incapsulata all'interno del file del modulo principale (`cgmaxa.php`) e dei suoi controller. I valori di configurazione sono memorizzati direttamente in `ps_configuration`.

### 4.4 Risorse JavaScript (`views/js/`)

-   `cgmaxa/views/js/cgmaxa.js`
    -   **Ambito**: Front-office.
    -   **Dettagli**: Questo script è responsabile delle interazioni lato client. Probabilmente si lega a eventi come modifiche della quantità nel carrello, aggiunta/rimozione di prodotti o navigazione attraverso le fasi di checkout. Invierebbe richieste AJAX a `cgmaxa/controllers/front/ajax.php` per convalidare il totale del carrello in tempo reale. Dopo aver ricevuto una risposta, visualizzerebbe dinamicamente il messaggio di avviso (se il limite è superato) e potenzialmente disabiliterebbe i pulsanti "Procedi al checkout" o "Pagamento" per impedire la finalizzazione dell'ordine. Potrebbe anche aggiornare dinamicamente il messaggio con il valore corrente del carrello e il valore massimo consentito.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `cgmaxa/css.css`
    -   **Ambito**: Front-office.
    -   **Dettagli**: Questo foglio di stile fornisce lo stile di base per il messaggio di avviso visualizzato ai clienti quando superano il limite di acquisto. Probabilmente definisce classi per il contenitore del messaggio, il colore del testo, lo sfondo e possibilmente icone per far risaltare l'avviso. Gli sviluppatori possono sovrascrivere questi stili nel `custom.css` del loro tema o utilizzando selettori più specifici.
-   `cgmaxa/views/css/cgmaxa.css`
    -   **Ambito**: Front-office.
    -   **Dettagli**: Simile a `cgmaxa/css.css`, questo file fornisce lo stile per gli elementi del front-office. Potrebbe contenere stili più specifici o aggiornati rispetto a `cgmaxa/css.css`, oppure uno potrebbe essere un file legacy. Gli sviluppatori dovrebbero ispezionare entrambi per comprendere lo stile completo applicato. I selettori chiave mirerebbero al contenitore del messaggio e al suo contenuto.

### 4.6 Struttura del template Smarty (`views/templates/`)

#### Template degli hook (`views/templates/hook/`)

-   `cgmaxa/views/templates/front/displayShoppingCart.tpl`
    -   **Hook**: `displayShoppingCart` (e potenzialmente `displayPaymentTop`, `stepBeforePaymentOPC`, `displaystepBeforePaymentOPC`).
    -   **Output**: Questo template è responsabile del rendering del messaggio di avviso sulla pagina del carrello e potenzialmente su altre fasi del checkout. Contenerebbe la struttura HTML per la casella di avviso, inserendo dinamicamente il messaggio personalizzato e il valore massimo consentito se il limite viene superato. Probabilmente utilizza variabili Smarty passate dai metodi hook del modulo per determinare se il messaggio deve essere visualizzato e quale contenuto deve contenere.

#### Template Admin (`views/templates/admin/`)

-   `cgmaxa/admin.tpl`
    -   **Ambito**: Configurazione Back-office.
    -   **Output**: Questo template viene utilizzato dal metodo `getContent()` del modulo per renderizzare il modulo di configurazione nel Back Office di PrestaShop. Include i campi di input per il valore massimo di ciascun gruppo di clienti, l'interruttore "Applica IVA", l'interruttore "Mostra messaggio" e l'area di testo del messaggio personalizzato. Itera attraverso i gruppi di clienti disponibili per creare i campi di input dinamici.

### 4.7 Schema del database e Mappa degli hook

#### Tabelle del database

Il modulo non crea tabelle di database personalizzate. Tutte le impostazioni di configurazione (valori massimi per gruppo, impostazione IVA, visualizzazione messaggio, messaggio personalizzato) sono memorizzate nella tabella `ps_configuration` utilizzando chiavi come `CGMAXA_GROUP_[ID_GROUP]`, `CGMAXA_TAX`, `CGMAXA_DISPLAY_MESSAGE`, `CGMAXA_MESSAGE`.

#### Tabella degli hook registrati

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Per includere i file CSS e JavaScript necessari (`cgmaxa.js`, `cgmaxa.css`) per la funzionalità del front-office e la convalida AJAX. |
| `displayShoppingCart` | Nella pagina di riepilogo del carrello. | Per visualizzare il messaggio di avviso se il totale del carrello supera il limite del gruppo e potenzialmente disabilitare il pulsante "Procedi al checkout". |
| `displayPaymentTop` | Nella parte superiore della fase di selezione del pagamento nel processo di checkout. | Per riconvalidare il totale del carrello prima del pagamento e visualizzare il messaggio di avviso, bloccando ulteriori progressi se il limite viene superato. |
| `stepBeforePaymentOPC` | Prima della fase di pagamento nel One-Page Checkout (OPC). | Simile a `displayPaymentTop`, questo hook garantisce che la convalida avvenga subito prima che il cliente possa selezionare un metodo di pagamento, cruciale per i flussi OPC. |
| `displaystepBeforePaymentOPC` | Un altro hook relativo alla fase prima del pagamento in OPC. | Fornisce un punto aggiuntivo per la convalida e la visualizzazione del messaggio in temi o configurazioni OPC specifici. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Valore massimo di acquisto per gruppi", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e alla configurazione del modulo.
