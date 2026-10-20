---
title: "Aggiornamento quantità in massa pro - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Aggiornamento quantità in massa pro di MyPresta.eu."
sidebar:
  label: "Aggiornamento quantità in massa pro - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Mass quantity update pro su MyPresta.eu](https://mypresta.eu/modules/administration-tools/mass-quantity-update-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/mass-quantity-update-pro/)
>
> ---


# Aggiornamento quantità in massa pro

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

Il modulo "Aggiornamento quantità in massa pro" fornisce una singola e intuitiva schermata di configurazione nel back office di PrestaShop dove definisci i prodotti da aggiornare e le modifiche di quantità da applicare.

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Per accedere alla configurazione del modulo, naviga su **Moduli > Gestione moduli**, cerca "Aggiornamento quantità in massa pro" e clicca sul pulsante "Configura".

La pagina di configurazione è divisa in due sezioni principali: **Prodotti target** e **Cosa fare?**.

#### 2.1.1 Prodotti target

Questa sezione ti permette di definire *quali* prodotti o combinazioni di prodotti saranno interessati dall'aggiornamento della quantità. Puoi selezionare i prodotti in base a vari criteri.

-   **Cosa fa questa impostazione:** Questa sezione definisce l'ambito del tuo aggiornamento di quantità. Scegli il gruppo specifico di prodotti che avranno le loro quantità modificate.
-   **Effetto della modifica di questa impostazione:** Solo i prodotti che corrispondono ai criteri selezionati saranno considerati per l'aggiornamento della quantità. Se nessun criterio è selezionato, nessun prodotto sarà mirato.
-   **Valore consigliato:** Seleziona uno o più criteri che definiscono precisamente i prodotti che intendi modificare.

**Criteri disponibili:**

1.  **Prodotti da categorie:**

    -   **Cosa fa questa impostazione:** Ti permette di selezionare una o più categorie di prodotti specifiche. Tutti i prodotti (e le loro combinazioni) appartenenti a queste categorie saranno mirati.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando selezionato:* I prodotti all'interno delle categorie scelte saranno inclusi.
        -   *Quando non selezionato:* I prodotti non vengono filtrati per categoria.
    -   **Valore consigliato:** Seleziona questa opzione se devi aggiornare lo stock per un'intera linea di prodotti o un reparto.
    -   **Scenario / esempio del commerciante:** Hai ricevuto una nuova spedizione per tutti i prodotti nella tua categoria "Collezione Estiva". Puoi selezionare questa categoria per aggiornare il loro stock.
2.  **Prodotti per marca:**

    -   **Cosa fa questa impostazione:** Ti permette di selezionare una o più marche di prodotti (produttori) specifiche. Tutti i prodotti (e le loro combinazioni) associati a queste marche saranno mirati.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando selezionato:* I prodotti delle marche scelte saranno inclusi.
        -   *Quando non selezionato:* I prodotti non vengono filtrati per marca.
    -   **Valore consigliato:** Seleziona questa opzione se devi aggiornare lo stock per prodotti di un particolare fornitore o marca.
    -   **Scenario / esempio del commerciante:** Il tuo fornitore "Fashionista Inc." ha consegnato nuovo stock. Selezioni "Fashionista Inc." per aggiornare tutti i loro prodotti.
3.  **Prodotti per caratteristiche:**

    -   **Cosa fa questa impostazione:** Ti permette di selezionare prodotti in base alle loro caratteristiche assegnate (es. "Colore: Rosso", "Materiale: Cotone"). Puoi scegliere una caratteristica e poi valori specifici per quella caratteristica.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando selezionato:* Solo i prodotti che possiedono la caratteristica e il valore specificati saranno inclusi.
        -   *Quando non selezionato:* I prodotti non vengono filtrati per caratteristiche.
    -   **Valore consigliato:** Utile per aggiornamenti altamente specifici basati sulle caratteristiche del prodotto.
    -   **Scenario / esempio del commerciante:** Vuoi aggiornare lo stock per tutte le magliette in "Cotone Biologico". Selezioni "Materiale" come caratteristica e "Cotone Biologico" come valore.
