---
title: "Accesso al negozio per gruppi di clienti - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Accesso al negozio per gruppi di clienti' di MyPresta.eu."
sidebar:
  label: "Accesso al negozio per gruppi di clienti - Manuale del commerciante e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Access to shop by customer groups su MyPresta.eu](https://mypresta.eu/modules/front-office-features/access-to-shop-by-customer-groups.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/access-to-shop-by-customer-groups/)
>
> ---


# Accesso al negozio per gruppi di clienti

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e sono solitamente disponibili su qualsiasi ambiente di hosting moderno.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al nome del modulo per accedere alle sue impostazioni.

#### **Gruppi di clienti senza accesso al negozio**

Questa è l'impostazione più cruciale. Determina quali gruppi di clienti saranno bloccati dalla visualizzazione del tuo negozio.

- **Cosa fa questa impostazione:** Questa sezione visualizza un elenco di tutti i gruppi di clienti definiti nel tuo negozio PrestaShop. Puoi selezionare uno o più gruppi da questo elenco.
- **Effetto della modifica di questa impostazione:**
  - *Quando uno o più gruppi sono selezionati:* Qualsiasi cliente appartenente a *qualsiasi* dei gruppi selezionati sarà bloccato dall'accesso al front office del negozio. Vedrà invece il contenuto personalizzato che definisci di seguito.
  - *Quando nessun gruppo è selezionato:* Il modulo non bloccherà alcun cliente in base alla sua affiliazione di gruppo. Tutti i clienti avranno accesso al negozio (a meno che non abiliti l'opzione "Blocca l'accesso per i clienti non loggati").
- **Valore consigliato:** Seleziona i gruppi specifici che desideri limitare. Ad esempio, se hai un gruppo "Approvazione in sospeso all'ingrosso", potresti selezionarlo qui.
- **Scenario / esempio del commerciante:** Hai creato un nuovo gruppo di clienti chiamato "Nuove registrazioni - In revisione". Selezioni questo gruppo qui. Ora, qualsiasi nuovo cliente che si registra verrà automaticamente inserito in questo gruppo e non potrà navigare nel tuo negozio finché non lo sposterai manualmente in un gruppo "Clienti approvati".

#### **Blocca l'accesso per i clienti non loggati**

Questa impostazione controlla l'accesso per i visitatori che non sono loggati nel tuo negozio.

- **Cosa fa questa impostazione:** Questo è un semplice interruttore ON/OFF.
- **Effetto della modifica di questa impostazione:**
  - *Quando abilitato (SÌ):* Tutti i visitatori che non sono loggati in un account cliente saranno bloccati dall'accesso al negozio. Vedranno la pagina del contenuto personalizzato. Una volta effettuato l'accesso (e se appartengono a un gruppo consentito), otterranno l'accesso.
  - *Quando disabilitato (NO):* I visitatori non loggati avranno accesso al negozio, a meno che non siano esplicitamente bloccati appartenendo a un "Gruppi di clienti senza accesso al negozio".
- **Valore consigliato:**
  - **SÌ:** Se vuoi che il tuo intero negozio sia privato, richiedendo a tutti i visitatori di accedere prima (es. un negozio B2B, un club per soli membri).
  - **NO:** Se vuoi che il tuo negozio sia visibile pubblicamente, ma limiti solo gruppi di clienti specifici.
- **Scenario / esempio del commerciante:** Gestisci un negozio solo all'ingrosso. Abiliti questa impostazione. Ora, chiunque visiti il tuo sito deve prima accedere per vedere i tuoi prodotti e prezzi.

#### **Mostra modulo di accesso sulla pagina bloccata**

Questa impostazione determina se un modulo di accesso appare sulla pagina mostrata ai clienti bloccati.

- **Cosa fa questa impostazione:** Questo è un semplice interruttore ON/OFF.
- **Effetto della modifica di questa impostazione:**
  - *Quando abilitato (SÌ):* Un modulo di accesso standard di PrestaShop verrà visualizzato sulla pagina del contenuto personalizzato, consentendo ai clienti bloccati di tentare di accedere.
  - *Quando disabilitato (NO):* Non verrà mostrato alcun modulo di accesso. I clienti vedranno solo il tuo messaggio personalizzato.
- **Valore consigliato:**
  - **SÌ:** Se ti aspetti che i clienti bloccati siano clienti esistenti che devono semplicemente accedere per ottenere l'accesso. Questo migliora l'esperienza utente.
  - **NO:** Se vuoi forzare i clienti a registrarsi prima, o se la restrizione di accesso è permanente per alcuni gruppi.
- **Scenario / esempio del commerciante:** Hai bloccato l'accesso per gli utenti non loggati. Abilitando questa opzione, i clienti possono facilmente accedere direttamente dalla pagina con restrizioni senza dover navigare a una pagina di accesso separata.

#### **Consenti registrazione sulla pagina bloccata**

Questa impostazione determina se un link di registrazione appare sulla pagina mostrata ai clienti bloccati.

- **Cosa fa questa impostazione:** Questo è un semplice interruttore ON/OFF.
- **Effetto della modifica di questa impostazione:**
  - *Quando abilitato (SÌ):* Un link alla pagina di registrazione del cliente verrà visualizzato sulla pagina del contenuto personalizzato.
  - *Quando disabilitato (NO):* Non verrà mostrato alcun link di registrazione.
- **Valore consigliato:**
  - **SÌ:** Se vuoi consentire ai nuovi clienti di registrarsi dalla pagina con restrizioni.
  - **NO:** Se vuoi controllare la registrazione separatamente, o se il tuo negozio è strettamente per clienti pre-approvati.
- **Scenario / esempio del commerciante:** Gestisci un negozio B2B che richiede la registrazione. Abiliti questa impostazione in modo che i potenziali nuovi clienti possano facilmente registrarsi per un account direttamente dalla pagina con accesso limitato.

#### **Contenuti personalizzati da mostrare**

Qui è dove definisci il messaggio e il contenuto visualizzati ai clienti bloccati.

- **Cosa fa questa impostazione:** Questo è un editor di testo ricco (WYSIWYG) dove puoi inserire testo, immagini, HTML e persino video. Supporta contenuti multilingue, quindi puoi fornire messaggi diversi per le diverse lingue installate nel tuo negozio.
- **Effetto della modifica di questa impostazione:** Il contenuto che inserisci qui verrà visualizzato a qualsiasi cliente bloccato dall'accesso al tuo negozio.
- **Valore consigliato:** Fornisci un messaggio chiaro, cortese e informativo.
- **Scenario / esempio del commerciante:**
  - *Per un negozio B2B:* "Benvenuti nel nostro Portale all'ingrosso! Effettuate il login con le vostre credenziali o registratevi per un nuovo account per visualizzare il nostro catalogo prodotti."
  - *Per una restrizione temporanea:* "Il nostro negozio è attualmente in manutenzione. Torneremo online presto! Grazie per la vostra pazienza."
  - *Per accesso esclusivo:* "Questa sezione del nostro negozio è riservata ai membri VIP. Effettuate il login o contattate il supporto per l'accesso."

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | **Gruppi di clienti senza accesso al negozio** | Nessuno selezionato | Seleziona i gruppi da bloccare dalla visualizzazione del negozio. I clienti in questi gruppi vedono contenuti personalizzati. |
| Configurazione modulo | **Blocca l'accesso per i clienti non loggati** | NO | SÌ: Tutti i visitatori non loggati sono bloccati. NO: I visitatori non loggati hanno accesso (a meno che non siano in un gruppo bloccato). |
| Configurazione modulo | **Mostra modulo di accesso sulla pagina bloccata** | SÌ | SÌ: Visualizza un modulo di accesso sulla pagina con restrizioni. NO: Non viene mostrato alcun modulo di accesso. |
| Configurazione modulo | **Consenti registrazione sulla pagina bloccata** | SÌ | SÌ: Visualizza un link di registrazione sulla pagina con restrizioni. NO: Non viene mostrato alcun link di registrazione. |
| Configurazione modulo | **Contenuti personalizzati da mostrare** | Vuoto | Definisce il messaggio/contenuto HTML visualizzato ai clienti bloccati. Supporta più lingue. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Il mio negozio è completamente bloccato, anche per me! Cosa faccio?**
R1: Questo di solito accade se hai abilitato "Blocca l'accesso per i clienti non loggati" e non sei loggato, o se il tuo account amministratore è in qualche modo associato a un gruppo di clienti bloccato.
\* **Soluzione 1 (Consigliata):** Accedi al tuo Back Office di PrestaShop. Il modulo blocca solo il front office. Una volta loggato nel BO, naviga su Moduli > Gestione moduli, trova "Accesso al negozio per gruppi di clienti" e clicca su "Configura". Regola le impostazioni per consentire il tuo accesso.
\* **Soluzione 2 (Se non riesci ad accedere al BO):** Se sei completamente bloccato, potresti dover disabilitare temporaneamente il modulo via FTP. Vai su `modules/asg/` e rinomina il file `asg.php` (es. `asg.php.bak`). Questo disabiliterà il modulo. Quindi, puoi accedere al tuo BO e riabilitarlo/riconfigurarlo. Ricorda di rinominare il file in `asg.php` in seguito.

**D2: Il contenuto personalizzato sembra semplice o non corrisponde al mio tema.**
R2: L'area del contenuto personalizzato utilizza un template di base.
\* **Soluzione:** Puoi utilizzare l'editor di testo ricco per aggiungere HTML, CSS inline o immagini per stilizzare il tuo messaggio. Per uno stile più avanzato, un webmaster può modificare il file `custom.css` o il template `custom-contents.tpl` (vedi sezione sviluppatori). Assicurati che il tuo contenuto personalizzato sia ben formattato e reattivo.

**D3: Perché il modulo di accesso/registrazione non viene visualizzato?**
R3: Controlla la configurazione del modulo:
\* Assicurati che "Mostra modulo di accesso sulla pagina bloccata" sia impostato su SÌ.
\* Assicurati che "Consenti registrazione sulla pagina bloccata" sia impostato su SÌ.
\* Inoltre, assicurati che la registrazione del cliente sia generalmente abilitata nelle impostazioni di PrestaShop (Clienti > Impostazioni > Abilita creazione account).

**D4: Ho apportato modifiche, ma non appaiono nel front office.**
R4: PrestaShop utilizza la cache, che a volte può ritardare la visualizzazione delle modifiche.
\* **Soluzione:** Vai su **Parametri avanzati > Prestazioni** nel tuo Back Office di PrestaShop. Clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti). Questo dovrebbe aggiornare il tuo front office.

