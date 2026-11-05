---
title: My AI Claude - AI content generation - documentazione e manuale utente
description: Guida alla configurazione, all'uso quotidiano e alla risoluzione dei problemi per i titolari di negozi che hanno già installato My AI Claude e vogliono collegarlo al proprio account Anthropic Claude e usarlo sul proprio catalogo.
sidebar:
  label: My AI Claude - AI content generation - documentazione e manuale utente
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo SEO meta and catalog descriptions with Claude AI su MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-claude-ai.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-claude-ai/)
>
> ---


## 1. Requisiti

My AI Claude funziona all'interno del back office di PrestaShop e invia i suoi prompt ad Anthropic Claude. Richiede quanto segue.

| Elemento | Requisito | Note |
|---|---|---|
| PrestaShop | 1.6, 1.7, 8 e 9 (da 1.6 a 9.99.99) | Funziona nella pagina prodotto classica e in quella nuova. |
| PHP | 7.0 o successivo | Con una versione inferiore l'installazione si ferma e mostra un messaggio con la versione PHP del suo server. |
| Estensioni PHP | cURL, JSON, mbstring, DOM, fileinfo, GD | Standard sulla maggior parte degli hosting. cURL dialoga con Claude, DOM legge la pagina di origine in **New product**, GD ridimensiona le foto importate. |
| Impostazione PHP | `allow_url_fopen` attivo | Necessario solo per **New product** (lettura dell'indirizzo della pagina di origine). |
| Altri moduli | Nessuno | Non è necessario installare nessun altro modulo. |
| Database | Nessun requisito aggiuntivo | Il modulo usa la versione di MySQL o MariaDB su cui PrestaShop già funziona. |
| Account esterno al negozio | Un account Anthropic con accesso alle API e credito | Crei la chiave su https://console.anthropic.com/settings/keys. Ogni generazione viene fatturata da Anthropic in base ai token usati. |
| Rete | Il server può aprire connessioni HTTPS | Il negozio contatta `api.anthropic.com` a ogni generazione. Il controllo degli aggiornamenti contatta il server di MyPresta.eu. La funzione Images apre pagine web pubbliche. |
| Browser | JavaScript attivo | Tutti i pulsanti del modulo sono script eseguiti nel back office. |

**Tempo e memoria.** Una generazione è una richiesta a Claude e dura da pochi secondi a circa un minuto. Il limite di attesa si imposta in **Settings, General** alla voce **API timeout (seconds)** (120 secondi all'inizio, qualsiasi valore da 10 a 600). Imposti il limite di tempo PHP del suo server a un valore superiore. Un'esecuzione di massa invia una richiesta per prodotto, per campo e per lingua, una dopo l'altra, e funziona solo finché la sua pagina resta aperta nel browser. Il modulo non avvia alcun processo in background e non richiede memoria aggiuntiva rispetto a una normale pagina del back office.

## 2. Installazione

### 2.1 Caricamento e installazione

1. Apra **Modules → Module Manager** (PrestaShop 1.6: **Modules and Services**).
2. Clicchi su **Upload a module** (PrestaShop 1.6: **Add a new module**).
3. Selezioni il file ZIP del modulo e attenda la fine del caricamento.
4. Clicchi su **Install** quando PrestaShop lo propone.
5. Attenda la conferma. L'installazione crea la voce di menu, due tabelle del database e i modelli di prompt predefiniti (vedere 3.6).

Il programma di installazione non svuota la cache. Se la voce di menu non compare, apra **Advanced Parameters → Performance**, clicchi su **Clear cache** e ricarichi la pagina.

Dopo l'installazione il modulo non fa nulla finché non inserisce la sua chiave Anthropic. Passi al capitolo 3, sezione 3.1.

### 2.2 Dove compare il modulo

Il modulo aggiunge una voce di menu chiamata **AI Content Generator** sotto **Modules**. Vi clicchi per aprire il modulo sulla sua **Dashboard**. Tutte le altre schermate si raggiungono dal menu orizzontale in alto nella pagina del modulo:

**Dashboard**, **Settings** (con le sottopagine **General**, **Claude**, **Studio**, **Prompt templates**, **Playground**), **Generate**, **New product**, **Cron**, **History**, **Images**, **Updates**.

Il modulo aggiunge anche un pannello **Modules → My AI Claude** in ogni pagina prodotto, piccoli pulsanti **Generate with AI** accanto ai campi di testo nei moduli di prodotto e categoria, una scorciatoia nella barra superiore del back office e un pulsante **My AI Claude** sopra l'elenco dei prodotti. Le sezioni 3.16 e 3.17 li descrivono tutti.

Se un dipendente che non è super amministratore non riesce ad aprire la voce di menu, dia al profilo di quel dipendente l'accesso alle schermate del modulo in **Advanced Parameters → Team → Permissions**.

### 2.3 Disattivazione e disinstallazione

- **Disattivi** il modulo nel Module Manager per nascondere le sue schermate. Finché è disattivato, qualsiasi indirizzo del modulo la riporta alla dashboard principale di PrestaShop. Tutti i dati restano.
- **Disinstallare** rimuove le voci di menu, la tabella con i modelli di prompt, la tabella con la cronologia delle generazioni e ogni impostazione del modulo (chiave API, modello, regole di Studio, impostazioni cron e segreti cron). La History scompare insieme ai suoi punti di ripristino, e scompaiono anche i dati della Dashboard.
- La disinstallazione lascia tutto ciò che il modulo ha già scritto nel suo negozio: testi di prodotti e categorie, foto importate e prodotti creati con **New product**.
- La disinstallazione lascia anche alcune scelte di schermata salvate dei filtri **Generate** e le impostazioni del controllo aggiornamenti di MyPresta.
- **Reinstallare** riparte da zero: la chiave API è vuota, i segreti sono nuovi (gli indirizzi cron cambiano, quindi aggiorni lo scheduler del suo server), la History è vuota e i modelli predefiniti tornano alla formulazione originale.

## 3. Configurazione e lavoro quotidiano nel back office

### 3.1 L'intero processo, passo dopo passo

1. Crei una chiave API Anthropic su https://console.anthropic.com/settings/keys e si assicuri che l'account abbia credito.
2. Apra **AI Content Generator → Settings → Claude**. Incolli la chiave in **Anthropic Claude API KEY**, scelga un **Model** e clicchi su **Save**.
3. Apra **Settings → Playground**, scriva una breve domanda e clicchi su **Generate**. Una risposta sulla pagina conferma che la chiave funziona.
4. Facoltativo: apra **Settings → Studio** e descriva la voce del suo marchio, il pubblico, il tono, i termini preferiti e le parole vietate. Queste regole vengono aggiunte a ogni generazione.
5. Apra **Settings → Prompt templates** e legga i modelli predefiniti. Modifichi quelli che vuole mantenere e disattivi gli altri.
6. Apra un prodotto, vada su **Modules → My AI Claude**, prema **Try** sulla scheda della descrizione per leggere un risultato senza modificare il prodotto, poi prema **Fill** per scriverlo nel prodotto.
7. Apra **History** e controlli la voce. Prema **Restore** nel pannello del prodotto se vuole riavere il testo precedente.
8. Per molti prodotti, apra **Generate → Products**, filtri l'elenco, scriva o scelga un prompt e clicchi su **Run on the list below**. Provi prima con un elenco piccolo.
9. Per le esecuzioni automatiche da parte del server, configuri **Cron** (sezione 3.12).
10. Tenga d'occhio costi e volumi su **Dashboard** e **History**. Imposti un **Monthly generation budget** in **Studio** per limitare l'utilizzo.

### 3.2 Aprire il modulo e muoversi al suo interno

Clicchi su **AI Content Generator** sotto **Modules**. Il menu superiore del modulo contiene **Dashboard**, **Settings**, **Generate**, **New product**, **Cron**, **History**, **Images** e **Updates**. Alcune pagine hanno una seconda riga: **Settings** ha **General**, **Claude**, **Studio**, **Prompt templates** e **Playground**; **Generate** ha **Products** e **Categories**.

I nomi in grassetto sono le etichette del back office in inglese, e gli screenshot di questo manuale mostrano il back office in inglese. Se il suo back office è in un'altra lingua, cerchi le voci corrispondenti nello stesso punto.

Ogni pagina del modulo ha un pulsante rotondo **Help** nell'angolo in basso a destra. Apre un pannello laterale con una breve spiegazione della pagina in cui si trova.

### 3.3 Dashboard

![My AI Claude dashboard with request and token cards and three charts](https://mypresta.eu/docs/images/docs/myaiclaude-dashboard.webp)

La Dashboard mostra quanto è stato usato il modulo. La prima riga indica il servizio e il modello attivi.

Scelga il periodo con uno dei pulsanti **Today**, **7 days**, **30 days**, **90 days**, **This month**, **All time**, oppure digiti le sue date in **From** e **To** e clicchi su **Apply**. La pagina si apre con **30 days**.

| Elemento | Significato | Note |
|---|---|---|
| Requests | Numero di chiamate fatte a Claude nel periodo | Conta ogni riga della History: esecuzioni di massa, pannello prodotto, Playground, barra superiore, cron. |
| Success | Chiamate che hanno restituito testo | |
| Errors | Chiamate fallite | Il motivo è salvato nella riga della History. |
| Tokens sent | Token nei suoi prompt | I token sono l'unità in base alla quale fattura Anthropic. |
| Tokens received | Token nelle risposte | |
| Requests and errors | Grafico per giorno | I periodi lunghi sono raggruppati per settimana. |
| Tokens sent and received | Grafico per giorno | |
| Requests by model | Grafico | Mostra quali modelli hanno svolto il lavoro. |

Il modulo aggiunge anche un blocco alla dashboard principale di PrestaShop. I dati completi e i grafici sono in questa pagina.

### 3.4 Settings – General

![Settings General page with switches and the image search prompt](https://mypresta.eu/docs/images/docs/myaiclaude-settings-general.webp)

Apra **Settings → General**, modifichi i campi e clicchi su **Save**. Il messaggio **Settings Updated** lo conferma.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| Live mode | No | Un'etichetta per lei che segna il negozio come attivo in produzione. Non attiva né disattiva alcuna funzione. |
| Debug mode | No | Scrive nel log di PrestaShop (**Advanced Parameters → Logs**) righe tecniche sulle chiamate fallite. Lo attivi quando il supporto chiede dettagli, poi lo disattivi. |
| API timeout (seconds) | 120 | Per quanto tempo il negozio attende Claude prima di arrendersi. I valori sotto 10 diventano 10, quelli sopra 600 diventano 600, un valore vuoto o non valido diventa 120. Lo aumenti per le descrizioni lunghe. |
| Product Edit History | Yes | Mostra la scheda **History** nel pannello del prodotto e permette di ripristinarvi il testo precedente. Se è disattivato, la scheda scompare. Le generazioni continuano a essere salvate nella History principale. |
| Admin Top Bar CTA | Yes | Mostra la piccola icona My AI Claude nella barra superiore del back office (sezione 3.17). |
| Product edit page Form | Yes | Mostra il pannello **Modules → My AI Claude** nella pagina prodotto. Se questo interruttore e **Product Edit History** sono entrambi disattivati, il pannello è vuoto. |
| AI Image Finder | Yes | Abilita la scheda **Photos** nella pagina prodotto. Lo stesso interruttore è nella pagina **Images**. |
| AI Image Search Prompt | Testo predefinito | L'istruzione usata per trovare pagine con foto di un prodotto. Lo stesso campo è nella pagina **Images** (sezione 3.14). |

### 3.5 Settings – Claude

![Settings Claude page with API key, model and sampling fields](https://mypresta.eu/docs/images/docs/myaiclaude-settings-claude.webp)

Questa pagina collega il negozio al suo account Claude. La prima volta che la apre, il modulo può mostrare un avviso che indica che sono stati rimossi spazi dal campo della chiave. È normale.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| Anthropic Claude API KEY | Vuoto | Il segreto che permette al negozio di chiamare il suo account Claude. Incolli la chiave da https://console.anthropic.com/settings/keys. Gli spazi vengono rimossi al salvataggio. Lasci il campo intatto per mantenere la chiave salvata. Una chiave mancante fa fallire ogni chiamata, e l'errore compare in **History**. |
| Model | claude-sonnet-4-5 | Il modello Claude che scrive il testo. Nomi integrati: claude-sonnet-4-5, claude-opus-4-5, claude-haiku-4-5, claude-3-5-sonnet-latest, claude-3-5-haiku-latest, claude-3-opus-latest, più i nomi che ha aggiunto. Un modello che la sua chiave non può usare restituisce un errore invece del testo. |
| Add a Claude model | Vuoto | Digiti il nome esatto del modello dal suo account Claude e clicchi su **Add model**. Il nome compare nell'elenco **Model**. Accanto a ogni nome aggiunto c'è un link **Remove**. I nomi integrati non si possono rimuovere. |
| Max Tokens | 3200 | Limite massimo della lunghezza della risposta, contato in token. Usi circa 256 per una meta description e 1000 o più per una descrizione completa. Un valore basso taglia la risposta. Un valore vuoto viene sostituito da 256. |
| Temperature | 0.7 | Quanto è varia la formulazione, da 0 a 1. Più basso è più regolare, più alto è più creativo. Inserisca 0.1 per lo stile più regolare, perché un semplice 0 viene letto come il valore iniziale 0.7. |
| Top P | 1 | Salvato con gli altri campi, ma My AI Claude non lo invia a Claude. Modificarlo non ha effetto. |
| Frequency Penalty Value | 0 | Salvato, ma non inviato a Claude. Modificarlo non ha effetto. |
| Presence Penalty Value | 0 | Salvato, ma non inviato a Claude. Modificarlo non ha effetto. |

Clicchi su **Save** in fondo al modulo. Compare una conferma quando i valori sono validi. Il messaggio **Anthropic Claude API KEY field is invalid!** significa che il campo della chiave è vuoto e nessuna chiave è ancora salvata.

Se un modello rifiuta una delle impostazioni (per esempio la temperature), il modulo rimuove quell'impostazione, riprova e la ricorda per quel modello. Non deve fare nulla.

I valori di campionamento (Max Tokens, Temperature) sono usati dalle esecuzioni di massa, dal pannello prodotto, dal Playground, dalla barra superiore e dal cron. **Images** usa propri valori fissi.

### 3.6 Settings – Prompt templates

![Prompt templates list with title, prompt, status and actions](https://mypresta.eu/docs/images/docs/myaiclaude-settings-templates.webp)

Un modello è un'istruzione salvata che può scegliere nelle esecuzioni di massa, nel pannello prodotto, nella barra superiore e nel cron. L'installazione crea 16 modelli, tutti attivi.

| Modello | Scopo | Note |
|---|---|---|
| Product name 1, Product name 2 | Nomi di prodotto più brevi o migliori | Name 2 usa il marchio e la categoria predefinita. |
| Product description 1 to 6 | Descrizioni di prodotto | Description 1 costruisce un layout HTML con titoli e chiede errori di ortografia deliberati. Elimini quella frase prima di usarlo. Description 3 chiede anche idee per H1, parole chiave, un meta title e una meta description, che finiscono tutti nel campo della descrizione. |
| Product description 7 - using product images | Descrizione con foto incorporate | Usa i link alle immagini del prodotto. |
| Product meta title 1 to 3 | Meta title | Meta title 1 chiede la lingua inglese e 60 caratteri. |
| Product meta description 1 to 3 | Meta description | Meta description 1 chiede la lingua inglese e 160 caratteri. Le Meta descriptions 2 e 3 sono identiche e citano uno smartwatch, quindi le riscriva per i suoi prodotti. |
| Product tags | Cinque tag su una riga | Chiede la lingua inglese. |

Diversi modelli chiedono l'inglese nel testo stesso. Se vende in un'altra lingua, modifichi quei modelli e rimuova la riga.

L'elenco mostra **ID**, **Title**, **Prompt**, **Status** (clicchi sull'interruttore per attivare o disattivare), **Timestamp** e le azioni di riga per modificare o eliminare. Selezioni più righe e usi l'azione di gruppo **Delete** (la domanda **Are you sure you want to delete the selected prompts?** chiede conferma). I modelli più recenti sono in alto e l'elenco mostra 50 righe per pagina.

Per creare un modello, clicchi sul pulsante **new** nella barra degli strumenti. Per modificarne uno, clicchi sull'azione di modifica nella sua riga.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| Status | Enabled per un nuovo modello | Solo i modelli attivi compaiono nei selettori del modulo. |
| Prompt title | Vuoto (obbligatorio) | Il nome che vede nei selettori e nell'elenco. |
| Prompt content | Vuoto (obbligatorio) | L'istruzione inviata a Claude. Può usare segnaposto come `{product_name}` (sezione 3.18). Le virgolette doppie vengono sostituite da virgolette semplici al salvataggio. |

Clicchi su **Save Prompt** per salvare il modello. I messaggi sono **Prompt template successfully added!** e **Prompt template successfully updated!**. Un modello eliminato mostra **Prompt template removed.**. Clicchi su **Go Back to Module Settings** per uscire dal modulo senza salvare.

Un modello dice a Claude cosa scrivere. Il modulo aggiunge anche le regole di **Studio** e la lingua dell'esecuzione (la sezione 3.8 descrive le regole di Studio).

### 3.7 Settings – Playground

![Playground with a text box and the Generate button](https://mypresta.eu/docs/images/docs/myaiclaude-settings-playground.webp)

Il Playground è una casella di testo libera per provare un prompt. Digiti il suo prompt e clicchi su **Generate**. La risposta compare sulla pagina. Non viene scritto nulla in alcun prodotto o categoria.

La chiamata viene salvata nella History come generazione generale, quindi conta per la Dashboard e per il budget mensile. Usi il Playground per verificare la chiave API, il modello e l'effetto delle regole di Studio.

### 3.8 Settings – Studio

![Studio page with brand voice, audience, tone, glossary and forbidden words](https://mypresta.eu/docs/images/docs/myaiclaude-settings-studio.webp)

Studio contiene le regole che vengono aggiunte a ogni generazione: esecuzioni di massa, pannello prodotto, categorie, cron, Playground e barra superiore. Anche con tutti i campi di Studio vuoti, il modulo indica a Claude in quale lingua scrivere (la lingua di quell'esecuzione).

| Campo | All'inizio | Cosa fa |
|---|---|---|
| Brand voice | Vuoto | Descrive come parla il suo negozio. Claude lo segue in ogni testo. |
| Audience | Vuoto | Descrive il cliente per cui scrive. |
| Tone | Vuoto | Il tono del testo, per esempio caldo, tecnico o neutro. |
| Glossary | Vuoto | Termini che Claude deve mantenere esattamente come li scrive lei. Uno per riga. |
| Forbidden words | Vuoto | Parole che Claude non deve usare. Una per riga. A Claude viene detto di non usarle e, quando il quality gate è attivo, una risposta che ne contiene ancora una viene rifiutata. |
| Monthly generation budget | 0 | Numero massimo di generazioni riuscite nel mese di calendario in corso. 0 significa nessun limite. Quando il numero viene raggiunto, le nuove chiamate si fermano con il messaggio **Monthly generation budget reached. Raise it in the studio settings or wait until next month.** Le chiamate fallite non vengono contate. |
| Quality gate | Yes | Controlla ogni risposta alla ricerca di parole vietate prima di salvarla. Una risposta rifiutata non viene scritta e mostra **The reply was rejected because it contains a forbidden word from the studio settings.** |

Clicchi su **Save studio**. Il messaggio **Studio settings saved.** lo conferma.

Il budget conta tutte le righe riuscite della History nel mese: esecuzioni di massa, pannello prodotto (**Try** incluso), Playground, barra superiore e cron. **New product** non viene contato.

### 3.9 Generate – Products

![Generate Products filter form](https://mypresta.eu/docs/images/docs/myaiclaude-generate-products.webp)

Apra **Generate → Products**. La pagina funziona in due passaggi: prima un filtro sceglie i prodotti, poi un pannello esegue Claude su quell'elenco.

**Passaggio 1 – il filtro.** Compili i campi e clicchi su **Go to next step**. Il modulo si apre sempre con i valori indicati qui sotto.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| Product Categories | Nulla selezionato | Selezioni delle categorie per limitare l'elenco ai prodotti in esse contenuti. Vuoto significa tutte le categorie. |
| Brand | All | Limita l'elenco a un marchio. |
| Product status | Active | Active, Disabled o Both. |
| Product stock | All products | **Only in stock products** mantiene i prodotti con quantità superiore a zero. |
| Update only | Update all | Tre opzioni: solo i prodotti che non hanno ancora una voce nella History, solo quelli che ce l'hanno già, oppure tutti i prodotti. Conta qualsiasi voce, comprese le chiamate fallite e le esecuzioni **Try**. |
| Product IDs | Vuoto | Un elenco di ID prodotto. |
| Product Reference | Vuoto | Limita l'elenco ai prodotti con questo riferimento. |
| Product Add Date From, Product Add Date To | Vuoto | Limita l'elenco in base alla data di creazione del prodotto. |
| Minimum product ID, Maximum product ID | Vuoto | Limita l'elenco a un intervallo di ID. |
| Product Limit | Vuoto | Il numero massimo di prodotti nell'elenco. |

**Passaggio 2 – il pannello Mass product generation.** I prodotti corrispondenti compaiono in una tabella con **ID**, **Reference** e **Result**. Sopra la tabella imposta l'esecuzione.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| Template | Nulla scelto | Sceglie un modello attivo e ne copia il testo nella casella del prompt. Può poi modificare il testo. |
| Prompt | Vuoto | L'istruzione per Claude, con segnaposto come `{product_name}`. Quando la casella è vuota, il modulo usa un incarico integrato per ogni campo: una descrizione HTML con introduzione ed elenco delle caratteristiche, un breve riassunto in testo semplice sotto i 400 caratteri, un meta title di circa 70 caratteri e una meta description di circa 160 caratteri. |
| What to generate | Descriptions | **Descriptions** (descrizione lunga e breve), **Meta title and meta description** oppure **Descriptions and meta together**. |
| Existing text | Replace | **Replace**, **Skip if filled**, **Add above** o **Add below**. |
| Languages | La lingua corrente selezionata | Selezioni ogni lingua che vuole scrivere. |

Clicchi su **Run on the list below**. Una riga di stato mostra l'avanzamento (per esempio `3 / 40` con il nome del campo) e termina con **Finished N products.** Ogni riga mostra il campo, il risultato e il messaggio, per esempio **Content successfully generated and updated to product.** o **Product skipped.**

Regole di un'esecuzione:

- L'esecuzione invia una richiesta per prodotto, per campo e per lingua, una dopo l'altra. Conti le richieste prima di iniziare, perché ognuna viene fatturata.
- Tenga la pagina aperta. Chiuderla o ricaricarla ferma l'esecuzione. I prodotti già scritti restano scritti.
- Un errore in una riga non ferma le altre. Il motivo è nella riga e in **History**.
- Limiti al salvataggio: nome del prodotto 128 caratteri, descrizione breve 800, meta title 69, meta description 159. Il testo più lungo viene tagliato.
- Il testo viene salvato direttamente nel prodotto. Usi il pannello prodotto (sezione 3.16) per ripristinare un testo precedente.

### 3.10 Generate – Categories

![Generate Categories filter form](https://mypresta.eu/docs/images/docs/myaiclaude-generate-categories.webp)

Apra **Generate → Categories**. Il primo modulo ha **Categories** (un albero, vuoto significa tutte) e **Category status** (Active, Disabled o Both, Active all'inizio). Clicchi su **Go to next step**. L'elenco può includere le categorie Root e Home, quindi selezioni le categorie desiderate.

Sotto il filtro compare il pannello **Run on the categories below** con una tabella di **ID** e **Result**.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| Prompt | Vuoto | L'istruzione per Claude. Usi segnaposto di categoria come `{category_name}`, `{category_description}` e `{category_parent_name}`. I segnaposto di prodotto qui non vengono compilati. |
| Field | Description | **Description**, **Name**, **Meta title**, **Meta description** o **Additional description**. |
| Existing text | Replace | **Replace** o **Skip if filled**. |
| Language | La lingua corrente | Una lingua per esecuzione. |

Clicchi su **Run on the categories below**. Ogni riga mostra il risultato, per esempio **Content successfully generated and updated to category.** o **Category skipped.**

Sotto il pannello la pagina mostra un secondo modulo chiamato **Generate category content**. Il suo pulsante non avvia alcuna esecuzione. Usi **Run on the categories below** e ignori il secondo modulo. Il pulsante **Go Back to Category Filter** riporta al filtro.

I limiti al salvataggio sono gli stessi dei prodotti: nome 128 caratteri, meta title 69, meta description 159. Il campo **Additional description** esiste solo nelle versioni di PrestaShop che lo hanno. Altrimenti la riga mostra un errore.

### 3.11 New product

![New product page with the product brief and the generated draft](https://mypresta.eu/docs/images/docs/myaiclaude-new-product.webp)

**New product** crea un prodotto completo a partire da una breve descrizione. Claude scrive una bozza, lei la legge e poi il modulo crea il prodotto nel suo catalogo.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| What is the product? | Vuoto | Descriva il prodotto in poche frasi: cos'è, a chi è destinato, le caratteristiche principali. È l'unico campo obbligatorio. Il testo viene tagliato a 8000 caratteri. |
| Optional source URL | Vuoto | L'indirizzo di una pagina sul prodotto. Il modulo ne legge il titolo, la meta description e il prezzo e li passa a Claude. |
| Language | La lingua predefinita del negozio | La lingua della bozza. |
| Default category ID | 2 | L'ID della categoria in cui viene collocato il prodotto. 2 è la categoria Home di un negozio standard. |

1. Compili i campi e clicchi su **Generate data**. La bozza compare sulla pagina come blocco di dati (nome, descrizioni, campi meta, tag, caratteristiche, prezzo). Non è ancora stato salvato nulla.
2. Legga la bozza. Se non va bene, modifichi la descrizione e clicchi di nuovo su **Generate data**.
3. Clicchi su **Create product** solo quando accetta la bozza. La pagina mostra allora **Product #** seguito dal numero del nuovo prodotto. Trovi il prodotto in **Catalog → Products**.

Il nuovo prodotto viene creato con queste impostazioni: attivo, ordinabile, prezzo visibile, visibile nel catalogo e nella ricerca, condizione nuovo, la prima regola fiscale del negozio, una giacenza di 100 pezzi e il prezzo della bozza (0 quando la bozza non ne ha). Claude compila anche il nome, le descrizioni, i campi meta, i tag, le caratteristiche e il riferimento (massimo 32 caratteri). Apra poi il prodotto, controlli il prezzo, l'imposta, la giacenza e le foto, e aggiunga le foto con la scheda **Photos** del pannello prodotto.

Se non è salvata alcuna chiave, la pagina mostra **Add an API key in the module settings first.** Questa pagina non applica le regole di Studio né il budget mensile, e le sue chiamate non compaiono in **History** né sulla **Dashboard**.

### 3.12 Cron

![Cron page with enable switch, secret and product cron form](https://mypresta.eu/docs/images/docs/myaiclaude-cron.webp)

Il cron permette al suo server di generare testo secondo una pianificazione senza che nessuno clicchi. La pagina costruisce l'indirizzo che il server deve aprire. Non avvia alcuno scheduler. L'attività pianificata la crea sul suo hosting o server, e ogni chiamata elabora un lotto e si ferma.

La pagina ha due moduli: il cron dei prodotti e il cron delle categorie. Il modulo dei prodotti è descritto qui sotto. Quello delle categorie ha la stessa logica, con il proprio segreto e le proprie impostazioni.

Sotto l'introduzione di ogni modulo la pagina mostra l'indirizzo del cron. L'indirizzo dei prodotti ha questo aspetto: `https://your-shop/module/myaiclaude/cron?secret=...`. L'indirizzo delle categorie termina con `&entity=category`.

**Completi l'indirizzo prima di usarlo.** Aggiunga `&action=generateProductContent` alla fine dell'indirizzo dei prodotti e `&action=generateCategoryContent` alla fine di quello delle categorie. Senza di esso l'indirizzo risponde **Invalid action!** e non fa nulla.

Esempio per i prodotti:

`https://your-shop/module/myaiclaude/cron?secret=YOUR_SECRET&action=generateProductContent`

L'indirizzo usa le scelte salvate nel modulo: campo, destinazione, numero di prodotti, lingua e modello. Può sovrascriverle nell'indirizzo (la sezione 6.3 elenca i parametri).

**Modulo del cron dei prodotti**

| Campo | All'inizio | Cosa fa |
|---|---|---|
| Enable Cron Feature | No | Interruttore generale di entrambi gli indirizzi cron (prodotti e categorie). Quando è disattivato, l'indirizzo risponde **Cron Job feature is disabled. You can enable it from the module settings.** |
| Cron Job Secret Token | Testo casuale | La lunga password nell'indirizzo. Senza quella giusta l'indirizzo risponde **The token does not exist or it's wrong!** Il pulsante **Generate Token** non funziona in questa versione (sezione 5.5). Digiti un segreto proprio di almeno 24 lettere e cifre, salvi e copi il nuovo indirizzo nel suo scheduler. |
| Update Field | description | L'unico campo scritto da questo indirizzo: name, description, description_short, meta_title, meta_description o tags. Per più campi crei più attività. |
| Selected Products | pendingClaude | **pendingClaude** prende i prodotti che non hanno ancora una generazione My AI Claude riuscita (qualsiasi campo). **pendingField** prende i prodotti senza generazione riuscita per questo campo, il che le permette di eseguire un'attività per la descrizione e un'altra per il nome sugli stessi prodotti. **emptyField** prende i prodotti il cui campo scelto è vuoto. |
| Product Categories | Nulla selezionato | Limita l'esecuzione ai prodotti nelle categorie selezionate. |
| Product ID list | Vuoto | Solo questi ID prodotto, separati da virgole. Le lettere vengono scartate al salvataggio. |
| Language | La lingua predefinita del negozio | La versione linguistica che viene scritta. Le altre lingue richiedono una propria attività. |
| Product to update | 5 | Quanti prodotti elabora una chiamata. Inizi con 5 o 10 in modo che una risposta lenta non raggiunga il limite di tempo del server. La chiamata successiva prosegue con i prodotti che corrispondono ancora. |
| Prompt Template | Nulla salvato | L'istruzione salvata usata per ogni prodotto dell'esecuzione. Ne scelga una e clicchi su **Save**. Senza un modello salvato l'indirizzo risponde **All must include all mandatory parameters!** |
| Enable Debug | No | Quando apre l'indirizzo in un browser, mostra il piano, la query al database e il prompt finale e non salva nulla. Lo disattivi prima che lo scheduler usi l'indirizzo. |
| CRON JOB interval | Every Hour | Una nota per lei sul ritmo del suo scheduler (da ogni minuto a ogni 6 ore). Non pianifica nulla e non cambia l'indirizzo. |
| Product Cron Job command | L'indirizzo | L'indirizzo del cron. Aggiunga la parte `&action=` come descritto sopra. |

Clicchi su **Save** sotto il modulo. Il modulo delle categorie ha i campi **Enable Debug**, **CRON JOB interval**, **Language**, **Prompt Template**, **Selected categories**, **Update Field** (name, description, meta_title, meta_description), **Categories to update** e il segreto, e un proprio pulsante **Save**.

Cosa fa ogni chiamata:

- Sostituisce il campo scelto. Il cron non ha opzioni per mantenere o aggiungere testo.
- Applica le regole di Studio e il budget mensile. Quando il budget è raggiunto, la chiamata risponde **Error!Monthly generation budget reached.**
- Scrive una riga di History per ogni testo, così può ripristinarlo o esaminarlo.
- Entrambi i segreti aprono entrambe le azioni. Il cron resta spento finché **Enable Cron Feature** non è **Yes**.

Provi con **Enable Debug** su **Yes** e l'indirizzo aperto in un browser. Quando il piano è corretto, lo imposti su **No**, salvi e crei l'attività.

### 3.13 History

![History page with filters, cards, breakdown panels and the prompt list](https://mypresta.eu/docs/images/docs/myaiclaude-history.webp)

La History è il registro di tutto ciò che è stato inviato a Claude. La pagina si apre su **This month**.

**Filtri.** Pulsanti rapidi: **Today**, **7 days**, **30 days**, **This month**, **All time**. Campi: **From**, **To**, **Model**, **Type**, **Status**, **Language**, **Employee**, **Product / category ID**, **Prompt or reply contains**. Clicchi su **Filter**.

**Schede.** **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time**.

**Pannelli di ripartizione.** **By day**, **By model**, **By type**, **By language**, **By employee**. Ognuno mostra chiamate, token inviati, token ricevuti e totale. Le righe senza dipendente (tutte le chiamate cron) compaiono come Unknown.

**Elenco della cronologia dei prompt.**

| Colonna | Significato | Note |
|---|---|---|
| ID | Numero di riga | |
| Status | Badge **Success** o **Error** | |
| Prompt | Il testo inviato | Tagliato a 180 caratteri nell'elenco. |
| Reply / Error | La risposta o il messaggio di errore | Tagliato a 180 caratteri nell'elenco. |
| Provider | Il servizio, il modello, il numero di stato dell'errore quando Claude ne ha restituito uno, e il tempo in secondi | |
| Sent, Received, Total | Token | |
| Entity ID | Il prodotto o la categoria | Vuoto per le chiamate del Playground e della barra superiore. |
| Type | Cosa è stato generato | Vedere la tabella successiva. |
| Timestamp | Data e ora | |

Clicchi sull'azione di visualizzazione in una riga per vedere il prompt e la risposta completi e il link **Back to the list**. L'elenco mostra 50 righe per pagina.

| Type | Significato | Note |
|---|---|---|
| general | Playground e barra superiore | Nessun prodotto o categoria. |
| product_name, product_description, product_description_short, product_meta_title, product_meta_description, product_tags | Un campo prodotto | Scritto dalle esecuzioni di massa, dal pannello prodotto, dai pulsanti con logo e dal cron. |
| product_seo_pack | Il pacchetto SEO del pannello prodotto | Nome, descrizioni e campi meta in una sola richiesta. |
| category_name, category_description, category_meta_title, category_meta_description, category_additional_description | Un campo categoria | |
| error | Una chiamata fallita | Il motivo è in **Reply / Error**. |

**Clear list** nella barra degli strumenti elimina **tutte** le righe dopo conferma e mostra **Log list successfully deleted.** Non si può annullare. Rimuove anche i punti di ripristino di ogni prodotto, svuota la Dashboard, azzera il contatore del budget mensile e modifica quali prodotti contano come già elaborati in **Update only** e nelle destinazioni del cron. Esporti o annoti prima ciò che le serve.

Quando non ci sono righe nel periodo scelto, la pagina mostra **No generations in this range.**

### 3.14 Images

![Images page with the image finder switch and search prompt](https://mypresta.eu/docs/images/docs/myaiclaude-images.webp)

Questa pagina controlla la scheda **Photos** della pagina prodotto. Il modulo si chiama **AI Image Finder**.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| AI Image Finder | Yes | Abilita la scheda **Photos** nella pagina prodotto. Se è disattivato, la scheda le dice di attivarlo in **Settings → General**. |
| AI Image Search Prompt | Testo predefinito | L'istruzione inviata a Claude per trovare pagine web che mostrano il prodotto. Usi `{product_name}` e `{product_description}` come segnaposto. Mantenga la richiesta di esattamente cinque indirizzi di pagina restituiti come elenco, perché il modulo legge quell'elenco. |

Il prompt predefinito chiede esattamente cinque indirizzi di pagine che mostrano il prodotto, come elenco JSON, usando il nome e la descrizione del prodotto.

Clicchi su **Save**. Il messaggio **Settings saved.** lo conferma. La pagina e la scheda in **Settings → General** condividono lo stesso interruttore e lo stesso prompt.

### 3.15 Updates

![Updates page with manual check and automatic notifications](https://mypresta.eu/docs/images/docs/myaiclaude-updates.webp)

La pagina **Updates** controlla se esiste una versione più recente di My AI Claude. Il controllo invia il nome del modulo, la sua versione e l'indirizzo del negozio al server di MyPresta.eu.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| Manual Check | Pulsante **Check Now** | Esegue subito il controllo. La risposta è **Module is up to date!** oppure **New version available!** |
| Automatic Notifications | Enabled | Quando è attivo, il modulo controlla circa ogni tre giorni e mostra un avviso nel back office quando esiste una nuova versione. |
| Product Page | Un link | Apre la pagina del modulo su MyPresta.eu. |

Clicchi su **Save**. Il messaggio **Update settings saved.** lo conferma.

### 3.16 Pagina prodotto – Modules → My AI Claude

![Product page with the My AI Claude panel and field cards](https://mypresta.eu/docs/images/docs/myaiclaude-product-edit.webp)

Apra un prodotto qualsiasi, vada alla scheda **Modules** e trovi **My AI Claude**. Il pannello ha le schede **Generate**, **Simulate**, **Photos** e **History**. Salvi un nuovo prodotto una volta prima di usare il pannello, perché il pannello lavora su un prodotto salvato.

**Generate e Simulate.**

1. Scelga l'etichetta della lingua, oppure **Every language**. All'inizio è selezionata la prima lingua del negozio.
2. Sotto **If the field already has text** scelga **Replace**, **Add above**, **Add below** o **Skip if filled**. All'inizio è selezionato **Replace**.
3. Prema **Fill** su una scheda: **Description**, **Short description**, **Name**, **Meta title**, **Meta description** o **Tags**. Il testo viene scritto direttamente nel prodotto.
4. La scheda **SEO pack** ha **Fill all**. Una sola richiesta restituisce il nome, entrambe le descrizioni ed entrambi i campi meta. Sovrascrive quei campi, compreso il nome. Il messaggio **SEO pack saved. Refresh the product to see it.** lo conferma. Se Claude non restituisce un pacchetto utilizzabile, il pannello dice **The model did not return a usable SEO pack.**
5. Apra **Use your own instruction or a saved prompt** per filtrare e scegliere **Standard brief** o un modello attivo, oppure digiti il suo testo nella casella **Instruction**. Con la casella vuota si usa l'incarico standard della scheda.
6. La risposta e il conteggio dei token compaiono sotto le schede.

Nella scheda **Simulate** le stesse schede hanno **Try**. **Try** mostra la risposta e lascia il prodotto invariato. Viene comunque salvato nella History e contato per il budget, e fa sì che il prodotto conti come già elaborato per **Update only** e per il cron.

**Dopo Fill, ricarichi la pagina del prodotto.** Il modulo aperto contiene ancora il vecchio testo. Se preme **Save** in PrestaShop senza ricaricare, PrestaShop sovrascrive il nuovo testo con quello vecchio.

**Photos.**

![Photos tab with found photos ready to be added](https://mypresta.eu/docs/images/docs/myaiclaude-product-photos.webp)

1. Apra la scheda **Photos** e clicchi su **Find pages**. Messaggi: **Looking for photos…** e **Reading photos…**.
2. Selezioni le foto che desidera. La pagina mostra **Tick the photos you want, then add them to this product.**
3. Clicchi su **Add selected to this product**. Compare il messaggio **Adding the photos to this product…**, poi il numero di immagini importate.
4. Ricarichi la pagina del prodotto per vedere le foto.

Il cercatore legge fino a 5 pagine e propone fino a 24 foto. La prima foto selezionata diventa la copertina del prodotto. Le foto vengono scaricate nel suo negozio e ridimensionate a tutte le dimensioni immagine del suo negozio. Verifichi di avere il diritto di usarle. Quando il cercatore è disattivato, la scheda le chiede di attivarlo in **Settings → General**.

**History.** La scheda mostra **When**, **Type**, **Status** e un pulsante **Restore** per le ultime 50 voci di questo prodotto. La riga di introduzione dice **Earlier writes for this product. Restore puts the previous text back…** Senza voci dice **No generations for this product yet.** Clicchi su **Restore** e confermi. Compare il messaggio **Content successfully restored. Refresh this page to see changes.** Una riga senza valore precedente mostra **Error! This log entry has no previous value to restore.** La scheda compare solo quando **Product Edit History** è attivo.

### 3.17 Altri punti in cui compare il modulo

**Pulsanti Generate with AI accanto ai campi.** Un piccolo pulsante con il logo compare accanto a questi campi.

| Posizione | Campi | Cosa succede |
|---|---|---|
| Modulo prodotto | Description, Short description, Meta title, Meta description | Claude scrive nel campo del modulo aperto. |
| Modulo categoria | Description, Additional description, Meta title, Meta description | Claude scrive nel campo del modulo aperto. |

Se il negozio ha più di una lingua, il pulsante chiede se scrivere la lingua corrente o tutte le lingue. Il testo compare nel campo ma non è salvato. La nota **Text is in the field. Save the product to keep it.** (per le categorie: **Save the category**) lo ricorda. Su un elemento nuovo e non salvato il pulsante dice **Save the product once before generating.** (per le categorie: **Save the category once…**). Ogni utilizzo viene salvato nella History e fa sì che il prodotto conti come già elaborato.

**Scorciatoia della barra superiore.** L'icona magica nella barra superiore del back office apre una piccola finestra chiamata **My AI Claude** con un elenco **Template**, una casella di testo, **Generate** e un pulsante di chiusura. Funziona come il Playground e non salva nulla. L'interruttore è **Admin Top Bar CTA** in **Settings → General**.

**Elenco prodotti.** Un pulsante **My AI Claude** nella barra degli strumenti sopra l'elenco dei prodotti apre **Generate → Products**.

### 3.18 Segnaposto per i prompt

I segnaposto sono parole tra parentesi graffe che il modulo sostituisce con dati reali prima di inviare il prompt. Funzionano nei modelli, nella casella del prompt delle esecuzioni di massa, nel pannello prodotto e nel cron.

| Segnaposto | Vale per | Sostituito con |
|---|---|---|
| `{product_name}`, `{product_description}`, `{product_description_short}`, `{product_tags}` | Prodotti | Il nome, la descrizione, la descrizione breve e i tag correnti nella lingua dell'esecuzione. |
| `{product_reference}`, `{product_ean13}`, `{product_weight}` | Prodotti | Riferimento, codice EAN-13 e peso. |
| `{product_brand}`, `{product_default_category}`, `{product_category_description}`, `{product_categories}` | Prodotti | Marchio, categoria predefinita con la sua descrizione e tutte le categorie. |
| `{product_attributes}`, `{product_features}`, `{product_feature_values}` | Prodotti | Combinazioni, nomi delle caratteristiche e valori delle caratteristiche. |
| `{product_images}` | Prodotti | Link alle foto del prodotto. |
| `{category_name}`, `{category_description}`, `{category_parent_name}` | Categorie | Nome, descrizione e nome della categoria padre. |
| `{shop_name}`, `{shop_url}`, `{shop_language}`, `{shop_country}`, `{shop_currency}` | Ovunque | Nome del negozio, indirizzo, lingua, paese e valuta. |

Un segnaposto che non ha dati viene sostituito con un testo vuoto.

## 4. Vetrina

My AI Claude non aggiunge nulla che i suoi clienti possano vedere o usare. Non ha pagine front office, blocchi, widget né impostazioni lato cliente. I testi che scrive diventano visibili solo perché sono salvati nei suoi prodotti e nelle sue categorie, e lei li vede attraverso il suo normale tema.

Il modulo ha due indirizzi che appartengono al dominio del negozio ma non sono destinati ai clienti.

| Indirizzo | Chi lo usa | Cosa restituisce |
|---|---|---|
| `…/module/myaiclaude/cron?secret=…&action=…` | Lo scheduler del suo server | Una risposta in testo semplice come **N products have been updated.**, **N categories have been updated.**, **No products to update.**, **No categories to update.** o uno dei messaggi della tabella successiva. |
| `…/module/myaiclaude/ajax` | Le schermate del back office del modulo stesso | Nulla di utile se aperto a mano. Risponde solo alle richieste che portano il segreto delle schermate. |

| Messaggio dall'indirizzo cron | Significato | Cosa fare |
|---|---|---|
| Cron Job feature is disabled. You can enable it from the module settings. | **Enable Cron Feature** è su **No**. | Lo imposti su **Yes** e salvi. |
| The token does not exist or it's wrong! | Il segreto nell'indirizzo non corrisponde a nessun segreto salvato. | Copi di nuovo l'indirizzo dalla pagina **Cron**. |
| Invalid action! | La parte `&action=` manca o è scritta in modo errato. | Aggiunga `&action=generateProductContent` o `&action=generateCategoryContent`. |
| All must include all mandatory parameters! | Manca una scelta obbligatoria, più spesso il modello di prompt. | Scelga un modello nel modulo e clicchi su **Save**. |
| updatedField parameter is wrong! | Il campo non è uno dei campi consentiti. | Scelga il campo nel modulo e salvi. |
| productTarget parameter is wrong! Allowed values: pendingClaude, pendingField, emptyField. | La destinazione nell'indirizzo è scritta in modo errato. | Usi uno dei tre valori. |
| No valid product IDs provided. | La **Product ID list** non contiene numeri. | Corregga l'elenco o lo svuoti. |
| Error!… | Claude o il negozio hanno restituito un errore. Il testo dopo la parola Error lo spiega. | Legga il testo, veda il capitolo 5. |

Gli hook del modulo per la vetrina sono vuoti, quindi non aggiunge alcun output alle pagine del suo negozio.

## 5. Risoluzione dei problemi

### 5.1 Menu e schermate

| Sintomo | Causa | Su cosa cliccare |
|---|---|---|
| **AI Content Generator** non è nel menu. | La cache non è stata svuotata, il modulo è disattivato o il dipendente non ha accesso. | **Advanced Parameters → Performance → Clear cache**. Controlli **Modules → Module Manager**. Controlli **Advanced Parameters → Team → Permissions**. |
| Ogni indirizzo del modulo riporta alla dashboard principale. | Il modulo è disattivato. | Lo attivi nel **Module Manager**. |
| Il pannello **Modules → My AI Claude** nella pagina prodotto è vuoto. | **Product edit page Form** e **Product Edit History** sono entrambi disattivati. | Ne attivi almeno uno in **Settings → General**. |
| Il pannello prodotto non funziona su un nuovo prodotto. | Il prodotto non è ancora salvato. | Salvi il prodotto una volta, poi usi il pannello. |
| La scheda **History** manca nel pannello prodotto. | **Product Edit History** è disattivato. | Lo attivi in **Settings → General**. |
| Il blocco My AI Claude nella dashboard principale di PrestaShop mostra dati vuoti o a zero. | Il blocco della home non contiene i dati del report. | Apra **AI Content Generator → Dashboard** per i dati reali. |

### 5.2 Connessione a Claude

| Sintomo | Causa | Su cosa cliccare |
|---|---|---|
| Il messaggio dice che la chiave API di Anthropic Claude non è impostata (**The Anthropic Claude API key is not set. Add it in the module settings.**). | Nessuna chiave è salvata. | **Settings → Claude**, incolli la chiave in **Anthropic Claude API KEY**, **Save**. |
| **Anthropic Claude API KEY field is invalid!** | Il campo della chiave è vuoto e nessuna chiave è salvata. | Incolli la chiave e salvi. |
| Il messaggio inizia con **Anthropic Claude API Error** seguito da un testo di Anthropic. | Claude ha rifiutato la chiamata. I motivi tipici sono una chiave errata, un modello che il suo account non può usare, credito esaurito o troppe richieste. | Legga il testo dopo i due punti. Controlli la chiave, il credito e il modello nel suo account Anthropic. Scelga un altro **Model**. |
| **Claude request timed out after N seconds. The model may be overloaded, or the timeout is too low for this prompt.** | Claude ha risposto troppo lentamente. | Aumenti **API timeout (seconds)** in **Settings → General** (massimo 600) o riduca **Max Tokens**. Riprovi più tardi. |
| Un messaggio che inizia con **cURL Error** | Il server non riesce a raggiungere Claude, oppure un firewall lo blocca. | Chieda al suo hosting di consentire HTTPS in uscita verso `api.anthropic.com`. |
| Un nuovo modello Claude manca nell'elenco **Model**. | L'elenco contiene solo i nomi integrati e quelli che ha aggiunto. | Digiti il nome esatto in **Add a Claude model** e clicchi su **Add model**. |
| Dopo **Remove**, l'elenco **Model** mostra un modello che non appartiene a Claude. | Rimuovere il modello aggiunto attivo porta il negozio a un nome di ripiego che Claude non conosce. | Scelga un modello Claude in **Model** e clicchi su **Save**. |
| Il modulo dice **OpenAi Settings Updated** o **OpenAi Model field is invalid!**, la colonna **Provider** nella History mostra `openai`, la guida della pagina parla di un account OpenAI e l'esempio in **Add a Claude model** cita un nome GPT. | Sono testi residui della versione precedente del modulo. | Nulla. Il modulo parla solo con Claude. Legga quei testi come Claude. |
| Il pulsante **Module settings** nei moduli filtro di **Generate** apre una pagina sbagliata. | Il pulsante punta alle impostazioni di un altro modulo (My ChatGPT), non di My AI Claude. | Apra **Settings** nel menu superiore del modulo. |
| Il log di PrestaShop si riempie di righe sull'elenco dei modelli. | **Debug mode** è attivo. | Disattivi **Debug mode** in **Settings → General**. |

### 5.3 Problemi di generazione

| Sintomo | Causa | Su cosa cliccare |
|---|---|---|
| **Error! Prompt is missing or too short!** | Il prompt ha meno di 4 caratteri. | Scriva un prompt più lungo o scelga un modello. |
| **Error! Product not found!** | Il prodotto non esiste più. | Ricarichi l'elenco. |
| **The model hit the token limit … Increase "Max Tokens" …** | La risposta ha consumato tutti i token prima di produrre testo. | Aumenti **Max Tokens** in **Settings → Claude**. |
| **The model returned an empty response.** | Claude non ha restituito testo. | Riprovi, riformuli il prompt o aumenti **Max Tokens**. |
| **The response was blocked by the provider content filter…** | Claude ha rifiutato l'argomento. | Riformuli il prompt. |
| Il testo si interrompe a metà frase. | **Max Tokens** è troppo basso. | Aumenti **Max Tokens**. Usi 1000 o più per una descrizione completa. |
| La descrizione contiene errori di ortografia, titoli non voluti, idee per H1 o elenchi di parole chiave. | Il modello predefinito lo richiede. | Modifichi il modello in **Settings → Prompt templates** (sezione 3.6). |
| Il testo è in inglese anche se il negozio è in un'altra lingua. | Un modello predefinito chiede l'inglese, oppure è stata selezionata la lingua sbagliata. | Modifichi il modello e selezioni la lingua giusta nell'esecuzione. |
| **The reply was rejected because it contains a forbidden word from the studio settings.** | Il **Quality gate** ha trovato una parola di **Forbidden words**. | Riesegua, rimuova la parola da **Studio** o disattivi **Quality gate**. |
| **Monthly generation budget reached. Raise it in the studio settings or wait until next month.** | Il numero di generazioni di questo mese ha raggiunto **Monthly generation budget**. | Aumenti il valore in **Settings → Studio** o lo imposti su 0. |
| **Error! The generated content could not be saved to the product.** | PrestaShop ha rifiutato il testo, per esempio un nome prodotto con caratteri non consentiti. | Legga i dettagli nella riga e in **History**. Modifichi il prompt e riesegua. |
| **Error! This PrestaShop version does not support the category Additional Description field.** | La sua versione di PrestaShop non ha quel campo. | Scelga un altro campo. |
| Una riga dice **Product skipped.** o **Category skipped.** | È selezionato **Skip if filled** e il campo ha già del testo. | Scelga **Replace** per sovrascrivere. |
| Dopo **Fill**, il vecchio testo è tornato. | Il modulo è stato salvato senza ricaricare la pagina. | Ricarichi la pagina del prodotto dopo ogni **Fill**, poi continui. |
| Un'esecuzione di massa si è fermata. | La pagina è stata chiusa o ricaricata. | Ricominci con **Update only** impostato sull'opzione per i prodotti non ancora aggiornati. Le chiamate fallite lì contano come aggiornate. |
| La pagina delle categorie ha un secondo modulo con **Generate content** che non fa nulla. | Quel modulo non è collegato. | Usi **Run on the categories below**. |
| **Error! This log entry has no previous value to restore.** | La riga della History non ha un testo precedente. | Modifichi il campo a mano. |
| Il risultato di **Try** non compare nel prodotto, ma esiste una riga della History. | **Try** non scrive mai nel prodotto. | Prema **Fill** per scriverlo. |

### 5.4 Foto e nuovi prodotti

| Sintomo | Causa | Su cosa cliccare |
|---|---|---|
| La scheda **Photos** le chiede di attivare il cercatore. | **AI Image Finder** è disattivato. | Lo attivi in **Settings → General** o in **Images**. |
| **Claude API key is not configured. Please check module settings.** | Nessuna chiave è salvata. | **Settings → Claude**. |
| **The search failed.** | Claude o la rete non hanno risposto. | Clicchi di nuovo su **Find pages**, controlli la chiave e il timeout. |
| **No photos were found on the suggested pages.** | Le pagine non avevano foto utilizzabili. | Cambi il nome o la descrizione del prodotto, oppure modifichi **AI Image Search Prompt**. |
| **URL not allowed (private network).** | L'indirizzo punta a una rete privata o locale. | Usi solo pagine web pubbliche. |
| **No images selected** | Non è stato selezionato nulla. | Selezioni almeno una foto. |
| **No images could be imported. Details: …** | Le foto non si sono potute scaricare o non erano immagini valide. | Legga i dettagli. Provi altre foto. |
| La foto di copertina è cambiata. | La prima foto selezionata diventa la copertina. | Riordini le foto nella pagina prodotto. |
| **Add an API key in the module settings first.** (**New product**) | Nessuna chiave è salvata. | **Settings → Claude**. |
| **Failed to parse AI response. Please try again.** | Claude ha restituito un testo che non è una bozza valida. | Clicchi di nuovo su **Generate data**. Descriva il prodotto in modo più dettagliato. |
| **Prompt is required**, **Invalid product data**, **Failed to create product** | La descrizione è vuota, la bozza è incompleta o PrestaShop non ha potuto salvare il prodotto. | Compili **What is the product?**, generi di nuovo, controlli l'ID della categoria. |

### 5.5 Problemi del cron

| Sintomo | Causa | Su cosa cliccare |
|---|---|---|
| L'indirizzo risponde **Invalid action!** | L'indirizzo cron copiato dalla pagina non ha la parte `&action=`. | Aggiunga `&action=generateProductContent` (prodotti) o `&action=generateCategoryContent` (categorie). |
| L'indirizzo risponde **Cron Job feature is disabled…** | **Enable Cron Feature** è disattivato. | Imposti **Yes** e **Save**. |
| **Generate Token** non fa nulla. | Il pulsante non è collegato in questa versione. | Digiti un segreto di almeno 24 lettere e cifre in **Cron Job Secret Token** e **Save**. Un segreto più corto viene sostituito da uno casuale la prossima volta che si apre una pagina di amministrazione. |
| L'indirizzo risponde **All must include all mandatory parameters!** | Il modulo non è mai stato salvato, quindi non c'è alcun modello memorizzato. | Scelga un **Prompt Template**, poi **Save**. |
| L'indirizzo risponde **No products to update.** mentre ci sono prodotti che hanno bisogno di testo. | **Selected Products** li esclude. **pendingClaude** salta ogni prodotto con una generazione riuscita, comprese le esecuzioni **Try**. | Usi **emptyField** o **pendingField**, oppure imposti la **Product ID list**. |
| Il testo di un prodotto è stato riscritto di nuovo. | Il cron sostituisce sempre il campo. | Usi **emptyField** per toccare solo i campi vuoti. |
| **Error!Monthly generation budget reached.** | Il budget mensile è esaurito. | Lo aumenti in **Settings → Studio**. |
| **Error! Could not save product N: … (X product(s) updated before this one.)** | PrestaShop ha rifiutato il testo per il prodotto N. | Corregga quel prodotto o lo escluda, riesegua. |
| Il comando nella pagina non cambia quando modifica il modulo. | Il comando mostra solo l'indirizzo di base. | Aggiunga `&action=` da sé. I valori del modulo vengono letti dalle impostazioni salvate. |
| L'intervallo nel modulo non ha effetto. | È una nota per lei. | Crei la pianificazione nel pannello del suo hosting. |

### 5.6 History e dati

| Sintomo | Causa | Su cosa cliccare |
|---|---|---|
| La Dashboard e la History sono vuote dopo **Clear list**. | **Clear list** elimina tutte le righe. | Non c'è nulla da ripristinare. Pianifichi le esportazioni prima di svuotare. |
| **This log entry no longer exists.** | La riga è stata eliminata. | Torni all'elenco. |
| **Update only** non mostra prodotti. | Il filtro usa le voci della History, e ogni prodotto ne ha già una. | Scelga **Update all**. |
| Alcuni prodotti sono esclusi da **Update only**. | Anche le chiamate fallite e le esecuzioni **Try** contano come voci. | Scelga **Update all**. |

## 6. Per gli sviluppatori

### 6.1 Panoramica

My AI Claude (`myaiclaude`, versione 1.1.0, autore MyPresta.eu) è un modulo PrestaShop per la scheda `front_office_features`. Supporta PrestaShop da 1.6 a 9.99.99 e PHP 7.0 e successivo. Chiama l'API Messages di Anthropic Claude all'indirizzo `https://api.anthropic.com/v1` (endpoint `/messages`) e scrive i risultati in prodotti e categorie.

- La classe `myaiclaude` in `myaiclaude.php` contiene installazione, disinstallazione, pagine di configurazione e hook.
- La classe `MyAIClaude\OpenAIService` (`src/OpenAIService.php`) è il client. Invia `model`, `max_tokens`, `messages`, un `system` facoltativo e un `temperature` facoltativo, con le intestazioni `x-api-key` e `anthropic-version: 2023-06-01`. Top P e le due penalità vengono salvati ma non inviati. Associa `input_tokens` e `output_tokens` ai token inviati e ricevuti. `listModels()` risponde sempre che l'elenco dei modelli è fornito dal catalogo del modulo, quindi l'elenco dei modelli è l'insieme integrato più i nomi conservati in `EXTRA_MODELS`. Il timeout è limitato a 10–600 secondi. Quando l'API risponde 400 e nomina un parametro, il client scarta quel parametro, riprova e ricorda la decisione per modello in `MODEL_CAPS`.
- La classe `MyAIClaude\Studio` (`src/Studio.php`) avvolge i prompt con la riga della lingua, voce, pubblico, tono, glossario e termini vietati, applica il budget mensile e il filtro delle parole vietate e costruisce il prompt del pacchetto SEO.
- Le schede della pagina di configurazione usano i parametri URL `mac_tab` (`dashboard`, `settings`, `updates`) e `mac_sub` (`general`, `openai`, `studio`, `templates`, `playground`). Il valore `openai` di `mac_sub` apre la scheda Claude. La Dashboard usa `mcg_preset` e le date `mac_from` e `mac_to`.
- Le classi CSS del back office usano il prefisso `.mac-`.
- I lavori di massa eseguono un elemento per richiesta AJAX da `back.js`.

### 6.2 File

| Percorso | Scopo | Note |
|---|---|---|
| `myaiclaude.php` | Classe del modulo | Installazione, disinstallazione, moduli, hook, posizionamento della scheda. |
| `autoload.php` | Loader per il namespace `MyAIClaude\` | |
| `src/OpenAIService.php`, `src/Studio.php` | Client API e regole di Studio | |
| `controllers/admin/AdminMyAIClaude*.php` | Controller del back office | Vedere 6.3. |
| `controllers/front/ajax.php`, `controllers/front/cron.php` | Controller front | AJAX e cron. |
| `lib/updateChecker.php` | Controllo aggiornamenti di MyPresta | Contatta `dev.mypresta.eu/update/get.php`. |
| `lib/sectionHelp.php` | Testi del cassetto **Help** | |
| `lib/prestashop9compatibility.php` | Helper di compatibilità | |
| `lib/searchTool` | Helper di autocompletamento per i moduli di amministrazione | |
| `views/templates/` | Template Smarty | Hook, pagine di amministrazione, pannelli di massa. |
| `views/js/` | `back.js`, `product-fields.js`, `image-finder.js`, `admin-products-bulk.js`, `dashboard.js`, `admin-help.js`, `chart.min.js` | |
| `views/css/` | Stili con il prefisso `.mac-` | |
| `translations/` | 34 file di lingua | |
| `upgrade/index.php` | Segnaposto | Il modulo non ha script di aggiornamento. |

### 6.3 Controller

| Controller | Menu o percorso | Ruolo |
|---|---|---|
| AdminMyAIClaudeMain | **AI Content Generator** sotto **Modules** | Reindirizza alla Dashboard. Genitore delle schede nascoste. |
| AdminMyAIClaude | Scheda nascosta **Mass Content Creator** | Generate: prodotti e categorie. |
| AdminMyAIClaudeProductCreator | Scheda nascosta **AI Product Creator** | New product. |
| AdminMyAIClaudeSettings | Scheda nascosta **Module Settings** | Reindirizza alla scheda Settings. |
| AdminMyAIClaudeCron | Scheda nascosta **Cron Job Settings** | I due moduli cron. |
| AdminMyAIClaudeUsage | Scheda nascosta **Module Log and Usage** | History. |
| AdminMyAIClaudeImageFinder | Scheda nascosta **AI Image Finder** | Images. |
| Front `ajax` | `module/myaiclaude/ajax` | Azioni `initiatePrompt`, `updateProduct`, `updateCategory`, `initiateProductRestore`, `updateSettings`, `generateAltTexts`, `generateSeoPack`. Richiede `secret_token` uguale a `TOKEN`. Non è legato a una sessione di dipendente. Nessuna schermata di questa versione chiama `generateAltTexts`. |
| Front `cron` | `module/myaiclaude/cron` | Richiede `secret` uguale a `SECRET` o `CAT_SECRET` e `ENABLE_CRON=1`. Parametri: `action` (`generateProductContent`, `generateCategoryContent`), `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug`, `categories`, `productIds`, `categoryTarget`, `categoriesToUpdate`. I parametri mancanti vengono letti dalle impostazioni salvate. |

Le schede figlie vengono create con `active=0` sotto `AdminMyAIClaudeMain`. Su `displayBackOfficeHeader` il modulo colloca la scheda principale sotto la scheda genitore Modules, la rinomina e rigenera i segreti più corti di 24 caratteri. La classe dell'icona è `icon-openai`. La scheda Image Finder viene registrata su richiesta e contrassegnata da `IMAGEFINDER_TAB_OK`.

Il cron dei prodotti accetta le destinazioni `pendingClaude`, `pendingField` e `emptyField` e conta solo le righe di log il cui stato non è `error`. Il filtro **Update only** di Generate conta ogni riga di log. Le righe di log del cron usano il metodo `cron`.

### 6.4 Hook

| Hook | Comportamento | Note |
|---|---|---|
| `displayAdminProductsExtra` | Mostra il pannello **Modules → My AI Claude** | Schede Generate, Simulate, Photos, History. |
| `displayBackOfficeHeader` | Carica le risorse, colloca il menu, rigenera i segreti corti | Viene eseguito su ogni pagina di amministrazione. |
| `displayBackOfficeTop` | Mostra la scorciatoia della barra superiore | |
| `dashboardZoneTwo` | Mostra `dashboard.tpl` sulla dashboard di PrestaShop | Il template viene reso senza le sue variabili di report. |
| `displayAdminProductsMainStepLeftColumnMiddle`, `displayAdminProductsMainStepLeftColumnBottom` | Registrati, restituiscono una stringa vuota | |
| `actionProductFormBuilderModifier` | Registrato, non fa nulla | |
| `displayHeader`, `displayFooter` | Registrati, vuoti | La vetrina non riceve alcun output. |

Il modulo non ha un metodo `enable()` né `disable()`. `displayCustomTop` e `top.tpl` esistono ma non vengono chiamati.

### 6.5 Override

Il modulo non ha una cartella `override` e non modifica alcun file del core. Le foto dei prodotti vengono scritte con le classi immagine di PrestaShop e il modulo scrive prodotti e categorie con gli oggetti di PrestaShop (`Product`, `Category`, `Tag::addTags`).

### 6.6 Database

Tabelle (prefisso come nel suo negozio, motore come PrestaShop):

| Tabella | Colonne | Note |
|---|---|---|
| `myaiclaude_prompt` | `id_prompt` (chiave primaria), `status`, `title`, `prompt`, `date_generated` | Contiene i 16 modelli installati e i suoi. |
| `myaiclaude_log` | Prompt, risposta, stato, tipo, modello, ID prodotto o categoria, lingua, dipendente, conteggi dei token, durata, data | Una riga per chiamata. Le colonne dei token vengono aggiunte su richiesta nelle installazioni più vecchie. |

Le scritture di prodotti e categorie toccano le tabelle del core dei dati modificati (`product`, `product_lang`, `category_lang`, `tag`, `image` e le tabelle correlate). La disinstallazione elimina entrambe le tabelle del modulo.

### 6.7 Chiavi e traduzioni

Le chiavi di configurazione usano il prefisso `MYPRESTA_MYAICLAUDE_`.

| Chiave (dopo il prefisso) | All'inizio | Significato |
|---|---|---|
| `LIVE_MODE`, `DEBUG_MODE` | 0 | Etichetta e log di debug. |
| `TIMEOUT` | 120 | Timeout dell'API. |
| `PRODUCT_LOG`, `TOPCTA`, `PRODUCT`, `IMAGEFINDER_ENABLE` | 1 | Interruttori della pagina General. |
| `IMAGEFINDER_PROMPT` | Testo predefinito | Usa `{product_name}` e `{product_description}`. |
| `API_KEY` | Un singolo spazio | Chiave Anthropic. |
| `MODEL`, `EXTRA_MODELS`, `MODEL_CAPS` | `claude-sonnet-4-5`, vuoto, vuoto | Modello attivo, modelli aggiunti, supporto dei parametri appreso. |
| `TEMPERATURE`, `MAX_TOKENS`, `TOP_P`, `FREQ_PEN`, `PRES_PEN` | 0.7, 3200, 1, 0, 0 | Campi di campionamento. Gli ultimi tre non vengono inviati. |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | Vuoto | Campi di testo di Studio. |
| `BUDGET`, `QUALITY` | 0, 1 | Budget mensile e quality gate. |
| `TOKEN` | 32 caratteri casuali | Segreto AJAX. |
| `SECRET`, `CAT_SECRET` | 32 caratteri casuali | Segreti del cron dei prodotti e delle categorie. |
| `ENABLE_CRON` | 0 | Interruttore del cron. |
| `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | 6 | Note sull'intervallo. |
| `updatedField`, `productTarget`, `productsToUpdate`, `promptTemplateId`, `languageId`, `interval_select`, `debug`, `productIdsList` | description, pendingClaude, 5, vuoto, lingua predefinita, vuoto, 0, vuoto | Modulo salvato del cron dei prodotti. |
| `catupdatedField`, `categoryTarget`, `categoriesToUpdate`, `catpromptTemplateId`, `catlanguageId`, `catdebug`, `categories` | description, pendingClaude, 5, vuoto, lingua predefinita, 0, vuoto | Modulo salvato del cron delle categorie. |

Le schermate Generate salvano anche le ultime scelte dei filtri in chiavi come `FIELD`, `LANGUAGE`, `CONTENT`, `DELAY`, `EXISTING`, `HISTORY`, `STATUS`, `STOCK`, `CATEGORIES`, `BRANDS`, `CATEGORIESC` e diverse chiavi `PROD_*`. La disinstallazione non le elimina, e nemmeno `mypresta_updates`, `update_myaiclaude` e `updatev_myaiclaude` del controllo aggiornamenti. La disinstallazione rimuove le altre chiavi e le chiavi più vecchie del fornitore precedente.

I testi di aiuto dei campi dei moduli sono costruiti con `fieldHelp()` nelle tre parti **What it does**, **How to configure** e **Effect**. Le stringhe passano attraverso il sistema di traduzione di PrestaShop (domini di traduzione del modulo e del controller). Per aggiungere una lingua, collochi un file `translations/<iso>.php`. I testi del cassetto Help provengono da `lib/sectionHelp.php`. Le risposte del cron, i prompt di Studio e i testi dei prompt predefiniti sono semplici stringhe inglesi nel codice.

### 6.8 Estensione

- Aggiunga modelli con il campo **Add a Claude model**, oppure aggiungendo l'id a `EXTRA_MODELS`.
- Aggiunga prompt come modelli, oppure invii il suo testo tramite le azioni `ajax` con il segreto.
- I segnaposto vengono sostituiti in `controllers/front/ajax.php`. I segnaposto `{cms_title}`, `{brand_name}`, `{brand_description}` e `{brand_short_description}` vengono riconosciuti quando la richiesta porta un ID di pagina CMS o di marchio. Nessuna schermata di questa versione invia quegli ID.
- Costruisca una propria pianificazione con l'indirizzo del cron e i suoi parametri (sezione 6.3).
- Il modulo non rende alcun template della vetrina, quindi un tema non ha nulla da sovrascrivere.

## 7. Aiuto

Pagina del modulo: https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-claude-ai.html

Per ottenere supporto:

1. Acceda a mypresta.eu.
2. Vada su **contact**.
3. Scelga **Support for paid modules**.
4. Scriva il nome del modulo (My AI Claude), la sua versione (1.1.0), le versioni di PrestaShop e PHP e cosa ha fatto prima che comparisse il problema. Aggiunga il testo del messaggio che vede.
