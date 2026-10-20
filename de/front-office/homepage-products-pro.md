---
title: "Homepage Products Pro - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Homepage Products Pro von MyPresta.eu."
sidebar:
  label: "Homepage Products Pro - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Homepage Products Pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/homepage-products-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/homepage-products-pro/)
>
> ---


# Homepage Products Pro

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zur Hauptseite der Einstellungen für „Homepage Products Pro“. Hier steuern Sie das globale Verhalten und die Funktionen Ihrer Produktblöcke.

#### Allgemeine Einstellungen

- **Interne Tabs aktivieren**

  - **Was diese Einstellung bewirkt:** Dies steuert, ob das Modul eigene benutzerdefinierte Tabs auf der Homepage erstellen kann, ähnlich den standardmäßigen PrestaShop-Tabs „Beliebte Produkte“ oder „Neue Produkte“.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Sie können neue Produktblöcke erstellen, die als anklickbare Tabs auf Ihrer Homepage erscheinen, sodass Kunden zwischen verschiedenen Produktsammlungen wechseln können.
    - *Wenn deaktiviert (Nein):* Das Modul zeigt Produktblöcke nur als eigenständige Abschnitte an (z. B. horizontale Karussells oder Spaltenblöcke), ohne die Tab-Oberfläche.
  - **Empfohlener Wert:** **Ja** (um die volle Leistung des Moduls für dynamische Homepage-Inhalte zu nutzen).
  - **Händlerszenario / Beispiel:** Sie möchten „Neuheiten“, „Bestseller“ und „Saisonale Empfehlungen“ alle auf Ihrer Homepage anzeigen, ohne sie zu lang zu machen. Das Aktivieren interner Tabs ermöglicht es Ihnen, jedes davon in einen eigenen Tab zu legen.
- **Rich-Text-Editor verwenden**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob ein visueller (WYSIWYG) Editor verfügbar ist, wenn Sie Produktblockbeschreibungen oder -titel erstellen oder bearbeiten, was die Textformatierung erleichtert.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Sie erhalten einen benutzerfreundlichen Editor (wie TinyMCE) mit Formatierungsoptionen (fett, kursiv, Links usw.) für Textfelder innerhalb des Moduls.
    - *Wenn deaktiviert (Nein):* Sie haben ein einfaches Texteingabefeld, das die Verwendung von grundlegendem HTML erfordert, wenn Sie Formatierungen wünschen.
  - **Empfohlener Wert:** **Ja** (für einfachere Inhaltserstellung und bessere visuelle Kontrolle).
  - **Händlerszenario / Beispiel:** Sie möchten eine kurze, gestylte Einleitung über einem Produktblock hinzufügen, z. B. „Entdecken Sie unsere **exklusive** Kollektion!“ Der Rich-Text-Editor macht dies einfach.
- **LightSlider laden**

  - **Was diese Einstellung bewirkt:** Steuert, ob das Modul die LightSlider JavaScript-Bibliothek lädt, die zum Erstellen responsiver Inhaltskarussells und Slider verwendet wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Die LightSlider-Bibliothek wird geladen, sodass Ihre Produktblöcke als interaktive, berührungsempfindliche Karussells angezeigt werden können. Dies ist typischerweise für die visuellen Effekte des Moduls erforderlich.
    - *Wenn deaktiviert (Nein):* Die LightSlider-Bibliothek wird nicht geladen. Wenn Ihr Theme oder ein anderes Modul ähnliche Karussell-Funktionen bietet, könnten Sie dies deaktivieren, um Konflikte oder redundantes Laden zu vermeiden. Wenn jedoch keine andere Karussell-Lösung vorhanden ist, könnten Ihre Produktblöcke als statische Raster oder Listen angezeigt werden.
  - **Empfohlener Wert:** **Ja** (es sei denn, Sie haben einen spezifischen Grund oder Konflikt, da es für die Karussell-Funktionen des Moduls unerlässlich ist).
  - **Händlerszenario / Beispiel:** Sie möchten, dass Ihr „Neue Produkte“-Block ein schlankes, horizontal scrollendes Karussell ist. Diese Einstellung stellt sicher, dass das notwendige Skript für diese Funktionalität geladen wird.
- **Analyse aktivieren**

  - **Was diese Einstellung bewirkt:** Aktiviert oder deaktiviert die interne Verfolgung der Leistung von Produktblöcken durch das Modul, wie z. B. Ansichten und Klicks.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (Aktiviert):* Das Modul sammelt Daten darüber, wie oft Ihre Produktblöcke angesehen und geklickt werden, und liefert Einblicke in deren Effektivität.
    - *Wenn deaktiviert (Deaktiviert):* Es werden keine Leistungsdaten innerhalb des Modul-Dashboards gesammelt oder angezeigt.
  - **Empfohlener Wert:** **Aktiviert** (um wertvolle Einblicke zu erhalten, welche Produktblöcke am besten funktionieren).
  - **Händlerszenario / Beispiel:** Sie möchten wissen, ob Ihr „Bestseller“-Block mehr Engagement erhält als Ihr „Im Angebot“-Block. Das Aktivieren der Analyse liefert diese Daten.
- **Analysezeitraum**

  - **Was diese Einstellung bewirkt:** Definiert den Zeitraum, für den die internen Analysedaten des Moduls angezeigt werden.
  - **Auswirkung der Änderung dieser Einstellung:** Ändert den Bereich der in den Analyseberichten angezeigten Daten.
  - **Optionen:** Letzte 7 Tage, Letzte 30 Tage, Letzte 90 Tage, Letzte 180 Tage, Letzte 365 Tage.
  - **Empfohlener Wert:** **Letzte 30 Tage** (ein gutes Gleichgewicht für aktuelle Trends, aber passen Sie es an Ihre Berichterstattungsbedürfnisse an).
  - **Händlerszenario / Beispiel:** Sie möchten die Leistung Ihrer Homepage-Produktblöcke im letzten Monat überprüfen, um zu sehen, ob eine kürzliche Aktion Auswirkungen hatte.
