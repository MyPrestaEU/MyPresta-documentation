---
title: "My AI Mistral - AI content generation - documentazione e manuale utente"
description: "Istruzioni di configurazione, uso quotidiano e risoluzione dei problemi per i commercianti che hanno già installato My AI Mistral nel proprio negozio PrestaShop."
sidebar:
  label: "My AI Mistral - AI content generation - documentazione e manuale utente"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Meta and catalog descriptions with Mistral AI su MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/meta-and-catalog-descriptions-with-mistral-ai.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ai-artificial-intelligence/meta-and-catalog-descriptions-with-mistral-ai/)
>
> ---


## 1. Requisiti

### 1.1 Negozio e server

| Elemento | Necessario | Note |
|---|---|---|
| PrestaShop | 1.6 fino a 9.x | Il modulo dichiara il supporto per le versioni da 1.6 a 9.99.99. La scheda **My AI Mistral** nella pagina di modifica del prodotto e i piccoli pulsanti "Generate with AI" sono pensati per PrestaShop 1.7, 8 e 9. |
| PHP | 7.0 o successivo | L'installazione si interrompe con un messaggio quando il server esegue un PHP più vecchio. |
| Estensioni PHP | cURL, JSON, mbstring, DOM | cURL viene usato per ogni chiamata a Mistral AI. DOM e mbstring servono a leggere le pagine web della ricerca foto e a misurare e tagliare il testo generato. |
| Connessione in uscita | HTTPS (porta 443) verso `api.mistral.ai` | Il server deve poter chiamare l'API di Mistral AI. I piani di hosting che bloccano le connessioni in uscita non funzionano. |
| Indirizzo del front del negozio | Raggiungibile dal browser | I pulsanti nel back office inviano le loro richieste a un indirizzo del front del suo negozio. Una richiesta di password, una regola del firewall o una pagina di manutenzione che blocca quell'indirizzo fa fallire i pulsanti. |

### 1.2 Account Mistral AI

1. Crei un account nella console di Mistral AI e apra la pagina delle chiavi API: https://console.mistral.ai/api-keys/
2. Crei una chiave e la copi. La console la mostra una sola volta.
3. Si assicuri che l'account possa usare l'API (un piano o una fatturazione che includa l'accesso all'API). Ogni testo generato è una richiesta API a pagamento o conteggiata nella sua quota.

Il modulo non richiede alcun altro modulo e non aggiunge alcun override. Non mostra nulla ai suoi clienti.

### 1.3 Costi e carico

- Un campo generato in una lingua è una richiesta. Un lotto di 40 prodotti con descrizioni e meta tag in due lingue equivale a 40 × 4 × 2 = 320 richieste, perché l'opzione delle descrizioni scrive due campi e l'opzione meta ne scrive altri due.
- Ogni richiesta attende la risposta al massimo per il tempo impostato in **API timeout (seconds)** (120 secondi per impostazione predefinita). Un lotto grande avviato dal browser è lento per natura; per i cataloghi grandi usi cron.
- Il modulo può smettere di generare dopo un numero mensile di richieste riuscite (**Monthly generation budget** in Studio).

## 2. Installazione

### 2.1 Installare il modulo

1. Apra **Modules > Module Manager** (**Modules and Services** in PrestaShop 1.6).
2. Faccia clic su **Upload a module** (**Add a new module** in 1.6) e scelga il file ZIP del modulo.
3. Faccia clic su **Install**, poi su **Configure**.

Che cosa fa l'installazione al posto suo:

- Aggiunge la voce di menu del back office **AI Content Generator** sotto **Modules**. Apre la pagina delle impostazioni del modulo, e tutte le altre schermate si raggiungono dalla barra dei menu in cima a quella pagina.
- Crea due tabelle nel database: una per i modelli di prompt e una per la cronologia delle richieste.
- Salva 16 modelli di prompt già pronti (nomi dei prodotti, descrizioni, meta title, meta description e tag). Tutti partono attivati.
- Genera i codici segreti per i pulsanti del back office e per cron, e seleziona il modello **mistral-small-latest**.
- Non svuota la cache di PrestaShop. Se la voce di menu non compare, svuoti la cache in **Advanced Parameters > Performance**.

Alla prima visita potrebbe vedere un messaggio verde "Mistral AI API Key has been automatically cleaned (whitespace removed)". Significa soltanto che la chiave segnaposto vuota è stata ripulita. Non c'è alcun problema.

### 2.2 Primi passi dopo l'installazione

1. Apra **AI Content Generator > Settings > Mistral** e incolli la sua chiave API.
2. Mantenga il modello predefinito per un primo test e faccia clic su **Save**.
3. Apra **Settings > Playground**, scriva una breve istruzione e faccia clic su **Generate**. Una risposta indica che la connessione funziona.
4. Apra un prodotto esistente, vada alla sua scheda **Modules**, scelga **My AI Mistral**, apra **Simulate** e faccia clic su **Try** accanto a **Meta title**. Il testo viene mostrato e non viene salvato nulla.

### 2.3 Aggiornamento

Carichi il nuovo ZIP in Module Manager nello stesso modo della prima installazione. Impostazioni, modelli e cronologia vengono mantenuti. La pagina **Updates** del modulo segnala se esiste una versione più recente (sezione 3.15).

### 2.4 Disinstallazione

La disinstallazione rimuove le voci di menu, i modelli di prompt, l'intera cronologia delle richieste e le impostazioni del modulo, compresi la chiave API e i segreti di cron. Una reinstallazione riparte da zero e crea nuovi segreti, quindi ogni indirizzo che ha fornito a un pianificatore di attività deve essere sostituito.

I testi già scritti in prodotti e categorie, le foto importate, i prodotti creati con **New product** e i tag restano nel suo negozio. Le impostazioni del controllo degli aggiornamenti e alcuni valori di filtro residui non vengono rimossi.

## 3. Configurazione e lavoro nel back office

Le schermate di questo manuale mostrano il back office in inglese. I nomi di menu, campi e pulsanti sono riportati in inglese e in grassetto, così come li vede sullo schermo.

### 3.1 Come procede il lavoro

1. **Connect** – incolli la chiave API e scelga il modello (Settings – Mistral).
2. **Set the rules** – regole della casa, budget e controllo qualità (Settings – Studio).
3. **Prepare prompts** – modifichi o aggiunga modelli di prompt (Settings – Prompt templates) e li provi nel Playground.
4. **Generate** – scelga una delle tre modalità:
   - un prodotto alla volta, dalla pagina di modifica del prodotto (sezione 3.16) o con i piccoli pulsanti "Generate with AI" accanto ai campi (sezione 3.17);
   - molti prodotti o categorie in una volta, dalle pagine Generate (sezioni 3.9 e 3.10);
   - automaticamente a piccoli lotti, con cron (sezione 3.12).
5. **Check** – ogni richiesta viene scritta in History (sezione 3.13). Un testo sbagliato può essere ripristinato dalla scheda History del prodotto stesso.

Ogni pagina delle impostazioni ha il proprio pulsante **Save**. Salvi una pagina prima di lasciarla, perché le pagine non condividono un unico modulo.

### 3.2 Aprire il modulo e la barra dei menu

Apra **Modules > AI Content Generator**, oppure faccia clic su **Configure** in Module Manager. Ogni schermata mostra in alto la stessa barra dei menu:

| Voce di menu | Che cosa apre |
|---|---|
| Dashboard | Schede di utilizzo e grafici (sezione 3.3). |
| Settings | Un gruppo con cinque sottopagine: General, Mistral, Studio, Prompt templates, Playground (sezioni da 3.4 a 3.8). |
| Generate | Generazione di massa per prodotti e per categorie (sezioni 3.9 e 3.10). |
| New product | Crea un prodotto a partire da un breve brief (sezione 3.11). |
| Cron | Indirizzi per la generazione pianificata (sezione 3.12). |
| History | Elenco di tutte le richieste con filtri e totali dei token (sezione 3.13). |
| Images | Impostazioni della ricerca foto (sezione 3.14). |
| Updates | Controllo degli aggiornamenti (sezione 3.15). |

Ogni schermata ha un pulsante **Help**. Apre un pannello laterale con una breve spiegazione di quella schermata. Passando il mouse su una voce di menu compare un suggerimento di una riga. Sotto ogni campo trova una descrizione in tre parti: che cosa fa il campo, come impostarlo e quale effetto ha.

### 3.3 Dashboard

