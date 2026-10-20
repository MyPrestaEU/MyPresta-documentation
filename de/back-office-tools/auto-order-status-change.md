---
title: "Automatischer Bestellstatuswechsel – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Automatischer Bestellstatuswechsel“ von MyPresta.eu."
sidebar:
  label: "Automatischer Bestellstatuswechsel – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Auto order status change auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/auto-order-status-change.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/auto-order-status-change/)
>
> ---


# Automatischer Bestellstatuswechsel

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind keine ungewöhnlichen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Automatischer Bestellstatuswechsel)

Dies ist der Haupt- und einzige Konfigurationsbildschirm für das Modul „Automatischer Bestellstatuswechsel“. Hier definieren Sie die Regeln, wie Bestellstatus automatisch übergehen.

Die Konfigurationsseite zeigt Ihnen eine Liste Ihrer aktuellen Bestellstatus an. Für jeden Status können Sie definieren, in welchen neuen Status er automatisch wechseln soll.

**So konfigurieren Sie eine Regel:**

1. **Identifizieren Sie den „Von“-Status:** Auf der linken Seite der Konfigurationstabelle sehen Sie eine Liste aller Ihrer bestehenden Bestellstatus (z. B. „Warten auf Banküberweisung“, „Zahlung akzeptiert“, „Versandt“ usw.). Dies ist der *Startstatus*, der die automatische Änderung auslöst.
2. **Wählen Sie den „Nach“-Status:** Neben jedem „Von“-Status finden Sie ein Dropdown-Menü. Dieses Menü enthält alle verfügbaren Bestellstatus in Ihrem Shop. Wählen Sie den Status aus, in den die Bestellung *automatisch wechseln soll*, wenn sie den „Von“-Status erreicht.
3. **Speichern Sie Ihre Änderungen:** Nachdem Sie Ihre gewünschten Übergänge eingerichtet haben, stellen Sie sicher, dass Sie auf die Schaltfläche **„Speichern“** klicken (normalerweise am unteren Rand der Seite), um Ihre Regeln anzuwenden.

Lassen Sie uns die typischen Einstellungen aufschlüsseln, denen Sie begegnen werden:

#### **Einstellungsgruppe: Automatische Statusübergänge**

Dieser Abschnitt zeigt eine Tabelle oder eine Reihe von Dropdowns an, mit denen Sie „Von“-Status zu „Nach“-Status zuordnen können.

- **Was diese Einstellung bewirkt:** Dies ist die Kernfunktionalität des Moduls. Für jeden bestehenden Bestellstatus in Ihrem Shop können Sie einen *Zielstatus* festlegen, in den eine Bestellung automatisch übergeht, *wenn* ihr Status in den „Von“-Status wechselt.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn ein „Nach“-Status für einen „Von“-Status ausgewählt ist:* Immer wenn der Status einer Bestellung auf den „Von“-Status aktualisiert wird (entweder manuell durch einen Administrator, durch ein Zahlungsgateway oder durch ein anderes Modul), versucht das Modul sofort, ihn in den ausgewählten „Nach“-Status zu ändern.
  - *Wenn „Keine Änderung“ oder Ähnliches ausgewählt ist (oder leer gelassen wird):* Wenn Sie keinen „Nach“-Status für einen bestimmten „Von“-Status auswählen, erfolgt keine automatische Änderung für Bestellungen, die diesen spezifischen „Von“-Status erreichen. Die Bestellung verbleibt einfach im „Von“-Status, bis sie manuell geändert oder durch eine andere Regel/ein anderes Modul bearbeitet wird.