4.  **Prodotti per attributi:**

    -   **Cosa fa questa impostazione:** Ti permette di selezionare prodotti in base ai loro attributi (es. "Taglia: M", "Colore: Blu"). Questo è particolarmente utile per le combinazioni di prodotti.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando selezionato:* Solo le combinazioni di prodotti con l'attributo e il valore specificati saranno incluse.
        -   *Quando non selezionato:* I prodotti non vengono filtrati per attributi.
    -   **Valore consigliato:** Essenziale per gestire lo stock di specifiche varianti di prodotto.
    -   **Scenario / esempio del commerciante:** Hai ricevuto una nuova consegna di magliette "Taglia L". Selezioni "Taglia" come attributo e "L" come valore per aggiornare solo quelle combinazioni.
5.  **Prodotti per associazioni di regole fiscali:**

    -   **Cosa fa questa impostazione:** Ti permette di selezionare prodotti in base al gruppo di regole fiscali applicato ad essi.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando selezionato:* Solo i prodotti associati al gruppo di regole fiscali scelto saranno inclusi.
        -   *Quando non selezionato:* I prodotti non vengono filtrati per regola fiscale.
    -   **Valore consigliato:** Utile per negozi con strutture fiscali complesse o quando gli aggiornamenti di stock sono legati all'inventario relativo alle tasse.
    -   **Scenario / esempio del commerciante:** Devi aggiustare lo stock per tutti i prodotti soggetti a una specifica regola fiscale "Dazio d'importazione".
6.  **Prodotti specifici:**

    -   **Cosa fa questa impostazione:** Fornisce una casella di ricerca con completamento automatico per selezionare manualmente i singoli prodotti per nome.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando i prodotti vengono aggiunti:* Solo i prodotti esplicitamente selezionati (e le loro combinazioni) saranno mirati.
        -   *Quando vuoto:* Nessun prodotto specifico viene mirato in questo modo.
    -   **Valore consigliato:** Usa questa opzione per aggiornamenti molto precisi su un piccolo set di prodotti selezionati manualmente.
    -   **Scenario / esempio del commerciante:** Devi aggiornare lo stock per "Prodotto A", "Prodotto B" e "Prodotto C" che non sono correlati per categoria o marca.

#### 2.1.2 Cosa fare?

Questa sezione definisce *come* verranno modificate le quantità dei prodotti target.

-   **Cosa fa questa impostazione:** Questa sezione specifica il tipo di modifica della quantità (aumento, diminuzione o impostazione a un valore fisso) e l'entità della modifica.
-   **Effetto della modifica di questa impostazione:** L'operazione selezionata verrà applicata alle quantità di tutti i prodotti definiti nella sezione "Prodotti target".
-   **Valore consigliato:** Scegli l'operazione che riflette accuratamente la tua regolazione dell'inventario.

**Operazioni disponibili:**

1.  **Aumenta quantità di:**

    -   **Cosa fa questa impostazione:** Aggiunge un numero specificato alla quantità corrente di ogni prodotto/combinazione target.
    -   **Effetto della modifica di questa impostazione:** Il livello di stock per ogni articolo target aumenterà dell'importo inserito.
    -   **Valore consigliato:** Utilizzare quando arriva nuovo stock. Inserire un numero intero positivo (es. `10`).
    -   **Scenario / esempio del commerciante:** Hai ricevuto 50 unità di un prodotto. Selezioni "Aumenta quantità di" e inserisci `50`.
2.  **Diminuisci quantità di:**

    -   **Cosa fa questa impostazione:** Sottrae un numero specificato dalla quantità corrente di ogni prodotto/combinazione target.
    -   **Effetto della modifica di questa impostazione:** Il livello di stock per ogni articolo target diminuirà dell'importo inserito.
    -   **Valore consigliato:** Utilizzare quando lo stock deve essere ridotto a causa di danni, resi o uso interno. Inserire un numero intero positivo (es. `5`).
    -   **Scenario / esempio del commerciante:** 5 articoli sono stati danneggiati nel magazzino. Selezioni "Diminuisci quantità di" e inserisci `5`.
