---
title: "Galeria zdjęć klientów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Galeria zdjęć klientów od MyPresta.eu."
sidebar:
  label: "Galeria zdjęć klientów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Customer Photo Gallery na MyPresta.eu](https://mypresta.eu/modules/front-office-features/customer-photo-gallery.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/customer-photo-gallery/)
>
> ---


# Galeria zdjęć klientów

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i wszelkich interakcji modułów. Upewnij się, że Twój serwer ma wystarczającą ilość miejsca na dysku do przechowywania przesłanych zdjęć i filmów.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu Galeria zdjęć klientów, gdzie kontrolujesz wszystkie jego funkcje i sposób wyświetlania w Twoim sklepie.

| Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- |
| **Zezwól na przesyłanie JPEG** | TAK | **Co robi to ustawienie:** Kontroluje, czy klienci mogą przesyłać obrazy w formacie JPEG.   **Efekt zmiany tego ustawienia:**   *Gdy włączone:* Klienci mogą przesyłać pliki .jpg i .jpeg.   *Gdy wyłączone:* Pliki JPEG zostaną odrzucone podczas przesyłania.   **Zalecana wartość:** TAK (JPEG to bardzo popularny format obrazu).   **Scenariusz dla sprzedawcy:** Jeśli chcesz ograniczyć typy obrazów ze względu na specyficzną jakość lub branding, możesz wyłączyć niektóre formaty. |
| **Zezwól na przesyłanie GIF** | TAK | **Co robi to ustawienie:** Kontroluje, czy klienci mogą przesyłać obrazy w formacie GIF.   **Efekt zmiany tego ustawienia:**   *Gdy włączone:* Klienci mogą przesyłać pliki .gif.   *Gdy wyłączone:* Pliki GIF zostaną odrzucone.   **Zalecana wartość:** TAK (GIF-y mogą być przydatne do prostych animacji lub przezroczystego tła). |
| **Zezwól na przesyłanie PNG** | TAK | **Co robi to ustawienie:** Kontroluje, czy klienci mogą przesyłać obrazy w formacie PNG.   **Efekt zmiany tego ustawienia:**   *Gdy włączone:* Klienci mogą przesyłać pliki .png.   *Gdy wyłączone:* Pliki PNG zostaną odrzucone.   **Zalecana wartość:** TAK (PNG jest doskonały do obrazów z przezroczystością i wysoką jakością). |
| **Zezwól na przesyłanie BMP** | NIE | **Co robi to ustawienie:** Kontroluje, czy klienci mogą przesyłać obrazy w formacie BMP.   **Efekt zmiany tego ustawienia:**   *Gdy włączone:* Klienci mogą przesyłać pliki .bmp.   *Gdy wyłączone:* Pliki BMP zostaną odrzucone.   **Zalecana wartość:** NIE (pliki BMP są zazwyczaj bardzo duże i nieskompresowane, nie idealne do użytku w sieci).   **Scenariusz dla sprzedawcy:** Włącz tylko, jeśli masz specyficzną potrzebę nieskompresowanych obrazów, ale bądź świadomy wpływu na przestrzeń serwerową i czas ładowania strony. |
| **Włącz paginację** | TAK | **Co robi to ustawienie:** Określa, czy strony galerii będą używać paginacji (np. „Strona 1 z 5”).   **Efekt zmiany tego ustawienia:**   *Gdy włączone:* Zawartość galerii jest dzielona na wiele stron, poprawiając czasy ładowania dla dużych galerii.   *Gdy wyłączone:* Cała zawartość galerii ładuje się na jednej stronie, co może być wolne dla wielu zdjęć.   **Zalecana wartość:** TAK.   **Scenariusz dla sprzedawcy:** Niezbędne do zarządzania dużymi galeriami i zapewnienia płynnego doświadczenia użytkownika. |
| **Zezwól niezalogowanym użytkownikom na przesyłanie** | NIE | **Co robi to ustawienie:** Pozwala odwiedzającym, którzy nie są zalogowani na konto klienta, przesyłać zdjęcia.   **Efekt zmiany tego ustawienia:**   *Gdy włączone:* Goście mogą przesyłać zdjęcia. Może to zwiększyć liczbę wkładów, ale może również prowadzić do większej ilości spamu lub nieistotnych treści.   *Gdy wyłączone:* Tylko zalogowani klienci mogą przesyłać zdjęcia, zapewniając pewien poziom odpowiedzialności.   **Zalecana wartość:** NIE (chyba że masz silną moderację).   **Scenariusz dla sprzedawcy:** Jeśli chcesz zmaksymalizować liczbę wkładów i jesteś przygotowany na moderację, włącz to. W przeciwnym razie pozostaw wyłączone, aby utrzymać kontrolę jakości. |
| **Maksymalny rozmiar pliku (MB)** | 5 | **Co robi to ustawienie:** Ustawia maksymalny rozmiar (w megabajtach) dla pojedynczego przesłanego pliku obrazu.   **Efekt zmiany tego ustawienia:**   *Gdy ustawione na wyższą wartość:* Klienci mogą przesyłać większe, potencjalnie wyższej jakości obrazy, ale to zużywa więcej miejsca na serwerze i przepustowości.   *Gdy ustawione na niższą wartość:* Ogranicza rozmiar pliku, oszczędzając zasoby serwera, ale potencjalnie ograniczając jakość obrazu.   **Zalecana wartość:** 5-10 MB jest zazwyczaj wystarczające dla obrazów zoptymalizowanych pod kątem sieci.   **Scenariusz dla sprzedawcy:** Zrównoważ jakość obrazu z zasobami serwera. Zbyt niska wartość może frustrować klientów; zbyt wysoka może zwiększyć koszty hostingu. |
| **Włącz zakładkę produktu** | NIE | **Co robi to ustawienie:** Wyświetla dedykowaną zakładkę „Zdjęcia klientów” na stronach produktów.   **Efekt zmiany tego ustawienia:**   *Gdy włączone:* Na stronach produktów pojawia się nowa zakładka, prezentująca zdjęcia specyficznie związane z tym produktem.   *Gdy wyłączone:* Brak dedykowanej zakładki dla zdjęć klientów na stronach produktów.   **Zalecana wartość:** TAK (jeśli chcesz pokazywać UGC specyficzne dla produktu).   **Scenariusz dla sprzedawcy:** Świetne dla produktów, gdzie wizualne referencje mają duży wpływ, takich jak moda czy wystrój wnętrz. |
| **Pozycja zakładki produktu (Hook modułu)** | displayProductExtraContent | **Co robi to ustawienie:** Określa, gdzie zakładka produktu jest zaczepiona na stronie produktu.   **Efekt zmiany tego ustawienia:** Zmienia wizualne umiejscowienie zakładki „Zdjęcia klientów” na stronie produktu.   **Zalecana wartość:** `displayProductExtraContent` lub `displayProductTab`.   **Scenariusz dla sprzedawcy:** Przetestuj różne hooki, aby znaleźć najlepszą wizualną integrację z Twoim motywem. |
| **Wyświetl w stopce produktu** | NIE | **Co robi to ustawienie:** Pokazuje blok zdjęć klientów w obszarze stopki stron produktów.   **Efekt zmiany tego ustawienia:**   *Gdy włączone:* Mały blok galerii pojawia się na dole stron produktów.   *Gdy wyłączone:* Brak zdjęć klientów w stopce strony produktu.   **Zalecana wartość:** NIE (chyba że masz specyficzną potrzebę projektową).   **Scenariusz dla sprzedawcy:** Może być używane do zachęcania do przeglądania lub sprzedaży krzyżowej poprzez pokazywanie powiązanych zdjęć klientów. |
| **Wyświetl w koncie klienta** | TAK | **Co robi to ustawienie:** Dodaje link do „Moich zdjęć” w panelu konta klienta.   **Efekt zmiany tego ustawienia:**   *Gdy włączone:* Zalogowani klienci widzą link do zarządzania swoimi przesłanymi zdjęciami.   *Gdy wyłączone:* Klienci nie mogą łatwo uzyskać dostępu do obszaru zarządzania zdjęciami ze swojego konta.   **Zalecana wartość:** TAK.   **Scenariusz dla sprzedawcy:** Niezbędne dla klientów do zarządzania swoimi wkładami. |
| **Wyświetl w bloku Moje konto** | TAK | **Co robi to ustawienie:** Dodaje link do „Moich zdjęć” w bloku „Moje konto” (zazwyczaj w lewej/prawej kolumnie lub stopce).   **Efekt zmiany tego ustawienia:**   *Gdy włączone:* Link pojawia się w bloku szybkiego dostępu „Moje konto”.   *Gdy wyłączone:* Brak linku w bloku „Moje konto”.   **Zalecana wartość:** TAK.   **Scenariusz dla sprzedawcy:** Zapewnia kolejny wygodny punkt dostępu dla klientów do zarządzania swoimi zdjęciami. |
| **Wysokość miniatury (px)** | 100 | **Co robi to ustawienie:** Ustawia wysokość generowanych miniatur dla obrazów galerii.   **Efekt zmiany tego ustawienia:**   *Gdy ustawione na wyższą wartość:* Większe miniatury, potencjalnie wyraźniejsze, ale zajmują więcej miejsca.   *Gdy ustawione na niższą wartość:* Mniejsze miniatury, oszczędzające miejsce, ale mniej szczegółowe.   **Zalecana wartość:** 100-150px.   **Scenariusz dla sprzedawcy:** Dostosuj, aby pasowało do projektu Twojego motywu i zapewniło atrakcyjny wizualnie układ galerii. |
| **Szerokość miniatury (px)** | 100 | **Co robi to ustawienie:** Ustawia szerokość generowanych miniatur dla obrazów galerii.   **Efekt zmiany tego ustawienia:**   *Gdy ustawione na wyższą wartość:* Większe miniatury.   *Gdy ustawione na niższą wartość:* Mniejsze miniatury.   **Zalecana wartość:** 100-150px.   **Scenariusz dla sprzedawcy:** Dostosuj, aby pasowało do projektu Twojego motywu i zapewniło atrakcyjny wizualnie układ galerii. |
| **Włącz formularz przesyłania zdjęć** | TAK | **Co robi to ustawienie:** Kontroluje widoczność formularza przesyłania zdjęć na stronie galerii.   **Efekt zmiany tego ustawienia:**   *Gdy włączone:* Klienci mogą widzieć i używać formularza przesyłania.   *Gdy wyłączone:* Formularz przesyłania jest ukryty, uniemożliwiając nowe zgłoszenia.   **Zalecana wartość:** TAK (chyba że tymczasowo chcesz wstrzymać nowe przesyłanie).   **Scenariusz dla sprzedawcy:** Wyłącz, jeśli prowadzisz konkurs z terminem zgłoszeń lub musisz wstrzymać przesyłanie w celu konserwacji. |
| **Wyświetl link do galerii** | TAK | **Co robi to ustawienie:** Dodaje link do głównej strony galerii zdjęć w nawigacji Twojego sklepu.   **Efekt zmiany tego ustawienia:**   *Gdy włączone:* Link (np. „Galeria klientów”) pojawia się w wybranym hooku.   *Gdy wyłączone:* Link do głównej strony galerii jest ukryty.   **Zalecana wartość:** TAK.   **Scenariusz dla sprzedawcy:** Niezbędne dla klientów do znajdowania i przeglądania galerii. |
| **Wyświetl w prawej kolumnie** | NIE | **Co robi to ustawienie:** Pokazuje blok z ostatnimi zdjęciami klientów w prawej kolumnie Twojego sklepu.   **Efekt zmiany tego ustawienia:**   *Gdy włączone:* Blok pojawia się w prawej kolumnie.   *Gdy wyłączone:* Brak bloku w prawej kolumnie.   **Zalecana wartość:** NIE (może zaśmiecać układ, ale zależy od Twojego motywu).   **Scenariusz dla sprzedawcy:** Przydatne, jeśli Twój motyw ma dużo miejsca w prawej kolumnie i chcesz wyróżnić ostatnie wkłady. |
| **Wyświetl w lewej kolumnie** | NIE | **Co robi to ustawienie:** Pokazuje blok z ostatnimi zdjęciami klientów w lewej kolumnie Twojego sklepu.   **Efekt zmiany tego ustawienia:**   *Gdy włączone:* Blok pojawia się w lewej kolumnie.   *Gdy wyłączone:* Brak bloku w lewej kolumnie.   **Zalecana wartość:** NIE (może zaśmiecać układ, ale zależy od Twojego motywu).   **Scenariusz dla sprzedawcy:** Podobnie jak w prawej kolumnie, użyj, jeśli Twój motyw dobrze to obsługuje. |
| **Włącz powiadomienia** | TAK | **Co robi to ustawienie:** Wysyła powiadomienia e-mail do administratora sklepu, gdy zostaną przesłane nowe zdjęcia.   **Efekt zmiany tego ustawienia:**   *Gdy włączone:* Otrzymujesz e-mail dla każdego nowego przesłania, co pozwala na szybką moderację.   *Gdy wyłączone:* Brak powiadomień e-mail.   **Zalecana wartość:** TAK.   **Scenariusz dla sprzedawcy:** Kluczowe dla terminowej moderacji i zapewnienia, że wyświetlane są tylko odpowiednie treści. |
| **Liczba zdjęć na stronie głównej** | 8 | **Co robi to ustawienie:** Ustawia, ile zdjęć klientów jest wyświetlanych w bloku na stronie głównej.   **Efekt zmiany tego ustawienia:** Zmienia ilość zdjęć wyświetlanych na stronie głównej.   **Zalecana wartość:** 6-12, w zależności od układu Twojej strony głównej.   **Scenariusz dla sprzedawcy:** Dostosuj, aby pasowało do projektu Twojej strony głównej, nie przytłaczając strony. |
| **Kolejność zdjęć na stronie głównej** | Najnowsze jako pierwsze | **Co robi to ustawienie:** Określa kolejność sortowania zdjęć wyświetlanych na stronie głównej.   **Efekt zmiany tego ustawienia:** Zdjęcia mogą być sortowane według najnowszych, najstarszych, najpopularniejszych itp.   **Zalecana wartość:** Najnowsze jako pierwsze lub Najpopularniejsze.   **Scenariusz dla sprzedawcy:** „Najnowsze jako pierwsze” utrzymuje świeżość treści; „Najpopularniejsze” wyróżnia angażujące treści. |
| **Włącz tryb konkursu fotograficznego** | NIE | **Co robi to ustawienie:** Aktywuje funkcje do prowadzenia konkursu fotograficznego, potencjalnie obejmując mechanizmy głosowania i nagród.   **Efekt zmiany tego ustawienia:**   *Gdy włączone:* Mogą pojawić się dodatkowe opcje związane z konkursem, a galeria może kłaść nacisk na głosowanie.   *Gdy wyłączone:* Standardowy tryb galerii.   **Zalecana wartość:** NIE (chyba że aktywnie prowadzisz konkurs).   **Scenariusz dla sprzedawcy:** Użyj tego, gdy chcesz przeprowadzić konkretną kampanię w celu zbierania zdjęć i angażowania użytkowników poprzez głosowanie. |
| **Wyklucz produkty z galerii** | (ID produktów) | **Co robi to ustawienie:** Pozwala określić ID produktów, dla których zdjęcia klientów NIE powinny być wyświetlane na ich stronach produktów.   **Efekt zmiany tego ustawienia:** Zdjęcia dla tych konkretnych produktów nie pojawią się w zakładce/stopce produktu, nawet jeśli główne ustawienie zakładki produktu jest włączone.   **Zalecana wartość:** Pozostaw puste, chyba że jest to konieczne.   **Scenariusz dla sprzedawcy:** Jeśli masz wrażliwe produkty lub produkty, dla których zdjęcia klientów są nieistotne lub nieodpowiednie, możesz je wykluczyć. |
| **Widoczność linku do konta klienta** | TAK | **Co robi to ustawienie:** Kontroluje widoczność linku „Moje zdjęcia” w panelu konta klienta.   **Efekt zmiany tego ustawienia:**   *Gdy włączone:* Link jest widoczny.   *Gdy wyłączone:* Link jest ukryty.   **Zalecana wartość:** TAK.   **Scenariusz dla sprzedawcy:** Pozostaw włączone dla wygody klienta. |
| **Widoczność linku w bloku Moje konto** | TAK | **Co robi to ustawienie:** Kontroluje widoczność linku „Moje zdjęcia” w bloku „Moje konto” (np. w kolumnach).   **Efekt zmiany tego ustawienia:**   *Gdy włączone:* Link jest widoczny.   *Gdy wyłączone:* Link jest ukryty.   **Zalecana wartość:** TAK.   **Scenariusz dla sprzedawcy:** Pozostaw włączone dla wygody klienta. |
| **Włącz głosowanie na zdjęcia** | TAK | **Co robi to ustawienie:** Pozwala klientom (i opcjonalnie gościom) głosować na przesłane zdjęcia.   **Efekt zmiany tego ustawienia:**   *Gdy włączone:* Przy zdjęciach pojawiają się przyciski/gwiazdki do głosowania.   *Gdy wyłączone:* Brak funkcji głosowania.   **Zalecana wartość:** TAK (zwiększa zaangażowanie).   **Scenariusz dla sprzedawcy:** Użyj, aby zidentyfikować popularne zdjęcia, prowadzić konkursy lub po prostu zachęcać do interakcji. |
| **Typ systemu głosowania** | Gwiazdki | **Co robi to ustawienie:** Wybiera styl wizualny systemu głosowania (np. gwiazdki, kciuki w górę/w dół).   **Efekt zmiany tego ustawienia:** Zmienia wygląd mechanizmu głosowania.   **Zalecana wartość:** Gwiazdki (ogólnie bardziej intuicyjne).   **Scenariusz dla sprzedawcy:** Wybierz styl, który najlepiej pasuje do estetyki Twojego sklepu. |
| **Zezwól niezalogowanym użytkownikom na głosowanie** | NIE | **Co robi to ustawienie:** Pozwala odwiedzającym, którzy nie są zalogowani, głosować na zdjęcia.   **Efekt zmiany tego ustawienia:**   *Gdy włączone:* Goście mogą głosować. Może to zwiększyć uczestnictwo, ale może być podatne na nadużycia.   *Gdy wyłączone:* Tylko zalogowani klienci mogą głosować.   **Zalecana wartość:** NIE (aby zapobiec manipulacji głosami).   **Scenariusz dla sprzedawcy:** Włącz tylko, jeśli priorytetem jest maksymalne uczestnictwo, a nie ścisła integralność głosowania. |

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | CG\_ALLOW\_JPEG | TAK | Zezwól na przesyłanie obrazów JPEG. |
| Konfiguracja modułu | CG\_ALLOW\_GIF | TAK | Zezwól na przesyłanie obrazów GIF. |
| Konfiguracja modułu | CG\_ALLOW\_PNG | TAK | Zezwól na przesyłanie obrazów PNG. |
| Konfiguracja modułu | CG\_ALLOW\_BMP | NIE | Zezwól na przesyłanie obrazów BMP (duże pliki). |
| Konfiguracja modułu | CG\_PAGINATION | TAK | Włącz paginację dla stron galerii. |
| Konfiguracja modułu | CG\_ALLOW\_UNLOGGED | NIE | Zezwól gościom na przesyłanie zdjęć. |
| Konfiguracja modułu | CG\_MAX\_FILE\_SIZE | 5 MB | Maksymalny rozmiar pliku do przesłania. |
| Konfiguracja modułu | CG\_PRODUCTTAB | NIE | Wyświetl zdjęcia klientów w zakładce produktu. |
| Konfiguracja modułu | cg\_productTabM | displayProductExtraContent | Hook dla umiejscowienia zakładki produktu. |
| Konfiguracja modułu | CG\_PRODUCTFOOTER | NIE | Wyświetl zdjęcia w stopce produktu. |
| Konfiguracja modułu | CG\_CUSTOMERACCOUNT | TAK | Pokaż link „Moje zdjęcia” w koncie klienta. |
| Konfiguracja modułu | CG\_MYACCOUNTBLOCK | TAK | Pokaż link „Moje zdjęcia” w bloku Moje konto. |
| Konfiguracja modułu | CG\_THUMBHEIGHT | 100 | Wysokość generowanych miniatur. |
| Konfiguracja modułu | CG\_THUMBWIDTH | 100 | Szerokość generowanych miniatur. |
| Konfiguracja modułu | CG\_FUPLOADON | TAK | Włącz formularz przesyłania zdjęć. |
| Konfiguracja modułu | CG\_GALLERY | TAK | Wyświetl link do głównej strony galerii. |
| Konfiguracja modułu | CG\_RIGHTCOL | NIE | Wyświetl zdjęcia w prawej kolumnie. |
| Konfiguracja modułu | CG\_LEFTCOL | NIE | Wyświetl zdjęcia w lewej kolumnie. |
| Konfiguracja modułu | CG\_NTF | TAK | Wysyłaj powiadomienia e-mail do administratora o nowych przesyłanych plikach. |
| Konfiguracja modułu | cg\_hpg\_nb | 8 | Liczba zdjęć na stronie głównej. |
| Konfiguracja modułu | cg\_hpg\_o | Najnowsze jako pierwsze | Kolejność zdjęć na stronie głównej. |
| Konfiguracja modułu | cg\_contest | NIE | Włącz tryb konkursu fotograficznego. |
| Konfiguracja modułu | cg\_excludeproduct | (puste) | ID produktów do wykluczenia z galerii. |
| Konfiguracja modułu | CG\_CUSTOMERACCOUNTV | TAK | Widoczność linku „Moje zdjęcia” w koncie klienta. |
| Konfiguracja modułu | CG\_MYACCOUNTBLOCKV | TAK | Widoczność linku „Moje zdjęcia” w bloku Moje konto. |
| Konfiguracja modułu | CG\_voting | TAK | Włącz głosowanie na zdjęcia. |
| Konfiguracja modułu | CG\_VOTE\_STAR | Gwiazdki | Styl wizualny systemu głosowania. |
| Konfiguracja modułu | cg\_unl\_voting | NIE | Zezwól niezalogowanym użytkownikom na głosowanie. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje przesłane zdjęcia nie pojawiają się w galerii.**
**O:**

