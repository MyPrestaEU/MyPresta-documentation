---
title: "Material Icons + Font Awesome - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Material Icons + Font Awesome di MyPresta.eu."
sidebar:
  label: "Material Icons + Font Awesome - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Material Icons + Font Awesome su MyPresta.eu](https://mypresta.eu/modules/front-office-features/material-icons-font-awesome.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/material-icons-font-awesome/)
>
> ---


# Material Icons + Font Awesome

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Nessun requisito speciale oltre a un ambiente di hosting PrestaShop standard.

## 2. Panoramica Completa della Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale e unica per il modulo "Material Icons + Font Awesome". La troverai navigando su **Moduli > Gestione moduli**, cercando "Material Icons + Font Awesome" e cliccando su "Configura".

#### **Aggiungi Font Awesome**

-   **Cosa fa questa impostazione:** Questo interruttore controlla se la libreria di icone Font Awesome viene caricata nel front-office del tuo negozio (ciò che vedono i clienti) e nel back-office (il tuo pannello di amministrazione).
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* Il file CSS di Font Awesome verrà aggiunto alla sezione `<head>` del tuo sito web, rendendo tutte le icone Font Awesome disponibili per l'uso. Questo risolverà eventuali icone Font Awesome mancanti.
    -   *Quando disabilitato:* Il file CSS di Font Awesome NON verrà caricato da questo modulo. Se il tuo tema o un altro modulo carica già Font Awesome, o se non ne hai bisogno, puoi disabilitarlo per evitare di caricarlo due volte.
-   **Valore consigliato:**
    -   **Abilitato** se noti icone Font Awesome mancanti sul tuo negozio o nel back-office, o se prevedi di utilizzare icone Font Awesome nei tuoi contenuti.
    -   **Disabilitato** se tutte le icone Font Awesome vengono già visualizzate correttamente (il che significa che il tuo tema o un altro modulo lo sta già caricando) per prevenire il caricamento ridondante.
-   **Scenario / esempio per il commerciante:** Hai installato un nuovo modulo di pagamento e le sue icone del metodo di pagamento (ad esempio, un simbolo di carta di credito) vengono visualizzate come caselle vuote. Se queste icone sono basate su Font Awesome, abilitando questa impostazione le farai apparire correttamente.

#### **Aggiungi Material Icons**

-   **Cosa fa questa impostazione:** Questo interruttore controlla se la libreria Material Icons (di Google) viene caricata nel front-office e nel back-office del tuo negozio.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* Il file CSS di Material Icons verrà aggiunto alla sezione `<head>` del tuo sito web, rendendo tutte le Material Icons disponibili per l'uso. Questo risolverà eventuali Material Icons mancanti.
    -   *Quando disabilitato:* Il file CSS di Material Icons NON verrà caricato da questo modulo. Se il tuo tema o un altro modulo carica già Material Icons, o se non ne hai bisogno, puoi disabilitarlo.
-   **Valore consigliato:**
    -   **Abilitato** se noti Material Icons mancanti sul tuo negozio o nel back-office.
    -   **Disabilitato** se tutte le Material Icons vengono già visualizzate correttamente (il che significa che il tuo tema o un altro modulo le sta già caricando) per prevenire il caricamento ridondante.
-   **Scenario / esempio per il commerciante:** Il tuo tema utilizza Material Icons per le sue frecce di navigazione o alcuni elementi della pagina prodotto, ma dopo un aggiornamento del tema, sono scomparse. Abilitando questa impostazione probabilmente le riporterà.

#### **Tabella di Riferimento Rapido della Configurazione**

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Aggiungi Font Awesome | Abilitato (se necessario) | Carica la libreria di icone Font Awesome per front e back office. Risolve le icone Font Awesome mancanti. |
| Configurazione Modulo | Aggiungi Material Icons | Abilitato (se necessario) | Carica la libreria Material Icons per front e back office. Risolve le Material Icons mancanti. |

## 3. Risoluzione dei Problemi del Commerciante e Domande Frequenti (FAQ)

**D: Ho abilitato le impostazioni, ma le icone sono ancora mancanti. Cosa devo fare?**
R: Innanzitutto, svuota la cache di PrestaShop. Vai su **Parametri Avanzati > Prestazioni** e clicca su "Svuota la cache" in alto a destra. Inoltre, svuota la cache del tuo browser (Ctrl+F5 o Cmd+Shift+R). Se le icone sono ancora mancanti, è possibile che le icone che stai cercando appartengano a una libreria di icone diversa non coperta da questo modulo, o che ci sia un conflitto CSS nel tuo tema.

**D: Questo modulo rallenterà il mio sito web?**
R: Il modulo carica file CSS standard per le librerie di icone. Se abiliti solo le librerie di cui hai bisogno e non sono già caricate dal tuo tema, l'impatto sulle prestazioni è minimo e necessario per una visualizzazione corretta. Se abiliti una libreria che è già caricata dal tuo tema, la caricherai due volte, il che può causare un leggero rallentamento. Controlla sempre se il tuo tema include già queste librerie prima di abilitarle qui.

