---
title: "Disabilita spedizione gratuita per paesi selezionati - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Disabilita spedizione gratuita per paesi selezionati' di MyPresta.eu."
sidebar:
  label: "Disabilita spedizione gratuita per paesi selezionati - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Disable free shipping to selected countries su MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-free-shipping-to-selected-countries.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/disable-free-shipping-to-selected-countries/)
>
> ---


# Disabilita spedizione gratuita per paesi selezionati

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale e unica per il modulo "Disabilita spedizione gratuita per paesi selezionati". La troverai navigando su **Moduli > Gestione moduli**, cercando "Disabilita spedizione gratuita per paesi selezionati" e cliccando su "Configura".

#### Escludi spedizione gratuita dai paesi:

- **Cosa fa questa impostazione:** Questa è l'impostazione principale del modulo. Ti consente di selezionare uno o più paesi in cui la spedizione gratuita *non* dovrebbe essere offerta, indipendentemente da altre regole di spedizione gratuita che potresti avere (ad esempio, spedizione gratuita oltre un certo importo dell'ordine).
- **Effetto della modifica di questa impostazione:**
  - *Quando i paesi sono selezionati:* Se l'indirizzo di consegna di un cliente si trova in uno dei paesi selezionati, l'opzione "Spedizione gratuita" verrà rimossa dall'elenco dei corrieri disponibili durante il checkout. Verranno visualizzate solo le opzioni di spedizione a pagamento.
  - *Quando nessun paese è selezionato:* Il modulo non avrà alcun effetto e la spedizione gratuita sarà offerta a tutti i paesi in base alle impostazioni standard di PrestaShop.
- **Valore consigliato:** Seleziona solo quei paesi in cui offrire la spedizione gratuita è realmente non redditizio o problematico per la tua attività.
- **Scenario / esempio del commerciante:** Spedisci a livello internazionale, ma la spedizione in Australia e Nuova Zelanda è significativamente più costosa a causa della distanza e delle dogane. Selezioneresti "Australia" e "Nuova Zelanda" da questo elenco. Ora, i clienti di questi paesi verranno sempre addebitati per la spedizione, anche se il valore del loro ordine si qualifica per la spedizione gratuita in altre regioni come l'UE o gli USA.

#### Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | Escludi spedizione gratuita dai paesi: | Nessuno selezionato | Seleziona i paesi in cui la spedizione gratuita NON deve essere offerta. Se l'indirizzo di consegna di un cliente si trova in un paese selezionato, la spedizione gratuita non sarà disponibile per il suo ordine. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho configurato il modulo, ma la spedizione gratuita è ancora visibile per un paese selezionato. Cosa c'è che non va?**
R:

1.  **Svuota la cache:** Svuota sempre la cache di PrestaShop dopo aver apportato modifiche alla configurazione. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" in alto a destra.
2.  **Testa con un nuovo carrello:** Assicurati di testare con un carrello nuovo e un indirizzo di consegna impostato sul paese escluso. A volte la cache del browser o i dati di sessione possono interferire.
3.  **Controlla le impostazioni del corriere:** Verifica che il tuo corriere di spedizione gratuita (o il corriere che offre la spedizione gratuita) sia configurato correttamente in **Spedizione > Corrieri**. Assicurati che sia attivo e che abbia "Spedizione gratuita" abilitata. Questo modulo *disabilita* l'opzione di spedizione gratuita, non crea nuove regole di spedizione.
4.  **Ordine dei moduli:** In rari casi, se hai più moduli relativi alla spedizione, potrebbe esserci un conflitto. Prova a disabilitare temporaneamente altri moduli di spedizione per isolare il problema.

**D: Questo modulo influisce su altri costi di spedizione?**
R: No, questo modulo influisce *solo* sulla disponibilità dell'opzione "Spedizione gratuita". Non modifica né rimuove alcuna opzione di spedizione a pagamento o i relativi costi. Se la spedizione gratuita è disabilitata per un paese, ai clienti verranno semplicemente presentate le opzioni di spedizione a pagamento standard disponibili per il loro carrello e la loro destinazione.

**D: Posso disabilitare la spedizione gratuita per prodotti o categorie specifiche invece che per paesi?**
R: No, questo modulo è progettato specificamente per disabilitare la spedizione gratuita in base al *paese di consegna*. Non offre opzioni per escludere la spedizione gratuita in base a prodotto, categoria o gruppo di clienti. Se hai bisogno di tale funzionalità, avresti bisogno di un modulo di regole di spedizione diverso e più avanzato.

