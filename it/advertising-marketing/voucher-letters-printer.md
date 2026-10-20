---
title: "Stampante Voucher & Lettere - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Stampante Voucher & Lettere di MyPresta.eu."
sidebar:
  label: "Stampante Voucher & Lettere - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Voucher & Letters Printer su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/voucher-letters-printer.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/voucher-letters-printer/)
>
> ---


# Stampante Voucher & Lettere

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL). Nessun requisito di hosting speciale oltre a una tipica configurazione PrestaShop.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Stampante Voucher & Lettere)

Questa è la schermata di configurazione principale dove definirai i parametri per i tuoi voucher e lettere.

#### **Impostazioni Generali**

- **Cosa fa questa impostazione:** Queste impostazioni controllano il comportamento generale e l'aspetto dei voucher e delle lettere generate.
- **Effetto della modifica di questa impostazione:** Le modifiche qui avranno un impatto diretto sul contenuto e sul formato dei documenti che stampi.

#### **Generazione Codice Voucher**

- **Prefisso Voucher:**

  - **Cosa fa questa impostazione:** Questo testo verrà aggiunto all'inizio di ogni codice voucher generato. Ti aiuta a identificare la fonte del voucher (es. "BENVENUTO-", "FEDELTÀ-").
  - **Effetto della modifica di questa impostazione:**
    - *Se impostato su "SALDI-":* Tutti i codici generati inizieranno con "SALDI-", come "SALDI-ABC123XYZ".
    - *Se lasciato vuoto:* I codici saranno caratteri puramente casuali, es. "ABC123XYZ".
  - **Valore consigliato:** Un prefisso breve e descrittivo relativo alla tua campagna.
  - **Scenario / esempio commerciante:** Se stai inviando un premio fedeltà, usa "FEDELTÀ-". Per una vendita stagionale, "ESTATE-".
- **Suffisso Voucher:**

  - **Cosa fa questa impostazione:** Simile al prefisso, questo testo verrà aggiunto alla fine di ogni codice voucher generato.
  - **Effetto della modifica di questa impostazione:**
    - *Se impostato su "-2024":* Tutti i codici generati termineranno con "-2024", come "ABC123XYZ-2024".
    - *Se lasciato vuoto:* I codici non avranno un suffisso.
  - **Valore consigliato:** Lasciare vuoto a meno che tu non abbia una specifica esigenza di tracciamento.
  - **Scenario / esempio commerciante:** Potresti usare un suffisso dell'anno come "-2024" per campagne annuali.
- **Lunghezza Codice Voucher (escluso prefisso/suffisso):**

  - **Cosa fa questa impostazione:** Determina il numero di caratteri casuali nel codice voucher stesso, tra il prefisso e il suffisso. Un codice più lungo è più sicuro ma più difficile da digitare.
  - **Effetto della modifica di questa impostazione:**
    - *Se impostato su 8:* I codici avranno 8 caratteri casuali (es. "ABC123XY").
    - *Se impostato su 12:* I codici avranno 12 caratteri casuali (es. "ABC123XYZ456").
  - **Valore consigliato:** 8-12 caratteri per un buon equilibrio tra sicurezza e usabilità.
  - **Scenario / esempio commerciante:** Per una promozione generale, 8 caratteri sono solitamente sufficienti. Per voucher esclusivi di alto valore, potresti optare per 10-12.

#### **Contenuto Voucher & Lettera**

- **Valore Voucher:**

  - **Cosa fa questa impostazione:** Questo è il valore monetario o la percentuale di sconto che il voucher generato fornirà.
  - **Effetto della modifica di questa impostazione:**
    - *Se impostato su "10":* Il voucher garantirà uno sconto di 10 unità (es. €10, $10).
    - *Se impostato su "20%":* Il voucher garantirà uno sconto del 20%.
  - **Valore consigliato:** Un valore che incoraggi gli acquisti senza influire significativamente sui tuoi margini.
  - **Scenario / esempio commerciante:** Offri €15 di sconto per un ordine minimo di €100, o il 10% di sconto sull'intero carrello.
- **Importo Minimo Voucher:**

  - **Cosa fa questa impostazione:** Il totale minimo dell'ordine (prima della spedizione) richiesto affinché il cliente possa utilizzare il voucher.
  - **Effetto della modifica di questa impostazione:**
    - *Se impostato su "50":* I clienti devono spendere almeno €50 per utilizzare il voucher.
    - *Se impostato su "0" o lasciato vuoto:* Non è richiesto un acquisto minimo.
  - **Valore consigliato:** Imposta un importo minimo per garantire la redditività, tipicamente 2-3 volte il valore del voucher.
  - **Scenario / esempio commerciante:** Se il voucher è di €10, imposta un minimo di €30 per incoraggiare un acquisto più grande.
