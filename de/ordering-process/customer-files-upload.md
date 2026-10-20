---
title: "Kunden-Dateiupload - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Kunden-Dateiupload' von MyPresta.eu."
sidebar:
  label: "Kunden-Dateiupload - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Customer Files Upload auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/customer-files-upload.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/customer-files-upload/)
>
> ---


# Kunden-Dateiupload

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) werden typischerweise von PrestaShop selbst benötigt und sind für dieses Modul ausreichend. Stellen Sie sicher, dass Ihr Server über ausreichend Speicherplatz zum Speichern hochgeladener Dateien verfügt.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul, der nach der Installation oder durch Klicken auf „Konfigurieren“ im Modul-Manager aufgerufen wird.

-   **Modul aktivieren:**

    *   **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter zum Aktivieren oder Deaktivieren der Modulfunktionalität in Ihrem gesamten Shop.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Alle Dateiupload-Funktionen, die Dateiverwaltung für Kunden und Back-Office-Tools werden aktiv.
        *   *Wenn deaktiviert:* Die Funktionen des Moduls sind vollständig ausgeschaltet, und es werden keine Upload-Formulare oder „Meine Dateien“-Bereiche angezeigt.
    *   **Empfohlener Wert:** JA
    *   **Händlerszenario / Beispiel:** Wenn Sie das Modul zum ersten Mal einrichten oder Wartungsarbeiten durchführen, können Sie es vorübergehend deaktivieren. Andernfalls lassen Sie es aktiviert, um den Dateiupload-Dienst anzubieten.
-   **Uploads auf Produktseite erlauben:**

    *   **Was diese Einstellung bewirkt:** Steuert, ob Kunden Dateien direkt von einer Produktseite hochladen können.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Ein Upload-Formular wird auf Produktseiten angezeigt, das Kunden ermöglicht, Dateien anzuhängen, bevor sie das Produkt in den Warenkorb legen.
        *   *Wenn deaktiviert:* Es wird kein Upload-Formular auf Produktseiten sichtbar sein.
    *   **Empfohlener Wert:** JA (wenn Ihre Produkte Anpassungsdateien vor dem Kauf erfordern)
    *   **Händlerszenario / Beispiel:** Wenn Sie individuell bedruckte Tassen verkaufen, ermöglicht diese Einstellung Kunden, ihr Foto direkt auf der Produktseite der Tasse hochzuladen.
-   **Uploads auf Warenkorbseite erlauben:**

    *   **Was diese Einstellung bewirkt:** Bestimmt, ob ein Upload-Bereich auf der Warenkorb-Übersichtsseite angezeigt wird.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Kunden können allgemeine Dateien hochladen, die sich auf ihren gesamten Warenkorb oder bestimmte Artikel beziehen, bevor sie zur Kasse gehen.
        *   *Wenn deaktiviert:* Es wird kein Upload-Formular auf der Warenkorbseite sichtbar sein.
    *   **Empfohlener Wert:** JA (wenn Kunden möglicherweise allgemeine Bestellanweisungen oder Dateien für mehrere Artikel bereitstellen müssen)
    *   **Händlerszenario / Beispiel:** Ein Kunde, der mehrere kundenspezifische Artikel bestellt, könnte ein einzelnes Dokument mit allgemeinen Anweisungen oder einem Branding-Leitfaden für die gesamte Bestellung hochladen.
-   **Uploads auf Bestellbestätigungsseite erlauben:**

    *   **Was diese Einstellung bewirkt:** Steuert, ob Kunden Dateien sofort nach der Bestellung auf dem Bestellbestätigungsbildschirm hochladen können.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Ein Upload-Formular erscheint auf der „Bestellbestätigung“-Seite, das Kunden ermöglicht, Dateien zu ihrer neu aufgegebenen Bestellung anzuhängen.
        *   *Wenn deaktiviert:* Es wird kein Upload-Formular auf der Bestellbestätigungsseite sichtbar sein.
    *   **Empfohlener Wert:** JA (sehr empfehlenswert für die meisten Anwendungsfälle)
    *   **Händlerszenario / Beispiel:** Ein Kunde hat gerade ein individuelles Banner gekauft. Er kann seine hochauflösende Designdatei sofort auf der Bestätigungsseite hochladen, ohne woanders navigieren zu müssen.
-   **Uploads im Kundenkonto erlauben (Meine Dateien & Bestellhistorie):**

    *   **Was diese Einstellung bewirkt:** Aktiviert den Bereich „Meine Dateien“ im Kundenkonto und erlaubt Uploads auf einzelnen Bestelldetailseiten innerhalb ihrer Historie.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Kunden erhalten einen dedizierten Bereich „Meine Dateien“, um alle ihre Uploads zu verwalten und können Dateien zu bestimmten vergangenen Bestellungen hinzufügen.
        *   *Wenn deaktiviert:* Kunden können Dateien nicht über ihr Konto verwalten, und es werden keine Upload-Optionen auf den Bestellhistorie-Seiten angezeigt.
    *   **Empfohlener Wert:** JA (bietet maximale Flexibilität und Kundenkontrolle)
    *   **Händlerszenario / Beispiel:** Ein Kunde bemerkt einen Tag später, dass er eine bestimmte Schriftartdatei für seine individuelle T-Shirt-Bestellung vergessen hat hochzuladen. Er kann sich in sein Konto einloggen, zur Bestellung gehen und sie hochladen.
