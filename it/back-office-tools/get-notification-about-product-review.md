---
title: "Ricevi notifica sulla recensione del prodotto - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Ricevi notifica sulla recensione del prodotto' di MyPresta.eu."
sidebar:
  label: "Ricevi notifica sulla recensione del prodotto"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Get notification about product review su MyPresta.eu](https://mypresta.eu/modules/administration-tools/get-notification-about-product-review.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/get-notification-about-product-review/)
>
> ---


# Ricevi notifica sulla recensione del prodotto

## 1. Requisiti e Compatibilità

-   **Versioni PrestaShop supportate**: PrestaShop 1.7.x
-   **Compatibilità PHP**: PHP 7.1 - 8.5
-   **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).
-   **Prerequisito**: Questo modulo richiede che il nostro addon gratuito per le recensioni dei prodotti sia installato e attivo. Estende la funzionalità di quel modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)
Dopo l'installazione, cliccando su "Configura" si accederà alla schermata di configurazione principale e unica per questo modulo. Questa schermata ti consente di definire quale indirizzo email riceve le notifiche.

#### **Indirizzo email a cui inviare le notifiche**
-   **Cosa fa questa impostazione:** Questa è l'impostazione più cruciale. Determina l'indirizzo email a cui verranno inviate tutte le notifiche relative alle recensioni.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando viene inserita un'email valida:* Tutti gli avvisi (nuova recensione, commento segnalato, voto utile) verranno inviati a questo specifico indirizzo email.
    -   *Quando lasciato vuoto o viene inserita un'email non valida:* Non riceverai alcuna notifica, disabilitando di fatto la funzione principale del modulo.
-   **Valore consigliato:** Il tuo indirizzo email aziendale principale, o un indirizzo email regolarmente monitorato dal tuo team di assistenza clienti o marketing.
-   **Scenario / esempio del commerciante:** Se il tuo team di assistenza clienti gestisce tutte le interazioni con i clienti, potresti inserire `servizioclienti@tuonegozio.com` qui. Se tu, come proprietario, vuoi essere informato personalmente, usa il tuo indirizzo email diretto.

#### **Tabella di riferimento rapido della configurazione**

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Configurazione modulo | Indirizzo email a cui inviare le notifiche | Il tuo indirizzo email aziendale principale | Specifica il destinatario dell'email per tutti gli avvisi relativi alle recensioni (nuova recensione, commento segnalato, voto utile). |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Non ricevo alcuna notifica via email. Cosa devo fare?**
R:
1.  **Controlla l'indirizzo email:** Vai su **Moduli > Gestione moduli > Configura** per "Ricevi notifica sulla recensione del prodotto" e assicurati che l'indirizzo email inserito sia corretto e privo di errori di battitura.
2.  **Controlla la cartella spam:** Le notifiche potrebbero a volte essere filtrate nella tua cartella spam o posta indesiderata. Aggiungi l'indirizzo email del mittente (solitamente l'email predefinita del tuo negozio) alla tua lista di mittenti sicuri.
3.  **Verifica le impostazioni email di PrestaShop:** Assicurati che le impostazioni email del tuo negozio PrestaShop siano configurate correttamente e che inviino email in generale. Puoi testarlo creando un nuovo account cliente o effettuando un ordine di prova. Vai su **Parametri avanzati > E-mail** nel tuo back office.
4.  **Contatta il tuo provider di hosting:** Se le email di PrestaShop non funzionano affatto, potrebbe esserci un problema con la funzione di posta del tuo server. Il tuo provider di hosting può aiutarti a diagnosticarlo.
5.  **Assicurati che il modulo prerequisito sia installato:** Questo modulo estende il nostro addon gratuito per le recensioni dei prodotti. Assicurati che quel modulo sia installato e funzioni correttamente.

