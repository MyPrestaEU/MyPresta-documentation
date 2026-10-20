---
title: "Produktspezifische Preise deaktivieren, wenn der Warenkorb eine Warenkorbregel enthält – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Produktspezifische Preise deaktivieren, wenn der Warenkorb eine Warenkorbregel enthält“ von MyPresta.eu."
sidebar:
  label: "Produktspezifische Preise deaktivieren, wenn der Warenkorb eine Warenkorbregel enthält – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Disable product specific prices when cart has cart rule auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/disable-product-specific-prices-when-cart-has-cart-rule.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/disable-product-specific-prices-when-cart-has-cart-rule/)
>
> ---


# Produktspezifische Preise deaktivieren, wenn der Warenkorb eine Warenkorbregel enthält

## 1. Anforderungen & Kompatibilität

Dieses Modul ist so konzipiert, dass es nahtlos mit modernen PrestaShop-Installationen funktioniert.

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind für PrestaShop selbst erforderlich und sind typischerweise in jeder modernen Webhosting-Umgebung verfügbar. Keine speziellen Hosting-Anforderungen über eine Standard-PrestaShop-Einrichtung hinaus.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Dieses Modul hat einen einzigen, einfachen Konfigurationsbildschirm.

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Um auf die Konfiguration zuzugreifen, navigieren Sie zu **Module > Modul-Manager**, suchen Sie nach „Produktspezifische Preise deaktivieren, wenn der Warenkorb eine Warenkorbregel enthält“ und klicken Sie auf die Schaltfläche „Konfigurieren“.

![Platzhalter für Modulkonfigurations-Screenshot]
*(Stellen Sie sich hier einen Screenshot vor, der ein einfaches Formular mit einem einzigen Umschalter zeigt, der mit „Nutzung spezifischer Preise im Warenkorb mit Warenkorbregel deaktivieren“ und den Optionen „Aktiviert“ / „Deaktiviert“ beschriftet ist.)*

**Einstellung: Nutzung spezifischer Preise im Warenkorb mit Warenkorbregel deaktivieren**

- **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für die Kernfunktionalität des Moduls. Er bestimmt, ob das Modul aktiv eingreift, um spezifische Preise zu deaktivieren, wenn eine Warenkorbregel (Gutscheincode) im Warenkorb des Kunden vorhanden ist.
- **Auswirkung der Änderung dieser Einstellung:**
  - **Wenn aktiviert (JA):** Wenn ein Kunde eine Warenkorbregel (Gutscheincode) auf seinen Warenkorb anwendet, verhindert das Modul, dass produktspezifische Preise auf die Produkte in diesem Warenkorb angewendet werden. Die Produktpreise kehren zu ihrem Grundpreis zurück, bevor der Warenkorbregel-Rabatt angewendet wird, wodurch sichergestellt wird, dass nur der Rabatt der Warenkorbregel den Endpreis beeinflusst. Dies verhindert Doppelrabatte.
  - **Wenn deaktiviert (NEIN):** Das Modul ist inaktiv. Spezifische Preise und Warenkorbregeln funktionieren unabhängig voneinander, was bedeutet, dass sie sich potenziell auf dasselbe Produkt stapeln können, was zu mehreren gleichzeitig angewendeten Rabatten führt. Dies ist das Standardverhalten von PrestaShop.
- **Empfohlener Wert:** **Aktiviert (JA)**. Dies ist der Hauptzweck des Moduls und ermöglicht es Ihnen, Ihre Gewinnmargen zu schützen und Ihre Rabattstrategie zu kontrollieren.
- **Händlerszenario / Beispiel:**
  - **Wählen Sie „Aktiviert“**, wenn Sie sicherstellen möchten, dass, wenn ein Kunde einen Gutscheincode verwendet (z. B. „SPARE10“ für 10 % Rabatt), alle vorhandenen spezifischen Preise für Produkte in seinem Warenkorb ignoriert werden. Dies bedeutet, dass der 10 %-Rabatt auf den regulären Preis des Produkts angewendet wird, nicht auf einen bereits reduzierten spezifischen Preis. Dies verhindert, dass ein Produkt zweimal rabattiert wird.
  - **Wählen Sie „Deaktiviert“**, wenn Sie das Standardverhalten von PrestaShop bevorzugen, bei dem sich spezifische Preise und Warenkorbregeln stapeln können, was potenziell zu tieferen Rabatten als beabsichtigt führen kann. Dies könnte in sehr spezifischen, aggressiven Werbekampagnen gewünscht sein, aber im Allgemeinen wird „Aktiviert“ zum Schutz des Gewinns empfohlen.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Nutzung spezifischer Preise im Warenkorb mit Warenkorbregel deaktivieren | Aktiviert | Wenn aktiviert, werden spezifische Preise ignoriert, wenn eine Warenkorbregel im Warenkorb aktiv ist, wodurch Doppelrabatte verhindert werden. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe das Modul aktiviert, aber spezifische Preise werden auch mit einem Gutscheincode noch angezeigt. Was ist falsch?**

