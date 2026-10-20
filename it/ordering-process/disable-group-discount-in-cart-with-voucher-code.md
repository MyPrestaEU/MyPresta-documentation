---
title: "Disabilita sconto gruppo nel carrello con codice voucher - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Disabilita sconto gruppo nel carrello con codice voucher' di MyPresta.eu."
sidebar:
  label: "Disabilita sconto gruppo nel carrello con codice voucher - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Disable group discount in cart with voucher code su MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-group-discount-in-cart-with-voucher-code.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/disable-group-discount-in-cart-with-voucher-code/)
>
> ---


# Disabilita sconto gruppo nel carrello con codice voucher

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al nome del modulo per accedere alle sue impostazioni.

#### Impostazione: Disabilita sconto gruppi nel carrello con regola carrello

Questo è l'interruttore di controllo principale per la funzionalità del modulo.

-   **Cosa fa questa impostazione:** Questa impostazione determina se il modulo interviene attivamente per disabilitare gli sconti di gruppo quando un codice voucher è presente nel carrello.
-   **Effetto della modifica di questa impostazione:**
    -   ***Quando Abilitato:*** Se un cliente appartiene a un gruppo con uno sconto speciale (ad esempio, 10% di sconto per "Clienti all'ingrosso") E applica un codice voucher (regola carrello) al suo carrello, lo sconto di gruppo verrà ignorato. Solo lo sconto del voucher verrà applicato al totale dell'ordine. Questo impedisce al cliente di ricevere entrambi gli sconti contemporaneamente.
    -   ***Quando Disabilitato:*** Il modulo non interverrà. Verrà applicato il comportamento predefinito di PrestaShop, il che significa che se un cliente ha diritto sia a uno sconto di gruppo che a uno sconto voucher, entrambi potrebbero essere applicati, potenzialmente cumulando gli sconti.
