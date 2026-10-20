---
title: "CDKeys / Lizenzschlüssel verkaufen - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „CDKeys / Lizenzschlüssel verkaufen“ von MyPresta.eu."
sidebar:
  label: "CDKeys / Lizenzschlüssel verkaufen - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Sell CDKeys / License keys auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/sell-cdkeys-license-keys.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/sell-cdkeys-license-keys/)
>
> ---


# CDKeys / Lizenzschlüssel verkaufen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen über eine Standard-PrestaShop-Hosting-Umgebung hinaus erforderlich.

## 2. Vollständige Konfigurationsanleitung (Alle Einstellungen nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > CDKeys / Lizenzschlüssel verkaufen)

Dies ist der Hauptkonfigurationsbereich, in dem Sie das Verhalten des Moduls, den Zeitpunkt des Schlüsselversands und allgemeine Einstellungen definieren.

#### Registerkarte „Allgemeine Einstellungen“

- **Aktiviert:**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter zum Aktivieren oder Deaktivieren der Kernfunktionalität des Moduls.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul verarbeitet Bestellungen, sendet CD-Keys und zeigt Kundenschlüssel im Front Office gemäß Ihren anderen Einstellungen an.
    - *Wenn deaktiviert:* Das Modul stoppt alle seine Operationen. Es werden keine Schlüssel automatisch gesendet, und der Bereich „Meine Schlüssel“ des Kunden kann verschwinden oder inaktiv werden.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Aktivieren Sie dies, sobald Sie alles konfiguriert haben, um mit dem Verkauf von Schlüsseln zu beginnen. Deaktivieren Sie es vorübergehend, wenn Sie Wartungsarbeiten durchführen oder den Verkauf digitaler Schlüssel einstellen müssen.
- **Bestellstatus auswählen:**

  - **Was diese Einstellung bewirkt:** Legt fest, welche Bestellstatus den automatischen Versand von CD-Keys an Kunden auslösen. Sie können mehrere Status auswählen.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Wenn ein ausgewählter Status erreicht wird:* Das Modul überprüft die Bestellung auf CD-Key-Produkte und sendet die Schlüssel.
    - *Wenn ein nicht ausgewählter Status erreicht wird:* Es werden keine Schlüssel gesendet, selbst wenn die Bestellung CD-Key-Produkte enthält.
  - **Empfohlener Wert:** „Zahlung akzeptiert“ und möglicherweise „Geliefert“, wenn Sie sicherstellen möchten, dass physische Produkte zuerst geliefert werden.
  - **Händlerszenario / Beispiel:** Wenn Sie möchten, dass Schlüssel sofort nach der Zahlung gesendet werden, wählen Sie „Zahlung akzeptiert“. Wenn Sie eine manuelle Zahlungsmethode wie Banküberweisung verwenden, können Sie „Zahlung akzeptiert“ auswählen, nachdem Sie die Zahlung manuell bestätigt haben.
- **Kundengruppen, die CD-Keys erhalten dürfen:**

  - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, die CD-Key-Lieferung auf bestimmte Kundengruppen zu beschränken (z. B. „Kunden“, „Besucher“, „Gäste“).
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Wenn ein Kunde in einer ausgewählten Gruppe ist:* Er erhält CD-Keys, wenn alle anderen Bedingungen erfüllt sind.
    - *Wenn ein Kunde NICHT in einer ausgewählten Gruppe ist:* Er erhält keine CD-Keys, selbst wenn er ein CD-Key-Produkt kauft.
  - **Empfohlener Wert:** „Kunde“ (und „Gast“, wenn Sie Gast-Checkouts für digitale Produkte zulassen).
  - **Händlerszenario / Beispiel:** Sie könnten dies auf „Kunden“ beschränken, wenn Sie die Kontoerstellung fördern möchten oder wenn Sie spezielle B2B-Gruppen haben, die verschiedene Arten von Schlüsseln erhalten.
- **Maximaler Bestellwert:**

  - **Was diese Einstellung bewirkt:** Legt eine Obergrenze für den Gesamtwert einer Bestellung fest, für die CD-Keys automatisch gesendet werden. Bestellungen, die diesen Wert überschreiten, lösen keine automatische Schlüsselzustellung aus.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Bestellsumme kleiner oder gleich dem Maximum:* Schlüssel werden automatisch gesendet.
    - *Bestellsumme über dem Maximum:* Schlüssel werden NICHT automatisch gesendet. Sie müssten sie manuell senden.
  - **Empfohlener Wert:** Leer lassen oder einen sehr hohen Wert (z. B. 999999) festlegen, wenn Sie keine Wertbeschränkung wünschen.
  - **Händlerszenario / Beispiel:** Verwenden Sie dies als Betrugspräventionsmaßnahme. Wenn Sie viele betrügerische Bestellungen mit hohem Wert bemerken, können Sie ein Limit festlegen, um diese manuell zu überprüfen, bevor Sie teure Schlüssel freigeben.
- **Viele Codes in einer E-Mail senden:**

  - **Was diese Einstellung bewirkt:** Steuert, ob mehrere CD-Keys für dasselbe Produkt in einer einzigen Bestellung in einer E-Mail oder in separaten E-Mails gesendet werden.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Wenn ein Kunde 3 Einheiten von „Spiel X“ kauft, erhält er eine E-Mail mit allen 3 Schlüsseln für „Spiel X“.
    - *Wenn deaktiviert:* Wenn ein Kunde 3 Einheiten von „Spiel X“ kauft, erhält er 3 separate E-Mails, jede mit einem Schlüssel für „Spiel X“.
  - **Empfohlener Wert:** JA (im Allgemeinen besser für die Kundenerfahrung und reduziert E-Mail-Unordnung).
  - **Händlerszenario / Beispiel:** Wenn ein Kunde ein „4er-Pack“ eines Spiels kauft, ist das Senden aller 4 Schlüssel in einer E-Mail viel klarer als 4 separate E-Mails.
- **Titel der E-Mail:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, die Betreffzeile der E-Mail anzupassen, die an Kunden mit ihren CD-Keys gesendet wird.
  - **Auswirkungen einer Änderung dieser Einstellung:** Die E-Mail-Betreffzeile spiegelt Ihren benutzerdefinierten Titel wider, wodurch Kunden die E-Mail leichter identifizieren können.
  - **Empfohlener Wert:** Etwas Klares und Professionelles, z. B. „Ihre CD-Keys / Lizenzen von [Ihr Shop-Name] - Bestellung #[Bestell-ID]“.
  - **Händlerszenario / Beispiel:** Eine klare Betreffzeile wie „Ihre Game Keys für Bestellung #12345“ hilft Kunden, ihre Schlüssel schnell zu finden.
