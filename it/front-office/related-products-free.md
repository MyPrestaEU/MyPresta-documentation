---
title: "Prodotti Correlati Free - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Prodotti Correlati Free di MyPresta.eu."
sidebar:
  label: "Prodotti Correlati Free - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Related Products Free su MyPresta.eu](https://mypresta.eu/modules/front-office-features/related-products-free.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/related-products-free/)
>
> ---


# Prodotti Correlati Free

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL), che sono tipicamente disponibili sulla maggior parte degli ambienti di hosting compatibili con PrestaShop.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Prodotti Correlati Free)

Questa è la schermata di configurazione principale e unica per il modulo “Prodotti Correlati Free”. Qui definirai come si comporta il blocco dei prodotti correlati e quali prodotti visualizza.

#### **Visualizza prodotti correlati dalla categoria**

-   **Cosa fa questa impostazione:** Questa impostazione cruciale determina *quali* prodotti verranno mostrati come “correlati”. Invece di selezionare manualmente i prodotti per ogni articolo, questo modulo semplifica le cose permettendoti di selezionare una categoria specifica. Tutti i prodotti appartenenti a questa categoria scelta verranno quindi visualizzati come prodotti correlati su *ogni* pagina prodotto del tuo negozio.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando una categoria è selezionata (es. “Accessori”):* Su ogni pagina prodotto del tuo negozio, apparirà un blocco che mostra i prodotti appartenenti alla categoria “Accessori”.
    -   *Quando “Nessuno” o nessuna categoria è selezionata:* Il modulo non visualizzerà alcun prodotto correlato, poiché non sa quali prodotti mostrare.
-   **Valore consigliato:** Scegli una categoria che contenga articoli generici, complementari o più venduti che potrebbero essere rilevanti per un'ampia gamma dei tuoi prodotti principali. Ad esempio, se vendi abbigliamento, “Accessori” o “Articoli in saldo” potrebbero essere buone scelte.
-   **Scenario / esempio per il commerciante:** Vendi vari tipi di elettronica. Crei una categoria chiamata “Accessori Gadget Indispensabili” e vi aggiungi articoli come caricabatterie universali, protezioni per lo schermo e cuffie. Selezionando questa categoria qui, ogni pagina prodotto (ad esempio, per uno smartphone, un laptop o un tablet) mostrerà questi “Accessori Gadget Indispensabili” come prodotti correlati, incoraggiando le vendite incrociate.

#### **Numero di prodotti da visualizzare**

-   **Cosa fa questa impostazione:** Controlla quanti prodotti correlati verranno mostrati nel blocco sulle pagine dei tuoi prodotti.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su '4':* Il modulo visualizzerà quattro prodotti dalla categoria scelta.
    -   *Quando impostato su '8':* Il modulo visualizzerà otto prodotti.
-   **Valore consigliato:** 4 o 5. Troppi prodotti possono sopraffare il cliente o rendere la pagina disordinata, specialmente su mobile. Una selezione più piccola e curata è spesso più efficace.
-   **Scenario / esempio per il commerciante:** Vuoi mostrare una selezione concisa di articoli correlati senza rendere la pagina del prodotto troppo lunga. Impostando questo valore su '4' si garantisce un layout pulito, offrendo comunque buone opportunità di cross-selling.

#### **Visualizza prodotti solo dalla categoria selezionata**

-   **Cosa fa questa impostazione:** Questa impostazione determina se i prodotti correlati mostrati provengono *solo* dalla categoria selezionata sopra, o se possono includere anche prodotti dalla *categoria del prodotto corrente*.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Verranno mostrati solo i prodotti della categoria scelta in “Visualizza prodotti correlati dalla categoria”.
    -   *Quando disabilitato (NO):* Il modulo mostrerà i prodotti della categoria selezionata *e* potenzialmente i prodotti della categoria del prodotto che il cliente sta attualmente visualizzando. Questo può portare a suggerimenti più pertinenti se la categoria del prodotto corrente contiene anche buoni articoli per il cross-selling.
-   **Valore consigliato:** “SÌ” se la categoria “prodotti correlati” scelta è molto generica (come “Accessori”). “NO” se vuoi mescolare articoli correlati più specifici dalla categoria del prodotto corrente. Prova entrambi per vedere cosa funziona meglio per il tuo negozio.
-   **Scenario / esempio per il commerciante:** Hai selezionato “Accessori” come categoria correlata. Se imposti questo su “SÌ”, verranno mostrati solo gli accessori. Se lo imposti su “NO”, e un cliente sta visualizzando una “T-shirt” (che si trova nella categoria “Magliette”), il modulo potrebbe mostrare sia “Accessori” che altre “Magliette” come correlati.

