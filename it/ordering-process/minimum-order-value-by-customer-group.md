---
title: "Valore minimo dell'ordine per gruppo clienti - Manuale del commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Valore minimo dell'ordine per gruppo clienti' di MyPresta.eu."
sidebar:
  label: "Valore minimo dell'ordine per gruppo clienti - Manuale del commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Minimum order value by customer group su MyPresta.eu](https://mypresta.eu/modules/ordering-process/minimum-order-value-by-customer-group.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/minimum-order-value-by-customer-group/)
>
> ---


# Valore minimo dell'ordine per gruppo clienti

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale in cui definisci i valori minimi dell'ordine per ogni gruppo di clienti.

#### Impostazioni generali

-   **Escludi specifici gruppi di clienti dalla regola del valore minimo dell'ordine:**

    -   **Cosa fa questa impostazione:** Ti consente di selezionare i gruppi di clienti che *non* saranno soggetti a nessun valore minimo dell'ordine, anche se ne hai impostato uno per loro di seguito. Possono sempre effettuare il checkout indipendentemente dal totale del loro carrello.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (gruppi selezionati):* I clienti appartenenti ai gruppi selezionati bypasseranno tutti i controlli del valore minimo dell'ordine.
        -   *Quando disabilitato (nessun gruppo selezionato):* Tutti i gruppi di clienti saranno soggetti ai valori minimi dell'ordine che definisci.
    -   **Valore consigliato:** Dipende dal tuo modello di business. Se hai VIP o specifici clienti B2C che desideri esentare, selezionali qui. Altrimenti, lascia vuoto.
    -   **Scenario / esempio del commerciante:** Hai un gruppo "Clienti VIP" che desideri che possano sempre effettuare il checkout, anche se il loro ordine è piccolo. Seleziona "Clienti VIP" qui.
-   **Includi tasse nel valore minimo dell'ordine:**

    -   **Cosa fa questa impostazione:** Determina se il valore minimo dell'ordine che imposti deve includere o escludere l'importo delle tasse calcolato per i prodotti nel carrello.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* Il modulo controllerà il totale del carrello *incluse* le tasse rispetto al minimo definito.
        -   *Quando disabilitato (NO):* Il modulo controllerà il totale del carrello *escluse* le tasse rispetto al minimo definito.
    -   **Valore consigliato:** "SÌ" per la maggior parte dei negozi B2C, poiché i clienti in genere vedono e pagano il prezzo totale incluse le tasse. "NO" potrebbe essere preferito per i negozi B2B dove i prezzi sono spesso quotati IVA esclusa.
    -   **Scenario / esempio del commerciante:** Se imposti un minimo di $100 e questo è abilitato, un totale del carrello di $90 (IVA esclusa) + $10 (IVA) = $100 passerebbe. Se disabilitato, lo stesso carrello fallirebbe perché $90 è inferiore a $100.
-   **Includi costo di spedizione nel valore minimo dell'ordine:**

    -   **Cosa fa questa impostazione:** Determina se il costo di spedizione per l'ordine deve essere aggiunto al totale del carrello prima di confrontarlo con il valore minimo dell'ordine.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* Il modulo controllerà (Totale carrello + Costo di spedizione) rispetto al minimo definito.
        -   *Quando disabilitato (NO):* Il modulo controllerà solo il Totale carrello (prodotti) rispetto al minimo definito.
    -   **Valore consigliato:** "NO" nella maggior parte dei casi, poiché i minimi riguardano solitamente il valore del prodotto. Tuttavia, se i costi di spedizione sono molto elevati e desideri garantire un certo valore totale della transazione, potresti abilitare questa opzione.
    -   **Scenario / esempio del commerciante:** Desideri che i clienti acquistino prodotti per almeno $50. Se questo è "NO", un carrello di prodotti da $50 passa. Se questo è "SÌ" e la spedizione è di $10, il cliente avrebbe bisogno di $50 in prodotti + $10 di spedizione = $60 totali per passare, il che significa che avrebbe bisogno di prodotti per $60 per soddisfare il minimo di $50. Questa impostazione è solitamente "NO" per evitare confusione.
