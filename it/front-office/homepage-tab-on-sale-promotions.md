---
title: "Scheda homepage in offerta (promozioni) - Manuale del commerciante e Guida alla configurazione"
description: "Manuale utente completo, guida alla configurazione schermata per schermata e riferimento per sviluppatori per il modulo PrestaShop 'Scheda homepage in offerta (promozioni)' di MyPresta.eu."
sidebar:
  label: "Scheda homepage in offerta (promozioni)"
---

> ⚠️ **Notice:** This is the documentazione ufficiale per il modulo PrestaShop.
> - 🛒 **Puoi trovare le specifiche commerciali complete, il changelog e le opzioni di acquisto sulla pagina ufficiale del prodotto su MyPresta.eu:** [Acquista il modulo Homepage tab on sale (promotions) su MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-tab-on-sale-promotions.html)
> - 🌐 **Hub ufficiale della documentazione online:** [Leggi la documentazione interattiva su MyPresta.eu](https://mypresta.eu/docs/it/front-office/homepage-tab-on-sale-promotions/)
>
> ---


# Scheda homepage in offerta (promozioni)

## 1. Requisiti e compatibilità
-   **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
-   **Compatibilità PHP**: PHP 7.1 - 8.5
-   **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 2. Panoramica completa della configurazione (ogni impostazione raggruppata per schermata)

### 2.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)
Questa è la schermata di configurazione principale e unica per il modulo "Scheda homepage in offerta (promozioni)". Puoi accedervi navigando su **Moduli > Gestione moduli** e cercando "Scheda homepage in offerta (promozioni)", quindi cliccando sul pulsante "Configura".

#### Impostazioni e opzioni:

-   **Numero di prodotti da visualizzare**
    -   **Cosa fa questa impostazione:** Controlla quanti prodotti verranno mostrati nella scheda "In offerta" sulla tua homepage. Se hai più prodotti in offerta di questo numero, verrà visualizzata solo la quantità specificata.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se impostato su un numero più alto (es. 10):* Più prodotti in offerta saranno visibili ai tuoi clienti contemporaneamente, aumentando potenzialmente la possibilità che trovino qualcosa che gli piace. Tuttavia, potrebbe rendere la pagina più lunga e richiedere più scorrimento.
        -   *Se impostato su un numero più basso (es. 4):* Verranno mostrati meno prodotti in offerta, rendendo la scheda più concisa e potenzialmente più veloce da caricare. Questo può essere utile per un design pulito ma potrebbe nascondere alcune offerte attraenti.
    -   **Valore consigliato:** Inizia con un valore tra **8 e 12**. Questo è un buon equilibrio per la maggior parte dei temi, fornendo una scelta sufficiente senza sopraffare il cliente.
    -   **Scenario/esempio del commerciante:** Se hai molti prodotti in offerta e vuoi evidenziare la varietà, potresti impostarlo a 12. Se preferisci un aspetto minimalista o hai solo poche promozioni chiave, impostarlo a 6 potrebbe essere migliore.

#### Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto
Il modulo PrestaShop "Scheda homepage in offerta (promozioni)" è uno strumento semplice ma efficace per evidenziare i prodotti attualmente in offerta speciale o sconto direttamente sulla homepage del tuo negozio. Crea una nuova scheda sulla tua homepage, accanto a quelle esistenti come "Nuovi prodotti" o "Bestseller", specificamente dedicata alla visualizzazione di questi articoli promozionali.

## 3. Requisiti e compatibilità
-   **Versioni PrestaShop supportate**: PrestaShop 1.7.x, 8.x, 9.x
-   **Compatibilità PHP**: PHP 7.1 - 8.5 (Sempre in estensione a PHP 8.5)
-   **Requisiti di hosting**: Estensioni PHP standard (cURL, JSON, OpenSSL).

## 4. Panoramica completa della configurazione (ogni impostazione raggruppata per schermata)

### 4.1 Pagina di configurazione del modulo (Back Office > Moduli > Configura)
Questa è la schermata di configurazione principale e unica per il modulo "Scheda homepage in offerta (promozioni)". Puoi accedervi andando su **Moduli > Gestione moduli**, cercando "Scheda homepage in offerta (promozioni)" e quindi cliccando sul pulsante "Configura".

#### Impostazioni e opzioni:

-   **Numero di prodotti da visualizzare**
    -   **Cosa fa questa impostazione:** Questa impostazione determina il numero massimo di prodotti scontati che verranno mostrati all'interno della scheda "In offerta" sulla homepage del tuo negozio. Se hai più prodotti attualmente in saldo del numero specificato qui, il modulo visualizzerà solo questa quantità impostata.
    -   **Effetto della modifica di questa impostazione:**
        -   *Se abilitato / impostato su un numero più alto (es. 12):* I tuoi clienti vedranno una selezione più ampia di prodotti promozionali quando cliccano sulla scheda "In offerta". Questo può essere vantaggioso per i negozi con molti sconti attivi, offrendo più scelta e potenzialmente aumentando la probabilità di un acquisto. Tuttavia, la visualizzazione di troppi prodotti potrebbe rendere la pagina più lunga e potrebbe aumentare leggermente il tempo di caricamento.
        -   *Se disabilitato / impostato su un numero più basso (es. 4):* Verranno visualizzati meno prodotti in saldo. Questo può creare una visualizzazione più pulita e focalizzata, che potrebbe essere preferita se hai solo poche promozioni chiave o desideri mantenere la tua homepage molto concisa. Può anche portare a un caricamento più rapido della pagina.
    -   **Valore consigliato:** Un buon punto di partenza è **da 8 a 10 prodotti**. Questo fornisce una selezione decente senza sopraffare il cliente o rendere la pagina eccessivamente lunga. Puoi regolarlo in base al numero medio di articoli in saldo e al layout del tuo tema.
    -   **Scenario/esempio del commerciante:**
        -   *Scenario 1 (Ampio inventario, vendite frequenti):* Esegui promozioni settimanali con oltre 50 prodotti in saldo. Potresti impostarlo a **12** per dare ai clienti una buona panoramica della varietà di offerte disponibili direttamente dalla homepage.
        -   *Scenario 2 (Negozio boutique, poche promozioni chiave):* Tipicamente hai solo 3-5 articoli di alto valore in saldo in un dato momento. Potresti impostarlo a **6** per assicurarti che tutte le tue promozioni chiave siano visibili senza spazi vuoti o scorrimenti inutili.

### 4.2 Tabella di riferimento rapido della configurazione

| Schermata / Vista | Impostazione / Opzione | Predefinito / Consigliato | Scopo e impatto
Il
