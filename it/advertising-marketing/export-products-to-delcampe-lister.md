---
title: "Esporta prodotti su Delcampe Lister - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Esporta prodotti su Delcampe Lister' di MyPresta.eu."
sidebar:
  label: "Esporta prodotti su Delcampe Lister - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Export products to Delcampe Lister su MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/export-products-to-delcampe-lister.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/advertising-marketing/export-products-to-delcampe-lister/)
>
> ---


# Esporta prodotti su Delcampe Lister

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono generalmente richieste per il corretto funzionamento di PrestaShop e dovrebbero essere disponibili sulla maggior parte degli ambienti di hosting.

## 2. Panoramica completa della configurazione (ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Puoi accedere a questa schermata navigando su **Moduli > Gestione moduli** e cliccando su "Configura" accanto a "Esporta prodotti su Delcampe Lister".

Questa schermata gestisce principalmente le impostazioni generali del modulo, inclusi i controlli degli aggiornamenti.

-   **MyPresta.eu Controllo aggiornamenti in tempo reale:**
    -   **Cosa fa questa impostazione:** Questa opzione controlla se il modulo verifica automaticamente la disponibilità di nuove versioni e aggiornamenti da MyPresta.eu.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Il modulo si connetterà periodicamente a MyPresta.eu per verificare se è disponibile una versione più recente. Questo ti aiuta a rimanere aggiornato con correzioni di bug e nuove funzionalità.
        -   *Quando disabilitato:* Il modulo non controllerà automaticamente gli aggiornamenti. Dovrai verificare manualmente gli aggiornamenti nel tuo account MyPresta.eu.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio per il commerciante:** Mantenere questa opzione abilitata ti assicura di utilizzare sempre la versione più stabile e ricca di funzionalità del modulo senza dover ricordare di controllare manualmente.

### 2.2 Schermate di amministrazione dedicate e viste del controller

#### 2.2.1 Gestione prodotti Delcampe (Back Office > Catalogo > Prodotti Delcampe)

Questa è la schermata di gestione principale per le esportazioni dei tuoi prodotti Delcampe. Puoi accedervi navigando su **Catalogo > Prodotti Delcampe** nel menu del Back Office di PrestaShop.

Questa schermata fornisce una visualizzazione a griglia dei tuoi prodotti e ti consente di gestire le loro impostazioni di esportazione per Delcampe. Puoi aggiungere nuovi prodotti all'elenco di esportazione, modificare quelli esistenti e generare il file di esportazione.

**Azioni e impostazioni disponibili:**

