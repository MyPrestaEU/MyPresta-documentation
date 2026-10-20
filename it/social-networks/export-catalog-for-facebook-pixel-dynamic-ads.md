---
title: "Esporta catalogo per annunci dinamici Facebook Pixel - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Esporta catalogo per annunci dinamici Facebook Pixel' di MyPresta.eu."
sidebar:
  label: "Esporta catalogo per annunci dinamici Facebook Pixel - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Export catalog for facebook pixel dynamic ads su MyPresta.eu](https://mypresta.eu/modules/social-networks/export-catalog-for-facebook-pixel-dynamic-ads.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/social-networks/export-catalog-for-facebook-pixel-dynamic-ads/)
>
> ---


# Esporta catalogo per annunci dinamici Facebook Pixel

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Assicurati che il tuo server abbia memoria e tempo di esecuzione sufficienti per generare feed di prodotti di grandi dimensioni se hai molti prodotti.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

La configurazione del modulo è gestita principalmente tramite una schermata di amministrazione dedicata, che ti consente di definire come viene esportato il tuo catalogo prodotti.

### 2.1 Schermata di configurazione principale del modulo (Back Office > Moduli > Gestione moduli > Configura)

Questa schermata fornisce le impostazioni principali per il modulo, consentendoti di generare e gestire i tuoi feed di prodotti.

**Posizione del menu:** Back Office > Moduli > Gestione moduli > Cerca "Esporta catalogo per annunci dinamici Facebook Pixel" > Clicca su "Configura".

#### Impostazioni generali e generazione del feed

Questa sezione è dove definisci i parametri principali per il tuo feed di prodotti.

- **Seleziona lingua per l'esportazione:**

  - **Cosa fa questa impostazione:** Determina quali nomi di prodotto, descrizioni e altri campi di testo della lingua verranno inclusi nel feed esportato.
  - **Effetto della modifica di questa impostazione:**
    - *Se impostato su Inglese:* Il tuo feed conterrà i dettagli del prodotto in inglese.
    - *Se impostato su Francese:* Il tuo feed conterrà i dettagli del prodotto in francese.
  - **Valore consigliato:** La lingua principale del tuo pubblico di destinazione per gli annunci di Facebook. Se pubblichi annunci in più lingue, dovrai generare feed separati per ogni lingua.
  - **Scenario / esempio del commerciante:** Se ti rivolgi principalmente a clienti negli USA, selezioneresti "Inglese". Se ti rivolgi anche a clienti in Francia, genereresti un feed separato con "Francese" selezionato.
- **Seleziona valuta per l'esportazione:**

  - **Cosa fa questa impostazione:** Determina quali prezzi della valuta verranno inclusi nel feed esportato.
  - **Effetto della modifica di questa impostazione:**
    - *Se impostato su USD:* Tutti i prezzi dei prodotti nel feed saranno in dollari USA.
    - *Se impostato su EUR:* Tutti i prezzi dei prodotti nel feed saranno in Euro.
  - **Valore consigliato:** La valuta principale del tuo pubblico di destinazione per gli annunci di Facebook. Come per la lingua, se ti rivolgi a più valute, avrai bisogno di feed separati.
  - **Scenario / esempio del commerciante:** Se il tuo negozio vende sia in USD che in CAD, e vuoi pubblicare annunci di Facebook per i tuoi clienti canadesi, selezioneresti "Dollaro canadese" per quel feed specifico.
- **Esporta solo prodotti attivi:**

  - **Cosa fa questa impostazione:** Controlla se solo i prodotti attualmente abilitati e visibili nel tuo negozio sono inclusi nel feed.
  - **Effetto della modifica di questa impostazione:**
    - *Se abilitato (SÌ):* Verranno esportati solo i prodotti attivi nel tuo negozio PrestaShop. Ciò impedisce la visualizzazione di annunci per articoli esauriti o fuori produzione.
    - *Se disabilitato (NO):* Tutti i prodotti, inclusi quelli inattivi, potrebbero essere esportati. Questo non è generalmente consigliato per le campagne pubblicitarie in tempo reale.
  - **Valore consigliato:** **SÌ**. Ciò garantisce che i tuoi annunci siano sempre pertinenti e si colleghino a prodotti disponibili.
  - **Scenario / esempio del commerciante:** Hai prodotti stagionali attualmente inattivi. L'abilitazione di questa opzione garantisce che non vengano visualizzati nei tuoi annunci di Facebook finché non li riattivi.
