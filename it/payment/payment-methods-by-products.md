---
title: "Metodi di pagamento per prodotto - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Metodi di pagamento per prodotto di MyPresta.eu."
sidebar:
  label: "Metodi di pagamento per prodotto - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Payment methods by products su MyPresta.eu](https://mypresta.eu/modules/payment-process/payment-methods-by-products.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/payment/payment-methods-by-products/)
>
> ---


# Metodi di pagamento per prodotto

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste da PrestaShop stesso e sono sufficienti per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

Questo modulo ha due aree di configurazione principali: la pagina di configurazione iniziale del modulo e una schermata di gestione dedicata per la creazione di associazioni prodotto-pagamento.

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Metodi di pagamento per prodotto)

Dopo aver cliccato su "Configura" dopo l'installazione, atterrerai sulla pagina di configurazione principale del modulo. Questa pagina contiene tipicamente le impostazioni generali per il modulo.

**Attualmente, non sono state rilevate impostazioni specifiche su questa pagina di configurazione principale oltre alle informazioni standard del modulo. La funzionalità principale è gestita tramite la schermata dedicata "Associazioni Pagamento - Prodotto".**

Se le versioni future introducessero impostazioni qui, apparirebbero come interruttori, campi di input o menu a discesa. Per ora, puoi procedere direttamente alla schermata di gestione dedicata.

### 2.2 Schermata di amministrazione dedicata: Associazioni Pagamento - Prodotto (Back Office > Moduli > Metodi di pagamento per prodotto > Associazioni Pagamento - Prodotto)

Questo è il centro nevralgico per la gestione delle restrizioni prodotto-pagamento. Troverai questa schermata navigando su **Moduli > Gestione moduli**, trovando "Metodi di pagamento per prodotto", cliccando su "Configura", e quindi cercando una scheda o un link etichettato "Associazioni Pagamento - Prodotto" (o simile, a seconda della navigazione del modulo).

**Nome schermata e posizione nel menu:**

- **Percorso menu:** Back Office > Moduli > Gestione moduli > Metodi di pagamento per prodotto > Configura > **Associazioni Pagamento - Prodotto** (o una scheda/link simile nella pagina di configurazione).
- Questa schermata ti consente di visualizzare, aggiungere, modificare ed eliminare associazioni tra prodotti e metodi di pagamento.

**Azioni e impostazioni disponibili:**

#### 2.2.1 La vista elenco "Associazioni Pagamento - Prodotto"

Questa vista presenta una tabella di tutte le restrizioni prodotto-pagamento esistenti che hai impostato.

| Nome colonna | Scopo e impatto |
| --- | --- |
| **ID** | Un identificatore univoco per ogni associazione. |
| **Prodotto** | Il nome del prodotto coinvolto nella restrizione. |
| **Pagamento** | Il nome del metodo di pagamento che è limitato o consentito per questo prodotto. |
| **Paese** | (Se applicabile) Il paese per il quale si applica questa restrizione. Se lasciato vuoto, si applica a livello globale. |
| **Azioni** | Icone per **Modificare** (icona a matita) o **Eliminare** (icona cestino) un'associazione esistente. |

**Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

- **Rivedi le regole esistenti:** Controlla regolarmente questo elenco per assicurarti che le tue restrizioni siano aggiornate con il tuo catalogo prodotti e le esigenze aziendali.
- **Identifica i conflitti:** Cerca eventuali regole sovrapposte o in conflitto, specialmente se hai molti prodotti e metodi di pagamento.
- **Usa ricerca/filtro:** Se l'elenco diventa lungo, usa le opzioni di ricerca o filtro disponibili per trovare rapidamente restrizioni specifiche di prodotto o pagamento.

#### 2.2.2 Aggiunta o modifica di un'associazione "Pagamento - Prodotto"

