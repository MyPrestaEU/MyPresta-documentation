---
title: "Gruppenrabatt von Produkten mit spezifischem Preis ausschließen – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Gruppenrabatt von Produkten mit spezifischem Preis ausschließen“ von MyPresta.eu."
sidebar:
  label: "Gruppenrabatt von Produkten mit spezifischem Preis ausschließen – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Exclude group discount from products with specific price auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/exclude-group-discount-from-products-with-specific-price.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/exclude-group-discount-from-products-with-specific-price/)
>
> ---


# Gruppenrabatt von Produkten mit spezifischem Preis ausschließen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind keine ungewöhnlichen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Navigieren Sie nach der Installation zu **Module > Modul-Manager**, suchen Sie „Gruppenrabatt von Produkten mit spezifischem Preis ausschließen“ und klicken Sie auf **Konfigurieren**. Sie sehen den Hauptkonfigurationsbildschirm.

#### Einstellung: Gruppenrabatt für Produkte mit spezifischen Preisen deaktivieren

- **Was diese Einstellung bewirkt:** Dies ist die zentrale Steuerung für die Funktionalität des Moduls. Sie bestimmt, ob das Modul aktiv verhindern soll, dass Gruppenrabatte auf Produkte angewendet werden, die bereits spezifische Preise haben.
- **Auswirkung der Änderung dieser Einstellung:**
  - **Wenn auf „Aktiviert“ gesetzt:** Wenn ein Produkt einen spezifischen Preis hat (z.B. einen speziellen Verkaufspreis, den Sie festgelegt haben) und ein Kunde aus einer Gruppe, die normalerweise einen Rabatt erhält (z.B. „VIP-Kunden“ erhalten 10 % Rabatt), dieses Produkt ansieht oder kauft, wird der 10 % Gruppenrabatt *nicht* angewendet. Der Kunde zahlt den von Ihnen festgelegten spezifischen Preis. Dies ist das beabsichtigte Verhalten des Moduls.
  - **Wenn auf „Deaktiviert“ gesetzt:** Das Modul ist inaktiv. Das Standardverhalten von PrestaShop wird wieder aufgenommen. Dies bedeutet, wenn ein Produkt einen spezifischen Preis hat und ein Kunde aus einer rabattierten Gruppe es ansieht oder kauft, werden *sowohl* der spezifische Preis als auch der Gruppenrabatt angewendet, was möglicherweise zu einem viel niedrigeren Endpreis als beabsichtigt führt.
- **Empfohlener Wert:** **Aktiviert**. Dies ist der Zweck des Moduls, um unbeabsichtigtes Stapeln von Rabatten zu verhindern.
- **Händlerszenario / Beispiel:** Sie haben einen „Sommer-Sale“, bei dem ein bestimmtes T-Shirt 15 $ kostet (statt 25 $). Sie haben auch eine Kundengruppe „Großhandel“, die 20 % Rabatt auf alle Bestellungen erhält.
  - Wenn diese Einstellung **Aktiviert** ist: Ein Großhandelskunde kauft das T-Shirt. Er zahlt 15 $. Der 20 % Großhandelsrabatt wird für dieses spezifische Produkt ignoriert.
  - Wenn diese Einstellung **Deaktiviert** ist: Ein Großhandelskunde kauft das T-Shirt. PrestaShop wendet zuerst den spezifischen Preis (15 $) an, dann den 20 % Großhandelsrabatt auf 15 $, wodurch der Endpreis 12 $ beträgt. Dies könnte unter Ihrer gewünschten Gewinnmarge liegen.

#### Kurzübersichtstabelle zur Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | Gruppenrabatt für Produkte mit spezifischen Preisen deaktivieren | Aktiviert | Steuert, ob Gruppenrabatte daran gehindert werden, sich mit spezifischen Preisen zu stapeln. **Aktiviert** verhindert das Stapeln und bewahrt die Gewinnmargen. **Deaktiviert** erlaubt das Stapeln, was potenziell zu niedrigeren Preisen führt. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul aktiviert, aber Gruppenrabatte werden immer noch auf meine spezifischen Preise angewendet. Was ist falsch?**
A:

1.  **Cache leeren:** Leeren Sie immer Ihren PrestaShop-Cache, nachdem Sie Konfigurationsänderungen vorgenommen haben. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie dann oben rechts auf „Cache leeren“.
2.  **Modulreihenfolge:** In seltenen Fällen könnte ein anderes Modul die Preisberechnungen überschreiben. Wenn Sie andere Preis- oder Rabattmodule haben, versuchen Sie, diese vorübergehend einzeln zu deaktivieren, um festzustellen, ob ein Konflikt vorliegt.
3.  **Spezifische Preiseinrichtung:** Überprüfen Sie, ob Ihre „spezifischen Preise“ für die betreffenden Produkte korrekt konfiguriert sind. Gehen Sie zur Produktbearbeitungsseite, dann zum Tab „Preise“ und stellen Sie sicher, dass der spezifische Preis aktiv und korrekt angewendet ist.
4.  **Gruppenrabatteinrichtung:** Überprüfen Sie, ob der Kundengruppenrabatt unter **Shop-Parameter > Kundeneinstellungen > Gruppen** korrekt eingerichtet ist.

