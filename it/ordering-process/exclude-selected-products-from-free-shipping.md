---
title: "Escludi prodotti selezionati dalla spedizione gratuita - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Escludi prodotti selezionati dalla spedizione gratuita' di MyPresta.eu."
sidebar:
  label: "Escludi prodotti selezionati dalla spedizione gratuita - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Exclude selected products from free shipping su MyPresta.eu](https://mypresta.eu/modules/ordering-process/exclude-selected-products-from-free-shipping.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/exclude-selected-products-from-free-shipping/)
>
> ---


# Escludi prodotti selezionati dalla spedizione gratuita

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata principale dove definirai le regole fondamentali per escludere i prodotti dalla spedizione gratuita.

#### 2.1.1 Impostazioni Generali

- **Rimuovi codice voucher con spedizione gratuita**

  - **Cosa fa questa impostazione:** Questa opzione determina se un voucher di spedizione gratuita (una `CartRule` che concede la spedizione gratuita) debba essere rimosso o invalidato dal carrello del cliente se è presente un prodotto escluso.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (SÌ):* Se un cliente applica un voucher di spedizione gratuita e poi aggiunge un prodotto che hai contrassegnato per l'esclusione, il modulo tenterà di rimuovere quel voucher dal suo carrello. Questo assicura che, anche con un voucher, la spedizione gratuita non venga concessa per gli articoli esclusi.
    - *Quando disabilitato (NO):* I voucher di spedizione gratuita rimarranno attivi anche se un prodotto escluso è nel carrello. Ciò significa che un cliente potrebbe comunque ottenere la spedizione gratuita tramite un voucher, ignorando l'esclusione basata sul prodotto del modulo.
  - **Valore consigliato:** **SÌ**. Questo fornisce il controllo più coerente sui costi di spedizione, impedendo la spedizione gratuita anche quando viene utilizzato un voucher.
  - **Scenario / esempio del commerciante:** Vendi articoli di arredamento di grandi dimensioni che comportano sempre un costo di spedizione. Offri anche un voucher "SPEDIZIONELIBERA" per ordini superiori a 100 €. Se un cliente aggiunge un divano (un prodotto escluso) e utilizza il voucher "SPEDIZIONELIBERA", abilitando questa impostazione il voucher verrà rimosso, assicurando che paghi la spedizione del divano.
- **Escludi prodotti esauriti**

  - **Cosa fa questa impostazione:** Questa opzione ti consente di escludere automaticamente i prodotti attualmente esauriti dalla qualificazione per la spedizione gratuita.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (SÌ):* Se un prodotto è esaurito e nel carrello del cliente, e lo hai anche contrassegnato per l'esclusione, il modulo applicherà le sue regole. Questo è generalmente meno rilevante poiché i prodotti esauriti spesso non possono comunque essere ordinati, ma garantisce coerenza.
    - *Quando disabilitato (NO):* Il modulo non considererà lo stato delle scorte quando applica le sue regole di esclusione.
  - **Valore consigliato:** **NO**. Questa impostazione è spesso ridondante poiché i prodotti esauriti di solito non possono essere aggiunti al carrello o ordinati. Tienila disabilitata a meno che tu non abbia un motivo specifico per usarla (ad esempio, consentire ordini in arretrato dove la spedizione gratuita dovrebbe comunque essere bloccata).
  - **Scenario / esempio del commerciante:** Consenti ordini in arretrato per alcuni articoli. Se un articolo è in arretrato (esaurito) ed è anche un articolo grande e pesante che non spedisci mai gratuitamente, abilitando questa impostazione si assicura che, anche in arretrato, contribuisca a disabilitare la spedizione gratuita.

#### 2.1.2 Regole di esclusione della spedizione gratuita

