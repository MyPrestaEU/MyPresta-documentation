---
title: "TikTok Katalog-Feed – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul TikTok Katalog-Feed von MyPresta.eu."
sidebar:
  label: "TikTok Katalog-Feed – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul TikTok Catalog Feed auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/tiktok-catalog-feed.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/tiktok-catalog-feed/)
>
> ---


# TikTok Katalog-Feed

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Stellen Sie sicher, dass Ihr Server die Generierung potenziell großer XML/CSV-Dateien verarbeiten kann, falls Sie einen sehr umfangreichen Katalog haben.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Das TikTok Katalog-Feed-Modul bietet einen dedizierten Bereich in Ihrem PrestaShop Back Office zur Verwaltung Ihrer Produkt-Feeds.

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dieser anfängliche Konfigurationsbildschirm ermöglicht es Ihnen, die grundlegenden Parameter für Ihren TikTok-Feed einzurichten.

- **Modul aktivieren:**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter zum Aktivieren oder Deaktivieren der Modulfunktionalität.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul ist aktiv und ermöglicht Ihnen das Generieren und Verwalten von TikTok-Produkt-Feeds.
    - *Wenn deaktiviert:* Das Modul funktioniert nicht mehr, und es können keine Feeds generiert oder abgerufen werden.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Sie würden dies aktivieren, wenn Sie bereit sind, TikTok Ads zu nutzen. Sie könnten es vorübergehend deaktivieren, wenn Sie Wartungsarbeiten durchführen oder Ihre TikTok-Werbekampagnen stoppen müssen.
- **Feed-Generierungstyp:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob das Modul eine CSV- (Comma Separated Values) oder XML-Datei (Extensible Markup Language) für Ihren Produkt-Feed generiert. TikTok unterstützt im Allgemeinen beides.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf CSV eingestellt:* Die generierte Feed-URL liefert eine CSV-Datei.
    - *Wenn auf XML eingestellt:* Die generierte Feed-URL liefert eine XML-Datei.
  - **Empfohlener Wert:** XML (oft wegen seiner strukturierten Natur bevorzugt, aber CSV funktioniert für TikTok genauso gut).
  - **Händlerszenario / Beispiel:** Wenn die TikTok-Dokumentation oder Ihre Werbeagentur ein bestimmtes Format empfiehlt, wählen Sie dieses. Andernfalls funktionieren beide.
- **Standardsprache für Feed:**

  - **Was diese Einstellung bewirkt:** Wählt die primäre Sprache für die Produktdaten in Ihrem Feed aus. Dies ist entscheidend für die Ausrichtung auf bestimmte Märkte auf TikTok.
  - **Auswirkung der Änderung dieser Einstellung:** Die Produkttitel, Beschreibungen und andere sprachabhängige Felder im Feed werden aus Ihrem PrestaShop-Shop in der gewählten Sprache abgerufen.
  - **Empfohlener Wert:** Die Sprache Ihrer primären Zielgruppe auf TikTok (z. B. Englisch für einen US-Markt, Französisch für einen französischen Markt).
  - **Händlerszenario / Beispiel:** Wenn Sie Kunden in Deutschland ansprechen, würden Sie hier „Deutsch“ auswählen, um sicherzustellen, dass Ihre Produktinformationen auf TikTok korrekt in deren Sprache angezeigt werden.
- **Standardwährung für Feed:**

  - **Was diese Einstellung bewirkt:** Wählt die Währung aus, die für alle Produktpreise in Ihrem Feed verwendet wird. Dies sollte mit der Währung Ihres Zielmarktes übereinstimmen.
  - **Auswirkung der Änderung dieser Einstellung:** Alle Preise im Feed werden in die ausgewählte Währung umgerechnet oder angezeigt.
  - **Empfohlener Wert:** Die Währung Ihrer primären Zielgruppe auf TikTok (z. B. USD für einen US-Markt, EUR für einen europäischen Markt).
  - **Händlerszenario / Beispiel:** Wenn Ihre TikTok-Anzeigen Kunden in Großbritannien ansprechen, würden Sie „GBP“ auswählen, um sicherzustellen, dass die Preise in Britischen Pfund angezeigt werden.
- **Standardland für den Versand:**

  - **Was diese Einstellung bewirkt:** Legt das Standardland fest, das für die Berechnung der Versandkosten und der Verfügbarkeit im Feed verwendet wird. Dies ist wichtig, damit TikTok versteht, wohin Ihre Produkte versendet werden können.
  - **Auswirkung der Änderung dieser Einstellung:** Die Versandinformationen im Feed basieren auf den Versandregeln des ausgewählten Landes, die in Ihrem PrestaShop-Shop konfiguriert sind.
  - **Empfohlener Wert:** Ihr primäres Versandzielland.
  - **Händlerszenario / Beispiel:** Wenn die meisten Ihrer Verkäufe innerhalb Frankreichs erfolgen, würden Sie hier „Frankreich“ auswählen.