**D5: Come gestisco quali clienti sono in quali gruppi?**
R5: Gestisci i gruppi di clienti tramite l'interfaccia standard di PrestaShop:
\* Vai su **Clienti > Clienti** per modificare i singoli account cliente e assegnarli ai gruppi.
\* Vai su **Clienti > Gruppi** per creare nuovi gruppi o modificare quelli esistenti.
\* Ricorda che un cliente può appartenere a più gruppi. Se un cliente appartiene a *qualsiasi* gruppo che hai contrassegnato come "senza accesso", verrà bloccato.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Accesso al negozio per gruppi di clienti" (`asg`) opera principalmente agganciandosi all'evento `displayHeader`. Ciò gli consente di eseguire la sua logica molto presto nel processo di caricamento della pagina, prima che qualsiasi contenuto venga renderizzato. Se un cliente viene determinato come con restrizioni, il modulo prende il controllo, impedisce l'ulteriore rendering della pagina standard di PrestaShop e visualizza invece la sua pagina di accesso personalizzata. Sfrutta il sistema di configurazione di PrestaShop per le impostazioni e Smarty per la creazione di template.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller dedicati per il front-office o il back-office. Tutta la logica è incapsulata nel file principale del modulo (`asg.php`) ed eseguita tramite hook o il metodo `getContent()` per la configurazione.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non definisce classi personalizzate o entità `ObjectModel`. Interagisce direttamente con le classi core di PrestaShop `Customer`, `Group` e `Configuration`.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo non include alcun file JavaScript personalizzato.