-   **Sprawdź konfigurację modułu:** Upewnij się, że „Włącz formularz przesyłania zdjęć” (`CG_FUPLOADON`) jest ustawione na TAK.
-   **Typ i rozmiar pliku:** Sprawdź, czy przesłany typ pliku (JPEG, PNG, GIF, BMP) jest dozwolony w ustawieniach modułu i czy rozmiar pliku mieści się w limicie „Maksymalny rozmiar pliku” (`CG_MAX_FILE_SIZE`).
-   **Moderacja:** Moduł może mieć wewnętrzną kolejkę moderacji (choć nie jest to wyraźnie wymienione jako ustawienie, wiele modułów galerii taką posiada). Sprawdź, czy istnieje sekcja administracyjna do zatwierdzania/odrzucania zdjęć.
-   **Uprawnienia:** Upewnij się, że katalog `img/customersgallery/` (lub podobna ścieżka, w której przechowywane są obrazy) na Twoim serwerze ma uprawnienia do zapisu (zazwyczaj 755 lub 777, choć 777 jest mniej bezpieczne).
-   **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop i wyczyść pamięć podręczną Smarty, pamięć podręczną przeglądarki i pamięć podręczną modułu.

**P2: Link do galerii lub blok nie pojawia się w moim sklepie.**
**O:**

