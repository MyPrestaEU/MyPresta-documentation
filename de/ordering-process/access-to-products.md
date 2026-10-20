---
title: "Produktzugriff - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Produktzugriff' von MyPresta.eu."
sidebar:
  label: "Produktzugriff - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Access to Products auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/access-to-products.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/access-to-products/)
>
> ---


# Produktzugriff

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) werden typischerweise von PrestaShop selbst benötigt und sind für dieses Modul ausreichend.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Produktzugriff)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie die Regeln für den Produktzugriff definieren.

#### Allgemeine Einstellungen

| Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- |
| **Modul aktivieren** | JA | **Zweck:** Schaltet die Funktionalität des Moduls ein oder aus.   **Auswirkung:**   *Wenn aktiviert:* Alle Ihre konfigurierten Einschränkungen sind im Front Office aktiv.   *Wenn deaktiviert:* Das Modul hat keine Auswirkung, und alle Produkte sind für alle Kunden sichtbar und kaufbar, unabhängig von der Gruppe.   **Empfohlen:** JA, sobald Sie Ihre Regeln konfiguriert haben. |
| **Möglichkeit zum Anzeigen der Produktseite blockieren** | NEIN | **Zweck:** Steuert, ob Kunden, die nicht zu den erlaubten Gruppen gehören, die dedizierte Produktseite überhaupt sehen können.   **Auswirkung:**   *Wenn aktiviert:* Wenn ein Kunde, der nicht zu einer erlaubten Gruppe gehört, versucht, direkt auf die Produktseite zuzugreifen (z. B. über einen Link oder eine Suchmaschine), wird er umgeleitet oder erhält eine Meldung „Zugriff verweigert“.   *Wenn deaktiviert:* Unautorisierte Kunden können die Produktseite weiterhin anzeigen, werden aber daran gehindert, sie in den Warenkorb zu legen.   **Empfohlen:** JA für wirklich exklusive Produkte, NEIN, wenn Sie möchten, dass sie das Produkt sehen, es aber nicht kaufen können (z. B. „kontaktieren Sie uns für Großhandel“). |
| **Produkt in Produktlisten ausblenden** | NEIN | **Zweck:** Bestimmt, ob eingeschränkte Produkte für unautorisierte Kunden auf Kategorieseiten, in Suchergebnissen und anderen Produktlisten ausgeblendet werden.   **Auswirkung:**   *Wenn aktiviert:* Produkte werden für Kunden, die nicht zu den erlaubten Gruppen gehören, einfach in keiner Produktliste angezeigt.   *Wenn deaktiviert:* Produkte werden in Listen angezeigt, aber wenn der Kunde darauf klickt, wird ihm entweder das Anzeigen der Seite blockiert (wenn „Möglichkeit zum Anzeigen der Produktseite blockieren“ auf JA steht) oder das Hinzufügen zum Warenkorb blockiert.   **Empfohlen:** JA für ein saubereres, gezielteres Browsing-Erlebnis für jede Kundengruppe. |
| **Nachricht für nicht zugelassene Kunden** | „Sie dürfen dieses Produkt nicht bestellen.“ | **Zweck:** Der Text, der Kunden angezeigt wird, die versuchen, ein eingeschränktes Produkt in ihren Warenkorb zu legen oder eine eingeschränkte Produktseite anzuzeigen (wenn „Möglichkeit zum Anzeigen der Produktseite blockieren“ auf NEIN steht).   **Auswirkung:** Diese Nachricht erscheint im Warenkorb neben dem eingeschränkten Produkt oder auf der Produktseite.   **Empfohlen:** Eine klare, höfliche Nachricht. Sie können sie anpassen, um zu erklären, warum (z. B. „Dieses Produkt ist nur für Großhandelskunden. Bitte melden Sie sich mit Ihrem Großhandelskonto an.“). |

#### Tabelle der Produktbeschränkungen

Dieser Abschnitt zeigt eine Liste aller Produkte an, für die Sie Zugriffsrechte definiert haben. Sie können hier neue Beschränkungen hinzufügen oder bestehende bearbeiten.

