---
title: "Geschenkkarten – Gutscheincodes verkaufen – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Geschenkkarten – Gutscheincodes verkaufen“ von MyPresta.eu."
sidebar:
  label: "Geschenkkarten – Gutscheincodes verkaufen – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Gift Cards - sell voucher codes auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/gift-cards-sell-voucher-codes.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/gift-cards-sell-voucher-codes/)
>
> ---


# Geschenkkarten – Gutscheincodes verkaufen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind erforderlich, die typischerweise in den meisten modernen Webhosting-Umgebungen verfügbar sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Das Modul „Geschenkkarten – Gutscheincodes verkaufen“ bietet mehrere Konfigurationsbildschirme, um Ihre Geschenkkarten effektiv zu verwalten.

### 2.1 Hauptkonfigurationsseite des Moduls (Back Office > Module > Modul-Manager > Geschenkkarten – Gutscheincodes verkaufen konfigurieren)

Dies ist der primäre Konfigurationsbildschirm für das Modul, auf dem Sie das allgemeine Verhalten einstellen und auf andere Verwaltungsbereiche zugreifen.

- **Was diese Einstellung bewirkt:** Dieser Abschnitt enthält typischerweise globale Einstellungen für das Modul, wie das Aktivieren/Deaktivieren von Funktionen, das Verknüpfen mit anderen Verwaltungsbildschirmen und möglicherweise das Festlegen von Standardverhalten für Geschenkkarten.
- **Auswirkung einer Änderung dieser Einstellung:** Änderungen hier wirken sich darauf aus, wie Geschenkkarten in Ihrem gesamten Shop angezeigt, gekauft und verwaltet werden.
- **Empfohlener Wert:** Überprüfen Sie jede Option sorgfältig. Aktivieren Sie im Allgemeinen Funktionen, die Sie verwenden möchten, und folgen Sie den Standardempfehlungen des Moduls, es sei denn, Sie haben einen bestimmten Grund, sie zu ändern.
- **Händlerszenario / Beispiel:** Sie könnten hier eine Einstellung finden, um einen dedizierten „Geschenkkarten“-Link im Footer Ihres Shops zu aktivieren. Dies würde es Kunden erleichtern, Geschenkkarten zu finden und zu kaufen.

### 2.2 Verwaltung von Geschenkkartengruppen (Back Office > Geschenkkarten > Geschenkkartengruppen)

Dieser Bildschirm ermöglicht es Ihnen, verschiedene Kategorien oder Gruppen für Ihre Geschenkkarten zu definieren. Stellen Sie sich diese als Vorlagen oder Arten von Geschenkkarten vor, die Sie anbieten möchten.

- **Bildschirmname & Menüpfad:** **Back Office > Geschenkkarten > Geschenkkartengruppen**
- **Verfügbare Aktionen & Einstellungen:**
  - **Auflistungstabelle:** Zeigt alle vorhandenen Geschenkkartengruppen an. Sie sehen Spalten wie Gruppenname, Wert, Status (aktiv/inaktiv) und Aktionen (Bearbeiten, Löschen).
  - **Neue Geschenkkartengruppe hinzufügen:** Klicken Sie auf diese Schaltfläche, um eine neue Art von Geschenkkarte zu erstellen.
    - **Gruppenname:** (z.B. „Geburtstagsgeschenkkarte“, „Weihnachtsgutschein“, „Geschenkkarte für jeden Anlass“)
      - *Was diese Einstellung bewirkt:* Dies ist der interne Name für Ihre Geschenkkartengruppe. Er hilft Ihnen, verschiedene Arten von Geschenkkarten im Back Office zu organisieren und zu identifizieren.
      - *Auswirkung einer Änderung dieser Einstellung:* Betrifft nur Ihre Back-Office-Organisation.
      - *Empfohlener Wert:* Beschreibend und klar.
    - **Wert:** (z.B. „25.00“, „50.00“, „100.00“)
      - *Was diese Einstellung bewirkt:* Dies definiert den Geldwert der Geschenkkarte in dieser Gruppe.
      - *Auswirkung einer Änderung dieser Einstellung:* Dies ist der Betrag, den Kunden bezahlen und Empfänger als Guthaben erhalten.
      - *Empfohlener Wert:* Gängige, ansprechende Stückelungen für Ihren Zielmarkt.
    - **Aktiv:** (Ja/Nein-Schalter)
      - *Was diese Einstellung bewirkt:* Steuert, ob Geschenkkarten aus dieser Gruppe in Ihrem Shop zum Kauf verfügbar sind.
      - *Auswirkung einer Änderung dieser Einstellung:*
        - *Wenn aktiviert:* Kunden können Geschenkkarten dieses Wertes sehen und kaufen.
        - *Wenn deaktiviert:* Geschenkkarten dieses Wertes sind im Front Office ausgeblendet und können nicht gekauft werden.
      - *Empfohlener Wert:* JA für aktive Geschenkkarten, die Sie verkaufen möchten.
    - **Weitere Felder:** Können Optionen für Gültigkeitsdauer, Mindestkauf für die Einlösung oder spezifische Produktbeschränkungen enthalten.
      - *Was diese Einstellung bewirkt:* Diese Felder ermöglichen es Ihnen, die Bedingungen, unter denen die Geschenkkarte verwendet werden kann, zu verfeinern.
      - *Auswirkung einer Änderung dieser Einstellung:* Wirkt sich direkt auf die Verwendbarkeit und die Einschränkungen der Geschenkkarte für den Empfänger aus.
      - *Empfohlener Wert:* Gemäß Ihrer Geschäftsrichtlinie festlegen (z.B. 1 Jahr Gültigkeit, kein Mindestkauf).