- **Bestellstatus ändern:**

  - **Was diese Einstellung bewirkt:** Nachdem CD-Keys erfolgreich gesendet wurden, können Sie mit dieser Option den Bestellstatus automatisch in einen neuen, angegebenen Status ändern.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Wenn aktiviert und ein Status ausgewählt ist:* Der Bestellstatus wird automatisch aktualisiert (z. B. von „Zahlung akzeptiert“ zu „CD-Keys gesendet“).
    - *Wenn deaktiviert:* Der Bestellstatus bleibt so, wie er nach dem ursprünglichen Auslöser war (z. B. „Zahlung akzeptiert“).
  - **Empfohlener Wert:** JA, und wählen Sie einen eindeutigen Status wie „CD-Keys gesendet“ (Sie müssen diesen Status möglicherweise in PrestaShop > Bestellstatus erstellen).
  - **Händlerszenario / Beispiel:** Dies hilft Ihnen, Bestellungen, für die Schlüssel bereits geliefert wurden, schnell zu identifizieren und Ihren Bestellverwaltungsworkflow zu verbessern.
- **Bestellstatus auswählen (für Statusänderung):**

  - **Was diese Einstellung bewirkt:** Wenn „Bestellstatus ändern“ aktiviert ist, können Sie in diesem Dropdown-Menü den spezifischen Bestellstatus auswählen, der nach dem Senden der Schlüssel angewendet werden soll.
  - **Auswirkungen einer Änderung dieser Einstellung:** Der gewählte Status wird auf die Bestellung angewendet.
  - **Empfohlener Wert:** Ein benutzerdefinierter Status wie „CD-Keys gesendet“ oder „Digitales Produkt geliefert“.
  - **Händlerszenario / Beispiel:** Das Erstellen eines spezifischen Status wie „CD-Keys gesendet“ ermöglicht es Ihnen, Bestellungen zu filtern und genau zu sehen, welche digitalen Produkte erfüllt wurden.
- **Schlüssel in Rechnung aufnehmen:**

  - **Was diese Einstellung bewirkt:** Legt fest, ob die gelieferten CD-Keys auch auf der Kundenrechnung gedruckt werden sollen.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Schlüssel erscheinen auf der für die Bestellung generierten PDF-Rechnung.
    - *Wenn deaktiviert:* Schlüssel werden nur per E-Mail gesendet und/oder erscheinen im Bereich „Meine Schlüssel“, aber nicht auf der Rechnung.
  - **Empfohlener Wert:** JA (bietet eine zusätzliche Aufzeichnung für den Kunden).
  - **Händlerszenario / Beispiel:** Einige Kunden bevorzugen es, alle Kaufdetails, einschließlich der Schlüssel, auf ihrer Rechnung für die Aufbewahrung oder Steuerzwecke zu haben.
- **Paginierung aktivieren:**

  - **Was diese Einstellung bewirkt:** Aktiviert die Paginierung für die Liste der CD-Keys, die im Bereich „Meine Schlüssel“ des Kunden im Front Office angezeigt werden.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Wenn ein Kunde viele Schlüssel hat, werden diese auf mehreren Seiten angezeigt, was die Ladezeiten und die Lesbarkeit verbessert.
    - *Wenn deaktiviert:* Alle Schlüssel werden auf einer einzigen Seite aufgelistet.
  - **Empfohlener Wert:** JA (insbesondere wenn Kunden viele Schlüssel ansammeln könnten).
  - **Händlerszenario / Beispiel:** Ein Kunde, der regelmäßig Game Keys kauft, wird die Paginierung schätzen, um bestimmte Schlüssel schnell zu finden, ohne eine sehr lange Liste durchsuchen zu müssen.
- **Anzahl der Elemente pro Seite (Paginierung):**

  - **Was diese Einstellung bewirkt:** Wenn die Paginierung aktiviert ist, legt dies fest, wie viele CD-Keys pro Seite im Bereich „Meine Schlüssel“ des Kunden angezeigt werden.
  - **Auswirkungen einer Änderung dieser Einstellung:** Steuert die Dichte der Schlüsselliste auf jeder Seite.
  - **Empfohlener Wert:** 10-20 (ein gutes Gleichgewicht für die Lesbarkeit).
  - **Händlerszenario / Beispiel:** Wenn dies auf 15 eingestellt ist, sieht ein Kunde mit 30 Schlüsseln 2 Seiten mit Schlüsseln.

#### Registerkarte „CSV-Import-Einstellungen“

- **CSV-Dateizeilentrennzeichen:**

  - **Was diese Einstellung bewirkt:** Gibt das Zeichen an, das zum Trennen einzelner Zeilen in Ihrer CSV-Datei beim Importieren von CD-Keys verwendet wird.
  - **Auswirkungen einer Änderung dieser Einstellung:** Das Modul verwendet dieses Zeichen, um Ihre CSV-Datei korrekt in einzelne Schlüsseleinträge zu parsen. Ein falsches Trennzeichen führt zu Importfehlern.
  - **Empfohlener Wert:** `\n` (Zeilenumbruchzeichen, Standard für die meisten CSV-Dateien).
  - **Händlerszenario / Beispiel:** Wenn Ihre Schlüsselliste `key1\nkey2\nkey3` lautet, muss das Modul wissen, dass `\n` jeden Schlüssel trennt.
- **CSV-Dateispalten-Trennzeichen:**

  - **Was diese Einstellung bewirkt:** Gibt das Zeichen an, das zum Trennen von Spalten (Feldern) innerhalb jeder Zeile Ihrer CSV-Datei beim Importieren von CD-Keys verwendet wird.
  - **Auswirkungen einer Änderung dieser Einstellung:** Das Modul verwendet dieses Zeichen, um verschiedene Datenpunkte (z. B. Schlüssel, Gruppen-ID) innerhalb jeder Zeile korrekt zu identifizieren. Ein falsches Trennzeichen führt zu Importfehlern.
  - **Empfohlener Wert:** `;` (Semikolon) oder `,` (Komma), je nachdem, wie Ihre CSV-Dateien generiert werden.
  - **Händlerszenario / Beispiel:** Wenn Ihre CSV-Datei `key1;product_id_1;group_id_1` lautet, muss das Modul wissen, dass `;` die Felder trennt.

#### Registerkarte „Analyse & Betrug“

