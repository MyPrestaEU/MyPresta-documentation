---
title: "European Union Cookie Law Pro - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop European Union Cookie Law Pro di MyPresta.eu."
sidebar:
  label: "European Union Cookie Law Pro - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo European Union Cookie Law Pro su MyPresta.eu](https://mypresta.eu/modules/front-office-features/european-union-cookie-law-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/european-union-cookie-law-pro/)
>
> ---


# European Union Cookie Law Pro

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Di solito non sono necessarie configurazioni speciali del server.

## 2. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura > European Union Cookie Law Pro)

Questa è la schermata di configurazione principale dove definirai l'aspetto, il contenuto e il comportamento del tuo avviso sui cookie. Il modulo offre una funzione di anteprima dal vivo, che ti consente di vedere le tue modifiche in tempo reale nel back office prima di salvare.

#### **Impostazioni Generali**

- **Abilita Modulo Cookie Law:**

  - **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare l'avviso sui cookie in tutto il tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (SÌ):* L'avviso sui cookie verrà visualizzato ai visitatori in base alle altre impostazioni.
    - *Quando disabilitato (NO):* L'avviso sui cookie non apparirà sul tuo negozio e nessun consenso sui cookie verrà raccolto da questo modulo.
  - **Valore consigliato:** SÌ (per garantire la conformità legale).
  - **Scenario / esempio del commerciante:** Lo disattiveresti temporaneamente durante la manutenzione o se stai testando una soluzione diversa per i cookie.
- **Tempo di Scadenza dei Cookie (in giorni):**

  - **Cosa fa questa impostazione:** Determina per quanto tempo il consenso ai cookie di un utente viene ricordato dal tuo negozio. Dopo questo periodo, all'utente verrà richiesto nuovamente il consenso.
  - **Effetto della modifica di questa impostazione:**
    - *Se impostato su 365:* Il consenso di un utente sarà valido per un anno.
    - *Se impostato su 30:* Il consenso sarà valido per un mese.
  - **Valore consigliato:** 365 (un anno) è un periodo comune e ragionevole per la maggior parte dei regolamenti. Controlla le leggi locali per requisiti specifici.
  - **Scenario / esempio del commerciante:** Se le tue normative locali richiedono un nuovo consenso ogni 6 mesi, imposteresti questo valore su 180.
- **Visualizza su Dispositivi Mobili:**

  - **Cosa fa questa impostazione:** Controlla se l'avviso sui cookie viene mostrato agli utenti che navigano su smartphone e tablet.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (SÌ):* L'avviso sui cookie apparirà sui dispositivi mobili, adattando il suo layout per schermi più piccoli.
    - *Quando disabilitato (NO):* Gli utenti mobili non vedranno l'avviso sui cookie.
  - **Valore consigliato:** SÌ (per la piena conformità su tutti i dispositivi).
  - **Scenario / esempio del commerciante:** Dovresti sempre abilitare questa opzione, poiché gli utenti mobili sono soggetti alle stesse leggi sulla privacy.
- **Visualizza solo ai Visitatori dei Paesi UE:**

  - **Cosa fa questa impostazione:** Se abilitata, l'avviso sui cookie verrà mostrato solo ai visitatori il cui indirizzo IP indica che stanno navigando da uno stato membro dell'UE.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato (SÌ):* I visitatori non UE non vedranno il banner.
    - *Quando disabilitato (NO):* Tutti i visitatori, indipendentemente dalla loro posizione, vedranno il banner.
  - **Valore consigliato:** Dipende dal tuo pubblico di destinazione e dalla consulenza legale. Se servi solo clienti UE, SÌ potrebbe essere appropriato. Se servi un pubblico globale e vuoi essere sicuro, NO è meglio.
  - **Scenario / esempio del commerciante:** Un negozio australiano che serve principalmente clienti australiani potrebbe abilitare questa opzione per evitare di mostrare il banner al loro pubblico principale, pur rispettando la conformità per i pochi visitatori UE. Un negozio globale potrebbe disabilitarla per essere universalmente conforme.

#### **Contenuto e Link**

