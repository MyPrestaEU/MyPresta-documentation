---
title: "Versanddienstleister-Verfügbarkeit nach Warenkorbwert – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Versanddienstleister-Verfügbarkeit nach Warenkorbwert' von MyPresta.eu."
sidebar:
  label: "Versanddienstleister-Verfügbarkeit nach Warenkorbwert – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Carrier availability by cart value auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/carrier-availability-by-cart-value.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/carrier-availability-by-cart-value/)
>
> ---


# Versanddienstleister-Verfügbarkeit nach Warenkorbwert

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst erforderlich und sind normalerweise in jeder modernen Hosting-Umgebung verfügbar.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zur Hauptkonfigurationsseite des Moduls.

- **Was diese Einstellung bewirkt:** Dieser Bildschirm behandelt hauptsächlich allgemeine Moduleinstellungen, oft im Zusammenhang mit Updates oder grundlegenden Funktionen.
- **Auswirkungen der Änderung dieser Einstellung:**
  - `mypresta_updates`: Dies ist eine gängige Einstellung bei MyPresta.eu-Modulen.
    - *Wenn aktiviert:* Das Modul sucht regelmäßig nach neuen Versionen und Updates von MyPresta.eu. Dies hilft Ihnen, mit Fehlerbehebungen und neuen Funktionen auf dem Laufenden zu bleiben.
    - *Wenn deaktiviert:* Das Modul sucht nicht automatisch nach Updates. Sie müssten manuell auf MyPresta.eu nach neuen Versionen suchen.
  - `update_` und `updatev_`: Dies sind interne Einstellungen, die vom Update-Mechanismus des Moduls verwendet werden, um die letzte Überprüfung und die verfügbare Version zu verfolgen. Sie müssen normalerweise nicht direkt mit diesen interagieren.
- **Empfohlener Wert:**
  - Für `mypresta_updates`: **JA** (Aktiviert). Es wird immer empfohlen, Module für Sicherheit, Leistung und neue Funktionen auf dem neuesten Stand zu halten.
- **Händlerszenario / Beispiel:** Die Aktivierung von Updates stellt sicher, dass Ihr Modul immer die neueste Version verwendet, wodurch potenzielle Kompatibilitätsprobleme mit zukünftigen PrestaShop-Updates oder anderen Modulen vermieden werden.

### 2.2 Dedizierter Admin-Bildschirm: Regeln für die Verfügbarkeit von Versanddienstleistern

Dies ist der Kern des Moduls, wo Sie die Regeln für die Verfügbarkeit von Versanddienstleistern basierend auf dem Warenkorbwert definieren.

- **Bildschirmname & Menüpfad:**

  - Navigieren Sie in Ihrem PrestaShop Back Office zu **Versand > Versanddienstleister-Verfügbarkeit nach Bestellwert**.
  - Dies öffnet einen neuen dedizierten Bildschirm, auf dem Sie Ihre Regeln verwalten können.
