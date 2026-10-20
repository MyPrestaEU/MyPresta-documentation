---
title: "Sticky Cart Bar PRO - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Sticky Cart Bar PRO von MyPresta.eu."
sidebar:
  label: "Sticky Cart Bar PRO - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Sticky Cart Bar PRO auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/sticky-cart-bar-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/sticky-cart-bar-pro/)
>
> ---


# Sticky Cart Bar PRO

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Das Modul Sticky Cart Bar PRO bietet eine leistungsstarke Reihe von Konfigurationsoptionen, die in mehrere Schlüsselbereiche zur Verwaltung Ihrer Sticky Bars und A/B-Tests unterteilt sind.

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Wenn Sie zum ersten Mal auf „Konfigurieren“ für das Modul klicken, gelangen Sie zu einem Dashboard, das eine Übersicht und Zugriff auf die Hauptbereiche bietet. Diese Seite dient als zentrale Anlaufstelle.

Die Hauptkonfigurationsseite für Sticky Cart Bar PRO ist mit Tabs oder Abschnitten strukturiert, um verschiedene Aspekte des Moduls zu verwalten.

#### Allgemeine Einstellungen / Dashboard-Übersicht

Dieser Abschnitt präsentiert typischerweise eine Zusammenfassung Ihrer aktiven Bars, A/B-Tests und schnelle Links zu den Hauptverwaltungsbildschirmen.

- **Was dieser Abschnitt leistet:** Bietet eine übergeordnete Übersicht über den Status Ihres Moduls und schnelle Navigation zum Erstellen neuer Bars, Verwalten bestehender Bars oder Einrichten von A/B-Tests.
- **Auswirkung der Änderung dieser Einstellung:** Dies ist primär ein Navigations- und Informationsbildschirm. Änderungen hier beinhalten das Klicken auf Links zu anderen dedizierten Verwaltungsbildschirmen.
- **Empfohlener Wert:** Überprüfen Sie dieses Dashboard regelmäßig, um Ihre Sticky Bars und Experimente zu überwachen.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Das Modul verfügt über dedizierte Admin-Controller zur Verwaltung Ihrer Sticky Bars und A/B-Tests, die eine umfassende Oberfläche für Design, Targeting und Analyse bieten.

#### 2.2.1 Sticky Cart Bars Verwaltung (Back Office > Module > Sticky Cart Bar PRO > **Bars verwalten**)

Auf diesem Bildschirm erstellen, bearbeiten und verwalten Sie alle Ihre Sticky Cart Bars.

- **Bildschirmname & Menüpfad:** Sie finden dies unter **Module > Sticky Cart Bar PRO > Bars verwalten** (oder einem ähnlichen Menüpunkt direkt in der Modulkonfiguration).
- **Verfügbare Aktionen & Einstellungen:**
  - **Bar-Auflistungstabelle:** Zeigt alle Ihre erstellten Sticky Bars mit wichtigen Informationen wie Name, Status (aktiv/inaktiv) und zugewiesenen Experimenten an.
    - *Effekt:* Bietet eine organisierte Ansicht aller Ihrer Sticky Bars.
    - *Empfohlen:* Halten Sie die Bar-Namen beschreibend für eine einfache Identifizierung.
  - **Neuen Bar hinzufügen Button:** Startet den Prozess zum Erstellen einer neuen Sticky Bar.
    - *Effekt:* Öffnet das „Layout Studio“, wo Sie Ihre Bar gestalten.
    - *Empfohlen:* Beginnen Sie mit einem klaren Ziel für Ihre neue Bar (z.B. „Produktseite Untere Leiste - Kostenloser Versand“).
  - **Bearbeiten Button (für bestehende Bars):** Ermöglicht Ihnen, eine bestehende Sticky Bar zu ändern.
    - *Effekt:* Öffnet das Layout Studio erneut mit den aktuellen Einstellungen der Bar.
    - *Empfohlen:* Überprüfen und aktualisieren Sie Bars regelmäßig basierend auf Leistung oder Aktionen.
  - **Duplizieren Button:** Erstellt eine exakte Kopie einer bestehenden Bar.
    - *Effekt:* Spart Zeit beim Erstellen ähnlicher Bars oder Variationen für A/B-Tests.
    - *Empfohlen:* Verwenden Sie dies, um schnell eine neue Bar basierend auf einem erfolgreichen Design zu erstellen und dann kleinere Anpassungen vorzunehmen.
  - **Status umschalten (Aktiv/Inaktiv):** Ein Schalter zum Aktivieren oder Deaktivieren einer Bar, ohne sie zu löschen.
    - *Effekt:* Eine aktive Bar erscheint auf Ihrem Front Office gemäß ihren Targeting-Regeln; eine inaktive Bar nicht.
    - *Empfohlen:* Deaktivieren Sie Bars, die saisonal oder nicht mehr relevant sind, anstatt sie zu löschen, falls Sie sie wieder benötigen.
  - **Löschen Button:** Entfernt eine Sticky Bar dauerhaft.
    - *Effekt:* Die Bar wird nicht mehr in Ihrem Shop angezeigt.
    - *Empfohlen:* Löschen Sie nur Bars, von denen Sie sicher sind, dass Sie sie nie wieder verwenden werden.
  - **Layout Studio (beim Hinzufügen/Bearbeiten einer Bar):** Dies ist die zentrale Designoberfläche.
    - **Drag-and-Drop Editor:** Ermöglicht Ihnen, Ihre Sticky Bar visuell zu erstellen, indem Sie Elemente hinzufügen und anordnen.
      - *Effekt:* Sie können das Layout, den Inhalt und das Aussehen Ihrer Bar ohne Programmierung anpassen.
      - *Empfohlen:* Experimentieren Sie mit verschiedenen Elementkombinationen, um herauszufinden, was am besten zu Ihren Produkten und Ihrem Publikum passt.
    - **Elementoptionen:** Jedes Element (z.B. „In den Warenkorb“-Button, „Produktbild“, „Countdown-Timer“, „Benutzerdefinierter Text“) hat eigene Einstellungen für Stil, Inhalt und Verhalten.
      - *Effekt:* Feinabstimmung des Aussehens und der Funktionalität jedes Teils Ihrer Bar.
      - *Empfohlen:* Achten Sie auf Farben, Schriftarten und Größen, um sie an das Branding Ihres Shops anzupassen.
    - **Voreinstellungen:** Wählen Sie aus einer Bibliothek von vorgefertigten Sticky Bar Layouts.
      - *Effekt:* Schneller Start mit einer professionell aussehenden Bar.
      - *Empfohlen:* Verwenden Sie Voreinstellungen als Ausgangspunkt und passen Sie sie dann an Ihre spezifischen Bedürfnisse an.
    - **Targeting-Regeln:** Definieren Sie, *wo* und *wem* die Sticky Bar angezeigt werden soll.
      - *Effekt:* Stellt sicher, dass Ihre Bar nur relevanten Kunden auf bestimmten Seiten angezeigt wird.
      - *Empfohlen:* Zielen Sie auf bestimmte Produktkategorien, Marken oder Kundengruppen ab, um maximale Wirkung zu erzielen. Beispiele:
        - *Anzeigen auf:* Allen Produktseiten, spezifischen Produkt-IDs, spezifischen Kategorien.
        - *Kundengruppen:* Nur eingeloggte Kunden, neue Besucher, spezifische Kundengruppen.
        - *Geografischer Standort:* Nur Kunden aus bestimmten Ländern.
        - *Gerätetyp:* Desktop, Mobil oder beides.
    - **Anzeigeposition:** Wählen Sie, ob die Leiste oben oder unten auf dem Bildschirm erscheinen soll.
      - *Effekt:* Steuert die visuelle Platzierung der Sticky Bar.
      - *Empfohlen:* Untere Leisten sind oft weniger aufdringlich, während obere Leisten prominenter sein können. Testen Sie beides!
    - **Sichtbarkeitseinstellungen:** Steuern Sie, wann die Leiste erscheint (z.B. nach dem Scrollen einer bestimmten Strecke, nach einer Verzögerung).
      - *Effekt:* Verhindert, dass die Leiste zu früh oder zu spät erscheint, und optimiert das Benutzererlebnis.
      - *Empfohlen:* Eine leichte Verzögerung oder ein Scroll-Schwellenwert kann die Leiste weniger aggressiv wirken lassen.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. **Planen:** Entscheiden Sie sich für den Zweck Ihrer neuen Sticky Bar (z.B. ein bestimmtes Produkt bewerben, kostenlosen Versand anbieten, Warenkorbabbruch reduzieren).
  2. **Erstellen:** Verwenden Sie den Button „Neue Bar hinzufügen“ und das Layout Studio, um Ihre Bar zu gestalten. Beginnen Sie mit einer Voreinstellung, wenn Sie unsicher sind.
  3. **Zielen:** Legen Sie die Targeting-Regeln sorgfältig fest, um sicherzustellen, dass die Bar dem richtigen Publikum auf den richtigen Seiten angezeigt wird.
  4. **Aktivieren:** Setzen Sie die Bar auf „Aktiv“, sobald Sie mit ihrem Design und Targeting zufrieden sind.
  5. **Überwachen:** Verwenden Sie das Analyse-Dashboard (siehe nächster Abschnitt), um ihre Leistung zu verfolgen.
  6. **Optimieren:** Basierend auf den Analysen bearbeiten Sie die Bar, um ihre Effektivität zu verbessern.