**D: Posso inviare notifiche a più indirizzi email?**
R: Il design attuale del modulo consente di configurare un solo indirizzo email. Se hai bisogno di inviare a più destinatari, puoi impostare una regola di inoltro email nel tuo client di posta o server (ad esempio, inoltrare le email dall'indirizzo configurato a un alias di gruppo).

**D: Questo modulo funziona con qualsiasi sistema di recensioni dei prodotti?**
R: No, questo modulo è specificamente progettato per funzionare come estensione dell'**addon gratuito per le recensioni dei prodotti di MyPresta.eu**. Non fornirà notifiche per altri moduli di recensioni di terze parti.

**D: Ho aggiornato il mio tema PrestaShop e ora le notifiche non funzionano.**
R: Questo modulo non ha componenti front-office, quindi un cambio di tema non dovrebbe influenzare direttamente la sua funzionalità di notifica. Ricontrolla la configurazione email nel modulo e le impostazioni email di PrestaShop come descritto sopra. Se il problema persiste, è probabile che non sia correlato al tema e indichi un problema del server o del core email di PrestaShop.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura
Il modulo "Ricevi notifica sulla recensione del prodotto" (`reviewsalerts`) è un modulo PrestaShop leggero progettato per estendere la funzionalità del modulo `productcomments` (o un modulo di recensioni simile, in particolare l'addon gratuito per le recensioni dei prodotti di MyPresta.eu). Opera principalmente agganciandosi ad azioni rilevanti attivate dal sistema di recensioni e inviando notifiche email basate su questi eventi. Segue un semplice modello basato su eventi, sfruttando il sistema di hook di PrestaShop senza introdurre complesse strutture MVC o tabelle di database personalizzate.

### 4.2 Controller (`controllers/`)
Questo modulo non contiene controller front-office o back-office personalizzati. Tutta la logica è incapsulata nel file principale del modulo ed eseguita tramite hook.

### 4.3 Classi e modelli principali (`classes/`)
Questo modulo non definisce classi personalizzate o istanze di `ObjectModel`. La sua funzionalità è contenuta all'interno della classe principale `reviewsalerts`.

### 4.4 Risorse JavaScript (`views/js/`)
Questo modulo non include alcun file JavaScript.

### 4.5 Fogli di stile CSS (`views/css/`)
Questo modulo non include alcun file CSS.

### 4.6 Struttura del template Smarty (`views/templates/`)
Questo modulo non include alcun file di template Smarty personalizzato per la visualizzazione front-office o la configurazione back-office. Il modulo di configurazione viene generato dinamicamente da `getContent()` nel file principale del modulo.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**: Questo modulo non crea tabelle del database personalizzate. Memorizza la sua singola impostazione di configurazione (l'indirizzo email di notifica) nella tabella standard `ps_configuration`.
    *   **Chiave di configurazione**: `REVIEWSALERTS_EMAIL`

-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| :-------- | :--------------- | :---------------- |
| `actionObjectProductCommentAddAfter` | Dopo che una nuova recensione del prodotto (commento) è stata aggiunta con successo al database. | Attiva una notifica email all'indirizzo configurato, informando il commerciante della nuova recensione. |
| `actionObjectProductCommentReportAfter` | Dopo che una recensione del prodotto è stata segnalata con successo da un cliente. | Attiva una notifica email all'indirizzo configurato, informando il commerciante che una recensione è stata segnalata. |
| `actionObjectProductCommentUsefulAfter` | Dopo che un cliente contrassegna una recensione del prodotto come "utile". | Attiva una notifica email all'indirizzo configurato, informando il commerciante che è stato votato l'utilità di una recensione. |

Il metodo `install()` del modulo registra questi hook, e i corrispondenti metodi `hookActionObjectProductCommentAddAfter()`, `hookActionObjectProductCommentReportAfter()` e `hookActionObjectProductCommentUsefulAfter()` gestiscono la logica di invio delle email.

L'invio delle email è tipicamente gestito dalla funzione `Mail::Send()` di PrestaShop, utilizzando i template e le impostazioni email configurate del negozio. Il modulo probabilmente costruirà il contenuto dell'email dinamicamente in base al contesto dell'azione attivata (ad esempio, contenuto della recensione, nome del prodotto, dettagli del segnalatore).

## 5. Supporto ufficiale e aggiornamenti
Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Ricevi notifica sulla recensione del prodotto", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e alla configurazione del modulo.