-   **Maximale Dateigröße (MB):**

    *   **Was diese Einstellung bewirkt:** Legt die Obergrenze für die Größe jeder einzelnen Datei fest, die ein Kunde hochladen kann.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn ein Wert festgelegt ist (z. B. 10):* Kunden wird das Hochladen von Dateien, die größer als 10 MB sind, untersagt.
        *   *Wenn auf 0 oder leer gesetzt:* Das Modul wird sich typischerweise an die PHP-Upload-Limits Ihres Servers halten, die sehr hoch oder sehr niedrig sein können.
    *   **Empfohlener Wert:** 5-20 MB (anpassen basierend auf typischen Dateitypen; z. B. hochauflösende Bilder benötigen möglicherweise mehr).
    *   **Händlerszenario / Beispiel:** Wenn Sie erwarten, dass Kunden hochauflösende Fotos hochladen, könnten Sie dies auf 20 MB einstellen. Wenn nur kleine Dokumente benötigt werden, könnten 5 MB ausreichen, um Serverplatz zu sparen.
-   **Erlaubte Dateitypen (kommagetrennt):**

    *   **Was diese Einstellung bewirkt:** Legt fest, welche Dateierweiterungen für den Upload zugelassen sind.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn auf „jpg,png,pdf“ gesetzt:* Nur Dateien mit diesen Erweiterungen können hochgeladen werden. Jeder andere Dateityp wird abgelehnt.
        *   *Wenn leer gelassen:* Alle Dateitypen könnten erlaubt sein (aus Sicherheitsgründen nicht empfohlen).
    *   **Empfohlener Wert:** Nur erwartete Typen einschließen (z. B. `jpg,jpeg,png,gif,pdf,doc,docx,xls,xlsx,txt,zip`). Ausführbare Dateien vermeiden.
    *   **Händlerszenario / Beispiel:** Wenn Sie nur Designdateien benötigen, könnten Sie `ai,eps,svg,psd,pdf,jpg,png` auflisten. Wenn Sie Dokumente benötigen, wären `doc,docx,pdf` angemessen.
-   **Dateiupload für bestimmte Produkte erzwingen (Produkt-IDs):**

    *   **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, Dateiuploads für bestimmte Produkte obligatorisch zu machen. Geben Sie Produkt-IDs durch Kommas getrennt ein.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn Produkt-IDs eingegeben werden:* Wenn ein Kunde versucht, eines dieser Produkte in den Warenkorb zu legen oder zur Kasse zu gehen, ohne eine Datei hochzuladen, wird er dazu aufgefordert.
        *   *Wenn leer gelassen:* Keine Produkte haben obligatorische Dateiuploads.
    *   **Empfohlener Wert:** Nur für Produkte verwenden, bei denen eine Datei für die Bearbeitung der Bestellung absolut unerlässlich ist.
    *   **Händlerszenario / Beispiel:** Für ein Produkt „Individuelles Visitenkarten-Design“ (ID 123) könnten Sie `123` eingeben. Der Kunde kann den Kauf nicht abschließen, ohne sein Logo oder seine Designbeschreibung hochzuladen.
-   **E-Mail-Benachrichtigung an Kunden bei Dateiupload:**

    *   **Was diese Einstellung bewirkt:** Steuert, ob eine E-Mail an den Kunden gesendet wird, wenn er erfolgreich eine Datei hochlädt.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Der Kunde erhält eine Bestätigungs-E-Mail, dass seine Datei empfangen wurde.
        *   *Wenn deaktiviert:* Es wird keine E-Mail-Benachrichtigung an den Kunden gesendet.
    *   **Empfohlener Wert:** JA (verbessert das Kundenvertrauen und bietet Bestätigung)
    *   **Händlerszenario / Beispiel:** Ein Kunde lädt ein Foto für ein personalisiertes Geschenk hoch. Eine E-Mail bestätigt den Upload und versichert ihm, dass seine Datei korrekt empfangen wurde.
-   **E-Mail-Benachrichtigung an Admin bei Dateiupload:**

    *   **Was diese Einstellung bewirkt:** Steuert, ob eine E-Mail an den/die Shop-Administrator(en) gesendet wird, wenn ein Kunde eine Datei hochlädt.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Der Shop-Admin erhält eine E-Mail-Benachrichtigung, die ihn auf neue Dateien aufmerksam macht, die Aufmerksamkeit erfordern.
        *   *Wenn deaktiviert:* Es wird keine E-Mail-Benachrichtigung an den Admin gesendet.
    *   **Empfohlener Wert:** JA (unerlässlich für eine zeitnahe Auftragsabwicklung)
    *   **Händlerszenario / Beispiel:** Ein Kunde lädt eine Designdatei hoch. Der Admin erhält eine E-Mail, die ihn auffordert, die Bestellung zu überprüfen und mit der Bearbeitung des kundenspezifischen Artikels zu beginnen.
