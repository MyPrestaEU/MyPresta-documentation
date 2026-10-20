---
title: "Schede della homepage - Manuale del commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Schede della homepage di MyPresta.eu."
sidebar:
  label: "Schede della homepage - Manuale del commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Homepage tabs su MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-tabs.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/homepage-tabs/)
>
> ---


# Schede della homepage

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Non sono richieste configurazioni server insolite.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo "Schede della homepage" in Gestione moduli. Questo ti porterà alla schermata di configurazione principale.

La pagina di configurazione del modulo è semplice, concentrandosi principalmente sull'assicurare che il modulo possa ricevere aggiornamenti.

- **Cosa fa questa impostazione:** Questa sezione gestisce la capacità del modulo di verificare e ricevere aggiornamenti da MyPresta.eu. Mantenere i tuoi moduli aggiornati è fondamentale per la sicurezza, le prestazioni e la compatibilità con le nuove versioni di PrestaShop.
- **Effetto della modifica di questa impostazione:**
  - *Quando abilitato (predefinito):* Il modulo verificherà periodicamente MyPresta.eu per nuove versioni. Se è disponibile un aggiornamento, verrai avvisato nel tuo back office PrestaShop, permettendoti di scaricare e installare facilmente l'ultima versione. Ciò garantisce che il tuo modulo rimanga compatibile e benefici delle ultime funzionalità e correzioni di bug.
  - *Quando disabilitato:* Il modulo non verificherà gli aggiornamenti. Non verrai avvisato delle nuove versioni, perdendo potenzialmente importanti miglioramenti, patch di sicurezza o correzioni di compatibilità. Dovresti verificare manualmente gli aggiornamenti su MyPresta.eu.
- **Valore consigliato:** **SÌ (Abilitato)**. Si consiglia vivamente di mantenere questa impostazione abilitata per garantire che il tuo modulo sia sempre aggiornato e sicuro.
- **Scenario / esempio del commerciante:** Immagina che PrestaShop rilasci una nuova versione minore (ad esempio, 8.1.5). Potrebbe essere rilasciato un aggiornamento al modulo "Schede della homepage" per garantire la piena compatibilità. Con gli aggiornamenti abilitati, verresti avvisato e potresti facilmente aggiornare, prevenendo qualsiasi potenziale problema. Se disabilitato, le tue schede potrebbero smettere di funzionare correttamente dopo l'aggiornamento di PrestaShop, e non sapresti perché finché non verifichi manualmente gli aggiornamenti del modulo.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | Controlli aggiornamenti (mypresta\_updates, update\_, updatev\_) | SÌ (Abilitato) | Abilita i controlli automatici per gli aggiornamenti del modulo da MyPresta.eu, garantendo compatibilità, sicurezza e accesso a nuove funzionalità. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Le mie schede della homepage non vengono visualizzate dopo l'installazione.**
R:

1.  **Verifica la posizione del modulo:** Vai su **Design > Posizioni** nel tuo back office PrestaShop. Cerca `displayHome`. Assicurati che il modulo "Schede della homepage" sia agganciato a `displayHome`. Se non è presente, usa il pulsante "Trapianta un modulo" per aggiungerlo.
2.  **Svuota la cache:** Svuota sempre la cache di PrestaShop dopo aver installato o configurato i moduli. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" nell'angolo in alto a destra.
3.  **Verifica i conflitti del tema:** Alcuni temi personalizzati potrebbero sovrascrivere l'hook `displayHome` o avere uno stile specifico che nasconde il modulo. Passa temporaneamente al tema predefinito di PrestaShop (Classic) per vedere se le schede appaiono. Se lo fanno, il tuo tema richiede CSS personalizzati o aggiustamenti del template.

**D: I prodotti nelle schede non hanno l'aspetto giusto (ad esempio, dimensioni sbagliate, disallineati).**
R: Questo è tipicamente un problema di stile legato al tema del tuo negozio. Il modulo stesso fornisce i dati del prodotto, ma il tuo tema detta come vengono visualizzati gli elenchi dei prodotti.

1.  **Svuota la cache:** Ancora una volta, svuota la cache di PrestaShop.
2.  **CSS del tema:** Il CSS del tuo tema potrebbe essere in conflitto con lo stile predefinito del modulo. Uno sviluppatore web può ispezionare gli elementi utilizzando gli strumenti di sviluppo del browser e applicare override CSS personalizzati nel file `custom.css` del tuo tema per correggere l'aspetto.

**D: Posso cambiare l'ordine delle schede o quali prodotti appaiono in esse?**
R: Questo modulo ripristina la *funzionalità* delle schede della homepage (Popolari, Nuovi, I più venduti, In offerta). I tipi di prodotto specifici visualizzati (ad esempio, "Prodotti popolari") sono determinati dalla logica principale di PrestaShop per tali categorie. Questo modulo non offre opzioni per selezionare manualmente i prodotti per ogni scheda o riordinare le schede stesse tramite la sua configurazione. Per personalizzazioni avanzate come selezioni di prodotti personalizzate o ordinamento delle schede, avresti tipicamente bisogno di un modulo più avanzato o di uno sviluppo personalizzato.

