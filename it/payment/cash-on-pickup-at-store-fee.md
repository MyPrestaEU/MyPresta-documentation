---
title: "Contanti al ritiro in negozio (+commissione) - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Contanti al ritiro in negozio (+commissione) di MyPresta.eu."
sidebar:
  label: "Contanti al ritiro in negozio (+commissione) - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Cash on pickup at store (+fee) su MyPresta.eu](https://mypresta.eu/modules/payment-process/cash-on-pickup-at-store-fee.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/payment/cash-on-pickup-at-store-fee/)
>
> ---


# Contanti al ritiro in negozio (+commissione)

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste e di solito sono abilitate per impostazione predefinita sulla maggior parte degli ambienti di hosting.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale dove imposterai tutte le opzioni per il tuo metodo di pagamento "Contanti al ritiro in negozio".

#### **Impostazioni generali**

- **Logo del pagamento**

  - **Cosa fa questa impostazione:** Ti permette di caricare un'immagine personalizzata (logo) che verrà visualizzata accanto all'opzione di pagamento "Contanti al ritiro in negozio" durante il checkout. Questo aiuta i clienti a identificare visivamente il metodo di pagamento.
  - **Effetto della modifica di questa impostazione:**
    - *Quando viene caricata un'immagine:* L'immagine scelta apparirà accanto al nome del metodo di pagamento nella pagina di selezione del pagamento.
    - *Quando non viene caricata alcuna immagine:* Verrà visualizzato un logo predefinito o nessun logo, a seconda del tuo tema.
  - **Valore consigliato:** Carica un logo chiaro e piccolo che rappresenti "ritiro" o "contanti" per un migliore riconoscimento.
  - **Scenario / esempio del commerciante:** Potresti caricare un'icona di una borsa della spesa o di una vetrina per far risaltare l'opzione di pagamento.
- **Titolo del metodo di pagamento** (Chiave di configurazione: `COPPRO_TITLE`)

  - **Cosa fa questa impostazione:** Definisce il nome del metodo di pagamento così come appare ai clienti durante il checkout.
  - **Effetto della modifica di questa impostazione:**
    - *Quando modificato:* Il nuovo titolo verrà visualizzato nella pagina di selezione del pagamento, nella conferma dell'ordine e nelle fatture.
  - **Valore consigliato:** "Contanti al ritiro in negozio" o "Paga al ritiro in negozio".
  - **Scenario / esempio del commerciante:** Se hai un nome di marca specifico per il tuo servizio di ritiro, puoi usarlo qui, ad esempio, "Ritiro locale MyStore".
- **Stato dell'ordine per i nuovi ordini** (Chiave di configurazione: `COPPRO_OS`)

  - **Cosa fa questa impostazione:** Seleziona lo stato iniziale che un ordine avrà nel tuo Back Office quando un cliente sceglie "Contanti al ritiro in negozio".
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su "In attesa di contanti al ritiro":* I nuovi ordini verranno automaticamente assegnati a questo stato, rendendo facile per te identificare gli ordini che devono essere preparati per il ritiro e il pagamento.
  - **Valore consigliato:** Crea uno stato d'ordine personalizzato come "In attesa di contanti al ritiro" o "Pronto per il ritiro" per chiarezza.
  - **Scenario / esempio del commerciante:** Potresti impostarlo su "In attesa di contanti al ritiro" in modo che il tuo personale sappia di preparare gli articoli ma di non spedirli.
- **Stato dell'ordine quando pagato** (Chiave di configurazione: `COPPRO_OS_READY`)

  - **Cosa fa questa impostazione:** Seleziona lo stato dell'ordine a cui un ordine dovrebbe essere modificato una volta che il cliente ha pagato e ritirato con successo i suoi articoli nel tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su "Pagamento accettato":* Una volta che aggiorni manualmente l'ordine nel Back Office dopo il ritiro e il pagamento, passerà a questo stato, contrassegnandolo come completato.
  - **Valore consigliato:** "Pagamento accettato" o "Consegnato".
  - **Scenario / esempio del commerciante:** Dopo che il cliente ritira e paga, cambieresti lo stato dell'ordine in "Pagamento accettato" per finalizzare la transazione nel tuo sistema.

#### **Restrizioni sul valore del carrello**

- **Valore minimo totale del carrello** (Chiave di configurazione: `COPPRO_MINCART`, `COPPRO_MINCART_V`)

  - **Cosa fa questa impostazione:** Ti permette di impostare un valore totale minimo per un ordine per essere idoneo a "Contanti al ritiro in negozio". Se il totale del carrello è inferiore a questo valore, il metodo di pagamento non verrà mostrato.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su un valore (es. 10 €):* I clienti con un totale del carrello inferiore a 10 € non vedranno "Contanti al ritiro in negozio" come opzione.
    - *Quando lasciato vuoto o 0:* Non ci sarà alcuna restrizione sul valore minimo del carrello.
  - **Valore consigliato:** Lasciare vuoto o 0 a meno che tu non abbia ragioni operative specifiche per richiedere un minimo.
  - **Scenario / esempio del commerciante:** Potresti impostare un minimo di 5 € per evitare ordini molto piccoli che non sono convenienti per il tuo personale da elaborare per il ritiro.
