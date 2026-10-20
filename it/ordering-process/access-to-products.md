---
title: "Accesso ai Prodotti - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Accesso ai Prodotti di MyPresta.eu."
sidebar:
  label: "Accesso ai Prodotti - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Access to Products su MyPresta.eu](https://mypresta.eu/modules/ordering-process/access-to-products.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/access-to-products/)
>
> ---


# Accesso ai Prodotti

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste da PrestaShop stesso e sono sufficienti per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Accesso ai Prodotti)

Questa è la schermata di configurazione principale dove definisci le regole per l'accesso ai prodotti.

#### Impostazioni Generali

| Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- |
| **Abilita modulo** | SÌ | **Scopo:** Attiva o disattiva la funzionalità del modulo. **Effetto:** *Quando abilitato:* Tutte le restrizioni configurate saranno attive nel front office. *Quando disabilitato:* Il modulo non avrà alcun effetto e tutti i prodotti saranno visibili e acquistabili da tutti i clienti, indipendentemente dal gruppo. **Consigliato:** SÌ, una volta configurate le tue regole. |
| **Blocca la possibilità di visualizzare la pagina del prodotto** | NO | **Scopo:** Controlla se i clienti non appartenenti ai gruppi consentiti possono persino vedere la pagina dedicata del prodotto. **Effetto:** *Quando abilitato:* Se un cliente non appartenente a un gruppo consentito tenta di accedere direttamente alla pagina del prodotto (ad esempio, tramite un link o un motore di ricerca), verrà reindirizzato o gli verrà mostrato un messaggio di accesso negato. *Quando disabilitato:* I clienti non autorizzati possono comunque visualizzare la pagina del prodotto, ma verrà impedito loro di aggiungerlo al carrello. **Consigliato:** SÌ per prodotti veramente esclusivi, NO se vuoi che vedano il prodotto ma non lo acquistino (ad esempio, "contattaci per l'ingrosso"). |
| **Nascondi prodotto negli elenchi di prodotti** | NO | **Scopo:** Determina se i prodotti con restrizioni sono nascosti dalle pagine di categoria, dai risultati di ricerca e da altri elenchi di prodotti per i clienti non autorizzati. **Effetto:** *Quando abilitato:* I prodotti semplicemente non appariranno in nessun elenco di prodotti per i clienti non appartenenti ai gruppi consentiti. *Quando disabilitato:* I prodotti appariranno negli elenchi, ma quando il cliente ci cliccherà sopra, gli verrà impedito di visualizzare la pagina (se "Blocca la possibilità di visualizzare la pagina del prodotto" è SÌ) o gli verrà impedito di aggiungerlo al carrello. **Consigliato:** SÌ per un'esperienza di navigazione più pulita e mirata per ogni gruppo di clienti. |
| **Messaggio per i clienti non autorizzati** | "Non sei autorizzato a ordinare questo prodotto." | **Scopo:** Il testo visualizzato ai clienti che tentano di aggiungere un prodotto con restrizioni al carrello o di visualizzare una pagina di prodotto con restrizioni (se "Blocca la possibilità di visualizzare la pagina del prodotto" è NO). **Effetto:** Questo messaggio appare nel carrello accanto al prodotto con restrizioni o sulla pagina del prodotto. **Consigliato:** Un messaggio chiaro e cortese. Puoi personalizzarlo per spiegare il motivo (ad esempio, "Questo prodotto è solo per clienti all'ingrosso. Accedi al tuo account all'ingrosso."). |

#### Tabella delle Restrizioni del Prodotto

Questa sezione visualizza un elenco di tutti i prodotti per i quali hai definito restrizioni di accesso. Puoi aggiungere nuove restrizioni o modificare quelle esistenti qui.

- **Nome del prodotto:** Il nome del prodotto soggetto a restrizioni.
- **Gruppi di clienti consentiti:** Un elenco di gruppi di clienti a cui *è* consentito visualizzare e/o acquistare questo prodotto.
- **Azioni:** Modifica (icona a matita) o Elimina (icona cestino) la restrizione.

#### Aggiunta/Modifica delle Restrizioni del Prodotto

Quando fai clic su "Aggiungi nuova restrizione" o sull'icona "Modifica" per una restrizione esistente, vedrai un modulo:

- **Seleziona Prodotto:**

  - **Cosa fa questa impostazione:** Ti consente di cercare e selezionare il prodotto specifico che desideri limitare.
  - **Effetto della modifica di questa impostazione:** Collega la regola di restrizione a un particolare prodotto nel tuo catalogo.
  - **Valore consigliato:** Seleziona il prodotto esatto.
  - **Scenario del commerciante:** Vuoi limitare "Miscela di caffè all'ingrosso" ai tuoi clienti all'ingrosso. Cercheresti e selezioneresti "Miscela di caffè all'ingrosso".