- **Messaggio Cookie Law:**

  - **Cosa fa questa impostazione:** Questo è il testo principale visualizzato nell'avviso sui cookie, che informa gli utenti sull'uso dei cookie. Puoi utilizzare un editor di testo ricco per formattarlo.
  - **Effetto della modifica di questa impostazione:** Il testo che inserisci qui sarà il messaggio principale che i tuoi clienti leggeranno.
  - **Valore consigliato:** Un messaggio chiaro e conciso come "Questo sito web utilizza i cookie per assicurarti la migliore esperienza sul nostro sito web. [Maggiori Informazioni]"
  - **Scenario / esempio del commerciante:** Potresti includere informazioni sui tipi di cookie utilizzati (es. "Utilizziamo i cookie per l'analisi e per migliorare la tua esperienza di acquisto.").
- **Testo Pulsante "Accetta":**

  - **Cosa fa questa impostazione:** Definisce il testo visualizzato sul pulsante che gli utenti cliccano per accettare i cookie.
  - **Effetto della modifica di questa impostazione:** Cambia l'etichetta del pulsante di accettazione.
  - **Valore consigliato:** "Accetta", "Ho capito", "OK", "Comprendo".
  - **Scenario / esempio del commerciante:** Potresti usare "Accetta e Continua" per incoraggiare gli utenti a procedere.
- **Testo Pulsante "Maggiori Informazioni":**

  - **Cosa fa questa impostazione:** Definisce il testo visualizzato sul pulsante che gli utenti cliccano per saperne di più sulla tua politica sui cookie.
  - **Effetto della modifica di questa impostazione:** Cambia l'etichetta del pulsante informativo.
  - **Valore consigliato:** "Maggiori Informazioni", "Info", "Politica sulla Privacy".
  - **Scenario / esempio del commerciante:** Potresti usare "Impostazioni Cookie" se hai un sistema dettagliato di gestione delle preferenze.
- **Link alla Pagina della Politica sulla Privacy:**

  - **Cosa fa questa impostazione:** Specifica l'URL dove gli utenti possono trovare la tua politica completa sulla privacy o sui cookie. Questo link sarà allegato al pulsante "Maggiori Informazioni" o a una parte specifica del tuo messaggio.
  - **Effetto della modifica di questa impostazione:** Quando gli utenti cliccano sul pulsante "Maggiori Informazioni", verranno reindirizzati a questo URL.
  - **Valore consigliato:** L'URL completo della tua pagina CMS (es. `https://iltuonegozio.com/content/3-termini-e-condizioni`).
  - **Scenario / esempio del commerciante:** Crei una pagina CMS dedicata in PrestaShop (Design > Pagine) per la tua "Politica sui Cookie" e la colleghi qui.

#### **Opzioni di Visualizzazione e Stile**

- **Posizione Avviso Cookie:**

  - **Cosa fa questa impostazione:** Determina dove appare l'avviso sui cookie sul tuo sito web.
  - **Effetto della modifica di questa impostazione:**
    - *Barra Superiore:* Il banner appare nella parte superiore della finestra del browser.
    - *Barra Inferiore:* Il banner appare nella parte inferiore della finestra del browser.
    - *Modale Centrale:* Un pop-up al centro dello schermo.
    - *Box Fluttuante (In alto a sinistra, In alto a destra, In basso a sinistra, In basso a destra):* Una scatola più piccola e fissa in uno degli angoli.
  - **Valore consigliato:** La Barra Inferiore o il Box Fluttuante sono generalmente meno intrusivi. Il Modale Centrale è molto visibile ma può essere dirompente.
  - **Scenario / esempio del commerciante:** Un negozio di moda potrebbe preferire una sottile "Barra Inferiore" per mantenere l'attenzione sui prodotti, mentre un'attività basata sui servizi potrebbe utilizzare un "Modale Centrale" per la massima visibilità.
- **Colore Sfondo:**

  - **Cosa fa questa impostazione:** Imposta il colore di sfondo principale del banner dell'avviso sui cookie.
  - **Effetto della modifica di questa impostazione:** Cambia lo sfondo visivo dell'avviso.
  - **Valore consigliato:** Un colore che contrasti bene con il tuo testo e si abbini al tuo brand.
  - **Scenario / esempio del commerciante:** Usa il colore primario del tuo brand o un grigio neutro.
- **Colore Testo:**

  - **Cosa fa questa impostazione:** Imposta il colore del testo del messaggio principale all'interno dell'avviso.
  - **Effetto della modifica di questa impostazione:** Cambia il colore del testo del messaggio.
  - **Valore consigliato:** Un colore che offra una buona leggibilità rispetto allo sfondo scelto.
  - **Scenario / esempio del commerciante:** Testo bianco su sfondo scuro, o testo grigio scuro su sfondo chiaro.
