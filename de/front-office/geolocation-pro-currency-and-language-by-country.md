---
title: "Geolocation pro - Währung und Sprache nach Land - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Geolocation pro - Währung und Sprache nach Land“ von MyPresta.eu."
sidebar:
  label: "Geolocation pro - Währung und Sprache nach Land - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Geolocation pro - currency and language by country auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/geolocation-pro-currency-and-language-by-country.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/geolocation-pro-currency-and-language-by-country/)
>
> ---


# Geolocation pro - Währung und Sprache nach Land

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise erforderlich und in den meisten Hosting-Umgebungen verfügbar.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Geolocation pro - Währung und Sprache nach Land)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie die Kernfunktionalität des Moduls aktivieren oder deaktivieren und auf Diagnosewerkzeuge zugreifen können.

- **Geolocation Pro aktivieren:**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für das gesamte Modul.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul erkennt aktiv Kundenstandorte und wendet Ihre definierten Währungs- und Sprachregeln an.
    - *Wenn deaktiviert:* Das Modul ist inaktiv, und Ihr Shop kehrt für alle Besucher zu seinen Standard-Währungs- und Spracheinstellungen zurück, unabhängig von ihrem Standort.
  - **Empfohlener Wert:** JA (um die Funktionen des Moduls zu nutzen).
  - **Händlerszenario / Beispiel:** Sie haben alle Regeln eingerichtet und sind bereit, mit personalisierten Erlebnissen live zu gehen. Aktivieren Sie diesen Schalter. Wenn Sie die Funktion vorübergehend für Wartungsarbeiten deaktivieren müssen, schalten Sie sie aus.
- **Banner mit Länderauswahl anzeigen:**

  - **Was diese Einstellung bewirkt:** Legt fest, ob ein kleines Banner oder Pop-up erscheint, um Kunden über das erkannte Land zu informieren und ihnen die Möglichkeit zu geben, es zu ändern.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Banner erscheint (normalerweise oben oder unten auf dem Bildschirm), das das erkannte Land anzeigt und dem Kunden möglicherweise erlaubt, den erkannten Standort, die Währung oder die Sprache manuell zu überschreiben. Dies kann nützlich sein für Kunden, die VPNs verwenden oder die Einstellungen einer anderen Region bevorzugen.
    - *Wenn deaktiviert:* Es wird kein Banner angezeigt. Das Modul wendet die Regeln stillschweigend basierend auf der IP-Erkennung an.
  - **Empfohlener Wert:** JA (anfangs, um Kunden Kontrolle zu geben, dann NO in Betracht ziehen, wenn Sie ein vollständig nahtloses Erlebnis bevorzugen und der IP-Erkennung vertrauen).
  - **Händlerszenario / Beispiel:** Ein Kunde aus den USA besucht Ihren Shop, und das Modul erkennt seinen Standort korrekt. Wenn diese Einstellung aktiviert ist, könnte ein Banner sagen: „Sie browsen aus den Vereinigten Staaten. [Land ändern?]“ Dies gibt ihm die Möglichkeit, dies zu korrigieren, wenn er ein VPN verwendet oder lieber aus einer anderen Region einkaufen möchte.
- **Diagnose & Tools:**

  - **Was diese Einstellung bewirkt:** Dieser Abschnitt bietet Tools zum Testen der Funktionalität des Moduls und zur Überprüfung der IP-Erkennung. Es ist keine Einstellung zum Ändern, sondern ein Dienstprogramm.
  - **Auswirkung der Änderung dieser Einstellung:** Das Klicken auf die Diagnosewerkzeuge öffnet neue Ansichten oder Pop-ups, die Ihnen Informationen über Ihre aktuelle IP-Adresse, das erkannte Land und wie das Modul Regeln anwenden würde, anzeigen.
  - **Empfohlener Wert:** Verwenden Sie dies immer, wenn Sie neue Regeln einrichten oder Fehler beheben.
  - **Händlerszenario / Beispiel:** Sie haben eine Regel für Deutschland erstellt. Sie können das Diagnosetool verwenden, um einen Besuch aus Deutschland zu simulieren und zu sehen, ob die richtige Währung und Sprache angewendet werden, um sicherzustellen, dass Ihre Regeln wie erwartet funktionieren.

