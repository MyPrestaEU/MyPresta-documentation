---
title: "Portafoglio Prepagato e Credito Negozio - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Portafoglio Prepagato e Credito Negozio di MyPresta.eu."
sidebar:
  label: "Portafoglio Prepagato e Credito Negozio - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Prepaid Wallet & Store Credit su MyPresta.eu](https://mypresta.eu/modules/payment-process/prepaid-wallet-store-credit.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/payment/prepaid-wallet-store-credit/)
>
> ---


# Portafoglio Prepagato e Credito Negozio

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Sono richieste estensioni PHP standard (cURL, JSON, OpenSSL), che sono tipicamente disponibili sulla maggior parte degli ambienti di hosting moderni.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale dove imposterai il comportamento centrale del tuo sistema di Portafoglio Prepagato.

#### Scheda Impostazioni Generali

-   **Abilita Modulo:**
    *   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare l'intero sistema di Portafoglio Prepagato per il tuo negozio.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* I clienti vedranno le opzioni del portafoglio, potranno ricaricare, utilizzare il credito e potrai gestire i portafogli nel back office.
        *   *Quando disabilitato:* Tutte le funzionalità del portafoglio sono nascoste ai clienti, e non possono utilizzare o gestire il loro credito. La gestione amministrativa potrebbe essere ancora accessibile ma non influenzerà il front office.
    *   **Valore consigliato:** SÌ (per attivare il modulo).
    *   **Scenario / esempio del commerciante:** Sei pronto a lanciare il tuo programma fedeltà. Abilita questa impostazione. Se hai bisogno di disabilitarlo temporaneamente per manutenzione, disattivalo.
-   **Consenti ai clienti di ricaricare il portafoglio:**
    *   **Cosa fa questa impostazione:** Determina se i clienti possono attivamente aggiungere fondi al loro portafoglio da soli.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* I clienti vedranno un'opzione "Ricarica Portafoglio" nel loro account, permettendo loro di acquistare credito del negozio.
        *   *Quando disabilitato:* I clienti possono ricevere credito solo da codici regalo o rimborsi/bonus emessi dall'amministratore. Non possono acquistare credito direttamente.
    *   **Valore consigliato:** SÌ (per incoraggiare la fedeltà self-service).
    *   **Scenario / esempio del commerciante:** Vuoi che i clienti possano acquistare credito del negozio quando vogliono. Abilita questa opzione. Se vuoi solo emettere credito come ricompense o carte regalo, disabilitala.
-   **Importo minimo di ricarica:**
    *   **Cosa fa questa impostazione:** Imposta l'importo più basso che un cliente può aggiungere al suo portafoglio in una singola transazione.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato su un valore (es. 10.00):* I clienti non possono ricaricare meno di questo importo.
        *   *Quando impostato su 0 o vuoto:* Non viene applicato alcun importo minimo di ricarica.
    *   **Valore consigliato:** 10.00 (o un importo ragionevole per la tua attività per coprire le commissioni di transazione e incoraggiare ricariche significative).
    *   **Scenario / esempio del commerciante:** Non vuoi che i clienti ricarichino 0.50 EUR. Imposta questo a 5.00 EUR per garantire un valore minimo.
-   **Importo massimo di ricarica:**
    *   **Cosa fa questa impostazione:** Imposta l'importo più alto che un cliente può aggiungere al suo portafoglio in una singola transazione.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato su un valore (es. 500.00):* I clienti non possono ricaricare più di questo importo.
        *   *Quando impostato su 0 o vuoto:* Non viene applicato alcun importo massimo di ricarica.
    *   **Valore consigliato:** 500.00 (o un limite superiore adatto per gestire il rischio e le grandi transazioni).
    *   **Scenario / esempio del commerciante:** Vuoi prevenire ricariche singole estremamente grandi per motivi di sicurezza o di flusso di cassa. Imposta questo a 1000.00 EUR.
-   **Consenti ai clienti di acquistare codici regalo:**
    *   **Cosa fa questa impostazione:** Controlla se i clienti possono acquistare codici regalo da dare ad altri.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* I clienti possono acquistare codici regalo di un valore specificato, che possono poi essere riscattati da chiunque.
        *   *Quando disabilitato:* I codici regalo possono essere generati ed emessi solo dall'amministratore del negozio.
    *   **Valore consigliato:** SÌ (per espandere le tue opzioni di regalo).
    *   **Scenario / esempio del commerciante:** Vuoi offrire carte regalo digitali. Abilita questa opzione in modo che i clienti possano acquistarle per amici e familiari.
-   **Scadenza codice regalo (Giorni):**
    *   **Cosa fa questa impostazione:** Definisce quanti giorni un codice regalo rimane valido dopo essere stato acquistato o generato.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato su un numero (es. 365):* I codici regalo scadranno dopo questo numero di giorni.
        *   *Quando impostato su 0 o vuoto:* I codici regalo non scadranno.
    *   **Valore consigliato:** 365 (una durata comune per le carte regalo, o 0 per nessuna scadenza).
    *   **Scenario / esempio del commerciante:** Vuoi che i codici regalo vengano utilizzati entro un anno. Imposta questo a 365.
-   **Scadenza saldo portafoglio (Giorni):**
    *   **Cosa fa questa impostazione:** Definisce quanti giorni i fondi del portafoglio rimangono validi dopo essere stati aggiunti (tramite ricarica, riscatto di codice regalo o credito amministrativo).
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato su un numero (es. 180):* I fondi nel portafoglio del cliente scadranno dopo questo numero di giorni.
        *   *Quando impostato su 0 o vuoto:* I fondi del portafoglio non scadranno.
    *   **Valore consigliato:** 0 (nessuna scadenza, per massimizzare la soddisfazione del cliente), o 180/365 se vuoi incoraggiare l'utilizzo.
    *   **Scenario / esempio del commerciante:** Vuoi incoraggiare i clienti a utilizzare il loro saldo del portafoglio entro 6 mesi. Imposta questo a 180. Sii consapevole delle leggi sulla protezione dei consumatori relative alla scadenza delle carte regalo nella tua regione.
