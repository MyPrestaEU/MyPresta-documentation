---
title: "Happy Birthday Coupon - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Happy Birthday Coupon di MyPresta.eu."
sidebar:
  label: "Happy Birthday Coupon - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Happy Birthday Coupon su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/happy-birthday-coupon.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/happy-birthday-coupon/)
>
> ---


# Happy Birthday Coupon

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono generalmente sufficienti. Assicurati che la funzionalità cron job del tuo server sia abilitata per l'invio automatico dei coupon.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Happy Birthday Coupon)

Questa è la schermata di configurazione principale dove definisci come verranno generati e inviati i tuoi coupon di compleanno.

#### Impostazioni Generali

- **Giorni prima del compleanno del cliente per inviare il coupon (bp\_daysbefore)**

  - **Cosa fa questa impostazione:** Determina quanti giorni *prima* del compleanno effettivo di un cliente verrà inviata l'email del coupon.
  - **Effetto della modifica di questa impostazione:**
    - *Se impostato a 0:* Il coupon verrà inviato il giorno del compleanno del cliente.
    - *Se impostato a 7:* Il coupon verrà inviato 7 giorni prima del compleanno del cliente. Questo gli dà una settimana per pianificare un acquisto.
  - **Valore consigliato:** `7` giorni. Questo fornisce ai clienti tempo sufficiente per navigare nel tuo negozio e prendere una decisione di acquisto, piuttosto che riceverlo il giorno stesso quando potrebbero essere occupati.
  - **Scenario / esempio per il commerciante:** Vuoi che i clienti ricevano il loro regalo di compleanno con una settimana di anticipo in modo che abbiano tempo per usarlo per un acquisto speciale di compleanno. Impostando questo a `7` si assicura che ricevano l'email con ampio tempo.
- **Abilita opzione newsletter (bpro\_nletter)**

  - **Cosa fa questa impostazione:** Controlla se la funzionalità del coupon di compleanno è legata allo stato di iscrizione alla newsletter del cliente.
  - **Effetto della modifica di questa impostazione:**
    - *Se abilitato (SÌ):* Solo i clienti iscritti alla tua newsletter riceveranno un coupon di compleanno.
    - *Se disabilitato (NO):* Tutti i clienti con una data di nascita valida nel loro account riceveranno un coupon di compleanno, indipendentemente dalla loro iscrizione alla newsletter.
  - **Valore consigliato:** `NO`. Per massimizzare l'impatto e la portata, è generalmente meglio inviare coupon di compleanno a tutti i clienti con una data di nascita, poiché è un gesto personale. Tuttavia, se vuoi premiare specificamente gli iscritti alla newsletter, impostalo su `SÌ`.
  - **Scenario / esempio per il commerciante:** Vuoi premiare tutti i tuoi clienti fedeli per il loro compleanno, non solo quelli iscritti alla tua newsletter. Imposteresti questo su `NO`.
