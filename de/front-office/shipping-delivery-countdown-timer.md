---
title: "Versand-Liefer-Countdown-Timer - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Versand-Liefer-Countdown-Timer“ von MyPresta.eu."
sidebar:
  label: "Versand-Liefer-Countdown-Timer - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Shipping delivery countdown timer auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/shipping-delivery-countdown-timer.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/shipping-delivery-countdown-timer/)
>
> ---


# Versand-Liefer-Countdown-Timer

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie alle Aspekte des Versand-Liefer-Countdown-Timers steuern.

#### Allgemeine Einstellungen

- **Aktiviert / Deaktiviert (Schalter)**
  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter, um das gesamte Modul in Ihrem Shop ein- oder auszuschalten.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der Countdown-Timer wird in Ihrem Front Office gemäß Ihren anderen Einstellungen angezeigt.
    - *Wenn deaktiviert:* Der Countdown-Timer ist nirgendwo in Ihrem Shop sichtbar.
  - **Empfohlener Wert:** **Aktiviert** (sobald Sie es konfiguriert haben).
  - **Händlerszenario / Beispiel:** Sie richten das Modul zum ersten Mal ein und möchten es vollständig konfigurieren, bevor Sie es live schalten. Sie würden es „Deaktiviert“ lassen, bis es bereit ist, und dann auf „Aktiviert“ umschalten.

#### Anzeige & Design

- **Wo möchten Sie den Timer anzeigen? (Kontrollkästchen)**

  - **Was diese Einstellung bewirkt:** Dies bestimmt die spezifischen Stellen (Hooks) in Ihrem PrestaShop-Theme, an denen der Countdown-Timer angezeigt wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Ankreuzen eines Kästchens (z.B. `displayProductAdditionalInfo`):* Der Timer wird in diesem spezifischen Bereich Ihres Themes angezeigt.
    - *Abhaken eines Kästchens:* Der Timer wird aus diesem spezifischen Bereich entfernt.
  - **Empfohlener Wert:** Beginnen Sie mit `displayProductAdditionalInfo` oder `displayFooterProduct` für die Sichtbarkeit auf der Produktseite. Sie können mit anderen wie `displayNav1` oder `displayReassurance` experimentieren, basierend auf Ihrem Theme und der gewünschten Wirkung.
  - **Händlerszenario / Beispiel:** Sie möchten, dass der Timer auf den Produktseiten gut sichtbar ist. Sie würden `displayProductAdditionalInfo` und `displayFooterProduct` ankreuzen. Wenn Sie ihn auch im Header haben möchten, könnten Sie `displayNav1` ankreuzen.
  - **Verfügbare Optionen:**
    - `displayFooterProduct`
    - `displayReassurance`
    - `displayDeliveryTimer` (Benutzerdefinierter Hook für fortgeschrittene Theme-Integration)
    - `displayProductAdditionalInfo`
    - `displayNav1`
- **Welches Design des Moduls möchten Sie verwenden? (Radio-Buttons)**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Auswahl eines vordefinierten visuellen Stils für Ihren Countdown-Timer. Dies umfasst Farbschemata und das Gesamtlayout.
  - **Auswirkung der Änderung dieser Einstellung:** Das Erscheinungsbild des Countdown-Timers in Ihrem Front Office ändert sich sofort zum ausgewählten Design.
  - **Empfohlener Wert:** Wählen Sie das Design, das am besten zum Branding und den Theme-Farben Ihres Shops passt.
  - **Händlerszenario / Beispiel:** Ihr Shop verwendet viel Blau und Weiß. Sie könnten „Blau 400x48“ oder „Blau 200x100“ auswählen, um sicherzustellen, dass der Timer nahtlos in die Ästhetik Ihrer Website passt.

#### Versandfristen

