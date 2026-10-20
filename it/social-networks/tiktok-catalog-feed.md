---
title: "TikTok Catalog Feed - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop TikTok Catalog Feed di MyPresta.eu."
sidebar:
  label: "TikTok Catalog Feed - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo TikTok Catalog Feed su MyPresta.eu](https://mypresta.eu/modules/social-networks/tiktok-catalog-feed.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/tiktok-catalog-feed/)
>
> ---


# TikTok Catalog Feed

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono generalmente sufficienti. Assicurati che il tuo server sia in grado di generare file XML/CSV potenzialmente grandi se hai un catalogo molto esteso.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

Il modulo TikTok Catalog Feed fornisce una sezione dedicata nel tuo Back Office di PrestaShop per la gestione dei tuoi feed di prodotti.

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa schermata di configurazione iniziale ti consente di impostare i parametri di base per il tuo feed TikTok.

- **Abilita Modulo:**

  - **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare la funzionalità del modulo.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il modulo sarà attivo, consentendoti di generare e gestire i feed di prodotti TikTok.
    - *Quando disabilitato:* Il modulo cesserà di funzionare e nessun feed potrà essere generato o accessibile.
  - **Valore consigliato:** SÌ
  - **Scenario / esempio del commerciante:** Lo abiliteresti quando sei pronto per iniziare a usare TikTok Ads. Potresti disabilitarlo temporaneamente se hai bisogno di eseguire manutenzione o interrompere le tue campagne pubblicitarie su TikTok.
- **Tipo di Generazione Feed:**

  - **Cosa fa questa impostazione:** Determina se il modulo genera un file CSV (Comma Separated Values) o XML (Extensible Markup Language) per il tuo feed di prodotti. TikTok generalmente supporta entrambi.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su CSV:* L'URL del feed generato fornirà un file CSV.
    - *Quando impostato su XML:* L'URL del feed generato fornirà un file XML.
  - **Valore consigliato:** XML (spesso preferito per la sua natura strutturata, ma CSV funziona altrettanto bene per TikTok).
  - **Scenario / esempio del commerciante:** Se la documentazione di TikTok o la tua agenzia pubblicitaria raccomanda un formato specifico, scegli quello. Altrimenti, entrambi funzionano.
- **Lingua predefinita per il feed:**

  - **Cosa fa questa impostazione:** Seleziona la lingua principale per i dati del prodotto nel tuo feed. Questo è cruciale per il targeting di mercati specifici su TikTok.
  - **Effetto della modifica di questa impostazione:** I titoli dei prodotti, le descrizioni e altri campi dipendenti dalla lingua nel feed verranno estratti dal tuo negozio PrestaShop nella lingua scelta.
  - **Valore consigliato:** La lingua del tuo pubblico target principale su TikTok (ad esempio, inglese per un mercato statunitense, francese per un mercato francese).
  - **Scenario / esempio del commerciante:** Se stai mirando a clienti in Germania, selezioneresti "Tedesco" qui per assicurarti che le informazioni sui tuoi prodotti siano visualizzate correttamente nella loro lingua su TikTok.
- **Valuta predefinita per il feed:**

  - **Cosa fa questa impostazione:** Seleziona la valuta utilizzata per tutti i prezzi dei prodotti nel tuo feed. Questa dovrebbe corrispondere alla valuta del tuo mercato di riferimento.
  - **Effetto della modifica di questa impostazione:** Tutti i prezzi nel feed verranno convertiti o visualizzati nella valuta selezionata.
  - **Valore consigliato:** La valuta del tuo pubblico target principale su TikTok (ad esempio, USD per un mercato statunitense, EUR per un mercato europeo).
  - **Scenario / esempio del commerciante:** Se i tuoi annunci TikTok sono rivolti a clienti nel Regno Unito, selezioneresti "GBP" per assicurarti che i prezzi siano mostrati in sterline britanniche.
- **Paese predefinito per la spedizione:**

  - **Cosa fa questa impostazione:** Imposta il paese predefinito utilizzato per il calcolo dei costi di spedizione e della disponibilità nel feed. Questo è importante affinché TikTok comprenda dove i tuoi prodotti possono essere spediti.
  - **Effetto della modifica di questa impostazione:** Le informazioni sulla spedizione nel feed saranno basate sulle regole di spedizione del paese selezionato configurate nel tuo negozio PrestaShop.
  - **Valore consigliato:** Il tuo paese di destinazione di spedizione principale.
  - **Scenario / esempio del commerciante:** Se la maggior parte delle tue vendite avviene in Francia, selezioneresti "Francia" qui.