#### **Hook per visualizzare i prodotti correlati**

-   **Cosa fa questa impostazione:** Qui decidi *dove* sulla pagina del prodotto apparirà il blocco dei prodotti correlati. PrestaShop utilizza gli “hook” come punti specifici nel codice della pagina dove i moduli possono inserire il loro contenuto.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su `displayFooterProduct` (Consigliato):* Il blocco dei prodotti correlati apparirà in fondo alla sezione delle informazioni sul prodotto, di solito sopra il piè di pagina dell'intera pagina. Questo è un posizionamento comune ed efficace.
    -   *Quando impostato su `displayProductExtraContent` (PrestaShop 1.7+):* Il blocco potrebbe apparire all'interno di una scheda o di una sezione specifica dell'area del contenuto principale della pagina del prodotto, a seconda del tuo tema.
    -   *Altri hook (es. `displayLeftColumnProduct`, `displayRightColumnProduct`):* Il blocco apparirà nella barra laterale sinistra o destra della pagina del prodotto, se il tuo tema supporta le barre laterali sulle pagine del prodotto.
-   **Valore consigliato:** `displayFooterProduct`. Questo hook è ampiamente supportato dai temi e fornisce un posizionamento chiaro e discreto per gli articoli correlati. Sperimenta con altri se hai un design specifico in mente.
-   **Scenario / esempio per il commerciante:** Vuoi che i prodotti correlati siano visibili ma non interferiscano con la descrizione principale del prodotto e il pulsante “Aggiungi al carrello”. Scegliere `displayFooterProduct` lo posiziona ordinatamente sotto il contenuto principale, consentendo ai clienti di scorrere verso il basso e scoprire di più.

#### **Visualizza prodotti in carosello**

-   **Cosa fa questa impostazione:** Determina se i prodotti correlati vengono mostrati in una griglia statica (tutti visibili contemporaneamente) o in un carosello dinamico e scorrevole (dove i clienti possono cliccare sulle frecce o scorrere per vederne altri).
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* I prodotti correlati appariranno in formato carosello, permettendoti di visualizzare più prodotti in uno spazio compatto.
    -   *Quando disabilitato (NO):* I prodotti verranno visualizzati in una griglia statica, mostrando tutti i prodotti selezionati contemporaneamente (fino al limite di “Numero di prodotti da visualizzare”).
-   **Valore consigliato:** “SÌ” se vuoi risparmiare spazio o visualizzare più prodotti di quanti possano stare comodamente in una singola riga. “NO” se preferisci che tutti i prodotti siano immediatamente visibili senza interazione.
-   **Scenario / esempio per il commerciante:** Vuoi mostrare 8 prodotti correlati, ma visualizzarli tutti in una griglia rende la pagina troppo lunga. Abilitando il carosello puoi mostrare 8 prodotti occupando lo spazio di 4, con i clienti che scorrono per vedere il resto.

#### **Visualizza prodotti in ordine casuale**

-   **Cosa fa questa impostazione:** Controlla l'ordine in cui vengono visualizzati i prodotti correlati dalla categoria scelta.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (SÌ):* Ogni volta che un cliente visita una pagina prodotto, i prodotti correlati appariranno in un ordine diverso e casuale.
    -   *Quando disabilitato (NO):* I prodotti appariranno in un ordine coerente, solitamente basato sul loro ID o sulla posizione all'interno della categoria selezionata.
