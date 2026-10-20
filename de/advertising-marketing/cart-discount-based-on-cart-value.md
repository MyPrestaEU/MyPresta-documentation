---
title: "Warenkorbrabatt basierend auf Warenkorbwert – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Warenkorbrabatt basierend auf Warenkorbwert' von MyPresta.eu."
sidebar:
  label: "Warenkorbrabatt basierend auf Warenkorbwert – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Cart discount based on cart value auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/cart-discount-based-on-cart-value.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/cart-discount-based-on-cart-value/)
>
> ---


# Warenkorbrabatt basierend auf Warenkorbwert

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind erforderlich, die typischerweise in den meisten PrestaShop-kompatiblen Hosting-Umgebungen verfügbar sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptbildschirm, auf dem Sie das Gesamtverhalten und die Einstellungen Ihres Warenkorbrabattprogramms steuern.

- **Programm aktivieren**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter, um das gesamte Warenkorbrabattprogramm ein- oder auszuschalten.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Das Modul überprüft aktiv die Warenkorbwerte und wendet Rabatte gemäß Ihren definierten Regeln an.
    - *Wenn deaktiviert (NEIN):* Es werden keine Warenkorbrabatte angewendet und keine entsprechenden Nachrichten auf der Warenkorbseite angezeigt, unabhängig von anderen Einstellungen.
  - **Empfohlener Wert:** JA (sobald Sie Ihre Rabattregeln konfiguriert haben).
  - **Händlerszenario / Beispiel:** Sie könnten es vorübergehend während eines Sonderverkaufs deaktivieren, bei dem andere Rabattregeln gelten, oder wenn Sie Wartungsarbeiten durchführen müssen.
- **Warenkorbrabattprogramm für ausgewählte Kundengruppen deaktivieren**

  - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, bestimmte Kundengruppen (z. B. Großhändler, VIPs oder Gäste) von diesen Warenkorbwert-basierten Rabatten auszuschließen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn ausgewählt:* Kunden, die zu den ausgewählten Gruppen gehören, erhalten keine Rabatte von diesem Modul, auch wenn ihr Warenkorbwert die Kriterien erfüllt.
    - *Wenn nicht ausgewählt:* Alle Kundengruppen sind für die Rabatte berechtigt.
  - **Empfohlener Wert:** Abhängig von Ihrer Geschäftsstrategie. Wenn Sie spezielle Preise für bestimmte Gruppen haben, könnten Sie diese ausschließen.
  - **Händlerszenario / Beispiel:** Sie haben eine Kundengruppe „Großhandel“, die bereits spezielle Preise erhält. Sie würden diese Gruppe hier auswählen, um eine Stapelung von Rabatten zu vermeiden.
- **Art des Preises**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob der Warenkorbwert für die Rabattberechnung Steuern enthalten oder ausschließen soll.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf „Preis mit Steuer“ eingestellt:* Der Rabatt wird basierend auf dem gesamten Warenkorbwert *einschließlich* Mehrwertsteuer/Steuern berechnet.
    - *Wenn auf „Preis ohne Steuer“ eingestellt:* Der Rabatt wird basierend auf dem gesamten Warenkorbwert *ausschließlich* Mehrwertsteuer/Steuern berechnet.
  - **Empfohlener Wert:** „Preis mit Steuer“ für die meisten B2C-Shops, „Preis ohne Steuer“ für B2B-Shops oder wenn Ihre primäre Preisgestaltung exklusive Steuern ist.
  - **Händlerszenario / Beispiel:** Wenn Ihre Kunden es gewohnt sind, Preise mit Steuer zu sehen, wird die Berechnung des Rabatts basierend auf dem „Preis mit Steuer“ für sie natürlicher und transparenter wirken.
