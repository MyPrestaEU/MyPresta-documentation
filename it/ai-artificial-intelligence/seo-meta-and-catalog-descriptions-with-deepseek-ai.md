---
title: "My AI DeepSeek - AI content generation - documentazione e manuale utente"
description: "Manuale di configurazione, uso quotidiano e risoluzione dei problemi per i titolari di negozi che hanno già installato il modulo My AI DeepSeek in PrestaShop."
sidebar:
  label: "My AI DeepSeek - AI content generation - documentazione e manuale utente"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo SEO meta and catalog descriptions with DeepSeek AI su MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-deepseek-ai.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-deepseek-ai/)
>
> ---


## 1. Requisiti

Il modulo scrive i testi del catalogo tramite il servizio DeepSeek, quindi il Suo negozio ha bisogno di una connessione funzionante a DeepSeek e di un proprio account DeepSeek.

- **PrestaShop:** versioni dalla 1.6 alla 9.99.99.
- **PHP:** 7.0 o successivo. Con una versione di PHP più vecchia l'installazione viene rifiutata con un messaggio che indica la versione richiesta e quella rilevata.
- **Estensione PHP:** cURL. Il server del negozio deve poter aprire connessioni HTTPS in uscita verso `https://api.deepseek.com/v1`. Se il Suo hosting blocca le connessioni in uscita, chieda all'hosting di consentirle.
- **Altri moduli:** nessuno. Il modulo non dipende da alcun altro modulo.
- **Account DeepSeek:** serve una chiave API. La crei su https://platform.deepseek.com/api_keys. L'utilizzo viene fatturato da DeepSeek al Suo account, non da MyPresta.eu.
- **Lingua del back office:** in questo manuale le schermate sono mostrate in inglese e gli screenshot provengono dal back office in inglese. I nomi in grassetto sono i nomi che vede sullo schermo.
- **Cataloghi grandi:** ogni campo generato è una richiesta a DeepSeek e richiede alcuni secondi. Un'elaborazione su centinaia di prodotti richiede molto tempo, e la scheda del browser deve restare aperta per tutta l'elaborazione nelle schermate Generate. Per i cataloghi grandi preferisca la schermata Cron, che lavora in background a piccoli lotti.

## 2. Installazione

### 2.1 Caricamento e installazione

1. Apra **Modules**, poi **Module Manager**.
2. Faccia clic su **Upload a module** e selezioni il file ZIP. Non lo decomprima prima.
3. Quando il caricamento termina, faccia clic su **Install** (se il pulsante è visibile) e poi su **Configure**.

L'installazione salva le impostazioni predefinite, crea le tabelle del modulo, aggiunge 16 modelli di prompt già pronti e aggiunge il modulo al menu del back office.

### 2.2 Cosa compare nel menu

Viene aggiunta una nuova voce di menu **AI Content Generator**. La sua prima pagina è **Dashboard**. All'interno del modulo ci si sposta tra le schermate con la barra di navigazione in alto in ogni pagina:

| Voce di navigazione | Cosa apre |
|---|---|
| **Dashboard** | Grafici di richieste, errori e token. |
| **Settings** | Cinque sezioni: **General**, **DeepSeek**, **Studio**, **Prompt templates**, **Playground**. |
| **Generate** | Due elenchi: **Products** e **Categories**. |
| **New product** | Crea una bozza di prodotto da una breve descrizione. |
| **Cron** | Crea gli indirizzi delle attività pianificate per prodotti e categorie. |
| **History** | Ogni richiesta con il suo prompt, la risposta, lo stato e i token. |
| **Images** | Interruttore e prompt della ricerca di foto del prodotto. |
| **Updates** | Verifica se è stata pubblicata una versione più recente. |

Passando il mouse su una voce di navigazione compare un breve suggerimento nella forma What it does / How to configure / Effect.

### 2.3 Cache

L'installazione non svuota la cache di PrestaShop. Se dopo la prima installazione la voce **AI Content Generator** manca nel menu, svuoti la cache in **Advanced Parameters**, **Performance** e ricarichi il back office.

### 2.4 Disinstallazione e reinstallazione

- **Rimosso:** la voce di menu, l'elenco dei modelli di prompt, la tabella History con tutte le sue righe e le impostazioni principali del modulo, inclusa la chiave API.
- **Conservato:** ogni testo già scritto in prodotti e categorie. Il modulo non rimuove mai i testi del catalogo.
- **Possibili residui:** alcuni valori di filtro salvati delle schermate Generate possono restare nella configurazione del negozio. Non causano alcun danno.
- **Reinstallazione:** una nuova installazione parte dai valori predefiniti. Modelli di prompt, History e chiave API vengono persi, quindi annoti i Suoi modelli e le Sue regole Studio prima di disinstallare.

## 3. Configurazione e lavoro quotidiano nel back office

### 3.1 L'intero processo in sintesi

Il modulo non ha passaggi lato cliente. I Suoi collaboratori avviano ogni azione nel back office.

1. **Una volta:** incolli la chiave API di DeepSeek e scelga un modello in **Settings**, **DeepSeek**. Facoltativamente compili **Studio** (voce del marchio, parole vietate, limite mensile).
2. **Singolo prodotto:** apra un prodotto, vada alla scheda **Modules**, **My AI DeepSeek**. Usi **Generate** per scrivere i campi, **Simulate** per provare prima, **Photos** per trovare immagini e **History** per ripristinare un testo precedente.
3. **Molti prodotti o categorie:** apra **Generate**, filtri l'elenco, scelga un prompt e un ambito e prema **Run**. Ogni riga mostra il proprio risultato al termine.
4. **Senza supervisione:** apra **Cron**, salvi la definizione di un lotto, copi l'indirizzo e lo consegni all'utilità di pianificazione del server.
5. **Controllo:** **History** mostra ogni richiesta. **Dashboard** mostra i totali. Nulla va perso: il testo precedente di ogni campo scritto viene conservato per **Restore** sul prodotto.
6. **Nuovo prodotto da un'idea:** **New product** crea una bozza e, dopo che l'ha accettata, un prodotto reale.

Ogni richiesta viene salvata in **History** con lo stato **Success** o **Error**. Una risposta che viola l'elenco **Forbidden words**, o che arriva dopo l'esaurimento del **Monthly generation budget**, non viene scritta nel prodotto.

