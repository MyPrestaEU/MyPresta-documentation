---
title: "AI Translations with Grok - documentazione e manuale utente"
description: "Guida alla configurazione e alla risoluzione dei problemi per i negozi che usano già AI Translations with Grok."
sidebar:
  label: "AI Translations with Grok - documentazione e manuale utente"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo AI Translations with Grok su MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-grok.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ai-artificial-intelligence/ai-translations-with-grok/)
>
> ---


## 1. Requisiti

Il modulo funziona su PrestaShop 1.7.0.0 e versioni successive, comprese PrestaShop 8 e 9.

- **PrestaShop:** 1.7.0.0 o successivo.
- **PHP:** 5.6 o successivo.
- **Estensioni PHP:** cURL, OpenSSL, SimpleXML e mbstring.
- **Altri moduli:** non ne richiede nessuno.
- **Fuori dal negozio:** un account xAI e una chiave API Grok, da ottenere nella console xAI. Il server del negozio deve poter raggiungere `https://api.x.ai/v1/chat/completions`.
- **Facoltativo:** un'attività nel pianificatore del server che richiami l'indirizzo cron indicato in **Impostazioni**. Senza di essa, i processi vanno avviati a mano da **Lavori**.
- **Cataloghi grandi:** un dominio con migliaia di stringhe comporta molte chiamate API. Un processo viene diviso in parti della dimensione indicata da **Dimensione del lotto (Batch size)**. Prima di avviare, prema **Stima** in **Massivo**, così vede il numero di stringhe e il costo previsto.
- Il negozio deve avere almeno due lingue. Con una sola, il back office mostra **Il negozio richiede almeno due lingue.** e non c'è nulla da tradurre.

## 2. Installazione

1. Apra **Moduli**, poi **Gestore moduli**. Scelga l'opzione per caricare un modulo, carichi il file ZIP e prema **Installa** accanto a **AI Translations with Grok**.
2. Al termine dell'installazione, **AI Translations with Grok** compare nel menu **International**.
3. L'installazione non svuota la cache del negozio. Il modulo la svuota quando salva una traduzione.

Apra poi **AI Translations with Grok**, vada su **Impostazioni** e incolli la sua chiave Grok. Finché non c'è una chiave salvata, ogni pagina del modulo mostra **Manca la chiave API di Grok.** con il link **Apri impostazioni**.

**Disinstallazione.** Nel **Gestore moduli** prema **Disinstalla** e confermi **Eliminare questo modulo e i suoi dati (lavori, glossario, cache)?**

- La voce di menu scompare. Vengono eliminati i processi, il glossario, i modelli di esclusione, la cronologia delle chiamate, la coda di **Revisione**, le copie per l'annullamento, il registro dei costi e le impostazioni del modulo, compresa la chiave API.
- Il testo che il modulo ha già scritto nel negozio resta dov'è: traduzioni del catalogo e file di traduzione dei moduli classici scritti da questo modulo. Resta anche la sua scelta sul controllo degli aggiornamenti.
- Una nuova installazione non ripristina processi, glossario o cronologia eliminati. Imposta i valori predefiniti e crea un nuovo indirizzo cron.

## 3. Configurazione e uso quotidiano

L'intero modulo si trova in un'unica pagina: **International**, poi **AI Translations with Grok**. Le schede sono **Dashboard**, **Manuale**, **Massivo**, **Lavori**, **Revisione**, **Catalogo**, **Glossario**, **Esclusioni**, **Cronologia** e **Impostazioni**. **Aggiornamenti** è in fondo alla barra. **Aiuto** apre il pannello della scheda in cui si trova. La scheda **Aggiornamenti** non ha il pulsante **Aiuto**.

Le immagini di questo manuale provengono dal back office in inglese. I nomi di pulsanti e campi nel testo sono quelli del back office in italiano.

Il lavoro abituale si compone di quattro passaggi.

1. **Connessione.** In **Impostazioni** incolli la chiave, scelga il modello, prema **Testa connessione** e poi **Salva**.
2. **Prova piccola.** In **Manuale** filtri un dominio, spunti alcune stringhe vuote e le traduca. Controlli il risultato prima di lanciare l'intero catalogo.
3. **Processo.** In **Massivo** scelga sezione, lingue e domini, prema **Stima** e poi **Avvia processo**. Apra il processo e prema **Elabora parte** oppure **Elaborazione automatica**, oppure lasci fare all'indirizzo cron.
4. **Verifica.** Apra **Revisione** per le righe trattenute dal controllo qualità e **Cronologia** quando una chiamata fallisce. Il pulsante **Annulla modifiche** del processo ripristina il testo precedente, nei casi in cui il modulo ha conservato una copia.

Il modulo non avvia mai una traduzione da solo. **Stima**, **Filtra** e **Salva** in **Impostazioni** non scrivono testo nel catalogo. Un processo resta in attesa in **Lavori** finché non lo elabora o finché l'indirizzo cron non lo richiama.

### 3.1. Configurazione del modulo

Apra **Moduli**, **Gestore moduli**, trovi **AI Translations with Grok** e prema **Configura**. Si apre la **Dashboard**. Passi a **Impostazioni**.

**Salva** e **Testa connessione** si trovano in fondo al modulo. Salvare questo modulo non avvia alcuna traduzione e non riscrive quelle già salvate.

![Impostazioni, back office in inglese. Parte alta: chiave API, modello, aggiunta modello, tono e locale di origine.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-settings.webp)

**Connessione**

| Campo | Predefinito | Cosa fa |
|---|---|---|
| **Chiave API Grok** | vuoto | La chiave segreta che il negozio invia a Grok. Incolli la chiave dalla console xAI. Un campo vuoto mantiene la chiave già salvata. Un valore nuovo la sostituisce. Un campo vuoto non la cancella. Quando una chiave è salvata, l'aiuto mostra **Chiave salvata:** seguito dalla chiave mascherata. |
| **Modello** | grok-4.7 | Il modello Grok che scrive la traduzione. I modelli integrati restano nell'elenco: grok-4.7, grok-4.6, grok-4.5, grok-4.3, grok-4.20-0309-non-reasoning e grok-4.20-0309-reasoning. I modelli aggiunti da lei si possono rimuovere. La traduzione successiva usa il modello scelto. Se l'account non può usare un modello, la chiamata fallisce e l'errore compare in **Cronologia**. |
| **Aggiungi un modello Grok** | vuoto | Scriva l'identificativo esatto dell'account xAI e prema **Aggiungi modello**. L'esempio è grok-4.7. Il nuovo identificativo compare in **Modello** e diventa il modello attivo. **Rimuovi** elimina solo gli identificativi aggiunti qui. Quelli integrati non si possono rimuovere. |

Messaggi che può vedere: **Modello aggiunto.**, **Modello rimosso.**, **Quel modello è già nell'elenco. Ora è il modello attivo.**, **Inserisci un id modello, ad esempio grok-4.7.**, **I modelli integrati non possono essere rimossi.**

**Tono e origine**