- **Gruppi di clienti da includere (birthdaypro\_groups)**

  - **Cosa fa questa impostazione:** Ti consente di selezionare specifici gruppi di clienti idonei a ricevere coupon di compleanno.
  - **Effetto della modifica di questa impostazione:**
    - *Quando vengono selezionati gruppi specifici:* Solo i clienti appartenenti a questi gruppi scelti riceveranno coupon di compleanno.
    - *Quando non vengono selezionati gruppi (o tutti sono selezionati):* Tutti i clienti (soggetti ad altre impostazioni come l'opzione newsletter) saranno idonei.
  - **Valore consigliato:** Seleziona `Cliente` e qualsiasi altro gruppo che desideri includere. Evita di selezionare `Visitatore` o `Ospite` poiché di solito non hanno account con date di nascita.
  - **Scenario / esempio per il commerciante:** Hai un gruppo "Clienti VIP" e un gruppo "Grossisti". Vuoi inviare coupon di compleanno solo al tuo gruppo "Cliente" regolare e ai "Clienti VIP", ma non ai tuoi partner all'ingrosso. Selezioneresti "Cliente" e "Clienti VIP" dall'elenco.
- **Elenco dei clienti (Informativo)**

  - **Cosa fa questa impostazione:** Questa non è un'impostazione da modificare, ma una sezione informativa che probabilmente visualizza un elenco di clienti che hanno ricevuto o sono idonei per i coupon di compleanno. Ti aiuta a monitorare l'attività del modulo.
  - **Effetto della modifica di questa impostazione:** Nessun effetto diretto in quanto è una funzione di sola visualizzazione.
  - **Valore consigliato:** N/A
  - **Scenario / esempio per il commerciante:** Vuoi vedere rapidamente quali clienti hanno date di nascita registrate e potrebbero ricevere coupon a breve.

#### Impostazioni Voucher (Personalizzazione Avanzata)

Il modulo consente un'ampia personalizzazione dei voucher generati. Queste impostazioni rispecchiano le opzioni standard delle regole del carrello (voucher) di PrestaShop.

- **Prefisso codice voucher:** (es. `BIRTHDAY-`)

  - **Cosa fa questa impostazione:** Definisce un prefisso per tutti i codici coupon di compleanno generati.
  - **Effetto della modifica di questa impostazione:** Tutti i codici unici inizieranno con questo prefisso, rendendoli facilmente identificabili.
  - **Valore consigliato:** `BIRTHDAY-` o `BDP-`.
  - **Scenario / esempio per il commerciante:** Vuoi distinguere facilmente i coupon di compleanno da altre promozioni nella cronologia degli ordini.
- **Tipo di sconto:** (es. Percentuale, Importo, Spedizione gratuita)

  - **Cosa fa questa impostazione:** Determina il tipo di sconto fornito dal coupon.
  - **Effetto della modifica di questa impostazione:**
    - *Percentuale:* Applica uno sconto percentuale all'ordine.
    - *Importo:* Applica uno sconto monetario fisso.
    - *Spedizione gratuita:* Offre la spedizione gratuita.
  - **Valore consigliato:** `Percentuale` o `Importo`, a seconda della tua strategia di marketing.
  - **Scenario / esempio per il commerciante:** Vuoi offrire uno sconto del 15% per i compleanni. Selezioneresti `Percentuale` e imposteresti il valore a `15`.
- **Valore sconto:** (es. `15` per percentuale, `10.00` per importo)

  - **Cosa fa questa impostazione:** Il valore effettivo dello sconto.
  - **Effetto della modifica di questa impostazione:** Influisce direttamente sullo sconto applicato all'ordine del cliente.
  - **Valore consigliato:** Un valore che sia attraente ma anche redditizio per il tuo negozio (es. `10` per 10% o `5.00` per 5€).
  - **Scenario / esempio per il commerciante:** Seguendo l'esempio precedente, qui inseriresti `15`.
- **Importo minimo:**

  - **Cosa fa questa impostazione:** Imposta un importo minimo di acquisto richiesto affinché il coupon sia valido.
  - **Effetto della modifica di questa impostazione:** Incoraggia i clienti a spendere di più per qualificarsi per lo sconto.
  - **Valore consigliato:** Un importo ragionevole che incoraggi l'upselling senza essere proibitivo.
  - **Scenario / esempio per il commerciante:** Vuoi che i clienti spendano almeno 50€ per utilizzare il loro coupon di compleanno. Imposteresti questo a `50.00`.
- **Periodo di validità:** (es. `30` giorni)

  - **Cosa fa questa impostazione:** Definisce quanti giorni il coupon è valido dalla data di invio.
  - **Effetto della modifica di questa impostazione:** Crea urgenza per il cliente di utilizzare il coupon.
  - **Valore consigliato:** `30` giorni. Questo offre ai clienti una buona finestra per utilizzare il loro regalo senza sentirsi affrettati.
  - **Scenario / esempio per il commerciante:** Vuoi che i clienti utilizzino il loro coupon di compleanno entro un mese dalla ricezione. Imposteresti questo a `30`.
- **Applica a prodotti/categorie specifici:**

  - **Cosa fa questa impostazione:** Ti consente di limitare l'uso del coupon a determinati prodotti o categorie.
  - **Effetto della modifica di questa impostazione:** Può essere utilizzato per promuovere articoli specifici o liquidare vecchie scorte.
  - **Valore consigliato:** Lascia vuoto a meno che tu non abbia un obiettivo promozionale specifico.
  - **Scenario / esempio per il commerciante:** Vuoi che il coupon di compleanno sia valido solo per gli articoli nella tua categoria "Nuovi Arrivi".
- **Altre opzioni voucher:** (es. cumulabile con altri voucher, prodotti regalo, ecc.)

  - **Cosa fa questa impostazione:** Il modulo probabilmente espone altre opzioni avanzate delle regole del carrello di PrestaShop, come se il voucher possa essere combinato con altri sconti, se si applica a specifici corrieri o se offre un regalo gratuito.
  - **Effetto della modifica di questa impostazione:** Ti offre un controllo granulare sul comportamento e sulle restrizioni del voucher.
  - **Valore consigliato:** Configura in base alla tua specifica strategia promozionale. Fai attenzione alla cumulabilità per evitare sconti eccessivi.
  - **Scenario / esempio per il commerciante:** Vuoi assicurarti che il coupon di compleanno non possa essere combinato con altre promozioni in corso. Disabiliteresti l'opzione "Cumulabile con altri voucher".

#### Impostazioni del modello email

- **Oggetto email:** (es. `Buon Compleanno da {shop_name}! Ecco un regalo per te!`)

  - **Cosa fa questa impostazione:** Definisce l'oggetto dell'email di compleanno.
  - **Effetto della modifica di questa impostazione:** Questa è la prima cosa che i clienti vedono; un oggetto accattivante aumenta i tassi di apertura.
  - **Valore consigliato:** Qualcosa di caldo, personale e che indichi chiaramente un regalo. Usa `{shop_name}` e `{customer_firstname}` se disponibili.
  - **Scenario / esempio per il commerciante:** Vuoi una riga dell'oggetto accattivante che faccia sentire speciali i clienti.
- **Contenuto email:** (editor HTML)

  - **Cosa fa questa impostazione:** Ti consente di personalizzare il contenuto completo dell'email di compleanno.
  - **Effetto della modifica di questa impostazione:** Qui è dove trasmetti i tuoi auguri di compleanno, spieghi lo sconto e incoraggi lo shopping.
  - **Valore consigliato:** Includi un saluto caloroso, indica chiaramente il codice sconto e il suo valore, spiega come usarlo e aggiungi una call to action. Usa segnaposto come `{customer_firstname}`, `{voucher_code}`, `{shop_name}`, `{shop_url}`.
  - **Scenario / esempio per il commerciante:** Vuoi scrivere un messaggio sentito, includere il logo del tuo brand e mostrare chiaramente il codice sconto.

#### Informazioni sul Cron Job

- **URL Cron Job:** (es. `http://tuonegozio.com/modules/birthdaypro/controllers/front/cron.php?token=TUO_TOKEN_SICURO`)
  - **Cosa fa questa impostazione:** Visualizza l'URL che devi impostare come cron job sul tuo server. Questo cron job è essenziale affinché il modulo controlli automaticamente i compleanni imminenti e invii i coupon.
  - **Effetto della modifica di questa impostazione:** Questa non è un'impostazione da modificare, ma un'istruzione. Se il cron job non è impostato correttamente, nessun coupon di compleanno verrà inviato automaticamente.
  - **Valore consigliato:** Imposta un cron job per eseguire questo URL una volta ogni 24 ore (es. ogni giorno a mezzanotte).
  - **Scenario / esempio per il commerciante:** Hai configurato tutte le impostazioni, ma non vengono inviate email. La prima cosa da controllare è se il tuo provider di hosting ha impostato correttamente il cron job utilizzando questo URL.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Giorni prima del compleanno del cliente per inviare il coupon | `7` | Invia il coupon X giorni prima del compleanno, incoraggiando acquisti pianificati. |
| Configurazione modulo | Abilita opzione newsletter | `NO` | Determina se solo gli iscritti alla newsletter ricevono coupon. `NO` per una portata più ampia. |
| Configurazione modulo | Gruppi di clienti da includere | `Cliente` (e altri se necessario) | Limita l'invio di coupon a specifici segmenti di clienti. |
| Configurazione modulo | Prefisso codice voucher | `BIRTHDAY-` | Aggiunge un prefisso unico ai codici coupon generati per una facile identificazione. |
| Configurazione modulo | Tipo di sconto | `Percentuale` o `Importo` | Definisce la natura dello sconto (es. 15% di sconto, 10€ di sconto). |
| Configurazione modulo | Valore sconto | `10` (per 10%) o `5.00` (per 5€) | Il valore effettivo dello sconto. |
| Configurazione modulo | Importo minimo | (Vuoto o valore specifico) | Imposta un valore minimo dell'ordine affinché il coupon sia valido. |
| Configurazione modulo | Periodo di validità | `30` giorni | Quanto tempo il coupon è valido dalla data di invio, creando urgenza. |
| Configurazione modulo | Applica a prodotti/categorie specifici | (Vuoto o selezione specifica) | Limita l'uso del coupon a determinati prodotti o categorie. |
| Configurazione modulo | Altre opzioni voucher | (Secondo la strategia) | Controllo granulare sul comportamento del voucher (es. cumulabilità). |
| Configurazione modulo | Oggetto email | `Buon Compleanno da {shop_name}!` | L'oggetto dell'email di compleanno. |
| Configurazione modulo | Contenuto email | (HTML personalizzato) | Il corpo dell'email di compleanno, inclusi saluti e dettagli del coupon. |
| Configurazione modulo | URL Cron Job | (URL visualizzato) | Essenziale per i controlli giornalieri automatizzati e l'invio di coupon. Deve essere impostato sul server. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei clienti non ricevono le email di compleanno. Cosa devo controllare per primo?**
R1:

1. **Cron Job:** La ragione più comune. Assicurati che l'URL del cron job fornito nella configurazione del modulo sia correttamente impostato sul tuo server di hosting per essere eseguito quotidianamente. Senza di esso, il modulo non può inviare automaticamente le email.
2. **Date di nascita dei clienti:** Verifica che i tuoi clienti abbiano effettivamente le loro date di nascita inserite nei loro account PrestaShop. Il modulo si basa su questi dati.
3. **Configurazione email:** Controlla le impostazioni email di PrestaShop (Parametri avanzati > E-mail) per assicurarti che il tuo negozio possa inviare email con successo. Prova a inviare un'email generale da PrestaShop.
4. **Cartelle spam:** Consiglia ai clienti di controllare le loro cartelle spam o posta indesiderata.
5. **Impostazioni del modulo:** Ricontrolla "Giorni prima del compleanno del cliente", "Abilita opzione newsletter" e "Gruppi di clienti da includere" per assicurarti che i clienti siano idonei.

**D2: Il codice sconto non funziona per i miei clienti.**
R2:

1. **Validità del voucher:** Controlla l'impostazione "Periodo di validità" nel modulo. Il coupon è scaduto?
2. **Importo minimo:** Il carrello del cliente soddisfa il requisito di "Importo minimo" impostato per il voucher?
3. **Restrizioni prodotto/categoria:** Se hai applicato restrizioni, il cliente sta cercando di acquistare un prodotto idoneo?
4. **Cumulabile con altri voucher:** Se hai disabilitato questa opzione, assicurati che il cliente non stia cercando di combinarlo con un altro sconto.
5. **Errori di battitura:** Chiedi al cliente di ricontrollare eventuali errori di battitura quando inserisce il codice.

**D3: Come posso cambiare l'aspetto dell'email di compleanno?**
R3: Puoi personalizzare completamente il contenuto dell'email utilizzando l'editor HTML nell'impostazione "Contenuto email" nella pagina di configurazione del modulo. Puoi aggiungere il tuo logo, cambiare font, colori e layout. Assicurati di utilizzare i segnaposto disponibili (come `{customer_firstname}`, `{voucher_code}`, `{shop_name}`) per personalizzare il messaggio.

**D4: Posso inviare diversi coupon di compleanno a diversi gruppi di clienti?**
R4: Il modulo Happy Birthday Coupon, nella sua configurazione standard, invia un solo tipo di coupon basato sulle impostazioni che definisci. Per inviare coupon diversi a gruppi diversi (es. uno sconto del 10% per i clienti regolari e uno sconto del 20% per i VIP), dovresti:
a) Creare e inviare manualmente voucher separati per gruppi specifici (vanificando l'automazione).
b) Utilizzare le "Regole del carrello" native di PrestaShop per gruppi specifici e gestirle manualmente.
c) Considerare una personalizzazione avanzata o una soluzione di automazione del marketing più complessa se questo è un requisito critico.

