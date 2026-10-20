---
title: "Dividi combinazioni in prodotti separati - Manuale del commerciante e guida alla configurazione"
description: ""
sidebar:
  label: "Dividi combinazioni in prodotti separati - Manuale del commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Split combinations into separate products su MyPresta.eu](https://mypresta.eu/modules/administration-tools/split-combinations-into-separate-products.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/split-combinations-into-separate-products/)
>
> ---


# Dividi combinazioni in prodotti separati

## 1. Panoramica completa della configurazione (ogni impostazione raggruppata per schermata)

### 1.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale del modulo, accessibile cliccando su "Configura" dopo l'installazione.

#### Impostazioni generali

-   **Abilita modulo:**

    *   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare la funzionalità del modulo.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Le funzionalità del modulo, inclusa la capacità di dividere i prodotti e la sua logica di visualizzazione, diventano attive.
        *   *Quando disabilitato:* La funzionalità del modulo è completamente disattivata. Nessuna combinazione verrà divisa e gli eventuali prodotti divisi esistenti torneranno al loro stato originale o verranno gestiti come prodotti normali a seconda della logica interna del modulo.
    *   **Valore consigliato:** SÌ (una volta che sei pronto a utilizzare il modulo).
    *   **Scenario/esempio del commerciante:** Stai configurando il modulo per la prima volta e vuoi testarlo. Lo abiliti per vederne gli effetti. Se hai bisogno di disabilitarlo temporaneamente per manutenzione, puoi disattivarlo.
-   **Modalità di divisione:**

    *   **Cosa fa questa impostazione:** Determina come il modulo gestisce le combinazioni di prodotti. Puoi scegliere tra la creazione di nuovi prodotti effettivi per ogni combinazione o semplicemente la modifica del modo in cui vengono visualizzati nelle pagine di elenco.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato su "Crea prodotti separati per ogni combinazione":* Il modulo creerà fisicamente nuove voci di prodotto nel tuo database per ogni combinazione. Ogni nuovo prodotto avrà il proprio ID, URL, stock, prezzo, ecc. Questa è l'opzione più potente per la SEO e il controllo granulare.
        *   *Quando impostato su "Mostra una scheda per combinazione nelle liste di categoria, marca, fornitore, ricerca e best-seller (divisione virtuale)":* Il modulo *non* creerà nuovi prodotti. Invece, modificherà il modo in cui i prodotti esistenti con combinazioni vengono visualizzati nelle pagine di elenco, facendo *apparire* ogni combinazione come un prodotto separato. Il catalogo prodotti effettivo rimane invariato. Questo ha un impatto minore sulla SEO ma può migliorare l'esperienza di navigazione.
    *   **Valore consigliato:** "Crea prodotti separati per ogni combinazione" per la massima SEO e controllo, o "Mostra una scheda per combinazione..." per un miglioramento della visualizzazione più semplice.
    *   **Scenario/esempio del commerciante:** Vuoi che ogni colore e taglia della tua T-shirt abbia la propria pagina prodotto e si posizioni su Google. Scegli "Crea prodotti separati". Se vuoi solo rendere le tue pagine di categoria più pulite mostrando ogni variante senza creare nuovi prodotti, scegli "Mostra una scheda per combinazione."
-   **Dividi solo prodotti attivi:**

    *   **Cosa fa questa impostazione:** Controlla se il modulo deve elaborare solo i prodotti attualmente abilitati nel tuo negozio, o tutti i prodotti indipendentemente dal loro stato attivo.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Solo i prodotti attualmente impostati su "attivo" nel tuo catalogo PrestaShop avranno le loro combinazioni divise. I prodotti inattivi verranno ignorati.
        *   *Quando disabilitato:* Il modulo tenterà di dividere le combinazioni per tutti i prodotti, inclusi quelli attualmente inattivi.
    *   **Valore consigliato:** SÌ (per evitare di creare prodotti non necessari per articoli che non stai vendendo).
    *   **Scenario/esempio del commerciante:** Hai molti prodotti vecchi e inattivi nel tuo catalogo. Vuoi dividere le combinazioni solo per il tuo inventario attuale e attivo per mantenere il tuo negozio organizzato. Abiliti questa impostazione.
