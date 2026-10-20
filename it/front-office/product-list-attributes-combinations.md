---
title: "Attributi elenco prodotti (combinazioni) - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Attributi elenco prodotti (combinazioni) di MyPresta.eu."
sidebar:
  label: "Attributi elenco prodotti (combinazioni)"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Product list attributes (combinations) su MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-list-attributes-combinations.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/product-list-attributes-combinations/)
>
> ---


# Attributi elenco prodotti (combinazioni)

## 1. Requisiti e compatibilità

-   **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
-   **Compatibilità PHP**: PHP 5.6 - 8.5
-   **Requisiti di hosting**: Sono richieste estensioni PHP standard (cURL, JSON, OpenSSL), che sono tipicamente disponibili nella maggior parte degli ambienti di hosting web moderni.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)
Dopo l'installazione, cliccando su "Configura" verrai indirizzato alla pagina delle impostazioni principali per il modulo "Attributi elenco prodotti (combinazioni)". Qui è dove controlli come le combinazioni vengono visualizzate negli elenchi dei tuoi prodotti.

#### Impostazioni generali

-   **Visualizza combinazioni nell'elenco prodotti:**
    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per il modulo. Controlla se le combinazioni di prodotti vengono visualizzate nelle pagine di elenco prodotti.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* Il modulo inietterà l'interfaccia di selezione delle combinazioni nei tuoi template di elenco prodotti, consentendo ai clienti di scegliere le varianti direttamente.
        -   *Quando disabilitato (NO):* Il modulo sarà inattivo nel front office e gli elenchi prodotti si comporteranno come PrestaShop standard, richiedendo ai clienti di visitare la pagina del prodotto per selezionare le combinazioni.
    -   **Valore consigliato:** SÌ (per utilizzare la funzionalità principale del modulo).
    -   **Scenario / esempio del commerciante:** Se vuoi offrire un'esperienza di acquisto più veloce, abilita questa opzione. Se preferisci che i clienti atterrino sempre sulla pagina del prodotto per maggiori dettagli, disabilitala.

-   **Visualizza pulsante "Aggiungi al carrello":**
    -   **Cosa fa questa impostazione:** Determina se un pulsante "Aggiungi al carrello" viene mostrato insieme ai selettori di combinazione nell'elenco prodotti.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* Un pulsante "Aggiungi al carrello" apparirà accanto alle opzioni di combinazione. Una volta che un cliente seleziona una combinazione, può cliccare su questo pulsante per aggiungerla al carrello.
        -   *Quando disabilitato (NO):* I selettori di combinazione saranno comunque visibili, ma i clienti dovranno cliccare sull'immagine o sul nome del prodotto per andare alla pagina del prodotto per aggiungerlo al carrello. Questo potrebbe essere utile se vuoi mostrare le opzioni ma incoraggiare comunque le visite alla pagina del prodotto.
    -   **Valore consigliato:** SÌ (per la massima comodità e conversione).
    -   **Scenario / esempio del commerciante:** Per un'esperienza di acquisto rapida, abilita questa opzione. Se i tuoi prodotti richiedono una lettura o una personalizzazione estesa prima dell'acquisto, potresti disabilitarla per guidare i clienti alla pagina del prodotto.

-   **Visualizza campo quantità:**
    -   **Cosa fa questa impostazione:** Controlla se un campo di input per la quantità viene visualizzato accanto al pulsante "Aggiungi al carrello" nell'elenco prodotti.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* I clienti possono specificare la quantità di una combinazione scelta che desiderano aggiungere al carrello direttamente dall'elenco prodotti.
        -   *Quando disabilitato (NO):* Il pulsante "Aggiungi al carrello" aggiungerà una singola unità della combinazione selezionata. I clienti dovrebbero quindi regolare le quantità nel carrello o nella pagina del prodotto.
    -   **Valore consigliato:** SÌ (per la maggior parte dei negozi, in quanto offre maggiore flessibilità).
    -   **Scenario / esempio del commerciante:** Se i clienti acquistano spesso più unità dello stesso articolo (ad esempio, calzini, articoli di cancelleria), abilita questa opzione. Se i tuoi prodotti vengono tipicamente acquistati uno alla volta, potresti disabilitarla per un aspetto più pulito.

-   **Visualizza riferimento prodotto:**
    -   **Cosa fa questa impostazione:** Mostra o nasconde il numero di riferimento del prodotto (SKU) accanto alle opzioni di combinazione.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* Il riferimento del prodotto sarà visibile, il che può essere utile per i clienti che tracciano articoli specifici o per i clienti B2B.
        -   *Quando disabilitato (NO):* Il riferimento non verrà visualizzato, portando a un'interfaccia più pulita e meno ingombra.
    -   **Valore consigliato:** NO (a meno che il tuo pubblico di destinazione non tragga specificamente beneficio dalla visualizzazione dei riferimenti).
    -   **Scenario / esempio del commerciante:** Per i negozi B2B o i prodotti tecnici in cui i clienti spesso ordinano per SKU, abilita questa opzione. Per la vendita al dettaglio generale, di solito non è necessario.

