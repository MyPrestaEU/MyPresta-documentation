---
title: "Wyklucz rabat grupowy z produktów z ceną specyficzną - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Wyklucz rabat grupowy z produktów z ceną specyficzną” od MyPresta.eu."
sidebar:
  label: "Wyklucz rabat grupowy z produktów z ceną specyficzną - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Exclude group discount from products with specific price na MyPresta.eu](https://mypresta.eu/modules/ordering-process/exclude-group-discount-from-products-with-specific-price.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/exclude-group-discount-from-products-with-specific-price/)
>
> ---


# Wyklucz rabat grupowy z produktów z ceną specyficzną

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Nie są wymagane żadne nietypowe konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji przejdź do **Moduły > Menedżer modułów**, znajdź „Wyklucz rabat grupowy z produktów z ceną specyficzną” i kliknij **Konfiguruj**. Zobaczysz główny ekran konfiguracji.

#### Ustawienie: Wyłącz rabat grupowy dla produktów z cenami specyficznymi

- **Co robi to ustawienie:** Jest to główna kontrola funkcjonalności modułu. Określa, czy moduł powinien aktywnie zapobiegać stosowaniu rabatów grupowych do produktów, które już mają ceny specyficzne.
- **Efekt zmiany tego ustawienia:**
  - **Gdy ustawione na „Włączone”:** Jeśli produkt ma cenę specyficzną (np. specjalną cenę promocyjną, którą ustawiłeś), a klient z grupy, która normalnie otrzymuje rabat (np. „Klienci VIP” otrzymują 10% zniżki), przegląda lub kupuje ten produkt, 10% rabat grupowy *nie* zostanie zastosowany. Klient zapłaci ustaloną przez Ciebie cenę specyficzną. Jest to zamierzone zachowanie modułu.
  - **Gdy ustawione na „Wyłączone”:** Moduł będzie nieaktywny. Przywrócone zostanie domyślne zachowanie PrestaShop. Oznacza to, że jeśli produkt ma cenę specyficzną, a klient z grupy objętej rabatem przegląda lub kupuje go, zastosowane zostaną *zarówno* cena specyficzna, jak i rabat grupowy, co potencjalnie prowadzi do znacznie niższej ceny końcowej niż zamierzono.
- **Zalecana wartość:** **Włączone**. Jest to cel modułu, aby zapobiec niezamierzonemu kumulowaniu się rabatów.
- **Scenariusz/przykład dla sprzedawcy:** Masz „Letnią Wyprzedaż”, gdzie konkretna koszulka kosztuje 15 $ (zamiast 25 $). Masz również grupę klientów „Hurtownicy”, którzy otrzymują 20% zniżki na wszystkie zamówienia.
  - Jeśli to ustawienie jest **Włączone**: Klient hurtowy kupuje koszulkę. Płaci 15 $. 20% rabat hurtowy jest ignorowany dla tego konkretnego produktu.
  - Jeśli to ustawienie jest **Wyłączone**: Klient hurtowy kupuje koszulkę. PrestaShop najpierw stosuje cenę specyficzną (15 $), a następnie stosuje 20% rabat hurtowy do 15 $, co daje ostateczną cenę 12 $. Może to być niższe niż Twoja pożądana marża zysku.

#### Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Wyłącz rabat grupowy dla produktów z cenami specyficznymi | Włączone | Kontroluje, czy rabaty grupowe są wykluczane z kumulowania się z cenami specyficznymi. **Włączone** zapobiega kumulowaniu, zachowując marże zysku. **Wyłączone** pozwala na kumulowanie, potencjalnie prowadząc do niższych cen. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Włączyłem moduł, ale rabaty grupowe nadal są stosowane do moich cen specyficznych. Co jest nie tak?**
O:

1.  **Wyczyść pamięć podręczną:** Zawsze wyczyść pamięć podręczną PrestaShop po wprowadzeniu zmian w konfiguracji. Przejdź do **Zaawansowane > Wydajność**, a następnie kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu.
2.  **Kolejność modułów:** W rzadkich przypadkach inny moduł może nadpisywać obliczenia cen. Jeśli masz inne moduły cenowe lub rabatowe, spróbuj tymczasowo wyłączyć je jeden po drugim, aby sprawdzić, czy występuje konflikt.
3.  **Konfiguracja ceny specyficznej:** Sprawdź dwukrotnie, czy Twoje „ceny specyficzne” są poprawnie skonfigurowane dla danych produktów. Przejdź do strony edycji produktu, następnie do zakładki „Ceny” i upewnij się, że cena specyficzna jest aktywna i poprawnie zastosowana.
4.  **Konfiguracja rabatu grupowego:** Sprawdź, czy rabat dla grupy klientów jest poprawnie ustawiony w **Parametry sklepu > Ustawienia klienta > Grupy**.

**P: Czy ten moduł wpłynie na moje regularne reguły koszyka lub kody kuponów?**
O: Nie, ten moduł dotyczy konkretnie „rabatów grupowych” (rabatów stosowanych automatycznie na podstawie przypisanej klientowi grupy) i ich interakcji z „cenami specyficznymi” (ręczne nadpisywanie cen dla produktu). Nie koliduje z regułami koszyka PrestaShop, kodami kuponów ani innymi mechanizmami promocyjnymi, chyba że te mechanizmy same opierają się na cenach specyficznych lub rabatach grupowych.

