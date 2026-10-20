---
title: "LLMS.txt Generator Pro - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop LLMS.txt Generator Pro od MyPresta.eu."
sidebar:
  label: "LLMS.txt Generator Pro - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł LLMS.txt Generator Pro na MyPresta.eu](https://mypresta.eu/modules/seo/llmstxt-generator-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/seo/llmstxt-generator-pro/)
>
> ---


# LLMS.txt Generator Pro

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL). Twój serwer musi również zezwalać na zapisywanie plików w katalogu głównym, aby plik `llms.txt` mógł zostać wygenerowany.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > LLMS.txt Generator Pro)

To jest główny panel sterowania dla Twojego modułu LLMS.txt Generator Pro. Tutaj zdefiniujesz, jak generowany jest Twój plik `llms.txt` i jakie treści zawiera.

#### Ustawienia ogólne

- **Włącz generowanie LLMS.txt:**

  - **Co robi to ustawienie:** To jest główny przełącznik do aktywacji lub dezaktywacji podstawowej funkcjonalności modułu.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Moduł będzie generować i udostępniać plik `llms.txt` zgodnie z Twoimi ustawieniami. Crawlery AI będą miały do niego dostęp.
    - *Gdy wyłączone:* Plik `llms.txt` nie będzie generowany ani udostępniany przez moduł. Crawlery AI nie otrzymają konkretnych wskazówek z Twojego sklepu.
  - **Zalecana wartość:** TAK
  - **Scenariusz / przykład dla sprzedawcy:** Właśnie zainstalowałeś moduł i chcesz zacząć kierować boty AI. Włącz to. Jeśli musisz tymczasowo wstrzymać wskazówki AI z powodu konserwacji, możesz to wyłączyć tutaj.
- **Typ pliku LLMS.txt:**

  - **Co robi to ustawienie:** Określa, czy plik `llms.txt` jest generowany jako plik statyczny (zapisywany na Twoim serwerze) czy dynamicznie udostępniany na żądanie.
  - **Efekt zmiany tego ustawienia:**
    - *Statyczny:* Moduł zapisuje fizyczny plik `llms.txt` w katalogu głównym Twojego sklepu. Jest to zazwyczaj szybsze dla botów AI, ponieważ nie wymaga przetwarzania PHP przy każdym żądaniu.
    - *Dynamiczny:* Plik `llms.txt` jest generowany przez kod PHP PrestaShop za każdym razem, gdy bot AI go żąda. Zapewnia to najbardziej aktualne treści, ale może być nieco wolniejsze.
  - **Zalecana wartość:** Statyczny (dla wydajności, chyba że masz częste, w czasie rzeczywistym zmiany treści, które muszą być natychmiast odzwierciedlone).
  - **Scenariusz / przykład dla sprzedawcy:** Dla większości sklepów statyczny jest w porządku. Jeśli masz sklep o bardzo dużym ruchu z ciągle zmieniającymi się cenami produktów lub stanem magazynowym, dynamiczny może być preferowany, ale rozważ wpływ na wydajność.
- **Generuj llms-full.txt:**

  - **Co robi to ustawienie:** Kontroluje, czy generowany jest również dodatkowy, bardziej kompleksowy plik `llms-full.txt`. Ten plik zazwyczaj zawiera bardziej szczegółowe lub mniej ograniczone informacje niż standardowy `llms.txt`.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Plik `llms-full.txt` zostanie utworzony obok `llms.txt`, oferując crawlerom AI bogatszy zestaw danych.
    - *Gdy wyłączone:* Zostanie wygenerowany tylko standardowy plik `llms.txt`.
  - **Zalecana wartość:** TAK (aby dostarczyć maksymalną ilość danych do AI, chyba że masz konkretne powody, aby je ograniczyć).
  - **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby modele AI miały dostęp do jak największej ilości istotnych informacji o Twoich produktach, w tym potencjalnie mniej krytycznych, ale nadal użytecznych szczegółów.
- **Uwzględnij strony produktów:**

  - **Co robi to ustawienie:** Określa, czy poszczególne strony produktów są wymienione w pliku `llms.txt`.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Adresy URL wszystkich Twoich aktywnych stron produktów zostaną uwzględnione, co sprawi, że będą wykrywalne przez AI.
    - *Gdy wyłączone:* Strony produktów zostaną wykluczone, co oznacza, że boty AI nie będą do nich jawnie kierowane za pośrednictwem `llms.txt`.
  - **Zalecana wartość:** TAK (Produkty są zazwyczaj rdzeniem sklepu e-commerce).
  - **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby AI pomagała klientom znaleźć konkretne produkty.
- **Uwzględnij strony kategorii:**

  - **Co robi to ustawienie:** Określa, czy strony kategorii (listujące grupy produktów) są wymienione w pliku `llms.txt`.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Adresy URL wszystkich Twoich aktywnych stron kategorii zostaną uwzględnione.
    - *Gdy wyłączone:* Strony kategorii zostaną wykluczone.
  - **Zalecana wartość:** TAK (Kategorie pomagają AI zrozumieć strukturę Twojego sklepu).
  - **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby AI rozumiała różne typy produktów, które sprzedajesz, i kierowała klientów do odpowiednich sekcji.
- **Uwzględnij strony CMS:**

  - **Co robi to ustawienie:** Określa, czy Twoje strony systemu zarządzania treścią (CMS) (np. O nas, Kontakt, Informacje o wysyłce, Polityka prywatności) są wymienione.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Adresy URL aktywnych stron CMS zostaną uwzględnione.
    - *Gdy wyłączone:* Strony CMS zostaną wykluczone.
  - **Zalecana wartość:** TAK (Ważne, aby AI rozumiała Twoją firmę i polityki).
  - **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby AI mogła odpowiadać na pytania dotyczące polityki lub historii Twojego sklepu.
- **Uwzględnij strony producentów/marek:**

  - **Co robi to ustawienie:** Określa, czy strony poświęcone konkretnym producentom lub markom są wymienione.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Adresy URL aktywnych stron producentów/marek zostaną uwzględnione.
    - *Gdy wyłączone:* Strony producentów/marek zostaną wykluczone.
  - **Zalecana wartość:** TAK (Jeśli marki są ważne dla Twojej oferty produktowej).
  - **Scenariusz / przykład dla sprzedawcy:** Sprzedajesz produkty znanych marek i chcesz, aby AI to rozpoznawała.