![Dashboard](https://mypresta.eu/docs/images/docs/myaideepseek-dashboard.webp)

### 3.2 Dashboard

Apra **AI Content Generator**, poi **Dashboard**. La pagina rappresenta nei grafici le richieste a DeepSeek, i token e gli errori salvati in **History** per l'intervallo scelto. Da questa pagina nel catalogo non viene generato né modificato nulla.

| Elemento | Valore iniziale | Cosa fa |
|---|---|---|
| **Today**, **7 days**, **30 days**, **90 days**, **This month**, **All time** | il modulo si apre con un intervallo predefinito | Intervalli di date rapidi. Faccia clic su uno per ridisegnare la pagina. |
| **From** / **To** e **Apply** | vuoto | Il Suo intervallo personale. Le schede e i grafici lo seguono. |
| Riga **Active service** | – | Mostra quale servizio usa il modulo. |
| Schede **Requests**, **Errors**, **Tokens sent**, **Tokens received** | – | Numero di chiamate salvate, di chiamate non riuscite, dimensione dei prompt e dimensione delle risposte nell'intervallo. |
| Grafici **Requests and errors**, **Tokens sent and received**, **Requests by model** | – | Curve giorno per giorno e una suddivisione per modello. |

La pagina compare anche come piccolo blocco nella **Dashboard** standard di PrestaShop con collegamenti rapidi a **Generate**, **History** e **Cron**.

### 3.3 Settings – General

Apra **Settings**, poi **General**. Questi interruttori decidono quanto a lungo può durare una chiamata e quali strumenti vedono i collaboratori. Il salvataggio qui non modifica alcun testo di prodotto.

![Settings – General](https://mypresta.eu/docs/images/docs/myaideepseek-settings-general.webp)

| Campo | Valore iniziale | Cosa fa |
|---|---|---|
| **Live mode** | Disabled | Indica che il modulo gira sul negozio reale e non su una configurazione di prova. Lo attivi sul negozio di produzione. Su una copia di staging lo lasci disattivato se non vuole che il personale consideri gli strumenti pronti. Gli strumenti funzionano allo stesso modo in entrambi gli stati. |
| **Debug mode** | Disabled | Scrive ulteriori dettagli diagnostici quando una chiamata a DeepSeek fallisce. Lo attivi solo mentre indaga su un errore, poi lo disattivi. I messaggi tecnici vanno nel log di PrestaShop. I clienti non li vedono mai. |
| **API timeout (seconds)** | 120 | Quanti secondi può durare una chiamata a DeepSeek prima che il modulo si arrenda. Usi 120 per le descrizioni normali. Lo alzi verso 600 per pacchetti SEO lunghi o per il modello di ragionamento. Non scenda sotto 10. Un timeout breve fallisce in fretta e scrive un errore in History. Un timeout lungo attende una risposta lenta. |
| **Product Edit History** | Enabled | Mostra nella pagina del prodotto le precedenti scritture dell'IA, in modo che un redattore possa rimettere un vecchio valore. Disattivato nasconde questo elenco. Le righe passate restano comunque in **History**. |
| **Admin Top Bar CTA** | Enabled | Aggiunge un collegamento nella barra superiore del back office che apre il generatore in ogni pagina. Disattivato rimuove solo quel pulsante. Il menu del modulo resta. |
| **Product edit page Form** | Enabled | Mostra il pannello del generatore e i pulsanti Generate with AI nella pagina di modifica del prodotto (PrestaShop 1.7, 8 e 9). Lo disattivi se devono essere usati solo la generazione di massa e il cron. |
| **AI Image Finder** | Enabled | Permette a un redattore di chiedere al modello pagine che probabilmente contengono foto del prodotto corrente. Non viene scaricato nulla finché qualcuno non conferma un'immagine. Disattivato nasconde la ricerca, e la scheda **Photos** spiega allora come attivarla. |
| **AI Image Search Prompt** | istruzione in inglese già pronta | L'istruzione inviata quando qualcuno cerca immagini del prodotto. Il nome e la descrizione del prodotto vengono inseriti per il prodotto corrente. Mantenga la richiesta di un elenco di indirizzi di pagine. Un prompt più preciso dà pagine più pertinenti. |

Prema **Save**. Compare una conferma verde. Gli stessi due campi immagine esistono in **Images**.

### 3.4 Settings – DeepSeek

Apra **Settings**, poi **DeepSeek**. Questi sono l'account e il campionamento usati da ogni generazione: i pulsanti del prodotto, le elaborazioni di massa, il cron e il playground.

![Settings – DeepSeek](https://mypresta.eu/docs/images/docs/myaideepseek-settings-deepseek.webp)

| Campo | Valore iniziale | Cosa fa |
|---|---|---|
| **DeepSeek API KEY** | vuoto | Il segreto che permette a questo negozio di chiamare il Suo account DeepSeek. Incolli la chiave da https://platform.deepseek.com/api_keys. Gli spazi vengono rimossi al salvataggio (vede una nota che indica che la chiave è stata pulita). Lasci il campo intatto per mantenere la chiave salvata. Una chiave vuota o errata fa fallire le chiamate e l'errore viene scritto in History. |
| **Model** | `deepseek-chat` | Il modello che scrive il testo. Modelli integrati: `deepseek-chat` (veloce, la scelta normale) e `deepseek-reasoner` (modello di ragionamento, più lento). Vengono mostrati anche i modelli che aggiunge Lei. La generazione successiva usa il modello selezionato. Un modello che la Sua chiave non può usare restituisce un errore API invece del testo. |
| **Add a DeepSeek model** | riga vuota | Digiti un id di modello e prema il pulsante di aggiunta in questa riga. Vede **Model added.** I modelli integrati non possono essere rimossi (**Built-in models cannot be removed.**). Un modello già integrato risponde **That model is already built in.** I modelli aggiunti da Lei possono essere rimossi dalla stessa riga (**Model removed.**). |
| **Max Tokens** | 3200 | Limite massimo della lunghezza della risposta, contato in token e non in parole. Usi circa 256 per una meta description e 1000 o più per una descrizione HTML completa. Un limite basso tronca la risposta. Un limite alto consente un testo più lungo e costa di più. Con `deepseek-reasoner` una parte del limite viene spesa per il ragionamento, quindi gli dia un valore più grande. |
| **Temperature** | 0.7 | Con quanta libertà il modello sceglie le parole. Resti tra 0 e 1. Usi circa 0.2 per specifiche e testi meta e circa 0.7 per le descrizioni. Cambi Temperature oppure Top P, non entrambi. |
| **Top P** | 1 | Un altro modo per limitare quanto può essere sorprendente la parola successiva. Lasci 1 se ha già impostato Temperature. Un valore più basso come 0.9 dà un vocabolario più ristretto. |
| **Frequency Penalty Value** | 0 | Riduce le righe che ripetono la stessa frase all'interno di una risposta. Provi da 0.3 a 0.6 solo se le descrizioni continuano a copiare una stessa frase. Intervallo da –2 a 2. |
| **Presence Penalty Value** | 0 | Spinge la risposta verso argomenti nuovi. Usi 0 per impostazione predefinita. Un piccolo numero positivo aiuta quando ogni paragrafo ripete lo stesso punto. Intervallo da –2 a 2. |

Prema **Save**. I campi di campionamento non cambiano quali prodotti vengono aggiornati.

> Il modello di ragionamento può ignorare Temperature, Top P e le due penalità. Se una modifica a questi campi non ha effetto visibile con `deepseek-reasoner`, passi a `deepseek-chat`.

### 3.5 Settings – Studio

Apra **Settings**, poi **Studio**. Studio aggiunge le Sue regole interne a ogni prompt: i pulsanti del prodotto, le elaborazioni di massa e il cron. I campi vuoti vengono saltati. Il testo già salvato nel catalogo non viene riscritto quando cambia una regola.

![Settings – Studio](https://mypresta.eu/docs/images/docs/myaideepseek-settings-studio.webp)

| Campo | Valore iniziale | Cosa fa |
|---|---|---|
| **Brand voice** | vuoto | Dice al modello chi parla, in modo che il testo del prodotto si adatti al Suo negozio e non a un assistente generico. Scriva un breve brief, per esempio: officina specializzata, frasi brevi, niente enfasi. |
| **Audience** | vuoto | Indica il lettore a cui è destinato il testo, per esempio installatori professionisti o acquirenti alla prima esperienza. |
| **Tone** | vuoto | Imposta il tono: formale, caloroso, tecnico e così via. Bastano una o due parole. Non cambia il modello né la temperatura. |
| **Glossary** | vuoto | Nomi di marchi, materiali e grafie che il modello deve copiare esattamente. Un termine per riga. I termini non elencati possono comunque essere riformulati. |
| **Forbidden words** | vuoto | Parole ed espressioni che non devono comparire in una risposta salvata. Una per riga. Usato solo quando **Quality gate** è attivato. Una risposta che contiene una riga dell'elenco viene rifiutata e non viene scritta nel prodotto. Il tentativo resta in History come errore. |
| **Monthly generation budget** | 0 | Limita quante generazioni riuscite il negozio può eseguire nel mese di calendario in corso. Inserisca un numero intero. 0 significa nessun limite. Il contatore riparte il primo giorno del mese. Dopo il limite vede **Monthly generation budget reached. Raise it in the studio settings or wait until next month.** Le chiamate non riuscite non vengono contate. |
| **Quality gate** | Enabled | Controlla la risposta del modello rispetto a **Forbidden words** prima di salvare qualsiasi cosa. Attivato blocca una risposta corrispondente. Disattivato la salva anche se contiene una parola elencata. |

Prema **Save studio**. Vede **Studio settings saved.**

### 3.6 Settings – Prompt templates

Apra **Settings**, poi **Prompt templates**. Un modello è un'istruzione salvata. I redattori lo scelgono invece di digitare di nuovo lo stesso brief. Nella pagina del prodotto, nella generazione di massa e nel cron vengono proposti solo i modelli attivati.

![Settings – Prompt templates](https://mypresta.eu/docs/images/docs/myaideepseek-settings-templates.webp)

L'installazione aggiunge **16 modelli**: Product name 1 e 2; Product description da 1 a 7 (il numero 7 usa le immagini del prodotto); Product meta title da 1 a 3; Product meta description da 1 a 3; Product tags.

**Colonne dell'elenco:** ID, **Title**, **Prompt**, **Status** (faccia clic sul segno di spunta per alternare Enabled/Disabled), **Timestamp**. Azioni di riga: **Edit** e **Delete**. Azione di gruppo: **Delete** per le righe selezionate (conferma: *Are you sure you want to delete the selected prompts?*).

Usi il pulsante **+** nell'intestazione dell'elenco per creare un modello. Il modulo **Generate Prompt Template** ha questi campi:

| Campo | Valore iniziale | Cosa fa |
|---|---|---|
| **Status** | interruttore Enabled / Disabled | Mostra o nasconde il modello negli elenchi usati nella pagina del prodotto, nella generazione di massa e nel cron. Disattivi una bozza invece di eliminarla. |
| **Prompt title** | vuoto (obbligatorio) | Il nome che i redattori vedono nell'elenco dei modelli, per esempio HTML description with features. Non viene inviato al modello. |
| **Prompt content** | vuoto (obbligatorio) | L'istruzione inviata al modello. La scriva come se desse un brief a un copywriter e indichi lunghezza, HTML e lingua se contano. Può usare i segnaposto `{product_name}`, `{product_brand}`, `{product_features}` e `{product_tags}`. Vengono sostituiti con il prodotto per cui genera. |

Prema **Save Prompt**. Messaggi: **Prompt template successfully added!**, **Prompt template successfully updated!**, **Prompt template removed.** Se il modulo è incompleto vede **Failed to edit prompt template! Please fill the form with the right informations!** Il pulsante **Go Back to Module Settings** torna all'elenco.

Scriva i modelli per le categorie senza segnaposto di prodotto. Le schermate delle categorie non li inseriscono.

### 3.7 Settings – Playground

Apra **Settings**, poi **Playground**. È un blocco per gli appunti che chiama il modello attivo e stampa la risposta sotto il pulsante. Nessun prodotto, categoria o campo meta viene modificato.

![Settings – Playground](https://mypresta.eu/docs/images/docs/myaideepseek-settings-playground.webp)

| Campo | Valore iniziale | Cosa fa |
|---|---|---|
| Grande casella di testo (**Ask the model anything about your catalog**) | vuoto | L'istruzione per questa singola chiamata. La scriva in linguaggio semplice. Può citare il nome del negozio, l'indirizzo del negozio, il nome di un prodotto, un riferimento o le caratteristiche del prodotto se vuole che la risposta si basi sui dati del catalogo. Vengono aggiunte anche le Sue regole Studio. |
| **Generate** | – | Invia l'istruzione. La risposta compare sotto il pulsante. |

### 3.8 Generate – Products

Apra **Generate**, poi **Products**. È una schermata in due passaggi. Il primo passaggio costruisce soltanto un elenco. Non viene inviato nulla a DeepSeek finché non preme **Run** nel secondo passaggio.

![Generate – Products](https://mypresta.eu/docs/images/docs/myaideepseek-generate-products.webp)

**Passaggio 1 – Filter products to update.** I filtri non vengono salvati come impostazioni del negozio. I filtri vuoti non restringono l'elenco.

| Campo | Valore iniziale | Cosa fa |
|---|---|---|
| **Product Categories** | nessuna selezionata | Mantiene i prodotti delle categorie selezionate. Un albero vuoto lascia disattivato questo filtro. |
| **Brand** | prima opzione (vuota) | Mantiene i prodotti di un solo produttore. |
| **Product status** | – | **Active** (in vendita), **Disabled** (bozze) oppure **Both**. |
| **Product stock** | – | **Only in stock products** rimuove i prodotti senza quantità. **All products** ignora la giacenza. |
| **Update only** | – | Usa la cronologia di generazione: prodotti mai scritti da questo modulo, prodotti già scritti oppure **Update all**. Usi "not yet updated" per un primo passaggio e "already updated" per riscrivere. |
| **Product IDs** | vuoto | Numeri di prodotto separati da virgole, per esempio 12,45,103. |
| **Product Reference** | vuoto | Uno o più codici di riferimento separati da virgole. |
| **Product Add Date From** / **Product Add Date To** | vuoto | Intervallo della data di creazione. Vuoto significa nessun limite su quel lato. |
| **Minimum product ID** / **Maximum product ID** | vuoto | Numero di prodotto più basso e più alto da includere. |
| **Product Limit** | vuoto | Limita quanti prodotti vengono caricati nell'elenco. Su un catalogo grande usi un numero piccolo come 20, così che un'elaborazione non percorra per errore l'intero catalogo. |

Prema **Go to next step**. Il pulsante **Module settings** torna alle impostazioni del modulo.

**Passaggio 2 – Run.** Vede **Mass product generation** con la tabella dei prodotti filtrati (colonne **ID**, **Reference**, **Result**).

| Campo | Valore iniziale | Cosa fa |
|---|---|---|
| **Template** | **Choose a template** | Compila la casella del prompt da un modello attivato. Lasci la prima opzione e digiti il Suo prompt se preferisce. Il titolo in sé non viene inviato. |
| Casella del prompt | vuoto | Il testo inviato per ogni riga. I segnaposto di prodotto vengono sostituiti riga per riga. |
| **What to generate** | **Descriptions** | **Descriptions** scrive la descrizione lunga e quella breve. **Meta title and meta description** scrive entrambi i campi meta. **Descriptions and meta together** scrive tutti e quattro. Ogni campo è una richiesta separata. Gli altri campi restano invariati. |
| **Existing text** | **Replace** | **Replace** sovrascrive. **Skip if filled** mantiene i campi compilati e non chiama DeepSeek per essi. **Add above** e **Add below** mantengono il vecchio testo e vi aggiungono il nuovo. |
| **Languages** | la lingua del Suo back office, selezionata | Selezioni ogni lingua desiderata. Le lingue non selezionate mantengono il loro testo. Ogni lingua selezionata viene generata separatamente. |
| **Run on the list below** | – | Avvia l'elaborazione. Ogni riga mostra il proprio risultato appena quel prodotto termina. I prodotti fuori dal filtro non vengono toccati. |

Tenga aperta la scheda del browser finché ogni riga non mostra un risultato. Una riga non riuscita mostra il motivo; le altre righe proseguono.

### 3.9 Generate – Categories

Apra **Generate**, poi **Categories**. Funziona come la schermata dei prodotti, con meno filtri.

![Generate – Categories](https://mypresta.eu/docs/images/docs/myaideepseek-generate-categories.webp)

**Passaggio 1 – Filter categories to update.**

| Campo | Valore iniziale | Cosa fa |
|---|---|---|
| **Categories** | nessuna selezionata | Le categorie proposte nell'elenco. Lasci vuoto l'albero per includere ogni categoria che corrisponde allo stato. |
| **Category status** | – | **Active**, **Disabled** oppure **Both**. |

Prema **Go to next step**.

**Passaggio 2 – Mass category generation.**

| Campo | Valore iniziale | Cosa fa |
|---|---|---|
| Casella del prompt | vuoto | L'istruzione inviata per ogni categoria. Descriva tono, lunghezza e HTML. I segnaposto di prodotto qui non sono disponibili. |
| Selettore del campo | **Description** | L'unico campo che questa elaborazione scrive: **Description**, **Name**, **Meta title**, **Meta description** oppure **Additional description**. |
| Existing data | **Replace** | **Replace** sovrascrive. **Skip if filled** protegge i campi compilati e non chiama DeepSeek per quella categoria. |
| **Language** | la lingua del Suo back office | Una lingua per elaborazione. Esegua di nuovo per un'altra lingua. |
| **Run on the categories below** | – | Avvia l'elaborazione. La tabella mostra **ID** e **Result** per ogni categoria. |

### 3.10 New product

Apra **New product**. Trasforma una breve descrizione in una bozza di prodotto e può inserire quel prodotto nel catalogo.

![New product](https://mypresta.eu/docs/images/docs/myaideepseek-new-product.webp)

| Campo | Valore iniziale | Cosa fa |
|---|---|---|
| **What is the product?** | vuoto | La descrizione che il modello sviluppa in nome, descrizioni, campi meta, tag, caratteristiche, riferimento e prezzo. Poche frasi con materiali, pubblico e nomi da mantenere danno una bozza più fedele. Una casella vuota viene rifiutata. |
| **Optional source URL** | vuoto | Una pagina pubblica (http o https) che descrive il prodotto. Il suo testo viene aggiunto come contesto. Una casella vuota, o una pagina che il negozio non può leggere, viene ignorata. |
| **Language** | la lingua del Suo back office | La lingua in cui vengono salvati nome, descrizioni, meta e tag. Le altre lingue qui non vengono compilate. |
| **Default category ID** | 2 | Il numero della categoria da **Catalog**, **Categories**. 2 di solito è Home. Il nuovo prodotto viene collocato lì. |
| **Generate data** | – | Mostra la bozza come testo. Nessun prodotto viene salvato. |
| **Create product** | – | Aggiunge un prodotto **attivo** in quella lingua e categoria con nome, descrizioni, meta, tag, caratteristiche, prezzo e una quantità di magazzino dalla bozza. |

Se non è salvata alcuna chiave vede **Add an API key in the module settings first.** Controlli la bozza, il prezzo e la giacenza prima di vendere: la bozza è scritta da un modello.

### 3.11 Cron

Apra **Cron**. La pagina crea indirizzi che l'utilità di pianificazione del server richiama. Ogni chiamata compila **un lotto** e si ferma. Il negozio non fa nulla finché il Suo server non richiede l'indirizzo.

![Cron](https://mypresta.eu/docs/images/docs/myaideepseek-cron.webp)

La pagina ha due moduli: **CRON JOB Settings – Generate product content using DeepSeek** e il modulo corrispondente per le categorie. Può creare un numero illimitato di varianti di comando, una per campo.

**Modulo cron dei prodotti**

| Campo | Valore iniziale | Cosa fa |
|---|---|---|
| **Enable Cron Feature** | No | Un solo interruttore per l'intero negozio (prodotti e categorie). Lo attivi solo dopo aver salvato il segreto, il campo, la lingua e il prompt qui sotto. Il server deve comunque chiamare l'indirizzo. |
| **Cron Job Secret Token** | generato | Una lunga password che deve far parte dell'indirizzo dei prodotti. Senza di essa il negozio rifiuta la chiamata. Mantenga il valore mostrato dopo l'installazione. Se lo sostituisce, copi subito il nuovo indirizzo nell'utilità di pianificazione del server. Il pulsante **Generate Token** nel modulo potrebbe non inserire un nuovo valore; digiti Lei stesso una lunga stringa casuale se deve cambiarlo. |
| **Update Field** | description | L'unico campo del prodotto che questo comando riscrive: name, description, short description, meta title, meta description oppure tags. Per compilare più campi crei più comandi. |
| **Selected Products** | pendingDeepSeek | Quali prodotti sono ancora in attesa. **pendingDeepSeek**: prodotti mai modificati da questo modulo (qualsiasi campo). **pendingField**: prodotti per i quali questo campo non è ancora stato generato, per più comandi sugli stessi prodotti. **emptyField**: solo i prodotti il cui campo è vuoto. |
| **Product Categories** | nessuna selezionata | Limita l'elaborazione alle categorie selezionate. Vuoto significa che la categoria non è un filtro. |
| **Product ID list** | vuoto | Solo questi numeri di prodotto, separati da virgole. Le lettere vengono eliminate al salvataggio. |
| **Language** | lingua predefinita del negozio | Una lingua per comando. Le altre lingue richiedono un comando proprio. |
| **Product to update** | 5 products | Dimensione del lotto per chiamata, da 2 a 1000. Inizi con 5 o 10 in modo che un modello lento non raggiunga il limite di tempo del server. |
| **Prompt Template** | none | Un modello attivato. Ogni prodotto dell'elaborazione viene scritto da quel brief. |
| **Enable Debug** | No | **Yes** stampa il piano quando apre l'indirizzo in un browser e non salva nulla. Imposti **No** prima che l'utilità di pianificazione lo usi. |
| **CRON JOB interval** | Every Hour | Solo un suggerimento usato per costruire il testo del comando (da **Every 1 Minute** a **Every 6 Hours**). Il modulo non avvia un'utilità di pianificazione. |
| **Product Cron Job command** | – | Il comando finito da copiare. Salvi prima il modulo. |

Il **modulo cron delle categorie** ha il proprio **Cron Job Secret Token**, **Update Field** (name, description, meta title, meta description), **Selected categories** (le stesse tre regole), **Language**, **Categories to update** (dimensione del lotto), **Prompt Template** (scriva il brief per una categoria), **Enable Debug**, **CRON JOB interval** e **Category Cron Job command**. Valori predefiniti: description, pendingDeepSeek, 5 categories, Every Hour.

**Completi l'indirizzo.** L'indirizzo mostrato nella pagina può essere incompleto. Verifichi sempre che l'indirizzo finale contenga l'azione. Usi questa forma, sostituendo i segnaposto:

```text
https://YOUR-SHOP-DOMAIN/module/myaideepseek/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent&updatedField=description&productTarget=pendingDeepSeek&productsToUpdate=5&languageId=1&promptTemplateId=TEMPLATE_ID
https://YOUR-SHOP-DOMAIN/module/myaideepseek/cron?secret=YOUR_CATEGORY_SECRET&action=generateCategoryContent&updatedField=description&categoryTarget=pendingDeepSeek&categoriesToUpdate=5&languageId=1&promptTemplateId=TEMPLATE_ID
```

Usi `&action=generateProductContent` per i prodotti e `&action=generateCategoryContent` per le categorie. Senza di essa la chiamata non fa nulla. Se il Suo negozio non usa URL semplificati, copi l'indirizzo di base dalla pagina e aggiunga le parti con `&`. Non pubblichi questi indirizzi: il segreto che contengono è l'unica protezione.

Primo test consigliato: imposti **Enable Debug** su **Yes**, apra l'indirizzo nel browser e legga il piano. Poi lo imposti su **No**, pianifichi l'indirizzo e controlli **History** dopo la prima chiamata.

### 3.12 History

Apra **History**. Elenca ogni prompt, risposta, stato e conteggio dei token. La pagina è un report: filtrarla non elimina righe e non modifica prodotti.

![History](https://mypresta.eu/docs/images/docs/myaideepseek-history.webp)

| Elemento | Cosa fa |
|---|---|
| **7 days**, **30 days**, **This month**, **All time** | Intervalli di date predefiniti. |
| **From** / **To** | Intervallo di date personale. |
| **Model**, **Type**, **Status** (**Success** oppure **Error**), **Language**, **Employee** | Restringono la pagina a una porzione. |
| **Product / category ID** | Solo le richieste per quell'elemento. |
| **Prompt or reply contains** | Una parola che deve comparire nel prompt o nella risposta. |
| **Filter** | Applica i filtri. |
| Schede **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time** | Totali delle righe filtrate. Un trattino significa che DeepSeek non ha restituito un conteggio di token per quella chiamata. |
| Gruppi **By day**, **By model**, **By type**, **By language**, **By employee** | Tabelle di suddivisione. |
| Colonne dell'elenco **Status**, **Prompt**, **Reply / Error**, **Provider**, **Received**, **Entity ID**, **Timestamp** | Una riga per richiesta. Apra una riga per leggere il prompt e la risposta complete e i token. **Back to the list** torna indietro. |
| **Clear list** | Elimina le righe della cronologia. Vede **Log list successfully deleted.** I punti **Restore** della pagina del prodotto scompaiono con esse. Il testo del catalogo non viene modificato. |

### 3.13 Images

Apra **Images**. Salva l'interruttore e l'istruzione della ricerca di foto del prodotto. L'apertura di questa pagina non scarica nulla.

![Images](https://mypresta.eu/docs/images/docs/myaideepseek-images.webp)

| Campo | Valore iniziale | Cosa fa |
|---|---|---|
| **AI Image Finder** | Enabled | Mostra o nasconde la ricerca di foto nella pagina di modifica del prodotto. Un'immagine viene importata solo dopo che qualcuno l'ha confermata. |
| **AI Image Search Prompt** | istruzione in inglese già pronta | L'istruzione inviata quando qualcuno effettua una ricerca. Il nome del prodotto e la descrizione breve vengono inseriti. Mantenga la richiesta di un semplice elenco di indirizzi di pagine. |

Prema **Save**. Sono le stesse due impostazioni di **Settings**, **General**.

### 3.14 Updates

Apra **Updates**. Chiede a MyPresta.eu se è stata pubblicata una versione più recente di questo modulo.

![Updates](https://mypresta.eu/docs/images/docs/myaideepseek-updates.webp)

| Elemento | Valore iniziale | Cosa fa |
|---|---|---|
| **Automatic Notifications** | segue l'impostazione salvata | Permette al back office di avvisarLa quando esiste una versione più recente. |
| **Check Now** | – | Chiede una volta, subito. La pagina indica poi che questa copia è aggiornata oppure che esiste una versione più recente. |
| Collegamento alla pagina del modulo | – | Apre la pagina del modulo su MyPresta.eu. |

Il Suo catalogo e i testi generati non vengono toccati da questa pagina.

### 3.15 La pagina di modifica del prodotto

Apra **Catalog**, poi **Products**, modifichi un prodotto e apra la scheda **Modules**, poi **My AI DeepSeek**. A seconda della versione di PrestaShop e delle impostazioni di **General**, può vedere anche piccoli pulsanti **Generate with AI** accanto alla descrizione, alla descrizione breve e ai campi meta.

![Product edit](https://mypresta.eu/docs/images/docs/myaideepseek-product-edit.webp)

La scheda ha quattro parti: **Generate**, **Simulate**, **Photos** e **History**. Se **Product edit page Form** è disattivato resta solo **History** (quando **Product Edit History** è attivato).

**Generate** – ogni pulsante scrive un campo e salva il testo sul prodotto.

| Controllo | Cosa fa |
|---|---|
| Pulsanti **Language** | Scelgono una lingua del negozio. **Every language** le scrive tutte. |
| **If the field already has text** | **Replace** (predefinito), **Add above**, **Add below** oppure **Skip if filled**. |
| **Description** | Il testo lungo, con una breve introduzione e un elenco di caratteristiche. |
| **Short description** | Un breve riassunto semplice, sotto i 400 caratteri circa. |
| **Name** | Il titolo del prodotto che vedono i clienti. |
| **Meta title** | Il titolo nei risultati di ricerca, circa 70 caratteri. |
| **Meta description** | Il testo nei risultati di ricerca, circa 160 caratteri. |
| **Tags** | Un elenco di parole separate da virgole. |
| **SEO pack** – **Fill all** | Scrive il nome, entrambe le descrizioni ed entrambi i campi meta in un colpo solo. Se la risposta non è utilizzabile vede **The model did not return a usable SEO pack.** |
| **Fill** | Compare su ogni scheda di campo: genera e salva quel campo. |
| **Use your own instruction or a saved prompt** | Apre una casella di filtro, riquadri con i modelli attivati (**Standard brief** è quello predefinito) e una casella **Instruction**. Lasci vuota la casella per usare il brief standard del campo su cui preme. |

**Simulate** – le stesse schede di campo con un pulsante **Try**. La risposta viene mostrata in questa pagina e il prodotto **non** viene modificato. Lo usi per provare un prompt, poi torni a **Generate**.

**Photos** – vedere la sezione 3.16.

**History** – la tabella **When**, **Type**, **Status** e un pulsante **Restore**. **Restore** rimette sul prodotto il testo precedente di quella scrittura. Le righe senza valore precedente, o con un errore, non hanno il pulsante. Il report **History** dell'intero negozio non viene eliminato. Un elenco vuoto riporta **No generations for this product yet.**

![Product photos](https://mypresta.eu/docs/images/docs/myaideepseek-product-photos.webp)

### 3.16 Foto del prodotto

Apra la scheda **Photos** di un prodotto. Se **AI Image Finder** è disattivato, la scheda spiega come attivarlo in **Settings**, **General**.

1. Faccia clic su **Find pages**. DeepSeek suggerisce pagine web che probabilmente contengono foto del prodotto.
2. Compaiono pagine e immagini. Selezioni le immagini che desidera.
3. Faccia clic su **Add selected to this product**. Prima di questo clic non viene salvato nulla.

Il modello suggerisce pagine dalla propria conoscenza, non da una ricerca web in tempo reale. Controlli diritti d'autore e qualità delle immagini prima di pubblicarle.

## 4. Front del negozio

Il modulo non mostra nulla ai clienti. I due hook front che registra sono vuoti e non viene aggiunto al Suo tema alcun template, pulsante o blocco. Il testo scritto dal modulo compare nel Suo negozio solo come normali campi di prodotti e categorie (nome, descrizioni, meta tag, tag). Non è necessario modificare il tema.

Il modulo ha inoltre due indirizzi che un browser o un server possono aprire:

| Indirizzo | Chi lo usa | Cosa succede |
|---|---|---|
| L'indirizzo **Cron** con `&action=generateProductContent` oppure `&action=generateCategoryContent` | L'utilità di pianificazione del Suo server, oppure Lei durante i test | Viene scritto un lotto. Con **Enable Debug** impostato su **Yes** il piano viene stampato e non viene salvato nulla. Un segreto errato o mancante viene rifiutato. |
| L'indirizzo interno delle richieste usato dai pulsanti del back office | Il Suo browser mentre lavora nel back office | Richiede un token che il back office aggiunge automaticamente. Non lo digita mai. Se viene rifiutato, ricarichi la pagina del back office. |

## 5. Problemi

**Una generazione fallisce e History mostra un Error.**
Apra **History**, apra la riga e legga il messaggio. Le cause comuni sono qui sotto.

**La chiave API viene rifiutata o manca.**
Apra **Settings**, **DeepSeek**, incolli di nuovo la chiave da https://platform.deepseek.com/api_keys e prema **Save**. Nella pagina del nuovo prodotto l'avviso **Add an API key in the module settings first.** scompare dopo di ciò. Se DeepSeek segnala l'assenza di credito, ricarichi l'account presso DeepSeek.

**La chiamata termina con un timeout.**
Aumenti **API timeout (seconds)** in **Settings**, **General** (per `deepseek-reasoner` usi diverse centinaia di secondi). Per il cron riduca **Product to update**.

**Il testo viene troncato a metà frase.**
Aumenti **Max Tokens** in **Settings**, **DeepSeek**. Con `deepseek-reasoner` il limite copre anche il suo ragionamento.

**Le impostazioni non sembrano cambiare lo stile.**
Con `deepseek-reasoner`, **Temperature**, **Top P** e i due campi di penalità possono essere ignorati. Usi `deepseek-chat`. Controlli anche che **Studio** sia salvato e di aver usato la lingua giusta.

**Una risposta non viene salvata e sul prodotto non cambia nulla.**
Cause possibili: la risposta contiene una riga di **Forbidden words** e **Quality gate** è attivato (modifichi l'elenco o disattivi il filtro); **Existing text** è su **Skip if filled** e il campo contiene testo; il limite mensile è stato raggiunto (**Monthly generation budget reached. Raise it in the studio settings or wait until next month.**).

**Il nome del modello che ho digitato non funziona.**
Ha aggiunto un id che il Suo account non può chiamare. Selezioni di nuovo il `deepseek-chat` integrato e rimuova la Sua voce.

**L'elenco di Generate è vuoto o troppo corto.**
Controlli **Product status**, **Product stock**, **Update only** e **Product Limit**. Un errore comune è lasciare **Update only** su "already updated" in una prima esecuzione.

**Il cron non fa nulla.**
Controlli in quest'ordine: **Enable Cron Feature** è su **Yes**; l'indirizzo termina con il corretto `&action=…`; il segreto è quello attualmente mostrato; **Enable Debug** è su **No**; **Selected Products** ha ancora elementi in attesa; il server chiama davvero l'indirizzo. Un insieme completato smette di cambiare di proposito. Per più campi usi **pendingField** invece di **pendingDeepSeek**, perché il secondo salta un prodotto non appena un qualsiasi campo è stato generato.

**Il cron si è fermato dopo aver cambiato il segreto.**
Il vecchio indirizzo non è più valido. Copi il nuovo indirizzo (con `&action=…`) nell'utilità di pianificazione.

**La pagina dice "Error! Invalid token!" o i pulsanti restano muti.**
La pagina è rimasta aperta troppo a lungo. Ricarichi la pagina del back office e riprovi.

**La scheda Modules del prodotto non ha contenuti di My AI DeepSeek.**
Controlli che **Product edit page Form** oppure **Product Edit History** sia attivato, che il modulo sia attivo e che la cache sia stata svuotata.

**Non c'è il pulsante "Restore".**
La riga era un errore, la scrittura non aveva un valore precedente, oppure **Clear list** ha rimosso le righe di History.

**Alcune etichette dicono ancora "OpenAi".**
Alcuni messaggi ed etichette di filtro mantengono un nome precedente, per esempio **OpenAi Settings Updated** dopo il salvataggio del modulo **DeepSeek**, le opzioni "updated with OpenAi content" del filtro **Update only** o un vecchio nome di modello d'esempio in un suggerimento. Il servizio utilizzato è DeepSeek. In History la colonna **Provider** può mostrare il vecchio nome interno. Ciò non influisce sui risultati.

**Nel front del negozio non cambia nulla.**
Il modulo scrive normali campi del prodotto. Controlli il prodotto in **Catalog** e la cache del Suo tema.

## 6. Per lo sviluppatore

### 6.1 Panoramica

- **Nome tecnico:** `myaideepseek`
- **Nome del modulo nell'elenco:** My AI DeepSeek - AI content generation
- **Versione:** 1.0.0
- **Autore:** MyPresta.eu
- **Compatibilità con PrestaShop:** 1.6 – 9.99.99
- **PHP:** 7.0 o successivo (l'installazione rifiuta le versioni precedenti)
- **Rete:** cURL e HTTPS verso `https://api.deepseek.com/v1`
- **Prefisso di configurazione:** `MYPRESTA_MYAIDEEPSEEK_`
- **Flusso:** le impostazioni vengono lette dalla tabella di configurazione; i prompt vengono costruiti dal modello o dall'istruzione più le regole Studio; viene inviata una richiesta di chat per campo; la risposta viene controllata (Quality gate, budget), salvata sul prodotto o sulla categoria e registrata in `myaideepseek_log` con il valore precedente.

### 6.2 File

| File | Scopo |
|---|---|
| `myaideepseek.php` | Classe principale: installazione, disinstallazione, moduli di impostazioni, navigazione, hook, scheda del prodotto. |
| `autoload.php` | Caricamento delle classi per `src/` e `lib/`. |
| `src/OpenAIService.php` | Client HTTP per la chiamata di chat completion (mantenuto con il vecchio nome del file). |
| `src/Studio.php` | Aggiunge le regole Studio e il controllo di qualità. |
| `lib/updateChecker.php` | Verifica degli aggiornamenti presso MyPresta.eu. |
| `lib/sectionHelp.php` | Testi dei suggerimenti di aiuto. |
| `lib/searchTool/` | Supporto per l'autocompletamento. |
| `lib/prestashop9compatibility.php` | Supporto di compatibilità per PrestaShop 9. |
| `controllers/admin/` | Sette controller di amministrazione (vedere 6.3). |
| `controllers/front/ajax.php` | Azioni AJAX del back office (generare, ripristinare, ricerca di immagini). |
| `controllers/front/cron.php` | Generazione pianificata. |
| `views/templates/hook/*.tpl` | Scheda del prodotto, generatori di massa, dashboard, cron, history, playground, navigazione. |
| `views/templates/admin/product_creator.tpl` | Schermata del nuovo prodotto. |
| `views/js/` | `back.js`, `product-fields.js`, `image-finder.js`, `dashboard.js`, `admin-help.js`, `admin-products-bulk.js`, `chart.min.js`. |
| `views/css/` | `back.css`, `admin-nav.css`, `stats.css`. |
| `translations/{iso}.php` | Traduzioni del modulo. |

### 6.3 Controller

| Classe | Ruolo |
|---|---|
| `AdminMyAIDeepSeekMain` | Genitore del menu **AI Content Generator**. |
| `AdminMyAIDeepSeek` | **Generate** (`mds_sub=products` oppure `categories`). |
| `AdminMyAIDeepSeekProductCreator` | **New product**. |
| `AdminMyAIDeepSeekSettings` | Ingresso delle impostazioni (i moduli si trovano nella pagina di configurazione del modulo). |
| `AdminMyAIDeepSeekCron` | Moduli **Cron**. |
| `AdminMyAIDeepSeekUsage` | **History**. |
| `AdminMyAIDeepSeekImageFinder` | **Images**. |
| `ModuleFrontController` ajax | Richiede il parametro `secret_token` uguale a `MYPRESTA_MYAIDEEPSEEK_TOKEN`; altrimenti risponde *Error! Invalid token!* |
| `ModuleFrontController` cron | Richiede `secret` uguale al segreto dei prodotti o delle categorie. |

La pagina di configurazione del modulo usa `mds_tab` (`dashboard`, `settings`, `updates`), `mds_sub` (`general`, `openai` = la sezione **DeepSeek**, `studio`, `templates`, `playground`) e `mcg_preset` per gli intervalli di date predefiniti.

Parametri di query del cron letti da `controllers/front/cron.php`:

| Parametro | Usato per | Valore predefinito se assente |
|---|---|---|
| `secret` | Segreto dei prodotti o delle categorie (obbligatorio) | – |
| `action` | `generateProductContent` oppure `generateCategoryContent` (obbligatorio) | – |
| `updatedField` | Campo da scrivere | valore salvato |
| `productTarget` / `categoryTarget` | `pendingDeepSeek`, `pendingField`, `emptyField` | valore salvato |
| `productsToUpdate` / `categoriesToUpdate` | Dimensione del lotto | valore salvato |
| `languageId` | Lingua | valore salvato |
| `promptTemplateId` | Modello | valore salvato |
| `debug` | Stampa solo il piano | valore salvato |
| `categories` | Filtro delle categorie (prodotti) | valore salvato |
| `productIds` | Filtro degli id dei prodotti | valore salvato |

### 6.4 Hook

Registrati: `displayAdminProductsMainStepLeftColumnMiddle`, `displayAdminProductsMainStepLeftColumnBottom` (entrambi restituiscono una stringa vuota), `actionProductFormBuilderModifier` (termina senza output), `displayAdminProductsExtra` (il contenuto della scheda **Modules**), `displayBackOfficeHeader` (risorse, caricatore della pagina del prodotto), `displayBackOfficeTop` (collegamento della barra superiore), `dashboardZoneTwo` (blocco nella dashboard di PrestaShop), `displayHeader` e `displayFooter` (entrambi vuoti). Il modulo non espone hook propri. Non ha alcun override di `enable()` o `disable()`.

### 6.5 Override

Nessuno.

### 6.6 Database

| Tabella | Contenuto |
|---|---|
| `myaideepseek_prompt` | `id_prompt`, `status`, `title`, `prompt`, `date_generated`. 16 righe dopo l'installazione. |
| `myaideepseek_log` | Una riga per richiesta: id di prodotto, categoria, CMS, produttore, lingua e collaboratore; `type`, `method`, `status`, servizio, `model`, codice HTTP, durata, conteggi dei token, messaggio di errore, `prompt`, `reply` e i vecchi e nuovi valori di nome, descrizioni, campi meta e tag. |

La disinstallazione elimina entrambe le tabelle. Le schede vengono rimosse. Il testo di prodotti e categorie non viene toccato.

### 6.7 Chiavi e traduzioni

Tutte le chiavi hanno il prefisso `MYPRESTA_MYAIDEEPSEEK_`.

| Suffisso della chiave | Predefinito | Significato |
|---|---|---|
| `LIVE_MODE` | 0 | Live mode. |
| `DEBUG_MODE` | 0 | Debug mode. |
| `TIMEOUT` | 120 | Timeout della chiamata in secondi. |
| `PRODUCT_LOG` | 1 | Cronologia di modifica del prodotto. |
| `TOPCTA` | 1 | Collegamento della barra superiore. |
| `PRODUCT` | 1 | Generatore nella pagina del prodotto. |
| `IMAGEFINDER_ENABLE` | 1 | Interruttore della ricerca di foto. |
| `IMAGEFINDER_PROMPT` | testo inglese integrato | Istruzione della ricerca di foto. |
| `API_KEY` | vuoto | Chiave DeepSeek. |
| `MODEL` | `deepseek-chat` | Modello attivo. |
| `EXTRA_MODELS` | vuoto | Modelli aggiunti dal commerciante, uno per riga. |
| `MODEL_CAPS` | vuoto | Parametri appresi per modello durante l'esecuzione. |
| `TEMPERATURE` | 0.7 | Campionamento. |
| `MAX_TOKENS` | 3200 | Limite della risposta. |
| `TOP_P`, `FREQ_PEN`, `PRES_PEN` | 1, 0, 0 | Campionamento e penalità. |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | vuoto | Regole Studio. |
| `BUDGET` | 0 | Limite mensile, 0 = nessuno. |
| `QUALITY` | 1 | Quality gate. |
| `TOKEN` | casuale | Token dell'indirizzo AJAX. |
| `SECRET`, `CAT_SECRET` | casuale | Segreti cron di prodotti e categorie. |
| `ENABLE_CRON` | 0 | Interruttore globale del cron. |
| `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | 6 | Intervallo suggerito (Every Hour). |
| `updatedField`, `catupdatedField` | `description` | Campo del cron. |
| `productTarget`, `categoryTarget` | `pendingDeepSeek` | Regola del cron. |
| `productsToUpdate`, `categoriesToUpdate` | 5 | Lotto del cron. |
| `promptTemplateId`, `catpromptTemplateId` | vuoto | Modello del cron. |
| `languageId`, `catlanguageId` | lingua predefinita | Lingua del cron. |
| `debug`, `catdebug` | 0 | Debug del cron. |
| `productIdsList`, `categories` | vuoto | Filtri del cron. |
| `interval_select`, `IMAGEFINDER_TAB_OK` | vuoto / impostato durante l'esecuzione | Stato dell'interfaccia. |

Il modello predefinito è `deepseek-chat`. I modelli integrati sono `deepseek-chat` e `deepseek-reasoner`. La disinstallazione elimina le chiavi sopra indicate. Le chiavi dei filtri di Generate (per esempio i filtri di categoria, marchio e stato dei moduli **Generate**) non sono nell'elenco di disinstallazione e possono restare.

Traduzioni: aggiunga `translations/{iso}.php` nel formato standard di PrestaShop. I testi di aiuto dei campi sono costruiti da `fieldHelp()` nella forma What it does / How to configure / Effect e passano attraverso `$this->l()`. Alcune stringhe nella scheda del prodotto e nei template di generate sono definite nei file `.tpl` con `{l s=…}`. Alcune stringhe residue contengono ancora il vecchio nome del fornitore (vedere Problemi).

### 6.8 Estensione

La scheda del prodotto, le schermate di massa e il cron usano gli stessi segnaposto del prompt e le stesse azioni AJAX, quindi un modello personalizzato che segue `{product_name}`, `{product_brand}`, `{product_features}` e `{product_tags}` funziona ovunque. I controller front non renderizzano alcun template, quindi un tema non ha nulla da sovrascrivere. I template di amministrazione in `views/templates/hook/` possono essere sovrascritti tramite l'override standard dei template dei moduli del tema del Suo back office.

## 7. Assistenza

Pagina del modulo: https://mypresta.eu/modules/administration-tools/my-ai-deepseek.html

Per scrivere a proposito del modulo:

1. Acceda al Suo account cliente su mypresta.eu.
2. Apra la pagina dei contatti.
3. Scelga l'oggetto **Support for paid modules**. Il modulo indica che deve aver effettuato l'accesso. Dopo l'accesso, selezioni questo modulo dalla cronologia degli acquisti.
4. Descriva il problema. Aggiunga la riga di **History** (stato e messaggio) e le versioni di PrestaShop e PHP. Non invii mai la chiave API né il segreto del cron.
