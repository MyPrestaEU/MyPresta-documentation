---
title: "Vendere CDKey / Chiavi di licenza - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Vendere CDKey / Chiavi di licenza di MyPresta.eu."
sidebar:
  label: "Vendere CDKey / Chiavi di licenza - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Sell CDKeys / License keys su MyPresta.eu](https://mypresta.eu/modules/ordering-process/sell-cdkeys-license-keys.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/sell-cdkeys-license-keys/)
>
> ---


# Vendere CDKey / Chiavi di licenza

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server oltre a un ambiente di hosting PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Vendere CDKey / Chiavi di licenza)

Questa è l'area di configurazione principale in cui definisci come si comporta il modulo, quando inviare le chiavi e le impostazioni generali.

#### Scheda Impostazioni generali

- **Abilitato:**

  - **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare la funzionalità principale del modulo.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il modulo elaborerà gli ordini, invierà le CD key e visualizzerà le chiavi del cliente nel front office in base alle altre impostazioni.
    - *Quando disabilitato:* Il modulo interromperà tutte le sue operazioni. Nessuna chiave verrà inviata automaticamente e la sezione "Le mie chiavi" del cliente potrebbe scomparire o diventare inattiva.
  - **Valore consigliato:** SÌ
  - **Scenario / esempio del commerciante:** Abilitalo una volta che hai configurato tutto per iniziare a vendere chiavi. Disabilitalo temporaneamente se devi eseguire la manutenzione o smettere di vendere chiavi digitali.
- **Seleziona stati dell'ordine:**

  - **Cosa fa questa impostazione:** Determina quali stati dell'ordine attiveranno l'invio automatico delle CD key ai clienti. Puoi selezionare più stati.
  - **Effetto della modifica di questa impostazione:**
    - *Quando viene raggiunto uno stato selezionato:* Il modulo controllerà l'ordine per i prodotti con CD key e invierà le chiavi.
    - *Quando viene raggiunto uno stato non selezionato:* Nessuna chiave verrà inviata, anche se l'ordine contiene prodotti con CD key.
  - **Valore consigliato:** "Pagamento accettato" e potenzialmente "Consegnato" se vuoi assicurarti che anche i prodotti fisici vengano consegnati per primi.
  - **Scenario / esempio del commerciante:** Se vuoi che le chiavi vengano inviate immediatamente dopo il pagamento, seleziona "Pagamento accettato". Se utilizzi un metodo di pagamento manuale come il bonifico bancario, potresti selezionare "Pagamento accettato" dopo aver confermato manualmente il pagamento.
- **Gruppi di clienti autorizzati a ricevere cdkey:**

  - **Cosa fa questa impostazione:** Ti consente di limitare la consegna delle CD key a specifici gruppi di clienti (ad esempio, "Clienti", "Visitatori", "Ospiti").
  - **Effetto della modifica di questa impostazione:**
    - *Quando un cliente è in un gruppo selezionato:* Riceverà le CD key se tutte le altre condizioni sono soddisfatte.
    - *Quando un cliente NON è in un gruppo selezionato:* Non riceverà le CD key, anche se acquista un prodotto con CD key.
  - **Valore consigliato:** "Cliente" (e "Ospite" se consenti il checkout come ospite per i prodotti digitali).
  - **Scenario / esempio del commerciante:** Potresti limitare questo a "Clienti" se vuoi incoraggiare la creazione di account o se hai gruppi B2B speciali che ricevono diversi tipi di chiavi.
- **Valore massimo dell'ordine:**

  - **Cosa fa questa impostazione:** Imposta un limite superiore al valore totale di un ordine per il quale le CD key verranno inviate automaticamente. Gli ordini che superano questo valore non attiveranno la consegna automatica delle chiavi.
  - **Effetto della modifica di questa impostazione:**
    - *Totale ordine inferiore o uguale al massimo:* Le chiavi vengono inviate automaticamente.
    - *Totale ordine superiore al massimo:* Le chiavi NON vengono inviate automaticamente. Dovresti inviarle manualmente.
  - **Valore consigliato:** Lascia vuoto o imposta un valore molto alto (ad esempio, 999999) se non desideri alcuna restrizione di valore.
  - **Scenario / esempio del commerciante:** Usalo come misura di prevenzione delle frodi. Se noti molti ordini fraudolenti di alto valore, potresti impostare un limite per esaminarli manualmente prima di rilasciare chiavi costose.
- **Invia molti codici in una sola mail:**

  - **Cosa fa questa impostazione:** Controlla se più CD key per lo stesso prodotto in un singolo ordine vengono inviate in un'unica email o in email separate.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Se un cliente acquista 3 unità di "Gioco X", riceverà un'email contenente tutte e 3 le chiavi per "Gioco X".
    - *Quando disabilitato:* Se un cliente acquista 3 unità di "Gioco X", riceverà 3 email separate, ciascuna con una chiave per "Gioco X".
  - **Valore consigliato:** SÌ (generalmente migliore per l'esperienza del cliente e riduce l'ingombro della posta elettronica).
  - **Scenario / esempio del commerciante:** Se un cliente acquista un "pacchetto da 4" di un gioco, inviare tutte e 4 le chiavi in un'unica email è molto più chiaro di 4 email separate.
- **Titolo dell'email:**

  - **Cosa fa questa impostazione:** Ti consente di personalizzare l'oggetto dell'email inviata ai clienti contenente le loro CD key.
  - **Effetto della modifica di questa impostazione:** L'oggetto dell'email rifletterà il tuo titolo personalizzato, rendendo più facile per i clienti identificare l'email.
  - **Valore consigliato:** Qualcosa di chiaro e professionale, ad esempio, "Le tue CD Key / Licenze da [Nome del tuo negozio] - Ordine #[ID Ordine]".
  - **Scenario / esempio del commerciante:** Un oggetto chiaro come "Le tue chiavi di gioco per l'ordine #12345" aiuta i clienti a trovare rapidamente le loro chiavi.
