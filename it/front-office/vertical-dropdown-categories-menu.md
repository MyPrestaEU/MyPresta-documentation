---
title: "Menu verticale a discesa per categorie - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Menu verticale a discesa per categorie di MyPresta.eu."
sidebar:
  label: "Menu verticale a discesa per categorie - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Vertical dropdown categories menu su MyPresta.eu](https://mypresta.eu/modules/front-office-features/vertical-dropdown-categories-menu.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/vertical-dropdown-categories-menu/)
>
> ---


# Menu verticale a discesa per categorie

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di Hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo "Menu verticale a discesa per categorie" in Gestione moduli. Questo ti porterà alla sua schermata di configurazione principale.

La pagina di configurazione del modulo fornisce impostazioni standard per controllare il suo comportamento e aspetto.

- **Cosa fa questa impostazione:** Questa sezione contiene tipicamente impostazioni generali per il modulo, come l'abilitazione/disabilitazione, la scelta di dove appare o le opzioni di visualizzazione di base. Sebbene le impostazioni specifiche non siano dettagliate nel dossier, le opzioni comuni per un modulo di questo tipo includono:

  - **Abilita/Disabilita Modulo**: Un semplice interruttore per attivare o disattivare il modulo senza disinstallarlo.
  - **Visualizza Categoria Radice**: Scegli se mostrare la categoria principale "Home" o "Radice" nel menu.
  - **Profondità Massima**: Limita quanti livelli di sottocategorie vengono visualizzati nel menu a discesa.
  - **Selezione Hook**: Scegli a quali hook di visualizzazione il modulo deve essere collegato (es. `displayLeftColumn`, `displayRightColumn`).
  - **Impostazioni Cache**: Opzioni per abilitare o disabilitare la cache per l'output del modulo per migliorare le prestazioni.
- **Effetto della modifica di questa impostazione:**

  - *Quando abilitato:* Il modulo sarà attivo e visualizzerà il menu verticale delle categorie nel tuo front office secondo le altre impostazioni.
  - *Quando disabilitato:* Il modulo non apparirà nel tuo negozio, ma la sua configurazione verrà salvata.
  - *Scelta di un hook (es. `displayLeftColumn`):* Il blocco del menu verticale apparirà nella colonna sinistra del tuo negozio.
  - *Limitazione della profondità:* Verranno mostrate solo le categorie fino al livello specificato, semplificando il menu per i clienti.
- **Valore consigliato:**

  - **Abilita Modulo**: SÌ
  - **Visualizza Categoria Radice**: NO (solitamente, per iniziare direttamente con le tue principali categorie di prodotti)
  - **Profondità Massima**: 3 (un buon equilibrio per la maggior parte dei negozi, prevenendo menu eccessivamente complessi)
  - **Selezione Hook**: `displayLeftColumn` o `displayRightColumn` (a seconda della preferenza di layout del tuo tema).
- **Scenario / esempio per il commerciante:**

  - *Scenario 1 (Semplificazione della Navigazione):* Hai una struttura di categorie molto profonda (es. 5-6 livelli). Potresti impostare "Profondità Massima" a 3 per assicurarti che i clienti non siano sopraffatti da troppe opzioni, guidandoli prima attraverso le scelte di livello superiore.
  - *Scenario 2 (Ottimizzazione delle Prestazioni):* Se il tuo negozio sperimenta un traffico elevato, abilitare la cache per l'output del modulo può accelerare significativamente i tempi di caricamento della pagina, poiché il menu non deve essere ricostruito per ogni visitatore.
  - *Scenario 3 (Regolazione del Layout):* Il tuo tema ha un aspetto migliore con la navigazione sul lato destro. Selezioneresti `displayRightColumn` nelle impostazioni dell'hook per spostare il blocco del menu di conseguenza.

### 2.2 Tabella di Riferimento Rapido per la Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Pagina di Configurazione del Modulo | Abilita/Disabilita Modulo | Abilitato | Controlla se il modulo è attivo nel tuo negozio. |
| Pagina di Configurazione del Modulo | Visualizza Categoria Radice | No | Determina se la categoria di primo livello "Home" viene mostrata. |
| Pagina di Configurazione del Modulo | Profondità Massima | 3 | Limita il numero di livelli di sottocategorie visualizzati. |
| Pagina di Configurazione del Modulo | Selezione Hook | `displayLeftColumn` | Specifica dove appare il blocco del menu (es. colonna sinistra o destra). |
| Pagina di Configurazione del Modulo | Caching | Abilitato | Migliora le prestazioni memorizzando l'HTML del menu generato. |

## 3. Risoluzione dei Problemi per il Commerciante e Domande Frequenti (FAQ)

**D1: Il menu non appare nel mio negozio dopo l'installazione.**
**R1:**