-   **Valore consigliato:** “SÌ”. La randomizzazione dell'ordine assicura che tutti i prodotti della categoria scelta abbiano la possibilità di essere visti nel tempo, evitando che gli stessi pochi prodotti siano sempre in cima.
-   **Scenario / esempio per il commerciante:** Hai 20 prodotti nella tua categoria “Accessori”, ma ne visualizzi solo 5. Se l'ordine è sempre lo stesso, solo i primi 5 verranno mai visti. Abilitando l'ordine casuale, appariranno accessori diversi ogni volta, aumentando l'esposizione per tutti.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Visualizza prodotti correlati dalla categoria | Seleziona una categoria pertinente | Definisce la categoria di origine per i prodotti correlati. |
| Configurazione Modulo | Numero di prodotti da visualizzare | 4-5 | Controlla quanti prodotti correlati vengono mostrati. |
| Configurazione Modulo | Visualizza prodotti solo dalla categoria selezionata | SÌ / NO (Testa entrambi) | Determina se vengono mostrati solo i prodotti della categoria selezionata, o se anche la categoria del prodotto corrente può contribuire. |
| Configurazione Modulo | Hook per visualizzare i prodotti correlati | `displayFooterProduct` | Specifica la posizione del blocco dei prodotti correlati sulla pagina del prodotto. |
| Configurazione Modulo | Visualizza prodotti in carosello | SÌ | Mostra i prodotti correlati in un carosello scorrevole per una visualizzazione compatta. |
| Configurazione Modulo | Visualizza prodotti in ordine casuale | SÌ | Randomizza l'ordine dei prodotti correlati visualizzati per un'esposizione variata. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho configurato il modulo, ma non vedo alcun prodotto correlato sulle mie pagine prodotto.**
R:

1.  **Verifica la selezione della categoria:** Assicurati di aver selezionato una categoria valida nell'impostazione “Visualizza prodotti correlati dalla categoria” e che questa categoria contenga effettivamente prodotti.
2.  **Verifica lo stato del prodotto:** Assicurati che i prodotti all'interno della categoria selezionata siano attivi, in stock e visibili nel tuo negozio.
3.  **Svuota la cache:** Vai su **Parametri Avanzati > Prestazioni** nel tuo Back Office di PrestaShop e clicca su “Svuota la cache” (o “Svuota la cache di Smarty”). A volte, PrestaShop ha bisogno di un aggiornamento della cache per visualizzare il nuovo contenuto del modulo.
4.  **Compatibilità del tema:** Sebbene il modulo utilizzi gli hook standard di PrestaShop, alcuni temi altamente personalizzati potrebbero avere override specifici. Prova a passare temporaneamente al tema predefinito di PrestaShop per vedere se il blocco appare. Se lo fa, il tuo tema potrebbe richiedere piccole modifiche.

**D: Il blocco dei prodotti correlati appare strano o non stilizzato sul mio sito.**
R: Questo è solitamente un conflitto CSS (di stile) con il tuo tema.

1.  **Svuota la cache:** Inizia sempre svuotando la cache di PrestaShop.
2.  **Override del tema:** Il tuo tema potrebbe avere un proprio stile per gli elenchi di prodotti o i caroselli che entrano in conflitto. Potrebbe essere necessario un web developer per ispezionare il CSS e applicare stili personalizzati per farlo adattare al design del tuo tema. Il modulo fornisce uno stile di base, ma gli stili del tuo tema spesso hanno la precedenza.

**D: Posso avere prodotti correlati diversi per prodotti principali diversi?**
R: Il modulo “Prodotti Correlati Free” è progettato per la semplicità, visualizzando prodotti da una *singola categoria scelta* su tutte le pagine prodotto. Per assegnazioni di prodotti correlati più avanzate e specifiche per prodotto, avresti bisogno di un modulo più completo (a pagamento).

**D: Il carosello non funziona o non viene visualizzato correttamente.**
R:

1.  **Verifica i conflitti JavaScript:** Un altro modulo o il tuo tema potrebbero avere JavaScript in conflitto che impedisce l'inizializzazione del carosello. Controlla la console per sviluppatori del tuo browser per errori JavaScript.
2.  **Svuota la cache:** Ancora una volta, svuota la cache di PrestaShop.
3.  **Disabilita e riabilita:** Prova a disabilitare l'impostazione “Visualizza prodotti in carosello”, salva, quindi riabilitala e salva di nuovo.

**D: Come traduco il titolo del modulo (es. “Prodotti Correlati”) in altre lingue?**
R:

1.  Vai su **Internazionale > Traduzioni** nel tuo Back Office di PrestaShop.
2.  Seleziona “Traduzioni dei moduli installati” per il “Tipo di traduzione”.
3.  Scegli il tuo tema (o “Core” se il tuo tema non è elencato).
4.  Seleziona la lingua che desideri tradurre.
5.  Trova il modulo “relatedfree” nell'elenco e traduci le stringhe pertinenti.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica per sviluppatori e webmaster che lavorano con il modulo “Prodotti Correlati Free”.

### 4.1 Panoramica dell'architettura

