---
title: "Gutschein-Generator - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Gutschein-Generator von MyPresta.eu."
sidebar:
  label: "Gutschein-Generator - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Vouchers Generator auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/vouchers-generator.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/vouchers-generator/)
>
> ---


# Gutschein-Generator

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind keine ungewöhnlichen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation des Moduls navigieren Sie zu **Module > Modul-Manager** und klicken Sie neben „Gutschein-Generator“ auf „Konfigurieren“. Dies ist der Hauptbildschirm, auf dem Sie alle Einstellungen verwalten und Ihre Gutscheine generieren.

Die Konfigurationsseite ist intuitiv gestaltet und ermöglicht es Ihnen, die Regeln für Ihre neuen Gutscheine zu definieren und diese dann zu generieren.

#### **1. Gutschein-Generierungs-Einstellungen**

Dieser Abschnitt ermöglicht es Ihnen, die Kerneigenschaften der Gutscheine zu definieren, die Sie generieren möchten.

- **Name:**

  - **Was diese Einstellung bewirkt:** Dies ist der Name, der in Ihrem PrestaShop Back Office unter „Katalog > Rabatte > Warenkorb-Regeln“ für den generierten Gutschein-Batch angezeigt wird. Es ist auch der Basisname für die einzelnen Gutscheincodes (z.B. wenn Sie „SOMMER2024“ einstellen, könnten die Codes „SOMMER2024-ABCDE“, „SOMMER2024-FGHIJ“ lauten).
  - **Auswirkung einer Änderung dieser Einstellung:** Ein klarer und beschreibender Name hilft Ihnen, den Zweck des Gutschein-Batches später zu identifizieren.
  - **Empfohlener Wert:** Etwas Beschreibendes wie „Sommer-Sale 2024“, „Willkommen neuer Kunde“ oder „Warenkorb-Wiederherstellung“.
  - **Händlerszenario / Beispiel:** Sie führen eine Sommeraktion durch. Sie könnten sie „SOMMER2024“ nennen.
- **Beschreibung:**

  - **Was diese Einstellung bewirkt:** Eine interne Notiz für Ihre Referenz, nur im Back Office sichtbar. Sie hilft Ihnen, die spezifischen Details oder Ziele dieser Gutscheinkampagne zu erinnern.
  - **Auswirkung einer Änderung dieser Einstellung:** Bietet Kontext für Sie und Ihr Team.
  - **Empfohlener Wert:** Eine kurze Erklärung, z.B. „20% Rabatt auf alle Bestellungen über 50 €, gültig für 1 Monat, verteilt über E-Mail-Newsletter.“
  - **Händlerszenario / Beispiel:** Für die Kampagne „SOMMER2024“ könnten Sie hinzufügen „20% Rabatt auf alle Produkte, Mindestbestellwert 50 €, gültig bis 31. August.“
- **Hervorheben:**

  - **Was diese Einstellung bewirkt:** Wenn aktiviert, wird dieser Gutschein in der Warenkorbzusammenfassung für alle Kunden angezeigt, auch wenn sie ihn nicht eingegeben haben. Dies wird typischerweise für allgemeine, öffentliche Aktionen verwendet.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der Gutschein erscheint automatisch in der Warenkorbzusammenfassung und ermutigt Kunden, ihn zu verwenden.
    - *Wenn deaktiviert:* Der Gutschein wird nur angewendet, wenn der Kunde den Code explizit eingibt.
  - **Empfohlener Wert:** „NEIN“ für einzigartige, zielgerichtete Gutscheine; „JA“ für shopweite, öffentliche Aktionen.
  - **Händlerszenario / Beispiel:** Wenn Sie einzigartige Codes an bestimmte Kunden vergeben, deaktivieren Sie dies. Wenn es eine allgemeine „10% Rabatt auf alles“-Aktion ist, aktivieren Sie dies.
