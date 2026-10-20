---
title: "Barra di avanzamento spedizione gratuita - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Barra di avanzamento spedizione gratuita' di MyPresta.eu."
sidebar:
  label: "Barra di avanzamento spedizione gratuita - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Free Shipping Progress Bar for free su MyPresta.eu](https://mypresta.eu/modules/front-office-features/free-shipping-progress-bar-for-free.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/free-shipping-progress-bar-for-free/)
>
> ---


# Barra di avanzamento spedizione gratuita

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Non sono necessarie configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo "Barra di avanzamento spedizione gratuita". Puoi accedervi navigando su **Moduli > Gestione moduli** e cliccando su "Configura" accanto al nome del modulo.

#### Impostazioni Generali

-   **Abilita barra di avanzamento spedizione gratuita:**

    -   **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare l'intera funzionalità della barra di avanzamento per il tuo negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (SÌ):* La barra di avanzamento apparirà nelle posizioni selezionate nel tuo front office, e tutte le altre impostazioni del modulo avranno effetto.
        -   *Quando disabilitato (NO):* La barra di avanzamento sarà completamente nascosta dal tuo negozio, indipendentemente dalle altre impostazioni.
    -   **Valore consigliato:** SÌ (per utilizzare le funzionalità del modulo).
    -   **Scenario / esempio per il commerciante:** Se stai temporaneamente eseguendo una promozione diversa o eseguendo manutenzione, potresti disabilitarla. Altrimenti, mantienila abilitata per incoraggiare le vendite.
-   **Soglia di spedizione gratuita:**

    -   **Cosa fa questa impostazione:** Definisce l'importo esatto (nella valuta predefinita del tuo negozio) che un cliente deve spendere per qualificarsi per la spedizione gratuita.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su un importo specifico (es. 50.00):* La barra di avanzamento calcolerà l'importo rimanente in base a questa soglia.
        -   *Quando modificato:* L'obiettivo per la spedizione gratuita si aggiorna istantaneamente per tutti i clienti.
    -   **Valore consigliato:** Imposta questo valore sulla soglia di spedizione gratuita effettiva del tuo negozio. Se offri la spedizione gratuita sopra i 50€, impostalo su 50.00.
    -   **Scenario / esempio per il commerciante:** Se il tuo corriere offre la spedizione gratuita per ordini superiori a 75€, imposteresti questo valore su 75.00.
-   **Hook di visualizzazione:**

    -   **Cosa fa questa impostazione:** Determina dove sul tuo sito web verrà visualizzata la barra di avanzamento della spedizione gratuita. Puoi scegliere tra diverse posizioni comuni.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su 'displayHeader':* La barra apparirà nella sezione superiore del tuo sito web, solitamente sopra o sotto il tuo logo/menu.
        -   *Quando impostato su 'displayLeftColumn' o 'displayRightColumn':* La barra apparirà nella rispettiva colonna laterale del tuo negozio.
        -   *Quando impostato su 'displayFooter':* La barra apparirà nella parte inferiore del tuo sito web.
        -   *Quando impostato su 'displayProductButtons' (o hook simile per la pagina prodotto):* La barra apparirà sulle pagine prodotto, spesso vicino al pulsante "aggiungi al carrello".
    -   **Valore consigliato:** `displayHeader` o `displayProductButtons` sono spesso i più efficaci per la visibilità e per incoraggiare un'azione immediata.
    -   **Scenario / esempio per il commerciante:** Per garantire la massima visibilità, potresti scegliere `displayHeader`. Se vuoi incoraggiare l'aggiunta di più articoli direttamente dalla pagina prodotto, `displayProductButtons` è una buona scelta.
