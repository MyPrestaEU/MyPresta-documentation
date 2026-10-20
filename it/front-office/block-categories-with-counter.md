---
title: "Blocco categorie con contatore - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Blocco categorie con contatore di MyPresta.eu."
sidebar:
  label: "Blocco categorie con contatore - Manuale del commerciante e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Block categories with counter su MyPresta.eu](https://mypresta.eu/modules/front-office-features/block-categories-with-counter.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/block-categories-with-counter/)
>
> ---


# Blocco categorie con contatore

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Non sono necessarie configurazioni speciali del server oltre a un ambiente di hosting PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

Il modulo "Blocco categorie con contatore" offre una configurazione semplice, principalmente focalizzata sull'abilitazione o la disabilitazione della sua funzionalità principale.

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, cliccando su "Configura" per il modulo "Blocco categorie con contatore" verrai indirizzato alla sua schermata di configurazione principale.

#### **Visualizza contatore prodotti**

- **Cosa fa questa impostazione:** Questo è l'interruttore principale che controlla se il conteggio dei prodotti viene visualizzato accanto a ogni nome di categoria nel blocco.
- **Effetto della modifica di questa impostazione:**
  - *Quando abilitato (SÌ):* Il modulo recupererà e visualizzerà il numero di prodotti attivi per ogni categoria nel blocco categorie, come "Elettronica (125)". Questa è la funzionalità principale del modulo.
  - *Quando disabilitato (NO):* Il modulo si comporterà come un blocco categorie standard, mostrando solo i nomi delle categorie senza alcun conteggio dei prodotti. Il modulo visualizzerà comunque l'albero delle categorie, ma la funzione unica del contatore sarà inattiva.
- **Valore consigliato:** **SÌ**. Per utilizzare il principale vantaggio del modulo, dovresti abilitare questa impostazione.
- **Scenario/esempio del commerciante:** Se vuoi che i tuoi clienti vedano rapidamente quali categorie sono popolari o ben fornite, abilita questa opzione. Se preferisci un elenco di categorie minimalista senza numeri, puoi disabilitarla, anche se questo annullerebbe lo scopo dell'installazione di questo modulo specifico.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione principale | Visualizza contatore prodotti | SÌ | Controlla se il conteggio dei prodotti viene mostrato accanto ai nomi delle categorie. Abilitandolo si attiva la funzionalità principale del modulo. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I conteggi dei prodotti non vengono visualizzati o sembrano errati.**
R:

1. **Controlla la configurazione del modulo:** Vai su **Moduli > Gestione moduli**, trova "Blocco categorie con contatore", clicca su "Configura" e assicurati che "Visualizza contatore prodotti" sia impostato su **SÌ**.
2. **Svuota la cache di PrestaShop:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). A volte, il vecchio contenuto della cache impedisce che le modifiche appaiano immediatamente.
3. **Stato del prodotto:** Assicurati che i prodotti che ti aspetti vengano contati siano "attivi" e "disponibili per l'ordine" nelle impostazioni del prodotto. Il modulo conta solo i prodotti attivi e visibili.
4. **Associazione categoria:** Ricontrolla che i prodotti siano correttamente associati alle rispettive categorie.

**D: Il blocco categorie ha un aspetto strano o non si adatta al mio tema.**
R: Il modulo eredita lo stile dal tuo tema PrestaShop attivo.

1. **Compatibilità del tema:** Sebbene il modulo sia compatibile con le versioni di PrestaShop, specifici design del tema possono talvolta causare lievi disallineamenti visivi.
2. **CSS personalizzato:** Se hai un tema personalizzato o esigenze di stile specifiche, potresti dover aggiungere regole CSS personalizzate al file `custom.css` del tuo tema (o equivalente) per regolare l'aspetto del blocco categorie e del contatore. Uno sviluppatore web può aiutarti in questo.

**D: Posso cambiare la posizione del blocco categorie?**
R: Sì, questa è una funzionalità standard di PrestaShop.

1. Vai su **Design > Posizioni** (o **Design > Tema e logo > Posizioni** nelle versioni precedenti).
2. Cerca l'hook in cui è attualmente visualizzato il modulo "Blocco categorie con contatore" (es. `displayLeftColumn`, `displayRightColumn`).
3. Puoi trascinare e rilasciare il modulo per riordinarne la posizione all'interno di quell'hook, oppure utilizzare il pulsante "Trapianta un modulo" per spostarlo completamente in un hook diverso.