- **Teilweise Nutzung:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob ein Gutschein mehrmals verwendet werden kann, wenn sein Wert den Bestellwert übersteigt.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Wenn ein Kunde einen 50 € Gutschein hat und einen Artikel für 30 € kauft, verbleibt ein Restbetrag von 20 € auf demselben Gutschein für einen zukünftigen Einkauf.
    - *Wenn deaktiviert:* Wenn ein Kunde einen 50 € Gutschein hat und einen Artikel für 30 € kauft, wird der gesamte 50 € Gutschein verbraucht und es verbleibt kein Restbetrag.
  - **Empfohlener Wert:** „NEIN“ für die meisten Aktionen, um die vollständige Nutzung zu fördern oder komplexe Nachverfolgung zu verhindern. „JA“ für Geschenkkarten oder Shop-Guthaben.
  - **Händlerszenario / Beispiel:** Für einen Standardrabatt würden Sie dies typischerweise deaktivieren. Für einen Geschenkgutschein würden Sie es aktivieren.
- **Priorität:**

  - **Was diese Einstellung bewirkt:** Legt die Reihenfolge fest, in der Warenkorb-Regeln angewendet werden, wenn mehrere Regeln aktiv sind. Eine niedrigere Zahl bedeutet höhere Priorität (wird zuerst angewendet).
  - **Auswirkung einer Änderung dieser Einstellung:** Beeinflusst, wie Rabatte gestapelt werden. Wenn zwei Gutscheine gelten, wird derjenige mit höherer Priorität zuerst verarbeitet.
  - **Empfohlener Wert:** Bei Standardeinstellung (1) belassen, es sei denn, Sie haben komplexe Stapelregeln.
  - **Händlerszenario / Beispiel:** Wenn Sie einen „Kostenloser Versand“-Gutschein (Priorität 1) und einen „10% Rabatt“-Gutschein (Priorität 2) haben, wird der kostenlose Versand vor dem prozentualen Rabatt berechnet.
- **Status:**

  - **Was diese Einstellung bewirkt:** Aktiviert oder deaktiviert die generierten Gutscheine.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Gutscheine sind aktiv und können von Kunden verwendet werden.
    - *Wenn deaktiviert:* Gutscheine sind inaktiv und können nicht verwendet werden.
  - **Empfohlener Wert:** „JA“, wenn die Gutscheine sofort nutzbar sein sollen. Sie können sie bei Bedarf später deaktivieren.
  - **Händlerszenario / Beispiel:** Sie generieren Gutscheine für einen zukünftigen Sale. Sie könnten sie am Tag des Sale-Starts aktivieren.

#### **2. Gutschein-Bedingungen**

Dieser Abschnitt definiert, wann und wie die generierten Gutscheine verwendet werden können.

- **Gültig ab:**

  - **Was diese Einstellung bewirkt:** Legt das Startdatum fest, ab dem die Gutscheine aktiv werden.
  - **Auswirkung einer Änderung dieser Einstellung:** Gutscheine können vor diesem Datum nicht verwendet werden.
  - **Empfohlener Wert:** Das heutige Datum, wenn sie sofort aktiv sein sollen, oder ein zukünftiges Datum für eine geplante Aktion.
  - **Händlerszenario / Beispiel:** Für eine Juli-Aktion auf „2024-07-01“ setzen.
- **Gültig bis:**

  - **Was diese Einstellung bewirkt:** Legt das Enddatum fest, nach dem die Gutscheine ablaufen.
  - **Auswirkung einer Änderung dieser Einstellung:** Gutscheine können nach diesem Datum nicht mehr verwendet werden.
  - **Empfohlener Wert:** Ein angemessenes Ablaufdatum für Ihre Aktion (z.B. 1 Woche, 1 Monat, Saisonende).
  - **Händlerszenario / Beispiel:** Für eine Juli-Aktion auf „2024-07-31“ setzen.
- **Mindestbetrag:**

  - **Was diese Einstellung bewirkt:** Der minimale Gesamtbestellwert (vor Versand und Steuern), der für die Gültigkeit des Gutscheins erforderlich ist.
  - **Auswirkung einer Änderung dieser Einstellung:** Wenn der Warenkorbwert des Kunden unter diesem Betrag liegt, kann der Gutschein nicht angewendet werden.
  - **Empfohlener Wert:** Setzen Sie einen Wert, der höhere durchschnittliche Bestellwerte fördert, oder 0, wenn kein Minimum erforderlich ist.
  - **Händlerszenario / Beispiel:** Auf „50.00“ setzen, um einen Rabatt nur für Bestellungen über 50 € anzubieten.
