---
title: "Condivisione prodotto Twitter + codice voucher - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Condivisione prodotto Twitter + codice voucher' di MyPresta.eu."
sidebar:
  label: "Condivisione prodotto Twitter + codice voucher - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Twitter product share + voucher code su MyPresta.eu](https://mypresta.eu/modules/social-networks/twitter-product-share-voucher-code.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/twitter-product-share-voucher-code/)
>
> ---


# Condivisione prodotto Twitter + codice voucher

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop e sono solitamente abilitate di default sulla maggior parte degli ambienti di hosting.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo "Condivisione prodotto Twitter + codice voucher", accessibile dopo l'installazione cliccando sul pulsante "Configura". Qui definirai come si comporta il pulsante di condivisione e come vengono generati i codici voucher.

#### **Impostazioni Generali**

-   **Abilita Modulo:**

    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare l'intero modulo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* Il pulsante di condivisione Twitter apparirà sulle tue pagine prodotto (in base alla selezione dell'hook), e il sistema di generazione del codice voucher sarà attivo.
        -   *Quando disabilitato (NO):* Il pulsante di condivisione Twitter non apparirà, e nessun codice voucher verrà generato per le condivisioni.
    -   **Valore consigliato:** SÌ (per attivare la funzionalità del modulo).
    -   **Scenario / esempio del commerciante:** Se stai configurando il modulo per la prima volta o eseguendo la manutenzione, potresti disabilitarlo temporaneamente. Altrimenti, mantienilo abilitato per beneficiare della condivisione social.
-   **Hook per visualizzare il pulsante:**

    -   **Cosa fa questa impostazione:** Determina dove il pulsante di condivisione Twitter verrà posizionato visivamente sulle tue pagine prodotto.
    -   **Effetto della modifica di questa impostazione:**
        -   *Opzioni (esempi):* `displayProductButtons`, `displayRightColumnProduct`, `displayFooterProduct`, `displayProductExtraContent`.
        -   *Quando impostato su `displayProductButtons` (comune):* Il pulsante apparirà probabilmente vicino al pulsante "Aggiungi al carrello" o al selettore della quantità del prodotto.
        -   *Quando impostato su `displayRightColumnProduct`:* Il pulsante apparirà nella colonna destra della tua pagina prodotto (se il tuo tema ne ha una).
        -   *Quando impostato su `displayFooterProduct`:* Il pulsante apparirà nella sezione del piè di pagina della pagina prodotto.
    -   **Valore consigliato:** `displayProductButtons` o `displayProductExtraContent` per la massima visibilità e coinvolgimento, poiché questi sono tipicamente vicini alle informazioni principali del prodotto.
    -   **Scenario / esempio del commerciante:** Potresti testare diversi hook per vedere quale posizionamento genera il maggior numero di condivisioni sul tuo tema specifico. Una posizione prominente è solitamente la migliore.
