---
title: "Loyalitätspunkte – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Loyalitätspunkte von MyPresta.eu."
sidebar:
  label: "Loyalitätspunkte – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Loyalty points auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/loyalty-points.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/loyalty-points/)
>
> ---


# Loyalitätspunkte

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise ausreichend für dieses Modul.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Um auf die Konfiguration des Moduls zuzugreifen, gehen Sie im PrestaShop Back Office zu **Module > Modul-Manager**, suchen Sie nach „Loyalitätspunkte“ und klicken Sie auf die Schaltfläche „Konfigurieren“.

Dieser Bildschirm ermöglicht es Ihnen, die Kernregeln Ihres Loyalitätsprogramms zu definieren.

#### **Umrechnungskurs für Loyalitätspunkte**

- **Was diese Einstellung bewirkt:** Diese entscheidende Einstellung definiert, wie viele Loyalitätspunkte ein Kunde für einen bestimmten Geldbetrag, der in Ihrem Shop ausgegeben wird, erhält. Sie ist die Grundlage Ihres Loyalitätsprogramms.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn auf „1 Punkt für jeden ausgegebenen 10 €“ eingestellt:* Ein Kunde, der 50 € ausgibt, erhält 5 Punkte.
  - *Wenn auf „1 Punkt für jeden ausgegebenen 5 €“ eingestellt:* Ein Kunde, der 50 € ausgibt, erhält 10 Punkte.
  - Ein höherer Wert (z.B. 10 €) bedeutet, dass Kunden langsamer Punkte sammeln, während ein niedrigerer Wert (z.B. 1 €) bedeutet, dass sie schneller Punkte sammeln.
- **Empfohlener Wert:** Dies hängt von Ihren Gewinnmargen und dem gewünschten Kundenanreiz ab. Ein gängiger Ausgangspunkt ist „1 Punkt für jeden ausgegebenen 10 €“ oder „1 Punkt für jeden ausgegebenen 5 €“.
- **Händlerszenario / Beispiel:** Wenn Ihr durchschnittlicher Bestellwert 50 € beträgt und Sie möchten, dass Kunden sich schnell belohnt fühlen, könnte „1 Punkt für jeden ausgegebenen 5 €“ besser sein. Wenn Ihre Margen enger sind, könnte „1 Punkt für jeden ausgegebenen 10 €“ nachhaltiger sein.

#### **Wert der Loyalitätspunkte**

- **Was diese Einstellung bewirkt:** Diese Einstellung bestimmt den monetären Wert jedes Loyalitätspunktes, wenn ein Kunde beschließt, diese in einen Rabattgutschein umzuwandeln.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn auf „1 Punkt = 0,10 €“ eingestellt:* Ein Kunde mit 100 Punkten kann einen 10 € Gutschein erhalten.
  - *Wenn auf „1 Punkt = 0,05 €“ eingestellt:* Ein Kunde mit 100 Punkten kann einen 5 € Gutschein erhalten.
  - Ein höherer Wert macht Punkte für den Kunden attraktiver und wertvoller, kostet Ihren Shop jedoch mehr an Rabatten.
- **Empfohlener Wert:** Dieser sollte mit dem „Umrechnungskurs für Loyalitätspunkte“ abgeglichen werden, um sicherzustellen, dass Ihr Programm sowohl für Kunden attraktiv als auch finanziell tragfähig für Ihr Unternehmen ist. Ein übliches Verhältnis ist, dass 10 Punkte (erworben durch Ausgaben von 100 €, wenn der Kurs 1 Punkt pro 10 € beträgt) 1 € wert sind.
- **Händlerszenario / Beispiel:** Wenn Sie 1 Punkt für jeden ausgegebenen 10 € geben und 1 Punkt 0,10 € wert ist, erhält ein Kunde, der 100 € ausgibt, 10 Punkte, die gegen einen 1 € Gutschein eingetauscht werden können. Das bedeutet, er erhält einen Rabatt von 1 % auf seine Einkäufe. Sie könnten dies auf 2 % oder 3 % erhöhen, um wettbewerbsfähiger zu sein.

#### **Mindestpunkte zum Umwandeln**