- **Includi prodotti esauriti:**

  - **Cosa fa questa impostazione:** Determina se i prodotti attualmente contrassegnati come "esauriti" nel tuo negozio PrestaShop debbano essere inclusi nel feed TikTok.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I prodotti esauriti appariranno nel feed, tipicamente con uno stato "non disponibile".
    - *Quando disabilitato:* I prodotti esauriti saranno completamente esclusi dal feed.
  - **Valore consigliato:** NO (a meno che tu non abbia una strategia specifica per preordini o notifiche di ritorno in stock).
  - **Scenario / esempio del commerciante:** Generalmente, vuoi mostrare solo prodotti disponibili nei tuoi annunci per evitare la frustrazione del cliente. Se hai un lungo tempo di consegna per prodotti personalizzati, potresti includerli ma contrassegnarli come "preordine".
- **Escludi Categorie Specifiche:**

  - **Cosa fa questa impostazione:** Ti consente di selezionare categorie di prodotti specifiche dal tuo negozio PrestaShop che NON desideri appaiano nel feed TikTok.
  - **Effetto della modifica di questa impostazione:** I prodotti appartenenti alle categorie selezionate verranno omessi dal feed generato.
  - **Valore consigliato:** Dipende dal tuo negozio.
  - **Scenario / esempio del commerciante:** Potresti escludere categorie come "Carte Regalo" o "Servizi" se non sono prodotti fisici adatti per gli annunci del catalogo TikTok. Oppure, se hai una categoria solo B2B, la escluderesti dagli annunci rivolti ai consumatori.
- **Escludi Prodotti Specifici:**

  - **Cosa fa questa impostazione:** Fornisce un modo per selezionare manualmente i singoli prodotti che dovrebbero essere esclusi dal feed TikTok, indipendentemente dalla loro categoria.
  - **Effetto della modifica di questa impostazione:** I prodotti selezionati non saranno inclusi nel feed.
  - **Valore consigliato:** Dipende dal tuo negozio.
  - **Scenario / esempio del commerciante:** Potresti escludere un prodotto che fa parte di una vendita flash a tempo limitato che non vuoi pubblicizzare su TikTok, o un prodotto che ha restrizioni legali per la pubblicità in determinate regioni.
- **Usa Descrizione Breve del Prodotto:**

  - **Cosa fa questa impostazione:** Determina se la descrizione breve o la descrizione completa dei tuoi prodotti viene utilizzata nel feed TikTok.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Verrà utilizzata la descrizione del prodotto più breve e concisa.
    - *Quando disabilitato:* Verrà utilizzata la descrizione del prodotto più lunga e completa.
  - **Valore consigliato:** SÌ (le descrizioni brevi sono spesso migliori per gli annunci, poiché gli utenti hanno una capacità di attenzione limitata).
  - **Scenario / esempio del commerciante:** Gli annunci TikTok beneficiano di informazioni concise. L'uso della descrizione breve assicura che il tuo testo pubblicitario sia incisivo e diretto.
- **Esporta Caratteristiche del Prodotto come Attributi:**

  - **Cosa fa questa impostazione:** Se abilitata, le caratteristiche del prodotto di PrestaShop (come "Materiale", "Colore", "Taglia") verranno esportate come attributi aggiuntivi nel feed TikTok, fornendo informazioni più dettagliate sul prodotto.
  - **Effetto della modifica di questa impostazione:** Informazioni più dettagliate sul prodotto saranno disponibili per TikTok per un migliore targeting e visualizzazione degli annunci.
  - **Valore consigliato:** SÌ
  - **Scenario / esempio del commerciante:** Se vendi abbigliamento, l'esportazione di "Colore" e "Taglia" come attributi consente a TikTok di mostrare annunci più specifici (ad esempio, "Vestito Rosso, Taglia M").
- **Esporta Combinazioni di Prodotto (Varianti):**

  - **Cosa fa questa impostazione:** Cruciale per i negozi con prodotti che hanno variazioni (ad esempio, una T-shirt disponibile in diverse taglie e colori). Questa impostazione assicura che ogni combinazione unica venga esportata come elemento separato nel feed.
  - **Effetto della modifica di questa impostazione:** Ogni variante di prodotto avrà la propria voce nel feed, con il suo prezzo specifico, stock e immagine, consentendo a TikTok di visualizzare la variante esatta pubblicizzata.
  - **Valore consigliato:** SÌ (quasi sempre, a meno che tu non venda solo prodotti semplici senza variazioni).
  - **Scenario / esempio del commerciante:** Se vendi una scarpa disponibile nelle taglie 7, 8 e 9, abilitando questa opzione TikTok vedrà tre prodotti distinti, ognuno con il proprio SKU e disponibilità.