### 2.2 Dedizierter Admin-Bildschirm: Geo-Regeln (Back Office > Module > Geolocation pro > Geo-Regeln)

Dieser Bildschirm ermöglicht es Ihnen, die Kernregeln für Währung und Sprache basierend auf dem Land zu definieren und zu verwalten.

- **Bildschirmname & Menüpfad:** **Back Office > Module > Geolocation pro - Währung und Sprache nach Land > Geo-Regeln** (oder ähnlicher Pfad unter dem Hauptmenüpunkt des Moduls).
- **Verfügbare Aktionen & Einstellungen:**
  - **Listentabelle:** Zeigt alle Ihre vorhandenen Geo-Regeln an, mit Land, zugewiesener Währung und zugewiesener Sprache.
  - **Neue Geo-Regel hinzufügen:** Eine Schaltfläche zum Erstellen einer neuen Regel.
  - **Bearbeiten/Löschen-Aktionen:** Symbole neben jeder Regel zum Ändern oder Entfernen.
- **Auswirkung von Änderungen:**
  - **Hinzufügen einer neuen Regel:** Wenn Sie eine Regel hinzufügen (z. B. für „Deutschland“, um „EUR“ und „Deutsch“ zu verwenden), werden jedem Besucher, der als aus Deutschland stammend erkannt wird, automatisch Währung und Sprache auf diese Werte gesetzt.
  - **Bearbeiten einer Regel:** Das Ändern einer vorhandenen Regel ändert sofort das Verhalten des Moduls für Besucher aus diesem spezifischen Land.
  - **Löschen einer Regel:** Das Entfernen einer Regel bedeutet, dass Besucher aus diesem Land keine spezifische Währung oder Sprache mehr durch dieses Modul zugewiesen bekommen und zu den Standardeinstellungen Ihres Shops zurückkehren.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. **Zielmärkte identifizieren:** Entscheiden Sie, welche Länder Sie mit spezifischen Währungen und Sprachen ansprechen möchten.
  2. **Sicherstellen, dass Währungen/Sprachen aktiviert sind:** Stellen Sie sicher, dass die Währungen und Sprachen, die Sie zuweisen möchten, bereits in Ihrem PrestaShop-Shop aktiviert sind (Back Office > International > Währungen / Sprachen).
  3. **Regeln erstellen:** Klicken Sie für jedes Land auf „Neue Geo-Regel hinzufügen“, wählen Sie das Land aus dem Dropdown-Menü und dann die gewünschte Währung und Sprache. Speichern Sie die Regel.
  4. **Mit Diagnose testen:** Verwenden Sie die Diagnosewerkzeuge des Moduls, um zu überprüfen, ob Ihre Regeln wie beabsichtigt funktionieren.

### 2.3 Dedizierter Admin-Bildschirm: Sprachregeln (Back Office > Module > Geolocation pro > Sprachregeln)

Dieser Bildschirm scheint eine Duplizierung oder eine alternative Schnittstelle zur Verwaltung sprachspezifischer Regeln zu sein, die möglicherweise eine granularere Kontrolle oder eine andere Ansicht bietet. Angesichts der Modulbeschreibung ist der Bildschirm „Geo-Regeln“ wahrscheinlich die primäre Schnittstelle für länderbasierte Zuweisungen. Dieser Bildschirm könnte für erweiterte, sprachspezifische Überschreibungen gedacht sein, die nicht direkt an ein Land gebunden sind.

- **Bildschirmname & Menüpfad:** **Back Office > Module > Geolocation pro - Währung und Sprache nach Land > Sprachregeln** (oder ähnlicher Pfad).
- **Verfügbare Aktionen & Einstellungen:**
  - **Listentabelle:** Zeigt vorhandene Sprachregeln an.
  - **Neue Sprachregel hinzufügen:** Schaltfläche zum Erstellen einer neuen Regel.
  - **Bearbeiten/Löschen-Aktionen:** Symbole zum Ändern oder Entfernen von Regeln.
