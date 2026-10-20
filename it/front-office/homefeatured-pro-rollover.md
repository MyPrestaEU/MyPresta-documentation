---
title: "HomeFeatured Pro Rollover - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop HomeFeatured Pro Rollover di MyPresta.eu."
sidebar:
  label: "HomeFeatured Pro Rollover"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo HomeFeatured Pro Rollover su MyPresta.eu](https://mypresta.eu/modules/front-office-features/homefeatured-pro-rollover.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/homefeatured-pro-rollover/)
>
> ---


# HomeFeatured Pro Rollover

## 1. Requisiti e Compatibilità
- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti e solitamente preinstallate nella maggior parte degli ambienti di hosting web.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)
Dopo l'installazione, clicca su "Configura" accanto a "HomeFeatured Pro Rollover" in Gestione moduli per accedere alle sue impostazioni.

#### 2.1.1 Numero di prodotti da visualizzare
-   **Cosa fa questa impostazione:** Controlla quanti prodotti in evidenza verranno mostrati nella sezione "Prodotti in evidenza" sulla tua homepage.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato su un numero specifico (es. 8):* La tua homepage visualizzerà esattamente quel numero di prodotti dalla tua categoria "Home" (o qualsiasi categoria tu abbia designato per i prodotti in evidenza).
    -   *Quando impostato su un numero diverso:* Il numero di prodotti visualizzati cambierà di conseguenza. Se lo imposti troppo alto, potrebbe rendere la tua homepage molto lunga; se troppo basso, potresti non mostrare abbastanza prodotti.
-   **Valore consigliato:** Un numero che si adatta bene al layout della tua homepage, tipicamente tra 8 e 12 per una griglia standard.
-   **Scenario / esempio per il commerciante:** Se vuoi evidenziare i tuoi 8 prodotti più venduti sulla homepage, imposteresti questo valore su "8". Se hai un layout più ampio e vuoi mostrare più varietà, potresti aumentarlo a "12".

#### 2.1.2 Visualizza attributi nella pagina del prodotto
-   **Cosa fa questa impostazione:** Questa è un'impostazione standard di PrestaShop che controlla se gli attributi del prodotto (come taglia, colore) vengono visualizzati nella pagina del prodotto stessa. Sebbene questo modulo influisca principalmente sulla homepage, questa impostazione è spesso inclusa nei moduli che interagiscono con le visualizzazioni dei prodotti.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato (Sì):* Gli attributi del prodotto saranno visibili e selezionabili nelle singole pagine del prodotto.
    -   *Quando disabilitato (No):* Gli attributi del prodotto non verranno mostrati nelle pagine del prodotto, semplificando potenzialmente la pagina ma rimuovendo importanti opzioni di selezione per i clienti.
-   **Valore consigliato:** **Sì**. La maggior parte dei negozi deve visualizzare gli attributi per i prodotti con varianti.
-   **Scenario / esempio per il commerciante:** Per un negozio di abbigliamento, i clienti devono selezionare taglia e colore. Abilitando questa opzione si garantisce che tali opzioni appaiano nella pagina del prodotto. Disabilitandola, sarebbe impossibile per i clienti scegliere le varianti.

#### 2.1.3 Lingua predefinita
-   **Cosa fa questa impostazione:** Questa impostazione specifica la lingua predefinita per il tuo negozio. È un'impostazione fondamentale di PrestaShop spesso richiamata dai moduli per garantire una corretta gestione della lingua.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando impostato sulla tua lingua principale (es. Italiano):* Il modulo utilizzerà questa lingua per qualsiasi dato dipendente dalla lingua o per i fallback se le traduzioni mancano.
-   **Valore consigliato:** **La lingua principale del tuo negozio.** Questo dovrebbe corrispondere alla lingua predefinita che hai impostato nelle impostazioni di localizzazione di PrestaShop.
-   **Scenario / esempio per il commerciante:** Se il pubblico principale del tuo negozio è in Italia, imposteresti questo valore su "Italiano" per assicurarti che tutto il testo predefinito e le informazioni sul prodotto siano visualizzate correttamente in italiano.