- **Colore Link:**

  - **Cosa fa questa impostazione:** Imposta il colore per qualsiasi link all'interno del tuo messaggio sui cookie (es. il link "Maggiori Informazioni" se fa parte del messaggio).
  - **Effetto della modifica di questa impostazione:** Cambia il colore del testo cliccabile all'interno del messaggio.
  - **Valore consigliato:** Il colore accentato del tuo brand o un blu standard per i link.
  - **Scenario / esempio del commerciante:** Usa un colore brillante per far risaltare il link "Maggiori Informazioni".
- **Colore Sfondo Pulsante:**

  - **Cosa fa questa impostazione:** Imposta il colore di sfondo per i pulsanti "Accetta" e "Maggiori Informazioni".
  - **Effetto della modifica di questa impostazione:** Cambia lo sfondo visivo dei pulsanti.
  - **Valore consigliato:** Un colore che renda i pulsanti chiaramente visibili e cliccabili.
  - **Scenario / esempio del commerciante:** Usa il colore della call-to-action del tuo brand.
- **Colore Testo Pulsante:**

  - **Cosa fa questa impostazione:** Imposta il colore del testo sui pulsanti "Accetta" e "Maggiori Informazioni".
  - **Effetto della modifica di questa impostazione:** Cambia il colore delle etichette dei pulsanti.
  - **Valore consigliato:** Un colore che offra un buon contrasto con lo sfondo del pulsante.
  - **Scenario / esempio del commerciante:** Testo bianco su un pulsante colorato, o testo nero su un pulsante chiaro.
- **Colore Sfondo Pulsante al Hover:**

  - **Cosa fa questa impostazione:** Imposta il colore di sfondo dei pulsanti quando un utente ci passa sopra con il mouse.
  - **Effetto della modifica di questa impostazione:** Fornisce un feedback visivo all'utente che il pulsante è interattivo.
  - **Valore consigliato:** Una tonalità leggermente più scura o più chiara del normale colore di sfondo del pulsante.
  - **Scenario / esempio del commerciante:** Un sottile cambiamento di colore per indicare l'interattività.
- **Colore Testo Pulsante al Hover:**

  - **Cosa fa questa impostazione:** Imposta il colore del testo dei pulsanti quando un utente ci passa sopra con il mouse.
  - **Effetto della modifica di questa impostazione:** Fornisce un feedback visivo.
  - **Valore consigliato:** Spesso lo stesso del normale colore del testo del pulsante, o un colore contrastante se lo sfondo cambia significativamente.
  - **Scenario / esempio del commerciante:** Se lo sfondo del tuo pulsante diventa scuro al passaggio del mouse, potresti cambiare il testo in bianco.
- **Raggio Bordo (px):**

  - **Cosa fa questa impostazione:** Controlla la rotondità degli angoli dell'avviso sui cookie e dei suoi pulsanti. Un valore di 0 significa angoli netti, valori più alti significano angoli più arrotondati.
  - **Effetto della modifica di questa impostazione:**
    - *0px:* Angoli netti, quadrati.
    - *5px:* Angoli leggermente arrotondati.
    - *20px:* Angoli molto arrotondati, a forma di pillola.
  - **Valore consigliato:** 0-5px per un aspetto moderno e pulito; più alto per una sensazione più morbida e amichevole.
  - **Scenario / esempio del commerciante:** Abbina questo al `border-radius` utilizzato nel tuo tema per coerenza.
- **Effetto Vetro:**

  - **Cosa fa questa impostazione:** Applica un effetto traslucido, simile a vetro smerigliato, allo sfondo dell'avviso sui cookie.
  - **Effetto della modifica di questa impostazione:** Rende lo sfondo leggermente trasparente e sfocato, permettendo al contenuto sottostante di trasparire sottilmente.
  - **Valore consigliato:** Provalo e vedi se si adatta al tuo design. Può aggiungere un tocco premium.
  - **Scenario / esempio del commerciante:** Usalo se il tuo tema ha un'estetica moderna e minimalista.
- **Sfondo Sfumato:**

  - **Cosa fa questa impostazione:** Ti consente di utilizzare una transizione fluida tra due colori per lo sfondo dell'avviso sui cookie invece di un singolo colore solido.
  - **Effetto della modifica di questa impostazione:** Crea una miscela di colori visivamente accattivante. Avrai tipicamente opzioni per un colore di inizio e fine.
  - **Valore consigliato:** Usa colori che si completano a vicenda e il tuo brand.
  - **Scenario / esempio del commerciante:** Un negozio di tecnologia potrebbe usare una sfumatura dal blu al viola per un look moderno.