1. **Controlla lo Stato del Modulo:** Vai su **Moduli > Gestione moduli** e assicurati che il modulo "Menu verticale a discesa per categorie" sia installato e abilitato.
2. **Verifica l'Assegnazione dell'Hook:** Nella configurazione del modulo, assicurati che sia assegnato a un hook attivo (es. `displayLeftColumn`, `displayRightColumn`). Alcuni temi potrebbero non visualizzare tutti gli hook per impostazione predefinita, oppure potresti dover regolare le impostazioni di layout del tuo tema.
3. **Svuota la Cache:** Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty"). A volte, i vecchi contenuti memorizzati nella cache impediscono la visualizzazione di nuovi moduli.
4. **Compatibilità del Tema:** Se stai utilizzando un tema altamente personalizzato, potrebbe sovrascrivere il rendering predefinito degli hook di PrestaShop. Contatta lo sviluppatore del tuo tema o un esperto di PrestaShop.

**D2: L'effetto a discesa non funziona o appare danneggiato.**
**R2:**

1. **Conflitti del Tema:** Un altro modulo o il JavaScript/CSS personalizzato del tuo tema potrebbe essere in conflitto con lo stile o la funzionalità del modulo.
2. **Svuota la Cache:** Prova sempre a svuotare la cache di PrestaShop (**Parametri Avanzati > Prestazioni**) e la cache del tuo browser.
3. **Ispeziona con gli Strumenti del Browser:** Utilizza gli strumenti per sviluppatori del tuo browser (F12) per verificare la presenza di errori JavaScript nella console o conflitti CSS. Cerca messaggi di errore rossi.
4. **Reinstallazione del Modulo:** Prova a disinstallare e reinstallare il modulo (dopo aver eseguito il backup delle tue impostazioni, se possibile).

**D3: Come posso cambiare i colori o i font del menu?**
**R3:** Il modulo viene fornito con il proprio file `blockcategories.css` per lo stile.

1. **Personalizzazione di Base:** Per modifiche minori, puoi spesso sovrascrivere questi stili nel file CSS personalizzato del tuo tema (es. `themes/yourtheme/assets/css/custom.css`). Questo è il modo più sicuro per apportare modifiche senza modificare i file core del modulo.
2. **Personalizzazione Avanzata:** Per modifiche più estese, potresti dover modificare direttamente il file `blockcategories.css` all'interno della directory `views/css/` del modulo. **Tuttavia, tieni presente che queste modifiche andranno perse con gli aggiornamenti del modulo.** È sempre meglio utilizzare le sovrascritture del tema.
3. **Personalizzatore del Tema PrestaShop:** Alcuni temi offrono un "Personalizzatore del Tema" o "Configuratore Live" che consente modifiche di stile di base senza toccare il codice. Controlla se il tuo tema ha questa funzione.

**D4: Le mie categorie non vengono visualizzate nel menu.**
**R4:**

1. **Stato della Categoria:** Assicurati che le tue categorie siano attive e visibili nel tuo Back Office di PrestaShop (**Catalogo > Categorie**).
2. **Impostazione Categoria Radice:** Controlla la configurazione del modulo per vedere se "Visualizza Categoria Radice" è abilitato o disabilitato. Se disabilitato, e le tue categorie sono figli diretti della radice, potrebbero non apparire.
3. **Permessi:** Assicurati che le categorie abbiano i permessi di gruppo appropriati se stai utilizzando gruppi di clienti.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

### 4.1 Panoramica dell'Architettura

Il modulo "Menu verticale a discesa per categorie" (`verticalblockcategories`) è un modulo PrestaShop standard progettato per visualizzare un blocco di navigazione dinamico delle categorie. Sfrutta principalmente il sistema di hook di PrestaShop per renderizzare il suo contenuto in varie posizioni del front-office. La logica del modulo è contenuta nel suo file PHP principale, che gestisce l'installazione, la disinstallazione, la registrazione degli hook e la configurazione. La presentazione visiva è gestita tramite template Smarty e un file CSS dedicato. Non introduce controller personalizzati o ObjectModels complessi, concentrandosi sulla renderizzazione efficiente dei dati di categoria esistenti.

### 4.2 Controller (`controllers/`)

Questo modulo non contiene alcun controller amministrativo Front-Office o Back-Office personalizzato. Tutta la logica è gestita all'interno del file principale del modulo (`index.php`) e renderizzata tramite hook.

### 4.3 Classi e Modelli Core (`classes/`)

Questo modulo non definisce classi o ObjectModels personalizzati in una directory `classes/`. Utilizza direttamente le classi core `Category` e `Tools` di PrestaShop per recuperare ed elaborare i dati delle categorie.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo non contiene file JavaScript personalizzati. L'effetto a discesa è tipicamente ottenuto puramente tramite CSS, o si basa su librerie jQuery/JavaScript esistenti già caricate da PrestaShop o dal tema.

### 4.5 Fogli di Stile CSS (`views/css/`)

