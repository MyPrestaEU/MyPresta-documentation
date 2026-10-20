---
title: "Perfect Money - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo Perfect Money PrestaShop di MyPresta.eu."
sidebar:
  label: "Perfect Money - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Perfect Money su MyPresta.eu](https://mypresta.eu/modules/payment-process/perfect-money.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/payment/perfect-money/)
>
> ---


# Perfect Money

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 1.6.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per una comunicazione sicura con il gateway di pagamento, e sono quasi sempre disponibili negli ambienti di hosting moderni.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Perfect Money)

Questa è la schermata di configurazione principale per il modulo Perfect Money, dove inserirai i dettagli del tuo account Perfect Money e imposterai come il metodo di pagamento appare e funziona nel tuo negozio.

#### **Impostazioni account Perfect Money**

-   **Cosa fa questa impostazione:** Questi campi sono cruciali per connettere il tuo negozio PrestaShop al tuo account commerciante Perfect Money. Dicono al modulo a quale account Perfect Money inviare i pagamenti e come verificare le transazioni.
-   **Effetto della modifica di questa impostazione:** Valori errati impediranno ai clienti di effettuare pagamenti, o i pagamenti potrebbero non essere correttamente attribuiti al tuo account.
    -   *Quando configurato correttamente:* I pagamenti verranno elaborati con successo tramite il tuo account Perfect Money.
    -   *Quando configurato in modo errato:* I pagamenti falliranno, o i clienti incontreranno errori durante il checkout.
-   **Valore consigliato:** Inserisci i dettagli esatti forniti dal tuo account commerciante Perfect Money.
-   **Scenario / esempio del commerciante:** Hai registrato un account commerciante con Perfect Money. Ti forniscono un "ID account Perfect Money" (es. U1234567) e un "Nome account Perfect Money" (es. MyStorePayments). Hai anche impostato una "Passphrase alternativa Perfect Money" all'interno delle impostazioni del tuo account Perfect Money per una maggiore sicurezza. Devi inserire questi valori esatti qui.

#### **Impostazioni di visualizzazione del pagamento**

-   **Cosa fa questa impostazione:** Questa sezione controlla come l'opzione di pagamento Perfect Money viene presentata ai tuoi clienti durante il checkout.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* I clienti vedranno l'opzione Perfect Money e potranno sceglierla per il pagamento.
    -   *Quando disabilitato:* Perfect Money non apparirà come opzione di pagamento.
-   **Valore consigliato:** "SÌ" (Abilitato) se desideri offrire Perfect Money come metodo di pagamento.
-   **Scenario / esempio del commerciante:** Vuoi offrire Perfect Money come opzione di pagamento. Lo abiliti. Se desideri disabilitarlo temporaneamente per manutenzione o se non desideri più accettare Perfect Money, lo imposteresti su "NO".

#### **Impostazioni stato ordine**

-   **Cosa fa questa impostazione:** Queste impostazioni determinano lo stato che un ordine avrà nel tuo back office PrestaShop dopo che un cliente completa un pagamento tramite Perfect Money.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su "Pagamento accettato":* Gli ordini pagati tramite Perfect Money verranno automaticamente contrassegnati come "Pagamento accettato" nel tuo back office PrestaShop, indicando una transazione riuscita.
    -   *Quando impostato su "Errore di pagamento":* Se un pagamento fallisce o si verifica un problema, l'ordine verrà contrassegnato con questo stato.
-   **Valore consigliato:**
    -   **Stato ordine per un pagamento riuscito:** "Pagamento accettato" (o uno stato simile che hai configurato per i pagamenti riusciti).
    -   **Stato ordine per un errore di pagamento:** "Errore di pagamento" (o uno stato simile per i pagamenti falliti).
-   **Scenario / esempio del commerciante:** Un cliente paga con successo con Perfect Money. Vuoi identificare rapidamente questi ordini come pronti per l'elaborazione. Impostando lo "Stato ordine per un pagamento riuscito" su "Pagamento accettato", il tuo team sa immediatamente che il pagamento è stato autorizzato. Se un cliente tenta di pagare ma la transazione fallisce, l'ordine verrà contrassegnato come "Errore di pagamento", consentendoti di dare seguito o al cliente di riprovare.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | ID Account Perfect Money | Il tuo ID Account Perfect Money (es. U1234567) | Identifica il tuo account commerciante Perfect Money per la ricezione dei pagamenti. **CRITICO per l'elaborazione dei pagamenti.** |
| Configurazione Modulo | Nome Account Perfect Money | Il tuo Nome Account Perfect Money | Il nome associato al tuo account Perfect Money. |
| Configurazione Modulo | Passphrase Alternativa Perfect Money | La tua Passphrase Alternativa Perfect Money | Chiave di sicurezza per la verifica delle transazioni. Impostala nel tuo account Perfect Money. **CRITICO per la sicurezza.** |
| Configurazione Modulo | Abilita Pagamento Perfect Money | SÌ | Attiva/disattiva la visibilità di Perfect Money come opzione di pagamento nella tua pagina di checkout. |
| Configurazione Modulo | Stato ordine per un pagamento riuscito | Pagamento accettato | Lo stato dell'ordine PrestaShop assegnato agli ordini pagati con successo tramite Perfect Money. |
| Configurazione Modulo | Stato ordine per un errore di pagamento | Errore di pagamento | Lo stato dell'ordine PrestaShop assegnato agli ordini in cui il pagamento Perfect Money è fallito. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei clienti riscontrano un errore quando cercano di pagare con Perfect Money.**
R:

