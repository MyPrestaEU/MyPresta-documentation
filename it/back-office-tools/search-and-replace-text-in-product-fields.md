---
title: "Cerca e sostituisci testo nei campi prodotto - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Cerca e sostituisci testo nei campi prodotto' di MyPresta.eu."
sidebar:
  label: "Cerca e sostituisci testo nei campi prodotto"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Search and replace text in product fields su MyPresta.eu](https://mypresta.eu/modules/administration-tools/search-and-replace-text-in-product-fields.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/search-and-replace-text-in-product-fields/)
>
> ---


# Cerca e sostituisci testo nei campi prodotto

## 1. Requisiti e Compatibilità
-   **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
-   **Compatibilità PHP**: PHP 7.1 - 8.5
-   **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Non sono richieste configurazioni speciali del server oltre a un ambiente di hosting PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

Il modulo "Cerca e sostituisci testo nei campi prodotto" non ha una pagina di configurazione tradizionale con impostazioni come interruttori o campi di input. Invece, si integra direttamente nell'elenco prodotti di PrestaShop, fornendo una nuova azione per eseguire operazioni di ricerca e sostituzione.

### 2.1 Accesso allo strumento di ricerca e sostituzione

La funzionalità del modulo è accessibile direttamente dall'elenco prodotti di PrestaShop:

1.  **Naviga all'elenco prodotti:**
    -   Nel tuo Back Office di PrestaShop, vai su **Catalogo > Prodotti**.
2.  **Seleziona i prodotti:**
    -   Puoi selezionare uno o più prodotti specifici spuntando le caselle accanto ad essi, oppure puoi scegliere di applicare la ricerca e sostituzione a *tutti* i prodotti attualmente visualizzati nell'elenco (ad esempio, se hai filtrato l'elenco).
3.  **Accedi al menu Azioni di massa:**
    -   Dopo aver selezionato i prodotti, apparirà un menu a discesa "Azioni di massa" (solitamente nella parte superiore o inferiore dell'elenco prodotti).
4.  **Seleziona "Cerca e sostituisci testo nei campi prodotto":**
    -   Clicca sul menu a discesa "Azioni di massa" e seleziona l'opzione etichettata **"Cerca e sostituisci testo nei campi prodotto"**.

### 2.2 L'interfaccia di ricerca e sostituzione

Una volta selezionata l'azione "Cerca e sostituisci testo nei campi prodotto", apparirà una finestra modale o un'interfaccia dedicata. Qui è dove definisci la tua operazione di ricerca e sostituzione.

**Campi disponibili per la ricerca e sostituzione:**
Il modulo ti consente di mirare a vari campi di testo associati ai tuoi prodotti. Questi tipicamente includono:
-   **Nome prodotto:** Il titolo principale del tuo prodotto.
-   **Descrizione breve:** Il breve riassunto spesso visualizzato vicino all'immagine del prodotto.
-   **Descrizione:** La descrizione completa e dettagliata del prodotto.
-   **Meta titolo:** Il titolo visualizzato nelle schede del browser e nei risultati dei motori di ricerca.
-   **Meta descrizione:** Il breve riassunto visualizzato sotto il titolo nei risultati dei motori di ricerca.
-   **URL amichevole:** La parte SEO-friendly dell'indirizzo web del prodotto.
-   **Tag:** Parole chiave associate al prodotto.
-   **Caratteristiche:** Valori di caratteristiche di prodotto personalizzate (es. "Colore: Rosso" - potresti sostituire "Rosso" con "Cremisi").
-   **Valori attributo:** Valori per gli attributi del prodotto (es. "Taglia: S" - potresti sostituire "S" con "Piccolo").
-   **Campi di personalizzazione:** Campi di testo che i clienti possono compilare per la personalizzazione del prodotto.

**Impostazioni chiave all'interno dell'interfaccia:**

-   **Cerca:**
    -   **Cosa fa questa impostazione:** Questa è la frase di testo esatta che vuoi trovare all'interno dei campi prodotto selezionati.
    -   **Effetto della modifica di questa impostazione:** Il modulo cercherà questa precisa stringa di caratteri. È sensibile alle maiuscole/minuscole per impostazione predefinita, a meno che non sia fornita un'opzione "Ignora maiuscole/minuscole" (controlla l'interfaccia per questo).
    -   **Valore consigliato:** Inserisci il testo esatto che desideri trovare.
    -   **Scenario/esempio del commerciante:** Se vuoi cambiare "vecchio nome del marchio" in "nuovo nome del marchio", qui inserirai "vecchio nome del marchio".

