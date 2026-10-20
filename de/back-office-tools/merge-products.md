---
title: "Produkte zusammenführen – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Produkte zusammenführen“ von MyPresta.eu."
sidebar:
  label: "Produkte zusammenführen – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Merge Products auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/merge-products.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/merge-products/)
>
> ---


# Produkte zusammenführen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Das Modul „Produkte zusammenführen“ bietet einen dedizierten Administrationsbildschirm zur Verwaltung des Zusammenführungsprozesses, der über Ihr PrestaShop Back Office zugänglich ist.

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Wenn Sie nach der Installation zum ersten Mal auf „Konfigurieren“ klicken, gelangen Sie zu einer Dashboard-ähnlichen Seite. Diese Seite dient hauptsächlich als Einstiegspunkt zum Haupt-Zusammenführungstool.

- **Was dieser Bildschirm tut:** Diese anfängliche Konfigurationsseite bietet einen kurzen Überblick und einen direkten Link zum Haupttool „Produkte zusammenführen“. Sie enthält selbst keine spezifischen Einstellungen, sondern führt Sie dorthin, wo die eigentliche Zusammenführung stattfindet.
- **Auswirkung der Änderung dieser Einstellung:** Auf diesem Startbildschirm gibt es keine direkten Einstellungen zu ändern.
- **Empfohlener Wert:** N/A
- **Händlerszenario / Beispiel:** Dies ist Ihr Ausgangspunkt. Von hier aus klicken Sie auf eine Schaltfläche oder einen Link, um auf die Kernfunktionalität des Moduls zuzugreifen.

### 2.2 Dedizierter Admin-Bildschirm: Produkte zusammenführen Tool (Back Office > Katalog > Produkte zusammenführen)

Dies ist die Hauptschnittstelle, über die Sie alle Produktzusammenführungsoperationen durchführen. Sie finden sie, indem Sie im PrestaShop Back Office-Menü zu **Katalog > Produkte zusammenführen** navigieren.

Dieser Bildschirm ist in mehrere Abschnitte unterteilt, um Sie durch den Zusammenführungsprozess zu führen:

#### Schritt 1: Master-Produkt auswählen

- **Was dieser Abschnitt tut:** Hier definieren Sie das „Master“-Produkt. Dies ist das Produkt, in das alle anderen ausgewählten „Quell“-Produkte zusammengeführt werden und dessen Kombinationen werden.
- **Eingabefeld: „Nach einem Produkt suchen“**
  - **Was diese Einstellung tut:** Ermöglicht Ihnen die Suche nach einem bestehenden Produkt in Ihrem Katalog, um es als Master-Produkt zu bestimmen. Sie können nach Produktname, ID, EAN oder Referenz suchen.
  - **Auswirkung der Änderung dieser Einstellung:** Während Sie tippen, erscheint eine Autocomplete-Liste. Die Auswahl eines Produkts füllt den Bereich „Master-Produkt“ mit dessen Details. Dieses Produkt wird die Basis für die neuen Kombinationen sein.
  - **Empfohlener Wert:** Wählen Sie das Produkt, das die konsolidierte Liste am besten repräsentiert. Wenn Sie beispielsweise „Rotes T-Shirt S“, „Rotes T-Shirt M“, „Rotes T-Shirt L“ zu einem zusammenführen, könnten Sie „Rotes T-Shirt S“ als Master wählen, und die anderen werden dessen Kombinationen.
  - **Händlerszenario / Beispiel:** Sie haben „iPhone 13 (Neu)“ und „iPhone 13 (Generalüberholt)“ als separate Produkte. Sie würden „iPhone 13 (Neu)“ suchen und als Ihr Master-Produkt auswählen.

#### Schritt 2: Quellprodukte auswählen

- **Was dieser Abschnitt tut:** Hier wählen Sie die Produkte aus, die in Kombinationen umgewandelt und dem Master-Produkt hinzugefügt werden.
- **Eingabefeld: „Nach Produkten zum Zusammenführen suchen“**
  - **Was diese Einstellung tut:** Ähnlich der Master-Produktsuche ermöglicht dieses Feld das Finden und Auswählen mehrerer Produkte, die zu Kombinationen werden sollen.
  - **Auswirkung der Änderung dieser Einstellung:** Jedes ausgewählte Produkt wird einer Liste darunter hinzugefügt. Dies sind die Produkte, deren Daten (Preis, Lagerbestand, Attribute) als neue Kombinationen auf das Master-Produkt übertragen werden.
  - **Empfohlener Wert:** Wählen Sie alle Produkte aus, die Variationen Ihres gewählten Master-Produkts sind und konsolidiert werden sollen.
  - **Händlerszenario / Beispiel:** Dem iPhone-Beispiel folgend, würden Sie hier „iPhone 13 (Generalüberholt)“ suchen und auswählen. Wenn Sie auch „iPhone 13 (Gebraucht - Klasse A)“ hätten, würden Sie auch dieses auswählen.

