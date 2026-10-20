---
title: "Banca Nazionale Slovacca (NBS) - tassi di cambio - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop \"Banca Nazionale Slovacca (NBS) - tassi di cambio\" di MyPresta.eu."
sidebar:
  label: "Banca Nazionale Slovacca (NBS) - tassi di cambio - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo The National Bank of Slovakia (NBS) - currency rates su MyPresta.eu](https://mypresta.eu/modules/administration-tools/the-national-bank-of-slovakia-nbs-currency-rates.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/the-national-bank-of-slovakia-nbs-currency-rates/)
>
> ---


# Banca Nazionale Slovacca (NBS) - tassi di cambio

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per il recupero di dati esterni, e sono quasi universalmente disponibili negli ambienti di hosting moderni.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al nome del modulo per accedere alle sue impostazioni.

#### **1. Abilita / Disabilita Modulo**

-   **Cosa fa questa impostazione:** Questo è un interruttore standard di PrestaShop per attivare o disattivare la funzionalità principale del modulo.
-   **Effetto della modifica di questa impostazione:**
    *   *Quando abilitato:* Il modulo inizierà a recuperare e aggiornare i tassi di cambio in base alle tue impostazioni.
    *   *Quando disabilitato:* Il modulo interromperà tutte le operazioni e i tuoi tassi di cambio non saranno più aggiornati automaticamente dai dati NBS.
-   **Valore consigliato:** **SÌ** (per abilitare la funzionalità del modulo).
-   **Scenario / esempio del commerciante:** Se desideri interrompere temporaneamente gli aggiornamenti automatici (ad esempio, durante la manutenzione o se passi alla gestione manuale dei tassi), puoi disabilitarlo. Altrimenti, mantienilo abilitato per aggiornamenti continui.

#### **2. URL CRON per aggiornamenti automatici**

