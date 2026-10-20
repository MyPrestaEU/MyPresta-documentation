---
title: "Punti Fedeltà Manuali e Cronologia - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Punti Fedeltà Manuali e Cronologia di MyPresta.eu."
sidebar:
  label: "Punti Fedeltà Manuali e Cronologia - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Manual Loyalty Points & History su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/manual-loyalty-points-history.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/manual-loyalty-points-history/)
>
> ---


# Punti Fedeltà Manuali e Cronologia

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di Hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL). Questo modulo richiede anche che il sistema di fedeltà principale di PrestaShop (ad esempio, `myprestaloyalty` o il modulo di fedeltà predefinito di PrestaShop) sia installato e attivo, poiché ne estende la funzionalità.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale del modulo, dove puoi impostare le preferenze globali.

- **Abilita notifiche email per modifiche manuali dei punti:**
  - **Cosa fa questa impostazione:** Controlla se i clienti ricevono una notifica email quando i loro punti fedeltà vengono regolati manualmente da un amministratore.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (SÌ):* Dopo aver aggiunto o sottratto manualmente punti per un cliente, verrà inviata un'email al loro indirizzo email registrato, informandoli della modifica e del loro nuovo saldo.
    - *Quando disabilitato (NO):* Nessuna notifica email verrà inviata ai clienti per le regolazioni manuali dei punti.
  - **Valore consigliato:** SÌ
  - **Scenario / esempio del commerciante:** Abilita questa opzione per mantenere i clienti pienamente informati e coinvolti nel loro programma fedeltà. Se un cliente riceve punti come compensazione, una notifica email conferma l'azione e rafforza il tuo servizio clienti. Se disabilitato, i clienti potrebbero non rendersi immediatamente conto che il loro saldo è cambiato.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### 2.2.1 Gestione manuale dei punti fedeltà (Back Office > Moduli > Punti Fedeltà Manuali)

Questa è la schermata principale in cui gestirai e registrerai tutte le regolazioni manuali dei punti fedeltà. Puoi trovare questa schermata navigando su **Moduli > Punti Fedeltà Manuali** nel menu del tuo Back Office PrestaShop.

Questa schermata presenta un elenco di tutte le regolazioni storiche manuali dei punti fedeltà. Puoi anche aggiungere nuove regolazioni da qui.

**Azioni e Impostazioni Disponibili:**

- **Pulsante "Aggiungi nuova regolazione punti fedeltà":**

  - **Cosa fa questo pulsante:** Cliccando questo pulsante si accede a un modulo dove è possibile aggiungere o sottrarre manualmente punti fedeltà per un cliente specifico.
  - **Effetto del clic su questo pulsante:** Apre un nuovo modulo per creare una nuova voce di punti fedeltà.
