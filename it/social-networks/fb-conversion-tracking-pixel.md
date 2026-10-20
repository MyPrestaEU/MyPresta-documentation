---
title: "Pixel di monitoraggio delle conversioni Fb - Manuale del commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Pixel di monitoraggio delle conversioni Fb' di MyPresta.eu."
sidebar:
  label: "Pixel di monitoraggio delle conversioni Fb - Manuale del commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Fb conversion tracking pixel su MyPresta.eu](https://mypresta.eu/modules/social-networks/fb-conversion-tracking-pixel.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/fb-conversion-tracking-pixel/)
>
> ---


# Pixel di monitoraggio delle conversioni Fb

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Per il corretto funzionamento del modulo, in particolare per le funzionalità dell'API delle conversioni (CAPI), sono richieste estensioni PHP standard come cURL, JSON e OpenSSL. Queste sono tipicamente disponibili su tutti gli ambienti di hosting moderni.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, atterrerai sulla pagina di configurazione principale. Qui collegherai il tuo negozio a Facebook e personalizzerai il modo in cui gli eventi vengono tracciati.

#### Scheda Impostazioni generali

-   **ID Pixel:**

    *   **Cosa fa questa impostazione:** Questo è l'identificatore univoco del tuo Pixel di Facebook. Puoi trovarlo nel tuo Facebook Business Manager o Gestione eventi. Puoi inserire più ID Pixel separati da virgole se gestisci più pixel.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando compilato:* Il modulo incorporerà il codice del Pixel di Facebook nel front office del tuo negozio, inviando dati agli ID Pixel specificati.
        *   *Quando vuoto:* Non avverrà alcun tracciamento del Pixel di Facebook.
    *   **Valore consigliato:** Il tuo ID Pixel di Facebook principale.
    *   **Scenario / esempio del commerciante:** Hai un pixel principale per il tuo marchio e un pixel secondario per una specifica linea di prodotti. Inseriscili entrambi qui: `1234567890,9876543210`.
-   **Token di accesso CAPI:**

    *   **Cosa fa questa impostazione:** Questo token abilita l'API delle conversioni di Facebook (CAPI), che invia i dati di conversione direttamente dal tuo server a Facebook, bypassando le limitazioni del browser (come i blocchi degli annunci o le restrizioni sui cookie). Ciò migliora l'accuratezza dei dati.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando compilato:* Il modulo tenterà di inviare eventi lato server a Facebook utilizzando CAPI, in aggiunta o al posto degli eventi pixel lato browser, a seconda delle altre impostazioni.
        *   *Quando vuoto:* Avverrà solo il tracciamento pixel lato browser (se l'ID Pixel è impostato).
    *   **Valore consigliato:** Altamente raccomandato l'uso di CAPI per una migliore accuratezza dei dati. Genera questo token nel tuo Gestione eventi di Facebook.
    *   **Scenario / esempio del commerciante:** Vuoi garantire la massima accuratezza dei dati per i tuoi eventi di acquisto, anche se i clienti utilizzano blocchi degli annunci. Generi un token di accesso nel Gestione eventi di Facebook e lo incolli qui.
-   **Codice evento di test:**

    *   **Cosa fa questa impostazione:** Questo codice viene utilizzato per testare la tua configurazione CAPI nel Gestione eventi di Facebook. Quando inserito, il modulo invierà eventi di test, permettendoti di verificare che il tuo tracciamento lato server funzioni correttamente.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando compilato:* Gli eventi CAPI includeranno questo codice di test, rendendoli visibili nella scheda "Eventi di test" del Gestione eventi di Facebook.
        *   *Quando vuoto:* Gli eventi CAPI verranno inviati come eventi live.
    *   **Valore consigliato:** Utilizzare solo quando si sta attivamente testando la configurazione CAPI. Rimuoverlo una volta completato il test.
    *   **Scenario / esempio del commerciante:** Hai appena configurato CAPI e vuoi confermare che stia inviando dati. Copi il codice di test dal Gestione eventi di Facebook, lo incolli qui, effettui un acquisto di prova sul tuo sito e poi controlli la scheda "Eventi di test" in Facebook.
-   **Modalità di consenso:**

    *   **Cosa fa questa impostazione:** Questa opzione si integra con la soluzione di consenso ai cookie del tuo negozio (ad esempio, moduli GDPR). Determina se gli eventi del Pixel di Facebook vengono attivati solo dopo che un cliente ha dato il consenso.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Gli eventi pixel verranno attivati solo se il cliente ha accettato i cookie.
        *   *Quando disabilitato:* Gli eventi pixel verranno attivati indipendentemente dal consenso ai cookie (usare con cautela, a seconda delle leggi sulla privacy locali).
    *   **Valore consigliato:** "Sì" se operi in regioni con leggi sulla privacy severe (come il GDPR in Europa).
    *   **Scenario / esempio del commerciante:** Il tuo negozio si rivolge a clienti nell'UE. Abiliti questa impostazione per conformarti al GDPR, assicurando che i dati del pixel vengano raccolti solo dagli utenti che acconsentono esplicitamente all'uso dei cookie.
-   **Stati pagati:**

    *   **Cosa fa questa impostazione:** Seleziona quali stati dell'ordine in PrestaShop dovrebbero attivare un evento "Purchase" su Facebook. Tipicamente, questo include stati come "Pagamento accettato" o "Consegnato".
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando selezionato:* Gli ordini che raggiungono questi stati invieranno un evento "Purchase" a Facebook.
        *   *Quando non selezionato:* Gli ordini non invieranno un evento "Purchase" quando raggiungono questi stati.
    *   **Valore consigliato:** Seleziona tutti gli stati che rappresentano realmente un ordine completato e pagato.
    *   **Scenario / esempio del commerciante:** Consideri un ordine "pagato" quando è "Pagamento accettato" e "Spedito". Selezioni entrambi questi stati.
-   **Stati di rimborso / annullamento:**

    *   **Cosa fa questa impostazione:** Seleziona quali stati dell'ordine indicano un rimborso o un annullamento. Ciò consente al modulo di inviare potenzialmente un evento "Refund" o "Cancel" (se supportato dall'API di Facebook e dalla versione del modulo) o di prevenire il tracciamento di acquisti falsi positivi.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando selezionato:* Il modulo riconoscerà questi ordini come non acquisti o rimborsati.
        *   *Quando non selezionato:* Questi ordini potrebbero comunque essere contati come acquisti se in precedenza hanno raggiunto uno "Stato pagato".
    *   **Valore consigliato:** Seleziona stati come "Annullato", "Rimborsato", "Errore di pagamento".
    *   **Scenario / esempio del commerciante:** Un cliente annulla un ordine. Vuoi assicurarti che questo non venga conteggiato come un acquisto riuscito. Selezioni "Annullato" e "Rimborsato" qui.