-   **Upload-Button in Header/Footer/Spalten anzeigen:**

    *   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Auswahl, wo ein allgemeiner „Dateien hochladen“-Button oder Link in Ihrem Shop erscheint (z. B. im Header, Footer oder in den Seitenleisten).
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn ein Hook ausgewählt ist:* Ein Link oder Button erscheint an dieser Stelle und leitet Kunden zu ihrem Bereich „Meine Dateien“ oder einer allgemeinen Upload-Seite weiter.
        *   *Wenn „Keine“ ausgewählt ist:* Es wird kein allgemeiner Upload-Button außerhalb von Produkt-/Warenkorb-/Bestellseiten angezeigt.
    *   **Empfohlener Wert:** Erwägen Sie `displayHeader` oder `displayFooter` für einen einfachen Zugriff auf „Meine Dateien“, wenn Sie häufige Uploads erwarten.
    *   **Händlerszenario / Beispiel:** Das Platzieren eines „Meine Dateien“-Links im Footer ermöglicht wiederkehrenden Kunden, schnell auf ihre hochgeladenen Dokumente zuzugreifen und diese zu verwalten.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### 2.2.1 Kunden-Dateimanager (Back Office > Module > Kunden-Dateiupload > Kunden-Dateien)

Dieser Bildschirm bietet Ihnen als Shop-Betreiber einen zentralen Ort, um alle von Ihren Kunden hochgeladenen Dateien anzuzeigen und zu verwalten.

-   **Bildschirmname & Menüpfad:** Sie finden dies, indem Sie zu **Module > Modul-Manager** navigieren, „Kunden-Dateiupload“ suchen und auf „Konfigurieren“ klicken. Innerhalb der Modulkonfiguration sollte ein Tab oder Link mit der Bezeichnung „Kunden-Dateien“ oder „Dateien verwalten“ vorhanden sein. Alternativ könnte es direkt unter dem Menü „Module“ als „Kunden-Dateien“ erscheinen.
-   **Verfügbare Aktionen & Einstellungen:**
    *   **Dateilistentabelle:** Zeigt eine Liste aller hochgeladenen Dateien an, einschließlich Details wie:
        *   **Dateiname:** Der Name der hochgeladenen Datei.
        *   **Kunde:** Der Name des Kunden, der die Datei hochgeladen hat.
        *   **Bestell-ID:** Wenn die Datei mit einer bestimmten Bestellung verknüpft ist.
        *   **Produkt:** Wenn die Datei mit einem bestimmten Produkt verknüpft ist.
        *   **Upload-Datum:** Wann die Datei hochgeladen wurde.
        *   **Größe:** Die Größe der Datei.
        *   **Aktionen:** Enthält typischerweise Optionen zum **Herunterladen** der Datei, **Details anzeigen** oder **Löschen** der Datei.
    *   **Filtern und Suchen:** Sie können Dateien normalerweise nach Kunde, Bestell-ID, Produkt oder Datumsbereich filtern, um schnell bestimmte Uploads zu finden.
    *   **Massenaktionen:** Optionen zum Auswählen mehrerer Dateien und zum Ausführen von Aktionen wie dem Massenlöschen.
-   **Auswirkung von Änderungen:**
    *   **Herunterladen einer Datei:** Ruft die hochgeladene Datei des Kunden auf Ihren Computer zur Verarbeitung ab.
    *   **Löschen einer Datei:** Entfernt die Datei dauerhaft von Ihrem Server und aus dem Bereich „Meine Dateien“ des Kunden. Mit Vorsicht verwenden!
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Überprüfen Sie diesen Bereich regelmäßig auf neue Uploads, insbesondere nach Erhalt von Admin-E-Mail-Benachrichtigungen. Laden Sie notwendige Dateien zur Auftragsabwicklung herunter und überprüfen und löschen Sie regelmäßig alte oder unnötige Dateien, um Serverplatz freizugeben.

#### 2.2.2 Integration auf der Bestelldetailseite (Back Office > Bestellungen > Bestellungen > Bestellung anzeigen)

Das Modul integriert sich direkt in Ihre bestehenden PrestaShop-Bestelldetailseiten.