- **CDKEYS\_ANALYTICS\_DEFAULT\_CHART, CDKEYS\_ANALYTICS\_PERIOD, CDKEYS\_ANALYTICS\_CHART\_DAYS, CDKEYS\_ANALYTICS\_CHART\_WEEKS, CDKEYS\_ANALYTICS\_CHART\_MONTHS, CDKEYS\_ANALYTICS\_PREDICTION\_DAYS, CDKEYS\_ANALYTICS\_TOP\_LIMIT, CDKEYS\_ANALYTICS\_MIN\_SALES, CDKEYS\_ANALYTICS\_SHOW\_EMPTY\_GROUPS, CDKEYS\_ANALYTICS\_INCLUDE\_INACTIVE:**

  - **Was diese Einstellungen bewirken:** Dies sind interne Konfigurationsschlüssel, die sich auf das Analyse- und Betrugserkennungs-Dashboard des Moduls beziehen. Sie steuern, wie Daten im Back-Office-Analysebereich des Moduls angezeigt, aggregiert und gefiltert werden.
  - **Auswirkungen einer Änderung dieser Einstellungen:** Passt die visuelle Darstellung und die im Modul-Dashboard angezeigten Datenpunkte an, um Ihnen die Überwachung wichtiger Verkaufs- und potenzieller Betrugsmuster zu erleichtern.
  - **Empfohlener Wert:** Die Standardwerte sind in der Regel in Ordnung. Passen Sie sie nur an, wenn Sie spezifische Berichtsansichten benötigen.
  - **Händlerszenario / Beispiel:** Sie könnten `CDKEYS_ANALYTICS_PERIOD` anpassen, um Verkaufstrends über eine Woche statt einen Monat anzuzeigen, oder `CDKEYS_ANALYTICS_TOP_LIMIT`, um mehr meistverkaufte Schlüsselgruppen zu sehen.
- **CDKEYS\_ALERT\_COOLDOWN\_HOURS:**

  - **Was diese Einstellung bewirkt:** Definiert eine Abklingzeit in Stunden für Betrugswarnungen. Wenn eine Warnung für einen Kunden ausgelöst wird, wird innerhalb dieser Abklingzeit keine weitere Warnung für denselben Kunden ausgelöst.
  - **Auswirkungen einer Änderung dieser Einstellung:** Verhindert Warnungs-Spam bei wiederholten betrügerischen Versuchen desselben Kunden innerhalb kurzer Zeit.
  - **Empfohlener Wert:** 24-48 Stunden (um Zeit für eine manuelle Überprüfung zu lassen, ohne ständig neu zu warnen).
  - **Händlerszenario / Beispiel:** Wenn ein Kunde innerhalb einer Stunde mehrere betrügerische Bestellungen versucht, verhindert dies, dass Sie für jeden Versuch eine Warnung erhalten, und konsolidiert diese zu einer ersten Warnung.
- **CDKEYS\_EXPORT\_MASK\_CODES:**

  - **Was diese Einstellung bewirkt:** Beim Exportieren von CD-Key-Daten bestimmt diese Einstellung, ob die tatsächlichen Key-Codes aus Sicherheitsgründen maskiert (verborgen) werden sollen.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Exportierte Daten zeigen maskierte Codes (z. B. `*****`).
    - *Wenn deaktiviert:* Exportierte Daten zeigen die vollständigen, unmaskierten Key-Codes.
  - **Empfohlener Wert:** JA (aus Sicherheitsgründen, insbesondere beim Teilen von Exportdateien).
  - **Händlerszenario / Beispiel:** Wenn Sie eine Liste verwendeter Schlüssel mit einem Lieferanten teilen müssen, aber die tatsächlichen Schlüsselwerte nicht preisgeben möchten, aktivieren Sie die Maskierung.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Das Modul fügt Ihrem PrestaShop Back Office-Menü mehrere neue Abschnitte hinzu, typischerweise unter einer Hauptregisterkarte „CD Keys“ oder „Lizenzen“.

#### 2.2.1 CD Keys > Gruppen (AdminCdKeysGroupsController)

- **Bildschirmname & Menüpfad:** **Back Office > CD Keys > Gruppen**
- **Zweck:** Dieser Bildschirm ermöglicht es Ihnen, Gruppen von CD-Keys zu erstellen und zu verwalten. Eine Gruppe ist im Wesentlichen ein Pool von Schlüsseln, die einem oder mehreren Produkten zugewiesen werden können. Dies ist entscheidend für die Verwaltung Ihres Schlüsselbestands.
- **Verfügbare Aktionen & Einstellungen:**
  - **Neue Gruppe hinzufügen:** Erstellen Sie eine neue Gruppe mit einem Namen (z. B. „Windows 11 Pro Keys“, „Spiel X Deluxe Edition“).
  - **Gruppe bearbeiten:** Ändern Sie den Namen einer bestehenden Gruppe.
  - **Gruppe löschen:** Entfernen Sie eine Gruppe (stellen Sie sicher, dass keine aktiven Produkte damit verknüpft sind und keine Schlüssel zugewiesen sind).
  - **Schlüssel in Gruppe anzeigen:** Navigieren Sie direkt zur Liste der Schlüssel, die einer bestimmten Gruppe zugeordnet sind.
- **Auswirkungen von Änderungen:**
  - Das Erstellen einer Gruppe ermöglicht es Ihnen, Ihre Schlüssel zu kategorisieren und mit Produkten zu verknüpfen.
  - Das Löschen einer Gruppe entfernt deren Verknüpfung mit Produkten und Schlüsseln, was potenziell Probleme verursachen kann, wenn Schlüssel noch benötigt werden.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Bevor Sie Schlüssel importieren, erstellen Sie eine Gruppe für jedes einzelne Produkt oder jede Version eines Produkts, das einen Schlüssel benötigt.
  2. Weisen Sie Ihren Produkten die entsprechende Gruppe zu (dies geschieht auf der Produktbearbeitungsseite unter der Registerkarte „Module“ oder einer vom Modul hinzugefügten dedizierten Registerkarte „CD Keys“).

#### 2.2.2 CD Keys > Liste (AdminCdKeysListController)

- **Bildschirmname & Menüpfad:** **Back Office > CD Keys > Liste**
- **Zweck:** Dies ist Ihr zentrales Inventar für alle einzelnen CD-Keys. Hier können Sie den Status jedes Schlüssels importieren, anzeigen und verwalten.
- **Verfügbare Aktionen & Einstellungen:**
  - **CSV importieren:** Laden Sie eine CSV-Datei mit Ihren Schlüsseln hoch. Sie geben während des Importvorgangs die Gruppe an, zu der diese Schlüssel gehören.
  - **Neuen Schlüssel hinzufügen:** Fügen Sie manuell einen einzelnen Schlüssel hinzu, weisen Sie ihn einer Gruppe zu und legen Sie seinen Status fest (z. B. „Verfügbar“, „Verwendet“).
  - **Schlüssel bearbeiten:** Ändern Sie den Wert, die Gruppe oder den Status eines vorhandenen Schlüssels.
  - **Schlüssel löschen:** Entfernen Sie einen Schlüssel aus dem Inventar.
  - **Filtern/Suchen:** Finden Sie bestimmte Schlüssel nach Wert, Gruppe oder Status.
  - **Exportieren:** Exportieren Sie Ihr Schlüsselinventar (mit optionaler Maskierung).
