---
title: "CMS in homepage - Manuale per il Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop CMS in homepage di MyPresta.eu."
sidebar:
  label: "CMS in homepage - Manuale per il Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo CMS on homepage su MyPresta.eu](https://mypresta.eu/modules/front-office-features/cms-on-homepage.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/cms-on-homepage/)
>
> ---


# CMS in homepage

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5 (Sempre in estensione a PHP 8.5)
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso, e questo modulo non ha requisiti speciali aggiuntivi.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo "CMS in homepage". Verrai indirizzato alla sua schermata di configurazione principale.

#### Seleziona pagina CMS

Questa è l'impostazione principale per il modulo. Ti permette di scegliere quale delle tue pagine CMS esistenti avrà il suo contenuto visualizzato sulla homepage.

- **Cosa fa questa impostazione:** Questo menu a discesa elenca tutte le pagine CMS che hai creato nel tuo negozio PrestaShop (si trovano sotto **Parametri negozio > Pagine**). Selezioni una di queste pagine.
- **Effetto della modifica di questa impostazione:**
  - *Quando una pagina CMS è selezionata:* Il contenuto della pagina CMS scelta verrà recuperato e visualizzato sulla homepage del tuo negozio.
  - *Quando nessuna pagina CMS è selezionata (o se cambi idea):* Il modulo non visualizzerà alcun contenuto, oppure visualizzerà il contenuto della pagina appena selezionata.
- **Valore consigliato:** Scegli la pagina CMS il cui contenuto desideri mettere in evidenza sulla tua homepage. Potrebbe essere la tua pagina "Chi siamo", "Informazioni sulla spedizione", "Informativa sulla privacy" (se vuoi che sia molto visibile), o una pagina personalizzata con contenuti promozionali.
- **Scenario / esempio per il commerciante:** Hai una pagina CMS intitolata "La nostra storia" che descrive la storia e i valori del tuo brand. Selezionando "La nostra storia" qui, ogni visitatore della tua homepage vedrà immediatamente questo contenuto, aiutando a costruire la connessione e la fiducia nel brand.

Dopo aver effettuato la selezione, ricorda di cliccare sul pulsante **"Salva"** per applicare le modifiche.

### 2.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e Impatto |
| --- | --- | --- | --- |
| Pagina di configurazione del modulo | Seleziona pagina CMS | (Nessuna selezionata inizialmente) | Scegli quale contenuto della pagina CMS appare sulla homepage. |

## 3. Risoluzione dei problemi per il commerciante e domande frequenti (FAQ)

**D: Ho selezionato una pagina CMS, ma non appare nulla sulla mia homepage. Cosa c'è che non va?**
R:

1. **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** nel tuo Back Office e clicca su "Svuota la cache" (o "Svuota la cache di Smarty" nelle versioni precedenti). A volte PrestaShop ha bisogno di un aggiornamento della cache per visualizzare nuovi contenuti.
2. **Controlla lo stato della pagina CMS:** Assicurati che la pagina CMS selezionata sia attiva e visibile nel tuo negozio (vai su **Parametri negozio > Pagine** e controlla il suo stato).
3. **Compatibilità del tema:** Sebbene il modulo utilizzi hook standard di PrestaShop, alcuni temi altamente personalizzati potrebbero sovrascrivere questi hook o avere requisiti di layout specifici. Se svuotare la cache non aiuta, contatta lo sviluppatore del tuo tema o il supporto MyPresta.eu.

**D: Il contenuto CMS viene visualizzato, ma non ha un aspetto corretto (ad esempio, caratteri, colori, layout sbagliati).**
R: Il modulo si limita a iniettare il contenuto della tua pagina CMS. Lo stile (caratteri, colori, spaziatura) è tipicamente controllato dal CSS del tuo tema PrestaShop.

1. **Controlla il contenuto della pagina CMS:** Assicurati che non ci sia HTML personalizzato o styling inline in conflitto all'interno del contenuto della pagina CMS stessa che potrebbe causare problemi.
2. **Personalizzazione del tema:** Potrebbe essere necessario aggiungere CSS personalizzato al tuo tema per integrare meglio visivamente il contenuto CMS. Uno sviluppatore web può aiutarti in questo.

**D: Posso visualizzare più pagine CMS sulla homepage?**
R: Questo modulo specifico è progettato per visualizzare *una* pagina CMS selezionata. Se hai bisogno di visualizzare più blocchi distinti di contenuto CMS, dovresti combinarli in un'unica pagina CMS o cercare un modulo di gestione dei contenuti più avanzato.

**D: Come traduco il contenuto CMS per diverse lingue?**
R: Il contenuto della tua pagina CMS è gestito direttamente all'interno della funzionalità CMS principale di PrestaShop. Quando modifichi una pagina CMS (**Parametri negozio > Pagine**), puoi selezionare la lingua per modificarne il contenuto. Il modulo visualizzerà automaticamente il contenuto nella lingua attualmente selezionata dal cliente sul tuo storefront.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

