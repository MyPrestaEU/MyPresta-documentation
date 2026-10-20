---
title: "Mass price change pro - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Mass price change pro di MyPresta.eu."
sidebar:
  label: "Mass price change pro - Manuale del commerciante e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Mass price change pro su MyPresta.eu](https://mypresta.eu/modules/administration-tools/mass-price-change-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/mass-price-change-pro/)
>
> ---


# Mass price change pro

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.0.0 - 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per il funzionamento generale di PrestaShop e sono sufficienti per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

Il modulo "Mass price change pro" fornisce un'interfaccia completa all'interno del Back Office di PrestaShop per definire ed eseguire le modifiche di prezzo. Tutte le impostazioni sono accessibili tramite la pagina di configurazione principale del modulo.

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Gestione moduli > Mass price change pro > Configura)

Accedendo alla pagina di configurazione del modulo, troverai una serie di schede o sezioni progettate per guidarti attraverso il processo di definizione dell'operazione di modifica del prezzo.

#### **Schede / Sezioni principali:**

La configurazione del modulo è tipicamente organizzata in diverse sezioni chiave, spesso presentate come schede o blocchi distinti nella pagina principale. Sebbene le etichette esatte possano variare leggermente tra le versioni, la funzionalità principale rimane coerente:

1. **Cosa fare (WTD):** Definisci il tipo di modifica del prezzo.
2. **Prodotti target:** Seleziona quali prodotti saranno interessati.
3. **Vincoli:** Aggiungi condizioni aggiuntive per il targeting.
4. **Regole:** Definisci regole di prezzo specifiche.
5. **Anteprima:** Visualizza l'impatto prima di applicare.
6. **Cronologia:** Rivedi le operazioni passate.
7. **Pianificatore:** Pianifica future modifiche di prezzo.
8. **Importa/Esporta CSV:** Gestisci i prezzi tramite CSV.
9. **Configurazione Cron:** Configura attività automatizzate.

Esaminiamo ogni sezione in dettaglio:

#### **4.1.1 Cosa fare (WTD)**

Questa sezione è dove definisci l'azione principale della tua modifica di prezzo.

- **Cosa fa questa impostazione:** Determina come verranno modificati i prezzi dei prodotti. Scegli tra aumentare, diminuire o impostare un nuovo prezzo, e se questo si applica al prezzo base, al prezzo specifico o all'impatto sulle combinazioni.
- **Effetto della modifica di questa impostazione:**
  - *Aumenta di percentuale:* Aggiunge una percentuale del prezzo corrente al prodotto.
  - *Diminuisci di percentuale:* Sottrae una percentuale del prezzo corrente dal prodotto.
  - *Aumenta di importo fisso:* Aggiunge un valore monetario specifico al prezzo del prodotto.
  - *Diminuisci di importo fisso:* Sottrae un valore monetario specifico dal prezzo del prodotto.
  - *Imposta nuovo prezzo a:* Sovrascrive il prezzo corrente con un nuovo valore specificato.
  - *Applica al prezzo base:* Modifica il prezzo principale del prodotto.
  - *Applica al prezzo specifico:* Modifica i prezzi impostati tramite le regole "Prezzi specifici" (es. per gruppi, paesi o quantità).
  - *Applica all'impatto sulle combinazioni:* Modifica l'aggiustamento del prezzo per le combinazioni di prodotti (attributi).
- **Valore consigliato:** Dipende interamente dal tuo obiettivo aziendale. Inizia con un obiettivo chiaro (es. "aumentare tutti i prezzi del 5%") prima di selezionare.
- **Scenario / esempio del commerciante:**
  - *Scenario 1 (Inflazione):* "Devo aumentare tutti i prezzi dei miei prodotti del 3% a causa dell'aumento dei costi dei fornitori." -> Seleziona "Aumenta di percentuale", inserisci "3" e scegli "Applica al prezzo base".
  - *Scenario 2 (Vendita di liquidazione):* "Voglio ridurre il prezzo di tutti i prodotti nella categoria 'Collezione Estiva' di $5." -> Seleziona "Diminuisci di importo fisso", inserisci "5" e scegli "Applica al prezzo base".

