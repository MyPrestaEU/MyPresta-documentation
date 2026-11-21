---
title: MyFAQ Free - documentazione e manuale utente
sidebar:
  label: MyFAQ Free - documentazione e manuale utente
description: Manuale di configurazione e risoluzione dei problemi per i negozi che hanno già MyFAQ Free.
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Free Product FAQ su MyPresta.eu](https://mypresta.eu/modules/front-office-features/free-product-faq.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/free-product-faq/)
>
> ---


## 1. Requisiti

MyFAQ Free gira dentro PrestaShop. Non ha bisogno di un altro modulo.

- PrestaShop dalla 1.7.0.0 fino a PrestaShop 9.
- La versione di PHP richiesta da quella versione di PrestaShop. Il modulo non controlla da solo la versione di PHP.
- Non serve alcuna estensione PHP in più. Il controllo degli aggiornamenti usa cURL quando il server ce l'ha. Senza cURL, il controllo legge l'indirizzo solo se il server consente le letture remote.
- Non serve nessun altro modulo. La pagina prodotto del tema deve stampare il piè di prodotto oppure le schede prodotto extra, perché il cliente veda le domande.
- Per scrivere e mostrare le tre domande non serve un account su un servizio esterno. La donazione PayPal nella pagina di configurazione è facoltativa. Il controllo degli aggiornamenti chiede solo che il negozio raggiunga MyPresta.eu.

Ogni prodotto tiene tre domande. Non c'è un import, quindi un catalogo grande non avvia un lotto e non alza la memoria che il modulo chiede.

## 2. Installazione

1. Nel back office apra **Moduli**, poi **Gestione moduli**.
2. Carichi lo zip e clicchi **Installa**.
3. Apra **Configura** su **MyFAQ Free**. La pagina si apre su **Unlock Pro**. La barra ha anche **Settings** e **Updates**.
4. MyFAQ Free non aggiunge una voce al menu a sinistra. Le domande si scrivono su ogni prodotto.

L'installazione non svuota la cache di PrestaShop. Se dopo un aggiornamento la pagina prodotto mostra ancora il layout precedente, svuoti la cache in **Parametri avanzati**, **Prestazioni**.

Per spegnerlo usi l'interruttore in **Gestione moduli**. La pagina prodotto non stampa più le domande e la scheda prodotto non mostra più il blocco FAQ. Le domande e la posizione restano. Riaccenda il modulo e vengono usate come prima. Il modulo non ha un pulsante proprio di attivazione o disattivazione.

Per toglierlo clicchi **Disinstalla** e confermi. La disinstallazione toglie le domande, la posizione, il titolo della scheda e l'intestazione. Sparisce la pagina nascosta che salva le domande. I file del modulo restano sul server finché non cancella il modulo. Una nuova installazione parte con domande vuote, **Product footer**, il titolo scheda FAQ e un'intestazione vuota. Le domande vecchie non tornano. L'interruttore degli avvisi di aggiornamento è condiviso con gli altri moduli MyPresta e resta come lo ha lasciato.

## 3. Configurazione e lavoro quotidiano

Le schermate di questo manuale sono in inglese. Poi uso i nomi di questo manuale e cito la scritta come compare nel back office.

Le domande si scrivono sul prodotto, non nella pagina del modulo. Apra **Catalogo**, **Prodotti** e modifichi il prodotto. In un negozio con più negozi, la pagina prodotto chiede di scegliere un negozio nell'intestazione multinegozio. Apra la scheda **Modules** e in **Module to configure** scelga **MyFAQ Free**. Inserisca fino a tre domande, spunti **Show on the product page** e clicchi **Save these questions**. Uno slot con la domanda vuota resta fuori dalla pagina prodotto.

Nella pagina del modulo sceglie solo dove viene stampato quel blocco e come si chiama. **Product footer** stampa la fisarmonica sotto il prodotto. **Product tab** aggiunge una scheda prodotto e lascia il piè vuoto. Un prodotto senza domanda non mostra nulla in nessuno dei due posti.

Il cliente apre il prodotto, clicca una domanda e legge la risposta. Non c'è un modulo con cui il cliente invii una domanda nuova. Il percorso finisce quando la pagina prodotto mostra la fisarmonica, oppure quando il prodotto non ha nulla da mostrare.

Apra **Moduli**, **Gestione moduli**, **MyFAQ Free**, **Configura**. Sopra la barra la pagina dice **I am developing this module for free - if you want** e propone **send me a donation**. Sotto quella riga c'è una striscia di altri moduli. La nota sotto la barra dice che le domande si impostano su ogni prodotto.

### 3.1 Unlock Pro

![Unlock Pro](https://mypresta.eu/docs/images/docs/myfaqfree-configure-unlock.webp)

La schermata è la sezione **Unlock Pro**, con la riga della donazione sopra la barra.

**Unlock Pro** non salva un'impostazione e non scrive domande. La riga sotto la barra è **MyFAQ without the three-question limit**. Dice che MyFAQ tiene ogni domanda già scritta e aggiunge il catalogo, la scrittura con IA e l'API, e che le domande di un prodotto restano nel modulo gratuito finché non le sposta.

Il riquadro **The full FAQ for the catalogue** elenca ciò che aggiunge il modulo a pagamento e finisce con **See MyFAQ**. Quel pulsante apre la pagina del modulo a pagamento in una scheda nuova. Questa scheda non memorizza nulla per il modulo gratuito.

### 3.2 Settings

![Settings](https://mypresta.eu/docs/images/docs/myfaqfree-configure-settings.webp)

La schermata è la sezione **Settings**. L'immagine mostra un negozio che ha già salvato **Product tab** e un'intestazione. Un'installazione nuova usa i valori della tabella.

La riga sotto la barra è **Where the three questions are shown**. Dice che il modulo gratuito scrive la FAQ su ogni prodotto, al massimo tre domande, e che qui sceglie solo il piè di prodotto o una scheda prodotto, e i nomi di quel blocco.

Il titolo del modulo è **Placement**.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Show the FAQ** | Product footer | **Product footer** stampa la fisarmonica sotto il prodotto. **Product tab** aggiunge una scheda prodotto e lascia il piè vuoto. Un prodotto senza domanda non mostra nulla in nessuno dei due posti. |
| **Tab title** | FAQ in ogni lingua | Nome della scheda prodotto quando **Show the FAQ** è **Product tab**. Compili ogni lingua con il pulsante della lingua. Una lingua vuota mostra FAQ. |
| **Heading** | vuoto | Titolo sopra le domande, nel piè e nella scheda. Compili ogni lingua con il pulsante della lingua. Vuoto mostra solo le domande. |

Clicchi **Save**. La pagina mostra **Settings saved.**

Il pulsante della lingua mostra le lingue di questo negozio. Nel negozio della foto sono inglese, francese e polacco.

### 3.3 Updates

![Updates](https://mypresta.eu/docs/images/docs/myfaqfree-configure-updates.webp)

La schermata è la sezione **Updates**.

La riga sotto la barra è **Newer versions of MyFAQ Free**. Dice che il controllo segnala una versione e che installare il pacchetto resta un download manuale.

Il titolo del modulo è **MyPresta Updates**.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Check updates** | **Check now** | Controlla a mano se sui server di MyPresta.eu c'è una versione più nuova di questo modulo. Il pulsante non scarica e non installa il pacchetto. Dopo il controllo, accanto al pulsante compare **New version available!** oppure **Module is up to date!** |
| **Updates notifications** | Enable | Attivo, controlla MyPresta.eu in automatico e mostra un avviso sulle nuove versioni di questo addon. **Disable** ferma quel controllo automatico. L'interruttore è condiviso: gli altri moduli MyPresta di questo negozio usano lo stesso interruttore. Il controllo automatico gira circa ogni tre giorni mentre il back office è in uso. |
| **Module page** | un link di nome **MyFAQ Free** | Link diretto alla pagina ufficiale dell'addon, dove si leggono i cambiamenti del modulo (changelog). Il link apre [https://mypresta.eu/](https://mypresta.eu/). |

Clicchi **Save**. La pagina mostra **Update settings saved.**

Quando è stata segnalata una versione più nuova e gli avvisi sono attivi, il back office mostra **New version available, check http://MyPresta.eu for more informations** e il link **More details in changelog**. Quel link apre lo stesso indirizzo di **Module page**.

### 3.4 Domande sul prodotto

![FAQ sul prodotto](https://mypresta.eu/docs/images/docs/myfaqfree-product-block.webp)

La schermata è il blocco **MyFAQ Free** sul prodotto, nella scheda **Modules**. L'immagine è un prodotto che ha già tre domande. Un prodotto nuovo parte con i campi vuoti. EN, FR e PL sono le lingue di questo negozio.

Apra **Catalogo**, **Prodotti**, modifichi il prodotto, apra **Modules** e in **Module to configure** scelga **MyFAQ Free**.

Su un prodotto non ancora salvato, il blocco dice **Save the product first** e **The three FAQ slots appear after the product has an id.** Salvi il prodotto e torni a questo blocco.

Il riquadro **Three questions on this product** ripete la nota sul modulo a pagamento e finisce con **See MyFAQ**. Non memorizza le domande gratuite.

Sotto, **FAQ for this product** dice: tre domande, una domanda vuota resta fuori dalla pagina, e **Save these questions** la lascia su questo prodotto. I pulsanti della lingua cambiano domanda e risposta. Compaiono quando il negozio ha più di una lingua.

| Campo | All'inizio | Cosa fa |
|---|---|---|
| **Question 1**, **Question 2**, **Question 3** | tre slot vuoti, **Show on the product page** spuntato | I tre slot di questo prodotto in questo negozio. Il cliente li vede in quest'ordine. |
| **Show on the product page** | spuntato | Spuntato mostra lo slot quando la domanda è compilata. Tolga la spunta per tenere il testo e nascondere lo slot. |
| **Question** | vuoto | La riga che il cliente clicca. Il campo accetta 512 caratteri. Una domanda vuota resta fuori dalla pagina. Compili la domanda in ogni lingua in cui vende. Una lingua con la domanda vuota non viene mostrata in quella lingua. |
| **Answer** | vuoto | Il testo sotto la domanda. Un a capo nel campo diventa una riga nuova nella pagina prodotto. Il testo digitato viene mostrato come testo. |
| **Save these questions** | un pulsante | Salva i tre slot e resta su questo prodotto. Durante il salvataggio la riga sotto il pulsante dice **Saving the three questions…** Dopo un salvataggio riuscito dice **The three FAQ slots are saved. A slot with an empty question stays off the product page.** |

Fuori dal prodotto non c'è un elenco di domande né un'azione di massa. Cancellare il prodotto cancella le sue tre domande. Le domande scritte in un negozio non compaiono in un altro finché non le scrive lì.

## 4. Negozio

![Domande nella pagina prodotto](https://mypresta.eu/docs/images/docs/myfaqfree-front-tab.webp)

La schermata del negozio è in inglese.

Il cliente vede il blocco solo in una pagina prodotto, e solo quando quel prodotto ha almeno una domanda compilata, con **Show on the product page** spuntato e scritta nella lingua del cliente.

Con **Show the FAQ** su **Product footer**, la fisarmonica sta sotto il prodotto. Con **Product tab**, la stessa fisarmonica sta in una scheda prodotto e il piè resta vuoto. Il nome della scheda è **Tab title**. Un titolo di scheda vuoto compare come FAQ. L'immagine è la scheda di questo negozio: la scheda si chiama FAQ e l'intestazione è **Questions before you buy**.

L'intestazione, quando ne ha inserita una, viene stampata sopra le domande. La prima domanda è aperta al caricamento della pagina. Il cliente clicca una domanda per aprire o chiudere la risposta. Un cliente senza JavaScript vede ogni risposta. Sotto l'elenco, la riga **Powered by MyFAQ for PrestaShop** porta al modulo a pagamento.

Non c'è una pagina a parte, un indirizzo da copiare né un modulo per il cliente. Un prodotto che non ha nulla da mostrare non stampa il blocco.

## 5. Problemi

**Il prodotto non mostra domande.** La domanda di quella lingua è vuota, **Show on the product page** non è spuntato, il modulo è spento, oppure il tema non stampa il posto che ha scelto. Apra il prodotto, controlli lo slot e in **Settings** confermi **Show the FAQ**. **Product footer** chiede che il tema stampi il piè di prodotto. **Product tab** chiede che il tema stampi le schede prodotto extra. Un prodotto senza una domanda compilata non mostra nulla in nessuno dei due posti.

**Il blocco di un prodotto nuovo dice Save the product first.** Il prodotto non ha ancora un id. Salvi il prodotto, lo riapra e compaiono i tre slot. Se clicca **Save these questions** prima, la riga dice **Save the product first, then add the FAQ.**

**Save these questions finisce con The FAQ could not be saved.** Clicchi di nuovo **Save these questions**. Se fallisce ancora, verifichi che il modulo sia installato e che il profilo del dipendente possa modificare i prodotti.

**La riga dice The FAQ could not reach the shop.** Il browser non ha raggiunto il back office. Controlli la connessione e clicchi di nuovo **Save these questions**. Durante la richiesta la riga dice **Saving the three questions…**

**La domanda nel negozio è più corta di quella digitata.** Il campo della domanda si ferma a 512 caratteri.

**La risposta mostra i tag che ha digitato.** La risposta è testo semplice. L'a capo resta. I tag si vedono come caratteri.

**Il piè è vuoto dopo aver scelto Product tab.** È l'impostazione. **Product tab** lascia il piè vuoto e mette la fisarmonica nella scheda prodotto. Scelga **Product footer** in **Settings** e clicchi **Save** quando vuole la fisarmonica sotto il prodotto.

**Un altro negozio non mostra le domande.** I tre slot appartengono al negozio che ha modificato. Sposti l'intestazione multinegozio su quel negozio, apra il prodotto e scriva lì le domande.

**La pagina prodotto del back office chiede di scegliere un negozio.** La modifica del prodotto lavora in un negozio alla volta. Scelga il negozio nell'intestazione multinegozio, poi apra **Modules**.

**Check now dice Module is up to date! e si aspettava una versione più nuova.** Il controllo non ha letto una versione da MyPresta.eu, oppure questo pacchetto è quello segnalato dal server. Verifichi che il negozio raggiunga MyPresta.eu e clicchi di nuovo **Check now**. Il pulsante non installa mai il pacchetto.

**Un avviso dice New version available, check http://MyPresta.eu for more informations.** Gli avvisi sono attivi ed è stata segnalata una versione più nuova. Apra **Updates**, legga **Module page** e installi il pacchetto da sé quando lo vuole. **Disable** in **Updates notifications** ferma l'avviso. Quell'interruttore è condiviso con gli altri moduli MyPresta.

**La striscia della donazione resta vuota.** Il resto della pagina di configurazione continua a funzionare. Scriva le domande sul prodotto e imposti la posizione in **Settings**.

## 6. Per lo sviluppatore

### 6.1 Panoramica

Classe principale `myfaqfree`, versione `1.0.0`, nome in elenco **MyFAQ Free**, autore mypresta.eu, scheda `front_office_features`. La compatibilità è dichiarata da `1.7.0.0` a `9.99.99`.

La posizione si legge da `MYFAQFREE_DISPLAY` (`footer` finché il valore non è `tab`). Il titolo della scheda e l'intestazione si leggono per lingua da `MYFAQFREE_TAB_TITLE` e `MYFAQFREE_HEADING`. La pagina prodotto carica al massimo tre slot attivi del negozio e della lingua correnti con `MyfaqfreeRepository::frontItems()` e rende `views/templates/hook/product.tpl`. Il primo elemento riceve `is-open` nel template. La risposta viene escapata e passata a `nl2br`.

### 6.2 File

- `myfaqfree.php` — installazione, configurazione, pannello prodotto, render del front.
- `lib/MyfaqfreeRepository.php` — tre slot, tabelle, salvataggio e cancellazione.
- `lib/updatesChecker.php` — classe `myfaqfreeUpdate`, controllo aggiornamenti.
- `lib/prestashop9compatibility.php` — directory dei template HelperForm e `curl_close` prima di PHP 8.
- `controllers/admin/AdminMyfaqfreeController.php` — salvataggio ajax. Il controller è una scheda nascosta.
- `views/templates/admin/configure.tpl` — Unlock Pro, Settings, Updates.
- `views/templates/admin/_pro.tpl` — riquadro del modulo a pagamento.
- `views/templates/admin/product.tpl` — tre slot sul prodotto.
- `views/templates/hook/product.tpl` — fisarmonica. Variabili: `mff_heading`, `mff_items` (`id`, `question`, `answer`), `mff_pro_url`.
- `views/js/admin.js` — cambio lingua e salvataggio sul prodotto.
- `views/js/front.js` — aprire e chiudere una domanda.
- `views/css/admin.css`, `views/css/front.css`.
- `translations/en.php` — presente e vuoto. I testi inglesi sono i testi sorgente.

### 6.3 Controller

`AdminMyfaqfree` estende `ModuleAdminController`. La scheda nasce con `id_parent = -1`, quindi non sta nel menu a sinistra. Il nome di classe della scheda è `AdminMyfaqfree` e l'etichetta è MyFAQ Free. `ajaxProcessSave` inoltra a `myfaqfree::ajaxProcessSave()`. Il blocco prodotto invia `id_product`, `mff_on_{position}`, `mff_q_{position}_{id_lang}` e `mff_a_{position}_{id_lang}` a `AdminMyfaqfree` con `ajax=1` e `action=Save`.

Non c'è un controller di front. La fisarmonica viene resa dagli hook.

`getContent()` è la pagina di configurazione. `mff_tab` accetta `unlock`, `settings` e `updates`. Ogni altro valore apre `unlock`.

### 6.4 Hook

Registrati in `install()`:

| Hook | Ruolo |
|---|---|
| `displayHeader` | CSS e JS solo nella pagina prodotto. |
| `displayFooterProduct` | Fisarmonica quando la posizione è il piè. |
| `displayProductFooter` | La stessa fisarmonica. Un flag statico la stampa una volta per richiesta. |
| `displayProductExtraContent` | Una scheda prodotto quando la posizione è la scheda. Altrimenti un array vuoto. |
| `displayAdminProductsExtra` | I tre slot nella modifica del prodotto. |
| `actionAdminControllerSetMedia` | CSS e JS di amministrazione nella pagina prodotto e nella configurazione del modulo. |
| `actionProductDelete` | Cancella gli slot di quel prodotto. |

La classe non definisce `enable()` né `disable()`. Spegnere il modulo in Gestione moduli usa l'interruttore del core. La classe non espone un hook proprio.

`ensureHiddenTab()` e `grantHiddenTabAccess()` partono dal costruttore quando l'oggetto è `myfaqfree`, da `getContent()` e dall'hook del prodotto. L'accesso concede `view`, `add`, `edit` e `delete` al profilo 1 e al profilo del dipendente corrente.

### 6.5 Override

Il modulo non sovrascrive una classe né un controller.

### 6.6 Database

| Tabella | Contenuto |
|---|---|
| `ps_myfaqfree_item` | `id_item`, `id_product`, `id_shop`, `position` (1–3), `active`, `date_upd`. Chiave unica su prodotto, negozio e posizione. |
| `ps_myfaqfree_item_lang` | `id_item`, `id_lang`, `question` (varchar 512), `answer` (text). |

`uninstall()` elimina entrambe le tabelle quando `parent::uninstall()` restituisce true. Se `parent::uninstall()` restituisce false, le tabelle restano. La scheda e le tre chiavi di configurazione vengono eliminate prima di quel return. Cancellare un prodotto cancella le sue righe in entrambe le tabelle. Uno slot la cui domanda è vuota in ogni lingua viene eliminato al salvataggio. Una lingua con la domanda vuota non viene inserita.

Le tabelle nascono all'installazione. Aprire la pagina di configurazione non aggiunge una colonna.

### 6.7 Chiavi e traduzioni

| Chiave | Se manca o all'installazione |
|---|---|
| `MYFAQFREE_DISPLAY` | L'installazione scrive `footer`. Ogni valore diverso da `tab` è trattato come piè. |
| `MYFAQFREE_TAB_TITLE` | L'installazione scrive `FAQ` per ogni lingua. Una lingua vuota torna al testo sorgente FAQ in fase di render. |
| `MYFAQFREE_HEADING` | L'installazione scrive una stringa vuota per ogni lingua. Un'intestazione vuota non viene stampata. |
| `mypresta_updates` | Questo modulo non la crea. Se manca, è trattata come attiva. **Disable** scrive `0`. La disinstallazione non la cancella. |
| `update_myfaqfree` | Tempo Unix dell'ultimo controllo. La disinstallazione non lo cancella. |
| `updatev_myfaqfree` | Stringa di versione restituita dal controllo. La disinstallazione non la cancella. |

L'indirizzo del controllo è `https://dev.mypresta.eu/update/get.php`. L'intervallo è 259200 secondi. Si usa cURL quando esiste `curl_init`, con timeout di 3 secondi. Altrimenti `file_get_contents` quando `allow_url_fopen` è attivo. Il corpo della risposta viene ripulito dai tag e salvato come versione disponibile.

I testi del back office passano da `$this->l()`. Il modulo degli aggiornamenti usa la sorgente `updatesChecker`. Aggiunga una lingua con `translations/{iso}.php`. Testi che non passano da `$this->l()`: **Saving the three questions…**, **The FAQ could not reach the shop.** e i fallback JavaScript **The FAQ could not be saved.** e **Saved.** in `views/js/admin.js`. Il credito in vetrina **Powered by MyFAQ for PrestaShop** è fisso in `product.tpl`.

Le descrizioni dei campi sono le stringhe `desc` di `renderSettingsForm()` e di `renderUpdateForm()`.

### 6.8 Estensione

Sovrascriva `views/templates/hook/product.tpl` dal tema in `themes/{theme}/modules/myfaqfree/views/templates/hook/product.tpl`. Allo stesso modo `views/css/front.css` e `views/js/front.js`. Il template non viene reso quando il prodotto non ha uno slot visibile, quindi un override del tema non ha nulla da stampare in quel caso.

## 7. Aiuto

Pagina del modulo: [https://mypresta.eu/](https://mypresta.eu/)

Per scrivere a proposito di questo modulo, acceda all'account cliente su [mypresta.eu](https://mypresta.eu), apra il contatto e scelga l'argomento **Support for paid modules**. Il modulo indica che per quell'argomento l'accesso è obbligatorio. Dopo l'accesso, scelga questo modulo dalla cronologia degli acquisti. Questo modulo è gratuito: se non compare in quella cronologia, indichi **MyFAQ Free** nel messaggio.
