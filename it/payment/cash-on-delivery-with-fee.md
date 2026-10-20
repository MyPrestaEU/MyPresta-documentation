---
title: "Contrassegno con commissione - Manuale del commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Contrassegno con commissione di MyPresta.eu."
sidebar:
  label: "Contrassegno con commissione - Manuale del commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Cash on delivery with fee su MyPresta.eu](https://mypresta.eu/modules/payment-process/cash-on-delivery-with-fee.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/payment/cash-on-delivery-with-fee/)
>
> ---


# Contrassegno con commissione

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e sono solitamente disponibili su qualsiasi ambiente di hosting moderno.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo "Contrassegno con commissione", accessibile direttamente dopo l'installazione o navigando su **Moduli > Gestione moduli**, cercando "Contrassegno con commissione" e facendo clic su "Configura".

#### **Impostazioni generali**

-   **Disabilita / Abilitato / Disabilitato (Stato principale del modulo)**

    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per abilitare o disabilitare l'intera opzione di pagamento in contrassegno con commissione nel tuo negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando Abilitato:* L'opzione di pagamento in contrassegno, insieme alle sue commissioni configurate, sarà disponibile per i clienti durante il checkout.
        -   *Quando Disabilitato:* L'opzione di pagamento in contrassegno non sarà mostrata ai clienti, indipendentemente dalle altre impostazioni.
    -   **Valore consigliato:** `Abilitato` se intendi offrire il contrassegno.
    -   **Scenario / esempio del commerciante:** Se stai testando il modulo o desideri temporaneamente smettere di offrire il contrassegno, imposteresti questo su `Disabilitato`.
-   **Valore (Valore commissione contrassegno)**

    -   **Cosa fa questa impostazione:** Questo campo determina l'importo base o la percentuale della commissione per il contrassegno. L'interpretazione esatta (importo fisso o percentuale) dipende dall'impostazione "Come includere la commissione?" di seguito.
    -   **Effetto della modifica di questa impostazione:** Modifica direttamente il costo aggiunto agli ordini in contrassegno.
    -   **Valore consigliato:** Inizia con `0.00` e regola in base alle commissioni del tuo corriere.
    -   **Scenario / esempio del commerciante:** Se il tuo corriere addebita €2.50 per il contrassegno, potresti inserire `2.50`. Se addebita l'1% dell'ordine, potresti inserire `1`.