- **Colore Sfondo Overlay (per Modale Centrale):**

  - **Cosa fa questa impostazione:** Quando si utilizza la posizione "Modale Centrale", imposta il colore dello strato semi-trasparente che copre il resto della pagina dietro il modale.
  - **Effetto della modifica di questa impostazione:** Controlla il focus visivo sul modale. Un overlay più scuro e opaco fa risaltare di più il modale.
  - **Valore consigliato:** Un nero semi-trasparente (`rgba(0,0,0,0.7)`) o una tonalità scura che si abbini al tuo tema.
  - **Scenario / esempio del commerciante:** Usa un overlay scuro e leggermente trasparente per assicurarti che il modale dei cookie sia il focus principale quando appare.
- **CSS Personalizzato:**

  - **Cosa fa questa impostazione:** Fornisce un'area di testo dove puoi aggiungere le tue regole CSS personalizzate per stilizzare ulteriormente l'avviso sui cookie, sovrascrivendo gli stili predefiniti del modulo.
  - **Effetto della modifica di questa impostazione:** Consente una personalizzazione avanzata oltre le opzioni fornite.
  - **Valore consigliato:** Lascia vuoto a meno che tu non abbia requisiti di design specifici e conoscenza CSS.
  - **Scenario / esempio del commerciante:** Potresti usarlo per cambiare la dimensione del carattere del messaggio, aggiungere un'ombra o regolare la spaziatura se le opzioni integrate non sono sufficienti.

#### **Preset e Anteprima Live**

- **Carica Preset:**

  - **Cosa fa questa impostazione:** Ti consente di applicare rapidamente un set predefinito di opzioni di stile (colori, posizioni, effetti) da una libreria di design già pronti.
  - **Effetto della modifica di questa impostazione:** Trasforma istantaneamente l'aspetto del tuo avviso sui cookie per abbinarlo al preset scelto. Tutte le singole impostazioni di stile verranno aggiornate.
  - **Valore consigliato:** Sfoglia i preset per trovarne uno che si avvicini al tuo brand, quindi affinalo.
  - **Scenario / esempio del commerciante:** Stai cercando un banner scuro e minimalista. Selezioni un preset "Tema Scuro" e poi regoli solo le tonalità esatte di nero e grigio.
- **Anteprima Live:**

  - **Cosa fa questa impostazione:** Questa sezione della pagina di configurazione visualizza un'anteprima in tempo reale del tuo avviso sui cookie mentre regoli le impostazioni.
  - **Effetto della modifica di questa impostazione:** Ti mostra esattamente come apparirà il tuo banner sul front office, senza dover salvare e aggiornare il tuo negozio.
  - **Valore consigliato:** Utilizza sempre l'anteprima dal vivo per verificare le tue scelte di design prima di salvare.
  - **Scenario / esempio del commerciante:** Stai sperimentando diversi colori per i pulsanti; l'anteprima dal vivo ti mostra immediatamente quale combinazione ha l'aspetto migliore.