- **Produktname:** Der Name des Produkts, das eingeschränkt wird.
- **Erlaubte Kundengruppen:** Eine Liste der Kundengruppen, die dieses Produkt *sehen und/oder kaufen dürfen*.
- **Aktionen:** Beschränkung bearbeiten (Bleistiftsymbol) oder löschen (Mülleimersymbol).

#### Hinzufügen/Bearbeiten von Produktbeschränkungen

Wenn Sie auf „Neue Beschränkung hinzufügen“ oder das „Bearbeiten“-Symbol für eine bestehende Beschränkung klicken, sehen Sie ein Formular:

- **Produkt auswählen:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, das spezifische Produkt zu suchen und auszuwählen, das Sie einschränken möchten.
  - **Auswirkung der Änderung dieser Einstellung:** Dies verknüpft die Beschränkungsregel mit einem bestimmten Produkt in Ihrem Katalog.
  - **Empfohlener Wert:** Wählen Sie das genaue Produkt aus.
  - **Händlerszenario:** Sie möchten „Großhandels-Kaffeemischung“ auf Ihre Großhandelskunden beschränken. Sie würden nach „Großhandels-Kaffeemischung“ suchen und diese auswählen.
- **Kundengruppen auswählen:**

  - **Was diese Einstellung bewirkt:** Eine Liste aller in Ihrem PrestaShop-Store definierten Kundengruppen (z. B. Besucher, Gast, Kunde, Großhändler, VIP). Sie wählen aus, welche dieser Gruppen auf das Produkt *zugreifen dürfen*.
  - **Auswirkung der Änderung dieser Einstellung:** Nur Kunden, die zu den ausgewählten Gruppen gehören, können gemäß Ihren allgemeinen Einstellungen mit dem Produkt interagieren (ansehen, in den Warenkorb legen). Alle anderen Gruppen werden eingeschränkt.
  - **Empfohlener Wert:** Wählen Sie nur die Gruppen aus, die Zugriff haben sollen.
  - **Händlerszenario:** Für „Großhandels-Kaffeemischung“ würden Sie „Großhändler“ auswählen. Wenn Sie auch VIPs Zugriff gewähren möchten, würden Sie „Großhändler“ und „VIP“ auswählen.

Nachdem Sie Ihre Auswahl getroffen haben, klicken Sie auf **„Speichern“**, um die Beschränkung anzuwenden.

### 2.2 Kurzübersichtstabelle zur Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| Modulkonfiguration | Modul aktivieren | JA | Aktiviert/deaktiviert die gesamte Modulfunktionalität. |
| Modulkonfiguration | Möglichkeit zum Anzeigen der Produktseite blockieren | NEIN (für Exklusivität JA in Betracht ziehen) | Verhindert, dass unautorisierte Kunden die Produktseite sehen. |
| Modulkonfiguration | Produkt in Produktlisten ausblenden | NEIN (für gezielte Anzeige JA in Betracht ziehen) | Blendet eingeschränkte Produkte für unautorisierte Kunden aus Kategorie-/Suchergebnissen aus. |
| Modulkonfiguration | Nachricht für nicht zugelassene Kunden | „Sie dürfen dieses Produkt nicht bestellen.“ | Anpassbare Nachricht, die unautorisierten Kunden angezeigt wird. |
| Tabelle der Produktbeschränkungen | Produkt auswählen | N/A | Wählen Sie das Produkt aus, für das Beschränkungen gelten sollen. |
| Tabelle der Produktbeschränkungen | Kundengruppen auswählen | N/A | Definieren Sie, welche Kundengruppen auf das ausgewählte Produkt *zugreifen dürfen*. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe Beschränkungen konfiguriert, aber sie scheinen nicht zu funktionieren. Was soll ich tun?**
A:

1. **Modulstatus prüfen:** Stellen Sie sicher, dass „Modul aktivieren“ in der Modulkonfiguration auf JA gesetzt ist.
2. **Cache leeren:** Gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Einstellungen > Leistung**. Klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Dies ist entscheidend, damit Änderungen wirksam werden.
3. **Kundengruppenzuweisung:** Überprüfen Sie nochmals, ob der Kunde, mit dem Sie testen, korrekt der beabsichtigten Kundengruppe zugewiesen ist (Kunden > Kunden, dann den Kunden bearbeiten).
4. **Produktauswahl:** Vergewissern Sie sich, dass Sie das richtige Produkt in den Beschränkungseinstellungen des Moduls ausgewählt haben.
5. **Browser-Cache:** Versuchen Sie, den Cache Ihres Browsers zu leeren oder in einem Inkognito-/privaten Browsing-Fenster zu testen, um clientseitige Caching-Probleme auszuschließen.