![Dashboard with usage cards and charts](https://mypresta.eu/docs/images/docs/myaimistral-dashboard.webp)

La Dashboard conta ciò che il modulo ha fatto nel periodo selezionato. La riga in alto indica il servizio attivo e il modello.

| Elemento | Predefinito | Che cosa mostra |
|---|---|---|
| Period buttons | 30 days | Today, 7 days, 30 days, 90 days, This month, All time. |
| From / To and Apply | compilato dal periodo | Un intervallo personalizzato. Se From è successivo a To, le due date vengono scambiate. |
| Requests | – | Ogni chiamata salvata a Mistral AI nel periodo. |
| Success | – | Chiamate che hanno restituito un testo. |
| Errors | – | Chiamate fallite. Apra History per vedere il motivo. |
| Tokens sent | – | Dimensione delle istruzioni che ha inviato. |
| Tokens received | – | Dimensione delle risposte. |
| Requests and errors | – | Grafico a linee per giorno. |
| Tokens sent and received | – | Grafico a linee per giorno. |
| Requests by model | – | Grafico a barre. |

La pagina si limita a riferire. Da qui non viene generato né modificato nulla nel catalogo, e History non viene cancellata.

### 3.4 Settings – General

![Settings – General](https://mypresta.eu/docs/images/docs/myaimistral-settings-general.webp)

Apra **Settings > General**. Questa pagina decide che cosa vedono i dipendenti nel back office. Salvarla non cambia alcun testo dei prodotti.

| Campo | Predefinito | Che cosa fa |
|---|---|---|
| Live mode | Disabled | Segna il modulo come in funzione sul negozio reale anziché in una configurazione di prova. Lo attivi sul negozio di produzione. |
| Debug mode | Disabled | Scrive ulteriori dettagli diagnostici nel log di PrestaShop quando una chiamata al provider fallisce. Lo attivi solo mentre indaga su un errore. I clienti non lo vedono mai. Non è la stessa cosa di **Enable Debug** nella pagina Cron. |
| API timeout (seconds) | 120 | Per quanti secondi una chiamata a Mistral può durare prima che il modulo rinunci. Il valore viene mantenuto tra 10 e 600. Un valore vuoto o non numerico viene salvato come 120. Lo alzi verso 600 per testi lunghi e modelli lenti. |
| Product Edit History | Enabled | Mostra la sottoscheda **History** nella pagina di modifica del prodotto, così può rimettere un vecchio valore. Le righe passate restano comunque in History. |
| Admin Top Bar CTA | Enabled | Mostra la piccola icona a bacchetta nella barra superiore del back office. Disattivarla rimuove solo quel pulsante, non il menu del modulo. |
| Product edit page Form | Enabled | Mostra il pannello **My AI Mistral** (Generate, Simulate, Photos) nella scheda **Modules** della pagina di modifica del prodotto. Lo disattivi quando devono essere usati solo la generazione di massa e cron. I piccoli pulsanti "Generate with AI" accanto ai campi (sezione 3.17) non vengono disattivati da questa impostazione in questa versione. |
| AI Image Finder | Enabled | Mostra o nasconde la ricerca foto nella pagina di modifica del prodotto. Un'immagine viene importata solo dopo la sua conferma. |
| AI Image Search Prompt | Istruzione integrata | L'istruzione inviata quando qualcuno cerca foto. `{product_name}` e `{product_description}` vengono sostituiti con il prodotto corrente. Mantenga la richiesta di un elenco di indirizzi di pagina in formato JSON. Gli stessi due campi si ripetono nella pagina **Images**. |

Faccia clic su **Save**. La conferma è "Settings Updated".

### 3.5 Settings – Mistral

![Settings – Mistral](https://mypresta.eu/docs/images/docs/myaimistral-settings-mistral.webp)

Apra **Settings > Mistral**. La pagina collega il negozio al suo account Mistral AI e imposta quanto sia varia la formulazione. I campi di campionamento non cambiano quali prodotti vengono aggiornati.

| Campo | Predefinito | Che cosa fa |
|---|---|---|
| Mistral AI API KEY | vuoto | La chiave da https://console.mistral.ai/api-keys/. Gli spazi vengono rimossi al salvataggio. Lasci il campo intatto per mantenere la chiave memorizzata. Un valore più corto di 10 caratteri viene rifiutato finché non è memorizzata alcuna chiave. |
| Model | mistral-small-latest | Il modello che scrive il testo. L'elenco contiene i modelli integrati e quelli che ha aggiunto. Un modello che la sua chiave non può usare restituisce un errore API invece del testo. |
| Add a Mistral model | vuoto | Digiti il nome esatto del modello dal suo account Mistral e prema **Add model**. Il nuovo nome compare nell'elenco **Model** e diventa subito il modello attivo. I nomi possono contenere lettere, cifre e i caratteri `.`, `_`, `:` e `-`. Accanto a ogni nome aggiunto c'è un link **Remove**. I modelli integrati non possono essere rimossi. |
| Max Tokens | 3200 | La risposta più lunga in token. Usi circa 256 per una meta description e 1000 o più per una descrizione HTML completa. Un valore troppo basso taglia il testo. Un valore alto costa di più. |
| Temperature | 0.7 | Con quanta libertà il modello sceglie le parole, da 0 a 1. Circa 0.2 va bene per i meta testi, circa 0.7 per le descrizioni. Modifichi Temperature oppure Top P, non entrambi. |
| Top P | 1 | Un altro modo per limitare quanto può essere sorprendente la parola successiva, da 0 a 1. Lasci 1 se imposta Temperature. |
| Frequency Penalty Value | 0 | Da -2 a 2. Un valore positivo come 0.3 – 0.6 riduce le frasi ripetute all'interno di una risposta. |
| Presence Penalty Value | 0 | Da -2 a 2. Un valore positivo distribuisce il testo su più punti. Alcuni modelli lo ignorano. |

I modelli integrati sono: mistral-small-latest, mistral-medium-latest, mistral-large-latest, ministral-8b-latest, ministral-3b-latest, codestral-latest e open-mistral-nemo.

Se Mistral rifiuta una delle impostazioni numeriche per un dato modello, il modulo lo ricorda, omette quell'impostazione per quel modello e riprova. Non deve fare nulla.

Il campo del nome del modello deve contenere almeno 3 caratteri al salvataggio, altrimenti la pagina mostra "OpenAi Model field is invalid!". La conferma dopo il salvataggio è "OpenAi Settings Updated". I messaggi "Model added.", "Model removed." e "That model is already built in." appartengono ai pulsanti di aggiunta e rimozione.

### 3.6 Settings – Studio

![Settings – Studio](https://mypresta.eu/docs/images/docs/myaimistral-settings-studio.webp)

Studio viene applicato sopra ogni prompt, ovunque abbia origine la richiesta: pagina del prodotto, pagine Generate, cron, Playground o barra superiore. I campi vuoti vengono ignorati.

| Campo | Predefinito | Che cosa fa |
|---|---|---|
| Brand voice | vuoto | Un breve brief che dice al modello chi sta parlando, per esempio "specialist workshop, short sentences, no hype". |
| Audience | vuoto | Il lettore per cui scrivere, per esempio "professional installers". |
| Tone | vuoto | Il tono della formulazione. Bastano una o due parole. |
| Glossary | vuoto | Nomi di marchi, materiali e grafie che il modello deve copiare esattamente. Un termine per riga. |
| Forbidden words | vuoto | Parole e frasi che non devono comparire in una risposta salvata. Una per riga. Usato solo quando Quality gate è Enabled. |
| Monthly generation budget | 0 | Il massimo di generazioni riuscite consentite nel mese di calendario corrente. 0 significa nessun limite. Il contatore ricomincia il primo giorno del mese. Quando il numero viene raggiunto, la generazione si ferma con un messaggio di budget. Le chiamate fallite non vengono contate. |
| Quality gate | Enabled | Controlla ogni risposta rispetto a Forbidden words prima di salvare qualsiasi cosa. Una risposta che contiene una parola in elenco viene rifiutata, non viene scritta nel prodotto e viene memorizzata in History come errore. Con Disabled, la risposta viene salvata comunque. |

Faccia clic su **Save studio**. La conferma è "Studio settings saved.".

### 3.7 Settings – Prompt templates

![Settings – Prompt templates](https://mypresta.eu/docs/images/docs/myaimistral-settings-templates.webp)

Un modello di prompt è un'istruzione salvata. La pagina mostra l'elenco **Prompt Templates** con un pulsante per crearne uno nuovo.

#### L'elenco

| Colonna | Che cosa mostra |
|---|---|
| ID | Numero del modello. |
| Title | Il nome che vede negli elenchi dei modelli. |
| Prompt | Il testo dell'istruzione. |
| Status | Faccia clic sull'icona per attivare o disattivare un modello. |
| Timestamp | Ora di creazione. |

Ogni riga ha **Edit** e **Delete**. Selezioni più righe e usi il **Delete** multiplo per rimuoverle. I modelli più recenti sono in alto.

#### Il modulo "Generate Prompt Template"

| Campo | Predefinito | Che cosa fa |
|---|---|---|
| Status | non impostato | I modelli attivati vengono proposti nel pannello del prodotto, nella pagina Generate – Products e nella barra superiore. Quelli disattivati restano nella tabella ma non vengono proposti lì. Scelga **Enabled** prima di salvare, perché un nuovo modello parte senza una scelta. |
| Prompt title | vuoto | Il nome mostrato nei menu a tendina. Non viene inviato al modello. Obbligatorio. |
| Prompt content | vuoto | L'istruzione inviata al modello. I segnaposto tra parentesi graffe vengono sostituiti per ogni elemento prima dell'invio. Le virgolette doppie vengono sostituite con virgolette semplici al salvataggio. Obbligatorio. |

Faccia clic su **Save Prompt**. Le conferme sono "Prompt template successfully added!", "Prompt template successfully updated!" e "Prompt template removed.". **Go Back to Module Settings** riporta all'elenco.

#### Segnaposto (placeholders)

| Segnaposto | Sostituito con | Funziona in |
|---|---|---|
| {product_name} | Nome del prodotto | Generazione di prodotti |
| {product_description} | Descrizione lunga | Generazione di prodotti |
| {product_description_short} | Descrizione breve | Generazione di prodotti |
| {product_tags} | Tag attuali | Generazione di prodotti |
| {product_reference} | Riferimento | Generazione di prodotti |
| {product_ean13} | Codice EAN-13 | Generazione di prodotti |
| {product_weight} | Peso | Generazione di prodotti |
| {product_brand} | Nome del marchio | Generazione di prodotti |
| {product_default_category} | Nome della categoria predefinita | Generazione di prodotti |
| {product_category_description} | Descrizione della categoria predefinita | Generazione di prodotti |
| {product_categories} | Nomi di tutte le categorie del prodotto | Generazione di prodotti |
| {product_attributes} | Attributi della combinazione (gruppo e valore) | Generazione di prodotti |
| {product_features} | Nomi delle caratteristiche | Generazione di prodotti |
| {product_feature_values} | Caratteristiche con i loro valori | Generazione di prodotti |
| {product_images} | Indirizzi delle foto del prodotto | Generazione di prodotti |
| {category_name} | Nome della categoria | Generazione di categorie |
| {category_description} | Descrizione della categoria | Generazione di categorie |
| {category_parent_name} | Nome della categoria superiore | Generazione di categorie |
| {shop_name} | Nome del negozio | Generazione di prodotti e di categorie |
| {shop_url} | Dominio del negozio | Generazione di prodotti e di categorie |
| {shop_language} | Nome della lingua | Generazione di prodotti e di categorie |
| {shop_country} | Paese predefinito | Generazione di prodotti e di categorie |
| {shop_currency} | Codice della valuta predefinita | Generazione di prodotti e di categorie |

"Generazione di prodotti" indica il pannello del prodotto, Generate – Products e il cron dei prodotti. "Generazione di categorie" indica Generate – Categories e il cron delle categorie. I segnaposto non vengono sostituiti nel Playground e nella finestra della barra superiore, perché lì non è selezionato alcun prodotto o categoria. Un segnaposto senza dati viene sostituito con un testo vuoto.

#### I 16 modelli forniti con il modulo

| N. | Titolo | Scopo |
|---|---|---|
| 1 | Product name 1 | Un nome più corto e migliore basato sul nome attuale. |
| 2 | Product name 2 | Un titolo di vendita che usa il marchio e la categoria predefinita. |
| 3 | Product description 1 | Descrizione HTML con tre titoli e i tag in grassetto. |
| 4 | Product description 2 | Descrizione in tre sezioni semplici. |
| 5 | Product description 3 | Un lungo brief SEO che chiede anche idee per i titoli, parole chiave e meta testi. |
| 6 | Product description 4 | Una breve richiesta di "descrizione accattivante". |
| 7 | Product description 5 | Descrizione che usa i tag del prodotto come parole chiave. |
| 8 | Product description 6 | Descrizione che usa il marchio e la categoria predefinita. |
| 9 | Product description 7 - using product images | Descrizione che incorpora le foto del prodotto tramite {product_images}. |
| 10 | Product meta title 1 | Meta title SEO, fino a 60 caratteri. |
| 11 | Product meta title 2 | Una seconda variante di meta title. |
| 12 | Product meta title 3 | Meta title che include il marchio. |
| 13 | Product meta description 1 | Meta description SEO, fino a 160 caratteri. |
| 14 | Product meta description 2 | Una seconda variante; il testo di esempio cita uno smartwatch. |
| 15 | Product meta description 3 | Lo stesso testo del numero 14. |
| 16 | Product tags | Cinque tag su una riga, separati da virgole. |

Legga e adatti i modelli prima di usarli su prodotti reali:

- Il modello 3 chiede al modello di aggiungere alcuni errori di ortografia al testo. Elimini quella frase.
- Il modello 5 restituisce più di una descrizione (idee per i titoli, un elenco di parole chiave e meta testi). Lo usi come ispirazione, non per salvare direttamente nel campo della descrizione.
- I modelli 5, 10, 13 e 16 chiedono una risposta in inglese. Modifichi quella riga se il suo negozio usa un'altra lingua.
- I modelli 14 e 15 sono scritti per uno smartwatch. Sostituisca l'esempio prima di usarli.

### 3.8 Settings – Playground

![Settings – Playground](https://mypresta.eu/docs/images/docs/myaimistral-settings-playground.webp)

Il Playground invia un prompt libero al modello attivo e stampa la risposta sotto il pulsante. La risposta resta in questa pagina. Non viene salvato alcun prodotto o categoria.

| Elemento | Predefinito | Che cosa fa |
|---|---|---|
| Prompt box | vuoto | L'istruzione per questa singola chiamata. Le regole di Studio vengono aggiunte. |
| Generate | – | Invia il prompt. Durante l'attesa, l'area della risposta mostra "Working…". |
| Answer area | – | La risposta del modello con il numero di token usati. |

Messaggi: "Write a prompt first." (la casella è vuota) e "The request timed out or the shop blocked it." (vedere la sezione 5.2).

La richiesta viene registrata in History come ogni altra.

### 3.9 Generate – Products

![Generate – Products](https://mypresta.eu/docs/images/docs/myaimistral-generate-products.webp)

Apra **Generate** e resti su **Products**. Il lavoro si svolge in due passaggi: costruire un elenco, poi eseguire la generazione su di esso.

#### Passaggio 1 – costruire l'elenco ("Filter products to update")

In questo passaggio non viene inviato nulla al modello. I filtri partono con i valori seguenti ogni volta che apre la pagina.

| Campo | Predefinito | Che cosa fa |
|---|---|---|
| Product Categories | nessuna selezionata | Albero delle categorie. Vengono elencati solo i prodotti che si trovano in una categoria selezionata, o che la hanno come categoria predefinita. Lasci l'albero vuoto per ignorare la categoria. |
| Brand | Select brand (all) | Solo i prodotti di un marchio. |
| Product status | Active | **Active**, **Disabled** o **Both**. |
| Product stock | All products | **All products** o **Only in stock products**. |
| Update only | Update all | Usa History: **Products that have not been updated with OpenAi content** elenca i prodotti senza riga in History, **Products that already have been updated with OpenAi content** elenca i prodotti con una riga, **Update all** ignora History. La parola "OpenAi" nelle prime due scelte è una vecchia etichetta; indica questo modulo. Conta una riga di qualsiasi stato, anche fallita. |
| Product IDs | vuoto | ID dei prodotti separati da virgole, per esempio 12,45,103. Digiti solo cifre e virgole. |
| Product Reference | vuoto | Uno o più riferimenti separati da virgole. Il riferimento deve corrispondere esattamente. |
| Product Add Date From | vuoto | Solo i prodotti creati dopo questa data e ora. |
| Product Add Date To | vuoto | Solo i prodotti creati prima di questa data e ora. |
| Minimum product ID | vuoto | L'ID prodotto più piccolo nell'elenco. |
| Maximum product ID | vuoto | L'ID prodotto più grande nell'elenco. |
| Product Limit | vuoto | Il massimo di prodotti da caricare. Usi un numero piccolo come 20 su un catalogo grande. |

Faccia clic su **Go to next step**. Il pulsante **Module settings** accanto è una vecchia scorciatoia e non apre le impostazioni di questo modulo.

#### Passaggio 2 – eseguire la generazione ("Mass product generation")

| Campo | Predefinito | Che cosa fa |
|---|---|---|
| Template | Choose a template | Copia un modello attivato nella casella del prompt. Il titolo in sé non viene inviato. |
| Prompt box | vuoto | L'istruzione inviata per ogni prodotto, con i segnaposto sostituiti prodotto per prodotto. Se la casella è vuota, per ogni campo viene usato un brief standard. |
| What to generate | Descriptions | **Descriptions** (descrizione lunga e breve), **Meta title and meta description** oppure **Descriptions and meta together** (tutti e quattro). Ogni campo è una richiesta a sé. |
| Existing text | Replace | **Replace** sovrascrive il testo. **Skip if filled** lascia in pace un campo già compilato e non chiama il modello per esso. **Add above** e **Add below** mantengono il vecchio testo e vi accodano il nuovo. |
| Languages | la lingua del suo back office selezionata | Selezioni ogni lingua da scrivere. Ogni lingua selezionata è una richiesta in più per campo. |

Faccia clic su **Run on the list below**. La tabella elenca i prodotti per ID e riferimento. L'esecuzione passa uno per uno attraverso ogni prodotto, campo e lingua. La riga sopra il pulsante mostra l'avanzamento, per esempio "3 / 120 – description", e la colonna **Result** mostra la risposta per ogni passaggio. "skipped" significa che il campo aveva già del testo e che ha scelto **Skip if filled**. Al termine la riga riporta "Finished N products.".

Non può deselezionare singoli prodotti nella tabella. Modifichi il filtro del passaggio 1 per cambiare l'elenco. Nomi e tag non fanno parte di questa esecuzione; usi la pagina di modifica del prodotto o cron. Il testo viene salvato man mano che arriva ogni risposta. Chiudere la pagina interrompe l'esecuzione, e i prodotti già elaborati mantengono il nuovo testo.

### 3.10 Generate – Categories

![Generate – Categories](https://mypresta.eu/docs/images/docs/myaimistral-generate-categories.webp)

Apra **Generate** e passi a **Categories**.

#### Passaggio 1 – costruire l'elenco ("Filter categories to update")

| Campo | Predefinito | Che cosa fa |
|---|---|---|
| Categories | nessuna selezionata | Selezioni le categorie da elencare. Senza alcuna selezione, l'elenco contiene ogni categoria che corrisponde allo stato, comprese Root e Home. Selezioni categorie specifiche per evitarlo. |
| Category status | Active | **Active**, **Disabled** o **Both**. |

Faccia clic su **Go to next step**.

#### Passaggio 2 – eseguire la generazione ("Mass category generation")

| Campo | Predefinito | Che cosa fa |
|---|---|---|
| Prompt box | vuoto | L'istruzione inviata per ogni categoria. Usi {category_name}, {category_description}, {category_parent_name} e i segnaposto del negozio. In questa pagina non c'è un elenco di modelli. |
| Field | Description | Il campo da scrivere: **Description**, **Name**, **Meta title**, **Meta description** o **Additional description**. Viene salvato solo quel campo. |
| Existing text | Replace | **Replace** o **Skip if filled**. |
| Language | la lingua del suo back office | Una lingua. Esegua di nuovo per un'altra lingua. |

Faccia clic su **Run on the categories below**. La tabella elenca gli ID delle categorie e mostra un risultato per ciascuna.

Se la casella del prompt è vuota, per descrizione, meta title e meta description viene usato un brief standard. Per **Name** e **Additional description** verrebbe usato il brief della descrizione, quindi per questi due campi scriva sempre un suo prompt.

Sotto l'elenco la pagina mostra anche il vecchio modulo **Generate category content** con il suo pulsante **Generate content**. Non genera nulla. Usi il pulsante di esecuzione sopra di esso.

### 3.11 New product

![New product](https://mypresta.eu/docs/images/docs/myaimistral-new-product.webp)

**New product** chiede al modello una bozza completa di prodotto e può inserirla nel catalogo.

| Campo | Predefinito | Che cosa fa |
|---|---|---|
| What is the product? | vuoto | Qualche frase: che cos'è il prodotto, materiali, pubblico, nomi da mantenere. Un brief più ricco dà una bozza più vicina. Una casella vuota viene rifiutata. |
| Optional source URL | vuoto | Un indirizzo http o https completo di una pagina pubblica. Il suo testo leggibile viene aggiunto al brief. Una pagina che il negozio non riesce a leggere viene ignorata. |
| Language | lingua predefinita del negozio | La lingua in cui vengono salvati nome, descrizioni, meta e tag. Le altre lingue non vengono compilate. |
| Default category ID | 2 | Il numero della categoria da **Catalog > Categories**. 2 di solito è Home. Il prodotto viene collocato lì. |

Pulsanti:

- **Generate data** mostra la bozza come testo semplice nella casella sotto i pulsanti. Non salva nulla. La bozza contiene nome, descrizioni, meta testi, tag, riferimento, un prezzo suggerito e caratteristiche.
- **Create product** inserisce l'ultima bozza generata. Il nuovo prodotto è **attivo**, ha una giacenza di **100**, usa il primo gruppo di regole fiscali del negozio ed è collocato nella categoria che ha digitato. Dopo il successo la casella mostra "Product #" e il numero del nuovo prodotto.

La bozza non può essere modificata in questa pagina. Controlli poi nel prodotto prezzo, imposta, foto e categoria; il prezzo è quello suggerito dal modello e può essere 0. La pagina mostra "Add an API key in the module settings first." quando non è salvata alcuna chiave.

### 3.12 Cron

![Cron](https://mypresta.eu/docs/images/docs/myaimistral-cron.webp)

Cron permette al suo server di aggiornare alcuni prodotti o categorie ogni volta che un pianificatore apre un indirizzo. La pagina mostra: il pannello **Category cron**, il modulo **CRON JOB Settings - Generate product content using Mistral AI**, il modulo **CRON JOB Settings - Generate category content using Mistral AI** e il pannello **Cron parameters**. I moduli si limitano a costruire e salvare impostazioni; nulla viene eseguito finché il suo server non chiama l'indirizzo.

#### L'indirizzo cron

L'indirizzo dei prodotti ha questo aspetto:

```text
https://YOUR-SHOP.EXAMPLE/module/myaimistral/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent
```

L'indirizzo delle categorie ha questo aspetto:

```text
https://YOUR-SHOP.EXAMPLE/module/myaimistral/cron?secret=YOUR_CATEGORY_SECRET&action=generateCategoryContent
```

- Sostituisca `YOUR-SHOP.EXAMPLE` con l'indirizzo del suo negozio.
- Sostituisca il segreto con il **Cron Job Secret Token** del modulo corrispondente. Non lo pubblichi mai.
- La parte `&action=generateProductContent` o `&action=generateCategoryContent` è obbligatoria. Senza di essa l'indirizzo risponde "Invalid action!".
- I pannelli nella pagina mostrano l'indirizzo solo fino al segreto. Il pannello delle categorie aggiunge `&entity=category`, che il negozio non usa. Aggiunga lei stesso la parte `action` come mostrato sopra.
- La riga "Command:" all'interno di ogni modulo mostra solo l'indirizzo semplice, senza segreto e senza azione. Costruisca lei stesso l'indirizzo completo.

#### Modulo dei prodotti

| Campo | Predefinito | Che cosa fa |
|---|---|---|
| Enable Cron Feature | No | L'interruttore generale sia per il cron dei prodotti sia per quello delle categorie. Con No, ogni indirizzo cron risponde che la funzione è disattivata. |
| Cron Job Secret Token | casuale, 32 caratteri | La password nell'indirizzo dei prodotti. Deve avere almeno 24 caratteri. Un segreto più corto viene sostituito con uno casuale al caricamento della pagina del modulo. |
| Update Field | description | Un campo per voce del pianificatore: name, description, description_short, meta_title, meta_description o tags. Per compilare più campi, crei più voci. |
| Selected Products | pendingMistral | Quali prodotti sono ancora in attesa. **pendingMistral** prende i prodotti che non hanno alcuna riga riuscita in History per nessun campo. **pendingField** prende i prodotti senza una riga riuscita per il campo scelto, così più voci possono compilare campi diversi degli stessi prodotti. **emptyField** prende i prodotti il cui campo scelto è vuoto nella lingua scelta. |
| Product Categories | nessuna selezionata | Limita l'esecuzione ai prodotti nelle categorie selezionate. Vedere l'avviso più sotto. |
| Product ID list | vuoto | Un elenco fisso di ID prodotto separati da virgole. Le lettere vengono scartate al salvataggio. |
| Language | lingua predefinita del negozio | La lingua da scrivere. Le altre lingue richiedono una propria voce. |
| Product to update | 5 products | Quanti prodotti elaborare per chiamata: 2, 3, 5, 8, 10, 15, 20, 50, 100, 200, 300, 500 o 1000. Inizi con 5 o 10 in modo che un modello lento non raggiunga il limite di tempo del server. |
| Prompt Template | primo modello dell'elenco | L'istruzione salvata usata per ogni prodotto. Vedere la nota più sotto. |
| Enable Debug | No | Con Yes, l'indirizzo stampa ciò che farebbe e non salva nulla. |
| CRON JOB interval | Every Hour | Un promemoria di ogni quanto prevede di chiamare l'indirizzo (da ogni minuto a ogni 6 ore). Il modulo non avvia nulla da solo. |

Faccia clic su **Save**. L'elenco di **Prompt Template** non ha una scelta vuota e mostra ogni modello salvato, anche quelli disattivati, dal più recente. Finché non ne ha salvato uno, il modulo mostra il modello più recente (Product tags). Scelga sempre il modello che desidera e salvi, altrimenti viene salvato quello mostrato.

Avviso: quando **Product Categories** ha categorie selezionate, il negozio sceglie anche i prodotti la cui categoria predefinita è selezionata, anche se erano già stati elaborati. Il cron può quindi riscrivere a ogni chiamata gli stessi primi prodotti. Lasci vuoto l'albero delle categorie e usi invece **Product ID list**.

#### Modulo delle categorie

| Campo | Predefinito | Che cosa fa |
|---|---|---|
| Cron Job Secret Token | casuale, 32 caratteri | La password nell'indirizzo delle categorie. Almeno 24 caratteri. |
| Update Field | description | name, description, meta_title o meta_description. |
| Selected categories | pendingMistral | **pendingMistral**, **pendingField** o **emptyField**, con lo stesso significato dei prodotti. |
| Language | lingua predefinita del negozio | La lingua da scrivere. |
| Categories to update | 5 categories | Quante categorie per chiamata (stesse scelte dei prodotti). |
| Prompt Template | primo modello dell'elenco | L'istruzione salvata. La scriva per una categoria, non per un prodotto. |
| Enable Debug | No | Con Yes, l'indirizzo stampa il piano e non salva nulla. |
| CRON JOB interval | Every Hour | Solo un promemoria. |

Faccia clic su **Save** sotto il modulo. Root e Home non vengono mai elaborate dal cron delle categorie. L'interruttore **Enable Cron Feature** si trova nel modulo dei prodotti e controlla anche il cron delle categorie.

#### Segreti e "Generate Token"

Se desidera un nuovo segreto, lo digiti a mano nel campo, almeno 24 caratteri, lettere e cifre. Il pulsante **Generate Token** potrebbe non compilare il campo in questa versione, quindi non faccia affidamento su di esso. Dopo aver salvato un nuovo segreto, lo cambi anche nel suo pianificatore, perché il vecchio indirizzo smette di funzionare. Ciascuno dei due segreti apre ciascuna delle due azioni, quindi tenga privati entrambi.

#### Configurare il pianificatore

Su un server Linux aggiunga al crontab una riga come questa (ogni ora):

```text
0 * * * * curl -s -o /dev/null "https://YOUR-SHOP.EXAMPLE/module/myaimistral/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent"
```

Tenga l'indirizzo tra virgolette, perché contiene il carattere `&`. Su Windows usi l'Utilità di pianificazione con `curl.exe` e lo stesso indirizzo. I pannelli degli hosting con una schermata "cron job" accettano lo stesso comando.

#### Provare in sicurezza

1. Salvi il modulo con **Enable Cron Feature** su Yes e **Enable Debug** su Yes.
2. Apra l'indirizzo completo in un browser. Vedrà le impostazioni lette, la query e il prompt finale, e non viene salvato nulla.
3. Imposti **Enable Debug** su No, salvi e riapra l'indirizzo. La pagina risponde ora con un breve testo come "5 products have been updated.".

Se **Enable Debug** resta attivo, le chiamate pianificate non salvano nulla. È il motivo più comune per cui un cron "non fa niente".

Il testo salvato viene tagliato alla lunghezza consentita da PrestaShop: nome 128, descrizione breve 799, meta title 69 e meta description 159 caratteri. Il vecchio testo viene mantenuto in History, quindi può ripristinarlo dalla pagina del prodotto.

### 3.13 History

![History](https://mypresta.eu/docs/images/docs/myaimistral-history.webp)

Ogni richiesta a Mistral AI viene scritta in History con la sua istruzione, la sua risposta o l'errore, il modello, il numero di token e il tempo impiegato.

#### Filtri e totali

| Elemento | Predefinito | Che cosa fa |
|---|---|---|
| Period buttons | This month | Today, 7 days, 30 days, This month, All time. |
| From / To | compilato dal periodo | Un intervallo personalizzato. |
| Model | Any | Solo un modello. |
| Type | Any | Solo un tipo di richiesta, per esempio product_description o category_meta_title. |
| Status | Any | Success o Error. |
| Language | Any | Solo una lingua. |
| Employee | Any | Solo le richieste fatte da un dipendente. |
| Product / category ID | vuoto | Solo le richieste per quel record. |
| Prompt or reply contains | vuoto | Una parola cercata nell'istruzione e nella risposta. |
| Filter | – | Applica i filtri. |

Le schede mostrano Requests, Success, Errors, Tokens sent, Tokens received, Tokens total e Average time. Un trattino significa che Mistral non ha restituito un conteggio dei token per quella chiamata. Sotto le schede ci sono le tabelle **By day**, **By model**, **By type**, **By language** e **By employee** con le colonne Group, Calls, Sent, Received e Total. Un piccolo numero accanto a Calls è il numero di errori di quel gruppo.

#### L'elenco "Prompt history"

L'elenco segue i filtri e mostra 50 righe per pagina.

| Colonna | Che cosa mostra |
|---|---|
| ID | Numero della riga del log. |
| Status | Success o Error. |
| Prompt | La prima parte dell'istruzione. |
| Reply / Error | La prima parte della risposta, oppure il testo dell'errore. |
| Provider | Il nome del provider, il modello, il codice HTTP e il tempo in secondi, separati da punti. Il nome del provider riporta ancora "openai". |
| Sent / Received / Total | Token. |
| Entity ID | Il prodotto o la categoria a cui era destinata la richiesta. |
| Type | Il tipo di richiesta. |
| Timestamp | Quando è stata fatta la richiesta. |

Faccia clic su **View** su una riga per leggere il prompt e la risposta completi. **Back to the list** riporta all'elenco.

**Clear list** (barra degli strumenti) elimina tutte le righe, non solo quelle filtrate, e mostra "Log list successfully deleted.". Reimposta inoltre le informazioni che cron usa per sapere quali elementi sono già stati aggiornati (gli obiettivi "pending" ripartono dall'inizio), azzera il contatore del budget mensile e rimuove i testi precedenti necessari per **Restore**. Non è possibile annullare.

### 3.14 Images

![Images](https://mypresta.eu/docs/images/docs/myaimistral-images.webp)

La pagina **AI Image Finder** contiene le stesse due impostazioni della parte finale di Settings – General. Salvarle non scarica alcuna immagine e non cambia alcun testo.

| Campo | Predefinito | Che cosa fa |
|---|---|---|
| AI Image Finder | Enabled | Mostra o nasconde la ricerca foto nella pagina di modifica del prodotto. |
| AI Image Search Prompt | Istruzione integrata | L'istruzione inviata quando qualcuno cerca foto. `{product_name}` e `{product_description}` vengono sostituiti con il prodotto corrente. Il testo integrato chiede esattamente 5 indirizzi di pagina come elenco JSON. Modifichi la formulazione se preferisce i siti dei produttori. Un prompt vago restituisce link non pertinenti. |

Faccia clic su **Save**. La conferma è "Settings saved.".

Come funziona: il modello suggerisce pagine web che probabilmente mostrano il prodotto, il modulo apre quelle pagine ed elenca le foto che trova, e lei seleziona le foto da importare. Il modulo non verifica di chi siano le foto. Usi solo foto che ha il diritto di usare.

### 3.15 Updates

![Updates](https://mypresta.eu/docs/images/docs/myaimistral-updates.webp)

| Elemento | Predefinito | Che cosa fa |
|---|---|---|
| Manual Check – Check Now | – | Chiede una volta al server degli aggiornamenti l'ultima versione. La risposta è "Module is up to date!" o "New version available!". |
| Automatic Notifications | Enabled | Circa ogni tre giorni il modulo controlla in background. Quando esiste una versione più recente, i dipendenti vedono un banner di avviso nel back office. Scelga Disabled per gestire gli aggiornamenti a mano. |
| Product Page | – | Un link alla pagina del modulo. |

Faccia clic su **Save**. La conferma è "Update settings saved.". Il controllo invia a MyPresta.eu il nome del modulo, la sua versione e l'indirizzo del suo negozio.

### 3.16 Pagina di modifica del prodotto

![Product edit page – My AI Mistral tab](https://mypresta.eu/docs/images/docs/myaimistral-product-edit.webp)

Apra **Catalog > Products**, modifichi un prodotto esistente e apra la scheda **Modules**. Scelga **My AI Mistral**. La scheda ha le sottoschede **Generate**, **Simulate**, **Photos** e **History**. Le prime tre compaiono quando **Product edit page Form** è Enabled; **History** compare quando **Product Edit History** è Enabled.

#### Controlli condivisi da Generate e Simulate

| Elemento | Predefinito | Che cosa fa |
|---|---|---|
| Language | prima lingua | Faccia clic su una lingua, oppure su **Every language** per scriverle tutte una dopo l'altra. |
| If the field already has text | Replace | **Replace**, **Add above**, **Add below** o **Skip if filled**. Mostrato solo nella sottoscheda Generate. |
| Use your own instruction or a saved prompt | chiuso | Apre una casella di filtro e dei riquadri: **Standard brief** e ogni modello attivato. Faccia clic su un riquadro per usarlo. |
| Instruction | vuoto | Il suo testo. Quando è vuoto, viene usato il brief standard del campo di cui preme il pulsante. I segnaposto vengono sostituiti per questo prodotto. |

La casella Instruction conserva il testo dell'ultima esecuzione. Dopo aver premuto un pulsante, la casella mostra il brief usato, e il pulsante successivo lo riutilizza. Svuoti la casella prima di premere il pulsante di un altro campo.

#### Generate

Ogni scheda ha un pulsante **Fill**: **Description** ("The long text on the product page, with a short intro and a feature list."), **Short description**, **Name**, **Meta title**, **Meta description** e **Tags**. Il testo viene **salvato subito sul prodotto** e mostrato sotto le schede con il numero di token. La scheda **SEO pack** ha il pulsante **Fill all**; compila il nome, entrambe le descrizioni ed entrambi i campi meta in una sola richiesta e risponde "SEO pack saved. Refresh the product to see it.".

Importante: il modulo del prodotto aperto nel suo browser contiene ancora i vecchi testi. Ricarichi la pagina del prodotto prima di fare clic su **Save** in PrestaShop, altrimenti i vecchi testi sovrascrivono i nuovi.

#### Simulate

Le stesse schede con il pulsante **Try**. Il testo viene mostrato nella pagina e il prodotto non viene modificato. Lo usi per confrontare prompt e modelli prima che il modulo scriva.

#### Photos

![Photos sub-tab](https://mypresta.eu/docs/images/docs/myaimistral-product-photos.webp)

1. Faccia clic su **Find pages**. Il modello suggerisce pagine che probabilmente mostrano il prodotto, e il modulo elenca le foto trovate su di esse.
2. Selezioni le foto che desidera. Il messaggio dice "Tick the photos you want, then add them to this product.".
3. Faccia clic su **Add selected to this product**. Le foto vengono scaricate e collegate al prodotto. Il messaggio dice "Done. Reload the product to see the new photos." oppure indica il numero aggiunto.

Quando la ricerca è disattivata, la scheda lo segnala e rimanda a Settings – General. Altri messaggi: "No photos were found on the suggested pages.", "The search failed." e "The photos could not be added.".

#### History

Una tabella con **When**, **Type**, **Status** e un pulsante **Restore** per le ultime 50 richieste del prodotto. **Restore** chiede "Restore the previous value?", rimette il testo precedente e risponde "Content successfully restored. Refresh this page to see changes.". Il pulsante viene mostrato solo per le modifiche riuscite che hanno conservato un testo precedente. Se non ce n'è nessuna, la pagina dice "No generations for this product yet.".

### 3.17 Pulsanti "Generate with AI" accanto ai campi

Nella pagina di modifica del prodotto un piccolo pulsante con il logo Mistral si trova accanto agli editor di **Description**, **Short description**, **Meta title** e **Meta description**. Nella pagina di modifica della categoria si trova accanto a **Description**, **Additional description**, **Meta title** e **Meta description**.

1. Faccia clic sul pulsante. Se il negozio ha più di una lingua, scelga **Current language**, **All languages** o **Cancel**.
2. Attenda. Il pulsante mostra uno stato di occupato mentre la richiesta è in corso.
3. Il testo compare nel campo. Faccia clic su **Save** sul prodotto o sulla categoria per mantenerlo. Prima di allora non viene salvato nulla.

Il record deve già esistere. Su un nuovo prodotto il pulsante risponde "Save the product once before generating." e su una nuova categoria "Save the category once before generating.". Gli errori compaiono in una finestra di messaggio, per esempio "Generation failed.".

Questi pulsanti usano sempre il brief standard del campo, non i suoi modelli. Le regole della casa, il budget e il controllo qualità di Studio e il modello di Settings continuano ad applicarsi.

### 3.18 Altre scorciatoie

| Posizione | Che cosa fa |
|---|---|
| Icona a bacchetta nella barra superiore | Apre una piccola finestra: **Template** facoltativo, una casella di testo e **Generate**. La risposta viene mostrata nella finestra; la copi dove le serve. Non viene salvato nulla e i segnaposto non vengono sostituiti. Nasconda l'icona con **Admin Top Bar CTA** in Settings – General. |
| Elenco dei prodotti | Un pulsante **My AI Mistral** accanto alle azioni di massa o alla barra degli strumenti di **Catalog > Products** apre la pagina Generate. |
| PrestaShop Dashboard | Un piccolo pannello con le scorciatoie **Mass content**, **Log** e **Cron** e il link al supporto di MyPresta.eu. |

## 4. Front del negozio

My AI Mistral non ha alcuna parte visibile ai clienti. Non aggiunge blocchi, pagine, script o stili alle pagine del suo negozio, e i clienti non possono vedere che il modulo esiste. I suoi due indirizzi front sono usati solo dal back office e dal suo pianificatore.

### 4.1 Indirizzi

| Indirizzo | Usato da | Che cosa fare |
|---|---|---|
| /module/myaimistral/cron | Il suo pianificatore (sezione 3.12) | Lo chiami con il segreto e l'azione come mostrato nella sezione 3.12. |
| /module/myaimistral/ajax | I pulsanti nel back office | Non lo chiami a mano e non lo inserisca in un pianificatore. |

### 4.2 Che cosa risponde l'indirizzo cron

L'indirizzo risponde con testo semplice. Un'esecuzione si ferma al primo errore; gli elementi già completati restano salvati.

| Risposta | Significato | Che cosa fare |
|---|---|---|
| Cron Job feature is disabled. You can enable it from the module settings. | **Enable Cron Feature** è su No. | Lo imposti su Yes e salvi. |
| The token does not exist or it's wrong! | Il segreto manca, è sbagliato o è vecchio. | Copi il segreto attuale del modulo. |
| Invalid action! | La parte `action` manca o è scritta male. | Aggiunga `&action=generateProductContent` o `&action=generateCategoryContent`. |
| updatedField parameter is wrong! | Il campo non è tra quelli consentiti. | Scelga di nuovo il campo e salvi il modulo. |
| All must include all mandatory parameters! | Un'impostazione salvata è vuota. | Salvi di nuovo il modulo, con una lingua e un modello scelti. |
| productTarget parameter is wrong! Allowed values: … | Il valore dell'obiettivo è sconosciuto. | Scelga di nuovo **Selected Products**. Lo stesso vale per il modulo delle categorie. |
| No valid product IDs provided. | **Product ID list** contiene testo ma nessun numero valido. | Corregga o svuoti l'elenco. |
| No products to update. / No categories to update. | Nulla corrisponde alle impostazioni. | Cambi i filtri o l'obiettivo, oppure consideri il lavoro finito. |
| 5 products have been updated. / 5 categories have been updated. | L'esecuzione è terminata. Il numero è il conteggio. | Controlli i dettagli in History. |
| 5 pending products. | Debug è attivo; non è stato salvato nulla. | Imposti **Enable Debug** su No. |
| Error! followed by a text | Il provider ha restituito un errore. | Legga il testo, vedere la sezione 5.2. |
| Error! The model returned an empty response. | Mistral non ha inviato testo. | Aumenti **Max Tokens** o cambi modello di prompt. |
| Error! Could not save product 12: … | PrestaShop ha rifiutato il testo per quel prodotto. | Legga il motivo che segue; l'esecuzione si è fermata lì. |

## 5. Problemi

### 5.1 Installazione e menu

| Sintomo | Causa | Che cosa fare |
|---|---|---|
| Il programma di installazione dice che il modulo richiede PHP 7.0 o successivo | Il server esegue un PHP più vecchio. | Cambi la versione di PHP nel pannello dell'hosting e reinstalli. |
| "Could not create the module database tables." | L'utente del database non può creare tabelle. | Conceda all'utente questo diritto o si rivolga al suo hosting. |
| Manca la voce di menu AI Content Generator | Vecchia cache, il modulo è disattivato, oppure il profilo del dipendente non ha il permesso. | Svuoti la cache, attivi il modulo e controlli **Administration > Permissions** per il profilo. |
| La pagina del prodotto non ha il pannello My AI Mistral nella scheda Modules | **Product edit page Form** e **Product Edit History** sono entrambi Disabled, oppure la pagina è in cache. | Attivi l'impostazione in Settings – General e ricarichi la pagina del prodotto. |

### 5.2 Connessione a Mistral AI

| Sintomo | Causa | Che cosa fare |
|---|---|---|
| "The Mistral API key is not set. Add it in the module settings." | Non è salvata alcuna chiave. | Incolli la chiave in Settings – Mistral. |
| "Mistral AI API KEY field is invalid!" | Meno di 10 caratteri e nessuna chiave memorizzata. | Copi l'intera chiave dalla console. |
| "Mistral AI API Error (401): …" | La chiave è sbagliata, revocata o di un altro account. | Crei una nuova chiave e la incolli di nuovo. |
| "Mistral AI API Error (429): …" | È stato raggiunto un limite di Mistral. | Attenda un minuto e riprovi, usi lotti più piccoli o potenzi il suo piano. |
| "Mistral request timed out after N seconds…" | Il modello è lento o il testo è lungo. | Aumenti **API timeout (seconds)** in Settings – General o usi un modello più veloce. |
| "The request timed out or the shop blocked it." | Il server, un firewall o il front del negozio ha bloccato la richiesta. | Consenta l'HTTPS in uscita verso l'API di Mistral e renda raggiungibile l'indirizzo del front del negozio. |
| Il modello non viene trovato | Un nome di modello che il suo account Mistral non può usare. | Scelga un altro modello dall'elenco. |
| L'elenco Model è passato a gpt-4o dopo aver rimosso un modello | Il modulo ripiega su un vecchio nome predefinito. | Scelga di nuovo un modello Mistral e salvi. |
| "Error! Invalid token!" | Il segreto contenuto nella pagina aperta del back office non corrisponde più a quello nel negozio, per esempio dopo una reinstallazione. | Ricarichi la pagina. |

### 5.3 Generazione

| Sintomo | Causa | Che cosa fare |
|---|---|---|
| "Error! Content retrieve has failed! Details: …" | L'API ha restituito un errore. I dettagli lo indicano. | Legga i dettagli e la riga in History. |
| "Monthly generation budget reached. Raise it in the studio settings or wait until next month." | Il limite di Studio è esaurito. | Aumenti il budget o attenda il mese successivo. |
| "The reply was rejected because it contains a forbidden word from the studio settings." | Quality gate ha trovato una parola della sua lista. | Modifichi l'elenco o il prompt ed esegua di nuovo. |
| "The model returned an empty response." oppure "The model hit the token limit before returning any text…" | **Max Tokens** è troppo basso o il modello lo ha speso nel ragionamento. | Aumenti **Max Tokens**. |
| "The response was blocked by the provider content filter. Try rewording the prompt." | Mistral ha rifiutato il contenuto. | Riformuli il prompt. |
| "Error! Prompt is missing or too short!" | Il prompt ha meno di 4 caratteri. | Scriva un'istruzione più lunga o lasci vuota la casella. |
| Un meta title o una meta description termina bruscamente in un'esecuzione cron | Il cron taglia i meta title a 69 e le meta description a 159 caratteri. | Chieda nel prompt un testo più breve. |
| Il prodotto mostra il vecchio testo dopo la generazione | Il modulo del prodotto aperto nel browser è stato salvato sopra di esso. | Ricarichi la pagina del prodotto prima di fare clic su Save. |
| Una riga riporta "skipped" | Il campo aveva del testo e ha scelto Skip if filled. | Scelga Replace per sovrascrivere. |
| Lo stesso brief viene usato per due campi | La casella Instruction contiene ancora il brief precedente. | Svuoti la casella prima di premere un altro campo. |
| Name o Additional description riceve in Generate – Categories un testo simile a una descrizione | Il prompt vuoto usa il brief della descrizione per questi due campi. | Scriva un suo prompt. |
| "Error! This log entry has no previous value to restore." | La riga non ha conservato alcun vecchio testo, oppure l'elenco è stato svuotato. | Il modulo non può recuperare il vecchio testo. |
| "Error! This PrestaShop version does not support the category Additional Description field." | PrestaShop più vecchio. | Salti quel campo. |

### 5.4 Foto e New product

| Sintomo | Causa | Che cosa fare |
|---|---|---|
| La scheda Photos dice che la ricerca è disattivata | **AI Image Finder** è Disabled. | Lo attivi in Settings – General o Images e ricarichi la pagina del prodotto. |
| "No photos were found on the suggested pages." | Le pagine suggerite non hanno foto utilizzabili. | Faccia di nuovo clic su **Find pages** o aggiunga le foto a mano. |
| "The photos could not be added." | Il server non è riuscito a scaricarle. | Scelga altre foto. |
| "Failed to parse AI response. Please try again." | Il modello ha restituito dati che il modulo non riesce a leggere. | Faccia di nuovo clic su **Generate data** o aumenti **Max Tokens**. |
| "Generate the product first." | Si è fatto clic su **Create product** prima di **Generate data**. | Generi prima. |
| "Prompt is required" | **What is the product?** è vuoto. | Descriva il prodotto. |

### 5.5 Cron

| Sintomo | Causa | Che cosa fare |
|---|---|---|
| L'indirizzo risponde ma non cambia nulla | **Enable Debug** è su Yes. | Lo imposti su No e salvi. |
| L'indirizzo dice che la funzione è disattivata | **Enable Cron Feature** è su No. | Lo imposti su Yes. |
| Il segreto è cambiato da solo | Un segreto più corto di 24 caratteri è stato sostituito. | Copi il nuovo segreto dal modulo e aggiorni il pianificatore. |
| Gli stessi prodotti vengono riscritti ogni volta | **Product Categories** è selezionato (vedere la sezione 3.12). | Lasci vuoto l'albero delle categorie e usi **Product ID list**. |
| Il cron usa il modello sbagliato | Il modulo mostrava il modello più recente e quella scelta è stata salvata. | Scelga il **Prompt Template** giusto e salvi. |
| "Generate Token" non fa nulla | Lo script del pulsante non è fornito in questa versione. | Digiti lei stesso il nuovo segreto. |
| "Command:" nel modulo non mostra alcun segreto | Mostra solo l'indirizzo semplice. | Costruisca l'indirizzo come nella sezione 3.12. |
| L'indirizzo termina con un timeout | Troppi elementi per chiamata. | Riduca **Product to update**. |
| Dopo un po' viene rielaborato tutto | **Clear list** in History ha rimosso il log che segna gli elementi completati. | Non svuoti History mentre un cron è in esecuzione, oppure usi **Product ID list**. |

### 5.6 Testi che citano OpenAI o ChatGPT

Il modulo è stato realizzato a partire da un modulo precedente per un altro provider di IA. Alcuni testi mostrano ancora il vecchio nome. Non cambiano il funzionamento del modulo.

| Dove | Che cosa vede | Significato |
|---|---|---|
| Settings – Mistral | L'esempio di nome del modello nel campo di aggiunta è un nome GPT; i messaggi "OpenAi Settings Updated" e "OpenAi Model field is invalid!". | Solo esempi e formulazioni. Digiti il nome di un modello Mistral. |
| Generate – Products | "OpenAi content" in **Update only**. | Indica il contenuto di questo modulo. |
| Generate pages | Pulsante **Module settings**. | Una vecchia scorciatoia che non apre questo modulo. Usi la barra dei menu. |
| History | Il provider mostra "openai". | Solo un'etichetta. |

## 6. Per lo sviluppatore

### 6.1 Panoramica

| Elemento | Valore |
|---|---|
| Nome del modulo | `myaimistral` |
| Nome visualizzato | My AI Mistral - AI content generation |
| Versione | 1.0.0 |
| Classe principale | `myaimistral` (`myaimistral.php`) |
| PrestaShop | da 1.6 a 9.99.99 |
| PHP | 7.0.0 o successivo (verificato all'installazione, costante `MIN_PHP_VERSION`) |
| Base dell'API | `https://api.mistral.ai/v1` (`/chat/completions`, `/models`) |
| Prefisso di configurazione | `MYPRESTA_MYAIMISTRAL_` |
| Tabelle | `PREFIX_myaimistral_prompt`, `PREFIX_myaimistral_log` |
| Prefisso CSS | `.mam-` |
| Parametri URL | `mam_tab`, `mam_sub`, `mcg_preset`, `mam_from`, `mam_to` e `stats_*` su History |

Cartelle: `controllers/admin`, `controllers/front`, `src` (classi con caricamento automatico `OpenAIService` e `Studio` nel namespace `MyAIMistral`), `lib` (controllo aggiornamenti, aiuto di sezione, compatibilità con PrestaShop 9), `views/templates`, `views/js`, `views/css`, `translations`.

Il modulo non ha override né template front. L'aiuto dei campi è scritto con l'helper `fieldHelp($does,$how,$effect)`, che costruisce il testo "What it does / How to configure / Effect" di ogni `desc` di HelperForm.

### 6.2 Controller di amministrazione, hook e instradamento

| Classe del controller | Nome della scheda | Scopo |
|---|---|---|
| `AdminMyAIMistralMain` | AI Content Generator (menu entry) | Reindirizza a `AdminModules&configure=myaimistral`. |
| `AdminMyAIMistral` | Mass Content Creator | Pagine Generate (prodotti e categorie). |
| `AdminMyAIMistralProductCreator` | AI Product Creator | New product. |
| `AdminMyAIMistralSettings` | Module Settings | Ingresso alle impostazioni. |
| `AdminMyAIMistralCron` | Cron Job Settings | Moduli cron. |
| `AdminMyAIMistralUsage` | Module Log and Usage | History. |
| `AdminMyAIMistralImageFinder` | AI Image Finder | Pagina Images e azioni foto `searchImages`, `extractImages`, `saveImages`. |

I controller di amministrazione reindirizzano a `AdminHome` quando il modulo è inattivo.

Hook registrati all'installazione: `displayBackOfficeHeader` (risorse e valori `Media::addJsDef` come `myaimistralField`, `myaimistralAdminLink`, `mamHelpLabels`), `displayBackOfficeTop` (icona della barra superiore e menu a tendina), `displayAdminProductsExtra` e `actionProductFormBuilderModifier` (scheda del prodotto), `actionProductGridDataModifier` (elenco dei prodotti), `dashboardZoneTwo` (pannello del PrestaShop Dashboard), `displayAdminProductsMainStepLeftColumnMiddle` e `displayAdminProductsMainStepLeftColumnBottom` (vuoti), `displayHeader` e `displayFooter` (vuoti).

La navigazione all'interno della pagina del modulo usa parametri URL:

| Parametro | Valori | Significato |
|---|---|---|
| `mam_tab` | dashboard, settings, updates (pagina del modulo); le altre schede sono controller | La scheda principale nella pagina di configurazione del modulo. |
| `mam_sub` | general, openai, studio, templates, playground (settings); products, categories (Generate) | La sottoscheda. `openai` è la scheda Mistral. |
| `mcg_preset` | today, 7, 30, 90, month, all | Periodo predefinito della Dashboard. |
| `mam_from`, `mam_to` | `YYYY-MM-DD` | Intervallo personalizzato della Dashboard. |
| `stats_preset`, `stats_from`, `stats_to`, `stats_model`, `stats_type`, `stats_status`, `stats_lang`, `stats_employee`, `stats_entity`, `stats_q` | vedere History | Filtri di History. `clear_log` elimina il log. |

### 6.3 Contratto del cron

```text
GET /module/myaimistral/cron?secret=SECRET&action=generateProductContent
GET /module/myaimistral/cron?secret=SECRET&action=generateCategoryContent
```

| Regola | Comportamento |
|---|---|
| Interruttore | `MYPRESTA_MYAIMISTRAL_ENABLE_CRON` non deve essere 0. |
| Autenticazione | `secret` deve essere uguale a `SECRET` o `CAT_SECRET`. Entrambi funzionano per entrambe le azioni. |
| Sostituzioni facoltative (prodotti) | `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug`, `categories`, `productIds`. Sostituiscono i valori salvati solo per quella chiamata. |
| Sostituzioni facoltative (categorie) | `updatedField`, `categoryTarget`, `categoriesToUpdate`, `languageId`, `promptTemplateId`, `debug`. |
| Campi consentiti | Prodotti: name, description, description_short, meta_title, meta_description, tags. Categorie: name, description, meta_title, meta_description, additional_description. |
| Obiettivi | `pendingMistral`: nessuna riga di log riuscita per l'elemento. `pendingField`: nessuna riga di log riuscita di tipo `product_FIELD` o `category_FIELD`. `emptyField`: il campo è vuoto nella lingua. Le righe con stato `error` non contano. |
| Ordine e limite | `ORDER BY id ASC LIMIT n`. Le query delle categorie iniziano dopo `PS_HOME_CATEGORY`. |
| Debug | Quando `debug` è 1, vengono stampati l'SQL, gli elementi selezionati e i prompt finali e non viene salvato nulla. Un valore debug salvato pari a 1 interrompe anche il salvataggio pianificato. |
| Troncamento | name 128, descrizione breve 799, meta title 69, meta description 159. I tag passano da `Tag::addTags`. |
| Segreti | `ensureLongSecrets()` sostituisce i segreti più corti di 24 caratteri. |
| Log | Ogni elemento salvato scrive una riga con `method` `cron` e il vecchio e il nuovo valore. |

Il filtro delle categorie del cron dei prodotti è costruito come `... AND p.id_product IN (...) OR p.id_category_default IN (...)` senza parentesi, quindi i prodotti con una categoria predefinita selezionata aggirano le altre condizioni. Il filtro di Generate – Products usa le parentesi e non è interessato.

### 6.4 Controller AJAX

`/module/myaimistral/ajax` è un controller di modulo front. Ogni chiamata porta `secret_token` (il valore `TOKEN`) e risponde con JSON `{status, msg, date}`.

| Azione | Scopo |
|---|---|
| `initiatePrompt` | Playground e barra superiore. Può portare `id_category`, `id_cms` o `id_manufacturer` per sostituire `{category_*}`, `{cms_title}`, `{brand_name}`, `{brand_description}`, `{brand_short_description}`. |
| `updateProduct` | Genera un campo di un prodotto. Comportamenti: `replace`, `keep`, `keep_top`, `keep_end`, `single_product` (senza salvataggio). `keep` risponde con lo stato `skipped`. |
| `updateCategory` | Lo stesso per le categorie (`single_category` non salva nulla). |
| `generateSeoPack` | Scrive nome, descrizioni e campi meta in una sola richiesta. |
| `generateAltTexts` | Scrive i testi alternativi delle immagini. Nessun pulsante nell'interfaccia. |
| `initiateProductRestore` | Ripristina un valore precedente da una riga di log. |
| `updateSettings` | Salva Max Tokens, Temperature, Top P e le penalità. |

Il token viene stampato nelle pagine del back office e il controller non controlla la sessione di un dipendente. Tratti il token come un segreto.

`Studio::gate()` applica le regole della casa, il budget mensile (conta le righe che non sono errori) e il controllo delle parole vietate. `OpenAIService` chiama Mistral con cURL, mantiene il timeout tra 10 e 600 secondi, riprova fino a sei volte senza i parametri che l'API rifiuta (ricordati in `MODEL_CAPS`) e allenta la verifica SSL solo su localhost. Il controller ajax estende il `max_execution_time` di PHP per farlo corrispondere al timeout.

### 6.5 Chiavi di configurazione

Tutte le chiavi iniziano con `MYPRESTA_MYAIMISTRAL_`.

| Suffisso della chiave | Predefinito | Scopo |
|---|---|---|
| `LIVE_MODE` | 0 | Live mode. |
| `DEBUG_MODE` | 0 | Debug mode. |
| `TOPCTA` | 1 | Admin Top Bar CTA. |
| `PRODUCT` | 1 | Product edit page Form. |
| `PRODUCT_LOG` | 1 | Product Edit History. |
| `TOKEN` | casuale | Segreto AJAX. |
| `SECRET` | casuale | Segreto del cron dei prodotti. |
| `CAT_SECRET` | casuale | Segreto del cron delle categorie. |
| `API_KEY` | un singolo spazio | Chiave Mistral. |
| `MODEL` | mistral-small-latest | Modello attivo. |
| `EXTRA_MODELS` | vuoto | Modelli aggiunti dal commerciante, uno per riga. |
| `MODEL_CAPS` | vuoto | Parametri rifiutati per modello. |
| `TEMPERATURE` | 0.7 | Temperatura di campionamento. |
| `MAX_TOKENS` | 3200 | Limite della risposta. |
| `TOP_P` | 1 | Top P. |
| `FREQ_PEN`, `PRES_PEN` | 0 | Penalità. |
| `TIMEOUT` | 120 | Secondi, da 10 a 600. |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | vuoto | Testi di Studio. |
| `BUDGET` | 0 | Limite mensile di richieste. |
| `QUALITY` | 1 | Controllo delle parole vietate. |
| `IMAGEFINDER_ENABLE` | 1 | Interruttore della ricerca foto. |
| `IMAGEFINDER_PROMPT` | testo integrato | Istruzione della ricerca foto. |
| `ENABLE_CRON` | 0 | Interruttore del cron. |
| `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | 6 | Promemoria dell'intervallo (6 è Every Hour). |
| `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug`, `productIdsList`, `categories` | description, pendingMistral, 5, lingua predefinita del negozio, vuoto, 0, vuoto, vuoto | Modulo del cron dei prodotti. |
| `catupdatedField`, `categoryTarget`, `categoriesToUpdate`, `catlanguageId`, `catpromptTemplateId`, `catdebug` | description, pendingMistral, 5, lingua predefinita del negozio, vuoto, 0 | Modulo del cron delle categorie. |

I filtri della pagina Generate usano lo stesso prefisso: `CATEGORIES`, `BRANDS`, `STATUS`, `STOCK`, `HISTORY`, `PROD_IDS`, `PROD_REF`, `PROD_DATE_FROM`, `PROD_DATE_TO`, `PROD_MIN_ID`, `PROD_MAX_ID`, `PROD_LIMIT`, `CATEGORIESC`, più `FIELD`, `LANGUAGE`, `CONTENT`, `DELAY` e `EXISTING` del vecchio modulo delle categorie. Vengono scritti a ogni richiesta del controller Generate e non vengono rimossi alla disinstallazione. Il valore di Product IDs viene inserito nella query così come digitato, con gli spazi rimossi, quindi riservi quella pagina a dipendenti fidati.

### 6.6 Database

| Tabella | Colonne | Note |
|---|---|---|
| `myaimistral_prompt` | `id_prompt`, `status`, `title`, `prompt`, `date_generated` | 16 righe all'installazione. |
| `myaimistral_log` | `id_log`, `type`, `method`, `status`, `ai_service`, `model`, `prompt`, `reply`, `error_message`, `http_code`, `duration_ms`, `id_product`, `id_category`, `id_cms`, `id_manufacturer`, `id_lang`, `id_employee`, valori dei campi `old_*` e `new_*`, `prompt_tokens`, `completion_tokens`, `total_tokens`, `date_updated` | Le colonne dei token vengono aggiunte su richiesta da `ensureUsageColumns()`. Entrambe le tabelle vengono eliminate alla disinstallazione. |

I valori di `type` sono per esempio `general`, `singleCategory`, `singleCMS`, `singleBrand`, `product_name`, `product_description`, `product_description_short`, `product_meta_title`, `product_meta_description`, `product_tags`, `category_description` ed `error`. I valori di `method` sono `initiatePrompt`, `updateProduct`, `updateCategory` e `cron`.

### 6.7 Elementi del front-end

| Elemento | Note |
|---|---|
| Classi | Gli stili di amministrazione iniziano con `.mam-` (navigazione, dashboard, schede, chip, riquadri, cassetto dell'aiuto). Il pannello del prodotto usa `.myaimistral-ui` e i pulsanti dei campi usano `.myaimistral-field-btn`. |
| `views/js/back.js` | Playground, pulsanti del pannello del prodotto, esecutore di massa, New product, restore, schede, menu a tendina della barra superiore. Attributi data del pannello del prodotto: `data-myaimistral`, `data-myaimistral-product`, `data-mam-fill`, `data-mam-for`. |
| `views/js/product-fields.js` | I pulsanti dei campi nelle pagine di prodotto e categoria. Legge `window.myaimistralField`. |
| `views/js/image-finder.js` | Ricerca e importazione delle foto. |
| `views/js/admin-products-bulk.js` | Il pulsante nell'elenco dei prodotti. Legge `myaimistralAdminLink`. |
| Stili | `back.css`, `admin-nav.css`, `stats.css`. |

### 6.8 Estendere

- Nuovi modelli di prompt: inserisca una riga in `myaimistral_prompt` con `status` 1.
- Nuovi segnaposto: estenda i costruttori di prompt di prodotto e categoria in `controllers/front/ajax.php` e in `controllers/front/cron.php`. I segnaposto del negozio sono gestiti in `applyShopShortcodes()`.
- Nuovi modelli: li aggiunga in Settings – Mistral, oppure accodi il nome all'elenco integrato in `myaimistral.php`.
- Un altro provider: cambi l'URL di base e il corpo della richiesta in `src/OpenAIService.php`. Tutto il resto parla solo con quella classe.
- Traduzioni: usi `$this->l()` nel modulo e `trans()` nei controller su PrestaShop 8 e 9. Le stringhe si trovano in `translations/`.

## 7. Aiuto

Pagina del prodotto: https://mypresta.eu/modules/administration-tools/my-ai-mistral.html

Per ricevere aiuto sul modulo, acceda a mypresta.eu, apra **contact** e scelga **Support for paid modules**. Descriva il problema, le sue versioni di PrestaShop e PHP e il testo del messaggio che vede. Non invii mai la chiave API né un segreto di cron.