- **Nicht vorrätige Produkte einschließen:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob Produkte, die in Ihrem PrestaShop-Shop derzeit als „nicht vorrätig“ gekennzeichnet sind, in den TikTok-Feed aufgenommen werden sollen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Nicht vorrätige Produkte erscheinen im Feed, typischerweise mit dem Status „nicht verfügbar“.
    - *Wenn deaktiviert:* Nicht vorrätige Produkte werden vollständig aus dem Feed ausgeschlossen.
  - **Empfohlener Wert:** NEIN (es sei denn, Sie haben eine spezifische Strategie für Vorbestellungen oder Benachrichtigungen bei Wiederverfügbarkeit).
  - **Händlerszenario / Beispiel:** Im Allgemeinen möchten Sie in Ihren Anzeigen nur verfügbare Produkte anzeigen, um Kundenfrustration zu vermeiden. Wenn Sie eine lange Lieferzeit für kundenspezifische Produkte haben, könnten Sie diese aufnehmen, aber als „Vorbestellung“ kennzeichnen.
- **Spezifische Kategorien ausschließen:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, bestimmte Produktkategorien aus Ihrem PrestaShop-Shop auszuwählen, die NICHT im TikTok-Feed erscheinen sollen.
  - **Auswirkung der Änderung dieser Einstellung:** Produkte, die zu den ausgewählten Kategorien gehören, werden aus dem generierten Feed weggelassen.
  - **Empfohlener Wert:** Abhängig von Ihrem Shop.
  - **Händlerszenario / Beispiel:** Sie könnten Kategorien wie „Geschenkkarten“ oder „Dienstleistungen“ ausschließen, wenn es sich nicht um physische Produkte handelt, die für TikTok Katalog-Anzeigen geeignet sind. Oder, wenn Sie eine reine B2B-Kategorie haben, würden Sie diese von kundenorientierten Anzeigen ausschließen.
- **Spezifische Produkte ausschließen:**

  - **Was diese Einstellung bewirkt:** Bietet eine Möglichkeit, einzelne Produkte manuell auszuwählen, die aus dem TikTok-Feed ausgeschlossen werden sollen, unabhängig von ihrer Kategorie.
  - **Auswirkung der Änderung dieser Einstellung:** Die ausgewählten Produkte werden nicht in den Feed aufgenommen.
  - **Empfohlener Wert:** Abhängig von Ihrem Shop.
  - **Händlerszenario / Beispiel:** Sie könnten ein Produkt ausschließen, das Teil eines zeitlich begrenzten Flash-Sales ist, den Sie nicht auf TikTok bewerben möchten, oder ein Produkt, das rechtliche Beschränkungen für die Werbung in bestimmten Regionen hat.
- **Kurze Produktbeschreibung verwenden:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob die kurze Beschreibung oder die vollständige Beschreibung Ihrer Produkte im TikTok-Feed verwendet wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die kürzere, prägnantere Produktbeschreibung wird verwendet.
    - *Wenn deaktiviert:* Die längere, vollständige Produktbeschreibung wird verwendet.
  - **Empfohlener Wert:** JA (kurze Beschreibungen sind oft besser für Anzeigen, da Benutzer eine begrenzte Aufmerksamkeitsspanne haben).
  - **Händlerszenario / Beispiel:** TikTok-Anzeigen profitieren von prägnanten Informationen. Die Verwendung der kurzen Beschreibung stellt sicher, dass Ihr Anzeigentext prägnant und auf den Punkt gebracht ist.
- **Produktmerkmale als Attribute exportieren:**

  - **Was diese Einstellung bewirkt:** Wenn aktiviert, werden Ihre PrestaShop-Produktmerkmale (wie „Material“, „Farbe“, „Größe“) als zusätzliche Attribute in den TikTok-Feed exportiert, was detailliertere Produktinformationen liefert.
  - **Auswirkung der Änderung dieser Einstellung:** Detailliertere Produktinformationen stehen TikTok für eine bessere Anzeigenzielgruppenansprache und -anzeige zur Verfügung.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Wenn Sie Kleidung verkaufen, ermöglicht der Export von „Farbe“ und „Größe“ als Attribute TikTok, spezifischere Anzeigen zu schalten (z. B. „Rotes Kleid, Größe M“).
- **Produktkombinationen (Varianten) exportieren:**

  - **Was diese Einstellung bewirkt:** Entscheidend für Shops mit Produkten, die Variationen aufweisen (z. B. ein T-Shirt in verschiedenen Größen und Farben). Diese Einstellung stellt sicher, dass jede einzigartige Kombination als separater Artikel im Feed exportiert wird.
  - **Auswirkung der Änderung dieser Einstellung:** Jede Produktvariante erhält einen eigenen Eintrag im Feed, mit ihrem spezifischen Preis, Lagerbestand und Bild, wodurch TikTok die genau beworbene Variante anzeigen kann.
  - **Empfohlener Wert:** JA (fast immer, es sei denn, Sie verkaufen nur einfache Produkte ohne Variationen).
  - **Händlerszenario / Beispiel:** Wenn Sie einen Schuh verkaufen, der in den Größen 7, 8 und 9 erhältlich ist, stellt die Aktivierung sicher, dass TikTok drei verschiedene Produkte sieht, jedes mit seiner eigenen SKU und Verfügbarkeit.
- **Größenattribut exportieren:**

  - **Was diese Einstellung bewirkt:** Speziell für Produkte mit Kombinationen stellt diese Einstellung sicher, dass das „Größen“-Attribut jeder Kombination explizit in den Feed aufgenommen wird, was für Bekleidung und Schuhe wichtig ist.
  - **Auswirkung der Änderung dieser Einstellung:** Die Größe jeder Produktvariante wird im Feed deutlich aufgeführt.
  - **Empfohlener Wert:** JA (insbesondere für Mode, Schuhe oder andere größenabhängige Produkte).
  - **Händlerszenario / Beispiel:** Für ein Bekleidungsgeschäft stellt dies sicher, dass ein „Großes blaues T-Shirt“ von TikTok korrekt identifiziert wird, nicht nur ein „Blaues T-Shirt“.
