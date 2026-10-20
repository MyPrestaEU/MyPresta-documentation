---
title: "Coupon popup responsive - Manuale per il commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Coupon popup responsive di MyPresta.eu."
sidebar:
  label: "Coupon popup responsive - Manuale per il commerciara e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Responsive popup coupons su MyPresta.eu](https://mypresta.eu/modules/social-networks/responsive-popup-coupons.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/responsive-popup-coupons/)
>
> ---


# Coupon popup responsive

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 1.6.x, 1.5.x, 1.4.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti e di solito abilitate per impostazione predefinita nella maggior parte degli ambienti di hosting.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale dove imposterai tutti i parametri per i tuoi coupon popup.

#### Impostazioni generali

-   **Abilita modulo:**

    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare l'intera funzionalità dei coupon popup per il tuo negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il popup inizierà ad apparire sulle pagine selezionate in base alle altre impostazioni.
        -   *Quando disabilitato:* Il popup non apparirà in nessun punto del tuo negozio, indipendentemente dalle altre impostazioni.
    -   **Valore consigliato:** SÌ (quando vuoi usare il modulo).
    -   **Scenario/esempio del commerciante:** Stai gestendo una promozione per le vacanze e vuoi attivare il popup per un tempo limitato. Lo abiliti all'inizio e lo disabiliti una volta terminata la promozione.
-   **Visualizza su:**

    -   **Cosa fa questa impostazione:** Ti permette di scegliere su quali tipi di pagine il popup verrà mostrato ai tuoi clienti.
    -   **Effetto della modifica di questa impostazione:**
        -   *Homepage:* Il popup appare solo sulla pagina principale del tuo negozio.
        -   *Pagine di categoria:* Il popup appare quando i clienti navigano tra le categorie di prodotti.
        -   *Pagine prodotto:* Il popup appare quando i clienti visualizzano i dettagli dei singoli prodotti.
        -   *Pagine CMS:* Il popup appare su pagine informative come "Chi siamo" o "Contatti".
        -   *Tutte le pagine:* Il popup appare su ogni pagina del tuo negozio.
    -   **Valore consigliato:** Pagine prodotto o Tutte le pagine (a seconda della tua strategia di marketing).
    -   **Scenario/esempio del commerciante:** Vuoi incoraggiare gli acquisti direttamente sulle pagine prodotto, quindi selezioni "Pagine prodotto". Se vuoi la massima esposizione, potresti scegliere "Tutte le pagine".
-   **Ritardo (in secondi) prima che il popup appaia:**

    -   **Cosa fa questa impostazione:** Controlla quanto tempo dopo il caricamento di una pagina il popup aspetterà prima di apparire.
    -   **Effetto della modifica di questa impostazione:**
        -   *Impostato a 0:* Il popup appare immediatamente al caricamento della pagina.
        -   *Impostato a 5:* Il popup appare 5 secondi dopo il caricamento della pagina.
    -   **Valore consigliato:** 3-5 secondi (permette ai clienti di vedere prima il contenuto).
    -   **Scenario/esempio del commerciante:** Non vuoi sopraffare immediatamente i clienti. Impostare un ritardo di 3 secondi dà loro un momento per orientarsi prima che appaia l'offerta.
-   **Visualizza popup solo una volta per sessione:**

    -   **Cosa fa questa impostazione:** Determina se un cliente vedrà il popup più volte durante una singola visita al tuo negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Una volta che un cliente vede il popup (e potenzialmente lo chiude), non lo vedrà più finché non chiuderà il browser e inizierà una nuova sessione.
        -   *Quando disabilitato:* Il popup potrebbe apparire ogni volta che visitano una pagina in cui è configurato per essere visualizzato.
    -   **Valore consigliato:** SÌ (per evitare di infastidire i clienti).
    -   **Scenario/esempio del commerciante:** Un cliente visita diverse pagine prodotto. Se questa opzione è abilitata, vedrà l'offerta del coupon solo una volta, prevenendo l'irritazione.
