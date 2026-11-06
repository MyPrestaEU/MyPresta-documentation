---
title: "Cart Conditions - documentazione e manuale utente"
sidebar:
  label: "Cart Conditions - documentazione e manuale utente"
description: "Manuale di configurazione e di risoluzione dei problemi per i negozi che usano già Cart Conditions."
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Cart conditions pro su MyPresta.eu](https://mypresta.eu/modules/ordering-process/cart-conditions-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/cart-conditions-pro/)
>
> ---


## 1. Requisiti

Cart Conditions gira dentro il negozio. Non serve un altro modulo e non serve un account su un servizio esterno.

- PrestaShop 1.7, 8 e 9. Questo manuale è stato verificato su PrestaShop 9.2.0.
- La versione di PHP richiesta da quella versione di PrestaShop. Il modulo non chiede un'estensione PHP in più.
- Non serve nessun altro modulo.
- Le regole leggono il carrello corrente. La dimensione del catalogo non cambia il controllo.

## 2. Installazione

1. Apra **Moduli**, poi **Module Manager**.
2. Carichi lo zip e installi il modulo. L'installazione lo attiva.
3. Apra **Catalogo**. Compaiono cinque voci, in questo ordine. I nomi restano in inglese in ogni lingua del back office:

- **Cart Conditions**
- **Cart Value Conditions**
- **Cart Quantity Conditions**
- **Cart Associations Conditions**
- **Cart value by country conditions**

L'installazione non svuota la cache del negozio.

La disinstallazione toglie queste cinque voci e sgancia il modulo. Lascia le regole salvate, l'elenco delle esclusioni, l'impostazione di disponibilità e l'impostazione degli avvisi. Una nuova installazione riporta il menu, e le regole vecchie sono ancora lì.

## 3. Configurazione e lavoro quotidiano

Il cliente riempie il carrello. Nella pagina del carrello il negozio elenca ogni regola infranta in un avviso rosso. Se il cliente prosegue verso il pagamento, il negozio lo rimanda al carrello finché ogni regola attiva non è rispettata. Un cliente di **Exclude customers from conditions** salta ogni regola e può ordinare.

Prepari il negozio in questo ordine:

1. Apra **Configure** e decida chi e quali prodotti le regole ignorano.
2. Decida se le date di disponibilità future si possono mescolare.
3. Apra ogni elenco sotto **Catalogo**, clicchi **Add new**, compili il modulo, metta **Active** su **On** e clicchi **Save**.
4. Faccia un ordine di prova con un cliente normale e con un cliente escluso.

Un modulo nuovo si apre con **Active** su **Off**. **Save** registra la riga e il carrello la ignora finché non mette **On**. La pagina di configurazione risponde **Saved**. Gli elenchi mostrano la conferma abituale del back office dopo **Save**.

La nota blu di **Configure** dice: "Management of this module is located under Price Rules menu." I cinque link di quella nota, e le voci sotto **Catalogo**, aprono gli elenchi. Questo modulo non aggiunge una voce in Price Rules.

Le schermate di questo manuale sono il back office inglese. Pulsanti e campi hanno il nome che si vede lì.

![Link della configurazione](https://mypresta.eu/docs/images/docs/cartcon-configure-links.webp)

### 3.1 Pagina di configurazione

Apra **Moduli**, **Module Manager**, trovi **Cart Conditions** e clicchi **Configure**.

#### Escludere clienti e prodotti

![Modulo delle esclusioni](https://mypresta.eu/docs/images/docs/cartcon-configure-exclude.webp)

Cerchi un cliente, clicchi il risultato e quella persona entra nell'elenco di esclusione. Tolga una persona dallo stesso elenco prima di salvare. I clienti esclusi saltano ogni regola del carrello, anche il controllo di disponibilità.

| Campo | Valore iniziale | Cosa fa |
|---|---|---|
| **Exclude customers from conditions** | vuoto | I clienti di questo elenco ordinano senza regole di carrello. **Save** registra l'elenco. |
| **Exclude products from conditions** | **Do not exclude products** | **Exclude selected products** fa ignorare alle regole i prodotti e le categorie scelti. **Do not exclude products** conta ogni prodotto. |
| **Categories** | nessuna selezionata | Le categorie selezionate si saltano quando l'interruttore sopra è **Exclude selected products**. |
| **Save** | - | Registra clienti, interruttore, prodotti e categorie. La pagina mostra **Saved**. |

La ricerca prodotti e l'albero delle categorie stanno sullo stesso modulo. Scelga un prodotto come sceglie un cliente: cerchi, poi clicchi il risultato.

#### Condizioni globali

![Confronto delle disponibilità](https://mypresta.eu/docs/images/docs/cartcon-configure-availability.webp)

Il controllo guarda solo i prodotti senza giacenza la cui **Availability date** è ancora nel futuro. I prodotti disponibili, quelli con data vuota o passata, e i prodotti esclusi restano fuori. Una sola data futura nel carrello non blocca. Due o più valori diversi bloccano.

| Campo | Valore iniziale | Cosa fa |
|---|---|---|
| **Block order of products with Various availabiltiy date** | **Off** | **On** blocca il carrello quando quelle date future non coincidono con il confronto sotto. **Off** salta il controllo. PrestaShop può già permettere un ordine per un prodotto che sarà disponibile più tardi. Questo interruttore decide se date diverse possono stare nello stesso carrello. |
| **How to compare availability dates** | **Exact date** | **Exact date** blocca quando le date future non sono lo stesso giorno. **Same calendar month** permette giorni diversi dello stesso mese e anno, e blocca quando cambiano mese o anno. Il 5 novembre 2026 e il 20 novembre 2026 passano. Il 2 dicembre 2026 no. Il 5 novembre 2027 no. |
| **Save** | - | Registra l'interruttore e il confronto. La pagina mostra **Saved**. Questo pulsante non crea una regola del Catalogo. |

Testo del carrello per **Exact date**: "Availability dates of products in your cart are different. You cant place an order." Per **Same calendar month**: "Availability months of products in your cart are different. You cant place an order."

#### Aggiornamenti MyPresta

![Controllo aggiornamenti](https://mypresta.eu/docs/images/docs/cartcon-configure-updates.webp)

| Campo | Valore iniziale | Cosa fa |
|---|---|---|
| **Check updates** / **Check now** | - | Chiede a MyPresta se esiste un file più recente. **Module is up to date!** significa che questo file è aggiornato. **New version available!** significa che un file più recente è pubblicato. Il pulsante non lo installa. |
| **Updates notifications** | **Disable** | **Enable** mostra un avviso nel back office quando esce una versione più recente. **Disable** resta in silenzio. **Save** registra la scelta. |
| **Module page** | link | Apre la pagina del modulo, dove c'è l'elenco delle modifiche. |
| **Save** | - | Registra la scelta degli avvisi. |

### 3.2 Cart Conditions

Apra **Catalogo**, poi **Cart Conditions**. Queste regole valgono per ogni cliente che non è escluso. Questo elenco non ha un campo gruppo clienti.

![Elenco Cart Conditions](https://mypresta.eu/docs/images/docs/cartcon-conditions-list.webp)

Colonne: **ID**, **Cart condition**, **Target type**, **Target item** e **Active**. Un negozio vuoto mostra **No records found**. I filtri stanno sopra le colonne. Azioni di riga: modifica, elimina, icona **Active**. Azione di massa: elimina. **Add new** apre il modulo.

![Nuova regola Cart Conditions](https://mypresta.eu/docs/images/docs/cartcon-conditions-form.webp)

| Campo | Valore iniziale | Cosa fa |
|---|---|---|
| **Condition** | **Must have** | **Must have** esige il bersaglio. **Can't have** lo blocca. |
| **Target type** | **Category** | **Category** usa un id di categoria. **Product** usa un id di prodotto. **More than defined number of products** usa un numero di pezzi di tutto il carrello. |
| **Target item** | vuoto | Id di categoria, id di prodotto o numero di pezzi. Il suggerimento del campo chiede un id o un numero di prodotti. |
| **Active** | **Off** | **On** fa controllare la riga dal carrello. **Off** tiene la riga e la salta. |
| **Save** | - | Registra la regola. |

Cosa vede il cliente:

- **Must have** e **Category**: "To place an order you must order product from category: ...".
- **Can't have** e **Category**: "Your cart contains product from forbidden category: .... To continue order please remove it from cart."
- **Must have** e **Product**: "To place an order you must order product: ...".
- **Can't have** e **Product**: "Your cart contains forbidden product: .... To continue order please remove it from cart."
- **Must have** e un numero di pezzi: "Your cart contains less products than required (...). To continue order please increase quantity of products in your cart".
- **Can't have** e un numero di pezzi: "Your cart contains more products than allowed (...). To continue order please decrease quantity of products in your cart".

Il numero di pezzi è la somma delle quantità nel carrello, dopo aver tolto i prodotti esclusi. **Must have** esige che il carrello raggiunga quel numero. **Can't have** blocca un carrello sopra quel numero.

### 3.3 Cart Value Conditions

Apra **Catalogo**, poi **Cart Value Conditions**. Ogni riga è un gruppo clienti, una categoria e un importo minimo.

![Elenco valori](https://mypresta.eu/docs/images/docs/cartcon-value-list.webp)

Colonne: **ID**, **Customer group**, **Cart condition**, **Target**, **Value** e **Active**. Elenco vuoto: **No records found**. Azioni di riga: modifica, elimina, icona **Active**. Azione di massa: elimina. **Add new** apre il modulo.

![Nuova regola di valore](https://mypresta.eu/docs/images/docs/cartcon-value-form.webp)

| Campo | Valore iniziale | Cosa fa |
|---|---|---|
| **Customer Group** | primo gruppo del negozio (Visitor in un negozio predefinito) | Si controllano solo gli acquirenti di quel gruppo. Un cliente connesso si controlla in ogni gruppo a cui appartiene. |
| **Condition** | **Must order from selected category** | È l'unica scelta. La regola agisce quando il carrello contiene già quella categoria. |
| **Target item** | vuoto | Id di categoria. |
| **Value** | vuoto | Totale minimo IVA inclusa dei prodotti di quella categoria. Lo scriva nella valuta predefinita del negozio. Il segno di valuta del modulo è la valuta del negozio. |
| **Active** | **Off** | **On** applica la riga. **Off** la registra senza usarla. |
| **Save** | - | Registra la regola. |

Se la categoria manca nel carrello, la regola tace. Se c'è e il totale IVA inclusa è sotto **Value**, il carrello mostra: "To place an order you must order for: ... from category: ...".

### 3.4 Cart Quantity Conditions

Apra **Catalogo**, poi **Cart Quantity Conditions**.

![Elenco quantità](https://mypresta.eu/docs/images/docs/cartcon-quantity-list.webp)

Colonne: **ID**, **Customer group**, **Cart condition**, **Target**, **Quantity** e **Active**. Elenco vuoto: **No records found**. Azioni di riga: modifica, elimina, icona **Active**. Azione di massa: elimina.

![Nuova regola di quantità](https://mypresta.eu/docs/images/docs/cartcon-quantity-form.webp)

| Campo | Valore iniziale | Cosa fa |
|---|---|---|
| **Customer Group** | primo gruppo del negozio | Si controlla solo quel gruppo. |
| **Condition** | **Must order at least X products from selected category** | Scelga il limite. L'elenco completo è sotto. |
| **Target country** | primo paese del negozio | Usato solo per le due regole "from Y category". Per ogni altra condizione la pagina nasconde questo elenco. |
| **Target item** | vuoto | Id di categoria, prodotto, produttore, oppure valore attributo, secondo **Condition**. Il suggerimento chiede l'id del bersaglio. Per le condizioni di tutto il carrello la pagina mette la parola Cart e blocca il campo. |
| **Quantity** | vuoto | Il numero X della condizione scelta. |
| **Accept only multiplied qty** | **Off** | **On** accetta solo multipli di **Quantity**, per esempio 6, 12, 18, 24 quando **Quantity** è 6. **Off** accetta qualsiasi numero che rispetta la regola. |
| **Active** | **Off** | **On** applica la riga. |
| **Save** | - | Registra la regola. |

Scelte di **Condition**, nell'ordine del modulo:

- **Must order at least X products from selected category**
- **Can't more than X products from selected category**
- **Must order at least X products from selected manufacturer**
- **Can't more than X products from selected manufacturer**
- **Must order at least X quantity of selected product**
- **Can't order more than X quantity of selected product**
- **Must order at least X quantity of each product**
- **Can't order more than X quantity of each product**
- **Can't order more than X products with the same attribute value**
- **Cart must have at least X products**
- **Cart can't have more than X products**
- **Cart must have at least X different products**
- **Cart can't have more than X different products**
- **Cart of user from selected country must have more than X products**
- **Cart of user from selected country can't have more than X products**
- **Cart of user from selected country must have more than X products from Y category**
- **Cart of user from selected country can't have more than X products from Y category**

Per le ultime due imposti **Target country** e metta l'id di categoria in **Target item**. Per le due regole di paese senza categoria la pagina nasconde **Target country**, quindi lì non sceglie un paese. Usi **Cart value by country conditions** per un limite in denaro. Usi le ultime due regole di quantità per un numero di pezzi di una categoria.

**Search for attribute value** compare solo per **Can't order more than X products with the same attribute value**. Cerchi, clicchi un valore, e quel valore diventa **Target item**.

Il testo del carrello segue la scelta. Le regole di categoria e produttore dicono "at least" o "can't order more than" e nominano categoria o produttore. Una regola prodotto cita la quantità attuale. Una regola di tutto il carrello dice "you must order more than" o "you can't order more than" e cita la quantità attuale. Con **Accept only multiplied qty** su **On**, il carrello aggiunge: "We accept only multiplied quantity...".

Nella scheda prodotto il tema può mostrare "You must order at least: ... quantity of this product" per **Must order at least X quantity of selected product**, quando quel prodotto è il bersaglio e il visitatore corrisponde al gruppo. È un avviso. Il blocco avviene nel carrello.

### 3.5 Cart Associations Conditions

Apra **Catalogo**, poi **Cart Associations Conditions**. Una riga collega un elemento a un altro per un gruppo clienti. La regola parte solo quando il primo elemento è già nel carrello.

![Elenco associazioni](https://mypresta.eu/docs/images/docs/cartcon-associations-list.webp)

Colonne: **ID**, **Customer group**, **Cart condition**, **Target item (1)**, **Associated item (2)** e **Active**. Elenco vuoto: **No records found**. Azioni di riga: modifica, elimina, icona **Active**. Azione di massa: elimina.

![Nuova associazione](https://mypresta.eu/docs/images/docs/cartcon-associations-form.webp)

| Campo | Valore iniziale | Cosa fa |
|---|---|---|
| **Active** | **Off** | **On** applica la riga. |
| **Type of condition** | **Associations between product and product** | **Associations between product and category** o **Associations between category and category** cambia il senso dei due id. |
| **For what customer group** | primo gruppo del negozio | Si controlla solo quel gruppo. |
| **Target item (1)** | vuoto | Id di prodotto o di categoria. La regola agisce quando il cliente mette quell'oggetto nel carrello. |
| **Condition** | **If customer will add to cart Target item (1) then it must order Associated item (2)** | Le scelte sono sotto. |
| **Associated item (2)** | vuoto | L'id di prodotto o categoria richiesto o vietato. |
| **Save** | - | Registra la coppia. |

Scelte di **Condition**:

- **If customer will add to cart Target item (1) then it must order Associated item (2)**. Testo: "If your cart has a product: ... you must order also product: ..." oppure l'equivalente di categoria.
- **If customer will add to cart Target item (1) then cart must have at least one different product**. Visibile solo per prodotto e prodotto. Il controllo del carrello non mostra un messaggio per questa scelta. Usi un'altra scelta quando il carrello deve bloccare.
- **If customer will add to cart Target item (1) then it will be forbidden to order Associated item (2)**. Testo: "If your cart has a product: ... you can't place an order for: ...".
- **If customer will add to cart Target item (1) then it will be forbidden to add any other product to cart**. La pagina nasconde **Associated item (2)**. Testo: "If your cart has a product: ... you can't place an order for any other product."
- **If customer will add to cart Target item (1) then it will be forbidden to add products from categories other than Target item (1)**. Visibile solo per categoria e categoria. La pagina nasconde **Associated item (2)**.

Il modulo contiene anche **Include subcategories of Target item (1)** e **Include subcategories of Associated item (2)**. La pagina nasconde entrambi gli interruttori per ogni tipo. La regola usa gli id che scrive.

### 3.6 Cart value by country conditions

Apra **Catalogo**, poi **Cart value by country conditions**. La regola usa il paese dell'indirizzo di consegna.

![Elenco importi per paese](https://mypresta.eu/docs/images/docs/cartcon-country-list.webp)

Colonne: **ID**, **Customer group**, **Condition**, **Country**, **Value** e **Active**. Elenco vuoto: **No records found**. Azioni di riga: modifica, elimina, icona **Active**. Azione di massa: elimina.

![Nuovo importo per paese](https://mypresta.eu/docs/images/docs/cartcon-country-form.webp)

| Campo | Valore iniziale | Cosa fa |
|---|---|---|
| **Customer Group** | primo gruppo del negozio | Si controlla solo quel gruppo. |
| **Target country** | primo paese del negozio | La regola agisce quando l'indirizzo di consegna è di quel paese. L'elenco è quello dei paesi del negozio. |
| **Condition** | **Cart must be worth at least ...** | **Cart can't be worth more than ...** è il massimo. |
| **Condition tax** | **Tax included** | **Tax excluded** confronta il totale senza imposta. Il messaggio del carrello ripete l'etichetta di imposta scelta. |
| **Cart value type** | **Products + shipping** | **Products** lascia la spedizione fuori dal totale confrontato. |
| **Value** | vuoto | L'importo, nella valuta predefinita del negozio. |
| **Active** | **Off** | **On** applica la riga. |
| **Save** | - | Registra la regola. |

Sotto il minimo il carrello mostra: "To place an order from country: ... your cart must be worth at least ..., while you cart is worth ...". Sopra il massimo: "To place an order from country: ... your cart can't be worth more than ..., while you cart is worth ...".

## 4. Negozio

Il cliente non apre una pagina a parte. Il modulo parla nella scheda prodotto e nel carrello.

Nella scheda, e solo con una regola attiva **Must order at least X quantity of selected product** puntata su quel prodotto, il tema può mostrare: "You must order at least: ... quantity of this product". Il tema deve stampare l'area azioni del prodotto. Questo manuale non ha una foto del negozio, perché quella riga non è stata confermata sul tema di prova.

Nel carrello ogni regola infranta è una riga di un solo avviso rosso. I nomi di prodotti e categorie richiesti o vietati sono link. Se il cliente apre il pagamento con una regola infranta, il negozio lo rimanda al carrello e mostra lo stesso avviso.

Un cliente dell'elenco di esclusione non vede questi messaggi e non viene rimandato indietro.

Non c'è un indirizzo del negozio da copiare. Non c'è un modulo con cui il cliente accetta o rifiuta una regola.

## 5. Problemi

**Mancano le cinque voci sotto Catalogo.** Il modulo non è installato, oppure è stato disinstallato. Lo installi di nuovo da **Module Manager**. Le regole vecchie tornano con lui.

**La nota blu parla di Price Rules e in Price Rules non c'è Cart Conditions.** Usi i cinque link della nota, oppure **Catalogo**. Il genitore del menu è Catalogo.

**Una regola salvata non fa nulla.** **Active** è **Off**, il cliente è nell'elenco di esclusione, oppure non è nel gruppo scelto. Un visitatore non connesso si controlla come gruppo Visitor. Apra la riga, metta **Active** su **On** e provi con un cliente di quel gruppo.

**Una regola di valore tace.** La categoria non è nel carrello. Aggiunga un prodotto di quella categoria. Il totale confrontato è IVA inclusa.

**Due regole di quantità per paese ignorano il paese.** **Target country** è nascosto finché **Condition** non è una delle due righe "from Y category". Ne scelga una, oppure usi **Cart value by country conditions** per un limite in denaro.

**Same calendar month blocca ancora novembre e novembre.** Gli anni sono diversi. Il 5 novembre 2026 e il 5 novembre 2027 sono valori diversi. Il prodotto deve anche essere senza giacenza e con **Availability date** futura. I prodotti disponibili non si confrontano.

**Check now non mostra nulla, oppure l'avviso non compare.** Il server del negozio non può aprire l'indirizzo remoto di MyPresta. **Check now** segnala solo una versione. Non scarica e non installa il file. Apra **Module page** e prenda il file nuovo da lì.

**Manca l'avviso nel carrello e il pagamento torna comunque al carrello.** Il tema non stampa il blocco del carrello. Il ritorno al carrello funziona lo stesso. Sovrascriva il template del carrello nel tema, oppure verifichi che il tema chiami l'hook del carrello.

**La disinstallazione ha tolto il menu e un'installazione successiva mostra le regole vecchie.** È il comportamento della disinstallazione. Cancelli le righe degli elenchi prima di disinstallare se dopo vuole il modulo vuoto.

## 6. Per lo sviluppatore

### 6.1 Panoramica

Classe principale `cartcon`, versione 2.1.9, nome in elenco **Cart Conditions**, autore MyPresta.eu, scheda `advertising_marketing`. `cartconPrestashopNewCompatibility` estende `cartcon` per il formato dei prezzi e non è l'istanza del modulo. `psversion()` mappa una major 8 o superiore sul ramo 1.7 per alcune scelte di markup del back office. Non c'è override di `enable()` né di `disable()`.

`getRestrictions()` legge le righe attive del negozio corrente, salta i clienti di `CARTCON_CUSTOMERS` e riempie `errors_cartcon`. `hookDisplayShoppingCart` stampa quell'elenco. `hookDisplayPaymentTop` reindirizza al carrello con `cartcon=show` quando l'elenco non è vuoto. `hookDisplayProductActions` stampa una quantità minima solo per `cartcon_quantity.c_type = 2` di quell'id prodotto.

### 6.2 File

- `cartcon.php` - installazione, moduli di configurazione, controlli, hook.
- `lib/prestashop9compatibility.php` - `cartconPrestashopNewCompatibility`.
- `controllers/admin/AdminCartConditionController.php` - must-have e can't-have.
- `controllers/admin/AdminCartValueConditionController.php` - importo minimo di categoria.
- `controllers/admin/AdminCartQuantityConditionController.php` - regole di quantità.
- `controllers/admin/AdminCartAssociationsConditionController.php` - coppie.
- `controllers/admin/AdminCartCountryConditionController.php` - importi per paese.
- `models/CartCondition.php`, `CartValueCondition.php`, `CartQuantityCondition.php`, `CartAssociationsCondition.php`, `CartCountryCondition.php` - modelli.
- `views/templates/front/displayShoppingCart.tpl` - avviso rosso.
- `views/templates/front/productActions.tpl` - minimo nella scheda.
- `views/templates/admin/script.tpl` - comportamento del modulo quantità.
- `views/templates/admin/search-attribute-value.tpl` - ricerca attributo, visibile per il tipo quantità 7.
- `lib/searchTool/searchTool.php` - `initTool()` inietta solo script. Non disegna un pannello.

### 6.3 Controller

I cinque controller admin estendono `ModuleAdminController`. `createMenu()` inserisce una scheda per lingua con il nome inglese, genitore `AdminCatalog` (`Sell > Catalog` su PrestaShop 9). Classi: `AdminCartCondition`, `AdminCartValueCondition`, `AdminCartQuantityCondition`, `AdminCartAssociationsCondition`, `AdminCartCountryCondition`. Non c'è un controller front. L'unica bandiera front letta dal modulo è `cartcon=show`, aggiunta dal redirect del pagamento.

`script.tpl` disattiva **Target item** e mette il valore `Cart` per i tipi quantità 4, 5, 8, 9, 15 e 16. La select paese si mostra per i tipi 8 e 9 e il blocco successivo la nasconde salvo che il tipo sia 10 o 11. Risultato visibile: un campo paese solo per i tipi 10 e 11. Il tipo 7 mostra `.searchAttributeValue`.

Lo script delle associazioni nasconde `.subcatt` e `.subcata` per ogni tipo. L'id condizione 4 è attivo solo per categoria-categoria (tipo 3). L'id 5 si mostra solo per prodotto-prodotto (tipo 1). Gli id 3, 4 e 5 nascondono **Associated item (2)**. `getRestrictions()` confronta `c_value` di associazione 1, 2, 3 e 4. Non confronta `c_value` 5.

### 6.4 Hook

- `displayHeader` - CSS e JS front, e la chiamata ajax `getCartConditions`.
- `displayShoppingCart` - elenco avvisi.
- `displayProductActions` - avviso di quantità minima.
- `displayPaymentTop` - ritorno al carrello quando esiste un errore.
- `actionAdminControllerSetMedia` - asset admin.

Il modulo non registra hook propri.

### 6.5 Override

Nessuno. Nessun override di classe o di controller.

### 6.6 Database

Tabelle con prefisso. `inconsistency()` / `maybeUpdateDatabase()` aggiungono le colonne mancanti in `installdb()` e dal pulsante aggiornamenti. Non girano a ogni caricamento della configurazione. La disinstallazione non cancella le tabelle.

| Tabella | Contenuto |
|---|---|
| `cartcon` | `id_cartcon`, `c_type`, `c_value`, `c_option`, `active` predefinito 1, `id_shop` aggiunto dopo. Nessun gruppo clienti. |
| `cartcon_value` | `id_cartcon_value`, `c_type`, `c_target`, `c_value`, `active`, `c_only_if_in_cart` predefinito 0, `c_group`, `id_shop`. `c_only_if_in_cart` non è nel modulo. |
| `cartcon_quantity` | `id_cartcon_quantity`, `c_type`, `c_target`, `c_value`, `active`, `c_only_if_in_cart` predefinito 0, `c_group`, `id_shop`, `multiply` predefinito 0, `c_country` predefinito 0. |
| `cartcon_ass` | `id_cartcon_ass`, `c_type`, `c_target1`, `c_target2`, `c_value`, `active`, `c_group`, `id_shop`, `subcatt` predefinito 0, `subcata` predefinito 0. L'abbinamento categorie legge `subcatt` e `subcata` quando valgono 1. Il modulo nasconde entrambi gli interruttori. |
| `cartcon_country` | `id_cartcon_country`, `c_type`, `c_target`, `c_value`, `active`, `c_group`, `id_shop`, `c_tax` predefinito 1, `c_cartValueType` predefinito 1. |

I moduli HelperForm nuovi inviano **Active** come 0 perché è selezionato Off. Il predefinito 1 della colonna vale solo se la colonna è omessa.

### 6.7 Chiavi e traduzioni

| Chiave | Se manca |
|---|---|
| `CARTCON_CUSTOMERS` | vuota. Id cliente separati da virgole. Quei clienti escono subito da `getRestrictions()`. |
| `ccon_visibility_rule` | `0` significa non escludere. `1` salta prodotti e categorie selezionati. |
| `ccon_visibility_products` | elenco vuoto di id prodotto. |
| `ccon_visibility_cat` | elenco vuoto di id categoria. |
| `CARTCON_FUTURE` | assente, trattato come spento. `1` esegue il confronto delle date. |
| `CARTCON_FUTURE_MODE` | se manca diventa `0` (**Exact date**). `1` raggruppa con `date('Y-m')`. I prodotti confrontati hanno `stock_quantity <= 0` e `available_date` strettamente nel futuro. Più di una chiave distinta blocca l'ordine. |
| `mypresta_updates` | `0` spegne l'avviso automatico. `1` lo accende. |
| `update_cartcon` | timestamp dell'ultimo controllo. |
| `updatev_cartcon` | stringa di versione dell'ultimo controllo. |

Il controllo usa `allow_url_fopen` e `file_get_contents` verso `dev.mypresta.eu`. Le traduzioni del negozio stanno in `translations/{iso}.php`. Le etichette del menu sono scritte in inglese per ogni lingua dentro `createMenu()` e non passano da un file di traduzione. Le descrizioni dei campi stanno nelle chiamate `l()` dei controller e nelle stringhe `desc` di HelperForm in `cartcon.php`. `getCustomerGroups()` mappa un carrello con `id_customer` 0 sull'id gruppo 1. Il ramo ospite gira solo quando `id_customer` non è impostato.

### 6.8 Estensione

Sovrascriva dal tema `views/templates/front/displayShoppingCart.tpl` e `views/templates/front/productActions.tpl`. Se il tema non chiama mai `displayShoppingCart` né `displayProductActions`, non c'è nulla da sovrascrivere e il cliente non vedrà l'avviso. Il redirect dal pagamento continua.

## 7. Aiuto

Pagina del modulo: [Cart Conditions Pro](https://mypresta.eu/modules/ordering-process/cart-conditions-pro.html).

Per scrivere di questo modulo entri nell'account cliente su mypresta.eu, apra il contatto e scelga **Support for paid modules**. Il modulo indica che l'accesso è obbligatorio per i moduli a pagamento. Dopo l'accesso scelga questo modulo dalla cronologia acquisti.