- **Empfohlener Wert:** Dies hängt vollständig vom Workflow Ihres Shops ab.
  - **Beispiel 1 (Zahlung akzeptiert zu In Bearbeitung):**
    - **Von Status:** `Zahlung akzeptiert`
    - **Nach Status:** `In Bearbeitung` (oder `Vorbereitung läuft`)
    - **Zweck & Auswirkung:** Dies ist eine sehr häufige und dringend empfohlene Einrichtung. Wenn ein Kunde bezahlt und die Zahlung bestätigt wird (z. B. durch PayPal, Stripe, Kreditkartenmodul), aktualisiert sich der Bestellstatus automatisch auf „Zahlung akzeptiert“. Diese Regel verschiebt ihn dann sofort in „In Bearbeitung“ und signalisiert Ihrem Lager- oder Fulfillment-Team, mit der Vorbereitung der Bestellung ohne manuelles Eingreifen zu beginnen. Dies spart Zeit und gewährleistet eine schnelle Abwicklung.
  - **Beispiel 2 (Versandt zu Geliefert):**
    - **Von Status:** `Versandt`
    - **Nach Status:** `Geliefert`
    - **Zweck & Auswirkung:** Während „Versandt“ anzeigt, dass der Artikel Ihr Lager verlassen hat, bestätigt „Geliefert“, dass er den Kunden erreicht hat. Wenn Ihre Versanddienstleister-Integration nicht automatisch auf „Geliefert“ aktualisiert, könnten Sie diese Regel einrichten. Seien Sie jedoch vorsichtig: Dies setzt voraus, dass alle „Versandten“ Bestellungen irgendwann „Geliefert“ werden. Es ist oft besser, sich auf die Sendungsverfolgung des Spediteurs für den Status „Geliefert“ zu verlassen, falls möglich. Verwenden Sie dies, wenn Sie „Versandte“ Bestellungen nach einer angemessenen Lieferzeit schnell aus Ihrer aktiven Liste entfernen möchten, aber beachten Sie, dass dies möglicherweise nicht die tatsächliche Lieferung widerspiegelt.
  - **Beispiel 3 (Warten auf Banküberweisung zu Storniert – mit Vorsicht):**
    - **Von Status:** `Warten auf Banküberweisung`
    - **Nach Status:** `Storniert`
    - **Zweck & Auswirkung:** Wenn Sie eine strenge Richtlinie haben, dass Banküberweisungen innerhalb eines bestimmten Zeitrahmens eingehen müssen, und Sie überfällige Bestellungen manuell auf „Storniert“ ändern, könnte dieses Modul dies automatisieren. Das Modul wird jedoch ausgelöst, *wenn der Status auf* „Warten auf Banküberweisung“ *wechselt*. Wenn Sie *nach einer Verzögerung* stornieren möchten, reicht dieses Modul allein nicht aus. Sie bräuchten einen anderen Mechanismus (z. B. einen Cron-Job oder ein anderes Modul), um den Status *nach* der Verzögerung auf „Warten auf Banküberweisung“ zu ändern, was dann dieses Modul auslösen würde, um es auf „Storniert“ zu ändern. Dieser spezifische Anwendungsfall ist für den sofortigen Auslöser dieses Moduls weniger direkt.
- **Händlerszenario / Beispiel:**
  - „Ich möchte, dass alle Bestellungen, bei denen die Zahlung erfolgreich abgeschlossen wurde, automatisch in ‚Vorbereitung läuft‘ verschoben werden, damit mein Packteam sofort mit der Arbeit daran beginnen kann.“
  - „Wenn ein Kunde eine Rückerstattung anfordert und ich den Bestellstatus auf ‚Rückerstattet‘ ändere, möchte ich, dass er automatisch auf ‚Geschlossen‘ verschoben wird, damit er nicht mehr in meiner aktiven Bestellliste ist.“

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | `Von Status` (z. B. Zahlung akzeptiert) | Variiert je nach Workflow | Der ursprüngliche Status, der eine automatische Änderung auslöst. |
| Modulkonfiguration | `Nach Status` (Dropdown für jeden `Von Status`) | `In Bearbeitung` (für `Zahlung akzeptiert`) | Der Zielstatus, in den eine Bestellung automatisch wechselt, wenn sie den `Von Status` erreicht. Automatisiert den Workflow, spart Zeit. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Bestellstatus ändern sich nicht automatisch. Was sollte ich überprüfen?**