- **Modulo di regolazione dei punti fedeltà (Accessibile tramite "Aggiungi nuova regolazione punti fedeltà"):**

  - **Campo di ricerca cliente:**

    - **Cosa fa questo campo:** Ti consente di cercare e selezionare il cliente i cui punti fedeltà desideri regolare. Inizia a digitare il nome o l'email del cliente e apparirà un elenco di clienti corrispondenti.
    - **Effetto della modifica di questa impostazione:** Una volta selezionato un cliente, la regolazione verrà applicata al suo account.
    - **Valore consigliato:** Seleziona il cliente corretto.
    - **Scenario / esempio del commerciante:** Devi aggiungere punti per "Mario Rossi". Digita "Mario" e selezionalo dal menu a discesa.
  - **Campo Punti da aggiungere/sottrarre:**

    - **Cosa fa questo campo:** Qui si inserisce il numero di punti fedeltà da regolare.
    - **Effetto della modifica di questa impostazione:**
      - *Numero positivo (es. 50):* Aggiunge 50 punti al saldo fedeltà del cliente.
      - *Numero negativo (es. -25):* Sottrae 25 punti dal saldo fedeltà del cliente.
    - **Valore consigliato:** Il numero esatto di punti che intendi aggiungere o sottrarre.
    - **Scenario / esempio del commerciante:** Un cliente ha ricevuto un articolo danneggiato, quindi aggiungi "100" punti come compensazione. Un altro cliente ha restituito un articolo per il quale aveva guadagnato punti, quindi sottrai "-50" punti.
  - **Campo Periodo di validità (Giorni):**

    - **Cosa fa questo campo:** Definisce per quanti giorni i punti aggiunti manualmente saranno validi dalla data di regolazione. Dopo questo periodo, i punti scadranno.
    - **Effetto della modifica di questa impostazione:**
      - *Impostato su un numero (es. 365):* I punti scadranno dopo 365 giorni.
      - *Impostato su 0 o vuoto:* I punti non avranno una data di scadenza (o seguiranno la scadenza predefinita del tuo modulo di fedeltà principale, se presente).
    - **Valore consigliato:** Considera la strategia complessiva del tuo programma fedeltà. Se vuoi incoraggiare un riscatto rapido, imposta un periodo più breve. Per una buona volontà generale, un periodo più lungo o nessuna scadenza potrebbe essere migliore.
    - **Scenario / esempio del commerciante:** Dai 50 punti come regalo di compleanno, validi per "30" giorni per incoraggiare un acquisto rapido. Per una compensazione importante, potresti lasciarlo vuoto per nessuna scadenza.
  - **Campo Motivo / Commento:**

    - **Cosa fa questo campo:** Un campo di testo per registrare il motivo della regolazione dei punti fedeltà. Questo è per il tracciamento interno e l'audit.
    - **Effetto della modifica di questa impostazione:** Questo testo verrà salvato nel registro fedeltà, fornendo una chiara cronologia del motivo per cui i punti sono stati regolati. Non è visibile al cliente.
    - **Valore consigliato:** Fornisci sempre un motivo chiaro e conciso.
    - **Scenario / esempio del commerciante:** "Compensazione per prodotto danneggiato #12345", "Regalo di compleanno per cliente VIP", "Punti per partecipazione a evento offline".
  - **Pulsante "Salva":**

    - **Cosa fa questo pulsante:** Applica la regolazione dei punti fedeltà all'account del cliente e salva la voce nel registro storico.
    - **Effetto del clic su questo pulsante:** I punti fedeltà del cliente vengono aggiornati e una nuova voce appare nella tabella "Gestione manuale dei punti fedeltà". Se le notifiche email sono abilitate, il cliente riceve un'email.
- **Tabella Cronologia Punti Fedeltà:**

  - **Cosa fa questa tabella:** Visualizza un elenco cronologico di tutte le regolazioni manuali dei punti fedeltà effettuate tramite questo modulo.
  - **Colonne:**
    - **ID:** Identificatore univoco per la voce di registro.
    - **Cliente:** Il nome del cliente i cui punti sono stati regolati.
    - **Punti:** Il numero di punti aggiunti o sottratti.
    - **Validità (Giorni):** Il periodo di scadenza impostato per i punti.
    - **Motivo:** Il commento interno fornito per la regolazione.
    - **Data Aggiunta:** La data e l'ora in cui è stata effettuata la regolazione.
    - **Amministratore:** Il nome dell'amministratore che ha effettuato la regolazione.
  - **Effetto delle modifiche:** Questa tabella fornisce una traccia di audit completa. È possibile ordinare e filtrare le voci per rivedere le regolazioni passate.

**Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

1. Quando si presenta una situazione che richiede una regolazione manuale dei punti (ad esempio, reclamo del cliente, promozione speciale), navigare su **Moduli > Punti Fedeltà Manuali**.
2. Cliccare su "Aggiungi nuova regolazione punti fedeltà".
3. Cercare e selezionare il cliente.
4. Inserire il numero di punti (positivo per aggiungere, negativo per sottrarre).
5. Impostare un periodo di validità se desiderato.
6. Fondamentale, aggiungere un "Motivo / Commento" chiaro per riferimento futuro.
7. Cliccare su "Salva".
8. Rivedere la tabella della cronologia per confermare la voce.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Abilita Notifiche Email | SÌ | Invia email al cliente per modifiche manuali dei punti. |
| Punti Fedeltà Manuali | Ricerca Cliente | N/A | Seleziona il cliente per la regolazione dei punti. |
| Punti Fedeltà Manuali | Punti da Aggiungere/Sottrarre | N/A | Inserisci un valore positivo o negativo per i punti. |
| Punti Fedeltà Manuali | Periodo di Validità (Giorni) | Vuoto (Nessuna Scadenza) | Imposta la scadenza per i punti aggiunti manualmente. |
| Punti Fedeltà Manuali | Motivo / Commento | N/A | Nota interna per la traccia di audit. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho aggiunto punti, ma il cliente dice di non aver ricevuto un'email.**
R: Innanzitutto, verifica se "Abilita notifiche email per modifiche manuali dei punti" è impostato su SÌ nella configurazione del modulo. Se lo è, controlla i registri email del tuo negozio (se disponibili) o i registri di posta del tuo server per vedere se l'email è stata inviata. Inoltre, consiglia al cliente di controllare la sua cartella spam o posta indesiderata. Assicurati che le impostazioni email di PrestaShop siano configurate correttamente e che le email vengano inviate con successo.

