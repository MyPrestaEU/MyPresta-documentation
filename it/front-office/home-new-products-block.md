---
title: "Blocco nuovi prodotti in homepage - Manuale per il commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Blocco nuovi prodotti in homepage di MyPresta.eu."
sidebar:
  label: "Blocco nuovi prodotti in homepage - Manuale per il commerciante e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Home new products block su MyPresta.eu](https://mypresta.eu/modules/front-office-features/home-new-products-block.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/home-new-products-block/)
>
> ---


# Blocco nuovi prodotti in homepage

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Non sono necessarie configurazioni speciali del server oltre a un ambiente di hosting PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo "Blocco nuovi prodotti in homepage" per accedere alle sue impostazioni.

#### Impostazione: Numero di prodotti da visualizzare

-   **Cosa fa questa impostazione:** Questo campo ti permette di controllare quanti dei tuoi prodotti più recenti verranno mostrati nel blocco sulla tua homepage.
-   **Effetto della modifica di questa impostazione:**
    -   *Se impostato su un numero più alto (es. 10):* Più nuovi prodotti saranno visibili nel blocco, offrendo ai clienti una selezione più ampia dei tuoi ultimi articoli. Questo potrebbe rendere il blocco più lungo o richiedere più scorrimento.
    -   *Se impostato su un numero più basso (es. 4):* Verranno visualizzati meno nuovi prodotti, rendendo il blocco più compatto. Questo può essere utile se hai spazio limitato o vuoi evidenziare solo gli articoli più freschi.
-   **Valore consigliato:** Un buon punto di partenza è `8` o `12` prodotti. Questo fornisce una selezione decente senza sovraccaricare la pagina.
-   **Scenario / esempio per il commerciante:** Se gestisci un negozio di moda e aggiungi 20 nuovi articoli ogni settimana, impostare questo valore a `12` assicura che una buona varietà sia sempre visibile. Se aggiungi solo pochi nuovi prodotti artigianali ogni mese, `4` o `6` potrebbero essere più appropriati per mantenere il blocco conciso.

#### Impostazione: Visualizza sulla homepage

-   **Cosa fa questa impostazione:** Questo è un semplice interruttore ON/OFF che controlla se il "Blocco nuovi prodotti in homepage" è visibile sulla homepage del tuo negozio.
-   **Effetto della modifica di questa impostazione:**
    -   *Se abilitato (SÌ):* Il blocco con i tuoi nuovi prodotti apparirà sulla tua homepage, come descritto nella Sezione 2.
    -   *Se disabilitato (NO):* Il blocco sarà nascosto dalla tua homepage. Questo potrebbe essere utile se desideri rimuoverlo temporaneamente senza disinstallare il modulo, o se preferisci utilizzare altri metodi per mostrare i nuovi prodotti.
-   **Valore consigliato:** `SÌ` (Abilitato). Lo scopo principale di questo modulo è visualizzare i nuovi prodotti sulla homepage.
-   **Scenario / esempio per il commerciante:** Potresti disabilitarlo temporaneamente se stai conducendo una campagna stagionale speciale che richiede tutto lo spazio della homepage per banner promozionali, e poi riabilitarlo una volta terminata la campagna.

### 2.2 Tabella di riferimento rapido per la configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | Numero di prodotti da visualizzare | 8-12 | Controlla quanti nuovi prodotti appaiono nel blocco. Un numero più alto ne mostra di più, un numero più basso lo rende più compatto. |
| Pagina di configurazione del modulo | Visualizza sulla homepage | SÌ | Attiva/disattiva la visibilità del blocco nuovi prodotti sulla tua homepage. |

## 3. Risoluzione dei problemi per il commerciante e Domande frequenti (FAQ)

**D: Il mio blocco nuovi prodotti non viene visualizzato sulla homepage dopo l'installazione.**
R:

1.  **Controlla la configurazione del modulo:** Vai su **Moduli > Gestione moduli**, trova "Blocco nuovi prodotti in homepage" e clicca su "Configura". Assicurati che "Visualizza sulla homepage" sia impostato su `SÌ`.
2.  **Svuota la cache:** A volte la cache di PrestaShop impedisce che le modifiche appaiano immediatamente. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" nell'angolo in alto a destra.
3.  **Controlla la posizione dell'hook:** Sebbene il modulo sia progettato per agganciarsi automaticamente, a volte conflitti con il tema o altri moduli possono interferire. Vai su **Design > Posizioni**. Cerca `displayHome` (o `displayHomeTabContent` se il tuo tema utilizza le schede). Assicurati che `home-new-products-block` sia elencato e abilitato all'interno di uno di questi hook. In caso contrario, potrebbe essere necessario "Trapiantare un modulo" su `displayHome`.

**D: Il blocco mostra prodotti vecchi, non nuovi.**
R: Il modulo visualizza i prodotti in base alla loro "data di aggiunta" in PrestaShop. Assicurati che quando aggiungi nuovi prodotti, la loro data di creazione sia impostata correttamente sulla data corrente. Se hai importato prodotti con date vecchie, potrebbero non apparire come "nuovi". Potrebbe essere necessario aggiornare manualmente il campo `date_add` per quei prodotti nel tuo database (operazione avanzata, consulta uno sviluppatore) o riaggiungerli.

**D: Voglio cambiare la posizione del blocco sulla mia homepage (ad esempio, più in alto o in una colonna).**
R: Puoi regolare la posizione del modulo utilizzando la funzione "Live Edit" integrata di PrestaShop.

1.  Vai su **Design > Posizioni**.
2.  Clicca sul pulsante "Avvia Live Edit" (solitamente in alto a destra).
3.  Naviga sulla tua homepage.
4.  Dovresti vedere i contorni intorno a vari blocchi del modulo. Trova il "Blocco nuovi prodotti in homepage" e trascinalo nella posizione desiderata. Puoi anche utilizzare il pulsante "Trapianta un modulo" per spostarlo in un hook diverso (ad esempio, `displayLeftColumn`, `displayRightColumn`, `displayFooter`).

**D: Il blocco ha un aspetto strano o non corrisponde allo stile del mio tema.**
R: Questo modulo utilizza i template di visualizzazione dei prodotti standard di PrestaShop, che dovrebbero ereditare la maggior parte dello stile del tuo tema. Se l'aspetto è strano:

1.  **Svuota la cache:** Come sopra, svuota la cache di PrestaShop.
2.  **Sovrascritture del tema:** Il tuo tema potrebbe avere CSS specifici che entrano in conflitto. Questo di solito richiede a uno sviluppatore web di ispezionare il CSS del tuo sito e potenzialmente aggiungere stili personalizzati al file `custom.css` del tuo tema o equivalente per sovrascrivere il valore predefinito.
3.  **Aggiornamento del modulo:** Assicurati di avere l'ultima versione del modulo da MyPresta.eu.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Blocco nuovi prodotti in homepage" è un modulo PrestaShop semplice che segue la struttura standard dei moduli. Utilizza principalmente la classe `Module` per gestire il suo ciclo di vita (installazione, disinstallazione) e i metodi `hook` per renderizzare il contenuto nel front office. Recupera i dati dei prodotti direttamente dalle tabelle del database core di PrestaShop, sfruttando le funzionalità esistenti di `Product` e `Category`. Non ci sono controller personalizzati o ObjectModels complessi, il che lo rende leggero e facile da integrare.

### 4.2 Controller (`controllers/`)

-   Questo modulo **non** contiene controller Front-Office o Back-Office personalizzati. Tutta la logica è incapsulata all'interno del file del modulo principale ed eseguita tramite hook.

### 4.3 Classi e modelli core (`classes/`)

