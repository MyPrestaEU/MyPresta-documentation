---
title: "Ausgewählte Produkte vom kostenlosen Versand ausschließen – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Ausgewählte Produkte vom kostenlosen Versand ausschließen“ von MyPresta.eu."
sidebar:
  label: "Ausgewählte Produkte vom kostenlosen Versand ausschließen – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Exclude selected products from free shipping auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/exclude-selected-products-from-free-shipping.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/exclude-selected-products-from-free-shipping/)
>
> ---


# Ausgewählte Produkte vom kostenlosen Versand ausschließen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptbildschirm, auf dem Sie die Kernregeln für den Ausschluss von Produkten vom kostenlosen Versand definieren.

#### 2.1.1 Allgemeine Einstellungen

- **Gutscheincode mit kostenlosem Versand entfernen**

  - **Was diese Einstellung bewirkt:** Diese Option bestimmt, ob ein Gutschein für kostenlosen Versand (eine `CartRule`, die kostenlosen Versand gewährt) aus dem Warenkorb des Kunden entfernt oder ungültig gemacht werden soll, wenn ein ausgeschlossenes Produkt vorhanden ist.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Wenn ein Kunde einen Gutschein für kostenlosen Versand anwendet und dann ein Produkt hinzufügt, das Sie zum Ausschluss markiert haben, versucht das Modul, diesen Gutschein aus seinem Warenkorb zu entfernen. Dies stellt sicher, dass selbst mit einem Gutschein kein kostenloser Versand für ausgeschlossene Artikel gewährt wird.
    - *Wenn deaktiviert (NEIN):* Gutscheine für kostenlosen Versand bleiben aktiv, auch wenn ein ausgeschlossenes Produkt im Warenkorb ist. Dies bedeutet, dass ein Kunde möglicherweise immer noch kostenlosen Versand über einen Gutschein erhalten könnte, wodurch die produktbasierte Ausschließung des Moduls außer Kraft gesetzt wird.
  - **Empfohlener Wert:** **JA**. Dies bietet die konsistenteste Kontrolle über Ihre Versandkosten und verhindert kostenlosen Versand, selbst wenn ein Gutschein verwendet wird.
  - **Händlerszenario / Beispiel:** Sie verkaufen große Möbelstücke, die immer Versandkosten verursachen. Sie bieten auch einen „FREESHIP“-Gutschein für Bestellungen über 100 € an. Wenn ein Kunde ein Sofa (ein ausgeschlossenes Produkt) hinzufügt und den „FREESHIP“-Gutschein verwendet, wird durch Aktivierung dieser Einstellung der Gutschein entfernt, wodurch sichergestellt wird, dass er den Versand für das Sofa bezahlt.
- **Nicht vorrätige Produkte ausschließen**

  - **Was diese Einstellung bewirkt:** Diese Option ermöglicht es Ihnen, Produkte, die derzeit nicht vorrätig sind, automatisch vom kostenlosen Versand auszuschließen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Wenn ein Produkt nicht vorrätig und im Warenkorb des Kunden ist und Sie es auch zum Ausschluss markiert haben, wendet das Modul seine Regeln an. Dies ist im Allgemeinen weniger relevant, da nicht vorrätige Produkte oft ohnehin nicht bestellt werden können, aber es gewährleistet Konsistenz.
    - *Wenn deaktiviert (NEIN):* Das Modul berücksichtigt den Lagerstatus nicht, wenn es seine Ausschlussregeln anwendet.
  - **Empfohlener Wert:** **NEIN**. Diese Einstellung ist oft redundant, da nicht vorrätige Produkte normalerweise nicht in den Warenkorb gelegt oder bestellt werden können. Lassen Sie sie deaktiviert, es sei denn, Sie haben einen bestimmten Grund, sie zu verwenden (z. B. die Erlaubnis von Nachbestellungen, bei denen der kostenlose Versand weiterhin blockiert werden sollte).
  - **Händlerszenario / Beispiel:** Sie erlauben Nachbestellungen für bestimmte Artikel. Wenn ein Artikel nachbestellt wird (nicht vorrätig) und es sich auch um einen großen, schweren Artikel handelt, den Sie niemals kostenlos versenden, stellt die Aktivierung dieser Einstellung sicher, dass er auch bei Nachbestellung dazu beiträgt, den kostenlosen Versand zu deaktivieren.

#### 2.1.2 Regeln für den Ausschluss vom kostenlosen Versand