**F: Wie übersetze ich die „Nachricht für nicht zugelassene Kunden“ in andere Sprachen?**
A:

1. Gehen Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**.
2. Wählen Sie „Übersetzungen installierter Module“ als Übersetzungstyp.
3. Wählen Sie Ihr Theme.
4. Wählen Sie die Sprache aus, in die Sie übersetzen möchten.
5. Suchen Sie das Modul „Produktzugriff“. Dort sollten Sie das Feld für die Nachricht finden, bereit zur Übersetzung.

**F: Wird dieses Modul meinen Store verlangsamen?**
A: Das Modul ist leichtgewichtig und effizient konzipiert. Es integriert sich direkt in die Kernprodukt- und Warenkorblogik von PrestaShop. Jegliche Leistungsauswirkungen sollten vernachlässigbar sein, insbesondere nach dem Caching. Wenn Sie erhebliche Verlangsamungen bemerken, stellen Sie sicher, dass Ihr Server die Mindestanforderungen von PrestaShop erfüllt und dass Sie eine aktuelle PHP-Version verwenden.

**F: Was passiert, wenn ein Kunde in mehreren Gruppen ist und eine Gruppe erlaubt ist, während eine andere nicht erlaubt ist?**
A: Wenn ein Kunde zu *irgendeiner* Gruppe gehört, die explizit Zugriff auf ein Produkt hat, erhält er Zugriff. Das Modul gewährt Zugriff, wenn *eine* der Kundengruppen mit einer erlaubten Gruppe für dieses Produkt übereinstimmt. Es ist eine „ODER“-Logik: Wenn Gruppe A erlaubt ist ODER Gruppe B erlaubt ist und der Kunde in Gruppe A ist, erhält er Zugriff.

**F: Kann ich den Zugriff auf ganze Kategorien anstelle einzelner Produkte beschränken?**
A: Dieses Modul konzentriert sich auf individuelle Produktbeschränkungen. Um ganze Kategorien zu beschränken, müssten Sie die Beschränkung auf jedes Produkt innerhalb dieser Kategorie anwenden. Für Beschränkungen auf Kategorieebene benötigen Sie möglicherweise ein anderes Modul oder eine kundenspezifische Entwicklung.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul „Produktzugriff“ (`pga`) arbeitet hauptsächlich durch das Überschreiben von PrestaShop-Kernklassen, um seine Zugriffssteuerungslogik zu injizieren. Es nutzt PrestaShops `ObjectModel` zur Konfigurationsspeicherung und modifiziert die Produktsichtbarkeit und das Warenkorbverhalten an wichtigen Stellen im Front-Office-Anfragezyklus. Die Hauptlogik des Moduls befindet sich in `index.php` (der Hauptmoduldatei) und seinen Overrides.

### 4.2 Controller (`controllers/`)

Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Controller ein. Die gesamte Konfiguration wird über die Methode `getContent()` in der Hauptmoduldatei (`pga/index.php`) gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul nutzt den PrestaShop-Override-Mechanismus, um das Kernverhalten zu modifizieren.

- `pga/override/classes/Pack.php`

  - **Klassenname:** `Pack` (überschreibt PrestaShops `Pack`-Klasse)
  - **Verantwortlichkeit:** Dieser Override modifiziert wahrscheinlich die Handhabung von Produktpaketen, insbesondere in Bezug auf Produktsichtbarkeit und -zugriff. Er stellt sicher, dass, wenn ein Produkt innerhalb eines Pakets eingeschränkt ist, das Paket selbst diese Einschränkungen respektiert. Dies ist entscheidend für die Aufrechterhaltung einer konsistenten Zugriffssteuerung für gebündelte Produkte.
  - **Schlüsselmethoden (wahrscheinlich modifiziert/hinzugefügt):** Methoden im Zusammenhang mit `getPackProducts()` oder `isPack()` könnten erweitert werden, um Produkte basierend auf `pga`-Einschränkungen zu filtern.