- **Uwzględnij strony dostawców:**

  - **Co robi to ustawienie:** Określa, czy strony poświęcone konkretnym dostawcom są wymienione. (Mniej powszechne dla widoczności w front-office, często używane do celów wewnętrznych).
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Adresy URL aktywnych stron dostawców zostaną uwzględnione.
    - *Gdy wyłączone:* Strony dostawców zostaną wykluczone.
  - **Zalecana wartość:** NIE (Chyba że specjalnie promujesz dostawców w swoim front-office).
  - **Scenariusz / przykład dla sprzedawcy:** Masz unikalny model biznesowy, w którym dostawcy są widoczni publicznie i chcesz, aby AI ich indeksowała.
- **Uwzględnij stronę Nowe produkty:**

  - **Co robi to ustawienie:** Określa, czy strona z listą „Nowe produkty” jest uwzględniona.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Adres URL strony z nowymi produktami zostanie uwzględniony.
    - *Gdy wyłączone:* Strona z nowymi produktami zostanie wykluczona.
  - **Zalecana wartość:** TAK (Aby podkreślić Twoje najnowsze oferty dla AI).
  - **Scenariusz / przykład dla sprzedawcy:** Często dodajesz nowe produkty i chcesz, aby AI szybko o nich wiedziała.
- **Uwzględnij stronę Najlepsze wyprzedaże:**

  - **Co robi to ustawienie:** Określa, czy strona z listą „Najlepsze wyprzedaże” lub „Bestsellery” jest uwzględniona.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Adres URL strony z najlepszymi wyprzedażami zostanie uwzględniony.
    - *Gdy wyłączone:* Strona z najlepszymi wyprzedażami zostanie wykluczona.
  - **Zalecana wartość:** TAK (Aby promować Twoje najpopularniejsze produkty).
  - **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby AI rekomendowała Twoje najlepiej sprzedające się produkty klientom.
- **Uwzględnij stronę Spadek cen:**

  - **Co robi to ustawienie:** Określa, czy strona z listą „Spadek cen” lub „W promocji” jest uwzględniona.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Adres URL strony ze spadkiem cen zostanie uwzględniony.
    - *Gdy wyłączone:* Strona ze spadkiem cen zostanie wykluczona.
  - **Zalecana wartość:** TAK (Aby podkreślić Twoje przecenione produkty).
  - **Scenariusz / przykład dla sprzedawcy:** Prowadzisz promocje i chcesz, aby AI informowała klientów o aktualnych ofertach.
- **Uwzględnij stronę Kontakt:**

  - **Co robi to ustawienie:** Określa, czy strona kontaktowa Twojego sklepu jest uwzględniona.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Adres URL strony kontaktowej zostanie uwzględniony.
    - *Gdy wyłączone:* Strona kontaktowa zostanie wykluczona.
  - **Zalecana wartość:** TAK (Niezbędne, aby AI dostarczała informacji o obsłudze klienta).
  - **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby AI mogła informować klientów, jak skontaktować się z Twoim zespołem wsparcia.
- **Uwzględnij stronę mapy witryny:**

  - **Co robi to ustawienie:** Określa, czy główna strona mapy witryny Twojego sklepu (jeśli ją masz) jest uwzględniona.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Adres URL strony mapy witryny zostanie uwzględniony.
    - *Gdy wyłączone:* Strona mapy witryny zostanie wykluczona.
  - **Zalecana wartość:** TAK (Może pomóc AI odkryć więcej treści, podobnie jak mapy witryn dla wyszukiwarek).
  - **Scenariusz / przykład dla sprzedawcy:** Chcesz zapewnić AI kompleksowy przegląd struktury Twojego sklepu.
- **Uwzględnij niestandardowe adresy URL:**

  - **Co robi to ustawienie:** Pozwala ręcznie dodać konkretne adresy URL, które nie są automatycznie generowane przez PrestaShop, ale nadal chcesz, aby AI je odkrywała.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Pojawi się pole tekstowe, w którym możesz wymienić jeden adres URL na linię. Te adresy URL zostaną dodane do Twojego pliku `llms.txt`.
    - *Gdy wyłączone:* Nie zostaną dodane żadne niestandardowe adresy URL.
  - **Zalecana wartość:** TAK (Jeśli masz ważne statyczne strony lub wpisy na blogu poza podstawową strukturą PrestaShop).
  - **Scenariusz / przykład dla sprzedawcy:** Masz oddzielny blog na subdomenie lub konkretne strony docelowe, które chcesz, aby AI indeksowała.
- **Wyklucz konkretne adresy URL:**

  - **Co robi to ustawienie:** Pozwala ręcznie określić adresy URL, które *nie* powinny być uwzględnione w pliku `llms.txt`, nawet jeśli w innym przypadku zostałyby wygenerowane.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Pojawi się pole tekstowe, w którym możesz wymienić jeden adres URL na linię. Te adresy URL zostaną jawnie wykluczone.
    - *Gdy wyłączone:* Żadne adresy URL nie zostaną jawnie wykluczone przez to ustawienie.
  - **Zalecana wartość:** Używaj w razie potrzeby dla stron wrażliwych lub nieistotnych.
  - **Scenariusz / przykład dla sprzedawcy:** Masz wewnętrzne strony testowe, nieaktualne promocje lub strony z wrażliwymi danymi klientów, do których absolutnie nie chcesz, aby AI miała dostęp.
- **Wyklucz produkty według kategorii:**

  - **Co robi to ustawienie:** Zapewnia sposób na wykluczenie wszystkich produktów należących do określonych kategorii z pliku `llms.txt`.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Pojawi się lista Twoich kategorii, umożliwiając wybór tych, które mają zostać wykluczone. Wszystkie produkty w wybranych kategoriach zostaną pominięte.
    - *Gdy wyłączone:* Wszystkie produkty zostaną uwzględnione, niezależnie od kategorii.
  - **Zalecana wartość:** Używaj w razie potrzeby.
  - **Scenariusz / przykład dla sprzedawcy:** Sprzedajesz zarówno produkty publiczne, jak i szereg produktów tylko dla B2B w określonej kategorii, których nie chcesz, aby AI indeksowała dla ogólnego wyszukiwania publicznego.
- **Wyklucz produkty według producenta:**

  - **Co robi to ustawienie:** Pozwala wykluczyć wszystkie produkty od określonych producentów.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Pojawi się lista Twoich producentów do wyboru. Produkty od wybranych producentów zostaną pominięte.
    - *Gdy wyłączone:* Wszystkie produkty zostaną uwzględnione, niezależnie od producenta.
  - **Zalecana wartość:** Używaj w razie potrzeby.
  - **Scenariusz / przykład dla sprzedawcy:** Tymczasowo przestałeś sprzedawać produkty określonej marki i nie chcesz, aby AI je wyświetlała, nawet jeśli nadal znajdują się w Twoim katalogu.