### 2.2 Tabella di Riferimento Rapido della Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Abilita Modulo Cookie Law | SÌ | Interruttore principale per l'avviso sui cookie. |
| | Tempo di Scadenza Cookie (giorni) | 365 | Per quanto tempo il consenso viene ricordato. |
| | Visualizza su Dispositivi Mobili | SÌ | Mostra banner su telefoni/tablet. |
| | Visualizza solo ai Visitatori UE | NO (per conformità globale) | Targetta visitatori UE o tutti i visitatori. |
| | Messaggio Cookie Law | Personalizzabile | Testo principale dell'avviso sui cookie. |
| | Testo Pulsante "Accetta" | "Accetta" | Etichetta per il pulsante di consenso. |
| | Testo Pulsante "Maggiori Info" | "Maggiori Informazioni" | Etichetta per il pulsante info. |
| | Link alla Pagina Politica Privacy | Il tuo URL della Politica | URL per la politica dettagliata sui cookie. |
| | Posizione Avviso Cookie | Barra Inferiore / Box Fluttuante | Dove appare il banner (Barra Superiore/Inferiore, Modale Centrale, Box Fluttuante). |
| | Colore Sfondo | Personalizzabile | Colore di sfondo principale dell'avviso. |
| | Colore Testo | Personalizzabile | Colore del testo del messaggio. |
| | Colore Link | Personalizzabile | Colore dei link all'interno del messaggio. |
| | Colore Sfondo Pulsante | Personalizzabile | Colore di sfondo dei pulsanti di azione. |
| | Colore Testo Pulsante | Personalizzabile | Colore del testo sui pulsanti di azione. |
| | Colore Sfondo Pulsante al Hover | Personalizzabile | Colore di sfondo al passaggio del mouse sul pulsante. |
| | Colore Testo Pulsante al Hover | Personalizzabile | Colore del testo al passaggio del mouse sul pulsante. |
| | Raggio Bordo (px) | 0-5 | Rotondità degli angoli. |
| | Effetto Vetro | NO | Aggiunge un effetto traslucido e smerigliato. |
| | Sfondo Sfumato | NO | Utilizza una sfumatura di colore per lo sfondo. |
| | Colore Sfondo Overlay | Scuro semi-trasparente | Colore dell'overlay di sfondo per il Modale Centrale. |
| | CSS Personalizzato | Vuoto | Per override di stile avanzati. |
| | Carica Preset | Scegli uno | Applica opzioni di stile predefinite. |
| | Anteprima Live | N/A | Feedback visivo in tempo reale delle impostazioni. |

## 3. Risoluzione dei Problemi del Commerciante e Domande Frequenti (FAQ)

**D: Ho configurato il modulo, ma il banner dei cookie non appare sul mio negozio.**
R:

1.  **Controlla "Abilita Modulo Cookie Law":** Assicurati che sia impostato su SÌ nella configurazione del modulo.
2.  **Svuota Cache:** Vai su **Parametri Avanzati > Prestazioni** nel back office di PrestaShop e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti). Potrebbe essere necessario svuotare anche la cache del browser (Ctrl+F5 o Cmd+R).
3.  **Controlla l'Impostazione del Paese UE:** Se "Visualizza solo ai Visitatori dei Paesi UE" è abilitato, assicurati di testare da un indirizzo IP dell'UE. Prova a disabilitare temporaneamente questa impostazione per il test.
4.  **Compatibilità del Tema:** Sebbene il modulo sia progettato per essere compatibile, alcuni temi altamente personalizzati potrebbero avere conflitti. Controlla la console per sviluppatori del tuo browser (F12) per errori JavaScript.

**D: Il banner appare diverso sul mio negozio rispetto all'anteprima dal vivo.**
R:

1.  **Svuota Cache:** Svuota sempre la cache di PrestaShop (**Parametri Avanzati > Prestazioni**) dopo aver apportato modifiche. La cache del tuo browser potrebbe anche mostrare una versione più vecchia.
2.  **Conflitti CSS Personalizzati:** Se hai aggiunto "CSS Personalizzato" o il tuo tema ha stili in conflitto, potrebbero sovrascrivere le impostazioni del modulo. Rimuovi temporaneamente il tuo CSS personalizzato per vedere se questo risolve il problema.
3.  **Override del Tema:** Il tuo tema potrebbe avere regole CSS specifiche più specifiche di quelle del modulo. Uno sviluppatore può aiutarti a identificare e risolvere questi problemi.

**D: Come traduco il messaggio sui cookie e i testi dei pulsanti in altre lingue?**
R:

1.  Vai su **Internazionale > Traduzioni** nel back office di PrestaShop.
2.  Seleziona "Traduzioni dei moduli installati" come Tipo di traduzione.
3.  Scegli il tuo tema.
4.  Seleziona la lingua che desideri tradurre.
5.  Trova il modulo "European Union Cookie Law Pro" nell'elenco. Potrai tradurre il "Messaggio Cookie Law", il "Testo Pulsante Accetta" e il "Testo Pulsante Maggiori Informazioni" lì.

**D: Il banner dei cookie copre una parte importante del mio sito web (es. un widget di chat, una voce di menu).**
R:

1.  **Regola la Posizione:** Sperimenta con l'impostazione "Posizione Avviso Cookie". Se una barra inferiore copre un widget di chat, prova una barra superiore o un box fluttuante in un angolo diverso.
2.  **CSS Personalizzato (Avanzato):** Se nessuna posizione funziona, uno sviluppatore può utilizzare il campo "CSS Personalizzato" per regolare la proprietà `z-index` del banner dei cookie o dell'elemento in conflitto per assicurarsi che l'elemento corretto sia in cima.