#### Scheda Impostazioni avanzate

-   **Selettore CSS aggiungi al carrello:**

    *   **Cosa fa questa impostazione:** Questa è un'impostazione tecnica che aiuta il modulo a identificare il pulsante "Aggiungi al carrello" sulle tue pagine prodotto. Se il tuo tema utilizza un pulsante non standard, potresti dover specificare il suo selettore CSS.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando corretto:* L'evento "AddToCart" si attiverà in modo affidabile quando un cliente clicca sul pulsante.
        *   *Quando errato o vuoto (e il rilevamento automatico fallisce):* L'evento "AddToCart" potrebbe non attivarsi, portando a dati mancanti.
    *   **Valore consigliato:** Lasciare vuoto inizialmente; il modulo spesso rileva automaticamente. Se gli eventi "AddToCart" mancano, consulta lo sviluppatore del tuo tema o usa l'ispettore del tuo browser per trovare il selettore CSS corretto (ad esempio, `.add-to-cart-button`).
    *   **Scenario / esempio del commerciante:** Il tuo tema personalizzato ha un pulsante "Aggiungi al carrello" unico. Ispezioni il pulsante nel tuo browser e trovi che la sua classe è `my-custom-add-button`. Inserisci `.my-custom-add-button` qui.
-   **Selettore CSS prezzo prodotto:**

    *   **Cosa fa questa impostazione:** Simile al selettore Aggiungi al carrello, questo aiuta il modulo a trovare accuratamente il prezzo del prodotto sulla pagina, specialmente per prezzi dinamici o layout di tema specifici.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando corretto:* Il parametro "value" per eventi come "ViewContent" e "AddToCart" rifletterà accuratamente il prezzo del prodotto.
        *   *Quando errato o vuoto (e il rilevamento automatico fallisce):* Il parametro "value" potrebbe essere mancante o errato, influenzando l'ottimizzazione degli annunci.
    *   **Valore consigliato:** Lasciare vuoto inizialmente. Se i valori dei prezzi sono errati nel Gestione eventi di Facebook, trova il selettore CSS corretto (ad esempio, `.current-price span[itemprop="price"]`).
    *   **Scenario / esempio del commerciante:** La tua pagina prodotto visualizza i prezzi in modo non standard. Identifichi il selettore CSS per l'elemento prezzo per assicurarti che Facebook riceva il valore corretto.
-   **Identificazione prodotto:**

    *   **Cosa fa questa impostazione:** Determina quale identificatore di prodotto (ID) il tuo negozio invia a Facebook. Le opzioni tipicamente includono `ID` (ID interno del prodotto di PrestaShop), `Reference` (SKU del tuo prodotto) o `EAN13` / `UPC` (numeri di codice a barre). Questo è cruciale per abbinare i prodotti nel tuo Catalogo Facebook.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato:* Facebook riceverà il tipo di ID scelto, che dovrebbe corrispondere agli ID nel tuo Catalogo prodotti di Facebook affinché gli annunci dinamici funzionino.
        *   *Quando non corrispondente al tuo catalogo:* Gli annunci dinamici potrebbero non visualizzare i prodotti corretti o potrebbero non essere visualizzati affatto.
    *   **Valore consigliato:** Scegli l'ID che utilizzi in modo coerente nel tuo Catalogo prodotti di Facebook. `Reference` (SKU) è spesso una buona scelta se univoco.
    *   **Scenario / esempio del commerciante:** Il tuo Catalogo prodotti di Facebook utilizza lo SKU del tuo prodotto come identificatore univoco. Selezioni "Reference" qui per garantire una corrispondenza perfetta.
-   **Separatore:**

    *   **Cosa fa questa impostazione:** Se utilizzi una combinazione di ID prodotto e ID attributo (ad esempio, per diverse taglie/colori), questo definisce il carattere utilizzato per separarli nell'ID di Facebook.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato:* L'ID prodotto inviato a Facebook sarà `ProductID` + `Separatore` + `AttributeID`.
        *   *Quando vuoto:* Potrebbe essere inviato solo l'ID prodotto di base, causando potenzialmente problemi con il tracciamento di specifiche varianti di prodotto.
    *   **Valore consigliato:** Un separatore comune come `-` o `_`.
    *   **Scenario / esempio del commerciante:** Vendi una maglietta (ID 123) in diverse taglie (ID attributo 10 per S, 11 per M). Se imposti il separatore su `-`, Facebook riceverà `123-10` per una maglietta piccola.
-   **Prefisso ID prodotto / Suffisso ID prodotto:**

    *   **Cosa fa questa impostazione:** Ti consente di aggiungere testo prima o dopo l'ID prodotto inviato a Facebook. Questo è utile se gli ID del tuo Catalogo prodotti di Facebook hanno un formato specifico che differisce dagli ID del tuo PrestaShop.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato:* L'ID prodotto finale inviato a Facebook sarà `Prefisso` + `ProductID` + `Suffisso`.
        *   *Quando vuoto:* Viene inviato solo l'ID prodotto grezzo (e il separatore/ID attributo, se applicabile).
    *   **Valore consigliato:** Lasciare vuoto a meno che il tuo Catalogo prodotti di Facebook non lo richieda.
    *   **Scenario / esempio del commerciante:** Il tuo Catalogo prodotti di Facebook richiede che tutti gli ID prodotto inizino con "PS\_". Inserisci `PS_` nel campo "Prefisso ID prodotto".