- **Seleziona Gruppi di Clienti:**

  - **Cosa fa questa impostazione:** Un elenco di tutti i gruppi di clienti definiti nel tuo negozio PrestaShop (ad esempio, Visitatore, Ospite, Cliente, Grossista, VIP). Selezioni quali di questi gruppi *sono autorizzati* ad accedere al prodotto.
  - **Effetto della modifica di questa impostazione:** Solo i clienti appartenenti ai gruppi selezionati potranno interagire con il prodotto secondo le tue impostazioni generali (visualizzare, aggiungere al carrello). Tutti gli altri gruppi saranno soggetti a restrizioni.
  - **Valore consigliato:** Seleziona solo i gruppi che dovrebbero avere accesso.
  - **Scenario del commerciante:** Per "Miscela di caffè all'ingrosso", selezioneresti "Grossista". Se volessi che anche i VIP avessero accesso, selezioneresti "Grossista" e "VIP".

Dopo aver effettuato le selezioni, fai clic su **"Salva"** per applicare la restrizione.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
|---|---|---|
| Configurazione modulo | Abilita modulo | SÌ | Attiva/disattiva tutte le funzionalità del modulo. |
| Configurazione modulo | Blocca la possibilità di visualizzare la pagina del prodotto | NO (considera SÌ per l'esclusività) | Impedisce ai clienti non autorizzati di vedere la pagina del prodotto. |
| Configurazione modulo | Nascondi prodotto negli elenchi di prodotti | NO (considera SÌ per la visualizzazione mirata) | Nasconde i prodotti con restrizioni dai risultati di categoria/ricerca per i clienti non autorizzati. |
| Configurazione modulo | Messaggio per i clienti non autorizzati | "Non sei autorizzato a ordinare questo prodotto." | Messaggio personalizzabile mostrato ai clienti non autorizzati. |
| Tabella delle restrizioni del prodotto | Seleziona Prodotto | N/A | Scegli il prodotto a cui applicare le restrizioni. |
| Tabella delle restrizioni del prodotto | Seleziona Gruppi di Clienti | N/A | Definisci quali gruppi di clienti sono *autorizzati* ad accedere al prodotto selezionato. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho configurato le restrizioni, ma non sembrano funzionare. Cosa devo fare?**
R:

1. **Controlla lo stato del modulo:** Assicurati che "Abilita modulo" sia impostato su SÌ nella configurazione del modulo.
2. **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** nel tuo Back Office di PrestaShop. Clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti). Questo è fondamentale affinché le modifiche abbiano effetto.
3. **Assegnazione del gruppo clienti:** Ricontrolla che il cliente con cui stai testando sia correttamente assegnato al gruppo clienti previsto (Clienti > Clienti, quindi modifica il cliente).
4. **Selezione del prodotto:** Verifica di aver selezionato il prodotto corretto nelle impostazioni di restrizione del modulo.
5. **Cache del browser:** Prova a svuotare la cache del tuo browser o a testare in una finestra di navigazione in incognito/privata per escludere problemi di caching lato client.

**D: Come posso tradurre il "Messaggio per i clienti non autorizzati" in altre lingue?**
R:

1. Vai su **Internazionale > Traduzioni** nel tuo Back Office di PrestaShop.
2. Seleziona "Traduzioni moduli installati" come Tipo di traduzione.
3. Scegli il tuo tema.
4. Seleziona la lingua che desideri tradurre.
5. Trova il modulo "Accesso ai Prodotti". Dovresti vedere il campo per il messaggio lì, pronto per la traduzione.

**D: Questo modulo rallenterà il mio negozio?**
R: Il modulo è progettato per essere leggero ed efficiente. Si integra direttamente con la logica principale del prodotto e del carrello di PrestaShop. Qualsiasi impatto sulle prestazioni dovrebbe essere trascurabile, soprattutto dopo la memorizzazione nella cache. Se noti rallentamenti significativi, assicurati che il tuo server soddisfi i requisiti minimi di PrestaShop e che tu stia utilizzando una versione PHP recente.

**D: Cosa succede se un cliente appartiene a più gruppi, e un gruppo è consentito mentre un altro no?**
R: Se un cliente appartiene a *qualsiasi* gruppo a cui è esplicitamente consentito l'accesso a un prodotto, avrà accesso. Il modulo concede l'accesso se *qualsiasi* dei gruppi del cliente corrisponde a un gruppo consentito per quel prodotto. È una logica "OR": se il Gruppo A è consentito OPPURE il Gruppo B è consentito, e il cliente è nel Gruppo A, ottiene l'accesso.

