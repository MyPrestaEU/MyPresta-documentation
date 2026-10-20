---
title: "Filtro MPN nell'elenco prodotti nel back office - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Filtro MPN nell'elenco prodotti nel back office' di MyPresta.eu."
sidebar:
  label: "Filtro MPN nell'elenco prodotti nel back office - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo MPN filter on products list in back office su MyPresta.eu](https://mypresta.eu/modules/administration-tools/mpn-filter-on-products-list-in-back-office.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/mpn-filter-on-products-list-in-back-office/)
>
> ---


# Filtro MPN nell'elenco prodotti nel back office

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti e di solito abilitate per impostazione predefinita sulla maggior parte degli ambienti di hosting.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questo modulo è progettato per essere plug-and-play. Non ha una schermata di configurazione dedicata con impostazioni da regolare. Dopo l'installazione, il modulo integra automaticamente la colonna MPN e le funzionalità di filtraggio nell'elenco dei prodotti.

Vedrai un pulsante "Configura" standard dopo l'installazione, ma cliccandoci sopra di solito verrà visualizzato un semplice messaggio che indica che il modulo è attivo e non richiede ulteriori configurazioni.

**Come usare il modulo dopo l'installazione:**

1. Vai su **Catalogo > Prodotti** nel back office di PrestaShop.
2. Ora vedrai una nuova colonna etichettata "MPN" nell'elenco dei tuoi prodotti.
3. Puoi cliccare sull'intestazione della colonna "MPN" per ordinare i tuoi prodotti per MPN in ordine crescente o decrescente.
4. Sopra l'elenco dei prodotti, nella sezione filtro, troverai un nuovo campo di input sotto la colonna "MPN". Puoi digitare un MPN (o parte di un MPN) in questo campo e premere Invio o cliccare sul pulsante "Filtra" per filtrare l'elenco dei prodotti per quell'MPN.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | (Nessuna impostazione configurabile) | N/A | Il modulo funziona automaticamente dopo l'installazione, aggiungendo la colonna MPN e il filtro a Catalogo > Prodotti. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho installato il modulo, ma non vedo la colonna MPN nell'elenco dei miei prodotti.**
R: Innanzitutto, assicurati di essere nella pagina "Catalogo > Prodotti" nel back office di PrestaShop. Se non è ancora visibile, prova a svuotare la cache di PrestaShop:
1. Vai su **Parametri avanzati > Prestazioni**.
2. Clicca su "Svuota la cache" nell'angolo in alto a destra.
3. Svuota anche la cache del tuo browser.
4. Se il problema persiste, assicurati che il modulo sia abilitato in Gestione moduli.

**D: Posso usare questo modulo per aggiungere l'MPN al front office per i clienti?**
R: No, questo modulo è strettamente per l'amministrazione del back office. Non modifica il front office né visualizza gli MPN ai clienti. Avresti bisogno di un modulo separato o di uno sviluppo personalizzato per la visualizzazione dell'MPN nel front office.

**D: Questo modulo crea nuovi campi nel database per l'MPN?**
R: No, PrestaShop ha già un campo `mpn` nella tabella `ps_product`. Questo modulo rende semplicemente quel campo esistente visibile e filtrabile nell'elenco dei prodotti del back office. Non aggiunge nuove tabelle o campi al database.

**D: Il filtro non funziona o la colonna non ordina correttamente.**
R: Questo potrebbe essere un problema di cache o un conflitto con un altro modulo che modifica l'elenco dei prodotti.
1. Svuota la cache di PrestaShop (come descritto sopra).
2. Se hai altri moduli che personalizzano pesantemente la pagina "Catalogo > Prodotti", prova a disabilitarli temporaneamente uno per uno per identificare un conflitto.
3. Assicurati che la tua versione di PrestaShop sia completamente compatibile con la versione del modulo che hai scaricato.

