---
title: "PrestaMind AI - documentazione e manuale utente"
sidebar:
  label: "PrestaMind AI - documentazione e manuale utente"
description: "Configurazione e risoluzione dei problemi per un negozio che ha già PrestaMind AI installato."
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo PrestaMind AI - AI assistant, live chat and chatbot su MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/prestamind-ai-ai-assistant-live-chat-and-chatbot.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ai-artificial-intelligence/prestamind-ai-ai-assistant-live-chat-and-chatbot/)
>
> ---


I nomi dei pulsanti e delle schede qui sotto sono le etichette inglesi della schermata del modulo. Se la lingua del dipendente è l'italiano, PrestaShop mostra la traduzione della stessa etichetta quando il modulo la contiene.

## 1. Requisiti

PrestaShop 1.7.6, 8 e 9. PHP nella versione richiesta da quella installazione di PrestaShop. Il modulo chiama l'estensione cURL e OpenSSL oppure libsodium per salvare le chiavi dei fornitori. Non richiede un altro modulo.

Serve un account e una chiave API del fornitore scelto, a meno che Lei resti sulla demo offline. Un server locale compatibile con OpenAI (Ollama, vLLM, LM Studio) deve avere un indirizzo che il server del negozio può aprire. Il tracciamento DHL in tempo reale richiede una chiave gratuita del sito sviluppatori DHL. Il tracciamento InPost in tempo reale non richiede una chiave.

Un catalogo grande allunga la prima indicizzazione. Gli embedding inviano il testo di ogni prodotto una volta al fornitore di embedding, quindi il primo passaggio consuma token e tempo. La ricerca per parole chiave non lo fa.

## 2. Installazione

1. Carichi il modulo in **Module Manager** e prema **Install**.
2. La domanda **Delete this module and all its data (conversations, knowledge index, settings)?** compare alla disinstallazione, non all'installazione.
3. Dopo l'installazione la voce **PrestaMind AI** sta sotto **Customer service**. Se quel menu non esiste, la voce sta sotto **Improve**. **Configure** sulla riga del modulo apre la stessa pagina.
4. L'installazione non svuota la cache del negozio. La bolla resta nascosta finché Lei non la attiva.

La disinstallazione toglie la voce di menu, le tabelle del modulo e le impostazioni salvate, chiavi comprese. Ordini, prodotti, pagine CMS e regole carrello già salvati in PrestaShop restano. La cartella del modulo resta sul disco finché Lei non la elimina. Una nuova installazione parte con conversazioni vuote e indice vuoto. Non ripristina quelle precedenti.

## 3. Configurazione e lavoro quotidiano

### 3.1 Il processo completo

Lei inizia nel back office. Il visitatore inizia sul negozio.

1. Apra **PrestaMind AI**. In **Settings**, poi **Health**, sistemi ogni riga che non è OK.
2. In **Model provider** faccia clic sulla tessera del fornitore, incolli la chiave API, scelga il modello principale e il modello veloce, inserisca i prezzi e prema **Save and test the connection**.
3. In **Knowledge** della pagina delle impostazioni scelga cosa viene indicizzato. Poi apra la scheda **Knowledge** e prema **Reindex now**.
4. In **Playground** invii una domanda su un prodotto, una sulla spedizione e una su un ordine. Ogni invio spende token presso il fornitore reale.
5. In **Settings**, poi **Widget**, lasci **Show the assistant to all visitors** su off. Metta il Suo IP pubblico in **Preview only for these IP addresses**, salvi e apra il negozio. Quando le risposte sono buone, attivi il widget per tutti e svuoti una cache di pagina intera se la bolla non compare.
6. Il visitatore apre la bolla, scrive una domanda e preme la freccia. Il modulo legge prezzo, giacenza, spedizione o ordine nel negozio quando la domanda lo richiede, e mostra la risposta nella stessa finestra.
7. Uno sconto esiste solo quando un'offerta che Lei ha salvato corrisponde al carrello. **Add to cart**, **Send the return request** e **Send the quote request** attendono il clic del visitatore.
8. Se il visitatore preme **Talk to a person**, la riga è in **Escalations** e, se la console è attiva, anche sul pulsante **Live chats**. Lei preme **Take over this conversation**, scrive la risposta, preme **Send**, poi **Give back to the assistant**. Lo stato **new**, **open** o **done** non invia un'e-mail al visitatore.

### 3.2 Dove sono le schermate

Schede, in questo ordine: **Dashboard**, **Live stats**, **History**, **Conversations**, **Knowledge**, **Triggers & offers**, **Playground**, **Quality tests**, **Escalations**, **Settings**, **Updates**.

**Settings** ha una propria riga: **Health**, **Widget**, **Model provider**, **Knowledge**, **Limits & cost**, **Privacy**, **Escalation**, **Cart reminders**, **Couriers**, **Tools**. Ogni sottopagina salva solo i propri campi. **Save** mostra **Settings saved.** Il salvataggio non cancella le conversazioni né l'indice.

La dashboard del negozio, dopo l'accesso, mostra un blocco con i numeri dell'assistente, i clienti in attesa di una persona e le ultime conversazioni.

### 3.3 Dashboard

