---
title: "Bonifico bancario con riepilogo ordine - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Bonifico bancario con riepilogo ordine di MyPresta.eu."
sidebar:
  label: "Bonifico bancario con riepilogo ordine - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Bank wire with order summary su MyPresta.eu](https://mypresta.eu/modules/payment-process/bank-wire-with-order-summary.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/payment/bank-wire-with-order-summary/)
>
> ---


# Bonifico bancario con riepilogo ordine

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste da PrestaShop stesso e sono solitamente disponibili sulla maggior parte degli ambienti di hosting. Nessuna estensione insolita specifica è necessaria per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale dove definisci i dettagli del tuo conto bancario e come il metodo di pagamento tramite bonifico bancario si comporta nel tuo negozio.

#### **Impostazioni del conto per bonifico bancario**

Questa sezione ti consente di definire più profili di conto bancario. Ogni profilo può avere i propri dettagli ed essere attivato o disattivato indipendentemente. Questo è utile se hai diversi conti bancari per diverse valute, paesi o anche diversi marchi.

-   **Nome profilo:**

    -   **Cosa fa questa impostazione:** Questo è un nome interno per il tuo profilo di conto bancario, che ti aiuta a identificarlo nel back office. Non è visibile ai clienti.
    -   **Effetto della modifica di questa impostazione:** La modifica di questa impostazione influisce solo su come vedi il profilo nel pannello di amministrazione.
    -   **Valore consigliato:** Un nome descrittivo, ad esempio, "Conto Euro Principale", "Conto USD per Ordini USA".
    -   **Scenario / esempio del commerciante:** Se hai un conto bancario in Germania per pagamenti in EUR e un altro negli USA per pagamenti in USD, creeresti due profili, nominandoli di conseguenza.
-   **Attivo:**

    -   **Cosa fa questa impostazione:** Controlla se questo specifico profilo di conto bancario è disponibile come opzione di pagamento per i clienti.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (Sì):* Questo profilo di conto bancario verrà offerto ai clienti se soddisfa tutti gli altri criteri di idoneità (valuta, paese, ecc.).
        -   *Quando disabilitato (No):* Questo profilo non verrà mostrato come opzione di pagamento, indipendentemente dalle altre impostazioni.
    -   **Valore consigliato:** "Sì" per i conti attivi, "No" per i conti inattivi o temporanei.
    -   **Scenario / esempio del commerciante:** Potresti disabilitare un profilo se un conto bancario è temporaneamente non disponibile o se stai eliminando gradualmente una particolare valuta.
-   **Priorità:**

    -   **Cosa fa questa impostazione:** Se più profili di bonifico bancario sono attivi e idonei per l'ordine di un cliente, questo numero determina quale viene visualizzato per primo o preferito. Numeri più bassi significano priorità più alta.
    -   **Effetto della modifica di questa impostazione:** Influisce sull'ordine in cui le opzioni di bonifico bancario idonee vengono presentate al cliente.
    -   **Valore consigliato:** Usa numeri sequenziali (ad esempio, 1, 2, 3) per ordinare le tue preferenze.
    -   **Scenario / esempio del commerciante:** Se preferisci che i clienti utilizzino il tuo conto EUR principale rispetto a uno secondario, assegna al conto principale un numero di priorità inferiore (ad esempio, 1) rispetto a quello secondario (ad esempio, 2).
-   **Valuta:**

    -   **Cosa fa questa impostazione:** Specifica in quale valuta questo profilo di conto bancario è configurato per ricevere pagamenti.
    -   **Effetto della modifica di questa impostazione:** Questo profilo verrà offerto solo ai clienti il cui totale dell'ordine è nella valuta selezionata.
    -   **Valore consigliato:** Seleziona la valuta principale per questo conto bancario.
    -   **Scenario / esempio del commerciante:** Se hai un conto bancario che accetta solo EUR, seleziona "Euro". Se un cliente effettua un ordine in USD, questo profilo non verrà mostrato.