**D: Il saldo dei punti fedeltà del cliente non si è aggiornato dopo che ho aggiunto i punti.**
R: Questo modulo aggiorna il sistema di fedeltà principale di PrestaShop. Se il saldo non viene visualizzato, prima svuota la cache di PrestaShop (Parametri Avanzati > Prestazioni > Svuota cache). Se il problema persiste, assicurati che il tuo modulo di fedeltà principale (ad esempio, il modulo di fedeltà predefinito di PrestaShop o `myprestaloyalty`) sia correttamente installato e attivo, poiché questo modulo si basa su di esso.

**D: Posso modificare una regolazione dei punti fedeltà dopo averla salvata?**
R: No, per motivi di audit e integrità dei dati, le singole regolazioni dei punti fedeltà non possono essere modificate una volta salvate. Se hai commesso un errore, dovresti aggiungere una *nuova* regolazione per correggerlo (ad esempio, se hai accidentalmente aggiunto 100 punti invece di 50, aggiungi una nuova voce sottraendo 50 punti) e annota chiaramente la correzione nel campo "Motivo / Commento".

**D: Cosa succede se sottraggo più punti di quanti ne abbia un cliente?**
R: Il sistema di solito consentirà la sottrazione, risultando in un saldo punti fedeltà negativo per il cliente. Questo potrebbe essere utile in scenari specifici, ma in generale, dovresti assicurarti che i clienti abbiano punti sufficienti prima di sottrarre.

**D: Come faccio a sapere chi ha effettuato una specifica regolazione dei punti?**
R: La colonna "Amministratore" nella tabella della cronologia "Gestione manuale dei punti fedeltà" mostra chiaramente quale account amministratore ha effettuato ogni regolazione, fornendo una traccia di audit completa.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo `Punti Fedeltà Manuali e Cronologia` (myprestaloyalty_manual) è progettato come un modulo PrestaShop standard, che estende la funzionalità di fedeltà principale. Opera principalmente all'interno del Back Office, fornendo un'interfaccia amministrativa per le regolazioni manuali dei punti e la registrazione. Sfrutta il modello MVC di PrestaShop per il suo controller amministrativo e utilizza un `ObjectModel` per l'archiviazione persistente delle voci di registro manuali. Il modulo si integra con il sistema di fedeltà esistente manipolando direttamente i punti fedeltà del cliente.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**: Questo modulo non include alcun controller front-office dedicato. Tutta la visualizzazione dei punti fedeltà rivolta al cliente è gestita dal modulo di fedeltà principale.
- **Controller Admin Back-Office**:

  - `controllers/admin/AdminMyprestaloyaltyManualController.php`

    - **Nome classe e classe padre**: `AdminMyprestaloyaltyManualController` estende `ModuleAdminController`.
    - **Responsabilità**: Questo è il controller amministrativo principale per la gestione delle regolazioni manuali dei punti fedeltà. Gestisce la visualizzazione dell'elenco del registro fedeltà (utilizzando `HelperList`) e il modulo per l'aggiunta di nuove regolazioni (utilizzando `HelperForm`). Elabora le sottomissioni del modulo, convalida i dati, crea oggetti `MyprestaloyaltyManualLog` e aggiorna i punti fedeltà del cliente. Attiva anche le notifiche email se abilitate.
    - **Nome scheda**: "Punti Fedeltà Manuali" (sotto il menu Moduli).
    - **Entità gestita**: `MyprestaloyaltyManualLog` (il registro delle regolazioni manuali).
  - `controllers/admin/index.php`

    - **Responsabilità**: Questo è un file segnaposto vuoto, spesso incluso nelle directory `controllers/admin` dei moduli PrestaShop per prevenire l'elenco delle directory. Non contiene alcuna logica di controller funzionale.