- **Produkte mit Rabatt ausschließen**

  - **Was diese Einstellung bewirkt:** Steuert, ob Produkte, die bereits im Angebot sind oder einen spezifischen Preis haben (z. B. aus einer Katalogregel), zum Warenkorbwert für die Rabattberechnung zählen sollen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Bereits reduzierte Produkte werden bei der Berechnung des Gesamtwerts des Warenkorbs für den gestaffelten Rabatt ignoriert.
    - *Wenn deaktiviert (NEIN):* Alle Produkte im Warenkorb, unabhängig davon, ob sie bereits reduziert sind, tragen zum Warenkorbwert für den gestaffelten Rabatt bei.
  - **Empfohlener Wert:** JA, um „Doppelrabatte“ zu vermeiden und Ihre Margen zu schützen.
  - **Händlerszenario / Beispiel:** Sie haben einen 20 %-Rabatt auf bestimmte T-Shirts. Wenn ein Kunde ein T-Shirt und andere Artikel kauft und diese Einstellung auf JA steht, trägt der Wert des T-Shirts nicht dazu bei, die nächste Warenkorbrabattstufe zu erreichen.
- **Produkte vom Hersteller ausschließen**

  - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, bestimmte Hersteller anzugeben, deren Produkte nicht zum Warenkorbwert beitragen sollen, wenn der gestaffelte Rabatt berechnet wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn ausgewählt:* Produkte der ausgewählten Hersteller werden bei der Berechnung des Gesamtwerts des Warenkorbs für den gestaffelten Rabatt ignoriert.
    - *Wenn nicht ausgewählt:* Alle Produkte, unabhängig vom Hersteller, tragen zum Warenkorbwert bei.
  - **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben spezifische Vereinbarungen oder Produkte mit geringer Marge von bestimmten Herstellern.
  - **Händlerszenario / Beispiel:** Sie verkaufen Produkte einer Premiummarke, die strenge Preisregeln hat und nicht in allgemeine Rabatte einbezogen werden kann. Sie würden diesen Hersteller hier auswählen.
- **Reduzierte Produkte vom Rabattwert ausschließen**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob der *Wert* von Produkten, die bereits reduziert sind, vom *Betrag* des angewendeten Warenkorbrabatts ausgeschlossen werden soll. Dies ist ein subtiler, aber wichtiger Unterschied zu „Produkte mit Rabatt ausschließen“.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Wenn ein Warenkorbrabatt von 5 % angewendet wird und einige Produkte im Warenkorb bereits reduziert sind, gelten die 5 % nur für die nicht reduzierten Artikel.
    - *Wenn deaktiviert (NEIN):* Der 5 %-Warenkorbrabatt gilt für den *gesamten* Warenkorbwert, auch wenn einige Artikel darin bereits reduziert sind.
  - **Empfohlener Wert:** JA, um Margen zu schützen und übermäßige Rabatte auf bereits reduzierte Artikel zu vermeiden.
  - **Händlerszenario / Beispiel:** Ein Kunde hat einen Warenkorb im Wert von 100 €, wobei ein Artikel im Wert von 20 € bereits um 10 % reduziert ist. Wenn ein 5 %-Warenkorbrabatt gilt und diese Einstellung auf JA steht, gelten die 5 % nur für die nicht reduzierten Artikel im Wert von 80 €.
- **Warenkorb mit Gutscheincode ausschließen**

  - **Was diese Einstellung bewirkt:** Verhindert, dass die Warenkorbwert-basierten Rabatte des Moduls angewendet werden, wenn ein Kunde bereits einen separaten Gutscheincode in seinem Warenkorb eingegeben hat.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Wenn ein Kunde einen Gutscheincode verwendet, wird der automatische Warenkorbrabatt des Moduls nicht angewendet, wodurch gestapelte Rabatte vermieden werden.
    - *Wenn deaktiviert (NEIN):* Der Rabatt des Moduls wird auch dann angewendet, wenn ein Gutscheincode vorhanden ist, wodurch Rabatte gestapelt werden können.
  - **Empfohlener Wert:** JA, um übermäßige Rabatte zu vermeiden und die Kontrolle über Ihre Werbeaktionen zu behalten.
  - **Händlerszenario / Beispiel:** Sie führen eine spezielle E-Mail-Kampagne mit einem einzigartigen 10 %-Rabattgutschein durch. Sie möchten, dass Kunden zwischen diesem Gutschein und dem gestaffelten Warenkorbrabatt wählen, nicht beides.
