---
title: "Valore massimo di acquisto per categorie - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Valore massimo di acquisto per categorie' di MyPresta.eu."
sidebar:
  label: "Valore massimo di acquisto per categorie - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Maximum purchase value by categories su MyPresta.eu](https://mypresta.eu/modules/ordering-process/maximum-purchase-value-by-categories.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/maximum-purchase-value-by-categories/)
>
> ---


# Valore massimo di acquisto per categorie

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Nessun requisito di hosting speciale oltre a una configurazione PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale del modulo, dove gestisci le impostazioni generali e accedi alle regole per i valori massimi di acquisto.

- **Cosa fa questa impostazione:** Questa pagina fornisce informazioni generali sul modulo e spesso include un link o un pulsante per gestire le regole effettive.
- **Effetto della modifica di questa impostazione:** Sebbene questa schermata specifica potrebbe non avere "impostazioni" dirette da modificare, serve come punto di ingresso alla funzionalità del modulo.
- **Valore consigliato:** N/A (Questa è una schermata informativa).
- **Scenario / esempio del commerciante:** Dopo l'installazione, atterrerai qui. Quindi cliccherai un pulsante o un link (es. "Gestisci regole" o "Configura valori massimi") per procedere alla schermata dedicata dove definisci i limiti delle tue categorie.

### 2.2 Schermata di amministrazione dedicata: Regole del valore massimo di acquisto (Back Office > Moduli > Valore massimo di acquisto per categorie > Configura)

Questo è il cuore del modulo dove definisci e gestisci le tue regole di valore massimo di acquisto per diverse categorie. Tipicamente troverai questa schermata cliccando su "Configura" dopo aver installato il modulo, o navigando su **Moduli > Gestione moduli**, trovando il modulo e cliccando su "Configura".

**Nome schermata e posizione nel menu:**
Accederai a questa schermata navigando su **Moduli > Gestione moduli**, cercando "Valore massimo di acquisto per categorie" e cliccando sul pulsante "Configura". Questo ti porterà a un'interfaccia di amministrazione dedicata per la gestione delle tue regole.

**Azioni e impostazioni disponibili:**
Su questa schermata, vedrai un elenco (griglia) di tutte le tue regole di valore massimo di acquisto attualmente definite. Per ogni regola, tipicamente vedrai:

- **Nome categoria:** Il nome della categoria di prodotti a cui si applica la regola.
- **Valore massimo:** Il valore totale più alto (nella tua valuta predefinita) consentito per i prodotti di questa categoria in un singolo ordine.
- **Azioni:** Pulsanti per "Modifica" una regola esistente o "Elimina" essa.

Troverai anche:

- **Pulsante "Aggiungi nuova regola":** Un pulsante prominente per creare una nuova regola di valore massimo di acquisto.

**Quando aggiungi o modifichi una regola, tipicamente incontrerai i seguenti campi:**

1. **Seleziona categoria:**

   - **Cosa fa questa impostazione:** Ti consente di scegliere a quale specifica categoria di prodotti si applicherà questa regola di valore massimo di acquisto. Di solito vedrai un menu a discesa o un selettore ad albero di categorie.
   - **Effetto della modifica di questa impostazione:**
     - *Quando una categoria è selezionata:* La regola si applicherà a tutti i prodotti all'interno di quella categoria (e spesso alle sue sottocategorie, a seconda della logica del modulo).
     - *Quando nessuna categoria è selezionata (o se la modifichi):* La regola sarà non valida o si applicherà a una categoria diversa.
   - **Valore consigliato:** Seleziona la categoria specifica che desideri limitare.
   - **Scenario / esempio del commerciante:** Vuoi limitare gli acquisti di prodotti "Elettronica". Selezioneresti "Elettronica" dall'elenco.
2. **Valore massimo di acquisto:**

   - **Cosa fa questa impostazione:** Questo è il valore numerico (nella valuta predefinita del tuo negozio) che rappresenta il totale più alto consentito per i prodotti della categoria selezionata nel carrello di un cliente.
   - **Effetto della modifica di questa impostazione:**
     - *Quando impostato su un valore specifico (es. 500):* I clienti non potranno avere più di 500 unità della valuta predefinita del tuo negozio di prodotti della categoria selezionata nel loro carrello.
     - *Quando impostato su 0 o lasciato vuoto (se consentito):* Questo potrebbe disabilitare la regola per la categoria o essere considerato un'immissione non valida.
   - **Valore consigliato:** Un valore numerico positivo che rappresenta il limite desiderato (es. `250.00`).
   - **Scenario / esempio del commerciante:** Vuoi limitare le "Stampe d'arte in edizione limitata" a un massimo di $250 per ordine. Inseriresti `250` qui. Il modulo calcolerà automaticamente i valori equivalenti per altre valute se il tuo negozio le supporta.