- **A:** Gehen Sie zuerst zu **Module > Modul-Manager > Automatischer Bestellstatuswechsel > Konfigurieren** und stellen Sie sicher, dass Sie die „Von“- und „Nach“-Status korrekt eingerichtet haben.
- **A:** Überprüfen Sie, ob die anfängliche Statusänderung (der „Von“-Status) tatsächlich stattfindet. Wenn Sie beispielsweise erwarten, dass „Zahlung akzeptiert“ eine Änderung auslöst, stellen Sie sicher, dass die Bestellung zuerst den Status „Zahlung akzeptiert“ erreicht.
- **A:** Leeren Sie Ihren PrestaShop-Cache. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie oben rechts auf „Cache leeren“. Manchmal benötigen Modulkonfigurationen eine Cache-Aktualisierung, um wirksam zu werden.

**F2: Kann dieses Modul Statusänderungen basierend auf einer Zeitverzögerung vornehmen (z. B. eine Bestellung stornieren, wenn sie nicht innerhalb von 24 Stunden bezahlt wird)?**

- **A:** Nein, dieses Modul wird *sofort* ausgelöst, wenn der Status einer Bestellung in einen bestimmten „Von“-Status *wechselt*. Es verfügt nicht über eine integrierte Funktionalität für zeitbasierte Verzögerungen oder Cron-Jobs. Für zeitbasierte Aktionen benötigen Sie ein separates Modul oder eine benutzerdefinierte Entwicklung, die den Bestellstatus nach einer Verzögerung ändert, was dann dieses Modul auslösen würde.

**F3: Wird dieses Modul die Statusaktualisierungen meines Zahlungsgateways beeinträchtigen?**

- **A:** Nein, es arbeitet *mit* ihnen zusammen. Zahlungsgateways aktualisieren eine Bestellung typischerweise auf einen Status wie „Zahlung akzeptiert“ oder „Warten auf Zahlung“. Dieses Modul übernimmt dann *nach* dieser anfänglichen Aktualisierung und wendet Ihre nächste Regel an. Es verhindert nicht, dass das Zahlungsgateway seinen ursprünglichen Status festlegt.

**F4: Ich habe ein benutzerdefiniertes Theme. Funktioniert dieses Modul?**

- **A:** Ja, absolut. Dieses Modul arbeitet vollständig im PrestaShop-Back-Office und mit der Bestellverarbeitungslogik. Es hat keine visuellen Front-Office-Komponenten oder themenspezifisches Styling, daher ist es vollständig kompatibel mit jedem PrestaShop-Theme.

**F5: Wie übersetze ich die Einstellungen des Moduls, wenn mein Back-Office in einer anderen Sprache ist?**

- **A:** PrestaShop übernimmt die Übersetzung der Bestellstatus automatisch. Das Modul verwendet die Namen Ihrer bestehenden Bestellstatus. Wenn Sie die eigenen Oberflächenelemente des Moduls (wie die Schaltfläche „Speichern“ oder Abschnittstitel) übersetzen müssen, können Sie dies über **International > Übersetzungen** in Ihrem PrestaShop-Back-Office tun. Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme, Ihre Sprache und suchen Sie dann das Modul „schange“.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster, die mit dem Modul „Automatischer Bestellstatuswechsel“ arbeiten.

### 4.1 Architekturübersicht