- **Wyklucz produkty według dostawcy:**

  - **Co robi to ustawienie:** Pozwala wykluczyć wszystkie produkty od określonych dostawców.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Pojawi się lista Twoich dostawców do wyboru. Produkty od wybranych dostawców zostaną pominięte.
    - *Gdy wyłączone:* Wszystkie produkty zostaną uwzględnione, niezależnie od dostawcy.
  - **Zalecana wartość:** Używaj w razie potrzeby.
  - **Scenariusz / przykład dla sprzedawcy:** Masz dostawcę, którego produkty nie są przeznaczone do publicznego indeksowania przez AI.
- **Wyklucz produkty według cechy:**

  - **Co robi to ustawienie:** Pozwala wykluczyć produkty na podstawie określonych cech produktu (np. „Kolor: Czerwony”, „Materiał: Drewno”).
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Możesz wybrać cechy i ich wartości. Produkty pasujące do tych cech zostaną pominięte.
    - *Gdy wyłączone:* Cechy produktu nie będą używane do wykluczenia.
  - **Zalecana wartość:** Używaj w razie potrzeby.
  - **Scenariusz / przykład dla sprzedawcy:** Masz produkty oznaczone cechą „Wycofane”, które chcesz ukryć przed AI.
- **Wyklucz produkty według atrybutu:**

  - **Co robi to ustawienie:** Pozwala wykluczyć produkty na podstawie określonych atrybutów produktu (np. „Rozmiar: XL”, „Waga: 1kg”).
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Możesz wybrać atrybuty i ich wartości. Produkty pasujące do tych atrybutów zostaną pominięte.
    - *Gdy wyłączone:* Atrybuty produktu nie będą używane do wykluczenia.
  - **Zalecana wartość:** Używaj w razie potrzeby.
  - **Scenariusz / przykład dla sprzedawcy:** Masz produkty z kombinacją atrybutów „Brak w magazynie”, których nie chcesz, aby AI wyświetlała.
- **Wyklucz produkty według zakresu cen:**

  - **Co robi to ustawienie:** Pozwala wykluczyć produkty, które mieszczą się w określonym zakresie cenowym.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Możesz wprowadzić cenę minimalną i maksymalną. Produkty z cenami w tym zakresie zostaną pominięte.
    - *Gdy wyłączone:* Ceny produktów nie będą używane do wykluczenia.
  - **Zalecana wartość:** Używaj w razie potrzeby.
  - **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby AI indeksowała tylko Twoje produkty premium (np. wyklucz produkty poniżej 10 USD).
- **Wyklucz produkty według ilości w magazynie:**

  - **Co robi to ustawienie:** Pozwala wykluczyć produkty na podstawie ich aktualnej ilości w magazynie.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Możesz ustawić minimalną ilość w magazynie. Produkty z ilością poniżej tej wartości zostaną pominięte.
    - *Gdy wyłączone:* Ilość w magazynie produktu nie będzie używana do wykluczenia.
  - **Zalecana wartość:** TAK (Wyklucz produkty z 0 sztuk w magazynie, aby uniknąć rekomendowania przez AI niedostępnych pozycji).
  - **Scenariusz / przykład dla sprzedawcy:** Nie chcesz, aby AI wyświetlała produkty, których nie ma w magazynie. Ustaw to, aby wykluczyć produkty z ilością w magazynie <= 0.
- **Wyklucz produkty według widoczności:**

  - **Co robi to ustawienie:** Pozwala wykluczyć produkty na podstawie ich ustawienia widoczności w PrestaShop (np. „Tylko katalog”, „Tylko wyszukiwanie”, „Wszędzie”).
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Możesz wybrać, które opcje widoczności mają zostać wykluczone. Produkty pasujące do tych opcji zostaną pominięte.
    - *Gdy wyłączone:* Widoczność produktu nie będzie używana do wykluczenia.
  - **Zalecana wartość:** Używaj w razie potrzeby.
  - **Scenariusz / przykład dla sprzedawcy:** Masz produkty ustawione na „Tylko katalog” (nie do wyszukiwania), które również chcesz ukryć przed AI.
- **Wyklucz produkty według statusu:**

  - **Co robi to ustawienie:** Pozwala wykluczyć produkty na podstawie ich statusu aktywnego/nieaktywnego.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Możesz wybrać wykluczenie nieaktywnych produktów.
    - *Gdy wyłączone:* Zarówno aktywne, jak i nieaktywne produkty zostaną uwzględnione.
  - **Zalecana wartość:** TAK (Wyklucz nieaktywne produkty).
  - **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby AI wyświetlała tylko aktualnie dostępne i aktywne produkty.
- **Wyklucz produkty według daty dodania:**

  - **Co robi to ustawienie:** Pozwala wykluczyć produkty na podstawie daty ich dodania do Twojego sklepu.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Możesz ustawić zakres dat. Produkty dodane poza tym zakresem zostaną pominięte.
    - *Gdy wyłączone:* Data dodania produktu nie będzie używana do wykluczenia.
  - **Zalecana wartość:** Używaj w razie potrzeby.
  - **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby AI indeksowała tylko produkty dodane w ciągu ostatniego roku.
- **Wyklucz produkty według daty aktualizacji:**

  - **Co robi to ustawienie:** Pozwala wykluczyć produkty na podstawie daty ich ostatniej aktualizacji.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Możesz ustawić zakres dat. Produkty zaktualizowane poza tym zakresem zostaną pominięte.
    - *Gdy wyłączone:* Data aktualizacji produktu nie będzie używana do wykluczenia.
  - **Zalecana wartość:** Używaj w razie potrzeby.
  - **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby AI indeksowała tylko produkty, które zostały niedawno zaktualizowane lub sprawdzone.
- **Wyklucz produkty według konkretnych identyfikatorów produktów:**

  - **Co robi to ustawienie:** Pozwala ręcznie wprowadzić listę konkretnych identyfikatorów produktów, oddzielonych przecinkami, które mają zostać wykluczone.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Produkty o określonych identyfikatorach zostaną pominięte.
    - *Gdy wyłączone:* Żadne produkty nie zostaną wykluczone według identyfikatora.
  - **Zalecana wartość:** Używaj w razie potrzeby.
  - **Scenariusz / przykład dla sprzedawcy:** Masz kilka konkretnych produktów, które są problematyczne lub wrażliwe i nigdy nie mogą być indeksowane przez AI.

#### Ustawienia zaawansowane