- **Valore massimo totale del carrello** (Chiave di configurazione: `COPPRO_MAXCART`, `COPPRO_MAXCART_V`)

  - **Cosa fa questa impostazione:** Ti permette di impostare un valore totale massimo per un ordine per essere idoneo a "Contanti al ritiro in negozio". Se il totale del carrello supera questo valore, il metodo di pagamento non verrà mostrato.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su un valore (es. 500 €):* I clienti con un totale del carrello superiore a 500 € non vedranno "Contanti al ritiro in negozio" come opzione.
    - *Quando lasciato vuoto o 0:* Non ci sarà alcuna restrizione sul valore massimo del carrello.
  - **Valore consigliato:** Lasciare vuoto o 0 a meno che tu non abbia preoccupazioni specifiche sulla gestione di pagamenti in contanti molto grandi.
  - **Scenario / esempio del commerciante:** Potresti impostare un massimo di 1000 € se non ti senti a tuo agio con il personale che gestisce somme di denaro molto grandi al punto di ritiro.

#### **Configurazione commissione / sconto**

- **Applica sconto (non commissione)** (Chiave di configurazione: `COPPRO_DISCOUNT`)

  - **Cosa fa questa impostazione:** Questo è un interruttore. Se abilitato, il modulo applicherà uno *sconto* al totale dell'ordine invece di una *commissione* quando viene selezionato "Contanti al ritiro in negozio".
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il valore impostato per "Valore percentuale di addebito" o "Valore fisso di addebito" verrà sottratto dal totale dell'ordine.
    - *Quando disabilitato:* Il valore impostato verrà aggiunto al totale dell'ordine come commissione.
  - **Valore consigliato:** Disabilitato (per applicare una commissione) se vuoi coprire i costi operativi, o Abilitato (per applicare uno sconto) se vuoi incentivare i ritiri.
  - **Scenario / esempio del commerciante:** Potresti abilitare questa opzione e impostare uno sconto del 5% per incoraggiare i clienti a ritirare i loro ordini, risparmiando sui costi di spedizione.
- **Valore della commissione vicino al metodo di pagamento** (Chiave di configurazione: `COPPRO_FEEPAY`)

  - **Cosa fa questa impostazione:** Questo è un interruttore. Se abilitato, l'importo della commissione o dello sconto verrà visualizzato direttamente accanto al nome del metodo di pagamento nella pagina di checkout.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I clienti vedranno "Contanti al ritiro in negozio (+ X,XX € di commissione)" o "Contanti al ritiro in negozio (- X,XX € di sconto)".
    - *Quando disabilitato:* Verrà mostrato solo il nome del metodo di pagamento, e la commissione/sconto verrà applicata al totale del carrello senza menzione esplicita accanto al metodo.
  - **Valore consigliato:** Abilitato, per trasparenza con i tuoi clienti.
  - **Scenario / esempio del commerciante:** Vuoi che i clienti siano pienamente consapevoli di eventuali costi aggiuntivi o risparmi in anticipo, quindi abiliti questa opzione.
- **Addebito percentuale** (Chiave di configurazione: `COPPRO_CHARGEP`, `COPPRO_CHARGEP_V`)

  - **Cosa fa questa impostazione:** Ti permette di applicare una commissione o uno sconto basato su una percentuale del totale dell'ordine.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato e viene inserito un valore (es. 5):* Una commissione del 5% (o uno sconto se "Applica sconto" è abilitato) verrà aggiunta/sottratta dal totale dell'ordine.
    - *Quando disabilitato:* Non verrà applicata alcuna commissione/sconto basato su percentuale.
  - **Valore consigliato:** Disabilitato, a meno che tu non voglia specificamente un addebito basato su percentuale. Se abilitato, un valore tra l'1-10% è comune per le commissioni, o 2-10% per gli sconti.
  - **Scenario / esempio del commerciante:** Vuoi addebitare una commissione del 3% per coprire il costo di elaborazione del contante e della gestione, quindi abiliti questa opzione e inserisci "3".
- **Addebito fisso** (Chiave di configurazione: `COPPRO_CHARGEA`, `COPPRO_CHARGEA_V`)

  - **Cosa fa questa impostazione:** Ti permette di applicare una commissione o uno sconto di importo fisso al totale dell'ordine.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato e viene inserito un valore (es. 2.50):* Una commissione fissa di 2,50 € (o uno sconto se "Applica sconto" è abilitato) verrà aggiunta/sottratta dal totale dell'ordine.
    - *Quando disabilitato:* Non verrà applicata alcuna commissione/sconto di importo fisso.
  - **Valore consigliato:** Abilitato, con un piccolo importo fisso (es. 1,00 € - 3,00 €) se desideri una commissione semplice e coerente.
  - **Scenario / esempio del commerciante:** Vuoi addebitare una commissione fissa di 2 € per tutti gli ordini di ritiro, quindi abiliti questa opzione e inserisci "2.00".

