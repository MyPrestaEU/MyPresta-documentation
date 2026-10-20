---
title: "Banca Nazionale Ungherese (MNB) - tassi di cambio valuta - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Banca Nazionale Ungherese (MNB) - tassi di cambio valuta' di MyPresta.eu."
sidebar:
  label: "Banca Nazionale Ungherese (MNB) - tassi di cambio valuta - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Hungarian National Bank (MNB) - currency exchange rates su MyPresta.eu](https://mypresta.eu/modules/administration-tools/hungarian-national-bank-mnb-currency-exchange-rates.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/hungarian-national-bank-mnb-currency-exchange-rates/)
>
> ---


# Banca Nazionale Ungherese (MNB) - tassi di cambio valuta

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per la comunicazione API esterna, che è comune per i moduli di tassi di cambio. Assicurati che il tuo ambiente di hosting le supporti.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" verrai indirizzato alla schermata di configurazione principale del modulo. Qui è dove imposti come il modulo recupera e applica i tassi di cambio.

#### **Impostazioni e Opzioni**

La pagina di configurazione del modulo "Banca Nazionale Ungherese (MNB) - tassi di cambio valuta" presenterà tipicamente un modulo con varie opzioni per controllare il suo comportamento. Sebbene i nomi specifici dei campi possano variare leggermente, la funzionalità principale ruota attorno all'abilitazione del processo di aggiornamento e alla sua potenziale pianificazione.

1.  **Abilita aggiornamenti tassi di cambio MNB**

    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare gli aggiornamenti automatici dei tassi di cambio dalla Banca Nazionale Ungherese.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* Il modulo recupererà periodicamente gli ultimi tassi di cambio dalla MNB e li applicherà alle valute configurate del tuo negozio. Questo assicura che i tuoi prezzi siano sempre aggiornati.
        -   *Quando disabilitato (NO):* Il modulo smetterà di recuperare e applicare i tassi di cambio MNB. I tassi di cambio del tuo negozio rimarranno come erano stati impostati l'ultima volta (manualmente o dal modulo prima che fosse disabilitato).
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio del commerciante:** Se vuoi che il tuo negozio rifletta automaticamente gli ultimi tassi di cambio MNB per HUF, EUR, USD, ecc., devi abilitare questa impostazione. Se preferisci gestire i tassi manualmente o utilizzare un sistema diverso, dovresti disabilitarla.
2.  **URL Cron Job (per aggiornamenti automatici)**

    -   **Cosa fa questa impostazione:** Questo campo visualizza un URL unico che puoi utilizzare per impostare un "cron job" sul tuo server web. Un cron job è un'attività pianificata che dice al tuo server di visitare questo URL a intervalli regolari, attivando il modulo per aggiornare automaticamente i tassi di cambio.
    -   **Effetto della modifica di questa impostazione:** Questa non è un'impostazione che modifichi direttamente, ma piuttosto un URL che copi.
        -   *Quando il cron job è impostato:* Il tuo server chiamerà periodicamente questo URL, e il modulo eseguirà il suo processo di aggiornamento in background senza che tu debba fare nulla.
        -   *Quando il cron job NON è impostato:* Dovresti visitare manualmente questo URL nel tuo browser (o cliccare un pulsante "Esegui aggiornamento ora" se disponibile) per attivare un aggiornamento. Questo non è raccomandato per un uso regolare.
    -   **Valore consigliato:** Copia questo URL e imposta un cron job sul tuo pannello di hosting (es. cPanel, Plesk o riga di comando del server) per eseguirlo almeno una volta al giorno, o più frequentemente se la tua attività lo richiede.
    -   **Scenario / esempio del commerciante:** Vuoi che i tuoi tassi di cambio si aggiornino ogni mattina alle 3 AM. Copieresti questo URL, andresti alla sezione "Cron Jobs" del tuo pannello di controllo hosting e creeresti un nuovo cron job che esegue `wget -O /dev/null -q "IL_TUO_URL_CRON_JOB_QUI"` (o comando simile) ogni giorno alle 3 AM.
3.  **Ora ultimo aggiornamento** (Visualizzazione informativa)

    -   **Cosa fa questa impostazione:** Questo è un campo di sola visualizzazione che ti mostra quando i tassi di cambio sono stati aggiornati con successo l'ultima volta dal modulo.
    -   **Effetto della modifica di questa impostazione:** Questa non è un'impostazione configurabile. Fornisce semplicemente un feedback sull'attività del modulo.
    -   **Valore consigliato:** N/A (informativo)
    -   **Scenario / esempio del commerciante:** Puoi controllare rapidamente questo timestamp per confermare che il tuo cron job sta funzionando correttamente e che i tassi vengono aggiornati come previsto. Se l'ora è vecchia, indica un problema con la configurazione del tuo cron job.

