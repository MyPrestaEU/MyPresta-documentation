---
title: "Gutscheincode nach Registrierung – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Gutscheincode nach Registrierung“ von MyPresta.eu."
sidebar:
  label: "Gutscheincode nach Registrierung – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Voucher code after registration auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/voucher-code-after-registration.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/voucher-code-after-registration/)
>
> ---


# Gutscheincode nach Registrierung

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend und auf den meisten Webhosting-Umgebungen vorinstalliert.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf die Schaltfläche „Konfigurieren“ neben dem Modul „Gutscheincode nach Registrierung“. Dies führt Sie zum Hauptkonfigurationsbildschirm, wo Sie festlegen können, wie Ihre neuen Kundengutscheine funktionieren sollen.

Die Konfigurationsseite bietet Ihnen Optionen zur Definition der Eigenschaften des Gutscheins, den neue Kunden erhalten. Diese Einstellungen entsprechen direkt den Standard-PrestaShop-Funktionen für „Warenkorbregeln“ (Gutscheine).

Hier sind die typischen Einstellungen, denen Sie begegnen werden:

- **Beschreibung:**

  - **Was diese Einstellung bewirkt:** Dies ist der interne Name für die Warenkorbregel (Gutschein), die erstellt wird. Sie hilft Ihnen, den Gutschein in Ihrem Back Office zu identifizieren.
  - **Auswirkung einer Änderung dieser Einstellung:** Dieser Name dient nur zu Ihrer Referenz und ist für Kunden nicht sichtbar.
  - **Empfohlener Wert:** Etwas Beschreibendes wie „Neukunden-Registrierungsgutschein“ oder „Willkommensrabatt“.
  - **Händlerszenario / Beispiel:** Wenn Sie mehrere Aktionen durchführen, hilft eine klare Beschreibung wie „Willkommensgutschein – 10% Rabatt“ Ihnen, die Leistung zu verfolgen.
- **Code:**

  - **Was diese Einstellung bewirkt:** Dies definiert das Präfix für die generierten einzigartigen Gutscheincodes. Das Modul hängt jedem neuen Kunden eine eindeutige Zeichenfolge an dieses Präfix an.
  - **Auswirkung einer Änderung dieser Einstellung:** Wenn Sie es auf „WELCOME“ setzen, erhalten Kunden möglicherweise Codes wie „WELCOME12345“ oder „WELCOMEABCDE“. Dies macht die Codes leicht identifizierbar.
  - **Empfohlener Wert:** Ein kurzes, einprägsames Präfix wie „WELCOME“, „NEWCUSTOMER“ oder „MYSTORE“. Lassen Sie es leer für einen vollständig zufälligen Code.
  - **Händlerszenario / Beispiel:** Die Verwendung von „WELCOME“ macht dem Kunden deutlich, dass es sich um ein Willkommensangebot handelt.
- **Hervorheben:**

  - **Was diese Einstellung bewirkt:** Wenn aktiviert, wird dieser Gutschein in der Warenkorbzusammenfassung (falls zutreffend) und auf der Produktseite (falls durch die PrestaShop-Kerneinstellungen konfiguriert) angezeigt.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Existenz des Gutscheins könnte an Stellen, an denen Warenkorbregeln normalerweise beworben werden, subtil angedeutet werden.
    - *Wenn deaktiviert:* Der Gutschein ist dem Kunden nur per E-Mail und über sein Konto bekannt.
  - **Empfohlener Wert:** JA (Aktiviert), da es Kunden subtil an verfügbare Rabatte erinnern kann.
  - **Händlerszenario / Beispiel:** Das Aktivieren kann Kunden dazu ermutigen, den erhaltenen Gutschein zu verwenden, auch wenn sie ihn vergessen haben.