#### Schritt 3: Zusammenführungsoptionen konfigurieren

Dieser Abschnitt enthält wichtige Einstellungen, die steuern, wie der Zusammenführungsvorgang durchgeführt wird.

- **Option: Zusammenführungsmodus**

  - **Was diese Einstellung tut:** Bestimmt, wie die Attribute der Quellprodukte beim Erstellen von Kombinationen behandelt werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Neue Attributgruppe hinzufügen:* Das Modul erstellt eine neue Attributgruppe (z. B. „Zustand“) und ein Attribut für jedes Quellprodukt (z. B. „Neu“, „Generalüberholt“, „Gebraucht“). Dies ist ideal, wenn sich Quellprodukte durch ein Merkmal unterscheiden, das nicht bereits durch bestehende Attribute abgedeckt ist.
    - *Bestehende Attributgruppe verwenden:* Wenn Ihre Quellprodukte bereits eine gemeinsame Attributgruppe (z. B. „Größe“ oder „Farbe“) teilen und Sie diese darauf basierend zusammenführen möchten, können Sie dies auswählen. Dies ist weniger üblich für das Zusammenführen völlig separater Produkte, aber nützlich, um Variationen innerhalb einer bestehenden Attributstruktur zu konsolidieren.
  - **Empfohlener Wert:** **„Neue Attributgruppe hinzufügen“** wird im Allgemeinen für das Zusammenführen unterschiedlicher Produkte empfohlen, da es eine klare Möglichkeit bietet, die neuen Kombinationen zu unterscheiden.
  - **Händlerszenario / Beispiel:** Sie führen „Produkt X - Neu“ und „Produkt X - Gebraucht“ zusammen. Die Auswahl von „Neue Attributgruppe hinzufügen“ erstellt eine Attributgruppe „Zustand“ mit den Attributen „Neu“ und „Gebraucht“ für die Kombinationen.
- **Eingabefeld: Name der neuen Attributgruppe (nur sichtbar, wenn „Neue Attributgruppe hinzufügen“ ausgewählt ist)**

  - **Was diese Einstellung tut:** Gibt den Namen für die neue Attributgruppe an, die erstellt wird, um die zusammengeführten Kombinationen zu unterscheiden.
  - **Auswirkung der Änderung dieser Einstellung:** Dieser Name wird auf Ihrer Produktseite angezeigt (z. B. „Zustand“, „Qualität“, „Version“).
  - **Empfohlener Wert:** Ein beschreibender Name wie „Zustand“, „Status“, „Typ“ oder „Qualität“.
  - **Händlerszenario / Beispiel:** Wenn Sie „Neue“ und „Gebrauchte“ Produkte zusammenführen, könnten Sie „Zustand“ eingeben.
- **Option: Master-Produkt-Regel**

  - **Was diese Einstellung tut:** Definiert, wie das Master-Produkt selbst während der Zusammenführung behandelt wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Als Master-Produkt beibehalten:* Das Master-Produkt bleibt das Standardprodukt, und Quellprodukte werden zu seinen Kombinationen. Seine bestehenden Kombinationen (falls vorhanden) bleiben erhalten.
    - *In Kombination umwandeln:* Das Master-Produkt selbst wird ebenfalls in eine Kombination unter seinem eigenen Eintrag umgewandelt. Dies ist nützlich, wenn Sie möchten, dass alle Variationen, einschließlich des ursprünglichen Masters, über die neue Attributgruppe auswählbar sind.
  - **Empfohlener Wert:** **„Als Master-Produkt beibehalten“** ist oft ausreichend. Wählen Sie „In Kombination umwandeln“, wenn Sie möchten, dass der ursprüngliche Zustand des Master-Produkts explizit als Kombination auswählbar ist.
  - **Händlerszenario / Beispiel:** Wenn „iPhone 13 (Neu)“ Ihr Master ist und Sie „iPhone 13 (Generalüberholt)“ darin zusammenführen, bedeutet „Als Master-Produkt beibehalten“, dass „iPhone 13 (Neu)“ die Standardeinstellung ist. Wenn Sie „In Kombination umwandeln“ wählen, würde „Neu“ zu einer auswählbaren Option neben „Generalüberholt“.