#### **Tabella di riferimento rapido della configurazione**

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Abilita aggiornamenti tassi di cambio MNB | SÌ | Attiva/disattiva il recupero e l'applicazione automatici dei tassi di cambio MNB. |
| Configurazione Modulo | URL Cron Job | N/A (Copia e Configura) | URL per impostare un'attività pianificata (cron job) per gli aggiornamenti automatici dei tassi. |
| Configurazione Modulo | Ora ultimo aggiornamento | N/A (Informativo) | Visualizza il timestamp dell'ultimo aggiornamento riuscito dei tassi di cambio. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei tassi di cambio non si aggiornano. Cosa devo fare?**
R1:

1.  **Controlla "Abilita aggiornamenti tassi di cambio MNB":** Assicurati che questa impostazione sia impostata su SÌ nella configurazione del modulo.
2.  **Verifica la configurazione del Cron Job:** La ragione più comune per i mancati aggiornamenti è un cron job configurato in modo errato.
    -   Assicurati di aver copiato l'esatto "URL Cron Job" dal modulo.
    -   Controlla il tuo pannello di controllo hosting (cPanel, Plesk, ecc.) per le impostazioni del cron job.
    -   Conferma che il comando sia corretto (es. `wget -O /dev/null -q "IL_TUO_URL_CRON_JOB"`).
    -   Controlla la pianificazione (es. `* * * * *` per ogni minuto, `0 3 * * *` per le 3 AM giornaliere).
    -   Cerca eventuali log di errore relativi al cron job nel tuo pannello di hosting.