- **Auswirkung von Änderungen:** Das Erstellen neuer Gruppen ermöglicht es Ihnen, verschiedene Geschenkkartenwerte anzubieten. Das Bearbeiten von Gruppen ändert den Wert oder die Verfügbarkeit bestehender Geschenkkartentypen. Das Löschen einer Gruppe entfernt die Option, diesen spezifischen Geschenkkartentyp zu kaufen.
- **Empfohlener Arbeitsablauf für die tägliche Shop-Verwaltung:**
  1. Beginnen Sie mit der Erstellung einiger gängiger Geschenkkartenwerte (z.B. 25 €, 50 €, 100 €).
  2. Wenn Ihr Geschäft wächst oder für saisonale Aktionen, fügen Sie neue Gruppen mit unterschiedlichen Werten oder spezifischen Gültigkeitsdauern hinzu.
  3. Deaktivieren Sie Gruppen, die Sie nicht mehr verkaufen möchten, anstatt sie zu löschen, um historische Daten zu erhalten.

### 2.3 Geschenkkarten-Historie (Back Office > Geschenkkarten > Geschenkkarten-Historie)

Dieser Bildschirm bietet einen umfassenden Überblick über alle gekauften Geschenkkarten und deren aktuellen Status.

- **Bildschirmname & Menüpfad:** **Back Office > Geschenkkarten > Geschenkkarten-Historie**
- **Verfügbare Aktionen & Einstellungen:**
  - **Auflistungstabelle:** Zeigt eine Liste aller generierten Geschenkgutscheine an. Die Spalten umfassen typischerweise:
    - **Gutscheincode:** Der einzigartige Code, der der Geschenkkarte zugeordnet ist.
    - **Ursprünglicher Wert:** Der ursprüngliche Wert der Geschenkkarte.
    - **Aktueller Saldo:** Der verbleibende Saldo auf der Geschenkkarte (falls teilweise verwendet).
    - **Empfänger-E-Mail:** Die E-Mail-Adresse der Person, die die Geschenkkarte erhalten hat.
    - **Absendername:** Der Name der Person, die die Geschenkkarte gekauft hat.
    - **Bestell-ID:** Die ID der Bestellung, über die die Geschenkkarte gekauft wurde.
    - **Status:** (z.B. „Ausstehend“, „Aktiv“, „Verwendet“, „Abgelaufen“).
    - **Aktionen:** Kann Optionen zum Anzeigen von Bestelldetails, zum erneuten Senden der Geschenkkarten-E-Mail oder zum manuellen Anpassen des Saldos enthalten (mit Vorsicht verwenden).
  - **Suchen und Filtern:** Tools zum Auffinden spezifischer Geschenkkarten nach Code, E-Mail, Bestell-ID oder Status.
- **Auswirkung von Änderungen:** Dieser Bildschirm dient hauptsächlich der Überwachung und Verwaltung. Sie können die Nutzung von Geschenkkarten verfolgen, ausstehende Salden identifizieren und Kunden bei ihren Geschenkkartenanfragen unterstützen.
- **Empfohlener Arbeitsablauf für die tägliche Shop-Verwaltung:**
  1. Überprüfen Sie diesen Abschnitt regelmäßig, um Geschenkkartenverkäufe und -einlösungen zu überwachen.
  2. Verwenden Sie die Suchfunktion, um schnell eine Geschenkkarte zu finden, wenn ein Kunde eine Frage zu deren Saldo oder Status hat.
  3. Wenn ein Kunde meldet, dass er seine Geschenkkarten-E-Mail nicht erhalten hat, können Sie den Status überprüfen und sie gegebenenfalls von hier aus erneut senden.