**D: Cosa succede se voglio offrire la spedizione gratuita a un paese per ordini superiori a un certo importo, ma disabilitarla per importi inferiori?**
R: Questo modulo disabilita *tutta* la spedizione gratuita per i paesi selezionati. Se desideri una spedizione gratuita condizionale (ad esempio, spedizione gratuita oltre $X), dovresti configurarla direttamente nelle impostazioni dei corrieri di PrestaShop (Spedizione > Corrieri). Questo modulo sovrascriverebbe quindi tale impostazione per i paesi esclusi, rendendo la spedizione gratuita non disponibile a *qualsiasi* importo per quelle specifiche destinazioni.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Disabilita spedizione gratuita per paesi selezionati" opera sovrascrivendo le classi principali di PrestaShop relative al comportamento del corriere e del carrello. In particolare, modifica la logica che determina se un corriere offre la spedizione gratuita e se un carrello si qualifica per essa, in base al paese di consegna del cliente. Ciò si ottiene tramite il sistema di override di PrestaShop, garantendo che la logica del modulo venga applicata ogni volta che vengono eseguiti i calcoli di spedizione.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza alcun controller personalizzato per il Front-Office o il Back-Office Admin. La sua logica viene iniettata direttamente nella funzionalità principale di PrestaShop tramite override di classe.

### 4.3 Classi e modelli principali (`classes/`)

Il modulo implementa la sua funzionalità principalmente tramite override di classe, situati nella directory `override/classes/` all'interno della cartella del modulo.

-   **`exfsc/override/classes/Carrier.php`**

    -   **Nome classe e classe padre:** `Carrier` (sovrascrive la classe `Carrier` principale)
    -   **Responsabilità:** Questo override modifica il metodo `isFree()` della classe `Carrier`. Quando PrestaShop verifica se un particolare corriere offre la spedizione gratuita, questo override intercetta la chiamata. Controlla se il paese di consegna del carrello corrente è tra quelli configurati per escludere la spedizione gratuita. Se lo è, e il metodo `isFree()` originale avrebbe restituito `true`, questo override lo forza a restituire `false`, disabilitando di fatto la spedizione gratuita per quel corriere per il paese escluso.
    -   **Metodi chiave:**
        -   `isFree($cart)`: Modificato per controllare la configurazione `exfsc_country` e restituire `false` se il paese di consegna del carrello è escluso e il metodo originale avrebbe restituito `true`.
-   **`exfsc/override/classes/Cart.php`**

    -   **Nome classe e classe padre:** `Cart` (sovrascrive la classe `Cart` principale)
    -   **Responsabilità:** Questo override modifica il metodo `getDeliveryOptionList()`. Questo metodo è responsabile della generazione dell'elenco delle opzioni di consegna disponibili (inclusi corrieri e loro servizi) durante il checkout. L'override garantisce che se un corriere è contrassegnato come "spedizione gratuita" ma il paese di consegna è escluso dal modulo, quel corriere venga correttamente presentato con le sue opzioni di spedizione *a pagamento*, o se offre solo la spedizione gratuita, venga escluso del tutto.
    -   **Metodi chiave:**
        -   `getDeliveryOptionList(Country $default_country = null, $product_list = null, $id_zone = null)`: Modificato per garantire che i corrieri contrassegnati come gratuiti siano correttamente valutati rispetto all'elenco di esclusione dei paesi del modulo.
-   **`exfsc/override/classes/index.php`**

    -   **Scopo:** Questo è un file `index.php` vuoto, tipicamente incluso nelle directory per impedire l'elenco delle directory quando vi si accede direttamente tramite un browser web, migliorando la sicurezza. Non ha alcun impatto funzionale sulla logica del modulo.

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo non include alcun file JavaScript personalizzato. Tutte le funzionalità sono gestite lato server.

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo non include alcun file CSS personalizzato. Tutte le funzionalità sono gestite lato server.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo non include alcun file di template Smarty personalizzato. I suoi effetti sono integrati nei template di checkout esistenti di PrestaShop modificando i dati sottostanti passati ad essi.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non crea alcuna tabella SQL personalizzata.
    -   Le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration`.
        -   `exfsc_country`: Memorizza un elenco separato da virgole di valori `id_country` per i paesi in cui la spedizione gratuita è disabilitata.
        -   `mypresta_updates`, `update_`, `updatev_`: Chiavi di configurazione interne utilizzate dai moduli MyPresta.eu per i controlli degli aggiornamenti.
        -   `exfsc_visibility_cat`, `exfsc_visibility_products`: Queste chiavi sono presenti nel metodo `getContent()` ma non sono attivamente utilizzate dalla logica principale del modulo come descritto nel set di funzionalità. Potrebbero essere residui o segnaposto per potenziali funzionalità future.
-   **Tabella degli hook registrati**:
    Il modulo non registra esplicitamente alcun hook di front-office. La sua funzionalità è implementata tramite override di classe, che vengono attivati automaticamente dai processi principali di PrestaShop quando vengono calcolate le opzioni di spedizione.
    Il metodo `install()` del modulo può registrare hook standard di back-office per la gestione dei moduli (ad esempio, `displayBackOfficeHeader`), ma questi sono a scopo amministrativo e non influenzano il comportamento del front-office.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo "Disabilita spedizione gratuita per paesi selezionati", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a garantire che il tuo modulo funzioni perfettamente con il tuo negozio PrestaShop.
"""
