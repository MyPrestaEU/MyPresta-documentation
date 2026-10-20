---
title: "Maksymalna dostępna ilość produktu do zakupu według daty - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Maksymalna dostępna ilość produktu do zakupu według daty” od MyPresta.eu."
sidebar:
  label: "Maksymalna dostępna ilość produktu do zakupu według daty"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Maximum available product quantity to purchase by date na MyPresta.eu](https://mypresta.eu/modules/ordering-process/maximum-available-product-quantity-to-purchase-by-date.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/maximum-available-product-quantity-to-purchase-by-date/)
>
> ---


# Maksymalna dostępna ilość produktu do zakupu według daty

## 1. Wymagania i kompatybilność
- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Wymagane są standardowe rozszerzenia PHP (cURL, JSON, OpenSSL), które są zazwyczaj dostępne w większości środowisk hostingowych kompatybilnych z PrestaShop.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel Administracyjny > Moduły > Konfiguruj)
Jest to główny ekran konfiguracji modułu, dostępny natychmiast po instalacji lub po kliknięciu „Konfiguruj” w Menedżerze modułów.

-   **Co robi to ustawienie:** Ten ekran zazwyczaj zawiera ogólne ustawienia modułu, takie jak włączanie/wyłączanie jego podstawowej funkcjonalności lub ustawianie globalnych preferencji.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy włączone:* Funkcje ograniczania ilości modułu będą aktywne w całym Twoim sklepie na podstawie zdefiniowanych przez Ciebie reguł.
    -   *Gdy wyłączone:* Moduł przestanie egzekwować jakiekolwiek limity ilościowe, a klienci będą mogli kupić dowolną dostępną ilość towaru.
-   **Zalecana wartość:** „TAK” (Włączone), aby aktywować podstawową funkcjonalność modułu.
-   **Scenariusz/przykład dla sprzedawcy:** Właśnie zainstalowałeś moduł i chcesz zacząć definiować limity. Pierwszym krokiem jest upewnienie się, że moduł jest aktywny na tym ekranie, zanim przejdziesz do definiowania konkretnych limitów produktów.

### 2.2 Dedykowany ekran administracyjny: Limit ilości zakupu produktu według daty (Panel Administracyjny > Katalog > Limit ilości zakupu produktu według daty)
Jest to główny ekran, na którym definiujesz i zarządzasz wszystkimi limitami ilości produktów na podstawie zakresów dat.

**Nazwa ekranu i lokalizacja w menu:**
Ten ekran znajdziesz, przechodząc do **Katalog > Limit ilości zakupu produktu według daty** w menu Panelu Administracyjnego PrestaShop.

**Dostępne akcje i ustawienia:**
Ten ekran przedstawia listę (siatkę) wszystkich istniejących limitów ilości, które ustawiłeś. Możesz dodawać nowe limity, edytować istniejące lub je usuwać.

#### **Kolumny tabeli listy:**
-   **ID:** Unikalny identyfikator dla każdej reguły limitu ilości.
-   **Produkt:** Nazwa produktu, do którego odnosi się limit.
-   **Data od:** Data i godzina rozpoczęcia obowiązywania limitu ilości.
-   **Data do:** Data i godzina wygaśnięcia limitu ilości.
-   **Ilość:** Maksymalna liczba jednostek produktu, które można kupić w określonym zakresie dat.
-   **Aktywny:** Przełącznik (Tak/Nie) do włączania lub wyłączania konkretnej reguły limitu bez jej usuwania.

#### **Dodawanie / Edytowanie reguły limitu ilości:**
Po kliknięciu „Dodaj nowy” lub edycji istniejącej reguły, zobaczysz formularz z następującymi polami:

-   **Limit ilości zakupu produktu według daty:** Jest to główny tytuł formularza.
-   **ID Produktu:**
    -   **Co robi to ustawienie:** To pole pozwala wybrać konkretny produkt, do którego będzie miał zastosowanie ten limit ilości. Zazwyczaj użyjesz paska wyszukiwania, aby znaleźć produkt po nazwie lub ID.
    -   **Efekt zmiany tego ustawienia:** Określa, którego produktu ilość zakupu zostanie ograniczona przez tę regułę.
    -   **Zalecana wartość:** Wybierz dokładnie ten produkt, który zamierzasz ograniczyć.
    -   **Scenariusz/przykład dla sprzedawcy:** Chcesz ograniczyć sprzedaż „Letniej Koszulki” do 50 sztuk. Wyszukujesz i wybierasz „Letnia Koszulka” tutaj.
-   **Data od:**
    -   **Co robi to ustawienie:** Definiuje dokładną datę i godzinę, od której ta reguła limitu ilości staje się aktywna.
    -   **Efekt zmiany tego ustawienia:** Limit będzie egzekwowany tylko dla zakupów dokonanych w tej dacie/godzinie lub po niej.
    -   **Zalecana wartość:** Ustaw precyzyjną datę i godzinę rozpoczęcia promocji lub ograniczenia.
    -   **Scenariusz/przykład dla sprzedawcy:** Chcesz, aby limit zaczął obowiązywać 1 sierpnia 2024 roku o godzinie 9:00.