#### **4.1.2 Prodotti target**

Qui selezioni con precisione *quali* prodotti saranno interessati dalla modifica del prezzo.

- **Cosa fa questa impostazione:** Ti consente di filtrare i prodotti in base a vari criteri come categorie, produttori, fornitori, ID prodotto specifici o persino prodotti senza prezzo specifico.
- **Effetto della modifica di questa impostazione:**
  - *Selezione di categorie:* Verranno considerati solo i prodotti all'interno delle categorie scelte.
  - *Selezione di produttori/fornitori:* Verranno interessati solo i prodotti di questi marchi/fonti.
  - *Inserimento di ID prodotto:* Verranno targettizzati solo i prodotti esatti che elenchi.
  - *Filtro per "Prodotti senza prezzo specifico":* Utile per assicurarsi di non sovrascrivere accidentalmente le regole di prezzo specifico esistenti.
- **Valore consigliato:** Sii il più specifico possibile per evitare modifiche indesiderate. Utilizza più filtri se necessario.
- **Scenario / esempio del commerciante:**
  - *Scenario 1 (Aggiornamento del marchio):* "Il mio fornitore principale, 'Fashionista Co.', ha aumentato i prezzi. Devo aggiornare tutti i prodotti di questo produttore." -> Seleziona "Produttore", quindi scegli "Fashionista Co.".
  - *Scenario 2 (Stock stagionale):* "Voglio mettere in saldo tutti i prodotti nella categoria 'Abbigliamento Invernale'." -> Seleziona "Categoria", quindi scegli "Abbigliamento Invernale".

#### **4.1.3 Vincoli**

Questa sezione ti consente di aggiungere condizioni ancora più specifiche al targeting dei tuoi prodotti.

- **Cosa fa questa impostazione:** Fornisce opzioni di filtraggio avanzate, come il targeting di prodotti all'interno di un certo intervallo di prezzo, prodotti con caratteristiche o attributi specifici, o prodotti attualmente in magazzino.
- **Effetto della modifica di questa impostazione:**
  - *Intervallo di prezzo:* Verranno inclusi solo i prodotti il cui prezzo corrente rientra tra il minimo e il massimo specificati.
  - *Caratteristiche/Attributi:* Targetizza i prodotti che hanno una particolare caratteristica (es. "Colore: Rosso") o attributo (es. "Taglia: XL").
  - *Solo in magazzino:* Assicura che vengano interessati solo i prodotti attualmente disponibili per l'acquisto.
- **Valore consigliato:** Utilizzali per affinare ulteriormente la tua lista target, specialmente per promozioni complesse o aggiustamenti basati sull'inventario.
- **Scenario / esempio del commerciante:**
  - *Scenario 1 (Vendita di prodotti premium):* "Voglio offrire uno sconto su articoli di alto valore. Riduci i prezzi del 10% per tutti i prodotti oltre $100 nella categoria 'Elettronica'." -> In "Prodotti target", seleziona "Elettronica". In "Vincoli", imposta "Intervallo di prezzo" da "$100" a "Max".
  - *Scenario 2 (Liquidazione di stock specifico):* "Devo liquidare tutte le camicie di colore 'Blu' attualmente in magazzino." -> In "Prodotti target", seleziona "Camicie". In "Vincoli", seleziona "Attributo: Colore > Blu" e "Solo in magazzino".

#### **4.1.4 Regole**

Questa sezione ti consente di definire una logica di prezzo più complessa, potenzialmente sovrascrivendo o aggiungendo all'azione generale "Cosa fare".