| Campo | Predefinito | Cosa fa |
|---|---|---|
| **Tono** | Formale | Aggiunge a ogni prompt un'istruzione di stile. **Formale** è adatto ai testi del negozio e del back office, **Informale** suona più leggero, **Brand** si usa insieme a **Voce del brand**. Le nuove traduzioni seguono lo stile scelto. Quelle già salvate restano invariate finché non le rilancia. |
| **Voce del brand** | vuoto | Compare solo quando **Tono** è su **Brand**. Alcune frasi semplici su come deve suonare il negozio, oppure un campo vuoto. Il testo viene inserito nel prompt successivo. Se il campo è vuoto, non si aggiunge alcuna voce. Non riscrive le traduzioni esistenti. |
| **Locale di origine** | vuoto | La lingua che il modello considera l'originale. La scelta vuota corrisponde al trattino dell'elenco: in quel caso l'origine è la schermata che sta traducendo. Di solito sceglie la locale in cui sono scritti i cataloghi, tipicamente en-US. **Manuale**, **Massivo** e le icone di **International → Translations** inviano questa locale come origine. La lingua predefinita del negozio non cambia. |
| **Pulsanti per singolo campo — moduli del negozio** | Sì | Un pulsante accanto a ogni campo multilingua dei moduli del negozio: prodotto, categoria, CMS e altri moduli del back office. Il pulsante traduce solo quel campo. **No** nasconde questi pulsanti in tutto il negozio. Le traduzioni salvate non cambiano. |
| **Caselle di spunta per singolo campo — moduli del negozio** | Sì | Ogni campo di questo tipo riceve una casella, e la barra traduce solo i campi spuntati. **No** nasconde le caselle e la barra. I pulsanti sopra hanno un interruttore a parte. |
| **Pulsanti per singolo campo — International → Translations** | Sì | Un pulsante su ogni campo di **International → Translations**. **No** nasconde questi pulsanti. I moduli del negozio restano invariati. Un clic compila quel campo. Il pulsante **Salva** di PrestaShop salva comunque la pagina. |
| **Caselle di spunta per singolo campo — International → Translations** | Sì | Caselle e barra su **International → Translations**. **No** le nasconde. I moduli del negozio restano invariati. |

**Limiti**

![Impostazioni, back office in inglese. Dimensione del lotto e i campi dei limiti sotto.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-settings-limits.webp)

| Campo | Predefinito | Cosa fa |
|---|---|---|
| **Dimensione del lotto** | 25 | Quante stringhe vanno in una singola chiamata API. Per la prima prova usi tra 10 e 25. Il valore deve restare tra 1 e 100. Un lotto più grande chiude il processo con meno chiamate, ma se fallisce viene ripetuto un blocco più grande. |
| **Campione di prova (Dry-run)** | 10 | Quante stringhe di esempio mostra **Stima** prima di un processo massivo. Il valore deve restare tra 1 e 50. **Stima** elenca quelle stringhe d'origine e una stima del costo. Non salva alcuna traduzione. |
| **Token massimi (0 = predefinito)** | 0 | Limita la lunghezza di una singola risposta. Lasci 0 per usare la lunghezza predefinita di Grok. Scriva un numero se le risposte vengono troncate o se le vuole più corte. Il limite vale solo per la chiamata successiva e non accorcia le traduzioni già salvate. |
| **Budget USD / mese** | 0 | Tetto mensile in dollari, calcolato dal registro d'uso. 0 significa nessun tetto. Scriva l'importo che vuole consentire a partire dal primo giorno del mese. Quando il registro raggiunge quella cifra, le nuove traduzioni si fermano e la schermata mostra **Monthly API budget has been exhausted.** Il lavoro già salvato resta. |
| **Limite di frequenza / min** | 60 | Quante chiamate API può avviare questo negozio in un minuto. 60 è un valore prudente di partenza. 0 disattiva questo limite locale. Le chiamate oltre il limite vengono saltate e registrate in **Cronologia**. Grok può applicare un limite proprio. |
| **Giorni di conservazione dei log** | 30 | Per quanti giorni restano le righe in **Cronologia**. Il minimo è 1. Le righe più vecchie vengono eliminate quando si salva una nuova chiamata. Questo valore non elimina processi, glossario né traduzioni salvate. |
| **Temperatura** | 0.2 | Quanta libertà ha il modello nel riformulare una frase. Un valore intorno a 0,2 resta vicino all'originale. I valori più vicini a 1 cambiano di più le frasi. Il valore deve restare tra 0 e 1. Segnaposto e HTML vengono controllati dopo. La traduzione successiva usa questo valore. |
| **Consenti pubblicazione / salvataggio** | Sì | Stabilisce se il modulo può scrivere una traduzione in PrestaShop. **No** blocca il salvataggio da **Manuale**, dai processi massivi e da **Catalogo**. Le icone nella pagina delle traduzioni e nei moduli del negozio si limitano a compilare il modulo. Il pulsante **Salva** di PrestaShop è separato. |

Dopo aver premuto **Salva** vedrà uno di questi messaggi:

- **Impostazioni salvate. Nessuna traduzione avviata.** Le impostazioni sono salvate e non è stato tradotto nulla.
- **Impostazioni salvate. Nessuna chiave API memorizzata, quindi non è possibile tradurre finché non ne incolli una.** Incolli la chiave in **Chiave API Grok** e prema di nuovo **Salva**.

**Posta e cron**

| Campo | Predefinito | Cosa fa |
|---|---|---|
| **Notifica email al completamento** | No | Invia una email quando un processo massivo termina. Il processo viene eseguito comunque. Cambia solo l'invio della email. |
| **Email di notifica** | vuoto | L'indirizzo che riceve quella email. Il campo compare solo quando l'interruttore sopra è attivo. Se è vuoto, si usa l'email del negozio. Salvare l'indirizzo non invia alcun messaggio. L'oggetto inizia con il nome del modulo, il numero del processo e lo stato. |
| **URL CRON** | indirizzo con token | L'indirizzo segreto con cui il server può elaborare una parte di un processo in attesa. Lo copi nel pianificatore del server e non lo pubblichi. Chi ha l'indirizzo può avviare una parte. Aprire **Impostazioni** non avvia alcun processo. |

**Testa connessione** verifica chiave e modello con una chiamata breve. Non traduce e non salva nulla.

- **Connessione OK (N ms). Nessuna traduzione avviata.** La connessione funziona.
- **Connessione non riuscita. Nessuna traduzione effettuata.** seguito subito dal motivo. Controlli chiave e modello. I dettagli sono in **Cronologia**.

Per iniziare in modo pratico: incolli la chiave, scelga modello e locale di origine, prema **Testa connessione** e poi **Salva**. Lasci i valori numerici a quelli d'installazione finché un processo non si comporta male.

### 3.2. Dashboard

Apra la scheda **Dashboard**. Conta le stringhe di catalogo mancanti e poi mostra l'uso di Grok con schede, grafici e i dieci prompt più recenti. La pagina non traduce e non modifica le stringhe.

![Dashboard, back office in inglese. Copertura di una locale, riga cron e filtri della cronologia.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-dashboard.webp)

**Copertura**

- **Locale:** la locale del negozio di cui si contano le stringhe mancanti.
- **Mostra:** ridisegna la tabella per quella locale.
- Colonne: **Sezione**, **Totale**, **Mancanti**, **Completati** e una barra di avanzamento. Le sezioni sono **Back office**, **Temi**, **Moduli installati**, **Email** e **Altri**. **Mancanti** indica quante stringhe non hanno traduzione in quella locale.
- Sotto la tabella, **CRON** mostra lo stesso indirizzo di **URL CRON** nelle **Impostazioni**.
- Una tabella vuota significa che il negozio non ha ancora un catalogo per quella locale. Lo crei in **International → Translations**.