-   **Controlla le impostazioni del tuo account Perfect Money:** Ricontrolla che il tuo "ID account Perfect Money", "Nome account Perfect Money" e "Passphrase alternativa Perfect Money" siano inseriti *esattamente* come appaiono nel tuo account commerciante Perfect Money. Anche un piccolo errore di battitura può causare errori.
-   **Verifica lo stato dell'account Perfect Money:** Accedi direttamente al tuo account Perfect Money per assicurarti che sia attivo, in regola e configurato per ricevere pagamenti.
-   **Rivedi i log degli errori di PrestaShop:** Nel tuo back office PrestaShop, naviga su **Parametri avanzati > Log** per vedere se vengono registrati errori specifici relativi al modulo Perfect Money.

**D: Gli ordini non vengono contrassegnati come "Pagamento accettato" dopo un pagamento Perfect Money riuscito.**
R:

-   **Controlla le impostazioni dello stato dell'ordine:** Vai alla configurazione del modulo e assicurati che "Stato ordine per un pagamento riuscito" sia impostato sullo stato corretto (es. "Pagamento accettato").
-   **IPN/Callback Perfect Money:** Assicurati che il tuo account Perfect Money sia configurato correttamente per inviare notifiche di pagamento istantanee (IPN) o callback al tuo negozio PrestaShop. Il modulo si basa su queste notifiche per aggiornare gli stati degli ordini. Sebbene il modulo gestisca l'URL, a volte le impostazioni dell'account Perfect Money possono interferire.

**D: Perfect Money non compare come opzione di pagamento nella mia pagina di checkout.**
R:

-   **Modulo abilitato:** Nella configurazione del modulo, assicurati che "Abilita pagamento Perfect Money" sia impostato su "SÌ".
-   **Modulo installato:** Verifica che il modulo sia correttamente installato e abilitato in **Moduli > Gestione moduli**.
-   **Cache:** Svuota la cache di PrestaShop (sotto **Parametri avanzati > Prestazioni**) e la cache del tuo browser. A volte i vecchi dati memorizzati nella cache possono impedire la visualizzazione di nuove opzioni di pagamento.
-   **Compatibilità del tema:** Sebbene il modulo sia progettato per essere compatibile, temi molto personalizzati potrebbero occasionalmente richiedere piccole modifiche. Se sospetti un conflitto con il tema, prova a passare temporaneamente al tema predefinito di PrestaShop per vedere se l'opzione appare.

**D: Posso personalizzare il logo o il testo di Perfect Money nella pagina di checkout?**
R: Il modulo utilizza un template standard per la visualizzazione dell'opzione di pagamento. Puoi tipicamente personalizzare il testo andando su **Internazionale > Traduzioni** nel tuo back office PrestaShop, selezionando "Traduzioni dei moduli installati", scegliendo il tuo tema e quindi trovando il modulo "Perfect Money". Per le modifiche al logo, dovresti modificare il file del template del modulo (`perfectmoney.tpl`) o utilizzare override CSS nel tuo tema.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata del modulo Perfect Money per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo Perfect Money segue l'architettura standard dei moduli PrestaShop, utilizzando principalmente una classe di modulo principale (`PerfectMoney`) per l'installazione, la disinstallazione e la configurazione, e classi `ModuleFrontController` per gestire i processi di reindirizzamento e validazione del pagamento. Si integra con il gateway di pagamento Perfect Money utilizzando un modello di comunicazione server-to-server (IPN/callback) per confermare le transazioni e aggiornare gli stati degli ordini.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

Questi controller gestiscono gli aspetti rivolti al cliente del processo di pagamento, inclusi il reindirizzamento a Perfect Money e la gestione del callback dopo il pagamento.

-   **`perfectmoney/controllers/front/index.php`**

    -   **Nome classe**: `PerfectMoneyIndexModuleFrontController`
    -   **Classe genitore**: `ModuleFrontController`
    -   **Responsabilità**: Questo controller è tipicamente responsabile dell'avvio del processo di pagamento. Quando un cliente seleziona Perfect Money e conferma il proprio ordine, questo controller prepara i parametri della richiesta di pagamento (ID commerciante, importo, valuta, descrizione dell'ordine, URL di ritorno) e reindirizza il browser del cliente al gateway di pagamento Perfect Money. Raccoglie i dettagli dell'ordine necessari dal carrello e costruisce il modulo di pagamento.