- **Was diese Einstellung bewirkt:** Dies legt die Mindestanzahl an Loyalitätspunkten fest, die ein Kunde ansammeln muss, bevor er diese in einen Rabattgutschein umwandeln darf.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn auf „50 Punkte“ eingestellt:* Kunden können Punkte erst einlösen, wenn sie mindestens 50 haben.
  - *Wenn auf „10 Punkte“ eingestellt:* Kunden können Punkte viel früher einlösen.
  - Ein höheres Minimum ermutigt Kunden, mehr Einkäufe zu tätigen, um die Schwelle zu erreichen, was potenziell ihren Lifetime Value erhöht. Ein niedrigeres Minimum bietet schnellere Befriedigung.
- **Empfohlener Wert:** Legen Sie einen Wert fest, der Wiederholungskäufe fördert, ohne so hoch zu sein, dass Kunden ihn als unerreichbar empfinden. 50-100 Punkte sind ein guter Startbereich, abhängig von Ihrer Punktsammelrate.
- **Händlerszenario / Beispiel:** Wenn 1 Punkt pro 10 € verdient wird und 50 Punkte benötigt werden, muss ein Kunde 500 € ausgeben, um seinen ersten Gutschein zu erhalten. Dies stellt sicher, dass er ein engagierter Kunde ist, bevor er einen signifikanten Rabatt erhält.

#### **Gutscheingültigkeit (Tage)**

- **Was diese Einstellung bewirkt:** Dies definiert, wie viele Tage ein aus Loyalitätspunkten generierter Rabattgutschein gültig ist.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn auf „30 Tage“ eingestellt:* Der Gutschein läuft 30 Tage nach seiner Generierung ab.
  - *Wenn auf „365 Tage“ eingestellt:* Der Gutschein ist ein ganzes Jahr gültig.
  - Eine kürzere Gültigkeitsdauer ermutigt Kunden, ihren Gutschein schneller zu verwenden, was zu schnelleren Wiederholungskäufen führt. Eine längere Dauer bietet mehr Flexibilität, könnte aber Käufe verzögern.
- **Empfohlener Wert:** 30 bis 90 Tage ist ein üblicher Bereich. Dies erzeugt ein Gefühl der Dringlichkeit, ohne übermäßig restriktiv zu sein.
- **Händlerszenario / Beispiel:** Eine Gültigkeitsdauer von 60 Tagen gibt Kunden genügend Zeit, etwas zu finden, das sie kaufen möchten, ohne dass der Gutschein unbegrenzt ungenutzt bleibt.

#### **Loyalitätsprogramm aktivieren**

- **Was diese Einstellung bewirkt:** Dies ist ein Hauptschalter, um das gesamte Loyalitätspunkteprogramm ein- oder auszuschalten.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Das Loyalitätsprogramm ist aktiv. Kunden sammeln Punkte, sehen Punktinformationen auf Produktseiten und im Warenkorb und können Punkte in ihrem Konto verwalten.
  - *Wenn deaktiviert (NEIN):* Das Loyalitätsprogramm ist inaktiv. Es werden keine Punkte gesammelt, keine Punktinformationen angezeigt und Kunden können keine Punkte einlösen. Bestehende Punkte bleiben erhalten, sind aber unzugänglich, bis das Programm wieder aktiviert wird.
- **Empfohlener Wert:** JA, sobald Sie alle anderen Einstellungen konfiguriert haben.
- **Händlerszenario / Beispiel:** Sie könnten es vorübergehend für Wartungsarbeiten deaktivieren oder wenn Sie eine andere Werbekampagne durchführen, die mit dem Loyalitätsprogramm kollidiert.

#### **Loyalitätspunkte auf der Produktseite anzeigen**

- **Was diese Einstellung bewirkt:** Dies steuert, ob die Informationen über die für ein Produkt gesammelten Loyalitätspunkte auf den einzelnen Produktseiten in Ihrem Shop angezeigt werden.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Kunden sehen auf jeder Produktseite Text wie „Sammeln Sie X Punkte mit diesem Kauf“.
  - *Wenn deaktiviert (NEIN):* Diese Informationen werden nicht auf den Produktseiten angezeigt.
- **Empfohlener Wert:** JA. Die prominente Anzeige dieser Informationen hilft Kunden, den Wert Ihres Loyalitätsprogramms zu verstehen und fördert Käufe.
- **Händlerszenario / Beispiel:** Wenn diese Option aktiviert bleibt, stellen Sie sicher, dass Kunden immer über die Belohnungen informiert sind, die sie verdienen können, was ein entscheidender Faktor für ihren Kauf sein kann.

#### **Loyalitätspunkte im Warenkorb anzeigen**

