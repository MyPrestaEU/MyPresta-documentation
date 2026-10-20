---
title: "Omnibus-Richtlinie Pro - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Omnibus-Richtlinie Pro von MyPresta.eu."
sidebar:
  label: "Omnibus-Richtlinie Pro - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Omnibus Directive Pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/omnibus-directive-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/omnibus-directive-pro/)
>
> ---


# Omnibus-Richtlinie Pro

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Omnibus-Richtlinie Pro)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie das Kernverhalten und die Anzeigeoptionen des Moduls Omnibus-Richtlinie Pro steuern.

#### Allgemeine Einstellungen

- **Modul aktivieren:**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter zum Aktivieren oder Deaktivieren der gesamten Funktionalität des Moduls.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul beginnt mit der Preisverfolgung, der Anzeige der niedrigsten Preisinformationen, und alle anderen konfigurierten Funktionen werden aktiv.
    - *Wenn deaktiviert:* Das Modul stoppt alle seine Operationen, einschließlich Preisverfolgung und Front-Office-Anzeige. Es werden keine Informationen zum niedrigsten Preis angezeigt.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Aktivieren Sie dies nach der Installation, um die Richtlinie einzuhalten. Deaktivieren Sie es nur, wenn Sie die Funktionalität vorübergehend für Wartungsarbeiten oder spezifische Tests pausieren müssen.
- **Niedrigsten Preis auf Produktseite anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert, ob das Abzeichen oder der Text „niedrigster Preis in den letzten 30 Tagen“ auf einzelnen Produktseiten angezeigt wird, wenn ein Produkt im Angebot ist.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Informationen zum niedrigsten Preis sind für Kunden auf jeder Produktseite sichtbar, auf der eine Preisermäßigung aktiv ist.
    - *Wenn deaktiviert:* Die Informationen zum niedrigsten Preis werden NICHT auf Produktseiten angezeigt, selbst wenn ein Produkt im Angebot ist.
  - **Empfohlener Wert:** JA (Dringend empfohlen zur Einhaltung der Vorschriften).
  - **Händlerszenario / Beispiel:** Sie müssen dies aktivieren, um die Omnibus-Richtlinie einzuhalten. Wenn Sie es deaktivieren, zeigen Ihre Produktseiten während des Verkaufs nicht die erforderlichen Informationen an.
- **Niedrigsten Preis in Produktlisten anzeigen (Kategorie, Suche usw.):**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob die Informationen zum niedrigsten Preis auf Produktkarten in Listen (z.B. Kategorieseiten, Suchergebnisse, Herstellerseiten) angezeigt werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Abzeichen für den niedrigsten Preis wird auf Produktkarten in Listenansichten angezeigt und bietet den Kunden frühzeitig Transparenz.
    - *Wenn deaktiviert:* Die Informationen zum niedrigsten Preis werden nur auf der einzelnen Produktseite angezeigt, nicht in Listen.
  - **Empfohlener Wert:** JA (Empfohlen für maximale Transparenz und Sichtbarkeit der Konformität).
  - **Händlerszenario / Beispiel:** Die Aktivierung hilft Kunden, konforme Verkäufe direkt von Kategorieseiten aus schnell zu identifizieren, was möglicherweise die Klickraten zu Produktseiten erhöht.
- **Preischart auf Produktseite aktivieren:**

  - **Was diese Einstellung bewirkt:** Aktiviert ein interaktives Diagramm auf der Produktseite, das die Preishistorie des Produkts im Laufe der Zeit visuell darstellt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Diagramm wird auf der Produktseite eingebettet, sodass Kunden vergangene Preisschwankungen sehen können.
    - *Wenn deaktiviert:* Das Preischart wird nicht angezeigt.
  - **Empfohlener Wert:** JA (Erhöht die Transparenz und das Kundenvertrauen).
  - **Händlerszenario / Beispiel:** Preisempfindliche Kunden oder solche, die die Legitimität eines Verkaufs überprüfen möchten, können dieses Diagramm verwenden. Es fügt eine zusätzliche Vertrauensebene hinzu.
