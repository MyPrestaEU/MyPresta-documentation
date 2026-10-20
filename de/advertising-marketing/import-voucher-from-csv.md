---
title: "Gutscheine aus CSV importieren – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Gutscheine aus CSV importieren“ von MyPresta.eu."
sidebar:
  label: "Gutscheine aus CSV importieren – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Import voucher from CSV auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/import-voucher-from-csv.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/import-voucher-from-csv/)
>
> ---


# Gutscheine aus CSV importieren

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend und auf den meisten Hosting-Umgebungen standardmäßig aktiviert.

## 2. Vollständige Konfigurationsanleitung (Alle Einstellungen nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zum Hauptkonfigurationsbildschirm des Moduls. Hier laden Sie Ihre CSV-Datei hoch und definieren, wie die Gutscheincodes importiert werden sollen und welche Eigenschaften sie haben sollen.

Die Konfigurationsseite ist typischerweise in mehrere Abschnitte gegliedert, die Sie durch den Importprozess führen.

#### **Schritt 1: Laden Sie Ihre CSV-Datei hoch**

- **Was diese Einstellung bewirkt:** Hier wählen Sie die CSV-Datei mit Ihren Gutscheincodes von Ihrem Computer aus.
- **Auswirkung der Änderung dieser Einstellung:** Durch Klicken auf „Durchsuchen“ oder „Datei auswählen“ wird ein Dateiauswahldialog geöffnet. Sobald Sie eine Datei ausgewählt haben, erscheint ihr Name neben der Schaltfläche, was anzeigt, dass sie zum Hochladen bereit ist.
- **Empfohlener Wert:** Wählen Sie die CSV-Datei aus, die Sie mit Ihren Gutscheincodes vorbereitet haben.
- **Händlerszenario / Beispiel:** Sie haben eine Liste mit 1000 einzigartigen Gutscheincodes von einem Partner wie Groupon erhalten. Sie haben diese Codes in einer CSV-Datei gespeichert (z.B. `groupon_vouchers.csv`). Sie würden auf „Datei auswählen“ klicken und diese Datei auswählen.

#### **Schritt 2: CSV-Dateieinstellungen**

Dieser Abschnitt definiert, wie das Modul Ihre CSV-Datei interpretieren soll.

- **CSV-Trennzeichen:**

  - **Was diese Einstellung bewirkt:** Gibt das Zeichen an, das zum Trennen von Werten (Spalten) innerhalb Ihrer CSV-Datei verwendet wird. Gängige Trennzeichen sind Komma (`,`), Semikolon (`;`) oder Tabulator (`\t`).
  - **Auswirkung der Änderung dieser Einstellung:** Wenn das falsche Trennzeichen gewählt wird, kann das Modul Ihre Datei nicht korrekt parsen, und alle Daten könnten in einer einzigen Spalte erscheinen oder falsch aufgeteilt werden.
  - **Empfohlener Wert:** Passen Sie das Trennzeichen an, das Sie beim Erstellen oder Exportieren Ihrer CSV-Datei verwendet haben. Die meisten Tabellenkalkulationsprogramme verwenden standardmäßig das Komma.
  - **Händlerszenario / Beispiel:** Wenn Ihre CSV-Datei wie `CODE123,10,USD` aussieht, würden Sie „Komma“ wählen. Wenn sie `CODE123;10;USD` ist, würden Sie „Semikolon“ wählen.
- **Textbegrenzer:**

  - **Was diese Einstellung bewirkt:** Gibt das Zeichen an, das zum Einschließen von Textwerten verwendet wird, insbesondere solcher, die das Trennzeichen enthalten könnten. Oft ist dies ein doppeltes Anführungszeichen (`"`).
  - **Auswirkung der Änderung dieser Einstellung:** Wenn Ihre Textfelder das Trennzeichen enthalten (z.B. ein Produktname mit einem Komma darin) und nicht ordnungsgemäß begrenzt sind, könnte das Modul die Daten falsch interpretieren, was zu einer falschen Analyse führt.
  - **Empfohlener Wert:** Passen Sie den Begrenzer an, der in Ihrer CSV-Datei verwendet wird. Normalerweise „Doppeltes Anführungszeichen“.
  - **Händlerszenario / Beispiel:** Wenn eine Gutscheinbeschreibung `"10% Rabatt, zeitlich begrenztes Angebot"` lautet und Ihr Trennzeichen ein Komma ist, stellen die doppelten Anführungszeichen sicher, dass „10% Rabatt, zeitlich begrenztes Angebot“ als ein Feld behandelt wird.
