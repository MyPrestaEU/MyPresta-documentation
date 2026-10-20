---
title: "Scorri in basso - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Scorri in basso di MyPresta.eu."
sidebar:
  label: "Scorri in basso - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Scroll to bottom su MyPresta.eu](https://mypresta.eu/modules/front-office-features/scroll-to-bottom.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/scroll-to-bottom/)
>
> ---


# Scorri in basso

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale e unica per il modulo "Scorri in basso". Puoi accedervi navigando su **Moduli > Gestione moduli** e cercando "Scorri in basso", quindi cliccando sul pulsante "Configura".

#### Impostazioni e Opzioni

-   **Colore del pulsante (st\_color)**

    *   **Cosa fa questa impostazione:** Ti permette di definire il colore del pulsante "Scorri in basso". Puoi usare nomi di colori HTML standard (come `red`, `blue`, `green`) o codici colore esadecimali (come `#FF0000` per il rosso, `#0000FF` per il blu).
    *   **Effetto della modifica di questa impostazione:**
        *   *Se impostato su un colore specifico (es. `#007bff`):* Il pulsante verrà visualizzato in quel colore esatto sul tuo front office.
        *   *Se lasciato vuoto o non valido:* Il pulsante probabilmente tornerà a un colore predefinito definito dal CSS del modulo, che potrebbe non corrispondere al tuo brand.
    *   **Valore consigliato:** Scegli un colore che si abbini al design del tuo negozio e sia chiaramente visibile sullo sfondo, ma non eccessivamente distraente. Usa il colore primario o secondario del tuo brand.
    *   **Scenario / esempio per il commerciante:** Se il tuo brand usa molto blu scuro, impostarlo su `#000080` (blu navy) farebbe sì che il pulsante si integri bene pur rimanendo funzionale.
-   **Posizione X del pulsante (st\_x)**

    *   **Cosa fa questa impostazione:** Controlla la posizione orizzontale del pulsante sullo schermo. Determina quanto lontano dal bordo destro della finestra del browser apparirà il pulsante. Il valore è tipicamente in pixel.
    *   **Effetto della modifica di questa impostazione:**
        *   *Se impostato su un valore inferiore (es. `20`):* Il pulsante sarà più vicino al bordo destro dello schermo.
        *   *Se impostato su un valore superiore (es. `80`):* Il pulsante sarà più lontano dal bordo destro, spostandosi verso il centro dello schermo.
    *   **Valore consigliato:** `20` o `30` pixel è un posizionamento comune e discreto. Lo mantiene fuori dall'area del contenuto principale ma comunque facilmente accessibile.
    *   **Scenario / esempio per il commerciante:** Se hai altri elementi fissi sul lato destro dello schermo (come un widget di chat), potresti dover aumentare questo valore a `50px` per evitare che il pulsante "Scorri in basso" si sovrapponga.
-   **Posizione Y del pulsante (st\_y)**

    *   **Cosa fa questa impostazione:** Controlla la posizione verticale del pulsante sullo schermo. Determina quanto lontano dal bordo superiore della finestra del browser apparirà il pulsante. Il valore è tipicamente in pixel.
    *   **Effetto della modifica di questa impostazione:**
        *   *Se impostato su un valore inferiore (es. `20`):* Il pulsante sarà più vicino al bordo superiore dello schermo.
        *   *Se impostato su un valore superiore (es. `80`):* Il pulsante sarà più in basso rispetto al bordo superiore.
    *   **Valore consigliato:** `20` o `30` pixel è un buon punto di partenza. Lo posiziona nell'angolo in alto a destra senza essere troppo in alto o troppo in basso.
    *   **Scenario / esempio per il commerciante:** Se l'intestazione del tuo negozio è molto alta o hai un pulsante "Scorri in alto" anch'esso nell'angolo in alto a destra, potresti regolarlo a `60px` o `70px` per assicurarti che entrambi i pulsanti abbiano spazio sufficiente e non si sovrappongano.