- `pga/override/classes/shop/Shop.php`

  - **Klassenname:** `Shop` (überschreibt PrestaShops `Shop`-Klasse)
  - **Verantwortlichkeit:** Dieser Override ist für Produktzugriffsmodule weniger üblich und deutet auf eine tiefere Integration hin. Er könnte verwendet werden, um sicherzustellen, dass Produktbeschränkungen in einer Multi-Shop-Umgebung korrekt auf verschiedene Shops angewendet werden, oder um die Art und Weise zu modifizieren, wie Produktdaten auf einer sehr grundlegenden Ebene abgerufen werden, was potenziell Produktabfragen beeinflusst.
  - **Schlüsselmethoden (wahrscheinlich modifiziert/hinzugefügt):** Methoden wie `getProducts()` oder `getProductById()` könnten erweitert werden, um Ergebnisse basierend auf `pga`-Regeln zu filtern, bevor sie überhaupt vom `Shop`-Kontext zurückgegeben werden.

### 4.4 JavaScript-Assets (`views/js/`)

- `pga/views/js/pga.js`
  - **Geltungsbereich:** Back-Office.
  - **Zweck:** Dieses Skript ist wahrscheinlich dafür verantwortlich, die Benutzererfahrung auf der Konfigurationsseite des Moduls zu verbessern. Es könnte AJAX-Aufrufe für die Produktsuche, dynamische Aktualisierungen der Produktbeschränkungstabelle oder clientseitige Validierung für das Konfigurationsformular verarbeiten.
  - **Schlüsselfunktionalität:**
    - Event-Listener für Produktsuch-Eingabefelder (z. B. `keyup`-Events, um AJAX-Vorschläge auszulösen).
    - AJAX-Anfragen an einen Modul-Endpunkt (über `AdminController` oder `index.php?fc=module&module=pga&controller=ajax`), um Produktdaten abzurufen oder Beschränkungen zu speichern.
    - DOM-Manipulation zur Anzeige von Suchergebnissen, Hinzufügen ausgewählter Produkte zur Beschränkungsliste oder Aktualisieren von Nachrichten.

### 4.5 CSS-Stylesheets (`views/css/`)

- `pga/views/css/pga.css`
  - **Geltungsbereich:** Back-Office.
  - **Zweck:** Bietet Styling für die Konfigurationsoberfläche des Moduls im PrestaShop Back Office.
  - **Haupt-UI-Komponenten:** Stile für das Produktsuchfeld, die Produktbeschränkungstabelle, Buttons und alle benutzerdefinierten Elemente, die durch die `getContent()`-Methode des Moduls eingeführt wurden.
  - **Schlüssel-CSS-Klassenselektoren:** Entwickler können die HTML-Ausgabe des Moduls im Back Office überprüfen, um spezifische Klassen (z. B. `.pga-product-search`, `.pga-restriction-table`) für potenzielle Overrides zu identifizieren, falls ein benutzerdefiniertes Admin-Theme-Styling erforderlich ist.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Alle Templates sind für die Back-Office-Konfiguration.

- `pga/views/templates/admin/AdminTab.tpl`

  - **Zweck:** Dieses Template ist wahrscheinlich ein generischer Wrapper oder ein Teiltemplate, das innerhalb der Hauptkonfigurationsansicht verwendet wird. Es könnte die Struktur für eine Registerkartenoberfläche oder einen gemeinsamen Header/Footer für Admin-Seiten definieren.
- `pga/views/templates/admin/csv.tpl`

  - **Zweck:** Deutet auf Funktionalität im Zusammenhang mit dem CSV-Import/Export von Produktbeschränkungen hin. Dieses Template würde die Schnittstelle zum Hochladen einer CSV-Datei oder zum Generieren einer solchen rendern.
- `pga/views/templates/admin/csv_file.tpl`

  - **Zweck:** Ein Sub-Template oder Partial, das von `csv.tpl` verwendet wird, möglicherweise zur Anzeige eines Dateiupload-Formulars oder einer Liste von CSV-Dateien.