#### 2.2.2 A/B-Test-Verwaltung (Back Office > Module > Sticky Cart Bar PRO > **A/B-Tests**)

Auf diesem Bildschirm können Sie A/B-Tests für Ihre Sticky Bars einrichten und verwalten, indem Sie verschiedene Versionen vergleichen, um zu sehen, welche am besten funktioniert.

- **Bildschirmname & Menüpfad:** Sie finden dies unter **Module > Sticky Cart Bar PRO > A/B-Tests**.
- **Verfügbare Aktionen & Einstellungen:**
  - **Experiment-Auflistungstabelle:** Zeigt alle Ihre aktiven und abgeschlossenen A/B-Tests an, einschließlich ihres Status, Start-/Enddaten und Leistungsmetriken.
    - *Effekt:* Bietet eine Übersicht über Ihre Testbemühungen.
    - *Empfohlen:* Überprüfen Sie regelmäßig den Status Ihrer Experimente.
  - **Neues Experiment hinzufügen Button:** Startet den Prozess zum Erstellen eines neuen A/B-Tests.
    - *Effekt:* Führt Sie durch die Auswahl einer Kontroll-Bar und einer oder mehrerer Varianten-Bars.
    - *Empfohlen:* Halten Sie mindestens zwei Sticky Bars bereit (eine Kontrolle, eine Variante), bevor Sie ein Experiment starten.
  - **Experimentkonfiguration (beim Hinzufügen/Bearbeiten):**
    - **Name:** Ein beschreibender Name für Ihren A/B-Test.
      - *Effekt:* Hilft Ihnen, das Experiment später zu identifizieren.
      - *Empfohlen:* Verwenden Sie Namen wie „Produktseite Untere Leiste - Button-Farben-Test“ oder „Obere Leiste vs. Untere Leiste“.
    - **Kontroll-Bar:** Die ursprüngliche oder Standard-Sticky Bar, gegen die Sie testen möchten.
      - *Effekt:* Dies ist Ihre Basislinie für den Vergleich.
      - *Empfohlen:* Wählen Sie Ihre derzeit am besten performende Bar oder ein Standarddesign.
    - **Varianten-Bars:** Eine oder mehrere alternative Sticky Bars, die Sie testen möchten.
      - *Effekt:* Dies sind die Versionen mit Änderungen, von denen Sie glauben, dass sie die Leistung verbessern könnten.
      - *Empfohlen:* Konzentrieren Sie sich darauf, pro Variante eine größere Änderung zu testen (z.B. andere Button-Farbe, andere Nachricht, andere Position).
    - **Traffic-Verteilung:** Definieren Sie, welcher Prozentsatz Ihres Publikums jede Bar sieht (Kontrolle vs. Varianten).
      - *Effekt:* Gewährleistet einen fairen Vergleich durch gleichmäßige oder gewünschte Traffic-Verteilung.
      - *Empfohlen:* Beginnen Sie mit einer gleichmäßigen Verteilung (z.B. 50/50 für zwei Bars, 33/33/33 für drei).
    - **Ziel:** Definieren Sie die Metrik, die Sie optimieren möchten (z.B. „In den Warenkorb“-Klicks, Konversionsrate, Umsatz).
      - *Effekt:* Das Modul verfolgt diese Metrik für jede Bar.
      - *Empfohlen:* Wählen Sie ein klares, messbares Ziel, das direkt mit Ihrem Geschäftsziel zusammenhängt.
    - **Targeting-Regeln:** Ähnlich wie beim Bar-Targeting, aber für das Experiment selbst. Stellt sicher, dass der A/B-Test nur für bestimmte Segmente läuft.
      - *Effekt:* Ermöglicht Ihnen, gezielte Experimente durchzuführen, ohne Ihr gesamtes Publikum zu beeinflussen.
      - *Empfohlen:* Wenn Sie eine Bar für eine bestimmte Kategorie testen, wenden Sie dasselbe Targeting auf das Experiment an.
  - **Analysen anzeigen Button:** Greift auf detaillierte Leistungsdaten für ein bestimmtes Experiment zu.
    - *Effekt:* Zeigt an, welche Bar basierend auf Ihrem definierten Ziel am besten abgeschnitten hat.
    - *Empfohlen:* Lassen Sie Experimente lange genug laufen, um statistisch signifikante Daten zu sammeln, bevor Sie Entscheidungen treffen.
  - **Experiment stoppen Button:** Beendet einen aktiven A/B-Test.
    - *Effekt:* Das Modul stoppt die Anzeige der Varianten-Bars, und Sie können wählen, die Gewinner-Bar dauerhaft zu machen.
      *Empfohlen:* Stoppen Sie ein Experiment, sobald ein klarer Gewinner identifiziert ist oder wenn es keine nützlichen Ergebnisse liefert.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. **Hypothese aufstellen:** Identifizieren Sie einen Bereich zur Verbesserung (z.B. „Ich denke, ein roter ‚In den Warenkorb‘-Button wird besser funktionieren als ein grüner“).
  2. **Varianten erstellen:** Duplizieren Sie Ihre bestehende Sticky Bar und nehmen Sie die spezifische Änderung vor, die Sie testen möchten (z.B. Button-Farbe ändern).
  3. **Experiment einrichten:** Gehen Sie zum Bildschirm „A/B-Tests“, klicken Sie auf „Neues Experiment hinzufügen“ und konfigurieren Sie Ihre Kontrolle, Varianten, Traffic und Ziel.
  4. **Starten & Überwachen:** Starten Sie das Experiment und überprüfen Sie regelmäßig das Analyse-Dashboard auf Fortschritte.
  5. **Analysieren & Implementieren:** Sobald das Experiment abgeschlossen ist oder ein klarer Gewinner feststeht, implementieren Sie die Gewinner-Bar als Ihre Standardeinstellung.