**D: Posso limitare l'accesso a intere categorie invece che a singoli prodotti?**
R: Questo modulo si concentra sulle restrizioni dei singoli prodotti. Per limitare intere categorie, dovresti applicare la restrizione a ciascun prodotto all'interno di quella categoria. Per le restrizioni a livello di categoria, potresti aver bisogno di un modulo diverso o di uno sviluppo personalizzato.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo "Accesso ai Prodotti" (`pga`) opera principalmente sovrascrivendo le classi principali di PrestaShop per iniettare la sua logica di controllo degli accessi. Sfrutta l'`ObjectModel` di PrestaShop per l'archiviazione della configurazione e modifica la visibilità del prodotto e il comportamento del carrello in punti chiave del ciclo di vita della richiesta del front-office. La logica principale del modulo risiede in `index.php` (il file principale del modulo) e nelle sue sovrascritture.

### 4.2 Controller (`controllers/`)

Questo modulo non introduce alcun controller front-office o back-office personalizzato. Tutta la configurazione è gestita tramite il metodo `getContent()` nel file principale del modulo (`pga/index.php`).

### 4.3 Classi e Modelli Core (`classes/`)

Il modulo utilizza il meccanismo di override di PrestaShop per modificare il comportamento del core.

- `pga/override/classes/Pack.php`

  - **Nome della classe:** `Pack` (sovrascrive la classe `Pack` di PrestaShop)
  - **Responsabilità:** Questa sovrascrittura probabilmente modifica il modo in cui vengono gestiti i pacchetti di prodotti, in particolare in relazione alla visibilità e all'accesso ai prodotti. Garantisce che se un prodotto all'interno di un pacchetto è soggetto a restrizioni, il pacchetto stesso rispetti tali restrizioni. Questo è fondamentale per mantenere un controllo degli accessi coerente per i prodotti in bundle.
  - **Metodi chiave (probabilmente modificati/aggiunti):** I metodi relativi a `getPackProducts()` o `isPack()` potrebbero essere estesi per filtrare i prodotti in base alle restrizioni `pga`.
- `pga/override/classes/shop/Shop.php`

  - **Nome della classe:** `Shop` (sovrascrive la classe `Shop` di PrestaShop)
  - **Responsabilità:** Questa sovrascrittura è meno comune per i moduli di accesso ai prodotti e suggerisce un'integrazione più profonda. Potrebbe essere utilizzata per garantire che le restrizioni sui prodotti siano correttamente applicate tra i diversi negozi in un ambiente multi-negozio, o per modificare il modo in cui i dati del prodotto vengono recuperati a un livello molto fondamentale, influenzando potenzialmente le query sui prodotti.
  - **Metodi chiave (probabilmente modificati/aggiunti):** Metodi come `getProducts()` o `getProductById()` potrebbero essere estesi per filtrare i risultati in base alle regole `pga` prima che vengano restituiti dal contesto `Shop`.

### 4.4 Risorse JavaScript (`views/js/`)

- `pga/views/js/pga.js`
  - **Ambito:** Back-office.
  - **Scopo:** Questo script è probabilmente responsabile del miglioramento dell'esperienza utente nella pagina di configurazione del modulo. Potrebbe gestire chiamate AJAX per la ricerca di prodotti, aggiornamenti dinamici alla tabella delle restrizioni dei prodotti o la convalida lato client per il modulo di configurazione.
  - **Funzionalità chiave:**
    - Listener di eventi per i campi di input di ricerca prodotti (ad esempio, eventi `keyup` per attivare suggerimenti AJAX).
    - Richieste AJAX a un endpoint del modulo (tramite `AdminController` o `index.php?fc=module&module=pga&controller=ajax`) per recuperare dati di prodotto o salvare restrizioni.
    - Manipolazione del DOM per visualizzare i risultati della ricerca, aggiungere prodotti selezionati all'elenco delle restrizioni o aggiornare i messaggi.

### 4.5 Fogli di stile CSS (`views/css/`)

- `pga/views/css/pga.css`
  - **Ambito:** Back-office.
  - **Scopo:** Fornisce lo stile per l'interfaccia di configurazione del modulo nel Back Office di PrestaShop.
  - **Componenti principali dell'interfaccia utente:** Stili per l'input di ricerca prodotti, la tabella delle restrizioni prodotti, i pulsanti e qualsiasi elemento personalizzato introdotto dal metodo `getContent()` del modulo.
  - **Selettori di classi CSS chiave:** Gli sviluppatori possono ispezionare l'output HTML del modulo nel Back Office per identificare classi specifiche (ad esempio, `.pga-product-search`, `.pga-restriction-table`) per potenziali override se è richiesta una personalizzazione del tema amministrativo.

### 4.6 Struttura del template Smarty (`views/templates/`)

