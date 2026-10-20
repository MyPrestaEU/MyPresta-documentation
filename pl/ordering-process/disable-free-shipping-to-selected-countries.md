---
title: "Wyłącz darmową wysyłkę do wybranych krajów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Wyłącz darmową wysyłkę do wybranych krajów” od MyPresta.eu."
sidebar:
  label: "Wyłącz darmową wysyłkę do wybranych krajów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Disable free shipping to selected countries na MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-free-shipping-to-selected-countries.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/disable-free-shipping-to-selected-countries/)
>
> ---


# Wyłącz darmową wysyłkę do wybranych krajów

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny i jedyny ekran konfiguracji modułu „Wyłącz darmową wysyłkę do wybranych krajów”. Znajdziesz go, przechodząc do **Moduły > Menedżer modułów**, wyszukując „Wyłącz darmową wysyłkę do wybranych krajów” i klikając „Konfiguruj”.

#### Wyklucz darmową wysyłkę z krajów:

- **Co robi to ustawienie:** Jest to kluczowe ustawienie modułu. Pozwala wybrać jeden lub więcej krajów, do których darmowa wysyłka *nie* powinna być oferowana, niezależnie od innych zasad darmowej wysyłki, które możesz mieć (np. darmowa wysyłka powyżej określonej kwoty zamówienia).
- **Efekt zmiany tego ustawienia:**
  - *Gdy kraje są wybrane:* Jeśli adres dostawy klienta znajduje się w którymkolwiek z wybranych krajów, opcja „Darmowa wysyłka” zostanie usunięta z listy dostępnych przewoźników podczas realizacji zamówienia. Zobaczy on tylko płatne opcje wysyłki.
  - *Gdy nie wybrano żadnych krajów:* Moduł nie będzie miał żadnego wpływu, a darmowa wysyłka będzie oferowana do wszystkich krajów zgodnie z Twoimi standardowymi ustawieniami PrestaShop.
- **Zalecana wartość:** Wybierz tylko te kraje, w których oferowanie darmowej wysyłki jest rzeczywiście nieopłacalne lub problematyczne dla Twojej firmy.
- **Scenariusz / przykład sprzedawcy:** Wysyłasz międzynarodowo, ale wysyłka do Australii i Nowej Zelandii jest znacznie droższa ze względu na odległość i cło. Wybrałbyś „Australia” i „Nowa Zelandia” z tej listy. Teraz klienci z tych krajów zawsze będą obciążani kosztami wysyłki, nawet jeśli wartość ich zamówienia kwalifikuje się do darmowej wysyłki w innych regionach, takich jak UE czy USA.

#### Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Wyklucz darmową wysyłkę z krajów: | Brak wybranych | Wybierz kraje, do których darmowa wysyłka NIE powinna być oferowana. Jeśli adres dostawy klienta znajduje się w wybranym kraju, darmowa wysyłka będzie niedostępna dla jego zamówienia. |

## 3. Rozwiązywanie problemów sprzedawcy i często zadawane pytania (FAQ)

**P: Skonfigurowałem moduł, ale darmowa wysyłka nadal jest wyświetlana dla wybranego kraju. Co jest nie tak?**
O:

1. **Wyczyść pamięć podręczną:** Zawsze czyść pamięć podręczną PrestaShop po wprowadzeniu zmian w konfiguracji. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu.
2. **Testuj z nowym koszykiem:** Upewnij się, że testujesz z nowym koszykiem i adresem dostawy ustawionym na wykluczony kraj. Czasami pamięć podręczna przeglądarki lub dane sesji mogą zakłócać działanie.
3. **Sprawdź ustawienia przewoźnika:** Zweryfikuj, czy Twój przewoźnik oferujący darmową wysyłkę (lub przewoźnik oferujący darmową wysyłkę) jest poprawnie skonfigurowany w **Wysyłka > Przewoźnicy**. Upewnij się, że jest aktywny i ma włączoną opcję „Darmowa wysyłka”. Ten moduł *wyłącza* opcję darmowej wysyłki, nie tworzy nowych zasad wysyłki.
4. **Kolejność modułów:** W rzadkich przypadkach, jeśli masz wiele modułów związanych z wysyłką, może wystąpić konflikt. Spróbuj tymczasowo wyłączyć inne moduły wysyłki, aby wyizolować problem.