#### 2.2.3 Analyse-Dashboard (Back Office > Module > Sticky Cart Bar PRO > **Analysen**)

Dieser Bildschirm bietet detaillierte Leistungsmetriken für Ihre Sticky Bars und A/B-Tests.

- **Bildschirmname & Menüpfad:** Sie finden dies unter **Module > Sticky Cart Bar PRO > Analysen**.
- **Verfügbare Aktionen & Einstellungen:**
  - **Dashboard-Ansicht:** Zeigt Diagramme und Grafiken mit Schlüsselmetriken wie Impressionen, Klicks, Klickraten (CTR) und Konversionen für Ihre Sticky Bars an.
    - *Effekt:* Gibt Ihnen eine klare visuelle Darstellung, wie Ihre Bars performen.
    - *Empfohlen:* Verwenden Sie diese Daten, um zu verstehen, welche Bars effektiv sind und welche verbessert werden müssen.
  - **Filteroptionen:** Filtern Sie Daten nach Datumsbereich, spezifischer Sticky Bar oder Experiment.
    - *Effekt:* Ermöglicht Ihnen, bestimmte Zeiträume zu untersuchen oder die Leistung einzelner Bars zu vergleichen.
    - *Empfohlen:* Vergleichen Sie die Leistung vor und nach einer größeren Änderung oder Aktion.
  - **A/B-Testergebnisse:** Für aktive oder abgeschlossene Experimente zeigt dieser Abschnitt deutlich an, welche Variante besser abschneidet als die Kontrolle, oft mit statistischen Signifikanzindikatoren.
    - *Effekt:* Liefert die notwendigen Beweise, um datengesteuerte Entscheidungen über Ihre Sticky Bar Designs zu treffen.
    - *Empfohlen:* Treffen Sie keine Entscheidungen auf der Grundlage kleiner Stichprobengrößen; warten Sie auf statistische Signifikanz.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. **Regelmäßige Überprüfung:** Überprüfen Sie das Analyse-Dashboard wöchentlich oder monatlich, um allgemeine Leistungstrends zu verstehen.
  2. **Tiefenanalyse:** Wenn eine Bar unterdurchschnittlich performt, verwenden Sie die Filter, um bestimmte Zeiträume zu untersuchen oder sie mit anderen Bars zu vergleichen.
  3. **Entscheidungsfindung:** Verwenden Sie die A/B-Testergebnisse, um souverän Gewinnerdesigns auszuwählen und diese in Ihrem Shop zu implementieren.

#### 2.2.4 AdminStickyCartBarAbController (stickycartbarpro/controllers/admin/AdminStickyCartBarAbController.php)

Dieser Controller verwaltet die A/B-Test-Experimente. Er kümmert sich um die Erstellung, Bearbeitung, Auflistung und Löschung von `stickycartbar_experiment`-Entitäten.