- **Auswirkung von Änderungen:** Diese Regeln würden wahrscheinlich die länderbasierten Regeln für die Sprache überschreiben oder ergänzen. Zum Beispiel könnten Sie eine allgemeine Regel für „Englisch“ für alle nicht spezifizierten Länder haben und dann diesen Bildschirm für Ausnahmen oder spezifische Sprachverhaltensweisen verwenden.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Verwenden Sie diesen Bildschirm, wenn Sie Spracheinstellungen unabhängig von länderspezifischen Geo-Regeln verwalten müssen oder wenn Sie Szenarien antreffen, in denen eine Länderregel für die Sprachbehandlung nicht ausreicht. Andernfalls konzentrieren Sie sich auf den Bildschirm „Geo-Regeln“.

### 2.4 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | Geolocation Pro aktivieren | JA | Hauptschalter für die Modulfunktionalität. JA aktiviert die länderbasierte Währungs-/Spracherkennung. |
| | Banner mit Länderauswahl anzeigen | JA | Zeigt ein Banner an, das Kunden über das erkannte Land informiert und eine manuelle Überschreibung ermöglicht. |
| | Diagnose & Tools | N/A | Dienstprogramm zum Testen der IP-Erkennung und Regelanwendung. |
| **Geo-Regeln** | Geo-Regel hinzufügen/bearbeiten (Land, Währung, Sprache) | N/A | Definiert, welche Währung und Sprache für Besucher aus einem bestimmten Land automatisch eingestellt werden. |
| **Sprachregeln** | Sprachregel hinzufügen/bearbeiten | N/A | (Potenziell) Definiert Sprachüberschreibungen oder spezifische Sprachverhaltensweisen, möglicherweise unabhängig vom Land. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Kunden sehen immer noch die falsche Währung/Sprache, obwohl ich Regeln eingerichtet habe. Was ist falsch?**
A1:

- **Ist das Modul aktiviert?** Überprüfen Sie die Einstellung „Geolocation Pro aktivieren“ auf der Hauptkonfigurationsseite.
- **Sind Ihre Regeln korrekt?** Gehen Sie zu „Geo-Regeln“ und stellen Sie sicher, dass Land, Währung und Sprache korrekt zugewiesen sind.
- **Sind die Währungen/Sprachen in PrestaShop aktiviert?** Stellen Sie sicher, dass die Währungen und Sprachen, die Sie zuweisen möchten, in Ihrem PrestaShop aktiv sind (International > Währungen / Sprachen).
- **Leeren Sie Ihren Browser-Cache:** Manchmal speichert Ihr Browser alte Einstellungen im Cache. Bitten Sie Kunden, ihren Browser-Cache zu leeren oder ein Inkognito-Fenster zu verwenden.
- **Leeren Sie den PrestaShop-Cache:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie oben rechts auf „Cache leeren“.
- **Mit Diagnose testen:** Verwenden Sie die integrierten Diagnosewerkzeuge des Moduls, um einen Besuch aus einem bestimmten Land zu simulieren und zu sehen, welche Währung/Sprache angewendet wird. Dies hilft, festzustellen, ob das Problem bei der Erkennung oder der Regelanwendung liegt.

**F2: Das Modul erkennt für einige Kunden das falsche Land. Warum?**
A2:

- **VPNs und Proxys:** Kunden, die Virtual Private Networks (VPNs) oder Proxy-Server verwenden, erscheinen so, als würden sie von dem Standort ihres VPNs/Proxys aus browsen, nicht von ihrem tatsächlichen physischen Standort. Das Modul basiert auf der IP-Adresserkennung, die gefälscht werden kann.
- **Genauigkeit der IP-Datenbank:** Geolocation-Datenbanken sind im Allgemeinen sehr genau, aber nicht 100% perfekt. Einige IP-Bereiche könnten falsch identifiziert werden.
- **„Banner mit Länderauswahl anzeigen“:** Wenn diese Einstellung aktiviert ist, können Kunden das erkannte Land manuell korrigieren, was die beste Lösung für diese Grenzfälle ist.

**F3: Wie füge ich eine neue Währung oder Sprache zu meinem Shop hinzu, damit ich sie in einer Geo-Regel verwenden kann?**
A3:

