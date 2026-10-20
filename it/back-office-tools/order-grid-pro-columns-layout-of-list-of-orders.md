---
title: "Order Grid Pro - colonne e layout dell'elenco degli ordini - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Order Grid Pro - colonne & layout dell'elenco degli ordini di MyPresta.eu."
sidebar:
  label: "Order Grid Pro - colonne e layout dell'elenco degli ordini - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Order Grid Pro - columns & layout of list of orders su MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-grid-pro-columns-layout-of-list-of-orders.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/order-grid-pro-columns-layout-of-list-of-orders/)
>
> ---


# Order Grid Pro - colonne e layout dell'elenco degli ordini

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.7.x, 1.7.8.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" verrai indirizzato alla pagina di configurazione principale di Order Grid Pro. Questa pagina è dove definisci quali colonne appaiono nel tuo elenco ordini e la loro disposizione.

La configurazione è tipicamente divisa in diverse schede o sezioni, che ti consentono di gestire diversi aspetti della griglia degli ordini.

**Impostazioni generali / Visibilità e ordine delle colonne:**
Questo è il cuore del modulo. Tipicamente vedrai un elenco di tutte le colonne disponibili, sia le colonne predefinite di PrestaShop che quelle nuove aggiunte da Order Grid Pro.

- **Cosa fa questa impostazione:** Questa sezione ti consente di scegliere quali colonne sono visibili nel tuo elenco ordini del Back Office e di organizzarne l'ordine di visualizzazione. Di solito vedrai due elenchi: "Colonne disponibili" e "Colonne attive" (o simili).
- **Effetto della modifica di questa impostazione:**
  - *Spostare una colonna da "Disponibili" a "Attive":* La colonna apparirà nel tuo elenco ordini del Back Office.
  - *Spostare una colonna da "Attive" a "Disponibili":* La colonna verrà nascosta dal tuo elenco ordini del Back Office.
  - *Trascinare e rilasciare le colonne all'interno di "Colonne attive":* Modifica l'ordine di visualizzazione da sinistra a destra delle colonne nel tuo elenco ordini.
- **Valore consigliato:** Questo dipende interamente dalle esigenze del tuo team. Inizia abilitando le colonne che controlli frequentemente e nascondendo quelle che non usi mai. Disponile in un flusso logico per le tue attività quotidiane.
- **Scenario / esempio del commerciante:**
  - **Responsabile del magazzino:** Potrebbe abilitare "Miniatura del prodotto", "Peso del prodotto", "Numero di tracciamento" e "Corriere" e posizionarli in evidenza a sinistra per una rapida elaborazione della spedizione. Potrebbe nascondere "Email del cliente" o "Metodo di pagamento" se non rilevanti per il suo ruolo.
  - **Agente del servizio clienti:** Darebbe priorità a "Telefono del cliente", "Email del cliente", "Frammento del thread del servizio clienti" e "Messaggio dell'ordine" per rispondere rapidamente alle richieste senza aprire ogni ordine.
  - **Dipartimento finanziario:** Potrebbe concentrarsi su "Metodo di pagamento", "ISO della valuta", "Totale pagato" e "Regole del carrello" per verificare transazioni e sconti.

**Opzioni specifiche delle colonne (Esempi di nuove colonne che puoi abilitare):**

- **Telefono del cliente:**

  - **Cosa fa questa impostazione:** Visualizza il numero di telefono del cliente direttamente nell'elenco degli ordini.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I numeri di telefono appaiono, rendendo facile chiamare i clienti senza navigare nei dettagli dell'ordine.
    - *Quando disabilitato:* I numeri di telefono sono nascosti.
  - **Valore consigliato:** SÌ, se il tuo servizio clienti o il team di spedizione ha spesso bisogno di contattare i clienti.
  - **Scenario / esempio del commerciante:** Un agente del servizio clienti può chiamare rapidamente un cliente per un problema di consegna direttamente dall'elenco degli ordini.
- **Numero di tracciamento:**

  - **Cosa fa questa impostazione:** Mostra il numero di tracciamento associato all'ordine.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I numeri di tracciamento sono visibili, consentendo una rapida copia-incolla per gli aggiornamenti di tracciamento.
    - *Quando disabilitato:* I numeri di tracciamento sono nascosti.
  - **Valore consigliato:** SÌ, essenziale per i team di magazzino e servizio clienti.
  - **Scenario / esempio del commerciante:** Il personale del magazzino può verificare rapidamente se un numero di tracciamento è stato aggiunto prima della spedizione, o il servizio clienti può fornirlo a un cliente.
