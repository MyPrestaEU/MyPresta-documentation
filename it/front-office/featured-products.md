---
title: "Prodotti in evidenza - Manuale per il commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Prodotti in evidenza di MyPresta.eu."
sidebar:
  label: "Prodotti in evidenza - Manuale per il commerciante e Guida alla configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Featured Products su MyPresta.eu](https://mypresta.eu/modules/front-office-features/featured-products.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/featured-products/)
>
> ---


# Prodotti in evidenza

## 1. Requisiti e compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente sufficienti. Non sono richieste configurazioni speciali del server.

## 2. Guida completa alla configurazione (Ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Per accedere alla configurazione, vai su **Moduli > Gestione moduli**, cerca "Prodotti in evidenza" e fai clic su "Configura".

Questa schermata ti consente di definire quali prodotti vengono visualizzati e come appaiono sulla tua homepage.

#### Impostazioni e opzioni:

1. **ID Categoria Sorgente**

   - **Cosa fa questa impostazione:** Questa è l'impostazione più cruciale. Determina *quali* prodotti di categoria verranno visualizzati come "in evidenza" sulla tua homepage. Devi inserire l'ID numerico della categoria che desideri mostrare.
   - **Effetto della modifica di questa impostazione:**
     - *Quando impostato su un ID Categoria valido (es. `3` per "Abbigliamento"):* Il modulo recupererà e visualizzerà i prodotti appartenenti alla categoria con quell'ID.
     - *Quando impostato su un ID non valido o inesistente:* Nessun prodotto verrà visualizzato, o potrebbe verificarsi un errore se l'ID è malformato.
   - **Valore consigliato:** L'ID della categoria che desideri promuovere.
   - **Scenario / esempio per il commerciante:** Se desideri mettere in evidenza la tua categoria "Nuovi arrivi" (che ha un ID di, diciamo, `12`), dovresti inserire `12` qui. Per trovare un ID di categoria, vai su **Catalogo > Categorie** nel tuo Back Office, fai clic su "Modifica" su una categoria e guarda l'URL nel tuo browser (es. `id_category=12`).
2. **Numero di Prodotti**

   - **Cosa fa questa impostazione:** Controlla quanti prodotti dalla tua "Categoria Sorgente" selezionata verranno visualizzati sulla homepage.
   - **Effetto della modifica di questa impostazione:**
     - *Quando impostato su `5`:* Verranno mostrati solo i primi 5 prodotti della categoria scelta.
     - *Quando impostato su `10`:* Verranno visualizzati fino a 10 prodotti.
   - **Valore consigliato:** Un numero ragionevole come `8` o `12` per evitare di sovraccaricare la homepage, ma sufficiente per mostrare varietà. Considera il layout del tuo tema.
   - **Scenario / esempio per il commerciante:** Se la tua categoria "Nuovi arrivi" ha 50 prodotti, ma vuoi mostrare solo gli ultimi 8 sulla homepage, imposteresti questo valore su `8`.
3. **Posizione di Posizionamento**

   - **Cosa fa questa impostazione:** Determina *come* i prodotti in evidenza vengono visualizzati sulla tua homepage: direttamente nell'area del contenuto principale (`displayHome`) o all'interno di una scheda (`displayHomeTabContent`).
   - **Effetto della modifica di questa impostazione:**
     - *Quando impostato su `Scheda Homepage`:* I prodotti appariranno sotto una nuova scheda sulla tua homepage (es. "Prodotti in evidenza"). Ciò richiede che il tuo tema supporti le schede della homepage.
     - *Quando impostato su `Homepage`:* I prodotti verranno visualizzati come una sezione autonoma direttamente sulla tua homepage, senza essere nascosti dietro una scheda.
   - **Valore consigliato:**
     - Scegli `Scheda Homepage` se il tuo tema utilizza le schede per le liste di prodotti (come spesso fanno i temi PrestaShop predefiniti) e vuoi mantenere la tua homepage pulita.
     - Scegli `Homepage` se desideri la massima visibilità per questi prodotti e il tuo tema ha ampio spazio nell'area del contenuto principale.
   - **Scenario / esempio per il commerciante:** Se stai eseguendo una promozione speciale e desideri che i prodotti siano immediatamente visibili senza che i clienti debbano fare clic su una scheda, selezioneresti `Homepage`. Se hai molti tipi di prodotti in evidenza sulla tua homepage e desideri organizzarli in modo ordinato, `Scheda Homepage` è una scelta migliore.

#### Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto |
| --- | --- | --- | --- |
| Configurazione modulo | ID Categoria Sorgente | (Il tuo ID Categoria) | Specifica quali prodotti di categoria vengono visualizzati. |
| Configurazione modulo | Numero di Prodotti | 8-12 | Limita il numero di prodotti mostrati dalla categoria selezionata. |
| Configurazione modulo | Posizione di Posizionamento | Scheda Homepage / Homepage | Determina se i prodotti appaiono in una scheda o direttamente sulla homepage. |