-   **Azione prodotto sorgente dopo la divisione:**

    *   **Cosa fa questa impostazione:** Definisce cosa succede al prodotto originale (quello con le combinazioni) dopo che le sue combinazioni sono state divise in nuovi prodotti individuali.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato su "Disabilita prodotto sorgente":* Il prodotto originale verrà contrassegnato come inattivo nel tuo catalogo. Non sarà più visibile nel front office.
        *   *Quando impostato su "Mantieni prodotto sorgente attivo":* Il prodotto originale rimarrà attivo e visibile nel tuo negozio. Potrebbe essere necessario regolare manualmente la sua visualizzazione o il suo contenuto per evitare confusione con i nuovi prodotti divisi.
        *   *Quando impostato su "Elimina prodotto sorgente":* Il prodotto originale verrà rimosso permanentemente dal tuo catalogo. Usare con estrema cautela!
    *   **Valore consigliato:** "Disabilita prodotto sorgente" o "Mantieni prodotto sorgente attivo" (a seconda della tua strategia). "Elimina prodotto sorgente" non è generalmente raccomandato a meno che tu non sia assolutamente sicuro.
    *   **Scenario/esempio del commerciante:** Hai diviso un prodotto "T-shirt" in "T-shirt - Rosso - S", "T-shirt - Blu - M", ecc. Vuoi che i clienti vedano solo le singole varianti, quindi scegli "Disabilita prodotto sorgente" per la "T-shirt" originale.
-   **Copia immagini prodotto:**

    *   **Cosa fa questa impostazione:** Determina se le immagini associate al prodotto originale e alle sue combinazioni devono essere copiate nei prodotti divisi appena creati.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Le immagini del prodotto originale e della sua combinazione specifica verranno duplicate e assegnate al nuovo prodotto diviso. Ciò garantisce che ogni nuovo prodotto abbia elementi visivi pertinenti.
        *   *Quando disabilitato:* I nuovi prodotti divisi verranno creati senza immagini. Dovresti quindi caricare manualmente le immagini per ogni nuovo prodotto, il che richiede molto tempo.
    *   **Valore consigliato:** SÌ.
    *   **Scenario/esempio del commerciante:** Hai una combinazione "T-shirt Rossa" con un'immagine specifica. Quando la dividi in "T-shirt - Rosso - Piccola", vuoi che l'immagine della t-shirt rossa venga automaticamente assegnata al nuovo prodotto.
-   **Combinazioni minime da dividere:**

    *   **Cosa fa questa impostazione:** Imposta una soglia per il numero di combinazioni che un prodotto deve avere prima che il modulo consideri di dividerlo. I prodotti con meno combinazioni di questo valore verranno ignorati.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato su un valore (ad esempio, 2):* Verranno elaborati solo i prodotti che hanno 2 o più combinazioni. I prodotti con una sola combinazione (o nessuna combinazione) verranno saltati.
        *   *Quando impostato su 0 o 1:* Tutti i prodotti con almeno una combinazione verranno considerati per la divisione.
    *   **Valore consigliato:** 2 (per evitare di dividere prodotti semplici che potrebbero non trarne beneficio).
    *   **Scenario/esempio del commerciante:** Hai alcuni prodotti con una sola combinazione (ad esempio, una T-shirt "Taglia Unica"). Non vuoi dividerli, ma vuoi dividere i prodotti con più colori e taglie. Imposti questo valore su 2.

#### Impostazioni del generatore di nomi

Queste impostazioni controllano come vengono generati i nomi dei nuovi prodotti divisi.

-   **Modello generatore di nomi:**

    *   **Cosa fa questa impostazione:** Ti consente di definire un modello personalizzato per la generazione dei nomi dei nuovi prodotti divisi. Puoi usare segnaposto per il nome del prodotto, i nomi dei gruppi di attributi e i nomi degli attributi.
    *   **Effetto della modifica di questa impostazione:** Il modulo userà questo modello per costruire il campo `name` per ogni nuovo prodotto.
    *   **Valore consigliato:** `[product_name] - [attribute_group_name]: [attribute_name]` (o simile, a seconda dello stile del tuo marchio).
    *   **Scenario/esempio del commerciante:** Il tuo prodotto originale è "Abito elegante". Ha combinazioni come "Colore: Rosso" e "Taglia: Piccola". Se il tuo modello è `[product_name] - [attribute_name]`, il nuovo nome del prodotto sarebbe "Abito elegante - Rosso".
-   **Modello generatore di URL:**

    *   **Cosa fa questa impostazione:** Simile al generatore di nomi, questo ti consente di definire un modello personalizzato per la generazione degli URL amichevoli (slug) dei nuovi prodotti divisi.
    *   **Effetto della modifica di questa impostazione:** Il modulo userà questo modello per costruire il campo `link_rewrite` per ogni nuovo prodotto.
    *   **Valore consigliato:** `[product_name]-[attribute_name]` (o simile, assicurandosi che sia SEO-friendly e unico).
    *   **Scenario/esempio del commerciante:** Usando l'esempio di "Abito elegante", se il tuo modello URL è `[product_name]-[attribute_name]`, il nuovo URL potrebbe essere `/abito-elegante-rosso`.