- **Option: Aktion für Quellprodukt**

  - **Was diese Einstellung tut:** Bestimmt, was mit den ursprünglichen Quellprodukten geschieht, nachdem sie als Kombinationen in das Master-Produkt zusammengeführt wurden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Deaktivieren:* Die ursprünglichen Quellproduktseiten werden deaktiviert und sind für Kunden nicht mehr zugänglich. Dies ist im Allgemeinen die sicherste Option.
    - *Löschen:* Die ursprünglichen Quellproduktseiten werden dauerhaft aus Ihrem Katalog entfernt. Mit Vorsicht verwenden, da diese Aktion irreversibel ist.
    - *Nichts tun:* Die ursprünglichen Quellproduktseiten bleiben aktiv. Dies wird im Allgemeinen nicht empfohlen, da es zu doppeltem Inhalt und Verwirrung führen kann.
  - **Empfohlener Wert:** **„Deaktivieren“** ist die sicherste und häufigste Wahl. Wenn Sie sich Ihrer Zusammenführung und Weiterleitungen sicher sind, kann „Löschen“ Ihren Katalog bereinigen, aber stellen Sie sicher, dass Sie Backups haben.
  - **Händlerszenario / Beispiel:** Nachdem Sie „iPhone 13 (Generalüberholt)“ in „iPhone 13 (Neu)“ zusammengeführt haben, würden Sie typischerweise „Deaktivieren“ wählen, um zu verhindern, dass Kunden die alte Seite für das „Generalüberholte“ Produkt finden.
- **Option: 301-Weiterleitungen erstellen**

  - **Was diese Einstellung tut:** Wenn aktiviert, erstellt das Modul permanente (301) Weiterleitungen von den alten URLs der Quellprodukte zur neuen URL des Master-Produkts.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Aktiviert:* Jeder Kunde oder jede Suchmaschine, die versucht, eine alte Quellprodukt-URL aufzurufen, wird automatisch zur Master-Produktseite weitergeleitet. Dies ist entscheidend für SEO, die Erhaltung des Link-Werts und die Vermeidung defekter Links.
    - *Deaktiviert:* Alte Quellprodukt-URLs führen zu einem „Seite nicht gefunden“-Fehler, wenn das Quellprodukt deaktiviert oder gelöscht wird.
  - **Empfohlener Wert:** **JA (Aktiviert)**. Dies wird dringend für SEO und Benutzererfahrung empfohlen.
  - **Händlerszenario / Beispiel:** Ein Kunde hat die alte Seite für das „iPhone 13 (Generalüberholt)“ als Lesezeichen gespeichert. Mit aktivierten Weiterleitungen landet er automatisch auf der Master-Seite des „iPhone 13“.
- **Option: Stapelgröße**

  - **Was diese Einstellung tut:** Steuert, wie viele Produkte in einem einzigen Stapel während des Zusammenführungsvorgangs verarbeitet werden. Dies ist eine technische Einstellung, um Server-Timeouts bei großen Zusammenführungen zu verhindern.
  - **Auswirkung der Änderung dieser Einstellung:** Eine niedrigere Zahl reduziert die Serverlast, verlängert aber den Prozess. Eine höhere Zahl beschleunigt ihn, kann aber auf weniger leistungsstarkem Hosting Probleme verursachen.
  - **Empfohlener Wert:** Standardwert beibehalten, es sei denn, Sie erleben Timeouts. Wenn ja, versuchen Sie, ihn zu reduzieren.
  - **Händlerszenario / Beispiel:** Wenn Sie Hunderte von Produkten zusammenführen und der Prozess fehlschlägt, kann eine Reduzierung der Stapelgröße helfen.
- **Option: Nur aktive Produkte**

  - **Was diese Einstellung tut:** Wenn aktiviert, werden nur aktive Quellprodukte für die Zusammenführung berücksichtigt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Aktiviert:* Verhindert, dass inaktive Produkte zusammengeführt werden, was den Prozess vereinfachen und die Erstellung von Kombinationen für Produkte vermeiden kann, die Sie nicht verkaufen möchten.
    - *Deaktiviert:* Alle Produkte, aktiv oder inaktiv, können zusammengeführt werden.
  - **Empfohlener Wert:** **JA (Aktiviert)**, es sei denn, Sie müssen speziell inaktive Produkte zusammenführen.
  - **Händlerszenario / Beispiel:** Sie möchten nur Produkte zusammenführen, die derzeit in Ihrem Shop sichtbar und kaufbar sind.
- **Option: Pakete ausschließen**

  - **Was diese Einstellung tut:** Wenn aktiviert, werden Produkte, die als „Pakete“ (Bündel anderer Produkte) konfiguriert sind, von der Auswahl der Quellprodukte ausgeschlossen.
  - **Auswirkung der Änderung dieser Einstellung:** Verhindert das versehentliche Zusammenführen von Produktpaketen, die komplexe Beziehungen haben und sich bei der Umwandlung in Kombinationen möglicherweise nicht wie erwartet verhalten.
  - **Empfohlener Wert:** **JA (Aktiviert)**. Das Zusammenführen von Paketen kann zu unerwartetem Verhalten führen.
  - **Händlerszenario / Beispiel:** Sie haben ein „Starter-Kit“-Paket. Sie möchten nicht, dass dieses als Kombination in ein anderes Produkt zusammengeführt wird.