- **Harmonogram regeneracji (Cron Job):**

  - **Co robi to ustawienie:** Definiuje, jak często plik `llms.txt` powinien być automatycznie regenerowany. Jest to kluczowe dla utrzymania aktualności pliku bez ręcznej interwencji.
  - **Efekt zmiany tego ustawienia:**
    - *Codziennie / Co tydzień / Co miesiąc:* Moduł udostępni adres URL zadania cron. Gdy ten adres URL zostanie wywołany (np. przez usługę cron Twojego dostawcy hostingu), plik `llms.txt` (i `llms-full.txt`) zostanie przebudowany.
    - *Ręcznie:* Będziesz musiał ręcznie kliknąć przycisk „Generuj LLMS.txt” za każdym razem, gdy chcesz zaktualizować plik.
  - **Zalecana wartość:** Codziennie (dla większości aktywnych sklepów).
  - **Scenariusz / przykład dla sprzedawcy:** Regularnie dodajesz nowe produkty lub aktualizujesz ceny. Ustawienie codziennej regeneracji zapewnia, że crawlery AI zawsze otrzymują najnowsze informacje. Moduł wyświetli adres URL cron, który musisz skonfigurować na swoim serwerze.
- **Obsługa Multistore:**

  - **Co robi to ustawienie:** Jeśli prowadzisz PrestaShop Multistore, ta opcja pozwala generować oddzielne pliki `llms.txt` dla każdego z Twoich sklepów lub pojedynczy plik dla wszystkich sklepów.
  - **Efekt zmiany tego ustawienia:**
    - *Włączone:* Moduł będzie respektować Twój kontekst Multistore i generować pliki specyficzne dla treści każdego sklepu.
    - *Wyłączone:* Moduł może generować pojedynczy plik na podstawie domyślnego sklepu lub zachowywać się nieoczekiwanie w środowisku Multistore.
  - **Zalecana wartość:** TAK (jeśli używasz Multistore).
  - **Scenariusz / przykład dla sprzedawcy:** Masz różne katalogi produktów lub języki dla każdego sklepu w konfiguracji Multistore i potrzebujesz odrębnych plików `llms.txt` dla każdego z nich.
- **Czas życia pamięci podręcznej (minuty):**

  - **Co robi to ustawienie:** Określa, jak długo wygenerowany plik `llms.txt` jest przechowywany w pamięci podręcznej, zanim zostanie uznany za „nieaktualny” i będzie wymagał regeneracji (dla dynamicznego typu pliku).
  - **Efekt zmiany tego ustawienia:**
    - *Wyższa wartość:* Rzadsza regeneracja, potencjalnie szybsza dla botów AI, ale treść może być nieco starsza.
    - *Niższa wartość:* Częstsza regeneracja, zapewniająca świeższe treści, ale potencjalnie większe obciążenie serwera.
  - **Zalecana wartość:** 60 (1 godzina) dla dynamicznego, lub nieistotne dla statycznego.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli używasz dynamicznego generowania, a Twoje dane produktów zmieniają się co godzinę, ustaw to na 60. Jeśli zmiany są rzadsze, możesz to zwiększyć.
- **Włącz analizy i śledzenie botów:**

  - **Co robi to ustawienie:** Aktywuje funkcję śledzenia, kiedy boty AI uzyskują dostęp do Twojego pliku `llms.txt`, dostarczając wglądu w ich aktywność.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Moduł będzie rejestrować dostęp do pliku `llms.txt`, co można przeglądać w panelu modułu.
    - *Gdy wyłączone:* Nie będą zbierane żadne dane dotyczące dostępu botów.
  - **Zalecana wartość:** TAK (Przydatne do zrozumienia aktywności crawlera AI).
  - **Scenariusz / przykład dla sprzedawcy:** Chcesz zobaczyć, jak często modele AI indeksują Twój sklep i które z nich są najbardziej aktywne.
- **Przycisk Wyczyść pamięć podręczną:**

  - **Co robi to ustawienie:** Ręczny przycisk do czyszczenia wszelkich buforowanych plików `llms.txt`.
  - **Efekt zmiany tego ustawienia:** Natychmiast usuwa wszelkie przechowywane pliki `llms.txt`, wymuszając świeżą regenerację przy następnym żądaniu (dla dynamicznego) lub po kliknięciu przycisku „Generuj LLMS.txt” (dla statycznego).
  - **Zalecana wartość:** Kliknij, gdy wprowadzasz znaczące zmiany w ustawieniach lub katalogu produktów i chcesz upewnić się, że plik `llms.txt` zostanie natychmiast zaktualizowany.
  - **Scenariusz / przykład dla sprzedawcy:** Właśnie dodałeś nową, dużą linię produktów i chcesz, aby AI natychmiast ją odkryła, więc czyścisz pamięć podręczną i regenerujesz.
- **Przycisk Generuj LLMS.txt:**

  - **Co robi to ustawienie:** Ręczny przycisk do natychmiastowego generowania lub regenerowania pliku `llms.txt` na podstawie Twoich bieżących ustawień.
  - **Efekt zmiany tego ustawienia:** Moduł przetwarza Twój katalog i ustawienia, a następnie tworzy lub aktualizuje plik `llms.txt`.
  - **Zalecana wartość:** Kliknij po wprowadzeniu jakichkolwiek zmian w konfiguracji lub gdy potrzebujesz natychmiastowej aktualizacji, zwłaszcza jeśli używasz statycznego generowania plików.
  - **Scenariusz / przykład dla sprzedawcy:** Zakończyłeś konfigurowanie wszystkich reguł wykluczeń i chcesz utworzyć początkowy plik `llms.txt`.

#### Nadpisywanie dla poszczególnych produktów (Strona produktu w panelu administracyjnym)

Moduł integruje się również bezpośrednio ze stronami edycji produktów w Panelu administracyjnym.

- **Wyklucz ten produkt z LLMS.txt:**
  - **Co robi to ustawienie:** Pole wyboru na poszczególnych stronach produktów, które pozwala nadpisać globalne ustawienia i konkretnie wykluczyć pojedynczy produkt z pliku `llms.txt`.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy zaznaczone:* Ten konkretny produkt nie zostanie uwzględniony w pliku `llms.txt`, niezależnie od innych globalnych reguł włączenia.
    - *Gdy odznaczone:* Włączenie produktu zostanie określone przez ustawienia globalne.
  - **Zalecana wartość:** Używaj w razie potrzeby dla konkretnych produktów.
  - **Scenariusz / przykład dla sprzedawcy:** Masz produkt, który jest tymczasowo niedostępny, lub bardzo niszowy przedmiot, którego nie chcesz, aby AI szeroko promowała.

#### Nadpisywanie dla poszczególnych kategorii (Strona kategorii w panelu administracyjnym)

Podobnie, moduł integruje się ze stronami edycji kategorii.

