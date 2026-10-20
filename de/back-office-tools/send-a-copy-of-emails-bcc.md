---
title: "E-Mail-Kopien senden (BCC) – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „E-Mail-Kopien senden (BCC)“ von MyPresta.eu."
sidebar:
  label: "E-Mail-Kopien senden (BCC)"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Send a copy of emails (BCC) auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/send-a-copy-of-emails-bcc.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/send-a-copy-of-emails-bcc/)
>
> ---


# E-Mail-Kopien senden (BCC)

## 1. Anforderungen & Kompatibilität
- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)
Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zur Hauptkonfigurationsseite des Moduls.

#### **MyPresta.eu Updates & Versionsprüfung**
Oben auf der Konfigurationsseite sehen Sie in der Regel Einstellungen zu MyPresta.eu-Updates. Diese sind Standard für MyPresta.eu-Module und helfen Ihnen, Ihr Modul auf dem neuesten Stand zu halten.

-   **Was diese Einstellung bewirkt:** Diese Felder (oft als `mypresta_updates`, `update_`, `updatev_` bezeichnet) werden vom Modul verwendet, um nach neuen Versionen von MyPresta.eu zu suchen und Sie zu informieren, wenn ein Update erforderlich ist. Sie sind normalerweise vorausgefüllt oder werden automatisch verwaltet.
-   **Auswirkung einer Änderung dieser Einstellung:**
    -   *Wenn aktiviert/aktiv:* Das Modul kann regelmäßig nach Updates suchen und Sie im PrestaShop Back Office benachrichtigen, wenn eine neue Version verfügbar ist.
    -   *Wenn deaktiviert/inaktiv:* Sie erhalten möglicherweise keine automatischen Benachrichtigungen über Modul-Updates, was manuelle Überprüfungen erfordert.
-   **Empfohlener Wert:** Belassen Sie diese Einstellungen wie sie sind, normalerweise aktiviert oder automatisch verwaltet, um sicherzustellen, dass Sie immer über die neuesten Modulversionen und Sicherheitskorrekturen informiert sind.
-   **Händlerszenario / Beispiel:** Sie möchten benachrichtigt werden, wenn eine neue Version des Moduls veröffentlicht wird, die neue Funktionen oder Fehlerbehebungen enthält, daher halten Sie diese Update-Prüfungen aktiv.

#### **Haupteinstellungen des Moduls**
Unter den Update-Einstellungen finden Sie die Kernkonfigurationsoptionen für die BCC-E-Mail-Funktionalität.

-   **E-Mail-Adresse für BCC:**
    -   **Was diese Einstellung bewirkt:** Dies ist die wichtigste Einstellung. Sie definiert die E-Mail-Adresse, an die alle ausgewählten BCC-Kopien gesendet werden.
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Wenn eine gültige E-Mail-Adresse festgelegt ist:* Alle in der Liste unten ausgewählten E-Mails erhalten eine Blindkopie an diese Adresse.
        -   *Wenn leer gelassen oder eine ungültige Adresse festgelegt ist:* Es werden keine BCC-Kopien gesendet, auch wenn E-Mails in der Liste ausgewählt sind.
    -   **Empfohlener Wert:** Eine dedizierte E-Mail-Adresse für die Archivierung (z. B. `archive@ihrshop.com`, `support@ihrshop.com` oder Ihre persönliche Admin-E-Mail).
    -   **Händlerszenario / Beispiel:** Sie möchten, dass alle Bestellbestätigungen an den Posteingang Ihres Kundenservice-Teams, `support@ihrshop.com`, kopiert werden, also geben Sie diese Adresse hier ein.

-   **E-Mails für BCC auswählen:**
    -   **Was diese Einstellung bewirkt:** Dieser Abschnitt zeigt eine Liste aller E-Mail-Vorlagen (E-Mail-Typen), die Ihr PrestaShop-Shop senden kann. Sie können auswählen, welche spezifischen E-Mail-Typen Sie per BCC senden möchten.
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Wenn ein E-Mail-Typ aktiviert ist:* Eine BCC-Kopie dieses spezifischen E-Mail-Typs wird an die „E-Mail-Adresse für BCC“ gesendet, wann immer Ihr Shop diese sendet.
        -   *Wenn ein E-Mail-Typ deaktiviert ist:* Es wird keine BCC-Kopie für diesen spezifischen E-Mail-Typ gesendet.
    -   **Empfohlener Wert:** Wählen Sie nur die E-Mail-Typen aus, die für Ihre Aufzeichnung oder betrieblichen Anforderungen kritisch sind. Zu viele BCCs können einen Posteingang überfluten. Häufige Auswahlmöglichkeiten sind:
        -   `order_conf` (Bestellbestätigung)
        -   `shipped` (Bestellung versandt)
        -   `contact_form` (Kontaktformular-Einreichung)
        -   `password` (Passwort-Reset)
        -   `account` (Neue Kontoerstellung)
    -   **Händlerszenario / Beispiel:** Sie möchten alle neuen Bestellungen und Kundenanfragen aufzeichnen. Sie würden `order_conf` und `contact_form` aus der Liste auswählen.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### **E-Mail-BCC-Verwaltung (Back Office > Erweiterte Einstellungen > E-Mail-BCC)**
