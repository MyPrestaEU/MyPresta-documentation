---
title: "Order reference change free - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Order reference change free di MyPresta.eu."
sidebar:
  label: "Order reference change free - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Order reference change free su MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-reference-change-free.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/order-reference-change-free/)
>
> ---


# Order reference change free

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono generalmente sufficienti. Nessun requisito speciale oltre a un ambiente di hosting PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo "Order reference change free". Ti verrà presentata la schermata di configurazione principale.

#### **Formato del riferimento dell'ordine**

Questa è l'impostazione principale del modulo, che ti consente di definire il modello per i numeri di riferimento dei tuoi ordini.

-   **Cosa fa questa impostazione:** Questo campo di input ti consente di specificare un modello per come verranno generati i nuovi numeri di riferimento dell'ordine. Puoi utilizzare una combinazione di caratteri speciali e segnaposto per creare il formato desiderato.
-   **Effetto della modifica di questa impostazione:**
    *   *Quando impostato su un formato specifico (ad esempio, `[0-9]{6}`):* Tutti i nuovi ordini riceveranno un numero di riferimento che aderisce rigorosamente a questo modello. Ad esempio, `[0-9]{6}` genererebbe un riferimento numerico di 6 cifre come `123456`.
    *   *Quando lasciato al valore predefinito (comportamento predefinito di PrestaShop):* Il modulo non altererà la generazione del riferimento dell'ordine e PrestaShop utilizzerà il suo formato alfanumerico standard (ad esempio, `ABCDEF123`).
-   **Valore consigliato:** Questo dipende interamente dalle tue esigenze aziendali.
    *   Se hai bisogno di un riferimento semplice, solo numerico, prova `[0-9]{6}` per un numero di 6 cifre.
    *   Se desideri un mix di lettere maiuscole e numeri, `[A-Z0-9]{8}` ti darebbe un riferimento alfanumerico di 8 caratteri.
    *   Puoi anche includere prefissi statici, ad esempio, `MIONOME-[0-9]{5}` genererebbe `MIONOME-12345`.
-   **Scenario / esempio del commerciante:**
    *   **Scenario 1: Riferimenti solo numerici per la contabilità.** Il tuo software di contabilità richiede che tutti i riferimenti d'ordine siano puramente numerici e lunghi 8 cifre. Imposteresti questo su `[0-9]{8}`.
    *   **Scenario 2: Riferimenti più brevi e memorizzabili.** Desideri riferimenti più brevi, di 6 caratteri, utilizzando solo lettere maiuscole e numeri per una più facile comunicazione con i clienti. Imposteresti questo su `[A-Z0-9]{6}`.
    *   **Scenario 3: Riferimenti brandizzati.** Desideri che tutti i riferimenti inizino con l'iniziale del tuo marchio seguita da un numero di 5 cifre. Imposteresti questo su `M-[0-9]{5}`.

**Segnaposto e caratteri disponibili:**
Il modulo utilizza una sintassi simile alle espressioni regolari per definire il formato:

-   `[0-9]`: Rappresenta una singola cifra da 0 a 9.
-   `[a-z]`: Rappresenta una singola lettera minuscola da a a z.
-   `[A-Z]`: Rappresenta una singola lettera maiuscola da A a Z.
-   `[a-zA-Z]`: Rappresenta una singola lettera (maiuscola o minuscola).
-   `[A-Z0-9]`: Rappresenta una singola lettera maiuscola o cifra.
-   `{n}`: Specifica che il carattere o gruppo precedente deve essere ripetuto esattamente `n` volte. Ad esempio, `[0-9]{6}` significa 6 cifre.
-   `{n,m}`: Specifica che il carattere o gruppo precedente deve essere ripetuto tra `n` e `m` volte.
-   Qualsiasi altro carattere (ad esempio, `-`, `_`, `MIONOME-`) sarà incluso letteralmente nel riferimento.

**Nota importante:** Il modulo garantisce che il riferimento generato sia univoco. Se un riferimento generato esiste già, tenterà di generarne uno nuovo finché non ne verrà trovato uno univoco.

#### **Pulsante Salva**

-   **Cosa fa questa impostazione:** Questo pulsante salva tutte le modifiche apportate nella pagina di configurazione.
-   **Effetto della modifica di questa impostazione:**
    *   *Quando cliccato:* Il tuo nuovo formato di riferimento dell'ordine verrà applicato immediatamente a tutti i *nuovi* ordini effettuati nel tuo negozio. I riferimenti d'ordine esistenti non verranno modificati.
-   **Valore consigliato:** Clicca sempre su "Salva" dopo aver apportato modifiche per assicurarti che vengano applicate.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | Formato riferimento ordine | Predefinito PrestaShop (alfanumerico) | Definisce il modello per i nuovi numeri di riferimento ordine (es. `[0-9]{6}`, `MIONOME-[A-Z0-9]{5}`). Influisce su come i nuovi ordini vengono referenziati nel tuo negozio e sui documenti del cliente. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho cambiato il formato, ma i vecchi ordini hanno ancora il vecchio riferimento. Perché?**
R: Questo modulo influisce solo sui *nuovi* ordini effettuati dopo aver salvato la configurazione. Non modifica retroattivamente i riferimenti d'ordine esistenti, poiché ciò potrebbe causare incoerenze nei dati con registri passati, fatture e comunicazioni con i clienti.