## 3. Risoluzione dei problemi del commerciante e domande frequenti (FAQ)

**D: I miei prodotti in evidenza non vengono visualizzati sulla homepage.**
R:

1. **Controlla "ID Categoria Sorgente":** Assicurati di aver inserito un ID di categoria corretto ed esistente. Vai su **Catalogo > Categorie**, modifica la categoria desiderata e trova il suo ID nell'URL del browser (es. `id_category=X`).
2. **Controlla "Numero di Prodotti":** Assicurati che sia impostato su un valore maggiore di 0.
3. **Controlla "Posizione di Posizionamento":** Se impostato su "Scheda Homepage", assicurati che il tuo tema supporti e visualizzi effettivamente le schede della homepage. Alcuni temi personalizzati potrebbero non farlo. Prova a passare a "Homepage" per vedere se appaiono come sezione diretta.
4. **Svuota la cache:** Vai su **Parametri avanzati > Prestazioni** e fai clic su "Svuota la cache". A volte, la cache di PrestaShop impedisce che le modifiche appaiano immediatamente.

**D: I prodotti vengono visualizzati, ma sembrano disallineati o hanno uno stile errato.**
R: Questo è solitamente un problema legato al tema.

1. **Compatibilità del tema:** Sebbene il modulo sia compatibile con le versioni di PrestaShop, il suo output visivo potrebbe entrare in conflitto con temi altamente personalizzati.
2. **Conflitto CSS:** Il CSS del tuo tema potrebbe sovrascrivere o entrare in conflitto con lo stile predefinito del modulo. Potrebbe essere necessario un web developer per ispezionare il CSS e applicare stili personalizzati a `featuredcategory.css` o al file CSS personalizzato del tuo tema.

**D: Posso mettere in evidenza prodotti da più categorie?**
R: Non direttamente con questo modulo. Il modulo "Prodotti in evidenza" è progettato per visualizzare i prodotti da *una* categoria selezionata alla volta. Se hai bisogno di mettere in evidenza prodotti da più categorie contemporaneamente, dovresti:
a) Creare una nuova categoria "Master in evidenza" e aggiungervi prodotti da varie categorie.
b) Installare più istanze di questo modulo (se il tuo tema lo consente) o utilizzare un modulo diverso progettato per visualizzazioni multi-categoria.

**D: Come traduco il titolo della scheda "Prodotti in evidenza"?**
R: Se stai utilizzando il posizionamento "Scheda Homepage", il titolo della scheda è solitamente generato dal modulo.

1. Vai su **Internazionale > Traduzioni**.
2. Seleziona "Traduzioni dei moduli installati", il tuo tema e la tua lingua.
3. Cerca il modulo "Prodotti in evidenza". Dovresti trovare la stringa di testo per il titolo della scheda lì e puoi tradurla.

## 4. Guida per sviluppatori e webmaster (Architettura tecnica e mappa del codice)

Questa sezione è strettamente per sviluppatori, webmaster di negozi e agenzie tecniche che mantengono o estendono il negozio.

### 4.1 Panoramica dell'architettura

Il modulo `Featured Products` è un modulo PrestaShop semplice progettato principalmente per visualizzare un elenco di prodotti da una categoria specificata sulla homepage. Sfrutta il sistema di hook di PrestaShop (`displayHome`, `displayHomeTab`, `displayHomeTabContent`) per iniettare il suo contenuto. La logica del modulo è contenuta nel suo file PHP principale, `featuredcategory.php`, che gestisce la configurazione, l'installazione e il rendering del contenuto. Non introduce controller, modelli o JavaScript complessi personalizzati, rendendolo una soluzione leggera e facilmente manutenibile.

### 4.2 Controller (`controllers/`)

- **Controller Front-Office**: Nessuno. Tutto il rendering del contenuto del front-office è gestito direttamente tramite hook nel file `featuredcategory.php` principale e nei relativi template Smarty.
- **Controller Admin Back-Office**: Nessuno. La configurazione del modulo è gestita tramite il metodo standard `getContent()` nel file principale del modulo.

### 4.3 Classi e modelli principali (`classes/`)

- Nessuna classe personalizzata o definizione di `ObjectModel` è presente in questo modulo. Tutti i recuperi di dati (prodotti, categorie) vengono eseguiti utilizzando le classi `Product` e `Category` principali di PrestaShop.

### 4.4 Risorse JavaScript (`views/js/`)

- Nessun file JavaScript personalizzato è incluso in questo modulo.

### 4.5 Fogli di stile CSS (`views/css/`)

- `featuredcategory/css/featuredcategory.css`
  - **Ambito:** Stile del cliente del front-office.
  - **Componenti UI principali e contenitori che stilizza:** Questo foglio di stile fornisce uno stile di base per l'elenco dei prodotti generato dal modulo, assicurando che appaia presentabile nel contesto della homepage. Probabilmente si rivolge a contenitori generici di elenchi di prodotti e a singoli elementi di prodotto.
  - **Selettori di classe CSS chiave che gli sviluppatori possono sovrascrivere nel loro tema:** Gli sviluppatori possono ispezionare l'output HTML del modulo per identificare classi specifiche (es. `.featuredcategory-products`, `.product-item`, `.product-name`) e sovrascriverle nel file CSS personalizzato del loro tema per adattarle al design generale del negozio.