-   **Applica valore minimo dell'ordine solo per il primo ordine:**

    -   **Cosa fa questa impostazione:** Se abilitata, le regole del valore minimo dell'ordine si applicheranno solo al primissimo ordine di un cliente nel tuo negozio. Gli ordini successivi non saranno soggetti ai minimi.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* Solo i nuovi clienti (quelli che non hanno mai effettuato un ordine prima) affronteranno le restrizioni del valore minimo dell'ordine.
        -   *Quando disabilitato (NO):* Tutti gli ordini, indipendentemente dal fatto che siano il primo o il decimo di un cliente, verranno controllati rispetto al valore minimo dell'ordine.
    -   **Valore consigliato:** "NO" per la maggior parte degli scenari in cui desideri minimi coerenti. "SÌ" potrebbe essere utile per incoraggiare acquisti iniziali più grandi da nuovi clienti, quindi allentare le regole per gli affari ripetuti.
    -   **Scenario / esempio del commerciante:** Desideri che i nuovi clienti B2B effettuino un primo ordine sostanzioso di $500 per stabilire il loro account, ma dopo di ciò, possono ordinare qualsiasi importo. Abilita questa opzione e imposta il minimo di $500 per il tuo gruppo B2B.

#### Valori minimi dell'ordine per gruppo clienti

Sotto le impostazioni generali, troverai un elenco di tutti i tuoi gruppi di clienti. Per ogni gruppo, puoi definire un valore minimo dell'ordine.

-   **Nome del gruppo clienti (es. "Visitatore", "Ospite", "Cliente", "Grossista"):**
    -   **Cosa fa questa impostazione:** Qui inserisci l'importo minimo specifico dell'ordine richiesto per i clienti appartenenti a questo particolare gruppo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando viene inserito un valore (es. 50.00):* I clienti di questo gruppo devono avere un totale del carrello uguale o superiore a questo valore per procedere al checkout.
        -   *Quando lasciato vuoto o impostato su 0.00:* Non esiste un valore minimo dell'ordine per questo gruppo di clienti. Possono effettuare il checkout con qualsiasi totale del carrello.
    -   **Valore consigliato:** Imposta un valore che abbia senso per il tuo business per ogni gruppo. Lascia vuoto per gruppi come "Visitatore" o "Ospite" a meno che tu non voglia specificamente bloccarli dall'ordinare.
    -   **Scenario / esempio del commerciante:**
        -   Per il gruppo "Cliente": Imposta a `25.00` per incoraggiare acquisti al dettaglio leggermente più grandi.
        -   Per il gruppo "Grossista": Imposta a `200.00` per garantire la redditività degli ordini B2B.
        -   Per il gruppo "Ospite": Lascia vuoto (`0.00`) per consentire acquisti rapidi senza registrazione.

#### Considerazioni su Multi-Store e Multi-Valuta

-   **Multi-Store:** Se hai più negozi abilitati, vedrai un menu a discesa nella parte superiore della pagina di configurazione (solitamente accanto al pulsante "Salva") che ti consente di selezionare quale negozio stai configurando. I valori minimi dell'ordine possono essere impostati indipendentemente per ogni negozio.
-   **Multi-Valuta:** I valori minimi dell'ordine che inserisci sono sempre nella *valuta predefinita* del tuo negozio PrestaShop. Il modulo converte automaticamente questi valori nella valuta selezionata dal cliente al tasso di cambio corrente quando controlla il totale del carrello.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Escludi specifici gruppi di clienti | Vuoto | Seleziona i gruppi per bypassare le regole di ordine minimo. |
| Configurazione modulo | Includi tasse nel valore minimo dell'ordine | SÌ | Determina se le tasse fanno parte del totale minimo. |
| Configurazione modulo | Includi costo di spedizione nel valore minimo dell'ordine | NO | Determina se la spedizione fa parte del totale minimo. |
| Configurazione modulo | Applica valore minimo dell'ordine solo per il primo ordine | NO | Applica i minimi solo all'acquisto iniziale di un cliente. |
| Configurazione modulo | Valore minimo dell'ordine per [Nome gruppo clienti] | 0.00 (vuoto) | Imposta il totale del carrello richiesto per ogni gruppo di clienti. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei clienti vedono il messaggio di ordine minimo anche se il totale del loro carrello sembra corretto. Cosa c'è che non va?**
R:

1.  **Controlla le impostazioni di tasse/spedizione:** Ricontrolla se "Includi tasse nel valore minimo dell'ordine" o "Includi costo di spedizione nel valore minimo dell'ordine" sono abilitati. Il totale del carrello visualizzato potrebbe essere diverso dal valore rispetto al quale il modulo sta controllando.
2.  **Conversione valuta:** Se operi in più valute, assicurati che i tassi di cambio siano aggiornati. Il modulo converte i tuoi minimi in valuta predefinita nella valuta selezionata dal cliente.
3.  **Assegnazione gruppo clienti:** Verifica che il cliente sia correttamente assegnato al gruppo clienti che intendi e che il valore minimo per quel gruppo sia impostato come previsto.
4.  **Svuota cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti). A volte, i vecchi dati memorizzati nella cache possono causare problemi.