3.  **Imposta quantità a:**

    -   **Cosa fa questa impostazione:** Modifica la quantità corrente di ogni prodotto/combinazione target a un numero specifico e fisso.
    -   **Effetto della modifica di questa impostazione:** Il livello di stock per ogni articolo target diventerà esattamente l'importo inserito, indipendentemente dalla sua quantità precedente.
    -   **Valore consigliato:** Utilizzare quando è necessario sincronizzare lo stock con un sistema esterno o correggere un conteggio assoluto dello stock. Inserire un numero intero non negativo (es. `100`).
    -   **Scenario / esempio del commerciante:** Dopo un conteggio completo dell'inventario, sai di avere esattamente 100 unità di un prodotto. Selezioni "Imposta quantità a" e inserisci `100`.

**Nota importante:** Dopo aver definito sia "Prodotti target" che "Cosa fare?", devi cliccare sul pulsante **"Aggiorna quantità"** per applicare le modifiche. Non esiste un pulsante "annulla", quindi controlla sempre due volte le tue selezioni prima di confermare.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | **Prodotti target** | | Definisce quali prodotti/combinazioni saranno interessati. |
| | Prodotti da categorie | Seleziona secondo necessità | Mira a tutti i prodotti all'interno delle categorie scelte. |
| | Prodotti per marca | Seleziona secondo necessità | Mira a tutti i prodotti delle marche scelte. |
| | Prodotti per caratteristiche | Seleziona secondo necessità | Mira a prodotti con caratteristiche/valori specifici. |
| | Prodotti per attributi | Seleziona secondo necessità | Mira a combinazioni di prodotti con attributi/valori specifici. |
| | Prodotti per associazioni di regole fiscali | Seleziona secondo necessità | Mira a prodotti associati alle regole fiscali scelte. |
| | Prodotti specifici | Seleziona secondo necessità | Mira a prodotti selezionati individualmente. |
| | **Cosa fare?** | | Definisce come verranno modificate le quantità. |
| | Aumenta quantità di | Inserisci un numero intero positivo | Aggiunge l'importo specificato allo stock corrente. |
| | Diminuisci quantità di | Inserisci un numero intero positivo | Sottrae l'importo specificato dallo stock corrente. |
| | Imposta quantità a | Inserisci un numero intero non negativo | Imposta lo stock a un importo esatto e specificato. |
| | **Pulsante Aggiorna quantità** | Clicca per applicare | Esegue le modifiche di quantità definite. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho aggiornato le quantità, ma il mio negozio mostra ancora i vecchi numeri. Cosa c'è che non va?**
**R1:** Questo è solitamente un problema di cache. PrestaShop utilizza la cache per velocizzare il tuo negozio.

-   **Soluzione:** Vai su **Parametri avanzati > Prestazioni** nel back office di PrestaShop. Clicca su "Svuota cache" (o "Svuota cache Smarty" / "Svuota cache" a seconda della tua versione di PrestaShop). Questo dovrebbe forzare il tuo negozio a visualizzare le quantità aggiornate.

**D2: Ho commesso un errore e ho aggiornato i prodotti/quantità sbagliati. Posso annullare?**
**R2:** Il modulo non ha un pulsante "annulla". Questo è il motivo per cui è fondamentale ricontrollare le tue selezioni prima di cliccare su "Aggiorna quantità".

-   **Soluzione:** Se hai un backup recente del tuo database, puoi ripristinarlo (anche se questo potrebbe annullare altre modifiche recenti). Altrimenti, dovrai correggere manualmente le quantità per i prodotti interessati, o utilizzare nuovamente il modulo con le impostazioni corrette per riadattarle. Ad esempio, se hai accidentalmente aumentato di 10, puoi diminuire di 10.

**D3: Il modulo non trova prodotti quando digito nella casella di ricerca "Prodotti specifici".**
**R3:** Assicurati di digitare il nome completo o parziale di un prodotto esistente nel tuo negozio. La funzione di completamento automatico si basa su JavaScript.

-   **Soluzione:**
    1.  Controlla la console del tuo browser per eventuali errori JavaScript (tasto F12, poi scheda "Console").
    2.  Prova a svuotare la cache del tuo browser.
    3.  Assicurati che il tuo negozio PrestaShop sia in esecuzione su una versione PHP compatibile (vedi sezione 3).
    4.  Se il problema persiste, contatta il supporto MyPresta.eu.