**D: I miei nuovi riferimenti d'ordine non seguono il formato che ho impostato.**
R:

1.  **Hai cliccato su "Salva"?** Assicurati di aver cliccato sul pulsante "Salva" dopo aver apportato modifiche nella pagina di configurazione del modulo.
2.  **Controlla la sintassi del formato:** Ricontrolla la tua stringa `Formato riferimento ordine` per eventuali errori di battitura o caratteri errati. Fai riferimento alla sezione "Segnaposto e caratteri disponibili" sopra.
3.  **Svuota la cache:** A volte, la cache di PrestaShop può impedire che le modifiche abbiano effetto immediatamente. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti).
4.  **Conflitti tra moduli:** Sebbene rari, un altro modulo che modifica pesantemente il processo d'ordine potrebbe entrare in conflitto. Prova a disabilitare temporaneamente altri moduli installati di recente per vedere se il problema si risolve.

**D: Posso rendere il riferimento dell'ordine più corto o più lungo?**
R: Sì, assolutamente! Usa la sintassi `{n}` o `{n,m}` per specificare la lunghezza esatta o un intervallo. Ad esempio, `[0-9]{4}` per un numero di 4 cifre, o `[A-Z0-9]{10}` per un riferimento alfanumerico di 10 caratteri.

**D: Cosa succede se il modulo genera un riferimento che esiste già?**
R: Il modulo è progettato per garantire l'unicità. Se genera un riferimento già in uso, tenterà automaticamente di generarne un altro finché non ne verrà trovato uno univoco. Questo processo è solitamente istantaneo e garantisce che nessun ordine condivida lo stesso riferimento.

**D: Questo modulo influisce sulla SEO o sulle prestazioni del mio negozio?**
R: No, questo modulo opera puramente sulla logica di backend della generazione del riferimento dell'ordine. Non ha un impatto diretto sulla SEO o sulle prestazioni del front-office del tuo negozio.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Order reference change free" raggiunge la sua funzionalità attraverso un override della classe `Order` principale di PrestaShop. Invece di agganciarsi direttamente ai listener di eventi, modifica il comportamento predefinito del metodo `Order::generateReference()`, che è responsabile della creazione del riferimento d'ordine univoco. Questo approccio garantisce che la logica di generazione del riferimento personalizzato venga applicata ogni volta che viene creato un nuovo ordine, indipendentemente dal flusso specifico del front-office.

### 4.2 Controller (`controllers/`)

Questo modulo non introduce alcun controller front-office o back-office personalizzato. Tutta la configurazione è gestita tramite il metodo `getContent()` del file principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

-   **`refchange/override/classes/order/Order.php`**
    *   **Scopo**: Questo file contiene l'override per la classe `Order` principale di PrestaShop. La sua funzione principale è quella di sostituire il metodo `generateReference()` predefinito con una logica personalizzata che applica il formato definito nella configurazione del modulo.
    *   **Classe genitore**: Estende `OrderCore`.
    *   **Metodi chiave**:
        *   `generateReference()`: Questo metodo sovrascritto è il cuore del modulo.
            *   Recupera il formato di riferimento personalizzato da `Configuration::get('REFCHANGE_FORMAT')`.
            *   Se è definito un formato personalizzato, utilizza un ciclo per generare una stringa di riferimento basata sul modello configurato (utilizzando `preg_match` e `rand` per la selezione dei caratteri).
            *   Controlla quindi la tabella `ps_orders` per assicurarsi che il riferimento generato sia univoco. Se non è univoco, lo rigenera finché non ne viene trovato uno univoco.
            *   Se non è definito alcun formato personalizzato, ricade sul metodo `OrderCore::generateReference()` del genitore.
    *   **Interazione con il database**: Interagisce con la tabella `ps_orders` per verificare i riferimenti esistenti.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo non include alcun file JavaScript personalizzato.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo non include alcun file CSS personalizzato.

### 4.6 Struttura del template Smarty (`views/templates/`)

Questo modulo non include alcun file di template Smarty personalizzato. L'interfaccia di configurazione viene renderizzata direttamente all'interno del metodo `getContent()` del file principale del modulo.

### 4.7 Schema del database e mappa degli hook

-   **Tabelle del database**:
    *   `ps_configuration`: Memorizza l'impostazione di configurazione del modulo:
        *   `REFCHANGE_FORMAT`: La stringa del formato di riferimento dell'ordine personalizzato (ad esempio, `[0-9]{6}`).
-   **Tabella degli hook registrati**:
    Questo modulo non registra esplicitamente alcun hook nella tabella `ps_hook_module`. La sua funzionalità è implementata tramite un override di classe, il che significa che modifica direttamente il comportamento del core piuttosto che rispondere a specifici eventi hook.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto professionale per il modulo "Order reference change free", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu). Il nostro team è dedicato a garantire che il modulo funzioni in modo ottimale con il tuo negozio PrestaShop.
