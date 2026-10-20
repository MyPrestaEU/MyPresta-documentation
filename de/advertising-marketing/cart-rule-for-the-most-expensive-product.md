---
title: "Warenkorb-Regel für das teuerste Produkt – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Warenkorb-Regel für das teuerste Produkt' von MyPresta.eu."
sidebar:
  label: "Warenkorb-Regel für das teuerste Produkt"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Cart rule for the most expensive product auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/cart-rule-for-the-most-expensive-product.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/cart-rule-for-the-most-expensive-product/)
>
> ---


# Warenkorb-Regel für das teuerste Produkt

## 1. Anforderungen & Kompatibilität

-   **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x
-   **PHP-Kompatibilität**: PHP 7.1 - 8.5
-   **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)
Nach der Installation klicken Sie im Modul-Manager neben dem Modul auf „Konfigurieren“. Dies führt Sie zum Hauptkonfigurationsbildschirm für „Warenkorb-Regel für das teuerste Produkt“.

#### Einstellungen & Optionen:

-   **MyPresta.eu Live-Updates (mypresta_updates)**
    -   **Was diese Einstellung bewirkt:** Diese Einstellung steuert, ob das Modul direkt von MyPresta.eu nach Updates suchen kann. Sie hilft sicherzustellen, dass Sie immer die neueste Version mit Fehlerbehebungen und neuen Funktionen verwenden.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert (JA):* Das Modul verbindet sich regelmäßig mit MyPresta.eu, um nach neuen Versionen zu suchen. Wenn ein Update verfügbar ist, sehen Sie möglicherweise eine Benachrichtigung in Ihrem PrestaShop Back Office.
        -   *Wenn deaktiviert (NEIN):* Das Modul sucht nicht automatisch nach Updates. Sie müssen Updates manuell von Ihrem MyPresta.eu-Konto überprüfen und herunterladen.
    -   **Empfohlener Wert:** JA
    -   **Händlerszenario / Beispiel:** Wenn diese Option aktiviert ist, erhalten Sie zeitnahe Benachrichtigungen für kritische Updates, was die Sicherheit und Kompatibilität ohne manuellen Aufwand verbessert.

-   **Ausgeschlossene Produkte (csc_excluded_products)**
    -   **Was diese Einstellung bewirkt:** Dieses Feld ermöglicht es Ihnen, Produkte anzugeben, die *niemals* für den Rabatt auf das „teuerste Produkt“ berücksichtigt werden sollen, selbst wenn sie tatsächlich der preisintensivste Artikel im Warenkorb sind. Dies ist nützlich für Produkte mit sehr geringen Margen, spezielle Aktionen oder Artikel, die Sie nicht rabattieren möchten.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn Produkt-IDs eingegeben werden:* Das Modul ignoriert diese spezifischen Produkte bei der Bestimmung, welcher Artikel der „teuerste“ für die Warenkorb-Regel ist. Wenn eines dieser ausgeschlossenen Produkte das preisintensivste ist, sucht das Modul nach dem nächstteuersten *nicht ausgeschlossenen* Produkt, um den Rabatt darauf anzuwenden.
        -   *Wenn leer gelassen:* Alle Produkte im Warenkorb sind berechtigt, als „teuerstes“ für den Rabatt identifiziert zu werden.
    -   **Empfohlener Wert:** Leer lassen, es sei denn, Sie möchten bestimmte Produkte ausschließen.
    -   **Händlerszenario / Beispiel:** Sie verkaufen ein sehr beliebtes Produkt mit hoher Marge (ID 123) und einige Lockvogel-Artikel (ID 456, ID 789). Sie möchten, dass der Rabatt auf das „teuerste Produkt“ auf Ihre Artikel mit hoher Marge angewendet wird, aber nicht auf die Lockvogel-Artikel. Sie würden `456,789` (durch Kommas getrennte Produkt-IDs) in dieses Feld eingeben.

#### 2.1.1 Warenkorb-Regel Bearbeitungsseite (Back Office > Katalog > Rabatte > Warenkorb-Regeln > Neu hinzufügen / Bearbeiten)
Dieses Modul fügt eine neue Option direkt zur Standard-PrestaShop-Seite für die Erstellung/Bearbeitung von Warenkorb-Regeln hinzu. Sie finden diese Option, wenn Sie eine Warenkorb-Regel erstellen oder ändern, die einen **prozentualen Rabatt** verwendet.

