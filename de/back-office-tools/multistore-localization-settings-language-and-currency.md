---
title: "Multistore Lokalisierungseinstellungen - Sprache und Währung - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Multistore Lokalisierungseinstellungen - Sprache und Währung' von MyPresta.eu."
sidebar:
  label: "Multistore Lokalisierungseinstellungen - Sprache und Währung - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Multistore localization settings - language and currency auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/multistore-localization-settings-language-and-currency.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/multistore-localization-settings-language-and-currency/)
>
> ---


# Multistore Lokalisierungseinstellungen - Sprache und Währung

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL). Ihre Hosting-Umgebung muss die PrestaShop Multistore-Funktion unterstützen.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Dieses Modul führt einen neuen Menüpunkt in Ihrem PrestaShop Back Office ein, um die Lokalisierungsregeln für jeden Ihrer Shops zu verwalten.

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Wenn Sie nach der Installation zum ersten Mal auf „Konfigurieren“ klicken, gelangen Sie auf eine grundlegende Konfigurationsseite. Diese Seite dient hauptsächlich als Einstiegspunkt zur Hauptverwaltungsoberfläche.

- **Was diese Einstellung bewirkt:** Dieser Bildschirm enthält wahrscheinlich eine einfache Nachricht oder eine Schaltfläche, die Sie zum dedizierten Verwaltungsbereich für Multistore-Lokalisierungsregeln leitet. Er könnte auch Informationen zur Modulversion oder einen Link zum Support enthalten.
- **Auswirkung der Änderung dieser Einstellung:** Das Klicken auf eine Schaltfläche oder einen Link hier navigiert Sie zur Hauptoberfläche, wo Sie Ihre shop-spezifischen Sprach- und Währungsregeln definieren.
- **Empfohlener Wert:** Befolgen Sie die Anweisungen auf dem Bildschirm, normalerweise indem Sie auf eine Schaltfläche klicken, um zur Hauptkonfiguration fortzufahren.
- **Händlerszenario / Beispiel:** Nach der Installation sehen Sie eine Nachricht wie „Klicken Sie hier, um Ihre Multistore-Lokalisierungsregeln zu verwalten.“ Sie klicken darauf, um auf die Kernfunktionalität zuzugreifen.

### 2.2 Dedizierter Admin-Bildschirm: Multistore-Lokalisierungsregeln (Back Office > Multistore-Lokalisierungsregeln)

Dies ist das Hauptkontrollpanel für das Modul. Sie finden diesen neuen Menüpunkt unter **Shop-Parameter > Multistore-Lokalisierungsregeln** (oder ähnlich, abhängig von Ihrer PrestaShop-Version und Menüstruktur).

Beim Betreten dieses Bildschirms sehen Sie eine Liste (Raster) Ihrer bestehenden Shops. Für jeden Shop können Sie dessen spezifische Sprach- und Währungseinstellungen definieren.

**Verfügbare Aktionen & Einstellungen:**

1. **Shop-Liste / Rasteransicht:**

   - **Zweck:** Diese Tabelle zeigt alle Shops an, die Sie in Ihrer PrestaShop Multistore-Einrichtung konfiguriert haben.
   - **Spalten:** Sie sehen typischerweise Spalten wie „Shop-Name“ und möglicherweise „Aktionen“ oder „Konfigurieren“.
   - **Auswirkung von Änderungen:** Diese Ansicht ermöglicht es Ihnen, schnell zu sehen, welche Shops konfiguriert sind, und bietet den Einstiegspunkt zum Bearbeiten ihrer Lokalisierungseinstellungen.
2. **Bearbeiten/Konfigurieren-Schaltfläche für jeden Shop:**

   - **Was diese Schaltfläche bewirkt:** Das Klicken auf diese Schaltfläche (oft ein Bleistiftsymbol) neben einem Shop-Namen öffnet ein detailliertes Konfigurationsformular speziell für diesen Shop.
   - **Auswirkung der Änderung dieser Einstellung:** Hier definieren Sie die spezifischen Sprachen und Währungen für den ausgewählten Shop.

**Innerhalb des shop-spezifischen Konfigurationsformulars:**

Wenn Sie auf „Shop bearbeiten“ klicken, sehen Sie zwei Hauptabschnitte: **Sprachen** und **Währungen**.

