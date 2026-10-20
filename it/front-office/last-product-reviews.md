---
title: "Ultime recensioni prodotti - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Ultime recensioni prodotti di MyPresta.eu."
sidebar:
  label: "Ultime recensioni prodotti - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Last product reviews su MyPresta.eu](https://mypresta.eu/modules/front-office-features/last-product-reviews.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/last-product-reviews/)
>
> ---


# Ultime recensioni prodotti

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti per questo modulo.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Questa è la schermata di configurazione principale per il modulo "Ultime recensioni prodotti". Qui troverai tutte le impostazioni per controllare come e dove vengono visualizzate le tue recensioni.

#### **Visualizza recensioni in**

-   **Cosa fa questa impostazione:** Questa opzione determina dove apparirà il blocco "Ultime recensioni prodotti" sul tuo sito web. Puoi scegliere tra diverse posizioni standard di hook di PrestaShop.
-   **Effetto della modifica di questa impostazione:**
    *   *Se impostato su "Intestazione":* Il blocco delle recensioni apparirà nella parte superiore del tuo negozio, spesso sopra o sotto la navigazione principale. Questo offre la massima visibilità.
    *   *Se impostato su "Colonna sinistra":* Il blocco delle recensioni apparirà nella barra laterale sinistra del tuo negozio, se il tuo tema ne ha una.
    *   *Se impostato su "Colonna destra":* Il blocco delle recensioni apparirà nella barra laterale destra del tuo negozio, se il tuo tema ne ha una.
    *   *Se impostato su "Pagina prodotto":* Il blocco delle recensioni apparirà sulle singole pagine dei prodotti. Questo è ottimo per il cross-selling o per mostrare una prova sociale generale mentre un cliente sta considerando un acquisto.
    *   *Se impostato su "Piè di pagina":* Il blocco delle recensioni apparirà nella parte inferiore di ogni pagina, tipicamente sopra le informazioni sul copyright.
-   **Valore consigliato:** "Colonna sinistra" o "Colonna destra" per visibilità generale, o "Pagina prodotto" se vuoi enfatizzare le recensioni durante il processo decisionale di acquisto. "Intestazione" può essere molto efficace ma potrebbe occupare troppo spazio prezioso a seconda del tuo tema.
-   **Scenario / esempio per il commerciante:** Se vuoi che i clienti vedano le recensioni recenti indipendentemente da dove navigano, scegli "Colonna sinistra". Se vuoi incoraggiare gli acquisti sulle pagine dei prodotti, seleziona "Pagina prodotto".

#### **Numero di recensioni da visualizzare**

-   **Cosa fa questa impostazione:** Controlla quante singole recensioni di prodotti verranno mostrate nel blocco "Ultime recensioni prodotti".
-   **Effetto della modifica di questa impostazione:**
    *   *Se impostato su un numero basso (es. 3):* Il blocco sarà compatto, mostrando solo poche recensioni. Questo è utile per risparmiare spazio ma potrebbe non trasmettere molta prova sociale.
    *   *Se impostato su un numero più alto (es. 10):* Il blocco sarà più grande, visualizzando più recensioni. Questo offre più prova sociale ma richiede più spazio sullo schermo.
-   **Valore consigliato:** 3-5 per le colonne, 5-8 per l'intestazione/piè di pagina, a seconda del layout del tuo tema e dello spazio disponibile.
-   **Scenario / esempio per il commerciante:** Se la tua colonna sinistra è stretta, impostala su 3 per evitare che il blocco diventi troppo lungo. Se hai un piè di pagina ampio, potresti impostarlo su 6 per mostrare più feedback.

#### **Visualizza nome cliente**

-   **Cosa fa questa impostazione:** Questo interruttore determina se il nome del cliente che ha lasciato la recensione sarà visibile nel blocco delle recensioni.
-   **Effetto della modifica di questa impostazione:**
    *   *Se abilitato (SÌ):* Ogni recensione mostrerà il nome del cliente (es. "Recensione di Mario Rossi"). Questo aggiunge autenticità e personalizzazione.
    *   *Se disabilitato (NO):* Il nome del cliente sarà nascosto e verranno mostrati solo il contenuto della recensione e il prodotto. Questo potrebbe essere preferito per la privacy o per un design più minimalista.