- **A:** Stellen Sie zunächst sicher, dass Sie die Konfiguration nach der Aktivierung des Moduls gespeichert haben.
- **A:** Leeren Sie Ihren PrestaShop-Cache. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie oben rechts auf „Cache leeren“.
- **A:** Testen Sie mit einem neuen Warenkorb. Manchmal können Browser-Cache oder Sitzungsdaten stören. Versuchen Sie es in einem Inkognito-Fenster.
- **A:** Überprüfen Sie, ob die Warenkorbregel, mit der Sie testen, tatsächlich aktiv und korrekt auf die Produkte im Warenkorb angewendet wird.

**F2: Meine Kunden beschweren sich, dass ihre spezifischen Preise verschwunden sind, als sie einen Gutschein verwendet haben. Ist das zu erwarten?**

- **A:** Ja, dies ist das beabsichtigte Verhalten des Moduls. Wenn das Modul aktiviert ist und ein Kunde eine Warenkorbregel (Gutschein) anwendet, werden die spezifischen Preise für Produkte im Warenkorb vorübergehend deaktiviert, um Doppelrabatte zu verhindern. Der Preis des Produkts wird dann basierend auf seinem ursprünglichen Preis berechnet, wobei der Warenkorbregel-Rabatt angewendet wird. Sie sollten Ihre Geschäftsbedingungen oder Werbebotschaften aktualisieren, um zu klären, wie Rabatte interagieren.

**F3: Beeinflusst dieses Modul andere Arten von Rabatten, wie Kategorie-Rabatte oder Kundengruppen-Rabatte?**

- **A:** Dieses Modul zielt speziell auf „spezifische Preise“ (Rabatte, die direkt auf einzelne Produkte oder Kombinationen festgelegt werden) und deren Interaktion mit „Warenkorbregeln“ (Gutscheincodes) ab. Es greift nicht direkt in andere Rabattmechanismen wie Kategorie-Rabatte, Kundengruppen-Rabatte oder Mengenrabatte ein, es sei denn, diese werden als spezifische Preise implementiert.

**F4: Wird dieses Modul meinen Shop verlangsamen?**

- **A:** Das Modul nimmt geringfügige Überschreibungen an den PrestaShop-Kernklassen vor, um die Preisberechnungslogik anzupassen. Diese Änderungen sind hochoptimiert und sollten eine vernachlässigbare Auswirkung auf die Leistung Ihres Shops haben. Das Modul aktiviert seine Logik nur, wenn eine Warenkorbregel vorhanden ist, sodass es nicht ständig läuft.

**F5: Ich möchte vorübergehend zulassen, dass sich spezifische Preise und Warenkorbregeln für eine spezielle Aktion stapeln. Wie mache ich das?**

- **A:** Gehen Sie einfach zur Konfigurationsseite des Moduls (**Module > Modul-Manager > Konfigurieren** für „Produktspezifische Preise deaktivieren, wenn der Warenkorb eine Warenkorbregel enthält“) und setzen Sie die Option „Nutzung spezifischer Preise im Warenkorb mit Warenkorbregel deaktivieren“ auf **„Deaktiviert“**. Denken Sie daran, es nach dem Ende Ihrer speziellen Aktion wieder zu aktivieren, um das standardmäßige Schutzverhalten wiederherzustellen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster, die mit dem Modul „Produktspezifische Preise deaktivieren, wenn der Warenkorb eine Warenkorbregel enthält“ arbeiten.

### 4.1 Architekturübersicht

Dieses Modul funktioniert hauptsächlich durch das Überschreiben von PrestaShop-Kernklassen, die sich auf die Preisberechnung und die Verwaltung spezifischer Preise beziehen. Es nutzt den PrestaShop-Überschreibungsmechanismus, um seine Logik in die Klassen `Cart`, `Product` und `SpecificPrice` einzuschleusen. Die Kernidee besteht darin, das Vorhandensein einer Warenkorbregel im aktuellen Warenkorb zu erkennen und, falls vorhanden, das Verhalten der spezifischen Preisabfrage zu ändern, um diese während der Preisberechnungen effektiv zu ignorieren.