![Dashboard](https://mypresta.eu/docs/images/docs/prestamindai-dashboard.webp)

La schermata è in inglese. In questo manuale questa pagina si chiama Dashboard.

Sola lettura. Scelga **today**, **7**, **30** o **90** giorni, oppure imposti **From** e **To**. Può limitare le chiamate IA per modello, fornitore, tipo (risposte o embedding) o stato, poi prema **Filter**. **See full history** apre **History**.

La schermata mostra il fatturato degli ordini fatti entro 7 giorni da una chat, le conversazioni, quante sono state risolte senza una persona, i voti, i token inviati e ricevuti e il costo stimato. Il costo prende il prezzo salvato su ogni chiamata. Non è una fattura del fornitore. Il gruppo di controllo si imposta in **Settings**, poi **Privacy**, se vuole confrontare il valore degli ordini.

### 3.4 Live stats

![Live stats](https://mypresta.eu/docs/images/docs/prestamindai-live.webp)

La schermata è in inglese. In questo manuale questa pagina si chiama Live stats.

Lasci la pagina aperta. Le righe nuove arrivano in alto ogni pochi secondi. I pallini nascondono clienti, assistente, team, strumenti o escalation. Cerchi nel testo o inserisca un numero di chat. **thumbs down only** tiene le risposte che i visitatori hanno rifiutato. **Pause** ferma la vista. **Compact** stringe le righe. **Reset filters** mostra tutto. **Clear** svuota la vista di questa pagina. **Open chat** apre la conversazione. **Take over** Le permette di rispondere.

La pagina legge solo le conversazioni salvate. I filtri restano in questo browser. Numeri di carta, IBAN e PESEL già mascherati restano mascherati.

### 3.5 History

![History](https://mypresta.eu/docs/images/docs/prestamindai-history.webp)

La schermata è in inglese. In questo manuale questa pagina si chiama History.

L'elenco completo delle chiamate ai modelli, la più recente per prima: data, tipo, fornitore, modello, token inviati, token ricevuti, il prezzo per 1M di token valido allora, il costo stimato, il tempo e lo stato, con un collegamento alla conversazione. Gli stessi filtri di **Dashboard**. Le schede sopra l'elenco usano questo filtro.

L'elenco non conserva il testo del messaggio. Un prezzo cambiato dopo non modifica le righe vecchie. Il registro resta dopo la cancellazione delle conversazioni per la conservazione.

### 3.6 Conversations

![Conversations](https://mypresta.eu/docs/images/docs/prestamindai-conversations.webp)

La schermata è in inglese. In questo manuale questa pagina si chiama Conversations.

Filtri per **Waiting for a reply**, **Handled by a person**, escalation o sentimento negativo. L'icona occhio apre il filo: messaggi, modello, tempo di risposta, pollice su e giù, e ogni chiamata di strumento. Il cestino elimina quella conversazione, i suoi messaggi e le sue chiamate di strumento. L'eliminazione è definitiva.

Prema **Take over this conversation**. L'assistente tace per quel visitatore. Le Sue risposte compaiono come **Shop team**. **Send** pubblica la risposta. **Give back to the assistant** restituisce la chat.

**Live chats** è un pulsante fluttuante in basso a destra di ogni pagina del back office, se **Live chat console in the back office** è attivo e se Lei può aprire **PrestaMind AI**. Il contatore mostra i clienti in attesa. Può tenere aperte più finestre. Spegnere nasconde il pulsante. Questa pagina funziona ancora.

### 3.7 Knowledge

![Knowledge](https://mypresta.eu/docs/images/docs/prestamindai-knowledge.webp)

La schermata è in inglese. In questo manuale questa pagina si chiama Knowledge.

Prema **Reindex now** dopo l'installazione, dopo un cambio delle esclusioni e dopo un cambio del fornitore o del modello di embedding. **Clear answer cache** cancella le risposte salvate alle domande ripetute sulle regole. La cache si svuota anche quando Lei modifica una FAQ o un prodotto. Un documento ancora in attesa non viene usato. Una FAQ nuova serve dalla domanda successiva.

Prezzo e giacenza non stanno nell'indice. Vengono letti sul prodotto al momento della domanda.

**Add FAQ entry** / **Edit FAQ entry**: scriva domanda e risposta come l'assistente deve dirle, poi salvi.

### 3.8 Triggers

![Triggers](https://mypresta.eu/docs/images/docs/prestamindai-triggers.webp)

La schermata è in inglese. In questo manuale questa pagina si chiama Triggers.

**Triggers & offers** ha due sottopagine. Crei prima l'offerta, poi la colleghi a un trigger. Un visitatore vede al massimo un messaggio proattivo per visita. Quel trigger tace poi per il periodo di raffreddamento.

Colonne: **Name**, **When**, **Threshold**, **Page**, **Message**, **Discount**, **Active**. Sulla riga: modifica ed elimina. Il riquadro di stato spiega perché una bolla può non uscire. **Open the shop in test mode** ignora il consenso, il raffreddamento e il limite di un messaggio per visita.

| Campo | Su un trigger nuovo | Cosa fa |
|---|---|---|
| **Name** | vuoto | Un'etichetta per Lei. Vuoto prende il testo del messaggio. Il visitatore non lo vede. |
| **Type** | **Seconds on the page** | **Seconds on the page**, **Scrolled percent of the page**, **Exit intent (desktop)**, **Seconds idle on the cart page** o **Product viewed N times in a visit**. Il messaggio sta accanto al pulsante della chat. Un clic apre la chat. |
| **Threshold** | 30 | Secondi, percentuale di scorrimento o numero di visualizzazioni. Exit intent lo ignora. Tempo e carrello inattivo usano almeno 5 secondi. |
| **Page type** | **Any page** | **Any page**, **Product page**, **Category page**, **Cart / checkout** o **Home page**. Sulle altre pagine questo trigger tace. |
| **Message shown to the visitor** | vuoto, obbligatorio | Una o due frasi per ogni lingua del negozio, fino a 300 caratteri. Una lingua vuota prende la lingua predefinita. Questo testo è anche la prima riga quando il visitatore apre la chat dal messaggio. |
| **Only for these categories** | nessuna | Su una scheda, il prodotto deve stare in una di esse. Su una categoria, la categoria deve corrispondere. Vuoto significa tutte. |
| **Only for these products** | nessuno | Limita il trigger a questi prodotti. Vuoto significa tutti. |
| **Offer the assistant may grant after this trigger** | **None** | Scelga un'offerta salvata o **None**. Decidono le regole. Il modello non inventa una percentuale. |
| **How the discount is handed out** | **Give the code at once when the visitor clicks the message** | **Only if the visitor asks or hesitates over the price**, oppure subito quando la chat si apre dal messaggio. In entrambi i casi il carrello deve corrispondere all'offerta. Se **apply_offer** è deselezionato in **Tools**, il codice viene consegnato subito. |
| **Cool-down (days)** | 7 | Da 0 a 365. Dopo la bolla, quel visitatore non rivede questo trigger prima della fine del periodo. |

**Add trigger** o **Save trigger** salva la riga. **Allow proactive messages** deve essere attivo in **Privacy**, altrimenti nessun trigger parte.

### 3.9 Offers

![Offers](https://mypresta.eu/docs/images/docs/prestamindai-offers.webp)

La schermata è in inglese. In questo manuale questa pagina si chiama Offers.

Colonne: **Name**, **%**, **Min. cart**, **Valid (h)**, **Max / day**. Sulla riga, modifica ed elimina. Senza offerte l'assistente non dà mai uno sconto. Una conversazione riceve al massimo un'offerta. Il codice è monouso, entra nel carrello e non si somma ai prodotti già scontati. Il visitatore vede il nome regola **PrestaMind offer**.

| Campo | Su un'offerta nuova | Cosa fa |
|---|---|---|
| **Name** | vuoto | La Sua etichetta nel modulo del trigger. |
| **Discount percent (1-50)** | 5 | Percentuale sui prodotti che non sono già in promozione. |
| **Minimum cart value (tax incl.)** | 0 | 0 significa qualsiasi carrello. Sotto, l'offerta viene rifiutata. L'importo è nella valuta predefinita del negozio. |
| **Valid for (hours)** | 24 | Da 1 a 720. Poi il codice scade. |
| **Maximum codes per day** | 20 | 0 significa nessun tetto. Raggiunto, questa offerta si ferma fino al giorno dopo. |
| **No offer when the cart contains products from** | nessuna | Se una riga sta in queste categorie, l'intero carrello viene rifiutato. |

**Add offer** o **Save offer** salva la regola. La colleghi a un trigger prima che l'assistente possa usarla. I promemoria carrello possono allegare anch'essi un'offerta.

### 3.10 Playground

![Playground](https://mypresta.eu/docs/images/docs/prestamindai-playground.webp)

La schermata è in inglese. In questo manuale questa pagina si chiama Playground.

Usa il fornitore reale. Spende token e conta nel budget del giorno. Il filo ha il canale playground. Nulla viene inviato ai visitatori.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Page the customer is on** | **Other** | **Other**, **Home**, **Product page**, **Category** o **Cart**. L'assistente riceve questa pagina come contesto. |
| **Product id (optional)** | vuoto | Solo con **Product page**. L'id di **Catalog**, poi **Products**. L'assistente vede prezzo e giacenza attuali. |
| **Customer message** | vuoto | La domanda. **Send** mostra la risposta e la traccia. **New conversation** ricomincia. |

### 3.11 Quality tests

![Quality tests](https://mypresta.eu/docs/images/docs/prestamindai-quality-tests.webp)

La schermata è in inglese. In questo manuale questa pagina si chiama Quality tests.

Aggiunga una domanda, parole che la risposta deve contenere e parole che non deve contenere. Prema **Run all tests**. Ogni passaggio interroga il modello reale e spende token. L'elenco mostra superato o no, il motivo e la risposta. Le conversazioni di test vengono eliminate dopo il passaggio.

### 3.12 Escalations

![Escalations](https://mypresta.eu/docs/images/docs/prestamindai-escalations.webp)

La schermata è in inglese. In questo manuale questa pagina si chiama Escalations.

Le righe sono i clienti che hanno chiesto una persona, le richieste di reso e le richieste di preventivo, con un riepilogo e il contatto lasciato. La destinazione si imposta in **Settings**, poi **Escalation**. Metta lo stato su **new**, **open** o **done**. Lo stato non invia un'e-mail al visitatore. Risponda al contatto della riga o apra il collegamento della chat.

### 3.13 Health

![Health](https://mypresta.eu/docs/images/docs/prestamindai-health.webp)

La schermata è in inglese. In questo manuale questa pagina si chiama Health.

Una lista di controllo. **OK** significa pronto. **!** significa non pronto. **Repair hooks** registra gli hook mancanti e mostra **All hooks are registered.** oppure **Could not register:** con i nomi. **Test streaming** verifica che il server non metta la risposta in tempo reale in un buffer. Guardare la pagina non cambia altro. La riga del widget è OK solo quando la bolla è visibile a Lei.

### 3.14 Widget

![Widget](https://mypresta.eu/docs/images/docs/prestamindai-widget.webp)

La schermata è in inglese. In questo manuale questa pagina si chiama Widget.

| Campo | Dopo l'installazione | Cosa fa |
|---|---|---|
| **Show the assistant to all visitors** | No | Attivo: ogni visitatore vede la bolla, tranne il gruppo di controllo. Spento: nessuno, tranne gli IP di anteprima. Svuoti una cache di pagina intera dopo il cambio. |
| **Preview only for these IP addresses** | vuoto | IP pubblici separati da virgole. La pagina mostra l'IP che il negozio vede ora. Dietro un proxy può differire da quello che Lei conosce. |
| **Assistant name** | PrestaMind | Nome nell'intestazione della chat, per lingua, fino a 60 caratteri. Una lingua vuota prende la lingua predefinita. |
| **Greeting** | vuoto | Primo messaggio di una chat vuota, fino a 300 caratteri per lingua. Vuoto prende una frase integrata. |
| **AI disclosure line** | vuoto | Riga sotto l'intestazione, fino a 300 caratteri per lingua. Vuoto prende una frase integrata che dice anche che le risposte possono contenere errori. |
| **Color** | #2563eb | Colore principale del pulsante, dell'intestazione, dei pulsanti e delle bolle del visitatore. |
| **Position** | **Bottom right** | **Bottom right** o **Bottom left**. |
| **Button shape** | **Circle** | **Circle**, **Rounded square** o **Square with sharp corners**. La finestra non cambia. |
| **Button size** | **Medium (56 px)** | **Small (48 px)**, **Medium (56 px)** o **Large (68 px)**. |
| **Window corners** | **Soft (default)** | **Sharp**, **Soft (default)** o **Very round**. |
| **Button icon** | bolla integrata | **Choose icon** apre Font Awesome e Material Icons. **Use the built-in bubble** ripristina quella predefinita. L'icona è salvata nel negozio. Salvi il modulo. |
| **Button color** | vuoto (prende **Color**) | Sfondo del pulsante della chat. |
| **Icon color** | #ffffff | Colore dell'icona sul pulsante. |
| **Header color** | vuoto (prende **Color**) | Sfondo della barra in alto. |
| **Header text color** | #ffffff | Nome e pulsanti della barra in alto. |
| **Customer bubble color** | vuoto (prende **Color**) | Messaggi del visitatore, e anche i pulsanti e la freccia di invio. |
| **Customer bubble text color** | #ffffff | Testo dei messaggi del visitatore e dei pulsanti principali. |
| **Preview** | anteprima | Cambia con i campi. Nulla è salvato prima di **Save**. |
| **Tone** | **Friendly** | **Friendly**, **Formal**, **Casual** o **Expert**. Vale per i messaggi nuovi. |
| **Your instructions to the assistant** | vuoto | Fino a 1500 caratteri, aggiunti a ogni conversazione. Non annullano i prezzi attuali, il divieto di uno sconto inventato né il divieto dei dati di altri clienti. Un testo lungo costa token a ogni messaggio. |

### 3.15 Fornitore del modello e ogni modello integrato

![Fornitore del modello e ogni modello integrato](https://mypresta.eu/docs/images/docs/prestamindai-provider.webp)

La schermata è in inglese. In questo manuale questa pagina si chiama Fornitore del modello e ogni modello integrato.

Faccia clic su una tessera. Viene chiamato solo il fornitore attivo, più il ripiego se Lei ne ha impostato uno e se l'attivo fallisce prima dell'invio della prima parola. Modelli e prezzi restano presso ogni fornitore.

Dopo l'installazione l'attivo è **Demo (offline)**. Nessuna chiave, nessun costo. Risposte preparate, solo per provare l'installazione. Non è un assistente del negozio.

| Campo | Dopo l'installazione | Cosa fa |
|---|---|---|
| **Fallback provider** | **None** | Secondo fornitore in caso di timeout, limite o errore del server. Ne scelga uno la cui chiave è salvata. Quell'uso è fatturato da quel secondo fornitore. La demo non può essere il ripiego. |
| **API key** | vuoto | Incolli la chiave e salvi. Un campo vuoto conserva la chiave salvata. La chiave è cifrata e non viene più mostrata, solo i primi e gli ultimi caratteri. **Remove the stored key** su Yes, poi salvare, la elimina. Il server compatibile può restare senza chiave. |
| **Base URL** | http://localhost:11434/v1 | Solo per **OpenAI-compatible / Ollama**. L'URL deve finire con /v1. Le richieste vanno lì, non nel cloud. |
| **Main model** | tabella di quel fornitore | Consulenza prodotto, domande sull'ordine e ogni risposta che ha bisogno di strumenti. |
| **Fast model** | tabella di quel fornitore | Domande sulle regole e chiacchiere. Metta lo stesso del principale se vuole un solo modello. |
| **Your own model id** | vuoto | Lettere, cifre e . _ - : / @, fino a 100 caratteri. **Add model** salva subito insieme al resto della pagina. **Model added. Choose it as the main or fast model and enter its price.** Già presente: **That model is already on the list.** Id errato: **Enter a model id: letters, digits and . _ - : / @ only.** |
| Colonne dei prezzi | prezzi di catalogo | **USD / 1M input tokens** e **USD / 1M output tokens**. Il punto è il separatore decimale. **set price** significa che non è noto un prezzo predefinito. Un modello senza prezzo conta come gratuito, quindi il budget giornaliero in dollari non La protegge. |
| **Reset prices to defaults** | - | Rimette i prezzi integrati. **Prices set back to the built-in defaults.** I prezzi che Lei ha inserito si perdono. |
| **Remove** | - | Solo su un modello di chat personale. **Model removed.** Un modello integrato mostra un lucchetto e **Built-in models cannot be removed.** |

**Save and test the connection** salva e chiama il fornitore attivo con il modello principale. **No API key stored for the selected provider.** significa che la chiave manca ancora.

I prezzi qui sotto sono in USD per 1 milione di token, prima l'ingresso, poi l'uscita. Sono i prezzi di catalogo salvati nel modulo il 2026-10-31. Il fornitore può cambiarli. Corregga entrambe le colonne se la Sua fattura differisce. DeepSeek ha un prezzo di punta e un prezzo fuori punta. Il modulo tiene il prezzo di punta perché la stima non sia troppo bassa.

**OpenAI.** Flusso, strumenti e embedding. Modello principale predefinito **gpt-6.1-sol**. Modello veloce predefinito **gpt-6-luna**.

| Modello | Tipo | Ingresso / uscita USD per 1M | Dopo l'installazione |
|---|---|---|---|
| gpt-6.1-sol | chat | 2 / 10 | modello principale |
| gpt-6.1-terra | chat | 1 / 5 | no |
| gpt-6-luna | chat | 0.10 / 0.50 | modello veloce |
| gpt-5.5 | chat | 5 / 30 | no |
| gpt-5-mini | chat | 0.25 / 2 | no |
| gpt-4.1 | chat | 2 / 8 | no |
| gpt-4.1-mini | chat | 0.40 / 1.60 | no |
| gpt-4o-mini | chat | 0.15 / 0.60 | no |
| text-embedding-3-small | embedding | 0.02 / 0 | modello di embedding predefinito |
| text-embedding-3-large | embedding | 0.13 / 0 | no |

**Anthropic Claude.** Flusso e strumenti. Nessun embedding. Modello principale predefinito **claude-sonnet-5-5**. Modello veloce predefinito **claude-haiku-5-5**.

| Modello | Tipo | Ingresso / uscita USD per 1M | Dopo l'installazione |
|---|---|---|---|
| claude-fable-5-1 | chat | 10 / 50 | no |
| claude-opus-5-5 | chat | 4 / 20 | no |
| claude-opus-5 | chat | 5 / 25 | no |
| claude-sonnet-5-5 | chat | 2 / 10 | modello principale |
| claude-sonnet-4-6 | chat | 3 / 15 | no |
| claude-haiku-5-5 | chat | 0.10 / 0.50 | modello veloce |
| claude-haiku-4-5 | chat | 1 / 5 | no |

**Google Gemini.** Flusso, strumenti e embedding. Modello principale predefinito **gemini-2.5-flash**. Modello veloce predefinito **gemini-2.5-flash-lite**.

| Modello | Tipo | Ingresso / uscita USD per 1M | Dopo l'installazione |
|---|---|---|---|
| gemini-2.5-pro | chat | 1.25 / 10 | no |
| gemini-2.5-flash | chat | 0.30 / 2.50 | modello principale |
| gemini-2.5-flash-lite | chat | 0.10 / 0.40 | modello veloce |
| gemini-embedding-001 | embedding | 0.15 / 0 | modello di embedding predefinito |

**DeepSeek.** API compatibile con OpenAI. Nessun embedding. Il modello principale e il modello veloce predefiniti sono entrambi **deepseek-flash**.

| Modello | Tipo | Ingresso / uscita USD per 1M | Dopo l'installazione |
|---|---|---|---|
| deepseek-flash | chat | 0.30 / 1.20 | modello principale e veloce |
| deepseek-v4-pro | chat | 1.32 / 3.96 | no |

**Mistral AI.** Flusso, strumenti e embedding. Modello principale predefinito **mistral-large-latest**. Modello veloce predefinito **mistral-small-latest**. Un prezzo vuoto significa che il modulo non ha un prezzo di catalogo: la riga porta **set price** finché Lei non ne inserisce uno.

| Modello | Tipo | Ingresso / uscita USD per 1M | Dopo l'installazione |
|---|---|---|---|
| mistral-large-latest | chat | 0.50 / 1.50 | modello principale |
| mistral-medium-latest | chat | nessun prezzo integrato | no |
| mistral-small-latest | chat | nessun prezzo integrato | modello veloce |
| open-mistral-nemo | chat | nessun prezzo integrato | no |
| mistral-embed | embedding | nessun prezzo integrato | modello di embedding predefinito |

**OpenAI-compatible / Ollama.** Il Suo server. I prezzi integrati sono 0 / 0, anche per i modelli locali. Il modello principale e il modello veloce predefiniti sono **llama3.1**. Il modello di embedding predefinito è **nomic-embed-text**.

| Modello | Tipo | Ingresso / uscita USD per 1M | Dopo l'installazione |
|---|---|---|---|
| llama3.1 | chat | 0 / 0 | modello principale e veloce |
| llama3.2 | chat | 0 / 0 | no |
| mistral | chat | 0 / 0 | no |
| qwen2.5 | chat | 0 / 0 | no |
| nomic-embed-text | embedding | 0 / 0 | modello di embedding predefinito |
| mxbai-embed-large | embedding | 0 / 0 | no |
| bge-m3 | embedding | 0 / 0 | no |
| snowflake-arctic-embed | embedding | 0 / 0 | no |

**Demo (offline).** Nessuna chiave. Prezzi 0 / 0.

| Modello | Tipo | Ingresso / uscita USD per 1M | Dopo l'installazione |
|---|---|---|---|
| mock | chat | 0 / 0 | modello principale e veloce, e questo fornitore è l'attivo |
| mock-64 | embedding | 0 / 0 | quando il fornitore di embedding è la demo |

Alcuni modelli OpenAI recenti ignorano **Temperature**. Un id che il fornitore non conosce compare come errore del fornitore su **Dashboard**.

### 3.16 Impostazioni Knowledge

![Impostazioni Knowledge](https://mypresta.eu/docs/images/docs/prestamindai-knowledge-settings.webp)

La schermata è in inglese. In questo manuale questa pagina si chiama Impostazioni Knowledge.

L'indirizzo cron è su questa pagina. Lo chiami ogni 10-15 minuti. Ogni chiamata indicizza le pagine nuove e modificate, costruisce gli embedding, invia i promemoria carrello se Lei li ha attivati, elimina le conversazioni più vecchie della conservazione e svuota la cache delle risposte e le righe di limite più vecchie di due giorni. Senza cron l'indice si aggiorna comunque quando i visitatori scrivono o quando girano gli hook di prodotto e CMS. Conservazione ed embedding passano allora solo dai pulsanti.

| Campo | Dopo l'installazione | Cosa fa |
|---|---|---|
| **Embeddings provider** | **None (keyword search)** | **None (keyword search)**, **openai**, **gemini**, **mistral**, **compatible** o **demo**. Anthropic e DeepSeek non sono in questo elenco. Il cambio richiede **Reindex now**. |
| **Embeddings model** | **Default for the chosen provider** | Un modello del fornitore qui sopra. I vettori di due modelli non si confrontano. Un modello di un altro fornitore viene ignorato e si usa il predefinito. Reindicizzi dopo il cambio. |
| **Other embeddings model** | vuoto | Id esatto di un modello assente dall'elenco, per esempio un modello Ollama. Se è compilato, sostituisce la scelta qui sopra. |
| **Index products** | Sì | Indicizza nome, marca, categorie, caratteristiche e descrizioni dei prodotti attivi e visibili. No: le domande sui prodotti non hanno testo di catalogo. |
| **Index CMS pages** | Sì | Indicizza le pagine CMS attive. Non indicizzi le pagine che contengono note interne. |
| **Never use these categories** | nessuna | I prodotti di queste categorie non vengono indicizzati e non possono essere mostrati, confrontati o proposti nel carrello. Reindicizzi dopo il cambio. |
| **Never use these products** | nessuno | La stessa cosa per prodotti singoli. |
| **Cache answers to repeated policy questions** | Sì | Visitatori, solo la prima domanda, e mai una risposta che contiene un prezzo o un ordine. **Clear answer cache** sulla scheda Knowledge dopo la modifica di una pagina di regole. |
| **Cache lifetime (hours)** | 24 | Da 1 a 720. Poi il modello risponde di nuovo. |

### 3.17 Limiti e costo

![Limiti e costo](https://mypresta.eu/docs/images/docs/prestamindai-limits.webp)

La schermata è in inglese. In questo manuale questa pagina si chiama Limiti e costo.

La riga in alto mostra richieste, token e costo stimato del giorno. Quando un budget giornaliero è raggiunto, l'assistente invia un breve avviso e propone di passare la domanda al Suo team fino al giorno dopo.

| Campo | Dopo l'installazione | Cosa fa |
|---|---|---|
| **Daily budget (USD)** | 0 | 0 significa nessun tetto. Funziona solo se i modelli usati hanno un prezzo. Quando il costo del giorno raggiunge il tetto, le chiamate al modello si fermano fino a mezzanotte. |
| **Daily token budget** | 0 | 0 significa nessun tetto. Conta i token anche se il prezzo è 0. 1000000 token sono circa qualche centinaio di conversazioni. |
| **Messages per minute per visitor IP** | 8 | Da 1 a 60. Un invio più rapido riceve una richiesta di attesa e nessuna chiamata al modello. |
| **Messages per conversation per day** | 60 | Da 1 a 500. Poi la conversazione è bloccata per la giornata. |
| **Max reply tokens** | 700 | Da 150 a 3000. A 700, circa 450 parole. Un limite corto taglia la risposta. |
| **Max tool steps per message** | 5 | Da 1 a 8. Quante letture in tempo reale (ricerca, prodotto, spedizione) un messaggio può avviare. 1 ferma la ricerca in più passaggi. |
| **Max characters per customer message** | 800 | Da 100 a 2000. Il testo più lungo viene tagliato. |
| **Messages of history sent to the model** | 12 | Da 2 a 30. 12 sono gli ultimi sei scambi. Più cronologia invia più token. |
| **Temperature (0-1)** | 0.3 | Da 0.2 a 0.4 resta più vicino ai dati del negozio. Più alto varia la formulazione. Alcuni modelli OpenAI recenti lo ignorano. |

### 3.18 Privacy

![Privacy](https://mypresta.eu/docs/images/docs/prestamindai-privacy.webp)

La schermata è in inglese. In questo manuale questa pagina si chiama Privacy.

| Campo | Dopo l'installazione | Cosa fa |
|---|---|---|
| **Mask card numbers, IBAN and PESEL** | Sì | Li sostituisce con [card], [iban] e [id] prima di salvare il testo e prima di inviarlo al fornitore. |
| **Delete conversations after (days)** | 90 | 0 le conserva. L'URL cron elimina le conversazioni più vecchie. Le statistiche degli ordini restano. |
| **Order status without signing in, for registered customers** | Sì | Un visitatore può chiedere con il riferimento ordine e l'e-mail del pagamento. No: quella coppia vale solo per gli ordini ospite, e un cliente con account deve accedere. Al massimo 10 tentativi in 10 minuti. |
| **Allow proactive messages** | Sì | No spegne tutti i trigger. |
| **Proactive triggers wait for consent** | Sì | Nessuna bolla finché il banner dei cookie non chiama la funzione di consenso. La chat stessa funziona. No: i trigger partono per tutti. |
| **Control group (% of visitors)** | 0 | Da 0 a 50. Quei visitatori non vedono mai l'assistente. **Dashboard** può confrontare il valore degli ordini. |

**Delete old conversations** è un modulo a parte. **Older than (days)** parte da 30. **Delete** elimina quelle conversazioni subito. Il messaggio è **Deleted N conversations.** Non si può tornare indietro.

### 3.19 Impostazioni Escalation

![Impostazioni Escalation](https://mypresta.eu/docs/images/docs/prestamindai-escalation.webp)

La schermata è in inglese. In questo manuale questa pagina si chiama Impostazioni Escalation.

| Campo | Dopo l'installazione | Cosa fa |
|---|---|---|
| **Live chat console in the back office** | Sì | Mostra il pulsante **Live chats**. Lo vedono solo i dipendenti che possono aprire **PrestaMind AI**. Off nasconde il pulsante. **Conversations** funziona ancora. |
| **E-mail for hand-offs** | vuoto | Ogni escalation invia un riepilogo e il contatto lasciato dal visitatore. Vuoto significa nessuna e-mail. La posta del negozio deve funzionare. |
| **Webhook type** | **Slack** | **Slack**, **Telegram** o **Generic JSON**. |
| **Webhook URL** | vuoto | URL di incoming webhook Slack, Telegram `https://api.telegram.org/bot<TOKEN>/sendMessage`, o qualsiasi URL https. Vuoto significa nessun webhook. Il risultato sta nell'elenco **Escalations**. |
| **Telegram chat id** | vuoto | Id numerico della chat o del gruppo. Ignorato per Slack e Generic JSON. |
| **Offer a person when sentiment falls below** | -0.5 | Da -1 a 0. Più vicino a 0 reagisce prima. L'assistente si scusa e propone di passare la pratica al team. |

### 3.20 Promemoria carrello

![Promemoria carrello](https://mypresta.eu/docs/images/docs/prestamindai-reminders.webp)

La schermata è in inglese. In questo manuale questa pagina si chiama Promemoria carrello.

Nulla parte finché **Send cart reminders** non è su Yes e l'URL cron non gira. Un'e-mail per carrello abbandonato, solo verso un cliente con account. I visitatori senza account non ricevono questa e-mail.

| Campo | Dopo l'installazione | Cosa fa |
|---|---|---|
| **Send cart reminders** | No | Attivo: il prossimo passaggio cron invia i promemoria che corrispondono. Spento: non parte nulla di nuovo. Le righe già inviate restano nell'elenco. |
| **Only customers who subscribed to the newsletter** | Sì | Sì: i clienti senza la casella newsletter non ricevono nulla. |
| **Send after (hours of inactivity)** | 3 | Almeno 1. Il carrello deve restare così per quel periodo. |
| **Stop after (hours since the last change)** | 72 | Deve essere maggiore del valore sopra. I carrelli più vecchi vengono ignorati. |
| **Minimum cart value (tax incl.)** | 0 | 0 significa qualsiasi carrello. L'importo è nella valuta del negozio. |
| **Discount code in the e-mail** | **No discount code** | Una delle Sue offerte, oppure nessuna. Le regole dell'offerta valgono ancora. Se il tetto del giorno è raggiunto, l'e-mail parte senza codice. |
| **E-mail subject** | vuoto | Per lingua. Vuoto prende un oggetto integrato. Il cliente riceve l'oggetto della lingua del suo account. |

**Send a test e-mail** usa **Send the test to** (prima la Sua e-mail del back office) e **Send test**. Un campione parte subito. Non viene registrato e non crea un codice. **Test e-mail sent.** oppure **The e-mail could not be sent. Check the e-mail settings of the shop.** Un indirizzo errato mostra **Enter a valid e-mail address.**

**Latest reminders** elenca data, carrello, cliente, codice e stato.

### 3.21 Couriers

![Couriers](https://mypresta.eu/docs/images/docs/prestamindai-couriers.webp)

La schermata è in inglese. In questo manuale questa pagina si chiama Couriers.

La pagina elenca i metodi di spedizione di questo negozio. Se non ce ne sono, Lei vede **Your shop has no shipping methods yet. Add them in Shipping > Carriers; they appear here automatically.**

Per ogni metodo, **tracking link** è un indirizzo per lingua. Metta `{n}` dove va il numero di tracciamento. Un indirizzo senza `{n}`, o che non inizia con http o https, viene ignorato. Una lingua vuota prende la lingua predefinita. Se il corriere ha già un URL di tracciamento in **Shipping**, poi **Carriers**, quell'URL viene prima. Senza alcun collegamento, l'assistente cita solo il numero.

**live status** compare solo se il nome contiene InPost o DHL, o se Lei l'ha scelto prima. **No live status (tracking link only)** tiene il collegamento. InPost non ha bisogno di una chiave. DHL mostra **DHL API key**: si iscriva sul sito sviluppatori DHL, crei un'applicazione Shipment Tracking - Unified e incolli la chiave. La chiave gratuita consente circa 250 chiamate al giorno. La chiave è salvata cifrata. Senza di essa lo stato DHL in tempo reale viene saltato e si usa il collegamento. Le risposte in tempo reale restano in cache 10 minuti.

### 3.22 Tools

![Tools](https://mypresta.eu/docs/images/docs/prestamindai-tools.webp)

La schermata è in inglese. In questo manuale questa pagina si chiama Tools.

Deselezioni uno strumento perché il modello non lo riceva. Uno strumento spento non può essere eseguito. In modalità catalogo gli strumenti di carrello, offerta e contenuto del carrello restano spenti. Una domanda sulle regole o una conversazione leggera può chiamare solo **create_ticket**.

| Strumento | Rischio a schermo | Ha bisogno di | Cosa ottiene il visitatore |
|---|---|---|---|
| search_products | lettura | - | Fino a sei schede. Prezzo massimo facoltativo e solo disponibili. Il visitatore preme **Add to cart**. |
| popular_products | lettura | - | Più venduti dagli ordini reali, 90 giorni predefiniti, da 7 a 365, fino a sei schede. Nessuna cifra esatta di vendita. |
| get_product_live | lettura | - | Prezzo, giacenza, caratteristiche e varianti attuali di un prodotto. |
| compare_products | lettura | - | Due o tre prodotti affiancati. |
| suggest_substitute | lettura | - | Equivalenti che sono disponibili. |
| get_cart | lettura | un carrello | Contenuto e totale. |
| add_to_cart | lo schermo segna la conferma | conferma del cliente | Una scheda. Quantità da 1 a 20. Il modulo non aggiunge la riga. Il visitatore preme **Add to cart**. |
| check_shipping | lettura | - | Metodi, tempi e soglia di spedizione gratuita. Codice ISO del paese facoltativo. |
| get_order_status | lettura | sessione, oppure riferimento più e-mail del pagamento | Stato di quell'ordine. |
| track_parcel | lettura | la stessa identità dello stato ordine | Corriere, numero e collegamento. InPost in tempo reale senza chiave. DHL in tempo reale con la chiave DHL. |
| start_return | conferma | cliente connesso | Nulla parte prima di **Send the return request**. |
| request_quote | conferma | il modulo | Articoli, società e contatto. Nulla parte prima di **Send the quote request**. |
| create_ticket | passaggio | un visitatore senza account è invitato a dare un'e-mail o un telefono | **Talk to a person** apre un'escalation. |
| apply_offer | decidono le regole | un carrello | Un codice solo se un'offerta salvata corrisponde. Nessuna regola corrispondente significa nessun codice. |

**Save** salva le caselle.

### 3.23 Updates

![Updates](https://mypresta.eu/docs/images/docs/prestamindai-updates.webp)

La schermata è in inglese. In questo manuale questa pagina si chiama Updates.

**Check now** confronta la versione installata con quella dei server MyPresta.eu. Lasci gli avvisi automatici attivi per vedere un avviso nel back office. Il modulo non si aggiorna mai da solo. Lei installa da sé il nuovo pacchetto.

## 4. Negozio

La bolla è nascosta finché **Show the assistant to all visitors** non è attivo, tranne per gli IP dell'elenco di anteprima. I visitatori del gruppo di controllo non la vedono.

Il visitatore preme il pulsante nell'angolo che Lei ha scelto. La finestra mostra il nome dell'assistente, la riga informativa e il saluto. Il visitatore scrive e preme la freccia. Sul negozio non c'è un pulsante con etichetta Send. La risposta arriva nella finestra se il server non la mette in un buffer.

Le schede mostrano **Add to cart**. Un reso attende **Send the return request**. Un preventivo attende **Send the quote request**. **Talk to a person** passa la chat al team. Finché Lei ha preso in carico la conversazione, i nuovi messaggi del visitatore vengono salvati e le Sue risposte compaiono come **Shop team**.

Una bolla proattiva compare solo se i trigger sono consentiti, se il visitatore corrisponde alla regola e se il consenso è dato quando Lei lo richiede. Una bolla per visita. Il collegamento di prova di **Triggers** è per Lei, non per i clienti.

L'indirizzo cron non è una pagina per i visitatori. Lo apra solo dallo scheduler del server. Un token errato riceve un rifiuto e non fa nulla.

## 5. Problemi

**La bolla manca.** **Show the assistant to all visitors** è su off, quel visitatore è nel gruppo di controllo, oppure una cache di pagina intera tiene la pagina vecchia. Attivi l'interruttore o aggiunga il Suo IP all'elenco di anteprima, salvi e svuoti la cache di pagina intera.

**Could not create the module tables.** L'installazione si è fermata prima della voce di menu. Legga il messaggio del database, sistemi i diritti dell'utente del database e reinstalli.

**Could not register hook** seguito da un nome di hook, oppure **Could not register:** in **Health**. Prema **Repair hooks**. Se la riga resta, l'utente del negozio non può scrivere gli hook. Sistemi i diritti del database e prema di nuovo il pulsante.

**Could not add the menu tab.** L'installazione non ha finito il menu. Apra **Module Manager**, disinstalli se il modulo è installato a metà e reinstalli. **Configure** prova anche a ricreare la voce di menu.

**No API key stored for the selected provider.** Incolli la chiave in **Model provider** e prema **Save and test the connection**. Un campo password vuoto non elimina una chiave. **Remove the stored key** la elimina.

**That model is already on the list.** Lo scelga come **Main model** o **Fast model** invece di aggiungerlo di nuovo.

**Enter a model id: letters, digits and . _ - : / @ only.** Riscriva l'id dall'elenco modelli del fornitore. Gli spazi non sono ammessi.

**Built-in models cannot be removed.** Lasci la riga. Aggiunga un id personale se Le serve un altro modello.

**Errori del fornitore su Dashboard.** La chiave è sbagliata, il fornitore non conosce l'id del modello, oppure il fornitore non risponde. Se un ripiego è impostato e il fallimento arriva prima della prima parola, risponde il ripiego. Sistemi la chiave o il modello, poi usi **Playground**.

**La risposta arriva in un blocco, non parola per parola.** Prema **Test streaming** in **Health**. Se il test fallisce, il proxy o l'host mette la risposta in un buffer. Chieda all'host di spegnerlo sull'indirizzo della chat del negozio.

**I cannot answer right now.** Il budget del giorno o il budget di token è raggiunto, oppure il fornitore è fallito e non c'è un ripiego. Alzi il budget, aspetti il giorno dopo o sistemi il fornitore. L'assistente propone di passare la domanda al team.

**Richiesta di attendere, o conversazione bloccata.** Il visitatore ha inviato più di **Messages per minute per visitor IP** o più di **Messages per conversation per day**. Attenda, oppure alzi il limite.

**Un trigger non esce mai.** Legga il riquadro di **Triggers**. **Allow proactive messages** è su off, il trigger è inattivo, **apply_offer** è su off mentre il trigger attende che il visitatore chieda, oppure i trigger attendono il consenso e il banner non chiama mai la funzione. Usi **Open the shop in test mode**. Dopo un test reale il raffreddamento nasconde questo trigger in quel browser.

**Lo sconto non esce mai.** Non c'è un'offerta, l'offerta non è collegata al trigger, il carrello è sotto il minimo, il tetto del giorno è raggiunto, un prodotto sta in una categoria esclusa, oppure il prodotto è già scontato. L'assistente non inventa una percentuale.

**Add to cart non aggiunge nulla da solo.** La scheda è solo una scheda. Il visitatore preme **Add to cart**. In modalità catalogo gli strumenti carrello restano spenti.

**Test e-mail sent.** è un successo. **The e-mail could not be sent. Check the e-mail settings of the shop.** significa che la posta del negozio è fallita. **Enter a valid e-mail address.** significa che l'indirizzo di prova è vuoto o errato. Le e-mail ai clienti richiedono anche **Send cart reminders** su Yes e un URL cron in esecuzione.

**Deleted N conversations.** Lei ha premuto **Delete** in **Privacy**. Quei fili sono spariti.

## 6. Per lo sviluppatore

### 6.1 Panoramica

Nome tecnico `prestamindai`, classe `prestamindai`, versione nel file `1.8.9`, nome mostrato **PrestaMind AI**, autore MyPresta.eu, scheda `front_office_features`. Compatibilità da 1.7.6.0, massimo `99.99.99`. Non c'è un `enable()` né un `disable()` proprio. Disattivare in PrestaShop ferma gli hook registrati. Attivare li registra di nuovo tramite il core.

`PmaiConfig` legge e scrive le chiavi `Configuration` con il prefisso `PMAI_`. `PmaiProviderRouter` sceglie `PmaiOpenAiProvider`, `PmaiAnthropicProvider`, `PmaiGeminiProvider` o `PmaiMockProvider`. DeepSeek e l'URL compatibile usano il client compatibile con OpenAI. `PmaiOrchestrator` costruisce il prompt, chiama il modello e avvia gli strumenti di `PmaiToolRegistry`. I prezzi usati per una chiamata vengono copiati sulla riga di utilizzo.

### 6.2 File

| File | Ruolo |
|---|---|
| `prestamindai.php` | Installazione, disinstallazione, hook, scheda di menu, reindirizzamento da **Configure**. |
| `sql/install.php` | Crea le 16 tabelle. |
| `sql/uninstall.php` | Elimina quelle tabelle. |
| `controllers/admin/AdminPrestamindaiController.php` | Schede del back office e azioni POST. |
| `controllers/front/chat.php` | Indirizzo della chat sul negozio. |
| `controllers/front/cron.php` | Un URL cron. |
| `src/Service/PmaiConfig.php` | Valori di partenza, elenchi modelli, prezzi integrati, modelli personali. |
| `src/Admin/PmaiForms.php` | Ogni modulo del back office e le descrizioni dei campi. |
| `src/Admin/PmaiSectionHelp.php` | Testo di aiuto di ogni scheda. |
| `src/Agent/PmaiToolRegistry.php` | I 14 strumenti e il filtro della modalità catalogo. |
| `src/Llm/PmaiOpenAiProvider.php` | OpenAI, DeepSeek e l'URL compatibile. |
| `src/Llm/PmaiAnthropicProvider.php` | Anthropic. |
| `src/Llm/PmaiGeminiProvider.php` | Gemini. |
| `src/Llm/PmaiMockProvider.php` | Demo offline. |
| `src/Knowledge/PmaiIndexer.php` | Scoperta e reindicizzazione. |
| `src/Safety/PmaiGuardrails.php` | Sostituisce carta, IBAN e PESEL. |
| `upgrade/` | Gli aggiornamenti di versione chiamano `upgradeDb()`. |
| `translations/{iso}.php` | Stringhe del back office. |
| `views/` | Template, CSS e JS del back office e del negozio. |

### 6.3 Controller

`AdminPrestamindai` è la classe di menu. Il genitore è la prima classe esistente tra `AdminParentCustomerThreads`, `AdminCustomerThreads` e `IMPROVE`. L'etichetta della scheda è **PrestaMind AI**. `getContent()` reindirizza a questo controller.

`pmai_tab` è uno tra `dashboard`, `live`, `history`, `conversations`, `knowledge`, `triggers`, `playground`, `evals`, `escalations`, `settings`, `updates`. Le impostazioni leggono anche `pmai_sub`: `health`, `widget`, `provider`, `knowledge`, `limits`, `privacy`, `escalation`, `reminders`, `couriers`, `tools`.

`controllers/front/chat.php` accetta le operazioni del negozio init, message, feedback, confirm, add_to_cart, escalate, poll, event e open_trigger. `controllers/front/cron.php` richiede il token cron. Un token errato restituisce il JSON `ok: false` e `error: token`.

### 6.4 Hook

Registrati all'installazione: `displayBackOfficeHeader`, `dashboardZoneTwo`, `actionAdminControllerSetMedia`, `displayHeader`, `displayBeforeBodyClosingTag`, `displayFooter`, `actionObjectProductAddAfter`, `actionObjectProductUpdateAfter`, `actionObjectProductDeleteAfter`, `actionObjectCmsAddAfter`, `actionObjectCmsUpdateAfter`, `actionObjectCmsDeleteAfter`, `actionValidateOrder`, `registerGDPRConsent`, `actionDeleteGDPRCustomer`, `actionExportGDPRData`.

`displayBeforeBodyClosingTag` mostra il widget, `displayFooter` è il ripiego. Gli hook di prodotto e CMS segnano i documenti da reindicizzare. `actionValidateOrder` collega l'ordine al fatturato. Gli hook GDPR esportano o eliminano le righe di quel cliente. **Repair hooks** chiama `ensureHooks()` per ogni nome mancante. Il modulo non pubblica hook propri per altri moduli.

### 6.5 Override

Il modulo non sovrascrive alcuna classe né alcun controller di PrestaShop.

### 6.6 Database

La disinstallazione esegue `DROP TABLE` su ogni tabella qui sotto. L'installazione usa `CREATE TABLE IF NOT EXISTS`. Una disinstallazione fallita che avesse lasciato le tabelle terrebbe le righe vecchie. Una disinstallazione normale le elimina, e l'installazione successiva è vuota.

| Tabella | Contenuto |
|---|---|
| `PREFIX_pmai_thread` | Una conversazione: negozio, cliente, visitatore, canale, stato, pagina. |
| `PREFIX_pmai_message` | Messaggi del filo, payload delle schede compreso. |
| `PREFIX_pmai_tool_call` | Nome dello strumento, argomenti e risultato di un messaggio. |
| `PREFIX_pmai_doc` | Documento indicizzato prodotto, CMS o FAQ. |
| `PREFIX_pmai_chunk` | Pezzi di un documento, embedding compreso se esiste. |
| `PREFIX_pmai_cache` | Risposte sulle regole messe in cache. |
| `PREFIX_pmai_trigger` | Regole dei trigger. |
| `PREFIX_pmai_offer` | Regole di sconto. |
| `PREFIX_pmai_event` | Eventi del negozio per trigger e statistiche. |
| `PREFIX_pmai_usage` | Una chiamata di modello: fornitore, modello, token, istantanea del prezzo, costo, stato. Nessun testo del messaggio. |
| `PREFIX_pmai_request` | Righe del limite di richieste. |
| `PREFIX_pmai_cart_reminder` | Un promemoria carrello inviato. |
| `PREFIX_pmai_escalation` | Passaggio, reso o preventivo, e risultato della notifica. |
| `PREFIX_pmai_ratelimit` | Contatori della finestra breve. |
| `PREFIX_pmai_eval_case` | Una domanda di qualità e le parole richieste. |
| `PREFIX_pmai_eval_run` | Un passaggio di quei test. |

`PmaiConfig::PRICES_CHECKED` vale `2026-10-31`. Gli id di chat e di embedding e i prezzi integrati stanno in `PmaiConfig::builtinModels()`, `builtinEmbeddingModels()` e `builtinPrices()`. Gli id personali sono JSON in `PMAI_CUSTOM_MODELS`. I prezzi modificati sono JSON in `PMAI_MODEL_PRICES` e prevalgono sul prezzo integrato.

### 6.7 Chiavi e traduzioni

Ogni chiave è `PMAI_` più il nome di `PmaiConfig::defaults()`. I segreti dei fornitori sono `PMAI_KEY_OPENAI`, `PMAI_KEY_ANTHROPIC`, `PMAI_KEY_GEMINI`, `PMAI_KEY_DEEPSEEK`, `PMAI_KEY_MISTRAL`, `PMAI_KEY_COMPATIBLE`, `PMAI_KEY_MOCK` e `PMAI_KEY_DHLTRACK`. Sono cifrati con libsodium se esiste `sodium_crypto_secretbox`, altrimenti con OpenSSL. `PMAI_CRON_TOKEN` è un hex casuale creato all'installazione se è vuoto.

Le chiavi di scelta del modello sono `PMAI_MODEL_MAIN_{PROVIDER}` e `PMAI_MODEL_FAST_{PROVIDER}`. Dopo l'installazione: OpenAI `gpt-6.1-sol` / `gpt-6-luna`, Anthropic `claude-sonnet-5-5` / `claude-haiku-5-5`, Gemini `gemini-2.5-flash` / `gemini-2.5-flash-lite`, DeepSeek `deepseek-flash` / `deepseek-flash`, Mistral `mistral-large-latest` / `mistral-small-latest`, compatible `llama3.1` / `llama3.1`, mock `mock` / `mock`. `PMAI_PROVIDER` vale `mock`. `PMAI_EMBED_PROVIDER` vale `none`. `PMAI_EMBED_MODEL` è vuoto, quindi si usa il primo modello di embedding integrato del fornitore scelto.

`PMAI_BOT_NAME`, `PMAI_GREETING`, `PMAI_DISCLOSURE` e `PMAI_REMINDER_SUBJECT` sono multilingue. L'aiuto dei campi è l'HTML `desc` costruito in `PmaiForms`. Aggiunga una lingua traducendo `translations/{iso}.php`. Le stringhe che non passano da `$this->l()` restano come sono scritte negli array PHP (nomi delle tessere, id dei modelli, id degli strumenti).

### 6.8 Estendere

Il template e il CSS del widget del negozio si possono sovrascrivere nel tema nel modo abituale di PrestaShop, sotto `modules/prestamindai/views/`. Il back office non è una sovrascrittura di tema. Non cambi gli id dei modelli nel tema. Aggiunga un modello in **Model provider**. Un banner dei cookie può chiamare `window.PrestaMindAI.setConsent(true)` dopo l'accettazione del visitatore. Il modulo non fornisce un banner.

## 7. Aiuto

Pagina del modulo: [https://mypresta.eu/ai-artificial-intelligence/prestamind-ai-ai-assistant-live-chat-and-chatbot.html](https://mypresta.eu/ai-artificial-intelligence/prestamind-ai-ai-assistant-live-chat-and-chatbot.html)

Per scrivere a proposito di questo modulo, acceda al Suo account cliente su mypresta.eu, apra il modulo di contatto e scelga l'argomento **Support for paid modules**. Il modulo indica che l'accesso è richiesto per i moduli a pagamento. Dopo l'accesso, scelga questo modulo nella cronologia degli acquisti.