- **Rabattprogramm-Info auf der Warenkorbseite anzeigen**

  - **Was diese Einstellung bewirkt:** Steuert, ob Nachrichten über das Warenkorbrabattprogramm (z. B. „Geben Sie X mehr aus für Y% Rabatt!“) auf der Warenkorbseite angezeigt werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Informative Nachrichten werden auf der Warenkorbseite angezeigt und leiten Kunden zu höheren Ausgaben an.
    - *Wenn deaktiviert (NEIN):* Es werden keine Nachrichten bezüglich der Rabatte dieses Moduls auf der Warenkorbseite angezeigt. Der Rabatt wird weiterhin angewendet, wenn aktiv, aber ohne die Werbebotschaft.
  - **Empfohlener Wert:** JA, da dies ein wichtiges Merkmal zur Förderung eines höheren AOV ist.
  - **Händlerszenario / Beispiel:** Sie möchten Kunden aktiv dazu ermutigen, die nächste Rabattstufe zu erreichen. Wenn Sie dies aktivieren, wird ihnen genau angezeigt, wie viel mehr sie ausgeben müssen.
- **Zusätzliche benutzerdefinierte Inhalte**

  - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, benutzerdefinierten Text, HTML oder sogar Bilder hinzuzufügen, die zusammen mit den Informationen zum Rabattprogramm auf der Warenkorbseite angezeigt werden. Dieser Inhalt kann in verschiedene Sprachen übersetzt werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn Inhalt eingegeben wird:* Ihre benutzerdefinierte Nachricht wird auf der Warenkorbseite angezeigt und verbessert die Werbebotschaft.
    - *Wenn leer gelassen:* Es werden keine zusätzlichen benutzerdefinierten Inhalte angezeigt.
  - **Empfohlener Wert:** Verwenden Sie dies, um einen überzeugenden Call-to-Action hinzuzufügen oder die Vorteile des Rabattprogramms zu erläutern.
  - **Händlerszenario / Beispiel:** Sie könnten hinzufügen „Verpassen Sie keine Ersparnisse! Je mehr Sie kaufen, desto mehr sparen Sie!“ oder einen Link zu Ihren Allgemeinen Geschäftsbedingungen für Rabatte.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### 2.2.1 AdminCdisListController (Back Office > Module > Warenkorbrabatt basierend auf Warenkorbwert > Schaltfläche „Konfigurieren“, dann zum Tab „Rabatte“ oder Ähnlichem navigieren)

Auf diesem Bildschirm definieren und verwalten Sie Ihre tatsächlichen Rabattregeln. Er wird typischerweise nach dem Klicken auf „Konfigurieren“ im Modul und der Navigation zu einem spezifischen Tab oder Link für „Rabatte“ oder „Regeln“ aufgerufen.

- **Bildschirmname & Menüpfad:** Dieser Bildschirm wird normalerweise über einen dedizierten Tab oder Link innerhalb der Hauptkonfigurationsseite des Moduls aufgerufen, oft mit „Rabatte“, „Regeln“ oder „Rabatte verwalten“ beschriftet.
- **Verfügbare Aktionen & Einstellungen:**
  - **Raster- / Verwaltungsansicht:** Sie sehen eine Tabelle mit all Ihren definierten Rabattregeln. Jede Zeile stellt eine Regel mit Spalten wie:
    - **Mindestwarenkorbwert:** Der Schwellenwert, den der Warenkorb erreichen muss.
    - **Rabattart:** Ob es sich um einen Prozentsatz oder einen festen Betrag handelt.
    - **Rabattwert:** Der Prozentsatz (z. B. 5) oder feste Betrag (z. B. 10,00).
    - **Aktiv:** Ob die Regel derzeit aktiviert ist.
    - **Aktionen:** Schaltflächen zum „Bearbeiten“ oder „Löschen“ einzelner Regeln.
  - **Schaltfläche „Neue Regel hinzufügen“:** Eine Schaltfläche (z. B. „Neue Rabattregel hinzufügen“), um eine neue Rabattbedingung zu erstellen. Beim Klicken öffnet sich ein Formular zur Definition einer neuen Regel.
  - **Formular „Regel bearbeiten“:** Beim Hinzufügen oder Bearbeiten einer Regel finden Sie typischerweise Felder für:
    - **Mindestwarenkorbwert:** (z. B. 500) – Der minimale Gesamtwert des Warenkorbs, damit dieser Rabatt angewendet wird.
    - **Rabattart:** (z. B. Prozentsatz, fester Betrag) – Wählen Sie, wie der Rabatt berechnet wird.
    - **Rabattwert:** (z. B. 5 für 5 % oder 10,00 für 10 €) – Der tatsächlich anzuwendende Rabatt.
    - **Aktiv:** (Ja/Nein-Schalter) – Um diese spezifische Regel zu aktivieren oder zu deaktivieren, ohne sie zu löschen.
    - **Priorität:** (z. B. 1, 2, 3) – Wenn mehrere Regeln anwendbar sein könnten (z. B. Warenkorbwert ist 1000 € und Sie haben Regeln für 500 € und 1000 €), bestimmt die Priorität, welche Vorrang hat. Kleinere Zahlen bedeuten normalerweise eine höhere Priorität.