### 2.4 Verwaltung von Geschenkkarten-Gutscheinen (Back Office > Geschenkkarten > Geschenkkarten-Gutscheine)

Dieser Bildschirm dient der Verwaltung der einzelnen Gutscheincodes, die für jeden Geschenkkartenkauf generiert werden.

- **Bildschirmname & Menüpfad:** **Back Office > Geschenkkarten > Geschenkkarten-Gutscheine**
- **Verfügbare Aktionen & Einstellungen:**
  - **Auflistungstabelle:** Zeigt einzelne Geschenkgutscheincodes an. Die Spalten könnten umfassen:
    - **Gutscheincode:** Der einzigartige Code.
    - **Zugehörige Geschenkkartengruppe:** Zu welchem Geschenkkartentyp dieser Gutschein gehört.
    - **Wert:** Der Wert dieses spezifischen Gutscheins.
    - **Kunde:** Der dem Gutschein zugeordnete Kunde (entweder Absender oder Empfänger).
    - **Datum hinzugefügt/generiert:** Wann der Gutschein erstellt wurde.
    - **Status:** (z.B. „Aktiv“, „Verwendet“, „Abgelaufen“).
    - **Aktionen:** Optionen zum Anzeigen von Details, Bearbeiten (z.B. Status ändern, Gültigkeit verlängern) oder Löschen (mit äußerster Vorsicht verwenden, da dies den Gutschein entfernt).
- **Auswirkung von Änderungen:** Dieser Bildschirm ermöglicht eine detaillierte Kontrolle über einzelne Geschenkkartengutscheine. Sie können Gutscheine manuell aktivieren/deaktivieren, ihre Gültigkeit verlängern oder bei Bedarf sogar ihren Wert ändern (z.B. bei Kundendienstproblemen).
- **Empfohlener Arbeitsablauf für die tägliche Shop-Verwaltung:**
  1. Verwenden Sie diesen Bildschirm für erweiterte Verwaltungsaufgaben, wie z.B. das manuelle Ausstellen einer Geschenkkarte als Geste des guten Willens oder die Lösung spezifischer Kundenprobleme im Zusammenhang mit einem Gutschein.
  2. Seien Sie vorsichtig beim Bearbeiten oder Löschen von Gutscheinen, da dies das Kundenguthaben direkt beeinflusst.
  3. Dieser Bildschirm bietet eine detaillierte Ansicht des Lebenszyklus jedes Gutscheins.

### 2.5 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | *Allgemeine Einstellungen* | Variiert | Globales Modulverhalten, Anzeigeoptionen und Links zu anderen Verwaltungsbereichen. |
| **Geschenkkartengruppen** | **Gruppenname** | Beschreibend | Interner Name für den Geschenkkartentyp. |
|  | **Wert** | Gängige Stückelungen (z.B. 25 €, 50 €) | Geldwert der Geschenkkarte. |
|  | **Aktiv** | JA | Steuert die Sichtbarkeit und Kaufbarkeit des Geschenkkartentyps. |
|  | *Gültigkeitsdauer* | Gemäß Richtlinie | Definiert, wie lange die Geschenkkarte nach dem Kauf gültig ist. |
|  | *Min. Kauf für Einlösung* | Gemäß Richtlinie | Legt einen Mindestbestellwert fest, damit die Geschenkkarte verwendet werden kann. |
| **Geschenkkarten-Historie** | *Gutscheincode* | N/A | Eindeutige Kennung für jede gekaufte Geschenkkarte. |
|  | *Aktueller Saldo* | N/A | Verbleibendes Guthaben auf der Geschenkkarte. |
|  | *Status* | N/A | Verfolgt den Lebenszyklus der Geschenkkarte (Aktiv, Verwendet, Abgelaufen). |
| **Geschenkkarten-Gutscheine** | *Gutscheincode* | N/A | Eindeutige Kennung für jeden generierten Gutschein. |
|  | *Status* | N/A | Verfolgt den Zustand des einzelnen Gutscheins. |
|  | *Bearbeiten/Löschen-Aktionen* | Mit Vorsicht verwenden | Ermöglicht die manuelle Änderung oder Entfernung einzelner Gutscheine. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Kunden können die Geschenkkarten in meinem Shop nicht finden.**