#### **Impostazioni avanzate di visualizzazione e compatibilità**

- **Riepilogo carrello** (Chiave di configurazione: `COPPRO_CARTPRESENTER`)

  - **Cosa fa questa impostazione:** Questo è un interruttore che controlla se la commissione/sconto viene esplicitamente mostrato nel blocco di riepilogo del carrello (ad esempio, nella colonna di destra o in fondo alla pagina del carrello).
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* La commissione/sconto verrà dettagliata nel riepilogo del carrello, mostrando come influisce sul totale.
    - *Quando disabilitato:* La commissione/sconto verrà applicata al totale ma potrebbe non essere esplicitamente dettagliata nel riepilogo del carrello prima del passaggio di pagamento.
  - **Valore consigliato:** Abilitato, per la massima trasparenza.
  - **Scenario / esempio del commerciante:** Vuoi che i clienti vedano la voce "Commissione di ritiro" nel riepilogo del loro carrello prima ancora di raggiungere il passaggio di pagamento, quindi abiliti questa opzione.
- **Riepilogo indirizzo** (Chiave di configurazione: `COPPRO_HOWFEE`)

  - **Cosa fa questa impostazione:** Questa impostazione controlla dove la commissione/sconto viene visualizzata nella sezione di riepilogo dell'indirizzo del checkout.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* La commissione/sconto sarà visibile nel riepilogo dell'indirizzo, di solito vicino al costo di spedizione.
    - *Quando disabilitato:* La commissione/sconto verrà applicata ma non esplicitamente mostrata nel riepilogo dell'indirizzo.
  - **Valore consigliato:** Abilitato, per coerenza e trasparenza.
  - **Scenario / esempio del commerciante:** Vuoi che la commissione sia visibile in più fasi del checkout, incluso il riepilogo dell'indirizzo, quindi abiliti questa opzione.
- **Abilitato** (Chiave di configurazione: `COPPRO_EVENTLISTENER`)

  - **Cosa fa questa impostazione:** Questo è un interruttore generale per abilitare o disabilitare la funzionalità principale del modulo.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il metodo di pagamento "Contanti al ritiro in negozio" sarà attivo e disponibile per i clienti.
    - *Quando disabilitato:* Il metodo di pagamento sarà nascosto e non disponibile.
  - **Valore consigliato:** Abilitato, una volta configurate tutte le altre impostazioni.
  - **Scenario / esempio del commerciante:** Hai finito di configurare il modulo e sei pronto a offrire questo metodo di pagamento, quindi lo abiliti.
- **Disabilitato** (Chiave di configurazione: `PS_ONE_PAGE_CHECKOUT_ENABLED`)

  - **Cosa fa questa impostazione:** Questa impostazione è probabilmente correlata alla compatibilità con il checkout a una pagina di PrestaShop. Potrebbe essere un'impostazione legacy o un indicatore di visualizzazione.
  - **Effetto della modifica di questa impostazione:** Questo è probabilmente un indicatore di sola lettura o un'impostazione che dovrebbe generalmente essere lasciata al suo valore predefinito a meno che non sia diversamente indicato dal supporto.
  - **Valore consigliato:** Lasciare come predefinito.
  - **Scenario / esempio del commerciante:** Nessuna interazione diretta del commerciante prevista.
- **Selettori CSS per gli elementi del carrello** (Chiavi di configurazione: `COPPRO_CSS_CART_TOTAL`, `COPPRO_CSS_CART_SUBTOTAL`, `COPPRO_CSS_CART_SHIPPING`)

  - **Cosa fanno queste impostazioni:** Questi campi ti permettono di specificare i selettori CSS per gli elementi del totale del carrello, del subtotale e del costo di spedizione del tuo tema. Questo è cruciale affinché il modulo aggiorni correttamente questi valori quando viene applicata una commissione/sconto, specialmente se il tuo tema utilizza selettori non standard.
  - **Effetto della modifica di questa impostazione:**
    - *Quando configurato correttamente:* Il modulo aggiornerà accuratamente i totali del carrello, i subtotali e i costi di spedizione visualizzati nella pagina di checkout per riflettere la commissione/sconto.
    - *Quando configurato in modo errato o lasciato vuoto:* I totali del carrello potrebbero non aggiornarsi correttamente, portando a confusione del cliente o a prezzi visualizzati errati.
  - **Valore consigliato:** Lasciare vuoto inizialmente. Se noti che i totali del carrello non si aggiornano correttamente dopo aver selezionato "Contanti al ritiro in negozio", potresti dover consultare lo sviluppatore del tuo tema o un webmaster per trovare i selettori CSS corretti.
  - **Scenario / esempio del commerciante:** Dopo aver installato il modulo, noti che il prezzo totale non cambia nella pagina di checkout quando viene applicata la commissione di ritiro. Il tuo webmaster ispezionerebbe il codice del tuo tema per trovare i selettori CSS corretti (es. `#cart-total-price`, `.product-total-price`) e li inserirebbe qui.

