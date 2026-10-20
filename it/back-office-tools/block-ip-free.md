---
title: "Block IP free - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Block IP free di MyPresta.eu."
sidebar:
  label: "Block IP free - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Block IP free su MyPresta.eu](https://mypresta.eu/modules/administration-tools/block-ip-free.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/block-ip-free/)
>
> ---


# Block IP free

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Nessun requisito speciale oltre a un ambiente di hosting PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Block IP free)

Questa è la schermata di configurazione principale e unica per il modulo "Block IP free". Qui troverai tutte le impostazioni per gestire i tuoi indirizzi IP bloccati e il messaggio visualizzato a essi.

**Nome schermata e posizione menu:**

- **Percorso menu:** Back Office > Moduli > Gestione moduli > Block IP free > Configura

#### Impostazioni e opzioni:

1. **Indirizzo IP (Campo di input)**

   - **Cosa fa questa impostazione:** Qui inserisci l'indirizzo IP che desideri bloccare dall'accesso al tuo negozio.
   - **Effetto della modifica di questa impostazione:**
     - *Quando un IP viene aggiunto all'elenco:* Qualsiasi visitatore che tenta di accedere al tuo negozio da questo specifico indirizzo IP vedrà l'accesso negato e gli verrà mostrato il "Messaggio di accesso bloccato".
     - *Quando un IP viene rimosso dall'elenco:* I visitatori da quell'indirizzo IP riacquisteranno pieno accesso al tuo negozio.
   - **Valore consigliato:** Inserisci l'indirizzo IP esatto che desideri bloccare. Puoi aggiungere più IP, uno alla volta, inserendoli e cliccando su "Aggiungi".
   - **Scenario / esempio per il commerciante:** Se noti che un indirizzo IP specifico (es. `192.168.1.100`) sta ripetutamente tentando ordini fraudolenti o estraendo i tuoi dati di prodotto, dovresti inserire `192.168.1.100` qui e cliccare su "Aggiungi" per bloccarlo.
2. **Messaggio di accesso bloccato (Area di testo)**

   - **Cosa fa questa impostazione:** Ti consente di personalizzare il messaggio che i visitatori bloccati vedranno quando tenteranno di accedere al tuo negozio.
   - **Effetto della modifica di questa impostazione:**
     - *Quando viene inserito un messaggio personalizzato:* I visitatori bloccati vedranno il tuo messaggio personalizzato invece di uno predefinito. Questo ti consente di essere cortese, informativo o fermo.
     - *Quando lasciato come predefinito:* Verrà mostrato un messaggio standard "Accesso negato".
   - **Valore consigliato:** Un messaggio chiaro e conciso. Qualcosa come: "L'accesso a questo negozio è stato bloccato dal tuo indirizzo IP. Se ritieni che si tratti di un errore, contatta il supporto."
   - **Scenario / esempio per il commerciante:** Potresti voler visualizzare un messaggio come "A causa di attività sospette, l'accesso dal tuo indirizzo IP è stato temporaneamente limitato. Contatta il nostro team di supporto se ritieni che si tratti di un errore." Questo offre una migliore esperienza utente rispetto a un errore generico.

#### Gestione dell'elenco IP bloccati:

Sotto il campo di input "Indirizzo IP", vedrai un elenco di tutti gli indirizzi IP attualmente bloccati.

