---
title: "Voucher per amico - Manuale del commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Voucher per amico di MyPresta.eu."
sidebar:
  label: "Voucher per amico - Manuale del commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Voucher for friend su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/voucher-for-friend.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/voucher-for-friend/)
>
> ---


# Voucher per amico

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per un negozio PrestaShop e sono sufficienti per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Voucher per amico)

Questa è la schermata di configurazione principale per il modulo "Voucher per amico". Qui definirai come si comporta la funzione di condivisione del voucher e dove appare nel tuo negozio.

#### **Impostazioni e opzioni**

- **Visualizza il link "Voucher per amico" nel blocco Il mio account (fvc\_b\_position)**

  - **Cosa fa questa impostazione:** Controlla se un link alla pagina "Voucher per amico" appare nel blocco "Il mio account" del cliente, che si trova tipicamente nell'intestazione o in una colonna dopo che un cliente ha effettuato l'accesso.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (Sì):* Un link, solitamente etichettato "I miei voucher" o "Voucher per un amico", sarà visibile nel blocco account cliente, fornendo un accesso rapido alla funzione di condivisione.
    - *Quando disabilitato (No):* Il link non apparirà nel blocco account cliente. I clienti dovrebbero navigare alla loro pagina completa "Il mio account" per trovare il link, o utilizzare un'altra opzione di posizionamento.
  - **Valore consigliato:** SÌ
  - **Scenario / esempio del commerciante:** Se vuoi rendere super facile per i clienti loggati trovare la funzione, abilitala. È un posizionamento prominente per gli utenti attivi.
- **Visualizza il link "Voucher per amico" nella pagina Il mio account (fvc\_b\_position2)**

  - **Cosa fa questa impostazione:** Determina se un link alla pagina "Voucher per amico" viene mostrato nella pagina principale "Il mio account", che elenca tutte le opzioni specifiche del cliente.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (Sì):* Un link dedicato apparirà nella pagina "Il mio account", solitamente come icona o link di testo insieme ad altre opzioni come "Cronologia ordini" o "I miei indirizzi".
    - *Quando disabilitato (No):* Il link non sarà presente nella pagina "Il mio account".
  - **Valore consigliato:** SÌ
  - **Scenario / esempio del commerciante:** Questo è un luogo standard e atteso per i clienti per trovare una tale funzione. Abilitarlo garantisce la scopribilità per tutti gli utenti loggati.
- **Visualizza il link "Voucher per amico" nella colonna sinistra/destra (fvc\_b\_position3)**

  - **Cosa fa questa impostazione:** Controlla se un blocco promozionale o un link per "Voucher per amico" appare nelle colonne sinistra o destra del tuo negozio. Questo può essere visibile sia ai visitatori loggati che a quelli non loggati.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (Sì):* Un blocco o un link verrà renderizzato nella colonna specificata, incoraggiando i visitatori a utilizzare o conoscere la funzione di condivisione del voucher.
    - *Quando disabilitato (No):* Nessun blocco di questo tipo apparirà nelle colonne.
  - **Valore consigliato:** SÌ (se vuoi promuovere ampiamente la funzione)
  - **Scenario / esempio del commerciante:** Se vuoi promuovere attivamente il programma di referral a tutti i visitatori, inclusi quelli non ancora loggati, abilitare questa opzione aumenterà la visibilità. Potresti posizionarlo nella colonna destra sulle pagine dei prodotti per incoraggiare la condivisione.
- **Numero di voucher da generare (FV\_NBC)**

  - **Cosa fa questa impostazione:** Definisce quanti codici voucher unici un singolo cliente può generare e inviare agli amici.
  - **Effetto della modifica di questa impostazione:**
    - *Impostato su 1:* Ogni cliente può inviare solo un voucher a un amico.
    - *Impostato su 5:* Ogni cliente può inviare fino a cinque voucher a cinque amici diversi.
    - *Impostato su 0 (o un numero molto alto):* Consente generazioni illimitate di voucher per cliente.
  - **Valore consigliato:** 3-5 (per incoraggiare la condivisione senza sovraccaricare il sistema o creare troppi sconti)
  - **Scenario / esempio del commerciante:** Se vuoi limitare il numero di referral che un singolo cliente può fare per prevenire abusi o gestire il tuo budget sconti, imposta un numero specifico come 3. Se vuoi la massima diffusione virale, imposta un numero più alto o 0 per illimitato.
