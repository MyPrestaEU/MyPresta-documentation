---
title: "Maximaler Einkaufswert nach Gruppen – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Maximaler Einkaufswert nach Gruppen“ von MyPresta.eu."
sidebar:
  label: "Maximaler Einkaufswert nach Gruppen – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Maximum purchase value by groups auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/maximum-purchase-value-by-groups.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/maximum-purchase-value-by-groups/)
>
> ---


# Maximaler Einkaufswert nach Gruppen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation des Moduls navigieren Sie zu **Module > Modul-Manager** und suchen Sie nach „Maximaler Einkaufswert nach Gruppen“. Klicken Sie auf die Schaltfläche „Konfigurieren“, um auf die Einstellungen zuzugreifen.

Die Konfigurationsseite zeigt eine Liste all Ihrer Kundengruppen an, sodass Sie für jede einen maximalen Einkaufswert festlegen können.

#### **Einstellung: Maximaler Einkaufswert für [Name der Kundengruppe]**

- **Was diese Einstellung bewirkt:** Dieses Eingabefeld ermöglicht es Ihnen, den höchsten Gesamtbestellwert (inklusive oder exklusive Steuern, abhängig von der Einstellung „Steuer auf maximalen Einkaufswert anwenden“), den Kunden einer bestimmten Gruppe tätigen können, zu definieren.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn ein Wert eingegeben wird (z. B. 500):* Kunden dieser Gruppe wird der Abschluss einer Bestellung verwehrt, wenn ihr Warenkorbwert diesen Betrag überschreitet. Eine Warnmeldung erscheint im Warenkorb und beim Checkout.
  - *Wenn leer gelassen oder auf 0 gesetzt:* Es gibt keinen maximalen Einkaufswert für diese spezifische Kundengruppe. Sie können jeden beliebigen Betrag bestellen.
- **Empfohlener Wert:** Dies hängt vollständig von Ihrem Geschäftsmodell und Ihrer Kundensegmentierung ab.
  - Für **Großhandelsgruppen** könnten Sie ein hohes Limit (z. B. 5000) festlegen oder es leer lassen, wenn Sie ihnen vertrauen.
  - Für **Neukundengruppen** könnten Sie ein niedrigeres Limit (z. B. 200) festlegen, um das Risiko zu steuern.
  - Für **Standard-Kundengruppen** könnten Sie es leer lassen, es sei denn, Sie haben einen spezifischen Grund, allgemeine Kunden zu limitieren.
- **Händlerszenario / Beispiel:** Sie haben eine Gruppe „Großhandel Stufe 1“. Sie möchten sicherstellen, dass keine einzelne Bestellung dieser Gruppe 10.000 € ohne vorherige Genehmigung überschreitet. Sie würden `10000` in das Feld neben „Großhandel Stufe 1“ eingeben. Wenn ein Kunde dieser Gruppe versucht, 10.001 € zu bestellen, wird er blockiert.

#### **Einstellung: Steuer auf maximalen Einkaufswert anwenden**

- **Was diese Einstellung bewirkt:** Dieser Schalter bestimmt, ob der maximale Einkaufswert, den Sie für jede Gruppe festlegen, basierend auf dem Warenkorbwert *inklusive* Steuern oder *exklusive* Steuern berechnet werden soll.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Das Modul vergleicht den Warenkorbwert des Kunden *inklusive aller anfallenden Steuern* mit dem von Ihnen definierten Maximalwert. Dies ist im Allgemeinen die Art und Weise, wie Kunden ihre Gesamtkosten wahrnehmen.
  - *Wenn deaktiviert (NEIN):* Das Modul vergleicht den Warenkorbwert des Kunden *exklusive Steuern* mit dem von Ihnen definierten Maximalwert. Dies kann nützlich sein, wenn Ihre interne Buchhaltung oder Großhandelsvereinbarungen auf Werten vor Steuern basieren.
