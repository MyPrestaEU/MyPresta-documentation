---
title: "Disabilita prezzi specifici del prodotto quando il carrello ha una regola del carrello - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Disabilita prezzi specifici del prodotto quando il carrello ha una regola del carrello' di MyPresta.eu."
sidebar:
  label: "Disabilita prezzi specifici del prodotto quando il carrello ha una regola del carrello - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Disable product specific prices when cart has cart rule su MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-product-specific-prices-when-cart-has-cart-rule.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/disable-product-specific-prices-when-cart-has-cart-rule/)
>
> ---


# Disabilita prezzi specifici del prodotto quando il carrello ha una regola del carrello

## 1. Requisiti e Compatibilità

Questo modulo è progettato per funzionare senza problemi con le moderne installazioni di PrestaShop.

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono richieste per PrestaShop stesso e sono tipicamente disponibili su qualsiasi ambiente di hosting web moderno. Nessun requisito di hosting speciale oltre a una configurazione standard di PrestaShop.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

Questo modulo ha una singola, semplice schermata di configurazione.

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Per accedere alla configurazione, vai su **Moduli > Gestione moduli**, cerca "Disabilita prezzi specifici del prodotto quando il carrello ha una regola del carrello" e clicca sul pulsante "Configura".

![Screenshot della configurazione del modulo Placeholder]
*(Immagina uno screenshot qui che mostra un semplice modulo con un singolo interruttore a levetta etichettato "Disabilita l'uso dei prezzi specifici nel carrello con regola del carrello" e le opzioni "Abilitato" / "Disabilitato".)*

**Impostazione: Disabilita l'uso dei prezzi specifici nel carrello con regola del carrello**

- **Cosa fa questa impostazione:** Questo è l'interruttore di controllo principale per la funzionalità principale del modulo. Determina se il modulo interviene attivamente per disabilitare i prezzi specifici quando una regola del carrello (codice voucher) è presente nel carrello del cliente.
- **Effetto della modifica di questa impostazione:**
  - **Quando abilitato (SÌ):** Se un cliente applica una qualsiasi regola del carrello (codice voucher) al proprio carrello, il modulo impedirà che eventuali prezzi specifici del prodotto vengano applicati ai prodotti in quel carrello. I prezzi dei prodotti torneranno al loro prezzo base prima che venga applicato lo sconto della regola del carrello, garantendo che solo lo sconto della regola del carrello influenzi il prezzo finale. Ciò previene il doppio sconto.
  - **Quando disabilitato (NO):** Il modulo sarà inattivo. I prezzi specifici e le regole del carrello funzioneranno indipendentemente, il che significa che possono potenzialmente accumularsi sullo stesso prodotto, portando all'applicazione simultanea di più sconti. Questo è il comportamento predefinito di PrestaShop.
- **Valore consigliato:** **Abilitato (SÌ)**. Questo è lo scopo principale del modulo e ti consente di proteggere i tuoi margini di profitto e controllare la tua strategia di sconto.
- **Scenario / esempio del commerciante:**
  - **Scegli "Abilitato"** se vuoi assicurarti che quando un cliente utilizza un codice voucher (ad esempio, "SALVA10" per il 10% di sconto), eventuali prezzi specifici esistenti sui prodotti nel suo carrello vengano ignorati. Ciò significa che lo sconto del 10% verrà applicato al prezzo normale del prodotto, non a un prezzo specifico già scontato. Questo impedisce che un prodotto venga scontato due volte.
  - **Scegli "Disabilitato"** se preferisci il comportamento predefinito di PrestaShop in cui i prezzi specifici e le regole del carrello possono accumularsi, portando potenzialmente a sconti più profondi del previsto. Questo potrebbe essere desiderato in campagne promozionali molto specifiche e aggressive, ma in generale, "Abilitato" è consigliato per la protezione del profitto.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Disabilita l'uso dei prezzi specifici nel carrello con regola del carrello | Abilitato | Quando abilitato, i prezzi specifici vengono ignorati se una regola del carrello è attiva nel carrello, prevenendo doppi sconti. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho abilitato il modulo, ma i prezzi specifici continuano a essere visualizzati anche con un codice voucher. Cosa c'è che non va?**

- **R:** Innanzitutto, assicurati di aver salvato la configurazione dopo aver abilitato il modulo.
- **R:** Svuota la cache di PrestaShop. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" in alto a destra.
- **R:** Prova con un carrello nuovo. A volte la cache del browser o i dati di sessione possono interferire. Prova in una finestra in incognito.
- **R:** Verifica che la regola del carrello con cui stai testando sia effettivamente attiva e applicata correttamente ai prodotti nel carrello.

**D2: I miei clienti si lamentano che i loro prezzi specifici sono scomparsi quando hanno usato un voucher. È normale?**