**D: Ho impostato un minimo, ma un gruppo di clienti specifico può ancora effettuare il checkout con qualsiasi importo. Perché?**
R: Controlla l'impostazione "Escludi specifici gruppi di clienti dalla regola del valore minimo dell'ordine" nella pagina di configurazione del modulo. Se quel gruppo di clienti è selezionato lì, bypasserà tutti i controlli di ordine minimo. Rimuovili da questo elenco di esclusione se desideri che il minimo si applichi.

**D: Il messaggio del modulo non viene visualizzato o appare strano sul mio tema personalizzato.**
R:

1.  **Compatibilità del tema:** I temi personalizzati potrebbero sovrascrivere i modelli o il CSS standard di PrestaShop, influenzando potenzialmente il modo in cui vengono visualizzati i messaggi del modulo.
2.  **Conflitti CSS:** Un altro modulo o il CSS del tuo tema potrebbero essere in conflitto con lo stile del modulo.
3.  **Cache Smarty:** Svuota la cache Smarty (Parametri avanzati > Prestazioni > Svuota cache) per assicurarti che vengano utilizzati i file di template più recenti.
    Per problemi visivi, potrebbe essere necessario consultare uno sviluppatore web per ispezionare il CSS e i file di template del tuo tema.

**D: Posso impostare minimi diversi per prodotti diversi?**
R: No, questo modulo imposta un minimo per il *valore totale del carrello* in base al gruppo di clienti, non per i singoli prodotti. Se hai bisogno di minimi specifici per prodotto, avresti bisogno di un tipo di modulo diverso.

**D: Come gestisce questo modulo le configurazioni multi-negozio?**
R: Il modulo è compatibile con il multi-negozio. Durante la configurazione, utilizza il selettore "Contesto negozio" nella parte superiore del back office di PrestaShop (solitamente accanto al pulsante "Salva") per passare da un negozio all'altro. Puoi quindi impostare valori minimi d'ordine unici per ogni gruppo di clienti, per negozio.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Valore minimo dell'ordine per gruppo clienti" (`cgma`) è costruito seguendo l'architettura standard dei moduli di PrestaShop. Utilizza principalmente gli hook per iniettare la sua logica nel processo di carrello e checkout del front-office. La configurazione è gestita tramite il metodo `getContent()` della classe principale del modulo, memorizzando le impostazioni in `ps_configuration`. L'interazione con il front-office è gestita da un controller AJAX dedicato per la convalida del carrello in tempo reale.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `cgma/controllers/front/ajax.php`
        -   **Nome classe:** `CgmaAjaxModuleFrontController` (estende `ModuleFrontController`)
        -   **Responsabilità:** Questo controller gestisce le richieste AJAX dal front-office, principalmente per la convalida in tempo reale del totale del carrello rispetto al valore minimo dell'ordine del gruppo clienti. Probabilmente restituisce una risposta JSON che indica se il carrello soddisfa i requisiti e potenzialmente un messaggio da visualizzare all'utente. Questo è cruciale per gli aggiornamenti dinamici senza ricaricamenti completi della pagina.
    -   `cgma/controllers/front/index.php`
        -   **Nome classe:** `CgmaIndexModuleFrontController` (estende `ModuleFrontController`)
        -   **Responsabilità:** Questo è un controller segnaposto o di fallback. In molti moduli, se un'azione specifica non è definita, le richieste potrebbero ricadere su un controller `index`. Potrebbe anche essere utilizzato per semplici reindirizzamenti o per garantire l'esistenza di una route di modulo valida, sebbene la sua funzione principale in questo modulo sia probabilmente minima rispetto a `ajax.php`.
-   **Controller Admin Back-Office**:

    -   Nessuno esplicitamente definito nell'inventario. Tutta la configurazione del back-office è gestita direttamente all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

-   Nessuna classe personalizzata o definizione di `ObjectModel` è esplicitamente elencata nell'inventario. Il modulo probabilmente si basa sulle classi `Customer`, `Group`, `Cart` e `Configuration` del core di PrestaShop per la sua funzionalità. I valori di configurazione sono memorizzati direttamente nella tabella `ps_configuration`.

### 4.4 Risorse JavaScript (`views/js/`)