-   **Visualizza EAN13/JAN prodotto:**
    -   **Cosa fa questa impostazione:** Mostra o nasconde il numero di codice a barre EAN13 o JAN del prodotto.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* L'EAN13/JAN sarà visibile, il che può essere utile per i clienti che devono confrontare i prodotti utilizzando questi identificatori.
        -   *Quando disabilitato (NO):* L'EAN13/JAN non verrà visualizzato.
    -   **Valore consigliato:** NO (simile al riferimento, abilita solo se c'è una specifica esigenza del cliente).
    -   **Scenario / esempio del commerciante:** Raramente necessario per la visualizzazione nel front-office, ma potrebbe essere utile per nicchie specifiche o B2B.

-   **Visualizza UPC prodotto:**
    -   **Cosa fa questa impostazione:** Mostra o nasconde il numero di codice a barre UPC del prodotto.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* L'UPC sarà visibile.
        -   *Quando disabilitato (NO):* L'UPC non verrà visualizzato.
    -   **Valore consigliato:** NO (simile a EAN13/JAN).
    -   **Scenario / esempio del commerciante:** Simile a EAN13/JAN, tipicamente non un requisito del front-office per la maggior parte della vendita al dettaglio.

-   **Visualizza peso prodotto:**
    -   **Cosa fa questa impostazione:** Mostra o nasconde il peso del prodotto accanto alle opzioni di combinazione.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* Il peso del prodotto sarà visibile, il che può essere importante per i clienti preoccupati per i costi di spedizione o la movimentazione.
        -   *Quando disabilitato (NO):* Il peso non verrà visualizzato.
    -   **Valore consigliato:** NO (a meno che il peso non sia un fattore critico per i tuoi prodotti).
    -   **Scenario / esempio del commerciante:** Per i prodotti in cui il peso è un fattore di acquisto significativo (ad esempio, merci sfuse, parti di macchinari pesanti), abilita questa opzione.

-   **Visualizza prezzo prodotto:**
    -   **Cosa fa questa impostazione:** Controlla se il prezzo della combinazione selezionata viene aggiornato dinamicamente e visualizzato nell'elenco prodotti.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* Quando un cliente seleziona diverse combinazioni, il prezzo visualizzato si aggiornerà per riflettere il prezzo della combinazione specifica (inclusi eventuali impatti sul prezzo degli attributi).
        -   *Quando disabilitato (NO):* Il prezzo mostrato nell'elenco prodotti rimarrà il prezzo base del prodotto e i clienti potrebbero dover dedurre i prezzi delle combinazioni o andare alla pagina del prodotto.
    -   **Valore consigliato:** SÌ (cruciale per la trasparenza e l'acquisto informato).
    -   **Scenario / esempio del commerciante:** Abilita sempre questa opzione per una chiara definizione dei prezzi. Se disabilitata, i clienti potrebbero essere confusi dai cambiamenti di prezzo al checkout.

-   **Visualizza disponibilità prodotto:**
    -   **Cosa fa questa impostazione:** Mostra o nasconde lo stato di disponibilità delle scorte per la combinazione selezionata (ad esempio, "Disponibile", "Esaurito", "Ultimi articoli!").
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* I clienti vedranno lo stato delle scorte, aiutandoli a prendere decisioni di acquisto e prevenendo la frustrazione di tentare di ordinare articoli esauriti.
        -   *Quando disabilitato (NO):* Lo stato delle scorte non verrà mostrato, potenzialmente portando i clienti a tentare di aggiungere articoli esauriti al carrello.
    -   **Valore consigliato:** SÌ (altamente raccomandato per gestire le aspettative dei clienti).
    -   **Scenario / esempio del commerciante:** Essenziale per qualsiasi negozio per prevenire ordini di articoli non disponibili. Abilita sempre.

-   **Visualizza descrizione prodotto:**
    -   **Cosa fa questa impostazione:** Mostra o nasconde una breve descrizione del prodotto sotto le combinazioni.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* Apparirà una breve descrizione del prodotto, offrendo più contesto senza richiedere un clic alla pagina del prodotto.
        -   *Quando disabilitato (NO):* La descrizione non verrà mostrata, mantenendo l'elenco prodotti conciso.
    -   **Valore consigliato:** NO (gli elenchi prodotti sono solitamente per una navigazione rapida; le descrizioni dettagliate appartengono alla pagina del prodotto).
    -   **Scenario / esempio del commerciante:** Se hai descrizioni molto brevi e d'impatto che aiutano le decisioni rapide, potresti abilitare questa opzione. Altrimenti, tienila disattivata per evitare disordine.

-   **Visualizza descrizione breve prodotto:**
    -   **Cosa fa questa impostazione:** Simile a "Visualizza descrizione prodotto", ma specificamente per il campo della descrizione breve.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* La descrizione breve del prodotto sarà visibile.
        -   *Quando disabilitato (NO):* La descrizione breve non verrà visualizzata.
    -   **Valore consigliato:** NO (per le stesse ragioni della descrizione completa).
    -   **Scenario / esempio del commerciante:** Utilizza con parsimonia, solo se le tue descrizioni brevi sono estremamente concise e cruciali per l'acquisto in modalità elenco.

-   **Visualizza immagini prodotto:**
    -   **Cosa fa questa impostazione:** Determina se l'immagine del prodotto si aggiorna dinamicamente quando un cliente seleziona una combinazione diversa (ad esempio, selezionando una maglietta "blu" mostra l'immagine della maglietta blu).
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* L'immagine principale del prodotto nell'elenco cambierà per riflettere l'immagine associata alla combinazione selezionata. Questo fornisce un ricco feedback visivo.
        -   *Quando disabilitato (NO):* L'immagine del prodotto rimarrà statica, mostrando l'immagine predefinita del prodotto indipendentemente dalla combinazione selezionata.
    -   **Valore consigliato:** SÌ (altamente raccomandato per la conferma visiva e una migliore esperienza utente).
    -   **Scenario / esempio del commerciante:** Cruciale per abbigliamento, elettronica o qualsiasi prodotto in cui la rappresentazione visiva della variante è importante.

-   **Visualizza attributi prodotto come:**
    -   **Cosa fa questa impostazione:** Questa è un'impostazione cruciale che definisce come le opzioni di combinazione (ad esempio, taglia, colore) vengono presentate al cliente.
    -   **Effetto della modifica di questa impostazione:**
        -   *Elenco a discesa:* Gli attributi appariranno come elementi `<select>` standard HTML a discesa. Questo è compatto e adatto a molte opzioni.
        -   *Pulsanti radio:* Gli attributi appariranno come pulsanti radio. Ottimo per un piccolo numero di opzioni distinte.
        -   *Selettore colore:* Se i tuoi attributi sono definiti come tipo "colore" in PrestaShop, questo li visualizzerà come campioni di colore cliccabili.
    -   **Valore consigliato:**
        -   *Selettore colore* per gli attributi di colore.
        -   *Elenco a discesa* per gli attributi con molte opzioni (ad esempio, taglie S-XXL).
        -   *Pulsanti radio* per gli attributi con poche opzioni distinte (ad esempio, "Sì/No", "Con/Senza").
    -   **Scenario / esempio del commerciante:** Per un negozio di abbigliamento, probabilmente useresti "Selettore colore" per i colori e "Elenco a discesa" per le taglie. Per un prodotto semplice con due opzioni come "Confezione regalo: Sì/No", i pulsanti radio potrebbero essere i migliori.

-   **Visualizza attributi prodotto per:**
    -   **Cosa fa questa impostazione:** Ti consente di specificare quali attributi del prodotto dovrebbero avere le loro combinazioni visualizzate nell'elenco prodotti. Puoi selezionare gruppi di attributi specifici (ad esempio, "Taglia", "Colore", "Materiale").
    -   **Effetto della modifica di questa impostazione:**
        -   *Gruppi di attributi selezionati:* Verranno visualizzate solo le combinazioni che coinvolgono i gruppi di attributi scelti. Ad esempio, se selezioni "Colore" e "Taglia", i clienti vedranno le opzioni per colori e taglie.
        -   *Nessuna selezione:* Se non viene selezionato nulla, il modulo potrebbe impostare come predefinito la visualizzazione di tutti gli attributi o nessuno, a seconda della logica interna del modulo. È meglio selezionare esplicitamente.
    -   **Valore consigliato:** Seleziona tutti i gruppi di attributi pertinenti che definiscono le combinazioni dei tuoi prodotti.
    -   **Scenario / esempio del commerciante:** Se vendi T-shirt in diversi colori e taglie, seleziona "Colore" e "Taglia". Se hai anche un attributo "Materiale" ma non vuoi mostrarlo nell'elenco, lascialo deselezionato.

-   **Hook per visualizzare il modulo:**
    -   **Cosa fa questa impostazione:** Determina dove verranno iniettati i selettori di combinazione nelle pagine di elenco prodotti.
    -   **Effetto della modifica di questa impostazione:**
        -   `displayProductListFunctionalButtons`: Questo hook si trova tipicamente vicino al pulsante "Aggiungi al carrello" o ad altri elementi funzionali sugli articoli dell'elenco prodotti.
        -   `displayProductListReviews`: Spesso vicino alle stelle delle recensioni o al numero di recensioni.
        -   `displayProductListPrice`: Di solito vicino al prezzo del prodotto.
        -   `displayProductListExtraContent`: Un hook generale per contenuti extra, spesso nella parte inferiore della scheda prodotto.
        -   `displayProductListFooter`: Nella parte inferiore della scheda prodotto.
    -   **Valore consigliato:** `displayProductListFunctionalButtons` o `displayProductListExtraContent` sono scelte comuni, ma questo dipende molto dal layout del tuo tema. Potrebbe essere necessario sperimentare per trovare il posizionamento visivo migliore.
    -   **Scenario / esempio del commerciante:** Se il tuo tema ha un'area pulita sotto il nome e il prezzo del prodotto, `displayProductListFunctionalButtons` potrebbe adattarsi bene. Se vuoi che le opzioni appaiano in modo più prominente, `displayProductListExtraContent` potrebbe essere migliore.

-   **Escludi prodotti dal modulo:**
    -   **Cosa fa questa impostazione:** Ti consente di specificare singoli prodotti tramite il loro ID che *non* dovrebbero visualizzare le combinazioni nell'elenco prodotti, anche se il modulo è generalmente abilitato.
    -   **Effetto della modifica di questa impostazione:**
        -   *Inserendo gli ID dei prodotti (separati da virgola):* I prodotti specificati torneranno al comportamento standard di PrestaShop negli elenchi prodotti, richiedendo un clic sulla pagina del prodotto per la selezione delle combinazioni.
        -   *Lasciando vuoto:* Tutti i prodotti con combinazioni le visualizzeranno nell'elenco.
    -   **Valore consigliato:** Lascia vuoto a meno che tu non abbia prodotti specifici che richiedono una visita completa alla pagina del prodotto.
    -   **Scenario / esempio del commerciante:** Potresti avere alcuni prodotti complessi con molti attributi, o prodotti che richiedono un configuratore dettagliato, dove preferisci che i clienti atterrino prima sulla pagina del prodotto.

-   **Escludi categorie dal modulo:**
    -   **Cosa fa questa impostazione:** Ti consente di specificare categorie tramite il loro ID che *non* dovrebbero visualizzare le combinazioni nei loro elenchi prodotti.
    -   **Effetto della modifica di questa impostazione:**
        -   *Inserendo gli ID delle categorie (separati da virgola):* I prodotti all'interno di queste categorie non mostreranno le combinazioni nelle rispettive pagine di elenco.
        -   *Lasciando vuoto:* Tutte le categorie visualizzeranno le combinazioni dei prodotti.
    -   **Valore consigliato:** Lascia vuoto a meno che tu non abbia categorie specifiche in cui questa funzione non è desiderata.
    -   **Scenario / esempio del commerciante:** Se hai una categoria "Liquidazione" in cui tutti i prodotti sono a variante singola e vuoi mantenere la visualizzazione molto minimale, potresti escluderla.

#### 2.1.1 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
|---|---|---|---|
| Configurazione modulo | Visualizza combinazioni nell'elenco prodotti | SÌ | Interruttore principale per abilitare/disabilitare la visualizzazione delle combinazioni negli elenchi prodotti. |
| Configurazione modulo | Visualizza pulsante "Aggiungi al carrello" | SÌ | Mostra un pulsante "Aggiungi al carrello" accanto alle combinazioni per l'acquisto diretto. |
| Configurazione modulo | Visualizza campo quantità | SÌ | Consente ai clienti di selezionare la quantità direttamente nell'elenco prodotti. |
| Configurazione modulo | Visualizza riferimento prodotto | NO | Mostra/nasconde lo SKU del prodotto. |
| Configurazione modulo | Visualizza EAN13/JAN prodotto | NO | Mostra/nasconde l'EAN13/JAN del prodotto. |
| Configurazione modulo | Visualizza UPC prodotto | NO | Mostra/nasconde l'UPC del prodotto. |
| Configurazione modulo | Visualizza peso prodotto | NO | Mostra/nasconde il peso del prodotto. |
| Configurazione modulo | Visualizza prezzo prodotto | SÌ | Aggiorna dinamicamente il prezzo in base alla combinazione selezionata. |
| Configurazione modulo | Visualizza disponibilità prodotto | SÌ | Mostra lo stato delle scorte per la combinazione selezionata. |
| Configurazione modulo | Visualizza descrizione prodotto | NO | Mostra/nasconde la descrizione completa del prodotto. |
| Configurazione modulo | Visualizza descrizione breve prodotto | NO | Mostra/nasconde la descrizione breve del prodotto. |
| Configurazione modulo | Visualizza immagini prodotto | SÌ | Aggiorna dinamicamente l'immagine del prodotto in base alla combinazione selezionata. |
| Configurazione modulo | Visualizza attributi prodotto come | Menu a discesa, Radio, Selettore colore | Definisce la presentazione visiva delle opzioni degli attributi. |
| Configurazione modulo | Visualizza attributi prodotto per | Seleziona i gruppi pertinenti | Specifica quali gruppi di attributi visualizzare. |
| Configurazione modulo | Hook per visualizzare il modulo | `displayProductListFunctionalButtons` | Determina il posizionamento visivo del modulo sulle schede prodotto. |
| Configurazione modulo | Escludi prodotti dal modulo | Lascia vuoto | ID prodotto separati da virgola da escludere dalla funzione. |
| Configurazione modulo | Escludi categorie dal modulo | Lascia vuoto | ID categoria separati da virgola da escludere dalla funzione. |

### 2.2 Schermate di amministrazione dedicate e viste del controller

Questo modulo utilizza controller di amministrazione personalizzati per la gestione interna, ma questi non sono tipicamente accessibili direttamente dal commerciante per la configurazione quotidiana. Sono principalmente per operazioni interne del modulo o debug avanzato.

#### 2.2.1 AdminPlaSearchController (Back Office > Moduli > Attributi elenco prodotti (combinazioni) > Configurazione ricerca)
-   **Nome schermata e posizione menu:** Questo controller è probabilmente utilizzato per la configurazione della ricerca interna o la gestione dei dati relativi a come le combinazioni vengono indicizzate o recuperate. Potrebbe non avere una voce di menu diretta e visibile per il commerciante, oppure potrebbe essere una scheda interna all'interno della configurazione principale del modulo.
-   **Azioni e impostazioni disponibili:** Questa schermata presenterebbe tipicamente una vista a griglia o elenco di dati (ad esempio, prodotti indicizzati, mappature degli attributi) e potrebbe offrire azioni come "Ricostruisci indice", "Svuota cache" o "Modifica impostazioni di ricerca".
-   **Effetto delle modifiche:** Le modifiche qui influirebbero sulle prestazioni o sull'accuratezza della visualizzazione delle combinazioni, specialmente in cataloghi di grandi dimensioni. Impostazioni errate potrebbero portare alla mancata visualizzazione delle combinazioni o a un caricamento lento.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** I commercianti generalmente non hanno bisogno di interagire con questa schermata a meno che non sia consigliato dal supporto o per la risoluzione avanzata dei problemi. La pagina di configurazione principale del modulo gestisce tutte le impostazioni rivolte all'utente.

#### 2.2.2 index.php (pla/controllers/admin/index.php)
-   **Nome schermata e posizione menu:** Questo file `index.php` all'interno della directory del controller `admin` è una pratica comune di PrestaShop per prevenire l'elenco delle directory. Tipicamente non rappresenta una schermata rivolta all'utente, ma piuttosto garantisce la sicurezza e il corretto routing per altri controller di amministrazione all'interno del modulo.
-   **Azioni e impostazioni disponibili:** Nessuna azione o impostazione diretta rivolta al commerciante.
-   **Effetto delle modifiche:** Nessun effetto diretto sulla visualizzazione del negozio o sui dati, in quanto è un file strutturale.
-   **Flusso di lavoro consigliato per la gestione quotidiana del negozio:** Nessuna interazione richiesta.

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Le combinazioni non vengono visualizzate nell'elenco dei miei prodotti. Cosa devo fare?**
R:
1.  **Verifica lo stato del modulo:** Vai su **Moduli > Gestione moduli**, trova "Attributi elenco prodotti (combinazioni)" e assicurati che sia installato e abilitato.
2.  **Verifica la configurazione del modulo:** Vai alla pagina di configurazione del modulo. Assicurati che "Visualizza combinazioni nell'elenco prodotti" sia impostato su SÌ.
3.  **Verifica i gruppi di attributi:** Assicurati di aver selezionato i gruppi corretti per "Visualizza attributi prodotto per" (ad esempio, "Taglia", "Colore").
4.  **Verifica le esclusioni:** Verifica che il prodotto o la categoria che stai testando non sia elencato in "Escludi prodotti dal modulo" o "Escludi categorie dal modulo".
5.  **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). A volte, i vecchi file memorizzati nella cache impediscono la visualizzazione dei nuovi contenuti del modulo.
6.  **Compatibilità del tema:** Il tuo tema potrebbe essere pesantemente personalizzato e non utilizzare gli hook standard di PrestaShop. Prova a cambiare l'impostazione "Hook per visualizzare il modulo" con un hook diverso (ad esempio, `displayProductListExtraContent`) e svuota la cache. Se i problemi persistono, contatta il tuo webmaster o il supporto MyPresta.eu.