- **Auswirkung von Änderungen:**
  - **Hinzufügen einer Regel:** Eine neue Rabattbedingung wird in Ihrem Shop aktiv und wird automatisch auf Kundenwarenkörbe angewendet, die die Kriterien erfüllen.
  - **Bearbeiten einer Regel:** Ändert eine bestehende Rabattbedingung, indem ihr Schwellenwert, Wert oder Aktivstatus geändert wird.
  - **Löschen einer Regel:** Entfernt eine Rabattbedingung dauerhaft, und sie wird nicht mehr auf Warenkörbe angewendet.
  - **Aktivieren/Deaktivieren:** Schaltet die Verfügbarkeit einer spezifischen Rabattregel um, ohne deren Konfiguration zu entfernen.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Beginnen Sie mit der Planung Ihrer Rabattstufen (z. B. 250 € für 2 %, 500 € für 5 %, 1000 € für 10 %).
  2. Klicken Sie für jede Stufe auf „Neue Rabattregel hinzufügen“.
  3. Geben Sie den „Mindestwarenkorbwert“ ein, wählen Sie „Rabattart“ (normalerweise Prozentsatz) und geben Sie den „Rabattwert“ ein.
  4. Stellen Sie sicher, dass „Aktiv“ auf JA gesetzt ist.
  5. Legen Sie Prioritäten fest, wenn Sie überlappende Bereiche haben (z. B. eine Regel für >500 € und eine weitere für >1000 €; stellen Sie sicher, dass die 1000 €-Regel eine höhere Priorität hat, wenn sie anstelle der 500 €-Regel angewendet werden soll, wenn der Warenkorb über 1000 € liegt). Das Modul handhabt dies typischerweise, indem es den Rabatt mit dem höchsten Wert für die höchste erreichte Stufe anwendet.
  6. Überprüfen Sie Ihre Rabattregeln regelmäßig, insbesondere vor großen Verkäufen oder Werbeaktionen, um sicherzustellen, dass sie Ihrer aktuellen Marketingstrategie entsprechen.

#### 2.2.2 index.php (cartdiscount/controllers/admin/index.php)