- **Disabilita spedizione gratuita per prodotti selezionati**

  - **Cosa fa questa impostazione:** Questa è la funzionalità principale. Ti consente di specificare singoli prodotti che, quando nel carrello, disabiliteranno la spedizione gratuita.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (SÌ):* Il modulo cercherà i prodotti specifici che hai aggiunto all'elenco di esclusione. Se uno di questi prodotti è nel carrello del cliente, la spedizione gratuita verrà disabilitata.
    - *Quando disabilitato (NO):* Nessun singolo prodotto disabiliterà la spedizione gratuita, indipendentemente da ciò che è nell'elenco di esclusione.
  - **Valore consigliato:** **SÌ**. Abilita questa opzione per utilizzare la funzionalità principale del modulo.
  - **Scenario / esempio del commerciante:** Vendi gioielli raffinati (piccoli, leggeri, di solito spedizione gratuita) e anche grandi vetrine (pesanti, costose da spedire). Abiliteresti questa opzione e aggiungeresti le vetrine all'elenco di esclusione.
- **Disabilita spedizione gratuita per categorie selezionate**

  - **Cosa fa questa impostazione:** Simile ai prodotti, questa opzione ti consente di selezionare intere categorie di prodotti. Se *qualsiasi* prodotto di una categoria selezionata è nel carrello del cliente, la spedizione gratuita verrà disabilitata.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (SÌ):* Il modulo controllerà se un prodotto nel carrello appartiene a una delle categorie che hai selezionato per l'esclusione. In tal caso, la spedizione gratuita è disabilitata.
    - *Quando disabilitato (NO):* Nessuna categoria disabiliterà la spedizione gratuita.
  - **Valore consigliato:** **SÌ** se hai interi gruppi di prodotti che non dovrebbero mai qualificarsi per la spedizione gratuita.
  - **Scenario / esempio del commerciante:** Vendi sia libri che grandi stampe d'arte. Tutte le stampe d'arte richiedono imballaggi e spedizioni speciali. Abiliteresti questa opzione e selezioneresti la categoria "Stampe d'arte". Qualsiasi stampa d'arte nel carrello disabiliterà la spedizione gratuita.

#### 2.1.3 Interfaccia di selezione prodotti e categorie

Sotto queste impostazioni, troverai due sezioni:

- **Prodotti da escludere dalla spedizione gratuita:** Una barra di ricerca e un elenco di prodotti attualmente esclusi.
  - **Come usare:** Inizia a digitare il nome di un prodotto nella barra di ricerca. Mentre digiti, apparirà un elenco di prodotti corrispondenti. Clicca su un prodotto per aggiungerlo all'elenco di esclusione. Per rimuovere un prodotto, clicca sulla "X" accanto al suo nome nell'elenco.
- **Categorie da escludere dalla spedizione gratuita:** Una vista ad albero delle categorie del tuo negozio con caselle di controllo.
  - **Come usare:** Seleziona la casella accanto a qualsiasi categoria che desideri escludere. Tutti i prodotti all'interno di quella categoria (e delle sue sottocategorie, a seconda del comportamento delle categorie della tua versione di PrestaShop) disabiliteranno la spedizione gratuita se presenti nel carrello.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione principale del modulo | Rimuovi codice voucher con spedizione gratuita | SÌ | Assicura che i voucher di spedizione gratuita vengano rimossi se i prodotti esclusi sono nel carrello. |
| Configurazione principale del modulo | Escludi prodotti esauriti | NO | Generalmente non necessario, poiché gli articoli esauriti spesso non possono essere ordinati. |
| Configurazione principale del modulo | Disabilita spedizione gratuita per prodotti selezionati | SÌ | Attiva l'esclusione della spedizione gratuita specifica per prodotto. |
| Configurazione principale del modulo | Disabilita spedizione gratuita per categorie selezionate | SÌ | Attiva l'esclusione della spedizione gratuita specifica per categoria. |
| Configurazione principale del modulo | Prodotti da escludere dalla spedizione gratuita | (Vuoto) | Aggiungi prodotti specifici qui usando lo strumento di ricerca. |
| Configurazione principale del modulo | Categorie da escludere dalla spedizione gratuita | (Nessuna selezionata) | Seleziona le categorie dalla vista ad albero. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho configurato il modulo, ma la spedizione gratuita è ancora visibile per un prodotto escluso. Cosa c'è che non va?**
R:

1.  **Controlla le tue impostazioni:** Ricontrolla che "Disabilita spedizione gratuita per prodotti selezionati" (o categorie) sia abilitato e che il prodotto/categoria specifico sia correttamente aggiunto all'elenco di esclusione.
2.  **Svuota la cache di PrestaShop:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" in alto a destra. A volte PrestaShop memorizza nella cache i calcoli di spedizione.
3.  **Testa con un nuovo carrello:** Assicurati di testare con un carrello nuovo, poiché la cache del browser o i dati di sessione potrebbero interferire. Prova in una finestra in incognito.
4.  **Conflitto voucher:** Se stai utilizzando un voucher di spedizione gratuita, assicurati che "Rimuovi codice voucher con spedizione gratuita" sia abilitato.

**D: Questo modulo influisce sulle mie tariffe di spedizione standard?**
R: No, questo modulo influisce solo sulla *disponibilità* dell'opzione "Spedizione Gratuita" (tramite regole del carrello o specifici corrieri di spedizione gratuita). Non modifica le tue tariffe di spedizione standard o altre configurazioni del corriere. Se la spedizione gratuita è disabilitata, i clienti vedranno e pagheranno semplicemente le tue opzioni di spedizione regolari.

**D: Posso escludere prodotti in base al peso o alle dimensioni invece di prodotti/categorie specifici?**
R: Questo modulo si rivolge specificamente a prodotti e categorie. Le regole di spedizione integrate di PrestaShop ti consentono di definire soglie di spedizione gratuita in base al peso totale del carrello o al prezzo. Questo modulo aggiunge un livello di *eccezione* a tali regole. Se hai bisogno di regole più complesse basate puramente su peso/dimensioni per *tutti* i prodotti, potresti aver bisogno di un modulo di spedizione più avanzato o di configurazioni di corriere personalizzate.

**D: Cosa succede se un cliente ha un prodotto escluso e un prodotto non escluso nel carrello?**
R: Se *qualsiasi* prodotto nel carrello è nella tua lista di esclusione (direttamente o tramite la sua categoria), la spedizione gratuita verrà disabilitata per l'intero carrello, anche se altri prodotti nel carrello normalmente si qualificherebbero. La logica del modulo è "se è presente un prodotto escluso, allora nessuna spedizione gratuita".

**D: Sto usando un tema personalizzato e lo strumento di ricerca prodotti non funziona correttamente.**
R: I temi personalizzati possono a volte interferire con JavaScript.

1.  **Controlla gli errori JavaScript:** Apri la console per sviluppatori del tuo browser (solitamente F12) e cerca eventuali errori nella scheda "Console" quando provi a utilizzare lo strumento di ricerca.
2.  **Compatibilità del tema:** Assicurati che il tuo tema sia completamente compatibile con la tua versione di PrestaShop.
3.  **Contatta il supporto:** Se vedi errori o il problema persiste, fornisci screenshot e log della console al supporto di MyPresta.eu.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Escludi prodotti selezionati dalla spedizione gratuita" opera principalmente sovrascrivendo le classi core di PrestaShop relative alla gestione del carrello e delle regole del carrello. Ciò gli consente di intercettare la logica di calcolo della spedizione gratuita e applicare le sue regole di esclusione prima che le opzioni di spedizione finali vengano presentate al cliente. Sfrutta il sistema di override di PrestaShop per le classi `CartController`, `Cart` e `CartRule`. Il modulo include anche un controller amministrativo dedicato per la ricerca e la gestione dei prodotti/categorie esclusi.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**:

  - `exfreeshipping/override/controllers/front/CartController.php`
    - **Nome classe e classe padre**: `CartController` (sovrascrive `CartControllerCore`)
    - **Responsabilità**: Questa sovrascrittura è cruciale per intercettare le azioni relative al carrello, in particolare quando i prodotti vengono aggiunti o rimossi, o quando vengono eseguiti i calcoli di spedizione. Assicura che la logica del modulo venga applicata ogni volta che lo stato del carrello cambia, influenzando l'idoneità alla spedizione gratuita.