-   **Hooki modułu:** Sprawdź stronę konfiguracji modułu. Upewnij się, że „Wyświetl link do galerii” (`CG_GALLERY`), „Wyświetl w prawej kolumnie” (`CG_RIGHTCOL`), „Wyświetl w lewej kolumnie” (`CG_LEFTCOL`) itp. są włączone dla oczekiwanych lokalizacji.
-   **Zarządzanie hookami:** Przejdź do **Wygląd > Pozycje** (lub **Moduły > Pozycje** w starszych wersjach) w Panelu administracyjnym PrestaShop. Wyszukaj moduł („Galeria zdjęć klientów”) i upewnij się, że jest zaczepiony do prawidłowych pozycji `display` (np. `displayHeader`, `displayHome`, `displayRightColumn`). Jeśli nie, „Przeszczep moduł” do żądanego hooka.
-   **Kompatybilność z motywem:** Niektóre niestandardowe motywy mogą nadpisywać standardowe pozycje hooków. Jeśli moduł nie pojawia się pomimo prawidłowego zaczepienia, może wymagać drobnych dostosowań motywu. Skontaktuj się z twórcą motywu lub wsparciem MyPresta.eu.
-   **Wyczyść pamięć podręczną:** Zawsze wyczyść pamięć podręczną PrestaShop po wprowadzeniu zmian w pozycjach modułów lub ustawieniach.