- **Verfügbarkeitsdatum exportieren:**

  - **Was diese Einstellung bewirkt:** Enthält das „verfügbar zur Bestellung“-Datum für Produkte, was nützlich für Vorbestellungsartikel oder Produkte mit zukünftigen Veröffentlichungsterminen ist.
  - **Auswirkung der Änderung dieser Einstellung:** TikTok erhält Informationen darüber, wann ein Produkt verfügbar sein wird.
  - **Empfohlener Wert:** JA (wenn Sie diese Funktion in PrestaShop nutzen).
  - **Händlerszenario / Beispiel:** Wenn Sie nächsten Monat ein neues Produkt auf den Markt bringen, ermöglicht dies TikTok, „Vorbestellungs“-Anzeigen mit dem korrekten Verfügbarkeitsdatum anzuzeigen.
- **Google-Produktkategorie-Mapping:**

  - **Was diese Einstellung bewirkt:** TikTok nutzt oft die umfangreiche Produkttaxonomie von Google. Dieser Abschnitt ermöglicht es Ihnen, Ihre PrestaShop-Kategorien den relevantesten Google-Produktkategorien zuzuordnen. Dies verbessert die Anzeigenrelevanz und das Targeting.
  - **Auswirkung der Änderung dieser Einstellung:** Ihre Produkte werden im Feed gemäß der Google-Taxonomie korrekt kategorisiert, die TikTok für ein besseres Verständnis und Targeting verwendet.
  - **Empfohlener Wert:** Ordnen Sie so viele Kategorien wie möglich zu.
  - **Händlerszenario / Beispiel:** Wenn Sie eine PrestaShop-Kategorie „Sommerkleider“ haben, würden Sie diese einer Google-Produktkategorie wie „Bekleidung & Accessoires > Kleidung > Kleider“ zuordnen.
- **Feed-URL generieren:**

  - **Was diese Einstellung bewirkt:** Nach der Konfiguration aller Einstellungen generiert diese Schaltfläche die eindeutige URL für Ihren TikTok-Produkt-Feed. Diese URL ist die, die Sie dem TikTok Ads Manager zur Verfügung stellen werden.
  - **Auswirkung der Änderung dieser Einstellung:** Durch Klicken wird die URL angezeigt. Der Feed unter dieser URL spiegelt alle Ihre gewählten Einstellungen wider.
  - **Empfohlener Wert:** Klicken Sie dies, nachdem alle anderen Einstellungen abgeschlossen sind.
  - **Händlerszenario / Beispiel:** Sobald Sie alles eingerichtet haben, klicken Sie darauf, kopieren Sie die URL und fügen Sie sie in Ihren TikTok Ads Manager ein, wenn Sie Ihren Katalog einrichten.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Das Modul bietet einen dedizierten Bereich in Ihrem PrestaShop Back Office zur Verwaltung und Generierung Ihrer TikTok-Produkt-Feeds.

**Bildschirmname & Menüpfad:**
Sie können diesen Bereich über das Hauptmenü von PrestaShop aufrufen: **Katalog > TikTok Feed**.

Dieser Bereich präsentiert typischerweise ein Dashboard oder eine Liste der generierten Feeds, sodass Sie verschiedene Feed-Konfigurationen verwalten können, falls das Modul mehrere Feeds unterstützt (z. B. für verschiedene Sprachen oder Währungen).

#### 2.2.1 TikTok Feed Dashboard (Back Office > Katalog > TikTok Feed)

Dies ist der Haupteinstiegspunkt zur Verwaltung Ihrer TikTok-Feeds.

- **Verfügbare Aktionen & Einstellungen:**

  - **Liste der Feeds:** Sie sehen eine Tabelle oder Liste aller Ihrer konfigurierten TikTok-Feeds. Jeder Eintrag zeigt typischerweise:
    - **Feed-Name:** Ein beschreibender Name für Ihren Feed (z. B. „Englischer US-Feed“, „Französischer EU-Feed“).
    - **Sprache:** Die Sprache der Produkte in diesem Feed.
    - **Währung:** Die Währung der Preise in diesem Feed.
    - **Zuletzt generiert:** Der Zeitstempel, wann der Feed zuletzt aktualisiert wurde.
    - **Feed-URL:** Der direkte Link zur generierten Feed-Datei (CSV oder XML).
    - **Aktionen:** Schaltflächen zum „Bearbeiten“, „Jetzt generieren“ oder „Löschen“ des Feeds.
  - **Schaltfläche „Neuen Feed hinzufügen“:** Ermöglicht Ihnen das Erstellen einer neuen Feed-Konfiguration, möglicherweise für eine andere Sprache, Währung oder eine andere Reihe von Produktausschlüssen.
  - **Schaltfläche „Alle Feeds generieren“:** Eine praktische Option, um alle Ihre konfigurierten Feeds auf einmal zu aktualisieren.