#### 2.2.1 Sprachen-Konfiguration für [Shop-Name]

- **Liste der verfügbaren Sprachen:**

  - **Was diese Einstellung bewirkt:** Dieser Abschnitt präsentiert eine Liste aller in Ihrem PrestaShop-Shop installierten Sprachen. Für jede Sprache sehen Sie typischerweise ein Kontrollkästchen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Sprache steht den Kunden im Front Office dieses spezifischen Shops zur Auswahl.
    - *Wenn deaktiviert:* Die Sprache wird NICHT in der Sprachauswahl für diesen Shop angezeigt, und Kunden können nicht zu ihr wechseln.
  - **Empfohlener Wert:** Aktivieren Sie nur die Sprachen, die für die Zielgruppe dieses spezifischen Shops relevant sind.
  - **Händlerszenario / Beispiel:** Für Ihren „Französischen Shop“ würden Sie „Français (Französisch)“ aktivieren und alle anderen Sprachen deaktivieren.
- **Standardsprache für [Shop-Name]:**

  - **Was diese Einstellung bewirkt:** Eine Dropdown- oder Radiobutton-Auswahl, mit der Sie eine der *aktivierten* Sprachen als Standard für diesen Shop auswählen können.
  - **Auswirkung der Änderung dieser Einstellung:** Wenn ein Kunde diesen Shop zum ersten Mal besucht, wird er automatisch in der ausgewählten Standardsprache geladen. Wenn der Kunde zuvor eine Sprache ausgewählt hat, wird seine Präferenz möglicherweise gespeichert, aber für neue Besucher gilt diese Standardeinstellung.
  - **Empfohlener Wert:** Legen Sie die primäre Sprache für die Zielgruppe des Shops fest.
  - **Händlerszenario / Beispiel:** Für Ihren „Französischen Shop“ würden Sie „Français (Französisch)“ als Standardsprache festlegen.

#### 2.2.2 Währungen-Konfiguration für [Shop-Name]

- **Liste der verfügbaren Währungen:**

  - **Was diese Einstellung bewirkt:** Dieser Abschnitt präsentiert eine Liste aller in Ihrem PrestaShop-Shop installierten Währungen. Für jede Währung sehen Sie typischerweise ein Kontrollkästchen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Währung steht den Kunden im Front Office dieses spezifischen Shops zur Auswahl. Preise werden in dieser Währung angezeigt, wenn ausgewählt.
    - *Wenn deaktiviert:* Die Währung wird NICHT in der Währungsauswahl für diesen Shop angezeigt, und Kunden können Preise nicht in dieser Währung anzeigen.
  - **Empfohlener Wert:** Aktivieren Sie nur die Währungen, die für die Zielgruppe dieses spezifischen Shops relevant sind.
  - **Händlerszenario / Beispiel:** Für Ihren „US-Shop“ würden Sie „US-Dollar ($)“ aktivieren und „Euro (€)“ sowie andere Währungen deaktivieren.
- **Standardwährung für [Shop-Name]:**

  - **Was diese Einstellung bewirkt:** Eine Dropdown- oder Radiobutton-Auswahl, mit der Sie eine der *aktivierten* Währungen als Standard für diesen Shop auswählen können.
  - **Auswirkung der Änderung dieser Einstellung:** Wenn ein Kunde diesen Shop zum ersten Mal besucht, werden alle Preise automatisch in der ausgewählten Standardwährung angezeigt.
  - **Empfohlener Wert:** Legen Sie die primäre Währung für die Zielgruppe des Shops fest.
  - **Händlerszenario / Beispiel:** Für Ihren „US-Shop“ würden Sie „US-Dollar ($)“ als Standardwährung festlegen.

**Empfohlener Arbeitsablauf für die tägliche Shop-Verwaltung:**