- **Gesamt verfügbar:**

  - **Was diese Einstellung bewirkt:** Die Gesamtzahl der Verwendungen, die *alle* generierten Gutscheine in diesem Batch über *alle* Kunden hinweg haben können.
  - **Auswirkung einer Änderung dieser Einstellung:** Sobald dieses Limit erreicht ist, können keine weiteren Gutscheine aus diesem Batch verwendet werden, auch wenn einzelne Codes noch Verwendungen übrig hätten.
  - **Empfohlener Wert:** Eine hohe Zahl (z.B. 99999), wenn individuelle Code-Limits gelten sollen, oder eine spezifische Zahl für eine zeitlich begrenzte, gesamt-nutzungsbasierte Kampagne.
  - **Händlerszenario / Beispiel:** Wenn Sie 100 einzigartige Codes generieren und „Gesamt verfügbar“ auf 50 setzen, sind nur die ersten 50 Verwendungen über alle Codes hinweg gültig.
- **Gesamt verfügbar pro Benutzer:**

  - **Was diese Einstellung bewirkt:** Die maximale Anzahl, wie oft *jeder einzelne Kunde* *einen* der Gutscheine aus diesem Batch verwenden kann.
  - **Auswirkung einer Änderung dieser Einstellung:** Verhindert, dass ein einzelner Kunde wiederholt verschiedene Codes aus demselben Batch verwendet.
  - **Empfohlener Wert:** „1“ für die meisten einzigartigen Gutscheinkampagnen, um sicherzustellen, dass jeder Kunde eine Verwendung erhält. „0“ für unbegrenzte Verwendungen pro Kunde (nicht empfohlen für einzigartige Codes).
  - **Händlerszenario / Beispiel:** Auf „1“ setzen, um sicherzustellen, dass jeder Kunde nur von einem Ihrer generierten Codes profitieren kann.

#### **3. Gutschein-Aktionen**

Dieser Abschnitt definiert, was der Gutschein tatsächlich bewirkt, wenn er angewendet wird.

- **Kostenloser Versand:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob der Gutschein kostenlosen Versand gewährt.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Versandkosten entfallen für Bestellungen, die diesen Gutschein verwenden.
    - *Wenn deaktiviert:* Standardversandkosten fallen an.
  - **Empfohlener Wert:** „NEIN“, es sei denn, es handelt sich um eine spezielle Aktion für kostenlosen Versand.
  - **Händlerszenario / Beispiel:** Für eine „Kostenloser Versand Wochenende“-Aktion würden Sie dies aktivieren.
- **Rabatt anwenden:**

  - **Was diese Einstellung bewirkt:** Hier definieren Sie den tatsächlichen Rabattbetrag oder Prozentsatz.
  - **Auswirkung einer Änderung dieser Einstellung:** Bestimmt den monetären Wert des Rabatts.
  - **Empfohlener Wert:** Wählen Sie eine Art von Rabatt (Prozentsatz, Betrag oder spezifisches Produkt) und füllen Sie die Details aus.
  - **Händlerszenario / Beispiel:** Sie möchten 15% Rabatt anbieten.
  - **Prozentsatz:**

    - **Was diese Einstellung bewirkt:** Wendet einen prozentualen Rabatt auf den Gesamtbestellwert an.
    - **Auswirkung einer Änderung dieser Einstellung:** Reduziert den Gesamtbestellwert um den angegebenen Prozentsatz.
    - **Empfohlener Wert:** Ein gängiger Prozentsatz wie 5, 10, 15, 20.
    - **Händlerszenario / Beispiel:** Geben Sie „15“ für 15% Rabatt ein.
  - **Betrag:**

    - **Was diese Einstellung bewirkt:** Wendet einen festen monetären Rabatt auf den Gesamtbestellwert an.
    - **Auswirkung einer Änderung dieser Einstellung:** Reduziert den Gesamtbestellwert um den angegebenen Betrag.
    - **Empfohlener Wert:** Ein fester Betrag wie 5.00, 10.00, 25.00.
    - **Händlerszenario / Beispiel:** Geben Sie „10.00“ für 10 € Rabatt ein.
  - **Rabatt anwenden auf:**

    - **Was diese Einstellung bewirkt:** Gibt an, auf welchen Teil der Bestellung der Rabatt angewendet wird.
    - **Auswirkung einer Änderung dieser Einstellung:**
      - *Bestellung (ohne Versand):* Rabatt gilt nur für den Produktgesamtbetrag.
      - *Spezifisches Produkt:* Rabatt gilt nur für ein bestimmtes Produkt oder eine Auswahl von Produkten.
      - *Günstigstes Produkt:* Rabatt gilt für den preisgünstigsten Artikel im Warenkorb.
      - *Ausgewählte Produkte:* Rabatt gilt für eine spezifische Liste von Produkten, die Sie definieren.
    - **Empfohlener Wert:** „Bestellung (ohne Versand)“ für allgemeine Rabatte.
    - **Händlerszenario / Beispiel:** Für einen allgemeinen 15% Rabatt wählen Sie „Bestellung (ohne Versand)“. Wenn Sie 20% Rabatt nur auf „T-Shirts“ möchten, wählen Sie „Ausgewählte Produkte“ und dann die T-Shirt-Kategorie/Produkte aus.