**Effetto delle modifiche:**

- **Aggiunta di una nuova regola:** Applica immediatamente il valore massimo di acquisto per la categoria selezionata in tutto il tuo negozio. Ai clienti sarà impedito di superare questo limite.
- **Modifica di una regola:** Aggiorna il valore massimo per una categoria esistente. Il nuovo limite ha effetto immediatamente.
- **Eliminazione di una regola:** Rimuove la restrizione per quella categoria. I clienti non saranno più limitati nei loro acquisti da quella categoria.

**Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

1. Rivedi periodicamente le tue categorie di prodotti e identifica quelle che potrebbero beneficiare di un limite di valore di acquisto (es. nuovi prodotti ad alta domanda, articoli con scorte limitate o prodotti con accordi di distribuzione specifici).
2. Naviga alla schermata di configurazione "Valore massimo di acquisto per categorie".
3. Utilizza il pulsante "Aggiungi nuova regola" per creare nuovi limiti.
4. Monitora il feedback dei clienti o i modelli di ordine per regolare i limiti esistenti secondo necessità utilizzando l'azione "Modifica".
5. Se una linea di prodotti o una categoria non richiede più un limite, utilizza l'azione "Elimina" per rimuovere la regola.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| AdminMaobcController (Gestione regole) | **Seleziona categoria** | Nome categoria specifico | Definisce a quale categoria di prodotti si applica il valore massimo. |
| AdminMaobcController (Gestione regole) | **Valore massimo di acquisto** | Valore numerico (es. `250.00`) | Imposta il valore totale più alto consentito per i prodotti della categoria selezionata in un singolo ordine (nella valuta predefinita). Converte automaticamente per altre valute. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho impostato un limite, ma i clienti possono ancora superarlo. Cosa c'è che non va?**
R1:

- **Verifica l'assegnazione della categoria:** Assicurati che i prodotti in questione siano correttamente assegnati alla categoria per la quale hai impostato il limite.
- **Modulo abilitato:** Verifica che il modulo "Valore massimo di acquisto per categorie" sia abilitato in **Moduli > Gestione moduli**.
- **Regola attiva:** Vai alla configurazione del modulo e conferma che la regola per la categoria specifica sia presente e abbia un valore massimo valido.
- **Svuota cache:** A volte la cache di PrestaShop può impedire che le modifiche abbiano effetto immediatamente. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache".

**D2: Il modulo mostra la valuta sbagliata o non converte correttamente.**
R2: Il modulo utilizza automaticamente la valuta predefinita del tuo negozio per il valore che inserisci e poi la converte per altre valute.

- **Valuta predefinita:** Assicurati che la tua valuta predefinita sia impostata correttamente in **Internazionale > Valute**. Il valore che inserisci nella configurazione del modulo dovrebbe essere sempre in questa valuta predefinita.
- **Tassi di cambio:** Controlla i tuoi tassi di cambio in **Internazionale > Valute** per assicurarti che siano aggiornati e accurati per le valute che supporti.