-   **Menüpfad:** Back Office > Katalog > Rabatte > Warenkorb-Regeln. Klicken Sie auf „Neue Warenkorb-Regel hinzufügen“ oder bearbeiten Sie eine bestehende.
-   **Verfügbare Aktion:** Auf dem Tab „Aktionen“ der Warenkorb-Regel-Konfiguration erscheint ein neues Kontrollkästchen, nachdem Sie „Prozentsatz“ für die Option „Rabatt anwenden“ ausgewählt haben.

    -   **Rabatt nur auf das teuerste Produkt anwenden**
        -   **Was diese Einstellung bewirkt:** Dies ist die Kernfunktionalität des Moduls. Wenn diese Option für eine bestimmte Warenkorb-Regel aktiviert ist, wird der für diese Regel definierte prozentuale Rabatt nur auf das einzelne teuerste Produkt im Warenkorb des Kunden angewendet.
        -   **Auswirkung der Änderung dieser Einstellung:**
            -   *Wenn aktiviert (angekreuzt):* Der prozentuale Rabatt der Warenkorb-Regel wird ausschließlich auf der Grundlage des Preises des preisintensivsten Produkts im Warenkorb berechnet (ausgenommen Produkte, die Sie in der Hauptkonfiguration des Moduls global ausgeschlossen haben).
            -   *Wenn deaktiviert (nicht angekreuzt):* Die Warenkorb-Regel verhält sich wie ein standardmäßiger PrestaShop-Prozentrabatt und wendet den Rabatt auf den gesamten Warenkorbwert oder auf berechtigte Produkte gemäß anderen Warenkorb-Regel-Konfigurationen an (z. B. Produktauswahl, Mindestbetrag).
        -   **Empfohlener Wert:** Aktivieren Sie dies nur für Warenkorb-Regeln, bei denen Sie gezielt den teuersten Artikel ansprechen möchten.
        -   **Händlerszenario / Beispiel:** Sie möchten eine Aktion „20 % Rabatt auf Ihren größten Artikel“ durchführen. Sie erstellen eine neue Warenkorb-Regel, stellen den Rabatt auf 20 % (Prozentsatz) ein und aktivieren dann dieses Kontrollkästchen. Wenn Kunden diesen Gutschein verwenden, erhalten sie 20 % Rabatt auf ihren teuersten Artikel, nicht 20 % Rabatt auf ihre gesamte Bestellung.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Modul-Konfiguration | MyPresta.eu Live-Updates | JA | Ermöglicht automatische Update-Prüfungen für das Modul. |
| Modul-Konfiguration | Ausgeschlossene Produkte | Leer | Durch Kommas getrennte Produkt-IDs, die von der Berechnung des „teuersten Produkts“ ausgeschlossen werden sollen. |
| Warenkorb-Regel bearbeiten (Aktionen-Tab) | Rabatt nur auf das teuerste Produkt anwenden | Nicht angekreuzt | Wenn angekreuzt, wird der prozentuale Rabatt nur auf den preisintensivsten Artikel im Warenkorb angewendet. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Der Rabatt wird nicht auf das teuerste Produkt angewendet, oder er funktioniert überhaupt nicht.**
A:
1.  **Warenkorb-Regel-Konfiguration prüfen:** Gehen Sie zu **Katalog > Rabatte > Warenkorb-Regeln**, bearbeiten Sie Ihre Regel und stellen Sie sicher, dass auf dem Tab „Aktionen“ „Rabatt anwenden“ auf „Prozentsatz“ eingestellt ist und das Kontrollkästchen „Rabatt nur auf das teuerste Produkt anwenden“ **aktiviert** ist.
2.  **Produktberechtigung überprüfen:** Überprüfen Sie die Hauptkonfiguration des Moduls (**Module > Modul-Manager > Konfigurieren** für „Warenkorb-Regel für das teuerste Produkt“). Stellen Sie sicher, dass das Produkt, auf das der Rabatt angewendet werden soll, nicht im Feld „Ausgeschlossene Produkte“ aufgeführt ist.
3.  **Cache leeren:** Manchmal kann der PrestaShop-Cache verhindern, dass Änderungen sofort wirksam werden. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie oben rechts auf „Cache leeren“.
4.  **Modulkonflikte:** Wenn Sie andere Module haben, die Warenkorb- oder Rabattberechnungen stark modifizieren, kann es zu einem Konflikt kommen. Versuchen Sie, andere rabattbezogene Module vorübergehend zu deaktivieren, um zu sehen, ob sich das Problem löst.

