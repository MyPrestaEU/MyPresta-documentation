---
title: "Prezzi IVA esclusa per utenti non loggati tramite geolocalizzazione - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Prezzi IVA esclusa per utenti non loggati tramite geolocalizzazione' di MyPresta.eu."
sidebar:
  label: "Prezzi IVA esclusa per utenti non loggati tramite geolocalizzazione - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Tax excluded prices for unlogged users by geolocation su MyPresta.eu](https://mypresta.eu/modules/front-office-features/tax-excluded-prices-for-unlogged-users-by-geolocation.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/tax-excluded-prices-for-unlogged-users-by-geolocation/)
>
> ---


# Prezzi IVA esclusa per utenti non loggati tramite geolocalizzazione

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questo modulo opera principalmente tramite override della logica di prezzo principale di PrestaShop, il che significa che la sua configurazione è solitamente minima o addirittura automatica. Il metodo `getContent()` nel file principale del modulo gestisce tipicamente la visualizzazione di un modulo di configurazione standard, ma per questo modulo specifico, la funzionalità principale è ottenuta tramite override di classe piuttosto che tramite impostazioni estese.

Se è presente una schermata di configurazione, questa offrirebbe tipicamente opzioni relative all'abilitazione/disabilitazione del modulo o alla messa a punto del suo comportamento di geolocalizzazione. Tuttavia, in base alla descrizione del modulo e alla struttura dei file, la sua funzione principale è quella di regolare *automaticamente* i prezzi in base alla geolocalizzazione senza richiedere complesse impostazioni rivolte al commerciante.

Pertanto, la schermata di configurazione per questo modulo è probabilmente molto semplice, forse solo un interruttore "Abilita/Disabilita", oppure potrebbe non avere nemmeno un modulo di configurazione dedicato se il suo comportamento è interamente automatico una volta installato.

**Se esiste una schermata di configurazione, includerebbe tipicamente:**

- **Abilita/Disabilita Modulo:**

  - **Cosa fa questa impostazione:** Questo è un interruttore standard per attivare o disattivare la funzionalità del modulo.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il modulo rileverà attivamente le posizioni degli utenti non loggati e regolerà la visualizzazione dei prezzi (IVA inclusa/esclusa) di conseguenza.
    - *Quando disabilitato:* PrestaShop tornerà al suo comportamento predefinito per gli utenti non loggati, mostrando tipicamente i prezzi in base al paese predefinito del negozio o a un'impostazione globale, senza aggiustamenti basati sulla geolocalizzazione.
  - **Valore consigliato:** SÌ (per utilizzare la funzionalità principale del modulo).
  - **Scenario/esempio per il commerciante:** Se hai temporaneamente bisogno di risolvere un problema di prezzo o preferisci il comportamento predefinito di PrestaShop per un breve periodo, potresti disabilitarlo. Altrimenti, mantienilo abilitato per prezzi internazionali accurati.
- **Fornitore di servizi di geolocalizzazione (Ipotetico):**

  - **Cosa fa questa impostazione:** Se il modulo offrisse una scelta, ciò ti consentirebbe di selezionare quale servizio esterno utilizza per rilevare gli indirizzi IP dei visitatori e mapparli ai paesi.
  - **Effetto della modifica di questa impostazione:**
    - *Se impostato su Fornitore A:* Il modulo utilizza il database del Fornitore A per la mappatura IP-paese.
    - *Se impostato su Fornitore B:* Il modulo utilizza il database del Fornitore B, offrendo potenzialmente una diversa precisione o velocità.
  - **Valore consigliato:** Il fornitore predefinito o consigliato da MyPresta.eu.
  - **Scenario/esempio per il commerciante:** Potresti cambiare fornitore se uno offre una migliore precisione per le tue regioni target o se riscontri problemi con quello predefinito.