Diese Datei ist ein Platzhalter und enthält typischerweise nur eine Sicherheitsanweisung `die()`, um den direkten Zugriff auf das Verzeichnis zu verhindern. Sie stellt keine konfigurierbare Bildschirm- oder Entitätsverwaltungsansicht für den Händler dar.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfigurationsseite** | Programm aktivieren | JA | Hauptschalter für das gesamte Rabattprogramm. |
| | Warenkorbrabattprogramm für ausgewählte Kundengruppen deaktivieren | (Keine ausgewählt) | Schließt ausgewählte Kundengruppen von Rabatten aus. |
| | Art des Preises | Preis mit Steuer | Bestimmt, ob der Warenkorbwert für die Berechnung Steuern enthält oder ausschließt. |
| | Produkte mit Rabatt ausschließen | JA | Verhindert, dass bereits reduzierte Produkte zum Warenkorbwert-Schwellenwert beitragen. |
| | Produkte vom Hersteller ausschließen | (Keine ausgewählt) | Ignoriert Produkte ausgewählter Hersteller bei der Warenkorbwertberechnung. |
| | Reduzierte Produkte vom Rabattwert ausschließen | JA | Stellt sicher, dass der Warenkorbrabatt nur für nicht reduzierte Artikel im Warenkorb gilt. |
| | Warenkorb mit Gutscheincode ausschließen | JA | Verhindert Modulrabatte, wenn ein separater Gutscheincode verwendet wird. |
| | Rabattprogramm-Info auf der Warenkorbseite anzeigen | JA | Zeigt Werbebotschaften auf der Warenkorbseite an. |
| | Zusätzliche benutzerdefinierte Inhalte | (Leer) | Fügt benutzerdefinierten Text/HTML zu den Warenkorbseiten-Rabattinformationen hinzu. |
| **AdminCdisListController (Rabattliste)** | Mindestwarenkorbwert | (Vom Händler definiert) | Der Warenkorb-Gesamtschwellenwert, um einen Rabatt auszulösen. |
| | Rabattart | Prozentsatz | Wie der Rabatt berechnet wird (Prozentsatz oder fester Betrag). |
| | Rabattwert | (Vom Händler definiert) | Der tatsächliche Rabattbetrag (z. B. 5 für 5 %, 10,00 für 10 €). |
| | Aktiv | JA | Aktiviert oder deaktiviert eine spezifische Rabattregel. |
| | Priorität | (Auto/Vom Händler definiert) | Bestimmt, welche Regel angewendet wird, wenn mehrere Schwellenwerte erreicht werden. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Rabatte werden nicht angewendet, obwohl ich Regeln eingerichtet habe. Was ist falsch?**
A:

1.  **„Programm aktivieren“ prüfen:** Stellen Sie sicher, dass der Hauptschalter auf der Konfigurationsseite des Moduls auf JA steht.
2.  **„Aktiv“-Status der einzelnen Regeln prüfen:** Stellen Sie sicher, dass jede Rabattregel, die Sie im AdminCdisListController erstellt haben, ebenfalls auf JA steht.
3.  **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). PrestaShop speichert Modul-Einstellungen oft im Cache.
4.  **Kundengruppen prüfen:** Vergewissern Sie sich, dass die Kundengruppe, mit der Sie testen, nicht unter „Warenkorbrabattprogramm für ausgewählte Kundengruppen deaktivieren“ ausgeschlossen ist.
5.  **Warenkorbwert-Schwellenwert:** Überprüfen Sie nochmals, ob Ihr Warenkorbwert tatsächlich den „Mindestwarenkorbwert“ erreicht, damit der Rabatt ausgelöst wird.

**F: Der Rabatt wird angewendet, aber die Nachricht auf der Warenkorbseite wird nicht angezeigt.**
A:

1.  **„Rabattprogramm-Info auf der Warenkorbseite anzeigen“ prüfen:** Stellen Sie sicher, dass diese Einstellung auf der Hauptkonfigurationsseite des Moduls aktiviert (JA) ist.
2.  **Theme-Kompatibilität:** Ihr benutzerdefiniertes Theme könnte die Standard-Warenkorbanzeige überschreiben. Überprüfen Sie, ob der Hook `displayShoppingCartFooter` in der `shopping-cart.tpl` oder einer entsprechenden Datei Ihres Themes korrekt implementiert ist. Falls nicht, muss ein Entwickler den Hook möglicherweise manuell hinzufügen.
3.  **Cache leeren:** Leeren Sie immer Ihren PrestaShop-Cache, nachdem Sie Konfigurationsänderungen vorgenommen haben.

**F: Der Rabattwert scheint falsch zu sein, oder er wird nicht auf alle Artikel angewendet.**
A:

1.  **„Art des Preises“:** Überprüfen Sie, ob Sie „Preis mit Steuer“ oder „Preis ohne Steuer“ für die Berechnung ausgewählt haben.
2.  **„Produkte mit Rabatt ausschließen“:** Wenn aktiviert, tragen bereits reduzierte Produkte nicht zum Schwellenwert bei.
3.  **„Reduzierte Produkte vom Rabattwert ausschließen“:** Wenn aktiviert, gilt der prozentuale Rabatt nur für nicht reduzierte Artikel im Warenkorb. Überprüfen Sie diese Einstellungen, um sicherzustellen, dass sie Ihrem beabsichtigten Verhalten entsprechen.
4.  **„Warenkorb mit Gutscheincode ausschließen“:** Wenn ein Kunde einen separaten Gutschein angewendet hat und diese Einstellung auf JA steht, wird der Rabatt des Moduls nicht angewendet.

**F: Wie übersetze ich die benutzerdefinierten Inhalte, die ich hinzugefügt habe?**
A:

1.  Gehen Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**.
2.  Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann die Sprache, in die Sie übersetzen möchten.
3.  Suchen Sie das Modul „Warenkorbrabatt basierend auf Warenkorbwert“. Sie sollten Felder sehen, um die „Zusätzlichen benutzerdefinierten Inhalte“ für jede Sprache zu übersetzen.

**F: Ich sehe einen Fehler nach der Aktualisierung von PrestaShop oder einem anderen Modul.**
A:

1.  **Modulversion prüfen:** Stellen Sie sicher, dass Sie die neueste Version des Moduls „Warenkorbrabatt basierend auf Warenkorbwert“ verwenden, die mit Ihrer PrestaShop-Version kompatibel ist. Laden Sie die korrekte ZIP-Datei von MyPresta.eu herunter.
2.  **PHP-Kompatibilität:** Überprüfen Sie, ob die PHP-Version Ihres Servers innerhalb des unterstützten Bereichs des Moduls liegt (PHP 5.6 - 8.5).
3.  **Overrides deaktivieren (für Entwickler):** Wenn Sie einen Konflikt vermuten, deaktivieren Sie vorübergehend Overrides unter **Erweiterte Einstellungen > Leistung** (setzen Sie „Nicht-PrestaShop-Module deaktivieren“ auf JA und leeren Sie dann den Cache). Wenn das Problem behoben ist, handelt es sich wahrscheinlich um einen Override-Konflikt. Aktivieren Sie sie wieder und konsultieren Sie einen Entwickler.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Warenkorbrabatt basierend auf Warenkorbwert“ erweitert die Kernfunktionen von PrestaShop `Cart` und `CartRule` durch Overrides, um Rabatte dynamisch anzuwenden. Es nutzt einen dedizierten Admin Controller (`AdminCdisListController`) zur Verwaltung von Rabattregeln, die in einer benutzerdefinierten Datenbanktabelle gespeichert sind. Die Front-Office-Integration erfolgt hauptsächlich über Hooks, um Informationsmeldungen anzuzeigen und die Rabattanwendung während des Warenkorb- und Checkout-Prozesses sicherzustellen.

### 4.2 Controller (`controllers/`)

- **Front-Office Controller**: Keine explizit im Verzeichnis `controllers/front/` des Moduls definiert. Die Front-Office-Logik für die Rabattanwendung wird über Overrides und Hooks abgewickelt.
- **Back-Office Admin Controller**:

  - `cartdiscount/controllers/admin/AdminCdisList.php`
    - **Klassenname & Elternklasse:** `AdminCdisListController` erweitert `ModuleAdminController`.
    - **Tab-Name und verwaltete Entität:** Verwaltet die Liste und Formulare für `Cdis` (Warenkorbrabatt)-Entitäten. Dieser Controller bietet die Schnittstelle zum Erstellen, Bearbeiten und Löschen der gestaffelten Rabattregeln. Er definiert die Listenansicht (`renderList()`) und die Formularansicht (`renderForm()`) für die Rabattregeln.
  - `cartdiscount/controllers/admin/index.php`
    - **Klassenname & Elternklasse:** N/A (Sicherheitsdatei).
    - **Verantwortlichkeit:** Enthält eine `die('No direct script access allowed');`-Anweisung, um den direkten Zugriff auf das Verzeichnis zu verhindern, eine standardmäßige PrestaShop-Sicherheitspraxis.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul stützt sich stark auf Overrides, um seine Logik in die Kernklassen von PrestaShop zu injizieren.