-   `cgma/views/js/cgma.js`
    -   **Ambito:** Front-office.
    -   **Dettagli:** Questo script è responsabile dell'interazione e della convalida lato client. Probabilmente ascolta le modifiche nel carrello (ad esempio, aggiornamenti della quantità, rimozioni di prodotti) o i tentativi di procedere al checkout. Quindi attiverebbe chiamate AJAX a `cgma/controllers/front/ajax.php` per convalidare il totale del carrello rispetto al valore minimo dell'ordine. Dopo aver ricevuto una risposta, aggiornerebbe dinamicamente il riepilogo del carrello o i pulsanti di checkout, visualizzando messaggi all'utente se il minimo non è soddisfatto e potenzialmente disabilitando il pulsante "Procedi al checkout". Potrebbe anche gestire la visualizzazione del messaggio del valore minimo dell'ordine in varie posizioni del front-office.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `cgma/css.css`

    -   **Ambito:** Probabilmente front-office.
    -   **Dettagli:** Questo foglio di stile fornisce lo stile di base per i messaggi o gli elementi del front-office del modulo, come il messaggio di avviso visualizzato quando il valore minimo dell'ordine non è soddisfatto.
    -   **Selettori di classe CSS chiave:** Gli sviluppatori dovrebbero ispezionare questo file per classi come `.cgma-warning-message`, `.cgma-disabled-button` o simili, che possono essere sovrascritte in un tema personalizzato.
-   `cgma/views/css/cgma.css`

    -   **Ambito:** Probabilmente front-office.
    -   **Dettagli:** Similmente a `cgma/css.css`, questo file fornisce uno stile aggiuntivo o più specifico per i componenti del front-office del modulo. Potrebbe contenere aggiustamenti reattivi o regole di layout specifiche.
    -   **Selettori di classe CSS chiave:** Controlla i selettori relativi al riepilogo del carrello, ai pulsanti di checkout o a specifici contenitori di messaggi.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**:

    -   Nessuno esplicitamente elencato nell'inventario, ma l'implementazione dell'hook `displayShoppingCart` del modulo probabilmente renderizzerebbe un template. È possibile che `displayShoppingCart.tpl` si trovi direttamente in `views/templates/front/` e sia utilizzato dall'hook.
-   **Template admin (`views/templates/admin/`)**:

    -   `cgma/admin.tpl`
        -   **Ambito:** Configurazione del back-office.
        -   **Dettagli:** Questo template viene renderizzato dal metodo `getContent()` della classe principale del modulo (`cgma.php`). Contiene la struttura HTML per il modulo di configurazione del modulo, inclusi i campi di input per le impostazioni generali (escludi gruppi, inclusione tasse/spedizione, solo primo ordine) e campi dinamici per impostare i valori minimi dell'ordine per ogni gruppo di clienti.
-   **Template front-office (`views/templates/front/`)**:

    -   `cgma/views/templates/front/displayShoppingCart.tpl`
        -   **Ambito:** Front-office, in particolare la pagina del carrello.
        -   **Dettagli:** Questo template viene probabilmente renderizzato quando il modulo si aggancia a `displayShoppingCart`. Visualizza il messaggio di avviso al cliente se il totale del carrello non soddisfa il valore minimo dell'ordine per il suo gruppo. Potrebbe anche contenere la logica per disabilitare il pulsante "Procedi al checkout" o fornire istruzioni su come soddisfare il minimo.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non crea tabelle SQL personalizzate.
    -   Le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` utilizzando chiavi come `CGMA_EXCV`, `CGMA_TAX`, `CGMA_FREE`, `CGMA_FIRST_ORDER` e `CGMA_[GROUP_ID]_[CURRENCY_ID]` per i valori minimi per gruppo e valuta. Viene anche fatto riferimento a `PS_CURRENCY_DEFAULT`.
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `stepBeforePaymentOPC` | Prima del passaggio di pagamento nel Checkout in una pagina. | Impedisce ai clienti di procedere al pagamento se il valore minimo dell'ordine non è soddisfatto. |
| `displayPaymentTop` | Nella parte superiore della sezione delle opzioni di pagamento durante il checkout. | Visualizza un messaggio di avviso se il valore minimo dell'ordine non è soddisfatto. |
| `displaystepBeforePaymentOPC` | Simile a `stepBeforePaymentOPC`, spesso utilizzato per visualizzare contenuti o controlli aggiuntivi. | Assicura che il valore minimo dell'ordine sia soddisfatto prima del pagamento, potenzialmente visualizzando un messaggio. |
| `displayShoppingCart` | Nella pagina di riepilogo del carrello. | Convalida il totale del carrello e visualizza un messaggio di avviso se il minimo non è soddisfatto, potenzialmente disabilitando i pulsanti di checkout. |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Inietta i file CSS (`cgma.css`) e JavaScript (`cgma.js`) necessari per la funzionalità e lo stile del front-office. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e per accedere alle ultime versioni del modulo "Valore minimo dell'ordine per gruppo clienti", visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere.