Dopo **Mostra**, il messaggio è **Copertura per {locale}. Questa pagina conta solo le stringhe. Nessuna traduzione effettuata.**

**Uso**

- Preimpostazioni: **Oggi**, **7 giorni**, **30 giorni**, **Questo mese** e **Sempre**.
- Filtri: **Da**, **A**, **Modello**, **Tipo**, **Stato** (**Qualsiasi**, **Successo**, **Errore**), **Lingua**, **Dipendente** e **Il prompt o la risposta contiene**. Prema **Filtra**.
- Schede: **Richieste**, **Successo**, **Errori**, **Token inviati**, **Token ricevuti**, **Token totali**, **Tempo medio** e **Costo stimato**. Il costo stimato è un calcolo locale, non una fattura di xAI. Un trattino indica che Grok non ha restituito il numero di token per quella chiamata.
- Grafici: **Richieste ed errori**, **Token inviati e ricevuti**, **Richieste per modello**. Sotto ci sono i gruppi **Per giorno**, **Per modello**, **Per tipo**, **Per lingua** e **Per dipendente**, con le colonne **Gruppo**, **Chiamate**, **Inviati**, **Ricevuti** e **Totale**. Un gruppo vuoto mostra **Nessuna richiesta in questo intervallo.**
- **Ultimi prompt** elenca le dieci chiamate più recenti. **Visualizza** apre prompt e risposta. **Vedi tutto** apre la **Cronologia** (sezione 3.10). Se l'elenco è vuoto, compare **Nessuna richiesta ancora.**

Filtrare non cancella la cronologia e non cambia le traduzioni.

Se una sezione è quasi vuota, apra **Manuale** per poche stringhe oppure **Massivo** per un intero dominio.

### 3.3. Manuale

Apra **Manuale**. Serve a tradurre un dominio o un modulo classico, qualche decina di stringhe alla volta. Filtrare non salva nulla.

![Manuale, back office in inglese. Sezione, origine, destinazione, dominio, solo vuoti e cerca.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-manual.webp)

| Campo | Predefinito | Cosa fa |
|---|---|---|
| **Sezione** | Back office | Quale catalogo viene letto: **Back office**, **Temi**, **Moduli installati**, **Email** o **Altri**. Cambiare sezione ricarica la pagina e mostra solo i campi di quella sezione. Non viene chiamato Grok. |
| **Tema** | vuoto | Visibile solo per **Temi**. Limita l'elenco a un tema. |
| **Modulo** | vuoto | Visibile solo per **Moduli installati**. Limita l'elenco a un modulo. Un modulo classico senza dominio carica tutte le stringhe di quel modulo. |
| **Dominio** | vuoto | La stessa suddivisione di **International → Translations**. Lo scelga e prema **Filtra**. Nascosto per i moduli classici e per le sezioni senza domini. La riga vuota mostra un trattino con il testo di scelta. |
| **Origine** | **Locale di origine** di **Impostazioni**, oppure en-US | La lingua da cui vengono prese le stringhe. Scelga una lingua che abbia già un buon testo. |
| **Destinazione** | la prima lingua dell'elenco | La lingua che vuole completare. Deve esistere in **International → Localizzazione → Lingue**. |
| **Solo vuoti** | Sì | Mostra solo le stringhe senza traduzione. Se lo disattiva, compaiono tutte le stringhe. Le traduzioni salvate non vengono eliminate. |
| **Cerca** | vuoto | Mantiene solo le stringhe di origine che contengono la parola digitata. |

Passaggi:

1. Imposti **Sezione**, **Origine** e **Destinazione**.
2. Per **Temi**, scelga un **Tema**. Per **Moduli installati**, scelga un **Modulo**.
3. Prema **Filtra**. L'elenco **Dominio** si aggiorna. Scelga un dominio e prema di nuovo **Filtra**. Per un modulo classico, lasci il dominio vuoto: **Filtra** carica tutte le stringhe del modulo.
4. Spunti le righe desiderate. **Seleziona tutto** e **Deseleziona tutto** spuntano o svuotano l'elenco.
5. Prema **Traduci selezionate (revisione)**. Si apre la tabella **Revisiona prima di salvare**, con le colonne **Origine**, **Proposta IA** e **Avvisi**. Tolga la spunta alle righe che non vuole, corregga la proposta direttamente nel campo e prema **Salva approvate**.
6. In alternativa, spunti **Salva ora (salta la revisione)** prima di tradurre. Le righe valide vengono salvate subito, senza passare dalla tabella di revisione.

Le colonne dell'elenco delle stringhe sono **Origine**, **Corrente** e **Stato** (**vuoto** o **compilato**).

Messaggi che può vedere:

- **Caricate N stringhe. Spunti le righe desiderate, quindi prema Traduci selezionate. Nulla è ancora stato salvato.**
- **Caricate N stringhe dall'intero modulo. Spunti le righe desiderate, quindi prema Traduci selezionate. Nulla è ancora stato salvato.** È l'elenco di un modulo classico.
- **Questo modulo non ha un dominio di traduzione. Prema Filtra per caricare tutte le stringhe del modulo. Nulla è stato inviato a Grok.**
- **Nessuna stringa corrisponde a questo filtro. Nulla è stato inviato a Grok.**
- **Nessuna stringa corrisponde a questo filtro. Disattivi Solo vuoti, oppure questo modulo non ha stringhe classiche. Nulla è stato inviato a Grok.**
- **Nessuna traduzione effettuata. Scelga un dominio, quindi prema Filtra per caricare le stringhe.**
- **Nessuna traduzione effettuata. Scelga un tema, quindi prema Filtra.**
- **Nessuna traduzione effettuata. Scelga un modulo, quindi prema Filtra.**
- **Nessuna traduzione effettuata. Spunti almeno una riga.**
- **Nessuna traduzione effettuata. Manca la chiave API di Grok. Apra Impostazioni e incolli la chiave.**
- **La revisione è pronta. Nulla viene salvato finché non preme Salva approvate.**
- **Salvato. Le stringhe approvate sono state scritte per la lingua di destinazione.**
- **Salvate N. Sono state scritte solo le righe spuntate.**
- **Nulla è stato salvato. Spunti OK sulle righe che vuole conservare.**
- **Non salvato per segnaposto o HTML non validi: N.** Quelle righe sono state saltate. Allinei segnaposto e tag all'originale e salvi di nuovo.
- **Nulla è stato salvato. Attivi Consenti pubblicazione nelle Impostazioni.**
- **Nessuna traduzione effettuata. Queste righe non sono nell'elenco attuale. Prema Filtra e spuntale di nuovo.**

Cambiare sezione mostra anche una riga breve, per esempio **La sezione è Back office. Tema e modulo non vengono usati.**, insieme a **Nulla è stato inviato a Grok.** Lo stesso schema vale per **Temi**, **Moduli installati**, **Email** e **Altri**.

### 3.4. Massivo

Apra **Massivo**. Crea un unico processo per molti domini e lingue. **Stima** non salva nulla. **Avvia processo** aggiunge una riga in **Lavori**. Non viene scritto nulla finché il processo non viene elaborato e **Consenti pubblicazione / salvataggio** non è attivo.

![Massivo, back office in inglese. Sezione, origine, destinazioni, domini, politica e processo di prova.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-bulk.webp)