- **Verfügbare Aktionen & Einstellungen:**
  Dieser Bildschirm zeigt eine Liste bestehender Regeln an und ermöglicht es Ihnen, neue hinzuzufügen oder bestehende zu bearbeiten/löschen.

  **Spalten der Listentabelle:**

  - **ID**: Eindeutiger Bezeichner für die Regel.
  - **Versanddienstleister**: Der Name des Versanddienstleisters, für den die Regel gilt.
  - **Bestellwert_von**: Der Mindestwert des Warenkorbs, damit dieser Versanddienstleister verfügbar ist.
  - **Bestellwert_bis**: Der Höchstwert des Warenkorbs, damit dieser Versanddienstleister verfügbar ist.
  - **Aktiv**: Ein Schalter zum Aktivieren oder Deaktivieren der Regel, ohne sie zu löschen.

  **Hinzufügen/Bearbeiten einer Regel (Formularfelder):**
  Wenn Sie auf „Neue Regel hinzufügen“ klicken oder eine bestehende bearbeiten, sehen Sie ein Formular mit den folgenden Feldern:

  - **Versanddienstleister-Verfügbarkeit nach Bestellwert**: Dies ist eine Dropdown-Liste, in der Sie den spezifischen Versanddienstleister auswählen, für den Sie die Regel anwenden möchten.

    - *Auswirkung:* Die von Ihnen definierte Regel beeinflusst nur die Verfügbarkeit des ausgewählten Versanddienstleisters.
    - *Empfohlener Wert:* Wählen Sie den Versanddienstleister aus, den Sie verwalten möchten.
    - *Händlerszenario:* Wenn Sie „Express-Lieferung“ auf hochpreisige Bestellungen beschränken möchten, wählen Sie hier „Express-Lieferung“.
  - **Bestellwert von**: Geben Sie den minimalen Gesamtwert des Warenkorbs (in Ihrer Standardwährung) ein, damit dieser Versanddienstleister verfügbar ist.

    - *Auswirkung:* Wenn der Warenkorbwert des Kunden unter diesem Betrag liegt, wird der ausgewählte Versanddienstleister während des Checkouts nicht angezeigt.
    - *Empfohlener Wert:* Geben Sie `0` ein, wenn es keinen Mindestwert gibt, oder einen bestimmten Betrag (z. B. `50.00`).
    - *Händlerszenario:* Auf `50.00` setzen, damit „Kostenloser Versand“ nur für Bestellungen über 50 € angezeigt wird.
  - **Bestellwert bis**: Geben Sie den maximalen Gesamtwert des Warenkorbs (in Ihrer Standardwährung) ein, damit dieser Versanddienstleister verfügbar ist.

    - *Auswirkung:* Wenn der Warenkorbwert des Kunden über diesem Betrag liegt, wird der ausgewählte Versanddienstleister während des Checkouts nicht angezeigt.
    - *Empfohlener Wert:* Leer lassen oder auf `0` setzen, wenn es keinen Höchstwert gibt, oder einen bestimmten Betrag (z. B. `200.00`).
    - *Händlerszenario:* Auf `200.00` setzen für „Standardversand“, um zu verhindern, dass er für sehr hochpreisige Bestellungen gewählt wird, die „Versicherter Versand“ verwenden sollten.
  - **Aktiv**: Ein einfacher EIN/AUS-Schalter.

    - *Auswirkung:*
      - *Wenn aktiviert:* Die Regel ist aktiv und filtert die Verfügbarkeit der Versanddienstleister.
      - *Wenn deaktiviert:* Die Regel wird ignoriert, und der Versanddienstleister ist basierend auf anderen PrestaShop-Einstellungen (Gewicht, Preis, Zonen) unabhängig vom Warenkorbwert verfügbar.
    - *Empfohlener Wert:* **EIN** für aktive Regeln.
    - *Händlerszenario:* Eine Regel während einer Aktion vorübergehend deaktivieren, ohne sie zu löschen.
  - **Speichern**: Klicken Sie auf diese Schaltfläche, um Ihre Änderungen zu übernehmen oder die neue Regel zu erstellen.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**

  1. **Identifizieren Sie Ihre Versanddienstleister:** Listen Sie alle Ihre Versanddienstleister und deren beabsichtigte Anwendungsfälle auf.
  2. **Definieren Sie Wertebereiche:** Entscheiden Sie für jeden Versanddienstleister, ob es einen spezifischen Warenkorbwertbereich gibt, in dem er verfügbar sein sollte.
     - *Beispiel 1:* „Economy-Versand“ für Bestellungen von 0 € bis 75 €.
     - *Beispiel 2:* „Standardversand“ für Bestellungen von 75 € bis 250 €.
     - *Beispiel 3:* „Premium versichert“ für Bestellungen ab 250 € (setzen Sie „Bestellwert von“ auf 250, lassen Sie „Bestellwert bis“ leer/0).
  3. **Regeln hinzufügen:** Gehen Sie zu **Versand > Versanddienstleister-Verfügbarkeit nach Bestellwert** und klicken Sie auf „Neue Regel hinzufügen“.
  4. **Jede Regel konfigurieren:** Wählen Sie den Versanddienstleister aus, geben Sie „Bestellwert von“ und „Bestellwert bis“ ein und stellen Sie sicher, dass „Aktiv“ auf EIN steht.
  5. **Gründlich testen:** Führen Sie nach dem Einrichten Ihrer Regeln Testkäufe mit verschiedenen Warenkorbwerten durch, um sicherzustellen, dass die Versanddienstleister wie erwartet angezeigt werden.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | `mypresta_updates` | JA (Aktiviert) | Aktiviert automatische Prüfungen auf Modul-Updates. |