**D4: Posso aggiornare le quantità per prodotti che hanno combinazioni (attributi)?**
**R4:** Sì, assolutamente! Il modulo è progettato per gestire le combinazioni di prodotti. Quando selezioni prodotti per categoria, marca, caratteristica o prodotto specifico, applicherà la modifica della quantità a tutte le combinazioni associate di quei prodotti. Se utilizzi "Prodotti per attributi", puoi persino mirare direttamente a combinazioni specifiche.

**D5: Il modulo sembra lento quando aggiorna un numero molto elevato di prodotti.**
**R5:** L'aggiornamento di migliaia di prodotti può essere intensivo in termini di risorse.

-   **Soluzione:**
    1.  Assicurati che il tuo server soddisfi le specifiche raccomandate da PrestaShop.
    2.  Aumenta i limiti di tempo di esecuzione PHP (`max_execution_time`) e i limiti di memoria (`memory_limit`) nel tuo file `php.ini` (consulta il tuo provider di hosting o webmaster).
    3.  Se possibile, suddividi gli aggiornamenti molto grandi in lotti più piccoli (es. aggiorna una categoria alla volta invece di tutte le categorie).

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster che lavorano con il modulo "Aggiornamento quantità in massa pro".

### 4.1 Panoramica dell'architettura

Il modulo `MassQtyPro` segue un'architettura standard per i moduli PrestaShop, sfruttando principalmente la classe `Module` per la sua funzionalità principale e il metodo `getContent()` per la sua singola interfaccia di configurazione del back-office. Integra uno strumento di ricerca personalizzato per la selezione dei prodotti, utilizzando AJAX per la funzionalità di completamento automatico. Il modulo interagisce direttamente con le classi `Product` e `StockAvailable` di PrestaShop per eseguire gli aggiornamenti di quantità.

### 4.2 Controller (`controllers/`)

Il modulo non utilizza controller front-office o back-office personalizzati. Tutta la logica di configurazione ed elaborazione per il back-office è gestita all'interno del metodo `getContent()` della classe principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

Il modulo non definisce alcuna classe `ObjectModel` personalizzata o classi dedicate all'interno di una directory `classes/`. Tutta la logica principale risiede nel file `massqtypro.php`.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`massqtypro/lib/searchTool/views/js/autocomplete.js`**
    -   **Ambito:** Back-office (utilizzato nella pagina di configurazione del modulo).
    -   **Descrizione:** Questo script probabilmente implementa o integra una funzionalità generica di completamento automatico. Ascolta l'input dell'utente nei campi di testo (specificamente per la ricerca di prodotti) e invia richieste AJAX per recuperare i nomi dei prodotti corrispondenti. Quindi visualizza questi suggerimenti in un elenco a discesa, consentendo all'utente di selezionare i prodotti. Gestisce la visualizzazione e la selezione dei risultati del completamento automatico.
-   **`massqtypro/views/js/jquery.autocomplete.js`**
    -   **Ambito:** Back-office (utilizzato nella pagina di configurazione del modulo).
    -   **Descrizione:** Questo sembra essere un plugin jQuery per la funzionalità di completamento automatico. Fornisce il framework principale per la casella di ricerca dei prodotti nella pagina di configurazione del modulo. Gestisce le chiamate AJAX al server (probabilmente al metodo `getContent()` o a un hook specifico che fornisce i dati del prodotto), elabora la risposta JSON e rende i suggerimenti. Gestisce anche la selezione di un elemento dall'elenco e il popolamento del campo di input o di un campo nascosto con l'ID del prodotto selezionato.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`massqtypro/lib/searchTool/views/css/autocomplete.css`**
    -   **Ambito:** Back-office (stile per la pagina di configurazione del modulo).
    -   **Descrizione:** Questo foglio di stile fornisce la presentazione visiva per la casella di ricerca con completamento automatico e il suo elenco di suggerimenti. Definisce gli stili per il campo di input, il contenitore a discesa, i singoli elementi di suggerimento e potenzialmente gli stati di hover/attivo per una migliore interazione dell'utente. Gli sviluppatori possono sovrascrivere questi stili nel loro tema amministrativo personalizzato o aggiungendo regole CSS specifiche per mirare agli elementi del modulo.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo utilizza i template Smarty per il rendering del suo modulo di configurazione del back-office.