- **Cambia stato dell'ordine:**

  - **Cosa fa questa impostazione:** Dopo che le CD key sono state inviate con successo, questa opzione ti consente di cambiare automaticamente lo stato dell'ordine a un nuovo stato specificato.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato e viene selezionato uno stato:* Lo stato dell'ordine si aggiornerà automaticamente (ad esempio, da "Pagamento accettato" a "CD Key inviate").
    - *Quando disabilitato:* Lo stato dell'ordine rimarrà quello che era dopo il trigger iniziale (ad esempio, "Pagamento accettato").
  - **Valore consigliato:** SÌ, e seleziona uno stato distinto come "CD Key inviate" (potrebbe essere necessario creare questo stato in PrestaShop > Stati dell'ordine).
  - **Scenario / esempio del commerciante:** Questo ti aiuta a identificare rapidamente gli ordini per i quali le chiavi sono già state consegnate, migliorando il flusso di lavoro di gestione degli ordini.
- **Seleziona stato dell'ordine (per il cambio di stato):**

  - **Cosa fa questa impostazione:** Se "Cambia stato dell'ordine" è abilitato, questo menu a discesa ti consente di scegliere lo stato specifico dell'ordine da applicare dopo l'invio delle chiavi.
  - **Effetto della modifica di questa impostazione:** Lo stato scelto verrà applicato all'ordine.
  - **Valore consigliato:** Uno stato personalizzato come "CD Key inviate" o "Prodotto digitale consegnato".
  - **Scenario / esempio del commerciante:** La creazione di uno stato specifico come "CD Key inviate" ti consente di filtrare gli ordini e vedere esattamente quali hanno avuto i loro prodotti digitali evasi.
- **Includi chiavi nella fattura:**

  - **Cosa fa questa impostazione:** Determina se le CD key consegnate devono essere stampate anche sulla fattura del cliente.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Le chiavi appariranno sulla fattura PDF generata per l'ordine.
    - *Quando disabilitato:* Le chiavi verranno inviate solo via email e/o appariranno nella sezione "Le mie chiavi", ma non sulla fattura.
  - **Valore consigliato:** SÌ (fornisce un record aggiuntivo per il cliente).
  - **Scenario / esempio del commerciante:** Alcuni clienti preferiscono avere tutti i dettagli dell'acquisto, comprese le chiavi, sulla loro fattura per la tenuta dei registri o per scopi fiscali.
- **Attiva paginazione:**

  - **Cosa fa questa impostazione:** Abilita la paginazione per l'elenco delle CD key visualizzate nella sezione "Le mie chiavi" del cliente nel front office.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Se un cliente ha molte chiavi, verranno visualizzate su più pagine, migliorando i tempi di caricamento e la leggibilità.
    - *Quando disabilitato:* Tutte le chiavi verranno elencate su una singola pagina.
  - **Valore consigliato:** SÌ (specialmente se i clienti potrebbero accumulare molte chiavi).
  - **Scenario / esempio del commerciante:** Un cliente che acquista regolarmente chiavi di gioco apprezzerà la paginazione per trovare rapidamente chiavi specifiche senza scorrere un elenco molto lungo.
- **Numero di elementi per paginazione:**

  - **Cosa fa questa impostazione:** Se la paginazione è abilitata, imposta quante CD key vengono visualizzate per pagina nella sezione "Le mie chiavi" del cliente.
  - **Effetto della modifica di questa impostazione:** Controlla la densità dell'elenco delle chiavi su ogni pagina.
  - **Valore consigliato:** 10-20 (un buon equilibrio per la leggibilità).
  - **Scenario / esempio del commerciante:** Impostando questo a 15 significa che un cliente con 30 chiavi vedrà 2 pagine di chiavi.

#### Scheda Impostazioni importazione CSV

- **Delimitatore di riga del file CSV:**

  - **Cosa fa questa impostazione:** Specifica il carattere utilizzato per separare le singole righe (linee) nel tuo file CSV durante l'importazione delle CD key.
  - **Effetto della modifica di questa impostazione:** Il modulo utilizza questo carattere per analizzare correttamente il tuo file CSV in singole voci di chiave. Un delimitatore errato porterà a errori di importazione.
  - **Valore consigliato:** `\n` (carattere di nuova riga, standard per la maggior parte dei file CSV).
  - **Scenario / esempio del commerciante:** Se il tuo elenco di chiavi è `chiave1\nchiave2\nchiave3`, il modulo deve sapere che `\n` separa ogni chiave.
- **Delimitatore di colonna del file CSV:**

  - **Cosa fa questa impostazione:** Specifica il carattere utilizzato per separare le colonne (campi) all'interno di ogni riga del tuo file CSV durante l'importazione delle CD key.
  - **Effetto della modifica di questa impostazione:** Il modulo utilizza questo carattere per identificare correttamente i diversi punti dati (ad esempio, chiave, ID gruppo) all'interno di ogni riga. Un delimitatore errato porterà a errori di importazione.
  - **Valore consigliato:** `;` (punto e virgola) o `,` (virgola), a seconda di come vengono generati i tuoi file CSV.
  - **Scenario / esempio del commerciante:** Se il tuo CSV è `chiave1;id_prodotto_1;id_gruppo_1`, il modulo deve sapere che `;` separa i campi.

#### Scheda Analisi e Frodi

- **CDKEYS\_ANALYTICS\_DEFAULT\_CHART, CDKEYS\_ANALYTICS\_PERIOD, CDKEYS\_ANALYTICS\_CHART\_DAYS, CDKEYS\_ANALYTICS\_CHART\_WEEKS, CDKEYS\_ANALYTICS\_CHART\_MONTHS, CDKEYS\_ANALYTICS\_PREDICTION\_DAYS, CDKEYS\_ANALYTICS\_TOP\_LIMIT, CDKEYS\_ANALYTICS\_MIN\_SALES, CDKEYS\_ANALYTICS\_SHOW\_EMPTY\_GROUPS, CDKEYS\_ANALYTICS\_INCLUDE\_INACTIVE:**

  - **Cosa fanno queste impostazioni:** Queste sono chiavi di configurazione interne relative al dashboard di analisi e rilevamento frodi del modulo. Controllano come i dati vengono visualizzati, aggregati e filtrati all'interno della sezione di analisi del back-office del modulo.
  - **Effetto della modifica di queste impostazioni:** Regola la rappresentazione visiva e i punti dati mostrati nel dashboard del modulo, aiutandoti a monitorare le vendite chiave e i potenziali schemi di frode.
  - **Valore consigliato:** I valori predefiniti sono solitamente adeguati. Modifica solo se hai bisogno di viste di reporting specifiche.
  - **Scenario / esempio del commerciante:** Potresti regolare `CDKEYS_ANALYTICS_PERIOD` per visualizzare le tendenze di vendita in una settimana anziché in un mese, o `CDKEYS_ANALYTICS_TOP_LIMIT` per vedere più gruppi di chiavi più venduti.
- **CDKEYS\_ALERT\_COOLDOWN\_HOURS:**

  - **Cosa fa questa impostazione:** Definisce un periodo di raffreddamento in ore per gli avvisi di frode. Se un avviso viene attivato per un cliente, un altro avviso per lo stesso cliente non verrà attivato entro questo periodo di raffreddamento.
  - **Effetto della modifica di questa impostazione:** Previene lo spam di avvisi per tentativi fraudolenti ripetuti dallo stesso cliente in un breve lasso di tempo.
  - **Valore consigliato:** 24-48 ore (per consentire il tempo per la revisione manuale senza continui ri-avvisi).
  - **Scenario / esempio del commerciante:** Se un cliente tenta più ordini fraudolenti entro un'ora, questo ti impedisce di ricevere un avviso per ogni tentativo, consolidandolo in un unico avviso iniziale.
- **CDKEYS\_EXPORT\_MASK\_CODES:**

  - **Cosa fa questa impostazione:** Quando si esportano i dati delle CD key, questa impostazione determina se i codici chiave effettivi devono essere mascherati (nascosti) per motivi di sicurezza.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I dati esportati mostreranno codici mascherati (ad esempio, `*****`).
    - *Quando disabilitato:* I dati esportati mostreranno i codici chiave completi e non mascherati.
  - **Valore consigliato:** SÌ (per sicurezza, specialmente se si condividono file di esportazione).
  - **Scenario / esempio del commerciante:** Se devi condividere un elenco di chiavi utilizzate con un fornitore ma non vuoi esporre i valori effettivi delle chiavi, abilita la mascheratura.

### 2.2 Schermate di amministrazione dedicate e viste del controller

Il modulo aggiunge diverse nuove sezioni al menu del tuo Back Office di PrestaShop, tipicamente sotto una scheda principale "CD Keys" o "Licenze".

#### 2.2.1 CD Keys > Gruppi (AdminCdKeysGroupsController)

- **Nome schermata e posizione menu:** **Back Office > CD Keys > Gruppi**
- **Scopo:** Questa schermata ti consente di creare e gestire gruppi di CD key. Un gruppo è essenzialmente un pool di chiavi che possono essere assegnate a uno o più prodotti. Questo è fondamentale per gestire il tuo inventario di chiavi.
- **Azioni e impostazioni disponibili:**
  - **Aggiungi nuovo gruppo:** Crea un nuovo gruppo con un nome (ad esempio, "Chiavi Windows 11 Pro", "Gioco X Edizione Deluxe").
  - **Modifica gruppo:** Modifica il nome di un gruppo esistente.
  - **Elimina gruppo:** Rimuovi un gruppo (assicurati che nessun prodotto attivo sia collegato ad esso e che nessuna chiave sia assegnata).
  - **Visualizza chiavi nel gruppo:** Naviga direttamente all'elenco delle chiavi associate a un gruppo specifico.
- **Effetto delle modifiche:**
  - La creazione di un gruppo ti consente di categorizzare le tue chiavi e collegarle ai prodotti.
  - L'eliminazione di un gruppo rimuoverà la sua associazione con prodotti e chiavi, causando potenzialmente problemi se le chiavi sono ancora necessarie.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1. Prima di importare qualsiasi chiave, crea un gruppo per ogni prodotto distinto o versione di un prodotto che richiede una chiave.
  2. Assegna il gruppo appropriato ai tuoi prodotti (questo viene fatto nella pagina di modifica del prodotto, sotto la scheda "Moduli" o una scheda dedicata "CD Keys" aggiunta dal modulo).

#### 2.2.2 CD Keys > Elenco (AdminCdKeysListController)

- **Nome schermata e posizione menu:** **Back Office > CD Keys > Elenco**
- **Scopo:** Questo è il tuo inventario centrale per tutte le singole CD key. Qui puoi importare, visualizzare e gestire lo stato di ogni chiave.
- **Azioni e impostazioni disponibili:**
  - **Importa CSV:** Carica un file CSV contenente le tue chiavi. Specificherai il gruppo a cui appartengono queste chiavi durante il processo di importazione.
  - **Aggiungi nuova chiave:** Aggiungi manualmente una singola chiave, assegnale un gruppo e impostane lo stato (ad esempio, "Disponibile", "Usata").
  - **Modifica chiave:** Modifica il valore, il gruppo o lo stato di una chiave esistente.
  - **Elimina chiave:** Rimuovi una chiave dall'inventario.
  - **Filtra/Cerca:** Trova chiavi specifiche per valore, gruppo o stato.
  - **Esporta:** Esporta il tuo inventario di chiavi (con mascheratura opzionale).
- **Effetto delle modifiche:**
  - L'importazione delle chiavi popola il tuo inventario, rendendole disponibili per la vendita.
  - La modifica dello stato di una chiave (ad esempio, a "Usata") impedisce che venga assegnata a nuovi ordini.
  - L'eliminazione di una chiave la rimuove permanentemente.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1. Importa regolarmente nuovi lotti di chiavi dai tuoi fornitori nei rispettivi gruppi.
  2. Monitora lo stato "Usata" per assicurarti che le chiavi vengano assegnate correttamente.
  3. Se un cliente segnala un problema con una chiave, puoi trovarla qui, verificarne lo stato e potenzialmente assegnarne una nuova.

#### 2.2.3 CD Keys > Archivio (AdminCdKeysArchiveController)

- **Nome schermata e posizione menu:** **Back Office > CD Keys > Archivio**
- **Scopo:** Questa schermata fornisce una registrazione storica di tutte le CD key che sono state assegnate agli ordini dei clienti. Funge da registro di controllo per la distribuzione delle chiavi.
- **Azioni e impostazioni disponibili:**
  - **Visualizza chiavi assegnate:** Vedi quale chiave è stata assegnata a quale ordine, per quale prodotto e a quale cliente.
  - **Filtra/Cerca:** Trova chiavi archiviate specifiche per ID ordine, nome cliente, prodotto o valore chiave.
  - **Reinvia email:** Opzione per reinviare l'email della CD key al cliente (utile se affermano di non averla ricevuta).
- **Effetto delle modifiche:** Questa schermata è principalmente per la visualizzazione e l'audit. Le azioni qui non modificano lo stato delle chiavi nella sezione "Elenco" ma consentono azioni di supporto clienti come il reinvio di email.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1. Usa questa schermata per cercare rapidamente le chiavi acquistate da un cliente se contatta il supporto.
  2. Verifica che le chiavi siano state inviate correttamente per ordini specifici.
  3. Reinvia le chiavi se l'email di un cliente è stata persa o cancellata accidentalmente.

#### 2.2.4 Pagina di modifica del prodotto (Back Office > Catalogo > Prodotti > Modifica prodotto)

- **Nome schermata e posizione menu:** Quando modifichi un prodotto, cerca una nuova scheda o sezione relativa a "CD Keys" o "Moduli".
- **Scopo:** Qui colleghi un prodotto specifico a un gruppo di CD key, contrassegnandolo come "prodotto CD Key".
- **Azioni e impostazioni disponibili:**
  - **Abilita CD Key per questo prodotto:** Un interruttore o una casella di controllo per indicare che questo prodotto richiede la consegna di una CD key.
  - **Seleziona Gruppo CD Key:** Un menu a discesa per scegliere da quale gruppo di chiavi questo prodotto dovrebbe attingere quando viene effettuato un ordine.
- **Effetto delle modifiche:**
  - *Quando abilitato e viene selezionato un gruppo:* Qualsiasi acquisto di questo prodotto attiverà automaticamente il modulo per assegnare una chiave disponibile dal gruppo scelto e inviarla al cliente.
  - *Quando disabilitato:* Il prodotto verrà trattato come un normale prodotto PrestaShop e nessuna chiave verrà assegnata o inviata.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1. Per ogni prodotto digitale che vendi che richiede una chiave unica, vai alla sua pagina di modifica.
  2. Abilita l'opzione CD Key e seleziona il gruppo di chiavi corretto che hai creato in precedenza.
  3. Assicurati di avere abbastanza chiavi nel gruppo selezionato per coprire le potenziali vendite.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Configurazione modulo** | Abilitato | SÌ | Interruttore principale per la funzionalità del modulo. |
| | Seleziona stati dell'ordine | Pagamento accettato | Attiva la consegna delle chiavi quando l'ordine raggiunge questo stato. |
| | Gruppi di clienti autorizzati a ricevere cdkey | Cliente, Ospite | Limita la consegna delle chiavi a gruppi di clienti specificati. |
| | Valore massimo dell'ordine | Vuoto (nessun limite) | Imposta un limite di valore per la consegna automatica delle chiavi (prevenzione frodi). |
| | Invia molti codici in una sola mail | SÌ | Raggruppa più chiavi per lo stesso prodotto in un'unica email. |
| | Titolo dell'email | Le tue CD Key da [Nome negozio] | Personalizza l'oggetto delle email di consegna delle chiavi. |
| | Cambia stato dell'ordine | SÌ | Aggiorna automaticamente lo stato dell'ordine dopo la consegna delle chiavi. |
| | Seleziona stato dell'ordine (per il cambio di stato) | "CD Key inviate" (personalizzato) | Lo stato specifico da applicare dopo l'invio delle chiavi. |
| | Includi chiavi nella fattura | SÌ | Stampa le chiavi consegnate sulla fattura PDF del cliente. |
| | Attiva paginazione | SÌ | Abilita la paginazione per "Le mie chiavi" nell'account cliente. |
| | Numero di elementi per paginazione | 10-20 | Numero di chiavi visualizzate per pagina in "Le mie chiavi". |
| | Delimitatore di riga del file CSV | `\n` | Carattere che separa le righe nell'importazione delle chiavi CSV. |
| | Delimitatore di colonna del file CSV | `;` o `,` | Carattere che separa le colonne nell'importazione delle chiavi CSV. |
| | CDKEYS\_EXPORT\_MASK\_CODES | SÌ | Maschera i codici chiave nei file di esportazione per sicurezza. |
| **CD Keys > Gruppi** | Aggiungi/Modifica nome gruppo | N/A | Gestisce categorie/pool di chiavi. |
| **CD Keys > Elenco** | Importa CSV | N/A | Carica in blocco le chiavi nei gruppi. |
| | Aggiungi/Modifica chiave | N/A | Gestisce manualmente i valori e lo stato delle singole chiavi. |
| **CD Keys > Archivio** | Reinvia email | N/A | Reinvia l'email di consegna della chiave per un ordine specifico. |
| **Pagina di modifica del prodotto** | Abilita CD Key per questo prodotto | SÌ | Contrassegna un prodotto come richiedente la consegna di una CD key. |
| | Seleziona Gruppo CD Key | (Gruppo specifico) | Collega il prodotto a un pool di chiavi per l'evasione. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei clienti non ricevono le loro CD key. Cosa dovrei controllare per primo?**
R1:

1.  **Modulo abilitato?** Vai su `Moduli > Gestione moduli > Vendere CDKey / Chiavi di licenza` e assicurati che il modulo sia "Abilitato".
2.  **Stato dell'ordine:** Controlla la configurazione del tuo modulo sotto "Seleziona stati dell'ordine". Lo stato attuale dell'ordine del cliente (ad esempio, "Pagamento accettato") è selezionato in questo elenco?
3.  **Prodotto collegato al gruppo:** Nella pagina di modifica del prodotto (`Catalogo > Prodotti > Modifica prodotto`), assicurati che "Abilita CD Key per questo prodotto" sia selezionato e che il "Gruppo CD Key" corretto sia selezionato.
4.  **Chiavi nel gruppo:** Vai su `CD Keys > Elenco` e controlla se ci sono chiavi disponibili (non utilizzate) nel gruppo assegnato al prodotto. In caso contrario, importa più chiavi.
5.  **Gruppo cliente:** Verifica che il gruppo del cliente sia autorizzato a ricevere chiavi sotto "Gruppi di clienti autorizzati a ricevere cdkey" nella configurazione del modulo.
6.  **Configurazione email:** Controlla le impostazioni email del tuo PrestaShop (`Parametri avanzati > E-mail`) per assicurarti che le email vengano inviate correttamente dal tuo negozio. Inoltre, chiedi al cliente di controllare la sua cartella spam/posta indesiderata.

**D2: Ho importato un file CSV, ma le chiavi non vengono visualizzate o sono errate.**
R2:

1.  **Impostazioni delimitatore:** Ricontrolla le impostazioni "Delimitatore di riga del file CSV" e "Delimitatore di colonna del file CSV" nella configurazione del modulo. Devono corrispondere esattamente alla struttura del tuo file CSV. Problemi comuni sono l'uso della virgola (`,`) invece del punto e virgola (`;`) o viceversa.
2.  **Formato file:** Assicurati che il tuo file CSV sia testo normale, non un file Excel salvato come CSV con formattazione complessa.
3.  **Gruppo target:** Hai selezionato il Gruppo CD Key corretto durante il processo di importazione?

**D3: La sezione "Le mie chiavi" non appare nell'account del cliente.**
R3:

1.  **Modulo abilitato:** Assicurati che il modulo sia attivo.
2.  **Compatibilità tema:** Sebbene il modulo utilizzi hook PrestaShop standard, alcuni temi pesantemente personalizzati potrebbero sovrascrivere l'hook `displayCustomerAccount` predefinito. Controlla se il tuo tema ha modificato quest'area. In tal caso, potrebbero essere necessarie piccole modifiche al tema (fare riferimento alla Sezione 7.6 per i modelli di hook).
3.  **Cache:** Svuota la cache del tuo PrestaShop (`Parametri avanzati > Prestazioni > Svuota cache`).

**D4: Come si crea un nuovo stato dell'ordine come "CD Key inviate"?**
R4:

1.  Vai su `Parametri negozio > Impostazioni ordine > Stati`.
2.  Clicca su "Aggiungi nuovo stato dell'ordine".
3.  Assegnagli un nome chiaro (ad esempio, "CD Key inviate").
4.  Scegli un colore distinto (ad esempio, azzurro) per identificarlo facilmente nel tuo elenco ordini.
5.  Assicurati che "Considera l'ordine associato come convalidato" sia selezionato se vuoi che venga conteggiato come un ordine completato.
6.  Salva il nuovo stato, quindi torna alla configurazione del modulo per selezionarlo per "Seleziona stato dell'ordine (per il cambio di stato)".

**D5: Posso assegnare manualmente una chiave a un ordine o a un cliente?**
R5: Il modulo automatizza principalmente questo. Se hai bisogno di assegnare manualmente una chiave (ad esempio, per una sostituzione), in genere dovresti:

1.  Vai su `CD Keys > Elenco`, trova una chiave disponibile e annota il suo valore.
2.  Vai all'ordine del cliente (`Ordini > Ordini`) e aggiungi una nota privata con la chiave.
3.  Invia manualmente la chiave via email al cliente.
4.  Quindi, torna su `CD Keys > Elenco`, trova quella chiave e cambia manualmente il suo stato in "Usata" per evitare che venga assegnata di nuovo.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce un'analisi approfondita della struttura tecnica del modulo "Vendere CDKey / Chiavi di licenza", destinata a sviluppatori, webmaster e agenzie tecniche.

### 4.1 Panoramica dell'architettura

Il modulo segue un modello MVC (Model-View-Controller) standard di PrestaShop. Estende `Module` per la sua funzionalità principale e `AdminController` per le sue interfacce di Back Office. Sfrutta `ObjectModel` di PrestaShop per la gestione dei gruppi di CD key, delle singole chiavi e della loro cronologia di utilizzo. La consegna delle chiavi è principalmente basata su eventi, attivata dagli hook `actionOrderStatusPostUpdate` e `actionOrderStatusUpdate`. L'interazione con il front-office è minima, fornendo principalmente una sezione "Le mie chiavi" rivolta al cliente.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

- `controllers/front/index.php`:
  - **Nome classe:** `CdkeysIndexModuleFrontController` (estende `ModuleFrontController`)
  - **Responsabilità:** Probabilmente un segnaposto o un controller di reindirizzamento. In molti moduli, `index.php` nella directory del controller frontale potrebbe gestire il routing predefinito o semplicemente reindirizzare a un controller più specifico.
- `controllers/front/mykeys.php`:
  - **Nome classe:** `CdkeysMykeysModuleFrontController` (estende `ModuleFrontController`)
  - **Responsabilità:** Gestisce la visualizzazione delle CD key acquistate dal cliente nella sezione "Il mio account". Recupera i record `cdkey_used` associati al cliente corrente, applica la paginazione se abilitata e renderizza `views/templates/front/mykeys.tpl`.

#### Controller Admin Back-Office

- `controllers/admin/AdminCdKeysArchiveController.php`:
  - **Nome scheda:** CD Keys > Archivio
  - **Entità gestita:** `cdkey_used` (registri delle chiavi assegnate)
  - **Responsabilità:** Fornisce un'interfaccia di gestione dell'elenco per tutte le CD key che sono state assegnate agli ordini. Consente la visualizzazione, il filtraggio e potenzialmente il reinvio delle email delle chiavi. Utilizza `HelperList` per la sua visualizzazione.
- `controllers/admin/AdminCdKeysGroupsController.php`:
  - **Nome scheda:** CD Keys > Gruppi
  - **Entità gestita:** `cdkey_group`
  - **Responsabilità:** Gestisce la creazione, la modifica e l'eliminazione dei gruppi di CD key. Questi gruppi fungono da categorie per le tue chiavi e sono collegati ai prodotti. Utilizza `HelperList` e `HelperForm` per le sue interfacce.
- `controllers/admin/AdminCdKeysListController.php`:
  - **Nome scheda:** CD Keys > Elenco
  - **Entità gestita:** `cdkey`
  - **Responsabilità:** Gestisce l'inventario delle singole CD key. Ciò include l'importazione di file CSV, l'aggiunta/modifica/eliminazione di chiavi e la visualizzazione del loro stato (disponibile, usata). Utilizza `HelperList` e `HelperForm`.
- `controllers/admin/index.php`:
  - **Nome scheda:** CD Keys (Dashboard principale)
  - **Entità gestita:** N/A (Dashboard)
  - **Responsabilità:** Questo probabilmente funge da dashboard principale per il modulo, visualizzando analisi, statistiche chiave e potenzialmente avvisi di frode. Aggrega i dati dalle tabelle `cdkey_used` e `cdkey`.

### 4.3 Classi e modelli principali (`classes/`)

Il dossier del modulo non indica una directory `classes/` esplicita. Ciò suggerisce che le definizioni `ObjectModel` primarie e la logica di business principale sono probabilmente incapsulate nel file `cdkeys.php` stesso, o all'interno dei rispettivi file controller.

Se le definizioni `ObjectModel` sono presenti in `cdkeys.php`, tipicamente apparirebbero come:

- `CdKeyGroup` (per la tabella `ps_cdkey_group`): Gestisce i gruppi di chiavi.
  - `$definition` includerebbe `id_cdkey_group`, `name`.
- `CdKey` (per la tabella `ps_cdkey`): Gestisce le singole chiavi.
  - `$definition` includerebbe `id_cdkey`, `id_cdkey_group`, `key_value`, `status` (ad esempio, 'available', 'used').
- `CdKeyUsed` (per la tabella `ps_cdkey_used`): Gestisce le chiavi assegnate.
  - `$definition` includerebbe `id_cdkey_used`, `id_cdkey`, `id_order`, `id_customer`, `id_product`, `date_add`.

### 4.4 Risorse JavaScript (`views/js/`)

- `cdkeys/lib/emailTemplatesManager/js/emailTemplatesManager.js`:
  - **Ambito:** Back-office.
  - **Responsabilità:** Gestisce l'interfaccia utente per la creazione, la modifica e la selezione dei modelli di email all'interno della configurazione del modulo. Probabilmente gestisce le chiamate AJAX per salvare il contenuto del modello, visualizzare in anteprima le email e passare tra diverse versioni del modello.
- `cdkeys/lib/searchTool/views/js/autocomplete.js`:
  - **Ambito:** Back-office.
  - **Responsabilità:** Fornisce la funzionalità di completamento automatico per i campi di ricerca all'interno delle interfacce di amministrazione del modulo (ad esempio, ricerca di prodotti, clienti o gruppi di chiavi). Si lega ai campi di input ed effettua richieste AJAX per recuperare suggerimenti.
- `cdkeys/views/js/adminCdKeysDashboard.js`:
  - **Ambito:** Back-office (AdminCdKeysDashboardController o dashboard principale del modulo).
  - **Responsabilità:** Alimenta gli elementi interattivi del dashboard principale del modulo. Ciò potrebbe includere il rendering di grafici (ad esempio, utilizzando Chart.js o una libreria simile), il filtraggio dei dati e gli aggiornamenti dinamici delle statistiche.
- `cdkeys/views/js/cdkeys-dashboard-demo-console.js`:
  - **Ambito:** Back-office.
  - **Responsabilità:** Probabilmente uno script di sviluppo/debug o una console demo per il dashboard, che potrebbe registrare eventi o fornire dati di test. Non dovrebbe essere attivo in produzione.
- `cdkeys/views/js/cdkeys-fraud-demo-console.js`:
  - **Ambito:** Back-office.
  - **Responsabilità:** Simile alla console demo del dashboard, questo è probabilmente uno script di sviluppo/debug per le funzionalità di rilevamento delle frodi. Non dovrebbe essere attivo in produzione.
- `cdkeys/views/js/cdkeys-pagination.js`:
  - **Ambito:** Front-office (`mykeys.tpl`).
  - **Responsabilità:** Gestisce la logica lato client per la paginazione nella sezione "Le mie chiavi" del cliente. Ciò potrebbe comportare chiamate AJAX per caricare nuove pagine di chiavi senza un ricaricamento completo della pagina, o semplicemente la gestione della visualizzazione dei numeri di pagina e della navigazione.

### 4.5 Fogli di stile CSS (`views/css/`)

- `cdkeys/lib/emailTemplatesManager/css/emailTemplatesManager.css`:
  - **Ambito:** Back-office.
  - **Componenti UI principali:** Stila l'interfaccia di gestione dei modelli di email, inclusi moduli, pulsanti e aree di anteprima.
  - **Selettori di classe CSS chiave:** `.email-template-manager`, `.template-form`, `.template-preview`.
- `cdkeys/lib/searchTool/views/css/autocomplete.css`:
  - **Ambito:** Back-office.
  - **Componenti UI principali:** Stila i menu a discesa di completamento automatico e i campi di input.
  - **Selettori di classe CSS chiave:** `.autocomplete-suggestions`, `.autocomplete-selected`, `.autocomplete-suggestion`.
- `cdkeys/views/css/admin_cdkeys.css`:
  - **Ambito:** Back-office.
  - **Componenti UI principali:** Stile generale per le pagine di amministrazione del modulo, inclusi elenchi, moduli ed elementi del dashboard.
  - **Selettori di classe CSS chiave:** `.cdkeys-admin-panel`, `.cdkeys-table`, `.cdkeys-form-group`.
- `cdkeys/views/css/cdkeys-admin.css`:
  - **Ambito:** Back-office.
  - **Componenti UI principali:** Stile aggiuntivo o specifico per le interfacce di amministrazione, potenzialmente sovrascrivendo o estendendo `admin_cdkeys.css`.
  - **Selettori di classe CSS chiave:** `.cdkeys-dashboard-widget`, `.cdkeys-alert`.
- `cdkeys/views/css/css.css`:
  - **Ambito:** Potenzialmente sia Front-office che Back-office, o stili di utilità generali.
  - **Componenti UI principali:** Potrebbe contenere stili di base per elementi utilizzati in diverse parti del modulo.
  - **Selettori di classe CSS chiave:** Classi generiche che potrebbero essere applicate a vari elementi del modulo.

### 4.6 Struttura del template Smarty (`views/templates/`)

#### Template hook (`views/templates/hook/`)

- `cdkeys/views/templates/hook/adminOrder.tpl`:
  - **Hook:** `displayAdminOrder`
  - **Output:** Visualizza le informazioni sulle CD key direttamente nella pagina dei dettagli dell'ordine del Back Office di PrestaShop. Ciò consente agli amministratori di vedere rapidamente quali chiavi sono state assegnate a un ordine.
- `cdkeys/views/templates/hook/adminOrderFraud.tpl`:
  - **Hook:** `displayAdminOrderTop` (o simile, potenzialmente `displayAdminOrder`)
  - **Output:** Visualizza informazioni o avvisi relativi alle frodi per un ordine nella pagina dei dettagli dell'ordine del Back Office.
- `cdkeys/views/templates/hook/my-account-16.tpl`:
  - **Hook:** `displayCustomerAccount` (per PrestaShop 1.6.x)
  - **Output:** Aggiunge un link o un blocco alla pagina "Il mio account" del cliente, indirizzandolo alla sezione "Le mie chiavi".
- `cdkeys/views/templates/hook/my-account-17.tpl`:
  - **Hook:** `displayCustomerAccount` (per PrestaShop 1.7.x, 8.x, 9.x)
  - **Output:** Simile a `my-account-16.tpl`, ma adattato per la diversa struttura del template delle versioni più recenti di PrestaShop, aggiungendo un link alla sezione "Le mie chiavi".
- `cdkeys/views/templates/hook/orderDetailDisplayed.tpl`:
  - **Hook:** `displayOrderDetailDisplayed`
  - **Output:** Visualizza le informazioni sulle CD key nella pagina dei dettagli dell'ordine del front-office del cliente.

#### Template admin (`views/templates/admin/`)

- `cdkeys/lib/emailTemplatesManager/views/buttonManager.tpl`:
  - **Scopo:** Renderizza pulsanti o controlli per il gestore dei modelli di email.
- `cdkeys/lib/emailTemplatesManager/views/createTemplateForm.tpl`:
  - **Scopo:** Renderizza il modulo per la creazione di nuovi modelli di email.
- `cdkeys/lib/emailTemplatesManager/views/editTemplateForm.tpl`:
  - **Scopo:** Renderizza il modulo per la modifica di modelli di email esistenti.
- `cdkeys/lib/emailTemplatesManager/views/mainForm.tpl`:
  - **Scopo:** Il contenitore principale o il modulo per l'interfaccia di gestione dei modelli di email.
- `cdkeys/lib/emailTemplatesManager/views/selectInput.tpl`:
  - **Scopo:** Renderizza un input a discesa di selezione, probabilmente per la scelta di modelli di email o lingue.
- `cdkeys/lib/searchTool/views/scripts.tpl`:
  - **Scopo:** Include script JavaScript per la funzionalità di ricerca/completamento automatico.
- `cdkeys/views/templates/admin/cdkeys/helpers/list/list_action_email.tpl`:
  - **Scopo:** Renderizza un pulsante di azione specifico (ad esempio, "Reinvia email") all'interno di una tabella `HelperList` nei controller di amministrazione (ad esempio, `AdminCdKeysArchiveController`).
- `cdkeys/views/templates/admin/customerGroups.tpl`:
  - **Scopo:** Renderizza l'interfaccia di selezione del gruppo di clienti nella configurazione del modulo.
- `cdkeys/views/templates/admin/getCombinations.tpl`:
  - **Scopo:** Potenzialmente utilizzato per visualizzare o selezionare combinazioni di prodotti relative alle CD key (ad esempio, se diverse combinazioni richiedono diversi gruppi di chiavi).
- `cdkeys/views/templates/admin/orderstates.tpl`:
  - **Scopo:** Renderizza il menu a discesa a selezione multipla per "Seleziona stati dell'ordine" nella configurazione del modulo.
- `cdkeys/views/templates/admin/orderstatesRadio.tpl`:
  - **Scopo:** Renderizza la selezione del pulsante radio per "Seleziona stato dell'ordine" (per il cambio di stato) nella configurazione del modulo.
- `cdkeys/views/templates/admin/script.tpl`:
  - **Scopo:** Inclusione generale di script per le pagine di amministrazione, possibilmente per JS specifico del modulo.

#### Template front-office (`views/templates/front/`)

- `cdkeys/views/templates/front/mykeys.tpl`:
  - **Scopo:** Il template principale per la visualizzazione dell'elenco delle CD key acquistate dal cliente nella sezione "Il mio account". Itererà i dati `cdkey_used` e presenterà le chiavi, i dettagli dell'ordine e potenzialmente i controlli di paginazione.

#### Template email (`views/templates/email/`)

- `cdkeys/views/templates/email/multikey-instance.tpl`:
  - **Scopo:** Questo è il template principale per l'email inviata ai clienti contenente le loro CD key. Si popolerà dinamicamente con il nome del cliente, i dettagli dell'ordine e la/e chiave/i effettiva/e.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

- `ps_cdkey_group`: Memorizza le informazioni sui gruppi di CD key.
  - `id_cdkey_group` (PK)
  - `name`
  - `date_add`
  - `date_upd`
- `ps_cdkey`: Memorizza le singole CD key.
  - `id_cdkey` (PK)
  - `id_cdkey_group` (FK a `ps_cdkey_group`)
  - `key_value` (la stringa della CD key effettiva)
  - `status` (ad esempio, 'available', 'used')
  - `date_add`
  - `date_upd`
- `ps_cdkey_used`: Memorizza i record delle CD key assegnate agli ordini.
  - `id_cdkey_used` (PK)
  - `id_cdkey` (FK a `ps_cdkey`)
  - `id_order` (FK a `ps_orders`)
  - `id_customer` (FK a `ps_customer`)
  - `id_product` (FK a `ps_product`)
  - `date_add`

#### Record di configurazione (`ps_configuration`)

- `CDKEYS_ENABLED`: (bool) Interruttore principale.
- `CDKEYS_OSTATES`: (string) Elenco di stati dell'ordine separati da virgole per la consegna delle chiavi.
- `CDKEYS_GROUPS`: (string) Elenco di gruppi di clienti separati da virgole per la consegna delle chiavi.
- `CDKEYS_MAX_ORDERTOTAL`: (float) Valore massimo dell'ordine per la consegna automatica.
- `CDKEY_HOWDELIVER`: (bool) Invia molti codici in una sola mail.
- `CDKEYS_MULTITITLE`: (string) Titolo dell'oggetto dell'email.
- `CDKEY_STATUSCHANGE`: (bool) Cambia lo stato dell'ordine dopo la consegna.
- `CDKEYS_OSTATES_RADIO`: (int) ID dello stato dell'ordine in cui cambiare.
- `CDKEY_INC_INV`: (bool) Includi le chiavi nella fattura.
- `CDKEY_PAGINATION`: (bool) Abilita la paginazione per Le mie chiavi.
- `CDKEY_PAGINATION_NB`: (int) Elementi per pagina per la paginazione Le mie chiavi.
- `IV_ROW_DELIMITER`: (string) Delimitatore di riga CSV.
- `IV_COL_DELIMITER`: (string) Delimitatore di colonna CSV.
- `CDKEYS_ANALYTICS_*`: Varie impostazioni per l'analisi del dashboard.
- `CDKEYS_ALERT_COOLDOWN_HOURS`: (int) Periodo di raffreddamento per gli avvisi di frode.
- `CDKEYS_EXPORT_MASK_CODES`: (bool) Maschera i codici all'esportazione.

#### Tabella degli hook registrati

| Nome hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionOrderStatusPostUpdate` | Dopo che lo stato di un ordine è stato aggiornato (e salvato). | Trigger principale per la consegna delle CD key. Controlla se il nuovo stato corrisponde agli stati configurati e invia le chiavi. |
| `displayAdminOrder` | Renderizza il contenuto all'interno della pagina dei dettagli dell'ordine del Back Office. | Visualizza le CD key assegnate per l'ordine corrente nel pannello di amministrazione. |
| `ActionAdminControllerSetMedia` | Quando un controller admin viene inizializzato e i media (JS/CSS) vengono impostati. | Inietta file JS e CSS specifici del modulo nel Back Office per i controller admin. |
| `displayCustomerAccount` | Renderizza il contenuto nella pagina "Il mio account" del cliente. | Aggiunge un link o un blocco per "Le mie chiavi" nell'account front office del cliente. |
| `DisplayAdminOrderTop` | Renderizza il contenuto nella parte superiore della pagina dei dettagli dell'ordine del Back Office. | Potenzialmente utilizzato per visualizzare avvisi di frode o informazioni di riepilogo relative alle CD key per l'ordine. |
| `actionOrderStatusUpdate` | Prima che lo stato di un ordine venga aggiornato (hook più vecchio, `actionOrderStatusPostUpdate` è preferito). | Trigger secondario o di fallback per la consegna delle CD key, garantendo la compatibilità con le versioni precedenti di PrestaShop o scenari specifici. |
| `DisplayBackOfficeHeader` | Renderizza il contenuto nell'intestazione di tutte le pagine del Back Office. | Inietta JS/CSS globale del Back Office o voci di menu per il modulo. |
| `displayHeader` | Renderizza il contenuto nella sezione `<head>` delle pagine del front-office. | Inietta JS/CSS specifico del front-office o meta tag. |
| `displayOrderDetailDisplayed` | Renderizza il contenuto all'interno della pagina dei dettagli dell'ordine del front-office del cliente. | Visualizza le CD key assegnate direttamente nella pagina di riepilogo dell'ordine del cliente. |
| `actionOrderHistoryAddAfter` | Dopo che è stata aggiunta una voce di cronologia dell'ordine (cambio di stato). | Potrebbe essere utilizzato come trigger alternativo per la consegna delle chiavi o per scopi di registrazione relativi ai cambi di stato. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, accedi al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Lì troverai l'accesso ai tuoi moduli acquistati e ai canali di supporto dedicati.