**D: Il pulsante "Aggiungi al carrello" o il campo quantità non vengono visualizzati.**
R:
1.  **Verifica la configurazione del modulo:** Assicurati che "Visualizza pulsante 'Aggiungi al carrello'" e "Visualizza campo quantità" siano entrambi impostati su SÌ nella configurazione del modulo.
2.  **Svuota la cache:** Svuota sempre la cache di PrestaShop dopo aver apportato modifiche alla configurazione.

**D: L'immagine del prodotto non cambia quando seleziono una combinazione diversa.**
R:
1.  **Verifica la configurazione del modulo:** Assicurati che "Visualizza immagini prodotto" sia impostato su SÌ.
2.  **Immagini prodotto:** Verifica che le combinazioni del tuo prodotto abbiano effettivamente immagini associate. Nella pagina di back office del tuo prodotto, vai alla scheda "Combinazioni" e assicurati che ogni combinazione abbia immagini collegate.
3.  **Svuota la cache:** Svuota la cache di PrestaShop.

**D: Lo stile (colori, allineamento) delle combinazioni sembra sbagliato nel mio negozio.**
R:
Questo è solitamente un conflitto CSS con il tuo tema.
1.  **Svuota la cache:** A volte, svuotare la cache aiuta.
2.  **Personalizzazione del tema:** Il tuo tema potrebbe avere regole di stile specifiche che sovrascrivono o sono in conflitto con il CSS predefinito del modulo. Ciò richiede a un webmaster o a uno sviluppatore di ispezionare il CSS e apportare modifiche al foglio di stile del tuo tema. Il modulo fornisce i propri file CSS, ma i temi possono sempre sovrascriverli.

