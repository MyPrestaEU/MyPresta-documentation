---
title: "Produttore (brand) nell'elenco prodotti nel back office - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Produttore (brand) nell'elenco prodotti nel back office' di MyPresta.eu."
sidebar:
  label: "Produttore (brand) nell'elenco prodotti nel back office - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Manufacturer (brand) on products list in back office su MyPresta.eu](https://mypresta.eu/modules/administration-tools/manufacturer-brand-on-products-list-in-back-office.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/manufacturer-brand-on-products-list-in-back-office/)
>
> ---


# Produttore (brand) nell'elenco prodotti nel back office

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.0.0 - 1.7.7.x, 1.7.8.x, 8.x (elenco standard), 8.x (elenco prodotti sperimentale), 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" verrai indirizzato alla pagina delle impostazioni principali del modulo. Questa pagina gestisce principalmente le notifiche di aggiornamento e la manutenzione generale del modulo.

-   **Cosa fa questa impostazione:** Questa sezione gestisce tipicamente come il modulo controlla gli aggiornamenti e visualizza le notifiche.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* Il modulo controllerà periodicamente MyPresta.eu per nuove versioni e ti informerà se è disponibile un aggiornamento. Questo ti aiuta a mantenere il modulo aggiornato con le ultime funzionalità e correzioni di bug.
    -   *Quando disabilitato:* Il modulo non controllerà automaticamente gli aggiornamenti e non riceverai notifiche sulle nuove versioni. Dovresti controllare manualmente il tuo account MyPresta.eu per gli aggiornamenti.
-   **Valore consigliato:** **Abilitato (Sì)**. Mantenere questa opzione abilitata ti assicura di essere sempre a conoscenza degli aggiornamenti disponibili, il che è cruciale per la sicurezza e la compatibilità con le future versioni di PrestaShop.
-   **Scenario / esempio per il commerciante:** Vuoi essere avvisato quando viene rilasciata una nuova versione del modulo che supporta le ultime funzionalità di PrestaShop 8.x. Abilitando questa impostazione riceverai tale notifica direttamente nel tuo back office.

### 2.2 Schermate di amministrazione dedicate e viste del controller

Questo modulo non introduce nuove voci di menu separate o schermate di amministrazione dedicate per la gestione della sua funzionalità principale. Invece, le sue modifiche sono integrate direttamente nella pagina esistente **Catalogo > Prodotti**.

**Nome schermata e posizione nel menu:**

-   **Catalogo > Prodotti** (La pagina standard di elenco prodotti di PrestaShop)

**Azioni e impostazioni disponibili:**
Navigando su **Catalogo > Prodotti**, noterai immediatamente le modifiche introdotte dal modulo:

-   **Nuova colonna: Produttore/Brand:** Una nuova colonna apparirà nel tuo elenco prodotti, mostrando il nome del produttore associato a ciascun prodotto.
-   **Logo del produttore (Opzionale):** A seconda della logica interna del modulo, potrebbe anche visualizzare il logo del produttore accanto al nome, se disponibile e configurato.
-   **Filtra per produttore:** Sopra l'elenco prodotti, troverai una nuova opzione di filtro, tipicamente un menu a discesa, che ti consente di selezionare un produttore specifico. Una volta selezionato, l'elenco prodotti si aggiornerà istantaneamente per mostrare solo i prodotti di quel brand.

**Effetto delle modifiche:**

-   **Aggiunta della colonna Produttore:** Fornisce un'indicazione visiva immediata del brand di ogni prodotto, eliminando la necessità di aprire le pagine dei prodotti individualmente per controllare questa informazione.
-   **Filtro per Produttore:** Velocizza drasticamente le attività in cui è necessario lavorare con prodotti di un brand specifico. Ad esempio, se un produttore annuncia un aumento di prezzo, puoi filtrare rapidamente tutti i suoi prodotti e aggiornare i prezzi. Oppure se devi controllare i livelli di stock per gli articoli di un particolare brand.

**Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

