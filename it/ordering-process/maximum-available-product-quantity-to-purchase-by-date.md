---
title: "Quantità massima di prodotto acquistabile per data - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Quantità massima di prodotto acquistabile per data' di MyPresta.eu."
sidebar:
  label: "Quantità massima di prodotto acquistabile per data"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Maximum available product quantity to purchase by date su MyPresta.eu](https://mypresta.eu/modules/ordering-process/maximum-available-product-quantity-to-purchase-by-date.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/maximum-available-product-quantity-to-purchase-by-date/)
>
> ---


# Quantità massima di prodotto acquistabile per data

## 1. Requisiti e Compatibilità
- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Sono richieste estensioni PHP standard (cURL, JSON, OpenSSL), che sono tipicamente disponibili sulla maggior parte degli ambienti di hosting compatibili con PrestaShop.

## 2. Panoramica completa della configurazione (ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)
Questa è la schermata di configurazione principale per il modulo, accessibile immediatamente dopo l'installazione o cliccando su "Configura" dal Gestore moduli.

-   **Cosa fa questa impostazione:** Questa schermata contiene tipicamente le impostazioni generali per il modulo, come l'abilitazione/disabilitazione della sua funzionalità principale o l'impostazione delle preferenze globali.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* Le funzionalità di limitazione della quantità del modulo saranno attive in tutto il tuo negozio in base alle regole che definisci.
    -   *Quando disabilitato:* Il modulo cesserà di imporre qualsiasi limite di quantità e i clienti potranno acquistare qualsiasi quantità di stock disponibile.
-   **Valore consigliato:** "SÌ" (Abilitato) per attivare la funzionalità principale del modulo.
-   **Scenario/esempio del commerciante:** Hai appena installato il modulo e vuoi iniziare a definire i limiti. Il primo passo è assicurarsi che il modulo sia attivo su questa schermata prima di procedere alla definizione di limiti di prodotto specifici.

### 2.2 Schermata di amministrazione dedicata: Limite di quantità di acquisto del prodotto per data (Back Office > Catalogo > Limite di quantità di acquisto del prodotto per data)
Questa è la schermata principale in cui definisci e gestisci tutti i tuoi limiti di quantità di prodotto in base agli intervalli di date.

**Nome schermata e posizione nel menu:**
Puoi trovare questa schermata navigando su **Catalogo > Limite di quantità di acquisto del prodotto per data** nel menu del tuo Back Office di PrestaShop.

**Azioni e impostazioni disponibili:**
Questa schermata presenta un elenco (griglia) di tutti i limiti di quantità esistenti che hai impostato. Puoi aggiungere nuovi limiti, modificare quelli esistenti o eliminarli.

#### **Colonne della tabella di elenco:**
-   **ID:** Un identificatore univoco per ogni regola di limite di quantità.
-   **Prodotto:** Il nome del prodotto a cui si applica il limite.
-   **Data da:** La data e l'ora di inizio in cui il limite di quantità diventa attivo.
-   **Data a:** La data e l'ora di fine in cui il limite di quantità scade.
-   **Quantità:** Il numero massimo di unità del prodotto che può essere acquistato entro l'intervallo di date specificato.
-   **Attivo:** Un interruttore (Sì/No) per abilitare o disabilitare una specifica regola di limite senza eliminarla.

#### **Aggiunta/Modifica di una regola di limite di quantità:**
Quando clicchi su "Aggiungi nuovo" o modifichi una regola esistente, vedrai un modulo con i seguenti campi:

-   **Limite di quantità di acquisto del prodotto per data:** Questo è il titolo principale del modulo.
-   **ID Prodotto:**
    -   **Cosa fa questa impostazione:** Questo campo ti consente di selezionare il prodotto specifico a cui si applicherà questo limite di quantità. Tipicamente userai una barra di ricerca per trovare il prodotto per nome o ID.
    -   **Effetto della modifica di questa impostazione:** Determina quale quantità di acquisto del prodotto sarà limitata da questa regola.
    -   **Valore consigliato:** Seleziona il prodotto esatto che intendi limitare.
    -   **Scenario/esempio del commerciante:** Vuoi limitare le vendite di "Maglietta estiva" a 50 unità. Cercheresti e selezioneresti "Maglietta estiva" qui.
-   **Data da:**
    -   **Cosa fa questa impostazione:** Definisce la data e l'ora esatte in cui questa regola di limite di quantità diventa attiva.
    -   **Effetto della modifica di questa impostazione:** Il limite sarà applicato solo per gli acquisti effettuati a partire da questa data/ora.
    -   **Valore consigliato:** Imposta la data e l'ora di inizio precise per la tua promozione o restrizione.
    -   **Scenario/esempio del commerciante:** Vuoi che il limite inizi il 1° agosto 2024, alle 9:00.
-   **Data a:**
    -   **Cosa fa questa impostazione:** Definisce la data e l'ora esatte in cui questa regola di limite di quantità scade.
    -   **Effetto della modifica di questa impostazione:** Dopo questa data/ora, il limite non sarà più applicato e i clienti potranno acquistare qualsiasi quantità di stock disponibile.
    -   **Valore consigliato:** Imposta la data e l'ora di fine precise per la tua promozione o restrizione.
    -   **Scenario/esempio del commerciante:** Vuoi che il limite termini il 7 agosto 2024, alle 17:00.
-   **Quantità:**
    -   **Cosa fa questa impostazione:** Specifica il numero massimo di unità del prodotto selezionato che può essere acquistato entro l'intervallo "Data da" e "Data a".
    -   **Effetto della modifica di questa impostazione:** Questo è il limite effettivo applicato. Se un cliente tenta di aggiungere più di questa quantità al carrello entro l'intervallo di date attivo, verrà impedito.
    -   **Valore consigliato:** La quantità massima specifica che desideri consentire.
    -   **Scenario/esempio del commerciante:** Vuoi limitare gli acquisti a 5 unità per cliente durante il periodo specificato. Inseriresti "5" qui.
-   **Attivo (interruttore On/Off):**
    -   **Cosa fa questa impostazione:** Attiva o disattiva lo stato attivo di questa specifica regola di limite di quantità.
    -   **Effetto della modifica di questa impostazione:**
        -   *On:* La regola è attiva e applicherà il limite di quantità durante il suo intervallo di date specificato.
        -   *Off:* La regola è inattiva e non applicherà alcun limite di quantità, anche se il suo intervallo di date è corrente. Questo è utile per sospendere temporaneamente una regola senza eliminarla.
    -   **Valore consigliato:** "On" per le regole attive, "Off" per le regole che desideri disabilitare temporaneamente.
    -   **Scenario/esempio del commerciante:** Hai impostato un limite per una vendita del Black Friday, ma decidi di posticiparla. Invece di eliminare la regola, puoi disattivarla e poi riattivarla quando sei pronto.
-   **Pulsante Salva:**
    -   **Cosa fa questa impostazione:** Salva tutte le modifiche apportate alla regola di limite di quantità.
    -   **Effetto della modifica di questa impostazione:** Applica la nuova o aggiornata regola all'applicazione della quantità di prodotto del tuo negozio.

**Effetto delle modifiche:**
-   **Aggiunta di una nuova regola:** Verrà creato un nuovo limite di quantità e diventerà attivo (se impostato su "On") durante il suo intervallo di date specificato, limitando gli acquisti del prodotto selezionato.
-   **Modifica di una regola esistente:** Le modifiche (es. prodotto, date, quantità, stato attivo) aggiorneranno immediatamente il modo in cui il limite viene applicato.
-   **Eliminazione di una regola:** Il limite di quantità verrà rimosso in modo permanente e nessuna restrizione si applicherà a quel prodotto per quell'intervallo di date (a meno che non esistano altre regole).

**Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
1.  **Pianifica le tue promozioni/restrizioni:** Prima di configurare, decidi quali prodotti necessitano di limiti, quali dovrebbero essere le quantità massime e le date e gli orari esatti di inizio/fine.
2.  **Naviga su "Limite di quantità di acquisto del prodotto per data":** Vai su **Catalogo > Limite di quantità di acquisto del prodotto per data**.
3.  **Aggiungi nuove regole:** Clicca su "Aggiungi nuovo" per ogni prodotto che desideri limitare. Compila attentamente Prodotto, Data da, Data a, Quantità e assicurati che "Attivo" sia "On".
4.  **Rivedi e regola:** Controlla regolarmente il tuo elenco di regole per assicurarti che siano ancora pertinenti e configurate correttamente. Usa l'interruttore "Attivo" per disabilitare temporaneamente le regole se necessario.
5.  **Monitora il feedback dei clienti:** Presta attenzione a qualsiasi richiesta dei clienti relativa ai limiti di quantità per assicurarti che le regole siano chiare e funzionino come previsto.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista                                       | Impostazione / Opzione                     | Predefinito / Consigliato | Scopo e Impatto Il modulo "Quantità massima di prodotto acquistabile per data" di MyPresta.eu è uno strumento potente per controllare la disponibilità dei prodotti. Ti consente di impostare quantità massime di acquisto specifiche per un prodotto entro un intervallo di date e orari definito. Questo è cruciale per gestire scorte limitate, creare urgenza per le promozioni o gestire la disponibilità di prodotti speciali.

## 3. Requisiti e Compatibilità
-   **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x
-   **Compatibilità PHP**: PHP 7.1 - 8.5
-   **Requisiti di hosting**: Sono richieste estensioni PHP standard (cURL, JSON, OpenSSL). Queste sono comuni e solitamente abilitate per impostazione predefinita sulla maggior parte degli ambienti di hosting compatibili con PrestaShop.

## 4. Panoramica completa della configurazione (ogni impostazione raggruppata per schermata)

### 4.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)
Questa è la schermata di configurazione iniziale che incontri dopo aver installato il modulo o cliccando su "Configura" dal Gestore moduli.

-   **Cosa fa questa impostazione:** Questa pagina contiene tipicamente un semplice interruttore per abilitare o disabilitare la funzionalità complessiva del modulo.
-   **Effetto della modifica di questa impostazione:**
    -   *Quando abilitato:* Il modulo controllerà e applicherà attivamente i limiti di quantità del prodotto che definisci.
    -   *Quando disabilitato:* Il modulo sarà inattivo e non verranno applicati limiti di quantità, indipendentemente dalle regole che hai impostato.
-   **Valore consigliato:** "SÌ" (Abilitato) per assicurarti che il modulo sia attivo e applichi le tue regole di quantità.
-   **Scenario/esempio del commerciante:** Dopo l'installazione, devi assicurarti che questa impostazione sia abilitata per iniziare a utilizzare le funzionalità del modulo. Se hai mai bisogno di sospendere temporaneamente tutti i limiti di quantità (ad esempio, durante una finestra di manutenzione del sito), puoi disabilitarlo qui.

### 4.2 Schermata di amministrazione dedicata: Limite di quantità di acquisto del prodotto per data (Back Office > Catalogo > Limite di quantità di acquisto del prodotto per data)
Questo è il centro nevralgico per creare, gestire e rivedere tutti i tuoi limiti di quantità di prodotto basati sulla data.

**Nome schermata e posizione nel menu:**
Puoi accedere a questa schermata navigando su **Catalogo > Limite di quantità di acquisto del prodotto per data** nel menu del tuo Back Office di PrestaShop.

**Azioni e impostazioni disponibili:**
Questa schermata visualizza un elenco di tutte le regole di limite di quantità esistenti. Da qui, puoi aggiungere nuove regole, modificare quelle esistenti o eliminarle.

#### **Colonne della tabella di elenco:**
-   **ID:** Un identificatore interno univoco per ogni specifica regola di limite di quantità. Utile per riferimento tecnico.
-   **Prodotto:** Il nome del prodotto a cui si applica questa specifica regola. Questo ti aiuta a identificare rapidamente quale prodotto viene limitato.
-   **Data da:** La data e l'ora esatte (es. "2024-08-01 09:00:00") in cui questo limite di quantità inizia ad essere applicato.
-   **Data a:** La data e l'ora esatte (es. "2024-08-07 17:00:00") in cui questo limite di quantità smette di essere applicato.
-   **Quantità:** Il numero massimo di unità del prodotto specificato che un cliente può acquistare entro il periodo "Data da" e "Data a".
-   **Attivo:** Un semplice indicatore "Sì" o "No" (spesso un interruttore a levetta) che mostra se la regola è attualmente abilitata.

#### **Aggiunta/Modifica di una regola di limite di quantità:**
Quando clicchi sul pulsante "Aggiungi nuovo" o clicchi per modificare una regola esistente, apparirà un modulo con i seguenti campi:

-   **Limite di quantità di acquisto del prodotto per data:** Questo è il titolo del modulo, che indica che stai definendo un nuovo limite o modificandone uno esistente.
-   **ID Prodotto:**
    -   **Cosa fa questa impostazione:** Questo è un campo di ricerca in cui digiti il nome o l'ID del prodotto a cui vuoi applicare il limite. Mentre digiti, appariranno suggerimenti, permettendoti di selezionare il prodotto corretto.
    -   **Effetto della modifica di questa impostazione:** Collega direttamente questa regola di limite di quantità a un prodotto specifico nel tuo catalogo.
    -   **Valore consigliato:** Seleziona sempre il prodotto esatto che intendi limitare.
    -   **Scenario/esempio del commerciante:** Stai facendo una promozione speciale su "Chicchi di caffè biologici". Digiteresti "Chicchi di caffè biologici" e lo selezioneresti dal menu a discesa.
-   **Data da:**
    -   **Cosa fa questa impostazione:** Ti consente di scegliere la data e l'ora precise in cui questa restrizione di quantità dovrebbe iniziare. Tipicamente include un selettore di data e un selettore di ora.
    -   **Effetto della modifica di questa impostazione:** Il modulo inizierà ad applicare il limite di quantità solo per gli acquisti effettuati a partire da questa data e ora specifiche.
    -   **Valore consigliato:** Imposta questo valore all'inizio esatto del tuo periodo promozionale o quando la restrizione dovrebbe entrare in vigore.
    -   **Scenario/esempio del commerciante:** Vuoi che un limite inizi all'inizio di una giornata lavorativa, quindi lo imposti su "2024-09-01 00:00:00".
-   **Data a:**
    -   **Cosa fa questa impostazione:** Ti consente di scegliere la data e l'ora precise in cui questa restrizione di quantità dovrebbe terminare. Simile a "Data da", include un selettore di data e un selettore di ora.
    -   **Effetto della modifica di questa impostazione:** Dopo questa data e ora specifiche, il limite di quantità definito in questa regola non sarà più attivo e i clienti potranno acquistare qualsiasi stock disponibile.
    -   **Valore consigliato:** Imposta questo valore alla fine esatta del tuo periodo promozionale o quando la restrizione dovrebbe essere rimossa.
    -   **Scenario/esempio del commerciante:** Vuoi che il limite termini alla chiusura di una giornata lavorativa, quindi lo imposti su "2024-09-07 23:59:59".
-   **Quantità:**
    -   **Cosa fa questa impostazione:** Questo è un campo di input numerico in cui specifichi il numero massimo di unità del prodotto selezionato che un singolo cliente può acquistare entro l'intervallo "Data da" e "Data a" definito.
    -   **Effetto della modifica di questa impostazione:** Questo valore è il fulcro della restrizione. Se un cliente tenta di aggiungere più di questa quantità al carrello (o ne ha già di più nel carrello) durante il periodo attivo, il modulo interverrà.
    -   **Valore consigliato:** La quantità massima specifica che desideri consentire. Ad esempio, "1" per un limite di uno per cliente, o "10" per un limite di acquisto all'ingrosso.
    -   **Scenario/esempio del commerciante:** Per garantire una distribuzione equa di un articolo in edizione limitata, imposti la quantità a "2" per cliente.
-   **Attivo (interruttore On/Off):**
    -   **Cosa fa questa impostazione:** Questo è un interruttore a levetta (spesso etichettato "On" e "Off") che controlla se questa specifica regola di limite di quantità è attualmente attiva e applicata dal modulo.
    -   **Effetto della modifica di questa impostazione:**
        -   *On:* La regola è attiva e applicherà il suo limite di quantità durante il suo intervallo di date specificato.
        -   *Off:* La regola è inattiva e non applicherà alcun limite di quantità, anche se il suo intervallo di date è corrente. Questo è utile per preparare le regole in anticipo o sospenderle temporaneamente senza eliminarle.
    -   **Valore consigliato:** "On" per le regole che vuoi siano attive, "Off" per le regole che stai preparando o che hai temporaneamente sospeso.
    -   **Scenario/esempio del commerciante:** Hai creato una regola per una vendita natalizia, ma la festività è ancora a un mese di distanza. Puoi impostarla su "Off" fino a quando non si avvicina la data, quindi attivarla quando sei pronto.
-   **Pulsante Salva:**
    -   **Cosa fa questa impostazione:** Invia tutte le modifiche apportate nel modulo al database.
    -   **Effetto della modifica di questa impostazione:** La nuova o aggiornata regola di limite di quantità verrà immediatamente applicata all'applicazione della quantità di prodotto del tuo negozio.

**Effetto delle modifiche:**
-   **Aggiunta di una nuova regola:** Verrà creata una nuova restrizione. Se contrassegnata come "Attiva" e all'interno del suo intervallo di date, inizierà immediatamente a limitare gli acquisti per il prodotto specificato.
-   **Modifica di una regola esistente:** Qualsiasi modifica al prodotto, alle date, alla quantità o allo stato attivo si rifletterà istantaneamente nel modo in cui il modulo applica i limiti.
-   **Eliminazione di una regola:** Il limite di quantità verrà rimosso in modo permanente e il prodotto non sarà più soggetto a quella specifica restrizione per quell'intervallo di date.

**Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
1.  **Identifica i prodotti per i limiti:** Determina quali prodotti richiedono restrizioni di quantità (ad esempio, nuovi arrivi, articoli in saldo, prodotti molto richiesti).
2.  **Definisci i parametri:** Per ogni prodotto, decidi la quantità massima e le date/ore precise di inizio e fine della restrizione.
3.  **Crea regole:** Naviga su **Catalogo > Limite di quantità di acquisto del prodotto per data** e clicca su "Aggiungi nuovo". Compila attentamente tutti i campi, assicurandoti che le date e gli orari siano accurati. Imposta "Attivo" su "On".
4.  **Rivedi e testa:** Dopo aver creato le regole, testale sul tuo front office (ad esempio, prova ad aggiungere più della quantità consentita al carrello) per assicurarti che funzionino come previsto.
5.  **Monitora e regola:** Tieni d'occhio le tue vendite e il tuo inventario. Se una promozione viene estesa o le scorte cambiano, aggiorna i campi "Data a" o "Quantità" delle tue regole secondo necessità. Usa l'interruttore "Attivo" per disabilitare temporaneamente le regole senza eliminarle se le circostanze cambiano.

### 4.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista                                       | Impostazione / Opzione                     | Predefinito / Consigliato | Scopo e Impatto
