---
title: "Währung und Sprache nach Land – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Währung und Sprache nach Land“ von MyPresta.eu."
sidebar:
  label: "Währung und Sprache nach Land – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Currency and language by country auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/currency-and-language-by-country.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/currency-and-language-by-country/)
>
> ---


# Währung und Sprache nach Land

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst erforderlich und auf jeder modernen Hosting-Umgebung verfügbar. Für dieses Modul sind keine speziellen Erweiterungen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Alle Einstellungen nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Haupt- und einzige Konfigurationsbildschirm für das Modul „Währung und Sprache nach Land“. Hier finden Sie alle Einstellungen, um zu definieren, wie sich Ihr Shop an Besucher aus bestimmten Ländern anpasst.

**Zugriff:** Back Office > Module > Modul-Manager > Suchen Sie nach „Währung und Sprache nach Land“ > Klicken Sie auf „Konfigurieren“.

#### **1. Land auswählen**

- **Was diese Einstellung bewirkt:** Dieses Dropdown-Menü ermöglicht es Ihnen, das spezifische Land auszuwählen, für das Sie die automatischen Sprach- und Währungsänderungen anwenden möchten.
- **Auswirkung der Änderung dieser Einstellung:** Wenn Sie ein Land auswählen (z.B. „Frankreich“), wendet das Modul die unten definierten Sprach- und Währungseinstellungen *nur* für Besucher an, die aus diesem Land stammen. Wenn Sie kein Land auswählen, wendet das Modul keine Geolokalisierungsregeln an.
- **Empfohlener Wert:** Wählen Sie zuerst das Land aus, das Sie ansprechen möchten. Mit dieser kostenlosen Version können Sie jeweils nur ein Land konfigurieren.
- **Händlerszenario / Beispiel:** Wenn Besucher aus Deutschland Ihren Shop auf Deutsch mit Euro-Währung sehen sollen, würden Sie hier „Deutschland“ auswählen.

#### **2. Sprachwechsel nach Besucher aktivieren**

- **Was diese Einstellung bewirkt:** Dieser Schalter steuert, ob das Modul die Sprache des Shops für Besucher aus dem ausgewählten Land automatisch ändern soll.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert („Aktiviert“):* Das Modul versucht, die Front-Office-Sprache des Shops auf die Sprache umzustellen, die Sie in der Einstellung „Sprache auswählen“ unten für Besucher aus dem ausgewählten Land angeben.
  - *Wenn deaktiviert („Deaktiviert“):* Die Sprache wird nicht automatisch geändert, selbst wenn Sie unten eine Sprache ausgewählt haben. Der Besucher sieht den Shop in Ihrer Standardsprache oder der bevorzugten Sprache seines Browsers (sofern das Standardverhalten von PrestaShop dies zulässt).
- **Empfohlener Wert:** „Aktiviert“, wenn Sie ein lokalisiertes Spracherlebnis bieten möchten.
- **Händlerszenario / Beispiel:** Wenn Sie „Frankreich“ als Land ausgewählt haben, bedeutet die Aktivierung dieser Einstellung, dass Sie dann „Französisch“ als Sprache für französische Besucher auswählen können.

#### **3. Sprache auswählen**

- **Was diese Einstellung bewirkt:** Dieses Dropdown-Menü erscheint nur, wenn „Sprachwechsel nach Besucher aktivieren“ aktiviert ist. Es ermöglicht Ihnen, auszuwählen, welche Sprache für Besucher aus dem ausgewählten Land eingestellt wird.
- **Auswirkung der Änderung dieser Einstellung:** Die Front-Office-Sprache des Shops wechselt für Besucher aus dem ausgewählten Land automatisch zur ausgewählten Sprache. Stellen Sie sicher, dass diese Sprache bereits in Ihrem PrestaShop-Shop installiert und aktiviert ist (Back Office > International > Sprachen).
- **Empfohlener Wert:** Die Amtssprache des von Ihnen ausgewählten Landes.
- **Händlerszenario / Beispiel:** Wenn Sie „Spanien“ als Land ausgewählt und den Sprachwechsel aktiviert haben, würden Sie hier „Spanisch“ auswählen.

#### **4. Währungswechsel nach Besucher aktivieren**

