---
title: "Commerce Connector Pixel – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Commerce Connector Pixel von MyPresta.eu."
sidebar:
  label: "Commerce Connector Pixel – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Commerce Connector pixel auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/commerce-connector-pixel.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/commerce-connector-pixel/)
>
> ---


# Commerce Connector Pixel

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop-Module ausreichend. Für dieses Modul sind in der Regel keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“ neben dem Modul „Commerce Connector Pixel“, um auf dessen Einstellungen zuzugreifen.

#### **Shop-Ident**

- **Was diese Einstellung bewirkt:** Dies ist die eindeutige Kennung, die Ihnen von Commerce Connector für Ihren spezifischen Shop oder Ihr Händlerkonto zur Verfügung gestellt wird. Sie ist entscheidend, damit Commerce Connector die Verkaufsdaten Ihrem Konto korrekt zuordnen kann.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn auf Ihre korrekte Shop-ID eingestellt:* Der Pixel wird mit Ihrer eindeutigen Kennung ausgelöst, sodass Commerce Connector Verkäufe für Ihren Shop genau verfolgen kann.
  - *Wenn falsch oder leer:* Der Pixel wird möglicherweise nicht korrekt ausgelöst, oder Verkaufsdaten werden dem falschen Konto zugeordnet, was zu ungenauer Verfolgung und potenziell verlorenen Marketing-Erkenntnissen führt.
- **Empfohlener Wert:** Geben Sie die genaue „Shop-Ident“-Zeichenfolge ein, die von Commerce Connector bereitgestellt wird. Dies ist normalerweise eine Kombination aus Buchstaben und Zahlen.
- **Händlerszenario / Beispiel:** Commerce Connector teilt Ihnen mit, dass Ihre Shop-ID „MYSTORE12345“ lautet. Sie würden „MYSTORE12345“ in dieses Feld eingeben. Ohne diese Angabe wüsste Commerce Connector nicht, aus welchem Shop der Verkauf stammt.

#### **Pixel-Starts protokollieren**

- **Was diese Einstellung bewirkt:** Diese Einstellung steuert, ob das Modul jedes Mal, wenn der Commerce Connector Pixel gestartet wird (d.h. jedes Mal, wenn ein Kunde die Bestellbestätigungsseite erreicht und der Pixel versucht, ausgelöst zu werden), einen Protokolleintrag erstellt. Dieses Protokoll kann zur Fehlerbehebung nützlich sein.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn aktiviert („An“):* Das Modul erstellt eine Protokolldatei (normalerweise im Modulverzeichnis), die jeden Pixel-Start detailliert beschreibt, einschließlich Bestelldetails. Dies kann Ihnen helfen zu überprüfen, ob der Pixel wie erwartet ausgelöst wird.
  - *Wenn deaktiviert („Aus“):* Es wird keine Protokolldatei generiert, was die Standardeinstellung für einen Produktions-Shop ist, um Speicherplatz und Verarbeitung zu sparen.
- **Empfohlener Wert:** „Aus“ für einen Live-Produktions-Shop. Aktivieren Sie „An“ nur vorübergehend, wenn Sie Probleme beheben müssen und die Pixel-Aktivität überprüfen möchten.
- **Händlerszenario / Beispiel:** Sie vermuten, dass der Pixel nicht alle Verkäufe verfolgt. Sie aktivieren „Pixel-Starts protokollieren“ auf „An“, tätigen eine Testbestellung und überprüfen dann die Protokolldatei, um zu sehen, ob Ihre Testbestellung aufgezeichnet wurde, was bestätigt, dass der Pixel ausgelöst wurde. Sobald dies bestätigt ist, schalten Sie es wieder auf „Aus“.

#### **Modul aktivieren / deaktivieren**

- **Was diese Einstellung bewirkt:** Dies ist ein Standard-PrestaShop-Modul-Schalter, mit dem Sie das gesamte Commerce Connector Pixel-Modul global aktivieren oder deaktivieren können.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Das Modul ist aktiv, und der Commerce Connector Pixel wird in Ihre Bestellbestätigungsseite eingefügt, um Verkäufe zu verfolgen.
  - *Wenn deaktiviert:* Das Modul ist inaktiv, und der Commerce Connector Pixel ist NICHT auf Ihrer Bestellbestätigungsseite vorhanden, was bedeutet, dass über dieses Modul keine Verkäufe verfolgt werden.