- `pga/views/templates/admin/customerGroups.tpl`

  - **Zweck:** Dieses Template ist entscheidend für die Funktionalität „Kundengruppen auswählen“. Es rendert die Liste der Kundengruppen mit Kontrollkästchen oder einem Mehrfachauswahl-Dropdown, sodass der Administrator auswählen kann, welche Gruppen für ein bestimmtes Produkt zugelassen sind.
- `pga/views/templates/admin/main.tpl`

  - **Zweck:** Dies ist das primäre Template für die Konfigurationsseite des Moduls (gerendert von `getContent()`). Es orchestriert alle anderen Partials und zeigt die allgemeinen Einstellungen, die Produktbeschränkungstabelle und die Formulare zum Hinzufügen/Bearbeiten von Beschränkungen an.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul speichert seine Konfiguration in der PrestaShop-Tabelle `ps_configuration` für allgemeine Einstellungen (z. B. `PGA_ENABLED`, `PGA_BLOCK_VIEW`, `PGA_HIDE_LISTS`, `PGA_MESSAGE`).
  - Für produktspezifische Beschränkungen erstellt das Modul wahrscheinlich eine benutzerdefinierte Datenbanktabelle (z. B. `ps_pga_product_group`), um die Zuordnung zwischen `id_product` und `id_group` zu speichern. Die `install()`-Methode in `pga/index.php` würde diese Tabelle definieren.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Potenziell verwendet, um modulspezifisches CSS/JS für die Front-Office-Anzeige zu laden (z. B. wenn eine benutzerdefinierte Nachricht gestylt werden muss) oder um frühe Prüfungen für die Produktseitenumleitung durchzuführen. |
| `displayRightColumn` / `displayLeftColumn` | In der rechten/linken Seitenleiste von Front-Office-Seiten. | Weniger wahrscheinlich für dieses Modul, könnte aber verwendet werden, um einen benutzerdefinierten Block anzuzeigen (z. B. „Melden Sie sich für exklusiven Zugang an“), falls konfiguriert. |
| `displayProductButtons` / `displayProductActions` (oder ähnliche Produktseiten-Hooks) | Auf der Produktseite, in der Nähe des „In den Warenkorb“-Buttons. | Wird verwendet, um den „In den Warenkorb“-Button für unautorisierte Benutzer auszublenden oder zu deaktivieren oder um die benutzerdefinierte Beschränkungsnachricht anzuzeigen. |
| `displayFooter` | Im Footer jeder Front-Office-Seite. | Weniger üblich für die Kernfunktionalität, könnte aber für spät ladende Skripte oder Analysen im Zusammenhang mit dem Produktzugriff verwendet werden. |
| `actionCartSave` / `actionObjectCartAddAfter` (oder ähnliche Warenkorb-Hooks) | Wenn ein Produkt in den Warenkorb gelegt oder gespeichert wird. | **KRITISCH:** Hier fängt das Modul den Warenkorbprozess ab, um zu prüfen, ob das hinzugefügte Produkt für die Gruppe des aktuellen Kunden eingeschränkt ist. Wenn eingeschränkt, verhindert es das Hinzufügen oder markiert den Artikel als ungültig und zeigt die benutzerdefinierte Nachricht an. |
| `actionProductListOverride` (oder ähnliche Produktlisten-Hooks) | Wenn PrestaShop eine Liste von Produkten generiert (z. B. Kategorieseite, Suchergebnisse). | **KRITISCH:** Wird verwendet, um eingeschränkte Produkte aus Produktlisten herauszufiltern, wenn „Produkt in Produktlisten ausblenden“ aktiviert ist. |
| `actionDispatcherBefore` / `actionFrontControllerSetMedia` | Bevor ein Front-Controller versendet wird oder bevor Medien-Assets gesetzt werden. | Könnte verwendet werden, um die Umleitungslogik für „Möglichkeit zum Anzeigen der Produktseite blockieren“ zu implementieren, indem die angeforderte Produkt-ID mit den Beschränkungen abgeglichen wird. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Produktzugriff“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei Fragen oder Problemen gerne zur Verfügung.