- **Wyklucz tę kategorię z LLMS.txt:**
  - **Co robi to ustawienie:** Pole wyboru na poszczególnych stronach kategorii, które pozwala nadpisać globalne ustawienia i konkretnie wykluczyć całą kategorię (i jej produkty) z pliku `llms.txt`.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy zaznaczone:* Ta konkretna kategoria i wszystkie produkty w niej nie zostaną uwzględnione w pliku `llms.txt`.
    - *Gdy odznaczone:* Włączenie kategorii zostanie określone przez ustawienia globalne.
  - **Zalecana wartość:** Używaj w razie potrzeby dla konkretnych kategorii.
  - **Scenariusz / przykład dla sprzedawcy:** Masz kategorię „Wyprzedaż”, która często się zmienia i wolisz, aby AI jej nie indeksowała, lub kategorię do użytku wewnętrznego.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### Panel (Panel administracyjny > Moduły > LLMS.txt Generator Pro > Panel)

- **Nazwa ekranu i lokalizacja w menu:** Ten ekran jest dostępny z głównej strony konfiguracji modułu, zazwyczaj za pośrednictwem zakładki lub linku „Panel”. Zapewnia przegląd aktywności botów AI i statusu modułu.
- **Dostępne działania i ustawienia:**
  - **Analiza ruchu botów:** Wyświetla wykresy lub tabele pokazujące, które crawlery AI (user agents) uzyskały dostęp do Twojego pliku `llms.txt`, jak często i kiedy.
  - **Status ostatniego generowania:** Pokazuje, kiedy plik `llms.txt` został ostatnio wygenerowany, jego rozmiar i liczbę uwzględnionych adresów URL.
  - **Dzienniki błędów:** Wszelkie problemy napotkane podczas generowania zostaną wyświetlone tutaj.
- **Efekt zmian:** Ten ekran służy przede wszystkim do monitorowania i raportowania. Zmiany tutaj są zazwyczaj związane z przeglądaniem danych, a nie zmienianiem zachowania sklepu.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Okresowo sprawdzaj panel, aby upewnić się, że plik `llms.txt` jest dostępny dla botów AI zgodnie z oczekiwaniami i monitoruj ewentualne błędy. Pomaga to zrozumieć wpływ Twojej strategii widoczności w AI.

#### Podgląd (Panel administracyjny > Moduły > LLMS.txt Generator Pro > Podgląd)

- **Nazwa ekranu i lokalizacja w menu:** Dostępny z głównej strony konfiguracji modułu, zazwyczaj za pośrednictwem zakładki lub linku „Podgląd”.
- **Dostępne działania i ustawienia:**
  - **Wyświetlanie zawartości LLMS.txt:** Pokazuje rzeczywistą zawartość pliku `llms.txt`, która zostałaby udostępniona crawlerom AI, na podstawie Twoich bieżących ustawień.
  - **Wyświetlanie zawartości llms-full.txt:** Jeśli włączone, pokazuje również zawartość pliku `llms-full.txt`.
- **Efekt zmian:** Ten ekran służy do weryfikacji. Pozwala przeglądać wygenerowaną zawartość przed jej uruchomieniem lub po wprowadzeniu zmian, upewniając się, że spełnia Twoje wymagania.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Po wprowadzeniu znaczących zmian w ustawieniach modułu lub katalogu produktów, użyj ekranu podglądu, aby zweryfikować, czy prawidłowe adresy URL są uwzględnione i wykluczone.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz generowanie LLMS.txt | TAK | Aktywuje/dezaktywuje podstawową funkcję modułu. |
| Konfiguracja modułu | Typ pliku LLMS.txt | Statyczny | Wybierz statyczny dla wydajności, dynamiczny dla aktualizacji w czasie rzeczywistym. |
| Konfiguracja modułu | Generuj llms-full.txt | TAK | Zapewnia bardziej kompleksowy plik dla AI. |
| Konfiguracja modułu | Uwzględnij strony produktów | TAK | Sprawia, że adresy URL produktów są wykrywalne przez AI. |
| Konfiguracja modułu | Uwzględnij strony kategorii | TAK | Sprawia, że adresy URL kategorii są wykrywalne przez AI. |
| Konfiguracja modułu | Uwzględnij strony CMS | TAK | Sprawia, że strony informacyjne są wykrywalne przez AI. |
| Konfiguracja modułu | Uwzględnij strony producentów/marek | TAK | Sprawia, że strony marek są wykrywalne przez AI. |
| Konfiguracja modułu | Uwzględnij strony dostawców | NIE | Zazwyczaj niepotrzebne do publicznego indeksowania przez AI. |
| Konfiguracja modułu | Uwzględnij stronę Nowe produkty | TAK | Podkreśla najnowsze produkty dla AI. |
| Konfiguracja modułu | Uwzględnij stronę Najlepsze wyprzedaże | TAK | Promuje najlepiej sprzedające się produkty dla AI. |
| Konfiguracja modułu | Uwzględnij stronę Spadek cen | TAK | Podkreśla przecenione produkty dla AI. |
| Konfiguracja modułu | Uwzględnij stronę Kontakt | TAK | Dostarcza informacje kontaktowe dla AI. |
| Konfiguracja modułu | Uwzględnij stronę mapy witryny | TAK | Pomaga AI odkryć więcej treści. |
| Konfiguracja modułu | Uwzględnij niestandardowe adresy URL | Używaj w razie potrzeby | Dodaj konkretne adresy URL spoza PrestaShop. |
| Konfiguracja modułu | Wyklucz konkretne adresy URL | Używaj w razie potrzeby | Ukryj wrażliwe lub nieistotne adresy URL. |
| Konfiguracja modułu | Wyklucz produkty według kategorii | Używaj w razie potrzeby | Filtruj produkty według kategorii. |
| Konfiguracja modułu | Wyklucz produkty według producenta | Używaj w razie potrzeby | Filtruj produkty według producenta. |
| Konfiguracja modułu | Wyklucz produkty według dostawcy | Używaj w razie potrzeby | Filtruj produkty według dostawcy. |
| Konfiguracja modułu | Wyklucz produkty według cechy | Używaj w razie potrzeby | Filtruj produkty według konkretnych cech. |
| Konfiguracja modułu | Wyklucz produkty według atrybutu | Używaj w razie potrzeby | Filtruj produkty według konkretnych atrybutów. |
| Konfiguracja modułu | Wyklucz produkty według zakresu cen | Używaj w razie potrzeby | Filtruj produkty w określonym zakresie cen. |
| Konfiguracja modułu | Wyklucz produkty według ilości w magazynie | TAK (<=0) | Ukryj produkty niedostępne w magazynie przed AI. |
| Konfiguracja modułu | Wyklucz produkty według widoczności | Używaj w razie potrzeby | Filtruj produkty według widoczności w PrestaShop. |
| Konfiguracja modułu | Wyklucz produkty według statusu | TAK (nieaktywne) | Ukryj nieaktywne produkty przed AI. |
| Konfiguracja modułu | Wyklucz produkty według daty dodania | Używaj w razie potrzeby | Filtruj produkty według daty utworzenia. |
| Konfiguracja modułu | Wyklucz produkty według daty aktualizacji | Używaj w razie potrzeby | Filtruj produkty według daty ostatniej aktualizacji. |
| Konfiguracja modułu | Wyklucz produkty według konkretnych identyfikatorów produktów | Używaj w razie potrzeby | Wyklucz pojedyncze produkty według identyfikatora. |
| Konfiguracja modułu | Harmonogram regeneracji (Cron Job) | Codziennie | Automatyzuje aktualizacje `llms.txt`. |
| Konfiguracja modułu | Obsługa Multistore | TAK (jeśli dotyczy) | Umożliwia odrębne pliki dla każdego sklepu. |
| Konfiguracja modułu | Czas życia pamięci podręcznej (minuty) | 60 (dla dynamicznego) | Ustawia, jak długo dynamiczny plik jest buforowany. |
| Konfiguracja modułu | Włącz analizy i śledzenie botów | TAK | Monitoruje aktywność crawlera AI. |
| Konfiguracja modułu | Przycisk Wyczyść pamięć podręczną | Kliknij w razie potrzeby | Wymusza czyszczenie pamięci podręcznej dla natychmiastowych aktualizacji. |
| Konfiguracja modułu | Przycisk Generuj LLMS.txt | Kliknij w razie potrzeby | Ręcznie generuje plik `llms.txt`. |
| Strona edycji produktu | Wyklucz ten produkt z LLMS.txt | Odznaczone | Nadpisuje globalne ustawienia dla pojedynczego produktu. |
| Strona edycji kategorii | Wyklucz tę kategorię z LLMS.txt | Odznaczone | Nadpisuje globalne ustawienia dla całej kategorii. |
| Panel | Analiza ruchu botów | N/A | Monitoruje dostęp botów AI. |
| Panel | Status ostatniego generowania | N/A | Pokazuje status pliku `llms.txt`. |
| Podgląd | Wyświetlanie zawartości LLMS.txt | N/A | Pokazuje wygenerowaną zawartość `llms.txt`. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Mój plik `llms.txt` nie pojawia się ani nie aktualizuje.**
O:

1.  **Sprawdź „Włącz generowanie LLMS.txt”:** Upewnij się, że jest ustawione na TAK w konfiguracji modułu.
2.  **Sprawdź typ pliku:** Jeśli ustawiono na „Statyczny”, upewnij się, że Twój serwer ma uprawnienia do zapisu w katalogu głównym PrestaShop. Ponadto ręcznie kliknij przycisk „Generuj LLMS.txt”.
3.  **Zadanie Cron:** Jeśli używasz zadania cron, sprawdź, czy jest ono poprawnie skonfigurowane na Twoim hostingu i czy adres URL podany przez moduł jest dostępny.
4.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** w PrestaShop i wyczyść pamięć podręczną Smarty. Następnie spróbuj ponownie wygenerować plik `llms.txt`.
5.  **Panel modułu:** Sprawdź panel modułu pod kątem wszelkich komunikatów o błędach podczas generowania.

**P: Wprowadziłem zmiany, ale plik `llms.txt` ich nie odzwierciedla.**
O:

1.  **Regeneruj ręcznie:** Kliknij przycisk „Generuj LLMS.txt” w konfiguracji modułu.
2.  **Czas zadania Cron:** Jeśli polegasz na zadaniu cron, pamiętaj, że działa ono tylko w zaplanowanych odstępach czasu. Twoje zmiany pojawią się po następnym zaplanowanym uruchomieniu.
3.  **Pamięć podręczna:** Jeśli używasz dynamicznego generowania, plik `llms.txt` może być buforowany. Kliknij przycisk „Wyczyść pamięć podręczną” w module lub wyczyść pamięć podręczną PrestaShop w **Zaawansowane > Wydajność**.

**P: Skąd mam wiedzieć, czy boty AI faktycznie używają mojego pliku `llms.txt`?**
O: Włącz „Analizy i śledzenie botów” w ustawieniach modułu. Panel modułu pokaże Ci statystyki dotyczące tego, które user agenty AI uzyskały dostęp do Twojego pliku `llms.txt` i kiedy.

**P: Plik `llms.txt` jest zbyt duży lub zawiera zbyt wiele nieistotnych adresów URL.**
O:

1.  **Przejrzyj ustawienia włączenia:** Przejrzyj opcje „Uwzględnij…” i wyłącz wszelkie typy treści, których nie chcesz, aby AI indeksowała (np. Strony dostawców).
2.  **Wykorzystaj filtry wykluczeń:** Intensywnie korzystaj z filtrów „Wyklucz produkty według…” (Kategoria, Stan magazynowy, Cena itp.) oraz „Wyklucz konkretne adresy URL”, aby precyzyjnie dostosować zawartość.
3.  **Nadpisywanie dla poszczególnych produktów/kategorii:** W bardzo specyficznych przypadkach użyj pól wyboru wykluczeń na poszczególnych stronach edycji produktów i kategorii.

**P: Mój niestandardowy motyw nie wyświetla poprawnie funkcji modułu (np. dodatkowych pól na stronie produktu).**
O: Integracja modułu ze stronami produktów/kategorii jest standardowa. Jeśli napotkasz problemy, prawdopodobnie jest to konflikt z Twoim niestandardowym motywem lub innym modułem, który mocno modyfikuje formularze edycji produktów/kategorii.

1.  **Sprawdź konflikty:** Tymczasowo wyłącz inne moduły, które modyfikują strony produktów/kategorii, aby sprawdzić, czy problem zostanie rozwiązany.
2.  **Nadpisywanie motywu:** Twój motyw może mieć nadpisania szablonów, które uniemożliwiają renderowanie dodatkowych pól modułu. Skontaktuj się z deweloperem motywu lub ekspertem PrestaShop, aby zbadać problem.
3.  **Wyczyść pamięć podręczną:** Zawsze czyść pamięć podręczną PrestaShop po zmianach motywu lub modułu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł LLMS.txt Generator Pro jest zgodny ze standardową architekturą modułów PrestaShop, wykorzystując zasady MVC. Działa głównie poprzez główną klasę modułu (`llmstxtpro/index.php`) do zarządzania konfiguracją i hookami, oraz zestaw dedykowanych klas (`classes/`) do logiki biznesowej, obsługi danych i generowania plików. Kontrolery front-office obsługują dynamiczne udostępnianie `llms.txt` i wykonywanie zadań cron. Konfiguracja jest przechowywana w `ps_configuration` i niestandardowych tabelach.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