1.  **Identificazione rapida del brand:** Quando navighi nell'elenco dei tuoi prodotti, usa la nuova colonna "Produttore" per identificare rapidamente i brand.
2.  **Gestione mirata:** Se devi eseguire un'azione su tutti i prodotti di un brand specifico (es. aggiornare descrizioni, aggiustare prezzi, controllare l'inventario), usa il nuovo menu a discesa "Filtra per Produttore" nella parte superiore dell'elenco prodotti. Seleziona il brand desiderato e il tuo elenco verrà istantaneamente raffinato.
3.  **Azioni di massa:** Combina il filtro per produttore con le azioni di massa standard di PrestaShop (es. selezionare più prodotti e applicare una modifica) per una gestione altamente efficiente e specifica per brand.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | Notifiche di aggiornamento | Abilitato | Ti avvisa delle nuove versioni del modulo per sicurezza e funzionalità. |
| Catalogo > Elenco prodotti | Colonna Produttore | N/A (Sempre Attiva) | Visualizza il brand del prodotto direttamente nell'elenco prodotti per una rapida identificazione. |
| Catalogo > Elenco prodotti | Filtra per Produttore | N/A (Sempre Attiva) | Consente di filtrare l'elenco prodotti per un brand specifico, semplificando le attività di gestione specifiche per brand. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D: Ho installato il modulo, ma non vedo la colonna o il filtro del produttore nel mio elenco prodotti.**
R:

1.  **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). A volte PrestaShop ha bisogno di un aggiornamento della cache per visualizzare nuovi elementi.
2.  **Modulo abilitato:** Ricontrolla che il modulo sia effettivamente abilitato in **Moduli > Gestione moduli**.
3.  **Compatibilità della versione di PrestaShop:** Assicurati di aver scaricato la versione corretta del modulo per la tua specifica installazione di PrestaShop. Se sei su PrestaShop 8.x, assicurati di non aver installato accidentalmente una versione 1.7.x, ad esempio.
4.  **Sovrascritture del tema:** Sebbene il modulo sia progettato senza sovrascritture, un tema pesantemente personalizzato o un altro modulo potrebbero entrare in conflitto. Se il problema persiste, prova a disabilitare altri moduli uno per uno per identificare un conflitto.

**D: Il nome del produttore appare, ma il logo no.**
R: Il modulo si concentra principalmente sulla visualizzazione del nome del produttore. Se supporta i loghi, assicurati che:

1.  **Logo del produttore caricato:** Hai effettivamente caricato un logo per quel produttore in **Catalogo > Produttori** nel tuo back office PrestaShop.
2.  **Impostazione del modulo:** Potrebbe esserci un'impostazione interna (anche se non esposta nella configurazione di base per questo modulo) che controlla la visualizzazione del logo. In caso contrario, significa che il modulo è progettato per mostrare solo il nome.

**D: Posso cambiare la posizione della colonna del produttore nell'elenco prodotti?**
R: Questo modulo si integra direttamente nel sistema di griglia dei prodotti di PrestaShop. La posizione esatta della colonna è determinata dalla configurazione principale dell'elenco prodotti di PrestaShop. Sebbene questo modulo aggiunga la colonna, tipicamente non offre opzioni per trascinare e rilasciare le posizioni delle colonne. Potrebbe essere necessario un modulo di personalizzazione della griglia più avanzato o uno sviluppo personalizzato per riordinare le colonne.

**D: Questo modulo rallenta il mio back office?**
R: No, il modulo è progettato per essere leggero ed efficiente. Sfrutta il sistema di hook nativo di PrestaShop per aggiungere i dati del produttore senza elaborazioni pesanti. Non dovresti riscontrare rallentamenti evidenti.

