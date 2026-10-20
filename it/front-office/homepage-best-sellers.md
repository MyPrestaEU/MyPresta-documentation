---
title: "Homepage Best Sellers - Manuale Commerciante e Guida alla Configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop Homepage Best Sellers di MyPresta.eu."
sidebar:
  label: "Homepage Best Sellers - Manuale Commerciante e Guida alla Configurazione"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Homepage Best Sellers su MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-best-sellers.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/homepage-best-sellers/)
>
> ---


# Homepage Best Sellers

## 1. Requisiti e Compatibilità

- **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilità PHP**: PHP 7.1 - 8.5
- **Requisiti di hosting**: Le estensioni PHP standard (cURL, JSON, OpenSSL) sono tipicamente richieste per un negozio PrestaShop e sono sufficienti per questo modulo. Non sono necessarie configurazioni server insolite o avanzate.

## 2. Guida completa alla configurazione (ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)

Dopo aver installato con successo il modulo "Homepage Best Sellers", naviga su **Moduli > Gestione moduli**, individua "Homepage Best Sellers" e clicca sul pulsante "Configura". Ti verrà presentata una schermata di configurazione semplice e intuitiva.

#### Impostazioni e Opzioni:

1.  **Numero di prodotti da visualizzare**

    -   **Cosa fa questa impostazione:** Questo è il controllo principale per il modulo. Determina esattamente quanti dei tuoi prodotti più venduti verranno mostrati all'interno del blocco "Best Sellers" sulla homepage del tuo negozio.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato / impostato su un numero più alto (es. 10):* La tua homepage presenterà più prodotti best-seller. Questo può essere ottimo per i negozi con una vasta gamma di articoli popolari, offrendo ai clienti più scelta. Tuttavia, tieni presente che un numero molto alto potrebbe rendere il blocco piuttosto lungo, richiedendo più scorrimento, o potrebbe potenzialmente ingombrare il design della tua homepage a seconda del tuo tema.
        -   *Quando disabilitato / impostato su un numero più basso (es. 4):* Verranno visualizzati meno prodotti best-seller. Questo rende il blocco più compatto e focalizzato, il che può essere ideale per design minimalisti o quando vuoi evidenziare solo i pochi articoli in assoluto più importanti.
    -   **Valore consigliato:** Un buon punto di partenza è solitamente tra **4 e 8 prodotti**. Questo fornisce abbastanza varietà senza sovraccaricare la pagina. Dovresti sperimentare con numeri diversi per vedere cosa si adatta meglio al tuo tema PrestaShop specifico e al layout generale della homepage.
    -   **Scenario / esempio del commerciante:** Se gestisci un negozio di moda e vuoi mostrare una selezione curata dei tuoi articoli più in voga, potresti impostarlo su `4`. Se hai un grande negozio di elettronica e vuoi dimostrare l'ampiezza dei tuoi gadget popolari, impostarlo su `8` o `10` potrebbe essere più efficace.
2.  **Visualizza gli attributi del prodotto sulla pagina del prodotto** (Chiave di configurazione: `PS_ATTRIBUTE_CATEGORY_DISPLAY`)

    -   **Cosa fa questa impostazione:** Questa impostazione, se presente nella configurazione del modulo, controlla se gli attributi del prodotto (come taglia, colore, materiale, ecc.) vengono visualizzati sulla pagina del prodotto quando un cliente visualizza un prodotto. È importante notare che `PS_ATTRIBUTE_CATEGORY_DISPLAY` è tipicamente un'impostazione globale di base di PrestaShop, non solitamente gestita da un modulo specifico come "Best Sellers". Se appare qui, è probabilmente un link di convenienza o un modulo che tenta di gestire un'impostazione globale.
    -   **Effetto della modifica di questa impostazione:**
        -   *Quando abilitato (es. "Sì" o selezionato):* Gli attributi del prodotto saranno chiaramente visibili sulla pagina del prodotto, consentendo ai clienti di selezionare varianti specifiche (es. "Rosso, Taglia M"). Questo è cruciale per i prodotti con opzioni.
        -   *Quando disabilitato (es. "No" o deselezionato):* Gli attributi del prodotto potrebbero essere nascosti o non visualizzati nel modo standard sulla pagina del prodotto, il che potrebbe confondere i clienti che cercano di selezionare le varianti del prodotto.
    -   **Valore consigliato:** **SÌ** (o abilitato). Per quasi tutti i negozi di e-commerce, è essenziale visualizzare gli attributi del prodotto sulle pagine dei prodotti per consentire ai clienti di scegliere le varianti e prendere decisioni di acquisto informate.
    -   **Scenario / esempio del commerciante:** Se vendi scarpe, abilitando questa opzione i clienti potranno selezionare "Taglia 9, Nero" dalle opzioni sulla pagina del prodotto della scarpa. Disabilitandola sarebbe impossibile per loro specificare la taglia o il colore desiderato.

#### Impostazioni interne/non configurabili:

-   `update_`, `updatev_`: Questi sono parametri interni di tracciamento della versione del modulo e di controllo degli aggiornamenti. Non sono destinati all'interazione del commerciante ma assicurano che il modulo possa verificare la sua versione e potenzialmente notificarti gli aggiornamenti.

### 2.2 Schermate di amministrazione dedicate e viste del controller

Il modulo "Homepage Best Sellers" è progettato per semplicità ed efficienza. Non introduce **nessuna** schermata di amministrazione aggiuntiva dedicata, voci di menu personalizzate o viste del controller complesse oltre alla sua singola e semplice pagina di configurazione accessibile tramite il Gestore moduli. Tutta la gestione viene eseguita direttamente su quella singola schermata.

### 2.3 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Valore predefinito / Consigliato | Scopo e Impatto |
| :--------------- | :--------------------- | :----------------------------- | :-------------- |
| Pagina di configurazione del modulo | Numero di prodotti da visualizzare | 4-8 | Controlla quanti prodotti best-seller vengono visualizzati sulla homepage. |
| Pagina di configurazione del modulo | Visualizza gli attributi del prodotto sulla pagina del prodotto | SÌ | Determina se gli attributi del prodotto (es. taglia, colore) sono visibili sulla pagina del prodotto. |