- **Cron-URL zur Bereinigung der Preishistorie:**

  - **Was diese Einstellung bewirkt:** Bietet eine eindeutige URL, die, wenn sie aufgerufen wird, den automatisierten Prozess des Moduls zur Bereinigung alter Preishistoriedaten auslöst. Dies hält Ihre Datenbank optimiert.
  - **Auswirkung der Änderung dieser Einstellung:** Dies ist ein schreibgeschütztes Feld. Sie müssen einen Cron-Job auf Ihrem Server einrichten, um diese URL regelmäßig aufzurufen.
  - **Empfohlener Wert:** Kopieren Sie diese URL und richten Sie einen Cron-Job ein.
  - **Händlerszenario / Beispiel:** Richten Sie einen Cron-Job ein, der diese URL einmal täglich (z.B. um 3 Uhr morgens) ausführt, um sicherzustellen, dass Ihre Preishistorie-Datenbank schlank und effizient bleibt und nicht mit der Zeit zu groß wird.
- **CSV-Audit-Log aktivieren:**

  - **Was diese Einstellung bewirkt:** Wenn aktiviert, generiert das Modul eine CSV-Datei mit einem detaillierten Protokoll von Preisänderungen und Berechnungen des niedrigsten Preises, was für Audits und die Überprüfung der Konformität nützlich sein kann.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Eine CSV-Datei wird generiert und mit Audit-Informationen aktualisiert.
    - *Wenn deaktiviert:* Es wird kein Audit-Log erstellt oder geführt.
  - **Empfohlener Wert:** NEIN (Es sei denn, es ist speziell für interne Audits oder rechtliche Zwecke erforderlich, da es Speicherplatz verbrauchen kann).
  - **Händlerszenario / Beispiel:** Wenn Ihr Rechtsteam oder Auditoren eine nachprüfbare Aufzeichnung Ihrer Konformitätsaktivitäten benötigen, aktivieren Sie dies. Andernfalls ist es für den täglichen Betrieb im Allgemeinen nicht erforderlich.

#### Badge Studio

Dieser Abschnitt ermöglicht es Ihnen, das visuelle Erscheinungsbild des „Niedrigster Preis“-Abzeichens in Ihrem Shop anzupassen.

- **Abzeichentyp:**

  - **Was diese Einstellung bewirkt:** Wählen Sie zwischen einem „Smart Badge“ (hochgradig anpassbar mit Symbolen, Farben und Text) oder einer „Einfachen Text“-Anzeige.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Smart Badge:* Schaltet weitere Anpassungsoptionen für ein visuell ansprechendes Abzeichen frei.
    - *Einfacher Text:* Zeigt nur einfachen Text ohne erweiterte Formatierung an.
  - **Empfohlener Wert:** Smart Badge (Bietet mehr Kontrolle und bessere Integration in Ihr Theme).
  - **Händlerszenario / Beispiel:** Wenn Sie ein prominentes, gebrandetes Abzeichen wünschen, wählen Sie „Smart Badge“. Wenn Sie einen minimalistischen Ansatz bevorzugen, ist „Einfacher Text“ möglicherweise besser.
- **Abzeichenposition (Produktseite):**

  - **Was diese Einstellung bewirkt:** Wählen Sie, wo das Abzeichen auf der Produktseite erscheint. Optionen umfassen typischerweise „Neben dem Preis“, „Unter dem Preis“, „Benutzerdefinierter Hook“ usw.
  - **Auswirkung der Änderung dieser Einstellung:** Ändert die visuelle Platzierung des Abzeichens auf der Produktseite.
  - **Empfohlener Wert:** Neben dem Preis (Häufigste und rechtlich eindeutigste Platzierung).
  - **Händlerszenario / Beispiel:** Testen Sie verschiedene Positionen, um zu sehen, was am besten zu Ihrem Theme passt und für Kunden am sichtbarsten ist, ohne aufdringlich zu wirken.