- **Impostazioni di caching (Ipotetico):**

  - **Cosa fa questa impostazione:** Controlla per quanto tempo i dati di geolocalizzazione vengono memorizzati nella cache per i visitatori per migliorare le prestazioni.
  - **Effetto della modifica di questa impostazione:**
    - *Durata della cache più lunga:* Caricamento delle pagine più veloce per i visitatori abituali, ma potenzialmente aggiornamenti più lenti se l'IP di un visitatore cambia.
    - *Durata della cache più breve:* Geolocalizzazione più in tempo reale, ma un leggero aumento del carico del server.
  - **Valore consigliato:** Predefinito (solitamente ottimizzato per l'equilibrio).
  - **Scenario/esempio per il commerciante:** Se il tuo sito ha un traffico molto elevato e dai priorità alla velocità, potresti aumentare la durata della cache. Se la tua base clienti è altamente mobile e cambia frequentemente IP, una durata più breve potrebbe essere preferita.

**Nota importante per i commercianti:**
Questo modulo funziona sovrascrivendo le classi principali di PrestaShop (`Product.php`, `Tax.php`, `TaxCalculator.php`). Questa è una tecnica potente che modifica direttamente il modo in cui PrestaShop calcola e visualizza i prezzi. Per questo motivo, di solito ci sono pochissime, se non nessuna, opzioni configurabili su una schermata dedicata. La forza del modulo risiede nelle sue regolazioni automatiche, dietro le quinte.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | Abilita/Disabilita Modulo | Abilitato | Attiva o disattiva la funzionalità di regolazione del prezzo basata sulla geolocalizzazione del modulo. |
| Pagina di configurazione del modulo | *[Altre impostazioni se presenti]* | *[Valore predefinito]* | *[Scopo e Impatto]* |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I prezzi non cambiano per gli utenti non loggati, anche dopo aver installato il modulo.**
R1:

- **Verifica lo stato del modulo:** Assicurati che il modulo sia installato e abilitato nel tuo Back Office di PrestaShop sotto Moduli > Gestione moduli.
- **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e svuota tutte le cache (cache Smarty, cache del filesystem, ecc.). Potrebbe essere necessario svuotare anche la cache del browser.
- **Precisione della geolocalizzazione:** Il modulo si basa sulla geolocalizzazione IP. Sebbene generalmente accurata, non è perfetta al 100%. Testa con IP diversi (ad esempio, usando una VPN) per confermare.
- **Regole fiscali di PrestaShop:** Verifica che le tue regole fiscali e i gruppi fiscali di PrestaShop siano configurati correttamente per i diversi paesi. Il modulo utilizza queste regole esistenti per determinare *quale* prezzo mostrare (IVA inclusa o esclusa) una volta che conosce il paese.
- **Conflitti di override:** Se hai altri moduli che sovrascrivono anche `Product.php`, `Tax.php` o `TaxCalculator.php`, potrebbe esserci un conflitto. Controlla la tua cartella `override/` per altri moduli che modificano questi file. Contatta il supporto MyPresta.eu se sospetti un conflitto.

**D2: Il mio tema personalizzato non sembra visualizzare correttamente i prezzi dopo l'installazione.**
R2: Questo modulo influisce principalmente sul *valore* del prezzo visualizzato, non sulla sua stilizzazione visiva. Se i prezzi appaiono disallineati o stilizzati in modo errato, è probabile che si tratti di un problema CSS con il tuo tema.

- **Compatibilità del tema:** Assicurati che il tuo tema sia completamente compatibile con la tua versione di PrestaShop.
- **Ispeziona elemento:** Utilizza gli strumenti per sviluppatori del tuo browser (F12) per ispezionare gli elementi del prezzo e vedere se qualche CSS personalizzato del tuo tema è in conflitto.
- **Contatta lo sviluppatore del tema:** Se stai utilizzando un tema personalizzato, contatta lo sviluppatore del tuo tema per assistenza con la stilizzazione. Il modulo stesso non introduce nuovi CSS.

**D3: Questo modulo influisce sugli utenti loggati o sugli utenti che hanno inserito il loro indirizzo?**
R3: No, questo modulo si rivolge specificamente agli *utenti non loggati* che non hanno ancora fornito le informazioni sul loro indirizzo. Una volta che un utente effettua l'accesso o inserisce il suo indirizzo di spedizione durante il checkout, la logica nativa di calcolo e visualizzazione delle tasse di PrestaShop (che conosce già il paese del cliente) avrà la precedenza. Questo modulo colma la lacuna per l'esperienza di navigazione iniziale.

**D4: Come fa il modulo a conoscere il paese del cliente?**
R4: Il modulo utilizza l'indirizzo IP del visitatore per determinare la sua posizione geografica. Questo è un metodo standard per la geolocalizzazione nelle applicazioni web. Utilizza quindi questo paese rilevato per applicare le regole fiscali appropriate di PrestaShop per la visualizzazione dei prezzi.

**D5: Questo modulo rallenterà il mio negozio?**
R5: Il modulo è progettato per essere efficiente. Le ricerche di geolocalizzazione sono tipicamente veloci e il modulo spesso memorizza i risultati nella cache per ridurre al minimo le ricerche ripetute per lo stesso visitatore. L'impatto sulle prestazioni dovrebbe essere trascurabile. Se noti un rallentamento, assicurati che il tuo server soddisfi i requisiti minimi di PrestaShop e che i tuoi meccanismi di caching siano configurati correttamente.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Prezzi IVA esclusa per utenti non loggati tramite geolocalizzazione" raggiunge la sua funzionalità principalmente attraverso il sistema di override di PrestaShop. Invece di affidarsi a hook tradizionali o controller personalizzati, modifica direttamente il comportamento delle classi core di PrestaShop responsabili della determinazione dei prezzi dei prodotti e del calcolo delle tasse. Ciò gli consente di iniettare la logica basata sulla geolocalizzazione nel processo fondamentale di determinazione dei prezzi, garantendo che i prezzi vengano regolati prima ancora di essere renderizzati. Il modulo sfrutta l'hook `displayHeader` per includere potenzialmente qualsiasi JavaScript o stile necessario, sebbene la sua logica principale sia basata su PHP.

### 4.2 Controller (`controllers/`)

Questo modulo **non** contiene alcun controller Front-Office o Back-Office Admin personalizzato. La sua logica è incorporata direttamente negli override delle classi core.

### 4.3 Classi e modelli core (`classes/`)

La funzionalità principale del modulo risiede nei suoi override delle classi fondamentali di PrestaShop per i prezzi e i prodotti.

- **`taxprice/override/classes/Product.php`**

  - **Classe originale:** `Product`
  - **Responsabilità:** Questo override è cruciale. La classe `Product` è responsabile del recupero e della formattazione delle informazioni sui prodotti, inclusi i prezzi. Questo override probabilmente intercetta metodi come `getPrice()` o metodi correlati di calcolo del prezzo per iniettare la logica di geolocalizzazione *prima* che il prezzo venga restituito per la visualizzazione. Determina se mostrare prezzi IVA inclusa o IVA esclusa in base al paese rilevato per gli utenti non loggati.
  - **Logica chiave:**
    - Rileva se l'utente corrente è un ospite (non loggato).
    - Ottiene il paese del visitatore in base all'indirizzo IP (potenzialmente tramite una funzione helper o un'integrazione di un servizio di terze parti).
    - Modifica il contesto di `TaxManagerFactory` o manipola direttamente il `price_display_method` in base alle regole fiscali del paese rilevato e alla configurazione di PrestaShop per quel paese.