- **Esporta Attributo Taglia:**

  - **Cosa fa questa impostazione:** Specificamente per i prodotti con combinazioni, questa impostazione assicura che l'attributo "taglia" di ogni combinazione sia esplicitamente incluso nel feed, il che è importante per abbigliamento e calzature.
  - **Effetto della modifica di questa impostazione:** La taglia di ogni variante di prodotto sarà chiaramente elencata nel feed.
  - **Valore consigliato:** SÌ (specialmente per moda, calzature o qualsiasi prodotto dipendente dalla taglia).
  - **Scenario / esempio del commerciante:** Per un negozio di abbigliamento, questo assicura che una "T-shirt Blu Grande" sia correttamente identificata da TikTok, non solo una "T-shirt Blu".
- **Esporta Data di Disponibilità:**

  - **Cosa fa questa impostazione:** Include la data "disponibile per l'ordine" per i prodotti, utile per gli articoli in preordine o i prodotti con date di rilascio future.
  - **Effetto della modifica di questa impostazione:** TikTok riceverà informazioni su quando un prodotto diventerà disponibile.
  - **Valore consigliato:** SÌ (se utilizzi questa funzione in PrestaShop).
  - **Scenario / esempio del commerciante:** Se stai lanciando un nuovo prodotto il mese prossimo, questo consente a TikTok di mostrare annunci di "preordine" con la data di disponibilità corretta.
- **Mappatura Categoria Prodotto Google:**

  - **Cosa fa questa impostazione:** TikTok spesso sfrutta l'ampia tassonomia dei prodotti di Google. Questa sezione ti consente di mappare le tue categorie PrestaShop alle categorie di prodotti Google più pertinenti. Questo migliora la rilevanza e il targeting degli annunci.
  - **Effetto della modifica di questa impostazione:** I tuoi prodotti saranno correttamente categorizzati secondo la tassonomia di Google nel feed, che TikTok utilizza per una migliore comprensione e targeting.
  - **Valore consigliato:** Mappa il maggior numero possibile di categorie.
  - **Scenario / esempio del commerciante:** Se hai una categoria PrestaShop "Abiti Estivi", la mapperesti a una categoria di prodotti Google come "Abbigliamento e Accessori > Abbigliamento > Abiti".
- **Genera URL Feed:**

  - **Cosa fa questa impostazione:** Dopo aver configurato tutte le impostazioni, questo pulsante genera l'URL unico per il tuo feed di prodotti TikTok. Questo URL è quello che fornirai a TikTok Ads Manager.
  - **Effetto della modifica di questa impostazione:** Cliccando su questo verrà visualizzato l'URL. Il feed a questo URL rifletterà tutte le impostazioni scelte.
  - **Valore consigliato:** Clicca su questo dopo che tutte le altre impostazioni sono state finalizzate.
  - **Scenario / esempio del commerciante:** Una volta configurato tutto, clicca su questo, copia l'URL e incollalo nel tuo TikTok Ads Manager quando imposti il tuo Catalogo.

### 2.2 Schermate di amministrazione dedicate e viste del controller

Il modulo fornisce una sezione dedicata nel tuo Back Office di PrestaShop per la gestione e la generazione dei tuoi feed di prodotti TikTok.

**Nome schermata e posizione menu:**
Puoi accedere a questa sezione tramite il menu principale di PrestaShop: **Catalogo > TikTok Feed**.

Questa sezione presenta tipicamente una dashboard o un elenco di feed generati, consentendoti di gestire diverse configurazioni di feed se il modulo supporta più feed (ad esempio, per diverse lingue o valute).

#### 2.2.1 Dashboard Feed TikTok (Back Office > Catalogo > TikTok Feed)

Questo è il punto di ingresso principale per la gestione dei tuoi feed TikTok.

- **Azioni e Impostazioni Disponibili:**

  - **Elenco dei Feed:** Vedrai una tabella o un elenco di tutti i tuoi feed TikTok configurati. Ogni voce mostrerà tipicamente:
    - **Nome Feed:** Un nome descrittivo per il tuo feed (ad esempio, "Feed Inglese US", "Feed Francese EU").
    - **Lingua:** La lingua dei prodotti in questo feed.
    - **Valuta:** La valuta dei prezzi in questo feed.
    - **Ultima Generazione:** Il timestamp di quando il feed è stato aggiornato l'ultima volta.
    - **URL Feed:** Il link diretto al file del feed generato (CSV o XML).
    - **Azioni:** Pulsanti per "Modifica", "Genera Ora" o "Elimina" il feed.
  - **Pulsante "Aggiungi Nuovo Feed":** Ti consente di creare una nuova configurazione di feed, potenzialmente per una lingua, valuta o set di esclusioni di prodotti diversi.
  - **Pulsante "Genera Tutti i Feed":** Un'opzione comoda per aggiornare tutti i tuoi feed configurati contemporaneamente.