- **Cosa fa questa impostazione:** Ti consente di creare aggiustamenti di prezzo condizionali. Ad esempio, "Se un prodotto è nella Categoria A, aumenta il suo prezzo del 5%, ma se è nella Categoria B, diminuiscilo del 10%."
- **Effetto della modifica di questa impostazione:** Consente strategie di prezzo altamente sfumate in cui diversi gruppi di prodotti ricevono aggiustamenti diversi all'interno di una singola operazione.
- **Valore consigliato:** Utilizza questa opzione quando una singola e uniforme modifica di prezzo non è sufficiente per tutti i prodotti target.
- **Scenario / esempio del commerciante:**
  - *Scenario (Sconto a livelli):* "Per i prodotti nella categoria 'Accessori', se il loro prezzo è tra $10 e $50, diminuisci del 5%. Se il loro prezzo è superiore a $50, diminuisci del 10%." -> Qui imposteresti più regole, ognuna con il proprio intervallo di prezzo e aggiustamento.

#### **4.1.5 Anteprima**

Prima di impegnare qualsiasi modifica, questa sezione cruciale ti consente di rivedere le modifiche proposte.

- **Cosa fa questa impostazione:** Visualizza un elenco di prodotti che saranno interessati, mostrando il loro prezzo attuale e quale sarà il loro nuovo prezzo dopo l'operazione.
- **Effetto della modifica di questa impostazione:** Questa è una sezione di sola lettura. Fornisce una rete di sicurezza, permettendoti di individuare eventuali errori nel tuo targeting o nelle regole prima che vengano applicati al tuo negozio live.
- **Valore consigliato:** **Rivedi SEMPRE** attentamente l'anteprima prima di procedere con la modifica effettiva del prezzo.
- **Scenario / esempio del commerciante:**
  - *Scenario (Doppio controllo):* "Ho impostato uno sconto del 10% per tutti i 'Vestiti Estivi'. L'anteprima mostra un vestito che so che non dovrebbe essere scontato. Posso tornare a 'Prodotti target' o 'Vincoli' per affinare la mia selezione."

#### **4.1.6 Cronologia**

Questa sezione mantiene un registro di tutte le operazioni di modifica del prezzo passate.

- **Cosa fa questa impostazione:** Mostra un registro di chi ha eseguito quale modifica di prezzo, quando è stata fatta e di che tipo di operazione si trattava.
- **Effetto della modifica di questa impostazione:** Questo è un registro di sola lettura. È inestimabile per l'audit, la risoluzione dei problemi e la comprensione delle decisioni di prezzo passate.
- **Valore consigliato:** Controlla regolarmente la cronologia, specialmente se più persone gestiscono il negozio, per assicurarti che tutte le modifiche siano intenzionali e tracciate.
- **Scenario / esempio del commerciante:**
  - *Scenario (Audit):* "Un cliente ha segnalato un prezzo errato. Posso controllare la cronologia per vedere se una recente modifica di prezzo di massa potrebbe averla causata e chi ha avviato la modifica."

#### **4.1.7 Pianificatore**

Pianifica le tue modifiche di prezzo in modo che vengano eseguite automaticamente in una data e ora future.

- **Cosa fa questa impostazione:** Ti consente di definire un'operazione di modifica del prezzo e impostarla per essere eseguita automaticamente a una data e ora specificate. Puoi anche impostarla per ripristinare i prezzi dopo un certo periodo, perfetto per vendite temporanee.
- **Effetto della modifica di questa impostazione:**
  - *Esecuzione programmata:* La modifica del prezzo verrà applicata senza intervento manuale all'ora scelta.
  - *Ripristina prezzi:* I prodotti torneranno ai loro prezzi originali (o a un prezzo diverso specificato) dopo la fine del periodo di vendita.
- **Valore consigliato:** Essenziale per la gestione di promozioni, vendite stagionali o qualsiasi modifica di prezzo che debba andare online al di fuori dell'orario di lavoro.
- **Scenario / esempio del commerciante:**
  - *Scenario (Vendita Black Friday):* "Voglio applicare uno sconto del 20% a tutti i prodotti alle 00:00 del Black Friday e ripristinare i prezzi originali alle 23:59 del Cyber Monday." -> Imposta l'operazione di sconto, pianificala per il Black Friday e aggiungi una pianificazione di ripristino per il Cyber Monday.

#### **4.1.8 Importa/Esporta CSV**

Gestisci i prezzi dei tuoi prodotti utilizzando file CSV per un controllo avanzato o la manipolazione di dati esterni.