-   **Opacità del pulsante (st\_o)**

    *   **Cosa fa questa impostazione:** Controlla la trasparenza del pulsante. I valori di opacità vanno da `0` (completamente trasparente/invisibile) a `1` (completamente opaco/solido). Puoi usare valori decimali come `0.5` per il 50% di trasparenza.
    *   **Effetto della modifica di questa impostazione:**
        *   *Se impostato su `1`:* Il pulsante sarà completamente visibile e solido.
        *   *Se impostato su `0.5`:* Il pulsante sarà semi-trasparente, permettendo al contenuto di sfondo di trasparire.
        *   *Se impostato su `0`:* Il pulsante sarà invisibile (anche se ancora cliccabile se sai dove si trova).
    *   **Valore consigliato:** `0.8` o `0.9` è spesso un buon equilibrio. Rende il pulsante leggermente meno invadente pur essendo chiaramente visibile. `1` è anche perfettamente accettabile se vuoi che risalti di più.
    *   **Scenario / esempio per il commerciante:** Se trovi il pulsante troppo prominente o distraente, ridurne l'opacità a `0.7` può farlo integrare più sottilmente nel design del tuo negozio senza perdere la sua funzionalità.

#### Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Colore del pulsante (st\_color) | `#007bff` (esempio) | Imposta il colore del pulsante. Influisce sulla visibilità e sulla coerenza del brand. |
| Configurazione modulo | Posizione X del pulsante (st\_x) | `20` | Distanza orizzontale dal bordo destro. Previene la sovrapposizione con altri elementi. |
| Configurazione modulo | Posizione Y del pulsante (st\_y) | `20` | Distanza verticale dal bordo superiore. Posiziona chiaramente il pulsante. |
| Configurazione modulo | Opacità del pulsante (st\_o) | `0.8` | Trasparenza del pulsante. Controlla quanto appare invadente o discreto. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

-   **D: Il pulsante non appare nel mio negozio.**
    *   **R:** Innanzitutto, assicurati che il modulo sia installato e abilitato in **Moduli > Gestione moduli**. Quindi, controlla la pagina di configurazione del modulo per assicurarti che tutte le impostazioni siano state salvate. Se non appare ancora, prova a svuotare la cache di PrestaShop (**Parametri avanzati > Prestazioni > Svuota la cache**). A volte, i temi personalizzati potrebbero anche interferire; prova a passare temporaneamente al tema PrestaShop predefinito per escludere questa possibilità.
-   **D: Il pulsante appare, ma è nel posto sbagliato o ha un aspetto strano.**
    *   **R:** Vai alla pagina di configurazione del modulo. Regola le impostazioni "Posizione X" e "Posizione Y" per spostare il pulsante orizzontalmente e verticalmente. Sperimenta con diversi valori finché non si trova in una posizione soddisfacente. Per problemi di aspetto, controlla le impostazioni "Colore" e "Opacità". Se l'aspetto è ancora strano, il CSS del tuo tema potrebbe sovrascrivere gli stili del modulo.
-   **D: L'animazione di scorrimento non è fluida o non funziona.**
    *   **R:** Questo modulo utilizza JavaScript per l'effetto di scorrimento fluido. Assicurati che non ci siano errori JavaScript sul tuo sito (puoi controllare la console per sviluppatori del tuo browser per errori). Conflitti con altri moduli o JavaScript del tema personalizzato possono talvolta impedire il corretto funzionamento dell'animazione. Svuotare la cache è un buon primo passo.
-   **D: Posso cambiare l'icona del pulsante?**
    *   **R:** La versione attuale del modulo non offre un'impostazione diretta per cambiare l'icona dal back office. Ciò richiederebbe CSS personalizzato o modifiche al template (vedi la Guida per gli sviluppatori per maggiori dettagli tecnici).
-   **D: Questo modulo influisce sulle prestazioni o sulla SEO del mio negozio?**
    *   **R:** Questo modulo è molto leggero, aggiungendo CSS e JavaScript minimi. Dovrebbe avere un impatto trascurabile sulla velocità di caricamento del tuo negozio o sulla SEO. La funzionalità è puramente per l'esperienza utente e non altera il contenuto in un modo che possa influenzare l'indicizzazione dei motori di ricerca.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo "Scorri in basso" è una semplice funzionalità front-office implementata come modulo PrestaShop standard. Sfrutta principalmente il sistema di hook di PrestaShop per iniettare il suo CSS, JavaScript e la struttura HTML del pulsante nel front office. La configurazione è gestita tramite il metodo `getContent()` nel file principale del modulo, memorizzando le impostazioni in `ps_configuration`. Non ci sono controller personalizzati, ObjectModels o interazioni complesse con il database.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Nessuno. La funzionalità front-office del modulo è iniettata direttamente tramite hook.