- **Kostenlosen Versand für ausgewählte Produkte deaktivieren**

  - **Was diese Einstellung bewirkt:** Dies ist die Kernfunktionalität. Sie ermöglicht es Ihnen, einzelne Produkte festzulegen, die, wenn sie sich im Warenkorb befinden, den kostenlosen Versand deaktivieren.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Das Modul sucht nach den spezifischen Produkten, die Sie der Ausschlussliste hinzugefügt haben. Wenn eines dieser Produkte im Warenkorb des Kunden ist, wird der kostenlose Versand deaktiviert.
    - *Wenn deaktiviert (NEIN):* Keine einzelnen Produkte deaktivieren den kostenlosen Versand, unabhängig davon, was in der Ausschlussliste steht.
  - **Empfohlener Wert:** **JA**. Aktivieren Sie dies, um die Hauptfunktion des Moduls zu nutzen.
  - **Händlerszenario / Beispiel:** Sie verkaufen feinen Schmuck (klein, leicht, normalerweise kostenloser Versand) und auch große Vitrinen (schwer, teuer im Versand). Sie würden dies aktivieren und die Vitrinen zur Ausschlussliste hinzufügen.
- **Kostenlosen Versand für ausgewählte Kategorien deaktivieren**

  - **Was diese Einstellung bewirkt:** Ähnlich wie bei Produkten ermöglicht diese Option die Auswahl ganzer Produktkategorien. Wenn *irgendein* Produkt aus einer ausgewählten Kategorie im Warenkorb des Kunden ist, wird der kostenlose Versand deaktiviert.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Das Modul prüft, ob ein Produkt im Warenkorb zu einer der von Ihnen zum Ausschluss ausgewählten Kategorien gehört. Wenn ja, wird der kostenlose Versand deaktiviert.
    - *Wenn deaktiviert (NEIN):* Keine Kategorien deaktivieren den kostenlosen Versand.
  - **Empfohlener Wert:** **JA**, wenn Sie ganze Produktgruppen haben, die niemals für kostenlosen Versand qualifiziert sein sollten.
  - **Händlerszenario / Beispiel:** Sie verkaufen sowohl Bücher als auch große Kunstdrucke. Alle Kunstdrucke erfordern eine spezielle Verpackung und Versand. Sie würden dies aktivieren und die Kategorie „Kunstdrucke“ auswählen. Jeder Kunstdruck im Warenkorb deaktiviert den kostenlosen Versand.

#### 2.1.3 Produkt- & Kategorieauswahl-Oberfläche

Unter diesen Einstellungen finden Sie zwei Abschnitte:

- **Produkte, die vom kostenlosen Versand ausgeschlossen werden sollen:** Eine Suchleiste und eine Liste der aktuell ausgeschlossenen Produkte.
  - **Anwendung:** Beginnen Sie, den Namen eines Produkts in die Suchleiste einzugeben. Während Sie tippen, erscheint eine Liste passender Produkte. Klicken Sie auf ein Produkt, um es der Ausschlussliste hinzuzufügen. Um ein Produkt zu entfernen, klicken Sie auf das „X“ neben seinem Namen in der Liste.
- **Kategorien, die vom kostenlosen Versand ausgeschlossen werden sollen:** Eine Baumansicht der Kategorien Ihres Shops mit Kontrollkästchen.
  - **Anwendung:** Aktivieren Sie das Kontrollkästchen neben jeder Kategorie, die Sie ausschließen möchten. Alle Produkte innerhalb dieser Kategorie (und ihrer Unterkategorien, abhängig vom Kategorieverhalten Ihrer PrestaShop-Version) deaktivieren den kostenlosen Versand, wenn sie im Warenkorb vorhanden sind.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modul-Hauptkonfiguration | Gutscheincode mit kostenlosem Versand entfernen | JA | Stellt sicher, dass Gutscheine für kostenlosen Versand entfernt werden, wenn ausgeschlossene Produkte im Warenkorb sind. |
| Modul-Hauptkonfiguration | Nicht vorrätige Produkte ausschließen | NEIN | Im Allgemeinen nicht erforderlich, da nicht vorrätige Artikel oft nicht bestellt werden können. |
| Modul-Hauptkonfiguration | Kostenlosen Versand für ausgewählte Produkte deaktivieren | JA | Aktiviert den produktspezifischen Ausschluss vom kostenlosen Versand. |
| Modul-Hauptkonfiguration | Kostenlosen Versand für ausgewählte Kategorien deaktivieren | JA | Aktiviert den kategoriespezifischen Ausschluss vom kostenlosen Versand. |
| Modul-Hauptkonfiguration | Produkte, die vom kostenlosen Versand ausgeschlossen werden sollen | (Leer) | Fügen Sie hier spezifische Produkte mit dem Suchwerkzeug hinzu. |
| Modul-Hauptkonfiguration | Kategorien, die vom kostenlosen Versand ausgeschlossen werden sollen | (Keine ausgewählt) | Wählen Sie Kategorien aus der Baumansicht aus. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul konfiguriert, aber der kostenlose Versand wird immer noch für ein ausgeschlossenes Produkt angezeigt. Was ist falsch?**
A:

1.  **Überprüfen Sie Ihre Einstellungen:** Überprüfen Sie nochmals, ob „Kostenlosen Versand für ausgewählte Produkte deaktivieren“ (oder Kategorien) aktiviert ist und ob das spezifische Produkt/die Kategorie korrekt zur Ausschlussliste hinzugefügt wurde.
2.  **PrestaShop-Cache leeren:** Gehen Sie zu **Erweiterte Parameter > Leistung** und klicken Sie oben rechts auf „Cache leeren“. Manchmal speichert PrestaShop Versandberechnungen im Cache.
3.  **Mit einem neuen Warenkorb testen:** Stellen Sie sicher, dass Sie mit einem frischen Warenkorb testen, da Browser-Cache oder Sitzungsdaten stören könnten. Versuchen Sie es in einem Inkognito-Fenster.
4.  **Gutscheinkonflikt:** Wenn Sie einen Gutschein für kostenlosen Versand verwenden, stellen Sie sicher, dass „Gutscheincode mit kostenlosem Versand entfernen“ aktiviert ist.

**F: Beeinflusst dieses Modul meine Standardversandkosten?**
A: Nein, dieses Modul beeinflusst nur die *Verfügbarkeit* der Option „Kostenloser Versand“ (entweder über Warenkorbregeln oder spezifische Versanddienstleister für kostenlosen Versand). Es ändert nicht Ihre Standardversandkosten oder andere Spediteurkonfigurationen. Wenn der kostenlose Versand deaktiviert ist, sehen Kunden einfach Ihre regulären Versandoptionen und bezahlen diese.

**F: Kann ich Produkte stattdessen nach Gewicht oder Abmessungen ausschließen, anstatt nach spezifischen Produkten/Kategorien?**
A: Dieses Modul zielt speziell auf Produkte und Kategorien ab. Die integrierten Versandregeln von PrestaShop ermöglichen es Ihnen, Schwellenwerte für kostenlosen Versand basierend auf dem Gesamtgewicht oder Preis des Warenkorbs zu definieren. Dieses Modul fügt eine *Ausnahmeschicht* über diesen Regeln hinzu. Wenn Sie komplexere Regeln benötigen, die rein auf Gewicht/Abmessungen für *alle* Produkte basieren, benötigen Sie möglicherweise ein fortschrittlicheres Versandmodul oder benutzerdefinierte Spediteurkonfigurationen.

**F: Was passiert, wenn ein Kunde ein ausgeschlossenes Produkt und ein nicht ausgeschlossenes Produkt in seinem Warenkorb hat?**
A: Wenn *irgendein* Produkt im Warenkorb auf Ihrer Ausschlussliste steht (entweder direkt oder über seine Kategorie), wird der kostenlose Versand für den gesamten Warenkorb deaktiviert, selbst wenn andere Produkte im Warenkorb normalerweise qualifiziert wären. Die Logik des Moduls lautet: „Wenn ein ausgeschlossenes Produkt vorhanden ist, dann kein kostenloser Versand.“

**F: Ich verwende ein benutzerdefiniertes Theme, und das Produktsuchwerkzeug funktioniert nicht richtig.**
A: Benutzerdefinierte Themes können manchmal JavaScript stören.

1.  **Auf JavaScript-Fehler prüfen:** Öffnen Sie die Entwicklerkonsole Ihres Browsers (normalerweise F12) und suchen Sie nach Fehlern auf der Registerkarte „Konsole“, wenn Sie versuchen, das Suchwerkzeug zu verwenden.
2.  **Theme-Kompatibilität:** Stellen Sie sicher, dass Ihr Theme vollständig mit Ihrer PrestaShop-Version kompatibel ist.
3.  **Support kontaktieren:** Wenn Sie Fehler sehen oder das Problem weiterhin besteht, senden Sie Screenshots und Konsolenprotokolle an den MyPresta.eu-Support.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Ausgewählte Produkte vom kostenlosen Versand ausschließen“ arbeitet hauptsächlich durch das Überschreiben von PrestaShop-Kernklassen, die mit der Warenkorb- und Warenkorbregelverwaltung zusammenhängen. Dies ermöglicht es, die Logik der kostenlosen Versandberechnung abzufangen und seine Ausschlussregeln anzuwenden, bevor die endgültigen Versandoptionen dem Kunden präsentiert werden. Es nutzt das PrestaShop-Override-System für die Klassen `CartController`, `Cart` und `CartRule`. Das Modul enthält auch einen dedizierten Admin-Controller zum Suchen und Verwalten ausgeschlossener Produkte/Kategorien.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `exfreeshipping/override/controllers/front/CartController.php`
    - **Klassenname & übergeordnete Klasse**: `CartController` (überschreibt `CartControllerCore`)
    - **Verantwortlichkeit**: Dieser Override ist entscheidend, um Aktionen im Zusammenhang mit dem Warenkorb abzufangen, insbesondere wenn Produkte hinzugefügt oder entfernt werden oder wenn Versandberechnungen durchgeführt werden. Er stellt sicher, dass die Logik des Moduls angewendet wird, wann immer sich der Warenkorbstatus ändert und die Berechtigung für kostenlosen Versand beeinflusst.