-   **Bildschirmname & Menüpfad:** Wenn Sie eine bestimmte Bestellung in Ihrem Back Office anzeigen (z. B. **Bestellungen > Bestellungen**, dann klicken Sie auf „Anzeigen“ neben einer Bestellung).
-   **Verfügbare Aktionen & Einstellungen:**
    *   Innerhalb der Bestelldetailseite erscheint ein neuer Abschnitt oder Tab, speziell für „Kunden-Dateien“ oder „Hochgeladene Dateien“.
    *   Dieser Abschnitt listet alle Dateien auf, die der Kunde für *diese spezifische Bestellung* hochgeladen hat.
    *   Sie sehen Dateinamen, Upload-Daten und Optionen zum **Herunterladen** jeder Datei.
    *   Es könnte auch eine Option für den Admin geben, eine **Datei hochzuladen** im Namen des Kunden oder für den internen Gebrauch im Zusammenhang mit der Bestellung.
-   **Auswirkung von Änderungen:**
    *   **Dateien von hier herunterladen:** Ermöglicht Ihnen den schnellen Zugriff auf Dateien, die für die aktuell angezeigte Bestellung relevant sind, und optimiert die Auftragsabwicklung.
    *   **Admin-Upload:** Falls verfügbar, ermöglicht es Ihnen, interne Notizen oder Dateien im Zusammenhang mit der Bestellung direkt zur Dateiliste der Bestellung hinzuzufügen.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Wenn Sie eine Bestellung bearbeiten, die Kundendateien erfordert, navigieren Sie zur Bestelldetailseite, suchen Sie den Abschnitt „Kunden-Dateien“ und laden Sie alle notwendigen Dokumente herunter, bevor Sie mit der Produktion oder Ausführung beginnen.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | Modul aktivieren | JA | Hauptschalter für die Modulfunktionalität. |
| | Uploads auf Produktseite erlauben | JA (falls benötigt) | Zeigt Upload-Formular auf Produktseiten an. |
| | Uploads auf Warenkorbseite erlauben | JA (falls benötigt) | Zeigt Upload-Formular auf Warenkorbseite an. |
| | Uploads auf Bestellbestätigungsseite erlauben | JA | Zeigt Upload-Formular nach der Bestellung an. |
| | Uploads im Kundenkonto erlauben | JA | Aktiviert „Meine Dateien“ und Uploads in der Bestellhistorie. |
| | Maximale Dateigröße (MB) | 5-20 MB | Begrenzt die Größe einzelner Dateiuploads. |
| | Erlaubte Dateitypen | `jpg,png,pdf,...` | Beschränkt Dateierweiterungen aus Sicherheits-/Relevanzgründen. |
| | Dateiupload für bestimmte Produkte erzwingen (IDs) | Leer (nach Bedarf verwenden) | Macht den Upload für angegebene Produkte obligatorisch. |
| | E-Mail-Benachrichtigung an Kunden | JA | Sendet E-Mail-Bestätigung an Kunden bei Upload. |
| | E-Mail-Benachrichtigung an Admin | JA | Sendet E-Mail-Benachrichtigung an Admin bei neuem Upload. |
| | Upload-Button in Header/Footer/Spalten anzeigen | `displayFooter` (oder nach Bedarf) | Platziert einen allgemeinen „Dateien hochladen“-Link im ausgewählten Hook. |
| **Kunden-Dateimanager** | Dateiliste | N/A | Alle Kundendateien anzeigen, filtern, herunterladen und löschen. |
| | Massenaktionen | N/A | Aktionen für mehrere ausgewählte Dateien durchführen. |
| **Bestelldetailseite** | Kunden-Dateien-Abschnitt | N/A | Dateien anzeigen und herunterladen, die spezifisch für die aktuelle Bestellung sind. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Kunden können die Upload-Formulare oder den Bereich „Meine Dateien“ nicht sehen.**
A:

-   **Modulstatus überprüfen:** Stellen Sie sicher, dass das Modul unter **Module > Modul-Manager** aktiviert ist.
-   **Konfiguration überprüfen:** Gehen Sie zur Konfigurationsseite des Moduls und vergewissern Sie sich, dass „Modul aktivieren“ auf JA gesetzt ist und dass spezifische Upload-Orte (Produktseite, Warenkorb, Kundenkonto) ebenfalls aktiviert sind.
-   **Cache leeren:** Manchmal kann der PrestaShop-Cache verhindern, dass Änderungen sofort angezeigt werden. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“.
-   **Theme-Kompatibilität:** Wenn Sie ein stark angepasstes Theme verwenden, ist es möglicherweise nicht korrekt mit den Anzeigepunkten des Moduls verbunden. Kontaktieren Sie den MyPresta.eu-Support oder Ihren Webentwickler.

**F2: Kunden erhalten eine Fehlermeldung beim Versuch, Dateien hochzuladen.**
A:

-   **Dateigrößenlimit überprüfen:** Überprüfen Sie die „Maximale Dateigröße (MB)“ in der Modulkonfiguration. Die Datei des Kunden könnte zu groß sein.
-   **Erlaubte Dateitypen überprüfen:** Stellen Sie sicher, dass der Dateityp, den der Kunde hochladen möchte, in der Einstellung „Erlaubte Dateitypen“ aufgeführt ist (z. B. wenn er eine `.zip`-Datei hochlädt, muss `zip` in der Liste sein).
-   **Server-Limits:** Ihr Webhoster hat möglicherweise serverseitige PHP-Upload-Limits (`upload_max_filesize`, `post_max_size`), die niedriger sind als die Einstellung Ihres Moduls. Möglicherweise müssen Sie Ihren Host kontaktieren oder Ihre `php.ini`-Datei anpassen.

