---
title: "Contrassegno con riepilogo ordine - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Contrassegno con riepilogo ordine di MyPresta.eu."
sidebar:
  label: "Contrassegno con riepilogo ordine"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Cash on delivery with order summary su MyPresta.eu](https://mypresta.eu/modules/payment-process/cash-on-delivery-with-order-summary.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/payment/cash-on-delivery-with-order-summary/)
>
> ---


# Contrassegno con riepilogo ordine

## 1. Requisiti e compatibilità

-   **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **Compatibilità PHP**: PHP 5.6 - 8.5
-   **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste da PrestaShop stesso e sono sufficienti per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale in cui imposti il comportamento principale e le commissioni per il tuo metodo di pagamento in Contrassegno.

-   **Posizione del menu:** Back Office > Moduli > Gestione moduli > Cerca "Contrassegno con riepilogo ordine" > Fai clic su "Configura".

#### Impostazioni generali

1.  **Disabilita COD per corrieri specifici**
    -   **Cosa fa questa impostazione:** Ti consente di impedire che l'opzione di pagamento in Contrassegno sia disponibile se un cliente sceglie determinati corrieri.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (selezionato per corrieri specifici):* Se un cliente seleziona uno dei corrieri scelti durante il checkout, l'opzione di pagamento in Contrassegno non verrà visualizzata.
        -   *Quando disabilitato (deselezionato per tutti i corrieri):* Il Contrassegno sarà disponibile indipendentemente dal corriere scelto (a meno che non si applichino altre restrizioni).
    -   **Valore consigliato:** Dipende dalla tua logistica di spedizione. Se alcuni corrieri non supportano il COD o addebitano commissioni eccessive, abilita questa opzione.
    -   **Scenario / esempio del commerciante:** Utilizzi un servizio di corriere specifico che non gestisce pagamenti in contanti. Selezioneresti quel corriere in questo elenco per disabilitare il COD per loro.

2.  **Come includere la commissione?**
    -   **Cosa fa questa impostazione:** Determina come viene calcolata e applicata la commissione di Contrassegno all'ordine.
    -   **Effetto della modifica di questa impostazione:**
        -   *Includi nei costi di spedizione:* La commissione COD verrà aggiunta direttamente al costo di spedizione mostrato al cliente. Questo può semplificare la visualizzazione del checkout ma potrebbe oscurare l'addebito separato del COD.
        -   *Includi come prodotto separato:* La commissione COD apparirà come voce separata nel carrello e nel riepilogo dell'ordine, spesso etichettata come "Commissione Contrassegno" o simile. Questo fornisce la massima trasparenza.
    -   **Valore consigliato:** "Includi come prodotto separato" per chiarezza e conformità legale, soprattutto nell'UE.
    -   **Scenario / esempio del commerciante:** Per mostrare chiaramente ai clienti il costo esatto dell'utilizzo del COD, selezioneresti "Includi come prodotto separato".

3.  **Stato dell'ordine dopo l'acquisto con modulo COD**
    -   **Cosa fa questa impostazione:** Imposta lo stato iniziale di un ordine effettuato utilizzando il metodo Contrassegno.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su "Pagamento accettato":* L'ordine verrà immediatamente contrassegnato come pagato, il che potrebbe essere fuorviante poiché il contante non è ancora stato riscosso.
        -   *Quando impostato su "In attesa di convalida Contrassegno" (o simile):* L'ordine sarà in uno stato di attesa, indicando che il pagamento è previsto alla consegna. Questo è generalmente più sicuro e accurato.
    -   **Valore consigliato:** Uno stato di attesa come "In attesa di convalida Contrassegno" o "Pagamento in sospeso" per riflettere accuratamente lo stato del pagamento.
    -   **Scenario / esempio del commerciante:** Per evitare di spedire prematuramente un ordine che non è stato pagato, imposteresti questo su uno stato di attesa.

4.  **Mostra riepilogo aggiuntivo prima della conferma**
    -   **Cosa fa questa impostazione:** Controlla se il modulo visualizza la pagina di riepilogo dell'ordine pre-conferma dedicata. Questa è la funzionalità principale di conformità del modulo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Dopo aver selezionato COD, i clienti vedranno un riepilogo dettagliato del loro ordine, inclusi tutti i costi, prima di poter fare clic sul pulsante finale "Conferma ordine".
        -   *Quando disabilitato:* Il modulo salterà questa pagina di riepilogo e i clienti procederanno direttamente alla conferma dell'ordine standard di PrestaShop (che potrebbe non essere legalmente conforme in alcune regioni).
    -   **Valore consigliato:** **Abilitato**. Questa è una caratteristica chiave per la conformità legale e la fiducia del cliente.
    -   **Scenario / esempio del commerciante:** Per conformarsi alle leggi sui consumatori dell'UE che richiedono un riepilogo chiaro dell'ordine prima della conferma finale, **devi** abilitare questa impostazione.

#### Restrizioni sul valore del carrello

5.  **Valore minimo totale carrello**
    -   **Cosa fa questa impostazione:** Imposta il valore totale minimo che un ordine deve avere affinché l'opzione di pagamento in Contrassegno sia disponibile.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su un valore (ad esempio, 10.00):* Se il totale del carrello del cliente è inferiore a questo importo, il Contrassegno non verrà offerto come opzione di pagamento.
        -   *Quando lasciato vuoto o impostato su 0:* Non ci sarà alcuna restrizione sul valore minimo del carrello per il COD.
    -   **Valore consigliato:** Imposta un minimo ragionevole se il costo operativo di elaborazione di piccoli ordini COD è troppo elevato. Altrimenti, lascia vuoto.
    -   **Scenario / esempio del commerciante:** Se il costo di elaborazione di un ordine COD (commissioni del corriere, lavoro amministrativo) è di €5, potresti impostare un valore minimo del carrello di €10 per garantire la redditività.

6.  **Valore massimo totale carrello**
    -   **Cosa fa questa impostazione:** Imposta il valore totale massimo che un ordine può avere affinché l'opzione di pagamento in Contrassegno sia disponibile.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su un valore (ad esempio, 500.00):* Se il totale del carrello del cliente supera questo importo, il Contrassegno non verrà offerto come opzione di pagamento.
        -   *Quando lasciato vuoto o impostato su 0:* Non ci sarà alcuna restrizione sul valore massimo del carrello per il COD.
    -   **Valore consigliato:** Imposta un massimo se vuoi limitare il rischio per ordini di valore molto elevato che potrebbero essere soggetti a frode o mancata riscossione. Altrimenti, lascia vuoto.
    -   **Scenario / esempio del commerciante:** Per mitigare il rischio di mancato pagamento per ordini molto costosi, potresti impostare un valore massimo del carrello di €200 per il COD.

#### Impostazioni commissione Contrassegno

7.  **Tipo di commissione COD (Percentuale o Importo)**
    -   **Cosa fa questa impostazione:** Determina se la commissione COD è un importo fisso o una percentuale del totale dell'ordine.
    -   **Effetto della modifica di questa impostazione:**
        -   *Percentuale:* La commissione verrà calcolata come percentuale del totale dell'ordine.
        -   *Importo:* La commissione sarà un valore monetario fisso.
    -   **Valore consigliato:** Scegli in base alla tua struttura dei costi. Se i tuoi costi aumentano con il valore dell'ordine, usa la percentuale. Se è una commissione di gestione fissa, usa l'importo.
    -   **Scenario / esempio del commerciante:** Se la tua banca addebita una percentuale del valore della transazione per la gestione del contante, sceglieresti "Percentuale". Se il tuo corriere addebita una commissione fissa per il COD, sceglieresti "Importo".

8.  **Valore commissione COD (Percentuale)** (Appare se "Percentuale" è selezionato sopra)
    -   **Cosa fa questa impostazione:** Il valore percentuale da addebitare come commissione COD.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su 5:* La commissione COD sarà il 5% del totale dell'ordine.
    -   **Valore consigliato:** Una percentuale che copra i tuoi costi senza scoraggiare i clienti.
    -   **Scenario / esempio del commerciante:** Per coprire una commissione bancaria del 2% per i depositi in contanti, potresti impostare questo su "2".

9.  **Valore commissione COD (Importo)** (Appare se "Importo" è selezionato sopra)
    -   **Cosa fa questa impostazione:** Il valore monetario fisso da addebitare come commissione COD.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su 2.50:* La commissione COD sarà di €2.50 (o la tua valuta predefinita) indipendentemente dal totale dell'ordine.
    -   **Valore consigliato:** Un importo fisso che copra i tuoi costi di gestione fissi.
    -   **Scenario / esempio del commerciante:** Se il tuo corriere addebita un fisso di €3 per il servizio COD, imposteresti questo su "3".

10. **Commissione COD minima**
    -   **Cosa fa questa impostazione:** Imposta un importo minimo per la commissione COD, indipendentemente dal calcolo percentuale.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su 1.00 e la percentuale calcola 0.50:* La commissione sarà 1.00.
        -   *Quando impostato su 1.00 e la percentuale calcola 2.00:* La commissione sarà 2.00.
    -   **Valore consigliato:** Utile se hai un costo minimo associato al COD anche per piccoli ordini.
    -   **Scenario / esempio del commerciante:** Se il 5% di un ordine di €10 è solo €0.50, ma il tuo costo di gestione minimo è €1, imposteresti questo su "1.00".

11. **Commissione COD massima**
    -   **Cosa fa questa impostazione:** Imposta un importo massimo per la commissione COD, indipendentemente dal calcolo percentuale.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su 10.00 e la percentuale calcola 15.00:* La commissione sarà 10.00.
        -   *Quando impostato su 10.00 e la percentuale calcola 5.00:* La commissione sarà 5.00.
    -   **Valore consigliato:** Utile per evitare che la commissione COD diventi eccessivamente alta per ordini molto grandi.
    -   **Scenario / esempio del commerciante:** Per garantire che la commissione COD non diventi proibitiva per ordini di grandi dimensioni, potresti limitarla a €15.

12. **Applica tasse alla commissione COD**
    -   **Cosa fa questa impostazione:** Determina se la commissione di Contrassegno stessa è soggetta a imposta sulle vendite.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Potrai selezionare una regola fiscale da applicare alla commissione COD.
        -   *Quando disabilitato:* La commissione COD sarà esente da tasse.
    -   **Valore consigliato:** Consulta le tue normative fiscali locali. In molte regioni, le commissioni di elaborazione dei pagamenti sono tassabili.
    -   **Scenario / esempio del commerciante:** Se le leggi fiscali del tuo paese richiedono di addebitare l'IVA sulle commissioni dei servizi di pagamento, abiliteresti questa opzione e selezioneresti la regola fiscale appropriata.

13. **Regola fiscale per commissione COD** (Appare se "Applica tasse alla commissione COD" è abilitato)
    -   **Cosa fa questa impostazione:** Ti consente di selezionare una regola fiscale esistente dal tuo negozio PrestaShop da applicare alla commissione COD.
    -   **Effetto della modifica di questa impostazione:** L'aliquota fiscale selezionata verrà applicata alla commissione COD calcolata.
    -   **Valore consigliato:** Seleziona la regola fiscale che corrisponde alle commissioni di elaborazione dei pagamenti nella tua giurisdizione.
    -   **Scenario / esempio del commerciante:** Se hai una regola fiscale "IVA 20%", la selezioneresti qui per applicare il 20% di IVA alla commissione COD.

#### Impostazioni di visualizzazione avanzate

14. **Selettore CSS per totale carrello**
    -   **Cosa fa questa impostazione:** Ti consente di specificare il selettore CSS per l'elemento che visualizza il valore totale del carrello nella tua pagina di checkout. Questo aiuta il modulo ad aggiornare accuratamente il totale quando viene applicata una commissione COD.
    -   **Effetto della modifica di questa impostazione:** Se impostato correttamente, il modulo può aggiornare dinamicamente il totale nella pagina di checkout per includere la commissione COD. Se errato, il totale potrebbe non aggiornarsi, causando confusione.
    -   **Valore consigliato:** Lascia vuoto a meno che non si verifichino problemi di visualizzazione con il totale che non si aggiorna. Se necessario, consulta lo sviluppatore del tuo tema o usa gli strumenti di sviluppo del browser per trovare il selettore corretto (ad esempio, `.cart-total-value`).
    -   **Scenario / esempio del commerciante:** Se il tuo tema utilizza una classe personalizzata come `.mytheme-total-price` per il totale del carrello, la inseriresti qui.

15. **Selettore CSS per subtotale carrello**
    -   **Cosa fa questa impostazione:** Simile al totale del carrello, questo specifica il selettore CSS per il subtotale del carrello.
    -   **Effetto della modifica di questa impostazione:** Aiuta il modulo a identificare correttamente e potenzialmente aggiornare la visualizzazione del subtotale.
    -   **Valore consigliato:** Lascia vuoto a meno che non si verifichino problemi di visualizzazione.
    -   **Scenario / esempio del commerciante:** Se il tuo tema ha un elemento specifico per il subtotale, potresti dover inserire il suo selettore qui.

16. **Selettore CSS per spedizione carrello**
    -   **Cosa fa questa impostazione:** Simile al totale del carrello, questo specifica il selettore CSS per la visualizzazione del costo di spedizione.
    -   **Effetto della modifica di questa impostazione:** Aiuta il modulo a identificare correttamente e potenzialmente aggiornare la visualizzazione del costo di spedizione, soprattutto se la commissione COD è inclusa nella spedizione.
    -   **Valore consigliato:** Lascia vuoto a meno che non si verifichino problemi di visualizzazione.
    -   **Scenario / esempio del commerciante:** Se il tuo tema ha un elemento specifico per il costo di spedizione, potresti dover inserire il suo selettore qui.

17. **Logo COD**
    -   **Cosa fa questa impostazione:** Ti consente di caricare un logo personalizzato che verrà visualizzato accanto all'opzione di pagamento in Contrassegno durante il checkout.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando caricato:* Verrà visualizzata un'icona o un logo visivo, rendendo l'opzione COD più prominente e visivamente accattivante.
        -   *Quando vuoto:* Non verrà visualizzato alcun logo personalizzato.
    -   **Valore consigliato:** Carica un logo piccolo e chiaro (ad esempio, un'icona di contanti) per migliorare l'esperienza utente.
    -   **Scenario / esempio del commerciante:** Per far risaltare l'opzione COD, potresti caricare una piccola immagine di banconote o monete.

#### Impostazioni di analisi (Uso interno del modulo)

Queste impostazioni sono tipicamente per l'analisi interna del modulo e di solito non richiedono l'intervento del commerciante.

18. **CODPRO_ANALYTICS_DEFAULT_CHART, CODPRO_ANALYTICS_PERIOD, CODPRO_ANALYTICS_IMPACT_DAYS, CODPRO_ANALYTICS_CHART_WEEKS, CODPRO_ANALYTICS_CHART_MONTHS**
    -   **Cosa fanno queste impostazioni:** Queste sono chiavi di configurazione interne utilizzate dal modulo per potenziali future funzionalità di analisi o visualizzazioni del dashboard all'interno della propria amministrazione del modulo. Controllano come i dati potrebbero essere raccolti o visualizzati per il monitoraggio delle prestazioni.
    -   **Effetto della modifica di queste impostazioni:** Improbabile che abbiano un impatto diretto e immediato sull'esperienza del cliente nel front-office. Influisce principalmente sulla potenziale reportistica del back-office.
    -   **Valore consigliato:** Lascia i loro valori predefiniti.
    -   **Scenario / esempio del commerciante:** Questi non vengono tipicamente regolati dai commercianti.

### 2.2 Schermate di amministrazione dedicate e viste del controller

Il modulo fornisce due schermate di amministrazione aggiuntive per un controllo più granulare sulle commissioni COD, particolarmente utili per strategie di spedizione e prezzi complesse.

#### 2.2.1 AdminCodProCarriersFeesController: Commissioni COD specifiche per corriere

-   **Nome schermata e posizione del menu:** Back Office > Moduli > Gestione moduli > Cerca "Contrassegno con riepilogo ordine" > Fai clic su "Configura" > Cerca una scheda o un link etichettato "Commissioni corriere" o simile (questo potrebbe essere integrato nella configurazione principale o in una voce di menu separata a seconda della versione di PrestaShop).
-   **Azioni e impostazioni disponibili:** Questa schermata presenta tipicamente una griglia o una tabella in cui è possibile definire diverse commissioni di Contrassegno in base al corriere selezionato. È possibile aggiungere, modificare o eliminare queste regole di commissione specifiche per corriere.
    -   **Selezione corriere:** Scegli un corriere specifico.
    -   **Tipo di commissione:** Seleziona se la commissione è un importo fisso o una percentuale.
    -   **Valore commissione:** Inserisci l'importo o la percentuale.
    -   **Regola fiscale:** Applica una regola fiscale specifica alla commissione COD di questo corriere.
-   **Effetto delle modifiche:** Quando un cliente seleziona un corriere per il quale hai definito una commissione COD specifica qui, tale commissione sovrascriverà la commissione COD generale impostata nella configurazione principale del modulo. Ciò consente una personalizzazione dei prezzi altamente personalizzata.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Accedi a questa schermata se devi addebitare commissioni COD diverse in base al corriere che consegna il pacco.
    2.  Fai clic su "Aggiungi nuova commissione corriere" (o pulsante simile).
    3.  Seleziona il corriere, definisci il tipo di commissione (importo/percentuale), il valore e la regola fiscale.
    4.  Salva le modifiche.
    5.  Rivedi l'elenco per assicurarti che tutte le commissioni specifiche per corriere siano impostate correttamente.
-   **Scenario / esempio del commerciante:** Il tuo servizio postale nazionale addebita una commissione fissa di €2 per il COD, ma un corriere espresso privato addebita il 3% del valore dell'ordine. Utilizzeresti questa schermata per impostare queste commissioni distinte per ciascun corriere.

#### 2.2.2 AdminCodProCarriersRangeFeesController: Commissioni COD specifiche per corriere e intervallo totale

-   **Nome schermata e posizione del menu:** Back Office > Moduli > Gestione moduli > Cerca "Contrassegno con riepilogo ordine" > Fai clic su "Configura" > Cerca una scheda o un link etichettato "Commissioni per intervallo" o simile.
-   **Azioni e impostazioni disponibili:** Questa schermata fornisce un livello ancora più avanzato di controllo delle commissioni. È possibile definire commissioni COD che variano non solo per corriere ma anche per il *valore totale del carrello del cliente*. Questo è spesso presentato come una griglia in cui si definiscono intervalli (ad esempio, "Totale ordine da €0 a €50", "Totale ordine da €50 a €100").
    -   **Selezione corriere:** Scegli un corriere specifico.
    -   **Totale ordine minimo:** Il limite inferiore dell'intervallo di valore dell'ordine.
    -   **Totale ordine massimo:** Il limite superiore dell'intervallo di valore dell'ordine.
    -   **Tipo di commissione:** Importo fisso o percentuale.
    -   **Valore commissione:** L'importo o la percentuale per questo specifico corriere e intervallo totale dell'ordine.
    -   **Regola fiscale:** Applica una regola fiscale specifica.
-   **Effetto delle modifiche:** Queste commissioni basate su intervallo hanno la precedenza sia sulla commissione COD generale che sulle semplici commissioni specifiche per corriere. Consentono strategie di prezzo altamente dinamiche.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  Utilizza questa schermata per le strutture di commissione COD più complesse.
    2.  Fai clic su "Aggiungi nuova commissione per intervallo" (o simile).
    3.  Seleziona il corriere, definisci il totale minimo e massimo dell'ordine per questa regola.
    4.  Specifica il tipo di commissione, il valore e la regola fiscale per questo particolare intervallo.
    5.  Salva e ripeti per tutti gli intervalli e i corrieri necessari.
-   **Scenario / esempio del commerciante:** Per un corriere specifico, potresti addebitare una commissione COD di €3 per ordini inferiori a €50, ma una commissione del 2% per ordini tra €50 e €200, e una commissione fissa di €5 per ordini superiori a €200. Questa schermata ti consente di impostare tali prezzi a livelli.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
|---|---|---|---|
| **Configurazione modulo** | Disabilita COD per corrieri specifici | No (tutti abilitati) | Limita la disponibilità del COD in base al corriere di spedizione scelto. |
| | Come includere la commissione? | Includi come prodotto separato | Determina come la commissione COD appare nel carrello/ordine. "Prodotto separato" per chiarezza. |
| | Stato dell'ordine dopo l'acquisto con modulo COD | In attesa di convalida COD | Imposta lo stato iniziale dell'ordine; "In attesa di convalida COD" è consigliato per accuratezza. |
| | Mostra riepilogo aggiuntivo prima della conferma | Abilitato | **CRITICO:** Visualizza il riepilogo legale pre-conferma. **Abilitato** per conformità. |
| | Valore minimo totale carrello | Vuoto / 0 | Valore minimo dell'ordine per il COD. Imposta se i piccoli ordini non sono redditizi. |
| | Valore massimo totale carrello | Vuoto / 0 | Valore massimo dell'ordine per il COD. Imposta per mitigare il rischio su ordini di grandi dimensioni. |
| | Tipo di commissione COD | Importo | Scegli se la commissione è fissa o basata su percentuale. |
| | Valore commissione COD (Percentuale) | 0 | Percentuale del totale dell'ordine per la commissione COD. |
| | Valore commissione COD (Importo) | 0 | Importo monetario fisso per la commissione COD. |
| | Commissione COD minima | 0 | Garantisce che venga addebitata una commissione minima, anche se la percentuale è bassa. |
| | Commissione COD massima | 0 | Limita la commissione COD per evitare che diventi troppo alta. |
| | Applica tasse alla commissione COD | No | Determina se la tassa viene applicata alla commissione COD. Consulta le leggi fiscali locali. |
| | Regola fiscale per commissione COD | (Nessuno) | Seleziona la regola fiscale se "Applica tasse" è abilitato. |
| | Selettore CSS per totale carrello | Vuoto | Avanzato: selettore CSS per la visualizzazione del totale del carrello. Lascia vuoto a meno che non ci siano problemi. |
| | Selettore CSS per subtotale carrello | Vuoto | Avanzato: selettore CSS per la visualizzazione del subtotale del carrello. Lascia vuoto a meno che non ci siano problemi. |
| | Selettore CSS per spedizione carrello | Vuoto | Avanzato: selettore CSS per la visualizzazione del costo di spedizione. Lascia vuoto a meno che non ci siano problemi. |
| | Logo COD | Vuoto | Carica un logo personalizzato per l'opzione di pagamento COD. |
| **AdminCodProCarriersFees** | Commissioni specifiche per corriere | N/A | Definisci le commissioni COD che variano in base al corriere di spedizione. |
| **AdminCodProCarriersRangeFees** | Commissioni specifiche per corriere e intervallo | N/A | Definisci le commissioni COD che variano in base al corriere E all'intervallo totale dell'ordine. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: L'opzione COD non viene visualizzata per i clienti.**
R1: Controlla quanto segue:
    *   **Modulo abilitato:** Il modulo "Contrassegno con riepilogo ordine" è abilitato in **Moduli > Gestione moduli**?
    *   **Restrizioni di pagamento:** Vai su **Parametri negozio > Impostazioni ordine > Pagamenti** (o **Pagamento > Preferenze** nelle versioni precedenti). Assicurati che "Contrassegno con riepilogo ordine" non sia limitato per gruppo di clienti, valuta o paese.
    *   **Restrizioni corriere:** Nella configurazione del modulo, controlla "Disabilita COD per corrieri specifici". Il corriere scelto dal cliente è stato accidentalmente selezionato?
    *   **Restrizioni valore carrello:** Controlla "Valore minimo totale carrello" e "Valore massimo totale carrello" nella configurazione del modulo. Il carrello del cliente rientra in questi limiti?
    *   **Zone geografiche:** Assicurati che il modulo sia abilitato per il paese del cliente in **Parametri negozio > Impostazioni ordine > Pagamenti > Restrizioni per zona/paese**.

**D2: La commissione COD non viene visualizzata o non viene calcolata correttamente.**
R2:
    *   **Impostazioni commissione:** Ricontrolla le impostazioni "Tipo di commissione COD" (Percentuale/Importo) e "Valore commissione COD" nella configurazione principale del modulo.
    *   **Commissioni corriere/intervallo:** Se stai utilizzando `AdminCodProCarriersFees` o `AdminCodProCarriersRangeFees`, assicurati che le regole siano definite correttamente per il corriere e il totale dell'ordine specifici. Queste regole specifiche sovrascrivono le impostazioni generali.
    *   **Regole fiscali:** Se "Applica tasse alla commissione COD" è abilitato, assicurati che sia selezionata una regola fiscale valida.
    *   **Cache:** Svuota la cache di PrestaShop (**Parametri avanzati > Prestazioni > Svuota cache**). A volte i dati vecchi possono impedire l'aggiornamento delle commissioni.

**D3: La pagina di riepilogo pre-conferma non viene visualizzata, o l'ordine va direttamente alla conferma.**
R3:
    *   **Impostazione "Mostra riepilogo aggiuntivo prima della conferma":** Nella configurazione principale del modulo, assicurati che questa impostazione sia **Abilitata**. Questo è cruciale affinché la pagina di riepilogo appaia.
    *   **Compatibilità tema:** Sebbene il modulo sia progettato per essere compatibile, alcuni temi pesantemente personalizzati potrebbero interferire. Se la pagina di riepilogo non appare ancora, passa temporaneamente al tema predefinito di PrestaShop per escludere un conflitto di tema. Se funziona sul tema predefinito, contatta lo sviluppatore del tuo tema o un esperto di PrestaShop.

**D4: La commissione COD non viene visualizzata sulla fattura PDF.**
R4:
    *   **Modulo attivo:** Assicurati che il modulo sia abilitato.
    *   **Generazione fattura:** Rigenera la fattura PDF per un ordine effettuato con COD *dopo* che il modulo è stato configurato correttamente. Le vecchie fatture potrebbero non riflettere le nuove impostazioni.
    *   **Versione PrestaShop:** Assicurati che la tua versione di PrestaShop sia completamente supportata. Sebbene il modulo miri a un'ampia compatibilità, versioni molto vecchie o molto nuove potrebbero presentare piccole anomalie di visualizzazione.

**D5: Come posso cambiare il testo "Contrassegno" o la descrizione della commissione?**
R5:
    *   **Traduzioni:** Vai su **Internazionale > Traduzioni**. Seleziona "Traduzioni moduli installati", scegli il tuo tema e poi seleziona "Contrassegno con riepilogo ordine". Potrai quindi trovare e modificare tutte le stringhe traducibili utilizzate dal modulo.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura
Il modulo "Contrassegno con riepilogo ordine" (`codpro`) è un modulo di pagamento standard di PrestaShop che segue il modello MVC (Model-View-Controller). Estende `PaymentModule` e sfrutta vari hook di PrestaShop per iniettare la sua opzione di pagamento, visualizzare il riepilogo pre-conferma e gestire lo stato dell'ordine e le commissioni. Utilizza valori di configurazione memorizzati in `ps_configuration` per le sue impostazioni e include controller admin personalizzati per la gestione avanzata delle commissioni. Il modulo calcola e visualizza dinamicamente le commissioni COD, integrandole nel carrello e nei totali dell'ordine.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office
-   `controllers/front/index.php`
    *   **Nome classe:** `CodProIndexModuleFrontController` (probabilmente, in base alla convenzione di denominazione dei file)
    *   **Classe genitore:** `ModuleFrontController`
    *   **Responsabilità:** Questo controller potrebbe essere un segnaposto o gestire il routing iniziale per i componenti front-office del modulo. Dato il controller `validation.php`, `index.php` potrebbe non avere una rotta diretta rivolta all'utente ma potrebbe essere utilizzato per la logica interna del modulo o i reindirizzamenti.
-   `controllers/front/validation.php`
    *   **Nome classe:** `CodProValidationModuleFrontController`
    *   **Classe genitore:** `ModuleFrontController`
    *   **Responsabilità:** Questo è il controller critico per l'elaborazione della conferma finale dell'ordine. Riceve i dati POST dalla pagina di riepilogo pre-conferma, convalida l'ordine, crea l'ordine in PrestaShop e reindirizza il cliente alla pagina di conferma dell'ordine (`paymentReturn`). Gestisce la logica per l'applicazione della commissione COD all'ordine.

#### Controller Admin Back-Office
-   `controllers/admin/AdminCodProCarriersFees.php`
    *   **Nome classe:** `AdminCodProCarriersFeesController`
    *   **Classe genitore:** `ModuleAdminController`
    *   **Nome scheda:** Probabilmente una sotto-scheda sotto la configurazione principale del modulo o una voce di menu personalizzata.
    *   **Entità gestita:** Gestisce le voci di configurazione relative alle commissioni COD specifiche per corriere.
    *   **Responsabilità:** Fornisce l'interfaccia (un `HelperList` o `HelperForm` basato sui modelli di `AdminController`) per gli amministratori per definire, modificare ed eliminare le commissioni di Contrassegno specifiche per i singoli corrieri. Gestisce le operazioni CRUD per queste regole di commissione.
-   `controllers/admin/AdminCodProCarriersRangeFees.php`
    *   **Nome classe:** `AdminCodProCarriersRangeFeesController`
    *   **Classe genitore:** `ModuleAdminController`
    *   **Nome scheda:** Probabilmente una sotto-scheda sotto la configurazione principale del modulo.
    *   **Entità gestita:** Gestisce le voci nella tabella `codprototal` (o simile, in base alle chiavi di configurazione `CODPRO_MOD_MAXCART_V` e `CODPRO_MOD_MINCART_V`).
    *   **Responsabilità:** Fornisce l'interfaccia per gli amministratori per definire, modificare ed eliminare le commissioni di Contrassegno che dipendono sia dal corriere selezionato che dal valore totale del carrello del cliente (cioè, commissioni basate su intervallo). Gestisce le operazioni CRUD per queste complesse regole di commissione.
-   `controllers/admin/index.php`
    *   **Nome classe:** (Non una tipica classe controller, di solito un reindirizzamento o una misura di sicurezza)
    *   **Classe genitore:** N/A
    *   **Responsabilità:** Spesso una misura di sicurezza per impedire l'elenco diretto delle directory o per reindirizzare alla configurazione principale del modulo. Tipicamente contiene un semplice `header('Location: ../../index.php?controller=AdminModules&token=...')` o `die('Forbidden');`.

### 4.3 Classi e modelli principali (`classes/`)
Le informazioni sul modulo fornite indicano l'assenza di classi personalizzate nella directory `classes/`. Ciò suggerisce che la logica principale del modulo, la gestione dei dati e le eventuali definizioni di `ObjectModel` (se vengono utilizzate tabelle personalizzate oltre a `ps_configuration`) sono incapsulate direttamente nel file principale `codpro.php` o gestite tramite `ObjectModel` standard di PrestaShop come `Order` e `Cart`.

### 4.4 Risorse JavaScript (`views/js/`)

-   `codpro/views/js/adminCodProCarriersFees.js`
    *   **Ambito:** Back-office (AdminCodProCarriersFeesController)
    *   **Responsabilità:** Probabilmente gestisce le interazioni dinamiche nella pagina di amministrazione delle commissioni specifiche per corriere. Ciò potrebbe includere chiamate AJAX per aggiungere/modificare commissioni, convalida dei moduli o aggiornamento della visualizzazione dell'elenco delle commissioni.
-   `codpro/views/js/adminCodProDashboard.js`
    *   **Ambito:** Back-office (potenzialmente la pagina di configurazione principale del modulo se include analisi)
    *   **Responsabilità:** Date le chiavi di configurazione `CODPRO_ANALYTICS_`, questo script è probabilmente responsabile del rendering di grafici, diagrammi o altri dati analitici relativi agli ordini COD all'interno dell'interfaccia back-office del modulo. Potrebbe utilizzare una libreria di grafici (ad esempio, Chart.js) ed effettuare richieste AJAX per recuperare i dati.
-   `codpro/views/js/codpro-checkout.js`
    *   **Ambito:** Front-office (Pagina di checkout)
    *   **Responsabilità:** Questo è uno script cruciale per l'esperienza front-office. Ascolta i cambiamenti nel processo di checkout (ad esempio, selezione del COD come metodo di pagamento, cambio del corriere, aggiornamento della quantità del carrello). Aggiorna dinamicamente le visualizzazioni del totale del carrello, del subtotale e del costo di spedizione (utilizzando i selettori CSS definiti nella configurazione del modulo) per riflettere la commissione COD calcolata. Potrebbe anche gestire il reindirizzamento alla pagina di riepilogo pre-conferma.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `codpro/views/css/admin_codpro.css`
    *   **Ambito:** Back-office (Pagine di amministrazione relative al modulo)
    *   **Responsabilità:** Fornisce lo stile per i moduli di configurazione, gli elenchi e potenzialmente qualsiasi elemento personalizzato del dashboard all'interno del back office di PrestaShop. Garantisce un'interfaccia di amministrazione coerente e intuitiva.
    *   **Selettori di classe CSS chiave:** Probabilmente si rivolge a elementi all'interno dei modelli `HelperForm` o `HelperList` del modulo, o a elementi personalizzati specifici delle viste amministrative del modulo.
-   `codpro/views/css/codpro.css`
    *   **Ambito:** Front-office (Pagina di checkout, riepilogo pre-conferma, dettagli dell'ordine)
    *   **Responsabilità:** Stila la visualizzazione dell'opzione di pagamento in Contrassegno, la pagina di riepilogo pre-conferma e la visualizzazione della commissione COD nelle pagine dei dettagli dell'ordine e nelle fatture. Garantisce che gli elementi del modulo si integrino visivamente con il tema del negozio.
    *   **Selettori di classe CSS chiave:** Si rivolgerà a elementi come il blocco dell'opzione di pagamento COD, la tabella di riepilogo, le voci di commissione e potenzialmente qualsiasi avviso o messaggio personalizzato introdotto dal modulo. Gli sviluppatori possono sovrascriverli nel `custom.css` del loro tema o utilizzando selettori più specifici.

### 4.6 Struttura del modello Smarty (`views/templates/`)

#### Modelli hook (`views/templates/hook/`)
-   `codpro/views/templates/hook/confirmation.tpl`
    *   **Hook:** `displayPaymentReturn`
    *   **Output:** Contenuto visualizzato nella pagina di conferma dell'ordine dopo un ordine COD riuscito. Potrebbe includere un messaggio che ricorda al cliente il pagamento in contanti alla consegna.
-   `codpro/views/templates/hook/displayAdminOrder16.tpl`
    *   **Hook:** `displayAdminOrder` (per PrestaShop 1.6.x)
    *   **Output:** Aggiunge informazioni specifiche relative al pagamento COD (ad esempio, dettagli della commissione) alla pagina di visualizzazione dell'ordine nel back office di PrestaShop 1.6.
-   `codpro/views/templates/hook/displayAdminOrder17.tpl`
    *   **Hook:** `displayAdminOrder` (per PrestaShop 1.7.x, 8.x, 9.x)
    *   **Output:** Simile a `displayAdminOrder16.tpl`, ma adattato per la visualizzazione dell'ordine nel back office di PrestaShop 1.7+, visualizzando i dettagli del pagamento COD.
-   `codpro/views/templates/hook/displayOrderDetail.tpl`
    *   **Hook:** `displayOrderDetail`
    *   **Output:** Visualizza informazioni specifiche del COD (ad esempio, la ripartizione della commissione) nella pagina dei dettagli dell'ordine del cliente nel front office.
-   `codpro/views/templates/hook/payment.tpl`
    *   **Hook:** `paymentOptions` o `displayPaymentOptions`
    *   **Output:** Renderizza il blocco dell'opzione di pagamento "Contrassegno" nella pagina di checkout, inclusi il logo del modulo e qualsiasi commissione visualizzata.
-   `codpro/views/templates/hook/pdf.tpl`
    *   **Hook:** `displayPDFInvoice`
    *   **Output:** Inietta la commissione di Contrassegno come voce o riepilogo nelle fatture PDF generate.

#### Modelli Front-office (`views/templates/front/`)
-   `codpro/views/templates/front/validation.tpl`
    *   **Output:** Questo è il modello per la cruciale pagina di riepilogo dell'ordine pre-conferma. Visualizza il riepilogo completo del carrello, l'indirizzo di spedizione, i costi totali (inclusa la commissione COD) e il pulsante finale "Conferma ordine". Questo modello viene renderizzato dal controller frontale `validation.php`.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database
Il modulo utilizza principalmente la tabella standard `ps_configuration` per memorizzare le sue impostazioni (ad esempio, `CODPRO_MOD_MAXCART`, `CODPRO_FEEPAY`, `CODPRO_CHARGEP_V`, ecc.).

In base al fatto che `AdminCodProCarriersRangeFeesController` gestisce l'entità `codprototal`, è altamente probabile che il modulo crei una tabella di database personalizzata, probabilmente denominata `ps_codprototal` (o simile, seguendo la convenzione del prefisso `ps_` di PrestaShop).
-   **`ps_codprototal` (Probabile tabella):**
    *   **Scopo:** Memorizza le regole di commissione COD basate su intervallo, collegando corrieri, totali minimi/massimi del carrello, importi/percentuali delle commissioni e regole fiscali.
    *   **Campi probabili:** `id_codprototal` (PK), `id_carrier`, `min_total`, `max_total`, `fee_type` (ad esempio, 'amount', 'percentage'), `fee_value`, `id_tax_rule`.

#### Tabella degli hook registrati

| Nome hook | Tempistica di esecuzione | Scopo tecnico |
|---|---|---|
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Per includere le risorse CSS/JS del modulo (ad esempio, `codpro-checkout.js`, `codpro.css`) nelle pagine front-office pertinenti. |
| `paymentOptions` | Durante il processo di checkout, quando vengono elencate le opzioni di pagamento. | Per iniettare l'opzione di pagamento "Contrassegno" nell'elenco. |
| `displayPaymentOptions` | (Alias o alternativa a `paymentOptions` per alcune versioni) | Per iniettare l'opzione di pagamento "Contrassegno" nell'elenco. |
| `paymentReturn` | Nella pagina di conferma dell'ordine dopo un ordine riuscito. | Per visualizzare un messaggio di conferma specifico per gli ordini COD. |
| `displayAdminOrder` | Nella pagina dei dettagli dell'ordine nel back office di PrestaShop. | Per visualizzare i dettagli della commissione COD e le informazioni sul metodo di pagamento per l'amministratore. |
| `displayOrderDetail` | Nella pagina dei dettagli dell'ordine del cliente nel front office. | Per visualizzare i dettagli della commissione COD al cliente. |
| `displayPDFInvoice` | Quando viene generata una fattura PDF. | Per garantire che la commissione COD sia correttamente inclusa e visualizzata nella fattura. |
| `ActionAdminControllerSetMedia` | Quando un controller admin viene inizializzato e le sue risorse multimediali vengono impostate. | Per includere le risorse CSS/JS specifiche dell'admin del modulo (ad esempio, `admin_codpro.css`, `adminCodProCarriersFees.js`, `adminCodProDashboard.js`). |

## 5. Supporto ufficiale e aggiornamenti
Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale degli sviluppatori, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Assicurati di utilizzare sempre la versione del modulo compatibile con la tua specifica installazione di PrestaShop.