- **Bestellschlusszeit (Zeitauswahl)**
  - **Was diese Einstellung bewirkt:** Dies ist die tägliche Bestellschlusszeit, bis zu der eine Bestellung aufgegeben werden muss, um für den Versand am aktuellen Tag berechtigt zu sein.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Einstellung auf 14:00 Uhr:* Wenn ein Kunde vor 14:00 Uhr bestellt, zählt der Timer bis 14:00 Uhr herunter. Wenn er nach 14:00 Uhr bestellt, zeigt der Timer den Countdown bis zur Bestellschlusszeit des nächsten verfügbaren Versandtags an.
  - **Empfohlener Wert:** Stellen Sie dies auf Ihre tatsächliche tägliche Versandfrist ein (z.B. 15:00 Uhr für 15:00 Uhr).
  - **Händlerszenario / Beispiel:** Ihr Lagerteam bearbeitet alle Bestellungen, die bis 16:00 Uhr eingehen, für den Versand am selben Tag. Sie würden dies auf `16:00` einstellen.

#### Tägliche Nachrichten & Verfügbarkeit

- **Anzeigen am Sonntag / Montag / Dienstag / Mittwoch / Donnerstag / Freitag / Samstag (Kontrollkästchen)**

  - **Was diese Einstellung bewirkt:** Diese Kontrollkästchen steuern, ob der Countdown-Timer an bestimmten Wochentagen aktiv und angezeigt wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Ankreuzen eines Tages (z.B. „Anzeigen am Sonntag“):* Der Timer ist aktiv und wird sonntags angezeigt.
    - *Abhaken eines Tages:* Der Timer wird an diesem spezifischen Tag nicht angezeigt, und die Nachricht für diesen Tag wird nicht gezeigt.
  - **Empfohlener Wert:** Kreuzen Sie alle Tage an, an denen Sie tatsächlich versenden. Wenn Sie am Wochenende nicht versenden, deaktivieren Sie Samstag und Sonntag.
  - **Händlerszenario / Beispiel:** Ihr Unternehmen ist von Montag bis Freitag tätig. Sie würden Montag bis Freitag ankreuzen und Samstag und Sonntag deaktivieren.
- **Nachricht (Texteingabe für jeden Tag: Sonntag, Montag, Dienstag, Mittwoch, Donnerstag, Freitag, Samstag)**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Anpassung der Nachricht, die zusammen mit dem Countdown-Timer für jeden Wochentag angezeigt wird. Sie können Platzhalter für dynamische Inhalte verwenden.
  - **Auswirkung der Änderung dieser Einstellung:** Der dem Kunden angezeigte Text ändert sich entsprechend Ihrer Eingabe für diesen spezifischen Tag.
  - **Empfohlener Wert:** Erstellen Sie klare, prägnante Nachrichten. Verwenden Sie Platzhalter wie `{time}` für die verbleibende Zeit und `{date}` für das geschätzte Lieferdatum.
  - **Händlerszenario / Beispiel:**
    - *Montagsnachricht:* „Bestellen Sie in den nächsten {time} für Lieferung bis Dienstag!“
    - *Samstagsnachricht (wenn kein Versand):* „Bestellungen, die am Samstag aufgegeben werden, werden am Montag versandt.“

#### Produkt- & Kategorieausschlüsse/-einschlüsse

- **Nur für vorrätige Produkte anzeigen (Schalter)**

  - **Was diese Einstellung bewirkt:** Steuert, ob der Countdown-Timer nur für Produkte angezeigt wird, die derzeit auf Lager sind.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der Timer erscheint nur auf Produktseiten, auf denen das Produkt verfügbaren Lagerbestand hat.
    - *Wenn deaktiviert:* Der Timer erscheint unabhängig vom Lagerstatus (obwohl dies bei nicht vorrätigen Artikeln verwirrend sein könnte).
  - **Empfohlener Wert:** **Aktiviert**. Es macht wenig Sinn, einen Versand-Countdown für einen Artikel anzuzeigen, der nicht sofort versandt werden kann.
  - **Händlerszenario / Beispiel:** Sie möchten vermeiden, schnellen Versand für Artikel zu versprechen, die Sie nicht auf Lager haben. Die Aktivierung dieser Option stellt sicher, dass der Timer nur für verfügbare Produkte angezeigt wird.