#### **Regole di esclusione**

- **Escludi prodotti** (Chiave di configurazione: `COPPRO_EXCL_PRODUCTS`)

  - **Cosa fa questa impostazione:** Ti permette di impedire che prodotti specifici vengano acquistati con il metodo di pagamento "Contanti al ritiro in negozio". Se un prodotto escluso è nel carrello, questo metodo di pagamento non sarà disponibile.
  - **Effetto della modifica di questa impostazione:**
    - *Quando i prodotti sono selezionati:* Se un cliente aggiunge uno di questi prodotti al carrello, l'opzione "Contanti al ritiro in negozio" scomparirà dai metodi di pagamento.
    - *Quando nessun prodotto è selezionato:* Tutti i prodotti sono idonei.
  - **Valore consigliato:** Lasciare vuoto a meno che tu non abbia prodotti specifici che non possono essere ritirati o pagati in contanti.
  - **Scenario / esempio del commerciante:** Vendi articoli di altissimo valore (es. gioielli costosi) per i quali preferisci accettare solo pagamenti online sicuri. Aggiungeresti questi prodotti all'elenco di esclusione.
- **Escludi categorie** (Chiave di configurazione: `COPPRO_EXCL_CAT`)

  - **Cosa fa questa impostazione:** Simile all'esclusione di prodotti, questo ti permette di impedire che intere categorie di prodotti vengano acquistate con "Contanti al ritiro in negozio".
  - **Effetto della modifica di questa impostazione:**
    - *Quando le categorie sono selezionate:* Se un cliente aggiunge un prodotto da queste categorie al carrello, l'opzione "Contanti al ritiro in negozio" non sarà disponibile.
    - *Quando nessuna categoria è selezionata:* Tutte le categorie sono idonee.
  - **Valore consigliato:** Lasciare vuoto a meno che tu non abbia categorie specifiche che non sono adatte per il ritiro.
  - **Scenario / esempio del commerciante:** Hai una categoria "Download digitali". Poiché questi articoli non richiedono il ritiro fisico, escluderesti questa categoria.
- **Abilita esclusioni** (Chiave di configurazione: `COPPRO_EXCL_ENABLE`)

  - **Cosa fa questa impostazione:** Questo è un interruttore principale per abilitare o disabilitare tutte le regole di esclusione di prodotti e categorie che hai impostato.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Le tue regole di esclusione di prodotti e categorie saranno attive.
    - *Quando disabilitato:* Tutti i prodotti e le categorie saranno idonei per "Contanti al ritiro in negozio", indipendentemente da ciò che hai selezionato negli elenchi di esclusione.
  - **Valore consigliato:** Abilitato, se hai definito delle regole di esclusione.
  - **Scenario / esempio del commerciante:** Hai impostato esclusioni per determinati prodotti e vuoi che queste regole siano attive, quindi abiliti questo interruttore.

#### **Impostazioni di analisi e interne**

- **Impostazioni di analisi** (Chiavi di configurazione: `COPPRO_ANALYTICS_DEFAULT_CHART`, `COPPRO_ANALYTICS_PERIOD`, `COPPRO_ANALYTICS_IMPACT_DAYS`, `COPPRO_ANALYTICS_CHART_WEEKS`, `COPPRO_ANALYTICS_CHART_MONTHS`, `COPPRO_ANALYTICS_CHART_YEARS`)

  - **Cosa fanno queste impostazioni:** Queste sono impostazioni interne relative a eventuali funzionalità di analisi o reporting che il modulo potrebbe avere, consentendoti di configurare come i dati vengono raccolti o visualizzati per uso interno.
  - **Effetto della modifica di questa impostazione:** Queste di solito influenzano solo le visualizzazioni di reporting del Back Office, non l'esperienza del cliente nel front-office.
  - **Valore consigliato:** Lasciare come predefinito a meno che tu non abbia esigenze di reporting specifiche.
  - **Scenario / esempio del commerciante:** Nessuna interazione diretta del commerciante prevista per le operazioni quotidiane.