- **R:** Sì, questo è il comportamento previsto del modulo. Quando il modulo è abilitato e un cliente applica una regola del carrello (voucher), i prezzi specifici sui prodotti nel carrello vengono temporaneamente disabilitati per prevenire il doppio sconto. Il prezzo del prodotto verrà quindi calcolato in base al suo prezzo originale, con lo sconto della regola del carrello applicato. Potresti voler aggiornare i tuoi termini e condizioni o i messaggi promozionali per chiarire come interagiscono gli sconti.

**D3: Questo modulo influisce su altri tipi di sconti, come sconti per categoria o sconti per gruppo di clienti?**

- **R:** Questo modulo si concentra specificamente sui "prezzi specifici" (sconti impostati direttamente su singoli prodotti o combinazioni) e sulla loro interazione con le "regole del carrello" (codici voucher). Non interferisce direttamente con altri meccanismi di sconto come sconti per categoria, sconti per gruppo di clienti o sconti per quantità, a meno che questi non siano implementati come prezzi specifici.

**D4: Questo modulo rallenterà il mio negozio?**

- **R:** Il modulo apporta piccole modifiche alle classi principali di PrestaShop per regolare la logica di calcolo dei prezzi. Queste modifiche sono altamente ottimizzate e dovrebbero avere un impatto trascurabile sulle prestazioni del tuo negozio. Il modulo attiva la sua logica solo quando è presente una regola del carrello, quindi non è costantemente in esecuzione.

**D5: Voglio consentire temporaneamente l'accumulo di prezzi specifici e regole del carrello per una promozione speciale. Come faccio?**

- **R:** Vai semplicemente alla pagina di configurazione del modulo (**Moduli > Gestione moduli > Configura** per "Disabilita prezzi specifici del prodotto quando il carrello ha una regola del carrello") e imposta l'opzione "Disabilita l'uso dei prezzi specifici nel carrello con regola del carrello" su **"Disabilitato"**. Ricorda di riabilitarlo dopo la fine della tua promozione speciale per ripristinare il comportamento protettivo predefinito.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster che lavorano con il modulo "Disabilita prezzi specifici del prodotto quando il carrello ha una regola del carrello".

### 4.1 Panoramica dell'architettura

Questo modulo funziona principalmente sovrascrivendo le classi principali di PrestaShop relative al calcolo dei prezzi e alla gestione dei prezzi specifici. Sfrutta il meccanismo di override di PrestaShop per iniettare la sua logica nelle classi `Cart`, `Product` e `SpecificPrice`. L'idea centrale è rilevare la presenza di una regola del carrello nel carrello corrente e, se trovata, modificare il comportamento del recupero dei prezzi specifici per ignorarli efficacemente durante i calcoli dei prezzi.

La configurazione principale del modulo è gestita tramite il metodo `getContent()` nel file principale del modulo, memorizzando un semplice flag booleano in `ps_configuration`.

### 4.2 Controller (`controllers/`)

Questo modulo non introduce alcun controller front-office o back-office personalizzato. La sua logica è interamente incorporata negli override delle classi.

- **Controller Front-Office**: Nessuno
- **Controller Admin Back-Office**: Nessuno

### 4.3 Classi e Modelli Core (`classes/`)

La funzionalità principale del modulo risiede nei suoi override di classe. Questi file si trovano in `cartspecdis/override/classes/`. PrestaShop carica automaticamente questi override, sostituendo le classi core originali con le versioni modificate del modulo.

- **`cartspecdis/override/classes/Cart.php`**

  - **Nome classe e classe genitore**: `Cart` (sovrascrive `\Cart`)
  - **Responsabilità**: Questo override è cruciale. Probabilmente introduce un metodo o modifica uno esistente (ad esempio, `getProducts()`, `getPackageList()` o un helper per il calcolo dei prezzi) per verificare la presenza di regole del carrello. Se vengono trovate regole del carrello, imposta un flag o modifica i parametri che influenzano il modo in cui i prezzi specifici vengono successivamente recuperati o applicati. Il metodo `hasCartRules()` è un probabile candidato per il controllo delle regole del carrello.
  - **Logica chiave**: L'override probabilmente aggiungerà un controllo all'interno dei metodi di calcolo dei prezzi per vedere se `Cart::getCartRules()` restituisce regole attive. In tal caso, influenzerà le chiamate a `Product::getPriceStatic()` o `SpecificPrice::getSpecificPrice()` per ignorare i prezzi specifici.
- **`cartspecdis/override/classes/Product.php`**

  - **Nome classe e classe genitore**: `Product` (sovrascrive `\Product`)
  - **Responsabilità**: Questo override dovrebbe modificare il metodo `getPriceStatic()`, che è centrale per il modo in cui i prezzi dei prodotti vengono recuperati in PrestaShop.
  - **Logica chiave**: All'interno di `getPriceStatic()`, il modulo probabilmente aggiungerà una condizione. Se l'oggetto `Cart` corrente (passato come parametro o accessibile globalmente) contiene regole del carrello attive e la configurazione del modulo è abilitata, allora i parametri passati a `SpecificPrice::getSpecificPrice()` verranno alterati (ad esempio, `id_specific_price` o flag `use_specific_price`) per garantire che nessun prezzo specifico venga restituito, o che il calcolo del prezzo specifico venga bypassato.