**D: Questo modulo gestisce diverse categorie di cookie (es. essenziali, analitici, di marketing)?**
R: Questo modulo si concentra principalmente sulla visualizzazione di un avviso generale di consenso ai cookie e sulla raccolta di un singolo consenso "accetta" o "rifiuta" (non accettando). Per una gestione più avanzata e granulare delle categorie di cookie (dove gli utenti possono selezionare quali tipi di cookie consentono), avresti tipicamente bisogno di una soluzione più complessa o di integrarti con una Piattaforma di Gestione del Consenso (CMP) dedicata. Questo modulo è progettato per una conformità semplice.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

Questa sezione fornisce una panoramica tecnica per sviluppatori e webmaster che desiderano comprendere, personalizzare o eseguire il debug del modulo "European Union Cookie Law Pro".

### 4.1 Panoramica dell'Architettura

Il modulo `uecookiepro` segue un'architettura standard dei moduli PrestaShop, sfruttando principalmente la classe `Module` per la sua funzionalità principale e `getContent()` per la configurazione del back-office. Inietta il suo contenuto front-office direttamente in un hook scelto, rendendo dinamicamente il banner dei cookie in base alle impostazioni di configurazione. Lo stile è gestito tramite stili in linea e potenzialmente CSS personalizzato, con JavaScript che gestisce l'interazione dell'utente e l'archiviazione del consenso.

### 4.2 Controller (`controllers/`)

Questo modulo non contiene controller front-office o back-office personalizzati. Tutta la configurazione è gestita all'interno del metodo `getContent()` del file principale del modulo, e la visualizzazione front-office è gestita tramite hook.

### 4.3 Classi e Modelli Core (`classes/`)

Questo modulo non definisce classi personalizzate o istanze di `ObjectModel`. Tutta la configurazione è memorizzata direttamente nella tabella `ps_configuration` utilizzando chiavi di configurazione standard di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

Il modulo include diversi file JavaScript, principalmente per miglioramenti della configurazione del back-office e interazione del front-office.

-   `uecookiepro/jscolor/jscolor.js`:
    -   **Ambito:** Back-office.
    -   **Responsabilità:** Fornisce la funzionalità del selettore di colore utilizzata nel modulo di configurazione del modulo, consentendo ai commercianti di selezionare visivamente i colori per il banner.
-   `uecookiepro/tinymce-original.js`:
    -   **Ambito:** Back-office.
    -   **Responsabilità:** La libreria core dell'editor di testo ricco TinyMCE. Questo viene utilizzato per il campo "Messaggio Cookie Law", consentendo ai commercianti di formattare il loro messaggio con HTML.
-   `uecookiepro/tinymce16.inc.js`:
    -   **Ambito:** Back-office.
    -   **Responsabilità:** Un file di inclusione che probabilmente contiene impostazioni di inizializzazione e configurazione specifiche di TinyMCE adattate per ambienti PrestaShop 1.6.x, garantendo che l'editor funzioni correttamente all'interno della configurazione del modulo.
-   `uecookiepro/views/js/patterns.js`:
    -   **Ambito:** Back-office.
    -   **Responsabilità:** Probabilmente contiene pattern o configurazioni predefinite per i preset di stile del modulo, utilizzati per caricare rapidamente diversi temi visivi per il banner dei cookie.
-   `uecookiepro/views/js/presets-community.js`:
    -   **Ambito:** Back-office.
    -   **Responsabilità:** Contiene preset aggiuntivi contribuiti dalla comunità o estesi per lo stile visivo del banner dei cookie, offrendo più opzioni di design pronte all'uso.
-   `uecookiepro/views/js/scripts.js`:
    -   **Ambito:** Front-office e Back-office.
    -   **Responsabilità:** Questo è il file JavaScript personalizzato principale per il modulo.
        -   **Front-office:** Gestisce la logica di visualizzazione del banner dei cookie, ascolta i clic sul pulsante "Accetta", imposta il cookie di consenso e nasconde il banner. Gestisce anche la visibilità in base al `Cookie Expiration Time`.
        -   **Back-office:** Probabilmente contiene la logica per la funzionalità di anteprima dal vivo, aggiornando dinamicamente il banner di anteprima man mano che le impostazioni vengono modificate nel modulo di configurazione. Potrebbe anche gestire le interazioni con la funzione "Carica Preset".