#### 2.1.4 Numero di prodotti da visualizzare (Duplicato di 4.1.1)
-   **Cosa fa questa impostazione:** Questo è un duplicato dell'impostazione "Numero di prodotti da visualizzare" (`HOME_FEATURED_PRO_NBR`). Controlla lo stesso aspetto: quanti prodotti in evidenza appaiono sulla tua homepage.
-   **Effetto della modifica di questa impostazione:** La modifica di questo valore altererà direttamente il conteggio dei prodotti mostrati nella sezione in evidenza.
-   **Valore consigliato:** Fare riferimento alla sezione 4.1.1.
-   **Scenario / esempio per il commerciante:** Fare riferimento alla sezione 4.1.1.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
|---|---|---|---|
| Configurazione modulo | Numero di prodotti da visualizzare (`HOME_FEATURED_PRO_NBR`) | 8-12 (dipende dal layout) | Imposta il conteggio dei prodotti in evidenza sulla homepage. |
| Configurazione modulo | Visualizza attributi nella pagina del prodotto (`PS_ATTRIBUTE_CATEGORY_DISPLAY`) | Sì | Controlla la visibilità degli attributi del prodotto nelle pagine del prodotto. |
| Configurazione modulo | Lingua predefinita (`PS_LANG_DEFAULT`) | Lingua principale del tuo negozio | Specifica la lingua predefinita per il negozio. |
| Configurazione modulo | Numero di prodotti da visualizzare (`HOME_FEATURED_NBR`) | Uguale a `HOME_FEATURED_PRO_NBR` | Impostazione duplicata per il conteggio dei prodotti in evidenza. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: L'effetto rollover non funziona sulla mia homepage.**
R:
1.  **Controlla lo stato del modulo:** Assicurati che il modulo "HomeFeatured Pro Rollover" sia installato e abilitato in **Moduli > Gestione moduli**.
2.  **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). A volte, la vecchia cache impedisce la visualizzazione delle nuove modifiche del modulo.
3.  **Immagini del prodotto:** Verifica che i prodotti in evidenza abbiano effettivamente *almeno due* immagini caricate nelle loro impostazioni di prodotto (**Catalogo > Prodotti > [Modifica Prodotto] > scheda Immagini**). Il modulo necessita di una seconda immagine da visualizzare al passaggio del mouse.
4.  **Compatibilità del tema:** Sebbene il modulo sia progettato per un'ampia compatibilità, temi molto pesantemente personalizzati potrebbero richiedere piccole modifiche CSS. Se il problema persiste, contatta il supporto MyPresta.eu.

**D: La mia homepage appare danneggiata dopo l'installazione.**
R:
1.  **Azione immediata:** Se il tuo negozio diventa inutilizzabile, disabilita immediatamente il modulo da **Moduli > Gestione moduli**.
2.  **Controlla la versione di PrestaShop:** Assicurati di aver scaricato la versione corretta del modulo per la tua installazione di PrestaShop (es. versione PS 8.x per PrestaShop 8.x).
3.  **Conflitti con il tema:** Alcuni temi potrebbero avere una propria logica per i "prodotti in evidenza" che entra in conflitto. Prova a passare temporaneamente al tema predefinito di PrestaShop (Classic) per vedere se il problema si risolve. Se lo fa, il problema è legato al tema.
4.  **Contatta il supporto:** Fornisci al supporto MyPresta.eu i dettagli sulla tua versione di PrestaShop, il tema e qualsiasi messaggio di errore che vedi.

**D: Come faccio a cambiare quali prodotti sono "in evidenza"?**
R: Il modulo utilizza il meccanismo standard di PrestaShop per i "Prodotti in evidenza". Per cambiare quali prodotti appaiono:
1.  Vai su **Catalogo > Categorie**.
2.  Trova la categoria denominata "Home" (o la categoria che hai designato come categoria della tua homepage).
3.  Modifica questa categoria e vai alla scheda "Prodotti".
4.  Puoi aggiungere o rimuovere prodotti da questa categoria per controllare cosa appare nella tua sezione in evidenza.

**D: Le immagini non sono perfettamente allineate o dimensionate durante il rollover.**
R: Questo di solito indica un conflitto CSS con il tuo tema.
1.  **Dimensioni delle immagini:** Assicurati che tutte le immagini dei prodotti (specialmente la prima e la seconda) siano caricate con proporzioni coerenti e dimensioni simili. PrestaShop le ridimensiona automaticamente, ma grandi differenze possono causare spostamenti del layout.
2.  **Personalizzazione del tema:** Il CSS del tuo tema potrebbe sovrascrivere lo stile del modulo. Un webmaster può ispezionare l'elemento utilizzando gli strumenti di sviluppo del browser per identificare le regole CSS in conflitto e applicare una correzione nel file CSS personalizzato del tuo tema.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura
Il modulo HomeFeatured Pro Rollover (`homefeaturedpro`) è un modulo PrestaShop semplice progettato per sovrascrivere e migliorare la funzionalità del modulo `homefeatured` predefinito. Si concentra principalmente sulla visualizzazione del front-office, in particolare sull'iniezione di JavaScript e CSS per abilitare l'effetto di rollover dell'immagine sui prodotti in evidenza della homepage. Sfrutta il sistema di hook di PrestaShop per integrare la sua logica e i suoi template. Il modulo non introduce nuove tabelle di database o ObjectModels complessi, ma si basa sui dati di prodotto esistenti di PrestaShop.