- **Data di Scadenza Voucher (Giorni dalla Generazione):**

  - **Cosa fa questa impostazione:** Definisce quanti giorni dopo la generazione del voucher questo scadrà. Questo crea urgenza.
  - **Effetto della modifica di questa impostazione:**
    - *Se impostato su "30":* Il voucher sarà valido per 30 giorni dalla data di creazione.
    - *Se impostato su "0" o lasciato vuoto:* Il voucher non avrà una data di scadenza (non consigliato per la maggior parte delle campagne).
  - **Valore consigliato:** 30-90 giorni, a seconda dell'urgenza che vuoi creare.
  - **Scenario / esempio commerciante:** Per una vendita rapida, 30 giorni. Per un premio fedeltà, 90 giorni.
- **Testo Intestazione Lettera:**

  - **Cosa fa questa impostazione:** Questo è il titolo principale o il saluto che apparirà in cima alla tua lettera personalizzata.
  - **Effetto della modifica di questa impostazione:**
    - *Se impostato su "Gentile Cliente Valutato,":* Questa sarà la riga di apertura di ogni lettera.
    - *Se impostato su "Un'Offerta Speciale Solo Per Te!":* Questo sarà l'intestazione prominente.
  - **Valore consigliato:** Un saluto caloroso e personale.
  - **Scenario / esempio commerciante:** "Ciao [Nome Cliente]," (se prevedi di inserire manualmente i nomi o utilizzare uno strumento di stampa unione in seguito) o "Grazie per essere un Cliente Fedele!"
- **Testo Corpo Lettera:**

  - **Cosa fa questa impostazione:** Questo è il contenuto principale della tua lettera, dove spieghi l'offerta, ringrazi il cliente e fornisci qualsiasi altra informazione rilevante. Puoi usare segnaposto per contenuti dinamici (anche se il modulo stesso non offre segnaposto diretti, in genere useresti uno strumento di stampa unione per questo dopo l'esportazione).
  - **Effetto della modifica di questa impostazione:** Questo testo formerà il messaggio centrale della tua lettera fisica.
  - **Valore consigliato:** Testo chiaro, conciso e persuasivo che spieghi i vantaggi del voucher e incoraggi il riscatto.
  - **Scenario / esempio commerciante:** "Come segno del nostro apprezzamento, goditi [Valore Voucher] di sconto sul tuo prossimo acquisto di [Importo Minimo]. Usa il codice: [Codice Voucher]. Valido fino a [Data di Scadenza]."
- **Testo Piè di Pagina Lettera:**

  - **Cosa fa questa impostazione:** Questo testo appare in fondo alla tua lettera, tipicamente per le informazioni di contatto del tuo negozio, il sito web o un commento di chiusura.
  - **Effetto della modifica di questa impostazione:** Questa sarà la sezione di chiusura della tua lettera.
  - **Valore consigliato:** Il sito web del tuo negozio, l'email di contatto o una chiusura amichevole come "Cordiali saluti, Il Team di [Nome del tuo negozio]."
  - **Scenario / esempio commerciante:** "Visitaci su [www.iltuonegozio.com](http://www.iltuonegozio.com) per altri prodotti fantastici!"

#### **Opzioni di Stampa e Design**

- **Stampa Codice Voucher sulla Lettera:**

  - **Cosa fa questa impostazione:** Un semplice interruttore per includere il codice voucher generato direttamente all'interno della lettera stampata.
  - **Effetto della modifica di questa impostazione:**
    - *Se abilitato (SÌ):* Il codice voucher unico verrà automaticamente inserito nel corpo della lettera dove specificato (o in una posizione predefinita se non specificato nel testo del corpo).
    - *Se disabilitato (NO):* Il codice voucher non verrà stampato sulla lettera. Potresti scegliere questa opzione se stai stampando carte voucher separate.
  - **Valore consigliato:** SÌ, per comodità e per assicurarsi che il cliente abbia il codice.
  - **Scenario / esempio commerciante:** Se desideri un unico documento per il cliente, abilita questa opzione.
- **Colore Testo (per Lettera/Voucher):**

  - **Cosa fa questa impostazione:** Ti permette di scegliere il colore del testo sui tuoi documenti stampati.
  - **Effetto della modifica di questa impostazione:** Cambia il colore dell'inchiostro utilizzato per il testo.
  - **Valore consigliato:** Nero o un colore scuro e leggibile che contrasti bene con la carta bianca.
  - **Scenario / esempio commerciante:** Usa il colore del testo primario del tuo brand per coerenza.