- **Was diese Einstellung bewirkt:** Dieser Schalter steuert, ob das Modul die Währung des Shops für Besucher aus dem ausgewählten Land automatisch ändern soll.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert („Aktiviert“):* Das Modul versucht, die Front-Office-Währung des Shops auf die Währung umzustellen, die Sie in der Einstellung „Währung auswählen“ unten für Besucher aus dem ausgewählten Land angeben.
  - *Wenn deaktiviert („Deaktiviert“):* Die Währung wird nicht automatisch geändert. Die Preise werden in der Standardwährung Ihres Shops oder der vom Kunden manuell ausgewählten Währung angezeigt.
- **Empfohlener Wert:** „Aktiviert“, wenn Sie Preise in der lokalen Währung anzeigen möchten.
- **Händlerszenario / Beispiel:** Wenn Sie „Vereinigte Staaten“ als Land ausgewählt haben, bedeutet die Aktivierung dieser Einstellung, dass Sie dann „US-Dollar“ als Währung für US-Besucher auswählen können.

#### **5. Währung auswählen**

- **Was diese Einstellung bewirkt:** Dieses Dropdown-Menü erscheint nur, wenn „Währungswechsel nach Besucher aktivieren“ aktiviert ist. Es ermöglicht Ihnen, auszuwählen, welche Währung für Besucher aus dem ausgewählten Land eingestellt wird.
- **Auswirkung der Änderung dieser Einstellung:** Alle Preise im Front-Office des Shops wechseln für Besucher aus dem ausgewählten Land automatisch zur ausgewählten Währung. Stellen Sie sicher, dass diese Währung bereits in Ihrem PrestaShop-Shop installiert und aktiviert ist (Back Office > International > Währungen).
- **Empfohlener Wert:** Die offizielle Währung des von Ihnen ausgewählten Landes.
- **Händlerszenario / Beispiel:** Wenn Sie „Japan“ als Land ausgewählt und den Währungswechsel aktiviert haben, würden Sie hier „Japanischer Yen“ auswählen.

#### **Wichtiger Hinweis zu Overrides:**

Dieses Modul verwendet das Override-System von PrestaShop, um das Kernverhalten von Währung und Sprache zu ändern. Wenn Sie andere Module haben, die ebenfalls Overrides für `Currency.php` oder `Language.php` verwenden, kann es zu Konflikten kommen. Testen Sie immer gründlich nach der Installation.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Land auswählen | Ihr Zielland | Definiert das Land, für das die Regeln gelten. |
| Modulkonfiguration | Sprachwechsel nach Besucher aktivieren | Aktiviert | Aktiviert die automatische Sprachumschaltung für das ausgewählte Land. |
| Modulkonfiguration | Sprache auswählen | Amtssprache des Landes | Legt die spezifische Sprache für Besucher aus dem ausgewählten Land fest. |
| Modulkonfiguration | Währungswechsel nach Besucher aktivieren | Aktiviert | Aktiviert die automatische Währungsumschaltung für das ausgewählte Land. |
| Modulkonfiguration | Währung auswählen | Amtliche Währung des Landes | Legt die spezifische Währung für Besucher aus dem ausgewählten Land fest. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Die Sprache/Währung ändert sich für Besucher aus dem ausgewählten Land nicht. Was sollte ich überprüfen?**
A:

1. **Modul aktiviert:** Stellen Sie sicher, dass das Modul „Währung und Sprache nach Land“ im Modul-Manager installiert und aktiviert ist.
2. **Konfiguration gespeichert:** Überprüfen Sie nochmals, ob Sie ein Land ausgewählt, die entsprechenden Optionen für Sprach-/Währungswechsel aktiviert, die richtige Sprache/Währung gewählt und auf der Konfigurationsseite des Moduls auf „Speichern“ geklickt haben.
3. **Sprache/Währung installiert & aktiviert:** Vergewissern Sie sich, dass die Zielsprache und -währung in Ihrem PrestaShop Back Office installiert und aktiviert sind (International > Sprachen und International > Währungen).
4. **Cache:** Leeren Sie Ihren PrestaShop-Cache (Erweiterte Einstellungen > Leistung > Cache leeren) und Ihren Browser-Cache.
5. **Genauigkeit der Geolokalisierung:** Geolokalisierungsdienste sind nicht immer zu 100 % genau. Testen Sie mit einem VPN, um sicherzustellen, dass Ihre IP-Adresse korrekt als aus dem Zielland stammend identifiziert wird.