- **Modul von ausgewählten Produkten ausschließen / Modulsichtbarkeit für ausgewählte Produkte (Radio-Buttons)**

  - **Was diese Einstellung bewirkt:** Dies ist eine entscheidende Einstellung, um zu definieren, ob die folgenden Produkt-/Kategorie-/Herstellerauswahlen dazu dienen, das Modul *auszuschließen* oder es *einzuschließen* (es nur für die ausgewählten Artikel sichtbar zu machen).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Modul von ausgewählten Produkten ausschließen:* Der Timer wird überall *außer* für die unten ausgewählten Artikel angezeigt.
    - *Modulsichtbarkeit für ausgewählte Produkte:* Der Timer wird *nur* für die unten ausgewählten Artikel angezeigt und nirgendwo sonst.
  - **Empfohlener Wert:** Hängt von Ihrer Strategie ab. Wenn Sie einige spezifische Produkte haben, die den Timer nicht verwenden können, wählen Sie „Ausschließen“. Wenn Sie den Timer nur für wenige ausgewählte Produkte wünschen, wählen Sie „Modulsichtbarkeit“.
  - **Händlerszenario / Beispiel:**
    - *Ausschließen:* Sie verkaufen hauptsächlich kleine Artikel mit schnellem Versand, aber auch einige große Möbelstücke, die länger dauern. Sie würden „Ausschließen“ wählen und dann die Möbelprodukte auswählen.
    - *Sichtbarkeit:* Sie führen eine Sonderaktion für eine bestimmte Produktkategorie durch und möchten, dass der Timer nur dort erscheint. Sie würden „Modulsichtbarkeit“ wählen und diese Kategorie auswählen.
- **Produktausschlüsse/-einschlüsse (Suchen & Auswählen)**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, spezifische Produkte zu suchen und auszuwählen, um den Timer entweder auszuschließen oder nur für diese sichtbar zu machen (basierend auf der obigen Einstellung „Modul von ausgewählten Produkten ausschließen“).
  - **Auswirkung der Änderung dieser Einstellung:** Fügt spezifische Produkte zur Ausschluss-/Einschlussliste hinzu oder entfernt sie.
  - **Empfohlener Wert:** Verwenden Sie dies für eine feingranulare Kontrolle über einzelne Produkte.
  - **Händlerszenario / Beispiel:** Sie haben ein neues Produkt, das vorbestellt ist und erst in Wochen versandt wird. Sie würden es zur Ausschlussliste hinzufügen, um zu verhindern, dass der Countdown angezeigt wird.
- **Kategorieausschlüsse/-einschlüsse (Suchen & Auswählen)**

  - **Was diese Einstellung bewirkt:** Ähnlich wie Produktausschlüsse, aber für ganze Kategorien.
  - **Auswirkung der Änderung dieser Einstellung:** Fügt ganze Kategorien zur Ausschluss-/Einschlussliste hinzu oder entfernt sie.
  - **Empfohlener Wert:** Nützlich, um Regeln auf große Produktgruppen anzuwenden.
  - **Händlerszenario / Beispiel:** Alle Produkte in Ihrer Kategorie „Maßanfertigungen“ haben lange Lieferzeiten. Sie würden diese Kategorie zur Ausschlussliste hinzufügen.
- **Herstellerausschlüsse/-einschlüsse (Suchen & Auswählen)**

  - **Was diese Einstellung bewirkt:** Ähnlich wie Produkt-/Kategorieausschlüsse, aber für Produkte bestimmter Hersteller.
  - **Auswirkung der Änderung dieser Einstellung:** Fügt Hersteller zur Ausschluss-/Einschlussliste hinzu oder entfernt sie.
  - **Empfohlener Wert:** Praktisch, wenn bestimmte Marken unterschiedliche Versandrichtlinien haben.
  - **Händlerszenario / Beispiel:** Einer Ihrer Lieferanten ist für langsamere Lieferungen bekannt. Sie würden dessen Hersteller zur Ausschlussliste hinzufügen.

#### Weitere Einstellungen

