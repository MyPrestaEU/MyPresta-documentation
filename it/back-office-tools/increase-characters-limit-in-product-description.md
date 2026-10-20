---
title: "Aumentare il limite di caratteri nella descrizione del prodotto - Manuale del Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Aumentare il limite di caratteri nella descrizione del prodotto' di MyPresta.eu."
sidebar:
  label: "Aumentare il limite di caratteri nella descrizione del prodotto - Manuale del Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Increase characters limit in product description su MyPresta.eu](https://mypresta.eu/modules/administration-tools/increase-characters-limit-in-product-description.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/back-office-tools/increase-characters-limit-in-product-description/)
>
> ---


# Aumentare il limite di caratteri nella descrizione del prodotto

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5 (Sempre esteso a PHP 8.5 per la futura compatibilità)
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Non sono richieste configurazioni speciali del server oltre a un ambiente di hosting PrestaShop standard.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al nome del modulo per accedere alle sue impostazioni. Questa è la schermata di configurazione principale e unica per questo modulo.

#### Impostazioni e opzioni:

1. **Lunghezza della descrizione del prodotto**

   - **Cosa fa questa impostazione:** Questo campo controlla il numero massimo di caratteri consentiti nel campo "Descrizione" principale per tutti i tuoi prodotti nel Back Office di PrestaShop. Il limite predefinito di PrestaShop è di 21.844 caratteri.
   - **Effetto della modifica di questa impostazione:**
     - *Se impostato su un numero più alto:* Sarai in grado di inserire più caratteri nel campo della descrizione del prodotto durante la modifica dei prodotti. Ciò consente un contenuto più dettagliato.
     - *Se impostato su un numero più basso (sconsigliato):* Limiteresti la tua capacità di aggiungere contenuti dettagliati, troncando potenzialmente descrizioni esistenti più lunghe.
   - **Valore consigliato:** Un numero significativamente più alto come `65535` o `16777215` (che corrisponde ai limiti `MEDIUMTEXT` o `LONGTEXT` di MySQL, rimuovendo efficacemente i limiti pratici per la maggior parte dei contenuti). Puoi anche impostarlo a `0` o lasciarlo vuoto per rimuovere completamente il limite e utilizzare il massimo possibile.
   - **Scenario / esempio del commerciante:** Vendi gadget high-tech e devi includere specifiche tecniche estese, elenchi di compatibilità e guide per l'utente direttamente nella descrizione del prodotto. Impostare questo valore a `65535` ti assicura ampio spazio.
2. **Lunghezza del nome del prodotto**

   - **Cosa fa questa impostazione:** Questo campo controlla il numero massimo di caratteri consentiti per il campo "Nome del prodotto" per tutti i tuoi prodotti. Il limite predefinito di PrestaShop è tipicamente di 128 o 255 caratteri, a seconda della versione.
   - **Effetto della modifica di questa impostazione:**
     - *Se impostato su un numero più alto:* Puoi utilizzare nomi di prodotti più lunghi, il che può essere utile per prodotti molto specifici, inclusi numeri di modello, o per scopi SEO dove titoli più lunghi e descrittivi sono vantaggiosi.
     - *Se impostato su un numero più basso (sconsigliato):* Limiteresti la denominazione dei prodotti, potenzialmente causando problemi con prodotti esistenti o rendendo più difficile differenziare gli articoli.
   - **Valore consigliato:** Un numero più alto come `512` o `1024` se hai bisogno di nomi di prodotti molto lunghi. Per la maggior parte dei negozi, il valore predefinito è sufficiente, ma se hai esigenze specifiche (ad esempio, includere numeri di parte completi o descrizioni dettagliate del modello), aumentarlo è utile.
   - **Scenario / esempio del commerciante:** Vendi attrezzature industriali e i nomi dei prodotti spesso includono produttore, modello, caratteristiche specifiche e numeri di versione (ad esempio, "XYZ Corp. Miscelatore Industriale Heavy Duty Modello 5000-A con Controllo Velocità Variabile e Tramoggia in Acciaio Inox"). Aumentare questo limite a `512` ti consente di inserire il nome completo e descrittivo.