**F: Kann ich verschiedene Sprachen/Währungen für mehrere Länder konfigurieren?**
A: Das kostenlose Modul „Währung und Sprache nach Land“ ermöglicht es Ihnen, Regeln für nur ein Land gleichzeitig zu konfigurieren. Wenn Sie eine erweiterte Multi-Länder-Ausrichtung benötigen, sollten Sie ein Upgrade auf das Modul „Geolocation Pro“ von MyPresta.eu in Betracht ziehen, das umfangreichere Funktionen bietet.

**F: Die Standardsprache/-währung meines Shops wird auch nach der Konfiguration noch angezeigt.**
A: Dieses Modul zielt speziell auf Besucher aus dem *ausgewählten* Land ab. Für alle anderen Besucher gelten die Standardsprache und -währung Ihres Shops oder die bevorzugten Browsereinstellungen, wenn PrestaShop so konfiguriert ist, dass es diese berücksichtigt. Stellen Sie sicher, dass Sie aus genau dem Land testen, das Sie konfiguriert haben.

**F: Ich habe ein anderes Modul installiert, und jetzt funktioniert der Sprach-/Währungswechsel nicht mehr.**
A: Dieses Modul verwendet das Override-System von PrestaShop. Wenn ein anderes Modul ebenfalls `classes/Currency.php` oder `classes/Language.php` überschreibt, kann es zu einem Konflikt kommen. Überprüfen Sie Ihre `app/config/parameters.php` (für PS 1.7+) oder `config/settings.inc.php` (für PS 1.6) auf `_PS_MODE_DEV_` und setzen Sie es auf `true`, um Fehlermeldungen anzuzeigen. Möglicherweise müssen Sie den Support kontaktieren, um Hilfe bei der Lösung von Override-Konflikten zu erhalten.

**F: Wie erkennt das Modul das Land des Besuchers?**
A: Das Modul verwendet die IP-Adresse des Besuchers, um dessen geografischen Standort zu bestimmen. Dies ist eine Standardmethode für die Geolokalisierung.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster, die mit dem Modul „Währung und Sprache nach Land“ arbeiten.

### 4.1 Architekturübersicht

Das Modul „Währung und Sprache nach Land“ (`freegeo`) ist ein leichtgewichtiges PrestaShop-Modul, das hauptsächlich dazu dient, die Standardsprache und -währung basierend auf der IP-Adresse eines Besuchers zu ändern. Dies wird erreicht, indem das Override-System von PrestaShop für die Kernklassen `Currency` und `Language` genutzt und in das `actionDispatcherBefore`-Ereignis eingehängt wird, um die Geolokalisierungslogik auszuführen, bevor der Hauptseiteninhalt gerendert wird. Die Konfiguration des Moduls wird über die Standardmethode `getContent()` in der Hauptmoduldatei gehandhabt.

### 4.2 Controller (`controllers/`)

Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Controller ein. Seine Logik wird hauptsächlich über Hooks und Klassen-Overrides ausgeführt.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul nutzt das Override-System von PrestaShop, um seine Logik in Kernfunktionen zu injizieren.

- **`freegeo/override/classes/Currency.php`**

  - **Klassenname:** `Currency` (überschreibt die Kernklasse `Currency`)
  - **Elternklasse:** `CurrencyCore`
  - **Verantwortlichkeit:** Dieser Override ist entscheidend für die Festlegung der Währung basierend auf der Geolokalisierung. Er ändert das Verhalten, wie die aktive Währung bestimmt wird. Die Modullogik innerhalb dieses Overrides prüft, ob die Einstellung `FREEGEO_CURRENCY_ON` aktiviert ist und ob das Land des Besuchers mit dem konfigurierten `FREEGEO_COUNTRY` übereinstimmt. Wenn ja, versucht es, die Währung auf `FREEGEO_CURRENCY` zu erzwingen.
  - **Schlüsselmethoden:** Der Override modifiziert wahrscheinlich Methoden, die mit `getCurrent()` oder `getCurrency()` zusammenhängen, um die geolokalisierte Währungs-ID zu injizieren.