- `cartdiscount/override/classes/Cart.php`
  - **Originalklasse:** `Cart`
  - **Verantwortlichkeit:** Dieser Override ist entscheidend. Er erweitert die `Cart`-Klasse, um die Berechnung der Warenkorb-Gesamtsummen zu ändern, insbesondere um die dynamischen Rabatte basierend auf den Modulregeln anzuwenden. Er fängt wahrscheinlich Methoden wie `getProducts()`, `getProductsTotal()` oder `getPackageShippingCost()` ab, um Preise anzupassen, bevor sie finalisiert werden. Er enthält auch Logik, um zu bestimmen, ob ein Rabatt basierend auf dem aktuellen Warenkorbwert und den konfigurierten Regeln angewendet werden soll.
- `cartdiscount/override/classes/CartRule.php`
  - **Originalklasse:** `CartRule`
  - **Verantwortlichkeit:** Dieser Override erweitert wahrscheinlich die `CartRule`-Klasse, um dem Modul zu ermöglichen, eigene interne `CartRule`-Objekte dynamisch zu erstellen und zu verwalten. Wenn das Modul einen Rabatt anwendet, geschieht dies oft durch die Erstellung einer temporären oder spezifischen `CartRule`, die den berechneten Rabatt widerspiegelt und dann auf den Warenkorb angewendet wird. Dieser Override gewährleistet Kompatibilität und die korrekte Handhabung dieser dynamisch generierten Regeln.
- `cartdiscount/override/classes/index.php`
  - **Verantwortlichkeit:** Sicherheitsdatei, `die('No direct script access allowed');`.
- `cartdiscount/override/classes/order/index.php`
  - **Verantwortlichkeit:** Sicherheitsdatei, `die('No direct script access allowed');`.
- `cartdiscount/override/classes/order/Order.php`
  - **Originalklasse:** `Order`
  - **Verantwortlichkeit:** Dieser Override stellt sicher, dass die vom Modul angewendeten Rabatte bei der Bestellung korrekt übernommen und gespeichert werden. Er könnte Methoden im Zusammenhang mit der Auftragserstellung oder der Gesamtberechnung ändern, um die angewendeten Warenkorbregeln widerzuspiegeln.

### 4.4 JavaScript-Assets (`views/js/`)

- `cartdiscount/views/admin/js/cdis.js`
  - **Geltungsbereich:** Back-Office.
  - **Verantwortlichkeit:** Dieses Skript verarbeitet wahrscheinlich clientseitige Interaktionen für den `AdminCdisListController`. Dies könnte umfassen:
    - AJAX-Aufrufe zum Speichern/Aktualisieren von Rabattregeln.
    - Formularvalidierung für das Formular „Rabattregel hinzufügen/bearbeiten“.
    - Dynamische UI-Updates oder Interaktionen innerhalb des Rabattregel-Verwaltungsrasters.
    - Potenziell die Handhabung der Felder „Produkte vom Hersteller ausschließen“ oder anderer dynamischer Auswahlfelder.

### 4.5 CSS-Stylesheets (`views/css/`)

- `cartdiscount/views/admin/css/cdis.css`
  - **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
  - **Verantwortlichkeit:** Bietet spezifisches Styling für die `AdminCdisListController`-Oberfläche, um sicherzustellen, dass die Formulare und Listen zur Verwaltung von Rabattregeln gut präsentiert und konsistent mit der PrestaShop-Back-Office-Benutzeroberfläche sind.
  - **Wichtige CSS-Klassenselektoren:** Entwickler können das von `AdminCdisListController` generierte HTML inspizieren, um spezifische Klassen (z. B. `.cdis-form`, `.cdis-list-table`) zu finden, die bei Bedarf für benutzerdefiniertes Admin-Styling überschrieben werden können.