**F3: Ich erhalte keine E-Mail-Benachrichtigungen, wenn Kunden Dateien hochladen.**
A:

-   **E-Mail-Benachrichtigungseinstellungen überprüfen:** Stellen Sie in der Modulkonfiguration sicher, dass „E-Mail-Benachrichtigung an Admin bei Dateiupload“ auf JA gesetzt ist.
-   **PrestaShop E-Mail-Einstellungen:** Überprüfen Sie, ob die E-Mail-Einstellungen Ihres PrestaShop-Shops korrekt konfiguriert sind und E-Mails erfolgreich versendet werden (**Erweiterte Einstellungen > E-Mail**). Senden Sie von dort eine Test-E-Mail.
-   **Spam-Ordner:** Überprüfen Sie Ihren Spam- oder Junk-Ordner auf die Benachrichtigungen.
-   **Server-Mailer:** Stellen Sie sicher, dass die Mail-Funktion Ihres Servers korrekt funktioniert.

**F4: Wie übersetze ich den Text des Moduls in andere Sprachen?**
A:

-   Navigieren Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**.
-   Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann „Kunden-Dateiupload“ aus dem Modul-Dropdown.
-   Sie können dann alle sichtbaren Zeichenketten, die vom Modul verwendet werden, übersetzen.

**F5: Wo werden die hochgeladenen Dateien auf meinem Server gespeichert?**
A: Das Modul speichert Dateien typischerweise in einem dedizierten Ordner innerhalb Ihrer PrestaShop-Installation, oft benannt `upload` oder `orderfiles_uploads` innerhalb des Modulverzeichnisses oder eines allgemeinen `upload`-Verzeichnisses. Sie können diese über FTP/SFTP zugreifen, aber es ist immer am besten, sie über die Back Office-Oberfläche zu verwalten, um die Datenbankintegrität zu gewährleisten.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Kunden-Dateiupload“ folgt einer Standard-PrestaShop-Modularchitektur und nutzt MVC-Prinzipien. Es erweitert `Module` für seine Kernfunktionalität und Konfiguration, verwendet `ModuleFrontController` für Front-Office-Interaktionen (Hochladen, Verwalten von Dateien) und `AdminController` für die Back-Office-Verwaltung. Daten werden im Dateisystem gespeichert und potenziell über `ps_configuration` für Einstellungen verknüpft. Das Modul stützt sich stark auf das PrestaShop-Hook-System, um seine Funktionalität in verschiedene Teile des Shops zu integrieren.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

-   `controllers/front/customerfiles.php`
    *   **Klassenname & Elternklasse:** `CustomerfilesCustomerfilesModuleFrontController` erweitert `ModuleFrontController`
    *   **Verantwortlichkeit:** Verwaltet wahrscheinlich die Hauptseite „Meine Dateien“ für Kunden, zeigt eine Liste der hochgeladenen Dateien an und bietet Optionen zur Verwaltung. Es würde Dateien abrufen, die dem angemeldeten Kunden zugeordnet sind.
-   `controllers/front/download.php`
    *   **Klassenname & Elternklasse:** `DownloadCustomerfilesModuleFrontController` erweitert `ModuleFrontController`
    *   **Verantwortlichkeit:** Verwaltet sichere Dateidownloads. Es nimmt eine Datei-ID oder einen Pfad entgegen, überprüft die Kundenberechtigungen (falls zutreffend) und stellt die Datei dem Browser zur Verfügung, oft erzwingt es einen Download.
-   `controllers/front/filesmanager.php`
    *   **Klassenname & Elternklasse:** `FilesmanagerCustomerfilesModuleFrontController` erweitert `ModuleFrontController`
    *   **Verantwortlichkeit:** Könnte eine generische Dateiverwaltungsschnittstelle sein, die potenziell für AJAX-Aufrufe im Zusammenhang mit Dateivorgängen (z. B. Löschen einer Datei aus der Kundenansicht) verwendet wird.
-   `controllers/front/index.php`
    *   **Klassenname & Elternklasse:** `IndexCustomerfilesModuleFrontController` erweitert `ModuleFrontController`
    *   **Verantwortlichkeit:** Oft ein Platzhalter oder ein Weiterleitungs-Controller. In einigen Modulen könnte er als Standard-Einstiegspunkt dienen oder grundlegendes Routing handhaben.
-   `controllers/front/myfiles.php`
    *   **Klassenname & Elternklasse:** `MyfilesCustomerfilesModuleFrontController` erweitert `ModuleFrontController`
    *   **Verantwortlichkeit:** Ähnlich wie `customerfiles.php` verwaltet dies wahrscheinlich den spezifischen Bereich „Meine Dateien“ im Kundenkonto, zeigt die hochgeladenen Dateien an und potenziell ein Upload-Formular.