- **Erste Zeile überspringen (Header):**

  - **Was diese Einstellung bewirkt:** Wenn Ihre CSV-Datei eine Kopfzeile hat (z.B. `Gutscheincode,Rabattbetrag,Ablaufdatum`), die die Spalten beschreibt, wird das Modul durch Aktivieren dieser Option angewiesen, diese erste Zeile während des Imports zu ignorieren.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Kopfzeile wird übersprungen, und nur die tatsächlichen Datenzeilen werden importiert.
    - *Wenn deaktiviert:* Die erste Zeile Ihrer CSV-Datei wird als Gutscheincode oder Daten behandelt, was normalerweise falsch ist und zu Fehlern führen kann.
  - **Empfohlener Wert:** „JA“, wenn Ihre CSV-Datei eine Kopfzeile hat, „NEIN“, wenn sie nur Daten enthält.
  - **Händlerszenario / Beispiel:** Ihre CSV-Datei beginnt mit `code,value,currency`. Sie würden dies aktivieren, um zu verhindern, dass „code“ als tatsächlicher Gutschein importiert wird.

#### **Schritt 3: Gutscheineinstellungen (Allgemeine Eigenschaften)**

Dieser Abschnitt definiert die gemeinsamen Eigenschaften für alle Gutscheine, die Sie importieren. Diese Einstellungen gelten für *alle* Codes in Ihrer CSV-Datei.

- **Name:**

  - **Was diese Einstellung bewirkt:** Dies ist der interne Name für die Gutscheinregel in Ihrem Back Office. Er hilft Ihnen, die Gruppe der Gutscheine zu identifizieren.
  - **Auswirkung der Änderung dieser Einstellung:** Dieser Name ist nur für Sie im Back Office sichtbar, nicht für Kunden.
  - **Empfohlener Wert:** Ein aussagekräftiger Name, z.B. „Groupon Codes – Mai 2024“.
  - **Händlerszenario / Beispiel:** Sie importieren Codes aus einer Kampagne „Sommer Sale 2024“. Sie würden sie „Sommer Sale 2024 Gutscheine“ nennen.
- **Beschreibung:**

  - **Was diese Einstellung bewirkt:** Eine optionale interne Beschreibung für die Gutscheinregel.
  - **Auswirkung der Änderung dieser Einstellung:** Bietet mehr Kontext für Ihr Team im Back Office.
  - **Empfohlener Wert:** Eine kurze Erklärung, z.B. „Einmalige Codes für 10% Rabatt, einmalige Verwendung, gültig bis 31.05.2024“.
  - **Händlerszenario / Beispiel:** „Codes von LivingSocial für Neukunden bereitgestellt.“
- **Hervorheben:**

  - **Was diese Einstellung bewirkt:** Legt fest, ob der Gutschein in der Warenkorbzusammenfassung hervorgehoben wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der Gutschein wird in der Warenkorbzusammenfassung prominenter angezeigt, was möglicherweise mehr Aufmerksamkeit auf den Rabatt lenkt.
    - *Wenn deaktiviert:* Der Gutschein wird normal aufgeführt.
  - **Empfohlener Wert:** „NEIN“ für den allgemeinen Gebrauch, „JA“, wenn Sie den Rabatt betonen möchten.
  - **Händlerszenario / Beispiel:** Für ein spezielles, zeitlich begrenztes Angebot könnten Sie „JA“ aktivieren, um sicherzustellen, dass Kunden den angewendeten Rabatt bemerken.
- **Teilweise Nutzung:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Kunden, nur einen Teil des Gutscheinwerts zu verwenden und den Rest für zukünftige Einkäufe zu behalten.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Wenn ein Kunde einen 50-Euro-Gutschein hat und einen Artikel für 30 Euro kauft, behält er ein Restguthaben von 20 Euro auf dem Gutschein.
    - *Wenn deaktiviert:* Der gesamte Gutscheinwert muss in einer Transaktion verwendet werden; ein verbleibendes Guthaben geht verloren.
  - **Empfohlener Wert:** „NEIN“ für die meisten Rabattcodes. „JA“ für Geschenkkarten oder Shop-Guthaben.
  - **Händlerszenario / Beispiel:** Wenn Sie Geschenkkartencodes importieren, würden Sie „JA“ aktivieren. Für einen Standard-„10% Rabatt“-Gutschein würden Sie „NEIN“ verwenden.
- **Priorität:**

  - **Was diese Einstellung bewirkt:** Bestimmt die Reihenfolge, in der mehrere Gutscheine angewendet werden, wenn ein Kunde mehr als einen verwendet. Gutscheine mit höherer Priorität werden zuerst angewendet.
  - **Auswirkung der Änderung dieser Einstellung:** Kann den endgültigen Rabattbetrag beeinflussen, wenn mehrere Gutscheine interagieren (z.B. prozentuale Rabatte vs. feste Rabattbeträge).
  - **Empfohlener Wert:** „1“ für höchste Priorität, oder Standardwert belassen, wenn Sie keine komplexen Gutscheininteraktionen haben.
  - **Händlerszenario / Beispiel:** Wenn Sie einen „Kostenloser Versand“-Gutschein und einen „10% Rabatt“-Gutschein haben, könnten Sie dem „Kostenloser Versand“-Gutschein eine höhere Priorität geben, um sicherzustellen, dass er zuerst angewendet wird, dann der prozentuale Rabatt.