- **Consenti agli utenti non loggati di inviare voucher (FV\_UNLOGGED)**

  - **Cosa fa questa impostazione:** Determina se i visitatori che non sono loggati in un account cliente possono comunque accedere al modulo "Voucher per amico" e inviare un voucher.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (Sì):* Gli utenti non loggati vedranno i link "Voucher per amico" (se abilitati nelle colonne/footer) e potranno procedere a compilare il modulo. Probabilmente verrà loro chiesto di inserire il proprio indirizzo email come referente.
    - *Quando disabilitato (No):* Solo i clienti loggati possono accedere e utilizzare la funzione di condivisione del voucher. Gli utenti non loggati che cliccano sul link potrebbero essere reindirizzati alla pagina di login/registrazione.
  - **Valore consigliato:** NO (per garantire che solo i clienti effettivi stiano referenziando e per prevenire spam/abusi)
  - **Scenario / esempio del commerciante:** Se vuoi controllare rigorosamente chi può referenziare e assicurarti che solo la tua base clienti esistente stia partecipando, disabilita questa opzione. Se vuoi consentire a chiunque di referenziare, anche se non ha ancora acquistato, abilitala (ma fai attenzione a potenziali spam).
- **Email del negozio (PS\_SHOP\_EMAIL)**

  - **Cosa fa questa impostazione:** Questo campo visualizza tipicamente l'indirizzo email di contatto predefinito del tuo negozio, che viene utilizzato come email del "mittente" per la notifica del voucher inviata agli amici. Di solito viene estratto dalle impostazioni generali di PrestaShop.
  - **Effetto della modifica di questa impostazione:** La modifica qui potrebbe sovrascrivere l'email del negozio a livello di sistema per le email specifiche di questo modulo.
  - **Valore consigliato:** Assicurati che sia un indirizzo email valido e professionale associato al tuo negozio (es. `info@iltuonegozio.com`).
  - **Scenario / esempio del commerciante:** L'amico che riceve il voucher vedrà questa email come mittente. Dovrebbe essere un indirizzo che può riconoscere e di cui fidarsi.
- **Nome del negozio (PS\_SHOP\_NAME)**

  - **Cosa fa questa impostazione:** Questo campo visualizza tipicamente il nome ufficiale del tuo negozio, che viene utilizzato nell'oggetto e nel corpo dell'email quando si invia il voucher a un amico. Di solito viene estratto dalle impostazioni generali di PrestaShop.
  - **Effetto della modifica di questa impostazione:** La modifica qui potrebbe sovrascrivere il nome del negozio a livello di sistema per le email specifiche di questo modulo.
  - **Valore consigliato:** Il nome ufficiale del tuo negozio (es. "Il Mio Fantastico Negozio").
  - **Scenario / esempio del commerciante:** L'amico che riceve il voucher vedrà questo nome. Dovrebbe essere chiaro e coerente con il tuo marchio.