-   **Valuta target:**

    *   **Cosa fa questa impostazione:** Specifica la valuta in cui i valori degli eventi (come l'importo dell'acquisto) vengono inviati a Facebook. Questo è cruciale per una reportistica accurata e l'ottimizzazione degli annunci, specialmente per i negozi multi-valuta.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato:* Tutti i valori degli eventi verranno convertiti e inviati in questa valuta target.
        *   *Quando vuoto:* Il modulo tenterà di utilizzare la valuta del contesto del negozio corrente o la valuta selezionata dal cliente.
    *   **Valore consigliato:** La tua valuta pubblicitaria principale (ad esempio, USD, EUR).
    *   **Scenario / esempio del commerciante:** Il tuo negozio vende in EUR, USD e GBP, ma tutti i tuoi annunci Facebook sono gestiti in USD. Imposti "Valuta target" su "USD" per garantire che tutti i valori di conversione siano riportati in modo coerente in USD.

#### Scheda Impostazioni di tracciamento eventi

Questa sezione ti consente di abilitare o disabilitare specifici eventi del Pixel di Facebook. Abilita solo gli eventi che desideri tracciare attivamente.

-   **Evento Pageview:**

    *   **Cosa fa questa impostazione:** Traccia quando un cliente visualizza qualsiasi pagina sul tuo sito web.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Un evento `PageView` viene inviato ad ogni caricamento di pagina.
        *   *Quando disabilitato:* Nessun evento `PageView` viene inviato.
    *   **Valore consigliato:** Sì. Questo è un evento fondamentale per tutti i tracciamenti.
-   **Evento Purchase:**

    *   **Cosa fa questa impostazione:** Traccia quando un cliente completa un acquisto. Questo è l'evento di conversione più critico.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Un evento `Purchase` viene inviato sulla pagina di conferma dell'ordine e/o tramite CAPI quando un ordine raggiunge uno "Stato pagato".
        *   *Quando disabilitato:* Nessun evento `Purchase` viene inviato.
    *   **Valore consigliato:** Sì. Assolutamente essenziale per la pubblicità e-commerce.
-   **Evento ViewContent:**

    *   **Cosa fa questa impostazione:** Traccia quando un cliente visualizza una pagina prodotto.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Un evento `ViewContent` viene inviato quando viene caricata una pagina prodotto.
        *   *Quando disabilitato:* Nessun evento `ViewContent` viene inviato.
    *   **Valore consigliato:** Sì. Importante per gli annunci dinamici di prodotti e il remarketing.
-   **Evento AddToCart:**

    *   **Cosa fa questa impostazione:** Traccia quando un cliente aggiunge un articolo al carrello.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Un evento `AddToCart` viene inviato quando un articolo viene aggiunto al carrello.
        *   *Quando disabilitato:* Nessun evento `AddToCart` viene inviato.
    *   **Valore consigliato:** Sì. Cruciale per le campagne di recupero carrelli abbandonati.
-   **Evento RemoveFromCart:**

    *   **Cosa fa questa impostazione:** Traccia quando un cliente rimuove un articolo dal carrello.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Un evento `RemoveFromCart` viene inviato quando un articolo viene rimosso.
        *   *Quando disabilitato:* Nessun evento `RemoveFromCart` viene inviato.
    *   **Valore consigliato:** Sì. Può fornire informazioni sul comportamento dei clienti e sull'interesse per i prodotti.
-   **Evento InitiateCheckout:**

    *   **Cosa fa questa impostazione:** Traccia quando un cliente inizia il processo di checkout.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Un evento `InitiateCheckout` viene inviato quando il cliente entra nel primo passaggio del checkout.
        *   *Quando disabilitato:* Nessun evento `InitiateCheckout` viene inviato.
    *   **Valore consigliato:** Sì. Utile per comprendere le prestazioni del funnel di checkout.
-   **Evento Search:**

    *   **Cosa fa questa impostazione:** Traccia quando un cliente utilizza la funzione di ricerca interna del tuo negozio.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Un evento `Search` viene inviato con la query di ricerca.
        *   *Quando disabilitato:* Nessun evento `Search` viene inviato.
    *   **Valore consigliato:** Sì. Fornisce dati preziosi su ciò che i clienti cercano.
-   **Evento AddToWishlist:**

    *   **Cosa fa questa impostazione:** Traccia quando un cliente aggiunge un prodotto alla sua lista dei desideri.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Viene inviato un evento `AddToWishlist`.
        *   *Quando disabilitato:* Nessun evento `AddToWishlist` viene inviato.
    *   **Valore consigliato:** Sì, se il tuo negozio utilizza una funzione lista dei desideri.
-   **Evento AddPaymentInfo:**

    *   **Cosa fa questa impostazione:** Traccia quando un cliente seleziona un metodo di pagamento durante il checkout.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Viene inviato un evento `AddPaymentInfo`.
        *   *Quando disabilitato:* Nessun evento `AddPaymentInfo` viene inviato.
    *   **Valore consigliato:** Sì. Aiuta ad analizzare le preferenze del metodo di pagamento e i potenziali abbandoni.
-   **Evento Contact:**

    *   **Cosa fa questa impostazione:** Traccia quando un cliente visita la tua pagina di contatto.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Viene inviato un evento `Contact`.
        *   *Quando disabilitato:* Nessun evento `Contact` viene inviato.
    *   **Valore consigliato:** Sì. Utile per tracciare le richieste di servizio clienti.
-   **Evento Lead:**

    *   **Cosa fa questa impostazione:** Traccia quando un cliente esegue un'azione che indica interesse per i tuoi prodotti o servizi, ma non è un acquisto diretto (ad esempio, iscrizione alla newsletter, creazione di un account).
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Un evento `Lead` viene inviato alla registrazione della newsletter e/o alla creazione dell'account.
        *   *Quando disabilitato:* Nessun evento `Lead` viene inviato.
    *   **Valore consigliato:** Sì. Importante per le campagne di generazione di lead.
