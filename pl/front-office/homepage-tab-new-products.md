---
title: "Zakładka Nowe produkty na stronie głównej - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop 'Homepage tab new products' od MyPresta.eu."
sidebar:
  label: "Zakładka Nowe produkty na stronie głównej"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Homepage tab new products na MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-tab-new-products.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/homepage-tab-new-products/)
>
> ---


# Zakładka Nowe produkty na stronie głównej

## 1. Wymagania i kompatybilność
- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)
Po instalacji kliknij "Konfiguruj" obok modułu "Homepage tab new products" w Menedżerze modułów. Zostaniesz przeniesiony do głównego ekranu konfiguracji.

#### **Liczba produktów do wyświetlenia**
-   **Co robi to ustawienie:** Kontroluje, ile najnowszych produktów zostanie wyświetlonych w zakładce "Nowe produkty" na Twojej stronie głównej.
-   **Efekt zmiany tego ustawienia:**
    -   *Ustawione na wyższą liczbę (np. 12):* Więcej nowych produktów będzie widocznych dla klientów bez konieczności przechodzenia na pełną stronę "Nowe produkty". Może to być świetne dla sklepów z dużą ilością nowych dostaw.
    -   *Ustawione na niższą liczbę (np. 4):* Mniej produktów zostanie wyświetlonych, co skutkuje czystszym, mniej zaśmieconym wyglądem. Może to być preferowane, jeśli chcesz wyróżnić tylko absolutnie najświeższe produkty lub masz ograniczoną przestrzeń.
-   **Zalecana wartość:** Zacznij od `8` lub `12`. Dostosuj w zależności od układu Twojego motywu i liczby produktów, które zazwyczaj dodajesz.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli prowadzisz sklep z modą i dodajesz 20 nowych produktów tygodniowo, ustawienie tej wartości na `12` zapewnia, że dobry wybór jest zawsze widoczny. Jeśli sprzedajesz produkty o wysokiej wartości, niszowe i dodajesz tylko 2-3 nowe produkty miesięcznie, `4` może być wystarczające, aby uniknąć pustych miejsc.

#### **Klasy listy produktów**
-   **Co robi to ustawienie:** To zaawansowane ustawienie pozwala dodać niestandardowe klasy CSS do kontenera, który zawiera listę nowych produktów. Jest to używane głównie do celów stylizacji, często w celu bezproblemowej integracji z projektem Twojego konkretnego motywu PrestaShop.
-   **Efekt zmiany tego ustawienia:**
    -   *Po dodaniu klas (np. `product-grid-container my-custom-style`):* CSS Twojego motywu lub Twój niestandardowy CSS może następnie celować w te klasy, aby zastosować specyficzną stylizację (np. zmienić układ kolumn, odstępy, rozmiary czcionek, kolory) do listy nowych produktów.
    -   *Pozostawione puste:* Moduł użyje swojej domyślnej stylizacji lub odziedziczy style z ogólnej listy produktów Twojego motywu.
-   **Zalecana wartość:** Pozostaw puste, chyba że Ty lub Twój programista internetowy potrzebujecie zastosować specyficzną niestandardową stylizację do listy produktów. Jeśli nie masz pewności, nie zmieniaj tego ustawienia.
-   **Scenariusz / przykład dla sprzedawcy:** Twój motyw wyświetla siatki produktów z 3 kolumnami, ale chcesz, aby zakładka "Nowe produkty" wyświetlała 4 kolumny. Twój programista internetowy może powiedzieć Ci, abyś dodał klasę taką jak `col-lg-3` (jeśli Twój motyw używa klas siatki Bootstrap) tutaj, a następnie dodał niestandardowy CSS, aby to działało.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|---|
| Strona konfiguracji modułu | **Liczba produktów do wyświetlenia** | `8` lub `12` | Określa, ile najnowszych produktów zostanie wyświetlonych w zakładce "Nowe produkty" na stronie głównej. Wyższa liczba zwiększa widoczność, niższa zapewnia czystszy wygląd. |
| Strona konfiguracji modułu | **Klasy listy produktów** | Puste | Umożliwia dodanie niestandardowych klas CSS do kontenera listy produktów w celu zaawansowanej stylizacji i integracji z motywem. Zostaw puste, chyba że masz specyficzne wymagania dotyczące stylizacji. |