- **Controller Admin Back-Office**:

  - `exfreeshipping/controllers/admin/AdminExfreeshippingSearchController.php`
    - **Nome scheda ed entità gestita**: Questo controller gestisce la funzionalità di ricerca AJAX per i prodotti all'interno della configurazione del modulo. Non gestisce direttamente un `ObjectModel` specifico ma fornisce dati per l'elenco di esclusione dei prodotti.
    - **Scopo**: Risponde alle richieste AJAX dalla pagina di configurazione del modulo per cercare prodotti per nome, consentendo all'amministratore di selezionare facilmente i prodotti da escludere.
  - `exfreeshipping/controllers/admin/index.php`
    - **Scopo**: Questo è un file `index.php` vuoto standard spesso incluso nelle directory per impedire l'elenco delle directory sui server web. Non contiene alcuna logica di controller funzionale.

### 4.3 Classi e Modelli Core (`classes/`)

- `exfreeshipping/override/classes/Cart.php`

  - **Nome classe e classe padre**: `Cart` (sovrascrive `CartCore`)
  - **Tabella database**: `ps_cart`
  - **Responsabilità**: Questa sovrascrittura è centrale per la funzionalità del modulo. Probabilmente modifica i metodi relativi al calcolo dei costi di spedizione o all'idoneità alla spedizione gratuita all'interno dell'oggetto `Cart`. Conterrà la logica per verificare se un prodotto nel carrello (o la sua categoria) è nell'elenco di esclusione e, in tal caso, per disabilitare il flag di spedizione gratuita per quel carrello.
  - **Metodi chiave (probabilmente modificati/estesi)**: `getProducts()`, `getPackageList()`, `getWsShippingCost()`, `getShippingCost()`, o metodi simili che determinano l'idoneità alla spedizione.
- `exfreeshipping/override/classes/CartRule.php`

  - **Nome classe e classe padre**: `CartRule` (sovrascrive `CartRuleCore`)
  - **Tabella database**: `ps_cart_rule`
  - **Responsabilità**: Questa sovrascrittura è responsabile della gestione dell'impostazione "Rimuovi codice voucher con spedizione gratuita". Modifica i metodi relativi all'applicazione o alla convalida delle regole del carrello per rimuovere i voucher di spedizione gratuita se un prodotto escluso è presente nel carrello.
  - **Metodi chiave (probabilmente modificati/estesi)**: `checkValidity()`, `addCartRule()`, `removeCartRule()` o metodi simili che interagiscono con le regole del carrello e la loro validità.
- `exfreeshipping/override/classes/index.php`

  - **Scopo**: Simile all'`index.php` dell'amministratore, questo è un file vuoto per impedire l'elenco delle directory.

### 4.4 Risorse JavaScript (`views/js/`)

- `exfreeshipping/lib/searchTool/views/js/autocomplete.js`
  - **Ambito**: Back-office (pagina di configurazione del modulo).
  - **Funzionalità**: Questo script alimenta l'interfaccia di ricerca e selezione dei prodotti nella pagina di configurazione del modulo.
  - **Dettagli**:
    - Inizializza un campo di input di completamento automatico per la ricerca di prodotti.
    - Collega i listener di eventi (ad esempio, `keyup`, `change`, `click`) all'input di ricerca e all'elenco dei risultati.
    - Invia richieste AJAX a `AdminExfreeshippingSearchController` per recuperare suggerimenti di prodotti in base all'input dell'utente.
    - Gestisce la visualizzazione dei risultati di ricerca e consente agli amministratori di selezionare i prodotti, aggiungendoli a un campo di input nascosto o a un elenco visibile di prodotti esclusi.
    - Gestisce la rimozione dei prodotti selezionati dall'elenco di esclusione.