- **Block-Cache aktivieren**

  - **Was diese Einstellung bewirkt:** Aktiviert einen Caching-Mechanismus für die vom Modul generierten Produktblöcke. Caching speichert eine temporäre Version des Blocks, sodass er nicht jedes Mal neu erstellt werden muss, wenn ein Kunde die Seite besucht.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Produktblöcke werden für Kunden schneller geladen, da der Server eine zwischengespeicherte Version bereitstellt. Dies kann die Seitenladezeiten und die Serverleistung erheblich verbessern, insbesondere bei stark frequentierten Shops.
    - *Wenn deaktiviert (Nein):* Produktblöcke werden bei jedem Seitenaufruf dynamisch generiert, was langsamer sein kann, aber sicherstellt, dass immer die absolut neuesten Produktdaten angezeigt werden (z. B. Lagerbestände, Preise).
  - **Empfohlener Wert:** **Ja** (für Leistungsvorteile, es sei denn, Sie haben sehr schnell wechselnde Produktdaten, die in Echtzeit sein müssen).
  - **Händlerszenario / Beispiel:** Ihre Homepage hat viel Traffic, und Sie möchten sicherstellen, dass sie so schnell wie möglich geladen wird. Das Aktivieren des Caches beschleunigt die Anzeige Ihrer Produktblöcke.
- **Cache TTL (Sekunden)**

  - **Was diese Einstellung bewirkt:** Definiert, wie lange (in Sekunden) eine zwischengespeicherte Version eines Produktblocks gültig bleibt, bevor sie aktualisiert wird. (TTL steht für „Time To Live“).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Höherer Wert:* Blöcke werden länger zwischengespeichert, was zu einer besseren Leistung führt, aber möglicherweise leicht veraltete Produktinformationen anzeigt (z. B. wenn sich ein Preis ändert, wird er möglicherweise erst auf der Homepage aktualisiert, wenn der Cache abläuft).
    - *Niedrigerer Wert:* Blöcke werden häufiger aktualisiert, was aktuellere Informationen gewährleistet, aber mit etwas geringerem Leistungsgewinn.
  - **Empfohlener Wert:** **3600** (1 Stunde) oder **7200** (2 Stunden) ist ein guter Ausgangspunkt. Passen Sie ihn an, wie oft sich Ihre Produktdaten ändern und wie kritisch Echtzeit-Updates sind.
  - **Händlerszenario / Beispiel:** Sie haben einen Flash-Sale, bei dem sich die Preise stündlich ändern. Sie könnten die Cache-TTL auf 3600 Sekunden (1 Stunde) einstellen, um sicherzustellen, dass die Preise auf der Homepage relativ schnell aktualisiert werden.
- **Theme automatisch erkennen**

  - **Was diese Einstellung bewirkt:** Versucht, Ihr aktives PrestaShop-Theme automatisch zu erkennen, um geeignete Stile und Template-Overrides für eine bessere visuelle Integration anzuwenden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Das Modul versucht, seine Ausgabe an die Struktur und das Styling Ihres Themes anzupassen, möglicherweise unter Verwendung themenspezifischer Templates (z. B. `firezy-products17.tpl`). Dies führt oft zu einem nahtloseren Erscheinungsbild.
    - *Wenn deaktiviert (Nein):* Das Modul verwendet seine Standard-, generischen Templates und Stile, die möglicherweise nicht perfekt zum Design Ihres Themes passen. Möglicherweise müssen Sie ein Theme manuell auswählen oder benutzerdefiniertes CSS anwenden.
  - **Empfohlener Wert:** **Ja** (für die beste sofortige visuelle Integration).
  - **Händlerszenario / Beispiel:** Sie haben das Modul installiert, und die Produktblöcke sehen mit Ihrem benutzerdefinierten Theme nicht ganz richtig aus. Das Aktivieren dieser Option könnte das Styling automatisch korrigieren.

#### Versteckte/Erweiterte Einstellungen (Interne Konfigurationsschlüssel)

Diese sind typischerweise nicht direkt als benutzerseitige Einstellungen verfügbar, sondern sind Konfigurationswerte, die das Modul intern verwendet. Sie werden hier zur Vollständigkeit und zum Verständnis des Entwicklers aufgeführt.