-   **Paesi idonei:**

    -   **Cosa fa questa impostazione:** Determina per quali paesi questo profilo di conto bancario è disponibile. Puoi selezionare più paesi.
    -   **Effetto della modifica di questa impostazione:** Questo profilo verrà offerto solo ai clienti il cui indirizzo di fatturazione si trova in uno dei paesi selezionati.
    -   **Valore consigliato:** Seleziona tutti i paesi da cui sei disposto ad accettare bonifici bancari su questo specifico conto.
    -   **Scenario / esempio del commerciante:** Se il tuo conto bancario tedesco è solo per clienti in Germania e Austria, seleziona "Germania" e "Austria".
-   **Zone idonee:**

    -   **Cosa fa questa impostazione:** Determina per quali zone geografiche questo profilo di conto bancario è disponibile. Puoi selezionare più zone.
    -   **Effetto della modifica di questa impostazione:** Similmente ai paesi, questo profilo verrà offerto solo ai clienti il cui indirizzo di fatturazione si trova in una delle zone selezionate.
    -   **Valore consigliato:** Seleziona le zone pertinenti a questo conto bancario.
    -   **Scenario / esempio del commerciante:** Se hai un conto bancario specificamente per i clienti europei, potresti selezionare la zona "Europa".
-   **Gruppi di clienti idonei:**

    -   **Cosa fa questa impostazione:** Limita questa opzione di pagamento a specifici gruppi di clienti (ad esempio, "Visitatori", "Ospiti", "Clienti", "Grossisti").
    -   **Effetto della modifica di questa impostazione:** Solo i clienti appartenenti ai gruppi selezionati vedranno questa opzione di bonifico bancario.
    -   **Valore consigliato:** Tipicamente "Clienti" e "Ospiti", ma può essere personalizzato per il B2B.
    -   **Scenario / esempio del commerciante:** Potresti voler offrire il bonifico bancario solo al tuo gruppo "Grossisti" per ordini B2B di grandi dimensioni, e non ai normali clienti al dettaglio.
-   **Intestatario del conto:**

    -   **Cosa fa questa impostazione:** Il nome completo dell'intestatario del conto (il nome della tua azienda o il tuo nome personale) così come appare sul conto bancario.
    -   **Effetto della modifica di questa impostazione:** Questa informazione viene visualizzata al cliente sulla pagina di conferma del pagamento, in modo che sappia a chi trasferire il denaro.
    -   **Valore consigliato:** Il tuo nome legale esatto dell'azienda o il tuo nome personale.
    -   **Scenario / esempio del commerciante:** "MyPresta.eu Sp. z o.o."
-   **IBAN:**

    -   **Cosa fa questa impostazione:** Il tuo International Bank Account Number. Questo è un identificatore standardizzato internazionale del conto bancario.
    -   **Effetto della modifica di questa impostazione:** Questa è un'informazione cruciale visualizzata al cliente per effettuare il bonifico bancario.
    -   **Valore consigliato:** Il tuo IBAN completo e corretto.
    -   **Scenario / esempio del commerciante:** "DE89370400440532013000"
-   **BIC / SWIFT:**

    -   **Cosa fa questa impostazione:** Il tuo Bank Identifier Code (BIC) o codice SWIFT. Questo identifica la tua banca a livello globale.
    -   **Effetto della modifica di questa impostazione:** Questa è un'informazione essenziale visualizzata al cliente per effettuare bonifici bancari internazionali.
    -   **Valore consigliato:** Il tuo codice BIC/SWIFT completo e corretto.
    -   **Scenario / esempio del commerciante:** "COBADEFFXXX"
-   **Numero di conto / dettagli:**

    -   **Cosa fa questa impostazione:** Il tuo numero di conto bancario tradizionale o altri dettagli specifici richiesti dalla tua banca o dal tuo paese, se IBAN/BIC non sono sufficienti o applicabili.
    -   **Effetto della modifica di questa impostazione:** Questa informazione viene visualizzata al cliente.
    -   **Valore consigliato:** Il tuo numero di conto se l'IBAN non viene utilizzato, o qualsiasi altro dettaglio specifico. Lascia vuoto se IBAN/BIC sono sufficienti.
    -   **Scenario / esempio del commerciante:** In alcuni paesi, un numero di conto locale potrebbe essere ancora preferito insieme o al posto dell'IBAN.