- **Option: Virtuelle Produkte ausschließen**

  - **Was diese Einstellung tut:** Wenn aktiviert, werden virtuelle Produkte (z. B. herunterladbare Dateien, Dienstleistungen) von der Auswahl der Quellprodukte ausgeschlossen.
  - **Auswirkung der Änderung dieser Einstellung:** Verhindert das versehentliche Zusammenführen von virtuellen Produkten, die typischerweise keine physischen Attribute oder Lagerbestände haben und möglicherweise nicht für die Umwandlung in Kombinationen geeignet sind.
  - **Empfohlener Wert:** **JA (Aktiviert)**. Virtuelle Produkte sind in der Regel keine guten Kandidaten für die Zusammenführung in physische Produktkombinationen.
  - **Händlerszenario / Beispiel:** Sie verkaufen ein herunterladbares E-Book. Sie möchten nicht, dass dieses als Kombination in ein physisches Buchprodukt zusammengeführt wird.
- **Option: Mindestgruppengröße**

  - **Was diese Einstellung tut:** Legt eine Mindestanzahl von Quellprodukten fest, die erforderlich sind, um eine neue Attributgruppe zu bilden.
  - **Auswirkung der Änderung dieser Einstellung:** Dies ist eine Schutzmaßnahme. Wenn Sie „Neue Attributgruppe hinzufügen“ auswählen, aber nur ein Quellprodukt zusammenführen, kann diese Einstellung die Erstellung einer unnötigen Attributgruppe mit nur einer Option verhindern.
  - **Empfohlener Wert:** Standardwert beibehalten (normalerweise 2).
  - **Händlerszenario / Beispiel:** Wenn Sie versehentlich nur ein Quellprodukt auswählen, kann dies verhindern, dass das Modul eine Attributgruppe mit nur einer Option erstellt, was redundant wäre.
- **Option: Zu verwendende Attributgruppe (nur sichtbar, wenn „Bestehende Attributgruppe verwenden“ ausgewählt ist)**

  - **Was diese Einstellung tut:** Ermöglicht Ihnen die Auswahl einer bestehenden Attributgruppe aus Ihrem Shop, um die neuen Kombinationen zu kategorisieren.
  - **Auswirkung der Änderung dieser Einstellung:** Das Modul versucht, die Quellprodukte Attributen innerhalb dieser ausgewählten Gruppe zuzuordnen. Dies erfordert eine sorgfältige Planung, um sicherzustellen, dass Ihre Quellprodukte logisch in die bestehende Attributstruktur passen.
  - **Empfohlener Wert:** Nur verwenden, wenn Sie ein sehr spezifisches Szenario haben, in dem Quellprodukte bereits Variationen eines bestehenden Attributs sind. Andernfalls ist „Neue Attributgruppe hinzufügen“ sicherer.
  - **Händlerszenario / Beispiel:** Sie haben die Produkte „Hemd - Blau“ und „Hemd - Rot“ als separate Produkte und möchten diese in ein Master-Produkt „Hemd“ zusammenführen, wobei die bestehende Attributgruppe „Farbe“ verwendet wird.

#### Schritt 4: Überprüfen & Zusammenführen

- **Schaltfläche: „Produkte zusammenführen“**
  - **Was diese Schaltfläche tut:** Leitet den eigentlichen Zusammenführungsprozess basierend auf Ihren Auswahlen und Konfigurationen ein.
  - **Auswirkung des Klicks:** Das Modul verarbeitet die ausgewählten Quellprodukte, wandelt sie in Kombinationen um, weist sie dem Master-Produkt zu, aktualisiert Lagerbestand und Preise und führt Weiterleitungen/Deaktivierungen wie konfiguriert durch. Eine Fortschrittsanzeige oder Erfolgsmeldung wird angezeigt.
  - **Empfohlene Aktion:** Überprüfen Sie alle Ihre Auswahlen sorgfältig, bevor Sie klicken. Stellen Sie sicher, dass Sie ein Backup Ihres Shops haben.
  - **Händlerszenario / Beispiel:** Nachdem Sie „iPhone 13 (Neu)“ als Master, „iPhone 13 (Generalüberholt)“ als Quelle ausgewählt, „Zustand“ als neue Attributgruppe festgelegt und 301-Weiterleitungen aktiviert haben, klicken Sie auf „Produkte zusammenführen“, um die Konsolidierung auszuführen.