### 4.5 Fogli di Stile CSS (`views/css/`)

Il modulo non elenca esplicitamente alcun file `.css` nell'inventario fornito. Ciò suggerisce che lo stile è gestito principalmente tramite:

1.  **Stili in linea:** Generati dinamicamente dal modulo in base alle impostazioni di configurazione (colori, posizioni, ecc.).
2.  **CSS interno di `jscolor.js`:** Per l'interfaccia utente del selettore di colore.
3.  **CSS interno di `tinymce`:** Per l'interfaccia utente dell'editor di testo ricco.
4.  **Campo CSS personalizzato:** Consente ai commercianti di iniettare i propri stili.
    Gli sviluppatori che desiderano sovrascrivere gli stili dovrebbero ispezionare l'HTML renderizzato del banner dei cookie e mirare ai suoi elementi con regole CSS più specifiche nel foglio di stile del loro tema o tramite il campo CSS personalizzato del modulo.

### 4.6 Struttura del Template Smarty (`views/templates/`)

-   **Template Hook (`views/templates/hook/`)**:
    -   `uecookiepro/top.tpl`:
        -   **Hook:** Questo template è progettato per essere renderizzato in vari hook del front-office come `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, o anche direttamente all'interno di `product.tpl` o `index.tpl` del tema a seconda della "Posizione Avviso Cookie" scelta e di come sono implementati i metodi `hookDisplay*` del modulo.
        -   **Output:** Genera la struttura HTML per il banner di consenso ai cookie, inclusi il testo del messaggio, il pulsante "Accetta" e il link "Maggiori Informazioni". Lo stile dinamico (colori, posizione, effetti) viene iniettato in questo template, sia come stili in linea che tramite manipolazione JavaScript.

### 4.7 Schema del Database e Mappa degli Hook

-   **Tabelle del Database**:
    Il modulo non crea tabelle SQL personalizzate. Tutte le impostazioni di configurazione sono memorizzate nella tabella standard `ps_configuration` di PrestaShop. Le chiavi di configurazione seguono tipicamente il pattern `UECOOKIEPRO_NOME_IMPOSTAZIONE`.
-   **Tabella degli Hook Registrati**:

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Renderizza nella sezione `<head>` di ogni pagina. | Potenzialmente utilizzato per caricare risorse CSS/JS o per iniettare il banner nella parte superiore della pagina. |
| `displayFooter` | Renderizza nella parte inferiore di ogni pagina, prima del tag di chiusura `</body>`. | Hook comune per iniettare il banner dei cookie (posizione barra inferiore) o il suo JavaScript associato. |
| `displayLeftColumn` | Renderizza nella barra laterale sinistra (se abilitata dal tema). | Meno comune per i banner dei cookie, ma potrebbe essere utilizzato per un box fluttuante nella colonna sinistra. |
| `displayRightColumn` | Renderizza nella barra laterale destra (se abilitata dal tema). | Meno comune per i banner dei cookie, ma potrebbe essere utilizzato per un box fluttuante nella colonna destra. |
| `displayProductAdditionalInfo` (o hook simile della pagina prodotto) | Renderizza nella pagina del prodotto, spesso sotto la descrizione o i dettagli del prodotto. | Potrebbe essere utilizzato per posizionare un box fluttuante specificamente sulle pagine dei prodotti. |
| `actionFrontControllerSetMedia` | Eseguito quando un controller front-end imposta i suoi media (CSS/JS). | Ideale per caricare condizionatamente CSS e JavaScript specifici del modulo solo quando necessario, migliorando le prestazioni. |

Il modulo sceglie dinamicamente quale hook utilizzare in base all'impostazione "Posizione Avviso Cookie". Ad esempio, se è selezionata "Barra Inferiore", probabilmente utilizza `displayFooter`. Se è selezionata "Barra Superiore", potrebbe utilizzare `displayHeader`. Le posizioni "Box Fluttuante" o "Modale Centrale" sono tipicamente gestite iniettando l'HTML in un hook generale come `displayFooter` e quindi utilizzando CSS (`position: fixed;`) e JavaScript per controllare il suo posizionamento esatto e la visibilità.

## 5. Supporto Ufficiale e Aggiornamenti

Per supporto ufficiale, aggiornamenti del modulo e qualsiasi ulteriore assistenza, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a fornire supporto tempestivo e a garantire che il modulo funzioni in modo ottimale.