**F: Kann ich diesen Rabatt nur auf eine bestimmte Produktkategorie anwenden?**
A: Ja, Sie können die Funktionalität dieses Moduls mit den Standard-Warenkorb-Regel-Einschränkungen von PrestaShop kombinieren. Auf dem Tab „Bedingungen“ Ihrer Warenkorb-Regel können Sie Bedingungen wie „Produktauswahl“ hinzufügen, um festzulegen, dass der Rabatt nur angewendet wird, wenn ein Produkt aus einer bestimmten Kategorie im Warenkorb ist. Beachten Sie jedoch, dass *wenn* ein solches Produkt vorhanden ist, das Modul immer noch das *insgesamt* teuerste Produkt im Warenkorb auswählt (es sei denn, dieses Produkt ist ausgeschlossen) und den Rabatt darauf anwendet, nicht unbedingt das teuerste Produkt *aus dieser spezifischen Kategorie*.

**F: Funktioniert dieses Modul mit festen Betragsrabatten?**
A: Nein, dieses Modul ist speziell für die Arbeit mit **prozentualen Rabatten** konzipiert. Die Option „Rabatt nur auf das teuerste Produkt anwenden“ wird nur angezeigt und funktioniert, wenn Sie „Prozentsatz“ als Rabattart auf dem Tab „Aktionen“ der Warenkorb-Regel auswählen.

**F: Mein benutzerdefiniertes Theme zeigt den Rabatt nicht korrekt an.**
A: Das Modul ändert hauptsächlich die Logik der Rabattberechnung, nicht die Anzeige im Front-Office. Die Standardvorlagen von PrestaShop sollten den Rabatt korrekt anzeigen. Wenn Ihr benutzerdefiniertes Theme die Warenkorb- oder Checkout-Zusammenfassung stark angepasst hat, sind möglicherweise geringfügige Anpassungen erforderlich, um die Anwendung der Rabatte korrekt widerzuspiegeln. In den meisten Fällen sollte das Leeren des Smarty-Caches (**Erweiterte Einstellungen > Leistung > Cache leeren**) Anzeigeprobleme beheben. Falls nicht, wenden Sie sich an Ihren Theme-Entwickler.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht
Das Modul „Warenkorb-Regel für das teuerste Produkt“ (`crexpensive`) erweitert hauptsächlich die Kernklasse `CartRule` von PrestaShop durch einen Override. Dies ermöglicht es, benutzerdefinierte Logik in den Rabattberechnungsprozess einzuschleusen, ohne Kerndateien direkt zu ändern. Das Modul bietet auch eine minimale Konfigurationsoberfläche im Back Office und registriert einen Hook, um das notwendige JavaScript für die Admin-Formulare einzufügen.

### 4.2 Controller (`controllers/`)
Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Controller ein. Seine Funktionalität ist über Overrides und Hooks direkt in bestehende PrestaShop-Prozesse integriert.

### 4.3 Kernklassen & Modelle (`classes/`)