**D: Questo modulo rallenta il mio negozio?**
R: Il modulo è progettato per essere efficiente. Interroga il database per i conteggi dei prodotti, che è un'operazione standard. Per negozi molto grandi con decine di migliaia di prodotti e categorie, potrebbe esserci un impatto minimo, ma per la maggior parte dei negozi dovrebbe essere trascurabile. Assicurati che il tuo server soddisfi le specifiche raccomandate da PrestaShop per prestazioni ottimali.

**D: Come traduco il modulo se il mio negozio è multilingue?**
R: Questo modulo visualizza principalmente nomi di categorie e numeri, che sono già gestiti dal sistema di traduzione principale di PrestaShop per le categorie. Se il modulo stesso avesse delle stringhe di testo specifiche (es. un titolo per il blocco), le tradurresti tramite **Internazionale > Traduzioni > Traduzioni dei moduli**. Tuttavia, per questo modulo specifico, la maggior parte del contenuto è dinamica dalle tue categorie.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce un'analisi approfondita della struttura tecnica del modulo "Blocco categorie con contatore", destinata a sviluppatori, webmaster e agenzie tecniche.

### 4.1 Panoramica dell'architettura

Il modulo "Blocco categorie con contatore" è un modulo PrestaShop leggero a file singolo (`block-categories-with-counter.php`). Estende la classe `Module` principale e utilizza principalmente il sistema di hook di PrestaShop per integrare la sua funzionalità. La sua logica principale ruota attorno all'override o all'estensione del comportamento predefinito del blocco categorie per iniettare i conteggi dei prodotti. Sfrutta gli ObjectModels `Category` e `Product` di PrestaShop per recuperare i dati.

### 4.2 Controller (`controllers/`)

Questo modulo **non** contiene alcun controller amministrativo Front-Office o Back-Office personalizzato. Tutta la configurazione è gestita direttamente all'interno del metodo `getContent()` del file principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo **non** introduce classi o ObjectModels personalizzati nella directory `classes/`. Utilizza direttamente gli ObjectModels `Category` e `Product` principali di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo **non** include alcun file JavaScript personalizzato. La sua funzionalità è puramente renderizzata lato server.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo **non** include alcun file CSS personalizzato. Si basa interamente sullo stile fornito dal tema PrestaShop attivo per il blocco categorie predefinito.

### 4.6 Struttura del template Smarty (`views/templates/`)

Questo modulo **non** contiene file di template personalizzati in `views/templates/`. Probabilmente sovrascrive o modifica l'output del template del modulo `blockcategories` predefinito o renderizza direttamente il suo contenuto all'interno dei metodi `hook`. Data la sua semplicità, è altamente probabile che utilizzi il metodo `display` per renderizzare il contenuto direttamente, oppure potrebbe essere progettato per sostituire l'output del modulo `blockcategories` predefinito agganciandosi alle stesse posizioni e fornendo il proprio HTML.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**: Questo modulo **non** crea tabelle del database personalizzate. Memorizza la sua configurazione (in particolare, l'impostazione `PS_BLOCK_CATEGORIES_WITH_COUNTER_DISPLAY_COUNT`) nella tabella standard `ps_configuration`.
- **Tabella degli hook registrati**:

| Nome dell'hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayLeftColumn` | Renderizza il blocco categorie nella colonna sinistra. |
| `displayRightColumn` | Renderizza il blocco categorie nella colonna destra. |
| `displayHome` | Renderizza il blocco categorie nella homepage. |
| `displayFooter` | Renderizza il blocco categorie nel piè di pagina. |
| `displayHeader` | Renderizza il blocco categorie nell'intestazione. |

Il modulo genera dinamicamente l'HTML per l'albero delle categorie e i conteggi dei prodotti all'interno di questi metodi hook, tipicamente utilizzando una funzione ricorsiva per costruire la struttura dell'elenco nidificato.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, il supporto ufficiale e per scaricare nuove versioni del modulo "Blocco categorie con contatore", visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e alla compatibilità del modulo.
