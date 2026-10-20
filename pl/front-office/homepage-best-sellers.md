---
title: "Najlepiej Sprzedające się Produkty na Stronie Głównej - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla deweloperów modułu PrestaShop „Najlepiej Sprzedające się Produkty na Stronie Głównej” od MyPresta.eu."
sidebar:
  label: "Najlepiej Sprzedające się Produkty na Stronie Głównej"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Homepage Best Sellers na MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-best-sellers.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/homepage-best-sellers/)
>
> ---


# Najlepiej Sprzedające się Produkty na Stronie Głównej

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla sklepu PrestaShop i są wystarczające dla tego modułu. Nie są potrzebne żadne nietypowe ani zaawansowane konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel Administracyjny > Moduły > Konfiguruj)

Po pomyślnej instalacji modułu „Najlepiej Sprzedające się Produkty na Stronie Głównej”, przejdź do **Moduły > Menedżer modułów**, znajdź „Najlepiej Sprzedające się Produkty na Stronie Głównej” i kliknij przycisk „Konfiguruj”. Zostanie wyświetlony prosty, intuicyjny ekran konfiguracji.

#### Ustawienia i opcje:

1.  **Liczba produktów do wyświetlenia**

    -   **Co robi to ustawienie:** Jest to główne sterowanie modułem. Określa dokładnie, ile najlepiej sprzedających się produktów zostanie zaprezentowanych w bloku „Najlepiej sprzedające się” na stronie głównej Twojego sklepu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone / ustawione na wyższą liczbę (np. 10):* Twoja strona główna będzie zawierać więcej najlepiej sprzedających się produktów. Może to być świetne dla sklepów z szeroką gamą popularnych pozycji, oferując klientom większy wybór. Należy jednak pamiętać, że bardzo duża liczba może sprawić, że blok będzie dość długi, wymagając więcej przewijania, lub potencjalnie zaśmiecić projekt strony głównej w zależności od Twojego motywu.
        -   *Gdy wyłączone / ustawione na niższą liczbę (np. 4):* Wyświetlanych będzie mniej najlepiej sprzedających się produktów. Sprawia to, że blok jest bardziej kompaktowy i skoncentrowany, co może być idealne dla minimalistycznych projektów lub gdy chcesz wyróżnić tylko absolutnie kilka najlepszych pozycji.
    -   **Zalecana wartość:** Dobrym punktem wyjścia jest zazwyczaj od **4 do 8 produktów**. Zapewnia to wystarczającą różnorodność bez przytłaczania strony. Powinieneś eksperymentować z różnymi liczbami, aby zobaczyć, co najlepiej wygląda z Twoim konkretnym motywem PrestaShop i ogólnym układem strony głównej.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli prowadzisz sklep z modą i chcesz pokazać wyselekcjonowany wybór swoich absolutnie najgorętszych pozycji, możesz ustawić to na `4`. Jeśli masz duży sklep z elektroniką i chcesz zademonstrować szeroki zakres swoich popularnych gadżetów, ustawienie na `8` lub `10` może być bardziej efektywne.
2.  **Wyświetlaj atrybuty produktu na stronie produktu** (Klucz konfiguracji: `PS_ATTRIBUTE_CATEGORY_DISPLAY`)

    -   **Co robi to ustawienie:** To ustawienie, jeśli jest obecne w konfiguracji modułu, kontroluje, czy atrybuty produktu (takie jak rozmiar, kolor, materiał itp.) są wyświetlane na rzeczywistej stronie produktu, gdy klient przegląda produkt. Ważne jest, aby zauważyć, że `PS_ATTRIBUTE_CATEGORY_DISPLAY` jest zazwyczaj globalnym ustawieniem rdzenia PrestaShop, a nie zazwyczaj zarządzanym przez konkretny moduł, taki jak „Najlepiej sprzedające się”. Jeśli pojawia się tutaj, jest to prawdopodobnie wygodne łącze lub moduł próbujący zarządzać globalnym ustawieniem.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (np. „Tak” lub zaznaczone):* Atrybuty produktu będą wyraźnie widoczne na stronie produktu, umożliwiając klientom wybór konkretnych wariantów (np. „Czerwony, Rozmiar M”). Jest to kluczowe dla produktów z opcjami.
        -   *Gdy wyłączone (np. „Nie” lub odznaczone):* Atrybuty produktu mogą być ukryte lub nie wyświetlane w standardowy sposób na stronie produktu, co może wprowadzić w błąd klientów próbujących wybrać warianty produktu.
    -   **Zalecana wartość:** **TAK** (lub włączone). Dla prawie wszystkich sklepów e-commerce, wyświetlanie atrybutów produktu na stronie produktu jest niezbędne, aby umożliwić klientom wybór wariantów i podejmowanie świadomych decyzji zakupowych.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli sprzedajesz buty, włączenie tego zapewnia, że klienci mogą wybrać „Rozmiar 9, Czarny” z opcji na stronie produktu buta. Wyłączenie tego uniemożliwiłoby im określenie pożądanego rozmiaru lub koloru.

#### Ustawienia wewnętrzne/niekonfigurowalne:

-   `update_`, `updatev_`: Są to wewnętrzne parametry śledzenia wersji modułu i sprawdzania aktualizacji. Nie są przeznaczone do interakcji ze sprzedawcą, ale zapewniają, że moduł może zweryfikować swoją wersję i potencjalnie powiadomić o aktualizacjach.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Moduł „Najlepiej Sprzedające się Produkty na Stronie Głównej” został zaprojektowany z myślą o prostocie i wydajności. Nie wprowadza **żadnych** dodatkowych dedykowanych ekranów administracyjnych, niestandardowych pozycji menu ani złożonych widoków kontrolerów poza swoją pojedynczą, prostą stroną konfiguracji dostępną poprzez Menedżer Modułów. Całe zarządzanie odbywa się bezpośrednio na tym jednym ekranie.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ
|---|---|---|---|
| Strona konfiguracji modułu | Liczba produktów do wyświetlenia | 4-8 | Określa, ile najlepiej sprzedających się produktów zostanie wyświetlonych na stronie głównej. |
| Strona konfiguracji modułu | Wyświetlaj atrybuty produktu na stronie produktu | TAK | Kontroluje, czy atrybuty produktu (np. rozmiar, kolor) są widoczne na stronie produktu. |