#### 2.2.5 AdminStickyCartBarProController (stickycartbarpro/controllers/admin/AdminStickyCartBarProController.php)

Dieser Controller verwaltet die einzelnen Sticky Cart Bars selbst. Er kümmert sich um die Erstellung, Bearbeitung, Auflistung und Löschung von `stickycartbar_bar`-Entitäten, einschließlich des Zugriffs auf das Layout Studio für das Design.

#### 2.2.6 index.php (stickycartbarpro/controllers/admin/index.php)

Dies ist eine Platzhalterdatei, die typischerweise verwendet wird, um direkte Verzeichnisauflistungen zu verhindern, und stellt selbst keinen konfigurierbaren Bildschirm dar.

### 2.3 Konfigurations-Schnellreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Bars verwalten** | Bar-Name | Beschreibend | Identifiziert die Bar im Back Office. |
|  | Layout Studio | N/A | Drag-and-Drop-Editor für Bar-Inhalt und -Stil. |
|  | Elementoptionen | Variiert | Passt einzelne Elemente an (Buttons, Text, Bilder). |
|  | Voreinstellungen | N/A | Schnellstart-Vorlagen für das Bar-Design. |
|  | Targeting-Regeln | Alle Produktseiten | Definiert, wo und wem die Bar angezeigt wird. |
|  | Anzeigeposition | Unten | Steuert, ob die Bar oben oder unten auf dem Bildschirm ist. |
|  | Sichtbarkeitseinstellungen | Nach Scrollen | Steuert, wann die Bar erscheint (Verzögerung, Scrollen). |
|  | Status (Aktiv/Inaktiv) | Inaktiv (anfänglich) | Aktiviert/deaktiviert die Bar-Anzeige im Front Office. |
| **A/B-Tests** | Experiment-Name | Beschreibend | Identifiziert den A/B-Test. |
|  | Kontroll-Bar | Bestehende Bar | Die Basis-Bar für den Vergleich. |
|  | Varianten-Bars | Neue/Geänderte Bar(s) | Die alternativen Versionen, die getestet werden. |
|  | Traffic-Verteilung | Gleichmäßig aufgeteilt | Wie das Publikum zwischen den Bars aufgeteilt wird. |
|  | Ziel | In den Warenkorb-Klicks | Die zu optimierende Metrik (z.B. Klicks, Konversionen). |
|  | Targeting-Regeln | Alle Produktseiten | Definiert, wo das Experiment läuft. |
|  | Status (Aktiv/Gestoppt) | Aktiv | Steuert, ob das Experiment läuft. |
| **Analysen** | Datumsbereichsfilter | Letzte 30 Tage | Filtert Leistungsdaten nach Zeit. |
|  | Bar/Experiment-Filter | Alle | Filtert Daten für spezifische Bars oder Tests. |
|  | Metriken-Anzeige | Impressionen, Klicks, CTR | Zeigt Leistungsdaten für Bars/Experimente an. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Sticky Bar wird auf meinen Produktseiten nicht angezeigt. Was sollte ich überprüfen?**
**A1:**

- **Ist die Bar „Aktiv“?** Gehen Sie zu **Module > Sticky Cart Bar PRO > Bars verwalten** und stellen Sie sicher, dass der Schalter für Ihre Bar auf „Aktiv“ steht.
- **Targeting-Regeln überprüfen:** Bearbeiten Sie Ihre Bar und überprüfen Sie die „Targeting-Regeln“. Stellen Sie sicher, dass sie so eingestellt ist, dass sie auf den richtigen Seiten (z.B. „Alle Produktseiten“ oder bestimmte Kategorien/Produkte) und für die richtigen Kundengruppen angezeigt wird.
- **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal verhindert der PrestaShop-Cache, dass neue Moduländerungen sofort erscheinen.
- **Modulposition:** Stellen Sie sicher, dass das Modul korrekt eingehängt ist. Obwohl das Modul dies normalerweise selbst verwaltet, wird es nicht angezeigt, wenn Sie es manuell ausgehängt haben. Überprüfen Sie **Design > Positionen** und suchen Sie nach „Sticky Cart Bar PRO“, um sicherzustellen, dass es in `displayHeader` oder `displayFooter` eingehängt ist (abhängig von der Position Ihrer Bar).

**F2: Die Sticky Bar sieht seltsam aus oder passt nicht zum Design meines Themes.**
**A2:**

- **Layout Studio Styling:** Gehen Sie zu **Module > Sticky Cart Bar PRO > Bars verwalten**, bearbeiten Sie Ihre Bar und verwenden Sie die Styling-Optionen des Layout Studios. Sie können Farben, Schriftarten, Größen, Abstände und mehr für jedes Element und die Bar selbst anpassen.
- **Theme-Konflikte:** Manchmal kann das CSS Ihres benutzerdefinierten Themes das Styling des Moduls überschreiben. Wenn grundlegende Styling-Optionen im Layout Studio das Problem nicht beheben, benötigen Sie möglicherweise einen Webmaster, um das CSS zu überprüfen (siehe Entwicklerbereich).
- **Modulkompatibilität:** Stellen Sie sicher, dass Sie die richtige Modulversion für Ihre PrestaShop-Version heruntergeladen haben.

**F3: Wie kann ich den Text in meiner Sticky Bar in andere Sprachen übersetzen?**
**A3:**

- **Modulübersetzungen:** Für statische Texte innerhalb des Moduls (wie Button-Beschriftungen, wenn nicht angepasst), gehen Sie zu **International > Übersetzungen**. Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme, wählen Sie „Sticky Cart Bar PRO“ und dann die Sprache, in die Sie übersetzen möchten.
- **Benutzerdefinierte Textelemente:** Wenn Sie benutzerdefinierte Textelemente mit dem Layout Studio hinzugefügt haben, müssen Sie die Bar für jede Sprache bearbeiten. Beim Bearbeiten der Bar sollten Sie eine Option sehen, um die Sprachen für Texteingaben zu wechseln, sodass Sie Übersetzungen direkt im Layout Studio eingeben können.

**F4: Mein A/B-Test zeigt keine klaren Ergebnisse oder scheint festzustecken.**
**A4:**