-   Questo modulo **non** contiene classi o ObjectModels personalizzati in una directory `classes/`. Si basa sulle classi core `Product` e `Category` di PrestaShop per il recupero dei dati.

### 4.4 Risorse JavaScript (`views/js/`)

-   Questo modulo **non** include file JavaScript personalizzati. Qualsiasi comportamento dinamico (ad esempio, caroselli) sarebbe tipicamente gestito dal JS esistente del tema o da un modulo separato.

### 4.5 Fogli di stile CSS (`views/css/`)

-   Questo modulo **non** include file CSS personalizzati. Si basa sullo stile predefinito del tema per elenchi e griglie di prodotti. Gli sviluppatori che desiderano stilizzare specificamente questo blocco dovrebbero mirare alla sua struttura HTML (ad esempio, `div#home_new_products`) nel file `custom.css` del loro tema o equivalente.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   Questo modulo utilizza principalmente un singolo file di template per renderizzare il suo contenuto.

    -   **Template degli hook (`views/templates/hook/`)**:
        -   `views/templates/hook/home-new-products-block.tpl`: Questo è il file di template principale responsabile del rendering del blocco di nuovi prodotti sulla homepage.
            -   **Hook:** Principalmente destinato a `displayHome` (o `displayHomeTabContent` in alcuni temi).
            -   **Scopo:** Itera attraverso la variabile `$products` (un array di oggetti `Product`) passata dal metodo `hookDisplayHome` e visualizza l'immagine, il nome, il prezzo e il pulsante "Aggiungi al carrello" di ogni prodotto, tipicamente utilizzando un ciclo e includendo un template standard per l'elemento della lista prodotti (ad esempio, `product-miniature.tpl` o simile, a seconda della versione di PrestaShop e del tema).

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**:

    -   Questo modulo **non** crea tabelle di database personalizzate.
    -   Memorizza le sue impostazioni di configurazione (ad esempio, `HOME_NEW_PRODUCTS_NBR`, `HOME_NEW_PRODUCTS_DISPLAY`) nella tabella standard `ps_configuration`.
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHome` | Renderizza il contenuto nell'area principale della homepage. | Visualizza il blocco dei nuovi prodotti sulla homepage del negozio. |
| `displayHeader` | Eseguito nella sezione `<head>` di ogni pagina. | Utilizzato per registrare risorse (CSS/JS) se presenti, anche se questo modulo non lo usa per questo. Potrebbe essere usato per meta tag o altri elementi globali. |
| `displayLeftColumn` | Renderizza il contenuto nella barra laterale sinistra. | Permette di spostare il blocco dei nuovi prodotti nella colonna sinistra tramite "Design > Posizioni". |
| `displayRightColumn` | Renderizza il contenuto nella barra laterale destra. | Permette di spostare il blocco dei nuovi prodotti nella colonna destra tramite "Design > Posizioni". |
| `displayFooter` | Renderizza il contenuto nel footer del negozio. | Permette di spostare il blocco dei nuovi prodotti nel footer tramite "Design > Posizioni". |
| `actionProductAdd` | Eseguito dopo l'aggiunta di un nuovo prodotto. | Potrebbe essere utilizzato per svuotare la cache o re-indicizzare, anche se non esplicitamente utilizzato da questo modulo. |
| `actionProductUpdate` | Eseguito dopo l'aggiornamento di un prodotto. | Potrebbe essere utilizzato per svuotare la cache o re-indicizzare, anche se non esplicitamente utilizzato da questo modulo. |
| `actionProductDelete` | Eseguito dopo l'eliminazione di un prodotto. | Potrebbe essere utilizzato per svuotare la cache o re-indicizzare, anche se non esplicitamente utilizzato da questo modulo. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Blocco nuovi prodotti in homepage", fai riferimento al tuo account cliente MyPresta.eu. Puoi scaricare le versioni più recenti e accedere alle risorse di supporto direttamente da [MyPresta.eu](https://mypresta.eu).