- **mypresta\_updates, update\_, updatev\_ (Interne Einstellungen)**
  - **Was diese Einstellung bewirkt:** Dies sind interne Einstellungen, die von MyPresta.eu-Modulen für Update-Prüfungen und Versionsverwaltung verwendet werden. Sie sind nicht für die direkte Interaktion des Händlers vorgesehen.
  - **Auswirkung der Änderung dieser Einstellung:** Eine Änderung dieser Einstellungen könnte die Fähigkeit des Moduls beeinträchtigen, nach Updates zu suchen.
  - **Empfohlener Wert:** Lassen Sie diese unverändert.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Aktiviert | Aktiviert | Hauptschalter für die Funktionalität des Moduls. |
| Modulkonfiguration | Bestellschlusszeit | Ihre tägliche Versandfrist | Definiert die tägliche Zeit, bis zu der eine Bestellung für den Versand am aktuellen Tag aufgegeben werden muss. |
| Modulkonfiguration | Wo möchten Sie den Timer anzeigen? | `displayProductAdditionalInfo`, `displayFooterProduct` | Wählt Theme-Positionen für den Timer aus. |
| Modulkonfiguration | Welches Design des Moduls möchten Sie verwenden? | Passt zu Ihrem Theme | Visueller Stil des Countdown-Timers. |
| Modulkonfiguration | Anzeigen am Sonntag/Montag/…/Samstag | Alle Versandtage ankreuzen | Steuert, an welchen Tagen der Timer aktiv ist. |
| Modulkonfiguration | Nachricht (für jeden Tag) | „Bestellen Sie in den nächsten {time} für Lieferung bis {date}!“ | Anpassbarer Text, der mit dem Timer angezeigt wird. |
| Modulkonfiguration | Nur für vorrätige Produkte anzeigen | Aktiviert | Der Timer erscheint nur für Produkte mit verfügbarem Lagerbestand. |
| Modulkonfiguration | Modul von ausgewählten Produkten ausschließen / Modulsichtbarkeit für ausgewählte Produkte | Abhängig von der Strategie | Definiert, ob Auswahlen zum Ausschluss oder zur Aufnahme dienen. |
| Modulkonfiguration | Produktausschlüsse/-einschlüsse | Leer | Wählen Sie spezifische Produkte zum Ein-/Ausschließen aus. |
| Modulkonfiguration | Kategorieausschlüsse/-einschlüsse | Leer | Wählen Sie spezifische Kategorien zum Ein-/Ausschließen aus. |
| Modulkonfiguration | Herstellerausschlüsse/-einschlüsse | Leer | Wählen Sie spezifische Hersteller zum Ein-/Ausschließen aus. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Der Timer wird in meinem Shop nicht angezeigt, oder er wird an der falschen Stelle angezeigt.**
A1:

- **Modulstatus prüfen:** Stellen Sie zunächst sicher, dass das Modul auf der Konfigurationsseite „Aktiviert“ ist.
- **Hook-Auswahl prüfen:** Vergewissern Sie sich, dass Sie die richtigen Kontrollkästchen unter „Wo möchten Sie den Timer anzeigen?“ ausgewählt haben. Wenn Ihr Theme stark angepasst ist, werden einige Standard-Hooks möglicherweise nicht gerendert, oder Sie müssen einen anderen Hook verwenden.
- **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal speichert PrestaShop alte Modulpositionen im Cache.
- **Theme-Kompatibilität:** Wenn Ihr Theme stark angepasst ist, implementiert es möglicherweise Standard-PrestaShop-Hooks nicht auf die übliche Weise. Möglicherweise müssen Sie Ihren Theme-Entwickler oder einen Webmaster konsultieren, um den Hook `displayDeliveryTimer` manuell in die `.tpl`-Dateien Ihres Themes einzufügen.

**F2: Die Countdown-Nachricht ist falsch, oder die Bestellschlusszeit scheint falsch zu sein.**
A2:

- **„Bestellschlusszeit“ überprüfen:** Überprüfen Sie nochmals, ob die „Bestellschlusszeit“ korrekt auf Ihre tägliche Versand-Cut-off-Stunde eingestellt ist.
- **Tägliche Nachrichten prüfen:** Stellen Sie sicher, dass die „Nachricht“ für den aktuellen Wochentag korrekt konfiguriert ist und Sinn ergibt.
- **Server-Zeitzone:** Stellen Sie sicher, dass die Server-Zeitzone Ihres PrestaShop-Shops korrekt konfiguriert ist. Wenn die Serverzeit falsch ist, ist der Countdown ungenau. Sie können dies unter **Erweiterte Einstellungen > Konfigurationsinformationen** oder bei Ihrem Hosting-Provider überprüfen.