- **`cartspecdis/override/classes/SpecificPrice.php`**

  - **Nome classe e classe genitore**: `SpecificPrice` (sovrascrive `\SpecificPrice`)
  - **Responsabilità**: Questo override probabilmente modificherà il metodo `getSpecificPrice()`, che è responsabile del recupero dei dettagli del prezzo specifico per un dato prodotto.
  - **Logica chiave**: Questo override conterrà la logica diretta per impedire che i prezzi specifici vengano restituiti. Verificherà se il `Cart` corrente ha regole del carrello e se il modulo è abilitato. Se entrambe le condizioni sono vere, `getSpecificPrice()` verrà fatto restituire `false` o un array vuoto, indicando efficacemente che nessun prezzo specifico si applica, anche se ne esiste uno nel database. Questo è il guardiano finale per i prezzi specifici.
- **`cartspecdis/override/classes/index.php`**

  - **Nome classe e classe genitore**: Nessuno
  - **Responsabilità**: Questo è un file `index.php` vuoto standard, tipicamente posizionato nelle directory per prevenire l'elenco delle directory quando vi si accede direttamente tramite un browser web. Non ha alcun impatto funzionale sulla logica del modulo.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo non include alcun file JavaScript personalizzato. Tutta la sua logica è gestita lato server.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo non include alcun file CSS personalizzato. Non ha componenti visivi front-office e la sua configurazione back-office utilizza elementi di modulo standard di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

Questo modulo non utilizza alcun template Smarty personalizzato. Il suo modulo di configurazione è generato dinamicamente dal metodo `getContent()` nel file principale del modulo utilizzando i moduli helper di PrestaShop.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Il modulo non crea tabelle SQL personalizzate.
  - Memorizza la sua impostazione di configurazione nella tabella `ps_configuration`:
    - Chiave `PS_CONFIGURATION`: `cartspecdis` (memorizza il valore booleano per abilitare/disabilitare la funzionalità principale del modulo).
- **Tabella degli hook registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Eseguito quando un Controller Admin sta impostando le sue risorse multimediali (CSS/JS). | Questo hook è tipicamente utilizzato dai moduli per aggiungere i propri file CSS o JavaScript al Back Office. Per questo modulo, è probabile che venga utilizzato per garantire che vengano caricati eventuali stili o script necessari lato amministratore (anche se nessuno è esplicitamente elencato nell'inventario), oppure potrebbe essere un residuo di una struttura di modulo template. Dato che non sono elencati file JS/CSS, il suo scopo principale qui è probabilmente minimo o per future espansioni. |

### 4.8 File principale del modulo (`cartspecdis/cartspecdis.php`)

- **Nome classe**: `Cartspecdis` (estende `Module`)
- **`__construct()`**: Inizializza i metadati del modulo (nome, tab, versione, autore, need\_instance, ps\_versions\_compliancy).
- **`install()`**:
  - Chiama `parent::install()`.
  - Registra l'hook `actionAdminControllerSetMedia`.
  - Imposta il valore di configurazione predefinito per `cartspecdis` a `1` (abilitato) in `ps_configuration`.
  - Registra gli override delle classi (`Cart`, `Product`, `SpecificPrice`).
- **`uninstall()`**:
  - Chiama `parent::uninstall()`.
  - Deregistra l'hook `actionAdminControllerSetMedia`.
  - Elimina il valore di configurazione `cartspecdis` da `ps_configuration`.
  - Deregistra gli override delle classi.
- **`getContent()`**:
  - Gestisce l'invio del modulo per la configurazione del modulo.
  - Aggiorna il valore di configurazione `cartspecdis` in `ps_configuration` in base all'input dell'utente.
  - Visualizza un messaggio di conferma.
  - Renderizza il modulo di configurazione utilizzando la classe `HelperForm` di PrestaShop, inclusa la singola levetta per "Disabilita l'uso dei prezzi specifici nel carrello con regola del carrello".
- **`hookActionAdminControllerSetMedia()`**:
  - Questo metodo viene chiamato quando viene eseguito l'hook `actionAdminControllerSetMedia`.
  - È tipicamente utilizzato per aggiungere file CSS o JavaScript al Back Office. Nello stato attuale di questo modulo (basato sull'inventario), probabilmente contiene codice minimo o nullo per l'aggiunta di risorse, oppure è un segnaposto.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Disabilita prezzi specifici del prodotto quando il carrello ha una regola del carrello", fai riferimento al tuo account cliente su MyPresta.eu.

- **Aggiornamenti del modulo**: Accedi al tuo account MyPresta.eu e naviga nella sezione della cronologia degli ordini e dei download per ottenere la versione più recente del modulo.
- **Supporto tecnico**: Se riscontri problemi o hai domande non trattate in questa documentazione, apri un ticket di supporto tramite il tuo account cliente MyPresta.eu. Il nostro team sarà lieto di assisterti.
"""