-   **Numero di condivisioni richieste per un voucher:**

    -   **Cosa fa questa impostazione:** Definisce quante condivisioni di prodotti uniche un cliente deve effettuare prima di ricevere un voucher sconto.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su 1:* Un cliente riceve un voucher immediatamente dopo la sua prima condivisione.
        -   *Quando impostato su 3:* Un cliente deve condividere tre prodotti diversi (o lo stesso prodotto tre volte, a seconda della logica interna) prima che venga emesso un voucher.
    -   **Valore consigliato:** 1 (per incoraggiare l'azione e la ricompensa immediate) o 2 (per incoraggiare un coinvolgimento leggermente maggiore senza essere troppo esigente).
    -   **Scenario / esempio del commerciante:** Se vuoi rendere facile per i clienti ottenere uno sconto, impostalo su 1. Se vuoi incoraggiare una condivisione più estesa, impostalo più in alto, ma tieni presente che un numero più alto potrebbe ridurre la partecipazione.

#### **Impostazioni Codice Voucher**

-   **Prefisso codice voucher:**

    -   **Cosa fa questa impostazione:** Una stringa di caratteri personalizzata che apparirà all'inizio di ogni codice voucher generato.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su `TWITTER-`:* Un codice voucher potrebbe apparire come `TWITTER-ABCDE123`.
        -   *Quando lasciato vuoto:* Il codice voucher sarà composto da caratteri puramente casuali.
    -   **Valore consigliato:** `TWITTER-` o `SHARE-` per identificare facilmente la fonte del voucher.
    -   **Scenario / esempio del commerciante:** L'uso di un prefisso ti aiuta a tenere traccia di quali campagne di marketing stanno generando voucher specifici nei tuoi rapporti di vendita di PrestaShop.
-   **Valore codice voucher (percentuale):**

    -   **Cosa fa questa impostazione:** La percentuale di sconto applicata dal codice voucher generato.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su 10:* Il voucher darà uno sconto del 10% sull'ordine del cliente.
        -   *Quando impostato su 5:* Il voucher darà uno sconto del 5%.
    -   **Valore consigliato:** 5-15% (a seconda dei tuoi margini di profitto e del livello di incentivo desiderato).
    -   **Scenario / esempio del commerciante:** Uno sconto del 10% è spesso un buon equilibrio tra l'attrarre i clienti e il mantenere la redditività.
-   **Validità codice voucher (giorni):**

    -   **Cosa fa questa impostazione:** Quanti giorni il codice voucher generato sarà valido dal momento in cui viene emesso.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su 7:* Il voucher scadrà 7 giorni dopo che il cliente lo riceve.
        -   *Quando impostato su 30:* Il voucher sarà valido per un mese.
    -   **Valore consigliato:** 7-14 giorni (per creare un senso di urgenza senza essere troppo restrittivo).
    -   **Scenario / esempio del commerciante:** Un periodo di validità più breve incoraggia i clienti a effettuare un acquisto prima piuttosto che dopo, impedendo loro di dimenticare il voucher.
-   **Importo minimo per la validità del voucher:**

    -   **Cosa fa questa impostazione:** L'importo totale minimo dell'ordine (prima della spedizione) richiesto affinché il cliente possa utilizzare il voucher sconto.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su 50:* Il voucher può essere utilizzato solo se il totale del carrello del cliente è di €50 o più.
        -   *Quando impostato su 0 (o vuoto):* Il voucher può essere utilizzato su qualsiasi importo dell'ordine.
    -   **Valore consigliato:** Un importo ragionevole che incoraggi un acquisto leggermente più grande, o 0 se vuoi consentirlo su qualsiasi ordine.
    -   **Scenario / esempio del commerciante:** Se il tuo valore medio dell'ordine è di €40, impostare un minimo di €50 potrebbe incoraggiare i clienti ad aggiungere un altro articolo al carrello per raggiungere la soglia e utilizzare lo sconto.
-   **Descrizione codice voucher:**

    -   **Cosa fa questa impostazione:** Una breve descrizione testuale che sarà associata al codice voucher nel tuo back office di PrestaShop (e potenzialmente visibile al cliente nel suo account se controlla i suoi voucher).
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su "Sconto Condivisione Twitter":* Questo testo apparirà nei dettagli del voucher.
    -   **Valore consigliato:** "Sconto per Condivisione Twitter" o "Grazie per aver condiviso su Twitter!"
    -   **Scenario / esempio del commerciante:** Questo aiuta te e i tuoi clienti a capire l'origine del voucher.
-   **Nome codice voucher:**

    -   **Cosa fa questa impostazione:** Il nome interno per la regola del voucher in PrestaShop. Questo è principalmente per la tua organizzazione interna.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su "Coupon Condivisione Twitter":* Questo nome apparirà nella sezione "Regole carrello" di PrestaShop.
    -   **Valore consigliato:** "Coupon Condivisione Twitter" o "Sconto Condivisione Social".
    -   **Scenario / esempio del commerciante:** Un nome chiaro rende facile trovare e gestire questi voucher generati automaticamente all'interno del tuo pannello di amministrazione di PrestaShop.

#### **Impostazioni Testo di Condivisione Twitter**

-   **Testo di condivisione predefinito:**
    -   **Cosa fa questa impostazione:** Il testo predefinito che verrà precompilato nel pop-up di condivisione di Twitter quando un cliente clicca sul pulsante di condivisione. Questo testo sarà combinato con il nome del prodotto e il link.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su "Dai un'occhiata a questo fantastico prodotto!":* Il tweet potrebbe apparire come "Dai un'occhiata a questo fantastico prodotto! [Nome Prodotto] [Link Prodotto]".
    -   **Valore consigliato:** Qualcosa di coinvolgente come "Dai un'occhiata a questo fantastico prodotto da [Nome del tuo negozio]!" o "Ho appena trovato questo ottimo prodotto!"
    -   **Scenario / esempio del commerciante:** Un testo predefinito accattivante incoraggia più clic e coinvolgimento da parte dei follower del cliente.

#### **Pulsante Salva**

-   **Salva:**
    -   **Cosa fa questo pulsante:** Applica tutte le modifiche che hai apportato in questa pagina di configurazione.
    -   **Effetto del clic su questo pulsante:** Le tue impostazioni vengono salvate nel database e il comportamento del modulo si aggiornerà immediatamente nel tuo front office.
    -   **Azione consigliata:** Clicca sempre su "Salva" dopo aver apportato qualsiasi modifica.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Abilita Modulo | SÌ | Attiva/disattiva il modulo. |
| | Hook per visualizzare il pulsante | `displayProductButtons` | Controlla dove appare il pulsante di condivisione sulle pagine prodotto. |
| | Numero di condivisioni richieste per un voucher | 1 | Quante condivisioni prima che un cliente ottenga un voucher. |
| | Prefisso codice voucher | `TWITTER-` | Aggiunge un prefisso personalizzato ai codici voucher generati. |
| | Valore codice voucher (percentuale) | 10 | La percentuale di sconto del voucher. |
| | Validità codice voucher (giorni) | 7-14 | Per quanto tempo il voucher è valido dopo la generazione. |
| | Importo minimo per la validità del voucher | 0 (o importo ragionevole) | Totale minimo del carrello richiesto per utilizzare il voucher. |
| | Descrizione codice voucher | "Sconto per Condivisione Twitter" | Descrizione interna per il voucher. |
| | Nome codice voucher | "Coupon Condivisione Twitter" | Nome interno per la regola del voucher. |
| | Testo di condivisione predefinito | "Dai un'occhiata a questo fantastico prodotto!" | Testo precompilato per il pop-up di condivisione di Twitter. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Il pulsante di condivisione di Twitter non appare sulle mie pagine prodotto.**

-   **R:** Innanzitutto, assicurati che il modulo sia **abilitato** nella sua configurazione. In secondo luogo, controlla l'impostazione **"Hook per visualizzare il pulsante"**. Il tuo tema potrebbe non renderizzare l'hook scelto in una posizione visibile, o l'hook potrebbe non esistere. Prova a passare a un hook comune diverso come `displayProductButtons` o `displayProductExtraContent`. Se ancora non appare, il tuo tema potrebbe richiedere un'integrazione personalizzata per certi hook, o potrebbe esserci un conflitto.
-   **Consiglio Pro:** Svuota la cache di PrestaShop (Parametri Avanzati > Prestazioni) dopo aver apportato modifiche alle impostazioni del modulo o ai file del tema.

**D2: I clienti condividono, ma non ricevono codici voucher.**

-   **R:**
    1.  **Controlla "Numero di condivisioni richieste per un voucher":** È impostato su 1? Se è più alto, i clienti devono condividere più volte prima di ottenere un voucher.
    2.  **Verifica le impostazioni del voucher:** Assicurati che "Valore codice voucher (percentuale)" sia impostato su un numero maggiore di 0 e che anche "Validità codice voucher (giorni)" sia impostato.
    3.  **Regole carrello PrestaShop:** Controlla il tuo Back Office di PrestaShop sotto **Catalogo > Sconti > Regole carrello**. Dovresti vedere i voucher generati automaticamente con il nome che hai specificato (ad esempio, "Coupon Condivisione Twitter"). Se non appaiono nuove regole, potrebbe esserci un problema con la logica di generazione del voucher.
-   **Consiglio Pro:** Testa il processo tu stesso. Condividi un prodotto dal tuo negozio mentre sei loggato come cliente e vedi se viene generato un voucher.

**D3: Il pop-up di condivisione di Twitter appare strano o non funziona correttamente.**

-   **R:** Questo è spesso dovuto a conflitti JavaScript con altri moduli o con il tuo tema.
    1.  **Controlla la Console del Browser:** Apri gli strumenti per sviluppatori del tuo browser (solitamente F12) e cerca errori nella scheda "Console" quando clicchi sul pulsante di condivisione.
    2.  **Conflitti tra moduli:** Disabilita temporaneamente altri moduli che aggiungono JavaScript alle pagine prodotto (specialmente moduli di condivisione social o pop-up) per vedere se il problema si risolve.
-   **Consiglio Pro:** Assicurati che la tua installazione di PrestaShop e il tuo tema siano aggiornati. Componenti obsoleti possono talvolta causare conflitti inaspettati.

**D4: Posso personalizzare l'aspetto del pulsante di condivisione?**

-   **R:** Il modulo utilizza il proprio CSS (`twittercoupon/css.css` e `twittercoupon/css/css.css`). Puoi sovrascrivere questi stili nel file CSS personalizzato del tuo tema. Ispeziona il pulsante usando gli strumenti per sviluppatori del tuo browser per identificare le sue classi CSS e quindi aggiungi i tuoi stili personalizzati al file `custom.css` del tuo tema o equivalente.
-   **Consiglio Pro:** Evita di modificare direttamente i file CSS del modulo, poiché le tue modifiche andranno perse durante gli aggiornamenti del modulo. Utilizza sempre le capacità CSS personalizzate del tuo tema.

**D5: Come impedisce il modulo gli abusi (ad esempio, qualcuno che condivide ripetutamente per ottenere più voucher)?**

-   **R:** Il modulo di solito traccia le condivisioni per cliente (spesso tramite indirizzo IP o ID cliente se loggato) per impedire a un singolo utente di generare voucher illimitati. L'impostazione "Numero di condivisioni richieste per un voucher" aiuta anche a gestire questo aspetto. Per una prevenzione delle frodi più avanzata, potresti aver bisogno di moduli di sicurezza aggiuntivi di PrestaShop.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Condivisione prodotto Twitter + codice voucher" (`twittercoupon`) è un modulo PrestaShop standard implementato principalmente all'interno del suo file PHP principale, `ajax_twittercoupon.php`. Sfrutta il sistema di hook di PrestaShop per la visualizzazione nel front-office e la classe `Configuration` per l'archiviazione delle impostazioni. Il modulo genera dinamicamente oggetti `CartRule` (voucher) basati sulle azioni dell'utente. La sua funzionalità di front-office si basa su JavaScript per interagire con l'API di Twitter e un endpoint AJAX all'interno del modulo per elaborare le condivisioni ed emettere i voucher.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller dedicati per il front-office o il back-office nella directory `controllers/`. Tutte le richieste AJAX del front-office e la gestione della configurazione del back-office sono gestite direttamente all'interno del file principale del modulo, `ajax_twittercoupon.php`, in particolare tramite il suo metodo `getContent()` per la configurazione e un dispatch AJAX personalizzato per l'elaborazione delle condivisioni.

### 4.3 Classi e Modelli Core (`classes/`)

Questo modulo non definisce classi personalizzate né estende `ObjectModel` in una directory `classes/` dedicata. La logica principale per la generazione dei voucher interagisce direttamente con le classi `CartRule` e `Configuration` di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo include file JavaScript per gestire le interazioni del front-office.

-   `twittercoupon/lib/voucherengine/script.js`
    -   **Ambito:** Front-office.
    -   **Responsabilità:** Questo sembra essere lo script principale responsabile della logica lato client del modulo. Probabilmente gestisce:
        -   Associazione di eventi click al pulsante di condivisione di Twitter.
        -   Apertura del pop-up di condivisione di Twitter (utilizzando l'API Web Intent di Twitter).
        -   Rilevamento delle condivisioni riuscite (possibilmente tramite callback o polling).
        -   Effettuazione di chiamate AJAX al backend del modulo per registrare la condivisione e richiedere un voucher.
        -   Visualizzazione del codice voucher all'utente in caso di generazione riuscita.
        -   Potrebbe includere logica per prevenire condivisioni multiple dallo stesso utente in un breve periodo o per tracciare il numero di condivisioni.
-   `twittercoupon/trusted.js`
    -   **Ambito:** Front-office.
    -   **Responsabilità:** Il nome "trusted.js" suggerisce che potrebbe essere correlato alla sicurezza, al tracciamento o alla garanzia dell'integrità del processo di condivisione. Potrebbe potenzialmente gestire:
        -   Validazione lato client prima di avviare una condivisione.
        -   Tracciamento delle interazioni dell'utente per misure anti-frode.
        -   Integrazione con altri script di tracciamento o analisi.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo fornisce file CSS per lo stile degli elementi del front-office.

-   `twittercoupon/css.css`
    -   **Ambito:** Stile del front-office per il cliente.
    -   **Responsabilità:** Contiene gli stili principali per il pulsante di condivisione di Twitter, eventuali pop-up associati o messaggi visualizzati al cliente.
    -   **Selettori di classe CSS chiave:** Gli sviluppatori dovrebbero ispezionare l'HTML renderizzato per identificare classi specifiche (ad esempio, `.twitter-share-button`, `.twitter-coupon-message`) da sovrascrivere nel `custom.css` del loro tema.
-   `twittercoupon/css/css.css`
    -   **Ambito:** Stile del front-office per il cliente.
    -   **Responsabilità:** Questo file sembra essere un duplicato o un percorso alternativo per il CSS principale. È comune che i moduli abbiano percorsi ridondanti o che uno sia un fallback. Gli sviluppatori dovrebbero verificare quale viene effettivamente caricato nel browser.
    -   **Selettori di classe CSS chiave:** Come sopra.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo utilizza i template Smarty per il rendering del suo contenuto nel front-office.

-   **Template hook (`views/templates/hook/`)**:
    -   `twittercoupon/share.tpl`
        -   **Hook:** Questo template viene renderizzato nell'hook scelto nella configurazione del modulo (ad esempio, `displayProductButtons`, `displayRightColumnProduct`, `displayFooterProduct`).
        -   **Scopo:** Emette l'HTML per il pulsante "Condividi su Twitter" e potenzialmente un segnaposto per il messaggio del codice voucher o un trigger modale. Probabilmente includerà variabili per il nome del prodotto, l'URL del prodotto e il testo di condivisione predefinito.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il modulo memorizza principalmente le sue impostazioni di configurazione nella tabella `ps_configuration` di PrestaShop.
        -   `PS_TWITTERCOUPON_ENABLED` (booleano)
        -   `PS_TWITTERCOUPON_HOOK` (stringa)
        -   `PS_TWITTERCOUPON_SHARES_REQUIRED` (int)
        -   `PS_TWITTERCOUPON_PREFIX` (stringa)
        -   `PS_TWITTERCOUPON_VALUE` (float)
        -   `PS_TWITTERCOUPON_VALIDITY` (int)
        -   `PS_TWITTERCOUPON_MIN_AMOUNT` (float)
        -   `PS_TWITTERCOUPON_DESCRIPTION` (stringa)
        -   `PS_TWITTERCOUPON_NAME` (stringa)
        -   `PS_TWITTERCOUPON_DEFAULT_TEXT` (stringa)
    -   Probabilmente utilizza anche una tabella personalizzata (ad esempio, `ps_twittercoupon_shares` o simile) per tracciare le condivisioni individuali dei clienti (per `id_customer` o `ip_address`, `id_product`) e prevenire abusi, sebbene non sia stato elencato alcun file SQL esplicito, questa logica sarebbe gestita nel metodo `install()` del modulo principale. Questa tabella traccerebbe:
        -   `id_customer` (se loggato)
        -   `ip_address`
        -   `id_product`
        -   `share_date`
        -   `voucher_issued` (booleano)
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Per caricare le risorse CSS e JavaScript del modulo (`twittercoupon/css.css`, `twittercoupon/lib/voucherengine/script.js`, `twittercoupon/trusted.js`). |
| `displayProductButtons` | Sulla pagina prodotto, tipicamente vicino al pulsante "aggiungi al carrello". | Per visualizzare il pulsante di condivisione di Twitter (`share.tpl`). |
| `displayRightColumnProduct` | Sulla pagina prodotto, nella colonna destra. | Hook alternativo per visualizzare il pulsante di condivisione di Twitter (`share.tpl`). |
| `displayFooterProduct` | Sulla pagina prodotto, nell'area del piè di pagina. | Hook alternativo per visualizzare il pulsante di condivisione di Twitter (`share.tpl`). |
| `displayProductExtraContent` | Sulla pagina prodotto, spesso sotto la descrizione principale del prodotto. | Hook alternativo per visualizzare il pulsante di condivisione di Twitter (`share.tpl`). |
| `actionFrontControllerSetMedia` | Prima che un controller front-end renderizzi il suo contenuto, consentendo ai moduli di aggiungere risorse. | Per caricare le risorse CSS e JavaScript del modulo condizionalmente in base alla pagina. |
| (Chiamata AJAX interna) | Attivata da JavaScript sull'evento di condivisione. | Per elaborare la condivisione, aggiornare il conteggio delle condivisioni e generare una `CartRule` (voucher) se le condizioni sono soddisfatte. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto tecnico dedicato per il modulo "Condivisione prodotto Twitter + codice voucher", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è impegnato a fornire assistenza tempestiva e a garantire le prestazioni ottimali del tuo modulo.