-   **Indirizzo della banca / dell'intestatario:**

    -   **Cosa fa questa impostazione:** L'indirizzo della tua banca o l'indirizzo registrato dell'intestatario del conto.
    -   **Effetto della modifica di questa impostazione:** Questa informazione viene visualizzata al cliente, a volte richiesta per i bonifici bancari.
    -   **Valore consigliato:** L'indirizzo completo della tua filiale bancaria o l'indirizzo registrato della tua azienda.
    -   **Scenario / esempio del commerciante:** "Banca Esempio, Via Principale 123, 10001 Città, Paese"
-   **Istruzioni aggiuntive:**

    -   **Cosa fa questa impostazione:** Un campo di testo dove puoi fornire note extra per il cliente riguardo al bonifico bancario (ad esempio, "Si prega di includere il numero di riferimento dell'ordine nella descrizione del bonifico", "I pagamenti di solito richiedono 1-3 giorni lavorativi per essere accreditati").
    -   **Effetto della modifica di questa impostazione:** Questo testo verrà visualizzato al cliente sulla pagina di conferma del pagamento.
    -   **Valore consigliato:** Istruzioni chiare e concise per aiutare i clienti a completare il bonifico correttamente.
    -   **Scenario / esempio del commerciante:** "Importante: Si prega di utilizzare il proprio ID Ordine # [ORDER\_ID] come riferimento di pagamento per garantire una rapida elaborazione."

#### **Restrizioni sul totale del carrello**

Queste impostazioni ti consentono di controllare i valori minimi e massimi dell'ordine per i quali è disponibile l'opzione di pagamento tramite bonifico bancario.

-   **Totale carrello minimo:**

    -   **Cosa fa questa impostazione:** Abilita o disabilita la restrizione del totale carrello minimo per questo metodo di pagamento.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il campo "Valore totale carrello minimo" diventa attivo, e il bonifico bancario sarà disponibile solo per ordini superiori a quel valore.
        -   *Quando disabilitato:* Non viene applicata alcuna restrizione sul totale carrello minimo.
    -   **Valore consigliato:** "Abilitato" se si desidera impostare un minimo, "Disabilitato" altrimenti.
    -   **Scenario / esempio del commerciante:** Potresti abilitarlo se i bonifici bancari sono più convenienti per ordini di grandi dimensioni, o per scoraggiare i bonifici bancari per acquisti molto piccoli.
-   **Valore totale carrello minimo:**

    -   **Cosa fa questa impostazione:** Il valore monetario effettivo che il carrello del cliente deve superare affinché l'opzione di bonifico bancario appaia.
    -   **Effetto della modifica di questa impostazione:** Se il totale del carrello del cliente è inferiore a questo valore, l'opzione di bonifico bancario non verrà mostrata.
    -   **Valore consigliato:** Un minimo ragionevole, ad esempio, "50.00".
    -   **Scenario / esempio del commerciante:** Imposta su "50.00" se vuoi offrire il bonifico bancario solo per ordini di €50 o più.
-   **Totale carrello massimo:**

    -   **Cosa fa questa impostazione:** Abilita o disabilita la restrizione del totale carrello massimo per questo metodo di pagamento.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il campo "Valore totale carrello massimo" diventa attivo, e il bonifico bancario sarà disponibile solo per ordini inferiori a quel valore.
        -   *Quando disabilitato:* Non viene applicata alcuna restrizione sul totale carrello massimo.
    -   **Valore consigliato:** "Abilitato" se si desidera impostare un massimo, "Disabilitato" altrimenti.
    -   **Scenario / esempio del commerciante:** Potresti abilitarlo se preferisci altri metodi di pagamento (come la negoziazione diretta o la fatturazione personalizzata) per ordini estremamente grandi.
-   **Valore totale carrello massimo:**

    -   **Cosa fa questa impostazione:** Il valore monetario effettivo che il carrello del cliente deve essere inferiore affinché l'opzione di bonifico bancario appaia.
    -   **Effetto della modifica di questa impostazione:** Se il totale del carrello del cliente è superiore a questo valore, l'opzione di bonifico bancario non verrà mostrata.
    -   **Valore consigliato:** Un massimo ragionevole, ad esempio, "5000.00".
    -   **Scenario / esempio del commerciante:** Imposta su "5000.00" se non vuoi accettare bonifici bancari per ordini superiori a €5000.