- **Data/snapshot modifica commissione** (Chiavi di configurazione: `COPPRO_FEE_CHANGE_DATE`, `COPPRO_FEE_CHANGE_SNAPSHOT`)

  - **Cosa fanno queste impostazioni:** Queste sono probabilmente impostazioni interne del modulo per tenere traccia di quando le configurazioni delle commissioni sono state modificate l'ultima volta o per memorizzare uno snapshot delle impostazioni precedenti delle commissioni. Questo è solitamente a scopo di audit o debug.
  - **Effetto della modifica di questa impostazione:** Nessun impatto diretto sull'esperienza del cliente.
  - **Valore consigliato:** Lasciare come predefinito.
  - **Scenario / esempio del commerciante:** Nessuna interazione diretta del commerciante prevista.

### 2.2 Schermate di amministrazione dedicate e viste del controller

Questo modulo non sembra avere controller di amministrazione personalizzati dedicati oltre alla sua pagina di configurazione principale. Tutte le impostazioni sono gestite tramite il metodo `getContent()` del file principale del modulo.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Logo del pagamento | Carica immagine pertinente | Identificazione visiva del metodo di pagamento. |
| Configurazione modulo | Titolo del metodo di pagamento | "Contanti al ritiro in negozio" | Nome visualizzato ai clienti per l'opzione di pagamento. |
| Configurazione modulo | Stato dell'ordine per i nuovi ordini | Personalizzato "In attesa di contanti al ritiro" | Stato iniziale per gli ordini che utilizzano questo metodo. |
| Configurazione modulo | Stato dell'ordine quando pagato | "Pagamento accettato" / "Consegnato" | Stato finale dopo che il cliente paga e ritira. |
| Configurazione modulo | Valore minimo totale del carrello | Vuoto / 0 | Valore minimo dell'ordine affinché questo metodo di pagamento appaia. |
| Configurazione modulo | Valore massimo totale del carrello | Vuoto / 0 | Valore massimo dell'ordine affinché questo metodo di pagamento appaia. |
| Configurazione modulo | Applica sconto (non commissione) | Disabilitato | Determina se viene applicato uno sconto o una commissione. |
| Configurazione modulo | Valore della commissione vicino al metodo di pagamento | Abilitato | Visualizza commissione/sconto accanto al nome del metodo di pagamento. |
| Configurazione modulo | Addebito percentuale | Disabilitato | Applica una commissione/sconto basato su percentuale. |
| Configurazione modulo | Valore addebito percentuale | 0 | Il valore percentuale per l'addebito/sconto. |
| Configurazione modulo | Addebito fisso | Abilitato (con valore) | Applica una commissione/sconto di importo fisso. |
| Configurazione modulo | Valore addebito fisso | es. 2.00 | L'importo fisso per l'addebito/sconto. |
| Configurazione modulo | Riepilogo carrello | Abilitato | Mostra commissione/sconto dettagliato nel riepilogo del carrello. |
| Configurazione modulo | Riepilogo indirizzo | Abilitato | Mostra commissione/sconto nel riepilogo dell'indirizzo. |
| Configurazione modulo | Abilitato | Abilitato | Attiva/disattiva il metodo di pagamento. |
| Configurazione modulo | Escludi prodotti | Vuoto | Impedisce a prodotti specifici di utilizzare questo metodo. |
| Configurazione modulo | Escludi categorie | Vuoto | Impedisce ai prodotti di categorie specifiche di utilizzare questo metodo. |
| Configurazione modulo | Abilita esclusioni | Abilitato (se le regole sono impostate) | Interruttore principale per le regole di esclusione di prodotti/categorie. |
| Configurazione modulo | Selettori CSS (Totale carrello, Subtotale, Spedizione) | Vuoto (regolare se necessario) | Assicura aggiornamenti corretti del totale del carrello con il tema. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Il metodo di pagamento "Contanti al ritiro in negozio" non viene visualizzato durante il checkout.**
R:

- **Controlla l'impostazione "Abilitato":** Vai su Moduli > Gestione moduli > Configura per "Contanti al ritiro in negozio (+commissione)" e assicurati che l'interruttore principale "Abilitato" sia su ON.
- **Controlla le restrizioni sul valore del carrello:** Verifica le impostazioni "Valore minimo totale del carrello" e "Valore massimo totale del carrello". Se il totale del carrello del cliente rientra al di fuori di questo intervallo, il metodo non apparirà.
- **Controlla le esclusioni:** Se hai impostato esclusioni di prodotti o categorie, assicurati che il carrello attuale non contenga articoli esclusi. Inoltre, controlla se "Abilita esclusioni" è su ON.
- **Controlla le restrizioni geografiche:** Assicurati che il metodo di pagamento non sia limitato per paese o valuta nelle impostazioni generali di pagamento di PrestaShop (Pagamento > Preferenze).
- **Svuota la cache:** A volte, la cache di PrestaShop può impedire che le modifiche appaiano immediatamente. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache".

**D2: La commissione/sconto non viene applicata o visualizzata correttamente nella pagina di checkout.**
R:

- **Verifica le impostazioni di commissione/sconto:** Ricontrolla che "Addebito percentuale" o "Addebito fisso" sia abilitato e che il valore corrispondente sia inserito correttamente. Inoltre, assicurati che "Applica sconto (non commissione)" sia impostato come desiderato.
- **Controlla le impostazioni di visualizzazione:** Assicurati che "Valore della commissione vicino al metodo di pagamento", "Riepilogo carrello" e "Riepilogo indirizzo" siano tutti abilitati per la massima visibilità.
- **Selettori CSS (Avanzato):** Se il tuo tema è fortemente personalizzato, il modulo potrebbe non essere in grado di trovare gli elementi corretti da aggiornare. Controlla le impostazioni "Selettori CSS per gli elementi del carrello". Potrebbe essere necessario un webmaster per identificare i selettori corretti per il totale del carrello, il subtotale e gli elementi di spedizione del tuo tema.

**D3: Come posso cambiare il testo "Contanti al ritiro in negozio" in qualcos'altro?**
R:

- Puoi cambiare il nome visualizzato direttamente nella configurazione del modulo. Cerca l'impostazione "Titolo del metodo di pagamento" nella pagina di configurazione principale.
- Per i negozi multilingue, assicurati di selezionare la lingua corretta dal menu a discesa nella parte superiore della pagina di configurazione del modulo (se disponibile) o usa lo strumento di traduzione di PrestaShop (Internazionale > Traduzioni > Traduzioni dei moduli installati).

**D4: Posso limitare questo metodo di pagamento solo a determinati corrieri o gruppi di clienti?**
R:

- **Corrieri:** Sì, le preferenze di pagamento principali di PrestaShop ti consentono di limitare i metodi di pagamento per corriere. Vai su **Pagamento > Preferenze** nel tuo Back Office. Nella sezione "Restrizioni corriere", assicurati che "Contanti al ritiro in negozio (+commissione)" sia selezionato per i corrieri con cui desideri consentirlo (ad esempio, il tuo corriere "Ritiro locale").
- **Gruppi di clienti:** Allo stesso modo, in **Pagamento > Preferenze**, puoi limitare i metodi di pagamento per gruppo di clienti. Assicurati che i gruppi di clienti pertinenti (ad esempio, "Cliente", "Visitatore") siano selezionati per questo metodo di pagamento.

**D5: Quale stato dell'ordine dovrei usare per gli ordini "Contanti al ritiro"?**
R:

- Si consiglia vivamente di creare uno stato dell'ordine personalizzato in PrestaShop (Ordini > Stati degli ordini) specificamente per gli ordini "Contanti al ritiro", come "In attesa di contanti al ritiro" o "Pronto per il ritiro". Questo ti aiuta a identificare facilmente questi ordini nel tuo Back Office.
- Quindi, nella configurazione del modulo, imposta "Stato dell'ordine per i nuovi ordini" su questo stato personalizzato.
- Una volta che il cliente ha pagato e ritirato, cambia manualmente lo stato dell'ordine in "Pagamento accettato" o "Consegnato" nella pagina dei dettagli dell'ordine.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo `Contanti al ritiro in negozio (+commissione)` (`coppro`) è un modulo di pagamento PrestaShop standard che segue il modello MVC. Estende `PaymentModule` e si integra principalmente tramite hook per visualizzare le opzioni di pagamento, elaborare la convalida e visualizzare le informazioni sull'ordine. Il modulo calcola dinamicamente commissioni/sconti in base alla configurazione e aggiorna i totali del carrello tramite JavaScript nel checkout del front-office. Utilizza `Configuration` per l'archiviazione delle impostazioni e non introduce classi `ObjectModel` personalizzate o tabelle di database.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**:

  - `controllers/front/index.php`
    - Nome classe: `CopproIndexModuleFrontController` (probabilmente estende `ModuleFrontController`)
    - Responsabilità: Questo controller potrebbe fungere da punto di ingresso predefinito o gestire richieste generiche del front-office relative al modulo che non rientrano in flussi di pagamento specifici. Dato il suo nome, potrebbe essere un fallback o un semplice controller di visualizzazione.
  - `controllers/front/store.php`
    - Nome classe: `CopproStoreModuleFrontController` (probabilmente estende `ModuleFrontController`)
    - Responsabilità: Potenzialmente gestisce la logica relativa alle posizioni dei negozi o ai punti di ritiro, sebbene la descrizione del modulo non menzioni esplicitamente più posizioni di negozi. Potrebbe essere un segnaposto o per future espansioni.
  - `controllers/front/validation.php`
    - Nome classe: `CopproValidationModuleFrontController` (probabilmente estende `ModuleFrontController`)
    - Responsabilità: Questo è il controller critico per l'elaborazione dei pagamenti. Riceve la conferma del pagamento dal processo di checkout, convalida l'ordine e reindirizza il cliente alla pagina di conferma dell'ordine. Interagisce con il modulo principale `coppro.php` per finalizzare l'ordine con lo stato corretto e le commissioni/sconti applicati.
