---
title: "Kostenloses Massen-Produktpreis-Update - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Kostenloses Massen-Produkpreis-Update' von MyPresta.eu."
sidebar:
  label: "Kostenloses Massen-Produkpreis-Update - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Free mass products prices update auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/free-mass-products-prices-update.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/free-mass-products-prices-update/)
>
> ---


# Kostenloses Massen-Produkpreis-Update

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind keine speziellen Serverkonfigurationen über eine Standard-PrestaShop-Hosting-Umgebung hinaus erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Kostenloses Massen-Produkpreis-Update)

Dies ist der Haupt- und einzige Konfigurationsbildschirm für das Modul „Kostenloses Massen-Produkpreis-Update“. Hier definieren Sie, wie Sie Ihre Produktpreise anpassen möchten.

#### **Preisanpassungstyp**

- **Was diese Einstellung bewirkt:** Diese entscheidende Einstellung bestimmt, ob Sie Ihre Produktpreise erhöhen oder senken möchten.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf „Erhöhen“ gesetzt:* Das Modul addiert den angegebenen Prozentsatz zum aktuellen Preis jedes Produkts.
  - *Wenn auf „Senken“ gesetzt:* Das Modul subtrahiert den angegebenen Prozentsatz vom aktuellen Preis jedes Produkts.
- **Empfohlener Wert:** Wählen Sie basierend auf Ihrem unmittelbaren Geschäftsanliegen (z.B. „Erhöhen“ für eine allgemeine Preiserhöhung, „Senken“ für einen Verkauf).
- **Händlerszenario / Beispiel:** Wenn Ihre Lieferantenkosten gestiegen sind, würden Sie „Erhöhen“ auswählen. Wenn Sie einen Flash Sale durchführen, würden Sie „Senken“ auswählen.

#### **Prozentwert**

- **Was diese Einstellung bewirkt:** Dieses Feld ermöglicht es Ihnen, den genauen Prozentsatz einzugeben, um den Sie Ihre Preise anpassen möchten.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf „10“ gesetzt:* Wenn „Erhöhen“ ausgewählt ist, steigen die Preise um 10 %. Wenn „Senken“ ausgewählt ist, sinken die Preise um 10 %.
  - *Wenn auf „0“ gesetzt:* Es findet keine Preisänderung statt.
- **Empfohlener Wert:** Geben Sie den genauen Prozentsatz ein, den Sie benötigen. Verwenden Sie ganze Zahlen oder Dezimalzahlen (z.B. „5“ für 5 %, „2.5“ für 2,5 %).
- **Händlerszenario / Beispiel:** Um einen shopweiten Rabatt von 15 % anzubieten, würden Sie „Preisanpassungstyp“ auf „Senken“ und „Prozentwert“ auf „15“ setzen. Um die Preise um 7,5 % zu erhöhen, würden Sie „Preisanpassungstyp“ auf „Erhöhen“ und „Prozentwert“ auf „7.5“ setzen.

#### **Änderungen anwenden-Schaltfläche**

- **Was dies bewirkt:** Diese Schaltfläche initiiert den eigentlichen Preisaktualisierungsprozess.
- **Auswirkung des Klickens auf diese Schaltfläche:** Nach dem Klicken verarbeitet das Modul alle Produkte in Ihrem Shop gemäß dem von Ihnen eingestellten „Preisanpassungstyp“ und „Prozentwert“. **Diese Aktion ist ohne eine Datenbank-Sicherung irreversibel.**
- **Empfohlene Aktion:** Überprüfen Sie immer Ihren „Preisanpassungstyp“ und „Prozentwert“, bevor Sie diese Schaltfläche klicken. Stellen Sie sicher, dass Sie ein aktuelles Datenbank-Backup haben.
- **Händlerszenario / Beispiel:** Nachdem Sie sorgfältig „Senken“ und „20“ für einen Wochenendverkauf eingestellt haben, klicken Sie auf „Änderungen anwenden“, um alle Produktpreise sofort um -20 % zu aktualisieren.

:::warning WICHTIGER HINWEIS
Das Modul „Kostenloses Massen-Produkpreis-Update“ führt eine direkte Aktualisierung Ihrer Produktpreise durch. **Es gibt keine „Rückgängig“-Schaltfläche.** Bevor Sie Änderungen anwenden, ist es **ENTSCHEIDEND**, dass Sie ein vollständiges Backup Ihrer PrestaShop-Datenbank erstellen. Dies ermöglicht es Ihnen, Ihre Preise auf ihren vorherigen Zustand zurückzusetzen, falls Sie einen Fehler machen oder Ihre Meinung ändern.
:::

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Preisanpassungstyp | (Erhöhen/Senken auswählen) | Bestimmt, ob die Preise steigen oder fallen. |
| Modulkonfiguration | Prozentwert | (Gewünschten Prozentsatz eingeben) | Der genaue Prozentsatz für die Preisanpassung. |
| Modulkonfiguration | Änderungen anwenden-Schaltfläche | (Vorsichtig klicken) | Führt die Massen-Preisaktualisierung aus. **Irreversibel ohne Backup.** |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe die Preise aktualisiert, aber sie werden in meinem Shop nicht angezeigt. Was ist falsch?**
A1: Nach jeder signifikanten Datenänderung in PrestaShop, insbesondere in Bezug auf Produkte, ist es eine gute Praxis, den Cache Ihres Shops zu leeren.
\* Gehen Sie in Ihrem Back Office zu **Erweiterte Parameter > Performance**.
\* Klicken Sie oben rechts auf die Schaltfläche „Cache leeren“.
\* Stellen Sie außerdem sicher, dass Ihr Browser-Cache geleert ist, oder versuchen Sie, Ihren Shop in einem Inkognito-/privaten Browserfenster anzuzeigen.