-   **Separatore per attributi multipli:**

    *   **Cosa fa questa impostazione:** Specifica il carattere o la stringa usata per separare i nomi di attributi multipli quando sono combinati nel nome del prodotto o nell'URL.
    *   **Effetto della modifica di questa impostazione:** Questo carattere verrà inserito tra i nomi degli attributi se un prodotto ha combinazioni da più gruppi di attributi (ad esempio, Colore e Taglia).
    *   **Valore consigliato:** `-` (trattino) per gli URL, `,` (virgola spazio) per i nomi.
    *   **Scenario/esempio del commerciante:** Se un prodotto è "T-shirt - Rosso - Piccola", il trattino è il separatore. Puoi cambiarlo in una barra `/` se preferisci.

#### Impostazioni avanzate

-   **Reindirizza vecchi URL:**

    *   **Cosa fa questa impostazione:** Se abilitata, il modulo creerà reindirizzamenti 301 dall'URL del prodotto originale (e potenzialmente dagli URL specifici delle combinazioni) all'URL del nuovo prodotto diviso. Questo è cruciale per la SEO.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* I motori di ricerca e gli utenti che accedono a vecchi URL verranno automaticamente reindirizzati alla pagina del nuovo prodotto corretta, preservando il valore SEO e prevenendo link interrotti.
        *   *Quando disabilitato:* I vecchi URL porteranno a errori 404 "Pagina non trovata", danneggiando la tua SEO e l'esperienza utente.
    *   **Valore consigliato:** SÌ.
    *   **Scenario/esempio del commerciante:** Hai diviso "T-shirt" in "T-shirt - Rosso - Piccola". Se un cliente o un motore di ricerca tenta di accedere alla vecchia pagina "T-shirt", verrà automaticamente inviato alla pagina del nuovo prodotto diviso più pertinente.
-   **Svuota cache dopo la divisione:**

    *   **Cosa fa questa impostazione:** Svuota automaticamente la cache di PrestaShop dopo l'esecuzione di un'operazione di divisione.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Garantisce che le modifiche apportate dal modulo (nuovi prodotti, reindirizzamenti) siano immediatamente visibili nel front office senza la necessità di svuotare manualmente la cache.
        *   *Quando disabilitato:* Potrebbe essere necessario svuotare manualmente la cache (Parametri avanzati > Prestazioni) affinché le modifiche appaiano.
    *   **Valore consigliato:** SÌ.
    *   **Scenario/esempio del commerciante:** Hai appena diviso un gran numero di prodotti. L'abilitazione di questa opzione garantisce che i tuoi clienti vedano subito i nuovi elenchi di prodotti senza che tu debba svuotare manualmente la cache.

### 1.2 Schermate di amministrazione dedicate e viste del controller

#### AdminMySplitProductsController (Back Office > Moduli > Dividi combinazioni in prodotti separati > Gestisci divisioni)

Questa schermata fornisce l'interfaccia per avviare, gestire e annullare le operazioni di divisione dei prodotti.

-   **Nome schermata e posizione nel menu:** "Gestisci divisioni" (accessibile dalla pagina di configurazione principale del modulo o potenzialmente da una nuova voce di menu sotto "Catalogo" o "Moduli").
-   **Azioni e impostazioni disponibili:**
    *   **Ricerca e selezione prodotti:** Una barra di ricerca e una funzione di completamento automatico per trovare prodotti specifici che desideri dividere.
    *   **Pulsante "Dividi prodotto":** Avvia il processo di divisione per il prodotto selezionato.
    *   **Pulsante "Annulla":** Ti consente di annullare un'operazione di divisione precedente per un prodotto specifico, ripristinando il prodotto originale e rimuovendo quelli divisi.
    *   **Tabella cronologia:** Un elenco di tutti i prodotti che sono stati divisi, che mostra:
        *   Nome prodotto originale
        *   Data di divisione
        *   Numero di combinazioni divise
        *   Stato (ad esempio, "Completato", "Annullato")
        *   Pulsanti azione (ad esempio, "Annulla", "Visualizza prodotti divisi")