- **Esporta solo prodotti in stock:**

  - **Cosa fa questa impostazione:** Determina se solo i prodotti con stock disponibile sono inclusi nel feed.
  - **Effetto della modifica di questa impostazione:**
    - *Se abilitato (SÌ):* Verranno esportati solo i prodotti attualmente in stock.
    - *Se disabilitato (NO):* I prodotti esauriti potrebbero essere esportati, portando potenzialmente a una scarsa esperienza del cliente se cliccano su un annuncio per un articolo non disponibile.
  - **Valore consigliato:** **SÌ**. Ciò impedisce ai clienti di cliccare su annunci per prodotti che non possono acquistare, riducendo la frustrazione e la spesa pubblicitaria sprecata.
  - **Scenario / esempio del commerciante:** Un articolo popolare è appena andato esaurito. Con questa opzione abilitata, verrà automaticamente rimosso dal tuo feed di Facebook finché non sarà rifornito.
- **Esporta combinazioni di prodotti (varianti):**

  - **Cosa fa questa impostazione:** Controlla se le singole combinazioni di prodotti (ad esempio, una T-shirt in diverse taglie e colori) vengono esportate come articoli separati nel feed.
  - **Effetto della modifica di questa impostazione:**
    - *Se abilitato (SÌ):* Ogni combinazione (ad esempio, "T-shirt rossa - Piccola", "T-shirt rossa - Media") apparirà come un articolo unico nel feed, con la propria immagine, prezzo e link. Questo è fondamentale per gli annunci dinamici per mostrare la variante esatta che un cliente ha visualizzato.
    - *Se disabilitato (NO):* Verrà esportato solo il prodotto principale, senza combinazioni individuali. Ciò limita la granularità dei tuoi annunci dinamici.
  - **Valore consigliato:** **SÌ**. Questo è altamente raccomandato per la maggior parte dei negozi, in particolare quelli che vendono abbigliamento, elettronica o qualsiasi prodotto con varianti, per garantire l'esperienza pubblicitaria più accurata e personalizzata.
  - **Scenario / esempio del commerciante:** Un cliente visualizza un "Vestito blu - Grande" sul tuo sito. Se le combinazioni vengono esportate, Facebook può mostrare loro un annuncio specifico per quel "Vestito blu - Grande".
- **Identificazione del prodotto (campo ID):**

  - **Cosa fa questa impostazione:** Specifica quale campo ID di PrestaShop deve essere utilizzato come identificatore univoco per i prodotti nel feed di Facebook (campo `id`).
  - **Effetto della modifica di questa impostazione:**
    - *ID prodotto:* Utilizza l'`id_product` standard di PrestaShop.
    - *EAN13:* Utilizza il codice a barre EAN13.
    - *UPC:* Utilizza il codice a barre UPC.
    - *Riferimento:* Utilizza il codice di riferimento interno del prodotto.
  - **Valore consigliato:** **ID prodotto** è generalmente l'opzione più sicura e affidabile in quanto è sempre univoca e interna a PrestaShop. Se utilizzi costantemente EAN13/UPC per tutti i prodotti e le combinazioni, anche questi possono funzionare.
  - **Scenario / esempio del commerciante:** Hai un'integrazione personalizzata che si basa su `id_product` per il tracciamento. L'utilizzo di "ID prodotto" qui garantisce la coerenza.
- **Campo Categoria Prodotto:**

  - **Cosa fa questa impostazione:** Determina quali informazioni sulla categoria vengono inviate a Facebook.
  - **Effetto della modifica di questa impostazione:**
    - *Categoria PrestaShop predefinita:* Utilizza il nome della categoria principale del prodotto.
    - *Categoria prodotto Google:* Utilizza la Categoria prodotto Google (se assegnata). Questa è spesso preferita da Facebook per una migliore corrispondenza.
  - **Valore consigliato:** **Categoria prodotto Google** se le hai assegnate. Altrimenti, "Categoria PrestaShop predefinita".
  - **Scenario / esempio del commerciante:** Vendi "T-shirt" in PrestaShop, ma la Categoria prodotto Google è "Abbigliamento e accessori > Abbigliamento > Camicie e top > T-shirt". L'utilizzo della categoria Google fornisce dati più specifici a Facebook.
- **Campo Marca Prodotto:**

  - **Cosa fa questa impostazione:** Seleziona quale campo dai dati del tuo prodotto deve essere utilizzato per l'attributo `brand` nel feed di Facebook.
  - **Effetto della modifica di questa impostazione:**
    - *Nome produttore:* Utilizza il produttore assegnato al prodotto in PrestaShop.
    - *Nome fornitore:* Utilizza il fornitore assegnato al prodotto.
  - **Valore consigliato:** **Nome produttore**. Questo è il campo più comune e logico per "marca".
  - **Scenario / esempio del commerciante:** Vendi scarpe Nike. Selezionando "Nome produttore" popolerà correttamente "Nike" come marca nel tuo feed.