**F2: Ich habe einen Fehler gemacht und die Preise falsch aktualisiert. Wie kann ich das rückgängig machen?**
A2: Wie bereits erwähnt, hat dieses Modul keine „Rückgängig“-Schaltfläche. Deshalb ist ein Datenbank-Backup entscheidend.
\* Wenn Sie *vor* dem Anwenden der Änderungen ein Backup erstellt haben, müssen Sie Ihre Datenbank aus diesem Backup wiederherstellen. Dies erfordert normalerweise den Zugriff auf Ihr Hosting-Kontrollpanel (z.B. cPanel, Plesk) oder die Verwendung eines PrestaShop-Backup-Moduls.
\* Wenn Sie *kein* Backup erstellt haben, müssen Sie die korrekten Preise für Ihre Produkte manuell erneut eingeben oder das Modul erneut mit einer inversen Berechnung verwenden (z.B. wenn Sie um 20 % gesenkt haben, müssten Sie um 25 % erhöhen, um zum ursprünglichen Wert zurückzukehren, aber dies ist aufgrund von Rundungen möglicherweise nicht perfekt genau).

**F3: Beeinflusst dieses Modul spezifische Preise oder Kombinationen?**
A3: Das Modul aktualisiert den *Basispreis* Ihrer Produkte. Es verwaltet nicht direkt spezifische Preise (Rabatte, Mengenrabatte) oder Preiseffekte von Produktkombinationen. Wenn Sie spezifische Preise eingerichtet haben, wirkt sich die Basispreisänderung auf den Ausgangspunkt für diese spezifischen Preise aus.

**F4: Ist es möglich, Preise nur für bestimmte Kategorien oder Hersteller zu aktualisieren?**
A4: Nein, diese kostenlose Version des Moduls führt eine Massenaktualisierung für *alle* Produkte in Ihrem Shop durch. Es bietet keine Filterung nach Kategorie, Hersteller oder anderen Kriterien. Für fortgeschrittenere, gefilterte Preisaktualisierungen benötigen Sie in der Regel ein ausgefeilteres, oft kostenpflichtiges Import-/Export- oder Massenaktualisierungsmodul.

**F5: Das Modul scheint zu hängen oder reagiert nicht, wenn ich auf „Änderungen anwenden“ klicke.**
A5: Bei Shops mit einer sehr großen Anzahl von Produkten (Tausende) kann der Aktualisierungsprozess einige Zeit in Anspruch nehmen.
\* Stellen Sie sicher, dass das PHP-Ausführungszeitlimit Ihres Servers ausreichend ist. Wenn es zu niedrig ist, sehen Sie möglicherweise einen „500 Internal Server Error“ oder einen Timeout. Dies ist ein Serverkonfigurationsproblem, kein Modulfehler.
\* Überprüfen Sie Ihre PrestaShop-Fehlerprotokolle (befindlich in `var/logs/` in PrestaShop 1.7/8/9) auf spezifische Fehler.
\* Wenn das Problem weiterhin besteht, wenden Sie sich an Ihren Hosting-Anbieter oder einen Webentwickler, um Serverprotokolle und PHP-Einstellungen zu überprüfen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Kostenloses Massen-Produkpreis-Update“ ist ein unkompliziertes PrestaShop-Modul, das hauptsächlich für die Back Office-Verwaltung entwickelt wurde. Es folgt einer grundlegenden PrestaShop-Modulstruktur und nutzt die `Module`-Klasse und ihre `getContent()`-Methode für die Konfiguration. Es interagiert direkt mit der PrestaShop-Datenbank, um Produktpreise ohne benutzerdefinierte Controller, Modelle oder komplexe JavaScript-Interaktionen zu aktualisieren. Die Modullogik ist in der Haupt-PHP-Datei selbst enthalten.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet **keine** benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Funktionalität wird direkt in der `getContent()`-Methode der Hauptmodulklasse behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert **keine** benutzerdefinierten Klassen oder erweitert `ObjectModel`. Es interagiert direkt mit den `Product`- und `Product::updatePrice()`-Methoden, die vom PrestaShop-Kern bereitgestellt werden.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält **keine** benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält **keine** benutzerdefinierten CSS-Dateien. Die Gestaltung der Konfigurationsseite wird durch das Standard-Back Office-Theme von PrestaShop übernommen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul verwendet zwei einfache Smarty-Templates:

- **`masspricefree/views/advert.tpl`**:
  - **Umfang:** Back-Office (Modulkonfigurationsseite).
  - **Zweck:** Wird wahrscheinlich verwendet, um eine Werbung oder eine Werbebotschaft von MyPresta.eu innerhalb der Konfigurationsoberfläche des Moduls anzuzeigen. Es wird typischerweise oben oder unten in der `getContent()`-Ausgabe gerendert.
- **`masspricefree/views/script.tpl`**:
  - **Umfang:** Back-Office (Modulkonfigurationsseite).
  - **Zweck:** Dieses Template könnte Inline-JavaScript oder einfache HTML-Elemente enthalten, die Teil des Konfigurationsformulars des Moduls sind, obwohl die Modulbeschreibung minimale JS vorschlägt. Angesichts der Einfachheit des Moduls ist es wahrscheinlicher, dass es ein Platzhalter ist oder sehr grundlegende UI-Elemente enthält.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt **keine** benutzerdefinierten Datenbanktabellen.
  - Es ändert direkt Daten in der Tabelle `ps_product` (insbesondere die Spalte `price`) und möglicherweise `ps_product_shop` (für Multi-Store-Kontexte) durch Aufruf von PrestaShop-Kernmethoden.
  - Konfigurationseinstellungen (Preisanpassungstyp, Prozentwert) werden in der Tabelle `ps_configuration` unter Verwendung von Standard-PrestaShop-Konfigurationsschlüsseln (z.B. `PS_MASS_PRICE_FREE_TYPE`, `PS_MASS_PRICE_FREE_VALUE`) gespeichert.
- **Registrierte Hooks-Tabelle**:
  Dieses Modul registriert **keine** spezifischen Hooks für die Front-Office-Anzeige oder Back-Office-Aktionen über die Standard-Hooks `displayBackOfficeHeader` (implizit für die Modulkonfiguration) und `actionModuleInstall`/`actionModuleUninstall` hinaus. Seine Hauptfunktion ist eine direkte Datenbankmanipulation, die durch die Übermittlung des Admin-Formulars ausgelöst wird.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayBackOfficeHeader` | Wird im `<head>`-Bereich des Back Office gerendert. | Wird von `getContent()` verwendet, um potenziell Assets zu laden oder Hinweise anzuzeigen, obwohl in diesem Modul nicht explizit für benutzerdefinierte Assets verwendet. |
| `actionModuleInstall` | Wird ausgelöst, wenn das Modul installiert wird. | Wird verwendet, um Standardkonfigurationswerte in `ps_configuration` festzulegen. |
| `actionModuleUninstall` | Wird ausgelöst, wenn das Modul deinstalliert wird. | Wird verwendet, um Konfigurationswerte aus `ps_configuration` zu entfernen. |

### 4.8 Hauptmoduldatei (`masspricefree/index.php`)

Die Kernlogik befindet sich in `masspricefree/index.php`.

- **Klassenname:** `MassPriceFree`
- **Elternklasse:** `Module`
- **Schlüsselmethoden:**
  - `__construct()`: Initialisiert Moduleigenschaften (Name, Tab, Version, Autor, need\_instance, Bootstrap).
  - `install()`: Registriert das Modul, setzt Standardkonfigurationswerte (z.B. `PS_MASS_PRICE_FREE_TYPE` auf 'increase', `PS_MASS_PRICE_FREE_VALUE` auf '0').
  - `uninstall()`: Löscht Konfigurationswerte.
  - `getContent()`: Dies ist die primäre Methode für die Funktionalität des Moduls.
    - Behandelt die Formularübermittlung (`Tools::isSubmit('submitMassPriceFree')`).
    - Ruft `price_type` und `price_value` aus dem übermittelten Formular ab.
    - Aktualisiert `ps_configuration` mit den neuen Einstellungen.
    - **Entscheidend ist, dass es alle aktiven Produkte (`Product::getProducts(Context::getContext()->language->id, 0, 0, 'id_product', 'ASC', false, true)`) durchläuft und deren Preise basierend auf dem konfigurierten Prozentsatz und Typ aktualisiert.** Es verwendet `Product::updatePrice()` dafür.
    - Rendert das Konfigurationsformular mit `displayForm()` und enthält die Templates `advert.tpl` und `script.tpl`.
  - `displayForm()`: Generiert den HTML-Code für das Konfigurationsformular des Moduls, einschließlich der Optionsfelder für Erhöhen/Senken und des Eingabefeldes für den Prozentsatz.

## 5. Offizieller Support & Updates

Für offizielle Updates, Fehlerbehebungen und dedizierten Support für das Modul „Kostenloses Massen-Produkpreis-Update“ verweisen wir Sie auf Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zur Funktionalität des Moduls gerne zur Verfügung.