#### Kurzübersichtstabelle zur Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Produkte zusammenführen Tool** | **Master-Produktsuche** | N/A | Wählt das Hauptprodukt aus, in das andere zusammengeführt werden. |
|  | **Quellproduktsuche** | N/A | Wählt Produkte aus, die in Kombinationen unter dem Master umgewandelt werden sollen. |
|  | **Zusammenführungsmodus** | Neue Attributgruppe hinzufügen | Bestimmt, ob eine neue Attributgruppe erstellt oder eine bestehende für Kombinationen verwendet wird. |
|  | **Name der neuen Attributgruppe** | Beschreibender Name (z. B. „Zustand“) | Name für die Attributgruppe, die zur Unterscheidung zusammengeführter Kombinationen erstellt wird. |
|  | **Master-Produkt-Regel** | Als Master-Produkt beibehalten | Definiert, ob das Master-Produkt selbst zu einer Kombination wird oder die Standardeinstellung bleibt. |
|  | **Aktion für Quellprodukt** | Deaktivieren | Was mit den ursprünglichen Quellproduktseiten nach der Zusammenführung geschieht (Deaktivieren, Löschen, Nichts tun). |
|  | **301-Weiterleitungen erstellen** | JA | Erstellt permanente Weiterleitungen von alten Quell-URLs zur neuen Master-URL. Entscheidend für SEO. |
|  | **Stapelgröße** | Standard (z. B. 10) | Anzahl der pro Stapel verarbeiteten Produkte. Anpassen für Serverleistung. |
|  | **Nur aktive Produkte** | JA | Beschränkt die Auswahl der Quellprodukte auf nur aktive Produkte. |
|  | **Pakete ausschließen** | JA | Verhindert, dass Produktpakete als Quellprodukte ausgewählt werden. |
|  | **Virtuelle Produkte ausschließen** | JA | Verhindert, dass virtuelle Produkte als Quellprodukte ausgewählt werden. |
|  | **Mindestgruppengröße** | Standard (z. B. 2) | Mindestanzahl von Quellprodukten, um eine neue Attributgruppe zu erstellen. |
|  | **Zu verwendende Attributgruppe** | N/A (nur im Modus „Bestehende verwenden…“) | Wählt eine bestehende Attributgruppe für die Kombinationszuordnung aus. |
|  | **Produkte zusammenführen Schaltfläche** | Nach Überprüfung klicken | Führt den Zusammenführungsvorgang aus. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Nach dem Zusammenführen sehe ich die neuen Kombinationen nicht auf meiner Produktseite.**
A1: Leeren Sie zuerst Ihren PrestaShop-Cache. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie oben rechts auf „Cache leeren“. Wenn das Problem weiterhin besteht, überprüfen Sie das Master-Produkt in Ihrem Back Office, um sicherzustellen, dass die Kombinationen korrekt erstellt und aktiv sind. Überprüfen Sie auch, ob die vom Modul erstellte Attributgruppe aktiviert und dem Master-Produkt zugeordnet ist.

**F2: Meine alten Produkt-URLs zeigen „Seite nicht gefunden“-Fehler an.**
A2: Dies bedeutet normalerweise, dass die 301-Weiterleitungen nicht erstellt wurden oder nicht funktionieren.
1. Gehen Sie zurück zum Tool „Produkte zusammenführen“ (**Katalog > Produkte zusammenführen**).
2. Überprüfen Sie, ob die Option „301-Weiterleitungen erstellen“ während der Zusammenführung aktiviert war. Wenn nicht, müssen Sie Weiterleitungen manuell einrichten oder erneut zusammenführen (nachdem Sie ein Backup wiederhergestellt haben, falls Sie die Quellprodukte gelöscht haben).
3. Stellen Sie sicher, dass die `.htaccess`-Datei Ihres Servers korrekt konfiguriert ist, um PrestaShops freundliche URLs und Weiterleitungen zu verarbeiten. Manchmal können Serverkonfigurationen stören.

**F3: Das Modul scheint während des Zusammenführungsprozesses hängen zu bleiben oder einen Timeout zu haben.**
A3: Dies kann bei einer großen Anzahl von Produkten oder auf Servern mit begrenzten Ressourcen passieren.
1. Versuchen Sie, die Einstellung **„Stapelgröße“** im Abschnitt „Zusammenführungsoptionen konfigurieren“ des Moduls zu reduzieren. Eine kleinere Stapelgröße (z. B. 5 oder 10) verarbeitet weniger Produkte gleichzeitig und reduziert die Serverlast.
2. Überprüfen Sie die PHP-Einstellungen `max_execution_time` und `memory_limit` Ihres Servers. Möglicherweise müssen Sie diese Werte vorübergehend erhöhen (wenden Sie sich an Ihren Hosting-Anbieter, wenn Sie unsicher sind).

**F4: Kann ich einen Zusammenführungsvorgang rückgängig machen?**
A4: Das Modul hat keine „Rückgängig“-Schaltfläche. Deshalb sind **Backups absolut entscheidend**. Wenn Sie zurücksetzen müssen, müssen Sie Ihren Shop aus einem Backup wiederherstellen, das *vor* der Zusammenführung erstellt wurde. Wenn Sie nur Quellprodukte deaktiviert und nicht gelöscht haben, könnten Sie diese manuell reaktivieren und die neu erstellten Kombinationen aus dem Master-Produkt löschen, aber dies ist ein komplexer manueller Prozess.