- **Was diese Einstellung bewirkt:** Dies steuert, ob die insgesamt zu verdienenden Loyalitätspunkte für die aktuelle Bestellung in der Warenkorb-Zusammenfassung angezeigt werden.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Kunden sehen eine Zusammenfassung der Punkte, die sie für den aktuellen Warenkorbinhalt verdienen werden.
  - *Wenn deaktiviert (NEIN):* Diese Informationen werden nicht im Warenkorb angezeigt.
- **Empfohlener Wert:** JA. Dies dient als letzter Anreiz vor dem Checkout und erinnert Kunden an die zukünftigen Vorteile ihres Kaufs.
- **Händlerszenario / Beispiel:** Die Anzeige von Punkten im Warenkorb kann Warenkorbabbrüche reduzieren, indem sie dem Kauf eine weitere Wertschicht hinzufügt, insbesondere wenn der Kunde unentschlossen ist.

#### **Beschreibung des Loyalitätspunkteprogramms**

- **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, eine benutzerdefinierte Beschreibung oder Erklärung Ihres Loyalitätsprogramms bereitzustellen. Dieser Text wird typischerweise im Bereich „Mein Konto“ des Kunden angezeigt, wo er seine Punkte verwaltet.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn mit Text gefüllt:* Kunden sehen Ihre benutzerdefinierte Nachricht, die erklärt, wie das Programm funktioniert, seine Vorteile oder spezifische Regeln.
  - *Wenn leer gelassen:* Es wird keine benutzerdefinierte Beschreibung angezeigt, was Kunden möglicherweise weniger Informationen hinterlässt.
- **Empfohlener Wert:** Geben Sie eine klare, prägnante und ansprechende Beschreibung an. Erklären Sie, wie Punkte gesammelt werden, ihren Wert und wie sie eingelöst werden können.
- **Händlerszenario / Beispiel:** „Sammeln Sie 1 Punkt für jeden ausgegebenen 10 €! Sammeln Sie 50 Punkte und erhalten Sie einen 5 € Gutschein für Ihren nächsten Einkauf. Das ist unsere Art, Ihnen für Ihre Treue zu danken!“

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Umrechnungskurs für Loyalitätspunkte | 1 Punkt für jeden 10 € | Definiert, wie viele Punkte pro ausgegebener Währungseinheit verdient werden. |
| Modulkonfiguration | Wert der Loyalitätspunkte | 1 Punkt = 0,10 € | Definiert den monetären Wert jedes Punktes bei der Umwandlung in einen Gutschein. |
| Modulkonfiguration | Mindestpunkte zum Umwandeln | 50 Punkte | Legt die Mindestpunktzahl fest, die ein Kunde benötigt, bevor er sie gegen einen Gutschein einlösen kann. |
| Modulkonfiguration | Gutscheingültigkeit (Tage) | 60 Tage | Wie lange ein generierter Gutschein gültig ist. |
| Modulkonfiguration | Loyalitätsprogramm aktivieren | JA | Hauptschalter zum Ein-/Ausschalten des gesamten Loyalitätsprogramms. |
| Modulkonfiguration | Loyalitätspunkte auf der Produktseite anzeigen | JA | Zeigt Informationen zum Punktesammeln auf einzelnen Produktseiten an. |
| Modulkonfiguration | Loyalitätspunkte im Warenkorb anzeigen | JA | Zeigt die insgesamt zu verdienenden Punkte in der Warenkorb-Zusammenfassung an. |
| Modulkonfiguration | Beschreibung des Loyalitätspunkteprogramms | Benutzerdefinierter Text | Bietet Kunden eine detaillierte Erklärung des Programms. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Kunden sehen die Loyalitätspunkte-Informationen auf Produktseiten oder im Warenkorb nicht. Was ist falsch?**
A:

1. **„Loyalitätsprogramm aktivieren“ prüfen:** Stellen Sie sicher, dass diese Einstellung in der Modulkonfiguration auf JA gesetzt ist.
2. **Anzeigeeinstellungen prüfen:** Vergewissern Sie sich, dass „Loyalitätspunkte auf der Produktseite anzeigen“ und „Loyalitätspunkte im Warenkorb anzeigen“ beide auf JA gesetzt sind.
3. **Cache leeren:** Gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal erscheinen Änderungen erst nach dem Aktualisieren des Caches.
4. **Theme-Kompatibilität:** Obwohl das Modul auf Kompatibilität ausgelegt ist, können benutzerdefinierte Themes manchmal Standard-Display-Hooks überschreiben. Wenn das Leeren des Caches nicht funktioniert, kontaktieren Sie den MyPresta.eu-Support.