- **Campo Tipo Prodotto:**

  - **Cosa fa questa impostazione:** Specifica quali informazioni devono essere utilizzate per il campo `product_type` nel feed di Facebook.
  - **Effetto della modifica di questa impostazione:**
    - *Categoria PrestaShop predefinita:* Utilizza il nome della categoria principale del prodotto.
    - *Categoria prodotto Google:* Utilizza la Categoria prodotto Google (se assegnata).
  - **Valore consigliato:** **Categoria prodotto Google** se disponibile, altrimenti "Categoria PrestaShop predefinita". Questo aiuta Facebook a capire il tipo di prodotto.
  - **Scenario / esempio del commerciante:** Per un prodotto in "Elettronica > Smartphone", la Categoria prodotto Google potrebbe essere "Elettronica > Comunicazioni > Telefonia > Telefoni cellulari".
- **Campo Immagine Prodotto:**

  - **Cosa fa questa impostazione:** Determina quale URL dell'immagine viene utilizzato per il `image_link` nel feed.
  - **Effetto della modifica di questa impostazione:**
    - *Immagine prodotto predefinita:* Utilizza l'immagine principale associata al prodotto.
    - *Immagine combinazione (se disponibile):* Se si esportano combinazioni, questa utilizzerà l'immagine specifica assegnata a quella combinazione, altrimenti l'immagine predefinita del prodotto.
  - **Valore consigliato:** **Immagine combinazione (se disponibile)**. Ciò garantisce che se un cliente visualizza una maglietta rossa, l'annuncio mostri una maglietta rossa, non solo l'immagine generica del prodotto.
  - **Scenario / esempio del commerciante:** Hai un prodotto con più combinazioni di colore, ognuna con la propria immagine. Questa impostazione garantisce che l'immagine del colore corretto venga visualizzata nell'annuncio.
- **Campo Descrizione Prodotto:**

  - **Cosa fa questa impostazione:** Seleziona quale campo di descrizione da PrestaShop (`description` o `short_description`) viene utilizzato per l'attributo `description` nel feed di Facebook.
  - **Effetto della modifica di questa impostazione:**
    - *Descrizione:* Esporta la descrizione completa e dettagliata del prodotto.
    - *Descrizione breve:* Esporta il breve riepilogo del prodotto.
  - **Valore consigliato:** **Descrizione**. Facebook di solito preferisce una descrizione più dettagliata per un migliore contesto dell'annuncio.
  - **Scenario / esempio del commerciante:** Vuoi fornire quante più informazioni possibili nei tuoi annunci. L'utilizzo della descrizione completa lo garantisce.
- **Campo Descrizione Breve Prodotto:**

  - **Cosa fa questa impostazione:** Seleziona quale campo di descrizione da PrestaShop (`description` o `short_description`) viene utilizzato per l'attributo `short_description` nel feed di Facebook.
  - **Effetto della modifica di questa impostazione:**
    - *Descrizione:* Esporta la descrizione completa e dettagliata del prodotto.
    - *Descrizione breve:* Esporta il breve riepilogo del prodotto.
  - **Valore consigliato:** **Descrizione breve**. Questo è utile se il feed di Facebook richiede sia una descrizione lunga che una breve, o se preferisci un riepilogo conciso per determinati formati di annuncio.
  - **Scenario / esempio del commerciante:** Vuoi un riepilogo conciso per il campo `short_description` nel tuo feed.
- **Delimitatore CSV:**

  - **Cosa fa questa impostazione:** Specifica il carattere utilizzato per separare i valori nel file CSV generato (ad esempio, virgola, punto e virgola).
  - **Effetto della modifica di questa impostazione:**
    - *Virgola (,):* Formato CSV standard.
    - *Punto e virgola (;):* Comune in alcune località europee.
  - **Valore consigliato:** **Virgola (,)**. Questo è il delimitatore più ampiamente accettato per i file CSV, incluso da Facebook.
  - **Scenario / esempio del commerciante:** Se lo strumento di importazione di Facebook specifica un delimitatore punto e virgola, lo cambieresti qui. Altrimenti, attieniti alla virgola.
- **Elimina immagini dal feed:**

  - **Cosa fa questa impostazione:** Se abilitata, il modulo rimuoverà i link delle immagini dal feed generato.
  - **Effetto della modifica di questa impostazione:**
    - *Se abilitato (SÌ):* Le colonne `image_link` e `additional_image_link` nel feed saranno vuote. Questo generalmente NON è raccomandato in quanto le immagini sono cruciali per gli annunci dinamici.
    - *Se disabilitato (NO):* I link delle immagini saranno inclusi nel feed.
  - **Valore consigliato:** **NO**. Le immagini sono fondamentali per gli annunci visivi.
  - **Scenario / esempio del commerciante:** Questa impostazione è raramente utile a meno che tu non abbia una configurazione molto specifica e avanzata in cui le immagini sono gestite interamente separatamente.