- **Dauer & Traffic:** A/B-Tests benötigen ausreichend Zeit und Traffic, um statistisch signifikante Daten zu sammeln. Stellen Sie sicher, dass Ihr Experiment lange genug gelaufen ist (mindestens ein paar Wochen) und genügend Besucher erhalten hat, um Schlussfolgerungen ziehen zu können.
- **Klares Ziel:** Überprüfen Sie nochmals, ob Ihr A/B-Test ein klar definiertes „Ziel“ hat (z.B. „In den Warenkorb“-Klicks). Ohne ein Ziel kann das Modul den Erfolg nicht messen.
- **Keine größeren Shop-Änderungen:** Vermeiden Sie es, während eines laufenden A/B-Tests größere Änderungen an Ihrem Shop vorzunehmen (z.B. neues Theme, große Aktionen), da dies die Ergebnisse verfälschen kann.

**F5: Kann ich mehrere Sticky Bars gleichzeitig aktiv haben?**
**A5:** Ja, Sie können mehrere Sticky Bars erstellen und aktivieren. Sie müssen jedoch ihre **Targeting-Regeln** sorgfältig konfigurieren, um Konflikte zu vermeiden. Zum Beispiel könnten Sie eine Bar für „Alle Produktseiten“ unten und eine andere spezifische Bar für „Kategorie X Produkte“ oben haben. Das Modul priorisiert Bars basierend auf ihrer Spezifität und internen Logik, aber es ist Best Practice, sicherzustellen, dass sich Ihre Targeting-Regeln nicht so überschneiden, dass zwei Bars versuchen, an derselben Position auf derselben Seite angezeigt zu werden.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul Sticky Cart Bar PRO folgt einer robusten PrestaShop MVC (Model-View-Controller)-Architektur und nutzt `ObjectModel` für die Datenpersistenz sowie `ModuleFrontController`/`AdminController` für die Anfragenbearbeitung. Es verwendet ein ausgeklügeltes System für den Layout-Aufbau, A/B-Tests und Analysen, mit dedizierten Klassen für Konfiguration, Styling, Targeting und Experimentauflösung. Das Modul verwendet einen modularen Ansatz, der die Verantwortlichkeiten in verschiedene Klassen aufteilt, um eine bessere Wartbarkeit und Erweiterbarkeit zu gewährleisten. Die Front-Office-Darstellung erfolgt hauptsächlich über Hooks, mit AJAX für dynamische Interaktionen.

### 4.2 Controller (`controllers/`)

#### Front-Office Controller

- `controllers/front/ajax.php`
  - **Klassenname:** `StickyCartBarProAjaxModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Bearbeitet alle AJAX-Anfragen von der Front-Office Sticky Bar. Dies beinhaltet:
    - Verfolgung von Impressionen und Klicks für Analysen.
    - Dynamische Aktualisierung von Warenkorbinformationen (z.B. Hinzufügen von Produkten, Ändern von Mengen).
    - Auflösung, welche Sticky Bar Variante für A/B-Tests angezeigt werden soll.
    - Abrufen von Produktdaten für Variantenwähler oder Cross-Selling-Vorschläge.
    - Gibt JSON-Antworten zurück.
- `controllers/front/index.php`
  - **Klassenname:** `StickyCartBarProIndexModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Ein Platzhalter-Front-Controller. Typischerweise könnte er für eine Standard-Modulseite verwendet werden, aber in diesem Modul wird die Front-Office-Darstellung hauptsächlich über Hooks und AJAX abgewickelt. Er könnte als Fallback oder Basis für zukünftige Funktionen dienen.

#### Back-Office Admin Controller

- `controllers/admin/AdminStickyCartBarAbController.php`
  - **Klassenname:** `AdminStickyCartBarAbController` (erweitert `AdminController`)
  - **Tab-Name:** A/B-Tests (innerhalb des Hauptmenüs des Moduls)
  - **Verwaltete Entität:** `StickyCartBarExperiment` (zugeordnet zur Tabelle `ps_stickycartbar_experiment`).
  - **Verantwortlichkeit:** Verwaltet die CRUD-Operationen für A/B-Test-Experimente. Dies beinhaltet:
    - Auflistung aller Experimente in einer `HelperList`.
    - Bereitstellung eines `HelperForm` zum Erstellen und Bearbeiten von Experimentdetails (Name, Kontroll-Bar, Varianten-Bars, Traffic-Verteilung, Ziel, Targeting-Regeln).
    - Handhabung der Experimentaktivierung/-deaktivierung und der Ergebnisansicht.
- `controllers/admin/AdminStickyCartBarProController.php`
  - **Klassenname:** `AdminStickyCartBarProController` (erweitert `AdminController`)
  - **Tab-Name:** Bars verwalten (innerhalb des Hauptmenüs des Moduls)
  - **Verwaltete Entität:** `StickyCartBarLayout` (zugeordnet zur Tabelle `ps_stickycartbar_bar`).
  - **Verantwortlichkeit:** Verwaltet die CRUD-Operationen für einzelne Sticky Cart Bars. Dieser Controller integriert sich mit dem „Layout Studio“ für das visuelle Design.
    - Auflistung aller Sticky Bars in einer `HelperList`.
    - Bereitstellung der Oberfläche für das Drag-and-Drop Layout Studio, einschließlich Elementkonfiguration, Styling und Targeting-Regeln.
    - Handhabung des Speicherns und Ladens von Bar-Konfigurationen, einschließlich HTML-Struktur, CSS und JavaScript-Einstellungen.
- `controllers/admin/index.php`
  - **Klassenname:** N/A (Platzhalterdatei)
  - **Verantwortlichkeit:** Verhindert direkte Verzeichnisauflistung aus Sicherheitsgründen.

### 4.3 Kernklassen & Modelle (`classes/`)

