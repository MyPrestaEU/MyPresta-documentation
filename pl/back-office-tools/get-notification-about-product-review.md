---
title: "Otrzymuj powiadomienia o recenzjach produktów - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla programistów modułu PrestaShop „Otrzymuj powiadomienia o recenzjach produktów” od MyPresta.eu."
sidebar:
  label: "Otrzymuj powiadomienia o recenzjach produktów"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Get notification about product review na MyPresta.eu](https://mypresta.eu/modules/administration-tools/get-notification-about-product-review.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/get-notification-about-product-review/)
>
> ---


# Otrzymuj powiadomienia o recenzjach produktów

## 1. Wymagania i kompatybilność

-   **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x
-   **Kompatybilność z PHP**: PHP 7.1 - 8.5
-   **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).
-   **Wymaganie wstępne**: Ten moduł wymaga zainstalowania i aktywowania naszego darmowego dodatku do recenzji produktów. Rozszerza on funkcjonalność tego modułu.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)
Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównego i jedynego ekranu konfiguracji tego modułu. Ten ekran pozwala zdefiniować adres e-mail, na który będą wysyłane powiadomienia.

#### **Adres e-mail do wysyłania powiadomień**
-   **Co robi to ustawienie:** Jest to najważniejsze ustawienie. Określa adres e-mail, na który będą wysyłane wszystkie powiadomienia związane z recenzjami.
-   **Efekt zmiany tego ustawienia:**
    -   *Po wprowadzeniu prawidłowego adresu e-mail:* Wszystkie alerty (nowa recenzja, zgłoszony komentarz, głos „przydatne”) zostaną wysłane na ten konkretny adres e-mail.
    -   *Po pozostawieniu pustego lub wprowadzeniu nieprawidłowego adresu e-mail:* Nie będziesz otrzymywać żadnych powiadomień, co skutecznie wyłączy podstawową funkcję modułu.
-   **Zalecana wartość:** Twój główny służbowy adres e-mail lub adres e-mail regularnie monitorowany przez Twój zespół obsługi klienta lub marketingowy.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój zespół obsługi klienta obsługuje wszystkie interakcje z klientami, możesz tutaj wpisać `obslugaklienta@twojsklep.com`. Jeśli Ty, jako właściciel, chcesz być osobiście informowany, użyj swojego bezpośredniego adresu e-mail.

#### **Tabela szybkiego odniesienia do konfiguracji**

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Konfiguracja modułu | Adres e-mail do wysyłania powiadomień | Twój główny służbowy adres e-mail | Określa odbiorcę e-maila dla wszystkich alertów związanych z recenzjami (nowa recenzja, zgłoszony komentarz, głos „przydatne”). |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Nie otrzymuję żadnych powiadomień e-mail. Co powinienem zrobić?**
O:
1.  **Sprawdź adres e-mail:** Przejdź do **Moduły > Menedżer modułów > Konfiguruj** dla modułu „Otrzymuj powiadomienia o recenzjach produktów” i upewnij się, że wprowadzony adres e-mail jest poprawny i wolny od literówek.
2.  **Sprawdź folder spamu:** Powiadomienia mogą czasami być filtrowane do folderu spamu lub wiadomości-śmieci. Dodaj adres e-mail nadawcy (zazwyczaj domyślny adres e-mail Twojego sklepu) do listy bezpiecznych nadawców.
3.  **Zweryfikuj ustawienia e-mail PrestaShop:** Upewnij się, że ustawienia e-mail Twojego sklepu PrestaShop są poprawnie skonfigurowane i ogólnie wysyłają e-maile. Możesz to przetestować, tworząc nowe konto klienta lub składając zamówienie testowe. Przejdź do **Zaawansowane > E-mail** w swoim panelu administracyjnym.
4.  **Skontaktuj się ze swoim dostawcą hostingu:** Jeśli e-maile PrestaShop w ogóle nie działają, może występować problem z funkcją poczty Twojego serwera. Twój dostawca hostingu może pomóc w diagnozie.
5.  **Upewnij się, że moduł wymagany jest zainstalowany:** Ten moduł rozszerza nasz darmowy dodatek do recenzji produktów. Upewnij się, że ten moduł jest zainstalowany i działa poprawnie.

**P: Czy mogę wysyłać powiadomienia na wiele adresów e-mail?**
O: Obecna konstrukcja modułu pozwala na skonfigurowanie tylko jednego adresu e-mail. Jeśli potrzebujesz wysyłać do wielu odbiorców, możesz ustawić regułę przekierowania e-maili w swoim kliencie poczty e-mail lub na serwerze (np. przekierować e-maile z skonfigurowanego adresu na alias grupy).

