---
title: "Blocchi Categorie Multiple - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Blocchi Categorie Multiple di MyPresta.eu."
sidebar:
  label: "Blocchi Categorie Multiple - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Multiple Categories Blocks su MyPresta.eu](https://mypresta.eu/modules/front-office-features/multiple-categories-blocks.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/multiple-categories-blocks/)
>
> ---


# Blocchi Categorie Multiple

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono generalmente sufficienti. Di solito non sono necessarie configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Blocchi Categorie Multiple)

Questa è la schermata di configurazione principale dove creerai e gestirai tutti i tuoi blocchi di categorie personalizzati.

Entrando nella pagina di configurazione, vedrai un elenco di blocchi di categorie esistenti (se presenti) e le opzioni per aggiungerne di nuovi.

#### **Aggiunta / Modifica di un blocco di categorie**

Quando fai clic su "Aggiungi nuovo blocco" o modifichi uno esistente, ti verranno presentate le seguenti impostazioni:

- **Nome blocco:**

  - **Cosa fa questa impostazione:** Questo è un nome interno per il tuo riferimento nel Back Office. Ti aiuta a identificare i diversi blocchi.
  - **Effetto della modifica di questa impostazione:** Influisce solo su come vedi il blocco nel pannello di amministrazione. Non è visibile ai clienti.
  - **Valore consigliato:** Un nome descrittivo (es. "Categorie Elettronica Homepage", "Abbigliamento Colonna Sinistra").
  - **Scenario / esempio per il commerciante:** Se hai un blocco per "Moda Uomo" nella colonna sinistra, chiamalo "Colonna Sinistra - Moda Uomo".
- **Visualizza titolo blocco:**

  - **Cosa fa questa impostazione:** Determina se un titolo (es. "Categorie") viene visualizzato sopra l'elenco delle categorie nel front office.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (Sì):* Un titolo apparirà sopra il blocco di categorie. Puoi definire questo titolo nel campo "Titolo blocco".
    - *Quando disabilitato (No):* Non verrà visualizzato alcun titolo, solo l'elenco delle categorie.
  - **Valore consigliato:** "Sì" per la maggior parte dei blocchi, in quanto fornisce contesto al cliente.
  - **Scenario / esempio per il commerciante:** Se vuoi che il tuo blocco si integri semplicemente nel design senza un titolo esplicito, impostalo su "No".
- **Titolo blocco:** (Appare solo se "Visualizza titolo blocco" è Sì)

  - **Cosa fa questa impostazione:** Il testo effettivo che verrà visualizzato come titolo del blocco nel front office. Questo è multilingua.
  - **Effetto della modifica di questa impostazione:** Modifica il titolo visibile per i clienti.
  - **Valore consigliato:** Un titolo chiaro e conciso (es. "Acquista per categoria", "I nostri prodotti", "Reparti").
  - **Scenario / esempio per il commerciante:** Per un blocco che mostra solo categorie di "Elettronica", potresti impostare il titolo su "Elettronica".
- **Hook per visualizzare il blocco:**

  - **Cosa fa questa impostazione:** Seleziona dove nel tuo negozio apparirà questo blocco di categorie. Gli hook sono punti di visualizzazione specifici nel tuo tema PrestaShop.
  - **Effetto della modifica di questa impostazione:** Determina la posizione fisica del blocco sul tuo sito web.
  - **Valore consigliato:** Dipende dal tuo design. Le scelte comuni sono `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayHome`.
  - **Scenario / esempio per il commerciante:** Per mostrare un blocco nella barra laterale sinistra, seleziona `displayLeftColumn`. Per mostrarlo nel piè di pagina, seleziona `displayFooter`.
- **Categoria radice:**

  - **Cosa fa questa impostazione:** Questo è il punto di partenza (il "genitore") per le categorie visualizzate in questo blocco specifico. Verranno mostrate solo questa categoria e le sue sottocategorie.
  - **Effetto della modifica di questa impostazione:**
    - *Selezionando "Home":* Il blocco visualizzerà tutte le categorie a partire dalla cima del tuo albero di categorie.
    - *Selezionando una categoria specifica (es. "Elettronica"):* Il blocco mostrerà solo "Elettronica" e tutte le sue sottocategorie.
  - **Valore consigliato:** Scegli la categoria di livello più alto che definisce l'ambito di questo blocco.
  - **Scenario / esempio per il commerciante:** Se desideri un blocco specifico per "Abbigliamento", seleziona qui la tua categoria "Abbigliamento".
