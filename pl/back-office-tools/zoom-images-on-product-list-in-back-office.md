---
title: "Powiększanie obrazów na liście produktów w panelu administracyjnym - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Powiększanie obrazów na liście produktów w panelu administracyjnym” od MyPresta.eu."
sidebar:
  label: "Powiększanie obrazów na liście produktów w panelu administracyjnym - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Zoom images on product list in back office na MyPresta.eu](https://mypresta.eu/modules/administration-tools/zoom-images-on-product-list-in-back-office.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/zoom-images-on-product-list-in-back-office/)
>
> ---


# Powiększanie obrazów na liście produktów w panelu administracyjnym

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok nazwy modułu. Zostaniesz przeniesiony do jego głównego ekranu konfiguracji.

Ten moduł ma bardzo prostą konfigurację, zazwyczaj składającą się z jednego przełącznika do włączania lub wyłączania jego funkcjonalności.

- **Włącz powiększanie na liście produktów:**
  - **Co robi to ustawienie:** Jest to główny przełącznik modułu. Kontroluje, czy funkcja powiększania obrazu jest aktywna, czy nieaktywna na liście produktów w Panelu administracyjnym.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone (TAK):* Gdy przejdziesz do **Katalog > Produkty** w Panelu administracyjnym, najechanie kursorem na dowolną miniaturę zdjęcia produktu na liście wyświetli większą, powiększoną wersję tego zdjęcia.
    - *Gdy wyłączone (NIE):* Funkcja powiększania zostanie wyłączona. Najechanie kursorem na zdjęcia produktów nie będzie miało żadnego specjalnego efektu, a zobaczysz standardowe małe miniatury.
  - **Zalecana wartość:** TAK
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz używać wygodnej funkcji powiększania do szybkiego sprawdzania zdjęć produktów, upewnij się, że jest ustawiona na „TAK”. Jeśli stwierdzisz, że koliduje z inną personalizacją Panelu administracyjnego lub po prostu wolisz jej nie używać, ustaw ją na „NIE”.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz powiększanie na liście produktów | TAK | Aktywuje lub dezaktywuje funkcję powiększania obrazu na liście produktów w Panelu administracyjnym. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Włączyłem moduł, ale powiększanie nie działa na mojej liście produktów. Co powinienem zrobić?**
O:

1. **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami pamięć podręczna PrestaShop może uniemożliwić ładowanie nowego JavaScriptu.
2. **Sprawdź konsolę przeglądarki:** Otwórz narzędzia deweloperskie przeglądarki (zazwyczaj F12) i poszukaj błędów w zakładce „Konsola”. Może to wskazywać na konflikt z innym modułem lub motywem.
3. **Konflikty modułów:** Tymczasowo wyłącz inne moduły, które modyfikują listę produktów w Panelu administracyjnym (jeśli takie istnieją), aby sprawdzić, czy występuje konflikt.
4. **Nadpisania motywu:** Jeśli używasz mocno dostosowanego motywu Panelu administracyjnego, może on nadpisywać standardową strukturę listy produktów, uniemożliwiając modułowi wstrzyknięcie jego JavaScriptu. Skontaktuj się z deweloperem motywu lub wsparciem MyPresta.eu.

**P: Powiększone zdjęcie pojawia się, ale wygląda na rozmazane lub pikselowane.**
O: Moduł wyświetla obraz, który PrestaShop dostarcza dla listy produktów. Jeśli oryginalny obraz przesłany dla tego produktu ma niską rozdzielczość, powiększona wersja również będzie wyglądać na rozmazaną. Upewnij się, że przesyłasz obrazy produktów w wysokiej rozdzielczości.

**P: Czy ten moduł spowalnia mój Panel administracyjny?**
O: Nie, moduł jest bardzo lekki. Ładuje tylko małą bibliotekę JavaScript i stosuje ją, gdy najedziesz kursorem na obraz. Nie wykonuje ciężkich operacji ani zapytań do bazy danych, które wpłynęłyby na wydajność.

**P: Czy mogę dostosować rozmiar pola powiększenia lub poziom powiększenia?**
O: Moduł używa standardowego narzędzia „elevateZoom”, które ma pewne domyślne zachowania. Chociaż sam moduł nie oferuje opcji konfiguracji dla tych konkretnych aspektów wizualnych, deweloper mógłby potencjalnie zmodyfikować plik `zplb.js`, aby dostosować te parametry. Wymagałoby to niestandardowego kodowania.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Powiększanie obrazów na liście produktów w panelu administracyjnym” (`zplb`) to prosty, ale skuteczny moduł PrestaShop, zaprojektowany przede wszystkim do wstrzykiwania JavaScriptu po stronie klienta do listy produktów w Panelu administracyjnym. Wykorzystuje system hooków PrestaShop do ładowania swoich zasobów i opiera się na zewnętrznej bibliotece JavaScript (elevateZoom, choć zintegrowanej z `zplb.js`), aby zapewnić funkcję powiększania. Nie wprowadza nowych tabel baz danych ani złożonej logiki biznesowej.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front Office**: Brak. Ten moduł jest przeznaczony wyłącznie dla Panelu administracyjnego.
- **Kontrolery Admin Panelu administracyjnego**: Brak. Konfiguracja modułu jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy i modele rdzenia (`classes/`)

- Brak. Moduł nie definiuje żadnych niestandardowych klas ani instancji `ObjectModel`. Cała logika zawarta jest w głównym pliku `zplb/index.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

- `zplb/lib/js/zplb.js`
  - **Zakres:** Panel administracyjny. Ten skrypt jest ładowany specjalnie na stronie listy produktów w Panelu administracyjnym.
  - **Funkcjonalność:** Ten plik zawiera podstawową logikę JavaScript dla funkcji powiększania. Prawdopodobnie zawiera lub integruje bibliotekę „elevateZoom”. Celuje w elementy obrazów produktów w tabeli listy produktów w Panelu administracyjnym (np. `img.img-thumbnail` lub podobne selektory używane przez listę produktów PrestaShop). Wiąże zdarzenia najechania myszą/hover z tymi obrazami i inicjuje funkcję powiększania, tworząc powiększony widok.

### 4.5 Arkusze stylów CSS (`views/css/`)

- Brak. Moduł nie zawiera żadnych niestandardowych plików CSS. Stylizacja pola powiększenia jest zazwyczaj obsługiwana przez samą bibliotekę JavaScript, często wstrzykując style inline lub używając minimalnej domyślnej stylizacji, która dobrze integruje się z Panelem administracyjnym PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- Brak. Moduł nie używa żadnych plików `.tpl`. Jego funkcjonalność jest wstrzykiwana bezpośrednio za pomocą JavaScriptu do istniejącej struktury HTML listy produktów w Panelu administracyjnym.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:
  - Moduł nie tworzy żadnych niestandardowych tabel baz danych.
  - Przechowuje swoją konfigurację (np. ustawienie „Włącz powiększanie”) w tabeli `ps_configuration`, używając klucza takiego jak `ZPLB_ENABLED`.
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayBackOfficeHeader` | Wykonywany w sekcji `<head>` każdej strony Panelu administracyjnego. | Służy do warunkowego ładowania skryptu `zplb.js` tylko wtedy, gdy bieżąca strona Panelu administracyjnego to lista produktów (`AdminProducts`). Zapewnia to, że skrypt nie jest ładowany niepotrzebnie na innych stronach administracyjnych, optymalizując wydajność. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Powiększanie obrazów na liście produktów w panelu administracyjnym”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