-   **Invia email di promemoria scadenza (Giorni prima della scadenza):**
    *   **Cosa fa questa impostazione:** Se la scadenza del saldo del portafoglio è abilitata, questa impostazione determina quanti giorni prima della scadenza viene inviata un'email di promemoria al cliente.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando impostato su un numero (es. 7):* I clienti riceveranno un'email 7 giorni prima della scadenza del loro saldo del portafoglio.
        *   *Quando impostato su 0 o vuoto:* Non verranno inviate email di promemoria scadenza.
    *   **Valore consigliato:** 7 (dà ai clienti abbastanza tempo per reagire).
    *   **Scenario / esempio del commerciante:** Hai una scadenza di 180 giorni. Imposta questo a 7 per ricordare ai clienti di utilizzare i loro fondi prima che li perdano.
-   **Consenti pagamenti parziali con portafoglio:**
    *   **Cosa fa questa impostazione:** Controlla se i clienti possono utilizzare il loro saldo del portafoglio per pagare solo una parte del loro ordine, combinandolo con un altro metodo di pagamento.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Se il saldo del portafoglio è inferiore al totale dell'ordine, i clienti possono utilizzare l'intero saldo e pagare il resto con un altro metodo.
        *   *Quando disabilitato:* I clienti possono utilizzare il loro portafoglio solo se copre l'*intero* totale dell'ordine. Altrimenti, devono scegliere un altro metodo di pagamento.
    *   **Valore consigliato:** SÌ (per massimizzare l'utilizzo del portafoglio e ridurre l'abbandono del carrello).
    *   **Scenario / esempio del commerciante:** Un cliente ha 10 EUR nel suo portafoglio e un ordine di 50 EUR. Se abilitato, paga 10 EUR con il portafoglio e 40 EUR con una carta di credito. Se disabilitato, non può utilizzare il portafoglio affatto per questo ordine.
-   **Opzione di rimborso al portafoglio:**
    *   **Cosa fa questa impostazione:** Ti consente di offrire ai clienti l'opzione di ricevere rimborsi per gli ordini restituiti direttamente nel loro portafoglio del negozio anziché al loro metodo di pagamento originale.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Quando elabori un rimborso nel back office, vedrai un'opzione per rimborsare al portafoglio del cliente.
        *   *Quando disabilitato:* I rimborsi devono essere elaborati tramite metodi PrestaShop standard (ad esempio, di nuovo alla carta di credito).
    *   **Valore consigliato:** SÌ (per mantenere i fondi nel tuo negozio e semplificare i rimborsi).
    *   **Scenario / esempio del commerciante:** Un cliente restituisce un articolo. Invece di un rimborso con carta di credito, offri di mettere il denaro nel suo portafoglio, incoraggiandolo ad acquistare qualcos'altro dal tuo negozio.
-   **Abilita supporto multi-valuta:**
    *   **Cosa fa questa impostazione:** Attiva la capacità del modulo di gestire i saldi del portafoglio e le transazioni in più valute, corrispondenti alle valute configurate del tuo negozio.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* I saldi del portafoglio sono gestiti per valuta. Un cliente che ricarica in EUR avrà un saldo in EUR, e un cliente che ricarica in USD avrà un saldo in USD.
        *   *Quando disabilitato:* Tutte le transazioni del portafoglio vengono convertite nella valuta predefinita del tuo negozio, il che può portare a problemi di tasso di conversione.
    *   **Valore consigliato:** SÌ (se il tuo negozio opera in più valute).
    *   **Scenario / esempio del commerciante:** Hai clienti nell'UE e negli Stati Uniti. Abilitando questa opzione si assicura che un cliente che ricarica 50 EUR abbia 50 EUR nel suo portafoglio, e un cliente che ricarica 50 USD abbia 50 USD, prevenendo perdite di conversione di valuta.

#### Scheda Bonus di Ricarica