- **Auswirkungen von Änderungen:**
  - Das Importieren von Schlüsseln füllt Ihr Inventar auf und macht sie zum Verkauf verfügbar.
  - Das Ändern des Status eines Schlüssels (z. B. auf „Verwendet“) verhindert, dass er neuen Bestellungen zugewiesen wird.
  - Das Löschen eines Schlüssels entfernt ihn dauerhaft.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Importieren Sie regelmäßig neue Schlüsselchargen von Ihren Lieferanten in die entsprechenden Gruppen.
  2. Überwachen Sie den Status „Verwendet“, um sicherzustellen, dass Schlüssel korrekt zugewiesen werden.
  3. Wenn ein Kunde ein Problem mit einem Schlüssel meldet, können Sie ihn hier finden, seinen Status überprüfen und möglicherweise einen neuen zuweisen.

#### 2.2.3 CD Keys > Archiv (AdminCdKeysArchiveController)

- **Bildschirmname & Menüpfad:** **Back Office > CD Keys > Archiv**
- **Zweck:** Dieser Bildschirm bietet eine historische Aufzeichnung aller CD-Keys, die Kundenbestellungen zugewiesen wurden. Er dient als Audit-Log für die Schlüsselverteilung.
- **Verfügbare Aktionen & Einstellungen:**
  - **Zugewiesene Schlüssel anzeigen:** Sehen Sie, welcher Schlüssel welcher Bestellung, für welches Produkt und welchem Kunden zugewiesen wurde.
  - **Filtern/Suchen:** Finden Sie bestimmte archivierte Schlüssel nach Bestell-ID, Kundennamen, Produkt oder Schlüsselwert.
  - **E-Mail erneut senden:** Option zum erneuten Senden der CD-Key-E-Mail an den Kunden (nützlich, wenn dieser behauptet, sie nicht erhalten zu haben).
- **Auswirkungen von Änderungen:** Dieser Bildschirm dient hauptsächlich der Anzeige und Prüfung. Aktionen hier ändern nicht den Status der Schlüssel im Abschnitt „Liste“, ermöglichen aber Kundensupport-Aktionen wie das erneute Senden von E-Mails.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Verwenden Sie diesen Bildschirm, um die gekauften Schlüssel eines Kunden schnell nachzuschlagen, wenn dieser den Support kontaktiert.
  2. Überprüfen Sie, ob die Schlüssel für bestimmte Bestellungen korrekt gesendet wurden.
  3. Senden Sie Schlüssel erneut, wenn die E-Mail eines Kunden verloren gegangen oder versehentlich gelöscht wurde.

#### 2.2.4 Produktbearbeitungsseite (Back Office > Katalog > Produkte > Produkt bearbeiten)

- **Bildschirmname & Menüpfad:** Suchen Sie beim Bearbeiten eines Produkts nach einer neuen Registerkarte oder einem Abschnitt, der sich auf „CD Keys“ oder „Module“ bezieht.
- **Zweck:** Hier verknüpfen Sie ein bestimmtes Produkt mit einer CD-Key-Gruppe und kennzeichnen es als „CD-Key-Produkt“.
- **Verfügbare Aktionen & Einstellungen:**
  - **CD-Key für dieses Produkt aktivieren:** Ein Umschalter oder Kontrollkästchen, um anzuzeigen, dass dieses Produkt eine CD-Key-Lieferung erfordert.
  - **CD-Key-Gruppe auswählen:** Ein Dropdown-Menü, um auszuwählen, aus welcher Schlüsselgruppe dieses Produkt bei einer Bestellung schöpfen soll.
- **Auswirkungen von Änderungen:**
  - *Wenn aktiviert und eine Gruppe ausgewählt ist:* Jeder Kauf dieses Produkts löst automatisch das Modul aus, um einen verfügbaren Schlüssel aus der gewählten Gruppe zuzuweisen und an den Kunden zu senden.
  - *Wenn deaktiviert:* Das Produkt wird als reguläres PrestaShop-Produkt behandelt, und es werden keine Schlüssel zugewiesen oder gesendet.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Navigieren Sie für jedes digitale Produkt, das Sie verkaufen und das einen eindeutigen Schlüssel erfordert, zu dessen Bearbeitungsseite.
  2. Aktivieren Sie die CD-Key-Option und wählen Sie die korrekte Schlüsselgruppe aus, die Sie zuvor erstellt haben.
  3. Stellen Sie sicher, dass Sie genügend Schlüssel in der ausgewählten Gruppe haben, um potenzielle Verkäufe abzudecken.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | Aktiviert | JA | Hauptschalter für die Modulfunktionalität. |
|  | Bestellstatus auswählen | Zahlung akzeptiert | Löst die Schlüsselzustellung aus, wenn die Bestellung diesen Status erreicht. |
|  | Kundengruppen, die CD-Keys erhalten dürfen | Kunde, Gast | Beschränkt die Schlüsselzustellung auf bestimmte Kundengruppen. |
|  | Maximaler Bestellwert | Leer (kein Limit) | Legt eine Wertobergrenze für die automatische Schlüsselzustellung fest (Betrugsprävention). |
|  | Viele Codes in einer E-Mail senden | JA | Bündelt mehrere Schlüssel für dasselbe Produkt in einer E-Mail. |
|  | Titel der E-Mail | Ihre CD-Keys von [Shop-Name] | Passt die Betreffzeile der Schlüsselzustellungs-E-Mails an. |
|  | Bestellstatus ändern | JA | Aktualisiert den Bestellstatus nach der Schlüsselzustellung automatisch. |
|  | Bestellstatus auswählen (für Statusänderung) | „CD-Keys gesendet“ (benutzerdefiniert) | Der spezifische Status, der nach dem Senden der Schlüssel angewendet werden soll. |
|  | Schlüssel in Rechnung aufnehmen | JA | Druckt gelieferte Schlüssel auf die PDF-Rechnung des Kunden. |
|  | Paginierung aktivieren | JA | Aktiviert die Paginierung für „Meine Schlüssel“ im Kundenkonto. |
|  | Anzahl der Elemente pro Seite (Paginierung) | 10-20 | Anzahl der Schlüssel, die pro Seite in „Meine Schlüssel“ angezeigt werden. |
|  | CSV-Dateizeilentrennzeichen | `\n` | Zeichen, das Zeilen beim CSV-Schlüsselimport trennt. |
|  | CSV-Dateispalten-Trennzeichen | `;` oder `,` | Zeichen, das Spalten beim CSV-Schlüsselimport trennt. |
|  | CDKEYS\_EXPORT\_MASK\_CODES | JA | Maskiert Schlüsselcodes in Exportdateien aus Sicherheitsgründen. |
| **CD Keys > Gruppen** | Gruppe hinzufügen/bearbeiten Name | N/A | Verwaltet Kategorien/Pools von Schlüsseln. |
| **CD Keys > Liste** | CSV importieren | N/A | Lädt Schlüssel in großen Mengen in Gruppen hoch. |
|  | Schlüssel hinzufügen/bearbeiten | N/A | Verwaltet manuell einzelne Schlüsselwerte und Status. |
| **CD Keys > Archiv** | E-Mail erneut senden | N/A | Sendet die Schlüsselzustellungs-E-Mail für eine bestimmte Bestellung erneut. |
| **Produktbearbeitungsseite** | CD-Key für dieses Produkt aktivieren | JA | Kennzeichnet ein Produkt als CD-Key-Lieferung erforderlich. |
|  | CD-Key-Gruppe auswählen | (Spezifische Gruppe) | Verknüpft das Produkt mit einem Schlüsselpool zur Erfüllung. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Kunden erhalten ihre CD-Keys nicht. Was sollte ich zuerst überprüfen?**
A1:

1.  **Modul aktiviert?** Gehen Sie zu `Module > Modul-Manager > CDKeys / Lizenzschlüssel verkaufen` und stellen Sie sicher, dass das Modul „Aktiviert“ ist.
2.  **Bestellstatus:** Überprüfen Sie Ihre Modulkonfiguration unter „Bestellstatus auswählen“. Ist der aktuelle Status der Kundenbestellung (z. B. „Zahlung akzeptiert“) in dieser Liste ausgewählt?
3.  **Produkt mit Gruppe verknüpft:** Stellen Sie auf der Produktbearbeitungsseite (`Katalog > Produkte > Produkt bearbeiten`) sicher, dass „CD-Key für dieses Produkt aktivieren“ aktiviert und die korrekte „CD-Key-Gruppe“ ausgewählt ist.
4.  **Schlüssel in Gruppe:** Gehen Sie zu `CD Keys > Liste` und überprüfen Sie, ob verfügbare (unbenutzte) Schlüssel in der dem Produkt zugewiesenen Gruppe vorhanden sind. Falls nicht, importieren Sie weitere Schlüssel.
5.  **Kundengruppe:** Überprüfen Sie, ob die Kundengruppe unter „Kundengruppen, die CD-Keys erhalten dürfen“ in der Modulkonfiguration Schlüssel erhalten darf.
6.  **E-Mail-Konfiguration:** Überprüfen Sie Ihre PrestaShop-E-Mail-Einstellungen (`Erweiterte Parameter > E-Mail`), um sicherzustellen, dass E-Mails korrekt von Ihrem Shop gesendet werden. Bitten Sie den Kunden auch, seinen Spam-/Junk-Ordner zu überprüfen.

**F2: Ich habe eine CSV-Datei importiert, aber die Schlüssel werden nicht angezeigt oder sind falsch.**
A2:

1.  **Trennzeicheneinstellungen:** Überprüfen Sie Ihre Einstellungen für „CSV-Dateizeilentrennzeichen“ und „CSV-Dateispalten-Trennzeichen“ in der Modulkonfiguration. Diese müssen genau mit der Struktur Ihrer CSV-Datei übereinstimmen. Häufige Probleme sind die Verwendung von Komma (`,`) anstelle von Semikolon (`;`) oder umgekehrt.
2.  **Dateiformat:** Stellen Sie sicher, dass Ihre CSV-Datei reiner Text ist und keine Excel-Datei, die als CSV mit komplexer Formatierung gespeichert wurde.
3.  **Zielgruppe:** Haben Sie während des Importvorgangs die richtige CD-Key-Gruppe ausgewählt?

**F3: Der Bereich „Meine Schlüssel“ wird im Kundenkonto nicht angezeigt.**
A3:

1.  **Modul aktiviert:** Stellen Sie sicher, dass das Modul aktiv ist.
2.  **Theme-Kompatibilität:** Obwohl das Modul Standard-PrestaShop-Hooks verwendet, können einige stark angepasste Themes den Standard-Hook `displayCustomerAccount` überschreiben. Überprüfen Sie, ob Ihr Theme diesen Bereich geändert hat. Falls ja, sind möglicherweise kleinere Theme-Anpassungen erforderlich (siehe Abschnitt 7.6 für Hook-Vorlagen).
3.  **Cache:** Leeren Sie Ihren PrestaShop-Cache (`Erweiterte Parameter > Leistung > Cache leeren`).

**F4: Wie erstelle ich einen neuen Bestellstatus wie „CD-Keys gesendet“?**
A4:

1.  Gehen Sie zu `Shop-Parameter > Bestell-Einstellungen > Status`.
2.  Klicken Sie auf „Neuen Bestellstatus hinzufügen“.
3.  Geben Sie ihm einen klaren Namen (z. B. „CD-Keys gesendet“).
4.  Wählen Sie eine eindeutige Farbe (z. B. Hellblau), um ihn in Ihrer Bestellliste leicht zu identifizieren.
5.  Stellen Sie sicher, dass „Zugehörige Bestellung als validiert betrachten“ aktiviert ist, wenn sie als abgeschlossene Bestellung zählen soll.
6.  Speichern Sie den neuen Status und gehen Sie dann zurück zur Modulkonfiguration, um ihn für „Bestellstatus auswählen (für Statusänderung)“ auszuwählen.

**F5: Kann ich einen Schlüssel manuell einer Bestellung oder einem Kunden zuweisen?**
A5: Das Modul automatisiert dies primär. Wenn Sie einen Schlüssel manuell zuweisen müssen (z. B. für einen Ersatz), würden Sie typischerweise:

1.  Gehen Sie zu `CD Keys > Liste`, finden Sie einen verfügbaren Schlüssel und notieren Sie seinen Wert.
2.  Gehen Sie zur Bestellung des Kunden (`Bestellungen > Bestellungen`) und fügen Sie eine private Notiz mit dem Schlüssel hinzu.
3.  Senden Sie den Schlüssel manuell per E-Mail an den Kunden.
4.  Gehen Sie dann zurück zu `CD Keys > Liste`, finden Sie diesen Schlüssel und ändern Sie seinen Status manuell auf „Verwendet“, um zu verhindern, dass er erneut zugewiesen wird.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen tiefen Einblick in die technische Struktur des Moduls „CDKeys / Lizenzschlüssel verkaufen“, der für Entwickler, Webmaster und technische Agenturen bestimmt ist.

### 4.1 Architekturübersicht