- **Geschenk senden:**

  - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, automatisch ein bestimmtes Produkt als kostenloses Geschenk hinzuzufügen, wenn der Gutschein verwendet wird.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein ausgewähltes Produkt wird kostenlos zum Warenkorb des Kunden hinzugefügt.
    - *Wenn deaktiviert:* Es wird kein kostenloses Geschenk bereitgestellt.
  - **Empfohlener Wert:** „NEIN“, es sei denn, es handelt sich um eine spezielle Geschenk-Aktion beim Kauf.
  - **Händlerszenario / Beispiel:** Sie möchten einen kostenlosen „Schlüsselanhänger“ zu jeder Bestellung über 100 € hinzufügen. Sie würden dies aktivieren und das Produkt Schlüsselanhänger auswählen.

#### **4. Gutschein-Generierung**

Dies ist der letzte Schritt, in dem Sie definieren, wie viele Codes generiert werden sollen, und dann die Generierung ausführen.

- **Anzahl der zu generierenden Gutscheine:**

  - **Was diese Einstellung bewirkt:** Gibt an, wie viele einzigartige Gutscheincodes das Modul erstellen soll.
  - **Auswirkung einer Änderung dieser Einstellung:** Bestimmt die Menge der einzelnen Rabattcodes, die zu Ihren PrestaShop-Warenkorb-Regeln hinzugefügt werden.
  - **Empfohlener Wert:** Die genaue Anzahl der einzigartigen Codes, die Sie für Ihre Kampagne benötigen (z.B. 100 für eine E-Mail-Liste, 500 für ein Social-Media-Gewinnspiel).
  - **Händlerszenario / Beispiel:** Sie benötigen 250 einzigartige Codes für eine Marketingkampagne. Geben Sie „250“ ein.
- **Gutscheine generieren Schaltfläche:**

  - **Was diese Einstellung bewirkt:** Diese Schaltfläche initiiert den Prozess der Erstellung aller Gutscheine basierend auf den oben konfigurierten Einstellungen.
  - **Auswirkung einer Änderung dieser Einstellung:** Das Klicken auf diese Schaltfläche erstellt die angegebene Anzahl einzigartiger Warenkorb-Regeln in Ihrem PrestaShop-Shop. Eine Bestätigungsmeldung wird angezeigt, und Sie können eine CSV-/Excel-Datei mit den generierten Codes herunterladen.
  - **Empfohlener Wert:** Klicken Sie dies nur, wenn Sie absolut sicher sind, dass alle Ihre Einstellungen korrekt sind.
  - **Händlerszenario / Beispiel:** Nachdem Sie alle Einstellungen für Ihre „SOMMER2024“-Kampagne überprüft und die Anzahl der Gutscheine auf 250 festgelegt haben, klicken Sie auf „Gutscheine generieren“.