### 4.3 Classi e modelli principali (`classes/`)

- `classes/index.php`

  - **Responsabilità**: File segnaposto vuoto per prevenire l'elenco delle directory.
- `classes/MyprestaloyaltyManualLog.php`

  - **Con quale tabella del database interagisce**: `ps_myprestaloyalty_manual_log`
  - **Estende `ObjectModel`**: Sì.
  - **Campi `$definition`**:
    - `id_myprestaloyalty_manual_log`: Chiave primaria.
    - `id_customer`: ID del cliente interessato.
    - `points`: Numero di punti regolati (può essere positivo o negativo).
    - `validity`: Periodo di validità in giorni per i punti.
    - `reason`: Motivo testuale della regolazione.
    - `id_employee`: ID dell'amministratore che ha effettuato la regolazione.
    - `date_add`: Timestamp di quando la voce è stata aggiunta.
  - **Metodi pubblici chiave e logica di business incapsulata**:
    - Metodi `ObjectModel` standard (`add`, `update`, `delete`).
    - Gestisce la convalida dei dati per i suoi campi.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo non include alcun file JavaScript personalizzato. Vengono utilizzati i JS standard di PrestaShop per la gestione dei moduli e AJAX (ad esempio, la ricerca clienti).

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo non include alcun file CSS personalizzato. Si basa sullo stile predefinito del Back Office di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

Questo modulo non include alcun file di template Smarty personalizzato. Si basa sui template predefiniti `HelperList` e `HelperForm` di PrestaShop per la sua interfaccia Back Office.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - `ps_myprestaloyalty_manual_log`:
    - `id_myprestaloyalty_manual_log` INT(10) UNSIGNED NOT NULL AUTO_INCREMENT
    - `id_customer` INT(10) UNSIGNED NOT NULL
    - `points` INT(10) NOT NULL
    - `validity` INT(10) UNSIGNED DEFAULT 0
    - `reason` TEXT NULL
    - `id_employee` INT(10) UNSIGNED NOT NULL
    - `date_add` DATETIME NOT NULL
    - PRIMARY KEY (`id_myprestaloyalty_manual_log`)
    - KEY `id_customer` (`id_customer`)
- **Record di configurazione (in `ps_configuration`)**:

  - `PS_LOYALTY_MANUAL_EMAIL_ENABLED`: Memorizza il valore booleano (0 o 1) per abilitare/disabilitare le notifiche email.
- **Tabella degli hook registrati**:

  | Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
  | --- | --- | --- |
  | `displayBackOfficeHeader` | Rende il contenuto nella sezione `<head>` del Back Office. | Utilizzato per includere CSS/JS specifici del modulo (anche se questo modulo non ne ha) o per registrare voci di menu admin. |
  | `actionCustomerAccountAdd` | Dopo la creazione di un nuovo account cliente. | Non esplicitamente utilizzato da questo modulo, ma un hook di fedeltà comune. |
  | `actionValidateOrder` | Dopo che un ordine è stato validato con successo. | Non esplicitamente utilizzato da questo modulo, ma un hook di fedeltà comune. |
  | `actionObjectCustomerUpdateAfter` | Dopo l'aggiornamento di un oggetto cliente. | Non esplicitamente utilizzato da questo modulo. |
  | `actionObjectCustomerDeleteAfter` | Dopo l'eliminazione di un oggetto cliente. | Non esplicitamente utilizzato da questo modulo. |

  *Nota: La funzionalità principale del modulo (aggiungere/sottrarre punti) viene attivata direttamente dal suo Controller Admin, non tramite hook front-office. Il modulo interagisce con i metodi del sistema di fedeltà principale per regolare i punti.*

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Punti Fedeltà Manuali e Cronologia", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere con qualsiasi problema o domanda riguardante la funzionalità del modulo.