3. **PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG** (Questa è un'impostazione standard di PrestaShop, non direttamente controllata dal modulo, ma spesso rilevante per la modifica dei contenuti)

   - **Cosa fa questa impostazione:** Questa impostazione principale di PrestaShop determina se i dipendenti possono selezionare la lingua per un campo del modulo direttamente all'interno del modulo, o se la lingua del modulo è determinata dalla lingua del back office del dipendente. Non è un'impostazione del modulo ma è spesso visibile o rilevante quando si tratta di contenuti multilingue.
   - **Effetto della modifica di questa impostazione:**
     - *Quando abilitato:* I dipendenti possono cambiare la lingua per i campi di testo (come le descrizioni dei prodotti) direttamente nella pagina di modifica del prodotto, consentendo loro di inserire contenuti per diverse lingue senza cambiare l'intera lingua del loro back office.
     - *Quando disabilitato:* La lingua dei campi di testo corrisponderà alla lingua corrente del back office del dipendente. Per modificare i contenuti in un'altra lingua, il dipendente deve cambiare la lingua del proprio back office.
   - **Valore consigliato:** Generalmente **SÌ** per negozi multilingue con più editor di contenuti, in quanto migliora il flusso di lavoro.
   - **Scenario / esempio del commerciante:** Hai un editor di contenuti di lingua francese e un editor di contenuti di lingua inglese. Se questa opzione è abilitata, l'editor francese può scrivere la descrizione francese e quindi cambiare il menu a discesa della lingua in inglese per scrivere la descrizione inglese, tutto nella stessa pagina del prodotto.

#### 2.1.1 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Config. Modulo | Lunghezza descrizione prodotto | `65535` o `0` (nessun limite) | Aumenta il numero massimo di caratteri per le descrizioni dei prodotti. Consente contenuti più dettagliati e un migliore SEO. |
| Config. Modulo | Lunghezza nome prodotto | `512` o `1024` | Aumenta il numero massimo di caratteri per i nomi dei prodotti. Utile per titoli di prodotti altamente specifici o descrittivi. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: Ho aumentato il limite di caratteri, ma le mie descrizioni dei prodotti sembrano ancora troncate nel front office. Cosa c'è che non va?**
R: Questo è di solito un problema legato al tema, non un problema del modulo.
- **Controlla le impostazioni di visualizzazione del tuo tema:** Alcuni temi potrebbero avere il proprio CSS o JavaScript che tronca testi lunghi per adattarli a un layout di design specifico. Potrebbe essere necessario consultare la documentazione del tuo tema o uno sviluppatore web per regolare queste impostazioni.
- **Svuota la cache di Smarty:** Vai su **Parametri avanzati > Prestazioni** nel tuo Back Office di PrestaShop, scorri fino a "Svuota la cache" e clicca su "Svuota la cache". A volte i vecchi file di template vengono memorizzati nella cache.
- **Verifica nel Back Office:** Ricontrolla che la descrizione completa sia salvata correttamente nella pagina di modifica del prodotto nel tuo Back Office. Se è troncata lì, allora il modulo potrebbe non essere stato applicato correttamente (anche se questo è raro).

**D: Questo modulo influisce sul SEO?**
R: Indirettamente, sì, in modo molto positivo. Permettendoti di scrivere descrizioni di prodotti più lunghe, più dettagliate e ricche di parole chiave, fornisci più contenuti da scansionare e indicizzare ai motori di ricerca. Ciò può portare a un migliore posizionamento per le query di ricerca pertinenti e attrarre più traffico organico alle tue pagine prodotto.

**D: Questo modulo rallenterà il mio negozio?**
R: No, questo modulo ha un impatto trascurabile sulle prestazioni del negozio. Modifica principalmente le definizioni delle colonne del database durante l'installazione/configurazione. Una volta configurato, non aggiunge alcuna elaborazione complessa o script di front-office che rallenterebbero i tempi di caricamento della pagina. L'unico potenziale "rallentamento" potrebbe verificarsi se scrivi descrizioni estremamente lunghe che impiegano più tempo a caricarsi dal database, ma questo è di solito minimo e compensato dai benefici SEO.

**D: Ho cambiato i limiti, ma non vedo la modifica nella pagina di modifica del prodotto. Cosa devo fare?**
R:
- **Salva la configurazione del modulo:** Assicurati di aver cliccato sul pulsante "Salva" dopo aver modificato i limiti di caratteri nella pagina di configurazione del modulo.
- **Svuota la cache di PrestaShop:** Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota la cache".
- **Aggiorna il tuo browser:** A volte il browser memorizza nella cache vecchi moduli. Esegui un aggiornamento forzato (Ctrl+F5 o Cmd+Shift+R).
- **Esci e rientra:** Per alcune modifiche amministrative, uscire e rientrare nel Back Office può garantire che tutti i dati della sessione vengano aggiornati.

**D: C'è un limite massimo che posso impostare?**
R: Sebbene il modulo ti permetta di impostare praticamente qualsiasi numero, il limite pratico è determinato dalle capacità del tuo database. Per i campi `TEXT` in MySQL, il massimo è `65.535` caratteri. Per `MEDIUMTEXT`, è `16.777.215` caratteri, e per `LONGTEXT`, è `4.294.967.295` caratteri. Impostare `0` o lasciare il campo vuoto di solito imposterà il tipo `TEXT` più grande possibile, rimuovendo efficacemente qualsiasi limite pratico per la maggior parte dei contenuti. Per i nomi dei prodotti, `255` o `512` caratteri sono di solito più che sufficienti.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e Mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "Aumentare il limite di caratteri nella descrizione del prodotto" è un modulo PrestaShop leggero progettato principalmente per modificare lo schema del database per i campi di testo relativi ai prodotti. Opera alterando il `type` e la `size` di colonne specifiche nella tabella `ps_product_lang` (per le descrizioni) e nelle tabelle `ps_product` / `ps_product_lang` (per i nomi) durante la sua installazione e configurazione. Non introduce alcun controller front-office, classi personalizzate o JavaScript/CSS complessi. La sua funzionalità principale viene eseguita tramite i metodi `install()` e `getContent()` della classe principale del modulo.

### 4.2 Controller (`controllers/`)

Questo modulo **non** contiene alcun controller amministrativo Front-Office o Back-Office personalizzato. Tutta la configurazione è gestita direttamente all'interno del metodo `getContent()` del modulo.

### 4.3 Classi e modelli principali (`classes/`)

Questo modulo **non** introduce classi personalizzate o definizioni `ObjectModel`. Interagisce direttamente con le tabelle del database e le impostazioni di configurazione principali di PrestaShop esistenti.

### 4.4 Risorse JavaScript (`views/js/`)

Questo modulo **non** include alcun file JavaScript personalizzato.

### 4.5 Fogli di stile CSS (`views/css/`)

Questo modulo **non** include alcun file CSS personalizzato.

### 4.6 Struttura del template Smarty (`views/templates/`)

Questo modulo **non** include alcun file di template Smarty personalizzato. Il modulo di configurazione viene renderizzato direttamente all'interno del metodo `getContent()` utilizzando i componenti `HelperForm` standard di PrestaShop.

### 4.7 Schema del database e mappa degli hook

#### Tabelle del database

Il modulo interagisce principalmente con le seguenti tabelle principali di PrestaShop:

- `ps_product_lang`:
  - Colonna **`description`**: Modificata a un tipo `TEXT` più grande (ad esempio, `MEDIUMTEXT` o `LONGTEXT`) per accogliere più caratteri.
  - Colonna **`description_short`**: Non direttamente modificata da questo modulo, ma spesso correlata.
  - Colonna **`name`**: Modificata a un tipo `VARCHAR` più grande (ad esempio, `VARCHAR(512)`) per accogliere più caratteri.
- `ps_configuration`:
  - `chr_max_description_length`: Memorizza la lunghezza massima configurata per le descrizioni dei prodotti.
  - `chr_max_name_length`: Memorizza la lunghezza massima configurata per i nomi dei prodotti.
  - `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Una chiave di configurazione standard di PrestaShop, non creata dal modulo, ma spesso referenziata nel contesto della modifica dei contenuti.

Il metodo `install()` del modulo contiene query SQL per alterare queste colonne della tabella. Il metodo `uninstall()` tenta di ripristinare queste modifiche, sebbene possa essere necessaria una verifica manuale a seconda dello stato del database.

#### Tabella degli hook registrati

Questo modulo **non** registra alcun hook di visualizzazione front-office o back-office. La sua funzionalità è interamente basata sul backend modificando lo schema del database.

Il metodo `install()` del modulo potrebbe utilizzare implicitamente `Configuration::updateValue()` che non registra direttamente gli hook ma memorizza i valori.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Aumentare il limite di caratteri nella descrizione del prodotto", fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assisterti con qualsiasi problema o domanda tu possa avere riguardo alla funzionalità e alla compatibilità del modulo.
