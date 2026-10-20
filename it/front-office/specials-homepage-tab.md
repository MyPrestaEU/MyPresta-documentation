---
title: "Scheda Offerte Speciali Homepage - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Scheda Offerte Speciali Homepage di MyPresta.eu."
sidebar:
  label: "Scheda Offerte Speciali Homepage - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Specials Homepage Tab su MyPresta.eu](https://mypresta.eu/modules/front-office-features/specials-homepage-tab.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/specials-homepage-tab/)
>
> ---


# Scheda Offerte Speciali Homepage

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per un'installazione PrestaShop e sono sufficienti per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo "Scheda Offerte Speciali Homepage" per accedere alle sue impostazioni.

#### Impostazioni e Opzioni:

-   **Numero di prodotti**

    -   **Cosa fa questa impostazione:** Controlla quanti prodotti in offerta speciale verranno visualizzati all'interno della scheda "Offerte Speciali" sulla tua homepage.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se impostato su un numero più alto (es. 12):* Più prodotti saranno visibili nella scheda, offrendo ai clienti una selezione più ampia di offerte. Questo potrebbe richiedere più scorrimento o paginazione a seconda del tuo tema.
        -   *Se impostato su un numero più basso (es. 4):* Verranno mostrati meno prodotti, creando una visualizzazione più concisa. Questo può essere utile se vuoi evidenziare solo le tue migliori offerte o mantenere la homepage pulita.
    -   **Valore consigliato:** Inizia con un numero che si adatti bene al design del tuo tema (es. 8 o 12) e regola in base a quante offerte speciali hai tipicamente e quanto spazio vuoi che occupino.
    -   **Scenario / esempio per il commerciante:** Se hai molti prodotti in saldo e vuoi mostrare varietà, impostalo su 12. Se preferisci una homepage minimalista e vuoi evidenziare solo alcune offerte speciali, impostalo su 4.