Dieses Modul erstellt einen dedizierten Menüpunkt in Ihrem PrestaShop Back Office unter „Erweiterte Einstellungen“ (oder ähnlich, je nach PrestaShop-Version) mit dem Namen „E-Mail-BCC“. Dieser Bildschirm wird vom `AdminMailBccController` verwaltet.

-   **Bildschirmname & Menüpfad:** **Erweiterte Einstellungen > E-Mail-BCC**
-   **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm zeigt typischerweise ein Raster (Liste) aller E-Mail-Typen an, die Sie für BCC konfiguriert haben, zusammen mit der BCC-E-Mail-Adresse. Er dient als Zusammenfassungs- und Verwaltungsoberfläche für Ihre BCC-Einstellungen.
    -   Sie könnten Spalten sehen wie:
        -   **ID:** Interne Kennung für die BCC-Regel.
        -   **E-Mail-Vorlage:** Der Name der E-Mail-Vorlage (z. B. `order_conf`).
        -   **BCC-E-Mail:** Die E-Mail-Adresse, an die die Kopie gesendet wird.
        -   **Aktiviert:** Ein Umschalter zum schnellen Aktivieren oder Deaktivieren von BCC für diesen spezifischen E-Mail-Typ.
        -   **Aktionen:** Schaltflächen zum Bearbeiten oder Löschen der BCC-Regel (obwohl oft die Hauptkonfigurationsseite des Moduls für die Massenauswahl verwendet wird).
-   **Auswirkung von Änderungen:**
    -   *Aktivieren/Deaktivieren einer Regel:* Steuert direkt, ob eine BCC-Kopie für diesen spezifischen E-Mail-Typ gesendet wird.
    -   *Bearbeiten einer Regel:* Ermöglicht Ihnen, die BCC-E-Mail-Adresse für einen spezifischen E-Mail-Typ zu ändern (wenn das Modul BCC-Adressen pro E-Mail unterstützt, andernfalls spiegelt es die globale Einstellung wider).
    -   *Löschen einer Regel:* Entfernt die BCC-Einstellung für diesen E-Mail-Typ.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Verwenden Sie diesen Bildschirm, um schnell zu überprüfen, welche E-Mails per BCC gesendet werden, und um schnelle Aktivierungs-/Deaktivierungsänderungen vorzunehmen, ohne zur Hauptmodulkonfiguration zurückkehren zu müssen. Zum Hinzufügen neuer E-Mail-Typen oder Ändern der primären BCC-Adresse ist die Hauptmodulkonfigurationsseite in der Regel effizienter.