Das Modul „Automatischer Bestellstatuswechsel“ (`schange`) ist ein unkompliziertes PrestaShop-Modul, das hauptsächlich dazu dient, sich in das `actionOrderStatusPostUpdate`-Ereignis einzuhaken. Es folgt einer Standard-PrestaShop-Modulstruktur und nutzt die `Module`-Klasse für Installation, Deinstallation und Konfiguration. Seine Kernlogik befindet sich in der Hauptmoduldatei und verarbeitet Statusänderungen basierend auf Konfigurationen, die in `ps_configuration` gespeichert sind.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält **keine** benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Konfiguration wird direkt in der Methode `getContent()` der Hauptmoduldatei gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert **keine** benutzerdefinierten Klassen oder `ObjectModel`-Instanzen in einem `classes/`-Verzeichnis. Die gesamte Logik ist in der Hauptklasse `schange` gekapselt.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält **keine** benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält **keine** benutzerdefinierten CSS-Dateien. Das Styling für die Konfigurationsseite wird durch das Standard-Back-Office-CSS von PrestaShop gehandhabt.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul verwendet ein einziges Smarty-Template für seine Konfigurationsoberfläche.

- **Admin-Templates (`views/templates/admin/`)**:
  - `schange/views/tpl/selectedProducts.tpl`: Dieses Template wird innerhalb der Methode `getContent()` verwendet, um das Konfigurationsformular des Moduls zu rendern. Es zeigt typischerweise die Liste der „Von“-Bestellstatus und deren entsprechende „Nach“-Status-Dropdowns an. Entwickler können diese Datei überprüfen, um die Struktur des Konfigurationsformulars und die Darstellung der Statuszuordnung zu verstehen.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt **keine** benutzerdefinierten SQL-Tabellen.
  - Alle Konfigurationseinstellungen (die Zuordnungen von „Von“ zu „Nach“ Status) werden in der Tabelle `ps_configuration` gespeichert. Jede Zuordnung wird wahrscheinlich als separater Konfigurationsschlüssel oder als serialisiertes Array unter einem einzigen Schlüssel gespeichert, wobei der Modulname als Präfix verwendet wird (z. B. `SCHANGE_STATUS_FROM_X_TO_Y` oder `SCHANGE_STATUS_MAP`).
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionOrderStatusPostUpdate` | Wird unmittelbar ausgelöst, nachdem der Status einer Bestellung erfolgreich aktualisiert wurde. | Dies ist der primäre Hook, der vom Modul verwendet wird. Wenn sich der Status einer Bestellung ändert (z. B. von „Warten auf Zahlung“ zu „Zahlung akzeptiert“), wird dieser Hook ausgelöst. Das Modul prüft dann, ob der neue Status (der „Von“-Status) einen konfigurierten „Nach“-Status hat. Wenn eine Zuordnung existiert, aktualisiert das Modul die Bestellung programmatisch auf den festgelegten „Nach“-Status. |

### 4.8 Hauptmoduldatei (`schange/index.php`)

- **Klassenname**: `schange`
- **Elternklasse**: `Module`
- **Schlüsselmethoden**:
  - `__construct()`: Initialisiert Modulmetadaten (Name, Tab, Version, Autor usw.).
  - `install()`: Registriert den Hook `actionOrderStatusPostUpdate` und setzt möglicherweise Standardkonfigurationswerte.
  - `uninstall()`: Deregistriert den Hook und bereinigt Konfigurationswerte aus `ps_configuration`.
  - `getContent()`: Rendert die Konfigurationsseite des Moduls im Back Office. Diese Methode verarbeitet die Formularübermittlung, speichert Einstellungen in `ps_configuration` und zeigt die Statuszuordnungsoberfläche mithilfe von `selectedProducts.tpl` an.
  - `hookActionOrderStatusPostUpdate($params)`: Dies ist der Kernlogik-Handler.
    - Er empfängt `$params`, die `newOrderStatus` und `id_order` enthalten.
    - Er ruft die konfigurierten Statuszuordnungen aus `ps_configuration` ab.
    - Wenn der `newOrderStatus` mit einem konfigurierten „Von“-Status übereinstimmt, lädt er das `Order`-Objekt für `id_order`.
    - Er versucht dann, den Status der Bestellung mithilfe von `Order->setCurrentState()` auf den entsprechenden „Nach“-Status zu aktualisieren.
    - Er stellt sicher, dass die Statusänderung gültig ist und behandelt potenzielle Fehler.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Automatischer Bestellstatuswechsel“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