### 4.6 Struttura del template Smarty (`views/templates/`)

Il modulo utilizza i template Smarty per renderizzare il suo contenuto, principalmente per gli hook della homepage.

- **Template degli hook (`views/templates/hook/`)**:
  - `featuredcategory/views/templates/hook/featuredcategory17-tabContents.tpl`
    - **Hook:** `displayHomeTabContent`
    - **Scopo:** Questo template è responsabile del rendering dell'elenco effettivo dei prodotti in evidenza quando la "Posizione di Posizionamento" è impostata su "Scheda Homepage". Tipicamente contiene il ciclo per iterare i prodotti e visualizzare i loro dettagli (immagine, nome, prezzo, pulsante aggiungi al carrello).
  - `featuredcategory/views/templates/hook/featuredcategory17.tpl`
    - **Hook:** `displayHome`
    - **Scopo:** Questo template renderizza l'elenco dei prodotti in evidenza quando la "Posizione di Posizionamento" è impostata su "Homepage" (cioè, non in una scheda). Produrerà la stessa struttura dell'elenco dei prodotti di `featuredcategory17-tabContents.tpl` ma direttamente nell'hook `displayHome` principale.
  - `featuredcategory/views/templates/hook/tab.tpl`
    - **Hook:** `displayHomeTab`
    - **Scopo:** Questo template renderizza il titolo effettivo della scheda (es. "Prodotti in evidenza") che appare sulla homepage quando la "Posizione di Posizionamento" è impostata su "Scheda Homepage". Fornisce l'elemento cliccabile che rivela il contenuto da `featuredcategory17-tabContents.tpl`.
- **Template admin (`views/templates/admin/`)**: Nessuno.
- **Template front-office (`views/templates/front/`)**: Nessuno.

### 4.7 Schema del database e mappa degli hook

- **Tabelle del database**: Questo modulo non crea tabelle del database personalizzate. Memorizza le sue impostazioni di configurazione nella tabella `ps_configuration` di PrestaShop.

  - Voci `ps_configuration`:
    - `CFEATURED_NBR`: Memorizza l'impostazione "Numero di Prodotti".
    - `CFEATURED_ID`: Memorizza l'impostazione "ID Categoria Sorgente".
    - `CFEATURED_WHERE`: Memorizza l'impostazione "Posizione di Posizionamento" (es. 'tab' o 'home').
    - `mypresta_updates`: Utilizzato per i controlli di aggiornamento del modulo da parte di MyPresta.eu.
- **Tabella degli hook registrati**:

| Nome Hook | Tempo di esecuzione | Scopo tecnico |
| --- | --- | --- |
| `displayHomeTab` | Renderizza il contenuto per una nuova scheda sulla homepage. | Emette l'HTML per il titolo della scheda "Prodotti in evidenza". |
| `displayHomeTabContent` | Renderizza il contenuto per la scheda selezionata sulla homepage. | Emette l'HTML per l'elenco dei prodotti in evidenza quando la scheda è attiva. |
| `displayHome` | Renderizza il contenuto direttamente nell'area principale della homepage. | Emette l'HTML per l'elenco dei prodotti in evidenza quando non si utilizzano le schede. |
| `displayHeader` | Eseguito nella sezione `<head>` di ogni pagina. | Utilizzato per includere il foglio di stile CSS del modulo (`featuredcategory.css`) per la visualizzazione del front-office. |
| `actionProductDelete` | Attivato dopo l'eliminazione di un prodotto. | Potenzialmente utilizzato per svuotare la cache o rivalutare i prodotti in evidenza se il prodotto eliminato era nella categoria in evidenza. |
| `actionProductUpdate` | Attivato dopo l'aggiornamento di un prodotto. | Potenzialmente utilizzato per svuotare la cache o rivalutare i prodotti in evidenza se il prodotto aggiornato è nella categoria in evidenza. |
| `actionProductAdd` | Attivato dopo l'aggiunta di un nuovo prodotto. | Potenzialmente utilizzato per svuotare la cache o rivalutare i prodotti in evidenza se il nuovo prodotto è nella categoria in evidenza. |
| `actionCategoryUpdate` | Attivato dopo l'aggiornamento di una categoria. | Potenzialmente utilizzato per svuotare la cache o rivalutare i prodotti in evidenza se la categoria in evidenza stessa viene aggiornata. |

## 5. Supporto ufficiale e aggiornamenti

Per gli ultimi aggiornamenti del modulo, correzioni di bug e supporto ufficiale, si prega di fare riferimento al proprio account cliente su [MyPresta.eu](https://mypresta.eu/my-account/orders/). Il nostro team di supporto è disponibile per assistere con qualsiasi problema o domanda riguardante il modulo "Prodotti in evidenza".