- **Back-Office-Admin-Controller**:

  - `exfreeshipping/controllers/admin/AdminExfreeshippingSearchController.php`
    - **Tab-Name und verwaltete Entität**: Dieser Controller verwaltet die AJAX-Suchfunktion für Produkte innerhalb der Modulkonfiguration. Er verwaltet kein spezifisches `ObjectModel` direkt, sondern stellt Daten für die Produktausschlussliste bereit.
    - **Zweck**: Reagiert auf AJAX-Anfragen von der Modulkonfigurationsseite, um Produkte nach Namen zu suchen, sodass der Administrator Produkte einfach zum Ausschluss auswählen kann.
  - `exfreeshipping/controllers/admin/index.php`
    - **Zweck**: Dies ist eine standardmäßige leere `index.php`-Datei, die oft in Verzeichnissen enthalten ist, um die Verzeichnisauflistung auf Webservern zu verhindern. Sie enthält keine funktionale Controller-Logik.

### 4.3 Kernklassen & Modelle (`classes/`)

- `exfreeshipping/override/classes/Cart.php`

  - **Klassenname & übergeordnete Klasse**: `Cart` (überschreibt `CartCore`)
  - **Datenbanktabelle**: `ps_cart`
  - **Verantwortlichkeit**: Dieser Override ist zentral für die Funktionalität des Moduls. Er modifiziert wahrscheinlich Methoden im Zusammenhang mit der Versandkostenberechnung oder der Berechtigung für kostenlosen Versand innerhalb des `Cart`-Objekts. Er enthält die Logik, um zu überprüfen, ob ein Produkt im Warenkorb (oder seine Kategorie) auf der Ausschlussliste steht, und wenn ja, das Flag für kostenlosen Versand für diesen Warenkorb zu deaktivieren.
  - **Schlüsselmethoden (wahrscheinlich modifiziert/erweitert)**: `getProducts()`, `getPackageList()`, `getWsShippingCost()`, `getShippingCost()` oder ähnliche Methoden, die die Versandberechtigung bestimmen.
- `exfreeshipping/override/classes/CartRule.php`

  - **Klassenname & übergeordnete Klasse**: `CartRule` (überschreibt `CartRuleCore`)
  - **Datenbanktabelle**: `ps_cart_rule`
  - **Verantwortlichkeit**: Dieser Override ist für die Handhabung der Einstellung „Gutscheincode mit kostenlosem Versand entfernen“ verantwortlich. Er modifiziert Methoden im Zusammenhang mit der Anwendung oder Validierung von Warenkorbregeln, um Gutscheine für kostenlosen Versand zu entfernen, wenn ein ausgeschlossenes Produkt im Warenkorb vorhanden ist.
  - **Schlüsselmethoden (wahrscheinlich modifiziert/erweitert)**: `checkValidity()`, `addCartRule()`, `removeCartRule()` oder ähnliche Methoden, die mit Warenkorbregeln und deren Gültigkeit interagieren.
- `exfreeshipping/override/classes/index.php`

  - **Zweck**: Ähnlich wie die Admin `index.php` ist dies eine leere Datei, um die Verzeichnisauflistung zu verhindern.

### 4.4 JavaScript-Assets (`views/js/`)

