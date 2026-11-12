---
title: MyFAQ - documentazione e manuale utente
sidebar:
  label: MyFAQ - documentazione e manuale utente
description: Manuale di configurazione e risoluzione dei problemi per i negozi che hanno già MyFAQ.
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo MyFAQ: product FAQ with FAQPage schema su MyPresta.eu](https://mypresta.eu/modules/front-office-features/myfaq-product-faq-with-faqpage-schema.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/myfaq-product-faq-with-faqpage-schema/)
>
> ---


## 1. Requisiti

MyFAQ gira dentro PrestaShop. Non serve un altro modulo.

- PrestaShop 1.7.0.0 fino a PrestaShop 9. Lo stesso pacchetto e le stesse schermate servono PrestaShop 8 e PrestaShop 9.
- PHP 7.0 o più recente, e almeno la versione di PHP richiesta da quella versione di PrestaShop. L'installazione e l'indirizzo pianificato usano `random_bytes`.
- cURL serve per generare le domande. Senza cURL la generazione si ferma e la riga di avanzamento mostra `curl_missing`. Il controllo degli aggiornamenti usa cURL quando PHP lo fornisce, e legge l'indirizzo in modo diretto quando cURL manca e il server consente le letture remote.
- OpenSSL cifra la chiave IA che Lei salva. Senza OpenSSL la chiave resta salvata così come viene incollata.
- Nessun altro modulo è obbligatorio. La pagina prodotto del tema deve stampare il footer del prodotto o le schede prodotto aggiuntive perché il cliente veda la fisarmonica.
- Un account presso OpenAI, Anthropic, Google, DeepSeek o Mistral serve solo per quel fornitore. La tessera compatibile può puntare al Suo server, per esempio Ollama, vLLM o LM Studio, e quel server può funzionare senza un account esterno.
- Un sistema esterno serve solo quando si chiama l'indirizzo FAQ da fuori del negozio. Un pianificatore serve solo quando il server deve finire una coda mentre il back office è chiuso.

Un catalogo grande si scrive una lingua alla volta. Lasci aperta la pagina di generazione in blocco finché la barra non arriva al 100 %, oppure pianifichi l'indirizzo da **Generazione in blocco**. Ogni chiamata lavora circa 20 secondi e poi si ferma, così non urta il limite di tempo di PHP. Una chiamata scrive al massimo 30 lingue.

## 2. Installazione

1. Nel back office apra **Moduli**, poi **Gestore dei moduli**.
2. Carichi lo zip del modulo e clicchi **Installa**.
3. Apra **Configura** su **MyFAQ**. La pagina si apre su **Visualizzazione**. La barra contiene anche **Voci**, **IA**, **Generazione in blocco**, **API** e **Aggiornamenti**.
4. MyFAQ non aggiunge una voce nel menu di sinistra. Il catalogo, l'elenco delle chiavi e la cronologia richieste sono pagine nascoste. La prima apertura di **Configura** le crea e dà al profilo del dipendente attuale il diritto di aprirle.
5. L'installazione non svuota la cache in un passo separato. Se dopo un aggiornamento la pagina prodotto mostra ancora il layout precedente, svuoti la cache in **Parametri avanzati**, **Prestazioni**.

Su un prodotto, apra il prodotto e il blocco **MyFAQ**. Lì si fissa la collocazione di quel prodotto e si scrivono domande che appartengono solo a lui.

Per spegnere il modulo usi l'interruttore del **Gestore dei moduli**. La pagina prodotto non stampa più la fisarmonica e la scheda prodotto non mostra più il blocco MyFAQ. Domande, chiavi e impostazioni restano. Lo riaccenda e vengono riusate. Il modulo non ha un pulsante proprio di attivazione o disattivazione.

Per toglierlo, clicchi **Disinstalla** e confermi. La disinstallazione toglie le pagine nascoste, le domande e le risposte, i collegamenti, la collocazione per prodotto, le chiavi API, la cronologia richieste, la coda di generazione e le impostazioni di visualizzazione e di IA. I due indirizzi pianificati smettono di funzionare perché il segreto che contengono viene eliminato. I file del modulo restano sul server finché non elimina il modulo. Una nuova installazione riparte con voci vuote e le impostazioni di un'installazione nuova. Le vecchie domande non tornano. L'interruttore del controllo aggiornamenti non viene cancellato dalla disinstallazione.

## 3. Configurazione e lavoro quotidiano

Scriva una domanda e una risposta, poi colleghi quella voce a un prodotto o a qualcosa che il prodotto ha già: una categoria, un valore di caratteristica, un valore di attributo, un tag, una marca o un fornitore. Basta un solo collegamento corrispondente. La FAQ della pagina prodotto è la fisarmonica che il negozio stampa dopo aver raccolto ogni corrispondenza attiva nella lingua del cliente e sostituito i token. Le voci collegate direttamente al prodotto passano per prime. Poi l'ordine è la posizione che Lei imposta.

Il footer del prodotto sta sotto il prodotto. La scheda prodotto è la stessa fisarmonica dentro una scheda. Su un prodotto può forzare il footer, forzare la scheda o nascondere MyFAQ. Nascondere toglie anche il blocco FAQ letto dai motori di ricerca. Il cliente apre solo le domande. Non c'è un modulo con cui inviarne una nuova. Il percorso finisce quando la pagina prodotto mostra la fisarmonica, oppure quando la collocazione è **Nascondi** o nessuna voce attiva corrisponde: quel prodotto non mostra allora alcun blocco MyFAQ.

Scrivere con un modello è facoltativo. Salvi il fornitore e la chiave in **IA**. Salvare lì non genera nulla. **Genera** su un prodotto, o **Avvia generazione** in **Generazione in blocco**, mette il lavoro in coda. Ogni lingua di un prodotto è una richiesta. **Aggiungi** conserva le voci IA attuali e ne aggiunge altre. **Sostituisci le voci IA non bloccate collegate solo al prodotto** elimina le voci IA non bloccate collegate solo a quel prodotto, poi ne scrive di nuove. Una voce che Lei ha modificato è bloccata e viene conservata. Una voce collegata anche a una categoria o a un altro destinatario viene conservata. L'indirizzo pianificato non legge i filtri di **Generazione in blocco**. Finisce una coda già esistente oppure, con il secondo indirizzo, aggiunge ogni prodotto attivo di questo negozio che non ha ancora una voce IA.

Un sistema esterno è facoltativo. In **API** generi una chiave, copi l'URL di base e incolli entrambi in quel sistema.

Apra **Moduli**, **Gestore dei moduli**, **MyFAQ**, **Configura**. La riga sotto la barra spiega la sezione aperta.

I nomi delle tessere fornitore, i titoli delle schede dati e i testi dei pulsanti shortcode restano in inglese sullo schermo. Anche le frasi della barra di avanzamento restano in inglese.

### 3.1 Visualizzazione

**Visualizzazione** è la presentazione di tutto il negozio. Un prodotto può comunque usare un'altra collocazione.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Collocazione** | Footer del prodotto | Valore del negozio per ogni prodotto che non imposta il proprio. **Footer del prodotto** stampa la fisarmonica sotto il prodotto. **Scheda prodotto** aggiunge una scheda nella pagina del prodotto. Su un prodotto può comunque forzare il footer, la scheda o nascondere MyFAQ. Gli altri moduli sullo stesso hook restano dove **Design**, **Posizioni** li mette. |
| **Titolo della scheda** | FAQ in ogni lingua | Etichetta della scheda prodotto. Viene usata solo quando la collocazione è **Scheda prodotto**. La compili in ogni lingua venduta. Se una lingua è vuota, quella lingua mostra FAQ. |
| **Intestazione sopra l'elenco** | FAQ in ogni lingua | Intestazione stampata sopra le domande, sia nel footer sia nella scheda. La compili per lingua. I clienti vedono questo testo. Lasci FAQ se non serve un'intestazione personalizzata. |
| **Includi categorie padre** | No | **Sì** mostra anche una voce collegata a un padre delle categorie del prodotto, così un solo collegamento copre le sottocategorie. La ricerca si ferma prima di Home, quindi un collegamento a Home non copre tutto il catalogo. **No** corrisponde solo alle categorie in cui il prodotto si trova direttamente. |
| **Apri la prima domanda** | No | **Sì** espande la prima risposta al caricamento della pagina. **No** lascia chiuse tutte le risposte finché il cliente non clicca. I clienti senza JavaScript vedono sempre le risposte. |
| **Markup schema FAQ** | Sì | **Sì** aggiunge un unico blocco schema.org FAQPage costruito dalle domande effettivamente mostrate su quel prodotto, dopo la sostituzione degli shortcode. I motori di ricerca possono usarlo per i risultati ricchi FAQ. **No** stampa la FAQ senza quel blocco. Un elenco vuoto o un prodotto nascosto non lo producono mai. |

Clicchi **Salva**. La pagina mostra **Salvato.**

### 3.2 Voci

**Voci** è un'anteprima delle domande. La riga sotto la barra dice che sono le 10 voci aggiornate più di recente, e che **Nuova voce** e **Modifica** aprono il catalogo.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Nuova voce** | un pulsante | Apre il modulo del catalogo per una domanda nuova. |
| **Mostra elenco completo** | un pulsante | Apre il catalogo con ricerca, dove si cambia l'ordine e si elimina una voce. |
| **Domanda** | vuota finché non ne salva una | La domanda nella lingua attuale del back office. **Nessuna domanda in questa lingua** significa che quella lingua non ha il testo della domanda. |
| **Collegata a** | vuoto | Fino a quattro collegamenti, poi i puntini di sospensione. |
| **Origine** | Scritta a mano per una voce digitata | **IA** o **Scritta a mano**. **bloccata** significa che una sostituzione successiva conserva questa voce. |
| **Stato** | Attiva su una voce nuova | **Attiva** viene mostrata sulle pagine prodotto corrispondenti. **Inattiva** resta nel back office ed è nascosta nel negozio. |

Il numero a destra è il totale delle voci, non solo le dieci di questa anteprima. **Modifica** apre quella voce nel catalogo.

Quando non ci sono voci, la pagina dice **Nessuna voce ancora** e spiega che il negozio non mostra nulla finché una voce attiva non è collegata a un prodotto, categoria, caratteristica, attributo, tag, marca o fornitore.

### 3.3 Catalogo

Apra **Mostra elenco completo**. Il titolo della pagina è **Voci FAQ**. La nota in alto dice che la ricerca confronta domanda, nome o ID del prodotto, lingua e gli altri collegamenti. La domanda è quella nella lingua corrente del back office. Il nome del prodotto apre quel prodotto. **Modifica** apre il modulo in questa pagina. **Su** e **Giù** spostano la voce. Trascini la colonna posizione per impostare lo stesso ordine. **Elimina** chiede conferma. **Attiva** mostra o nasconde la voce. Le voci bloccate vengono conservate quando l'IA sostituisce un prodotto.

Colonne: **ID**, **Domanda**, **Prodotto**, **Collegata anche a**, **Lingue**, **Negozio**, **Origine**, **Attiva**, **Bloccata**, **Posizione**, **Creata**, **Aggiornata**.

**Negozio** mostra **Tutti i negozi** quando la voce è stata salvata con il contesto di tutti i negozi. Altrimenti mostra il nome di quel negozio. La vetrina di un negozio mostra le voci di tutti i negozi e quelle salvate per quel negozio.

**Origine** è **Scritta a mano** o **IA**. Filtri questa colonna con l'elenco. **Attiva** è un interruttore sulla riga: clicchi per mostrare o nascondere la voce. **Bloccata** è un segno, non un interruttore. Modificare una voce esistente la blocca. Una voce nuova non è bloccata.

Le azioni di riga sono **Modifica**, **Su**, **Giù** ed **Elimina**. **Elimina** chiede **Eliminare questa voce? Scomparirà da tutti i prodotti che la usavano.** L'azione di gruppo **Elimina selezionate** chiede **Eliminare le voci selezionate? Scompariranno da tutti i prodotti che le usavano.** Se un'eliminazione non si conclude, la pagina mostra **Impossibile eliminare la voce.**

**Nuova voce** nella barra apre un modulo vuoto. **Torna al modulo** torna a **Voci**.

Il titolo del modulo è **Nuova voce** o **Modifica voce**.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Domanda** | vuota | La riga su cui il cliente clicca per aprire la risposta. È l'intestazione della fisarmonica. Scriva una domanda per lingua. L'aiuto sotto il campo dice che la lingua predefinita è obbligatoria. La domanda può contenere anche shortcode. Vengono sostituiti nella pagina del prodotto e mostrati come testo semplice. Se tutte le lingue sono vuote, **Salva** mostra **Inserisci una domanda in almeno una lingua.** |
| **Risposta** | vuota | Il testo mostrato quando il cliente apre la domanda. Usi l'editor per paragrafi ed elenchi. Gli shortcode vengono sostituiti nella pagina del prodotto e l'HTML circostante resta. L'elenco degli shortcode si trova sotto questo campo: clicchi un token per inserirlo nel cursore. Compili ogni lingua che vende. Una lingua vuota non viene mostrata in quella lingua. |
| **Shortcode** | i pulsanti dei token | Clicchi un token per inserirlo dove si trova il cursore, nella domanda o nella risposta. Il negozio lo sostituisce nella pagina del prodotto con i dati di quel prodotto, nella lingua e nella valuta del cliente. Il testo salvato conserva il token, quindi una modifica di prezzo o nome aggiorna ogni voce che lo usa. Nella domanda il risultato è testo semplice. |
| **Attiva** | Sì | **Sì** mostra la voce sulle pagine prodotto corrispondenti e la include nello schema. **No** la conserva nel back office e la nasconde al negozio. |
| **Prodotti** | nessuno | Digiti il nome di un prodotto nel campo di ricerca e lo selezioni. La voce viene mostrata su questi prodotti anche se nessun altro collegamento corrisponde. Basta un collegamento corrispondente. Salvare sostituisce i collegamenti precedenti di questa voce. |
| **Categorie** | nessuna | Digiti il nome di una categoria e la selezioni. La voce viene mostrata sui prodotti collocati in queste categorie. Un collegamento è una FAQ per un'intera categoria. Le categorie padre contano solo se quell'opzione è attiva in **Visualizzazione**. |
| **Valori delle caratteristiche** | nessuno | Digiti un valore di caratteristica e lo selezioni, per esempio Cotone. La voce viene mostrata quando il prodotto ha quel valore. |
| **Valori degli attributi** | nessuno | Digiti un valore di attributo e lo selezioni, per esempio M. La voce viene mostrata quando una combinazione del prodotto usa quel valore. |
| **Tag** | nessuno | Digiti un tag e lo selezioni. La voce viene mostrata quando il prodotto ha questo tag nella lingua della pagina. |
| **Marche** | nessuna | Digiti un nome di marca e lo selezioni. La voce viene mostrata sui prodotti di queste marche. |
| **Fornitori** | nessuno | Digiti un nome di fornitore e lo selezioni. La voce viene mostrata sui prodotti di questi fornitori, incluso il fornitore predefinito e i fornitori aggiunti sulle combinazioni. |

**Salva** senza alcun collegamento mostra **Collega la voce ad almeno un prodotto, categoria, caratteristica, attributo, tag, marca o fornitore.** Se la riga non può essere memorizzata, la pagina mostra **Impossibile salvare la voce.** Un salvataggio riuscito resta sul modulo e PrestaShop conferma l'aggiornamento. **Torna all'elenco** torna al catalogo.

I pulsanti dei token, e il testo inglese di ogni pulsante, sono:

| Token | Cosa vede il cliente |
|---|---|
| `[product_name]` | Nome del prodotto |
| `[product_reference]` | Riferimento |
| `[product_ean13]` | EAN-13 |
| `[product_isbn]` | ISBN |
| `[product_upc]` | UPC |
| `[product_mpn]` | MPN |
| `[product_condition]` | Condizione: New, Used o Refurbished |
| `[product_price]` | Prezzo IVA inclusa, nella valuta del cliente |
| `[product_price_tax_excl]` | Prezzo IVA esclusa |
| `[product_price_before_discount]` | Prezzo prima dello sconto |
| `[product_discount_amount]` | Importo dello sconto, vuoto quando non c'è una riduzione |
| `[product_discount_percent]` | Percentuale di sconto, vuota quando non c'è una riduzione |
| `[product_quantity]` | Quantità disponibile della combinazione predefinita, o del prodotto se non ci sono combinazioni |
| `[product_availability]` | Etichetta «disponibile ora» se la quantità è superiore a zero, oppure etichetta «disponibile più tardi» se la quantità è zero |
| `[product_minimal_quantity]` | Quantità minima |
| `[product_manufacturer]` | Marca |
| `[product_supplier]` | Fornitore |
| `[product_category]` | Categoria predefinita |
| `[product_categories]` | Tutte le categorie |
| `[product_features]` | Elenco delle caratteristiche, nome e valore |
| `[product_feature id=ID]` | Un valore di caratteristica. Sostituisca ID con il numero della caratteristica in **Catalogo**, **Attributi e caratteristiche**. |
| `[product_tags]` | Tag nella lingua attuale |
| `[product_url]` | URL del prodotto |
| `[product_weight]` | Peso con l'unità di peso del negozio |
| `[product_description_short]` | Descrizione breve, in testo semplice |
| `[shop_name]` | Nome del negozio |
| `[shop_url]` | URL del negozio |

La riga sotto i pulsanti dice di cliccare uno shortcode per inserirlo nel cursore. Prezzi e nomi vengono sostituiti nella pagina del prodotto, nella valuta e nella lingua del cliente. `[product_price]` è lo shortcode del prezzo: diventa il prezzo vivo in una risposta, nella valuta del cliente.

### 3.4 IA

**IA** salva la connessione usata dal generatore. La riga sotto la barra dice che salvare qui non genera nulla. Usi **Generazione in blocco** per molti prodotti, oppure il blocco del prodotto per uno solo.

Clicchi una tessera. La tessera in uso mostra **Attivo**. Una tessera mostra **Chiave salvata**, **Nessuna chiave**, oppure **Chiave facoltativa** sulla tessera compatibile. I nomi delle tessere restano in inglese.

| Tessera | Cosa chiama |
|---|---|
| **OpenAI** | Modelli GPT dell'API ufficiale di OpenAI. L'elenco inizia con `gpt-4o-mini`, `gpt-4o`, `gpt-4.1-mini`, `gpt-4.1`. |
| **Anthropic Claude** | Modelli Claude dell'API ufficiale di Anthropic. L'elenco inizia con `claude-sonnet-4-5`, `claude-3-5-haiku-latest`, `claude-3-5-sonnet-latest`. |
| **Google Gemini** | Modelli Gemini dell'API ufficiale di Google. L'elenco inizia con `gemini-2.0-flash`, `gemini-1.5-pro`, `gemini-1.5-flash`. |
| **DeepSeek** | Modelli DeepSeek tramite un'API compatibile con OpenAI. L'elenco inizia con `deepseek-chat`. |
| **Mistral AI** | Modelli Mistral dell'API ufficiale. L'elenco inizia con `mistral-small-latest`, `mistral-large-latest`. |
| **OpenAI-compatible / Ollama** | Il Suo server: Ollama, vLLM, LM Studio. Può funzionare interamente in locale. L'elenco è vuoto finché non aggiunge un ID modello. |

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Fornitore** | OpenAI | Clicchi una tessera per scegliere il servizio che scrive le domande. L'elenco dei modelli cambia subito. **Salva** memorizza fornitore, chiave e modello. I fornitori ufficiali usano il proprio host. L'URL di base compare solo per la tessera compatibile. |
| **Chiave API** | vuota | Segreto dell'account presso il fornitore della tessera selezionata. Incolli una nuova chiave per sostituire quella salvata. Lasci il campo vuoto e salvi per mantenere la chiave già memorizzata per quel fornitore. La chiave è cifrata quando il server ha OpenSSL. Ogni tessera indica se una chiave è salvata. Un server locale compatibile, come Ollama, può restare senza chiave. |
| **Rimuovi la chiave salvata** | No | **Sì** elimina al salvataggio la chiave memorizzata del fornitore selezionato. Lo usi quando ruota o revoca una chiave. **No** lascia la chiave salvata al suo posto. La generazione senza chiave fallisce con i fornitori ufficiali. |
| **URL di base compatibile** | vuoto | Usato solo quando è selezionata la tessera compatibile. Inserisca la radice dell'API che termina con `/v1`, per esempio `http://localhost:11434/v1` per Ollama. I fornitori ufficiali ignorano questo campo. Lo lasci vuoto e un'esecuzione non parte: la pagina mostra **Imposta l'URL di base compatibile nella scheda IA prima di avviare un'esecuzione.** |
| **Modello** | `gpt-4o-mini` per OpenAI | ID modello inviato con ogni generazione per il fornitore selezionato. L'elenco contiene gli ID integrati e quelli che ha aggiunto nel riquadro sotto questo modulo. Un ID errato viene rifiutato dal fornitore e quella lingua viene segnata come non riuscita in coda. La tessera compatibile mostra **Nessun modello ancora. Aggiungine uno qui sotto.** finché non ne aggiunge uno. |
| **Temperatura** | 0,4 | Quanto liberamente scrive il modello, da 0 a 2. 0,4 mantiene le risposte vicine ai dati del prodotto. Un valore più alto varia la formulazione e può allontanarsi dai fatti. I valori fuori da 0 a 2 vengono riportati in quell'intervallo. Alcuni fornitori rifiutano questa impostazione. Il modulo riprova allora una volta senza di essa. |
| **Token massimi** | 2000 | Limite massimo della lunghezza di una risposta. 2000 bastano per qualche risposta breve. Lo alzi se le risposte vengono troncate. Il fornitore potrebbe fermarsi prima. Valori molto alti costano di più e possono raggiungere il limite del fornitore. Il valore salvato resta tra 200 e 8000. |
| **Domande per prodotto** | 5 | Quante coppie domanda-risposta richiedere per ogni prodotto e per ogni lingua. Questo numero è il predefinito in **Generazione in blocco** e nella pagina del prodotto. 5 è un inizio pratico. Un'esecuzione successiva può usare un numero diverso. Il valore salvato resta tra 1 e 20. |
| **Istruzioni aggiuntive** | vuote | Regole facoltative aggiunte a ogni prompt: tono, lunghezza o argomenti da evitare. Il modulo indica già al modello di scrivere `[product_name]` e `[product_price]` invece di un nome o di un prezzo fisso, così una modifica futura del prezzo resta corretta. Lasci vuoto per usare solo le istruzioni integrate. |

Clicchi **Salva**. La pagina mostra **Salvato.**

**Modelli aggiunti da te** sta sotto il modulo. È un riquadro separato per gli ID che non sono nell'elenco integrato. Rinomini o rimuova solo questi. I modelli integrati restano nell'elenco **Modello** e non hanno il pulsante elimina.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Nuovo ID modello** | vuoto | Aggiunge l'ID alla tessera del fornitore selezionata sopra e lo seleziona per la prossima esecuzione. Solo lettere, cifre e `.` `_` `:` `/` `@` `-`, fino a 100 caratteri. Un ID integrato viene rifiutato. |
| **Aggiungi modello** | un pulsante | Salva quell'ID. |
| **Salva** su una riga aggiunta da Lei | l'ID attuale | Rinomina quell'ID. Se era il modello selezionato, la selezione segue il nuovo ID. |
| **Elimina** | un pulsante su una riga aggiunta da Lei | Chiede **Rimuovere questo modello?** e toglie quell'ID. Un ID integrato non può essere rimosso. |

Finché non ne ha aggiunti, il riquadro dice **Non hai ancora un modello tuo per questo fornitore. Gli ID integrati restano nell'elenco sopra.**

Messaggi che può vedere qui:

- **Scegli un fornitore prima di aggiungere un modello.**
- **Questo ID è già un modello integrato. Resta nell'elenco e non può essere aggiunto di nuovo.**
- **Questo ID modello non è valido. Usa lettere, cifre e . _ : / @ -, fino a 100 caratteri.**
- **I modelli integrati non possono essere modificati.**
- **Questo ID è un modello integrato. Digita un ID diverso.**
- **Impossibile rinominare il modello. Usa un nuovo ID che non sia già nell'elenco.**
- **I modelli integrati non possono essere rimossi.**
- **Questo modello non l'hai aggiunto tu, quindi è stato lasciato al suo posto.**

### 3.5 Generazione in blocco

**Generazione in blocco** mette in coda molti prodotti. La riga sotto la barra dice che i filtri vuoti vengono ignorati, che **Avvia generazione** scrive una lingua per richiesta e che questa pagina mostra una barra dallo 0 % al 100 %. L'indirizzo pianificato non legge questi filtri.

**Prodotti attivi in questo negozio** mostra il numero di prodotti attivi prima di qualsiasi filtro. Quel numero è il catalogo del negozio, non un valore fisso del modulo.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Categorie** | nessuna spuntata | Spunti ogni categoria da includere. Una sottocategoria non è inclusa se non la spunta anche Lei. Lasci l'albero vuoto per ignorare le categorie. Un prodotto presente in più categorie spuntate viene messo in coda una sola volta. |
| **Marche** | nessuna selezionata | Tenga premuto Ctrl o Cmd e clicchi una o più marche. Vengono messi in coda solo i prodotti di quelle marche. Lasci l'elenco intatto per ignorare la marca. Insieme alle categorie, il prodotto deve trovarsi in una categoria spuntata e in una di queste marche. |
| **Fornitori** | nessuno selezionato | Tenga premuto Ctrl o Cmd e clicchi uno o più fornitori. Un prodotto corrisponde quando quel fornitore è quello predefinito o un fornitore aggiuntivo. Lasci l'elenco intatto per ignorare il fornitore. |
| **Salta i prodotti che hanno già una voce IA** | No | **Sì** esclude i prodotti che hanno già una voce IA collegata direttamente. Le voci scritte a mano non contano, quindi quei prodotti restano in coda. **No** rimette in coda anche i prodotti corrispondenti. |
| **Salta i prodotti che hanno già una FAQ qualsiasi** | No | **Sì** esclude i prodotti che hanno già una voce qualsiasi collegata direttamente, comprese quelle scritte a mano. **No** applica solo l'interruttore IA qui sopra. |
| **Solo prodotti disponibili a magazzino** | No | **Sì** mantiene i prodotti con quantità superiore a zero, incluse le combinazioni disponibili. **No** ignora il magazzino. |
| **Solo prodotti con immagine di copertina** | No | **Sì** salta i prodotti che non hanno un'immagine di copertina in questo negozio. **No** ignora le immagini. |
| **Solo prodotti con descrizione** | No | **Sì** mantiene i prodotti la cui descrizione breve o completa è compilata nella lingua predefinita del negozio. **No** ignora il testo. |
| **Prezzo base da** | vuoto | Prezzo di catalogo al netto delle tasse, prima dei prezzi specifici. Lasci vuoto per nessun minimo. Un prodotto sotto questo prezzo viene escluso. |
| **Prezzo base a** | vuoto | Prezzo di catalogo al netto delle tasse, prima dei prezzi specifici. Lasci vuoto per nessun massimo. Un prodotto sopra questo prezzo viene escluso. |
| **Aggiunti dal** | vuoto | Metta in coda solo i prodotti creati in questa data o dopo. Lasci vuoto per ignorare la data di creazione. |
| **Numero massimo di prodotti** | vuoto | Si ferma dopo questo numero di prodotti, dall'ID più basso. 0 o vuoto significa nessun limite. Usi un numero piccolo per provare i filtri prima di un'esecuzione completa. |
| **Lingue** | nessuna selezionata | Tenga premuto Ctrl o Cmd e clicchi le lingue da scrivere. Ogni lingua è una richiesta per prodotto. Lasci l'elenco vuoto per scrivere ogni lingua attiva di questo negozio. I nomi sono le lingue di questo negozio. |
| **Domande** | 5, il numero di **IA** | Quante coppie scrivere per ogni prodotto in questa esecuzione. Sostituisce il predefinito della scheda **IA** solo per questa coda. Usi lo stesso numero in tutte le lingue del prodotto. |
| **Voci IA esistenti del prodotto** | Aggiungi | **Aggiungi** mantiene le voci IA attuali e ne aggiunge di nuove. **Sostituisci le voci IA non bloccate collegate solo al prodotto** elimina le voci IA non bloccate collegate solo a quel prodotto, una volta per prodotto, poi scrive quelle nuove. Le voci modificate a mano sono bloccate e restano. Le voci collegate anche a una categoria o a un altro destinatario restano. |
| **Invia al modello** | vedi le schede | Scelga i dati del prodotto che il modello può leggere. Una scheda disattivata non viene inviata. Salvare un'esecuzione memorizza anche queste schede per la volta successiva. |

I titoli delle schede sotto **Invia al modello** restano in inglese. La frase sotto ogni titolo è l'aiuto della scheda.

| Scheda | All'inizio | Aiuto della scheda |
|---|---|---|
| **Name and reference** | attiva | Titolo e riferimento del prodotto. |
| **Short description** | attiva | Il riepilogo mostrato sotto il titolo. |
| **Full description** | attiva | La descrizione lunga dalla pagina del prodotto. |
| **Price summary** | attiva | Prezzo attuale e prezzo prima dello sconto. |
| **Categories** | attiva | Categoria predefinita e le altre categorie. |
| **Features** | attiva | Nomi delle caratteristiche e i loro valori. |
| **Brand** | attiva | Nome della marca. |
| **Attributes and combinations** | disattivata | Attributi di ogni combinazione. |
| **Tags** | disattivata | Tag nella lingua in cui si scrive. |
| **Supplier** | disattivata | Nome del fornitore predefinito. |
| **Stock and availability** | disattivata | Quantità ed etichetta di disponibilità. |
| **Weight and dimensions** | disattivata | Peso, larghezza, altezza e profondità. |
| **EAN, ISBN and condition** | disattivata | EAN, ISBN, UPC, MPN e condizione. |
| **Attachment titles** | disattivata | Titoli dei file allegati al prodotto. |
| **Existing questions (avoid duplicates)** | disattivata | Domande già pubblicate, così il modello non le ripete. |

**Esegui** ha due schede.

**Avvia in questo browser.** **Avvia generazione** mette in coda i prodotti che corrispondono ai campi sopra, una riga per lingua. Questa pagina resta aperta e mostra qui lo stato, poi invia ogni lingua al modello. Lasci la scheda aperta finché la barra non termina. Chiudere la scheda ferma questa pagina. La coda rimane e l'indirizzo pianificato può completarla.

La barra inizia con `Starting…` e 0 %. Mentre corre, la riga è il numero fatto, una barra e il totale. Alla fine legge `Finished.` più quel conteggio. Una lingua non riuscita aggiunge `failed` e l'ultimo testo di errore del fornitore. Quando niente corrisponde, la pagina mostra **Nessun prodotto corrisponde a questa selezione.** Quando la coda non può essere memorizzata, mostra **Impossibile creare la coda.** Quando l'esecuzione non può partire, la riga di stato mostra `The run did not start.` Una risposta che la pagina non riesce a leggere mostra `That request could not be read.` Un passo non riuscito mostra `The generation request failed.` oppure il testo di errore del fornitore. Queste frasi di avanzamento restano in inglese.

**Continua sul server.** Non è un secondo pulsante di avvio. Non legge da questo modulo categorie, numero di domande o aggiungi o sostituisci. Pianifichi un URL ogni pochi minuti. Ogni chiamata lavora circa 20 secondi e poi si ferma.

Copi **Completa una coda già esistente** dopo **Avvia generazione** se chiuderà la scheda, o quando un'esecuzione si è fermata prima che la barra arrivasse in fondo. Scrive solo le righe già in coda.

Copi **Compila i prodotti che non hanno ancora una voce IA** quando vuole che i nuovi prodotti vengano compilati senza aprire questa pagina. Questo indirizzo aggiunge ogni prodotto attivo di questo negozio che non ha una voce IA, usando il numero di domande e le scelte di dati salvate in **IA**. Aggiunge sempre, poi svuota la coda.

Tenga privati entrambi gli indirizzi. Contengono il segreto che autorizza la chiamata. **Salva** su questo modulo non è ciò che avvia l'esecuzione. Lo è **Avvia generazione**.

Prima di un'esecuzione la pagina rifiuta di partire e mostra uno di questi messaggi:

- **Scegli un fornitore nella scheda IA prima di avviare un'esecuzione.**
- **Scegli un modello nella scheda IA prima di avviare un'esecuzione.**
- **Imposta l'URL di base compatibile nella scheda IA prima di avviare un'esecuzione.** Compili **URL di base compatibile** sulla tessera compatibile. Un indirizzo vuoto non avvia l'esecuzione.
- **Salva una chiave API per il fornitore selezionato nella scheda IA prima di avviare un'esecuzione.**

### 3.6 API

**API** serve a un sistema fuori dal negozio. La riga sotto la barra dice che qui si genera una chiave, le si dà un'etichetta e si copia l'URL di base. **Mostra elenco completo** apre il catalogo delle chiavi. **Cronologia richieste** elenca ogni chiamata, con i parametri e la risposta. **Documentazione API** elenca ogni azione.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **URL di base** | l'indirizzo di questo negozio | Indirizzo che un sistema esterno chiama. Invii `action` e `api_key` come parametri di query o come campi POST. Viene accettata anche l'intestazione `X-Api-Key`. Apra **Documentazione API** per l'elenco dei parametri di ogni azione. Una chiave mancante o revocata viene rifiutata. |
| **Etichetta della chiave** | vuota | Un nome per distinguere le chiavi, per esempio ERP o staging. Non è il segreto. **Genera chiave** crea un nuovo segreto e lo mostra nella tabella. **Revoca** blocca una chiave e la lascia nell'elenco. **Elimina** rimuove la riga e il segreto. Le altre chiavi continuano a funzionare. Può creare più di una chiave. |

**Genera chiave** aggiunge la chiave e torna su questa pagina. L'anteprima **Chiavi già emesse** elenca le cinque chiavi più recenti. Il conteggio è il numero totale di chiavi. Il segreto di questa anteprima è abbreviato. **Mostra elenco completo** mostra il segreto intero da copiare nell'altro sistema.

| Colonna | A cosa serve |
|---|---|
| **Etichetta** | Il nome che ha inserito. |
| **Chiave** | L'inizio del segreto in questa anteprima. Il segreto completo è nell'elenco delle chiavi. |
| **Stato** | **Attiva** o **Revocata**. |
| **Creata** | Quando la chiave è stata generata. |
| **Ultimo utilizzo** | L'ultima chiamata accettata, oppure **Non ancora utilizzata**. |
| **Cronologia** | Apre **Cronologia richieste** filtrata su questa chiave. |
| **Revoca** | Chiede **Revocare questa chiave? Smette di funzionare subito e resta in questo elenco.** Nascosto quando la chiave è già revocata. |
| **Elimina** | Chiede **Eliminare questa chiave? La riga e il segreto vengono rimossi. Le richieste passate restano nella cronologia.** |

Quando non ci sono chiavi, la pagina dice **Nessuna chiave ancora**.

**Documentazione API** apre una finestra. **Copia** copia l'URL di base e poi mostra `OK`. Ogni azione ha **Copia URL** e **Copia cURL**. Sostituisca `YOUR_API_KEY` dell'esempio con il segreto dell'elenco chiavi. La finestra elenca anche **Parametro**, **Obbligatorio** e **Descrizione**. **Chiudi** esce dalla finestra.

| Azione | Cosa inviare | Cosa fa |
|---|---|---|
| `list` | `action=list`. Facoltativi `id_product`, `resolved=1`, `page`, `id_shop`. | Restituisce delle voci. Con `id_product`, solo quelle collegate direttamente a quel prodotto. Con `resolved=1`, l'insieme che la pagina prodotto mostrerebbe. Senza prodotto, `page` scorre il catalogo, 50 voci per pagina. |
| `get` | `action=get` e `id`. | Restituisce una voce con ogni traduzione e ogni associazione. |
| `create` | `action=create`, più una domanda e almeno un collegamento. Facoltativi `id_product`, `id_lang`, `question`, `answer`, `translations`, `assoc`, `active`, `id_shop`. | Crea una voce. `id_product` la attacca a quel prodotto. `translations` è un oggetto JSON la cui chiave è l'id lingua. Gli shortcode come `[product_name]` vengono memorizzati così come sono. `active` parte attivo. Una domanda o un collegamento mancante viene rifiutato. |
| `update` | `action=update` e `id`, più solo i campi che vuole cambiare. | Aggiorna solo i campi inviati. `replace_assoc=1` sostituisce le associazioni. Altrimenti `id_product` e `assoc` vengono aggiunti. Questa chiamata non blocca la voce. |
| `activate` | `action=activate` e `id`. | Mostra di nuovo la voce senza cambiare il testo. |
| `deactivate` | `action=deactivate` e `id`. | Nasconde la voce. Resta nel back office e sparisce dalla pagina prodotto. |
| `delete` | `action=delete` e `id`. | Elimina la voce, le sue traduzioni e i suoi collegamenti. |

`assoc` è un elenco JSON di oggetti con `type` e `id`. Il tipo è `product`, `category`, `feature_value`, `attribute`, `tag`, `manufacturer` o `supplier`. Il `id_shop` facoltativo seleziona il negozio. Senza di esso viene usato il negozio dell'URL chiamato. GET basta per una chiamata breve. Invii gli stessi campi in POST quando una domanda o una risposta è un HTML lungo.

**Cronologia richieste** è un elenco in sola lettura. La nota dice che ogni riga è una chiamata. Cerchi nei campi sotto i titoli delle colonne. **Visualizza** apre i parametri e la risposta. Il segreto della chiamata memorizzata è nascosto. Le righe restano come sono state registrate. Non può aggiungere, modificare né eliminare una riga. Se si tenta una scrittura, la pagina mostra **La cronologia richieste è un registro delle chiamate. Apri Visualizza per leggere una riga.**

Colonne: **ID**, **Data**, **Azione**, **HTTP**, **ID chiave**, **Chiave**, **Dettagli**, **IP**. **Chiavi API** nella barra apre il catalogo delle chiavi. **Torna al modulo** torna a **API**. Aprire la cronologia dal modulo usa un link di azzeramento, quindi un filtro precedente viene cancellato. **Cronologia** su una chiave mantiene il filtro di quella chiave.

Il catalogo delle chiavi si intitola **Chiavi API**. La nota dice che il segreto è mostrato perché possa copiarlo nell'altro sistema. **Revoca** ferma quella chiave e lascia la riga. **Elimina** toglie la riga e il segreto. Le richieste passate restano in **Cronologia richieste**. **Genera una chiave** torna alla scheda **API**. Questo elenco non ha un pulsante **Nuovo**. Colonne: **ID**, **Etichetta**, **Chiave**, **Stato**, **Creata**, **Ultimo utilizzo**. **Stato** indica **Attiva** o **Revocata**. **Ultimo utilizzo** indica **Non ancora utilizzata** fino alla prima chiamata accettata. Le azioni di riga sono **Revoca**, **Cronologia** ed **Elimina**. **Revoca** è nascosto su una chiave revocata e chiede **Revocare questa chiave? Smette di funzionare subito e resta in questo elenco.** **Elimina** chiede **Eliminare questa chiave? La riga e il segreto vengono rimossi. Le richieste passate restano nella cronologia.** Le azioni di gruppo sono **Revoca selezionate** ed **Elimina selezionate**, con lo stesso effetto su ogni riga spuntata. Se il dipendente non può modificare, la pagina mostra **Non hai il permesso di modificare questo.**

### 3.7 Aggiornamenti

**Aggiornamenti** interroga MyPresta.eu per una versione più recente. Il controllo segnala solo una versione. Installare il pacchetto resta un download manuale dalla pagina del modulo. Il titolo del modulo è **Aggiornamenti MyPresta**.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Controlla aggiornamenti** | un pulsante **Controlla ora** | Verifica a mano se sui server MyPresta.eu è disponibile una nuova versione di questo modulo. **Nuova versione disponibile!** significa che è elencata una versione più recente. **Il modulo è aggiornato!** significa che questa installazione corrisponde alla versione pubblicata. Il pulsante non carica uno zip. |
| **Notifiche di aggiornamento** | Attiva | **Attiva** ripete questo controllo circa ogni tre giorni mentre lavora nel back office. **Disattiva** lo salta. **Attiva** e **Disattiva** sono le due scelte. |
| **Pagina del modulo** | un link chiamato **MyFAQ** | Collegamento diretto alla pagina ufficiale del modulo, dove può leggere le modifiche. |

Clicchi **Salva**. La pagina mostra **Impostazioni di aggiornamento salvate.**

Quando è nota una versione più recente, il back office può mostrare **È disponibile una nuova versione, controlla http://MyPresta.eu per maggiori informazioni** e un link **Maggiori dettagli nel changelog**. Carichi il nuovo zip dal **Gestore dei moduli**.

### 3.8 Un prodotto

Apra **Catalogo**, **Prodotti**, il prodotto, poi il blocco **MyFAQ**. Il titolo è **FAQ su questo prodotto**. Il testo sotto dice: scegli dove questo prodotto mostra le proprie domande, verifica cosa eredita dal catalogo e scrivi voci che appartengono solo qui. Se nessuna voce è attiva, oppure la collocazione è **Nascondi**, il negozio non mostra alcun blocco MyFAQ su questo prodotto.

Le schede sono **Voci FAQ**, **Domanda e risposta** e **Genera con IA**.

**Voci FAQ** inizia con **Collocazione**.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Collocazione** | Usa l'impostazione predefinita del negozio | **Usa l'impostazione predefinita del negozio** segue **Visualizzazione**. **Footer del prodotto** o **Scheda prodotto** forza quel posto solo per questo prodotto. **Nascondi** rimuove MyFAQ da questo prodotto, compreso il blocco schema. Gli altri moduli sull'hook non vengono spostati. Il loro ordine resta in **Design**, **Posizioni**. |

**Salva** mostra **Salvato.**

**FAQ su questo prodotto** ha due elenchi. Il primo è in sola lettura e proviene da una categoria, caratteristica, attributo, tag, marca o fornitore. Il secondo è salvato per questo prodotto. Trascini una riga per cambiare l'ordine, usi l'interruttore per mostrare o nascondere una domanda ed elimini per rimuoverla.

**Dal catalogo** elenca le voci mostrate perché un altro prodotto con lo stesso collegamento le mostrerebbe comunque. Cambi il testo nel catalogo del modulo. Le colonne sono **Domanda**, **Stato** e **Azioni**. **Stato** è **Attiva** o **Inattiva**. **Modifica nel catalogo** apre quella voce. Una voce IA può mostrare **IA** e **bloccata**. Una voce digitata mostra **Scritta a mano**. Quando niente corrisponde, la scheda dice **Nulla ereditato**.

**Solo questo prodotto** elenca le domande collegate a questo prodotto. Trascini la maniglia (**Trascina per riordinare**) per impostarne l'ordine nella pagina del prodotto. L'interruttore mostra **Attiva** o **Inattiva**. **Modifica** apre **Domanda e risposta**. **Elimina** chiede **Eliminare questa voce?** Quando l'elenco è vuoto, la scheda dice **Nessuna FAQ per questo prodotto** e propone **Aggiungi una voce**. **Nessuna domanda in questa lingua** significa che la lingua attuale del back office non ha il testo della domanda; un'altra lingua può averlo.

**Domanda e risposta** è **Aggiungi una voce** o **Modifica voce**. La nota dice che il salvataggio riguarda solo questo prodotto. I collegamenti a categoria, caratteristica e gli altri restano nella schermata **Voci**. La domanda è testo semplice nel negozio. La risposta mantiene la formattazione dell'editor. Gli shortcode stanno sotto la risposta. Il pulsante della lingua a destra cambia domanda e risposta insieme.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Domanda** | vuota | Lo stesso ruolo che nel catalogo. L'aiuto dice che la lingua predefinita è obbligatoria. Se tutte le lingue sono vuote, il blocco mostra **Inserisci una domanda in almeno una lingua.** |
| **Risposta** | vuota | Lo stesso ruolo che nel catalogo. Una lingua vuota non viene mostrata in quella lingua. |
| **Shortcode** | i pulsanti dei token | Gli stessi token del catalogo. Clicchi uno di essi per inserirlo nel cursore. |
| **Attiva** | Sì | **Sì** mostra la voce. **No** la nasconde al negozio. |

**Salva** collega la voce solo a questo prodotto. Modificare una riga esistente la blocca, quindi una sostituzione successiva la conserva. Una riga nuova non è bloccata. **Nuova voce** svuota il modulo. **Elimina voce** la toglie dopo **Eliminare questa voce?** Se apre una voce collegata anche ad altro, il blocco mostra **Questa voce non è esclusiva del prodotto.** e non salva sopra. La cambi da **Modifica nel catalogo**.

Se il salvataggio non raggiunge il negozio, il blocco mostra in inglese `The save could not reach the shop. Reload the product and try again.`

**Genera con IA** scrive le domande per questo prodotto a partire dai dati del catalogo, in tutte le lingue del negozio. L'esecuzione continua in background. Dopo l'avvio qui compare una barra di avanzamento.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Domande** | 5, il numero di **IA** | Quante coppie scrivere per questo prodotto, in tutte le lingue del negozio. Sostituisce il predefinito della scheda **IA** solo per questa esecuzione. |
| **Voci IA esistenti del prodotto** | Aggiungi | **Aggiungi** mantiene le voci IA attuali e ne aggiunge di nuove. **Sostituisci le voci IA non bloccate collegate solo al prodotto** elimina le voci IA non bloccate collegate solo a questo prodotto, poi scrive quelle nuove. Le voci modificate a mano sono bloccate e restano. |
| **Invia al modello** | le stesse schede di **Generazione in blocco** | Le stesse schede. Una scheda disattivata non viene inviata. Questa esecuzione memorizza le schede per la volta successiva. |

**Genera** avvia l'esecuzione. Gli stessi quattro messaggi di **Generazione in blocco** compaiono quando mancano il fornitore, il modello, l'indirizzo compatibile o la chiave. La barra usa le stesse frasi inglesi: `Starting…`, poi i conteggi, poi `Finished.` Lasci aperta questa pagina prodotto finché la barra non finisce, oppure completi la coda con l'indirizzo di **Generazione in blocco**.

## 4. Negozio

Il cliente vede il blocco solo su una pagina prodotto.

Quando **Collocazione** è **Footer del prodotto**, la fisarmonica sta sotto il prodotto. Il titolo è **Intestazione sopra l'elenco** nella lingua del cliente. Ogni domanda è un pulsante. La risposta si apre sotto. **Apri la prima domanda** su **Sì** apre la prima risposta al caricamento. Senza JavaScript tutte le risposte sono visibili.

Quando **Collocazione** è **Scheda prodotto**, il tema aggiunge una scheda prodotto. L'etichetta della scheda è **Titolo della scheda** di quella lingua, oppure FAQ quando quella lingua è vuota. Il contenuto della scheda è la stessa fisarmonica e lo stesso titolo.

Le voci collegate direttamente al prodotto passano per prime. Poi l'ordine è la posizione del catalogo e di **Trascina per riordinare** sul prodotto. Una domanda o una risposta vuota nella lingua del cliente viene saltata. Dopo la sostituzione dei token, una domanda che resta vuota, o una risposta che non lascia più testo, viene saltata anche lei. Le voci inattive vengono saltate. **Nascondi** su questo prodotto non stampa nulla, compreso il blocco schema.

**Markup schema FAQ** su **Sì** è lo schema FAQ che PrestaShop scrive nel codice della pagina: un blocco FAQPage, costruito dalle domande che il cliente può aprire, nella lingua della pagina, e che punta all'URL del prodotto. Il cliente non vede una casella di schema separata. **No**, un elenco vuoto o **Nascondi** non stampano quel blocco.

Il cliente non può aggiungere, modificare né inviare una domanda. Non c'è una pagina dell'account per queste voci.

Se il tema non stampa il footer del prodotto e non stampa schede prodotto aggiuntive, il cliente non vede nulla anche quando le voci esistono. Sposti **MyFAQ** in **Design**, **Posizioni**, su `displayFooterProduct` o `displayProductExtraContent`. Gli altri moduli di quell'hook restano nell'ordine che Lei vi fissa.

Un tema può avere due posizioni di footer. La fisarmonica viene stampata una sola volta.

## 5. Problemi

**La pagina prodotto non ha la fisarmonica.** Il prodotto non ha una voce attiva nella lingua del cliente, la domanda o la risposta è vuota dopo la sostituzione dei token, oppure **Collocazione** di quel prodotto è **Nascondi**. Apra il prodotto, metta **Collocazione** su **Usa l'impostazione predefinita del negozio**, **Footer del prodotto** o **Scheda prodotto**, e confermi una voce **Attiva**. Se il tema non ha né footer né schede aggiuntive, sposti il modulo in **Design**, **Posizioni**.

**Una voce collegata a una categoria padre non compare.** **Includi categorie padre** è su **No**, oppure il collegamento è Home. Metta **Includi categorie padre** su **Sì**. Un collegamento a Home non copre il catalogo. Spunti il padre che vuole davvero, sotto Home.

**Il negozio mostra la voce in una lingua e non in un'altra.** Quella lingua ha una domanda o una risposta vuota. Modifichi la voce e compili entrambe. La pagina salta una lingua vuota.

**Salva mostra «Inserisci una domanda in almeno una lingua.»** Inserisca una domanda in almeno una lingua e clicchi di nuovo **Salva**.

**Salva mostra «Collega la voce ad almeno un prodotto, categoria, caratteristica, attributo, tag, marca o fornitore.»** Scelga almeno un risultato in **Prodotti**, **Categorie**, **Valori delle caratteristiche**, **Valori degli attributi**, **Tag**, **Marche** o **Fornitori**.

**Il blocco prodotto mostra «Questa voce non è esclusiva del prodotto.»** Questa domanda è collegata anche a una categoria o a un altro destinatario. Clicchi **Modifica nel catalogo** e la cambi lì.

**Il blocco prodotto mostra «The save could not reach the shop. Reload the product and try again.»** Ricarichi il prodotto e salvi di nuovo. Questa frase resta in inglese.

**Genera non fa nulla e mostra un messaggio sulla scheda IA.** Apra **IA**, scelga la tessera, salvi un modello e salvi una chiave per un fornitore ufficiale. Sulla tessera compatibile compili **URL di base compatibile**, per esempio `http://localhost:11434/v1` per Ollama. Poi rilanci l'esecuzione.

**Avvia generazione mostra «Nessun prodotto corrisponde a questa selezione.»** Tolga un filtro o spunti una categoria che contiene prodotti attivi. I filtri vuoti vengono ignorati, quindi un filtro che ha impostato è ciò che ha tolto i prodotti.

**La barra si ferma prima del 100 %.** Lasci la scheda aperta, oppure copi **Completa una coda già esistente** e la apra secondo un piano. Chiudere la scheda non cancella la coda. Una riga con `failed` e un messaggio del fornitore significa che quella lingua è stata rifiutata. Legga il messaggio, corregga la chiave o l'ID del modello e rilanci. **Aggiungi** aggiunge un altro insieme. **Sostituisci le voci IA non bloccate collegate solo al prodotto** toglie prima l'insieme IA non bloccato.

**La riga di avanzamento mostra `curl_missing`.** Il server non ha cURL. Lo faccia attivare dall'hosting. La generazione non gira senza di esso.

**Compare un avviso di nuova versione.** Il testo è **È disponibile una nuova versione, controlla http://MyPresta.eu per maggiori informazioni**. Apra **Aggiornamenti** e clicchi **Controlla ora**. Scarichi lo zip dalla pagina del modulo e lo carichi nel **Gestore dei moduli**. **Disattiva** sotto **Notifiche di aggiornamento** ferma l'avviso automatico.

**MyFAQ non è nel menu di sinistra.** È previsto. Apra **Moduli**, **Gestore dei moduli**, **MyFAQ**, **Configura**. Il catalogo, le chiavi e la cronologia si aprono da questa pagina. Se **Configura** non riesce ad aprire il catalogo, apra **Configura** una volta mentre è collegato come dipendente autorizzato a installare i moduli. Quella visita crea le pagine nascoste e dà l'accesso al profilo attuale.

**Una chiave viene rifiutata.** La chiave è stata revocata, eliminata, oppure copiata senza il segreto completo. Apra **Chiavi API**, copi la **Chiave** completa di una riga **Attiva**, oppure clicchi **Genera una chiave**.

**Non può eliminare una riga della cronologia richieste.** La pagina mostra **La cronologia richieste è un registro delle chiamate. Apri Visualizza per leggere una riga.** Usi **Visualizza**.

**Non hai il permesso di modificare questo.** Il profilo del dipendente non può modificare l'elenco delle chiavi. Apra **Configura** come amministratore, oppure dia al profilo l'accesso alle pagine del modulo.

**La prima risposta è chiusa anche se Apri la prima domanda è su Sì.** Il cliente ha JavaScript disattivato. In quel caso tutte le risposte sono visibili. Con JavaScript attivo, solo la prima parte aperta.

**La stessa domanda compare due volte.** È collegata due volte solo se ha salvato due voci. Una voce viene mostrata una sola volta. Controlli **Solo questo prodotto** e **Dal catalogo** per due righe diverse con lo stesso testo.

**Sostituisci ha lasciato una vecchia domanda IA.** Quella voce è bloccata, oppure è collegata anche a una categoria o a un altro destinatario. Bloccata è il segno della riga. La modifichi e la elimini se vuole che sparisca.

## 6. Per lo sviluppatore

### 6.1 Panoramica

Classe principale `myfaq` in `myfaq.php`. Versione `1.3.1`. Etichetta dell'elenco **MyFAQ**. Autore `mypresta.eu`. Scheda `front_office_features`. `ps_versions_compliancy` va da `1.7.0.0` a `9.99.99`. `need_instance` vale 0. `bootstrap` vale true. `config.xml` indica ancora la versione `1.0.0`; la versione della classe è quella che il negozio esegue.

`getContent()` rende `MyfaqAdminBo`. Le impostazioni di visualizzazione sono chiavi `Configuration`. Voci, collegamenti, collocazione per prodotto, chiavi API, registro delle richieste e coda IA sono tabelle. La vetrina legge le corrispondenze con `MyfaqMatcher`, sostituisce i token con `MyfaqShortcode` e stampa eventualmente `MyfaqSchema`. Le chiamate IA escono da `MyfaqAi` e `MyfaqQueue`. L'indirizzo pubblico è il controller front `api`.

Non ci sono né `enable()` né `disable()`.

### 6.2 File

- `myfaq.php` — installazione, disinstallazione, hook, valori di partenza, ingressi ajax.
- `config.xml` — metadati del pacchetto. La versione lì è `1.0.0`.
- `lib/MyfaqAdminBo.php` — moduli del back office, testi `desc`, pannello prodotto.
- `lib/MyfaqConfig.php` — fornitori, modelli, flag, cifratura, token cron.
- `lib/MyfaqRepository.php` — tabelle e CRUD.
- `lib/MyfaqMatcher.php` — quali voci mostra un prodotto.
- `lib/MyfaqShortcode.php` — catalogo dei token e sostituzione.
- `lib/MyfaqSchema.php` — pubblica il JSON-LD FAQ sulla pagina prodotto.
- `lib/MyfaqAi.php` — chiamate HTTP verso i fornitori. Richiede cURL.
- `lib/MyfaqQueue.php` — lotto e coda.
- `lib/MyfaqApi.php` — API pubblica.
- `lib/MyfaqApiDocumentation.php` — testo della finestra.
- `lib/updatesChecker.php` — classe `myfaqUpdate`.
- `lib/prestashop9compatibility.php` — modelli di aiuto, prezzo, elenchi di id.
- `lib/searchTool/searchTool.php` — autocompletamento dei campi di associazione.
- `controllers/admin/AdminMyfaqController.php` — solo ajax: ricerca, pannello prodotto, avvio di massa, passo di massa, riordino.
- `controllers/admin/AdminMyfaqEntriesController.php` — catalogo.
- `controllers/admin/AdminMyfaqKeysController.php` — chiavi.
- `controllers/admin/AdminMyfaqLogsController.php` — cronologia.
- `controllers/front/api.php` — API JSON pubblica.
- `controllers/front/cron.php` — lavoratore della coda.
- `views/templates/admin/tabs.tpl` — barra delle sezioni.
- `views/templates/admin/entries.tpl` — anteprima delle dieci più recenti.
- `views/templates/admin/product.tpl` — blocco di modifica prodotto.
- `views/templates/admin/api.tpl` — anteprima delle chiavi.
- `views/templates/admin/_shortcodes.tpl` — pulsanti dei token.
- `views/templates/admin/_api_documentation_modal.tpl` — finestra delle azioni.
- `views/templates/admin/_api_log_modal.tpl` — una chiamata memorizzata.
- `views/templates/hook/product.tpl` — fisarmonica della vetrina.
- `views/css/myfaq.css`, `views/js/myfaq.js` — vetrina.
- `views/css/myfaq-admin.css`, `views/css/myfaq-controls.css`, `views/js/admin.js` — back office. Diverse frasi di avanzamento in `admin.js` sono fisse in inglese.
- `upgrade/upgrade-1.0.0.php` — chiama `installDb()`.
- `key.php` — facoltativo. Se è presente, il controllo aggiornamenti invia il suo valore di licenza. Se è assente, il controllo invia `nlc`.

### 6.3 Controller

`AdminMyfaq`, `AdminMyfaqEntries`, `AdminMyfaqKeys` e `AdminMyfaqLogs` sono schede con `id_parent` `-1`. Non compaiono nel menu. `ensureSearchTab()` crea una scheda mancante. `grantHiddenTabAccess()` concede vedere, aggiungere, modificare ed eliminare al profilo super amministratore e al profilo del dipendente attuale.

`AdminMyfaq` serve solo l'ajax: `SearchTool`, `ProductPanel`, `BulkStart`, `BulkStep`, `Reorder`. Le stesse azioni esistono sull'oggetto del modulo perché il pannello prodotto e la pagina di massa vi fanno POST.

`AdminMyfaqEntries` è il catalogo. **Nuova voce** della barra è `addmyfaq_item`. Salvare invia `submitMyfaqItem` e reindirizza con `conf=4`. La posizione usa i link di posizione dell'helper.

`AdminMyfaqKeys` non ha un modulo di aggiunta. **Genera una chiave** rimanda a `configure=myfaq&mfq_tab=api`. `processRevoke` e la revoca di gruppo chiamano `MyfaqRepository::revokeApiKey`. Eliminare chiama `deleteApiKey`.

`AdminMyfaqLogs` rifiuta aggiunta, aggiornamento ed eliminazione con **La cronologia richieste è un registro delle chiamate. Apri Visualizza per leggere una riga.** `action=View` restituisce la richiesta e la risposta memorizzate in JSON per la finestra. `id_api_key` nella richiesta precompila il filtro della chiave, salvo se l'elenco viene azzerato.

Il controller front `api` (`module/myfaq/api`) chiama `MyfaqApi::handle()` e restituisce JSON. Imposta lo stato HTTP a partire dal risultato. Il controller front `cron` (`module/myfaq/cron`) esige `token` uguale a `MYFAQ_CRON_TOKEN`. Un token errato restituisce `403` e `{"error":"forbidden"}`. `fill_missing=1` chiama `MyfaqQueue::enqueueMissing` per il negozio attuale, poi l'azione svuota le righe in attesa per circa 20 secondi, al massimo 30 righe. Il JSON è `ok`, `enqueued_batch`, `processed`, `finished`.

Risultati dell'API: chiave assente o revocata `401` `unauthorized`. `action` sconosciuta `400` `unknown_action`. Id assente o sconosciuto `400` `missing_id` o `not_found`. Creazione senza domanda `422` `question_required`. Creazione senza collegamento `422` `association_required`. Creazione riuscita `201`. Aggiornamento, attivazione, disattivazione ed eliminazione riusciti `200`. Una scrittura non riuscita `500`.

`list` con `id_product` e `resolved=1` usa `MyfaqMatcher::forProductAllLangs`. `list` con `id_product` e senza `resolved` restituisce le voci collegate direttamente a quel prodotto. `list` senza prodotto pagina `MyfaqRepository::listItems` a 50 per pagina. L'aggiornamento usa `lock_on_update` false, quindi un aggiornamento via API non blocca la riga.

### 6.4 Hook

Registrati in `install()`:

| Hook | Ruolo |
|---|---|
| `displayHeader` | Su un controller prodotto aggiunge `views/css/myfaq.css` e `views/js/myfaq.js`. |
| `displayFooterProduct` | Rende la fisarmonica quando la collocazione risolta è `footer`. |
| `displayProductFooter` | Lo stesso rendering. Un flag statico stampa il blocco di footer una sola volta per richiesta. |
| `displayProductExtraContent` | Quando la collocazione è `tab`, restituisce un `ProductExtraContent`. Il titolo è `MYFAQ_TAB_TITLE` della lingua attuale, oppure la stringa sorgente FAQ quando quel valore è vuoto. |
| `displayAdminProductsExtra` | Blocco di modifica prodotto più CSS e JS. |
| `actionAdminControllerSetMedia` | CSS e JS di amministrazione sulla pagina prodotto, su `configure=myfaq` e sui controller di voci, chiavi e cronologia. |

Il modulo non registra hook propri e non chiama `Hook::exec` per un hook personalizzato. `displayProductExtraContent` restituisce un array vuoto quando la collocazione non è `tab`, quando l'HTML è vuoto o quando `ProductExtraContent` non esiste.

### 6.5 Override

Il modulo non sovrascrive alcuna classe né alcun controller di PrestaShop.

### 6.6 Database

`MyfaqRepository::installDb()` crea le tabelle con `_MYSQL_ENGINE_` e `utf8mb4`, e riprova con `utf8` se fallisce. `uninstall()` le elimina in questo ordine: `myfaq_queue`, `myfaq_batch`, `myfaq_api_log`, `myfaq_api_key`, `myfaq_product_display`, `myfaq_assoc`, `myfaq_item_lang`, `myfaq_item`. La disinstallazione elimina davvero le tabelle. Una reinstallazione non ripristina le righe.

| Tabella | Contenuto |
|---|---|
| `myfaq_item` | `id_item`, `id_shop` (`0` significa tutti i negozi), `active`, `position`, `source` (`manual` o `ai`), `locked`, `date_add`, `date_upd`. |
| `myfaq_item_lang` | `id_item`, `id_lang`, `question`, `answer`. |
| `myfaq_assoc` | `id_assoc`, `id_item`, `type`, `id_target`. Univoco su voce, tipo e destinazione. Tipi: `product`, `category`, `feature_value`, `attribute`, `tag`, `manufacturer`, `supplier`. |
| `myfaq_product_display` | `id_product`, `id_shop`, `mode` (`inherit`, `footer`, `tab`, `hidden`). |
| `myfaq_api_key` | `id_api_key`, `api_key`, `label`, `active`, `date_add`, `last_used`. |
| `myfaq_api_log` | `id_log`, `id_api_key`, `label`, `action`, `http_code`, `ip`, `request`, `response`, `date_add`. La chiave memorizzata è mascherata. |
| `myfaq_batch` | `id_batch`, `id_shop`, `id_employee`, `status` (`pending`, `running`, `done`), `total`, `done`, `failed`, `options`, `date_add`, `date_upd`. |
| `myfaq_queue` | `id_queue`, `id_batch`, `id_shop`, `id_product`, `id_lang`, `status` (`pending`, `running`, `done`, `error`), `attempts`, `error`, `date_upd`. Una riga `running` più vecchia di cinque minuti torna a `pending`. |

`ensureApiSchema()` gira all'apertura della scheda API, dell'elenco chiavi, della cronologia o di una chiamata pubblica all'API. Aggiunge `last_used` quando quella colonna manca e crea `myfaq_api_log` quando quella tabella manca.

Il salvataggio del catalogo imposta `lock_on_update`, quindi un aggiornamento mette `locked` a 1. `source` in un aggiornamento resta il valore attuale salvo se è impostato `force_source`. Una riga nuova del catalogo è `manual` e non bloccata. Un aggiornamento dalla pagina prodotto blocca anch'esso. Un inserimento dalla pagina prodotto collega solo quel prodotto e non blocca. La sostituzione IA elimina le righe il cui `source` è `ai`, `locked` vale 0 e che non hanno un'associazione diversa da quel prodotto.

`MyfaqMatcher::categoryIds()` aggiunge i padri solo quando `MYFAQ_INCLUDE_PARENT_CAT` vale 1. Il percorso si ferma quando `id_parent` è minore o uguale a 2, oppure dopo 25 passi.

### 6.7 Chiavi e traduzioni

Installate da `installConfig()`. Rimosse da `deleteConfig()` alla disinstallazione.

| Chiave | Quando manca o all'installazione |
|---|---|
| `MYFAQ_DISPLAY` | `footer` |
| `MYFAQ_TAB_TITLE` | `FAQ` per lingua |
| `MYFAQ_HEADING` | `FAQ` per lingua |
| `MYFAQ_INCLUDE_PARENT_CAT` | `0` |
| `MYFAQ_SCHEMA` | `1` |
| `MYFAQ_OPEN_FIRST` | `0` |
| `MYFAQ_AI_PROVIDER` | `openai` |
| `MYFAQ_AI_MODEL_OPENAI` | `gpt-4o-mini` |
| `MYFAQ_AI_MODEL_ANTHROPIC`, `MYFAQ_AI_MODEL_GEMINI`, `MYFAQ_AI_MODEL_DEEPSEEK`, `MYFAQ_AI_MODEL_MISTRAL`, `MYFAQ_AI_MODEL_COMPATIBLE` | vuote finché non viene salvato un modello. `MyfaqConfig::model()` restituisce allora il primo id integrato, oppure una stringa vuota per `compatible` |
| `MYFAQ_AI_KEY_` più il fornitore in maiuscolo | vuota. Memorizzata con `MyfaqConfig::encrypt` (`enc:` e AES-256-CBC, chiave `sha256` di `_COOKIE_KEY_`) |
| `MYFAQ_AI_BASE_URL` | vuota. `baseUrl('compatible')` usa allora `http://localhost:11434/v1`. `aiBlockReason()` rifiuta un'esecuzione finché quel valore è vuoto, quindi i pulsanti del back office non raggiungono quel ripiego |
| `MYFAQ_AI_TEMPERATURE` | `0.4`. La lettura limita da 0 a 2 |
| `MYFAQ_AI_MAX_TOKENS` | `2000`. La lettura usa 2000 quando il valore memorizzato è sotto 200, e limita a 8000 |
| `MYFAQ_AI_COUNT` | `5`. La lettura usa 5 quando il valore memorizzato è sotto 1, e limita a 20 |
| `MYFAQ_AI_PROMPT` | vuoto |
| `MYFAQ_AI_CONTEXT` | JSON di `MyfaqConfig::defaultFlags()`. Attivi: `name`, `description_short`, `description`, `prices`, `categories`, `features`, `manufacturer`. Disattivi: `combinations`, `tags`, `supplier`, `stock`, `dimensions`, `identifiers`, `attachments`, `existing` |
| `MYFAQ_CUSTOM_MODELS` | `{}` |
| `MYFAQ_CRON_TOKEN` | `bin2hex(random_bytes(16))`. `ensureCronToken()` ne crea uno quando il valore è vuoto |
| `MYFAQ_BO_TAB` | non impostata all'installazione. La sezione aperta viene memorizzata a ogni rendering. I valori sconosciuti tornano a `display` |

`deleteConfig()` elimina anche ogni `MYFAQ_AI_KEY_*` e `MYFAQ_AI_MODEL_*` per `openai`, `anthropic`, `gemini`, `deepseek`, `mistral`, `compatible`.

La disinstallazione non elimina `mypresta_updates`, `update_myfaq` né `updatev_myfaq`. Appartengono al controllo degli aggiornamenti. `mypresta_updates` è attivo quando la chiave manca. L'intervallo del controllo automatico è di 259200 secondi.

Le descrizioni dei campi stanno in `MyfaqAdminBo` (`desc` e i testi `sectionBrief`) e in `MyfaqApiDocumentation`. Le stringhe del back office passano da `$this->l()`. Aggiunga una lingua con il file `translations/{iso}.php`. Stringhe che non passano da `$this->l()`: gli aiuti degli shortcode in `MyfaqShortcode::catalogue()`, i nomi delle tessere fornitore, i titoli delle schede dati in `MyfaqConfig::contextFlagDefs()` (passano da `$this->l()`, ma non c'è una traduzione, quindi si vedono in inglese) e le frasi di avanzamento fisse in `views/js/admin.js`. Gli aiuti delle schede sono tradotti. Le etichette di stato di `conditionLabel()` sono `New`, `Used` e `Refurbished`.

`MyfaqConfig::shopScope()` restituisce `0` quando il contesto multinegozio è tutti i negozi, e l'id del negozio attuale altrimenti. I salvataggi del catalogo usano quel valore. I salvataggi della pagina prodotto usano solo l'id del negozio attuale.

### 6.8 Estendere

Sovrascriva `views/templates/hook/product.tpl` dal tema in `themes/{theme}/modules/myfaq/views/templates/hook/product.tpl`. Le variabili assegnate sono `mfq_items` (`id`, `question`, `answer`), `mfq_heading`, `mfq_open_first` e `mfq_schema`. Sovrascriva `views/css/myfaq.css` e `views/js/myfaq.js` allo stesso modo. La fisarmonica non viene resa quando l'abbinamento non restituisce alcuna riga visibile, quindi un override del tema non ha allora nulla da stampare. Non modifichi i template del modulo sul posto se il tema può portare l'override.

## 7. Aiuto

Pagina del modulo: [https://mypresta.eu/contact.html](https://mypresta.eu/contact.html)

Per scrivere a proposito di questo modulo, acceda all'account cliente su [mypresta.eu](https://mypresta.eu), apra il contatto e scelga l'argomento **Support for paid modules**. Il modulo indica che l'accesso è richiesto per questo argomento. Una volta collegato, scelga questo modulo nella cronologia degli acquisti.