**P: Czy ten moduł działa z dowolnym systemem recenzji produktów?**
O: Nie, ten moduł jest specjalnie zaprojektowany do działania jako rozszerzenie **darmowego dodatku do recenzji produktów MyPresta.eu**. Nie będzie dostarczał powiadomień dla innych modułów recenzji stron trzecich.

**P: Zaktualizowałem swój motyw PrestaShop, a teraz powiadomienia nie działają.**
O: Ten moduł nie posiada żadnych komponentów front-office, więc zmiana motywu nie powinna bezpośrednio wpływać na jego funkcjonalność powiadomień. Sprawdź ponownie konfigurację e-mail w module i ustawienia e-mail PrestaShop, jak opisano powyżej. Jeśli problem nadal występuje, prawdopodobnie nie jest on związany z motywem i wskazuje na problem z serwerem lub podstawową funkcją e-mail PrestaShop.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury
Moduł „Otrzymuj powiadomienia o recenzjach produktów” (`reviewsalerts`) to lekki moduł PrestaShop zaprojektowany do rozszerzania funkcjonalności podstawowego modułu `productcomments` (lub podobnego modułu recenzji, w szczególności darmowego dodatku do recenzji produktów MyPresta.eu). Działa głównie poprzez podłączanie się do odpowiednich akcji wyzwalanych przez system recenzji i wysyłanie powiadomień e-mail na podstawie tych zdarzeń. Stosuje prosty wzorzec sterowany zdarzeniami, wykorzystując system hooków PrestaShop bez wprowadzania złożonych struktur MVC ani niestandardowych tabel baz danych.

### 4.2 Kontrolery (`controllers/`)
Ten moduł nie zawiera żadnych niestandardowych kontrolerów front-office ani back-office. Cała logika jest hermetyzowana w głównym pliku modułu i wykonywana za pośrednictwem hooków.

### 4.3 Klasy podstawowe i modele (`classes/`)
Ten moduł nie definiuje żadnych niestandardowych klas ani instancji `ObjectModel`. Jego funkcjonalność jest zawarta w głównej klasie `reviewsalerts`.

### 4.4 Zasoby JavaScript (`views/js/`)
Ten moduł nie zawiera żadnych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)
Ten moduł nie zawiera żadnych plików CSS.

### 4.6 Struktura szablonów Smarty (`views/templates/`)
Ten moduł nie zawiera żadnych niestandardowych plików szablonów Smarty do wyświetlania w front-office ani konfiguracji w back-office. Formularz konfiguracji jest generowany dynamicznie przez `getContent()` w głównym pliku modułu.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele baz danych**: Ten moduł nie tworzy żadnych niestandardowych tabel baz danych. Przechowuje swoje pojedyncze ustawienie konfiguracyjne (adres e-mail powiadomień) w standardowej tabeli `ps_configuration`.
    *   **Klucz konfiguracji**: `REVIEWSALERTS_EMAIL`

-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| :-------- | :--------------- | :---------------- |
| `actionObjectProductCommentAddAfter` | Po pomyślnym dodaniu nowej recenzji produktu (komentarza) do bazy danych. | Wyzwala powiadomienie e-mail na skonfigurowany adres, informując sprzedawcę o nowej recenzji. |
| `actionObjectProductCommentReportAfter` | Po pomyślnym zgłoszeniu recenzji produktu przez klienta. | Wyzwala powiadomienie e-mail na skonfigurowany adres, informując sprzedawcę, że recenzja została zgłoszona. |
| `actionObjectProductCommentUsefulAfter` | Po tym, jak klient oznaczy recenzję produktu jako „przydatną”. | Wyzwala powiadomienie e-mail na skonfigurowany adres, informując sprzedawcę, że głosowano na przydatność recenzji. |

Metoda `install()` modułu rejestruje te hooki, a odpowiadające im metody `hookActionObjectProductCommentAddAfter()`, `hookActionObjectProductCommentReportAfter()` i `hookActionObjectProductCommentUsefulAfter()` obsługują logikę wysyłania e-maili.

Wysyłanie e-maili jest zazwyczaj obsługiwane przez funkcję `Mail::Send()` PrestaShop, wykorzystując skonfigurowane szablony e-maili i ustawienia sklepu. Moduł prawdopodobnie dynamicznie konstruuje treść e-maila na podstawie kontekstu wyzwolonej akcji (np. treść recenzji, nazwa produktu, dane zgłaszającego).

## 5. Oficjalne wsparcie i aktualizacje
Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Otrzymuj powiadomienia o recenzjach produktów”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i konfiguracji modułu.