**D: Il mio tema personalizzato ha il suo set di icone. Questo modulo interferirà?**
R: Non dovrebbe interferire direttamente. Questo modulo aggiunge le librerie di icone specificate. Se il tuo tema utilizza un set di icone diverso (ad esempio, SVG personalizzati o un'altra libreria di icone font), questo modulo aggiungerà semplicemente Font Awesome e/o Material Icons accanto ad esso. Se riscontri conflitti, puoi provare a disabilitare una o entrambe le opzioni nel modulo per vedere se risolve il problema.

**D: Come faccio a sapere se il mio tema carica già Font Awesome o Material Icons?**
R: Il modo più semplice è fare clic con il tasto destro sulla pagina del tuo negozio (front-office) e selezionare "Visualizza sorgente pagina" o "Ispeziona elemento". Quindi cerca "font-awesome.css" o "material-icons.css" all'interno della sezione `<head>`. Se li trovi, il tuo tema probabilmente li sta già caricando. In alternativa, se tutte le icone vengono visualizzate correttamente senza questo modulo, allora il tuo tema o un altro modulo lo sta già gestendo.

**D: Posso usare sia Font Awesome che Material Icons contemporaneamente?**
R: Sì, assolutamente. Puoi abilitare entrambe le opzioni nella configurazione del modulo. Questo è spesso necessario se diverse parti del tuo negozio (ad esempio, il tuo tema e un modulo di terze parti) si basano su diverse librerie di icone.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

### 4.1 Panoramica dell'Architettura

Il modulo "Material Icons + Font Awesome" è un modulo PrestaShop leggero progettato principalmente per iniettare fogli di stile CSS esterni per le librerie di icone. Segue una struttura standard dei moduli PrestaShop, sfruttando gli hook per integrare la sua funzionalità nel front-office e nel back-office. Non introduce controller, modelli o tabelle di database personalizzati, concentrandosi esclusivamente sulla gestione degli asset.

### 4.2 Controller (`controllers/`)

Questo modulo non contiene controller front-office o back-office personalizzati. Tutta la logica è gestita all'interno del file principale del modulo (`fonticons.php`) tramite hook.

### 4.3 Classi e Modelli Core (`classes/`)

Questo modulo non definisce classi personalizzate né estende `ObjectModel`. Tutta la configurazione è memorizzata direttamente in `ps_configuration` utilizzando le chiavi definite di seguito.

### 4.4 Asset JavaScript (`views/js/`)

Questo modulo non include file JavaScript personalizzati.

### 4.5 Fogli di Stile CSS (`views/css/`)

La funzionalità principale del modulo si basa su questi file CSS:

-   **`fonticons/views/css/font-awesome.css`**:

    -   **Ambito**: Front-office e Back-office.
    -   **Scopo**: Contiene le regole CSS e le dichiarazioni `@font-face` per la libreria di icone Font Awesome. Questo file è responsabile di rendere le icone Font Awesome disponibili in tutto il negozio.
    -   **Selettori di classe CSS chiave**: `fa`, `fas`, `far`, `fal`, `fab` (per diversi stili di Font Awesome), seguiti da classi di icone specifiche come `fa-shopping-cart`, `fa-user`, ecc. Gli sviluppatori possono sovrascriverli mirando a queste classi nel CSS del loro tema.
-   **`fonticons/views/css/material-icons.css`**:

    -   **Ambito**: Front-office e Back-office.
    -   **Scopo**: Contiene le regole CSS e le dichiarazioni `@font-face` per la libreria Material Icons di Google. Questo file rende disponibili le Material Icons.
    -   **Selettori di classe CSS chiave**: `material-icons`. Le icone vengono tipicamente renderizzate posizionando il nome della legatura dell'icona all'interno di un elemento con questa classe (ad esempio, `<i class="material-icons">shopping_cart</i>`). Gli sviluppatori possono sovrascrivere lo stile per questa classe.

### 4.6 Struttura del Template Smarty (`views/templates/`)

-   **`fonticons/views/advert.tpl`**:
    -   **Ambito**: Back-office (pagina di configurazione del modulo).
    -   **Scopo**: Questo template viene utilizzato per visualizzare un annuncio o un messaggio promozionale all'interno della pagina di configurazione del modulo nel back-office di PrestaShop. Viene renderizzato dal metodo `getContent()`.

### 4.7 Schema del Database e Mappa degli Hook

-   **Tabelle del Database**:
    Questo modulo non crea tabelle di database personalizzate. Memorizza le sue impostazioni di configurazione nella tabella standard `ps_configuration`.

    -   Voci di `ps_configuration`:
        -   `fonticons_FA`: Memorizza lo stato (1 per abilitato, 0 per disabilitato) dell'inclusione di Font Awesome per il front-office.
        -   `fonticons_MI`: Memorizza lo stato (1 per abilitato, 0 per disabilitato) dell'inclusione di Material Icons per il front-office.
        -   `BO_fonticons_FA`: Memorizza lo stato (1 per abilitato, 0 per disabilitato) dell'inclusione di Font Awesome per il back-office.
        -   `BO_fonticons_MI`: Memorizza lo stato (1 per abilitato, 0 per disabilitato) dell'inclusione di Material Icons per il back-office.
-   **Tabella degli Hook Registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Eseguito nella sezione `<head>` di ogni pagina del front-office. | Utilizzato per caricare i file CSS di Font Awesome e/o Material Icons per la parte del negozio rivolta al cliente, in base alla configurazione `fonticons_FA` e `fonticons_MI`. |
| `actionAdminControllerSetMedia` | Eseguito quando un AdminController sta impostando i suoi asset multimediali (CSS/JS). | Utilizzato per caricare i file CSS di Font Awesome e/o Material Icons per il back-office di PrestaShop, in base alla configurazione `BO_fonticons_FA` e `BO_fonticons_MI`. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, accedi al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Lì troverai i tuoi moduli acquistati e i link per il download. Per assistenza tecnica o qualsiasi domanda, utilizza i canali di supporto forniti su MyPresta.eu.