| Campo | Predefinito | Cosa fa |
|---|---|---|
| **Sezione** | Back office | Quale catalogo legge il processo. La pagina si ricarica e mostra **Tema** solo per **Temi**, e **Modulo** solo per **Moduli installati**. Le stringhe fuori dalla sezione scelta non entrano. Cambiare sezione non avvia il processo. |
| **Tema** | vuoto | Solo per **Temi**. Gli altri temi restano esclusi. |
| **Modulo** | vuoto | Solo per **Moduli installati**. Un modulo classico non ha domini: **Stima** e **Avvia processo** coprono tutte le stringhe del modulo. |
| **Origine** | **Locale di origine** di **Impostazioni**, oppure en-US | La locale che il processo considera l'originale. Ogni destinazione viene tradotta da questa locale. |
| **Destinazioni** | nessuna spuntata | Le locali che il processo deve completare. Ne spunti una o più. Un clic senza Ctrl sostituisce la selezione. Il processo conserva un insieme di stringhe per ogni locale spuntata. |
| **Domini** | nessuno spuntato | I domini inclusi nel processo. Tenga premuto Ctrl o Cmd per spuntare più righe. I domini non spuntati restano fuori. Lasci tutto vuoto solo se vuole un processo vuoto. Nascosto per i moduli classici. |
| **Politica** | Riempi i vuoti | **Riempi i vuoti** salta le stringhe che hanno già una traduzione. **Sovrascrivi tutto** invia ogni stringa e sostituisce il lavoro già completato, quando il processo può salvare. **Obsoleto se uguale all'origine** invia le stringhe la cui traduzione è ancora identica all'originale. |
| **Processo di prova (Dry-run)** | No | Chiama il modello, ma non scrive la risposta in PrestaShop. Il processo compare comunque in **Lavori**. I file del catalogo e le traduzioni nel database restano come prima. |

Passaggi:

1. Imposti **Sezione**, **Origine** e **Destinazioni**.
2. Per **Temi**, scelga un **Tema**. Per **Moduli installati**, scelga un **Modulo**.
3. Scelga i **Domini** quando l'elenco è visibile. Tenga premuto Ctrl o Cmd.
4. Prema **Stima**. Controlli il conteggio, la stima dei token, la stima del costo e il **Campione**. Nulla è stato inviato a Grok e nulla è stato salvato. Messaggio: **Solo stima: N stringhe, ~N token, ~$N. Nulla è stato inviato a Grok né salvato.**
5. Prema **Avvia processo**. Il modulo apre quel processo. Messaggio: **Processo n. N in attesa (N stringhe, stima $N). Non è ancora stato eseguito.**

Se manca una scelta obbligatoria, vedrà uno di questi messaggi:

- **Nulla è stato avviato. Selezioni almeno una lingua di destinazione.**
- **Nulla è stato avviato. Scelga un tema.**
- **Nulla è stato avviato. Scelga un modulo.**
- **Nulla è stato avviato. Manca la chiave API di Grok. Apra Impostazioni e incolli la chiave. Non è stato creato alcun processo.**

### 3.5. Lavori

Apra **Lavori**. L'elenco mostra ogni processo. Se è vuoto, compare **Nessun lavoro ancora.**

