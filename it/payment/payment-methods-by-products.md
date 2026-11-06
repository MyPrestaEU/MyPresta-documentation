---
title: "Metodi di pagamento per prodotto - documentazione e manuale del venditore"
description: "Questo manuale serve a impostare i metodi di pagamento per prodotto, a combinarli nel carrello e a correggere una cassa che mostra ancora il metodo sbagliato."
sidebar:
  label: "Metodi di pagamento per prodotto - documentazione e manuale del venditore"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Payment methods by products su MyPresta.eu](https://mypresta.eu/modules/payment-process/payment-methods-by-products.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/payment/payment-methods-by-products/)
>
> ---


## 1. Requisiti

Controlli questi punti prima dell’installazione.

- Usi PrestaShop 1.7.0.0 o successivo, inclusi PrestaShop 8 e 9. Il modulo accetta versioni del negozio fino a 9.99.99.
- Mantenga la versione di PHP richiesta da quella versione di PrestaShop. Il programma di installazione non controlla PHP a parte.
- Attivi l’estensione PHP cURL se il controllo aggiornamenti deve contattare MyPresta.eu. Se manca cURL, il controllo prova ad aprire l’indirizzo con l’impostazione del server che consente le letture remote. Le regole di pagamento non hanno bisogno di cURL.
- Non serve nessun altro modulo PrestaShop. L’elenco dei metodi nasce dai moduli di pagamento già installati. Se non ce n’è nessuno, le caselle sono vuote.
- Installi e attivi almeno un modulo di pagamento se un metodo deve comparire in cassa.
- Il modulo non chiede un account esterno.

I testi del modulo nel back office sono in inglese. È fornito solo il polacco. I nomi di questa guida sono le denominazioni italiane di quelle etichette inglesi.

## 2. Installazione

1. Apra **Moduli**, poi **Gestione moduli**.
2. Scelga **Carica un modulo** e invii il file ZIP.
3. Scelga **Installa** su **Payment options by products**.

L’installazione fa questo:

- Aggiunge **Payment - Product associations** sotto **Migliora**, poi **Pagamento**. Se quel menu manca, la voce resta sotto **Migliora**.
- Crea la tabella. Una riga è un prodotto, un modulo di pagamento, un negozio e un paese.
- Registra il filtro della cassa e la scheda nella pagina prodotto.
- Copia l’override della cassa. PrestaShop deve consentire gli override. Se sono spenti, la scheda prodotto e il filtro della cassa funzionano comunque. L’avviso giallo nella configurazione lo dice.
- Non svuota la cache del negozio. La svuoti in **Parametri avanzati**, **Prestazioni**, solo se resta visibile una schermata vecchia.
- Non crea alcuna regola. La cassa non cambia finché non salva una regola.

**Configura** in **Gestione moduli** apre le impostazioni. La voce **Payment - Product associations** apre l’elenco delle regole.

Disinstallazione:

- Rimuove la voce **Payment - Product associations**.
- Rimuove l’override della cassa e gli hook registrati.
- Rimuove la versione salvata usata dall’aggiornamento.
- Non cancella le regole prodotto. Un’installazione successiva rilegge quelle righe.
- Non spegne gli avvisi di aggiornamento condivisi con gli altri moduli MyPresta.
- Lascia la cartella del modulo finché non la elimina da **Gestione moduli** o dal server.

Disattivare il modulo in **Gestione moduli** ferma il filtro della cassa. Le regole restano nel database.

## 3. Configurazione e lavoro nel back office

Una regola è un elenco di metodi di pagamento per un prodotto, nel negozio che sta modificando, per un paese di consegna o per tutti i paesi.

Segua questo ordine:

1. Apra **Configura** e scelga come si combinano più prodotti limitati nello stesso carrello. Scelga **Save**. Questo passo è facoltativo. Finché non salva, il negozio tiene ogni metodo consentito da almeno un prodotto limitato.
2. Apra un prodotto e la scheda **Payment methods**, oppure **Migliora**, **Pagamento**, **Payment - Product associations**, e aggiunga una riga.
3. Selezioni i metodi che devono restare disponibili quando quel prodotto è nel carrello. Scelga **All countries** o un paese. Salvi.
4. In cassa il negozio legge l’indirizzo di consegna e nasconde i metodi che le regole non consentono.

Un prodotto senza regola salvata non toglie metodi di pagamento. **Free order** resta quando è l’unico metodo di un carrello a zero.

Non c’è uno stato ordine. Il risultato è l’elenco dei pagamenti nella pagina di cassa.

Le schermate di questo capitolo mostrano il back office in inglese. La didascalia usa il nome di questo manuale.

### 3.1 Configurazione del modulo

Apra **Moduli**, **Gestione moduli**, **Payment options by products**, **Configura**.

In alto ci sono due note. Il primo link apre **Payment - Product associations**. La seconda indica la scheda **Payment methods** del prodotto. Nessuna delle due salva una regola.

Se gli override sono spenti, l’avviso giallo dice: «Overrides are disabled. Checkout filtering still runs through the payment options hook.» Li lasci spenti se usa solo PrestaShop 8 o 9. Li attivi in **Parametri avanzati**, **Prestazioni**, solo se le serve anche il vecchio override della cassa.

Il pannello **Settings** spiega la regola del paese e la modalità di combinazione. Il testo sopra l’elenco non salva nulla da solo.

![Settings](https://mypresta.eu/docs/images/docs/pobp-configure-settings.webp)

**Configura**, pannello **Settings**. Il testo blu spiega i paesi. L’elenco è **How to get available payment methods?**.

| Campo | All’inizio | Effetto |
|---|---|---|
| **How to get available payment methods?** | **Show all payment methods from products**, finché non salva un’altra scelta | **Show the same payment methods available for all products in cart** tiene un metodo solo se ogni prodotto limitato del carrello lo consente. **Show all payment methods from products** lo tiene se almeno un prodotto limitato lo consente. Un prodotto senza regola non toglie metodi. |
| **Save** | — | Salva solo questa scelta. Non modifica una regola prodotto. La pagina si ricarica con il valore scelto. |

### 3.2 Payment - Product associations

Apra **Migliora**, **Pagamento**, **Payment - Product associations**. La nota in alto ripete che la stessa regola è sul prodotto, nella scheda **Payment methods**.

L’elenco mostra una riga per prodotto nel negozio corrente.

![Payment - Product associations](https://mypresta.eu/docs/images/docs/pobp-associations-list.webp)

**Payment - Product associations** senza righe. Le colonne sono **ID**, **Product**, **Payment** e **Country**. Il più è **Add new**.

| Colonna | Contenuto |
|---|---|
| **ID** | Il numero di riga. Non è il numero del prodotto. |
| **Product** | Numero e nome del prodotto. |
| **Payment** | Ogni metodo salvato per quel prodotto, uno sotto l’altro. |
| **Country** | **All countries**, oppure il paese di consegna salvato. Il testo della colonna dice che un paese scelto vale solo se l’indirizzo di consegna è in quel paese, e che **All countries** vale per ogni indirizzo. |

**Add new** apre un modulo vuoto. **Edit** apre il modulo di quel prodotto. **Delete** cancella quella sola riga del database, non ogni metodo elencato in **Payment**. **Delete selected** fa lo stesso per le righe selezionate. Questo modulo rifiuta una selezione vuota. Cancelli le righe rimaste, oppure svuoti la regola nella scheda prodotto, dove una selezione vuota è consentita.

Ricerca e filtri dell’elenco sono i filtri abituali del back office per queste colonne.

### 3.3 Modulo di associazione

Su **Add new** o **Edit**:

![Modulo di associazione](https://mypresta.eu/docs/images/docs/pobp-associations-form.webp)

**Add new**, compilato per questa immagine e non salvato. **ID Product** è 1. Nel modulo ci sono **Payment methods** e **Country** (**All countries**).

| Campo | All’inizio | Effetto |
|---|---|---|
| **ID Product** | Vuoto su una riga nuova. Compilato in modifica. | Inserisca il numero del prodotto o usi **Search**. L’aiuto dice di cercare per nome, ID o riferimento. **Save** senza prodotto mostra «Product is required.» e non scrive una regola. |
| **Payment methods** | Non selezionati su una riga nuova. In modifica sono selezionati i metodi già salvati. | Selezioni i metodi che restano in cassa quando il carrello contiene questo prodotto e il paese di consegna coincide con il paese sotto. L’etichetta mostra il nome del modulo di pagamento. |
| **Country** | **All countries** | Se sceglie un paese, i metodi selezionati valgono solo quando l’indirizzo di consegna del cliente è in quel paese. **All countries** li applica a ogni indirizzo. |
| **Save** | — | Sostituisce tutti i metodi salvati per questo prodotto nel negozio corrente con le selezioni e il paese di questo modulo. Se non c’è nulla di selezionato, la pagina mostra «There was a problem with form. No payment method selected» e le righe precedenti restano. |

Un prodotto ha un paese. Un nuovo salvataggio sostituisce i metodi precedenti di quel prodotto in questo negozio. Le regole di un altro negozio restano. Cambi il contesto negozio prima di modificare lì.

### 3.4 Scheda prodotto

Apra **Catalogo**, **Prodotti**, modifichi il prodotto, poi la scheda **Payment methods**.

![Payment methods sul prodotto](https://mypresta.eu/docs/images/docs/pobp-product-tab.webp)

Prodotto Hummingbird printed t-shirt, scheda **Payment methods**. Ci sono **Country** e **Available payment methods**. I segni sono solo nell’immagine. Il prodotto non è stato salvato.

| Campo | All’inizio | Effetto |
|---|---|---|
| **Country** | **All countries** se il prodotto non ha una regola. Altrimenti il paese già salvato. | Se sceglie un paese, i metodi selezionati valgono solo se l’indirizzo di consegna è in quel paese. **All countries** li applica a ogni indirizzo. |
| **Available payment methods** | Non selezionati se non c’è una regola. Altrimenti sono selezionati i metodi già salvati. | I metodi selezionati restano in cassa quando il carrello contiene questo prodotto e il paese di consegna coincide con il paese sopra. Nessuna selezione toglie la limitazione di questo prodotto. |

Scelga **Save** sul prodotto. PrestaShop conferma il salvataggio del prodotto. La regola di pagamento viene scritta con quel salvataggio, per il negozio che sta modificando. Una selezione vuota cancella la regola di questo prodotto in questo negozio. Il modulo delle associazioni, invece, non salva se non c’è nulla di selezionato.

Gli stessi dati compaiono in **Payment - Product associations**.

### 3.5 Aggiornamenti MyPresta

In **Configura**, sotto le impostazioni, **MyPresta Updates** controlla se esiste un file più recente. Non lo installa.

![MyPresta Updates](https://mypresta.eu/docs/images/docs/pobp-updates.webp)

**MyPresta Updates**, sotto le impostazioni in **Configura**.

| Campo | All’inizio | Effetto |
|---|---|---|
| **Check updates** | — | **Check now** chiede a MyPresta.eu se esiste un file più recente. La riga sopra il pulsante mostra una nuova versione oppure che il modulo è aggiornato. Non scarica e non installa il file. |
| **Updates notifications** | Attive, finché non salva **Disable** | **Enable** mostra un avviso nel back office quando esce una versione più recente. **Disable** ferma quel controllo automatico. **Save** salva la scelta e mostra «Update settings saved.» |
| **Module page** | — | Apre la pagina del modulo su MyPresta.eu, dove c’è il registro delle modifiche. Non salva alcuna impostazione. |
| **Save** | — | Salva solo **Updates notifications**. |

## 4. Fronte del negozio

Il modulo non aggiunge un blocco, una pagina o un messaggio sul prodotto, nel carrello o nell’account cliente. In quelle pagine il tema non ha nulla da cambiare.

Il cliente vede l’effetto nel passo di pagamento della cassa. I metodi che le regole non consentono non sono nell’elenco. I metodi senza regola, e **Free order** quando è l’unica scelta, restano.

Il paese è quello dell’indirizzo di consegna. Prima che esista un indirizzo, valgono solo le regole **All countries**. Una regola per un paese aspetta che l’indirizzo sia in quel paese.

## 5. Problemi

**L’elenco dei pagamenti non è cambiato.** Il prodotto non ha una regola, oppure nessun prodotto del carrello ne ha una. Apra il prodotto, **Payment methods**, selezioni i metodi e salvi il prodotto. Un prodotto senza selezioni non limita la cassa.

**Un metodo è sparito solo per un paese.** Il paese della regola non è **All countries** e l’indirizzo di consegna è in quel paese. Imposti **All countries** se la regola deve valere per ogni indirizzo.

**Un metodo viene ancora offerto.** Un altro prodotto del carrello lo consente e **How to get available payment methods?** è su **Show all payment methods from products**. Passi a **Show the same payment methods available for all products in cart** se ogni prodotto limitato deve consentire il metodo. Un prodotto senza regola non lo blocca.

**Nella configurazione compare «Overrides are disabled…» e non sa se il filtro è attivo.** In PrestaShop 8 e 9 il filtro continua. Il testo giallo dice che filtra l’hook della cassa. Attivi gli override solo se conta anche sul vecchio file.

**Save in Payment - Product associations mostra «Product is required.»** Il campo prodotto è vuoto. Cerchi il prodotto o inserisca il numero e scelga di nuovo **Save**.

**Save mostra «There was a problem with form. No payment method selected».** Nessun metodo è selezionato. Ne selezioni almeno uno. La regola precedente non è stata sostituita. Per togliere del tutto una regola, usi la scheda **Payment methods** del prodotto e salvi senza selezioni.

**Delete nell’elenco ha tolto un solo metodo.** **Delete** cancella la singola riga di quella linea, mentre **Payment** elenca tutti i metodi. Apra **Edit** e **Save** per riscrivere l’insieme, oppure cancelli finché il prodotto sparisce dall’elenco.

**Free order è l’unico metodo e la regola non lo contiene.** Un carrello a zero tiene **Free order**. Il modulo non toglie quel metodo unico.

**La regola di un negozio manca nell’altro.** Le regole sono salvate per negozio. Cambi negozio nell’intestazione multinegozio e salvi la regola lì.

## 6. Per lo sviluppatore

### 6.1 Panoramica

Classe principale `pobp`, versione `1.4.0`, nome **Payment options by products**, autore MyPresta.eu, scheda `administration`. Compatibilità da `1.7.0.0` a `9.99.99`.

Una riga di `ps_pobp` è un modulo di pagamento consentito per un prodotto, un negozio e un paese (`id_country` `0` significa tutti i paesi). La cassa legge i prodotti del carrello e l’indirizzo di consegna in `pobp::filterPaymentOptions()`. L’hook `actionPresentPaymentOptions` toglie le chiavi scartate dal filtro. L’override `PaymentOptionsFinder::find()` restituisce lo stesso filtro se il modulo è attivo. `pobp_innerjoin` vero significa l’intersezione dei prodotti limitati. Ogni altro valore, inclusa una chiave assente, significa l’unione. I prodotti senza righe corrispondenti sono ignorati. La chiave `free_order` non viene mai tolta. Un elenco che contiene solo `free_order` torna invariato.

### 6.2 File

| File | Ruolo |
|---|---|
| `pobp.php` | Installazione, modulo impostazioni, filtro cassa, scheda prodotto. |
| `lib/updatesChecker.php` | Classe `pobpUpdate`. Controllo aggiornamenti e modulo MyPresta Updates. |
| `lib/searchTool/searchTool.php` | Ricerca prodotto nel modulo di associazione. |
| `models/pob.php` | ObjectModel `pob` e `replaceForProduct()`. |
| `controllers/admin/AdminPobpController.php` | Elenco e modulo delle associazioni. |
| `override/classes/checkout/PaymentOptionsFinder.php` | `find()` chiama `filterPaymentOptions()`. |
| `upgrade/upgrade-1.4.0.php` | Chiama `ensureModuleComplements()` e salva `POBP_VERSION`. |
| `translations/pl.php` | Testi polacchi. |

Non ci sono controller né template di fronte.

### 6.3 Controller

`AdminPobpController` estende `ModuleAdminController`. Classe scheda `AdminPobp`, padre `AdminParentPayment`, oppure `IMPROVE` se quel padre manca. Icona `credit_card`. Nome visibile **Payment - Product associations**.

L’elenco raggruppa con una sottoquery `MIN(id_pobp)` per prodotto e negozio. `processAdd()` e `processUpdate()` chiamano `pob::replaceForProduct()`. Un insieme vuoto di metodi o un prodotto assente restituisce false e non sostituisce le righe. I testi passano da `$this->module->l(..., 'AdminPobpController')`.

La configurazione del modulo è `getContent()` di `pobp`, non un controller separato.

### 6.4 Hook

Registrati in `registerHooks()`:

| Hook | Ruolo |
|---|---|
| `actionPresentPaymentOptions` | Toglie i moduli di pagamento scartati dal filtro. L’array viene modificato sul posto. |
| `actionProductFormBuilderModifier` | Aggiunge la scheda `pobp` (paese e pagamenti) al modulo prodotto. |
| `actionAfterUpdateProductFormHandler` | Scrive `form_data['pobp']` per il prodotto salvato. |
| `actionAfterCreateProductFormHandler` | La stessa scrittura dopo la creazione di un prodotto. |

Non ci sono `enable()` né `disable()` propri. Disattivare il modulo toglie gli hook. L’override continua a caricarsi e restituisce l’elenco padre quando `Module::isEnabled('pobp')` è falso.

Il primo caricamento del back office dopo il caricamento dei file chiama `ensureModuleComplements()` se `POBP_VERSION` differisce dalla versione del file.

### 6.5 Override

`override/classes/checkout/PaymentOptionsFinder.php` sostituisce solo `find()`. Non sovrascrive `present()` né `findFree()`.

### 6.6 Database

| Tabella | Contenuto |
|---|---|
| `ps_pobp` | `id_pobp`, `id_product`, `id_payment` (id del modulo), `id_shop`, `id_country`. `inconsistency()` aggiunge `id_country` se manca la colonna. `0` significa tutti i paesi. |

La disinstallazione non cancella `ps_pobp`. L’installazione usa `CREATE TABLE IF NOT EXISTS`: una nuova installazione conserva le righe vecchie.

### 6.7 Chiavi e traduzioni

| Chiave | Se manca |
|---|---|
| `pobp_innerjoin` | Trattata come spenta. La cassa usa l’unione dei prodotti limitati. |
| `POBP_VERSION` | La richiesta successiva del back office esegue `ensureModuleComplements()` e poi salva la versione del file. |
| `mypresta_updates` | Trattata come accesa. `0` ferma il controllo automatico. La chiave è condivisa con altri moduli MyPresta. |
| `update_pobp` | Data e ora dell’ultimo controllo. |
| `updatev_pobp` | Stringa di versione restituita dal server di aggiornamento. |

I testi del negozio passano da `$this->l()`. Il pannello aggiornamenti usa la fonte `updatesChecker`. Il controller delle associazioni usa `AdminPobpController`. Il polacco è in `translations/pl.php`. Aggiunga un’altra lingua come `translations/{iso}.php` con la stessa forma di chiave.

`key.php` nella cartella del modulo può impostare `$this->mkey`. Se il file manca, il controllo invia `nlc`.

### 6.8 Estensione

Il fronte non renderizza un template del modulo, quindi il tema non ha nulla da sovrascrivere. Per cambiare l’elenco della cassa resti sull’hook delle opzioni di pagamento o sull’override di `PaymentOptionsFinder`. Per cambiare la scheda prodotto estenda `hookActionProductFormBuilderModifier` e conservi le chiavi del form `pobp`, altrimenti l’hook di salvataggio ignora i dati.

## 7. Aiuto

Pagina del modulo: [https://mypresta.eu/modules/payment-process/payment-methods-by-products.html](https://mypresta.eu/modules/payment-process/payment-methods-by-products.html)

Per scrivere di questo modulo acceda al suo account cliente su mypresta.eu, apra il modulo di contatto e scelga il tema **Support for paid modules**. Il modulo indica che l’accesso è obbligatorio per quel tema. Dopo l’accesso scelga questo modulo dalla cronologia degli acquisti.