- **Abzeichenposition (Produktlisten):**

  - **Was diese Einstellung bewirkt:** Wählen Sie, wo das Abzeichen auf Produktkarten in Listenansichten erscheint. Optionen umfassen typischerweise „Unter dem Produktnamen“, „Unter dem Preis“, „Benutzerdefinierter Hook“ usw.
  - **Auswirkung der Änderung dieser Einstellung:** Ändert die visuelle Platzierung des Abzeichens auf Produktkarten.
  - **Empfohlener Wert:** Unter dem Preis (Klar und konsistent mit der Platzierung auf der Produktseite).
  - **Händlerszenario / Beispiel:** Stellen Sie sicher, dass das Abzeichen keine anderen Elemente auf Ihren Produktkarten überlappt, insbesondere auf Mobilgeräten.
- **Abzeichentext:**

  - **Was diese Einstellung bewirkt:** Passen Sie den tatsächlichen Text an, der im Abzeichen angezeigt wird. Sie können Platzhalter wie `{lowest_price}` für den tatsächlichen niedrigsten Preiswert verwenden.
  - **Auswirkung der Änderung dieser Einstellung:** Ändert die Nachricht, die Kunden lesen.
  - **Empfohlener Wert:** „Niedrigster Preis in den letzten 30 Tagen: {lowest\_price}“ (Klar und konform).
  - **Händlerszenario / Beispiel:** Sie können diesen Text für verschiedene Sprachen übersetzen oder leicht umformulieren, um ihn an den Ton Ihrer Marke anzupassen, solange die Bedeutung klar und konform bleibt.
- **Abzeichen-Hintergrundfarbe:**

  - **Was diese Einstellung bewirkt:** Legt die Hintergrundfarbe des Smart Badges fest.
  - **Auswirkung der Änderung dieser Einstellung:** Ändert den visuellen Hintergrund des Abzeichens.
  - **Empfohlener Wert:** Eine Farbe, die gut mit Ihrem Text und Theme kontrastiert, z.B. ein helles Grau oder eine Akzentfarbe Ihrer Marke.
  - **Händlerszenario / Beispiel:** Wählen Sie eine Farbe, die das Abzeichen hervorhebt, aber dennoch professionell aussieht und sich in das Design Ihres Shops integriert.
- **Abzeichen-Textfarbe:**

  - **Was diese Einstellung bewirkt:** Legt die Farbe des Textes innerhalb des Smart Badges fest.
  - **Auswirkung der Änderung dieser Einstellung:** Ändert die visuelle Farbe des Textes.
  - **Empfohlener Wert:** Eine Farbe, die vor der gewählten Hintergrundfarbe gut lesbar ist, z.B. Schwarz oder Dunkelgrau.
  - **Händlerszenario / Beispiel:** Sorgen Sie für hohen Kontrast für Zugänglichkeit und Lesbarkeit.
- **Abzeichen-Symbol:**

  - **Was diese Einstellung bewirkt:** Ermöglicht die Auswahl eines Symbols, das zusammen mit dem Text im Smart Badge angezeigt wird.
  - **Auswirkung der Änderung dieser Einstellung:** Fügt dem Abzeichen ein visuelles Symbol hinzu.
  - **Empfohlener Wert:** Ein relevantes Symbol, z.B. ein „Tag“- oder „Info“-Symbol.
  - **Händlerszenario / Beispiel:** Ein kleines, klares Symbol kann die Aufmerksamkeit auf das Abzeichen lenken und seinen Zweck intuitiver machen.

#### Analyse-Panel

Dieser Abschnitt bietet Einblicke in die Leistung und den Konformitätsstatus Ihres Moduls.