-   **Tabella Elenco Prodotti:** Questa tabella mostra tutti i prodotti che sono già configurati per l'esportazione su Delcampe o disponibili per essere configurati. Vedrai colonne come l'ID del prodotto, il nome e potenzialmente le loro impostazioni specifiche per Delcampe.
-   **Aggiungi Nuovo Prodotto / Modifica Prodotto:**
    -   Cliccando su "Aggiungi Nuovo" o modificando un prodotto esistente si aprirà un modulo in cui è possibile definire parametri specifici di inserzione Delcampe per quel prodotto.
    -   **`category_id` (ID Categoria Delcampe):**
        -   **Cosa fa questa impostazione:** Questo è l'ID di categoria specifico su Delcampe dove il tuo prodotto verrà elencato. Delcampe ha una propria struttura di categorie, che potrebbe differire da quella di PrestaShop.
        -   **Effetto della modifica di questa impostazione:** ID di categoria errati comporteranno l'inserimento del tuo prodotto nella sezione sbagliata su Delcampe, o potenzialmente il fallimento dell'inserimento.
        -   **Valore consigliato:** L'ID numerico esatto della categoria Delcampe di destinazione.
        -   **Scenario / esempio per il commerciante:** Se stai vendendo un francobollo raro, dovresti trovare l'ID della categoria "Francobolli" appropriata su Delcampe e inserirlo qui.
    -   **`title` (Titolo Inserzione Delcampe):**
        -   **Cosa fa questa impostazione:** Il titolo che apparirà per il tuo prodotto su Delcampe. Questo può essere diverso dal nome del tuo prodotto PrestaShop.
        -   **Effetto della modifica di questa impostazione:** Un titolo accattivante e ricco di parole chiave può migliorare significativamente la visibilità su Delcampe.
        -   **Valore consigliato:** Un titolo descrittivo, conciso e ottimizzato per le ricerche su Delcampe.
        -   **Scenario / esempio per il commerciante:** Invece di "Vecchio Francobollo", potresti usare "Raro Francobollo Francese 1920 - Inutilizzato - Condizioni Eccellenti".
    -   **`description` (Descrizione Inserzione Delcampe):**
        -   **Cosa fa questa impostazione:** La descrizione dettagliata del prodotto che verrà visualizzata nella tua inserzione Delcampe.
        -   **Effetto della modifica di questa impostazione:** Una descrizione approfondita con tutti i dettagli rilevanti aiuta gli acquirenti a prendere decisioni informate e a costruire fiducia.
        -   **Valore consigliato:** Una descrizione completa, che potenzialmente includa contesto storico, condizioni e dimensioni.
        -   **Scenario / esempio per il commerciante:** Copia la tua descrizione PrestaShop, ma considera di aggiungere dettagli o formattazioni specifiche per Delcampe.
    -   **`personal_reference` (Il tuo riferimento interno):**
        -   **Cosa fa questa impostazione:** Un campo opzionale per il tuo numero di tracciamento o riferimento interno per il prodotto su Delcampe.
        -   **Effetto della modifica di questa impostazione:** Ti aiuta a collegare le vendite Delcampe al tuo sistema di inventario interno.
        -   **Valore consigliato:** Il tuo riferimento prodotto o SKU di PrestaShop.
        -   **Scenario / esempio per il commerciante:** L'utilizzo del tuo SKU di PrestaShop qui ti consente di identificare rapidamente il prodotto nel tuo negozio quando arriva un ordine Delcampe.
    -   **`currency` (Valuta dell'inserzione):**
        -   **Cosa fa questa impostazione:** La valuta in cui il prodotto verrà elencato su Delcampe.
        -   **Effetto della modifica di questa impostazione:** Deve corrispondere a una valuta supportata da Delcampe.
        -   **Valore consigliato:** La tua valuta di vendita principale (es. EUR, USD).
        -   **Scenario / esempio per il commerciante:** Se vendi principalmente in Euro, imposta questo su EUR.
    -   **`selling_type` (Tipo di vendita Delcampe):**
        -   **Cosa fa questa impostazione:** Definisce come il prodotto viene venduto su Delcampe (es. asta, prezzo fisso).
        -   **Effetto della modifica di questa impostazione:** Determina il processo di acquisto per i clienti su Delcampe.
        -   **Valore consigliato:** Scegli il tipo che meglio si adatta al tuo prodotto e alla tua strategia di vendita (es. "Prezzo Fisso" per articoli standard, "Asta" per articoli rari).
        -   **Scenario / esempio per il commerciante:** Per un oggetto da collezione comune, "Prezzo Fisso" potrebbe essere adatto. Per un oggetto veramente unico, un'"Asta" potrebbe generare offerte più alte.
    -   **`price` (Prezzo di partenza / Prezzo fisso):**
        -   **Cosa fa questa impostazione:** Il prezzo iniziale per un'asta o il prezzo fisso per una vendita diretta.
        -   **Effetto della modifica di questa impostazione:** Incide direttamente sul costo per l'acquirente.
        -   **Valore consigliato:** Il prezzo di vendita desiderato.
        -   **Scenario / esempio per il commerciante:** Per un articolo a prezzo fisso, questo sarebbe il tuo prezzo al dettaglio. Per un'asta, è l'offerta minima.
    -   **`initial_quantity` (Quantità disponibile):**
        -   **Cosa fa questa impostazione:** Il numero di unità di questo prodotto che stai rendendo disponibili su Delcampe.
        -   **Effetto della modifica di questa impostazione:** Determina quanti articoli un acquirente può acquistare.
        -   **Valore consigliato:** Il tuo attuale livello di scorte per il prodotto.
        -   **Scenario / esempio per il commerciante:** Se hai 5 di un particolare francobollo, imposta questo su 5.
    -   **`minimum_bid_step` (Incremento minimo dell'offerta per l'asta):**
        -   **Cosa fa questa impostazione:** Per le inserzioni in stile asta, questo definisce l'importo minimo di cui un'offerta deve aumentare.
        -   **Effetto della modifica di questa impostazione:** Influisce sul comportamento delle offerte.
        -   **Valore consigliato:** Un incremento ragionevole (es. 0.50, 1.00).
        -   **Scenario / esempio per il commerciante:** Se impostato su 1.00, un'offerta di 10.00 richiederebbe che l'offerta successiva sia almeno 11.00.
    -   **`renew_duration` (Durata rinnovo automatico):**
        -   **Cosa fa questa impostazione:** Se abilitato, specifica per quanto tempo un'inserzione invenduta verrà automaticamente rinnovata.
        -   **Effetto della modifica di questa impostazione:** Mantiene il tuo prodotto elencato su Delcampe senza intervento manuale.
        -   **Valore consigliato:** Una durata che si allinea con il tuo ciclo di vendita (es. 7 giorni, 14 giorni).
        -   **Scenario / esempio per il commerciante:** Se un articolo non viene venduto in 7 giorni, verrà automaticamente ripubblicato per altri 7 giorni.
    -   **`renew_total_count` (Limite rinnovo automatico):**
        -   **Cosa fa questa impostazione:** Il numero massimo di volte in cui un'inserzione invenduta verrà automaticamente rinnovata.
        -   **Effetto della modifica di questa impostazione:** Impedisce il rinnovo indefinito di articoli impopolari.
        -   **Valore consigliato:** Un limite ragionevole (es. 3, 5).
        -   **Scenario / esempio per il commerciante:** Se un articolo non riesce a vendere dopo 3 rinnovi, verrà rimosso da Delcampe.
    -   **`shipping_model` (Modello di spedizione Delcampe):**
        -   **Cosa fa questa impostazione:** Il metodo o modello di spedizione che utilizzi su Delcampe. Questo deve corrispondere alle tue impostazioni di spedizione preconfigurate su Delcampe.
        -   **Effetto della modifica di questa impostazione:** Determina come vengono calcolati e presentati i costi di spedizione all'acquirente.
        -   **Valore consigliato:** L'ID o il nome del tuo modello di spedizione Delcampe preferito.
        -   **Scenario / esempio per il commerciante:** Se hai un modello di "Spedizione Internazionale Standard" impostato su Delcampe, dovresti inserire il suo identificatore qui.
    -   **`weight` (Peso del prodotto):**
        -   **Cosa fa questa impostazione:** Il peso del prodotto, utilizzato per i calcoli di spedizione su Delcampe.
        -   **Effetto della modifica di questa impostazione:** Cruciale per una stima accurata dei costi di spedizione.
        -   **Valore consigliato:** Il peso effettivo del prodotto.
        -   **Scenario / esempio per il commerciante:** Inserisci "0.1" per un francobollo leggero.
    -   **`lister_sale_end_time` (Ora di fine vendita):**
        -   **Cosa fa questa impostazione:** L'ora specifica del giorno in cui l'inserzione terminerà.
        -   **Effetto della modifica di questa impostazione:** Ti consente di programmare la fine delle tue inserzioni.
        -   **Valore consigliato:** Un'ora in cui il tuo pubblico di riferimento è più propenso a essere online (es. 20:00).
        -   **Scenario / esempio per il commerciante:** Terminare un'asta alle 20:00 di domenica potrebbe attirare più offerte dell'ultimo minuto.
    -   **`lister_sale_end_day` (Giorno di fine vendita):**
        -   **Cosa fa questa impostazione:** Il giorno specifico della settimana in cui l'inserzione terminerà.
        -   **Effetto della modifica di questa impostazione:** Ti consente di programmare la fine delle tue inserzioni.
        -   **Valore consigliato:** Un giorno in cui il tuo pubblico di riferimento è più propenso a essere online (es. Domenica).
        -   **Scenario / esempio per il commerciante:** Terminare un'asta di domenica potrebbe attirare più offerte dell'ultimo minuto.
    -   **`option_last_minute_extension` (Estensione ultimo minuto):**
        -   **Cosa fa questa impostazione:** Se abilitato, estende la durata dell'asta se viene fatta un'offerta negli ultimi minuti.
        -   **Effetto della modifica di questa impostazione:** Previene lo "sniping" e incoraggia offerte più alte.
        -   **Valore consigliato:** SÌ (per le aste).
        -   **Scenario / esempio per il commerciante:** Un'offerta fatta 30 secondi prima della fine di un'asta estenderà l'asta di qualche minuto, dando agli altri la possibilità di controbattere.
    -   **`option_anonymous_buyer` (Acquirente anonimo):**
        -   **Cosa fa questa impostazione:** Nasconde l'identità dell'acquirente agli altri offerenti in un'asta.
        -   **Effetto della modifica di questa impostazione:** Può aumentare la privacy per gli offerenti.
        -   **Valore consigliato:** NO (a meno che non siano fondamentali specifiche preoccupazioni sulla privacy).
        -   **Scenario / esempio per il commerciante:** Se vuoi proteggere la privacy dell'acquirente, abilita questa opzione.
    -   **`option_strong_title` (Titolo forte / Titolo in grassetto):**
        -   **Cosa fa questa impostazione:** Rende il titolo della tua inserzione in grassetto su Delcampe, aumentandone la visibilità.
        -   **Effetto della modifica di questa impostazione:** La tua inserzione risalta di più nei risultati di ricerca.
        -   **Valore consigliato:** SÌ.
        -   **Scenario / esempio per il commerciante:** L'utilizzo di un titolo in grassetto aiuta la tua inserzione di francobolli rari a catturare l'attenzione dei collezionisti che sfogliano molti articoli simili.
    -   **`option_background_color` (Colore di sfondo):**
        -   **Cosa fa questa impostazione:** Imposta un colore di sfondo personalizzato per la tua inserzione su Delcampe.
        -   **Effetto della modifica di questa impostazione:** Può rendere la tua inserzione più accattivante visivamente o abbinarla al tuo marchio.
        -   **Valore consigliato:** Lascia vuoto o usa un colore tenue.
        -   **Scenario / esempio per il commerciante:** L'utilizzo di uno sfondo azzurro chiaro potrebbe far risaltare la tua inserzione senza essere distraente.
    -   **`option_border_color` (Colore del bordo):**
        -   **Cosa fa questa impostazione:** Imposta un colore del bordo personalizzato per la tua inserzione su Delcampe.
        -   **Effetto della modifica di questa impostazione:** Può rendere la tua inserzione più accattivante visivamente o abbinarla al tuo marchio.
        -   **Valore consigliato:** Lascia vuoto o usa un colore tenue.
        -   **Scenario / esempio per il commerciante:** Un bordo sottile e scuro può dare alla tua inserzione un aspetto più professionale.

**Flusso di lavoro consigliato per la gestione quotidiana del negozio:**

1.  **Identifica i prodotti per Delcampe:** Decidi quali dei tuoi prodotti PrestaShop sono adatti al marketplace Delcampe.
2.  **Aggiungi/Modifica prodotti:** Vai su **Catalogo > Prodotti Delcampe**. Utilizza il pulsante "Aggiungi nuovo" o modifica le voci esistenti per configurare le impostazioni specifiche di Delcampe per ogni prodotto. Presta particolare attenzione agli ID di categoria Delcampe, ai prezzi e al tipo di vendita.
3.  **Genera esportazione:** Una volta configurati i tuoi prodotti, il modulo ti consentirà di generare il file di esportazione. Questo file conterrà tutti i dati necessari in un formato che Delcampe Lister può importare.
4.  **Importa su Delcampe Lister:** Scarica il file generato e importalo nel tuo strumento Delcampe Lister.
5.  **Monitora e aggiorna:** Tieni d'occhio le tue inserzioni Delcampe e aggiorna le configurazioni dei prodotti in PrestaShop secondo necessità (ad es. per modifiche di prezzo, aggiornamenti di magazzino).

#### 2.2.2 AdminDelcampeProductsController (delcampeproducts/controllers/admin/AdminDelcampeProducts.php)

Questo controller è responsabile della gestione delle inserzioni di prodotti Delcampe all'interno del back office di PrestaShop. Gestisce la visualizzazione dell'elenco dei prodotti, nonché la creazione, la modifica e l'eliminazione delle singole configurazioni dei prodotti Delcampe.

#### 2.2.3 index.php (delcampeproducts/controllers/admin/index.php)

Questo file probabilmente funge da segnaposto o da semplice reindirizzamento all'interno della struttura del controller amministrativo, garantendo che la sezione amministrativa del modulo sia correttamente inizializzata o instradata. Tipicamente non contiene opzioni di configurazione dirette per il commerciante.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | MyPresta.eu Controllo aggiornamenti in tempo reale | SÌ | Controlla i controlli automatici per gli aggiornamenti del modulo. |
| Gestione prodotti Delcampe | ID Categoria Delcampe (`category_id`) | (ID Delcampe specifico) | Mappa il prodotto PrestaShop a una categoria Delcampe. |
| Gestione prodotti Delcampe | Titolo Inserzione Delcampe (`title`) | (Personalizzato) | Titolo del prodotto visualizzato su Delcampe. |
| Gestione prodotti Delcampe | Descrizione Inserzione Delcampe (`description`) | (Personalizzato) | Descrizione dettagliata del prodotto per Delcampe. |
| Gestione prodotti Delcampe | Il tuo riferimento interno (`personal_reference`) | (SKU PrestaShop) | Tracciamento interno per i tuoi prodotti. |
| Gestione prodotti Delcampe | Valuta dell'inserzione (`currency`) | (La tua valuta principale) | Valuta per l'inserzione Delcampe. |
| Gestione prodotti Delcampe | Tipo di vendita Delcampe (`selling_type`) | (Prezzo Fisso / Asta) | Come il prodotto viene venduto su Delcampe. |
| Gestione prodotti Delcampe | Prezzo di partenza / Prezzo fisso (`price`) | (Il tuo prezzo desiderato) | Prezzo per la vendita diretta o l'inizio dell'asta. |
| Gestione prodotti Delcampe | Quantità disponibile (`initial_quantity`) | (Il tuo livello di scorte) | Numero di unità disponibili su Delcampe. |
| Gestione prodotti Delcampe | Incremento minimo dell'offerta per l'asta (`minimum_bid_step`) | (es. 0.50, 1.00) | Importo minimo di cui le offerte devono aumentare. |
| Gestione prodotti Delcampe | Durata rinnovo automatico (`renew_duration`) | (es. 7 giorni) | Per quanto tempo un'inserzione invenduta si rinnova. |
| Gestione prodotti Delcampe | Limite rinnovo automatico (`renew_total_count`) | (es. 3, 5) | Numero massimo di volte in cui un'inserzione invenduta si rinnoverà automaticamente. |
| Gestione prodotti Delcampe | Modello di spedizione Delcampe (`shipping_model`) | (ID/Nome Modello Delcampe) | Metodo di spedizione utilizzato su Delcampe. |
| Gestione prodotti Delcampe | Peso del prodotto (`weight`) | (Peso effettivo del prodotto) | Peso del prodotto per i calcoli di spedizione. |
| Gestione prodotti Delcampe | Ora di fine vendita (`lister_sale_end_time`) | (es. 20:00) | Ora specifica del giorno per la fine dell'inserzione. |
| Gestione prodotti Delcampe | Giorno di fine vendita (`lister_sale_end_day`) | (es. Domenica) | Giorno specifico della settimana per la fine dell'inserzione. |
| Gestione prodotti Delcampe | Estensione ultimo minuto (`option_last_minute_extension`) | SÌ (per le aste) | Estende l'asta se l'offerta viene fatta negli ultimi minuti. |
| Gestione prodotti Delcampe | Acquirente anonimo (`option_anonymous_buyer`) | NO | Nasconde l'identità dell'acquirente nelle aste. |
| Gestione prodotti Delcampe | Titolo forte / Titolo in grassetto (`option_strong_title`) | SÌ | Rende il titolo dell'inserzione in grassetto su Delcampe. |
| Gestione prodotti Delcampe | Colore di sfondo (`option_background_color`) | (Lascia vuoto o tenue) | Colore di sfondo personalizzato per l'inserzione. |
| Gestione prodotti Delcampe | Colore del bordo (`option_border_color`) | (Lascia vuoto o tenue) | Colore del bordo personalizzato per l'inserzione. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei prodotti non vengono visualizzati su Delcampe dopo l'esportazione. Cosa dovrei controllare?**
R:

1.  **Hai completato l'importazione su Delcampe Lister?** Questo modulo *esporta* solo i dati. Devi comunque scaricare il file generato e *importarlo* nel tuo strumento Delcampe Lister.
2.  **Controlla gli ID delle categorie Delcampe:** Assicurati che il `category_id` che hai inserito per ogni prodotto sia corretto ed esista su Delcampe. ID errati possono causare errori di importazione.
3.  **Rivedi gli errori di Delcampe Lister:** Quando importi il file in Delcampe Lister, di solito fornisce feedback o messaggi di errore se qualcosa è andato storto. Controlla questi messaggi per indizi.
4.  **Stato del prodotto:** Assicurati che i prodotti siano attivi e in magazzino nel tuo negozio PrestaShop se hai configurato il modulo per esportare solo articoli attivi/in magazzino.

**D: Come gestisco gli aggiornamenti dei prodotti (modifiche di prezzo, modifiche di magazzino) su Delcampe?**
R: Dovrai riesportare e reimportare i dati del prodotto aggiornati in Delcampe Lister. Il modulo genera un nuovo file di esportazione basato sui dati attuali del tuo prodotto PrestaShop e sulle impostazioni specifiche di Delcampe che hai configurato. Delcampe Lister gestisce tipicamente gli aggiornamenti delle inserzioni esistenti quando importi un file con identificatori di prodotto corrispondenti.

**D: Il file di esportazione sembra vuoto o incompleto.**
R:

1.  **Configurazione del prodotto:** Ricontrolla di aver effettivamente configurato i prodotti per l'esportazione su Delcampe in **Catalogo > Prodotti Delcampe**. Se nessun prodotto è configurato, l'esportazione sarà vuota.
2.  **Impostazioni del modulo:** Rivedi eventuali impostazioni generali del modulo (se presenti) che potrebbero filtrare i prodotti, come "esporta solo prodotti attivi" o "esporta solo prodotti in magazzino".
3.  **Cache di PrestaShop:** A volte, la pulizia della cache di PrestaShop (**Parametri Avanzati > Prestazioni > Svuota cache**) può risolvere comportamenti inaspettati con la generazione dei dati.

**D: Il mio tema personalizzato sta causando problemi di visualizzazione nella configurazione del back-office del modulo.**
R: L'interfaccia del back-office di questo modulo utilizza componenti standard di PrestaShop, quindi dovrebbe essere generalmente compatibile. Se riscontri problemi di stile, è probabile che si tratti di un conflitto con le sovrascritture del back-office del tuo tema personalizzato.

1.  **Verifica le sovrascritture:** Se il tuo tema ha una cartella `admin` con sovrascritture di template, rinominala temporaneamente per vedere se il problema si risolve.
2.  **Contatta lo sviluppatore del tema:** Se il problema persiste, contatta lo sviluppatore del tuo tema per assistenza, poiché potrebbe essere necessario che adatti il suo CSS per adattarsi alle interfacce standard dei moduli.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Esporta prodotti su Delcampe Lister" segue un'architettura standard per i moduli PrestaShop, sfruttando principalmente i Controller Admin per la sua interfaccia di back-office e la gestione dei dati. Non si basa pesantemente sui componenti del front-office per l'interazione diretta con il cliente, ma utilizza gli hook per integrarsi nel ciclo di vita di PrestaShop. La funzionalità principale ruota attorno alla gestione delle impostazioni di esportazione Delcampe specifiche del prodotto e alla generazione di un feed di dati per lo strumento Delcampe Lister.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `controllers/front/feed.php`
        -   **Nome classe e classe padre**: `DelcampeproductsFeedModuleFrontController` che estende `ModuleFrontController`.
        -   **Responsabilità**: Questo controller è probabilmente responsabile della generazione del feed di prodotti Delcampe effettivo (ad esempio, XML, CSV) che il commerciante scaricherebbe. Interrogherebbe i prodotti configurati e formatterebbe i loro dati secondo le specifiche di Delcampe. Risponde a una specifica rotta del front-office, sebbene non sia direttamente visibile all'utente finale che naviga nel negozio.
    -   `controllers/front/index.php`
        -   **Nome classe e classe padre**: `DelcampeproductsIndexModuleFrontController` che estende `ModuleFrontController`.
        -   **Responsabilità**: Questo potrebbe fungere da controller frontale predefinito o di fallback, oppure potrebbe essere utilizzato per un semplice reindirizzamento. In molti moduli, se `feed.php` gestisce l'interazione principale del front-office (generando il feed), `index.php` potrebbe essere minimo o inutilizzato.
-   **Controller Admin Back-Office**:

    -   `controllers/admin/AdminDelcampeProducts.php`
        -   **Nome classe e classe padre**: `AdminDelcampeProductsController` che estende `ModuleAdminController`.
        -   **Nome scheda ed entità gestita**: Questo controller gestisce la sezione "Prodotti Delcampe" sotto il menu "Catalogo" nel Back Office di PrestaShop. È responsabile dell'elenco, dell'aggiunta, della modifica e dell'eliminazione della configurazione specifica di Delcampe per ogni prodotto. Utilizza `HelperList` e `HelperForm` di PrestaShop per visualizzare la griglia dei prodotti e il modulo di configurazione dettagliato.
    -   `controllers/admin/index.php`
        -   **Nome classe e classe padre**: Non una classe controller completa, tipicamente un semplice file `index.php` per impedire l'elenco delle directory o per includere il file del modulo principale per il contesto. Non definisce una distinta classe Admin Controller.

### 4.3 Classi e modelli principali (`classes/`)

Il dossier del modulo non indica classi personalizzate nella directory `classes/`. Ciò suggerisce che il modulo potrebbe archiviare le sue impostazioni di esportazione del prodotto personalizzate direttamente nella tabella `ps_configuration` o estendere dinamicamente le classi `ObjectModel` esistenti di PrestaShop (come `Product`), oppure utilizzare un'interazione diretta con il database all'interno del controller. Dati i campi dettagliati del modulo, è altamente probabile che le impostazioni Delcampe specifiche del prodotto siano archiviate in `ps_configuration` con chiavi come `dp_export_categories` o direttamente all'interno della logica di `AdminDelcampeProductsController`.

### 4.4 Risorse JavaScript (`views/js/`)

-   `delcampeproducts/lib/js/admin/delcampeproducts.js`
    -   **Ambito**: Back-office.
    -   **Dettagli**: Questo script viene caricato nel Back Office di PrestaShop, in particolare per il controller `AdminDelcampeProducts`. Probabilmente gestisce:
        -   Comportamento dinamico del modulo (ad esempio, mostrare/nascondere campi in base a `selling_type`).
        -   Chiamate AJAX per salvare le impostazioni o generare il file di esportazione.
        -   Validazione o formattazione dell'input per campi come `category_id`, `price`, `weight`.
        -   Qualsiasi elemento interattivo all'interno dei moduli di configurazione del prodotto o della griglia di elenco.
        -   Potenzialmente utilizza jQuery per la manipolazione del DOM e la gestione degli eventi.

### 4.5 Fogli di stile CSS (`views/css/`)

Il dossier del modulo non indica file CSS personalizzati. Ciò implica che il modulo si basa interamente sullo stile predefinito del Back Office di PrestaShop per i suoi moduli di configurazione e elenchi, garantendo un aspetto e una sensazione coerenti con il resto del pannello di amministrazione. Gli sviluppatori che desiderano stilizzare l'interfaccia amministrativa del modulo dovrebbero mirare alle classi CSS esistenti di PrestaShop o iniettare CSS personalizzato tramite l'hook `actionAdminControllerSetMedia`.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template degli hook (`views/templates/hook/`)**: Nessuno esplicitamente elencato, ma i moduli spesso utilizzano `displayAdminProductsExtra` o simili per le schede della pagina del prodotto.
-   **Template amministrativi (`views/templates/admin/`)**:
    -   `delcampeproducts/script.tpl`
        -   **Ambito**: Back-office.
        -   **Dettagli**: Questo template è probabilmente utilizzato per produrre variabili JavaScript o script inline necessari a `delcampeproducts.js`. Potrebbe passare valori di configurazione da PHP a JavaScript, o definire oggetti JS globali. Viene spesso renderizzato tramite l'hook `actionAdminControllerSetMedia`.
-   **Template front-office (`views/templates/front/`)**: Nessuno esplicitamente elencato, il che si allinea con la natura di esportazione in background del modulo.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il modulo probabilmente memorizza le sue impostazioni di configurazione nella tabella `ps_configuration` utilizzando chiavi come `dp_export_categories`, `dp_remember_settings`, `dp_option_homepage_promotion`, `dp_lister_status`, `dp_lister_creation_date`, `dp_lister_sending_date`, `dp_llister_sending_date`, `dp_lister_edit_date`, `dp_export_format`, `dp_export_active`, `dp_export_instock`, `dp_export_identification`, `dp_export_category`, `dp_export_manufacturers_default`.
    -   Per le impostazioni Delcampe specifiche del prodotto (come `category_id`, `title`, `price`, ecc.), dato che non è elencato alcun `ObjectModel` personalizzato, queste sono probabilmente memorizzate come dati serializzati all'interno di `ps_configuration` (meno ideale per le impostazioni per prodotto) o, più probabilmente, `AdminDelcampeProductsController` gestisce direttamente una tabella di database personalizzata (ad esempio, `ps_delcampe_product_settings`) che non è stata esplicitamente identificata nel dossier ma sarebbe un approccio standard per dati così dettagliati per prodotto. Se non esiste una tabella personalizzata, potrebbe utilizzare `Product::addFeature` o `Product::addCustomization` in modo non standard, o memorizzare i dati in `ps_product_lang` o `ps_product_shop` tramite override. **(Nota per lo sviluppatore: Indagare il database per `ps_delcampe_product_settings` o una tabella simile al momento dell'installazione.)**
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `actionProductUpdate` | Dopo l'aggiornamento di un prodotto nel Back Office. | Consente al modulo di reagire alle modifiche del prodotto (ad esempio, aggiornare i suoi dati di esportazione Delcampe interni, contrassegnare un prodotto per la riesportazione). |
| `actionAdminControllerSetMedia` | Quando un controller amministrativo viene caricato e i suoi media (JS/CSS) vengono impostati. | Utilizzato per iniettare il JavaScript personalizzato del modulo (`delcampeproducts.js`) e potenzialmente script inline (`script.tpl`) nelle pagine del Back Office, specialmente per il controller `AdminDelcampeProducts`. |
| `displayAdminProductsExtra` | (Implicito, spesso usato per le schede dei prodotti) | Se il modulo aggiunge una scheda alla pagina di modifica del prodotto per le impostazioni Delcampe, questo hook verrebbe utilizzato. (Non esplicitamente elencato come hook, ma comune per tale funzionalità). |
| `displayBackOfficeHeader` | Nell'intestazione di ogni pagina del Back Office. | Può essere utilizzato per JS/CSS globali lato amministratore o per visualizzare notifiche. |
| `moduleRoutes` | Durante la generazione delle rotte per il modulo. | Utilizzato per definire URL front-office personalizzati per controller come `feed.php`. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto completo per il modulo "Esporta prodotti su Delcampe Lister", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto dedicato è disponibile per assisterti con qualsiasi problema tecnico o domanda relativa alla funzionalità del modulo.
"""