-   **`crexpensive/override/classes/CartRule.php`**
    *   **Klassenname:** `CartRule` (überschreibt die Kernklasse `CartRule`)
    *   **Elternklasse:** `CartRuleCore`
    *   **Verantwortlichkeit:** Dieser Override ist das Herzstück der Modulfunktionalität. Er modifiziert das Verhalten der Anwendung von Warenkorb-Regeln, insbesondere die Berechnung von `reduction_percent`.
    *   **Schlüsselmethoden & Logik:**
        *   Der Override fängt wahrscheinlich Methoden ab oder modifiziert sie, die mit der `reduction_percent`-Berechnung innerhalb der `CartRule`-Klasse zusammenhängen. Er wird Logik enthalten, um:
            1.  Zu prüfen, ob die aktuelle Warenkorb-Regel das Flag `apply_to_most_expensive_product` aktiviert hat (ein vom Modul hinzugefügtes benutzerdefiniertes Feld).
            2.  Falls aktiviert, die Produkte im Warenkorb zu durchlaufen, um das teuerste zu identifizieren, unter Berücksichtigung aller global ausgeschlossenen Produkte, die im Modul konfiguriert sind.
            3.  Die Anwendung von `reduction_percent` so anzupassen, dass sie nur das identifizierte teuerste Produkt betrifft, um sicherzustellen, dass der Rabatt gegen dessen Preis und nicht gegen den gesamten Warenkorb oder andere Produkte berechnet wird.
        *   Es fügt auch ein neues Feld zur `CartRule`-Definition (`$definition`) hinzu, um das Flag `apply_to_most_expensive_product` in der Datenbanktabelle `ps_cart_rule` zu speichern.

### 4.4 JavaScript-Assets (`views/js/`)

-   **`crexpensive/views/js/crexpensive.js`**
    *   **Geltungsbereich:** Back-Office (insbesondere die Bearbeitungsseite für Warenkorb-Regeln).
    *   **Verantwortlichkeit:** Dieses Skript ist dafür verantwortlich, das Kontrollkästchen „Rabatt nur auf das teuerste Produkt anwenden“ auf der Bearbeitungsseite für Warenkorb-Regeln dynamisch ein- und auszublenden.
    *   **Schlüssellogik:**
        *   Es lauscht wahrscheinlich auf Änderungen an den Dropdown-Menüs/Radio-Buttons für „Rabatt anwenden“ (insbesondere wenn „Prozentsatz“ ausgewählt ist).
        *   Wenn „Prozentsatz“ ausgewählt ist, wird das benutzerdefinierte Kontrollkästchen sichtbar gemacht.
        *   Wenn andere Rabattarten (z. B. „Betrag“, „Kostenloser Versand“) ausgewählt sind, wird das Kontrollkästchen ausgeblendet, da das Modul nur für prozentuale Rabatte gilt.
        *   Stellt sicher, dass der Status des Kontrollkästchens beim Bearbeiten einer bestehenden Warenkorb-Regel korrekt geladen wird.

### 4.5 CSS-Stylesheets (`views/css/`)
Dieses Modul enthält keine benutzerdefinierten CSS-Dateien. Es verlässt sich auf die Standard-Styling von PrestaShop für seine Konfigurationselemente und das eingefügte Kontrollkästchen auf der Warenkorb-Regel-Seite.

### 4.6 Smarty-Template-Struktur (`views/templates/`)
Dieses Modul enthält keine benutzerdefinierten Smarty-Template-Dateien. Das Konfigurationsformular wird über `getContent()` in der Hauptmoduldatei gerendert, und das benutzerdefinierte Kontrollkästchen wird über JavaScript in die vorhandene Bearbeitungsseite für Warenkorb-Regeln eingefügt.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:
    *   Das Modul modifiziert die Tabelle `ps_cart_rule` durch Hinzufügen einer neuen Spalte, wahrscheinlich benannt `apply_to_most_expensive_product` (oder ähnlich), die ein Tinyint (Boolean)-Feld ist, um den Status des benutzerdefinierten Kontrollkästchens für jede Warenkorb-Regel zu speichern.
    *   Konfigurationswerte (`mypresta_updates`, `csc_excluded_products`) werden in der Tabelle `ps_configuration` gespeichert.

-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| :-------- | :--------------- | :---------------- |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin-Controller seine Medien-Assets (JS/CSS) festlegt. | Dieser Hook wird verwendet, um `crexpensive.js` auf der Bearbeitungsseite für Warenkorb-Regeln im Back Office zu laden, wodurch die dynamische Anzeige des Kontrollkästchens „Rabatt nur auf das teuerste Produkt anwenden“ ermöglicht wird. |

## 5. Offizieller Support & Updates
Für offizielle Updates, technischen Support und um die neuesten Versionen des Moduls „Warenkorb-Regel für das teuerste Produkt“ zu erhalten, besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen gerne zur Verfügung.