#### 2.1.1 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Visualizza il link "Voucher per amico" nel blocco Il mio account (fvc\_b\_position) | SÌ | Mostra il link nel blocco account cliente (intestazione/colonna) per un accesso rapido. |
| Configurazione modulo | Visualizza il link "Voucher per amico" nella pagina Il mio account (fvc\_b\_position2) | SÌ | Mostra il link nella pagina principale "Il mio account". |
| Configurazione modulo | Visualizza il link "Voucher per amico" nella colonna sinistra/destra (fvc\_b\_position3) | SÌ | Mostra un blocco/link promozionale nelle colonne laterali per tutti i visitatori. |
| Configurazione modulo | Numero di voucher da generare (FV\_NBC) | 3-5 | Limita quanti voucher un singolo cliente può inviare. |
| Configurazione modulo | Consenti agli utenti non loggati di inviare voucher (FV\_UNLOGGED) | NO | Limita l'invio di voucher solo ai clienti loggati. |
| Configurazione modulo | Email del negozio (PS\_SHOP\_EMAIL) | Email del tuo negozio | Email del mittente per le notifiche dei voucher. |
| Configurazione modulo | Nome del negozio (PS\_SHOP\_NAME) | Nome del tuo negozio | Nome del negozio utilizzato nelle email di notifica dei voucher. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei clienti non riescono a trovare il link "Voucher per amico".**
R1: Vai su **Moduli > Gestione moduli > Configura** per "Voucher per amico". Assicurati che `fvc_b_position`, `fvc_b_position2` e `fvc_b_position3` siano impostati su "Sì" per i posizionamenti desiderati (blocco Il mio account, pagina Il mio account, colonna sinistra/destra). Inoltre, controlla le assegnazioni degli hook del tuo tema in **Design > Posizioni** per assicurarti che il modulo sia agganciato a `displayMyAccountBlock`, `displayCustomerAccount`, `displayLeftColumn` o `displayRightColumn` come previsto.

**D2: Gli amici non ricevono le email del voucher.**
R2:
1. **Controlla le cartelle spam:** Consiglia ai tuoi clienti di chiedere ai loro amici di controllare le loro cartelle spam o posta indesiderata.
2. **Configurazione email del negozio:** Verifica che l'impostazione `PS_SHOP_EMAIL` nella configurazione del modulo sia un indirizzo email valido e attivo.
3. **Impostazioni email di PrestaShop:** Vai su **Parametri avanzati > E-mail** nel back office di PrestaShop. Invia un'email di prova per assicurarti che il sistema di posta del tuo negozio funzioni correttamente. In caso contrario, potresti avere un problema con la configurazione del tuo server SMTP.
4. **Log del server:** Il tuo webmaster può controllare i log di posta del server per eventuali errori relativi alle email in uscita.

**D3: Il codice voucher non funziona per l'amico.**
R3:
1. **Controlla scadenza/condizioni:** Assicurati che il voucher non sia scaduto e che il carrello dell'amico soddisfi eventuali requisiti di acquisto minimo o restrizioni di prodotto che potrebbero essere impostate per il voucher generato (questi sono solitamente definiti nella sezione nativa "Regole carrello" di PrestaShop, che questo modulo sfrutta).
2. **Inserimento corretto del codice:** Conferma che l'amico stia inserendo il codice esattamente come appare (sensibile alle maiuscole/minuscole, senza spazi extra).
3. **Uso singolo:** La maggior parte dei voucher referral sono a uso singolo. Se l'amico ha precedentemente provato a usarlo, potrebbe non essere più valido.

**D4: Il modulo non appare correttamente sul mio tema personalizzato.**
R4: I temi personalizzati hanno spesso uno stile unico che a volte può entrare in conflitto con il design dei moduli.
1. **Svuota la cache:** Per prima cosa, prova a svuotare la cache di PrestaShop in **Parametri avanzati > Prestazioni**.
2. **Sovrascritture del tema:** Il tuo webmaster potrebbe aver bisogno di creare sovrascritture CSS nel foglio di stile del tuo tema per regolare l'aspetto del modulo. Il modulo utilizza `views/css/ps16.css` per il suo stile, che può essere un punto di partenza per le modifiche.
3. **Visualizzazione mobile:** Assicurati che il tuo tema sia completamente reattivo. Se i problemi persistono su mobile, è probabile un conflitto CSS che richiede l'intervento di uno sviluppatore.