-   `controllers/front/thumb.php`
    *   **Klassenname & Elternklasse:** `ThumbCustomerfilesModuleFrontController` erweitert `ModuleFrontController`
    *   **Verantwortlichkeit:** Generiert und liefert Miniaturansichten für hochgeladene Bilddateien, um die Leistung und Anzeige auf Dateilisten-Seiten zu verbessern.
-   `controllers/front/upload.php`
    *   **Klassenname & Elternklasse:** `UploadCustomerfilesModuleFrontController` erweitert `ModuleFrontController`
    *   **Verantwortlichkeit:** Der Kern-Upload-Handler. Er empfängt Dateiuploads (über AJAX oder Standard-Formularübermittlung), validiert Dateityp und -größe, verschiebt die Datei in das vorgesehene Verzeichnis und speichert Dateinformationen in der Datenbank.

#### Back-Office-Admin-Controller

-   `controllers/admin/customerFiles.php`
    *   **Klassenname & Elternklasse:** `AdminCustomerFilesController` erweitert `ModuleAdminController`
    *   **Tab-Name und verwaltete Entität:** „Kunden-Dateien“ (oder ähnlich). Dieser Controller verwaltet die Hauptgitteransicht aller vom Kunden hochgeladenen Dateien im Back Office. Er bietet Funktionen zum Auflisten, Filtern, Anzeigen von Details, Herunterladen und Löschen von Dateien.
    *   **Zugehörige Konfigurationsschlüssel:** `PS_SHOP_EMAIL`, `PS_SHOP_NAME` (für E-Mail-Benachrichtigungen), `OF_CEMAIL_CUSTOMER`, `OF_CEMAIL_ATTACH` (wahrscheinlich im Zusammenhang mit E-Mail-Vorlageneinstellungen für Kundenbenachrichtigungen).
-   `controllers/admin/index.php`
    *   **Klassenname & Elternklasse:** `IndexCustomerfilesModuleAdminController` erweitert `ModuleAdminController`
    *   **Tab-Name und verwaltete Entität:** Ähnlich wie `index.php` im Front-Office könnte dies ein Platzhalter oder ein Weiterleitungs-Controller für den Admin-Bereich des Moduls sein.

### 4.3 Kernklassen & Modelle (`classes/`)

Das bereitgestellte Inventar zeigt keine benutzerdefinierten Klassen im Verzeichnis `classes/`. Dies deutet darauf hin, dass das Modul `ObjectModel` direkt innerhalb der Hauptmoduldatei oder der Admin-Controller verwendet, oder es handelt sich um eine ältere Modulstruktur, bei der die Datenverarbeitung eingebettet ist. Wenn Daten in einer benutzerdefinierten Tabelle gespeichert werden, würde die `install()`-Methode des Hauptmoduls deren Schema definieren.

### 4.4 JavaScript-Assets (`views/js/`)

-   `js/jquery.form.js`
    *   **Geltungsbereich:** Wahrscheinlich Front-Office und Back-Office.
    *   **Erklärung:** Ein jQuery-Plugin zum einfachen Senden von Formularen über AJAX, einschließlich Dateiuploads. Es handhabt die Komplexität von `multipart/form-data` und bietet Fortschritts-Callbacks.
-   `js/orders.js`
    *   **Geltungsbereich:** Back-Office (speziell Bestelldetailseiten).
    *   **Erklärung:** Dieses Skript fügt wahrscheinlich Funktionen zur PrestaShop-Bestelldetailseite hinzu, wie das Anzeigen des Abschnitts für hochgeladene Dateien, das Verwalten von Dateidownloads auf Admin-Seite oder potenziell das Ermöglichen von Admins, Dateien zu einer Bestellung hochzuladen.
-   `js/script-customers.js`
    *   **Geltungsbereich:** Front-Office (Kundenkontoseiten).
    *   **Erklärung:** Verwaltet die clientseitige Logik für den Bereich „Meine Dateien“ im Kundenkonto, einschließlich der Anzeige von Dateilisten, der Verwaltung von Löschaktionen und der Initiierung neuer Uploads.
-   `js/script.js`
    *   **Geltungsbereich:** Front-Office (allgemein, Produkt-, Warenkorbseiten) und potenziell Back-Office-Konfiguration.
    *   **Erklärung:** Ein Allzweckskript für das Modul. Es initialisiert wahrscheinlich Upload-Formulare, handhabt die Dateivalidierung (Größe, Typ) vor dem Absenden, zeigt den Upload-Fortschritt an und verwaltet UI-Interaktionen im Zusammenhang mit Dateiuploads an verschiedenen Front-Office-Standorten.

### 4.5 CSS-Stylesheets (`views/css/`)

-   `css/ajaxuploader.css`
    *   **Geltungsbereich:** Front-Office.
    *   **Erklärung:** Stile für die AJAX-basierte Dateiupload-Oberfläche, einschließlich Fortschrittsbalken, Drag-and-Drop-Zonen und Dateieingabeelementen.