-   **Valore consigliato:** SÌ. La visualizzazione dei nomi dei clienti aggiunge credibilità e rende le recensioni più genuine.
-   **Scenario / esempio per il commerciante:** Per massimizzare la fiducia, abilita questa opzione. Se sei preoccupato per la privacy dei clienti o preferisci un aspetto molto pulito, potresti disabilitarla.

#### **Visualizza nome prodotto**

-   **Cosa fa questa impostazione:** Questo interruttore controlla se il nome del prodotto recensito verrà visualizzato insieme al testo della recensione.
-   **Effetto della modifica di questa impostazione:**
    *   *Se abilitato (SÌ):* Ogni recensione indicherà chiaramente a quale prodotto si riferisce (es. "Prodotto: Super Widget"). Questo aiuta i clienti a comprendere il contesto della recensione.
    *   *Se disabilitato (NO):* Verranno mostrati solo il testo della recensione e il nome del cliente (se abilitato), senza menzionare esplicitamente il prodotto. Questo rende il blocco più generico.
-   **Valore consigliato:** SÌ. È fondamentale che i clienti sappiano quale prodotto viene recensito.
-   **Scenario / esempio per il commerciante:** Se un cliente vede una recensione entusiasta, vorrà sapere di quale prodotto si tratta. Abilitando questa opzione, potrà cliccare e potenzialmente acquistare quell'articolo specifico.

#### **Visualizza contenuto recensione**

-   **Cosa fa questa impostazione:** Questo interruttore determina se il testo effettivo della recensione del cliente verrà mostrato nel blocco.
-   **Effetto della modifica di questa impostazione:**
    *   *Se abilitato (SÌ):* Verrà visualizzato il testo completo o troncato della recensione. Questo fornisce un feedback dettagliato ai potenziali acquirenti.
    *   *Se disabilitato (NO):* Verranno mostrati solo la valutazione (stelle), il nome del cliente e il nome del prodotto, senza la recensione scritta. Questo crea un blocco molto compatto, concentrandosi solo sulle valutazioni a stelle.
-   **Valore consigliato:** SÌ. Il contenuto della recensione è la parte più preziosa della prova sociale.
-   **Scenario / esempio per il commerciante:** Per dare ai clienti una rapida panoramica di ciò che gli altri dicono, abilita questa opzione. Se vuoi mostrare solo le valutazioni a stelle come un rapido segnale di fiducia, potresti disabilitarla.

#### **Visualizza stelle recensione**

-   **Cosa fa questa impostazione:** Questo interruttore controlla se la valutazione a stelle (es. 5 su 5 stelle) associata a ogni recensione sarà visibile.
-   **Effetto della modifica di questa impostazione:**
    *   *Se abilitato (SÌ):* La valutazione a stelle sarà visualizzata in modo prominente per ogni recensione. Questo è un rapido indicatore visivo della qualità del prodotto.
    *   *Se disabilitato (NO):* La valutazione a stelle sarà nascosta e verrà mostrato solo il contenuto testuale (se abilitato). Questo non è generalmente raccomandato in quanto le valutazioni a stelle sono un segnale di fiducia universale.
-   **Valore consigliato:** SÌ. Le valutazioni a stelle sono incredibilmente efficaci per trasmettere rapidamente la soddisfazione del prodotto.
-   **Scenario / esempio per il commerciante:** Abilita sempre questa opzione per dare ai clienti un'indicazione visiva istantanea della qualità del prodotto e della soddisfazione del cliente.

#### **Visualizza immagine prodotto**

-   **Cosa fa questa impostazione:** Questo interruttore determina se l'immagine principale del prodotto recensito verrà mostrata accanto alla sua recensione.
-   **Effetto della modifica di questa impostazione:**
    *   *Se abilitato (SÌ):* Una piccola miniatura dell'immagine del prodotto apparirà con ogni recensione. Questo rende il blocco più accattivante visivamente e aiuta i clienti a identificare rapidamente il prodotto.
    *   *Se disabilitato (NO):* Non verrà mostrata alcuna immagine del prodotto, rendendo il blocco più incentrato sul testo.