- **Empfohlener Wert:** **JA**. Die meisten Händler und Kunden denken in Bezug auf den Endpreis, einschließlich Steuern. Dies stellt sicher, dass das Limit für den tatsächlichen Betrag gilt, den der Kunde zahlen wird.
- **Händlerszenario / Beispiel:** Sie legen einen Maximalwert von 500 € für eine Gruppe fest.
  - Wenn „Steuer anwenden“ JA ist: Ein Kunde mit einem Warenkorbwert von 450 € (Produkte) + 50 € (Steuer) = 500 € wird zugelassen. Ein Warenkorb von 460 € (Produkte) + 50 € (Steuer) = 510 € wird blockiert.
  - Wenn „Steuer anwenden“ NEIN ist: Ein Kunde mit einem Warenkorbwert von 500 € (Produkte) + 50 € (Steuer) = 550 € wird zugelassen, da der Produktgesamtbetrag genau 500 € beträgt.

#### **Einstellung: Meldung über Einschränkungen anzeigen**

- **Was diese Einstellung bewirkt:** Dieser Schalter steuert, ob die informative Meldung über das Überschreiten des maximalen Einkaufswerts dem Kunden im Front-Office angezeigt wird.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Kunden sehen eine klare, benutzerfreundliche Meldung auf den Warenkorb- und Checkout-Seiten, wenn ihr Bestellwert das Limit für ihre Gruppe überschreitet. Dies hilft ihnen zu verstehen, warum sie nicht fortfahren können.
  - *Wenn deaktiviert (NEIN):* Die Einschränkung wird weiterhin durchgesetzt (Kunden werden am Bestellen gehindert), aber es wird keine explizite Meldung angezeigt. Dies kann zu Verwirrung und einem schlechten Kundenerlebnis führen, da sie nicht wissen, *warum* sie ihre Bestellung nicht abschließen können.
- **Empfohlener Wert:** **JA**. Informieren Sie Ihre Kunden immer klar. Das Ausblenden der Nachricht führt nur zu Frustration und Support-Tickets.
- **Händlerszenario / Beispiel:** Ein Kunde versucht, zu viel zu bestellen. Wenn dies aktiviert ist, sieht er: „Ihre Bestellung überschreitet den maximal zulässigen Wert für Ihre Kundengruppe (500 €). Bitte reduzieren Sie Ihren Warenkorbwert, um fortzufahren.“ Wenn deaktiviert, sehen sie nur einen Fehler oder die Schaltfläche „Zur Kasse gehen“ bleibt ohne Erklärung inaktiv.

#### **Einstellung: Anzuzeigende Nachricht**

- **Was diese Einstellung bewirkt:** Dieses Textfeld ermöglicht es Ihnen, die Nachricht anzupassen, die Kunden sehen, wenn sie den maximalen Einkaufswert ihrer Gruppe überschreiten. Sie können sie spezifischer auf das Branding oder die Richtlinien Ihres Shops abstimmen.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn eine benutzerdefinierte Nachricht eingegeben wird:* Diese Nachricht wird den Kunden anstelle der Standardnachricht des Moduls angezeigt. Sie können HTML für grundlegende Formatierungen verwenden.
  - *Wenn leer gelassen:* Das Modul zeigt eine Standard-, generische Nachricht an (z. B. „Ihre Bestellung überschreitet den maximal zulässigen Wert für Ihre Kundengruppe.“).
- **Empfohlener Wert:** Passen Sie sie so an, dass sie freundlich und hilfreich ist. Fügen Sie Platzhalter wie `{max_value}` und `{currency_sign}` ein, wenn das Modul diese unterstützt (überprüfen Sie das tatsächliche Verhalten des Moduls, da dieses spezifische Modul möglicherweise keine Platzhalter direkt verwendet, sondern den Wert dynamisch einfügt). Eine gute Standardeinstellung ist oft ausreichend.
- **Händlerszenario / Beispiel:** Anstelle einer generischen Nachricht möchten Sie vielleicht sagen: „Sehr geehrter Kunde, Ihr aktueller Bestellwert überschreitet den maximal zulässigen Einkaufswert von {max_value} {currency_sign} für Ihren Kontotyp. Bitte passen Sie Ihren Warenkorb an oder kontaktieren Sie unser Verkaufsteam für größere Bestellungen.“