- **Colore Sfondo (per Sezione Voucher):**

  - **Cosa fa questa impostazione:** Se stai stampando i voucher direttamente sulla lettera, questa imposta un colore di sfondo per l'area del codice voucher per farlo risaltare.
  - **Effetto della modifica di questa impostazione:** Crea una casella colorata dietro il codice voucher.
  - **Valore consigliato:** Un colore chiaro e sottile che non oscuri il testo, o lascialo bianco se preferisci.
  - **Scenario / esempio commerciante:** Un grigio chiaro o una versione pastello del colore del tuo brand per evidenziare il voucher.
- **Dimensione Carattere (per Lettera/Voucher):**

  - **Cosa fa questa impostazione:** Controlla la dimensione del testo sui tuoi documenti stampati.
  - **Effetto della modifica di questa impostazione:**
    - *Se impostato su "12px":* Il testo avrà una dimensione standard leggibile.
    - *Se impostato su "16px":* Il testo sarà più grande, più facile da leggere per alcuni.
  - **Valore consigliato:** 10-14px per il testo del corpo, leggermente più grande per le intestazioni.
  - **Scenario / esempio commerciante:** Se il tuo pubblico di riferimento include demografie più anziane, una dimensione del carattere leggermente più grande potrebbe essere vantaggiosa.

#### **Selezione e Generazione Clienti**

- **Seleziona Clienti:**

  - **Cosa fa questa impostazione:** Questa sezione ti permette di scegliere quali clienti riceveranno le lettere e i voucher personalizzati. Puoi selezionare clienti specifici da un elenco.
  - **Effetto della modifica di questa impostazione:** Solo i clienti selezionati avranno voucher generati per loro, e i loro dettagli verranno utilizzati per le lettere.
  - **Valore consigliato:** Seleziona i clienti in base agli obiettivi della tua campagna (es. nuovi clienti, clienti fedeli, clienti inattivi).
  - **Scenario / esempio commerciante:** Seleziona tutti i clienti che non hanno acquistato negli ultimi 6 mesi per riattivarli.
- **Pulsante Genera Voucher & Lettere:**

  - **Cosa fa questa impostazione:** Dopo aver configurato tutte le impostazioni e selezionato i clienti, cliccando su questo pulsante si avvierà il processo di generazione dei codici voucher unici e la preparazione delle lettere personalizzate per la stampa.
  - **Effetto della modifica di questa impostazione:** Questa azione crea nuove regole carrello (voucher) nel tuo negozio PrestaShop e genera i documenti stampabili.
  - **Valore consigliato:** Clicca solo dopo aver esaminato attentamente tutte le impostazioni.
  - **Scenario / esempio commerciante:** Una volta pianificata una campagna, clicca qui per preparare l'invio.

#### **Tabella di Riferimento Rapido della Configurazione**

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Principale | Prefisso Voucher | `FEDELTÀ-` | Testo all'inizio del codice voucher. Aiuta a identificare la campagna. |
| Configurazione Principale | Suffisso Voucher | Vuoto | Testo alla fine del codice voucher. Utile per il tracciamento. |
| Configurazione Principale | Lunghezza Codice Voucher | 8-12 | Numero di caratteri casuali nel codice. Influisce su sicurezza/usabilità. |
| Configurazione Principale | Valore Voucher | `10` (es. €10 o 10%) | Importo o percentuale di sconto. |
| Configurazione Principale | Importo Minimo Voucher | `0` (o 2-3x valore voucher) | Ordine minimo per l'uso del voucher. Garantisce la redditività. |
| Configurazione Principale | Data di Scadenza Voucher (Giorni) | `30-90` | Giorni fino alla scadenza del voucher. Crea urgenza. |
| Configurazione Principale | Testo Intestazione Lettera | `Gentile Cliente Valutato,` | Saluto/titolo principale della lettera. |
| Configurazione Principale | Testo Corpo Lettera | (Messaggio personalizzato) | Contenuto principale della lettera, che spiega l'offerta. |
| Configurazione Principale | Testo Piè di Pagina Lettera | `www.iltuonegozio.com` | Commenti di chiusura, informazioni di contatto. |
| Configurazione Principale | Stampa Codice Voucher sulla Lettera | SÌ | Include il codice voucher direttamente sulla lettera. |
| Configurazione Principale | Colore Testo | Nero | Colore di tutto il testo sui documenti stampati. |
| Configurazione Principale | Colore Sfondo | Bianco (o grigio chiaro) | Colore di sfondo per l'area del codice voucher. |
| Configurazione Principale | Dimensione Carattere | `12px` | Dimensione del testo sui documenti stampati. |
| Configurazione Principale | Seleziona Clienti | (Selezione specifica) | Scegli quali clienti ricevono l'invio. |
| Configurazione Principale | Genera Voucher & Lettere | (Clic sul pulsante) | Crea voucher e documenti stampabili. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho generato dei voucher, ma non sembrano funzionare nel mio negozio.**
R1: Dopo la generazione, il modulo crea "Regole Carrello" in PrestaShop.
1. **Controlla le Regole Carrello:** Vai su **Catalogo > Sconti > Regole Carrello** nel tuo Back Office. Assicurati che i voucher generati siano elencati lì e siano "Abilitati".
2. **Controlla le Condizioni:** Verifica che le condizioni del voucher (importo minimo, data di scadenza, restrizioni per i clienti) corrispondano a quanto intendevi. Se un cliente tenta di utilizzare un voucher che non soddisfa i criteri, non verrà applicato.
3. **Svuota la Cache:** A volte la cache di PrestaShop può impedire che le nuove impostazioni abbiano effetto immediatamente. Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota la cache".