- `classes/index.php`: Platzhalterdatei zur Verhinderung von Verzeichnisauflistungen.
- `classes/ScbpCompatibility.php`: Handhabt Kompatibilitätsschichten für verschiedene PrestaShop-Versionen (z.B. `Context`-Unterschiede, spezifische Hilfsmethoden).
- `classes/StickyCartBarAdminUi.php`: Dienstprogrammklasse zum Generieren gängiger UI-Elemente oder zur Handhabung spezifischer UI-Logik im Admin-Panel.
- `classes/StickyCartBarAnalytics.php`: Verwaltet die Sammlung, Speicherung und den Abruf von Analysedaten für Sticky Bars und A/B-Tests (Impressionen, Klicks, Konversionen).
- `classes/StickyCartBarConfig.php`: Verwaltet modulspezifische Konfigurationseinstellungen, die in `ps_configuration` gespeichert sind (z.B. globale Modulaktivierung/-deaktivierung, Standardeinstellungen).
- `classes/StickyCartBarElementStyles.php`: Verwaltet die Styling-Eigenschaften und die Generierung von CSS für einzelne Elemente innerhalb einer Sticky Bar.
- `classes/StickyCartBarExperiment.php`
  - **Erweitert:** `ObjectModel`
  - **Datenbanktabelle:** `ps_stickycartbar_experiment`
  - **`$definition`-Felder:** `id_stickycartbar_experiment`, `name`, `id_control_bar`, `id_variant_bars` (JSON), `traffic_distribution` (JSON), `goal`, `targeting_rules` (JSON), `active`, `date_add`, `date_upd`.
  - **Wichtige öffentliche Methoden:** CRUD-Operationen, Methoden zum Abrufen von Kontroll-/Varianten-Bars, Berechnen von Experimentergebnissen.
- `classes/StickyCartBarExperimentMatcher.php`: Bestimmt, ob die Targeting-Regeln eines bestimmten Experiments mit dem aktuellen Kontext (Kunde, Seite, Gerät) übereinstimmen.
- `classes/StickyCartBarExperimentResolver.php`: Bestimmt anhand einer Reihe aktiver Experimente, welche Sticky Bar (Kontrolle oder Variante) dem aktuellen Besucher basierend auf Traffic-Verteilung und Experimentregeln angezeigt werden soll.
- `classes/StickyCartBarExperimentRule.php`: Repräsentiert eine einzelne Targeting-Regel innerhalb eines Experiments.
- `classes/StickyCartBarExperimentVariant.php`: Repräsentiert eine Varianten-Sticky Bar innerhalb eines A/B-Tests.
- `classes/StickyCartBarLayout.php`
  - **Erweitert:** `ObjectModel`
  - **Datenbanktabelle:** `ps_stickycartbar_bar`
  - **`$definition`-Felder:** `id_stickycartbar_bar`, `name`, `content` (JSON für Elemente, Stile, Einstellungen), `targeting_rules` (JSON), `position`, `active`, `date_add`, `date_upd`.
  - **Wichtige öffentliche Methoden:** CRUD-Operationen, Methoden zum Rendern der Bar, Abrufen ihrer Elemente, Anwenden von Stilen.
- `classes/StickyCartBarLayoutInstances.php`: Verwaltet Instanzen von Sticky Bar Layouts, potenziell für Caching oder Laufzeitzugriff.
- `classes/StickyCartBarLayoutPreset.php`: Repräsentiert ein einzelnes vorgefertigtes Sticky Bar Layout.
- `classes/StickyCartBarLayoutPresets.php`: Verwaltet die Sammlung der verfügbaren Layout-Voreinstellungen.
- `classes/StickyCartBarLayoutPresetsBuiltin.php`: Enthält die Definitionen für die Standard-, integrierten Layout-Voreinstellungen des Moduls.
- `classes/StickyCartBarListPresenter.php`: Hilfsklasse zum Formatieren und Präsentieren von Daten in Admin-Listen (z.B. `HelperList`).
- `classes/StickyCartBarMatcher.php`: Bestimmt, ob die Targeting-Regeln einer Sticky Bar (für eine Nicht-Experiment-Bar) mit dem aktuellen Kontext übereinstimmen.
- `classes/StickyCartBarRule.php`: Repräsentiert eine einzelne Targeting-Regel für eine Sticky Bar.
- `classes/StickyCartBarTargeting.php`: Zentrale Klasse zur Bewertung aller Targeting-Regeln (sowohl für Bars als auch für Experimente) anhand des aktuellen Front-Office-Kontexts.

### 4.4 JavaScript-Assets (`views/js/`)

- `lib/searchTool/views/js/autocomplete.js`: Bietet Autocomplete-Funktionalität, wahrscheinlich im Admin für die Auswahl von Produkten, Kategorien oder Herstellern für Targeting-Regeln verwendet.
- `views/js/admin-ab-dashboard.js`: Handhabt interaktive Elemente und Datenvisualisierung auf dem A/B-Test-Dashboard im Back Office.
- `views/js/admin-analytics-dashboard.js`: Verwaltet Diagramme, Filter und Datenanzeige auf dem Analyse-Dashboard.
- `views/js/admin-audience-picker.js`: Betreibt die interaktive Oberfläche zur Definition von Zielgruppen-Targeting-Regeln (z.B. Auswahl von Kundengruppen, Ländern).
- `views/js/admin-element-editor.js`: Bietet die JavaScript-Logik zum Bearbeiten einzelner Elemente innerhalb des Layout Studios (z.B. Öffnen eines Modals für Texteingabe, Farbwähler).
- `views/js/admin-layout-builder.js`: Das Kern-JavaScript für das Drag-and-Drop Layout Studio, das die Elementplatzierung, Größenänderung und Interaktion handhabt.
- `views/js/admin-layout-preview.js`: Verwaltet die Echtzeit-Vorschau der Sticky Bar innerhalb des Layout Studios.
- `views/js/admin-layout-studio.js`: Orchestriert alle Komponenten des Layout Studios, kombiniert Builder-, Editor- und Vorschau-Funktionalitäten.
- `views/js/admin.js`: Allzweck-JavaScript für die Back-Office-Seiten des Moduls, einschließlich globaler Event-Listener, Formularübermittlungen und AJAX-Aufrufe.
- `views/js/front.js`: Das Haupt-Front-Office-JavaScript für die Sticky Bar.
  - **Umfang:** Front-Office.
  - **Event-Listener:** Scrolls (um zu erkennen, wann die Bar angezeigt/ausgeblendet werden soll), Klicks auf „In den Warenkorb“-Buttons innerhalb der Bar, Klicks auf Variantenwähler, Formularübermittlungen.
  - **DOM-Manipulation:** Fügt den HTML-Code der Sticky Bar in das DOM ein, aktualisiert Warenkorbmengen, ändert Produktvarianten, zeigt/versteckt Elemente (z.B. FOMO-Timer).
  - **AJAX-Aufrufe:** Kommuniziert mit `controllers/front/ajax.php`, um Ereignisse zu verfolgen, den Warenkorb zu aktualisieren und dynamische Inhalte abzurufen.
  - **Drittanbieter-SDKs:** Keine explizit aufgeführt, aber könnte potenziell mit Analyseplattformen integriert werden, falls konfiguriert.

