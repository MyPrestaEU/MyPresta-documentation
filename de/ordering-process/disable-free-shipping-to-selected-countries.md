---
title: "Kostenlosen Versand für ausgewählte Länder deaktivieren – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Kostenlosen Versand für ausgewählte Länder deaktivieren' von MyPresta.eu."
sidebar:
  label: "Kostenlosen Versand für ausgewählte Länder deaktivieren – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Disable free shipping to selected countries auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/disable-free-shipping-to-selected-countries.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/disable-free-shipping-to-selected-countries/)
>
> ---


# Kostenlosen Versand für ausgewählte Länder deaktivieren

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Haupt- und einzige Konfigurationsbildschirm für das Modul „Kostenlosen Versand für ausgewählte Länder deaktivieren“. Sie finden ihn, indem Sie zu **Module > Modul-Manager** navigieren, nach „Kostenlosen Versand für ausgewählte Länder deaktivieren“ suchen und auf „Konfigurieren“ klicken.

#### Kostenlosen Versand aus Ländern ausschließen:

- **Was diese Einstellung bewirkt:** Dies ist die Kerneinstellung des Moduls. Sie ermöglicht es Ihnen, ein oder mehrere Länder auszuwählen, in denen kein kostenloser Versand angeboten werden soll, unabhängig von anderen Regeln für kostenlosen Versand, die Sie möglicherweise eingerichtet haben (z.B. kostenloser Versand ab einem bestimmten Bestellwert).
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn Länder ausgewählt sind:* Wenn die Lieferadresse eines Kunden in einem der ausgewählten Länder liegt, wird die Option „Kostenloser Versand“ aus der Liste der verfügbaren Versanddienstleister während des Checkouts entfernt. Es werden nur kostenpflichtige Versandoptionen angezeigt.
  - *Wenn keine Länder ausgewählt sind:* Das Modul hat keine Auswirkung, und kostenloser Versand wird allen Ländern gemäß Ihren Standard-PrestaShop-Einstellungen angeboten.
- **Empfohlener Wert:** Wählen Sie nur die Länder aus, in denen das Anbieten von kostenlosem Versand für Ihr Unternehmen wirklich unrentabel oder problematisch ist.
- **Händlerszenario / Beispiel:** Sie versenden international, aber der Versand nach Australien und Neuseeland ist aufgrund der Entfernung und des Zolls erheblich teurer. Sie würden „Australien“ und „Neuseeland“ aus dieser Liste auswählen. Nun werden Kunden aus diesen Ländern immer Versandkosten berechnet, selbst wenn ihr Bestellwert in anderen Regionen wie der EU oder den USA für kostenlosen Versand qualifiziert wäre.

#### Kurzübersichtstabelle zur Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | Kostenlosen Versand aus Ländern ausschließen: | Keine ausgewählt | Wählen Sie Länder aus, in denen KEIN kostenloser Versand angeboten werden soll. Wenn die Lieferadresse eines Kunden in einem ausgewählten Land liegt, ist der kostenlose Versand für seine Bestellung nicht verfügbar. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul konfiguriert, aber der kostenlose Versand wird immer noch für ein ausgewähltes Land angezeigt. Was ist falsch?**
A:

1. **Cache leeren:** Leeren Sie immer Ihren PrestaShop-Cache, nachdem Sie Konfigurationsänderungen vorgenommen haben. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie oben rechts auf „Cache leeren“.
2. **Mit neuem Warenkorb testen:** Stellen Sie sicher, dass Sie mit einem frischen Warenkorb und einer auf das ausgeschlossene Land eingestellten Lieferadresse testen. Manchmal können Browser-Cache oder Sitzungsdaten stören.
3. **Versanddienstleister-Einstellungen prüfen:** Vergewissern Sie sich, dass Ihr kostenloser Versanddienstleister (oder der Versanddienstleister, der kostenlosen Versand anbietet) unter **Versand > Versanddienstleister** korrekt konfiguriert ist. Stellen Sie sicher, dass er aktiv ist und „Kostenloser Versand“ aktiviert ist. Dieses Modul *deaktiviert* die Option für kostenlosen Versand, es erstellt keine neuen Versandregeln.
4. **Modulreihenfolge:** In seltenen Fällen, wenn Sie mehrere versandbezogene Module haben, kann es zu einem Konflikt kommen. Versuchen Sie, andere Versandmodule vorübergehend zu deaktivieren, um das Problem zu isolieren.