- **Profondità massima:**

  - **Cosa fa questa impostazione:** Controlla quanti livelli di sottocategorie vengono visualizzati all'interno di questo blocco, a partire dalla Categoria radice.
  - **Effetto della modifica di questa impostazione:**
    - *Impostando su 1:* Verrà mostrata solo la Categoria radice stessa (se "Visualizza Categoria radice" è Sì).
    - *Impostando su 2:* Verranno mostrate la Categoria radice e le sue sottocategorie immediate.
    - *Impostando su 0 (o vuoto):* Verranno visualizzate tutte le sottocategorie, indipendentemente dalla profondità.
  - **Valore consigliato:** 2 o 3 per la maggior parte dei blocchi di colonna per mantenerli gestibili. 0 per i blocchi di piè di pagina se desideri una mappa del sito completa.
  - **Scenario / esempio per il commerciante:** Se la tua categoria "Elettronica" ha sottocategorie come "Fotocamere" e "Laptop", e "Fotocamere" ha "DSLR" e "Mirrorless", impostando la profondità su 2 verrebbe mostrato "Elettronica > Fotocamere, Laptop". Impostando su 3 verrebbe mostrato "Elettronica > Fotocamere > DSLR, Mirrorless, Laptop".
- **Dinamico (apri l'albero delle categorie corrente):**

  - **Cosa fa questa impostazione:** Quando un cliente naviga a una pagina di categoria, questa opzione determina se il blocco di categorie si espande automaticamente per mostrare la categoria corrente e le sue sottocategorie.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (Sì):* Se un cliente si trova sulla pagina "DSLR", il blocco di categorie espanderà automaticamente "Elettronica > Fotocamere > DSLR" per mostrare il percorso.
    - *Quando disabilitato (No):* Il blocco di categorie rimarrà nel suo stato predefinito compresso, indipendentemente dalla pagina corrente.
  - **Valore consigliato:** "Sì" per una migliore esperienza utente, in quanto aiuta i clienti a capire la loro posizione attuale nell'albero delle categorie.
  - **Scenario / esempio per il commerciante:** Questo è particolarmente utile nelle colonne laterali per mantenere la navigazione pertinente al contesto di navigazione corrente dell'utente.
- **Visualizza Categoria radice:**

  - **Cosa fa questa impostazione:** Controlla se la "Categoria radice" stessa (quella che hai selezionato sopra) viene visualizzata come primo elemento nel blocco.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (Sì):* La Categoria radice sarà il primo elemento cliccabile nel blocco.
    - *Quando disabilitato (No):* Il blocco inizierà a visualizzare dalle sottocategorie immediate della Categoria radice.
  - **Valore consigliato:** "Sì" se la Categoria radice è una categoria ampia come "Acquista per reparto". "No" se la Categoria radice è solo un raggruppamento logico e vuoi iniziare direttamente con le sue sottocategorie (es. un blocco "Marche" dove "Marche" stessa non è una categoria di prodotto).
  - **Scenario / esempio per il commerciante:** Se la tua Categoria radice è "Abbigliamento Uomo" e vuoi che sia il link principale, imposta su "Sì". Se vuoi che il blocco inizi direttamente con "Camicie", "Pantaloni", ecc., imposta su "No".
- **Visualizza numero di prodotti:**

  - **Cosa fa questa impostazione:** Mostra il conteggio dei prodotti disponibili all'interno di ogni categoria accanto al suo nome nel blocco.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (Sì):* Le categorie appariranno come "Nome Categoria (X)".
    - *Quando disabilitato (No):* Verrà visualizzato solo il nome della categoria.
  - **Valore consigliato:** "Sì" può essere utile per i clienti per valutare la dimensione di una categoria, ma "No" può portare a un aspetto più pulito. Prova entrambi per vedere cosa si adatta al tuo design.
  - **Scenario / esempio per il commerciante:** Se vuoi mostrare "T-shirt (125)" accanto al nome della categoria, abilita questa opzione.
- **Visualizza categorie senza prodotti:**

  - **Cosa fa questa impostazione:** Determina se le categorie che attualmente non hanno prodotti assegnati vengono comunque mostrate nel blocco.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (Sì):* Le categorie vuote appariranno comunque.
    - *Quando disabilitato (No):* Le categorie vuote verranno nascoste dal blocco.
  - **Valore consigliato:** "No" per evitare vicoli ciechi per i clienti e mantenere pulita la tua navigazione. Abilita "Sì" solo se hai un motivo specifico per mostrare categorie in arrivo.
  - **Scenario / esempio per il commerciante:** Se stai sviluppando una nuova linea di prodotti e hai creato categorie ma non hai ancora aggiunto prodotti, potresti temporaneamente abilitare "Sì" per i test interni, ma generalmente "No" per i negozi live.
- **Ordina per:**

  - **Cosa fa questa impostazione:** Definisce l'ordine di ordinamento delle categorie all'interno del blocco.
  - **Effetto della modifica di questa impostazione:** Modifica la sequenza in cui le categorie sono elencate.
  - **Valore consigliato:** "Posizione" (ordine predefinito di PrestaShop) o "Nome" (alfabetico).
  - **Scenario / esempio per il commerciante:** Se vuoi che le tue categorie appaiano in ordine alfabetico, seleziona "Nome". Se preferisci ordinarle manualmente nella sezione Categorie di PrestaShop, seleziona "Posizione".
- **Direzione ordine:**

  - **Cosa fa questa impostazione:** Specifica l'ordine crescente o decrescente per l'impostazione "Ordina per".
  - **Effetto della modifica di questa impostazione:**
    - *ASC:* Crescente (A-Z, 1-9).
    - *DESC:* Decrescente (Z-A, 9-1).
  - **Valore consigliato:** "ASC" per la maggior parte dei casi.
  - **Scenario / esempio per il commerciante:** Se hai ordinato per "Nome" e vuoi A-Z, seleziona "ASC".

#### **Gestione dei blocchi esistenti**

Dopo aver creato i blocchi, vedrai un elenco con le opzioni per:

- **Modifica:** Modifica le impostazioni di un blocco esistente.
- **Elimina:** Rimuovi un blocco dal tuo negozio.
- **Attiva/Disattiva stato:** Attiva o disattiva rapidamente un blocco senza eliminare la sua configurazione.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | **Nome blocco** | Descrittivo | Identificatore interno per il blocco. |
| | **Visualizza titolo blocco** | Sì | Mostra/nasconde il titolo del blocco ai clienti. |
| | **Titolo blocco** | "Categorie" (esempio) | Il titolo visibile per il blocco (multilingua). |
| | **Hook per visualizzare il blocco** | `displayLeftColumn` | Determina dove appare il blocco nel tuo tema. |
| | **Categoria radice** | Home | Imposta il punto di partenza per le categorie in questo blocco. |
| | **Profondità massima** | 0 (Tutte) | Limita il numero di livelli di sottocategorie visualizzati. |
| | **Dinamico (apri l'albero delle categorie corrente)** | Sì | Espande automaticamente l'albero alla categoria corrente. |
| | **Visualizza Categoria radice** | Sì | Mostra/nasconde la Categoria radice selezionata. |
| | **Visualizza numero di prodotti** | No | Mostra/nasconde il conteggio dei prodotti accanto ai nomi delle categorie. |
| | **Visualizza categorie senza prodotti** | No | Mostra/nasconde le categorie che non hanno prodotti. |
| | **Ordina per** | Posizione | Ordina le categorie per posizione o nome. |
| | **Direzione ordine** | ASC | Ordina le categorie in ordine crescente o decrescente. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Il mio nuovo blocco di categorie non viene visualizzato nel front office.**
R1:

- **Controlla l'Hook:** Assicurati di aver selezionato l'hook corretto "Hook per visualizzare il blocco" nella configurazione del modulo.
- **Posizione del modulo:** Vai su **Design > Posizioni** (o **Moduli > Posizioni** nelle versioni precedenti). Cerca `Blocchi Categorie Multiple` e assicurati che sia agganciato alla posizione selezionata e non sia disabilitato. Potrebbe essere necessario spostare la sua posizione su o giù se altri moduli si sovrappongono.
- **Stato del modulo:** Nella configurazione del modulo, assicurati che il blocco sia "Abilitato" (segno di spunta verde).
- **Cache:** Svuota la cache di PrestaShop (**Parametri avanzati > Prestazioni > Svuota cache**).

**D2: Le categorie nel mio blocco non si espandono o non vengono visualizzate correttamente.**
R2:

- **Categoria radice e profondità massima:** Ricontrolla le impostazioni di "Categoria radice" e "Profondità massima". Se la profondità massima è troppo bassa, le sottocategorie non appariranno. Se la Categoria radice non è corretta, vedrai l'albero sbagliato.
- **Opzione dinamica:** Se ti aspetti che l'albero si espanda automaticamente durante la navigazione, assicurati che "Dinamico (apri l'albero delle categorie corrente)" sia impostato su "Sì".
- **Categorie senza prodotti:** Se mancano delle categorie, controlla "Visualizza categorie senza prodotti". Se è "No", le categorie senza prodotti saranno nascoste.

**D3: Lo stile del blocco di categorie non corrisponde al mio tema.**
R3:

- Il modulo cerca di ereditare gli stili dal tuo tema PrestaShop attivo. Tuttavia, i temi personalizzati potrebbero richiedere piccole modifiche CSS.
- Spesso puoi sovrascrivere il CSS predefinito del modulo aggiungendo regole al file `custom.css` o `theme.css` del tuo tema. (Vedi Sezione 7.5 per i dettagli dello sviluppatore sul CSS del modulo).
- Per PrestaShop 1.7/8/9, assicurati di utilizzare il file `multicatblock-prestashop17.css` se il tuo tema lo richiede (questo viene gestito automaticamente dal modulo).

**D4: Come posso tradurre il titolo del blocco in altre lingue?**
R4:

- Quando modifichi un blocco, il campo "Titolo blocco" avrà delle bandiere linguistiche accanto. Fai clic su ogni bandiera per inserire il titolo per quella lingua specifica.
- Salva le modifiche dopo aver inserito tutte le traduzioni.

**D5: Perché alcune categorie mancano dal blocco, anche se hanno prodotti?**
R5:

- **Ambito della Categoria radice:** Assicurati che le categorie mancanti siano effettivamente discendenti (sottocategorie) della "Categoria radice" che hai selezionato per quel blocco specifico. Se sono al di fuori di quel ramo, non appariranno.
- **Stato della categoria:** Controlla in **Catalogo > Categorie** che le categorie mancanti siano "Abilitate" e "Visualizzate" (visibili).
- **Associazione prodotti:** Ricontrolla che i prodotti siano correttamente associati alle categorie in questione.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo Blocchi Categorie Multiple (`multicatblocks`) segue un'architettura standard per i moduli PrestaShop, sfruttando principalmente la classe `Module` per la sua funzionalità principale e configurazione. Si integra nel front-office tramite vari hook di visualizzazione e utilizza i template Smarty per il rendering. Il modulo memorizza le sue impostazioni di configurazione nella tabella `ps_configuration`, consentendo di definire più blocchi di categorie distinti. Utilizza una logica di rendering ad albero personalizzata per costruire la navigazione delle categorie.

### 4.2 Controller (`controllers/`)

Questo modulo non utilizza controller dedicati per il front-office o il back-office. Tutta la logica di configurazione e rendering del front-office è gestita all'interno del file principale del modulo `index.php` e dei suoi template e hook associati.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non definisce classi `ObjectModel` personalizzate. Tutta la manipolazione dei dati per le categorie si basa sulla classe `Category` nativa di PrestaShop.

La logica principale risiede in `multicatblocks/index.php`:

- **Classe `Multicatblocks`:** Estende `Module`.
  - **`__construct()`:** Inizializza i dettagli del modulo, imposta le schede e registra gli hook.
  - **`install()`:** Registra gli hook necessari (`displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayHome`, `displayProductButtons` - anche se quest'ultimo potrebbe essere per uso legacy/interno in quanto non esposto nella configurazione), crea le voci di configurazione predefinite.
  - **`uninstall()`:** Pulisce le voci di configurazione.
  - **`getContent()`:** Gestisce l'invio e la visualizzazione del modulo di configurazione del Back Office. Gestisce la creazione, la modifica e l'eliminazione dei blocchi di categorie, memorizzando le loro impostazioni in `Configuration::updateValue()`.
  - **`hookDisplayHeader()`:** Inietta risorse CSS e JavaScript nella sezione `<head>` del front office.
  - **`hookDisplayLeftColumn()`, `hookDisplayRightColumn()`, `hookDisplayFooter()`, `hookDisplayHome()`, `hookDisplayProductButtons()`:** Questi metodi sono responsabili del recupero dei blocchi configurati per i rispettivi hook, del recupero dei dati delle categorie, della preparazione delle variabili Smarty e del rendering del template `multicatblock.tpl` o `multicatblock-footer.tpl`.
  - **`getCategoryTree()`:** Un metodo interno cruciale che recupera e struttura ricorsivamente i dati delle categorie in base alla configurazione del blocco (categoria radice, profondità massima, conteggio prodotti, ecc.).

### 4.4 Risorse JavaScript (`views/js/`)

- **`multicatblocks/js/script.js`**:

  - **Ambito:** Front-office.
  - **Scopo:** Gestisce il comportamento interattivo principale dell'albero delle categorie, come l'espansione/compressione delle sottocategorie. Probabilmente lega gli eventi di clic ai link delle categorie o alle icone di espansione/compressione.
  - **Dettagli:** Questo script è responsabile del comportamento "dinamico", garantendo che quando si fa clic su una categoria, le sue sottocategorie vengano rivelate o nascoste, e potenzialmente evidenziando il percorso della categoria attiva.
- **`multicatblocks/js/tree.js`**:

  - **Ambito:** Front-office.
  - **Scopo:** Probabilmente una dipendenza o una versione precedente della funzionalità dell'albero, o gestisce specificamente lo stato iniziale e il rendering della struttura dell'albero.
  - **Dettagli:** Potrebbe contenere la logica per l'inizializzazione dell'albero, la gestione delle chiamate AJAX per i dati delle categorie (se applicabile, anche se il modulo sembra renderizzare l'intero albero al caricamento della pagina), o la gestione dello stato dell'albero.
- **`multicatblocks/lib/searchTool/views/js/autocomplete.js`**:

  - **Ambito:** Back-office (configurazione amministrativa).
  - **Scopo:** Fornisce una funzionalità di completamento automatico per la selezione delle categorie nel modulo di configurazione del modulo, in particolare per l'impostazione "Categoria radice".
  - **Dettagli:** Si lega a un campo di input, effettua richieste AJAX a un controller amministrativo di PrestaShop (probabilmente `AdminCategories` o uno personalizzato se presente, anche se nessuno è elencato) per cercare categorie e visualizza suggerimenti.

### 4.5 Fogli di stile CSS (`views/css/`)

- **`multicatblocks/css.css`**:

  - **Ambito:** Front-office.
  - **Scopo:** Stile generale per i blocchi di categorie.
  - **Dettagli:** Contiene regole di base per gli elementi di elenco, i link e potenzialmente le icone di espansione/compressione. I selettori chiave potrebbero includere `.multicatblock`, `.multicatblock_list`, `.multicatblock_item`.
- **`multicatblocks/lib/searchTool/views/css/autocomplete.css`**:

  - **Ambito:** Back-office (configurazione amministrativa).
  - **Scopo:** Stili per l'input di ricerca con completamento automatico e il suo menu a discesa di suggerimenti.
  - **Dettagli:** Assicura che lo strumento di ricerca delle categorie nel pannello di amministrazione sia visivamente coerente e facile da usare.
- **`multicatblocks/multicatblock-prestashop17.css`**:

  - **Ambito:** Front-office.
  - **Scopo:** Sovrascritture specifiche o stili aggiuntivi personalizzati per i temi di PrestaShop 1.7.x, 8.x e 9.x (es. tema Classic).
  - **Dettagli:** Affronta potenziali incoerenze di layout o stile che potrebbero sorgere tra le versioni precedenti di PrestaShop e le nuove strutture dei temi. Questo viene caricato condizionalmente in base alla versione di PS.
- **`multicatblocks/multicatblock.css`**:

  - **Ambito:** Front-office.
  - **Scopo:** Stile principale per i blocchi di categorie, probabilmente per le versioni precedenti di PrestaShop (1.5.x, 1.6.x) o come fallback.
  - **Dettagli:** Simile a `css.css`, ma potrebbe contenere regole più specifiche per le strutture dei temi più vecchi.
- **`multicatblocks/views/css/mcb-admin.css`**:

  - **Ambito:** Back-office (configurazione amministrativa).
  - **Scopo:** Stile per la pagina di configurazione del modulo nel Back Office di PrestaShop.
  - **Dettagli:** Assicura che il modulo di impostazioni del modulo, l'elenco dei blocchi e altri elementi dell'interfaccia utente amministrativa siano ben presentati e coerenti con il tema amministrativo di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template degli hook (`views/templates/hook/` - anche se i file sono direttamente in `multicatblocks/`):**

  - **`multicatblocks/multicatblock.tpl`**:
    - **Agganciato in:** `displayLeftColumn`, `displayRightColumn`, `displayHome`, `displayProductButtons`.
    - **Output:** La struttura principale del blocco di categorie, inclusi il titolo (se abilitato) e l'albero di categorie ricorsivo generato da `category-tree-branch.tpl`.
  - **`multicatblocks/multicatblock-footer.tpl`**:
    - **Agganciato in:** `displayFooter`.
    - **Output:** Una variazione del blocco di categorie specificamente per il piè di pagina, potenzialmente con stili o elementi strutturali diversi. Utilizza anche `category-tree-branch-footer.tpl`.
  - **`multicatblocks/category-tree-branch.tpl`**:
    - **Agganciato in:** Incluso da `multicatblock.tpl`.
    - **Output:** Renderizza ricorsivamente un singolo ramo dell'albero delle categorie. Itera attraverso le sottocategorie, gestisce i limiti di profondità e visualizza i conteggi dei prodotti.
  - **`multicatblocks/category-tree-branch-footer.tpl`**:
    - **Agganciato in:** Incluso da `multicatblock-footer.tpl`.
    - **Output:** Simile a `category-tree-branch.tpl` ma personalizzato per la struttura del blocco del piè di pagina.
- **Template di amministrazione (`views/templates/admin/` - anche se `shell.tpl` è in `multicatblocks/views/templates/admin/`):**

  - **`multicatblocks/views/templates/admin/shell.tpl`**:
    - **Scopo:** Il template principale per la pagina di configurazione del modulo nel Back Office.
    - **Output:** Il modulo per aggiungere/modificare blocchi, l'elenco dei blocchi esistenti e potenzialmente include altri elementi specifici dell'amministrazione.
- **Template di libreria:**

  - **`multicatblocks/lib/searchTool/views/scripts.tpl`**:
    - **Scopo:** Probabilmente include JavaScript necessario per lo strumento di ricerca con completamento automatico utilizzato nella configurazione amministrativa.
    - **Output:** Tag `<script>` o JavaScript inline per la funzionalità di completamento automatico.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Il modulo non crea tabelle SQL personalizzate.
  - Tutta la configurazione per ogni blocco di categorie è memorizzata nella tabella `ps_configuration`. Le impostazioni di ogni blocco sono serializzate e memorizzate sotto una chiave di configurazione univoca (es. `MULTICATBLOCKS_BLOCKS`).
- **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Inietta i file CSS e JavaScript del modulo. |
| `displayLeftColumn` | Nella barra laterale sinistra del front office. | Renderizza un blocco di categorie configurato nella colonna sinistra. |
| `displayRightColumn` | Nella barra laterale destra del front office. | Renderizza un blocco di categorie configurato nella colonna destra. |
| `displayFooter` | Nella sezione del piè di pagina del front office. | Renderizza un blocco di categorie configurato nel piè di pagina. |
| `displayHome` | Sulla homepage (se il tema supporta l'hook `displayHome`). | Renderizza un blocco di categorie configurato sulla homepage. |
| `displayProductButtons` | Sulla pagina del prodotto, vicino al pulsante "aggiungi al carrello". | Renderizza un blocco di categorie configurato sulle pagine dei prodotti (meno comune per questo modulo, ma disponibile). |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Blocchi Categorie Multiple", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema tecnico o domanda tu possa avere.