#### **5. MyPresta.eu Updates & Informationen**

Dieser Abschnitt enthält typischerweise Informationen über die Modulversion, die Verfügbarkeit von Updates und Links zu MyPresta.eu.

- **MyPresta.eu Updates / Update-Prüfung:**
  - **Was diese Einstellung bewirkt:** Ermöglicht dem Modul, nach neuen Versionen von MyPresta.eu zu suchen.
  - **Auswirkung einer Änderung dieser Einstellung:** Hilft Ihnen, Ihr Modul mit den neuesten Funktionen und Fehlerbehebungen auf dem neuesten Stand zu halten.
  - **Empfohlener Wert:** Lassen Sie dies aktiviert, um Benachrichtigungen über Updates zu erhalten.
  - **Händlerszenario / Beispiel:** Sie sehen eine Benachrichtigung, dass eine neue Version verfügbar ist, um sicherzustellen, dass Sie die stabilste und funktionsreichste Version haben.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Name | Beschreibender Text | Interner Name für den Gutschein-Batch. |
| Modulkonfiguration | Beschreibung | Optionaler Text | Interne Notizen für Kampagnendetails. |
| Modulkonfiguration | Hervorheben | NEIN | Gutschein in der Warenkorbzusammenfassung anzeigen (JA für öffentlich, NEIN für privat). |
| Modulkonfiguration | Teilweise Nutzung | NEIN | Erlaubt die mehrfache Nutzung des Gutscheins, wenn der Wert > Bestellung ist. |
| Modulkonfiguration | Priorität | 1 | Anwendungsreihenfolge für mehrere Warenkorb-Regeln (niedriger = höhere Priorität). |
| Modulkonfiguration | Status | JA | Generierte Gutscheine aktivieren/deaktivieren. |
| Modulkonfiguration | Gültig ab | Aktuelles Datum | Startdatum für die Gutscheingültigkeit. |
| Modulkonfiguration | Gültig bis | Zukünftiges Datum | Enddatum für die Gutscheingültigkeit. |
| Modulkonfiguration | Mindestbetrag | 0.00 | Mindestkaufbetrag für die Gutscheinnutzung. |
| Modulkonfiguration | Gesamt verfügbar | Hohe Zahl (z.B. 99999) | Gesamtzahl der Verwendungen für ALLE Gutscheine in diesem Batch. |
| Modulkonfiguration | Gesamt verfügbar pro Benutzer | 1 | Max. Verwendungen pro Kunde für jeden Gutschein in diesem Batch. |
| Modulkonfiguration | Kostenloser Versand | NEIN | Kostenlosen Versand mit Gutschein gewähren. |
| Modulkonfiguration | Rabatt anwenden | JA | Rabattanwendung aktivieren. |
| Modulkonfiguration | Prozentsatz | (z.B. 10) | Prozentualer Rabatt. |
| Modulkonfiguration | Betrag | (z.B. 10.00) | Fester monetärer Rabatt. |
| Modulkonfiguration | Rabatt anwenden auf | Bestellung (ohne Versand) | Umfang des Rabatts (Bestellung, spezifisches Produkt usw.). |
| Modulkonfiguration | Geschenk senden | NEIN | Ein kostenloses Produkt als Geschenk hinzufügen. |
| Modulkonfiguration | Anzahl der zu generierenden Gutscheine | (z.B. 100) | Menge der zu erstellenden einzigartigen Codes. |
| Modulkonfiguration | Gutscheine generieren Schaltfläche | Klicken, wenn bereit | Initiiert die Gutscheinerstellung und den CSV-Export. |
| Modulkonfiguration | MyPresta.eu Updates | JA | Nach Modul-Updates suchen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe Gutscheine generiert, aber sie scheinen im Front Office nicht zu funktionieren.**
A1:

- **Status & Daten überprüfen:** Gehen Sie in Ihrem PrestaShop Back Office zu „Katalog > Rabatte > Warenkorb-Regeln“. Suchen Sie die von Ihnen generierten Gutscheine. Stellen Sie sicher, dass ihr „Status“ auf „Ja“ gesetzt ist und dass die Daten „Gültig ab“ und „Gültig bis“ aktuell sind.
- **Mindestbetrag:** Überprüfen Sie, ob der Warenkorb des Kunden die für den Gutschein festgelegte „Mindestbetrag“-Anforderung erfüllt.
- **Bedingungen:** Überprüfen Sie alle anderen von Ihnen festgelegten Bedingungen (z.B. spezifische Produkte, Kundengruppen).
- **Cache:** Leeren Sie Ihren PrestaShop-Cache (Erweiterte Einstellungen > Leistung > Cache leeren).

**F2: Kann ich die generierten Gutscheine nach ihrer Erstellung bearbeiten?**
A2: Ja, einmal generiert, wird jeder Gutschein zu einer Standard-„Warenkorb-Regel“ in PrestaShop. Sie können in Ihrem Back Office zu „Katalog > Rabatte > Warenkorb-Regeln“ gehen, die einzelnen Gutscheine finden (sie teilen sich normalerweise den von Ihnen angegebenen Basisnamen) und deren Eigenschaften (z.B. Ablaufdatum, Rabattbetrag, Bedingungen) einzeln bearbeiten. Es ist jedoch im Allgemeinen besser, alle Einstellungen vor der Generierung korrekt festzulegen.

**F3: Wie erhalte ich die Liste der generierten Gutscheincodes?**
A3: Unmittelbar nach dem Klicken auf die Schaltfläche „Gutscheine generieren“ fordert das Modul Sie auf, eine CSV-/Excel-Datei mit allen einzigartigen Codes herunterzuladen. Wenn Sie dies verpasst haben, können Sie die Liste nicht direkt vom Modul erneut herunterladen. Sie müssten die „Warenkorb-Regeln“ manuell aus „Katalog > Rabatte > Warenkorb-Regeln“ in PrestaShop exportieren oder direkt auf die Datenbank zugreifen (Entwickleraufgabe). Es ist entscheidend, die CSV-Datei sofort nach der Generierung zu speichern.

**F4: Das Modul zeigt „MyPresta.eu Updates“ an, aber keine neue Version.**
A4: Das bedeutet, dass Ihr Modul derzeit auf dem neuesten Stand der offiziellen Version von MyPresta.eu ist. Es ist keine Aktion erforderlich.

**F5: Mein benutzerdefiniertes Theme zeigt das Gutscheineingabefeld nicht korrekt an.**
A5: Das Gutschein-Generator-Modul fügt keine Front-Office-Elemente hinzu. Das Gutscheineingabefeld ist eine Standard-PrestaShop-Funktion. Wenn es nicht korrekt angezeigt wird, liegt dies wahrscheinlich an der Formatierung Ihres benutzerdefinierten Themes oder an Template-Overrides für die Warenkorb-/Checkout-Seiten. Sie müssten Ihren Theme-Entwickler oder einen Webmaster konsultieren, um die CSS- oder TPL-Dateien anzupassen, die mit den Hooks `displayCart` oder `displayPaymentTop` zusammenhängen, wo das Gutscheinfeld typischerweise erscheint.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Gutschein-Generator-Modul (`vouchers`) ist ein Standard-PrestaShop-Modul, das hauptsächlich im Back Office arbeitet. Es nutzt die Kernfunktionalität von PrestaShop `CartRule`, um mehrere Rabattcodes effizient zu erstellen. Die Hauptlogik des Moduls befindet sich in seiner `vouchers.php`-Datei und handhabt die Konfiguration und den Generierungsprozess. Es führt keine komplexen MVC-Muster oder benutzerdefinierten Datenbanktabellen ein, sondern interagiert direkt mit dem bestehenden `CartRule`-Objektmodell von PrestaShop.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Das Modul fügt keine benutzerdefinierten Front-Office-Controller hinzu. Alle Front-Office-Interaktionen im Zusammenhang mit Gutscheinen werden von PrestaShops nativem `CartController` oder `OrderController` gehandhabt.
- **Back-Office-Admin-Controller**: Keine. Die Konfigurations- und Generierungslogik des Moduls ist vollständig in der `getContent()`-Methode der Hauptmodulklasse enthalten, die vom Standard `AdminModulesController` gerendert wird.