**D2: Le lettere stampate non hanno un bell'aspetto, o i colori sono spenti.**
R2:
1. **Controlla le Impostazioni del Modulo:** Rivedi la pagina di configurazione del modulo. Ricontrolla le impostazioni di "Colore Testo", "Colore Sfondo" e "Dimensione Carattere". Assicurati di aver selezionato colori che stampano bene.
2. **Impostazioni della Stampante:** La qualità finale dell'output dipende molto dalla tua stampante fisica. Controlla i livelli di inchiostro della stampante, il tipo di carta e le impostazioni di qualità di stampa. Prova a stampare una pagina di prova da un'altra applicazione.
3. **Anteprima di Stampa del Browser:** Quando avvii la stampa dal tuo browser, usa la funzione di anteprima di stampa per vedere come apparirà prima di consumare inchiostro e carta. Regola le impostazioni di stampa del browser (ad esempio, margini, intestazioni/piè di pagina) se necessario.

**D3: Posso tradurre il contenuto della lettera in diverse lingue per i clienti internazionali?**
R3: La versione attuale del modulo non offre campi multilingue integrati per il contenuto della lettera direttamente nella sua configurazione. Dovresti:
1. **Generare per ogni lingua:** Configura il modulo con il contenuto della lettera in una lingua, genera le lettere per i clienti pertinenti, quindi ripeti il processo per altre lingue e gruppi di clienti.
2. **Traduzione manuale:** Se esporti i dati dei clienti e i codici voucher, potresti utilizzare uno strumento di stampa unione separato per creare lettere multilingue.

**D4: Voglio inviare lettere solo a clienti di un paese specifico. Come posso farlo?**
R4: La funzione "Seleziona Clienti" del modulo ti consente di scegliere singoli clienti. Se hai bisogno di filtrare per paese o altri criteri, in genere dovresti:
1. **Esporta i Dati dei Clienti:** Vai su **Clienti > Clienti** nel tuo Back Office e usa la funzione di esportazione per ottenere un elenco di tutti i tuoi clienti.
2. **Filtra Esternamente:** Usa un programma di foglio di calcolo (come Excel o Google Sheets) per filtrare il tuo elenco di clienti per paese o qualsiasi altro criterio desiderato.
3. **Selezione Manuale:** Torna al modulo e seleziona manualmente i clienti filtrati dall'elenco. Questo può essere noioso per elenchi di grandi dimensioni.
4. **Personalizzazione dello Sviluppatore (Avanzato):** Per esigenze di filtraggio molto grandi o complesse, uno sviluppatore potrebbe estendere il modulo per aggiungere opzioni di filtraggio clienti più avanzate.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster che lavorano con il modulo "Stampante Voucher & Lettere".

### 4.1 Panoramica dell'Architettura

Il modulo "Stampante Voucher & Lettere" è un modulo PrestaShop standard che opera principalmente nel Back Office. Sfrutta la classe `Module` di PrestaShop per la sua funzionalità principale e la classe `Configuration` per l'archiviazione delle impostazioni. Lo scopo principale del modulo è generare oggetti `CartRule` (voucher) e quindi renderizzare contenuto HTML stampabile basato sulle impostazioni del modulo e sui dati dei clienti selezionati. Non introduce tabelle di database personalizzate o strutture `ObjectModel` complesse oltre a quelle che PrestaShop già fornisce per `CartRule` e `Customer`.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller amministrativi personalizzati per il Front-Office o il Back-Office. Tutta la configurazione e la logica sono gestite all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

