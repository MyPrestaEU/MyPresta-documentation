---
title: "LLMS.txt Generator Pro - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop LLMS.txt Generator Pro di MyPresta.eu."
sidebar:
  label: "LLMS.txt Generator Pro - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo LLMS.txt Generator Pro su MyPresta.eu](https://mypresta.eu/modules/seo/llmstxt-generator-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/seo/llmstxt-generator-pro/)
>
> ---


# LLMS.txt Generator Pro

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL). Il tuo server deve anche consentire la scrittura di file nella directory root affinché il file `llms.txt` possa essere generato.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > LLMS.txt Generator Pro)

Questo è il pannello di controllo principale per il tuo modulo LLMS.txt Generator Pro. Qui definirai come viene generato il tuo file `llms.txt` e quali contenuti include.

#### Impostazioni generali

- **Abilita generazione LLMS.txt:**

  - **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare la funzionalità principale del modulo.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il modulo genererà e servirà il file `llms.txt` in base alle tue impostazioni. I crawler AI potranno accedervi.
    - *Quando disabilitato:* Il file `llms.txt` non verrà generato o servito dal modulo. I crawler AI non riceveranno indicazioni specifiche dal tuo negozio.
  - **Valore consigliato:** SÌ
  - **Scenario / esempio del commerciante:** Hai appena installato il modulo e vuoi iniziare a guidare i bot AI. Abilita questa opzione. Se hai bisogno di interrompere temporaneamente la guida AI per manutenzione, puoi disabilitarla qui.
- **Tipo di file LLMS.txt:**

  - **Cosa fa questa impostazione:** Determina se il file `llms.txt` viene generato come file statico (scritto sul tuo server) o servito dinamicamente su richiesta.
  - **Effetto della modifica di questa impostazione:**
    - *Statico:* Il modulo scrive un file `llms.txt` fisico nella directory root del tuo negozio. Questo è generalmente più veloce per i bot AI in quanto non richiede l'elaborazione PHP ad ogni richiesta.
    - *Dinamico:* Il file `llms.txt` viene generato dal codice PHP di PrestaShop ogni volta che un bot AI lo richiede. Questo garantisce il contenuto più aggiornato ma può essere leggermente più lento.
  - **Valore consigliato:** Statico (per le prestazioni, a meno che tu non abbia frequenti modifiche ai contenuti in tempo reale che devono essere riflesse istantaneamente).
  - **Scenario / esempio del commerciante:** Per la maggior parte dei negozi, statico va bene. Se hai un negozio con traffico molto elevato e prezzi o stock di prodotti in costante cambiamento, dinamico potrebbe essere preferito, ma considera l'impatto sulle prestazioni.