**D: Questo modulo funziona con negozi multilingue?**
R: Sì, il modulo è progettato per essere compatibile con le funzionalità multilingue di PrestaShop. I nomi e i valori degli attributi verranno visualizzati nella lingua del front-office selezionata, a condizione che siano correttamente tradotti nel back office di PrestaShop (Catalogo > Attributi e caratteristiche).

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata del modulo "Attributi elenco prodotti (combinazioni)" per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura
Il modulo segue un modello MVC (Model-View-Controller) standard di PrestaShop, estendendo principalmente `Module` per la sua funzionalità principale e `ModuleFrontController` per le interazioni AJAX. Sfrutta il sistema di hook di PrestaShop per iniettare il suo contenuto nei template di elenco prodotti. La logica principale del modulo risiede in `index.php` (il file principale del modulo), che gestisce l'installazione, la disinstallazione e il metodo `getContent()` per la configurazione del back-office. La visualizzazione del front-office è gestita tramite template Smarty renderizzati tramite hook, con interazioni dinamiche alimentate da JavaScript e AJAX.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office
-   `controllers/front/ajax.php`
    *   **Nome classe e classe genitore:** `PlaAjaxModuleFrontController` estende `ModuleFrontController`.
    *   **Responsabilità:** Questo controller gestisce tutte le richieste AJAX dal front office. Quando un cliente interagisce con i selettori di combinazione (ad esempio, cambia una taglia o un colore), questo controller è responsabile di ricevere la richiesta, elaborarla (ad esempio, recuperare prezzi aggiornati, scorte, immagini per la combinazione selezionata) e restituire una risposta JSON per aggiornare il front-end dinamicamente senza un ricaricamento completo della pagina. È cruciale per l'esperienza interattiva del modulo.