1. Navigieren Sie zu **Shop-Parameter > Multistore-Lokalisierungsregeln**.
2. Identifizieren Sie den Shop, den Sie aus der Liste konfigurieren möchten.
3. Klicken Sie auf die Schaltfläche „Bearbeiten“ oder „Konfigurieren“ neben diesem Shop.
4. Aktivieren Sie im Abschnitt „Sprachen“ alle Sprachen, die für diesen spezifischen Shop verfügbar sein sollen.
5. Wählen Sie eine der *aktivierten* Sprachen als „Standardsprache“ für diesen Shop aus.
6. Aktivieren Sie im Abschnitt „Währungen“ alle Währungen, die für diesen spezifischen Shop verfügbar sein sollen.
7. Wählen Sie eine der *aktivierten* Währungen als „Standardwährung“ für diesen Shop aus.
8. Klicken Sie auf „Speichern“, um Ihre Änderungen zu übernehmen.
9. Wiederholen Sie dies für alle anderen Shops in Ihrer Multistore-Einrichtung.
10. **Leeren Sie immer Ihren PrestaShop-Cache** (Erweiterte Parameter > Leistung), nachdem Sie Änderungen vorgenommen haben, um sicherzustellen, dass diese sofort im Front Office widergespiegelt werden.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Multistore-Lokalisierungsregeln (Listenansicht)** | Bearbeiten/Konfigurieren-Schaltfläche | N/A | Zugriff auf detaillierte Sprach-/Währungseinstellungen für einen bestimmten Shop. |
| **Shop-spezifische Konfiguration (Sprachen)** | Verfügbare Sprachen (Kontrollkästchen) | Relevante aktivieren | Steuert, welche Sprachen im Front-Office-Auswahlfeld für diesen Shop erscheinen. |
| **Shop-spezifische Konfiguration (Sprachen)** | Standardsprache | Primäre Sprache für die Zielgruppe des Shops | Legt die anfängliche Sprache für neue Besucher dieses Shops fest. |
| **Shop-spezifische Konfiguration (Währungen)** | Verfügbare Währungen (Kontrollkästchen) | Relevante aktivieren | Steuert, welche Währungen im Front-Office-Auswahlfeld für diesen Shop erscheinen. |
| **Shop-spezifische Konfiguration (Währungen)** | Standardwährung | Primäre Währung für die Zielgruppe des Shops | Legt die anfängliche Währung für neue Besucher dieses Shops fest. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe die Sprachen/Währungen konfiguriert, aber sie ändern sich nicht in meinem Front Office.**
A: Der häufigste Grund dafür ist der Cache. Gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Parameter > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ und „Cache leeren“ für alle Caches). Versuchen Sie auch, den Cache Ihres Browsers zu leeren.

**F: Mein benutzerdefiniertes Theme scheint die Moduleinstellungen für die Sprach-/Währungsauswahl nicht zu berücksichtigen.**
A: Dieses Modul steuert, *welche* Optionen verfügbar sind, aber Ihr Theme bestimmt, *wie* diese Optionen angezeigt werden. Wenn Ihr Theme stark angepasste Sprach-/Währungsauswahlen hat, könnte es das Standardverhalten von PrestaShop überschreiben.
\* **Lösung:** Überprüfen Sie die Dokumentation Ihres Themes oder kontaktieren Sie Ihren Theme-Entwickler. Möglicherweise müssen Sie kleinere Anpassungen an den `.tpl`-Dateien Ihres Themes vornehmen, um sicherzustellen, dass sie die Standardvariablen `languages` und `currencies` von PrestaShop verwenden, die dieses Modul modifiziert.

**F: Kann ich verschiedene Standardsprachen/Währungen für verschiedene Kundengruppen festlegen?**
A: Nein, dieses Modul legt die Standardsprache und -währung *pro Shop* fest, nicht pro Kundengruppe. Der Standard gilt für alle Besucher dieses spezifischen Shops. Kunden können sie dann manuell ändern, wenn andere Optionen verfügbar sind.

**F: Was passiert, wenn ich eine Sprache/Währung deaktiviere, die derzeit als Standard für einen Shop festgelegt ist?**
A: Das Modul sollte Sie daran hindern, dies zu tun, oder automatisch zur nächsten verfügbaren Sprache/Währung zurückkehren. Stellen Sie immer sicher, dass Ihre gewählte Standardeinstellung eine der *aktivierten* Optionen für diesen Shop ist. Wenn Probleme auftreten, aktivieren Sie einen geeigneten Standard erneut und leeren Sie Ihren Cache.