-   **Evento CompleteRegistration:**

    *   **Cosa fa questa impostazione:** Traccia quando un cliente crea con successo un account sul tuo negozio.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Viene inviato un evento `CompleteRegistration`.
        *   *Quando disabilitato:* Nessun evento `CompleteRegistration` viene inviato.
    *   **Valore consigliato:** Sì. Utile per tracciare l'acquisizione di nuovi clienti.

#### Scheda Statistiche in tempo reale

Questa scheda fornisce informazioni in tempo reale sugli eventi inviati dal tuo negozio a Facebook, aiutandoti a monitorare lo stato del tuo pixel.

-   **Conserva gli eventi per (giorni):**

    *   **Cosa fa questa impostazione:** Determina per quanto tempo il modulo memorizza i dati degli eventi localmente per la visualizzazione nella scheda Statistiche in tempo reale.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato:* I dati degli eventi più vecchi di questo numero di giorni verranno automaticamente eliminati.
        *   *Quando impostato a 0:* Gli eventi non vengono memorizzati localmente (e le Statistiche in tempo reale non mostreranno dati).
    *   **Valore consigliato:** 7-30 giorni, a seconda di quanti dati storici desideri rivedere.
    *   **Scenario / esempio del commerciante:** Vuoi rivedere gli eventi dell'ultima settimana. Imposti questo valore a `7`.
-   **Intervallo di polling in tempo reale (secondi):**

    *   **Cosa fa questa impostazione:** Controlla la frequenza con cui la scheda Statistiche in tempo reale si aggiorna per mostrare nuovi eventi.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato:* La tabella delle Statistiche in tempo reale si aggiornerà ogni X secondi.
        *   *Quando impostato a 0:* Le Statistiche in tempo reale non si aggiorneranno automaticamente.
    *   **Valore consigliato:** 5-10 secondi per un monitoraggio attivo.
    *   **Scenario / esempio del commerciante:** Stai attivamente testando il tuo pixel e vuoi vedere gli eventi apparire quasi istantaneamente. Imposti questo valore a `5`.

#### Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Impostazioni generali | ID Pixel | Il tuo ID Pixel di Facebook | Collega il tuo negozio al Pixel di Facebook per il tracciamento. |
| Impostazioni generali | Token di accesso CAPI | Il tuo Token di accesso CAPI | Abilita il tracciamento lato server per una maggiore accuratezza dei dati. |
| Impostazioni generali | Codice evento di test | Vuoto (usare solo per test) | Invia eventi di test al Gestione eventi di Facebook. |
| Impostazioni generali | Modalità di consenso | Sì (per conformità GDPR) | Attiva gli eventi pixel solo dopo il consenso del cliente. |
| Impostazioni generali | Stati pagati | Pagamento accettato, Consegnato | Definisce quali stati dell'ordine attivano un evento "Purchase". |
| Impostazioni generali | Stati di rimborso / annullamento | Annullato, Rimborsato | Definisce quali stati dell'ordine sono considerati non acquisti. |
| Impostazioni avanzate | Selettore CSS aggiungi al carrello | Vuoto (rilevamento automatico) | Aiuta a identificare il pulsante "Aggiungi al carrello" per il tracciamento. |
| Impostazioni avanzate | Selettore CSS prezzo prodotto | Vuoto (rilevamento automatico) | Aiuta a identificare il prezzo del prodotto per i valori degli eventi. |
| Impostazioni avanzate | Identificazione prodotto | Riferimento (SKU) | Determina quale ID prodotto viene inviato a Facebook. |
| Impostazioni avanzate | Separatore | - (trattino) | Separatore per ID prodotto e ID attributo. |
| Impostazioni avanzate | Prefisso ID prodotto | Vuoto | Aggiunge un prefisso all'ID prodotto inviato a Facebook. |
| Impostazioni avanzate | Suffisso ID prodotto | Vuoto | Aggiunge un suffisso all'ID prodotto inviato a Facebook. |
| Impostazioni avanzate | Valuta target | La tua valuta pubblicitaria principale | Converte i valori degli eventi in una valuta specifica. |
| Tracciamento eventi | Evento Pageview | Sì | Traccia tutte le visualizzazioni di pagina. |
| Tracciamento eventi | Evento Purchase | Sì | Traccia gli acquisti completati. |
| Tracciamento eventi | Evento ViewContent | Sì | Traccia le visualizzazioni delle pagine prodotto. |
| Tracciamento eventi | Evento AddToCart | Sì | Traccia gli articoli aggiunti al carrello. |
| Tracciamento eventi | Evento RemoveFromCart | Sì | Traccia gli articoli rimossi dal carrello. |
| Tracciamento eventi | Evento InitiateCheckout | Sì | Traccia l'inizio del checkout. |
| Tracciamento eventi | Evento Search | Sì | Traccia le ricerche interne al sito. |
| Tracciamento eventi | Evento AddToWishlist | Sì (se la lista dei desideri è usata) | Traccia gli articoli aggiunti alla lista dei desideri. |
| Tracciamento eventi | Evento AddPaymentInfo | Sì | Traccia le informazioni di pagamento aggiunte durante il checkout. |
| Tracciamento eventi | Evento Contact | Sì | Traccia le visite alla pagina di contatto. |
| Tracciamento eventi | Evento Lead | Sì | Traccia le iscrizioni alla newsletter/creazioni di account. |
| Tracciamento eventi | Evento CompleteRegistration | Sì | Traccia le registrazioni di account riuscite. |
| Statistiche in tempo reale | Conserva gli eventi per (giorni) | 7-30 | Periodo di conservazione per i dati degli eventi locali. |
| Statistiche in tempo reale | Intervallo di polling in tempo reale (secondi) | 5-10 | Frequenza di aggiornamento per la visualizzazione delle Statistiche in tempo reale. |

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### AdminFbpixelAjaxController (Back Office > Moduli > Pixel di monitoraggio delle conversioni Fb > Scheda Statistiche in tempo reale)