-   **Effetto delle modifiche:**
    *   **Divisione di un prodotto:** Crea nuove voci di prodotto nel tuo catalogo in base alle combinazioni del prodotto selezionato e alle impostazioni di configurazione del modulo (nomi, URL, immagini, ecc.). Lo stato del prodotto originale potrebbe cambiare (ad esempio, disabilitato).
    *   **Annullamento di una divisione:** Elimina i prodotti creati durante la divisione e ripristina il prodotto originale al suo stato precedente alla divisione (ad esempio, lo riabilita, ripristina le sue combinazioni). Questa è una potente funzione di annullamento.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Usa la barra di ricerca per trovare il prodotto che desideri dividere.
    2.  Rivedi i nomi e gli URL proposti (se è disponibile un'anteprima).
    3.  Clicca su "Dividi prodotto".
    4.  Monitora la tabella della cronologia per lo stato.
    5.  Se commetti un errore o cambi idea, usa la funzione "Annulla" dalla tabella della cronologia.

#### index.php (mysplitproducts/controllers/admin/index.php)

Questo file probabilmente funge da segnaposto o da base per i controller di amministrazione del modulo, garantendo le migliori pratiche di sicurezza di PrestaShop impedendo l'elenco diretto delle directory. Non rappresenta una schermata distinta rivolta all'utente, ma fa parte della struttura interna del modulo.

### 1.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Pagina di configurazione del modulo** | Abilita modulo | SÌ | Interruttore principale per la funzionalità del modulo. |
| | Modalità di divisione | "Crea prodotti separati" | Come vengono gestite le combinazioni (nuovi prodotti vs. visualizzazione virtuale). |
| | Dividi solo prodotti attivi | SÌ | Elabora solo prodotti attivi. |
| | Azione prodotto sorgente dopo la divisione | "Disabilita prodotto sorgente" | Cosa succede al prodotto originale. |
| | Copia immagini prodotto | SÌ | Duplica le immagini nei nuovi prodotti divisi. |
| | Combinazioni minime da dividere | 2 | Soglia per la divisione dei prodotti. |
| | Modello generatore di nomi | `[product_name] - [attribute_group_name]: [attribute_name]` | Definisce i nomi dei nuovi prodotti. |
| | Modello generatore di URL | `[product_name]-[attribute_name]` | Definisce gli URL amichevoli dei nuovi prodotti. |
| | Separatore per attributi multipli | `-` (per URL), `,` (per nome) | Carattere per separare attributi multipli. |
| | Reindirizza vecchi URL | SÌ | Crea reindirizzamenti 301 per la SEO. |
| | Svuota cache dopo la divisione | SÌ | Svuota automaticamente la cache di PrestaShop. |
| **Gestisci divisioni (AdminMySplitProductsController)** | Ricerca e divisione prodotti | N/A | Trova e avvia la divisione per i prodotti. |
| | Annulla divisione | N/A | Annulla un'operazione di divisione precedente. |
| | Tabella cronologia | N/A | Visualizza e gestisci le operazioni di divisione passate. |

## 2. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Dopo aver diviso i prodotti, non vedo i nuovi prodotti nelle mie categorie o nei risultati di ricerca.**

-   **R:** La ragione più comune è la cache.
    *   **Soluzione:** Vai su **Parametri avanzati > Prestazioni** nel tuo Back Office di PrestaShop. Clicca su "Svuota cache" (o "Svuota cache Smarty" e "Svuota cache" per tutte le cache). Se l'impostazione del modulo "Svuota cache dopo la divisione" è abilitata, questo dovrebbe accadere automaticamente, ma a volte è necessario uno svuotamento manuale. Inoltre, assicurati che i nuovi prodotti siano impostati su "attivo" e associati alle categorie.

**D2: I miei vecchi URL di prodotto ora mostrano "Pagina non trovata" (errori 404).**

-   **R:** Questo di solito significa che la funzione di reindirizzamento non è attiva o non funziona correttamente.
    *   **Soluzione:** Vai alla pagina di configurazione del modulo e assicurati che "Reindirizza vecchi URL" sia impostato su SÌ. Se è già abilitato, svuota la cache di PrestaShop (Parametri avanzati > Prestazioni). Se il problema persiste, controlla il file `.htaccess` del tuo server per eventuali regole di riscrittura in conflitto, o contatta il supporto.

**D3: I nomi o gli URL dei miei nuovi prodotti divisi sembrano strani o non sono quelli che mi aspettavo.**

-   **R:** Questo è controllato dalle impostazioni "Modello generatore di nomi" e "Modello generatore di URL".
    *   **Soluzione:** Vai alla pagina di configurazione del modulo e rivedi questi modelli. Assicurati di utilizzare i segnaposto corretti (`[product_name]`, `[attribute_name]`, `[attribute_group_name]`) e che i separatori siano appropriati. Puoi testare diversi modelli su un singolo prodotto prima. Ricorda di svuotare la cache dopo aver apportato modifiche ai modelli.

**D4: Alcuni prodotti con combinazioni non sono stati divisi, anche se ho avviato il processo.**

-   **R:** Controlla l'impostazione "Combinazioni minime da dividere" nella configurazione del modulo.
    *   **Soluzione:** Se un prodotto ha meno combinazioni di questa soglia, verrà saltato. Regola questa impostazione se desideri dividere prodotti con meno varianti. Inoltre, assicurati che "Dividi solo prodotti attivi" non impedisca l'elaborazione di prodotti inattivi se questa è la tua intenzione.

**D5: Cosa succede ai carrelli dei clienti se divido un prodotto che hanno già aggiunto?**

-   **R:** Il modulo è progettato per gestire questo in modo elegante. I carrelli aperti esistenti che contengono una combinazione di un prodotto che è stato diviso verranno tipicamente aggiornati per riflettere il nuovo ID prodotto distinto. Ciò significa che il carrello del cliente conterrà ancora l'articolo corretto, ora collegato alla sua nuova voce di prodotto individuale. Tuttavia, è sempre meglio eseguire le divisioni durante periodi di basso traffico o testare accuratamente.

## 3. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 3.1 Panoramica dell'architettura

Il modulo "Dividi combinazioni in prodotti separati" (`mysplitproducts`) è costruito seguendo il modello MVC (Model-View-Controller) di PrestaShop. Sfrutta ampiamente `ObjectModel` per la persistenza dei dati, `AdminController` personalizzato per la sua interfaccia Back Office e un set di classi di servizio dedicate per incapsulare la logica complessa di divisione dei prodotti, denominazione e reindirizzamento. Il modulo estende la funzionalità principale di PrestaShop creando e gestendo dinamicamente entità prodotto, gestendo le riscritture URL e integrandosi con il gestore dei moduli. Si basa su un robusto sistema di logging interno e un pattern finder per un efficiente recupero dei dati.

### 3.2 Controller (`controllers/`)

-   **Controller Front-Office**: Nessuno esplicitamente definito nell'inventario fornito. La logica di visualizzazione del front-office per le divisioni virtuali o i reindirizzamenti è probabilmente gestita tramite hook all'interno del file `mysplitproducts.php` principale o tramite override.
-   **Controller Admin Back-Office**:

    -   `controllers/admin/AdminMySplitProductsController.php`
        -   **Nome classe e classe genitore:** `AdminMySplitProductsController` estende `ModuleAdminController`.
        -   **Nome scheda ed entità gestita:** Questo controller gestisce la funzionalità principale di divisione e ripristino dei prodotti. Presenta una vista a griglia/gestione per i prodotti che sono stati elaborati e consente agli amministratori di avviare nuove divisioni o annullare quelle esistenti. Interagisce con le classi `MspSplitEngine`, `MspLogger` e `MspRedirector`.
        -   **Responsabilità:** Gestisce la visualizzazione dell'interfaccia "Gestisci divisioni", elabora le richieste AJAX per la ricerca di prodotti, avvia il processo di divisione dei prodotti e gestisce le operazioni di ripristino. È l'hub centrale per le attività amministrative del modulo.
    -   `controllers/admin/index.php`
        -   **Nome classe e classe genitore:** N/A (non è un file di classe).
        -   **Responsabilità:** Questo è un file `index.php` vuoto standard posizionato nelle sottodirectory per impedire l'elenco delle directory, migliorando la sicurezza. Non contiene alcuna logica funzionale per il modulo.

### 3.3 Classi e modelli principali (`classes/`)

-   `classes/index.php`
    -   **Responsabilità:** `index.php` vuoto standard per la sicurezza, impedisce l'elenco delle directory.
-   `classes/MspAliasStore.php`
    -   **Con quale tabella del database interagisce:** Probabilmente `ps_mysplitproducts_alias` (tabella personalizzata) o `ps_configuration` per l'archiviazione di alias/reindirizzamenti.
    -   **Se estende ObjectModel:** Improbabile che estenda direttamente `ObjectModel` ma gestisce i dati relativi agli alias.
    -   **Metodi pubblici chiave e logica di business incapsulata:** Gestisce la mappatura tra gli ID prodotto/combinazione originali e gli ID prodotto divisi appena creati. Cruciale per la funzionalità di reindirizzamento e ripristino.
-   `classes/MspCatalog.php`
    -   **Con quale tabella del database interagisce:** `ps_product`, `ps_product_lang`, `ps_product_shop`, `ps_category_product`, `ps_image`, `ps_image_shop`, `ps_stock_available`, ecc. (tabelle prodotto principali di PrestaShop).
    -   **Se estende ObjectModel:** No, probabilmente una classe di servizio.
    -   **Metodi pubblici chiave e logica di business incapsulata:** Fornisce metodi per interrogare e manipolare i dati dei prodotti principali di PrestaShop. Utilizzato da `MspSplitEngine` per recuperare i dettagli del prodotto, le combinazioni e aggiornare gli stati dei prodotti.
-   `classes/MspCombinationSearchProvider.php`
    -   **Con quale tabella del database interagisce:** `ps_product`, `ps_product_lang`, `ps_product_attribute`, `ps_attribute`, `ps_attribute_lang`, `ps_attribute_group`, `ps_attribute_group_lang`.
    -   **Se estende ObjectModel:** No, probabilmente una classe di servizio.
    -   **Metodi pubblici chiave e logica di business incapsulata:** Fornisce funzionalità per la ricerca di prodotti e delle loro combinazioni, spesso utilizzata per la funzione di completamento automatico nel controller di amministrazione.
-   `classes/MspFinder.php`
    -   **Con quale tabella del database interagisce:** Varie tabelle PrestaShop, a seconda del contesto di ricerca.
    -   **Se estende ObjectModel:** No, probabilmente una classe di utilità/servizio.
    -   **Metodi pubblici chiave e logica di business incapsulata:** Una classe di recupero dati generica, che astrae le query di database comuni per prodotti, attributi e altre entità necessarie al modulo.
-   `classes/MspLogger.php`
    -   **Con quale tabella del database interagisce:** Probabilmente `ps_mysplitproducts_log` (tabella personalizzata).
    -   **Se estende ObjectModel:** Sì, o gestisce direttamente una tabella personalizzata.
    -   **Metodi pubblici chiave e logica di business incapsulata:** Registra tutte le operazioni di divisione e ripristino, inclusi timestamp, prodotti interessati e stato. Essenziale per la tabella della cronologia in `AdminMySplitProductsController` e per il debug.
-   `classes/MspNameBuilder.php`
    -   **Con quale tabella del database interagisce:** N/A (pura logica).
    -   **Se estende ObjectModel:** No, una classe di utilità.
    -   **Metodi pubblici chiave e logica di business incapsulata:** Implementa la logica per la generazione di nuovi nomi di prodotti e URL amichevoli basati sui modelli configurati (`MSP_NAME_BUILDER_TEMPLATE`, `MSP_URL_BUILDER_TEMPLATE`) e sui dati degli attributi.
-   `classes/MspProductCloner.php`
    -   **Con quale tabella del database interagisce:** `ps_product`, `ps_product_lang`, `ps_product_shop`, `ps_category_product`, `ps_image`, `ps_image_shop`, `ps_stock_available`, ecc.
    -   **Se estende ObjectModel:** No, una classe di servizio.
    -   **Metodi pubblici chiave e logica di business incapsulata:** La classe principale responsabile della duplicazione di un prodotto e dei suoi dati associati (immagini, stock, categorie, caratteristiche, ecc.) per creare un nuovo prodotto distinto per una combinazione specifica. Gestisce il complesso processo di copia dei dati tra più tabelle di PrestaShop.
-   `classes/MspRedirector.php`
    -   **Con quale tabella del database interagisce:** `ps_mysplitproducts_redirect` (tabella personalizzata) o `ps_url_rewrite` (PrestaShop core).
    -   **Se estende ObjectModel:** No, una classe di servizio.
    -   **Metodi pubblici chiave e logica di business incapsulata:** Gestisce la creazione e la rimozione di reindirizzamenti 301 dagli URL del prodotto/combinazione originali ai nuovi URL del prodotto diviso. Si integra con il sistema di riscrittura URL di PrestaShop o implementa la propria logica di reindirizzamento.
-   `classes/MspSplitEngine.php`
    -   **Con quale tabella del database interagisce:** Orchesta le interazioni con `MspCatalog`, `MspProductCloner`, `MspNameBuilder`, `MspRedirector`, `MspLogger`.
    -   **Se estende ObjectModel:** No, la principale classe di servizio orchestratrice.
    -   **Metodi pubblici chiave e logica di business incapsulata:** La classe centrale che coordina l'intero processo di divisione. Prende un ID prodotto, recupera le sue combinazioni, usa `MspNameBuilder` per generare nuovi dettagli, `MspProductCloner` per creare nuovi prodotti, `MspRedirector` per gli URL e `MspLogger` per registrare l'operazione. Gestisce anche la logica di rollback.

### 3.4 Risorse JavaScript (`views/js/`)

-   `lib/searchTool/views/js/autocomplete.js`
    -   **Ambito:** Back-office.
    -   **Quali listener di eventi associa:** Eventi di input sui campi di ricerca.
    -   **Quali manipolazioni DOM, popup modali, animazioni o chiamate SDK di terze parti esegue:** Fornisce una funzionalità di completamento automatico per i campi di ricerca dei prodotti nell'interfaccia di amministrazione, probabilmente utilizzando chiamate AJAX a `AdminMySplitProductsController` per recuperare i suggerimenti di prodotto.
-   `views/js/admin.js`
    -   **Ambito:** Back-office.
    -   **Quali listener di eventi associa:** Eventi di clic sui pulsanti (ad esempio, "Dividi prodotto", "Annulla"), invii di moduli.
    -   **Quali manipolazioni DOM, popup modali, animazioni o chiamate SDK di terze parti esegue:** Gestisce gli elementi interattivi del dashboard `AdminMySplitProductsController`, inclusa l'iniziazione di azioni di divisione/annullamento, l'aggiornamento della tabella della cronologia e la visualizzazione di indicatori di caricamento o messaggi di successo/errore.
-   `views/js/configure.js`
    -   **Ambito:** Back-office.
    -   **Quali listener di eventi associa:** Eventi di modifica sui campi di configurazione, invii di moduli.
    -   **Quali manipolazioni DOM, popup modali, animazioni o chiamate SDK di terze parti esegue:** Gestisce il modulo di configurazione principale del modulo. Potrebbe includere la logica per mostrare/nascondere i campi in base ad altre selezioni (ad esempio, modalità di divisione), la convalida del modulo e il salvataggio AJAX delle impostazioni di configurazione.
-   `views/js/listing.js`
    -   **Ambito:** Front-office (per la modalità di divisione virtuale).
    -   **Quali listener di eventi associa:** Potenzialmente eventi `prestashop.on` per gli aggiornamenti dell'elenco prodotti, DOM ready.
    -   **Quali manipolazioni DOM, popup modali, animazioni o chiamate SDK di terze parti esegue:** Se la modalità "divisione virtuale" è attiva, questo script modificherebbe dinamicamente gli elenchi di prodotti nelle pagine di categoria, ricerca e altre pagine per visualizzare le singole schede di combinazione. Ciò potrebbe comportare la clonazione di elementi di prodotto esistenti, l'aggiornamento del loro contenuto (nome, immagine, prezzo) e il rendering di parti della griglia dei prodotti.

### 3.5 Fogli di stile CSS (`views/css/`)

-   `lib/searchTool/views/css/autocomplete.css`
    -   **Ambito:** Styling del modulo di amministrazione del Back-office.
    -   **Principali componenti UI e contenitori che stilizza:** Stili per il menu a discesa di completamento automatico, i campi di input di ricerca e gli elenchi di suggerimenti all'interno del pannello di amministrazione.
    -   **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere nel loro tema:** `.autocomplete-suggestions`, `.autocomplete-suggestion`, `.autocomplete-selected`.
-   `views/css/admin.css`
    -   **Ambito:** Styling del modulo di amministrazione del Back-office.
    -   **Principali componenti UI e contenitori che stilizza:** Styling generale per le pagine di configurazione del modulo e il dashboard "Gestisci divisioni", inclusi tabelle, pulsanti, elementi del modulo e indicatori di stato.
    -   **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere nel loro tema:** `.mysplitproducts-config`, `.mysplitproducts-dashboard`, `.mysplitproducts-table`, `.mysplitproducts-status-success`, `.mysplitproducts-status-error`.

### 3.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**: Nessuno esplicitamente elencato, ma il modulo potrebbe utilizzare hook per la visualizzazione front-office in modalità di divisione virtuale (ad esempio, `displayProductList`, `displayProductExtraContent`) che verrebbero gestiti dal file `mysplitproducts.php` principale.
-   **Template admin (`views/templates/admin/`)**:
    -   `views/templates/admin/configure_shell.tpl`
        -   **Scopo:** Questo template funge probabilmente da wrapper principale o shell per la pagina di configurazione del modulo, incluse le impostazioni generali e possibilmente schede o sezioni per altre impostazioni. Fornisce il layout generale per `getContent()`.
    -   `views/templates/admin/dashboard.tpl`
        -   **Scopo:** Questo template renderizza il dashboard "Gestisci divisioni", inclusi l'input di ricerca prodotti, il pulsante "Dividi prodotto" e la tabella della cronologia delle operazioni di divisione. È la vista per `AdminMySplitProductsController`.
-   **Template front-office (`views/templates/front/`)**: Nessuno esplicitamente elencato. Il rendering front-office per le divisioni virtuali comporterebbe probabilmente la modifica dei template del tema esistenti tramite hook o override, o l'iniezione dinamica di contenuto tramite JavaScript (`listing.js`).

### 3.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   `ps_mysplitproducts_log`: Memorizza una cronologia di tutte le operazioni di divisione e ripristino, inclusi `id_product_original`, `id_product_split`, `action` (divisione/ripristino), `date_add`, `status`.
    -   `ps_mysplitproducts_redirect`: Memorizza le mappature di reindirizzamento 301 da vecchi URL a nuovi URL di prodotti divisi, inclusi `old_url`, `new_url`, `id_product_original`, `id_product_split`.
    -   `ps_mysplitproducts_alias`: Memorizza le mappature tra gli ID prodotto/combinazione originali e i nuovi ID prodotto divisi, cruciali per le ricerche interne e i ripristini.
    -   Record di configurazione memorizzati in `ps_configuration`:
        -   `MSP_MODE`: (int) 0 per virtuale, 1 per divisione reale.
        -   `MSP_ACTIVE_ONLY`: (bool) Dividi solo prodotti attivi.
        -   `MSP_SOURCE_ACTION`: (int) Azione per il prodotto sorgente (disabilita, mantieni attivo, elimina).
        -   `MSP_IMAGE_COPY`: (bool) Copia immagini nei nuovi prodotti.
        -   `MSP_MIN_COMBINATIONS`: (int) Combinazioni minime per la divisione.
        -   `MSP_NAME_BUILDER_TEMPLATE`: (string) Modello per i nuovi nomi dei prodotti.
        -   `MSP_URL_BUILDER_TEMPLATE`: (string) Modello per i nuovi URL dei prodotti.
        -   `MSP_SEPARATOR_MULTIPLE_ATTRIBUTES`: (string) Separatore per attributi multipli.
        -   `MSP_REDIRECT_OLD_URLS`: (bool) Abilita reindirizzamenti 301.
        -   `MSP_CLEAR_CACHE_AFTER_SPLIT`: (bool) Svuota automaticamente la cache.
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Potenzialmente inietta CSS/JS per la divisione virtuale del front-office o meta tag per la SEO. |
| `displayBackOfficeHeader` | Nella sezione `<head>` di ogni pagina del Back Office. | Inietta CSS/JS per le pagine di amministrazione del modulo (`admin.css`, `admin.js`, `autocomplete.css`, `autocomplete.js`). |
| `actionProductUpdate` | Dopo l'aggiornamento di un prodotto. | Potenzialmente attiva la rivalutazione per la divisione o gli aggiornamenti relativi ai prodotti divisi. |
| `actionProductDelete` | Dopo l'eliminazione di un prodotto. | Gestisce la pulizia dei prodotti divisi o i reindirizzamenti se il prodotto originale viene eliminato. |
| `actionProductSave` | Prima o dopo il salvataggio di un prodotto. | Intercetta i salvataggi dei prodotti per gestire i prodotti divisi o i dati correlati. |
| `actionObjectProductAddAfter` | Dopo l'aggiunta di un nuovo prodotto. | Potenzialmente attiva la divisione per i prodotti appena aggiunti se configurato. |
| `actionObjectProductUpdateAfter` | Dopo l'aggiornamento di un prodotto. | Aggiorna i prodotti divisi o i reindirizzamenti correlati. |
| `actionObjectProductDeleteAfter` | Dopo l'eliminazione di un prodotto. | Pulisce i prodotti divisi e i reindirizzamenti associati. |
| `displayProductList` | Quando viene renderizzato un elenco di prodotti (categoria, ricerca, ecc.). | **Cruciale per la modalità di divisione virtuale.** Modifica l'elenco dei prodotti per visualizzare le singole schede di combinazione. |
| `displayProductExtraContent` | Sulla pagina del prodotto, sotto il contenuto principale. | Potrebbe essere utilizzato per visualizzare collegamenti ad altre combinazioni o un messaggio sui prodotti divisi. |
| `displayAdminProductsExtra` | Sulla pagina di modifica del prodotto nel Back Office. | Aggiunge una scheda o una sezione personalizzata alla pagina di modifica del prodotto per la gestione delle divisioni relative a quel prodotto specifico. |
| `actionAdminProductsListingResultsModifier` | Modifica i risultati dell'elenco prodotti nel Back Office. | Regola l'elenco prodotti per mostrare/nascondere i prodotti originali o evidenziare i prodotti divisi. |
| `actionFrontControllerSetMedia` | Prima che un controller front-end renderizzi il suo template. | Registra JavaScript (`listing.js`) e CSS front-office per la modalità di divisione virtuale. |
| `moduleRoutes` | Durante l'inizializzazione del routing URL. | Registra percorsi personalizzati per prodotti divisi o reindirizzamenti. |

## 4. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto completo, fare riferimento al proprio account cliente su MyPresta.eu.

-   **Aggiornamenti del modulo:** Accedi al tuo account su [MyPresta.eu Order History & Downloads](https://mypresta.eu/my-account/orders/) per scaricare la versione più recente di "Dividi combinazioni in prodotti separati".
-   **Supporto tecnico:** Se riscontri problemi o hai domande non trattate in questa guida, apri un ticket di supporto tramite il tuo account cliente MyPresta.eu. Il nostro team di esperti è pronto ad assisterti.
"""
