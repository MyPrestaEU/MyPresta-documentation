---
title: "Accessori nell'elenco dei prodotti - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Accessori nell'elenco dei prodotti' di MyPresta.eu."
sidebar:
  label: "Accessori nell'elenco dei prodotti - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Accessories on list of products su MyPresta.eu](https://mypresta.eu/modules/front-office-features/accessories-on-list-of-products.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/accessories-on-list-of-products/)
>
> ---


# Accessori nell'elenco dei prodotti

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste da PrestaShop stesso e sono sufficienti per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, fai clic sul pulsante "Configura" accanto al modulo "Accessori nell'elenco dei prodotti" in Gestione moduli. Questo ti porterà alla schermata di configurazione principale.

| Impostazione / Opzione | Cosa fa questa impostazione | Effetto della modifica di questa impostazione | Valore consigliato | Scenario / esempio del commerciante |
| --- | --- | --- | --- | --- |
| **Correggi bug tema classic** | Questa impostazione risolve un problema di visualizzazione specifico che può verificarsi con il tema Classic predefinito di PrestaShop o temi basati su di esso, dove gli accessori potrebbero non essere renderizzati correttamente. | *Quando abilitato:* Il modulo applica una correzione per garantire che gli accessori vengano visualizzati correttamente negli elenchi di prodotti, specialmente con il tema Classic. *Quando disabilitato:* La correzione non viene applicata. Se stai utilizzando il tema Classic o un derivato, gli accessori potrebbero non essere visualizzati correttamente o potrebbero presentare problemi di layout. | **SÌ** (Se usi il tema Classic o un tema basato su di esso) / **NO** (Se usi un tema completamente personalizzato e non riscontri problemi) | Se hai installato il modulo e gli accessori non vengono visualizzati o sembrano danneggiati nelle tue pagine di categoria, abilitare questa impostazione è il primo passo per la risoluzione dei problemi, specialmente se sei sul tema Classic. Se il tuo tema è fortemente personalizzato e non mostra questo bug, potresti mantenerlo disabilitato per evitare potenziali conflitti, anche se è generalmente sicuro abilitarlo. |
| **Abilitato / Disabilitato** | Questo è l'interruttore principale per attivare o disattivare la funzionalità del modulo in tutto il tuo negozio. | *Quando abilitato:* Il modulo visualizzerà attivamente gli accessori nelle pagine di elenco prodotti come descritto. *Quando disabilitato:* La funzionalità del modulo è completamente disattivata e nessun accessorio apparirà negli elenchi di prodotti. | **Abilitato** | Hai finito di impostare i tuoi accessori per i prodotti e vuoi che appaiano nel tuo negozio live. Lo abiliteresti. Se hai bisogno di nascondere temporaneamente gli accessori per manutenzione o una campagna speciale, lo disabiliteresti. |

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | Correggi bug tema classic | SÌ (per gli utenti del tema Classic) | Risolve i problemi di visualizzazione degli accessori negli elenchi di prodotti con il tema Classic. |
| Pagina di configurazione del modulo | Abilitato / Disabilitato | Abilitato | Attiva o disattiva la funzionalità principale del modulo. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Gli accessori non vengono visualizzati nelle mie pagine di elenco prodotti.**
R:

1.  **Controlla lo stato del modulo**: Assicurati che il modulo sia "Abilitato" nella sua configurazione.
2.  **Controlla l'assegnazione degli accessori**: Verifica che i prodotti principali abbiano effettivamente accessori assegnati nella pagina di modifica del prodotto di PrestaShop (sotto la scheda "Accessori").
3.  **Compatibilità del tema**: Se stai utilizzando un tema personalizzato, potrebbe sovrascrivere il modello standard dell'elenco prodotti in un modo che impedisce al modulo di agganciarsi correttamente. Prova ad abilitare l'impostazione "Correggi bug tema classic", anche se non sei sul tema Classic, poiché potrebbe risolvere alcuni problemi di visualizzazione generali.
4.  **Svuota la cache**: Vai su **Parametri avanzati > Prestazioni** e fai clic su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). A volte, la cache di PrestaShop deve essere aggiornata per riflettere le nuove modifiche del modulo.

**D: Gli accessori sembrano strani o sono disallineati nel mio negozio.**
R:

1.  **"Correggi bug tema classic"**: Prova ad abilitare questa impostazione nella configurazione del modulo. Risolve specificamente i problemi di layout.
2.  **Conflitto CSS del tema**: Il CSS del tuo tema potrebbe essere in conflitto con lo stile del modulo. Questo spesso richiede a un webmaster o sviluppatore di ispezionare il CSS e apportare modifiche.
3.  **Svuota la cache**: Svuota sempre la cache di PrestaShop dopo aver apportato modifiche alla configurazione.

**D: Posso controllare quali accessori appaiono per prodotti specifici?**
R: Sì, il modulo utilizza la funzione nativa di assegnazione degli accessori di PrestaShop. Per aggiungere o rimuovere accessori per un prodotto, vai su **Catalogo > Prodotti**, modifica il prodotto desiderato e naviga alla scheda "Accessori". Qui puoi cercare e aggiungere/rimuovere prodotti associati.