- **Auswirkung von Änderungen:**

  - **Hinzufügen eines neuen Feeds:** Erstellt eine neue Konfigurationsinstanz, die es Ihnen ermöglicht, einen separaten Satz von Regeln (Sprache, Währung, Ausschlüsse) für einen eigenständigen TikTok-Feed zu definieren. Dies ist nützlich für Shops, die mehrere Länder oder Sprachen bedienen.
  - **Bearbeiten eines Feeds:** Führt Sie zu einem Konfigurationsformular (ähnlich der Hauptmodulkonfiguration, aber spezifisch für diese Feed-Instanz), wo Sie dessen Einstellungen anpassen können.
  - **Generieren eines Feeds:** Löst das Modul aus, Ihren Produktkatalog basierend auf den Einstellungen des Feeds zu verarbeiten und die Feed-Datei unter ihrer eindeutigen URL zu erstellen/aktualisieren. Dies ist entscheidend, um sicherzustellen, dass TikTok immer die aktuellsten Produktinformationen hat.
  - **Löschen eines Feeds:** Entfernt die Feed-Konfiguration und die zugehörige generierte Datei.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**

  1. **Ersteinrichtung:** Erstellen Sie mindestens einen Feed für Ihren primären Zielmarkt (z. B. Englisch, USD).
  2. **Multi-Markt-Einrichtung:** Wenn Sie mehrere Länder oder Sprachen ansprechen, erstellen Sie für jedes einen separaten Feed und konfigurieren Sie die Sprach-, Währungs- und Ländereinstellungen entsprechend.
  3. **Regelmäßige Generierung:** TikTok ruft Feeds typischerweise nach einem Zeitplan ab (z. B. täglich). Sie können manuell auf „Jetzt generieren“ klicken, wenn Sie wesentliche Produktänderungen vorgenommen haben (neue Produkte, Preisaktualisierungen, Bestandsänderungen) und möchten, dass TikTok diese sofort widerspiegelt. Andernfalls verfügt das Modul oft über einen automatischen Generierungsmechanismus oder eine Cron-Job-Einrichtung (siehe Entwicklerbereich).
  4. **Feed-Gesundheit überwachen:** Überprüfen Sie regelmäßig Ihren TikTok Ads Manager auf Feed-Fehler oder Warnungen. Wenn Probleme auftreten, überprüfen Sie Ihre Moduleinstellungen und generieren Sie den Feed neu.

#### 2.2.2 Feed-Konfigurationsformular (Zugriff über „Neuen Feed hinzufügen“ oder „Feed bearbeiten“)

Dieser Bildschirm ist der Ort, an dem Sie die spezifischen Parameter für einen einzelnen TikTok-Produkt-Feed definieren. Er spiegelt viele der Einstellungen wider, die auf der Hauptmodulkonfigurationsseite zu finden sind, wendet sie jedoch auf eine einzelne Feed-Instanz an.

- **Formularfelder & Spalten:**

  - **Feed-Name:** Ein eindeutiger, beschreibender Name für diesen spezifischen Feed (z. B. „US English Katalog“, „DE German Katalog“).
  - **Sprache:** Wählen Sie die Sprache für diesen Feed.
  - **Währung:** Wählen Sie die Währung für diesen Feed.
  - **Land:** Wählen Sie das Standardland für den Versand für diesen Feed.
  - **Nicht vorrätige Produkte einschließen:** (Wie oben, aber spezifisch für diesen Feed).
  - **Spezifische Kategorien ausschließen:** (Wie oben, aber spezifisch für diesen Feed).
  - **Spezifische Produkte ausschließen:** (Wie oben, aber spezifisch für diesen Feed).
  - **Kurze Produktbeschreibung verwenden:** (Wie oben, aber spezifisch für diesen Feed).
  - **Produktmerkmale als Attribute exportieren:** (Wie oben, aber spezifisch für diesen Feed).
  - **Produktkombinationen (Varianten) exportieren:** (Wie oben, aber spezifisch für diesen Feed).
  - **Größenattribut exportieren:** (Wie oben, aber spezifisch für diesen Feed).
  - **Verfügbarkeitsdatum exportieren:** (Wie oben, aber spezifisch für diesen Feed).
  - **Google-Produktkategorie-Mapping:** (Wie oben, aber spezifisch für diesen Feed).