#### **index.php (bccmail/controllers/admin/index.php)**
Diese Datei ist eine Standard-PrestaShop-Praxis zur Sicherung von Admin-Controller-Verzeichnissen und bietet in der Regel keine benutzerorientierte Oberfläche oder Konfigurationsoptionen direkt an. Sie enthält normalerweise ein einfaches `header('Location: ../../index.php?controller=AdminHome');` oder Ähnliches, um unbefugten Zugriff umzuleiten und das direkte Durchsuchen des Verzeichnisses zu verhindern. Händler werden nicht mit dieser Datei interagieren.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| **Modulkonfigurationsseite** | MyPresta.eu Updates | Aktiviert | Hält Sie über Modul-Updates auf dem Laufenden. |
| | **E-Mail-Adresse für BCC** | Ihre Admin-E-Mail / `archive@ihrshop.com` | Die Ziel-E-Mail für alle BCC-Kopien. Entscheidend für die Archivierung. |
| | **E-Mails für BCC auswählen** | `order_conf`, `contact_form`, `shipped` | Wählen Sie aus, welche spezifischen E-Mail-Typen kopiert werden sollen. Verhindert das Überfluten des Posteingangs. |
| **Erweiterte Einstellungen > E-Mail-BCC** | E-Mail-Vorlagenliste | Variiert je nach Auswahl | Übersicht und schneller Umschalter für konfigurierte BCC-E-Mail-Typen. |
| | Aktiviert-Umschalter | Aktiviert | Aktiviert/deaktiviert BCC schnell für einen bestimmten E-Mail-Typ. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul konfiguriert, erhalte aber keine BCC-E-Mails. Was sollte ich überprüfen?**
A:
1.  **Überprüfen Sie die BCC-E-Mail-Adresse:** Gehen Sie zu **Module > Modul-Manager > Konfigurieren** für „E-Mail-Kopien senden (BCC)“ und stellen Sie sicher, dass die „E-Mail-Adresse für BCC“ korrekt geschrieben und gültig ist.
2.  **Überprüfen Sie die ausgewählten E-Mail-Typen:** Stellen Sie sicher, dass die spezifischen E-Mail-Typen, die Sie kopiert haben möchten (z. B. `order_conf`), in der Modulkonfiguration tatsächlich aktiviert sind.
3.  **Überprüfen Sie den Spam-Ordner:** Die BCC-E-Mails könnten im Spam- oder Junk-Ordner des Posteingangs des BCC-Empfängers landen.
4.  **PrestaShop E-Mail-Einstellungen:** Stellen Sie sicher, dass die allgemeinen E-Mail-Einstellungen Ihres PrestaShop-Shops (**Erweiterte Einstellungen > E-Mail**) korrekt konfiguriert sind und dass Ihr Shop generell E-Mails senden kann. Testen Sie dies, indem Sie eine Test-E-Mail von PrestaShop senden.
5.  **Cache leeren:** Manchmal kann der PrestaShop-Cache verhindern, dass Änderungen sofort wirksam werden. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen).

**F: Kann ich BCC-Kopien an mehrere E-Mail-Adressen senden?**
A: Die primäre Konfiguration des Moduls erlaubt eine Haupt-BCC-E-Mail-Adresse. Wenn Sie Kopien an mehrere Adressen senden müssen, haben Sie zwei Optionen:
1.  Legen Sie die BCC-E-Mail-Adresse auf eine Verteilerliste oder Gruppen-E-Mail-Adresse fest, die an mehrere Empfänger weiterleitet.
2.  Konfigurieren Sie eine E-Mail-Regel im Posteingang des BCC-Empfängers, um Kopien automatisch an andere Adressen basierend auf Absender oder Betreff weiterzuleiten.

**F: Wird dieses Modul meinen Shop oder den E-Mail-Versand verlangsamen?**
A: Die Auswirkungen auf die Leistung sind im Allgemeinen vernachlässigbar. Das Senden einer zusätzlichen BCC-Kopie ist ein sehr geringer Vorgang für den Mailserver. Das Modul verwendet den Standard-E-Mail-Versandmechanismus von PrestaShop und fügt lediglich einen zusätzlichen Empfänger hinzu.

**F: Mein benutzerdefiniertes Theme hat benutzerdefinierte E-Mail-Vorlagen. Funktioniert dieses Modul trotzdem?**
A: Ja, das Modul greift in die Kern-`Mail`-Klasse von PrestaShop ein, die für das Senden aller E-Mails verantwortlich ist, unabhängig davon, ob sie Standard- oder benutzerdefinierte Vorlagen verwenden. Solange PrestaShop die E-Mail sendet, kann dieses Modul sie per BCC senden.

**F: Wie übersetze ich die Benutzeroberfläche des Moduls in eine andere Sprache?**
A: Gehen Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**. Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann „E-Mail-Kopien senden (BCC)“. Sie können dann alle vom Modul im Back Office angezeigten Zeichenketten übersetzen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten Einblick in die technische Implementierung des Moduls „E-Mail-Kopien senden (BCC)“ für Entwickler und Webmaster.

