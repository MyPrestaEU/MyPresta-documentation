---
title: "Valore massimo di acquisto per produttore - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Valore massimo di acquisto per produttore di MyPresta.eu."
sidebar:
  label: "Valore massimo di acquisto per produttore - Manuale del commerciante e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Maximum purchase value by manufacturer su MyPresta.eu](https://mypresta.eu/modules/ordering-process/maximum-purchase-value-by-manufacturer.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/maximum-purchase-value-by-manufacturer/)
>
> ---


# Valore massimo di acquisto per produttore

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono generalmente sufficienti. Di solito non sono necessarie configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale dove puoi abilitare o disabilitare il modulo e accedere all'area di gestione dedicata per impostare i limiti del produttore.

- **Cosa fa questa impostazione:** Questa sezione contiene tipicamente un semplice interruttore per abilitare o disabilitare la funzionalità principale del modulo. Fornisce anche un link diretto alla schermata dedicata dove si definiscono i valori massimi di acquisto effettivi per i produttori.
- **Effetto della modifica di questa impostazione:**
  - *Quando abilitato:* Il modulo controllerà attivamente i carrelli dei clienti rispetto ai limiti del produttore definiti e impedirà gli ordini se i limiti vengono superati.
  - *Quando disabilitato:* Il modulo cesserà di funzionare e non verranno applicati limiti di acquisto per i produttori.
- **Valore consigliato:** "SÌ" (Abilitato) se intendi utilizzare le funzionalità del modulo.
- **Scenario / esempio del commerciante:** Hai appena installato il modulo e vuoi iniziare a impostare i limiti. Lo abiliteresti qui, quindi procederesti alla sezione "Gestisci limiti produttore".

### 2.2 Schermata di amministrazione dedicata: Limiti produttore (Back Office > Moduli > Valore massimo di acquisto per produttore > Configura > pulsante "Gestisci limiti produttore" o una voce di menu dedicata)

Questa schermata è dove definisci e gestisci i valori massimi di acquisto effettivi per ciascun produttore. Tipicamente presenterà un elenco dei tuoi produttori e ti consentirà di aggiungere, modificare o eliminare regole.

**Nome schermata e posizione nel menu:**
Accederai a questa schermata cliccando sul pulsante "Configura" accanto al modulo in Gestione moduli, e quindi probabilmente cliccando un pulsante prominente come "Gestisci limiti produttore" o "Aggiungi nuova regola". In alternativa, il modulo potrebbe creare una nuova voce di menu sotto "Catalogo" o "Parametri negozio" per l'accesso diretto a `AdminMaobm`.

**Azioni e impostazioni disponibili:**

1. **Tabella di elenco delle regole esistenti:**

   - Vedrai una tabella che elenca tutti i limiti del produttore che hai già impostato.
   - Le colonne tipicamente includono: Nome produttore, Valore massimo e azioni come "Modifica" o "Elimina".
   - **Effetto delle modifiche:** Questa tabella fornisce una panoramica delle tue regole attive. L'eliminazione di una regola rimuoverà il limite di acquisto per quel produttore specifico.
   - **Flusso di lavoro consigliato:** Rivedi regolarmente questa tabella per assicurarti che i tuoi limiti siano aggiornati con le tue esigenze aziendali.
2. **Modulo Aggiungi nuovo / Modifica regola:**

   - Quando clicchi su "Aggiungi nuovo" o "Modifica" una regola esistente, vedrai tipicamente un modulo con i seguenti campi:
     - **Produttore:** Un elenco a discesa o una casella di ricerca per selezionare il produttore a cui vuoi applicare il limite.
       - **Cosa fa questa impostazione:** Specifica a quale produttore si applica questa regola.
       - **Effetto della modifica di questa impostazione:** La regola si applicherà solo ai prodotti associati al produttore selezionato.
       - **Valore consigliato:** Seleziona il produttore specifico che desideri limitare.
       - **Scenario / esempio del commerciante:** Vuoi impostare un limite per i prodotti "Acme Corp.", quindi selezioni "Acme Corp." dall'elenco.
     - **Valore massimo di acquisto:** Un campo di input in cui inserisci il valore totale massimo (nella valuta predefinita del tuo negozio) che un cliente può acquistare dal produttore selezionato in un singolo ordine.
       - **Cosa fa questa impostazione:** Definisce il tetto monetario per i prodotti del produttore scelto.
       - **Effetto della modifica di questa impostazione:** Se il valore totale dei prodotti di questo produttore nel carrello di un cliente supera questo numero, gli verrà impedito di ordinare.
       - **Valore consigliato:** Un valore numerico che rappresenta il totale massimo consentito, ad esempio, "500.00" per 500 unità della tua valuta predefinita.
       - **Scenario / esempio del commerciante:** Vuoi limitare i prodotti "Acme Corp." a un massimo di $500 per ordine. Inseriresti "500" qui.
     - **Pulsante Salva:** Per applicare le modifiche.
       - **Effetto delle modifiche:** Salva la nuova regola o aggiorna una esistente nel database, rendendola attiva immediatamente.

**Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

- **Configurazione iniziale:** Esamina l'elenco dei tuoi produttori e identifica quelli per i quali devi impostare limiti di acquisto. Aggiungi una nuova regola per ciascuno.
- **Monitoraggio:** Tieni d'occhio le tue vendite e il tuo inventario. Se noti che i prodotti di un produttore vengono acquistati in quantità eccessive, o se gli accordi con i fornitori cambiano, torna a questa schermata per regolare o aggiungere nuovi limiti.
- **Aggiornamenti:** Quando vengono aggiunti nuovi produttori al tuo negozio, considera se richiedono una regola di limite di acquisto.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | Stato del modulo (Abilita/Disabilita) | Abilitato | Attiva o disattiva la funzionalità del modulo. |
| AdminMaobmController (Limiti produttore) | Produttore | Seleziona dall'elenco | Specifica il produttore a cui si applica il limite. |
| AdminMaobmController (Limiti produttore) | Valore massimo di acquisto | Il tuo limite monetario desiderato (es. 500.00) | Imposta il valore totale massimo per i prodotti del produttore selezionato in un singolo ordine. Il superamento di questo blocca il checkout. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Un cliente sta cercando di effettuare il checkout, ma vede un messaggio che indica il superamento di un limite del produttore. Cosa devo fare?**
R: Ciò significa che il modulo funziona come previsto. Il cliente ha troppi articoli di un produttore specifico nel carrello e il valore totale di tali articoli supera il limite impostato. Puoi:
1. Consigliare al cliente di ridurre la quantità di articoli di quel produttore.
2. Disabilitare temporaneamente o regolare il limite per quel produttore nella configurazione del modulo se ritieni che l'ordine sia accettabile (ma sii cauto).

**D: Ho impostato un limite, ma non sembra funzionare. I clienti possono ancora ordinare più del massimo.**
R:
1. **Controlla lo stato del modulo:** Assicurati che il modulo sia abilitato in **Moduli > Gestione moduli** e nella sua pagina di configurazione principale.
2. **Verifica la regola:** Ricontrolla la regola che hai creato nella schermata "Gestisci limiti produttore". È stato selezionato il produttore corretto? Il "Valore massimo di acquisto" è impostato correttamente?
3. **Svuota la cache:** A volte la cache di PrestaShop può impedire che le modifiche abbiano effetto immediatamente. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache".
4. **Produttore del prodotto:** Assicurati che i prodotti in questione siano correttamente assegnati al produttore per il quale hai impostato il limite. Controlla le impostazioni del prodotto nel tuo catalogo.

**D: Posso impostare limiti diversi per diversi gruppi di clienti?**
R: Questo modulo, nella sua forma standard, applica un singolo limite per produttore a tutti i clienti. Se hai bisogno di limiti specifici per gruppo di clienti, ciò richiederebbe uno sviluppo personalizzato.

**D: Il messaggio di avviso non è chiaro o non corrisponde alla lingua/tema del mio negozio.**
R:
1. **Traduzioni:** Vai su **Internazionale > Traduzioni**, seleziona "Traduzioni dei moduli installati", il tuo tema e il modulo "Valore massimo di acquisto per produttore". Puoi personalizzare il testo del messaggio di avviso lì.
2. **Stile del tema:** Il modulo utilizza lo stile standard di PrestaShop per i suoi messaggi. Se sembra fuori luogo, il tuo tema potrebbe avere CSS personalizzati che necessitano di aggiustamenti. Un webmaster può ispezionare il file `maobm.css` e il CSS del tuo tema per renderlo visivamente coerente.