-   **Sostituisci con:**
    -   **Cosa fa questa impostazione:** Questa è la nuova frase di testo che sostituirà ogni istanza del testo "Cerca" trovata.
    -   **Effetto della modifica di questa impostazione:** Tutte le occorrenze del testo "Cerca" verranno aggiornate con questo nuovo testo. Se lasciato vuoto, il testo "Cerca" verrà eliminato.
    -   **Valore consigliato:** Inserisci il nuovo testo che desideri utilizzare.
    -   **Scenario/esempio del commerciante:** Seguendo l'esempio precedente, qui inserirai "nuovo nome del marchio".

-   **Seleziona i campi in cui cercare:**
    -   **Cosa fa questa impostazione:** Questo è un elenco di caselle di controllo o un menu a discesa a selezione multipla in cui scegli quali specifici campi di testo del prodotto (es. "Descrizione", "Descrizione breve", "Meta titolo") il modulo dovrebbe elaborare.
    -   **Effetto della modifica di questa impostazione:** Solo i campi selezionati verranno scansionati e modificati. I campi non selezionati rimarranno intatti.
    -   **Valore consigliato:** Seleziona solo i campi pertinenti al tuo compito attuale per evitare modifiche indesiderate.
    -   **Scenario/esempio del commerciante:** Se vuoi aggiornare solo la descrizione principale del prodotto, seleziona solo "Descrizione". Se stai aggiornando un nome di marca ovunque, potresti selezionare "Nome prodotto", "Descrizione breve", "Descrizione", "Meta titolo" e "Meta descrizione".

-   **Applica ai prodotti selezionati / Applica a tutti i prodotti filtrati:**
    -   **Cosa fa questa impostazione:** Questo conferma se l'operazione si applica solo ai prodotti che hai selezionato manualmente nell'elenco, o a tutti i prodotti attualmente visibili nell'elenco prodotti (che potrebbe essere un sottoinsieme filtrato).
    -   **Effetto della modifica di questa impostazione:** Determina l'ambito dell'operazione. Fai molta attenzione con "tutti i prodotti filtrati" per assicurarti che i tuoi filtri siano applicati correttamente.
    -   **Valore consigliato:** Controlla sempre due volte la selezione dei prodotti prima di procedere.
    -   **Scenario/esempio del commerciante:** Se hai filtrato l'elenco prodotti per mostrare solo i prodotti di una categoria specifica, e poi scegli "Applica a tutti i prodotti filtrati", le modifiche influenzeranno solo i prodotti di quella categoria.

-   **Sensibile alle maiuscole / Insensibile alle maiuscole (se disponibile):**
    -   **Cosa fa questa impostazione:** Determina se la ricerca deve distinguere tra lettere maiuscole e minuscole.
    -   **Effetto della modifica di questa impostazione:**
        -   *Sensibile alle maiuscole:* "Apple" non corrisponderà a "apple".
        -   *Insensibile alle maiuscole:* "Apple" corrisponderà a "apple", "APPLE", "Apple", ecc.
    -   **Valore consigliato:** Usa l'opzione insensibile alle maiuscole per sostituzioni ampie (es. correggere un errore di battitura comune che potrebbe apparire in diversi casi). Usa l'opzione sensibile alle maiuscole per sostituzioni precise dove la capitalizzazione è importante.
    -   **Scenario/esempio del commerciante:** Se vuoi sostituire "ProdottoX" con "Prodotto Y", ma alcune descrizioni potrebbero avere "prodottoX", l'uso dell'opzione insensibile alle maiuscole catturerà entrambi.