**F5: Was ist, wenn mein benutzerdefiniertes Theme die neue Attributgruppe nicht korrekt anzeigt?**
A5: Das Modul erstellt Standard-PrestaShop-Attributgruppen und -Kombinationen. Wenn Ihr Theme diese nicht richtig anzeigt, handelt es sich wahrscheinlich um ein CSS- oder Smarty-Template-Problem innerhalb Ihres Themes.
1. Überprüfen Sie, ob Standard-PrestaShop-Themes (z. B. Classic) die Kombinationen korrekt anzeigen. Wenn ja, liegt das Problem bei Ihrem benutzerdefinierten Theme.
2. Möglicherweise müssen Sie einen Webentwickler konsultieren, um die `product.tpl`-Datei Ihres Themes oder das zugehörige CSS anzupassen, um die neuen Attributauswahlen korrekt darzustellen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen gedacht, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul `Merge Products` folgt einem Standard-PrestaShop-MVC-Muster für seine Back-Office-Komponenten. Es nutzt PrestaShops `ObjectModel` für die Datenmanipulation (obwohl es primär direkt mit den Kernobjekten `Product` und `Combination` interagiert, anstatt mit benutzerdefinierten modulspezifischen Modellen). Die Kernlogik zum Finden, Erstellen und Zusammenführen von Produkten und deren Kombinationen ist in dedizierten Dienstklassen gekapselt. Das Modul verwendet einen benutzerdefinierten Admin-Controller für seine Hauptschnittstelle, der ein benutzerfreundliches Raster und Formular für den Zusammenführungsprozess bietet. Es implementiert auch einen Protokollierungsmechanismus zur Verfolgung von Zusammenführungsvorgängen.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Das Modul ist ein reines Back-Office-Verwaltungstool.
- **Back-Office-Admin-Controller**:

  - `controllers/admin/AdminMyMergeProductsController.php`

    - **Klassenname**: `AdminMyMergeProductsController`
    - **Elternklasse**: `ModuleAdminController`
    - **Verantwortlichkeit**: Dies ist der primäre Controller für die administrative Schnittstelle des Moduls. Er verwaltet die Anzeige des Zusammenführungstools, einschließlich Produktsuche (Autocomplete), Konfigurationsoptionen und die Initiierung des Zusammenführungsprozesses. Er orchestriert Aufrufe an die Kern-Dienstklassen (`MmpFinder`, `MmpMergeEngine`, `MmpLogger`, `MmpRedirector`), um die eigentliche Zusammenführung durchzuführen. Er verwaltet die Formularübermittlung und zeigt dem Benutzer Feedback an.
    - **Tab-Name**: „Produkte zusammenführen“ (unter dem Katalog-Menü)
    - **Verwaltete Entität**: Produkte und deren Kombinationen, Attribute.
  - `controllers/admin/index.php`

    - **Klassenname**: N/A (leere Datei)
    - **Elternklasse**: N/A
    - **Verantwortlichkeit**: Dies ist eine standardmäßige leere `index.php`-Datei, die oft in Verzeichnissen platziert wird, um die Verzeichnisauflistung auf Webservern zu verhindern. Sie hat keine funktionale Rolle in der Logik des Moduls.

### 4.3 Kernklassen & Modelle (`classes/`)

- `classes/index.php`

  - **Verantwortlichkeit**: Standardmäßige leere `index.php`-Datei, um die Verzeichnisauflistung zu verhindern.
- `classes/MmpCombinationBuilder.php`

  - **Klassenname**: `MmpCombinationBuilder`
  - **Elternklasse**: Keine (eigenständige Dienstklasse)
  - **Verantwortlichkeit**: Diese Klasse ist verantwortlich für die komplexe Logik der Erstellung neuer Produktkombinationen basierend auf den Quellprodukten. Sie verwaltet:
    - Die Zuordnung von Quellproduktdaten (Preis, Menge, EAN, Referenz) zu neuen Kombinationen.
    - Die Erstellung neuer Attribute und Attributgruppen, wenn `MMP_MERGE_MODE` auf „Neue Attributgruppe hinzufügen“ gesetzt ist.
    - Die Zuweisung bestehender Attribute zu neuen Kombinationen.
    - Die Handhabung von Bildern für Kombinationen.
    - Die Sicherstellung, dass Lager- und Preisregeln korrekt auf die neuen Kombinationen angewendet werden.
- `classes/MmpFinder.php`

  - **Klassenname**: `MmpFinder`
  - **Elternklasse**: Keine (eigenständige Dienstklasse)
  - **Verantwortlichkeit**: Bietet Methoden zum Suchen und Abrufen von Produkten basierend auf verschiedenen Kriterien (ID, Name, EAN, Referenz). Diese Klasse wird vom `AdminMyMergeProductsController` für die Autocomplete-Suchfunktion sowohl für Master- als auch für Quellprodukte verwendet. Sie filtert auch Produkte basierend auf der Modulkonfiguration (z. B. `MMP_ACTIVE_ONLY`, `MMP_EXCLUDE_PACKS`, `MMP_EXCLUDE_VIRTUAL`).