- **Effetto dei cambiamenti:**

  - **Aggiunta di un Nuovo Feed:** Crea una nuova istanza di configurazione, consentendoti di definire un set separato di regole (lingua, valuta, esclusioni) per un feed TikTok distinto. Questo è utile per negozi multi-paese o multi-lingua.
  - **Modifica di un Feed:** Ti porta a un modulo di configurazione (simile alla configurazione principale del modulo, ma specifico per questa istanza di feed) dove puoi regolare le sue impostazioni.
  - **Generazione di un Feed:** Attiva il modulo per elaborare il tuo catalogo prodotti in base alle impostazioni del feed e creare/aggiornare il file del feed al suo URL unico. Questo è cruciale per garantire che TikTok abbia sempre le informazioni più aggiornate sui prodotti.
  - **Eliminazione di un Feed:** Rimuove la configurazione del feed e il file generato associato.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

  1. **Configurazione Iniziale:** Crea almeno un feed per il tuo mercato di riferimento principale (ad esempio, inglese, USD).
  2. **Configurazione Multi-Mercato:** Se ti rivolgi a più paesi o lingue, crea un feed separato per ciascuno, configurando le impostazioni di lingua, valuta e paese in modo appropriato.
  3. **Generazione Regolare:** TikTok tipicamente estrae i feed secondo una pianificazione (ad esempio, giornalmente). Puoi cliccare manualmente su "Genera Ora" se hai apportato modifiche significative ai prodotti (nuovi prodotti, aggiornamenti di prezzo, modifiche di stock) e vuoi che TikTok le rifletta immediatamente. Altrimenti, il modulo spesso ha un meccanismo di generazione automatica o una configurazione di cron job (vedi la sezione Sviluppatore).
  4. **Monitora lo Stato del Feed:** Controlla regolarmente il tuo TikTok Ads Manager per eventuali errori o avvisi del feed. Se sorgono problemi, rivedi le impostazioni del tuo modulo e rigenera il feed.

#### 2.2.2 Modulo di configurazione del feed (Accessibile tramite "Aggiungi nuovo feed" o "Modifica" un feed)

Questa schermata è dove definisci i parametri specifici per un singolo feed di prodotti TikTok. Rispecchia molte delle impostazioni trovate nella pagina di configurazione principale del modulo, ma le applica a una singola istanza di feed.

- **Campi e Colonne del Modulo:**

  - **Nome Feed:** Un nome unico e descrittivo per questo feed specifico (ad esempio, "Catalogo Inglese US", "Catalogo Tedesco DE").
  - **Lingua:** Seleziona la lingua per questo feed.
  - **Valuta:** Seleziona la valuta per questo feed.
  - **Paese:** Seleziona il paese predefinito per la spedizione per questo feed.
  - **Includi Prodotti Esauriti:** (Come sopra, ma specifico per questo feed).
  - **Escludi Categorie Specifiche:** (Come sopra, ma specifico per questo feed).
  - **Escludi Prodotti Specifici:** (Come sopra, ma specifico per questo feed).
  - **Usa Descrizione Breve del Prodotto:** (Come sopra, ma specifico per questo feed).
  - **Esporta Caratteristiche del Prodotto come Attributi:** (Come sopra, ma specifico per questo feed).
  - **Esporta Combinazioni di Prodotto (Varianti):** (Come sopra, ma specifico per questo feed).
  - **Esporta Attributo Taglia:** (Come sopra, ma specifico per questo feed).
  - **Esporta Data di Disponibilità:** (Come sopra, ma specifico per questo feed).
  - **Mappatura Categoria Prodotto Google:** (Come sopra, ma specifico per questo feed).