- **Miniatura del prodotto di prima linea:**

  - **Cosa fa questa impostazione:** Visualizza una piccola immagine del primo prodotto nell'ordine.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Appare un segnale visivo del contenuto dell'ordine, aiutando l'identificazione rapida.
    - *Quando disabilitato:* Non viene mostrata alcuna immagine del prodotto.
  - **Valore consigliato:** SÌ, molto utile per la conferma visiva, specialmente per la preparazione del magazzino.
  - **Scenario / esempio del commerciante:** Il personale del magazzino può confermare visivamente il tipo di prodotto in un ordine senza aprirlo, accelerando la preparazione.
- **Peso dell'ordine:**

  - **Cosa fa questa impostazione:** Mostra il peso totale dell'ordine.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il peso dell'ordine viene visualizzato, utile per i calcoli di spedizione o la selezione del corriere.
    - *Quando disabilitato:* Il peso dell'ordine è nascosto.
  - **Valore consigliato:** SÌ, se tratti prodotti fisici e il peso è un fattore nella spedizione.
  - **Scenario / esempio del commerciante:** I responsabili delle spedizioni possono valutare rapidamente le dimensioni e i pesi dei pacchi per spedizioni in blocco.
- **Frammento del thread del servizio clienti:**

  - **Cosa fa questa impostazione:** Visualizza un breve frammento dell'ultimo messaggio del servizio clienti relativo all'ordine.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Fornisce un contesto immediato sulle recenti comunicazioni con i clienti.
    - *Quando disabilitato:* Non viene mostrato alcun frammento.
  - **Valore consigliato:** SÌ, inestimabile per i team di servizio clienti.
  - **Scenario / esempio del commerciante:** Un agente del servizio clienti può vedere se un cliente ha recentemente chiesto informazioni su un ordine senza aprire l'intero thread.
- **ISO della valuta:**

  - **Cosa fa questa impostazione:** Mostra il codice ISO della valuta utilizzata per l'ordine (ad esempio, EUR, USD).
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Utile per i negozi internazionali per identificare rapidamente la valuta.
    - *Quando disabilitato:* L'ISO della valuta è nascosto.
  - **Valore consigliato:** SÌ, se gestisci un negozio multi-valuta.
  - **Scenario / esempio del commerciante:** Il personale finanziario può ordinare o filtrare rapidamente gli ordini per valuta per la riconciliazione.
- **Regole del carrello (Sconti) applicate:**

  - **Cosa fa questa impostazione:** Indica se sono state applicate regole del carrello (sconti) all'ordine.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Fornisce una rapida panoramica degli ordini scontati.
    - *Quando disabilitato:* Le informazioni sugli sconti applicati sono nascoste.
  - **Valore consigliato:** SÌ, per finanza, marketing o servizio clienti per comprendere i prezzi.
  - **Scenario / esempio del commerciante:** Il marketing può identificare rapidamente gli ordini che hanno utilizzato un codice promozionale specifico.

**Salvataggio delle modifiche:**
Ricorda sempre di cliccare sul pulsante "Salva" o "Aggiorna" dopo aver apportato modifiche alle selezioni o all'ordine delle colonne. Il modulo salva l'ordine delle colonne come JSON, garantendo che il tuo layout personalizzato persista.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### 2.2.1 AdminMyordergridproAjaxController (Back Office > Moduli > Configura > Order Grid Pro)

Questo controller gestisce principalmente le interazioni dinamiche sulla pagina di configurazione del modulo. Non ha una voce di menu separata nella navigazione di PrestaShop.

- **Nome schermata e posizione del menu:** Questo controller viene attivato quando ti trovi sulla pagina "Moduli > Gestione moduli > Order Grid Pro > Configura". Elabora le richieste AJAX effettuate dal JavaScript su quella pagina.
- **Azioni e impostazioni disponibili:** Gestisce il salvataggio e il caricamento delle tue configurazioni di griglia personalizzate (quali colonne sono visibili e il loro ordine). Quando trascini e rilasci le colonne o ne attivi la visibilità sulla pagina di configurazione del modulo, questo controller riceve i dati e li salva.
- **Effetto delle modifiche:** Qualsiasi modifica apportata al layout delle colonne sulla pagina di configurazione del modulo viene inviata a questo controller, che poi aggiorna le preferenze memorizzate per la tua griglia degli ordini. Ciò garantisce che quando navighi su "Ordini > Ordini", il tuo layout personalizzato venga applicato.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Interagisci con questo controller indirettamente semplicemente configurando il modulo sulla sua pagina principale. Non esiste una "vista di gestione" diretta per i commercianti qui; è il processore di backend per le tue scelte di configurazione.