- **Status:**

  - **Was diese Einstellung bewirkt:** Aktiviert oder deaktiviert die Gutscheinregel.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Gutscheine, die unter dieser Regel importiert wurden, können von Kunden verwendet werden.
    - *Wenn deaktiviert:* Gutscheine können nicht verwendet werden, auch wenn sie gültig sind.
  - **Empfohlener Wert:** „JA“, um die Gutscheine sofort nutzbar zu machen. Sie können sie später bei Bedarf deaktivieren.
  - **Händlerszenario / Beispiel:** Sie möchten Gutscheine im Voraus vorbereiten, sie aber erst am Starttag einer Kampagne aktivieren. Sie würden zunächst „NEIN“ einstellen und dann auf „JA“ ändern, wenn Sie bereit sind.

#### **Schritt 4: Gutscheineinstellungen (Bedingungen)**

Dieser Abschnitt definiert die Bedingungen, unter denen die importierten Gutscheine verwendet werden können.

- **Mindestbetrag:**

  - **Was diese Einstellung bewirkt:** Gibt den Mindestbestellwert (vor Versand und Steuern) an, der für die Gültigkeit des Gutscheins erforderlich ist.
  - **Auswirkung der Änderung dieser Einstellung:** Kunden müssen diesen Mindestkaufwert erreichen, um den Rabatt anwenden zu können.
  - **Empfohlener Wert:** „0“, wenn kein Minimum erforderlich ist, oder ein bestimmter Betrag (z.B. „50.00“).
  - **Händlerszenario / Beispiel:** „Erhalten Sie 10 € Rabatt auf Bestellungen über 100 €.“ Sie würden „100.00“ einstellen.
- **Währung:**

  - **Was diese Einstellung bewirkt:** Wählt die Währung für den Mindestbetrag aus.
  - **Auswirkung der Änderung dieser Einstellung:** Stellt sicher, dass der Mindestbetrag für Shops mit mehreren Währungen korrekt interpretiert wird.
  - **Empfohlener Wert:** Die Standardwährung Ihres Shops (z.B. „USD“, „EUR“).
  - **Händlerszenario / Beispiel:** Wenn Ihr Shop in mehreren Währungen betrieben wird, stellen Sie sicher, dass dies mit der Währung übereinstimmt, die Kunden voraussichtlich für diesen Gutschein verwenden werden.
- **Kumulierbar mit anderen Gutscheinen:**

  - **Was diese Einstellung bewirkt:** Legt fest, ob dieser Gutschein mit anderen aktiven Gutscheinen in derselben Bestellung kombiniert werden kann.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden können diesen Gutschein zusammen mit anderen gültigen Gutscheinen verwenden.
    - *Wenn deaktiviert:* Dieser Gutschein kann nicht verwendet werden, wenn bereits ein anderer Gutschein auf den Warenkorb angewendet wurde.
  - **Empfohlener Wert:** „NEIN“ für die meisten einzigartigen Codes, um übermäßige Rabatte zu vermeiden. „JA“ für spezifische Aktionen wie „kostenloser Versand“, die Sie kombinieren möchten.
  - **Händlerszenario / Beispiel:** Sie importieren „10% Rabatt“-Codes. Sie möchten wahrscheinlich „NEIN“, um zu verhindern, dass Kunden mehrere prozentuale Rabatte stapeln.
- **Ablaufdatum (Von):**

  - **Was diese Einstellung bewirkt:** Legt das Startdatum fest, ab dem die importierten Gutscheine gültig werden.
  - **Auswirkung der Änderung dieser Einstellung:** Gutscheine können vor diesem Datum nicht verwendet werden.
  - **Empfohlener Wert:** Das heutige Datum oder ein zukünftiges Datum für geplante Aktionen.
  - **Händlerszenario / Beispiel:** Sie möchten, dass Gutscheine ab nächstem Montag aktiv sind. Sie würden das Datum des nächsten Montags auswählen.
- **Ablaufdatum (Bis):**

  - **Was diese Einstellung bewirkt:** Legt das Enddatum fest, nach dem die importierten Gutscheine nicht mehr gültig sind.
  - **Auswirkung der Änderung dieser Einstellung:** Gutscheine können nach diesem Datum nicht mehr verwendet werden.
  - **Empfohlener Wert:** Ein zukünftiges Datum, das dem Ende Ihrer Aktion entspricht.
  - **Händlerszenario / Beispiel:** Ihre Kampagne endet am 31. Dezember. Sie würden den 31. Dezember auswählen.
- **Menge:**

  - **Was diese Einstellung bewirkt:** Definiert, wie oft *jeder einzelne Gutscheincode* verwendet werden kann.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Auf 1 gesetzt:* Jeder Code in Ihrer CSV-Datei kann nur einmal verwendet werden (am häufigsten für einzigartige Codes).
    - *Auf >1 gesetzt:* Jeder Code kann bis zu diesem Limit mehrmals verwendet werden.
  - **Empfohlener Wert:** „1“ für einzigartige, einmalig verwendbare Codes (z.B. von Groupon).
  - **Händlerszenario / Beispiel:** Für 1000 einzigartige Groupon-Codes würden Sie dies auf „1“ setzen, damit jeder Kunde seinen spezifischen Code nur einmal verwenden kann.