### 4.1 Architekturübersicht
Das Modul „E-Mail-Kopien senden (BCC)“ (`bccmail`) funktioniert hauptsächlich durch das Überschreiben der Kern-`Mail`-Klasse von PrestaShop. Dies ist eine gängige und leistungsstarke Technik in PrestaShop, um das Kernverhalten zu ändern, ohne Kerndateien direkt zu bearbeiten. Durch das Überschreiben von `Mail.php fängt das Modul alle E-Mail-Sendeoperationen ab und injiziert die BCC-Funktionalität basierend auf seiner Konfiguration. Es folgt einer Standard-PrestaShop-Modulstruktur mit einer Hauptmoduldatei, Admin-Controllern für die Konfiguration und einer Override-Klasse.

### 4.2 Controller (`controllers/`)

-   **Front-Office-Controller**: Dieses Modul hat keine dedizierten Front-Office-Controller, da seine Funktionalität vollständig im Back-Office und serverseitig ist.

-   **Back-Office-Admin-Controller**:
    *   `bccmail/controllers/admin/AdminMailBcc.php`
        *   **Klassenname & Elternklasse:** `AdminMailBccController` erweitert `ModuleAdminController`.
        *   **Tab-Name und verwaltete Entität:** Dieser Controller verwaltet den Tab „E-Mail-BCC“ unter „Erweiterte Einstellungen“. Er ist verantwortlich für die Anzeige und Verwaltung der Liste der konfigurierten BCC-E-Mail-Typen. Er verwendet wahrscheinlich PrestaShops `HelperList` oder `HelperView`, um ein Raster von `MailBcc`-Objekten (oder eine Darstellung der Modulkonfiguration) zu rendern.
        *   **Verantwortlichkeit:** Behandelt die Anzeige der BCC-Konfigurationszusammenfassung und ermöglicht möglicherweise die individuelle Aktivierung/Deaktivierung oder Löschung von Regeln. Er interagiert mit den Konfigurationsdaten des Moduls (wahrscheinlich in `ps_configuration` oder einer benutzerdefinierten Tabelle gespeichert, falls komplexere Daten pro BCC-Regel benötigt werden).
    *   `bccmail/controllers/admin/index.php`
        *   **Klassenname & Elternklasse:** Keine Klasse, sondern eine Sicherheitsdatei.
        *   **Verantwortlichkeit:** Diese Datei ist eine Standard-PrestaShop-Sicherheitsmaßnahme. Sie enthält typischerweise `header('Location: ../../index.php?controller=AdminHome');` oder Ähnliches, um die direkte Verzeichnisauflistung und den unbefugten Zugriff auf das Verzeichnis `controllers/admin` zu verhindern. Sie bietet keine funktionale Logik für das Modul selbst.

### 4.3 Kernklassen & Modelle (`classes/`)

-   `bccmail/override/classes/Mail.php`
    *   **Mit welcher Datenbanktabelle es interagiert:** Interagiert indirekt mit `ps_configuration`, um die Moduleinstellungen (BCC-E-Mail-Adresse und ausgewählte E-Mail-Vorlagen) abzurufen.
    *   **Ob es `ObjectModel` erweitert:** Nein, es überschreibt die Kern-`Mail`-Klasse.
    *   **Wichtige öffentliche Methoden und gekapselte Geschäftslogik:**
        *   Diese Datei enthält die Kernlogik zum Abfangen des E-Mail-Versands. Sie überschreibt die Methode `send()` (oder eine ähnliche Methode) der ursprünglichen `Mail`-Klasse.
        *   Innerhalb der überschriebenen `send()`-Methode wird sie:
            1.  Die Modulkonfiguration abrufen: die globale BCC-E-Mail-Adresse und die Liste der für BCC ausgewählten E-Mail-Vorlagen.
            2.  Prüfen, ob die aktuell gesendete E-Mail (identifiziert durch ihren Vorlagennamen, z. B. `order_conf`) in der Liste der ausgewählten BCC-Vorlagen enthalten ist.
            3.  Wenn eine Übereinstimmung gefunden wird, werden die E-Mail-Header oder -Parameter geändert, um die konfigurierte BCC-E-Mail-Adresse einzuschließen, bevor die übergeordnete `Mail::send()`-Methode aufgerufen wird, um die E-Mail zu versenden.
        *   Dies stellt sicher, dass der BCC-Empfänger zur Blindkopie-Liste der E-Mail hinzugefügt wird, wodurch er für die primären Empfänger unsichtbar wird.

-   `bccmail/override/classes/index.php`
    *   **Verantwortlichkeit:** Ähnlich wie `controllers/admin/index.php` ist dies eine Sicherheitsdatei, um die direkte Verzeichnisauflistung des Verzeichnisses `override/classes` zu verhindern. Sie enthält typischerweise ein leeres PHP-Tag oder eine Weiterleitung.

### 4.4 JavaScript-Assets (`views/js/`)

-   `bccmail/views/templates/admin/js/bccmail.js`
    *   **Geltungsbereich:** Back-Office.
    *   **Welche Event-Listener es bindet:** Dieses Skript wird wahrscheinlich auf der Konfigurationsseite des Moduls oder dem `AdminMailBccController`-Bildschirm verwendet. Es könnte Listener binden für:
        *   Formular-Übermittlungsereignisse zur Speicherung der Konfiguration.
        *   Kontrollkästchenänderungen zur Auswahl von E-Mail-Vorlagen für BCC.
        *   Eingabefeldvalidierung für die BCC-E-Mail-Adresse.
        *   AJAX-Aufrufe zur dynamischen Aktualisierung von Einstellungen ohne vollständiges Neuladen der Seite.
    *   **Welche DOM-Manipulationen, modalen Popups, Animationen oder externen Drittanbieter-SDK-Aufrufe es ausführt:** Könnte einfache DOM-Manipulationen durchführen, wie das Anzeigen/Ausblenden von Elementen basierend auf Auswahlen, das Anzeigen von Erfolgs-/Fehlermeldungen oder grundlegende Formularvalidierung. Für die Funktionalität dieses Moduls sind komplexe Animationen oder Drittanbieter-SDKs unwahrscheinlich.

### 4.5 CSS-Stylesheets (`views/css/`)
Das Modul scheint keine benutzerdefinierten CSS-Dateien in seinem Archiv zu enthalten. Es verlässt sich wahrscheinlich auf die Standard-Back-Office-Formatierung von PrestaShop für seine Konfigurationsformulare und -listen oder auf Inline-Styles, falls unbedingt erforderlich.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

-   **Hook-Vorlagen (`views/templates/hook/`)**: Keine explizit aufgeführt, aber das Hauptkonfigurationsformular des Moduls (`getContent()`) würde seine Einstellungen mithilfe einer Smarty-Vorlage rendern, die typischerweise in `views/templates/admin/configure.tpl` oder ähnlich liegt, auch wenn sie nicht explizit im Inventar als separate Datei aufgeführt ist.
-   **Admin-Vorlagen (`views/templates/admin/`)**:
    *   `bccmail/lib/searchTool/views/scripts.tpl`
        *   **Zweck:** Diese Vorlage ist wahrscheinlich Teil einer Hilfs- oder Dienstprogrammbibliothek innerhalb des Moduls (z. B. ein Suchwerkzeug für E-Mail-Vorlagen). Sie würde JavaScript- oder Smarty-Logik enthalten, um Sucheingaben zu rendern, Listen zu filtern oder dynamische Inhaltsladungen innerhalb der Admin-Oberfläche zu verwalten. Es ist keine eigenständige Seite, sondern eine Komponente.
-   **Front-Office-Vorlagen (`views/templates/front/`)**: Keine. Das Modul hat keine Front-Office-Präsenz.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:
    *   Das Modul speichert seine Konfiguration hauptsächlich in der PrestaShop-Tabelle `ps_configuration`.
        *   `PS_CONFIGURATION`-Schlüssel würden Folgendes umfassen:
            *   `BCCMAIL_EMAIL_ADDRESS`: Speichert die Haupt-E-Mail-Adresse für BCC.
            *   `BCCMAIL_SELECTED_TEMPLATES`: Speichert ein serialisiertes Array oder eine durch Kommas getrennte Zeichenfolge der für BCC ausgewählten E-Mail-Vorlagennamen.
            *   `MYPRESTA_UPDATES`, `UPDATE_`, `UPDATEV_`: Für Modul-Update-Prüfungen.
    *   Basierend auf dem bereitgestellten Inventar werden von diesem Modul keine benutzerdefinierten SQL-Tabellen explizit erstellt.

-   **Registrierte Hooks-Tabelle**:
    Das Modul registriert keine Standard-Display-Hooks (wie `displayHeader`, `displayRightColumn`, `displayFooter`), da es keine Front-Office-Präsenz hat. Seine Kernfunktionalität basiert auf dem Überschreiben der `Mail`-Klasse und nicht auf der Verwendung traditioneller PrestaShop-Hooks für den E-Mail-Versand.

    Es „hookt“ sich jedoch implizit über seinen Override in den E-Mail-Versandprozess ein.
    *   **`actionEmailSend` (Implizit über Override)**: Obwohl kein formal registrierter Hook, fängt die Datei `override/classes/Mail.php` des Moduls effektiv die Methode `Mail::send()` ab, die die Kernaktion des E-Mail-Versands ist. Hier wird die BCC-Logik injiziert.
        *   **Ausführungszeitpunkt:** Jedes Mal, wenn `Mail::send()` von PrestaShop aufgerufen wird (z. B. bei Bestellbestätigung, Kundenregistrierung, Kontaktformular-Einreichung).
        *   **Technischer Zweck:** Den konfigurierten BCC-Empfänger zur E-Mail hinzuzufügen, bevor sie vom PrestaShop-Mailer versendet wird.

## 5. Offizieller Support & Updates
Für die neuesten Modul-Updates, technischen Support und zusätzliche Ressourcen besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zum Modul „E-Mail-Kopien senden (BCC)“ zur Verfügung.