### 4.5 Fogli di stile CSS (`views/css/`)

- **`asg/views/css/custom.css`**
  - **Scopo:** Stile del front-office per il cliente per la pagina di accesso con restrizioni.
  - **Componenti UI principali e contenitori che stilizza:** Questo file fornisce uno stile di base per il wrapper del contenuto personalizzato, il modulo di accesso e il link di registrazione sulla pagina di accesso con restrizioni. Assicura che il contenuto visualizzato sia centrato e leggibile.
  - **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere:**
    - `.asg_wrapper`: Il contenitore principale per l'intero contenuto con restrizioni.
    - `.asg_content`: Il div contenente il messaggio HTML personalizzato.
    - `.asg_login_form`: Il contenitore per il modulo di accesso.
    - `.asg_registration_link`: Il contenitore per il link di registrazione.
    - Elementi standard del modulo PrestaShop all'interno del modulo di accesso.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template hook (`views/templates/hook/`)**: Nessuno esplicitamente definito come template hook. Il modulo renderizza direttamente i template in base alla sua logica interna.
- **Template admin (`views/templates/admin/`)**:
  - **`asg/views/admin.tpl`**: Questo template viene renderizzato dal metodo `getContent()` in `asg.php`. Contiene la struttura HTML per il modulo di configurazione del modulo nel Back Office di PrestaShop. Include la selezione del gruppo di clienti, gli interruttori per l'accesso/registrazione e l'editor di testo ricco per il contenuto personalizzato.