- **A:** Stellen Sie zunächst sicher, dass die von Ihnen erstellten „Geschenkkartengruppen“ im Back Office unter **Geschenkkarten > Geschenkkartengruppen** als „Aktiv“ markiert sind. Überprüfen Sie zweitens die Hauptkonfigurationsseite Ihres Moduls (Module > Modul-Manager > Geschenkkarten – Gutscheincodes verkaufen konfigurieren) auf Optionen zur Anzeige von Links im Header, Footer oder in Spalten. Wenn Ihr Theme eine benutzerdefinierte Menüverwaltung hat, müssen Sie möglicherweise manuell einen Link zur Geschenkkartenseite hinzufügen (normalerweise über eine sprechende URL wie `ihrshop.de/geschenke` zugänglich).

**F2: Ein Kunde hat eine Geschenkkarte gekauft, aber der Empfänger hat die E-Mail nicht erhalten.**

- **A:** Gehen Sie in Ihrem Back Office zu **Geschenkkarten > Geschenkkarten-Historie**. Suchen Sie die spezifische Geschenkkarte nach Bestell-ID oder Absender-/Empfänger-E-Mail. Überprüfen Sie ihren Status – sie sollte „Aktiv“ oder „Ausstehend“ sein, wenn sie noch nicht verwendet wurde. Suchen Sie nach einer Option zum „E-Mail erneut senden“ für diesen spezifischen Gutschein. Raten Sie dem Kunden außerdem, seinen Spam-/Junk-Ordner zu überprüfen. Stellen Sie sicher, dass die E-Mail-Einstellungen Ihres Shops (Erweiterte Parameter > E-Mail) korrekt konfiguriert sind und Ihr Server E-Mails zuverlässig senden kann.

**F3: Der Geschenkkartenrabatt wird beim Checkout nicht angewendet.**

- **A:** Überprüfen Sie Folgendes:
  1. **Code-Eingabe:** Stellen Sie sicher, dass der Kunde den korrekten, vollständigen Geschenkkartencode ohne Tippfehler oder zusätzliche Leerzeichen eingibt.
  2. **Gültigkeit:** Überprüfen Sie den Status der Geschenkkarte unter **Geschenkkarten > Geschenkkarten-Historie** oder **Geschenkkarten > Geschenkkarten-Gutscheine**. Ist sie „Aktiv“? Ist sie abgelaufen? Ist noch ein Restguthaben vorhanden?
  3. **Mindestkauf:** Hat die Geschenkkarte eine Mindestkaufanforderung, die der aktuelle Warenkorbwert nicht erfüllt?
  4. **Produkteinschränkungen:** Gibt es Produktkategorien oder spezifische Produkte, die von der Geschenkkartennutzung ausgeschlossen sind? (Dies würde in den Einstellungen der Geschenkkartengruppe konfiguriert).
  5. **Cache:** Manchmal kann das Leeren Ihres PrestaShop-Caches (Erweiterte Parameter > Leistung) Anzeige- oder Funktionalitätsprobleme beheben.

**F4: Kann ich die E-Mail-Vorlage für die Geschenkkarten anpassen?**

- **A:** Ja, das Modul enthält einen E-Mail-Vorlagen-Manager. Sie sollten Optionen innerhalb der Modulkonfiguration oder eines dedizierten Abschnitts (z.B. unter **Geschenkkarten > E-Mail-Vorlagen**) finden, um den Inhalt und das Erscheinungsbild der an Geschenkkartenempfänger gesendeten E-Mail zu bearbeiten. Dies ermöglicht es Ihnen, die E-Mail zu branden und spezifische Anweisungen oder Nachrichten einzufügen.

**F5: Was passiert, wenn der Bestellwert eines Kunden geringer ist als der Geschenkkartenwert?**

- **A:** Das Modul ist darauf ausgelegt, dies zu handhaben. Wenn der Bestellwert geringer ist als der Geschenkkartenwert, sollte das Restguthaben auf der Geschenkkarte verbleiben, sodass der Empfänger es für zukünftige Einkäufe verwenden kann, bis das Guthaben aufgebraucht ist oder die Karte abläuft. Sie können das Restguthaben im Abschnitt **Geschenkkarten > Geschenkkarten-Historie** überprüfen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Geschenkkarten – Gutscheincodes verkaufen“ folgt einem Standard-PrestaShop-MVC-Muster, obwohl es keine expliziten benutzerdefinierten `ObjectModel`-Klassen im Verzeichnis `classes/` definiert. Stattdessen nutzt es die Kernfunktionalität von PrestaShops `CartRule` (Gutschein) und erweitert die Admin-Funktionen durch dedizierte `AdminController`s zur Verwaltung von Geschenkkartengruppen, Historie und einzelnen Gutscheinen. Die Front-Office-Interaktion wird von `ModuleFrontController`s übernommen, hauptsächlich zur Anzeige von Geschenkkarten und zur Verwaltung von Benutzerkonten. Das Modul stützt sich stark auf das PrestaShop-Konfigurationssystem (`Configuration::get()`) für seine Einstellungen und integriert sich in verschiedene Hooks, um Inhalte anzuzeigen und Bestellprozesse zu verwalten.