- **Per aggiungere un IP:** Digita l'indirizzo IP nel campo "Indirizzo IP" e clicca sul pulsante "Aggiungi".
- **Per rimuovere un IP:** Accanto a ogni indirizzo IP elencato, ci sarà un pulsante "Elimina" (spesso rappresentato da un'icona a forma di cestino). Clicca su questo pulsante per sbloccare quell'IP specifico.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | Indirizzo IP | Vuoto (aggiungi IP secondo necessità) | Aggiunge/rimuove specifici indirizzi IP dall'elenco di blocco. Gli IP bloccati non possono accedere al negozio. |
| Pagina di configurazione del modulo | Messaggio di accesso bloccato | "Accesso negato" (o simile) | Personalizza il messaggio visualizzato ai visitatori provenienti da indirizzi IP bloccati. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D: Ho bloccato un IP, ma l'utente può ancora accedere al mio negozio. Perché?**
R:

1. **Caching:** Il tuo negozio PrestaShop o il server potrebbero avere la cache abilitata. Svuota la cache di PrestaShop (**Parametri avanzati > Prestazioni > Svuota la cache**) e qualsiasi cache lato server (come Varnish, LiteSpeed cache, Cloudflare) se applicabile.
2. **IP dinamico:** L'utente potrebbe avere un indirizzo IP dinamico che è cambiato da quando hai bloccato il precedente.
3. **Proxy/VPN:** L'utente potrebbe utilizzare una VPN o un server proxy, che maschera il suo vero indirizzo IP. Dovresti bloccare l'IP del server VPN/proxy se riesci a identificarlo.
4. **IP errato:** Ricontrolla di aver inserito l'indirizzo IP corretto.

**D: Ho accidentalmente bloccato il mio indirizzo IP e ora non riesco ad accedere al mio Back Office! Cosa faccio?**
R: Questa è una situazione critica ma risolvibile. Devi accedere direttamente al tuo server:

1. **Tramite FTP/SFTP:** Connettiti al server del tuo negozio utilizzando un client FTP (come FileZilla).
2. **Naviga nella cartella dei moduli:** Vai a `tua_root_prestashop/modules/`.
3. **Rinomina la cartella del modulo:** Trova la cartella `banipfree` e rinominala in qualcosa come `banipfree_DISABLED`. Questo disabiliterà efficacemente il modulo.
4. **Accedi al Back Office:** Ora dovresti essere in grado di accedere al tuo Back Office di PrestaShop.
5. **Riabilita e configura:** Rinomina la cartella in `banipfree`, quindi vai su **Moduli > Gestione moduli**, trova "Block IP free" e clicca su "Configura" per rimuovere il tuo IP dall'elenco bloccato.

**D: Posso bloccare un intervallo di indirizzi IP invece di uno solo?**
R: La versione attuale del modulo "Block IP free" consente di bloccare singoli indirizzi IP. Per bloccare interi intervalli (es. `192.168.1.0/24`), avresti tipicamente bisogno di una configurazione a livello di server (es. regole `.htaccess` o impostazioni del firewall) o di un modulo di sicurezza più avanzato.

**D: Questo modulo rallenterà il mio negozio?**
R: No, il modulo è molto leggero. Controlla l'indirizzo IP del visitatore molto presto nel processo di caricamento di PrestaShop. Se l'IP è bloccato, il contenuto del negozio non viene caricato affatto, il che può effettivamente risparmiare risorse del server impedendo al traffico indesiderato di elaborare completamente le richieste.

**D: Come trovo l'indirizzo IP di un visitatore problematico?**
R: Puoi trovare gli indirizzi IP in diversi posti:

- **Log di accesso al server:** Il pannello di controllo del tuo hosting web (cPanel, Plesk) di solito fornisce l'accesso ai log di accesso grezzi, che elencano l'indirizzo IP di ogni visitatore.
- **Dettagli ordine PrestaShop:** Per gli ordini, l'indirizzo IP del cliente è solitamente registrato nella pagina dei dettagli dell'ordine nel Back Office.
- **Strumenti di analisi:** Alcuni strumenti di analisi avanzati potrebbero mostrare gli indirizzi IP dei visitatori, anche se spesso anonimizzati.
- **Moduli di sicurezza di terze parti:** Altri moduli di sicurezza potrebbero registrare attività sospette con gli indirizzi IP.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster che lavorano con il modulo "Block IP free".

### 4.1 Panoramica dell'architettura

Il modulo "Block IP free" è un semplice modulo PrestaShop a file singolo (`banipfree.php`) che sfrutta principalmente l'hook `actionDispatcher`. Questo hook viene eseguito molto presto nel ciclo di vita della richiesta di PrestaShop, consentendo al modulo di controllare l'indirizzo IP del visitatore prima che avvenga qualsiasi elaborazione o rendering significativo del contenuto del negozio. Se l'IP viene trovato nell'elenco bloccato, il modulo termina immediatamente la richiesta e visualizza un messaggio personalizzato, agendo efficacemente come un firewall di primo livello. La configurazione è gestita tramite il metodo standard `getContent()`, memorizzando le impostazioni in `ps_configuration`.

### 4.2 Controller (`controllers/`)

- Questo modulo **non** contiene alcun controller Front-Office o Back-Office personalizzato. Tutta la logica è incapsulata all'interno del file principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

- Questo modulo **non** contiene classi personalizzate o definizioni di `ObjectModel` nella directory `classes/`. Tutta la gestione dei dati è diretta tramite `Configuration::get()` e `Configuration::updateValue()`.

### 4.4 Risorse JavaScript (`views/js/`)

- Questo modulo **non** contiene alcun file JavaScript personalizzato.

### 4.5 Fogli di stile CSS (`views/css/`)

- Questo modulo **non** contiene alcun file CSS personalizzato. Il messaggio di accesso bloccato viene visualizzato con uno stile minimo, in linea o con lo stile predefinito del browser.

### 4.6 Struttura del template Smarty (`views/templates/`)

- Questo modulo **non** contiene alcun file di template Smarty personalizzato. Il messaggio di accesso bloccato viene generato direttamente come HTML/testo grezzo all'interno del metodo `hookActionDispatcher`.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

Il modulo non crea tabelle di database personalizzate. Memorizza le sue impostazioni di configurazione nella tabella standard `ps_configuration`:

- `BANIPFREE_LIST`: Memorizza una stringa separata da virgole di indirizzi IP bloccati.
- `BANIPFREE_MSG`: Memorizza il messaggio personalizzato visualizzato agli utenti bloccati.
- `mypresta_updates`, `update_`, `updatev_`: Chiavi interne utilizzate da MyPresta.eu per i controlli di aggiornamento del modulo.

#### Tabella degli hook registrati

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionDispatcher` | Eseguito molto presto nel ciclo di vita della richiesta di PrestaShop, prima del dispatch del controller. | Questo è l'hook principale utilizzato dal modulo. Recupera l'indirizzo IP del visitatore, lo confronta con la `BANIPFREE_LIST` e, se viene trovata una corrispondenza, restituisce la `BANIPFREE_MSG` e termina l'esecuzione dello script (`die()`), impedendo un ulteriore caricamento del negozio. |

### 4.8 File principale del modulo (`banipfree/banipfree.php`)

Questo è il cuore del modulo.

- **`__construct()`**: Inizializza i metadati del modulo (nome, tab, versione, autore, ecc.).
- **`install()`**:
  - Chiama `parent::install()`.
  - Registra l'hook `actionDispatcher`.
  - Imposta i valori di configurazione iniziali per `BANIPFREE_LIST` (vuoto) e `BANIPFREE_MSG` (messaggio predefinito).
- **`uninstall()`**:
  - Chiama `parent::uninstall()`.
  - Deregistra l'hook `actionDispatcher`.
  - Elimina i valori di configurazione (`BANIPFREE_LIST`, `BANIPFREE_MSG`).
- **`getContent()`**:
  - Gestisce l'invio del modulo per il salvataggio degli indirizzi IP e del messaggio personalizzato.
  - Recupera e visualizza l'elenco corrente degli IP bloccati.
  - Renderizza il modulo di configurazione utilizzando elementi standard `HelperForm` di PrestaShop (input di testo per IP, textarea per messaggio, elenco per IP bloccati con pulsanti di eliminazione).
- **`hookActionDispatcher()`**:
  - Questo è il metodo critico per il blocco.
  - Recupera l'indirizzo IP del visitatore (`$_SERVER['REMOTE_ADDR']`).
  - Recupera la `BANIPFREE_LIST` dalla `Configuration`.
  - Controlla se l'IP corrente è presente nell'elenco separato da virgole.
  - Se l'IP è bloccato, recupera `BANIPFREE_MSG`, restituisce una semplice pagina HTML con il messaggio e chiama `die()` per interrompere l'ulteriore esecuzione.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Block IP free", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità del modulo.