#### Escludi prodotti

Questa sezione ti consente di impedire che prodotti specifici vengano inclusi nel tuo feed di Facebook.

- **Escludi prodotti per ID:**
  - **Cosa fa questa impostazione:** Ti consente di inserire un elenco di ID prodotto separati da virgole che non desideri vengano visualizzati nel tuo catalogo prodotti di Facebook.
  - **Effetto della modifica di questa impostazione:**
    - *Prodotti elencati qui:* Saranno completamente omessi dal feed generato.
  - **Valore consigliato:** Lascia vuoto a meno che tu non abbia prodotti specifici che non vuoi mai pubblicizzare (ad esempio, prodotti di test interni, servizi non adatti agli annunci dinamici).
  - **Scenario / esempio del commerciante:** Vendi sia prodotti fisici che servizi digitali. Potresti escludere i prodotti di servizi digitali dal feed in quanto non si adattano al formato degli annunci dinamici.

#### Pulsante Genera Feed

- **Cosa fa questo pulsante:** Avvia il processo di generazione del file CSV del catalogo prodotti in base a tutte le impostazioni che hai configurato sopra.
- **Effetto del clic su questo pulsante:** Il modulo elaborerà i tuoi prodotti e creerà un file CSV scaricabile. A seconda del numero di prodotti, questo potrebbe richiedere del tempo.
- **Azione consigliata:** Clicca su questo pulsante dopo aver rivisto e salvato tutte le impostazioni desiderate.
- **Scenario / esempio del commerciante:** Dopo aver apportato modifiche alle descrizioni dei tuoi prodotti o aver aggiunto nuovi prodotti, cliccheresti su questo per generare un feed aggiornato per Facebook.

#### Pulsante Scarica Feed

- **Cosa fa questo pulsante:** Ti consente di scaricare il file CSV del catalogo prodotti generato più di recente sul tuo computer.
- **Effetto del clic su questo pulsante:** Il tuo browser scaricherà il file `facebook_products.csv`.
- **Azione consigliata:** Scarica il file dopo la generazione e poi caricalo sul tuo Facebook Business Manager.
- **Scenario / esempio del commerciante:** Una volta generato il feed, lo scarichi e poi navighi su Facebook Business Manager > Cataloghi > Origini dati per caricare il CSV.

### 2.2 Schermata di amministrazione dedicata: AdminExportProductsFeedController

Questa è la schermata di amministrazione principale in cui gestisci l'effettiva generazione del feed di prodotti e rivedi i dati che verranno esportati.