**D: Questo modulo funzionerà con la nuova pagina prodotto sperimentale in PrestaShop 8.x?**
R: Sì, la descrizione del modulo dichiara esplicitamente la compatibilità con "8.x-experimental product list", il che significa che è progettato per funzionare sia con l'interfaccia di elenco prodotti standard che con quella più recente e sperimentale in PrestaShop 8.x.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo `Produttore (brand) nell'elenco prodotti nel back office` (nome interno `dpmypresta`) è progettato per migliorare la pagina di elenco prodotti del Back Office di PrestaShop aggiungendo le informazioni del produttore. Aderisce a un approccio senza sovrascritture, basandosi pesantemente sul sistema di hook di PrestaShop, in particolare sugli hook `actionProductGrid*` introdotti in PrestaShop 1.7.x per modificare la griglia del catalogo prodotti. Questo lo rende robusto contro gli aggiornamenti del core di PrestaShop. Il modulo inietta principalmente nuove colonne e capacità di filtraggio nei dati esistenti della griglia prodotti e nel processo di rendering.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller front-office. Include due file controller admin, ma `AdminDpMyPrestaController.php` sembra essere un segnaposto o un residuo, e `index.php` è un file vuoto standard per prevenire l'elenco delle directory. La logica principale del modulo per la configurazione è gestita all'interno del metodo `getContent()` di `dpmypresta.php`, e le modifiche alla griglia dei prodotti sono gestite tramite hook.

-   **Controller Front-Office**: Nessuno. Tutte le funzionalità sono specifiche del back-office.
-   **Controller Admin Back-Office**:
    -   `controllers/admin/AdminDpMyPrestaController.php`
        -   Nome classe: `AdminDpMyPrestaController` (estende `ModuleAdminController`)
        -   Responsabilità: Questo controller è presente ma sembra essere un segnaposto. Il suo metodo `__construct` imposta il contesto base del modulo. Non definisce azioni specifiche né renderizza viste uniche oltre a quelle che potrebbero essere ereditate da `ModuleAdminController`. Non è direttamente collegato alla funzionalità principale di aggiunta dei dati del produttore all'elenco prodotti, che è basata su hook.
    -   `controllers/admin/index.php`
        -   File `index.php` vuoto standard per sicurezza per prevenire l'elenco delle directory.

### 4.3 Classi e Modelli Core (`classes/`)

Il modulo non definisce classi personalizzate o `ObjectModel` nella directory `classes/`. Le sue operazioni sono direttamente integrate nelle strutture dati e nei meccanismi di griglia esistenti di PrestaShop tramite hook.

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo non include alcun file JavaScript personalizzato. Tutte le interazioni e la logica di visualizzazione per la colonna e il filtro del produttore sono gestite dai componenti nativi della griglia di PrestaShop e dalla logica PHP del modulo.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo non include alcun file CSS personalizzato. Lo stile per la colonna e il filtro del produttore aggiunti è ereditato dal tema del back office di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo sfrutta il nuovo sistema di templating Twig utilizzato in PrestaShop 1.7+ per le griglie del back-office.

-   **Template Admin (`views/templates/admin/`)**:
    -   `views/PrestaShop/Admin/Product/CatalogPage/Lists/list.html.twig`
        -   Questo template Twig probabilmente estende o modifica il template principale dell'elenco prodotti di PrestaShop. È responsabile del rendering della pagina complessiva del catalogo prodotti, inclusa la griglia. Il modulo inietta la colonna e il filtro del produttore in questa struttura.
    -   `views/PrestaShop/Admin/Product/CatalogPage/Lists/products_table.html.twig`
        -   Questo template Twig renderizza specificamente la tabella dei prodotti all'interno della pagina del catalogo. Il modulo modifica questo template per aggiungere i dati del produttore a ogni riga del prodotto.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**: Il modulo non crea tabelle di database personalizzate. Si basa sulle tabelle esistenti di PrestaShop, principalmente `ps_product`, `ps_manufacturer` e `ps_configuration` per le sue impostazioni.

    -   I valori di configurazione (`mypresta_updates`, `update_`, `updatev_`) sono memorizzati nella tabella `ps_configuration`.
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `actionProductGridDataModifier` | Dopo che i dati del prodotto sono stati recuperati per la griglia. | Modifica l'array di dati grezzi per ogni prodotto, iniettando ID e nome del produttore. |
| `actionAdminProductsListingFieldsModifier` | Prima che i campi della griglia prodotti siano definiti. | Aggiunge la definizione della colonna 'Produttore' alla griglia prodotti. |
| `actionProductGridDefinitionModifier` | Modifica la definizione della griglia prodotti stessa. | Potenzialmente aggiunge il filtro del produttore alla collezione di filtri della griglia. |
| `actionAdminProductsListingResultsModifier` | Dopo che i risultati dell'elenco prodotti sono stati preparati. | Modifica ulteriormente i risultati, assicurando che i dati del produttore siano correttamente formattati per la visualizzazione. |
| `actionProductGridQueryBuilderModifier` | Modifica il Doctrine Query Builder per la griglia prodotti. | Unisce la tabella `ps_manufacturer` alla query del prodotto e aggiunge condizioni per il filtraggio per produttore. |
| `displayBackOfficeHeader` | Renderizza il contenuto nella sezione `<head>` del Back Office. | Utilizzato per caricare risorse specifiche del modulo (anche se nessuna è presente in questo modulo) o per i controlli di aggiornamento. |
| `displayAdminProductsExtra` | Renderizza contenuto extra nella pagina del prodotto (non direttamente utilizzato per la modifica dell'elenco). | Non direttamente correlato alla funzionalità principale di questo modulo, ma un hook comune per le estensioni della pagina del prodotto admin. |

## 5. Supporto Ufficiale e Aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e ulteriore assistenza con il modulo "Produttore (brand) nell'elenco prodotti nel back office", visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è pronto ad aiutarti con qualsiasi domanda o problema tu possa incontrare.
"""