-   `css/backoffice.css`
    *   **Geltungsbereich:** Back-Office.
    *   **Erklärung:** Spezifische Stile für die Administrationsseiten des Moduls, wie das „Kunden-Dateimanager“-Raster, Konfigurationsformulare und die Integration in die Bestelldetailseite.
-   `css/orderfiles.css`
    *   **Geltungsbereich:** Front-Office.
    *   **Erklärung:** Allgemeine Stile für die Front-Office-Komponenten des Moduls, einschließlich Dateilisten, Schaltflächen und Nachrichten, die den Kunden angezeigt werden.
-   `css.css`
    *   **Geltungsbereich:** Front-Office.
    *   **Erklärung:** Könnte ein älteres oder allgemeines Stylesheet sein, das potenziell Kernstile für die visuellen Elemente des Moduls enthält.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

-   `displayProductPageUploadFormSmall.tpl`: Rendert ein kompaktes Upload-Formular auf der Produktseite.
-   `filesmanager-orderhistory.tpl`: Zeigt den Dateimanager/Upload-Bereich innerhalb der Bestelldetailseite des Kundenkontos an.
-   `force-redirect.tpl`: Eine Dienstprogrammvorlage, möglicherweise zur Handhabung von Weiterleitungen nach bestimmten Aktionen oder zur Anzeige von Nachrichten vor der Weiterleitung.
-   `header.tpl`: Wird in `displayHeader` eingefügt, typischerweise zum Laden von CSS/JS-Assets oder Meta-Tags, die vom Modul benötigt werden.
-   `my-account-17.tpl`: Rendert den „Meine Dateien“-Link oder Block im Kundenkonto-Dashboard für PrestaShop 1.7.x und neuere Versionen.
-   `my-account.tpl`: Rendert den „Meine Dateien“-Link oder Block im Kundenkonto-Dashboard für ältere PrestaShop-Versionen (1.5.x, 1.6.x).
-   `orderConfirmation.tpl`: Zeigt das Upload-Formular oder die Dateiliste auf der Bestellbestätigungsseite an.
-   `product-files-button.tpl`: Rendert einen Button oder Link auf der Produktseite, der ein Upload-Modal öffnen oder zu einem Upload-Bereich weiterleiten könnte.
-   `product-files.tpl`: Zeigt eine Liste von Dateien an, die einem Produkt zugeordnet sind, oder ein Upload-Formular auf der Produktseite.
-   `shopping-cart-force-files-alert.tpl`: Zeigt eine Warnung im Warenkorb an, wenn obligatorische Dateien für bestimmte Produkte fehlen.
-   `shopping-cart-qty-infos-alert.tpl`: Potenziell im Zusammenhang mit Warnungen für mengenbasierte Dateianforderungen im Warenkorb.
-   `shopping-cart.tpl`: Zeigt das Upload-Formular oder die Dateiliste auf der Warenkorb-Übersichtsseite an.
-   `tab.tpl`: Eine generische Tab-Vorlage, möglicherweise zur Anzeige eines „Dateien“-Tabs auf Produktseiten oder im Kundenkonto.

#### Admin-Templates (`views/templates/admin/`)

-   `admin.tpl`: Allgemeine Admin-Vorlage, möglicherweise für die Hauptkonfigurationsseite des Moduls oder ein Dashboard.
-   `adminOrderDetailUpload.tpl`: Integriert den Dateiupload-/Verwaltungsbereich in die PrestaShop-Bestelldetailseite im Back Office.
-   `boscript.tpl`: Enthält JavaScript, das spezifisch für das Back Office ist, potenziell zur Initialisierung von Formularen oder zur Handhabung von AJAX auf Admin-Seiten.
-   `bulk-delete-files.tpl`: Vorlage für eine Massenlöschbestätigung oder -schnittstelle innerhalb des Admin-Dateimanagers.
-   `comments_cartfiles.tpl`: Zeigt Kommentare oder Notizen zu Dateien an, die für einen bestimmten Warenkorb hochgeladen wurden.
-   `comments_orderfiles.tpl`: Zeigt Kommentare oder Notizen zu Dateien an, die für eine bestimmte Bestellung hochgeladen wurden.
-   `comments_productfiles.tpl`: Zeigt Kommentare oder Notizen zu Dateien an, die für ein bestimmtes Produkt hochgeladen wurden.
-   `customerfilesmanager.tpl`: Die Hauptvorlage für die Gitteransicht des „Kunden-Dateimanagers“ im Back Office.
-   `_configure/helpers/list/list_action_details.tpl`: Vorlage für einen „Details“-Aktionsbutton in einem Listen-Helfer.
-   `_configure/helpers/list/list_content.tpl`: Vorlage für den Hauptinhalt eines Listen-Helfers (z. B. die Zeilen der Dateiliste).
-   `_configure/prestashopbug/helpers/list/*.tpl`: Diese Templates (`list.tpl`, `list_action_delete.tpl`, `list_action_details.tpl`, `list_content.tpl`, `list_footer.tpl`, `list_header.tpl`) deuten auf eine benutzerdefinierte oder überschriebene Listen-Helfer-Implementierung hin, möglicherweise um spezifische Anzeigeanforderungen oder Fehler in älteren PrestaShop-Versionen zu beheben.

