---
title: "Free My AI Act - Conformità all'Artificial Intelligence Act - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Free My AI Act - Conformità all'Artificial Intelligence Act di MyPresta.eu."
sidebar:
  label: "Free My AI Act - Conformità all'Artificial Intelligence Act"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Free My AI Act - Artificial Intelligence Act compliance su MyPresta.eu](https://mypresta.eu/modules/front-office-features/free-my-ai-act-artificial-intelligence-act-compliance.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/free-my-ai-act-artificial-intelligence-act-compliance/)
>
> ---


# Free My AI Act - Conformità all'Artificial Intelligence Act

## 1. Requisiti e Compatibilità
-   **Versioni PrestaShop supportate**: PrestaShop 9.x
-   **Compatibilità PHP**: PHP 7.4 - 8.5
-   **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per un'installazione PrestaShop e sono sufficienti per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)
Per accedere alla configurazione del modulo, naviga su **Moduli > Gestione moduli**, cerca "Free My AI Act" e clicca sul pulsante "Configura".

Questa schermata fornisce tutte le impostazioni essenziali per controllare come i contenuti AI vengono divulgati nel tuo negozio.

#### **Impostazioni generali**

-   **Abilita conformità AI Act:**
    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare le funzionalità del modulo in tutto il tuo negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Tutte le funzionalità di divulgazione AI configurate (badge, banner, avvisi) diventeranno attive nel tuo front office.
        -   *Quando disabilitato:* Tutte le funzionalità di divulgazione AI saranno nascoste e il modulo non visualizzerà alcuna informazione relativa all'IA ai clienti.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio del commerciante:** Hai completato la configurazione e sei pronto a rendere operativa la conformità all'AI Act. Abilita questa impostazione. Se hai bisogno di disabilitare temporaneamente tutte le divulgazioni per manutenzione, impostala su NO.

#### **Opzioni di divulgazione dei contenuti AI**

-   **Mostra badge AI sulle immagini dei prodotti:**
    -   **Cosa fa questa impostazione:** Controlla se un piccolo badge (ad esempio, "Generato da AI" o un'icona) appare direttamente sulle immagini dei prodotti negli elenchi di categoria e nella pagina del prodotto.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Un indicatore visivo verrà sovrapposto alle immagini dei prodotti che hai contrassegnato come generate dall'IA.
        -   *Quando disabilitato:* Nessun badge apparirà sulle immagini dei prodotti, anche se sono contrassegnate come generate dall'IA.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio del commerciante:** Utilizzi l'IA per generare o migliorare molte delle tue foto di prodotti. L'abilitazione di questa opzione fornisce una divulgazione visiva immediata ai clienti mentre navigano.

-   **Mostra avviso informazioni aggiuntive nella pagina del prodotto:**
    -   **Cosa fa questa impostazione:** Determina se un avviso di testo dedicato viene visualizzato nelle singole pagine dei prodotti per informare i clienti sui contenuti generati dall'IA (testo o immagini) per quel prodotto specifico.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Un blocco di testo personalizzabile apparirà nelle pagine dei prodotti, tipicamente sotto la descrizione o in una nuova scheda, dettagliando l'uso dell'IA per il contenuto di quel prodotto.
        -   *Quando disabilitato:* Nessun avviso specifico di divulgazione AI verrà mostrato nelle pagine dei prodotti.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio del commerciante:** Vuoi fornire una spiegazione più dettagliata sui contenuti AI per ogni prodotto. Questo avviso ti consente di elaborare oltre un semplice badge.

-   **Mostra banner politica AI a livello di negozio:**
    -   **Cosa fa questa impostazione:** Attiva un banner che appare in modo coerente in tutto il tuo negozio (ad esempio, nella parte superiore o inferiore di ogni pagina) per informare i visitatori sulla tua politica generale sui contenuti AI.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato:* Un banner personalizzabile sarà visibile su tutte le pagine, spesso con un link a una pagina di politica AI più completa.
        -   *Quando disabilitato:* Nessun banner a livello di negozio verrà visualizzato.
    -   **Valore consigliato:** SÌ
    -   **Scenario / esempio del commerciante:** Vuoi fare una dichiarazione generale sull'uso dell'IA nel tuo negozio e indirizzare i clienti a una pagina di politica dedicata per una completa trasparenza.

-   **Link alla pagina della politica AI (URL):**
    -   **Cosa fa questa impostazione:** Ti consente di specificare l'URL di una pagina CMS o di un link esterno dove i clienti possono trovare la tua politica dettagliata sui contenuti AI. Questo link sarà tipicamente incluso nel banner a livello di negozio o negli avvisi di informazioni aggiuntive.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando viene inserito un URL:* Il banner e gli avvisi includeranno un link cliccabile a questa pagina.
        -   *Quando lasciato vuoto:* Non verrà fornito alcun link, oppure il banner/avviso potrebbe non apparire se dipende da questo link.
    -   **Valore consigliato:** `[Il tuo URL della pagina CMS, ad esempio, /content/10-ai-policy]`
    -   **Scenario / esempio del commerciante:** Hai creato una pagina CMS dedicata che spiega il tuo utilizzo dell'IA, le pratiche sui dati e l'impegno per la trasparenza. Inserisci qui il suo URL in modo che i clienti possano accedervi facilmente.

#### **Personalizzazione dei contenuti**

-   **Testo badge AI (es. "AI"):**
    -   **Cosa fa questa impostazione:** Definisce il testo breve che appare sul badge AI sovrapposto alle immagini dei prodotti.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando modificato:* Il testo sul badge si aggiornerà di conseguenza.
    -   **Valore consigliato:** AI
    -   **Scenario / esempio del commerciante:** Preferisci un'etichetta più breve come "AI" invece di "Generato da AI" per mantenere il badge conciso.

-   **Colore badge AI:**
    -   **Cosa fa questa impostazione:** Imposta il colore di sfondo del badge AI.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando modificato:* Il colore di sfondo del badge si aggiornerà, consentendoti di abbinarlo al branding del tuo negozio.
    -   **Valore consigliato:** #FF0000 (Rosso) o un colore che contrasti bene con le immagini dei tuoi prodotti.
    -   **Scenario / esempio del commerciante:** Il tuo marchio utilizza una specifica palette di colori. Puoi impostare il colore del badge su una tonalità contrastante che sia comunque visivamente accattivante.

-   **Colore testo badge AI:**
    -   **Cosa fa questa impostazione:** Imposta il colore del testo all'interno del badge AI.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando modificato:* Il colore del testo sul badge si aggiornerà.
    -   **Valore consigliato:** #FFFFFF (Bianco) o un colore che contrasti bene con lo sfondo del badge scelto.
    -   **Scenario / esempio del commerciante:** Se lo sfondo del tuo badge è scuro, vorrai un testo bianco o di colore chiaro per la leggibilità.

-   **Testo avviso informazioni aggiuntive:**
    -   **Cosa fa questa impostazione:** Ti consente di personalizzare il testo completo visualizzato nell'"Avviso informazioni aggiuntive" nelle pagine dei prodotti.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando modificato:* Il contenuto dell'avviso nelle pagine dei prodotti rifletterà il tuo testo personalizzato.
    -   **Valore consigliato:** "Si prega di notare: Parti di questa descrizione del prodotto e/o immagini potrebbero essere state generate o migliorate utilizzando l'Intelligenza Artificiale per fornirvi informazioni complete."
    -   **Scenario / esempio del commerciante:** Vuoi dichiarare chiaramente che sia il testo che le immagini potrebbero essere generati dall'IA e spiegare il motivo (ad esempio, per informazioni complete).

-   **Testo banner a livello di negozio:**
    -   **Cosa fa questa impostazione:** Personalizza il messaggio visualizzato nel banner della politica AI a livello di negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando modificato:* Il testo nel banner su tutte le pagine si aggiornerà.
    -   **Valore consigliato:** "Il nostro negozio utilizza l'IA per migliorare i contenuti. Scopri di più sulla nostra politica AI."
    -   **Scenario / esempio del commerciante:** Vuoi un messaggio conciso nel banner che incoraggi i clienti a cliccare sul link per maggiori dettagli.

#### **Contrassegno AI specifico per prodotto**

Questo modulo si integra anche direttamente nella pagina di modifica del prodotto. Quando modifichi un prodotto nel Back Office (**Catalogo > Prodotti > Modifica Prodotto**), troverai una nuova scheda o sezione relativa a "Conformità AI Act".

-   **Contrassegna il contenuto del prodotto come generato dall'IA:**
    -   **Cosa fa questa impostazione:** Una casella di controllo o un interruttore nella pagina di modifica del prodotto che ti consente di contrassegnare individualmente il contenuto testuale di un prodotto specifico (descrizione, descrizione breve, caratteristiche) come generato dall'IA.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato per un prodotto:* L'"Avviso informazioni aggiuntive" (se abilitato nella configurazione del modulo) apparirà nella pagina di quel prodotto e qualsiasi altra divulgazione AI basata su testo si attiverà.
        -   *Quando disabilitato per un prodotto:* Nessuna divulgazione AI basata su testo apparirà per quel prodotto specifico.
    -   **Valore consigliato:** Abilita per qualsiasi prodotto in cui l'IA è stata utilizzata per il testo.
    -   **Scenario / esempio del commerciante:** Hai utilizzato un assistente di scrittura AI per creare la descrizione lunga di un nuovo prodotto. Abiliteresti questa impostazione per quel prodotto specifico.

-   **Contrassegna le immagini del prodotto come generate dall'IA:**
    -   **Cosa fa questa impostazione:** Una casella di controllo o un interruttore nella pagina di modifica del prodotto che ti consente di contrassegnare individualmente le immagini di un prodotto specifico come generate dall'IA o migliorate dall'IA.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato per un prodotto:* Il "Badge AI" (se abilitato nella configurazione del modulo) apparirà sulle immagini di quel prodotto e si attiverà anche l'"Avviso informazioni aggiuntive".
        -   *Quando disabilitato per un prodotto:* Nessun badge AI apparirà sulle immagini per quel prodotto specifico.
    -   **Valore consigliato:** Abilita per qualsiasi prodotto in cui l'IA è stata utilizzata per le immagini.
    -   **Scenario / esempio del commerciante:** Hai utilizzato un generatore o un miglioratore di immagini AI per l'immagine principale del prodotto. Abiliteresti questa impostazione per quel prodotto specifico.

#### 2.1.1 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
|---|---|---|---|
| Configurazione modulo | Abilita conformità AI Act | SÌ | Interruttore principale per tutte le funzionalità del modulo. |
| Configurazione modulo | Mostra badge AI sulle immagini dei prodotti | SÌ | Visualizza il badge "AI" sulle immagini dei prodotti contrassegnate come AI. |
| Configurazione modulo | Mostra avviso informazioni aggiuntive nella pagina del prodotto | SÌ | Visualizza un avviso di testo nelle pagine dei prodotti contrassegnate come AI. |
| Configurazione modulo | Mostra banner politica AI a livello di negozio | SÌ | Visualizza un banner su tutte le pagine per la politica generale. |
| Configurazione modulo | Link alla pagina della politica AI (URL) | `/content/10-ai-policy` | URL per la tua pagina dettagliata della politica AI. |
| Configurazione modulo | Testo badge AI | AI | Testo visualizzato sul badge dell'immagine del prodotto. |
| Configurazione modulo | Colore badge AI | `#FF0000` (Rosso) | Colore di sfondo del badge AI. |
| Configurazione modulo | Colore testo badge AI | `#FFFFFF` (Bianco) | Colore del testo del badge AI. |
| Configurazione modulo | Testo avviso informazioni aggiuntive | Personalizzabile | Testo completo per l'avviso della pagina del prodotto. |
| Configurazione modulo | Testo banner a livello di negozio | Personalizzabile | Testo completo per il banner a livello di negozio. |
| Pagina di modifica prodotto | Contrassegna il contenuto del prodotto come generato dall'IA | N/A (per prodotto) | Contrassegna il contenuto testuale del prodotto come generato dall'IA. |
| Pagina di modifica prodotto | Contrassegna le immagini del prodotto come generate dall'IA | N/A (per prodotto) | Contrassegna le immagini del prodotto come generate dall'IA. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: Ho abilitato il modulo e configurato le impostazioni, ma non vedo alcun badge o banner AI nel mio negozio.**
**R1:**
1.  **Controlla "Abilita conformità AI Act":** Assicurati che l'interruttore principale nella configurazione del modulo sia impostato su SÌ.
2.  **Svuota cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti). Potrebbe essere necessario svuotare anche la cache del browser (Ctrl+F5 o Cmd+R).
3.  **Controlla le impostazioni dei singoli prodotti:** Per i badge e gli avvisi nella pagina del prodotto, assicurati di aver contrassegnato individualmente i prodotti specifici come aventi contenuti/immagini generate dall'IA nelle rispettive pagine di modifica del prodotto.
4.  **Compatibilità del tema:** Sebbene il modulo sia progettato per PrestaShop 9.x, i temi personalizzati possono talvolta interferire. Se i problemi persistono, passa temporaneamente al tema PrestaShop predefinito per escludere un conflitto di tema.

**D2: Il badge o il banner AI appare strano o è posizionato male sul mio tema personalizzato.**
**R2:** Questo è spesso un conflitto CSS con il tuo tema.
1.  **Ispeziona elemento:** Utilizza gli strumenti per sviluppatori del tuo browser (F12) per ispezionare il badge/banner AI. Cerca regole CSS in conflitto.
2.  **CSS personalizzato:** Potrebbe essere necessario aggiungere CSS personalizzato al foglio di stile del tuo tema (o tramite un modulo CSS personalizzato) per regolare il posizionamento o lo stile. Le classi CSS del modulo sono solitamente ben definite (ad esempio, `.myaiactfree-badge`, `.myaiactfree-banner`).
3.  **Contatta il supporto:** Se non ti senti a tuo agio con il CSS, contatta il supporto MyPresta.eu o il tuo sviluppatore web per assistenza.

**D3: Come posso tradurre il testo del badge AI, il testo del banner o l'avviso di informazioni aggiuntive in altre lingue?**
**R3:**
1.  Vai su **Internazionale > Traduzioni** nel tuo Back Office di PrestaShop.
2.  Seleziona "Traduzioni dei moduli installati" per il "Tipo di traduzione".
3.  Scegli il tuo tema e la lingua in cui vuoi tradurre.
4.  Trova il modulo "Free My AI Act" nell'elenco. Potrai tradurre i campi di testo che hai configurato (Testo badge AI, Testo avviso informazioni aggiuntive, Testo banner a livello di negozio) direttamente lì.
5.  Salva le modifiche.

**D4: Qual è la differenza tra questo modulo "Free" e "My AI Act Pro"?**
**R4:** Il modulo "Free My AI Act" fornisce funzionalità essenziali di divulgazione per la conformità di base. "My AI Act Pro" (un modulo separato a pagamento) offre funzionalità avanzate come l'integrazione con AI Studio, l'accesso API per la segnalazione automatica, i registri di controllo e funzionalità avanzate di filigrana per le immagini. La versione Free è un ottimo punto di partenza e puoi aggiornare a Pro se le tue esigenze diventano più complesse.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica per sviluppatori e webmaster che desiderano comprendere, estendere o risolvere i problemi del modulo "Free My AI Act".

### 4.1 Panoramica dell'architettura
Il modulo `myaiactfree` segue un'architettura standard per i moduli PrestaShop, sfruttando principalmente gli hook per la visualizzazione nel front-office e `getContent()` per la configurazione nel back-office. Si integra direttamente nell'interfaccia di modifica del prodotto agganciandosi a `displayAdminProductsExtra` per fornire opzioni di segnalazione AI specifiche per il prodotto. La configurazione è memorizzata in `ps_configuration` e il rendering del front-office è ottenuto tramite i template Smarty e un file JavaScript dedicato per le interazioni dinamiche.

### 4.2 Controller (`controllers/`)
Questo modulo non contiene controller dedicati per il front-office o il back-office. Tutta la logica del front-office è gestita tramite hook all'interno del file principale del modulo, e la configurazione del back-office è gestita dal metodo `getContent()`.

### 4.3 Classi e modelli principali (`classes/`)
Questo modulo non definisce classi personalizzate o istanze di `ObjectModel`. Tutti i dati sono gestiti direttamente tramite `Configuration` per le impostazioni globali e le proprietà `Product` per i flag specifici del prodotto.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`myaiactfree/views/js/front.js`**
    *   **Ambito:** Front-office.
    *   **Responsabilità:** Questo script è probabilmente responsabile di qualsiasi comportamento dinamico del front-office relativo agli elementi di divulgazione AI. Ciò potrebbe includere:
        *   Inizializzazione della visualizzazione del badge AI sulle immagini dei prodotti dopo che il DOM è pronto.
        *   Gestione degli eventi di clic sul banner della politica AI (se è chiudibile o ha elementi interattivi).
        *   Garantire il corretto posizionamento e la reattività del badge o del banner AI, specialmente se le immagini vengono caricate dinamicamente o ridimensionate.
        *   Potenzialmente aggiunta di tooltip o popover al passaggio del mouse sui badge AI.
        *   Binding agli eventi `prestashop.on` per gli aggiornamenti dinamici dei contenuti (ad esempio, `updateProduct` nella pagina del prodotto).

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`myaiactfree/views/css/admin.css`**
    *   **Ambito:** Stile del modulo di amministrazione del back-office.
    *   **Responsabilità:** Fornisce lo stile per la pagina di configurazione del modulo (`configure.tpl`) e potenzialmente la scheda/sezione personalizzata aggiunta alla pagina di modifica del prodotto (`product_tab.tpl`). Ciò garantisce un aspetto coerente e intuitivo all'interno del Back Office di PrestaShop.
    *   **Selettori di classe CSS chiave:** Probabilmente si rivolge a elementi all'interno del modulo di configurazione del modulo, come campi di input specifici, etichette o blocchi informativi.

-   **`myaiactfree/views/css/front.css`**
    *   **Ambito:** Stile del cliente del front-office.
    *   **Responsabilità:** Definisce l'aspetto visivo di tutti gli elementi di divulgazione AI visibili ai clienti. Ciò include:
        *   Stile per il badge AI (ad esempio, `.myaiactfree-badge`, `.myaiactfree-badge-text`, `.myaiactfree-badge-icon`) inclusa la sua posizione, colore di sfondo, colore del testo, spaziatura interna e raggio del bordo.
        *   Stile per l'avviso di informazioni aggiuntive nelle pagine dei prodotti (ad esempio, `.myaiactfree-additional-info`).
        *   Stile per il banner della politica AI a livello di negozio (ad esempio, `.myaiactfree-banner`, `.myaiactfree-banner-text`, `.myaiactfree-banner-link`).
    *   **Selettori di classe CSS chiave:** Gli sviluppatori possono sovrascrivere queste classi nel CSS personalizzato del loro tema per abbinarle al design del loro marchio.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template hook (`views/templates/hook/`)**:
    *   **`myaiactfree/views/templates/hook/additional_info.tpl`**:
        *   **Hook:** Probabilmente renderizzato in `displayProductExtraContent` o hook simili della pagina del prodotto.
        *   **Output:** Visualizza il testo personalizzabile "Avviso informazioni aggiuntive" nella pagina del prodotto quando un prodotto è contrassegnato come generato dall'IA.
    *   **`myaiactfree/views/templates/hook/ai_badge.tpl`**:
        *   **Hook:** Probabilmente renderizzato in `displayProductListReviews` (per gli elenchi di prodotti) o `displayProductAdditionalInfo` (per l'immagine della pagina del prodotto).
        *   **Output:** Genera la struttura HTML per il badge AI che si sovrappone alle immagini dei prodotti, inclusi il testo e lo stile personalizzabili.
    *   **`myaiactfree/views/templates/hook/banner.tpl`**:
        *   **Hook:** Probabilmente renderizzato in `displayHeader`, `displayTop`, `displayWrapperTop` o `displayFooter`.
        *   **Output:** Renderizza il banner della politica AI a livello di negozio, inclusi il testo personalizzabile e un link alla pagina della politica AI.

-   **Template di amministrazione (`views/templates/admin/`)**:
    *   **`myaiactfree/views/templates/admin/configure.tpl`**:
        *   **Scopo:** Questo è il template principale per la pagina di configurazione del modulo accessibile tramite `getContent()`. Renderizza tutte le impostazioni globali (abilita/disabilita, testo badge, testo banner, ecc.) come descritto nella sezione 4.1.
    *   **`myaiactfree/views/templates/admin/configure_intro.tpl`**:
        *   **Scopo:** Probabilmente visualizza un messaggio introduttivo o una spiegazione nella parte superiore della pagina di configurazione del modulo, magari spiegando l'AI Act o lo scopo del modulo.
    *   **`myaiactfree/views/templates/admin/product_tab.tpl`**:
        *   **Hook:** Renderizzato tramite `displayAdminProductsExtra`.
        *   **Scopo:** Questo template fornisce l'interfaccia all'interno della pagina di modifica del prodotto (Back Office > Catalogo > Prodotti > Modifica Prodotto) dove i commercianti possono contrassegnare individualmente il contenuto e le immagini di un prodotto come generati dall'IA. Contiene le caselle di controllo o gli interruttori per i flag AI specifici del prodotto.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    *   Questo modulo non crea tabelle SQL personalizzate.
    *   Le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` utilizzando chiavi tipicamente prefissate con `MYAIACTFREE_`. Esempi:
        *   `MYAIACTFREE_ENABLED`
        *   `MYAIACTFREE_SHOW_BADGE`
        *   `MYAIACTFREE_BADGE_TEXT`
        *   `MYAIACTFREE_BADGE_COLOR`
        *   `MYAIACTFREE_BADGE_TEXT_COLOR`
        *   `MYAIACTFREE_SHOW_ADDITIONAL_INFO`
        *   `MYAIACTFREE_ADDITIONAL_INFO_TEXT`
        *   `MYAIACTFREE_SHOW_BANNER`
        *   `MYAIACTFREE_BANNER_TEXT`
        *   `MYAIACTFREE_POLICY_URL`
    *   I flag AI specifici del prodotto (per contenuto e immagini) sono probabilmente memorizzati come proprietà dell'oggetto `Product` o in un campo personalizzato associato all'entità `Product`, possibilmente tramite `Configuration::updateValue` con un suffisso ID prodotto o modificando direttamente i dati dell'oggetto `Product`.

-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
|---|---|---|
| `displayHeader` | Nella sezione `<head>` di ogni pagina. | Inietta risorse CSS/JS (`front.css`, `front.js`) e potenzialmente il banner a livello di negozio (`banner.tpl`). |
| `displayTop` / `displayWrapperTop` | Spesso nella parte superiore del contenuto della pagina. | Hook alternativo per il banner a livello di negozio (`banner.tpl`). |
| `displayFooter` | Nella parte inferiore di ogni pagina. | Hook alternativo per il banner a livello di negozio (`banner.tpl`). |
| `displayProductListReviews` | Nelle pagine di elenco prodotti, vicino alle immagini dei prodotti. | Renderizza il badge AI (`ai_badge.tpl`) sulle miniature dei prodotti. |
| `displayProductAdditionalInfo` | Nella pagina del prodotto, vicino al blocco immagine/prezzo del prodotto. | Renderizza il badge AI (`ai_badge.tpl`) sull'immagine principale del prodotto. |
| `displayProductExtraContent` | Nella pagina del prodotto, tipicamente sotto la descrizione o in una nuova scheda. | Renderizza l'avviso di informazioni aggiuntive (`additional_info.tpl`). |
| `displayAdminProductsExtra` | Nella pagina di modifica del prodotto nel Back Office. | Inietta la scheda/sezione personalizzata per la segnalazione AI specifica del prodotto (`product_tab.tpl`). |
| `actionProductUpdate` | Dopo l'aggiornamento di un prodotto nel Back Office. | Salva i flag AI specifici del prodotto (contenuto/immagine) nel database. |
| `actionProductAdd` | Dopo l'aggiunta di un nuovo prodotto nel Back Office. | Inizializza i flag AI specifici del prodotto per i nuovi prodotti. |

## 5. Supporto ufficiale e aggiornamenti
Per aggiornamenti ufficiali, supporto tecnico e per accedere alle ultime versioni del modulo "Free My AI Act - Conformità all'Artificial Intelligence Act", visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità o alla compatibilità del modulo.
"""