- **Auswirkung von Änderungen:** Das Speichern von Änderungen in diesem Formular aktualisiert die Konfiguration für den spezifischen Feed, den Sie bearbeiten. Sie müssen dann „Jetzt generieren“ für diesen Feed, um die Änderungen auf die tatsächliche Feed-Datei anzuwenden.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfigurationsseite** | Modul aktivieren | JA | Aktiviert/deaktiviert die Modulfunktionalität. |
| | Feed-Generierungstyp | XML | Wählen Sie das CSV- oder XML-Format für den Feed. |
| | Standardsprache für Feed | Primäre Shop-Sprache | Legt die Sprache für Produktdaten fest. |
| | Standardwährung für Feed | Primäre Shop-Währung | Legt die Währung für Produktpreise fest. |
| | Standardland für den Versand | Primäres Versandland | Legt das Standardland für Versandinformationen fest. |
| | Nicht vorrätige Produkte einschließen | NEIN | Schließt nicht vorrätige Artikel aus dem Feed aus. |
| | Spezifische Kategorien ausschließen | (Keine) | Lässt Produkte aus ausgewählten Kategorien weg. |
| | Spezifische Produkte ausschließen | (Keine) | Lässt bestimmte Produkte aus dem Feed weg. |
| | Kurze Produktbeschreibung verwenden | JA | Verwendet kurze Beschreibungen für Prägnanz. |
| | Produktmerkmale als Attribute exportieren | JA | Schließt Produktmerkmale als Attribute ein. |
| | Produktkombinationen (Varianten) exportieren | JA | Exportiert jede Produktvariante als separaten Artikel. |
| | Größenattribut exportieren | JA | Schließt das Größenattribut für Varianten ein. |
| | Verfügbarkeitsdatum exportieren | JA | Schließt das Produktverfügbarkeitsdatum ein. |
| | Google-Produktkategorie-Mapping | Alle relevanten zuordnen | Ordnet PrestaShop-Kategorien der Google-Taxonomie für TikTok zu. |
| | Feed-URL generieren | Nach der Einrichtung klicken | Erstellt/aktualisiert die eindeutige URL für den Feed. |
| **TikTok Feed Dashboard** | Neuen Feed hinzufügen | N/A | Erstellt eine neue, separate Feed-Konfiguration. |
| | Feed bearbeiten | N/A | Ändert Einstellungen für einen bestehenden Feed. |
| | Jetzt generieren (für einen spezifischen Feed) | N/A | Aktualisiert manuell eine einzelne Feed-Datei. |
| | Alle Feeds generieren | N/A | Aktualisiert manuell alle konfigurierten Feed-Dateien. |
| | Feed löschen | N/A | Entfernt eine Feed-Konfiguration und ihre Datei. |
| **Feed-Konfigurationsformular** | Feed-Name | Beschreibender Name | Identifiziert den spezifischen Feed. |
| | (Alle anderen Einstellungen) | (Wie oben) | Konfiguriert Parameter für diese individuelle Feed-Instanz. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine TikTok-Anzeigen zeigen veraltete Preise oder nicht vorrätige Produkte an. Was soll ich tun?**
**A1:** Das bedeutet normalerweise, dass Ihr TikTok-Feed nicht häufig genug aktualisiert wird.
1. Gehen Sie in Ihrem PrestaShop Back Office zu **Katalog > TikTok Feed**.
2. Suchen Sie den relevanten Feed und klicken Sie auf die Schaltfläche „Jetzt generieren“.
3. Stellen Sie sicher, dass Sie einen Cron-Job eingerichtet haben, um Ihre Feeds täglich automatisch zu aktualisieren (empfohlen). Überprüfen Sie bei Ihrem Webmaster oder Hosting-Anbieter, ob der Cron-Job korrekt ausgeführt wird.
4. Überprüfen Sie Ihre Einstellung „Nicht vorrätige Produkte einschließen“ in der Feed-Konfiguration. Wenn sie aktiviert ist und Sie keine nicht vorrätigen Artikel möchten, deaktivieren Sie sie.

**F2: Einige meiner Produkte fehlen im TikTok-Feed.**
**A2:** Überprüfen Sie die folgenden Einstellungen für den spezifischen Feed:
1. **„Spezifische Kategorien ausschließen“:** Stellen Sie sicher, dass die Kategorien der fehlenden Produkte hier nicht ausgewählt sind.
2. **„Spezifische Produkte ausschließen“:** Stellen Sie sicher, dass die einzelnen Produkte nicht manuell ausgeschlossen sind.
3. **„Nicht vorrätige Produkte einschließen“:** Wenn die Produkte nicht vorrätig sind und diese Einstellung deaktiviert ist, werden sie nicht angezeigt.
4. **Produktsichtbarkeit:** Stellen Sie sicher, dass die Produkte in Ihrem PrestaShop-Shop aktiv und sichtbar sind.

**F3: Meine Produktbeschreibungen sehen im TikTok-Feed zu lang oder zu kurz aus.**
**A3:** Gehen Sie zur Feed-Konfiguration und passen Sie die Einstellung „Kurze Produktbeschreibung verwenden“ an:
- Wenn Beschreibungen zu lang sind, aktivieren Sie diese Einstellung, um die kürzere Beschreibung zu verwenden.
- Wenn Beschreibungen zu kurz sind und Sie mehr Details wünschen, deaktivieren Sie diese Einstellung, um die vollständige Beschreibung zu verwenden.

**F4: Wie ordne ich meine Kategorien effektiv den Google-Produktkategorien zu?**
**A4:**
1. Greifen Sie auf den Abschnitt „Google-Produktkategorie-Mapping“ in Ihrer Feed-Konfiguration zu.
2. Suchen Sie für jede Ihrer PrestaShop-Kategorien die relevanteste Google-Produktkategorie. Seien Sie so spezifisch wie möglich.
3. Wenn Sie keine exakte Übereinstimmung finden, wählen Sie die nächstgelegene, breitere Kategorie.
4. Diese Zuordnung hilft TikTok, Ihre Produkte besser für das Targeting zu verstehen.

**F5: Ich habe Änderungen vorgenommen, aber die Feed-URL zeigt immer noch alte Daten an. Was ist falsch?**
**A5:** Nachdem Sie Änderungen an den Moduleinstellungen oder der Konfiguration eines bestimmten Feeds vorgenommen haben, **müssen** Sie den Feed neu generieren. Gehen Sie zu **Katalog > TikTok Feed**, suchen Sie den geänderten Feed und klicken Sie auf „Jetzt generieren“. Wenn Sie globale Einstellungen geändert haben, müssen Sie möglicherweise alle Feeds neu generieren.