-   **Abilita Bonus di Ricarica:**
    *   **Cosa fa questa impostazione:** Attiva il sistema per premiare i clienti con credito extra quando ricaricano il loro portafoglio oltre determinate soglie.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Le regole bonus che definisci di seguito verranno applicate alle ricariche dei clienti.
        *   *Quando disabilitato:* Nessun bonus verrà dato per le ricariche.
    *   **Valore consigliato:** SÌ (per incentivare ricariche più grandi e aumentare l'AOV).
    *   **Scenario / esempio del commerciante:** Vuoi dare ai clienti un credito extra del 5% se ricaricano 100 EUR o più. Abilita questa opzione.
-   **Livelli Bonus (Aggiungi/Modifica/Elimina):**
    *   **Cosa fa questa impostazione:** Ti consente di definire regole bonus specifiche basate sull'importo della ricarica. Ogni livello consiste in un valore minimo di ricarica e una percentuale di bonus.
    *   **Effetto della modifica di questa impostazione:**
        *   *Aggiungendo un livello (es. "Importo Min: 100, Bonus %: 5"):* I clienti che ricaricano 100 EUR o più riceveranno un ulteriore 5% di quell'importo nel loro portafoglio.
        *   *Modificando un livello:* Cambia le regole bonus per quella specifica soglia.
        *   *Eliminando un livello:* Rimuove una regola bonus.
    *   **Valore consigliato:** Crea 2-3 livelli (es. 5% per 100 EUR, 10% per 200 EUR) per incoraggiare ricariche progressivamente più grandi.
    *   **Scenario / esempio del commerciante:**
        *   Livello 1: Importo Min = 50 EUR, Bonus % = 2% (Il cliente ricarica 50 EUR, ottiene 51 EUR nel portafoglio)
        *   Livello 2: Importo Min = 100 EUR, Bonus % = 5% (Il cliente ricarica 100 EUR, ottiene 105 EUR nel portafoglio)
        *   Livello 3: Importo Min = 200 EUR, Bonus % = 10% (Il cliente ricarica 200 EUR, ottiene 220 EUR nel portafoglio)

#### Scheda Opzioni di Visualizzazione

-   **Visualizza saldo portafoglio nell'intestazione:**
    *   **Cosa fa questa impostazione:** Mostra il saldo attuale del portafoglio del cliente in modo prominente nella sezione dell'intestazione del tuo negozio.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* I clienti loggati vedranno il loro saldo (es. "Il tuo portafoglio: 25.00 EUR") vicino al loro link dell'account.
        *   *Quando disabilitato:* Il saldo è visibile solo sulla pagina dedicata "Il mio portafoglio".
    *   **Valore consigliato:** SÌ (per alta visibilità e comodità).
    *   **Scenario / esempio del commerciante:** Vuoi che i clienti siano sempre consapevoli del loro credito disponibile, incoraggiandoli a usarlo.
-   **Visualizza link portafoglio nel menu account cliente:**
    *   **Cosa fa questa impostazione:** Aggiunge un link diretto alla pagina "Il mio portafoglio" nel menu di navigazione dell'account del cliente.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Un link "Il mio portafoglio" o "Credito negozio" appare nel menu a sinistra della dashboard dell'account del cliente.
        *   *Quando disabilitato:* I clienti dovrebbero navigare alla pagina del portafoglio tramite un altro link (es. dall'intestazione se abilitato).
    *   **Valore consigliato:** SÌ (essenziale per un facile accesso).
    *   **Scenario / esempio del commerciante:** Vuoi che i clienti trovino e gestiscano facilmente i loro fondi del portafoglio.
-   **Visualizza link portafoglio nel piè di pagina:**
    *   **Cosa fa questa impostazione:** Aggiunge un link alla pagina "Il mio portafoglio" nella sezione del piè di pagina del tuo negozio.
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Un link "Il mio portafoglio" o "Credito negozio" appare nel piè di pagina, accessibile da qualsiasi pagina.
        *   *Quando disabilitato:* Nessun link del portafoglio nel piè di pagina.
    *   **Valore consigliato:** NO (solitamente ridondante se nell'intestazione/menu account, ma può essere SÌ per massima visibilità).
    *   **Scenario / esempio del commerciante:** Se il menu del tuo account cliente non è molto prominente, o vuoi evidenziare la funzione del portafoglio più ampiamente, potresti abilitare questa opzione.
-   **Visualizza link portafoglio nella colonna sinistra/destra:**
    *   **Cosa fa questa impostazione:** Aggiunge un link alla pagina "Il mio portafoglio" in una delle colonne laterali del tuo negozio (se il tuo tema le supporta).
    *   **Effetto della modifica di questa impostazione:**
        *   *Quando abilitato:* Un link "Il mio portafoglio" o "Credito negozio" appare nella colonna scelta.
        *   *Quando disabilitato:* Nessun link del portafoglio nelle colonne.
    *   **Valore consigliato:** NO (può ingombrare il layout, solitamente meglio nell'intestazione/account).
    *   **Scenario / esempio del commerciante:** Se hai un'intestazione/piè di pagina molto minimalista e vuoi usare una colonna per la navigazione, questa potrebbe essere un'opzione.

#### Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Impostazioni Generali** | Abilita Modulo | SÌ | Attiva/disattiva tutte le funzionalità del portafoglio. |
| | Consenti ai clienti di ricaricare il portafoglio | SÌ | I clienti possono acquistare credito del negozio. |
| | Importo minimo di ricarica | 10.00 | Importo più basso che il cliente può aggiungere. |
| | Importo massimo di ricarica | 500.00 | Importo più alto che il cliente può aggiungere. |
| | Consenti ai clienti di acquistare codici regalo | SÌ | I clienti possono acquistare carte regalo. |
| | Scadenza codice regalo (Giorni) | 365 | Periodo di validità per i codici regalo (0 per nessuna scadenza). |
| | Scadenza saldo portafoglio (Giorni) | 0 | Periodo di validità per i fondi del portafoglio (0 per nessuna scadenza). |
| | Invia email di promemoria scadenza (Giorni prima della scadenza) | 7 | Giorni prima della scadenza per inviare un'email di promemoria. |
| | Consenti pagamenti parziali con portafoglio | SÌ | I clienti possono combinare il portafoglio con altri metodi di pagamento. |
| | Opzione di rimborso al portafoglio | SÌ | Opzione per rimborsare gli ordini direttamente al portafoglio del cliente. |
| | Abilita supporto multi-valuta | SÌ (se negozio multi-valuta) | Gestisce saldi separati per ogni valuta. |
| **Bonus di Ricarica** | Abilita Bonus di Ricarica | SÌ | Attiva il sistema bonus per le ricariche. |
| | Livelli Bonus | (Personalizzato) | Definisci le percentuali bonus per diversi importi di ricarica. |
| **Opzioni di Visualizzazione** | Visualizza saldo portafoglio nell'intestazione | SÌ | Mostra il saldo nell'intestazione del negozio per gli utenti loggati. |
| | Visualizza link portafoglio nel menu account cliente | SÌ | Aggiunge il link "Il mio portafoglio" alla navigazione dell'account cliente. |
| | Visualizza link portafoglio nel piè di pagina | NO | Aggiunge il link "Il mio portafoglio" al piè di pagina del negozio. |
| | Visualizza link portafoglio nella colonna sinistra/destra | NO | Aggiunge il link "Il mio portafoglio" alle colonne laterali. |

### 2.2 Schermate di amministrazione dedicate e viste del controller

Il modulo fornisce schermate di amministrazione dedicate per la gestione dei portafogli dei clienti e dei codici regalo.

#### 2.2.1 Gestione Portafogli (Back Office > Moduli > Portafoglio Prepagato e Credito Negozio > Portafogli)

-   **Nome schermata e posizione nel menu:** **Portafogli** (si trova sotto la voce di menu "Portafoglio Prepagato e Credito Negozio", che appare sotto "Moduli" o "Pagamento" a seconda della tua versione di PrestaShop e della configurazione del menu).
-   **Azioni e impostazioni disponibili:** Questa schermata mostra un elenco di tutti i clienti che hanno un portafoglio, insieme al loro saldo attuale, ricariche totali e altre informazioni pertinenti.
    *   **Elenco clienti:** Una tabella ricercabile e filtrabile che mostra il nome, l'email, il saldo attuale del portafoglio (per valuta se il multi-valuta è abilitato) e l'importo totale ricaricato di ogni cliente.
    *   **Visualizza/Modifica portafoglio:** Clicca su una riga del cliente o su un'icona "Modifica" per visualizzare la cronologia dettagliata del portafoglio e apportare modifiche.
        *   **Aggiungi/Rimuovi fondi:** Aggiungi o sottrai manualmente fondi dal portafoglio di un cliente. Questo è utile per emettere credito di buona volontà, compensazioni o correggere errori.
        *   **Visualizza cronologia transazioni:** Visualizza un registro dettagliato di tutte le attività del portafoglio per quel cliente (ricariche, acquisti, rimborsi, bonus, scadenza).
        *   **Imposta data di scadenza:** Imposta o modifica manualmente la data di scadenza per fondi specifici nel portafoglio di un cliente.
-   **Effetto delle modifiche:**
    *   *Aggiunta/Rimozione fondi:* Influisce direttamente sul saldo disponibile del cliente nel front office.
    *   *Modifica delle date di scadenza:* Influisce su quando i fondi diventano inutilizzabili per il cliente.
    *   *Visualizzazione della cronologia:* Fornisce un percorso di audit completo per il servizio clienti e la contabilità.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  **Richiesta del cliente:** Se un cliente chiede informazioni sul proprio saldo o su una transazione specifica, usa questa schermata per cercare rapidamente il suo portafoglio e la cronologia.
    2.  **Emissione di credito:** Se devi dare a un cliente un credito del negozio (ad esempio, per un reclamo, un premio fedeltà), naviga al suo portafoglio e usa l'opzione "Aggiungi fondi".
    3.  **Rimborsi al portafoglio:** Quando elabori un rimborso per un ordine, puoi scegliere di inviare il denaro al portafoglio del cliente dalla pagina dei dettagli dell'ordine. Questa azione sarà riflessa qui.

#### 2.2.2 Gestione Codici Regalo (Back Office > Moduli > Portafoglio Prepagato e Credito Negozio > Codici)

-   **Nome schermata e posizione nel menu:** **Codici** (si trova sotto la voce di menu "Portafoglio Prepagato e Credito Negozio").
-   **Azioni e impostazioni disponibili:** Questa schermata ti consente di generare, gestire e tracciare tutti i codici regalo nel tuo sistema.
    *   **Elenco codici:** Una tabella che mostra tutti i codici regalo generati, il loro valore, lo stato attuale (attivo, riscattato, scaduto), chi lo ha acquistato (se applicabile), chi lo ha riscattato e la data di scadenza.
    *   **Genera nuovo codice:** Crea nuovi codici regalo con un valore, una valuta e una data di scadenza opzionale specificati. Questi possono essere utilizzati per promozioni, omaggi o crediti manuali del servizio clienti.
    *   **Modifica codice:** Modifica il valore, lo stato o la scadenza di un codice esistente (se non ancora riscattato).
    *   **Elimina codice:** Rimuovi un codice (solo se non riscattato).
    *   **Cerca/Filtra:** Trova facilmente codici specifici per valore, stato o cliente.
-   **Effetto delle modifiche:**
    *   *Generazione di un codice:* Crea un nuovo codice regalo utilizzabile che può essere dato a un cliente.
    *   *Modifica di un codice:* Cambia le sue proprietà, influenzando la sua riscattabilità e il suo valore.
    *   *Eliminazione di un codice:* Impedisce che venga riscattato.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  **Campagne promozionali:** Genera un lotto di codici regalo per una campagna di marketing (ad esempio, "10 EUR di sconto per i nuovi iscritti").
    2.  **Servizio clienti:** Se un cliente ha un problema, puoi generare rapidamente un codice regalo unico per compensarlo.
    3.  **Monitoraggio dell'utilizzo:** Monitora quali codici sono stati riscattati e da chi, aiutandoti ad analizzare l'efficacia della campagna.

#### 2.2.3 Registro di Audit (Back Office > Moduli > Portafoglio Prepagato e Credito Negozio > Audit)

-   **Nome schermata e posizione nel menu:** **Audit** (si trova sotto la voce di menu "Portafoglio Prepagato e Credito Negozio").
-   **Azioni e impostazioni disponibili:** Questa schermata fornisce un registro completo di tutte le attività relative al portafoglio nel tuo negozio.
    *   **Elenco attività:** Una tabella dettagliata che mostra ogni transazione, ricarica, riscatto, aggiustamento amministrativo ed evento di scadenza.
    *   **Dettagli:** Ogni voce include la data, il cliente coinvolto, il tipo di attività, l'importo e eventuali note pertinenti (ad esempio, ID ordine, amministratore che ha effettuato la modifica).
    *   **Cerca/Filtra:** Filtra il registro di audit per cliente, intervallo di date o tipo di attività per trovare rapidamente eventi specifici.
-   **Effetto delle modifiche:** Questo è un registro di sola lettura; non è possibile apportare modifiche qui. Serve come un record cruciale per la responsabilità e la risoluzione dei problemi.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
    1.  **Risoluzione dei problemi:** Se un cliente segnala un saldo errato, usa il registro di audit per tracciare tutte le transazioni e identificare eventuali discrepanze.
    2.  **Conformità:** Mantieni un registro chiaro di tutti i movimenti finanziari relativi al sistema del portafoglio per scopi contabili e legali.
    3.  **Revisione delle prestazioni:** Analizza l'attività complessiva del portafoglio per comprendere l'engagement del cliente e l'utilizzo del modulo.

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei clienti non riescono a vedere le opzioni del portafoglio nel front office.**
R1:

-   **Verifica l'abilitazione del modulo:** Vai su **Moduli > Gestione moduli**, trova "Portafoglio Prepagato e Credito Negozio" e assicurati che il modulo sia abilitato.
-   **Verifica le impostazioni generali:** Nella pagina di configurazione del modulo, assicurati che "Abilita Modulo" sia impostato su SÌ. Inoltre, controlla che le opzioni di visualizzazione specifiche come "Visualizza link portafoglio nel menu account cliente" siano abilitate.
-   **Accesso del cliente:** Le funzionalità del portafoglio sono tipicamente visibili solo ai clienti loggati. Chiedi al tuo cliente di effettuare l'accesso.
-   **Compatibilità del tema:** Sebbene il modulo sia progettato per la compatibilità, alcuni temi altamente personalizzati potrebbero richiedere piccole modifiche. Se sospetti un conflitto con il tema, prova a passare temporaneamente al tema PrestaShop predefinito per vedere se il problema si risolve.

**D2: Il saldo del portafoglio di un cliente sembra errato.**
R2:

-   **Controlla il registro di audit:** Vai su **Moduli > Portafoglio Prepagato e Credito Negozio > Audit**. Cerca il nome del cliente e rivedi l'intera cronologia delle transazioni. Questo mostrerà tutte le ricariche, gli acquisti, i rimborsi, i bonus e gli aggiustamenti amministrativi.
-   **Controlla i dettagli del portafoglio:** Vai su **Moduli > Portafoglio Prepagato e Credito Negozio > Portafogli**, trova il cliente e clicca per visualizzare il suo portafoglio dettagliato. Confronta il saldo con il registro di audit.
-   **Problema di valuta:** Se "Abilita supporto multi-valuta" è attivo, assicurati di visualizzare il saldo nella valuta corretta. Un cliente potrebbe avere saldi in più valute.
-   **Scadenza:** Controlla se ci sono fondi scaduti. Il registro di audit mostrerà gli eventi di scadenza.

**D3: I miei clienti non ricevono le email di promemoria scadenza.**
R3:

-   **Controlla le impostazioni di scadenza:** Assicurati che "Scadenza saldo portafoglio (Giorni)" sia impostato su un valore maggiore di 0 e che "Invia email di promemoria scadenza (Giorni prima della scadenza)" sia anch'esso impostato su un valore maggiore di 0.
-   **Cron Job:** Il modulo probabilmente utilizza un cron job per attivare queste email. Assicurati che il tuo cron job di PrestaShop sia configurato correttamente e in esecuzione regolarmente. (Vedi Sezione 7.2 per `cron.php`).
-   **Configurazione email:** Verifica che le impostazioni email di PrestaShop (**Parametri Avanzati > E-mail**) siano configurate correttamente e che le email vengano inviate con successo. Prova a inviare un'email generica da PrestaShop.
-   **Cartelle spam:** Consiglia ai clienti di controllare le loro cartelle spam o posta indesiderata.

**D4: Come posso svuotare la cache di Smarty se vedo contenuti vecchi o problemi di visualizzazione?**
R4:

-   Vai su **Parametri Avanzati > Prestazioni** nel tuo Back Office di PrestaShop.
-   Nella sezione "Smarty", imposta "Compilazione dei template" su "Ricompila i template se i file sono stati aggiornati" (o "Forza compilazione" temporaneamente).
-   Clicca su "Svuota la cache" nell'angolo in alto a destra.
-   Dopo aver svuotato, puoi ripristinare "Compilazione dei template" a "Non ricompilare mai i file dei template" per migliori prestazioni.

**D5: Il modulo non appare correttamente sul mio tema personalizzato.**
R5:

-   **Sovrascritture CSS:** Il CSS del tuo tema personalizzato potrebbe sovrascrivere gli stili predefiniti del modulo.
-   **Ispeziona elemento:** Utilizza gli strumenti per sviluppatori del tuo browser (clic destro, "Ispeziona") per identificare le regole CSS che influenzano gli elementi del modulo. Puoi quindi aggiungere CSS personalizzato al foglio di stile del tuo tema per sovrascrivere queste regole.
-   **Contatta lo sviluppatore:** Se non ti senti a tuo agio con il CSS, contatta lo sviluppatore del tuo tema o il supporto MyPresta.eu per assistenza. Fornisci screenshot e il nome del tuo tema.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

Questa sezione fornisce un'analisi approfondita della struttura tecnica del modulo "Portafoglio Prepagato e Credito Negozio", progettata per sviluppatori e webmaster.

### 4.1 Panoramica dell'Architettura

Il modulo "Portafoglio Prepagato e Credito Negozio" segue il modello MVC (Model-View-Controller) standard di PrestaShop. Estende le funzionalità principali di PrestaShop tramite hook, controller personalizzati e classi dedicate.

-   **Controller:** Gestisce le interazioni del front-office (ricariche, riscatto codici, elaborazione pagamenti) e l'amministrazione del back-office (gestione portafogli/codici).
-   **Modelli:** Le classi `ObjectModel` personalizzate (`PrepaidWalletService`, `PrepaidCodeService`, ecc.) gestiscono la persistenza dei dati per portafogli, codici e transazioni, interagendo con tabelle di database dedicate.
-   **Viste:** I file Smarty `.tpl` rendono sia le interfacce utente del front-office (pagina del portafoglio, moduli di ricarica) sia le griglie/moduli di amministrazione del back-office.
-   **Servizi:** Diverse classi helper incapsulano la logica di business specifica (ad esempio, `PrepaidCartCreditService` per l'integrazione del checkout, `PrepaidExpiry` per la gestione della scadenza dei fondi).
-   **Hook:** Il modulo utilizza ampiamente gli hook di PrestaShop per iniettare la sua funzionalità in varie parti del negozio (intestazione, account cliente, processo di pagamento, dettagli dell'ordine).

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

-   `prepaidpayment/controllers/front/applycode.php`
    *   **Nome classe e classe genitore:** `PrepaidPaymentApplyCodeModuleFrontController` che estende `ModuleFrontController`.
    *   **Responsabilità:** Gestisce la richiesta AJAX per l'applicazione di un codice regalo durante il processo di checkout o sulla pagina di riscatto dedicata. Convalida il codice e aggiorna il credito del carrello.
-   `prepaidpayment/controllers/front/buycode.php`
    *   **Nome classe e classe genitore:** `PrepaidPaymentBuyCodeModuleFrontController` che estende `ModuleFrontController`.
    *   **Responsabilità:** Gestisce il processo di acquisto di codici regalo da parte dei clienti. Gestisce la visualizzazione del modulo di acquisto del codice regalo e la creazione del prodotto codice regalo nel carrello.
-   `prepaidpayment/controllers/front/cron.php`
    *   **Nome classe e classe genitore:** `PrepaidPaymentCronModuleFrontController` che estende `ModuleFrontController`.
    *   **Responsabilità:** Questo controller è progettato per essere chiamato da un cron job. Esegue attività in background come il controllo dei fondi del portafoglio scaduti, l'invio di email di promemoria scadenza e potenzialmente altre manutenzioni programmate.
-   `prepaidpayment/controllers/front/entercode.php`
    *   **Nome classe e classe genitore:** `PrepaidPaymentEnterCodeModuleFrontController` che estende `ModuleFrontController`.
    *   **Responsabilità:** Visualizza la pagina dedicata dove i clienti possono inserire un codice regalo per riscattarlo e aggiungere fondi al loro portafoglio.
-   `prepaidpayment/controllers/front/index.php`
    *   **Nome classe e classe genitore:** `PrepaidPaymentIndexModuleFrontController` che estende `ModuleFrontController`.
    *   **Responsabilità:** Probabilmente funge da controller frontale predefinito o di fallback, o una base per altri controller frontali. In molti moduli, questo potrebbe reindirizzare o visualizzare una pagina generale del modulo.
-   `prepaidpayment/controllers/front/payment.php`
    *   **Nome classe e classe genitore:** `PrepaidPaymentPaymentModuleFrontController` che estende `ModuleFrontController`.
    *   **Responsabilità:** Gestisce il processo di pagamento quando un cliente sceglie di pagare con il proprio portafoglio. Convalida il saldo del portafoglio rispetto al totale dell'ordine ed elabora il pagamento.
-   `prepaidpayment/controllers/front/redeempay.php`
    *   **Nome classe e classe genitore:** `PrepaidPaymentRedeemPayModuleFrontController` che estende `ModuleFrontController`.
    *   **Responsabilità:** Questo controller probabilmente gestisce il riscatto di un codice regalo e la sua applicazione al carrello corrente, potenzialmente combinando la logica di `applycode.php` e `payment.php` in un flusso specifico.
-   `prepaidpayment/controllers/front/topup.php`
    *   **Nome classe e classe genitore:** `PrepaidPaymentTopupModuleFrontController` che estende `ModuleFrontController`.
    *   **Responsabilità:** Gestisce il processo di ricarica del portafoglio del cliente. Visualizza il modulo di ricarica, gestisce la selezione degli importi di ricarica (e i bonus associati) e aggiunge il prodotto di ricarica al carrello.

#### Controller Admin Back-Office

-   `prepaidpayment/controllers/admin/index.php`
    *   **Nome classe e classe genitore:** `AdminPrepaidPaymentController` che estende `ModuleAdminController`.
    *   **Nome scheda ed entità gestita:** Questo controller funge da punto di ingresso principale per l'interfaccia di amministrazione del modulo. Probabilmente distribuisce a varie viste (Portafogli, Codici, Audit) e gestisce la configurazione generale e i dati per il modulo. Non gestisce direttamente un singolo `ObjectModel` ma orchestra la gestione dei dati di `PrepaidWalletService` e `PrepaidCodeService`.

### 4.3 Classi e Modelli Core (`classes/`)

-   `prepaidpayment/classes/index.php`
    *   **Scopo:** Tipicamente un file vuoto o contiene una semplice istruzione `die()` per prevenire la visualizzazione diretta della directory, una pratica di sicurezza comune.
-   `prepaidpayment/classes/PrepaidAdmin.php`
    *   **Scopo:** Probabilmente una classe helper per le attività amministrative, potenzialmente contenente metodi per il rendering di moduli amministrativi, la gestione di richieste AJAX all'interno del back office o manipolazioni di dati specifiche per le viste amministrative.
-   `prepaidpayment/classes/PrepaidCartCreditService.php`
    *   **Scopo:** Incapsula la logica per l'applicazione del credito del portafoglio o dei codici regalo al carrello di un cliente durante il checkout. Gestisce calcoli, convalide e aggiornamenti al totale del carrello.
-   `prepaidpayment/classes/PrepaidCodeService.php`
    *   **Scopo:** Gestisce il ciclo di vita dei codici regalo.
    *   **Interazione `ObjectModel`:** Probabilmente estende `ObjectModel` e interagisce con una tabella di database personalizzata (ad esempio, `ps_prepaid_codes`).
    *   **Campi `$definition`:** Includerebbe campi come `id_prepaid_code`, `code`, `value`, `id_currency`, `id_customer_buyer`, `id_customer_redeemer`, `date_add`, `date_redeem`, `date_expiry`, `active`.
    *   **Metodi pubblici chiave:** `generateCode()`, `redeemCode()`, `getCodeByCode()`, `isCodeValid()`, `getCodesForCustomer()`.
-   `prepaidpayment/classes/PrepaidCurrency.php`
    *   **Scopo:** Una classe helper per la gestione degli aspetti multi-valuta del portafoglio, garantendo conversioni e visualizzazioni corrette delle valute. Potrebbe estendere `Currency` o fornire metodi di utilità per operazioni sensibili alla valuta.
-   `prepaidpayment/classes/PrepaidExpiry.php`
    *   **Scopo:** Gestisce la logica di scadenza sia per i codici regalo che per i saldi del portafoglio. Contiene metodi per calcolare le date di scadenza, controllare i fondi scaduti e potenzialmente attivare azioni di scadenza (ad esempio, impostare i fondi come inattivi).
-   `prepaidpayment/classes/PrepaidThemeCompat.php`
    *   **Scopo:** Fornisce livelli di compatibilità o aggiustamenti specifici per diversi temi PrestaShop (ad esempio, Classic, Hummingbird) o versioni, garantendo che gli elementi del front-office del modulo vengano visualizzati correttamente in vari ambienti.
-   `prepaidpayment/classes/PrepaidTopupCart.php`
    *   **Scopo:** Gestisce la logica specifica del carrello quando un cliente sta ricaricando il proprio portafoglio. Potrebbe creare un prodotto virtuale nel carrello che rappresenta l'importo della ricarica e gestire i bonus associati.
-   `prepaidpayment/classes/PrepaidWalletService.php`
    *   **Scopo:** La classe principale per la gestione dei portafogli dei clienti.
    *   **Interazione `ObjectModel`:** Probabilmente estende `ObjectModel` e interagisce con una tabella di database personalizzata (ad esempio, `ps_prepaid_wallets` per i saldi e `ps_prepaid_wallet_history` per le transazioni).
    *   **Campi `$definition`:** Per `ps_prepaid_wallets`: `id_prepaid_wallet`, `id_customer`, `id_currency`, `balance`, `date_update`. Per `ps_prepaid_wallet_history`: `id_prepaid_wallet_history`, `id_customer`, `id_currency`, `amount`, `type` (topup, purchase, refund, bonus, expiry), `id_order`, `date_add`, `notes`.
    *   **Metodi pubblici chiave:** `getBalance()`, `addFunds()`, `deductFunds()`, `getHistory()`, `getWalletsForCustomer()`, `processRefundToWallet()`.

### 4.4 Risorse JavaScript (`views/js/`)

-   `prepaidpayment/lib/searchTool/views/js/autocomplete.js`
    *   **Ambito:** Probabilmente Back-office.
    *   **Dettagli:** Fornisce funzionalità di autocompletamento, probabilmente per la ricerca di clienti o prodotti all'interno dell'interfaccia di amministrazione, ad esempio, quando si assegna un codice regalo a un cliente specifico o si gestisce un portafoglio.
-   `prepaidpayment/views/js/adminPrepaid.js`
    *   **Ambito:** Back-office.
    *   **Dettagli:** JavaScript generale per le pagine di amministrazione del modulo. Potrebbe gestire l'invio di moduli, gli aggiornamenti AJAX per elenchi (portafogli, codici), miglioramenti generali dell'interfaccia utente e interazioni nella pagina di configurazione principale.
-   `prepaidpayment/views/js/adminPrepaidBonusBuilder.js`
    *   **Ambito:** Back-office.
    *   **Dettagli:** Gestisce specificamente la creazione e la gestione dinamica dei livelli bonus nella pagina di configurazione del modulo. Probabilmente aggiunge/rimuove campi di input per le percentuali bonus e gli importi minimi, e convalida questi input.
-   `prepaidpayment/views/js/adminPrepaidDashboard.js`
    *   **Ambito:** Back-office.
    *   **Dettagli:** JavaScript per la dashboard o la schermata di panoramica dell'amministratore, potenzialmente gestendo la visualizzazione dei dati, le statistiche rapide o gli elementi interattivi relativi all'utilizzo complessivo del portafoglio.
-   `prepaidpayment/views/js/adminPrepaidSelector.js`
    *   **Ambito:** Back-office.
    *   **Dettagli:** Gestisce i componenti di selezione nell'amministrazione, possibilmente per la scelta di clienti, valute o codici specifici all'interno di vari moduli o elenchi.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `prepaidpayment/lib/searchTool/views/css/autocomplete.css`
    *   **Ambito:** Stile di amministrazione del Back-office.
    *   **Dettagli:** Stili per lo strumento di ricerca con autocompletamento utilizzato nel back office, garantendo che i menu a discesa e i suggerimenti siano visivamente coerenti.
-   `prepaidpayment/views/css/admin_prepaidpayment.css`
    *   **Ambito:** Stile di amministrazione del Back-office.
    *   **Dettagli:** CSS principale per le pagine di amministrazione del modulo, che stilizza moduli, tabelle, pulsanti e layout generale all'interno del back office di PrestaShop.
-   `prepaidpayment/views/css/front-hummingbird.css`
    *   **Ambito:** Stile cliente del Front-office (specificamente per il tema Hummingbird).
    *   **Dettagli:** Fornisce aggiustamenti o sovrascritture di stile specifici per garantire un'integrazione visiva ottimale con il tema PrestaShop Hummingbird.
-   `prepaidpayment/views/css/front.css`
    *   **Ambito:** Stile cliente del Front-office (generale).
    *   **Dettagli:** CSS generale per i componenti del front-office del modulo, come la pagina "Il mio portafoglio", i moduli di ricarica, i moduli di riscatto dei codici regalo e la visualizzazione del portafoglio nell'intestazione/checkout.
-   `prepaidpayment/views/css/prepaidpayment.css`
    *   **Ambito:** Sia Front-office che Back-office (o stili generali a livello di modulo).
    *   **Dettagli:** Contiene stili comuni utilizzati sia nel front che nel back office, o stili fondamentali per gli elementi unici del modulo.

### 4.6 Struttura del template Smarty (`views/templates/`)

#### Template Hook (`views/templates/hook/`)

-   `prepaidpayment/views/templates/hook/adminOrder.tpl`
    *   **Hook:** `displayAdminOrder` o simile.
    *   **Output:** Visualizza informazioni o azioni relative al portafoglio all'interno della pagina dei dettagli dell'ordine di PrestaShop nel back office (ad esempio, opzione per rimborsare al portafoglio, dettagli del pagamento del portafoglio).
-   `prepaidpayment/views/templates/hook/customerAccount-hummingbird.tpl`
    *   **Hook:** `displayCustomerAccount` (specificamente per il tema Hummingbird).
    *   **Output:** Aggiunge un link o un blocco "Il mio portafoglio" alla dashboard dell'account del cliente, stilizzato per il tema Hummingbird.
-   `prepaidpayment/views/templates/hook/customerAccount.tpl`
    *   **Hook:** `displayCustomerAccount`.
    *   **Output:** Aggiunge un link o un blocco "Il mio portafoglio" alla dashboard dell'account del cliente, per temi generici.
-   `prepaidpayment/views/templates/hook/orderDetail.tpl`
    *   **Hook:** `displayOrderDetail` o simile.
    *   **Output:** Visualizza i dettagli del pagamento del portafoglio nella pagina dei dettagli dell'ordine del cliente nel front office.
-   `prepaidpayment/views/templates/hook/payment.tpl`
    *   **Hook:** `displayPayment` (PrestaShop 1.6) o `paymentOptions` (PrestaShop 1.7+).
    *   **Output:** Rende l'opzione "Paga con Portafoglio" nella pagina di selezione del pagamento del checkout.
-   `prepaidpayment/views/templates/hook/paymentReturn.tpl`
    *   **Hook:** `displayPaymentReturn`.
    *   **Output:** Visualizza informazioni sui pagamenti del portafoglio nella pagina di conferma dell'ordine dopo il checkout.
-   `prepaidpayment/views/templates/hook/paymentTop.tpl`
    *   **Hook:** `displayPaymentTop`.
    *   **Output:** Potrebbe visualizzare un riepilogo del saldo del portafoglio o un'opzione per applicare un codice regalo nella parte superiore della pagina di pagamento.
-   `prepaidpayment/views/templates/hook/walletNav.tpl`
    *   **Hook:** `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`.
    *   **Output:** Rende il saldo del portafoglio o un link alla pagina del portafoglio in varie aree di navigazione del negozio.

#### Template Admin (`views/templates/admin/`)

-   `prepaidpayment/views/templates/admin/audit.tpl`
    *   **Output:** Rende la tabella del registro di audit e le opzioni di filtro nel back office.
-   `prepaidpayment/views/templates/admin/codes.tpl`
    *   **Output:** Rende l'elenco dei codici regalo, il modulo per generare nuovi codici e modificare quelli esistenti nel back office.
-   `prepaidpayment/views/templates/admin/dashboard.tpl`
    *   **Output:** Rende la dashboard principale o la pagina di panoramica per il modulo nel back office, potenzialmente mostrando statistiche o collegamenti rapidi.
-   `prepaidpayment/views/templates/admin/scopeSelector.tpl`
    *   **Output:** Un template riutilizzabile per la selezione di ambiti specifici, come valute o gruppi di clienti, all'interno dei moduli amministrativi.
-   `prepaidpayment/views/templates/admin/wallets.tpl`
    *   **Output:** Rende l'elenco dei portafogli dei clienti, la vista dettagliata del portafoglio e le opzioni per aggiungere/rimuovere fondi nel back office.

#### Template Front-office (`views/templates/front/`)

-   `prepaidpayment/views/templates/front/buycode.tpl`
    *   **Output:** Rende il modulo e l'interfaccia per i clienti per acquistare codici regalo.
-   `prepaidpayment/views/templates/front/entercode.tpl`
    *   **Output:** Rende la pagina dedicata dove i clienti possono inserire un codice regalo per riscattarlo.
-   `prepaidpayment/views/templates/front/topup.tpl`
    *   **Output:** Rende il modulo e le opzioni per i clienti per ricaricare il loro portafoglio, incluse le informazioni sui bonus.

#### Template di libreria (`prepaidpayment/lib/searchTool/views/scripts.tpl`)

-   `prepaidpayment/lib/searchTool/views/scripts.tpl`
    *   **Output:** Contiene logica JavaScript o Smarty per lo strumento di ricerca, probabilmente inclusa nei template amministrativi dove è necessario l'autocompletamento.

### 4.7 Schema del Database e Mappa degli Hook

#### Tabelle del Database

-   `ps_prepaid_wallets`: Memorizza il saldo attuale per ogni cliente e valuta.
    *   `id_prepaid_wallet` (PK)
    *   `id_customer` (FK a `ps_customer`)
    *   `id_currency` (FK a `ps_currency`)
    *   `balance` (decimale)
    *   `date_upd` (datetime)
-   `ps_prepaid_wallet_history`: Registra tutte le transazioni e le modifiche ai portafogli dei clienti.
    *   `id_prepaid_wallet_history` (PK)
    *   `id_customer` (FK a `ps_customer`)
    *   `id_currency` (FK a `ps_currency`)
    *   `amount` (decimale, positivo per credito, negativo per debito)
    *   `type` (varchar, es. 'topup', 'purchase', 'refund', 'bonus', 'expiry', 'admin\_add', 'admin\_deduct')
    *   `id_order` (FK a `ps_order`, nullable)
    *   `id_prepaid_code` (FK a `ps_prepaid_codes`, nullable)
    *   `notes` (testo, es. "Aggiustamento amministrativo", "Riscatto codice regalo")
    *   `date_add` (datetime)
    *   `date_expiry` (datetime, nullable)
-   `ps_prepaid_codes`: Memorizza le informazioni sui codici regalo generati e acquistati.
    *   `id_prepaid_code` (PK)
    *   `code` (varchar, unico, la stringa del codice regalo effettivo)
    *   `value` (decimale, valore iniziale del codice)
    *   `id_currency` (FK a `ps_currency`)
    *   `id_customer_buyer` (FK a `ps_customer`, nullable, se acquistato dal cliente)
    *   `id_customer_redeemer` (FK a `ps_customer`, nullable, una volta riscattato)
    *   `date_add` (datetime)
    *   `date_redeem` (datetime, nullable)
    *   `date_expiry` (datetime, nullable)
    *   `active` (tinyint, 0 o 1)
-   `ps_prepaid_bonus_tiers`: Memorizza le regole bonus di ricarica configurate.
    *   `id_prepaid_bonus_tier` (PK)
    *   `min_amount` (decimale)
    *   `bonus_percentage` (decimale)
    *   `position` (int)
-   `ps_configuration`: Le impostazioni del modulo sono memorizzate qui con chiavi come `PREPAIDPAYMENT_ENABLED`, `PREPAIDPAYMENT_MIN_TOPUP`, ecc.

#### Tabella degli Hook Registrati

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Inietta CSS/JS, visualizza il saldo del portafoglio per gli utenti loggati. |
| `displayLeftColumn` | Nella colonna sinistra del negozio. | Visualizza il link del portafoglio. |
| `displayRightColumn` | Nella colonna destra del negozio. | Visualizza il link del portafoglio. |
| `displayFooter` | Nella sezione del piè di pagina di ogni pagina. | Visualizza il link del portafoglio. |
| `displayCustomerAccount` | Nella pagina "Il mio account" del cliente. | Aggiunge il link/blocco "Il mio portafoglio". |
| `displayPayment` (PS 1.6) / `paymentOptions` (PS 1.7+) | Nella pagina di selezione del pagamento del checkout. | Visualizza l'opzione di pagamento "Paga con Portafoglio". |
| `displayPaymentReturn` | Nella pagina di conferma dell'ordine dopo il checkout. | Mostra i dettagli del pagamento del portafoglio. |
| `displayPaymentTop` | Nella parte superiore della pagina di pagamento. | Potrebbe visualizzare il saldo del portafoglio o l'input del codice regalo. |
| `displayAdminOrder` | Nella pagina dei dettagli dell'ordine nel back office. | Aggiunge l'opzione per rimborsare al portafoglio, mostra le informazioni di pagamento del portafoglio. |
| `displayOrderDetail` | Nella pagina dei dettagli dell'ordine del cliente nel front office. | Mostra i dettagli del pagamento del portafoglio. |
| `actionValidateOrder` | Dopo che un ordine è stato convalidato con successo. | Dedurre fondi dal portafoglio, registrare la transazione. |
| `actionOrderStatusPostUpdate` | Dopo che lo stato di un ordine è stato aggiornato. | Potrebbe attivare rimborsi al portafoglio in base al cambio di stato. |
| `actionFrontControllerSetMedia` | Prima che un controller frontale renda il suo contenuto. | Aggiunge CSS e JS specifici del modulo alle pagine del front-office. |
| `actionAdminControllerSetMedia` | Prima che un controller amministrativo renda il suo contenuto. | Aggiunge CSS e JS specifici del modulo alle pagine del back-office. |
| `actionCronJob` (hook personalizzato) | Attivato dal controller cron del modulo. | Esegue attività programmate come controlli di scadenza e promemoria via email. |

## 5. Supporto Ufficiale e Aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e qualsiasi ulteriore assistenza con il modulo "Portafoglio Prepagato e Credito Negozio", si prega di fare riferimento al proprio account cliente su MyPresta.eu. Il nostro team è dedicato a fornire un supporto completo e a garantire che il modulo funzioni senza problemi.

-   **MyPresta.eu Cronologia Ordini e Download:** <https://mypresta.eu/my-account/orders/>
-   **MyPresta.eu Contatto Supporto:** <https://mypresta.eu/contact>