- **Effetto dei cambiamenti:** Il salvataggio delle modifiche in questo modulo aggiorna la configurazione per il feed specifico che stai modificando. Dovrai quindi "Generare ora" per quel feed per applicare le modifiche al file del feed effettivo.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Pagina di configurazione del modulo** | Abilita Modulo | SÌ | Attiva/disattiva la funzionalità del modulo. |
|  | Tipo di Generazione Feed | XML | Scegli il formato CSV o XML per il feed. |
|  | Lingua predefinita per il feed | Lingua principale del negozio | Imposta la lingua per i dati del prodotto. |
|  | Valuta predefinita per il feed | Valuta principale del negozio | Imposta la valuta per i prezzi dei prodotti. |
|  | Paese predefinito per la spedizione | Paese di spedizione principale | Imposta il paese predefinito per le informazioni di spedizione. |
|  | Includi prodotti esauriti | NO | Esclude gli articoli esauriti dal feed. |
|  | Escludi Categorie Specifiche | (Nessuno) | Omette i prodotti dalle categorie selezionate. |
|  | Escludi Prodotti Specifici | (Nessuno) | Omette prodotti specifici dal feed. |
|  | Usa Descrizione Breve del Prodotto | SÌ | Utilizza descrizioni brevi per la concisione. |
|  | Esporta Caratteristiche del Prodotto come Attributi | SÌ | Include le caratteristiche del prodotto come attributi. |
|  | Esporta Combinazioni di Prodotto (Varianti) | SÌ | Esporta ogni variante di prodotto come un elemento separato. |
|  | Esporta Attributo Taglia | SÌ | Include l'attributo taglia per le varianti. |
|  | Esporta Data di Disponibilità | SÌ | Include la data di disponibilità del prodotto. |
|  | Mappatura Categoria Prodotto Google | Mappa tutti i pertinenti | Mappa le categorie PrestaShop alla tassonomia di Google per TikTok. |
|  | Genera URL Feed | Clicca dopo la configurazione | Crea/aggiorna l'URL unico per il feed. |
| **Dashboard Feed TikTok** | Aggiungi Nuovo Feed | N/A | Crea una nuova, separata configurazione del feed. |
|  | Modifica Feed | N/A | Modifica le impostazioni per un feed esistente. |
|  | Genera Ora (per un feed specifico) | N/A | Aggiorna manualmente un singolo file di feed. |
|  | Genera Tutti i Feed | N/A | Aggiorna manualmente tutti i file di feed configurati. |
|  | Elimina Feed | N/A | Rimuove una configurazione del feed e il suo file. |
| **Modulo di configurazione del feed** | Nome Feed | Nome Descrittivo | Identifica il feed specifico. |
|  | (Tutte le altre impostazioni) | (Come sopra) | Configura i parametri per questa singola istanza di feed. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei annunci TikTok mostrano prezzi obsoleti o prodotti esauriti. Cosa devo fare?**
**R1:** Questo di solito significa che il tuo feed TikTok non viene aggiornato abbastanza frequentemente.
1. Vai su **Catalogo > TikTok Feed** nel tuo Back Office di PrestaShop.
2. Trova il feed pertinente e clicca sul pulsante "Genera ora".
3. Assicurati di aver impostato un cron job per aggiornare automaticamente i tuoi feed quotidianamente (consigliato). Verifica con il tuo webmaster o provider di hosting per confermare che il cron job sia in esecuzione correttamente.
4. Verifica l'impostazione "Includi prodotti esauriti" nella configurazione del feed. Se è abilitata e non desideri articoli esauriti, disabilitala.

**D2: Alcuni dei miei prodotti mancano dal feed TikTok.**
**R2:** Controlla le seguenti impostazioni per il feed specifico:
1. **"Escludi Categorie Specifiche":** Assicurati che le categorie dei prodotti mancanti non siano selezionate qui.
2. **"Escludi Prodotti Specifici":** Assicurati che i singoli prodotti non siano esclusi manualmente.
3. **"Includi Prodotti Esauriti":** Se i prodotti sono esauriti e questa impostazione è disabilitata, non appariranno.
4. **Visibilità del Prodotto:** Assicurati che i prodotti siano attivi e visibili nel tuo negozio PrestaShop.

**D3: Le mie descrizioni dei prodotti sembrano troppo lunghe o troppo brevi nel feed TikTok.**
**R3:** Vai alla configurazione del feed e regola l'impostazione "Usa Descrizione Breve del Prodotto":
- Se le descrizioni sono troppo lunghe, abilita questa impostazione per utilizzare la descrizione più breve.
- Se le descrizioni sono troppo brevi e desideri maggiori dettagli, disabilita questa impostazione per utilizzare la descrizione completa.

**D4: Come posso mappare efficacemente le mie categorie alle Categorie di Prodotto Google?**
**R4:**
1. Accedi alla sezione "Mappatura Categoria Prodotto Google" all'interno della configurazione del tuo feed.
2. Per ciascuna delle tue categorie PrestaShop, cerca la Categoria di Prodotto Google più pertinente. Sii il più specifico possibile.
3. Se non riesci a trovare una corrispondenza esatta, scegli la categoria più ampia e vicina.
4. Questa mappatura aiuta TikTok a comprendere meglio i tuoi prodotti per il targeting.

**D5: Ho apportato modifiche, ma l'URL del feed mostra ancora dati vecchi. Cosa c'è che non va?**
**R5:** Dopo aver apportato modifiche alle impostazioni del modulo o alla configurazione di un feed specifico, **devi** rigenerare il feed. Vai su **Catalogo > TikTok Feed**, trova il feed che hai modificato e clicca su "Genera ora". Se hai modificato le impostazioni globali, potresti dover rigenerare tutti i feed.