### 4.3 Kernklassen & Modelle (`classes/`)

- Keine. Das Modul definiert keine benutzerdefinierten Klassen oder erweitert `ObjectModel`. Es verwendet direkt die native `CartRule`-Klasse von PrestaShop zum Erstellen und Verwalten von Gutscheinen.

### 4.4 JavaScript-Assets (`views/js/`)

- `vouchers/lib/voucherengine/script.js`
  - **Umfang:** Back-Office.
  - **Zweck:** Dieses Skript enthält wahrscheinlich clientseitige Logik für die Konfigurationsseite des Moduls. Dies könnte umfassen:
    - Formularvalidierung vor der Gutscheingenerierung.
    - AJAX-Aufrufe an die `getContent()`-Methode des Moduls für dynamische Updates oder Verarbeitung.
    - UI-Verbesserungen oder Interaktionen, die spezifisch für das Gutschein-Generierungsformular sind.
    - Potenziell die Handhabung des Downloads der generierten CSV-Datei.
  - **Event-Listener:** Bindet wahrscheinlich an Formular-Submit-Events, Input-Change-Events und Button-Klicks auf der Modulkonfigurationsseite.
  - **DOM-Manipulation:** Kann Elemente basierend auf Benutzerauswahlen ein-/ausblenden (z.B. Anzeige spezifischer Produktauswahlfelder, wenn „Rabatt anwenden auf: Spezifisches Produkt“ gewählt wird).

### 4.5 CSS-Stylesheets (`views/css/`)

- `vouchers/lib/voucherengine/ps16.css`
  - **Umfang:** Back-Office-Admin-Formular-Styling.
  - **Zweck:** Bietet spezifisches Styling für die Konfigurationsoberfläche des Moduls, möglicherweise um ein konsistentes Erscheinungsbild über verschiedene PrestaShop-Versionen hinweg zu gewährleisten (z.B. Anpassung an die spezifische Admin-Theme-Struktur von PrestaShop 1.6).
  - **Haupt-UI-Komponenten:** Stile Formularfelder, Schaltflächen und Layout-Elemente innerhalb der `getContent()`-Ausgabe des Moduls.
  - **Wichtige CSS-Klassenselektoren:** Entwickler können die Konfigurationsseite des Moduls im Browser inspizieren, um spezifische Klassen (z.B. `.vouchers-generator-form`, `.mypresta-update-block`) zu identifizieren, die bei Bedarf in einem benutzerdefinierten Admin-Theme überschrieben werden können.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- `vouchers/views/pdf.tpl`
  - **Umfang:** Back-Office / Dienstprogramm.
  - **Zweck:** Dieses Template wird wahrscheinlich zur Generierung eines druckbaren oder herunterladbaren PDF-Dokuments verwendet, das die Liste der generierten Gutscheine enthält. Während die Modulbeschreibung den CSV-/Excel-Export erwähnt, deutet ein PDF-Template auf ein alternatives oder zusätzliches Ausgabeformat für die Gutscheinliste hin, möglicherweise zum Drucken physischer Gutscheine.
  - **Verwendung:** Es würde gerendert, wenn das Modul die generierten Gutscheincodes in einem strukturierten, druckbaren Format präsentieren muss. Es würde ein Array von Gutscheindaten (Code, Wert, Ablaufdatum usw.) von der PHP-Logik erhalten.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten Datenbanktabellen.
  - Es interagiert mit den nativen PrestaShop-Tabellen `ps_cart_rule` und `ps_cart_rule_lang`, um die generierten Gutscheine zu speichern.
  - Konfigurationseinstellungen (wie `vg_counter`, `mypresta_updates`) werden in der Tabelle `ps_configuration` gespeichert.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin-Controller initialisiert wird und seine Medien (JS/CSS) gesetzt werden. | Wird vom Modul verwendet, um seine Back-Office-JavaScript (`script.js`) und CSS (`ps16.css`)-Dateien speziell auf seiner Konfigurationsseite einzubinden, um sicherzustellen, dass sie nur bei Bedarf geladen werden. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Gutschein-Generator-Modul verweisen wir auf Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.