- **Währung hinzufügen:** Gehen Sie in Ihrem PrestaShop Back Office zu **International > Währungen**. Klicken Sie auf „Neue Währung hinzufügen“, füllen Sie die Details aus und aktivieren Sie sie.
- **Sprache hinzufügen:** Gehen Sie in Ihrem PrestaShop Back Office zu **International > Sprachen**. Klicken Sie auf „Neue Sprache hinzufügen“, füllen Sie die Details aus und aktivieren Sie sie. Denken Sie daran, auch Sprachpakete zu installieren und Ihre Inhalte für die neue Sprache zu übersetzen.

**F4: Wird dieses Modul meine Website verlangsamen?**
A4: Das Modul führt eine schnelle IP-Suche und Regelanwendung durch, die im Allgemeinen sehr schnell und optimiert ist. Es sollte die Ladezeit Ihrer Website nicht merklich beeinflussen. Wenn Sie Leistungsprobleme feststellen, stellen Sie sicher, dass Ihr PrestaShop-Cache aktiviert und regelmäßig geleert wird.

**F5: Ich möchte das Banner zur Länderauswahl an mein Theme anpassen. Wie mache ich das?**
A5: Das Banner verwendet spezifische CSS-Klassen. Obwohl die direkte Änderung von Moduldateien nicht empfohlen wird (da Updates diese überschreiben würden), kann ein Webentwickler die benutzerdefinierte CSS-Datei Ihres Themes verwenden, um die Standardstile zu überschreiben. Er würde das Banner mit den Browser-Entwicklertools inspizieren, um die relevanten CSS-Selektoren (z. B. Klassen wie `.progeo-banner`, `.progeo-choice`) zu identifizieren und dann seine eigenen Stile anzuwenden.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Geolocation pro - Währung und Sprache nach Land“ (`progeo`) ist so konzipiert, dass es tief in die Kernfunktionen der PrestaShop-Internationalisierung integriert ist. Es nutzt hauptsächlich Überschreibungen, um zu ändern, wie PrestaShop die aktive `Configuration`, `Currency` und `Language` basierend auf der IP-Adresse des Besuchers bestimmt. Es folgt einer Standard-PrestaShop-Modulstruktur, verwendet Front- und Admin-Controller, benutzerdefinierte Klassen (insbesondere für `ObjectModel`-Entitäten) und Smarty-Templates sowohl für die Konfiguration als auch für die Front-Office-Anzeige (z. B. das Banner zur Länderauswahl). Die Kernlogik des Moduls befindet sich in seiner `index.php` (Hauptmoduldatei) und den überschriebenen Kernklassen.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `progeo/controllers/front/choice.php`
  - **Klassenname & Elternklasse:** `ProgeoChoiceModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller verarbeitet AJAX-Anfragen im Zusammenhang mit dem Banner zur Länderauswahl. Wenn ein Kunde mit dem Banner interagiert (z. B. ein anderes Land, eine andere Währung oder Sprache auswählt), verarbeitet dieser Controller die Anfrage, aktualisiert Sitzungsvariablen oder Cookies und leitet den Benutzer möglicherweise um, um die neuen Einstellungen anzuwenden. Er ist entscheidend für den interaktiven Aspekt des Banners.
- `progeo/controllers/front/index.php`
  - **Klassenname & Elternklasse:** `ProgeoIndexModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller könnte als Fallback oder einfacher Einstiegspunkt für Front-Office-Modulaktionen dienen, obwohl `choice.php` spezifischer für die Interaktivität des Banners ist. In vielen Modulen ist `index.php` in `controllers/front` ein Platzhalter oder verarbeitet sehr grundlegende, unspezifische Front-Office-Anfragen.

#### Back-Office-Admin-Controller

- `progeo/controllers/admin/AdminGeorulesController.php`
  - **Tab-Name und verwaltete Entität:** „Geo-Regeln“ (unter dem Hauptmenü des Moduls). Verwaltet `Georule`-Entitäten.
  - **Verantwortlichkeit:** Dies ist der primäre Controller zur Verwaltung länderspezifischer Währungs- und Sprachzuweisungen. Er bietet die CRUD-Schnittstelle (Create, Read, Update, Delete) für `ps_progeo_georule`-Datensätze, die es Administratoren ermöglicht, zu definieren, welche Währung und Sprache für Besucher aus bestimmten Ländern aktiv sein sollen. Er erweitert `AdminController` und verwendet `HelperList` für das Raster und `HelperForm` für Hinzufügen-/Bearbeiten-Formulare.