**D6: Il mio tema personalizzato sta causando problemi di visualizzazione nel Back Office per il modulo.**
**R6:** Sebbene i componenti front-office del modulo siano invisibili, la sua interfaccia Back Office potrebbe entrare in conflitto con temi di amministrazione pesantemente personalizzati.
1. **Svuota Cache Smarty:** Vai su **Parametri Avanzati > Prestazioni** nel tuo Back Office di PrestaShop. Clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti). Questo spesso risolve piccoli problemi di visualizzazione.
2. **Controlla Errori JavaScript:** Apri la console per sviluppatori del tuo browser (F12) nel Back Office. Cerca eventuali errori JavaScript. Se trovi errori, contatta il supporto MyPresta.eu con i dettagli dell'errore.
3. **Cambio Tema Temporaneo:** Se possibile, cambia temporaneamente il tema del tuo Back Office con il tema PrestaShop predefinito per vedere se il problema persiste. Se si risolve, il conflitto è con il tuo tema di amministrazione personalizzato.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

Questa sezione fornisce un'analisi approfondita della struttura tecnica del modulo TikTok Catalog Feed, destinata a sviluppatori e webmaster.

### 4.1 Panoramica dell'Architettura

Il modulo TikTok Catalog Feed segue un modello MVC (Model-View-Controller) standard di PrestaShop, focalizzato principalmente sull'amministrazione del Back Office e sulla consegna dei dati al front-office. Sfrutta la classe `Module` di PrestaShop per l'installazione/disinstallazione e la configurazione, e `AdminController` per la gestione delle impostazioni del feed. La logica centrale ruota attorno alla generazione dinamica dei dati del prodotto in un formato CSV o XML strutturato, accessibile tramite un `ModuleFrontController` dedicato. Non introduce classi `ObjectModel` personalizzate ma interroga direttamente i dati principali di prodotto e categoria di PrestaShop.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

Questi controller sono responsabili di servire il feed di prodotti effettivo a TikTok.

- `controllers/front/feed.php`
  - **Nome classe e classe genitore:** `TiktokfeedFeedModuleFrontController` estende `ModuleFrontController`.
  - **Responsabilità:** Questo è l'endpoint primario per TikTok per estrarre il catalogo prodotti. Genera dinamicamente il feed di prodotti (CSV o XML) in base ai parametri di configurazione (lingua, valuta, esclusioni) associati a un ID feed specifico. Gestisce il recupero dei dati, la formattazione e l'output come download di file o stream diretto. È progettato per essere stateless, elaborando la richiesta e restituendo il feed.
- `controllers/front/index.php`
  - **Nome classe e classe genitore:** `TiktokfeedIndexModuleFrontController` estende `ModuleFrontController`.
  - **Responsabilità:** Questo controller è tipicamente un segnaposto o un fallback. In molti moduli, `index.php` nella directory del controller frontale potrebbe gestire il routing predefinito o semplicemente reindirizzare. Per questo modulo, `feed.php` è il controller frontale critico. Questo `index.php` potrebbe non avere una logica specifica o potrebbe essere utilizzato per una pagina frontale generale del modulo se ne fosse implementata una (cosa che non è il caso per un modulo di feed).

#### Controller Admin Back-Office

Questi controller gestiscono la configurazione del modulo e le impostazioni di generazione del feed all'interno del Back Office di PrestaShop.

- `controllers/admin/AdminExportProductsFeedTiktok.php`
  - **Nome classe e classe genitore:** `AdminExportProductsFeedTiktokController` estende `ModuleAdminController`.
  - **Nome tab e entità gestita:** Questo controller è responsabile della sezione principale "TikTok Feed" sotto **Catalogo > TikTok Feed**. Gestisce la creazione, la modifica e l'eliminazione delle singole configurazioni del feed. Visualizza un elenco dei feed configurati e fornisce moduli per le loro impostazioni dettagliate.
  - **Funzionalità chiave:**
    - `renderList()`: Visualizza la tabella dei feed esistenti.
    - `renderForm()`: Renderizza il modulo per aggiungere/modificare un feed, inclusi campi per lingua, valuta, esclusioni di categoria/prodotto, mappatura delle categorie Google, ecc.
    - Gestisce il salvataggio e l'aggiornamento delle configurazioni del feed (`postProcess()`).
    - Attiva il processo di generazione del feed per feed specifici.
- `controllers/admin/index.php`
  - **Nome classe e classe genitore:** `AdminTiktokfeedIndexController` estende `ModuleAdminController`.
  - **Nome tab e entità gestita:** Questo controller probabilmente funge da punto di ingresso principale per la sezione amministrativa del modulo, potenzialmente reindirizzando a `AdminExportProductsFeedTiktokController` o fornendo una dashboard di alto livello. Data la struttura del modulo, `AdminExportProductsFeedTiktokController` è dove risiede la logica principale di gestione del feed. Questo `index.php` potrebbe essere per una panoramica generale del modulo o un semplice reindirizzamento.

### 4.3 Classi Core e Modelli (`classes/`)