Das Modul folgt einem Standard-PrestaShop MVC-Muster (Model-View-Controller). Es erweitert `Module` für seine Kernfunktionalität und `AdminController` für seine Back-Office-Schnittstellen. Es nutzt PrestaShops `ObjectModel` zur Verwaltung von CD-Key-Gruppen, einzelnen Schlüsseln und deren Nutzungsverlauf. Die Schlüsselzustellung ist primär ereignisgesteuert und wird durch die Hooks `actionOrderStatusPostUpdate` und `actionOrderStatusUpdate` ausgelöst. Die Front-Office-Interaktion ist minimal und bietet hauptsächlich einen kundenorientierten Bereich „Meine Schlüssel“.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `controllers/front/index.php`:
  - **Klassenname:** `CdkeysIndexModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Wahrscheinlich ein Platzhalter oder ein Weiterleitungs-Controller. In vielen Modulen könnte `index.php` im Front-Controller-Verzeichnis das Standard-Routing übernehmen oder einfach zu einem spezifischeren Controller weiterleiten.
- `controllers/front/mykeys.php`:
  - **Klassenname:** `CdkeysMykeysModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Handhabt die Anzeige der vom Kunden gekauften CD-Keys im Bereich „Mein Konto“. Es ruft `cdkey_used`-Datensätze ab, die dem aktuellen Kunden zugeordnet sind, wendet bei Bedarf die Paginierung an und rendert `views/templates/front/mykeys.tpl`.

#### Back-Office-Admin-Controller

- `controllers/admin/AdminCdKeysArchiveController.php`:
  - **Registerkartenname:** CD Keys > Archiv
  - **Verwaltete Entität:** `cdkey_used` (Datensätze zugewiesener Schlüssel)
  - **Verantwortlichkeit:** Bietet eine Listenverwaltungsoberfläche für alle CD-Keys, die Bestellungen zugewiesen wurden. Es ermöglicht das Anzeigen, Filtern und möglicherweise das erneute Senden von Schlüssel-E-Mails. Es verwendet `HelperList` für seine Anzeige.
- `controllers/admin/AdminCdKeysGroupsController.php`:
  - **Registerkartenname:** CD Keys > Gruppen
  - **Verwaltete Entität:** `cdkey_group`
  - **Verantwortlichkeit:** Verwaltet die Erstellung, Bearbeitung und Löschung von CD-Key-Gruppen. Diese Gruppen dienen als Kategorien für Ihre Schlüssel und sind mit Produkten verknüpft. Es verwendet `HelperList` und `HelperForm` für seine Schnittstellen.
- `controllers/admin/AdminCdKeysListController.php`:
  - **Registerkartenname:** CD Keys > Liste
  - **Verwaltete Entität:** `cdkey`
  - **Verantwortlichkeit:** Verwaltet den Bestand einzelner CD-Keys. Dies umfasst den Import von CSV-Dateien, das Hinzufügen/Bearbeiten/Löschen von Schlüsseln und die Anzeige ihres Status (verfügbar, verwendet). Es verwendet `HelperList` und `HelperForm`.
- `controllers/admin/index.php`:
  - **Registerkartenname:** CD Keys (Haupt-Dashboard)
  - **Verwaltete Entität:** N/A (Dashboard)
  - **Verantwortlichkeit:** Dies dient wahrscheinlich als Haupt-Dashboard für das Modul, das Analysen, Schlüsselstatistiken und möglicherweise Betrugswarnungen anzeigt. Es aggregiert Daten aus den Tabellen `cdkey_used` und `cdkey`.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist kein explizites Verzeichnis `classes/` auf. Dies deutet darauf hin, dass die primären `ObjectModel`-Definitionen und die Kern-Geschäftslogik wahrscheinlich in der Hauptdatei `cdkeys.php` selbst oder in den jeweiligen Controller-Dateien gekapselt sind.

Wenn `ObjectModel`-Definitionen in `cdkeys.php` vorhanden sind, würden sie typischerweise so aussehen:

- `CdKeyGroup` (für Tabelle `ps_cdkey_group`): Verwaltet Schlüsselgruppen.
  - `$definition` würde `id_cdkey_group`, `name` enthalten.
- `CdKey` (für Tabelle `ps_cdkey`): Verwaltet einzelne Schlüssel.
  - `$definition` würde `id_cdkey`, `id_cdkey_group`, `key_value`, `status` (z. B. 'available', 'used') enthalten.
- `CdKeyUsed` (für Tabelle `ps_cdkey_used`): Verwaltet zugewiesene Schlüssel.
  - `$definition` würde `id_cdkey_used`, `id_cdkey`, `id_order`, `id_customer`, `id_product`, `date_add` enthalten.

### 4.4 JavaScript-Assets (`views/js/`)

- `cdkeys/lib/emailTemplatesManager/js/emailTemplatesManager.js`:
  - **Geltungsbereich:** Back-Office.
  - **Verantwortlichkeit:** Verwaltet die Benutzeroberfläche zum Erstellen, Bearbeiten und Auswählen von E-Mail-Vorlagen innerhalb der Modulkonfiguration. Es verarbeitet wahrscheinlich AJAX-Aufrufe zum Speichern von Vorlageninhalten, zum Vorschau von E-Mails und zum Wechseln zwischen verschiedenen Vorlagenversionen.
- `cdkeys/lib/searchTool/views/js/autocomplete.js`:
  - **Geltungsbereich:** Back-Office.
  - **Verantwortlichkeit:** Bietet Autocomplete-Funktionalität für Suchfelder innerhalb der Admin-Oberflächen des Moduls (z. B. Suche nach Produkten, Kunden oder Schlüsselgruppen). Es bindet an Eingabefelder und führt AJAX-Anfragen aus, um Vorschläge abzurufen.
- `cdkeys/views/js/adminCdKeysDashboard.js`:
  - **Geltungsbereich:** Back-Office (AdminCdKeysDashboardController oder Hauptmodul-Dashboard).
  - **Verantwortlichkeit:** Steuert die interaktiven Elemente des Haupt-Dashboards des Moduls. Dies könnte die Diagramm-Rendering (z. B. mit Chart.js oder ähnlicher Bibliothek), Datenfilterung und dynamische Aktualisierungen von Statistiken umfassen.
- `cdkeys/views/js/cdkeys-dashboard-demo-console.js`:
  - **Geltungsbereich:** Back-Office.
  - **Verantwortlichkeit:** Wahrscheinlich ein Entwicklungs-/Debug-Skript oder eine Demo-Konsole für das Dashboard, das möglicherweise Ereignisse protokolliert oder Testdaten bereitstellt. Sollte in der Produktion nicht aktiv sein.
- `cdkeys/views/js/cdkeys-fraud-demo-console.js`:
  - **Geltungsbereich:** Back-Office.
  - **Verantwortlichkeit:** Ähnlich der Dashboard-Demo-Konsole ist dies wahrscheinlich ein Entwicklungs-/Debug-Skript für die Betrugserkennungsfunktionen. Sollte in der Produktion nicht aktiv sein.