- **Template front-office (`views/templates/front/`)**:
  - **`asg/views/custom-contents.tpl`**: Questo è il template principale renderizzato quando un cliente è bloccato. Visualizza il contenuto personalizzato definito nella configurazione del modulo. Include condizionalmente `login-form.tpl` e `registration-link.tpl` in base alle impostazioni del modulo.
  - **`asg/views/login-form.tpl`**: Questo template contiene l'HTML per il modulo di accesso standard del cliente PrestaShop. È incluso in `custom-contents.tpl` se l'opzione "Mostra modulo di accesso" è abilitata.
  - **`asg/views/registration-link.tpl`**: Questo template contiene l'HTML per il link alla pagina di registrazione del cliente. È incluso in `custom-contents.tpl` se l'opzione "Consenti registrazione" è abilitata.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Questo modulo non crea tabelle SQL personalizzate.
  - Memorizza le sue impostazioni di configurazione nella tabella `ps_configuration` (o `_configuration` a seconda del prefisso) utilizzando chiavi come:
    - `ASG_ALLOWREGAUTH`: Booleano per consentire la registrazione.
    - `ASG_SHOWLOGINFORM`: Booleano per mostrare il modulo di accesso.
    - `ASG_CCONTENTS`: Campo multilingue per il contenuto personalizzato (HTML).
    - `ASG_WHATTOSHOW`: Array serializzato di ID di gruppi di clienti bloccati.
    - `ASG_BLOCK_NOT_LOGGED`: Booleano per bloccare gli utenti non loggati.
- **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Eseguito molto presto nel caricamento della pagina del front-office, all'interno della sezione `<head>`. | Questo è l'hook principale utilizzato dal modulo. Controlla lo stato di accesso del cliente e l'affiliazione al gruppo. Se un cliente è con restrizioni, termina immediatamente il processo di rendering standard di PrestaShop e produce la pagina di accesso personalizzata (`custom-contents.tpl`). |
| `actionCustomerGroupsUpdate` | Eseguito quando i gruppi di clienti vengono aggiornati. | Utilizzato per svuotare la cache interna del modulo relativa ai gruppi di clienti, garantendo che le modifiche alle assegnazioni dei gruppi siano immediatamente riflesse. |
| `actionObjectCustomerAddAfter` | Eseguito dopo l'aggiunta di un nuovo cliente. | Utilizzato per svuotare la cache interna del modulo relativa ai gruppi di clienti, garantendo che i nuovi clienti siano correttamente valutati per l'accesso. |
| `actionObjectCustomerUpdateAfter` | Eseguito dopo l'aggiornamento di un cliente esistente. | Utilizzato per svuotare la cache interna del modulo relativa ai gruppi di clienti, garantendo che le modifiche alle assegnazioni dei gruppi di clienti siano immediatamente riflesse. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, correzioni di bug e supporto dedicato agli sviluppatori per il modulo "Accesso al negozio per gruppi di clienti", fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è impegnato a fornire assistenza tempestiva e a garantire la compatibilità del modulo con le ultime versioni di PrestaShop.