### 4.1 Panoramica dell'architettura

Il modulo "CMS in homepage" è un modulo PrestaShop leggero progettato principalmente per iniettare il contenuto delle pagine CMS esistenti in vari hook della homepage. Segue una struttura standard dei moduli PrestaShop, sfruttando la classe `Module` e i suoi metodi `install()` e `uninstall()` per la configurazione e la pulizia, e `getContent()` per la configurazione del back-office. La visualizzazione front-office è gestita interamente tramite la registrazione degli hook e i template Smarty. Non introduce controller, modelli o JavaScript complessi personalizzati.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**: Nessuno. Tutto il rendering dei contenuti front-office è gestito direttamente tramite hook registrati all'interno del file principale del modulo.
- **Controller Admin Back-Office**: Nessuno. La configurazione del modulo è gestita tramite il metodo `getContent()` della classe principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

- Nessuno. Il modulo si basa sulle classi `CMS` e `Configuration` principali di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

- Nessuno. Il modulo non include alcun JavaScript personalizzato.

### 4.5 Fogli di stile CSS (`views/css/`)

- Nessuno. Il modulo non include alcun CSS personalizzato. Il contenuto CMS visualizzato eredita lo stile dal tema PrestaShop attivo.

### 4.6 Struttura del template Smarty (`views/templates/`)

- **`cmshomepage/views/templates/hook/cmshomepage.tpl`**

  - **Scopo:** Questo è il template principale responsabile del rendering del contenuto effettivo della pagina CMS selezionata. È progettato per essere agganciato a `displayHome` o `displayHomeTabContent` per l'output diretto del contenuto.
  - **Variabili:**
    - `{$cms_content}`: Il contenuto HTML della pagina CMS selezionata, recuperato e assegnato dal modulo.
  - **Output:** Renderizza il contenuto HTML grezzo della pagina CMS.
- **`cmshomepage/views/templates/hook/tab.tpl`**

  - **Scopo:** Questo template viene utilizzato quando il modulo è agganciato a `displayHomeTab`. Genera l'HTML per un'intestazione di scheda che, quando cliccata, rivela il contenuto CMS.
  - **Variabili:**
    - `{$tab_name}`: Il titolo della scheda, tipicamente derivato dal titolo della pagina CMS.
    - `{$tab_id}`: Un ID univoco per la scheda, utilizzato per collegarla al suo pannello di contenuto corrispondente.
  - **Output:** Un elemento `<li>` contenente un tag `<a>`, adatto per l'inclusione in una struttura di navigazione a schede.
- **`cmshomepage/views/templates/hook/tabContents.tpl`**

  - **Scopo:** Questo template viene utilizzato quando il modulo è agganciato a `displayHomeTabContent`. Genera l'HTML per il pannello di contenuto associato a una scheda.
  - **Variabili:**
    - `{$tab_id}`: L'ID univoco corrispondente all'ID di `tab.tpl`.
    - `{$cms_content}`: Il contenuto HTML della pagina CMS selezionata.
  - **Output:** Un elemento `<div>` con il contenuto della scheda, tipicamente nascosto per impostazione predefinita e rivelato tramite JavaScript quando la sua scheda corrispondente viene cliccata.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**:

  - Il modulo non crea tabelle di database personalizzate.
  - Memorizza la sua configurazione nella tabella `ps_configuration` utilizzando la chiave `CMSHOMEPAGE_ID_CMS` per memorizzare l'ID della pagina CMS selezionata.
- **Tabella degli hook registrati**:

| Nome dell'Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHomeTabContent` | Renderizza il contenuto all'interno di una scheda della homepage. | Output di `cmshomepage.tpl` o `tabContents.tpl` con il contenuto CMS. |
| `displayHomeTab` | Renderizza un'intestazione di scheda sulla homepage. | Output di `tab.tpl` con il titolo della pagina CMS come nome della scheda. |
| `displayHome` | Renderizza il contenuto direttamente nell'area principale della homepage. | Output di `cmshomepage.tpl` con il contenuto CMS. |

Il metodo `install()` del modulo registra questi hook. I metodi `hookDisplayHome()`, `hookDisplayHomeTab()` e `hookDisplayHomeTabContent()` in `cmshomepage.php` sono responsabili del recupero del contenuto della pagina CMS selezionata e del rendering del template appropriato.

### 4.8 Chiavi di configurazione

Il modulo utilizza le seguenti chiavi di configurazione in `ps_configuration`:

- `CMSHOMEPAGE_ID_CMS`: Memorizza l'`id_cms` della pagina CMS selezionata dal commerciante per essere visualizzata sulla homepage.

## 5. Supporto ufficiale e aggiornamenti

Per aggiornamenti ufficiali, correzioni di bug e supporto dedicato agli sviluppatori, fai riferimento al tuo account cliente su [MyPresta.eu](https://mypresta.eu/). Assicurati di utilizzare l'ultima versione del modulo per prestazioni ottimali e compatibilità con il tuo negozio PrestaShop.