- `update_`, `mypresta_updates`: Bezogen auf Modul-Update-Prüfungen und Benachrichtigungen von MyPresta.eu.
- `hpp_analytics_enabled`: Entspricht der Einstellung „Analyse aktivieren“.
- `hpp_cache_enabled`: Entspricht der Einstellung „Block-Cache aktivieren“.
- `hpp_cache_ttl`: Entspricht der Einstellung „Cache TTL (Sekunden)“.
- `hpp_theme_auto_detect`: Entspricht der Einstellung „Theme automatisch erkennen“.
- `hpp_analytics_period`: Entspricht der Einstellung „Analysezeitraum“.
- `hpp_carousel_native`: Wahrscheinlich ein internes Flag für den Karusselltyp, möglicherweise im Zusammenhang mit LightSlider.
- `PS_NB_DAYS_NEW_PRODUCT`: PrestaShops Standardeinstellung, wie viele Tage ein Produkt als „neu“ gilt. Das Modul könnte dies für „Neue Produkte“-Blöcke verwenden.
- `PS_CURRENCY_DEFAULT`: PrestaShops Standardwährungs-ID.
- `hpp_internal_tabs`: Entspricht der Einstellung „Interne Tabs aktivieren“.
- `hpp_bxslider`: Eine ältere Karussell-Bibliothek, möglicherweise eine Legacy-Einstellung oder ein Fallback.
- `PS_LANG_DEFAULT`: PrestaShops Standardsprachen-ID.
- `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: PrestaShops Einstellung, die es Mitarbeitern erlaubt, die Formularsprache zu ändern.
- `hpp_rich_text`: Entspricht der Einstellung „Rich-Text-Editor verwenden“.
- `hpp_theme`: Speichert den erkannten oder manuell ausgewählten Themanamen.
- `hpp_customtplpath`: Ermöglicht die Angabe eines benutzerdefinierten Pfads für Templates, nützlich für die erweiterte Theme-Integration.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Das Modul „Homepage Products Pro“ erweitert das PrestaShop Back Office um einen speziellen Bereich zur Verwaltung Ihrer Produktblöcke.

- **Bildschirmname & Menüpfad:**

  - Sie finden einen neuen Menüpunkt, typischerweise unter **Module > Homepage Products Pro** oder einem ähnlichen Namen, der zum Dashboard des Moduls führt.
  - Dieses Dashboard ist der Ort, an dem Sie Ihre Produktblöcke erstellen, bearbeiten, löschen und organisieren.
- **Verfügbare Aktionen & Einstellungen:**

  - **Produkblock-Auflistungstabelle:** Diese Hauptansicht zeigt eine Liste aller von Ihnen erstellten Produktblöcke an. Jeder Eintrag zeigt:
    - **Name:** Der interne Name, den Sie dem Block gegeben haben (z. B. „Homepage Bestseller“).
    - **Titel:** Der öffentliche Titel, der den Kunden angezeigt wird (z. B. „Unsere Top-Auswahl!“).
    - **Hook:** Wo der Block angezeigt wird (z. B. `displayHome`, `displayHomeTabContent`, `displayLeftColumn`).
    - **Status:** Ob der Block aktiviert oder deaktiviert ist.
    - **Position:** Die Reihenfolge, in der Blöcke innerhalb desselben Hooks erscheinen.
    - **Aktionen:** Schaltflächen zum **Bearbeiten**, **Duplizieren** oder **Löschen** des Blocks.
  - **Schaltfläche „Neuen Block hinzufügen“:** Durch Klicken darauf wird ein Formular zum Erstellen eines brandneuen Produktblocks geöffnet.
  - **Formular „Block bearbeiten“:** Beim Hinzufügen oder Bearbeiten eines Blocks konfigurieren Sie typischerweise:
    - **Blockname:** Ein interner Bezeichner (z. B. „Sommerkollektion2023“).
    - **Anzeigetitel:** Der Titel, den Kunden sehen (z. B. „Sommerkollektion“).
    - **Beschreibung:** Ein kurzer Text, der über den Produkten erscheint (Rich-Text-Editor verfügbar, wenn aktiviert).
    - **Hook-Auswahl:** Wählen Sie, wo der Block erscheinen soll (z. B. `displayHome`, `displayHomeTabContent` für Tabs, `displayLeftColumn`).
    - **Produktauswahl:** Dies ist entscheidend. Sie definieren, *welche* Produkte im Block erscheinen. Optionen umfassen typischerweise:
      - **Spezifische Produkte:** Manuelles Auswählen einzelner Produkte mithilfe eines Suchwerkzeugs.
      - **Produkte aus Kategorie:** Wählen Sie eine oder mehrere Kategorien aus, und das Modul zeigt Produkte daraus an.
      - **Neue Produkte:** Automatische Anzeige der neuesten Produkte, die Ihrem Shop hinzugefügt wurden.
      - **Bestseller:** Automatische Anzeige der meistverkauften Produkte Ihres Shops.
      - **Produkte im Angebot:** Automatische Anzeige von Produkten, die derzeit im Angebot sind.
      - **Empfohlene Produkte:** Produkte, die als empfohlen markiert sind.
    - **Anzahl der anzuzeigenden Produkte:** Begrenzen Sie, wie viele Produkte angezeigt werden.
    - **Anzeigetyp:** Wählen Sie zwischen einem Karussell/Slider oder einem statischen Raster/einer Liste.
    - **Karussell-Einstellungen:** Bei Verwendung eines Karussells, Einstellungen für Artikel pro Folie, Autoplay, Navigationspfeile usw.
    - **Sichtbarkeit/Zielgruppen-Auswahl:** Definieren Sie, wer den Block sieht (z. B. alle Kunden, bestimmte Kundengruppen, bestimmte Länder).
    - **Sprachspezifität:** Konfigurieren Sie Titel und Beschreibungen für verschiedene Sprachen.
    - **Status:** Aktivieren/Deaktivieren des einzelnen Blocks.
    - **Position:** Legen Sie die Anzeigereihenfolge relativ zu anderen Blöcken im selben Hook fest.
- **Auswirkung von Änderungen:**

  - **Hinzufügen eines neuen Blocks:** Eine neue Produktanzeige erscheint in Ihrem Front-Office im gewählten Hook und zeigt die ausgewählten Produkte gemäß Ihren Einstellungen an.
  - **Bearbeiten eines Blocks:** Änderungen an Titeln, Beschreibungen, Produktauswahl, Anzeigetyp oder Einstellungen werden sofort im Front-Office widergespiegelt (vorbehaltlich der Cache-TTL, wenn Caching aktiviert ist).
  - **Löschen eines Blocks:** Die Produktanzeige wird aus Ihrem Front-Office entfernt.
  - **Ändern der Position:** Die Reihenfolge der Blöcke innerhalb eines bestimmten Hooks wird im Front-Office aktualisiert.
  - **Aktivieren/Deaktivieren:** Schaltet die Sichtbarkeit des Blocks in Ihrem Shop um.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**

  1. **Planen Sie Ihr Homepage-Layout:** Entscheiden Sie, welche Produkttypen Sie hervorheben möchten (neu, Bestseller, spezifische Kategorien, Aktionen).
  2. **Neue Blöcke erstellen:** Für jeden geplanten Abschnitt gehen Sie zum Dashboard des Moduls und klicken Sie auf „Neuen Block hinzufügen“.
  3. **Jeden Block konfigurieren:**
     - Geben Sie ihm einen klaren internen Namen (z. B. „HP\_Neuheiten“).
     - Schreiben Sie einen ansprechenden Anzeigetitel und eine Beschreibung.
     - Wählen Sie den entsprechenden Hook aus (z. B. `displayHome` für Hauptinhalt, `displayHomeTabContent` für Tabs).
     - Wählen Sie Ihre Produktauswahlmethode (manuell, Kategorie, neu, etc.).
     - Passen Sie Anzeige- und Karussell-Einstellungen an.
     - Legen Sie die Position fest, um die Reihenfolge zu steuern.
  4. **Im Front-Office überprüfen:** Überprüfen Sie immer die Homepage Ihres Shops, nachdem Sie Änderungen vorgenommen haben, um sicherzustellen, dass alles wie erwartet aussieht und funktioniert.
  5. **Analysen überwachen:** Überprüfen Sie regelmäßig die Analysen des Moduls (falls aktiviert), um zu verstehen, welche Blöcke gut funktionieren, und passen Sie Ihre Strategie entsprechend an.
  6. **Pflegen und aktualisieren:** Wenn neue Produkte eintreffen oder Aktionen sich ändern, aktualisieren Sie Ihre bestehenden Blöcke oder erstellen Sie neue, um Ihre Homepage frisch und relevant zu halten.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Hauptkonfiguration | Interne Tabs aktivieren | Ja | Ermöglicht die Erstellung von Produkt-Tabs auf der Homepage. |
| Hauptkonfiguration | Rich-Text-Editor verwenden | Ja | Bietet einen visuellen Editor für Textfelder. |
| Hauptkonfiguration | LightSlider laden | Ja | Aktiviert Produktkarussells/Slider. |
| Hauptkonfiguration | Analyse aktivieren | Aktiviert | Verfolgt Ansichten und Klicks für Produktblöcke. |
| Hauptkonfiguration | Analysezeitraum | Letzte 30 Tage | Legt den Zeitraum für Analyseberichte fest. |
| Hauptkonfiguration | Block-Cache aktivieren | Ja | Verbessert die Seitenladezeit durch Caching von Blöcken. |
| Hauptkonfiguration | Cache TTL (Sekunden) | 3600 (1 Stunde) | Wie lange zwischengespeicherte Blöcke gültig bleiben. |
| Hauptkonfiguration | Theme automatisch erkennen | Ja | Passt die Modulausgabe an Ihr Theme an. |
| Blockverwaltung | Blockname | N/A (Benutzerdefiniert) | Interner Bezeichner für Ihren Produktblock. |
| Blockverwaltung | Anzeigetitel | N/A (Benutzerdefiniert) | Öffentlicher Titel, der den Kunden angezeigt wird. |
| Blockverwaltung | Beschreibung | N/A (Benutzerdefiniert) | Text, der über dem Produktblock angezeigt wird. |
| Blockverwaltung | Hook-Auswahl | `displayHome` / `displayHomeTabContent` | Bestimmt, wo der Block im Shop erscheint. |
| Blockverwaltung | Produktauswahl | N/A (Benutzerdefiniert) | Definiert, welche Produkte angezeigt werden (manuell, Kategorie, neu, Bestseller usw.). |
| Blockverwaltung | Anzahl der Produkte | N/A (Benutzerdefiniert) | Begrenzt die Menge der angezeigten Produkte. |
| Blockverwaltung | Anzeigetyp | Karussell / Raster | Wie Produkte visuell präsentiert werden. |
| Blockverwaltung | Sichtbarkeit/Zielgruppe | Alle Kunden | Beschränkt die Blocksichtbarkeit auf bestimmte Gruppen/Länder. |
| Blockverwaltung | Status | Aktiviert | Schaltet die Sichtbarkeit des Blocks im Front-Office um. |
| Blockverwaltung | Position | N/A (Benutzerdefiniert) | Legt die Anzeigereihenfolge der Blöcke innerhalb eines Hooks fest. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Produktblöcke werden nicht auf der Homepage angezeigt oder sehen fehlerhaft aus.**

- **A:**
  1. **Modulstatus prüfen:** Stellen Sie sicher, dass das Modul „Homepage Products Pro“ unter **Module > Modul-Manager** aktiviert ist.
  2. **Blockstatus prüfen:** Gehen Sie zum Konfigurations-Dashboard des Moduls und überprüfen Sie, ob die von Ihnen erstellten Produktblöcke „Aktiviert“ sind.
  3. **Hook-Auswahl:** Überprüfen Sie nochmals, ob Sie die Blöcke den richtigen Front-Office-Hooks zugewiesen haben (z. B. `displayHome` für den Hauptinhalt, `displayHomeTabContent` für Tabs, `displayLeftColumn` für Spalten).
  4. **Cache leeren:** Gehen Sie zu **Erweiterte Parameter > Leistung** und klicken Sie auf „Cache leeren“. Manchmal verhindert alter Cache-Inhalt, dass neue Modulausgaben angezeigt werden.
  5. **Theme-Kompatibilität:** Wenn Sie ein benutzerdefiniertes Theme haben, versuchen Sie, „Theme automatisch erkennen“ in der Hauptkonfiguration des Moduls zu aktivieren. Wenn die Probleme weiterhin bestehen, benötigt Ihr Theme möglicherweise kleinere CSS-Anpassungen (siehe F3).

**F2: Meine Produktblöcke werden angezeigt, aber die Produkte werden nicht aktualisiert (z. B. alte Preise, nicht vorrätige Artikel sind immer noch sichtbar).**

- **A:** Dies ist normalerweise ein Caching-Problem.
  1. **Modul-Cache:** Überprüfen Sie in der Hauptkonfiguration des Moduls „Block-Cache aktivieren“ und „Cache TTL (Sekunden)“. Wenn Caching aktiviert ist, zeigt der Block möglicherweise eine ältere, zwischengespeicherte Version an. Sie können das Caching vorübergehend deaktivieren, speichern und dann wieder aktivieren, oder einfach warten, bis die TTL abläuft.
  2. **PrestaShop-Cache:** Gehen Sie zu **Erweiterte Parameter > Leistung** und klicken Sie auf „Cache leeren“. Dadurch werden alle PrestaShop-Caches gelöscht.
  3. **Browser-Cache:** Leeren Sie den Cache und die Cookies Ihres Browsers oder sehen Sie sich Ihre Website in einem Inkognito-/privaten Fenster an, um sicherzustellen, dass Sie keine lokal zwischengespeicherte Version sehen.

**F3: Die Produktblöcke erscheinen, aber das Styling ist fehlerhaft (z. B. falsche Schriftarten, falsch ausgerichtete Elemente, defektes Karussell).**

- **A:**
  1. **Theme automatisch erkennen:** Stellen Sie in der Hauptkonfiguration des Moduls sicher, dass „Theme automatisch erkennen“ aktiviert ist. Dies hilft dem Modul, themenspezifisches Styling zu verwenden.
  2. **LightSlider laden:** Wenn Karussells defekt sind, stellen Sie sicher, dass „LightSlider laden“ in der Modulkonfiguration aktiviert ist.
  3. **Theme-Konflikte:** Benutzerdefinierte Themes haben manchmal widersprüchliches CSS oder JavaScript. Wenn Sie dies vermuten, versuchen Sie, vorübergehend zu einem Standard-PrestaShop-Theme (wie Classic) zu wechseln, um zu sehen, ob das Problem behoben wird. Wenn ja, benötigt Ihr benutzerdefiniertes Theme Anpassungen.
  4. **Benutzerdefiniertes CSS:** Möglicherweise müssen Sie benutzerdefiniertes CSS zu Ihrem Theme-Stylesheet hinzufügen, um die Standardstile des Moduls zu überschreiben und Ihrem Theme anzupassen. Ein Webentwickler kann Ihnen dabei helfen.

**F4: Ich habe einen neuen Produktblock erstellt, aber er wird nicht als Tab auf der Homepage angezeigt.**

- **A:**
  1. **Interne Tabs aktivieren:** Stellen Sie in der Hauptkonfiguration des Moduls sicher, dass „Interne Tabs aktivieren“ auf „Ja“ eingestellt ist.
  2. **Korrekter Hook:** Stellen Sie sicher, dass die **Hook-Auswahl** des Produktblocks auf `displayHomeTabContent` eingestellt ist. Blöcke, die auf `displayHome` oder Spalten eingestellt sind, werden nicht als Tabs angezeigt.
  3. **Positionierung:** Überprüfen Sie die Position Ihrer Tab-Blöcke. Wenn sie in der Reihenfolge sehr niedrig sind, werden sie möglicherweise nicht angezeigt, wenn andere Module Platz beanspruchen.

**F5: Mein Rich-Text-Editor funktioniert nicht, oder ich kann keinen Text formatieren.**

- **A:**
  1. **Rich-Text-Editor aktivieren:** Stellen Sie in der Hauptkonfiguration des Moduls sicher, dass „Rich-Text-Editor verwenden“ auf „Ja“ eingestellt ist.
  2. **Browser-Probleme:** Versuchen Sie einen anderen Webbrowser oder leeren Sie den Cache Ihres aktuellen Browsers.
  3. **JavaScript-Konflikte:** Gelegentlich können andere Module oder Theme-Skripte den Rich-Text-Editor stören. Wenn das Problem weiterhin besteht, konsultieren Sie einen Entwickler.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen tiefen Einblick in die technische Architektur und den Code des Moduls „Homepage Products Pro“, konzipiert für Entwickler, Webmaster und technische Agenturen.

### 4.1 Architekturübersicht

Das Modul „Homepage Products Pro“ (`hpp`) folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich Hooks für die Front-Office-Anzeige und eine `getContent()`-Methode für die Back-Office-Konfiguration nutzt. Es implementiert ein benutzerdefiniertes Dashboard zur Verwaltung von Produktblöcken, die als Konfigurationswerte oder potenziell in benutzerdefinierten Datenbanktabellen gespeichert werden (obwohl keine expliziten `ObjectModel`-Klassen im bereitgestellten Inventar identifiziert wurden, werden komplexe Daten oft in `ps_configuration` serialisiert oder über Hilfsklassen verwaltet). Das Modul stützt sich stark auf Smarty-Templates für die Darstellung seiner verschiedenen Produktblöcke und Admin-Oberflächen. Es integriert externe Bibliotheken wie LightSlider für Karussells und TinyMCE für die Rich-Text-Bearbeitung. Analyse- und Caching-Mechanismen sind für Leistung und Einblicke integriert.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `hpp/controllers/front/index.php`
  - **Klassenname:** `HppIndexModuleFrontController` (wahrscheinlich, basierend auf der Dateinamenskonvention)
  - **Elternklasse:** `ModuleFrontController`
  - **Verantwortlichkeit:** Dieser Controller dient wahrscheinlich als allgemeiner Einstiegspunkt für Front-Office-Modulaktionen, die nicht in spezifische AJAX- oder Tracking-Kategorien passen. Er könnte das anfängliche Laden von Daten oder das Rendern spezifischer Blocktypen handhaben, wenn dies nicht vollständig hook-gesteuert ist.
- `hpp/controllers/front/lazyblock.php`
  - **Klassenname:** `HppLazyblockModuleFrontController`
  - **Elternklasse:** `ModuleFrontController`
  - **Verantwortlichkeit:** Dieser Controller ist für die Bearbeitung von AJAX-Anfragen zum Lazy-Loading von Produktblöcken konzipiert. Wenn ein Benutzer scrollt oder mit einem Tab interagiert, würde dieser Controller aufgerufen, um Produktdaten abzurufen und das HTML für einen bestimmten Block zu rendern, wodurch die anfänglichen Seitenladezeiten verbessert werden. Er nimmt wahrscheinlich Parameter wie Block-ID, Seitenzahl oder Filterkriterien entgegen.
- `hpp/controllers/front/track.php`
  - **Klassenname:** `HppTrackModuleFrontController`
  - **Elternklasse:** `ModuleFrontController`
  - **Verantwortlichkeit:** Dieser Controller ist für die Bearbeitung von Analyse-Tracking-Anfragen verantwortlich. Wenn ein Produktblock angesehen oder ein Produkt innerhalb eines Blocks angeklickt wird, wird eine Anfrage an diesen Controller gesendet, um das Ereignis aufzuzeichnen, was zu den internen Analysedaten des Moduls beiträgt.

#### Back-Office-Admin-Controller

Es wurden keine dedizierten `AdminController`-Dateien im bereitgestellten Inventar identifiziert. Dies deutet darauf hin, dass die Back-Office-Verwaltung des Moduls (Erstellen/Bearbeiten von Produktblöcken) direkt innerhalb der `getContent()`-Methode der Datei `hpp.php` gehandhabt wird, möglicherweise unter Verwendung der PrestaShop-Klassen `HelperForm` und `HelperList` oder eines benutzerdefinierten Rendering-Ansatzes innerhalb der Hauptkonfigurationsseite des Moduls.

### 4.3 Kernklassen & Modelle (`classes/`)

Es wurden keine benutzerdefinierten PHP-Klassen, die `ObjectModel` oder andere Kernfunktionen erweitern, explizit im Verzeichnis `classes/` aufgeführt. Dies impliziert, dass:

- Komplexe Daten (wie individuelle Produktblockkonfigurationen) wahrscheinlich als serialisierte Arrays oder JSON-Strings in der Tabelle `ps_configuration` gespeichert werden, die direkt von der Moduldatei `hpp.php` verwaltet wird.
- Alternativ könnte das Modul einen prozeduraleren Ansatz verwenden oder sich auf Hilfsklassen verlassen, die direkt in `hpp.php` oder seinen enthaltenen Bibliotheken definiert sind.
- Das Verzeichnis `lib/` enthält verschiedene Hilfsklassen und externe Bibliotheken (z. B. `searchTool`, `smartyTemplatesManager`, `src`). Diese werden wahrscheinlich für spezifische Funktionen wie Produktsuche, Template-Verwaltung oder Karussell-Implementierung verwendet, anstatt Kern-Geschäftsentitäten zu definieren.

### 4.4 JavaScript-Assets (`views/js/`)

- `hpp/js/script.js`
  - **Umfang:** Front-Office.
  - **Details:** Enthält wahrscheinlich die Haupt-Front-Office-Logik zum Initialisieren von Produktkarussells (LightSlider), zum Umschalten von Tabs und für allgemeine UI-Interaktionen im Zusammenhang mit den Produktblöcken. Es könnte auch Logik für Lazy Loading oder grundlegendes Analyse-Tracking enthalten.
- `hpp/js/tinymce16-force-urls.inc.js`
  - **Umfang:** Back-Office.
  - **Details:** Ein spezifisches Skript für den TinyMCE Rich-Text-Editor, wahrscheinlich um sicherzustellen, dass URLs im Editor korrekt behandelt und formatiert werden, insbesondere in älteren PrestaShop 1.6-Kontexten.
- `hpp/lib/searchTool/views/js/autocomplete.js`
  - **Umfang:** Back-Office.
  - **Details:** Bietet die JavaScript-Funktionalität für ein Autocomplete-Suchfeld, das beim Auswählen spezifischer Produkte für einen Produktblock in der Back-Office-Konfiguration verwendet wird. Es führt wahrscheinlich AJAX-Aufrufe durch, um Produktvorschläge abzurufen.
- `hpp/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`
  - **Umfang:** Back-Office.
  - **Details:** Verwaltet die dynamische Erstellung, Bearbeitung und Auswahl von Smarty-Templates innerhalb der Back-Office-Oberfläche, wahrscheinlich für fortgeschrittene Benutzer zur Anpassung von Blocklayouts.
- `hpp/lib/src/js/lightslider.js`
  - **Umfang:** Front-Office.
  - **Details:** Die Kern-LightSlider-Bibliothek, verantwortlich für die Erstellung responsiver, berührungsempfindlicher Inhaltskarussells für die Produktblöcke. Sie handhabt Folienübergänge, Navigation und Responsivität.
- `hpp/views/js/admin-audience-picker.js`
  - **Umfang:** Back-Office.
  - **Details:** Bietet die interaktive Logik für die „Zielgruppen-Auswahl“-Oberfläche im Back-Office, die es Administratoren ermöglicht, spezifische Kundengruppen oder Länder für die Blocksichtbarkeit auszuwählen.
- `hpp/views/js/adminHppDashboard.js`
  - **Umfang:** Back-Office.
  - **Details:** Das Haupt-JavaScript für das Back-Office-Dashboard des Moduls, das Interaktionen wie das Hinzufügen/Bearbeiten von Blöcken, Drag-and-Drop-Neuanordnung und allgemeine UI-Verwaltung handhabt.
- `hpp/views/js/adminHppDashboardDemo.js`
  - **Umfang:** Back-Office.
  - **Details:** Enthält wahrscheinlich demo-spezifisches JavaScript für das Back-Office-Dashboard, möglicherweise für die Erstkonfiguration oder zur Präsentation von Funktionen, und ist möglicherweise in einer Produktionsumgebung nicht aktiv.
- `hpp/views/js/hpp-analytics.js`
  - **Umfang:** Front-Office.
  - **Details:** Handhabt die Front-Office-Seite des Analyse-Trackings, sendet Daten (z. B. Blockansichten, Produktklicks) über AJAX an den `track.php`-Controller.
- `hpp/views/js/hpp-lazyload.js`
  - **Umfang:** Front-Office.
  - **Details:** Implementiert Lazy Loading für Produktblöcke oder deren Inhalt, indem AJAX-Aufrufe an `lazyblock.php` gesendet werden, wenn Blöcke in den Viewport gelangen oder Tabs aktiviert werden.

### 4.5 CSS-Stylesheets (`views/css/`)

- `hpp/css/global.css`
  - **Umfang:** Front-Office.
  - **Details:** Enthält allgemeine, globale Stile für die Front-Office-Ausgabe des Moduls, um eine grundlegende visuelle Konsistenz zu gewährleisten.
- `hpp/css/homefeaturedslider.css`
  - **Umfang:** Front-Office.
  - **Details:** Spezifische Stile für die Home-Featured-Slider-Komponente, wahrscheinlich für ältere PrestaShop-Versionen oder spezifische Karussell-Implementierungen.
- `hpp/css/hpp.css`
  - **Umfang:** Front-Office.
  - **Details:** Das Haupt-Front-Office-Stylesheet für das Modul, das das Aussehen und Verhalten von Produktblöcken, Rastern und Karussells definiert.
- `hpp/css/internal-tabs.css`
  - **Umfang:** Front-Office.
  - **Details:** Stile speziell für die interne Tab-Oberfläche auf der Homepage, einschließlich Tab-Navigation und Inhaltsbereichen.
- `hpp/css.css`
  - **Umfang:** Front-Office.
  - **Details:** Potenziell ein älteres oder zusätzliches allgemeines Stylesheet.
- `hpp/lib/searchTool/views/css/autocomplete.css`
  - **Umfang:** Back-Office.
  - **Details:** Stile für das Autocomplete-Suchfeld, das im Back-Office für die Produktauswahl verwendet wird.
- `hpp/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`
  - **Umfang:** Back-Office.
  - **Details:** Stile für die Smarty-Template-Manager-Oberfläche im Back-Office.
- `hpp/lib/src/css/lightslider.css`
  - **Umfang:** Front-Office.
  - **Details:** Das Kern-CSS für die LightSlider-Bibliothek, das die Basisstile für die Karussell-Komponente bereitstellt.
- `hpp/views/css/admin-audience-picker.css`
  - **Umfang:** Back-Office.
  - **Details:** Stile für die Zielgruppen-Auswahl-Oberfläche im Back-Office.
- `hpp/views/css/admin-searchtool.css`
  - **Umfang:** Back-Office.
  - **Details:** Zusätzliche Stile für das Suchwerkzeug im Admin-Panel.
- `hpp/views/css/admin_hpp.css`
  - **Umfang:** Back-Office.
  - **Details:** Das primäre Stylesheet für die Back-Office-Konfiguration und das Dashboard des Moduls.
- `hpp/views/templates/admin/css/css.css`
  - **Umfang:** Back-Office.
  - **Details:** Ein Stylesheet, das speziell im Admin-Templates-Verzeichnis liegt, wahrscheinlich für sehr spezifische Styling-Anforderungen innerhalb dieser Templates.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

Diese Templates werden gerendert, wenn das Modul an bestimmten Positionen im Front-Office eingehängt wird. Viele sind themenspezifische Überschreibungen.

- `hpp/views/templates/hook/column17.tpl`
  - **Hook:** `displayLeftColumn`, `displayRightColumn` (PrestaShop 1.7.x+).
  - **Ausgabe:** Rendert einen Produktblock, der für die linke oder rechte Spalte konzipiert ist, typischerweise eine vertikale Liste oder ein kleines Raster.
- `hpp/views/templates/hook/firezy-column17.tpl`
  - **Hook:** `displayLeftColumn`, `displayRightColumn` (PrestaShop 1.7.x+ für Firezy-Theme).
  - **Ausgabe:** Themenspezifische Überschreibung für Spalten-Produktblöcke, zugeschnitten auf das Firezy-Theme.
- `hpp/views/templates/hook/firezy-homeTab.tpl`
  - **Hook:** `displayHomeTab` (für Firezy-Theme).
  - **Ausgabe:** Rendert den eigentlichen Tab-Navigationslink (z. B. „Sommerkollektion“) für das Firezy-Theme.
- `hpp/views/templates/hook/firezy-homeTabContent.tpl`
  - **Hook:** `displayHomeTabContent` (für Firezy-Theme).
  - **Ausgabe:** Rendert den Inhalt (den Produktblock selbst), der erscheint, wenn ein bestimmter Tab aktiv ist, zugeschnitten auf das Firezy-Theme.
- `hpp/views/templates/hook/firezy-internal-tabs.tpl`
  - **Hook:** `displayHome` (für Firezy-Theme).
  - **Ausgabe:** Rendert die gesamte interne Tab-Oberfläche (sowohl Navigation als auch Inhalts-Wrapper) für das Firezy-Theme.
- `hpp/views/templates/hook/firezy-products17.tpl`
  - **Hook:** `displayHome` (für Firezy-Theme).
  - **Ausgabe:** Rendert einen allgemeinen Produktblock (Karussell oder Raster) für den Haupt-Homepage-Inhaltsbereich, zugeschnitten auf das Firezy-Theme.
- `hpp/views/templates/hook/homeTab.tpl`
  - **Hook:** `displayHomeTab`.
  - **Ausgabe:** Rendert den generischen Tab-Navigationslink.
- `hpp/views/templates/hook/homeTabContent.tpl`
  - **Hook:** `displayHomeTabContent`.
  - **Ausgabe:** Rendert den generischen Inhalt für einen Tab-Produktblock.
- `hpp/views/templates/hook/hummingbird-column17.tpl`, `hummingbird-homeTab.tpl`, `hummingbird-homeTabContent.tpl`, `hummingbird-internal-tabs.tpl`, `hummingbird-products17.tpl`
  - **Hook:** Ähnlich wie Firezy sind dies themenspezifische Überschreibungen für das Hummingbird-Theme, die maßgeschneiderte Layouts für Spalten, Tab-Navigation, Tab-Inhalt, interne Tab-Wrapper und allgemeine Produktblöcke bereitstellen.
- `hpp/views/templates/hook/internal-tabs.tpl`
  - **Hook:** `displayHome`.
  - **Ausgabe:** Rendert die generische interne Tab-Oberfläche (Navigation und Inhalts-Wrapper).
- `hpp/views/templates/hook/products17.tpl`
  - **Hook:** `displayHome`, `displayTopColumn`.
  - **Ausgabe:** Rendert einen generischen Produktblock (Karussell oder Raster) für den Haupt-Homepage- oder Top-Spalten-Inhaltsbereich (PrestaShop 1.7.x+).
- `hpp/views/templates/hook/warehouse-column17.tpl`, `warehouse-homeTab.tpl`, `warehouse-homeTabContent.tpl`, `warehouse-internal-tabs.tpl`, `warehouse-products17.tpl`
  - **Hook:** Ähnlich wie Firezy und Hummingbird sind dies themenspezifische Überschreibungen für das Warehouse-Theme, die maßgeschneiderte Layouts für Spalten, Tab-Navigation, Tab-Inhalt, interne Tab-Wrapper und allgemeine Produktblöcke bereitstellen.

#### Admin-Templates (`views/templates/admin/`)

Diese Templates werden für die Back-Office-Oberfläche des Moduls verwendet.

- `hpp/views/templates/admin/audience-picker.tpl`
  - **Ausgabe:** Rendert das HTML für die Kunden- und Länderauswahl-Oberfläche.
- `hpp/views/templates/admin/country-priority-picker.tpl`
  - **Ausgabe:** Rendert das HTML zum Auswählen und Priorisieren von Ländern.
- `hpp/views/templates/admin/menu.tpl`
  - **Ausgabe:** Rendert das modulspezifische Menü oder die Navigation innerhalb seines Back-Office-Dashboards.
- `hpp/views/templates/admin/scripts.tpl`
  - **Ausgabe:** Enthält JavaScript-Dateien oder Inline-Skripte speziell für die Admin-Oberfläche.
- `hpp/views/templates/admin/ul-li.tpl`
  - **Ausgabe:** Ein generisches Listen-Template, möglicherweise zur Anzeige von Listen von Elementen oder Optionen innerhalb der Admin-Formulare.

#### Bibliotheks-Templates (`hpp/lib/`)

Diese Templates sind Teil integrierter Bibliotheken.

- `hpp/lib/searchTool/views/scripts.tpl`
  - **Ausgabe:** Enthält JavaScript-Dateien oder Inline-Skripte für die Suchwerkzeug-Funktionalität.
- `hpp/lib/smartyTemplatesManager/tpl/example.tpl`
  - **Ausgabe:** Ein Beispiel-Template für den Smarty Templates Manager, wahrscheinlich zur Demonstration oder als Basis.
- `hpp/lib/smartyTemplatesManager/views/buttonManager.tpl`
  - **Ausgabe:** Rendert Schaltflächen oder Steuerelemente zur Verwaltung von Templates.
- `hpp/lib/smartyTemplatesManager/views/createTemplateForm.tpl`
  - **Ausgabe:** Rendert das Formular zum Erstellen neuer benutzerdefinierter Templates.
- `hpp/lib/smartyTemplatesManager/views/editTemplateForm.tpl`
  - **Ausgabe:** Rendert das Formular zum Bearbeiten bestehender benutzerdefinierter Templates.
- `hpp/lib/smartyTemplatesManager/views/mainForm.tpl`
  - **Ausgabe:** Das Hauptformular für die Smarty Templates Manager-Oberfläche.
- `hpp/lib/smartyTemplatesManager/views/selectInput.tpl`
  - **Ausgabe:** Rendert ein generisches Auswahl-/Dropdown-Eingabefeld.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Es wurden keine benutzerdefinierten SQL-Dateien (`.sql`) identifiziert und keine `ObjectModel`-Klassen aufgeführt. Dies deutet stark darauf hin, dass das Modul seine Konfigurationsdaten und Produktblockdefinitionen hauptsächlich in der PrestaShop-Tabelle `ps_configuration` speichert.

- **`ps_configuration`**: Diese Tabelle enthält Einträge mit Schlüsseln wie `HPP_ANALYTICS_ENABLED`, `HPP_CACHE_TTL`, `HPP_BLOCKS_DATA` (oder ähnliches, wobei `HPP_BLOCKS_DATA` ein serialisiertes Array oder einen JSON-String aller Produktblockkonfigurationen enthalten würde).

#### Registrierte Hooks-Tabelle

Das Modul registriert sich bei verschiedenen PrestaShop-Hooks, um seine Inhalte und Funktionen einzufügen.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | CSS- und JS-Assets injizieren (z. B. LightSlider, `hpp.css`, `script.js`). |
| `actionFrontControllerSetMedia` | Bevor ein Front-Controller seine Ausgabe rendert. | Spezifische CSS/JS-Assets bedingt basierend auf der Seite oder dem Controller hinzufügen. |
| `displayHome` | Hauptinhaltsbereich der Homepage. | Allgemeine Produktblöcke (Karussells, Raster) direkt auf der Homepage rendern. |
| `displayHomeTab` | Innerhalb des Homepage-Tab-Navigationsbereichs. | Die Navigationslinks für benutzerdefinierte Produkt-Tabs rendern. |
| `displayHomeTabContent` | Innerhalb des Homepage-Tab-Inhaltsbereichs. | Die eigentlichen Produktblöcke rendern, die erscheinen, wenn ein benutzerdefinierter Tab aktiv ist. |
| `displayLeftColumn` | In der linken Spalte von Seiten, auf denen sie aktiv ist. | Vertikale Produktblöcke in der linken Seitenleiste rendern. |
| `displayRightColumn` | In der rechten Spalte von Seiten, auf denen sie aktiv ist. | Vertikale Produktblöcke in der rechten Seitenleiste rendern. |
| `displayTopColumn` | Im oberen Inhaltsbereich, normalerweise unterhalb des Headers. | Produktblöcke im oberen Bereich der Homepage rendern. |
| `displayBackOfficeHeader` | Im `<head>`-Bereich jeder Back-Office-Seite. | CSS- und JS-Assets für die Back-Office-Konfigurationsseiten des Moduls injizieren. |
| `actionAdminControllerSetMedia` | Bevor ein Admin-Controller seine Ausgabe rendert. | Spezifische CSS/JS-Assets für die Admin-Seiten des Moduls hinzufügen. |
| `actionProductUpdate` | Nachdem ein Produkt im Back-Office aktualisiert wurde. | Potenziell den Cache für Blöcke, die dieses Produkt enthalten, leeren oder Produktdaten neu indizieren. |
| `actionProductDelete` | Nachdem ein Produkt im Back-Office gelöscht wurde. | Potenziell den Cache für Blöcke, die dieses Produkt enthalten, leeren oder es aus Blockkonfigurationen entfernen. |
| `actionCategoryUpdate` | Nachdem eine Kategorie im Back-Office aktualisiert wurde. | Potenziell den Cache für Blöcke leeren, die Produkte aus dieser Kategorie anzeigen. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Homepage Products Pro“ besuchen Sie bitte Ihr Kundenkonto bei MyPresta.eu. Unser engagiertes Support-Team steht Ihnen bei technischen Problemen oder Fragen gerne zur Verfügung.

- **MyPresta.eu Bestellhistorie & Downloads:** <https://mypresta.eu/my-account/orders/>
- **MyPresta.eu Support-Kontakt:** <https://mypresta.eu/contact>