-   **Anteprima / Simulazione (se disponibile):**
    -   **Cosa fa questa impostazione:** Alcuni strumenti avanzati di ricerca e sostituzione offrono una modalità "anteprima" o "simulazione" che mostra quali modifiche *verrebbero* apportate senza effettivamente salvarle.
    -   **Effetto della modifica di questa impostazione:** Ti consente di rivedere l'impatto della tua operazione prima di confermare, prevenendo la perdita accidentale di dati.
    -   **Valore consigliato:** Utilizza sempre un'anteprima se disponibile, specialmente per operazioni su larga scala.
    -   **Scenario/esempio del commerciante:** Prima di sostituire "vecchio" con "nuovo" su 1000 prodotti, un'anteprima ti mostrerebbe esattamente quali prodotti e campi sarebbero interessati.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Elenco prodotti (Azioni di massa) | Cerca | Definito dall'utente | La stringa di testo esatta da trovare. Sensibile alle maiuscole/minuscole a meno che non specificato. |
| Elenco prodotti (Azioni di massa) | Sostituisci con | Definito dall'utente | La stringa di testo con cui sostituire il testo 'Cerca'. Vuoto elimina il testo. |
| Elenco prodotti (Azioni di massa) | Seleziona i campi in cui cercare | Definito dall'utente | Caselle di controllo per selezionare quali campi prodotto (descrizione, nome, meta, ecc.) modificare. |
| Elenco prodotti (Azioni di massa) | Applica ai prodotti selezionati / a tutti i prodotti filtrati | Definito dall'utente | Definisce l'ambito dell'operazione: solo i prodotti selezionati o tutti i prodotti attualmente filtrati. |
| Elenco prodotti (Azioni di massa) | Sensibile alle maiuscole / Insensibile alle maiuscole | (Controlla l'interfaccia del modulo) | Determina se la ricerca distingue tra lettere maiuscole e minuscole. |
| Elenco prodotti (Azioni di massa) | Anteprima / Simulazione | (Se disponibile, usa sempre) | Mostra le modifiche potenziali prima di applicarle, prevenendo errori. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho eseguito la ricerca e sostituzione, ma non vedo le modifiche sul mio sito web.**
R: PrestaShop utilizza la cache per velocizzare il tuo negozio. Dopo aver apportato modifiche nel back office, spesso è necessario svuotare la cache affinché appaiano nel front office.
    -   Vai su **Parametri avanzati > Prestazioni**.
    -   Clicca su "Svuota la cache" nell'angolo in alto a destra.
    -   Se utilizzi un modulo di caching di terze parti o un CDN, svuota anche le loro cache.

**D: Il modulo non appare nel menu "Azioni di massa" nell'elenco prodotti.**
R:
    1.  **Verifica l'installazione:** Assicurati che il modulo sia correttamente installato e abilitato in **Moduli > Gestione moduli**.
    2.  **Permessi:** Verifica che il tuo account utente abbia i permessi necessari per gestire moduli e prodotti.
    3.  **Conflitti tra moduli:** Raramente, un altro modulo che modifica pesantemente l'elenco prodotti o le azioni di massa potrebbe entrare in conflitto. Prova a disabilitare temporaneamente altri moduli installati di recente per vedere se il problema si risolve.

**D: Ho accidentalmente sostituito il testo sbagliato o ho commesso un errore. Come posso annullarlo?**
R: Sfortunatamente, il modulo esegue un aggiornamento diretto del database e non esiste un pulsante "annulla" integrato. Questo è il motivo per cui i backup sono cruciali.
    -   **Ripristina da backup:** Il modo più sicuro per annullare è ripristinare il database da un backup effettuato *prima* di eseguire l'operazione.
    -   **Esegui un'operazione inversa:** Se hai cambiato solo una semplice frase, potresti essere in grado di eseguire un'altra operazione di ricerca e sostituzione per ripristinarla (es. cerca "nuovo testo" e sostituisci con "vecchio testo"). Questo è rischioso e funziona solo per sostituzioni semplici e dirette.

**D: Posso usare questo modulo per negozi multilingue?**
R: Sì, il modulo opera sui campi prodotto, che sono spesso multilingue in PrestaShop. Quando selezioni campi come "Descrizione" o "Nome prodotto", il modulo applicherà tipicamente la ricerca e sostituzione a tutte le lingue attive per quei campi. L'interfaccia dovrebbe consentirti di specificare quali lingue targetizzare se tale opzione è disponibile.

**D: L'operazione di ricerca e sostituzione è molto lenta o va in timeout per un gran numero di prodotti.**
R:
    1.  **Risorse del server:** Operazioni su larga scala su migliaia di prodotti possono essere intensive in termini di risorse. Assicurati che il tuo server abbia limiti di memoria PHP e tempo di esecuzione adeguati. Potrebbe essere necessario aumentare `memory_limit` e `max_execution_time` nel tuo `php.ini` (consulta il tuo provider di hosting o webmaster).
    2.  **Elabora in lotti:** Se possibile, filtra l'elenco prodotti ed esegui l'operazione su lotti più piccoli di prodotti (es. per categoria, marca o intervallo di ID) invece di provare a elaborare l'intero catalogo in una volta sola.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce una panoramica tecnica per sviluppatori e webmaster che desiderano comprendere, eseguire il debug o estendere il modulo "Cerca e sostituisci testo nei campi prodotto".

### 4.1 Panoramica dell'architettura
Il modulo `snrp` è un modulo PrestaShop semplice, principalmente focalizzato sull'estensione della funzionalità dell'elenco prodotti del Back Office. Sfrutta il sistema di hook di PrestaShop per iniettare una nuova azione di massa nel controller `AdminProducts`. La logica principale risiede nel file principale del modulo, gestendo la visualizzazione del modulo di ricerca/sostituzione e l'esecuzione degli aggiornamenti del database. Non utilizza classi `ObjectModel` personalizzate o controller admin dedicati, ma piuttosto estende le viste admin esistenti di PrestaShop.

### 4.2 Controller (`controllers/`)
Questo modulo non introduce alcun controller Front-Office o Back-Office personalizzato. La sua funzionalità è integrata nel controller `AdminProducts` esistente tramite hook.

### 4.3 Classi e modelli principali (`classes/`)
Questo modulo non definisce alcuna classe personalizzata in una directory `classes/`. Tutta la logica principale è contenuta nel file principale del modulo `snrp/index.php`. Il modulo interagisce direttamente con gli `ObjectModel` di PrestaShop `Product` e `ProductLang`, e potenzialmente con i dati di `FeatureValue`, `AttributeGroup` e `Tag`, eseguendo aggiornamenti SQL basati sull'input dell'utente.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`snrp/views/js/snrp.js`**
    *   **Ambito:** Back-office (in particolare, la pagina dell'elenco `AdminProducts`).
    *   **Responsabilità:** Questo script è responsabile del comportamento lato client dello strumento di ricerca e sostituzione.
        *   Probabilmente lega un listener di eventi all'opzione "Cerca e sostituisci testo nei campi prodotto" all'interno del menu a discesa "Azioni di massa".
        *   Quando selezionato, attiva la visualizzazione della finestra modale o del modulo in cui l'utente inserisce il termine di ricerca, il termine di sostituzione e seleziona i campi target.
        *   Gestisce la richiesta AJAX al metodo `getContent()` del modulo (o a un endpoint AJAX dedicato se implementato all'interno di `index.php`) per inviare i parametri di ricerca e sostituzione.
        *   Gestisce il feedback dell'interfaccia utente durante e dopo l'operazione (es. spinner di caricamento, messaggi di successo/errore).
        *   Potrebbe includere la logica di validazione per i campi di input prima dell'invio.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`snrp/views/css/snrp.css`**
    *   **Ambito:** Back-office (in particolare, la pagina dell'elenco `AdminProducts`).
    *   **Responsabilità:** Questo foglio di stile fornisce lo stile visivo per l'interfaccia di ricerca e sostituzione.
        *   Definisce l'aspetto della finestra modale (dimensioni, posizionamento, overlay di sfondo).
        *   Stilizza i campi di input, i pulsanti, le caselle di controllo e qualsiasi altro elemento dell'interfaccia utente all'interno del modulo di ricerca e sostituzione.
        *   Garantisce che l'interfaccia si integri visivamente con il tema del Back Office di PrestaShop.
    *   **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere:** Gli sviluppatori possono ispezionare l'HTML generato della modale per identificare nomi di classe specifici (es. `.snrp-modal`, `.snrp-form-group`, `.snrp-button`) per personalizzarne l'aspetto nei loro temi admin personalizzati o tramite `override/css/admin.css`.

### 4.6 Struttura del template Smarty (`views/templates/`)
La descrizione del modulo indica l'assenza di file `.tpl` in `views/templates/`. Ciò suggerisce che il modulo di configurazione e l'interfaccia modale di ricerca/sostituzione sono probabilmente renderizzati direttamente all'interno del metodo `getContent()` di `snrp/index.php` utilizzando HTML e PHP grezzi, o generando dinamicamente gli elementi del modulo tramite JavaScript.

Se viene utilizzata una modale, è possibile che la struttura HTML venga iniettata direttamente nel DOM da `snrp.js` o renderizzata come parte della risposta `getContent()`.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    *   Questo modulo non crea tabelle di database personalizzate.
    *   Modifica direttamente le tabelle PrestaShop esistenti, principalmente:
        *   `ps_product_lang`: Per nomi di prodotti, descrizioni brevi, descrizioni, meta titoli, meta descrizioni e URL amichevoli (campi specifici per la lingua).
        *   `ps_tag`: Per i tag dei prodotti.
        *   Potenzialmente `ps_feature_product` e `ps_product_attribute_lang` se i valori delle caratteristiche e i valori degli attributi sono targetizzati.
    *   Le impostazioni di configurazione (se presenti) sarebbero tipicamente memorizzate in `ps_configuration`.

-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| :-------- | :--------------- | :---------------- |
| `displayBackOfficeHeader` | Renderizza nella sezione `<head>` del Back Office. | Utilizzato per includere `snrp.js` e `snrp.css` nelle pagine admin pertinenti (es. `AdminProducts`). |
| `displayAdminProductsExtra` | Renderizza contenuto aggiuntivo nella pagina dell'elenco `AdminProducts`. | Questo hook è probabilmente utilizzato per iniettare la struttura HTML per l'opzione "Cerca e sostituisci testo nei campi prodotto" nel menu a discesa "Azioni di massa" o per aggiungere un pulsante che attiva la modale. |
| `actionProductUpdate` / `actionObjectProductUpdateAfter` | Eseguito dopo l'aggiornamento di un prodotto. | Sebbene non esplicitamente dichiarato, il modulo potrebbe agganciarsi a questi per eseguire azioni aggiuntive o logging dopo un'operazione di ricerca e sostituzione riuscita, anche se gli aggiornamenti SQL diretti sono più probabili per le prestazioni. |
| `actionAdminProductsListingResultsModifier` | Modifica i risultati dell'elenco prodotti. | Meno probabile per questo modulo, ma potrebbe essere utilizzato per aggiungere una colonna o modificare i dati visualizzati prima che l'azione di ricerca/sostituzione venga attivata. |

La funzionalità principale di esecuzione della logica di ricerca e sostituzione sarà gestita all'interno del metodo `getContent()` del modulo (o di un metodo AJAX dedicato all'interno di `index.php`) quando il modulo viene inviato, elaborando gli ID e i campi dei prodotti selezionati.

## 5. Supporto ufficiale e aggiornamenti
Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Cerca e sostituisci testo nei campi prodotto", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda possiate avere riguardo alla funzionalità e compatibilità del modulo.