**F6: Mein benutzerdefiniertes Theme verursacht Anzeigeprobleme im Back Office für das Modul.**
**A6:** Während die Front-Office-Komponenten des Moduls unsichtbar sind, kann seine Back-Office-Oberfläche mit stark angepassten Admin-Themes kollidieren.
1. **Smarty-Cache leeren:** Gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Parameter > Leistung**. Klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Dies behebt oft kleinere Anzeigefehler.
2. **Nach JavaScript-Fehlern suchen:** Öffnen Sie die Entwicklerkonsole Ihres Browsers (F12) im Back Office. Suchen Sie nach JavaScript-Fehlern. Wenn Sie Fehler finden, kontaktieren Sie den MyPresta.eu-Support mit den Fehlerdetails.
3. **Temporärer Theme-Wechsel:** Wenn möglich, wechseln Sie Ihr Back Office-Theme vorübergehend zum Standard-PrestaShop-Theme, um zu sehen, ob das Problem weiterhin besteht. Wenn es sich löst, liegt der Konflikt bei Ihrem benutzerdefinierten Admin-Theme.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten Einblick in die technische Struktur des TikTok Katalog-Feed-Moduls, der für Entwickler und Webmaster gedacht ist.

### 4.1 Architekturübersicht

Das TikTok Katalog-Feed-Modul folgt einem Standard-PrestaShop MVC-Muster (Model-View-Controller), das sich hauptsächlich auf die Back-Office-Administration und die Front-Office-Datenbereitstellung konzentriert. Es nutzt die PrestaShop-Klasse `Module` für Installation/Deinstallation und Konfiguration sowie `AdminController` für die Verwaltung der Feed-Einstellungen. Die Kernlogik dreht sich um die dynamische Generierung von Produktdaten in einem strukturierten CSV- oder XML-Format, das über einen dedizierten `ModuleFrontController` zugänglich ist. Es führt keine benutzerdefinierten `ObjectModel`-Klassen ein, sondern fragt direkt die Kernprodukt- und Kategoriedaten von PrestaShop ab.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

Diese Controller sind für die Bereitstellung des eigentlichen Produkt-Feeds an TikTok verantwortlich.

- `controllers/front/feed.php`
  - **Klassenname & Elternklasse:** `TiktokfeedFeedModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dies ist der primäre Endpunkt für TikTok, um den Produktkatalog abzurufen. Er generiert dynamisch den Produkt-Feed (CSV oder XML) basierend auf den Konfigurationsparametern (Sprache, Währung, Ausschlüsse), die mit einer bestimmten Feed-ID verknüpft sind. Er übernimmt den Datenabruf, die Formatierung und die Ausgabe als Dateidownload oder direkten Stream. Er ist zustandslos konzipiert, verarbeitet die Anfrage und gibt den Feed zurück.
- `controllers/front/index.php`
  - **Klassenname & Elternklasse:** `TiktokfeedIndexModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller ist typischerweise ein Platzhalter oder ein Fallback. In vielen Modulen könnte `index.php` im Front-Controller-Verzeichnis das Standard-Routing übernehmen oder einfach weiterleiten. Für dieses Modul ist `feed.php` der kritische Front-Controller. Dieses `index.php` hat möglicherweise keine spezifische Logik oder könnte für eine allgemeine Modul-Frontpage verwendet werden, falls eine implementiert wäre (was bei einem Feed-Modul nicht der Fall ist).

#### Back-Office-Admin-Controller

Diese Controller verwalten die Modulkonfiguration und die Feed-Generierungseinstellungen innerhalb des PrestaShop Back Office.

- `controllers/admin/AdminExportProductsFeedTiktok.php`
  - **Klassenname & Elternklasse:** `AdminExportProductsFeedTiktokController` erweitert `ModuleAdminController`.
  - **Tab-Name und verwaltete Entität:** Dieser Controller ist für den Hauptbereich „TikTok Feed“ unter **Katalog > TikTok Feed** verantwortlich. Er verwaltet die Erstellung, Bearbeitung und Löschung individueller Feed-Konfigurationen. Er zeigt eine Liste der konfigurierten Feeds an und bietet Formulare für deren detaillierte Einstellungen.
  - **Schlüsselfunktionalitäten:**
    - `renderList()`: Zeigt die Tabelle der vorhandenen Feeds an.
    - `renderForm()`: Rendert das Formular zum Hinzufügen/Bearbeiten eines Feeds, einschließlich Feldern für Sprache, Währung, Kategorie-/Produktausschlüsse, Google-Kategorie-Mapping usw.
    - Behandelt das Speichern und Aktualisieren von Feed-Konfigurationen (`postProcess()`).
    - Löst den Feed-Generierungsprozess für bestimmte Feeds aus.
- `controllers/admin/index.php`
  - **Klassenname & Elternklasse:** `AdminTiktokfeedIndexController` erweitert `ModuleAdminController`.
  - **Tab-Name und verwaltete Entität:** Dieser Controller dient wahrscheinlich als Haupteinstiegspunkt für den Admin-Bereich des Moduls, leitet möglicherweise zu `AdminExportProductsFeedTiktokController` weiter oder bietet ein übergeordnetes Dashboard. Angesichts der Modulstruktur befindet sich die primäre Feed-Verwaltungslogik in `AdminExportProductsFeedTiktokController`. Dieses `index.php` könnte für eine allgemeine Modulübersicht oder eine einfache Weiterleitung sein.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist keine benutzerdefinierten Klassen im Verzeichnis `classes/` auf. Dies deutet darauf hin, dass das Modul hauptsächlich auf den Kern-`ObjectModel`-Klassen `Product`, `Category`, `Language`, `Currency`, `Carrier` von PrestaShop und `Configuration` für die Datenspeicherung und -abfrage basiert. Die Logik zur Feed-Generierung ist wahrscheinlich in der Hauptmoduldatei (`tiktokfeed/index.php`) und dem `AdminExportProductsFeedTiktokController` gekapselt.