#### **Visualizzazione del riepilogo dell'ordine**

Queste impostazioni controllano quali informazioni vengono mostrate al cliente nella pagina di conferma del pagamento prima che finalizzi l'ordine. Questo è cruciale per la conformità legale.

-   **Riepilogo ordine prima della conferma:**

    -   **Cosa fa questa impostazione:** Controlla se un riepilogo dettagliato dell'ordine viene visualizzato al cliente nella pagina di conferma del pagamento.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Verrà mostrato un riepilogo di prodotti, prezzi e totali.
        -   *Quando disabilitato:* Il riepilogo dettagliato non verrà mostrato, potenzialmente influenzando la conformità legale in alcune regioni.
    -   **Valore consigliato:** "Abilitato" per garantire la conformità legale e la chiarezza per il cliente.
    -   **Scenario / esempio del commerciante:** Mantieni sempre abilitato per fornire piena trasparenza ai tuoi clienti prima che si impegnino nell'acquisto.
-   **Visualizza riepilogo cliente prima della conferma:**

    -   **Cosa fa questa impostazione:** Controlla se il riepilogo dell'indirizzo di fatturazione e spedizione del cliente viene visualizzato nella pagina di conferma del pagamento.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Verranno mostrati i dettagli dell'indirizzo del cliente.
        -   *Quando disabilitato:* I dettagli dell'indirizzo non verranno mostrati.
    -   **Valore consigliato:** "Abilitato" per la massima trasparenza.
    -   **Scenario / esempio del commerciante:** Abilitando questa opzione i clienti possono ricontrollare le informazioni di consegna un'ultima volta prima di effettuare l'ordine.

#### **Analisi avanzate (Interne)**

Queste impostazioni sono tipicamente per l'analisi e la reportistica interna del modulo, non influenzando direttamente l'esperienza del cliente nel front-office.

-   **BANKWIREPRO\_ANALYTICS\_DEFAULT\_CHART, BANKWIREPRO\_ANALYTICS\_PERIOD, BANKWIREPRO\_ANALYTICS\_CHART\_WEEKS, BANKWIREPRO\_ANALYTICS\_CHART\_MONTHS, BANKWIREPRO\_ANALYTICS\_CHART\_YEARS:**
    -   **Cosa fanno queste impostazioni:** Questi sono valori di configurazione interni relativi a come il modulo potrebbe tracciare o visualizzare le statistiche di pagamento all'interno del back office di PrestaShop (se tale funzionalità è implementata). Definiscono i tipi di grafico predefiniti, i periodi di reporting e gli intervalli di tempo per l'analisi.
    -   **Effetto della modifica di queste impostazioni:** Queste non influiscono sul processo di pagamento rivolto al cliente. Potrebbero influenzare il modo in cui i dati vengono presentati in una dashboard di analisi interna, se disponibile.
    -   **Valore consigliato:** Lasciare come predefinito a meno che non sia specificamente indicato dal supporto.
    -   **Scenario / esempio del commerciante:** Non direttamente applicabile al processo decisionale del commerciante per l'elaborazione dei pagamenti.

#### **Impostazioni della lingua (Interne)**

-   **PS\_LANG\_DEFAULT, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG:**

    -   **Cosa fanno queste impostazioni:** Queste sono variabili di configurazione standard di PrestaShop che determinano la lingua predefinita del tuo negozio e se i dipendenti possono cambiare la lingua dei moduli del back office. Sono visualizzate qui per riferimento ma non sono specifiche di questo modulo.
    -   **Effetto della modifica di queste impostazioni:** Le modifiche a queste verrebbero apportate nelle impostazioni generali di PrestaShop, non qui. Influenzano la lingua predefinita per i campi di testo nel back office.
    -   **Valore consigliato:** La lingua predefinita del tuo negozio.
    -   **Scenario / esempio del commerciante:** Se la lingua principale del tuo negozio è l'inglese, `PS_LANG_DEFAULT` sarebbe impostato sull'ID della lingua inglese.