### 4.5 Fogli di stile CSS (`views/css/`)

- `exfreeshipping/lib/searchTool/views/css/autocomplete.css`
  - **Ambito**: Back-office (pagina di configurazione del modulo).
  - **Stile**: Fornisce lo stile per l'input di completamento automatico della ricerca prodotti, l'elenco a discesa dei risultati di ricerca e la visualizzazione dei prodotti esclusi selezionati nella pagina di configurazione del modulo.
  - **Selettori chiave**: Probabilmente include stili per `.autocomplete-input`, `.autocomplete-results`, `.selected-product-tag`, ecc. Gli sviluppatori possono sovrascriverli nei loro temi amministrativi personalizzati se necessario.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template amministrativi (`views/templates/admin/`)**:
  - `exfreeshipping/lib/searchTool/views/scripts.tpl`
    - **Scopo**: Questo template è probabilmente incluso nel metodo `getContent()` del modulo per renderizzare la struttura HTML necessaria per lo strumento di ricerca prodotti, inclusi il campo di input di ricerca e l'area in cui vengono visualizzati i prodotti selezionati. Probabilmente include anche il tag `<script>` per caricare `autocomplete.js`.
  - `exfreeshipping/views/tpl/selectedProducts.tpl`
    - **Scopo**: Questo template viene utilizzato per renderizzare l'elenco dei prodotti che sono stati selezionati per l'esclusione dalla spedizione gratuita. Viene aggiornato dinamicamente dal JavaScript quando i prodotti vengono aggiunti o rimossi.

### 4.7 Schema del database e Mappa degli hook

- **Tabelle del database**:

  - Il modulo non crea tabelle SQL personalizzate.
  - Le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` utilizzando chiavi come `exfreeshipping_oos`, `exfreeshipping_vcode`, `exfreeshipping_visibility_rule`, `exfreeshipping_visibility_products`, `exfreeshipping_visibility_cat`.
  - Gli elenchi di prodotti e categorie esclusi sono memorizzati come array serializzati o stringhe separate da virgole all'interno di `ps_configuration` sotto `exfreeshipping_visibility_products` e `exfreeshipping_visibility_cat` rispettivamente.
- **Tabella degli hook registrati**:
  Il modulo utilizza principalmente override piuttosto che chiamate dirette agli hook per la sua logica principale. Tuttavia, potrebbe registrare alcuni hook standard per l'inizializzazione o scopi di visualizzazione specifici.

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionFrontControllerSetMedia` | Eseguito quando un controller front-office imposta i suoi media (CSS/JS). | Potenzialmente utilizzato per caricare CSS/JS specifici del front-office, sebbene l'impatto principale del modulo sia la logica di backend. |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Potrebbe essere utilizzato per la configurazione iniziale o il caricamento di script/stili molto leggeri se necessario, ma non direttamente per la logica principale. |
| `displayBackOfficeHeader` | Nella sezione `<head>` di ogni pagina del back-office. | Utilizzato per caricare `autocomplete.js` e `autocomplete.css` per la pagina di configurazione del modulo. |
| `actionCartSave` | Dopo che un carrello viene salvato o aggiornato. | Qui verrebbe attivata o rivalutata la logica principale del modulo per il controllo dei prodotti esclusi e la disabilitazione della spedizione gratuita. |
| `actionValidateOrder` | Quando un ordine viene convalidato. | Assicura che le regole di spedizione gratuita siano correttamente applicate nella fase finale del checkout. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto tecnico per il modulo "Escludi prodotti selezionati dalla spedizione gratuita", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda riguardante la funzionalità e la compatibilità del modulo.