#### 2.2.2 index.php (myordergridpro/controllers/admin/index.php)

Questo file è un segnaposto standard o un punto di ingresso per i controller di amministrazione all'interno di un modulo, garantendo che l'accesso diretto alla directory sia impedito e che i meccanismi di sicurezza di PrestaShop siano rispettati. Non rappresenta una schermata distinta e configurabile per il commerciante.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Pagina di configurazione del modulo** | **Visibilità e ordine delle colonne** | Varia in base al ruolo | Seleziona quali colonne appaiono nell'elenco ordini del Back Office e il loro ordine di visualizzazione. Impatta direttamente l'efficienza del team. |
|  | *Telefono del cliente* | SÌ | Visualizza il numero di telefono del cliente per un contatto rapido. |
|  | *Numero di tracciamento* | SÌ | Mostra il numero di tracciamento dell'ordine per la spedizione/supporto. |
|  | *Miniatura del prodotto di prima linea* | SÌ | Segnale visivo del primo prodotto nell'ordine. |
|  | *Peso dell'ordine* | SÌ (per beni fisici) | Visualizza il peso totale dell'ordine per la spedizione. |
|  | *Frammento del thread del servizio clienti* | SÌ | Fornisce contesto sulle recenti comunicazioni con i clienti. |
|  | *ISO della valuta* | SÌ (per multi-valuta) | Mostra il codice della valuta per i negozi internazionali. |
|  | *Regole del carrello applicate* | SÌ | Indica se sono stati utilizzati sconti sull'ordine. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho configurato le colonne, ma non vedo le modifiche nella pagina Ordini.**
R:

1. **Svuota la cache di PrestaShop:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" in alto a destra. A volte, PrestaShop memorizza nella cache le configurazioni dei moduli.
2. **Cache del browser:** Prova a svuotare la cache del tuo browser o ad aprire il Back Office in una finestra in incognito/privata per assicurarti di non visualizzare una vecchia versione della pagina memorizzata nella cache.
3. **Salva configurazione:** Ricontrolla di aver cliccato sul pulsante "Salva" o "Aggiorna" nella pagina di configurazione del modulo dopo aver apportato le modifiche.

**D: Alcune colonne che ho abilitato sono vuote o mostrano "N/D". Perché?**
R: Questo di solito significa che i dati per quella specifica colonna non sono disponibili per quell'ordine particolare. Ad esempio:

- "Numero di tracciamento" sarà vuoto se nessun numero di tracciamento è stato aggiunto all'ordine.
- "Frammento del thread del servizio clienti" sarà vuoto se non ci sono messaggi del servizio clienti per quell'ordine.
- "Peso dell'ordine" potrebbe essere vuoto se i pesi dei prodotti non sono definiti o se l'ordine contiene solo prodotti virtuali.
  Questo è un comportamento normale e indica dati mancanti piuttosto che un errore del modulo.

**D: Il drag-and-drop per riordinare le colonne non funziona.**
R:

1. **Conflitto JavaScript:** Un altro modulo o il tuo tema potrebbe avere un conflitto JavaScript. Prova a disabilitare altri moduli installati di recente uno per uno per identificare il colpevole.
2. **Problema del browser:** Testa in un browser diverso (Chrome, Firefox, Edge) per escludere un problema specifico del browser.
3. **Svuota cache:** Svuota sia la cache di PrestaShop che quella del browser come descritto sopra.

**D: Questo modulo rallenterà il mio Back Office?**
R: Il modulo è progettato per utilizzare gli hook ufficiali della griglia di PrestaShop ed evitare override del core, il che aiuta a mantenere le prestazioni e la compatibilità. Sebbene l'aggiunta di molte nuove colonne richieda a PrestaShop di recuperare più dati, l'impatto è generalmente minimo. Se noti rallentamenti significativi, considera di ridurre il numero di colonne personalizzate molto complesse che hai abilitato.