**D: Il modulo è installato, ma non vedo opzioni di configurazione oltre alle impostazioni di aggiornamento.**
R: Questo modulo è progettato per riabilitare la funzionalità principale delle schede della homepage di PrestaShop che è stata rimossa. La sua funzione principale è far apparire di nuovo le schede, utilizzando la logica predefinita di PrestaShop per i prodotti "Popolari", "Nuovi", "I più venduti" e "In offerta". Pertanto, non ha ampie opzioni di configurazione per la gestione dei contenuti all'interno delle schede stesse, poiché tale logica è gestita dal core di PrestaShop.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Schede della homepage" (`homepagetabs`) è un modulo PrestaShop leggero progettato per riabilitare una funzionalità principale del front-office che è stata rimossa nelle versioni più recenti di PrestaShop. Opera principalmente agganciandosi a `displayHome` per renderizzare le schede dei prodotti e a `displayHeader` per includere le risorse necessarie. Sfrutta i meccanismi di recupero dei prodotti esistenti di PrestaShop per i prodotti "Popolari", "Nuovi", "I più venduti" e "In offerta", agendo efficacemente come un ponte per ripristinare il componente visivo. Il modulo segue un modello MVC standard di PrestaShop, sebbene la sua logica principale risieda all'interno della classe principale del modulo (`homepagetabs.php`) per il rendering.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**: Nessuno. La logica di visualizzazione del front-office del modulo è interamente gestita dal file del modulo `homepagetabs.php` tramite hook.
- **Controller Admin Back-Office**: Nessuno. Tutta la configurazione è gestita direttamente all'interno del metodo `getContent()` della classe principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

- Nessuno. Il modulo non definisce classi personalizzate o istanze di `ObjectModel`. Si basa sulle classi principali di PrestaShop per il recupero dei dati del prodotto.

### 4.4 Risorse JavaScript (`views/js/`)

- `homepagetabs/views/js/homepagetabs.js`
  - **Ambito**: Front-office.
  - **Responsabilità**: Questo script è responsabile del comportamento interattivo delle schede della homepage. Probabilmente gestisce:
    - Il binding dei listener di eventi click alle intestazioni delle schede.
    - Il cambio di visibilità dei blocchi di contenuto del prodotto in base alla scheda attiva.
    - L'aggiunta/rimozione di classi CSS attive alle intestazioni e al contenuto delle schede.
    - Potenzialmente la gestione delle richieste AJAX se il contenuto del prodotto viene caricato dinamicamente (anche se per questo modulo, è più probabile che sia un semplice meccanismo di mostra/nascondi per il contenuto pre-renderizzato).
    - Assicurare che le schede funzionino correttamente su diverse dimensioni di schermo e dispositivi.

### 4.5 Fogli di stile CSS (`views/css/`)

- `homepagetabs/views/css/homepagetabs.css`
  - **Ambito**: Stile del cliente del front-office.
  - **Responsabilità**: Questo foglio di stile fornisce la presentazione visiva predefinita per le schede della homepage e il loro contenuto. Definisce gli stili per:
    - Il contenitore delle schede stesso.
    - Le singole intestazioni delle schede (ad esempio, `ul.home-tabs li a`).
    - Lo stato della scheda attiva (ad esempio, `ul.home-tabs li.active a`).
    - Il contenitore della griglia dei prodotti per ogni scheda (ad esempio, `.tab-content`).
    - Regolazioni responsive di base per diverse dimensioni di schermo.
  - **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere**: Gli sviluppatori possono mirare a classi come `.home-tabs`, `.home-tabs li`, `.home-tabs li.active`, `.tab-content` e gli elementi della griglia dei prodotti all'interno di `.tab-content` per integrare l'aspetto del modulo senza problemi con il loro tema personalizzato.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **Template degli hook (`views/templates/hook/`)**:
  - `homepagetabs/views/templates/hook/homepagetabs.tpl`
    - **Hook**: `displayHome`
    - **Scopo**: Questo è il template principale del front-office responsabile del rendering dell'intero blocco delle schede della homepage. Conterrà la struttura HTML per le intestazioni delle schede (ad esempio, `<ul>` per i titoli delle schede) e le aree di contenuto corrispondenti (ad esempio, `<div>` per gli elenchi dei prodotti). Itera attraverso i dati del prodotto passati ad esso dal metodo `hookDisplayHome()` del modulo, visualizzando i prodotti "Popolari", "Nuovi", "I più venduti" e "In offerta" nelle rispettive aree di contenuto delle schede. Questo template è dove vengono renderizzate le schede dei prodotti (immagini, nomi, prezzi, pulsanti aggiungi al carrello) per ogni tipo di prodotto.
- **Template di amministrazione (`views/templates/admin/`)**:
  - `homepagetabs/views/templates/admin/homepagetabs.tpl`
    - **Scopo**: Questo template renderizza il modulo di configurazione del modulo nel back office di PrestaShop. Visualizza le impostazioni relative ai controlli degli aggiornamenti (`mypresta_updates`, `update_`, `updatev_`) e qualsiasi altro elemento di configurazione standard del modulo.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**: Il modulo non crea tabelle del database personalizzate. Memorizza le sue impostazioni di configurazione (ad esempio, `mypresta_updates`) nella tabella standard `ps_configuration`.
- **Tabella degli hook registrati**:

| Nome dell'hook | Tempistica di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHome` | Renderizza il contenuto sulla homepage del negozio. | Questo hook viene utilizzato per produrre l'intera struttura HTML delle schede della homepage, incluse le intestazioni delle schede e gli elenchi dei prodotti. |
| `displayHeader` | Eseguito nella sezione `<head>` di ogni pagina del front-office. | Questo hook viene utilizzato per includere i file CSS (`homepagetabs.css`) e JavaScript (`homepagetabs.js`) del modulo, garantendo uno stile corretto e una funzionalità interattiva delle schede. |

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, supporto tecnico e ulteriore assistenza con il modulo "Schede della homepage", visita il tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per aiutarti con qualsiasi domanda o problema tu possa incontrare.