-   **PS\_CURRENCY\_DEFAULT:**

    -   **Cosa fa questa impostazione:** Questa è la valuta predefinita del tuo negozio PrestaShop. Viene visualizzata qui per riferimento.
    -   **Effetto della modifica di questa impostazione:** Questa è un'impostazione globale di PrestaShop. Modificarla influenzerebbe tutti i prezzi e le visualizzazioni di valuta in tutto il tuo negozio.
    -   **Valore consigliato:** La valuta operativa principale del tuo negozio.
    -   **Scenario / esempio del commerciante:** Se il tuo negozio commercia principalmente in Euro, questo sarebbe impostato su "Euro".

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Nome profilo | Nome descrittivo | Identificazione interna del conto bancario. |
| Configurazione modulo | Attivo | Sì | Abilita/disabilita questo profilo di conto bancario per l'uso da parte del cliente. |
| Configurazione modulo | Priorità | 1 (o sequenziale) | Ordina la visualizzazione di più opzioni di bonifico bancario idonee. |
| Configurazione modulo | Valuta | Valuta del tuo negozio | Limita il profilo agli ordini in questa valuta. |
| Configurazione modulo | Paesi idonei | Tutti i paesi | Limita il profilo ai clienti dei paesi selezionati. |
| Configurazione modulo | Zone idonee | Tutte le zone | Limita il profilo ai clienti delle zone selezionate. |
| Configurazione modulo | Gruppi di clienti idonei | Tutti i gruppi | Limita il profilo ai gruppi di clienti selezionati. |
| Configurazione modulo | Intestatario del conto | La tua azienda/nome | Visualizzato al cliente per il bonifico bancario. |
| Configurazione modulo | IBAN | Il tuo IBAN | Visualizzato al cliente per il bonifico bancario. |
| Configurazione modulo | BIC / SWIFT | Il tuo BIC/SWIFT | Visualizzato al cliente per il bonifico bancario internazionale. |
| Configurazione modulo | Numero di conto / dettagli | (Opzionale) | Dettagli bancari aggiuntivi per il cliente. |
| Configurazione modulo | Indirizzo della banca / dell'intestatario | Indirizzo della tua banca/azienda | Visualizzato al cliente per il bonifico bancario. |
| Configurazione modulo | Istruzioni aggiuntive | Istruzioni chiare | Note extra per il cliente (ad es. numero di riferimento). |
| Configurazione modulo | Totale carrello minimo | Disabilitato | Abilita/disabilita la restrizione del valore minimo dell'ordine. |
| Configurazione modulo | Valore totale carrello minimo | 0.00 | Valore minimo dell'ordine affinché il bonifico bancario sia disponibile. |
| Configurazione modulo | Totale carrello massimo | Disabilitato | Abilita/disabilita la restrizione del valore massimo dell'ordine. |
| Configurazione modulo | Valore totale carrello massimo | 0.00 | Valore massimo dell'ordine affinché il bonifico bancario sia disponibile. |
| Configurazione modulo | Riepilogo ordine prima della conferma | Abilitato | Visualizza il riepilogo dettagliato del prodotto nella pagina di conferma. |
| Configurazione modulo | Visualizza riepilogo cliente prima della conferma | Abilitato | Visualizza il riepilogo dell'indirizzo del cliente nella pagina di conferma. |
| Configurazione modulo | BANKWIREPRO\_ANALYTICS\_\* | Predefinito | Impostazioni di analisi interne (nessun impatto sul front-office). |
| Configurazione modulo | PS\_LANG\_DEFAULT | Predefinito del negozio | Impostazione della lingua predefinita di PrestaShop. |
| Configurazione modulo | PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG | Predefinito del negozio | Impostazione della lingua del modulo dipendente di PrestaShop. |
| Configurazione modulo | PS\_CURRENCY\_DEFAULT | Predefinito del negozio | Impostazione della valuta predefinita di PrestaShop. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Perché l'opzione Bonifico Bancario non viene visualizzata per i miei clienti?**
R1: Controlla le seguenti impostazioni nella configurazione del modulo:
\* Interruttore **"Attivo"** per il profilo del conto bancario: Assicurati che sia impostato su "Sì".
\* **"Valuta"**: La valuta dell'ordine del cliente corrisponde alla valuta del profilo?
\* **"Paesi idonei" / "Zone idonee"**: Il paese/zona dell'indirizzo di fatturazione del cliente è incluso?
\* **"Gruppi di clienti idonei"**: Il gruppo del cliente è autorizzato a utilizzare questo metodo di pagamento?
\* **"Totale carrello minimo" / "Totale carrello massimo"**: Il valore del carrello del cliente rientra nell'intervallo consentito?
\* **Cache di PrestaShop**: A volte, la pulizia della cache di Smarty (Parametri Avanzati > Prestazioni > Svuota cache) può risolvere i problemi di visualizzazione.