- **Menge pro Benutzer:**

  - **Was diese Einstellung bewirkt:** Definiert, wie oft *ein einzelner Kunde* *beliebige* Gutscheine aus dieser importierten Charge verwenden kann.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Auf 1 gesetzt:* Ein Kunde kann nur einen Gutschein aus dieser Charge verwenden, auch wenn er mehrere einzigartige Codes hat.
    - *Auf >1 gesetzt:* Ein Kunde kann mehrere Gutscheine aus dieser Charge verwenden, bis zu diesem Limit.
  - **Empfohlener Wert:** „1“ für die meisten Kampagnen mit einzigartigen Codes, um zu verhindern, dass ein einzelner Kunde viele Codes verwendet.
  - **Händlerszenario / Beispiel:** Sie möchten, dass jeder Kunde nur von einem „Willkommens“-Gutschein profitiert. Sie würden dies auf „1“ setzen.

#### **Schritt 5: Gutscheineinstellungen (Aktionen)**

Dieser Abschnitt definiert, welche Art von Rabatt die importierten Gutscheine gewähren.

- **Kostenloser Versand:**

  - **Was diese Einstellung bewirkt:** Wenn aktiviert, gewährt der Gutschein kostenlosen Versand für die Bestellung.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Versandkosten entfallen, wenn der Gutschein angewendet wird.
    - *Wenn deaktiviert:* Versandkosten werden normal berechnet.
  - **Empfohlener Wert:** „NEIN“, es sei denn, der Hauptzweck dieser Gutscheine ist der kostenlose Versand.
  - **Händlerszenario / Beispiel:** Sie importieren Codes für eine „Kostenloser Versand am Wochenende“-Aktion. Sie würden „JA“ aktivieren.
- **Rabatt anwenden:**

  - **Was diese Einstellung bewirkt:** Bestimmt Art und Wert des durch den Gutschein angewendeten Rabatts.
  - **Auswirkung der Änderung dieser Einstellung:** Dies ist der zentrale Rabattmechanismus.
  - **Empfohlener Wert:** Wählen Sie eine der folgenden Optionen basierend auf Ihrer Aktion.
  - **Händlerszenario / Beispiel:** Sie möchten 10% Rabatt geben.
  - **Prozentsatz:**

    - **Was diese Einstellung bewirkt:** Wendet einen prozentualen Rabatt auf die Bestellung an.
    - **Auswirkung der Änderung dieser Einstellung:** Das Feld `Wert` wird als Prozentsatz interpretiert (z.B. `10` für 10%).
    - **Empfohlener Wert:** Wählen Sie dies für prozentuale Rabatte.
    - **Händlerszenario / Beispiel:** Für eine „15% Rabatt“-Aktion wählen Sie „Prozentsatz“ und geben `15` in das Feld `Wert` ein.
  - **Betrag:**

    - **Was diese Einstellung bewirkt:** Wendet einen festen monetären Rabatt auf die Bestellung an.
    - **Auswirkung der Änderung dieser Einstellung:** Das Feld `Wert` wird als fester Betrag in Ihrer gewählten Währung interpretiert (z.B. `10.00` für 10 € Rabatt).
    - **Empfohlener Wert:** Wählen Sie dies für feste Rabattbeträge.
    - **Händlerszenario / Beispiel:** Für eine „20 € Rabatt“-Aktion wählen Sie „Betrag“ und geben `20.00` in das Feld `Wert` ein.
  - **Keine:**

    - **Was diese Einstellung bewirkt:** Wenn ausgewählt, wendet der Gutschein keinen monetären oder prozentualen Rabatt an. Dies wird typischerweise verwendet, wenn die einzige Aktion des Gutscheins „Kostenloser Versand“ oder „Geschenk senden“ ist.
    - **Auswirkung der Änderung dieser Einstellung:** Es wird kein Rabattwert angewendet.
    - **Empfohlener Wert:** Wählen Sie „Keine“ nur, wenn Sie „Kostenloser Versand“ oder „Geschenk senden“ als primäre Aktion verwenden.
    - **Händlerszenario / Beispiel:** Wenn Sie nur kostenlosen Versand anbieten möchten, würden Sie hier „Keine“ auswählen und oben „Kostenloser Versand“ aktivieren.
- **Wert:**

  - **Was diese Einstellung bewirkt:** Der tatsächliche numerische Wert des Rabatts. Seine Interpretation hängt davon ab, ob oben „Prozentsatz“ oder „Betrag“ ausgewählt ist.
  - **Auswirkung der Änderung dieser Einstellung:** Steuert direkt die Höhe des Rabatts.
  - **Empfohlener Wert:** Ein numerischer Wert (z.B. `10` für 10% oder 10 €).
  - **Händlerszenario / Beispiel:** Wenn Sie „Prozentsatz“ gewählt haben und 15% Rabatt wünschen, geben Sie `15` ein. Wenn Sie „Betrag“ gewählt haben und 20 € Rabatt wünschen, geben Sie `20.00` ein.