**F: Beeinflusst dieses Modul meine regulären Warenkorbregeln oder Gutscheincodes?**
A: Nein, dieses Modul zielt speziell auf „Gruppenrabatte“ (Rabatte, die automatisch basierend auf der zugewiesenen Gruppe eines Kunden angewendet werden) und deren Interaktion mit „spezifischen Preisen“ (manuelle Preisüberschreibungen für ein Produkt) ab. Es stört PrestaShops Warenkorbregeln, Gutscheincodes oder andere Werbemechanismen nicht, es sei denn, diese Mechanismen basieren selbst auf spezifischen Preisen oder Gruppenrabatten.

**F: Verlangsamt dieses Modul meinen Shop?**
A: Nein, das Modul ist sehr leichtgewichtig. Es funktioniert, indem es eine zentrale PrestaShop-Klasse (`Product.php`) überschreibt, um die Art und Weise zu ändern, wie Preise berechnet werden. Dies ist ein hochoptimierter Prozess und sollte keine spürbare Leistungsverschlechterung verursachen.

**F: Was ist, wenn ich möchte, dass Gruppenrabatte *manchmal* auf spezifische Preise angewendet werden?**
A: Dieses Modul bietet einen „Alles-oder-Nichts“-Ansatz: Entweder werden Gruppenrabatte von *allen* Produkten mit spezifischen Preisen ausgeschlossen, oder sie werden es nicht. Wenn Sie eine granularere Kontrolle benötigen (z.B. Ausschluss für Produkt A, aber Zulassung für Produkt B, beide mit spezifischen Preisen), wird dieses Modul allein dies nicht erreichen. Sie müssten spezifische Preise und Gruppenrabatte manuell verwalten oder ein fortschrittlicheres Preismodul in Betracht ziehen. Für dieses Modul wird empfohlen, es zu aktivieren, um unbeabsichtigtes Stapeln zu verhindern.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul `Gruppenrabatt von Produkten mit spezifischem Preis ausschließen` implementiert seine Kernfunktionalität durch eine Überschreibung der Klasse `Product`. Dies ist ein gängiges und effektives PrestaShop-Entwicklungsmuster zur Änderung von Kernverhalten, ohne Kerndateien direkt zu ändern. Durch die Überschreibung von `Product::getPriceStatic()` fängt das Modul die Preisberechnungslogik ab, um zu verhindern, dass gruppenspezifische Rabatte angewendet werden, wenn ein Produkt einen aktiven spezifischen Preis hat.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Die gesamte Front-Office-Logik wird über die Überschreibung der `Product`-Klasse abgewickelt.
- **Back-Office-Admin-Controller**: Keine. Die Konfiguration des Moduls wird direkt in der `getContent()`-Methode der Hauptmoduldatei behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Die primäre Funktionalität des Moduls liegt in seiner Klassenüberschreibung.

- **Dateipfad**: `exgdis/override/classes/Product.php`
- **Klassenname**: `Product` (überschreibt die Kernklasse `Product`)
- **Elternklasse**: `ProductCore`
- **Verantwortlichkeit**: Diese Überschreibung modifiziert die Methode `getPriceStatic()`, die zentral dafür ist, wie PrestaShop Produktpreise im gesamten Front Office (Produktseiten, Warenkorb, Kasse) und Back Office berechnet.
  - **Schlüssellogik**: Innerhalb der überschriebenen `getPriceStatic()`-Methode prüft das Modul, ob seine Konfigurationseinstellung `exgdis_groups` (die „Gruppenrabatt für Produkte mit spezifischen Preisen deaktivieren“ entspricht) aktiviert ist.
  - Wenn aktiviert und wenn das aktuell bepreiste Produkt einen aktiven spezifischen Preis hat, stellt das Modul sicher, dass der an die ursprüngliche `ProductCore::getPriceStatic()`-Methode übergebene Parameter `$use_group_reduction` auf `false` gesetzt wird. Dies weist PrestaShop effektiv an, für diese spezielle Preisberechnung *keine* gruppenspezifischen Rabatte anzuwenden.
  - Die Datei `index.php` in `override/classes/` ist eine standardmäßige leere Datei, um die Verzeichnisauflistung zu verhindern.

### 4.4 JavaScript-Assets (`views/js/`)

- Keine. Das Modul hat keine Front-End- oder Back-End-JavaScript-Komponenten.

### 4.5 CSS-Stylesheets (`views/css/`)

- Keine. Das Modul hat keine benutzerdefinierte CSS-Formatierung.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- Keine. Die Konfiguration des Moduls wird direkt über `getContent()` in der Hauptmoduldatei gerendert, und seine Funktionalität ist rein logikbasiert, nicht anzeigebasiert.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es speichert seine Konfiguration in der Tabelle `ps_configuration`.

  - `ps_configuration`-Eintrag: `exgdis_groups` (speichert den aktivierten/deaktivierten Status der Haupteinstellung).
- **Registrierte Hooks-Tabelle**: Das Modul registriert keine Hooks explizit in der Tabelle `ps_hook_module`. Seine Funktionalität wird über einen Klassen-Override implementiert, der durch PrestaShops Override-Mechanismus geladen wird.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `override/classes/Product.php` | Während `Product::getPriceStatic()`-Aufrufen | Fängt die Preisberechnung ab, um Gruppenrabatte auf Produkte mit spezifischen Preisen zu verhindern. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Gruppenrabatt von Produkten mit spezifischem Preis ausschließen“ besuchen Sie bitte Ihr MyPresta.eu-Kundenkonto. Sie können die neuesten Versionen herunterladen und direkt über [MyPresta.eu](https://mypresta.eu) auf Support-Ressourcen zugreifen.
