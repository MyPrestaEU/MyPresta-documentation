---
title: "Filtro UPC nell'elenco prodotti nel back office - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Filtro UPC nell'elenco prodotti nel back office' di MyPresta.eu."
sidebar:
  label: "Filtro UPC nell'elenco prodotti nel back office - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo UPC filter on products list in back office su MyPresta.eu](https://mypresta.eu/modules/administration-tools/upc-filter-on-products-list-in-back-office.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/upc-filter-on-products-list-in-back-office/)
>
> ---


# Filtro UPC nell'elenco prodotti nel back office

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono generalmente sufficienti. Non sono richieste configurazioni speciali del server oltre a un ambiente di hosting PrestaShop standard.

## 2. Panoramica completa della configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questo modulo è progettato per essere plug-and-play. Non ha una schermata di configurazione dedicata con impostazioni da regolare. Una volta installato, il modulo integra automaticamente la colonna e il filtro UPC nell'elenco dei prodotti nel back office.

Troverai la nuova funzionalità navigando su:
**Back Office > Catalogo > Prodotti**

In questa pagina, vedrai ora:

-   Una nuova colonna etichettata "UPC" che visualizza il codice UPC per ogni prodotto.
-   Un nuovo campo filtro nella parte superiore della colonna "UPC", che ti consente di digitare un codice UPC (o parte di esso) per filtrare l'elenco dei prodotti.

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho installato il modulo, ma non vedo la colonna o il filtro UPC nel mio elenco prodotti.**
R:
\* **Svuota la cache:** La soluzione più comune è svuotare la cache di PrestaShop. Vai su **Parametri avanzati > Prestazioni** e fai clic su "Svuota la cache" nell'angolo in alto a destra.
\* **Controlla lo stato del modulo:** Assicurati che il modulo sia abilitato. Vai su **Moduli > Gestione moduli**, cerca "Filtro UPC nell'elenco prodotti nel back office" e verifica che sia attivo.
\* **Compatibilità del tema:** Sebbene raro per i moduli di back-office, un tema di amministrazione altamente personalizzato *potrebbe* potenzialmente interferire. Se svuotare la cache non funziona, passa temporaneamente al tema di amministrazione predefinito di PrestaShop per vedere se la colonna appare.
\* **Posizione del modulo:** Questo modulo modifica i modelli esistenti. Assicurati che il modulo sia installato correttamente e non mostri errori durante l'installazione.

**D: La colonna UPC è presente, ma alcuni prodotti non mostrano un UPC.**
R: Questo modulo visualizza semplicemente il codice UPC già memorizzato nelle informazioni del tuo prodotto. Se un prodotto non mostra un UPC, significa che il campo UPC per quel prodotto specifico nel tuo catalogo PrestaShop è vuoto. Dovrai modificare il prodotto (Catalogo > Prodotti > Modifica Prodotto > scheda Quantità) e inserire il codice UPC lì.

**D: Posso cambiare la posizione della colonna UPC?**
R: Il modulo integra la colonna UPC in una posizione specifica all'interno della tabella dell'elenco prodotti. Non esiste un'opzione di configurazione all'interno del modulo per cambiarne la posizione. Ciò richiederebbe modifiche personalizzate al modello (vedi Guida per sviluppatori).

**D: Questo modulo aggiunge campi UPC ai prodotti se non esistono?**
R: No, questo modulo presuppone che la tua installazione di PrestaShop abbia già il campo UPC standard disponibile per i prodotti (cosa che fa per impostazione predefinita). Visualizza e filtra solo in base ai dati che hai già inserito in quel campo.

**D: Questo modulo rallenterà il mio back office?**
R: Il modulo è altamente ottimizzato. Sfrutta i meccanismi di filtraggio esistenti di PrestaShop e aggiunge solo una semplice visualizzazione della colonna. Non dovrebbe influire in modo significativo sulle prestazioni dell'elenco prodotti del tuo back office.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata per sviluppatori e webmaster che desiderano comprendere, eseguire il debug o estendere il modulo "Filtro UPC nell'elenco prodotti nel back office".

### 4.1 Panoramica dell'architettura

Il modulo funziona principalmente sovrascrivendo specifici modelli Twig utilizzati per l'elenco del catalogo prodotti nel back office di PrestaShop. Inietta l'HTML necessario per l'intestazione della colonna UPC e l'input del filtro, quindi modifica il modello della riga del prodotto per visualizzare il valore UPC. La logica di filtraggio è gestita dal controller nativo `AdminProducts` di PrestaShop, che riconosce automaticamente il campo `upc` per il filtraggio una volta che è presente nel modello.

### 4.2 Controller (`controllers/`)

Questo modulo **non** introduce alcun controller front-office o back-office personalizzato. La sua funzionalità è ottenuta tramite override di modelli e sfruttando la logica del controller PrestaShop esistente.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo **non** introduce alcuna classe PHP personalizzata o definizione di `ObjectModel`. Interagisce direttamente con i dati dei prodotti PrestaShop esistenti.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo **non** include alcun file JavaScript personalizzato. La funzionalità di filtraggio è gestita lato server dal controller `AdminProducts` di PrestaShop.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo **non** include alcun file CSS personalizzato. Si basa sullo stile predefinito del back-office di PrestaShop.

### 4.6 Struttura del modello Smarty (`views/templates/`)

Questo modulo utilizza il nuovo motore di templating Twig introdotto in PrestaShop 1.7+ per le pagine del back-office. Sovrascrive due modelli principali dell'elenco prodotti:

-   **`upcmypresta/views/PrestaShop/Admin/Product/CatalogPage/Lists/list.html.twig`**

    -   **Scopo:** Questo modello è responsabile del rendering della pagina principale del catalogo prodotti, inclusa l'intestazione della tabella e il modulo di ricerca/filtro.
    -   **Modifica:** Il modulo inietta un nuovo elemento `<th>` per la colonna "UPC" nell'intestazione della tabella e un campo di input corrispondente per il filtraggio nel modulo di ricerca. Ciò consente al campo `upc` di essere riconosciuto dal controller `AdminProducts` per il filtraggio.
-   **`upcmypresta/views/PrestaShop/Admin/Product/CatalogPage/Lists/products_table.html.twig`**

    -   **Scopo:** Questo modello è responsabile del rendering delle singole righe della tabella dell'elenco prodotti.
    -   **Modifica:** Il modulo aggiunge un nuovo elemento `<td>` all'interno del ciclo del prodotto per visualizzare il valore `product.upc` per ogni prodotto.

### 4.7 Schema del database e Mappa degli hook

-   **Tabelle del database**: Questo modulo **non** crea alcuna tabella del database personalizzata. Legge il campo `upc` dalla tabella standard `ps_product`.
-   **Tabella degli hook registrati**: Questo modulo **non** registra alcun hook specifico nel senso tradizionale di PrestaShop (ad esempio, `displayHeader`, `actionValidateOrder`). La sua integrazione è ottenuta puramente tramite override dei modelli Twig, che sono una forma di "hooking" implicito nel processo di rendering.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Filtro UPC nell'elenco prodotti nel back office", fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda relativa alla funzionalità del modulo.