-   **`perfectmoney/controllers/front/validation.php`**

    -   **Nome classe**: `PerfectMoneyValidationModuleFrontController`
    -   **Classe genitore**: `ModuleFrontController`
    -   **Responsabilità**: Questo è il controller cruciale che gestisce il callback (Instant Payment Notification - IPN) da Perfect Money dopo che un pagamento è stato elaborato.
        -   Riceve i dati POST da Perfect Money contenenti i dettagli della transazione e un hash di sicurezza.
        -   Verifica l'integrità e l'autenticità della notifica di pagamento utilizzando la Passphrase Alternativa configurata.
        -   Se il pagamento è valido e riuscito, aggiorna lo stato dell'ordine PrestaShop (es. a "Pagamento accettato"), crea una voce nella cronologia degli ordini e potenzialmente invia e-mail di conferma dell'ordine.
        -   Se il pagamento fallisce o non è valido, aggiorna lo stato dell'ordine di conseguenza (es. a "Errore di pagamento").
        -   Reindirizza quindi il cliente alla pagina PrestaShop appropriata (es. conferma dell'ordine o pagina di errore).

### 4.3 Classi e Modelli Core (`classes/`)

Il modulo non sembra definire alcuna classe personalizzata che estenda `ObjectModel` o altre classi core di PrestaShop in una directory `classes/` dedicata. Tutta la logica core è probabilmente incapsulata all'interno della classe del modulo principale `PerfectMoney` (`index.php`) e dei controller front-end.

### 4.4 Risorse JavaScript (`views/js/`)

Nessun file JavaScript personalizzato è stato rilevato nell'archivio del modulo. Il processo di pagamento è gestito principalmente da reindirizzamenti lato server e dall'interfaccia di pagamento di Perfect Money.

### 4.5 Fogli di stile CSS (`views/css/`)

Nessun file CSS personalizzato è stato rilevato nell'archivio del modulo. Lo stile per l'opzione di pagamento nella pagina di checkout è probabilmente ereditato dal tema PrestaShop o da stili inline all'interno del template.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **`perfectmoney/views/admin.tpl`**

    -   **Ambito**: Configurazione amministrativa del back-office.
    -   **Scopo**: Questo template viene utilizzato per renderizzare il modulo di configurazione del modulo all'interno del back office di PrestaShop. Visualizza i campi di input per l'ID account Perfect Money, il nome account, la passphrase alternativa e i menu a discesa per la selezione dello stato dell'ordine. Utilizza gli helper e lo stile standard dei moduli PrestaShop.
-   **`perfectmoney/views/perfectmoney.tpl`**

    -   **Ambito**: Front-office (passaggio di pagamento del checkout).
    -   **Scopo**: Questo template è responsabile della visualizzazione dell'opzione di pagamento Perfect Money al cliente nella pagina di checkout. Tipicamente include il titolo del metodo di pagamento, la descrizione e potenzialmente il logo Perfect Money. Viene renderizzato all'interno di un hook di pagamento (es. `displayPaymentOptions` in PS 1.7+ o `displayPayment` in PS 1.6).
-   **`perfectmoney/views/success_page.tpl`**

    -   **Ambito**: Front-office (pagina di conferma/successo dell'ordine).
    -   **Scopo**: Questo template è probabilmente utilizzato per visualizzare un messaggio di successo personalizzato o informazioni aggiuntive al cliente dopo un pagamento Perfect Money riuscito, prima o come parte della pagina di conferma dell'ordine standard. Potrebbe essere renderizzato dal controller `validation.php`.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non sembra creare tabelle SQL personalizzate.
    -   Le impostazioni di configurazione (ID account Perfect Money, Passphrase, ecc.) sono memorizzate nella tabella `ps_configuration`, utilizzando chiavi prefissate con `PERFECTMONEY_`.
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayPaymentOptions` (PS 1.7+) | Nella pagina di checkout, passaggio di pagamento. | Renderizza l'opzione di pagamento Perfect Money utilizzando `perfectmoney.tpl`. |
| `displayPayment` (PS 1.6) | Nella pagina di checkout, passaggio di pagamento. | Renderizza l'opzione di pagamento Perfect Money utilizzando `perfectmoney.tpl`. |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Potrebbe essere utilizzato per caricare risorse specifiche del modulo (JS/CSS) se presenti, o per meta tag. (Nessuna risorsa rilevata, quindi probabilmente per l'inizializzazione del modulo o la compatibilità). |
| `actionPaymentConfirmation` | Dopo che lo stato di pagamento di un ordine è confermato. | Potrebbe essere utilizzato per l'elaborazione post-pagamento, sebbene l'aggiornamento dello stato primario sia gestito dal controller `validation.php`. |
| `actionValidateOrder` | Dopo che un ordine è stato validato e creato con successo. | Utilizzato dal modulo per creare l'ordine in PrestaShop con lo stato iniziale prima del reindirizzamento a Perfect Money. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo Perfect Money, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e all'integrazione del modulo.