- **Teilweise Nutzung:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob der Gutschein mehrmals verwendet werden kann, wenn sein Wert größer ist als der Gesamtbestellwert.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Wenn ein Kunde einen 50-€-Gutschein hat und einen Artikel für 30 € kauft, verbleibt ein Restbetrag von 20 € auf dem Gutschein für einen zukünftigen Kauf.
    - *Wenn deaktiviert:* Der gesamte Gutscheinwert muss in einer Transaktion verwendet werden, oder der Restbetrag verfällt.
  - **Empfohlener Wert:** NEIN (Deaktiviert) für die meisten Willkommensgutscheine, um einen vollständigen Kauf zu fördern.
  - **Händlerszenario / Beispiel:** Für einen „10% Rabatt“-Gutschein ist diese Einstellung weniger relevant, aber für einen „festen Betrag“-Gutschein (z. B. „10 € Rabatt“) fördert das Deaktivieren der teilweisen Nutzung eine größere Erstbestellung.
- **Priorität:**

  - **Was diese Einstellung bewirkt:** Wenn ein Kunde mehrere Gutscheine hat, bestimmt diese Zahl die Reihenfolge, in der sie angewendet werden. Niedrigere Zahlen bedeuten höhere Priorität.
  - **Auswirkung einer Änderung dieser Einstellung:** Ein Gutschein mit Priorität 1 wird vor einem Gutschein mit Priorität 2 angewendet. Dies ist wichtig, wenn Gutscheine nicht kombiniert werden können.
  - **Empfohlener Wert:** 1 (Höchste Priorität) für Willkommensgutscheine, um sicherzustellen, dass sie zuerst angewendet werden.
  - **Händlerszenario / Beispiel:** Wenn Sie einen allgemeinen „kostenloser Versand“-Gutschein (Priorität 5) und einen „Willkommensrabatt“-Gutschein (Priorität 1) haben, wird der Willkommensrabatt zuerst berechnet.
- **Status:**

  - **Was diese Einstellung bewirkt:** Steuert, ob das Modul aktiv ist und Gutscheine generiert.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Neue Kunden erhalten bei der Registrierung Gutscheine.
    - *Wenn deaktiviert:* Das Modul stoppt die Generierung und den Versand von Gutscheinen.
  - **Empfohlener Wert:** JA (Aktiviert), um die Kernfunktionalität des Moduls zu aktivieren.
  - **Händlerszenario / Beispiel:** Sie könnten es während eines bestimmten Verkaufsereignisses vorübergehend deaktivieren, wenn Sie keine zusätzlichen Registrierungsrabatte anbieten möchten.
- **Rabattart:**

  - **Was diese Einstellung bewirkt:** Definiert, ob der Rabatt ein Prozentsatz, ein fester Betrag oder kostenloser Versand ist.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Prozentsatz:* z. B. „10%“ Rabatt auf die Bestellung.
    - *Betrag:* z. B. „10 €“ Rabatt auf die Bestellung.
    - *Kostenloser Versand:* Erlässt die Versandkosten.
  - **Empfohlener Wert:** Prozentsatz oder Betrag, abhängig von Ihrer Marketingstrategie.
  - **Händlerszenario / Beispiel:** Das Anbieten von „10% Rabatt“ ist üblich für Willkommensrabatte. „5 € Rabatt“ könnte für preisgünstigere Artikel besser sein.
- **Wert:**

  - **Was diese Einstellung bewirkt:** Der tatsächliche Rabattwert, entsprechend der ausgewählten „Rabattart“.
  - **Auswirkung einer Änderung dieser Einstellung:** Wenn „Rabattart“ Prozentsatz und „Wert“ 10 ist, erhalten Kunden 10% Rabatt. Wenn „Rabattart“ Betrag und „Wert“ 10 ist, erhalten sie 10 € Rabatt.
  - **Empfohlener Wert:** Ein Wert, der attraktiv, aber auch profitabel ist, z. B. „10“ für 10% oder „5 €“.
  - **Händlerszenario / Beispiel:** Ein 10%iger Rabatt ist ein guter Ausgangspunkt, um neue Kunden anzulocken.