-   **Valore consigliato:** SÌ. Le immagini dei prodotti migliorano significativamente l'attrattiva visiva e la chiarezza del blocco delle recensioni.
-   **Scenario / esempio per il commerciante:** Per rendere il tuo blocco recensioni più coinvolgente e aiutare i clienti ad associare rapidamente le recensioni a prodotti specifici, abilita le immagini dei prodotti.

#### **Visualizza prezzo prodotto**

-   **Cosa fa questa impostazione:** Questo interruttore controlla se il prezzo corrente del prodotto recensito verrà visualizzato nel blocco delle recensioni.
-   **Effetto della modifica di questa impostazione:**
    *   *Se abilitato (SÌ):* Verrà mostrato il prezzo del prodotto. Questo può essere utile per i clienti sensibili al prezzo o che desiderano vedere rapidamente se un prodotto recensito rientra nel loro budget.
    *   *Se disabilitato (NO):* Il prezzo non verrà visualizzato, mantenendo l'attenzione esclusivamente sulla recensione e sui dettagli del prodotto.
-   **Valore consigliato:** NO, a meno che tu non voglia specificamente evidenziare i prezzi dei prodotti nel blocco delle recensioni. A volte può ingombrare la visualizzazione.
-   **Scenario / esempio per il commerciante:** Se stai facendo una vendita e vuoi evidenziare i prodotti recensiti che sono attualmente scontati, potresti abilitare questa opzione. Altrimenti, è spesso meglio mantenere l'attenzione sulla recensione stessa.

#### **Visualizza link prodotto**

