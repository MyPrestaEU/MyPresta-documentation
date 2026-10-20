---
title: "Scheda prodotti più venduti nella homepage - Manuale per il commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Scheda prodotti più venduti nella homepage' di MyPresta.eu."
sidebar:
  label: "Scheda prodotti più venduti nella homepage - Manuale per il commerciante e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Homepage tab best sellers su MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-tab-best-sellers.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/homepage-tab-best-sellers/)
>
> ---


# Scheda prodotti più venduti nella homepage

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per PrestaShop stesso e sono solitamente disponibili su qualsiasi ambiente di hosting moderno.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo l'installazione, clicca su "Configura" accanto al modulo "Scheda prodotti più venduti nella homepage" in Gestione moduli. Verrai indirizzato alla sua pagina di configurazione.

#### Numero di prodotti da visualizzare

- **Cosa fa questa impostazione:** Questa impostazione controlla quanti prodotti più venduti verranno mostrati all'interno della scheda "Prodotti più venduti" sulla tua homepage.
- **Effetto della modifica di questa impostazione:**
  - *Se impostato su un numero più alto (ad esempio, 12):* Verranno visualizzati più prodotti nella scheda, offrendo ai clienti una selezione più ampia dei tuoi prodotti più venduti da sfogliare. Questo può essere utile per i negozi con molti articoli popolari.
  - *Se impostato su un numero più basso (ad esempio, 4):* Verranno visualizzati meno prodotti, creando una presentazione più concisa e focalizzata. Questo può essere vantaggioso per i negozi con meno prodotti più venduti o quando si desidera enfatizzare pochi selezionati.
- **Valore consigliato:** Un buon punto di partenza è tipicamente tra **8 e 12** prodotti. Questo fornisce una varietà sufficiente senza sopraffare il cliente o rendere la pagina troppo lunga.
- **Scenario / esempio del commerciante:** Se hai un catalogo ampio e molti prodotti che vendono costantemente bene, potresti impostarlo su 10 o 12 per mostrare più dei tuoi articoli popolari. Se preferisci una homepage più pulita e minimalista, potresti impostarlo su 6.

#### Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto ## 5. Casi d'uso pratici e migliori pratiche (Consigli professionali)

1. **Sfrutta la prova sociale per i nuovi visitatori:**
   - **Scenario:** Un nuovo cliente arriva sulla tua homepage. Non conosce il tuo marchio o i tuoi prodotti.
   - **Consiglio professionale:** La scheda "Prodotti più venduti" fornisce immediatamente una prova sociale, mostrando loro cosa stanno acquistando e amando gli altri clienti. Assicurati che i tuoi prodotti più venduti abbiano buone immagini e descrizioni chiare. Considera di avviare una promozione temporanea (ad esempio, "I nostri 5 prodotti più venduti - 10% di sconto questa settimana!") per attirare ancora più attenzione su questa sezione.
2. **Ottimizza per prodotti stagionali e di tendenza:**
   - **Scenario:** Il tuo negozio sperimenta picchi di vendite stagionali (ad esempio, regali per le vacanze, abbigliamento estivo) o ha prodotti che diventano improvvisamente di tendenza.
   - **Consiglio professionale:** Sebbene il modulo identifichi automaticamente i prodotti più venduti, puoi influenzare indirettamente questo aspetto promuovendo strategicamente determinati prodotti. Ad esempio, durante l'estate, se vuoi che i tuoi costumi da bagno appaiano in "Prodotti più venduti", assicurati che siano ben forniti, a prezzi competitivi e magari presenti in altre iniziative di marketing. Man mano che vendono di più, saliranno naturalmente nelle classifiche dei prodotti più venduti e appariranno nella scheda.