- `cartdiscount/views/css/cartdiscount.css`
  - **Geltungsbereich:** Front-Office-Kunden-Styling.
  - **Verantwortlichkeit:** Gestaltet die Informationsmeldungen, die auf der Warenkorbseite angezeigt werden (z. B. „Geben Sie X mehr aus für Y% Rabatt!“).
  - **Wichtige CSS-Klassenselektoren:** Zielt wahrscheinlich auf Elemente innerhalb der `myDiscount.tpl`-Vorlage ab (z. B. `.cartdiscount-info`, `.cartdiscount-message`, `.cartdiscount-progress`). Entwickler können diese Klassen in der `custom.css` ihres Themes oder einer entsprechenden Datei überschreiben, um sie an das Branding des Shops anzupassen.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

- **Hook-Vorlagen (`views/templates/hook/`)**:
  - `cartdiscount/views/templates/hook/myDiscount.tpl`
    - **Hook:** `displayShoppingCartFooter` (und potenziell andere wie `displayHeader` für JS/CSS-Einbindung).
    - **Visueller Block:** Diese Vorlage ist für das Rendern der dynamischen Nachrichten auf der Warenkorbseite verantwortlich. Sie zeigt Informationen über den aktuellen Warenkorbwert, den angewendeten Rabatt und wie viel mehr der Kunde ausgeben muss, um die nächste Rabattstufe zu erreichen. Sie rendert auch die „Zusätzlichen benutzerdefinierten Inhalte“, falls konfiguriert.
- **Admin-Vorlagen (`views/templates/admin/`)**:
  - Der `AdminCdisListController` verwendet Standard-PrestaShop-Admin-Vorlagen zum Rendern seiner Listen- und Formularansichten, die normalerweise in `_partials` oder `helpers/list/list_header.tpl`, `helpers/form/form.tpl` usw. zu finden sind und Teil des PrestaShop-Kerns sind. Das Modul selbst hat möglicherweise keine benutzerdefinierten `.tpl`-Dateien in `views/templates/admin/`, sondern verlässt sich darauf, dass der Controller Daten an die Kernhelfer übergibt.
- **Front-Office-Vorlagen (`views/templates/front/`)**: Keine explizit definiert.
- `cartdiscount/lib/searchTool/views/scripts.tpl`
  - **Geltungsbereich:** Wahrscheinlich für die Einbindung von JavaScript- oder CSS-Assets für eine Suchwerkzeugkomponente innerhalb der Modulkonfiguration oder einer spezifischen Funktion verwendet. Die genaue Verwendung hängt von der Implementierung des Suchwerkzeugs ab (z. B. zur Auswahl von Herstellern, die ausgeschlossen werden sollen).

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - `ps_cdis`: Diese benutzerdefinierte Tabelle speichert die vom Händler definierten Rabattregeln (Mindestwarenkorbwert, Rabattart, Rabattwert, Aktivstatus, Priorität).
  - `ps_configuration`: Moduleinstellungen wie `CDIS_ACTIVE`, `CDIS_PRICETYPE`, `CDIS_GROUPSNOT`, `CDIS_EXMANUFACTURER`, `CDIS_SHOWINFO_CART`, `CDIS_EXSPECIFIC`, `CDIS_ORDERCOUPON`, `cdis_contents` (für benutzerdefinierte Inhalte) und `mypresta_updates` werden hier gespeichert.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Wird verwendet, um das Front-Office-CSS (`cartdiscount.css`) und potenziell JavaScript des Moduls einzubinden, um sicherzustellen, dass Stile und Skripte für die Warenkorbseite geladen werden. |
| `ActionAdminControllerSetMedia` | Wenn ein Admin Controller initialisiert wird und seine Medien (JS/CSS) gesetzt werden. | Wird verwendet, um das Back-Office-CSS (`cdis.css`) und JavaScript (`cdis.js`) des Moduls für den `AdminCdisListController` einzubinden, um die korrekte Gestaltung und Funktionalität der Admin-Oberfläche zu gewährleisten. |
| `displayShoppingCartFooter` | Am unteren Rand der Warenkorb-Übersichtsseite. | Rendert die `myDiscount.tpl`-Vorlage und zeigt dem Kunden Informationsmeldungen über das Rabattprogramm, aktuelle Einsparungen und die nächsten Rabattstufen an. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Warenkorbrabatt basierend auf Warenkorbwert“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.