**D: Come inserisco o modifico l'MPN per un prodotto?**
R: Modifichi l'MPN direttamente nella pagina di modifica del prodotto:
1. Vai su **Catalogo > Prodotti**.
2. Clicca su "Modifica" accanto al prodotto che desideri modificare.
3. Vai alla scheda "Quantità" (o "Impostazioni di base" nelle versioni precedenti).
4. Troverai il campo "MPN (Manufacturer Part Number)" lì. Inserisci o aggiorna il valore e salva il prodotto. Il nuovo MPN apparirà quindi nell'elenco dei prodotti.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Filtro MPN nell'elenco prodotti nel back office" è un modulo PrestaShop leggero progettato principalmente per estendere la funzionalità esistente di elencazione dei prodotti nel Back Office. Lo fa sovrascrivendo specifici template Twig responsabili del rendering della pagina del catalogo prodotti in PrestaShop 1.7.x, 8.x e 9.x. Non introduce nuovi controller, modelli o complessi asset JavaScript/CSS. La sua funzione principale è quella di iniettare la colonna MPN e il suo filtro associato nella vista standard dell'elenco prodotti.

### 4.2 Controller (`controllers/`)

Questo modulo non introduce alcun controller front-office o back-office personalizzato. Tutta la sua funzionalità è ottenuta tramite override di template e meccanismi di modulo core di PrestaShop.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo non introduce alcuna classe PHP personalizzata o definizione di `ObjectModel`. Sfrutta l'esistente `ObjectModel` `Product` e il suo campo `mpn`.

### 4.4 Asset JavaScript (`views/js/`)

Questo modulo non include alcun file JavaScript personalizzato. La funzionalità di filtraggio e ordinamento per la nuova colonna MPN è gestita dall'implementazione esistente di DataTables.js di PrestaShop per l'elenco prodotti, che si adatta automaticamente alle nuove colonne.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo non include alcun file CSS personalizzato. Lo stile della nuova colonna MPN e del campo filtro erediterà direttamente dal tema del back office di PrestaShop.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il meccanismo principale del modulo è quello di sovrascrivere i template Twig del Back Office di PrestaShop per iniettare la colonna MPN.

- **`mpnmypresta/views/PrestaShop/Admin/Product/CatalogPage/Lists/list.html.twig`**:
  - **Scopo**: Questo template è un override diretto del template core dell'elenco prodotti di PrestaShop (`admin-dev/themes/new-theme/template/catalog/products/list.html.twig` o percorso simile a seconda della versione di PS).
  - **Funzionalità**: Modifica la struttura dell'elenco prodotti per includere l'intestazione della colonna MPN e il campo di input del filtro corrispondente. Assicura che il campo MPN sia riconosciuto come colonna ordinabile e filtrabile all'interno della configurazione di DataTables.
- **`mpnmypresta/views/PrestaShop/Admin/Product/CatalogPage/Lists/products_table.html.twig`**:
  - **Scopo**: Questo template è un override diretto del template core della tabella prodotti di PrestaShop (`admin-dev/themes/new-theme/template/catalog/products/products_table.html.twig` o percorso simile).
  - **Funzionalità**: Modifica le righe della tabella per visualizzare il valore MPN effettivo per ogni prodotto nella colonna appena aggiunta. Accede alla proprietà `product.mpn` dai dati del prodotto passati al template.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**: Questo modulo non crea nuove tabelle del database. Si basa sulla colonna `mpn` esistente all'interno della tabella `ps_product` (o `ps_product_shop` per MPN specifici del negozio, anche se tipicamente è su `ps_product`).
- **Tabella degli hook registrati**: Questo modulo non registra esplicitamente nuovi hook. La sua funzionalità è ottenuta tramite override di template. Sebbene non utilizzi `displayHeader`, `displayRightColumn`, `actionValidateOrder` ecc., nel suo metodo `install()`, probabilmente si registra per gli override di template, che è una forma implicita di aggancio al processo di rendering.

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e qualsiasi domanda relativa al modulo "Filtro MPN nell'elenco prodotti nel back office", si prega di fare riferimento al proprio account cliente MyPresta.eu. Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda possiate avere.

- **MyPresta.eu Cronologia ordini e download**: <https://mypresta.eu/my-account/orders/>
- **Contatto supporto MyPresta.eu**: <https://mypresta.eu/contact>