Per aggiungere una nuova restrizione, troverai tipicamente un pulsante "Aggiungi nuovo" nella vista elenco. Per la modifica, clicca sull'icona a matita accanto a una voce esistente. Questo aprirà un modulo con i seguenti campi:

| Campo modulo | Cosa fa questa impostazione | Effetto della modifica di questa impostazione | Valore consigliato | Scenario/esempio commerciante |
| --- | --- | --- | --- | --- |
| **ID Prodotto** | Questo campo ti consente di selezionare il prodotto specifico che desideri associare a restrizioni di pagamento. | Quando selezioni un prodotto, il modulo applicherà le restrizioni di pagamento scelte ogni volta che questo prodotto si trova nel carrello di un cliente. | Seleziona il prodotto esatto dal tuo catalogo. Usa la funzionalità di ricerca se hai molti prodotti. | Vendi "Ebook Digitale: Guida al Marketing". Vuoi assicurarti che sia pagato solo tramite PayPal o Carta di Credito, non Contrassegno. Selezioni questo prodotto qui. |
| **Metodi di pagamento** | Questo è un elenco di tutti i metodi di pagamento attivi nel tuo negozio PrestaShop. Selezioni quali metodi di pagamento sono **consentiti** per il prodotto scelto. | - *Quando selezioni uno o più metodi di pagamento:* Solo questi metodi selezionati saranno disponibili al checkout se il prodotto associato è nel carrello. Tutti gli altri metodi di pagamento saranno nascosti.   - *Quando non selezioni NESSUN metodo di pagamento:* Questo significa effettivamente che il prodotto non può essere acquistato, oppure erediterà le regole da altri prodotti nel carrello. Generalmente non è consigliabile lasciare questo campo vuoto a meno che tu non abbia un caso d'uso molto specifico. | Seleziona tutti i metodi di pagamento accettabili per il prodotto scelto. | Per "Ebook Digitale: Guida al Marketing", selezioni "PayPal" e "Carta di Credito". Se un cliente acquista questo ebook, solo queste due opzioni appariranno al checkout. |
| **Paese** | (Opzionale) Questo campo ti consente di specificare un paese per il quale si applica questa particolare restrizione prodotto-pagamento. | - *Quando viene selezionato un paese:* La restrizione (prodotto + pagamenti consentiti) si applicherà solo se l'indirizzo di spedizione del cliente si trova nel paese selezionato.   - *Quando lasciato vuoto:* La restrizione si applica a livello globale, indipendentemente dal paese del cliente. | Lascia vuoto per l'applicazione globale, o seleziona un paese specifico se la restrizione è geograficamente limitata. | Vendi "Scultura in Vetro Fragile" che può essere pagata solo tramite "Bonifico Bancario" in Italia a causa dei requisiti di assicurazione sulla spedizione. Selezioni la scultura, "Bonifico Bancario" e "Italia". Per i clienti al di fuori dell'Italia, altri metodi di pagamento potrebbero essere ancora disponibili per questo prodotto (se non si applicano altre regole globali). |
| **Salva** | Questo pulsante salva la tua associazione prodotto-pagamento nuova o aggiornata. | Le modifiche vengono immediatamente applicate al processo di checkout del tuo negozio. | Clicca sempre su "Salva" dopo aver apportato qualsiasi modifica. | Dopo aver impostato le regole per il tuo "Ebook Digitale", clicchi su "Salva" per attivarle. |

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | (Nessuna impostazione specifica rilevata) | N/A | Informazioni generali sul modulo. |
| Associazioni Pagamento - Prodotto (Elenco) | ID | N/A | Identificatore univoco per l'associazione. |
| Associazioni Pagamento - Prodotto (Elenco) | Prodotto | N/A | Nome del prodotto nell'associazione. |
| Associazioni Pagamento - Prodotto (Elenco) | Pagamento | N/A | Nome del metodo di pagamento nell'associazione. |
| Associazioni Pagamento - Prodotto (Elenco) | Paese | N/A | Paese per il quale si applica la restrizione (se presente). |
| Associazioni Pagamento - Prodotto (Modulo Aggiungi/Modifica) | ID Prodotto | Seleziona un prodotto | Specifica il prodotto per il quale i metodi di pagamento saranno limitati. |
| Associazioni Pagamento - Prodotto (Modulo Aggiungi/Modifica) | Metodi di pagamento | Seleziona tutti i metodi accettabili | Definisce quali metodi di pagamento sono **consentiti** per il prodotto selezionato. |
| Associazioni Pagamento - Prodotto (Modulo Aggiungi/Modifica) | Paese | Lascia vuoto per globale, o seleziona specifico | Limita la restrizione a un paese specifico. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho impostato una restrizione, ma tutti i metodi di pagamento sono ancora visibili al checkout. Cosa c'è che non va?**
R:

1.  **Cache:** Cancella sempre la cache di PrestaShop dopo aver apportato modifiche. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti).
2.  **Prodotto nel carrello:** Assicurati che il prodotto specifico che hai limitato sia effettivamente nel carrello del cliente durante il test. Il modulo applica le regole solo se il prodotto è presente.
3.  **Metodo di pagamento abilitato:** Ricontrolla che i metodi di pagamento che ti *aspetti* di vedere siano effettivamente abilitati in **Moduli > Pagamento > Metodi di pagamento**. Questo modulo filtra i metodi *abilitati*, non li abilita da solo.
4.  **Regole in conflitto:** Se hai più prodotti nel carrello, e ognuno ha restrizioni, il modulo mostrerà solo i metodi di pagamento consentiti da *tutti* i prodotti con restrizioni. Se non c'è un metodo consentito comune, potrebbe sembrare che non vengano mostrati metodi. Rivedi attentamente le tue associazioni.

**D: Ho impostato una restrizione, e ora NESSUN metodo di pagamento è visibile al checkout!**
R: Questo di solito accade se:

1.  **Nessun metodo comune:** Hai più prodotti con restrizioni nel carrello e non ci sono metodi di pagamento consentiti da *tutti* loro. Ad esempio, il Prodotto A consente PayPal, il Prodotto B consente la Carta di Credito. Se entrambi sono nel carrello, nessuno dei due verrà mostrato. Devi assicurarti che ci sia almeno un metodo consentito comune.
2.  **Elenco consentito vuoto:** Hai creato un'associazione per un prodotto ma non hai selezionato *alcun* metodo di pagamento come consentito. Il modulo nasconderà quindi tutti i metodi per quel prodotto. Modifica l'associazione e seleziona i metodi di pagamento appropriati.

**D: Questo modulo influisce sui metodi di pagamento per i prodotti che NON sono in alcuna associazione?**
R: No. Se un prodotto non fa parte di alcuna "Associazione Pagamento - Prodotto", non impone alcuna restrizione. Il modulo agisce solo sui prodotti per i quali hai esplicitamente definito delle regole. Se un carrello contiene solo prodotti senza restrizioni, verranno visualizzati tutti i metodi di pagamento standard abilitati del tuo negozio.

**D: Come interagisce questo modulo con altri moduli di restrizione del pagamento (ad esempio, per gruppo di clienti, per importo totale)?**
R: Questo modulo funziona tipicamente sovrascrivendo la classe core `PaymentOptionsFinder` di PrestaShop (come si vede nella cartella `override/`). Ciò significa che ha la precedenza o si integra a un livello fondamentale. Generalmente, si applicherà la regola più restrittiva. Se un altro modulo limita un metodo di pagamento, e questo modulo lo consente per un prodotto, il metodo di pagamento sarà probabilmente ancora limitato dall'altro modulo. È fondamentale testare accuratamente se si utilizzano più moduli di restrizione.

