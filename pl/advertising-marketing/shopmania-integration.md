---
title: "Integracja z Shopmania - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Integracja z Shopmania” od MyPresta.eu."
sidebar:
  label: "Integracja z Shopmania"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Shopmania Integration na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/shopmania-integration.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/shopmania-integration/)
>
> ---


# Integracja z Shopmania

## 1. Wymagania i kompatybilność
- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do ogólnego działania PrestaShop, ale ten moduł ma minimalne specyficzne wymagania poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)
Po instalacji kliknij „Konfiguruj” obok modułu „Integracja z Shopmania” w Menedżerze modułów. Spowoduje to przejście do głównej strony konfiguracji.

Moduł Integracja z Shopmania został zaprojektowany tak, aby był bardzo prosty, często wymagając minimalnej konfiguracji, ponieważ koncentruje się głównie na generowaniu pliku danych produktów.

| Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|
| **URL pliku danych ShopMania** | Generowany automatycznie | Jest to bezpośredni link do pliku danych produktów generowanego przez Twój moduł. Będziesz musiał skopiować ten URL i podać go ShopMania podczas konfigurowania konta sprzedawcy. Ten URL będzie używany przez ShopMania do regularnego pobierania danych Twoich produktów. |

**Co robi to ustawienie:**
Ta sekcja wyświetla URL, którego ShopMania użyje do uzyskania dostępu do Twojego pliku danych produktów. Ten plik danych zawiera wszystkie niezbędne informacje o Twoich produktach (nazwa, opis, cena, zdjęcia, dostępność itp.) w formacie, który ShopMania może zrozumieć i wyświetlić na swojej platformie.

**Wpływ zmiany tego ustawienia:**
Nie możesz bezpośrednio zmienić tego URL-a. Jest on generowany automatycznie przez moduł na podstawie domeny Twojego sklepu i wewnętrznej logiki modułu.

**Zalecana wartość:**
Skopiuj ten URL dokładnie tak, jak się pojawia. Nie modyfikuj go.

**Scenariusz / przykład dla sprzedawcy:**
Po zainstalowaniu i skonfigurowaniu modułu zalogujesz się na swoje konto sprzedawcy ShopMania (lub utworzysz nowe). ShopMania poprosi Cię o „URL pliku danych produktów” lub „URL pliku danych”. Następnie wkleisz URL podany na tej stronie konfiguracji w odpowiednie pole na stronie ShopMania. ShopMania będzie następnie okresowo odwiedzać ten URL, aby aktualizować Twoje oferty produktów na swojej platformie.

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moje produkty nie pojawiają się na ShopMania. Co powinienem zrobić?**
O:
1.  **Sprawdź URL pliku danych:** Upewnij się, że poprawnie skopiowałeś i wkleiłeś dokładny URL pliku danych ze strony konfiguracji modułu do ustawień konta sprzedawcy ShopMania.
2.  **Czas przetwarzania ShopMania:** Przetworzenie pliku danych przez ShopMania po raz pierwszy może zająć trochę czasu (od kilku godzin do kilku dni). Bądź cierpliwy.
3.  **Dostępność pliku danych:** Spróbuj otworzyć URL pliku danych w przeglądarce internetowej. Czy się ładuje? Czy wyświetla dane produktów? Jeśli wyświetla błąd lub pustą stronę, może to być problem po stronie serwera lub problem z procesem generowania modułu. Skontaktuj się z pomocą techniczną MyPresta.eu.
4.  **Widoczność produktu:** Upewnij się, że Twoje produkty są aktywne, dostępne w magazynie i widoczne w Twoim sklepie PrestaShop. Produkty, które są wyłączone lub niedostępne, mogą nie być uwzględnione w pliku danych.

**P: Czy ten moduł automatycznie aktualizuje ceny i stany magazynowe na ShopMania?**
O: Tak, plik danych generowany przez ten moduł będzie odzwierciedlał aktualne ceny i stany magazynowe z Twojego sklepu PrestaShop. ShopMania będzie okresowo ponownie pobierać ten plik danych, aby utrzymać aktualność swoich ofert. Częstotliwość aktualizacji zależy od harmonogramu pobierania ShopMania, który możesz być w stanie skonfigurować na swoim koncie sprzedawcy ShopMania.

**P: Czy mogę wybrać, które produkty są uwzględniane w pliku danych?**
O: Podstawowa wersja tego modułu zazwyczaj obejmuje wszystkie aktywne i widoczne produkty. Jeśli potrzebujesz zaawansowanego filtrowania (np. wykluczania konkretnych kategorii lub produktów), wymagałoby to niestandardowego rozwoju lub bardziej zaawansowanego modułu do zarządzania plikami danych. Moduł „Integracja z Shopmania” koncentruje się na prostym, pełnym katalogu integracji.

**P: Widzę błąd podczas próby konfiguracji modułu.**
O:
1.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** w panelu administracyjnym PrestaShop i kliknij „Wyczyść pamięć podręczną”. Czasami stare pliki pamięci podręcznej mogą zakłócać konfigurację modułu.
2.  **Sprawdź logi błędów serwera:** Jeśli problem nadal występuje, sprawdź logi błędów PHP serwera. Te logi mogą dostarczyć szczegółowych informacji technicznych o tym, co poszło nie tak. Może być konieczne skontaktowanie się z dostawcą hostingu lub deweloperem w tej sprawie.
3.  **Skontaktuj się z pomocą techniczną:** Jeśli nadal masz problemy, zbierz wszelkie komunikaty o błędach lub zrzuty ekranu i skontaktuj się z pomocą techniczną MyPresta.eu w celu uzyskania pomocy.