**D5: Il modulo sembra funzionare, ma non vedo alcuna prova di coupon generati nella sezione "Regole del carrello" di PrestaShop.**
R5: Il modulo genera regole del carrello (voucher) uniche dinamicamente quando si avvicina il compleanno di un cliente. Queste sono vere e proprie regole del carrello di PrestaShop. Dovresti essere in grado di vederle in **Catalogo > Sconti > Regole del carrello** (o **Regole prezzo > Regole del carrello** nelle versioni precedenti). Cerca le regole con il prefisso che hai definito (es. `BIRTHDAY-`). Se non appaiono, ricontrolla la configurazione del tuo cron job e del modulo.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster che lavorano con il modulo Happy Birthday Coupon.

### 4.1 Panoramica dell'architettura

Il modulo Happy Birthday Coupon (`birthdaypro`) segue un'architettura standard dei moduli PrestaShop, sfruttando `Module` come base. Funziona principalmente tramite un cron job che attiva un controller frontale per identificare i clienti idonei e generare oggetti `CartRule` di PrestaShop. Il modulo non estende `ObjectModel` per i propri dati, ma si basa sui dati esistenti dei clienti PrestaShop e sulla funzionalità `CartRule`. Utilizza un motore di voucher personalizzato e uno strumento di ricerca con autocompletamento, probabilmente per la selezione dei clienti nel back-office o per i test.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