**D5: Posso cambiare l'importo o il tipo di sconto del voucher?**
R5: Il modulo stesso genera una regola carrello standard di PrestaShop. Tipicamente configureresti le specifiche del voucher generato (es. sconto percentuale, importo fisso, acquisto minimo, prodotti specifici) all'interno della sezione nativa di PrestaShop **Catalogo > Sconti > Regole carrello**. Il modulo crea il *meccanismo* per la condivisione, ma i *dettagli* dello sconto sono gestiti dal sistema di sconti principale di PrestaShop.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce un'analisi approfondita della struttura tecnica del modulo "Voucher per amico", destinata a sviluppatori, webmaster e agenzie tecniche.

### 4.1 Panoramica dell'architettura

Il modulo "Voucher per amico" segue un'architettura standard dei moduli PrestaShop, sfruttando principalmente `ModuleFrontController` per le interazioni del front-office e la classe principale del modulo per la configurazione e la gestione degli hook. Si integra con il sistema nativo `CartRule` di PrestaShop per generare e gestire i voucher di sconto. La logica del modulo è contenuta nel suo file PHP principale e nei controller frontali dedicati, con i template Smarty che gestiscono la presentazione.

### 4.2 Controller (`controllers/`)

#### Controller del Front-Office

Questi controller gestiscono la logica rivolta al cliente per la generazione e la gestione dei voucher.

- **`controllers/front/index.php`**

  - **Nome classe:** `FriendvoucherIndexModuleFrontController` (estende `ModuleFrontController`)
  - **Responsabilità:** Questo controller è probabilmente responsabile della visualizzazione del modulo iniziale "Voucher per amico" dove un cliente inserisce i dettagli del suo amico. Gestisce l'invio di questo modulo, convalida l'input, genera la `CartRule` (voucher) e invia la notifica via email all'amico. Gestisce anche la logica per limitare il numero di voucher che un cliente può inviare.
  - **Percorsi:** Risponde a un URL come `iltuonegozio.com/module/friendvoucher/index`.
- **`controllers/front/myvoucher.php`**

  - **Nome classe:** `FriendvoucherMyvoucherModuleFrontController` (estende `ModuleFrontController`)
  - **Responsabilità:** Questo controller è responsabile della visualizzazione della pagina personale "I miei voucher" del cliente, tipicamente accessibile dalla sezione "Il mio account". Elenca i voucher che il cliente ha già inviato e potenzialmente fornisce opzioni per visualizzarne lo stato o inviarne di nuovi.
  - **Percorsi:** Risponde a un URL come `iltuonegozio.com/module/friendvoucher/myvoucher`.

#### Controller di amministrazione del Back-Office

Questo modulo non sembra avere controller di amministrazione personalizzati dedicati. Tutta la configurazione del back-office è gestita tramite il metodo `getContent()` della classe principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

Sulla base dell'inventario fornito, questo modulo non definisce classi personalizzate o `ObjectModel` in una directory `classes/`. Probabilmente utilizza la classe `CartRule` di PrestaShop per la gestione dei voucher e `Customer` per i dati utente.

### 4.4 Risorse JavaScript (`views/js/`)

- **`lib/voucherengine/script.js`**
  - **Ambito:** Front-office.
  - **Dettagli:** Questo script probabilmente gestisce le interazioni lato client sul modulo "Voucher per amico". Ciò potrebbe includere:
    - Convalida del modulo (es. controllo di formati email validi, campi obbligatori).
    - Invii AJAX della richiesta di voucher al controller frontale `index.php`.
    - Visualizzazione di messaggi di successo o di errore all'utente senza un ricaricamento completo della pagina.
    - Potenziali aggiornamenti dinamici del modulo basati sull'input dell'utente.
    - Qualsiasi elemento interattivo relativo al processo di generazione del voucher.

### 4.5 Fogli di stile CSS (`views/css/`)

- **`lib/voucherengine/ps16.css`**
  - **Ambito:** Stile del cliente del front-office.
  - **Dettagli:** Questo foglio di stile fornisce lo stile visivo per i moduli, i link e i blocchi di visualizzazione "Voucher per amico" nel front office. Probabilmente contiene stili per:
    - Gli elementi del modulo di condivisione del voucher (campi di input, pulsanti).
    - L'elenco "I miei voucher" nella pagina dell'account cliente.
    - I blocchi promozionali nelle colonne sinistra/destra.
    - Layout e tipografia di base per garantire la leggibilità.
  - **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere:** Gli sviluppatori dovrebbero ispezionare l'HTML renderizzato per identificare nomi di classe specifici (es. `.friendvoucher-form`, `.voucher-list`, `.friendvoucher-block`) da utilizzare per l'integrazione e la personalizzazione del tema.