**D2: I miei dettagli bancari sono errati o obsoleti. Come posso modificarli?**
R2: Vai su **Moduli > Gestione moduli**, trova "Bonifico bancario con riepilogo ordine" e clicca su "Configura". Vedrai i tuoi profili di conto bancario esistenti. Clicca sul pulsante "Modifica" (icona a matita) accanto al profilo che desideri aggiornare, modifica i campi "Intestatario del conto", "IBAN", "BIC / SWIFT", ecc., e poi salva le modifiche.

**D3: Il riepilogo dell'ordine non viene visualizzato nella pagina di conferma. C'è qualcosa che non va?**
R3: Assicurati che le impostazioni "Riepilogo ordine prima della conferma" e "Visualizza riepilogo cliente prima della conferma" siano entrambe impostate su "Abilitato" nella configurazione del modulo. Se lo sono e hai svuotato la cache di PrestaShop, potrebbe esserci un conflitto con il tema. Prova con il tema predefinito di PrestaShop per escludere questa possibilità.

**D4: Posso offrire diversi conti bancari per diversi tipi di clienti o prodotti?**
R4: Sì, assolutamente! Questo modulo supporta più profili di conto bancario. Puoi creare profili separati e utilizzare le impostazioni "Gruppi di clienti idonei", "Valuta", "Paesi idonei" e "Totale carrello" per definire quando viene offerto ogni specifico conto bancario. Ad esempio, un conto per clienti al dettaglio in EUR, un altro per clienti all'ingrosso in USD.