**F3: Der Timer wird für nicht vorrätige Produkte angezeigt.**
A3:

- **Einstellung „Nur für vorrätige Produkte anzeigen“:** Stellen Sie sicher, dass der Schalter „Nur für vorrätige Produkte anzeigen“ in der Modulkonfiguration auf **Aktiviert** steht. Wenn er deaktiviert ist, wird der Timer unabhängig vom Lagerstatus angezeigt.

**F4: Ich möchte die Farben oder Schriftarten des Timers über die voreingestellten Designs hinaus ändern.**
A4:

- Das Modul bietet mehrere vordefinierte Designs. Für eine tiefere Anpassung (z.B. spezifische Schriftarten, genaue Farbcodes, die in den Designs nicht verfügbar sind) benötigen Sie einen Webmaster oder Entwickler. Diese können die CSS-Stile des Moduls überschreiben, indem sie benutzerdefiniertes CSS in das Stylesheet Ihres Themes einfügen. Details zu den CSS-Dateien finden Sie in Abschnitt 7.5.

**F5: Der Timer wird nicht in andere Sprachen übersetzt.**
A5:

- Gehen Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**.
- Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann „Versand-Liefer-Countdown-Timer“ aus der Modul-Dropdown-Liste.
- Sie können dann alle täglichen Nachrichten und andere Modul-Strings in Ihre gewünschten Sprachen übersetzen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul `Shipping delivery countdown timer` (`deliverycountdown`) ist ein Standard-PrestaShop-Modul, das ein MVC-ähnliches Muster im Rahmen des Moduls befolgt. Es erweitert hauptsächlich `Module` und nutzt das Hook-System von PrestaShop, um seine Inhalte und Funktionen in das Front Office zu integrieren. Die Konfiguration wird über die Methode `getContent()` gehandhabt, wobei die Einstellungen in `ps_configuration` gespeichert werden. Die Front-Office-Anzeige basiert auf Smarty-Templates und einer dedizierten JavaScript-Datei für die Countdown-Logik.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine benutzerdefinierten Front-Office- oder Back-Office-Controller. Die gesamte Konfiguration wird innerhalb der `getContent()`-Methode der Hauptmoduldatei gehandhabt. Die Front-Office-Darstellung erfolgt direkt über Hooks und zugehörige Templates.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder `ObjectModel`s im Verzeichnis `classes/`. Alle Daten werden direkt in `ps_configuration` unter Verwendung von Konfigurationsschlüsseln gespeichert.

### 4.4 JavaScript-Assets (`views/js/`)

- **`deliverycountdown/views/js/deliverycountdown.js`**
  - **Umfang:** Front-Office.
  - **Verantwortlichkeit:** Dies ist die zentrale JavaScript-Datei, die für die Countdown-Logik verantwortlich ist.
  - **Details:**
    - Sie initialisiert wahrscheinlich einen Countdown-Timer auf Elementen, die durch spezifische CSS-Klassen oder IDs identifiziert werden.
    - Sie berechnet die verbleibende Zeit bis zur „Bestellschlusszeit“ für den aktuellen Tag oder den nächsten verfügbaren Versandtag.
    - Sie aktualisiert dynamisch die angezeigte Zeit (Stunden, Minuten, Sekunden) im Front-Office-Template.
    - Sie handhabt den Übergang von Nachrichten, wenn die Bestellschlusszeit erreicht ist (z.B. Wechsel von „Bestellen Sie in X Zeit“ zu „Jetzt aufgegebene Bestellungen werden morgen versandt“).
    - Sie kann `setInterval` oder `setTimeout` für Echtzeit-Updates verwenden.
    - Sie liest wahrscheinlich Konfigurationswerte (wie die Bestellschlusszeit, tägliche Nachrichten und aktivierte Tage), die vom Smarty-Template oder Inline-JavaScript übergeben werden.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul enthält eine Basis-CSS-Datei und mehrere Theme-spezifische CSS-Dateien für verschiedene visuelle Designs.

