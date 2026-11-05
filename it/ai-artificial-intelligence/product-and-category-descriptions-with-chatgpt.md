---
title: "My ChatGPT - generazione di contenuti AI - documentazione e manuale d'uso"
description: "Utilizzi questo manuale per configurare OpenAI, generare i testi del catalogo con il modulo che possiede già e risolvere i problemi quando una generazione non riesce."
sidebar:
  label: "My ChatGPT - generazione di contenuti AI - documentazione e manuale d'uso"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Product and Category Descriptions with ChatGPT su MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/product-and-category-descriptions-with-chatgpt.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ai-artificial-intelligence/product-and-category-descriptions-with-chatgpt/)
>
> ---


## 1. Requisiti

Verifichi questi punti prima di collegare il modulo a OpenAI.

- Utilizzi PrestaShop 1.6, 1.7, 8 o 9 (fino alla 9.99.99).
- Utilizzi PHP 7.0 o successivo. Il programma di installazione si rifiuta di proseguire con una versione di PHP più vecchia.
- Abiliti le estensioni PHP cURL e JSON. Ogni chiamata a OpenAI e il controllo degli aggiornamenti usano cURL. Abiliti anche mbstring, perché la pulizia del testo nella ricerca immagini e nella schermata del nuovo prodotto la utilizza.
- Usi il campo facoltativo **URL sorgente opzionale** in **Nuovo prodotto** solo quando PHP può leggere pagine web (l'impostazione `allow_url_fopen`) e l'estensione DOM è disponibile. Senza di essi il campo viene ignorato e si usa solo il suo brief.
- Disponga di un proprio account OpenAI e di una chiave API da platform.openai.com. La chiave deve poter richiamare il modello scelto. Ogni richiesta viene pagata a OpenAI. Il modulo non include credito.
- Consenta al server di raggiungere internet sulla porta 443. Il negozio contatta OpenAI a ogni generazione e il server di aggiornamento di MyPresta.eu per il controllo degli aggiornamenti.
- Aggiunga un'attività pianificata (CRON) sul server solo se vuole che la generazione avvenga senza che nessuno faccia clic. Gli indirizzi cron non fanno nulla finché il server non li richiama.
- Non è richiesto nessun altro modulo PrestaShop.
- Pianifichi del tempo per i cataloghi grandi. Ogni campo in ogni lingua è una richiesta separata a OpenAI. Un'esecuzione di massa su 500 prodotti con quattro campi e due lingue invia 4000 richieste, una dopo l'altra, e tiene occupata la scheda del browser. Inizi con piccoli lotti di prova oppure usi i lotti cron per i cataloghi grandi.

## 2. Installazione

1. Apra **Moduli**, poi **Gestione moduli**.
2. Faccia clic su **Carica un modulo** e carichi il file ZIP.
3. Faccia clic su **Installa** su **My ChatGPT - Generazione di contenuti AI**.
4. Apra **Moduli** nel menu a sinistra. Vi compare una nuova voce **Generatore di Contenuti AI**. Faccia clic su di essa per aprire la **Dashboard** del modulo. **Configura** in **Gestione moduli** apre lo stesso punto.

L'installazione esegue le seguenti operazioni:

- Aggiunge la voce di menu **Generatore di Contenuti AI** sotto **Moduli**. Tutte le altre schermate del modulo si raggiungono dal menu superiore del modulo stesso e non hanno voci di menu separate.
- Crea due tabelle: una per i modelli di prompt e una per la cronologia di ogni generazione.
- Aggiunge 16 modelli di prompt già pronti (nomi prodotto, descrizioni, meta titoli, meta descrizioni e tag). Sono tutti abilitati.
- Crea lunghi valori segreti per le chiamate interne del modulo e per i due indirizzi cron.
- Disattiva il filtro HTML valido per tutto il negozio (HTMLPurifier). Le descrizioni e i testi delle categorie mantengono allora i tag HTML, ma lo stesso interruttore è disattivato per ogni altro testo del negozio. Lo riattivi nelle impostazioni del negozio se non lo desidera.
- Non svuota la cache di PrestaShop. La svuoti in **Parametri avanzati**, poi **Prestazioni**, solo se restano visibili vecchi stili o una vecchia schermata.

Se il programma di installazione mostra «Questo modulo richiede PHP 7.0.0 o versioni successive», aggiorni prima PHP. Se mostra «Impossibile creare le tabelle del database del modulo.», verifichi che l'utente del database possa creare tabelle, poi installi di nuovo.

Disinstallazione:

- Rimuove le voci di menu, entrambe le tabelle (tutti i modelli di prompt e l'intera **Cronologia** vanno persi) e quasi tutte le impostazioni del modulo, compresi la chiave API e i segreti cron.
- Non riattiva il filtro HTML. Lo riattivi lei stesso se lo desidera.
- Non elimina alcun testo di prodotto, testo di categoria o foto di prodotto creato dal modulo. Restano nel catalogo.
- Lascia alcuni residui innocui nella configurazione del negozio (la scelta salvata delle categorie cron, gli ultimi valori dei filtri di **Genera** e i valori del controllo aggiornamenti).
- Una nuova installazione crea nuovi segreti, una Cronologia vuota e di nuovo i 16 modelli predefiniti. I vecchi indirizzi cron smettono di funzionare, quindi li copi di nuovo.

## 3. Configurazione e lavoro nel back office

Apra **Moduli**, poi **Generatore di Contenuti AI**. Il menu superiore del modulo contiene queste voci: **Dashboard**, **Impostazioni**, **Genera**, **Nuovo prodotto**, **Cron**, **Cronologia**, **Immagini** e, a destra, **Aggiornamenti**. Un pulsante rotondo **Aiuto** in fondo a ogni schermata del modulo apre una breve spiegazione della schermata in cui si trova.

Le schermate di questo manuale provengono dal back office in inglese. I nomi di pulsanti, campi e schede sono indicati in questo manuale in italiano. Nella descrizione di ogni schermata, tra parentesi, compare il testo inglese visibile sullo schermo.

Segua questo procedimento:

1. Apra **Impostazioni**, poi **ChatGPT**. Incolli la chiave API di OpenAI e scelga un modello. Faccia clic su **Salva**.
2. Facoltativo: apra **Studio** e imposti tono di voce del brand, pubblico, tono, glossario, parole proibite, budget mensile e controllo qualità.
3. Apra **Modelli di prompt**. Esamini i 16 modelli, li modifichi o aggiunga i propri e lasci abilitati solo quelli che il suo team deve usare.
4. Generi il testo nel modo più adatto al lavoro:
   - Un prodotto: apra il prodotto, la scheda **Moduli**, e usi **Genera**, **Simula** o **Foto**. Funzionano anche i piccoli pulsanti **Genera con AI** accanto ai campi di descrizione e meta.
   - Molti prodotti o categorie insieme: apra **Genera**, costruisca un elenco con i filtri e prema **Esegui**.
   - Un nuovo prodotto da un breve brief: apra **Nuovo prodotto**.
   - Lotti pianificati senza clic: apra **Cron** e aggiunga l'indirizzo all'utilità di pianificazione del server.
5. Controlli la **Cronologia** per vedere ogni prompt, risposta, errore e numero di token. Controlli la **Dashboard** per totali e grafici.

Il modulo non ha stati in stile ordine. Un modello di prompt è **Abilitato** o **Disabilitato**. Ogni chiamata nella **Cronologia** è **Successo** o **Errore**. Un'esecuzione di massa o cron termina quando l'ultimo elemento è stato scritto, e il testo viene salvato sul prodotto o sulla categoria non appena arriva ciascuna risposta.

Se **CTA barra superiore Admin** è attivo, un piccolo pulsante a bacchetta magica **My ChatGPT** compare nella barra superiore di ogni pagina del back office. Apre una piccola finestra con un elenco di modelli, un campo di testo e **Genera**. Funziona come il **Playground** (sezione 3.6): la risposta viene mostrata nella finestra e nulla viene salvato nel catalogo.

Nell'elenco prodotti di **Catalogo**, **Prodotti**, il modulo aggiunge anche un pulsante **My ChatGPT** che apre **Genera**.

### 3.1 Dashboard

Apra **Generatore di Contenuti AI**, **Dashboard**. Questa pagina è un resoconto. Non scrive mai testi di prodotto o di categoria.

![Dashboard (Dashboard)](https://mypresta.eu/docs/images/docs/mychatgpt-dashboard.webp)

- Faccia clic su un pulsante di periodo: **Oggi**, **7 giorni**, **30 giorni** (aperto per impostazione predefinita), **90 giorni**, **Questo mese** o **Tutto il tempo**. Oppure digiti **Da** e **A** e faccia clic su **Applica**.
- La riga **Servizio attivo** mostra ChatGPT e il modello salvato in **Impostazioni**, **ChatGPT**.
- Legga le schede **Richieste**, **Successo**, **Errori**, **Token inviati** e **Token ricevuti** per il periodo scelto. **Richieste** conta ogni chiamata memorizzata nella **Cronologia**. **Errori** conta quelle non riuscite. I token inviati sono la dimensione della sua istruzione, i token ricevuti la dimensione della risposta.
- Legga i grafici **Richieste ed errori**, **Token inviati e ricevuti** e **Richieste per modello**.
- Grafici vuoti significano che in quel periodo non è stato generato nulla. Cambiare le date ridisegna soltanto la pagina. Non viene eliminato nulla.

### 3.2 Impostazioni – Generale

Apra **Impostazioni**, poi **Generale**. Dopo ogni modifica faccia clic su **Salva**. Vedrà «Impostazioni aggiornate».

![Impostazioni generali (General settings)](https://mypresta.eu/docs/images/docs/mychatgpt-settings-general.webp)

| Campo | Predefinito | Cosa fa |
|---|---|---|
| **Modalità live** | No | Segnala che il modulo gira sul negozio reale e non su una configurazione di prova. La attivi in produzione. Disattivata, gli strumenti restano gli stessi ma si segnala che non è la configurazione di produzione. |
| **Modalità debug** | No | Scrive ulteriori dettagli tecnici quando una chiamata a OpenAI fallisce. La attivi solo mentre indaga su un problema. I dettagli compaiono in **Parametri avanzati**, **Log**. I clienti non li vedono mai. |
| **Timeout API (secondi)** | 120 | Quanto può durare una chiamata a OpenAI prima che il modulo si arrenda. 120 è adatto alle descrizioni normali. Lo alzi fino a 600 per testi lunghi o modelli lenti. I valori inferiori a 10 vengono portati a 10, quelli superiori a 600 abbassati a 600, e un valore vuoto o non numerico diventa 120. Un timeout breve fallisce subito e scrive un errore nella Cronologia. |
| **Cronologia modifiche prodotto** | Sì | Aggiunge nella pagina del prodotto un elenco **Cronologia** con un pulsante **Ripristina**, così i redattori possono rimettere un testo precedente. Disattivato nasconde quell'elenco. Le righe restano comunque nella **Cronologia**. |
| **CTA barra superiore Admin** | Sì | Aggiunge il pulsante di scelta rapida **My ChatGPT** alla barra superiore del back office in ogni pagina. Disattivato rimuove solo quel pulsante. La voce di menu **Generatore di Contenuti AI** resta. |
| **Modulo pagina di modifica prodotto** | Sì | Mostra il pannello del generatore (**Genera**, **Simula**, **Foto**) nella scheda **Moduli** del prodotto e i pulsanti **Genera con AI** accanto ai campi di descrizione e meta. Disattivato li nasconde. Usi No quando devono essere usati solo la generazione di massa e il cron. |
| **Ricerca immagini AI** | Sì | Permette a un redattore di chiedere al modello pagine web che probabilmente mostrano foto del prodotto corrente. Attivato mostra la scheda **Foto** sul prodotto. Disattivato la nasconde. Non viene scaricato nulla finché qualcuno non conferma le foto. Lo stesso interruttore è in **Immagini** (sezione 3.12). |
| **Prompt di ricerca immagini AI** | Testo lungo predefinito | L'istruzione inviata quando qualcuno cerca foto. Per impostazione predefinita chiede esattamente cinque indirizzi di pagina come semplice elenco, preferendo le pagine dei produttori, i grandi rivenditori e i cataloghi. Le parole `{product_name}` e `{product_description}` vengono sostituite con il prodotto corrente. Mantenga la richiesta di un semplice elenco di indirizzi. Un prompt preciso restituisce pagine pertinenti. Un prompt vago restituisce link non correlati. Lo stesso testo è in **Immagini**. |

### 3.3 Impostazioni – ChatGPT

Apra **Impostazioni**, poi **ChatGPT**. Il form si intitola **Impostazioni OpenAI**. Ogni generazione, compresi i pulsanti del prodotto, le esecuzioni di massa e il cron, usa questi valori. Faccia clic su **Salva**. Vedrà «Impostazioni OpenAI aggiornate».

![Impostazioni ChatGPT (ChatGPT settings)](https://mypresta.eu/docs/images/docs/mychatgpt-settings-chatgpt.webp)

| Campo | Predefinito | Cosa fa |
|---|---|---|
| **CHIAVE API OpenAI** | Vuoto | Il segreto che permette a questo negozio di richiamare il suo account OpenAI. Incolli la chiave creata su platform.openai.com nel suo account OpenAI. Gli spazi intorno vengono rimossi al salvataggio. Lasci il campo intatto per mantenere la chiave già memorizzata. Una chiave vuota o errata fa fallire ogni generazione, e l'errore viene scritto nella Cronologia. Se salva una nuova chiave più corta di 10 caratteri mentre non c'è nessuna chiave memorizzata, vedrà «Il campo CHIAVE API OpenAI non è valido!». |
| **Modello** | gpt-3.5-turbo | Il modello ChatGPT che scrive il testo. L'elenco contiene i modelli integrati (gpt-4o, gpt-4o-mini, gpt-4-turbo, gpt-4, gpt-3.5-turbo, o4-mini, o3-mini, o1-mini e altri) e i modelli che ha aggiunto. Ne scelga uno e faccia clic su **Salva**. Un modello che la sua chiave non può usare restituisce un errore di OpenAI invece del testo. Un modello vuoto dà «Il campo Modello OpenAI non è valido!». |
| **Aggiungi un modello ChatGPT** | Vuoto | Aggiunge un nome di modello che non è nell'elenco integrato. Digiti il nome esatto dal suo account OpenAI (ad esempio `gpt-4.1`) e faccia clic su **Aggiungi modello**. Il nome compare in **Modello** e diventa il modello attivo. **Rimuovi** accanto a un nome aggiunto lo elimina. I nomi integrati non possono essere rimossi. Se rimuove il modello aggiunto attivo, il modulo passa a gpt-4o. Messaggi: «Modello aggiunto.», «Quel modello è già integrato.», «Modello rimosso.», «I modelli integrati non possono essere rimossi.», «Inserisci un ID modello come gpt-4.1.». |
| **Max Token** | 3200 | Il limite superiore della lunghezza di una risposta, contato in token, non in parole. Usi circa 256 per una meta descrizione e 1000 o più per una descrizione HTML completa. Troppo basso taglia la risposta. Troppo alto consente testi lunghi e fa salire il conto di OpenAI. Un valore 0 viene trattato come vuoto e sostituito da 256. |
| **Temperatura** | 0.7 | Con quanta libertà il modello sceglie le parole. Resti tra 0 e 1. Usi circa 0.2 per specifiche e testi meta e circa 0.7 per le descrizioni. Modifichi questo valore oppure **Top P**, non entrambi. Valori bassi ripetono una struttura simile. Valori alti variano di più e possono allontanarsi dal brief. Un valore 0 viene trattato come vuoto e sostituito da 0.7. |
| **Top P** | 1 | Un altro modo di limitare quanto può sorprendere la parola successiva. 1 considera l'intero intervallo. Lasci 1 se ha già impostato la **Temperatura**. Un valore più basso come 0.9 dà un vocabolario più ristretto. Un valore 0 viene sostituito da 1. |
| **Valore penalità di frequenza** | 0 | Riduce le frasi che si ripetono all'interno di una risposta. Usi 0 a meno che le descrizioni continuino a copiare la stessa frase; in tal caso provi 0.3–0.6. Intervallo consentito da -2 a 2. Non confronta i prodotti tra loro. |
| **Valore penalità di presenza** | 0 | Spinge la risposta verso nuovi argomenti. Usi 0 per impostazione predefinita. Provi un piccolo numero positivo se ogni paragrafo dice la stessa cosa. Intervallo consentito da -2 a 2. Alcuni modelli più recenti ignorano questo campo. |

Il modulo impara da solo quali impostazioni un modello rifiuta (alcuni modelli di ragionamento respingono temperatura o penalità) e smette poi di inviargliele.

### 3.4 Impostazioni – Studio

Apra **Impostazioni**, poi **Studio**. Lo Studio aggiunge regole interne a ogni prompt: pulsanti del prodotto, esecuzioni di massa, cron e playground. I campi vuoti vengono saltati. Faccia clic su **Salva studio**. Vedrà «Impostazioni dello studio salvate.». Il testo già presente nel catalogo non viene riscritto.

![Impostazioni dello Studio (Studio settings)](https://mypresta.eu/docs/images/docs/mychatgpt-settings-studio.webp)

| Campo | Predefinito | Cosa fa |
|---|---|---|
| **Tono di voce del brand** | Vuoto | Dice al modello chi parla, così il testo si adatta al suo negozio e non a un assistente generico. Scriva un breve brief, ad esempio «officina specializzata, frasi brevi, niente enfasi». Ogni generazione successiva parte da questa voce. |
| **Pubblico** | Vuoto | Indica il lettore per cui scrivere, ad esempio «installatori professionisti» o «acquirenti alla prima esperienza». Le risposte usano vocabolario ed esempi rivolti a quel lettore. |
| **Tono** | Vuoto | L'atmosfera della formulazione: formale, cordiale, tecnica. Bastano una o due parole. Non cambia il modello né la temperatura. |
| **Glossario** | Vuoto | Nomi di marchi, materiali e grafie che il modello deve copiare esattamente. Inserisca un termine per riga. Il nuovo testo preferisce quelle grafie. I termini non elencati possono comunque essere riformulati. |
| **Parole proibite** | Vuoto | Parole e frasi che non devono comparire in una risposta salvata. Una per riga. L'elenco funziona solo quando il **Controllo qualità** è attivo. Una risposta che contiene una delle righe (anche all'interno di una parola più lunga) viene respinta, non viene scritta nel prodotto e viene memorizzata nella Cronologia come errore. |
| **Budget di generazione mensile** | 0 | Il numero massimo di generazioni riuscite che il negozio può eseguire nel mese di calendario corrente. Inserisca un numero intero. 0 significa nessun limite. Il contatore riparte il primo giorno del mese. Quando il tetto è raggiunto, le nuove generazioni si fermano con un messaggio sul budget. Le chiamate non riuscite non vengono contate. Playground, pulsanti del prodotto, esecuzioni di massa e cron contano tutti. |
| **Controllo qualità** | Sì | Controlla ogni risposta rispetto alle **Parole proibite** prima di salvare qualsiasi cosa. Attivo blocca una risposta corrispondente. Disattivo salva la risposta anche se contiene una parola dell'elenco. |

### 3.5 Impostazioni – Modelli di prompt

Apra **Impostazioni**, poi **Modelli di prompt**. Un modello è un'istruzione salvata che i redattori scelgono per titolo invece di digitare ogni volta lo stesso brief. Il titolo è solo un'etichetta per il menu a discesa. Il modello riceve il testo del prompt. I modelli abilitati compaiono nel pannello del prodotto, nel generatore di massa e nel form cron. Quelli disabilitati restano nell'elenco ma non vengono offerti (il form cron li elenca ancora, quindi ne scelga uno abilitato).

![Modelli di prompt (Prompt templates)](https://mypresta.eu/docs/images/docs/mychatgpt-settings-templates.webp)

L'elenco **Modelli di prompt** mostra **ID**, **Titolo**, **Prompt**, **Stato** e **Timestamp**, dal più recente, 50 per pagina.

- Faccia clic sul pulsante verde **+** per creare un modello.
- Faccia clic sul segno di stato in una riga per passare un modello da abilitato a disabilitato e viceversa.
- Usi **Modifica** o **Elimina** in una riga. Selezioni più righe e usi l'azione di gruppo **Elimina** (deve confermare «Sei sicuro di voler eliminare i prompt selezionati?»).

Il form **Genera modello di prompt**:

| Campo | Predefinito | Cosa fa |
|---|---|---|
| **Stato** | Disabilitato per un nuovo modello | Mostra o nasconde questo modello nei menu a discesa della pagina del prodotto, della generazione di massa e del cron. Abiliti i modelli che il suo personale deve usare. Disabiliti una bozza invece di eliminarla. |
| **Titolo del prompt** | Vuoto (obbligatorio) | Il nome che i redattori vedono nel menu a discesa, ad esempio «Descrizione HTML con caratteristiche». Non viene inviato al modello. |
| **Contenuto del prompt** | Vuoto (obbligatorio) | L'istruzione inviata al modello. La scriva come farebbe con un copywriter: lunghezza, HTML, lingua. I segnaposto vengono riempiti con i dati dell'elemento che si sta scrivendo. Le virgolette doppie vengono trasformate in virgolette semplici al salvataggio. |

Faccia clic su **Salva prompt**. Vedrà «Modello di prompt aggiunto con successo!» oppure «Modello di prompt aggiornato con successo!». **Torna alle impostazioni del modulo** riporta all'elenco. L'eliminazione mostra «Modello di prompt rimosso.».

Segnaposto che può usare in un modello:

| Per | Segnaposto | Sostituiti con |
|---|---|---|
| Prodotti | `{product_name}`, `{product_description}`, `{product_description_short}`, `{product_tags}`, `{product_reference}`, `{product_ean13}`, `{product_weight}` | Il valore di quel prodotto nella lingua che si sta scrivendo. |
| Prodotti | `{product_brand}`, `{product_default_category}`, `{product_category_description}`, `{product_categories}` | I dati di marchio e categoria del prodotto. |
| Prodotti | `{product_attributes}`, `{product_features}`, `{product_feature_values}`, `{product_images}` | Attributi separati da virgole, nomi delle caratteristiche, coppie nome:valore delle caratteristiche e indirizzi delle foto del prodotto. |
| Categorie | `{category_name}`, `{category_description}`, `{category_parent_name}` | La categoria e la sua categoria padre. |
| Prodotti e categorie | `{shop_name}`, `{shop_url}`, `{shop_language}`, `{shop_country}`, `{shop_currency}` | I dati del suo negozio. |

I 16 modelli predefiniti sono **Nome prodotto 1–2**, **Descrizione prodotto 1–7**, **Meta titolo prodotto 1–3**, **Meta descrizione prodotto 1–3** e **Tag prodotto**. Alcuni contengono formulazioni di esempio (ad esempio uno smartwatch). Li esamini prima della prima esecuzione di massa.

### 3.6 Impostazioni – Playground

Apra **Impostazioni**, poi **Playground**. Il playground è un blocco per gli appunti che richiama il modello attivo e mostra la risposta nella pagina. Lo usi per provare un prompt prima di salvarlo come modello, o per verificare che la sua chiave API funzioni.

![Playground (Playground)](https://mypresta.eu/docs/images/docs/mychatgpt-settings-playground.webp)

1. Digiti un'istruzione nel campo. Il suggerimento grigio dice «Chiedi al modello qualsiasi cosa sul tuo catalogo».
2. Faccia clic su **Genera**.
3. Legga la risposta e il numero di token sotto il pulsante.

La chiamata usa il modello, i valori di campionamento e le regole dello Studio che ha salvato. La risposta viene memorizzata nella Cronologia. Nessun prodotto, categoria o campo meta viene modificato. Scriva nomi e dettagli reali: i segnaposto tra parentesi graffe non vengono riempiti nel playground.

### 3.7 Genera – Prodotti

Apra **Genera**, poi la sottoscheda **Prodotti**. Lavori in due passi. Il passo 1 costruisce soltanto un elenco. Non viene inviato nulla a OpenAI e nulla viene salvato come impostazione del negozio.

![Genera prodotti (Generate products)](https://mypresta.eu/docs/images/docs/mychatgpt-generate-products.webp)

Passo 1 – il form **Filtra i prodotti da aggiornare**. Tutti i filtri si combinano. Un filtro lasciato vuoto viene ignorato.

| Campo | Predefinito | Cosa fa |
|---|---|---|
| **Categorie prodotto** | Nessuna selezione | Mantiene i prodotti delle categorie selezionate (compresi i prodotti la cui categoria predefinita è una di esse). Un albero vuoto lascia disattivato questo filtro. |
| **Marchio** | Seleziona marchio | Mantiene i prodotti di un produttore. L'opzione vuota comprende ogni marchio. |
| **Stato del prodotto** | Attivo | **Attivo** mantiene i prodotti in vendita, **Disabilitato** mantiene le bozze, **Entrambi** mantiene tutto. |
| **Stock del prodotto** | Tutti i prodotti | **Solo prodotti disponibili in stock** rimuove i prodotti senza quantità disponibile. **Tutti i prodotti** ignora lo stock. |
| **Aggiorna solo** | Aggiorna tutto | **Prodotti non ancora aggiornati con contenuti OpenAI** serve per un primo passaggio (prodotti senza riga nella Cronologia). **Prodotti già aggiornati con contenuti OpenAI** serve per la riscrittura. **Aggiorna tutto** ignora la Cronologia. |
| **ID prodotti** | Vuoto | Solo questi numeri di prodotto, separati da virgole, ad esempio 12,45,103. |
| **Riferimento prodotto** | Vuoto | Solo i prodotti con questi codici di riferimento, separati da virgole. |
| **Data di aggiunta prodotto da** | Vuoto | Esclude i prodotti creati prima di questa data e ora. |
| **Data di aggiunta prodotto a** | Vuoto | Esclude i prodotti creati dopo questa data e ora. |
| **ID prodotto minimo** | Vuoto | Salta i prodotti con un numero più piccolo. |
| **ID prodotto massimo** | Vuoto | Salta i prodotti con un numero più grande. |
| **Limite prodotti** | Vuoto | Il numero massimo di prodotti caricati nell'elenco, ad esempio 20. L'elenco non ne mostra mai di più, così un'esecuzione non può percorrere per caso l'intero catalogo. |

Faccia clic su **Vai al passo successivo**. **Impostazioni del modulo** apre la configurazione del modulo.

Passo 2 – il pannello **Generazione di massa prodotti** e la tabella dei prodotti (**ID**, **Riferimento**, **Risultato**):

| Campo | Predefinito | Cosa fa |
|---|---|---|
| **Modello** | Scegli un modello | Riempie il campo del prompt da un modello abilitato. Può anche digitare un prompt personale. Il titolo non viene inviato. Se il campo resta vuoto, il modulo usa un brief standard per ogni campo. |
| Campo del prompt | Vuoto | L'istruzione per ogni prodotto nella tabella. Se digita un solo testo, lo stesso testo viene usato per ogni campo scelto, quindi esegua un campo alla volta quando i campi richiedono formulazioni diverse. |
| **Cosa generare** | Descrizioni | **Descrizioni** scrive la descrizione lunga e quella breve. **Meta titolo e meta descrizione** scrive entrambi i campi meta. **Descrizioni e meta insieme** scrive tutti e quattro. Ogni campo è una richiesta separata. Nomi e tag vengono scritti dalla pagina del prodotto, non da qui. |
| **Testo esistente** | Sostituisci | **Sostituisci** sovrascrive. **Salta se compilato** lascia in pace un campo già compilato e non richiama il modello per esso. **Aggiungi sopra** e **Aggiungi sotto** mantengono il vecchio testo e vi accodano il nuovo. |
| **Lingue** | Lingua attuale selezionata | Selezioni ogni lingua da scrivere. Ogni lingua selezionata viene generata separatamente. Le lingue non selezionate mantengono il loro testo. |

Faccia clic su **Esegui sulla lista sottostante**. La riga di stato mostra l'avanzamento, ad esempio «3 / 40 – description». Ogni riga mostra i propri risultati non appena quel prodotto termina, ad esempio «description: success Content successfully generated and updated to product.», «description_short: skipped Product skipped.» oppure «meta_title: error …» con il motivo. Alla fine vedrà «Finished N products.». Senza alcuna lingua selezionata vedrà «Select at least one language.».

Tenga aperta la scheda del browser fino al termine dell'esecuzione. Chiuderla interrompe l'esecuzione, e i prodotti già scritti restano salvati. Per proseguire, ricostruisca l'elenco con **Aggiorna solo** impostato sui prodotti non ancora aggiornati. Un errore su un campo non annulla quelli già salvati. Inizi con un **Limite prodotti** piccolo, come 20, e controlli prima la formulazione.

### 3.8 Genera – Categorie

Apra **Genera**, poi la sottoscheda **Categorie**. I due passi funzionano come nella schermata dei prodotti.

![Genera categorie (Generate categories)](https://mypresta.eu/docs/images/docs/mychatgpt-generate-categories.webp)

Passo 1 – il form **Filtra le categorie da aggiornare**:

| Campo | Predefinito | Cosa fa |
|---|---|---|
| **Categorie** | Nessuna selezione | Sceglie le categorie per il passo successivo. Un albero vuoto non restringe l'elenco per categoria, quindi l'elenco contiene ogni categoria con lo stato scelto, compresa **Home** e la categoria radice. Selezioni le categorie desiderate. |
| **Stato della categoria** | Attivo | **Attivo**, **Disabilitato** o **Entrambi**. |

Faccia clic su **Vai al passo successivo**.

Passo 2 – il pannello **Generazione massiva di categorie** e la tabella delle categorie (**ID**, **Risultato**):

| Campo | Predefinito | Cosa fa |
|---|---|---|
| Campo del prompt (primo campo) | Vuoto | L'istruzione inviata per ogni categoria. Descriva tono, lunghezza e HTML. Nomini l'argomento nel testo. Questo campo non inserisce segnaposto di prodotto. Questo pannello non ha un selettore di modelli. |
| Elenco dei campi | Descrizione | Il campo da scrivere: **Descrizione**, **Nome**, **Meta titolo**, **Meta descrizione** o **Descrizione aggiuntiva**. Viene salvato solo quel campo. |
| Elenco del testo esistente | Sostituisci | **Sostituisci** sovrascrive. **Salta se compilato** lascia in pace un campo già compilato e non richiama il modello per quella categoria. |
| Elenco delle lingue | Lingua attuale | Una lingua. Esegua di nuovo per un'altra lingua. |

Faccia clic su **Esegui sulle categorie sottostanti**. I risultati compaiono per riga come nella schermata dei prodotti. Una categoria senza il campo **Descrizione aggiuntiva** nella sua versione di PrestaShop mostra «Error! This PrestaShop version does not support the category Additional Description field.».

Sotto la tabella la schermata mostra anche il form **Genera contenuto categoria**. La sua introduzione dice «This form writes the filtered categories. Press Generate content to start. Each category is saved as soon as its reply arrives.» In questa versione quel form non avvia un'esecuzione. Usi **Esegui sulle categorie sottostanti** sopra di esso. Il form ha questi campi:

| Campo | Predefinito | Cosa fa |
|---|---|---|
| **Campo da aggiornare** | Descrizione | Il campo di categoria che questo form riscriverebbe: **Nome categoria**, **Descrizione**, **Meta titolo**, **Meta descrizione** o **Descrizione aggiuntiva**. Solo quel campo viene inviato al modello e salvato. Gli altri campi restano come sono. Descrizione e meta sono esecuzioni separate. |
| **Dati esistenti** | Mantieni i dati esistenti e aggiungi il nuovo contenuto generato in alto | Cosa succede quando il campo scelto ha già del testo: **Mantieni i dati esistenti e aggiungi il nuovo contenuto generato in alto**, **Mantieni i dati esistenti e aggiungi il nuovo contenuto generato alla fine**, **Mantieni i dati esistenti e salta la categoria** oppure **Rimuovi i dati e aggiungi il nuovo contenuto generato**. Sostituire cambia il testo memorizzato. Saltare non richiama il modello per una categoria che ha già quel campo. Aggiungere mantiene entrambe le versioni in un solo campo. |
| **Lingua** | Prima lingua dell'elenco | La versione linguistica che viene scritta. Cambia solo quella lingua. |
| **Prompt del contenuto** | Vuoto (obbligatorio) | L'istruzione per ogni categoria dell'elenco. Descriva tono, lunghezza e HTML. Nomini l'argomento della categoria nel testo, perché i segnaposto di prodotto non vengono inseriti. |
| **Ritardo chiamate API** | Vuoto | Una pausa in secondi tra una categoria e la successiva, per non raggiungere il limite di frequenza di OpenAI. Usi 1 o 2 con una chiave di livello basso. Imposti 0 per inviare subito la richiesta successiva. Il pannello **Esegui** qui sopra non usa questa pausa. |

I pulsanti **Genera contenuto** e **Torna al filtro categorie** non generano testo. **Genera contenuto** memorizza soltanto i valori digitati e mostra di nuovo il filtro. **Impostazioni del modulo** apre la configurazione del modulo.

### 3.9 Nuovo prodotto

Apra **Nuovo prodotto**. Il pannello **Crea un prodotto da un brief** chiede al modello una bozza di prodotto e può inserire quella bozza come nuovo prodotto. Serve per prodotti che non sono ancora nel catalogo. Per compilare un prodotto esistente, usi **Genera** o la pagina del prodotto.

![Nuovo prodotto (New product)](https://mypresta.eu/docs/images/docs/mychatgpt-new-product.webp)

Se non è salvata nessuna chiave, vedrà «Aggiungi prima una chiave API nelle impostazioni del modulo.».

| Campo | Predefinito | Cosa fa |
|---|---|---|
| **Cos'è il prodotto?** | Vuoto (obbligatorio) | Il brief che il modello sviluppa in nome, descrizioni, meta, tag, caratteristiche, riferimento e prezzo. Scriva alcune frasi con materiale, pubblico e nomi che devono restare. Un campo vuoto viene rifiutato con «Prompt is required». |
| **URL sorgente opzionale** | Vuoto | Un indirizzo web completo di una pagina pubblica sul prodotto. Una pagina leggibile aggiunge al brief il proprio titolo, la descrizione e il testo del prezzo. Una pagina che non può essere letta viene ignorata. |
| **Lingua** | Lingua predefinita del negozio | La lingua in cui viene salvato il testo. Le altre lingue non vengono compilate. Scelga la lingua predefinita del negozio, perché PrestaShop richiede un nome nella lingua predefinita per creare un prodotto. |
| **ID categoria predefinita** | 2 | Il numero di categoria da **Catalogo**, **Categorie**. 2 di solito è **Home**. Il prodotto viene inserito in quella categoria, che diventa la categoria predefinita. |

1. Faccia clic su **Genera dati**. La bozza compare come testo nel campo sottostante (nome, descrizione, descrizione breve, meta titolo, meta descrizione, parole chiave, tag, riferimento, prezzo, caratteristiche). Non viene ancora salvato nulla. Faccia di nuovo clic per una nuova bozza. In questa schermata non può modificare la bozza.
2. Controlli la bozza, in particolare il prezzo e il riferimento suggeriti.
3. Faccia clic su **Crea prodotto**. La riga del risultato mostra «Product #» e il numero del nuovo prodotto.

Il nuovo prodotto è attivo, ordinabile, visibile nel catalogo e nella ricerca, in condizione nuovo, con il gruppo di regole fiscali numero 1, una giacenza di 100 pezzi e il prezzo suggerito. Nome, descrizioni, meta, tag e caratteristiche vengono salvati solo nella lingua scelta. Questa schermata non aggiunge foto. Apra il nuovo prodotto, scheda **Moduli**, **Foto**, per aggiungerle. Controlli prezzo, imposta, quantità e categoria prima di pubblicare. La generazione qui non viene registrata nella Cronologia e non conta per il budget mensile.

### 3.10 Cron

Apra **Cron**. Il cron è pensato per il server, non per una persona che fa clic su **Esegui**. Questa schermata memorizza le sue scelte e mostra gli indirizzi segreti che il suo server richiama secondo una pianificazione. Ogni chiamata reale scrive un piccolo lotto e si ferma. Il negozio non fa nulla finché il server non richiede l'indirizzo.

![Cron (Cron)](https://mypresta.eu/docs/images/docs/mychatgpt-cron.webp)

Il pannello superiore **Cron categorie** e il pannello **Parametri Cron** mostrano gli indirizzi del suo negozio con i segreti. Tratti i segreti come password: non pubblichi mai un indirizzo completo. Questo manuale li mostra come `YOUR_SECURE_KEY`, ad esempio `https://your-shop.example/module/mychatgpt/cron?secret=YOUR_SECURE_KEY`. A ogni indirizzo vanno aggiunte le impostazioni del form (campo, lingua, modello, dimensione del lotto e così via). La sezione 6.3 le elenca. Chieda al suo sviluppatore o al suo hosting di aggiungerle quando configura l'utilità di pianificazione.

Form dei prodotti **CRON JOB Settings – Generate product content using OpenAI**. Faccia clic su **Salva** dopo averlo modificato.

| Campo | Predefinito | Cosa fa |
|---|---|---|
| **Abilita funzione cron** | No | Permette al server di generare i testi di prodotti e categorie secondo una pianificazione. La attivi solo dopo aver salvato segreto, campo, lingua e modello. Finché è disattivata, ogni indirizzo cron risponde che la funzione è disabilitata. Questo unico interruttore è necessario anche per il cron delle categorie. |
| **Token segreto del job cron** | Lungo valore casuale | Una lunga password che deve far parte dell'indirizzo cron dei prodotti. Senza di essa il negozio rifiuta la chiamata. Conservi il valore generato. Cambiarlo invalida subito il vecchio indirizzo. Il pulsante **Genera token** in questa versione non crea un nuovo valore, quindi conservi il valore creato all'installazione. |
| **Campo da aggiornare** | description | L'unico campo di prodotto che questo cron scrive: name, description, description_short, meta_title, meta_description o tags. Per compilare più campi, crei più comandi cron. |
| **Prodotti selezionati** | pendingOpenAI | Decide quali prodotti sono ancora in attesa. **pendingOpenAI**: i prodotti che il modulo non ha ancora scritto (qualsiasi campo). **pendingField**: i prodotti non ancora scritti per questo campo specifico, così più comandi (ad esempio description e name) possono lavorare sugli stessi prodotti. **emptyField**: solo i prodotti in cui il campo scelto è vuoto. Ogni esecuzione salta i prodotti che non corrispondono più, quindi un catalogo completato smette di cambiare. |
| **Categorie prodotto** | Nessuna selezione | Limita l'esecuzione alle categorie selezionate. Un albero vuoto significa che la categoria non è un filtro. |
| **Elenco ID prodotto** | Vuoto | Limita l'esecuzione a questi numeri di prodotto, separati da virgole. Lettere e altri caratteri vengono rimossi al salvataggio. |
| **Lingua** | Lingua predefinita del negozio | La versione linguistica che viene scritta. Le altre lingue richiedono un comando proprio. |
| **Prodotti da aggiornare** | 5 prodotti | Quanti prodotti corrispondenti elabora una chiamata (2, 3, 5, 8, 10, 15, 20, 50, 100, 200, 300, 500 o 1000). Inizi con 5 o 10 in modo che un modello lento non superi il limite di tempo del server. |
| **Modello di prompt** | Primo modello dell'elenco | L'istruzione salvata usata per ogni prodotto dell'esecuzione. I segnaposto vengono riempiti per prodotto. Scelga un modello abilitato. |
| **Abilita debug** | No | Quando l'indirizzo viene aperto con il debug attivo, stampa il piano (impostazioni, prodotti selezionati, prompt finali) e non scrive nulla. Controlli un comando con esso una volta. Lo disattivi prima che l'utilità di pianificazione usi l'indirizzo. |
| **Intervallo del job cron** | Ogni ora | Il ritmo che prevede di usare (ogni 1, 2, 5, 10 o 30 minuti, ogni ora, ogni 2 o ogni 6 ore). Documenta il suo piano. Il modulo non avvia l'utilità di pianificazione. |
| **Comando del job cron prodotti** | – | Mostra la riga di comando da copiare nell'utilità di pianificazione. Salvi prima il form. |

Form delle categorie **CRON JOB Settings – Generate category content using OpenAI**. Ha un proprio segreto e un proprio pulsante **Salva**, e non ha bisogno di un proprio interruttore di abilitazione:

| Campo | Predefinito | Cosa fa |
|---|---|---|
| **Token segreto del job cron** | Lungo valore casuale | La password dell'indirizzo delle categorie. È separata dal segreto dei prodotti. Cambiarla invalida il vecchio indirizzo delle categorie. |
| **Campo da aggiornare** | description | L'unico campo di categoria scritto: name, description, meta_title o meta_description. |
| **Categorie selezionate** | pendingOpenAI | Le stesse tre regole dei prodotti, applicate alle categorie. **pendingField** permette a più comandi di condividere le stesse categorie. |
| **Lingua** | Lingua predefinita del negozio | La versione linguistica che viene scritta. |
| **Categorie da aggiornare** | 5 categorie | Quante categorie elabora una chiamata (da 2 a 1000). |
| **Modello di prompt** | Primo modello dell'elenco | Scriva il modello per una categoria, non per un prodotto, ad esempio con `{category_name}`. |
| **Abilita debug** | No | Stampa il piano e non salva le categorie. |
| **Intervallo del job cron** | Ogni ora | Il ritmo che prevede di usare. |
| **Comando del job cron categorie** | – | La riga di comando da copiare dopo il salvataggio. |

Il cron delle categorie non tocca mai **Home** né la categoria radice.

### 3.11 Cronologia

Apra **Cronologia**. La Cronologia è il registro di ciò che è stato richiesto e di ciò che è tornato. Aprire o filtrare la pagina non elimina nulla e non modifica alcun prodotto.

![Cronologia (History)](https://mypresta.eu/docs/images/docs/mychatgpt-history.webp)

La barra dei filtri si apre su **Questo mese**. Usi i pulsanti di periodo **Oggi**, **7 giorni**, **30 giorni**, **Questo mese** e **Tutto il tempo**, oppure **Da** e **A**. Può anche restringere per **Modello**, **Tipo**, **Stato** (**Qualsiasi**, **Successo**, **Errore**), **Lingua**, **Dipendente**, **ID prodotto / categoria** e **Il prompt o la risposta contengono**. Faccia clic su **Filtra**.

- Le schede mostrano **Richieste**, **Successo**, **Errori**, **Token inviati**, **Token ricevuti**, **Token totali** e **Tempo medio** per il filtro. Un trattino significa che OpenAI non ha restituito il conteggio dei token per quella chiamata.
- I pannelli **Per giorno**, **Per modello**, **Per tipo**, **Per lingua** e **Per dipendente** raggruppano le stesse righe per **Gruppo**, **Chiamate**, **Inviato**, **Ricevuto** e **Totale**. Un piccolo numero in corsivo accanto alle chiamate è il numero di errori.
- L'elenco **Cronologia dei prompt** ha le colonne **ID**, **Stato**, **Prompt**, **Risposta / Errore**, **Provider** (modello, codice di errore, secondi), **Inviato**, **Ricevuto**, **Totale**, **ID entità**, **Tipo** e **Timestamp**. Prompt e risposta sono abbreviati. Faccia clic su **Visualizza** in una riga per leggere il prompt completo e la risposta completa con i token, poi su **Torna all'elenco**. Una riga di errore mostra il testo dell'errore al posto di una risposta. **Tipo** mostra che cosa è stato scritto, ad esempio product_description o category_meta_title. Anche le simulazioni e il playground creano righe.
- Il pulsante **Svuota elenco** elimina tutte le righe in una volta, senza chiedere conferma, comprese quelle fuori dal suo filtro. Dopodiché i contatori della **Dashboard**, il filtro **Aggiorna solo**, la regola **pendingOpenAI** e il contatore del budget mensile ripartono da zero, e **Ripristina** non è più possibile per i vecchi testi.

### 3.12 Immagini

Apra **Immagini**. Questa pagina non scarica immagini. Attiva o disattiva la ricerca di immagini della pagina del prodotto e memorizza l'istruzione usata per quella ricerca.

![Immagini (Images)](https://mypresta.eu/docs/images/docs/mychatgpt-images.webp)

| Campo | Predefinito | Cosa fa |
|---|---|---|
| **Ricerca immagini AI** | Abilitato | **Abilitato** mostra la scheda **Foto** nella pagina di modifica del prodotto. **Disabilitato** la rimuove. Un'immagine viene importata solo dopo la conferma di qualcuno. |
| **Prompt di ricerca immagini AI** | Lo stesso lungo testo predefinito di **Generale** | L'istruzione inviata quando qualcuno cerca. `{product_name}` e `{product_description}` vengono sostituiti con il prodotto corrente. Mantenga la richiesta di un semplice elenco di indirizzi di pagina. |

Faccia clic su **Salva**. Vedrà «Impostazioni salvate.». La ricerca delle pagine e l'importazione delle foto sono descritte nella sezione 3.13.

### 3.13 Modifica del prodotto (scheda Moduli)

Apra **Catalogo**, **Prodotti**, modifichi un prodotto e apra la scheda **Moduli**. Il pannello **My ChatGPT** ha le schede **Genera**, **Simula**, **Foto** e **Cronologia**. Se **Modulo pagina di modifica prodotto** è disattivato, resta solo **Cronologia**. Se anche **Cronologia modifiche prodotto** è disattivata, non compare nulla. Salvi una volta un nuovo prodotto prima di generare, in modo che abbia un numero.

![Modifica del prodotto (Product edit)](https://mypresta.eu/docs/images/docs/mychatgpt-product-edit.webp)

**Genera** scrive un campo e lo salva subito sul prodotto.

1. Scelga un chip **Lingua**, oppure **Ogni lingua**.
2. Sotto **Se il campo ha già del testo** scelga **Sostituisci**, **Aggiungi sopra**, **Aggiungi sotto** o **Salta se compilato**.
3. Faccia clic su **Compila** su una scheda campo: **Descrizione** (testo lungo con una breve introduzione e un elenco di caratteristiche), **Descrizione breve** (riepilogo semplice sotto i 400 caratteri circa), **Nome**, **Meta titolo** (circa 70 caratteri), **Meta descrizione** (circa 160 caratteri) o **Tag** (parole separate da virgole).
4. **Pacchetto SEO** con **Compila tutto** scrive il nome, entrambe le descrizioni ed entrambi i campi meta in un colpo solo. Sostituisce quei campi qualunque sia la scelta fatta sotto **Se il campo ha già del testo**.
5. Facoltativo: apra **Usa la tua istruzione o un prompt salvato**. Digiti in **Filtra per titolo o testo**, scelga **Brief standard** (un brief già pronto per il campo che preme) o un modello abilitato, oppure digiti una propria **Istruzione**.

Sotto i pulsanti vedrà l'istruzione inviata e la risposta, e «Content successfully generated and updated to product.». Il form del prodotto sullo schermo non viene aggiornato. Ricarichi la pagina del prodotto prima di modificare di nuovo. Se preme **Salva** sul vecchio form, PrestaShop riscrive il vecchio testo. Il modulo accorcia le risposte lunghe alla dimensione del campo: nome 128 caratteri, descrizione breve 800, meta titolo 69, meta descrizione 159.

**Simula** ha le stesse scelte e i pulsanti **Prova**. Mostra la risposta nella pagina e non modifica il prodotto. Il tentativo viene scritto nella Cronologia.

**Foto** (richiede **Ricerca immagini AI** attiva):

1. Faccia clic su **Trova pagine**. Il modello suggerisce pagine che probabilmente mostrano questo prodotto.
2. Faccia clic sull'indirizzo di una pagina. Il negozio legge la pagina (gli indirizzi di reti private o locali vengono rifiutati) ed elenca fino a 24 immagini. Le piccole icone e i pixel di tracciamento vengono saltati.
3. Selezioni le foto desiderate. La prima foto selezionata diventa l'immagine di copertina del prodotto e sostituisce la copertina attuale. Le altre vengono aggiunte dopo le foto esistenti.
4. Faccia clic su **Aggiungi selezionati a questo prodotto**. Prima di questo clic non viene salvato nulla. Ricarichi il prodotto per vedere le foto.

Le ricerche di foto non vengono scritte nella Cronologia e non contano per il budget. Rispetti il diritto d'autore delle foto che importa.

**Cronologia** elenca le scritture precedenti per questo prodotto con **Quando**, **Tipo** e **Stato**. **Ripristina** rimette il testo precedente dopo che ha confermato «Restore the previous value?». Vedrà «Content successfully restored. Refresh this page to see changes.». La Cronologia di tutto il negozio non viene eliminata.

Accanto ai campi descrizione, descrizione breve, meta titolo e meta descrizione (in qualsiasi form di prodotto) vede anche un piccolo pulsante rotondo con il logo OpenAI **Genera con AI**. Vi faccia clic. Se il negozio ha più di una lingua, scelga **Lingua attuale**, **Tutte le lingue** o **Annulla**. Il campo riceve un brief già pronto per quel campo, e il testo va solo nel campo del form, con «Il testo è nel campo. Salva il prodotto per mantenerlo.». Faccia clic su **Salva** sul prodotto per conservarlo. Questo pulsante non usa i modelli né il campo **Istruzione**.

### 3.14 Aggiornamenti

Apra **Aggiornamenti** (lato destro del menu superiore). Il form **Aggiornamenti MyPresta** controlla su MyPresta.eu se esiste un file del modulo più recente. Non modifica il suo catalogo e non installa nulla.

![Aggiornamenti (Updates)](https://mypresta.eu/docs/images/docs/mychatgpt-updates.webp)

| Campo | Predefinito | Cosa fa |
|---|---|---|
| **Controllo manuale** | – | Faccia clic su **Controlla ora**. Il negozio interroga una volta il server di aggiornamento di MyPresta.eu e mostra accanto al pulsante «Il modulo è aggiornato!» oppure «Nuova versione disponibile!». |
| **Notifiche automatiche** | Abilitato | **Abilitato** permette al back office di controllare circa ogni tre giorni e di mostrare un avviso con un link quando esiste una versione più recente. **Disabilitato** lo interrompe. |
| **Pagina prodotto** | – | Un link alla pagina del modulo su MyPresta.eu. |

Faccia clic su **Salva** per memorizzare la scelta delle notifiche. Vedrà «Impostazioni di aggiornamento salvate.». Il numero di versione accanto al nome del modulo nel menu è la versione installata sul suo negozio, non la più recente.

## 4. Vetrina del negozio

Il modulo non mostra nulla ai suoi clienti. Non aggiunge alcun blocco, pagina, script o stile alla vetrina del negozio. Il tema non ha nulla da sovrascrivere. Tutto ciò che vede si trova nel back office: il pulsante **My ChatGPT** nella barra superiore, le schermate del modulo e il pannello nella pagina del prodotto.

Il modulo ha due indirizzi web che esistono solo per i server e per il back office:

- L'**indirizzo cron**. Lo copi da **Cron** (sezione 3.10) e lo inserisca solo nell'utilità di pianificazione del suo server. Chiunque conosca l'indirizzo completo con il segreto può avviare un lotto, quindi non lo pubblichi mai e non lo incolli in chat o ticket.
- Un indirizzo tecnico usato dai pulsanti del back office a ogni generazione. Non lo apra e non lo condivida.

Aprire l'indirizzo cron in un browser mostra testo semplice. Questi sono i messaggi che può leggere:

| Cosa vede | Cosa fare |
|---|---|
| Cron Job feature is disabled. You can enable it from the module settings. | Apra **Cron**, imposti **Abilita funzione cron** su **Sì** e faccia clic su **Salva**. |
| The token does not exist or it’s wrong! | Il segreto manca o non corrisponde. Copi di nuovo l'indirizzo da **Cron** dopo il salvataggio. |
| Invalid action! | All'indirizzo manca la parte del job. Aggiunga le impostazioni elencate nella sezione 6.3. |
| updatedField parameter is wrong! | Il nome del campo nell'indirizzo non è tra i campi consentiti. Usi un campo elencato in **Campo da aggiornare**. |
| All must include all mandatory parameters! | All'indirizzo mancano campo, regola di selezione, dimensione del lotto, lingua o modello. Li aggiunga (sezione 6.3). |
| productTarget parameter is wrong! Allowed values: … (oppure categoryTarget) | Usi pendingOpenAI, pendingField o emptyField. |
| No valid product IDs provided. | L'**Elenco ID prodotto** non contiene numeri utilizzabili. Corregga o svuoti l'elenco. |
| No products to update. / No categories to update. | Non c'è più nulla che corrisponda alla regola. Il job è terminato, oppure cambi **Prodotti selezionati** o i filtri. |
| N products have been updated. / N categories have been updated. | È stato scritto un lotto. La chiamata successiva prosegue con gli elementi seguenti. |
| N pending products. | Il debug è attivo. Non è stato scritto nulla. Disattivi il debug per le esecuzioni reali. |
| Error!Monthly generation budget reached. | Aumenti il **Budget di generazione mensile** o attenda il mese successivo. |
| Error!Reply rejected by the studio quality gate. | La risposta conteneva una parola proibita. Modifichi **Parole proibite** o disattivi il **Controllo qualità**. |
| Error! The model returned an empty response. | Aumenti **Max Token**, provi un altro modello o un altro modello di prompt. |
| Error! seguito da un messaggio di OpenAI | Legga il messaggio. Le cause tipiche sono una chiave errata, mancanza di credito o un modello sconosciuto. |
| Error! Could not save product … (N product(s) updated before this one.) | PrestaShop ha rifiutato il testo per quell'elemento. Controlli il prodotto, poi esegua di nuovo. |

## 5. Risoluzione dei problemi

### 5.1 Connessione e impostazioni

| Sintomo | Causa | Cosa fare |
|---|---|---|
| «The OpenAI API key is not set. Add it in the module settings.» oppure «The ChatGPT API key is not set. Add it in the module settings.» | Non è memorizzata nessuna chiave. | Apra **Impostazioni**, **ChatGPT**, incolli la chiave in **CHIAVE API OpenAI** e faccia clic su **Salva**. |
| «Il campo CHIAVE API OpenAI non è valido!» | Ha salvato una nuova chiave più corta di 10 caratteri mentre non c'era nessuna chiave memorizzata. | Incolli la chiave completa. |
| «Il campo Modello OpenAI non è valido!» | **Modello** ha meno di 3 caratteri. | Scelga un modello dall'elenco e salvi di nuovo. |
| Messaggio di OpenAI su una chiave errata, una quota o un modello che non esiste | OpenAI ha rifiutato la chiamata. Il modulo mostra il testo originale di OpenAI. | Controlli la chiave, la fatturazione di OpenAI e il nome del modello in **Impostazioni**, **ChatGPT**. Un modello che ha aggiunto deve essere disponibile per il suo account. |
| «Error! Invalid token!» | La pagina è stata aperta prima che il modulo rinnovasse il suo segreto interno, oppure è rimasta aperta per moltissimo tempo. | Ricarichi la pagina e riprovi. |
| «OpenAI request timed out after N seconds. The model may be overloaded, or the timeout is too low for this prompt.» | OpenAI ha risposto troppo lentamente. | Aumenti **Timeout API (secondi)** in **Impostazioni**, **Generale** (fino a 600), usi un modello più veloce o chieda un testo più breve. |
| «The model hit the token limit before returning any text. Increase "Max Tokens" in the module settings – reasoning models spend part of that budget on thinking.» | **Max Token** è troppo basso per questo modello. | Aumenti **Max Token** in **Impostazioni**, **ChatGPT**. |
| «The response was blocked by the provider content filter. Try rewording the prompt.» | Il filtro di OpenAI ha fermato la risposta. | Riformuli il prompt o i dati del prodotto che usa. |
| «The model returned an empty response.» | Il modello non ha restituito testo. | Riprovi, con un altro modello o con un prompt meno restrittivo. |
| «Monthly generation budget reached. Raise it in the studio settings or wait until next month.» | Il numero di generazioni riuscite ha raggiunto il **Budget di generazione mensile**. | Aumenti il numero in **Impostazioni**, **Studio**, lo imposti a 0 oppure attenda il mese successivo. Anche svuotare la **Cronologia** azzera il contatore. |
| «The reply was rejected because it contains a forbidden word from the studio settings.» | Una riga di **Parole proibite** compare nella risposta, anche all'interno di una parola più lunga. | Accorci o modifichi l'elenco, oppure imposti **Controllo qualità** su **No**. Nel prodotto non è stato scritto nulla. |

### 5.2 Pagina del prodotto e risultati della generazione

| Sintomo | Causa | Cosa fare |
|---|---|---|
| Il pannello **My ChatGPT** manca nella pagina del prodotto. | **Modulo pagina di modifica prodotto** e **Cronologia modifiche prodotto** sono entrambi disattivati, oppure non si trova nella scheda **Moduli**. | Attivi gli interruttori in **Impostazioni**, **Generale**, poi apra la scheda **Moduli**. |
| «Salva il prodotto una volta prima di generare.» | Il prodotto non ha ancora un numero. | Salvi il prodotto, poi generi. |
| Il nuovo testo è sparito dopo aver salvato il prodotto. | Il form del prodotto sullo schermo conteneva ancora il vecchio testo. | Dopo **Compila**, ricarichi la pagina del prodotto prima di modificare e salvare. |
| «Product skipped.» oppure «Category skipped.» | **Salta se compilato** ha trovato del testo nel campo. Non è un errore. | Scelga **Sostituisci**, **Aggiungi sopra** o **Aggiungi sotto** se vuole scrivere comunque. |
| «Error! Content retrieve has failed! Details: …» | OpenAI o il server ha restituito un errore. | Legga i dettagli dopo «Details:». Apra la **Cronologia**, filtri **Stato** su **Errore** e apra la riga. |
| «Error! The generated content could not be saved to the product.» oppure «… to the category.» | PrestaShop ha rifiutato il testo, ad esempio per un carattere non consentito. | Legga il motivo dopo la frase. Provi un altro prompt o un campo più breve. |
| «Error! Prompt is missing or too short!» | L'istruzione ha meno di 4 caratteri. | Scriva un'istruzione più lunga oppure lasci vuoto il campo per usare il brief standard. |
| «Error! Product not found!» / «Error! Category not found!» | L'elemento è stato eliminato o il numero è sbagliato. | Ricostruisca l'elenco ed esegua di nuovo. |
| «Error! This log entry has no previous value to restore.» oppure «Error! Nothing to restore for this entry.» | Quella riga della Cronologia non ha un vecchio testo. | Usi un'altra riga. Le righe scritte da **Simula** o gli errori non possono ripristinare nulla di utile. |
| «The model did not return a usable SEO pack.» | La risposta non aveva il formato previsto. | Faccia di nuovo clic su **Compila tutto** oppure compili i campi uno alla volta. |
| «Generazione fallita.» su un pulsante **Genera con AI** | La chiamata non è riuscita. | Riprovi. Veda la **Cronologia** per il motivo. |
| «Error! This PrestaShop version does not support the category Additional Description field.» | Il suo negozio non ha quel campo di categoria. | Scelga un altro campo di categoria. |

### 5.3 Generazione di massa

| Sintomo | Causa | Cosa fare |
|---|---|---|
| La tabella dopo **Vai al passo successivo** è vuota. | I filtri non corrispondono a nulla. | Allenti i filtri. Controlli **Stato del prodotto**, **Stock del prodotto** e **Aggiorna solo**. |
| «Select at least one language.» | Nessuna lingua è selezionata. | Selezioni almeno una lingua. |
| L'esecuzione si è fermata a metà. | La scheda è stata chiusa, la connessione è caduta o il server si è fermato. | Ricostruisca l'elenco con **Aggiorna solo** impostato sui prodotti non ancora aggiornati ed esegua di nuovo. |
| Molte righe mostrano errori. | Un problema di budget, chiave o timeout. | Apra la **Cronologia**, legga il primo errore, lo risolva ed esegua di nuovo. |
| Home e la categoria radice sono nell'elenco delle categorie. | **Categorie** è stato lasciato vuoto. | Selezioni le categorie desiderate prima di **Vai al passo successivo**. |

### 5.4 Cron

| Sintomo | Causa | Cosa fare |
|---|---|---|
| Nel catalogo non cambia nulla. | **Abilita funzione cron** è disattivata, l'utilità di pianificazione non richiama l'indirizzo, o nessun elemento corrisponde alla regola. | Controlli l'interruttore, il registro dell'utilità di pianificazione e **Prodotti selezionati**. Apra una volta l'indirizzo con il debug attivo per vedere il piano. |
| L'indirizzo risponde con un messaggio della tabella nella sezione 4. | Veda quella tabella. | Faccia ciò che dice la tabella. |
| Gli stessi prodotti vengono scritti ripetutamente. | **Prodotti selezionati** è **emptyField** e il campo resta vuoto, oppure si usa **pendingOpenAI** e la Cronologia è stata svuotata. | Usi **pendingField**, oppure corregga il prompt in modo che venga scritto del testo. |
| Un vecchio indirizzo ha smesso di funzionare. | Il modulo sostituisce i segreti più corti di 24 caratteri, oppure il segreto è stato cambiato o il modulo è stato reinstallato. | Copi di nuovo l'indirizzo da **Cron** e aggiorni l'utilità di pianificazione. |
| **Genera token** non fa nulla. | Il pulsante in questa versione non ha alcuna funzione. | Conservi il segreto creato all'installazione. |

### 5.5 Immagini, nuovo prodotto e menu

| Sintomo | Causa | Cosa fare |
|---|---|---|
| Manca la scheda **Foto**. | **Ricerca immagini AI** è disattivata. | La attivi in **Impostazioni**, **Generale** o **Immagini**, poi ricarichi il prodotto. |
| «No pages were suggested.» oppure «The search failed.» | Il modello non ha restituito indirizzi utilizzabili, oppure la chiave ha un problema. | Faccia di nuovo clic su **Trova pagine** o controlli il **Prompt di ricerca immagini AI**. |
| «That page could not be read.», «URL not allowed (private network)» o un errore che inizia con HTTP | La pagina blocca il negozio, richiede un accesso o si trova in una rete privata. | Scelga un'altra pagina. |
| «No photos were found on that page.» | La pagina non ha immagini utilizzabili. | Scelga un'altra pagina. |
| «No images could be imported. Details: …» | Le immagini non hanno potuto essere scaricate o non sono vere immagini. | Legga i dettagli. Scelga altre foto. |
| «Failed to parse AI response. Please try again.» in **Nuovo prodotto** | La risposta non aveva il formato previsto. | Faccia di nuovo clic su **Genera dati**. |
| «Error creating product: …» oppure «Failed to create product» | PrestaShop ha rifiutato il prodotto, spesso perché la **Lingua** scelta non è la lingua predefinita del negozio. | Scelga la lingua predefinita e controlli il numero di categoria. |
| «Generate the product first.» | Ha fatto clic su **Crea prodotto** prima di **Genera dati**. | Faccia prima clic su **Genera dati**. |
| Manca la voce di menu **Generatore di Contenuti AI**. | Il modulo è disabilitato, oppure la voce è stata spostata. | Abiliti il modulo in **Gestione moduli** e apra una volta una pagina qualsiasi del back office. Il modulo rimette la voce sotto **Moduli**. Se manca ancora, verifichi che il suo profilo dipendente possa aprire **Moduli**. |
| Dashboard e Cronologia sono vuote. | Nel periodo scelto non è stato generato nulla, oppure è stato usato **Svuota elenco**. | Scelga **Tutto il tempo**. |

## 6. Per gli sviluppatori

### 6.1 Panoramica

| Voce | Valore |
|---|---|
| Nome tecnico | mychatgpt |
| Versione | 1.1.0 |
| Nome nell'elenco dei moduli | My ChatGPT - AI content generation |
| Autore | MyPresta.eu |
| Scheda del modulo | front_office_features |
| PrestaShop | 1.6 – 9.99.99 |
| PHP minimo | 7.0.0 (verificato in `install()`) |
| Classe principale | `mychatgpt extends Module`, con le classi di supporto `mychatgptUpdate` e `searchToolmychatgpt` che la estendono |

Flusso dei dati: il JavaScript del back office richiama il controller front `ajax` con `secret_token` (letto da `MYPRESTA_MYCHATGPT_TOKEN`) oppure un controller di amministrazione. Il controller legge le chiavi del modello e del campionamento, applica lo Studio (`MyChatGPT\Studio`), richiama OpenAI tramite `MyChatGPT\OpenAIService` (cURL verso l'endpoint chat completions dell'API OpenAI), scrive il testo con il modello a oggetti di PrestaShop e inserisce una riga in `mychatgpt_log`. `cron` fa lo stesso senza browser. `getServiceName()` restituisce sempre `openai`. Il codice residuo per altri provider è stato rimosso. Le chiavi delle impostazioni di un precedente secondo provider (`_GEMINI_API_KEY`, `_GEMINI_MODEL`, `_ACTIVE_SERVICE`) vengono eliminate ogni volta che si apre la schermata delle impostazioni.

### 6.2 File

| Percorso | Scopo |
|---|---|
| `mychatgpt.php` | Classe principale: installazione e disinstallazione, schede, form delle impostazioni, modelli di prompt, dashboard, hook, scheda del prodotto, catalogo dei modelli. |
| `autoload.php` | Piccolo caricatore di classi per il namespace `MyChatGPT\` (senza Composer). |
| `src/OpenAIService.php` | Client cURL per chat completions e per l'elenco dei modelli. Timeout 10–600 s, scarta i parametri che un modello rifiuta (fino a 6 tentativi), disattiva il controllo dei certificati solo su localhost. |
| `src/Studio.php` | Controllo del budget, decorazione del prompt (lingua, voce, pubblico, tono, glossario, parole proibite), ispezione della risposta, pacchetto SEO e prompt per i testi alternativi. |
| `controllers/admin/*.php` | Sette controller di amministrazione (sezione 6.3). |
| `controllers/front/ajax.php` | Endpoint JSON per tutta la generazione avviata dal browser. |
| `controllers/front/cron.php` | Endpoint cron in testo semplice. |
| `lib/updateChecker.php` | Controllo degli aggiornamenti su dev.mypresta.eu ogni 3 giorni e form Aggiornamenti. |
| `lib/sectionHelp.php` | Testi del pannello Aiuto. |
| `lib/searchTool/` | Classe di supporto `searchToolmychatgpt` (strumento di autocompletamento nelle schermate del modulo). |
| `lib/prestashop9compatibility.php` | Wrapper per visualizzazione prezzi, hashing e reindirizzamenti su PrestaShop 9. |
| `views/templates/hook/*.tpl` | Schermate e pannelli del modulo (dashboard, navigazione, sotto-navigazione, generatori di massa, scheda del prodotto, cronologia, informazioni cron, finestra della barra superiore). |
| `views/templates/admin/product_creator.tpl` | Schermata del nuovo prodotto. |
| `views/js/back.js` | Esecuzioni di massa, pannello del prodotto, playground, finestra della barra superiore, nuovo prodotto, ripristino. |
| `views/js/product-fields.js` | Pulsanti **Genera con AI** accanto ai campi del prodotto. |
| `views/js/image-finder.js` | Scheda **Foto**. |
| `views/js/admin-products-bulk.js` | Aggiunge il pulsante **My ChatGPT** all'elenco dei prodotti. |
| `views/js/dashboard.js`, `chart.min.js`, `admin-help.js` | Grafici e pannello Aiuto. |
| `views/css/admin-nav.css`, `back.css`, `stats.css` | Stili. |
| `translations/*.php` | 34 file di lingua. |
| `upgrade/index.php` | Solo un file di reindirizzamento. Non ci sono script di aggiornamento. |

Le classi `AdminMyChatGPTMain` e `AdminMyChatGPTSettings` richiamano `addJS`/`addCSS` per `views/js/admin.js` e `views/css/admin.css`, e il controller del nuovo prodotto per `product_creator.js` e `product_creator.css`. Nessuno di questi file è incluso. Il form cron si aspetta le funzioni JavaScript `generateTokenAndFill()` e `generateCategoryTokenAndFill()` e riempie gli span `.cron-parameters`. Neanche questo script è incluso.

### 6.3 Controller

| Controller | Padre e route | Scopo |
|---|---|---|
| `AdminMyChatGPTMain` | Sotto **Moduli**, visibile. Reindirizza alla configurazione del modulo, Dashboard. | La voce di menu **Generatore di Contenuti AI**. |
| `AdminMyChatGPTSettings` | Scheda nascosta (`active = 0`). Reindirizza alla configurazione, Impostazioni. | Voce di compatibilità. |
| `AdminMyChatGPT` (file `AdminMyChatGPT.php`, classe `AdminMyChatGPTController`) | Scheda nascosta. `mcg_sub=products` o `categories`. | Filtri e generatori di massa. `renderProductUpdateForm()` e il form di aggiornamento delle categorie non hanno un gestore. Gli invii `generateProductContent` e `generateCategoryContent` salvano soltanto i valori del form. La generazione viene eseguita da `back.js`. |
| `AdminMyChatGPTProductCreator` | Scheda nascosta. Azioni Ajax `generateProductData`, `createProduct`, `extractImages`, `generateImages` (stub). | Nuovo prodotto. |
| `AdminMyChatGPTCron` | Scheda nascosta. Form `submitCronUpdate`, `submitCatCronUpdate`. | Impostazioni cron. |
| `AdminMyChatGPTUsage` | Scheda nascosta. Parametri `stats_*`, `view` e `clear_log`. | Cronologia. `clear_log` esegue `DELETE` sull'intera tabella di log. |
| `AdminMyChatGPTImageFinder` | Scheda nascosta. Azioni Ajax `searchImages`, `extractImages`, `saveImages`. | Form **Immagini** e ricerca delle foto. |

Tutti i controller di amministrazione reindirizzano alla schermata iniziale se il modulo è inattivo. La pagina di configurazione del modulo (`getContent`) mostra Dashboard, Impostazioni (`mcg_tab=settings`, `mcg_sub` general, openai, studio, templates, playground) e Aggiornamenti (`mcg_tab=updates`).

Controller front `ajax` (`secret_token` deve essere uguale a `_TOKEN`; non c'è alcun controllo del dipendente). Azioni: `initiatePrompt`, `updateSettings` (scrive max tokens, temperature, top p ed entrambe le penalità), `updateProduct`, `updateCategory`, `initiateProductRestore`, `generateAltTexts` (nessun pulsante la usa; al massimo 8 immagini), `generateSeoPack`. `updateProduct` e `updateCategory` accettano `target` (campo), `behavior` (`replace`, `keep`, `keep_top`, `keep_end` o `single_product` per un'anteprima non salvata), `prompt`, la lingua e il numero dell'elemento. Le risposte sono JSON con `status` (`success`, `error`, `skipped`), `msg` e `date`.

Controller front `cron`: rifiuta con il messaggio «disabled» quando `_ENABLE_CRON` è 0. Il parametro `secret` deve essere uguale a `_SECRET` o `_CAT_SECRET` (ciascun segreto apre entrambi i job). Parametri:

| Parametro | Usato da | Significato |
|---|---|---|
| `secret` | entrambi | Segreto di prodotti o categorie. |
| `action` | entrambi | `generateProductContent` o `generateCategoryContent`. |
| `updatedField` | entrambi | Prodotti: name, description, description_short, meta_title, meta_description, tags. Categorie: name, description, meta_title, meta_description, additional_description. |
| `productTarget` / `categoryTarget` | ciascuno | `pendingOpenAI`, `pendingField`, `emptyField`. |
| `productsToUpdate` / `categoriesToUpdate` | ciascuno | Dimensione del lotto (`LIMIT`). |
| `languageId` | entrambi | Numero della lingua. |
| `promptTemplateId` | entrambi | Numero del modello da `mychatgpt_prompt`. |
| `debug` | entrambi | Qualsiasi valore diverso da 0 stampa il piano e non scrive nulla. |
| `categories` | prodotti | Numeri di categoria separati da virgole. |
| `productIds` | prodotti | Numeri di prodotto separati da virgole. |

Esempio (usi `YOUR_SECURE_KEY` solo come segnaposto):

```text
https://your-shop.example/module/mychatgpt/cron?secret=YOUR_SECURE_KEY&action=generateProductContent&updatedField=description&productTarget=pendingField&productsToUpdate=5&languageId=1&promptTemplateId=3&debug=1
```

`pendingOpenAI` e `pendingField` guardano le righe riuscite di `mychatgpt_log` (le righe con stato error vengono ignorate, quindi gli elementi falliti vengono ritentati). Il job delle categorie esclude le categorie con un numero fino alla categoria home inclusa.

### 6.4 Hook

Registrati in `install()`:

| Hook | Comportamento |
|---|---|
| `displayAdminProductsExtra` | Mostra il pannello della scheda **Moduli** (`product-tab-wrapper.tpl`) quando `_PRODUCT` o `_PRODUCT_LOG` è 1. |
| `displayBackOfficeHeader` | Carica le risorse; esegue `ensureLongSecrets()` (sostituisce `_TOKEN`, `_SECRET`, `_CAT_SECRET` più corti di 24 caratteri) e `placeModuleMenu()`; registra una volta la scheda **Ricerca immagini AI** (`_IMAGEFINDER_TAB_OK`); mette in coda `product-fields.js`, `admin-products-bulk.js` e `image-finder.js` su `AdminProducts`; registra di nuovo `dashboardZoneTwo` se manca. `product-fields.js` viene messo in coda su ogni pagina prodotto, qualunque sia il valore di `_PRODUCT`. |
| `displayBackOfficeTop` | Definisce valori JavaScript (`admin_controller_url`, `idcms`, `idcategory`, `idmanufacturer`) e mostra la finestra della barra superiore quando `_TOPCTA` è 1. |
| `dashboardZoneTwo` | Mostra `dashboard.tpl`, che legge variabili `mcg_*` che questo hook non assegna. |
| `displayAdminProductsMainStepLeftColumnMiddle` | Stub vuoto, restituisce una stringa vuota. |
| `displayAdminProductsMainStepLeftColumnBottom` | Stub vuoto, restituisce una stringa vuota. |
| `actionProductFormBuilderModifier` | Nessuna operazione, non restituisce nulla. |
| `displayHeader` | Stub vuoto. |
| `displayFooter` | Stub vuoto. |

Il metodo `hookActionProductGridDataModifier` esiste ma non è registrato. Il modulo non ha override di `enable()` o `disable()` e non espone hook propri.

### 6.5 Override

Il modulo non ha override.

### 6.6 Database

| Tabella | Contenuto |
|---|---|
| `mychatgpt_prompt` | `id_prompt`, `status` (0/1), `title` (128), `prompt` (text), `date_generated`. Popolata con 16 righe. |
| `mychatgpt_log` | `id_log`, `id_product`, `id_category`, `id_cms`, `id_manufacturer`, `id_lang`, `id_employee`, `type`, `method`, `status`, `ai_service`, `model`, `http_code`, `duration_ms`, `prompt_tokens`, `completion_tokens`, `total_tokens`, `error_message`, `prompt`, `reply`, coppie `old_*` e `new_*` per name, description, description_short, meta_title, meta_description e tags, `date_updated`. Chiavi su `id_product` e `status`. |

La disinstallazione elimina entrambe le tabelle. `ensureUsageColumns()` aggiunge le tre colonne dei token all'apertura di una schermata, se una tabella più vecchia ne è priva. Le righe di prodotti, categorie e immagini scritte dal modulo sono dati standard di PrestaShop e non vengono toccate alla disinstallazione.

### 6.7 Chiavi e traduzioni

Le chiavi usano il prefisso `MYPRESTA_MYCHATGPT_`. Valori impostati all'installazione:

| Chiave | Predefinito |
|---|---|
| `_LIVE_MODE`, `_DEBUG_MODE` | 0 |
| `_TOPCTA`, `_PRODUCT`, `_PRODUCT_LOG` | 1 |
| `_TOKEN`, `_SECRET`, `_CAT_SECRET` | 32 caratteri casuali |
| `_API_KEY` | Uno spazio |
| `_MODEL` | gpt-3.5-turbo |
| `_EXTRA_MODELS`, `_MODEL_CAPS` | Vuoto (il secondo viene riempito durante l'esecuzione con i parametri rifiutati per modello) |
| `_TEMPERATURE`, `_TOP_P` | 0.7, 1 |
| `_MAX_TOKENS`, `_TIMEOUT` | 3200, 120 |
| `_FREQ_PEN`, `_PRES_PEN` | 0 |
| `_VOICE`, `_AUDIENCE`, `_TONE`, `_GLOSSARY`, `_FORBIDDEN` | Vuoto |
| `_BUDGET`, `_QUALITY` | 0, 1 |
| `_IMAGEFINDER_ENABLE`, `_IMAGEFINDER_PROMPT` | 1, lungo prompt predefinito |
| `_ENABLE_CRON`, `_CRON_INTERVAL`, `_CAT_CRON_INTERVAL` | 0, 6, 6 |
| `updatedField`, `productTarget`, `productsToUpdate`, `promptTemplateId`, `languageId`, `interval_select`, `debug`, `productIdsList` | description, pendingOpenAI, 5, vuoto, lingua predefinita, vuoto, 0, vuoto |
| `catupdatedField`, `categoryTarget`, `categoriesToUpdate`, `catpromptTemplateId`, `catlanguageId`, `catdebug` | description, pendingOpenAI, 5, vuoto, lingua predefinita, 0 |
| `PS_USE_HTMLPURIFIER` | Impostato a 0 (per tutto il negozio) |

Le chiavi cron senza prefisso (`updatedField`, `debug` e le altre sopra) sono nomi globali e possono entrare in conflitto con altri moduli.

Create in seguito: `_IMAGEFINDER_TAB_OK`, `categories` (scelta delle categorie cron), `mypresta_updates`, `update_mychatgpt`, `updatev_mychatgpt`. `AdminMyChatGPT::postProcess()` scrive inoltre ogni campo di filtro (`_FIELD`, `_LANGUAGE`, `_CONTENT`, `_DELAY`, `_EXISTING`, `_HISTORY`, `_STATUS`, `_STOCK`, `_PROD_IDS`, `_PROD_REF`, `_PROD_DATE_FROM`, `_PROD_DATE_TO`, `_PROD_MIN_ID`, `_PROD_MAX_ID`, `_PROD_LIMIT`, `_CATEGORIES`, `_BRANDS`) nella configurazione a ogni richiesta di quel controller, ma nulla li rilegge.

La disinstallazione elimina le chiavi elencate in `uninstall()`. Non ripristina `PS_USE_HTMLPURIFIER`. Lascia `categories`, le chiavi dei filtri sopra e le chiavi degli aggiornamenti.

I generatori, il cron e la normale validazione usano `Tools::getValue` con whitelist. La chiave API è memorizzata in chiaro nella tabella di configurazione. `randomString()` usa `rand()`.

Traduzioni: aggiunga `translations/{iso}.php` nel formato standard dei moduli PrestaShop (sono inclusi 34 lingue). I testi passano attraverso `$this->l()` nella classe principale, nel controllo degli aggiornamenti e nel pannello Aiuto. Su PrestaShop 8 e 9 i controller di amministrazione usano `trans()` con i domini `Admin.MyChatGPT`, `Admin.MyChatGPTCron` e `Admin.MyChatGPTUsage`. Non tradotti: i messaggi dentro `back.js` e `image-finder.js`, le istruzioni predefinite usate da **Compila** e **Genera con AI**, l'output di `cron` e i testi di errore di `AdminMyChatGPTProductCreator` e `AdminMyChatGPTImageFinder`. I lunghi testi di aiuto («What it does / How to configure / Effect») sono costruiti da `fieldHelp()` e si trovano nelle definizioni dei form di `mychatgpt.php` e dei controller di amministrazione (metodo `help()`), nei template e in `lib/sectionHelp.php`. I nomi dei modelli predefiniti e i nomi dei menu vengono scritti nel database nelle lingue del negozio durante l'installazione.

### 6.8 Estensione

- Aggiunga o modifichi i modelli di prompt nella schermata del modulo o in `mychatgpt_prompt`.
- Aggiunga segnaposto nei costruttori di prompt di `ajax.php` (`updateProduct`, `updateCategory`) e di `cron.php`.
- Aggiunga modelli in **Impostazioni**, **ChatGPT** senza modificare il codice. Il modulo impara da solo i parametri non supportati.
- Modifichi le istruzioni standard per **Compila**, **Genera con AI** e le esecuzioni di massa in `back.js` e `product-fields.js`.
- Il front office non ha template, quindi il tema non ha nulla da sovrascrivere. I template del back office in `views/templates` si modificano nella cartella del modulo.

## 7. Aiuto

Pagina del prodotto: https://mypresta.eu/modules/administration-tools/my-chatgpt.html

Per scrivere a proposito del modulo:

1. Acceda al suo account cliente su mypresta.eu.
2. Apra la pagina dei contatti.
3. Scelga **Support for paid modules**.
4. Descriva il problema. Indichi il messaggio esatto mostrato sullo schermo e i passaggi che lo causano. Non incolli mai la sua chiave API OpenAI né un indirizzo cron completo con il segreto.