**P3: Zdjęcia na stronach produktów nie pojawiają się w zakładce.**
**O:**

-   **Włącz zakładkę produktu:** Upewnij się, że `CG_PRODUCTTAB` jest ustawione na TAK w konfiguracji modułu.
-   **Hook zakładki produktu:** Sprawdź, czy `cg_productTabM` jest ustawione na odpowiedni hook, taki jak `displayProductExtraContent` lub `displayProductTab`.
-   **Wykluczenie produktu:** Sprawdź `cg_excludeproduct`, aby upewnić się, że przeglądany produkt nie jest tam wymieniony.
-   **Powiązane zdjęcia:** Upewnij się, że faktycznie przesłano i powiązano zdjęcia z tym konkretnym produktem.
-   **Wyczyść pamięć podręczną:** Wyczyść wszystkie pamięci podręczne.

**P4: System głosowania nie działa lub nie jest widoczny.**
**O:**

-   **Włącz głosowanie:** Upewnij się, że „Włącz głosowanie na zdjęcia” (`CG_voting`) jest ustawione na TAK.
-   **Niezalogowani użytkownicy:** Jeśli goście nie mogą głosować, sprawdź „Zezwól niezalogowanym użytkownikom na głosowanie” (`cg_unl_voting`).
-   **Konflikty CSS:** Czasami CSS motywu może ukrywać lub zniekształcać elementy modułu. Użyj narzędzi deweloperskich przeglądarki (F12), aby zbadać obszar i sprawdzić, czy nie ma konfliktowych stylów.
-   **Błędy JavaScript:** Sprawdź konsolę przeglądarki (F12 > zakładka Konsola) pod kątem błędów JavaScript, które mogą uniemożliwiać działanie funkcji głosowania.

