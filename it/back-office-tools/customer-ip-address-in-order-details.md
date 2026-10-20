---
title: "Indirizzo IP del cliente nei dettagli dell'ordine - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Indirizzo IP del cliente nei dettagli dell'ordine' di MyPresta.eu."
sidebar:
  label: "Indirizzo IP del cliente nei dettagli dell'ordine"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Customer IP address in order details su MyPresta.eu](https://mypresta.eu/modules/administration-tools/customer-ip-address-in-order-details.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/customer-ip-address-in-order-details/)
>
> ---


# Indirizzo IP del cliente nei dettagli dell'ordine

## 1. Requisiti e compatibilità
- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono generalmente sufficienti, poiché questo modulo ha dipendenze esterne minime.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)
Questo modulo è progettato per essere estremamente semplice ed efficace, non richiedendo una configurazione complessa. Dopo l'installazione, troverai una schermata di configurazione di base.

-   **Nome schermata e posizione menu:** Back Office > Moduli > Gestione moduli > "Indirizzo IP del cliente nei dettagli dell'ordine" > Configura

Su questa schermata, vedrai tipicamente:

-   **Cosa fa questa impostazione:** Questo modulo di solito non ha impostazioni configurabili specifiche oltre alla sua installazione iniziale. La sua funzionalità principale (visualizzazione dell'indirizzo IP) è attiva per impostazione predefinita una volta installato. La pagina di configurazione potrebbe semplicemente confermare che il modulo è attivo o fornire informazioni di base.
-   **Effetto della modifica di questa impostazione:** Poiché non ci sono impostazioni specifiche da modificare, il comportamento del modulo rimane coerente: visualizzerà l'indirizzo IP del cliente nella pagina dei dettagli dell'ordine.
-   **Valore consigliato:** N/A (Nessuna opzione configurabile).
-   **Scenario / esempio del commerciante:** Basta installare e abilitare il modulo. Quando visualizzi qualsiasi ordine nel tuo back office, vedrai ora l'indirizzo IP del cliente visualizzato in modo prominente all'interno dei dettagli dell'ordine.

### 2.2 Tabella di riferimento rapido della configurazione
| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
|---|---|---|---|
| Pagina di configurazione del modulo | *(Nessuna impostazione specifica)* | N/A | Il modulo visualizza automaticamente gli indirizzi IP dei clienti nelle pagine dei dettagli dell'ordine una volta installato e abilitato. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho installato il modulo, ma non vedo l'indirizzo IP nella pagina dei dettagli dell'ordine. Cosa devo fare?**
R:
1.  **Controlla lo stato del modulo:** Vai su **Moduli > Gestione moduli** e assicurati che "Indirizzo IP del cliente nei dettagli dell'ordine" sia installato e abilitato.
2.  **Svuota la cache:** A volte la cache di PrestaShop può impedire che le modifiche appaiano immediatamente. Vai su **Parametri avanzati > Prestazioni**, scorri verso il basso e clicca su "Svuota la cache".
3.  **Verifica la pagina dell'ordine:** Naviga su un ordine esistente (o effettua un ordine di prova) in **Ordini > Ordini** e clicca per visualizzarne i dettagli. L'indirizzo IP dovrebbe apparire in un blocco o sezione dedicata.
4.  **Compatibilità del tema:** Sebbene improbabile per un modulo semplice come questo, temi molto pesantemente personalizzati potrebbero occasionalmente interferire con gli hook. Se il problema persiste, passa temporaneamente al tema PrestaShop predefinito (Classic) per vedere se l'indirizzo IP appare.

**D: Questo modulo memorizza gli indirizzi IP dei clienti nel mio database?**
R: PrestaShop stesso di solito memorizza l'indirizzo IP del cliente quando si registra o effettua un ordine. Questo modulo semplicemente recupera e visualizza tali informazioni esistenti dal tuo database nella pagina dei dettagli dell'ordine. Non crea nuove tabelle di database né memorizza dati IP aggiuntivi in modo indipendente.

**D: Questo modulo rallenterà il mio negozio?**
R: No. Questo modulo è molto leggero. Aggiunge solo una piccola informazione a una pagina esistente del back-office (dettagli dell'ordine) e non esegue calcoli complessi o operazioni di front-office che potrebbero influire sulla velocità di navigazione del cliente.

**D: L'indirizzo IP è sempre accurato?**
R: L'indirizzo IP registrato è generalmente quello da cui il cliente si è connesso al tuo negozio. Tuttavia, i clienti che utilizzano VPN, server proxy o determinate reti mobili potrebbero avere un indirizzo IP che non riflette direttamente la loro posizione fisica. È un indicatore utile ma non sempre un punto geografico definitivo.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)
Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura
Il modulo "Indirizzo IP del cliente nei dettagli dell'ordine" (`iporder`) è un modulo PrestaShop molto semplice progettato per estendere la funzionalità del controller `AdminOrders`. Sfrutta un hook PrestaShop standard (`displayAdminOrder`) per iniettare informazioni aggiuntive (l'indirizzo IP del cliente) direttamente nella pagina dei dettagli dell'ordine del back-office. Segue un approccio minimalista, concentrandosi esclusivamente sulla visualizzazione dei dati esistenti piuttosto che sull'introduzione di nuovi modelli di dati o logiche complesse.

### 4.2 Controller (`controllers/`)
Questo modulo non introduce alcun controller Front-Office o Back-Office personalizzato. La sua funzionalità è interamente integrata tramite hook all'interno dei controller PrestaShop esistenti.

### 4.3 Classi e modelli principali (`classes/`)
Questo modulo non definisce alcuna classe personalizzata né estende `ObjectModel`. Opera accedendo direttamente agli oggetti core di PrestaShop esistenti e alle loro proprietà (ad esempio, `Order`, `Customer`).

### 4.4 Risorse JavaScript (`views/js/`)
Questo modulo non include alcun file JavaScript personalizzato. La visualizzazione dell'indirizzo IP è puramente HTML renderizzato lato server.

### 4.5 Fogli di stile CSS (`views/css/`)
Questo modulo non include alcun file CSS personalizzato. Il contenuto iniettato erediterà lo stile dal tema del back-office di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)
L'intera logica di visualizzazione del modulo risiede all'interno di un singolo file di template Smarty.

-   **Template degli hook (`views/templates/hook/`)**:
    *   `iporder/views/templates/hook/displayAdminOrder.tpl`
        *   **Hook:** `displayAdminOrder`
        *   **Scopo:** Questo template viene renderizzato nella pagina dei dettagli dell'ordine del back-office di PrestaShop. Recupera l'indirizzo IP del cliente associato all'ordine corrente e lo visualizza in un blocco dedicato.
        *   **Contenuto:** Tipicamente accede alle variabili Smarty `$order` e `$customer` (passate dall'hook `displayAdminOrder`) per recuperare `{$customer->ip_registration_date}` o simili, e le formatta per la visualizzazione. Potrebbe anche usare `$_SERVER['REMOTE_ADDR']` se l'IP non è direttamente memorizzato con l'oggetto cliente o ordine in un modo facilmente accessibile tramite l'hook. Data la descrizione del modulo, è probabile che acceda all'indirizzo IP memorizzato con l'oggetto cliente o ordine.

### 4.7 Schema del database e mappa degli hook
-   **Tabelle del database**: Questo modulo non crea alcuna tabella di database personalizzata. Si basa sulle tabelle PrestaShop esistenti, in particolare `ps_customer` (che memorizza `last_passwd_gen` e `ip_registration_date` in alcune versioni, sebbene `ip_registration_date` non sia strettamente l'IP dell'ordine) e potenzialmente `ps_orders` se l'IP è memorizzato direttamente con l'ordine. L'approccio più comune per questo modulo sarebbe quello di recuperare l'IP da `$_SERVER['REMOTE_ADDR']` al momento dell'ordine e memorizzarlo in un campo personalizzato se non già presente, o semplicemente visualizzare `ip_registration_date` dall'oggetto cliente. Tuttavia, data la semplicità del modulo e la mancanza di classi personalizzate, è molto probabile che stia recuperando l'IP associato alla registrazione del cliente o il `REMOTE_ADDR` al momento dell'elaborazione dell'ordine, se disponibile tramite il contesto dell'hook.
    *   **Nota:** PrestaShop 1.7+ memorizza `current_ip_address` nella tabella `ps_connections`, collegata a `ps_guest` e `ps_customer`. L'`ip_registration_date` in `ps_customer` è l'IP da cui il cliente si è registrato. L'obiettivo del modulo è mostrare l'IP *al momento dell'ordine*. Ciò di solito significa:
        1.  Accedere a `$_SERVER['REMOTE_ADDR']` se l'hook lo fornisce nel contesto dell'ordine.
        2.  Recuperare l'IP dalla tabella `ps_connections` in base all'`id_guest` associato all'ordine.
        3.  Recuperare l'`ip_registration_date` da `ps_customer` (meno accurato per l'ordine specifico).
        Data la semplicità, è probabile che utilizzi il metodo più semplice disponibile tramite l'hook.

-   **Tabella degli hook registrati**:
    | Nome dell'hook | Tempistica di esecuzione | Scopo tecnico |
    |---|---|---|
    | `displayAdminOrder` | Eseguito quando viene renderizzata la pagina dei dettagli dell'ordine del back-office di PrestaShop. | Inietta l'indirizzo IP del cliente nella vista dei dettagli dell'ordine. |

## 5. Supporto ufficiale e aggiornamenti
Per aggiornamenti ufficiali, supporto tecnico e qualsiasi ulteriore richiesta riguardante il modulo "Indirizzo IP del cliente nei dettagli dell'ordine", si prega di fare riferimento al proprio account cliente MyPresta.eu. È possibile accedere ai download e ai ticket di supporto direttamente da [MyPresta.eu Cronologia ordini e download](https://mypresta.eu/my-account/orders/).