-   **Data do:**
    -   **Co robi to ustawienie:** Definiuje dokładną datę i godzinę, o której ta reguła limitu ilości wygasa.
    -   **Efekt zmiany tego ustawienia:** Po tej dacie/godzinie limit nie będzie już egzekwowany, a klienci będą mogli kupić dowolną dostępną ilość towaru.
    -   **Zalecana wartość:** Ustaw precyzyjną datę i godzinę zakończenia promocji lub ograniczenia.
    -   **Scenariusz/przykład dla sprzedawcy:** Chcesz, aby limit zakończył się 7 sierpnia 2024 roku o godzinie 17:00.
-   **Ilość:**
    -   **Co robi to ustawienie:** Określa maksymalną liczbę jednostek wybranego produktu, które można kupić w zakresie „Data od” i „Data do”.
    -   **Efekt zmiany tego ustawienia:** Jest to faktycznie egzekwowany limit. Jeśli klient spróbuje dodać więcej niż tę ilość do koszyka w aktywnym zakresie dat, zostanie to uniemożliwione.
    -   **Zalecana wartość:** Konkretna maksymalna ilość, którą chcesz zezwolić.
    -   **Scenariusz/przykład dla sprzedawcy:** Chcesz ograniczyć zakupy do 5 sztuk na klienta w określonym okresie. Wpisujesz tutaj „5”.
-   **Aktywny (przełącznik Wł./Wył.):**
    -   **Co robi to ustawienie:** Przełącza status aktywności tej konkretnej reguły limitu ilości.
    -   **Efekt zmiany tego ustawienia:**
        -   *Wł.:* Reguła jest aktywna i będzie egzekwować limit ilości w określonym zakresie dat.
        -   *Wył.:* Reguła jest nieaktywna i nie będzie egzekwować żadnego limitu ilości, nawet jeśli jej zakres dat jest aktualny. Jest to przydatne do tymczasowego wstrzymywania reguły bez jej usuwania.
    -   **Zalecana wartość:** „Wł.” dla aktywnych reguł, „Wył.” dla reguł, które chcesz tymczasowo wyłączyć.
    -   **Scenariusz/przykład dla sprzedawcy:** Ustawiłeś limit na wyprzedaż Black Friday, ale postanawiasz ją przełożyć. Zamiast usuwać regułę, możesz ją przełączyć na „Wył.”, a następnie na „Wł.”, gdy będziesz gotowy.
-   **Przycisk Zapisz:**
    -   **Co robi to ustawienie:** Zapisuje wszystkie zmiany wprowadzone w regule limitu ilości.
    -   **Efekt zmiany tego ustawienia:** Stosuje nową lub zaktualizowaną regułę do egzekwowania ilości produktów w Twoim sklepie.

**Efekt zmian:**
-   **Dodanie nowej reguły:** Zostanie utworzony nowy limit ilości, który stanie się aktywny (jeśli ustawiono na „Wł.”) w określonym zakresie dat, ograniczając zakupy wybranego produktu.
-   **Modyfikacja istniejącej reguły:** Zmiany (np. produkt, daty, ilość, status aktywności) natychmiast zaktualizują sposób egzekwowania limitu.
-   **Usunięcie reguły:** Limit ilości zostanie trwale usunięty, a dla tego produktu nie będą obowiązywać żadne ograniczenia dla tego zakresu dat (chyba że istnieją inne reguły).

**Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
1.  **Zaplanuj promocje/ograniczenia:** Przed konfiguracją zdecyduj, które produkty wymagają limitów, jakie powinny być maksymalne ilości oraz dokładne daty i godziny rozpoczęcia/zakończenia.
2.  **Przejdź do „Limit ilości zakupu produktu według daty”:** Przejdź do **Katalog > Limit ilości zakupu produktu według daty**.
3.  **Dodaj nowe reguły:** Kliknij „Dodaj nowy” dla każdego produktu, który chcesz ograniczyć. Ostrożnie wypełnij pola Produkt, Data od, Data do, Ilość i upewnij się, że „Aktywny” jest ustawione na „Wł.”.
4.  **Przejrzyj i dostosuj:** Regularnie sprawdzaj listę reguł, aby upewnić się, że są nadal aktualne i poprawnie skonfigurowane. Użyj przełącznika „Aktywny”, aby tymczasowo wyłączyć reguły, jeśli to konieczne.
5.  **Monitoruj opinie klientów:** Zwracaj uwagę na wszelkie zapytania klientów dotyczące limitów ilości, aby upewnić się, że reguły są jasne i działają zgodnie z przeznaczeniem.

### 2.3 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok                                       | Ustawienie / Opcja                     | Domyślne / Zalecane | Cel i wpływ
"""