**D: Questo modulo rallenta il mio negozio?**
R: Il modulo è progettato per essere efficiente. Sfrutta i dati degli accessori esistenti di PrestaShop. Tuttavia, se hai migliaia di prodotti, ognuno con decine di accessori, e le risorse del tuo server sono limitate, qualsiasi caricamento di dati aggiuntivo può avere un impatto minore. Per la maggior parte dei negozi, l'impatto sulle prestazioni è trascurabile.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Accessori nell'elenco dei prodotti" (`accol`) è un modulo PrestaShop standard focalizzato principalmente sulla visualizzazione front-office. Estende `Module` e sfrutta il sistema di hook di PrestaShop per iniettare dati e rendering degli accessori nei modelli di elenco prodotti esistenti. Non introduce nuove tabelle di database o controller personalizzati complessi, rendendolo leggero e focalizzato sul suo scopo di visualizzazione. La logica del modulo è contenuta nel suo file PHP principale, con JS e CSS associati per lo stile e l'interazione.

### 4.2 Controller (`controllers/`)

-   **Controller Front-Office**: Nessuno. Il modulo inietta il suo contenuto direttamente nei modelli di elenco prodotti esistenti tramite hook.
-   **Controller Admin Back-Office**: Nessuno. La configurazione è gestita direttamente tramite il metodo `getContent()` nel file principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

-   Il modulo non definisce alcuna classe personalizzata nella directory `classes/`. Tutta la logica principale risiede nel file principale del modulo `accol.php`.
-   Interagisce con i metodi standard `Product` e `Product::getAccessories()` di PrestaShop per recuperare i dati degli accessori.

### 4.4 Risorse JavaScript (`views/js/`)

-   **`accol/js/accol.js`**
    -   **Ambito**: Front-office.
    -   **Scopo**: Questo script è responsabile della gestione della visualizzazione dinamica e delle potenziali interazioni con gli elenchi di accessori. Potrebbe includere logica per caroselli reattivi (se implementati), mostrare/nascondere blocchi di accessori o chiamate AJAX per aggiungere accessori al carrello (anche se la funzione principale del modulo è la visualizzazione, non l'aggiunta diretta al carrello tramite AJAX). È probabile che venga caricato tramite l'hook `displayHeader` o `header`.
    -   **Dettagli**: Potrebbe associare listener di eventi agli elementi degli accessori, gestire la loro visibilità o inizializzare qualsiasi libreria di terze parti utilizzata per caroselli o slider se il modulo implementa tali funzionalità per la visualizzazione degli accessori.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`accol/css/accol.css`**
    -   **Ambito**: Stile del cliente front-office.
    -   **Scopo**: Questo foglio di stile fornisce lo stile visivo necessario per gli elenchi di accessori visualizzati nelle pagine dei prodotti.
    -   **Componenti e contenitori UI principali**: Stila il contenitore per gli accessori, i singoli articoli accessori (immagini, nomi, prezzi) ed eventualmente qualsiasi elemento di navigazione (come le frecce per i caroselli).
    -   **Selettori di classe CSS chiave**: Gli sviluppatori possono aspettarsi selettori come `.accol-accessories-list`, `.accol-accessory-item`, `.accol-accessory-image`, `.accol-accessory-name`, ecc., che possono essere sovrascritti nel `custom.css` o `theme.css` di un tema personalizzato per adattarsi all'estetica del tema.

### 4.6 Struttura del modello Smarty (`views/templates/`)

-   **Modelli di hook (`views/templates/hook/`)**:
    -   `accol/accol.tpl`: Questo è il modello front-office primario responsabile del rendering dell'elenco di accessori per un dato prodotto. È probabile che sia agganciato a `displayProductListReviews` o a un hook simile che consente di iniettare contenuto nel ciclo degli elementi dell'elenco prodotti. Riceve un array di prodotti accessori e li itera per visualizzare le loro immagini, nomi ed eventualmente prezzi.
-   **Modelli di amministrazione (`views/templates/admin/`)**:
    -   `accol/admin.tpl`: Questo modello viene utilizzato per la pagina di configurazione del modulo nel Back Office di PrestaShop. Contiene gli elementi del modulo HTML per le impostazioni "Correggi bug tema classic" e "Abilitato/Disabilitato", insieme a eventuali messaggi informativi o pulsanti di salvataggio.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**: Il modulo non crea tabelle di database personalizzate. Si basa sulla tabella nativa `ps_product_accessory` di PrestaShop (che collega i prodotti ai loro accessori) e su `ps_configuration` per le proprie impostazioni (`ACCOL_FIX`).
-   **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina front-office. | Utilizzato per caricare risorse CSS (`accol.css`) e JavaScript (`accol.js`) per la visualizzazione front-office. |
| `displayProductListReviews` | All'interno del ciclo degli elementi dell'elenco prodotti, tipicamente sotto le informazioni principali del prodotto. | L'hook principale utilizzato per iniettare il modello `accol.tpl`, rendendo gli accessori per ogni prodotto nell'elenco. Questo hook è spesso disponibile in `product-list.tpl` o modelli simili. |
| `header` | (Alias per `displayHeader` in molti contesti, specialmente nelle versioni precedenti di PrestaShop). | Stesso scopo di `displayHeader` – caricamento delle risorse. |
| `actionFrontControllerSetMedia` | Eseguito quando un controller front-end sta impostando le sue risorse multimediali. | Può essere utilizzato per aggiungere condizionalmente CSS/JS in base al contesto della pagina corrente, garantendo che le risorse vengano caricate solo quando necessario. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Accessori nell'elenco dei prodotti", fai riferimento al tuo account cliente su MyPresta.eu. Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e compatibilità del modulo.