-   **Colore barra di avanzamento:**

    -   **Cosa fa questa impostazione:** Ti permette di personalizzare il colore della barra di avanzamento stessa. Questo ti aiuta ad abbinarla al branding del tuo negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su un colore specifico (es. #4CAF50 per il verde):* La barra verrà visualizzata in quel colore.
    -   **Valore consigliato:** Un colore che contrasti bene con lo sfondo ma che si integri con la palette di colori del tuo brand.
    -   **Scenario / esempio per il commerciante:** Se il tuo brand utilizza molto blu, potresti scegliere una tonalità di blu o un arancione complementare per far risaltare la barra.
-   **Colore di sfondo:**

    -   **Cosa fa questa impostazione:** Ti permette di personalizzare il colore di sfondo del contenitore della barra di avanzamento.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su un colore specifico (es. #F0F0F0 per il grigio chiaro):* Lo sfondo dietro l'avanzamento verrà visualizzato in quel colore.
    -   **Valore consigliato:** Un colore tenue che fornisca un buon contrasto con il colore della barra di avanzamento, spesso un grigio chiaro o bianco.
    -   **Scenario / esempio per il commerciante:** Per far risaltare la barra di avanzamento stessa, potresti usare un colore di sfondo chiaro come il bianco o un grigio molto chiaro.
-   **Colore del testo:**

    -   **Cosa fa questa impostazione:** Ti permette di personalizzare il colore del testo visualizzato all'interno o intorno alla barra di avanzamento (es. "Ti mancano X per la spedizione gratuita!").
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando impostato su un colore specifico (es. #333333 per il grigio scuro):* Il testo verrà visualizzato in quel colore.
    -   **Valore consigliato:** Un colore facilmente leggibile sia sulla barra di avanzamento che sul suo sfondo.
    -   **Scenario / esempio per il commerciante:** Se la tua barra di avanzamento è verde e il suo sfondo è grigio chiaro, un colore del testo grigio scuro o nero garantirebbe la leggibilità.

#### Anteprima Edizione Pro

Questa sezione contiene tipicamente informazioni e link per l'aggiornamento alla versione "Pro" del modulo, che offre funzionalità più avanzate. Queste non sono impostazioni di configurazione per il modulo gratuito, ma piuttosto contenuti promozionali.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Abilita barra di avanzamento spedizione gratuita | SÌ | Interruttore principale per la funzionalità del modulo. |
| Configurazione Modulo | Soglia di spedizione gratuita | Importo spedizione gratuita del tuo negozio | Definisce l'importo target per la spedizione gratuita. |
| Configurazione Modulo | Hook di visualizzazione | `displayHeader` / `displayProductButtons` | Determina dove appare la barra nel tuo negozio. |
| Configurazione Modulo | Colore barra di avanzamento | Personalizzabile (es. #4CAF50) | Imposta il colore della parte riempita della barra di avanzamento. |
| Configurazione Modulo | Colore di sfondo | Personalizzabile (es. #F0F0F0) | Imposta il colore di sfondo del contenitore della barra di avanzamento. |
| Configurazione Modulo | Colore del testo | Personalizzabile (es. #333333) | Imposta il colore del testo visualizzato con la barra. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: La barra di avanzamento non appare nel mio negozio. Cosa devo fare?**
R1:

-   **Verifica lo stato del modulo:** Vai su **Moduli > Gestione moduli** e assicurati che "Barra di avanzamento spedizione gratuita" sia installato e abilitato.
-   **Verifica la configurazione:** Naviga alla pagina di configurazione del modulo. Assicurati che "Abilita barra di avanzamento spedizione gratuita" sia impostato su SÌ. Inoltre, verifica che l'impostazione "Hook di visualizzazione" sia scelta correttamente e che il tuo tema effettivamente renderizzi quell'hook (alcuni temi personalizzati potrebbero non farlo).
-   **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty"). A volte, la vecchia cache impedisce la visualizzazione di nuovi contenuti del modulo.
-   **Compatibilità del tema:** Sebbene il modulo sia progettato per i temi PrestaShop standard (Classic, Hummingbird), temi altamente personalizzati potrebbero richiedere piccole modifiche. Se i passaggi precedenti non funzionano, contatta il supporto MyPresta.eu.

**D2: La barra di avanzamento viene visualizzata, ma non si aggiorna quando aggiungo articoli al carrello.**
R2:

-   **Verifica JavaScript:** Assicurati che non ci siano errori JavaScript sul tuo sito che potrebbero impedire l'esecuzione dello script del modulo. Puoi controllare la console per sviluppatori del tuo browser (solitamente F12) per errori.
-   **Carrello AJAX:** Il modulo si basa sulla funzionalità del carrello AJAX di PrestaShop. Assicurati che il meccanismo di aggiornamento del carrello del tuo tema sia standard e non stia sovrascrivendo le chiamate AJAX principali di PrestaShop in un modo che impedisca al modulo di rilevare le modifiche.
-   **Conflitti tra moduli:** Disabilita temporaneamente altri moduli che modificano il comportamento del carrello o visualizzano elementi negli stessi hook per verificare la presenza di conflitti.

**D3: Come posso modificare il testo visualizzato nella barra di avanzamento (es. "Ti mancano X per la spedizione gratuita!")?**
R3: La versione gratuita del modulo utilizza tipicamente testo predefinito. Per personalizzare questo testo, di solito dovresti modificare il file del template del modulo (`progress.tpl`). Tuttavia, ciò richiede una conoscenza di base dei template Smarty. Per un modo più user-friendly di personalizzare il testo, la versione Pro del modulo spesso include campi di testo dedicati nel back office.

**D4: La barra di avanzamento ha un aspetto strano o non corrisponde allo stile del mio tema.**
R4:

-   **Colori di configurazione del modulo:** Per prima cosa, usa le impostazioni "Colore barra di avanzamento", "Colore di sfondo" e "Colore del testo" nella configurazione del modulo per provare ad abbinare il tuo tema.
-   **Conflitti CSS:** Il CSS del tuo tema potrebbe sovrascrivere gli stili predefiniti del modulo. Un webmaster può ispezionare l'elemento utilizzando gli strumenti per sviluppatori del browser per identificare le regole CSS in conflitto e aggiungere CSS personalizzato al tuo tema per sovrascriverle. I file CSS del modulo (`front.css`) possono essere un buon punto di partenza per identificare i selettori da mirare.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Barra di avanzamento spedizione gratuita" segue un'architettura standard per i moduli PrestaShop, sfruttando principalmente la classe `Module` per l'installazione, la disinstallazione e la configurazione. Utilizza controller frontali per le interazioni AJAX per aggiornare dinamicamente la barra di avanzamento senza ricaricare completamente la pagina. Il modulo si integra con il sistema di hook di PrestaShop per visualizzare il suo contenuto in varie posizioni del front-office e utilizza i template Smarty per il rendering della sua interfaccia utente. La configurazione è memorizzata nella tabella `ps_configuration`.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**:

    -   `controllers/front/index.php`
        -   **Nome classe e classe genitore:** `SmartFreeShippingFreeIndexModuleFrontController` estende `ModuleFrontController`.
        -   **Responsabilità:** Questo controller probabilmente funge da base o punto di ingresso per le interazioni del front-office, sebbene i suoi metodi specifici possano essere minimi se `refresh.php` gestisce l'AJAX primario. Potrebbe essere utilizzato per il caricamento iniziale dei dati o per la configurazione del contesto.
    -   `controllers/front/refresh.php`
        -   **Nome classe e classe genitore:** `SmartFreeShippingFreeRefreshModuleFrontController` estende `ModuleFrontController`.
        -   **Responsabilità:** Questo è il controller AJAX principale. Risponde alle richieste (probabilmente POST o GET) dal JavaScript del front-office per recuperare il totale corrente del carrello, calcolare l'importo rimanente per la spedizione gratuita e restituire l'HTML o i dati aggiornati della barra di avanzamento. Gestisce la conversione di valuta e assicura che la barra di avanzamento rifletta le modifiche del carrello in tempo reale.
-   **Controller Admin Back-Office**:

    -   Nessuno. Tutta la configurazione è gestita all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

-   Nessuno. Il modulo non definisce classi `ObjectModel` personalizzate o classi di logica di business complesse oltre a quanto contenuto nel file principale del modulo (`index.php`) e nei controller frontali.

### 4.4 Risorse JavaScript (`views/js/`)

-   `views/js/front.js`
    -   **Ambito:** Front-office.
    -   **Dettagli:** Questo script è responsabile del comportamento dinamico della barra di avanzamento.
        -   Probabilmente lega i listener di eventi agli eventi di aggiornamento del carrello (es. `prestashop.on('updateCart', ...)` o eventi personalizzati attivati dal carrello AJAX del tema).
        -   Quando viene rilevato un aggiornamento del carrello, effettua una chiamata AJAX al controller frontale `refresh.php` per ottenere lo stato aggiornato della barra di avanzamento.
        -   Quindi aggiorna il DOM per riflettere il nuovo avanzamento (es. larghezza della barra di avanzamento, testo dell'importo rimanente).
        -   Potrebbe includere logica per il rendering iniziale al caricamento della pagina e la gestione di diversi hook di visualizzazione.

### 4.5 Fogli di stile CSS (`views/css/`)

-   `views/css/admin-config.css`

    -   **Ambito:** Stile del modulo di amministrazione del back-office.
    -   **Dettagli:** Contiene stili specifici per la pagina di configurazione del modulo nel back office di PrestaShop, garantendo un layout pulito e user-friendly per le impostazioni.
    -   **Selettori di classe CSS chiave:** Probabilmente mira elementi all'interno del modulo di configurazione del modulo, come `.panel`, `.form-group`, `.control-label`, ecc., specifici della struttura HTML del modulo.
-   `views/css/admin-pro-teaser.css`

    -   **Ambito:** Stile del modulo di amministrazione del back-office.
    -   **Dettagli:** Stili per il contenuto promozionale relativo alla versione "Pro" del modulo, garantendo che abbia un aspetto accattivante e distinto all'interno della pagina di configurazione.
    -   **Selettori di classe CSS chiave:** Mira elementi come `.pro-teaser-block`, `.pro-feature-list`, ecc.
-   `views/css/front.css`

    -   **Ambito:** Stile del cliente del front-office.
    -   **Dettagli:** Contiene il CSS principale per la barra di avanzamento della spedizione gratuita stessa, inclusi il suo layout, i colori, le animazioni e la reattività.
    -   **Selettori di classe CSS chiave:** Mira elementi come `#smartfreeshippingfree-progress-bar-container`, `.progress-bar-fill`, `.progress-bar-text`, ecc. Gli sviluppatori possono sovrascrivere queste classi nel `custom.css` o `theme.css` del loro tema per adattarle al loro design specifico.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template Admin (`views/templates/admin/`)**:

    -   `views/templates/admin/configure.tpl`
        -   **Scopo:** Questo è il template Smarty principale per la pagina di configurazione del modulo nel Back Office. Renderizza i campi del modulo, gli interruttori e gli elementi di input per tutte le impostazioni del modulo. Probabilmente include `get-pro-hero.tpl` e `get-pro.tpl` per il contenuto promozionale.
    -   `views/templates/admin/get-pro-hero.tpl`
        -   **Scopo:** Renderizza una sezione "hero" prominente che promuove la versione Pro del modulo, spesso nella parte superiore della pagina di configurazione.
    -   `views/templates/admin/get-pro.tpl`
        -   **Scopo:** Renderizza una sezione dettagliata che illustra le caratteristiche e i vantaggi dell'aggiornamento alla versione Pro, tipicamente includendo una call to action.
-   **Template Hook (`views/templates/hook/`)**:

    -   `views/templates/hook/progress.tpl`
        -   **Scopo:** Questo è il template principale del front-office. Renderizza la struttura HTML della barra di avanzamento della spedizione gratuita, inclusi il contenitore, la sezione di avanzamento riempita e il testo dinamico (es. "Ti mancano X per la spedizione gratuita!"). Questo template viene renderizzato dal metodo `displayHook` del file principale del modulo.
-   **Template Front-office (`views/templates/front/`)**:

    -   Nessuno. La visualizzazione del front-office è gestita tramite `hook/progress.tpl`.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    -   Il modulo non crea tabelle SQL personalizzate. Tutte le impostazioni di configurazione sono memorizzate nella tabella standard di PrestaShop `ps_configuration`, utilizzando chiavi prefissate con `SMARTFREESHIPPINGFREE_` (es. `SMARTFREESHIPPINGFREE_ENABLED`, `SMARTFREESHIPPINGFREE_THRESHOLD`).
-   **Tabella degli hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina, o all'inizio del `<body>`. | Utilizzato per iniettare risorse CSS/JS e potenzialmente renderizzare la barra di avanzamento nell'intestazione. |
| `displayLeftColumn` | Nella colonna sinistra del tema. | Posizione alternativa per visualizzare la barra di avanzamento. |
| `displayRightColumn` | Nella colonna destra del tema. | Posizione alternativa per visualizzare la barra di avanzamento. |
| `displayFooter` | Nella sezione del piè di pagina del tema. | Posizione alternativa, meno intrusiva, per visualizzare la barra di avanzamento. |
| `displayProductButtons` (o simile) | Sulla pagina del prodotto, spesso vicino al pulsante "aggiungi al carrello". | Posizionamento specifico per incoraggiare l'aggiunta di articoli direttamente dalle pagine dei prodotti. |
| `actionCartSave` | Dopo che un carrello viene salvato (es. articolo aggiunto/rimosso). | Hook interno (non per la visualizzazione) utilizzato dal modulo per attivare gli aggiornamenti AJAX per la barra di avanzamento. |
| `actionFrontControllerSetMedia` | Prima che un controller frontale renderizzi il suo output, per aggiungere CSS/JS. | Utilizzato per registrare `front.js` e `front.css` per le pagine del front-office. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo "Barra di avanzamento spedizione gratuita", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema tecnico o domanda.