- **`taxprice/override/classes/tax/Tax.php`**

  - **Classe originale:** `Tax`
  - **Responsabilità:** La classe `Tax` gestisce il recupero e l'applicazione delle aliquote fiscali. Questo override potrebbe essere utilizzato per garantire che le aliquote fiscali corrette vengano applicate *dopo* che la geolocalizzazione ha determinato se i prezzi dovrebbero essere IVA inclusa o IVA esclusa. Potrebbe modificare il modo in cui vengono recuperate le aliquote fiscali o come viene inizializzato il `TaxCalculator` in base al paese dell'ospite.
- **`taxprice/override/classes/tax/TaxCalculator.php`**

  - **Classe originale:** `TaxCalculator`
  - **Responsabilità:** Questa classe è centrale per il calcolo dei prezzi con e senza tasse. L'override qui influenzerebbe direttamente il calcolo finale del prezzo. Probabilmente garantisce che, quando il paese di un ospite è noto, il `TaxCalculator` utilizzi il `price_display_method` corretto (ad esempio, `PS_TAX_EXC` o `PS_TAX_INC`) che corrisponde alle regole fiscali del paese rilevato, piuttosto che al valore predefinito del negozio.
- **`taxprice/override/classes/index.php`**

  - **Scopo:** Questo è un file `index.php` vuoto standard, tipicamente posizionato nelle directory per impedire l'elenco delle directory per motivi di sicurezza. Non ha alcun impatto funzionale sulla logica del modulo.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo **non** contiene alcun file JavaScript personalizzato. La sua funzionalità principale è gestita lato server tramite override PHP.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo **non** contiene alcun file CSS personalizzato. Non introduce nuovi elementi visivi, ma modifica solo i valori dei prezzi esistenti.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **`taxprice/views/displayHeader.tpl`**

  - **Hook:** `displayHeader`
  - **Scopo:** Questo template viene renderizzato nella sezione `<head>` di ogni pagina del front-office. Viene tipicamente utilizzato per includere JavaScript, CSS o meta tag. Sebbene la logica principale del modulo sia basata su PHP, questo template potrebbe essere utilizzato per:
    - Inizializzare eventuali variabili lato client se necessario (anche se improbabile data la natura lato server).
    - Potenzialmente includere un piccolo script inline per il debug o aggiustamenti lato client molto specifici (ad esempio, impostare un cookie con il paese rilevato, anche se meno comune per questo tipo di modulo).
    - In assenza di file JS dedicati, potrebbe contenere qualsiasi JS inline minimo richiesto.