- **Mindestbetrag:**

  - **Was diese Einstellung bewirkt:** Der Mindestbestellwert (vor Versand), der für die Gültigkeit des Gutscheins erforderlich ist.
  - **Auswirkung einer Änderung dieser Einstellung:** Wenn auf 50 € festgelegt, muss der Kunde eine Bestellung von 50 € oder mehr aufgeben, um den Gutschein zu verwenden.
  - **Empfohlener Wert:** Legen Sie ein angemessenes Minimum fest, um größere Erstbestellungen zu fördern, oder 0, wenn kein Minimum erforderlich ist.
  - **Händlerszenario / Beispiel:** Das Festlegen eines Mindestbetrags von 50 € für einen 10%igen Rabattgutschein stellt sicher, dass Sie bei der ersten Bestellung immer noch einen guten Gewinn erzielen.
- **Kumulativ:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob dieser Gutschein mit anderen Gutscheinen kombiniert werden kann.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden können diesen Willkommensgutschein zusammen mit anderen aktiven Gutscheinen (z. B. einem kostenlosen Versandgutschein) verwenden.
    - *Wenn deaktiviert:* Dieser Gutschein kann nicht verwendet werden, wenn bereits ein anderer Gutschein auf den Warenkorb angewendet wurde.
  - **Empfohlener Wert:** NEIN (Deaktiviert) für die meisten Willkommensgutscheine, um übermäßige Rabatte zu vermeiden.
  - **Händlerszenario / Beispiel:** Sie möchten in der Regel die Stapelung von Rabatten begrenzen, um Ihre Margen zu schützen, daher ist das Deaktivieren der kumulativen Nutzung oft vorzuziehen.
- **Gültig von / Gültig bis:**

  - **Was diese Einstellung bewirkt:** Definiert den Datumsbereich, in dem der Gutschein aktiv ist.
  - **Auswirkung einer Änderung dieser Einstellung:** Der Gutschein ist nur zwischen diesen Daten gültig.
  - **Empfohlener Wert:** Lassen Sie „Gültig von“ als aktuelles Datum. Für „Gültig bis“ sollten Sie ein Ablaufdatum (z. B. 30 Tage nach der Registrierung) festlegen, um Dringlichkeit zu erzeugen, oder es weit in der Zukunft lassen, wenn es immerwährend sein soll.
  - **Händlerszenario / Beispiel:** Das Festlegen von „Gültig bis“ auf 30 Tage in der Zukunft ermutigt Kunden, den Gutschein schnell zu verwenden.
- **Menge:**

  - **Was diese Einstellung bewirkt:** Dies bezieht sich auf die Gesamtzahl der *einzigartigen* Gutscheine, die vom Modul generiert werden können.
  - **Auswirkung einer Änderung dieser Einstellung:** Wenn auf 100 festgelegt, erhalten nur die ersten 100 neuen Registranten einen Gutschein.
  - **Empfohlener Wert:** Eine sehr hohe Zahl (z. B. 999999) oder leer lassen, wenn eine unbegrenzte Anzahl von Gutscheinen für neue Registranten generiert werden soll.
  - **Händlerszenario / Beispiel:** Für ein laufendes Willkommensangebot möchten Sie in der Regel eine unbegrenzte Menge. Wenn Sie eine zeitlich begrenzte Kampagne für die ersten X Registranten durchführen, würden Sie eine bestimmte Zahl festlegen.