- **Controller di amministrazione Back-Office**:

  - Questo modulo non include alcun controller di amministrazione personalizzato. Tutta la configurazione del Back Office è gestita direttamente all'interno del metodo `getContent()` del file principale del modulo `coppro.php`.

### 4.3 Classi e modelli principali (`classes/`)

Il modulo non sembra definire alcuna classe personalizzata all'interno di una directory `classes/`. La sua logica principale risiede all'interno del file principale del modulo `coppro.php`, che estende `PaymentModule`.

### 4.4 Risorse JavaScript (`views/js/`)

- `coppro/lib/searchTool/views/js/autocomplete.js`
  - Scopo: Probabilmente Back-office.
  - Responsabilità: Fornisce la funzionalità di completamento automatico, probabilmente per la selezione di prodotti o categorie nella configurazione del modulo (ad esempio, per gli elenchi di esclusione). Si lega ai campi di input ed esegue richieste AJAX per recuperare i suggerimenti.
- `coppro/views/js/adminCopproDashboard.js`
  - Scopo: Back-office.
  - Responsabilità: Gestisce JavaScript per eventuali funzionalità di dashboard amministrativa o di analisi all'interno della pagina di configurazione del modulo. Potrebbe gestire il rendering di grafici o la visualizzazione dei dati.
- `coppro/views/js/adminCopproProductSearch.js`
  - Scopo: Back-office.
  - Responsabilità: Gestisce specificamente l'interfaccia di ricerca prodotti all'interno della configurazione amministrativa del modulo, probabilmente per l'impostazione "Escludi prodotti". Gestisce l'input di ricerca, la visualizzazione dei risultati e la selezione.
- `coppro/views/js/adminCopproSelector.js`
  - Scopo: Back-office.
  - Responsabilità: Gestisce la logica di selezione per vari elementi nel pannello di amministrazione, possibilmente per categorie o altri elenchi configurabili.
- `coppro/views/js/coppro-checkout.js`
  - Scopo: Front-office.
  - Responsabilità: Questo è lo script principale del front-office. Ascolta i cambiamenti nella selezione del metodo di pagamento durante il checkout. Quando viene scelto "Contanti al ritiro in negozio", aggiorna dinamicamente il riepilogo del carrello (totale, subtotale, spedizione) per riflettere la commissione o lo sconto calcolato. Utilizza i selettori CSS definiti nella configurazione del modulo (`COPPRO_CSS_CART_TOTAL`, ecc.) per mirare e modificare gli elementi DOM. Potrebbe anche gestire chiamate AJAX per ricalcolare i totali se è necessario il backend.
- `coppro/views/js/copproBoMockConsole.js`
  - Scopo: Back-office.
  - Responsabilità: Probabilmente un'utilità di debug o sviluppo, possibilmente per simulare l'output della console o la registrazione all'interno del Back Office.

### 4.5 Fogli di stile CSS (`views/css/`)

- `coppro/lib/searchTool/views/css/autocomplete.css`
  - Scopo: Back-office.
  - Responsabilità: Stila i menu a discesa di completamento automatico e i campi di input di ricerca utilizzati nella configurazione amministrativa.
- `coppro/views/css/admin_coppro.css`
  - Scopo: Styling del modulo di amministrazione del Back-office.
  - Responsabilità: Fornisce uno styling specifico per la pagina di configurazione del modulo nel Back Office di PrestaShop, garantendo un'interfaccia coerente e facile da usare.
- `coppro/views/css/coppro.css`
  - Scopo: Styling del cliente del Front-office.
  - Responsabilità: Contiene stili per la visualizzazione dell'opzione di pagamento "Contanti al ritiro in negozio", potenzialmente per il logo del pagamento, il testo della commissione/sconto o qualsiasi elemento personalizzato introdotto dal modulo nella pagina di checkout. Gli sviluppatori possono sovrascrivere questi stili nel `custom.css` del loro tema o nel tema figlio.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template hook (`views/templates/hook/`)**:

  - `coppro/views/templates/hook/confirmation.tpl`
    - Hook: Probabilmente `displayPaymentReturn` o simile.
    - Output: Contenuto per la pagina di conferma dell'ordine dopo un ordine "Contanti al ritiro" riuscito, che informa il cliente sul pagamento al momento del ritiro.
  - `coppro/views/templates/hook/displayAdminOrder16.tpl`
    - Hook: `displayAdminOrder` (per PrestaShop 1.6.x).
    - Output: Informazioni aggiuntive o azioni relative agli ordini "Contanti al ritiro" all'interno della pagina dei dettagli dell'ordine del Back Office per PS 1.6.
  - `coppro/views/templates/hook/displayAdminOrder17.tpl`
    - Hook: `displayAdminOrder` (per PrestaShop 1.7.x, 8.x, 9.x).
    - Output: Simile a `displayAdminOrder16.tpl` ma adattato per la pagina dei dettagli dell'ordine del Back Office di PS 1.7+, potenzialmente mostrando istruzioni di ritiro o dettagli sulle commissioni.
  - `coppro/views/templates/hook/displayOrderDetail.tpl`
    - Hook: `displayOrderDetail`.
    - Output: Informazioni sul metodo di pagamento "Contanti al ritiro in negozio" all'interno della pagina dei dettagli dell'ordine del front-office del cliente.
  - `coppro/views/templates/hook/payment.tpl`
    - Hook: `paymentOptions` (o `displayPaymentOptions`).
    - Output: La struttura HTML per l'opzione di pagamento "Contanti al ritiro in negozio" nella pagina di checkout, inclusi il logo del pagamento, il titolo e il testo della commissione/sconto calcolato dinamicamente.