-   **Cosa fa questa impostazione:** Visualizza un URL unico che devi impostare come "cron job" sul tuo server di hosting web. Un cron job è un'attività pianificata che indica al tuo server di visitare questo URL a intervalli regolari, attivando il modulo per recuperare e aggiornare automaticamente gli ultimi tassi di cambio NBS.
-   **Effetto della modifica di questa impostazione:**
    *   *Se configurato correttamente come cron job:* I tuoi tassi di cambio verranno aggiornati automaticamente senza alcun intervento manuale.
    *   *Se non configurato come cron job:* Il modulo non aggiornerà i tassi automaticamente. Dovresti visitare manualmente questo URL nel tuo browser per attivare un aggiornamento (il che vanifica lo scopo dell'automazione).
-   **Valore consigliato:** Questo è un URL generato. Dovresti **copiare questo URL** e incollarlo nello scheduler dei cron job del tuo pannello di controllo hosting.
-   **Scenario / esempio del commerciante:** Vuoi che i tuoi tassi di cambio si aggiornino ogni giorno alle 3 del mattino. Copieresti questo URL, andresti al tuo pannello di hosting (ad esempio, cPanel, Plesk, o chiedi aiuto al tuo host) e creeresti un cron job che esegue questo URL quotidianamente alle 3 del mattino.

#### **3. Aggiungi margine percentuale ai tassi di cambio**

-   **Cosa fa questa impostazione:** Ti consente di aggiungere un valore percentuale in aggiunta ai tassi di cambio ufficiali recuperati dalla NBS. Questo margine viene applicato a tutte le valute aggiornate dal modulo.
-   **Effetto della modifica di questa impostazione:**
    *   *Se impostato a 0 (o lasciato vuoto):* I tuoi tassi di cambio saranno esattamente quelli forniti dalla NBS.
    *   *Se impostato su un valore positivo (ad esempio, 2):* Il modulo aumenterà il tasso di cambio NBS di quella percentuale (ad esempio, se il tasso è 1 EUR = 1.10 USD, con un margine del 2%, diventa 1 EUR = 1.122 USD). Questo rende i tuoi prodotti leggermente più costosi se pagati nella valuta non base.
-   **Valore consigliato:** **0** (se desideri tassi NBS esatti) o una piccola percentuale positiva (ad esempio, **1-3%**) per coprire le commissioni di transazione o la volatilità del mercato.
-   **Scenario / esempio del commerciante:** Vuoi tenere conto di potenziali commissioni bancarie durante la conversione dei pagamenti o semplicemente desideri un piccolo buffer sulle tue vendite internazionali. Impostando questo valore su "2" aggiungerà un margine del 2% a tutti i tassi di cambio aggiornati.

#### **4. Aggiorna solo le valute selezionate**

-   **Cosa fa questa impostazione:** Questa opzione ti consente di scegliere valute specifiche nel tuo negozio PrestaShop che dovrebbero essere aggiornate dal modulo NBS. Se hai molte valute ma vuoi che NBS ne gestisca solo alcune, questo è utile.
-   **Effetto della modifica di questa impostazione:**
    *   *Se deselezionato:* Il modulo tenterà di aggiornare tutte le valute attive nel tuo negozio PrestaShop che hanno un tasso corrispondente disponibile dalla NBS.
    *   *Se selezionato e sono state scelte valute specifiche:* Solo le valute scelte avranno i loro tassi di cambio aggiornati dal modulo. Altre valute manterranno i loro tassi esistenti (manuali o da altre fonti).
-   **Valore consigliato:** **Seleziona questa casella** e scegli solo le valute che gestisci attivamente con i dati NBS. Questo previene modifiche indesiderate ad altre valute.
-   **Scenario / esempio del commerciante:** La tua valuta base è EUR e vendi anche in USD e CZK. Vuoi che NBS aggiorni i tassi USD e CZK, ma gestisci manualmente i tassi GBP. Selezioneresti questa casella e sceglieresti solo USD e CZK dall'elenco.

#### **5. Elenco delle valute da aggiornare**

-   **Cosa fa questa impostazione:** Questo è un elenco a selezione multipla che appare solo se "Aggiorna solo le valute selezionate" è selezionato. Mostra tutte le valute attive nel tuo negozio PrestaShop, permettendoti di scegliere quali il modulo dovrebbe aggiornare.
-   **Effetto della modifica di questa impostazione:**
    *   *Selezione delle valute:* Queste valute avranno i loro tassi di cambio aggiornati automaticamente dal modulo NBS.
    *   *Deselezione delle valute:* Queste valute verranno ignorate dal modulo NBS e i loro tassi non verranno modificati.
-   **Valore consigliato:** Seleziona tutte le valute per le quali desideri utilizzare i tassi NBS.
-   **Scenario / esempio del commerciante:** Seguendo l'esempio precedente, cliccheresti su "USD" e "CZK" in questo elenco per assicurarti che solo quelle vengano aggiornate.

#### **6. Pulsante Salva**

-   **Cosa fa questa impostazione:** Applica tutte le modifiche che hai apportato nella pagina di configurazione.
-   **Effetto della modifica di questa impostazione:** Le impostazioni del tuo modulo verranno salvate e avranno effetto immediatamente (per le future esecuzioni del cron job o gli aggiornamenti manuali).
-   **Valore consigliato:** Clicca sempre su **"Salva"** dopo aver apportato qualsiasi modifica.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Abilita / Disabilita Modulo | SÌ | Attiva/disattiva la funzionalità del modulo. |
| Configurazione modulo | URL CRON per aggiornamenti automatici | URL generato | Copia e configura come cron job per aggiornamenti automatici dei tassi. |
| Configurazione modulo | Aggiungi margine percentuale ai tassi di cambio | 0 (o 1-3%) | Aggiunge un buffer percentuale ai tassi NBS per la strategia di prezzo. |
| Configurazione modulo | Aggiorna solo le valute selezionate | Seleziona e scegli | Limita gli aggiornamenti NBS a valute specifiche scelte. |
| Configurazione modulo | Elenco delle valute da aggiornare | Seleziona quelle desiderate | Scegli quali valute attive ricevono gli aggiornamenti dei tassi NBS. |
| Configurazione modulo | Pulsante Salva | Clicca dopo le modifiche | Salva tutte le impostazioni di configurazione del modulo. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei tassi di cambio non si aggiornano automaticamente. Cosa devo fare?**
R:

1.  **Controlla lo stato del modulo:** Assicurati che il modulo sia abilitato in **Moduli > Gestione moduli**.
2.  **Verifica il Cron Job:** Il problema più comune è un cron job configurato in modo errato.
    *   Torna alla pagina di configurazione del modulo e copia di nuovo l'"URL CRON".
    *   Accedi al tuo pannello di controllo hosting (cPanel, Plesk, ecc.) e vai alla sezione "Cron Jobs" o "Attività pianificate".
    *   Ricontrolla che l'URL sia esattamente quello fornito dal modulo e che la pianificazione (ad esempio, giornaliera, oraria) sia corretta.
    *   Assicurati che il comando utilizzi `wget` o `curl` per eseguire l'URL (ad esempio, `wget -O /dev/null "IL_TUO_URL_CRON_QUI"`).
    *   Se non sei sicuro, contatta il supporto del tuo provider di hosting con l'URL CRON e chiedi loro di configurarlo per te.
3.  **Controlla i log del server:** Il tuo provider di hosting potrebbe avere log per l'esecuzione dei cron job che possono indicare se c'è un errore.

**D2: Il modulo è abilitato, ma alcune valute non si aggiornano.**
R:

1.  **Controlla "Aggiorna solo le valute selezionate":** Vai alla configurazione del modulo. Se "Aggiorna solo le valute selezionate" è selezionato, assicurati che le valute specifiche che ti aspetti vengano aggiornate siano selezionate nell'"Elenco delle valute da aggiornare".
2.  **Disponibilità dei dati NBS:** La Banca Nazionale Slovacca potrebbe non fornire tassi per tutte le valute. Il modulo può aggiornare solo le valute per le quali NBS pubblica i dati. Controlla il sito web ufficiale della NBS per le coppie di valute disponibili.
3.  **Stato della valuta PrestaShop:** Assicurati che le valute in questione siano attive nel tuo negozio PrestaShop (**Internazionale > Valute**). Le valute inattive non possono essere aggiornate.

**D3: Con quale frequenza dovrei eseguire il cron job?**
R: Per la maggior parte dei negozi, eseguire il cron job una volta al giorno è sufficiente per mantenere i tassi aggiornati. Se la tua attività richiede tassi estremamente in tempo reale a causa di transazioni internazionali ad alto volume o mercati volatili, potresti impostarlo per l'esecuzione più frequentemente (ad esempio, ogni 6 o 12 ore), ma giornalmente è generalmente adeguato.

**D4: Ho aggiunto un margine, ma i prezzi non sembrano rifletterlo.**
R:

1.  **Salva le impostazioni:** Assicurati di aver cliccato il pulsante "Salva" dopo aver impostato il margine.
2.  **Attiva l'aggiornamento:** Il margine si applicherà solo quando i tassi di cambio verranno aggiornati. Questo accadrà con la prossima esecuzione del tuo cron job, oppure puoi attivare manualmente un aggiornamento visitando l'URL CRON nel tuo browser.
3.  **Svuota la cache:** A volte, la cache di PrestaShop potrebbe contenere valori vecchi. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti).