Denken Sie daran, nach jeder Änderung auf die Schaltfläche **„Speichern“** am unteren Rand der Konfigurationsseite zu klicken.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Maximaler Einkaufswert für [Gruppenname] | Leer / Variiert | Legt die obere Ausgabengrenze für eine bestimmte Kundengruppe fest. Leer bedeutet keine Begrenzung. |
| Modulkonfiguration | Steuer auf maximalen Einkaufswert anwenden | JA | Bestimmt, ob das Limit für den Warenkorbwert mit oder ohne Steuern gilt. Empfohlen: JA (Endpreis). |
| Modulkonfiguration | Meldung über Einschränkungen anzeigen | JA | Steuert, ob Kunden eine Erklärung sehen, wenn sie blockiert werden. Empfohlen: JA (zur Klarheit). |
| Modulkonfiguration | Anzuzeigende Nachricht | Standardnachricht | Passt die Warnmeldung an, die Kunden angezeigt wird. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe ein Limit festgelegt, aber Kunden können immer noch mehr bestellen. Was ist falsch?**
A:

1. **Überprüfen Sie die Kundengruppe:** Stellen Sie sicher, dass der Kunde, mit dem Sie testen, tatsächlich zu der Gruppe gehört, für die Sie das Limit festgelegt haben.
2. **Einstellung „Steuer anwenden“:** Überprüfen Sie nochmals, ob die Einstellung „Steuer auf maximalen Einkaufswert anwenden“ korrekt konfiguriert ist. Wenn Ihr Limit 500 beträgt und es auf „NEIN“ (Steuer ausschließen) eingestellt ist, könnte ein Kunde Produkte im Wert von 500 + Steuer bestellen, was über 500 hinausgeht.
3. **Modul aktiviert:** Stellen Sie sicher, dass das Modul in Ihrem Modul-Manager tatsächlich aktiviert ist.
4. **Cache:** Leeren Sie Ihren PrestaShop-Cache (Erweiterte Einstellungen > Leistung > Cache leeren) und Ihren Browser-Cache.

**F: Die Meldung über die Einschränkung wird nicht angezeigt, aber Kunden werden trotzdem blockiert.**
A: Überprüfen Sie die Einstellung „Meldung über Einschränkungen anzeigen“ in der Modulkonfiguration. Stellen Sie sicher, dass sie auf „JA“ gesetzt ist. Wenn sie auf „NEIN“ gesetzt ist, erzwingt das Modul das Limit stillschweigend, was für Kunden verwirrend sein kann.

**F: Kann ich verschiedene Nachrichten für verschiedene Kundengruppen festlegen?**
A: Nein, das Modul verwendet derzeit eine einzige Einstellung „Anzuzeigende Nachricht“, die für alle Gruppen gilt. Wenn Sie gruppenspezifische Nachrichten benötigen, wäre dies eine kundenspezifische Entwicklung.

**F: Beeinflusst dieses Modul Rabatte oder Versandkosten?**
A: Das Modul bewertet in der Regel den *endgültigen Warenkorbwert* zum Zeitpunkt des Checkouts, der normalerweise Rabatte, Versandkosten und Steuern (abhängig von Ihrer Einstellung „Steuer anwenden“) beinhaltet. Das Limit gilt also für den letztendlichen Betrag, den der Kunde voraussichtlich zahlen wird.

**F: Mein benutzerdefiniertes Theme zeigt die Nachricht nicht korrekt an.**
A: Dies kann passieren, wenn Ihr Theme stark angepasste Warenkorb- oder Checkout-Vorlagen hat.

