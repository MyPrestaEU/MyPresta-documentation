---
title: Step by Step - documentazione e manuale utente
sidebar:
  label: Step by Step - documentazione e manuale utente
description: Guida alla configurazione e alla risoluzione dei problemi per i negozi che hanno già il filtro categorie Step by Step.
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Step by step - categories su MyPresta.eu](https://mypresta.eu/modules/front-office-features/step-by-step-categories.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/step-by-step-categories/)
>
> ---


## 1. Requisiti

Il modulo gira in PrestaShop. Non ha bisogno di un altro modulo né di un account esterno.

- PrestaShop dalla 1.6.0.0, compresi PrestaShop 8 e 9.
- PHP nella versione richiesta da quella versione di PrestaShop. Il controllo degli aggiornamenti usa cURL se PHP lo ha. Altrimenti apre l'indirizzo con una richiesta ordinaria. Non installi un'estensione PHP in più per gli elenchi.
- Non serve nessun altro modulo.
- In multishop un blocco può appartenere a un negozio o a tutti.

## 2. Installazione

1. Nel back office apra **Moduli**, poi **Gestione moduli**.
2. Carichi il file zip e scelga **Installa**.
3. Apra **Configura** su **Step By Step - categories tree**. La pagina ha **Blocks**, **Settings** e **Updates**. **Blocks** è l'elenco dei set di menu. La prima visita crea la pagina nascosta di quell'elenco. Non compare come voce propria nel menu a sinistra.
4. L'installazione non svuota la cache in un passo separato. Se dopo un aggiornamento il negozio mostra ancora il layout precedente, svuoti la cache in **Parametri avanzati**, **Prestazioni**.

La disinstallazione toglie quella pagina nascosta. Blocchi, titoli, etichette e i due interruttori globali restano nel database. Dopo una nuova installazione gli stessi blocchi sono ancora lì. Apra **Configura** una volta per registrare di nuovo la pagina dell'elenco.

Oltre all'interruttore normale di **Gestione moduli** non c'è un'azione di attivazione separata. Se disattiva il modulo, gli elenchi spariscono dal negozio e i blocchi salvati restano.

## 3. Configurazione e uso nel back office

Crei un blocco, fissi la profondità dell'albero categorie e scelga il posto nel negozio. Il cliente sceglie una categoria. L'elenco successivo carica le figlie. **ok** apre la categoria scelta, o un prodotto se l'elenco prodotti è attivo.

Le immagini di questo capitolo sono del back office in inglese. Le scritte sullo schermo restano in inglese.

### 3.1 Pagina di configurazione del modulo

Apra **Moduli**, **Gestione moduli**, **Step By Step - categories tree**, **Configura**.

![Impostazioni](https://mypresta.eu/docs/images/docs/stepbystep-configure-settings.webp)

In alto ci sono **Blocks**, **Settings** e **Updates**. **Blocks** esce da questa pagina e apre l'elenco dei blocchi. **Settings** è la scheda iniziale. Sotto la barra c'è scritto che queste opzioni valgono per ogni blocco e che i blocchi si modificano da **Blocks**.

| Campo | All'inizio | Effetto |
|---|---|---|
| **Reset search fields** | No | Yes svuota gli elenchi dopo una ricerca. No tiene le categorie scelte dal visitatore. Il browser tiene quella scelta 30 minuti. |
| **Include Select2 library** | No | Yes carica lo script e il foglio di stile aggiuntivi per **Search inside dropdown** di un blocco. No lascia elenchi normali. |

Scelga **Save**. La pagina mostra **Settings saved.**

![Aggiornamenti](https://mypresta.eu/docs/images/docs/stepbystep-configure-updates.webp)

**Updates** è il modulo **MyPresta updates**.

| Campo | All'inizio | Effetto |
|---|---|---|
| **Manual check** | pulsante **Check now** | Chiede a MyPresta se esiste una versione più recente. **New version available!** porta al registro delle modifiche. **Module is up to date!** significa che questa installazione coincide con la versione pubblicata. Il pulsante non carica uno zip. |
| **Automatic notifications** | Enabled | Enabled ripete quel controllo circa ogni 3 giorni mentre lavora nel back office. Disabled lo salta. |
| **Product page** | link alla pagina del modulo | Apre la pagina Step by Step su mypresta.eu. |

**Save** mostra **Update settings saved.** Carichi un nuovo zip da **Gestione moduli** quando compare una versione più recente.

### 3.2 Elenco dei blocchi

Apra **Blocks**. Sotto la barra c'è scritto che ogni blocco è un set di elenchi.

![Elenco dei blocchi](https://mypresta.eu/docs/images/docs/stepbystep-blocks-list.webp)

| Campo | All'inizio | Effetto |
|---|---|---|
| **ID** | assegnato al salvataggio | Numero del blocco. Serve a distinguere le righe. |
| **Title** | Block e il numero, finché non scrive un titolo | Intestazione nella lingua del back office. |
| **Depth** | 3 in un blocco nuovo | Quanti elenchi disegna il blocco. |
| **Root category** | categoria Home del negozio in un blocco nuovo | Genitore del primo elenco, come numero e nome. |
| **Hook** | Top in un blocco nuovo | Posto del blocco nel negozio. |
| **Active** | Yes | L'icona attiva o disattiva il blocco. Off nasconde gli elenchi e lascia la riga. |
| **Position** | prossima posizione libera | Trascini la riga per cambiare l'ordine dei blocchi dello stesso hook. |

Le azioni di riga sono **Edit** e **Delete**. **Bulk actions** ha **Enable selection**, **Disable selection** e **Delete selected**. La conferma chiede **Delete selected blocks?**

**Add new** apre un modulo vuoto. Un blocco nuovo è attivo, profondità 3, radice la categoria Home, ordine per ID crescente, contatore prodotti spento, pulsante dopo l'ultimo elenco, prodotti spenti, invio automatico spento, ricerca nell'elenco spenta, etichetta dentro l'elenco, hook Top e il negozio corrente. Lo salvi. Il modulo si riapre perché compili le etichette. Le etichette compaiono nel modulo solo quando il blocco esiste.

L'elenco mostra i blocchi del negozio in cui si trova e i blocchi con **All shops**.

### 3.3 Modulo del blocco

Apra una riga con **Edit**, oppure usi **Add new** e poi la schermata di modifica che segue il primo salvataggio.

![Modulo del blocco, parte alta](https://mypresta.eu/docs/images/docs/stepbystep-block-form.webp)

![Modulo del blocco, etichette e posizione](https://mypresta.eu/docs/images/docs/stepbystep-block-form-bottom.webp)

| Campo | All'inizio | Effetto |
|---|---|---|
| **Block title** | vuoto | Intestazione sopra gli elenchi. Un campo per lingua del negozio. |
| **Depth** | 3 | Quanti elenchi disegna il blocco. Salvi il blocco e lo riapra per compilare un'etichetta per livello. Il modulo mostra al massimo 30 campi etichetta. |
| **Root category** | categoria Home | Il primo elenco mostra le figlie di questa categoria. |
| **Sort method** | By ID | By ID, By name o By position. Position è l'ordine della categoria nel catalogo. |
| **Sort direction** | Ascending | Ascending o Descending. |
| **Products counter** | No | Yes scrive il numero di prodotti tra parentesi dopo il nome della categoria. |
| **Submit button** | After last select box | After each select box mostra **ok** al livello in cui si trova il cliente. After last select box mostra un **ok** per tutto il set. |
| **Include products** | No | Yes mostra un elenco di prodotti dell'ultima categoria scelta. |
| **Auto submit** | No | Yes invia il modulo appena è scelta l'ultima categoria disponibile. Il negozio apre quella categoria. Vale quando **Include products** è spento. Se la categoria scelta non ha figlie, il negozio la apre lo stesso. |
| **Search inside dropdown** | No | Yes attiva la ricerca dentro gli elenchi. In **Settings**, **Include Select2 library** deve essere acceso anche lui. |
| **Exclude categories** | vuoto | ID di categoria che non devono comparire negli elenchi. Li separi con virgole, per esempio 1,2,3,4,5,6. La ricerca accanto al campo trova una categoria e aggiunge il suo ID. |
| **Show on category pages** | vuoto | Vuoto mostra il blocco su ogni pagina in cui sta il suo hook. ID di categoria, separati da virgole, lo mostrano solo su quelle pagine di categoria. |
| **Label position** | Inside select box | Inside select box mette l'etichetta come prima opzione. Outside select box la stampa sopra il campo. |
| **Label 1**, **Label 2** e seguenti | vuoto | Un campo per livello e per lingua. Compaiono dopo il salvataggio del blocco. Cambi **Depth** e salvi se ne servono di più o di meno. |
| **Module position** | Top | Top, displaySearch, TopColumn, Left column, Right column, Home o displaySbs. |
| **Position top settings** | Blocks | Blocks impila gli elenchi. Wide horizontal bar li mette su una riga. La barra larga vale su Top e displaySearch. Gli altri posti restano impilati. Sulla barra larga **ok** sta dopo l'ultimo elenco e scende alla riga successiva se non c'è spazio. |
| **Shop** | il negozio che sta modificando | Un negozio o **All shops**. **All shops** lascia il blocco in ogni negozio. |
| **Active** | Yes | No nasconde il blocco nel negozio. |

Scelga **Save**. PrestaShop mostra la conferma abituale. Cancellare un blocco cancella anche il titolo, la scelta della barra larga e le etichette di livello.

Per mostrare un blocco in un file del tema che non ha un hook già posizionato, usi l'hook displaySbs e metta **Module position** su displaySbs. Gli altri posti si agganciano in **Design**, **Posizioni**, se il tema non li stampa da solo.

## 4. Negozio

Il cliente vede il titolo del blocco e gli elenchi.

1. Il primo elenco mostra le figlie della categoria radice. Gli elenchi successivi restano inattivi finché il livello precedente ha una categoria.
2. Il cliente sceglie una categoria. Un indicatore copre il blocco. L'elenco successivo si riempie con le figlie. L'indicatore sparisce quando l'elenco è pronto, e anche se la richiesta fallisce.
3. Gli ID esclusi non compaiono in quegli elenchi.
4. Con **Submit button** su after each select box, **ok** sta al livello corrente. Con after last select box c'è un **ok** per il set.
5. **ok** apre la categoria scelta.
6. Con **Include products**, l'ultimo livello aggiunge un elenco prodotti. La prima opzione è **- Select Product -**. **ok** usa allora il prodotto scelto.
7. Con **Auto submit** acceso e **Include products** spento, l'ultima categoria si apre senza **ok**. La stessa apertura vale se la categoria scelta non ha figlie.
8. Con **Reset search fields** spento, una visita successiva può mostrare le stesse categorie. Il browser le tiene 30 minuti. Con l'opzione accesa, gli elenchi partono vuoti.
9. Se **Search inside dropdown** e **Include Select2 library** sono accesi, il cliente può scrivere dentro l'elenco.

Nella colonna sinistra e in quella destra i livelli stanno uno sotto l'altro, con il titolo in maiuscolo come su Classic. Sulla barra larga i livelli stanno su una riga. Su uno schermo stretto la barra larga si impila. Colori, bordo e pulsante **ok** arrivano dal tema, anche Hummingbird e Classic su PrestaShop 9.

Un blocco con **Show on category pages** compilato manca sulle altre pagine. Un blocco inattivo manca. Manca anche un blocco di un altro negozio.

## 5. Problemi

**Il blocco manca nel negozio.** Apra il blocco e controlli **Active**, **Module position** e **Shop**. **Show on category pages** vuoto lo mostra su ogni pagina di quell'hook. Un elenco compilato lo mostra solo su quelle pagine di categoria. In **Design**, **Posizioni**, controlli che l'hook stia sulle pagine previste. Per un posto proprio il template deve chiamare displaySbs e il blocco deve usare quella posizione.

**L'elenco successivo non si riempie, o l'indicatore resta.** Svuoti la cache del negozio perché prenda il foglio di stile e lo script attuali. L'indicatore deve sparire quando la richiesta finisce, anche se la risposta non si può applicare. Se il negozio mostra ancora il vecchio caricatore gif, il CSS precedente è in cache.

**La ricerca nell'elenco non fa nulla.** Accenda **Include Select2 library** in **Settings** e **Search inside dropdown** sul blocco. Salvi entrambi. Svuoti la cache.

**A un blocco nuovo mancano le etichette.** Salvi il blocco una volta. Lo riapra. **Label 1** e il resto compaiono quando il blocco esiste, e solo fino al **Depth** salvato.

**Manca una categoria che dovrebbe stare nell'elenco.** Tolga il suo ID da **Exclude categories**. Controlli che sia figlia del genitore scelto e che sia attiva nel catalogo.

**La barra larga continua a impilare i campi.** **Wide horizontal bar** vale su Top e displaySearch. Sinistra, destra, home, TopColumn e displaySbs restano impilati. Sul telefono la barra larga si impila di proposito.

**Dopo un aggiornamento manca la pagina Blocks.** Apra **Configura** una volta. Quella visita registra la pagina. Non disinstalli il modulo se vuole continuare a usare le righe già presenti. La disinstallazione toglie la pagina e lascia le righe.

**La vecchia schermata di configurazione non ha l'icona del cestino.** Quella è una versione precedente. Carichi lo zip attuale dall'account cliente. Nella versione attuale si cancella un blocco nell'elenco **Blocks**, con **Delete** sulla riga o con **Delete selected**.

## 6. Per gli sviluppatori

### 6.1 Panoramica

Nome tecnico `stepbystep`, classe `Stepbystep`, versione 1.9.0, autore MyPresta.eu, scheda `front_office_features`. Il nome nel back office è **Step By Step - categories tree**.

`AdminStepbystepBlocksController` scrive le righe in `sbs_block` e titolo, etichette e flag della barra larga in `Configuration`. Gli hook del negozio leggono le righe attive del negozio corrente o con `id_shop = 0`. `controllers/front/tree.php` consegna lo script che riempie l'elenco successivo.

### 6.2 File

| File | Ruolo |
|---|---|
| `stepbystep.php` | Installazione, hook, modulo impostazioni, HTML degli elenchi, script del negozio. |
| `controllers/admin/AdminStepbystepBlocksController.php` | Elenco blocchi e modulo del blocco. |
| `models/SbsBlock.php` | Modello oggetto di `sbs_block`. |
| `controllers/front/tree.php` | Controller del negozio che consegna lo script del livello successivo. |
| `views/templates/hook/front.tpl` | Markup del negozio per ogni hook. |
| `views/templates/hook/header.tpl` | Stampa lo script inline. |
| `views/templates/admin/configure.tpl` | Barra Blocks, Settings, Updates. |
| `css/sbs-front.css` | Layout del negozio, variabili del tema, indicatore. |
| `js/advajax.js` | Richiesta degli elenchi. |
| `lib/updatesChecker.php` | Controllo aggiornamenti. Classe `stepbystepUpdate`. |
| `lib/searchTool/searchTool.php` | Ricerca dell'ID categoria nel modulo del blocco. Classe `searchToolstepbystep`. |
| `lib/prestashop9compatibility.php` | Classe `stepbystepPrestashopNewCompatibility`. |
| `views/css/admin.css` | Barra del back office. |

`tree.php` nella radice del modulo è la copia precedente del controller del negozio. Il link del negozio usa `controllers/front/tree.php`. `views/templates/hook/block.tpl`, `blockSbs.tpl`, `top.tpl` e `displaySearch.tpl` non vengono renderizzati. `css/sbs-block.css` e `css/sbs-top.css` non vengono caricati.

### 6.3 Controller

`AdminStepbystepBlocksController` estende `ModuleAdminController`. `class_name` è `AdminStepbystepBlocks`. `id_parent` è `-1`, la pagina è nascosta nel menu. L'identificatore dell'elenco è `id`. Il trascinamento della posizione chiama `ajaxProcessUpdatePositions`. Il filtro dell'elenco è `id_shop` del negozio di contesto o `0`.

`stepbysteptreeModuleFrontController` è il controller del negozio `tree`. `initContent` imposta `ajax` e non chiama `parent::initContent`. Legge `sbs_block`, `sbs_pid`, `sbs_lvl` e, alla conferma, `sbs_blockid` e `sbs_cidlink`. Il corpo della risposta è JavaScript. Un blocco assente chiude la risposta.

### 6.4 Hook

Hook registrati: `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayTop`, `displaySearch`, `displayHome`, `displaySbs`, `displayBackOfficeHeader`. Da PrestaShop 1.6 anche `displaytopColumn`.

| Hook | Valore posizione del blocco | Layout |
|---|---|---|
| `displayTop` | 1 | in alto, barra larga se `sbs_top_type{id}` è 1 |
| `displayLeftColumn` | 2 | impilato |
| `displayRightColumn` | 3 | impilato |
| `displayHome` | 4 | impilato |
| `displaytopColumn` | 5 | impilato |
| `displaySearch` | 6 | in alto, barra larga se `sbs_top_type{id}` è 1 |
| `displaySbs` | 7 | impilato |

`displayHeader` carica `js/advajax.js` e `css/sbs-front.css`. Se `SBS_SELECT2` è 1, carica anche Select2. Non c'è un override di `enable()` né di `disable()`.

### 6.5 Override

Il modulo non sostituisce nessuna classe né nessun controller di PrestaShop.

### 6.6 Database

| Tabella | Contenuto |
|---|---|
| `ps_sbs_block` | `id`, `depth`, `root`, `orderby`, `orderway`, `counter`, `each_submit`, `lbl_position`, `block_position`, `position`, `active`, `products`, `last_submit`, `search_inside`, `exclude`, `id_shop`, `on_cat_only`, `id_categories`. |

Il prefisso è quello del negozio. La disinstallazione non cancella la tabella. `inconsistency()` aggiunge una colonna mancante di questo elenco quando si apre la configurazione del modulo o l'elenco dei blocchi. `on_cat_only` resta e non è nel modulo. Il negozio usa `id_categories`.

### 6.7 Chiavi di configurazione e traduzioni

| Chiave | Se manca |
|---|---|
| `SBS_RESET` | Vale 0. La scelta resta 30 minuti nei cookie `sbs_selectbox_{block}_{level}`. |
| `SBS_SELECT2` | Vale 0. Select2 non viene caricato. |
| `sbs_title{id}` | Titolo del blocco, multilingue. |
| `{id}sbs_lbl_{n}` | Etichetta del livello `n`, multilingue, da 1 alla profondità, al massimo 30. |
| `sbs_top_type{id}` | 0 impilato, 1 barra larga. |

L'installazione scrive anche `sbs_depth`, `sbs_counter`, `sbs_each_submit`, `sbs_position`, `sbs_lbl_position` e `sbs_root`. Il modulo del blocco non legge quelle chiavi. I blocchi nuovi usano i valori di `prepareObjectDefaults()`.

Le traduzioni stanno in `translations/{iso}.php`. I testi del controller dei blocchi hanno origine `AdminStepbystepBlocksController`. Il testo del pulsante è il testo del modulo `ok`. Il segnaposto prodotto è `- Select Product -`.

### 6.8 Estensione

Sostituisca `views/templates/hook/front.tpl` nel tema come `themes/{theme}/modules/stepbystep/views/templates/hook/front.tpl`. Sostituisca `css/sbs-front.css` per la stessa via se il tema deve cambiare il layout. Il posto del pulsante sulla barra larga è l'ordine flex di quel foglio: il `.sbs__actions` visibile sta dopo gli elenchi e va a capo con loro.

## 7. Aiuto

Pagina del modulo: [Step by Step categories](https://mypresta.eu/modules/front-office-features/step-by-step-categories.html).

Per scrivere a proposito di questo modulo, entri nell'account cliente su [mypresta.eu](https://mypresta.eu), apra il modulo di contatto e scelga **Support for paid modules**. Quell'argomento indica che serve l'accesso. Dopo l'accesso, scelga questo modulo dalla cronologia acquisti.