**P: Czy ten moduł wpływa na inne koszty wysyłki?**
O: Nie, ten moduł wpływa *tylko* na dostępność opcji „Darmowa wysyłka”. Nie modyfikuje ani nie usuwa żadnych płatnych opcji wysyłki ani ich kosztów. Jeśli darmowa wysyłka jest wyłączona dla danego kraju, klientom zostaną po prostu przedstawione standardowe płatne opcje wysyłki dostępne dla ich koszyka i miejsca docelowego.

**P: Czy mogę wyłączyć darmową wysyłkę dla konkretnych produktów lub kategorii zamiast krajów?**
O: Nie, ten moduł jest zaprojektowany specjalnie do wyłączania darmowej wysyłki na podstawie *kraju dostawy*. Nie oferuje opcji wykluczania darmowej wysyłki na podstawie produktu, kategorii lub grupy klientów. Jeśli potrzebujesz takiej funkcjonalności, będziesz potrzebować innego, bardziej zaawansowanego modułu zasad wysyłki.

**P: Co jeśli chcę oferować darmową wysyłkę do kraju dla zamówień powyżej określonej kwoty, ale wyłączyć ją dla niższych kwot?**
O: Ten moduł wyłącza *wszystkie* darmowe wysyłki dla wybranych krajów. Jeśli chcesz mieć warunkową darmową wysyłkę (np. darmowa wysyłka powyżej X $), powinieneś skonfigurować to bezpośrednio w ustawieniach przewoźników PrestaShop (Wysyłka > Przewoźnicy). Ten moduł nadpisałby wtedy to ustawienie dla wykluczonych krajów, czyniąc darmową wysyłkę niedostępną przy *jakiejkolwiek* kwocie dla tych konkretnych miejsc docelowych.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Wyłącz darmową wysyłkę do wybranych krajów” działa poprzez nadpisywanie podstawowych klas PrestaShop związanych z zachowaniem przewoźnika i koszyka. W szczególności modyfikuje logikę, która określa, czy przewoźnik oferuje darmową wysyłkę i czy koszyk kwalifikuje się do niej, na podstawie kraju dostawy klienta. Osiąga się to poprzez system nadpisywania PrestaShop, zapewniając, że logika modułu jest stosowana za każdym razem, gdy wykonywane są obliczenia wysyłki.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wykorzystuje żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Jego logika jest wstrzykiwana bezpośrednio do podstawowej funkcjonalności PrestaShop poprzez nadpisywanie klas.

### 4.3 Klasy podstawowe i modele (`classes/`)

Moduł implementuje swoją funkcjonalność głównie poprzez nadpisywanie klas, znajdujących się w katalogu `override/classes/` w folderze modułu.

- **`exfsc/override/classes/Carrier.php`**

  - **Nazwa klasy i klasa nadrzędna:** `Carrier` (nadpisuje podstawową klasę `Carrier`)
  - **Odpowiedzialność:** To nadpisanie modyfikuje metodę `isFree()` klasy `Carrier`. Kiedy PrestaShop sprawdza, czy dany przewoźnik oferuje darmową wysyłkę, to nadpisanie przechwytuje wywołanie. Sprawdza, czy kraj dostawy bieżącego koszyka znajduje się wśród krajów skonfigurowanych do wykluczenia darmowej wysyłki. Jeśli tak jest, a oryginalna metoda `isFree()` zwróciłaby `true`, to nadpisanie wymusza zwrócenie `false`, skutecznie wyłączając darmową wysyłkę dla tego przewoźnika dla wykluczonego kraju.
  - **Kluczowe metody:**
    - `isFree($cart)`: Zmodyfikowana w celu sprawdzenia konfiguracji `exfsc_country` i zwrócenia `false`, jeśli kraj dostawy koszyka jest wykluczony, a oryginalna metoda zwróciłaby `true`.