-   **Visualizza popup solo una volta per cliente (per sempre):**

    -   **Cosa fa questa impostazione:** Questa è un'impostazione più permanente, che impedisce a un cliente loggato di vedere nuovamente il popup una volta che lo ha visto.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il modulo ricorda che un cliente specifico (tramite il suo account) ha visto il popup e non glielo mostrerà più, anche in sessioni future.
        -   *Quando disabilitato:* Si applica la regola "una volta per sessione", o se questa è disattivata, lo vedranno ripetutamente.
    -   **Valore consigliato:** SÌ (per un'esperienza meno intrusiva per i clienti fedeli).
    -   **Scenario/esempio del commerciante:** Vuoi dare a ogni cliente la possibilità di ottenere il coupon, ma non ricordarglielo costantemente se lo ha già visto o usato.
-   **Visualizza popup solo per gli ospiti (clienti non loggati):**

    -   **Cosa fa questa impostazione:** Limita la visibilità del popup solo ai visitatori che non sono loggati in un account cliente.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Solo i visitatori nuovi o di ritorno non loggati vedranno il popup. I clienti loggati non lo vedranno.
        -   *Quando disabilitato:* Sia gli ospiti che i clienti loggati vedranno il popup (soggetto ad altre regole di visualizzazione).
    -   **Valore consigliato:** SÌ (spesso, si desidera convertire nuovi visitatori, non necessariamente offrire sconti ai clienti fedeli esistenti).
    -   **Scenario/esempio del commerciante:** Il tuo obiettivo è attrarre nuovi clienti o incoraggiare i primi acquisti. Abiliti questa opzione per concentrare la tua offerta su potenziali nuovi clienti.
-   **Visualizza popup solo per gruppi di clienti selezionati:**

    -   **Cosa fa questa impostazione:** Ti permette di indirizzare gruppi specifici di clienti (ad esempio, "Visitatori", "Clienti", "Ospiti" o gruppi personalizzati che hai creato) con il popup.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando sono selezionati gruppi specifici:* Solo i clienti appartenenti a quei gruppi vedranno il popup.
        -   *Quando non sono selezionati gruppi (o sono selezionati tutti):* Tutti i clienti vedranno il popup (soggetto ad altre regole).
    -   **Valore consigliato:** Seleziona "Ospiti" e "Visitatori" se il tuo obiettivo è l'acquisizione di nuovi clienti.
    -   **Scenario/esempio del commerciante:** Vuoi offrire uno sconto speciale solo al tuo gruppo di clienti VIP. Selezioneresti solo quel gruppo qui.
-   **Visualizza popup solo per paesi selezionati:**

    -   **Cosa fa questa impostazione:** Limita l'apparizione del popup in base alla posizione geografica del cliente.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando sono selezionati paesi specifici:* Solo i clienti di quei paesi vedranno il popup.
        -   *Quando non sono selezionati paesi (o sono selezionati tutti):* Tutti i clienti vedranno il popup.
    -   **Valore consigliato:** Seleziona paesi specifici se hai promozioni geo-mirate, altrimenti lascia vuoto.
    -   **Scenario/esempio del commerciante:** Stai gestendo una promozione esclusiva per i clienti in Francia e Germania. Selezioneresti solo questi due paesi.
-   **Visualizza popup solo per valute selezionate:**

    -   **Cosa fa questa impostazione:** Controlla la visibilità del popup in base alla valuta che il cliente sta attualmente utilizzando nel tuo negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando sono selezionate valute specifiche:* Solo i clienti che utilizzano quelle valute vedranno il popup.
        -   *Quando non sono selezionate valute (o sono selezionate tutte):* Tutti i clienti vedranno il popup.
    -   **Valore consigliato:** Seleziona valute specifiche se la tua promozione dipende dalla valuta, altrimenti lascia vuoto.
    -   **Scenario/esempio del commerciante:** Hai un'offerta speciale per i clienti che pagano in USD. Selezioneresti solo USD qui.
-   **Visualizza popup solo per lingue selezionate:**

    -   **Cosa fa questa impostazione:** Determina se il popup appare in base alla lingua che il cliente ha selezionato per il tuo negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando sono selezionate lingue specifiche:* Solo i clienti che visualizzano il tuo negozio in quelle lingue vedranno il popup.
        -   *Quando non sono selezionate lingue (o sono selezionate tutte):* Tutti i clienti vedranno il popup.
    -   **Valore consigliato:** Seleziona lingue specifiche se il contenuto del tuo popup è tradotto solo per alcune lingue, altrimenti lascia vuoto.
    -   **Scenario/esempio del commerciante:** Il tuo messaggio popup è disponibile solo in inglese e spagnolo. Selezioneresti queste due lingue per assicurarti che i clienti vedano un messaggio pertinente.

#### Impostazioni coupon

-   **Valore del buono:**

    -   **Cosa fa questa impostazione:** Definisce l'importo o la percentuale di sconto offerta dal coupon.
    -   **Effetto della modifica di questa impostazione:**
        -   *Impostato a 10:* Il coupon fornirà uno sconto di 10 unità (ad esempio, $10, €10).
        -   *Impostato a 15%:* Il coupon fornirà uno sconto del 15%.
    -   **Valore consigliato:** Uno sconto interessante (ad esempio, 10%, $5, €10).
    -   **Scenario/esempio del commerciante:** Vuoi offrire uno sconto del 10%, quindi inserisci "10%" qui.
-   **Tipo di buono:**

    -   **Cosa fa questa impostazione:** Specifica se il buono è un importo fisso o una percentuale.
    -   **Effetto della modifica di questa impostazione:**
        -   *Percentuale:* Il "Valore del buono" sarà trattato come una percentuale del totale dell'ordine.
        -   *Importo:* Il "Valore del buono" sarà trattato come una deduzione monetaria fissa.
    -   **Valore consigliato:** Percentuale (spesso più attraente per ordini di dimensioni variabili).
    -   **Scenario/esempio del commerciante:** Vuoi dare il 10% di sconto, quindi selezioni "Percentuale". Se vuoi dare uno sconto fisso di $5, selezioni "Importo".
-   **Importo minimo del buono:**

    -   **Cosa fa questa impostazione:** Imposta un valore minimo dell'ordine che un cliente deve raggiungere per poter utilizzare il coupon.
    -   **Effetto della modifica di questa impostazione:**
        -   *Impostato a 50:* Il coupon può essere utilizzato solo se il totale del carrello è di $50 o più.
        -   *Impostato a 0 (o vuoto):* Non è richiesto alcun importo minimo dell'ordine.
    -   **Valore consigliato:** Un minimo ragionevole per proteggere i tuoi margini, o 0 se vuoi incoraggiare qualsiasi acquisto.
    -   **Scenario/esempio del commerciante:** Vuoi assicurarti che lo sconto venga applicato solo agli ordini superiori a $50, quindi inserisci "50".
-   **Scadenza del buono (in giorni):**

    -   **Cosa fa questa impostazione:** Definisce quanti giorni il codice coupon generato sarà valido dal momento in cui viene emesso.
    -   **Effetto della modifica di questa impostazione:**
        -   *Impostato a 7:* Il coupon scadrà 7 giorni dopo che il cliente lo riceve.
        -   *Impostato a 0 (o vuoto):* Il coupon non scadrà.
    -   **Valore consigliato:** 7-30 giorni (crea urgenza senza essere troppo restrittivo).
    -   **Scenario/esempio del commerciante:** Vuoi che i clienti utilizzino il coupon rapidamente, quindi imposti una scadenza di 7 giorni.
-   **Descrizione del buono:**

    -   **Cosa fa questa impostazione:** Fornisce un nome descrittivo per il coupon nel tuo back office di PrestaShop (ad esempio, nella sezione "Regole carrello"). Questo è per il tuo riferimento interno.
    -   **Effetto della modifica di questa impostazione:** Questo testo apparirà nel tuo pannello di amministrazione di PrestaShop quando visualizzi le regole del carrello generate, aiutandoti a identificarne l'origine. Non appare al cliente.
    -   **Valore consigliato:** "Coupon Popup - [Data]" o "Sconto Mi piace Facebook".
    -   **Scenario/esempio del commerciante:** Inserisci "Sconto Popup Mi piace Facebook" in modo da sapere esattamente da dove provengono questi coupon quando rivedi le tue regole del carrello.
-   **Spedizione gratuita con buono:**

    -   **Cosa fa questa impostazione:** Determina se il coupon concede anche la spedizione gratuita sull'ordine.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Al cliente non verrà addebitata la spedizione quando utilizza questo coupon.
        -   *Quando disabilitato:* Si applicheranno i costi di spedizione standard.
    -   **Valore consigliato:** NO (a meno che tu non voglia offrire la spedizione gratuita come forte incentivo).
    -   **Scenario/esempio del commerciante:** Vuoi offrire un'offerta molto attraente, quindi abiliti la spedizione gratuita insieme allo sconto.
-   **Buono applicabile a prodotti specifici:**

    -   **Cosa fa questa impostazione:** Ti permette di limitare l'utilizzo del coupon solo a determinati prodotti nel tuo negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando sono selezionati prodotti specifici:* Il coupon funzionerà solo se quei prodotti sono nel carrello.
        -   *Quando non sono selezionati prodotti:* Il coupon si applica a tutti i prodotti nel carrello.
    -   **Valore consigliato:** Lascia vuoto a meno che tu non abbia una promozione specifica per un prodotto.
    -   **Scenario/esempio del commerciante:** Stai promuovendo una nuova linea di scarpe. Selezioni solo quelle scarpe qui, in modo che il coupon funzioni solo per esse.
-   **Buono applicabile a categorie specifiche:**

    -   **Cosa fa questa impostazione:** Ti permette di limitare l'utilizzo del coupon ai prodotti all'interno di categorie specifiche.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando sono selezionate categorie specifiche:* Il coupon funzionerà solo se i prodotti di quelle categorie sono nel carrello.
        -   *Quando non sono selezionate categorie:* Il coupon si applica a tutti i prodotti.
    -   **Valore consigliato:** Lascia vuoto a meno che tu non abbia una promozione specifica per una categoria.
    -   **Scenario/esempio del commerciante:** Vuoi svuotare il vecchio stock nella tua categoria "Collezione estiva". Selezioni quella categoria qui.
-   **Buono applicabile a produttori specifici:**

    -   **Cosa fa questa impostazione:** Ti permette di limitare l'utilizzo del coupon ai prodotti di marchi/produttori specifici.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando sono selezionati produttori specifici:* Il coupon funzionerà solo se i prodotti di quei produttori sono nel carrello.
        -   *Quando non sono selezionati produttori:* Il coupon si applica a tutti i prodotti.
    -   **Valore consigliato:** Lascia vuoto a meno che tu non abbia una promozione specifica per un marchio.
    -   **Scenario/esempio del commerciante:** Hai una partnership con un marchio specifico e vuoi offrire uno sconto solo sui loro prodotti.

#### Design e contenuto del popup

-   **Larghezza popup (in pixel):**

    -   **Cosa fa questa impostazione:** Controlla la dimensione orizzontale della finestra popup.
    -   **Effetto della modifica di questa impostazione:** Un numero maggiore rende il popup più largo, un numero minore lo rende più stretto.
    -   **Valore consigliato:** 600px - 800px (per una buona visibilità su desktop, il design responsive gestirà il mobile).
    -   **Scenario/esempio del commerciante:** Vuoi che il popup sia prominente ma non troppo largo, quindi lo imposti a 700px.
-   **Colore di sfondo del popup:**

    -   **Cosa fa questa impostazione:** Imposta il colore di sfondo della finestra popup.
    -   **Effetto della modifica di questa impostazione:** Cambia l'aspetto visivo del popup per abbinarlo al tuo brand o farlo risaltare.
    -   **Valore consigliato:** Un colore che contrasti bene con il tuo testo e il tuo brand (ad esempio, #FFFFFF per il bianco, #F0F0F0 per il grigio chiaro).
    -   **Scenario/esempio del commerciante:** Il tuo brand usa molto blu, quindi scegli un codice esadecimale blu chiaro come #E0F2F7.
-   **Colore del testo del popup:**

    -   **Cosa fa questa impostazione:** Imposta il colore del testo visualizzato all'interno del popup.
    -   **Effetto della modifica di questa impostazione:** Garantisce la leggibilità rispetto al colore di sfondo scelto.
    -   **Valore consigliato:** Un colore che fornisca un buon contrasto (ad esempio, #000000 per il nero, #333333 per il grigio scuro).
    -   **Scenario/esempio del commerciante:** Con uno sfondo chiaro, scegli un colore di testo scuro come #333333 per una leggibilità ottimale.
-   **Colore del bordo del popup:**

    -   **Cosa fa questa impostazione:** Imposta il colore del bordo attorno alla finestra popup.
    -   **Effetto della modifica di questa impostazione:** Aggiunge una cornice visiva al popup.
    -   **Valore consigliato:** Un colore tenue che si abbini al tuo design o un colore forte per farlo risaltare (ad esempio, #CCCCCC per il grigio chiaro, o il colore accentato del tuo brand).
    -   **Scenario/esempio del commerciante:** Vuoi un aspetto pulito, quindi scegli un bordo grigio tenue #DDDDDD.
-   **Larghezza del bordo del popup (in pixel):**

    -   **Cosa fa questa impostazione:** Controlla lo spessore del bordo del popup.
    -   **Effetto della modifica di questa impostazione:** Un numero più alto rende il bordo più spesso.
    -   **Valore consigliato:** 1-3px.
    -   **Scenario/esempio del commerciante:** Vuoi un bordo sottile ed elegante, quindi lo imposti a 1px.
-   **Raggio del bordo del popup (in pixel):**

    -   **Cosa fa questa impostazione:** Controlla l'arrotondamento degli angoli del popup.
    -   **Effetto della modifica di questa impostazione:**
        -   *Impostato a 0:* Angoli netti e squadrati.
        -   *Impostato a 10:* Angoli leggermente arrotondati.
        -   *Impostato a 50 (o superiore):* Angoli molto arrotondati, a forma di pillola.
    -   **Valore consigliato:** 5-10px (per un aspetto moderno e morbido).
    -   **Scenario/esempio del commerciante:** Preferisci un'estetica più morbida, quindi imposti il raggio del bordo a 8px.
-   **Ombra del popup:**

    -   **Cosa fa questa impostazione:** Aggiunge un effetto ombra attorno al popup, facendolo apparire come se fluttuasse sopra la pagina.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il popup avrà un'ombra sottile, conferendogli profondità.
        -   *Quando disabilitato:* Il popup non avrà ombra.
    -   **Valore consigliato:** SÌ (aggiunge un tocco professionale e moderno).
    -   **Scenario/esempio del commerciante:** Vuoi che il popup si distingua visivamente dallo sfondo, quindi abiliti l'ombra.
-   **Colore del pulsante di chiusura del popup:**

    -   **Cosa fa questa impostazione:** Imposta il colore del pulsante 'X' che i clienti usano per chiudere il popup.
    -   **Effetto della modifica di questa impostazione:** Assicura che il pulsante di chiusura sia visibile e si abbini al tuo design.
    -   **Valore consigliato:** Un colore contrastante per la visibilità (ad esempio, #000000, #FF0000).
    -   **Scenario/esempio del commerciante:** Vuoi che il pulsante di chiusura sia chiaramente visibile, quindi lo imposti a nero #000000.
-   **Contenuto del popup (HTML consentito):**

    -   **Cosa fa questa impostazione:** Qui inserisci il messaggio principale e il contenuto per il tuo popup. Puoi usare HTML per formattare il testo, aggiungere immagini e includere i tuoi pulsanti social media.
    -   **Effetto della modifica di questa impostazione:** Questo testo e HTML verranno visualizzati all'interno del popup.
    -   **Valore consigliato:** Messaggio chiaro e conciso con una forte call to action. Includi il codice del tuo pulsante "Mi piace" di Facebook o un widget social media simile.
    -   **Scenario/esempio del commerciante:** Potresti inserire: `<p>Metti "Mi piace" su Facebook e ottieni il <strong>10% DI SCONTO</strong> sul tuo prossimo ordine!</p><div class="fb-like" data-href="URL_TUA_PAGINA_FACEBOOK" data-layout="button_count" data-action="like" data-size="large" data-show-faces="false" data-share="false"></div>` (Ricorda di sostituire `URL_TUA_PAGINA_FACEBOOK`).
-   **Messaggio coupon popup (HTML consentito):**

    -   **Cosa fa questa impostazione:** Questo è il messaggio visualizzato *dopo* che il cliente esegue l'azione richiesta (ad esempio, mette "Mi piace" alla tua pagina) e riceve il suo codice coupon.
    -   **Effetto della modifica di questa impostazione:** Questo messaggio apparirà nel popup, tipicamente sopra il codice coupon generato.
    -   **Valore consigliato:** Un messaggio di ringraziamento e istruzioni su come utilizzare il coupon.
    -   **Scenario/esempio del commerciante:** Potresti inserire: `<p>Grazie per averci messo "Mi piace"! Ecco il tuo codice sconto esclusivo:</p><p>Usa il codice <strong>{coupon_code}</strong> al checkout.</p>` (Il segnaposto `{coupon_code}` verrà automaticamente sostituito).

#### Impostazioni avanzate

-   **Codice CSS personalizzato:**

    -   **Cosa fa questa impostazione:** Ti permette di aggiungere le tue regole CSS personalizzate per stilizzare ulteriormente il popup o sovrascrivere gli stili predefiniti.
    -   **Effetto della modifica di questa impostazione:** Qualsiasi CSS che inserisci qui verrà applicato al popup, dandoti un controllo granulare sul suo aspetto.
    -   **Valore consigliato:** Lascia vuoto a meno che tu non abbia esigenze di stile specifiche.
    -   **Scenario/esempio del commerciante:** Vuoi cambiare la dimensione del carattere del codice coupon. Potresti aggiungere: `.coupon-code { font-size: 24px !important; }`
-   **Codice JavaScript personalizzato:**

    -   **Cosa fa questa impostazione:** Ti permette di aggiungere il tuo codice JavaScript personalizzato per interagire con il popup o integrarlo con altri servizi.
    -   **Effetto della modifica di questa impostazione:** Qualsiasi JavaScript che inserisci qui verrà eseguito quando il popup viene visualizzato o interagito.
    -   **Valore consigliato:** Lascia vuoto a meno che tu non abbia esigenze di scripting specifiche (ad esempio, tracciamento eventi di Google Analytics).
    -   **Scenario/esempio del commerciante:** Vuoi inviare un evento a Google Analytics quando il popup viene visualizzato. Potresti aggiungere: `ga('send', 'event', 'Popup', 'Displayed', 'Coupon Offer');`

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Configurazione modulo** | Abilita modulo | SÌ | Interruttore principale per la funzionalità del popup. |
| | Visualizza su | Pagine prodotto / Tutte le pagine | Seleziona dove appare il popup (Homepage, Categoria, Prodotto, CMS, Tutte). |
| | Ritardo (in secondi) prima che il popup appaia | 3-5 secondi | Tempo prima che il popup venga mostrato dopo il caricamento della pagina. |
| | Visualizza popup solo una volta per sessione | SÌ | Impedisce al popup di essere mostrato più volte in una sessione del browser. |
| | Visualizza popup solo una volta per cliente (per sempre) | SÌ | Impedisce ai clienti loggati di vedere nuovamente il popup. |
| | Visualizza popup solo per gli ospiti | SÌ | Si rivolge ai visitatori non loggati. |
| | Visualizza popup solo per gruppi di clienti selezionati | Ospiti, Visitatori | Limita il popup a specifici gruppi di clienti. |
| | Visualizza popup solo per paesi selezionati | Lascia vuoto | Limita il popup a specifici paesi. |
| | Visualizza popup solo per valute selezionate | Lascia vuoto | Limita il popup a specifiche valute. |
| | Visualizza popup solo per lingue selezionate | Lascia vuoto | Limita il popup a specifiche lingue. |
| | Valore del buono | es., 10% | L'importo o la percentuale di sconto. |
| | Tipo di buono | Percentuale / Importo | Definisce se il buono è in % o importo fisso. |
| | Importo minimo del buono | 0 (o valore ragionevole) | Valore minimo dell'ordine per l'utilizzo del coupon. |
| | Scadenza del buono (in giorni) | 7-30 giorni | Periodo di validità del coupon generato. |
| | Descrizione del buono | "Sconto Popup Mi piace Facebook" | Nome interno per il coupon nel BO. |
| | Spedizione gratuita con buono | NO | Concede la spedizione gratuita con il coupon. |
| | Buono applicabile a prodotti specifici | Lascia vuoto | Limita il coupon a prodotti specifici. |
| | Buono applicabile a categorie specifiche | Lascia vuoto | Limita il coupon a categorie specifiche. |
| | Buono applicabile a produttori specifici | Lascia vuoto | Limita il coupon a produttori specifici. |
| | Larghezza popup (in pixel) | 600px - 800px | Dimensione orizzontale del popup. |
| | Colore di sfondo del popup | #FFFFFF (bianco) | Colore di sfondo del popup. |
| | Colore del testo del popup | #000000 (nero) | Colore del testo all'interno del popup. |
| | Colore del bordo del popup | #DDDDDD (grigio chiaro) | Colore del bordo del popup. |
| | Larghezza del bordo del popup (in pixel) | 1-3px | Spessore del bordo del popup. |
| | Raggio del bordo del popup (in pixel) | 5-10px | Arrotondamento degli angoli del popup. |
| | Ombra del popup | SÌ | Aggiunge un effetto ombra al popup. |
| | Colore del pulsante di chiusura del popup | #000000 (nero) | Colore del pulsante di chiusura 'X'. |
| | Contenuto del popup (HTML consentito) | Messaggio coinvolgente + widget social | Contenuto principale visualizzato nel popup. |
| | Messaggio coupon popup (HTML consentito) | Messaggio di ringraziamento + {coupon\_code} | Messaggio visualizzato dopo la generazione del coupon. |
| | Codice CSS personalizzato | Lascia vuoto | Aggiungi stili CSS personalizzati. |
| | Codice JavaScript personalizzato | Lascia vuoto | Aggiungi JavaScript personalizzato. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Il popup non appare nel mio negozio. Cosa devo controllare per prima cosa?**
R1:

-   **Il modulo è abilitato?** Vai su **Moduli > Gestione moduli** e assicurati che "Coupon popup responsive" sia installato e abilitato.
-   **Controlla l'impostazione "Abilita modulo":** Nella configurazione del modulo, assicurati che l'interruttore "Abilita modulo" sia impostato su SÌ.
-   **Verifica le impostazioni "Visualizza su":** Assicurati di aver selezionato i tipi di pagina corretti (ad esempio, Homepage, Pagine prodotto) dove ti aspetti che il popup appaia.
-   **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti). Potrebbe essere necessario svuotare anche la cache del browser (Ctrl+F5 o Cmd+Shift+R).
-   **Verifica la presenza di conflitti:** Disabilita temporaneamente altri moduli che potrebbero interagire con i popup o il contenuto della pagina per escludere conflitti.

**D2: Il popup appare, ma il pulsante "Mi piace" di Facebook (o altro widget social) non funziona o non viene visualizzato correttamente.**
R2:

-   **HTML errato:** Ricontrolla il codice HTML che hai inserito nel campo "Contenuto del popup". Anche un piccolo errore di battitura può romperlo. Assicurati che l'URL della tua pagina Facebook sia corretto.
-   **Facebook SDK:** Affinché i pulsanti "Mi piace" di Facebook funzionino, l'SDK JavaScript di Facebook deve essere caricato. I temi di PrestaShop spesso lo includono, ma in caso contrario, potresti doverlo aggiungere tramite codice personalizzato o assicurarti che il tuo tema lo supporti.
-   **Ad Blocker:** Alcuni ad blocker potrebbero impedire il caricamento dei widget social. Prova in una finestra in incognito senza estensioni.

**D3: Il codice coupon viene generato, ma non funziona al checkout.**
R3:

-   **Controlla le impostazioni del coupon:** Rivedi tutte le impostazioni "Buono" nella configurazione del modulo:
    -   **Importo minimo:** Il valore del carrello del cliente è superiore all'"Importo minimo del buono"?
    -   **Scadenza:** La data di "Scadenza del buono" è passata?
    -   **Prodotti/categorie/produttori specifici:** Il carrello del cliente contiene gli articoli richiesti se queste impostazioni vengono utilizzate?
    -   **Gruppi di clienti/paesi/valute/lingue:** Il cliente soddisfa i criteri impostati per queste restrizioni?
-   **Regole carrello PrestaShop:** Il modulo crea una "Regola carrello" in PrestaShop. Vai su **Catalogo > Sconti > Regole carrello** (o **Regole prezzo > Regole carrello** nelle versioni precedenti) e cerca il codice coupon. Controlla i suoi dettagli per vedere se sono state applicate restrizioni in modo errato.

**D4: Il design del popup non si abbina perfettamente al tema del mio negozio.**
R4:

-   **Usa le impostazioni di design del modulo:** Regola "Colore di sfondo del popup", "Colore del testo del popup", "Colore del bordo del popup", "Larghezza del bordo del popup" e "Raggio del bordo del popup" per abbinarli meglio al tuo tema.
-   **CSS personalizzato:** Per uno stile più avanzato, usa il campo "Codice CSS personalizzato" nella configurazione del modulo. Puoi ispezionare gli elementi del popup usando gli strumenti per sviluppatori del tuo browser (F12) per trovare i selettori CSS corretti da targettizzare.
-   **Sovrascritture del tema:** Se hai familiarità con la codifica, puoi anche sovrascrivere il CSS del modulo nel file `custom.css` o `theme.css` del tuo tema.

**D5: Come traduco il contenuto del popup in più lingue?**
R5:

-   I campi "Contenuto del popup" e "Messaggio coupon popup" sono tipicamente progettati per essere inseriti una sola volta. Per il supporto multilingue, dovresti utilizzare il sistema di traduzione di PrestaShop.
-   Vai su **Internazionale > Traduzioni**. Seleziona "Traduzioni dei moduli installati", scegli il tuo tema, quindi seleziona "Coupon popup responsive". Dovresti trovare i campi di testo per la traduzione lì.
-   Se i campi non sono direttamente traducibili tramite l'interfaccia standard di PrestaShop, potresti dover creare popup separati per ogni lingua (se il modulo supporta più istanze) o utilizzare una soluzione personalizzata che coinvolga variabili Smarty e logica condizionale all'interno del contenuto HTML, il che richiede l'assistenza di uno sviluppatore.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata del modulo "Coupon popup responsive" per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo "Coupon popup responsive" (`popcoupon`) è un modulo PrestaShop standard implementato principalmente nel suo file PHP principale, `ajax_popcoupon.php`. Sfrutta il sistema di hook di PrestaShop per la visualizzazione nel front-office e la classe `Configuration` per l'archiviazione delle impostazioni. La funzionalità principale del modulo prevede la visualizzazione di un popup, la gestione dell'interazione dell'utente (ad esempio, azione sui social media) e la generazione dinamica di codici `CartRule` (buoni) di PrestaShop. Utilizza JavaScript lato client per la logica di visualizzazione e lo stile del popup, e un template minimale per il rendering della struttura del popup.

### 4.2 Controller (`controllers/`)

Questo modulo non contiene controller Front-Office o Back-Office Admin dedicati in file separati. Tutta la logica di configurazione del back-office è gestita all'interno del metodo `getContent()` della classe principale del modulo. La visualizzazione nel front-office è gestita tramite hook e JavaScript lato client.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non definisce alcuna classe `ObjectModel` personalizzata o altre classi PHP principali in una directory `classes/`. Tutta la logica è contenuta nel file principale del modulo `ajax_popcoupon.php`. Il modulo interagisce direttamente con la classe `Configuration` di PrestaShop per le impostazioni e la classe `CartRule` per la generazione dei buoni.

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo include diversi file JavaScript:

-   **`popcoupon/jscolor/jscolor.js`**

    -   **Ambito:** Back-office.
    -   **Scopo:** Questa è una libreria JavaScript di terze parti per un selettore di colori. Viene utilizzata nel modulo nel modulo di configurazione del back-office per consentire ai commercianti di selezionare facilmente i colori per lo sfondo, il testo, il bordo e il pulsante di chiusura del popup. Si lega ai campi di input con classi specifiche per fornire un'interfaccia visiva di selezione del colore.
-   **`popcoupon/lib/voucherengine/script.js`**

    -   **Ambito:** Front-office.
    -   **Scopo:** Questo è il file JavaScript principale responsabile della funzionalità del popup nel front-office.
        -   **Listener di eventi:** Ascolta gli eventi di caricamento della pagina per attivare il popup dopo il ritardo configurato. Gestisce anche gli eventi relativi alla chiusura del popup (ad esempio, cliccando sul pulsante 'X' o al di fuori del popup).
        -   **Manipolazione del DOM:** Inietta dinamicamente la struttura HTML del popup nella pagina, gestisce la sua visibilità (mostra/nascondi) e aggiorna il suo contenuto (ad esempio, visualizzando il codice coupon dopo un'azione social).
        -   **Chiamate AJAX:** Probabilmente effettua chiamate AJAX a `ajax_popcoupon.php` del modulo (o un punto di ingresso simile) per:
            1.  Verificare se il popup deve essere visualizzato per l'utente/sessione corrente.
            2.  Generare un codice coupon unico dopo che l'utente ha completato l'azione richiesta (ad esempio, "Mi piace" di Facebook).
            3.  Memorizzare i dati dell'utente/sessione (ad esempio, un cookie) per impedire la visualizzazione ripetuta del popup in base alle impostazioni di configurazione ("una volta per sessione", "una volta per cliente").
        -   **SDK di terze parti:** Se il "Contenuto del popup" include un pulsante "Mi piace" di Facebook, questo script potrebbe interagire con l'SDK JavaScript di Facebook (se caricato dal tema) per rilevare quando l'azione "Mi piace" è completata.
-   **`popcoupon/trusted.js`**

    -   **Ambito:** Front-office.
    -   **Scopo:** Lo scopo esatto di questo file non è esplicitamente definito nelle informazioni fornite, ma in base alle pratiche comuni dei moduli, potrebbe essere:
        -   Un piccolo script di utilità per il tracciamento o l'analisi.
        -   Uno script relativo a badge di fiducia o funzionalità di sicurezza.
        -   Uno script di fallback o supplementare per il file `script.js` principale.
        -   Potrebbe contenere logica relativa alla gestione dei cookie o all'archiviazione locale per le funzionalità "visualizza una volta".

### 4.5 Fogli di stile CSS (`views/css/`)

Il modulo include i seguenti file CSS:

-   **`popcoupon/css.css`**

    -   **Ambito:** Front-office.
    -   **Scopo:** Questo è il foglio di stile principale per la finestra popup.
        -   **Componenti UI:** Stila il contenitore generale del popup, la sua sovrapposizione, il pulsante di chiusura e potenzialmente l'area del contenuto.
        -   **Selettori chiave:** Gli sviluppatori possono aspettarsi selettori come `.popcoupon-overlay`, `.popcoupon-modal`, `.popcoupon-close`, ecc. Questi possono essere sovrascritti nel `custom.css` di un tema personalizzato o utilizzando l'impostazione "Codice CSS personalizzato" del modulo.
        -   **Responsività:** Contiene media query o proprietà flexbox/grid per garantire che il popup si adatti bene a diverse dimensioni dello schermo.
-   **`popcoupon/lib/voucherengine/ps16.css`**

    -   **Ambito:** Front-office.
    -   **Scopo:** Questo foglio di stile contiene probabilmente aggiustamenti di stile specifici o sovrascritture adattate per i temi di PrestaShop 1.6. Potrebbe affrontare differenze di layout o stili di elementi predefiniti prevalenti in PS 1.6 per garantire che il popup appaia coerente tra le diverse versioni di PrestaShop. Per PS 1.7/8, alcuni di questi stili potrebbero essere sovrascritti da `css.css` o dal tema stesso.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo utilizza un singolo template Smarty:

-   **`popcoupon/views/header.tpl`**
    -   **Hook:** `displayHeader` (o simile, a seconda di come è registrato in `ajax_popcoupon.php`).
    -   **Scopo:** Questo template è probabilmente responsabile dell'iniezione della struttura HTML necessaria per il popup (che è inizialmente nascosto) e potenzialmente delle risorse JavaScript e CSS nell' `<head>` o `<body>` della pagina del front-office. Potrebbe contenere:
        -   Lo scheletro HTML di base per il modale del popup e la sua sovrapposizione.
        -   Logica condizionale per includere i file JavaScript e CSS solo quando il modulo è abilitato.
        -   Segnaposto per contenuti dinamici che verranno riempiti da JavaScript.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database:**

    -   Questo modulo non crea tabelle SQL personalizzate.
    -   Memorizza le sue impostazioni di configurazione nella tabella `ps_configuration` di PrestaShop. Le chiavi di configurazione inizieranno tipicamente con `POPCOUPON_` (ad esempio, `POPCOUPON_ENABLED`, `POPCOUPON_DELAY`, `POPCOUPON_VOUCHER_VALUE`).
    -   Sfrutta le tabelle `ps_cart_rule` e `ps_cart_rule_lang` di PrestaShop per generare e gestire i codici coupon unici.
    -   Per le funzionalità "visualizza una volta per cliente/sessione", probabilmente utilizza cookie o voci di configurazione specifiche di `ps_customer`.
-   **Tabella degli hook registrati:**

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Iniezione di CSS, JavaScript e della struttura HTML iniziale (nascosta) per il popup. |
| `displayFooter` | Alla fine della sezione `<body>` di ogni pagina del front-office. | Hook alternativo per l'iniezione di JS/CSS o dell'HTML del popup, spesso preferito per le prestazioni. |
| `displayLeftColumn` | Nella colonna sinistra del front-office. | Meno comune per i popup, ma potrebbe essere utilizzato per attivare o visualizzare un elemento popup più piccolo. |
| `displayRightColumn` | Nella colonna destra del front-office. | Simile a `displayLeftColumn`. |
| `displayProductButtons` | Nella pagina del prodotto, vicino al pulsante "aggiungi al carrello". | Potrebbe essere utilizzato per attivare un popup specifico per il prodotto o visualizzare una piccola offerta di coupon. |
| `actionFrontControllerSetMedia` | Quando un controller front-end imposta i suoi media (JS/CSS). | Un modo più robusto per registrare le risorse JS/CSS, garantendo che vengano caricate correttamente. |
| `actionValidateOrder` | Dopo che un ordine è stato validato con successo. | (Meno probabile per questo modulo, ma potrebbe essere utilizzato per azioni post-acquisto relative ai coupon). |

*Nota: Gli hook esatti utilizzati sono determinati dai metodi `hook` implementati in `ajax_popcoupon.php` (ad esempio, `hookDisplayHeader()`). La descrizione del modulo menziona "Header, Colonne, Prodotto o Footer", indicando che si registra per almeno uno di questi hook di visualizzazione.*

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Coupon popup responsive", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere commercianti e sviluppatori con qualsiasi problema o domanda riguardante la funzionalità e l'integrazione del modulo.
