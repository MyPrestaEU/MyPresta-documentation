---
title: My AI Gemini - AI content generation - documentazione e manuale utente
description: Guida alla configurazione, al lavoro quotidiano e alla risoluzione dei problemi per i titolari di negozi che hanno già installato il modulo My AI Gemini nel back office di PrestaShop.
sidebar:
  label: My AI Gemini - AI content generation - documentazione e manuale utente
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Product and Category Descriptions with Gemini su MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/product-and-category-descriptions-with-gemini.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ai-artificial-intelligence/product-and-category-descriptions-with-gemini/)
>
> ---


Gli screenshot di questo manuale provengono da un back office in inglese. Ogni pulsante e ogni nome di campo è scritto esattamente come appare sullo schermo.

## 1. Requisiti

Prima di iniziare, verifichi che il suo negozio e il suo server soddisfino i punti seguenti.

- **PrestaShop:** 1.6, 1.7, 8 e 9 (tutte le versioni dalla 1.6 alla 9.99.99).
- **PHP:** 7.0 o successivo. L'installatore si rifiuta di proseguire con un PHP più vecchio e mostra il messaggio "This module requires PHP 7.0.0 or newer. This server is running PHP …".
- **Estensioni PHP:** cURL (ogni chiamata a Gemini e ogni download di pagina), JSON, DOM (lettura di pagine web per New product e per la ricerca di foto), mbstring e fileinfo (controllo delle immagini scaricate).
- **Connessione in uscita:** il suo server deve poter aprire connessioni sicure (HTTPS) verso il servizio Google Gemini. Se il server blocca le connessioni in uscita, non è possibile generare nulla.
- **Altri moduli:** il modulo non richiede nessun altro modulo.
- **Account Google:** serve una sua chiave API Google Gemini. La crei su https://aistudio.google.com/apikey e la tenga riservata. Google fattura o limita l'utilizzo in base al suo account Google, non tramite questo modulo.
- **Tempo e dimensioni:** ogni campo è una richiesta a Gemini. Testi lunghi e modelli lenti possono richiedere più di un minuto per richiesta. Un'esecuzione di massa grande o un lotto di cron grande dura quanto tutte le sue richieste sommate, quindi cominci con elenchi piccoli.

## 2. Installazione

1. Apra **Modules**, poi **Module Manager**.
2. Faccia clic su **Upload a module** e trascini il file ZIP, oppure lo carichi con il suo metodo abituale.
3. Faccia clic su **Install** accanto al modulo quando compare nell'elenco e confermi.
4. Dopo l'installazione compare una nuova voce chiamata **AI Content Generator** nel menu a sinistra, nella sezione **Modules**. Vi faccia clic: si apre la **Dashboard** del modulo. Le stesse schermate sono raggiungibili anche da **Module Manager**, **Configure**.
5. Prima che si possa generare qualcosa, apra **Settings**, poi **Gemini**, incolli la chiave in **Google Gemini API KEY** e salvi (dettagli nel capitolo 3).

L'installazione crea 16 modelli di prompt già pronti (nomi dei prodotti, descrizioni, meta title, meta description e tag) così può provare subito il modulo. Non svuota la cache del negozio. Se la voce di menu non compare, apra ancora una volta una qualsiasi pagina del back office: il modulo rimette al suo posto la voce di menu a ogni caricamento di una pagina del back office.

**Disinstallazione.** La disinstallazione rimuove la voce di menu **AI Content Generator**, elimina i modelli di prompt e l'intero History (quindi spariscono anche gli elenchi di ripristino sui prodotti) ed elimina le impostazioni del modulo, compresi la chiave API e i segreti del cron. Non tocca i testi, le immagini e i prodotti già scritti o creati con il modulo. Alcuni filtri di schermata che ha usato nelle pagine **Generate** possono restare memorizzati nelle impostazioni del negozio; sono innocui. Una nuova installazione parte da uno stato pulito: tornano i 16 modelli predefiniti, mentre le vecchie impostazioni, i modelli e l'History non vengono ripristinati.

## 3. Configurazione e lavoro quotidiano nel back office

### 3.1 L'intero processo, passo dopo passo

1. **Collegare Gemini.** **Settings**, **Gemini**: incolli la chiave API, mantenga o cambi il modello, salvi.
2. **Provare.** **Settings**, **Playground**: scriva una breve istruzione e prema **Generate**. Se vede una risposta, la connessione funziona. Nel catalogo non viene salvato nulla.
3. **Impostare lo stile del negozio (facoltativo).** **Settings**, **Studio**: scriva la voce del marchio, il pubblico, il tono, le parole da mantenere e le parole vietate.
4. **Preparare le istruzioni.** **Settings**, **Prompt templates**: mantenga i modelli predefiniti o aggiunga i suoi. I modelli abilitati vengono proposti ovunque altrove.
5. **Scegliere come lavorare:**
   - Un prodotto alla volta: apra il prodotto, poi **Modules**, **My AI Gemini**, e prema **Fill** accanto a un campo (3.16).
   - Molti prodotti o categorie: **Generate**, **Products** o **Categories** (3.9 e 3.10).
   - Un prodotto che non esiste ancora: **New product** (3.11).
   - Automaticamente, a piccoli lotti, senza che nessuno faccia clic: **Cron** (3.12).
6. **Controllare il risultato.** **History** elenca ogni richiesta con prompt, risposta, stato e consumo di token. **Dashboard** mostra gli stessi numeri sotto forma di grafici.
7. **Annullare.** Su un prodotto: **Modules**, **My AI Gemini**, **History**: **Restore** rimette il testo precedente.

I testi vengono salvati direttamente nel prodotto o nella categoria non appena Gemini risponde, salvo dove questo manuale indichi diversamente (i pulsanti **Try**, il **Playground**, **Generate data** e i pulsanti **Generate with AI** accanto ai campi, che inseriscono il testo solo nel modulo aperto finché lei non salva).

### 3.2 Aprire il modulo e muoversi al suo interno

Apra **AI Content Generator** nel menu a sinistra. La barra in alto di ogni schermata contiene queste voci: **Dashboard**, **Settings**, **Generate**, **New product**, **Cron**, **History**, **Images** e, all'estrema destra, **Updates**. Tenga il mouse su una voce per vedere una breve spiegazione. Sotto **Settings** compare una seconda riga con **General**, **Gemini**, **Studio**, **Prompt templates** e **Playground**. Sotto **Generate** la seconda riga mostra **Products** e **Categories**.

Il pulsante rotondo **Help** sul bordo di ogni pagina del modulo apre un pannello laterale con una breve spiegazione della pagina in cui si trova. Una riga di quel pannello fa ancora riferimento a un account OpenAI (vedere il capitolo 5); usi la sua chiave Google Gemini.

Può raggiungere il modulo anche da **Module Manager** con il pulsante **Configure**, dal pulsante di scelta rapida nella barra superiore (3.18) e da un link nell'elenco dei prodotti (3.18).

### 3.3 Dashboard

La **Dashboard** è un report. Non scrive mai testi di prodotti o categorie.

