---
title: "Rewards - Codici voucher dopo gli ordini - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Rewards - Codici voucher dopo gli ordini di MyPresta.eu."
sidebar:
  label: "Rewards - Codici voucher dopo gli ordini - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Rewards - Voucher codes after orders su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/rewards-voucher-codes-after-orders.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/rewards-voucher-codes-after-orders/)
>
> ---


# Rewards - Codici voucher dopo gli ordini

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per il corretto funzionamento di un negozio PrestaShop. Questo modulo non ha requisiti di hosting insoliti o aggiuntivi oltre a una configurazione PrestaShop standard.

## 2. Panoramica completa della configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Rewards - Codici voucher dopo gli ordini)

Questa è la schermata di configurazione principale dove definisci le regole per la generazione e l'invio dei codici voucher.

#### Impostazioni Generali

-   **Abilita modulo:**

    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per il modulo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il modulo monitorerà attivamente gli ordini e genererà/invierà voucher secondo le tue regole.
        -   *Quando disabilitato:* Il modulo sarà inattivo e nessun voucher verrà generato o inviato, indipendentemente dalle altre impostazioni.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio del commerciante:** Hai finito di impostare tutte le tue regole e sei pronto a lanciare il tuo programma di ricompense. Abilita questa opzione per iniziare a inviare voucher. Se hai bisogno di mettere in pausa temporaneamente il programma per manutenzione, disabilitala.
-   **Stati dell'ordine per la generazione del voucher:**

    -   **Cosa fa questa impostazione:** Determina quali stati dell'ordine attiveranno il processo di generazione del voucher. Solo gli ordini che raggiungono uno di questi stati selezionati saranno idonei per una ricompensa.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando selezionato:* Gli ordini con questi stati verranno controllati per l'idoneità al voucher.
        -   *Quando deselezionato:* Gli ordini con questi stati verranno ignorati dal modulo.
    -   **Valore consigliato:** Tipicamente "Pagamento accettato" e "Consegnato". Potresti anche includere "Spedito" se vuoi inviare il voucher prima.
    -   **Scenario / esempio del commerciante:** Vuoi assicurarti che i clienti ricevano un voucher solo dopo che il loro pagamento è confermato e l'ordine è in fase di elaborazione o è stato consegnato. Seleziona "Pagamento accettato" e "Consegnato" per evitare di inviare voucher per ordini annullati o in sospeso.
-   **Totale minimo dell'ordine per il voucher:**

    -   **Cosa fa questa impostazione:** Imposta un valore totale minimo (escluse le spese di spedizione) che un ordine deve raggiungere per qualificarsi per un voucher.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su un valore (es. 50):* Solo gli ordini con un totale maggiore o uguale a 50 attiveranno un voucher.
        -   *Quando impostato su 0 (o vuoto):* Tutti gli ordini, indipendentemente dal valore, saranno idonei (se le altre condizioni sono soddisfatte).
    -   **Valore consigliato:** Un valore che abbia senso commerciale per il tuo valore medio dell'ordine, o 0 se vuoi premiare tutti gli ordini.
    -   **Scenario / esempio del commerciante:** Vuoi incoraggiare acquisti più grandi. Imposta questo valore a €50 in modo che solo i clienti che spendono €50 o più ricevano uno sconto, rendendo il voucher una ricompensa per transazioni di valore più elevato.

#### Impostazioni del codice voucher

-   **Prefisso del codice voucher:**

    -   **Cosa fa questa impostazione:** Una stringa di caratteri che apparirà all'inizio di ogni codice voucher generato. Questo ti aiuta a identificare i voucher di questo modulo.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato (es. "REWARD"):* I codici appariranno come "REWARDABCD123".
        -   *Quando vuoto:* I codici saranno puramente caratteri casuali.
    -   **Valore consigliato:** Un prefisso breve e descrittivo come "REWARD", "THANKYOU" o le iniziali del tuo negozio.
    -   **Scenario / esempio del commerciante:** Hai più promozioni. L'uso di "REWARD" come prefisso ti aiuta a identificare rapidamente quali voucher provengono da questo modulo nelle tue regole di sconto PrestaShop.
-   **Lunghezza del codice voucher:**

    -   **Cosa fa questa impostazione:** Definisce il numero totale di caratteri nel codice voucher generato (incluso il prefisso).
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato a 10 con un prefisso "REWARD":* La parte casuale sarà lunga 4 caratteri (10 - 6 per "REWARD").
        -   *Quando impostato su un numero inferiore:* Codici più brevi, potenzialmente più facili da digitare ma meno unici.
        -   *Quando impostato su un numero superiore:* Codici più lunghi, più sicuri ma più difficili da digitare.
    -   **Valore consigliato:** 8-12 caratteri (incluso il prefisso) per un buon equilibrio tra sicurezza e usabilità.
    -   **Scenario / esempio del commerciante:** Vuoi che i codici siano facili da ricordare ma comunque unici. Una lunghezza di 10-12 caratteri è solitamente sufficiente.