- **Menge pro Kunde:**

  - **Was diese Einstellung bewirkt:** Definiert, wie oft ein *einzelner Kunde* diesen spezifischen Gutschein erhalten kann.
  - **Auswirkung einer Änderung dieser Einstellung:** Auf 1 setzen, um sicherzustellen, dass jeder Kunde nur einen Willkommensgutschein bei seiner ersten Registrierung erhält.
  - **Empfohlener Wert:** 1.
  - **Händlerszenario / Beispiel:** Sie möchten, dass jeder neue Kunde einen Willkommensrabatt erhält, nicht mehrere, wenn er sich erneut mit einer anderen E-Mail-Adresse registriert (obwohl PrestaShop dies normalerweise verhindert).

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | **Beschreibung** | „Neukundengutschein“ | Interner Name für den Gutschein im BO. |
| Modulkonfiguration | **Code** | Leer (zufällig) / „WELCOME“ | Präfix für generierte Gutscheincodes. |
| Modulkonfiguration | **Hervorheben** | JA | Gutschein in Warenkorbzusammenfassung/Produktseite anzeigen. |
| Modulkonfiguration | **Teilweise Nutzung** | NEIN | Mehrfache Nutzung zulassen, wenn Wert > Bestellsumme. |
| Modulkonfiguration | **Priorität** | 1 | Anwendungsreihenfolge bei mehreren Gutscheinen. |
| Modulkonfiguration | **Status** | JA | Aktiviert/deaktiviert die Gutscheingenerierung des Moduls. |
| Modulkonfiguration | **Rabattart** | Prozentsatz | Art des Rabatts (%, Betrag, kostenloser Versand). |
| Modulkonfiguration | **Wert** | 10 | Der tatsächliche Rabattwert (z. B. 10 für 10%). |
| Modulkonfiguration | **Mindestbetrag** | 0 | Mindestbestellwert für Gutscheingültigkeit. |
| Modulkonfiguration | **Kumulativ** | NEIN | Kombinieren mit anderen Gutscheinen zulassen. |
| Modulkonfiguration | **Gültig von** | Aktuelles Datum | Startdatum für die Gutscheingültigkeit. |
| Modulkonfiguration | **Gültig bis** | Weit in der Zukunft / 30 Tage | Enddatum für die Gutscheingültigkeit. |
| Modulkonfiguration | **Menge** | 999999 | Gesamtzahl der zu generierenden einzigartigen Gutscheine. |
| Modulkonfiguration | **Menge pro Kunde** | 1 | Wie oft ein einzelner Kunde ihn erhalten kann. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Kunden erhalten die Gutschein-E-Mail nicht. Was soll ich überprüfen?**
A:

1. **Modulstatus:** Stellen Sie sicher, dass die Einstellung „Status“ in der Modulkonfiguration auf JA (Aktiviert) gesetzt ist.
2. **E-Mail-Konfiguration:** Überprüfen Sie Ihre PrestaShop-E-Mail-Einstellungen unter **Erweiterte Einstellungen > E-Mail**. Senden Sie eine Test-E-Mail, um sicherzustellen, dass das E-Mail-System Ihres Shops ordnungsgemäß funktioniert.
3. **Spam-Ordner:** Weisen Sie Kunden an, ihre Spam- oder Junk-Ordner zu überprüfen.
4. **Modulprotokolle:** Falls verfügbar, suchen Sie nach Fehlerprotokollen, die sich auf das Modul oder den E-Mail-Versand beziehen.
5. **Smarty-Cache:** Manchmal kann das Leeren des Smarty-Caches unter **Erweiterte Einstellungen > Leistung** Anzeige- oder Funktionalitätsprobleme beheben.

**F: Der Gutscheincode wird generiert, aber er wird an der Kasse nicht korrekt angewendet.**
A:

1. **Gutscheineinstellungen:** Überprüfen Sie alle Gutscheineinstellungen in der Modulkonfiguration (z. B. „Mindestbetrag“, „Gültig von/bis“, „Kumulativ“). Stellen Sie sicher, dass der Warenkorb des Kunden alle Bedingungen erfüllt.
2. **Code-Eingabe:** Bestätigen Sie, dass der Kunde den Code korrekt im Warenkorb/an der Kasse eingibt.
3. **Produkteinschränkungen:** Stellen Sie sicher, dass keine versteckten Produkt- oder Kategorieeinschränkungen auf die generierte Warenkorbregel angewendet werden (obwohl dieses Modul typischerweise einfache, allgemeine Regeln erstellt).

**F: Kann ich die E-Mail-Vorlage anpassen, die den Gutschein versendet?**
A: Ja, das Modul verwendet das Standard-E-Mail-Vorlagensystem von PrestaShop. Sie können die relevanten E-Mail-Vorlagendateien (normalerweise in `themes/your_theme/mail/en/` oder `mails/en/` für ältere Versionen) finden und anpassen, die ausgelöst werden, wenn eine neue Warenkorbregel erstellt und gesendet wird. Suchen Sie nach Vorlagen, die sich auf `voucher` oder `cart_rule` beziehen.