Te kontrolery są odpowiedzialne za udostępnianie plików `llms.txt` i `llms-full.txt` oraz obsługę żądań zadań cron.

- `controllers/front/aicatalog.php`
  - **Nazwa klasy i klasa nadrzędna:** `LlmsTxtProAiCatalogModuleFrontController` rozszerzająca `ModuleFrontController`.
  - **Odpowiedzialność:** Prawdopodobnie obsługuje specyficzne żądania katalogu AI, potencjalnie dla bardziej ustrukturyzowanych formatów danych niż `llms.txt`. Może udostępniać reprezentację katalogu w formacie JSON lub XML do konsumpcji przez AI.
- `controllers/front/cron.php`
  - **Nazwa klasy i klasa nadrzędna:** `LlmsTxtProCronModuleFrontController` rozszerzająca `ModuleFrontController`.
  - **Odpowiedzialność:** Ten kontroler jest przeznaczony do wywoływania przez zadanie cron po stronie serwera. Po uzyskaniu dostępu, wyzwala proces regeneracji `llms.txt` (i `llms-full.txt`) na podstawie konfiguracji modułu. Zazwyczaj zwraca prosty komunikat o sukcesie/porażce.
- `controllers/front/index.php`
  - **Nazwa klasy i klasa nadrzędna:** `LlmsTxtProIndexModuleFrontController` rozszerzająca `ModuleFrontController`.
  - **Odpowiedzialność:** Może to być symbol zastępczy lub ogólny punkt wejścia. Biorąc pod uwagę inne specyficzne kontrolery, jest mniej prawdopodobne, aby miał bezpośrednią, unikalną funkcję dla samego generowania `llms.txt`, ale mógłby być używany do ogólnego routingu front-office modułu lub informacji.
- `controllers/front/llmsfull.php`
  - **Nazwa klasy i klasa nadrzędna:** `LlmsTxtProLlmsFullModuleFrontController` rozszerzająca `ModuleFrontController`.
  - **Odpowiedzialność:** Gdy typ pliku `llms-full.txt` jest ustawiony na dynamiczny, ten kontroler udostępnia zawartość pliku `llms-full.txt`. Odpytuje bazę danych i generuje pełną listę adresów URL i powiązanych danych.
- `controllers/front/llmstxt.php`
  - **Nazwa klasy i klasa nadrzędna:** `LlmsTxtProLlmsTxtModuleFrontController` rozszerzająca `ModuleFrontController`.
  - **Odpowiedzialność:** Gdy typ pliku `llms.txt` jest ustawiony na dynamiczny, ten kontroler udostępnia zawartość standardowego pliku `llms.txt`. Odpytuje bazę danych i generuje listę adresów URL na podstawie konfiguracji modułu i reguł wykluczeń.

#### Kontrolery administracyjne Back-Office

Moduł nie wydaje się mieć dedykowanych niestandardowych kontrolerów administracyjnych (`controllers/admin/`). Cała konfiguracja jest obsługiwana za pomocą metody `getContent()` głównego modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

- `classes/index.php`
  - **Odpowiedzialność:** Zazwyczaj pusty plik zapobiegający listowaniu katalogów, nie jest klasą funkcjonalną.
- `classes/LlmsTxtProAiCatalog.php`
  - **Odpowiedzialność:** Prawdopodobnie zawiera logikę generowania bardziej ustrukturyzowanego katalogu AI (np. JSON-LD, znaczników schema.org), który mógłby być udostępniany przez `aicatalog.php`. Zawierałby metody do odpytywania danych produktów, kategorii i CMS z formatowaniem specyficznym dla AI.
- `classes/LlmsTxtProAnalytics.php`
  - **Odpowiedzialność:** Obsługuje logowanie i pobieranie danych dostępu botów AI. Współpracowałby z niestandardową tabelą bazy danych do przechowywania informacji o user agencie, sygnaturze czasowej i dostępie do pliku (`llms.txt` lub `llms-full.txt`). Zapewnia metody do raportowania tych danych do panelu administracyjnego.
- `classes/LlmsTxtProConfig.php`
  - **Odpowiedzialność:** Klasa pomocnicza do zarządzania ustawieniami konfiguracji modułu. Zapewniałaby statyczne metody do pobierania i ustawiania wartości konfiguracyjnych z `Configuration::get()` i `Configuration::updateValue()`, potencjalnie z wartościami domyślnymi i rzutowaniem typów.
- `classes/LlmsTxtProGenerator.php`
  - **Odpowiedzialność:** Jest to klasa logiki rdzenia do generowania zawartości `llms.txt` i `llms-full.txt`. Zawiera metody do:
    - Pobierania produktów, kategorii, stron CMS, producentów, dostawców itp.
    - Stosowania wszystkich filtrów włączeń i wykluczeń (według kategorii, producenta, ceny, stanu magazynowego, niestandardowych adresów URL itp.).
    - Formatowania adresów URL zgodnie ze standardem `llms.txt`.
    - Obsługi zapisu plików statycznych do katalogu głównego.
    - Potencjalnie zarządzania buforowaniem dla dynamicznego generowania.
- `classes/LlmsTxtProLogger.php`
  - **Odpowiedzialność:** Klasa narzędziowa do logowania zdarzeń, ostrzeżeń lub błędów specyficznych dla modułu. Może zapisywać do niestandardowego pliku dziennika lub integrować się z domyślnym loggerem PrestaShop. Przydatna do debugowania problemów z generowaniem.

### 4.4 Zasoby JavaScript (`views/js/`)

- `llmstxtpro/lib/searchTool/views/js/autocomplete.js`
  - **Zakres:** Back-office.
  - **Odpowiedzialność:** Zapewnia funkcjonalność autouzupełniania dla pól wejściowych w konfiguracji administracyjnej, prawdopodobnie do wybierania produktów, kategorii, producentów lub konkretnych adresów URL do wykluczenia. Wiąże się z polami wejściowymi i wykonuje wywołania AJAX w celu pobrania sugestii.
- `llmstxtpro/views/js/adminLlmsTxtProDashboard.js`
  - **Zakres:** Back-office (ekran Panelu).
  - **Odpowiedzialność:** Obsługuje dynamiczne wyświetlanie danych analitycznych na panelu modułu. Może używać AJAX do pobierania statystyk ruchu botów z `LlmsTxtProAnalytics` i renderowania ich za pomocą bibliotek wykresów lub tabel danych.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `llmstxtpro/lib/searchTool/views/css/autocomplete.css`
  - **Zakres:** Back-office.
  - **Odpowiedzialność:** Stylizuje rozwijane listy autouzupełniania i sugestie używane w formularzach konfiguracji administracyjnej.