- `cdkeys/views/js/cdkeys-pagination.js`:
  - **Geltungsbereich:** Front-Office (`mykeys.tpl`).
  - **Verantwortlichkeit:** Handhabt die clientseitige Logik für die Paginierung im Bereich „Meine Schlüssel“ des Kunden. Dies könnte AJAX-Aufrufe zum Laden neuer Schlüssel-Seiten ohne vollständiges Neuladen der Seite oder einfach die Verwaltung der Anzeige von Seitenzahlen und Navigation umfassen.

### 4.5 CSS-Stylesheets (`views/css/`)

- `cdkeys/lib/emailTemplatesManager/css/emailTemplatesManager.css`:
  - **Geltungsbereich:** Back-Office.
  - **Haupt-UI-Komponenten:** Gestaltet die E-Mail-Vorlagenverwaltungsoberfläche, einschließlich Formularen, Schaltflächen und Vorschau-Bereichen.
  - **Wichtige CSS-Klassenselektoren:** `.email-template-manager`, `.template-form`, `.template-preview`.
- `cdkeys/lib/searchTool/views/css/autocomplete.css`:
  - **Geltungsbereich:** Back-Office.
  - **Haupt-UI-Komponenten:** Gestaltet die Autocomplete-Dropdowns und Eingabefelder.
  - **Wichtige CSS-Klassenselektoren:** `.autocomplete-suggestions`, `.autocomplete-selected`, `.autocomplete-suggestion`.
- `cdkeys/views/css/admin_cdkeys.css`:
  - **Geltungsbereich:** Back-Office.
  - **Haupt-UI-Komponenten:** Allgemeine Gestaltung für die Admin-Seiten des Moduls, einschließlich Listen, Formularen und Dashboard-Elementen.
  - **Wichtige CSS-Klassenselektoren:** `.cdkeys-admin-panel`, `.cdkeys-table`, `.cdkeys-form-group`.
- `cdkeys/views/css/cdkeys-admin.css`:
  - **Geltungsbereich:** Back-Office.
  - **Haupt-UI-Komponenten:** Zusätzliche oder spezifische Gestaltung für Admin-Oberflächen, die möglicherweise `admin_cdkeys.css` überschreiben oder erweitern.
  - **Wichtige CSS-Klassenselektoren:** `.cdkeys-dashboard-widget`, `.cdkeys-alert`.
- `cdkeys/views/css/css.css`:
  - **Geltungsbereich:** Potenziell sowohl Front-Office als auch Back-Office oder allgemeine Dienstprogramm-Stile.
  - **Haupt-UI-Komponenten:** Könnte grundlegende Stile für Elemente enthalten, die in verschiedenen Teilen des Moduls verwendet werden.
  - **Wichtige CSS-Klassenselektoren:** Generische Klassen, die auf verschiedene Modulelemente angewendet werden könnten.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

#### Hook-Vorlagen (`views/templates/hook/`)

- `cdkeys/views/templates/hook/adminOrder.tpl`:
  - **Hook:** `displayAdminOrder`
  - **Ausgabe:** Zeigt CD-Key-Informationen direkt auf der Bestelldetailseite des PrestaShop Back Office an. Dies ermöglicht Administratoren, schnell zu sehen, welche Schlüssel einer Bestellung zugewiesen wurden.
- `cdkeys/views/templates/hook/adminOrderFraud.tpl`:
  - **Hook:** `displayAdminOrderTop` (oder ähnlich, potenziell `displayAdminOrder`)
  - **Ausgabe:** Zeigt betrugsbezogene Informationen oder Warnungen für eine Bestellung auf der Bestelldetailseite des Back Office an.
- `cdkeys/views/templates/hook/my-account-16.tpl`:
  - **Hook:** `displayCustomerAccount` (für PrestaShop 1.6.x)
  - **Ausgabe:** Fügt einen Link oder Block zur Seite „Mein Konto“ des Kunden hinzu, der ihn zu seinem Bereich „Meine Schlüssel“ leitet.
- `cdkeys/views/templates/hook/my-account-17.tpl`:
  - **Hook:** `displayCustomerAccount` (für PrestaShop 1.7.x, 8.x, 9.x)
  - **Ausgabe:** Ähnlich wie `my-account-16.tpl`, aber angepasst an die unterschiedliche Vorlagenstruktur neuerer PrestaShop-Versionen, fügt einen Link zum Bereich „Meine Schlüssel“ hinzu.
- `cdkeys/views/templates/hook/orderDetailDisplayed.tpl`:
  - **Hook:** `displayOrderDetailDisplayed`
  - **Ausgabe:** Zeigt CD-Key-Informationen auf der Bestelldetailseite des Kunden im Front-Office an.

#### Admin-Vorlagen (`views/templates/admin/`)

- `cdkeys/lib/emailTemplatesManager/views/buttonManager.tpl`:
  - **Zweck:** Rendert Schaltflächen oder Steuerelemente für den E-Mail-Vorlagenmanager.
- `cdkeys/lib/emailTemplatesManager/views/createTemplateForm.tpl`:
  - **Zweck:** Rendert das Formular zum Erstellen neuer E-Mail-Vorlagen.
- `cdkeys/lib/emailTemplatesManager/views/editTemplateForm.tpl`:
  - **Zweck:** Rendert das Formular zum Bearbeiten bestehender E-Mail-Vorlagen.
- `cdkeys/lib/emailTemplatesManager/views/mainForm.tpl`:
  - **Zweck:** Der Hauptcontainer oder das Formular für die E-Mail-Vorlagenverwaltungsoberfläche.
- `cdkeys/lib/emailTemplatesManager/views/selectInput.tpl`:
  - **Zweck:** Rendert ein Dropdown-Auswahlfeld, wahrscheinlich zur Auswahl von E-Mail-Vorlagen oder Sprachen.
- `cdkeys/lib/searchTool/views/scripts.tpl`:
  - **Zweck:** Enthält JavaScript-Skripte für die Suchwerkzeug-/Autocomplete-Funktionalität.
- `cdkeys/views/templates/admin/cdkeys/helpers/list/list_action_email.tpl`:
  - **Zweck:** Rendert eine spezifische Aktionsschaltfläche (z. B. „E-Mail erneut senden“) innerhalb einer `HelperList`-Tabelle in den Admin-Controllern (z. B. `AdminCdKeysArchiveController`).
- `cdkeys/views/templates/admin/customerGroups.tpl`:
  - **Zweck:** Rendert die Kundengruppenauswahl-Oberfläche in der Modulkonfiguration.
- `cdkeys/views/templates/admin/getCombinations.tpl`:
  - **Zweck:** Potenziell zur Anzeige oder Auswahl von Produktkombinationen im Zusammenhang mit CD-Keys verwendet (z. B. wenn verschiedene Kombinationen unterschiedliche Schlüsselgruppen erfordern).