Il modulo “Prodotti Correlati Free” è un modulo PrestaShop semplice che segue un modello di tipo MVC di base all'interno dell'ambito del modulo. Utilizza principalmente il metodo `getContent()` della classe `Module` per la configurazione del Back Office e registra un singolo hook (`displayFooterProduct` per impostazione predefinita, ma configurabile) per iniettare il suo template front-office. Non introduce controller personalizzati, ObjectModels o asset JavaScript/CSS complessi oltre la sua funzionalità principale.

### 4.2 Controller (`controllers/`)

-   Questo modulo **non** contiene alcun controller Front-Office o Back-Office personalizzato. Tutta la configurazione è gestita all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

-   Questo modulo **non** contiene classi o ObjectModels personalizzati nella directory `classes/`. Tutta la logica è incapsulata all'interno della classe principale `RelatedFree` (definita in `index.php`).

### 4.4 Asset JavaScript (`views/js/`)

-   Questo modulo **non** contiene alcun file JavaScript personalizzato. Se l'opzione carosello è abilitata, si basa sulle librerie JavaScript principali di PrestaShop (ad esempio, Owl Carousel se disponibile nel tema, o una semplice implementazione personalizzata all'interno del TPL in caso contrario).

### 4.5 Fogli di stile CSS (`views/css/`)

-   Questo modulo **non** contiene alcun file CSS personalizzato. Lo stile è previsto che sia gestito dal tema o si basa su stili/strutture inline di base che i temi tipicamente stilizzano. Gli sviluppatori dovrebbero applicare CSS personalizzati per adattarsi all'estetica del loro tema.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template amministrativi (`views/templates/admin/`)**:

    -   `views/templates/admin/tabs.tpl`: Questo template viene utilizzato per renderizzare il modulo di configurazione del modulo nel Back Office. Definisce la struttura delle impostazioni, inclusi i campi di input per la selezione della categoria, il numero di prodotti, la selezione dell'hook e gli interruttori per il carosello e l'ordine casuale. Viene renderizzato da `getContent()` in `index.php`.
-   **Template hook (`views/templates/hook/`)**:

    -   `views/templates/hook/productFooter.tpl`: Questo è il template front-office principale. Viene renderizzato quando il modulo è agganciato (ad esempio, `displayFooterProduct`). Questo template contiene la struttura HTML per il blocco dei prodotti correlati, incluso il titolo, e itera sulla variabile `$products` (passata dal modulo) per visualizzare l'immagine, il nome e il prezzo di ogni prodotto correlato. Contiene anche la logica per il rendering di un carosello se l'opzione di configurazione corrispondente è abilitata.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    Il modulo non crea tabelle di database personalizzate. Tutte le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` utilizzando chiavi di configurazione standard di PrestaShop.

    -   `PS_RELATEDFREE_CATEGORY`: Memorizza l'ID della categoria selezionata per i prodotti correlati.
    -   `PS_RELATEDFREE_NUMBER`: Memorizza il numero di prodotti da visualizzare.
    -   `PS_RELATEDFREE_ONLY_SELECTED`: Memorizza un booleano (0/1) per visualizzare solo i prodotti della categoria selezionata.
    -   `PS_RELATEDFREE_HOOK`: Memorizza il nome dell'hook in cui viene visualizzato il modulo.
    -   `PS_RELATEDFREE_CAROUSEL`: Memorizza un booleano (0/1) per abilitare il carosello.
    -   `PS_RELATEDFREE_RANDOM`: Memorizza un booleano (0/1) per visualizzare i prodotti in ordine casuale.
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Utilizzato per registrare gli asset (anche se questo modulo non lo usa per gli asset). |
| `displayLeftColumn` | Nella barra laterale sinistra delle pagine che ne hanno una. | Posizionamento alternativo per il blocco dei prodotti correlati. |
| `displayRightColumn` | Nella barra laterale destra delle pagine che ne hanno una. | Posizionamento alternativo per il blocco dei prodotti correlati. |
| `displayFooter` | In fondo a ogni pagina, prima del tag di chiusura `</body>`. | Posizionamento alternativo per il blocco dei prodotti correlati. |
| `displayProductExtraContent` | All'interno dell'area del contenuto principale del prodotto, spesso in schede (PrestaShop 1.7+). | Posizionamento alternativo per il blocco dei prodotti correlati. |
| `displayFooterProduct` | In fondo alla sezione delle informazioni sul prodotto nelle pagine prodotto. | **Hook principale utilizzato dal modulo** per la visualizzazione dei prodotti correlati. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo “Prodotti Correlati Free”, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda relativa alla funzionalità del modulo.