![My AI Gemini – Dashboard con intervallo di date, schede e grafici](https://mypresta.eu/docs/images/docs/myaigemini-dashboard.webp)

In alto sceglie il periodo. La riga **Active service** mostra sempre Gemini e il modello salvato nella schermata **Gemini**.

| Campo | All'avvio | Cosa fa |
|---|---|---|
| **Today**, **7 days**, **30 days**, **90 days**, **This month**, **All time** | **30 days** | Pulsanti di periodo rapido. Quello scelto è evidenziato. Cambiano solo i numeri e i grafici di questa pagina. |
| **From** e **To** | Date degli ultimi 30 giorni | Il suo periodo personalizzato. Prema **Apply** per ridisegnare. Se From è successivo a To, il modulo li scambia. |
| **Apply** | – | Ridisegna le schede e i grafici per le date inserite. |
| **Requests** | Conteggiato da History | Ogni chiamata registrata nel periodo, riuscita o fallita. |
| **Success** | Conteggiato da History | Chiamate che non sono terminate con un errore. |
| **Errors** | Conteggiato da History | Chiamate terminate con un errore. |
| **Tokens sent** | Conteggiato da History | Dimensione totale delle sue istruzioni inviate a Gemini. |
| **Tokens received** | Conteggiato da History | Dimensione totale delle risposte. |
| Grafico **Requests and errors** | – | Grafico a linee, un punto al giorno. Per periodi superiori a 120 giorni un punto copre una settimana. |
| Grafico **Tokens sent and received** | – | Stesso periodo, due linee. |
| Grafico **Requests by model** | – | Grafico a barre: quante richieste ha gestito ciascun modello. |

Se i grafici sono vuoti, in quel periodo non è stato generato nulla. La Dashboard esiste anche come piccolo blocco nella dashboard principale di PrestaShop, ma quel blocco non riceve i dati di History, quindi le sue schede e i suoi grafici restano vuoti. Usi la **Dashboard** del modulo.

### 3.4 Settings – General

Apra **Settings**, poi **General**. Questi interruttori decidono cosa vedono i dipendenti nel back office. Il salvataggio non riscrive alcun testo di prodotto.

![Settings – General](https://mypresta.eu/docs/images/docs/myaigemini-settings-general.webp)

| Campo | All'avvio | Cosa fa |
|---|---|---|
| **Live mode** | Disabled | Indica che il modulo funziona sul negozio reale. Lo abiliti sul negozio di produzione. Lo lasci disattivato su una copia di prova per segnalare che la configurazione non è quella di produzione. Gli stessi strumenti funzionano in entrambi gli stati. |
| **Debug mode** | Disabled | Scrive messaggi tecnici aggiuntivi nel log di PrestaShop (**Advanced Parameters**, **Logs**) quando una chiamata a Gemini fallisce. Lo attivi solo mentre indaga su un errore, poi lo disattivi. I clienti non lo vedono mai. |
| **API timeout (seconds)** | 120 | Quanti secondi può durare una chiamata a Gemini prima che il modulo rinunci. 120 va bene per le descrizioni normali. Lo alzi fino a 600 per testi SEO lunghi o modelli lenti. I valori inferiori a 10 diventano 10, quelli superiori a 600 diventano 600, un valore vuoto o non numerico diventa 120. Un timeout breve fallisce subito e registra un errore. |
| **Product Edit History** | Enabled | Mostra la scheda **History** con i pulsanti **Restore** nella pagina del prodotto (**Modules**, **My AI Gemini**). Disattivato nasconde quell'elenco. Le righe passate restano comunque nell'**History** di tutto il negozio. |
| **Admin Top Bar CTA** | Enabled | Inserisce un piccolo pulsante a bacchetta magica nella barra superiore di ogni pagina del back office che apre una finestra di prompt. Disattivato rimuove solo quel pulsante. Il menu del modulo resta. |
| **Product edit page Form** | Enabled | Mostra il pannello del generatore sotto **Modules**, **My AI Gemini** nella pagina del prodotto. Lo abiliti per gli editor del catalogo. Lo disabiliti se devono essere usati solo la generazione di massa e il cron. |
| **AI Image Finder** | Enabled | Mostra la scheda **Photos** nella pagina del prodotto. Disattivato la nasconde. Un'immagine viene importata solo dopo che qualcuno la spunta e conferma. |
| **AI Image Search Prompt** | Un'istruzione integrata in inglese che chiede 5 indirizzi di pagine | L'istruzione inviata quando qualcuno cerca immagini del prodotto. Le parole {product_name} e {product_description} vengono sostituite con il prodotto corrente. Mantenga la richiesta di un elenco di indirizzi di pagine. Un prompt più mirato dà pagine più pertinenti. |
| **Save** | – | Salva tutti i campi precedenti. Messaggio: **Settings Updated**. |

I due campi delle immagini compaiono sia qui sia nella schermata **Images** (3.14). Sono le stesse due impostazioni.

### 3.5 Settings – Gemini

Apra **Settings**, poi **Gemini**. Qui collega l'account Google e stabilisce quanto sia varia la formulazione. Ogni generazione (pulsanti del prodotto, esecuzioni di massa, cron, New product, ricerca di foto, Playground) usa questi valori.

![Settings – Gemini](https://mypresta.eu/docs/images/docs/myaigemini-settings-gemini.webp)

| Campo | All'avvio | Cosa fa |
|---|---|---|
| **Google Gemini API KEY** | Vuoto | Il segreto che consente al suo negozio di chiamare il suo account Gemini. Incolli la chiave da https://aistudio.google.com/apikey. Gli spazi all'inizio e alla fine vengono rimossi. Se lascia la casella intatta, la chiave memorizzata resta. Una chiave vuota o errata fa fallire le chiamate e l'errore viene scritto in History. |
| **Model** | gemini-2.0-flash | Il modello Gemini che scrive il testo. Scelte integrate: gemini-2.0-flash, gemini-2.0-flash-lite, gemini-1.5-flash, gemini-1.5-flash-8b, gemini-1.5-pro, gemini-2.5-flash, gemini-2.5-pro. La generazione successiva usa il modello che salva. Un modello che la sua chiave non può usare restituisce un errore invece del testo. |
| **Add a Gemini model** (casella con **Add model**) | – | Aggiunge un nome di modello che non è nell'elenco integrato. Digiti il nome esatto dal suo account Gemini e prema **Add model**. Il nome compare in **Model** e viene selezionato subito. I nomi aggiunti hanno accanto un link **Remove**. I nomi integrati non possono essere rimossi. |
| **Max Tokens** | 3200 | Limite massimo della lunghezza di una risposta, contato in token, non in parole. Circa 256 bastano per una meta description, 1000 o più per una descrizione HTML completa. Un limite basso taglia la risposta. Un limite alto consente un testo più lungo. Alcuni modelli Gemini 2.5 spendono parte di questo limite per «pensare», quindi lo tenga generoso per loro. |
| **Temperature** | 0.7 | Quanta libertà ha il modello nello scegliere le parole. Resti tra 0 e 1. Circa 0.2 va bene per specifiche e testi meta, circa 0.7 per le descrizioni. Un valore basso ripete una struttura simile. Un valore alto dà una formulazione più varia e un rischio maggiore di allontanarsi dall'incarico. |
| **Top P** | 1 | Un secondo modo per restringere la scelta della parola successiva. In questa versione il valore viene salvato ma non inviato a Gemini, quindi modificarlo non cambia le risposte. |
| **Frequency Penalty Value** | 0 | Pensato per scoraggiare le frasi ripetute. Salvato ma non inviato a Gemini in questa versione, quindi senza effetto sulle risposte. |
| **Presence Penalty Value** | 0 | Pensato per spingere il testo verso nuovi punti. Salvato ma non inviato a Gemini in questa versione, quindi senza effetto sulle risposte. |
| **Save** | – | Salva il modulo. Messaggio: **OpenAi Settings Updated** (il modulo usa qui ancora la vecchia dicitura). |

Messaggi che può vedere in questa schermata:

| Messaggio | Causa | Cosa fare |
|---|---|---|
| **Google Gemini API KEY field is invalid!** | La casella della chiave ha meno di 10 caratteri e non c'è ancora una chiave salvata. | Incolli la chiave completa e prema di nuovo **Save**. |
| **OpenAi Model field is invalid!** | Il nome del modello ha meno di 3 caratteri. | Scelga un nome dall'elenco **Model**. |
| **Google Gemini API Key has been automatically cleaned (whitespace removed).** | La chiave salvata aveva spazi intorno. | Niente: il modulo l'ha corretta. |
| **Model added.** | Il nuovo nome è stato salvato e selezionato. | Prema **Save** se ha modificato anche altri campi. |
| **That model is already built in.** | Il nome digitato è già nell'elenco. | Il modulo lo seleziona per lei. |
| **Model removed.** | Un nome aggiunto è stato eliminato. | Se era il modello attivo, scelga di nuovo un modello Gemini (vedere il capitolo 5). |
| **Built-in models cannot be removed.** | Ha provato a rimuovere un nome integrato. | Niente da fare. |
| **Enter a model id such as gpt-4.1.** | La casella del nome del modello era vuota o conteneva caratteri non validi. | Digiti un nome Gemini, per esempio gemini-2.5-flash. L'esempio in questo messaggio è un residuo del passato. |

### 3.6 Settings – Studio

Apra **Settings**, poi **Studio**. Studio aggiunge regole della casa sopra ogni prompt: pulsanti del prodotto, esecuzioni di massa, cron e Playground. I campi vuoti vengono saltati. Il modulo dice inoltre sempre a Gemini di scrivere nella lingua dell'elemento generato.

![Settings – Studio](https://mypresta.eu/docs/images/docs/myaigemini-settings-studio.webp)

| Campo | All'avvio | Cosa fa |
|---|---|---|
| **Brand voice** | Vuoto | Dice al modello chi parla, in modo che il testo suoni come il suo negozio. Scriva un breve incarico, per esempio: officina specializzata, frasi brevi, niente toni enfatici. Modificarlo non riscrive i testi già salvati. |
| **Audience** | Vuoto | Indica il lettore, per esempio installatori professionisti o acquirenti alla prima esperienza. Le nuove risposte usano un vocabolario rivolto a quel lettore. |
| **Tone** | Vuoto | Una o due parole per l'atmosfera: formale, cordiale, tecnico. Non cambia il modello né la temperatura. |
| **Glossary** | Vuoto | Nomi di marchi, materiali e grafie che il modello deve copiare esattamente. Un termine per riga. I termini non elencati possono comunque essere riformulati. |
| **Forbidden words** | Vuoto | Parole ed espressioni che non devono comparire in una risposta salvata. Una per riga. L'elenco viene inviato al modello anche come parole da evitare. Il rifiuto di una risposta corrispondente avviene solo quando **Quality gate** è abilitato. |
| **Monthly generation budget** | 0 | Numero massimo di generazioni riuscite nel mese di calendario in corso, contate da History. 0 significa nessun limite. Quando il tetto viene raggiunto, le nuove richieste si fermano con un messaggio di budget fino al mese successivo. Le chiamate fallite non vengono contate. |
| **Quality gate** | Enabled | Controlla ogni risposta rispetto a **Forbidden words** prima che venga salvato qualcosa. Abilitato rifiuta una risposta corrispondente: il prodotto resta invariato e History registra un errore. Disabilitato salva la risposta anche se contiene una parola dell'elenco. Con un elenco Forbidden words vuoto il controllo non ha nulla da verificare. |
| **Save studio** | – | Salva il modulo. Messaggio: **Studio settings saved.** |

### 3.7 Settings – Prompt templates

Apra **Settings**, poi **Prompt templates**. Un modello è un'istruzione salvata. Gli editor lo scelgono dal titolo invece di digitare ogni volta lo stesso incarico.

![Settings – Prompt templates](https://mypresta.eu/docs/images/docs/myaigemini-settings-templates.webp)

L'elenco mostra queste colonne: **ID**, **Title**, **Prompt**, **Status** (faccia clic sul segno di spunta o sulla croce per abilitare o disabilitare il modello), **Timestamp**. Ogni riga ha **Edit** e **Delete**. Spunti più righe e usi l'azione di gruppo **Delete** (le viene chiesto "Are you sure you want to delete the selected prompts?"). Il pulsante verde con il segno più sopra l'elenco crea un nuovo modello.

Il modulo del modello:

| Campo | All'avvio | Cosa fa |
|---|---|---|
| **Status** | Interruttore Enabled / Disabled | Mostra o nasconde il modello negli elenchi usati nella pagina del prodotto, nella finestra di prompt della barra superiore, nella generazione di massa e nel cron. Abiliti i modelli che il suo personale deve usare. Disabiliti una bozza invece di eliminarla. |
| **Prompt title** | Vuoto (obbligatorio) | Il nome che gli editor vedono nell'elenco. Non viene inviato a Gemini. Usi un'etichetta breve, per esempio HTML description with features. |
| **Prompt content** | Vuoto (obbligatorio) | L'istruzione inviata a Gemini. La scriva come se desse un incarico a un copywriter: lunghezza, HTML, lingua. Può usare segnaposto (3.19). Le virgolette doppie vengono cambiate in virgolette singole al salvataggio. |
| **Save Prompt** | – | Salva il modello. |
| **Go Back to Module Settings** | – | Torna all'elenco senza salvare. |

Messaggi: **Prompt template successfully added!**, **Prompt template successfully updated!**, **Prompt template removed.**, **Unable to delete prompt template with id:** seguito da un numero, **Failed to edit prompt template! Please fill the form with the right informations!**.

I 16 modelli predefiniti sono: Product name 1–2, Product description 1–7 (il settimo incorpora i link alle immagini del prodotto), Product meta title 1–3, Product meta description 1–3 e Product tags. Due dei modelli di meta description citano uno smartwatch; li modifichi prima dell'uso se vende altro. I testi dei modelli sono salvati nella lingua che il negozio usava al momento dell'installazione.

### 3.8 Settings – Playground

Apra **Settings**, poi **Playground**. È un blocco per gli appunti: invia un'istruzione libera al modello attivo e mostra la risposta nella pagina.

![Settings – Playground](https://mypresta.eu/docs/images/docs/myaigemini-settings-playground.webp)

1. Digiti l'istruzione nella casella grande ("Ask the model anything about your catalog").
2. Prema **Generate**.
3. Legga la risposta sotto il pulsante, con il numero di token utilizzati.

Può citare il nome del negozio, l'indirizzo del negozio, il nome di un prodotto, un riferimento o caratteristiche se desidera che la risposta si basi sui dati del catalogo. Le regole di Studio vengono applicate. Nessun prodotto, categoria o campo meta viene modificato e la chiamata viene registrata in History. Se la casella è vuota vede "Write a prompt first." Usi il Playground per provare la chiave e rifinire un prompt prima di trasformarlo in modello.

### 3.9 Generate – Products

Apra **Generate**, poi **Products**. La generazione di massa ha due passaggi. Durante il passaggio 1 non viene inviato nulla a Gemini.

![Generate – Products](https://mypresta.eu/docs/images/docs/myaigemini-generate-products.webp)

**Passaggio 1 – filtrare i prodotti.** Tutti i filtri sono facoltativi e non vengono salvati come impostazioni del negozio.

| Campo | All'avvio | Cosa fa |
|---|---|---|
| **Product Categories** | Niente spuntato | Mantiene i prodotti che si trovano in una qualsiasi delle categorie spuntate o la hanno come categoria principale. Un albero vuoto non filtra per categoria. |
| **Brand** | **Select brand** | Mantiene i prodotti di un produttore. La prima opzione significa ogni marchio. |
| **Product status** | **Active** | **Active** mantiene i prodotti in vendita, **Disabled** i prodotti disattivati, **Both** tutti. |
| **Product stock** | **All products** | **Only in stock products** scarta i prodotti senza quantità disponibile. |
| **Update only** | **Update all** | Usa History. La prima opzione mantiene i prodotti che questo modulo non ha mai scritto. La seconda mantiene quelli che ha già scritto. Le etichette dicono ancora "OpenAi content" (vedere il capitolo 5). |
| **Product IDs** | Vuoto | Digiti gli id separati da virgole, per esempio 12,45,103. Possono comparire solo quei prodotti. |
| **Product Reference** | Vuoto | Digiti uno o più riferimenti separati da virgole. |
| **Product Add Date From** / **Product Add Date To** | Vuoto | Mantengono i prodotti creati dopo la prima data e prima della seconda. |
| **Minimum product ID** / **Maximum product ID** | Vuoto | Mantengono i prodotti all'interno di quell'intervallo di id. |
| **Product Limit** | Vuoto | Numero massimo di prodotti caricati nell'elenco. La prima volta usi un numero piccolo come 20. |
| **Go to next step** | – | Costruisce l'elenco. |
| **Module settings** | – | Pulsante accanto a **Go to next step**. Apre la pagina delle impostazioni di un altro modulo (vedere il capitolo 5); usi invece **Settings** nella barra del modulo. |

**Passaggio 2 – scrivere.** La pagina mostra ora il pannello **Mass product generation** con una tabella dei prodotti trovati (colonne **ID**, **Reference**, **Result**).

| Campo | All'avvio | Cosa fa |
|---|---|---|
| **Template** | **Choose a template** | Copia il testo di un modello abilitato nella casella sottostante. Il titolo in sé non viene inviato. |
| Casella grande del prompt | Vuoto | L'istruzione inviata per ogni prodotto. I segnaposto vengono compilati per ogni prodotto (3.19). Se la lascia vuota, viene usata un'istruzione standard per ogni campo. |
| **What to generate** | **Descriptions** | **Descriptions** scrive la descrizione lunga e quella breve. **Meta title and meta description** scrive entrambi i campi meta. **Descriptions and meta together** scrive tutti e quattro. Ogni campo è una richiesta a sé. Gli altri campi (compresi il nome del prodotto e i tag) non vengono mai modificati qui. |
| **Existing text** | **Replace** | **Replace** sovrascrive il campo. **Skip if filled** lascia in pace un campo compilato e non invia nulla a Gemini per esso. **Add above** e **Add below** mantengono il vecchio testo e aggiungono il nuovo prima o dopo. |
| **Languages** | È spuntata la lingua che usa nel back office | Spunti ogni lingua desiderata. Ogni lingua spuntata viene generata separatamente. Almeno una deve essere spuntata ("Select at least one language."). |
| **Run on the list below** | – | Avvia l'esecuzione. |

Durante l'esecuzione la riga sopra il pulsante mostra l'avanzamento, per esempio "3 / 40 – description". Ogni riga della tabella mostra un risultato come "description: success Content successfully generated and updated to product." oppure "description: skipped Product skipped." o un testo di errore. L'esecuzione prende i prodotti uno alla volta e salva subito ogni risposta, quindi un errore su un prodotto non annulla quelli già salvati. Non chiuda la pagina finché non vede "Finished … products."

### 3.10 Generate – Categories

Apra **Generate**, poi **Categories**.

![Generate – Categories](https://mypresta.eu/docs/images/docs/myaigemini-generate-categories.webp)

**Passaggio 1 – filtrare le categorie.**

| Campo | All'avvio | Cosa fa |
|---|---|---|
| **Categories** | Niente spuntato | Spunti le categorie da includere. Un albero vuoto include ogni categoria corrispondente allo stato. |
| **Category status** | **Active** | **Active**, **Disabled** o **Both**. |
| **Go to next step** | – | Costruisce l'elenco. Non viene ancora generato nulla. |
| **Module settings** | – | Apre la pagina delle impostazioni di un altro modulo (vedere il capitolo 5). |

**Passaggio 2 – scrivere.** Il pannello **Mass category generation** elenca le categorie (colonne **ID**, **Result**).

| Campo | All'avvio | Cosa fa |
|---|---|---|
| Casella grande del prompt | Vuoto | L'istruzione inviata per ogni categoria. Può usare {category_name}, {category_description}, {category_parent_name} e i segnaposto del negozio (3.19). Scriva sempre un prompt qui: per le categorie non esiste un'istruzione standard. |
| Elenco dei campi | **Description** | **Description**, **Name**, **Meta title**, **Meta description** o **Additional description**. Viene salvato solo quel campo. |
| Elenco del testo esistente | **Replace** | **Replace** sovrascrive. **Skip if filled** lascia in pace un campo compilato. |
| Elenco delle lingue | La sua lingua del back office | Una lingua per esecuzione. Esegua di nuovo per un'altra lingua. |
| **Run on the categories below** | – | Avvia l'esecuzione. Ogni categoria viene salvata non appena arriva la sua risposta. |

Sotto la tabella c'è un secondo modulo intitolato **Generate category content** con un pulsante **Generate content**. Non genera nulla: la riporta soltanto al filtro delle categorie. Usi sempre **Run on the categories below**.

### 3.11 New product

Apra **New product**. Questa schermata trasforma un breve incarico nella bozza di un prodotto che non esiste ancora.

![New product](https://mypresta.eu/docs/images/docs/myaigemini-new-product.webp)

| Campo | All'avvio | Cosa fa |
|---|---|---|
| **What is the product?** | Vuoto | L'incarico. Scriva alcune frasi con materiali, pubblico e nomi che devono restare. Un incarico più ricco dà una bozza più fedele. Un incarico vuoto viene rifiutato. |
| **Optional source URL** | Vuoto | L'indirizzo completo di una pagina pubblica sul prodotto. Il testo della pagina (titolo, descrizione, prezzo) viene aggiunto al suo incarico. Una casella vuota o una pagina che il negozio non riesce a leggere viene ignorata. |
| **Language** | Lingua predefinita del negozio | La lingua in cui vengono salvati nome, descrizioni, meta e tag. Le altre lingue non vengono compilate. Scelga la lingua predefinita del negozio, perché PrestaShop si aspetta un nome in quella lingua. |
| **Default category ID** | 2 | Il numero della categoria in Catalog, Categories. 2 di solito è Home. Il nuovo prodotto viene collocato in quella categoria, che diventa la categoria predefinita. |
| **Generate data** | – | Chiede una bozza a Gemini e la stampa sotto come testo strutturato (nome, descrizioni, meta, tag, riferimento, prezzo, caratteristiche). Nessun prodotto viene salvato. |
| **Create product** | – | Salva la bozza come nuovo prodotto attivo. Imposta nome, descrizioni, meta, tag, caratteristiche, riferimento e prezzo dalla bozza, visibilità ovunque e una quantità in magazzino di 100. Non vengono allegate immagini; le aggiunga dopo (3.16). Riga del risultato: "Product #" seguito dal numero del nuovo prodotto. |

Se non è salvata alcuna chiave API vede "Add an API key in the module settings first." Premere **Create product** prima di **Generate data** mostra "Generate the product first." Dopo la creazione controlli prezzo, imposta e immagini: il modulo imposta il primo gruppo di regole fiscali e il prezzo suggerito da Gemini.

### 3.12 Cron

Apra **Cron**. Il cron è pensato per il server, non per una persona: il suo server richiama un indirizzo web segreto con una pianificazione e il negozio compila ogni volta un piccolo lotto di prodotti o categorie. Non succede nulla finché il server non richiede l'indirizzo.

![Cron](https://mypresta.eu/docs/images/docs/myaigemini-cron.webp)

La schermata ha due moduli: uno per i prodotti e uno per le categorie. Ognuno ha il proprio pulsante **Save** e dopo il salvataggio non viene mostrato alcun messaggio di conferma.

**Modulo del cron dei prodotti**

| Campo | All'avvio | Cosa fa |
|---|---|---|
| **Enable Cron Feature** | **No** | Interruttore dell'intero cron (prodotti e categorie). Finché è su **No**, ogni chiamata viene rifiutata con "Cron Job feature is disabled. You can enable it from the module settings." Lo attivi solo dopo aver salvato gli altri campi. |
| **Cron Job Secret Token** | Un lungo valore casuale | La password che deve essere presente nell'indirizzo. Senza di essa il negozio rifiuta la chiamata. Sostituirla invalida il vecchio indirizzo. Il pulsante **Generate Token** accanto al campo potrebbe non fare nulla in questa versione; se non lo fa, digiti lei stessa un valore lungo. |
| **Update Field** | **description** | Quale singolo campo del prodotto il cron riscrive: **name**, **description**, **description_short**, **meta_title**, **meta_description** o **tags**. Per compilare più campi, crei più comandi cron. |
| **Selected Products** | **pendingGemini** | Quali prodotti sono ancora in attesa. **pendingGemini**: prodotti che questo modulo non ha mai scritto con successo (qualsiasi campo). **pendingField**: prodotti non ancora generati per il campo scelto, così un catalogo può essere elaborato da più cron job. **emptyField**: solo i prodotti il cui campo scelto è vuoto nella lingua scelta. |
| **Product Categories** | Niente spuntato | Limita l'esecuzione alle categorie spuntate (vedere il capitolo 5 per un'avvertenza). |
| **Product ID list** | Vuoto | Id di prodotto espliciti separati da virgole. I caratteri diversi dalle cifre vengono eliminati al salvataggio. |
| **Language** | Lingua predefinita del negozio | La versione linguistica che viene scritta. |
| **Product to update** | 5 products | Dimensione del lotto per chiamata: 2, 3, 5, 8, 10, 15, 20, 50, 100, 200, 300, 500 o 1000. Cominci con 5 o 10 in modo che un modello lento non raggiunga il limite di tempo del server. I prodotti vengono presi in ordine di ID. |
| **Prompt Template** | Primo modello dell'elenco | L'istruzione salvata usata per ogni prodotto. I segnaposto vengono compilati per prodotto (3.19). |
| **Enable Debug** | **No** | **Yes** fa stampare all'indirizzo il piano (query, prodotti selezionati, prompt finali) e non salva nulla. Lo disattivi prima che lo scheduler del server usi l'indirizzo. |
| **CRON JOB interval** | **Every Hour** | Un suggerimento mostrato per la sua pianificazione. Il modulo non esegue alcuno scheduler. Imposti la tempistica reale sul suo server. |
| **Product Cron Job command** | – | Mostra il prefisso dell'indirizzo. In questa versione la riga di comando sullo schermo è incompleta (vedere sotto). |
| **Save** | – | Salva le impostazioni del cron dei prodotti. |

Il **modulo del cron delle categorie** ha il proprio **Cron Job Secret Token**, **Update Field** (**name**, **description**, **meta_title**, **meta_description**), **Selected categories** (le stesse tre modalità), **Language**, **Categories to update** (2–1000), **Prompt Template**, **Enable Debug**, **CRON JOB interval** e **Save**. Salta sempre la categoria radice del negozio.

**L'indirizzo da dare al server.** Sopra i moduli la schermata stampa un indirizzo per i prodotti e uno per le categorie, ciascuno terminante dopo il segreto. Al server va anche detto quale lavoro eseguire. Aggiunga questo alla fine dell'indirizzo mostrato sullo schermo:

| Lavoro | Indirizzo completo | Note |
|---|---|---|
| Prodotti | `https://your-shop.example/module/myaigemini/cron?secret=PRODUCT_SECRET&action=generateProductContent` | Usi il segreto del modulo dei prodotti. |
| Categorie | `https://your-shop.example/module/myaigemini/cron?secret=CATEGORY_SECRET&action=generateCategoryContent` | La riga delle categorie sullo schermo termina con `&entity=category`; sostituisca quella parte finale con `&action=generateCategoryContent`. |

Aggiunte facoltative che può accodare per sostituire il modulo salvato per un singolo comando: per i prodotti `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug=1`, `categories` (id separati da virgole), `productIds`; per le categorie `updatedField`, `categoryTarget`, `categoriesToUpdate`, `languageId`, `promptTemplateId`, `debug=1`. I valori non accodati provengono dal modulo salvato.

**Scheduler.** Nel pannello del suo hosting crei un'attività pianificata che apra l'indirizzo completo, per esempio con `curl -s "ADDRESS"` ogni ora. Provi prima in un browser con **Enable Debug** su **Yes**: vedrà quali prodotti verrebbero elaborati e i prompt finali. Poi lo imposti su **No** e apra l'indirizzo ancora una volta. Ogni chiamata reale aggiorna un lotto e si ferma.

Risposte che può vedere quando l'indirizzo viene aperto:

| Risposta | Causa | Cosa fare |
|---|---|---|
| **N products have been updated.** / **N categories have been updated.** | Il lotto ha funzionato. | Niente. |
| **N pending products.** | Il debug è attivo, non è stato salvato nulla. | Disattivi il debug quando è soddisfatta. |
| **No products to update.** / **No categories to update.** | Non c'è più nulla che corrisponda a **Selected Products** e agli altri filtri. | Il lavoro è finito, oppure cambi la regola. |
| **Cron Job feature is disabled. You can enable it from the module settings.** | **Enable Cron Feature** è su **No**. | Lo imposti su **Yes** e prema **Save**. |
| **The token does not exist or it's wrong!** | Il segreto manca o non corrisponde. | Copi di nuovo l'indirizzo dallo schermo. |
| **Invalid action!** | L'indirizzo non ha la parte `action` o ne ha una errata. | Aggiunga la parte `action` dalla tabella precedente. |
| **updatedField parameter is wrong!** | Il campo non è consentito per quel lavoro. | Scelga un campo del modulo. |
| **All must include all mandatory parameters!** | Un valore salvato (per esempio il modello) è vuoto. | Scelga un **Prompt Template** e salvi. |
| **productTarget parameter is wrong! Allowed values: …** | Il nome della modalità nell'indirizzo è errato. | Usi una delle tre modalità. |
| **Error!** seguito da un messaggio | Gemini ha rifiutato o ha fallito. | Legga il messaggio, poi controlli History. |
| **Error! The model returned an empty response.** | Gemini non ha restituito nulla, per esempio perché il limite Max Tokens era troppo basso. | Alzi **Max Tokens** nella schermata **Gemini**. |
| **Monthly generation budget reached.** | Il budget di Studio è esaurito. | Alzi il budget o attenda il mese prossimo. |
| **Reply rejected by the studio quality gate.** | La risposta conteneva una parola vietata. | Modifichi l'elenco o il modello. |
| **Error! Could not save product …** | PrestaShop ha rifiutato il nuovo testo (per esempio troppo lungo). | Controlli il campo e il prompt. |

Una chiamata cron si ferma al primo errore e riferisce quanti elementi erano già stati aggiornati prima di esso.

### 3.13 History

Apra **History**. È il registro di ciò che è stato richiesto e di ciò che è tornato. Aprire o filtrare la pagina non elimina nulla e non modifica i prodotti.

![History](https://mypresta.eu/docs/images/docs/myaigemini-history.webp)

| Campo | All'avvio | Cosa fa |
|---|---|---|
| **Today**, **7 days**, **30 days**, **This month**, **All time** | **This month** | Preimpostazioni di data. |
| **From** / **To** | Il mese corrente | Il suo periodo personalizzato. |
| **Model** | **Any** | Solo le richieste fatte con quel modello. |
| **Type** | **Any** | Solo un tipo di lavoro, per esempio una descrizione di prodotto o un meta title di categoria. |
| **Status** | **Any** | **Success** o **Error**. |
| **Language** | **Any** | Solo le richieste per quella lingua. |
| **Employee** | **Any** | Solo le richieste avviate da quell'utente del back office. |
| **Product / category ID** | Vuoto | Un numero di prodotto o di categoria. |
| **Prompt or reply contains** | Vuoto | Una parola che deve essere nel prompt, nella risposta o nel testo dell'errore. |
| **Filter** | – | Applica i filtri. |

Schede: **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time**. Un trattino in una colonna dei token significa che Gemini non ha restituito un conteggio per quella chiamata. Sotto, cinque tabelle raggruppano le richieste filtrate: **By day**, **By model**, **By type**, **By language**, **By employee**, con una piccola barra che mostra la quota di token. Un piccolo numero in corsivo accanto a un conteggio di chiamate è il numero di errori.

L'elenco in basso ha le colonne **ID**, **Status** (**Success** verde o **Error** rosso), **Prompt** (primi 180 caratteri), **Reply / Error**, **Provider** (servizio, modello e durata), **Sent**, **Received**, **Total**, **Entity ID**, **Type**, **Timestamp** e un pulsante **View** che apre il prompt completo e la risposta con **Back to the list**. L'elenco mostra 50 righe per pagina.

Il pulsante della barra degli strumenti **Clear list** elimina tutte le righe di History in una volta, senza chiedere. Lo faccia solo di proposito: i pulsanti di ripristino sui prodotti, il contatore del budget mensile e le modalità cron **pendingGemini** e **pendingField** si basano tutti su History, quindi dopo la pulizia il cron tratta ogni prodotto come non ancora scritto.

### 3.14 Images

Apra **Images**. Questa schermata attiva o disattiva soltanto la ricerca di foto dei prodotti e memorizza la sua istruzione. Non scarica alcuna immagine.

![Images](https://mypresta.eu/docs/images/docs/myaigemini-images.webp)

| Campo | All'avvio | Cosa fa |
|---|---|---|
| **AI Image Finder** | Enabled | Mostra la scheda **Photos** nella pagina del prodotto. Disattivato la nasconde. |
| **AI Image Search Prompt** | Istruzione integrata in inglese | L'istruzione che chiede a Gemini gli indirizzi di pagine dove è probabile che ci siano foto di questo prodotto. {product_name} e {product_description} vengono sostituiti per il prodotto corrente. Mantenga la richiesta di un semplice elenco di indirizzi. |
| **Save** | – | Salva entrambi i campi. Messaggio: **Settings saved.** |

La ricerca trova pagine web che mostrano già il suo prodotto; non crea immagini. Verifichi di avere il diritto di usare ogni immagine che importa.

### 3.15 Updates

Apra **Updates** (all'estrema destra della barra del modulo). La pagina controlla su MyPresta.eu se esiste un file del modulo più recente. Non modifica il suo catalogo e non installa nulla.

![Updates](https://mypresta.eu/docs/images/docs/myaigemini-updates.webp)

| Campo | All'avvio | Cosa fa |
|---|---|---|
| **Manual Check** (**Check Now**) | – | Chiede una volta, subito. Vede **Module is up to date!** o **New version available!**. |
| **Automatic Notifications** | Interruttore Enabled o Disabled | Enabled: circa ogni tre giorni il back office controlla e mostra un banner di avviso con un link quando esiste una versione più recente. Questa impostazione è condivisa con altri moduli MyPresta dello stesso negozio. |
| **Product Page** | – | Un link alla pagina del modulo su MyPresta.eu, dove può leggere cosa è cambiato e scaricare il file. |
| **Save** | – | Salva l'impostazione delle notifiche. Messaggio: **Update settings saved.** |

### 3.16 Lavorare nella pagina di modifica del prodotto

Apra **Catalog**, **Products**, modifichi un prodotto e apra **Modules**, poi **My AI Gemini**. Il prodotto deve essere già stato salvato una volta. Il pannello compare quando **Product edit page Form** o **Product Edit History** (3.4) è abilitato.

![Pagina di modifica del prodotto – pannello My AI Gemini](https://mypresta.eu/docs/images/docs/myaigemini-product-edit.webp)

Il pannello ha fino a quattro schede: **Generate**, **Simulate**, **Photos** e **History**.

**Scheda Generate**

| Campo | All'avvio | Cosa fa |
|---|---|---|
| Pulsanti **Language** | La prima lingua | Scelga quale versione linguistica viene scritta. **Every language** scrive tutte le lingue attive, una dopo l'altra. |
| **If the field already has text** | **Replace** | **Replace**, **Add above**, **Add below** o **Skip if filled**. Skip non invia nulla a Gemini per un campo compilato. |
| Schede dei campi | – | **Description**, **Short description**, **Name**, **Meta title**, **Meta description**, **Tags**. Prema **Fill** sulla scheda per scrivere quel campo e salvarlo subito sul prodotto. |
| **SEO pack** – **Fill all** | – | Scrive il nome, entrambe le descrizioni ed entrambi i campi meta in un'unica richiesta e li salva. |
| **Use your own instruction or a saved prompt** | Chiuso | Lo apra per filtrare i modelli salvati per titolo o testo, scegliere un riquadro (**Standard brief** o un modello abilitato) e modificare la casella **Instruction**. Se la casella è vuota, **Fill** usa un'istruzione standard per il campo. |

La risposta viene stampata sotto il pannello. Il testo viene salvato subito sul prodotto, ma i campi del modulo prodotto aperto non si aggiornano da soli: ricarichi la pagina del prodotto prima di modificare e di premere salva nel modulo, altrimenti i vecchi valori nel modulo possono sovrascrivere il nuovo testo.

**Scheda Simulate.** Stessa scelta della lingua e stesse schede dei campi, ma i pulsanti si chiamano **Try**. La risposta resta in questa pagina e il prodotto non viene modificato. La usi per controllare prima la formulazione.

![Pagina di modifica del prodotto – scheda Photos](https://mypresta.eu/docs/images/docs/myaigemini-product-photos.webp)

**Scheda Photos.** Prema **Find pages**. Il modulo chiede a Gemini fino a 5 pagine che probabilmente mostrano questo prodotto, ne legge fino a 24 immagini e le mostra come piccole miniature. Spunti quelle che desidera e prema **Add selected to this product**. La prima immagine spuntata diventa la copertina se ne aggiunge più di una. Non viene salvato nulla prima di premere il pulsante. La riga sotto i pulsanti indica l'avanzamento: "Looking for photos…", "Reading photos…", "Tick the photos you want, then add them to this product." Dopo l'aggiunta, ricarichi la pagina del prodotto per vederle. Se l'interruttore è disattivato, vede una nota che le dice di abilitare **AI Image Finder** in **Settings**, **General**.

**Scheda History.** Una tabella con **When**, **Type**, **Status** e un pulsante **Restore** per ogni scrittura riuscita che ha conservato un valore precedente. Prema **Restore**, confermi "Restore the previous value?" e il testo precedente torna. Le righe fallite non hanno il pulsante. Un SEO pack ripristinato riporta il nome, entrambe le descrizioni ed entrambi i campi meta. Senza righe vede "No generations for this product yet."

**Pulsanti Generate with AI accanto ai campi.** Nella pagina del prodotto il modulo aggiunge anche un pulsante **Generate with AI** accanto ai campi descrizione, descrizione breve, meta title e meta description. Se il negozio ha più di una lingua, chiede "Generate this field for the current language, or for every active language?" con **Current language**, **All languages** e **Cancel**. Il testo va solo nel modulo aperto: "Text is in the field. Save the product to keep it." Gli altri campi non vengono modificati. Per un prodotto che non è mai stato salvato vede "Save the product once before generating."

### 3.17 Lavorare nella pagina di modifica della categoria

Modifichi una categoria in **Catalog**, **Categories**. Accanto ai campi descrizione, descrizione aggiuntiva, meta title e meta description il modulo aggiunge il pulsante **Generate with AI**. Funziona esattamente come sui prodotti: scelga la lingua corrente o tutte le lingue, il testo viene inserito nel modulo e lei salva la categoria per conservarlo ("Text is in the field. Save the category to keep it."). Una categoria mai salvata mostra "Save the category once before generating." La stessa finestra di prompt della barra superiore (3.18) funziona anche nelle pagine di categoria, delle pagine CMS e dei marchi e le registra in History.

### 3.18 Scorciatoie: barra superiore, elenco dei prodotti e Help

- **Pulsante della barra superiore.** Con **Admin Top Bar CTA** abilitato, un'icona a bacchetta magica si trova nella barra superiore. Apre la finestra **My AI Gemini** con un elenco **Template**, un'area di testo e **Generate**. La risposta viene mostrata sotto il pulsante, con il numero di token. Non modifica alcun campo. Usi la **×** per chiudere.
- **Elenco dei prodotti.** Nell'elenco dei prodotti in **Catalog**, **Products**, il modulo aggiunge un link **My AI Gemini** accanto alle azioni di gruppo o nella barra degli strumenti. Apre **Generate**, **Products**.
- **Help.** Il pulsante **Help** di ogni pagina del modulo apre la spiegazione della pagina.

### 3.19 Segnaposto utilizzabili nei prompt

Nei modelli, nella casella **Instruction**, nelle caselle dei prompt di massa e nel Playground può scrivere segnaposto tra parentesi graffe. Il modulo li sostituisce con dati reali per ogni elemento prima di inviare l'istruzione.

| Segnaposto | Funziona per | In cosa si trasforma |
|---|---|---|
| {product_name}, {product_description}, {product_description_short}, {product_tags}, {product_reference}, {product_ean13}, {product_weight} | Prodotti | I dati propri del prodotto nella lingua scelta. |
| {product_default_category}, {product_category_description}, {product_categories}, {product_brand} | Prodotti | Nome e descrizione della categoria principale, nomi di tutte le categorie (separati da virgole), nome del marchio. |
| {product_attributes}, {product_features}, {product_feature_values} | Prodotti | Attributi delle combinazioni, nomi delle caratteristiche e coppie nome caratteristica:valore. |
| {product_images} | Prodotti | I link alle immagini del prodotto, separati da virgole. |
| {category_name}, {category_description}, {category_parent_name} | Categorie | I dati propri della categoria e il nome del genitore. |
| {cms_title}, {brand_name}, {brand_description}, {brand_short_description} | Pagine CMS, marchi (finestra della barra superiore) | Il titolo della pagina o i dati del marchio. |
| {shop_name}, {shop_url}, {shop_language}, {shop_country}, {shop_currency} | Tutto | Nome del negozio, dominio, nome della lingua, paese predefinito e codice della valuta predefinita. |

Un segnaposto privo di dati diventa testo vuoto. I segnaposto delle categorie non vengono sostituiti nei prompt dei prodotti e viceversa.

## 4. Front del negozio

My AI Gemini non ha un'interfaccia per i clienti. Non aggiunge nulla alle pagine dei prodotti, alle pagine delle categorie, al carrello, al footer o all'account cliente e nel tema non c'è nulla da attivare o disattivare. Il front del negozio non riceve alcun template del modulo, quindi non viene mostrato alcuno screenshot.

Il modulo possiede due indirizzi web che non sono pagine per i clienti:

| Indirizzo | Chi lo usa | Cosa sapere |
|---|---|---|
| Indirizzo del cron (`…/module/myaigemini/cron?secret=…&action=…`) | Lo scheduler del suo server | Descritto in 3.12. Aperto senza il segreto corretto risponde soltanto "The token does not exist or it's wrong!". Lo tenga riservato: chi lo conosce può avviare un lotto. |
| Indirizzo interno usato dalle schermate del modulo | I pulsanti del modulo stesso nel back office | Non lo apra né lo condivida. Rifiuta le richieste prive del segreto proprio del modulo ("Error! Invalid token!"). |

## 5. Problemi

**Non viene generato nulla e vedo il messaggio "The Gemini API key is not set. Add it in the module settings."**
La casella della chiave in **Settings**, **Gemini** è vuota. Incolli la chiave da https://aistudio.google.com/apikey e prema **Save**.

**Un errore di Google compare in un risultato, in History o in una risposta del cron (per esempio un messaggio che inizia con "Google Gemini API Error").**
Google ha rifiutato la chiamata: chiave errata o disattivata, un modello che la sua chiave potrebbe non poter usare, limiti gratuiti esauriti o una regione bloccata. Apra **History**, prema **View** sulla riga rossa per leggere il testo completo. Corregga la chiave o scelga un altro modello in **Settings**, **Gemini**, poi riprovi.

**"Gemini request timed out after … seconds. The model may be overloaded, or the timeout is too low for this prompt."**
Il modello ha avuto bisogno di più tempo di **API timeout (seconds)**. Alzi il timeout in **Settings**, **General** (fino a 600), accorci il testo o scelga un modello più veloce come gemini-2.0-flash.

**"The model hit the token limit before returning any text. Increase "Max Tokens" …" oppure "The model returned an empty response."**
La risposta è stata tagliata o è vuota. Alzi **Max Tokens** in **Settings**, **Gemini**. Alcuni modelli Gemini 2.5 usano parte del limite per «pensare».

**"The response was blocked by the provider content filter. Try rewording the prompt."**
Google ha rifiutato di rispondere all'istruzione. Riscriva il modello o il testo del prodotto che esso usa.

**"Monthly generation budget reached. Raise it in the studio settings or wait until next month."**
Il tetto in **Settings**, **Studio**, **Monthly generation budget** è esaurito. Lo alzi o imposti 0 per nessun limite.

**"The reply was rejected because it contains a forbidden word from the studio settings."**
**Quality gate** è abilitato e la risposta conteneva una riga di **Forbidden words**. Il prodotto è rimasto invariato. Modifichi l'elenco, cambi il prompt o disabiliti il controllo.

**"Error! Prompt is missing or too short!"**
L'istruzione ha meno di 4 caratteri. Digiti un'istruzione completa o scelga un modello.

**Una riga di un'esecuzione di massa mostra "skipped Product skipped."**
**Existing text** è su **Skip if filled** e il campo aveva già del testo. Scelga **Replace**, **Add above** o **Add below** per scrivere comunque.

**Dopo aver rimosso un modello aggiunto, ogni richiesta fallisce.**
Rimuovere il modello attivo reimposta il nome del modello a gpt-4o, che Gemini non conosce. Apra **Settings**, **Gemini**, scelga un nome Gemini in **Model** (per esempio gemini-2.0-flash) e prema **Save**.

**Le schermate dicono ancora "OpenAi" o "gpt".**
Questa versione conserva ancora alcune diciture di una versione precedente: la conferma **OpenAi Settings Updated**, l'errore **OpenAi Model field is invalid!**, le etichette dei filtri "Products that have not been updated with OpenAi content" e "Products that already have been updated with OpenAi content" in **Generate**, **Products**, l'esempio "gpt-4.1" nella casella del modello e nel messaggio "Enter a model id such as gpt-4.1.", il nome del servizio "openai" nella colonna **Provider** di History e la riga del pannello **Help** "Paste the secret key from your OpenAI account". Sono tutte solo diciture. Il modulo chiama Google Gemini. Usi una chiave da https://aistudio.google.com/apikey e nomi di modelli Gemini.

**Il pulsante "Module settings" in Generate apre la pagina di un altro modulo o un errore.**
Quel pulsante punta alle impostazioni di un vecchio modulo gemello e non a questo. Usi **Settings** nella barra del modulo.

**Il modulo in basso "Generate category content" non fa nulla.**
Ricarica soltanto il filtro delle categorie. Prema **Run on the categories below** nel pannello sopra di esso.

**Il cron dei prodotti non fa nulla.**
Controlli, in quest'ordine: **Enable Cron Feature** è su **Yes** e salvato; l'indirizzo contiene `&action=generateProductContent`; il segreto nell'indirizzo corrisponde a quello sullo schermo; è scelto un **Prompt Template**; **Enable Debug** è su **No**; il suo server chiama davvero l'indirizzo (guardi il log del suo scheduler). Una prova nel browser con **Enable Debug** su **Yes** stampa ciò che verrebbe eseguito.

**Il comando cron sullo schermo termina subito dopo il segreto e il pulsante "Generate Token" non fa nulla.**
Limitazione nota di questa versione. La riga di comando non viene completata dalla pagina e il pulsante del token non compila il campo. Costruisca lei stessa l'indirizzo come mostrato in 3.12 e digiti un segreto lungo se vuole cambiarlo.

**Il cron continua a riscrivere i prodotti di una categoria spuntata.**
Quando **Product Categories** è spuntato, a ogni chiamata vengono selezionati i prodotti la cui categoria principale è spuntata, anche se erano già stati scritti. Per le esecuzioni pianificate lasci vuoto l'albero delle categorie e limiti l'esecuzione con **Product ID list**, oppure usi **Enable Debug** per controllare quali prodotti vengono scelti prima di pianificare.

**Il cron elabora di nuovo gli stessi prodotti dopo che ho svuotato History.**
Le modalità cron **pendingGemini** e **pendingField** usano History per sapere cosa è già scritto. Dopo **Clear list** tutto conta come non scritto. Usi **emptyField** se vuole che i campi compilati vengano lasciati in pace.

**Top P, Frequency Penalty e Presence Penalty non cambiano nulla.**
In questa versione solo **Temperature** e **Max Tokens** vengono inviati a Gemini. Gli altri tre sono memorizzati ma non usati.

**Manca la voce di menu "AI Content Generator".**
Apra ancora una volta una qualsiasi pagina del back office; il modulo rimette la voce al suo posto. Se continua a mancare, disinstalli e reinstalli il modulo (questo cancella History e impostazioni).

**Nessun pannello "Modules → My AI Gemini" nella pagina del prodotto.**
Verifichi che **Product edit page Form** (o **Product Edit History**) sia abilitato in **Settings**, **General**, che il prodotto sia stato salvato una volta e che stia aprendo la scheda **Modules** del prodotto. I pulsanti **Generate with AI** accanto ai campi vengono aggiunti separatamente dal modulo e possono restare visibili anche quando il pannello è disattivato.

**Il testo che ho generato è sparito dopo aver salvato il prodotto.**
Il modulo del prodotto era aperto con i vecchi valori. Ricarichi la pagina del prodotto dopo aver usato **Fill** e modifichi solo dopo. Usi **Restore** nella scheda **History** per riportare un testo precedente.

**Il blocco Dashboard nella dashboard principale di PrestaShop è vuoto.**
Quel blocco non riceve i dati di History. Apra **AI Content Generator**, **Dashboard**.

**Ricerca di foto: "The search did not return photos. Reload the product page and try again." oppure "No photos were found on the suggested pages."**
Gemini ha suggerito pagine che non è stato possibile leggere o che non contenevano immagini adatte. Prema di nuovo **Find pages** o migliori **AI Image Search Prompt** in **Images**. Le pagine su indirizzi privati o locali vengono rifiutate.

**New product mostra "Failed to parse AI response. Please try again." oppure "Failed to create product".**
Gemini non ha restituito una bozza utilizzabile, oppure il negozio ha rifiutato i dati (per esempio una lingua senza nome nella lingua predefinita). Prema di nuovo **Generate data**, scelga la lingua predefinita del negozio e controlli il numero della categoria.

## 6. Per lo sviluppatore

### 6.1 Panoramica

| Elemento | Valore | Dove è definito |
|---|---|---|
| Nome tecnico | `myaigemini` | File principale del modulo |
| Classe principale | `myaigemini` (extends `Module`) | File principale del modulo |
| Versione | **1.1.0** | File principale del modulo |
| Nome visualizzato | My AI Gemini - AI content generation | File principale del modulo |
| Autore | MyPresta.eu | File principale del modulo |
| Tab | `front_office_features` | File principale del modulo |
| PrestaShop | 1.6 – 9.99.99 (`ps_versions_compliancy`) | File principale del modulo |
| PHP | 7.0 o successivo (`MIN_PHP_VERSION`, controllato in `install()`) | File principale del modulo |
| API | Google Gemini su `https://generativelanguage.googleapis.com/v1beta`, chiave come parametro di query `key` | File principale del modulo |
| Origine della chiave | https://aistudio.google.com/apikey | File principale del modulo |
| Prefisso di configurazione | `MYPRESTA_MYAIGEMINI_` | File principale del modulo |
| Prefisso CSS | `.mag-` (più `.myaigemini-ui`, `.myaigemini-stats`) | File principale del modulo |

Flusso dei dati: una schermata (pannello del prodotto, esecuzione di massa, finestra della barra superiore, Playground) invia in POST al front controller del modulo `ajax` con il token segreto; il controller costruisce il prompt (modello, segnaposto, `Studio::decorate`), chiama `OpenAIService` (un client Gemini mantenuto con il suo vecchio nome di classe), scrive il risultato nel prodotto o nella categoria e inserisce una riga in `myaigemini_log`. Il cron funziona allo stesso modo tramite il front controller `cron`. Il testo generato viene salvato da `Product::save()` o `Category::save()`.

Parametri URL nella pagina di configurazione: `mag_tab` (`dashboard`, `settings`, `updates`), `mag_sub` (`general`, `openai`, `studio`, `templates`, `playground`; `openai` è la scheda **Gemini**; su **Generate** `products` e `categories`), intervallo della dashboard `mcg_preset` (`today`, `7`, `30`, `90`, `month`, `all`), `mag_from`, `mag_to`. In History: `stats_preset`, `stats_from`, `stats_to`, `stats_model`, `stats_type`, `stats_status`, `stats_lang`, `stats_employee`, `stats_entity`, `stats_q`.

### 6.2 File

| File | Scopo | Area |
|---|---|---|
| `myaigemini.php` | Classe principale: installazione e disinstallazione, moduli di configurazione (General, Gemini, Studio, modelli), Dashboard, hook, posizionamento del menu, catalogo dei modelli. | Codice del modulo |
| `autoload.php` | Carica le classi del modulo senza Composer. | Codice del modulo |
| `src/OpenAIService.php` | Client Gemini (`generateContent`, `models`); timeout; ricorda i parametri che un modello rifiuta. | Codice del modulo |
| `src/Studio.php` | Decorazione del prompt, budget mensile, controllo delle parole vietate, SEO pack e prompt dei testi alt. | Codice del modulo |
| `controllers/admin/AdminMyAIGeminiMain.php` | Voce di menu; reindirizza alla Dashboard. | Codice del modulo |
| `controllers/admin/AdminMyAIGeminiSettings.php` | Nascosto; reindirizza a Settings. | Codice del modulo |
| `controllers/admin/AdminMyAIGemini.php` | **Generate** (filtri e pannelli di massa). | Codice del modulo |
| `controllers/admin/AdminMyAIGeminiProductCreator.php` | **New product**. | Codice del modulo |
| `controllers/admin/AdminMyAIGeminiCron.php` | Moduli **Cron**. | Codice del modulo |
| `controllers/admin/AdminMyAIGeminiUsage.php` | **History**. | Codice del modulo |
| `controllers/admin/AdminMyAIGeminiImageFinder.php` | Modulo **Images** e azioni di ricerca delle foto. | Codice del modulo |
| `controllers/front/ajax.php` | Azioni JSON usate dalle schermate. | Codice del modulo |
| `controllers/front/cron.php` | Endpoint del cron. | Codice del modulo |
| `lib/sectionHelp.php` | Testo del pannello Help. | Codice del modulo |
| `lib/updateChecker.php` | Controllo degli aggiornamenti (`myaigeminiUpdate`). | Codice del modulo |
| `lib/prestashop9compatibility.php`, `lib/searchTool/` | Helper di compatibilità e strumento di ricerca del modulo. | Codice del modulo |
| `views/templates/hook/*.tpl`, `views/templates/admin/product_creator.tpl` | Schermate. | Codice del modulo |
| `views/js/back.js`, `product-fields.js`, `image-finder.js`, `admin-products-bulk.js`, `dashboard.js`, `admin-help.js`, `chart.min.js` | Comportamento delle schermate. | Codice del modulo |
| `views/css/admin-nav.css`, `back.css`, `stats.css` | Stili. | Codice del modulo |
| `translations/*.php` | File di lingua (molte lingue). | Codice del modulo |

Risorse referenziate ma non fornite: `views/js/admin.js`, `views/css/admin.css` (controller Main e Settings), `views/js/product_creator.js` e `views/css/product_creator.css` (controller New product). Vengono saltate silenziosamente; i pulsanti di New product sono gestiti da `back.js`.

### 6.3 Controller

| Controller | Classe e genitore del menu | Note |
|---|---|---|
| `AdminMyAIGeminiMain` | `AdminMyAIGeminiMainController` (genitore: sezione Modules) | Voce visibile **AI Content Generator**. `initContent()` reindirizza alla pagina di configurazione con `mag_tab=dashboard`. |
| `AdminMyAIGemini` | `AdminMyAIGeminiController` (genitore: AdminMyAIGeminiMain) | Scheda nascosta (`active = 0`). **Generate**. `mag_sub` `products` / `categories`; nomi di invio `filterProducts`, `filterCategories`. |
| `AdminMyAIGeminiProductCreator` | `AdminMyAIGeminiProductCreatorController` (genitore: AdminMyAIGeminiMain) | Nascosto. AJAX `generateProductData`, `extractImages`, `createProduct`, `generateImages` (risposta segnaposto "coming soon"). |
| `AdminMyAIGeminiSettings` | `AdminMyAIGeminiSettingsController` (genitore: AdminMyAIGeminiMain) | Nascosto. Solo reindirizzamento. |
| `AdminMyAIGeminiCron` | `AdminMyAIGeminiCronController` (genitore: AdminMyAIGeminiMain) | Nascosto. Invio `submitCronUpdate`, `submitCatCronUpdate`. |
| `AdminMyAIGeminiUsage` | `AdminMyAIGeminiUsageController` (genitore: AdminMyAIGeminiMain) | Nascosto. `clear_log` svuota la tabella del log. |
| `AdminMyAIGeminiImageFinder` | `AdminMyAIGeminiImageFinderController` (genitore: AdminMyAIGeminiMain) | Nascosto. Azioni `searchImages`, `extractImages` (host privati rifiutati), `saveImages`. Invio del modulo `submitImageFinder`. |
| `ajax` (front) | `myaigeminiajaxModuleFrontController` (genitore: –) | Richiede `secret_token` uguale a `MYPRESTA_MYAIGEMINI_TOKEN`, altrimenti "Error! Invalid token!". Azioni: `initiatePrompt`, `updateSettings`, `updateProduct`, `initiateProductRestore`, `updateCategory`, `generateSeoPack`, `generateAltTexts` (nessun pulsante chiama quest'ultima). |
| `cron` (front) | `MyAIGeminiCronModuleFrontController` (genitore: –) | Richiede `MYPRESTA_MYAIGEMINI_ENABLE_CRON` e un `secret` uguale a `_SECRET` o `_CAT_SECRET` (ciascun segreto apre entrambe le azioni). `action` = `generateProductContent` o `generateCategoryContent`. |

I moduli dei filtri di Generate collegano "Module settings" a `configure=mychatgpt`. L'output dell'hook del pannello di modifica dei prodotti viene costruito in `renderProductModulesContent()`.

SQL di selezione del cron: il filtro delle categorie e l'elenco degli id dei prodotti vengono accodati alla clausola WHERE; la condizione sulla categoria (`id_product IN (…) OR id_category_default IN (…)`) non è racchiusa tra parentesi, quindi l'OR amplia l'intera condizione. `pendingGemini` e `pendingField` usano `NOT EXISTS` su righe di `myaigemini_log` il cui stato è vuoto o diverso da `error`; `pendingField` fa corrispondere anche `type = product_<field>` / `category_<field>`. `emptyField` unisce `product_lang` / `category_lang` per la lingua scelta. Lunghezze dei testi di prodotto al salvataggio: nome 128, descrizione breve 799 (cron) o 800 (ajax), meta title 69, meta description 159.

### 6.4 Hook

Registrati in `install()`: `displayAdminProductsMainStepLeftColumnMiddle` (restituisce una stringa vuota), `displayAdminProductsMainStepLeftColumnBottom` (vuoto), `actionProductFormBuilderModifier` (nessuna azione), `displayAdminProductsExtra` (renderizza il pannello nella scheda **Modules** del prodotto), `displayBackOfficeHeader` (carica le risorse, esegue `ensureLongSecrets()` e `placeModuleMenu()`, registra una sola volta la scheda del cercatore di immagini, aggiunge variabili JS), `displayBackOfficeTop` (la finestra della barra superiore quando `TOPCTA` è attivo e variabili JS per gli id di categoria, CMS e marchio), `displayFooter` (vuoto), `displayHeader` (vuoto), `dashboardZoneTwo` (renderizza `dashboard.tpl` senza i suoi dati). `actionProductGridDataModifier` esiste come metodo ma non è registrato. Il modulo non ha i metodi `enable()` e `disable()`. Il modulo non espone hook personalizzati.

`hookDisplayBackOfficeHeader` carica `product-fields.js` nelle pagine di modifica di prodotto e categoria indipendentemente dall'interruttore `MYPRESTA_MYAIGEMINI_PRODUCT` (l'interruttore controlla solo il pannello della scheda Modules).

### 6.5 Override

Il modulo non ha override. Non sostituisce alcun file del core.

### 6.6 Database

| Tabella | Contenuto | Note |
|---|---|---|
| `myaigemini_prompt` | `id_prompt` (PK), `status`, `title` (128), `prompt` (text), `date_generated`. 16 righe inserite all'installazione. | Creata all'installazione, eliminata alla disinstallazione |
| `myaigemini_log` | `id_log` (PK), `id_product`, `id_category`, `id_cms`, `id_manufacturer`, `id_lang`, `id_employee`, `type`, `method`, `status`, `ai_service`, `model`, `http_code`, `duration_ms`, `prompt_tokens`, `completion_tokens`, `total_tokens`, `error_message`, `prompt`, `reply`, coppie `old_` / `new_` per `name`, `description`, `description_short`, `meta_title`, `meta_description`, `tags`, `date_updated`. Indici su `id_product` e `status`. | Creata all'installazione, eliminata alla disinstallazione |

Entrambe le tabelle usano il motore del database del negozio e vengono eliminate alla disinstallazione. Le tre colonne dei token vengono inoltre aggiunte a runtime da `ensureUsageColumns()` quando la Dashboard, History o una scrittura di log di cron/ajax ne ha bisogno e mancano. `ai_service` memorizza sempre il valore `openai` (residuo). Il `postProcess()` del generatore di massa scrive i valori dei filtri inviati in chiavi di configurazione come `MYPRESTA_MYAIGEMINI_FIELD`, `_LANGUAGE`, `_CONTENT`, `_DELAY`, `_EXISTING`, `_HISTORY`, `_STATUS`, `_STOCK`, `_PROD_*`, `_CATEGORIES`, `_BRANDS` a ogni caricamento di **Generate**. La disinstallazione non elimina queste chiavi.

### 6.7 Chiavi di configurazione e traduzioni

Prefisso `MYPRESTA_MYAIGEMINI_`. Valori scritti da `install()`:

| Chiave | Predefinito | Significato |
|---|---|---|
| `LIVE_MODE`, `DEBUG_MODE` | `0`, `0` | Interruttori live e debug (`PrestaShopLogger` con tipo di oggetto `MyAIGemini`). |
| `TIMEOUT` | `120` | Secondi; limitato a 10–600; il timeout del browser è questo valore più 15. |
| `PRODUCT_LOG`, `TOPCTA`, `PRODUCT` | `1`, `1`, `1` | Elenco di ripristino, finestra della barra superiore, pannello del prodotto. |
| `IMAGEFINDER_ENABLE`, `IMAGEFINDER_PROMPT` | `1`, testo integrato | Interruttore e istruzione della ricerca di foto. `IMAGEFINDER_TAB_OK` segna la riparazione una tantum della scheda. |
| `TOKEN`, `SECRET`, `CAT_SECRET` | 32 caratteri casuali | Token ajax, segreto del cron dei prodotti, segreto del cron delle categorie. I valori inferiori a 24 caratteri vengono rigenerati alla pagina successiva del back office. |
| `API_KEY` | un singolo spazio | Salvata senza spazi ai bordi; il modulo mantiene la chiave salvata se la casella è vuota. |
| `MODEL`, `EXTRA_MODELS` | `gemini-2.0-flash`, vuoto | Modello attivo e nomi aggiunti (uno per riga). Rimuovere il modello aggiunto attivo imposta `gpt-4o`. |
| `TEMPERATURE`, `MAX_TOKENS` | `0.7`, `3200` | Inviati a Gemini come `temperature` e `maxOutputTokens`. |
| `TOP_P`, `FREQ_PEN`, `PRES_PEN` | `1`, `0`, `0` | Memorizzati; non inclusi nella richiesta a Gemini. |
| `MODEL_CAPS` | vuoto | Parametri appresi per modello. |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | vuoto | Testi di Studio. |
| `BUDGET`, `QUALITY` | `0`, `1` | Tetto mensile; quality gate. |
| `ENABLE_CRON` | `0` | Interruttore globale del cron. |
| `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | `6`, `6` | Scelta dell'intervallo (6 = Every Hour). Solo memorizzato; usato per la visualizzazione. |
| `updatedField`, `catupdatedField` | `description`, `description` | Campo del cron (i nomi delle chiavi sono scritti come `MYPRESTA_MYAIGEMINI_updatedField` ecc.). |
| `productTarget`, `categoryTarget` | `pendingGemini` | Modalità di selezione del cron. |
| `productsToUpdate`, `categoriesToUpdate` | `5`, `5` | Dimensione del lotto. |
| `promptTemplateId`, `catpromptTemplateId` | vuoto | Modello del cron. |
| `languageId`, `catlanguageId` | `PS_LANG_DEFAULT` | Lingua del cron. |
| `debug`, `catdebug`, `interval_select` | `0`, `0`, vuoto | Debug del cron e selettore legacy. |
| `productIdsList`, `categories` | vuoto | Filtri del cron. |

La disinstallazione elimina le chiavi precedenti più `ACTIVE_SERVICE`, `GEMINI_API_KEY` e `GEMINI_MODEL` (vecchi nomi), le schede e entrambe le tabelle. Il back office rimuove inoltre `GEMINI_API_KEY`, `GEMINI_MODEL` e `ACTIVE_SERVICE` a ogni caricamento della pagina di configurazione. Le chiavi condivise `mypresta_updates`, `update_myaigemini` e `updatev_myaigemini` appartengono al controllo degli aggiornamenti e non vengono rimosse.

Traduzioni: aggiunga una lingua creando `translations/{iso}.php` (il modulo ne fornisce molte). I testi passano attraverso `$this->l()` nella classe principale e `l s='…' mod='myaigemini'` nei template. I controller di amministrazione traducono tramite `trans()` su PrestaShop 8 e 9 e tramite il `l()` del modulo su 1.6 e 1.7. Testi non tradotti: il titolo di colonna **ID**, l'etichetta **Cron Job Secret Token** e **Generate Token**, i messaggi JavaScript in `back.js`, `image-finder.js` e nella pagina di selezione delle foto ("Write a prompt first.", "Looking for photos…" e simili) e la bozza restituita da New product. Le descrizioni dei campi sono voci `desc` costruite con `fieldHelp()` nelle definizioni dei moduli, nella forma "What it does / How to configure / Effect"; il testo del pannello Help si trova in `lib/sectionHelp.php`.

I segnaposto vengono sostituiti in `controllers/front/ajax.php` (esecuzioni interattive) e `controllers/front/cron.php` (cron); gli elenchi sono uguali tranne che il cron non ha segnaposto CMS o di marchio.

### 6.8 Estensione

Non c'è alcun template front da sovrascrivere in un tema. Per aggiungere segnaposto ai prompt, estenda i blocchi di sostituzione in `ajax.php` e `cron.php`. Per cambiare il comportamento del servizio di IA, modifichi `src/OpenAIService.php` (`createChatCompletion()` costruisce il payload di Gemini). Per aggiungere un modello, usi **Add a Gemini model** oppure estenda `getPopularGeminiModels()`. Il CSS personalizzato può indirizzare le classi `.mag-` nelle schermate del modulo. Cambiare il formato dell'indirizzo del cron richiede di modificare `AdminMyAIGeminiCron.php` e i template `cron.tpl` e `cron-info.tpl`.

## 7. Assistenza

Pagina del modulo: https://mypresta.eu/ai-artificial-intelligence/product-and-category-descriptions-with-gemini.html

Per chiedere assistenza:

1. Acceda al suo account cliente su mypresta.eu.
2. Vada alla pagina dei contatti.
3. Scelga l'oggetto **Support for paid modules**. Per i moduli a pagamento il modulo indica che occorre aver effettuato l'accesso; dopo l'accesso, scelga questo modulo dalla cronologia degli acquisti.
4. Descriva cosa ha fatto, cosa si aspettava e cosa ha visto. Aggiunga la riga rossa di **History** (la apra con **View**) o il testo del messaggio dallo schermo, e il nome del modello che usa.