### 4.2 Controller (`controllers/`)

#### Front-Office Controller

- `controllers/front/gifts.php`
  - **Klassenname & Elternklasse**: `GiftcertificateGiftsModuleFrontController` erweitert `ModuleFrontController`
  - **Verantwortlichkeit**: Dieser Controller ist für die Anzeige der Hauptgeschenkkartenseite im Front Office verantwortlich. Er ruft verfügbare Geschenkkartengruppen ab und rendert sie mithilfe der `gifts.tpl`-Vorlage, sodass Kunden Geschenkkarten zum Kauf durchsuchen und auswählen können.
- `controllers/front/index.php`
  - **Klassenname & Elternklasse**: `GiftcertificateIndexModuleFrontController` erweitert `ModuleFrontController`
  - **Verantwortlichkeit**: Dies ist ein Platzhalter- oder Fallback-Controller, der oft verwendet wird, um Basis-Modul-Routing umzuleiten oder zu handhaben. In vielen Fällen könnte er einfach zum `gifts.php`-Controller umleiten oder als Basis für andere Front-Office-Aktionen dienen.

#### Back-Office Admin Controller

- `controllers/admin/AdminGiftcertificateGroupController.php`
  - **Tab-Name und verwaltete Entität**: „Geschenkkartengruppen“ (unter dem Hauptmenü „Geschenkkarten“). Verwaltet `gift_group`-Entitäten.
  - **Verantwortlichkeit**: Dieser Controller bietet die Schnittstelle zum Erstellen, Bearbeiten und Löschen von Geschenkkartengruppen. Er verarbeitet die Formularübermittlung zur Definition von Geschenkkartenwerten, Namen und anderen gruppenspezifischen Einstellungen. Er verwendet PrestaShops `HelperList` und `HelperForm` zum Rendern des Rasters und der Formulare.
- `controllers/admin/AdminGiftcertificateHistoryController.php`
  - **Tab-Name und verwaltete Entität**: „Geschenkkarten-Historie“ (unter dem Hauptmenü „Geschenkkarten“). Verwaltet `giftcertlist`-Entitäten.
  - **Verantwortlichkeit**: Dieser Controller zeigt eine historische Übersicht aller gekauften Geschenkkarten an. Er listet Gutscheincodes, Werte, Empfänger und Status auf. Er ermöglicht Administratoren, die Geschenkkartennutzung zu verfolgen und möglicherweise E-Mails erneut zu senden. Er verwendet PrestaShops `HelperList` für die Rasteransicht und interagiert mit Konfigurationsschlüsseln wie `mowner`, `PS_SHOP_EMAIL`, `PS_SHOP_NAME` für E-Mail-bezogene Aktionen.
- `controllers/admin/AdminGiftcertificateVoucherController.php`
  - **Tab-Name und verwaltete Entität**: „Geschenkkarten-Gutscheine“ (unter dem Hauptmenü „Geschenkkarten“). Verwaltet `gift_voucher`-Entitäten.
  - **Verantwortlichkeit**: Dieser Controller bietet eine detaillierte Verwaltung für einzelne Geschenkkarten-Gutscheincodes. Er ermöglicht Administratoren, spezifische Gutscheine anzuzeigen, zu bearbeiten (z.B. Status ändern, Gültigkeit verlängern) oder zu löschen. Er verwendet PrestaShops `HelperList` und `HelperForm` zur Verwaltung einzelner Gutschein-Datensätze.
- `controllers/admin/index.php`
  - **Tab-Name und verwaltete Entität**: N/A
  - **Verantwortlichkeit**: Diese Datei dient typischerweise als Sicherheitsmaßnahme, um direkte Verzeichnisauflistungen oder Zugriffe zu verhindern. Sie enthält normalerweise ein einfaches `header('Location: ../../../index.php'); exit;` oder Ähnliches, um zum Haupt-PrestaShop-Admin umzuleiten.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist keine benutzerdefinierten Klassen im Verzeichnis `classes/` auf. Dies deutet darauf hin, dass das Modul entweder:

1. Datenbanktabellen direkt mit `Db::getInstance()` ohne `ObjectModel`s manipuliert.
2. Sich auf PrestaShops Kernklasse `CartRule` (Gutschein) für die eigentliche Gutscheinlogik verlässt und seine eigenen Admin-Controller den „Geschenkkarten“-Aspekt als Wrapper um die Erstellung und Verwaltung von `CartRule`s verwalten.
3. Die Hauptmoduldatei (`ajax_giftcertificate.php`) oder ihre enthaltenen Bibliotheken die Kernlogik und Datenverarbeitung enthalten.

### 4.4 JavaScript-Assets (`views/js/`)

- `giftcertificate/js/script.js`
  - **Geltungsbereich**: Wahrscheinlich Front-Office oder allgemeine Modulfunktionalität.
  - **Details**: Enthält allgemeines JavaScript für das Modul, das möglicherweise AJAX-Anfragen zum Hinzufügen von Geschenkkarten zum Warenkorb, dynamische Aktualisierungen auf der Geschenkkartenseite oder Front-End-Formularvalidierungen verarbeitet.
- `giftcertificate/lib/emailTemplatesManager/js/emailTemplatesManager.js`
  - **Geltungsbereich**: Back-Office (Admin).
  - **Details**: Verwaltet die Funktionalität zum Bearbeiten und Erstellen von E-Mail-Vorlagen innerhalb der Modulkonfiguration. Dies würde die Verarbeitung von Formularübermittlungen, AJAX-Aufrufen zum Speichern von Vorlagen und möglicherweise Rich-Text-Editor-Integrationen umfassen.
- `giftcertificate/lib/pdfTemplatesManager/js/pdfTemplatesManager.js`
  - **Geltungsbereich**: Back-Office (Admin).
  - **Details**: Ähnlich dem E-Mail-Vorlagen-Manager, jedoch für PDF-Vorlagen, die wahrscheinlich zum Generieren druckbarer Geschenkkarten verwendet werden. Verarbeitet Formularinteraktionen, das Speichern von PDF-Vorlagendesigns und die Vorschaufunktion.
- `giftcertificate/lib/searchTool/views/js/autocomplete.js`
  - **Geltungsbereich**: Back-Office (Admin).
  - **Details**: Bietet Autocomplete-Funktionalität für Suchfelder innerhalb der Admin-Controller, z.B. zum Suchen nach Kunden oder Produkten beim Erstellen/Bearbeiten von Geschenkkarten oder Gutscheinen.
- `giftcertificate/lib/voucherengine/script.js`
  - **Geltungsbereich**: Wahrscheinlich Front-Office oder allgemeine Modulfunktionalität.
  - **Details**: Enthält JavaScript, das spezifisch für die Gutscheingenerierungs- und Einlösungslogik ist, und möglicherweise mit dem Warenkorb oder dem Checkout-Prozess interagiert, um Geschenkkartenrabatte anzuwenden.

### 4.5 CSS-Stylesheets (`views/css/`)

- `giftcertificate/css.css`
  - **Geltungsbereich**: Allgemein, könnte Front-Office oder Back-Office sein.
  - **Details**: Enthält Kern-Styling für die Elemente des Moduls, möglicherweise einschließlich allgemeinem Layout, Schaltflächenstilen oder gemeinsamen Komponenten.
- `giftcertificate/lib/emailTemplatesManager/css/emailTemplatesManager.css`
  - **Geltungsbereich**: Back-Office (Admin).
  - **Details**: Stile für die E-Mail-Vorlagenverwaltungsoberfläche, um ein konsistentes Erscheinungsbild innerhalb des PrestaShop Back Office zu gewährleisten.
- `giftcertificate/lib/pdfTemplatesManager/css/pdfTemplatesManager.css`
  - **Geltungsbereich**: Back-Office (Admin).
  - **Details**: Stile für die PDF-Vorlagenverwaltungsoberfläche, ähnlich dem E-Mail-Vorlagen-Manager.
- `giftcertificate/lib/searchTool/views/css/autocomplete.css`
  - **Geltungsbereich**: Back-Office (Admin).
  - **Details**: Styling für die Autocomplete-Suchergebnisse und Eingabefelder.
- `giftcertificate/lib/voucherengine/ps16.css`
  - **Geltungsbereich**: Front-Office (speziell für PrestaShop 1.6 Themes).
  - **Details**: Enthält Kompatibilitätsstile für PrestaShop 1.6 Themes, die potenzielle Layout- oder Elementunterschiede ansprechen, um die korrekte Anzeige von Geschenkkartenkomponenten zu gewährleisten.