- **`deliverycountdown/views/css/deliverycountdown.css`**

  - **Umfang:** Front-Office.
  - **Verantwortlichkeit:** Enthält die grundlegende strukturelle und Standard-Formatierung für den Countdown-Timer. Dies umfasst grundlegendes Layout, Schriftgrößen und gemeinsame Elemente, die über alle Designs hinweg geteilt werden.
  - **Wichtige Selektoren:** Entwickler können die HTML-Ausgabe des Timers überprüfen, um Klassen wie `.deliverycountdown-container`, `.deliverycountdown-message`, `.deliverycountdown-timer` usw. zu identifizieren, um Stile in der `custom.css` oder `theme.css` ihres Themes zu überschreiben.
- **`deliverycountdown/views/css/deliverycountdown-{color}-{size}.css`** (z.B. `deliverycountdown-black-200x100.css`, `deliverycountdown-blue-400x48.css`)

  - **Umfang:** Front-Office.
  - **Verantwortlichkeit:** Diese Dateien bieten die spezifischen Farbschemata, Hintergrundbilder (falls vorhanden) und Größenanpassungen für die verschiedenen im Back Office ausgewählten Designoptionen. Sie überschreiben oder erweitern typischerweise die in `deliverycountdown.css` definierten Stile.
  - **Wichtige Selektoren:** Diese Dateien zielen auf dieselben Kernselektoren ab, wenden aber spezifische `background-color`, `color`, `width`, `height`, `border` usw. an, um den gewählten visuellen Stil zu erreichen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:

  - **`deliverycountdown/views/hook/displayFooterProduct.tpl`**
    - **Hook:** `displayFooterProduct` (und potenziell andere wie `displayProductAdditionalInfo`, `displayReassurance`, `displayNav1`, `displayDeliveryTimer`, falls konfiguriert).
    - **Zweck:** Dies ist das primäre Template, das für das Rendern der HTML-Struktur des Countdown-Timers und seiner zugehörigen Nachricht im Front Office verantwortlich ist.
    - **Inhalt:**
      - Es enthält die Haupt-`div`-Elemente für den Timer-Container.
      - Es zeigt die dynamische Nachricht (z.B. „Bestellen Sie in den nächsten…“) und die Countdown-Ziffern an.
      - Es übergibt wahrscheinlich notwendige Konfigurationsvariablen (wie die Bestellschlusszeit, tägliche Nachrichten, aktivierte Tage, aktueller Produktlagerstatus, Ausschluss-/Einschlussregeln) an das `deliverycountdown.js`-Skript, entweder über Datenattribute oder Inline-`<script>`-Tags.
      - Es bindet die ausgewählte CSS-Design-Datei und das `deliverycountdown.js`-Skript ein.
- **Admin-Templates (`views/templates/admin/`)**:

  - **`deliverycountdown/views/admin/datepicker.tpl`**
    - **Zweck:** Wahrscheinlich ein wiederverwendbares Template zum Rendern eines Datumsauswahl-Eingabefeldes in der Back-Office-Konfiguration des Moduls. (Obwohl in der aktuellen Konfiguration nicht explizit für Daten verwendet, könnte es eine Bibliothekskomponente sein).
  - **`deliverycountdown/views/admin/selectedExcludedProducts.tpl`**
    - **Zweck:** Rendert die Liste der Produkte, die für den Ausschluss oder die Aufnahme in die Modulkonfiguration ausgewählt wurden. Dies ist Teil der Produkt-/Kategorie-/Hersteller-Auswahloberfläche.
  - **`deliverycountdown/views/admin/selectedProducts.tpl`**
    - **Zweck:** Ähnlich wie `selectedExcludedProducts.tpl`, aber möglicherweise für einen anderen Auswahlkontext (z.B. wenn es separate Einschluss- und Ausschlusslisten gäbe).
  - **`deliverycountdown/views/admin/timepicker.tpl`**
    - **Zweck:** Rendert das Zeitauswahl-Eingabefeld, das zum Festlegen der „Bestellschlusszeit“ in der Back-Office-Konfiguration verwendet wird.