| Regeln für die Verfügbarkeit von Versanddienstleistern | Versanddienstleister | Aus Liste auswählen | Der spezifische Versanddienstleister, für den diese Regel gilt. |
| Regeln für die Verfügbarkeit von Versanddienstleistern | Bestellwert von | `0` oder spezifischer Betrag | Mindestwert des Warenkorbs, damit der Versanddienstleister verfügbar ist. |
| Regeln für die Verfügbarkeit von Versanddienstleistern | Bestellwert bis | `0` (kein Max) oder spezifischer Betrag | Höchstwert des Warenkorbs, damit der Versanddienstleister verfügbar ist. |
| Regeln für die Verfügbarkeit von Versanddienstleistern | Aktiv | EIN | Aktiviert oder deaktiviert die spezifische Regel zur Verfügbarkeit des Versanddienstleisters. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe Regeln eingerichtet, aber die Versanddienstleister ändern sich im Checkout nicht. Was ist falsch?**
A1:

- **Cache leeren:** Leeren Sie immer Ihren PrestaShop-Cache, nachdem Sie Modulkonfigurationsänderungen vorgenommen haben. Gehen Sie zu **Erweiterte Einstellungen > Performance** und klicken Sie dann oben rechts auf „Cache leeren“.
- **Regelkonflikte:** Überprüfen Sie, ob Sie widersprüchliche Regeln haben. Wenn beispielsweise Versanddienstleister A von 0 € bis 100 € und Versanddienstleister B von 50 € bis 150 € eingestellt ist, stellen Sie sicher, dass Ihre Bereiche logisch sind.
- **Status des Versanddienstleisters:** Stellen Sie sicher, dass die Versanddienstleister selbst aktiv und in **Versand > Versanddienstleister** in PrestaShop korrekt konfiguriert sind. Dieses Modul filtert nur *verfügbare* Versanddienstleister, es aktiviert keine inaktiven.
- **Andere Versanddienstleister-Einschränkungen:** Denken Sie daran, dass PrestaShop eigene Versanddienstleister-Einschränkungen (nach Zone, Gewicht, Preis) hat. Dieses Modul *fügt* eine weitere Filterebene hinzu. Wenn ein Versanddienstleister bereits durch das Gewicht eingeschränkt ist, wird dieses Modul ihn nicht verfügbar machen.

**F2: Mein Währungssymbol wird nicht korrekt angezeigt, oder die Werte scheinen falsch zu sein.**
A2: Das Modul verwendet die Standardwährung Ihres Shops für die Felder „Bestellwert von“ und „Bestellwert bis“. Stellen Sie sicher, dass Ihre Standardwährung in **International > Währungen** korrekt eingestellt ist. Das Modul arbeitet mit dem numerischen Wert, daher dient das im Back Office angezeigte Symbol nur zu Ihrer Referenz.

**F3: Kann ich dieses Modul mit anderen Versandmodulen verwenden?**
A3: Ja, im Allgemeinen. Dieses Modul greift in den Standard-PrestaShop-Prozess zum Filtern von Versanddienstleisterlisten ein. Es wendet seine Regeln *nachdem* andere PrestaShop-Kernbedingungen (wie Gewicht, Preis, Zone) die Liste der potenziellen Versanddienstleister bereits eingegrenzt haben. Wenn ein anderes Modul ebenfalls Versanddienstleister filtert, gelten die restriktivsten Regeln aller Module.