- **Template di amministrazione (`views/templates/admin/`)**:

  - `coppro/lib/searchTool/views/scripts.tpl`
    - Hook: Probabilmente `actionAdminControllerSetMedia` o incluso direttamente in `getContent()`.
    - Output: Include risorse JavaScript e CSS per lo strumento di ricerca utilizzato nella configurazione amministrativa.
  - `coppro/views/templates/admin/productSearchTool.tpl`
    - Output: La struttura HTML per l'interfaccia di ricerca e selezione prodotti all'interno della configurazione del modulo, utilizzata per l'impostazione "Escludi prodotti".
  - `coppro/views/templates/admin/scopeSelector.tpl`
    - Output: HTML per un selettore di ambito generico, potenzialmente utilizzato per categorie o altri elenchi filtrabili nella configurazione amministrativa.
- **Template front-office (`views/templates/front/`)**:

  - `coppro/views/templates/front/validation.tpl`
    - Output: Contenuto visualizzato da `CopproValidationModuleFrontController` dopo la convalida del pagamento, tipicamente un reindirizzamento o un semplice messaggio prima della pagina di conferma finale.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:
  Il modulo non crea tabelle di database personalizzate. Tutte le sue impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` utilizzando i metodi `Configuration::updateValue()` e `Configuration::get()`, con chiavi prefissate da `COPPRO_`.
  Esempio di chiavi di configurazione:

  - `COPPRO_OS`
  - `COPPRO_OS_READY`
  - `COPPRO_MAXCART_V`
  - `COPPRO_MINCART_V`
  - `COPPRO_FEEPAY`
  - `COPPRO_DISCOUNT`
  - `COPPRO_CHARGEP_V`
  - `COPPRO_CHARGEA_V`
  - `COPPRO_EXCL_PRODUCTS`
  - `COPPRO_EXCL_CAT`
  - `COPPRO_TITLE`
  - `COPPRO_CARTPRESENTER`
  - `COPPRO_HOWFEE`
- **Tabella degli hook registrati**:

| Nome dell'hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Per includere risorse CSS (`coppro.css`) e JavaScript (`coppro-checkout.js`) del front-office. |
| `displayPaymentOptions` | Durante il checkout, per elencare i metodi di pagamento disponibili. | Per visualizzare l'opzione di pagamento "Contanti al ritiro in negozio" con il suo titolo, logo e commissione/sconto calcolato. |
| `paymentOptions` | Alias per `displayPaymentOptions` (versioni PS più vecchie). | Come `displayPaymentOptions`. |
| `displayPaymentReturn` | Nella pagina di conferma dell'ordine dopo il pagamento. | Per visualizzare istruzioni specifiche o messaggi di conferma per gli ordini "Contanti al ritiro". |
| `displayPDFInvoice` | Quando viene generata una fattura PDF. | Per garantire che il metodo di pagamento "Contanti al ritiro in negozio" sia correttamente indicato sulla fattura. |
| `displayOrderDetail` | Nella pagina dei dettagli dell'ordine del cliente nel front-office. | Per mostrare il metodo di pagamento scelto e qualsiasi dettaglio correlato. |
| `displayAdminOrder` | Nella pagina dei dettagli dell'ordine nel Back Office. | Per visualizzare informazioni aggiuntive o strumenti di gestione specifici per gli ordini "Contanti al ritiro" per gli amministratori. |
| `actionAdminControllerSetMedia` | Quando un controller di amministrazione carica le sue risorse multimediali. | Per includere risorse CSS (`admin_coppro.css`, `autocomplete.css`) e JavaScript (`adminCopproDashboard.js`, `adminCopproProductSearch.js`, `adminCopproSelector.js`, `autocomplete.js`) del Back-office per la pagina di configurazione del modulo. |
| `actionValidateOrder` | Dopo che un ordine è stato convalidato con successo. | Per eseguire eventuali azioni post-convalida, come l'aggiornamento dello stato dell'ordine o la registrazione dei dettagli, specifiche per gli ordini "Contanti al ritiro". |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto tecnico ufficiale, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda riguardante il modulo "Contanti al ritiro in negozio (+commissione)".