- **Rabatt anwenden auf:**

  - **Was diese Einstellung bewirkt:** Bestimmt, worauf der Rabatt angewendet wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Bestellung (ohne Versand):* Rabatt gilt für den gesamten Produktwert im Warenkorb.
    - *Bestimmtes Produkt:* Rabatt gilt nur für ein bestimmtes Produkt, das Sie angeben.
    - *Günstigstes Produkt:* Rabatt gilt für das preisgünstigste Produkt im Warenkorb.
    - *Ausgewählte Produkte:* Rabatt gilt für eine Auswahl von Produkten.
  - **Empfohlener Wert:** „Bestellung (ohne Versand)“ für allgemeine Rabatte.
  - **Händlerszenario / Beispiel:** Für eine allgemeine „10% Rabatt auf alles“-Kampagne wählen Sie „Bestellung (ohne Versand)“. Wenn es „10% Rabatt auf alle T-Shirts“ ist, würden Sie „Ausgewählte Produkte“ auswählen und dann Ihre T-Shirt-Kategorie/Produkte wählen.
- **Geschenk senden:**

  - **Was diese Einstellung bewirkt:** Wenn aktiviert, fügt der Gutschein ein bestimmtes Produkt als kostenloses Geschenk zum Warenkorb des Kunden hinzu.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Sie werden aufgefordert, ein Produkt auszuwählen, das als Geschenk hinzugefügt werden soll.
    - *Wenn deaktiviert:* Es wird kein Geschenk hinzugefügt.
  - **Empfohlener Wert:** „NEIN“, es sei denn, Sie führen eine „Kaufe X, erhalte Y gratis“-Aktion durch.
  - **Händlerszenario / Beispiel:** „Kaufe ein beliebiges Produkt, erhalte einen kostenlosen Schlüsselanhänger.“ Sie würden „JA“ aktivieren und das Schlüsselanhänger-Produkt auswählen.

Nachdem Sie alle Einstellungen konfiguriert haben, finden Sie in der Regel eine Schaltfläche „Speichern“ oder „Importieren“. Klicken Sie darauf, um den Importvorgang zu starten. Das Modul liest dann Ihre CSV-Datei und erstellt die entsprechenden Gutscheinregeln in Ihrer PrestaShop-Datenbank basierend auf den von Ihnen definierten Einstellungen.

### 2.2 Konfigurations-Schnellreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | CSV-Datei hochladen | Ihre vorbereitete CSV | Wählt die Datei mit den Gutscheincodes aus. |
| | CSV-Trennzeichen | Komma (`,`) | Zeichen, das Spalten in Ihrer CSV trennt. Muss mit Ihrer Datei übereinstimmen. |
| | Textbegrenzer | Doppeltes Anführungszeichen (`"`) | Zeichen, das Textfelder in Ihrer CSV umschließt. Muss mit Ihrer Datei übereinstimmen. |
| | Erste Zeile überspringen (Header) | JA (wenn Header vorhanden) | Ignoriert die erste Zeile Ihrer CSV, wenn es sich um einen Header handelt. |
| | **Gutscheineinstellungen (Allgemein)** | | |
| | Name | Beschreibender Name | Interner Name für die Gutscheinregel im BO. |
| | Beschreibung | Optionaler Text | Interne Beschreibung für die Gutscheinregel. |
| | Hervorheben | NEIN | Hebt den Gutschein in der Warenkorbzusammenfassung hervor. |
| | Teilweise Nutzung | NEIN | Ermöglicht die teilweise Nutzung des Gutscheinwerts. JA für Geschenkkarten. |
| | Priorität | 1 | Reihenfolge der Anwendung für mehrere Gutscheine. |
| | Status | JA | Aktiviert/deaktiviert die Gutscheinregel. |
| | **Gutscheineinstellungen (Bedingungen)** | | |
| | Mindestbetrag | 0 | Mindestbestellwert für die Gutscheingültigkeit. |
| | Währung | Standard des Shops | Währung für den Mindestbetrag. |
| | Kumulierbar mit anderen Gutscheinen | NEIN | Ermöglicht die Kombination mit anderen Gutscheinen. |
| | Ablaufdatum (Von) | Heutiges Datum | Startdatum für die Gutscheingültigkeit. |
| | Ablaufdatum (Bis) | Zukünftiges Datum | Enddatum für die Gutscheingültigkeit. |
| | Menge | 1 | Gesamtnutzungen pro *individuellem* Gutscheincode. |
| | Menge pro Benutzer | 1 | Gesamtnutzungen pro *Kunde* aus dieser Charge. |
| | **Gutscheineinstellungen (Aktionen)** | | |
| | Kostenloser Versand | NEIN | Gewährt kostenlosen Versand. |
| | Rabatt anwenden | Prozentsatz / Betrag | Art des Rabatts (prozentual oder fester Betrag). |
| | Wert | Numerischer Wert | Der tatsächliche Rabattwert (z.B. 10 für 10% oder 10 €). |
| | Rabatt anwenden auf | Bestellung (ohne Versand) | Worauf der Rabatt angewendet wird (Bestellung, bestimmtes Produkt usw.). |
| | Geschenk senden | NEIN | Fügt ein kostenloses Produkt als Geschenk hinzu. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe meine CSV-Datei importiert, aber die Gutscheine funktionieren nicht oder werden nicht angezeigt.**
A:

1. **Modulstatus prüfen:** Stellen Sie sicher, dass das Modul selbst unter **Module > Modul-Manager** aktiviert ist.
2. **Gutscheinstatus prüfen:** Gehen Sie zu **Katalog > Rabatte > Warenkorbregeln** (oder **Preisregeln > Warenkorbregeln** in älteren Versionen). Suchen Sie die durch den Import erstellte Gutscheinregel (sie hat den „Namen“, den Sie bei der Konfiguration angegeben haben). Stellen Sie sicher, dass ihr „Status“ auf „JA“ (aktiv) gesetzt ist.
3. **Ablaufdaten:** Überprüfen Sie die Einstellungen für „Ablaufdatum (Von)“ und „Ablaufdatum (Bis)“. Wenn das aktuelle Datum außerhalb dieses Bereichs liegt, funktionieren die Gutscheine nicht.
4. **Mindestbetrag:** Überprüfen Sie, ob der Warenkorb des Kunden die von Ihnen festgelegte Bedingung „Mindestbetrag“ erfüllt.
5. **Gutscheincodes:** Stellen Sie sicher, dass die Codes in Ihrer CSV-Datei genau so sind, wie Kunden sie eingeben (Groß-/Kleinschreibung beachten, keine zusätzlichen Leerzeichen).

**F: Meine CSV-Datei wird nicht korrekt geparst. Alle Daten sind in einer Spalte, oder die Spalten sind vertauscht.**
A: Dies liegt fast immer an falschen Einstellungen für „CSV-Trennzeichen“ oder „Textbegrenzer“.

1. **Öffnen Sie Ihre CSV-Datei** in einem einfachen Texteditor (wie Notepad, Sublime Text, VS Code oder sogar Excel/Google Sheets, aber speichern Sie sie dann erneut als CSV).
2. **Identifizieren Sie das Trennzeichen:** Schauen Sie, wie die Werte getrennt sind. Ist es ein Komma (`,`), Semikolon (`;`) oder Tabulator? Wählen Sie das richtige in den Moduleinstellungen aus.
3. **Identifizieren Sie den Begrenzer:** Suchen Sie nach Zeichen, die Text umschließen, normalerweise doppelte Anführungszeichen (`"`). Wenn vorhanden, stellen Sie sicher, dass „Textbegrenzer“ auf „Doppeltes Anführungszeichen“ gesetzt ist.
4. **Kopfzeile:** Wenn Ihre CSV eine Kopfzeile hat, stellen Sie sicher, dass „Erste Zeile überspringen (Header)“ auf „JA“ gesetzt ist.

**F: Ich habe Gutscheine importiert, möchte sie aber jetzt löschen oder deaktivieren.**
A:

1. Gehen Sie zu **Katalog > Rabatte > Warenkorbregeln** (oder **Preisregeln > Warenkorbregeln**).
2. Suchen Sie die Gutscheinregel, die Sie mit dem Modul erstellt haben (mithilfe des von Ihnen zugewiesenen „Namens“).
3. Sie können entweder:
   - **Deaktivieren:** Klicken Sie auf das grüne Häkchen neben der Regel, um es in ein rotes „X“ zu verwandeln. Dies deaktiviert alle Gutscheine unter dieser Regel.
   - **Löschen:** Wählen Sie die Regel aus und verwenden Sie die Massenaktionen oder klicken Sie auf das Löschsymbol, um die gesamte Regel und alle zugehörigen Gutscheincodes zu entfernen.

Das Löschen einer Warenkorbregel ist dauerhaft und kann nicht rückgängig gemacht werden.

**F: Kann ich bestehende Gutscheine mit diesem Modul aktualisieren?**
A: Nein, dieses Modul ist für den Import *neuer* Gutscheine konzipiert. Es verfügt nicht über Funktionen zum Aktualisieren bestehender Gutscheincodes oder Warenkorbregeln. Wenn Sie einen bestehenden Gutschein ändern müssen, müssen Sie dies manuell über **Katalog > Rabatte > Warenkorbregeln** tun.

**F: Warum sind meine importierten Gutscheine nicht mit anderen Rabatten kumulierbar?**
A: Überprüfen Sie die Einstellung „Kumulierbar mit anderen Gutscheinen“ in der Modulkonfiguration. Wenn Sie diese auf „NEIN“ gesetzt haben (was oft für einzigartige Codes empfohlen wird), können Kunden diese Gutscheine nicht zusammen mit anderen aktiven Rabatten in ihrem Warenkorb verwenden. Wenn Sie möchten, dass sie kumulierbar sind, setzen Sie dies während des Imports auf „JA“.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster, die mit dem Modul „Gutscheine aus CSV importieren“ arbeiten.