Questo controller alimenta la scheda "Statistiche in tempo reale" all'interno della configurazione del modulo. Non ha una voce di menu separata ma è parte integrante dell'interfaccia di configurazione del modulo.

-   **Nome schermata e posizione menu:** Accessibile tramite **Moduli > Gestione moduli > Pixel di monitoraggio delle conversioni Fb > Configura**, quindi clicca sulla scheda **"Statistiche in tempo reale"**.
-   **Azioni e impostazioni disponibili:** Questa schermata visualizza una griglia o una tabella degli eventi recenti del Pixel di Facebook che sono stati attivati dal tuo negozio. Mostra dettagli come il nome dell'evento (ad esempio, `PageView`, `AddToCart`, `Purchase`), il timestamp, l'ID Pixel associato e spesso i parametri inviati con l'evento (ad esempio, ID prodotto, valore, valuta).
-   **Effetto delle modifiche:** Non ci sono "impostazioni" dirette da modificare su questa schermata. È uno strumento di monitoraggio. I dati visualizzati sono influenzati dalle impostazioni "Conserva gli eventi per (giorni)" e "Intervallo di polling in tempo reale (secondi)" sulla stessa pagina di configurazione.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Controlla regolarmente questa scheda, specialmente dopo aver apportato modifiche al tuo negozio o lanciato nuovi prodotti, per assicurarti che il tuo Pixel di Facebook si attivi correttamente e invii dati accurati. Questa è la tua prima linea di difesa per la risoluzione dei problemi del pixel prima di controllare il Gestione eventi di Facebook.

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: L'estensione Chrome "Facebook Pixel Helper" non mostra alcun pixel o errori. Cosa devo fare?**

-   **R:** Innanzitutto, assicurati di aver inserito correttamente i tuoi "ID Pixel" nella configurazione del modulo.
-   **R:** Controlla se la "Modalità di consenso" è abilitata. In tal caso, potresti dover accettare i cookie sul tuo storefront affinché il pixel si attivi.
-   **R:** Svuota la cache di PrestaShop (Parametri avanzati > Prestazioni > Svuota cache).
-   **R:** Se stai utilizzando un tema personalizzato, potrebbero esserci dei conflitti. Passa temporaneamente al tema predefinito di PrestaShop per escludere questa possibilità.
-   **R:** Utilizza lo strumento "Eventi di test" di Facebook in Gestione eventi per vedere se gli eventi vengono ricevuti.

**D2: I miei eventi di acquisto non vengono visualizzati correttamente nel Gestione eventi di Facebook.**

-   **R:** Verifica che i tuoi "Stati pagati" siano selezionati correttamente nella configurazione del modulo. Solo gli ordini che raggiungono questi stati attiveranno un evento di acquisto.
-   **R:** Se utilizzi CAPI, assicurati che il tuo "Token di accesso CAPI" sia corretto e testalo utilizzando la funzione "Codice evento di test".
-   **R:** Controlla se la tua "Valuta target" è impostata correttamente, specialmente per i negozi multi-valuta.
-   **R:** Rivedi la scheda "Statistiche in tempo reale" nella configurazione del modulo per vedere se il modulo sta registrando internamente gli eventi di acquisto.

**D3: Gli annunci dinamici di prodotti non mostrano i prodotti corretti o non mostrano affatto prodotti.**

-   **R:** La ragione più comune è una mancata corrispondenza tra l'impostazione "Identificazione prodotto" nel modulo e gli ID nel tuo Catalogo prodotti di Facebook. Assicurati che siano identici (ad esempio, se il tuo catalogo utilizza SKU, imposta il modulo su "Riferimento").
-   **R:** Assicurati che il tuo Catalogo prodotti di Facebook sia aggiornato e privo di errori.
-   **R:** Verifica che gli eventi "ViewContent" e "AddToCart" si attivino correttamente con il parametro `content_ids` che corrisponde agli ID del tuo catalogo.

**D4: Come posso garantire la conformità al GDPR o ad altre normative sulla privacy con questo modulo?**

-   **R:** Abilita l'impostazione "Modalità di consenso" nel modulo. Questo si integrerà con il tuo modulo di consenso ai cookie esistente (se configurato correttamente) per attivare il pixel solo dopo il consenso esplicito dell'utente.
-   **R:** Assicurati che la politica sulla privacy del tuo negozio dichiari chiaramente che utilizzi il Pixel di Facebook per la pubblicità e l'analisi, e come gli utenti possono disattivare o gestire le loro preferenze sui cookie.

**D5: L'evento "Aggiungi al carrello" non si attiva sulla mia pagina prodotto.**