-   `controllers/front/index.php`
    *   **Nome classe e classe genitore:** `PlaIndexModuleFrontController` estende `ModuleFrontController`.
    *   **Responsabilità:** Questo è un controller frontale segnaposto, spesso utilizzato per prevenire l'elenco delle directory o come fallback per percorsi specifici del modulo. Nel contesto di questo modulo, potrebbe non avere un routing diretto e attivo, ma serve come pratica standard di PrestaShop. L'interazione principale del front-office avviene tramite `ajax.php`.

#### Controller di amministrazione Back-Office
-   `controllers/admin/AdminPlaSearchController.php`
    *   **Nome classe e classe genitore:** `AdminPlaSearchController` estende `ModuleAdminController`.
    *   **Nome scheda ed entità gestita:** Questo controller probabilmente gestisce meccanismi di ricerca o indicizzazione interni per le combinazioni di prodotti. Potrebbe non avere una voce di menu diretta ma potrebbe essere accessibile internamente dal modulo per attività come la ricostruzione di un indice di ricerca per le combinazioni. Gestirebbe tipicamente un'entità virtuale correlata ai dati di ricerca piuttosto che un `ObjectModel` diretto.
-   `controllers/admin/index.php`
    *   **Nome classe e classe genitore:** Non una classe controller diretta, ma un file `index.php` standard.
    *   **Nome scheda ed entità gestita:** Questo file è una misura di sicurezza per prevenire l'elenco delle directory della cartella `admin`. Non rappresenta di per sé una schermata di amministrazione funzionale.