**D: Questo modulo è compatibile con il mio tema personalizzato?**
R: Sì, questo modulo funziona all'interno del Back Office di PrestaShop, che utilizza il proprio tema predefinito (New Classic o simile). Non influisce sul tuo tema front-office, quindi non dovrebbero esserci problemi di compatibilità con i temi front-office personalizzati.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Order Grid Pro" estende la funzionalità dell'elenco ordini del Back Office di PrestaShop, mirando specificamente al sistema di griglia Symfony introdotto in PrestaShop 1.7.7+. Aderisce alle migliori pratiche di sviluppo dei moduli di PrestaShop utilizzando hook ufficiali (`actionGet` e `actionSet` per le definizioni della griglia) piuttosto che override diretti del core. Ciò garantisce compatibilità e stabilità degli aggiornamenti. Il modulo inietta principalmente nuove definizioni di colonna e fornitori di dati nella griglia degli ordini esistente e memorizza le preferenze dell'utente per la visibilità e l'ordine delle colonne utilizzando la configurazione standard di PrestaShop. Le chiamate AJAX gestiscono gli aggiornamenti dinamici di queste preferenze.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**: Nessuno. Questo modulo è puramente Back-Office.
- **Controller Admin Back-Office**:

  - `controllers/admin/AdminMyordergridproAjaxController.php`
    - **Nome classe e classe genitore**: `AdminMyordergridproAjaxController` estende `ModuleAdminController`.
    - **Responsabilità**: Questo controller è responsabile della gestione delle richieste AJAX dalla pagina di configurazione del modulo. Elabora le richieste per salvare e caricare la configurazione personalizzata della griglia degli ordini (visibilità e ordine delle colonne). Tipicamente riceve dati JSON che rappresentano il layout di griglia desiderato e li memorizza in `Configuration::updateValue()`.
    - **Percorsi**: Risponde alle chiamate AJAX effettuate a `index.php?controller=AdminMyordergridproAjax&token=...&ajax=1`.
  - `controllers/admin/index.php`
    - **Nome classe e classe genitore**: Non una classe, ma un file di sicurezza.
    - **Responsabilità**: Questo è un file `index.php` vuoto standard posizionato nelle directory dei controller per impedire l'elenco delle directory e l'accesso diretto, migliorando la sicurezza. Tipicamente contiene `<?php header('Expires: Mon, 26 Jul 1997 05:00:00 GMT'); header('Last-Modified: '.gmdate('D, d M Y H:i:s').' GMT'); header('Cache-Control: no-store, no-cache, must-revalidate'); header('Cache-Control: post-check=0, pre-check=0', false); header('Pragma: no-cache'); header('Location: ../'); exit;`.

### 4.3 Classi e modelli core (`classes/`)

Il modulo non sembra definire classi `ObjectModel` personalizzate o tabelle di database. Funziona principalmente estendendo le definizioni di griglia esistenti di PrestaShop e memorizzando i dati di configurazione in `ps_configuration`.

### 4.4 Risorse JavaScript (`views/js/`)

- `views/js/grid_pro.js`

  - **Ambito**: Back-office (pagina Elenco ordini).
  - **Descrizione**: Questo script contiene probabilmente la logica principale per manipolare la griglia Symfony di PrestaShop nella pagina "Ordini > Ordini". Sarebbe responsabile di:
    - Leggere la configurazione delle colonne salvata da `Configuration::get()`.
    - Aggiungere/rimuovere dinamicamente colonne alla griglia in base alla configurazione.
    - Applicare l'ordine personalizzato delle colonne.
    - Potenzialmente gestire aggiornamenti in tempo reale o logica di rendering di colonne specifiche.
    - Collegarsi agli eventi della griglia di PrestaShop (ad esempio, `prestashop.on('grid.loaded', ...)`).
- `views/js/order_grid_admin.js`

  - **Ambito**: Back-office (pagina di configurazione del modulo).
  - **Descrizione**: Questo script è utilizzato principalmente nella pagina di configurazione del modulo (`getContent()`). Gestisce l'interfaccia utente per la selezione e l'ordinamento delle colonne. Ciò include:
    - Implementazione della funzionalità drag-and-drop per il riordino delle colonne.
    - Gestione degli elenchi "Colonne disponibili" e "Colonne attive".
    - Collegamento dei listener di eventi a interruttori/checkbox per la visibilità delle colonne.
    - Effettuare chiamate AJAX a `AdminMyordergridproAjaxController.php` per salvare la configurazione aggiornata.