1. **Smarty-Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung**, setzen Sie „Template-Kompilierung“ auf „Kompilierung erzwingen“ und „Cache“ auf „Nein“, leeren Sie dann den Cache. Testen Sie erneut. Setzen Sie die Einstellungen danach zurück.
2. **CSS-Konflikt:** Das CSS Ihres Themes könnte das Styling des Moduls überschreiben. Möglicherweise benötigen Sie einen Webentwickler, um das Element zu überprüfen und benutzerdefiniertes CSS anzuwenden, um sicherzustellen, dass die Nachricht sichtbar und korrekt gestylt ist.
3. **Hook-Problem:** Stellen Sie sicher, dass Ihr Theme die Standard-PrestaShop-Hooks, in die das Modul seinen Inhalt einfügt (z. B. `displayShoppingCart`, `displayPaymentTop`), korrekt aufruft.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen gedacht, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul `Maximaler Einkaufswert nach Gruppen` (`cgmaxa`) ist ein Standard-PrestaShop-Modul, das das MVC-Muster implementiert. Es arbeitet hauptsächlich, indem es sich in wichtige Front-Office-Ereignisse während des Warenkorb- und Checkout-Prozesses einklinkt, um den aktuellen Warenkorbwert mit gruppenspezifischen Limits zu validieren, die in der Tabelle `ps_configuration` gespeichert sind. Es verwendet einen Front-Controller für AJAX-Anfragen, um dynamisches Feedback zu geben, und eine Hauptmodulklasse für die Konfiguration und Hook-Registrierung.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `cgmaxa/controllers/front/ajax.php`
  - **Klassenname**: `CgmaxaAjaxModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit**: Dieser Controller verarbeitet AJAX-Anfragen vom Front-Office, wahrscheinlich für die Echtzeit-Validierung des Warenkorbwertes, wenn Artikel hinzugefügt/entfernt werden oder während der Checkout-Schritte. Er würde typischerweise Warenkorbdaten empfangen, die Limitprüfung durchführen und eine JSON-Antwort zurückgeben, die angibt, ob das Limit überschritten wurde und die entsprechende Nachricht.
- `cgmaxa/controllers/front/index.php`
  - **Klassenname**: `CgmaxaIndexModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit**: Dieser Controller könnte ein Platzhalter sein oder für spezifisches Routing verwendet werden, das nicht in die Hauptmodul-Verteilung passt. Angesichts seines Namens könnte er potenziell ein Standard-Einstiegspunkt sein oder nicht-AJAX-Front-Office-Interaktionen verarbeiten, wenn das Modul eine dedizierte Seite hätte, obwohl seine primäre Funktion für dieses Modul wahrscheinlich minimal oder für den Fallback ist.

#### Back-Office-Admin-Controller

Dieses Modul scheint keine dedizierten Admin-Controller zu verwenden. Die gesamte Konfiguration wird direkt innerhalb der `getContent()`-Methode des Hauptmoduls gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul scheint keine benutzerdefinierten Klassen oder `ObjectModel`s in einem `classes/`-Verzeichnis zu definieren. Die gesamte Logik ist in der Hauptmoduldatei (`cgmaxa.php`) und ihren Controllern gekapselt. Konfigurationswerte werden direkt in `ps_configuration` gespeichert.

### 4.4 JavaScript-Assets (`views/js/`)

- `cgmaxa/views/js/cgmaxa.js`
  - **Geltungsbereich**: Front-Office.
  - **Details**: Dieses Skript ist für clientseitige Interaktionen verantwortlich. Es bindet sich wahrscheinlich an Ereignisse wie Mengenänderungen im Warenkorb, Hinzufügen/Entfernen von Produkten oder Navigieren durch Checkout-Schritte. Es würde AJAX-Anfragen an `cgmaxa/controllers/front/ajax.php` senden, um den Warenkorbwert in Echtzeit zu validieren. Nach Erhalt einer Antwort würde es dynamisch die Warnmeldung anzeigen (wenn das Limit überschritten wird) und potenziell die Schaltflächen „Zur Kasse gehen“ oder „Zahlung“ deaktivieren, um den Bestellabschluss zu verhindern. Es könnte auch die Nachricht dynamisch mit dem aktuellen Warenkorbwert und dem maximal zulässigen Wert aktualisieren.

### 4.5 CSS-Stylesheets (`views/css/`)

- `cgmaxa/css.css`
  - **Geltungsbereich**: Front-Office.
  - **Details**: Dieses Stylesheet bietet die grundlegende Formatierung für die Warnmeldung, die Kunden angezeigt wird, wenn sie das Kauflimit überschreiten. Es definiert wahrscheinlich Klassen für den Nachrichtencontainer, die Textfarbe, den Hintergrund und möglicherweise Symbole, um die Warnung hervorzuheben. Entwickler können diese Stile in der `custom.css` ihres Themes oder durch die Verwendung spezifischerer Selektoren überschreiben.