**D5: Questo modulo influenzerà la mia valuta base?**
R: No, il modulo aggiorna i tassi di cambio *relativamente* alla tua valuta base. Il valore della tua valuta base rimane costante. Ad esempio, se la tua valuta base è EUR, il modulo aggiornerà quanti USD o CZK equivalgono a 1 EUR.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Banca Nazionale Slovacca (NBS) - tassi di cambio" segue un'architettura standard per i moduli PrestaShop, sfruttando principalmente una classe di modulo principale (`cronjob.php`) per la configurazione e la gestione degli hook, e un controller frontale (`cronjob.php`) per gestire l'esecuzione del cron job. Interagisce con la gestione delle valute core di PrestaShop per aggiornare i tassi. La funzione principale del modulo è recuperare dati esterni (tassi NBS) e integrarli nel modello oggetto `Currency` di PrestaShop.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `controllers/front/cronjob.php`
        -   **Nome classe e classe padre:** `NbsratesCronjobModuleFrontController` che estende `ModuleFrontController`.
        -   **Responsabilità:** Questo controller è specificamente progettato per essere chiamato da un cron job. Quando viene richiamato, avvia il processo di recupero degli ultimi tassi di cambio dalla Banca Nazionale Slovacca e li aggiorna nel database di PrestaShop. Non produce alcun output visivo nel browser ma esegue l'elaborazione in background. Gestisce la logica per l'applicazione del margine percentuale configurato e l'aggiornamento solo delle valute selezionate.
    -   `controllers/front/index.php`
        -   **Nome classe e classe padre:** Questo è tipicamente un file vuoto o un segnaposto, spesso utilizzato per prevenire l'elenco delle directory o per garantire un punto di ingresso valido per le versioni precedenti di PrestaShop. Non contiene logica specifica del modulo per i tassi NBS.