- `progeo/controllers/admin/AdminLangrules.php`
  - **Tab-Name und verwaltete Entität:** „Sprachregeln“ (unter dem Hauptmenü des Moduls). Verwaltet `Langrule`-Entitäten.
  - **Verantwortlichkeit:** Dieser Controller verwaltet sprachspezifische Regeln. Er bietet eine CRUD-Schnittstelle für `ps_progeo_langrule`-Datensätze. Er wird wahrscheinlich für eine granularere Sprachsteuerung verwendet, die möglicherweise die in `AdminGeorulesController` festgelegte Sprache überschreibt oder ergänzt.
- `progeo/controllers/admin/AdminLangrulesController.php`
  - **Tab-Name und verwaltete Entität:** „Sprachregeln“ (unter dem Hauptmenü des Moduls). Verwaltet `Langrule`-Entitäten.
  - **Verantwortlichkeit:** Dies scheint eine Duplizierung oder eine alternative Implementierung von `AdminLangrules.php` zu sein. In einem typischen PrestaShop-Modul wäre `AdminLangrulesController.php` die Standard-Namenskonvention. Entwickler sollten überprüfen, welche Datei tatsächlich von der Menüregistrierung des Moduls verwendet wird.
- `progeo/controllers/admin/index.php`
  - **Tab-Name und verwaltete Entität:** Kein direkter Tab, aber ein Standard-Platzhalter.
  - **Verantwortlichkeit:** Diese Datei ist oft in `controllers/admin`-Verzeichnissen vorhanden, aber typischerweise leer oder enthält grundlegende Sicherheitsmaßnahmen (z. B. `die('Forbidden');`). Sie verwaltet keine spezifische Entität und bietet keine Benutzeroberfläche.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul verwendet Überschreibungen, um seine Logik in das Kernverhalten von PrestaShop zu injizieren.

- `progeo/override/classes/Configuration.php`
  - **Verantwortlichkeit:** Überschreibt die Kernklasse `Configuration`. Dies ist entscheidend, damit das Modul globale Konfigurationswerte (wie `PS_CURRENCY_DEFAULT` oder `PS_LANG_DEFAULT`) dynamisch basierend auf der Geolocation ändern kann, ohne die Datenbankwerte für andere Besucher tatsächlich zu ändern. Es stellt sicher, dass, wenn PrestaShop einen Konfigurationswert anfordert, das Modul diesen abfangen und einen lokalisierten zurückgeben kann.
- `progeo/override/classes/Currency.php`
  - **Verantwortlichkeit:** Überschreibt die Kernklasse `Currency`. Diese Überschreibung ermöglicht es dem Modul, zu manipulieren, welche Währung für den aktuellen Besucher als „aktiv“ oder „Standard“ gilt, um sicherzustellen, dass die Preise gemäß der Geo-Regel korrekt angezeigt werden.
- `progeo/override/classes/Language.php`
  - **Verantwortlichkeit:** Überschreibt die Kernklasse `Language`. Ähnlich wie `Currency.php` ermöglicht diese Überschreibung dem Modul, die aktive Sprache für den aktuellen Besucher basierend auf der Geolocation festzulegen, um sicherzustellen, dass Inhalte in der richtigen Sprache angezeigt werden.
- `progeo/override/classes/index.php`
  - **Verantwortlichkeit:** Standardmäßig leere `index.php`-Datei zur Sicherheit in einem Verzeichnis.
- `progeo/override/classes/_Configuration.php`
  - **Verantwortlichkeit:** Dieser Dateiname deutet auf ein potenzielles Backup oder eine ältere Version der `Configuration`-Überschreibung hin. In einer Produktionsumgebung sollte nur eine `Configuration.php`-Überschreibung aktiv sein. Entwickler sollten den Installationsprozess des Moduls überprüfen, um sicherzustellen, dass die korrekte Überschreibung verwendet wird.

### 4.4 JavaScript-Assets (`views/js/`)