- `cgmaxa/views/css/cgmaxa.css`
  - **Geltungsbereich**: Front-Office.
  - **Details**: Ähnlich wie `cgmaxa/css.css` bietet diese Datei Styling für die Front-Office-Elemente. Sie könnte spezifischere oder aktualisierte Stile im Vergleich zu `cgmaxa/css.css` enthalten, oder eine davon könnte eine ältere Datei sein. Entwickler sollten beide überprüfen, um das vollständige angewendete Styling zu verstehen. Wichtige Selektoren würden den Nachrichtencontainer und seinen Inhalt ansprechen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

- `cgmaxa/views/templates/front/displayShoppingCart.tpl`
  - **Hook**: `displayShoppingCart` (und potenziell `displayPaymentTop`, `stepBeforePaymentOPC`, `displaystepBeforePaymentOPC`).
  - **Ausgabe**: Dieses Template ist für das Rendern der Warnmeldung auf der Warenkorbseite und potenziell anderen Checkout-Schritten verantwortlich. Es würde die HTML-Struktur für das Warnfeld enthalten, wobei die benutzerdefinierte Nachricht und der maximal zulässige Wert dynamisch eingefügt werden, wenn das Limit überschritten wird. Es verwendet wahrscheinlich Smarty-Variablen, die von den Hook-Methoden des Moduls übergeben werden, um zu bestimmen, ob die Nachricht angezeigt werden soll und welchen Inhalt sie haben soll.

#### Admin-Templates (`views/templates/admin/`)

- `cgmaxa/admin.tpl`
  - **Geltungsbereich**: Back-Office-Konfiguration.
  - **Ausgabe**: Dieses Template wird von der `getContent()`-Methode des Moduls verwendet, um das Konfigurationsformular im PrestaShop Back Office zu rendern. Es enthält die Eingabefelder für den Maximalwert jeder Kundengruppe, den Schalter „Steuer anwenden“, den Schalter „Meldung anzeigen“ und das Textfeld für die benutzerdefinierte Nachricht. Es iteriert durch die verfügbaren Kundengruppen, um die dynamischen Eingabefelder zu erstellen.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Alle Konfigurationseinstellungen (Maximalwerte pro Gruppe, Steuereinstellung, Nachrichtenanzeige, benutzerdefinierte Nachricht) werden in der Tabelle `ps_configuration` unter Schlüsseln wie `CGMAXA_GROUP_[ID_GROUP]`, `CGMAXA_TAX`, `CGMAXA_DISPLAY_MESSAGE`, `CGMAXA_MESSAGE` gespeichert.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Zum Einbinden notwendiger CSS- und JavaScript-Dateien (`cgmaxa.js`, `cgmaxa.css`) für die Front-Office-Funktionalität und AJAX-Validierung. |
| `displayShoppingCart` | Auf der Warenkorb-Übersichtsseite. | Zum Anzeigen der Warnmeldung, wenn der Warenkorbwert das Limit der Gruppe überschreitet, und potenziell zum Deaktivieren der Schaltfläche „Zur Kasse gehen“. |
| `displayPaymentTop` | Am oberen Rand des Zahlungsauswahlschritts im Checkout-Prozess. | Zum erneuten Validieren des Warenkorbwertes vor der Zahlung und zum Anzeigen der Warnmeldung, die den weiteren Fortschritt blockiert, wenn das Limit überschritten wird. |
| `stepBeforePaymentOPC` | Vor dem Zahlungsschritt im One-Page Checkout (OPC). | Ähnlich wie `displayPaymentTop` stellt dieser Hook sicher, dass die Validierung direkt vor der Auswahl einer Zahlungsmethode durch den Kunden erfolgt, entscheidend für OPC-Abläufe. |
| `displaystepBeforePaymentOPC` | Ein weiterer Hook, der sich auf den Schritt vor der Zahlung im OPC bezieht. | Bietet einen zusätzlichen Punkt für die Validierung und Nachrichtenanzeige in spezifischen OPC-Themes oder -Konfigurationen. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Maximaler Einkaufswert nach Gruppen“ verweisen wir Sie auf Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Konfiguration des Moduls zur Verfügung.