**F: Beeinflusst dieses Modul andere Versandkosten?**
A: Nein, dieses Modul beeinflusst *nur* die Verfügbarkeit der Option „Kostenloser Versand“. Es ändert oder entfernt keine kostenpflichtigen Versandoptionen oder deren Kosten. Wenn der kostenlose Versand für ein Land deaktiviert ist, werden den Kunden einfach die standardmäßigen kostenpflichtigen Versandoptionen angezeigt, die für ihren Warenkorb und ihr Ziel verfügbar sind.

**F: Kann ich den kostenlosen Versand für bestimmte Produkte oder Kategorien anstelle von Ländern deaktivieren?**
A: Nein, dieses Modul wurde speziell entwickelt, um den kostenlosen Versand basierend auf dem *Lieferland* zu deaktivieren. Es bietet keine Optionen, um den kostenlosen Versand basierend auf Produkt, Kategorie oder Kundengruppe auszuschließen. Wenn Sie eine solche Funktionalität benötigen, würden Sie ein anderes, fortschrittlicheres Modul für Versandregeln benötigen.

**F: Was ist, wenn ich kostenlosen Versand in ein Land für Bestellungen über einem bestimmten Betrag anbieten möchte, ihn aber für niedrigere Beträge deaktivieren möchte?**
A: Dieses Modul deaktiviert *jeglichen* kostenlosen Versand für die ausgewählten Länder. Wenn Sie bedingten kostenlosen Versand wünschen (z.B. kostenloser Versand über X $), sollten Sie dies direkt in Ihren PrestaShop-Versanddienstleister-Einstellungen (Versand > Versanddienstleister) konfigurieren. Dieses Modul würde dann diese Einstellung für die ausgeschlossenen Länder überschreiben, wodurch der kostenlose Versand für diese spezifischen Ziele bei *jedem* Betrag nicht verfügbar wäre.

## 4. Entwickler- & Webmaster-Leitfaden (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Kostenlosen Versand für ausgewählte Länder deaktivieren“ funktioniert, indem es zentrale PrestaShop-Klassen im Zusammenhang mit dem Verhalten von Versanddienstleistern und Warenkörben überschreibt. Insbesondere modifiziert es die Logik, die bestimmt, ob ein Versanddienstleister kostenlosen Versand anbietet und ob ein Warenkorb dafür qualifiziert ist, basierend auf dem Lieferland des Kunden. Dies wird durch das PrestaShop-Override-System erreicht, wodurch sichergestellt wird, dass die Modullogik immer dann angewendet wird, wenn Versandberechnungen durchgeführt werden.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Seine Logik wird direkt über Klassen-Overrides in die Kernfunktionalität von PrestaShop injiziert.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul implementiert seine Funktionalität hauptsächlich durch Klassen-Overrides, die sich im Verzeichnis `override/classes/` innerhalb des Modulordners befinden.

- **`exfsc/override/classes/Carrier.php`**

  - **Klassenname & Elternklasse:** `Carrier` (überschreibt die Kernklasse `Carrier`)
  - **Verantwortlichkeit:** Dieser Override modifiziert die Methode `isFree()` der Klasse `Carrier`. Wenn PrestaShop überprüft, ob ein bestimmter Versanddienstleister kostenlosen Versand anbietet, fängt dieser Override den Aufruf ab. Er überprüft, ob das Lieferland des aktuellen Warenkorbs zu den Ländern gehört, die für den kostenlosen Versand ausgeschlossen sind. Wenn dies der Fall ist und die ursprüngliche `isFree()`-Methode `true` zurückgegeben hätte, erzwingt dieser Override die Rückgabe von `false`, wodurch der kostenlose Versand für diesen Versanddienstleister für das ausgeschlossene Land effektiv deaktiviert wird.
  - **Schlüsselmethoden:**
    - `isFree($cart)`: Modifiziert, um die Konfiguration `exfsc_country` zu überprüfen und `false` zurückzugeben, wenn das Lieferland des Warenkorbs ausgeschlossen ist und die ursprüngliche Methode `true` zurückgegeben hätte.
