---
title: "Bonifico bancario con sconto - Manuale del commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Bonifico bancario con sconto di MyPresta.eu."
sidebar:
  label: "Bonifico bancario con sconto - Manuale del commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Bankwire with discount su MyPresta.eu](https://mypresta.eu/modules/payment-process/bankwire-with-discount.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/payment/bankwire-with-discount/)
>
> ---


# Bonifico bancario con sconto

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono richieste per PrestaShop stesso e generalmente disponibili su tutti gli ambienti di hosting moderni.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Bonifico bancario con sconto)

Questa è la schermata di configurazione principale dove imposterai tutte le funzionalità principali del modulo.

#### **Impostazioni generali**

- **Abilita pagamento tramite bonifico bancario:**

  - **Cosa fa questa impostazione:** Questo è l'interruttore principale per abilitare o disabilitare il metodo di pagamento "Bonifico bancario con sconto" nel tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I clienti vedranno "Paga con bonifico bancario" come opzione di pagamento durante il checkout.
    - *Quando disabilitato:* L'opzione di pagamento tramite bonifico bancario sarà nascosta ai clienti.
  - **Valore consigliato:** SÌ (per utilizzare le funzionalità del modulo).
  - **Scenario del commerciante:** Vuoi offrire pagamenti tramite bonifico bancario.
- **Titolo bonifico bancario:**

  - **Cosa fa questa impostazione:** Definisce il titolo visualizzato per l'opzione di pagamento tramite bonifico bancario nella pagina di checkout.
  - **Effetto della modifica di questa impostazione:** Modifica il testo che i clienti vedono quando scelgono questo metodo di pagamento.
  - **Valore consigliato:** "Paga con bonifico bancario", "Bonifico bancario (con sconto!)" o simile.
  - **Scenario del commerciante:** Vuoi etichettare chiaramente il metodo di pagamento per i clienti.
- **Istruzioni di pagamento (Riepilogo al checkout):**

  - **Cosa fa questa impostazione:** Un breve testo visualizzato nella pagina di selezione del pagamento (prima della conferma) per fornire ai clienti istruzioni rapide o informazioni sul bonifico bancario.
  - **Effetto della modifica di questa impostazione:** Fornisce un contesto immediato al cliente sul metodo di bonifico bancario.
  - **Valore consigliato:** "Riceverai i dettagli bancari dopo aver confermato l'ordine. Sconto applicato!"
  - **Scenario del commerciante:** Vuoi informare i clienti sui passaggi successivi o evidenziare il vantaggio dello sconto in anticipo.