### 4.2 Controller (`controllers/`)
Questo modulo non introduce alcun controller Front-Office o Back-Office Admin personalizzato. Tutta la configurazione è gestita tramite il metodo `getContent()` del file principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)
Questo modulo non introduce classi o ObjectModels personalizzati. Opera estendendo la funzionalità esistente di PrestaShop e rendendo i propri template.

### 4.4 Risorse JavaScript (`views/js/`)
Questo modulo non include alcun file JavaScript personalizzato. L'effetto rollover è ottenuto puramente tramite CSS.

### 4.5 Fogli di stile CSS (`views/css/`)
-   **`homefeaturedpro/homefeatured.css`**
    *   **Scopo:** Stile del front-office per il cliente.
    *   **Componenti UI principali e contenitori che stilizza:** Questo foglio di stile contiene le regole CSS principali responsabili dell'effetto di rollover dell'immagine. Si rivolge ai contenitori delle immagini dei prodotti all'interno della sezione dei prodotti in evidenza, probabilmente utilizzando selettori come `.product-container .product-image`, `.product-image-container`, o simili, per nascondere la seconda immagine per impostazione predefinita e visualizzarla al passaggio del mouse.
    *   **Selettori di classi CSS chiave che gli sviluppatori possono sovrascrivere nel loro tema:**
        *   `.product-image-container .img-hover`: Probabilmente controlla la visibilità e il posizionamento della seconda immagine.
        *   `.product-image-container .img-primary`: Controlla l'immagine principale.
        *   Stili relativi alle proprietà `transition` per cambi di immagine fluidi.
        *   `overflow: hidden` sul contenitore dell'immagine per gestire lo scambio di immagini.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **`homefeaturedpro/homefeatured.tpl`**
    *   **Scopo:** Front-office.
    *   **Hook:** Principalmente renderizzato in `displayHome` o `Home` (a seconda della versione di PrestaShop e della configurazione del tema).
    *   **Scopo:** Questo è il template principale responsabile del rendering della griglia dei prodotti in evidenza sulla homepage. Itera attraverso la variabile `$products` (passata dal metodo `hookDisplayHome` del modulo) e per ogni prodotto, genera la struttura HTML includendo le immagini primaria e secondaria, il nome del prodotto, il prezzo e altri dettagli. È progettato per funzionare con PrestaShop 1.7.x e versioni successive. La logica all'interno di questo template è cruciale per visualizzare entrambe le immagini e applicare le classi CSS necessarie per l'effetto rollover.

-   **`homefeaturedpro/homefeatured14.tpl`**
    *   **Scopo:** Front-office.
    *   **Hook:** Probabilmente destinato a versioni precedenti di PrestaShop (es. 1.4.x, 1.5.x, 1.6.x) se il modulo le supporta, o come alternativa per specifiche strutture di temi.
    *   **Scopo:** Questo template serve allo stesso scopo di `homefeatured.tpl` ma è strutturato per essere compatibile con sintassi di template e strutture HTML di PrestaShop più vecchie. Itererebbe anche attraverso i prodotti e renderebbe gli elementi immagine necessari per l'effetto rollover. Per le versioni moderne di PrestaShop (1.7+), `homefeatured.tpl` è il template principale utilizzato.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    *   Il modulo non crea tabelle di database personalizzate.
    *   Memorizza le sue impostazioni di configurazione nella tabella `ps_configuration` utilizzando le seguenti chiavi:
        *   `HOME_FEATURED_PRO_NBR`: Memorizza il numero di prodotti in evidenza da visualizzare.
        *   `PS_ATTRIBUTE_CATEGORY_DISPLAY`: (Configurazione standard di PrestaShop, potenzialmente richiamata o impostata dal modulo).
        *   `PS_LANG_DEFAULT`: (Configurazione standard di PrestaShop, potenzialmente richiamata o impostata dal modulo).
        *   `HOME_FEATURED_NBR`: (Duplicato di `HOME_FEATURED_PRO_NBR`, probabilmente per retrocompatibilità o coerenza interna).

-   **Tabella degli hook registrati**:

| Nome dell'Hook | Tempo di esecuzione | Scopo tecnico |
|---|---|---|
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Utilizzato per includere il foglio di stile CSS del modulo (`homefeatured.css`) per garantire che gli stili di rollover siano caricati prima del contenuto della pagina. |
| `header` | Alias per `displayHeader`. | Uguale a `displayHeader`. |
| `Home` | Sulla homepage, tipicamente nell'area del contenuto principale. | Renderizza il template dei prodotti in evidenza del modulo (`homefeatured.tpl` o `homefeatured14.tpl`) e gli passa i dati del prodotto. |
| `displayHome` | Alias per `Home` nelle versioni moderne di PrestaShop. | Uguale a `Home`. |

## 5. Supporto ufficiale e aggiornamenti
Per aggiornamenti ufficiali, supporto tecnico e ulteriore assistenza con il modulo HomeFeatured Pro Rollover, visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per aiutarti con qualsiasi problema o domanda tu possa avere.