- `classes/MmpLogger.php`

  - **Klassenname**: `MmpLogger`
  - **Elternklasse**: Keine (eigenständige Dienstklasse)
  - **Verantwortlichkeit**: Verwaltet die Protokollierung von Zusammenführungsvorgängen. Es zeichnet Details jeder Zusammenführung auf, einschließlich des Master-Produkts, der Quellprodukte und der verwendeten Konfigurationseinstellungen. Dies ist entscheidend für die Fehlerbehebung und Prüfung. Es speichert Protokolle wahrscheinlich in einer benutzerdefinierten Datenbanktabelle oder einer Datei.
- `classes/MmpMergeEngine.php`

  - **Klassenname**: `MmpMergeEngine`
  - **Elternklasse**: Keine (eigenständige Dienstklasse)
  - **Verantwortlichkeit**: Dies ist der zentrale Orchestrator für den Zusammenführungsprozess. Er nimmt das Master-Produkt und die Quellprodukte zusammen mit den Konfigurationseinstellungen und koordiniert die Aktionen:
    - Ruft `MmpCombinationBuilder` auf, um Kombinationen zu erstellen.
    - Aktualisiert das Master-Produkt.
    - Verwaltet die `MMP_SOURCE_ACTION` (Deaktivieren oder Löschen von Quellprodukten).
    - Verwaltet die Stapelverarbeitung (`MMP_BATCH_SIZE`).
    - Interagiert mit `MmpRedirector` für 301-Weiterleitungen.
    - Verwendet `MmpLogger`, um den Vorgang aufzuzeichnen.
- `classes/MmpRedirector.php`

  - **Klassenname**: `MmpRedirector`
  - **Elternklasse**: Keine (eigenständige Dienstklasse)
  - **Verantwortlichkeit**: Verwaltet die Erstellung von 301-Weiterleitungen. Wenn `MMP_REDIRECT` aktiviert ist, erstellt diese Klasse Einträge in PrestaShops `ps_product_redirect`-Tabelle (oder einem ähnlichen Mechanismus), um alte Quellprodukt-URLs auf die neue Master-Produkt-URL umzuleiten.

### 4.4 JavaScript-Assets (`views/js/`)

- `lib/searchTool/views/js/autocomplete.js`

  - **Bereich**: Back-Office.
  - **Verantwortlichkeit**: Bietet die JavaScript-Logik für die Autocomplete-Suchfelder für Produkte, die im `AdminMyMergeProductsController` verwendet werden. Es verwendet wahrscheinlich AJAX, um `MmpFinder` nach Produktvorschlägen abzufragen, während der Benutzer tippt, und zeigt die Ergebnisse in einem Dropdown-Menü an. Es verwaltet die Auswahl und das Ausfüllen der entsprechenden Produktfelder.
- `views/js/admin.js`

  - **Bereich**: Back-Office.
  - **Verantwortlichkeit**: Enthält allgemeine JavaScript-Funktionalitäten für die Admin-Oberfläche des Moduls. Dies könnte beinhalten:
    - Bedingte Anzeige von Konfigurationsfeldern (z. B. `Name der neuen Attributgruppe` nur sichtbar, wenn „Neue Attributgruppe hinzufügen“ ausgewählt ist).
    - Formularvalidierung.
    - AJAX-Aufrufe zur Initiierung des Zusammenführungsprozesses und zur Anzeige des Fortschritts.
    - Event-Listener für Schaltflächen und Formularänderungen.

### 4.5 CSS-Stylesheets (`views/css/`)

- `lib/searchTool/views/css/autocomplete.css`

  - **Bereich**: Back-Office-Admin-Styling.
  - **Verantwortlichkeit**: Gestaltet das Autocomplete-Dropdown und die Such-Eingabefelder, um sicherzustellen, dass sie visuell konsistent und benutzerfreundlich innerhalb des PrestaShop Back Office sind.
- `views/css/admin.css`

  - **Bereich**: Back-Office-Admin-Styling.
  - **Verantwortlichkeit**: Bietet spezifisches Styling für die `AdminMyMergeProductsController`-Oberfläche, einschließlich des Layouts der Abschnitte, des Stylings von Produktlisten und allgemeiner visueller Verbesserungen für die Konfigurationsseite des Moduls.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- `lib/searchTool/views/scripts.tpl`

  - **Bereich**: Back-Office.
  - **Verantwortlichkeit**: Dieses Template enthält wahrscheinlich die notwendigen JavaScript- und CSS-Dateien für das Autocomplete-Suchtool, um sicherzustellen, dass es auf den relevanten Admin-Seiten geladen wird. Es könnte `script`- und `link`-Tags enthalten.