**D: Cosa succede se a un prodotto non è assegnato alcun produttore?**
R: I prodotti senza un produttore assegnato non saranno soggetti ad alcun limite impostato da questo modulo, poiché le regole sono specifiche del produttore.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Valore massimo di acquisto per produttore" (`maobm`) segue un'architettura standard per i moduli PrestaShop. Utilizza principalmente una classe `Module` per l'installazione e la configurazione di base, un `AdminController` per la gestione dei limiti del produttore e `FrontController` per gestire le richieste AJAX e integrarsi con il processo del carrello del front-office. Il modulo sfrutta il sistema di hook di PrestaShop per iniettare la sua logica nel flusso del carrello e del checkout, impedendo gli ordini se i limiti vengono superati. Memorizza la sua configurazione in `ps_configuration` e gestisce i limiti specifici del produttore tramite una tabella di database dedicata (sebbene non sia esplicitamente elencato alcun `ObjectModel`, implica un'interazione diretta con il DB o un semplice `AdminController` che gestisce la configurazione).

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**:

  - `controllers/front/ajax.php`
    - **Nome classe**: `MaobmAjaxModuleFrontController` (implicito, estende `ModuleFrontController`)
    - **Responsabilità**: Questo controller probabilmente gestisce le richieste AJAX dal front-office, ad esempio quando un cliente aggiorna il carrello. Rivaluterebbe i limiti del produttore e restituirebbe una risposta (ad esempio, un messaggio di avviso o uno stato che indica se l'ordine può procedere). Potrebbe essere agganciato a `actionCartSave` o eventi simili per fornire feedback in tempo reale.
  - `controllers/front/index.php`
    - **Nome classe**: `MaobmIndexModuleFrontController` (implicito, estende `ModuleFrontController`)
    - **Responsabilità**: Questo controller potrebbe fungere da fallback o da semplice punto di ingresso, sebbene la sua funzione principale potrebbe essere minima se `ajax.php` gestisce la maggior parte delle interazioni front-end. Potrebbe potenzialmente visualizzare un messaggio generico o reindirizzare se acceduto direttamente.
- **Controller Admin Back-Office**:

  - `controllers/admin/AdminMaobm.php`
    - **Nome classe**: `AdminMaobmController` (estende `ModuleAdminController`)
    - **Nome scheda**: Probabilmente una scheda personalizzata creata dal modulo, o accessibile tramite la pagina di configurazione del modulo.
    - **Entità gestita**: Gestisce le regole specifiche di limite del produttore. Fornisce l'interfaccia per elencare, aggiungere, modificare ed eliminare queste regole. Questo controller interagirebbe direttamente con il database per archiviare e recuperare gli ID dei produttori e i loro valori massimi associati. Tipicamente utilizzerebbe `HelperList` per la tabella di riepilogo e `HelperForm` per il modulo di aggiunta/modifica.
  - `controllers/admin/index.php`
    - **Nome classe**: `AdminMaobmIndexController` (implicito, estende `ModuleAdminController`)
    - **Responsabilità**: Simile a `index.php` del front-office, questo potrebbe essere un segnaposto o un semplice reindirizzamento. In PrestaShop, i file `index.php` nelle directory dei controller spesso fungono da misure di sicurezza per prevenire l'elenco diretto delle directory.

### 4.3 Classi e modelli principali (`classes/`)

L'inventario fornito non indica classi personalizzate nella directory `classes/`. Ciò suggerisce che il modulo:

1. Manipola direttamente le tabelle del database (ad esempio, `ps_maobm_limits`) utilizzando `Db::getInstance()` nei suoi controller o nel file principale del modulo.
2. Memorizza tutta la configurazione in `ps_configuration` utilizzando `Configuration::updateValue()`, con `AdminMaobmController` che gestisce queste voci di configurazione.
   Data la funzionalità di "numero illimitato di regole", l'interazione diretta con il DB per una tabella personalizzata è più probabile rispetto a `ps_configuration` per l'archiviazione di più limiti del produttore.

### 4.4 Risorse JavaScript (`views/js/`)

- `views/js/maobm.js`
  - **Ambito**: Probabilmente Front-office.
  - **Dettagli**: Questo script sarebbe responsabile delle interazioni lato client relative alla funzionalità del modulo. Potrebbe:
    - Associare listener di eventi alle azioni di aggiornamento del carrello (ad esempio, modifiche della quantità, rimozione del prodotto).
    - Effettuare chiamate AJAX a `controllers/front/ajax.php` per rivalutare i limiti del produttore in tempo reale senza un ricaricamento completo della pagina.
    - Visualizzare messaggi di avviso o disabilitare il pulsante di checkout se i limiti vengono superati, in base alla risposta AJAX.
    - Potenzialmente integrarsi con gli eventi `prestashop.on` di PrestaShop per una migliore compatibilità.

### 4.5 Fogli di stile CSS (`views/css/`)

- `views/css/maobm.css`
  - **Ambito**: Principalmente Front-office, eventualmente alcuni stili Back-office per elementi personalizzati.
  - **Dettagli**: Questo foglio di stile conterrebbe le regole CSS necessarie per stilizzare i messaggi di avviso visualizzati al cliente nel carrello o nel processo di checkout. Potrebbe definire classi per:
    - `#maobm-warning-message` o contenitori simili per il testo di errore.
    - Stile per i pulsanti di checkout disabilitati.
    - Garantire la reattività su diverse dimensioni dello schermo.
  - **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere**: Cerca classi come `.maobm-alert`, `.maobm-error-message` o ID specifici utilizzati per il contenitore di avviso.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template hook (`views/templates/hook/`)**:

  - `views/templates/front/displayShoppingCart.tpl`
    - **Hook**: Questo template è probabilmente renderizzato in un hook che appare nella pagina del carrello, come `displayShoppingCartFooter` o `displayShoppingCart`.
    - **Output**: Sarebbe responsabile della visualizzazione del messaggio di avviso al cliente se supera il limite di acquisto di un produttore. Riceverebbe variabili dal modulo che indicano se un limite è stato superato e il messaggio pertinente da mostrare.
- **Template admin (`views/templates/admin/`)**: (Non esplicitamente elencato, ma implicito da `AdminMaobmController`)

  - L'`AdminMaobmController` utilizzerebbe tipicamente i template `HelperList` e `HelperForm` di PrestaShop per la sua interfaccia, ma potrebbe avere file `.tpl` personalizzati per parti specifiche della sua configurazione o per visualizzare un elenco di regole. Questi si troverebbero solitamente in `views/templates/admin/maobm/` o simili.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - `ps_maobm_limits` (Implicito): Una tabella personalizzata per memorizzare i limiti del produttore.
    - `id_maobm_limit` (Chiave primaria, AUTO_INCREMENT)
    - `id_manufacturer` (Chiave esterna a `ps_manufacturer.id_manufacturer`)
    - `max_value` (Decimale o Float, che memorizza il valore massimo di acquisto consentito)
    - `date_add`, `date_upd` (Timestamp standard di PrestaShop)
  - `ps_configuration`: Il modulo potrebbe memorizzare impostazioni generali (come lo stato abilitato/disabilitato del modulo) qui.
- **Tabella degli hook registrati**:

| Nome hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Renderizza nella sezione `<head>` di tutte le pagine del front-office. | Per includere le risorse `maobm.css` e `maobm.js`. |
| `displayShoppingCart` o `displayShoppingCartFooter` | Renderizza il contenuto nella pagina del carrello. | Per visualizzare il messaggio di avviso (`displayShoppingCart.tpl`) se i limiti vengono superati. |
| `actionCartSave` | Eseguito dopo che un carrello viene salvato o aggiornato. | Per rivalutare i limiti del produttore e potenzialmente aggiornare lo stato del carrello o visualizzare messaggi. |
| `actionValidateOrder` | Eseguito prima che un ordine venga ufficialmente convalidato. | **CRITICO**: Per eseguire un controllo finale sui limiti del produttore e impedire la convalida dell'ordine se i limiti vengono superati. Qui risiederebbe la logica di blocco dell'ordine. |
| `displayAdminProductsExtra` (o simile) | Potrebbe essere utilizzato per visualizzare le informazioni sul limite del produttore direttamente nella pagina di modifica del prodotto nel BO. | (Opzionale) Per fornire un accesso rapido alle informazioni sul limite per il produttore del prodotto. |
| `displayBackOfficeHeader` | Renderizza nella sezione `<head>` di tutte le pagine del back-office. | Per includere CSS/JS specifici del back-office per `AdminMaobmController`. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Valore massimo di acquisto per produttore", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e alla configurazione del modulo.