-   **Valore consigliato:** **Abilitato**. Questa è la funzionalità principale del modulo ed è generalmente consigliata per prevenire accumuli di sconti indesiderati e proteggere i tuoi margini di profitto durante le campagne voucher.
-   **Scenario / esempio per il commerciante:**
    -   *Scenario 1 (Abilitato):* Hai un gruppo "Clienti VIP" che ottiene il 5% di sconto su tutti i prodotti. Gestisci anche un codice voucher "ESTATE20" per il 20% di sconto. Un cliente VIP aggiunge articoli al carrello e applica "ESTATE20". Con il modulo **Abilitato**, otterrà solo il 20% di sconto dal voucher, non 5% + 20%.
    -   *Scenario 2 (Disabilitato):* Usando lo stesso esempio, se il modulo è **Disabilitato**, il cliente VIP potrebbe ricevere sia lo sconto di gruppo del 5% che lo sconto voucher del 20%, portando a uno sconto totale del 25% (o un calcolo più complesso a seconda dell'ordine interno di applicazione degli sconti di PrestaShop).

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Disabilita sconto gruppi nel carrello con regola carrello | Abilitato | Quando abilitato, gli sconti di gruppo vengono ignorati se un codice voucher è presente nel carrello, garantendo che venga applicato solo lo sconto del voucher. Previene l'accumulo di sconti. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D1: Ho abilitato il modulo, ma i clienti stanno ancora ottenendo entrambi gli sconti. Cosa c'è che non va?**
R1: Innanzitutto, assicurati che il modulo sia effettivamente "Abilitato" nella sua configurazione. In secondo luogo, svuota la cache di PrestaShop (Vai su **Parametri avanzati > Prestazioni**, quindi clicca su "Svuota la cache" nell'angolo in alto a destra). A volte, i vecchi dati della cache possono impedire che le modifiche abbiano effetto immediatamente. Inoltre, testa con un carrello nuovo e una nuova sessione cliente (ad esempio, in una finestra del browser in incognito).

**D2: Questo modulo influenzerà i miei prezzi specifici o le regole del catalogo prezzi?**
R2: No, questo modulo si rivolge specificamente agli *sconti di gruppo* e alle *regole del carrello (codici voucher)*. Non interferisce con i prezzi specifici impostati per singoli prodotti, combinazioni di prodotti o regole del catalogo prezzi che si applicano in base alla quantità o ad altre condizioni. Modifica solo l'interazione tra gli sconti per gruppo cliente e i codici voucher.

**D3: Questo modulo funziona con tutti i tipi di codici voucher (percentuale, importo fisso, spedizione gratuita)?**
R3: Sì, la logica del modulo è progettata per rilevare la presenza di *qualsiasi* regola del carrello (codice voucher) attiva nel carrello. Una volta rilevata una regola del carrello, disabiliterà lo sconto di gruppo, indipendentemente dal tipo di sconto fornito dal voucher (percentuale, importo fisso, spedizione gratuita, ecc.).

**D4: E se volessi consentire sconti di gruppo E un codice voucher per una promozione specifica?**
R4: Se hai una promozione specifica in cui *vuoi* consentire l'accumulo di entrambi gli sconti, dovrai temporaneamente **Disabilitare** questo modulo nella sua configurazione. Ricorda di riabilitarlo una volta terminata quella promozione specifica se desideri tornare al comportamento di sconto "solo voucher".

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Questo modulo funziona principalmente tramite un override di una classe core di PrestaShop. Invece di utilizzare gli hook, modifica direttamente il comportamento della classe `Product` per regolare il modo in cui i prezzi vengono calcolati quando è coinvolto uno sconto per gruppo cliente e una regola del carrello è attiva. Questo approccio garantisce che la logica di sconto sia applicata a un livello fondamentale durante il recupero del prezzo del prodotto.

### 4.2 Controller (`controllers/`)

- Questo modulo non include alcun controller front-office o back-office personalizzato. La sua funzionalità è implementata tramite override di classe.

### 4.3 Classi e modelli core (`classes/`)

-   **Percorso file**: `exgcr/override/classes/Product.php`

    -   **Nome classe**: `Product` (sovrascrive la classe core `Product`)
    -   **Classe padre**: `ProductCore`
    -   **Responsabilità**: Questo override modifica il metodo `getPriceStatic` della classe `Product`. Il metodo `getPriceStatic` è cruciale in quanto è responsabile del calcolo del prezzo finale di un prodotto, tenendo conto di vari fattori come tasse, prezzi specifici, gruppi di clienti e regole del carrello.
    -   **Logica chiave**:
        -   L'override verifica se il modulo `exgcr` è abilitato.
        -   Quindi verifica se è presente una `CartRule` (codice voucher) attiva applicata al carrello corrente.
        -   Se entrambe le condizioni sono soddisfatte (modulo abilitato E voucher presente), modifica i parametri passati al metodo `getPriceStatic` padre per ignorare efficacemente lo sconto per gruppo cliente. In particolare, imposta il parametro `$use_group_reduction` su `false` quando chiama il metodo padre, impedendo così l'applicazione dello sconto di gruppo.
        -   Ciò garantisce che quando un voucher è in uso, il calcolo del prezzo procede come se il cliente non appartenesse a un gruppo scontato, prevenendo così l'accumulo di sconti di gruppo con sconti voucher.
-   **Percorso file**: `exgcr/override/classes/index.php`

    -   **Scopo**: Questo è un file `index.php` vuoto standard posizionato nelle directory per prevenire l'elenco delle directory (misura di sicurezza). Non contiene codice funzionale.

### 4.4 Risorse JavaScript (`views/js/`)

- Questo modulo non include alcun file JavaScript personalizzato.

### 4.5 Fogli di stile CSS (`views/css/`)

- Questo modulo non include alcun file CSS personalizzato.

### 4.6 Struttura del template Smarty (`views/templates/`)

- Questo modulo non include alcun file di template Smarty personalizzato. La sua configurazione è gestita direttamente all'interno del metodo `getContent()` del file principale del modulo.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**:

    -   Questo modulo non crea tabelle di database personalizzate.
    -   Memorizza la sua impostazione di configurazione (`exgcr`) nella tabella standard `ps_configuration`.
        -   Voce `PS_CONFIGURATION`: `EXGCR_ENABLED` (memorizza `1` per abilitato, `0` per disabilitato).
-   **Tabella degli hook registrati**:

    -   Questo modulo non registra alcun hook specifico nella tabella `ps_hook_module`. La sua funzionalità è implementata tramite un override di classe, che è un modo più diretto per modificare il comportamento core senza fare affidamento sull'esecuzione degli hook.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo "Disabilita sconto gruppo nel carrello con codice voucher", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità del modulo e all'integrazione con il tuo negozio PrestaShop.