- `progeo/views/js/banner.js`
  - **Geltungsbereich:** Front-Office.
  - **Verantwortlichkeit:** Dieses Skript verarbeitet das interaktive Banner zur Länderauswahl.
    - **Event-Listener:** Bindet Ereignisse an Elemente innerhalb des Banners (z. B. Klickereignisse auf „Land ändern“-Schaltflächen, Änderungen in Auswahlfeldern für Währung/Sprache).
    - **AJAX-Aufrufe:** Führt AJAX-Anfragen an den `ProgeoChoiceModuleFrontController` (z. B. `choice.php`) aus, um das vom Benutzer ausgewählte Land, die Währung oder die Sprache zu aktualisieren.
    - **DOM-Manipulation:** Zeigt/versteckt das Banner, aktualisiert Textinhalte basierend auf Benutzerauswahlen und leitet den Browser möglicherweise nach einer Auswahl um.
    - **Cookies/Lokaler Speicher:** Kann Benutzereinstellungen in Cookies oder im lokalen Speicher speichern, um die Auswahl über Sitzungen hinweg zu merken.

### 4.5 CSS-Stylesheets (`views/css/`)

- `progeo/views/css/admin.css`
  - **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
  - **Verantwortlichkeit:** Bietet spezifisches Styling für die Konfigurationsseiten des Moduls und die Admin-Controller (z. B. `AdminGeorulesController`, `AdminLangrulesController`). Dies gewährleistet ein konsistentes Erscheinungsbild im PrestaShop Back Office und verbessert die Benutzerfreundlichkeit der Formulare und Listen des Moduls.
- `progeo/views/css/banner.css`
  - **Geltungsbereich:** Front-Office-Kunden-Styling.
  - **Verantwortlichkeit:** Gestaltet das Banner zur Länderauswahl, das im Front Office erscheint. Es definiert die Position, Farben, Schriftarten, Responsivität und die gesamte visuelle Darstellung des Banners. Entwickler können diese Stile in der benutzerdefinierten CSS-Datei ihres Themes überschreiben, um das Banner nahtlos in das Design des Shops zu integrieren. Wichtige Selektoren könnten `.progeo-banner`, `.progeo-choice-form` usw. sein.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - `progeo/views/displayHeader.tpl`: Dieses Template ist wahrscheinlich in `displayHeader` (oder `actionFrontControllerSetMedia`) eingehängt, um notwendige CSS- und JS-Dateien für das Front-Office-Banner einzubinden oder initiale JavaScript-Variablen zu injizieren.
- **Admin-Templates (`views/templates/admin/`)**:
  - `progeo/views/advert.tpl`: Wahrscheinlich zur Anzeige von Werbebotschaften oder Links zu anderen MyPresta.eu-Modulen innerhalb der Modulkonfiguration verwendet.
  - `progeo/views/banner.tpl`: Dieses Template wird wahrscheinlich innerhalb der Modulkonfiguration verwendet, um Einstellungen für das Front-Office-Banner vorab anzuzeigen oder zu verwalten.
  - `progeo/views/currenciesForm.tpl`: Template zur Verwaltung währungsbezogener Einstellungen, möglicherweise innerhalb der Hauptkonfiguration oder eines dedizierten Admin-Bildschirms.
  - `progeo/views/diagnostics-layer1.tpl`, `progeo/views/diagnostics-layer2.tpl`, `progeo/views/diagnostics-overview.tpl`, `progeo/views/diagnostics-result.tpl`, `progeo/views/diagnostics.tpl`: Diese Templates werden verwendet, um die verschiedenen Diagnosewerkzeuge und deren Ausgabe zu rendern, um dem Administrator bei der Fehlerbehebung der IP-Erkennung und Regelanwendung zu helfen.
  - `progeo/views/languagesForm.tpl`: Template zur Verwaltung sprachbezogener Einstellungen, ähnlich wie `currenciesForm.tpl`.
  - `progeo/views/tabs.tpl`: Wird zum Rendern von Navigations-Tabs innerhalb der Konfigurationsoberfläche des Moduls verwendet, sodass der Administrator zwischen verschiedenen Einstellungsbereichen wechseln kann (z. B. „Geo-Regeln“, „Sprachregeln“, „Konfiguration“).
  - `progeo/views/tools-hint.tpl`, `progeo/views/tools.tpl`: Templates zur Anzeige von Hinweisen oder allgemeinen Tools innerhalb der Back-Office-Oberfläche des Moduls.