- **Empfohlener Wert:** „An“, wenn Sie Commerce Connector aktiv zur Verkaufsverfolgung verwenden.
- **Händlerszenario / Beispiel:** Sie haben Ihre Commerce Connector-Integration abgeschlossen und möchten mit der Verkaufsverfolgung beginnen. Sie stellen sicher, dass diese Einstellung auf „An“ steht. Wenn Sie Ihre Commerce Connector-Kampagnen vorübergehend pausieren, könnten Sie sie auf „Aus“ stellen, um unnötiges Pixel-Auslösen zu verhindern.

#### Andere Konfigurationsschlüssel (Intern)

Das Modul verwendet auch interne Konfigurationsschlüssel wie `mypresta_updates`, `update_`, `updatev_`, `COMCONN_SIDENT_`, `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`. Diese dienen typischerweise der internen Modulverwaltung, Update-Prüfungen und der Sprachbehandlung innerhalb des PrestaShop Back Office. Händler müssen in der Regel nicht direkt mit diesen interagieren.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Shop-Ident | Ihre eindeutige Commerce Connector ID | Entscheidend für die Zuordnung von Verkaufsdaten zu Ihrem spezifischen Commerce Connector-Konto. |
| Modulkonfiguration | Pixel-Starts protokollieren | Aus | Steuert, ob das Modul eine Protokolldatei der Pixel-Auslösungen erstellt. Für die Fehlerbehebung aktivieren, für den Produktivbetrieb deaktivieren. |
| Modulkonfiguration | Modul aktivieren / deaktivieren | An | Aktiviert oder deaktiviert das gesamte Modul und seine Pixel-Verfolgung global. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul installiert, aber Commerce Connector zeigt keine Verkäufe an. Was soll ich tun?**
A:

1. **„Shop-Ident“ überprüfen:** Gehen Sie zur Modulkonfiguration und stellen Sie sicher, dass Ihre „Shop-Ident“ korrekt eingegeben wurde und genau mit der von Commerce Connector bereitgestellten übereinstimmt.
2. **Modul aktiviert:** Stellen Sie sicher, dass das Modul auf der Konfigurationsseite aktiviert ist.
3. **Cache leeren:** Gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Einstellungen > Leistung** und leeren Sie den Smarty-Cache und alle Caches.
4. **Testkauf:** Führen Sie einen vollständigen Testkauf in Ihrem Shop durch, bis zur Bestellbestätigungsseite.
5. **Protokollierung aktivieren:** Aktivieren Sie vorübergehend „Pixel-Starts protokollieren“ in der Modulkonfiguration, führen Sie einen weiteren Testkauf durch und überprüfen Sie dann die `logFile.tpl` (oder eine ähnliche Protokolldatei) im Modulverzeichnis über FTP, um zu sehen, ob der Pixel-Start aufgezeichnet wurde.
6. **Support kontaktieren:** Wenn die Probleme weiterhin bestehen, wenden Sie sich an den MyPresta.eu-Support mit Details zu Ihrer Konfiguration und eventuellen Protokolleinträgen.

**F: Wird dieses Modul meine Website verlangsamen?**
A: Nein. Der Commerce Connector Pixel ist ein sehr leichtgewichtiges Skript, das nur auf der Bestellbestätigungsseite geladen wird. Diese Seite wird typischerweise nach dem Haupteinkaufserlebnis erreicht, und die Ausführung des Pixels ist minimal, sodass es die Leistung oder Ladezeit Ihres Shops für Kunden nicht merklich beeinträchtigen wird.

**F: Kann ich dieses Modul mit anderen Tracking-Pixeln (z.B. Google Analytics, Facebook Pixel) verwenden?**
A: Ja, absolut. Dieses Modul wurde speziell für die Integration mit Commerce Connector entwickelt. Es arbeitet unabhängig und wird nicht mit anderen Tracking-Pixeln oder Analyse-Skripten, die Sie in Ihrem PrestaShop-Shop installiert haben, in Konflikt geraten.

**F: Wo finde ich die Protokolldatei, wenn ich „Pixel-Starts protokollieren“ aktiviere?**
A: Wenn aktiviert, wird die Protokolldatei typischerweise im Verzeichnis des Moduls generiert. Sie benötigen FTP-Zugriff auf Ihren Server, um zu `your_prestashop_root/modules/comconn/views/templates/hook/logFile.tpl` (oder einem ähnlichen Pfad) zu navigieren und dessen Inhalt anzuzeigen. Denken Sie daran, die Protokollierung zu deaktivieren, sobald die Fehlerbehebung abgeschlossen ist.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Übersicht)

