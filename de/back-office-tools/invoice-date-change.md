---
title: "Rechnungsdatum ändern - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Rechnungsdatum ändern' von MyPresta.eu."
sidebar:
  label: "Rechnungsdatum ändern - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Invoice date change auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/invoice-date-change.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/invoice-date-change/)
>
> ---


# Rechnungsdatum ändern

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind keine speziellen Serverkonfigurationen über eine Standard-PrestaShop-Hosting-Umgebung hinaus erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“ neben dem Modul „Rechnungsdatum ändern“. Dies führt Sie zum Hauptkonfigurationsbildschirm.

Auf diesem Bildschirm finden Sie die Kernfunktionalität des Moduls, die es Ihnen ermöglicht, das gewünschte Rechnungsdatum für eine Bestellung festzulegen.

**Anwendung:**

1. **Navigieren Sie zu einer Bestellung:**
   - Gehen Sie in Ihrem PrestaShop Back Office zu **Bestellungen > Bestellungen**.
   - Klicken Sie auf eine bestehende Bestellung, um deren Details anzuzeigen.
2. **Suchen Sie den Abschnitt Rechnungsdatum:**
   - Scrollen Sie auf der Bestelldetailseite nach unten. Sie finden einen neuen Abschnitt oder Block zum Thema „Rechnungsdatum ändern“.
   - Dieser Abschnitt erscheint typischerweise innerhalb des Blocks „Dokumente“ oder eines ähnlichen Bereichs, in dem Rechnungen verwaltet werden.
3. **Wählen Sie das gewünschte Datum:**
   - Sie sehen ein Datumsauswahlfeld. Klicken Sie auf dieses Feld, um einen Kalender zu öffnen.
   - Wählen Sie das genaue Datum, das auf der Rechnung erscheinen soll. Dies kann ein vergangenes oder ein zukünftiges Datum sein.
4. **Speichern Sie Ihre Änderungen:**
   - Nach der Datumsauswahl gibt es in diesem Abschnitt eine Schaltfläche „Speichern“ oder „Aktualisieren“. Klicken Sie darauf, um das neue Rechnungsdatum auf die Bestellung anzuwenden.
5. **Rechnung generieren oder neu generieren:**
   - Sobald das Datum gespeichert ist, wird die PDF-Datei das von Ihnen festgelegte Datum widerspiegeln, wenn Sie eine neue Rechnung für diese Bestellung generieren (oder eine bestehende neu generieren).

**Was diese Einstellung bewirkt:** Dieses Modul hat keinen globalen „Ein-/Aus“-Schalter oder komplexe Einstellungen. Seine Hauptfunktion besteht darin, einen Datumswähler direkt in Ihre Bestelldetailseiten im Back Office einzufügen. Dieser Datumswähler ermöglicht es Ihnen, das Standard-Rechnungserstellungsdatum für einzelne Bestellungen manuell zu überschreiben.

**Auswirkung der Änderung dieser Einstellung:**

- *Wenn Sie ein Datum auswählen und speichern:* Das gewählte Datum wird für diese spezifische Bestellung gespeichert. Jede Rechnung, die für diese Bestellung *nachdem* Sie dieses Datum festgelegt haben, generiert wird, verwendet Ihr ausgewähltes Datum anstelle des aktuellen Systemdatums.
- *Wenn Sie den Datumswähler des Moduls nicht verwenden:* PrestaShop generiert weiterhin Rechnungen mit dem aktuellen Datum, wie es standardmäßig der Fall ist.

**Empfohlener Wert:** Verwenden Sie den Datumswähler, um das genaue Datum auszuwählen, das für jede spezifische Rechnung erforderlich ist. Es gibt keinen globalen „empfohlenen Wert“, da das Datum pro Bestellung variieren wird.

**Händlerszenario / Beispiel:**
Stellen Sie sich vor, ein Kunde hat am 15. Januar eine Bestellung aufgegeben, aber aufgrund einer Lagerverzögerung wurde das Produkt erst am 25. Januar versandt und in Rechnung gestellt. Für buchhalterische Zwecke benötigen Sie jedoch, dass das Rechnungsdatum das ursprüngliche Bestelldatum vom 15. Januar widerspiegelt.