Questi controller sono progettati per essere accessibili esternamente, principalmente tramite cron job.

- **`controllers/front/cron.php`**

  - **Nome classe e classe genitore:** `BirthdayproCronModuleFrontController` che estende `ModuleFrontController`.
  - **Responsabilità:** Questa è la logica principale per la generazione e l'invio automatico dei coupon. È progettata per essere richiamata da un cron job lato server.
    - Recupera le date di nascita dei clienti.
    - Determina quali clienti sono idonei in base alla configurazione `bp_daysbefore`, `bpro_nletter` e `birthdaypro_groups`.
    - Per ogni cliente idoneo, genera una `CartRule` (voucher) unica di PrestaShop con i parametri configurati.
    - Invia un'email di compleanno contenente il codice del voucher al cliente.
    - Include un controllo del token di sicurezza per prevenire accessi non autorizzati.
- **`controllers/front/index.php`**

  - **Nome classe e classe genitore:** `BirthdayproIndexModuleFrontController` che estende `ModuleFrontController`.
  - **Responsabilità:** Questo controller probabilmente funge da segnaposto o da semplice punto di ingresso, possibilmente per test o per gestire richieste che non corrispondono ad altri controller frontali specifici. In molti moduli, un `index.php` in una directory di controller è un fallback o un controller di tipo "hello world" di base. Potrebbe non avere una logica di business significativa.