3. **Promuovi incrociando con altre sezioni della homepage:**
   - **Scenario:** Hai altre sezioni di prodotti sulla tua homepage (ad esempio, "Nuovi prodotti", "Prodotti in evidenza").
   - **Consiglio professionale:** Utilizza la scheda "Prodotti più venduti" come sezione complementare. Se un prodotto è nuovo e vende eccezionalmente bene, potrebbe apparire sia in "Nuovi prodotti" che in "Prodotti più venduti", rafforzando la sua popolarità. Evita di avere troppi prodotti sovrapposti, se possibile, per offrire ai clienti più varietà, ma non nascondere un prodotto nuovo e veramente più venduto solo per il gusto della varietà. La natura automatica del modulo gestirà questo aspetto in modo naturale.

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D1: La mia scheda "Prodotti più venduti" non viene visualizzata sulla homepage.**

- **R:** Innanzitutto, assicurati che il modulo sia installato e abilitato in **Moduli > Gestione moduli**. Quindi, controlla la sua configurazione. Se la scheda non appare ancora, potrebbe essere un problema di cache. Vai su **Parametri avanzati > Prestazioni** e clicca su "Svuota cache" (o "Svuota cache Smarty" nelle versioni precedenti). Se il tuo tema è fortemente personalizzato, potrebbe non agganciarsi correttamente a `displayHomeTab` e `displayHomeTabContent`. In questo caso, potresti dover consultare lo sviluppatore del tuo tema o un esperto di PrestaShop.

**D2: I prodotti nella scheda "Prodotti più venduti" non sembrano essere i miei veri prodotti più venduti.**

- **R:** Il modulo si basa sui dati di vendita interni di PrestaShop per determinare i prodotti più venduti.
  - Assicurati di avere dati di vendita effettivi per i prodotti. I nuovi negozi o i negozi con pochissime vendite potrebbero non avere dati sufficienti per un elenco significativo di "prodotti più venduti".
  - Il calcolo dei "prodotti più venduti" si basa solitamente sul numero di unità vendute in un periodo. Potrebbe essere necessario del tempo affinché le vendite recenti si riflettano nell'elenco.
  - Svuota la cache di PrestaShop (**Parametri avanzati > Prestazioni > Svuota cache**) per assicurarti che vengano recuperati i dati più recenti.

**D3: Con quale frequenza si aggiorna l'elenco dei "Prodotti più venduti"?**

- **R:** L'elenco dei prodotti più venduti viene generato dinamicamente da PrestaShop in base ai dati di vendita. Si aggiorna automaticamente man mano che gli ordini vengono effettuati ed elaborati. Tuttavia, affinché le modifiche siano visibili nel front office, potrebbe essere necessario svuotare la cache di PrestaShop, soprattutto se hai abilitato una cache aggressiva.

**D4: Posso cambiare il titolo della scheda (ad esempio, da "Prodotti più venduti" a "I nostri preferiti")?**

- **R:** Sì, puoi. Il titolo della scheda è tipicamente una stringa traducibile all'interno del modulo.
  1. Vai su **Internazionale > Traduzioni**.
  2. Seleziona "Traduzioni dei moduli installati".
  3. Scegli il tuo tema.
  4. Seleziona la tua lingua.
  5. Trova il modulo "Scheda prodotti più venduti nella homepage" nell'elenco.
  6. Individua la stringa di testo per il titolo della scheda (ad esempio, "Prodotti più venduti") e modificala con il testo desiderato. Ricorda di salvare le modifiche.

**D5: I prodotti appaiono strani o disallineati nella scheda.**

- **R:** Questo è solitamente un conflitto di stile CSS con il tuo tema PrestaShop. Il modulo fornisce i dati del prodotto, ma il tuo tema è responsabile di come tali dati vengono visualizzati (layout, font, colori, dimensioni delle immagini).
  - Assicurati che il tuo tema sia aggiornato.
  - Prova a svuotare la cache di PrestaShop (**Parametri avanzati > Prestazioni**).
  - Se il problema persiste, potrebbe essere necessario aggiungere CSS personalizzato al tuo tema per sovrascrivere lo stile predefinito del modulo o del tema. Questo di solito richiede uno sviluppatore web.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione fornisce una panoramica tecnica dettagliata del modulo "Scheda prodotti più venduti nella homepage" per sviluppatori e webmaster.

### 4.1 Panoramica dell'architettura