**F4: Wie mache ich einen Versanddienstleister *immer* verfügbar, unabhängig vom Warenkorbwert?**
A4: Sie müssen keine Regel für einen solchen Versanddienstleister erstellen. Wenn ein Versanddienstleister nicht in Ihren Regeln für die „Versanddienstleister-Verfügbarkeit nach Bestellwert“ aufgeführt ist, bleibt er basierend auf den Standard-Versanddienstleister-Einstellungen von PrestaShop (Gewicht, Preis, Zone usw.) ohne Einschränkungen durch den Warenkorbwert dieses Moduls verfügbar.

**F5: Das Modul scheint meinen Checkout zu verlangsamen. Ist das normal?**
A5: Dieses Modul ist leichtgewichtig konzipiert und sollte die Leistung nicht wesentlich beeinträchtigen. Wenn Sie eine Verlangsamung bemerken, stellen Sie sicher, dass Ihre PrestaShop-Installation optimiert ist (z. B. Caching aktiviert, neueste PHP-Version, keine übermäßigen Module). Wenn das Problem weiterhin besteht, wenden Sie sich mit Details zu Ihrer Einrichtung an den MyPresta.eu-Support.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Versanddienstleister-Verfügbarkeit nach Warenkorbwert“ (`cbp`) folgt der Standard-PrestaShop-Modularchitektur und nutzt hauptsächlich einen AdminController für die Konfiguration und einen Front-Office-Hook, um die Versanddienstleisterliste während des Checkouts zu ändern. Es verwendet ein benutzerdefiniertes `ObjectModel`, um Regeln für die Verfügbarkeit von Versanddienstleistern in einer eigenen Datenbanktabelle zu verwalten.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:
  Dieses Modul enthält keine dedizierten Front-Office-Controller. Die gesamte Front-Office-Logik wird direkt über einen Hook in der Hauptmoduldatei (`cbp.php`) abgewickelt.
- **Back-Office-Admin-Controller**:

  - `cbp/controllers/admin/AdminCbpr.php`

    - **Klassenname:** `AdminCbprController` (erweitert `ModuleAdminController`)
    - **Verantwortlichkeit:** Dies ist die primäre administrative Schnittstelle zur Verwaltung von Regeln für die Verfügbarkeit von Versanddienstleistern. Sie verwaltet die CRUD-Operationen (Create, Read, Update, Delete) für die `cbpr`-Entität.
    - **Tab-Name:** „Versanddienstleister-Verfügbarkeit nach Bestellwert“ (unter dem Menü Versand).
    - **Verwaltete Entität:** `Cbpr` (das benutzerdefinierte `ObjectModel` für Versanddienstleister-Regeln).
    - **Hauptmerkmale:**
      - Zeigt eine `list`-Ansicht aller konfigurierten Regeln an, einschließlich ID, Name des Versanddienstleisters, Bestellwert_von, Bestellwert_bis und Aktiv-Status.
      - Bietet `add`- und `edit`-Formulare für einzelne Regeln, die die Auswahl eines Versanddienstleisters und die Eingabe von Min-/Max-Bestellwerten ermöglichen.
      - Verwaltet Formularübermittlungen und Datenbankinteraktionen zum Speichern und Aktualisieren von Regeln.
      - Verwendet `PS_CURRENCY_DEFAULT`, um Währungsinformationen in den Formularen anzuzeigen.
  - `cbp/controllers/admin/index.php`

    - **Verantwortlichkeit:** Diese Datei ist eine standardmäßige leere `index.php`-Datei, die typischerweise in PrestaShop-Verzeichnissen enthalten ist, um die Verzeichnisauflistung aus Sicherheitsgründen zu verhindern. Sie enthält keine funktionale Controller-Logik.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul hat kein dediziertes `classes/`-Verzeichnis. Das primäre `ObjectModel` zur Verwaltung von Versanddienstleister-Regeln ist wahrscheinlich direkt in der Hauptmoduldatei (`cbp/cbp.php`) definiert oder implizit vom `AdminCbprController` unter Verwendung einer dynamischen `ObjectModel`-Definition behandelt.