- **Genera llms-full.txt:**

  - **Cosa fa questa impostazione:** Controlla se viene generato anche un file `llms-full.txt` aggiuntivo e più completo. Questo file include tipicamente informazioni più dettagliate o meno ristrette rispetto allo standard `llms.txt`.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Un file `llms-full.txt` verrà creato insieme a `llms.txt`, offrendo ai crawler AI un set di dati più ricco.
    - *Quando disabilitato:* Verrà generato solo il file `llms.txt` standard.
  - **Valore consigliato:** SÌ (per fornire il massimo dei dati all'AI, a meno che tu non abbia ragioni specifiche per limitarlo).
  - **Scenario / esempio del commerciante:** Vuoi che i modelli AI abbiano accesso a quante più informazioni pertinenti possibile sui tuoi prodotti, inclusi dettagli potenzialmente meno critici ma comunque utili.
- **Includi pagine prodotto:**

  - **Cosa fa questa impostazione:** Determina se le singole pagine prodotto sono elencate nel file `llms.txt`.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Gli URL di tutte le tue pagine prodotto attive saranno inclusi, rendendole scopribili dall'AI.
    - *Quando disabilitato:* Le pagine prodotto saranno escluse, il che significa che i bot AI non saranno esplicitamente guidati ad esse tramite `llms.txt`.
  - **Valore consigliato:** SÌ (I prodotti sono solitamente il cuore di un negozio e-commerce).
  - **Scenario / esempio del commerciante:** Vuoi che l'AI aiuti i clienti a trovare prodotti specifici.
- **Includi pagine categoria:**

  - **Cosa fa questa impostazione:** Determina se le pagine di categoria (che elencano gruppi di prodotti) sono elencate nel file `llms.txt`.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Gli URL di tutte le tue pagine di categoria attive saranno inclusi.
    - *Quando disabilitato:* Le pagine di categoria saranno escluse.
  - **Valore consigliato:** SÌ (Le categorie aiutano l'AI a comprendere la struttura del tuo negozio).
  - **Scenario / esempio del commerciante:** Vuoi che l'AI comprenda i diversi tipi di prodotti che vendi e guidi i clienti alle sezioni pertinenti.
- **Includi pagine CMS:**

  - **Cosa fa questa impostazione:** Determina se le tue pagine del sistema di gestione dei contenuti (CMS) (ad esempio, Chi siamo, Contatti, Informazioni sulla spedizione, Informativa sulla privacy) sono elencate.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Gli URL delle pagine CMS attive saranno inclusi.
    - *Quando disabilitato:* Le pagine CMS saranno escluse.
  - **Valore consigliato:** SÌ (Importante per l'AI per comprendere la tua attività e le tue politiche).
  - **Scenario / esempio del commerciante:** Vuoi che l'AI sia in grado di rispondere a domande sulle politiche o sulla storia del tuo negozio.
- **Includi pagine produttore/marchio:**

  - **Cosa fa questa impostazione:** Determina se le pagine dedicate a specifici produttori o marchi sono elencate.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Gli URL delle pagine produttore/marchio attive saranno inclusi.
    - *Quando disabilitato:* Le pagine produttore/marchio saranno escluse.
  - **Valore consigliato:** SÌ (Se i marchi sono importanti per la tua offerta di prodotti).
  - **Scenario / esempio del commerciante:** Vendi prodotti di marchi noti e vuoi che l'AI lo riconosca.
- **Includi pagine fornitore:**

  - **Cosa fa questa impostazione:** Determina se le pagine dedicate a specifici fornitori sono elencate. (Meno comune per la visibilità del front-office, spesso utilizzata per scopi interni).
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Gli URL delle pagine fornitore attive saranno inclusi.
    - *Quando disabilitato:* Le pagine fornitore saranno escluse.
  - **Valore consigliato:** NO (A meno che tu non promuova specificamente i fornitori sul tuo front-office).
  - **Scenario / esempio del commerciante:** Hai un modello di business unico in cui i fornitori sono visibili al pubblico e vuoi che l'AI li indicizzi.
- **Includi pagina Nuovi Prodotti:**

  - **Cosa fa questa impostazione:** Determina se la pagina di elenco "Nuovi Prodotti" è inclusa.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* L'URL della pagina dei nuovi prodotti sarà incluso.
    - *Quando disabilitato:* La pagina dei nuovi prodotti sarà esclusa.
  - **Valore consigliato:** SÌ (Per evidenziare le tue ultime offerte all'AI).
  - **Scenario / esempio del commerciante:** Aggiungi frequentemente nuovi prodotti e vuoi che l'AI ne sia a conoscenza rapidamente.
- **Includi pagina Migliori Vendite:**

  - **Cosa fa questa impostazione:** Determina se la pagina di elenco "Migliori Vendite" o "Più Venduti" è inclusa.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* L'URL della pagina delle migliori vendite sarà incluso.
    - *Quando disabilitato:* La pagina delle migliori vendite sarà esclusa.
  - **Valore consigliato:** SÌ (Per promuovere i tuoi articoli più popolari).
  - **Scenario / esempio del commerciante:** Vuoi che l'AI raccomandi i tuoi articoli più venduti ai clienti.
- **Includi pagina Prezzi Scontati:**

  - **Cosa fa questa impostazione:** Determina se la pagina di elenco "Prezzi Scontati" o "In Offerta" è inclusa.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* L'URL della pagina dei prezzi scontati sarà incluso.
    - *Quando disabilitato:* La pagina dei prezzi scontati sarà esclusa.
  - **Valore consigliato:** SÌ (Per evidenziare i tuoi articoli scontati).
  - **Scenario / esempio del commerciante:** Esegui promozioni e vuoi che l'AI informi i clienti sulle offerte attuali.
- **Includi pagina Contatti:**

  - **Cosa fa questa impostazione:** Determina se la pagina di contatto del tuo negozio è inclusa.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* L'URL della pagina di contatto sarà incluso.
    - *Quando disabilitato:* La pagina di contatto sarà esclusa.
  - **Valore consigliato:** SÌ (Essenziale per l'AI per fornire informazioni sul servizio clienti).
  - **Scenario / esempio del commerciante:** Vuoi che l'AI sia in grado di dire ai clienti come raggiungere il tuo team di supporto.
- **Includi pagina Sitemap:**

  - **Cosa fa questa impostazione:** Determina se la pagina sitemap principale del tuo negozio (se ne hai una) è inclusa.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* L'URL della pagina sitemap sarà incluso.
    - *Quando disabilitato:* La pagina sitemap sarà esclusa.
  - **Valore consigliato:** SÌ (Può aiutare l'AI a scoprire più contenuti, in modo simile alle sitemap dei motori di ricerca).
  - **Scenario / esempio del commerciante:** Vuoi fornire all'AI una panoramica completa della struttura del tuo negozio.
- **Includi URL personalizzati:**

  - **Cosa fa questa impostazione:** Ti consente di aggiungere manualmente URL specifici che non sono generati automaticamente da PrestaShop ma che desideri comunque che l'AI scopra.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Apparirà un'area di testo in cui puoi elencare un URL per riga. Questi URL verranno aggiunti al tuo file `llms.txt`.
    - *Quando disabilitato:* Nessun URL personalizzato verrà aggiunto.
  - **Valore consigliato:** SÌ (Se hai pagine statiche importanti o post di blog al di fuori della struttura principale di PrestaShop).
  - **Scenario / esempio del commerciante:** Hai un blog separato su un sottodominio o pagine di destinazione specifiche che vuoi che l'AI indicizzi.
- **Escludi URL specifici:**

  - **Cosa fa questa impostazione:** Ti consente di specificare manualmente gli URL che *non* devono essere inclusi nel file `llms.txt`, anche se verrebbero altrimenti generati.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Apparirà un'area di testo in cui puoi elencare un URL per riga. Questi URL saranno esplicitamente esclusi.
    - *Quando disabilitato:* Nessun URL sarà esplicitamente escluso da questa impostazione.
  - **Valore consigliato:** Utilizzare secondo necessità per pagine sensibili o irrilevanti.
  - **Scenario / esempio del commerciante:** Hai pagine di test interne, promozioni obsolete o pagine di dati sensibili dei clienti a cui non vuoi assolutamente che l'AI acceda.
- **Escludi prodotti per categoria:**

  - **Cosa fa questa impostazione:** Fornisce un modo per escludere tutti i prodotti appartenenti a categorie specifiche dal file `llms.txt`.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Apparirà un elenco delle tue categorie, permettendoti di selezionare quali escludere. Tutti i prodotti all'interno delle categorie selezionate verranno omessi.
    - *Quando disabilitato:* Tutti i prodotti saranno considerati per l'inclusione, indipendentemente dalla categoria.
  - **Valore consigliato:** Utilizzare secondo necessità.
  - **Scenario / esempio del commerciante:** Vendi sia prodotti pubblici che una gamma di prodotti solo B2B in una categoria specifica che non vuoi che l'AI indicizzi per la ricerca pubblica generale.
- **Escludi prodotti per produttore:**

  - **Cosa fa questa impostazione:** Ti consente di escludere tutti i prodotti di produttori specifici.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Apparirà un elenco dei tuoi produttori per la selezione. I prodotti dei produttori selezionati verranno omessi.
    - *Quando disabilitato:* Tutti i prodotti saranno considerati per l'inclusione, indipendentemente dal produttore.
  - **Valore consigliato:** Utilizzare secondo necessità.
  - **Scenario / esempio del commerciante:** Hai temporaneamente smesso di vendere prodotti di un particolare marchio e non vuoi che l'AI li mostri, anche se sono ancora nel tuo catalogo.
- **Escludi prodotti per fornitore:**

  - **Cosa fa questa impostazione:** Ti consente di escludere tutti i prodotti di fornitori specifici.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Apparirà un elenco dei tuoi fornitori per la selezione. I prodotti dei fornitori selezionati verranno omessi.
    - *Quando disabilitato:* Tutti i prodotti saranno considerati per l'inclusione, indipendentemente dal fornitore.
  - **Valore consigliato:** Utilizzare secondo necessità.
  - **Scenario / esempio del commerciante:** Hai un fornitore i cui prodotti non sono destinati all'indicizzazione pubblica da parte dell'AI.
- **Escludi prodotti per caratteristica:**

  - **Cosa fa questa impostazione:** Ti consente di escludere prodotti in base a specifiche caratteristiche del prodotto (ad esempio, "Colore: Rosso", "Materiale: Legno").
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Puoi selezionare caratteristiche e i loro valori. I prodotti che corrispondono a queste caratteristiche verranno omessi.
    - *Quando disabilitato:* Le caratteristiche del prodotto non verranno utilizzate per l'esclusione.
  - **Valore consigliato:** Utilizzare secondo necessità.
  - **Scenario / esempio del commerciante:** Hai prodotti contrassegnati con una caratteristica "Fuori produzione" che vuoi nascondere all'AI.
- **Escludi prodotti per attributo:**

  - **Cosa fa questa impostazione:** Ti consente di escludere prodotti in base a specifici attributi del prodotto (ad esempio, "Taglia: XL", "Peso: 1kg").
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Puoi selezionare attributi e i loro valori. I prodotti che corrispondono a questi attributi verranno omessi.
    - *Quando disabilitato:* Gli attributi del prodotto non verranno utilizzati per l'esclusione.
  - **Valore consigliato:** Utilizzare secondo necessità.
  - **Scenario / esempio del commerciante:** Hai prodotti con una combinazione di attributi "Esaurito" che non vuoi che l'AI mostri.
- **Escludi prodotti per fascia di prezzo:**

  - **Cosa fa questa impostazione:** Ti consente di escludere prodotti che rientrano in una fascia di prezzo specificata.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Puoi inserire un prezzo minimo e massimo. I prodotti con prezzi all'interno di questo intervallo verranno omessi.
    - *Quando disabilitato:* I prezzi dei prodotti non verranno utilizzati per l'esclusione.
  - **Valore consigliato:** Utilizzare secondo necessità.
  - **Scenario / esempio del commerciante:** Vuoi che l'AI indicizzi solo i tuoi prodotti premium (ad esempio, escludere prodotti sotto i $10).
- **Escludi prodotti per quantità in magazzino:**

  - **Cosa fa questa impostazione:** Ti consente di escludere prodotti in base alla loro attuale quantità in magazzino.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Puoi impostare una quantità minima di magazzino. I prodotti con scorte inferiori a questa quantità verranno omessi.
    - *Quando disabilitato:* La quantità di magazzino del prodotto non verrà utilizzata per l'esclusione.
  - **Valore consigliato:** SÌ (Escludi prodotti con 0 scorte per evitare che l'AI raccomandi articoli non disponibili).
  - **Scenario / esempio del commerciante:** Non vuoi che l'AI mostri prodotti esauriti. Imposta questa opzione per escludere i prodotti con scorte <= 0.
- **Escludi prodotti per visibilità:**

  - **Cosa fa questa impostazione:** Ti consente di escludere prodotti in base alla loro impostazione di visibilità PrestaShop (ad esempio, "Solo catalogo", "Solo ricerca", "Ovunque").
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Puoi selezionare quali opzioni di visibilità escludere. I prodotti che corrispondono a queste verranno omessi.
    - *Quando disabilitato:* La visibilità del prodotto non verrà utilizzata per l'esclusione.
  - **Valore consigliato:** Utilizzare secondo necessità.
  - **Scenario / esempio del commerciante:** Hai prodotti impostati su "Solo catalogo" (non ricercabili) che vuoi anche nascondere all'AI.
- **Escludi prodotti per stato:**

  - **Cosa fa questa impostazione:** Ti consente di escludere prodotti in base al loro stato attivo/inattivo.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Puoi scegliere di escludere i prodotti inattivi.
    - *Quando disabilitato:* Verranno considerati sia i prodotti attivi che quelli inattivi.
  - **Valore consigliato:** SÌ (Escludi prodotti inattivi).
  - **Scenario / esempio del commerciante:** Vuoi che l'AI mostri solo prodotti attualmente disponibili e attivi.
- **Escludi prodotti per data di aggiunta:**

  - **Cosa fa questa impostazione:** Ti consente di escludere prodotti in base alla data in cui sono stati aggiunti al tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Puoi impostare un intervallo di date. I prodotti aggiunti al di fuori di questo intervallo verranno omessi.
    - *Quando disabilitato:* La data di aggiunta del prodotto non verrà utilizzata per l'esclusione.
  - **Valore consigliato:** Utilizzare secondo necessità.
  - **Scenario / esempio del commerciante:** Vuoi che l'AI indicizzi solo i prodotti aggiunti nell'ultimo anno.
- **Escludi prodotti per data di aggiornamento:**

  - **Cosa fa questa impostazione:** Ti consente di escludere prodotti in base alla loro ultima data di aggiornamento.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Puoi impostare un intervallo di date. I prodotti aggiornati al di fuori di questo intervallo verranno omessi.
    - *Quando disabilitato:* La data di aggiornamento del prodotto non verrà utilizzata per l'esclusione.
  - **Valore consigliato:** Utilizzare secondo necessità.
  - **Scenario / esempio del commerciante:** Vuoi che l'AI indicizzi solo i prodotti che sono stati recentemente aggiornati o revisionati.
- **Escludi prodotti per ID prodotto specifici:**

  - **Cosa fa questa impostazione:** Ti consente di inserire manualmente un elenco di ID prodotto specifici, separati da virgole, da escludere.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I prodotti con gli ID specificati verranno omessi.
    - *Quando disabilitato:* Nessun prodotto verrà escluso per ID.
  - **Valore consigliato:** Utilizzare secondo necessità.
  - **Scenario / esempio del commerciante:** Hai alcuni prodotti specifici che sono problematici o sensibili e non devono mai essere indicizzati dall'AI.

#### Impostazioni avanzate

- **Pianificazione rigenerazione (Cron Job):**

  - **Cosa fa questa impostazione:** Definisce la frequenza con cui il file `llms.txt` deve essere rigenerato automaticamente. Questo è cruciale per mantenere il file aggiornato senza intervento manuale.
  - **Effetto della modifica di questa impostazione:**
    - *Giornaliero / Settimanale / Mensile:* Il modulo fornirà un URL per il cron job. Quando questo URL viene richiamato (ad esempio, dal servizio cron del tuo provider di hosting), il file `llms.txt` verrà ricostruito.
    - *Manuale:* Dovrai cliccare manualmente il pulsante "Genera LLMS.txt" ogni volta che desideri aggiornare il file.
  - **Valore consigliato:** Giornaliero (per la maggior parte dei negozi attivi).
  - **Scenario / esempio del commerciante:** Aggiungi nuovi prodotti o aggiorni i prezzi regolarmente. L'impostazione di una rigenerazione giornaliera garantisce che i crawler AI ricevano sempre le informazioni più recenti. Il modulo visualizzerà l'URL del cron job che devi configurare sul tuo server.
- **Supporto Multistore:**

  - **Cosa fa questa impostazione:** Se gestisci un PrestaShop Multistore, questa opzione ti consente di generare file `llms.txt` separati per ciascuno dei tuoi negozi o un singolo file per tutti i negozi.
  - **Effetto della modifica di questa impostazione:**
    - *Abilitato:* Il modulo rispetterà il tuo contesto Multistore e genererà file specifici per il contenuto di ogni negozio.
    - *Disabilitato:* Il modulo potrebbe generare un singolo file basato sul negozio predefinito o comportarsi in modo inaspettato in un ambiente Multistore.
  - **Valore consigliato:** SÌ (se utilizzi Multistore).
  - **Scenario / esempio del commerciante:** Hai cataloghi di prodotti o lingue diverse per ogni negozio nella tua configurazione Multistore e hai bisogno di file `llms.txt` distinti per ciascuno.
- **Durata cache (minuti):**

  - **Cosa fa questa impostazione:** Determina per quanto tempo il file `llms.txt` generato viene memorizzato nella cache prima di essere considerato "obsoleto" e necessitare di rigenerazione (per il tipo di file dinamico).
  - **Effetto della modifica di questa impostazione:**
    - *Valore più alto:* Rigenerazione meno frequente, potenzialmente più veloce per i bot AI ma il contenuto potrebbe essere leggermente più vecchio.
    - *Valore più basso:* Rigenerazione più frequente, garantendo un contenuto più fresco ma potenzialmente un carico del server più elevato.
  - **Valore consigliato:** 60 (1 ora) per dinamico, o irrilevante per statico.
  - **Scenario / esempio del commerciante:** Se utilizzi la generazione dinamica e i dati dei tuoi prodotti cambiano ogni ora, imposta questo valore su 60. Se i cambiamenti sono meno frequenti, puoi aumentarlo.
- **Abilita analisi e tracciamento bot:**

  - **Cosa fa questa impostazione:** Attiva una funzione per tracciare quando i bot AI accedono al tuo file `llms.txt`, fornendo informazioni sulla loro attività.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il modulo registrerà gli accessi al file `llms.txt`, che possono essere visualizzati nella dashboard del modulo.
    - *Quando disabilitato:* Nessun dato di accesso ai bot verrà raccolto.
  - **Valore consigliato:** SÌ (Utile per comprendere l'attività dei crawler AI).
  - **Scenario / esempio del commerciante:** Vuoi vedere quanto spesso i modelli AI scansionano il tuo negozio e quali sono i più attivi.
- **Pulsante Cancella Cache:**

  - **Cosa fa questa impostazione:** Un pulsante manuale per cancellare tutti i file `llms.txt` memorizzati nella cache.
  - **Effetto della modifica di questa impostazione:** Rimuove immediatamente tutti i file `llms.txt` memorizzati, forzando una nuova rigenerazione alla prossima richiesta (per dinamico) o quando viene cliccato il pulsante "Genera LLMS.txt" (per statico).
  - **Valore consigliato:** Clicca quando apporti modifiche significative alle tue impostazioni o al catalogo prodotti e vuoi assicurarti che il file `llms.txt` sia immediatamente aggiornato.
  - **Scenario / esempio del commerciante:** Hai appena aggiunto una nuova importante linea di prodotti e vuoi che l'AI la scopra subito, quindi cancelli la cache e rigeneri.
- **Pulsante Genera LLMS.txt:**

  - **Cosa fa questa impostazione:** Un pulsante manuale per generare o rigenerare immediatamente il file `llms.txt` in base alle tue impostazioni attuali.
  - **Effetto della modifica di questa impostazione:** Il modulo elabora il tuo catalogo e le impostazioni, quindi crea o aggiorna il file `llms.txt`.
  - **Valore consigliato:** Clicca dopo aver apportato modifiche alla configurazione o quando hai bisogno di un aggiornamento immediato, specialmente se utilizzi la generazione di file statici.
  - **Scenario / esempio del commerciante:** Hai finito di configurare tutte le tue regole di esclusione e vuoi creare il file `llms.txt` iniziale.

#### Override per prodotto (Pagina prodotto amministrativa)

Il modulo si integra anche direttamente nelle pagine di modifica del prodotto nel Back Office.

- **Escludi questo prodotto da LLMS.txt:**
  - **Cosa fa questa impostazione:** Una casella di controllo sulle singole pagine prodotto che ti consente di sovrascrivere le impostazioni globali e di escludere specificamente un singolo prodotto dal file `llms.txt`.
  - **Effetto della modifica di questa impostazione:**
    - *Quando selezionato:* Questo prodotto specifico non sarà incluso nel file `llms.txt`, indipendentemente da altre regole di inclusione globali.
    - *Quando deselezionato:* L'inclusione del prodotto sarà determinata dalle impostazioni globali.
  - **Valore consigliato:** Utilizzare secondo necessità per prodotti specifici.
  - **Scenario / esempio del commerciante:** Hai un prodotto temporaneamente non disponibile, o un articolo molto di nicchia che non vuoi che l'AI promuova ampiamente.

#### Override per categoria (Pagina categoria amministrativa)

Allo stesso modo, il modulo si integra nelle pagine di modifica delle categorie.

- **Escludi questa categoria da LLMS.txt:**
  - **Cosa fa questa impostazione:** Una casella di controllo sulle singole pagine di categoria che ti consente di sovrascrivere le impostazioni globali e di escludere specificamente un'intera categoria (e i suoi prodotti) dal file `llms.txt`.
  - **Effetto della modifica di questa impostazione:**
    - *Quando selezionato:* Questa categoria specifica e tutti i prodotti al suo interno non saranno inclusi nel file `llms.txt`.
    - *Quando deselezionato:* L'inclusione della categoria sarà determinata dalle impostazioni globali.
  - **Valore consigliato:** Utilizzare secondo necessità per categorie specifiche.
  - **Scenario / esempio del commerciante:** Hai una categoria "Liquidazione" che cambia frequentemente e preferisci non farla indicizzare dall'AI, o una categoria per uso interno.

### 2.2 Schermate di amministrazione dedicate e viste controller

#### Dashboard (Back Office > Moduli > LLMS.txt Generator Pro > Dashboard)

- **Nome schermata e posizione menu:** Questa schermata è accessibile dalla pagina di configurazione principale del modulo, solitamente tramite una scheda o un link "Dashboard". Fornisce una panoramica dell'attività dei bot AI e dello stato del modulo.
- **Azioni e impostazioni disponibili:**
  - **Analisi del traffico bot:** Visualizza grafici o tabelle che mostrano quali crawler AI (user agent) hanno acceduto al tuo file `llms.txt`, con quale frequenza e quando.
  - **Stato ultima generazione:** Mostra quando il file `llms.txt` è stato generato l'ultima volta, la sua dimensione e il numero di URL inclusi.
  - **Log degli errori:** Eventuali problemi riscontrati durante la generazione verranno visualizzati qui.
- **Effetto delle modifiche:** Questa schermata è principalmente per il monitoraggio e la reportistica. Le modifiche qui sono tipicamente correlate alla visualizzazione dei dati, non all'alterazione del comportamento del negozio.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Controlla periodicamente la dashboard per assicurarti che il tuo file `llms.txt` venga acceduto dai bot AI come previsto e per monitorare eventuali errori. Questo ti aiuta a comprendere l'impatto della tua strategia di visibilità AI.

#### Anteprima (Back Office > Moduli > LLMS.txt Generator Pro > Anteprima)

- **Nome schermata e posizione menu:** Accessibile dalla pagina di configurazione principale del modulo, solitamente tramite una scheda o un link "Anteprima".
- **Azioni e impostazioni disponibili:**
  - **Visualizzazione contenuto LLMS.txt:** Mostra il contenuto effettivo del file `llms.txt` che verrebbe servito ai crawler AI, in base alle tue impostazioni attuali.
  - **Visualizzazione contenuto llms-full.txt:** Se abilitato, mostra anche il contenuto del file `llms-full.txt`.
- **Effetto delle modifiche:** Questa schermata è per la verifica. Ti consente di rivedere il contenuto generato prima che sia live o dopo aver apportato modifiche, assicurandoti che soddisfi i tuoi requisiti.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Dopo aver apportato modifiche significative alle impostazioni del modulo o al catalogo prodotti, utilizza la schermata di anteprima per verificare che gli URL corretti siano inclusi ed esclusi.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Abilita generazione LLMS.txt | SÌ | Attiva/disattiva la funzione principale del modulo. |
| Configurazione Modulo | Tipo di file LLMS.txt | Statico | Scegli statico per le prestazioni, dinamico per gli aggiornamenti in tempo reale. |
| Configurazione Modulo | Genera llms-full.txt | SÌ | Fornisce un file più completo per l'AI. |
| Configurazione Modulo | Includi pagine prodotto | SÌ | Rende gli URL dei prodotti scopribili dall'AI. |
| Configurazione Modulo | Includi pagine categoria | SÌ | Rende gli URL delle categorie scopribili dall'AI. |
| Configurazione Modulo | Includi pagine CMS | SÌ | Rende le pagine informative scopribili dall'AI. |
| Configurazione Modulo | Includi pagine produttore/marchio | SÌ | Rende le pagine dei marchi scopribili dall'AI. |
| Configurazione Modulo | Includi pagine fornitore | NO | Generalmente non necessario per l'indicizzazione AI pubblica. |
| Configurazione Modulo | Includi pagina Nuovi Prodotti | SÌ | Evidenzia gli ultimi prodotti all'AI. |
| Configurazione Modulo | Includi pagina Migliori Vendite | SÌ | Promuove gli articoli più venduti all'AI. |
| Configurazione Modulo | Includi pagina Prezzi Scontati | SÌ | Evidenzia gli articoli scontati all'AI. |
| Configurazione Modulo | Includi pagina Contatti | SÌ | Fornisce informazioni di contatto all'AI. |
| Configurazione Modulo | Includi pagina Sitemap | SÌ | Aiuta l'AI a scoprire più contenuti. |
| Configurazione Modulo | Includi URL personalizzati | Utilizzare secondo necessità | Aggiungi URL specifici, non PrestaShop. |
| Configurazione Modulo | Escludi URL specifici | Utilizzare secondo necessità | Nascondi URL sensibili o irrilevanti. |
| Configurazione Modulo | Escludi prodotti per categoria | Utilizzare secondo necessità | Filtra i prodotti per categoria. |
| Configurazione Modulo | Escludi prodotti per produttore | Utilizzare secondo necessità | Filtra i prodotti per produttore. |
| Configurazione Modulo | Escludi prodotti per fornitore | Utilizzare secondo necessità | Filtra i prodotti per fornitore. |
| Configurazione Modulo | Escludi prodotti per caratteristica | Utilizzare secondo necessità | Filtra i prodotti per caratteristiche specifiche. |
| Configurazione Modulo | Escludi prodotti per attributo | Utilizzare secondo necessità | Filtra i prodotti per attributi specifici. |
| Configurazione Modulo | Escludi prodotti per fascia di prezzo | Utilizzare secondo necessità | Filtra i prodotti all'interno di una fascia di prezzo. |
| Configurazione Modulo | Escludi prodotti per quantità in magazzino | SÌ (<=0) | Nascondi i prodotti esauriti all'AI. |
| Configurazione Modulo | Escludi prodotti per visibilità | Utilizzare secondo necessità | Filtra i prodotti per visibilità PrestaShop. |
| Configurazione Modulo | Escludi prodotti per stato | SÌ (inattivo) | Nascondi i prodotti inattivi all'AI. |
| Configurazione Modulo | Escludi prodotti per data di aggiunta | Utilizzare secondo necessità | Filtra i prodotti per data di creazione. |
| Configurazione Modulo | Escludi prodotti per data di aggiornamento | Utilizzare secondo necessità | Filtra i prodotti per data dell'ultimo aggiornamento. |
| Configurazione Modulo | Escludi prodotti per ID prodotto specifici | Utilizzare secondo necessità | Escludi singoli prodotti per ID. |
| Configurazione Modulo | Pianificazione rigenerazione (Cron Job) | Giornaliero | Automatizza gli aggiornamenti di `llms.txt`. |
| Configurazione Modulo | Supporto Multistore | SÌ (se applicabile) | Abilita file distinti per ogni negozio. |
| Configurazione Modulo | Durata cache (minuti) | 60 (per dinamico) | Imposta la durata della cache per il file dinamico. |
| Configurazione Modulo | Abilita analisi e tracciamento bot | SÌ | Monitora l'attività dei crawler AI. |
| Configurazione Modulo | Pulsante Cancella Cache | Clicca secondo necessità | Forza la cancellazione della cache per aggiornamenti immediati. |
| Configurazione Modulo | Pulsante Genera LLMS.txt | Clicca secondo necessità | Genera manualmente il file `llms.txt`. |
| Pagina modifica prodotto | Escludi questo prodotto da LLMS.txt | Deselezionato | Sovrascrive le impostazioni globali per un singolo prodotto. |
| Pagina modifica categoria | Escludi questa categoria da LLMS.txt | Deselezionato | Sovrascrive le impostazioni globali per un'intera categoria. |
| Dashboard | Analisi del traffico bot | N/A | Monitora l'accesso dei bot AI. |
| Dashboard | Stato ultima generazione | N/A | Mostra lo stato del file `llms.txt`. |
| Anteprima | Visualizzazione contenuto LLMS.txt | N/A | Mostra il contenuto `llms.txt` generato. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Il mio file `llms.txt` non appare o non si aggiorna.**
R:

1.  **Controlla "Abilita generazione LLMS.txt":** Assicurati che sia impostato su SÌ nella configurazione del modulo.
2.  **Controlla il tipo di file:** Se impostato su "Statico", assicurati che il tuo server abbia i permessi di scrittura nella directory root di PrestaShop. Inoltre, clicca manualmente il pulsante "Genera LLMS.txt".
3.  **Cron Job:** Se utilizzi un cron job, verifica che sia configurato correttamente sul tuo hosting e che l'URL fornito dal modulo sia accessibile.
4.  **Svuota cache:** Vai su **Parametri avanzati > Prestazioni** in PrestaShop e svuota la cache di Smarty. Quindi, prova a rigenerare il file `llms.txt`.
5.  **Dashboard del modulo:** Controlla la dashboard del modulo per eventuali messaggi di errore durante la generazione.

**D: Ho apportato modifiche, ma il file `llms.txt` non le riflette.**
R:

1.  **Rigenera manualmente:** Clicca sul pulsante "Genera LLMS.txt" nella configurazione del modulo.
2.  **Tempistiche del Cron Job:** Se ti affidi a un cron job, ricorda che viene eseguito solo a intervalli programmati. Le tue modifiche appariranno dopo la prossima esecuzione programmata.
3.  **Cache:** Se stai utilizzando la generazione dinamica, il file `llms.txt` potrebbe essere memorizzato nella cache. Clicca sul pulsante "Svuota cache" nel modulo, oppure svuota la cache di PrestaShop in **Parametri avanzati > Prestazioni**.

**D: Come faccio a sapere se i bot AI stanno effettivamente utilizzando il mio file `llms.txt`?**
R: Abilita "Abilita analisi e tracciamento bot" nelle impostazioni del modulo. La dashboard del modulo ti mostrerà quindi le statistiche su quali user agent AI hanno acceduto al tuo file `llms.txt` e quando.

**D: Il file `llms.txt` è troppo grande o include troppi URL irrilevanti.**
R:

1.  **Rivedi le impostazioni di inclusione:** Esamina le opzioni "Includi..." e disabilita tutti i tipi di contenuto che non vuoi che l'AI indicizzi (ad esempio, Pagine fornitore).
2.  **Utilizza i filtri di esclusione:** Fai un uso estensivo dei filtri "Escludi prodotti per..." (Categoria, Scorte, Prezzo, ecc.) e "Escludi URL specifici" per affinare il contenuto.
3.  **Override per prodotto/categoria:** Per casi molto specifici, utilizza le caselle di controllo di esclusione sulle singole pagine di modifica del prodotto e della categoria.

**D: Il mio tema personalizzato non visualizza correttamente le funzionalità del modulo (ad esempio, campi extra nella pagina del prodotto).**
R: L'integrazione del modulo con le pagine prodotto/categoria è standard. Se riscontri problemi, è probabile che si tratti di un conflitto con il tuo tema personalizzato o con un altro modulo che modifica pesantemente i moduli di modifica prodotto/categoria.

1.  **Verifica i conflitti:** Disabilita temporaneamente altri moduli che modificano le pagine prodotto/categoria per vedere se il problema si risolve.
2.  **Override del tema:** Il tuo tema potrebbe avere override di template che impediscono la visualizzazione dei campi extra del modulo. Contatta lo sviluppatore del tuo tema o un esperto PrestaShop per indagare.
3.  **Svuota cache:** Svuota sempre la cache di PrestaShop dopo modifiche al tema o al modulo.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo LLMS.txt Generator Pro segue un'architettura standard per i moduli PrestaShop, sfruttando i principi MVC. Opera principalmente attraverso una classe modulo principale (`llmstxtpro/index.php`) per la configurazione e la gestione degli hook, e un set di classi dedicate (`classes/`) per la logica di business, la gestione dei dati e la generazione di file. I controller front-end gestiscono la distribuzione dinamica di `llms.txt` e l'esecuzione dei cron job. La configurazione è memorizzata in `ps_configuration` e tabelle personalizzate.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

Questi controller sono responsabili della distribuzione dei file `llms.txt` e `llms-full.txt` e della gestione delle richieste di cron job.

- `controllers/front/aicatalog.php`
  - **Nome classe e classe padre:** `LlmsTxtProAiCatalogModuleFrontController` che estende `ModuleFrontController`.
  - **Responsabilità:** Probabilmente gestisce richieste specifiche del catalogo AI, potenzialmente per formati di dati più strutturati oltre a `llms.txt`. Potrebbe servire una rappresentazione JSON o XML del catalogo per il consumo da parte dell'AI.
- `controllers/front/cron.php`
  - **Nome classe e classe padre:** `LlmsTxtProCronModuleFrontController` che estende `ModuleFrontController`.
  - **Responsabilità:** Questo controller è progettato per essere chiamato da un cron job lato server. Quando viene acceduto, attiva il processo di rigenerazione di `llms.txt` (e `llms-full.txt`) in base alla configurazione del modulo. Tipicamente restituisce un semplice messaggio di successo/fallimento.
- `controllers/front/index.php`
  - **Nome classe e classe padre:** `LlmsTxtProIndexModuleFrontController` che estende `ModuleFrontController`.
  - **Responsabilità:** Questo potrebbe essere un segnaposto o un punto di ingresso generico. Dati gli altri controller specifici, è meno probabile che abbia una funzione diretta e unica per la generazione di `llms.txt` stessa, ma potrebbe essere utilizzato per il routing generale del front-office del modulo o per informazioni.
- `controllers/front/llmsfull.php`
  - **Nome classe e classe padre:** `LlmsTxtProLlmsFullModuleFrontController` che estende `ModuleFrontController`.
  - **Responsabilità:** Quando il tipo di file `llms-full.txt` è impostato su dinamico, questo controller serve il contenuto del file `llms-full.txt`. Interroga il database e genera l'elenco completo di URL e dati associati.
- `controllers/front/llmstxt.php`
  - **Nome classe e classe padre:** `LlmsTxtProLlmsTxtModuleFrontController` che estende `ModuleFrontController`.
  - **Responsabilità:** Quando il tipo di file `llms.txt` è impostato su dinamico, questo controller serve il contenuto del file `llms.txt` standard. Interroga il database e genera l'elenco di URL in base alla configurazione del modulo e alle regole di esclusione.

#### Controller di amministrazione Back-Office

Il modulo non sembra avere controller di amministrazione personalizzati dedicati (`controllers/admin/`). Tutta la configurazione è gestita tramite il metodo `getContent()` del modulo principale.

### 4.3 Classi e modelli principali (`classes/`)

- `classes/index.php`
  - **Responsabilità:** Tipicamente un file vuoto per prevenire l'elenco delle directory, non una classe funzionale.
- `classes/LlmsTxtProAiCatalog.php`
  - **Responsabilità:** Probabilmente contiene la logica per generare un catalogo AI più strutturato (ad esempio, JSON-LD, markup schema.org) che potrebbe essere servito da `aicatalog.php`. Incapsulerebbe metodi per interrogare i dati di prodotti, categorie e CMS con formattazione specifica per l'AI.
- `classes/LlmsTxtProAnalytics.php`
  - **Responsabilità:** Gestisce la registrazione e il recupero dei dati di accesso dei bot AI. Interagirebbe con una tabella di database personalizzata per memorizzare lo user agent, il timestamp e le informazioni sul file acceduto (`llms.txt` o `llms-full.txt`). Fornisce metodi per riportare questi dati alla dashboard di amministrazione.
- `classes/LlmsTxtProConfig.php`
  - **Responsabilità:** Una classe helper per la gestione delle impostazioni di configurazione del modulo. Fornirebbe metodi statici per ottenere e impostare i valori di configurazione da `Configuration::get()` e `Configuration::updateValue()`, potenzialmente con valori predefiniti e casting di tipo.
- `classes/LlmsTxtProGenerator.php`
  - **Responsabilità:** Questa è la classe logica principale per la generazione del contenuto di `llms.txt` e `llms-full.txt`. Contiene metodi per:
    - Recuperare prodotti, categorie, pagine CMS, produttori, fornitori, ecc.
    - Applicare tutti i filtri di inclusione ed esclusione (per categoria, produttore, prezzo, scorte, URL personalizzati, ecc.).
    - Formattare gli URL secondo lo standard `llms.txt`.
    - Gestire la scrittura di file statici nella directory root.
    - Potenzialmente gestire la cache per la generazione dinamica.
- `classes/LlmsTxtProLogger.php`
  - **Responsabilità:** Una classe utility per la registrazione di eventi, avvisi o errori specifici del modulo. Potrebbe scrivere su un file di log personalizzato o integrarsi con il logger predefinito di PrestaShop. Utile per il debug dei problemi di generazione.

### 4.4 Risorse JavaScript (`views/js/`)

- `llmstxtpro/lib/searchTool/views/js/autocomplete.js`
  - **Ambito:** Back-office.
  - **Responsabilità:** Fornisce la funzionalità di autocompletamento per i campi di input nella configurazione amministrativa, probabilmente per la selezione di prodotti, categorie, produttori o URL specifici da escludere. Si lega ai campi di input ed effettua chiamate AJAX per recuperare suggerimenti.
- `llmstxtpro/views/js/adminLlmsTxtProDashboard.js`
  - **Ambito:** Back-office (schermata Dashboard).
  - **Responsabilità:** Gestisce la visualizzazione dinamica dei dati analitici sulla dashboard del modulo. Potrebbe utilizzare AJAX per recuperare le statistiche sul traffico bot da `LlmsTxtProAnalytics` e renderle utilizzando librerie di grafici o tabelle di dati.

### 4.5 Fogli di stile CSS (`views/css/`)

- `llmstxtpro/lib/searchTool/views/css/autocomplete.css`
  - **Ambito:** Back-office.
  - **Responsabilità:** Stila i menu a discesa e i suggerimenti di autocompletamento utilizzati nei moduli di configurazione amministrativa.
- `llmstxtpro/views/css/admin-config.css`
  - **Ambito:** Back-office (pagina di configurazione del modulo).
  - **Responsabilità:** Fornisce uno stile specifico per il modulo di configurazione principale del modulo, garantendo un layout coerente e facile da usare all'interno del Back Office di PrestaShop.
- `llmstxtpro/views/css/admin-dashboard.css`
  - **Ambito:** Back-office (schermata Dashboard).
  - **Responsabilità:** Stila gli elementi della dashboard, inclusi grafici, tabelle e indicatori di stato per l'analisi del traffico bot e lo stato di generazione.
- `llmstxtpro/views/css/admin-searchtool.css`
  - **Ambito:** Back-office.
  - **Responsabilità:** Stile generale per i componenti dell'interfaccia utente relativi alla ricerca all'interno dell'amministrazione, potenzialmente condiviso con `autocomplete.css` o per altre interfacce di ricerca/filtro.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**: La descrizione del modulo non elenca esplicitamente i template hook, suggerendo che la sua presenza nel front-office sia principalmente attraverso il file `llms.txt` stesso, non elementi visivi.
-   **Template admin (`views/templates/admin/`)**:
    -   `llmstxtpro/views/templates/admin/category-extra.tpl`
        -   **Scopo:** Renderizza la casella di controllo "Escludi questa categoria da LLMS.txt" e tutti i campi correlati nella pagina di modifica della categoria di PrestaShop. Questo template è probabilmente agganciato a `displayAdminProductsExtra` o simili.
    -   `llmstxtpro/views/templates/admin/configure.tpl`
        -   **Scopo:** Il template principale per la pagina di configurazione del modulo (metodo `getContent()`). Renderizza tutte le impostazioni generali, le opzioni di inclusione/esclusione, le impostazioni avanzate e i pulsanti di azione.
    -   `llmstxtpro/views/templates/admin/dashboard.tpl`
        -   **Scopo:** Renderizza la dashboard di analisi del modulo, visualizzando il traffico dei bot, lo stato di generazione e potenzialmente i log degli errori.
    -   `llmstxtpro/views/templates/admin/preview.tpl`
        -   **Scopo:** Renderizza il contenuto dei file `llms.txt` e `llms-full.txt` generati per la revisione all'interno del Back Office.
    -   `llmstxtpro/views/templates/admin/product-extra.tpl`
        -   **Scopo:** Renderizza la casella di controllo "Escludi questo prodotto da LLMS.txt" e tutti i campi correlati nella pagina di modifica del prodotto di PrestaShop. Questo template è probabilmente agganciato a `displayAdminProductsExtra` o simili.
-   **Template front-office (`views/templates/front/`)**: Nessuno esplicitamente elencato, rafforzando il fatto che l'interazione front-office del modulo è principalmente machine-to-machine tramite il file `llms.txt`.
-   `llmstxtpro/lib/searchTool/views/scripts.tpl`
    -   **Scopo:** Probabilmente include risorse JavaScript e CSS per lo strumento di ricerca (ad esempio, autocomplete.js, autocomplete.css) all'interno del contesto amministrativo.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    -   `ps_configuration`: Memorizza tutte le impostazioni di configurazione del modulo (ad esempio, `LLMSTXTPRO_ENABLED`, `LLMSTXTPRO_FILE_TYPE`, `LLMSTXTPRO_INCLUDE_PRODUCTS`, `LLMSTXTPRO_EXCLUDE_URLS`, ecc.).
    -   `ps_llmstxtpro_product_override`: Una tabella personalizzata per memorizzare le impostazioni di esclusione per prodotto. (Probabilmente `id_product`, `excluded`).
    -   `ps_llmstxtpro_category_override`: Una tabella personalizzata per memorizzare le impostazioni di esclusione per categoria. (Probabilmente `id_category`, `excluded`).
    -   `ps_llmstxtpro_analytics_log`: Una tabella personalizzata per memorizzare i log di accesso dei bot (ad esempio, `id_llmstxtpro_analytics_log`, `user_agent`, `access_time`, `file_type`).
    -   `ps_llmstxtpro_urls`: Potenzialmente una tabella per memorizzare nella cache gli URL generati per le prestazioni, specialmente per la generazione di file statici. (Probabilmente `id_url`, `url`, `file_type`, `date_add`).
-   **Tabella degli hook registrati**:

| Nome Hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Prima che il controller admin renderizzi il suo contenuto. | Inietta CSS/JS del modulo per la configurazione admin, la dashboard e i campi extra di prodotto/categoria. |
| `displayAdminProductsExtra` | Nella pagina di modifica del prodotto. | Renderizza la casella di controllo "Escludi questo prodotto da LLMS.txt". |
| `displayAdminCategoriesExtra` | Nella pagina di modifica della categoria. | Renderizza la casella di controllo "Escludi questa categoria da LLMS.txt". |
| `actionModuleInstall` | Durante l'installazione del modulo. | Crea tabelle del database, imposta valori di configurazione predefiniti. |
| `actionModuleUninstall` | Durante la disinstallazione del modulo. | Elimina tabelle del database e valori di configurazione. |
| `displayHeader` | Nella sezione `<head>` delle pagine front-office. | (Meno probabile per questo modulo, ma potrebbe essere usato per meta tag o link specifici per l'AI se necessario). |
| `displayRightColumn` | Nella colonna destra delle pagine front-office. | (Non direttamente rilevante per la generazione di `llms.txt`). |
| `displayFooter` | Nel footer delle pagine front-office. | (Non direttamente rilevante per la generazione di `llms.txt`). |
| `actionProductUpdate` | Dopo l'aggiornamento di un prodotto. | Potenzialmente attiva una cancellazione della cache o segnala per la rigenerazione se si utilizza `llms.txt` dinamico. |
| `actionCategoryUpdate` | Dopo l'aggiornamento di una categoria. | Potenzialmente attiva una cancellazione della cache o segnala per la rigenerazione. |
| `actionObjectProductAddAfter` | Dopo l'aggiunta di un nuovo prodotto. | Potenzialmente attiva una cancellazione della cache o segnala per la rigenerazione. |
| `actionObjectCategoryAddAfter` | Dopo l'aggiunta di una nuova categoria. | Potenzialmente attiva una cancellazione della cache o segnala per la rigenerazione. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, accedi al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere commercianti e sviluppatori con qualsiasi problema o domanda riguardante il modulo LLMS.txt Generator Pro.