- `giftcertificate/views/css/giftcertificate.css`
  - **Geltungsbereich**: Front-Office (kundenorientiert).
  - **Details**: Primäres Stylesheet für die Front-Office-Anzeige von Geschenkkarten, einschließlich der dedizierten Geschenkkartenseite, Produktseitenelementen und möglicherweise Styling für den Bereich „Mein Konto“. Entwickler können diese Klassen in der `custom.css` ihres Themes oder im Child-Theme überschreiben.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

#### Hook-Vorlagen (`views/templates/hook/`)

- `giftcertificate/views/templates/hook/displayAdminOrder.tpl`
  - **Hook**: `displayAdminOrder`
  - **Ausgabe**: Rendert Informationen zu Geschenkkarten auf der PrestaShop-Bestelldetailseite im Back Office. Dies könnte anzeigen, welche Geschenkkarten in der Bestellung gekauft oder zur Bezahlung der Bestellung verwendet wurden.
- `giftcertificate/views/templates/hook/displayMyAccountBlock.tpl`
  - **Hook**: `displayMyAccountBlock` (PrestaShop 1.6)
  - **Ausgabe**: Fügt einen Link oder Block zur Seite „Mein Konto“ des Kunden hinzu, der ihn zu seinen gekauften Geschenkkarten oder seiner Geschenkkarten-Historie führt.
- `giftcertificate/views/templates/hook/my-account-16.tpl`
  - **Hook**: `displayCustomerAccount` (PrestaShop 1.6)
  - **Ausgabe**: Spezifische Vorlage zum Hinzufügen eines Links zur Seite „Mein Konto“ für PrestaShop 1.6 Themes.
- `giftcertificate/views/templates/hook/my-account-17.tpl`
  - **Hook**: `displayCustomerAccount` (PrestaShop 1.7+)
  - **Ausgabe**: Spezifische Vorlage zum Hinzufügen eines Links zur Seite „Mein Konto“ für PrestaShop 1.7 und neuere Themes.
- `giftcertificate/views/templates/hook/my-account.tpl`
  - **Hook**: `displayCustomerAccount` (Allgemein/Fallback)
  - **Ausgabe**: Eine allgemeine „Mein Konto“-Linkvorlage, die möglicherweise als Fallback oder für ältere Versionen verwendet wird.

#### Admin-Vorlagen (`views/templates/admin/`)

- `giftcertificate/views/templates/admin/admin.tpl`
  - **Geltungsbereich**: Allgemeine Admin-Konfiguration.
  - **Ausgabe**: Wahrscheinlich das Hauptkonfigurationsformular für das Modul, gerendert über `getContent()` in der Hauptmoduldatei. Es könnte Registerkarten oder Abschnitte für verschiedene Einstellungen enthalten.
- `giftcertificate/views/templates/admin/adminOrder.tpl`
  - **Geltungsbereich**: Admin-Bestellansicht.
  - **Ausgabe**: Ähnlich wie `displayAdminOrder.tpl`, aber möglicherweise für eine stärker integrierte Ansicht innerhalb einer benutzerdefinierten Admin-Bestellseite, falls das Modul diese überschreibt oder erweitert.
- `giftcertificate/views/templates/admin/list/list_action_email.tpl`
  - **Geltungsbereich**: Admin-Listenansichten (z.B. Geschenkkarten-Historie).
  - **Ausgabe**: Eine spezifische Aktionsschaltfläche oder ein Link zum Senden von E-Mails, typischerweise in der Aktionsspalte einer `HelperList`-Tabelle zu finden, die es Administratoren ermöglicht, Geschenkkarten-E-Mails erneut zu senden.

#### Front-Office-Vorlagen (`views/templates/front/`)

- `giftcertificate/views/templates/front/gifts.tpl`
  - **Geltungsbereich**: Dedizierte Front-Office-Seite.
  - **Ausgabe**: Die Hauptvorlage zur Anzeige der Liste der verfügbaren Geschenkkarten für Kunden, gerendert von `GiftcertificateGiftsModuleFrontController`.

#### Bibliotheksvorlagen (`lib/`)

- `giftcertificate/lib/emailTemplatesManager/views/*.tpl`
  - **Geltungsbereich**: Back-Office (Admin).
  - **Ausgabe**: Vorlagen für die E-Mail-Vorlagenverwaltungsoberfläche (z.B. `buttonManager.tpl`, `createTemplateForm.tpl`, `editTemplateForm.tpl`, `mainForm.tpl`, `selectInput.tpl`).
- `giftcertificate/lib/helpers/views/orderStates.tpl`
  - **Geltungsbereich**: Back-Office (Admin).
  - **Ausgabe**: Eine Hilfsvorlage, wahrscheinlich zum Anzeigen oder Auswählen von Bestellstatus innerhalb von Modulkonfigurationen oder Formularen.