**P5: Jak przetłumaczyć tekst modułu na inne języki?**
**O:**

-   Przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym PrestaShop.
-   Wybierz „Tłumaczenia zainstalowanych modułów”.
-   Wybierz swój motyw, język, na który chcesz przetłumaczyć, a następnie wybierz „Galeria zdjęć klientów” z listy modułów.
-   Możesz wtedy przetłumaczyć wszystkie ciągi tekstowe modułu z front-office i back-office.
-   Pamiętaj, aby zapisać zmiany i wyczyścić pamięć podręczną.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł Galeria zdjęć klientów stosuje standardową architekturę modułów PrestaShop, wykorzystując głównie kontrolery Front do interakcji użytkownika i szablony Smarty do renderowania. Integruje się z różnymi hookami wyświetlania, aby osadzić funkcje galerii w całym sklepie. Chociaż nie definiuje jawnie niestandardowych klas `ObjectModel` w dostarczonym spisie, prawdopodobnie używa `Configuration` do ustawień i bezpośrednio wchodzi w interakcje z bazą danych w celu przechowywania i zarządzania zdjęciami/filmami. AJAX jest używany do dynamicznego ładowania treści i interakcji, takich jak głosowanie.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

Te kontrolery obsługują wszystkie interakcje z klientem i przetwarzanie danych dla galerii.

