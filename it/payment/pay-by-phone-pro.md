---
title: "Pay By Phone Pro - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Pay By Phone Pro di MyPresta.eu."
sidebar:
  label: "Pay By Phone Pro - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Pay By Phone Pro su MyPresta.eu](https://mypresta.eu/modules/payment-process/pay-by-phone-pro.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/payment/pay-by-phone-pro/)
>
> ---


# Pay By Phone Pro

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop Supportate**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 5.6 - 8.5
- **Requisiti di Hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso, e questo modulo non ha requisiti specifici aggiuntivi oltre a un ambiente di hosting PrestaShop standard.

## 2. Guida Completa alla Configurazione (Ogni Impostazione Raggruppata per Schermata)

### 2.1 Pagina di Configurazione del Modulo (Back Office > Moduli > Configura > Pay By Phone Pro)

Questa è la schermata di configurazione principale dove definisci come il metodo di pagamento "Pay By Phone Pro" appare e si comporta nel tuo negozio.

- **Posizione del Menu:** Back Office > Moduli > Gestione moduli > Cerca "Pay By Phone Pro" > Clicca "Configura".

#### Impostazioni e Opzioni

1. **Titolo del Metodo di Pagamento**

   - **Cosa fa questa impostazione:** Questo è il nome del metodo di pagamento che i tuoi clienti vedranno durante il checkout. È ciò che appare nell'elenco delle opzioni di pagamento.
   - **Effetto della modifica di questa impostazione:**
     - *Se impostato su "Paga tramite telefono":* I clienti vedranno "Paga tramite telefono" come opzione.
     - *Se impostato su "Chiamaci per pagare":* I clienti vedranno "Chiamaci per pagare" come opzione.
   - **Valore consigliato:** Qualcosa di chiaro e professionale, come "Paga tramite telefono" o "Chiama per completare l'ordine".
   - **Scenario / esempio del commerciante:** Se vuoi enfatizzare il contatto diretto, potresti usare "Chiama il nostro team di vendita per pagare". Se vuoi che suoni più come un'opzione di pagamento standard, "Paga tramite telefono" è meglio.
2. **Descrizione del Metodo di Pagamento**

   - **Cosa fa questa impostazione:** Questa è una breve descrizione che appare sotto il titolo del metodo di pagamento durante il checkout. Spiega al cliente cosa comporta questo metodo di pagamento.
   - **Effetto della modifica di questa impostazione:**
     - *Se impostato su "Chiamaci per fornire i dettagli della tua carta di credito e finalizzare il tuo ordine.":* Questo testo apparirà, guidando il cliente sui passaggi successivi.
     - *Se impostato su "Contatta il nostro servizio clienti per discutere le opzioni di pagamento.":* Questo testo alternativo verrà visualizzato.
   - **Valore consigliato:** Indica chiaramente cosa deve fare il cliente, ad es. "Ti preghiamo di chiamarci al [Il tuo numero di telefono] per finalizzare il pagamento e i dettagli dell'ordine."
   - **Scenario / esempio del commerciante:** Potresti scrivere: "Dopo aver effettuato l'ordine, ti preghiamo di chiamarci al +1-800-123-4567 durante l'orario di lavoro per completare il pagamento. Tieni a portata di mano il numero del tuo ordine."
