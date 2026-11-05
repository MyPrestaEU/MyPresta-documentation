---
title: "My AI Grok - AI content generation - documentazione e manuale utente"
description: "Una guida per i commercianti che possiedono già il modulo: collegare il proprio account Grok (xAI), generare i testi del catalogo dal back office e risolvere i problemi quando qualcosa non funziona."
sidebar:
  label: "My AI Grok - AI content generation - documentazione e manuale utente"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo SEO meta and catalog descriptions with Grok AI su MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-grok-ai.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-grok-ai/)
>
> ---


## 1. Requisiti

Questo capitolo elenca ciò di cui il suo negozio e il suo server hanno bisogno prima che il modulo possa scrivere testi per lei.

- **PrestaShop:** versioni dalla 1.6 alla 9.x.
- **PHP:** versione 7.0 o successiva. Con un PHP più vecchio l'installazione viene rifiutata con un messaggio.
- **Estensioni PHP:** cURL. Il modulo comunica con Grok tramite cURL.
- **Connessione in uscita:** il server deve poter aprire connessioni sicure (HTTPS) verso `https://api.x.ai/v1`. Se un firewall le blocca, ogni generazione fallisce.
- **Altri moduli:** nessuno. Il modulo funziona da solo.
- **Un account xAI:** le serve un account personale su https://console.x.ai per ottenere una chiave API di Grok. Le chiamate a Grok sono fatturate da xAI al suo account, non dal modulo.
- **Cataloghi grandi:** il modulo scrive un campo di un prodotto per richiesta. Un'esecuzione di massa lunga dura quindi quanto tutte quelle richieste messe insieme. Usi i limiti di lotto delle schermate Generate e Cron e mantenga il timeout dell'API abbastanza alto per i modelli lenti (vedere la sezione 3.4).

## 2. Installazione

### 2.1 Caricare, installare e attivare

1. Nel back office apra **Modules**, poi **Module Manager**.
2. Carichi lo ZIP del modulo, oppure lo cerchi nell'elenco se è già sul server.
3. Faccia clic su **Install**. L'installazione controlla la versione di PHP, crea i dati del modulo e poi attiva il modulo.
4. Se l'installazione si interrompe con un messaggio, legga la sezione 5.1.

### 2.2 Cosa compare nel menu

- Sotto **Modules** compare una nuova voce chiamata **AI Content Generator**. Facendo clic si apre la schermata **Dashboard** del modulo.
- Tutte le altre schermate del modulo (Settings, Generate, New product, Cron, History, Images, Updates) si raggiungono dalla barra di navigazione in alto nel modulo, non dal menu di sinistra.
- Nella pagina di modifica del prodotto compare un blocco **My AI Grok** nella scheda **Modules**, e accanto ai campi di testo compaiono piccoli pulsanti **Generate with AI** (vedere la sezione 3.16).
- Nella barra superiore di ogni pagina del back office può comparire una scorciatoia a forma di bacchetta magica (vedere **Admin Top Bar CTA** nella sezione 3.4).

Può raggiungere le impostazioni anche da **Modules**, **Module Manager**, nome del modulo, **Configure**.

### 2.3 Cache

L'installazione non svuota la cache di PrestaShop. Se la voce di menu o il blocco prodotto non compaiono subito dopo l'installazione, svuoti la cache da sé in **Advanced Parameters**, **Performance** e ricarichi la pagina.

### 2.4 Disinstallazione e reinstallazione