- **Analysen anzeigen:**
  - **Was diese Einstellung bewirkt:** Diese Schaltfläche öffnet ein spezielles Panel in Ihrem Back Office, das Statistiken zur Preisverfolgung, zu Produkten im Angebot und zum Konformitätsstatus anzeigt.
  - **Auswirkung der Änderung dieser Einstellung:** Durch Klicken auf diese Schaltfläche gelangen Sie zum Analyse-Dashboard.
  - **Empfohlener Wert:** Überprüfen Sie dies regelmäßig.
  - **Händlerszenario / Beispiel:** Verwenden Sie das Analyse-Panel, um zu überwachen, wie viele Produkte derzeit den niedrigsten Preis anzeigen, potenzielle Probleme zu identifizieren oder den gesamten Konformitätsstatus Ihres Shops zu überprüfen.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | Modul aktivieren | JA | Aktiviert/deaktiviert alle Modulfunktionen. |
|  | Niedrigsten Preis auf Produktseite anzeigen | JA | Zeigt den niedrigsten 30-Tage-Preis auf Produktseiten während des Verkaufs an. |
|  | Niedrigsten Preis in Produktlisten anzeigen | JA | Zeigt den niedrigsten 30-Tage-Preis auf Kategorie-/Suchseiten während des Verkaufs an. |
|  | Preischart auf Produktseite aktivieren | JA | Zeigt ein interaktives Preishistorie-Diagramm auf Produktseiten an. |
|  | Cron-URL zur Bereinigung der Preishistorie | (Kopieren & Einrichten) | URL für die automatisierte Datenbankbereinigung. Täglich ausführen. |
|  | CSV-Audit-Log aktivieren | NEIN | Erstellt ein detailliertes Protokoll von Preisänderungen für Audits. |
| **Badge Studio** | Abzeichentyp | Smart Badge | Wählen Sie zwischen anpassbarem Abzeichen oder einfachem Text. |
|  | Abzeichenposition (Produktseite) | Neben dem Preis | Legt die Platzierung des Abzeichens auf einzelnen Produktseiten fest. |
|  | Abzeichenposition (Produktlisten) | Unter dem Preis | Legt die Platzierung des Abzeichens auf Produktkarten in Listen fest. |
|  | Abzeichentext | „Niedrigster Preis in den letzten 30 Tagen: {lowest\_price}“ | Anpassbarer Text für das Abzeichen. |
|  | Abzeichen-Hintergrundfarbe | (Theme-abhängig) | Legt die Hintergrundfarbe des Smart Badges fest. |
|  | Abzeichen-Textfarbe | (Theme-abhängig) | Legt die Textfarbe des Smart Badges fest. |
|  | Abzeichen-Symbol | (Relevantes Symbol) | Fügt dem Smart Badge ein visuelles Symbol hinzu. |
| **Analyse-Panel** | Analysen anzeigen | (Schaltfläche klicken) | Öffnet ein Dashboard für Konformitäts- und Preisverfolgungsstatistiken. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Das Abzeichen für den niedrigsten Preis wird auf meinen Produktseiten nicht angezeigt, obwohl ich es aktiviert habe.**
A:

1. **Modulstatus überprüfen:** Stellen Sie sicher, dass die Einstellung „Modul aktivieren“ auf JA steht.
2. **Produkt im Angebot?** Das Abzeichen erscheint nur für Produkte, die derzeit im Angebot sind (einen spezifischen Preis oder Rabatt haben). Stellen Sie sicher, dass das Produkt, das Sie testen, eine aktive Preisermäßigung aufweist.
3. **Cache leeren:** Gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Einstellungen > Leistung** und leeren Sie den Smarty-Cache, den Browser-Cache und alle anderen Caches (z.B. CDN-Cache), die Sie möglicherweise verwenden.
4. **Theme-Kompatibilität:** Obwohl das Modul für eine breite Kompatibilität ausgelegt ist, können sehr stark angepasste Themes geringfügige Anpassungen erfordern. Wenn das Problem weiterhin besteht, wenden Sie sich an den MyPresta.eu-Support.