-   **Tipo di valore del voucher:**

    -   **Cosa fa questa impostazione:** Determina se il voucher offre uno sconto percentuale o un importo fisso.
    -   **Effetto della modifica di questa impostazione:**
        -   *Percentuale:* Il voucher dedurrà una percentuale del totale dell'ordine.
        -   *Importo fisso:* Il voucher dedurrà un valore monetario specifico.
    -   **Valore consigliato:** Dipende dalla tua strategia di marketing. La percentuale è buona per incoraggiare ordini più grandi, l'importo fisso è più semplice e chiaro.
    -   **Scenario / esempio del commerciante:** Vuoi offrire il 10% di sconto sul prossimo ordine, quindi selezioni "Percentuale". Se vuoi offrire uno sconto fisso di €5, seleziona "Importo fisso".
-   **Valore del voucher:**

    -   **Cosa fa questa impostazione:** Il valore effettivo dello sconto. Sarà una percentuale (es. 10) o un importo fisso (es. 5.00) a seconda dell'impostazione "Tipo di valore del voucher".
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato a 10 e "Percentuale":* I clienti ottengono il 10% di sconto.
        -   *Quando impostato a 5.00 e "Importo fisso":* I clienti ottengono €5 di sconto.
    -   **Valore consigliato:** Un valore che renda l'offerta attraente ma sia sostenibile per la tua attività.
    -   **Scenario / esempio del commerciante:** Decidi di offrire uno sconto del 15%, quindi inserisci "15" qui dopo aver selezionato "Percentuale" sopra.
-   **Totale minimo dell'ordine per l'utilizzo del voucher:**

    -   **Cosa fa questa impostazione:** Imposta un importo minimo di acquisto richiesto affinché il cliente possa utilizzare il codice voucher generato.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato a 20:* Il cliente deve spendere almeno €20 sul suo prossimo ordine per applicare il voucher.
        -   *Quando impostato a 0 (o vuoto):* Il voucher può essere utilizzato su qualsiasi ordine, indipendentemente dal suo valore.
    -   **Valore consigliato:** Un valore leggermente superiore al tuo valore medio dell'ordine per incoraggiare l'upselling, o 0 se vuoi la massima usabilità.
    -   **Scenario / esempio del commerciante:** Vuoi assicurarti che il voucher incoraggi un nuovo acquisto, non solo un piccolo extra. Imposta questo valore a €25, in modo che il cliente debba acquistare qualcosa di sostanzioso per utilizzare il suo voucher da €5.