Da der `AdminCbprController` eine Tabelle namens `cbpr` verwaltet, muss es eine `ObjectModel`-Klasse geben, wahrscheinlich `Cbpr` genannt, die irgendwo definiert ist. Diese Klasse würde die Struktur der Regeln für die Verfügbarkeit von Versanddienstleistern definieren.

**Angenommenes `Cbpr` ObjectModel (wahrscheinlich in `cbp.php`):**

- **Klassenname:** `Cbpr` (erweitert `ObjectModel`)
- **Datenbanktabelle:** `ps_cbpr` (oder `_cbpr` mit Präfix)
- **`$definition`-Felder (erwartet):**
  - `id_cbpr`: Primärschlüssel.
  - `id_carrier`: Fremdschlüssel zur Tabelle `ps_carrier`.
  - `order_from`: Dezimalfeld für den Mindestwert des Warenkorbs.
  - `order_to`: Dezimalfeld für den Höchstwert des Warenkorbs.
  - `active`: Boolesches Feld für den Regelstatus.
- **Schlüsselmethoden:** Standard `ObjectModel`-Methoden für `add()`, `update()`, `delete()`.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul enthält keine benutzerdefinierten JavaScript-Dateien in `views/js/`. Die gesamte Front-Office-Logik wird serverseitig über PHP-Hooks abgewickelt. Back-Office-Formulare basieren auf der Standard-Formularbehandlung von PrestaShop und jQuery.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul enthält keine benutzerdefinierten CSS-Dateien in `views/css/`. Die Back-Office-Oberfläche verwendet das Standard-Styling von PrestaShop für `ModuleAdminController`-Formulare und -Listen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul enthält keine benutzerdefinierten Smarty-Template-Dateien in `views/templates/`. Die Konfigurationsformulare und Listen im Back Office werden mit den Standard-`ModuleAdminController`-Templates von PrestaShop gerendert. Front-Office-Änderungen werden durch direktes Filtern der Versanddienstleisterliste in PHP vorgenommen, nicht durch das Rendern neuer Templates.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - `ps_cbpr`: Diese Tabelle speichert die Regeln für die Verfügbarkeit von Versanddienstleistern.

    - `id_cbpr` INT(10) UNSIGNED NOT NULL AUTO_INCREMENT
    - `id_carrier` INT(10) UNSIGNED NOT NULL
    - `order_from` DECIMAL(20,6) NOT NULL DEFAULT ‘0.000000’
    - `order_to` DECIMAL(20,6) NOT NULL DEFAULT ‘0.000000’
    - `active` TINYINT(1) UNSIGNED NOT NULL DEFAULT ‘1’
    - PRIMARY KEY (`id_cbpr`)
    - KEY `id_carrier` (`id_carrier`)
  - `ps_configuration`: Das Modul speichert seine allgemeinen Einstellungen (wie `mypresta_updates`, `update_`, `updatev_`) in der Tabelle `ps_configuration`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein AdminController initialisiert und seine Medien (JS/CSS) gesetzt werden. | Wird vom Modul verwendet, um seinen benutzerdefinierten AdminController (`AdminCbprController`) in der PrestaShop-Menüstruktur zu registrieren. |
| `actionFilterDeliveryOptionList` | Wird während des Checkout-Prozesses ausgeführt, insbesondere wenn PrestaShop die Liste der verfügbaren Lieferoptionen erstellt. | Dies ist der zentrale Front-Office-Hook. Das Modul verwendet diesen, um die Liste der Versanddienstleister zu durchlaufen, die PrestaShop bereits als verfügbar erachtet hat (basierend auf Zonen, Gewicht, Preis), und filtert diese Liste dann weiter basierend auf dem Gesamtwert des Warenkorbs und den in `ps_cbpr` definierten Regeln. Wenn eine Regel eines Versanddienstleisters nicht mit dem aktuellen Warenkorbwert übereinstimmt, wird er aus der dem Kunden präsentierten Liste entfernt. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul „Versanddienstleister-Verfügbarkeit nach Warenkorbwert“ verweisen wir Sie auf Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, den reibungslosen Betrieb und die kontinuierliche Verbesserung unserer Module sicherzustellen.