-   **Prodotti casuali**

    -   **Cosa fa questa impostazione:** Determina se i prodotti in offerta speciale visualizzati nella scheda sono mostrati in un ordine fisso (es. per ID, data di aggiunta) o in un ordine casuale ogni volta che la pagina viene caricata.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se abilitato (SÌ):* Ogni volta che un cliente visita la tua homepage, l'ordine dei prodotti nella scheda "Offerte Speciali" sarà casuale. Questo assicura che prodotti diversi ottengano visibilità e impedisce che gli stessi pochi articoli siano sempre in cima.
        -   *Se disabilitato (NO):* I prodotti verranno visualizzati in un ordine coerente e non casuale (tipicamente per ID prodotto o data di creazione, a seconda dell'ordinamento predefinito di PrestaShop per le offerte speciali). Ciò significa che gli stessi prodotti appariranno sempre per primi.
    -   **Valore consigliato:** **SÌ**. La randomizzazione dei prodotti è generalmente consigliata per dare a tutte le tue offerte speciali una giusta possibilità di essere viste e per mantenere la homepage fresca per i clienti che ritornano.
    -   **Scenario / esempio per il commerciante:** Se hai 20 prodotti in saldo ma ne visualizzi solo 8, abilitare "Prodotti casuali" assicura che, nel tempo, tutti i 20 prodotti appariranno eventualmente nella scheda, piuttosto che solo i primi 8.

#### Altre chiavi di configurazione (Impostazioni interne di PrestaShop):

Il modulo interagisce anche con diverse chiavi di configurazione principali di PrestaShop. Sebbene queste non siano direttamente configurabili all'interno del modulo stesso, comprenderne lo scopo aiuta nella risoluzione dei problemi o nella personalizzazione avanzata:

-   `PS_CATALOG_MODE`: Se il tuo negozio è in modalità catalogo (senza prezzi, senza aggiunta al carrello), i prezzi speciali non saranno rilevanti.
-   `PS_LANG_DEFAULT`: La lingua predefinita del tuo negozio, utilizzata per recuperare nomi e descrizioni dei prodotti.
-   `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Determina se i dipendenti possono cambiare la lingua dei moduli nel back office.
-   `PS_TAX_ADDRESS_TYPE`: Come vengono calcolate le tasse (es. in base all'indirizzo di consegna o di fatturazione).
-   `PS_COUNTRY_DEFAULT`: Il paese predefinito per il tuo negozio, che influisce sul calcolo delle tasse e delle spedizioni.
-   `PS_NB_DAYS_NEW_PRODUCT`: Il numero di giorni in cui un prodotto è considerato "nuovo". (Non direttamente correlato alle offerte speciali, ma spesso presente nei moduli che elencano i prodotti).

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Numero di prodotti | 8-12 (Regola in base al tema) | Imposta quanti prodotti in offerta speciale vengono mostrati nella scheda. |
| Configurazione modulo | Prodotti casuali | SÌ | Randomizza l'ordine dei prodotti nella scheda per una visualizzazione fresca. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: La mia scheda "Offerte Speciali" è vuota o non mostra alcun prodotto, ma ho prodotti in saldo.**

-   **R:** Innanzitutto, assicurati che i tuoi prodotti siano correttamente contrassegnati come "in saldo" nelle impostazioni del prodotto nel back office di PrestaShop (sotto la scheda "Prezzi", assicurati che i "Prezzi specifici" siano configurati e attivi). Inoltre, controlla l'impostazione "Numero di prodotti" nella configurazione del modulo; se è impostata su 0, nessun prodotto verrà visualizzato. Infine, svuota la cache di PrestaShop (**Parametri Avanzati > Prestazioni > Svuota cache**).

**D2: La scheda "Offerte Speciali" non appare affatto sulla mia homepage.**

-   **R:**
    1.  **Modulo Abilitato:** Vai su **Moduli > Gestione moduli** e assicurati che il modulo "Scheda Offerte Speciali Homepage" sia abilitato.
    2.  **Hook Correttamente:** Il modulo utilizza `displayHomeTab` e `displayHomeTabContent`. Il tuo tema deve supportare questi hook affinché la scheda appaia. La maggior parte dei temi PrestaShop standard lo fa. Se stai usando un tema fortemente personalizzato, potrebbe non chiamare questi hook.
    3.  **Cache:** Svuota sempre la cache di PrestaShop (**Parametri Avanzati > Prestazioni > Svuota cache**) dopo aver installato o configurato i moduli.
    4.  **Compatibilità del Tema:** Sebbene il modulo sia progettato per essere compatibile, temi molto vecchi o altamente personalizzati potrebbero richiedere piccole modifiche. Se i problemi persistono, contatta il supporto MyPresta.eu.

**D3: I prodotti nella scheda "Offerte Speciali" non hanno un bell'aspetto o non corrispondono al design del mio tema.**

-   **R:** Il modulo utilizza lo stile esistente del tuo tema per gli elenchi di prodotti. Se i prodotti sembrano strani, di solito è un problema CSS con il tuo tema piuttosto che con il modulo stesso.
    -   **Controlla il CSS del Tema:** Ispeziona il CSS del tuo tema per gli stili degli elenchi di prodotti.
    -   **CSS Personalizzato:** Potrebbe essere necessario aggiungere CSS personalizzato al file `custom.css` del tuo tema (se disponibile) o modificare direttamente il foglio di stile del tuo tema per regolare l'aspetto.
    -   **Responsività Mobile:** Testa su diversi dispositivi. Se l'aspetto è buono su desktop ma non su mobile, è un problema di responsività con il CSS del tuo tema.

**D4: Posso cambiare il titolo della scheda "Offerte Speciali" (es. in "Offerte" o "Promozioni")?**

-   **R:** Il modulo utilizza la traduzione predefinita di PrestaShop per "Offerte Speciali". Per cambiarla, dovresti tipicamente andare su **Internazionale > Traduzioni**, selezionare "Traduzioni dei moduli installati", scegliere il tuo tema e quindi trovare il modulo "Scheda Offerte Speciali Homepage". Potrai quindi modificare la traduzione per il titolo della scheda.

**D5: Perché alcuni prodotti in saldo non vengono visualizzati nella scheda?**

-   **R:**
    1.  **Limite Numero di Prodotti:** Controlla l'impostazione "Numero di prodotti" nella configurazione del modulo. Se hai più offerte speciali di questo limite, verrà visualizzato solo il primo set (o casuale, se abilitato).
    2.  **Visibilità del Prodotto:** Assicurati che il prodotto sia attivo, visibile e abbia un prezzo specifico effettivo configurato (non solo una riduzione di prezzo regolare).
    3.  **Cache:** Svuota la cache di PrestaShop.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Scheda Offerte Speciali Homepage" (`blockspecialstab`) è un modulo PrestaShop leggero, principalmente focalizzato sulla visualizzazione front-office. Aderisce all'architettura standard dei moduli PrestaShop, sfruttando gli hook per iniettare contenuto nella homepage. Non introduce controller, modelli o JavaScript/CSS complessi personalizzati oltre a quanto necessario per la templating di base. La sua funzionalità principale ruota attorno al recupero di prodotti con prezzi specifici e alla loro visualizzazione all'interno di una struttura a schede.

### 4.2 Controller (`controllers/`)

Questo modulo **non** include alcun controller Front-Office o Back-Office Admin personalizzato. Tutta la logica è incapsulata all'interno della classe principale del modulo (`blockspecialstab.php`).

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo **non** introduce classi personalizzate o definizioni di `ObjectModel`. Si basa sulle classi `Product` e `SpecificPrice` di PrestaShop per recuperare i dati dei prodotti.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo **non** include alcun file JavaScript personalizzato. La funzionalità di cambio scheda e la visualizzazione dei prodotti sono gestite dal JavaScript esistente del tema (es. jQuery, Bootstrap JS) che tipicamente gestisce le interazioni `displayHomeTab` e `displayHomeTabContent`.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo **non** include alcun file CSS personalizzato. È progettato per ereditare lo stile del tema PrestaShop attivo per gli elenchi di prodotti, garantendo un'integrazione perfetta. Gli sviluppatori dovrebbero fare riferimento al CSS del loro tema per lo stile delle griglie di prodotti e delle schede.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo utilizza due template Smarty principali, entrambi situati nella directory `views/templates/hook/`, per renderizzare la scheda e il suo contenuto.

-   **`blockspecialstab/views/templates/hook/blockspecialstab.tpl`**

    -   **Scopo:** Questo template è responsabile del rendering dell'effettiva *intestazione* della scheda "Offerte Speciali" che appare accanto ad altre schede (es. "Nuovi Arrivi").
    -   **Hook:** Principalmente renderizzato tramite `displayHomeTab`.
    -   **Output:** Tipicamente produce un elemento `<li>` contenente un tag `<a>` con un link al contenuto della scheda (es. `#blockspecialstab`).
    -   **Elementi chiave per gli sviluppatori:**
        -   `id="home-page-tabs"`: Il contenitore per tutte le schede della homepage (solitamente nel tema).
        -   `id="blockspecialstab"`: L'ID per la scheda stessa, utilizzato per il collegamento al suo contenuto.
        -   `{l s='Specials' mod='blockspecialstab'}`: Il testo traducibile per il titolo della scheda.
-   **`blockspecialstab/views/templates/hook/blockspecialstabcontents.tpl`**

    -   **Scopo:** Questo template renderizza il *contenuto* che appare quando si clicca sulla scheda "Offerte Speciali". Contiene l'elenco effettivo dei prodotti in offerta speciale.
    -   **Hook:** Principalmente renderizzato tramite `displayHomeTabContent`.
    -   **Output:** Tipicamente produce un elemento `<div>` contenente un ciclo che itera sulla variabile `$products` (passata dal modulo) e visualizza ogni prodotto utilizzando un partial comune per l'elenco dei prodotti dal tema (es. `product-list.tpl` o uno snippet simile).
    -   **Elementi chiave per gli sviluppatori:**
        -   `id="blockspecialstab"`: L'ID per il blocco di contenuto, corrispondente all'intestazione della scheda.
        -   `{$products}`: Un array di oggetti `Product` (o array associativi che rappresentano i prodotti) passati dal modulo, contenenti dettagli come ID, nome, prezzo, immagine, ecc.
        -   `{include file='catalog/_partials/miniatures/product.tpl' product=$product}` (esempio per PS 1.7/8): Il modulo tipicamente utilizza un partial standard del tema per renderizzare ogni prodotto, garantendo uno stile coerente. Gli sviluppatori dovrebbero controllare `_partials/miniatures/product.tpl` o `product-list.tpl` del loro tema per capire come vengono renderizzati i singoli prodotti.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Questo modulo non crea tabelle SQL personalizzate.
    -   Memorizza le sue impostazioni di configurazione nella tabella `ps_configuration` utilizzando chiavi come `BLOCKSTAB_NB_CACHES` (legacy), `BLOCKSTABS_NB_CACHES` (attuale) e `BLOCKSTABS_RAND`.
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHomeTab` | Renderizza nell'area di navigazione delle schede della homepage. | Inietta l'intestazione della scheda "Offerte Speciali" (`blockspecialstab.tpl`) nell'elenco principale delle schede della homepage. |
| `displayHomeTabContent` | Renderizza nell'area del contenuto della homepage, corrispondente alla scheda. | Inietta l'elenco dei prodotti in offerta speciale (`blockspecialstabcontents.tpl`) quando la scheda "Offerte Speciali" è attiva. |
| `addproduct` | Dopo l'aggiunta di un prodotto. | Svuota la cache interna del modulo per garantire che i nuovi prodotti siano considerati per le offerte speciali. |
| `updateproduct` | Dopo l'aggiornamento di un prodotto. | Svuota la cache interna del modulo per riflettere le modifiche ai prezzi o allo stato dei prodotti. |
| `deleteproduct` | Dopo l'eliminazione di un prodotto. | Svuota la cache interna del modulo per rimuovere i prodotti eliminati dalle offerte speciali. |
| `displayAddProduct` | (Hook legacy, spesso usato per i moduli di amministrazione) | Svuota la cache interna del modulo. |
| `displayUpdateProduct` | (Hook legacy, spesso usato per i moduli di amministrazione) | Svuota la cache interna del modulo. |
| `displayDeleteProduct` | (Hook legacy, spesso usato per i moduli di amministrazione) | Svuota la cache interna del modulo. |

Gli hook `addproduct`, `updateproduct`, `deleteproduct`, `displayAddProduct`, `displayUpdateProduct` e `displayDeleteProduct` sono utilizzati principalmente per attivare uno svuotamento della cache all'interno del modulo. Ciò garantisce che l'elenco dei prodotti speciali visualizzati sulla homepage sia sempre aggiornato quando le informazioni sui prodotti (specialmente prezzi o stato) cambiano.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Scheda Offerte Speciali Homepage", fai riferimento al tuo account cliente su MyPresta.eu. Il nostro team di supporto è disponibile per assisterti con qualsiasi problema tecnico o domanda riguardante la funzionalità del modulo.