**F2: Das Preishistorie-Diagramm zeigt keine Daten an oder sieht unvollständig aus.**
A:

1. **Modul aktiviert:** Stellen Sie sicher, dass „Preischart auf Produktseite aktivieren“ auf JA steht.
2. **Preisänderungen:** Das Diagramm zeigt nur Daten an, wenn das Produkt seit der Installation und Aktivierung des Moduls aufgezeichnete Preisänderungen hatte. Wenn sich der Preis eines Produkts nie geändert hat, gibt es keine Historie anzuzeigen.
3. **Zeit zum Sammeln von Daten:** Es dauert eine Weile, bis das Modul die Preishistorie gesammelt hat. Wenn Sie es gerade installiert haben, werden Daten gesammelt, wenn sich die Preise im Laufe der Tage/Wochen ändern.

**F3: Wie oft sollte ich den Cron-Job zur Bereinigung der Preishistorie ausführen?**
A: Wir empfehlen, den Cron-Job einmal alle 24 Stunden auszuführen. Diese Häufigkeit ist ausreichend, um Ihre Datenbank optimiert zu halten, ohne den Server übermäßig zu belasten.

**F4: Das Styling meines benutzerdefinierten Themes kollidiert mit dem Abzeichen des Moduls. Wie kann ich das beheben?**
A: Das „Badge Studio“ bietet umfangreiche Anpassungsmöglichkeiten für Farben, Text und Symbole. Versuchen Sie zunächst, diese Einstellungen an Ihr Theme anzupassen. Wenn Sie immer noch Styling-Konflikte haben, müssen Sie möglicherweise einen Webmaster beauftragen, benutzerdefinierte CSS-Überschreibungen anzuwenden. Die CSS-Dateien des Moduls sind so konzipiert, dass sie leicht von der Stylesheet-Datei Ihres Themes überschrieben werden können.

**F5: Was passiert, wenn ich das Modul deaktiviere? Werden meine Preishistorie-Daten gelöscht?**
A: Das Deaktivieren des Moduls stoppt die Front-Office-Anzeige und die Hintergrundprozesse, löscht jedoch normalerweise nicht die gesammelten Preishistorie-Daten. Wenn Sie es später wieder aktivieren, sollten die Daten noch verfügbar sein. Für eine vollständige Datenentfernung müssten Sie das Modul deinstallieren und die Option zum Löschen seiner Daten wählen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen tiefen Einblick in die technische Architektur des Moduls Omnibus-Richtlinie Pro, der für Entwickler, Webmaster und technische Agenturen bestimmt ist.

### 4.1 Architekturübersicht

Das Modul Omnibus-Richtlinie Pro folgt einem Standard-PrestaShop-MVC-Muster (Model-View-Controller) mit einem Fokus auf ereignisgesteuerte Hooks für die Integration. Es erweitert hauptsächlich `Module` für seine Kernfunktionalität und Konfiguration, verwendet `ModuleFrontController` für spezifische Front-Office-Aktionen (wie Cron-Bereinigung) und nutzt Smarty-Templates für das Rendering. Die Preishistorie wird durch direkte Datenbankinteraktion und `Configuration`-Werte verwaltet. Das Modul integriert ein „Badge Studio“ und ein „Analytics Panel“ im Back Office für erweiterte Händlerkontrolle und Einblicke.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `omnipro/controllers/front/cleanupcron.php`
  - **Klassenname & Elternklasse:** `OmniproCleanupcronModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller ist für den Zugriff über einen Cron-Job konzipiert. Wenn er aufgerufen wird, führt er die interne Bereinigungslogik des Moduls für Preishistoriedaten aus, wobei typischerweise alte Datensätze entfernt werden, um die Datenbankleistung aufrechtzuerhalten. Er rendert keine visuelle Ausgabe an den Browser, sondern gibt normalerweise eine einfache Erfolgs- oder Fehlermeldung zurück.
- `omnipro/controllers/front/index.php`
  - **Klassenname & Elternklasse:** `OmniproIndexModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller dient wahrscheinlich als Fallback oder als allgemeiner Einstiegspunkt für Front-Office-Modulaktionen, die kein spezifisches Routing erfordern, oder er könnte ein Platzhalter sein. Angesichts der Hauptfunktion des Moduls ist es weniger wahrscheinlich, dass er komplexe Benutzerinteraktionen direkt verarbeitet, könnte aber für einfache Datenabrufe oder Statusprüfungen verwendet werden.