1. Sie gehen zur Bestelldetailseite für diese spezifische Bestellung.
2. Im Abschnitt „Rechnungsdatum ändern“ öffnen Sie den Kalender und wählen den 15. Januar aus.
3. Sie klicken auf „Speichern“.
4. Wenn Sie nun die PDF-Rechnung für diese Bestellung generieren, wird „15. Januar“ als Rechnungsdatum angezeigt, obwohl Sie sie am 25. Januar generiert haben.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Bestelldetailseite (Back Office) | Datumswähler (innerhalb des Abschnitts „Rechnungsdatum ändern“) | Variiert pro Bestellung | Ermöglicht die manuelle Auswahl des Rechnungsstellungsdatums für eine bestimmte Bestellung. Das ausgewählte Datum wird auf der generierten PDF-Rechnung angezeigt und überschreibt das standardmäßige aktuelle Datum. |
| Bestelldetailseite (Back Office) | Speichern/Aktualisieren-Schaltfläche | N/A | Wendet das ausgewählte Rechnungsdatum auf die aktuelle Bestellung an. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Datum geändert, aber die Rechnung zeigt immer noch das alte Datum an. Was ist falsch?**
A: Stellen Sie sicher, dass Sie nach der Auswahl des neuen Datums auf der Bestelldetailseite auf die Schaltfläche „Speichern“ oder „Aktualisieren“ geklickt haben. Stellen Sie außerdem sicher, dass Sie eine *neue* Rechnung generieren oder die bestehende *neu generieren*, *nachdem* Sie das neue Datum gespeichert haben. Wenn Sie sich eine bereits heruntergeladene PDF ansehen, wird diese nicht magisch aktualisiert. Sie müssen sie erneut herunterladen.

**F: Der Datumswähler wird auf meiner Bestellseite nicht angezeigt.**
A:

1. **Modulinstallation prüfen:** Gehen Sie zu **Module > Modul-Manager** und stellen Sie sicher, dass „Rechnungsdatum ändern“ installiert und aktiviert ist.
2. **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal benötigt PrestaShop eine Cache-Aktualisierung, um neue Modulelemente anzuzeigen.
3. **Theme-Kompatibilität:** Obwohl das Modul für eine nahtlose Integration konzipiert ist, können sehr stark angepasste Themes gelegentlich stören. Wenn das Leeren des Caches nicht hilft, wechseln Sie vorübergehend zum Standard-PrestaShop-Theme, um zu sehen, ob der Datumswähler erscheint. Wenn ja, benötigt Ihr Theme möglicherweise eine kleine Anpassung.

**F: Kann ich das Datum für mehrere Rechnungen gleichzeitig ändern?**
A: Nein, dieses Modul ist für die Änderung des Rechnungsdatums einzelner Bestellungen konzipiert. Sie müssen die Detailseite jeder Bestellung aufrufen, um das spezifische Rechnungsdatum festzulegen. Es gibt keine Massenbearbeitungsfunktion.

**F: Beeinflusst dieses Modul andere Daten in PrestaShop, wie das Bestelldatum oder das Zahlungsdatum?**
A: Nein, dieses Modul ändert *nur* das Ausstellungsdatum, das auf der generierten PDF-Rechnung erscheint. Es ändert nicht das Bestelldatum, das Zahlungsdatum oder andere Zeitstempel, die mit der Bestellung in Ihrer Datenbank verknüpft sind.

**F: Funktioniert dieses Modul mit meiner benutzerdefinierten Rechnungsvorlage?**
A: Ja, das Modul fügt das gewählte Datum in den Standard-PrestaShop-Rechnungserstellungsprozess ein. Solange Ihre benutzerdefinierte Rechnungsvorlage die Standardvariablen für das Rechnungsdatum korrekt verwendet, sollte sie das vom Modul festgelegte Datum anzeigen.