**F: Ich habe nur einen Shop. Brauche ich dieses Modul?**
A: Nein, dieses Modul ist speziell für die Multistore-Funktion von PrestaShop konzipiert. Wenn Sie nur einen einzigen Shop haben, reichen die Standard-Lokalisierungseinstellungen von PrestaShop (unter International > Lokalisierung) aus.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten Einblick in die technische Implementierung des Moduls „Multistore Lokalisierungseinstellungen - Sprache und Währung“ für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul erweitert hauptsächlich das Kern-Lokalisierungsverhalten von PrestaShop, indem es die Klassen `Currency` und `Language` überschreibt. Es führt einen benutzerdefinierten Administrations-Controller (`AdminMultirulesController`) ein, um shop-spezifische Lokalisierungsregeln zu verwalten, die in einer benutzerdefinierten Datenbanktabelle gespeichert werden. Das Modul nutzt das MVC-Muster von PrestaShop für seine Back-Office-Oberfläche und verwendet Overrides, um seine Logik in den Sprach- und Währungsauswahlprozess des Front Office zu integrieren.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Dieses Modul enthält keine dedizierten Front-Office-Controller. Seine Front-Office-Logik wird über Klassen-Overrides und Hooks injiziert.
- **Back-Office-Admin-Controller**:

  - `multishoplang/controllers/admin/AdminMultirules.php`
    - **Klassenname & Elternklasse**: `AdminMultirulesController` erweitert `ModuleAdminController`.
    - **Verantwortlichkeit**: Dieser Controller verwaltet die Auflistung und Bearbeitung von Lokalisierungsregeln für jeden Shop. Er ist verantwortlich für die Anzeige des Shop-Rasters, die Handhabung des Formulars zur Auswahl verfügbarer Sprachen und Währungen für einen bestimmten Shop und das Speichern dieser Einstellungen in der Datenbank. Er verwendet wahrscheinlich `HelperList` für das Shop-Raster und `HelperForm` für die shop-spezifische Konfiguration.
    - **Tab-Name**: „Multistore Lokalisierungsregeln“ (oder ähnlich, definiert in der Methode `installTab()`).
  - `multishoplang/controllers/admin/index.php`
    - **Klassenname & Elternklasse**: Dies ist typischerweise eine leere Datei oder eine Datei, die eine Sicherheitsanweisung `die()` enthält, um den direkten Zugriff auf das Verzeichnis zu verhindern. Sie repräsentiert keinen aktiven Controller.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul stützt sich stark auf Overrides, um das Kernverhalten von PrestaShop zu modifizieren.

- `multishoplang/override/classes/Currency.php`
  - **Klassenname & Elternklasse**: `Currency` (überschreibt die Kernklasse `Currency` von PrestaShop).
  - **Verantwortlichkeit**: Dieser Override fängt Aufrufe im Zusammenhang mit dem Abrufen und Auswählen von Währungen ab. Er modifiziert Methoden wie `getCurrencies()` oder `getDefaultCurrency()`, um die Liste der verfügbaren Währungen basierend auf der Konfiguration des aktuellen Shops, wie sie vom Modul definiert wurde, zu filtern. Er stellt sicher, dass nur Währungen, die für den aktiven Shop aktiviert sind, im Front Office präsentiert werden.
- `multishoplang/override/classes/Language.php`
  - **Klassenname & Elternklasse**: `Language` (überschreibt die Kernklasse `Language` von PrestaShop).
  - **Verantwortlichkeit**: Ähnlich wie der `Currency`-Override fängt diese Klasse sprachbezogene Aufrufe ab. Sie modifiziert Methoden wie `getLanguages()` oder `getDefaultLanguage()`, um die Liste der verfügbaren Sprachen basierend auf der Konfiguration des aktuellen Shops zu filtern. Sie stellt sicher, dass nur Sprachen, die für den aktiven Shop aktiviert sind, im Front Office präsentiert werden.