**F: Kunden sammeln Punkte, können diese aber nicht in Gutscheine umwandeln.**
A:

1. **„Mindestpunkte zum Umwandeln“ prüfen:** Stellen Sie sicher, dass der Kunde mindestens die in dieser Einstellung angegebene Punktzahl gesammelt hat. Wenn das Minimum 50 beträgt und er nur 45 hat, wird die Umwandlungsoption nicht angezeigt.
2. **Gutscheingenerierungsprozess:** Leiten Sie Ihre Kunden zu ihrem Bereich „Mein Konto“, dann zum Bereich „Meine Loyalitätspunkte“ (oder ähnlich), wo sie eine Option zum Umwandeln ihrer Punkte in einen Gutschein finden sollten.

**F: Ein Kunde hat einen Gutschein generiert, aber er funktioniert nicht oder ist verschwunden.**
A:

1. **„Gutscheingültigkeit (Tage)“ prüfen:** Der Gutschein könnte abgelaufen sein, wenn der Kunde zu lange gewartet hat, ihn zu verwenden.
2. **Gutscheincode:** Stellen Sie sicher, dass der Kunde den Gutscheincode während des Checkouts korrekt eingibt.
3. **Gutscheinstatus:** Gehen Sie im PrestaShop Back Office zu **Katalog > Rabatte > Warenkorbregeln**. Suchen Sie nach dem generierten Gutscheincode. Überprüfen Sie dessen Gültigkeitsdaten, Mindestbetrag und ob er bereits verwendet wurde.

**F: Kann ich Loyalitätspunkte für einen Kunden manuell hinzufügen oder entfernen?**
A: Die aktuelle Version des Moduls bietet keine direkte Schnittstelle im Back Office, um Loyalitätspunkte von Kunden manuell anzupassen. Punkte werden automatisch basierend auf Bestellungen berechnet. Wenn Sie manuelle Anpassungen vornehmen müssen, müssen Sie möglicherweise eine kundenspezifische Entwicklung in Betracht ziehen oder den MyPresta.eu-Support für erweiterte Optionen kontaktieren.

**F: Die Beschreibung des Loyalitätsprogramms wird in mehreren Sprachen nicht korrekt angezeigt.**
A: Wenn Sie die „Beschreibung des Loyalitätspunkteprogramms“ festlegen, stellen Sie sicher, dass Sie den Sprachwähler oben rechts im Textfeld verwenden, um Übersetzungen für alle in Ihrem Shop aktivierten Sprachen bereitzustellen. Wenn Sie nur Text in einer Sprache eingeben, wird er auch nur in dieser Sprache angezeigt.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Store-Webmaster und technische Agenturen, die den Store warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul `Loyalitätspunkte` (`myprestaloyalty`) folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich die `Module`-Klasse für ihre Kernfunktionalität und Konfiguration nutzt. Es integriert sich über verschiedene Hooks in das Front Office, um Loyalitätsinformationen anzuzeigen, und bietet eine dedizierte Kundenkontoseite für die Punktverwaltung. Das Modul führt keine benutzerdefinierten Datenbanktabellen oder `ObjectModel`-Klassen ein, sondern verlässt sich auf PrestaShop's `Configuration` für Einstellungen und erweitert möglicherweise bestehende Kunden- oder Bestelldaten über Hooks.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `myprestaloyalty/controllers/front/default.php`
    - **Klassenname & Elternklasse**: `MyPrestaLoyaltyDefaultModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit**: Dieser Controller dient wahrscheinlich als Fallback oder als generischer Einstiegspunkt für Front-Office-Aktionen im Zusammenhang mit dem Modul. Er könnte anfängliche Anfragen oder Weiterleitungen bearbeiten, wenn kein spezifischerer Controller gefunden wird. Angesichts des `index.php`-Controllers könnte `default.php` weniger kritisch sein oder einen spezifischen, weniger häufigen Zweck erfüllen.
  - `myprestaloyalty/controllers/front/index.php`
    - **Klassenname & Elternklasse**: `MyPrestaLoyaltyIndexModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit**: Dies ist der primäre Front-Office-Controller für das Modul. Er ist verantwortlich für die Anzeige der Loyalitätspunkte-Informationen des Kunden und die Handhabung der Logik zum Umwandeln von Punkten in Gutscheine. Er ruft wahrscheinlich die aktuellen Punkte des Kunden ab, berechnet potenzielle Gutscheinwerte und verarbeitet die Gutscheingenerierungsanfrage. Er rendert das `loyalty.tpl`-Template.