-   **Validità del voucher (Giorni):**

    -   **Cosa fa questa impostazione:** Definisce quanti giorni il codice voucher generato sarà valido dalla data di creazione.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato a 30:* Il voucher scadrà 30 giorni dopo l'invio.
        -   *Quando impostato a 0 (o vuoto):* Il voucher sarà valido indefinitamente (non consigliato, in quanto rimuove l'urgenza).
    -   **Valore consigliato:** 30-90 giorni per creare urgenza senza essere troppo restrittivo.
    -   **Scenario / esempio del commerciante:** Vuoi che i clienti utilizzino il loro voucher entro un periodo di tempo ragionevole. Imposta questo valore a 60 giorni per dare loro due mesi per effettuare un altro acquisto.
-   **Applica voucher a gruppi di clienti specifici:**

    -   **Cosa fa questa impostazione:** Ti consente di limitare l'utilizzo del voucher generato a specifici gruppi di clienti (es. "Clienti VIP", "Grossisti").
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando selezionato:* Solo i clienti appartenenti ai gruppi scelti possono utilizzare il voucher.
        -   *Quando deselezionato (o tutti i gruppi selezionati):* Qualsiasi cliente può utilizzare il voucher.
    -   **Valore consigliato:** Lascia tutti selezionati a meno che tu non abbia una strategia di segmentazione specifica.
    -   **Scenario / esempio del commerciante:** Vuoi offrire uno sconto speciale solo al tuo gruppo "Clienti registrati". Seleziona solo quel gruppo qui.
-   **Applica voucher a prodotti/categorie specifici:**

    -   **Cosa fa questa impostazione:** Ti consente di limitare l'applicabilità del voucher a determinati prodotti o categorie di prodotti.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando selezionato:* Il voucher si applicherà solo agli articoli dei prodotti/categorie scelti.
        -   *Quando deselezionato (o nessuno selezionato):* Il voucher si applica a tutti i prodotti nel carrello.
    -   **Valore consigliato:** Lascia deselezionato per sconti generali su tutto il negozio. Usalo per promozioni mirate.
    -   **Scenario / esempio del commerciante:** Vuoi promuovere una nuova collezione specifica. Puoi configurare il voucher in modo che si applichi solo ai prodotti all'interno di quella categoria.
-   **Escludi prodotti scontati:**

    -   **Cosa fa questa impostazione:** Se abilitata, il voucher non può essere utilizzato su prodotti già in saldo o con un prezzo specifico.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Impedisce l'accumulo di sconti, assicurando che i clienti non ottengano doppi sconti.
        -   *Quando disabilitato:* I voucher possono essere applicati a articoli già scontati.
    -   **Valore consigliato:** SÌ, per proteggere i tuoi margini di profitto.
    -   **Scenario / esempio del commerciante:** Stai facendo un saldo del 20% su tutto il negozio. Non vuoi che i clienti utilizzino il loro voucher premio in aggiunta, dando loro effettivamente il 30% di sconto. Abilita questa opzione per evitarlo.
-   **Escludi spedizione:**

    -   **Cosa fa questa impostazione:** Determina se lo sconto del voucher si applica al costo di spedizione dell'ordine.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il voucher riduce solo il totale del prodotto, non la tariffa di spedizione.
        -   *Quando disabilitato:* Il voucher può ridurre il valore totale dell'ordine, inclusa la spedizione.
    -   **Valore consigliato:** SÌ, poiché i costi di spedizione sono spesso fissi e non fanno parte del tuo margine di prodotto.
    -   **Scenario / esempio del commerciante:** Offri la spedizione gratuita sopra una certa soglia. Vuoi che il voucher influenzi solo i prezzi dei prodotti, non il costo di spedizione. Abilita questa opzione.
-   **Voucher per l'N-esimo ordine:**

    -   **Cosa fa questa impostazione:** Questa è una potente funzionalità che ti consente di specificare per quale numero d'ordine (1°, 2°, 3°, ecc.) un cliente riceve un voucher.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato a 1:* Solo il primissimo ordine del cliente attiverà un voucher.
        -   *Quando impostato a 2:* Solo il loro secondo ordine attiverà un voucher.
        -   *Quando impostato a 0 (o vuoto):* Ogni ordine idoneo attiverà un voucher (se le altre condizioni sono soddisfatte).
    -   **Valore consigliato:** 1 per un'offerta "bentornato", o 0 per un programma di fedeltà generale. Puoi anche creare più regole (vedi sezione 4.2) per diversi N-esimi ordini.
    -   **Scenario / esempio del commerciante:** Vuoi dare un "grazie" speciale ai primi acquirenti. Imposta questo valore a "1". Per un programma di fedeltà generale, lascialo a "0" o crea regole specifiche per il 2°, 3°, ecc. ordine.

#### Impostazioni del modello di email

-   **Oggetto dell'email:**

    -   **Cosa fa questa impostazione:** La riga dell'oggetto dell'email che i clienti ricevono contenente il loro codice voucher.
    -   **Effetto della modifica di questa impostazione:** Questo è ciò che i clienti vedono nella loro casella di posta. Una riga dell'oggetto accattivante aumenta i tassi di apertura.
    -   **Valore consigliato:** Qualcosa di coinvolgente come "Il tuo sconto speciale per il tuo prossimo ordine!" o "Grazie! Ecco un regalo da parte nostra."
    -   **Scenario / esempio del commerciante:** Vuoi chiarire che si tratta di una ricompensa. Imposta l'oggetto su "Il tuo voucher esclusivo da [Nome del tuo negozio]!"
-   **Contenuto dell'email:**

    -   **Cosa fa questa impostazione:** Il corpo principale dell'email. Puoi usare segnaposto come `{customer_name}`, `{voucher_code}`, `{voucher_value}`, `{min_order_total}`, `{validity_days}` per personalizzare il messaggio.
    -   **Effetto della modifica di questa impostazione:** Qui comunichi il valore del voucher e come usarlo. Un messaggio chiaro e amichevole incoraggia l'utilizzo.
    -   **Valore consigliato:** Un messaggio di benvenuto, istruzioni chiare e tutti i dettagli rilevanti del voucher.
    -   **Scenario / esempio del commerciante:** "Caro {customer\_name}, grazie per il tuo recente acquisto! Come segno del nostro apprezzamento, ecco un codice sconto di {voucher\_value} per il tuo prossimo ordine: **{voucher\_code}**. Questo voucher è valido per {validity\_days} giorni e può essere utilizzato su ordini superiori a {min\_order\_total}. Buono shopping!"
-   **Invia email al cliente:**

    -   **Cosa fa questa impostazione:** Controlla se l'email contenente il voucher viene effettivamente inviata al cliente.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* I clienti ricevono l'email.
        -   *Quando disabilitato:* I voucher vengono comunque generati (se abilitato), ma i clienti non ricevono una notifica via email. Dovresti quindi comunicare il codice voucher tramite un altro canale.
    -   **Valore consigliato:** SÌ, poiché l'email è il metodo di consegna principale per questo modulo.
    -   **Scenario / esempio del commerciante:** Hai impostato tutto e vuoi che i clienti ricevano le loro ricompense. Abilita questa opzione. Se stai testando o preferisci inviare i codici manualmente, potresti disabilitarla temporaneamente.

#### Impostazioni Cron Job

-   **URL del Cron Job:**
    -   **Cosa fa questa impostazione:** Questo è un URL unico che, quando viene richiamato, attiva il modulo per controllare nuovi ordini idonei e generare/inviare voucher.
    -   **Effetto della modifica di questa impostazione:** Questo URL è cruciale per l'automazione del modulo. Deve essere chiamato regolarmente.
    -   **Valore consigliato:** NON modificare questo URL. Copialo e impostalo nel pannello di controllo del tuo hosting.
    -   **Scenario / esempio del commerciante:** Copi questo URL e lo incolli nel gestore dei cron job del tuo provider di hosting (es. cPanel, Plesk) per eseguirlo ogni 15-30 minuti. Ciò garantisce che i voucher vengano inviati prontamente dopo l'elaborazione degli ordini.

### 2.2 Schermata di amministrazione dedicata: Elenco premi (Back Office > Rewards > Elenco premi)

Questa schermata fornisce una panoramica completa di tutti i codici voucher generati dal modulo. Funge da registro e interfaccia di gestione per il tuo programma di premi.

-   **Nome schermata e posizione nel menu:** **Elenco premi** (si trova sotto una nuova voce di menu "Rewards" nel tuo Back Office di PrestaShop, o potenzialmente sotto "Catalogo" o "Marketing" a seconda della tua versione e tema di PrestaShop).
-   **Azioni e impostazioni disponibili:**
    -   **Colonne della tabella:** Vedrai una tabella con le seguenti colonne:
        -   **ID:** L'identificatore unico per la voce del premio.
        -   **ID ordine:** L'ID dell'ordine PrestaShop che ha attivato questo premio.
        -   **Cliente:** Il nome del cliente che ha ricevuto il voucher.
        -   **Email:** L'indirizzo email del cliente.
        -   **Riferimento ordine:** Il numero di riferimento unico dell'ordine.
        -   **Codice premio:** Il codice voucher effettivo generato e inviato al cliente.
        -   **Data di generazione:** La data e l'ora in cui il voucher è stato generato.
    -   **Filtro e ricerca:** Puoi tipicamente filtrare o cercare per qualsiasi di queste colonne (es. cercare un'email cliente specifica, un ID ordine o un codice voucher) per trovare voci di premio specifiche.
    -   **Nessun pulsante "Aggiungi/Modifica":** Questa schermata è principalmente per la visualizzazione dei premi generati. I voucher vengono creati automaticamente in base alla tua configurazione, non aggiunti manualmente qui.
-   **Effetto delle modifiche:** Questa schermata è un registro di sola lettura. Le modifiche alla configurazione del modulo (Sezione 4.1) influenzeranno le *future* generazioni di voucher, ma le voci esistenti qui riflettono eventi passati.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    -   Controlla periodicamente questo elenco per monitorare l'attività del tuo programma di premi.
    -   Se un cliente afferma di non aver ricevuto un voucher, puoi cercare rapidamente il suo ordine qui, trovare il "Codice premio" e confermare la data di generazione. Puoi quindi fornire manualmente il codice al cliente se necessario.
    -   Utilizza le opzioni di filtro per analizzare quali ordini stanno attivando i premi o per risolvere problemi specifici dei clienti.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Configurazione modulo** | Abilita modulo | SÌ | Interruttore principale per la funzionalità del modulo. |
| | Stati dell'ordine per la generazione del voucher | Pagamento accettato, Consegnato | Definisce quali stati dell'ordine attivano la generazione del voucher. |
| | Totale minimo dell'ordine per il voucher | 0 (o il valore desiderato) | Valore minimo dell'ordine affinché un ordine si qualifichi per un voucher. |
| | Prefisso del codice voucher | REWARD (o a tua scelta) | Prefisso per i codici voucher generati. |
| | Lunghezza del codice voucher | 8-12 | Lunghezza totale del codice voucher. |
| | Tipo di valore del voucher | Percentuale / Importo fisso | Scegli tra uno sconto percentuale o un importo fisso. |
| | Valore del voucher | Il tuo valore desiderato (es. 10 o 5.00) | Il valore effettivo dello sconto del voucher. |
| | Totale minimo dell'ordine per l'utilizzo del voucher | 0 (o il valore desiderato) | Valore minimo dell'ordine richiesto per *utilizzare* il voucher. |
| | Validità del voucher (Giorni) | 30-90 | Quanti giorni il voucher è valido dopo la generazione. |
| | Applica voucher a gruppi di clienti specifici | Tutti selezionati | Limita l'utilizzo del voucher ai gruppi di clienti selezionati. |
| | Applica voucher a prodotti/categorie specifici | Nessuno selezionato | Limita l'utilizzo del voucher ai prodotti/categorie selezionati. |
| | Escludi prodotti scontati | SÌ | Impedisce che i voucher si applichino a articoli già scontati. |
| | Escludi spedizione | SÌ | Impedisce che i voucher riducano i costi di spedizione. |
| | Voucher per l'N-esimo ordine | 0 (o 1 per il primo ordine) | Specifica per quale numero d'ordine (1°, 2°, ecc.) viene generato un voucher. |
| | Oggetto dell'email | Il tuo sconto speciale! | Riga dell'oggetto dell'email contenente il voucher. |
| | Contenuto dell'email | Messaggio personalizzato con segnaposto | Corpo dell'email, inclusi i dettagli del voucher. |
| | Invia email al cliente | SÌ | Controlla se l'email del voucher viene inviata al cliente. |
| | URL del Cron Job | NON modificare | URL essenziale per la generazione automatica dei voucher. |
| **Elenco premi** | ID, ID ordine, Cliente, Email, Riferimento ordine, Codice premio, Data di generazione | N/A (sola lettura) | Visualizza un registro di tutti i voucher generati per monitoraggio e risoluzione dei problemi. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei clienti non ricevono le email dei voucher. Cosa dovrei controllare?**
R:

1.  **Modulo abilitato?** Ricontrolla che "Abilita modulo" sia impostato su SÌ nella configurazione del modulo.
2.  **Stati dell'ordine:** Assicurati che lo stato dell'ordine corrisponda a uno degli "Stati dell'ordine per la generazione del voucher" che hai selezionato.
3.  **Cron Job:** Verifica che il tuo cron job sia configurato correttamente e in esecuzione regolarmente sul tuo hosting. L'"URL del Cron Job" deve essere richiamato affinché il modulo elabori gli ordini.
4.  **Invio email abilitato:** Assicurati che "Invia email al cliente" sia impostato su SÌ.
5.  **Cartella spam:** Chiedi ai clienti di controllare le loro cartelle spam o posta indesiderata.
6.  **Impostazioni email di PrestaShop:** Controlla la configurazione principale delle email del tuo PrestaShop (Parametri avanzati > E-mail) per assicurarti che le email vengano inviate correttamente dal tuo negozio.

**D: I voucher vengono generati, ma non sembrano funzionare per i clienti.**
R:

1.  **Validità del voucher:** Controlla l'impostazione "Validità del voucher (Giorni)". Il voucher è scaduto?
2.  **Totale minimo dell'ordine per l'utilizzo:** Il carrello attuale del cliente soddisfa il "Totale minimo dell'ordine per l'utilizzo del voucher"?
3.  **Gruppi di clienti:** Il cliente fa parte dei "Gruppi di clienti specifici a cui applicare il voucher" selezionati?
4.  **Restrizioni prodotto/categoria:** I prodotti nel carrello del cliente sono idonei in base a "Applica voucher a prodotti/categorie specifici"?
5.  **Escludi prodotti scontati:** Il cliente sta cercando di utilizzare il voucher su un prodotto già scontato e "Escludi prodotti scontati" è abilitato?
6.  **Errori di battitura:** Chiedi al cliente di ricontrollare il codice voucher per eventuali errori di battitura.

**D: Voglio offrire voucher diversi per diversi numeri d'ordine (es. 1°, 2°, 5° ordine). Come faccio?**
R: La descrizione del modulo indica il supporto per "molti tipi di azioni come: voucher per il primo ordine, voucher per il secondo ordine, quinto, sesto ecc.". Ciò implica che il modulo ha un meccanismo per definire più regole basate sull'N-esimo ordine.

-   **Verifica la presenza di schede per regole multiple:** Cerca schede o sezioni aggiuntive all'interno della configurazione del modulo che ti consentano di "Aggiungi nuova regola" o definire configurazioni separate per diversi valori di "N-esimo ordine". Se tale interfaccia esiste, creeresti una regola separata per ogni N-esimo ordine con le sue impostazioni specifiche del voucher.
-   **Se esiste solo un campo "Voucher per l'N-esimo ordine":** Se il modulo presenta un solo campo "Voucher per l'N-esimo ordine" nella pagina di configurazione principale, significa che puoi impostare *una sola* di queste regole alla volta. Per implementare un sistema a livelli, dovresti modificare manualmente questa impostazione dopo un certo periodo o considerare se la versione attuale del modulo supporta questa funzionalità avanzata tramite un'interfaccia meno ovvia. Per la maggior parte degli utenti, impostarlo su `0` (ogni ordine) o `1` (solo il primo ordine) è il caso d'uso principale.

**D: Il modulo sta rallentando il mio Back Office / Front Office.**
R: Questo modulo opera principalmente in background tramite un cron job e ha un impatto minimo sulle prestazioni del front-office. Se noti rallentamenti:

1.  **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e svuota la cache di PrestaShop.
2.  **Controlla le risorse del server:** Monitora l'utilizzo di CPU e memoria del tuo server, specialmente quando il cron job è in esecuzione. Se il tuo server è sottodimensionato, anche semplici attività possono causare rallentamenti.
3.  **Altri moduli:** Disabilita temporaneamente altri moduli installati di recente per vedere se c'è un conflitto.

**D: Posso personalizzare ulteriormente il modello di email?**
R: Sì, il modulo fornisce i campi "Oggetto dell'email" e "Contenuto dell'email" con segnaposto per una personalizzazione di base. Per modifiche di design avanzate (es. aggiungere il logo del tuo negozio, cambiare font/colori), dovresti tipicamente modificare direttamente i file del modello di email del modulo. Questo di solito richiede un webmaster o uno sviluppatore. La struttura interna del modulo suggerisce che utilizza `lib/emailTemplatesManager`, che potrebbe offrire una gestione più avanzata dei modelli all'interno del modulo stesso, ma la configurazione primaria avviene tramite i campi di testo.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Rewards - Codici voucher dopo gli ordini" segue un'architettura standard dei moduli PrestaShop, sfruttando i principi MVC ove applicabile. La sua funzionalità principale ruota attorno a un meccanismo di cron job che controlla periodicamente gli ordini idonei e, una volta trovati, genera oggetti `CartRule` (voucher) di PrestaShop e invia email. Il modulo estende `Module` per la sua funzionalità principale e utilizza `AdminController` per la sua interfaccia di gestione del Back Office. Incorpora anche diverse librerie di utilità per la gestione dei modelli di email e la funzionalità di ricerca.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

-   `controllers/front/cronJob.php`
    -   **Nome classe:** `OrdercouponsCronJobModuleFrontController` (probabilmente, in base al nome del file)
    -   **Classe genitore:** `ModuleFrontController`
    -   **Responsabilità:** Questo controller è progettato per essere accessibile tramite l'URL del Cron Job fornito nella configurazione del modulo. Quando richiamato, attiva la logica principale all'interno del file del modulo `cronjob.php` per elaborare gli ordini, generare voucher e inviare email. Tipicamente non renderizza alcun contenuto del front-office ma esegue attività in background.
-   `controllers/front/index.php`
    -   **Nome classe:** `OrdercouponsIndexModuleFrontController` (probabilmente)
    -   **Classe genitore:** `ModuleFrontController`
    -   **Responsabilità:** Questo è spesso un segnaposto o un semplice controller di reindirizzamento. In molti moduli, `index.php` in una directory di controller assicura semplicemente che l'accesso diretto alla directory non si traduca in un elenco di directory, oppure potrebbe contenere una logica minima per una vista predefinita del front-office se il modulo ne avesse una. Per questo modulo, è improbabile che abbia una significativa responsabilità di rendering del front-office.

#### Controller Admin del Back-Office

-   `controllers/admin/AdminOrderCouponsRewards.php`
    -   **Nome classe:** `AdminOrderCouponsRewardsController`
    -   **Classe genitore:** `ModuleAdminController` (o `AdminController` nelle versioni precedenti)
    -   **Nome scheda:** "Elenco premi" (sotto una voce di menu "Rewards")
    -   **Entità gestita:** `orewards_list` (probabilmente una tabella di database personalizzata per la registrazione dei premi generati).
    -   **Responsabilità:** Questo controller gestisce l'"Elenco premi" nel Back Office di PrestaShop. Visualizza un elenco di tutti i codici voucher generati, gli ID ordine associati, i dettagli del cliente e le date di generazione. Utilizza `HelperList` per il rendering della tabella e fornisce funzionalità di filtro. Non consente la creazione o la modifica manuale dei premi, poiché vengono generati automaticamente.
-   `controllers/admin/index.php`
    -   **Nome classe:** `AdminOrdercouponsIndexController` (probabilmente)
    -   **Classe genitore:** `ModuleAdminController` (o `AdminController`)
    -   **Responsabilità:** Simile a `index.php` del front-office, questo è probabilmente un segnaposto o un controller predefinito per la sezione amministrativa, garantendo la protezione della directory o fornendo una vista di fallback. La funzionalità amministrativa principale è gestita da `AdminOrderCouponsRewards.php`.

### 4.3 Classi e modelli principali (`classes/`)

L'inventario fornito non indica classi personalizzate nella directory `classes/`. Ciò suggerisce che la logica principale del modulo per la generazione dei voucher potrebbe essere direttamente all'interno del file del modulo principale `cronjob.php` o sfrutta l'`ObjectModel` `CartRule` (Sconto) integrato di PrestaShop e i suoi metodi associati.

-   **Interazione con `CartRule`:** Il modulo interagirebbe direttamente con la classe `CartRule` di PrestaShop per creare nuovi codici sconto. Ciò implica l'impostazione di proprietà come `code`, `value`, `reduction_type`, `minimum_amount`, `date_from`, `date_to`, `quantity`, `quantity_per_user`, `id_customer`, `id_group`, `id_product`, `id_category`, `reduction_exclude_special`, `free_shipping`, ecc., in base alla configurazione del modulo.
-   **Tabella personalizzata `orewards_list`:** Sebbene non sia esplicitamente elencato alcun `ObjectModel`, `AdminOrderCouponsRewardsController` gestisce `orewards_list`. Ciò implica fortemente che esiste una tabella di database personalizzata `ps_orewards_list` (o prefisso simile) per registrare i premi generati. Il controller interrogherebbe direttamente questa tabella o utilizzerebbe un semplice livello di accesso ai dati.

### 4.4 Risorse JavaScript (`views/js/`)

-   `ordercoupons/js/script.js`
    -   **Ambito:** Probabilmente Back-office.
    -   **Responsabilità:** JavaScript generale per la pagina di configurazione del modulo o le schermate di amministrazione. Questo potrebbe includere la convalida del modulo, chiamate AJAX per il salvataggio delle impostazioni, aggiornamenti dinamici dell'interfaccia utente o listener di eventi per opzioni di configurazione specifiche.
-   `ordercoupons/lib/emailTemplatesManager/js/emailTemplatesManager.js`
    -   **Ambito:** Back-office.
    -   **Responsabilità:** Gestisce l'interfaccia di modifica del modello di email. Questo script gestirebbe l'inserimento dinamico di segnaposto, le capacità di modifica del testo ricco, la funzionalità di anteprima e il salvataggio del contenuto dell'email.
-   `ordercoupons/lib/searchTool/views/js/autocomplete.js`
    -   **Ambito:** Back-office.
    -   **Responsabilità:** Fornisce la funzionalità di completamento automatico per i campi di input, probabilmente utilizzata per selezionare prodotti, categorie o gruppi di clienti specifici all'interno dei moduli di configurazione del modulo. Gestirebbe le richieste AJAX per recuperare i risultati della ricerca e visualizzarli all'utente.
-   `ordercoupons/lib/voucherengine/script.js`
    -   **Ambito:** Back-office.
    -   **Responsabilità:** JavaScript specifico relativo al motore di generazione dei voucher. Questo potrebbe includere la logica per il calcolo dinamico della lunghezza del codice voucher, la convalida dei valori del voucher o l'interazione con le impostazioni di `CartRule` nel modulo di configurazione.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `ordercoupons/css.css`
    -   **Ambito:** Principalmente Back-office, potenzialmente anche Front-office se il modulo avesse elementi visibili. Data la natura del modulo, è principalmente per lo stile dell'amministrazione.
    -   **Componenti UI principali:** Stile generale per la pagina di configurazione del modulo e la tabella "Elenco premi".
    -   **Selettori di classe CSS chiave:** `.ordercoupons-config`, `.ordercoupons-table`, `.ordercoupons-form-group`.
-   `ordercoupons/lib/emailTemplatesManager/css/emailTemplatesManager.css`
    -   **Ambito:** Back-office.
    -   **Componenti UI principali:** Stili per l'interfaccia dell'editor di modelli di email, inclusi aree di testo, pulsanti e sezioni di anteprima.
    -   **Selettori di classe CSS chiave:** `.email-template-editor`, `.template-preview`.
-   `ordercoupons/lib/searchTool/views/css/autocomplete.css`
    -   **Ambito:** Back-office.
    -   **Componenti UI principali:** Stile per i menu a discesa di completamento automatico e i campi di input.
    -   **Selettori di classe CSS chiave:** `.autocomplete-container`, `.autocomplete-results`, `.autocomplete-item`.
-   `ordercoupons/lib/voucherengine/ps16.css`
    -   **Ambito:** Back-office.
    -   **Componenti UI principali:** Regolazioni di stile specifiche per la compatibilità con PrestaShop 1.6 o elementi specifici relativi al motore dei voucher, garantendo un aspetto e una sensazione coerenti tra le diverse versioni di PS.
    -   **Selettori di classe CSS chiave:** `.voucher-engine-settings`, `.ps16-compat`.

### 4.6 Struttura del modello Smarty (`views/templates/`)

#### Modelli hook (`views/templates/hook/`)

L'inventario non elenca alcun modello direttamente sotto `views/templates/hook/`. Ciò conferma che il modulo non renderizza alcun contenuto visivo direttamente negli hook standard di PrestaShop come `displayHeader`, `displayRightColumn`, `displayFooter`, ecc. La sua interazione con il front-office avviene puramente tramite email.

#### Modelli admin (`views/templates/admin/`)

-   `ordercoupons/views/templates/admin/admin.tpl`
    -   **Scopo:** Il modello principale per la pagina di configurazione del modulo (accessibile tramite `getContent()` in `cronjob.php`). Contenerebbe la struttura del modulo per tutte le impostazioni descritte nella Sezione 4.1.
-   `ordercoupons/views/templates/admin/customerGroups.tpl`
    -   **Scopo:** Un modello parziale probabilmente utilizzato all'interno di `admin.tpl` per renderizzare l'interfaccia di selezione per "Applica voucher a gruppi di clienti specifici".
-   `ordercoupons/views/templates/admin/orderstates.tpl`
    -   **Scopo:** Un modello parziale probabilmente utilizzato all'interno di `admin.tpl` per renderizzare l'interfaccia di selezione per "Stati dell'ordine per la generazione del voucher".
-   `ordercoupons/views/templates/admin/scripts.tpl`
    -   **Scopo:** Un modello parziale utilizzato per includere file JavaScript o JavaScript inline specifici per la pagina di configurazione dell'amministrazione. Questa è una pratica comune per mantenere il JS separato dalla struttura HTML principale.

#### Modelli front-office (`views/templates/front/`)

L'inventario non elenca alcun modello direttamente sotto `views/templates/front/`. Ciò è coerente con il comportamento del modulo di non visualizzare contenuti del front-office.

#### Modelli di libreria

-   `ordercoupons/lib/emailTemplatesManager/views/buttonManager.tpl`
-   `ordercoupons/lib/emailTemplatesManager/views/createTemplateForm.tpl`
-   `ordercoupons/lib/emailTemplatesManager/views/editTemplateForm.tpl`
-   `ordercoupons/lib/emailTemplatesManager/views/mainForm.tpl`
-   `ordercoupons/lib/emailTemplatesManager/views/selectInput.tpl`
    -   **Scopo:** Questi modelli fanno parte della libreria `emailTemplatesManager` e vengono utilizzati per renderizzare l'interfaccia per la gestione e la modifica dei modelli di email all'interno della configurazione del modulo. `mainForm.tpl` sarebbe probabilmente il punto di ingresso principale, con gli altri che sono parziali per elementi UI specifici.
-   `ordercoupons/lib/searchTool/views/scripts.tpl`
    -   **Scopo:** Un modello per includere file JavaScript o script inline per la libreria `searchTool`, in particolare per la funzionalità di completamento automatico.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

-   **`ps_configuration`**: Il modulo memorizza le sue impostazioni di configurazione (es. `ORDERCOUPONS_ENABLED`, `ORDERCOUPONS_ORDER_STATES`, `ORDERCOUPONS_VOUCHER_VALUE`) nella tabella standard `ps_configuration` di PrestaShop.
-   **`ps_orewards_list` (Tabella personalizzata implicita)**: Basandosi sul fatto che `AdminOrderCouponsRewardsController` gestisce `orewards_list`, è altamente probabile che il modulo crei una tabella di database personalizzata, probabilmente denominata `ps_orewards_list`, per registrare ogni voucher generato.
    -   **Schema (Campi probabili):**
        -   `id_orewards_list` (CHIAVE PRIMARIA, INT)
        -   `id_order` (INT)
        -   `id_customer` (INT)
        -   `customer_email` (VARCHAR)
        -   `order_reference` (VARCHAR)
        -   `reward_code` (VARCHAR)
        -   `date_add` (DATETIME)

#### Tabella degli hook registrati

La descrizione del modulo menziona "Hook Front-Office: Header, Colonne, Prodotto o Footer". Tuttavia, l'inventario dei file e la funzione principale del modulo (invio di voucher via email) suggeriscono che questi probabilmente *non* vengono utilizzati per visualizzare contenuti, ma forse per l'elaborazione interna o il caricamento di risorse se il modulo avesse componenti front-end. Data la natura del modulo, gli hook più critici sono gli hook di azione.

| Nome hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionValidateOrder` | Dopo che un ordine è stato convalidato con successo e salvato nel database. | Questo è l'hook più probabile per il modulo per rilevare nuovi ordini che devono essere elaborati per la generazione del voucher. Il modulo ascolterebbe questo evento per identificare potenziali candidati. |
| `actionOrderStatusPostUpdate` | Dopo che lo stato di un ordine è stato modificato nel Back Office. | Cruciale per il modulo per verificare se un ordine ha raggiunto uno degli "Stati dell'ordine per la generazione del voucher" configurati (es. "Pagamento accettato", "Consegnato"). Qui è dove il cron job probabilmente attiverebbe la logica di generazione del voucher. |
| `displayBackOfficeHeader` | Renderizza il contenuto nella sezione `<head>` del Back Office. | Utilizzato per includere file CSS e JavaScript specifici del modulo per le pagine di configurazione dell'amministrazione e la schermata "Elenco premi". |
| `moduleRoutes` | Consente ai moduli di definire URL amichevoli personalizzati. | Meno probabile per questo modulo, ma possibile se avesse bisogno di una rotta specifica per il suo cron job o altri processi interni. |
| `displayHeader` | Renderizza il contenuto nella sezione `<head>` del front office. | Se il modulo avesse bisogno di caricare JS/CSS globali per potenziali future funzionalità front-end, o per scopi di tracciamento. (Improbabile per la funzionalità attuale). |
| `displayRightColumn` / `displayLeftColumn` | Renderizza il contenuto nelle colonne laterali del front office. | Non utilizzato per la funzionalità attuale di questo modulo. |
| `displayFooter` | Renderizza il contenuto nel piè di pagina del front office. | Non utilizzato per la funzionalità attuale di questo modulo. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Rewards - Codici voucher dopo gli ordini", fai riferimento al tuo account cliente su MyPresta.eu. Puoi scaricare le versioni più recenti dalla cronologia degli ordini e accedere a canali di supporto dedicati per qualsiasi assistenza tecnica o richiesta.