**D3: Posso impostare limiti diversi per diversi gruppi di clienti?**
R3: Questo modulo specifico imposta un limite globale per categoria, applicabile a tutti i clienti. Se hai bisogno di limiti diversi per gruppi di clienti specifici (es. all'ingrosso vs. al dettaglio), avresti bisogno di un modulo più avanzato o di uno sviluppo personalizzato.

**D4: Come traduco i messaggi di errore mostrati ai clienti?**
R4: I messaggi del front-office del modulo sono solitamente traducibili tramite il sistema di traduzione di PrestaShop:

1. Vai su **Internazionale > Traduzioni**.
2. Seleziona "Traduzioni dei moduli installati".
3. Scegli il tuo tema, la lingua e poi seleziona "Valore massimo di acquisto per categorie" dall'elenco dei moduli.
4. Potrai quindi trovare e modificare le stringhe di testo visualizzate dal modulo ai tuoi clienti.

**D5: Il modulo sembra essere in conflitto con un altro modulo nel mio carrello/checkout.**
R5: I conflitti tra moduli possono talvolta verificarsi.

- **Isola il problema:** Disabilita temporaneamente altri moduli che interagiscono con il carrello o la pagina del prodotto uno per uno per vedere se il conflitto si risolve.
- **Compatibilità del tema:** Se stai utilizzando un tema personalizzato, potrebbe avere override specifici che interferiscono. Verifica se il problema persiste con il tema PrestaShop predefinito.
- **Contatta il supporto:** Se non riesci a identificare il conflitto, raccogli i dettagli (quali moduli, quale errore esatto) e contatta il supporto MyPresta.eu per assistenza.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Valore massimo di acquisto per categorie" (`maobc`) segue un modello MVC (Model-View-Controller) standard di PrestaShop. Utilizza principalmente un Controller Admin per gestire la configurazione e le regole, e un Controller Front per intercettare le richieste AJAX relative agli aggiornamenti del carrello. La logica principale risiede all'interno della classe principale del modulo, che si aggancia a vari eventi di PrestaShop per applicare i limiti di valore basati sulla categoria. Memorizza la sua configurazione nella tabella `ps_configuration` e gestisce le sue regole tramite una tabella personalizzata e un Controller Admin.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**:

  - `controllers/front/ajax.php`
    - **Nome classe**: `MaobcAjaxModuleFrontController` (estende `ModuleFrontController`)
    - **Responsabilità**: Questo controller è responsabile della gestione delle richieste AJAX dal front-office, principalmente quelle relative all'aggiunta di prodotti al carrello o all'aggiornamento delle quantità del carrello. Intercetta queste richieste per eseguire la convalida in tempo reale rispetto alle regole di valore massimo di acquisto definite prima che PrestaShop elabori l'aggiornamento del carrello. Restituisce risposte JSON che indicano successo o fallimento con messaggi appropriati.
  - `controllers/front/index.php`
    - **Nome classe**: `MaobcIndexModuleFrontController` (estende `ModuleFrontController`)
    - **Responsabilità**: Questo controller potrebbe servire come fallback o un semplice punto di ingresso, ma data la funzionalità del modulo, `ajax.php` è il punto di interazione principale del front-office. Potrebbe renderizzare una semplice pagina o reindirizzare se acceduto direttamente.
- **Controller Admin Back-Office**:

  - `controllers/admin/AdminMaobc.php`
    - **Nome classe**: `AdminMaobcController` (estende `ModuleAdminController`)
    - **Nome scheda**: "Valore massimo di acquisto per categorie" (o simile, accessibile tramite il pulsante "Configura" del modulo).
    - **Entità gestita**: Questo controller gestisce l'entità `maobc` personalizzata, che rappresenta le singole regole per i valori massimi di acquisto per categoria. Gestisce le operazioni CRUD (Create, Read, Update, Delete) per queste regole.
    - **Responsabilità**: Visualizza un elenco (griglia) di tutte le regole configurate, consente agli amministratori di aggiungere nuove regole, modificare quelle esistenti (selezionando una categoria e impostando un valore massimo) ed eliminare le regole. Interagisce con l'archiviazione dati interna del modulo (probabilmente una tabella di database personalizzata o voci `ps_configuration`).
  - `controllers/admin/index.php`
    - **Nome classe**: `AdminMaobcIndexController` (estende `ModuleAdminController`)
    - **Responsabilità**: Simile a `index.php` del front-office, questo potrebbe essere un semplice punto di ingresso o un fallback. `AdminMaobcController` è il controller principale per la gestione delle regole del modulo.

### 4.3 Classi e modelli principali (`classes/`)

Il dossier del modulo non indica classi personalizzate nella directory `classes/`. Ciò suggerisce che la logica principale del modulo e la gestione dei dati sono probabilmente integrate direttamente nel file principale del modulo (`maobc/index.php`) o gestite tramite la classe `Configuration` standard di PrestaShop per le impostazioni e potenzialmente una tabella di database personalizzata gestita direttamente da `AdminMaobcController` senza un `ObjectModel` dedicato.

### 4.4 Risorse JavaScript (`views/js/`)

- `views/js/maobc.js`
  - **Ambito**: Front-office.
  - **Dettagli**: Questo script è probabilmente responsabile delle interazioni lato client relative agli aggiornamenti del carrello. Potrebbe:
    - Sovrascrivere o estendere le funzioni predefinite del carrello AJAX di PrestaShop (es. clic sui pulsanti `aggiungi al carrello`).
    - Intercettare le risposte AJAX da `controllers/front/ajax.php` per visualizzare messaggi di errore personalizzati all'utente se un valore massimo viene superato.
    - Potenzialmente aggiornare l'interfaccia utente (es. disabilitare pulsanti, mostrare avvisi) in base ai risultati della convalida.
    - Probabilmente utilizzerà `jQuery` o eventi `prestashop.on` per associare la sua logica.

### 4.5 Fogli di stile CSS (`views/css/`)

- `views/css/maobc.css`
  - **Ambito**: Front-office.
  - **Dettagli**: Questo foglio di stile fornisce una stilizzazione personalizzata per gli elementi del front-office del modulo, principalmente i messaggi di notifica visualizzati ai clienti quando viene superato un valore massimo di acquisto.
  - **Selettori di classi CSS chiave**: Gli sviluppatori dovrebbero ispezionare questo file per classi come `.maobc-error-message`, `.maobc-alert` o simili, che possono essere sovrascritte nel `custom.css` o `theme.css` del loro tema per adattarsi al branding del negozio.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template hook (`views/templates/hook/`)**:

  - Il dossier del modulo non elenca esplicitamente i template in `views/templates/hook/`. Ciò suggerisce che eventuali messaggi o contenuti dinamici potrebbero essere iniettati direttamente tramite JavaScript o renderizzati dal file principale del modulo utilizzando i metodi `display()`.
- **Template admin (`views/templates/admin/`)**:

  - Il dossier del modulo non elenca esplicitamente i template in `views/templates/admin/`. L'`AdminMaobcController` probabilmente utilizza i moduli helper standard di PrestaShop (`HelperList`, `HelperForm`) per la sua griglia e i moduli di configurazione, che generano il loro HTML dinamicamente.
- **Template front-office (`views/templates/front/`)**:

  - `views/templates/front/displayShoppingCart.tpl`
    - **Scopo**: Questo template è probabilmente utilizzato per visualizzare il messaggio di errore personalizzato nella pagina del carrello se il valore massimo di acquisto per una categoria viene superato. Contiene la struttura HTML per l'avviso o la notifica che informa il cliente sul limite. È probabilmente agganciato a un `displayShoppingCartFooter` o un hook simile.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Il modulo probabilmente crea una tabella di database personalizzata (es. `ps_maobc_rules`) per memorizzare l'ID della categoria e il valore massimo di acquisto associato per ogni regola.
  - I valori di configurazione (es. stato abilitato del modulo, impostazioni generali) sono memorizzati nella tabella `ps_configuration`, tipicamente con chiavi prefissate `MAOBC_`.
- **Tabella degli hook registrati**:

| Nome hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Renderizza nella sezione `<head>` di tutte le pagine del front-office. | Potenzialmente utilizzato per caricare le risorse `maobc.js` e `maobc.css`, o per iniettare variabili JavaScript. |
| `displayRightColumn` / `displayLeftColumn` | Renderizza il contenuto nelle colonne laterali. | Meno probabile per questo modulo, ma potrebbe essere utilizzato per visualizzare un messaggio statico sui limiti di acquisto. |
| `displayProductAdditionalInfo` / `displayProductButtons` | Renderizza nella pagina del prodotto. | Potrebbe essere utilizzato per visualizzare un messaggio di avviso nella pagina del prodotto se l'articolo appartiene a una categoria con restrizioni. |
| `displayShoppingCartFooter` / `displayShoppingCart` | Renderizza nella pagina del carrello. | Utilizzato per visualizzare il template `displayShoppingCart.tpl` con messaggi di errore se i limiti vengono superati. |
| `actionCartSave` | Eseguito dopo il salvataggio di un carrello (es. prodotto aggiunto/rimosso, quantità modificata). | Cruciale per la convalida lato server del contenuto del carrello rispetto ai limiti di categoria. Qui la logica principale impedisce stati del carrello non validi. |
| `actionAjaxDieCartController` | Eseguito prima di una risposta AJAX dal CartController. | Consente al modulo di intercettare e modificare le risposte AJAX, iniettando messaggi di errore personalizzati se i limiti vengono superati durante gli aggiornamenti del carrello AJAX. |
| `actionFrontControllerSetMedia` | Eseguito prima che un controller frontale renderizzi il suo output. | Utilizzato per registrare file CSS e JavaScript del front-office. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e per scaricare le ultime versioni del modulo "Valore massimo di acquisto per categorie", accedi al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità o all'integrazione del modulo.