-   **`massqtypro/lib/searchTool/views/scripts.tpl`**
    -   **Ambito:** Back-office (incluso nella pagina di configurazione del modulo).
    -   **Descrizione:** Questo template probabilmente include i file JavaScript e CSS necessari per lo strumento di ricerca con completamento automatico. Potrebbe anche contenere JavaScript inline per inizializzare il plugin di completamento automatico su campi di input specifici, passando opzioni di configurazione e definendo funzioni di callback per quando un prodotto viene selezionato.
-   **`massqtypro/views/templates/admin/target_products.tpl`**
    -   **Ambito:** Back-office (parte del modulo di configurazione).
    -   **Descrizione:** Questo template rende la sezione "Prodotti target" della pagina di configurazione del modulo. Contiene l'HTML per tutti i criteri di selezione del prodotto: menu a discesa delle categorie, menu a discesa delle marche, selettori di caratteristiche/attributi, selettori di regole fiscali e il campo di input per il completamento automatico del prodotto specifico. Utilizza gli helper di modulo standard di PrestaShop e potenzialmente HTML personalizzato per gli elementi di selezione dinamici.
-   **`massqtypro/views/templates/admin/wtd.tpl`**
    -   **Ambito:** Back-office (parte del modulo di configurazione).
    -   **Descrizione:** Questo template rende la sezione "Cosa fare?" della pagina di configurazione del modulo. Contiene l'HTML per le operazioni di aggiornamento della quantità: pulsanti radio per "Aumenta", "Diminuisci" o "Imposta a", e il campo di input corrispondente per il valore della quantità. Include anche il pulsante di invio "Aggiorna quantità".
-   **`massqtypro/views/templates/hook/form.tpl`**
    -   **Ambito:** Back-office (modulo di configurazione principale).
    -   **Descrizione:** Questo è il template principale per la pagina di configurazione del modulo. Probabilmente racchiude i template `target_products.tpl` e `wtd.tpl`, combinandoli nel modulo di configurazione completo. Gestirebbe anche l'invio complessivo del modulo e visualizzerebbe eventuali messaggi di successo o di errore.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**: Il modulo non crea tabelle del database personalizzate. Interagisce principalmente con le tabelle esistenti di PrestaShop, in particolare `ps_product`, `ps_product_attribute`, `ps_stock_available`, `ps_category_product`, `ps_manufacturer`, `ps_feature_product`, `ps_product_attribute_combination` e `ps_tax_rule_group_product`. Le impostazioni di configurazione sono memorizzate in `ps_configuration`.
-   **Tabella degli hook registrati**:
    La funzionalità principale del modulo viene eseguita tramite il suo metodo `getContent()` nel back-office. Non si registra esplicitamente agli hook del front-office per scopi di visualizzazione. Tuttavia, il modulo potrebbe utilizzare internamente gli hook per azioni amministrative o recupero dati.

    | Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
    | --- | --- | --- |
    | `displayBackOfficeHeader` | Renderizza nella sezione `<head>` del Back Office. | Potenzialmente utilizzato per caricare CSS/JS specifici del modulo per la pagina di configurazione, anche se spesso gestito direttamente in `getContent()`. |
    | `actionProductUpdate` | Dopo l'aggiornamento di un prodotto. | Potrebbe essere utilizzato per la registrazione interna o per attivare azioni correlate, anche se non esplicitamente dichiarato nelle funzionalità. |
    | `actionUpdateQuantity` | Dopo l'aggiornamento della quantità di un prodotto. | Potrebbe essere utilizzato per la registrazione interna o per attivare azioni correlate, anche se non esplicitamente dichiarato nelle funzionalità. |

    La logica principale del modulo per gli aggiornamenti di quantità manipola direttamente le voci di `StockAvailable`, che attivano internamente i meccanismi di aggiornamento dello stock di PrestaShop.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto tecnico ufficiale, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere commercianti e sviluppatori con qualsiasi problema o domanda relativa al modulo "Aggiornamento quantità in massa pro".