- **Istruzioni di pagamento (Dopo la conferma dell'ordine):**

  - **Cosa fa questa impostazione:** Istruzioni dettagliate visualizzate nella pagina di conferma dell'ordine dopo che un cliente ha effettuato un ordine tramite bonifico bancario. Qui inserisci i dettagli del tuo conto bancario.
  - **Effetto della modifica di questa impostazione:** Fornisce le informazioni essenziali ai clienti per effettuare il bonifico bancario.
  - **Valore consigliato:** Includi il nome della tua banca, l'intestatario del conto, l'IBAN, lo SWIFT/BIC e qualsiasi nota specifica (ad esempio, "Si prega di includere il riferimento dell'ordine nella descrizione del bonifico").
  - **Scenario del commerciante:** Questo è fondamentale affinché i clienti completino con successo il loro pagamento.

#### **Dettagli conto bancario**

Questi campi vengono utilizzati per fornire le informazioni del tuo conto bancario ai clienti.

- **Intestatario conto:**

  - **Cosa fa questa impostazione:** Il nome dell'intestatario del conto bancario.
  - **Effetto della modifica di questa impostazione:** Visualizza questo nome al cliente.
  - **Valore consigliato:** Il nome della tua azienda o il tuo nome personale.
  - **Scenario del commerciante:** Essenziale per il bonifico bancario.
- **Nome della banca:**

  - **Cosa fa questa impostazione:** Il nome della tua banca.
  - **Effetto della modifica di questa impostazione:** Visualizza questo nome al cliente.
  - **Valore consigliato:** ad esempio, "Deutsche Bank", "Bank of America".
  - **Scenario del commerciante:** Essenziale per il bonifico bancario.
- **Indirizzo:**

  - **Cosa fa questa impostazione:** L'indirizzo della tua banca.
  - **Effetto della modifica di questa impostazione:** Visualizza questo indirizzo al cliente.
  - **Valore consigliato:** L'indirizzo della filiale della tua banca.
  - **Scenario del commerciante:** Potrebbe essere richiesto per i bonifici internazionali.
- **IBAN (International Bank Account Number):**

  - **Cosa fa questa impostazione:** Il tuo IBAN, un numero di conto bancario internazionale standardizzato.
  - **Effetto della modifica di questa impostazione:** Visualizza questo numero al cliente.
  - **Valore consigliato:** Il tuo IBAN completo.
  - **Scenario del commerciante:** Cruciale per i bonifici bancari, specialmente in Europa.
- **SWIFT/BIC (Bank Identifier Code):**

  - **Cosa fa questa impostazione:** Il tuo codice SWIFT/BIC, utilizzato per i bonifici bancari internazionali.
  - **Effetto della modifica di questa impostazione:** Visualizza questo codice al cliente.
  - **Valore consigliato:** Il tuo codice SWIFT/BIC completo.
  - **Scenario del commerciante:** Essenziale per i bonifici bancari internazionali.
- **Informazioni aggiuntive:**

  - **Cosa fa questa impostazione:** Eventuali note o istruzioni aggiuntive che desideri fornire in merito al bonifico bancario (ad esempio, "Si prega di consentire 1-3 giorni lavorativi per l'elaborazione").
  - **Effetto della modifica di questa impostazione:** Fornisce ulteriori indicazioni al cliente.
  - **Valore consigliato:** Qualsiasi istruzione specifica non coperta da altri campi.
  - **Scenario del commerciante:** Vuoi gestire le aspettative dei clienti sui tempi di bonifico.

#### **Impostazioni sconto e supplemento**

Questa sezione ti consente di configurare sconti o supplementi per l'utilizzo del bonifico bancario.

- **Tipo di sconto:**

  - **Cosa fa questa impostazione:** Determina come viene calcolato lo sconto.
  - **Effetto della modifica di questa impostazione:**
    - *Percentuale:* Lo sconto è una percentuale del totale dell'ordine.
    - *Importo fisso:* Lo sconto è un importo fisso, indipendentemente dal totale dell'ordine.
  - **Valore consigliato:** Percentuale (spesso più attraente per valori d'ordine variabili).
  - **Scenario del commerciante:** Vuoi offrire il 5% di sconto o uno sconto fisso di 10 €.
- **Valore dello sconto:**

  - **Cosa fa questa impostazione:** Il valore effettivo dello sconto (ad esempio, "5" per il 5% o "10 €" per un importo fisso).
  - **Effetto della modifica di questa impostazione:** Applica direttamente lo sconto al totale dell'ordine se viene scelto il bonifico bancario.
  - **Valore consigliato:** Un valore che rende il bonifico bancario attraente senza intaccare i tuoi margini.
  - **Scenario del commerciante:** Decidi di offrire uno sconto del 3% o uno sconto di 5 €.
- **Base percentuale (se il tipo di sconto è percentuale):**

  - **Cosa fa questa impostazione:** Specifica su quale parte del totale dell'ordine viene applicato lo sconto percentuale.
  - **Effetto della modifica di questa impostazione:** Modifica l'importo base per il calcolo dello sconto.
    - *Totale ordine (con tasse):* Sconto calcolato sul prezzo intero incluse le tasse.
    - *Totale ordine (senza tasse):* Sconto calcolato sul prezzo prima delle tasse.
    - *Totale prodotti (con tasse):* Sconto solo sul valore del prodotto, incluse le tasse.
    - *Totale prodotti (senza tasse):* Sconto solo sul valore del prodotto, escluse le tasse.
  - **Valore consigliato:** Totale ordine (con tasse) per semplicità e chiarezza per il cliente.
  - **Scenario del commerciante:** Vuoi dare il 5% di sconto sull'intero prezzo finale che il cliente vede.
- **Valore minimo del carrello:**

  - **Cosa fa questa impostazione:** Il valore totale minimo che un ordine deve avere affinché venga applicato lo sconto sul bonifico bancario.
  - **Effetto della modifica di questa impostazione:** Lo sconto apparirà e verrà applicato solo se il totale del carrello raggiunge o supera questo valore.
  - **Valore consigliato:** Lascia vuoto se non c'è un minimo, o imposta un valore per incoraggiare ordini più grandi.
  - **Scenario del commerciante:** Vuoi offrire uno sconto solo su ordini superiori a 100 €.
- **Valore massimo del carrello:**

  - **Cosa fa questa impostazione:** Il valore totale massimo che un ordine può avere affinché venga applicato lo sconto sul bonifico bancario.
  - **Effetto della modifica di questa impostazione:** Lo sconto non verrà applicato se il totale del carrello supera questo valore.
  - **Valore consigliato:** Lascia vuoto se non c'è un massimo, o imposta un valore per limitare l'esposizione dello sconto su ordini molto grandi.
  - **Scenario del commerciante:** Non vuoi dare uno sconto su ordini superiori a 1000 €.
- **Valute:**

  - **Cosa fa questa impostazione:** Seleziona per quali valute sarà disponibile il metodo di pagamento tramite bonifico bancario (e il suo sconto).
  - **Effetto della modifica di questa impostazione:** L'opzione di pagamento apparirà solo per i clienti che acquistano nelle valute selezionate.
  - **Valore consigliato:** Seleziona tutte le valute che accetti.
  - **Scenario del commerciante:** Accetti bonifici bancari solo in EUR e USD.
- **Zone:**

  - **Cosa fa questa impostazione:** Seleziona per quali zone geografiche sarà disponibile il metodo di pagamento tramite bonifico bancario (e il suo sconto).
  - **Effetto della modifica di questa impostazione:** L'opzione di pagamento apparirà solo per i clienti il cui indirizzo di spedizione rientra nelle zone selezionate.
  - **Valore consigliato:** Seleziona tutte le zone in cui spedisci.
  - **Scenario del commerciante:** Offri bonifici bancari solo in Europa.
- **Paesi:**

  - **Cosa fa questa impostazione:** Seleziona paesi specifici in cui sarà disponibile il metodo di pagamento tramite bonifico bancario (e il suo sconto).
  - **Effetto della modifica di questa impostazione:** Sovrascrive le impostazioni di zona per paesi specifici.
  - **Valore consigliato:** Seleziona tutti i paesi in cui spedisci.
  - **Scenario del commerciante:** Vuoi escludere un paese specifico dai pagamenti tramite bonifico bancario.
- **Gruppi di clienti:**

  - **Cosa fa questa impostazione:** Seleziona quali gruppi di clienti possono vedere e utilizzare il metodo di pagamento tramite bonifico bancario (e il suo sconto).
  - **Effetto della modifica di questa impostazione:** Solo i clienti appartenenti ai gruppi selezionati vedranno questa opzione di pagamento.
  - **Valore consigliato:** Seleziona tutti i gruppi di clienti pertinenti (ad esempio, "Cliente", "Visitatore", "Ospite").
  - **Scenario del commerciante:** Vuoi offrire bonifici bancari solo ai clienti registrati.

#### **Gestione ordini non pagati**

Queste funzionalità ti aiutano a gestire gli ordini effettuati tramite bonifico bancario ma non ancora pagati.

- **Invia promemoria per ordini non pagati:**

  - **Cosa fa questa impostazione:** Abilita o disabilita i promemoria e-mail automatici ai clienti per gli ordini tramite bonifico bancario non pagati.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il modulo invierà e-mail di promemoria.
    - *Quando disabilitato:* Non verranno inviati promemoria.
  - **Valore consigliato:** SÌ (aiuta a ridurre i pagamenti abbandonati).
  - **Scenario del commerciante:** Vuoi ricordare delicatamente ai clienti di completare il pagamento.
- **Primo promemoria dopo (giorni):**

  - **Cosa fa questa impostazione:** Il numero di giorni dopo l'effettuazione di un ordine prima che venga inviata la prima e-mail di promemoria.
  - **Effetto della modifica di questa impostazione:** Controlla la tempistica del primo promemoria.
  - **Valore consigliato:** 2-3 giorni (dà ai clienti il tempo di pagare, ma non troppo a lungo).
  - **Scenario del commerciante:** Vuoi inviare un promemoria se il pagamento non viene ricevuto entro 2 giorni.
- **Max promemoria per ordine:**

  - **Cosa fa questa impostazione:** Il numero massimo di e-mail di promemoria che un ordine attiverà.
  - **Effetto della modifica di questa impostazione:** Impedisce di inviare troppi promemoria ai clienti.
  - **Valore consigliato:** 1-2 (sufficiente per ricordare senza infastidire).
  - **Scenario del commerciante:** Vuoi inviare un solo promemoria e-mail.
- **Annulla automaticamente gli ordini non pagati:**

  - **Cosa fa questa impostazione:** Abilita o disabilita l'annullamento automatico degli ordini tramite bonifico bancario che rimangono non pagati dopo un periodo specificato.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Gli ordini verranno annullati automaticamente, liberando l'inventario.
    - *Quando disabilitato:* Gli ordini rimarranno nello stato "In attesa di pagamento tramite bonifico bancario" a tempo indeterminato.
  - **Valore consigliato:** SÌ (automatizza la gestione dell'inventario e mantiene pulito l'elenco degli ordini).
  - **Scenario del commerciante:** Non vuoi tenere l'inventario per ordini non pagati per troppo tempo.
- **Annulla dopo (giorni):**

  - **Cosa fa questa impostazione:** Il numero di giorni dopo l'effettuazione di un ordine prima che venga annullato automaticamente se non pagato.
  - **Effetto della modifica di questa impostazione:** Controlla quando gli ordini non pagati vengono annullati.
  - **Valore consigliato:** 5-7 giorni (consente un tempo ragionevole per il pagamento, ma impedisce blocchi indefiniti).
  - **Scenario del commerciante:** Vuoi annullare gli ordini se il pagamento non viene ricevuto entro 7 giorni.
- **Inserisci automaticamente i trasgressori nella blacklist:**

  - **Cosa fa questa impostazione:** Se abilitato, i clienti che effettuano ripetutamente ordini tramite bonifico bancario e poi li vedono annullati a causa del mancato pagamento verranno aggiunti a una blacklist.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I clienti che superano la soglia verranno inseriti nella blacklist.
    - *Quando disabilitato:* Nessun cliente verrà inserito automaticamente nella blacklist.
  - **Valore consigliato:** SÌ (aiuta a scoraggiare clienti fraudolenti o che fanno perdere tempo).
  - **Scenario del commerciante:** Vuoi impedire ai clienti che non pagano mai di effettuare futuri ordini tramite bonifico bancario.
- **Soglia ordini annullati:**

  - **Cosa fa questa impostazione:** Il numero di ordini tramite bonifico bancario annullati che un cliente può avere prima di essere automaticamente inserito nella blacklist.
  - **Effetto della modifica di questa impostazione:** Definisce la tolleranza per il mancato pagamento prima dell'inserimento nella blacklist.
  - **Valore consigliato:** 2-3 (consente errori genuini ma individua i trasgressori abituali).
  - **Scenario del commerciante:** Vuoi inserire un cliente nella blacklist dopo 3 ordini tramite bonifico bancario non pagati e annullati.

#### **Impostazioni avanzate**

- **Token Cron Job:**

  - **Cosa fa questa impostazione:** Un token di sicurezza univoco utilizzato per proteggere l'URL del cron job del modulo. Questo è essenziale affinché le funzionalità automatiche di promemoria e annullamento funzionino.
  - **Effetto della modifica di questa impostazione:** Il cron job verrà eseguito solo se questo token è correttamente incluso nell'URL.
  - **Valore consigliato:** Lascia come generato. Non modificare a meno che tu non sappia cosa stai facendo.
  - **Scenario del commerciante:** Devi impostare un cron job sul tuo server per eseguire le attività automatizzate del modulo. L'URL del cron sarà qualcosa del tipo `iltuonegozio.com/module/bankwiredis/cron?token=IL_TUO_TOKEN_QUI`.
- **Selettori CSS per aggiornamenti dinamici:**

  - **Cosa fa questa impostazione:** Questi campi ti consentono di specificare i selettori CSS per gli elementi nella pagina di checkout che visualizzano il totale del carrello, il subtotale e il costo di spedizione. Il modulo li utilizza per aggiornare dinamicamente i prezzi quando viene applicato uno sconto.
  - **Effetto della modifica di questa impostazione:** Se il tuo tema utilizza classi CSS non standard per questi elementi, la regolazione di questi selettori garantisce che lo sconto sia correttamente riflesso nei prezzi visualizzati durante il checkout.
  - **Valore consigliato:** Lascia come predefinito a meno che lo sconto non venga visualizzato correttamente nella pagina di checkout. In caso di problemi, consulta lo sviluppatore del tuo tema o un webmaster.
  - **Scenario del commerciante:** Il tuo tema personalizzato utilizza `.my-custom-total-price` invece del predefinito `.cart-total-price`. Aggiorneresti questo campo per assicurarti che lo sconto venga applicato visivamente.
- **Modello e-mail:**

  - **Cosa fa questa impostazione:** Ti consente di selezionare un modello di e-mail personalizzato per le istruzioni di pagamento tramite bonifico bancario e i promemoria.
  - **Effetto della modifica di questa impostazione:** Modifica il design e il contenuto delle e-mail inviate dal modulo.
  - **Valore consigliato:** Predefinito (a meno che tu non abbia un modello personalizzato).
  - **Scenario del commerciante:** Vuoi utilizzare un modello di e-mail con il tuo marchio per le comunicazioni tramite bonifico bancario.

#### **Regole di visibilità (Targeting avanzato degli sconti)**

Questa sezione ti consente di creare regole altamente specifiche per quando viene offerto lo sconto sul bonifico bancario.

- **Nome regola:**

  - **Cosa fa questa impostazione:** Un nome descrittivo per la tua regola di sconto (ad esempio, "Sconto festivo per bonifico bancario").
  - **Effetto della modifica di questa impostazione:** Ti aiuta a identificare e gestire diverse regole.
  - **Valore consigliato:** Nome chiaro e conciso.
  - **Scenario del commerciante:** Hai più regole di sconto e devi distinguerle.
- **Attivo:**

  - **Cosa fa questa impostazione:** Abilita o disabilita questa specifica regola di sconto.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* La regola è attiva e le sue condizioni verranno controllate.
    - *Quando disabilitato:* La regola viene ignorata.
  - **Valore consigliato:** SÌ (se vuoi che la regola si applichi).
  - **Scenario del commerciante:** Vuoi disabilitare temporaneamente uno sconto stagionale.
- **Posizione (priorità):**

  - **Cosa fa questa impostazione:** Determina l'ordine in cui le regole vengono valutate se più regole potrebbero applicarsi. I numeri più bassi hanno una priorità più alta.
  - **Effetto della modifica di questa impostazione:** Se il carrello di un cliente corrisponde a più regole, verrà applicata quella con la posizione più bassa.
  - **Valore consigliato:** Usa numeri sequenziali (1, 2, 3...) per gestire la priorità.
  - **Scenario del commerciante:** Se un cliente si qualifica sia per una regola "Sconto generale del 5%" (posizione 10) che per una regola "Sconto VIP del 10%" (posizione 5), verrà applicata la regola VIP.
- **Tipo di sconto, Valore dello sconto, Base percentuale, Valore minimo del carrello, Valore massimo del carrello, Valute, Zone, Paesi, Gruppi di clienti:**

  - **Cosa fa questa impostazione:** Queste sono le stesse impostazioni descritte nella sezione "Impostazioni sconto e supplemento" sopra, ma applicate specificamente a *questa singola regola*. Ciò ti consente di avere importi di sconto o condizioni diverse per scenari diversi.
  - **Effetto della modifica di questa impostazione:** Lo sconto definito all'interno di questa regola si applicherà solo se tutte le sue condizioni specifiche sono soddisfatte.
  - **Valore consigliato:** Configura in base alla tua specifica strategia promozionale.
  - **Scenario del commerciante:** Vuoi offrire uno sconto del 10% per i pagamenti tramite bonifico bancario solo per i clienti del gruppo "Grossista" e solo per ordini superiori a 500 €.
- **Prodotti:**

  - **Cosa fa questa impostazione:** Ti consente di specificare che questa regola di sconto si applica solo se determinati prodotti sono nel carrello.
  - **Effetto della modifica di questa impostazione:** Lo sconto sul bonifico bancario verrà offerto solo se uno o più dei prodotti selezionati sono presenti nel carrello del cliente.
  - **Valore consigliato:** Lascia vuoto per applicare a tutti i prodotti, o seleziona prodotti specifici per promozioni mirate.
  - **Scenario del commerciante:** Vuoi offrire uno sconto sul bonifico bancario solo se un cliente acquista un articolo specifico di alto valore.
- **Categorie:**

  - **Cosa fa questa impostazione:** Ti consente di specificare che questa regola di sconto si applica solo se i prodotti di determinate categorie sono nel carrello.
  - **Effetto della modifica di questa impostazione:** Lo sconto sul bonifico bancario verrà offerto solo se uno o più prodotti delle categorie selezionate sono presenti nel carrello del cliente.
  - **Valore consigliato:** Lascia vuoto per applicare a tutte le categorie, o seleziona categorie specifiche per promozioni mirate.
  - **Scenario del commerciante:** Vuoi offrire uno sconto sul bonifico bancario solo per i prodotti della tua categoria "Elettronica".

#### **Tabella di riferimento rapido della configurazione**

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Configurazione modulo** | Abilita pagamento tramite bonifico bancario | SÌ | Attiva/disattiva il metodo di pagamento. |
| | Titolo bonifico bancario | "Paga con bonifico bancario" | Testo visualizzato per l'opzione di pagamento. |
| | Istruzioni di pagamento (Checkout) | Testo breve e chiaro | Informazioni mostrate nella pagina di selezione del pagamento. |
| | Istruzioni di pagamento (Conferma) | Dettagli bancari dettagliati | Dettagli bancari e istruzioni dopo l'ordine. |
| | Intestatario conto | Nome della tua azienda | Nome sull'account bancario. |
| | Nome della banca | La tua banca | Nome della tua banca. |
| | Indirizzo | Indirizzo della tua banca | Indirizzo della tua banca. |
| | IBAN | Il tuo IBAN | Numero di conto bancario internazionale. |
| | SWIFT/BIC | Il tuo SWIFT/BIC | Codice identificativo della banca per i bonifici internazionali. |
| | Informazioni aggiuntive | Note opzionali | Istruzioni extra per i clienti. |
| | Tipo di sconto | Percentuale | Come viene calcolato lo sconto (percentuale/fisso). |
| | Valore dello sconto | 0 (o valore desiderato) | L'importo o la percentuale di sconto effettivi. |
| | Base percentuale | Totale ordine (con tasse) | A quale importo si applica lo sconto percentuale. |
| | Valore minimo del carrello | Vuoto (o valore desiderato) | Valore minimo dell'ordine per lo sconto. |
| | Valore massimo del carrello | Vuoto (o valore desiderato) | Valore massimo dell'ordine per lo sconto. |
| | Valute | Tutte attive | Valute in cui è disponibile il bonifico bancario. |
| | Zone | Tutte attive | Zone geografiche in cui è disponibile il bonifico bancario. |
| | Paesi | Tutti attivi | Paesi specifici in cui è disponibile il bonifico bancario. |
| | Gruppi di clienti | Tutti attivi | Gruppi di clienti che possono utilizzare il bonifico bancario. |
| | Invia promemoria per ordini non pagati | SÌ | Abilita i promemoria e-mail per gli ordini non pagati. |
| | Primo promemoria dopo (giorni) | 2-3 giorni | Ritardo prima del primo promemoria. |
| | Max promemoria per ordine | 1-2 | Numero massimo di e-mail di promemoria. |
| | Annulla automaticamente gli ordini non pagati | SÌ | Annulla automaticamente gli ordini non pagati. |
| | Annulla dopo (giorni) | 5-7 giorni | Ritardo prima dell'annullamento automatico. |
| | Inserisci automaticamente i trasgressori nella blacklist | SÌ | Inserisce nella blacklist i clienti con troppi ordini annullati. |
| | Soglia ordini annullati | 2-3 | Numero di ordini annullati prima dell'inserimento nella blacklist. |
| | Token Cron Job | Generato automaticamente | Token di sicurezza per il cron job. |
| | Selettori CSS | Predefinito (o specifico del tema) | Per aggiornamenti dinamici dei prezzi al checkout. |
| | Modello e-mail | Predefinito | Modello e-mail per le comunicazioni tramite bonifico bancario. |
| | **Regole di visibilità** | Nome regola | Nome descrittivo |
| | Attivo | SÌ | Attiva/disattiva una regola specifica. |
| | Posizione (priorità) | 1, 2, 3… | Ordine di valutazione delle regole (inferiore = priorità più alta). |
| | Prodotti | Vuoto (o prodotti specifici) | Lo sconto si applica solo se questi prodotti sono nel carrello. |
| | Categorie | Vuoto (o categorie specifiche) | Lo sconto si applica solo se i prodotti di queste categorie sono nel carrello. |

### 2.2 Schermata del controller Back-Office: AdminBankwiredisSearchController

- **Nome schermata e posizione nel menu:** Questo controller viene tipicamente utilizzato per gestire entità specifiche relative al modulo, come clienti nella blacklist o regole di sconto specifiche, spesso accessibile tramite una sotto-scheda sotto la configurazione principale del modulo o una voce di menu dedicata. In questo modulo, è probabile che venga utilizzato per gestire le regole di visibilità o i clienti nella blacklist.
  - **Posizione nel menu:** Probabilmente accessibile tramite una scheda o un link all'interno della pagina di configurazione principale del modulo "Bonifico bancario con sconto", o potenzialmente sotto **Vendi > Ordini > Blacklist Bonifico bancario con sconto** (esempio, la posizione effettiva può variare in base alla versione di PrestaShop e al design del modulo).
- **Azioni e impostazioni disponibili:** Questa schermata fornisce una vista di gestione basata su griglia.
  - **Tabella di elenco:** Visualizza un elenco di elementi (ad esempio, clienti nella blacklist, regole di sconto). Ogni riga mostra tipicamente dettagli rilevanti come ID cliente, E-mail cliente, Motivo della blacklist, Nome regola, Stato attivo, ecc.
  - **Pulsanti Aggiungi/Modifica:** Consente di aggiungere manualmente nuove voci (ad esempio, inserire manualmente un cliente nella blacklist) o modificare quelle esistenti.
  - **Azioni di massa:** Opzioni per eseguire azioni su più elementi selezionati (ad esempio, eliminare più clienti nella blacklist).
  - **Cerca/Filtra:** Strumenti per trovare voci specifiche all'interno dell'elenco.
- **Effetto delle modifiche:**
  - **Aggiunta/Modifica di voci nella blacklist:** Influisce direttamente su quali clienti sono impediti di utilizzare il metodo di pagamento tramite bonifico bancario.
  - **Aggiunta/Modifica di regole di sconto:** Modifica le condizioni in base alle quali vengono applicati gli sconti, influenzando i prezzi e gli incentivi per i clienti.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1. Rivedere regolarmente l'elenco dei clienti nella blacklist per assicurarsi che sia aggiornato.
  2. Se è necessario inserire manualmente un cliente nella blacklist (ad esempio, dopo una comunicazione diretta), utilizzare la funzione "Aggiungi" qui.
  3. Se è necessario modificare o creare nuove regole di sconto, è qui che le si gestisce, assicurandosi che siano allineate con le promozioni attuali.

### 2.3 Schermata del controller Back-Office: index.php (Controller Admin)

- **Nome schermata e posizione nel menu:** Il file `index.php` in una directory del controller admin spesso funge da segnaposto o reindirizzamento, o in alcuni casi, può essere il punto di ingresso per una dashboard o un semplice elenco. Date le funzionalità del modulo, questa potrebbe essere una dashboard per le statistiche dei bonifici bancari o un semplice elenco di ordini in sospeso tramite bonifico bancario.
  - **Posizione nel menu:** Potenzialmente una sotto-scheda sotto la configurazione principale del modulo, o una voce di menu dedicata come **Vendi > Ordini > Dashboard Bonifico bancario con sconto**.
- **Azioni e impostazioni disponibili:** Questa schermata probabilmente presenta una griglia o una dashboard.
  - **Vista Griglia / Gestione:** Potrebbe visualizzare un elenco di ordini recenti tramite bonifico bancario, il loro stato, i promemoria di pagamento inviati o lo stato di annullamento.
  - **Analisi/Statistiche:** Potrebbe mostrare grafici o riepiloghi relativi ai pagamenti tramite bonifico bancario, come tassi di conversione, sconto medio applicato o numero di ordini non pagati.
- **Effetto delle modifiche:** Questa schermata è tipicamente per il monitoraggio e la reportistica, piuttosto che per modifiche dirette alla configurazione. Qualsiasi azione intrapresa qui (ad esempio, contrassegnare manualmente un ordine come pagato) aggiornerebbe lo stato dell'ordine in PrestaShop.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1. Controllare periodicamente questa dashboard per monitorare le prestazioni del metodo di pagamento tramite bonifico bancario.
  2. Rivedere gli ordini in sospeso tramite bonifico bancario per assicurarsi che vengano elaborati o ricordati/annullati come previsto.
  3. Utilizzare le statistiche disponibili per valutare l'efficacia degli sconti sui bonifici bancari e del sistema di promemoria.

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: L'opzione di pagamento tramite bonifico bancario non viene visualizzata nella mia pagina di checkout.**

- **R:** Innanzitutto, controlla se "Abilita pagamento tramite bonifico bancario" è impostato su SÌ nella configurazione del modulo.
- **R:** Successivamente, verifica le impostazioni di "Valute", "Zone", "Paesi" e "Gruppi di clienti". Se il contesto del cliente (valuta, indirizzo di spedizione o gruppo) non corrisponde alle tue selezioni, il metodo di pagamento non apparirà.
- **R:** Se hai regole di visibilità specifiche, assicurati che il carrello del cliente soddisfi tutte le condizioni (valore minimo/massimo del carrello, prodotti/categorie specifici).
- **R:** Svuota la cache di PrestaShop (Parametri avanzati > Prestazioni > Svuota cache).

**D2: Lo sconto non viene applicato o visualizzato correttamente nella pagina di checkout.**

- **R:** Ricontrolla le impostazioni di "Tipo di sconto" e "Valore dello sconto".
- **R:** Rivedi le impostazioni di "Valore minimo del carrello" o "Valore massimo del carrello" – il totale del carrello deve rientrare in questi intervalli.
- **R:** Se stai utilizzando un tema personalizzato, il modulo potrebbe non essere in grado di trovare i selettori CSS corretti per aggiornare i prezzi dinamicamente. Vai alla sezione "Impostazioni avanzate" e assicurati che i "Selettori CSS per aggiornamenti dinamici" corrispondano ai selettori effettivi del tuo tema per il totale del carrello, il subtotale e la spedizione. Potrebbe essere necessario un webmaster per ispezionare il codice del tuo tema.
- **R:** Svuota la cache di PrestaShop.

**D3: I promemoria o gli annullamenti automatici non funzionano.**

- **R:** Questo è quasi sempre un problema di cron job. Devi impostare un cron job sul tuo server per eseguire periodicamente le attività del modulo.
- **R:** Nelle "Impostazioni avanzate" del modulo, copia il "Token Cron Job" e l'URL completo del cron.
- **R:** Accedi al pannello di controllo del tuo hosting (cPanel, Plesk, ecc.) e trova la sezione "Cron Jobs".
- **R:** Aggiungi un nuovo cron job che esegua l'URL fornito ogni poche ore (ad esempio, `wget -O /dev/null "https://iltuonegozio.com/module/bankwiredis/cron?token=IL_TUO_TOKEN_QUI"`).
- **R:** Assicurati che "Invia promemoria per ordini non pagati" e "Annulla automaticamente gli ordini non pagati" siano abilitati e che i giorni siano impostati correttamente.

**D4: Come posso tradurre i testi del modulo in altre lingue?**

- **R:** Nel Back Office di PrestaShop, vai su **Internazionale > Traduzioni**.
- **R:** Seleziona "Traduzioni dei moduli installati", scegli il tuo tema e quindi seleziona "Bonifico bancario con sconto" dal menu a discesa del modulo.
- **R:** Potrai quindi modificare tutte le stringhe traducibili per il modulo. Ricorda di salvare le modifiche.

**D5: Un cliente è stato inserito nella blacklist, ma voglio consentirgli di utilizzare nuovamente il bonifico bancario.**

- **R:** Vai alla schermata di amministrazione dedicata del modulo (probabilmente sotto **Vendi > Ordini > Blacklist Bonifico bancario con sconto** o simile, o una scheda all'interno della configurazione del modulo).
- **R:** Trova il cliente nell'elenco ed elimina la sua voce nella blacklist o modificala per disattivare la blacklist per lui.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Bonifico bancario con sconto" (`bankwiredis`) estende la funzionalità di pagamento di PrestaShop, aderendo al modello MVC. Si integra con il processo di checkout tramite gli hook `PaymentOptions`, gestisce gli stati degli ordini e implementa attività automatizzate (promemoria, annullamenti, blacklist) tramite un cron job. La logica dello sconto viene applicata dinamicamente durante il checkout e mantenuta con l'ordine. I controller admin personalizzati forniscono interfacce di gestione per le regole di sconto e i clienti nella blacklist.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

- `controllers/front/cron.php`
  - **Nome classe:** `BankwiredisCronModuleFrontController` (estende `ModuleFrontController`)
  - **Responsabilità:** Questo controller gestisce l'esecuzione delle attività pianificate. È progettato per essere chiamato da un cron job lato server utilizzando un token sicuro. Elabora i promemoria degli ordini non pagati, gli annullamenti automatici e l'inserimento dei clienti nella blacklist in base alla configurazione del modulo. Non renderizza direttamente alcun contenuto front-office ma esegue operazioni in background.
- `controllers/front/index.php`
  - **Nome classe:** `BankwiredisIndexModuleFrontController` (estende `ModuleFrontController`)
  - **Responsabilità:** Spesso un segnaposto o un punto di ingresso predefinito. In questo modulo, potrebbe gestire i reindirizzamenti o fungere da fallback se altri controller front specifici non corrispondono. Tipicamente non ha una funzione diretta rivolta all'utente.
- `controllers/front/payment.php`
  - **Nome classe:** `BankwiredisPaymentModuleFrontController` (estende `ModuleFrontController`)
  - **Responsabilità:** Questo controller è responsabile della visualizzazione dei dettagli e delle istruzioni di pagamento tramite bonifico bancario al cliente *dopo* che ha selezionato il bonifico bancario come metodo di pagamento ma *prima* che l'ordine sia completamente convalidato. Prepara i dati (dettagli bancari, importo finale con sconto) per il template `payment.tpl` o `validation.tpl`.
- `controllers/front/validation.php`
  - **Nome classe:** `BankwiredisValidationModuleFrontController` (estende `ModuleFrontController`)
  - **Responsabilità:** Questo è il controller cruciale che elabora la convalida finale di un ordine tramite bonifico bancario. Dopo che il cliente conferma la sua scelta, questo controller crea l'ordine in PrestaShop, imposta il suo stato iniziale (ad esempio, "In attesa di pagamento tramite bonifico bancario"), applica lo sconto calcolato e reindirizza il cliente alla pagina di conferma dell'ordine.

#### Controller Admin Back-Office

- `controllers/admin/AdminBankwiredisSearchController.php`
  - **Nome classe:** `AdminBankwiredisSearchController` (estende `ModuleAdminController`)
  - **Nome scheda:** Probabilmente una sotto-scheda sotto la configurazione principale del modulo o una voce di menu dedicata.
  - **Entità gestita:** Questo controller gestisce le entità personalizzate del modulo, in particolare le regole di visibilità dello sconto ed eventualmente i clienti nella blacklist. Fornisce un'interfaccia standard PrestaShop `HelperList` o `HelperForm` per visualizzare, aggiungere, modificare ed eliminare questi record.
- `controllers/admin/index.php`
  - **Nome classe:** `AdminBankwiredisIndexController` (estende `ModuleAdminController`)
  - **Nome scheda:** Simile a `AdminBankwiredisSearchController`, questa sarebbe una pagina admin dedicata.
  - **Entità gestita:** Date le funzionalità del modulo, questo controller probabilmente funge da dashboard o interfaccia di gestione per i dati principali del modulo, come un elenco di ordini in sospeso tramite bonifico bancario, statistiche o una vista semplificata dei clienti nella blacklist.

### 4.3 Classi e modelli principali (`classes/`)

Il dossier del modulo indica l'assenza di classi personalizzate nella directory `classes/`. Ciò suggerisce che i dati del modulo (come le regole di sconto, i clienti nella blacklist) potrebbero essere archiviati direttamente in `ps_configuration` o gestiti tramite istanze generiche di `ObjectModel` definite all'interno del file principale `bankwiredis.php` o direttamente all'interno dei controller admin.

- **Nota:** Se vengono utilizzate tabelle personalizzate, le loro definizioni `ObjectModel` risiederebbero tipicamente qui. Il modulo probabilmente utilizza `Configuration::get()` e `Configuration::updateValue()` per la maggior parte delle impostazioni e potenzialmente `Db::getInstance()` per interazioni dirette con il database per strutture di dati più complesse come regole di sconto o clienti nella blacklist, se non mappate a un `ObjectModel` personalizzato.

### 4.4 Risorse JavaScript (`views/js/`)

- `bankwiredis/lib/searchTool/views/js/autocomplete.js`
  - **Ambito:** Back-office.
  - **Funzionalità:** Fornisce la funzionalità di completamento automatico, probabilmente utilizzata nei moduli admin (ad esempio, `AdminBankwiredisSearchController`) per selezionare prodotti o categorie durante la definizione delle regole di visibilità dello sconto. Ascolta l'input dell'utente in campi di testo specifici ed effettua richieste AJAX per suggerire elementi corrispondenti.
- `bankwiredis/views/js/adminBankwiredisAccounts.js`
  - **Ambito:** Back-office.
  - **Funzionalità:** Probabilmente gestisce il comportamento dinamico nella pagina di configurazione del modulo relativo ai dettagli del conto bancario. Ciò potrebbe includere la visualizzazione/nascondimento di campi in base alle opzioni selezionate, la convalida dell'input o le chiamate AJAX per salvare le informazioni del conto.
- `bankwiredis/views/js/adminBankwiredisDashboard.js`
  - **Ambito:** Back-office.
  - **Funzionalità:** Gestisce elementi interattivi e visualizzazione dei dati nella dashboard admin del modulo (ad esempio, `AdminBankwiredisIndexController`). Ciò potrebbe comportare il recupero di dati tramite AJAX per popolare grafici, tabelle o aggiornare statistiche, e la gestione delle interazioni dell'utente con i widget della dashboard.
- `bankwiredis/views/js/bankwiredis-checkout.js`
  - **Ambito:** Front-office.
  - **Funzionalità:** Questo è uno script critico per l'esperienza del cliente. Ascolta la selezione dell'opzione di pagamento tramite bonifico bancario nella pagina di checkout. Alla selezione, effettua una chiamata AJAX al controller front del modulo per calcolare e visualizzare lo sconto dinamico, aggiornando gli elementi del totale dell'ordine, del subtotale e del costo di spedizione nella pagina. Utilizza i selettori CSS configurati nel back office (`BDIS_CSS_PAY_INPUT`, `BDIS_CSS_CART_TOTAL`, ecc.) per targettizzare gli elementi DOM corretti per l'aggiornamento.

### 4.5 Fogli di stile CSS (`views/css/`)

- `bankwiredis/lib/searchTool/views/css/autocomplete.css`
  - **Ambito:** Back-office.
  - **Funzionalità:** Stila i suggerimenti a discesa del completamento automatico e i campi di input utilizzati negli strumenti di ricerca admin.
- `bankwiredis/views/css/admin_bankwiredis.css`
  - **Ambito:** Back-office.
  - **Funzionalità:** Fornisce uno stile specifico per la pagina di configurazione del modulo e le viste del controller admin personalizzate, garantendo un'interfaccia coerente e user-friendly all'interno del back office di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

#### Template hook (`views/templates/hook/`)

- `bankwiredis/views/templates/hook/infos.tpl`
  - **Hook:** Probabilmente `displayPaymentInfo` o simile.
  - **Output:** Visualizza informazioni generali o un riepilogo sul metodo di pagamento tramite bonifico bancario, potenzialmente includendo l'offerta di sconto, nella pagina di selezione del pagamento o nel riepilogo dell'ordine.
- `bankwiredis/views/templates/hook/payment.tpl`
  - **Hook:** `displayPaymentOptions` (PrestaShop 1.7+), `displayPayment` (PrestaShop 1.6).
  - **Output:** Renderizza l'effettiva opzione di pagamento tramite bonifico bancario nella pagina di checkout, inclusi il suo titolo, la descrizione e l'importo dello sconto calcolato dinamicamente. È qui che il cliente seleziona "Paga con bonifico bancario".
- `bankwiredis/views/templates/hook/payment_return.tpl`
  - **Hook:** `displayPaymentReturn`.
  - **Output:** Visualizza i dettagli del conto bancario e le istruzioni di pagamento nella pagina di conferma dell'ordine dopo che un cliente ha effettuato con successo un ordine tramite bonifico bancario.
- `bankwiredis/views/templates/hook/payment_return_pdf_invoice.tpl`
  - **Hook:** `displayPDFInvoice` (o simile per la generazione di PDF).
  - **Output:** Fornisce il contenuto necessario (dettagli bancari, riepilogo dello sconto) da includere nella fattura PDF generata per gli ordini tramite bonifico bancario.

#### Template admin (`views/templates/admin/`)

- `bankwiredis/lib/searchTool/views/scripts.tpl`
  - **Output:** Probabilmente include risorse JavaScript e CSS per lo strumento di ricerca con completamento automatico all'interno dei moduli admin.
- `bankwiredis/views/templates/admin/scopeSelector.tpl`
  - **Output:** Un template per la selezione dell'ambito (ad esempio, negozio, gruppo, tutti i negozi) in un ambiente multi-negozio, spesso utilizzato nei moduli di configurazione.
- `bankwiredis/views/templates/admin/selectedProducts.tpl`
  - **Output:** Visualizza un elenco di prodotti che sono stati selezionati per una specifica regola di sconto (ad esempio, in `AdminBankwiredisSearchController` durante la configurazione di una regola basata sui prodotti).

#### Template front-office (`views/templates/front/`)

- `bankwiredis/views/templates/front/validation.tpl`
  - **Output:** Questo template viene renderizzato da `BankwiredisPaymentModuleFrontController` o `BankwiredisValidationModuleFrontController` per visualizzare i dettagli bancari finali e le istruzioni *prima* che l'ordine sia completamente confermato o immediatamente dopo, fornendo una pagina dedicata per le istruzioni di pagamento.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

Il modulo utilizza principalmente la tabella `ps_configuration` di PrestaShop per la maggior parte delle sue impostazioni (ad esempio, `BANK_WIRE_DIS_OWNER_`, `BDIS_CRON_TOKEN`, `BANK_WIRE_DIS_CHARGEP`).
Per dati più complessi come le regole di visibilità dello sconto e i clienti nella blacklist, il modulo probabilmente crea tabelle personalizzate durante il suo metodo `install()`. In base alle opzioni di configurazione, queste tabelle sarebbero tipicamente:

- `ps_bankwiredis_rules`: Archivia la definizione di ogni regola di sconto (nome regola, stato attivo, tipo di sconto, valore, carrello min/max, valute, zone, paesi, gruppi di clienti, prodotti, categorie).
- `ps_bankwiredis_blacklist`: Archivia i record dei clienti nella blacklist (ID cliente, e-mail, motivo, data di inserimento nella blacklist).
- `ps_bankwiredis_reminders`: Archivia un registro delle e-mail di promemoria inviate per ogni ordine per tenere traccia di `Max reminders per order`.

#### Tabella degli hook registrati

| Nome hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina front-office. | Utilizzato per caricare risorse CSS e JavaScript front-office (`bankwiredis-checkout.js`) per la visualizzazione dinamica dello sconto. |
| `actionAdminControllerSetMedia` | Quando un controller admin carica le sue risorse multimediali. | Utilizzato per caricare risorse CSS e JavaScript back-office (`admin_bankwiredis.css`, `adminBankwiredisAccounts.js`, `autocomplete.js`) per la configurazione del modulo e le pagine admin. |
| `displayPaymentOptions` | Nella pagina di checkout, quando vengono elencate le opzioni di pagamento. | Renderizza l'opzione di pagamento tramite bonifico bancario, incluso lo sconto calcolato, utilizzando `payment.tpl`. |
| `displayPaymentReturn` | Nella pagina di conferma dell'ordine dopo un ordine riuscito. | Visualizza i dettagli del conto bancario e le istruzioni di pagamento al cliente, utilizzando `payment_return.tpl`. |
| `displayPDFInvoice` | Quando viene generata una fattura PDF. | Inietta i dettagli del conto bancario e le informazioni sullo sconto nella fattura PDF generata per gli ordini tramite bonifico bancario, utilizzando `payment_return_pdf_invoice.tpl`. |
| `actionValidateOrder` | Dopo che un ordine è stato convalidato con successo. | Utilizzato per acquisire i dettagli dell'ordine, applicare lo sconto finale ed eventualmente registrare l'ordine per l'elaborazione di promemoria/annullamento. |
| `displayPaymentInfo` | (Implicito) Spesso utilizzato per visualizzare informazioni aggiuntive sulla selezione del pagamento. | Renderizza `infos.tpl` con informazioni generali sul bonifico bancario. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale degli sviluppatori, fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Assicurarsi di utilizzare la versione più recente e compatibile del modulo per il proprio negozio PrestaShop.