**D5: Dopo aver aggiornato il mio tema o PrestaShop, la pagina del bonifico bancario appare strana. Cosa devo fare?**
R5: Questo spesso indica un conflitto CSS o un problema di override del template.
1.  **Svuota la cache:** Inizia sempre svuotando la cache di PrestaShop (Parametri Avanzati > Prestazioni).
2.  **Controlla gli aggiornamenti del modulo:** Assicurati di avere l'ultima versione del modulo "Bonifico bancario con riepilogo ordine" da MyPresta.eu, poiché gli aggiornamenti spesso includono correzioni di compatibilità.
3.  **Conflitto del tema:** Se il problema persiste, passa temporaneamente al tema predefinito di PrestaShop (ad esempio, "Classic") per vedere se il problema scompare. Se lo fa, il tuo tema personalizzato sta probabilmente sovrascrivendo o entrando in conflitto con lo stile o i template del modulo. Potrebbe essere necessario consultare lo sviluppatore del tuo tema o un webmaster per regolare il CSS o i file di template del tema.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo `bankwirepro` segue l'architettura standard dei moduli PrestaShop, sfruttando `ModuleFrontController` per le interazioni front-office e la classe principale `Module` per la configurazione. Si integra nel flusso di checkout tramite hook di pagamento (`displayPaymentOptions`, `paymentOptions`, `displayPaymentReturn`). La configurazione è gestita tramite voci della tabella `Configuration`, e i dettagli del conto bancario sono archiviati come array serializzati o singole chiavi `Configuration`, consentendo più profili. La funzione principale del modulo è presentare i dettagli bancari e un riepilogo dell'ordine al cliente prima e dopo la convalida dell'ordine.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:
    -   `controllers/front/index.php`
        -   **Nome classe**: `BankwireproIndexModuleFrontController` (estende `ModuleFrontController`)
        -   **Responsabilità**: Questo controller probabilmente funge da punto di ingresso predefinito o da fallback. In molti moduli, i controller `index.php` reindirizzano a un controller più specifico o gestiscono la visualizzazione di base del modulo se non viene richiesta alcuna altra azione specifica. Potrebbe gestire la configurazione iniziale o il reindirizzamento alla selezione del pagamento.
    -   `controllers/front/payment.php`
        -   **Nome classe**: `BankwireproPaymentModuleFrontController` (estende `ModuleFrontController`)
        -   **Responsabilità**: Questo controller è responsabile del rendering della pagina di selezione del pagamento quando viene scelta l'opzione di bonifico bancario. Raccoglie i dettagli del conto bancario necessari in base al carrello corrente, al cliente e alla valuta, e li prepara per la visualizzazione nel template `payment.tpl`. Agisce come ponte tra la selezione dell'opzione di pagamento e il passaggio di convalida finale.
    -   `controllers/front/validation.php`
        -   **Nome classe**: `BankwireproValidationModuleFrontController` (estende `ModuleFrontController`)
        -   **Responsabilità**: Questo è il controller critico che gestisce il passaggio finale del processo di pagamento tramite bonifico bancario. Convalida l'ordine, crea l'ordine nel database di PrestaShop e quindi renderizza il template `validation.tpl`. Questo template visualizza il riepilogo completo dell'ordine, il riepilogo dell'indirizzo del cliente e i dettagli del conto bancario scelto, insieme a istruzioni aggiuntive, prima che il cliente venga reindirizzato alla pagina standard `order-confirmation`. Garantisce che tutte le informazioni necessarie siano presentate per la conformità legale.

### 4.3 Classi e modelli principali (`classes/`)

Il dossier del modulo non indica classi personalizzate in `classes/`. La logica principale per la gestione dei profili di conto bancario e della configurazione è probabilmente contenuta nel file principale `bankwirepro.php`, utilizzando `Configuration::get()` e `Configuration::updateValue()` per archiviare le impostazioni, potenzialmente con array serializzati per più profili di conto bancario.

### 4.4 Risorse JavaScript (`views/js/`)

Il dossier del modulo non indica file JavaScript personalizzati. Ciò suggerisce che la funzionalità front-office del modulo è principalmente renderizzata lato server e si basa su JavaScript standard di PrestaShop per le interazioni di base, o che qualsiasi JS minimo è inline nei template.

### 4.5 Fogli di stile CSS (`views/css/`)

Il dossier del modulo non indica file CSS personalizzati. Ciò implica che il modulo si basa interamente sullo stile del tema predefinito di PrestaShop, o che qualsiasi stile minimo è inline all'interno dei template. Gli sviluppatori dovrebbero essere consapevoli che l'aspetto del modulo sarà in gran parte dettato dal CSS del tema attivo.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template di amministrazione (`views/templates/admin/`)**:

    -   `accountSelector.tpl`: Questo template è probabilmente utilizzato nella configurazione del back-office del modulo per visualizzare un elenco di profili di conto bancario configurati, consentendo all'amministratore di selezionarli, modificarli o eliminarli. Tipicamente renderizzerebbe una tabella o un elenco con nomi di profilo, stato e pulsanti di azione.
-   **Template front-office (`views/templates/front/`)**:

    -   `validation.tpl`: Questo è un template cruciale renderizzato da `BankwireproValidationModuleFrontController`. Visualizza il riepilogo completo dell'ordine (prodotti, totali), il riepilogo dell'indirizzo del cliente e i dettagli del conto bancario selezionato (intestatario del conto, IBAN, BIC/SWIFT, istruzioni) al cliente prima che l'ordine sia completamente confermato. Questo template è fondamentale per la conformità legale.