- **Front-Office-Templates (`views/templates/front/`)**:
  - `progeo/views/banner.tpl`: Dies ist das eigentliche Template für das Front-Office-Banner zur Länderauswahl, das dem Kunden gerendert wird. Es enthält die HTML-Struktur zur Anzeige des erkannten Landes, der Währung, der Sprache und der Optionen zur manuellen Auswahl.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - `ps_progeo_georule`: Speichert die Haupt-Geolocation-Regeln.
    - `id_progeo_georule` (Primärschlüssel)
    - `id_country` (Fremdschlüssel zu `ps_country`)
    - `id_currency` (Fremdschlüssel zu `ps_currency`)
    - `id_lang` (Fremdschlüssel zu `ps_lang`)
  - `ps_progeo_langrule`: Speichert sprachspezifische Regeln (Details würden von der spezifischen Implementierung abhängen, aber wahrscheinlich eine ähnliche Struktur für Sprachüberschreibungen).
    - `id_progeo_langrule` (Primärschlüssel)
    - `id_lang` (Fremdschlüssel zu `ps_lang`)
    - (Potenziell weitere Felder für spezifische Sprachverhaltensweisen)
  - Konfigurationsdatensätze in `ps_configuration`:
    - `PROGEO_ENABLED`: (1 oder 0) Hauptschalter für das Modul.
    - `PROGEO_SHOW_BANNER`: (1 oder 0) Ob das Banner zur Länderauswahl angezeigt werden soll.
    - (Weitere Konfigurationsschlüssel, wie in `getContent()` und `install()` definiert)
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Zum Einbinden von CSS- und JavaScript-Assets (`banner.css`, `banner.js`) für das Front-Office-Banner und potenziell zum Injizieren initialer JavaScript-Variablen oder zum Rendern des Banners selbst. |
| `actionFrontControllerSetMedia` | Wird ausgeführt, wenn ein Front-Controller seine Medien-Assets festlegt. | Ähnlich wie `displayHeader`, wird zum bedingten oder auf modernere PrestaShop-Weise Hinzufügen von CSS- und JS-Dateien verwendet. |
| `actionModuleInstall` | Während der Modulinstallation. | Zum Erstellen von Datenbanktabellen (`ps_progeo_georule`, `ps_progeo_langrule`), Registrieren von Hooks und Festlegen von Standardkonfigurationswerten. |
| `actionModuleUninstall` | Während der Moduldeinstallation. | Zum Entfernen von Datenbanktabellen, Aufheben der Registrierung von Hooks und Bereinigen von Konfigurationswerten. |
| `displayBackOfficeHeader` | Im `<head>`-Bereich jeder Back-Office-Seite. | Zum Einbinden von `admin.css` für Modulkonfigurationsseiten und potenziell admin-spezifischem JavaScript. |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin-Controller seine Medien-Assets festlegt. | Ähnlich wie `displayBackOfficeHeader`, zum Hinzufügen von Admin-CSS und JS. |
| `actionDispatcherBefore` | Bevor der Dispatcher eine Anfrage verarbeitet. | Entscheidend für die Kernlogik des Moduls: um die IP des Besuchers zu erkennen, die Geo-Regel anzuwenden und die korrekte `Context`-Währung und -Sprache festzulegen, *bevor* PrestaShop die Seite rendert. Hier werden die Überschreibungen effektiv ausgelöst. |
| `displayBanner` (Benutzerdefinierter Hook) | Potenziell ein benutzerdefinierter Hook zum Rendern des Front-Office-Banners. | Wenn `displayBanner` ein benutzerdefinierter Hook ist, würde sich das Modul registrieren, um `banner.tpl` an dieser spezifischen Stelle zu rendern. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul „Geolocation pro - Währung und Sprache nach Land“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, sicherzustellen, dass Ihr Modul optimal funktioniert und nahtlos in Ihren PrestaShop-Shop integriert ist.