#### Back-Office-Admin-Controller

Es wurden keine dedizierten Admin-Controller (`controllers/admin/`) identifiziert, was darauf hindeutet, dass alle Back Office-Konfigurationen und Analysen direkt in der `getContent()`-Methode der Hauptmoduldatei behandelt werden.

### 4.3 Kernklassen & Modelle (`classes/`)

Es wurden keine benutzerdefinierten Klassen, die `ObjectModel` erweitern, im Verzeichnis `classes/` identifiziert. Dies deutet darauf hin, dass Preishistoriedaten wahrscheinlich direkt in `ps_configuration` oder einer benutzerdefinierten Tabelle gespeichert werden, die von der Hauptmoduldatei (`omnipro/index.php`) ohne einen dedizierten `ObjectModel`-Wrapper verwaltet wird.

### 4.4 JavaScript-Assets (`views/js/`)

- `omnipro/views/js/admin-analytics.js`
  - **Geltungsbereich:** Back-Office.
  - **Beschreibung:** Dieses Skript ist für die interaktiven Elemente und die Datenvisualisierung innerhalb des „Analytics Panel“ des Moduls im Back Office verantwortlich. Es verarbeitet wahrscheinlich AJAX-Anfragen zum Abrufen von Analysedaten, rendert Diagramme (z.B. mit Chart.js oder ähnlichen Bibliotheken) und aktualisiert die Benutzeroberfläche basierend auf Benutzerinteraktionen innerhalb des Analyse-Dashboards.
- `omnipro/views/js/admin-badge-studio.js`
  - **Geltungsbereich:** Back-Office.
  - **Beschreibung:** Dieses Skript bietet die interaktive Funktionalität für den Konfigurationsbildschirm „Badge Studio“. Es verwaltet Echtzeit-Vorschauen des Abzeichens, während der Händler Farben, Text, Symbole und Positionen anpasst. Es verarbeitet wahrscheinlich Farbwähler, Aktualisierungen von Eingabefeldern und die dynamische Darstellung eines Vorschau-Abzeichens.
- `omnipro/views/js/admin-config.js`
  - **Geltungsbereich:** Back-Office.
  - **Beschreibung:** Ein Allzweckskript für die Hauptmodulkonfigurationsseite. Es könnte die Formularvalidierung, die bedingte Anzeige von Einstellungen basierend auf anderen Auswahlen (z.B. Anzeige der Abzeichenanpassung nur, wenn „Smart Badge“ ausgewählt ist) und allgemeine UI-Verbesserungen für das Konfigurationsformular behandeln.
- `omnipro/views/js/front-chart.js`
  - **Geltungsbereich:** Front-Office.
  - **Beschreibung:** Dieses Skript ist für das Rendern des interaktiven Preishistorie-Diagramms auf der Produktseite verantwortlich. Es ruft wahrscheinlich Preisdaten über AJAX ab (möglicherweise von einem dedizierten Front-Controller oder einem Hook), initialisiert eine Diagrammbibliothek (z.B. Chart.js) und zeigt die Preisentwicklung visuell dem Kunden an.

### 4.5 CSS-Stylesheets (`views/css/`)

