---
title: "Combinations Tab Pro - documentazione e manuale utente"
description: "Configuri la matrice delle combinazioni, le impostazioni quotidiane della scheda prodotto e risolva i problemi comuni del front office se possiede già Combinations Tab Pro."
sidebar:
  label: "Combinations Tab Pro - documentazione e manuale utente"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Product page combinations table su MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-combinations-table.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/product-page-combinations-table/)
>
> ---


Le schermate di questo manuale provengono da un back office in inglese. Usi gli stessi nomi di schede e campi indicati sotto anche se la lingua del dipendente è diversa.

## 1. Requisiti

Combinations Tab Pro mostra un elenco di combinazioni o una matrice 2D nella scheda prodotto così i clienti possono filtrare, ordinare, impostare le quantità e aggiungere le varianti al carrello.

- PrestaShop: 1.7, 8 e 9
- PHP: una versione supportata dal suo negozio PrestaShop
- Estensioni PHP usate dal modulo: JSON
- Altri moduli: nessuno obbligatorio. Opzionale, **Product combination features** sblocca le colonne descrizione combinazione e caratteristiche combinazione quando quel modulo è installato nel negozio
- Fuori dal negozio: nulla. I controlli di aggiornamento contattano MyPresta quando le notifiche sono abilitate
- Cataloghi grandi: molte combinazioni per prodotto rallentano la pagina se lascia attive tutte le colonne e gli extra di elenco e griglia; usi filtri, paginazione o un preset adatto al suo catalogo

## 2. Installazione

1. Carichi lo ZIP del modulo in **Modules** → **Module Manager**, poi installi e abiliti **Combinations Tab Pro**.
2. Apra la configurazione dall’elenco moduli con **Configure**. Non c’è una voce di menu separata nel back office per l’uso quotidiano; tutte le impostazioni sono in quella pagina di configurazione.
3. L’installazione non svuota da sola la cache di PrestaShop. Svuoti la cache Smarty / del tema in **Advanced Parameters** → **Performance** se la tabella non compare dopo l’installazione.

**Dopo la disinstallazione:** il modulo viene rimosso dal Module Manager. Le tabelle del database per wishlist, avvisi di rientro stock e profili di override per entità vengono eliminate. I valori di configurazione restano nel database del negozio, così una reinstallazione successiva può riprendere gli interruttori precedenti finché non li modifica di nuovo. Gli override dei template del modulo nel tema (se ne ha aggiunti) non vengono rimossi dalla disinstallazione.

## 3. Configurazione e lavoro in back office

Apra **Modules** → **Module Manager** → **Combinations Tab Pro** → **Configure**. La pagina usa schede in alto: **Overview**, **Display**, **Cart**, **B2B**, **Visibility**, **Exclusions**, **Integrations**, **Overrides**, **Updates**. La ricerca prodotti su **Visibility**, **Exclusions** e **Overrides** avviene in background (AJAX); non c’è un menu Orders separato per questo modulo.

### 3.1 Processo completo

1. Il rivenditore configura posizionamento, modalità di visualizzazione, colonne o celle griglia, regole carrello, strumenti B2B opzionali, visibilità, esclusioni, integrazioni e override.
2. Il cliente apre un prodotto che ha combinazioni e che supera le regole di visibilità.
3. Il front office mostra un elenco (una riga per combinazione) o una griglia 2D (matrice quando il prodotto ha due gruppi di attributi e la modalità di visualizzazione lo consente), nel footer prodotto o sotto una scheda **Product variants**.
4. Il cliente può usare i filtri attributo, ordinare le intestazioni elenco, impostare le quantità e aggiungere una o più righe al carrello (incluso l’aggiunta massiva).
5. Strumenti opzionali: cuore wishlist, notifica rientro stock, incolla quantità CSV, foglio di esportazione, riempi ultimo ordine.
6. Il checkout prosegue come un ordine PrestaShop normale. Il modulo non usa stati tipo preventivo; il successo è una tabella visibile, quantità compilate e un carrello con le combinazioni selezionate.

### 3.2 Overview & presets