### 4.3 Classi e modelli principali (`classes/`)
Il dossier del modulo indica l'assenza di classi o modelli personalizzati nella directory `classes/`. Ciò suggerisce che il modulo opera principalmente estendendo le funzionalità principali esistenti di PrestaShop (come `Product`, `Combination`) e utilizza query dirette al database o la classe `Db` di PrestaShop per l'interazione con i dati, piuttosto che definire le proprie entità `ObjectModel`. Tutta la logica principale è probabilmente incapsulata nel file principale del modulo (`pla/index.php`) e nei suoi controller.

### 4.4 Risorse JavaScript (`views/js/`)
-   `pla/lib/searchTool/views/js/autocomplete.js`
    *   **Ambito:** Potenzialmente sia Front-office (per funzionalità di ricerca in tempo reale se integrata) che Back-office (per campi di ricerca amministrativi). Dato il focus del modulo, è più probabile per la configurazione di ricerca del back-office correlata a `AdminPlaSearchController`.
    *   **Dettagli:** Gestisce la funzionalità di completamento automatico, probabilmente per la ricerca di prodotti o attributi all'interno della configurazione amministrativa del modulo o di una funzione di ricerca personalizzata. Si legherebbe ai campi di input, ascolterebbe gli eventi `keyup` ed effettuerebbe chiamate AJAX per recuperare i suggerimenti.