## 4. Entwickler- & Webmaster-Leitfaden (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Rechnungsdatum ändern“ ist ein leichtgewichtiges PrestaShop-Modul, das hauptsächlich dazu dient, die Back Office-Bestellverwaltungsfunktionalität zu erweitern. Es nutzt das Hook-System von PrestaShop, um ein benutzerdefiniertes Datumseingabefeld in die Bestelldetailseite einzufügen. Wenn ein neues Datum ausgewählt und gespeichert wird, aktualisiert es das Feld `invoice_date` des `OrderInvoice`-Objekts, um sicherzustellen, dass nachfolgende PDF-Rechnungserstellungen das vom Benutzer definierte Datum widerspiegeln. Es verfolgt einen einfachen, direkten Ansatz ohne komplexe MVC-Strukturen oder benutzerdefinierte Datenbanktabellen und stützt sich auf bestehende PrestaShop-Kernfunktionen.

### 4.2 Controller (`controllers/`)

Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Controller ein. Die gesamte Logik wird innerhalb der Hauptmoduldatei (`invoicedate/index.php`) und über das Hook-System von PrestaShop abgewickelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul führt keine benutzerdefinierten Klassen oder Modelle im Verzeichnis `classes/` ein. Es interagiert direkt mit dem Kernobjekt `OrderInvoice` und seinen Eigenschaften.

### 4.4 JavaScript-Assets (`views/js/`)

In diesem Modul sind keine benutzerdefinierten JavaScript-Dateien enthalten. Die Datumsauswahlfunktionalität wird typischerweise von den Kern-JavaScript-Bibliotheken von PrestaShop (z.B. jQuery UI Datepicker) bereitgestellt, die bereits im Back Office geladen sind.

### 4.5 CSS-Stylesheets (`views/css/`)

In diesem Modul sind keine benutzerdefinierten CSS-Dateien enthalten. Das Styling für den Datumswähler und die umgebenden Elemente basiert auf dem Standard-Back-Office-CSS von PrestaShop.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul verwendet zwei spezifische Templates, um das Datumseingabefeld auf der Bestelldetailseite anzuzeigen, abhängig von der PrestaShop-Version.

- **Hook-Templates (`views/templates/hook/`)**:
  - `invoicedate/views/templates/hook/displayAdminOrder16.tpl`
    - **Hook**: Dieses Template wird im Hook `displayAdminOrder` gerendert, speziell für PrestaShop 1.6.x-Versionen.
    - **Zweck**: Es gibt die HTML-Struktur für das Rechnungsdatum-Eingabefeld (einen Datumswähler) und eine Absende-Schaltfläche innerhalb der Bestelldetailseite im PrestaShop 1.6 Back Office aus. Es ermöglicht dem Administrator, ein benutzerdefiniertes Rechnungsdatum für die aktuelle Bestellung auszuwählen und zu speichern.
  - `invoicedate/views/templates/hook/displayAdminOrder17.tpl`
    - **Hook**: Dieses Template wird im Hook `displayAdminOrder` gerendert, speziell für PrestaShop 1.7.x und neuere Versionen.
    - **Zweck**: Ähnlich wie die 1.6-Version bietet dieses Template das HTML für das Rechnungsdatum-Eingabefeld und die Absende-Schaltfläche, angepasst an die strukturellen und stilistischen Unterschiede der PrestaShop 1.7+ Back Office-Bestellseite.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Dieses Modul erstellt keine neuen benutzerdefinierten Datenbanktabellen. Es ändert das Feld `invoice_date` der bestehenden Tabelle `ps_order_invoice` (oder `_order_invoice`, abhängig von Ihrem Präfix), wenn ein Rechnungsdatum über die Moduloberfläche aktualisiert wird.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayAdminOrder` | Wird auf der PrestaShop Back Office Bestelldetailseite ausgeführt. | Dieser Hook wird verwendet, um das benutzerdefinierte HTML des Moduls (den Datumswähler und die Speichern-Schaltfläche) in die Bestelldetailansicht einzufügen, sodass der Händler mit der Rechnungsdatumseinstellung interagieren kann. Das Modul verwendet versionsspezifische Templates (`displayAdminOrder16.tpl` oder `displayAdminOrder17.tpl`) für diesen Hook. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Rechnungsdatum ändern“ verweisen wir Sie auf Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.