#### Controller Admin Back-Office

Il modulo non sembra avere controller Admin personalizzati dedicati in base all'inventario fornito. Tutta la configurazione del back-office è gestita all'interno del metodo `getContent()` del modulo principale.

### 4.3 Classi e Modelli Core (`classes/`)

L'inventario fornito indica l'assenza di classi o modelli personalizzati nella directory `classes/`. Il modulo probabilmente sfrutta direttamente le classi native di PrestaShop `Customer`, `CartRule` e `Mail`. Il "voucherengine" e il "searchTool" menzionati nei percorsi JS/CSS suggeriscono classi o funzioni helper interne all'interno di `birthdaypro.php` o delle sue librerie incluse, piuttosto che file `classes/` autonomi.

### 4.4 Risorse JavaScript (`views/js/`)

- **`lib/searchTool/views/js/autocomplete.js`**

  - **Ambito:** Probabilmente Back-office.
  - **Dettagli:** Questo script fornisce la funzionalità di autocompletamento, probabilmente per la ricerca di clienti o prodotti all'interno della configurazione del modulo o di un'interfaccia amministrativa correlata. Si legherebbe ai campi di input, effettuerebbe richieste AJAX a un endpoint backend (possibilmente il file del modulo principale o un controller admin dedicato se esistente) e visualizzerebbe suggerimenti.