- **`exfsc/override/classes/Cart.php`**

  - **Nazwa klasy i klasa nadrzędna:** `Cart` (nadpisuje podstawową klasę `Cart`)
  - **Odpowiedzialność:** To nadpisanie modyfikuje metodę `getDeliveryOptionList()`. Metoda ta jest odpowiedzialna za generowanie listy dostępnych opcji dostawy (w tym przewoźników i ich usług) podczas realizacji zamówienia. Nadpisanie zapewnia, że jeśli przewoźnik jest oznaczony jako „darmowa wysyłka”, ale kraj dostawy jest wykluczony przez moduł, ten przewoźnik jest poprawnie prezentowany z jego *płatnymi* opcjami wysyłki, lub jeśli oferuje tylko darmową wysyłkę, jest całkowicie wykluczony.
  - **Kluczowe metody:**
    - `getDeliveryOptionList(Country $default_country = null, $product_list = null, $id_zone = null)`: Zmodyfikowana w celu zapewnienia, że przewoźnicy oznaczeni jako darmowi są poprawnie oceniani pod kątem listy wykluczeń krajów modułu.
- **`exfsc/override/classes/index.php`**

  - **Cel:** Jest to pusty plik `index.php`, zazwyczaj dołączany do katalogów w celu zapobiegania listowaniu katalogów po bezpośrednim dostępie przez przeglądarkę internetową, co zwiększa bezpieczeństwo. Nie ma on funkcjonalnego wpływu na logikę modułu.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł nie zawiera żadnych niestandardowych plików JavaScript. Cała funkcjonalność jest obsługiwana po stronie serwera.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł nie zawiera żadnych niestandardowych plików CSS. Cała funkcjonalność jest obsługiwana po stronie serwera.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł nie zawiera żadnych niestandardowych plików szablonów Smarty. Jego efekty są zintegrowane z istniejącymi szablonami realizacji zamówienia PrestaShop poprzez modyfikację danych przekazywanych do nich.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Moduł nie tworzy żadnych niestandardowych tabel SQL.
  - Ustawienia konfiguracji są przechowywane w tabeli `ps_configuration`.
    - `exfsc_country`: Przechowuje listę `id_country` oddzielonych przecinkami dla krajów, w których darmowa wysyłka jest wyłączona.
    - `mypresta_updates`, `update_`, `updatev_`: Wewnętrzne klucze konfiguracyjne używane przez moduły MyPresta.eu do sprawdzania aktualizacji.
    - `exfsc_visibility_cat`, `exfsc_visibility_products`: Te klucze są obecne w metodzie `getContent()`, ale nie są aktywnie używane przez podstawową logikę modułu, jak opisano w zestawie funkcji. Mogą być pozostałościami lub symbolami zastępczymi dla potencjalnych przyszłych funkcji.
- **Tabela zarejestrowanych hooków**:
  Moduł nie rejestruje jawnie żadnych hooków front-office. Jego funkcjonalność jest implementowana poprzez nadpisywanie klas, które są automatycznie wyzwalane przez podstawowe procesy PrestaShop podczas obliczania opcji wysyłki.
  Metoda `install()` modułu może rejestrować standardowe hooki back-office do zarządzania modułami (np. `displayBackOfficeHeader`), ale służą one celom administracyjnym i nie wpływają na zachowanie front-office.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „Wyłącz darmową wysyłkę do wybranych krajów”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnienie doskonałego funkcjonowania Twojego modułu w Twoim sklepie PrestaShop.