### 4.1 Architekturübersicht

Das Modul `importvoucher` ist ein Standard-PrestaShop-Modul, das sich hauptsächlich auf die Back-Office-Funktionalität konzentriert. Es nutzt die Kern-ObjectModels `CartRule` und `CartRuleProduct` von PrestaShop, um Rabattcodes zu erstellen und zu verwalten. Die Hauptlogik des Moduls befindet sich in seiner primären PHP-Datei und verarbeitet Dateiuploads, CSV-Parsing und Datenbankinteraktionen. Es führt keine komplexen MVC-Muster mit dedizierten Front- oder Admin-Controllern ein, sondern verwendet die Methode `getContent()` für seine Konfigurationsoberfläche.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine dedizierten Front-Office- oder Back-Office-Controller in den Verzeichnissen `controllers/front` oder `controllers/admin`. Die gesamte administrative Logik, einschließlich des Konfigurationsformulars und des CSV-Importprozesses, wird direkt in der `getContent()`-Methode der Hauptmoduldatei behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul definiert keine benutzerdefinierten Klassen in einem `classes/`-Verzeichnis. Es interagiert direkt mit den Kern-ObjectModels `CartRule` und `CartRuleProduct` von PrestaShop, um Rabattcodes zu erstellen und zu verwalten.

- **`CartRule` (PrestaShop-Kernklasse):**

  - Interagiert mit der Datenbanktabelle `ps_cart_rule`.
  - Das Modul füllt Eigenschaften von `CartRule`-Objekten (z.B. `name`, `description`, `code`, `quantity`, `quantity_per_user`, `date_from`, `date_to`, `minimum_amount`, `reduction_percent`, `reduction_amount`, `free_shipping`, `active`, `highlight`, `partial_use`, `priority`, `cumulative_with_other_rules`) basierend auf der Konfiguration und den CSV-Daten.
  - Die Methode `add()` von `CartRule` wird verwendet, um die neuen Gutscheinregeln in der Datenbank zu speichern.
- **`CartRuleProduct` (PrestaShop-Kernklasse):**

  - Interagiert mit den Tabellen `ps_cart_rule_product_rule_group` und `ps_cart_rule_product_rule`.
  - Wird verwendet, wenn die Option „Rabatt anwenden auf: Ausgewählte Produkte“ gewählt wird, um die Warenkorbregel mit bestimmten Produkten, Kategorien oder Herstellern zu verknüpfen.

### 4.4 JavaScript-Assets (`views/js/`)

- `importvoucher/lib/voucherengine/script.js`:
  - **Umfang:** Back-Office.
  - **Zweck:** Dieses Skript behandelt wahrscheinlich dynamische Interaktionen auf der Konfigurationsseite des Moduls. Dies könnte Folgendes umfassen:
    - Anzeigen/Ausblenden von Feldern basierend auf ausgewählten Optionen (z.B. Anzeigen des „Wert“-Eingabefeldes nur, wenn der Rabatttyp „Prozentsatz“ oder „Betrag“ ausgewählt ist).
    - AJAX-Aufrufe zur Formularvalidierung oder -verarbeitung.
    - Initialisierung des Datumswählers für „Ablaufdatum (Von)“ und „Ablaufdatum (Bis)“.
    - Potenziell clientseitige CSV-Parsing-Vorschauen oder Fehlerbehandlung.
  - **Interaktion:** Bindet Event-Listener an Formularelemente (z.B. `change`-Ereignisse an Radio-Buttons, `click` an Schaltflächen).

### 4.5 CSS-Stylesheets (`views/css/`)

- `importvoucher/lib/voucherengine/ps16.css`:

  - **Umfang:** Back-Office (wahrscheinlich für PrestaShop 1.6-Kompatibilität, kann aber auch in neueren Versionen für allgemeines Styling geladen werden).
  - **Zweck:** Bietet Styling für die Konfigurationsoberfläche des Moduls, um sicherzustellen, dass es sich visuell in das PrestaShop 1.6 Back Office-Theme integriert. Kann allgemeines Styling für Formularelemente, Layoutanpassungen und spezifische klassenbasierte Stile für Modulkomponenten enthalten.
  - **Schlüsselselektoren:** Zielt wahrscheinlich auf generische Formularelemente (`.form-group`, `.control-label`, `.form-control`) und potenziell modulspezifische Wrapper (z.B. `#module_form_importvoucher`).
- `importvoucher/views/css/css.css`:

  - **Umfang:** Back-Office.
  - **Zweck:** Enthält allgemeine oder spezifische Styling-Regeln für die Konfigurationsseite des Moduls. Dies könnte `ps16.css` für neuere PrestaShop-Versionen überschreiben oder erweitern oder ein einzigartiges Styling für benutzerdefinierte Elemente innerhalb der Modulvorlage bereitstellen.
  - **Schlüsselselektoren:** Ähnlich wie `ps16.css`, konzentriert sich auf die UI-Elemente des Moduls. Entwickler sollten diese Datei auf spezifische Klassennamen überprüfen, um sie bei Bedarf in ihren benutzerdefinierten Admin-Themes zu überschreiben.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