- **Cosa fa questa impostazione:**
  - *Esporta:* Ti consente di esportare un elenco di prodotti (in base ai tuoi criteri di targeting) con i loro prezzi attuali in un file CSV.
  - *Importa:* Ti consente di caricare un file CSV contenente ID prodotto e nuovi prezzi, applicando queste modifiche al tuo negozio.
- **Effetto della modifica di questa impostazione:**
  - *Esporta:* Fornisce un foglio di calcolo dei tuoi prodotti target e dei loro prezzi, che può essere modificato esternamente.
  - *Importa:* Sovrascrive o aggiorna i prezzi per i prodotti elencati nel CSV, offrendo un modo potente per gestire elenchi di prezzi grandi e complessi.
- **Valore consigliato:** Utilizza l'esportazione per analisi dettagliate o quando devi apportare aggiustamenti di prezzo molto specifici e non formulari che sono più facili da gestire in un foglio di calcolo. Utilizza l'importazione quando hai un elenco predefinito di nuovi prezzi da un fornitore o da un sistema esterno.
- **Scenario / esempio del commerciante:**
  - *Scenario (Listino prezzi fornitore):* "Il mio fornitore mi ha inviato un nuovo listino prezzi per 500 prodotti. Invece di aggiornare manualmente ciascuno, posso esportare il mio elenco prodotti attuale, confrontarlo con quello del fornitore, regolare i prezzi nel CSV e quindi importarlo di nuovo."

#### **4.1.9 Configurazione Cron**

Configura il cron job del modulo per attività automatizzate, in particolare per le modifiche di prezzo programmate.

- **Cosa fa questa impostazione:** Fornisce il comando o l'URL necessario per impostare un cron job sul tuo server. Questo cron job è essenziale affinché la funzione "Pianificatore" funzioni, poiché controlla periodicamente ed esegue le modifiche di prezzo programmate.
- **Effetto della modifica di questa impostazione:**
  - *Corretta configurazione Cron:* Assicura che le modifiche di prezzo programmate vengano eseguite automaticamente agli orari specificati. Senza un cron job configurato correttamente, le attività programmate non verranno eseguite.