Questo modulo non definisce alcuna classe personalizzata nella directory `classes/`. Interagisce direttamente con le classi core di PrestaShop, principalmente:

- `Module`: La classe base per il modulo stesso.
- `Configuration`: Per archiviare e recuperare le impostazioni del modulo.
- `Customer`: Per recuperare i dati del cliente per la personalizzazione della lettera.
- `CartRule`: Per creare e gestire i codici voucher generati.

### 4.4 Risorse JavaScript (`views/js/`)

- **`voucherletter/js/jscolor/jscolor.js`**

  - **Ambito:** Back-office.
  - **Descrizione:** Questa è una libreria JavaScript di terze parti per un selettore di colori avanzato. Permette all'utente amministratore di selezionare visivamente i colori per il testo e lo sfondo all'interno del modulo di configurazione.
  - **Funzionalità:** Si lega ai campi di input con classi specifiche (es. `jscolor`) per visualizzare una tavolozza di colori e aggiornare il valore dell'input con il codice colore esadecimale scelto.
- **`voucherletter/js/script.js`**

  - **Ambito:** Back-office (pagina di configurazione del modulo).
  - **Descrizione:** Contiene la logica JavaScript personalizzata specifica per il modulo di configurazione.
  - **Funzionalità:**
    - Probabilmente gestisce le richieste AJAX per la generazione di voucher e lettere (anche se il dossier del modulo implica che `getContent()` gestisce l'intero processo, questo script potrebbe aiutare con l'invio del modulo o gli aggiornamenti dinamici).
    - Potrebbe includere la logica di validazione per i campi del modulo (es. assicurarsi che il valore del voucher sia un numero).
    - Potrebbe gestire la visualizzazione/nascondimento di alcuni elementi del modulo in base ad altre selezioni.
    - Potrebbe attivare la funzionalità di stampa nel browser dopo la generazione del contenuto della lettera.

### 4.5 Fogli di Stile CSS (`views/css/`)

Il dossier del modulo indica che non sono presenti file CSS personalizzati in `views/css/`. Lo stile per la configurazione del Back Office si baserebbe sul CSS del tema amministrativo predefinito di PrestaShop. Qualsiasi stile per l'*output stampato* sarebbe CSS inline generato dal codice PHP o uno stile HTML molto semplice.

### 4.6 Struttura del Template Smarty (`views/templates/`)

Il dossier del modulo indica che non sono presenti file `.tpl` personalizzati in `views/templates/`. Ciò suggerisce che:

- Il modulo di configurazione del Back Office è probabilmente renderizzato direttamente all'interno del metodo `getContent()` utilizzando `HelperForm` di PrestaShop o concatenando stringhe HTML.
- Il contenuto della lettera stampabile viene generato dinamicamente come stringa HTML all'interno del codice PHP e quindi inviato alla funzione di stampa del browser.

### 4.7 Schema del Database e Mappa degli Hook

- **Tabelle del Database**:

  - Il modulo non crea tabelle di database personalizzate.
  - Archivia le sue impostazioni di configurazione nella tabella `ps_configuration` di PrestaShop. Le chiavi di configurazione seguirebbero tipicamente un modello come `VOUCHERLETTER_PREFIX`, `VOUCHERLETTER_VALUE`, ecc.
  - Crea nuove voci nelle tabelle `ps_cart_rule` e tabelle correlate (`ps_cart_rule_lang`, `ps_cart_rule_product_rule_group`, ecc.) durante la generazione dei voucher.
- **Tabella degli Hook Registrati**:
  Il dossier del modulo indica che il modulo non registra alcun hook del front-office (Header, Colonne, Prodotto, Footer). Ciò conferma la sua funzione primaria come strumento del Back Office per la generazione di posta fisica.

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `actionModuleInstall` | Durante l'installazione del modulo | Imposta i valori di configurazione predefiniti in `ps_configuration`. |
| `actionModuleUninstall` | Durante la disinstallazione del modulo | Pulisce i valori di configurazione da `ps_configuration`. |

## 5. Supporto Ufficiale e Aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e qualsiasi ulteriore assistenza con il modulo "Stampante Voucher & Lettere", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per aiutarvi con qualsiasi problema o domanda possiate avere.