-   **`customersgallery/controllers/front/ajax.php`**

    -   **Nazwa klasy:** `CustomersGalleryAjaxModuleFrontController` (prawdopodobnie rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Ten kontroler jest podstawą dynamicznych interakcji bez pełnego przeładowania strony. Obsługuje żądania AJAX dla działań takich jak:
        -   Przesyłanie nowych zdjęć/filmów.
        -   Przetwarzanie głosów (np. ocen gwiazdkowych).
        -   Ładowanie większej liczby elementów galerii (paginacja/nieskończone przewijanie).
        -   Potencjalnie działania moderacyjne, jeśli niezalogowany użytkownik przesyła i wymaga zatwierdzenia.
        -   Zwraca odpowiedzi JSON do JavaScriptu po stronie klienta.
-   **`customersgallery/controllers/front/gallery.php`**

    -   **Nazwa klasy:** `CustomersGalleryGalleryModuleFrontController` (prawdopodobnie rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Ten kontroler jest odpowiedzialny za wyświetlanie głównej strony galerii zdjęć i filmów klientów.
        -   Pobiera wszystkie zatwierdzone zdjęcia/filmy z bazy danych.
        -   Stosuje logikę paginacji na podstawie ustawień modułu (`CG_PAGINATION`).
        -   Przygotowuje dane dla szablonu `gallery.tpl`, w tym ścieżki obrazów, tytuły, opisy i dane głosowania.
        -   Obsługuje sortowanie (np. według najnowszych, najpopularniejszych).
-   **`customersgallery/controllers/front/index.php`**

    -   **Nazwa klasy:** `CustomersGalleryIndexModuleFrontController` (prawdopodobnie rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Ten kontroler może służyć jako domyślny punkt wejścia lub przekierowanie dla sekcji front-office modułu. Może być również używany do prostej strony docelowej lub do przekierowania do głównej galerii. W wielu modułach `index.php` w katalogu kontrolera front-office jest rezerwowym lub prostym przekierowaniem do głównej funkcji.
-   **`customersgallery/controllers/front/myphotos.php`**

    -   **Nazwa klasy:** `CustomersGalleryMyPhotosModuleFrontController` (prawdopodobnie rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Ten kontroler zarządza sekcją „Moje zdjęcia” w koncie klienta.
        -   Uwierzytelnia zalogowanego klienta.
        -   Pobiera wszystkie zdjęcia przesłane przez bieżącego klienta.
        -   Pozwala klientom przeglądać, edytować (np. tytuł, opis) lub usuwać własne zgłoszenia.
        -   Przygotowuje dane dla szablonu `my-photos.tpl`.
-   **`customersgallery/controllers/front/myvideos.php`**

    -   **Nazwa klasy:** `CustomersGalleryMyVideosModuleFrontController` (prawdopodobnie rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Podobnie jak `myphotos.php`, ale specjalnie do zarządzania filmami przesłanymi przez bieżącego klienta.
        -   Uwierzytelnia zalogowanego klienta.
        -   Pobiera wszystkie filmy przesłane przez bieżącego klienta.
        -   Pozwala klientom przeglądać, edytować lub usuwać własne zgłoszenia wideo.
        -   Przygotowuje dane dla szablonu `my-videos-16.tpl`.

#### Kontrolery administracyjne Back-Office

Dossier modułu wskazuje brak dedykowanych kontrolerów administracyjnych. Cała konfiguracja back-office jest obsługiwana za pomocą metody `getContent()` głównego pliku modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Dossier modułu wskazuje brak niestandardowych klas w katalogu `classes/`. Sugeruje to, że moduł prawdopodobnie zarządza swoimi danymi bezpośrednio w pliku `customersgallery.php` lub używa ogólnych metod interakcji z bazą danych PrestaShop.

-   **Przechowywanie danych:** Metadane zdjęć i filmów (ścieżki, tytuły, ID użytkowników, ID produktów, status zatwierdzenia, głosy) są prawdopodobnie przechowywane w niestandardowych tabelach bazy danych utworzonych podczas instalacji modułu. Główny plik PHP modułu (`customersgallery.php`) zawierałby zapytania SQL dla tych tabel.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`customersgallery/js/customersgallery.js`**

    -   **Zakres:** Front-office.
    -   **Szczegóły:** Jest to prawdopodobnie główny niestandardowy plik JavaScript dla galerii. Zawierałby:
        -   Słuchacze zdarzeń dla przesyłania zdjęć/filmów (np. wysyłanie formularza, zmiany wejścia pliku).
        -   Wywołania AJAX do `ajax.php` dla przesyłania, głosowania i ładowania większej ilości treści.
        -   Walidację po stronie klienta dla typów i rozmiarów plików.
        -   Dynamiczne aktualizacje wyświetlania galerii (np. dodawanie nowych zdjęć bez odświeżania strony).
        -   Interakcja z biblioteką Fancybox dla lightboxów obrazów.
-   **`customersgallery/js/fancybox.js`**

    -   **Zakres:** Front-office.
    -   **Szczegóły:** Biblioteka zewnętrzna (Fancybox) do tworzenia eleganckich, responsywnych lightboxów dla obrazów i multimediów. Ten skrypt umożliwia funkcję „kliknij, aby powiększyć” dla zdjęć z galerii.
-   **`customersgallery/js/script.js`**

    -   **Zakres:** Front-office.
    -   **Szczegóły:** Może to być ogólny skrypt narzędziowy lub skrypt dziedziczony. Może zawierać:
        -   Funkcje pomocnicze dla interakcji UI.
        -   Dodatkowe obsługi zdarzeń nie specyficzne dla podstawowej logiki galerii.
        -   Potencjalnie skrypty związane z mechanizmem głosowania lub innymi elementami interaktywnymi.
-   **`customersgallery/lib/voucherengine/script.js`**

    -   **Zakres:** Front-office.
    -   **Szczegóły:** Sugeruje to integrację z „silnikiem kuponów” lub podobnym systemem nagród. Ten skrypt obsługiwałby:
        -   Logikę przyznawania kuponów lub rabatów po pomyślnym przesłaniu zdjęcia/filmu (jeśli `cg_contest` jest włączony lub podobny system nagród jest w miejscu).
        -   Wywołania AJAX do wyzwalania generowania lub zastosowania kuponu.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`customersgallery/css/customersgallery.css`**

    -   **Zakres:** Front-office (główne style galerii).
    -   **Szczegóły:** Zawiera podstawowe reguły CSS dla układu, wyglądu i responsywności galerii zdjęć klientów, w tym:
        -   Układy siatkowe do wyświetlania zdjęć.
        -   Stylizacja miniatur, podpisów i informacji o użytkowniku.
        -   Style dla formularza przesyłania i paginacji.
        -   Responsywne dostosowania dla różnych rozmiarów ekranu.
    -   **Kluczowe selektory:** `.customer-gallery-container`, `.gallery-item`, `.gallery-thumbnail`, `.upload-form`, `.pagination`.
-   **`customersgallery/css/fancybox.css`**

    -   **Zakres:** Front-office.
    -   **Szczegóły:** Arkusz stylów dla biblioteki lightbox Fancybox, kontrolujący wygląd powiększonych obrazów, strzałek nawigacyjnych, przycisku zamykania i nakładki.
    -   **Kluczowe selektory:** `.fancybox-container`, `.fancybox-image`, `.fancybox-caption`.
-   **`customersgallery/css/star-black.css`, `star-blue.css`, `star-gold.css`, `star-pink.css`, `star-red.css`, `star-whitered.css`, `star.css`**

    -   **Zakres:** Front-office.
    -   **Szczegóły:** Są to różne motywy kolorystyczne dla systemu głosowania opartego na gwiazdkach (`CG_VOTE_STAR`). `star.css` to prawdopodobnie podstawowa stylizacja, a pozostałe zapewniają nadpisania kolorów.
    -   **Kluczowe selektory:** `.star-rating`, `.star-rating-control`, `.star-rating-star`.
-   **`customersgallery/lib/voucherengine/ps16.css`**

    -   **Zakres:** Front-office.
    -   **Szczegóły:** Ten arkusz stylów jest specjalnie dla integracji „silnika kuponów”, prawdopodobnie zapewniając stylizację dla wszelkich elementów związanych z wyświetlaniem lub powiadomieniami o kuponach, potencjalnie z konkretnymi nadpisaniami dla motywów PrestaShop 1.6.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Niestandardowe szablony (`views/templates/custom/`)

Są to prawdopodobnie specyficzne formularze lub komponenty.

-   **`customersgallery/views/templates/custom/upload-form.tpl`**
    -   **Cel:** Renderuje formularz HTML dla klientów do przesyłania zdjęć.
    -   **Zmienne:** Prawdopodobnie zawiera pola do wprowadzania plików, tytułu, opisu i potencjalnie powiązania z produktem.
-   **`customersgallery/views/templates/custom/upload-form2.tpl`**
    -   **Cel:** Może być alternatywną lub zaktualizowaną wersją formularza przesyłania, prawdopodobnie do przesyłania filmów lub innego układu.

#### Szablony Front-Office (`views/templates/front/`)

Te szablony renderują główne strony galerii i treści specyficzne dla użytkownika.

-   **`customersgallery/views/templates/front/gallery.tpl`**
    -   **Cel:** Główny szablon do wyświetlania galerii zdjęć i filmów klientów.
    -   **Zmienne:** Przechodzi przez tablice `$photos` i `$videos`, wyświetlając miniatury, tytuły i elementy głosowania. Zawiera paginację.
-   **`customersgallery/views/templates/front/gallery2.tpl`**
    -   **Cel:** Może być alternatywnym układem galerii lub specyficznym widokiem dla konkursów.
-   **`customersgallery/views/templates/front/gallery3.tpl`**
    -   **Cel:** Kolejny alternatywny układ galerii.
-   **`customersgallery/views/templates/front/menu.tpl`**
    -   **Cel:** Renderuje menu nawigacyjne specyficzne dla galerii, potencjalnie z linkami do „Moich zdjęć”, „Moich filmów”, „Prześlij” itp.
-   **`customersgallery/views/templates/front/my-photos.tpl`**
    -   **Cel:** Wyświetla listę zdjęć przesłanych przez aktualnie zalogowanego klienta, z opcjami edycji lub usunięcia.
    -   **Zmienne:** Tablica `$customer_photos`.
-   **`customersgallery/views/templates/front/my-videos-16.tpl`**
    -   **Cel:** Wyświetla listę filmów przesłanych przez aktualnie zalogowanego klienta, specjalnie zaprojektowaną dla kompatybilności z PrestaShop 1.6.
    -   **Zmienne:** Tablica `$customer_videos`.
-   **`customersgallery/views/templates/front/video-upload.tpl`**
    -   **Cel:** Renderuje formularz specjalnie do przesyłania filmów, odrębny od formularza przesyłania zdjęć.

#### Szablony hooków (`views/templates/hook/`)

Te szablony są zaprojektowane do renderowania w ramach określonych hooków PrestaShop.

-   **`customersgallery/views/templates/hook/column-link.tpl`**
    -   **Hook:** `displayLeftColumn`, `displayRightColumn`
    -   **Cel:** Renderuje blok w lewej lub prawej kolumnie z linkiem do głównej strony galerii lub kilku ostatnich zdjęć.
-   **`customersgallery/views/templates/hook/customer-my-account.tpl`**
    -   **Hook:** `displayCustomerAccount`
    -   **Cel:** Dodaje link lub blok w panelu konta klienta, zazwyczaj linkujący do „Moich zdjęć” lub „Moich filmów”.
-   **`customersgallery/views/templates/hook/hookHome.tpl`**
    -   **Hook:** `displayHome`
    -   **Cel:** Wyświetla blok ostatnich lub popularnych zdjęć klientów na stronie głównej sklepu.
    -   **Zmienne:** Tablica `$homepage_photos`.
-   **`customersgallery/views/templates/hook/my-account.tpl`**
    -   **Hook:** `displayMyAccountBlock`, `displayMyAccountBlockFooter`
    -   **Cel:** Dodaje link do „Moich zdjęć” w bloku „Moje konto”, często znajdującym się w kolumnach bocznych lub stopce.
-   **`customersgallery/views/templates/hook/productfooter.tpl`**
    -   **Hook:** `displayProductFooter`
    -   **Cel:** Renderuje blok zdjęć klientów związanych z bieżącym produktem w stopce strony produktu.
-   **`customersgallery/views/templates/hook/tab.tpl`**
    -   **Hook:** `displayProductTab`, `displayProductExtraContent`
    -   **Cel:** Renderuje nagłówek zakładki „Zdjęcia klientów” na stronie produktu.
-   **`customersgallery/views/templates/hook/tabContents.tpl`**
    -   **Hook:** `displayProductTabContent`, `displayProductExtraContent`
    -   **Cel:** Renderuje rzeczywistą zawartość (galerię zdjęć) w zakładce „Zdjęcia klientów” na stronie produktu.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

Moduł prawdopodobnie tworzy niestandardowe tabele podczas instalacji. Na podstawie funkcjonalności, byłyby to:

-   **`ps_customersgallery_photos`**:

    -   `id_photo` (KLUCZ GŁÓWNY, INT)
    -   `id_customer` (INT, FK do `ps_customer`)
    -   `id_product` (INT, FK do `ps_product`, MOŻE BYĆ NULL)
    -   `filename` (VARCHAR, ścieżka do pliku obrazu)
    -   `title` (VARCHAR)
    -   `description` (TEXT)
    -   `date_add` (DATETIME)
    -   `active` (TINYINT, dla statusu moderacji)
    -   `votes` (INT, całkowita liczba głosów)
    -   `rating` (DECIMAL, średnia ocena)
-   **`ps_customersgallery_videos`**:

    -   `id_video` (KLUCZ GŁÓWNY, INT)
    -   `id_customer` (INT, FK do `ps_customer`)
    -   `id_product` (INT, FK do `ps_product`, MOŻE BYĆ NULL)
    -   `url` (VARCHAR, dla zewnętrznych linków wideo, takich jak YouTube/Vimeo)
    -   `title` (VARCHAR)
    -   `description` (TEXT)
    -   `date_add` (DATETIME)
    -   `active` (TINYINT)
-   **`ps_customersgallery_votes`**:

    -   `id_vote` (KLUCZ GŁÓWNY, INT)
    -   `id_photo` (INT, FK do `ps_customersgallery_photos`)
    -   `id_customer` (INT, FK do `ps_customer`, MOŻE BYĆ NULL dla niezalogowanych głosów)
    -   `ip_address` (VARCHAR, dla niezalogowanych głosów i zapobiegania nadużyciom)
    -   `vote_value` (INT, np. 1-5 dla gwiazdek)
    -   `date_add` (DATETIME)
-   **`ps_configuration`**: Ustawienia modułu (np. `CG_ALLOW_JPEG`, `CG_MAX_FILE_SIZE`, `CG_PAGINATION`) są przechowywane tutaj.

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayProductExtraContent` | Renderuje dodatkową zawartość na stronie produktu, często używaną do zakładek. | Wyświetla zakładkę „Zdjęcia klientów” i jej zawartość na stronach produktów. |
| `displayRightColumnProduct` | Renderuje zawartość w prawej kolumnie strony produktu. | Wyświetla blok zdjęć klientów specyficznych dla produktu w prawej kolumnie. |
| `displayCustomerAccount` | Renderuje zawartość w panelu „Moje konto” klienta. | Dodaje link lub blok do „Moich zdjęć” i „Moich filmów” dla zalogowanego klienta. |
| `displayRightColumn` | Renderuje zawartość w prawej kolumnie ogólnych stron sklepu. | Wyświetla blok ostatnich zdjęć klientów w prawej kolumnie. |
| `displayMyAccountBlockFooter` | Renderuje zawartość w stopce bloku „Moje konto”. | Dodaje link do „Moich zdjęć” w bloku „Moje konto”, często w stopce. |
| `displayProductFooter` | Renderuje zawartość w obszarze stopki strony produktu. | Wyświetla blok zdjęć klientów specyficznych dla produktu w stopce produktu. |
| `displayProductTabContent` | Renderuje zawartość zakładki produktu. | Wyświetla zawartość galerii w zakładce „Zdjęcia klientów” na stronach produktów. |
| `displayLeftColumnProduct` | Renderuje zawartość w lewej kolumnie strony produktu. | Wyświetla blok zdjęć klientów specyficznych dla produktu w lewej kolumnie. |
| `displayLeftColumn` | Renderuje zawartość w lewej kolumnie ogólnych stron sklepu. | Wyświetla blok ostatnich zdjęć klientów w lewej kolumnie. |
| `displayHome` | Renderuje zawartość na stronie głównej sklepu. | Wyświetla blok ostatnich lub popularnych zdjęć klientów na stronie głównej. |
| `displayHeader` | Renderuje zawartość w sekcji `<head>` wszystkich stron. | Wstrzykuje pliki CSS i JavaScript wymagane przez moduł w całym sklepie. |
| `displayMyAccountBlock` | Renderuje zawartość w bloku „Moje konto” (np. w kolumnach bocznych). | Dodaje link do „Moich zdjęć” w bloku „Moje konto”. |
| `displayProductTab` | Renderuje nagłówek zakładki dla zakładki produktu. | Wyświetla tytuł zakładki „Zdjęcia klientów” na stronach produktów. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i profesjonalne wsparcie, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnienie płynnego działania i ciągłego ulepszania Twoich modułów PrestaShop.