### 4.4 JavaScript-Assets (`views/js/`)

- `tiktokfeed/lib/searchTool/views/js/autocomplete.js`
  - **Geltungsbereich:** Back-Office.
  - **Zweck:** Bietet Autocomplete-Funktionalität, wahrscheinlich zum Auswählen von Produkten oder Kategorien, die ausgeschlossen werden sollen, oder für das Google-Kategorie-Mapping. Es bindet Event-Listener an Eingabefelder, führt AJAX-Anfragen für Suchvorschläge aus und aktualisiert das DOM mit den Ergebnissen.
- `tiktokfeed/views/js/admin-app.js`
  - **Geltungsbereich:** Back-Office.
  - **Zweck:** Dies ist die Haupt-JavaScript-Datei für die Back-Office-Oberfläche des Moduls. Sie verarbeitet verschiedene interaktive Elemente auf den Feed-Konfigurationsformularen und dem Dashboard. Dies könnte Folgendes umfassen:
    - Formularvalidierung.
    - Dynamische Aktualisierungen basierend auf ausgewählten Optionen (z. B. Anzeigen/Ausblenden von Feldern).
    - AJAX-Aufrufe zum Speichern von Einstellungen oder zum Auslösen der Feed-Generierung.
    - Interaktionen mit Fancybox-Modals (z. B. für die Kategorie-/Produktauswahl).

### 4.5 CSS-Stylesheets (`views/css/`)

- `tiktokfeed/lib/searchTool/views/css/autocomplete.css`
  - **Geltungsbereich:** Back-Office-Admin-Styling.
  - **Zweck:** Stile für die Autocomplete-Dropdowns und Eingabefelder, die vom `autocomplete.js`-Skript verwendet werden, um eine konsistente und benutzerfreundliche Sucherfahrung innerhalb der Admin-Formulare zu gewährleisten.
- `tiktokfeed/views/admin-theme.css`
  - **Geltungsbereich:** Back-Office-Admin-Styling.
  - **Zweck:** Bietet allgemeine Stil-Anpassungen für die Back-Office-Oberfläche des Moduls, um sich nahtlos in das PrestaShop-Admin-Theme zu integrieren. Dies kann Layout-Anpassungen, Button-Styling oder Tabellenformatierung umfassen.
- `tiktokfeed/views/css/admin-app.css`
  - **Geltungsbereich:** Back-Office-Admin-Styling.
  - **Zweck:** Enthält spezifische Stile für die benutzerdefinierten Komponenten, Formulare und Dashboard-Elemente des Moduls innerhalb des PrestaShop Back Office. Dies könnte Stile für die Feed-Listen-Tabelle, Konfigurationspanels und Fancybox-Modals umfassen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

Das Moduldossier listet keine Templates in einem `hook/`-Unterverzeichnis explizit auf, was impliziert, dass das Modul keine Inhalte direkt in Front-Office-Hooks rendert. Seine primäre Funktion ist die Datengenerierung, nicht die Front-End-Anzeige.

#### Admin-Templates (`views/templates/admin/`)

Diese Templates werden zum Rendern der Back-Office-Oberfläche des Moduls verwendet.

- `tiktokfeed/views/templates/admin/dashboard.tpl`
  - **Zweck:** Wahrscheinlich das Haupt-Dashboard-Template für den TikTok Feed-Bereich, das möglicherweise eine Übersicht über Feeds, Status und schnelle Aktionen anzeigt.
- `tiktokfeed/views/templates/admin/feeds.tpl`
  - **Zweck:** Rendert die Liste der konfigurierten TikTok-Feeds, typischerweise eine Tabelle mit Spalten für Feed-Name, Sprache, Währung, URL und Aktionsschaltflächen (bearbeiten, generieren, löschen). Dies wird wahrscheinlich von `AdminExportProductsFeedTiktokController::renderList()` gerendert.
- `tiktokfeed/views/templates/admin/form-chrome.tpl`
  - **Zweck:** Ein Wrapper oder partielles Template, das verwendet wird, um eine konsistente Stilgebung und Struktur für die Konfigurationsformulare des Moduls bereitzustellen, möglicherweise einschließlich Header, Footer und allgemeiner Layout-Elemente für das Formular.
- `tiktokfeed/views/templates/admin/layout.tpl`
  - **Zweck:** Ein Basis-Layout-Template für die Admin-Seiten des Moduls, das die Gesamtstruktur definiert, einschließlich Header, Navigation und Inhaltsbereichen.

#### Andere Admin-bezogene Templates

Diese Templates werden wahrscheinlich als Partials oder für spezifische UI-Komponenten innerhalb der Admin-Formulare verwendet.

- `tiktokfeed/lib/searchTool/views/scripts.tpl`
  - **Zweck:** Enthält JavaScript für das Suchwerkzeug, wahrscheinlich das `autocomplete.js`-Skript und dessen Initialisierung.