- `cdkeys/views/templates/admin/orderstates.tpl`:
  - **Zweck:** Rendert das Mehrfachauswahl-Dropdown für „Bestellstatus auswählen“ in der Modulkonfiguration.
- `cdkeys/views/templates/admin/orderstatesRadio.tpl`:
  - **Zweck:** Rendert die Radiobutton-Auswahl für „Bestellstatus auswählen“ (für Statusänderung) in der Modulkonfiguration.
- `cdkeys/views/templates/admin/script.tpl`:
  - **Zweck:** Allgemeine Skripteinbindung für Admin-Seiten, möglicherweise für modulspezifisches JS.

#### Front-Office-Vorlagen (`views/templates/front/`)

- `cdkeys/views/templates/front/mykeys.tpl`:
  - **Zweck:** Die Hauptvorlage zur Anzeige der Liste der gekauften CD-Keys des Kunden im Bereich „Mein Konto“. Sie iteriert durch `cdkey_used`-Daten und präsentiert die Schlüssel, Bestelldetails und möglicherweise Paginierungssteuerelemente.

#### E-Mail-Vorlagen (`views/templates/email/`)

- `cdkeys/views/templates/email/multikey-instance.tpl`:
  - **Zweck:** Dies ist die Kernvorlage für die E-Mail, die an Kunden mit ihren CD-Keys gesendet wird. Sie wird dynamisch mit dem Namen des Kunden, Bestelldetails und den tatsächlichen Schlüssel(n) gefüllt.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

- `ps_cdkey_group`: Speichert Informationen über CD-Key-Gruppen.
  - `id_cdkey_group` (PK)
  - `name`
  - `date_add`
  - `date_upd`
- `ps_cdkey`: Speichert einzelne CD-Keys.
  - `id_cdkey` (PK)
  - `id_cdkey_group` (FK zu `ps_cdkey_group`)
  - `key_value` (der eigentliche CD-Key-String)
  - `status` (z. B. 'available', 'used')
  - `date_add`
  - `date_upd`
- `ps_cdkey_used`: Speichert Datensätze von CD-Keys, die Bestellungen zugewiesen wurden.
  - `id_cdkey_used` (PK)
  - `id_cdkey` (FK zu `ps_cdkey`)
  - `id_order` (FK zu `ps_orders`)
  - `id_customer` (FK zu `ps_customer`)
  - `id_product` (FK zu `ps_product`)
  - `date_add`

#### Konfigurationsdatensätze (`ps_configuration`)

- `CDKEYS_ENABLED`: (bool) Hauptschalter.
- `CDKEYS_OSTATES`: (string) Kommagetrennte Liste der Bestellstatus für die Schlüsselzustellung.
- `CDKEYS_GROUPS`: (string) Kommagetrennte Liste der Kundengruppen für die Schlüsselzustellung.
- `CDKEYS_MAX_ORDERTOTAL`: (float) Maximaler Bestellwert für die automatische Zustellung.
- `CDKEY_HOWDELIVER`: (bool) Viele Codes in einer E-Mail senden.
- `CDKEYS_MULTITITLE`: (string) E-Mail-Betreffzeile.
- `CDKEY_STATUSCHANGE`: (bool) Bestellstatus nach Zustellung ändern.
- `CDKEYS_OSTATES_RADIO`: (int) ID des Bestellstatus, in den gewechselt werden soll.
- `CDKEY_INC_INV`: (bool) Schlüssel auf Rechnung aufnehmen.
- `CDKEY_PAGINATION`: (bool) Paginierung für Meine Schlüssel aktivieren.
- `CDKEY_PAGINATION_NB`: (int) Elemente pro Seite für Meine Schlüssel-Paginierung.
- `IV_ROW_DELIMITER`: (string) CSV-Zeilentrennzeichen.
- `IV_COL_DELIMITER`: (string) CSV-Spaltentrennzeichen.
- `CDKEYS_ANALYTICS_*`: Verschiedene Einstellungen für die Dashboard-Analyse.
- `CDKEYS_ALERT_COOLDOWN_HOURS`: (int) Abklingzeit für Betrugswarnungen.
- `CDKEYS_EXPORT_MASK_CODES`: (bool) Codes beim Export maskieren.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionOrderStatusPostUpdate` | Nachdem der Status einer Bestellung aktualisiert (und gespeichert) wurde. | Primärer Auslöser für die CD-Key-Zustellung. Überprüft, ob der neue Status mit den konfigurierten Status übereinstimmt und sendet Schlüssel. |
| `displayAdminOrder` | Rendert Inhalte auf der Bestelldetailseite des Back Office. | Zeigt zugewiesene CD-Keys für die aktuelle Bestellung im Admin-Panel an. |
| `ActionAdminControllerSetMedia` | Wenn ein Admin-Controller initialisiert wird und Medien (JS/CSS) gesetzt werden. | Fügt modulspezifische JS- und CSS-Dateien in das Back Office für Admin-Controller ein. |
| `displayCustomerAccount` | Rendert Inhalte auf der Seite „Mein Konto“ des Kunden. | Fügt einen Link oder Block für „Meine Schlüssel“ im Front-Office-Konto des Kunden hinzu. |
| `DisplayAdminOrderTop` | Rendert Inhalte oben auf der Bestelldetailseite des Back Office. | Potenziell zur Anzeige von Betrugswarnungen oder Zusammenfassungsinformationen zu CD-Keys für die Bestellung verwendet. |
| `actionOrderStatusUpdate` | Bevor der Status einer Bestellung aktualisiert wird (älterer Hook, `actionOrderStatusPostUpdate` wird bevorzugt). | Sekundärer oder Fallback-Auslöser für die CD-Key-Zustellung, um die Kompatibilität mit älteren PrestaShop-Versionen oder spezifischen Szenarien zu gewährleisten. |
| `DisplayBackOfficeHeader` | Rendert Inhalte im Header aller Back-Office-Seiten. | Fügt globale Back-Office-JS/CSS oder Menüpunkte für das Modul ein. |
| `displayHeader` | Rendert Inhalte im `<head>`-Bereich der Front-Office-Seiten. | Fügt Front-Office-spezifische JS/CSS oder Meta-Tags ein. |
| `displayOrderDetailDisplayed` | Rendert Inhalte auf der Bestelldetailseite des Kunden im Front-Office. | Zeigt zugewiesene CD-Keys direkt auf der Bestellübersichtsseite des Kunden an. |
| `actionOrderHistoryAddAfter` | Nachdem ein Bestellhistorie-Eintrag (Statusänderung) hinzugefügt wurde. | Könnte als alternativer Auslöser für die Schlüsselzustellung oder zu Protokollierungszwecken im Zusammenhang mit Statusänderungen verwendet werden. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support melden Sie sich bitte in Ihrem Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/) an. Dort finden Sie Zugang zu Ihren gekauften Modulen und dedizierten Supportkanälen.