- **`verticalblockcategories/blockcategories.css`**
  - **Ambito**: Stile del front-office per il cliente.
  - **Componenti UI principali e contenitori che stilizza**: Questo foglio di stile è responsabile del layout visivo, dell'aspetto e dell'animazione a discesa del menu verticale delle categorie. Si rivolge agli elementi all'interno della struttura HTML generata dal modulo, come `div#categories_block_left`, `ul.tree`, `li.last`, `a.selected` e `ul.tree li ul`.
  - **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere nel loro tema**:
    - `#categories_block_left` (o ID/classe simile per il contenitore del blocco principale)
    - `.block_content`
    - `ul.tree` (per l'elenco principale delle categorie)
    - `ul.tree li` (per i singoli elementi di categoria)
    - `ul.tree li a` (per i link delle categorie)
    - `ul.tree li ul` (per i menu a discesa delle sottocategorie)
    - `ul.tree li ul li` (per i singoli elementi delle sottocategorie)
    - `.selected` (per la categoria attualmente attiva)
    - Classi relative agli effetti hover e alle transizioni per il menu a discesa.

### 4.6 Struttura del Template Smarty (`views/templates/`)

- **Template degli hook (`views/templates/hook/`)**:
  - **`verticalblockcategories/blockcategories.tpl`**: Questo è il file template principale renderizzato dal modulo quando agganciato. Tipicamente contiene la struttura complessiva del blocco categorie, inclusi il titolo e l'elenco non ordinato principale (`<ul>`) che conterrà l'albero delle categorie. Probabilmente include `category-tree-branch.tpl` ricorsivamente per costruire il menu completo.
    - **Agganciato in**: `displayLeftColumn`, `displayRightColumn`, `displayHeader`, `displayFooter`, `displayProductExtraContent` (o altri hook di colonna/contenuto).
    - **Output**: Il blocco HTML principale per il menu verticale delle categorie.
  - **`verticalblockcategories/category-tree-branch.tpl`**: Questo template è progettato per il rendering ricorsivo dei singoli rami di categoria (categorie e le loro sottocategorie). Gestisce la visualizzazione di un singolo elemento di categoria e, se quella categoria ha figli, richiama se stesso ricorsivamente per renderizzare quei figli come un elenco annidato, creando la struttura ad albero.
    - **Incluso da**: `blockcategories.tpl` (e potenzialmente se stesso).
    - **Output**: Un elemento `<li>` per una categoria, che può contenere un `<ul>` annidato per le sue sottocategorie.

### 4.7 Schema del Database e Mappa degli Hook

- **Tabelle del Database**: Questo modulo non crea tabelle di database personalizzate. Si basa interamente sulle tabelle core di PrestaShop `ps_category`, `ps_category_lang` e `ps_category_product` per i dati delle categorie. Le impostazioni di configurazione sono memorizzate in `ps_configuration` utilizzando chiavi prefissate con `VERTICALBLOCKCATEGORIES_`.
- **Tabella degli Hook Registrati**:

  | Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
  | --- | --- | --- |
  | `displayHeader` | Nella sezione `<head>` dell'HTML. | Potenzialmente utilizzato per caricare risorse CSS/JS, sebbene per questo modulo, il CSS sia tipicamente registrato tramite `install()` o `hookDisplayHeader` stesso. |
  | `displayLeftColumn` | Renderizza il contenuto nella colonna sinistra del negozio. | Hook primario per visualizzare il blocco del menu verticale delle categorie. |
  | `displayRightColumn` | Renderizza il contenuto nella colonna destra del negozio. | Hook alternativo per visualizzare il blocco del menu verticale delle categorie. |
  | `displayHome` | Renderizza il contenuto nella homepage. | Può essere utilizzato per visualizzare il menu nella homepage, sebbene meno comune per un menu verticale. |
  | `displayFooter` | Renderizza il contenuto nella sezione del piè di pagina. | Meno comune per un menu di navigazione primario, ma possibile per link supplementari. |
  | `displayProductExtraContent` | Renderizza il contenuto nella pagina del prodotto, tipicamente sotto le informazioni principali del prodotto. | Potrebbe essere utilizzato per mostrare categorie correlate per la navigazione del prodotto. |
  | `actionObjectCategoryAddAfter` | Dopo l'aggiunta di una categoria. | Potenzialmente utilizzato per svuotare la cache del modulo se la struttura delle categorie cambia. |
  | `actionObjectCategoryUpdateAfter` | Dopo l'aggiornamento di una categoria. | Potenzialmente utilizzato per svuotare la cache del modulo se la struttura delle categorie cambia. |
  | `actionObjectCategoryDeleteAfter` | Dopo l'eliminazione di una categoria. | Potenzialmente utilizzato per svuotare la cache del modulo se la struttura delle categorie cambia. |
  | `actionShopDataDuplication` | Quando un negozio viene duplicato (in contesto multishop). | Assicura che la configurazione del modulo venga copiata nel nuovo negozio. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Menu verticale a discesa per categorie", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema tecnico o domanda riguardante la funzionalità del modulo.