- **`lib/voucherengine/script.js`**

  - **Ambito:** Probabilmente Back-office.
  - **Dettagli:** Questo script fa parte del "motore voucher" del modulo. Probabilmente gestisce elementi dinamici del modulo relativi alla creazione di voucher all'interno della pagina di configurazione del modulo. Ciò potrebbe includere la visualizzazione/nascondimento di campi in base alla selezione del tipo di sconto, la convalida dell'input per i valori dei voucher o l'interazione con altre impostazioni relative ai voucher.

### 4.5 Fogli di stile CSS (`views/css/`)

- **`lib/searchTool/views/css/autocomplete.css`**

  - **Ambito:** Probabilmente Back-office.
  - **Dettagli:** Fornisce lo stile per il menu a discesa dei suggerimenti di autocompletamento e possibilmente per il campo di input stesso, garantendo che si integri visivamente con il back office di PrestaShop.
- **`lib/voucherengine/ps16.css`**

  - **Ambito:** Probabilmente Back-office.
  - **Dettagli:** Questo foglio di stile fornisce uno stile specifico per gli elementi di configurazione del voucher, potenzialmente mirato all'estetica del back office di PrestaShop 1.6. Potrebbe includere stili per gruppi di moduli, campi di input ed etichette relative alle impostazioni del voucher.
- **`views/css/css.css`**

  - **Ambito:** Probabilmente Back-office.
  - **Dettagli:** Un foglio di stile generale per il modulo, che potenzialmente contiene stili per la pagina di configurazione principale (`admin.tpl`) o qualsiasi elemento personalizzato introdotto dal modulo nel back office. Potrebbe includere layout di base, pulsanti o stili di avviso.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **`lib/searchTool/views/scripts.tpl`**

  - **Ambito:** Back-office.
  - **Dettagli:** Questo template probabilmente include codice JavaScript o variabili Smarty necessarie per il corretto funzionamento dello script `autocomplete.js`, come URL AJAX, stringhe di lingua o dati iniziali. Sarebbe incluso nel template di configurazione admin principale.