-   **Controller Admin Back-Office**: Nessuno. Tutta l'amministrazione è gestita tramite il metodo `getContent()` del modulo principale.

### 4.3 Classi e modelli core (`classes/`)

Il modulo non definisce classi `ObjectModel` personalizzate. Interagisce direttamente con la classe `Currency` core di PrestaShop per aggiornare i tassi di cambio.

### 4.4 Risorse JavaScript (`views/js/`)

Nessuno. Il modulo non include alcun file JavaScript personalizzato.

### 4.5 Fogli di stile CSS (`views/css/`)

Nessuno. Il modulo non include alcun file CSS personalizzato.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template Admin (`views/templates/admin/`)**:
    -   `views/templates/admin/admin.tpl`
        -   **Scopo:** Questo template viene renderizzato quando si accede alla pagina di configurazione del modulo nel Back Office di PrestaShop. Visualizza i campi di input per abilitare/disabilitare il modulo, l'URL CRON, la percentuale di margine e le opzioni di selezione della valuta. Utilizza gli helper e gli elementi standard dei moduli di PrestaShop.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    Il modulo non crea tabelle SQL personalizzate. Memorizza le sue impostazioni di configurazione nella tabella `ps_configuration` di PrestaShop.

    -   `PS_NBS_RATES_ENABLED`: Memorizza lo stato abilitato/disabilitato del modulo.
    -   `PS_NBS_RATES_MARGIN`: Memorizza il margine percentuale da applicare.
    -   `PS_NBS_RATES_SELECTED_CURRENCIES`: Memorizza un array serializzato di ID di valuta se "Aggiorna solo le valute selezionate" è attivo.
    -   `PS_NBS_RATES_CRON_TOKEN`: Memorizza un token unico per l'URL del cron per motivi di sicurezza.
-   **Tabella degli hook registrati**:
    Il modulo utilizza principalmente l'hook `actionFrontControllerSetMedia` (implicitamente, se dovesse caricare risorse, anche se non lo fa) e si basa sui suoi metodi `install()` e `uninstall()` per la configurazione e la pulizia. La sua funzionalità principale è attivata dal controller frontale `cronjob.php` piuttosto che da un tradizionale hook di PrestaShop.

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `install()` | Durante l'installazione del modulo | Imposta i valori di configurazione predefiniti in `ps_configuration` e registra il modulo. |
| `uninstall()` | Durante la disinstallazione del modulo | Pulisce i valori di configurazione da `ps_configuration`. |
| (Cron Job) | Richiesta HTTP esterna a `controllers/front/cronjob.php` | Recupera i tassi NBS, applica il margine e aggiorna la tabella `ps_currency`. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Banca Nazionale Slovacca (NBS) - tassi di cambio", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda relativa alla funzionalità e alla configurazione del modulo.