-   **R:** Il tuo tema potrebbe avere un pulsante "Aggiungi al carrello" personalizzato che il modulo non riesce a rilevare automaticamente. Prova a ispezionare il pulsante "Aggiungi al carrello" sulla tua pagina prodotto utilizzando gli strumenti per sviluppatori del tuo browser (clic destro > Ispeziona) per trovare la sua classe o ID CSS. Quindi, inseriscilo nel campo "Selettore CSS aggiungi al carrello" nella configurazione del modulo (ad esempio, `.my-custom-atc-button` o `#add_to_cart_button`).

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo `Fb conversion tracking pixel` segue un'architettura standard dei moduli PrestaShop, sfruttando gli hook per l'iniezione di eventi nel front-office e un AdminController per le interazioni AJAX nel back-office (Statistiche in tempo reale). Si basa fortemente su un pattern factory (`FbpixelTrackerFactory`) per gestire diversi meccanismi di tracciamento (pixel lato browser, CAPI lato server). I dati degli eventi vengono raccolti e elaborati da classi dedicate (`FbpixelEvents`, `FbpixelPixelTracker`, `FbpixelCapiTracker`) e quindi inviati. La configurazione è memorizzata in `ps_configuration`. Il modulo include anche strumenti robusti per il debug e i controlli di integrità.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `controllers/front/ajax.php`
        -   **Nome classe:** `FbpixelAjaxModuleFrontController` (estende `ModuleFrontController`)
        -   **Responsabilità:** Gestisce le richieste AJAX dal front-office, principalmente per la raccolta e la registrazione dei dati degli eventi in tempo reale per la funzione Statistiche in tempo reale. Potrebbe anche essere utilizzato per trigger di eventi specifici che non possono essere gestiti puramente lato client (ad esempio, `RemoveFromCart` dopo un aggiornamento del carrello).
    -   `controllers/front/cron.php`
        -   **Nome classe:** `FbpixelCronModuleFrontController` (estende `ModuleFrontController`)
        -   **Responsabilità:** Progettato per essere chiamato da un cron job. Questo controller è probabilmente responsabile dell'elaborazione degli eventi CAPI in coda, dell'esecuzione della pulizia dei dati (ad esempio, l'eliminazione delle vecchie voci delle Statistiche in tempo reale) o di altre attività pianificate.
    -   `controllers/front/index.php`
        -   **Nome classe:** `FbpixelIndexModuleFrontController` (estende `ModuleFrontController`)
        -   **Responsabilità:** Un controller segnaposto o di fallback, spesso utilizzato per prevenire l'elenco delle directory o fornire una risposta predefinita per le rotte specifiche del modulo.
    -   `controllers/front/sync.php`
        -   **Nome classe:** `FbpixelSyncModuleFrontController` (estende `ModuleFrontController`)
        -   **Responsabilità:** Potrebbe gestire attività di sincronizzazione, come l'invio di aggiornamenti del catalogo prodotti o altri dati a Facebook, o la ricezione di dati da Facebook.
-   **Controller Admin Back-Office**:

    -   `controllers/admin/AdminFbpixelAjaxController.php`
        -   **Nome classe:** `AdminFbpixelAjaxController` (estende `ModuleAdminController`)
        -   **Nome scheda:** Non una scheda autonoma, ma integrata nella configurazione del modulo.
        -   **Entità gestita:** Gestisce le richieste AJAX dalla pagina di configurazione del back-office del modulo, in particolare per il recupero e la visualizzazione dei dati degli eventi delle "Statistiche in tempo reale". Fornisce i dati per il template `recent-events.tpl`.

### 4.3 Classi e modelli principali (`classes/`)

-   `fbpixel/classes/autoload.php`: Gestisce il caricamento delle classi personalizzate per il modulo.
-   `fbpixel/classes/FbpixelCapiClient.php`:
    -   **Responsabilità:** Incapsula la logica per effettuare richieste HTTP all'API delle conversioni di Facebook. Gestisce l'autenticazione, la formattazione delle richieste e la gestione degli errori.
-   `fbpixel/classes/FbpixelCapiTracker.php`:
    -   **Responsabilità:** Implementa l'`FbpixelTrackerInterface` per il tracciamento degli eventi lato server. Formatta i dati degli eventi secondo le specifiche CAPI e li invia tramite `FbpixelCapiClient`.
-   `fbpixel/classes/FbpixelCatalogDoctor.php`:
    -   **Responsabilità:** Fornisce strumenti e logica per diagnosticare problemi relativi alla corrispondenza del catalogo prodotti e alla coerenza dei dati tra PrestaShop e Facebook.
-   `fbpixel/classes/FbpixelConsent.php`:
    -   **Responsabilità:** Gestisce e controlla lo stato del consenso dell'utente, integrandosi con i meccanismi di consenso ai cookie di PrestaShop (se disponibili) per garantire la conformità al GDPR.
-   `fbpixel/classes/FbpixelCurrencyHelper.php`:
    -   **Responsabilità:** Classe di utilità per la conversione e la formattazione della valuta, garantendo che i valori degli eventi vengano inviati nella valuta target corretta.
-   `fbpixel/classes/FbpixelEmqCoach.php`:
    -   **Responsabilità:** Probabilmente fornisce indicazioni o raccomandazioni per migliorare la qualità della corrispondenza degli eventi (EMQ) per gli eventi di Facebook.
-   `fbpixel/classes/FbpixelEventId.php`:
    -   **Responsabilità:** Genera e gestisce ID evento univoci, cruciali per la deduplicazione tra eventi lato browser e lato server.
-   `fbpixel/classes/FbpixelEvents.php`:
    -   **Responsabilità:** Una classe centrale per la definizione e la gestione dei vari tipi di eventi del Pixel di Facebook (PageView, Purchase, AddToCart, ecc.) e dei loro parametri standard.
-   `fbpixel/classes/FbpixelHealthScore.php`:
    -   **Responsabilità:** Calcola e visualizza un "punteggio di salute" per la configurazione del pixel, identificando potenziali problemi o aree di miglioramento.
-   `fbpixel/classes/FbpixelLiveStats.php`:
    -   **Tabella del database:** `ps_fbpixel_events` (probabilmente, in base alla funzionalità)
    -   **Estende:** Probabilmente `ObjectModel`
    -   **Responsabilità:** Memorizza e recupera i dati degli eventi localmente per la funzione "Statistiche in tempo reale" nel back office. Gestisce la conservazione e l'eliminazione dei dati.
-   `fbpixel/classes/FbpixelPixelRules.php`:
    -   **Responsabilità:** Definisce regole e condizioni per quando specifici eventi pixel dovrebbero attivarsi, potenzialmente in base al tipo di pagina, alle azioni dell'utente o alla configurazione.
-   `fbpixel/classes/FbpixelPixelTracker.php`:
    -   **Responsabilità:** Implementa l'`FbpixelTrackerInterface` per il tracciamento degli eventi lato browser. Genera il codice JavaScript per le chiamate `fbq()` e lo inietta nel front office.
-   `fbpixel/classes/FbpixelProductIdResolver.php`:
    -   **Responsabilità:** Risolve l'ID prodotto e l'ID attributo corretti in base alla configurazione del modulo (prefisso, suffisso, separatore, tipo di ID scelto) per l'invio a Facebook.
-   `fbpixel/classes/FbpixelTrackerFactory.php`:
    -   **Responsabilità:** Una classe factory che istanzia il tracker appropriato (ad esempio, `FbpixelPixelTracker` per il browser, `FbpixelCapiTracker` per il server) in base alla configurazione e al contesto del modulo.
-   `fbpixel/classes/FbpixelTrackerInterface.php`:
    -   **Responsabilità:** Definisce un'interfaccia comune per tutte le classi di tracciamento, garantendo firme di metodo coerenti per l'invio degli eventi.
-   `fbpixel/classes/FbpixelUserData.php`:
    -   **Responsabilità:** Raccoglie e formatta i dati dell'utente (ad esempio, e-mail, telefono, indirizzo IP) per l'invio con gli eventi CAPI, cruciale per la qualità della corrispondenza degli eventi.
-   `fbpixel/classes/index.php`: File vuoto, tipicamente utilizzato per prevenire l'elenco delle directory.

### 4.4 Risorse JavaScript (`views/js/`)

-   `fbpixel/lib/searchTool/views/js/autocomplete.js`:
    -   **Ambito:** Back-office.
    -   **Dettagli:** Fornisce la funzionalità di completamento automatico per i campi di input, probabilmente utilizzata nella configurazione del modulo per selezionare prodotti, categorie o altre entità.
-   `fbpixel/views/js/fbpixel-admin.js`:
    -   **Ambito:** Back-office.
    -   **Dettagli:** Gestisce la logica amministrativa generale per la pagina di configurazione del modulo, inclusi l'invio di moduli, il cambio di scheda e potenzialmente le chiamate AJAX a `AdminFbpixelAjaxController`.
-   `fbpixel/views/js/fbpixel-debug.js`:
    -   **Ambito:** Front-office (condizionale).
    -   **Dettagli:** Fornisce informazioni di debug nella console del browser o in un overlay visivo, mostrando quali eventi pixel si stanno attivando e i loro parametri. Attivato da un'impostazione della modalità di debug.
-   `fbpixel/views/js/fbpixel-ghost.js`:
    -   **Ambito:** Front-office.
    -   **Dettagli:** Probabilmente uno script lato client che aiuta a rilevare e tracciare eventi che altrimenti potrebbero essere persi dall'osservazione DOM standard, come il caricamento di contenuti dinamici o interazioni AJAX specifiche.
-   `fbpixel/views/js/fbpixel-live.js`:
    -   **Ambito:** Back-office.
    -   **Dettagli:** Alimenta la scheda "Statistiche in tempo reale", effettuando richieste AJAX a `AdminFbpixelAjaxController` per recuperare e visualizzare i dati degli eventi in tempo reale e gestendo l'intervallo di polling.
-   `fbpixel/views/js/fbpixel-wizard.js`:
    -   **Ambito:** Back-office.
    -   **Dettagli:** Gestisce la procedura guidata di configurazione passo-passo, guidando il commerciante attraverso la configurazione iniziale.
-   `fbpixel/views/js/fbpixel.js`:
    -   **Ambito:** Front-office.
    -   **Dettagli:** Il JavaScript lato client principale per il Pixel di Facebook. Inizializza la funzione `fbq()`, gestisce i listener di eventi per `AddToCart`, `RemoveFromCart`, `Search`, `InitiateCheckout`, ecc., e invia gli eventi a Facebook. Gestisce anche i selettori CSS per gli elementi dinamici.
-   `fbpixel/views/js/mp-collect.js`:
    -   **Ambito:** Front-office.
    -   **Dettagli:** Probabilmente uno script di utilità per la raccolta di specifici punti dati dal front-office, possibilmente correlati al comportamento dell'utente o a fattori ambientali, per migliorare i parametri degli eventi.
-   `fbpixel/views/js/mp-front.js`:
    -   **Ambito:** Front-office.
    -   **Dettagli:** Utilità JavaScript generali del front-office o funzioni di supporto utilizzate dal modulo.
-   `fbpixel/views/js/mp-inspect.js`:
    -   **Ambito:** Front-office (condizionale).
    -   **Dettagli:** Fornisce uno strumento di ispezione, possibilmente un overlay visivo, per aiutare a eseguire il debug e verificare gli eventi pixel direttamente sullo storefront.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `fbpixel/lib/searchTool/views/css/autocomplete.css`:
    -   **Ambito:** Back-office.
    -   **Dettagli:** Stili per i menu a discesa di completamento automatico e i campi di input utilizzati nell'interfaccia di amministrazione.
-   `fbpixel/views/css/fbpixel-admin.css`:
    -   **Ambito:** Stile del modulo di amministrazione del back-office.
    -   **Dettagli:** Stila la pagina di configurazione del modulo, le schede, i campi di input e la tabella delle Statistiche in tempo reale.
-   `fbpixel/views/css/fbpixel-debug.css`:
    -   **Ambito:** Front-office (condizionale).
    -   **Dettagli:** Stili per l'overlay di debug o l'output della console, rendendo le informazioni di debug più leggibili.
-   `fbpixel/views/css/mp-inspect.css`:
    -   **Ambito:** Front-office (condizionale).
    -   **Dettagli:** Stili per lo strumento di ispezione del front-office, se abilitato.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**:

    -   `fbpixel/views/templates/hook/capi-pageview.tpl`: Renderizzato in un hook (probabilmente `displayHeader` o `actionFrontControllerSetMedia`) per attivare un evento `PageView` lato server tramite CAPI.
    -   `fbpixel/views/templates/hook/debug.tpl`: Renderizza l'overlay di debug o l'output della console per il debug del front-office.
    -   `fbpixel/views/templates/hook/displayOrderConfirmation.tpl`: Renderizza l'evento `Purchase` lato browser sulla pagina di conferma dell'ordine.
    -   `fbpixel/views/templates/hook/ghost.tpl`: Renderizza un elemento o script nascosto per la funzionalità `fbpixel-ghost.js`.
    -   `fbpixel/views/templates/hook/header.tpl`: Renderizza il codice di inizializzazione base del Pixel di Facebook (`fbq('init', ...)` e `fbq('track', 'PageView')`) all'interno della sezione `<head>`, tipicamente tramite `displayHeader` o `actionFrontControllerSetMedia`.
    -   `fbpixel/views/templates/hook/payment.tpl`: Potenzialmente utilizzato per tracciare eventi `AddPaymentInfo` o altre interazioni relative al pagamento.
    -   `fbpixel/views/templates/hook/product-details.tpl`: Renderizza script o dati specifici per le pagine prodotto, principalmente per gli eventi `ViewContent` e `AddToCart`, probabilmente iniettati tramite `displayProductFooter` o `displayProductAdditionalInfo`.
-   **Template admin (`views/templates/admin/`)**:

    -   `fbpixel/lib/searchTool/views/scripts.tpl`: Include JavaScript per lo strumento di ricerca/completamento automatico nell'amministrazione.
    -   `fbpixel/views/templates/admin/configure.tpl`: Il template principale per la pagina di configurazione del modulo, che orchestra tutti gli altri template di amministrazione.
    -   `fbpixel/views/templates/admin/doctor.tpl`: Visualizza i risultati di `FbpixelCatalogDoctor` per la diagnosi di problemi del catalogo.
    -   `fbpixel/views/templates/admin/emq.tpl`: Visualizza informazioni o raccomandazioni da `FbpixelEmqCoach` relative alla qualità della corrispondenza degli eventi.
    -   `fbpixel/views/templates/admin/health.tpl`: Visualizza il punteggio di salute del pixel da `FbpixelHealthScore`.
    -   `fbpixel/views/templates/admin/live-maintain.tpl`: Template per la gestione delle impostazioni delle statistiche in tempo reale (conservazione, intervallo di polling).
    -   `fbpixel/views/templates/admin/live.tpl`: Il template contenitore per la scheda "Statistiche in tempo reale".
    -   `fbpixel/views/templates/admin/mode-context.tpl`: Visualizza informazioni specifiche del contesto in base alla modalità operativa del pixel.
    -   `fbpixel/views/templates/admin/mode-note-capi.tpl`: Visualizza note o avvisi specifici per la configurazione CAPI.
    -   `fbpixel/views/templates/admin/mode-note-pixel.tpl`: Visualizza note o avvisi specifici per la configurazione del pixel lato browser.
    -   `fbpixel/views/templates/admin/mode-picker.tpl`: Consente al commerciante di selezionare la modalità operativa del pixel (ad esempio, standard, debug).
    -   `fbpixel/views/templates/admin/pixels-list.tpl`: Visualizza un elenco di ID pixel configurati.
    -   `fbpixel/views/templates/admin/recent-events.tpl`: Renderizza la tabella degli eventi recenti per la scheda "Statistiche in tempo reale", popolata da `AdminFbpixelAjaxController`.
    -   `fbpixel/views/templates/admin/tabs.tpl`: Renderizza la navigazione a schede per la pagina di configurazione del modulo.
    -   `fbpixel/views/templates/admin/wizard.tpl`: Renderizza l'interfaccia della procedura guidata di configurazione passo-passo.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   `ps_configuration`: Memorizza tutte le impostazioni del modulo (ad esempio, `FBPIXEL_ID`, `FBPIXEL_CAPI_TOKEN`, `FBPIXEL_PAID_STATUSES`).
    -   `ps_fbpixel_events` (probabilmente): Una tabella personalizzata creata dal modulo per memorizzare i log degli eventi locali per la funzione "Statistiche in tempo reale". Le colonne includerebbero tipicamente `id_fbpixel_event`, `pixel_id`, `event_name`, `event_data` (JSON), `timestamp`, `ip_address`, `user_agent`.
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionFrontControllerSetMedia` | Prima che il controller frontale renderizzi, per aggiungere JS/CSS. | Inietta il JS principale del Pixel di Facebook, gli script di tracciamento degli eventi e il CAPI PageView. |
| `displayContactContent` | Sulla pagina di contatto. | Attiva l'evento `Contact`. |
| `displayOrderConfirmation` | Sulla pagina di conferma dell'ordine. | Attiva l'evento `Purchase` lato browser. |
| `actionNewsletterRegistrationAfter` | Dopo l'iscrizione a una newsletter. | Attiva l'evento `Lead` (e potenzialmente `CompleteRegistration` se combinato). |
| `displayProductFooter` | In fondo alle pagine prodotto. | Inietta dati specifici del prodotto e l'evento `ViewContent`. |
| `displayHeader` | Nella sezione `<head>` di tutte le pagine del front-office. | Inietta il codice base del Pixel di Facebook e l'evento `PageView`. |
| `DisplayProductButtons` | Vicino ai pulsanti di azione del prodotto (ad esempio, Aggiungi al carrello). | Potrebbe iniettare JS per il listener dell'evento `AddToCart`. |
| `ActionObjectProductInCartDeleteBefore` | Prima che un prodotto venga rimosso dal carrello. | Potenzialmente attiva l'evento `RemoveFromCart`. |
| `DisplayProductAdditionalInfo` | Nel blocco informazioni prodotto. | Iniezione di dati aggiuntivi del prodotto o trigger di eventi. |
| `ActionCronJob` | Durante l'esecuzione di un cron job pianificato. | Attiva l'elaborazione degli eventi CAPI, la pulizia dei dati. |
| `ActionObjectProductInCartDeleteAfter` | Dopo che un prodotto viene rimosso dal carrello. | Attiva l'evento `RemoveFromCart`. |
| `ActionValidateOrder` | Dopo che un ordine è stato validato con successo. | Attiva l'evento `Purchase` lato server tramite CAPI. |
| `DisplayLeftColumnProduct` | Nella colonna sinistra delle pagine prodotto. | Meno comune per il pixel, forse per eventi specifici relativi al prodotto. |
| `displayExtraLeft` | Nella colonna extra sinistra. | Meno comune per il pixel, forse per eventi specifici relativi al prodotto. |
| `ActionCartUpdateQuantityBefore` | Prima che la quantità del carrello venga aggiornata. | Potenzialmente utilizzato per tracciare modifiche che potrebbero portare a `RemoveFromCart`. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, accedi al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda relativa al modulo "Pixel di monitoraggio delle conversioni Fb".