- `omnipro/views/css/admin-analytics.css`
  - **Geltungsbereich:** Back-Office-Admin-Styling.
  - **Beschreibung:** Stylesheets speziell für das Layout und das Erscheinungsbild des „Analytics Panel“ in der Back Office-Konfiguration des Moduls.
- `omnipro/views/css/admin-badge-studio.css`
  - **Geltungsbereich:** Back-Office-Admin-Styling.
  - **Beschreibung:** Stylesheets für die „Badge Studio“-Oberfläche, einschließlich Styling für Farbwähler, Vorschau-Elemente und Layout der Anpassungsoptionen.
- `omnipro/views/css/admin-config.css`
  - **Geltungsbereich:** Back-Office-Admin-Styling.
  - **Beschreibung:** Allgemeines Styling für das Hauptmodul-Konfigurationsformular im Back Office, um eine konsistente und benutzerfreundliche Oberfläche zu gewährleisten.
- `omnipro/views/css/omnibus-classic.css`
  - **Geltungsbereich:** Front-Office-Kunden-Styling.
  - **Beschreibung:** Bietet Standard-Styling für das Abzeichen des niedrigsten Preises und möglicherweise das Preischart, speziell zugeschnitten auf ältere PrestaShop „Classic“-Themes oder Themes, die deren Struktur nachahmen.
- `omnipro/views/css/omnibus-hummingbird.css`
  - **Geltungsbereich:** Front-Office-Kunden-Styling.
  - **Beschreibung:** Bietet Standard-Styling für das Abzeichen des niedrigsten Preises und möglicherweise das Preischart, speziell optimiert für das neuere PrestaShop „Hummingbird“-Theme.
- `omnipro/views/css/omnibus.css`
  - **Geltungsbereich:** Front-Office-Kunden-Styling.
  - **Beschreibung:** Kern-Front-Office-Styles für das Abzeichen des niedrigsten Preises und das Preischart, anwendbar auf verschiedene Themes. Dies enthält wahrscheinlich die grundlegenden visuellen Regeln, wobei `omnibus-classic.css` und `omnibus-hummingbird.css` Theme-spezifische Überschreibungen oder Ergänzungen bereitstellen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- `omnipro/lib/searchTool/views/scripts.tpl`
  - **Geltungsbereich:** Unklar ohne Kontext, aber `lib` deutet auf eine Drittanbieterbibliothek oder ein internes Dienstprogramm hin. `scripts.tpl` enthält oft JS- oder CSS-Assets.
  - **Beschreibung:** Dieses Template enthält wahrscheinlich JavaScript- oder CSS-Dateien, die von einem internen Suchwerkzeug oder Dienstprogramm des Moduls benötigt werden, möglicherweise für die Datenverarbeitung oder spezifische UI-Komponenten innerhalb des Admin-Bereichs.
- `omnipro/views/templates/admin/analytics-panel.tpl`
  - **Geltungsbereich:** Admin-Template.
  - **Beschreibung:** Rendert die HTML-Struktur für das „Analytics Panel“ im Back Office, einschließlich Platzhaltern für Diagramme, Statistiken und Datentabellen.
- `omnipro/views/templates/admin/badge-studio.tpl`
  - **Geltungsbereich:** Admin-Template.
  - **Beschreibung:** Rendert das HTML-Formular und den Vorschaubereich für die „Badge Studio“-Konfiguration, sodass Händler das Erscheinungsbild des Abzeichens für den niedrigsten Preis anpassen können.
- `omnipro/views/templates/admin/configure.tpl`
  - **Geltungsbereich:** Admin-Template.
  - **Beschreibung:** Das Hauptkonfigurationstemplate für das Modul, gerendert von `getContent()` in `omnipro/index.php`. Es enthält alle allgemeinen Einstellungen und wahrscheinlich `analytics-panel.tpl` und `badge-studio.tpl` oder Links dazu.