Il modulo `Scheda prodotti più venduti nella homepage` è un modulo PrestaShop semplice progettato per integrarsi perfettamente con il sistema di schede della homepage. Segue una classica struttura di modulo PrestaShop, utilizzando principalmente la classe `Module` e gli hook del front-office. Non introduce controller, modelli o JavaScript/CSS complessi personalizzati, affidandosi invece alle funzionalità principali di PrestaShop per il recupero dei dati del prodotto e allo stile del tema esistente per la presentazione. La sua logica principale risiede nel file `homebestsellerstab.php`, che gestisce la configurazione e la registrazione degli hook.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**: Nessuno. Il contenuto del front-office del modulo viene renderizzato direttamente tramite i template Smarty agganciati a `displayHomeTab` e `displayHomeTabContent`.
- **Controller Admin Back-Office**: Nessuno. La configurazione del modulo è gestita dal metodo `getContent()` all'interno della classe principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

- Nessuno. Il modulo non definisce classi personalizzate né estende `ObjectModel`. Sfrutta le classi `Product` e `ProductSale` (o meccanismi interni simili) di PrestaShop per recuperare i dati dei prodotti più venduti.

### 4.4 Risorse JavaScript (`views/js/`)

- Nessuno. Il modulo non include file JavaScript personalizzati. Qualsiasi comportamento interattivo (come il cambio di scheda) dovrebbe essere gestito dal JavaScript esistente del tema PrestaShop.

### 4.5 Fogli di stile CSS (`views/css/`)

- Nessuno. Il modulo non include file CSS personalizzati. Lo stile della scheda e degli elenchi di prodotti al suo interno dipende interamente dal tema PrestaShop attivo. Gli sviluppatori dovrebbero ispezionare l'HTML generato e mirare a classi/ID pertinenti nel CSS del loro tema per personalizzare l'aspetto.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo utilizza due file di template Smarty, entrambi situati nella directory `views/templates/hook/`, per renderizzare il suo contenuto nel front office.

- **`views/templates/hook/tab.tpl`**

  - **Hook**: `displayHomeTab`
  - **Scopo**: Questo template è responsabile del rendering dell'elemento scheda cliccabile effettivo sulla homepage. Tipicamente contiene il tag `<li>` o `<a>` che rappresenta la scheda "Prodotti più venduti", incluso il suo titolo traducibile.
  - **Output**: Un elemento scheda che, quando cliccato, rivela il contenuto renderizzato da `homebestsellerstab.tpl`.
- **`views/templates/hook/homebestsellerstab.tpl`**

  - **Hook**: `displayHomeTabContent`
  - **Scopo**: Questo template renderizza l'elenco o la griglia effettivi dei prodotti più venduti quando la scheda "Prodotti più venduti" è attiva. Riceve un array di dati del prodotto dalla logica PHP del modulo.
  - **Output**: Markup HTML per la visualizzazione dei prodotti (ad esempio, contenitori `div`, immagini del prodotto, nomi, prezzi, pulsanti aggiungi al carrello). Tipicamente itera sulla variabile `$products` passata ad esso.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**: Il modulo non crea tabelle del database personalizzate. Memorizza la sua configurazione (ad esempio, `HOME_BEST_NBR`) nella tabella `ps_configuration` di PrestaShop.
- **Tabella degli hook registrati**:

| Nome dell'hook | Tempistica di esecuzione | Scopo tecnico La chiave di configurazione `HOME_BEST_NBR` viene utilizzata per memorizzare il numero di prodotti da visualizzare.
`PS_LANG_DEFAULT` e `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` sono chiavi di configurazione core di PrestaShop utilizzate per gestire le impostazioni della lingua predefinita e della lingua del modulo dipendente. Queste non sono direttamente configurate dal modulo ma sono accessibili per contesto.

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti, correzioni di bug e supporto ufficiale per il modulo "Scheda prodotti più venduti nella homepage", fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu). È possibile scaricare la versione più recente del modulo dalla cronologia degli ordini. Per assistenza tecnica o domande, utilizzare i canali di supporto forniti sul sito web di MyPresta.eu.