- **Bibliotheks-Templates (`deliverycountdown/lib/searchTool/views/scripts.tpl`)**:

  - **`deliverycountdown/lib/searchTool/views/scripts.tpl`**
    - **Zweck:** Enthält wahrscheinlich JavaScript- oder Smarty-Logik im Zusammenhang mit dem Produkt-/Kategorie-/Hersteller-Such- und Auswahlwerkzeug, das in der Modulkonfiguration verwendet wird. Dieses Skript erleichtert die AJAX-basierte Suche und Anzeige ausgewählter Elemente.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen. Alle Konfigurationseinstellungen werden in der Standard-PrestaShop-Tabelle `ps_configuration` gespeichert.
  - **Wichtige Konfigurationseinträge (Beispiele):**
    - `DC_LAYOUT`: Speichert das ausgewählte Design-Layout (z.B. „black-200x100“).
    - `DC_SUNDAY_MSG`, `DC_MONDAY_MSG`, etc.: Speichert die benutzerdefinierte Nachricht für jeden Tag.
    - `DC_TIME`: Speichert die „Bestellschlusszeit“ (z.B. „16:00“).
    - `DC_EXCL`: Boolean für Ausschlussregel (0 oder 1).
    - `DC_INSTOCK`: Boolean für „Nur für vorrätige Produkte anzeigen“.
    - `dc_exclusions_products`, `dc_exclusions_cat`, `DC_EXCL_MANUF`: JSON- oder kommagetrennte Listen von IDs für ausgeschlossene/eingeschlossene Entitäten.
    - `DC_SUNDAY`, `DC_MONDAY`, etc.: Booleans zum Aktivieren/Deaktivieren des Timers an bestimmten Tagen.
    - `DC_HOOK_displayFooterProduct`, `DC_HOOK_displayReassurance`, etc.: Booleans, die angeben, welche Hooks für die Anzeige aktiviert sind.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Umfang | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- | --- |
| `displayHeader` | Front-Office | Im `<head>`-Bereich jeder Seite. | Wird verwendet, um CSS- und JS-Assets des Moduls global zu laden oder für die allgemeine site-weite Timer-Anzeige. |
| `displayNav1` | Front-Office | Typischerweise in der oberen Navigationsleiste. | Zeigt den Timer im primären Navigationsbereich an. |
| `displayNav2` | Front-Office | Oft in einer sekundären Navigationsleiste oder Utility-Links. | Zeigt den Timer in einem sekundären Navigationsbereich an. |
| `displayTop` | Front-Office | Im Haupt-Header-Bereich, unter `displayNav`. | Zeigt den Timer im Haupt-Header an. |
| `displayProductAdditionalInfo` | Front-Office | Auf der Produktseite, oft in der Nähe des „In den Warenkorb“-Buttons. | Strategische Platzierung für produktspezifische Dringlichkeit. |
| `displayFooterProduct` | Front-Office | Auf der Produktseite, typischerweise unter der Produktbeschreibung oder den Details. | Eine weitere produktspezifische Platzierung für Dringlichkeit. |
| `displayReassurance` | Front-Office | In einem Vertrauensblock (falls das Theme dies unterstützt), oft unter den Produktinformationen. | Integriert den Timer mit anderen vertrauensbildenden Elementen. |
| `displayDeliveryTimer` | Front-Office | Benutzerdefinierter Hook. | Ermöglicht Theme-Entwicklern, den Timer präzise an jeder beliebigen Stelle im Theme zu platzieren. |
| `actionAdminControllerSetMedia` | Back-Office | Wenn ein Admin-Controller seine Medien-Assets lädt. | Wird verwendet, um modulspezifisches CSS/JS für die Back-Office-Konfigurationsseite zu laden (z.B. für das Suchwerkzeug, die Zeitauswahl). |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Versand-Liefer-Countdown-Timer“ besuchen Sie bitte Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