- **Back-Office-Admin-Controller**: Keine identifiziert. Alle Konfigurationen werden über die `getContent()`-Methode des Hauptmoduls gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Es wurden keine benutzerdefinierten Klassen oder Modelle (`ObjectModel`-Erweiterungen) im bereitgestellten Modulinventar identifiziert. Das Modul verwaltet die Loyalitätspunkte-Logik wahrscheinlich direkt in der Hauptdatei `myprestaloyalty.php` und über PrestaShop's `Configuration` für Einstellungen.

### 4.4 JavaScript-Assets (`views/js/`)

- `myprestaloyalty/views/js/admin_manual_customer_search.js`
  - **Geltungsbereich**: Back-Office.
  - **Beschreibung**: Dieses Skript deutet auf eine Funktionalität zur manuellen Suche von Kunden im Admin-Panel hin. Obwohl keine Admin-Controller explizit aufgeführt wurden, impliziert diese JS-Datei, dass es eine Admin-Oberfläche geben könnte (möglicherweise in eine bestehende PrestaShop-Seite oder ein benutzerdefiniertes Formular innerhalb von `getContent()` integriert), wo ein Administrator nach Kunden suchen kann, möglicherweise um deren Loyalitätspunkte anzuzeigen oder zu verwalten (obwohl eine direkte Punktmodifikation durch die Modulbeschreibung nicht bestätigt wird). Es verwendet wahrscheinlich AJAX, um Kundendaten abzurufen.
- `myprestaloyalty/views/js/myprestaloyalty.js`
  - **Geltungsbereich**: Front-Office.
  - **Beschreibung**: Dies ist das Haupt-Front-Office-JavaScript für das Modul. Es verarbeitet wahrscheinlich dynamische Interaktionen auf der Loyalitätsseite des Kunden (`loyalty.tpl`), wie zum Beispiel:
    - Anzeige aktueller Punkte und potenzieller Gutscheinwerte.
    - Handhabung des Klickereignisses für die Schaltfläche „Punkte in Gutschein umwandeln“.
    - Durchführung von AJAX-Anfragen an den `index.php`-Front-Controller zur Verarbeitung der Gutscheingenerierung.
    - Aktualisierung der Benutzeroberfläche zur Anzeige des neu generierten Gutscheincodes oder von Erfolgs-/Fehlermeldungen.

### 4.5 CSS-Stylesheets (`views/css/`)

- `myprestaloyalty/views/css/myprestaloyalty.css`
  - **Geltungsbereich**: Front-Office (und potenziell einige Back-Office-Elemente, wenn gemeinsame Stile verwendet werden).
  - **Beschreibung**: Dieses Stylesheet bietet die visuelle Gestaltung für die Front-Office-Komponenten des Moduls. Dazu gehören:
    - Die Anzeige von Loyalitätspunkten auf Produktseiten.
    - Die Zusammenfassung der Punkte im Warenkorb.
    - Das Layout und die Gestaltung des Bereichs „Meine Loyalitätspunkte“ im Kundenkonto, einschließlich des Punktestands, der Historie und des Gutscheingenerierungsformulars.
    - Wichtige CSS-Klassenselektoren, die Entwickler in ihrem Theme überschreiben können: Suchen Sie nach Klassen, die mit `myprestaloyalty-` oder ähnlichem beginnen, wie z.B. `.myprestaloyalty-product-points`, `.myprestaloyalty-cart-summary`, `.myprestaloyalty-account-section`, `.myprestaloyalty-voucher-form`, etc.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Admin-Templates (`views/templates/admin/`)**:

  - `myprestaloyalty/views/templates/admin/advert.tpl`
    - **Beschreibung**: Dieses Template wird wahrscheinlich verwendet, um Werbeinhalte oder Anzeigen von MyPresta.eu innerhalb der Konfigurationsseite des Moduls im Back Office anzuzeigen. Es ist eine gängige Praxis für Modulentwickler, solche Elemente einzuschließen.
  - `myprestaloyalty/views/templates/admin/_configure/helpers/form/form.tpl`
    - **Beschreibung**: Dieses Template ist ein Standard-PrestaShop-Helfer-Template, das zum Rendern des Konfigurationsformulars des Moduls verwendet wird. Es ist nicht einzigartig für dieses Modul, sondern ist enthalten, um sicherzustellen, dass die Konfigurationsseite (`getContent()`) korrekt gerendert wird, möglicherweise mit benutzerdefinierten Feldern oder spezifischer Gestaltung.