Die Hauptkonfiguration des Moduls wird über die Methode `getContent()` in der Hauptmoduldatei gehandhabt, wobei ein einfacher boolescher Flag in `ps_configuration` gespeichert wird.

### 4.2 Controller (`controllers/`)

Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Controller ein. Seine Logik ist vollständig in Klassenüberschreibungen eingebettet.

- **Front-Office-Controller**: Keine
- **Back-Office-Admin-Controller**: Keine

### 4.3 Kernklassen & Modelle (`classes/`)

Die Kernfunktionalität des Moduls liegt in seinen Klassenüberschreibungen. Diese Dateien befinden sich in `cartspecdis/override/classes/`. PrestaShop lädt diese Überschreibungen automatisch und ersetzt die ursprünglichen Kernklassen durch die modifizierten Versionen des Moduls.

- **`cartspecdis/override/classes/Cart.php`**

  - **Klassenname & Elternklasse**: `Cart` (überschreibt `\Cart`)
  - **Verantwortlichkeit**: Diese Überschreibung ist entscheidend. Sie führt wahrscheinlich eine Methode ein oder modifiziert eine bestehende (z. B. `getProducts()`, `getPackageList()` oder einen Preisberechnungshelfer), um das Vorhandensein von Warenkorbregeln zu überprüfen. Wenn Warenkorbregeln gefunden werden, setzt sie ein Flag oder modifiziert Parameter, die beeinflussen, wie spezifische Preise später abgerufen oder angewendet werden. Die Methode `hasCartRules()` ist ein wahrscheinlicher Kandidat für die Überprüfung von Warenkorbregeln.
  - **Schlüssellogik**: Die Überschreibung wird wahrscheinlich eine Überprüfung innerhalb der Preisberechnungsmethoden hinzufügen, um zu sehen, ob `Cart::getCartRules()` aktive Regeln zurückgibt. Wenn ja, wird sie dann die Aufrufe von `Product::getPriceStatic()` oder `SpecificPrice::getSpecificPrice()` beeinflussen, um spezifische Preise zu ignorieren.
- **`cartspecdis/override/classes/Product.php`**

  - **Klassenname & Elternklasse**: `Product` (überschreibt `\Product`)
  - **Verantwortlichkeit**: Diese Überschreibung soll die Methode `getPriceStatic()` modifizieren, die zentral dafür ist, wie Produktpreise in PrestaShop abgerufen werden.
  - **Schlüssellogik**: Innerhalb von `getPriceStatic()` wird das Modul wahrscheinlich eine Bedingung hinzufügen. Wenn das aktuelle `Cart`-Objekt (als Parameter übergeben oder global zugänglich) aktive Warenkorbregeln enthält und die Konfiguration des Moduls aktiviert ist, werden die an `SpecificPrice::getSpecificPrice()` übergebenen Parameter (z. B. `id_specific_price` oder `use_specific_price` Flags) geändert, um sicherzustellen, dass kein spezifischer Preis zurückgegeben wird oder die spezifische Preisberechnung umgangen wird.
- **`cartspecdis/override/classes/SpecificPrice.php`**

  - **Klassenname & Elternklasse**: `SpecificPrice` (überschreibt `\SpecificPrice`)
  - **Verantwortlichkeit**: Diese Überschreibung soll wahrscheinlich die Methode `getSpecificPrice()` modifizieren, die für das Abrufen spezifischer Preisdetails für ein bestimmtes Produkt verantwortlich ist.
  - **Schlüssellogik**: Diese Überschreibung enthält die direkte Logik, um zu verhindern, dass spezifische Preise zurückgegeben werden. Sie prüft, ob der aktuelle `Cart` Warenkorbregeln hat und ob das Modul aktiviert ist. Wenn beide Bedingungen wahr sind, wird `getSpecificPrice()` dazu gebracht, `false` oder ein leeres Array zurückzugeben, was effektiv anzeigt, dass kein spezifischer Preis gilt, selbst wenn einer in der Datenbank existiert. Dies ist der letzte Gatekeeper für spezifische Preise.