3. **Istruzioni per il Cliente nella Pagina di Conferma dell'Ordine**

   - **Cosa fa questa impostazione:** Questo è un messaggio più dettagliato visualizzato al cliente nella pagina di conferma dell'ordine *dopo* che ha selezionato "Pay By Phone Pro" e ha effettuato l'ordine. Qui fornisci istruzioni specifiche.
   - **Effetto della modifica di questa impostazione:**
     - *Se impostato su "Grazie per il tuo ordine. Ti preghiamo di chiamarci per finalizzare il pagamento.":* Questo messaggio verrà mostrato.
     - *Se impostato su "Il tuo ordine è in sospeso. Ti preghiamo di contattare il nostro team di supporto con il numero del tuo ordine per organizzare il pagamento.":* Questo messaggio alternativo verrà visualizzato.
   - **Valore consigliato:** Includi il tuo numero di telefono, gli orari di apertura e quali informazioni il cliente dovrebbe avere a portata di mano (ad es. numero d'ordine).
   - **Scenario / esempio del commerciante:** "Il tuo ordine #12345 è stato effettuato. Ti preghiamo di chiamare il nostro team di vendita al +1-800-123-4567 (Lun-Ven, 9:00 - 17:00 EST) entro 24 ore per fornire i dettagli di pagamento. Tieni a portata di mano il numero del tuo ordine."
4. **Stato dell'Ordine per Pagamenti in Sospeso**

   - **Cosa fa questa impostazione:** Questo determina lo stato iniziale di un ordine effettuato utilizzando "Pay By Phone Pro" nel tuo Back Office di PrestaShop. Questo stato indica che il pagamento non è ancora completo e richiede la tua azione.
   - **Effetto della modifica di questa impostazione:**
     - *Se impostato su "In attesa di bonifico bancario":* Gli ordini appariranno con questo stato.
     - *Se impostato su "Pagamento accettato":* (Non consigliato per questo modulo) Questo contrassegnerebbe erroneamente l'ordine come pagato prima che tu lo abbia elaborato.
   - **Valore consigliato:** Scegli uno stato che indichi chiaramente "pagamento in sospeso" o "in attesa di pagamento". Le scelte comuni sono "In attesa di bonifico bancario", "Pagamento in sospeso" o "In attesa di pagamento con assegno". Se hai uno stato d'ordine personalizzato come "In attesa di pagamento telefonico", sarebbe l'ideale.
   - **Scenario / esempio del commerciante:** La selezione di "In attesa di bonifico bancario" assicura che questi ordini siano facilmente identificabili nella tua lista ordini come bisognosi di elaborazione manuale del pagamento.
5. **Abilita per Paesi Specifici**

   - **Cosa fa questa impostazione:** Ti consente di limitare questo metodo di pagamento ai clienti di determinati paesi. Se lasciato vuoto, sarà disponibile per tutti i paesi.
   - **Effetto della modifica di questa impostazione:**
     - *Quando sono selezionati paesi specifici (ad es. "Stati Uniti", "Canada"):* Solo i clienti con un indirizzo di fatturazione in questi paesi vedranno "Pay By Phone Pro" come opzione.
     - *Quando non sono selezionati paesi:* Il metodo di pagamento è disponibile a livello globale.
   - **Valore consigliato:** Lascia vuoto se vuoi offrirlo in tutto il mondo, oppure seleziona paesi specifici se hai limitazioni operative (ad es. hai supporto telefonico solo in alcune regioni).
   - **Scenario / esempio del commerciante:** Se il tuo supporto telefonico è disponibile solo in inglese e spedisci solo negli Stati Uniti e in Canada, selezioneresti "Stati Uniti" e "Canada" per evitare di offrirlo a clienti che non puoi servire.
6. **Abilita per Valute Specifiche**

   - **Cosa fa questa impostazione:** Ti consente di limitare questo metodo di pagamento ai clienti che pagano in valute specifiche. Se lasciato vuoto, sarà disponibile per tutte le valute.
   - **Effetto della modifica di questa impostazione:**
     - *Quando sono selezionate valute specifiche (ad es. "USD", "EUR"):* Solo i clienti che pagano in queste valute vedranno "Pay By Phone Pro".
     - *Quando non sono selezionate valute:* Il metodo di pagamento è disponibile per tutte le valute configurate nel tuo negozio.
   - **Valore consigliato:** Lascia vuoto se supporti tutte le valute, oppure seleziona quelle specifiche se il tuo sistema di elaborazione manuale dei pagamenti ha limitazioni di valuta.
   - **Scenario / esempio del commerciante:** Se il tuo terminale per carte di credito elabora solo USD ed EUR, selezioneresti queste due valute.
7. **Abilita per Gruppi di Clienti Specifici**

   - **Cosa fa questa impostazione:** Ti consente di limitare questo metodo di pagamento a determinati gruppi di clienti (ad es. "Ospiti", "Clienti", "Grossisti"). Se lasciato vuoto, sarà disponibile per tutti i gruppi di clienti.
   - **Effetto della modifica di questa impostazione:**
     - *Quando sono selezionati gruppi specifici (ad es. "Grossisti"):* Solo i clienti appartenenti al gruppo "Grossisti" vedranno questa opzione di pagamento.
     - *Quando non sono selezionati gruppi:* Il metodo di pagamento è disponibile per tutti i gruppi di clienti.
   - **Valore consigliato:** Lascia vuoto per uso generale, oppure seleziona gruppi specifici se questo metodo di pagamento fa parte di un accordo speciale (ad es. per VIP o clienti B2B).
   - **Scenario / esempio del commerciante:** Potresti offrirlo solo al tuo gruppo di clienti "Grossisti", poiché spesso hanno termini di pagamento personalizzati che richiedono una discussione diretta.

#### Tabella di Riferimento Rapido della Configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Configurazione Modulo | Titolo Metodo di Pagamento | "Paga tramite telefono" | Nome visualizzato ai clienti durante il checkout. |
| Configurazione Modulo | Descrizione Metodo di Pagamento | "Chiamaci per fornire i dettagli della tua carta di credito e finalizzare il tuo ordine." | Breve spiegazione sotto il titolo del pagamento. |
| Configurazione Modulo | Istruzioni per il Cliente nella Pagina di Conferma dell'Ordine | "Grazie per il tuo ordine. Ti preghiamo di chiamarci per finalizzare il pagamento." | Istruzioni dettagliate nella pagina di conferma dell'ordine. |
| Configurazione Modulo | Stato dell'Ordine per Pagamenti in Sospeso | "In attesa di bonifico bancario" (o stato simile in sospeso) | Stato iniziale degli ordini effettuati con questo metodo. |
| Configurazione Modulo | Abilita per Paesi Specifici | Vuoto (Tutti i Paesi) | Limita il metodo di pagamento in base al paese del cliente. |
| Configurazione Modulo | Abilita per Valute Specifiche | Vuoto (Tutte le Valute) | Limita il metodo di pagamento in base alla valuta selezionata. |
| Configurazione Modulo | Abilita per Gruppi di Clienti Specifici | Vuoto (Tutti i Gruppi) | Limita il metodo di pagamento in base al gruppo di clienti. |

## 3. Risoluzione dei Problemi del Commerciante e Domande Frequenti (FAQ)

**D1: L'opzione "Pay By Phone Pro" non compare durante il checkout.**
R:

- **Verifica lo Stato del Modulo:** Vai su **Moduli > Gestione moduli** e assicurati che "Pay By Phone Pro" sia installato e abilitato.
- **Impostazioni di Configurazione:** Rivedi le impostazioni "Abilita per Paesi Specifici", "Abilita per Valute Specifiche" e "Abilita per Gruppi di Clienti Specifici". Se hai limitato il modulo, assicurati che il cliente/carrello di prova attuale soddisfi tali criteri.
- **Cache:** Svuota la cache di PrestaShop in **Parametri Avanzati > Prestazioni**. A volte, la vecchia cache impedisce la visualizzazione di nuovi moduli o impostazioni.
- **Compatibilità del Tema:** Sebbene raro, un tema altamente personalizzato potrebbe interferire. Passa temporaneamente a un tema PrestaShop predefinito (ad es. Classic) per escludere conflitti di tema.

**D2: Come posso modificare il testo che i clienti vedono per questo metodo di pagamento?**
R: Tutto il testo rivolto al cliente (titolo, descrizione e istruzioni di conferma) può essere personalizzato direttamente dalla pagina di configurazione del modulo nel tuo Back Office. Vai su **Moduli > Gestione moduli**, trova "Pay By Phone Pro" e clicca su "Configura". Troverai campi come "Titolo Metodo di Pagamento", "Descrizione Metodo di Pagamento" e "Istruzioni per il Cliente nella Pagina di Conferma dell'Ordine". Ricorda di salvare le modifiche.

**D3: Cosa succede se un cliente effettua un ordine utilizzando "Pay By Phone Pro" ma non chiama mai?**
R: L'ordine rimarrà nello stato "pagamento in sospeso" che hai configurato (ad es. "In attesa di bonifico bancario"). Dovrai monitorare questi ordini nel tuo Back Office. Puoi impostare promemoria automatici o contattare manualmente il cliente dopo un certo periodo (ad es. 24-48 ore) per un follow-up. Se non viene stabilito alcun contatto, potresti eventualmente dover annullare l'ordine.

**D4: Posso tradurre il testo del modulo in altre lingue?**
R: Sì, il sistema di traduzione di PrestaShop gestisce i testi dei moduli. Vai su **Internazionale > Traduzioni**, seleziona "Traduzioni dei moduli installati", scegli il tuo tema e poi seleziona "Pay By Phone Pro". Potrai quindi tradurre tutti i campi di testo configurabili nelle lingue attive del tuo negozio.

**D5: Come elaboro il pagamento una volta che un cliente chiama?**
R: Questo modulo non elabora i pagamenti da solo. Facilita l'effettuazione dell'ordine. Una volta che un cliente chiama, utilizzerai i tuoi metodi di elaborazione dei pagamenti offline esistenti (ad es. un terminale fisico per carte di credito, un terminale virtuale fornito dalla tua banca o la registrazione di un bonifico bancario) per prendere i dettagli del pagamento e completare la transazione. Dopo il successo del pagamento, devi aggiornare manualmente lo stato dell'ordine nel tuo Back Office di PrestaShop da "pagamento in sospeso" a "Pagamento accettato" (o "Elaborazione in corso") per riflettere la modifica.

## 4. Guida per Sviluppatori e Webmaster (Architettura Tecnica e Mappa del Codice)

Questa sezione fornisce una panoramica tecnica dettagliata del modulo "Pay By Phone Pro" per sviluppatori e webmaster.

### 4.1 Panoramica dell'Architettura

Il modulo "Pay By Phone Pro" segue un'architettura standard dei moduli PrestaShop, sfruttando principalmente `PaymentModule` per la sua funzionalità principale. Si integra nel flusso di checkout registrando hook e fornendo controller frontali per l'esecuzione e la validazione del pagamento. La configurazione è gestita tramite il metodo `getContent()` della classe principale del modulo.

### 4.2 Controller (`controllers/`)

#### Controller Front-Office

Questi controller gestiscono gli aspetti rivolti al cliente del processo di pagamento.

- **`controllers/front/index.php`**

  - **Nome classe e classe genitore:** `PayByPhoneIndexModuleFrontController` che estende `ModuleFrontController`.
  - **Responsabilità:** Questo controller è tipicamente responsabile della visualizzazione del modulo di pagamento iniziale o del reindirizzamento alla pagina di esecuzione del pagamento. Nel contesto di questo modulo, probabilmente agisce come un gateway prima dell'effettiva esecuzione del pagamento, potenzialmente impostando dati di sessione o reindirizzando a `payment_execution.tpl`.
- **`controllers/front/validation.php`**

  - **Nome classe e classe genitore:** `PayByPhoneValidationModuleFrontController` che estende `ModuleFrontController`.
  - **Responsabilità:** Questo è il controller critico che elabora l'ordine dopo che il cliente seleziona "Pay By Phone Pro". Valida l'ordine, lo crea nel database di PrestaShop con lo stato in sospeso configurato e quindi reindirizza il cliente alla pagina di conferma dell'ordine, visualizzando le istruzioni specifiche. Utilizza il metodo `validateOrder` della classe genitore `PaymentModule`.

#### Controller Amministrativi Back-Office

Questo modulo non include alcun controller amministrativo Back-Office personalizzato. Tutta la configurazione è gestita all'interno del metodo `getContent()` del modulo principale.

### 4.3 Classi e Modelli Core (`classes/`)

Questo modulo non contiene classi personalizzate o definizioni di `ObjectModel` nella directory `classes/`. Si basa sulle classi `PaymentModule` e `Configuration` di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo non include alcun file JavaScript personalizzato. La sua funzionalità è principalmente lato server e basata su template.

### 4.5 Fogli di Stile CSS (`views/css/`)

- **`paybyphone/css/paybyphone.css`**
  - **Ambito:** Stile front-office per il cliente.
  - **Componenti UI principali e contenitori che stilizza:** Questo foglio di stile è probabilmente utilizzato per fornire uno stile di base per l'aspetto del metodo di pagamento durante il checkout, come il blocco dell'opzione di pagamento, il testo della descrizione o qualsiasi elemento specifico all'interno dei template `payment.tpl` o `shopping-cart.tpl`.
  - **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere:** Gli sviluppatori possono ispezionare l'HTML generato per il metodo di pagamento nella pagina di checkout per identificare classi specifiche (ad es. `.paybyphone-payment-option`, `.paybyphone-description`) da sovrascrivere nel `custom.css` del loro tema o tramite le opzioni di personalizzazione del tema.

### 4.6 Struttura del Template Smarty (`views/templates/`)

#### Template Hook (`views/templates/hook/`)

Questi template vengono renderizzati quando vengono eseguiti specifici hook di PrestaShop.

- **`views/templates/hook/infos.tpl`**

  - **Hook:** Probabilmente `displayPaymentTop` o simile, fornendo informazioni aggiuntive sul metodo di pagamento.
  - **Blocco visivo:** Potrebbe essere utilizzato per visualizzare un blocco informativo generale sull'opzione "Paga tramite telefono", magari nella pagina del prodotto o in una colonna, prima che il cliente raggiunga il checkout.
- **`views/templates/hook/payment.tpl`**

  - **Hook:** `displayPayment` (PrestaShop 1.6) o `paymentOptions` (PrestaShop 1.7+).
  - **Blocco visivo:** Questo è il template principale per visualizzare l'opzione "Pay By Phone Pro" nella pagina di selezione del pagamento durante il checkout. Conterrà il titolo e la descrizione del metodo di pagamento come configurato nel Back Office.

#### Template Admin (`views/templates/admin/`)

Questo modulo non contiene alcun template amministrativo personalizzato. Il modulo di configurazione è probabilmente generato direttamente all'interno del metodo `getContent()` di `index.php` utilizzando `HelperForm` di PrestaShop.

#### Template Front-office (`views/templates/front/`)

Questi template vengono renderizzati dai controller frontali del modulo.

- **`views/templates/front/payment_execution.tpl`**

  - **Scopo:** Questo template è probabilmente renderizzato da `PayByPhoneIndexModuleFrontController` o direttamente dopo che il cliente seleziona il metodo di pagamento. Potrebbe servire come pagina intermedia o un passaggio di conferma prima della validazione finale, potenzialmente visualizzando un pulsante "Conferma Ordine".
- **`views/templates/front/shopping-cart.tpl`**

  - **Scopo:** Questo template è probabilmente un fallback o una visualizzazione alternativa per l'opzione di pagamento all'interno del riepilogo del carrello, possibilmente per versioni precedenti di PrestaShop o integrazioni di temi specifici. Presenterebbe l'opzione "Paga tramite telefono" prima dell'inizio del processo di checkout completo.
- **`views/templates/front/validation.tpl`**

  - **Scopo:** Questa è la pagina di conferma dell'ordine, renderizzata dopo che `PayByPhoneValidationModuleFrontController` ha validato e creato con successo l'ordine. Visualizza il testo "Istruzioni per il Cliente nella Pagina di Conferma dell'Ordine", insieme a un riepilogo dell'ordine.

### 4.7 Schema del Database e Mappa degli Hook

#### Tabelle del Database

Il modulo "Pay By Phone Pro" non crea tabelle di database personalizzate. Memorizza le sue impostazioni di configurazione nella tabella `ps_configuration` di PrestaShop utilizzando chiavi come `PAYBYPHONE_TITLE`, `PAYBYPHONE_DESCRIPTION`, `PAYBYPHONE_INSTRUCTIONS`, `PAYBYPHONE_ORDER_STATUS`, `PAYBYPHONE_COUNTRIES`, `PAYBYPHONE_CURRENCIES` e `PAYBYPHONE_GROUPS`.

#### Tabella degli Hook Registrati

| Nome Hook | Tempistica di Esecuzione | Scopo Tecnico |
| --- | --- | --- |
| `displayPayment` (PrestaShop 1.6) | Nella pagina di selezione del pagamento durante il checkout. | Visualizza l'opzione di pagamento "Pay By Phone Pro". |
| `paymentOptions` (PrestaShop 1.7+) | Nella pagina di selezione del pagamento durante il checkout. | Visualizza l'opzione di pagamento "Pay By Phone Pro" (hook moderno). |
| `displayPaymentReturn` | Nella pagina di conferma dell'ordine dopo il pagamento. | Visualizza le istruzioni specifiche per il cliente per chiamare. |
| `displayHeader` | Nella sezione `<head>` di ogni pagina front-office. | Potenzialmente utilizzato per caricare file CSS (`paybyphone.css`). |
| `displayLeftColumn` / `displayRightColumn` / `displayFooter` | Nelle rispettive aree colonna/footer. | Potrebbe essere utilizzato per visualizzare blocchi informativi sul metodo di pagamento (tramite `infos.tpl`). |
| `actionValidateOrder` | Dopo che un ordine è stato validato e creato con successo. | Consente al modulo di eseguire azioni aggiuntive o di logging dopo la creazione dell'ordine (ad es. impostazione di dettagli specifici dell'ordine). |

## 5. Supporto Ufficiale e Aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo "Pay By Phone Pro", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team è dedicato a garantire il buon funzionamento e la continua compatibilità dei nostri moduli con le ultime versioni di PrestaShop.