- **`freegeo/override/classes/Language.php`**

  - **Klassenname:** `Language` (überschreibt die Kernklasse `Language`)
  - **Elternklasse:** `LanguageCore`
  - **Verantwortlichkeit:** Ähnlich dem `Currency`-Override ist diese Klasse für die Festlegung der Sprache basierend auf der Geolokalisierung verantwortlich. Sie prüft `FREEGEO_LANGUAGE_ON` und `FREEGEO_COUNTRY` und erzwingt, wenn die Bedingungen erfüllt sind, die Sprache auf `FREEGEO_LANGUAGE`.
  - **Schlüsselmethoden:** Der Override modifiziert wahrscheinlich Methoden, die mit `getCurrentLanguage()` oder `getLanguage()` zusammenhängen, um die geolokalisierte Sprach-ID zu injizieren.
- **`freegeo/override/classes/index.php`**

  - **Zweck:** Dies ist eine standardmäßige leere `index.php`-Datei, die typischerweise in Verzeichnissen platziert wird, um die Verzeichnisauflistung auf Webservern zu verhindern und die Sicherheit zu erhöhen. Sie hat keine funktionale Auswirkung auf die Modullogik.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien. Alle seine Funktionen werden serverseitig verarbeitet.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält keine benutzerdefinierten CSS-Dateien. Seine Funktionalität beinhaltet keine spezifische Front-Office-Gestaltung.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **`freegeo/views/advert.tpl`**
  - **Geltungsbereich:** Back-Office (Modulkonfigurationsseite).
  - **Zweck:** Dieses Template wird wahrscheinlich verwendet, um eine Werbung oder Werbebotschaft für das Modul „Geolocation Pro“ von MyPresta.eu auf der Konfigurationsseite des Moduls anzuzeigen. Es dient als Marketingelement innerhalb der Admin-Oberfläche.
  - **Hook:** Dieses Template wird innerhalb der Methode `getContent()` der Hauptmoduldatei gerendert, typischerweise vor oder nach dem Hauptkonfigurationsformular.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es speichert seine Konfigurationseinstellungen direkt in der `ps_configuration`-Tabelle von PrestaShop.
- **Konfigurationseinträge in `ps_configuration`**:

  - `FREEGEO_CURRENCY_ON`: Speichert einen booleschen Wert (0 oder 1), der angibt, ob der Währungswechsel aktiviert ist.
  - `FREEGEO_LANGUAGE_ON`: Speichert einen booleschen Wert (0 oder 1), der angibt, ob der Sprachwechsel aktiviert ist.
  - `FREEGEO_CURRENCY`: Speichert die ID der einzustellenden Währung (z.B. `id_currency`).
  - `FREEGEO_LANGUAGE`: Speichert die ID der einzustellenden Sprache (z.B. `id_lang`).
  - `FREEGEO_COUNTRY`: Speichert den ISO-Code oder die ID des Ziellandes.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin Controller seine Medien-Assets (JS/CSS) setzt. | Obwohl aufgeführt, verwendet dieses Modul es wahrscheinlich minimal oder für spezifisches Laden von Admin-seitigen Skripten/Stilen, falls vorhanden (keine im Inventar gefunden). |
| `actionDispatcherBefore` | Wird sehr früh im PrestaShop-Anfragezyklus ausgeführt, bevor der Dispatcher die URL verarbeitet. | **KRITISCHER HOOK:** Hier befindet sich die Kern-Geolokalisierungslogik des Moduls. Er wird verwendet, um die IP des Besuchers zu erkennen, sein Land zu bestimmen und dann, basierend auf den Moduleinstellungen, möglicherweise `Context::getContext()->language` und `Context::getContext()->currency` zu überschreiben, bevor die Seite gerendert wird. |
| `actionFrontControllerAfterInit` | Wird ausgeführt, nachdem ein Front Controller initialisiert wurde. | Dieser Hook könnte verwendet werden, um zusätzliche Prüfungen oder Anpassungen durchzuführen, nachdem der Hauptcontroller eingerichtet wurde, aber vor dem Rendern. Er könnte als Fallback oder ergänzender Punkt für Sprach-/Währungsanpassungen dienen, wenn `actionDispatcherBefore` nicht in allen Szenarien ausreicht. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Währung und Sprache nach Land“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.