#### Front-Office-Templates (`views/templates/front/`)

-   `access-denied.tpl`: Zeigt eine Meldung an, wenn ein Kunde versucht, auf eine Datei oder Seite ohne entsprechende Berechtigungen zuzugreifen.
-   `customerfilesmanager.tpl`: Die Hauptvorlage für die „Meine Dateien“-Seite des Kunden, die seine hochgeladenen Dateien und Verwaltungsoptionen anzeigt.
-   `filesmanager.tpl`: Eine generische Dateimanager-Vorlage, die potenziell für verschiedene Front-Office-Dateilisten- und Upload-Szenarien verwendet wird.
-   `my-files.tpl`: Eine weitere Vorlage für den Bereich „Meine Dateien“ des Kunden, wahrscheinlich ähnlich wie `customerfilesmanager.tpl` oder in Verbindung damit verwendet.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:

    *   Das Modul erstellt wahrscheinlich mindestens eine benutzerdefinierte Tabelle, um Metadaten über die hochgeladenen Dateien zu speichern. Eine typische Tabellenstruktur wäre `ps_orderfiles` (oder ähnlich), die Felder wie:
        *   `id_order_file` (Primärschlüssel)
        *   `id_customer` (Fremdschlüssel zu `ps_customer`)
        *   `id_order` (Fremdschlüssel zu `ps_order`, nullable)
        *   `id_product` (Fremdschlüssel zu `ps_product`, nullable)
        *   `filename` (Originalname der Datei)
        *   `filepath` (Pfad zur gespeicherten Datei auf dem Server)
        *   `filesize` (Größe in Bytes)
        *   `file_extension`
        *   `date_add` (Zeitstempel des Uploads)
        *   `comment` (Optionaler Kommentar vom Kunden oder Admin)
    *   Konfigurationseinstellungen werden in `ps_configuration` mit Schlüsseln wie `OF_CEMAIL_CUSTOMER`, `OF_CEMAIL_ATTACH` und anderen modulspezifischen Einstellungen gespeichert.
-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | CSS, JavaScript und potenziell Meta-Tags für das Modul injizieren. |
| `displayProductAdditionalInfo` (oder ähnlicher Produktseiten-Hook) | Auf der Produktseite, typischerweise unter der Produktbeschreibung oder dem „In den Warenkorb“-Button. | Das produktspezifische Upload-Formular oder den Button anzeigen. |
| `displayShoppingCartFooter` (oder ähnlicher Warenkorbseiten-Hook) | Auf der Warenkorb-Übersichtsseite. | Das warenkorbweite Upload-Formular oder die Dateiliste anzeigen. |
| `displayOrderConfirmation` | Auf der Bestellbestätigungsseite nach einem erfolgreichen Kauf. | Das Upload-Formular nach dem Kauf anzeigen. |
| `displayCustomerAccount` | Im „Mein Konto“-Dashboard des Kunden. | Einen Link oder Block zum Bereich „Meine Dateien“ hinzufügen. |
| `displayMyAccountBlock` (PrestaShop 1.6.x) | Im „Mein Konto“-Dashboard des Kunden. | Einen Link oder Block zum Bereich „Meine Dateien“ hinzufügen. |
| `displayRightColumn` / `displayLeftColumn` | In den Seitenleisten des Shops. | Einen allgemeinen „Dateien hochladen“-Button/Link anzeigen, falls konfiguriert. |
| `displayFooter` | Im Footer jeder Seite. | Einen allgemeinen „Dateien hochladen“-Button/Link anzeigen, falls konfiguriert. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | Potenziell verwendet, um hochgeladene Dateien mit der neu erstellten Bestell-ID zu verknüpfen oder Admin-Benachrichtigungen auszulösen. |
| `actionProductUpdate` / `actionProductAdd` | Wenn ein Produkt aktualisiert oder hinzugefügt wird. | Könnte verwendet werden, um produktspezifische Dateianforderungen zu verwalten oder zugehörige Dateien zu bereinigen. |
| `actionCustomerAccountAdd` | Wenn ein neues Kundenkonto erstellt wird. | (Weniger wahrscheinlich für dieses Modul, aber für die Erstkonfiguration möglich). |
| `actionAdminOrdersView` | Wenn ein Administrator eine Bestellung im Back Office anzeigt. | Den Dateiverwaltungsbereich des Moduls in die Bestelldetailseite injizieren. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul „Kunden-Dateiupload“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, sicherzustellen, dass Ihr Modul perfekt funktioniert und Ihnen hilft, das Potenzial Ihres Shops zu maximieren.