**D: Posso limitare i metodi di pagamento in base al paese senza limitare per prodotto?**
R: La funzione principale di questo modulo è la restrizione basata sul prodotto. Sebbene abbia un campo "Paese", si applica *all'associazione prodotto-pagamento*. Se hai bisogno di restrizioni di pagamento puramente basate sul paese (indipendentemente dal prodotto), potresti aver bisogno di un modulo separato progettato per questo, o verificare se i tuoi gateway di pagamento offrono restrizioni per paese direttamente.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce un'analisi tecnica approfondita del modulo "Metodi di pagamento per prodotto" per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo estende principalmente il meccanismo di scoperta delle opzioni di pagamento core di PrestaShop. Sfrutta un `override` per modificare la classe `PaymentOptionsFinder`, che è responsabile della determinazione dei metodi di pagamento disponibili durante il checkout. Ciò consente al modulo di iniettare la sua logica di filtraggio basata sul prodotto direttamente nel processo di recupero delle opzioni di pagamento, garantendo un'integrazione perfetta con il flusso di checkout di PrestaShop.
Il modulo segue un pattern MVC standard di PrestaShop per la sua gestione Back Office, utilizzando un AdminController per gestire l'entità `pobp` (Associazione Prodotto-Pagamento).

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**: Nessuno. La funzionalità front-office del modulo è gestita tramite un override di una classe core, non un controller frontale dedicato.
- **Controller Admin Back-Office**:

  - `pobp/controllers/admin/AdminPobpController.php`
    - **Nome classe e classe genitore**: `AdminPobpController` estende `ModuleAdminController`.
    - **Nome tab**: Questo controller gestisce l'entità "Associazioni Pagamento - Prodotto". È probabile che sia registrato come sotto-tab sotto la configurazione principale del modulo.
    - **Responsabilità**: Questo è il controller CRUD (Create, Read, Update, Delete) principale per le associazioni prodotto-pagamento. Gestisce:
      - La visualizzazione dell'elenco delle associazioni esistenti (ID, Prodotto, Pagamento, Paese).
      - La fornitura del modulo per l'aggiunta di nuove associazioni o la modifica di quelle esistenti.
      - L'elaborazione delle sottomissioni del modulo per salvare associazioni nuove o aggiornate nel database.
      - La gestione dell'eliminazione delle associazioni.
      - I campi del modulo "ID Prodotto", "Metodi di pagamento" e "Paese" sono gestiti qui.
  - `pobp/controllers/admin/index.php`
    - Questo file è tipicamente un segnaposto vuoto o contiene misure di sicurezza di base (ad esempio, `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../"); exit;`). Non rappresenta una vista controller funzionale in sé, ma garantisce che l'accesso diretto alla directory `controllers/admin` sia reindirizzato.

### 4.3 Classi e modelli core (`classes/`)

- `pobp/override/classes/checkout/PaymentOptionsFinder.php`
  - **Scopo**: Questo è un file di override critico. Modifica la classe core di PrestaShop responsabile della ricerca e della restituzione delle opzioni di pagamento disponibili durante il checkout.
  - **Nome classe e classe genitore**: `PaymentOptionsFinder` (sovrascrive la classe `PaymentOptionsFinder` originale).
  - **Logica chiave**: Il metodo `getPaymentOptions()` sovrascritto (o un metodo simile) conterrà la logica core del modulo.
    - Recupera i prodotti attualmente nel carrello del cliente.
    - Per ogni prodotto, verifica se ci sono "Associazioni Pagamento - Prodotto" definite nel database del modulo.
    - Filtra quindi le opzioni di pagamento inizialmente disponibili (restituite dal metodo `getPaymentOptions()` genitore) in base a queste associazioni.
    - La logica di filtraggio garantisce che vengano restituiti solo i metodi di pagamento esplicitamente consentiti per *tutti* i prodotti con restrizioni nel carrello. Se un prodotto non ha associazioni, non limita nulla. Se più prodotti hanno associazioni, viene utilizzata l'intersezione dei metodi di pagamento consentiti.
  - **Interazione con il database**: Questa classe interrogherà la tabella del database personalizzata del modulo (probabilmente `ps_pobp` o simile) per recuperare le associazioni prodotto-pagamento.