![Lavori, back office in inglese. L'elenco dei processi con stato, lingue, avanzamento, costo, dipendente e data.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-jobs.webp)

Colonne: **#**, **Stato**, **Lingue**, **Avanzamento**, **Costo**, **Dipendente**, **Data** e **Apri**.

Gli stati di questa schermata restano in inglese: **pending**, **running**, **paused**, **cancelled**, **completed**, **completed_with_errors** e **failed**.

Prema **Apri** su una riga. Il dettaglio mostra lo **Stato**, l'avanzamento come completati/totale, i **falliti**, i **saltati**, il costo, il numero del dipendente e **simulazione (dry-run)** se quell'interruttore era attivo. Sotto c'è una barra di avanzamento.

Pulsanti del processo aperto:

- **Elabora parte** traduce un lotto e si ferma. Messaggio: **È stata elaborata una parte. Controlli le righe sotto per vedere cosa è stato salvato, saltato o fallito.** Quando non resta nulla, vede: **Il processo non ha più stringhe in attesa.**
- **Elaborazione automatica** richiede la parte successiva finché il processo non termina o non si ferma.
- **Pausa** ferma le parti successive. Messaggio: **Processo in pausa. Non tradurrà altre stringhe finché non lo riprende.**
- **Riprendi** rimette in attesa un processo in pausa. Messaggio: **Il processo è di nuovo in attesa. Non si esegue da solo. Prema Elabora parte, Elaborazione automatica oppure lasci che il cron lo richiami.**
- **Riprova i falliti** rimette in coda le righe fallite. Messaggio: **Riprovati N elementi falliti.**
- **Annulla modifiche** chiede **Annullare questo processo?** e ripristina il testo precedente dove il modulo ha conservato una copia. Messaggio: **Ripristino: ripristinate N traduzioni.**
- **CSV errori** scarica le righe fallite.
- **Solo falliti** mostra soltanto le righe con stato **failed**.
- **Coda di revisione** apre **Revisione**.

In questa schermata non c'è un pulsante per annullare il processo. Se non vuole che un processo arrivi a termine, può lasciarlo in **paused**.

Le colonne della tabella delle righe sono **ID**, **Dominio**, **Locale**, **Stato**, **Origine**, **Nuovo** ed **Errore**. Anche gli stati delle singole voci restano in inglese: **pending**, **processing**, **done**, **failed**, **skipped** e **rolled_back**.

Se il negozio raggiunge il proprio limite al minuto durante una parte, il processo va in pausa e la riga di errore resta in inglese: **Rate limit — job auto-paused. Resume later.** Più tardi prema **Riprendi**, poi **Elabora parte**.

Un processo di prova chiama Grok e salva la proposta sul processo. Non scrive nel catalogo.

### 3.6. Revisione

Apra **Revisione**. È la coda delle traduzioni dei processi massivi da controllare. La pagina dice **Coda da rivedere (punteggio di qualità / segnalazioni).** Se la coda è vuota, compare **La coda è vuota.**

![Revisione, back office in inglese. La coda da rivedere.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-review.webp)

Colonne: **ID**, **Punteggio**, **Dominio**, **Origine**, **IA**, **Segnalazioni**, **Approva** e **Rifiuta**.

Una riga finisce qui quando il controllo qualità le assegna un punteggio inferiore a 70, quando segnaposto o HTML non coincidono, o quando la traduzione è molto più lunga dell'originale. Se il processo poteva pubblicare e la stringa ha superato la validazione, il catalogo potrebbe già contenere la proposta. **Approva** e **Rifiuta** modificano solo questa coda. Non scrivono una nuova traduzione e non ripristinano quella precedente. Dopo uno dei due pulsanti compare **Revisione aggiornata.** e la riga esce dalla coda.

La tabella di revisione in **Manuale** è un'altra schermata e lì c'è il pulsante **Salva approvate**.

### 3.7. Catalogo

Apra **Catalogo**. Serve a tradurre i campi di prodotti, categorie o pagine CMS. Non è lo stesso catalogo di **International → Translations**. Ogni pressione elabora al massimo 100 record.

![Catalogo, back office in inglese. Entità, campi, lingua di origine, lingua di destinazione, solo vuoti e inizia dopo l'ID.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-catalog.webp)

| Campo | Predefinito | Cosa fa |
|---|---|---|
| **Entità** | product | Quali record vengono letti: **product**, **category** o **cms**. Queste tre parole restano in inglese. La pagina si ricarica e mostra solo l'elenco dei campi di quel tipo. Cambiare entità non traduce nulla. Messaggio: **Visualizzazione dei campi per {entità}. Nulla è stato tradotto.** |
| **Campi** | tutti i campi dell'entità | I testi che il lotto invia. Tenga premuto Ctrl o Cmd per sceglierne più d'uno. **Titolo** è il nome del prodotto, il nome della categoria o il titolo della pagina CMS. **Contenuto** è il corpo della pagina CMS. Se i link devono restare com'è, escluda **URL semplificato**. Vengono tradotti solo i campi selezionati. |
| **Lingua di origine** | l'elenco delle lingue del negozio | La lingua da cui vengono copiati i campi. La lingua di origine stessa non viene modificata. |
| **Lingua di destinazione** | l'elenco delle lingue del negozio | La lingua che riceve la traduzione. Deve essere diversa dall'origine. Vengono scritti fino a 100 record. |
| **Solo vuoti** | Sì | Salta i campi che nella lingua di destinazione hanno già del testo. **No** consente di sostituire quel testo quando la pubblicazione è permessa. |
| **Inizia dopo l'ID** | 0 | Salta i record fino a questo ID. Lasci 0 per partire dal primo. Dopo un lotto il campo mostra l'ultimo ID letto. Prema di nuovo il pulsante per proseguire. |

Campi del prodotto: **Titolo**, **Descrizione breve**, **Descrizione**, **Meta titolo**, **Meta descrizione** e **URL semplificato**.

Campi della categoria: **Titolo**, **Descrizione**, **Meta titolo**, **Meta descrizione** e **URL semplificato**.

Campi CMS: **Titolo**, **Meta descrizione**, **Meta parole chiave**, **Contenuto** e **URL semplificato**.

Prema **Traduci lotto (max 100)**. Il messaggio è **Catalogo completato: salvati N, falliti N.** Sotto il modulo compaiono anche i contatori **Salvato** e **fallito**.

- **Nulla è stato tradotto. Manca la chiave API di Grok. Apra Impostazioni e incolli la chiave.**
- **Nulla è stato salvato. Attivi Consenti pubblicazione nelle Impostazioni.**
- **Nessuna traduzione effettuata. Le lingue di origine e di destinazione devono essere diverse.**
- **Nessuna traduzione effettuata. Selezioni almeno un campo.**

### 3.8. Glossario

Apra **Glossario**. L'elenco conserva le parole che il modello deve mantenere o rendere in modo fisso. Aggiungere un termine non riscrive le traduzioni già salvate, ma la traduzione successiva userà l'elenco.

![Glossario, back office in inglese. Aggiunta di un termine e il modulo CSV.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-glossary.webp)

| Campo | Predefinito | Cosa fa |
|---|---|---|
| **Termine di origine** | vuoto | Il modo in cui il termine compare nella lingua di origine. Scriva la parola o la frase esatta, con le maiuscole se contano. Obbligatorio. |
| **Locale di destinazione** | vuoto | Limita questa riga a una sola locale di destinazione, per esempio it-IT. Se è vuoto, la riga vale per ogni destinazione. Una locale compilata viene ignorata per le altre lingue. |
| **Termine di destinazione** | vuoto | Il modo in cui il termine deve comparire nella traduzione. Lo lasci vuoto solo quando **Non tradurre** è attivo. |
| **Non tradurre** | No | **Sì** dice al modello di copiare il termine di origine senza modifiche. Lo usi per nomi di marchi, SKU e segnaposto. **No** significa che il **Termine di destinazione** è la traduzione che vuole. |

Prema **Aggiungi**.

- **Termine del glossario aggiunto. Le traduzioni già salvate non sono state modificate.**
- **Nulla è stato aggiunto. Scriva un termine di origine.**

Le colonne della tabella sono **Origine**, **Locale**, **Destinazione**, **Non tradurre** (**Sì** o **No**) ed **Elimina**. Se la tabella è vuota, compare **Nessun termine nel glossario ancora.** **Elimina** rimuove la riga. Messaggio: **Termine del glossario eliminato.**

**CSV del glossario**

| Campo | Predefinito | Cosa fa |
|---|---|---|
| **File CSV** | vuoto | Il file deve avere le colonne source_term, target_locale, target_term e do_not_translate. **Importa CSV** aggiunge le righe leggibili. **Esporta CSV** scarica l'elenco attuale e ignora il campo del file. L'esportazione non modifica il glossario. |

- **Importate N righe.**
- **Il file CSV manca.** Scelga un file e prema di nuovo **Importa CSV**.
- **Impossibile aprire il file CSV.** Salvi il file in formato CSV e riprovi.

### 3.9. Esclusioni

Apra **Esclusioni**. L'elenco contiene le stringhe di origine che il modulo deve saltare. Una stringa che corrisponde non viene inviata a Grok e non viene cancellata da PrestaShop. Salvare un modello non modifica le stringhe già salvate.

![Esclusioni, back office in inglese. Modello, tipo e la tabella dei modelli.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-excludes.webp)

| Campo | Predefinito | Cosa fa |
|---|---|---|
| **Modello** | vuoto | Il testo confrontato con ogni stringa di origine. Obbligatorio. |
| **Tipo** | exact | **exact** corrisponde all'intera stringa, **prefix** all'inizio, **contains** a un frammento, e **regex** è un'espressione regolare PHP applicata esattamente come scritta. Provi prima con un modello breve. Un tipo sbagliato può escludere troppo o nulla. |

Prema **Aggiungi**.

- **Modello di esclusione aggiunto. Le stringhe corrispondenti verranno saltate alla prossima esecuzione. Per ora non è stato tradotto nulla.**
- **Nulla è stato aggiunto. Scriva un modello.**

Le colonne della tabella sono **Modello**, **Tipo**, **Attivo** ed **Elimina**. **Attivo** mostra 1 quando il modello è in uso. Se la tabella è vuota, compare **Nessun modello ancora.** **Elimina** rimuove la riga. Messaggio: **Modello eliminato.**

### 3.10. Cronologia

Apra **Cronologia**. È l'elenco completo delle chiamate a Grok, inclusi i test di connessione e le chiamate bloccate prima dell'invio. I grafici e i dieci prompt più recenti si trovano nella **Dashboard**, dove **Vedi tutto** apre questa scheda.

![Cronologia, back office in inglese. L'elenco delle chiamate e cancella cronologia.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-history.webp)

Colonne: **ID**, **Quando**, **Stato**, **Tipo**, **Modello**, **Lingue**, **Inviati**, **Ricevuti**, **Totale**, **Tempo**, **Prompt** e **Visualizza**.

**Tipo** è uno tra **Manuale**, **Pagina di traduzione**, **Processo massivo**, **Catalogo**, **Test di connessione**, **Traduci** o **Non inviato**. **Stato** è **Successo** o **Errore**.

**Visualizza** apre il prompt e la **Risposta**, insieme a **HTTP**, **Inviati**, **Ricevuti** e **Totale**. **Torna all'elenco** riporta alla tabella. Se la riga è stata eliminata, la pagina mostra **Questa riga della cronologia non esiste più.** Se il dettaglio non può essere caricato, la pagina mostra **Impossibile caricare questa richiesta.**

**Precedente** e **Successiva** cambiano pagina. La riga indica **Pagina N / N**.

**Cancella cronologia** chiede **Cancellare la cronologia salvata? Le traduzioni salvate restano.** Confermando, vengono cancellate solo queste righe. Messaggio: **Cronologia cancellata. Le traduzioni salvate non sono state modificate.** Se l'elenco è vuoto, compare **Nessuna richiesta ancora.**

I **Giorni di conservazione dei log** nelle **Impostazioni** eliminano anche le righe più vecchie di quel numero di giorni quando viene salvata una nuova chiamata.

### 3.11. Aggiornamenti

Apra **Aggiornamenti**. Questa pagina controlla se è disponibile un pacchetto più recente. Non traduce nulla.

![Aggiornamenti, back office in inglese. Controllo manuale, notifiche automatiche e pagina prodotto.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-updates.webp)

| Campo | Predefinito | Cosa fa |
|---|---|---|
| **Controllo manuale** | il pulsante **Controlla ora** | Interroga l'editore una volta. **Il modulo è aggiornato!** significa che questa installazione corrisponde al pacchetto attuale. **Nuova versione disponibile!** significa che è stato pubblicato un pacchetto più recente. Lo scarichi dalla pagina del prodotto e lo installi dal **Gestore moduli**. |
| **Notifiche automatiche** | Attive | **Attive** permette al back office di mostrare un avviso quando esiste un pacchetto più recente. **Disattive** spegne quell'avviso. Prema **Salva** per conservare la scelta. Disinstallare il modulo non cancella questa scelta. |
| **Pagina prodotto** | un link con il nome del modulo | Apre la pagina del modulo. L'indirizzo è nella sezione 7. |

Quando esiste un pacchetto più recente, il back office può anche mostrare **Nuova versione disponibile, consulti MyPresta.eu per maggiori informazioni** con il link **Maggiori dettagli nel changelog**.

### 3.12. Pulsanti su International → Translations

Apra **International**, poi **Translations**, e apra un catalogo. Quando **Pulsanti per singolo campo — International → Translations** è **Sì**, ogni campo ha un pulsante **Traduci**. Un clic compila quel campo. Il pulsante **Salva** di PrestaShop salva comunque la pagina.

Quando **Caselle di spunta per singolo campo — International → Translations** è **Sì**, la pagina mostra anche una barra **Traduzioni Grok**.

- **Origine** viene dalla **Locale di origine** nelle **Impostazioni**. Se quell'impostazione è vuota, la barra usa en-US. Il campo si può modificare.
- **Destinazione** è la lingua del catalogo aperto.
- **Seleziona tutto**, **Deseleziona tutto** e **Seleziona vuoti** cambiano le spunte.
- **Traduci vuoti** compila i campi vuoti. **Traduci selezionati** compila i campi spuntati.
- Il suggerimento è **Compila i campi. Salva con il pulsante di PrestaShop.**
- Durante il lavoro la barra mostra **Traduzione in corso…**. Alla fine mostra **Fatto**.
- **Selezionati** indica quanti campi sono spuntati.
- **Spunti almeno un campo.** compare quando premi **Traduci selezionati** senza aver spuntato nulla.
- **Compili prima il campo della lingua di origine.** compare quando il testo di origine è vuoto.
- **Il file email della lingua di origine non è stato trovato.** compare su una schermata email quando manca il file di origine.
- **Traduci i vuoti in questa sezione** compila le stringhe vuote della sezione che sta guardando.

Questi pulsanti non sostituiscono **Salva** nella pagina di PrestaShop. **Consenti pubblicazione / salvataggio** non li blocca, perché si limitano a compilare il modulo.

### 3.13. Pulsanti sui moduli di prodotto, categoria e CMS

Apra un prodotto, una categoria, una pagina CMS o un altro modulo del back office che abbia un campo per lingua. Quando **Pulsanti per singolo campo — moduli del negozio** è **Sì**, ognuno di questi campi ha il pulsante **Traduci**. Un clic compila quel campo partendo dalla lingua di origine dello stesso modulo.

![Modulo prodotto, back office in inglese. La barra Traduzioni Grok sotto i campi descrizione.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-product.webp)

Quando **Caselle di spunta per singolo campo — moduli del negozio** è **Sì**, il modulo mostra anche la barra **Traduzioni Grok**.

- **Origine** parte dalla **Locale di origine**, oppure da en-US se quell'impostazione è vuota.
- **Destinazione** elenca le altre lingue del negozio, più **tutte le altre lingue**.
- **Seleziona tutto**, **Deseleziona tutto**, **Seleziona vuoti**, **Traduci vuoti** e **Traduci selezionati** funzionano come nella pagina delle traduzioni.
- Il suggerimento è **Compila i campi. Salva con il pulsante di PrestaShop.**
- **Spunti almeno un campo.**, **Compili prima il campo della lingua di origine.** e **Il campo della lingua di origine non è presente in questa pagina.** indicano cosa correggere.
- **La destinazione non è una lingua di questo negozio.** significa che la destinazione non corrisponde a nessuna lingua del negozio.
- La riga sopra un campo può dire **Traduci da** il nome dell'origine **a** il nome della destinazione.

Prema **Salva** di PrestaShop su quel modulo per conservare i campi compilati. La barra non salva il prodotto da sola.

## 4. Negozio

Il tema del negozio non mostra questo modulo. Il cliente non vede alcun pulsante di traduzione, né un modulo o una pagina di stato.

L'unico indirizzo fuori dal back office è l'**URL CRON** in **Impostazioni**, ripetuto sotto la tabella di copertura nella **Dashboard**. Copi quell'indirizzo nel pianificatore del server. Ogni chiamata elabora una parte del primo processo in attesa o in corso e poi si ferma. Aprire **Impostazioni** non la richiama.

| Cosa vede | Cosa fare |
|---|---|
| Una riga JSON con il risultato della parte | La parte è stata eseguita. Apra **Lavori** e legga le righe. |
| **No pending jobs** | Non c'è un processo in attesa. Ne crei uno in **Massivo**, oppure il precedente è già terminato, in pausa o annullato. Questo testo resta in inglese. |
| **Forbidden** | L'indirizzo è sbagliato, oppure il token è stato sostituito da una nuova installazione. Copi di nuovo l'**URL CRON**. Non pubblichi l'indirizzo. Questo testo resta in inglese. |

Non aggiunga parametri propri. L'indirizzo che copia è esattamente quello che il modulo legge.

## 5. Problemi

**Manca la chiave API di Grok.** e **Apri impostazioni** compaiono su ogni scheda. Incolli la chiave in **Impostazioni**, prema **Testa connessione** e poi **Salva**.

**Il negozio richiede almeno due lingue.** Aggiunga una lingua in **International → Localizzazione → Lingue**, poi riapra il modulo.

**Connessione non riuscita. Nessuna traduzione effettuata.** Il motivo segue subito dopo questa frase. Controlli chiave, modello e che il server raggiunga l'indirizzo di Grok. Apra **Cronologia** e prema **Visualizza** sulla riga di errore.

**Monthly API budget has been exhausted.** Questo messaggio resta in inglese. Alzi **Budget USD / mese**, oppure lo imposti a 0 se non deve esserci un tetto, e prema **Salva**. Il testo già salvato resta.

**Grok rate limit (429). Try again later.** Questo messaggio resta in inglese. Attenda e rilanci la parte. Se il processo mostra **Rate limit — job auto-paused. Resume later.**, prema **Riprendi**, poi **Elabora parte**. Se si ripete, abbassi la **Dimensione del lotto** o allunghi la pausa tra le chiamate cron. **Limite di frequenza / min** è il tetto di questo negozio, e Grok può comunque rifiutare una chiamata.

**Nulla è stato salvato. Attivi Consenti pubblicazione nelle Impostazioni.** Imposti **Consenti pubblicazione / salvataggio** su **Sì**, prema **Salva** e poi salvi di nuovo. Le icone nei moduli continuano a compilare solo il modulo.

**Non salvato per segnaposto o HTML non validi: N.** La proposta ha modificato un segnaposto o un tag. Allinei la proposta all'originale, oppure lasci quella riga senza spunta e prema di nuovo **Salva approvate**.

**Nessuna traduzione effettuata. Scelga un tema, quindi prema Filtra.** oppure **Scelga un modulo.** La sezione ha bisogno di questa scelta prima che l'elenco possa caricarsi.

**Nessuna stringa corrisponde a questo filtro. Nulla è stato inviato a Grok.** Disattivi **Solo vuoti**, svuoti **Cerca** oppure scelga un altro dominio.

**Il file CSV manca.** oppure **Impossibile aprire il file CSV.** Scelga un CSV con le quattro colonne e prema di nuovo **Importa CSV**.

**Il file email della lingua di origine non è stato trovato.** In **International → Translations** apra la sezione email di una lingua che ha già il file, oppure generi prima le traduzioni delle email in PrestaShop.

**Questa riga della cronologia non esiste più.** La riga è stata cancellata o rimossa da **Giorni di conservazione dei log**. La traduzione salvata è ancora nel negozio.

Manca la voce di menu, oppure il back office dice che il controller non è stato trovato. Apra il **Gestore moduli**, trovi **AI Translations with Grok** e prema **Configura**. Così si ricrea la voce del menu **International**. Se il modulo non compare affatto nell'elenco, installi di nuovo lo ZIP.

L'installazione si blocca con **Impossibile creare le tabelle del modulo.** L'utente del database non può creare tabelle. Corregga i permessi del database e prema di nuovo **Installa**. **Impossibile aggiungere la scheda del menu.** significa che la voce di menu non è stata creata. Dopo un'installazione riuscita prema **Configura**, oppure installi di nuovo.

## 6. Per gli sviluppatori

### 6.1. Panoramica

Nome tecnico `myaitranslationsgrok`, versione `1.2.0`, autore MyPresta.eu, scheda del modulo `administration`. Il nome nell'elenco dei moduli e l'etichetta nel menu **International** sono **AI Translations with Grok**. La classe è `myaitranslationsgrok`. Il minimo di `ps_versions_compliancy` è `1.7.0.0`.

`getContent()` chiama `ensureTab()` e reindirizza a `AdminMyaitranslationsgrok`. Le impostazioni vengono lette da `MyaitgkConfigService` (chiavi `MYAITGK_*`). La chiave API è cifrata e salvata in `MYAITGK_API_KEY_ENC`. Le chiamate di traduzione passano da `MyaitgkTranslateService` fino a `MyaitgkGrokTranslationProvider`, che invia un JSON in POST a `https://api.x.ai/v1/chat/completions`. Le scritture nel catalogo passano da `MyaitgkTranslationAdapter`. Le scritture di prodotti, categorie e CMS passano da `MyaitgkCatalogTranslateService`. Dopo il salvataggio di una traduzione di catalogo viene chiamato `Tools::clearCache()`.

Il modulo non definisce `enable()` né `disable()`. Disattivarlo nel **Gestore moduli** non esegue alcuna pulizia aggiuntiva. A rimuovere la scheda di menu, le tabelle e le chiavi `MYAITGK_*` è la disinstallazione.

### 6.2. File

- `myaitranslationsgrok.php` - installazione, disinstallazione, hook, scheda e configurazione dei pulsanti di campo.
- `controllers/admin/AdminMyaitranslationsgrokController.php` - ogni scheda del back office e le azioni AJAX.
- `controllers/front/cron.php` - elabora una parte di processo per l'indirizzo cron.
- `lib/updateChecker.php` - la scheda **Aggiornamenti** e il controllo della versione.
- `sql/install.php`, `sql/uninstall.php` - creano ed eliminano le tabelle.
- `src/Admin/MyaitgkForms.php` - campi HelperForm e testi `desc`.
- `src/Admin/MyaitgkSectionHelp.php` - il pannello **Aiuto**.
- `src/Service/MyaitgkConfigService.php` - chiavi, elenco dei modelli, token cron.
- `src/Service/MyaitgkTranslateService.php` - budget, limite, glossario, esclusioni e salvataggio.
- `src/Service/MyaitgkBulkJobFactory.php` - crea un processo da **Massivo**.
- `src/Service/MyaitgkCatalogTranslateService.php` - lotti di prodotto, categoria e CMS.
- `src/Service/MyaitgkDashboardService.php` - conteggi di copertura.
- `src/Service/MyaitgkRateLimiter.php` - limite al minuto salvato in `var/rate_limit.json`.
- `src/Provider/MyaitgkGrokTranslationProvider.php` - la richiesta verso xAI.
- `src/Provider/MyaitgkPromptBuilder.php` - prompt di sistema e utente.
- `src/Job/MyaitgkJobWorker.php` - parte, nuovo tentativo ed email di fine processo.
- `src/Job/MyaitgkJobRepository.php`, `src/Job/MyaitgkJobStatuses.php` - righe dei processi e costanti di stato.
- `src/Quality/MyaitgkPlaceholderValidator.php`, `MyaitgkHtmlValidator.php`, `MyaitgkPsNativeValidator.php`, `MyaitgkEmailHtmlPipeline.php`, `MyaitgkQualityScorer.php` - controlli prima del salvataggio.
- `src/Glossary/MyaitgkGlossaryRepository.php`, `MyaitgkExcludePatternRepository.php` - glossario ed esclusioni.
- `src/Audit/MyaitgkRequestLogRepository.php` - **Cronologia** e il report della dashboard.
- `src/Audit/MyaitgkSnapshotService.php` - copie per l'annullamento.
- `src/Security/MyaitgkApiKeyEncryptor.php` - cifratura OpenSSL della chiave.
- `src/Adapter/MyaitgkTranslationAdapter.php`, `MyaitgkLegacyModuleCatalogue.php` - cataloghi PrestaShop e moduli classici `translations/{iso}.php`.
- `views/templates/admin/configure.tpl` e `views/templates/admin/_partials/*.tpl` - le schede.
- `views/js/admin.js`, `admin-help.js`, `history-charts.js`, `translations-tool.js`, `entity-fields.js`, `chart.min.js`.
- `views/css/admin.css`.
- `translations/{iso}.php` - testi del back office.

### 6.3. Controller

`AdminMyaitranslationsgrok` estende `ModuleAdminController`. La classe padre della scheda è `AdminInternational` (in alternativa `IMPROVE`). Il parametro della query è `myaitgk_tab` e accetta i valori `dashboard`, `manual`, `bulk`, `jobs`, `review`, `catalog`, `glossary`, `excludes`, `logs`, `settings` e `updates`. I valori sconosciuti tornano a `dashboard`.

Le azioni visibili sono i pulsanti di invio descritti nel capitolo 3. Altri endpoint di amministrazione usati dagli script della pagina: `ajax=1&action=HistoryDetail` per **Visualizza**, il polling dello stato del processo per **Elaborazione automatica** e le azioni di traduzione dei campi usate da `translations-tool.js` e `entity-fields.js`.

`MyaitranslationsgrokCronModuleFrontController` (`controllers/front/cron.php`) legge il parametro `token`. Un token mancante o errato restituisce HTTP 403 con `{"ok":false,"error":"Forbidden"}`. Un token corretto senza `id_job` elabora una parte del primo processo in stato `pending` o `running`. Con `id_job` viene elaborato quel processo specifico. Se non c'è nulla in attesa, il corpo della risposta è `{"ok":true,"message":"No pending jobs"}`.

`job_action` nella scheda dei lavori accetta `process`, `pause`, `resume`, `cancel`, `retry_failed`, `rollback` ed `export_errors`. Il template mostra tutte le azioni tranne `cancel`.

### 6.4. Hook

Registrati in `install()`:

- `displayBackOfficeHeader` - corregge l'etichetta tecnica della scheda e carica le risorse del back office.
- `actionAdminControllerSetMedia` - carica le stesse risorse.

Su `AdminMyaitranslationsgrok` il modulo aggiunge `views/css/admin.css`, `views/js/admin.js` e `views/js/admin-help.js`. La **Dashboard** aggiunge anche `chart.min.js` e `history-charts.js`. In **International → Translations** aggiunge `translations-tool.js` quando gli interruttori di quella pagina sono attivi. Sugli altri moduli del back office aggiunge `entity-fields.js` quando sono attivi gli interruttori dei moduli del negozio. Entrambi passano l'oggetto `myaitgkTr` a JavaScript.

Il modulo non registra alcun hook lato vetrina e non espone un hook proprio.

### 6.5. Override

Il modulo non sovrascrive alcuna classe o controller di PrestaShop.

### 6.6. Database

La disinstallazione esegue `sql/uninstall.php` ed elimina ogni tabella elencata qui sotto. L'installazione usa `CREATE TABLE IF NOT EXISTS`, quindi una tabella rimasta in piedi viene conservata.

| Tabella | Contenuto |
|---|---|
| `myaitgk_glossary` | `source_term`, `target_locale`, `target_term`, `do_not_translate`, `id_shop`. |
| `myaitgk_exclude_pattern` | `pattern`, `pattern_type` (`exact`, `prefix`, `contains`, `regex`), `enabled`. |
| `myaitgk_job` | Un processo massivo: locali, `scope_json`, `policy_json`, `dry_run`, conteggi, costo, stato e dipendente. |
| `myaitgk_job_item` | Una stringa di un processo: dominio, chiave, tema, locali, origine, testo precedente, testo nuovo, stato e avvisi. |
| `myaitgk_memory` | Traduzione riutilizzata, identificata da `memory_hash`, modello e `hit_count`. |
| `myaitgk_usage_ledger` | Righe giornaliere di token e costo, usate per **Budget USD / mese**. |
| `myaitgk_snapshot` | Il testo precedente a una scrittura del processo, usato da **Annulla modifiche**. |
| `myaitgk_api_log` | Breve contesto dell'errore. La chiave API viene rimossa prima dell'inserimento. |
| `myaitgk_request` | Le righe della **Cronologia**: prompt, risposta, token, modello, stato e durata. Il repository ricrea la tabella se manca. |
| `myaitgk_review` | Righe della coda con `needs_review`, `approved` o `rejected`, più `quality_score` e `flags_json`. |
| `myaitgk_catalog_item` | Righe dei lotti di catalogo: entità, campo, lingue, origine, testo precedente, testo nuovo e stato. |

`var/rate_limit.json` è un file, non una tabella. La disinstallazione non elimina `mypresta_updates`, `update_myaitranslationsgrok` né `updatev_myaitranslationsgrok`.

### 6.7. Chiavi e traduzioni

Prefisso `MYAITGK_`. `installDefaults()` scrive una chiave solo se manca. Valori usati quando la chiave è assente:

| Chiave | Valore se assente |
|---|---|
| `API_KEY_ENC` | vuoto |
| `MODEL` | `grok-4.7` |
| `EXTRA_MODELS` | vuoto |
| `PROVIDER` | `grok` |
| `TONE` | `formal` |
| `CUSTOM_VOICE` | vuoto |
| `BATCH_SIZE` | `25` (salvato tra 1 e 100) |
| `MONTHLY_BUDGET` | `0` |
| `SOURCE_LOCALE` | vuoto |
| `TEMPERATURE` | `0.2` (salvato tra 0 e 1) |
| `DRY_RUN_SAMPLE` | `10` (salvato tra 1 e 50) |
| `RATE_LIMIT_PER_MIN` | `60` |
| `LOG_RETENTION_DAYS` | `30` (salvato almeno 1) |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` |
| `NOTIFY_EMAIL` | vuoto |
| `PERM_ALLOW_PUBLISH` | `1` |
| `ENTITY_FIELD_BUTTONS` | `1` |
| `ENTITY_BULK` | `1` |
| `TR_FIELD_BUTTONS` | `1` |
| `TR_BULK` | `1` |
| `MAX_TOKENS` | `0` (con 0 viene omesso dal corpo della traduzione; con un valore maggiore di 0 viene inviato come `max_tokens`) |
| `CRON_TOKEN` | 32 caratteri esadecimali, rigenerato quando è vuoto |

Il salvataggio di **Impostazioni** forza `PROVIDER` a `grok` e cancella `MYAITGK_DEEPL_API_KEY` e `MYAITGK_CLAUDE_API_KEY`, se esistono ancora da versioni precedenti. Un campo della chiave API vuoto non svuota `API_KEY_ENC`.

Gli identificativi di modello integrati sono `grok-4.7`, `grok-4.6`, `grok-4.5`, `grok-4.3`, `grok-4.20-0309-non-reasoning` e `grok-4.20-0309-reasoning`. Un interruttore assente viene trattato come attivo, quindi i negozi installati prima di quegli interruttori mantengono le icone.

Le descrizioni dei campi sono generate da `MyaitgkForms::help()` nelle sezioni **Cosa fa:**, **Come configurare:** ed **Effetto:**. I pannelli di aiuto sono `MyaitgkSectionHelp`. I testi del back office passano da `$this->l()`. Per aggiungere una lingua, copi `translations/en.php` in `translations/{iso}.php`. Alcuni messaggi sono scritti in inglese direttamente nel PHP e compaiono così: `No Grok API key.`, `Monthly API budget has been exhausted.`, `Grok rate limit (429). Try again later.`, `Rate limit — job auto-paused. Resume later.` e i messaggi JSON del cron.

### 6.8. Estensione

Il tema del negozio non ha un template da sovrascrivere. Il modulo non genera alcun file Smarty per la vetrina. Il markup del back office si trova in `views/templates/admin/`. I pulsanti dei campi vengono iniettati da `views/js/translations-tool.js` e `views/js/entity-fields.js`. Non esiste un hook lato vetrina a cui agganciarsi.

## 7. Aiuto

Pagina del modulo: [AI Translations with Grok](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-grok.html).

Per scrivere a proposito di questo modulo, acceda al Suo account cliente su mypresta.eu, apra il modulo di contatto e scelga l'argomento **Support for paid modules**. Il modulo indica che per i moduli a pagamento è necessario l'accesso. Dopo aver effettuato l'accesso, scelga questo modulo dalla cronologia degli acquisti.