- **`views/templates/admin.tpl`**

  - **Ambito:** Back-office.
  - **Dettagli:** Questo è il template principale per la pagina di configurazione del modulo, renderizzato dal metodo `getContent()` in `birthdaypro.php`. Contiene la struttura HTML per tutte le impostazioni descritte nella Sezione 4.1, inclusi campi modulo, pulsanti e potenzialmente inclusioni per altri template come `scripts.tpl`.
- **`views/templates/script.tpl`**

  - **Ambito:** Back-office.
  - **Dettagli:** Simile a `scripts.tpl` nella libreria `searchTool`, questo template probabilmente contiene JavaScript o variabili Smarty specifiche del modulo che vengono iniettate nella pagina di configurazione del back-office. Potrebbe gestire il comportamento dinamico o il passaggio di dati per il motore dei voucher.
- **`views/templates/test.tpl`**

  - **Ambito:** Back-office o test interni.
  - **Dettagli:** Lo scopo di questo template è meno chiaro dal solo nome. Potrebbe essere un template utilizzato per test interni durante lo sviluppo, un template di output di debug o un semplice segnaposto. È improbabile che faccia parte della configurazione standard rivolta al commerciante.

### 4.7 Schema del database e Mappa degli hook

- **Tabelle del database**:

  - Il modulo non crea tabelle di database personalizzate in base all'inventario fornito.
  - Memorizza le sue impostazioni di configurazione (es. `bp_daysbefore`, `bpro_nletter`, `birthdaypro_groups`) nella tabella `ps_configuration` di PrestaShop.
  - Interagisce con le tabelle esistenti di PrestaShop: `ps_customer` (per le date di nascita), `ps_cart_rule` (per la creazione di voucher), `ps_cart_rule_lang`, `ps_cart_rule_shop`, `ps_cart_rule_product_rule_group`, ecc.
- **Tabella degli hook registrati**:

| Nome Hook | Tempistica / Contesto di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Tipicamente usato per aggiungere CSS, JS o meta tag. La descrizione del modulo lo menziona, ma la sua funzione principale è basata su cron, quindi questo hook potrebbe essere usato per una configurazione front-end minima o non attivamente usato per la funzionalità principale. |
| `displayRightColumn` | Nella colonna destra delle pagine del front-office. | Visualizza il contenuto nella barra laterale destra. Improbabile che venga usato da questo modulo data la sua operazione in background. |
| `displayLeftColumn` | Nella colonna sinistra delle pagine del front-office. | Visualizza il contenuto nella barra laterale sinistra. Improbabile che venga usato da questo modulo data la sua operazione in background. |
| `displayFooter` | Nella sezione del piè di pagina di ogni pagina del front-office. | Visualizza il contenuto nel piè di pagina. Improbabile che venga usato da questo modulo data la sua operazione in background. |
| `displayProductButtons` / `displayProductExtraContent` (o hook di prodotto simili) | Sulla pagina del prodotto. | Improbabile che venga usato da questo modulo. |
| `actionValidateOrder` | Dopo che un ordine è stato convalidato con successo. | Potrebbe essere usato per tracciare l'utilizzo del coupon o il comportamento del cliente dopo l'applicazione di un coupon di compleanno, anche se non esplicitamente elencato come funzione principale. |
| `actionCustomerAccountAdd` / `actionCustomerAccountUpdate` | Quando un account cliente viene creato o aggiornato. | Potrebbe essere usato per controllare l'inserimento della data di nascita o attivare la configurazione iniziale per i nuovi clienti, anche se il cron job è il trigger principale. |
| (Implicito) Esecuzione Cron Job | Quotidianamente, tramite cron esterno al server. | **CRITICO:** Questo è l'"hook" principale per la funzionalità core del modulo, che attiva `controllers/front/cron.php` per elaborare i compleanni e inviare le email. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo Happy Birthday Coupon, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team è dedicato a garantire che il vostro modulo funzioni in modo ottimale e vi aiuti a raggiungere i vostri obiettivi di e-commerce.
"""