### 4.4 Risorse JavaScript (`views/js/`)

Nessun file JavaScript specifico è stato rilevato nell'inventario fornito. Qualsiasi comportamento dinamico nel Back Office (come la ricerca di prodotti nel modulo di associazione) è probabilmente gestito dal JS core di PrestaShop o da uno script inline minimo.

### 4.5 Fogli di stile CSS (`views/css/`)

Nessun file CSS specifico è stato rilevato nell'inventario fornito. Lo stile per i moduli e gli elenchi del Back Office è probabilmente ereditato dal tema admin predefinito di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template hook (`views/templates/hook/`)**: Nessuno esplicitamente elencato, poiché il modulo opera tramite un override piuttosto che tramite il rendering diretto di hook nel front office.
- **Template admin (`views/templates/admin/`)**:
  - `pobp/lib/searchTool/views/scripts.tpl`
    - **Scopo**: Questo template contiene probabilmente logica JavaScript o Smarty relativa a uno strumento di ricerca utilizzato all'interno del Back Office, possibilmente per la ricerca di prodotti durante la creazione o la modifica di un'associazione. Potrebbe includere chiamate AJAX o filtraggio dinamico per la selezione del prodotto.
- **Template front-office (`views/templates/front/`)**: Nessuno.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Il modulo creerà almeno una tabella personalizzata durante il suo metodo `install()` (definito in `pobp/index.php`).
  - **`ps_pobp` (o nome simile, ad esempio, `ps_payment_by_product_association`)**:
    - Questa tabella memorizza le associazioni prodotto-pagamento effettive.
    - Colonne previste:
      - `id_pobp` (Chiave primaria, INT)
      - `id_product` (INT, chiave esterna a `ps_product`)
      - `id_payment_module` (INT, chiave esterna a `ps_module` o `ps_payment_module` se tale tabella esiste, o semplicemente memorizza il nome/ID del modulo)
      - `id_country` (INT, chiave esterna a `ps_country`, nullable per regole globali)
      - Altre colonne potenziali per impostazioni o timestamp.
  - I valori di configurazione (se presenti in `getContent()`) verrebbero memorizzati in `ps_configuration`.
- **Tabella degli hook registrati**:
  La funzionalità core del modulo si basa sul meccanismo di `override` piuttosto che sull'esecuzione diretta di hook per il suo filtraggio primario. Tuttavia, per la sua integrazione nel Back Office e potenzialmente per funzionalità future, potrebbe registrare hook standard.

  | Nome hook | Tempo di esecuzione | Scopo tecnico |
  | --- | --- | --- |
  | `displayAdminProductsExtra` | Nella pagina di modifica del prodotto nel Back Office. | Potrebbe essere utilizzato per visualizzare un link rapido o un riepilogo delle restrizioni di pagamento per il prodotto corrente. (Non esplicitamente rilevato ma un punto di integrazione comune). |
  | `actionPaymentOptionsModifier` | Durante il processo di recupero delle opzioni di pagamento. | Questo hook è specificamente progettato per i moduli per modificare l'elenco delle opzioni di pagamento. L'override di `PaymentOptionsFinder` raggiunge efficacemente un risultato simile a un livello inferiore. |
  | `actionModuleInstall` | Quando il modulo è installato. | Per creare tabelle del database e registrare gli hook necessari. |
  | `actionModuleUninstall` | Quando il modulo è disinstallato. | Per pulire le tabelle del database e annullare la registrazione degli hook. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e per assicurarti di avere l'ultima versione compatibile del modulo "Metodi di pagamento per prodotto", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda riguardante la funzionalità e l'integrazione del modulo.