Il dossier del modulo non indica classi personalizzate nella directory `classes/`. Ciò suggerisce che il modulo si basa principalmente sulle classi `ObjectModel` core di PrestaShop `Product`, `Category`, `Language`, `Currency`, `Carrier` e `Configuration` per l'archiviazione e il recupero dei dati. La logica di generazione del feed è probabilmente incapsulata nel file principale del modulo (`tiktokfeed/index.php`) e nel `AdminExportProductsFeedTiktokController`.

### 4.4 Risorse JavaScript (`views/js/`)

- `tiktokfeed/lib/searchTool/views/js/autocomplete.js`
  - **Ambito:** Back-office.
  - **Scopo:** Fornisce la funzionalità di completamento automatico, probabilmente utilizzata per selezionare prodotti o categorie da escludere, o per la mappatura delle categorie Google. Collega i listener di eventi ai campi di input, esegue richieste AJAX per suggerimenti di ricerca e aggiorna il DOM con i risultati.
- `tiktokfeed/views/js/admin-app.js`
  - **Ambito:** Back-office.
  - **Scopo:** Questo è il file JavaScript principale per l'interfaccia Back Office del modulo. Gestisce vari elementi interattivi sui moduli di configurazione del feed e sulla dashboard. Questo potrebbe includere:
    - Validazione del modulo.
    - Aggiornamenti dinamici basati sulle opzioni selezionate (ad esempio, mostrare/nascondere campi).
    - Chiamate AJAX per salvare le impostazioni o attivare la generazione del feed.
    - Interazioni con i modali fancybox (ad esempio, per la selezione di categorie/prodotti).

### 4.5 Fogli di stile CSS (`views/css/`)

- `tiktokfeed/lib/searchTool/views/css/autocomplete.css`
  - **Ambito:** Stile dell'amministrazione del Back-office.
  - **Scopo:** Stila i menu a discesa di completamento automatico e i campi di input utilizzati dallo script `autocomplete.js`, garantendo un'esperienza di ricerca coerente e facile da usare all'interno dei moduli di amministrazione.
- `tiktokfeed/views/admin-theme.css`
  - **Ambito:** Stile dell'amministrazione del Back-office.
  - **Scopo:** Fornisce regolazioni di stile generali per l'interfaccia del Back Office del modulo per integrarsi perfettamente con il tema di amministrazione di PrestaShop. Questo potrebbe includere regolazioni del layout, stile dei pulsanti o formattazione delle tabelle.
- `tiktokfeed/views/css/admin-app.css`
  - **Ambito:** Stile dell'amministrazione del Back-office.
  - **Scopo:** Contiene stili specifici per i componenti personalizzati del modulo, i moduli e gli elementi della dashboard all'interno del Back Office di PrestaShop. Questo potrebbe includere stili per la tabella di elenco dei feed, i pannelli di configurazione e i modali fancybox.

### 4.6 Struttura del Template Smarty (`views/templates/`)

#### Template Hook (`views/templates/hook/`)

Il dossier del modulo non elenca esplicitamente i template in una sottodirectory `hook/`, il che implica che il modulo non renderizza contenuti direttamente negli hook del front-office. La sua funzione principale è la generazione di dati, non la visualizzazione front-end.

#### Template Admin (`views/templates/admin/`)

Questi template sono utilizzati per il rendering dell'interfaccia Back Office del modulo.

- `tiktokfeed/views/templates/admin/dashboard.tpl`
  - **Scopo:** Probabilmente il template principale della dashboard per la sezione TikTok Feed, che mostra una panoramica dei feed, dello stato e delle azioni rapide.
- `tiktokfeed/views/templates/admin/feeds.tpl`
  - **Scopo:** Renderizza l'elenco dei feed TikTok configurati, tipicamente una tabella con colonne per nome del feed, lingua, valuta, URL e pulsanti di azione (modifica, genera, elimina). Questo è probabilmente renderizzato da `AdminExportProductsFeedTiktokController::renderList()`.
- `tiktokfeed/views/templates/admin/form-chrome.tpl`
  - **Scopo:** Un wrapper o un template parziale utilizzato per fornire uno stile e una struttura coerenti per i moduli di configurazione del modulo, potenzialmente includendo intestazione, piè di pagina ed elementi di layout generali per il modulo.
- `tiktokfeed/views/templates/admin/layout.tpl`
  - **Scopo:** Un template di layout di base per le pagine di amministrazione del modulo, che definisce la struttura complessiva, inclusi intestazione, navigazione e aree di contenuto.

#### Altri template relativi all'amministrazione

Questi template sono probabilmente utilizzati come parziali o per componenti UI specifici all'interno dei moduli di amministrazione.

- `tiktokfeed/lib/searchTool/views/scripts.tpl`
  - **Scopo:** Include JavaScript per lo strumento di ricerca, probabilmente lo script `autocomplete.js` e la sua inizializzazione.
- `tiktokfeed/views/categories-fancybox.tpl`
  - **Scopo:** Renderizza il contenuto per un modale Fancybox utilizzato per selezionare le categorie per l'esclusione o la mappatura.
