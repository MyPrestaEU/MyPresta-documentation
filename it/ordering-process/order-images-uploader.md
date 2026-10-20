---
title: "Caricatore immagini ordine - Manuale del commerciante e guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Caricatore immagini ordine di MyPresta.eu."
sidebar:
  label: "Caricatore immagini ordine - Manuale del commerciante e guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Order images uploader su MyPresta.eu](https://mypresta.eu/modules/ordering-process/order-images-uploader.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/ordering-process/order-images-uploader/)
>
> ---


# Caricatore immagini ordine

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Assicurati che il tuo server abbia limiti di caricamento file adeguati configurati in `php.ini` (ad esempio, `upload_max_filesize`, `post_max_size`) per accogliere le dimensioni dei file che i tuoi clienti potrebbero caricare.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura > Caricatore immagini ordine)

Questa è la schermata di configurazione principale dove controlli il comportamento generale e l'aspetto del modulo.

#### Impostazioni generali

- **Abilita modulo:**

  - **Cosa fa questa impostazione:** Questo è l'interruttore principale per attivare o disattivare la funzionalità dell'intero modulo.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Le funzionalità del modulo (moduli di caricamento, gestione file) saranno attive nel tuo front office e back office.
    - *Quando disabilitato:* Tutte le funzionalità del modulo saranno nascoste ai clienti e agli amministratori, mettendo di fatto in pausa la sua operatività.
  - **Valore consigliato:** SÌ
  - **Scenario/esempio per il commerciante:** Se stai configurando il modulo per la prima volta, abilitalo per testare. Se hai bisogno di disabilitare temporaneamente i caricamenti di file per manutenzione, impostalo su NO.
- **Consenti ai clienti di caricare file:**

  - **Cosa fa questa impostazione:** Determina se ai clienti è consentito caricare file.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I clienti vedranno i moduli di caricamento e potranno inviare file.
    - *Quando disabilitato:* I clienti non vedranno alcuna opzione di caricamento, anche se il modulo è abilitato.
  - **Valore consigliato:** SÌ
  - **Scenario/esempio per il commerciante:** Se desideri utilizzare il modulo solo per la gestione interna dei file (ad esempio, gli amministratori che caricano file sugli ordini), potresti disabilitarlo. Per la maggior parte dei casi d'uso, i clienti devono caricare file, quindi mantienilo abilitato.
- **Consenti ai clienti ospiti di caricare file:**

  - **Cosa fa questa impostazione:** Controlla se i clienti non registrati (ospiti) possono caricare file.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Gli ospiti possono caricare file, tipicamente associati al loro carrello o ordine durante il checkout.
    - *Quando disabilitato:* Solo i clienti registrati e loggati possono caricare file.
  - **Valore consigliato:** SÌ (se consenti il checkout come ospite e hai bisogno di file dagli ospiti)
  - **Scenario/esempio per il commerciante:** Se il tuo negozio consente il checkout come ospite e richiede il caricamento di file per gli ordini degli ospiti (ad esempio, un lavoro di stampa rapido), abilita questa opzione. Se vuoi forzare i clienti a registrarsi per caricare file, disabilitala.
- **Consenti ai clienti di eliminare file:**

  - **Cosa fa questa impostazione:** Dà ai clienti la possibilità di rimuovere i file che hanno precedentemente caricato.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I clienti vedranno un'opzione "Elimina" accanto ai loro file caricati nel loro account.
    - *Quando disabilitato:* I clienti possono caricare ma non possono rimuovere file. Solo gli amministratori possono eliminarli.
  - **Valore consigliato:** NO (a meno che tu non ti fidi dei clienti per gestire perfettamente i loro file)
  - **Scenario/esempio per il commerciante:** Per ordini di stampa personalizzati, potresti voler disabilitare questa opzione per impedire ai clienti di eliminare accidentalmente un file già in produzione. Se i file sono temporanei o facilmente sostituibili, potresti abilitarla per comodità del cliente.
- **Consenti ai clienti di scaricare file:**

  - **Cosa fa questa impostazione:** Determina se i clienti possono scaricare i file che loro (o tu) avete caricato sui loro ordini.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I clienti possono cliccare per scaricare i loro file dalla cronologia degli ordini.
    - *Quando disabilitato:* I clienti non possono scaricare file.
  - **Valore consigliato:** SÌ (per trasparenza e accesso del cliente)
  - **Scenario/esempio per il commerciante:** Se carichi una prova o un design finale affinché il cliente lo riveda, abilitando questa opzione gli permetti di scaricarlo.
- **Consenti ai clienti di caricare file sugli ordini:**

  - **Cosa fa questa impostazione:** Controlla specificamente se i clienti possono caricare file *dopo* che un ordine è stato effettuato, dalla pagina della cronologia degli ordini.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Un'opzione di caricamento apparirà sulla pagina dei dettagli dell'ordine individuale del cliente nella sezione "Il mio account".
    - *Quando disabilitato:* I clienti possono caricare file solo durante il processo di carrello/checkout o sulle pagine dei prodotti, non sugli ordini esistenti.
  - **Valore consigliato:** SÌ (altamente raccomandato per flessibilità)
  - **Scenario/esempio per il commerciante:** Un cliente ha dimenticato di caricare un logo specifico dopo aver effettuato un ordine per magliette personalizzate. Con questa opzione abilitata, può facilmente aggiungerlo in seguito.
- **Consenti ai clienti di caricare file sui carrelli:**

  - **Cosa fa questa impostazione:** Controlla se i clienti possono caricare file mentre i loro articoli sono ancora nel carrello.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Un'opzione di caricamento apparirà sulla pagina del carrello.
    - *Quando disabilitato:* I clienti non possono caricare file sul loro carrello.
  - **Valore consigliato:** SÌ (comodo per i clienti)
  - **Scenario/esempio per il commerciante:** Un cliente sta creando un album fotografico personalizzato. Può caricare le foto direttamente nel carrello prima di procedere al checkout.
- **Consenti ai clienti di caricare file sui prodotti:**

  - **Cosa fa questa impostazione:** Controlla se i clienti possono caricare file direttamente sulle singole pagine dei prodotti.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Un'opzione di caricamento apparirà sulle pagine dei prodotti.
    - *Quando disabilitato:* I clienti non possono caricare file sulle pagine dei prodotti.
  - **Valore consigliato:** SÌ (per prodotti altamente personalizzabili)
  - **Scenario/esempio per il commerciante:** Per una tazza personalizzata, il cliente può caricare la foto desiderata direttamente sulla pagina del prodotto della tazza prima di aggiungerla al carrello.
- **Consenti ai clienti di caricare file sull'account cliente:**

  - **Cosa fa questa impostazione:** Abilita una sezione dedicata "I miei file" nell'account del cliente, consentendogli di caricare e gestire file non necessariamente legati a un ordine o carrello specifico.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Una nuova voce di menu "I miei file" appare nella dashboard "Il mio account" del cliente.
    - *Quando disabilitato:* Questa sezione è nascosta.
  - **Valore consigliato:** NO (a meno che tu non abbia una necessità specifica di archiviazione generale di file)
  - **Scenario/esempio per il commerciante:** Se desideri che i clienti pre-carichino risorse comuni (ad esempio, il logo della loro azienda) che potrebbero utilizzare in più ordini futuri, questo potrebbe essere utile. Altrimenti, potrebbe aggiungere complessità non necessaria.
- **Forza i clienti a caricare file sugli ordini:**

  - **Cosa fa questa impostazione:** Rende il caricamento dei file obbligatorio per il completamento di un ordine. Se non vengono caricati file, il cliente non può procedere.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I clienti saranno bloccati dal completare il checkout finché non caricheranno almeno un file.
    - *Quando disabilitato:* Il caricamento dei file è facoltativo.
  - **Valore consigliato:** NO (abilita solo se assolutamente critico per ogni ordine)
  - **Scenario/esempio per il commerciante:** Per una tipografia in cui *ogni* ordine richiede un file di design, abilitando questa opzione si garantisce che nessun ordine venga elaborato senza le risorse necessarie. Sii cauto, poiché ciò può influire sui tassi di conversione se non tutti i prodotti richiedono un file.
- **Forza i clienti a caricare file sui prodotti:**

  - **Cosa fa questa impostazione:** Rende il caricamento dei file obbligatorio per l'aggiunta di un prodotto al carrello.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I clienti non possono aggiungere un prodotto al carrello finché non caricano almeno un file per quel prodotto.
    - *Quando disabilitato:* Il caricamento dei file è facoltativo sulla pagina del prodotto.
  - **Valore consigliato:** NO (abilita solo per prodotti che sono *sempre* personalizzati)
  - **Scenario/esempio per il commerciante:** Per un prodotto "Disegna la tua maglietta", questo garantisce che il cliente fornisca il suo design prima di aggiungerlo al carrello.