### 4.5 CSS-Stylesheets (`views/css/`)

- `lib/searchTool/views/css/autocomplete.css`: Stile für das Autocomplete-Suchwerkzeug im Admin.
- `views/css/admin-audience-picker.css`: Stile für die Zielgruppen-Targeting-Oberfläche im Admin.
- `views/css/admin-bars-list.css`: Stile für die Liste der Sticky Bars im Admin.
- `views/css/admin-config.css`: Allgemeine Stile für die Hauptkonfigurationsseite des Moduls.
- `views/css/admin-dashboard.css`: Stile für das Hauptmodul-Dashboard und potenziell Übersichten zu Analysen/A/B-Tests.
- `views/css/admin-element-editor.css`: Stile für die Elementbearbeitungs-Modals/Panels innerhalb des Layout Studios.
- `views/css/admin-layout-builder.css`: Kernstile für die Drag-and-Drop-Layout-Builder-Oberfläche.
- `views/css/admin-layout-preview.css`: Stile für den Echtzeit-Vorschau-Bereich im Layout Studio.
- `views/css/admin-layout-studio.css`: Gesamtstile für das Layout Studio, die alle seine Komponenten kombinieren.
- `views/css/admin-searchtool.css`: Spezifische Stile für das im Admin verwendete Suchwerkzeug.
- `views/css/front-classic.css`: Spezifische Front-Office-Stile für das PrestaShop-Theme „Classic“.
  - **Haupt-UI-Komponenten:** Überschreibt oder fügt Stile hinzu, um sicherzustellen, dass die Sticky Bar gut mit den Standardelementen des Classic-Themes integriert ist.
  - **Wichtige CSS-Klassenselektoren:** `.scbp-bar`, `.scbp-button`, `.scbp-product-info`, etc., potenziell mit Theme-spezifischen Überschreibungen.
- `views/css/front-hummingbird.css`: Spezifische Front-Office-Stile für das PrestaShop-Theme „Hummingbird“ (PrestaShop 8.1+).
  - **Haupt-UI-Komponenten:** Ähnlich wie `front-classic.css`, aber auf die Struktur und das Design des Hummingbird-Themes zugeschnitten.
  - **Wichtige CSS-Klassenselektoren:** `.scbp-bar`, `.scbp-button`, etc., mit Hummingbird-spezifischen Anpassungen.
- `views/css/front.css`: Allgemeine Front-Office-Stile für die Sticky Bar, die auf alle Themes angewendet werden.
  - **Haupt-UI-Komponenten:** Basis-Styling für den Sticky Bar Container, seine Elemente (Buttons, Text, Bilder, Timer) und Positionierung (fixiert oben/unten).
  - **Wichtige CSS-Klassenselektoren:** `.scbp-bar`, `.scbp-element`, `.scbp-add-to-cart`, `.scbp-product-name`, `.scbp-price`, `.scbp-quantity-selector`, `.scbp-countdown`, `.scbp-stock-indicator`. Entwickler können diese Klassen in ihrem Theme-eigenen CSS überschreiben.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

- `sticky-cart-bar-classic.tpl`: Rendert die Sticky Bar speziell für das Classic-Theme. Dieses Template enthält wahrscheinlich Theme-spezifische HTML-Strukturen oder Klassennamen, um eine nahtlose Integration zu gewährleisten.
  - **Hook:** `displayHeader` oder `displayFooter` (abhängig von der Bar-Position und der internen Modul-Logik).
  - **Ausgabe:** Die Haupt-HTML-Struktur für die Sticky Bar, einschließlich Platzhaltern für dynamische Inhalte.
- `sticky-cart-bar-element-inner.tpl`: Rendert den inneren Inhalt eines einzelnen Elements innerhalb der Sticky Bar. Dies ist ein wiederverwendbares Partial.
  - **Hook:** N/A (wird von anderen Templates inkludiert).
  - **Ausgabe:** HTML für einen spezifischen Elementtyp (z.B. Produktname, Preis, Mengeneingabe).
- `sticky-cart-bar-element.tpl`: Rendert ein einzelnes Element (z.B. Button, Bild, Textblock) der Sticky Bar, wobei `sticky-cart-bar-element-inner.tpl` mit gemeinsamen Element-Wrappern umschlossen wird.
  - **Hook:** N/A (wird von anderen Templates inkludiert).
  - **Ausgabe:** HTML für eine einzelne, gestylte Sticky Bar Komponente.
- `sticky-cart-bar-hummingbird.tpl`: Rendert die Sticky Bar speziell für das Hummingbird-Theme. Ähnlich wie `sticky-cart-bar-classic.tpl`, aber an das neuere Theme angepasst.
  - **Hook:** `displayHeader` oder `displayFooter`.
  - **Ausgabe:** Die Haupt-HTML-Struktur für die Sticky Bar, optimiert für Hummingbird.
- `sticky-cart-bar-inner.tpl`: Rendert den inneren Inhalt der gesamten Sticky Bar, der alle einzelnen Elemente enthält.
  - **Hook:** N/A (wird von `sticky-cart-bar.tpl` inkludiert).
  - **Ausgabe:** Das kombinierte HTML aller konfigurierten Elemente für eine Sticky Bar.
