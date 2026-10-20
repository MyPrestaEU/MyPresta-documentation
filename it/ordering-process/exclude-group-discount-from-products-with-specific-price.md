---
title: "Escludi sconto gruppo dai prodotti con prezzo specifico - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Escludi sconto gruppo dai prodotti con prezzo specifico' di MyPresta.eu."
sidebar:
  label: "Escludi sconto gruppo dai prodotti con prezzo specifico - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Exclude group discount from products with specific price su MyPresta.eu](https://mypresta.eu/modules/ordering-process/exclude-group-discount-from-products-with-specific-price.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/exclude-group-discount-from-products-with-specific-price/)
>
> ---


# Escludi sconto gruppo dai prodotti con prezzo specifico

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono generalmente sufficienti. Non sono richieste configurazioni server insolite.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, vai su **Moduli > Gestione moduli**, trova "Escludi sconto gruppo dai prodotti con prezzo specifico" e clicca su **Configura**. Vedrai la schermata di configurazione principale.

#### Impostazione: Disabilita lo sconto per gruppi per i prodotti con prezzi specifici

- **Cosa fa questa impostazione:** Questo è il controllo principale per la funzionalità del modulo. Determina se il modulo deve impedire attivamente che gli sconti di gruppo vengano applicati ai prodotti che hanno già prezzi specifici.
- **Effetto della modifica di questa impostazione:**
  - **Quando impostato su "Abilitato":** Se un prodotto ha un prezzo specifico (ad esempio, un prezzo di vendita speciale che hai impostato), e un cliente di un gruppo che normalmente riceve uno sconto (ad esempio, i "Clienti VIP" ottengono il 10% di sconto) visualizza o acquista quel prodotto, lo sconto di gruppo del 10% *non* verrà applicato. Il cliente pagherà il prezzo specifico che hai impostato. Questo è il comportamento previsto del modulo.
  - **Quando impostato su "Disabilitato":** Il modulo sarà inattivo. Il comportamento predefinito di PrestaShop riprenderà. Ciò significa che se un prodotto ha un prezzo specifico, e un cliente di un gruppo scontato lo visualizza o lo acquista, *sia* il prezzo specifico che lo sconto di gruppo verranno applicati, portando potenzialmente a un prezzo finale molto più basso del previsto.
- **Valore consigliato:** **Abilitato**. Questo è lo scopo del modulo, prevenire l'accumulo non intenzionale di sconti.
- **Scenario/esempio del commerciante:** Hai una "Vendita Estiva" in cui una specifica T-shirt ha un prezzo di $15 (da $25). Hai anche un gruppo di clienti "Grossisti" che ottiene il 20% di sconto su tutti gli ordini.
  - Se questa impostazione è **Abilitata**: Un cliente grossista acquista la T-shirt. Paga $15. Lo sconto del 20% per i grossisti viene ignorato per questo prodotto specifico.
  - Se questa impostazione è **Disabilitata**: Un cliente grossista acquista la T-shirt. PrestaShop applica prima il prezzo specifico ($15), quindi applica lo sconto del 20% per i grossisti a $15, rendendo il prezzo finale $12. Questo potrebbe essere inferiore al tuo margine di profitto desiderato.

#### Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | Disabilita lo sconto per gruppi per i prodotti con prezzi specifici | Abilitato | Controlla se gli sconti di gruppo sono impediti di accumularsi con i prezzi specifici. **Abilitato** impedisce l'accumulo, preservando i margini di profitto. **Disabilitato** consente l'accumulo, portando potenzialmente a prezzi più bassi. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho abilitato il modulo, ma gli sconti di gruppo si applicano ancora ai miei prezzi specifici. Cosa c'è che non va?**
R:

1.  **Svuota la cache:** Svuota sempre la cache di PrestaShop dopo aver apportato modifiche alla configurazione. Vai su **Parametri avanzati > Prestazioni**, quindi clicca su "Svuota la cache" in alto a destra.
2.  **Ordine dei moduli:** In rari casi, un altro modulo potrebbe sovrascrivere i calcoli dei prezzi. Se hai altri moduli di prezzo o sconto, prova a disabilitarli temporaneamente uno per uno per vedere se c'è un conflitto.
3.  **Configurazione del prezzo specifico:** Ricontrolla che i tuoi "prezzi specifici" siano configurati correttamente per i prodotti in questione. Vai alla pagina di modifica del prodotto, quindi alla scheda "Prezzi" e assicurati che il prezzo specifico sia attivo e applicato correttamente.
4.  **Configurazione dello sconto di gruppo:** Verifica che lo sconto per il gruppo di clienti sia impostato correttamente in **Parametri negozio > Impostazioni cliente > Gruppi**.

