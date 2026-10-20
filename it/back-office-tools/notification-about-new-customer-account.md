---
title: "Notifica nuovo account cliente - Manuale commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Notifica nuovo account cliente' di MyPresta.eu."
sidebar:
  label: "Notifica nuovo account cliente - Manuale commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Notification about new customer account su MyPresta.eu](https://mypresta.eu/modules/administration-tools/notification-about-new-customer-account.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/notification-about-new-customer-account/)
>
> ---


# Notifica nuovo account cliente

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti e di solito sono abilitate di default sulla maggior parte degli ambienti di hosting.

## 2. Panoramica completa della configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo "Notifica nuovo account cliente". Ti verrà presentata la schermata di configurazione principale.

#### **1. Invia notifica al proprietario del negozio riguardo al nuovo account cliente**

-   **Cosa fa questa impostazione:** Questo interruttore controlla se tu, il proprietario del negozio, ricevi una notifica email quando un nuovo cliente si registra nel tuo negozio.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Ogni volta che un cliente crea con successo un account nel front office del tuo negozio, verrà inviata un'email all'indirizzo(i) email specificato(i) nel campo "Indirizzo(i) email per le notifiche" sottostante.
    -   *Quando disabilitato (NO):* Non riceverai alcuna notifica email sulle nuove registrazioni dei clienti.
-   **Valore consigliato:** SÌ.
-   **Scenario / esempio per il commerciante:** Vuoi essere immediatamente consapevole delle nuove iscrizioni dei clienti per monitorare la crescita o identificare potenziali lead per una campagna di benvenuto. L'abilitazione di questa opzione ti garantisce di ottenere queste informazioni cruciali.

#### **2. Indirizzo(i) email per le notifiche**

-   **Cosa fa questa impostazione:** Questo campo specifica l'indirizzo(i) email a cui verranno inviate le notifiche di nuova registrazione cliente.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su uno o più indirizzi email:* Le notifiche verranno consegnate a questi indirizzi. Se inserisci più indirizzi, separali con una virgola (es. `admin@tuonegozio.com, support@tuonegozio.com`).
    -   *Quando lasciato vuoto:* Anche se "Invia notifica al proprietario del negozio" è abilitato, non verranno inviate email perché non c'è un destinatario.
-   **Valore consigliato:** Il tuo indirizzo email di amministrazione principale del negozio, o un'email di team dedicata (es. `info@tuonegozio.com`).
-   **Scenario / esempio per il commerciante:** Vuoi che sia tu che il tuo team di assistenza clienti riceviate gli avvisi di nuove registrazioni. Inseriresti `tuonome@tuonegozio.com, support@tuonegozio.com` qui.

#### **3. Invia notifica al cliente se l'amministratore crea un nuovo account**

-   **Cosa fa questa impostazione:** Questo interruttore determina se un'email di benvenuto viene inviata automaticamente a un cliente se il suo account viene creato manualmente da un amministratore nel Back Office di PrestaShop (es. tramite Clienti > Aggiungi nuovo cliente).
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Quando tu o un altro amministratore create un nuovo account cliente nel Back Office, il cliente appena creato riceverà automaticamente un'email di benvenuto. Questa email include tipicamente i suoi dettagli di accesso o una conferma della creazione del suo account.
    -   *Quando disabilitato (NO):* I clienti i cui account sono creati manualmente nel Back Office non riceveranno alcuna email di benvenuto automatica dal modulo. Dovresti informarli manualmente se lo desideri.
-   **Valore consigliato:** SÌ.
-   **Scenario / esempio per il commerciante:** Crei frequentemente account per clienti B2B o per clienti che ordinano telefonicamente. L'abilitazione di questa opzione garantisce che ricevano un'email di benvenuto immediata e professionale senza che tu debba comporla e inviarla manualmente ogni volta.

#### **4. Pulsante Salva**

-   **Cosa fa:** Dopo aver apportato modifiche alle impostazioni sopra, devi cliccare su questo pulsante per applicare e salvare la tua nuova configurazione.
-   **Effetto del clic:** Le tue modifiche vengono salvate nel database e il modulo inizierà a operare immediatamente secondo le nuove impostazioni.
-   **Azione consigliata:** Clicca sempre su "Salva" dopo aver modificato qualsiasi impostazione.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Invia notifica al proprietario del negozio riguardo al nuovo account cliente | SÌ | Controlla se il proprietario del negozio riceve un'email sulla nuova registrazione del cliente. |
| Configurazione modulo | Indirizzo(i) email per le notifiche | L'email principale del tuo negozio | Specifica il/i destinatario/i per le notifiche del proprietario (separati da virgola). |
| Configurazione modulo | Invia notifica al cliente se l'amministratore crea un nuovo account | SÌ | Controlla se il cliente riceve un'email di benvenuto quando l'amministratore crea il suo account. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Non ricevo notifiche di nuovi clienti, ma il modulo è abilitato. Cosa dovrei controllare?**
R1:

-   **Controlla gli indirizzi email:** Ricontrolla il campo "Indirizzo(i) email per le notifiche" nella configurazione del modulo. Assicurati che sia inserito correttamente e che non ci siano errori di battitura. Se sono più indirizzi, assicurati che siano separati da virgola.
-   **Cartella spam:** Controlla la cartella spam o posta indesiderata della tua email. Le notifiche potrebbero essere filtrate lì.
-   **Impostazioni email di PrestaShop:** Verifica che le impostazioni email principali del tuo PrestaShop (Parametri avanzati > E-mail) siano configurate correttamente e che le email vengano inviate con successo. Puoi inviare un'email di prova da lì.
-   **Problemi email di hosting:** Contatta il tuo provider di hosting per assicurarti che non ci siano restrizioni di invio email lato server o problemi con il tuo server di posta.