3.  **Controlla "Ora ultimo aggiornamento":** Se questo timestamp è vecchio, conferma che il cron job non è in esecuzione.
4.  **Connettività del server:** Assicurati che il tuo server possa effettuare connessioni in uscita a siti web esterni (come l'API MNB). A volte firewall o impostazioni di sicurezza possono bloccare questo. Contatta il tuo provider di hosting se sospetti questo.

**D2: Ho abilitato il modulo, ma alcune valute non si aggiornano.**
R2:

1.  **Attivazione valuta:** Vai su **Internazionale > Valute** nel tuo Back Office di PrestaShop. Assicurati che le valute che ti aspetti vengano aggiornate siano abilitate (attive). Il modulo aggiorna solo le valute attive.
2.  **Supporto MNB:** La MNB fornisce tassi per valute specifiche. Se una valuta non è supportata dalla MNB, il modulo non può aggiornarla. Potrebbe essere necessario impostare manualmente i tassi per tali valute o utilizzare un altro modulo per esse.

**D3: Il mio tema personalizzato non visualizza correttamente i prezzi dopo l'aggiornamento.**
R3: Questo modulo aggiorna principalmente i *dati* (tassi di cambio) nel database di PrestaShop. Non influisce direttamente su come i prezzi vengono *visualizzati* dal tuo tema. Se riscontri problemi di visualizzazione:

1.  **Svuota la cache di PrestaShop:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty").
2.  **Personalizzazione del tema:** Se il tuo tema ha una logica di visualizzazione dei prezzi fortemente personalizzata, potrebbe interferire. Controlla la documentazione del tuo tema o contatta lo sviluppatore del tuo tema.
3.  **Cache del browser:** Chiedi ai tuoi clienti di svuotare la cache del loro browser o di provare un browser diverso per escludere problemi di caching lato client.

**D4: Posso sovrascrivere manualmente un tasso di cambio dopo che il modulo lo ha aggiornato?**
R4: Sì, puoi. Dopo l'esecuzione del modulo, i tassi vengono memorizzati nel database di PrestaShop. Puoi andare su **Internazionale > Valute**, modificare una valuta specifica e regolare manualmente il suo tasso di cambio. Tuttavia, tieni presente che la prossima volta che il cron job verrà eseguito, il modulo sovrascriverà le tue modifiche manuali con gli ultimi dati MNB. Se hai bisogno di un controllo manuale permanente su una valuta specifica, potresti considerare di disabilitare gli aggiornamenti del modulo per quella valuta (se il modulo offre un'impostazione così granulare, cosa rara) o di disabilitare completamente il modulo e gestire tutti i tassi manualmente.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Banca Nazionale Ungherese (MNB) - tassi di cambio valuta" segue un'architettura standard dei moduli PrestaShop, concentrandosi principalmente sull'elaborazione in background. Sfrutta la classe `Module` di PrestaShop per l'installazione e la configurazione, e `ModuleFrontController` per la gestione dell'esecuzione del cron job. La logica principale prevede l'invio di una richiesta HTTP all'API ufficiale dei tassi di cambio della MNB (probabilmente un feed XML), l'analisi della risposta e quindi l'aggiornamento della tabella `ps_currency` nel database di PrestaShop.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `mnbrates/controllers/front/cronjob.php`
        -   **Nome classe e classe padre**: `MnbratesCronjobModuleFrontController` che estende `ModuleFrontController`
        -   **Responsabilità**: Questo controller è il punto di ingresso per il cron job pianificato. Quando il suo URL viene acceduto (es. `iltuonegozio.com/module/mnbrates/cronjob`), attiva la logica principale del modulo per recuperare e aggiornare i tassi di cambio. Tipicamente gestisce la richiesta HTTP, chiama il metodo di aggiornamento del modulo principale e restituisce un semplice messaggio di successo/fallimento o nessun output (per l'esecuzione silenziosa del cron).
    -   `mnbrates/controllers/front/index.php`
        -   **Nome classe e classe padre**: `MnbratesIndexModuleFrontController` che estende `ModuleFrontController`
        -   **Responsabilità**: Questo è un controller segnaposto standard spesso incluso nei moduli. In molti casi, potrebbe semplicemente reindirizzare alla homepage o servire come fallback. Per questo modulo specifico, il suo scopo principale è probabilmente quello di prevenire l'elenco delle directory se qualcuno tenta di accedere direttamente a `/module/mnbrates/`, oppure potrebbe essere un file vestigiale. È improbabile che contenga la logica di business principale per gli aggiornamenti dei tassi di cambio.
-   **Controller Admin Back-Office**:

    -   Nessun controller admin dedicato (`controllers/admin/`) è identificato. Ciò significa che tutta la configurazione del back-office è gestita direttamente all'interno del metodo `getContent()` del file del modulo principale.

### 4.3 Classi e Modelli Core (`classes/`)

Nessuna classe o modello personalizzato è identificato nella directory `classes/`. Ciò suggerisce che il modulo probabilmente esegue le sue operazioni direttamente all'interno del file del modulo principale `cronjob.php`, potenzialmente utilizzando l'`ObjectModel` `Currency` di PrestaShop per aggiornare i tassi.

### 4.4 Risorse JavaScript (`views/js/`)

Nessun file JavaScript è identificato. Ciò conferma la natura del modulo focalizzata sul backend, senza componenti front-office interattivi o moduli back-office complessi che richiedono JS dinamico.

### 4.5 Fogli di stile CSS (`views/css/`)

Nessun file CSS è identificato. Ciò indica che il modulo non introduce alcuno stile personalizzato né per il front-office né per il back-office. La configurazione del back-office erediterà gli stili del tema admin predefinito di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template Admin (`views/templates/admin/`)**:
    -   `mnbrates/views/admin.tpl`
        -   **Scopo**: Questo template viene renderizzato dal metodo `getContent()` del file del modulo principale (`mnbrates/cronjob.php`). Definisce la struttura e il contenuto della pagina di configurazione del modulo nel Back Office di PrestaShop. Conterrà gli elementi del modulo per abilitare/disabilitare gli aggiornamenti, visualizzare l'URL del cron job e mostrare il timestamp dell'ultimo aggiornamento.
-   **Template Hook (`views/templates/hook/`)**: Nessuno identificato.
-   **Template Front-office (`views/templates/front/`)**: Nessuno identificato.

### 4.7 Schema del database e Mappa degli Hook

-   **Tabelle del database**:

    -   Il modulo non crea tabelle SQL personalizzate. Interagisce con la tabella `ps_currency` di PrestaShop per aggiornare il campo `conversion_rate` per ogni valuta.
    -   Le impostazioni di configurazione (come `PS_MNBRATES_ENABLED`, `PS_MNBRATES_LAST_UPDATE`) sono memorizzate nella tabella `ps_configuration`.
-   **Tabella degli Hook registrati**:
    Il modulo probabilmente registra gli hook durante il suo metodo `install()`. Data la sua funzionalità, l'hook più cruciale è per il cron job, che è gestito da un front controller. Altri hook potrebbero essere a scopo informativo o per garantire la compatibilità.

| Nome Hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Renderizza nella sezione `<head>` di tutte le pagine del front-office. | Improbabile che venga utilizzato per la logica principale, forse per aggiungere un meta tag o un JS/CSS molto semplice (anche se nessuno identificato). |
| `displayRightColumn` | Renderizza nella colonna destra delle pagine dove è disponibile. | Improbabile che venga utilizzato per la logica principale, forse per un piccolo blocco informativo se il modulo avesse un componente front-office. |
| `displayLeftColumn` | Renderizza nella colonna sinistra delle pagine dove è disponibile. | Simile a `displayRightColumn`. |
| `displayFooter` | Renderizza nel piè di pagina di tutte le pagine del front-office. | Simile a `displayHeader`, ma in fondo. |
| `displayProductExtraContent` | Renderizza contenuto aggiuntivo nella pagina del prodotto. | Improbabile per questo modulo. |
| `actionModuleInstall` | Eseguito quando un modulo viene installato. | Registra gli hook necessari e imposta i valori di configurazione predefiniti. |
| `actionModuleUninstall` | Eseguito quando un modulo viene disinstallato. | Pulisce i valori di configurazione e deregistra gli hook. |
| `actionModuleUpdate` | Eseguito quando un modulo viene aggiornato. | Gestisce le modifiche dello schema o le migrazioni di configurazione tra le versioni. |
| (Implicito) `frontController` dispatch | Quando si accede a `mnbrates/controllers/front/cronjob.php`. | Attiva la logica principale di aggiornamento dei tassi di cambio. Questo è l'“hook” primario per il cron job. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo "Banca Nazionale Ungherese (MNB) - tassi di cambio valuta", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team è dedicato a garantire che il tuo modulo funzioni in modo ottimale e che il tuo negozio benefici delle funzionalità e della compatibilità più recenti.