**D: Questo modulo influenzerà le mie regole del carrello o i codici coupon regolari?**
R: No, questo modulo si rivolge specificamente agli "sconti di gruppo" (sconti applicati automaticamente in base al gruppo assegnato a un cliente) e alla loro interazione con i "prezzi specifici" (sovrascritture manuali del prezzo per un prodotto). Non interferisce con le regole del carrello di PrestaShop, i codici coupon o altri meccanismi promozionali a meno che tali meccanismi non siano essi stessi basati su prezzi specifici o sconti di gruppo.

**D: Questo modulo rallenta il mio negozio?**
R: No, il modulo è molto leggero. Funziona sovrascrivendo una classe PrestaShop fondamentale (`Product.php`) per modificare il modo in cui vengono calcolati i prezzi. Questo è un processo altamente ottimizzato e non dovrebbe introdurre alcuna degradazione delle prestazioni evidente.

**D: E se volessi che gli sconti di gruppo si applicassero *a volte* ai prezzi specifici?**
R: Questo modulo offre un approccio "tutto o niente": o gli sconti di gruppo sono esclusi da *tutti* i prodotti con prezzi specifici, oppure no. Se hai bisogno di un controllo più granulare (ad esempio, escludere per il Prodotto A ma consentire per il Prodotto B, entrambi con prezzi specifici), questo modulo da solo non lo raggiungerà. Dovresti gestire manualmente i prezzi specifici e gli sconti di gruppo o considerare un modulo di prezzo più avanzato. Per questo modulo, la raccomandazione è di abilitarlo per prevenire l'accumulo non intenzionale.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo `Escludi sconto gruppo dai prodotti con prezzo specifico` implementa la sua funzionalità principale tramite un override della classe `Product`. Questo è un modello di sviluppo PrestaShop comune ed efficace per modificare i comportamenti principali senza alterare direttamente i file core. Sovrascrivendo `Product::getPriceStatic()`, il modulo intercetta la logica di calcolo del prezzo per impedire che gli sconti specifici per gruppo vengano applicati quando un prodotto ha un prezzo specifico attivo.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**: Nessuno. Tutta la logica del front-office è gestita tramite l'override della classe `Product`.
- **Controller Admin Back-Office**: Nessuno. La configurazione del modulo è gestita direttamente all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

La funzionalità principale del modulo risiede nel suo override di classe.

- **Percorso file**: `exgdis/override/classes/Product.php`
- **Nome classe**: `Product` (sovrascrive la classe `Product` core)
- **Classe genitore**: `ProductCore`
- **Responsabilità**: Questo override modifica il metodo `getPriceStatic()`, che è centrale per il modo in cui PrestaShop calcola i prezzi dei prodotti in tutto il front office (pagine prodotto, carrello, checkout) e nel back office.
  - **Logica chiave**: All'interno del metodo `getPriceStatic()` sovrascritto, il modulo controlla se la sua impostazione di configurazione `exgdis_groups` (che corrisponde a "Disabilita lo sconto per gruppi per i prodotti con prezzi specifici") è abilitata.
  - Se abilitato, e se il prodotto attualmente in fase di prezzatura ha un prezzo specifico attivo, il modulo assicura che il parametro `$use_group_reduction` passato al metodo originale `ProductCore::getPriceStatic()` sia impostato su `false`. Questo dice efficacemente a PrestaShop di *non* applicare sconti specifici per gruppo per quel particolare calcolo del prezzo.
  - Il file `index.php` in `override/classes/` è un file vuoto standard per prevenire l'elenco delle directory.

### 4.4 Risorse JavaScript (`views/js/`)

- Nessuno. Il modulo non ha componenti JavaScript front-end o back-end.

### 4.5 Fogli di stile CSS (`views/css/`)

- Nessuno. Il modulo non ha stili CSS personalizzati.

### 4.6 Struttura del template Smarty (`views/templates/`)

- Nessuno. La configurazione del modulo viene renderizzata direttamente tramite `getContent()` nel file principale del modulo, e la sua funzionalità è puramente basata sulla logica, non sulla visualizzazione.

### 4.7 Schema del database e Mappa degli hook

- **Tabelle del database**: Il modulo non crea tabelle del database personalizzate. Memorizza la sua configurazione nella tabella `ps_configuration`.

  - Voce `ps_configuration`: `exgdis_groups` (memorizza lo stato abilitato/disabilitato dell'impostazione principale).
- **Tabella degli hook registrati**: Il modulo non registra esplicitamente alcun hook nella tabella `ps_hook_module`. La sua funzionalità è implementata tramite un override di classe, che viene caricato dal meccanismo di override di PrestaShop.

| Nome Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `override/classes/Product.php` | Durante le chiamate a `Product::getPriceStatic()` | Intercetta il calcolo del prezzo per impedire sconti di gruppo sui prodotti con prezzi specifici. |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Escludi sconto gruppo dai prodotti con prezzo specifico", si prega di fare riferimento al proprio account cliente MyPresta.eu. È possibile scaricare le versioni più recenti e accedere alle risorse di supporto direttamente da [MyPresta.eu](https://mypresta.eu).