**D2: I miei clienti non ricevono email di benvenuto quando creo i loro account nel Back Office.**
R2:

-   **Impostazione del modulo:** Assicurati che "Invia notifica al cliente se l'amministratore crea un nuovo account" sia impostato su SÌ nella configurazione del modulo.
-   **Email del cliente:** Verifica che l'indirizzo email inserito per il cliente nel Back Office sia corretto e valido.
-   **Cartella spam del cliente:** Consiglia al cliente di controllare la sua cartella spam o posta indesiderata.
-   **Impostazioni email di PrestaShop:** Come sopra, assicurati che le impostazioni email generali del tuo negozio siano funzionanti.

**D3: Posso personalizzare il contenuto delle email di notifica?**
R3: Questo modulo, nella sua versione attuale, invia email di sistema standard di PrestaShop. La personalizzazione del contenuto richiederebbe tipicamente la modifica diretta dei template email di PrestaShop (trovati nella directory `mails/` per la tua lingua) o del codice principale del modulo, cosa non consigliata per i commercianti. Per personalizzazioni avanzate, consulta uno sviluppatore.

**D4: Questo modulo rallenterà il mio negozio?**
R4: No. Questo modulo esegue un'operazione molto leggera (l'invio di un'email) solo quando viene creato un nuovo account cliente. Non aggiunge alcun overhead ai caricamenti delle pagine o alle prestazioni generali del negozio.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster che lavorano con il modulo "Notifica nuovo account cliente".

### 4.1 Panoramica dell'architettura

Il modulo `registernotification` è un modulo PrestaShop standard che segue il modello MVC-like. Sfrutta principalmente il sistema di hook di PrestaShop per intercettare eventi relativi alla registrazione dei clienti e quindi utilizza la classe `Mail` di PrestaShop per inviare notifiche. Memorizza la sua configurazione direttamente nella tabella `ps_configuration`.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller front-office o back-office personalizzati. Tutta la logica è incapsulata all'interno della classe principale del modulo e del suo metodo `getContent()` per la configurazione.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non definisce classi personalizzate o istanze di `ObjectModel`. Tutta la logica principale risiede all'interno della classe principale `registernotification`.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo non include file JavaScript personalizzati.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo non include file CSS personalizzati.

### 4.6 Struttura del template Smarty (`views/templates/`)

Questo modulo non include file di template Smarty personalizzati. Si basa sui template email predefiniti di PrestaShop per le notifiche ai clienti.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    Il modulo non crea tabelle di database personalizzate. Tutte le sue impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` utilizzando chiavi con prefisso `REGISTERNOTIFICATION_`.

    -   Voci `PS_CONFIGURATION`:
        -   `REGISTERNOTIFICATION_SEND_OWNER`: Memorizza il valore booleano (0 o 1) per l'invio di notifiche al proprietario del negozio.
        -   `REGISTERNOTIFICATION_EMAIL_ADDRESSES`: Memorizza la stringa di indirizzi email separati da virgola per le notifiche del proprietario.
        -   `REGISTERNOTIFICATION_SEND_CUSTOMER_ADMIN`: Memorizza il valore booleano (0 o 1) per l'invio di notifiche ai clienti quando creati da un amministratore.
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionCustomerAccountAdd` | Eseguito immediatamente dopo che un nuovo account cliente è stato aggiunto con successo al database. | Questo hook viene utilizzato per attivare la notifica email al proprietario del negozio quando un cliente si registra tramite il front office. Attiva anche l'email di benvenuto al cliente se il suo account è stato creato da un amministratore nel back office. |
| `displayBackOfficeHeader` | Eseguito quando viene renderizzato l'header del Back Office. | Tipicamente utilizzato per aggiungere CSS/JS o visualizzare avvisi nel Back Office. Sebbene elencato come un potenziale hook, il suo uso primario in questo modulo sarebbe per visualizzare un messaggio di successo/errore dopo il salvataggio della configurazione, o potenzialmente per aggiungere risorse specifiche del modulo (anche se nessuna è presente). |

### 4.8 Struttura dei file del modulo (`registernotification/`)

-   `index.php`: Il file principale del modulo. Questo file contiene la classe `registernotification`, che estende `Module`. Gestisce:
    -   `__construct()`: Inizializzazione del modulo, impostazione di nome, scheda, versione, autore, ecc.
    -   `install()`: Registra gli hook necessari (`actionCustomerAccountAdd`, `displayBackOfficeHeader`) e imposta i valori di configurazione predefiniti in `ps_configuration`.
    -   `uninstall()`: Deregistra gli hook ed elimina i valori di configurazione.
    -   `getContent()`: Renderizza il modulo di configurazione del modulo nel Back Office, gestisce l'invio del modulo e aggiorna `ps_configuration`.
    -   `hookActionCustomerAccountAdd($params)`: La logica principale per l'invio di email. Controlla la configurazione del modulo e utilizza `Mail::Send()` per inviare email al proprietario e/o al nuovo cliente in base al contesto di creazione dell'account.
    -   `hookDisplayBackOfficeHeader()`: Potenzialmente utilizzato per visualizzare messaggi di conferma dopo il salvataggio della configurazione.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Notifica nuovo account cliente", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere.
"""