- `exfreeshipping/lib/searchTool/views/js/autocomplete.js`
  - **Geltungsbereich**: Back-Office (Modulkonfigurationsseite).
  - **Funktionalität**: Dieses Skript treibt die Produktsuch- und Auswahl-Oberfläche auf der Konfigurationsseite des Moduls an.
  - **Details**:
    - Initialisiert ein Autocomplete-Eingabefeld für die Produktsuche.
    - Bindet Ereignis-Listener (z. B. `keyup`, `change`, `click`) an das Suchfeld und die Ergebnisliste.
    - Sendet AJAX-Anfragen an `AdminExfreeshippingSearchController`, um Produktvorschläge basierend auf der Benutzereingabe abzurufen.
    - Handhabt die Anzeige der Suchergebnisse und ermöglicht Administratoren die Auswahl von Produkten, die zu einem versteckten Eingabefeld oder einer sichtbaren Liste ausgeschlossener Produkte hinzugefügt werden.
    - Verwaltet das Entfernen ausgewählter Produkte aus der Ausschlussliste.

### 4.5 CSS-Stylesheets (`views/css/`)

- `exfreeshipping/lib/searchTool/views/css/autocomplete.css`
  - **Geltungsbereich**: Back-Office (Modulkonfigurationsseite).
  - **Styling**: Bietet Styling für das Autocomplete-Eingabefeld der Produktsuche, die Dropdown-Liste der Suchergebnisse und die Anzeige ausgewählter ausgeschlossener Produkte auf der Konfigurationsseite des Moduls.
  - **Schlüsselselektoren**: Enthält wahrscheinlich Stile für `.autocomplete-input`, `.autocomplete-results`, `.selected-product-tag` usw. Entwickler können diese bei Bedarf in ihren benutzerdefinierten Admin-Themes überschreiben.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Admin-Templates (`views/templates/admin/`)**:
  - `exfreeshipping/lib/searchTool/views/scripts.tpl`
    - **Zweck**: Dieses Template wird wahrscheinlich in der `getContent()`-Methode des Moduls eingebunden, um die notwendige HTML-Struktur für das Produktsuchwerkzeug zu rendern, einschließlich des Sucheingabefeldes und des Bereichs, in dem ausgewählte Produkte angezeigt werden. Es enthält wahrscheinlich auch den `<script>`-Tag zum Laden von `autocomplete.js`.
  - `exfreeshipping/views/tpl/selectedProducts.tpl`
    - **Zweck**: Dieses Template wird verwendet, um die Liste der Produkte zu rendern, die vom kostenlosen Versand ausgeschlossen wurden. Es wird dynamisch durch das JavaScript aktualisiert, wenn Produkte hinzugefügt oder entfernt werden.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Konfigurationseinstellungen werden in der Tabelle `ps_configuration` unter Verwendung von Schlüsseln wie `exfreeshipping_oos`, `exfreeshipping_vcode`, `exfreeshipping_visibility_rule`, `exfreeshipping_visibility_products`, `exfreeshipping_visibility_cat` gespeichert.
  - Die Listen der ausgeschlossenen Produkte und Kategorien werden als serialisierte Arrays oder kommagetrennte Zeichenketten in `ps_configuration` unter `exfreeshipping_visibility_products` bzw. `exfreeshipping_visibility_cat` gespeichert.
- **Registrierte Hooks-Tabelle**:
  Das Modul verwendet hauptsächlich Overrides anstelle direkter Hook-Aufrufe für seine Kernlogik. Es kann jedoch einige Standard-Hooks für die Initialisierung oder spezifische Anzeigezwecke registrieren.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionFrontControllerSetMedia` | Wird ausgeführt, wenn ein Front-Controller seine Medien (CSS/JS) einstellt. | Potenziell zum Laden von Front-Office-spezifischem CSS/JS verwendet, obwohl die primäre Auswirkung des Moduls die Backend-Logik ist. |
| `displayHeader` | Im `<head>`-Abschnitt jeder Front-Office-Seite. | Könnte für die Erstkonfiguration oder das Laden sehr leichter Skripte/Stile verwendet werden, falls erforderlich, aber nicht direkt für die Kernlogik. |
| `displayBackOfficeHeader` | Im `<head>`-Abschnitt jeder Back-Office-Seite. | Wird zum Laden von `autocomplete.js` und `autocomplete.css` für die Konfigurationsseite des Moduls verwendet. |
| `actionCartSave` | Nachdem ein Warenkorb gespeichert oder aktualisiert wurde. | Hier würde die Kernlogik des Moduls zur Überprüfung ausgeschlossener Produkte und zur Deaktivierung des kostenlosen Versands ausgelöst oder neu bewertet werden. |
| `actionValidateOrder` | Wenn eine Bestellung validiert wird. | Stellt sicher, dass die Regeln für den kostenlosen Versand in der letzten Phase des Checkouts korrekt angewendet werden. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und technischen Support für das Modul „Ausgewählte Produkte vom kostenlosen Versand ausschließen“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.