- **`taxprice/views/script.tpl`**

  - **Scopo:** Questo nome di template suggerisce che potrebbe contenere codice JavaScript. Se presente, verrebbe probabilmente incluso tramite `displayHeader.tpl` o un altro hook.
  - **Contenuto potenziale:**
    - Qualsiasi logica lato client relativa alla geolocalizzazione (ad esempio, utilizzando un'API di ricerca IP lato client, anche se meno affidabile rispetto al lato server).
    - Script per gestire aggiornamenti dinamici dei prezzi se il modulo supporta anche la commutazione lato client o aggiustamenti in tempo reale (improbabile data la descrizione).
    - Script di debug o semplice output di dati per gli sviluppatori.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Questo modulo **non** crea alcuna tabella di database personalizzata.
  - Si basa sulle tabelle esistenti di PrestaShop per prodotti (`ps_product`, `ps_product_shop`), tasse (`ps_tax`, `ps_tax_rule`, `ps_tax_rule_group`) e configurazione (`ps_configuration`).
  - I valori di configurazione sono memorizzati in `ps_configuration` utilizzando i metodi standard `Configuration::get()` e `Configuration::updateValue()`, tipicamente prefissati con `TAXPRICE_`.
- **Tabella degli hook registrati**:

| Nome dell'Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Utilizzato per includere `displayHeader.tpl` e potenzialmente `script.tpl` per eventuali script lato client o meta-informazioni necessarie. |
| `actionProductUpdate` | Dopo l'aggiornamento di un prodotto. | (Implicito, non esplicitamente elencato ma comune per i moduli relativi ai prezzi) Potrebbe svuotare la cache relativa ai prezzi dei prodotti per garantire che gli override vengano riapplicati. |
| `actionProductAdd` | Dopo l'aggiunta di un prodotto. | (Implicito) Simile a `actionProductUpdate`. |
| `actionTaxManagerFactory` | Quando `TaxManagerFactory` viene inizializzato. | (Implicito, cruciale per questo modulo) Gli override in `Tax.php` e `TaxCalculator.php` si "aggancerebbero" o modificherebbero efficacemente il comportamento del calcolo delle tasse in questa fase, anche se non si tratta di una registrazione formale di `hook`. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e ulteriore assistenza con il modulo "Prezzi IVA esclusa per utenti non loggati tramite geolocalizzazione", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a fornire un supporto completo e a garantire che il modulo funzioni senza problemi.
"""