-   **Cosa fa questa impostazione:** Questo interruttore determina se il nome del prodotto (o l'immagine, se abilitata) nel blocco delle recensioni sarà un link cliccabile che porta il cliente direttamente alla pagina del prodotto.
-   **Effetto della modifica di questa impostazione:**
    *   *Se abilitato (SÌ):* I clienti possono cliccare sul nome/immagine del prodotto per navigare alla pagina completa del prodotto, dove possono saperne di più e potenzialmente effettuare un acquisto. Questo è cruciale per generare traffico verso le pagine dei prodotti.
    *   *Se disabilitato (NO):* Il nome/immagine del prodotto sarà un testo/immagine statico e i clienti non potranno cliccare. Ciò riduce la capacità del modulo di generare conversioni.
-   **Valore consigliato:** SÌ. Abilita sempre questa opzione per consentire ai clienti di esplorare facilmente i prodotti recensiti.
-   **Scenario / esempio per il commerciante:** Un cliente vede un'ottima recensione per un "Altoparlante Bluetooth". Se il nome del prodotto è cliccabile, può andare immediatamente alla pagina dell'altoparlante per acquistarlo.

#### **Visualizza data recensione**

-   **Cosa fa questa impostazione:** Questo interruttore controlla se la data di invio della recensione verrà visualizzata.
-   **Effetto della modifica di questa impostazione:**
    *   *Se abilitato (SÌ):* Verrà mostrata la data (es. "Recensito il 26-10-2023"). Questo aggiunge trasparenza e assicura ai clienti che le recensioni sono recenti e pertinenti.
    *   *Se disabilitato (NO):* La data sarà nascosta.
-   **Valore consigliato:** SÌ. Le recensioni recenti sono più efficaci e affidabili.
-   **Scenario / esempio per il commerciante:** Mostrare la data aiuta i clienti a vedere che il tuo negozio è attivo e riceve costantemente nuovi feedback, costruendo fiducia.

#### **Visualizza titolo recensione**

-   **Cosa fa questa impostazione:** Questo interruttore determina se il titolo della recensione (se i clienti ne forniscono uno) verrà visualizzato.
-   **Effetto della modifica di questa impostazione:**
    *   *Se abilitato (SÌ):* Se una recensione ha un titolo (es. "Prodotto fantastico!"), verrà mostrato, spesso in grassetto, fornendo un rapido riassunto del sentimento della recensione.
    *   *Se disabilitato (NO):* Verrà mostrato solo il contenuto principale della recensione, senza un titolo separato.
-   **Valore consigliato:** SÌ. I titoli delle recensioni sono eccellenti per catturare rapidamente l'attenzione e riassumere l'essenza della recensione.
-   **Scenario / esempio per il commerciante:** Un cliente che scorre rapidamente le recensioni può cogliere l'essenza da titoli come "Ottimo rapporto qualità-prezzo" o "Deluso" prima di leggere il testo completo.

#### **Valutazione minima da visualizzare**

-   **Cosa fa questa impostazione:** Questo filtro ti consente di impostare una valutazione minima a stelle per le recensioni da includere nel blocco "Ultime recensioni prodotti".
-   **Effetto della modifica di questa impostazione:**
    *   *Se impostato su 1 stella:* Verranno visualizzate tutte le recensioni (da 1 a 5 stelle).
    *   *Se impostato su 3 stelle:* Verranno visualizzate solo le recensioni con 3, 4 o 5 stelle. Le recensioni con 1 o 2 stelle verranno escluse.
    *   *Se impostato su 5 stelle:* Verranno visualizzate solo le recensioni perfette a 5 stelle.
-   **Valore consigliato:** 3 o 4 stelle. Sebbene la trasparenza sia buona, potresti voler evidenziare principalmente il feedback positivo in questo blocco prominente.
-   **Scenario / esempio per il commerciante:** Per assicurarti che il tuo blocco "Ultime recensioni prodotti" mostri sempre feedback positivo, impostalo su 4 stelle. Questo aiuta a mantenere un'immagine positiva pur essendo autentico.

#### **Visualizza solo recensioni dalla categoria selezionata**

-   **Cosa fa questa impostazione:** Questa opzione ti consente di filtrare le recensioni visualizzate in modo che siano solo quelle associate a prodotti di una categoria specifica.
-   **Effetto della modifica di questa impostazione:**
    *   *Quando è selezionato "No":* Le recensioni di tutte le categorie verranno considerate per la visualizzazione.
    *   *Quando è selezionata una categoria specifica (es. "Elettronica"):* Verranno mostrate solo le recensioni per i prodotti all'interno della categoria "Elettronica" (e delle sue sottocategorie).
-   **Valore consigliato:** "No" per una prova sociale generale. Seleziona una categoria se il blocco delle recensioni è posizionato in un contesto in cui sono rilevanti solo tipi di prodotti specifici (es. su una pagina di categoria).
-   **Scenario / esempio per il commerciante:** Se posizioni il blocco delle recensioni sulla pagina della tua categoria "T-shirt", potresti selezionare qui la categoria "T-shirt" per assicurarti che vengano mostrate solo le recensioni pertinenti, migliorando l'esperienza del cliente.

#### **Visualizza solo recensioni dal prodotto selezionato**

-   **Cosa fa questa impostazione:** Questa opzione ti consente di filtrare le recensioni visualizzate in modo che siano solo quelle associate a un prodotto specifico.
-   **Effetto della modifica di questa impostazione:**
    *   *Quando è selezionato "No":* Le recensioni per tutti i prodotti verranno considerate per la visualizzazione.
    *   *Quando è selezionato un prodotto specifico (es. "Il mio fantastico gadget"):* Verranno mostrate solo le recensioni per "Il mio fantastico gadget".
-   **Valore consigliato:** "No" per una prova sociale generale. Seleziona un prodotto se il blocco delle recensioni è posizionato in un contesto in cui sono rilevanti solo le recensioni di un singolo prodotto (es. su una pagina di destinazione personalizzata per quel prodotto).
-   **Scenario / esempio per il commerciante:** Se hai una pagina promozionale speciale per la tua "Macchina da caffè più venduta", potresti configurare questo blocco per mostrare solo le recensioni per quella specifica macchina da caffè su quella pagina.

#### **Visualizza recensioni come slider**

-   **Cosa fa questa impostazione:** Questo interruttore abilita o disabilita uno slider dinamico (carosello) per il blocco delle recensioni.
-   **Effetto della modifica di questa impostazione:**
    *   *Se abilitato (SÌ):* Le recensioni scorreranno automaticamente o consentiranno ai clienti di navigare tra di esse utilizzando frecce/punti. Questo è ottimo per visualizzare molte recensioni in uno spazio compatto.
    *   *Se disabilitato (NO):* Le recensioni verranno visualizzate come un elenco statico, una dopo l'altra.
-   **Valore consigliato:** SÌ, specialmente se visualizzi più di 3-4 recensioni o se il blocco si trova in una colonna stretta.
-   **Scenario / esempio per il commerciante:** Se vuoi mostrare 8 recensioni nella tua colonna sinistra ma non vuoi che la colonna diventi eccessivamente lunga, abilitare lo slider la renderà compatta e interattiva.

#### **Riproduzione automatica dello slider**

-   **Cosa fa questa impostazione:** Se "Visualizza recensioni come slider" è abilitato, questa impostazione controlla se lo slider si sposta automaticamente alla recensione successiva senza interazione dell'utente.
-   **Effetto della modifica di questa impostazione:**
    *   *Se abilitato (SÌ):* Lo slider passerà automaticamente tra le recensioni dopo un ritardo impostato.
    *   *Se disabilitato (NO):* Lo slider si muoverà solo quando il cliente clicca sulle frecce di navigazione o sui punti.
-   **Valore consigliato:** SÌ, ma assicurati che la "Velocità di riproduzione automatica dello slider" sia impostata su una durata ragionevole.
-   **Scenario / esempio per il commerciante:** Per mantenere il blocco delle recensioni dinamico e assicurare che tutte le recensioni ottengano visibilità, abilita la riproduzione automatica.

#### **Velocità di riproduzione automatica dello slider (in ms)**

-   **Cosa fa questa impostazione:** Se "Riproduzione automatica dello slider" è abilitato, questa impostazione determina per quanto tempo (in millisecondi) ogni recensione viene visualizzata prima che lo slider passi automaticamente alla successiva.
-   **Effetto della modifica di questa impostazione:**
    *   *Un numero inferiore (es. 2000ms = 2 secondi):* Le recensioni cambieranno rapidamente.
    *   *Un numero superiore (es. 5000ms = 5 secondi):* Le recensioni rimarranno visibili più a lungo, dando ai clienti più tempo per leggere.
-   **Valore consigliato:** 4000-6000 (4-6 secondi) per dare ai clienti abbastanza tempo per leggere una recensione senza sentirsi affrettati.
-   **Scenario / esempio per il commerciante:** Imposta questo valore a 5000ms in modo che i clienti abbiano tutto il tempo per leggere ogni recensione mentre scorre.

#### **Controlli dello slider**

-   **Cosa fa questa impostazione:** Se "Visualizza recensioni come slider" è abilitato, questo controlla se le frecce di navigazione (sinistra/destra) sono visibili per consentire ai clienti di sfogliare manualmente le recensioni.
-   **Effetto della modifica di questa impostazione:**
    *   *Se abilitato (SÌ):* Le frecce appariranno sullo slider, consentendo la navigazione manuale.
    *   *Se disabilitato (NO):* Non verranno mostrate frecce. I clienti potranno fare affidamento solo sulla riproduzione automatica (se abilitata) o sui gesti touch/swipe.
-   **Valore consigliato:** SÌ. Fornire controlli migliora l'esperienza utente, anche con la riproduzione automatica.
-   **Scenario / esempio per il commerciante:** Per dare ai clienti il pieno controllo sulla navigazione delle recensioni, abilita i controlli dello slider.

#### **Paginazione dello slider**

-   **Cosa fa questa impostazione:** Se "Visualizza recensioni come slider" è abilitato, questo controlla se sono visibili piccoli punti (paginazione), che indicano il numero totale di recensioni e la recensione corrente visualizzata.
-   **Effetto della modifica di questa impostazione:**
    *   *Se abilitato (SÌ):* Appariranno dei punti, mostrando i progressi e consentendo salti diretti a recensioni specifiche.
    *   *Se disabilitato (NO):* Non verranno mostrati punti.
-   **Valore consigliato:** SÌ. I pager forniscono un'indicazione visiva chiara di quante recensioni sono disponibili e dove si trova il cliente nella sequenza.
-   **Scenario / esempio per il commerciante:** Per aiutare i clienti a capire quante recensioni ci sono nello slider e a saltare facilmente a una specifica, abilita la paginazione dello slider.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Visualizza recensioni in | Colonna sinistra / Colonna destra | Controlla la posizione del blocco recensioni nel tuo negozio. |
| Configurazione modulo | Numero di recensioni da visualizzare | 3-5 (colonne), 5-8 (intestazione/piè di pagina) | Imposta quante recensioni sono visibili nel blocco. |
| Configurazione modulo | Visualizza nome cliente | SÌ | Mostra il nome del recensore per autenticità. |
| Configurazione modulo | Visualizza nome prodotto | SÌ | Collega chiaramente la recensione al suo prodotto. |
| Configurazione modulo | Visualizza contenuto recensione | SÌ | Mostra il testo effettivo della recensione. |
| Configurazione modulo | Visualizza stelle recensione | SÌ | Indicatore visivo della valutazione del prodotto. |
| Configurazione modulo | Visualizza immagine prodotto | SÌ | Rende il blocco più accattivante visivamente e identificabile. |
| Configurazione modulo | Visualizza prezzo prodotto | NO | Mostra il prezzo del prodotto (può ingombrare, di solito non necessario). |
| Configurazione modulo | Visualizza link prodotto | SÌ | Consente ai clienti di cliccare per accedere alla pagina del prodotto. |
| Configurazione modulo | Visualizza data recensione | SÌ | Mostra quando la recensione è stata inviata, provando la sua attualità. |
| Configurazione modulo | Visualizza titolo recensione | SÌ | Visualizza il titolo della recensione per riassunti rapidi. |
| Configurazione modulo | Valutazione minima da visualizzare | 3 o 4 stelle | Filtra le recensioni con valutazioni più basse per una visualizzazione positiva. |
| Configurazione modulo | Visualizza solo recensioni dalla categoria selezionata | No | Filtra le recensioni per categoria di prodotto. |
| Configurazione modulo | Visualizza solo recensioni dal prodotto selezionato | No | Filtra le recensioni per un prodotto specifico. |
| Configurazione modulo | Visualizza recensioni come slider | SÌ | Presenta le recensioni in un carosello dinamico e scorrevole. |
| Configurazione modulo | Riproduzione automatica dello slider | SÌ | Fa avanzare automaticamente lo slider. |
| Configurazione modulo | Velocità di riproduzione automatica dello slider (in ms) | 4000-6000 | Imposta la durata di visualizzazione di ogni recensione nello slider. |
| Configurazione modulo | Controlli dello slider | SÌ | Mostra le frecce di navigazione per il controllo manuale dello slider. |
| Configurazione modulo | Paginazione dello slider | SÌ | Mostra i punti per la paginazione dello slider. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho configurato il modulo, ma il blocco delle recensioni non appare nel mio negozio.**
R:

1.  **Controlla la posizione del modulo:** Vai su **Design > Posizioni** (o **Moduli > Posizioni** nelle versioni precedenti di PrestaShop) nel tuo Back Office. Cerca `displayLastReviews` (o l'hook che hai selezionato nella configurazione del modulo). Assicurati che il modulo "Ultime recensioni prodotti" sia elencato e abilitato per quell'hook. In caso contrario, clicca su "Trapianta un modulo" e aggiungilo all'hook desiderato.
2.  **Svuota la cache:** PrestaShop spesso memorizza i contenuti nella cache. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" (o sui pulsanti "Svuota cache Smarty" e "Svuota cache").
3.  **Verifica la presenza di recensioni:** Assicurati di avere effettivamente recensioni di prodotti approvate nel tuo negozio. Il modulo può visualizzare solo le recensioni esistenti e visibili.
4.  **Compatibilità del tema:** Sebbene il modulo sia progettato per essere compatibile, alcuni temi altamente personalizzati potrebbero richiedere piccole modifiche CSS. Controlla la console per sviluppatori del tuo browser per eventuali errori JavaScript.

**D: Le recensioni vengono visualizzate, ma non hanno un aspetto corretto (ad esempio, stile errato, immagini troppo grandi).**
R:

1.  **Conflitti del tema:** Il CSS del tuo tema potrebbe sovrascrivere gli stili del modulo. Puoi provare ad aggiungere CSS personalizzato al file `custom.css` del tuo tema (se ne ha uno) o modificare direttamente `lastreviews/views/css/lastreviews.css` (anche se questo non è sicuro per gli aggiornamenti).
2.  **Dimensioni delle immagini:** Se le immagini dei prodotti sono troppo grandi, controlla le impostazioni delle immagini del tuo tema o il CSS del modulo. Il modulo utilizza una dimensione immagine standard, ma il tuo tema potrebbe renderla in modo diverso.
3.  **Problemi dello slider:** Se lo slider non funziona, assicurati che "Visualizza recensioni come slider" sia abilitato. Controlla la console del browser per errori JavaScript, poiché altri moduli o script del tema potrebbero essere in conflitto.

**D: Posso visualizzare recensioni solo da un prodotto o una categoria specifica?**
R: Sì! Nella configurazione del modulo, hai le opzioni "Visualizza solo recensioni dalla categoria selezionata" e "Visualizza solo recensioni dal prodotto selezionato". Utilizza questi menu a discesa per filtrare le recensioni mostrate nel blocco.

**D: Le mie recensioni sono in più lingue. Il modulo le visualizzerà correttamente?**
R: Il modulo si basa sul sistema di recensioni standard di PrestaShop. Se le tue recensioni sono correttamente associate alle lingue in PrestaShop, il modulo dovrebbe visualizzare le recensioni nella lingua attiva del front-office. Assicurati che il tuo tema e PrestaShop siano correttamente configurati per contenuti multilingue.

**D: Come posso ottenere più recensioni da visualizzare?**
R: Questo modulo *visualizza* solo le recensioni esistenti. Per ottenere più recensioni, devi incoraggiare i clienti a lasciarle. Considera l'utilizzo di un modulo separato per i promemoria delle recensioni, offrendo incentivi o rendendo il processo di invio delle recensioni molto semplice sulle tue pagine prodotto.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Ultime recensioni prodotti" è un modulo PrestaShop standard che segue un modello simile a MVC. Funziona principalmente come una funzionalità di front-office, agganciandosi a vari punti di visualizzazione per renderizzare un blocco di recensioni recenti dei prodotti. Sfrutta la funzionalità principale `ProductComment` (o simile) di PrestaShop per recuperare i dati delle recensioni. La logica principale del modulo risiede in `index.php`, gestendo la configurazione e la registrazione degli hook, mentre i template e gli asset gestiscono la visualizzazione front-end. Utilizza una libreria JavaScript di terze parti, `lightslider.js`, per la funzionalità del carosello.

### 4.2 Controller (`controllers/`)

Questo modulo non contiene alcun controller personalizzato per il Front-Office o il Back-Office Admin. Tutta la configurazione è gestita direttamente all'interno del metodo `getContent()` della classe principale del modulo.

### 4.3 Classi e Modelli Core (`classes/`)

Questo modulo non definisce classi personalizzate o `ObjectModel` nella directory `classes/`. Si basa sulle tabelle core di PrestaShop per i commenti dei prodotti, tipicamente `ProductComment` (o equivalente, a seconda della versione di PrestaShop e se il modulo ufficiale Product Comments è installato).

### 4.4 Risorse JavaScript (`views/js/`)

-   **`lastreviews/lib/src/js/lightslider.js`**
    *   **Ambito:** Front-office.
    *   **Scopo:** Questa è la libreria JavaScript principale per la creazione di slider/caroselli di contenuti reattivi. Fornisce la funzionalità per la funzione "Visualizza recensioni come slider".
    *   **Funzionalità:** Si lega a un elemento `<ul>` (o contenitore simile) per trasformarlo in uno slider reattivo. Gestisce la riproduzione automatica, i controlli di navigazione (frecce), la paginazione (punti), i gesti touch/swipe e il ridimensionamento reattivo.
    *   **Dipendenze:** Tipicamente richiede jQuery.

### 4.5 Fogli di stile CSS (`views/css/`)

-   **`lastreviews/lib/src/css/lightslider.css`**
    *   **Ambito:** Stile del cliente del front-office.
    *   **Scopo:** Fornisce lo stile predefinito per la libreria `lightslider.js`, inclusi layout di base, frecce di navigazione, punti di paginazione e stili di animazione per lo slider.
    *   **Selettori chiave:** `.lightSlider`, `.lSAction > .lSPrev`, `.lSAction > .lSNext`, `.lSPager`, ecc. Gli sviluppatori possono sovrascriverli per adattarli all'estetica del loro tema.
-   **`lastreviews/views/css/lastreviews.css`**
    *   **Ambito:** Stile del cliente del front-office.
    *   **Scopo:** Contiene stili personalizzati specifici per il blocco di visualizzazione del modulo "Ultime recensioni prodotti". Questo include lo stile per il contenitore delle recensioni, i singoli elementi delle recensioni, le immagini dei prodotti, le valutazioni a stelle e gli elementi di testo.
    *   **Selettori chiave:** `.last-reviews-block`, `.last-review-item`, `.review-product-image`, `.review-stars`, `.review-customer-name`, `.review-product-name`, ecc. Questi selettori sono progettati per essere facilmente sovrascritti dal CSS di un tema personalizzato per l'integrazione.

### 4.6 Struttura del template Smarty (`views/templates/`)

-   **Template degli hook (`views/templates/hook/`)**:
    *   **`lastreviews/views/templates/hook/admin-tips.tpl`**
        *   **Scopo:** Questo template è probabilmente utilizzato nella pagina di configurazione del Back Office (`getContent()`) per visualizzare suggerimenti o istruzioni amministrative al commerciante. Non viene renderizzato nel front office.
        *   **Contenuto:** Tipicamente contiene HTML per messaggi informativi, link alla documentazione o avvisi.
    *   **`lastreviews/views/templates/hook/last-reviews.tpl`**
        *   **Scopo:** Questo è il template principale del front-office responsabile del rendering del blocco "Ultime recensioni prodotti". È agganciato a vari punti di visualizzazione (es. `displayLeftColumn`, `displayFooter`).
        *   **Dati:** Riceve un array di dati delle recensioni (nome cliente, nome prodotto, valutazione, contenuto, data, immagine, link) dalla logica PHP del modulo.
        *   **Struttura:** Itera attraverso le recensioni fornite, visualizzando condizionalmente gli elementi in base alla configurazione del modulo (es. nome cliente, immagine prodotto, slider). Include la struttura HTML necessaria per l'inizializzazione di `lightslider.js` se l'opzione slider è abilitata.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    *   Questo modulo non crea le proprie tabelle di database personalizzate. Si basa sulle tabelle core di PrestaShop per le recensioni dei prodotti, tipicamente `ps_product_comment` e tabelle correlate (se il modulo ufficiale Product Comments è installato e attivo).
    *   Le impostazioni di configurazione sono memorizzate nella tabella `ps_configuration`, con chiavi tipicamente prefissate da `LASTREVIEWS_` (es. `LASTREVIEWS_DISPLAY_IN`, `LASTREVIEWS_NUM_REVIEWS`).
-   **Tabella degli hook registrati**:

| Nome dell'Hook | Tempo di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di tutte le pagine del front-office. | Utilizzato per includere risorse CSS/JS e potenzialmente renderizzare il blocco delle recensioni nella parte superiore della pagina. |
| `displayLeftColumn` | Nella barra laterale sinistra delle pagine del front-office. | Renderizza il blocco delle recensioni nella colonna sinistra. |
| `displayRightColumn` | Nella barra laterale destra delle pagine del front-office. | Renderizza il blocco delle recensioni nella colonna destra. |
| `displayFooter` | Nella sezione del piè di pagina di tutte le pagine del front-office. | Renderizza il blocco delle recensioni nel piè di pagina. |
| `displayProductAdditionalInfo` (o hook simile per la pagina prodotto) | Sulla pagina del prodotto, tipicamente sotto le informazioni principali del prodotto. | Renderizza il blocco delle recensioni sulle singole pagine dei prodotti. |
| `actionFrontControllerSetMedia` | Eseguito quando un controller front-end imposta i suoi media (CSS/JS). | Utilizzato per registrare i file CSS e JavaScript del modulo (`lightslider.js`, `lastreviews.css`) da caricare nel front office. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Ultime recensioni prodotti", si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistervi con qualsiasi problema o domanda relativa alla funzionalità e compatibilità del modulo.