- `views/templates/admin/configure_shell.tpl`

  - **Bereich**: Back-Office-Admin.
  - **Verantwortlichkeit**: Dieses Template dient als Wrapper oder Shell für den Hauptkonfigurationsinhalt des Moduls. Es könnte gemeinsame Kopf-/Fußzeilenelemente, Navigation oder eine allgemeine Layoutstruktur für die Admin-Seiten des Moduls enthalten. Es enthält wahrscheinlich `dashboard.tpl`.
- `views/templates/admin/dashboard.tpl`

  - **Bereich**: Back-Office-Admin.
  - **Verantwortlichkeit**: Dies ist das Haupttemplate für die `AdminMyMergeProductsController`-Ansicht. Es rendert die gesamte Oberfläche des Zusammenführungstools, einschließlich:
    - Des Bereichs zur Auswahl des Master-Produkts.
    - Des Bereichs zur Auswahl der Quellprodukte.
    - Des Formulars für die Zusammenführungskonfigurationsoptionen (mit allen Einstellungen wie `MMP_MERGE_MODE`, `MMP_REDIRECT` usw.).
    - Der Schaltfläche „Produkte zusammenführen“.
    - Jeglicher Statusmeldungen oder Fortschrittsanzeigen während der Zusammenführung.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul interagiert hauptsächlich mit bestehenden PrestaShop-Kerntabellen:
    - `ps_product`: Zum Abrufen von Produktinformationen und Aktualisieren des Produktstatus (aktiv/inaktiv).
    - `ps_product_attribute`: Zum Erstellen und Verwalten von Produktkombinationen.
    - `ps_product_attribute_shop`: Für shop-spezifische Kombinationsdaten.
    - `ps_product_attribute_combination`: Verknüpft Kombinationen mit Attributen.
    - `ps_attribute_group`, `ps_attribute_group_lang`, `ps_attribute_group_shop`: Zum Erstellen neuer Attributgruppen.
    - `ps_attribute`, `ps_attribute_lang`, `ps_attribute_shop`: Zum Erstellen neuer Attribute.
    - `ps_stock_available`: Zum Aktualisieren der Lagerbestände für Kombinationen.
    - `ps_product_lang`: Für Produktnamen und Beschreibungen.
    - `ps_product_shop`: Für shop-spezifische Produktdaten.
    - `ps_url_rewrite`: Zum Verwalten von freundlichen URLs.
    - `ps_configuration`: Speichert Modulkonfigurationseinstellungen (z. B. `MMP_MERGE_MODE`, `MMP_MASTER_RULE`, `MMP_SOURCE_ACTION`, `MMP_REDIRECT`, `MMP_BATCH_SIZE`, `MMP_ACTIVE_ONLY`, `MMP_EXCLUDE_PACKS`, `MMP_EXCLUDE_VIRTUAL`, `MMP_MIN_GROUP`, `MMP_ATTRIBUTE_GROUP`, `MMP_ATTRIBUTE_GROUP_NAME`).
  - Das Modul könnte eine benutzerdefinierte Tabelle zum Protokollieren von Zusammenführungsvorgängen erstellen (z. B. `ps_mmp_log` oder ähnlich), obwohl dies im bereitgestellten Inventar nicht explizit detailliert ist. Falls vorhanden, würde es Aufzeichnungen jedes Zusammenführungsereignisses speichern.
  - Für 301-Weiterleitungen verwendet es wahrscheinlich PrestaShops `ps_product_redirect`-Tabelle (oder einen ähnlichen Mechanismus, falls das Modul einen eigenen Weiterleitungs-Handler implementiert).
- **Registrierte Hooks-Tabelle**:
  Das Modul registriert keine expliziten Front-Office-Hooks (wie `displayHeader`, `displayProductButtons` usw.), da es ein Back-Office-Tool ist. Seine primäre Interaktion mit dem PrestaShop-Hook-System wäre für:

  - `actionAdminControllerSetMedia`: Zum Laden seiner spezifischen CSS- und JS-Dateien im Back Office.
  - `actionProductUpdate` / `actionProductAdd` / `actionProductDelete`: Obwohl nicht explizit aufgeführt, könnte die interne Logik des Moduls zur Produktänderung diese PrestaShop-Kern-Hooks auslösen, auf die andere Module hören könnten.
  - `actionObjectProductAddAfter`, `actionObjectProductUpdateAfter`, `actionObjectProductDeleteAfter`: ObjectModel-Hooks, die ausgelöst würden, wenn das Modul `Product`- oder `ProductAttribute`-Objekte erstellt, aktualisiert oder löscht.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Produkte zusammenführen“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei technischen Problemen oder Fragen zur Funktionalität des Moduls gerne zur Verfügung.