- **`cartspecdis/override/classes/index.php`**

  - **Klassenname & Elternklasse**: Keine
  - **Verantwortlichkeit**: Dies ist eine standardmäßige leere `index.php`-Datei, die typischerweise in Verzeichnissen platziert wird, um die Verzeichnisauflistung zu verhindern, wenn direkt über einen Webbrowser darauf zugegriffen wird. Sie hat keine funktionale Auswirkung auf die Logik des Moduls.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien. Die gesamte Logik wird serverseitig verarbeitet.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält keine benutzerdefinierten CSS-Dateien. Es hat keine visuellen Front-Office-Komponenten und seine Back-Office-Konfiguration verwendet Standard-PrestaShop-Formularelemente.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Dieses Modul verwendet keine benutzerdefinierten Smarty-Templates. Sein Konfigurationsformular wird dynamisch durch die Methode `getContent()` in der Hauptmoduldatei unter Verwendung der PrestaShop-Hilfsformulare generiert.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfigurationseinstellung in der Tabelle `ps_configuration`:
    - `PS_CONFIGURATION`-Schlüssel: `cartspecdis` (speichert den booleschen Wert für die Aktivierung/Deaktivierung der Kernfunktionalität des Moduls).
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin-Controller seine Medien-Assets (CSS/JS) einrichtet. | Dieser Hook wird typischerweise von Modulen verwendet, um eigene CSS- oder JavaScript-Dateien zum Back Office hinzuzufügen. Für dieses Modul wird er wahrscheinlich verwendet, um sicherzustellen, dass alle notwendigen Admin-seitigen Stile oder Skripte (obwohl keine explizit im Inventar aufgeführt sind) geladen werden, oder es könnte ein Überbleibsel einer Template-Modulstruktur sein. Da keine JS/CSS-Dateien aufgeführt sind, ist sein Hauptzweck hier wahrscheinlich minimal oder für zukünftige Erweiterungen. |

### 4.8 Hauptmoduldatei (`cartspecdis/cartspecdis.php`)

- **Klassenname**: `Cartspecdis` (erweitert `Module`)
- **`__construct()`**: Initialisiert Modul-Metadaten (Name, Tab, Version, Autor, `need_instance`, `ps_versions_compliancy`).
- **`install()`**:
  - Ruft `parent::install()` auf.
  - Registriert den Hook `actionAdminControllerSetMedia`.
  - Setzt den Standardkonfigurationswert für `cartspecdis` auf `1` (aktiviert) in `ps_configuration`.
  - Registriert die Klassenüberschreibungen (`Cart`, `Product`, `SpecificPrice`).
- **`uninstall()`**:
  - Ruft `parent::uninstall()` auf.
  - Deregistriert den Hook `actionAdminControllerSetMedia`.
  - Löscht den Konfigurationswert `cartspecdis` aus `ps_configuration`.
  - Deregistriert die Klassenüberschreibungen.
- **`getContent()`**:
  - Behandelt die Formularübermittlung für die Modulkonfiguration.
  - Aktualisiert den Konfigurationswert `cartspecdis` in `ps_configuration` basierend auf der Benutzereingabe.
  - Zeigt eine Bestätigungsnachricht an.
  - Rendert das Konfigurationsformular unter Verwendung der PrestaShop-Klasse `HelperForm`, einschließlich des einzelnen Umschalters für „Nutzung spezifischer Preise im Warenkorb mit Warenkorbregel deaktivieren“.
- **`hookActionAdminControllerSetMedia()`**:
  - Diese Methode wird aufgerufen, wenn der Hook `actionAdminControllerSetMedia` ausgeführt wird.
  - Sie wird typischerweise verwendet, um CSS- oder JavaScript-Dateien zum Back Office hinzuzufügen. Im aktuellen Zustand dieses Moduls (basierend auf dem Inventar) enthält sie wahrscheinlich minimalen oder keinen aktiven Code zum Hinzufügen von Assets, oder sie ist ein Platzhalter.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Produktspezifische Preise deaktivieren, wenn der Warenkorb eine Warenkorbregel enthält“ besuchen Sie bitte Ihr Kundenkonto bei MyPresta.eu.

- **Modul-Updates**: Melden Sie sich in Ihrem MyPresta.eu-Konto an und navigieren Sie zu Ihrer Bestellhistorie und dem Download-Bereich, um die aktuellste Version des Moduls zu erhalten.
- **Technischer Support**: Wenn Sie Probleme haben oder Fragen, die in dieser Dokumentation nicht behandelt werden, eröffnen Sie bitte ein Support-Ticket über Ihr MyPresta.eu-Kundenkonto. Unser Team hilft Ihnen gerne weiter.