- **Cosa scompare:** la voce di menu **AI Content Generator** e le sue schermate nascoste, i 16 modelli di prompt già pronti insieme a quelli che ha aggiunto, l'intera History (ogni prompt salvato, risposta e conteggio di token) e le impostazioni salvate del modulo (chiave API, modello, regole Studio, scelte del cron, segreti).
- **Cosa resta:** tutti i testi già scritti in prodotti e categorie. Il modulo non rimuove mai i testi generati.
- **Residui:** alcune scelte memorizzate dalle schermate Generate (filtri come l'ultima lingua o lo stato scelti) possono restare salvate nel negozio. Non hanno alcun effetto.
- **Reinstallazione:** una nuova installazione parte dai valori predefiniti elencati nel capitolo 3. La sua chiave API, le regole Studio, i modelli personalizzati e la History non vengono ripristinati, quindi annoti o esporti prima ciò che le serve.

## 3. Configurazione e lavoro nel back office

Questo è il capitolo principale. Inizia con l'intero processo di lavoro e poi descrive ogni schermata nell'ordine della barra di navigazione.

Gli screenshot provengono da un back office in inglese. In questo capitolo i nomi di pulsanti, campi e messaggi sono in grassetto così come compaiono nell'interfaccia inglese; le spiegazioni sono in italiano.

### 3.1 L'intero processo, passo dopo passo

1. **Colleghi Grok.** Apra **Settings**, poi **Grok**. Incolli la sua chiave API da https://console.x.ai e scelga un modello. Salvi.
2. **Imposti lo stile della casa (facoltativo).** Apra **Settings**, poi **Studio**. Compili voce, pubblico, tono, un glossario di nomi da mantenere, parole vietate, un budget mensile e il controllo di qualità. Lasci vuoto ciò che non le serve.
3. **Provi in sicurezza.** Usi **Settings**, poi **Playground** per inviare un'istruzione libera e leggere la risposta. Nella pagina di un prodotto usi la scheda **Simulate** e **Try**. In questi due punti non viene salvato nulla nel catalogo.
4. **Compili un prodotto.** Apra il prodotto, vada nella scheda **Modules**, **My AI Grok**, **Generate**, scelga la lingua e prema **Fill** accanto al campo. Oppure usi i pulsanti **Generate with AI** accanto ai campi del prodotto e poi salvi il prodotto.
5. **Compili molti prodotti.** Apra **Generate**, **Products**. Filtri l'elenco, prema **Go to next step**, scelga un modello o scriva un'istruzione, scelga cosa generare, come trattare il testo esistente e per quali lingue, poi prema **Run on the list below**. Faccia lo stesso per le categorie in **Generate**, **Categories**.
6. **Lotti non presidiati.** Apra **Cron**, salvi le sue scelte e copi l'indirizzo nello scheduler del suo server (vedere le sezioni 3.12 e 4.2).
7. **Verificare e annullare.** **History** mostra ogni chiamata con prompt, risposta, stato e token. In un prodotto, la scheda **History** le permette di rimettere un testo precedente con **Restore**.

Il testo generato viene scritto direttamente nel catalogo non appena arriva ogni risposta. Prima di una prima esecuzione ampia, provi su pochi prodotti con **Simulate** oppure con i filtri **Product IDs** e **Product Limit**.

### 3.2 Navigazione e pannello Help

![Dashboard with the navigation bar and date presets](https://mypresta.eu/docs/images/docs/myaigrok-dashboard.webp)

*Dashboard: la barra di navigazione si trova in alto in ogni schermata del modulo.*

La barra mostra il nome del modulo con la versione e queste voci, in quest'ordine:

| Voce | Cosa vi trova |
|---|---|
| **Dashboard** | Grafici di richieste, token ed errori. |
| **Settings** | Cinque sottoschede: **General**, **Grok**, **Studio**, **Prompt templates**, **Playground**. |
| **Generate** | Due sottoschede: **Products** e **Categories** per le esecuzioni di massa. |
| **New product** | Crea un nuovo prodotto a partire da una breve descrizione. |
| **Cron** | Costruisce indirizzi che il server può richiamare secondo una pianificazione. |
| **History** | L'elenco completo delle chiamate con filtri. |
| **Images** | Interruttore e istruzione per la ricerca delle immagini del prodotto. |
| **Updates** | Controlla se è stata pubblicata una versione più recente del modulo. |

Passi il mouse su una voce per leggere una breve spiegazione. Un pulsante rotondo **Help** sul bordo dello schermo apre un pannello laterale con l'aiuto per la pagina in cui si trova. Lo chiuda con la croce.

Ogni campo del modulo è spiegato a schermo in tre parti: **What it does**, **How to configure** ed **Effect**. Le tabelle seguenti riformulano quei testi con parole semplici e aggiungono il valore che il campo ha subito dopo l'installazione.

### 3.3 Dashboard

Apra **AI Content Generator** sotto **Modules**, oppure la voce **Dashboard** della barra.

- **Intervalli predefiniti:** **Today**, **7 days**, **30 days**, **90 days**, **This month**, **All time**. La pagina si apre su **30 days**.
- **From** e **To:** scelga le sue date e prema **Apply**. Se From è successiva a To, le date vengono invertite.
- **Active service:** mostra Grok e il modello selezionato in Settings.
- **Schede:** **Requests** (ogni chiamata salvata), **Success**, **Errors**, **Tokens sent** (dimensione dei prompt) e **Tokens received** (dimensione delle risposte).
- **Grafici:** **Requests and errors**, **Tokens sent and received** e **Requests by model**. Per intervalli più lunghi di circa quattro mesi i giorni vengono raggruppati per settimana.

| Controllo | All'installazione | Cosa fa |
|---|---|---|
| **Presets** | 30 days | Conta le generazioni di Grok salvate in History entro le date scelte. La chiave API e il modello non si scelgono qui ma in Settings. |
| **From / To / Apply** | ultimi 30 giorni | Disegna solo quella porzione. Da questa pagina non viene generato né modificato nulla nel catalogo e la History non viene cancellata. |

### 3.4 Settings – General

Apra **Settings**, poi **General**.

![Settings, General tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-general.webp)

*Settings – General: interruttori validi per tutto il negozio e timeout dell'API.*

Questi interruttori decidono cosa vedono i dipendenti nel back office. Salvare qui non modifica da solo il testo dei prodotti. Prema **Save**; la conferma riporta **Settings Updated**.

| Campo | All'installazione | Cosa fa |
|---|---|---|
| **Live mode** | Disattivato | Indica che il modulo gira sul negozio reale e non su un'installazione di prova. Lo attivi nel negozio di produzione. Lo lasci disattivato su una copia di staging se non vuole che il personale consideri gli strumenti pronti. Disattivato mantiene gli stessi strumenti ma segnala che non è l'installazione di produzione. |
| **Debug mode** | Disattivato | Scrive dettagli diagnostici aggiuntivi quando una chiamata a Grok fallisce. Lo attivi solo mentre indaga su un errore, poi lo disattivi. Attivato aggiunge messaggi tecnici al log di PrestaShop (**Advanced Parameters**, **Logs**). Disattivato limita il log alla normale cronologia delle generazioni. I clienti non lo vedono mai. |
| **API timeout (seconds)** | 120 | Quanti secondi può durare una chiamata a Grok prima che il modulo rinunci. Usi 120 per descrizioni normali. Lo alzi verso 600 per pacchetti SEO lunghi o modelli lenti. Non scenda sotto 10. I valori inferiori a 10 vengono salvati come 10 e quelli superiori a 600 come 600; un valore vuoto o non numerico viene salvato come 120. Un timeout breve fallisce subito e registra un errore. Un timeout lungo attende un modello lento invece di interrompere una buona risposta. |
| **Product Edit History** | Attivato | Mostra nella pagina del prodotto le precedenti scritture dell'IA, così da poter rimettere un valore vecchio. Lo attivi se i redattori devono poter annullare una generazione. Attivato aggiunge una scheda **History** con **Restore** al blocco del modulo nel prodotto. Disattivato la nasconde. Le righe passate restano in History in entrambi i casi. |
| **Admin Top Bar CTA** | Attivato | Inserisce nella barra superiore del back office una scorciatoia che apre il generatore. La attivi nei negozi in cui il personale genera testi spesso. La disattivi se la barra è già affollata. Attivato mostra il pulsante in ogni pagina del back office. Disattivato rimuove solo quel pulsante. Il menu del modulo resta. |
| **Product edit page Form** | Attivato | Mostra il pannello del generatore nella pagina di modifica del prodotto: le schede **Generate**, **Simulate** e **Photos** del blocco **My AI Grok**. Lo attivi per i redattori del catalogo. Lo disattivi se devono essere usati solo la generazione di massa e il cron. |
| **AI Image Finder** | Attivato | Permette a un redattore di chiedere al modello pagine che probabilmente contengono foto del prodotto corrente. Lo attivi se vuole quel pulsante nella pagina del prodotto. È sempre lei a scegliere quali immagini importare. Disattivato nasconde il contenuto della scheda **Photos**. Non viene scaricato nulla finché qualcuno non conferma un'immagine. |
| **AI Image Search Prompt** | Richiede esattamente 5 indirizzi di pagine | L'istruzione inviata quando si cercano immagini del prodotto. `{product_name}` e `{product_description}` vengono sostituiti con il prodotto corrente. Mantenga la richiesta di un elenco di indirizzi di pagine. Cambi la formulazione se vuole siti dei produttori o un numero diverso. Un prompt più preciso restituisce pagine più pertinenti. Uno vago restituisce link non correlati. Non viene salvato nulla finché non sceglie le immagini. |

Lo stesso interruttore **AI Image Finder** e lo stesso prompt esistono anche nella schermata **Images** (sezione 3.14); entrambi i punti modificano la stessa impostazione.

### 3.5 Settings – Grok

Apra **Settings**, poi **Grok**.

![Settings, Grok tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-grok.webp)

*Settings – Grok: chiave API, modello e valori di campionamento.*

Questo modulo contiene l'account Grok usato per ogni generazione, compresi il cron e i pulsanti del prodotto. I campi di campionamento modificano quanto è varia la formulazione. Non cambiano quali prodotti vengono aggiornati.

Messaggi che può vedere dopo **Save**: **OpenAi Settings Updated** (successo; la dicitura è un residuo, ma la schermata appartiene a Grok), **Grok API KEY field is invalid!** (nessuna chiave salvata e quella incollata è più corta di 10 caratteri) e **OpenAi Model field is invalid!** (il nome del modello è troppo corto). Una chiave con spazi ai lati viene ripulita automaticamente e può comparire **Grok API Key has been automatically cleaned (whitespace removed).**

| Campo | All'installazione | Cosa fa |
|---|---|---|
| **Grok API KEY** | vuoto | Il segreto che permette a questo negozio di richiamare il suo account Grok. Incolli la chiave da https://console.x.ai. Gli spazi vengono rimossi al salvataggio. Lasci il campo intatto per mantenere la chiave già salvata. Una chiave valida consente le generazioni di Grok. Una chiave vuota o errata fa fallire quelle chiamate e l'errore viene scritto in History. |
| **Model** | grok-4.7 | Il modello Grok che scrive il testo. I nomi integrati sono grok-4.7, grok-4.6, grok-4.5, grok-4.3, grok-4.20-0309-non-reasoning e grok-4.20-0309-reasoning. Restano nell'elenco. I nomi che aggiunge nella riga successiva possono essere rimossi. La generazione successiva usa quel modello. Un modello a cui la sua chiave non ha accesso restituisce un errore invece del testo. |
| **Add a Grok model** | nessun modello aggiuntivo | Aggiunge un id di modello Grok non presente nell'elenco integrato, così da poterlo selezionare sopra. Digiti l'id esatto del suo account Grok (ad esempio grok-4.6), poi faccia clic su **Add model**. Il nuovo id compare nell'elenco **Model** e diventa il modello attivo. **Remove** accanto a un id aggiunto elimina solo gli id aggiunti qui. Gli id integrati non possono essere eliminati. Se rimuove il modello attivo, diventa attivo grok-4.7. Messaggi: **Model added.**, **Model removed.**, **That model is already built in.**, **Built-in models cannot be removed.**, **Enter a model id such as grok-4.6.** |
| **Max Tokens** | 3200 | Limite superiore alla lunghezza della risposta, contata in token e non in parole. Usi circa 256 per una meta description e 1000 o più per una descrizione HTML completa. Un limite basso tronca la risposta. Uno alto consente testi più lunghi e costa di più sulla fattura del fornitore. Non modifica il prompt. |
| **Temperature** | 0.7 | Con quanta libertà il modello sceglie le parole. Più bassa è più stabile, più alta è più varia. Resti tra 0 e 1. Usi circa 0,2 per schede tecniche e testi meta, circa 0,7 per le descrizioni. Cambi questo valore oppure **Top P**, non entrambi. Un valore basso ripete una struttura simile. Un valore alto produce formulazioni più diverse e un rischio maggiore di allontanarsi dalla traccia. |
| **Top P** | 1 | Un altro modo per limitare quanto può essere sorprendente la parola successiva. 1 considera l'intero intervallo. Lasci 1 se ha già impostato **Temperature**. Usi un valore più basso, come 0,9, solo se vuole un vocabolario più ristretto. Valori più bassi rendono le risposte più sicure e più ripetitive. |
| **Frequency Penalty Value** | 0 | Riduce le righe che ripetono la stessa frase all'interno di una risposta. Usi 0 a meno che le descrizioni continuino a copiare la stessa frase. Provi da 0,3 a 0,6. Resti tra -2 e 2. Un valore positivo rende meno probabile la formulazione ripetuta. Non guarda gli altri prodotti. |
| **Presence Penalty Value** | 0 | Spinge la risposta verso argomenti nuovi invece di restare sulle parole già usate. Usi 0 per impostazione predefinita. Provi un piccolo numero positivo se ogni paragrafo tratta lo stesso punto. Resti tra -2 e 2. Alcuni modelli più recenti ignorano questo campo. |

Il modulo ricorda da solo quali di questi valori un modello rifiuta e smette di inviarglieli, quindi non vedrà un errore per questo motivo.

### 3.6 Settings – Studio

Apra **Settings**, poi **Studio**.

![Settings, Studio tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-studio.webp)

*Settings – Studio: regole della casa aggiunte a ogni prompt.*

Studio viene applicato sopra a ogni prompt, compresi i pulsanti del prodotto, la generazione di massa e il cron. I campi vuoti vengono saltati. Un budget di 0 significa nessun limite mensile. Il modulo indica inoltre al modello in quale lingua scrivere, in base alla lingua del prodotto, della categoria o della schermata in uso. Prema **Save studio**; la conferma riporta **Studio settings saved.** Il testo già salvato nel catalogo non viene riscritto.

| Campo | All'installazione | Cosa fa |
|---|---|---|
| **Brand voice** | vuoto | Dice al modello chi sta parlando, così che i testi dei prodotti corrispondano al negozio e non a un assistente generico. Scriva una breve traccia, ad esempio: officina specializzata, frasi brevi, niente toni enfatici. Ogni generazione successiva parte da questa voce. Modificarla non riscrive il testo già salvato. |
| **Audience** | vuoto | Indica il lettore a cui il modello deve rivolgersi. Usi una frase semplice come installatori professionisti o primi acquirenti. Le risposte usano vocabolario ed esempi pensati per quel lettore. |
| **Tone** | vuoto | Stabilisce il tono della formulazione: formale, caloroso, tecnico e così via. Bastano una o due parole. Lo lasci vuoto per far decidere al prompt. Non modifica il modello né la temperatura. |
| **Glossary** | vuoto | Un elenco di nomi di marchi, materiali e grafie che il modello deve copiare esattamente. Inserisca un termine per riga, nella forma che vuole mantenere. Il nuovo testo preferisce quelle grafie. I termini non elencati possono comunque essere riformulati. |
| **Forbidden words** | vuoto | Parole e frasi che non devono comparire in una risposta salvata. Una parola o frase per riga. L'elenco viene controllato solo quando il **Quality gate** è attivato. Una risposta che contiene una di queste righe viene rifiutata e non viene scritta nel prodotto. Il tentativo viene comunque salvato in History come errore. |
| **Monthly generation budget** | 0 | Limita quante generazioni riuscite il negozio può eseguire nel mese di calendario in corso. Inserisca un numero intero. Usi 0 per nessun limite. Il contatore riparte il primo giorno del mese. Una volta raggiunto il limite, le nuove generazioni si fermano con un messaggio di budget fino al mese successivo. Le chiamate fallite non vengono contate. I numeri negativi vengono salvati come 0. |
| **Quality gate** | Attivato | Controlla la risposta del modello rispetto all'elenco dei vietati prima che venga salvato qualsiasi cosa. Lo attivi dopo aver compilato **Forbidden words**. Lo disattivi se vuole solo conservare l'elenco per dopo. Attivato blocca una risposta che corrisponde. Disattivato salva la risposta anche se contiene una parola dell'elenco. |

Il budget conta le righe di History, quindi usare **Clear list** nella schermata History fa ripartire da zero il conteggio del mese.

### 3.7 Settings – Prompt templates

Apra **Settings**, poi **Prompt templates**.

![Settings, Prompt templates tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-templates.webp)

*Settings – Prompt templates: l'elenco delle istruzioni salvate.*

Un modello è un'istruzione salvata. I redattori lo scelgono invece di digitare di nuovo la stessa traccia. I segnaposto (placeholders) vengono sostituiti con il prodotto o la categoria per cui genera. Il negozio parte con 16 modelli già pronti per nomi di prodotto, descrizioni, meta title, meta description e tag, tutti attivati.

**L'elenco** mostra **ID**, **Title**, **Prompt**, **Status** (faccia clic sul segno di spunta o sulla croce per attivare o disattivare un modello) e **Timestamp**. Ogni riga ha **Edit** e **Delete**. Selezioni più righe e usi l'azione di gruppo **Delete** (le viene chiesto: **Are you sure you want to delete the selected prompts?**). Il pulsante **Add new** sopra l'elenco crea un modello.

**Il modulo** (**Generate Prompt Template**) ha tre campi. Prema **Save Prompt**, oppure **Go Back to Module Settings** per uscire senza salvare. Messaggi: **Prompt template successfully added!**, **Prompt template successfully updated!**, **Prompt template removed.** Le virgolette doppie digitate nel prompt vengono salvate come virgolette semplici.

| Campo | All'installazione | Cosa fa |
|---|---|---|
| **Status** | Disattivato per un nuovo modello | Mostra o nasconde questo modello nei menu a tendina usati nella pagina del prodotto, nella generazione di massa e nel cron. Attivi i modelli che il personale deve usare. Disattivi una bozza invece di eliminarla. I modelli attivati compaiono negli elenchi. Quelli disattivati restano in questa tabella ma non vengono proposti. |
| **Prompt title** | vuoto (obbligatorio) | Il nome che i redattori vedono nel menu dei modelli. Non viene inviato al modello. Usi un'etichetta breve come HTML description with features. |
| **Prompt content** | vuoto (obbligatorio) | L'istruzione inviata al modello. Scriva la traccia come la direbbe a un copywriter e menzioni lunghezza, HTML e lingua se contano. Quando qualcuno esegue il modello, i segnaposto vengono compilati dall'elemento corrente e la risposta viene scritta nel campo che ha scelto. |

**Segnaposto** (placeholders) che può digitare in un prompt (vengono compilati per ogni prodotto, categoria o pagina quando il modello viene eseguito):

| Segnaposto | Sostituito con |
|---|---|
| `{product_name}` `{product_description}` `{product_description_short}` `{product_tags}` `{product_reference}` `{product_ean13}` `{product_weight}` | I dati propri del prodotto nella lingua in cui si scrive. |
| `{product_brand}` `{product_default_category}` `{product_category_description}` `{product_categories}` | Il marchio del prodotto, il nome e la descrizione della sua categoria predefinita e i nomi di tutte le sue categorie. |
| `{product_attributes}` `{product_features}` `{product_feature_values}` `{product_images}` | Gli attributi di combinazione del prodotto, i nomi delle caratteristiche, le coppie nome e valore delle caratteristiche e i link alle sue immagini. |
| `{category_name}` `{category_description}` `{category_parent_name}` | La categoria che si sta scrivendo e il nome della sua categoria genitore. |
| `{cms_title}` `{brand_name}` `{brand_description}` `{brand_short_description}` | I dati della pagina di contenuto o del marchio aperti quando usa la scorciatoia della barra superiore. |
| `{shop_name}` `{shop_url}` `{shop_language}` `{shop_country}` `{shop_currency}` | I dati dell'intero negozio: nome, dominio, lingua, paese predefinito e codice della valuta predefinita. |

Usi solo i segnaposto che hanno senso dove il modello verrà eseguito. Un segnaposto di prodotto in una traccia per una categoria resta come testo digitato.

### 3.8 Settings – Playground

Apra **Settings**, poi **Playground**.

![Settings, Playground tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-playground.webp)

*Settings – Playground: un blocco appunti per un'istruzione libera.*

Il Playground invia un'istruzione libera al modello attivo e stampa la risposta sotto il pulsante. Può menzionare il nome del negozio, l'URL del negozio, il nome di un prodotto, un riferimento o le caratteristiche del prodotto affinché il modulo sostituisca i dati del catalogo. La risposta resta in questa pagina. Non viene salvato alcun campo di prodotto o categoria.

| Campo | All'installazione | Cosa fa |
|---|---|---|
| **Instruction box** | vuoto | Digiti l'istruzione in linguaggio semplice e prema **Generate**. Il fornitore attivo riceve questo testo insieme alle regole Studio. La risposta compare sotto il pulsante con il numero di token usati. Il catalogo non viene aggiornato. |

Se preme **Generate** con la casella vuota vede **Write a prompt first.** Ogni chiamata viene salvata in History con il tipo **general**.

### 3.9 Generate – Products

Apra **Generate**, poi **Products**. Può anche fare clic sul pulsante **My AI Grok** che compare accanto alle azioni di gruppo nell'elenco dei prodotti.

La generazione di massa ha due passaggi: un filtro che costruisce un elenco e un'esecuzione su quell'elenco.

**Passaggio 1: Filter products to update.** Questo passaggio si limita a costruire l'elenco dei prodotti. Non viene scritto nulla nei prodotti finché nella schermata successiva non sceglie un ambito e le lingue e non preme **Run**. Questi filtri non vengono salvati come impostazioni del negozio. Prema **Go to next step** quando è pronto. Lasci vuoto un filtro per ignorarlo.

| Campo | All'installazione | Cosa fa |
|---|---|---|
| **Product Categories** | nessuna selezionata | Limita l'elenco dei prodotti a quelli che si trovano nelle categorie selezionate (o che hanno una di esse come categoria predefinita). Selezioni le categorie desiderate. Lasci l'albero vuoto se la categoria non deve contare. |
| **Brand** | Select brand (no filter) | Mantiene i prodotti di un produttore. Scelga un marchio, oppure lasci la prima opzione vuota se devono essere inclusi tutti i marchi. |
| **Product status** | Active | Mantiene i prodotti in vendita, disattivati o entrambi. Scelga **Active** per il catalogo online, **Disabled** per le bozze o **Both**. |
| **Product stock** | All products | Esclude facoltativamente i prodotti esauriti. **Only in stock products** toglie dall'elenco i prodotti senza quantità disponibile. **All products** lascia la disponibilità fuori dal filtro. |
| **Update only** | Update all | Usa la cronologia delle generazioni per includere i prodotti mai scritti da questo modulo (**Products that have not been updated with OpenAi content**), solo quelli che lo sono stati (**Products that already have been updated with OpenAi content**), oppure ogni prodotto (**Update all**). Scelga «non ancora aggiornati» per un primo passaggio e «già aggiornati» quando vuole riscrivere. Un prodotto conta come già aggiornato quando History contiene una qualsiasi voce per esso, anche un tentativo fallito. |
| **Product IDs** | vuoto | Restringe l'elenco a id di prodotto specifici. Digiti gli id separati da virgole, ad esempio 12,45,103. |
| **Product Reference** | vuoto | Restringe l'elenco a codici di riferimento specifici. Digiti uno o più riferimenti separati da virgole. |
| **Product Add Date From** | vuoto | La data di creazione più remota che un prodotto può avere per essere incluso. I prodotti creati prima di quel momento vengono esclusi. |
| **Product Add Date To** | vuoto | La data di creazione più recente che un prodotto può avere per essere incluso. I prodotti creati dopo quel momento vengono esclusi. |
| **Minimum product ID** | vuoto | L'id di prodotto più piccolo che può comparire nell'elenco. Digiti un numero intero. |
| **Maximum product ID** | vuoto | L'id di prodotto più grande che può comparire nell'elenco. Digiti un numero intero. |
| **Product Limit** | vuoto (nessun limite) | Limita quanti prodotti vengono caricati nell'elenco di generazione. Usi un numero piccolo, come 20, su un catalogo grande. La schermata successiva non ne mostra mai di più, così un'esecuzione non può percorrere per errore l'intero catalogo. |

**Passaggio 2: Mass product generation.** La schermata successiva mostra una tabella dei prodotti corrispondenti (**ID**, **Reference**, **Result**) con i controlli di esecuzione sopra.

![Mass product generation with the filtered list](https://mypresta.eu/docs/images/docs/myaigrok-generate-products.webp)

*Generate – Products: modello, ambito, testo esistente, lingue e l'elenco su cui si esegue.*

Scrive i prodotti filtrati uno per uno con il modello attivo. Ogni prodotto nella tabella viene aggiornato nelle lingue selezionate. I prodotti che non erano nel filtro non vengono toccati. Una riga mostra il suo risultato non appena quel prodotto è terminato.

| Campo | All'installazione | Cosa fa |
|---|---|---|
| **Template** | **Choose a template** (nessuno) | Compila la casella del prompt da un modello salvato in Settings. Scelga un titolo, oppure lasci la prima opzione e digiti il suo prompt nella casella sottostante. Il modello riceve il testo della casella con i segnaposto del prodotto sostituiti per ogni riga. Il titolo in sé non viene inviato. Se la casella resta vuota viene usata una breve traccia già pronta per ciascun campo. |
| **What to generate** | Descriptions | **Descriptions** scrive la descrizione lunga e quella breve. **Meta title and meta description** scrive entrambi i campi meta. **Descriptions and meta together** scrive tutti e quattro. I campi al di fuori di questa scelta restano come sono. Ogni campo ha la propria richiesta. |
| **Existing text** | Replace | **Replace** sovrascrive il campo. **Skip if filled** lascia in pace un campo compilato e non chiama il modello per esso. **Add above** e **Add below** conservano il vecchio testo e aggiungono il nuovo prima o dopo. Replace cambia il valore salvato. Skip protegge i campi compilati. Add mantiene entrambe le versioni nello stesso campo. |
| **Languages** | è selezionata la lingua della sua sessione di back office | Selezioni ogni lingua da scrivere. Deselezioni una lingua per lasciarla intatta. Ogni lingua selezionata viene generata separatamente. Le lingue non selezionate mantengono il testo attuale. |
| **Run on the list below** | – | Avvia l'esecuzione. Una riga di stato mostra l'avanzamento (ad esempio 3 / 24 seguito dal nome del campo) e termina con **Finished N products.** Se non è selezionata alcuna lingua vede **Select at least one language.** |

Ogni riga nella colonna **Result** riporta una riga per campo e lingua, ad esempio il nome del campo seguito da **success**, **skipped** o **error** e da un breve messaggio. **skipped** con **Product skipped.** significa che il campo aveva già del testo ed era stato scelto **Skip if filled**. Le righe **error** riportano il motivo; lo stesso errore viene salvato in History.

Tenga aperta questa scheda del browser finché l'esecuzione non indica **Finished**. L'esecuzione è guidata dalla pagina: invia una richiesta alla volta e chiudere o ricaricare la scheda la interrompe. I prodotti già terminati restano scritti. Un testo molto lungo viene accorciato per rispettare i limiti di PrestaShop: nomi a 128 caratteri, descrizioni brevi a 800, meta title a 69 e meta description a 159.

### 3.10 Generate – Categories

Apra **Generate**, poi **Categories**. Funziona come la schermata dei prodotti con meno filtri.

**Passaggio 1: Filter categories to update.** Questo passaggio si limita a costruire l'elenco delle categorie. Non viene inviato nulla al modello finché nella schermata successiva non scrive un prompt e avvia l'esecuzione. I filtri qui non vengono salvati come impostazioni del negozio. Prema **Go to next step**.

| Campo | All'installazione | Cosa fa |
|---|---|---|
| **Categories** | nessuna selezionata | Sceglie le categorie che compariranno nell'elenco del passaggio successivo. Selezioni una o più categorie. Lasci l'albero vuoto per includere ogni categoria che corrisponde allo stato sottostante. |
| **Category status** | Active | Mantiene le categorie attive, disattivate o entrambe (**Active**, **Disabled**, **Both**). Il passaggio successivo elenca solo le categorie con quello stato. |

**Passaggio 2: Mass category generation.**

![Mass category generation](https://mypresta.eu/docs/images/docs/myaigrok-generate-categories.webp)

*Generate – Categories: l'istruzione, il campo, il testo esistente, la lingua e l'elenco delle categorie.*

Scrive un campo per ogni categoria dell'elenco filtrato. Ogni categoria elencata viene aggiornata in quella lingua. Gli altri campi e le altre lingue restano come sono.

| Campo | All'installazione | Cosa fa |
|---|---|---|
| **Instruction box** (sopra l'elenco dei campi) | vuoto | L'istruzione inviata per ogni categoria. Descriva tono, lunghezza e HTML. Usi `{category_name}` quando vuole il nome della categoria nella traccia. Ogni categoria viene generata da questo stesso testo. Se lasciata vuota viene usata una breve traccia già pronta. |
| **Field selector** | Description | Il campo della categoria che questa esecuzione scrive: **Description**, **Name**, **Meta title**, **Meta description** o **Additional description**. Viene salvato solo quel campo. Gli altri campi della categoria restano come sono. Se il suo PrestaShop non ha il campo Additional description per le categorie vede **Error! This PrestaShop version does not support the category Additional Description field.** |
| **Existing text selector** | Replace | **Replace** sovrascrive il campo. **Skip if filled** lo lascia e non chiama il modello per quella categoria. |
| **Language selector** | la lingua del suo back office | La versione linguistica che verrà scritta. Scelga una lingua. Esegua di nuovo per un'altra lingua. Cambia solo quella lingua. |
| **Run on the categories below** | – | Avvia l'esecuzione. I risultati compaiono per riga, come nella schermata dei prodotti. |

Sotto l'elenco la schermata mostra anche un secondo modulo chiamato **Generate category content**. Per generare usi il pulsante **Run on the categories below** sopra di esso. Quel secondo modulo si limita a ricordare le sue scelte e la riporta al filtro delle categorie (vedere la sezione 5.12).

### 3.11 New product

Apra **New product**. Questa schermata trasforma una breve descrizione in una bozza di prodotto e può inserire quella bozza nel catalogo.

![New product screen](https://mypresta.eu/docs/images/docs/myaigrok-new-product.webp)

*New product: descrizione, pagina sorgente facoltativa, lingua e categoria predefinita.*

**Generate data** mostra la bozza e non salva un prodotto. **Create product** aggiunge un prodotto attivo in quella lingua e categoria, copia dalla bozza nome, descrizioni, meta, tag, caratteristiche, prezzo e riferimento, gli assegna una disponibilità iniziale di 100 pezzi e lo colloca nella categoria scelta.

| Campo | All'installazione | Cosa fa |
|---|---|---|
| **What is the product?** | vuoto | La traccia che il modello sviluppa in un nome, descrizioni, meta, tag, caratteristiche, riferimento e prezzo. Descriva il prodotto in poche frasi. Menzioni materiali, pubblico e nomi da mantenere. Una traccia più ricca produce una bozza più aderente. Una casella vuota viene rifiutata con **Prompt is required**. |
| **Optional source URL** | vuoto | Aggiunge alla traccia il testo letto da una pagina pubblica, così che la bozza possa seguire una pagina prodotto esistente. Incolli un indirizzo web completo, oppure lasci vuoto. Una pagina leggibile viene aggiunta come contesto supplementare. Una pagina che il negozio non riesce a leggere viene ignorata e si usa la sola traccia. |
| **Language** | la lingua predefinita del negozio | La lingua del negozio in cui viene salvato il testo del nuovo prodotto. Le altre lingue non vengono compilate da questa schermata. Nome, descrizioni, meta e tag vengono salvati solo in quella lingua. |
| **Default category ID** | 2 | L'id di categoria assegnato come categoria predefinita del prodotto. Digiti l'id numerico da **Catalog**, **Categories**. 2 di solito è Home. Il nuovo prodotto viene collocato in quella categoria. |
| **Generate data** | – | Chiede la bozza al modello e la stampa come testo strutturato sotto i pulsanti. Se la risposta non può essere letta vede **Failed to parse AI response. Please try again.** |
| **Create product** | – | Inserisce la bozza. In caso di successo la casella mostra **Product #** seguito dall'id del nuovo prodotto. Premerlo prima di generare mostra **Generate the product first.** |

Il prodotto viene creato senza foto, con la prima regola fiscale del negozio e un prezzo preso dalla bozza; lo apra poi per controllare prezzo, imposta, foto e disponibilità. Se non è salvata alcuna chiave API la schermata mostra **Add an API key in the module settings first.**

### 3.12 Cron

Apra **Cron**. Questa schermata costruisce indirizzi che il suo server richiama secondo una pianificazione per compilare campi di prodotti o categorie in piccoli lotti. Nulla viene eseguito da solo. Il negozio non fa nulla finché il server non richiede l'indirizzo.

![Cron screen](https://mypresta.eu/docs/images/docs/myaigrok-cron.webp)

*Cron: il pannello dell'indirizzo delle categorie, poi il modulo dei prodotti con il suo indirizzo e gli interruttori.*

**Cosa contiene la schermata, dall'alto in basso:** un pannello **Category cron** con l'indirizzo delle categorie; il modulo **CRON JOB Settings – Generate product content using Grok**; il modulo **CRON JOB Settings - Generate category content using Grok**; e un pannello **Cron parameters** con l'indirizzo dei prodotti, il campo scelto, la destinazione e la dimensione del lotto.

**Importante:** gli indirizzi mostrati in questa schermata terminano al segreto. Perché la chiamata faccia qualcosa deve aggiungere l'azione all'indirizzo. Le forme complete dell'indirizzo sono nella sezione 4.2. Inoltre **Enable Cron Feature** deve essere su **Yes**, altrimenti ogni chiamata cron, per prodotti e per categorie, risponde che la funzione è disattivata.

**Modulo dei prodotti** (prema **Save** in fondo al modulo):

| Campo | All'installazione | Cosa fa |
|---|---|---|
| **Enable Cron Feature** | No | Consente al server di generare testo secondo una pianificazione, senza che un dipendente faccia clic nel catalogo. Lo attivi solo dopo aver salvato il segreto, il campo, la lingua e il prompt qui sotto. Il server deve comunque richiamare l'indirizzo. Attivato fa lavorare l'indirizzo salvato. Questo interruttore condiziona anche l'indirizzo delle categorie. |
| **Cron Job Secret Token** | un lungo valore casuale creato all'installazione | Una lunga password che deve essere presente nell'indirizzo dei prodotti. Senza di essa il negozio rifiuta la chiamata. Mantenga il valore generato. Se lo sostituisce, copi il nuovo indirizzo nello scheduler del server. Chi non conosce questo segreto non può eseguire il cron dei prodotti. Cambiarlo invalida subito il vecchio indirizzo. Usi almeno 24 caratteri (vedere la sezione 5.10). |
| **Update Field** | description | L'unico campo del prodotto che questo comando cron riscrive: **name**, **description**, **description_short**, **meta_title**, **meta_description** o **tags**. Per compilare descrizione e meta, crei due comandi cron con due campi diversi. Ogni esecuzione scrive solo quel campo nella lingua scelta sotto. |
| **Selected Products** | pendingGrok | Decide quali prodotti sono ancora in attesa. **pendingGrok** prende i prodotti mai scritti con successo da questo modulo in alcun campo. **pendingField** prende i prodotti non ancora scritti per questo specifico campo, così può eseguire più cron job (ad esempio descrizione e nome) sugli stessi prodotti. **emptyField** prende solo i prodotti in cui il campo scelto è vuoto nella lingua scelta. Ogni esecuzione salta i prodotti che non corrispondono più, quindi un catalogo completato smette di cambiare. I precedenti tentativi falliti non contano come scritti e vengono ritentati. |
| **Product Categories** | nessuna selezionata | Limita il cron ai prodotti che si trovano nelle categorie selezionate. Selezioni una o più categorie. Lasci l'albero vuoto per ignorare la categoria e usare solo gli altri filtri. Veda la sezione 5.10 prima di selezionare categorie. |
| **Product ID list** | vuoto | Restringe l'esecuzione a un elenco esplicito di id di prodotto. Digiti gli id separati da virgole, ad esempio 12,45,103. Lettere e altri caratteri vengono scartati al salvataggio. Solo quei prodotti possono essere aggiornati da questo comando. |
| **Language** | la lingua predefinita del negozio al momento dell'installazione | La versione linguistica del campo del prodotto che questo cron scrive. Scelga una lingua del negozio. Le altre lingue richiedono un proprio comando cron. |
| **Product to update** | 5 products | Quanti prodotti corrispondenti vengono elaborati a ogni chiamata dell'indirizzo (da 2 a 1000). Parta con 5 o 10 perché un modello lento non raggiunga il limite di tempo del server. Lo alzi quando un'esecuzione termina senza problemi. |
| **Prompt Template** | nessuno selezionato | L'istruzione salvata inviata al modello per ogni prodotto di questa esecuzione. Scelga un modello attivato da Settings. I segnaposto di quel modello vengono compilati per prodotto. Scelga un modello prima della prima chiamata. Cambiare il modello in seguito influisce solo sull'esecuzione successiva. |
| **Enable Debug** | No | Mostra cosa farebbe il cron quando apre l'indirizzo in un browser, senza salvare i prodotti. Lo attivi mentre controlla il comando. Lo disattivi prima che lo scheduler del server usi lo stesso indirizzo. Attivato stampa il piano e non scrive testo nel catalogo. |
| **CRON JOB interval** | Every Hour | Il ritmo che intende usare sul server (da **Every 1 Minute** a **Every 6 Hours**). Lo faccia corrispondere allo scheduler che creerà. Il modulo non avvia lo scheduler da sé e non impone questo valore. |
| **Product Cron Job command** | – | Mostra l'indirizzo base. Lo copi, aggiunga l'azione come descritto nella sezione 4.2 e incolli il risultato nello scheduler del suo server. Può creare tutti i comandi cron che desidera. |

**Il modulo delle categorie** ha la stessa logica con il proprio segreto e il proprio lotto:

| Campo | All'installazione | Cosa fa |
|---|---|---|
| **Cron Job Secret Token** | un lungo valore casuale creato all'installazione | Una lunga password che deve essere presente nell'indirizzo delle categorie. È separata dal segreto dei prodotti. Mantenga il valore generato. Le chiamate senza questo segreto vengono rifiutate. Cambiarlo invalida subito il vecchio indirizzo delle categorie. |
| **Update Field** | description | L'unico campo della categoria che questo comando riscrive: **name**, **description**, **meta_title** o **meta_description**. Nome, descrizione e meta richiedono ciascuno un proprio comando se vuole compilarli tutti. |
| **Selected categories** | pendingGrok | Le stesse tre scelte dei prodotti (**pendingGrok**, **pendingField**, **emptyField**), applicate alle categorie. Ogni esecuzione salta le categorie che non corrispondono più. |
| **Language** | la lingua predefinita del negozio al momento dell'installazione | La versione linguistica del campo della categoria che questo cron scrive. Le altre lingue richiedono un proprio comando. |
| **Categories to update** | 5 categories | Quante categorie corrispondenti vengono elaborate a ogni chiamata dell'indirizzo. Parta con 5 o 10. |
| **Prompt Template** | nessuno selezionato | L'istruzione salvata inviata al modello per ogni categoria di questa esecuzione. Scriva la traccia per una categoria, non per un prodotto (ad esempio con `{category_name}`). |
| **Enable Debug** | No | Mostra cosa farebbe il cron delle categorie quando apre l'indirizzo in un browser, senza salvare le categorie. Lo disattivi prima che lo scheduler usi l'indirizzo. |
| **CRON JOB interval** | Every Hour | Il ritmo che intende usare sul server. È solo un promemoria. |
| **Category Cron Job command** | – | Mostra l'indirizzo base da copiare. Aggiunga l'azione come descritto nella sezione 4.2. |

Il cron delle categorie non tocca mai la categoria radice (home) stessa.

### 3.13 History

Apra **History**. Questa schermata è un rapporto di ogni chiamata a Grok e funge da traccia di verifica.

![History screen](https://mypresta.eu/docs/images/docs/myaigrok-history.webp)

*History: filtri, totali, tabelle di dettaglio e l'elenco delle chiamate.*

Restringa le schede, le tabelle di dettaglio e l'elenco della cronologia a una porzione di generazioni. Faccia clic su un intervallo predefinito oppure imposti **From** e **To**. Poi, se vuole, limiti per modello, tipo, stato, lingua, dipendente, un id di prodotto o categoria, oppure una parola che deve comparire nel prompt o nella risposta. Prema **Filter**. Restano visibili solo le righe corrispondenti. La cronologia salvata non viene cancellata e nessun prodotto viene modificato.

| Controllo | All'installazione | Cosa fa |
|---|---|---|
| **Date presets** | This month | **Today**, **7 days**, **30 days**, **This month**, **All time**. |
| **From / To** | dal primo giorno del mese a oggi | Un intervallo di date personalizzato. |
| **Model** | Any | Solo le chiamate fatte con quel modello. |
| **Type** | Any | Solo quel tipo di chiamata (vedere la tabella sotto). |
| **Status** | Any | **Success** o **Error**. |
| **Language** | Any | Solo le chiamate per quella lingua. |
| **Employee** | Any | Solo le chiamate avviate da quel dipendente. Le chiamate avviate dal cron non hanno dipendente. |
| **Product / category ID** | vuoto | Solo le righe per quell'id (un prodotto, una categoria, una pagina di contenuto o un marchio con quel numero). |
| **Prompt or reply contains** | vuoto | Solo le righe in cui il prompt, la risposta o il testo dell'errore contengono la parola. |
| **Filter** | – | Applica i filtri. |

**Schede:** **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total** e **Average time**. Un trattino significa che Grok non ha restituito un conteggio di token per quella chiamata.

**Tabelle di dettaglio:** **By day**, **By model**, **By type**, **By language**, **By employee**, ciascuna con **Group**, **Calls**, **Sent**, **Received** e **Total**. Un piccolo numero accanto a Calls è il numero di errori in quel gruppo.

**L'elenco** ha il titolo **Prompt history** e mostra 50 righe per pagina con le colonne **ID**, **Status** (un badge verde **Success** o rosso **Error**), **Prompt**, **Reply / Error**, **Provider** (servizio, modello e tempo impiegato, più un codice di stato di Grok quando c'è), **Sent**, **Received**, **Total**, **Entity ID**, **Type** e **Timestamp**. L'azione di riga **View** apre il prompt e la risposta completi con i token, e **Back to the list** torna indietro. Se nel frattempo la riga è stata eliminata vede **This log entry no longer exists.**

| Valore del tipo | Significato |
|---|---|
| **general** | Un'istruzione libera dal Playground o dalla scorciatoia della barra superiore. |
| **singleCategory**, **singleCMS**, **singleBrand** | La scorciatoia della barra superiore è stata usata mentre era aperta una categoria, una pagina di contenuto o un marchio. |
| **product_name**, **product_description**, **product_description_short**, **product_meta_title**, **product_meta_description**, **product_tags** | Un campo del prodotto è stato scritto (o tentato) da un pulsante, da un'esecuzione di massa o dal cron. |
| **product_seo_pack** | Il pacchetto SEO ha scritto nome, descrizioni e meta in un colpo solo. |
| **category_name**, **category_description**, **category_meta_title**, **category_meta_description**, **category_additional_description** | È stato scritto un campo della categoria. |
| **error** | Una chiamata prodotto fallita. |

Il pulsante della barra degli strumenti **Clear list** elimina definitivamente ogni riga della History e lo conferma con **Log list successfully deleted.** Rimuove anche i punti di ripristino nelle pagine dei prodotti e azzera il conteggio del budget mensile, quindi lo usi con cautela.

### 3.14 Images

Apra **Images**. Questa schermata attiva o disattiva la ricerca di immagini nella pagina del prodotto e memorizza l'istruzione inviata al modello.

![Images screen](https://mypresta.eu/docs/images/docs/myaigrok-images.webp)

*Images: l'interruttore AI Image Finder e il suo prompt.*

Questi due campi controllano la ricerca di immagini nella pagina del prodotto. Salvarli non scarica immagini e non modifica il testo dei prodotti. Prema **Save**; la conferma riporta **Settings saved.**

| Campo | All'installazione | Cosa fa |
|---|---|---|
| **AI Image Finder** | Attivato | Mostra o nasconde la ricerca di immagini nella pagina di modifica del prodotto. Lo attivi quando i redattori devono cercare foto del prodotto corrente. Lo disattivi per rimuovere quel pulsante. Attivato mostra la ricerca. Disattivato la nasconde. Un'immagine viene importata solo dopo che qualcuno la conferma. |
| **AI Image Search Prompt** | Richiede esattamente 5 indirizzi di pagine | L'istruzione inviata quando si cercano immagini del prodotto. I segnaposto del nome e della descrizione del prodotto vengono sostituiti con il prodotto corrente. Mantenga la richiesta di un elenco di indirizzi di pagine (la schermata lo chiama un array JSON di URL di pagine). Cambi la formulazione se vuole siti dei produttori o un numero diverso di link. Un prompt più preciso restituisce pagine più pertinenti. Uno vago restituisce link non correlati. Non viene salvato nulla finché un redattore non sceglie un'immagine. |

### 3.15 Updates

Apra **Updates** (all'estrema destra della barra).

![Updates screen](https://mypresta.eu/docs/images/docs/myaigrok-updates.webp)

*Updates: controllo manuale, notifiche automatiche e link alla pagina del prodotto.*

La schermata ha il titolo **MyPresta Updates**. Controlla su MyPresta.eu se esiste una versione più recente del modulo e può avvisarla nel back office. Il catalogo e i testi generati restano come sono.

| Campo | All'installazione | Cosa fa |
|---|---|---|
| **Manual Check** | – | Contatta una volta i server di aggiornamento di MyPresta.eu e confronta la versione remota con quella di questo negozio. Faccia clic su **Check Now** dopo l'installazione o quando sospetta una nuova versione. Accanto al pulsante compare **Module is up to date!** oppure **New version available!**. |
| **Automatic Notifications** | Attivato | Controlla periodicamente (circa ogni 3 giorni) la presenza di aggiornamenti nel back office. Imposti **Enabled** per ricevere un banner di avviso quando esiste una versione più recente. I dipendenti vedono allora una notifica con un link per maggiori dettagli. Imposti **Disabled** se gestisce gli aggiornamenti solo a mano. Salvi con **Save**; la conferma è **Update settings saved.** |
| **Product Page** | link | Apre in una nuova scheda la pagina prodotto ufficiale di MyPresta per questo modulo. |

### 3.16 Lavorare nella pagina di modifica del prodotto

Apra un prodotto (**Catalog**, **Products**, il prodotto), poi la scheda **Modules**, poi **My AI Grok**. Il blocco ha fino a quattro schede: **Generate**, **Simulate**, **Photos** e **History**. Le schede che vede dipendono da **Product edit page Form** e **Product Edit History** nella sezione 3.4. Il prodotto deve essere stato salvato almeno una volta.

![My AI Grok block on the product edit page](https://mypresta.eu/docs/images/docs/myaigrok-product-edit.webp)

*Pagina di modifica del prodotto, scheda Generate: chip delle lingue, comportamento del testo esistente e una scheda per campo.*

**Scheda Generate.** Ogni pulsante scrive un campo del prodotto e il testo viene salvato subito nel prodotto.

- **Language:** un chip per ogni lingua attiva, più **Every language**, che esegue ogni lingua una dopo l'altra.
- **If the field already has text:** **Replace**, **Add above**, **Add below** o **Skip if filled**. Si comportano come descritto nella sezione 3.9.
- **Schede dei campi:** **Description** (testo lungo con una breve introduzione e un elenco di caratteristiche), **Short description** (un breve riassunto semplice, sotto i 400 caratteri circa), **Name**, **Meta title** (circa 70 caratteri), **Meta description** (circa 160 caratteri) e **Tags** (un elenco separato da virgole). Prema **Fill** sulla scheda.
- **SEO pack:** **Fill all** compila nome, entrambe le descrizioni ed entrambi i campi meta in una sola richiesta. È disponibile solo nella scheda Generate. Poi aggiorni la pagina del prodotto per vedere i nuovi valori.
- **Use your own instruction or a saved prompt:** apra questa sezione per filtrare i suoi modelli salvati per titolo o testo, sceglierne uno (la prima tessera **Standard brief** usa una traccia già pronta per il campo che preme) oppure digitare il suo testo in **Instruction**. Lasci vuoto per usare la traccia standard. Se nessun modello corrisponde al filtro vede **No prompt matches that filter.**
- Il risultato viene stampato anche in un pannello sotto le schede, con il numero di token.

Dopo un **Fill**, ricarichi la pagina del prodotto per vedere il nuovo testo nel modulo.

**Scheda Simulate.** Provi prima un campo. La risposta resta in questa pagina e il prodotto non viene modificato. Ha gli stessi chip delle lingue e le stesse schede dei campi, ma ogni scheda ha **Try** al posto di **Fill**. Ogni Try crea comunque una riga in History.

![Simulate tab on the product edit page](https://mypresta.eu/docs/images/docs/myaigrok-product-simulate.webp)

*Scheda Simulate: **Try** mostra la risposta senza salvare.*

**Scheda Photos.** Quando **AI Image Finder** è attivato, Grok cerca foto di questo prodotto.

![Photos tab on the product edit page](https://mypresta.eu/docs/images/docs/myaigrok-product-photos.webp)

*Scheda Photos: trovare pagine, selezionare foto, aggiungerle al prodotto.*

1. Prema **Find pages**. Grok suggerisce pagine web e il modulo legge le foto da un massimo di cinque di esse (fino a 24 foto).
2. Selezioni le foto che desidera.
3. Prema **Add selected to this product**. Le foto vengono scaricate e collegate; la prima foto che ha selezionato diventa la copertina. Prima di questo passaggio non viene salvato nulla.

Gli indirizzi di reti private non vengono mai aperti. Se il cercatore è disattivato, la scheda indica che deve attivare **AI Image Finder** in Settings, General, e riaprire il prodotto.

**Scheda History.** Elenca le scritture precedenti per questo prodotto con **When**, **Type**, **Status** e un pulsante **Restore**. **Restore** chiede **Restore the previous value?** e, una volta confermato, rimette il testo precedente e le dice di aggiornare la pagina. La History dell'intero negozio non viene cancellata. **Restore** viene offerto solo per le righe riuscite che hanno memorizzato un valore precedente. La scheda mostra **No generations for this product yet.** quando l'elenco è vuoto.

![History tab on the product edit page](https://mypresta.eu/docs/images/docs/myaigrok-product-history.webp)

*Scheda History: scritture precedenti con un pulsante Restore.*

### 3.17 Altri punti in cui compare il modulo

- **Pulsanti Generate with AI accanto ai campi.** Nel modulo di modifica del prodotto compare un piccolo pulsante accanto a descrizione, descrizione breve, meta title e meta description di ogni lingua. Nel modulo di modifica della categoria compare accanto a descrizione, descrizione aggiuntiva, meta title e meta description. Ci faccia clic. Se il negozio ha più di una lingua le viene chiesto di scegliere **Current language**, **All languages** o **Cancel**. Il testo viene inserito nel campo del modulo. Salvi il prodotto o la categoria per conservarlo. Viene usata una traccia già pronta per quel campo e le sue regole Studio continuano ad applicarsi. Se l'elemento non è mai stato salvato vede **Save the product once before generating.** (o **Save the category once before generating.**). L'interruttore **Product edit page Form** nasconde solo il blocco del modulo nella scheda **Modules**; non rimuove questi piccoli pulsanti.
- **Scorciatoia della barra superiore.** Con **Admin Top Bar CTA** attivato, un'icona a bacchetta magica nella barra superiore apre una piccola finestra: scelga un **Template** (facoltativo), digiti l'istruzione e prema **Generate**. Quando si trova nella schermata di modifica di una categoria, pagina di contenuto o marchio, i segnaposto corrispondenti vengono compilati. La risposta compare nella finestra e non viene salvato nulla.
- **Elenco prodotti.** Un pulsante **My AI Grok** accanto alle azioni di gruppo apre **Generate**, **Products**.

## 4. Front del negozio

Il modulo non ha alcuna schermata rivolta ai clienti. Non mostra nulla nell'intestazione, nel piè di pagina o in alcuna pagina di prodotto, categoria o checkout, e il tema non ha nulla da visualizzare o da sovrascrivere. I clienti non vedono mai alcuno strumento di generazione di testo; vedono solo il testo che lei ha già salvato nel catalogo.

### 4.1 Indirizzi usati dal modulo stesso

Due indirizzi web del suo negozio appartengono al modulo. Il primo non lo apre mai lei stesso.

- L'**indirizzo del generatore** viene richiamato dai pulsanti all'interno del back office (Fill, Try, Run, Playground e così via). È protetto da un segreto integrato nelle pagine del back office.
- L'**indirizzo del cron** viene richiamato dallo scheduler del suo server, oppure da lei in un browser durante i test. È descritto qui sotto.

### 4.2 Indirizzo del cron

L'indirizzo ha la forma dell'indirizzo del suo negozio, seguito dal percorso del modulo, dal segreto e dall'azione. Sostituisca i segnaposto con i suoi valori. Usi il segreto che vede nella schermata **Cron** e non lo pubblichi mai.

Per i prodotti:

`https://YOUR-SHOP/module/myaigrok/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent`

Per le categorie:

`https://YOUR-SHOP/module/myaigrok/cron?secret=YOUR_CATEGORY_SECRET&action=generateCategoryContent`

L'indirizzo mostrato nella schermata Cron si ferma dopo il segreto (il pannello delle categorie aggiunge una conclusione diversa che il negozio non usa). Aggiunga lei la parte `action`. Senza azione il negozio risponde **Invalid action!**

Il lotto usa le scelte salvate nella schermata Cron: campo, regola di selezione, lingua, modello, dimensione del lotto e debug. Ogni chiamata aggiorna un lotto e poi si ferma. Ogni scrittura riuscita compare anche in History con il metodo **cron**.

Per pianificarlo su un server Linux, crei un job cron che richiami l'indirizzo, ad esempio ogni dieci minuti:

```
*/10 * * * * curl -s "https://YOUR-SHOP/module/myaigrok/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent" > /dev/null
```

Mantenga l'indirizzo tra virgolette, perché contiene una e commerciale. Su Windows usi l'Utilità di pianificazione con un'attività che apra l'indirizzo. Per provare, imposti **Enable Debug** su **Yes**, salvi e apra l'indirizzo in un browser: la pagina stampa il piano (i parametri, i prodotti o le categorie selezionati e l'istruzione finale) e non salva nulla. Non condivida quell'output, perché contiene i parametri del suo indirizzo. Riporti il debug su **No** prima che lo scheduler usi l'indirizzo.

### 4.3 Cosa risponde l'indirizzo del cron

| Cosa vede | Cosa fare |
|---|---|
| **Cron Job feature is disabled. You can enable it from the module settings.** | Imposti **Enable Cron Feature** su **Yes** nella schermata Cron e salvi. |
| **The token does not exist or it's wrong!** | Il segreto manca o non corrisponde. Copi di nuovo il segreto dalla schermata Cron. |
| **Invalid action!** | La parte `action` manca o è scritta male. Usi una delle due forme della sezione 4.2. |
| **All must include all mandatory parameters!** | Un valore come campo, destinazione, dimensione del lotto, lingua o modello è vuoto. Apra la schermata Cron, lo compili e salvi. |
| **No valid product IDs provided.** | La Product ID list non contiene alcun numero utilizzabile. Corregga o svuoti l'elenco e salvi. |
| **No products to update.** oppure **No categories to update.** | Ormai nulla corrisponde alla regola. È la normale conclusione di un job completato. Cambi la regola di selezione o i filtri per elaborarne altri. |
| **N products have been updated.** oppure **N categories have been updated.** | Il lotto è terminato. Lo scheduler prenderà il lotto successivo alla chiamata seguente. |
| **Error!** seguito da un messaggio (ad esempio **Monthly generation budget reached.** o **Reply rejected by the studio quality gate.**) | Legga il messaggio e segua il capitolo 5. L'esecuzione si ferma al primo errore. |
| **Error! The model returned an empty response.** | Alzi **Max Tokens** in Settings, Grok, oppure provi un altro modello. |
| **Error! Could not save product** seguito da un id | Il prodotto non ha potuto essere salvato con il nuovo testo, ad esempio perché PrestaShop ha rifiutato il testo. Controlli quel prodotto ed esegua di nuovo. |

## 5. Problemi

### 5.1 L'installazione viene rifiutata

- **Sintomo:** **This module requires PHP 7.0.0 or newer. This server is running PHP** seguito dalla sua versione, oppure **Could not create the module database tables.**
- **Causa:** il PHP del server è troppo vecchio, oppure l'utente del database non può creare tabelle.
- **Cosa fare:** chieda al suo provider di hosting di passare a PHP 7.0 o successivo, oppure di dare all'utente del database il permesso di creare tabelle, e installi di nuovo.

### 5.2 Manca la voce di menu o il blocco prodotto

- **Sintomo:** nessun **AI Content Generator** sotto **Modules**, oppure nessun blocco **My AI Grok** nella scheda **Modules** del prodotto.
- **Causa:** una cache obsoleta, permessi mancanti del profilo del suo dipendente o un interruttore disattivato.
- **Cosa fare:** svuoti la cache in **Advanced Parameters**, **Performance**. In **Advanced Parameters**, **Team**, **Permissions** controlli che il suo profilo possa aprire le schermate del modulo. Se il menu continua a mancare, disinstalli e reinstalli il modulo. Per il blocco prodotto, controlli **Product edit page Form** e **Product Edit History** in Settings, General, e salvi il prodotto una volta così che abbia un id.

### 5.3 La chiave viene rifiutata o manca

- **Sintomo:** **Grok API KEY field is invalid!** al salvataggio, oppure **The Grok API key is not set. Add it in the module settings.** durante la generazione, oppure una riga di errore in History dopo ogni tentativo.
- **Causa:** il campo della chiave è vuoto o troppo corto, oppure la chiave è stata copiata con un errore di battitura o è stata revocata in xAI.
- **Cosa fare:** apra **Settings**, **Grok**, incolli una chiave nuova da https://console.x.ai e prema **Save**. Poi apra **History**, filtri **Status** su **Error** e apra la riga più recente per leggere la risposta esatta di Grok.

### 5.4 Il modello viene rifiutato

- **Sintomo:** **OpenAi Model field is invalid!**, oppure errori in History che dicono che il modello non esiste o che non ha accesso.
- **Causa:** il nome del modello è troppo corto, scritto male, oppure il suo account xAI non può richiamare quel modello.
- **Cosa fare:** in **Settings**, **Grok** scelga uno dei modelli integrati, oppure aggiunga l'id esatto dal suo account xAI con **Add model**, poi salvi.

### 5.5 La chiamata va in timeout

- **Sintomo:** **Grok request timed out after N seconds. The model may be overloaded, or the timeout is too low for this prompt.** oppure, in una schermata, **The request timed out or the shop blocked it.**
- **Causa:** un modello lento, una risposta molto lunga, un servizio xAI occupato o un server che blocca le richieste lunghe.
- **Cosa fare:** alzi **API timeout (seconds)** in **Settings**, **General** (fino a 600), abbassi **Max Tokens** per i campi brevi oppure provi un modello più veloce. Per il cron, abbassi **Product to update** così che un lotto rientri nel limite di tempo del server.

### 5.6 La risposta è vuota o troncata

- **Sintomo:** **The model hit the token limit before returning any text. Increase "Max Tokens" in the module settings — reasoning models spend part of that budget on thinking.** oppure **The response was blocked by the provider content filter. Try rewording the prompt.** oppure **The model returned an empty response.**
- **Cosa fare:** alzi **Max Tokens** in **Settings**, **Grok**. Per una risposta bloccata riformuli l'istruzione. Poi riprovi.

### 5.7 Il budget mensile è stato raggiunto

- **Sintomo:** **Monthly generation budget reached. Raise it in the studio settings or wait until next month.**
- **Cosa fare:** apra **Settings**, **Studio**, alzi **Monthly generation budget** oppure lo imposti a 0, e salvi. Le chiamate fallite non vengono contate.

### 5.8 Una risposta viene rifiutata per una parola vietata

- **Sintomo:** **The reply was rejected because it contains a forbidden word from the studio settings.** (il cron mostra **Reply rejected by the studio quality gate.**). Il prodotto resta invariato e History mostra una riga di errore.
- **Cosa fare:** esegua di nuovo la generazione (la formulazione cambia ogni volta), accorci **Forbidden words** in **Settings**, **Studio**, oppure imposti **Quality gate** su **Disabled**.

### 5.9 Un campo viene saltato o il testo è sbagliato

- **Sintomo:** una riga indica **skipped** con **Product skipped.** (o **Category skipped.**), oppure il testo è stato aggiunto al vecchio invece di sostituirlo.
- **Causa:** **Existing text** era impostato su **Skip if filled**, **Add above** o **Add below**.
- **Cosa fare:** scelga **Replace** ed esegua di nuovo. Per annullare una scrittura indesiderata su un prodotto, usi la scheda **History** del prodotto e prema **Restore**.

### 5.10 Il cron non fa nulla, si ripete o l'indirizzo smette di funzionare

- **Sintomo:** lo scheduler viene eseguito ma non viene scritto nulla, oppure gli stessi prodotti vengono riscritti, oppure un indirizzo che ieri funzionava ora risponde **The token does not exist or it's wrong!**
- **Cron disattivato:** **Cron Job feature is disabled.** Imposti **Enable Cron Feature** su **Yes** nella schermata Cron e salvi.
- **Nessuna azione nell'indirizzo:** ottiene **Invalid action!** Aggiunga l'azione come mostrato nella sezione 4.2.
- **Debug lasciato attivo:** il debug stampa il piano e non salva mai. Imposti **Enable Debug** su **No** e salvi.
- **Nessun modello:** se **Prompt Template** è vuoto, l'istruzione inviata è vuota. Scelga un modello attivato e salvi.
- **Segreto sostituito:** il pulsante **Generate Token** accanto al segreto non ha alcuna funzione in questa versione, quindi digiti o incolli lei stesso un lungo segreto casuale. Un segreto più corto di 24 caratteri viene sostituito da uno nuovo casuale la prossima volta che si apre una qualsiasi pagina del back office, e il vecchio indirizzo smette di funzionare. Copi di nuovo il segreto dalla schermata Cron.
- **Sempre gli stessi prodotti:** quando seleziona **Product Categories**, i prodotti la cui categoria predefinita è selezionata vengono scelti a ogni chiamata, anche se la regola di selezione dice che non sono più in attesa. Lasci vuoto l'albero delle categorie e limiti il cron con **Product ID list**, oppure usi la schermata **Generate** per il lavoro limitato per categoria.
- **Errori del server:** gli errori del cron vengono stampati solo nella risposta dell'indirizzo; non vengono salvati in History. Esegua l'indirizzo in un browser con il debug attivo per leggerli.

### 5.11 Un'esecuzione di massa si ferma a metà

- **Sintomo:** la riga di stato smette di muoversi, oppure alcune righe non hanno risultato.
- **Causa:** la scheda del browser è stata chiusa o ricaricata, il computer è andato in sospensione o una chiamata è andata in timeout.
- **Cosa fare:** prema di nuovo **Run**. Scelga **Skip if filled** in **Existing text** così che i campi già terminati non vengano pagati due volte. Le righe con un errore riportano il motivo; lo stesso motivo è in History.

### 5.12 Il modulo Generate category content non fa nulla

- **Sintomo:** dopo aver premuto **Generate content** nel modulo sotto l'elenco delle categorie, finisce nel filtro delle categorie e non viene scritto nulla.
- **Cosa fare:** usi il pulsante **Run on the categories below** sopra quel modulo. Nelle schermate dei filtri di prodotti e categorie, il pulsante **Module settings** non apre le impostazioni di questo modulo; usi la voce **Settings** della barra di navigazione.

### 5.13 Problemi con le foto del prodotto (Photos)

- **Sintomo:** **Find pages** non mostra foto, oppure vede **No images could be imported.** seguito da dettagli.
- **Causa:** Grok ha suggerito pagine senza foto utilizzabili, la pagina ha bloccato il download del negozio, l'indirizzo puntava a una rete privata oppure il file non era un'immagine valida.
- **Cosa fare:** prema di nuovo **Find pages**, riformuli **AI Image Search Prompt** nella schermata **Images** (ad esempio chiedendo siti dei produttori) oppure carichi le foto a mano.

### 5.14 La schermata New product fallisce

- **Sintomo:** **Add an API key in the module settings first.**, **Prompt is required**, **Failed to parse AI response. Please try again.** oppure **Failed to create product**.
- **Cosa fare:** salvi la chiave API in **Settings**, **Grok**, scriva una traccia e prema di nuovo **Generate data**. Alzi **Max Tokens** se la risposta sembra troncata. Se **Create product** fallisce, controlli che la bozza non abbia un nome vuoto.

### 5.15 Il ripristino non è possibile

- **Sintomo:** **Error! This log entry has no previous value to restore.** oppure **Error! Nothing to restore for this entry.**
- **Causa:** quella riga non ha memorizzato un valore precedente (ad esempio un prompt libero, o un campo che era vuoto).
- **Cosa fare:** usi un'altra riga dello stesso prodotto, oppure corregga il testo a mano.

### 5.16 La schermata dice che il token non è valido

- **Sintomo:** **Error! Invalid token!** premendo un pulsante dopo una lunga pausa.
- **Causa:** la pagina del back office è stata aperta prima che il segreto interno del modulo fosse rinnovato.
- **Cosa fare:** ricarichi la pagina e riprovi.

### 5.17 Il testo è più corto del previsto

- **Causa:** PrestaShop limita alcuni campi. Il modulo accorcia un nome a 128 caratteri, una descrizione breve a 800, un meta title a 69 e una meta description a 159.
- **Cosa fare:** usi un'istruzione più concisa, ad esempio chiedendo un titolo inferiore a 60 caratteri.

### 5.18 Log tecnico e debug

- **Sintomo:** le servono più dettagli su una chiamata fallita, oppure il log di PrestaShop cresce.
- **Cosa fare:** attivi **Debug mode** in **Settings**, **General**, ripeta l'azione, legga le nuove voci in **Advanced Parameters**, **Logs** e disattivi di nuovo il debug. Riporti anche **Enable Debug** della schermata Cron su **No** dopo i test.

### 5.19 Notifiche di aggiornamento

- **Sintomo:** **Check Now** non mostra né **Module is up to date!** né **New version available!**
- **Causa:** il suo server non riesce a raggiungere il server di aggiornamento di MyPresta.eu, che viene interrogato con un breve limite di tempo.
- **Cosa fare:** consenta le connessioni in uscita oppure riprovi più tardi. Il modulo funziona anche senza questo controllo.

## 6. Per gli sviluppatori

### 6.1 Panoramica

- **Classe principale:** `myaigrok` (file `myaigrok.php`), estende `Module`, versione `1.1.0`, `bootstrap = true`, `need_instance = 0`.
- **Nome nell'elenco dei moduli:** `My AI Grok - AI content generation`. **Autore:** `MyPresta.eu`. **Tab:** `front_office_features`.
- **Compatibilità:** PrestaShop da 1.6 fino a 9.99.99 (`ps_versions_compliancy`). PHP minimo 7.0.0 (`MIN_PHP_VERSION`); `install()` rifiuta un PHP più vecchio con un messaggio tradotto.
- **Classi:** il namespace `MyAIGrok\` è caricato da `autoload.php` (senza Composer). `MyAIGrok\OpenAIService` è un client cURL per `https://api.x.ai/v1` (`/chat/completions`, `/models`); `MyAIGrok\Studio` applica lo stile della casa, il budget mensile e il controllo di qualità. Il verificatore di aggiornamenti `myaigrokUpdate` (in `lib/updateChecker.php`) estende `myaigrok`.
- **Flusso dei dati:** le impostazioni risiedono in `ps_configuration` (prefisso `MYPRESTA_MYAIGROK_`). I pulsanti del back office e le esecuzioni di massa richiamano il front controller `ajax`; gli scheduler richiamano il front controller `cron`. Entrambi leggono le impostazioni, fanno passare il prompt da `Studio::gate()` (controllo del budget e `Studio::decorate()`), lo inviano con `OpenAIService::createChatCompletion()`, controllano la risposta con `Studio::inspect()`, scrivono il testo nell'oggetto prodotto o categoria e inseriscono una riga in `myaigrok_log`.
- **Chiamate al fornitore:** vengono inviati i parametri del modello `temperature`, `max_tokens`, `top_p`, `frequency_penalty`, `presence_penalty`; i parametri che un modello rifiuta vengono appresi e memorizzati in `MYPRESTA_MYAIGROK_MODEL_CAPS`. La verifica del certificato è disattivata solo quando il negozio stesso gira su localhost.

### 6.2 File

| Percorso | Scopo |
|---|---|
| `myaigrok.php` | Classe del modulo: installazione, disinstallazione, hook, schermate Settings (HelperForm), Dashboard, posizionamento del menu, scheda Modules del prodotto. |
| `autoload.php` | Caricatore di classi per il namespace `MyAIGrok\`. |
| `src/OpenAIService.php` | Client cURL per Grok: chat completions, elenco dei modelli, timeout, adattamento dei parametri. |
| `src/Studio.php` | `gate()`, `decorate()`, `inspect()`, `overBudget()`, prompt del pacchetto SEO e dei testi alt. |
| `controllers/admin/AdminMyAIGrok.php` | Schermate Generate (filtri di prodotti e categorie, pannelli di massa). |
| `controllers/admin/AdminMyAIGrokProductCreator.php` | Schermata New product e le sue azioni Ajax. |
| `controllers/admin/AdminMyAIGrokCron.php` | Moduli Cron. |
| `controllers/admin/AdminMyAIGrokUsage.php` | Rapporto e elenco di History. |
| `controllers/admin/AdminMyAIGrokImageFinder.php` | Schermata Images e azioni di ricerca e importazione delle immagini. |
| `controllers/admin/AdminMyAIGrokMain.php`, `AdminMyAIGrokSettings.php` | Reindirizzano alla pagina di configurazione del modulo. |
| `controllers/front/ajax.php` | Endpoint di generazione usato dal back office. |
| `controllers/front/cron.php` | Endpoint del cron. |
| `lib/sectionHelp.php` | Contenuto del pannello laterale Help. |
| `lib/updateChecker.php` | Controllo degli aggiornamenti di MyPresta.eu (`dev.mypresta.eu/update/get.php`; invia nome del modulo, versione, segnaposto della chiave di licenza e indirizzo del negozio). |
| `lib/prestashop9compatibility.php` | Funzioni di compatibilità (cifratura dei token per PS 9). |
| `lib/searchTool/` | Piccolo helper di autocompletamento caricato nella pagina di configurazione. |
| `views/templates/hook/*.tpl` | Template di hook e schermate (nav, subnav, dashboard, usage, generatori di massa, playground, schede prodotto, pannelli cron). |
| `views/templates/admin/product_creator.tpl` | Schermata New product. |
| `views/js/back.js`, `product-fields.js`, `image-finder.js`, `admin-products-bulk.js`, `admin-help.js`, `dashboard.js`, `chart.min.js` | Script del back office. |
| `views/css/back.css`, `admin-nav.css`, `stats.css` | Stili del back office. |
| `translations/{iso}.php` | File di traduzione (molte lingue). |

### 6.3 Controller

| Controller | Genitore e percorso | Note |
|---|---|---|
| `AdminMyAIGrokMain` | Figlio della scheda genitore Modules (`AdminParentModulesSf`, altrimenti `AdminParentModules`, altrimenti `AdminModules`), nome nel menu **AI Content Generator** | Reindirizza a `AdminModules&configure=myaigrok&mds_tab=dashboard`. |
| `AdminMyAIGrokSettings` | Figlio nascosto (`active = 0`) di Main | Reindirizza a `mds_tab=settings`. |
| `AdminMyAIGrok` | Figlio nascosto di Main | `mds_sub=products` o `categories`; azioni di invio `filterProducts`, `filterCategories`. |
| `AdminMyAIGrokProductCreator` | Figlio nascosto di Main | Azioni Ajax `generateProductData`, `extractImages`, `createProduct`, `generateImages` (segnaposto). |
| `AdminMyAIGrokCron` | Figlio nascosto di Main | Invio `submitCronUpdate`, `submitCatCronUpdate`. |
| `AdminMyAIGrokUsage` | Figlio nascosto di Main | Filtri `stats_preset`, `stats_from`, `stats_to`, `stats_model`, `stats_type`, `stats_status`, `stats_lang`, `stats_employee`, `stats_entity`, `stats_q`; `clear_log` elimina tutte le righe; azione di riga `view`. |
| `AdminMyAIGrokImageFinder` | Figlio nascosto di Main | Azioni `searchImages`, `extractImages`, `saveImages`; host di reti private rifiutati; fino a 5 pagine e 24 foto. |

I permessi sono i diritti standard delle schede del back office per questi controller. Ogni controller di amministrazione reindirizza a `AdminHome` quando il modulo è disattivato. `AdminModules` con `configure=myaigrok` accetta `mds_tab` (`dashboard`, `settings`, `updates`), `mds_sub` (`general`, `openai`, `studio`, `templates`, `playground`; `openai` è la scheda Grok) e `mcg_preset` (`today`, `7`, `30`, `90`, `month`, `all`) oltre a `mds_from`, `mds_to`.

**Front `ajax`** (`module/myaigrok/ajax`): richiede `secret_token` uguale a `MYPRESTA_MYAIGROK_TOKEN`, altrimenti `Error! Invalid token!`. Non c'è alcun controllo sul dipendente; il token presente nella pagina è l'unica protezione. Azioni: `initiatePrompt`, `updateSettings` (scrive le chiavi di campionamento), `updateProduct`, `updateCategory`, `initiateProductRestore`, `generateSeoPack`, `generateAltTexts` (nessun pulsante nell'interfaccia). `updateProduct` e `updateCategory` accettano i valori di `behavior` `replace`, `keep`, `keep_top`, `keep_end` e `single_product` / `single_category` (prova a vuoto, non viene salvato nulla).

**Front `cron`** (`module/myaigrok/cron`): il costruttore fa tutto il lavoro. Esce con un messaggio quando `ENABLE_CRON` è 0, poi richiede `secret` uguale a `MYPRESTA_MYAIGROK_SECRET` oppure a `MYPRESTA_MYAIGROK_CAT_SECRET` (uno qualsiasi dei due segreti viene accettato per entrambe le azioni). `action` deve essere `generateProductContent` o `generateCategoryContent`, altrimenti `Invalid action!`. Il parametro `entity` mostrato nell'indirizzo delle categorie nella schermata Cron non viene letto. Parametri facoltativi sovrascrivono le scelte salvate: per i prodotti `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug`, `categories`, `productIds`; per le categorie `updatedField`, `categoryTarget`, `categoriesToUpdate`, `languageId`, `promptTemplateId`, `debug`. Destinazioni ammesse: `pendingGrok`, `pendingField`, `emptyField`; un valore errato risponde `productTarget parameter is wrong! Allowed values: ...`, un campo errato `updatedField parameter is wrong!`. La condizione dell'elenco di categorie per i prodotti viene aggiunta come `p.id_product IN (...) OR p.id_category_default IN (...)` senza parentesi, quindi si combina con le altre condizioni secondo la precedenza SQL (vedere la sezione 5.10). Gli errori del cron vengono stampati (echo) e la richiesta termina; non vengono scritti in `myaigrok_log`.

Risorse referenziate ma non fornite nel pacchetto: `views/js/admin.js` e `views/css/admin.css` (controller Main e Settings, irraggiungibili perché prima reindirizzano) e `views/js/product_creator.js` e `views/css/product_creator.css` (schermata New product; la schermata usa `back.js`). Le funzioni `generateTokenAndFill()` e `generateCategoryTokenAndFill()` richiamate dai pulsanti **Generate Token** non sono definite in alcuno script fornito. I pulsanti **Module settings** nei moduli di filtro di Generate rimandano a `configure=mychatgpt`.

### 6.4 Hook

Registrati in `install()`:

| Hook | Comportamento |
|---|---|
| `displayAdminProductsExtra` | Genera il blocco My AI Grok (`product-tab-wrapper.tpl`) nella scheda Modules del prodotto. Non restituisce nulla quando sia `PRODUCT` sia `PRODUCT_LOG` sono 0. |
| `displayBackOfficeHeader` | Richiama `ensureLongSecrets()` e `placeModuleMenu()`, aggiunge CSS e JS, pubblica variabili JS, registra una sola volta la scheda Image Finder (`IMAGEFINDER_TAB_OK`), carica `product-fields.js` nelle pagine di prodotti e categorie e lo script del pulsante dell'elenco prodotti. |
| `displayBackOfficeTop` | Pubblica `admin_controller_url` e gli id della categoria, pagina CMS o marchio in modifica, e restituisce il generatore della barra superiore quando `TOPCTA` è 1. |
| `dashboardZoneTwo` | Genera `dashboard.tpl`. Registrato di nuovo in `displayBackOfficeHeader` se manca. |
| `displayHeader`, `displayFooter` | Registrati; i metodi sono vuoti. |
| `displayAdminProductsMainStepLeftColumnMiddle`, `displayAdminProductsMainStepLeftColumnBottom`, `actionProductFormBuilderModifier` | Registrati; i metodi restituiscono una stringa vuota o nulla. |

Il modulo non sovrascrive né `enable()` né `disable()`. Disattivare il modulo fa solo sì che i suoi controller di amministrazione reindirizzino alla dashboard di PrestaShop. Il metodo `hookActionProductGridDataModifier` esiste ma non è registrato. Il modulo non espone hook propri.

### 6.5 Override

Il modulo non ha override.

### 6.6 Database

| Tabella | Contenuto |
|---|---|
| `{prefix}myaigrok_prompt` | `id_prompt`, `status`, `title` (128), `prompt` (text), `date_generated`. Popolata con 16 modelli all'installazione. |
| `{prefix}myaigrok_log` | `id_log`, `id_product`, `id_category`, `id_cms`, `id_manufacturer`, `id_lang`, `id_employee`, `type`, `method`, `status`, `ai_service`, `model`, `http_code`, `duration_ms`, `prompt_tokens`, `completion_tokens`, `total_tokens`, `error_message`, `prompt`, `reply`, coppie `old_` e `new_` per name, description, description_short, meta_title, meta_description e tags, `date_updated`. Chiavi su `id_product` e `status`. |

Le tre colonne dei token vengono aggiunte da `ensureUsageColumns()` al primo utilizzo quando una tabella più vecchia ne è priva. La disinstallazione elimina entrambe le tabelle, tutte le schede di amministrazione (compresa la vecchia `AdminMyAIGrokChangelog`) e le chiavi di configurazione principali. I testi generati di prodotti e categorie non vengono toccati.

### 6.7 Chiavi e traduzioni

Tutte le chiavi iniziano con `MYPRESTA_MYAIGROK_`. Valori dopo l'installazione:

| Chiave | Valore |
|---|---|
| `LIVE_MODE`, `DEBUG_MODE` | 0, 0 |
| `TIMEOUT` | 120 (limitato a 10–600 al salvataggio) |
| `PRODUCT_LOG`, `TOPCTA`, `PRODUCT`, `IMAGEFINDER_ENABLE` | 1 ciascuna |
| `IMAGEFINDER_PROMPT` | Prompt predefinito che chiede 5 URL di pagine come array JSON |
| `TOKEN`, `SECRET`, `CAT_SECRET` | 32 caratteri casuali; `ensureLongSecrets()` rigenera quelli più corti di 24 caratteri |
| `API_KEY`, `MODEL`, `EXTRA_MODELS`, `MODEL_CAPS` | un singolo spazio, `grok-4.7`, vuoto, vuoto |
| `TEMPERATURE`, `MAX_TOKENS`, `TOP_P`, `FREQ_PEN`, `PRES_PEN` | 0.7, 3200, 1, 0, 0 |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | vuoto |
| `BUDGET`, `QUALITY` | 0, 1 |
| `ENABLE_CRON`, `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | 0, 6, 6 |
| `updatedField`, `productTarget`, `productsToUpdate`, `promptTemplateId`, `languageId`, `interval_select`, `debug`, `productIdsList`, `categories` | `description`, `pendingGrok`, 5, vuoto, lingua predefinita del negozio, vuoto, 0, vuoto, vuoto |
| `catupdatedField`, `categoryTarget`, `categoriesToUpdate`, `catpromptTemplateId`, `catlanguageId`, `catdebug` | `description`, `pendingGrok`, 5, vuoto, lingua predefinita del negozio, 0 |
| `IMAGEFINDER_TAB_OK` | Impostata dopo il primo caricamento del back office |

Le schermate Generate memorizzano anche gli ultimi valori dei filtri sotto `MYPRESTA_MYAIGROK_FIELD`, `_LANGUAGE`, `_CONTENT`, `_DELAY`, `_EXISTING`, `_HISTORY`, `_STATUS`, `_STOCK`, `_PROD_IDS`, `_PROD_REF`, `_PROD_DATE_FROM`, `_PROD_DATE_TO`, `_PROD_MIN_ID`, `_PROD_MAX_ID`, `_PROD_LIMIT`, `_CATEGORIES`, `_BRANDS`. La disinstallazione non le elimina. Il verificatore di aggiornamenti usa `mypresta_updates`, `update_myaigrok` e `updatev_myaigrok`. Ogni caricamento della pagina di configurazione nel back office elimina le chiavi obsolete `GEMINI_API_KEY`, `GEMINI_MODEL` e `ACTIVE_SERVICE`.

**Traduzioni:** per aggiungere una lingua, crei `translations/{iso}.php`. Le stringhe del modulo usano `$this->l()` e `{l s='...' mod='myaigrok'}`. I controller di amministrazione usano `trans()` con domini come `Admin.MyAIGrok` e `Admin.MyAIGrokCron` su PrestaShop 8 e 9, e il `l()` del modulo su 1.6 e 1.7. Queste stringhe non sono tradotte: i messaggi costruiti in `back.js` e i testi di riserva di `product-fields.js`, le risposte in testo semplice del cron, i testi di errore di Image Finder e New product e i prompt in inglese costruiti da `Studio`. Le descrizioni dei campi (What it does / How to configure / Effect) sono costruite da `fieldHelp()` in `myaigrok.php` e dal wrapper `help()` di ogni controller di amministrazione; i testi del generatore di massa e del Playground si trovano nei template; i testi del pannello Help sono in `lib/sectionHelp.php`.

### 6.8 Estendere

- Aggiunga o modifichi i modelli di prompt in `myaigrok_prompt` (o nella schermata Prompt templates); i segnaposto vengono sostituiti in `ajax.php` e `cron.php`.
- Aggiunga id di modello tramite **Add a Grok model**; vengono memorizzati in `EXTRA_MODELS`.
- Dia forma all'output con le regole Studio; vengono applicate in `Studio::decorate()`.
- Richiami l'endpoint del cron con parametri di sovrascrittura per eseguire job diversi senza toccare il modulo salvato.
- Il front office non genera alcun template del modulo, quindi il tema non ha nulla da sovrascrivere.

## 7. Aiuto

Pagina prodotto del modulo: https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-grok-ai.html

Per contattare il supporto sul modulo:

1. Acceda al suo account cliente su mypresta.eu.
2. Vada al modulo di contatto.
3. Scelga l'argomento **Support for paid modules**.
4. Descriva cosa ha fatto e cosa ha visto. Aggiunga il numero di versione mostrato accanto al nome del modulo in alto nelle sue schermate e, se una generazione è fallita, il testo dell'errore dalla colonna **Reply / Error** di **History**.