-   `pla/views/templates/js/pla.js`
    *   **Ambito:** Front-office.
    *   **Dettagli:** Questo è il file JavaScript principale per la funzionalità del front-office.
        *   **Listener di eventi:** Collega gli eventi `change` ai selettori di combinazione (menu a discesa, pulsanti radio, selettori di colore) sugli elementi dell'elenco prodotti.
        *   **Manipolazione del DOM:** Aggiorna i prezzi dei prodotti, lo stato delle scorte, le immagini dei prodotti e gli stati dei pulsanti "Aggiungi al carrello" in base alle combinazioni selezionate.
        *   **Chiamate AJAX:** Effettua richieste AJAX a `controllers/front/ajax.php` per recuperare i dati di combinazione aggiornati (prezzo, scorte, URL immagine, ecc.) quando una selezione cambia.
        *   **Inizializzazione del modulo:** Probabilmente contiene codice per inizializzare i selettori di combinazione al caricamento della pagina e per reinizializzarli dopo gli aggiornamenti AJAX (ad esempio, scorrimento infinito, filtraggio per categoria).

### 4.5 Fogli di stile CSS (`views/css/`)
-   `pla/css.css`
    *   **Ambito:** Probabilmente Front-office.
    *   **Dettagli:** Stile generale per gli elementi di visualizzazione delle combinazioni negli elenchi prodotti. Contiene stili di base per menu a discesa, pulsanti radio, campi quantità e pulsanti "Aggiungi al carrello" come renderizzati dal modulo.
-   `pla/lib/searchTool/views/css/autocomplete.css`
    *   **Ambito:** Potenzialmente sia Front-office che Back-office.
    *   **Dettagli:** Stili per l'elenco dei suggerimenti di completamento automatico e i campi di input, probabilmente utilizzati in combinazione con `autocomplete.js`.
-   `pla/views/templates/css/pla-classic.css`
    *   **Ambito:** Front-office.
    *   **Dettagli:** Stile specifico adattato per temi PrestaShop più vecchi (ad esempio, tema Classic o strutture simili). Potrebbe contenere override più espliciti o stili di fallback.
-   `pla/views/templates/css/pla.css`
    *   **Ambito:** Front-office.
    *   **Dettagli:** Stile primario per gli elementi del front-office del modulo, potenzialmente per versioni più recenti di PrestaShop o un approccio più generico. Contiene stili per i wrapper delle combinazioni, le opzioni degli attributi e gli elementi dinamici.
    *   **Selettori di classi CSS chiave:** Gli sviluppatori possono aspettarsi classi come `.pla-combinations-wrapper`, `.pla-attribute-group`, `.pla-attribute-option`, `.pla-add-to-cart-btn`, `.pla-quantity-input`, `.pla-price-display`, `.pla-availability-status` e possono sovrascriverle nel file `custom.css` o `theme.css` del loro tema.

### 4.6 Struttura del template Smarty (`views/templates/`)

#### Template degli hook (`views/templates/hook/`)
-   `pla/views/templates/hook/pla.tpl`
    *   **Hook:** Destinato principalmente a hook come `displayProductListFunctionalButtons`, `displayProductListExtraContent`, ecc.
    *   **Output:** Questo è il template principale responsabile del rendering dei selettori di combinazione, del pulsante "Aggiungi al carrello", del campo quantità, del prezzo e della disponibilità su ogni articolo del prodotto nell'elenco prodotti. Itera attraverso i gruppi di attributi e i valori disponibili, generando l'HTML appropriato (menu a discesa, pulsanti radio, campioni di colore) in base alla configurazione del modulo.