- **Front-Office-Templates (`views/templates/front/`)**:

  - `myprestaloyalty/views/templates/front/loyalty.tpl`
    - **Beschreibung**: Dies ist das Haupt-Template für die dedizierte Seite „Meine Loyalitätspunkte“ des Kunden, gerendert vom `MyPrestaLoyaltyIndexModuleFrontController`. Es zeigt den aktuellen Punktestand des Kunden, die Historie der gesammelten und eingelösten Punkte und die Schnittstelle zum Umwandeln von Punkten in Rabattgutscheine an.
- **Hook-Templates (`views/templates/hook/`)**:

  - `myprestaloyalty/views/templates/hook/my-account.tpl`
    - **Hook**: `displayCustomerAccount` (oder ähnlich, z.B. `displayMyAccountBlock`).
    - **Beschreibung**: Dieses Template fügt einen Link oder einen Block zur Seite „Mein Konto“ des Kunden hinzu, der ihn zur dedizierten Loyalitätspunkte-Seite des Moduls (`loyalty.tpl`) leitet.
  - `myprestaloyalty/views/templates/hook/product.tpl`
    - **Hook**: `displayProductExtraContent`, `displayProductButtons` oder `displayProductActions` (abhängig von PrestaShop-Version und Theme).
    - **Beschreibung**: Dieses Template zeigt die Informationen darüber an, wie viele Loyalitätspunkte ein Kunde durch den Kauf des spezifischen Produkts auf dessen Produktseite verdienen wird.
  - `myprestaloyalty/views/templates/hook/shopping-cart.tpl`
    - **Hook**: `displayShoppingCartFooter`, `displayCartExtraProductActions` oder `displayReassurance` (abhängig von PrestaShop-Version und Theme).
    - **Beschreibung**: Dieses Template zeigt eine Zusammenfassung der gesamten Loyalitätspunkte an, die der Kunde für die derzeit im Warenkorb befindlichen Artikel verdienen wird.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen. Alle Moduleinstellungen werden in der PrestaShop-Tabelle `ps_configuration` gespeichert, typischerweise mit Schlüsseln, die mit `MYPRESTALOYALTY_` beginnen.

  - Beispiel für Konfigurationsschlüssel: `MYPRESTALOYALTY_EXCHANGE_RATE`, `MYPRESTALOYALTY_POINT_VALUE`, `MYPRESTALOYALTY_MIN_POINTS`, `MYPRESTALOYALTY_VOUCHER_VALIDITY`, `MYPRESTALOYALTY_ENABLED`, `MYPRESTALOYALTY_DISPLAY_PRODUCT`, `MYPRESTALOYALTY_DISPLAY_CART`, `MYPRESTALOYALTY_DESCRIPTION`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Zum Einbinden von CSS- und JS-Assets für das Front-Office. |
| `displayCustomerAccount` | Auf der Seite „Mein Konto“ des Kunden. | Zum Hinzufügen eines Links zum Bereich „Meine Loyalitätspunkte“. |
| `displayProductExtraContent` (oder ähnlich) | Auf der Produktseite, in der Nähe von Produktdetails/Schaltflächen. | Zum Anzeigen der für das spezifische Produkt gesammelten Punkte. |
| `displayShoppingCartFooter` (oder ähnlich) | In der Warenkorb-Zusammenfassung. | Zum Anzeigen der insgesamt für die aktuelle Bestellung gesammelten Punkte. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | Zum Berechnen und Vergeben von Loyalitätspunkten an den Kunden basierend auf dem Bestellwert. |
| `displayLeftColumn` / `displayRightColumn` / `displayFooter` (optional) | In den jeweiligen Spalten-/Fußzeilenbereichen. | Potenziell zur Anzeige eines Schnelllinks oder einer Zusammenfassung des Loyalitätsprogramms, falls konfiguriert. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und dedizierten technischen Support für das Modul „Loyalitätspunkte“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Händlern und Entwicklern bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