-   **Controller Admin Back-Office**: Nessuno. La configurazione è gestita all'interno del file principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

-   Nessuno. Il modulo non definisce classi o ObjectModels personalizzati. Tutta la logica è contenuta in `scrollbottom.php`.

### 4.4 Risorse JavaScript (`views/js/`)

-   `scrollbottom/scrollbottom.js`
    *   **Ambito:** Front-office.
    *   **Responsabilità:** Questo script è responsabile della funzionalità principale del pulsante "Scorri in basso".
        *   Probabilmente ascolta il DOM per essere pronto.
        *   Allega un listener di eventi `click` all'elemento del pulsante "Scorri in basso".
        *   Quando cliccato, utilizza il metodo JavaScript `window.scrollTo()` o `element.scrollIntoView()`, spesso con `behavior: 'smooth'`, per animare lo scorrimento fino alla fine della pagina (specificamente, l'altezza massima di scorrimento dell'elemento `body` o `html`).
        *   Potrebbe anche gestire la visibilità del pulsante, facendolo apparire o scomparire in base alla posizione di scorrimento dell'utente (ad esempio, mostrare solo quando l'utente ha scorrevole una certa quantità).

### 4.5 Fogli di stile CSS (`views/css/`)

-   `scrollbottom/scrollbottom.css`
    *   **Ambito:** Stile del cliente del front-office.
    *   **Componenti e contenitori UI principali che stilizza:** Questo foglio di stile definisce l'aspetto visivo e il posizionamento del pulsante "Scorri in basso".
        *   Probabilmente si rivolgerà a un ID o una classe specifica per il pulsante (ad esempio, `#scrollbottom_button`).
        *   Definisce proprietà come `position: fixed`, `right`, `top`, `z-index`, `background-color`, `color`, `padding`, `border-radius`, `cursor` e potenzialmente `display: none` inizialmente, con JavaScript che controlla la sua visibilità.
        *   Potrebbe anche includere stili per l'icona della freccia all'interno del pulsante (ad esempio, utilizzando un'icona di font o un'immagine di sfondo).
    *   **Selettori di classi CSS chiave che gli sviluppatori possono sovrascrivere nel loro tema:** Gli sviluppatori possono ispezionare l'HTML generato per trovare l'ID/classe esatta del pulsante (ad esempio, `#scrollbottom_button`) e sovrascrivere i suoi stili nel file `custom.css` del loro tema o file equivalente per ottenere un aspetto personalizzato.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template degli hook (`views/templates/hook/`)**:

    *   `scrollbottom/adv.tpl`: Questo template è probabilmente utilizzato per visualizzare un annuncio o contenuto promozionale relativo a MyPresta.eu, spesso iniettato in un hook come `displayAdminHome` o simile, ma non direttamente correlato alla funzionalità del pulsante front-office.
    *   `scrollbottom/footer.tpl`: Questo è il template principale per il pulsante front-office.
        *   **Agganciato a:** `displayFooter` o `footer` (a seconda della versione di PrestaShop e del tema).
        *   **Output:** La struttura HTML per il pulsante "Scorri in basso", inclusi il suo ID/classe, l'icona della freccia e potenzialmente stili inline o attributi di dati derivati dalle impostazioni di configurazione del modulo (colore, posizione, opacità).
-   **Template di amministrazione (`views/templates/admin/`)**: Nessuno.
-   **Template front-office (`views/templates/front/`)**: Nessuno.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:

    *   Il modulo non crea tabelle SQL personalizzate.
    *   Le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration` utilizzando chiavi come `ST_COLOR`, `ST_X`, `ST_Y`, `ST_O`.
-   **Tabella degli hook registrati**:

| Nome dell'Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` del front office. | Utilizzato per registrare e includere i file CSS (`scrollbottom.css`) e JavaScript (`scrollbottom.js`) del modulo, assicurando che vengano caricati prima del contenuto della pagina. |
| `header` | Alias per `displayHeader` in alcuni contesti. | Come `displayHeader`. |
| `displayFooter` | Alla fine della sezione `<body>`, prima del tag di chiusura `</body>`. | Utilizzato per renderizzare il template `footer.tpl`, che contiene la struttura HTML per il pulsante "Scorri in basso". |
| `footer` | Alias per `displayFooter` in alcuni contesti. | Come `displayFooter`. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e per accedere alle ultime versioni del modulo "Scorri in basso", visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e compatibilità del modulo.