#### Template di amministrazione (`views/templates/admin/`)
-   `pla/views/templates/admin/admin.tpl`
    *   **Scopo:** Questo template viene utilizzato per la pagina di configurazione principale del modulo nel back office di PrestaShop (accessibile tramite `getContent()` in `pla/index.php`). Contiene i moduli per tutte le impostazioni descritte nella Sezione 4.1.
-   `pla/views/templates/admin/selectedCa.tpl`
    *   **Scopo:** Probabilmente un template parziale utilizzato all'interno di un modulo o di una griglia di amministrazione per visualizzare le categorie selezionate (ad esempio, per l'impostazione "Escludi categorie dal modulo"). Renderizzerebbe un elenco di categorie selezionate, possibilmente con opzioni per rimuoverle.
-   `pla/views/templates/admin/selectedProducts.tpl`
    *   **Scopo:** Simile a `selectedCa.tpl`, ma per i prodotti selezionati (ad esempio, per l'impostazione "Escludi prodotti dal modulo"). Visualizzerebbe un elenco di prodotti selezionati.

#### Template JavaScript (`views/templates/js/`)
-   `pla/views/templates/js/pla_admin.tpl`
    *   **Ambito:** Back-office.
    *   **Output:** Questo template probabilmente contiene codice JavaScript specifico per il pannello di amministrazione. Potrebbe includere script per la gestione di elementi dinamici del modulo, chiamate AJAX all'interno dell'amministrazione o l'inizializzazione di componenti nella pagina di configurazione del modulo.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database
Il dossier del modulo indica l'assenza di file SQL personalizzati. Ciò implica che il modulo memorizza principalmente le sue impostazioni di configurazione nella tabella `ps_configuration` di PrestaShop.
-   **`ps_configuration`**: Memorizza le impostazioni del modulo (ad esempio, `PLA_DISPLAY_COMBINATIONS`, `PLA_DISPLAY_ADD_TO_CART`, `PLA_EXCLUDE_PRODUCTS`, `PLA_HOOK_NAME`, ecc.). Queste chiavi sono tipicamente prefissate con `PLA_` o `MYPRESTA_PLA_`.

#### Tabella degli hook registrati
Il modulo registra e utilizza diversi hook di PrestaShop per integrare la sua funzionalità.

| Nome hook | Tempistica di esecuzione | Scopo tecnico |
|---|---|---|
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Per includere i file CSS e JavaScript necessari per la funzionalità del front-office del modulo. |
| `displayProductListFunctionalButtons` | All'interno di ogni articolo del prodotto nelle pagine di elenco prodotti, tipicamente vicino ai pulsanti di azione. | Un hook comune per iniettare i selettori di combinazione e il pulsante "Aggiungi al carrello". |
| `displayProductListReviews` | All'interno di ogni articolo del prodotto nelle pagine di elenco prodotti, spesso vicino agli elementi di recensione. | Hook alternativo per visualizzare le opzioni di combinazione. |
| `displayProductListPrice` | All'interno di ogni articolo del prodotto nelle pagine di elenco prodotti, vicino al prezzo del prodotto. | Hook alternativo per visualizzare le opzioni di combinazione. |
| `displayProductListExtraContent` | Un hook generico all'interno di ogni articolo del prodotto per contenuti aggiuntivi. | Hook flessibile per iniettare i selettori di combinazione, spesso nella parte inferiore della scheda prodotto. |
| `displayProductListFooter` | Nella parte inferiore di ogni articolo del prodotto nelle pagine di elenco prodotti. | Un altro hook alternativo per visualizzare le opzioni di combinazione. |
| `actionFrontControllerSetMedia` | Prima che un controller frontale renderizzi il suo contenuto, consentendo ai moduli di aggiungere risorse. | Per caricare condizionalmente risorse JS/CSS specifiche solo quando necessarie al modulo nelle pagine pertinenti. |
| `actionProductUpdate` | Dopo che un prodotto viene aggiornato nel back office. | Potenzialmente utilizzato per svuotare le cache specifiche del modulo o reindicizzare i dati delle combinazioni di prodotti se il modulo ha un meccanismo di indicizzazione interno. |
| `actionAttributeGroupUpdate` / `actionAttributeUpdate` | Dopo che i gruppi di attributi o gli attributi vengono aggiornati. | Simile a `actionProductUpdate`, per lo svuotamento della cache o la reindicizzazione. |

## 5. Supporto ufficiale e aggiornamenti
Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team è dedicato a fornire assistenza e garantire il buon funzionamento del vostro modulo.
"""