- `views/js/order_list_live_status.js`

  - **Ambito**: Back-office (pagina Elenco ordini).
  - **Descrizione**: Questo script fornisce probabilmente funzionalità per aggiornamenti in tempo reale o elementi interattivi direttamente all'interno dell'elenco degli ordini. Ciò potrebbe includere:
    - Aggiornamenti di stato basati su AJAX per gli ordini senza aggiornamento della pagina.
    - Tooltip o popover per informazioni aggiuntive su colonne specifiche.
    - Potenzialmente migliorando i menu a discesa di cambio stato predefiniti o aggiungendo azioni rapide personalizzate.

### 4.5 Fogli di stile CSS (`views/css/`)

- `views/css/order_grid_admin.css`
  - **Ambito**: Back-office (pagina di configurazione del modulo e potenzialmente pagina Elenco ordini).
  - **Descrizione**: Questo foglio di stile fornisce lo stile visivo per l'interfaccia di configurazione del modulo, garantendo che gli elementi drag-and-drop e gli elenchi di colonne siano presentati chiaramente. Potrebbe anche includere piccole regolazioni di stile per le nuove colonne introdotte nell'elenco degli ordini effettivo per garantire un corretto allineamento e leggibilità all'interno del tema del Back Office di PrestaShop.
  - **Selettori di classe CSS chiave**: Probabilmente si rivolge a ID o classi specifici all'interno del template `getContent()` del modulo e potenzialmente a nuove classi di colonna iniettate nella griglia.

### 4.6 Struttura del template Smarty (`views/templates/`)

Le informazioni del modulo indicano che non sono stati trovati file `.tpl` espliciti in `views/templates/`. Ciò suggerisce che l'interfaccia di configurazione del modulo è probabilmente renderizzata direttamente all'interno del metodo `getContent()` del file principale del modulo (`index.php`) utilizzando PHP per generare l'HTML, oppure inietta dinamicamente il contenuto nei template di griglia esistenti di PrestaShop tramite hook.

Se i template fossero presenti, sarebbero tipicamente:

- **Template degli hook (`views/templates/hook/`)**: Per il rendering del nuovo contenuto delle colonne all'interno delle celle della griglia.
- **Template di amministrazione (`views/templates/admin/`)**: Per il modulo di configurazione del modulo.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Il modulo non crea tabelle SQL personalizzate.
  - Le impostazioni di configurazione (ad esempio, la stringa JSON che rappresenta l'ordine e la visibilità delle colonne) sono memorizzate nella tabella `ps_configuration` utilizzando chiavi come `MYORDERGRIDPRO_CONFIG` o simili.
- **Tabella degli hook registrati**:
  Il modulo si basa principalmente sugli hook della griglia Symfony di PrestaShop per la sua funzionalità.

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionGet` e `actionSet` (per le definizioni della griglia) | Quando la griglia degli ordini viene definita e renderizzata nel Back Office. | Questi sono gli hook principali utilizzati per iniettare nuove definizioni di colonna e fornitori di dati nella griglia degli ordini esistente di PrestaShop. `actionGet` consente al modulo di recuperare la definizione corrente della griglia e `actionSet` gli consente di modificare o aggiungere nuove colonne prima che la griglia venga renderizzata. |
| `displayBackOfficeHeader` | Eseguito nella sezione `<head>` di ogni pagina del Back Office. | Utilizzato per includere risorse CSS e JavaScript (`order_grid_admin.css`, `grid_pro.js`, `order_grid_admin.js`, `order_list_live_status.js`) specificamente per il Back Office, assicurando che vengano caricate quando necessario. |
| `displayAdminOrderListToolbar` (o simile) | Renderizza il contenuto nell'area della barra degli strumenti dell'elenco degli ordini. | Potenzialmente utilizzato per aggiungere pulsanti di azione rapida o filtri relativi alla funzionalità del modulo. |
| `actionAdminOrdersListingFieldsModifier` (o simile) | Modifica i campi/colonne disponibili nella query dell'elenco degli ordini. | Consente al modulo di aggiungere nuovi campi alla query SQL che recupera i dati dell'ordine, consentendo la visualizzazione di dati di colonne personalizzate. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per "Order Grid Pro - colonne e layout dell'elenco degli ordini", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team è dedicato a garantire che il tuo modulo funzioni perfettamente e ti aiuti a massimizzare l'efficienza del tuo negozio PrestaShop.
"""