Das Modul verwendet Smarty-Vorlagen zur Darstellung seiner Back-Office-Konfigurationsoberfläche.

- **`importvoucher/views/backoffice.tpl`**:

  - **Umfang:** Admin-Vorlage.
  - **Zweck:** Dies ist wahrscheinlich die Hauptvorlagendatei, die von der `getContent()`-Methode gerendert wird. Sie dient als Container für das gesamte Modulkonfigurationsformular, einschließlich aller Einstellungen, Eingabefelder und Schaltflächen. Sie enthält wahrscheinlich andere Teilvorlagen.
  - **Inhalt:** Enthält die HTML-Struktur für die Konfigurationsseite des Moduls, einschließlich Formular-Tags, Fieldsets und potenziell Aufrufe zum Einbinden anderer `.tpl`-Dateien.
- **`importvoucher/views/csv.tpl`**:

  - **Umfang:** Admin-Vorlage.
  - **Zweck:** Diese Vorlage behandelt wahrscheinlich die Anzeige des CSV-Dateiupload-Bereichs und verwandter Einstellungen (Trennzeichen, Begrenzer, Header überspringen). Es ist eine Teilvorlage, die in `backoffice.tpl` enthalten ist.
- **`importvoucher/views/csv_file.tpl`**:

  - **Umfang:** Admin-Vorlage.
  - **Zweck:** Eine granularere Teilvorlage, möglicherweise speziell für das Dateieingabefeld selbst oder zur Anzeige von Informationen über die hochgeladene CSV-Datei.
- **`importvoucher/views/file_settings.tpl`**:

  - **Umfang:** Admin-Vorlage.
  - **Zweck:** Diese Vorlage rendert wahrscheinlich den Abschnitt „CSV-Dateieinstellungen“, einschließlich Eingaben für CSV-Trennzeichen, Textbegrenzer und das Kontrollkästchen „Erste Zeile überspringen“.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen:**
  Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es interagiert direkt mit den PrestaShop-Kerntabellen, die sich auf Warenkorbregeln beziehen:

  - `ps_cart_rule`: Speichert die Haupteigenschaften jeder Rabattregel (Name, Code, Daten, Mindestbetrag usw.).
  - `ps_cart_rule_lang`: Speichert sprachspezifische Felder für Warenkorbregeln (z.B. `name`, wenn mehrsprachig).
  - `ps_cart_rule_product_rule_group`: Wird verwendet, wenn Rabatte auf bestimmte Produkte/Kategorien angewendet werden.
  - `ps_cart_rule_product_rule`: Definiert die tatsächlichen Produktregeln innerhalb einer Gruppe.
  - `ps_cart_rule_product_rule_exclusion`: Zum Ausschließen bestimmter Produkte von einer Regel.
  - `ps_cart_rule_carrier`: Für Trägerbeschränkungen.
  - `ps_cart_rule_country`: Für Länderbeschränkungen.
  - `ps_cart_rule_group`: Für Kundengruppenbeschränkungen.
  - `ps_cart_rule_shop`: Für Multi-Store-Kontext.
- **Registrierte Hooks-Tabelle:**
  Die Hauptfunktion des Moduls liegt in der Back-Office-Konfiguration. Obwohl die Modulbeschreibung „Front-Office Hooks: Header, Columns, Product, or Footer“ erwähnt, deuten das bereitgestellte Dateiverzeichnis und die typische Funktionalität eines Importmoduls darauf hin, dass es keine Inhalte in diesen Front-Office-Hooks aktiv rendert. Diese Erwähnungen könnten generisch sein oder sich darauf beziehen, wo die *Auswirkungen* der importierten Gutscheine sichtbar sind (z.B. ein im Warenkorb angewendeter Gutschein, der Teil des Checkout-Flows ist und möglicherweise durch Hooks beeinflusst wird).

  Das Modul verwendet hauptsächlich den folgenden Hook für seine Back-Office-Oberfläche:

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `displayBackOfficeHeader` | Wird im `<head>`-Bereich der Back-Office-Seiten gerendert. | Wird verwendet, um CSS- und JavaScript-Assets für die Konfigurationsseite des Moduls einzubinden. |
  | `moduleRoutes` (PrestaShop 1.7+) | Wenn Modulrouten initialisiert werden. | Wenn das Modul benutzerdefinierte Front-Controller hätte, würde dieser Hook deren URLs definieren. (Hier nicht anwendbar, da keine benutzerdefinierten Front-Controller vorhanden sind). |

  Die Kernlogik des Moduls zum *Erstellen* von Gutscheinen basiert nicht auf spezifischen PrestaShop-Hooks, sondern auf direkten Aufrufen von `CartRule`-Methoden, die durch die Formularübermittlung in `getContent()` ausgelöst werden.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Gutscheine aus CSV importieren“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu). Unser Support-Team steht Ihnen bei Fragen oder Problemen bezüglich der Funktionalität und Kompatibilität des Moduls gerne zur Verfügung.