- `llmstxtpro/views/css/admin-config.css`
  - **Zakres:** Back-office (strona konfiguracji modułu).
  - **Odpowiedzialność:** Zapewnia specyficzne style dla głównego formularza konfiguracji modułu, zapewniając spójny i przyjazny dla użytkownika układ w Panelu administracyjnym PrestaShop.
- `llmstxtpro/views/css/admin-dashboard.css`
  - **Zakres:** Back-office (ekran Panelu).
  - **Odpowiedzialność:** Stylizuje elementy panelu, w tym wykresy, tabele i wskaźniki statusu dla analizy ruchu botów i statusu generowania.
- `llmstxtpro/views/css/admin-searchtool.css`
  - **Zakres:** Back-office.
  - **Odpowiedzialność:** Ogólne style dla komponentów interfejsu użytkownika związanych z wyszukiwaniem w panelu administracyjnym, potencjalnie współdzielone z `autocomplete.css` lub dla innych interfejsów wyszukiwania/filtrowania.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony hooków (`views/templates/hook/`)**: Opis modułu nie wymienia jawnie szablonów hooków, co sugeruje, że jego obecność w front-office jest przede wszystkim poprzez sam wygenerowany plik `llms.txt`, a nie elementy wizualne.
- **Szablony administracyjne (`views/templates/admin/`)**:
  - `llmstxtpro/views/templates/admin/category-extra.tpl`
    - **Cel:** Renderuje pole wyboru „Wyklucz tę kategorię z LLMS.txt” i wszelkie powiązane pola na stronie edycji kategorii PrestaShop. Ten szablon jest prawdopodobnie podłączony do `displayAdminProductsExtra` lub podobnego.
  - `llmstxtpro/views/templates/admin/configure.tpl`
    - **Cel:** Główny szablon dla strony konfiguracji modułu (metoda `getContent()`). Renderuje wszystkie ogólne ustawienia, opcje włączeń/wykluczeń, ustawienia zaawansowane i przyciski akcji.
  - `llmstxtpro/views/templates/admin/dashboard.tpl`
    - **Cel:** Renderuje panel analityczny modułu, wyświetlając ruch botów, status generowania i potencjalnie dzienniki błędów.
  - `llmstxtpro/views/templates/admin/preview.tpl`
    - **Cel:** Renderuje zawartość wygenerowanych plików `llms.txt` i `llms-full.txt` do przeglądu w Panelu administracyjnym.
  - `llmstxtpro/views/templates/admin/product-extra.tpl`
    - **Cel:** Renderuje pole wyboru „Wyklucz ten produkt z LLMS.txt” i wszelkie powiązane pola na stronie edycji produktu PrestaShop. Ten szablon jest prawdopodobnie podłączony do `displayAdminProductsExtra` lub podobnego.
- **Szablony front-office (`views/templates/front/`)**: Żadne nie są jawnie wymienione, co potwierdza, że interakcja modułu z front-office odbywa się głównie maszyna-maszyna za pośrednictwem pliku `llms.txt`.
- `llmstxtpro/lib/searchTool/views/scripts.tpl`
  - **Cel:** Prawdopodobnie zawiera zasoby JavaScript i CSS dla narzędzia wyszukiwania (np. autocomplete.js, autocomplete.css) w kontekście administracyjnym.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:
  - `ps_configuration`: Przechowuje wszystkie ustawienia konfiguracji modułu (np. `LLMSTXTPRO_ENABLED`, `LLMSTXTPRO_FILE_TYPE`, `LLMSTXTPRO_INCLUDE_PRODUCTS`, `LLMSTXTPRO_EXCLUDE_URLS` itp.).
  - `ps_llmstxtpro_product_override`: Niestandardowa tabela do przechowywania ustawień wykluczeń dla poszczególnych produktów. (Prawdopodobnie `id_product`, `excluded`).
  - `ps_llmstxtpro_category_override`: Niestandardowa tabela do przechowywania ustawień wykluczeń dla poszczególnych kategorii. (Prawdopodobnie `id_category`, `excluded`).
  - `ps_llmstxtpro_analytics_log`: Niestandardowa tabela do przechowywania dzienników dostępu botów (np. `id_llmstxtpro_analytics_log`, `user_agent`, `access_time`, `file_type`).
  - `ps_llmstxtpro_urls`: Potencjalnie tabela do buforowania wygenerowanych adresów URL dla wydajności, zwłaszcza dla statycznego generowania plików. (Prawdopodobnie `id_url`, `url`, `file_type`, `date_add`).
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Przed renderowaniem zawartości kontrolera administracyjnego. | Wstrzykuje CSS/JS modułu dla konfiguracji administracyjnej, panelu i dodatkowych pól produktów/kategorii. |
| `displayAdminProductsExtra` | Na stronie edycji produktu. | Renderuje pole wyboru „Wyklucz ten produkt z LLMS.txt”. |
| `displayAdminCategoriesExtra` | Na stronie edycji kategorii. | Renderuje pole wyboru „Wyklucz tę kategorię z LLMS.txt”. |
| `actionModuleInstall` | Podczas instalacji modułu. | Tworzy tabele bazy danych, ustawia domyślne wartości konfiguracyjne. |
| `actionModuleUninstall` | Podczas deinstalacji modułu. | Usuwa tabele bazy danych i wartości konfiguracyjne. |
| `displayHeader` | W sekcji `<head>` stron front-office. | (Mniej prawdopodobne dla tego modułu, ale może być używane do metatagów lub linków specyficznych dla AI, jeśli to konieczne). |
| `displayRightColumn` | W prawej kolumnie stron front-office. | (Nie jest bezpośrednio związane z generowaniem `llms.txt`). |
| `displayFooter` | W stopce stron front-office. | (Nie jest bezpośrednio związane z generowaniem `llms.txt`). |
| `actionProductUpdate` | Po zaktualizowaniu produktu. | Potencjalnie wyzwala czyszczenie pamięci podręcznej lub flaguje do regeneracji, jeśli używane jest dynamiczne `llms.txt`. |
| `actionCategoryUpdate` | Po zaktualizowaniu kategorii. | Potencjalnie wyzwala czyszczenie pamięci podręcznej lub flaguje do regeneracji. |
| `actionObjectProductAddAfter` | Po dodaniu nowego produktu. | Potencjalnie wyzwala czyszczenie pamięci podręcznej lub flaguje do regeneracji. |
| `actionObjectCategoryAddAfter` | Po dodaniu nowej kategorii. | Potencjalnie wyzwala czyszczenie pamięci podręcznej lub flaguje do regeneracji. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zaloguj się na swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc sprzedawcom i programistom w przypadku wszelkich problemów lub pytań dotyczących modułu LLMS.txt Generator Pro.