-   **Come includere la commissione?**

    -   **Cosa fa questa impostazione:** Definisce come il "Valore" (dall'impostazione precedente) viene applicato al totale dell'ordine.
    -   **Effetto della modifica di questa impostazione:**
        -   *Includi nei costi di spedizione:* La commissione per il contrassegno viene aggiunta al costo di spedizione visualizzato al cliente. Questo può semplificare la visualizzazione del checkout combinando gli addebiti.
        -   *Includi come prodotto/servizio separato:* La commissione per il contrassegno appare come una voce distinta nel riepilogo del carrello e nella fattura, spesso etichettata come "Commissione contrassegno" o simile. Questo fornisce la massima trasparenza.
    -   **Valore consigliato:** `Includi come prodotto/servizio separato` per chiarezza e conformità legale.
    -   **Scenario / esempio del commerciante:** Se desideri che i clienti vedano chiaramente l'addebito del contrassegno come un elemento separato, scegli "Includi come prodotto/servizio separato". Se preferisci un costo di spedizione più pulito e combinato, scegli "Includi nei costi di spedizione".
-   **Stato dell'ordine dopo l'acquisto con modulo contrassegno**

    -   **Cosa fa questa impostazione:** Specifica lo stato iniziale di un ordine effettuato utilizzando il metodo di pagamento in contrassegno.
    -   **Effetto della modifica di questa impostazione:** Determina come gli ordini in contrassegno appaiono nel tuo Back Office immediatamente dopo essere stati effettuati.
    -   **Valore consigliato:** `Pagamento accettato` (o uno stato simile "in attesa di pagamento" che hai configurato). Questo ti consente di differenziare gli ordini in contrassegno che sono confermati ma non ancora fisicamente pagati.
    -   **Scenario / esempio del commerciante:** Potresti impostare questo su "In attesa di pagamento in contrassegno" (se hai creato tale stato) per filtrare e gestire facilmente gli ordini in contrassegno in attesa di pagamento fisico alla consegna.
-   **Mostra riepilogo aggiuntivo prima della conferma**

    -   **Cosa fa questa impostazione:** Controlla se un blocco di riepilogo extra viene visualizzato nel passaggio finale del checkout, appena prima che il cliente confermi il proprio ordine.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Verrà mostrata una ripartizione dettagliata che include il totale del carrello, la spedizione e la commissione per il contrassegno.
        -   *Quando disabilitato:* Verrà utilizzato il riepilogo standard di PrestaShop, che potrebbe non suddividere esplicitamente la commissione per il contrassegno come voce separata.
    -   **Valore consigliato:** `Abilitato` per la massima trasparenza e conformità legale.
    -   **Scenario / esempio del commerciante:** Per assicurarti che i clienti siano pienamente consapevoli di tutti gli addebiti prima di impegnarsi, in particolare la commissione per il contrassegno, abilita questa opzione.
-   **Riepilogo carrello / Riepilogo indirizzo / Valore minimo totale carrello (Selettori CSS)**

    -   **Cosa fa questa impostazione:** Questi campi ti consentono di specificare selettori CSS per vari elementi nella tua pagina di checkout. Il modulo utilizza questi selettori per iniettare correttamente le informazioni sulla commissione per il contrassegno nel riepilogo del checkout del tuo tema.
    -   **Effetto della modifica di questa impostazione:** Se il tuo tema utilizza classi CSS non standard per questi elementi, la regolazione di questi selettori assicura che la commissione per il contrassegno venga visualizzata correttamente. Valori errati possono portare alla mancata visualizzazione della commissione o alla sua visualizzazione nel posto sbagliato.
    -   **Valore consigliato:** Lascia vuoto per il rilevamento automatico o usa i valori predefiniti forniti dal modulo. Modifica solo se la visualizzazione della commissione per il contrassegno è interrotta nel tuo tema personalizzato.
    -   **Scenario / esempio del commerciante:** Se hai installato un tema personalizzato e la commissione per il contrassegno non viene visualizzata nel riepilogo del carrello, il tuo sviluppatore web potrebbe dover ispezionare l'HTML del tuo tema e aggiornare questi selettori per corrispondere alla struttura del tuo tema.

#### **Calcolo e condizioni della commissione**

-   **Disabilita / Abilitato / Disabilitato (Condizione valore massimo carrello)**

    -   **Cosa fa questa impostazione:** Abilita o disabilita una condizione in cui il metodo di pagamento in contrassegno è disponibile solo se il totale del carrello è *inferiore* a un certo valore massimo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando Abilitato:* I clienti con carrelli che superano il valore massimo specificato non vedranno il contrassegno come opzione di pagamento.
        -   *Quando Disabilitato:* Nessuna restrizione sul valore massimo del carrello si applica al contrassegno.
    -   **Valore consigliato:** `Disabilitato` a meno che tu non abbia ragioni specifiche per limitare gli ordini in contrassegno di alto valore.
    -   **Scenario / esempio del commerciante:** Se hai avuto problemi con ordini in contrassegno di alto valore fraudolenti o non ritirati, potresti abilitare questo e impostare un `CODPRO_MOD_MAXCART_V` a €500 per mitigare il rischio.
-   **CODPRO\_MOD\_MAXCART\_V (Valore massimo carrello)**

    -   **Cosa fa questa impostazione:** Il valore monetario specifico per la condizione del totale massimo del carrello.
    -   **Effetto della modifica di questa impostazione:** Definisce il limite superiore per l'idoneità al contrassegno.
    -   **Valore consigliato:** Imposta un valore che si allinei alla tua tolleranza al rischio per gli ordini in contrassegno.
    -   **Scenario / esempio del commerciante:** Se `Disabilita / Abilitato / Disabilitato (Condizione valore massimo carrello)` è abilitato e imposti questo a `500.00`, i clienti con ordini superiori a €500 non possono utilizzare il contrassegno.
-   **Disabilita / Abilitato / Disabilitato (Condizione valore minimo carrello)**

    -   **Cosa fa questa impostazione:** Abilita o disabilita una condizione in cui il metodo di pagamento in contrassegno è disponibile solo se il totale del carrello è *superiore* a un certo valore minimo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando Abilitato:* I clienti con carrelli inferiori al valore minimo specificato non vedranno il contrassegno come opzione di pagamento.
        -   *Quando Disabilitato:* Nessuna restrizione sul valore minimo del carrello si applica al contrassegno.
    -   **Valore consigliato:** `Disabilitato` a meno che tu non abbia ragioni specifiche per evitare ordini in contrassegno molto piccoli.
    -   **Scenario / esempio del commerciante:** Se la commissione fissa per il contrassegno rende gli ordini molto piccoli non redditizi, potresti abilitare questo e impostare un `CODPRO_MOD_MINCART_V` a €10.
-   **CODPRO\_MOD\_MINCART\_V (Valore minimo carrello)**

    -   **Cosa fa questa impostazione:** Il valore monetario specifico per la condizione del totale minimo del carrello.
    -   **Effetto della modifica di questa impostazione:** Definisce il limite inferiore per l'idoneità al contrassegno.
    -   **Valore consigliato:** Imposta un valore che renda il contrassegno redditizio per te.
    -   **Scenario / esempio del commerciante:** Se `Disabilita / Abilitato / Disabilitato (Condizione valore minimo carrello)` è abilitato e imposti questo a `10.00`, i clienti con ordini inferiori a €10 non possono utilizzare il contrassegno.
-   **CODPRO\_CHARGEP\_V (Valore commissione percentuale)**

    -   **Cosa fa questa impostazione:** Questo campo definisce il valore percentuale della commissione per il contrassegno.
    -   **Effetto della modifica di questa impostazione:** Se "Come includere la commissione?" è impostato su un'opzione basata su percentuale, questo valore verrà utilizzato per calcolare la commissione.
    -   **Valore consigliato:** `0.00` inizialmente, regola in base all'addebito percentuale del tuo corriere.
    -   **Scenario / esempio del commerciante:** Se il tuo corriere addebita l'1.5% del valore dell'ordine per il contrassegno, dovresti inserire `1.5` qui.
-   **CODPRO\_PERCENTAGE\_TYPE (Base di calcolo percentuale)**

    -   **Cosa fa questa impostazione:** Determina su cosa viene calcolata la commissione percentuale.
    -   **Effetto della modifica di questa impostazione:**
        -   *Totale carrello (con spedizione):* La percentuale viene calcolata sull'importo totale inclusi prodotti e spedizione.
        -   *Totale carrello (senza spedizione):* La percentuale viene calcolata solo sul subtotale dei prodotti.
    -   **Valore consigliato:** `Totale carrello (con spedizione)` poiché è tipicamente così che i corrieri calcolano le loro commissioni per il contrassegno.
    -   **Scenario / esempio del commerciante:** Se il tuo corriere addebita l'1% dell'intero importo che riscuote dal cliente (prodotti + spedizione), scegli "Totale carrello (con spedizione)".
-   **CODPRO\_CHARGEA\_V (Valore commissione importo fisso)**

    -   **Cosa fa questa impostazione:** Questo campo definisce l'importo monetario fisso della commissione per il contrassegno.
    -   **Effetto della modifica di questa impostazione:** Se "Come includere la commissione?" è impostato su un'opzione di importo fisso, questo valore verrà utilizzato.
    -   **Valore consigliato:** `0.00` inizialmente, regola in base all'addebito fisso del tuo corriere.
    -   **Scenario / esempio del commerciante:** Se il tuo corriere addebita un importo fisso di €3.00 per il contrassegno, dovresti inserire `3.00` qui.
-   **CODPRO\_MIN\_CHARGEV (Commissione minima per commissione percentuale)**

    -   **Cosa fa questa impostazione:** Se stai utilizzando una commissione basata su percentuale, questo imposta un importo fisso minimo che la commissione per il contrassegno sarà, anche se la percentuale calcolata è inferiore.
    -   **Effetto della modifica di questa impostazione:** Assicura che tu recuperi sempre almeno un certo importo per il contrassegno, specialmente su piccoli ordini dove una percentuale potrebbe essere molto bassa.
    -   **Valore consigliato:** `0.00` (nessun minimo) o un piccolo importo come `1.00` o `2.00` se hai un costo minimo.
    -   **Scenario / esempio del commerciante:** Se la tua commissione percentuale è dell'1% e un ordine di €50 risulterebbe in una commissione di €0.50, ma desideri assicurare un minimo di €1.50, imposteresti questo a `1.50`.
-   **CODPRO\_MAX\_CHARGEV (Commissione massima per commissione percentuale)**

    -   **Cosa fa questa impostazione:** Se stai utilizzando una commissione basata su percentuale, questo imposta un importo fisso massimo che la commissione per il contrassegno sarà, anche se la percentuale calcolata è superiore.
    -   **Effetto della modifica di questa impostazione:** Impedisce che la commissione per il contrassegno diventi eccessivamente alta su ordini molto grandi.
    -   **Valore consigliato:** `0.00` (nessun massimo) o un limite ragionevole come `10.00` o `15.00`.
    -   **Scenario / esempio del commerciante:** Se la tua commissione percentuale è dell'1% e un ordine di €2000 risulterebbe in una commissione di €20, ma desideri limitare la commissione per il contrassegno a €10, imposteresti questo a `10.00`.
-   **CODPRO\_FEETAX (Applica IVA alla commissione)**

    -   **Cosa fa questa impostazione:** Determina se la commissione per il contrassegno stessa debba essere soggetta a IVA/tasse.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Alla commissione per il contrassegno verrà applicata l'IVA secondo la regola fiscale selezionata.
        -   *Quando disabilitato:* La commissione per il contrassegno sarà trattata come esente da IVA.
    -   **Valore consigliato:** `Abilitato` se le tue normative fiscali locali richiedono che le commissioni siano tassate. Consulta il tuo commercialista.
    -   **Scenario / esempio del commerciante:** In molti paesi, le commissioni di servizio come gli addebiti per il contrassegno sono soggette a IVA. Abiliteresti questo per garantire la conformità.
-   **CODPRO\_FEETAXRULE (Regola fiscale per la commissione)**

    -   **Cosa fa questa impostazione:** Se `CODPRO_FEETAX` è abilitato, questo menu a discesa ti consente di selezionare quale regola fiscale di PrestaShop si applica alla commissione per il contrassegno.
    -   **Effetto della modifica di questa impostazione:** L'aliquota fiscale selezionata verrà applicata alla commissione per il contrassegno.
    -   **Valore consigliato:** Seleziona la regola fiscale appropriata per i servizi nel tuo paese.
    -   **Scenario / esempio del commerciante:** Se hai una regola fiscale "IVA standard (20%)" per i servizi, la selezioneresti qui.

#### **Commissioni specifiche per corriere**

-   **codpro\_carrier (Selezione corriere)**
    -   **Cosa fa questa impostazione:** Questa sezione ti consente di definire diverse commissioni per il contrassegno per ogni corriere che offri.
    -   **Effetto della modifica di questa impostazione:** Quando un cliente seleziona un corriere specifico durante il checkout, verrà applicata la commissione per il contrassegno associata a quel corriere invece della commissione generale.
    -   **Valore consigliato:** Configura le commissioni per tutti i corrieri che offrono il contrassegno.
    -   **Scenario / esempio del commerciante:** Se il Corriere A addebita €3.00 per il contrassegno e il Corriere B addebita l'1.5% del valore dell'ordine, puoi configurare queste commissioni distinte qui.

#### **Impostazioni avanzate (solitamente per sviluppatori/scenari specifici)**

-   **PS\_LANG\_DEFAULT / PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG (Impostazioni lingua)**

    -   **Cosa fa questa impostazione:** Questi sono valori di configurazione standard di PrestaShop relativi alla lingua predefinita e alla lingua del modulo dipendente. Il modulo potrebbe visualizzarli per riferimento ma in genere non richiede modifiche qui.
    -   **Effetto della modifica di questa impostazione:** Nessun effetto diretto sulla funzionalità principale del modulo, ma garantisce la corretta visualizzazione della lingua nel Back Office.
    -   **Valore consigliato:** Lascia come predefinito.
-   **CODPRO\_ANALYTICS\_DEFAULT\_CHART / CODPRO\_ANALYTICS\_PERIOD / CODPRO\_ANALYTICS\_IMPACT\_DAYS / CODPRO\_ANALYTICS\_CHART\_WEEKS / CODPRO\_ANALYTICS\_CHART\_MONTHS (Impostazioni analitiche)**

    -   **Cosa fa questa impostazione:** Queste impostazioni si riferiscono a potenziali analisi interne o funzionalità del dashboard all'interno del modulo (se implementate). Controllano come i dati potrebbero essere visualizzati o filtrati.
    -   **Effetto della modifica di questa impostazione:** Modifica il modo in cui i dati analitici relativi agli ordini in contrassegno potrebbero essere presentati nel Back Office.
    -   **Valore consigliato:** Lascia come predefinito a meno che tu non abbia requisiti analitici specifici.
    -   **Scenario / esempio del commerciante:** Se il modulo include un dashboard, queste impostazioni potrebbero controllare la visualizzazione predefinita (es. ultimi 7 giorni, ultimo mese) per le prestazioni degli ordini in contrassegno.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### **4.2.1 AdminCodProCarriersFeesController (Back Office > Moduli > Contrassegno con commissione > Commissioni corriere)**

-   **Nome schermata e posizione menu:** "Commissioni corriere" (solitamente si trova sotto la voce di menu "Contrassegno con commissione" nel Back Office di PrestaShop).
-   **Azioni e impostazioni disponibili:** Questa schermata fornisce una griglia o una visualizzazione elenco per gestire le commissioni per il contrassegno specificamente per ogni corriere. Puoi aggiungere nuove regole specifiche per corriere, modificare quelle esistenti o eliminarle. Per ogni corriere, puoi definire:
    -   Se la commissione è un importo fisso o una percentuale.
    -   L'importo fisso o il valore percentuale specifico.
    -   Commissioni minime e massime per le commissioni percentuali.
    -   Se si applica l'IVA e quale regola fiscale utilizzare.
-   **Effetto delle modifiche:** Tutte le regole configurate qui sovrascriveranno le impostazioni generali della commissione per il contrassegno per i corrieri specificati. Se un corriere ha una regola qui, verrà applicata la commissione di quella regola. Se un corriere non è elencato qui, verranno applicate le impostazioni generali della commissione per il contrassegno.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Rivedi regolarmente questa sezione se i tuoi contratti con i corrieri o gli addebiti per il contrassegno cambiano. Aggiungi nuovi corrieri man mano che li introduci nel tuo negozio e configura le loro commissioni specifiche per il contrassegno.

#### **4.2.2 AdminCodProCarriersRangeFeesController (Back Office > Moduli > Contrassegno con commissione > Commissioni per intervallo)**

-   **Nome schermata e posizione menu:** "Commissioni per intervallo" (solitamente si trova sotto la voce di menu "Contrassegno con commissione" nel Back Office di PrestaShop).
-   **Azioni e impostazioni disponibili:** Questa schermata ti consente di definire le commissioni per il contrassegno in base al valore totale del carrello del cliente. Puoi impostare diverse strutture di commissioni per vari intervalli di prezzo (es. ordini da €0-€50, €50-€100, ecc.). Per ogni intervallo, puoi definire:
    -   Il valore minimo e massimo del carrello per l'intervallo.
    -   Se la commissione è un importo fisso o una percentuale.
    -   L'importo fisso o il valore percentuale specifico.
    -   Commissioni minime e massime per le commissioni percentuali all'interno di quell'intervallo.
    -   Se si applica l'IVA e quale regola fiscale utilizzare.
-   **Effetto delle modifiche:** Queste regole basate su intervallo forniscono un ulteriore livello di flessibilità. Se il totale del carrello di un cliente rientra in un intervallo definito, verrà applicata la commissione specificata per quell'intervallo. Queste regole possono interagire con le regole specifiche per corriere, consentendo potenzialmente un controllo molto granulare (es. il Corriere A addebita X per ordini inferiori a €50 e Y per ordini superiori a €50).
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Utilizza questa sezione per implementare prezzi dinamici per il contrassegno in base al valore dell'ordine. Questo è particolarmente utile per gestire il rischio su ordini di alto valore o per rendere il contrassegno più attraente per ordini di fascia media.

#### **4.2.3 index.php (Back Office > Moduli > Contrassegno con commissione > Dashboard/Analisi)**

-   **Nome schermata e posizione menu:** Questo controller `index.php` funge tipicamente da segnaposto o punto di ingresso predefinito per la sezione amministrativa di un modulo. Nel contesto di questo modulo, potrebbe essere utilizzato per visualizzare un dashboard o analisi relative agli ordini in contrassegno.
-   **Azioni e impostazioni disponibili:** Se questo controller viene utilizzato per un dashboard, probabilmente visualizzerà grafici, statistiche o indicatori chiave di prestazione (KPI) relativi agli ordini in contrassegno (es. numero di ordini in contrassegno, ricavo totale dal contrassegno, commissione media raccolta per il contrassegno). Potrebbero esserci filtri per intervalli di date o altri parametri.
-   **Effetto delle modifiche:** L'interazione con un dashboard qui cambierebbe solo i dati visualizzati, non la configurazione del negozio.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Controlla periodicamente questo dashboard (se disponibile) per monitorare le prestazioni e l'impatto del tuo metodo di pagamento in contrassegno.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Configurazione principale del modulo** | Abilitato / Disabilitato | Abilitato | Interruttore principale per il metodo di pagamento in contrassegno. |
| | Valore (Commissione base) | 0.00 | Importo/percentuale della commissione predefinita. |
| | Come includere la commissione? | Includi come prodotto/servizio separato | Determina come la commissione appare nel carrello/fattura. |
| | Stato dell'ordine dopo l'acquisto | Pagamento accettato | Stato iniziale per gli ordini in contrassegno. |
| | Mostra riepilogo aggiuntivo | Abilitato | Visualizza la ripartizione dettagliata della commissione prima della conferma. |
| | Condizione valore massimo carrello | Disabilitato | Limita il contrassegno per ordini superiori a un valore. |
| | Valore massimo carrello | 0.00 | Il valore massimo specifico del carrello. |
| | Condizione valore minimo carrello | Disabilitato | Limita il contrassegno per ordini inferiori a un valore. |
| | Valore minimo carrello | 0.00 | Il valore minimo specifico del carrello. |
| | Valore commissione percentuale | 0.00 | Il valore percentuale per la commissione in contrassegno. |
| | Base di calcolo percentuale | Totale carrello (con spedizione) | Su cosa viene calcolata la percentuale. |
| | Valore commissione importo fisso | 0.00 | Il valore dell'importo fisso per la commissione in contrassegno. |
| | Commissione minima (per %) | 0.00 | Assicura una commissione minima per i calcoli percentuali. |
| | Commissione massima (per %) | 0.00 | Limita la commissione per i calcoli percentuali. |
| | Applica IVA alla commissione | Abilitato (se applicabile) | Determina se la commissione in contrassegno è tassata. |
| | Regola fiscale per la commissione | Seleziona la regola fiscale appropriata | Quale regola fiscale si applica alla commissione. |
| **AdminCodProCarriersFees** | Regole commissioni specifiche per corriere | Configura secondo necessità | Sovrascrive la commissione generale per corrieri specifici. |
| **AdminCodProCarriersRangeFees** | Regole commissioni per intervallo di valore ordine | Configura secondo necessità | Applica commissioni diverse in base agli intervalli totali del carrello. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: La commissione per il contrassegno non viene visualizzata nella mia pagina di checkout, o è nel posto sbagliato.**
R1: Questo di solito accade con i temi personalizzati.
-   **Controlla "Mostra riepilogo aggiuntivo prima della conferma":** Assicurati che sia `Abilitato` nella configurazione principale del modulo.
-   **Selettori CSS:** Se il tuo tema utilizza classi CSS non standard, il modulo potrebbe non trovare i punti giusti per iniettare la commissione. Vai alla pagina di configurazione del modulo e controlla i campi dei selettori CSS "Riepilogo carrello", "Riepilogo indirizzo" e "Valore minimo totale carrello". Potrebbe essere necessario che uno sviluppatore web ispezioni l'HTML del tuo tema e fornisca i selettori corretti.
-   **Svuota cache:** Svuota sempre la cache di PrestaShop (Parametri avanzati > Prestazioni > Svuota cache) dopo aver apportato modifiche alla configurazione.

**D2: Ho impostato una commissione, ma non viene applicata agli ordini.**
R2:
-   **Modulo abilitato:** Assicurati che l'interruttore principale "Abilitato / Disabilitato" per il modulo sia impostato su `Abilitato`.
-   **Valore commissione:** Ricontrolla di aver inserito un "Valore" diverso da zero nella configurazione principale, o di aver configurato commissioni specifiche nelle sezioni "Commissioni corriere" o "Commissioni per intervallo".
-   **Condizioni soddisfatte:** Verifica che il carrello del cliente soddisfi eventuali condizioni di "Valore minimo carrello" o "Valore massimo carrello" che hai impostato.
-   **Sovrascritture specifiche per corriere:** Se hai configurato commissioni in "Commissioni corriere", assicurati che il cliente stia selezionando uno di quei corrieri. In caso contrario, dovrebbe essere applicata la commissione generale.
-   **Regola fiscale:** Se stai utilizzando una regola fiscale per la commissione, assicurati che la regola fiscale stessa sia configurata correttamente in PrestaShop.

**D3: Come posso tradurre il testo del modulo (es. "Commissione contrassegno") in altre lingue?**
R3: Puoi tradurre le stringhe del modulo direttamente all'interno di PrestaShop:
-   Vai su **Internazionale > Traduzioni**.
-   Seleziona "Traduzioni dei moduli installati".
-   Scegli il tuo tema, la tua lingua, quindi seleziona "Contrassegno con commissione" dal menu a discesa del modulo.
-   Vedrai un elenco di tutte le stringhe traducibili dal modulo. Inserisci le tue traduzioni e salva.

**D4: Posso offrire il contrassegno solo per specifici gruppi di clienti o paesi?**
R4: Il modulo "Contrassegno con commissione" stesso non ha opzioni integrate per restrizioni di gruppo di clienti o paese. Tuttavia, è possibile utilizzare le restrizioni dei moduli di pagamento principali di PrestaShop:
-   Vai su **Parametri negozio > Impostazioni ordine > Pagamento**.
-   Puoi limitare i metodi di pagamento per valuta, paese o gruppo. Trova "Contrassegno con commissione" e applica le restrizioni desiderate lì.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Contrassegno con commissione" (`codpro`) segue un'architettura standard dei moduli PrestaShop, estendendo `PaymentModule` per integrarsi nel flusso di checkout. Utilizza diversi controller front-office e admin per funzionalità specifiche come la convalida del pagamento, la gestione delle commissioni specifiche per corriere e le configurazioni delle commissioni basate su intervallo. Il modulo si basa fortemente sul sistema di hook di PrestaShop per iniettare la sua logica e visualizzare gli elementi in varie fasi del front-office (checkout, conferma ordine, fattura) e del back-office (visualizzazione ordine). La configurazione è principalmente archiviata in `ps_configuration`, con tabelle personalizzate probabilmente utilizzate per le definizioni delle commissioni basate su corriere e intervallo.

### 4.2 Controller (`controllers/`)

#### **Controller Front-Office**

-   `controllers/front/index.php`
    -   Nome classe: `CodProIndexModuleFrontController` (probabilmente estende `ModuleFrontController`)
    -   Responsabilità: Questo controller potrebbe fungere da punto di ingresso predefinito o gestire il routing di base per le azioni del modulo front-office. Dato lo scopo del modulo, potrebbe essere un segnaposto o utilizzato per semplici richieste AJAX relative agli aggiornamenti del calcolo delle commissioni durante il checkout.
-   `controllers/front/validation.php`
    -   Nome classe: `CodProValidationModuleFrontController` (probabilmente estende `ModuleFrontController`)
    -   Responsabilità: Questo è il controller critico per l'elaborazione del pagamento quando un cliente sceglie "Contrassegno con commissione". Gestisce la convalida finale dell'ordine, applica la commissione per il contrassegno calcolata al carrello e reindirizza il cliente alla pagina di conferma dell'ordine. Interagisce con la classe principale del modulo `codpro.php` per recuperare le impostazioni delle commissioni e aggiornare l'ordine.

#### **Controller Admin Back-Office**

-   `controllers/admin/AdminCodProCarriersFees.php`
    -   Nome classe: `AdminCodProCarriersFeesController` (estende `ModuleAdminController`)
    -   Nome scheda: "Commissioni corriere" (o simile, accessibile tramite il menu del modulo).
    -   Entità gestita: `Configuration` (sebbene gestisca voci di configurazione specifiche relative ai corrieri).
    -   Responsabilità: Fornisce l'interfaccia per la gestione delle commissioni per il contrassegno su base per corriere. Visualizza un elenco di commissioni per corriere configurate, consente di aggiungerne di nuove e di modificare/eliminare le voci esistenti. Probabilmente utilizza `HelperList` e `HelperForm` di PrestaShop per la sua interfaccia utente.
-   `controllers/admin/AdminCodProCarriersRangeFees.php`
    -   Nome classe: `AdminCodProCarriersRangeFeesController` (estende `ModuleAdminController`)
    -   Nome scheda: "Commissioni per intervallo" (o simile, accessibile tramite il menu del modulo).
    -   Entità gestita: `CodProTotal` (probabilmente un `ObjectModel` personalizzato per le commissioni basate su intervallo).
    -   Responsabilità: Gestisce le commissioni per il contrassegno in base agli intervalli totali dell'ordine. Fornisce una griglia per definire, modificare ed eliminare le regole delle commissioni per diversi intervalli di valore del carrello. Questo controller sfrutta anche `HelperList` e `HelperForm` di PrestaShop per la sua interfaccia amministrativa.
-   `controllers/admin/index.php`
    -   Nome classe: `AdminCodProIndexController` (probabilmente estende `ModuleAdminController`)
    -   Nome scheda: Segnaposto o Dashboard.
    -   Entità gestita: Nessuna direttamente.
    -   Responsabilità: Questo controller funge probabilmente da punto di ingresso per un dashboard del modulo o una vista predefinita quando si naviga nella sezione amministrativa del modulo. Potrebbe visualizzare analisi o un riepilogo degli ordini in contrassegno.

### 4.3 Classi e modelli principali (`classes/`)

Il dossier del modulo non indica classi personalizzate nella directory `classes/`. Ciò suggerisce che la logica principale per la gestione delle commissioni per corriere e per intervallo potrebbe essere gestita direttamente all'interno di `AdminCodProCarriersFeesController` e `AdminCodProCarriersRangeFeesController` utilizzando interazioni dirette con il database o definendo semplici array per la configurazione. Tuttavia, `AdminCodProCarriersRangeFeesController` che gestisce `codprototal` implica che *dovrebbe* esserci un `ObjectModel` chiamato `CodProTotal` (o simile) nella directory `classes/`, anche se non esplicitamente elencato nel dossier. In caso contrario, significa che vengono utilizzate query SQL dirette, il che è meno ideale.

### 4.4 Risorse JavaScript (`views/js/`)

-   `views/js/adminCodProCarriersFees.js`
    -   Ambito: Back-office (AdminCodProCarriersFeesController).
    -   Funzionalità: Probabilmente gestisce il comportamento dinamico nella pagina di configurazione delle commissioni del corriere. Ciò potrebbe includere chiamate AJAX per salvare/caricare dati, convalida del modulo o elementi interattivi per aggiungere/rimuovere regole di commissione del corriere.
-   `views/js/adminCodProDashboard.js`
    -   Ambito: Back-office (AdminCodProIndexController o vista dashboard simile).
    -   Funzionalità: Responsabile del rendering di grafici, dell'aggiornamento delle statistiche e della gestione degli elementi interattivi nel dashboard del modulo. Potrebbe utilizzare librerie di grafici (es. Chart.js) ed effettuare richieste AJAX per recuperare dati analitici.
-   `views/js/codpro-checkout.js`
    -   Ambito: Front-office (Pagina di checkout).
    -   Funzionalità: Questo è cruciale per l'esperienza utente front-end. Ascolta i cambiamenti nella selezione del metodo di pagamento (specificamente per "Contrassegno con commissione"), aggiorna dinamicamente il riepilogo dell'ordine per riflettere la commissione per il contrassegno e potenzialmente gestisce le richieste AJAX per ricalcolare le commissioni se il corriere o il contenuto del carrello cambiano. Assicura che la commissione sia visibile prima della conferma dell'ordine.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `views/css/admin_codpro.css`
    -   Ambito: Back-office (Pannello di amministrazione).
    -   Funzionalità: Fornisce lo stile per le pagine di configurazione del modulo, la gestione delle commissioni del corriere, la gestione delle commissioni per intervallo e qualsiasi elemento del dashboard. Garantisce un aspetto coerente all'interno del Back Office di PrestaShop.
    -   Selettori chiave: Probabilmente si rivolge a ID o classi specifici all'interno dei moduli e degli elenchi di amministrazione del modulo (es. `.codpro-admin-form`, `.codpro-dashboard-chart`).
-   `views/css/codpro.css`
    -   Ambito: Front-office (Pagina di checkout, conferma ordine, fattura).
    -   Funzionalità: Stila la visualizzazione della commissione per il contrassegno nel riepilogo del checkout, nelle opzioni di pagamento, nella pagina di conferma dell'ordine e potenzialmente nella fattura PDF. Assicura che la commissione sia chiaramente visibile e integrata con il tema del negozio.
    -   Selettori chiave: Si rivolge agli elementi in cui viene iniettata la commissione per il contrassegno (es. `.codpro-fee-display`, `.payment_option_codpro`, `.order-summary-cod-fee`). Gli sviluppatori potrebbero doverli sovrascrivere nel loro tema per una perfetta integrazione visiva.

### 4.6 Struttura del template Smarty (`views/templates/`)

#### **Template hook (`views/templates/hook/`)**

-   `views/templates/hook/confirmation.tpl`
    -   Hook: `paymentReturn` o simile.
    -   Output: I dettagli della commissione per il contrassegno nella pagina di conferma dell'ordine dopo un ordine in contrassegno riuscito.
-   `views/templates/hook/displayAdminOrder16.tpl`
    -   Hook: `displayAdminOrder` (per PrestaShop 1.6).
    -   Output: Informazioni aggiuntive sulla commissione per il contrassegno all'interno della pagina dei dettagli dell'ordine nel Back Office di PrestaShop 1.6.
-   `views/templates/hook/displayAdminOrder17.tpl`
    -   Hook: `displayAdminOrder` (per PrestaShop 1.7+).
    -   Output: Simile a `displayAdminOrder16.tpl`, ma adattato per il layout della pagina dei dettagli dell'ordine del Back Office di PrestaShop 1.7+.
-   `views/templates/hook/displayOrderDetail.tpl`
    -   Hook: `displayOrderDetail` (cronologia ordini cliente front-office).
    -   Output: Visualizza la commissione per il contrassegno come parte del riepilogo dell'ordine quando un cliente visualizza i dettagli del proprio ordine passato nella sezione "Il mio account".
-   `views/templates/hook/payment.tpl`
    -   Hook: `displayPaymentOptions` o `paymentOptions`.
    -   Output: L'opzione di pagamento "Contrassegno con commissione" nella pagina di checkout, incluso l'importo della commissione calcolato dinamicamente.
-   `views/templates/hook/pdf.tpl`
    -   Hook: `displayPDFInvoice`.
    -   Output: La commissione per il contrassegno come voce di riga nella fattura PDF generata per l'ordine.

#### **Template front-office (`views/templates/front/`)**

-   `views/templates/front/validation.tpl`
    -   Scopo: Questo template è probabilmente utilizzato dal controller frontale `validation.php`. Potrebbe visualizzare un semplice messaggio durante il processo di convalida del pagamento o fungere da pagina di reindirizzamento.

### 4.7 Schema del database e mappa degli hook

#### **Tabelle del database**

-   `ps_configuration`: Archivia tutte le impostazioni generali del modulo (es. `CODPRO_MOD_MAXCART_V`, `CODPRO_CHARGEP_V`, `CODPRO_FEETAX`).
-   `ps_codpro_carrier_fees` (probabilmente): Una tabella personalizzata per archiviare le regole delle commissioni per il contrassegno specifiche per corriere.
    -   Colonne: `id_codpro_carrier_fee`, `id_carrier`, `fee_type` (fisso/percentuale), `fee_value`, `min_charge`, `max_charge`, `tax_enabled`, `id_tax_rule`.
-   `ps_codpro_range_fees` (probabilmente): Una tabella personalizzata per archiviare le regole delle commissioni per il contrassegno basate sull'intervallo di valore dell'ordine.
    -   Colonne: `id_codpro_range_fee`, `min_value`, `max_value`, `fee_type`, `fee_value`, `min_charge`, `max_charge`, `tax_enabled`, `id_tax_rule`.

#### **Tabella degli hook registrati**

| Nome hook | Ambito | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- | --- |
| `displayHeader` | Front-Office | Nella sezione `<head>` di tutte le pagine. | Per includere CSS front-office (`codpro.css`) e JS (`codpro-checkout.js`) nelle pagine pertinenti (es. checkout). |
| `displayPaymentOptions` | Front-Office | Durante la selezione del metodo di pagamento nel checkout. | Per visualizzare "Contrassegno con commissione" come opzione di pagamento, inclusa la commissione calcolata. |
| `paymentOptions` | Front-Office | Equivalente di PrestaShop 1.6 di `displayPaymentOptions`. | Per visualizzare "Contrassegno con commissione" come opzione di pagamento. |
| `paymentReturn` | Front-Office | Nella pagina di conferma dell'ordine dopo il pagamento. | Per visualizzare i dettagli della commissione per il contrassegno nella pagina di conferma. |
| `displayPaymentReturn` | Front-Office | Equivalente di PrestaShop 1.6 di `paymentReturn`. | Per visualizzare i dettagli della commissione per il contrassegno nella pagina di conferma. |
| `displayPDFInvoice` | Front-Office (Generazione PDF) | Quando viene generata una fattura PDF. | Per aggiungere la commissione per il contrassegno come voce di riga nella fattura. |
| `displayOrderDetail` | Front-Office (Il mio account) | Quando un cliente visualizza i dettagli del proprio ordine. | Per mostrare la commissione per il contrassegno nella cronologia ordini del cliente. |
| `displayAdminOrder` | Back-Office (Visualizzazione ordine) | Quando un amministratore visualizza un ordine nel Back Office. | Per visualizzare i dettagli della commissione per il contrassegno nel riepilogo dell'ordine per la revisione dell'amministratore. |
| `ActionAdminControllerSetMedia` | Back-Office (Pagine di amministrazione) | Prima che un controller di amministrazione renda la sua vista. | Per includere CSS back-office (`admin_codpro.css`) e JS (`adminCodProCarriersFees.js`, `adminCodProDashboard.js`) nelle pagine di amministrazione del modulo. |
| `actionValidateOrder` | Back-Office (Elaborazione ordine) | Dopo che un ordine è stato convalidato. | Per eseguire potenzialmente azioni aggiuntive o la registrazione dei dati relativi agli ordini in contrassegno. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, fai riferimento al tuo account cliente su MyPresta.eu.

-   **MyPresta.eu Cronologia ordini e download:** <https://mypresta.eu/my-account/orders/>
-   **Supporto MyPresta.eu:** <https://mypresta.eu/contact>