**Posizione del menu:** Back Office > Moduli > Gestione moduli > Configura "Esporta catalogo per annunci dinamici Facebook Pixel" > (Questa schermata è l'interfaccia di configurazione principale stessa, spesso accessibile direttamente dopo aver cliccato su "Configura").

Questa schermata presenta un'interfaccia a griglia o un modulo con varie opzioni per controllare l'output del tuo feed di prodotti. I campi elencati di seguito rappresentano i punti dati che possono essere inclusi nel tuo catalogo prodotti di Facebook.

- **ID:** L'identificatore univoco per il prodotto (basato sulla tua impostazione "Identificazione del prodotto").
- **item\_group\_id:** Utilizzato per le combinazioni di prodotti per raggrupparle sotto un singolo prodotto padre.
- **Titolo:** Il nome del prodotto.
- **Descrizione breve:** Il breve riepilogo del prodotto.
- **Descrizione:** La descrizione completa del prodotto.
- **Override:** (Probabilmente un'impostazione interna del modulo, non esportata direttamente su Facebook).
- **Disponibilità:** Indica se il prodotto è in stock (`in stock`, `out of stock`).
- **Inventario:** La quantità di stock attuale.
- **Condizione:** La condizione del prodotto (ad esempio, `new`, `used`, `refurbished`).
- **Link immagine:** L'URL dell'immagine principale del prodotto.
- **Additional\_image\_link:** URL di immagini aggiuntive del prodotto.
- **Prezzo:** Il prezzo attuale del prodotto.
- **sale\_price:** Il prezzo di vendita del prodotto (se applicabile).
- **Marca:** La marca del prodotto (produttore).
- **Link:** L'URL diretto alla pagina del prodotto sul tuo negozio.
- **Categoria prodotto Google:** La Categoria prodotto Google assegnata al prodotto.
- **product\_type:** Il tipo di prodotto (ad esempio, nome della categoria).
- **gender:** Per l'abbigliamento, il genere di destinazione (ad esempio, `male`, `female`, `unisex`).
- **size:** Per l'abbigliamento, la taglia del prodotto.
- **age\_group:** Per l'abbigliamento, la fascia d'età di destinazione (ad esempio, `newborn`, `infant`, `toddler`, `kids`, `adult`).

**Azioni e impostazioni disponibili:**
Su questa schermata, troverai le varie opzioni di configurazione dettagliate nella sezione 4.1. La "Tabella / Entità gestita" qui si riferisce alla tabella virtuale dei dati del prodotto che il modulo costruisce prima dell'esportazione. Non c'è una tabella di database diretta gestita da questo controller specifico, ma piuttosto elabora e prepara i dati dalle tue tabelle di prodotti PrestaShop esistenti.

**Effetto delle modifiche:**
Qualsiasi modifica apportata alle impostazioni su questa schermata (ad esempio, la selezione di una lingua diversa, l'abilitazione/disabilitazione dell'esportazione delle combinazioni) altererà direttamente il contenuto e il formato del file CSV generato quando si fa clic sul pulsante "Genera feed".

**Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

1. Periodicamente (ad esempio, quotidianamente o settimanalmente, a seconda della frequenza con cui cambia il tuo catalogo prodotti) visita questa pagina di configurazione.
2. Assicurati che le impostazioni di lingua, valuta e stock/prodotti attivi siano corrette.
3. Clicca su "Genera feed" per creare un CSV aggiornato.
4. Scarica il CSV generato.
5. Carica questo nuovo CSV su Facebook Business Manager per aggiornare il tuo catalogo prodotti. Facebook offre anche opzioni per pianificare recuperi automatici da un URL, che possono essere configurati una volta che hai un URL di feed stabile (spesso fornito dal modulo o dalla configurazione del tuo server).

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| **Configurazione modulo** | Seleziona lingua per l'esportazione | La tua lingua principale | Determina la lingua dei nomi/descrizioni dei prodotti nel feed. |
|  | Seleziona valuta per l'esportazione | La tua valuta principale | Determina la valuta dei prezzi nel feed. |
|  | Esporta solo prodotti attivi | SÌ | Include solo prodotti attivi, prevenendo annunci per articoli non disponibili. |
|  | Esporta solo prodotti in stock | SÌ | Include solo prodotti in stock, prevenendo annunci per articoli esauriti. |
|  | Esporta combinazioni di prodotti | SÌ | Esporta ogni variazione di prodotto (taglia, colore) come un articolo unico per annunci granulari. |
|  | Identificazione del prodotto (campo ID) | ID prodotto | Definisce l'identificatore univoco per i prodotti nel feed. |
|  | Campo Categoria Prodotto | Categoria prodotto Google (se disponibile) | Specifica i dati della categoria per Facebook. |
|  | Campo Marca Prodotto | Nome produttore | Specifica i dati della marca per Facebook. |
|  | Campo Tipo Prodotto | Categoria prodotto Google (se disponibile) | Specifica i dati del tipo di prodotto per Facebook. |
|  | Campo Immagine Prodotto | Immagine combinazione (se disponibile) | Garantisce l'immagine corretta per le varianti del prodotto. |
|  | Campo Descrizione Prodotto | Descrizione | Utilizza la descrizione completa del prodotto per il feed. |
|  | Campo Descrizione Breve Prodotto | Descrizione breve | Utilizza la descrizione breve del prodotto per il feed. |
|  | Delimitatore CSV | Virgola (,) | Carattere che separa i valori nel file CSV. |
|  | Elimina immagini dal feed | NO | Include i link delle immagini nel feed (essenziale per gli annunci). |
|  | Escludi prodotti per ID | Vuoto | Elenco di ID prodotto separati da virgole da escludere dal feed. |
|  | Pulsante Genera Feed | Clicca dopo aver finalizzato le impostazioni | Crea il file CSV del catalogo prodotti. |
|  | Pulsante Scarica Feed | Clicca dopo la generazione | Scarica il file CSV sul tuo computer. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Il mio file di feed generato è vuoto o contiene pochissimi prodotti.**
R:

- **Controlla "Esporta solo prodotti attivi" e "Esporta solo prodotti in stock":** Assicurati che queste opzioni non siano eccessivamente restrittive se ti aspetti molti prodotti.
- **Controlla la lingua e la valuta selezionate:** Assicurati che esistano prodotti per la lingua selezionata e che abbiano prezzi nella valuta selezionata.
- **Verifica la visibilità del prodotto:** I tuoi prodotti sono effettivamente visibili nel contesto del negozio selezionato (se hai abilitato il multi-negozio)?
- **Svuota la cache di Smarty:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache". A volte i vecchi dati possono interferire.

**D: Facebook sta rifiutando il mio feed o mostrando errori.**
R:

- **Controlla il delimitatore CSV:** Assicurati che corrisponda a quello che Facebook si aspetta (di solito una virgola).
- **Rivedi i messaggi di errore di Facebook:** Facebook Business Manager fornisce rapporti di errore dettagliati. Presta molta attenzione a quali campi stanno causando problemi (ad esempio, link immagine mancanti, prezzi non validi).
- **Verifica i link delle immagini:** Assicurati che le immagini dei tuoi prodotti siano accessibili pubblicamente e che gli URL siano corretti. Se hai SSL (HTTPS), assicurati che anche i link delle immagini siano HTTPS.
- **Controlla i caratteri speciali:** A volte caratteri insoliti nei nomi o nelle descrizioni dei prodotti possono causare problemi di analisi.
- **Assicurati che gli ID siano univoci:** L'impostazione "Identificazione del prodotto" è cruciale. Ogni elemento nel feed (specialmente le combinazioni) necessita di un `id` univoco.

**D: Le immagini dei miei prodotti non vengono visualizzate nel feed di Facebook.**
R:

- **Controlla l'impostazione "Elimina immagini dal feed":** Assicurati che sia impostata su **NO**.
- **Verifica gli URL delle immagini:** Apri alcuni link delle immagini dal CSV generato nel tuo browser. Si caricano correttamente? Sono accessibili dall'esterno della tua rete?
- **Immagini delle combinazioni:** Se stai utilizzando immagini delle combinazioni, assicurati che siano correttamente assegnate alle combinazioni dei tuoi prodotti in PrestaShop.

**D: Con quale frequenza dovrei generare e caricare un nuovo feed?**
R:

- Dipende dalla frequenza con cui cambia il tuo catalogo prodotti.
- **Giornaliero:** Consigliato per la maggior parte dei negozi, soprattutto se hai frequenti modifiche di stock, aggiornamenti di prezzo o nuove aggiunte di prodotti.
- **Settimanale:** Accettabile per i negozi con un catalogo molto stabile.
- **Recupero automatico:** La migliore pratica è configurare Facebook per recuperare automaticamente il feed da un URL. Questo modulo genera il feed su richiesta, quindi potresti aver bisogno di un cron job per attivare la generazione e rendere il file disponibile a un URL coerente affinché Facebook lo recuperi.

**D: Il modulo non compare nell'elenco dei miei moduli o non riesco a configurarlo.**
R:

- **Ricarica:** Prova a ricaricare il file ZIP del modulo tramite il Gestore moduli.
- **Controlla i permessi:** Assicurati che la cartella del modulo (`/modules/pixelfeed/`) e il suo contenuto abbiano i permessi di file corretti (solitamente 755 per le cartelle, 644 per i file).
- **Log degli errori:** Controlla la modalità di debug di PrestaShop e i log degli errori del server per eventuali errori PHP durante l'installazione o la configurazione.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata del modulo "Esporta catalogo per annunci dinamici Facebook Pixel" per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo segue un modello MVC (Model-View-Controller) standard di PrestaShop, concentrandosi principalmente sulla funzionalità amministrativa per generare un feed di prodotti. Sfrutta le classi `Product` e `Combination` di base di PrestaShop per estrarre i dati, quindi formatta questi dati in un file CSV compatibile con le specifiche del catalogo di annunci dinamici di Facebook. Il file principale del modulo (`index.php`) funge da punto di ingresso per la configurazione, mentre i controller amministrativi dedicati gestiscono la logica complessa di estrazione dei dati e generazione del feed. Sono presenti controller frontali, probabilmente per servire il feed generato o per richieste AJAX specifiche.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

- `controllers/front/feed.php`
  - **Nome classe:** `PixelfeedFeedModuleFrontController` (o simile, che estende `ModuleFrontController`)
  - **Responsabilità:** Questo controller è probabilmente responsabile di servire il file CSV del feed generato tramite un URL pubblico. Gestirebbe le richieste a una rotta specifica (ad esempio, `tuonegozio.com/module/pixelfeed/feed`) e produrrebbe direttamente il contenuto CSV. Questo è cruciale per i recuperi pianificati di Facebook.
- `controllers/front/index.php`
  - **Nome classe:** `PixelfeedIndexModuleFrontController` (o simile, che estende `ModuleFrontController`)
  - **Responsabilità:** Questo potrebbe essere un segnaposto o un controller per un'azione front-office molto specifica, non correlata al feed, sebbene la funzione principale del modulo sia la generazione del feed nel back-office. Potrebbe potenzialmente gestire richieste AJAX relative allo stato del feed o altre interazioni minori.

#### Controller Admin Back-Office

- `controllers/admin/AdminExportProductsFeed.php`
  - **Nome classe:** `AdminExportProductsFeedController` (che estende `ModuleAdminController`)
  - **Nome scheda:** Questo controller è il cuore dell'interfaccia amministrativa del modulo. È la schermata di configurazione principale in cui i commercianti interagiscono con le impostazioni e attivano la generazione del feed.
  - **Entità gestita:** Non gestisce direttamente una singola entità `ObjectModel`, ma piuttosto orchestra il recupero e l'elaborazione dei dati `Product` e `Combination` dal core di PrestaShop.
  - **Funzionalità chiave:**
    - Gestisce la visualizzazione del modulo di configurazione (`renderForm`).
    - Elabora le sottomissioni del modulo (`postProcess`) per salvare le impostazioni del modulo (ad esempio, lingua, valuta, opzioni di esportazione).
    - Attiva la logica di estrazione dei dati e generazione CSV.
    - Gestisce l'esclusione dei prodotti.
    - I campi del modulo e le colonne elencate nel dossier del modulo (`ID`, `item_group_id`, `Title`, ecc.) rappresentano la *struttura di output* del feed, non necessariamente campi di input diretti nel modulo di amministrazione, sebbene molte impostazioni influenzino queste colonne di output.
    - Chiavi di configurazione associate: `pf_tree`, `PS_LANG_DEFAULT`, `PS_CURRENCY_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`, `pf_pixelfeed_products`, `pf_remember_settings`, `pf_export_not_group_combinations`, `pf_export_active`, `pf_export_instock`, `pf_export_identification`, `pf_export_category`, `pf_export_manufacturers_default`, `pf_export_type`, `pf_export_img`, `pf_export_manufacturers`, `pf_export_description_what`, `pf_export_short_description_what`, `pf_export_suppliers`, `pf_export_delimiter`, `pf_delete_images`. Queste sono le chiavi `Configuration` utilizzate per memorizzare le impostazioni del modulo.
- `controllers/admin/index.php`
  - **Nome classe:** `PixelfeedAdminIndexController` (o simile, che estende `ModuleAdminController`)
  - **Nome scheda:** Questo potrebbe essere un controller amministrativo secondario, potenzialmente per una dashboard o una vista di gestione più semplice, oppure potrebbe essere un file legacy. Dato che `AdminExportProductsFeedController` gestisce la logica principale, questo `index.php` potrebbe essere un reindirizzamento o una pagina di atterraggio molto semplice all'interno della sezione amministrativa.

### 4.3 Classi e modelli principali (`classes/`)

Il dossier del modulo indica l'assenza di classi personalizzate nella directory `classes/`. Ciò implica che la logica principale per l'estrazione dei dati e la generazione del feed è probabilmente contenuta nel file principale del modulo (`pixelfeed/index.php`) e nel `AdminExportProductsFeedController`. Utilizza direttamente le classi `Product`, `Combination`, `Category`, `Manufacturer`, `Image` e `Tools` di base di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

- `pixelfeed/lib/searchTool/views/js/autocomplete.js`
  - **Ambito:** Back-office.
  - **Funzionalità:** Probabilmente fornisce funzionalità di completamento automatico per i campi di input all'interno della configurazione amministrativa, come il campo "Escludi prodotti per ID". Si legherebbe agli elementi di input, effettuerebbe chiamate AJAX per cercare prodotti e visualizzerebbe suggerimenti.
- `pixelfeed/views/js/admin-app.js`
  - **Ambito:** Back-office.
  - **Funzionalità:** Questo è il file JavaScript principale per l'interfaccia amministrativa del modulo. Gestirebbe:
    - Validazione e invio del modulo.
    - Richieste AJAX per la generazione del feed (a `AdminExportProductsFeedController`).
    - Visualizzazione di indicatori di caricamento o messaggi di successo/errore.
    - Potenzialmente aggiornamenti dinamici dell'interfaccia utente in base alle opzioni selezionate.
    - Interazioni con Fancybox (se utilizzato per la selezione di categorie o simili).

### 4.5 Fogli di stile CSS (`views/css/`)

- `pixelfeed/lib/searchTool/views/css/autocomplete.css`
  - **Ambito:** Stile amministrativo del back-office.
  - **Funzionalità:** Stila il menu a discesa di completamento automatico e i campi di input, garantendo un aspetto e una sensazione coerenti all'interno del back-office di PrestaShop.
- `pixelfeed/views/admin-theme.css`
  - **Ambito:** Stile amministrativo del back-office.
  - **Funzionalità:** Fornisce uno stile generale per la pagina di configurazione del modulo, assicurando che si integri bene con il tema del back-office di PrestaShop. Ciò potrebbe includere layout, stili dei pulsanti e stili degli elementi del modulo.
- `pixelfeed/views/css/admin-app.css`
  - **Ambito:** Stile amministrativo del back-office.
  - **Funzionalità:** Stile specifico per gli elementi dell'interfaccia utente personalizzati del modulo, come l'avanzamento della generazione del feed, gli avvisi o eventuali widget personalizzati nella pagina di configurazione.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo utilizza principalmente i template Smarty per la sua interfaccia Back Office.

#### Template Admin (`views/templates/admin/`)

- `pixelfeed/views/templates/admin/dashboard.tpl`
  - **Scopo:** Potrebbe essere una panoramica simile a una dashboard per il modulo, che mostra potenzialmente lo stato del feed, l'ultima data di generazione o collegamenti rapidi.
- `pixelfeed/views/templates/admin/feeds.tpl`
  - **Scopo:** Probabilmente il template principale per la visualizzazione delle opzioni e dei risultati della generazione del feed, possibilmente includendo un elenco di feed generati o un log.
- `pixelfeed/views/templates/admin/form-chrome.tpl`
  - **Scopo:** Un wrapper generico o un template strutturale per i moduli all'interno dell'interfaccia amministrativa, garantendo un layout e uno stile coerenti.
- `pixelfeed/views/templates/admin/layout.tpl`
  - **Scopo:** Il template di layout generale per le pagine amministrative del modulo, che definisce la struttura complessiva, l'intestazione e il piè di pagina.

#### Altri template (`views/`)

- `pixelfeed/lib/searchTool/views/scripts.tpl`
  - **Scopo:** Include JavaScript per lo strumento di ricerca, probabilmente renderizzato alla fine del corpo HTML o all'interno di una sezione specifica.
- `pixelfeed/views/categories-fancybox.tpl`
  - **Scopo:** Template per un modale Fancybox, possibilmente utilizzato per selezionare le categorie da includere/escludere dal feed, o per visualizzare alberi di categorie.
- `pixelfeed/views/exclude-products.tpl`
  - **Scopo:** Template per la sezione in cui i prodotti possono essere esclusi per ID, potenzialmente includendo il campo di input di completamento automatico.
- `pixelfeed/views/google_lang_links.tpl`
  - **Scopo:** Potrebbe essere correlato alla visualizzazione di link o informazioni specifiche per la lingua, possibilmente per le categorie di prodotti Google.
- `pixelfeed/views/returnAlert.tpl`
  - **Scopo:** Un template per la visualizzazione di messaggi di successo, errore o avviso all'utente nell'interfaccia amministrativa.
- `pixelfeed/views/script-fancybox.tpl`
  - **Scopo:** Include JavaScript per l'integrazione di Fancybox, spesso per popup modali.
- `pixelfeed/views/script.tpl`
  - **Scopo:** Inclusione generale di JavaScript per le pagine amministrative del modulo, potenzialmente per variabili globali o inizializzazioni.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

Il dossier del modulo indica l'assenza di file SQL personalizzati, suggerendo che non crea le proprie tabelle di database dedicate. Tutte le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` di PrestaShop utilizzando chiavi con prefisso `pf_` (ad esempio, `pf_export_active`, `pf_export_delimiter`).

#### Tabella degli hook registrati

La funzione principale del modulo è l'esportazione dei dati, non la visualizzazione nel front-office. Gli hook front-office elencati (Header, Colonne, Prodotto, Footer) sono probabilmente *non* utilizzati per l'output visivo diretto da questo modulo. Invece, potrebbero essere registrati per:

- **`displayHeader`**: Per includere le risorse JavaScript o CSS necessarie per il controller del feed front-office del modulo (se serve direttamente il feed).
- **Hook `action*`**: Il modulo probabilmente utilizza hook `action` (ad esempio, `actionProductUpdate`, `actionProductAdd`) internamente per svuotare le cache o attivare richieste di rigenerazione nel back-office quando i dati del prodotto cambiano, sebbene questi non siano esplicitamente elencati nel dossier. La logica principale del modulo per la generazione del feed viene tipicamente attivata manualmente o tramite un cron job, non direttamente da un hook front-office.

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` delle pagine front-office. | Potenzialmente per caricare JS/CSS per il servizio di feed front-office, o per integrazioni molto specifiche e non visive. |
| `displayRightColumn` / `displayLeftColumn` | Nelle colonne laterali delle pagine front-office. | Improbabile che venga utilizzato per la funzione principale di questo modulo; possibilmente per un blocco di debug o una funzionalità di nicchia non centrale per la generazione del feed. |
| `displayProductAdditionalInfo` / `displayProductButtons` (Pagina prodotto) | Nelle pagine prodotto. | Improbabile che venga utilizzato per la funzione principale di questo modulo. |
| `displayFooter` | Nel piè di pagina delle pagine front-office. | Improbabile che venga utilizzato per la funzione principale di questo modulo. |
| (Implicito) `actionProductUpdate` / `actionProductAdd` / `actionProductDelete` | Dopo le modifiche ai dati del prodotto nel BO. | Per invalidare i dati del feed memorizzati nella cache o richiedere all'amministratore la rigenerazione del feed. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Esporta catalogo per annunci dinamici Facebook Pixel", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e all'integrazione del modulo.