- `multishoplang/override/classes/index.php`
  - **Klassenname & Elternklasse**: Dies ist typischerweise eine leere Datei oder eine Datei, die eine Sicherheitsanweisung `die()` enthält, um den direkten Zugriff auf das Verzeichnis zu verhindern. Sie repräsentiert keine aktive Klasse.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul enthält keine benutzerdefinierten JavaScript-Dateien. Alle Interaktionen im Back Office werden von den Standard-JavaScript-Dateien `HelperForm` und `HelperList` von PrestaShop verarbeitet, und das Front-Office-Verhalten wird durch die Klassen-Overrides verwaltet.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul enthält keine benutzerdefinierten CSS-Dateien. Seine Back-Office-Oberfläche basiert auf dem Standard-Admin-Theme-Styling von PrestaShop. Die Front-Office-Anzeige wird durch das aktive Theme gesteuert.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**: Keine explizit aufgeführt, aber die Logik des Moduls arbeitet hauptsächlich über Klassen-Overrides und nicht über direkte Hook-Templates.
- **Admin-Templates (`views/templates/admin/`)**:
  - `multishoplang/views/advert.tpl`
    - **Zweck**: Wahrscheinlich ein Template zur Anzeige von Werbebotschaften oder Informationen über andere MyPresta.eu-Module innerhalb der Konfigurationsoberfläche des Moduls.
  - `multishoplang/views/currenciesForm.tpl`
    - **Zweck**: Dieses Template wird innerhalb des `AdminMultirulesController` verwendet, um den Formularabschnitt zur Konfiguration verfügbarer Währungen und der Standardwährung für einen bestimmten Shop zu rendern. Es enthält Kontrollkästchen für Währungen und ein Dropdown-Menü für den Standardwert.
  - `multishoplang/views/languagesForm.tpl`
    - **Zweck**: Dieses Template wird innerhalb des `AdminMultirulesController` verwendet, um den Formularabschnitt zur Konfiguration verfügbarer Sprachen und der Standardsprache für einen bestimmten Shop zu rendern. Es enthält Kontrollkästchen für Sprachen und ein Dropdown-Menü für den Standardwert.
- **Front-Office-Templates (`views/templates/front/`)**: Keine.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - `ps_multirule`: Dies ist die benutzerdefinierte Tabelle, die vom Modul erstellt wurde, um die Lokalisierungsregeln zu speichern. Sie enthält wahrscheinlich Felder wie:
    - `id_shop`: Fremdschlüssel, der auf `ps_shop.id_shop` verweist.
    - `id_lang_default`: Die Standard-Sprach-ID für diesen Shop.
    - `id_currency_default`: Die Standard-Währungs-ID für diesen Shop.
    - `available_languages`: Ein serialisiertes Array oder eine kommagetrennte Zeichenfolge von `id_lang`-Werten, die für den Shop aktiviert sind.
    - `available_currencies`: Ein serialisiertes Array oder eine kommagetrennte Zeichenfolge von `id_currency`-Werten, die für den Shop aktiviert sind.
  - Konfigurationseinträge werden in `ps_configuration` für allgemeine Moduleinstellungen (falls vorhanden) gespeichert.
- **Registrierte Hooks-Tabelle**:
  Das Modul arbeitet hauptsächlich über Klassen-Overrides und nicht über direkte Hook-Ausführung im Front Office. Es registriert jedoch Standard-Back-Office-Hooks für seine Verwaltungsoberfläche.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller geladen wird | Zum Laden modulspezifischer CSS/JS (obwohl in diesem Modul keine vorhanden sind). |
| `displayBackOfficeHeader` | Im Header des Back Office | Potenziell zur Anzeige modulspezifischer Warnungen oder Hinweise. |
| `moduleRoutes` | Während der URL-Routing-Initialisierung | Wenn das Modul benutzerdefinierte Front-Office-Routen definiert hat (hier nicht zutreffend). |
| `actionObjectLanguageAddAfter` | Nachdem eine neue Sprache hinzugefügt wurde | Um die internen Daten des Moduls für neue Sprachen potenziell zu aktualisieren. |
| `actionObjectCurrencyAddAfter` | Nachdem eine neue Währung hinzugefügt wurde | Um die internen Daten des Moduls für neue Währungen potenziell zu aktualisieren. |
| `actionShopDataDuplication` | Wenn ein Shop dupliziert wird | Um sicherzustellen, dass Lokalisierungsregeln für den neuen Shop kopiert werden. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support wenden Sie sich bitte an Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, den reibungslosen Betrieb und die kontinuierliche Verbesserung Ihrer PrestaShop-Module sicherzustellen.