![Overview and presets — English back office](https://mypresta.eu/docs/images/docs/combinationstab-overview.webp)

**Overview & presets** è la scheda di partenza. Le configurazioni pronte attivano o disattivano molti interruttori in una volta. Usi **Preview** per vedere i valori previsti, poi **Apply**. Conferma: *Preset applied. Review Display & Columns and Cart & prices if you want to fine-tune.* Poi apra **Display** e **Cart** per regolare i dettagli.

Preset principali per nome:

| Preset | Tag | What it prepares |
|---|---|---|
| **Fashion** | B2C | Foto, filtri, campioni colore, wishlist, card mobili per abbigliamento con molte taglie e colori |
| **B2B Wholesale** | B2B | Matrice orientata allo SKU, aggiunta massiva al carrello, import CSV, export, sconti volume |
| **Minimal** | Simple | Solo nome combinazione, prezzo e aggiungi al carrello |
| **Replace buy block** | UX | Nasconde il blocco acquisto PrestaShop predefinito così i clienti ordinano dalla tabella |
| **2D size × color** | Grid | Forza la griglia 2D con contenuto celle ricco quando i prodotti hanno Color + Size |
| **Detailed list** | List | Elenco completo con immagini, SKU, EAN, stock, ordinamento, paginazione |
| **Electronics** | B2C | Riferimento, EAN, prezzo unitario, date di disponibilità per elettrodomestici e gadget |
| **Beauty & cosmetics** | B2C | Riquadro colore + testo, foto, wishlist e rientro stock per tonalità e kit |
| **Catalog only** | Display | Combinazioni senza ordine; i prezzi possono restare per i clienti connessi |
| **Logged-in pricing** | B2B | Prezzi e aggiungi al carrello solo per clienti connessi |
| **Mobile first** | UX | Elenco con card mobili, quantità +/- , aggiunta massiva sticky |
| **Restock & alerts** | Conversion | Righe esaurite con date e avvisi di rientro stock |
| **Luxury / lookbook** | B2C | Foto grandi, zoom, stock esatto nascosto, evidenziazioni di risparmio |
| **Food & packaging** | Retail | Prezzo unitario, peso, qty min, sconti volume |
| **Quick order sheet** | B2B | Griglia + aggiunta massiva + CSV/export/riordino senza immagini |

### 3.3 Display — Placement

![Display settings — English back office](https://mypresta.eu/docs/images/docs/combinationstab-display.webp)

Sotto-scheda **Placement**. Posizionamento a livello di pagina e cornice intorno alla tabella (elenco e griglia 2D). Il salvataggio mostra *Display settings saved.*

| Field | At the start | What it does |
|---|---|---|
| **Position on the product page** | Product footer (below product content) | Sceglie dove i clienti vedono la tabella combinazioni. Usi **Product footer** sotto il prodotto, o **Product tabs section** per una scheda tipo **Product variants**. Scelga la posizione adatta al suo tema: la scelta sbagliata può nascondere la tabella o metterla troppo in basso. |
| **Tab style (legacy themes)** | Classic tabs (PS 1.5 style) | Conta solo se usa la posizione Product tabs su temi vecchi. Lasci il valore predefinito salvo che il tema usi ancora schede stile PrestaShop 1.5. Cambia come viene iniettato il titolo della scheda; i temi moderni 1.7/8/9 di solito lo ignorano. Opzioni: Classic tabs (PS 1.5 style) o Accordion bars (PS 1.6 style). |
| **Custom HTML above the table** | Empty | Contenuto libero (nota spedizione, link guida taglie, ecc.) sopra la matrice. Opzionale per lingua. Visibile sopra elenco e griglia 2D. |
| **Hide default PrestaShop buy block** | No | Nasconde i menu a tendina attributi classici e l’aggiungi al carrello nella scheda prodotto. Imposti **Yes** quando la tabella deve essere l’unico modo per acquistare. Pagina più pulita; si assicuri che la tabella stessa consenta l’aggiungi al carrello. |
| **Hide default buy block only when table has combinations** | No | Mantiene il blocco acquisto normale sui prodotti semplici; lo nasconde quando viene mostrata la matrice. **Yes** è di solito il più sicuro così i prodotti semplici funzionano ancora normalmente. |
| **Also hide default buy block based on product restrictions** | No | Accoppiamento avanzato con le regole Visibility. Lasci **No** salvo liste complesse di mostra/nascondi prodotti. Può nascondere il blocco nativo su prodotti selezionati anche senza la tabella. |

### 3.4 Display — View mode

| Field | At the start | What it does |
|---|---|---|
| **View mode** | List (classic table — one row per combination) | Sceglie tabella elenco o matrice 2D. **List** = sempre righe; **2D grid** = forza la matrice quando possibile; **Auto** = matrice per 2 gruppi di attributi, elenco altrimenti. Negozi fashion/B2B con Color+Size si adattano a Grid/Auto; prodotti con un attributo restano elenco. |
| **Click combination to open that variant** | Off | Un clic su riga/cella apre l’URL prodotto di quella combinazione. Imposti **Yes** se vuole sfogliare le varianti dalla tabella. Utile con le foto; disabiliti se i clic devono solo cambiare la quantità. |

### 3.5 Display — Filters

Queste regole si applicano sia alla tabella elenco sia alla griglia 2D.

| Field | At the start | What it does |
|---|---|---|
| **Attribute filters above the table / grid** | Off | Mostra chip cliccabili (ad es. Red, XL) per filtrare righe/colonne. Imposti **Yes** per prodotti con molte combinazioni. I clienti restringono elenco e matrice senza scorrere all’infinito. |
| **Hide out-of-stock combinations** | Off | Rimuove le combinazioni esaurite da elenco e griglia 2D. Imposti **Yes** per vendere solo varianti disponibili. Tabella/matrice più corta; i clienti non vedono le taglie mancanti. |
| **Hide combinations with price = 0** | Off | Nasconde varianti gratuite/a prezzo zero da elenco e griglia. Imposti **Yes** se zero significa «non in vendita». Le matrici possono sembrare incomplete se alcune celle sono intenzionalmente 0. |
| **Show only combinations that have a picture** | Off | Nasconde le combinazioni senza immagini in elenco e griglia. Imposti **Yes** per lookbook; **No** se ogni SKU deve essere ordinabile. Cataloghi incompleti sembrano migliori ma alcune varianti spariscono. |
| **Multistore: disabled attribute values** | Hide the whole combination | Quando un valore attributo è disabilitato per il negozio corrente. Solo multinegozio — scelga nascondi combinazione, mostra come «-», o ignora. Si applica prima di costruire elenco e griglia; i negozi a un solo shop possono lasciare il valore predefinito. |

### 3.6 Display — Stock format

Come vengono mostrate le quantità di stock in elenco e griglia quando lo stock è visibile. La visibilità colonna/cella è sotto List columns o Grid cells.

| Field | At the start | What it does |
|---|---|---|
| **Show negative stock as zero** | Off | Mostra 0 invece di numeri negativi. Imposti **Yes** se lo stock può scendere sotto zero. Numeri di stock più chiari in elenco e griglia. |
| **Hide exact stock above a threshold** | Off | Mostra ad esempio «20+» invece del numero reale. Imposti **Yes** e la soglia. Nasconde grandi quantità di magazzino ai concorrenti in elenco e griglia. |
| **Stock threshold (show as X+)** | Empty | Quando nascondi stock esatto è **Yes**, le quantità sopra appaiono come «N+». Esempio: 20 fa apparire lo stock 45 come «20+». |

### 3.7 Display — Grid axes, images, cells

Una griglia 2D è una matrice stile taglia×colore. Funziona quando il prodotto ha esattamente due gruppi di attributi e View mode è **Grid** o **Auto**. Un accoppiamento assi errato (stesso gruppo due volte) rompe la griglia e torna all’elenco.

**Grid axes**

| Field | At the start | What it does |
|---|---|---|
| **Grid rows = attribute group** | -- automatic -- | Quale attributo diventa il lato sinistro della matrice (ad es. Color). Scelga un gruppo o lasci Automatic (primo gruppo attributi per posizione). Una coppia sbagliata rompe la griglia e torna all’elenco. |
| **Grid columns = attribute group** | -- automatic -- | Quale attributo diventa la parte superiore della matrice (ad es. Size). Scelga un gruppo diverso dalle righe, o Automatic. Ogni cella è una combinazione in cui i clienti digitano la quantità. |

**Grid images** (solo griglia 2D)

| Field | At the start | What it does |
|---|---|---|
| **Show image in cells** | Off | Miniatura in ogni cella della matrice. Imposti **Yes** per matrici fashion colore×taglia. Celle più dense; usa l’immagine combinazione o il fallback cover sotto. |
| **Use product cover when combination has no image** | Yes | Mostra la foto principale del prodotto come fallback nelle celle. Imposti **Yes** per non mostrare mai un’immagine vuota nella matrice. Influisce solo sulla griglia 2D, non sull’elenco. |
| **Grid thumbnail image type** | Empty (shop image types) | Dimensione immagine PrestaShop usata nelle celle. Scelga un tipo piccolo (ad es. cart / small_default). Solo griglia 2D; l’elenco usa List images → Thumbnail type. |

**Grid cells** — trascini **Cell block order** (alto→basso), poi Save. Solo i blocchi abilitati appaiono. Wishlist/BIS richiedono ancora **Integrations**; aggiungi al carrello richiede l’interruttore master sotto **Cart**.

| Field | At the start | What it does |
|---|---|---|
| **Cell block order** | Default block order | Ordine dei blocchi in ogni cella della matrice. Trascini, poi Save. Solo i blocchi abilitati sotto appaiono. Immagine on/off e dimensione sotto Grid images. |
| **Grid: show reference (SKU)** | Off | SKU sotto il contenuto della cella. Imposti **Yes** per B2B così gli acquirenti identificano gli SKU senza aprire il prodotto. |
| **Grid: show price** | Off | Prezzo nella cella (le regole tasse/sconti seguono Cart). Imposti **Yes** per quasi ogni negozio così i clienti confrontano le varianti per prezzo nella matrice. |
| **Grid: show unit price** | Off | Prezzo unitario nella cella. Imposti **Yes** se usa i prezzi unitari. Riga compatta sotto il prezzo principale. |
| **Grid: show stock quantity** | Off | Numero di stock disponibile nella cella. Imposti **Yes** per trasparenza; rivela l’inventario per taglia/colore. |
| **Grid: show availability** | Off | Etichetta In stock / Out of stock nella cella. Imposti **Yes** quando i numeri di stock sono nascosti. Stato chiaro senza la qty esatta. |
| **Grid: show minimal quantity** | Off | Qty minima d’ordine nella cella. Imposti **Yes** per pack B2B; riduce quantità carrello errate. |
| **Grid: show savings badge** | Off | % risparmiato rispetto alla combinazione più cara. Imposti **Yes** per la conversione; evidenzia taglie/colori più economici. |
| **Grid: quantity input** | Off | Campo qty in ogni cella (funziona con Bulk Add to cart). Imposti **Yes** per l’ordine a matrice così i clienti compilano le quantità per taglia. |
| **Grid: Add to cart button (when bulk ATC is off)** | Off | Pulsante aggiungi per cella quando Bulk add to cart è disabilitato. Imposti **Yes** per aggiunte in un clic senza bulk. Ignorato mentre bulk ATC è attivo. |
| **Grid: wishlist heart** | Off | Pulsante cuore nella cella. Abiliti prima Wishlist sotto Integrations. I clienti salvano taglia/colore dalla matrice. |
| **Grid: back-in-stock alert** | Off | Pulsante notifica sulle celle esaurite. Abiliti prima Back in stock sotto Integrations. Cattura la domanda per le taglie mancanti. |

### 3.8 Display — List layout, images, columns

Queste impostazioni riguardano solo l’elenco classico (una riga per combinazione), non le celle della griglia 2D.

**List layout & sorting**

| Field | At the start | What it does |
|---|---|---|
| **Column order (list only)** | Default column order | Imposta l’ordine da sinistra a destra delle colonne nella vista elenco. Trascini gli elementi, poi Save. I clienti vedono le colonne in quest’ordine (appaiono solo quelle abilitate). |
| **Mobile card layout (list)** | Yes | Sui telefoni, trasforma le righe larghe della tabella in card impilate. Imposti **Yes** per una migliore UX mobile. Ogni combinazione sembra una piccola card; il desktop resta una tabella normale. |
| **Hide table header (list)** | Off | Rimuove la riga superiore con i nomi delle colonne. Di solito lasci **No**. Aspetto più pulito ma colonne più difficili da capire. |
| **Paginate long tables (list)** | Off | Divide molte combinazioni in pagine. Imposti **Yes** se un prodotto ha decine di varianti. Sensazione di pagina più veloce; imposti Rows per page sotto. |
| **Rows per page** | 10 when pagination is used without a custom value | Quante combinazioni per pagina con paginazione attiva. Esempio: 10 o 20. Numero minore = pagine più corte, più clic. |
| **Allow sorting by column headers** | Yes | Intestazioni cliccabili per ordinare l’elenco. Imposti **Yes** per elenchi lunghi. I clienti ordinano per prezzo, riferimento, ecc. (solo vista elenco). |
| **Default sort by price** | Off | L’ordinamento iniziale usa il prezzo. Opzionale. Più economico/caro per primo a seconda della direzione. |
| **Default sort by attribute** | Off | Ordinamento iniziale per un gruppo di attributi scelto. Imposti ID attributo e direzione sotto. Esempio: taglie S→XL. |
| **Attribute sort uses** | Attribute value position | Ordina per posizione attributo (ordine catalogo) o per nome A→Z. La posizione di solito è migliore per le taglie. Cambia l’ordine righe predefinito quando l’ordinamento per attributo è abilitato. |
| **Attribute group ID to sort by** | Empty | ID numerico del gruppo attributi usato per l’ordinamento predefinito. In Catalog → Attributes, apra il gruppo e legga l’ID dall’URL. ID errato = ordine inatteso. |
| **Sort direction** | Ascending | Ordine predefinito ascendente o discendente. Ascending per S→XL; Descending per prezzo alto→basso quando si ordina per prezzo. Controlla le prime righe che i clienti vedono. |

**List images**

| Field | At the start | What it does |
|---|---|---|
| **Show image column** | Yes | Aggiunge una miniatura per ogni combinazione. Imposti **Yes** quando le varianti hanno foto diverse così i clienti le riconoscono prima. |
| **Show image column only if at least one combination has a photo** | Off | Nasconde la colonna immagine vuota quando nessuna combinazione ha una foto. Imposti **Yes** per evitare una colonna vuota inutile. La tabella resta pulita sui prodotti senza immagini combinazione. |
| **Use product cover when combination has no image** | Off | Mostra la foto principale del prodotto come fallback nell’elenco. Imposti **Yes** per non mostrare mai una cella immagine vuota. Influisce solo sulla vista elenco, non sulla griglia 2D. |
| **Click image to zoom** | Off | Apre un’immagine più grande in lightbox. Imposti **Yes** per prodotti visivi; imposti la dimensione zoom sotto. I clienti ispezionano i dettagli senza lasciare la pagina. |
| **Thumbnail image type** | Empty (shop image types) | Dimensione immagine PrestaShop usata nella colonna elenco. Scelga un tipo piccolo (ad es. cart / small_default). Solo elenco; la griglia usa Grid images → Thumbnail type. |
| **Zoom image type** | Empty (shop image types) | Dimensione immagine aperta nel lightbox quando lo zoom è abilitato. Scelga un tipo grande (ad es. large_default). Anteprima zoom più nitida in vista elenco. |

**List columns** — visibilità per l’elenco classico. Descrizione / caratteristiche combinazione richiedono il modulo opzionale Combination features; altrimenti quei controlli restano bloccati con un link al negozio.

| Field | At the start | What it does |
|---|---|---|
| **How attributes are shown** | All attributes in one column | Una colonna combinata «Combination name» vs colonne separate per attributo (Color, Size…). Le colonne separate sono più facili da scansionare e ordinare. Il layout della vista elenco cambia subito. |
| **Include attribute label in the name** | Off | Mostra «Color: Red, Size: L» invece di «Red, L». Imposti **Yes** per chiarezza; si applica solo al metodo a una colonna. Nomi più lunghi ma più chiari. |
| **Color attribute display** | Text only | Come appaiono i valori colore (swatch, testo, o entrambi). Riquadro colore per la moda; Testo se i colori hanno nomi particolari. Influisce solo sugli attributi di tipo «color». |
| **Show combination / attribute columns** | Yes | Interruttore master per le colonne nome attributo. Quasi sempre **Yes**. **No** nasconde come le varianti differiscono — solo per layout molto speciali. |
| **Show combination description** | Off (locked without Combination features) | Mostra la descrizione personalizzata assegnata alla combinazione da Combination features. Imposti **Yes** quando le varianti hanno un testo unico. Colonna elenco extra; le celle vuote mostrano «-». |
| **Show combination features** | Off (locked without Combination features) | Mostra i valori caratteristica assegnati alla combinazione da Combination features. Imposti **Yes** quando le varianti hanno la propria scheda dati. Colonna elenco extra con nome caratteristica + valori. |
| **Show reference (SKU)** | Yes | Mostra il riferimento combinazione. Imposti **Yes** per B2B / ingrosso così gli acquirenti ordinano più in fretta per SKU. |
| **Show EAN** | No | Mostra il codice a barre EAN-13. Imposti **Yes** se staff/clienti scansionano i codici. Colonna extra; disattivi per moda B2C se inutilizzato. |
| **Show MPN** | No | Colonna numero pezzo produttore. Imposti **Yes** quando valorizza l’MPN nel catalogo. Le celle vuote mostrano «-» se l’MPN è vuoto. |
| **Show weight** | Off | Peso prodotto + impatto combinazione. Imposti **Yes** per beni sensibili alla spedizione così i clienti stimano i costi. |
| **Show stock quantity** | Yes | Stock disponibile per combinazione. Imposti **Yes** per trasparenza; abbini a Stock format per «10+». Costruisce fiducia; rivela l’inventario. |
| **Show total product stock in header** | No | Aggiunge la somma dello stock accanto all’intestazione Quantity. Panoramica opzionale rapida della disponibilità totale. |
| **Show availability text** | Yes | «In stock» / «Out of stock» (o le etichette del suo negozio). Imposti **Yes** per chiarezza così i clienti vedono lo stato senza leggere il numero. |
| **Show availability date when out of stock** | Yes | Stampa la data di disponibilità della combinazione sotto lo stato esaurito. Imposti **Yes** se valorizza le date di disponibilità. Imposta le aspettative di rientro. |
| **Show minimal quantity** | Off | Mostra la quantità minima d’ordine della combinazione. Imposti **Yes** per pack B2B; riduce errori di aggiungi al carrello. |
| **Show price** | Yes | Colonna prezzo per combinazione (solo elenco). Imposti **Yes** per quasi ogni negozio. I clienti confrontano le varianti per prezzo. La griglia usa Grid cells → show price. |
| **Show unit price** | Off | Colonna prezzo unitario (solo elenco). Imposti **Yes** se usa i prezzi unitari. Valori vuoti/strani se l’unità non è impostata sul prodotto. |
| **Show savings column** | No | Quanto una combinazione è più economica rispetto alla più cara (solo elenco). Imposti **Yes** per psicologia di upsell. Colonna extra con % e importo risparmiato. La griglia usa Grid cells → savings badge. |
| **Show volume (quantity) discounts column** | Off | Elenca i livelli di sconto quantità per combinazione (solo elenco). Imposti **Yes** per l’ingrosso. Tabella più larga; ottima per B2B. |
| **Hide volume discount rows that do not apply** | Off | Pulisce gli elenchi sconto vuoti nella colonna elenco. Imposti **Yes** per ridurre il rumore e lasciare solo i livelli significativi. |

### 3.9 Cart — Prices

![Cart settings — English back office](https://mypresta.eu/docs/images/docs/combinationstab-cart.webp)

Sotto-scheda **Prices**. Regole globali di visualizzazione prezzi per elenco e griglia 2D. Il salvataggio mostra *Cart & price settings saved.*

| Field | At the start | What it does |
|---|---|---|
| **Show prices only to logged-in customers** | No | Gli ospiti vedono un invito al login invece dei prezzi. Imposti **Yes** per prezzi B2B nascosti. Gli ospiti devono accedere per vedere gli importi in elenco e griglia. |
| **Tax display** | Tax included | Tasse incluse, escluse, o seguire l’impostazione del gruppo clienti. Allinei alla politica prezzi del suo negozio. Una scelta sbagliata confonde acquirenti B2B e B2C. |
| **Show “tax incl./excl.” label next to price** | Off | Piccolo testo dopo il prezzo. Imposti **Yes** per chiarezza legale nell’UE. Celle un po’ più affollate. |
| **Show discount % badge on reduced prices** | Off | Mostra -X% quando esiste una riduzione di prezzo specifica. Imposti **Yes** per evidenziare le offerte. Attira l’attenzione sulle combinazioni scontate in elenco e griglia. |
| **Highlight the cheapest combination** | Yes | Segna la riga/cella al prezzo più basso. Imposti **Yes** per guidare gli acquisti d’impulso. Evidenziazione verde del miglior prezzo in elenco e griglia. |

### 3.10 Cart — Add to cart

| Field | At the start | What it does |
|---|---|---|
| **Show add to cart controls** | Yes | Campo quantità e/o pulsante per combinazione. Imposti **Yes** per vendere dalla tabella. **No** = matrice solo visualizzazione. |
| **Add to cart only for logged-in customers** | Off | Gli ospiti non possono aggiungere dalla tabella. Imposti **Yes** per B2B. Gli ospiti vedono un messaggio al posto dei pulsanti. |
| **Show quantity input** | Yes | Casella qty modificabile. **Yes** sempre consigliato. **No** nasconde la qty (più difficile acquistare più unità). |
| **Qty box also in the table header (fill all rows)** | Off | Una qty in intestazione si copia su tutte le righe. Comodità opzionale. Velocizza il riempimento massivo; usi con attenzione. |
| **Plus / minus buttons** | No | Pulsanti +/- accanto alla qty. Imposti **Yes** per dispositivi touch. Cambi di quantità più facili. |
| **Block qty higher than stock** | Off | Impedisce di ordinare più del disponibile (quando gli ordini fuori stock non sono consentiti). Imposti **Yes** per evitare la sovravendita. Il pulsante + si ferma allo stock. |
| **AJAX add to cart** | Yes | Aggiunge senza ricaricare tutta la pagina. Imposti **Yes** sui temi moderni. UX più fluida; disabiliti solo se c’è conflitto col tema. |
| **Bulk add to cart (one button for many rows)** | Off | Il cliente compila più campi qty, poi un **Add to cart** invia tutto. Imposti **Yes** per B2B/moda. I pulsanti per riga possono essere nascosti; compare una barra sticky sul mobile. |
| **Show live total price of selected quantities** | Off | Calcola la somma delle righe selezionate (rispetta gli sconti quantità quando possibile). Imposti **Yes** con aggiunta massiva. I clienti vedono il valore del carrello prima di cliccare Add. |
| **Tip: how many units until next quantity discount** | Yes | Sotto la barra massiva, dice al cliente «add X more to unlock the next discount». Imposti **Yes** se usa sconti quantità. Incoraggia carrelli più grandi. |
| **Use Font Awesome cart icon** | Off | Icona FA invece dell’icona Material. Imposti **Yes** solo se il suo tema carica Font Awesome. FA mancante = icona rotta. |

### 3.11 B2B Tools and Groups

![B2B tools — English back office](https://mypresta.eu/docs/images/docs/combinationstab-b2b.webp)

**Tools** — aiuti per l’ingrosso. Gli interruttori globali sono i valori predefiniti; usi **Groups** per consentire o negare per gruppo clienti PrestaShop. Il salvataggio mostra *B2B settings saved.*

| Field | At the start | What it does |
|---|---|---|
| **CSV quantity import on product page** | No | Gli acquirenti incollano righe come SKU;5 (o EAN;qty) per riempire le quantità. Imposti **Yes** per l’ingrosso; poi lo consenta per gruppo se serve. Grande risparmio di tempo sui riordini. |
| **Export order sheet (CSV / XLSX / PDF)** | No | Scarica le combinazioni con le quantità digitate. Imposti **Yes** per acquirenti che inviano fogli alla contabilità. I pulsanti compaiono accanto all’aggiunta massiva. |
| **Fill last order button** | No | Ripristina le quantità dall’ultimo aggiunta massiva / export per questo prodotto. Imposti **Yes** per ordini all’ingrosso ripetuti. Un clic riempie di nuovo la matrice. |

**Groups** — per ogni gruppo clienti imposti **Show table**, **Add to cart**, **CSV import**, **Export**, **Reorder** (Yes/No). Predefiniti senza regola personalizzata: show table Yes, add to cart Yes, CSV/export/reorder seguono gli interruttori globali Tools (off dopo l’installazione). Se **Show table** è No per il gruppo del visitatore, la matrice non appare. Se **Add to cart** è No, il visitatore non può aggiungere dalla tabella anche quando gli interruttori Cart globali sono attivi.

### 3.12 Visibility

![Visibility — English back office](https://mypresta.eu/docs/images/docs/combinationstab-visibility.webp)

Controlli su quali prodotti i clienti vedono la tabella combinazioni. Cerchi prodotti con il selettore a schermo (ricerca AJAX). Conferma: *Successfully updated*.

| Field | At the start | What it does |
|---|---|---|
| **Visibility rule** | Show on all products | Decide se la tabella appare su ogni prodotto, solo su quelli selezionati, o ovunque tranne i selezionati. Scelga una regola, poi spunti categorie / aggiunga prodotti nel selettore sotto. «All products» è il più semplice; usi Include/Exclude quando solo una parte del catalogo necessita della matrice. |
| **Selected categories & products** | None | L’elenco di categorie e prodotti usati dalla regola sopra. Spunti categorie e/o cerchi prodotti e clicchi Add. Usato solo quando la regola è Include o Exclude — ignorato per «all products». |
| **Hide table when product has too few attribute groups** | Off | Nasconde la tabella sui prodotti con pochi gruppi di attributi (ad es. solo Color, senza Size). Imposti **Yes** e il numero sotto. Esempio: soglia 1 nasconde prodotti con 1 o meno gruppi di attributi — utile se vuole la matrice solo per prodotti Color+Size. |
| **Hide when attribute groups ≤** | Empty | Soglia per l’interruttore sopra. Inserisca 1 per nascondere prodotti a un attributo; 0 di fatto non nasconde mai con questa regola. Confrontato con il numero di gruppi di attributi sul prodotto. |

### 3.13 Exclusions

Nasconda permanentemente combinazioni scelte dalla tabella (tutti i prodotti). Cerchi un prodotto, scelga le combinazioni con **Select**, poi **Save**. Conferma: *Settings saved*. Quelle varianti restano in PrestaShop ma non appaiono mai nella matrice — utile per taglie obsolete o SKU interni. La ricerca prodotto e combinazione usa la stessa ricerca AJAX prodotti di Visibility.

| Field | At the start | What it does |
|---|---|---|
| **Search for product** | Empty | Trovi il prodotto le cui combinazioni vuole escludere. |
| **Combination** | None selected | Contrassegni le combinazioni da nascondere dalla matrice del front office, poi Save. |

### 3.14 Integrations

![Integrations — English back office](https://mypresta.eu/docs/images/docs/combinationstab-integrations.webp)

Il salvataggio mostra *Integrations saved.* Il form segnala Advanced Stock Management quando rilevato; senza ASM, lasci l’interruttore magazzino su Off.

| Field | At the start | What it does |
|---|---|---|
| **Combination wishlist** | No | Il pulsante cuore salva una variante in una wishlist leggera (account o cookie). Imposti **Yes** se i clienti segnano le taglie. Il link appare in My Account; non è una suite wishlist completa. |
| **Back-in-stock email alerts** | No | Le righe esaurite ottengono un pulsante notifica; quando lo stock torna, il modulo invia email al cliente. Imposti **Yes** e si assicuri che il negozio possa inviare email. Recupera la domanda sulle taglie mancanti. |
| **Warehouse stock column** | No | Elenca le quantità per magazzino quando Advanced Stock è abilitato. Imposti **Yes** solo con ASM. Senza ASM la colonna resta vuota — lasci Off. |

### 3.15 Overrides

![Overrides — English back office](https://mypresta.eu/docs/images/docs/combinationstab-overrides.webp)

I profili si cascadenano **Product → deepest Category → Manufacturer → Global**. Solo i campi sovrascritti cambiano lo strato inferiore. Filtri l’elenco con **All / Products / Categories / Manufacturers**. Crei con **Product override**, **Category override** o **Manufacturer override**.

Nella schermata di modifica: cerchi e selezioni un’entità, abiliti solo i campi da sovrascrivere, lasci ereditare i campi non spuntati. Usi **Copy all from global** per seminare i valori, poi **Save override**. Successo: *Override profile saved.* L’eliminazione chiede *Delete this override profile?* Successo: *Override profile deleted.*

Motivi tipici per usare gli override: un brand ha sempre bisogno della modalità griglia; una categoria nasconde i prezzi agli ospiti; un prodotto necessita di colonne SKU extra senza cambiare tutto il negozio.

### 3.16 Updates

**Check now** chiede a MyPresta se esiste una build più recente. Messaggi: *New version available!* o *Module is up to date!*

| Field | At the start | What it does |
|---|---|---|
| **Check updates** | — | Esegue un controllo immediato e mostra se esiste una nuova versione. |
| **Updates notifications** | Select / as previously saved | Attivi questa opzione se vuole controllare automaticamente su MyPresta.eu gli aggiornamenti del modulo. Questa opzione mostrerà notifiche sulle nuove versioni di questo addon. |
| **Module page** | Link on screen | Link diretto alla pagina ufficiale dell’addon dove può leggere le modifiche del modulo (changelog). Usi Support (capitolo 7) per le richieste di aiuto. |

## 4. Front office

- **Placement:** footer prodotto sotto il contenuto, o una scheda **Product variants** nell’area schede prodotto, a seconda di Display → Placement.
- **List vs 2D grid:** l’elenco è una riga per combinazione. La griglia è una matrice quando il prodotto ha esattamente due gruppi di attributi e View mode è Grid o Auto; altrimenti il front office torna all’elenco.
- **Filters:** chip attributo sopra tabella/griglia quando abilitati.
- **Sorting / pagination / mobile cards:** solo elenco, quando quelle opzioni Display sono attive.
- **Add to cart:** controlli per riga e/o **Add to cart** massivo con totale live opzionale e tip «units until next discount».
- **Toolbar:** quando abilitata — **Fill last order**, **Export** (CSV / XLSX / PDF), area di testo **Import quantities** con righe come `REF001;5`, poi **Apply**.
- **Wishlist:** cuore su righe/celle quando Integrations + interruttori colonna/cella lo consentono. I clienti connessi ottengono **My combination wishlist** nella pagina account cliente.
- **Back in stock:** controllo notifica sulle righe esaurite; email quando lo stock torna (la mail del negozio deve funzionare).
- **Guest prices:** con «prices only for logged-in», gli ospiti vedono un invito al login invece degli importi; con «ATC only for logged-in», gli ospiti non possono aggiungere dalla tabella.

Qui non è richiesta una schermata front office separata; il layout del tema decide la cornice esatta intorno al blocco del modulo.

## 5. Problemi comuni

### 5.1 Tabella non visibile nella scheda prodotto

Verifichi modulo abilitato, prodotto con combinazioni, regola **Visibility** che include il prodotto, gruppo clienti **Show table** a Yes, e posizione adatta al suo tema (footer vs schede). Svuoti la cache. Confermi che Exclusions non abbia nascosto ogni combinazione.

### 5.2 Posizione sbagliata o scheda vuota

Cambi **Position on the product page**. Sui temi moderni, ignori Tab style. Se usa le schede, apra il prodotto e cerchi **Product variants**.

### 5.3 Si aspettava la griglia 2D ma vede un elenco

La griglia richiede esattamente due gruppi di attributi e View mode Grid o Auto. Un attributo, o tre o più, forza l’elenco. Lo stesso gruppo di attributi per entrambi gli assi torna pure all’elenco — imposti gruppi di righe e colonne diversi.

### 5.4 Blocco acquisto predefinito mancante o ancora visibile

Controlli **Hide default PrestaShop buy block** e **Hide default buy block only when table has combinations**. Se il blocco nativo è nascosto ma la tabella non ha aggiungi al carrello, i clienti non possono acquistare — attivi Cart → **Show add to cart controls**.

### 5.5 L’aggiunta massiva non fa nulla o ricarica male

Attivi **AJAX add to cart** per i temi moderni. Confermi che **Bulk add to cart** è Yes e che le quantità sono compilate. La regola di gruppo **Add to cart** deve essere Yes per quel gruppo clienti.

### 5.6 Le regole di gruppo bloccano l’aggiungi al carrello o nascondono la tabella

Sotto **B2B** → **Groups**, imposti **Show table** e **Add to cart** a Yes per il gruppo del visitatore (Guest, Customer, o il suo gruppo ingrosso).

### 5.7 Prezzi nascosti per gli ospiti

Atteso quando **Show prices only to logged-in customers** è Yes. Lo metta Off per prezzi pubblici, o chieda agli ospiti di accedere.

### 5.8 Wishlist o rientro stock mancanti

Li abiliti sotto **Integrations**, poi abiliti gli interruttori di colonna elenco o cella griglia corrispondenti. Per BIS, confermi che PrestaShop può inviare mail e che lo stock si aggiorna al reintegro.

### 5.9 Colonne descrizione / caratteristiche combinazione bloccate

Installi e abiliti il modulo opzionale **Product combination features**. Fino ad allora quelle colonne restano bloccate in Display e Overrides.

### 5.10 CSV / export / riempi ultimo ordine mancanti

Abiliti gli strumenti sotto **B2B** → **Tools**, e imposti Yes per quel gruppo clienti sotto **Groups**.

## 6. Guida per sviluppatori

### 6.1 Panoramica

- Nome tecnico: `combinationstab`
- Versione: 3.0.5
- Nome visualizzato: Combinations Tab Pro
- Autore: mypresta.eu
- Scheda modulo: `smart_shopping`
- Classe principale: `Combinationstab`
- UI BO: `CtpAdminBo` (`lib/CtpAdminBo.php`)
- Risoluzione impostazioni: `CtpSettingsResolver` (Product → Category → Manufacturer → Global)
- Opzionale: `CtpCombfeat` — il file può essere assente; `class_exists('CtpCombfeat')` controlla descrizione/caratteristiche combinazione. Senza la classe, quelle opzioni restano bloccate.

Flusso: Configuration / impostazioni entità → gli hook FO renderizzano i template elenco o griglia → i controller front gestiscono gli helper AJAX carrello, wishlist, BIS, CSV, export, riordino, calcolatore prezzi.

### 6.2 File importanti

| Path | Role |
|---|---|
| `combinationstab.php` | Classe modulo, install/uninstall, hook, form visibility/exclusions |
| `lib/CtpAdminBo.php` | Schede pagina Configure e campi HelperForm |
| `lib/CtpColumnRegistry.php` | Colonne elenco, preset, JSON ordine |
| `lib/CtpGridRegistry.php` | Blocchi celle griglia e JSON ordine |
| `lib/CtpGrid2d.php` | Costruzione matrice 2D / `shouldUseGrid` |
| `lib/CtpCombinationsData.php` | Righe combinazione per FO |
| `lib/CtpGroupRules.php` | Per gruppo show/atc/csv/export/reorder |
| `lib/CtpWishlist.php` / `CtpBackInStock.php` / `CtpExport.php` / `CtpReorder.php` | Helper funzionalità |
| `lib/CtpSettingsResolver.php` | Tabella override e cascata |
| `views/templates/admin/tabs.tpl` | Cornice schede BO |
| `views/templates/hook/productfooter.tpl` / `productfooter_grid.tpl` | Elenco / griglia FO |
| `views/templates/hook/_toolbar.tpl` | Toolbar bulk / export / CSV |
| `controllers/front/*.php` | Endpoint front |
| `controllers/admin/AdminCombinationstabSearchController.php` | Ricerca AJAX prodotti per i selettori BO |

### 6.3 Controller

**Admin:** `AdminCombinationstabSearchController` — ricerca AJAX prodotto/combinazione usata da Visibility, Exclusions, Overrides. Non è una pagina di menu per i rivenditori.

**Front:**

| Controller | Purpose |
|---|---|
| `Wishlist` | Attiva/disattiva / elenca wishlist (JSON + pagina account) |
| `BackInStock` | Iscriviti agli avvisi OOS (JSON) |
| `CsvImport` | Applica quantità SKU/EAN incollate (JSON) |
| `Export` | Scarica foglio CSV/XLSX/PDF |
| `Reorder` | Salva / ripristina ultime quantità (JSON) |
| `PriceCalculator` | Totale selezionato live / tip volume (corpo JSON, senza curl) |

### 6.4 Hook (registrati all’installazione)

`displayHeader`, `displayProductFooter`, `displayFooterProduct`, `displayProductTab`, `displayProductExtraContent`, `displayProductTabContent`, `CombinationsTable`, `ActionAdminControllerSetMedia`, `displayCustomerAccount`, `actionUpdateQuantity`.

Nessun `enable()` / `disable()` personalizzato oltre ai default PrestaShop. Uninstall elimina le tabelle funzionalità poi `parent::uninstall()`.

### 6.5 Override

Il modulo non fornisce override di classe/controller sotto `override/`. Gli override di template `.tpl` del modulo nel tema sono opzionali e lato rivenditore.

### 6.6 Database

Uninstall elimina queste tabelle; le chiavi Configuration vengono mantenute.

| Table | Content |
|---|---|
| `ctp_wishlist` | `id_ctp_wishlist`, customer/guest, product, combination, shop, `date_add` |
| `ctp_backinstock` | Iscrizioni email, product/combination, shop, lang, `notified`, dates |
| `ctp_entity_settings` | `entity_type`, `id_entity`, JSON `settings`, `date_upd` |

### 6.7 Chiavi di configurazione e default (installazione)

Default selezionati scritti all’installazione: `ctp_position` = `productFooter`, `ctp_where` = `1`, `ctp_view_mode` = `list`, `ctp_image`/`ctp_price`/`ctp_reference`/`ctp_cname`/`ctp_atc`/`ctp_atcq`/`ctp_ajax`/`ctp_sort`/`ctp_quantity`/`ctp_availability`/`ctp_availability_d` = `1`, `ctp_ean`/`ctp_mpn` = `0`, `ctp_wishlist`/`ctp_bis`/`ctp_export`/`ctp_csv_import`/`ctp_reorder` = `0`, `ctp_group_rules` = `{}`, `ctp_column_order` = JSON da `CtpColumnRegistry::defaultKeys()`, più chiavi tasse/nascondi/griglia correlate come in `install()`. L’ordine colonne/celle usa anche JSON (`ctp_column_order`, `ctp_grid_cell_order`). Traduzioni: `translations/{iso}.php`. I testi `desc` dei campi vivono principalmente in `CtpAdminBo`.

### 6.8 Estensione

Sovrascriva i template FO dal tema sotto `modules/combinationstab/...` senza modificare il pacchetto del modulo. Il tema deve continuare a chiamare gli hook prodotto registrati per l’output. L’integrazione opzionale Combination features richiede `lib/CtpCombfeat.php` presente e `CtpCombfeat::isAvailable()` true.

## 7. Supporto

Pagina prodotto: https://mypresta.eu/modules/front-office-features/product-page-combinations-table.html

Per ottenere aiuto: acceda al suo account cliente su mypresta.eu, apra Contact e scelga **Support for paid modules**. Il form richiede il login per i moduli a pagamento; dopo il login, scelga questo modulo dalla cronologia acquisti.