**P: Czy ten moduł spowalnia mój sklep?**
O: Nie, moduł jest bardzo lekki. Działa poprzez nadpisywanie podstawowej klasy PrestaShop (`Product.php`) w celu modyfikacji sposobu obliczania cen. Jest to wysoce zoptymalizowany proces i nie powinien wprowadzać żadnego zauważalnego pogorszenia wydajności.

**P: Co jeśli chcę, aby rabaty grupowe *czasami* były stosowane do cen specyficznych?**
O: Ten moduł oferuje podejście „wszystko albo nic”: albo rabaty grupowe są wykluczone ze *wszystkich* produktów z cenami specyficznymi, albo nie. Jeśli potrzebujesz bardziej szczegółowej kontroli (np. wyklucz dla Produktu A, ale zezwól dla Produktu B, oba z cenami specyficznymi), ten moduł sam w sobie tego nie osiągnie. Musiałbyś ręcznie zarządzać cenami specyficznymi i rabatami grupowymi lub rozważyć bardziej zaawansowany moduł cenowy. W przypadku tego modułu zaleca się jego włączenie, aby zapobiec niezamierzonemu kumulowaniu się.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł `Exclude group discount from products with specific price` implementuje swoją podstawową funkcjonalność poprzez nadpisanie klasy `Product`. Jest to powszechny i skuteczny wzorzec rozwoju PrestaShop do modyfikowania podstawowych zachowań bez bezpośredniej zmiany plików rdzenia. Poprzez nadpisanie `Product::getPriceStatic()`, moduł przechwytuje logikę obliczania cen, aby zapobiec stosowaniu rabatów specyficznych dla grup, gdy produkt ma aktywną cenę specyficzną.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**: Brak. Cała logika front-office jest obsługiwana poprzez nadpisanie klasy `Product`.
- **Kontrolery Back-Office Admin**: Brak. Konfiguracja modułu jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy i modele rdzenia (`classes/`)

Główna funkcjonalność modułu znajduje się w jego nadpisanej klasie.

- **Ścieżka pliku**: `exgdis/override/classes/Product.php`
- **Nazwa klasy**: `Product` (nadpisuje podstawową klasę `Product`)
- **Klasa nadrzędna**: `ProductCore`
- **Odpowiedzialność**: To nadpisanie modyfikuje metodę `getPriceStatic()`, która jest kluczowa dla sposobu, w jaki PrestaShop oblicza ceny produktów w całym front office (strony produktów, koszyk, kasa) i back office.
  - **Kluczowa logika**: Wewnątrz nadpisanej metody `getPriceStatic()` moduł sprawdza, czy jego ustawienie konfiguracyjne `exgdis_groups` (które odpowiada „Wyłącz rabat grupowy dla produktów z cenami specyficznymi”) jest włączone.
  - Jeśli jest włączone i jeśli aktualnie wyceniany produkt ma aktywną cenę specyficzną, moduł zapewnia, że parametr `$use_group_reduction` przekazany do oryginalnej metody `ProductCore::getPriceStatic()` jest ustawiony na `false`. Skutecznie informuje to PrestaShop, aby *nie* stosował żadnych rabatów specyficznych dla grup dla tego konkretnego obliczenia ceny.
  - Plik `index.php` w `override/classes/` jest standardowym pustym plikiem, aby zapobiec listowaniu katalogów.

### 4.4 Zasoby JavaScript (`views/js/`)

- Brak. Moduł nie posiada komponentów JavaScript dla front-endu ani back-endu.

### 4.5 Arkusze stylów CSS (`views/css/`)

- Brak. Moduł nie posiada niestandardowych stylów CSS.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- Brak. Konfiguracja modułu jest renderowana bezpośrednio za pomocą `getContent()` w głównym pliku modułu, a jego funkcjonalność opiera się wyłącznie na logice, a nie na wyświetlaniu.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**: Moduł nie tworzy żadnych niestandardowych tabel bazy danych. Przechowuje swoją konfigurację w tabeli `ps_configuration`.

  - Wpis w `ps_configuration`: `exgdis_groups` (przechowuje status włączony/wyłączony głównego ustawienia).
- **Tabela zarejestrowanych hooków**: Moduł nie rejestruje jawnie żadnych hooków w tabeli `ps_hook_module`. Jego funkcjonalność jest zaimplementowana poprzez nadpisanie klasy, która jest ładowana przez mechanizm nadpisywania PrestaShop.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `override/classes/Product.php` | Podczas wywołań `Product::getPriceStatic()` | Przechwytuje obliczanie ceny, aby zapobiec rabatom grupowym na produktach z cenami specyficznymi. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Wyklucz rabat grupowy z produktów z ceną specyficzną”, zapoznaj się ze swoim kontem klienta MyPresta.eu. Możesz pobrać najnowsze wersje i uzyskać dostęp do zasobów wsparcia bezpośrednio z [MyPresta.eu](https://mypresta.eu).
"""