- `giftcertificate/lib/pdfTemplatesManager/views/*.tpl`
  - **Geltungsbereich**: Back-Office (Admin).
  - **Ausgabe**: Vorlagen für die PDF-Vorlagenverwaltungsoberfläche (z.B. `buttonManager.tpl`, `createTemplateForm.tpl`, `editTemplateForm.tpl`, `mainForm.tpl`, `selectInput.tpl`).
- `giftcertificate/lib/searchTool/views/scripts.tpl`
  - **Geltungsbereich**: Back-Office (Admin).
  - **Ausgabe**: Enthält JavaScript- oder Smarty-Logik im Zusammenhang mit dem Suchwerkzeug, möglicherweise einschließlich Initialisierungsskripten für die Autovervollständigung.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Das Modul erstellt wahrscheinlich benutzerdefinierte Tabellen zur Verwaltung seiner Daten, obwohl keine expliziten `classes/` mit `ObjectModel`-Definitionen gefunden wurden. Basierend auf den Admin-Controllern sind die folgenden Tabellen impliziert:

- `ps_gift_group`: Speichert Definitionen für Geschenkkartengruppen (z.B. Wert, Name, Gültigkeit, Einschränkungen).
- `ps_giftcertlist`: Speichert die Historie der gekauften Geschenkkarten, einschließlich ihrer eindeutigen Codes, des ursprünglichen Werts, des aktuellen Saldos, des Empfängers, des Absenders und der zugehörigen Bestellung.
- `ps_gift_voucher`: Speichert Details einzelner Gutscheincodes, möglicherweise mit Verknüpfung zu `ps_cart_rule`, wenn es PrestaShops natives Gutscheinsystem nutzt.

Konfigurationsdatensätze, die in `ps_configuration` gespeichert sind, würden Folgendes umfassen:

- Modulspezifische Einstellungen, die über `getContent()` konfiguriert wurden, wie z.B. E-Mail-Vorlagen-IDs, PDF-Vorlagen-IDs, Anzeigeoptionen usw.
- `mowner`, `PS_SHOP_EMAIL`, `PS_SHOP_NAME` sind PrestaShop-Kernkonfigurationen, die vom Modul zum Senden von E-Mails verwendet werden.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Abschnitt jeder Seite. | CSS/JS-Assets, Meta-Tags oder modulspezifische Daten injizieren. |
| `displayLeftColumn` / `displayRightColumn` | In der linken/rechten Spalte des Front Office. | Einen Block zur Geschenkkartenwerbung oder einen Link zur Geschenkkartenseite anzeigen. |
| `displayProductAdditionalInfo` / `displayProductButtons` | Auf der Produktseite. | Möglicherweise eine Schaltfläche „Geschenkkarte kaufen“ oder verwandte Informationen anzeigen. |
| `displayFooter` | Im Footer-Abschnitt jeder Seite. | Einen Link zur Geschenkkartenseite hinzufügen. |
| `displayCustomerAccount` | Auf der Seite „Mein Konto“ des Kunden. | Einen Link zur Geschenkkarten-Historie/Details des Kunden hinzufügen. |
| `displayMyAccountBlock` | Auf der Seite „Mein Konto“ des Kunden (spezifisch für PrestaShop 1.6). | Einen Link zur Geschenkkarten-Historie/Details des Kunden hinzufügen. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | Die Generierung und das Senden von Geschenkkarten-Gutscheinen auslösen, wenn ein Geschenkkartenprodukt gekauft wird. Geschenkkarten-Historie aktualisieren. |
| `displayAdminOrder` | Auf der Bestelldetailseite im Back Office. | Geschenkkarteninformationen zur Bestellung anzeigen (gekauft oder verwendet). |
| `actionOrderStatusUpdate` | Wenn sich der Status einer Bestellung ändert. | Geschenkkarten basierend auf dem Bestellstatus aktivieren/deaktivieren (z.B. bei „Zahlung akzeptiert“ aktivieren). |
| `actionFrontControllerSetMedia` | Bevor ein Front-Controller seine Vorlage rendert. | Front-Office-spezifische CSS- und JavaScript-Assets laden. |
| `actionAdminControllerSetMedia` | Bevor ein Admin-Controller seine Vorlage rendert. | Back-Office-spezifische CSS- und JavaScript-Assets laden. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und um sicherzustellen, dass Sie die neueste, sicherste Version des Moduls „Geschenkkarten – Gutscheincodes verkaufen“ verwenden, besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, zeitnahe Unterstützung und kontinuierliche Verbesserungen unserer Module zu bieten.