-   **Template hook (`views/templates/hook/`)**:

    -   `infos.tpl`: Questo template è probabilmente agganciato a `displayPaymentReturn` o un hook simile nella pagina `order-confirmation`. Ribadisce le istruzioni di pagamento tramite bonifico bancario e i dettagli bancari dopo che l'ordine è stato effettuato con successo, fungendo da promemoria per il cliente per completare il bonifico.
    -   `payment.tpl`: Questo template è probabilmente utilizzato per l'hook `displayPayment` (PrestaShop 1.6.x) o `paymentOptions` (PrestaShop 1.7+). Renderizza l'opzione di bonifico bancario stessa nella pagina di selezione del pagamento durante il checkout, presentandola come un metodo di pagamento disponibile al cliente.
    -   `payment_return.tpl`: Simile a `infos.tpl`, questo template è anche probabilmente agganciato a `displayPaymentReturn`. Fornisce il messaggio di conferma finale e i dettagli bancari nella pagina di conferma dell'ordine, assicurando che il cliente abbia tutte le informazioni per procedere con il bonifico bancario.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non crea tabelle SQL personalizzate. Tutte le impostazioni di configurazione, inclusi più profili di conto bancario, sono archiviate nella tabella `ps_configuration`.
    -   Chiavi di configurazione utilizzate:
        -   `BANK_WIRE_PRO_MINCART`, `BANK_WIRE_PRO_MINCART_V`, `BANK_WIRE_PRO_MAXCART`, `BANK_WIRE_PRO_MAXCART_V`: Per le restrizioni sul totale del carrello.
        -   `BANK_WIRE_PRO_OWNER_`, `BANK_WIRE_PRO_DETAILS_`, `BANK_WIRE_PRO_ADDRESS_`, `BANK_WIRE_PRO_SWIFT_`, `BANK_WIRE_PRO_IBAN_`, `BANK_WIRE_PRO_MORE_`: Questi sono probabilmente prefissi per archiviare i dettagli di *ogni* profilo di conto bancario, possibilmente con un ID lingua o un suffisso ID profilo (ad esempio, `BANK_WIRE_PRO_OWNER_1_1` per il profilo 1, lingua 1).
        -   `BANK_WIRE_PRO_OWNER_SUMMARY`, `BANK_WIRE_PRO_CSUMMARY`, `BANK_WIRE_PRO_ASUMMARY`: Per controllare la visualizzazione dei riepiloghi di ordine e indirizzo.
        -   `BANKWIREPRO_ANALYTICS_*`: Impostazioni di analisi interne.
        -   Le chiavi standard di PrestaShop come `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`, `PS_CURRENCY_DEFAULT` vengono lette ma non gestite dal modulo.
-   **Tabella degli hook registrati**:

| Nome Hook | Ambito | Tempistica di Esecuzione | Scopo Tecnico |
| --- | --- | --- | --- |
| `displayPayment` | Front-Office | Fase di selezione del pagamento (PrestaShop 1.6.x) | Renderizza l'opzione di pagamento tramite bonifico bancario nella pagina di checkout. |
| `paymentOptions` | Front-Office | Fase di selezione del pagamento (PrestaShop 1.7.x, 8.x, 9.x) | Fornisce oggetti `PaymentOption` per il bonifico bancario alla pagina di checkout. |
| `displayPaymentReturn` | Front-Office | Pagina di conferma dell'ordine (`order-confirmation`) | Visualizza i dettagli bancari e le istruzioni dopo la convalida dell'ordine. |
| `displayPaymentOptions` | Front-Office | Fase di selezione del pagamento (PrestaShop 1.7.x, 8.x, 9.x) | Hook alternativo o supplementare per il rendering delle opzioni di pagamento. |
| `actionPaymentConfirmation` | Back-Office | Dopo che un ordine è confermato come pagato | (Implicito, comune per i moduli di pagamento) Può aggiornare lo stato dell'ordine o eseguire azioni post-pagamento. |
| `actionValidateOrder` | Back-Office | Dopo che un ordine è convalidato | (Implicito, comune per i moduli di pagamento) Utilizzato per impostare lo stato iniziale dell'ordine, salvare i dettagli di pagamento. |

## 5. Supporto Ufficiale e Aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e per assicurarti di utilizzare la versione più sicura e compatibile del modulo "Bonifico bancario con riepilogo ordine", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda riguardante la funzionalità e l'integrazione del modulo.