- `tiktokfeed/views/categories-fancybox.tpl`
  - **Zweck:** Rendert den Inhalt für ein Fancybox-Modal, das zur Auswahl von Kategorien für den Ausschluss oder das Mapping verwendet wird.
- `tiktokfeed/views/exclude-products.tpl`
  - **Zweck:** Rendert die Benutzeroberfläche zum Auswählen und Verwalten von Produkten, die aus dem Feed ausgeschlossen werden sollen, möglicherweise innerhalb einer Fancybox oder eines dedizierten Abschnitts des Formulars.
- `tiktokfeed/views/google_lang_links.tpl`
  - **Zweck:** Rendert Links oder UI-Elemente im Zusammenhang mit dem Google-Produktkategorie-Mapping, möglicherweise für verschiedene Sprachen.
- `tiktokfeed/views/returnAlert.tpl`
  - **Zweck:** Ein generisches Template zum Anzeigen von Erfolgs- oder Fehlermeldungen/Warnungen im Back Office.
- `tiktokfeed/views/script-fancybox.tpl`
  - **Zweck:** Enthält JavaScript für die Fancybox-Integration, wahrscheinlich zum Öffnen von Modals für die Kategorie-/Produktauswahl.
- `tiktokfeed/views/script.tpl`
  - **Zweck:** Ein allgemeines Skript-Template, möglicherweise für die modulweite JavaScript-Initialisierung oder kleine Inline-Skripte.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul scheint laut Dossier keine benutzerdefinierten SQL-Tabellen zu erstellen.
  - Es speichert seine Konfigurationseinstellungen (z. B. Feed-Typ, Standardsprache/-währung, Ausschlusslisten, Google-Kategorie-Mappings) in der PrestaShop-Tabelle `ps_configuration`. Konfigurationsschlüssel würden typischerweise einem Muster wie `TTF_FEED_TYPE`, `TTF_DEFAULT_LANG`, `TTF_EXCLUDE_CATEGORIES` usw. folgen.
  - Individuelle Feed-Konfigurationen (falls mehrere Feeds unterstützt werden) könnten als serialisierte Arrays in `ps_configuration` oder potenziell in einer benutzerdefinierten Tabelle gespeichert werden, falls das Modul eine einführen würde (was nicht angegeben ist).
- **Registrierte Hooks-Tabelle**:
  Die Hauptfunktion des Moduls ist die Datengenerierung, nicht die Front-Office-Anzeige, daher registriert es keine Hooks zum Anzeigen von Inhalten im Storefront (z. B. `displayHeader`, `displayRightColumn`).
  Es wird jedoch die folgenden Hooks für seine Kernfunktionalität registrieren:

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `actionModuleInstall` | Während der Modulinstallation | Erstellt Konfigurationseinträge, registriert Admin-Tabs. |
  | `actionModuleUninstall` | Während der Moduldeinstallation | Bereinigt Konfigurationseinträge, deregistriert Admin-Tabs. |
  | `actionAdminControllerSetMedia` | Wenn ein Admin-Controller geladen wird | Fügt modulspezifisches JS und CSS für das Back Office in die Warteschlange ein. |
  | `displayBackOfficeHeader` | Rendert Inhalte im Back Office-Header | Potenziell für globales Admin-JS/CSS oder Benachrichtigungen. |
  | `actionSchedulerCron` (oder ähnlich) | Wenn der PrestaShop-Cron-Job ausgeführt wird | Löst die automatische Feed-Generierung aus, falls konfiguriert. |

### Cron-Job-Einrichtung für die automatisierte Feed-Generierung

Für automatisierte Feed-Updates müssen Sie einen Cron-Job auf Ihrem Server einrichten, um eine bestimmte URL oder ein Skript aufzurufen, das vom Modul bereitgestellt wird. Diese URL verweist typischerweise auf einen Front-Controller, der die Feed-Generierung auslöst.

**Beispiel für einen Cron-Job-Befehl (Konsultieren Sie Ihren Hosting-Anbieter für die genaue Syntax):**

Terminalfenster

```
0 3 \* \* \* wget -q -O /dev/null "https://yourstore.com/module/tiktokfeed/feed?action=generate\_all&token=YOUR\_SECURE\_TOKEN" >/dev/null 2>&1
```

- `0 3 * * *`: Dies plant den Job so, dass er täglich um 3:00 Uhr morgens ausgeführt wird.
- `wget -q -O /dev/null`: Ruft die URL stillschweigend ab und verwirft die Ausgabe.
- `https://yourstore.com/module/tiktokfeed/feed?action=generate_all&token=YOUR_SECURE_TOKEN`: Dies ist die URL, die die Feed-Generierung auslöst. Der Parameter `token` ist entscheidend für die Sicherheit, um unbefugten Zugriff zu verhindern. Das Modul sollte diesen Token in seiner Konfiguration oder Dokumentation bereitstellen.
- `>/dev/null 2>&1`: Leitet alle Ausgaben nach null um, um unnötige E-Mail-Benachrichtigungen zu vermeiden.

**Wichtig:** Die genaue URL und der Token werden vom Modul nach der Konfiguration bereitgestellt. Verwenden Sie immer den sicheren Token, um Ihren Feed-Generierungs-Endpunkt zu schützen.

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Entwickler-Support besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Stellen Sie sicher, dass Sie die neueste kompatible Version des Moduls für Ihren PrestaShop-Shop verwenden.