**F: Was passiert, wenn ein Kunde sich mehrmals mit verschiedenen E-Mail-Adressen registriert?**
A: Das Modul generiert für jede neue Registrierung einen neuen einzigartigen Gutschein. Die Kernfunktionalität von PrestaShop verhindert normalerweise doppelte E-Mail-Registrierungen, aber wenn ein Kunde verschiedene E-Mails verwendet, würde er jedes Mal einen neuen Gutschein erhalten. Die Einstellung „Menge pro Kunde“ bezieht sich auf eine einzelne Kunden-ID, nicht unbedingt auf eindeutige E-Mail-Adressen, wenn diese Kernprüfungen umgangen werden.

**F: Das Modul ist installiert, aber ich sehe keine neuen Menüpunkte im Back Office.**
A: Dieses Modul integriert sich direkt in den bestehenden Bereich „Module > Modul-Manager“ und fügt keine neuen Top-Level-Menüpunkte hinzu. Seine Konfiguration ist zugänglich, indem Sie neben seinem Namen in der Modulliste auf „Konfigurieren“ klicken.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Gutscheincode nach Registrierung“ (`registervoucher`) ist ein Standard-PrestaShop-Modul, das hauptsächlich zur Erweiterung des Hooks `actionCustomerAccountAdd` entwickelt wurde. Es nutzt die Kernfunktionalität der PrestaShop-`CartRule` (Gutschein), um automatisch einen einzigartigen Rabattcode für neue Kundenkonten zu erstellen und zuzuweisen. Die Konfiguration des Moduls wird über die Methode `getContent()` in der Hauptmoduldatei gehandhabt, wobei die Einstellungen in `ps_configuration` gespeichert werden. Es beinhaltet minimale Front-Office-Interaktion und verlässt sich hauptsächlich auf das native E-Mail-System von PrestaShop und die Kundenkontenanzeige für die Gutscheinlieferung.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Logik ist in der Hauptmoduldatei und ihren registrierten Hooks gekapselt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder erweitert `ObjectModel`. Es interagiert direkt mit der PrestaShop-Kernklasse `CartRule`, um Gutscheine zu erstellen und zu verwalten.

### 4.4 JavaScript-Assets (`views/js/`)

- `registervoucher/lib/voucherengine/script.js`
  - **Umfang:** Potenziell Back-Office oder ein generisches Skript, das zur Kompatibilität enthalten ist.
  - **Beschreibung:** Angesichts der Hauptfunktion des Moduls (Backend-Gutscheingenerierung) ist dieses Skript wahrscheinlich ein Dienstprogramm oder ein Kompatibilitätsskript. Es könnte UI-Verbesserungen auf der Konfigurationsseite, Formularvalidierung oder Kompatibilitätskorrekturen für ältere PrestaShop-Versionen behandeln, insbesondere in Bezug auf dynamische Formularelemente oder AJAX-Interaktionen innerhalb der `getContent()`-Methode. Ohne weitere Prüfung ist sein genauer Zweck spekulativ, aber im Allgemeinen auf die Verbesserung der Konfigurationsoberfläche des Moduls oder die Sicherstellung der versionsübergreifenden Kompatibilität für das Admin-Panel bezogen.

### 4.5 CSS-Stylesheets (`views/css/`)

- `registervoucher/css.css`

  - **Umfang:** Wahrscheinlich Styling für das Back-Office-Admin-Formular.
  - **Beschreibung:** Dieses Stylesheet enthält wahrscheinlich benutzerdefinierte Stile für die Konfigurationsseite des Moduls im PrestaShop Back Office. Es könnte Layout, Abstände, Farben oder spezifische Elementdarstellungen anpassen, um sicherzustellen, dass das Konfigurationsformular visuell konsistent ist oder um benutzerdefiniertes Branding anzuwenden.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:** `.registervoucher-config`, `.form-group`, `.control-label`, `.help-block` (spezifisch für den vom Modul generierten HTML-Code).