- **`exfsc/override/classes/Cart.php`**

  - **Klassenname & Elternklasse:** `Cart` (überschreibt die Kernklasse `Cart`)
  - **Verantwortlichkeit:** Dieser Override modifiziert die Methode `getDeliveryOptionList()`. Diese Methode ist für die Generierung der Liste der verfügbaren Lieferoptionen (einschließlich Versanddienstleister und deren Dienste) während des Checkouts verantwortlich. Der Override stellt sicher, dass, wenn ein Versanddienstleister als „kostenloser Versand“ markiert ist, das Lieferland jedoch vom Modul ausgeschlossen ist, dieser Versanddienstleister korrekt mit seinen *kostenpflichtigen* Versandoptionen präsentiert wird, oder, wenn er nur kostenlosen Versand anbietet, vollständig ausgeschlossen wird.
  - **Schlüsselmethoden:**
    - `getDeliveryOptionList(Country $default_country = null, $product_list = null, $id_zone = null)`: Modifiziert, um sicherzustellen, dass als kostenlos markierte Versanddienstleister korrekt gegen die Länderausschlussliste des Moduls bewertet werden.
- **`exfsc/override/classes/index.php`**

  - **Zweck:** Dies ist eine leere `index.php`-Datei, die typischerweise in Verzeichnissen enthalten ist, um die Verzeichnisauflistung zu verhindern, wenn direkt über einen Webbrowser zugegriffen wird, was die Sicherheit erhöht. Sie hat keine funktionale Auswirkung auf die Logik des Moduls.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul enthält keine benutzerdefinierten JavaScript-Dateien. Die gesamte Funktionalität wird serverseitig verarbeitet.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul enthält keine benutzerdefinierten CSS-Dateien. Die gesamte Funktionalität wird serverseitig verarbeitet.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul enthält keine benutzerdefinierten Smarty-Template-Dateien. Seine Effekte werden in bestehende PrestaShop-Checkout-Templates integriert, indem die zugrunde liegenden Daten, die an sie übergeben werden, modifiziert werden.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Konfigurationseinstellungen werden in der Tabelle `ps_configuration` gespeichert.
    - `exfsc_country`: Speichert eine durch Kommas getrennte Liste von `id_country`-Werten für Länder, in denen der kostenlose Versand deaktiviert ist.
    - `mypresta_updates`, `update_`, `updatev_`: Interne Konfigurationsschlüssel, die von MyPresta.eu-Modulen für Update-Prüfungen verwendet werden.
    - `exfsc_visibility_cat`, `exfsc_visibility_products`: Diese Schlüssel sind in der Methode `getContent()` vorhanden, werden aber von der Kernlogik des Moduls, wie im Funktionsumfang beschrieben, nicht aktiv verwendet. Sie könnten Überbleibsel oder Platzhalter für potenzielle zukünftige Funktionen sein.
- **Registrierte Hooks-Tabelle**:
  Das Modul registriert keine expliziten Front-Office-Hooks. Seine Funktionalität wird durch Klassen-Overrides implementiert, die automatisch durch die Kernprozesse von PrestaShop ausgelöst werden, wenn Versandoptionen berechnet werden.
  Die `install()`-Methode des Moduls kann Standard-Back-Office-Hooks für die Modulverwaltung registrieren (z.B. `displayBackOfficeHeader`), diese dienen jedoch administrativen Zwecken und beeinflussen das Front-Office-Verhalten nicht.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul „Kostenlosen Versand für ausgewählte Länder deaktivieren“ verweisen wir Sie auf Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, sicherzustellen, dass Ihr Modul perfekt mit Ihrem PrestaShop-Shop funktioniert.