- `tiktokfeed/views/exclude-products.tpl`
  - **Scopo:** Renderizza l'interfaccia utente per la selezione e la gestione dei prodotti da escludere dal feed, possibilmente all'interno di un Fancybox o di una sezione dedicata del modulo.
- `tiktokfeed/views/google_lang_links.tpl`
  - **Scopo:** Renderizza collegamenti o elementi UI relativi alla mappatura delle categorie di prodotto Google, potenzialmente per diverse lingue.
- `tiktokfeed/views/returnAlert.tpl`
  - **Scopo:** Un template generico per la visualizzazione di messaggi/avvisi di successo o errore nel Back Office.
- `tiktokfeed/views/script-fancybox.tpl`
  - **Scopo:** Include JavaScript per l'integrazione di Fancybox, probabilmente per l'apertura di modali per la selezione di categorie/prodotti.
- `tiktokfeed/views/script.tpl`
  - **Scopo:** Un template di script generale, possibilmente per l'inizializzazione JavaScript a livello di modulo o piccoli script inline.

### 4.7 Schema del Database e Mappa degli Hook

- **Tabelle del database**:

  - Il modulo non sembra creare tabelle SQL personalizzate in base al dossier.
  - Memorizza le sue impostazioni di configurazione (ad esempio, tipo di feed, lingua/valuta predefinita, elenchi di esclusione, mappature delle categorie Google) nella tabella `ps_configuration` di PrestaShop. Le chiavi di configurazione seguirebbero tipicamente un modello come `TTF_FEED_TYPE`, `TTF_DEFAULT_LANG`, `TTF_EXCLUDE_CATEGORIES`, ecc.
  - Le configurazioni dei singoli feed (se sono supportati più feed) potrebbero essere memorizzate come array serializzati in `ps_configuration` o potenzialmente in una tabella personalizzata se il modulo ne introducesse una (cosa non indicata).
- **Tabella degli Hook Registrati**:
  La funzione principale del modulo è la generazione di dati, non la visualizzazione front-office, quindi non registra hook per la visualizzazione di contenuti sul negozio (ad esempio, `displayHeader`, `displayRightColumn`).
  Registrerà, tuttavia, i seguenti hook per la sua funzionalità principale:

  | Nome Hook | Tempistica di Esecuzione | Scopo Tecnico |
  | --- | --- | --- |
  | `actionModuleInstall` | Durante l'installazione del modulo | Crea voci di configurazione, registra schede amministrative. |
  | `actionModuleUninstall` | Durante la disinstallazione del modulo | Pulisce le voci di configurazione, annulla la registrazione delle schede amministrative. |
  | `actionAdminControllerSetMedia` | Quando viene caricato un controller amministrativo | Mette in coda JS e CSS specifici del modulo per il Back Office. |
  | `displayBackOfficeHeader` | Renderizza il contenuto nell'intestazione del Back Office | Potenzialmente per JS/CSS amministrativi globali o notifiche. |
  | `actionSchedulerCron` (o simile) | Quando viene eseguito il cron job di PrestaShop | Attiva la generazione automatica del feed se configurato. |

### Configurazione del Cron Job per la Generazione Automatica del Feed

Per gli aggiornamenti automatici del feed, dovrai impostare un cron job sul tuo server per richiamare un URL o uno script specifico fornito dal modulo. Questo URL tipicamente punta a un controller frontale che attiva la generazione del feed.

**Esempio di comando Cron Job (Consulta il tuo provider di hosting per la sintassi esatta):**

Finestra del terminale

```
0 3 \* \* \* wget -q -O /dev/null "https://yourstore.com/module/tiktokfeed/feed?action=generate\_all&token=YOUR\_SECURE\_TOKEN" >/dev/null 2>&1
```

- `0 3 * * *`: Questo programma il job per essere eseguito quotidianamente alle 3:00 del mattino.
- `wget -q -O /dev/null`: Recupera silenziosamente l'URL e scarta l'output.
- `https://yourstore.com/module/tiktokfeed/feed?action=generate_all&token=YOUR_SECURE_TOKEN`: Questo è l'URL che attiva la generazione del feed. Il parametro `token` è cruciale per la sicurezza per prevenire accessi non autorizzati. Il modulo dovrebbe fornire questo token nella sua configurazione o documentazione.
- `>/dev/null 2>&1`: Reindirizza tutto l'output a null, prevenendo notifiche email non necessarie.

**Importante:** L'URL e il token esatti saranno forniti dal modulo dopo la configurazione. Utilizza sempre il token sicuro per proteggere il tuo endpoint di generazione del feed.

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale degli sviluppatori, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Assicurati di utilizzare l'ultima versione compatibile del modulo per il tuo negozio PrestaShop.