- **Forza i clienti a caricare file sui carrelli:**

  - **Cosa fa questa impostazione:** Rende il caricamento dei file obbligatorio per l'elaborazione dell'intero carrello.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I clienti non possono procedere dal carrello al checkout finché non caricano almeno un file per il carrello.
    - *Quando disabilitato:* Il caricamento dei file è facoltativo sulla pagina del carrello.
  - **Valore consigliato:** NO (usa con estrema cautela, può influire gravemente sulla conversione)
  - **Scenario/esempio per il commerciante:** Questo è raramente raccomandato a meno che *ogni singolo ordine* nel tuo negozio non richieda un caricamento di file generale. Di solito è meglio forzare i caricamenti a livello di prodotto o di ordine, se necessario.
- **Estensioni file consentite (separate da virgola):**

  - **Cosa fa questa impostazione:** Definisce quali tipi di file i clienti sono autorizzati a caricare.
  - **Effetto della modifica di questa impostazione:**
    - *Quando modificato:* Saranno accettati solo i file con le estensioni specificate (ad esempio, `jpg,png,gif,pdf`). Qualsiasi altro tipo di file verrà rifiutato.
  - **Valore consigliato:** `jpg,jpeg,png,gif,pdf,doc,docx,xls,xlsx,txt` (regola in base alle tue esigenze)
  - **Scenario/esempio per il commerciante:** Una tipografia potrebbe consentire `jpg,png,pdf,ai,eps`. Una gioielleria personalizzata potrebbe aver bisogno solo di `jpg,png`. Limitare le estensioni migliora la sicurezza e garantisce la ricezione di file utilizzabili.
- **Dimensione massima del file (in MB):**

  - **Cosa fa questa impostazione:** Imposta il limite superiore per la dimensione di un singolo file che un cliente può caricare.
  - **Effetto della modifica di questa impostazione:**
    - *Quando modificato:* I file più grandi di questo limite verranno rifiutati.
  - **Valore consigliato:** `10` (o superiore se ti aspetti file di design di grandi dimensioni)
  - **Scenario/esempio per il commerciante:** Se i clienti caricano immagini ad alta risoluzione o file di design di grandi dimensioni, potresti impostarlo a `50` o `100`. Sii consapevole che file molto grandi possono rallentare i caricamenti e consumare spazio sul server. Assicurati che `upload_max_filesize` e `post_max_size` del tuo server in `php.ini` siano configurati per supportare questo valore.
- **Numero massimo di file per ordine:**

  - **Cosa fa questa impostazione:** Limita quanti singoli file un cliente può caricare per un singolo ordine.
  - **Effetto della modifica di questa impostazione:**
    - *Quando modificato:* Ai clienti verrà impedito di caricare più file una volta raggiunto questo limite per un dato ordine.
  - **Valore consigliato:** `5` (o superiore se si prevedono molti file)
  - **Scenario/esempio per il commerciante:** Se un cliente sta ordinando 10 articoli personalizzati diversi e ognuno necessita di un file, potresti impostarlo a `10` o `20`. Se di solito sono necessari solo uno o due file, un numero inferiore previene il disordine.
- **Numero massimo di file per prodotto:**

  - **Cosa fa questa impostazione:** Limita quanti singoli file un cliente può caricare per un singolo prodotto.
  - **Effetto della modifica di questa impostazione:**
    - *Quando modificato:* Ai clienti verrà impedito di caricare più file una volta raggiunto questo limite per un dato prodotto.
  - **Valore consigliato:** `1` (se ogni prodotto necessita di un design) o `5` (se sono necessarie più angolazioni/versioni)
  - **Scenario/esempio per il commerciante:** Per un ritratto personalizzato, potresti consentire `3` file (foto di riferimento fronte, lato, retro). Per una semplice stampa di logo, `1` file è sufficiente.
- **Numero massimo di file per carrello:**

  - **Cosa fa questa impostazione:** Limita quanti singoli file un cliente può caricare per l'intero carrello.
  - **Effetto della modifica di questa impostazione:**
    - *Quando modificato:* Ai clienti verrà impedito di caricare più file una volta raggiunto questo limite per il carrello.
  - **Valore consigliato:** `5` (o superiore se si prevedono molti file generici)
  - **Scenario/esempio per il commerciante:** Se un cliente sta caricando un documento di istruzioni generale che si applica all'intero carrello, potresti impostarlo a `1`.
- **Visualizza modulo di caricamento sulla pagina del prodotto:**

  - **Cosa fa questa impostazione:** Controlla dove appare il modulo di caricamento sulla pagina del prodotto.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su 'Nella scheda prodotto':* Il modulo di caricamento apparirà all'interno di una nuova scheda sulla pagina del prodotto (ad esempio, accanto a "Descrizione" o "Scheda tecnica").
    - *Quando impostato su 'Sotto la descrizione del prodotto':* Il modulo di caricamento apparirà direttamente sotto la descrizione principale del prodotto.
    - *Quando impostato su 'Sotto il prezzo del prodotto':* Il modulo di caricamento apparirà vicino al prezzo del prodotto, di solito sopra il pulsante "Aggiungi al carrello".
  - **Valore consigliato:** 'Nella scheda prodotto' (per una visualizzazione meno invasiva) o 'Sotto il prezzo del prodotto' (per alta visibilità)
  - **Scenario/esempio per il commerciante:** Per un prodotto in cui il caricamento di file è critico, posizionarlo "Sotto il prezzo del prodotto" lo rende altamente visibile. Per caricamenti meno critici, una "scheda prodotto" mantiene pulite le informazioni principali del prodotto.
- **Visualizza modulo di caricamento sulla pagina del carrello:**

  - **Cosa fa questa impostazione:** Controlla dove appare il modulo di caricamento sulla pagina del carrello.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su 'Nel blocco riepilogo':* Il modulo di caricamento apparirà all'interno dell'area di riepilogo principale del carrello.
    - *Quando impostato su 'Sotto il riepilogo del carrello':* Il modulo di caricamento apparirà sotto l'intero riepilogo del carrello.
  - **Valore consigliato:** 'Sotto il riepilogo del carrello' (spesso offre più spazio)
  - **Scenario/esempio per il commerciante:** Se i clienti devono caricare un file generale per l'intero ordine, posizionarlo chiaramente sulla pagina del carrello assicura che non lo perdano prima del checkout.