### 4.6 Struttura del template Smarty (`views/templates/`)

#### Template degli hook (`views/templates/hook/`)

Il modulo non elenca esplicitamente i template in una sottodirectory `hook/`, ma i template elencati di seguito sono tipicamente renderizzati tramite hook.

- **`views/templates/front/footer.tpl`**

  - **Hook:** `displayFooter`
  - **Output:** Un link o un blocco relativo a "Voucher per amico" nel footer del negozio.
- **`views/templates/front/leftcolumn.tpl`**

  - **Hook:** `displayLeftColumn`
  - **Output:** Un blocco promozionale o un link per "Voucher per amico" nella barra laterale sinistra del negozio.
- **`views/templates/front/rightcolumn.tpl`**

  - **Hook:** `displayRightColumn`
  - **Output:** Un blocco promozionale o un link per "Voucher per amico" nella barra laterale destra del negozio.

#### Template di amministrazione (`views/templates/admin/`)

Questo modulo non sembra avere template di amministrazione personalizzati. La configurazione è probabilmente renderizzata direttamente dal metodo `getContent()` utilizzando i moduli helper di PrestaShop.

#### Template del front-office (`views/templates/front/`)

Questi template sono renderizzati dai controller frontali del modulo.

- **`views/templates/front/my-account.tpl`**

  - **Hook:** `displayCustomerAccount` (o `displayMyAccountBlock`)
  - **Output:** Un link o un'icona nella pagina principale "Il mio account" del cliente, che lo indirizza al controller `myvoucher.php`.
- **`views/templates/front/my-voucher.tpl`**

  - **Controller:** `FriendvoucherMyvoucherModuleFrontController`
  - **Output:** La pagina dedicata che mostra un elenco di voucher che il cliente ha inviato, il loro stato e potenzialmente un modulo per inviarne di nuovi.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

Questo modulo non sembra creare tabelle SQL personalizzate. Probabilmente memorizza la sua configurazione in `ps_configuration` e sfrutta le tabelle principali di PrestaShop `ps_cart_rule` e `ps_cart_rule_lang` per i voucher generati.

#### Tabella degli hook registrati

Il modulo si registra a vari hook per visualizzare il suo contenuto e la sua funzionalità.

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displaymyAccountBlock` | Renderizza nel blocco account cliente (intestazione/colonna) dopo il login. | Visualizza un link rapido alla pagina del voucher per gli utenti loggati. |
| `displayrightColumn` | Renderizza il contenuto nella barra laterale destra. | Visualizza un blocco/link promozionale per la funzione voucher. |
| `displayLeftColumn` | Renderizza il contenuto nella barra laterale sinistra. | Visualizza un blocco/link promozionale per la funzione voucher. |
| `displayFooter` | Renderizza il contenuto nel footer del negozio. | Visualizza un link alla pagina del voucher nel footer. |
| `displaycustomerAccount` | Renderizza il contenuto nella pagina principale "Il mio account" del cliente. | Visualizza un link/icona dedicato per la funzione voucher nella pagina dell'account. |
| `actionValidateOrder` | Eseguito dopo che un ordine è stato validato con successo. | (Potenziale) Potrebbe essere utilizzato per attivare azioni relative a ricompense per i referenti o per tracciare referral di successo, sebbene non esplicitamente confermato dall'inventario dei file. |

## 5. Supporto ufficiale e aggiornamenti

Per supporto ufficiale, aggiornamenti del modulo e qualsiasi ulteriore assistenza, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). È possibile accedere ai moduli acquistati, scaricare le ultime versioni e inviare ticket di supporto direttamente dal proprio account.