- `sticky-cart-bar.tpl`: Das Haupt-Template, das für das Rendern der Sticky Cart Bar im Front Office verantwortlich ist. Es bestimmt, welches Theme-spezifische Template (Classic/Hummingbird) inkludiert werden soll oder verwendet eine generische Struktur.
  - **Hook:** `displayHeader` oder `displayFooter` (Modul registriert sich für diese Hooks).
  - **Ausgabe:** Die vollständige, gerenderte Sticky Cart Bar, einschließlich ihres Containers, ihrer Elemente und notwendiger Datenattribute für JavaScript.

#### Admin-Templates (`views/templates/admin/`)

- `ab-test-dashboard.tpl`: Rendert das Haupt-Dashboard für A/B-Tests, zeigt Experimentlisten und Zusammenfassungsdaten an.
- `ab-tests-tab.tpl`: Rendert den Inhalt für den Tab „A/B-Tests“ innerhalb der Modulkonfiguration.
- `analytics-dashboard.tpl`: Rendert das Analyse-Dashboard mit Diagrammen und Leistungsmetriken.
- `audience-picker.tpl`: Rendert das HTML für die Oberfläche zur Auswahl der Zielgruppen-Targeting (z.B. Länder, Kundengruppen).
- `bars-tab.tpl`: Rendert den Inhalt für den Tab „Bars verwalten“, einschließlich der Liste der Sticky Bars.
- `configure.tpl`: Das Hauptkonfigurations-Template für das Modul, das als Wrapper für alle anderen Admin-Templates und Tabs dient.
- `country-priority-picker.tpl`: Rendert eine spezifische UI-Komponente zur Auswahl und Priorisierung von Ländern in Targeting-Regeln.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

- `ps_stickycartbar_bar`: Speichert die Konfiguration für jede einzelne Sticky Cart Bar.
  - `id_stickycartbar_bar` (PK, INT)
  - `name` (VARCHAR)
  - `content` (TEXT, JSON-kodiert: enthält Elemente, Stile, Position, Sichtbarkeitseinstellungen)
  - `targeting_rules` (TEXT, JSON-kodiert: Bedingungen für die Anzeige)
  - `active` (TINYINT)
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_stickycartbar_experiment`: Speichert die Konfiguration für jedes A/B-Test-Experiment.
  - `id_stickycartbar_experiment` (PK, INT)
  - `name` (VARCHAR)
  - `id_control_bar` (INT, FK zu `ps_stickycartbar_bar`)
  - `id_variant_bars` (TEXT, JSON-kodiertes Array von FKs zu `ps_stickycartbar_bar`)
  - `traffic_distribution` (TEXT, JSON-kodiert: Prozentsatz für jede Bar)
  - `goal` (VARCHAR: z.B. ‘add\_to\_cart’, ‘conversion’)
  - `targeting_rules` (TEXT, JSON-kodiert)
  - `active` (TINYINT)
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_stickycartbar_analytics`: Speichert Analysedaten (Impressionen, Klicks, Konversionen) für Bars und Experimente.
  - `id_stickycartbar_analytics` (PK, INT)
  - `id_stickycartbar_bar` (INT, FK)
  - `id_stickycartbar_experiment` (INT, FK, NULLABLE)
  - `type` (VARCHAR: ‘impression’, ‘click’, ‘add\_to\_cart’, ‘conversion’)
  - `id_customer` (INT, NULLABLE)
  - `id_guest` (INT, NULLABLE)
  - `date_add` (DATETIME)
- **`ps_configuration`**: Speichert globale Moduleinstellungen (z.B. `STICKYCARTBARPRO_ENABLED`, `STICKYCARTBARPRO_ANALYTICS_ENABLED`).

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Fügt CSS- und JavaScript-Dateien für die Sticky Bar ein und potenziell die anfängliche HTML-Struktur, wenn die Bar oben positioniert ist. |
| `displayFooter` | Vor dem schließenden `</body>`-Tag auf jeder Seite. | Fügt die HTML-Struktur für Sticky Bars, die unten positioniert sind, und alle notwendigen JavaScript-Initialisierungen ein. |
| `actionFrontControllerSetMedia` | Nachdem ein Front-Controller seine Medien-Assets gesetzt hat. | Ermöglicht dem Modul, seine JS/CSS bedingt basierend auf dem aktuellen Seitenkontext hinzuzufügen (z.B. nur auf Produktseiten). |
| `actionProductUpdate` | Nachdem ein Produkt im Back Office aktualisiert wurde. | Potenziell verwendet, um den Cache bezüglich Produktdaten zu leeren, die in Sticky Bars angezeigt werden könnten. |
| `actionObjectProductAddAfter` | Nachdem ein neues Produkt hinzugefügt wurde. | Ähnlich wie `actionProductUpdate`. |
| `actionObjectProductUpdateAfter` | Nachdem ein bestehendes Produkt aktualisiert wurde. | Ähnlich wie `actionProductUpdate`. |
| `actionObjectProductDeleteAfter` | Nachdem ein Produkt gelöscht wurde. | Potenziell verwendet, um alle Verweise auf das gelöschte Produkt in Sticky Bar Konfigurationen zu bereinigen. |
| `actionCartSave` | Nachdem ein Warenkorb gespeichert oder aktualisiert wurde. | Wird verwendet, um „In den Warenkorb“-Ereignisse für Analysen und A/B-Testziele zu verfolgen. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | Wird verwendet, um Konversionsereignisse für Analysen und A/B-Testziele zu verfolgen. |
| `displayBackOfficeHeader` | Im `<head>`-Bereich jeder Back-Office-Seite. | Fügt CSS und JavaScript für die Admin-Oberflächen des Moduls (Layout Studio, Dashboards) ein. |
| `moduleRoutes` | Während der URL-Routing-Initialisierung. | Registriert benutzerdefinierte Front-Office-Routen für AJAX-Controller, falls erforderlich. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul Sticky Cart Bar PRO besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.