- `omnipro/views/templates/hook/omnibus-badge.tpl`
  - **Geltungsbereich:** Hook-Template (Front-Office).
  - **Beschreibung:** Dieses Template wird in verschiedenen Front-Office-Hooks (z.B. `displayProductPriceBlock`, `displayProductListFunctionalButtons`) gerendert, um das HTML für das Abzeichen des niedrigsten Preises auf Produktseiten und in Listen auszugeben. Es empfängt Variablen, die den niedrigsten Preis und andere Anpassungsoptionen für das Abzeichen enthalten.
- `omnipro/views/templates/hook/omnibus.tpl`
  - **Geltungsbereich:** Hook-Template (Front-Office).
  - **Beschreibung:** Ein allgemeineres Hook-Template, das möglicherweise zum Einbetten des Preischarts (`front-chart.js`) oder anderer modulbezogener Inhalte auf der Produktseite oder zur allgemeinen Modulinitialisierung in `displayHeader` oder `displayFooter` verwendet wird.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul speichert seine Hauptkonfigurationseinstellungen wahrscheinlich in `ps_configuration` (z.B. `OMNIPRO_ENABLED`, `OMNIPRO_DISPLAY_PRODUCT_PAGE`).
  - Angesichts der Funktion „Preishistorie“ und der „Cron-Bereinigung“ ist es sehr wahrscheinlich, dass das Modul mindestens eine benutzerdefinierte Datenbanktabelle (z.B. `ps_omnipro_price_history`) erstellt, um Produktpreisdatensätze im Laufe der Zeit zu speichern. Diese Tabelle würde typischerweise die Felder `id_product`, `id_product_attribute`, `id_shop`, `id_currency`, `price` und `date_add` enthalten.
  - Wenn „CSV-Audit-Log“ aktiviert ist, speichert es möglicherweise Verweise auf generierte CSV-Dateien oder Protokolleinträge in einer dedizierten Tabelle.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | CSS/JS-Assets für das Front-Office injizieren, modulweite JS-Variablen initialisieren. |
| `displayProductPriceBlock` | In der Nähe des Produktpreises auf der Produktseite. | Das Abzeichen für den niedrigsten Preis (`omnibus-badge.tpl`) auf der Produktseite rendern. |
| `displayProductListFunctionalButtons` | Innerhalb von Produktlisten (Kategorie, Suche usw.). | Das Abzeichen für den niedrigsten Preis (`omnibus-badge.tpl`) auf Produktkarten rendern. |
| `displayFooterProduct` | Am unteren Rand der Produktseite. | Potenziell das Preischart (`omnibus.tpl` mit `front-chart.js`) rendern. |
| `actionProductUpdate` | Nach der Aktualisierung eines Produkts im Back Office. | Die Aufzeichnung der Preishistorie für das aktualisierte Produkt auslösen. |
| `actionProductAdd` | Nach dem Hinzufügen eines neuen Produkts. | Die Aufzeichnung der Preishistorie für das neue Produkt initialisieren. |
| `actionProductDelete` | Nach dem Löschen eines Produkts. | Zugehörige Preishistoriedaten bereinigen. |
| `actionUpdateQuantity` | Nach Änderungen der Produktmenge. | (Weniger wahrscheinlich für die Preishistorie, aber möglich für verwandte Logik). |
| `actionUpdateSpecificPrice` | Nach dem Hinzufügen/Aktualisieren eines spezifischen Preises (Rabatt). | Entscheidend für die Auslösung der Logik zur Berechnung und Anzeige des niedrigsten Preises. |
| `actionFrontControllerSetMedia` | Bevor ein Front-Controller seine Ausgabe rendert. | Bedingt Front-Office-CSS/JS basierend auf dem Seitenkontext hinzufügen. |
| `actionAdminControllerSetMedia` | Bevor ein Admin-Controller seine Ausgabe rendert. | Bedingt Back-Office-CSS/JS für Konfigurationsseiten hinzufügen. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul Omnibus-Richtlinie Pro besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