- **Visualizza modulo di caricamento sulla pagina della cronologia ordini:**

  - **Cosa fa questa impostazione:** Controlla dove appare il modulo di caricamento sulla pagina dei dettagli dell'ordine individuale del cliente.
  - **Effetto della modifica di questa impostazione:**
    - *Quando impostato su 'Nel blocco dettagli ordine':* Il modulo di caricamento apparirà all'interno della sezione principale dei dettagli dell'ordine.
    - *Quando impostato su 'Sotto i dettagli ordine':* Il modulo di caricamento apparirà sotto i dettagli dell'ordine.
  - **Valore consigliato:** 'Nel blocco dettagli ordine' (per una più stretta associazione con l'ordine)
  - **Scenario/esempio per il commerciante:** Dopo che un cliente ha effettuato un ordine, può facilmente trovare l'opzione di caricamento sulla pagina della cronologia degli ordini per aggiungere file mancanti.
- **Visualizza modulo di caricamento sulla pagina del mio account:**

  - **Cosa fa questa impostazione:** Controlla se un link dedicato "I miei file" appare nella dashboard "Il mio account" del cliente.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Apparirà un link, che porta a una pagina dove i clienti possono gestire i file generici.
    - *Quando disabilitato:* Il link non apparirà.
  - **Valore consigliato:** NO (a meno che tu non abbia abilitato "Consenti ai clienti di caricare file sull'account cliente" e abbia bisogno di questa funzionalità)
  - **Scenario/esempio per il commerciante:** Se desideri che i clienti abbiano un luogo centrale per tutti i loro file caricati, indipendentemente dagli ordini specifici, abilita questa opzione.
- **Visualizza modulo di caricamento nel piè di pagina:**

  - **Cosa fa questa impostazione:** Aggiunge un link al gestore di caricamento file nel piè di pagina del tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Apparirà un link nel piè di pagina, fornendo un altro punto di accesso al gestore file.
    - *Quando disabilitato:* Nessun link nel piè di pagina.
  - **Valore consigliato:** NO (a meno che tu non voglia un'alta visibilità per il gestore file)
  - **Scenario/esempio per il commerciante:** Se i caricamenti di file sono una parte fondamentale della tua attività, un link nel piè di pagina può renderlo facilmente accessibile da qualsiasi pagina.
- **Visualizza modulo di caricamento nella colonna sinistra:**

  - **Cosa fa questa impostazione:** Aggiunge un link al gestore di caricamento file nella colonna sinistra del tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Apparirà un link nella colonna sinistra.
    - *Quando disabilitato:* Nessun link nella colonna sinistra.
  - **Valore consigliato:** NO (a meno che tu non voglia un'alta visibilità per il gestore file)
  - **Scenario/esempio per il commerciante:** Simile al piè di pagina, questo fornisce un altro punto di accesso prominente.
- **Visualizza modulo di caricamento nella colonna destra:**

  - **Cosa fa questa impostazione:** Aggiunge un link al gestore di caricamento file nella colonna destra del tuo negozio.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Apparirà un link nella colonna destra.
    - *Quando disabilitato:* Nessun link nella colonna destra.
  - **Valore consigliato:** NO (a meno che tu non voglia un'alta visibilità per il gestore file)
  - **Scenario/esempio per il commerciante:** Simile al piè di pagina e alla colonna sinistra, questo fornisce un altro punto di accesso prominente.
- **Invia email al cliente per nuovo file:**

  - **Cosa fa questa impostazione:** Controlla se viene inviata una notifica via email al cliente quando un nuovo file viene caricato sul suo ordine da un amministratore.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I clienti ricevono una notifica via email.
    - *Quando disabilitato:* Non viene inviata alcuna notifica via email.
  - **Valore consigliato:** SÌ (per una buona comunicazione con il cliente)
  - **Scenario/esempio per il commerciante:** Se carichi una prova di design affinché il cliente la riveda, verrà avvisato via email.
- **Invia email al proprietario del negozio per nuovo file:**

  - **Cosa fa questa impostazione:** Controlla se viene inviata una notifica via email al proprietario del negozio (o all'email del negozio configurata) quando un cliente carica un nuovo file.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Tu (il proprietario del negozio) ricevi una notifica via email.
    - *Quando disabilitato:* Non viene inviata alcuna notifica via email.
  - **Valore consigliato:** SÌ (altamente raccomandato per un'elaborazione tempestiva)
  - **Scenario/esempio per il commerciante:** Un cliente carica un file di design critico. Ricevi immediatamente un'email, permettendoti di iniziare a elaborare l'ordine senza ritardi.
- **Allega file all'email di conferma dell'ordine:**

  - **Cosa fa questa impostazione:** Determina se i file caricati dal cliente vengono allegati all'email di conferma dell'ordine standard di PrestaShop.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I file saranno inclusi come allegati nell'email di conferma dell'ordine inviata al cliente.
    - *Quando disabilitato:* I file non vengono allegati all'email.
  - **Valore consigliato:** NO (a meno che i file non siano piccoli e pochi, poiché allegati di grandi dimensioni possono causare problemi di consegna delle email)
  - **Scenario/esempio per il commerciante:** Se i clienti caricano file molto piccoli e non critici, potresti abilitare questa opzione. Per file più grandi o numerosi, è meglio lasciare che i clienti li scarichino dal loro account per evitare problemi con il server di posta elettronica.
- **Allega file all'email del servizio clienti:**

  - **Cosa fa questa impostazione:** Determina se i file caricati dal cliente vengono allegati all'email inviata al cliente quando un amministratore carica un nuovo file.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I file saranno inclusi come allegati nell'email.
    - *Quando disabilitato:* I file non vengono allegati all'email.
  - **Valore consigliato:** NO (simile alla conferma dell'ordine, evita allegati di grandi dimensioni)
  - **Scenario/esempio per il commerciante:** Se carichi una piccola prova per il cliente, potresti abilitare questa opzione. Per file più grandi, indirizzali a scaricare dal loro account.
- **Allega file all'email del proprietario del negozio:**

  - **Cosa fa questa impostazione:** Determina se i file caricati dal cliente vengono allegati all'email inviata al proprietario del negozio quando un nuovo file viene caricato da un cliente.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I file saranno inclusi come allegati nella notifica via email che ricevi.
    - *Quando disabilitato:* I file non vengono allegati all'email.
  - **Valore consigliato:** NO (a meno che i file non siano piccoli e pochi, poiché allegati di grandi dimensioni possono intasare la tua casella di posta)
  - **Scenario/esempio per il commerciante:** Se preferisci scaricare i file direttamente dal back office, disabilita questa opzione. Se ti aspetti solo file molto piccoli e li vuoi immediatamente nella tua casella di posta, abilitala.
- **Abilita commenti per i file:**

  - **Cosa fa questa impostazione:** Consente a clienti e amministratori di aggiungere commenti a ogni file caricato.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Apparirà un campo di testo accanto a ogni file per aggiungere note o istruzioni.
    - *Quando disabilitato:* Non saranno disponibili campi per i commenti.
  - **Valore consigliato:** SÌ (per una migliore comunicazione e contesto)
  - **Scenario/esempio per il commerciante:** Un cliente carica un logo e aggiunge un commento: "Usa questo logo, ma per favore cambia il colore in blu." Questo fornisce un contesto cruciale.
- **Abilita commenti per i carrelli:**

  - **Cosa fa questa impostazione:** Consente ai clienti di aggiungere un commento generale al loro carrello.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Apparirà un campo di testo sulla pagina del carrello per commenti generali sul carrello.
    - *Quando disabilitato:* Nessun campo per commenti generali sul carrello.
  - **Valore consigliato:** SÌ (utile per istruzioni generali)
  - **Scenario/esempio per il commerciante:** Un cliente potrebbe aggiungere un commento come: "Assicurati che tutti gli articoli siano confezionati insieme come regalo."
- **Abilita commenti per gli ordini:**

  - **Cosa fa questa impostazione:** Consente ai clienti di aggiungere un commento generale al loro ordine.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Apparirà un campo di testo sulla pagina dei dettagli dell'ordine per commenti generali sull'ordine.
    - *Quando disabilitato:* Nessun campo per commenti generali sull'ordine.
  - **Valore consigliato:** SÌ (utile per istruzioni post-ordine)
  - **Scenario/esempio per il commerciante:** Un cliente potrebbe aggiungere un commento dopo aver effettuato un ordine: "Ho bisogno che questo venga consegnato entro venerdì, per favore."
- **Abilita commenti per i prodotti:**

  - **Cosa fa questa impostazione:** Consente ai clienti di aggiungere un commento specifico a un prodotto.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Apparirà un campo di testo sulla pagina del prodotto per commenti specifici del prodotto.
    - *Quando disabilitato:* Nessun campo per commenti specifici del prodotto.
  - **Valore consigliato:** SÌ (utile per istruzioni di personalizzazione del prodotto)
  - **Scenario/esempio per il commerciante:** Un cliente che ordina un'incisione personalizzata potrebbe aggiungere un commento: "Incidi 'Buon Compleanno John' con carattere corsivo."
- **Abilita la scheda "I miei file" nell'account cliente:**

  - **Cosa fa questa impostazione:** Aggiunge una scheda dedicata "I miei file" alla dashboard dell'account cliente.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Appare una nuova scheda, che consente ai clienti di visualizzare e gestire tutti i loro file caricati in un unico posto.
    - *Quando disabilitato:* La scheda è nascosta.
  - **Valore consigliato:** SÌ (migliora l'esperienza del cliente centralizzando i file)
  - **Scenario/esempio per il commerciante:** I clienti possono facilmente trovare tutti i loro design, prove o documenti caricati in un'unica comoda posizione.
- **Abilita la scheda "I miei file" nella pagina della cronologia ordini:**

  - **Cosa fa questa impostazione:** Aggiunge una sezione dedicata "I miei file" all'interno della pagina della cronologia ordini per ogni ordine specifico.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Appare una sezione all'interno della pagina dei dettagli di ogni ordine, che mostra i file relativi a quell'ordine specifico.
    - *Quando disabilitato:* Questa sezione è nascosta.
  - **Valore consigliato:** SÌ (cruciale per la gestione dei file specifici dell'ordine)
  - **Scenario/esempio per il commerciante:** Quando un cliente rivede un ordine passato, può immediatamente vedere tutti i file che ha caricato per quell'ordine.
- **Abilita la scheda "I miei file" nella pagina del prodotto:**

  - **Cosa fa questa impostazione:** Aggiunge una sezione dedicata "I miei file" all'interno della pagina del prodotto.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Appare una sezione sulla pagina del prodotto, che mostra i file relativi a quel prodotto specifico.
    *Quando disabilitato:* Questa sezione è nascosta.
  - **Valore consigliato:** NO (a meno che tu non abbia un caso d'uso molto specifico, poiché questo può ingombrare le pagine dei prodotti)
  - **Scenario/esempio per il commerciante:** Questo potrebbe essere utile se i clienti riordinano frequentemente lo stesso prodotto personalizzato e hanno bisogno di fare riferimento a file precedentemente caricati per quel prodotto.
- **Abilita la scheda "I miei file" nella pagina del carrello:**

  - **Cosa fa questa impostazione:** Aggiunge una sezione dedicata "I miei file" all'interno della pagina del carrello.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Appare una sezione sulla pagina del carrello, che mostra i file relativi agli articoli nel carrello.
    *Quando disabilitato:* Questa sezione è nascosta.
  - **Valore consigliato:** NO (a meno che tu non abbia un caso d'uso molto specifico, poiché questo può ingombrare le pagine del carrello)
  - **Scenario/esempio per il commerciante:** Se i clienti stanno costruendo un ordine complesso con molti file, questo potrebbe fornire una panoramica di tutti i file attualmente associati al carrello.
- **Mostra pulsante di caricamento file sulla pagina del prodotto:**

  - **Cosa fa questa impostazione:** Controlla la visibilità del pulsante "Carica file" sulle pagine dei prodotti.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il pulsante sarà visibile.
    - *Quando disabilitato:* Il pulsante sarà nascosto.
  - **Valore consigliato:** SÌ (se consenti il caricamento di file di prodotto)
  - **Scenario/esempio per il commerciante:** Se desideri che i clienti carichino file per la personalizzazione del prodotto, questo pulsante deve essere visibile.
- **Mostra pulsante di caricamento file sulla pagina del carrello:**

  - **Cosa fa questa impostazione:** Controlla la visibilità del pulsante "Carica file" sulla pagina del carrello.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il pulsante sarà visibile.
    - *Quando disabilitato:* Il pulsante sarà nascosto.
  - **Valore consigliato:** SÌ (se consenti il caricamento di file del carrello)
  - **Scenario/esempio per il commerciante:** Se i clienti devono caricare un file generale per il loro intero ordine, questo pulsante deve essere visibile sulla pagina del carrello.
- **Mostra pulsante di caricamento file sulla pagina della cronologia ordini:**

  - **Cosa fa questa impostazione:** Controlla la visibilità del pulsante "Carica file" sulla pagina dei dettagli dell'ordine del cliente.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il pulsante sarà visibile.
    - *Quando disabilitato:* Il pulsante sarà nascosto.
  - **Valore consigliato:** SÌ (se consenti il caricamento di file post-ordine)
  - **Scenario/esempio per il commerciante:** Se i clienti potrebbero aver bisogno di aggiungere file dopo aver effettuato un ordine, questo pulsante deve essere visibile sulla pagina della cronologia degli ordini.
- **Mostra pulsante di caricamento file sulla pagina del mio account:**

  - **Cosa fa questa impostazione:** Controlla la visibilità del pulsante "Carica file" sulla pagina "Il mio account" del cliente.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il pulsante sarà visibile.
    *Quando disabilitato:* Il pulsante sarà nascosto.
  - **Valore consigliato:** NO (a meno che tu non abbia abilitato "Consenti ai clienti di caricare file sull'account cliente" e abbia bisogno di questa funzionalità)
  - **Scenario/esempio per il commerciante:** Se desideri che i clienti carichino file generici sul loro account, questo pulsante deve essere visibile.
- **Mostra pulsante di caricamento file nel piè di pagina:**

  - **Cosa fa questa impostazione:** Controlla la visibilità del pulsante "Carica file" nel piè di pagina.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il pulsante sarà visibile.
    *Quando disabilitato:* Il pulsante sarà nascosto.
  - **Valore consigliato:** NO (a meno che tu non voglia un'alta visibilità per il gestore file)
  - **Scenario/esempio per il commerciante:** Se i caricamenti di file sono una parte fondamentale della tua attività, un pulsante nel piè di pagina può renderlo facilmente accessibile da qualsiasi pagina.
- **Mostra pulsante di caricamento file nella colonna sinistra:**

  - **Cosa fa questa impostazione:** Controlla la visibilità del pulsante "Carica file" nella colonna sinistra.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il pulsante sarà visibile.
    *Quando disabilitato:* Il pulsante sarà nascosto.
  - **Valore consigliato:** NO (a meno che tu non voglia un'alta visibilità per il gestore file)
  - **Scenario/esempio per il commerciante:** Simile al piè di pagina, questo fornisce un altro punto di accesso prominente.
- **Mostra pulsante di caricamento file nella colonna destra:**

  - **Cosa fa questa impostazione:** Controlla la visibilità del pulsante "Carica file" nella colonna destra.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il pulsante sarà visibile.
    *Quando disabilitato:* Il pulsante sarà nascosto.
  - **Valore consigliato:** NO (a meno che tu non voglia un'alta visibilità per il gestore file)
  - **Scenario/esempio per il commerciante:** Simile al piè di pagina e alla colonna sinistra, questo fornisce un altro punto di accesso prominente.

#### Impostazioni avanzate

- **Abilita modalità debug:**

  - **Cosa fa questa impostazione:** Attiva una modalità speciale che visualizza informazioni aggiuntive e messaggi di errore, principalmente per la risoluzione dei problemi.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Messaggi di errore più dettagliati e informazioni di debug potrebbero apparire sullo schermo o nei log.
    - *Quando disabilitato:* Funzionamento normale, gli errori sono soppressi o registrati silenziosamente.
  - **Valore consigliato:** NO (abilita solo durante la risoluzione dei problemi con il supporto)
  - **Scenario/esempio per il commerciante:** Se riscontri un problema e hai bisogno di fornire maggiori informazioni al supporto MyPresta.eu, potrebbero chiederti di abilitare la modalità debug.
- **Elimina file quando l'ordine viene eliminato:**

  - **Cosa fa questa impostazione:** Rimuove automaticamente tutti i file caricati associati quando un ordine viene eliminato dal back office di PrestaShop.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I file vengono rimossi permanentemente dal tuo server quando un ordine viene eliminato.
    - *Quando disabilitato:* I file rimangono sul server anche se l'ordine associato viene eliminato.
  - **Valore consigliato:** SÌ (per mantenere pulito il tuo server ed evitare file orfani)
  - **Scenario/esempio per il commerciante:** Se elimini frequentemente ordini di prova, abilitando questa opzione impedisci al tuo server di accumulare file non necessari.
- **Elimina file quando il prodotto viene eliminato:**

  - **Cosa fa questa impostazione:** Rimuove automaticamente tutti i file caricati associati quando un prodotto viene eliminato dal back office di PrestaShop.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I file vengono rimossi permanentemente dal tuo server quando un prodotto viene eliminato.
    *Quando disabilitato:* I file rimangono sul server anche se il prodotto associato viene eliminato.
  - **Valore consigliato:** SÌ (per mantenere pulito il tuo server ed evitare file orfani)
  - **Scenario/esempio per il commerciante:** Se rimuovi prodotti vecchi o fuori produzione, questo assicura che anche i file associati vengano puliti.
- **Elimina file quando il carrello viene eliminato:**

  - **Cosa fa questa impostazione:** Rimuove automaticamente tutti i file caricati associati quando un carrello viene eliminato dal back office di PrestaShop.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I file vengono rimossi permanentemente dal tuo server quando un carrello viene eliminato.
    *Quando disabilitato:* I file rimangono sul server anche se il carrello associato viene eliminato.
  - **Valore consigliato:** SÌ (per mantenere pulito il tuo server ed evitare file orfani)
  - **Scenario/esempio per il commerciante:** I carrelli sono spesso temporanei. Abilitando questa opzione impedisci al tuo server di accumulare file da carrelli abbandonati.
- **Elimina file quando il cliente viene eliminato:**

  - **Cosa fa questa impostazione:** Rimuove automaticamente tutti i file caricati associati quando un account cliente viene eliminato dal back office di PrestaShop.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* I file vengono rimossi permanentemente dal tuo server quando un cliente viene eliminato.
    *Quando disabilitato:* I file rimangono sul server anche se il cliente associato viene eliminato.
  - **Valore consigliato:** SÌ (per la privacy dei dati e l'igiene del server)
  - **Scenario/esempio per il commerciante:** Se un cliente richiede la rimozione dei suoi dati (conformità GDPR), questo assicura che anche i suoi file caricati vengano eliminati.
- **Elimina file quando il file del cliente viene eliminato:**

  - **Cosa fa questa impostazione:** Quando un amministratore o un cliente elimina un file specifico, questa impostazione controlla se il file effettivo viene rimosso dal server.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato:* Il file viene rimosso permanentemente dal server.
    *Quando disabilitato:* Il record del file viene rimosso dal database, ma il file effettivo rimane sul server (orfano).
  - **Valore consigliato:** SÌ (sempre, per prevenire file orfani e risparmiare spazio su disco)
  - **Scenario/esempio per il commerciante:** Quando un cliente decide di non aver più bisogno di un file, eliminarlo libera anche spazio sul server.
- **Abilita CSS personalizzato:**

  - **Cosa fa questa impostazione:** Fornisce un'area di testo dove puoi aggiungere le tue regole CSS per personalizzare l'aspetto degli elementi del modulo.
  - **Effetto della modifica di questa impostazione:**
    - *Quando abilitato e CSS aggiunto:* I tuoi stili personalizzati sovrascriveranno o integreranno lo stile predefinito del modulo.
    *Quando disabilitato o vuoto:* Il modulo utilizza il suo stile predefinito.
  - **Valore consigliato:** NO (a meno che tu non abbia esigenze di design specifiche e conoscenze CSS)
  - **Scenario/esempio per il commerciante:** Vuoi cambiare il colore del pulsante di caricamento per abbinarlo al colore principale del tuo marchio. Aggiungeresti qui le regole CSS.
- **CSS personalizzato:**

  - **Cosa fa questa impostazione:** Questa è l'area di testo dove digiti o incolli il tuo codice CSS personalizzato.
  - **Effetto della modifica di questa impostazione:** L'aspetto visivo degli elementi del modulo cambierà in base alle tue regole CSS.
  - **Valore consigliato:** Lascia vuoto a meno che tu non conosca il CSS.
  - **Scenario/esempio per il commerciante:** `button.upload-btn { background-color: #ff0000; color: white; }`

### 2.2 Schermate di amministrazione dedicate e viste del controller

Il modulo aggiunge nuove sezioni al back office di PrestaShop per la gestione dei file caricati.

#### 2.2.1 Gestore file cliente (Back Office > Ordini > File cliente)

Questa schermata fornisce un luogo centralizzato per visualizzare e gestire tutti i file caricati dai tuoi clienti.

- **Nome schermata e posizione menu:** **File cliente** (si trova sotto il menu **Ordini** in PrestaShop 1.7/8/9. Nelle versioni precedenti, potrebbe essere direttamente sotto il menu principale Moduli o una scheda personalizzata).
- **Azioni e impostazioni disponibili:**
  - **Tabella elenco file:** Vedrai una tabella che elenca tutti i file caricati. Ogni riga tipicamente mostra:
    - **Nome file:** Il nome del file caricato.
    - **Cliente:** Il nome del cliente che ha caricato il file (o "Ospite" se applicabile).
    - **ID ordine:** L'ID dell'ordine a cui è associato il file.
    - **Prodotto:** Il nome del prodotto se il file è collegato a un prodotto specifico.
    - **ID carrello:** L'ID del carrello a cui è associato il file.
    - **Data caricamento:** Quando il file è stato caricato.
    - **Dimensione:** La dimensione del file.
    - **Azioni:** Pulsanti per **Scaricare** il file, **Visualizzare dettagli** (inclusi i commenti) o **Eliminare** il file.
  - **Filtro e ricerca:** Puoi tipicamente filtrare l'elenco per cliente, ID ordine o cercare per nome file per trovare rapidamente file specifici.
  - **Azioni in blocco:** Opzioni per selezionare più file ed eseguire azioni come l'eliminazione in blocco.
- **Effetto delle modifiche:**
  - **Scaricare un file:** Salva il file sul tuo computer per la revisione o l'elaborazione.
  - **Eliminare un file:** Rimuove il file dall'elenco e, se configurato, dal tuo server.
  - **Visualizzare i dettagli:** Apre un pop-up o una nuova pagina con maggiori informazioni sul file, inclusi eventuali commenti associati.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1. Controlla regolarmente questa sezione, soprattutto se ricevi notifiche via email per nuovi caricamenti.
  2. Usa i filtri per trovare rapidamente i file per ordini specifici che stai elaborando.
  3. Scarica i file necessari per la produzione, il design o la revisione.
  4. Aggiungi commenti ai file se hai bisogno di comunicare con il cliente o il tuo team su di essi.
  5. Elimina i file vecchi o non necessari per mantenere pulito il tuo server.

#### 2.2.2 Integrazione della pagina dei dettagli dell'ordine (Back Office > Ordini > Ordini > Visualizza ordine)

Il modulo si integra anche direttamente nella pagina standard dei dettagli dell'ordine di PrestaShop.

- **Nome schermata e posizione menu:** Quando visualizzi un ordine specifico in **Back Office > Ordini > Ordini**, troverai una nuova sezione o scheda relativa a "File cliente" o "File caricati".
- **Azioni e impostazioni disponibili:**
  - **File per questo ordine:** Un elenco di tutti i file specificamente caricati per l'ordine corrente dal cliente o da un amministratore.
  - **Carica nuovo file:** Un'opzione per caricare un file tu stesso come amministratore, associandolo direttamente a questo ordine. Questo è utile per caricare prove, design finali o documenti interni.
  - **Aggiungi commenti:** Puoi aggiungere commenti a singoli file o un commento generale per l'ordine.
  - **Scarica/Elimina:** Opzioni per scaricare o eliminare singoli file associati a questo ordine.
- **Effetto delle modifiche:**
  - **Caricamento di un file come amministratore:** Il file diventa parte degli allegati dell'ordine, visibile al cliente nella sua cronologia ordini (se configurato).
  - **Aggiunta di commenti:** Fornisce contesto per il file o l'ordine, visibile al cliente e ad altri amministratori.
- **Flusso di lavoro consigliato per la gestione quotidiana del negozio:**
  1. Quando elabori un ordine che richiede file del cliente, naviga alla pagina dei dettagli dell'ordine.
  2. Rivedi i file caricati nella sezione dedicata.
  3. Scarica i file secondo necessità per la produzione.
  4. Se crei una prova o un design finale, caricalo qui in modo che il cliente possa accedervi.
  5. Usa i campi dei commenti per comunicare con il cliente o lasciare note interne.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| **Configurazione modulo** | Abilita modulo | SÌ | Interruttore principale per la funzionalità del modulo. |
|  | Consenti ai clienti di caricare file | SÌ | Consenti ai clienti di inviare file. |
|  | Consenti ai clienti ospiti di caricare file | SÌ | Consenti agli utenti non registrati di caricare. |
|  | Consenti ai clienti di eliminare file | NO | Impedisci ai clienti di rimuovere file. |
|  | Consenti ai clienti di scaricare file | SÌ | Consenti ai clienti di recuperare i loro file. |
|  | Consenti ai clienti di caricare file sugli ordini | SÌ | Abilita i caricamenti post-ordine tramite la cronologia ordini. |
|  | Consenti ai clienti di caricare file sui carrelli | SÌ | Abilita i caricamenti sulla pagina del carrello. |
|  | Consenti ai clienti di caricare file sui prodotti | SÌ | Abilita i caricamenti sulle singole pagine dei prodotti. |
|  | Consenti ai clienti di caricare file sull'account cliente | NO | Abilita l'archiviazione generale dei file in "Il mio account". |
|  | Forza i clienti a caricare file sugli ordini | NO | Rendi il caricamento dei file obbligatorio per il completamento dell'ordine. |
|  | Forza i clienti a caricare file sui prodotti | NO | Rendi il caricamento dei file obbligatorio per aggiungere il prodotto al carrello. |
|  | Forza i clienti a caricare file sui carrelli | NO | Rendi il caricamento dei file obbligatorio per procedere dal carrello. |
|  | Estensioni file consentite | `jpg,jpeg,png,gif,pdf,doc,docx,xls,xlsx,txt` | Limita i tipi di file per sicurezza e usabilità. |
|  | Dimensione massima del file (MB) | `10` | Limita la dimensione del singolo file. |
|  | Numero massimo di file per ordine | `5` | Limita i file per ordine. |
|  | Numero massimo di file per prodotto | `1` | Limita i file per prodotto. |
|  | Numero massimo di file per carrello | `5` | Limita i file per carrello. |
|  | Visualizza modulo di caricamento sulla pagina del prodotto | 'Nella scheda prodotto' o 'Sotto il prezzo del prodotto' | Posizione del modulo di caricamento sulla pagina del prodotto. |
|  | Visualizza modulo di caricamento sulla pagina del carrello | 'Sotto il riepilogo del carrello' | Posizione del modulo di caricamento sulla pagina del carrello. |
|  | Visualizza modulo di caricamento sulla pagina della cronologia ordini | 'Nel blocco dettagli ordine' | Posizione del modulo di caricamento sulla pagina della cronologia ordini. |
|  | Visualizza modulo di caricamento sulla pagina del mio account | NO | Mostra/nascondi il link "I miei file" nell'account cliente. |
|  | Visualizza modulo di caricamento nel piè di pagina | NO | Mostra/nascondi il link "I miei file" nel piè di pagina. |
|  | Visualizza modulo di caricamento nella colonna sinistra | NO | Mostra/nascondi il link "I miei file" nella colonna sinistra. |
|  | Visualizza modulo di caricamento nella colonna destra | NO | Mostra/nascondi il link "I miei file" nella colonna destra. |
|  | Invia email al cliente per nuovo file | SÌ | Notifica il cliente quando l'amministratore carica un file. |
|  | Invia email al proprietario del negozio per nuovo file | SÌ | Notifica il proprietario del negozio quando il cliente carica un file. |
|  | Allega file all'email di conferma dell'ordine | NO | Allega i file caricati alla conferma dell'ordine. |
|  | Allega file all'email del servizio clienti | NO | Allega i file caricati all'email del servizio clienti. |
|  | Allega file all'email del proprietario del negozio | NO | Allega i file caricati alla notifica del proprietario del negozio. |
|  | Abilita commenti per i file | SÌ | Consenti commenti sui singoli file. |
|  | Abilita commenti per i carrelli | SÌ | Consenti commenti generali sui carrelli. |
|  | Abilita commenti per gli ordini | SÌ | Consenti commenti generali sugli ordini. |
|  | Abilita commenti per i prodotti | SÌ | Consenti commenti sui singoli prodotti. |
|  | Abilita la scheda "I miei file" nell'account cliente | SÌ | Mostra la scheda dedicata "I miei file" nell'account cliente. |
|  | Abilita la scheda "I miei file" nella pagina della cronologia ordini | SÌ | Mostra la sezione file nella pagina della cronologia ordini. |
|  | Abilita la scheda "I miei file" nella pagina del prodotto | NO | Mostra la sezione file nella pagina del prodotto. |
|  | Abilita la scheda "I miei file" nella pagina del carrello | NO | Mostra la sezione file nella pagina del carrello. |
|  | Mostra pulsante di caricamento file sulla pagina del prodotto | SÌ | Controlla la visibilità del pulsante di caricamento sulla pagina del prodotto. |
|  | Mostra pulsante di caricamento file sulla pagina del carrello | SÌ | Controlla la visibilità del pulsante di caricamento sulla pagina del carrello. |
|  | Mostra pulsante di caricamento file sulla pagina della cronologia ordini | SÌ | Controlla la visibilità del pulsante di caricamento sulla pagina della cronologia ordini. |
|  | Mostra pulsante di caricamento file sulla pagina del mio account | NO | Controlla la visibilità del pulsante di caricamento sulla pagina del mio account. |
|  | Mostra pulsante di caricamento file nel piè di pagina | NO | Controlla la visibilità del pulsante di caricamento nel piè di pagina. |
|  | Mostra pulsante di caricamento file nella colonna sinistra | NO | Controlla la visibilità del pulsante di caricamento nella colonna sinistra. |
|  | Mostra pulsante di caricamento file nella colonna destra | NO | Controlla la visibilità del pulsante di caricamento nella colonna destra. |
| **Impostazioni avanzate** | Abilita modalità debug | NO | Visualizza messaggi di errore dettagliati. |
|  | Elimina file quando l'ordine viene eliminato | SÌ | Rimuovi i file quando l'ordine associato viene eliminato. |
|  | Elimina file quando il prodotto viene eliminato | SÌ | Rimuovi i file quando il prodotto associato viene eliminato. |
|  | Elimina file quando il carrello viene eliminato | SÌ | Rimuovi i file quando il carrello associato viene eliminato. |
|  | Elimina file quando il cliente viene eliminato | SÌ | Rimuovi i file quando il cliente associato viene eliminato. |
|  | Elimina file quando il file del cliente viene eliminato | SÌ | Rimuovi il file effettivo dal server quando eliminato. |
|  | Abilita CSS personalizzato | NO | Attiva l'input CSS personalizzato. |
|  | CSS personalizzato | Lascia vuoto | Area di testo per le regole CSS personalizzate. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: I miei clienti non riescono a caricare file o ricevono un messaggio di errore.**
R1:

- **Controlla lo stato del modulo:** Assicurati che "Abilita modulo" e "Consenti ai clienti di caricare file" siano entrambi impostati su SÌ nella configurazione del modulo.
- **Tipo e dimensione del file:** Verifica che il tipo di file (estensione) e la dimensione rientrino nei limiti di "Estensioni file consentite" e "Dimensione massima del file" che hai impostato.
- **Limiti del server:** Il tuo provider di hosting potrebbe avere limiti di caricamento PHP inferiori (`upload_max_filesize`, `post_max_size` in `php.ini`) rispetto alle impostazioni del tuo modulo. Contatta il tuo host o webmaster per aumentarli se necessario.
- **Permessi:** Assicurati che la directory di caricamento del modulo (solitamente `modules/orderfiles/uploads/`) abbia i permessi di scrittura (ad esempio, 755 o 777, anche se 777 non è generalmente raccomandato per la sicurezza).
- **Modalità debug:** Abilita temporaneamente la "Modalità debug" nelle impostazioni avanzate del modulo e controlla eventuali messaggi di errore specifici.

**D2: Il modulo di caricamento non appare sulla mia pagina prodotto/carrello/ordine.**
R2:

- **Configurazione del modulo:** Ricontrolla le impostazioni "Visualizza modulo di caricamento su..." per la pagina specifica (prodotto, carrello, cronologia ordini) nella configurazione del modulo.
- **Conflitti di hook:** Un altro modulo potrebbe interferire con gli hook di visualizzazione. Prova a disabilitare temporaneamente altri moduli che modificano le pagine prodotto, carrello o ordine per vedere se il modulo appare.
- **Compatibilità del tema:** I temi personalizzati potrebbero non renderizzare correttamente gli hook standard di PrestaShop. Se stai utilizzando un tema personalizzato, potresti aver bisogno di un webmaster per integrare manualmente gli hook del modulo nei tuoi file del tema.
- **Cache:** Svuota la cache di PrestaShop (Parametri avanzati > Prestazioni > Svuota cache) e la cache del tuo browser.

**D3: Non ricevo notifiche via email quando i clienti caricano file.**
R3:

- **Configurazione del modulo:** Assicurati che "Invia email al proprietario del negozio per nuovo file" sia impostato su SÌ.
- **Email del negozio:** Verifica che l'indirizzo email del tuo negozio (PS\_SHOP\_EMAIL in Parametri avanzati > E-mail) sia configurato correttamente e funzionante.
- **Impostazioni email:** Controlla le impostazioni email di PrestaShop (Parametri avanzati > E-mail) e assicurati che le email vengano inviate correttamente (ad esempio, prova a inviare un'email di prova).
- **Cartella spam:** Controlla la tua cartella spam o posta indesiderata per le notifiche.
- **Mailer del server:** La funzione di posta del tuo server potrebbe essere configurata in modo errato. Consulta il tuo provider di hosting.

**D4: Come posso tradurre il testo del modulo in altre lingue?**
R4:

- Nel back office di PrestaShop, vai su **Internazionale > Traduzioni**.
- Seleziona "Traduzioni dei moduli installati".
- Scegli il tuo tema, la lingua che desideri tradurre, quindi seleziona "Caricatore immagini ordine" dall'elenco dei moduli.
- Potrai quindi tradurre tutte le stringhe di testo visibili del modulo.

**D5: I miei file caricati non vengono eliminati quando elimino un ordine/prodotto/cliente.**
R5:

- **Configurazione del modulo:** Assicurati che le impostazioni corrispondenti "Elimina file quando..." (ad esempio, "Elimina file quando l'ordine viene eliminato") siano impostate su SÌ nelle impostazioni avanzate del modulo.
- **Eliminazione manuale:** Se queste impostazioni erano disabilitate, i file potrebbero essersi accumulati. Potrebbe essere necessario pulire manualmente la directory `modules/orderfiles/uploads/` sul tuo server per i file vecchi e orfani.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Caricatore immagini ordine" segue un'architettura standard dei moduli PrestaShop, sfruttando i principi MVC. Estende la classe `Module` per la sua funzionalità principale e utilizza `ModuleFrontController` e `AdminController` per gestire rispettivamente le richieste del front-office e del back-office. I caricamenti di file sono gestiti tramite controller dedicati e JavaScript, garantendo un'esperienza utente fluida. La configurazione è memorizzata in `ps_configuration` e i dati personalizzati (record di file) sono gestiti tramite interazione diretta con il database o potenzialmente un `ObjectModel` personalizzato (anche se nessuno è stato esplicitamente elencato nell'inventario, il modulo probabilmente utilizza SQL diretto per i record di file).

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

Questi controller gestiscono le interazioni dei clienti e la gestione dei file sul negozio.

- `controllers/front/customerfiles.php`
  - **Nome classe e classe genitore:** `OrderFilesCustomerfilesModuleFrontController` che estende `ModuleFrontController`
  - **Responsabilità:** Gestisce la sezione "I miei file" del cliente, visualizzando un elenco dei file caricati, consentendo loro di visualizzarli, scaricarli ed eventualmente eliminarli. Probabilmente gestisce le richieste AJAX per le operazioni sui file in questo contesto.
- `controllers/front/download.php`
  - **Nome classe e classe genitore:** `OrderFilesDownloadModuleFrontController` che estende `ModuleFrontController`
  - **Responsabilità:** Gestisce i download sicuri dei file. Verifica i permessi dell'utente (ad esempio, se il file appartiene al cliente loggato o se l'utente è un amministratore) prima di servire il file, impedendo l'accesso non autorizzato.
- `controllers/front/filesmanager.php`
  - **Nome classe e classe genitore:** `OrderFilesFilesmanagerModuleFrontController` che estende `ModuleFrontController`
  - **Responsabilità:** Questo è probabilmente un controller centrale per l'interfaccia principale di gestione dei file, potenzialmente utilizzato per caricamenti di file generici non legati a un ordine/prodotto specifico, o come hub per tutti i file del cliente.
- `controllers/front/index.php`
  - **Nome classe e classe genitore:** `OrderFilesIndexModuleFrontController` che estende `ModuleFrontController`
  - **Responsabilità:** Un segnaposto o controller frontale predefinito. In PrestaShop, `index.php` in una directory di controller spesso funge da fallback o da semplice reindirizzamento.
- `controllers/front/myfiles.php`
  - **Nome classe e classe genitore:** `OrderFilesMyfilesModuleFrontController` che estende `ModuleFrontController`
  - **Responsabilità:** Simile a `customerfiles.php`, questo controller probabilmente gestisce la sezione "I miei file" nell'account cliente, fornendo l'interfaccia per la visualizzazione e la gestione dei file personali.
- `controllers/front/thumb.php`
  - **Nome classe e classe genitore:** `OrderFilesThumbModuleFrontController` che estende `ModuleFrontController`
  - **Responsabilità:** Genera e serve miniature per i file immagine caricati, migliorando le prestazioni e la visualizzazione negli elenchi di file.
- `controllers/front/upload.php`
  - **Nome classe e classe genitore:** `OrderFilesUploadModuleFrontController` che estende `ModuleFrontController`
  - **Responsabilità:** Il controller principale per la gestione di tutte le richieste di caricamento file dal front office (pagina prodotto, pagina carrello, cronologia ordini, "I miei file"). Elabora il file caricato, ne convalida il tipo e la dimensione, lo memorizza sul server e ne registra i dettagli nel database. Probabilmente gestisce le risposte AJAX per lo stato e l'avanzamento del caricamento.

#### Controller di amministrazione Back-Office

Questi controller forniscono l'interfaccia amministrativa per la gestione dei file caricati.

- `controllers/admin/customerFiles.php`
  - **Nome scheda ed entità gestita:** "File cliente" (sotto il menu Ordini). Gestisce l'elenco, la visualizzazione, il download e l'eliminazione di tutti i file caricati dai clienti in tutto il negozio. Fornisce una vista a griglia completa con opzioni di filtro.
- `controllers/admin/index.php`
  - **Nome classe e classe genitore:** `AdminOrderFilesIndexController` che estende `ModuleAdminController`
  - **Nome scheda ed entità gestita:** Simile a `index.php` del front-office, questo potrebbe essere un segnaposto o un semplice reindirizzamento per la sezione amministrativa. La gestione principale dei file è gestita da `AdminCustomerFilesController`.

### 4.3 Classi e modelli principali (`classes/`)

L'inventario fornito indica l'assenza di classi personalizzate nella directory `classes/`. Ciò suggerisce che il modulo potrebbe utilizzare query dirette al database per la gestione dei file o memorizzare le informazioni sui file direttamente in `ps_configuration` o in una tabella personalizzata senza un `ObjectModel` dedicato. Data la complessità della gestione dei file, è più probabile che i record dei file siano memorizzati in una tabella di database personalizzata e gestiti tramite SQL diretto o una semplice classe helper all'interno del file principale del modulo.

### 4.4 Risorse JavaScript (`views/js/`)

Questi script migliorano l'esperienza utente per il caricamento e la gestione dei file.

- `orderfiles/js/jquery.form.js`
  - **Ambito:** Front-office e Back-office (ovunque i moduli vengano inviati tramite AJAX).
  - **Descrizione:** Un plugin jQuery per inviare facilmente moduli HTML tramite AJAX, inclusi i caricamenti di file. Gestisce il monitoraggio dell'avanzamento e semplifica gli invii di moduli asincroni.
- `orderfiles/js/orders.js`
  - **Ambito:** Back-office (specificamente all'interno delle pagine dei dettagli dell'ordine).
  - **Descrizione:** Probabilmente gestisce la funzionalità AJAX per il caricamento di file direttamente dalla pagina dei dettagli dell'ordine dell'amministratore, la visualizzazione dei file associati a un ordine e la gestione dei commenti nel contesto dell'ordine.
- `orderfiles/js/script-customers.js`
  - **Ambito:** Front-office (pagine dell'account cliente, sezione "I miei file").
  - **Descrizione:** Gestisce gli elementi interattivi all'interno della sezione "I miei file" del cliente, inclusa la visualizzazione degli elenchi di file, la gestione delle azioni di download/eliminazione e potenzialmente gli aggiornamenti AJAX per lo stato dei file o i commenti.
- `orderfiles/js/script.js`
  - **Ambito:** Front-office (pagine prodotto, pagine carrello, moduli di caricamento generici).
  - **Descrizione:** Il principale JavaScript del front-office per la gestione dei caricamenti di file. Probabilmente inizializza i moduli di caricamento, gestisce la funzionalità drag-and-drop, visualizza l'avanzamento del caricamento, convalida i tipi/dimensioni dei file lato client e invia richieste AJAX a `upload.php`.

### 4.5 Fogli di stile CSS (`views/css/`)

Questi fogli di stile controllano la presentazione visiva degli elementi del modulo.

- `orderfiles/css/ajaxuploader.css`
  - **Ambito:** Front-office e Back-office (ovunque venga utilizzata l'interfaccia di caricamento AJAX).
  - **Descrizione:** Stili per il widget di caricamento file stesso, incluse barre di avanzamento, aree drag-and-drop ed elementi di anteprima file.
  - **Selettori di classe CSS chiave:** `.ajax-uploader-container`, `.upload-drop-zone`, `.file-list`, `.progress-bar`
- `orderfiles/css/backoffice.css`
  - **Ambito:** Back-office (controller di amministrazione).
  - **Descrizione:** Stili specifici per le interfacce amministrative del modulo, come l'elenco "File cliente" e l'integrazione all'interno della pagina dei dettagli dell'ordine.
  - **Selettori di classe CSS chiave:** `.orderfiles-admin-table`, `.orderfiles-order-details-block`
- `orderfiles/css/orderfiles.css`
  - **Ambito:** Front-office (elementi generali del modulo).
  - **Descrizione:** Stili generali per i componenti del front-office del modulo, inclusi pulsanti, elenchi di file e sezioni di commenti sulle pagine prodotto, carrello e cronologia ordini.
  - **Selettori di classe CSS chiave:** `.orderfiles-upload-form`, `.orderfiles-file-item`, `.orderfiles-comments`
- `orderfiles/css.css`
  - **Ambito:** Potenzialmente stile globale o di fallback.
  - **Descrizione:** Questo potrebbe essere un foglio di stile più vecchio o generico. Gli sviluppatori dovrebbero controllarne il contenuto per comprenderne l'impatto specifico, poiché `orderfiles.css` è più descrittivo.
  - **Selettori di classe CSS chiave:** (Richiede ispezione)

### 4.6 Struttura del template Smarty (`views/templates/`)

#### Template degli hook (`views/templates/hook/`)

Questi template vengono renderizzati tramite gli hook di PrestaShop per iniettare il contenuto del modulo in varie parti del negozio.

- `displayProductPageUploadFormSmall.tpl`: Renderizza un modulo di caricamento compatto sulla pagina del prodotto.
- `filesmanager-orderhistory.tpl`: Visualizza l'interfaccia del gestore file all'interno della pagina della cronologia ordini del cliente.
- `force-redirect.tpl`: Un template di utilità, probabilmente utilizzato per reindirizzamenti dopo determinate azioni o per imporre il caricamento di file.
- `header.tpl`: Inietta risorse CSS/JS o altro codice necessario nella sezione `<head>` del front office.
- `my-account-17.tpl`: Renderizza il link/scheda "I miei file" per le dashboard dell'account cliente di PrestaShop 1.7.x e successive.
- `my-account.tpl`: Renderizza il link/scheda "I miei file" per le dashboard dell'account cliente delle versioni precedenti di PrestaShop (ad esempio, 1.6.x).
- `orderConfirmation.tpl`: Visualizza le opzioni di caricamento file o un riepilogo sulla pagina di conferma dell'ordine.
- `product-files-button.tpl`: Renderizza il pulsante "Carica file" sulla pagina del prodotto.
- `product-files.tpl`: Visualizza un elenco di file associati a un prodotto, potenzialmente con opzioni di caricamento.
- `shopping-cart-force-files-alert.tpl`: Visualizza un messaggio di avviso se il caricamento di file è obbligatorio sulla pagina del carrello e nessun file è stato caricato.
- `shopping-cart-qty-infos-alert.tpl`: Probabilmente visualizza un messaggio di avviso relativo alle informazioni sulla quantità nel carrello, possibilmente legato ai caricamenti di file.
- `shopping-cart.tpl`: Integra la funzionalità di caricamento file o gli elenchi di file nella pagina del carrello.
- `tab.tpl`: Un template di scheda generico, possibilmente utilizzato per creare nuove schede sulle pagine dei prodotti o nell'account cliente.

#### Template di amministrazione (`views/templates/admin/`)

Questi template sono utilizzati per le interfacce di back-office del modulo.

- `admin.tpl`: Il template di configurazione principale per il metodo `getContent()` del modulo, che renderizza il modulo delle impostazioni.
- `adminOrderDetailUpload.tpl`: Integra l'interfaccia di caricamento e gestione file direttamente nella pagina dei dettagli dell'ordine di PrestaShop nel back office.
- `boscript.tpl`: Contiene codice JavaScript specifico per il back office, probabilmente incluso nelle pagine di amministrazione.
- `bulk-delete-files.tpl`: Template per un'interfaccia o una conferma di eliminazione file in blocco.
- `comments_cartfiles.tpl`: Renderizza la sezione dei commenti per i file associati a un carrello.
- `comments_orderfiles.tpl`: Renderizza la sezione dei commenti per i file associati a un ordine.
- `comments_productfiles.tpl`: Renderizza la sezione dei commenti per i file associati a un prodotto.
- `customerfilesmanager.tpl`: Il template principale per `AdminCustomerFilesController`, che visualizza la griglia di tutti i file caricati.
- `_configure/helpers/list/list_action_details.tpl`: Un template helper per visualizzare un pulsante di azione "dettagli" in un elenco.
- `_configure/helpers/list/list_content.tpl`: Un template helper per renderizzare le righe di contenuto di un elenco.
- `_configure/prestashopbug/helpers/list/*.tpl`: Questi template sembrano essere override o correzioni specifiche per gli helper di elenco predefiniti di PrestaShop, possibilmente per risolvere problemi di compatibilità o personalizzare la visualizzazione dell'elenco per le griglie di amministrazione del modulo. Includono `list.tpl`, `list_action_delete.tpl`, `list_action_details.tpl`, `list_content.tpl`, `list_footer.tpl`, `list_header.tpl`.

#### Template front-office (`views/templates/front/`)

Questi sono template autonomi per pagine front-office dedicate.

- `access-denied.tpl`: Visualizza un messaggio quando un cliente tenta di accedere a un file o a una pagina senza i permessi adeguati.
- `customerfilesmanager.tpl`: Il template principale per la pagina "I miei file" del cliente, che visualizza i file caricati.
- `filesmanager.tpl`: Un template generico per il gestore file, potenzialmente utilizzato per una pagina di gestione file più ampia.
- `my-files.tpl`: Un altro template per la sezione "I miei file", probabilmente simile a `customerfilesmanager.tpl` o a una vista specifica al suo interno.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

Il modulo probabilmente crea almeno una tabella di database personalizzata per memorizzare le informazioni sui file caricati.

- **`ps_orderfiles_files` (o simile):**
  - `id_order_file` (Chiave primaria)
  - `id_customer` (Collegamento a `ps_customer`)
  - `id_order` (Collegamento a `ps_order`)
  - `id_cart` (Collegamento a `ps_cart`)
  - `id_product` (Collegamento a `ps_product`)
  - `filename` (Nome originale del file)
  - `filepath` (Percorso del file memorizzato sul server)
  - `file_extension`
  - `file_size`
  - `comment` (Commenti utente/amministratore)
  - `date_add`
  - `date_upd`
  - `is_admin_upload` (Booleano, per distinguere i caricamenti del cliente da quelli dell'amministratore)
- **`ps_configuration`:** Memorizza tutte le impostazioni del modulo (ad esempio, `OF_ALLOW_CUSTOMER_UPLOAD`, `OF_MAX_FILE_SIZE`, `OF_ALLOWED_EXTENSIONS`, `OF_CEMAIL_CUSTOMER`, `OF_CEMAIL_ATTACH`, ecc.). Queste chiavi sono prefissate con `OF_` (Order Files).

#### Tabella degli hook registrati

| Nome hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHeader` | Nella sezione `<head>` di ogni pagina del front-office. | Inietta i file CSS (`orderfiles.css`, `ajaxuploader.css`) e JavaScript (`jquery.form.js`, `script.js`, `script-customers.js`) del modulo. |
| `displayProductAdditionalInfo` (o hook simile della pagina prodotto) | Sulla pagina del prodotto, tipicamente sotto i dettagli principali del prodotto. | Renderizza `product-files.tpl` o `displayProductPageUploadFormSmall.tpl` per i caricamenti di file specifici del prodotto. |
| `displayShoppingCartFooter` (o hook simile della pagina carrello) | In fondo al riepilogo del carrello. | Renderizza `shopping-cart.tpl` per i caricamenti di file a livello di carrello e gli avvisi. |
| `displayCustomerAccount` | Nella dashboard "Il mio account" del cliente. | Renderizza `my-account.tpl` o `my-account-17.tpl` per aggiungere il link "I miei file". |
| `displayMyAccountBlock` | Nella dashboard "Il mio account" del cliente (alternativa per alcuni temi). | Renderizza `my-account.tpl` o `my-account-17.tpl` per aggiungere il link "I miei file". |
| `displayOrderConfirmation` | Sulla pagina di conferma dell'ordine dopo un acquisto riuscito. | Renderizza `orderConfirmation.tpl` per mostrare opzioni di caricamento o riepiloghi dei file. |
| `displayOrderDetail` | Sulla pagina dei dettagli dell'ordine del cliente in "Il mio account". | Renderizza `filesmanager-orderhistory.tpl` per mostrare i file relativi all'ordine specifico. |
| `displayLeftColumn` | Nella colonna sinistra del front office. | Renderizza `tab.tpl` (o simile) per visualizzare un link al gestore file. |
| `displayRightColumn` | Nella colonna destra del front office. | Renderizza `tab.tpl` (o simile) per visualizzare un link al gestore file. |
| `displayFooter` | Nel piè di pagina del front office. | Renderizza `tab.tpl` (o simile) per visualizzare un link al gestore file. |
| `actionObjectOrderAddAfter` | Dopo che un nuovo ordine è stato aggiunto con successo al database. | Attiva le notifiche via email al proprietario del negozio se un cliente ha caricato file durante il checkout. |
| `actionObjectOrderDeleteAfter` | Dopo che un ordine è stato eliminato dal database. | Attiva l'eliminazione dei file dal server se "Elimina file quando l'ordine viene eliminato" è abilitato. |
| `actionObjectProductDeleteAfter` | Dopo che un prodotto è stato eliminato dal database. | Attiva l'eliminazione dei file dal server se "Elimina file quando il prodotto viene eliminato" è abilitato. |
| `actionObjectCartDeleteAfter` | Dopo che un carrello è stato eliminato dal database. | Attiva l'eliminazione dei file dal server se "Elimina file quando il carrello viene eliminato" è abilitato. |
| `actionObjectCustomerDeleteAfter` | Dopo che un cliente è stato eliminato dal database. | Attiva l'eliminazione dei file dal server se "Elimina file quando il cliente viene eliminato" è abilitato. |
| `actionAdminOrdersControllerSaveAfter` | Dopo che un ordine è stato salvato/aggiornato nel back office. | Potenzialmente gestisce i caricamenti di file dell'amministratore o gli aggiornamenti dei commenti dalla pagina dei dettagli dell'ordine. |
| `actionAdminControllerSetMedia` | Quando un controller di amministrazione viene caricato e le sue risorse multimediali sono impostate. | Inietta i file CSS (`backoffice.css`) e JavaScript (`orders.js`, `jquery.form.js`, `boscript.tpl`) del modulo per la funzionalità del back-office. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto tecnico, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda relativa al modulo "Caricatore immagini ordine".