Tutti i template sono per la configurazione del Back Office.

- `pga/views/templates/admin/AdminTab.tpl`

  - **Scopo:** Questo template è probabilmente un wrapper generico o un template parziale utilizzato all'interno della vista di configurazione principale. Potrebbe definire la struttura per un'interfaccia a schede o un'intestazione/piè di pagina comune per le pagine di amministrazione.
- `pga/views/templates/admin/csv.tpl`

  - **Scopo:** Suggerisce funzionalità relative all'importazione/esportazione CSV delle restrizioni sui prodotti. Questo template renderizzerebbe l'interfaccia per caricare un file CSV o generarne uno.
- `pga/views/templates/admin/csv_file.tpl`

  - **Scopo:** Un sotto-template o parziale utilizzato da `csv.tpl`, possibilmente per visualizzare un modulo di caricamento file o un elenco di file CSV.
- `pga/views/templates/admin/customerGroups.tpl`

  - **Scopo:** Questo template è cruciale per la funzionalità "Seleziona Gruppi di Clienti". Renderizza l'elenco dei gruppi di clienti con caselle di controllo o un menu a discesa a selezione multipla, consentendo all'amministratore di scegliere quali gruppi sono consentiti per un prodotto specifico.
- `pga/views/templates/admin/main.tpl`

  - **Scopo:** Questo è il template principale per la pagina di configurazione del modulo (renderizzato da `getContent()`). Orchesta tutti gli altri parziali e visualizza le impostazioni generali, la tabella delle restrizioni dei prodotti e i moduli di aggiunta/modifica delle restrizioni.

### 4.7 Schema del database e Mappa degli hook

- **Tabelle del database**:

  - Il modulo memorizza la sua configurazione nella tabella `ps_configuration` di PrestaShop per le impostazioni generali (ad esempio, `PGA_ENABLED`, `PGA_BLOCK_VIEW`, `PGA_HIDE_LISTS`, `PGA_MESSAGE`).
  - Per le restrizioni specifiche del prodotto, il modulo probabilmente crea una tabella di database personalizzata (ad esempio, `ps_pga_product_group`) per memorizzare la mappatura tra `id_product` e `id_group`. Il metodo `install()` in `pga/index.php` definirebbe questa tabella.
- **Tabella degli hook registrati**:

| Nome dell'Hook | Tempistica di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Potenzialmente utilizzato per caricare CSS/JS specifici del modulo per la visualizzazione del front-office (ad esempio, se un messaggio personalizzato necessita di stile) o per eseguire controlli preliminari per il reindirizzamento della pagina del prodotto. |
| `displayRightColumn` / `displayLeftColumn` | Nella barra laterale destra/sinistra delle pagine del front-office. | Meno probabile per questo modulo, ma potrebbe essere utilizzato per visualizzare un blocco personalizzato (ad esempio, "Accedi per accesso esclusivo") se configurato. |
| `displayProductButtons` / `displayProductActions` (o hook simili della pagina del prodotto) | Sulla pagina del prodotto, vicino al pulsante Aggiungi al carrello. | Utilizzato per nascondere o disabilitare il pulsante "Aggiungi al carrello" per gli utenti non autorizzati, o per visualizzare il messaggio di restrizione personalizzato. |
| `displayFooter` | Nel piè di pagina di ogni pagina del front-office. | Meno comune per la funzionalità principale, ma potrebbe essere utilizzato per script a caricamento tardivo o analisi relative all'accesso ai prodotti. |
| `actionCartSave` / `actionObjectCartAddAfter` (o hook simili del carrello) | Quando un prodotto viene aggiunto o salvato nel carrello. | **CRITICO:** Qui il modulo intercetta il processo del carrello per verificare se il prodotto aggiunto è soggetto a restrizioni per il gruppo del cliente corrente. Se soggetto a restrizioni, impedisce l'aggiunta o contrassegna l'articolo come non valido, visualizzando il messaggio personalizzato. |
| `actionProductListOverride` (o hook simili di elenco prodotti) | Quando PrestaShop genera un elenco di prodotti (ad esempio, pagina di categoria, risultati di ricerca). | **CRITICO:** Utilizzato per filtrare i prodotti con restrizioni dagli elenchi di prodotti se "Nascondi prodotto negli elenchi di prodotti" è abilitato. |
| `actionDispatcherBefore` / `actionFrontControllerSetMedia` | Prima che un front controller venga inviato o prima che vengano impostate le risorse multimediali. | Potrebbe essere utilizzato per implementare la logica di reindirizzamento per "Blocca la possibilità di visualizzare la pagina del prodotto" controllando l'ID del prodotto richiesto rispetto alle restrizioni. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Accesso ai Prodotti", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere.