**P: Co jeśli mój niestandardowy motyw powoduje problemy z wyświetlaniem (chociaż ten moduł nie ma wyświetlania w front-office)?**
O: Ponieważ ten moduł nie ma wyświetlania w front-office, jest bardzo mało prawdopodobne, aby powodował jakiekolwiek problemy wizualne z Twoim niestandardowym motywem. Jego działanie jest czysto backendowe, generując plik danych.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)
Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury
Moduł `Integracja z Shopmania` to prosty, jednoplikowy moduł PrestaShop zaprojektowany do generowania pliku danych produktów XML kompatybilnego z platformą ShopMania. Przestrzega standardowej struktury modułu PrestaShop, wykorzystując głównie metody `install()` i `uninstall()` do konfiguracji oraz metodę `getContent()` do konfiguracji w panelu administracyjnym, która w tym przypadku po prostu wyświetla wygenerowany URL pliku danych. Główna logika znajduje się w głównym pliku modułu, odpowiedzialnym za dynamiczne generowanie pliku danych XML, gdy uzyskuje się dostęp do określonego URL pliku danych. Nie używa niestandardowych kontrolerów, modeli ani dedykowanych plików szablonów do swojej podstawowej funkcjonalności, opierając się na bezpośrednim wyjściu dla pliku danych.

### 4.2 Kontrolery (`controllers/`)
-   **Kontrolery Front-Office**: Brak. Plik danych produktów jest generowany bezpośrednio przez główny plik modułu, gdy uzyskuje się dostęp do jego konkretnego URL, a nie za pośrednictwem dedykowanego `ModuleFrontController`.
-   **Kontrolery Panelu Administracyjnego**: Brak. Cała konfiguracja (wyświetlanie URL pliku danych) jest obsługiwana w metodzie `getContent()` głównej klasy modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)
-   W tym module nie ma niestandardowych klas ani definicji `ObjectModel`. Cała logika zawarta jest w klasie `ShopmaniaIntegration` w głównym pliku modułu.

### 4.4 Zasoby JavaScript (`views/js/`)
-   W tym module nie ma żadnych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)
-   W tym module nie ma żadnych plików CSS.

### 4.6 Struktura szablonów Smarty (`views/templates/`)
-   W tym module nie są używane żadne niestandardowe pliki szablonów Smarty (`.tpl`). Metoda `getContent()` bezpośrednio wyprowadza kod HTML dla strony konfiguracji, a plik danych produktów jest generowany jako czysty XML.

### 4.7 Schemat bazy danych i mapa hooków
-   **Tabele bazy danych**: Ten moduł nie tworzy żadnych niestandardowych tabel bazy danych. Przechowuje swoją konfigurację (jeśli byłaby potrzebna poza URL pliku danych) w standardowej tabeli `ps_configuration`, chociaż dla tego modułu URL pliku danych jest generowany dynamicznie i nie jest przechowywany jako wartość konfiguracyjna.
-   **Tabela zarejestrowanych hooków**:
    Ten moduł nie rejestruje jawnie żadnych hooków w metodzie `install()` do wyświetlania lub działania w front-office. Jego główną funkcją jest odpowiadanie na bezpośrednie żądanie URL dla pliku danych XML. Chociaż opis funkcji wspomina o „Hookach Front-Office: Nagłówek, Kolumny, Produkt lub Stopka”, jest to prawdopodobnie ogólny opis dla modułów, które *mogłyby* ich używać, ale ten konkretny moduł nie implementuje żadnych wizualnych komponentów front-office. Jego integracja opiera się wyłącznie na pliku danych.

| Nazwa hooka | Czas wykonania | Cel techniczny |
|---|---|---|
| `displayBackOfficeHeader` | Wykonywany podczas renderowania nagłówka Panelu administracyjnego. | Służy do dołączania specyficznych dla modułu CSS/JS dla strony konfiguracji (chociaż ten moduł ich nie używa). |
| `displayHeader` | Wykonywany w sekcji `<head>` stron front-office. | (Nie używany przez ten moduł do wizualnego wyjścia, ale mógłby być używany do meta tagów lub skryptów, jeśli byłoby to potrzebne). |
| `displayRightColumn` | Wykonywany w prawej kolumnie stron front-office. | (Nie używany przez ten moduł). |
| `displayLeftColumn` | Wykonywany w lewej kolumnie stron front-office. | (Nie używany przez ten moduł). |
| `displayProductAdditionalInfo` | Wykonywany na stronie produktu. | (Nie używany przez ten moduł). |
| `displayFooter` | Wykonywany w stopce stron front-office. | (Nie używany przez ten moduł). |

Główna funkcjonalność modułu (generowanie pliku danych XML) jest wyzwalana, gdy uzyskuje się dostęp do określonego URL pliku danych (np. `twojasklep.com/modules/shopmania-integration/shopmania-feed.php` lub podobnego, w zależności od routingu PrestaShop). Nie jest to standardowy hook PrestaShop, ale bezpośrednie żądanie HTTP do punktu końcowego specyficznego dla modułu.

## 5. Oficjalne wsparcie i aktualizacje
W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i wszelkiej dalszej pomocy z modułem Integracja z Shopmania, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w rozwiązywaniu problemów związanych z modułem i zapewnić płynne działanie integracji.