- **Valore consigliato:** Segui le istruzioni fornite dal modulo per impostare il cron job sul tuo server di hosting. Tipicamente, questo comporta l'aggiunta di una riga al crontab del tuo server. Il modulo di solito fornisce il comando esatto.
- **Scenario / esempio del commerciante:**
  - *Scenario (Vendite automatizzate):* "Ho programmato una vendita flash per la prossima settimana. Per assicurarmi che inizi esattamente in orario, devo assicurarmi che il cron job sia configurato correttamente e funzioni ogni 5-15 minuti." -> Copia il comando cron fornito e aggiungilo al gestore cron del tuo server.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Cosa fare** | Tipo di operazione (Aumenta/Diminuisci/Imposta) | N/A (dipende dall'obiettivo) | Definisce come vengono modificati i prezzi (es. +5%, -$10, imposta a $25). |
|  | Valore (Percentuale/Fisso) | N/A (dipende dall'obiettivo) | L'importo o la percentuale dell'aggiustamento del prezzo. |
|  | Applica a (Base/Specifico/Combinazioni) | Prezzo base | Determina quale tipo di prezzo è interessato. |
| **Prodotti target** | Categorie | Seleziona specifiche | Filtra i prodotti per categoria. |
|  | Produttori | Seleziona specifici | Filtra i prodotti per marchio. |
|  | Fornitori | Seleziona specifici | Filtra i prodotti per fornitore. |
|  | ID prodotto | Inserisci elenco | Targetizza prodotti specifici per ID. |
|  | Prodotti senza prezzo specifico | Sì/No | Esclude i prodotti con prezzi specifici esistenti. |
| **Vincoli** | Intervallo di prezzo (Min/Max) | N/A (opzionale) | Filtra i prodotti all'interno di una fascia di prezzo. |
|  | Caratteristiche / Attributi | Seleziona specifici | Filtra i prodotti in base alle loro caratteristiche o attributi. |
|  | Solo in magazzino | Sì/No | Influisce solo sui prodotti attualmente in magazzino. |
| **Regole** | Aggiungi regola | N/A (opzionale) | Definisce aggiustamenti di prezzo condizionali basati su criteri. |
| **Anteprima** | (Tabella di sola lettura) | N/A | Mostra i prezzi attuali rispetto ai nuovi prezzi per i prodotti interessati. **Rivedi sempre!** |
| **Cronologia** | (Registro di sola lettura) | N/A | Registra tutte le operazioni di modifica del prezzo passate. |
| **Pianificatore** | Pianifica operazione | N/A (opzionale) | Imposta una data/ora futura per l'esecuzione automatica delle modifiche di prezzo. |
|  | Ripristina prezzi | N/A (opzionale) | Pianifica un ripristino dei prezzi dopo un periodo stabilito. |
| **Importa/Esporta CSV** | Esporta prodotti | N/A (opzionale) | Scarica i dati dei prodotti target per la modifica esterna. |
|  | Importa prezzi | N/A (opzionale) | Carica un CSV per applicare nuovi prezzi ai prodotti. |
| **Configurazione Cron** | Comando Cron | Copia dal modulo | Essenziale per le attività programmate automatizzate. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei prezzi non sono cambiati dopo aver applicato l'operazione. Cosa è andato storto?**
R1:

- **Controlla la scheda Cronologia:** Verifica che l'operazione sia stata registrata e completata con successo.
- **Svuota la cache:** PrestaShop utilizza la cache. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache". Il tuo browser potrebbe anche memorizzare dati vecchi nella cache, quindi prova a svuotare la cache del browser o a visualizzare il negozio in modalità incognito.
- **Controlla il targeting:** Rivedi le impostazioni di "Prodotti target" e "Vincoli". Hai accidentalmente escluso i prodotti che intendevi modificare?
- **Prezzi specifici:** Se stavi cercando di modificare i prezzi base ma i prodotti hanno prezzi specifici, i prezzi specifici potrebbero sovrascriverli. Controlla se la tua operazione era impostata per influenzare "Prezzi specifici" o "Prezzo base".

**D2: La mia modifica di prezzo programmata non è stata eseguita all'ora specificata.**
R2:

- **Cron Job:** La ragione più comune per questo è un cron job configurato in modo errato o non in esecuzione. Vai alla scheda **Configurazione Cron** nella configurazione del modulo. Assicurati che il comando cron fornito sia stato aggiunto correttamente al crontab del tuo server e che sia in esecuzione alla frequenza consigliata (es. ogni 5-15 minuti). Se non sei sicuro di come farlo, contatta il tuo provider di hosting o un webmaster.
- **Modulo abilitato:** Assicurati che il modulo "Mass price change pro" sia ancora abilitato nel tuo Gestore moduli.

**D3: Ho accidentalmente cambiato i prezzi sbagliati. Posso annullare le modifiche?**
R3:

- **Scheda Cronologia:** La scheda "Cronologia" del modulo spesso offre un'opzione per annullare un'operazione precedente. Cerca un pulsante "Annulla" o "Ripristina" accanto all'operazione specifica che desideri annullare.
- **Backup del database:** Se un'opzione di ripristino non è disponibile o non funziona come previsto, ciò evidenzia l'importanza di avere un backup recente del database. Dovresti ripristinare il tuo database a un punto precedente alla modifica errata del prezzo. **Esegui sempre un backup prima di operazioni importanti!**

**D4: Il modulo non viene visualizzato correttamente o causa errori dopo l'installazione.**
R4:

- **Versione PrestaShop:** Assicurati di aver scaricato e installato la versione corretta del modulo per la tua specifica installazione di PrestaShop (es. PrestaShop 8.x, 1.7.x).
- **Compatibilità PHP:** Verifica che la versione PHP del tuo server rientri nell'intervallo supportato dal modulo (PHP 5.6 - 8.5).
- **Conflitti con il tema:** A volte, i temi personalizzati possono interferire. Passa temporaneamente al tema predefinito di PrestaShop per vedere se il problema si risolve. In tal caso, il tuo tema potrebbe richiedere degli aggiustamenti.
- **Log degli errori:** Controlla la modalità di debug di PrestaShop (se abilitata) o i log degli errori PHP del tuo server per messaggi di errore specifici. Questi possono fornire indizi agli sviluppatori.

**D5: Come posso tradurre il testo del modulo in altre lingue?**
R5:

- Nel tuo Back Office di PrestaShop, naviga su **Internazionale > Traduzioni**.
- Seleziona "Traduzioni dei moduli installati", scegli il tuo tema e quindi seleziona "Mass price change pro" dal menu a discesa del modulo.
- Potrai quindi tradurre tutte le stringhe del modulo nelle lingue desiderate.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster che lavorano con il modulo "Mass price change pro".

### 4.1 Panoramica dell'architettura

Il modulo "Mass price change pro" segue un'architettura standard per i moduli PrestaShop, sfruttando principalmente la classe `Module` per la sua funzionalità principale e `ModuleFrontController` per attività specifiche del front-office come l'esecuzione del cron. Il modulo si basa fortemente sul suo `index.php` (file principale del modulo) per la configurazione e l'elaborazione del back-office, utilizzando i template Smarty per il rendering delle varie sezioni di configurazione. Integra JavaScript personalizzato per elementi UI migliorati come il targeting dei prodotti e l'autocomplete, e CSS per lo stile. Sebbene non definisca esplicitamente classi `ObjectModel` nell'inventario fornito, probabilmente interagisce direttamente con le tabelle `Product`, `SpecificPrice` e `Configuration` del core di PrestaShop.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

- `controllers/front/cron.php`
  - **Nome classe:** `MassPriceProCronModuleFrontController` (probabilmente, basato sulla convenzione di denominazione dei file)
  - **Classe genitore:** `ModuleFrontController`
  - **Responsabilità:** Questo controller è progettato per essere chiamato da un cron job lato server. Il suo ruolo principale è quello di eseguire operazioni di modifica del prezzo programmate definite all'interno della configurazione del back-office del modulo. Elabora attività come l'applicazione di sconti programmati, il ripristino dei prezzi o l'esecuzione di altri aggiustamenti automatici dei prezzi. Tipicamente restituisce un semplice messaggio di successo/fallimento o registra la sua attività.
- `controllers/front/index.php`
  - **Nome classe:** `MassPriceProIndexModuleFrontController` (probabilmente)
  - **Classe genitore:** `ModuleFrontController`
  - **Responsabilità:** Questo controller potrebbe fungere da punto di ingresso generale per le azioni del modulo nel front-office che non rientrano in una categoria specifica, oppure potrebbe essere un segnaposto. Data la natura del modulo, è meno probabile che abbia funzionalità direttamente rivolte al cliente e più probabile che gestisca richieste AJAX in background o recupero di dati specifici se necessario dagli script front-end.

#### Controller Admin Back-Office

Il modulo non sembra utilizzare file `AdminController` dedicati in base all'inventario fornito. Tutta la configurazione e l'elaborazione del back-office sono probabilmente gestite direttamente all'interno del metodo `getContent()` del file principale `masspricepro/index.php`.

### 4.3 Classi e modelli principali (`classes/`)

In base all'inventario fornito, non ci sono classi personalizzate o definizioni `ObjectModel` all'interno di una directory `classes/`. Ciò suggerisce che il modulo interagisce direttamente con le classi `ObjectModel` principali di PrestaShop `Product`, `SpecificPrice`, `Category`, `Manufacturer`, `Supplier`, `Configuration` e potenzialmente altre classi correlate e le loro tabelle di database associate. La logica di modifica del prezzo è probabilmente incapsulata all'interno dei metodi della classe principale `MassPricePro` (in `index.php`).

### 4.4 Risorse JavaScript (`views/js/`)

- `masspricepro/lib/searchTool/views/js/autocomplete.js`
  - **Ambito:** Probabilmente sia Front-office (se usato per la ricerca prodotti) che Back-office (per il targeting prodotti).
  - **Dettagli:** Fornisce funzionalità generiche di autocompletamento. Ascolta l'input dell'utente nei campi di testo, invia richieste AJAX a un endpoint backend (possibilmente `controllers/front/index.php` o un gestore AJAX dedicato nel file principale del modulo) e visualizza suggerimenti in un elenco a discesa.
- `masspricepro/views/js/jquery.autocomplete.js`
  - **Ambito:** Probabilmente Back-office.
  - **Dettagli:** Un plugin di autocompletamento basato su jQuery. Questa potrebbe essere un'implementazione specifica o una dipendenza per le interfacce di selezione dei prodotti del modulo nel back office, ad esempio quando si targetizzano prodotti per nome o ID. Gestisce il rendering dell'interfaccia utente dei suggerimenti e gli eventi di selezione.
- `masspricepro/views/js/mpp_pro.js`
  - **Ambito:** Back-office.
  - **Dettagli:** Questo è probabilmente il file JavaScript principale per la configurazione del back-office del modulo. Contiene:
    - Listener di eventi per l'invio di moduli, i cambi di scheda, i clic sui pulsanti (es. "Applica modifiche", "Anteprima", "Aggiungi regola").
    - Chiamate AJAX al metodo `getContent()` o a un controller front-end per l'elaborazione dei dati (es. generazione di anteprime, salvataggio delle impostazioni, esecuzione delle modifiche di prezzo).
    - Manipolazione del DOM per mostrare/nascondere dinamicamente sezioni, aggiornare tabelle di anteprima o gestire gli input delle regole.
    - Logica di convalida per i campi del modulo.
- `masspricepro/views/js/mpp_target_products.js`
  - **Ambito:** Back-office.
  - **Dettagli:** Gestisce specificamente la logica per la sezione "Prodotti target" del modulo. Ciò include:
    - Gestione della selezione di categorie, produttori, fornitori (es. utilizzando menu a discesa a selezione multipla o viste ad albero).
    - Gestione dell'input per gli ID prodotto, potenzialmente con convalida.
    - Interazione con gli script di autocompletamento per consentire agli amministratori di cercare e selezionare prodotti.
    - Aggiornamento dinamico dell'elenco dei prodotti target selezionati.

### 4.5 Fogli di stile CSS (`views/css/`)

- `masspricepro/lib/searchTool/views/css/autocomplete.css`
  - **Ambito:** Sia Front-office che Back-office.
  - **Dettagli:** Fornisce lo stile per i menu a discesa dei suggerimenti di autocompletamento e i campi di input, assicurando che siano visivamente coerenti e facili da usare.
- `masspricepro/views/css/mpp_admin.css`
  - **Ambito:** Stile del modulo di amministrazione del Back-office.
  - **Dettagli:** Questo è il foglio di stile principale per l'interfaccia di configurazione del modulo nel Back Office di PrestaShop. Stila:
    - Il layout delle schede/sezioni di configurazione.
    - Gli elementi del modulo (input, pulsanti, select, checkbox).
    - Le tabelle (es. per la cronologia, l'anteprima).
    - Eventuali componenti UI personalizzati specifici del modulo.
    - Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere: `.mpp-container`, `.mpp-tab-content`, `.mpp-form-group`, `.mpp-table`, ecc.

### 4.6 Struttura del template Smarty (`views/templates/`)

#### Template Admin (`views/templates/admin/`)

Questi template vengono renderizzati all'interno del metodo `getContent()` del file principale del modulo per costruire l'interfaccia di configurazione del back-office.

- `constraints.tpl`: Renderizza la sezione per definire vincoli aggiuntivi (es. intervallo di prezzo, caratteristiche, attributi).
- `cron_setup.tpl`: Visualizza le istruzioni e il comando per impostare il cron job del server.
- `csv.tpl`: Renderizza l'interfaccia per la funzionalità di importazione CSV.
- `csv_export_target.tpl`: Renderizza l'interfaccia per la funzionalità di esportazione CSV, specificamente per i prodotti target.
- `history.tpl`: Visualizza la tabella e i dettagli delle operazioni di modifica del prezzo passate.
- `mpp_operation_block.tpl`: Probabilmente un blocco riutilizzabile per definire una singola operazione di modifica del prezzo (aumenta/diminuisci/imposta).
- `mpp_target_block.tpl`: Probabilmente un blocco riutilizzabile per definire i criteri di targeting dei prodotti.
- `mpp_target_products_full.tpl`: Renderizza l'interfaccia completa per la selezione dei prodotti target, possibilmente includendo campi di autocompletamento ed elenchi di prodotti selezionati.
- `preview.tpl`: Visualizza la tabella che mostra i prezzi attuali e i nuovi prezzi proposti prima dell'esecuzione.
- `rules.tpl`: Renderizza l'interfaccia per definire regole di prezzo condizionali.
- `scheduler.tpl`: Visualizza il modulo per la pianificazione di future modifiche e ripristini dei prezzi.
- `target_products.tpl`: Un template più conciso o alternativo per il targeting dei prodotti, potenzialmente utilizzato all'interno di altre sezioni.
- `wtd.tpl`: Renderizza la sezione "Cosa fare", dove viene selezionato il tipo principale di aggiustamento del prezzo.

#### Template Hook (`views/templates/hook/`)

- `form.tpl`: Questo template è probabilmente utilizzato per renderizzare il modulo di configurazione principale o una parte specifica di esso quando il modulo è agganciato a un hook di visualizzazione generico (anche se il modulo utilizza principalmente `getContent()` per la sua configurazione principale). Dato lo scopo del modulo, è improbabile che visualizzi qualcosa direttamente nel front office tramite hook come `displayHeader` o `displayFooter`, ma piuttosto utilizza questi hook per caricare risorse o per l'elaborazione interna.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

Il modulo non crea tabelle SQL personalizzate in base all'inventario fornito. Si basa principalmente sulle tabelle principali di PrestaShop:

- `ps_product`: Per i prezzi base dei prodotti.
- `ps_product_shop`: Per i prezzi dei prodotti specifici del negozio.
- `ps_specific_price`: Per le regole di prezzo specifiche.
- `ps_product_attribute`, `ps_product_attribute_shop`: Per i prezzi e gli impatti delle combinazioni.
- `ps_category_product`, `ps_manufacturer`, `ps_supplier`: Per il targeting dei prodotti.
- `ps_configuration`: Per memorizzare le impostazioni e i valori di configurazione del modulo (es. `MPP_LAST_OPERATION_DATE`, `MPP_CRON_TOKEN`, `MPP_SCHEDULED_TASKS`).

#### Tabella degli hook registrati

Il modulo probabilmente registra gli hook per integrarsi con il ciclo di vita di PrestaShop e visualizzare le risorse.

| Nome Hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Per caricare CSS specifici del modulo (`mpp_admin.css` se necessario per qualche motivo, anche se improbabile per il front-office) e JavaScript (`autocomplete.js`, `jquery.autocomplete.js` se usato per la ricerca front-end). |
| `actionModuleInstall` | Durante l'installazione del modulo. | Per eseguire la configurazione iniziale, creare voci di configurazione e registrare altri hook. |
| `actionModuleUninstall` | Durante la disinstallazione del modulo. | Per pulire le voci di configurazione e annullare la registrazione degli hook. |
| `actionAdminControllerSetMedia` | Quando viene caricato un controller admin. | Per caricare CSS specifici del Back-office (`mpp_admin.css`) e JavaScript (`mpp_pro.js`, `mpp_target_products.js`, `autocomplete.js`) per la pagina di configurazione del modulo. |
| `actionScheduler` (o hook personalizzato simile) | Attivato dal cron job del modulo. | Per eseguire le modifiche di prezzo programmate e le operazioni di ripristino. Questo è un hook interno personalizzato o un metodo chiamato dal controller `cron.php`. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Mass price change pro", si prega di fare riferimento al proprio account cliente su MyPresta.eu. È possibile scaricare le versioni più recenti dalla cronologia degli ordini e accedere alle risorse di supporto direttamente tramite la piattaforma.