### 4.1 Architekturübersicht

Das Commerce Connector Pixel-Modul (`comconn`) ist ein unkompliziertes PrestaShop-Modul, das dazu dient, einen spezifischen JavaScript-Pixel auf der Bestellbestätigungsseite einzufügen. Es hält sich an die PrestaShop-Modularchitektur und nutzt hauptsächlich den `displayOrderConfirmation`-Hook, um sein Tracking-Skript zu rendern. Die Modullogik ist in der Haupt-PHP-Datei enthalten, die Konfiguration wird über `getContent()` verwaltet und Templates dienen zum Rendern des Pixels und eines optionalen Logs.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Das Modul hängt sich direkt in `displayOrderConfirmation` ein und rendert seinen Inhalt über ein Template.
- **Back-Office-Admin-Controller**: Keine. Die gesamte Konfiguration wird innerhalb der `getContent()`-Methode der Hauptmoduldatei gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

- Keine. Das Modul definiert keine benutzerdefinierten Klassen oder `ObjectModel`-Instanzen. Die gesamte Logik ist in `comconn.php` enthalten.

### 4.4 JavaScript-Assets (`views/js/`)

- Keine. Das Modul bettet das Commerce Connector Pixel-Skript direkt in sein Smarty-Template ein, anstatt auf externe `.js`-Dateien zu verlinken.

### 4.5 CSS-Stylesheets (`views/css/`)

- Keine. Das Modul fügt dem Front- oder Back-Office keine benutzerdefinierten Stile hinzu.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul verwendet Smarty-Templates, um seine Ausgabe zu rendern.

- **Hook-Templates (`views/templates/hook/`)**:

  - `comconn/views/templates/hook/displayOrderConfirmation.tpl`
    - **Hook**: `displayOrderConfirmation`
    - **Zweck**: Dies ist das primäre Template, das für das Rendern des Commerce Connector Pixel-Skripts verantwortlich ist. Es fügt dynamisch die `Shop-Ident` (aus der `COMCONN_SIDENT`-Konfiguration) und Bestelldetails (Bestell-ID, Gesamtbetrag, Währung, Produkte) in den JavaScript-Code ein, der den Pixel auslöst. Dieses Template ist entscheidend für die Kernfunktionalität des Moduls.
  - `comconn/views/templates/hook/logFile.tpl`
    - **Hook**: Nicht direkt gehookt, aber vom internen Protokollierungsmechanismus des Moduls verwendet.
    - **Zweck**: Dieses Template wird verwendet, um Protokolleinträge zu formatieren und zu speichern, wenn die Option „Pixel-Starts protokollieren“ aktiviert ist. Es zeichnet Details jedes Pixel-Starts auf, einschließlich Zeitstempel, Bestell-ID und der an Commerce Connector gesendeten Daten. Entwickler können diese Datei über FTP zur Fehlerbehebung überprüfen.
- **Admin-Templates (`views/templates/admin/`)**: Keine.
- **Front-Office-Templates (`views/templates/front/`)**: Keine.

### 4.7 Datenbankschema & Hooks-Übersicht

- **Datenbanktabellen**: Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es speichert seine Konfigurationseinstellungen in der Standardtabelle `ps_configuration`.

  - `PS_CONFIGURATION`-Einträge:
    - `COMCONN_SIDENT`: Speichert die Commerce Connector Shop-ID des Händlers.
    - `COMCONN_LOG`: Speichert den booleschen Wert (0 oder 1) zum Aktivieren/Deaktivieren der Pixel-Start-Protokollierung.
    - `mypresta_updates`, `update_`, `updatev_`: Interne Schlüssel für Modul-Updates und Versionierung.
- **Registrierte Hooks-Tabelle**:

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `displayOrderConfirmation` | Nachdem ein Kunde eine Bestellung erfolgreich abgeschlossen und die Bestätigungsseite erreicht hat. | Fügt das Commerce Connector Pixel-Skript in die Seite ein, um den abgeschlossenen Kauf zu verfolgen. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und weitere Unterstützung zum Modul „Commerce Connector Pixel“ wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