- `registervoucher/lib/voucherengine/ps16.css`

  - **Umfang:** Styling für das Back-Office-Admin-Formular, speziell für PrestaShop 1.6-Kompatibilität.
  - **Beschreibung:** Dieses Stylesheet ist mit ziemlicher Sicherheit enthalten, um sicherzustellen, dass die Konfigurationsseite des Moduls korrekt und konsistent mit dem PrestaShop 1.6 Back Office-Theme gerendert wird. Es behebt Styling-Unterschiede zwischen PS 1.6 und neueren Versionen und bietet notwendige Überschreibungen oder spezifische Stile für Elemente wie Schaltflächen, Formularfelder und Layout-Container, um ein ordnungsgemäßes Erscheinungsbild zu gewährleisten.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:** Spezifisch für das PS 1.6 Admin-Theme, z. B. `.panel`, `.form-horizontal`, `.btn`.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

Das Moduldossier weist keine benutzerdefinierten `.tpl`-Dateien auf. Dies deutet darauf hin, dass das Konfigurationsformular des Moduls direkt innerhalb der Methode `getContent()` mithilfe der PrestaShop-Hilfsklassen (z. B. `HelperForm`) gerendert wird und jede Front-Office-Anzeige (wie der Gutschein im Kundenkonto) durch Überschreiben von PrestaShop-Kernvorlagen oder durch direktes Einfügen von Inhalten über Hooks ohne dedizierte Modulvorlagen gehandhabt wird. Der E-Mail-Inhalt wird über die nativen E-Mail-Vorlagen von PrestaShop verwaltet.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten Datenbanktabellen.
  - Konfigurationseinstellungen werden in der Tabelle `ps_configuration` gespeichert (z. B. `PS_REGISTERVOUCHER_DESCRIPTION`, `PS_REGISTERVOUCHER_CODE` usw.).
  - Die generierten Gutscheine werden in den PrestaShop-Kerntabellen `ps_cart_rule` und `ps_cart_rule_lang` gespeichert.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionCustomerAccountAdd` | Wird unmittelbar nach erfolgreicher Erstellung eines neuen Kundenkontos ausgeführt. | Dies ist der primäre Hook. Das Modul lauscht auf dieses Ereignis, um den Gutscheingenerierungs- und Zuweisungsprozess für den neu registrierten Kunden auszulösen. |
| `displayHeader` | Wird im `<head>`-Bereich jeder Front-Office-Seite ausgeführt. | Wird oft zum Hinzufügen von CSS/JS verwendet, aber in diesem Modul nicht explizit für die Front-Office-Anzeige. Könnte für die interne Moduleinrichtung oder Kompatibilität sein. |
| `displayRightColumn` | Wird in der rechten Spalte des Front-Office ausgeführt. | Nicht direkt für die Kernfunktionalität der Gutscheinanzeige des Moduls verwendet. |
| `displayLeftColumn` | Wird in der linken Spalte des Front-Office ausgeführt. | Nicht direkt für die Kernfunktionalität der Gutscheinanzeige des Moduls verwendet. |
| `displayFooter` | Wird im Fußbereich jeder Front-Office-Seite ausgeführt. | Nicht direkt für die Kernfunktionalität der Gutscheinanzeige des Moduls verwendet. |
| `displayProductButtons` | Wird auf der Produktseite, in der Nähe des In-den-Warenkorb-Buttons, ausgeführt. | Nicht direkt für die Kernfunktionalität der Gutscheinanzeige des Moduls verwendet. |
| `displayCustomerAccount` | Wird auf der Seite „Mein Konto“ des Kunden ausgeführt. | Dieser Hook ist entscheidend für die Anzeige des generierten Gutscheincodes direkt im Kundenkontobereich, wodurch er leicht zugänglich ist. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul „Gutscheincode nach Registrierung“ wenden Sie sich bitte an Ihr Kundenkonto bei MyPresta.eu. Unser Support-Team steht Ihnen bei technischen Problemen oder Fragen zur Funktionalität des Moduls gerne zur Verfügung.
