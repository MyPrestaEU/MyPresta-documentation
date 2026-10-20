---
title: "Block IP address Pro - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Block IP address Pro von MyPresta.eu."
sidebar:
  label: "Block IP address Pro"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Block IP address Pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/block-ip-address-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/block-ip-address-pro/)
>
> ---


# Block IP address Pro

## 1. Anforderungen & Kompatibilität
- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL), die typischerweise in jeder modernen Webhosting-Umgebung verfügbar sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren > Block IP address Pro)

Dies ist der Hauptkonfigurationsbildschirm für das Modul, auf dem Sie das globale Verhalten für blockierte Besucher definieren.

-   **Menüpfad:** Back Office > Module > Modul-Manager > Block IP address Pro > Konfigurieren

#### Einstellungen & Optionen:

1.  **Update-Benachrichtigungen anzeigen**
    -   **Was diese Einstellung bewirkt:** Steuert, ob Sie in Ihrem PrestaShop-Back-Office Benachrichtigungen erhalten, wenn eine neue Version des Moduls "Block IP address Pro" verfügbar ist.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Sie sehen Warnungen oder Nachrichten in Ihrem Admin-Panel, wenn ein Update veröffentlicht wird, was Ihnen hilft, Ihr Modul aktuell zu halten.
        -   *Wenn deaktiviert:* Sie erhalten diese Benachrichtigungen nicht und müssen manuell auf MyPresta.eu nach Updates suchen.
    -   **Empfohlener Wert:** JA
    -   **Händlerszenario / Beispiel:** Wenn diese Option aktiviert ist, stellen Sie sicher, dass Sie immer über neue Funktionen, Fehlerbehebungen oder Sicherheitsverbesserungen für das Modul informiert sind.

2.  **Nachricht für blockierte Benutzer (`banippro_msg`)**
    -   **Was diese Einstellung bewirkt:** Dies ist die benutzerdefinierte Nachricht, die Benutzern angezeigt wird, deren IP-Adresse blockiert wurde, *wenn* Sie sich entscheiden, sie nicht umzuleiten.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn ausgefüllt:* Blockierte Benutzer sehen diesen spezifischen Text auf einer leeren Seite anstelle Ihres Shop-Inhalts.
        -   *Wenn leer:* Wenn die Umleitung ebenfalls deaktiviert ist, sehen blockierte Benutzer möglicherweise einen generischen Fehler oder eine leere Seite ohne spezifische Nachricht.
    -   **Empfohlener Wert:** "Der Zugriff auf diesen Shop wurde für Ihre IP-Adresse verweigert." (oder eine ähnliche höfliche, aber bestimmte Nachricht).
    -   **Händlerszenario / Beispiel:** Sie möchten möglicherweise "Es tut uns leid, aber der Zugriff von Ihrem Standort wurde aufgrund ungewöhnlicher Aktivitäten eingeschränkt." anzeigen, um den Benutzer zu informieren, ohne zu viele Details preiszugeben.

3.  **Blockierte Benutzer umleiten (`banippro_redirect`)**
    -   **Was diese Einstellung bewirkt:** Bestimmt, ob blockierten Benutzern eine Nachricht angezeigt oder sie automatisch zu einer anderen Webseite weitergeleitet werden.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Blockierte Benutzer werden sofort zu der in der Einstellung "Umleitungs-URL" angegebenen URL weitergeleitet.
        -   *Wenn deaktiviert:* Blockierte Benutzer sehen die von Ihnen definierte "Nachricht für blockierte Benutzer".
    -   **Empfohlener Wert:** JA (Umleitung ist oft eine sauberere Benutzererfahrung als eine leere Seite mit einer Nachricht).
    -   **Händlerszenario / Beispiel:** Wenn Sie Spammer vollständig von Ihrer Website fernhalten oder einen problematischen Kunden auf eine Kundendienstseite leiten möchten, aktivieren Sie diese Option.

4.  **Umleitungs-URL (`banippro_url`)**
    -   **Was diese Einstellung bewirkt:** Die spezifische Webadresse (URL), zu der blockierte Benutzer weitergeleitet werden, wenn die Einstellung "Blockierte Benutzer umleiten" aktiviert ist.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn mit einer gültigen URL ausgefüllt:* Blockierte Benutzer werden zu dieser genauen Seite gesendet.
        -   *Wenn leer:* Wenn die Umleitung aktiviert ist, aber keine URL angegeben wird, könnte das Verhalten des Moduls unvorhersehbar sein, oder es könnte standardmäßig die Nachricht anzeigen.
    -   **Empfohlener Wert:** Die URL Ihrer Shop-Homepage (z.B. `https://www.ihrshop.de/`), oder eine spezifische "Kontakt"-Seite, oder sogar eine externe Website wie Google.
    -   **Händlerszenario / Beispiel:** Sie könnten sie zu `https://www.ihrshop.de/kontakt` umleiten, wenn Sie möchten, dass sie sich melden, oder zu `https://www.google.com`, um sie einfach von Ihrer Website zu entfernen.

#### Konfigurations-Kurzreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| Modulkonfiguration | Update-Benachrichtigungen anzeigen | JA | Zeigt Warnungen für neue Modulversionen an. |
| Modulkonfiguration | Nachricht für blockierte Benutzer | "Der Zugriff auf diesen Shop wurde für Ihre IP-Adresse verweigert." | Text, der blockierten Benutzern angezeigt wird, wenn sie nicht umgeleitet werden. |
| Modulkonfiguration | Blockierte Benutzer umleiten | JA | Wenn aktiviert, leitet blockierte Benutzer zu einer angegebenen URL weiter. |
| Modulkonfiguration | Umleitungs-URL | Die URL Ihrer Shop-Homepage | Das Ziel für umgeleitete blockierte Benutzer. |

### 2.2 Dedizierter Admin-Bildschirm: IP-Adressverwaltung (Back Office > Module > Block IP address Pro > IP-Adressen verwalten)

Dies ist der zentrale Verwaltungsbildschirm, auf dem Sie spezifische IP-Adressen hinzufügen, bearbeiten, aktivieren und deaktivieren können, die blockiert werden sollen.

-   **Menüpfad:** Nach der Installation des Moduls erscheint ein neuer Menüpunkt unter **Module > Block IP address Pro** (oder ähnlich, je nach PrestaShop-Version und Menüregistrierung des Moduls). Klicken Sie auf "IP-Adressen verwalten" oder "IP-Adressen sperren".

#### Verfügbare Aktionen & Einstellungen:

1.  **IP-Adressen-Liste:**
    -   Diese Tabelle zeigt alle IP-Adressen an, die Sie zum Blockieren konfiguriert haben.
    -   **Spalten:**
        -   **ID:** Eindeutige Kennung für den blockierten IP-Eintrag.
        -   **IP-Adresse:** Die tatsächlich blockierte IP-Adresse (z.B. `192.168.1.1`, `203.0.113.45`).
        -   **Anzahl der Aufrufe:** Eine Statistik, die anzeigt, wie oft diese spezifische IP-Adresse versucht hat, auf Ihren Shop zuzugreifen und blockiert wurde. Dies ist von unschätzbarem Wert, um hartnäckige Bedrohungen zu identifizieren.
        -   **Kommentar:** Ihre interne Notiz, warum diese IP blockiert wurde (z.B. "Spammer-Bot", "Konkurrenten-Scraping", "Problematischer Kunde").
        -   **Aktiv:** Ein Umschalter (An/Aus), um die Blockierung für diese spezifische IP schnell zu aktivieren oder zu deaktivieren, ohne den Eintrag zu löschen.
        -   **Aktionen:** Schaltflächen zum "Bearbeiten" oder "Löschen" einzelner IP-Einträge.

2.  **Hinzufügen einer neuen IP-Adresse:**
    -   Klicken Sie auf die Schaltfläche "Neue IP-Adresse hinzufügen" (oder ähnlich, normalerweise ein Plus-Symbol oder "Neu hinzufügen" oben rechts in der Tabelle).
    -   **Formularfelder:**
        -   **IP:** Geben Sie die genaue IP-Adresse ein, die Sie blockieren möchten.
        -   **Kommentar:** Fügen Sie eine beschreibende Notiz für Ihre Referenz hinzu (z.B. "Bekannte Spam-Quelle aus Analysen", "Kunde 'Max Mustermann' verursacht Probleme").
        -   **Aktiv:** Wählen Sie "An", um die Blockierung sofort zu aktivieren, oder "Aus", um den Eintrag zu speichern, ihn aber vorerst inaktiv zu lassen.
    -   **Speichern:** Klicken Sie auf "Speichern", um die neue IP zu Ihrer Sperrliste hinzuzufügen.

3.  **Bearbeiten einer vorhandenen IP-Adresse:**
    -   Klicken Sie auf das "Bearbeiten"-Symbol neben einer IP-Adresse in der Liste.
    -   Sie können die "IP", den "Kommentar" und den "Aktiv"-Status ändern.
    -   **Speichern:** Klicken Sie auf "Speichern", um Ihre Änderungen zu übernehmen.

4.  **Löschen einer IP-Adresse:**
    -   Klicken Sie auf das "Löschen"-Symbol neben einer IP-Adresse.
    -   Bestätigen Sie die Löschung. Dadurch wird die IP dauerhaft aus Ihrer Sperrliste entfernt.

#### Auswirkung von Änderungen:
-   **Hinzufügen einer IP:** Sobald gespeichert und aktiv, wird jeder Besucher, der versucht, von dieser IP-Adresse auf Ihren Shop zuzugreifen, sofort gemäß der globalen Konfiguration Ihres Moduls blockiert oder umgeleitet.
-   **Bearbeiten einer IP:** Änderungen an der IP-Adresse, dem Kommentar oder dem aktiven Status werden sofort wirksam.
-   **Deaktivieren einer IP:** Die IP-Adresse bleibt in Ihrer Liste, aber Besucher von dieser IP werden nicht mehr blockiert. Dies ist nützlich für temporäre Blockierungen oder wenn eine IP versehentlich blockiert wurde.
-   **Löschen einer IP:** Die IP wird dauerhaft aus der Sperrliste entfernt, und Besucher von dieser IP erhalten wieder vollen Zugriff auf Ihren Shop.

#### Empfohlener Arbeitsablauf für die tägliche Shop-Verwaltung:
1.  **Analysen überwachen:** Überprüfen Sie regelmäßig Ihre Website-Analysen auf verdächtige Traffic-Muster, hohe Absprungraten von bestimmten IPs oder ungewöhnliche Aktivitäten.
2.  **Problematische IPs identifizieren:** Wenn Sie eine IP-Adresse finden, die ständig Probleme verursacht (z.B. wiederholte fehlgeschlagene Anmeldeversuche, übermäßiges Seiten-Scraping, Spam-Kommentare), notieren Sie diese.
3.  **Zur Sperrliste hinzufügen:** Navigieren Sie zum Bildschirm "IP-Adressen verwalten", klicken Sie auf "Neue IP-Adresse hinzufügen", geben Sie die IP ein, fügen Sie einen beschreibenden Kommentar hinzu und stellen Sie sie auf "An".
4.  **Statistiken überprüfen:** Überprüfen Sie regelmäßig die Spalte "Anzahl der Aufrufe" für blockierte IPs. Hohe Zahlen weisen auf hartnäckige Versuche hin und bestätigen die Wirksamkeit Ihrer Blockierung.
5.  **Verwalten & Verfeinern:** Wenn eine IP-Adresse keine Bedrohung mehr darstellt, können Sie sie entweder deaktivieren (setzen Sie "Aktiv" auf "Aus") oder vollständig löschen.

### 2.3 Konfigurations-Kurzreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| IP-Adressverwaltung | Neue IP hinzufügen | N/A | Fügt eine neue IP-Adresse zur Sperrliste hinzu. |
| IP-Adressverwaltung | IP-Adresse (Feld) | N/A | Die spezifische IP, die blockiert werden soll. |
| IP-Adressverwaltung | Kommentar (Feld) | N/A | Ihre interne Notiz für die blockierte IP. |
| IP-Adressverwaltung | Aktiv (Umschalter) | An | Aktiviert/deaktiviert die Blockierung für eine bestimmte IP. |
| IP-Adressverwaltung | Anzahl der Aufrufe (Spalte) | 0 | Zählt, wie oft eine IP blockiert wurde. |
| IP-Adressverwaltung | Bearbeiten / Löschen Aktionen | N/A | Vorhandene blockierte IP-Einträge ändern oder entfernen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe eine IP blockiert, aber der Benutzer kann immer noch auf meinen Shop zugreifen. Was ist falsch?**
A:
1.  **"Aktiv"-Status überprüfen:** Stellen Sie sicher, dass der "Aktiv"-Umschalter für diese spezifische IP im Bildschirm "IP-Adressen verwalten" auf "An" steht.
2.  **Cache leeren:** PrestaShop verwendet Caching. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf "Cache leeren" (oder "Smarty-Cache leeren" für ältere Versionen). Dies stellt sicher, dass die Einstellungen des Moduls neu geladen werden.
3.  **IP-Adresse überprüfen:** Überprüfen Sie nochmals, ob Sie die korrekte IP-Adresse eingegeben haben. Manchmal ändern sich dynamische IPs, oder Sie haben ein Proxy-/CDN-Problem.
4.  **Browser-Cache:** Bitten Sie den blockierten Benutzer, seinen Browser-Cache zu leeren oder den Zugriff über ein Inkognito-Fenster zu versuchen.

**F: Mein legitimer Kunde ist blockiert! Wie behebe ich das?**
A:
1.  **Identifizieren Sie deren IP:** Bitten Sie den Kunden um seine aktuelle IP-Adresse (er kann sie finden, indem er bei Google nach "was ist meine IP" sucht).
2.  **Überprüfen Sie Ihre Sperrliste:** Gehen Sie zu **Module > Block IP address Pro > IP-Adressen verwalten** und suchen Sie nach deren IP.
3.  **Deaktivieren oder Löschen:** Wenn gefunden, setzen Sie entweder den "Aktiv"-Umschalter für diesen Eintrag auf "Aus" oder löschen Sie ihn vollständig.
4.  **Cache leeren:** Denken Sie daran, danach Ihren PrestaShop-Cache zu leeren.

**F: Kann ich einen Bereich von IP-Adressen anstelle nur einer blockieren?**
A: Die aktuelle Version des Moduls unterstützt das Blockieren einzelner IP-Adressen. Für das Blockieren von Bereichen müssten Sie jede IP innerhalb des Bereichs einzeln eingeben oder eine IP-Blockierung auf Serverebene in Betracht ziehen, wenn Sie Zugriff auf die Firewall Ihres Servers haben (z.B. über `.htaccess`-Regeln).

**F: Was passiert, wenn ich die Umleitung aktiviere, aber keine Umleitungs-URL angebe?**
A: Wenn "Blockierte Benutzer umleiten" aktiviert ist, aber "Umleitungs-URL" leer ist, könnte das Verhalten des Moduls inkonsistent sein. Es ist Best Practice, immer eine gültige URL anzugeben, wenn die Umleitung aktiv ist. Wenn Sie nicht umleiten möchten, deaktivieren Sie die Option "Blockierte Benutzer umleiten" und verwenden Sie stattdessen die benutzerdefinierte Nachricht.

**F: Wird dieses Modul meinen Shop verlangsamen?**
A: Nein, das Modul ist sehr leichtgewichtig und effizient konzipiert. Es überprüft die IP-Adresse des Besuchers sehr früh im PrestaShop-Ladevorgang. Wenn eine IP blockiert ist, wird die Anfrage schnell beendet oder umgeleitet, oft *bevor* Ihr Shop überhaupt beginnt, seinen vollständigen Inhalt zu laden, was die Leistung tatsächlich *verbessern* kann, indem es unerwünschte Serverlast reduziert.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen technischen Einblick in das Modul "Block IP address Pro" für Entwickler und Webmaster.

### 4.1 Architekturübersicht
Das Modul "Block IP address Pro" folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich die `Module`-Klasse für Installation/Deinstallation und Konfiguration sowie `AdminController` für die Back-Office-Verwaltung nutzt. Es verwendet eine benutzerdefinierte Datenbanktabelle zum Speichern blockierter IP-Adressen und bindet sich in den Hook `actionFrontControllerAfterInit` ein, um die IP-Prüfung so früh wie möglich im Anforderungslebenszyklus durchzuführen.

### 4.2 Controller (`controllers/`)

-   **Front-Office-Controller**:
    Das Modul verfügt über keine dedizierten Front-Office-Controller. Die IP-Blockierungslogik wird direkt in der Hauptmoduldatei (`banippro.php`) über einen Hook behandelt, um eine frühe Ausführung zu gewährleisten.

-   **Back-Office-Admin-Controller**:
    1.  `banippro/controllers/admin/AdminBanIpProController.php`
        *   **Klassenname & Elternklasse:** `AdminBanIpProController` erweitert `ModuleAdminController`.
        *   **Verantwortlichkeit:** Dieser Controller ist für die Verwaltung der Liste der blockierten IP-Adressen im PrestaShop Back Office zuständig. Er bietet die Standard-CRUD-Schnittstelle (Create, Read, Update, Delete) für die `BanIpPro`-Entität. Er verwaltet:
            *   Anzeige der Liste der blockierten IPs mit ihren Details (IP, Aufrufe, Kommentar, aktiver Status).
            *   Hinzufügen neuer IP-Adressen zur Sperrliste.
            *   Bearbeiten vorhandener IP-Adresseneinträge.
            *   Löschen von IP-Adressen aus der Sperrliste.
            *   Verwaltung des "Aktiv"-Status-Umschalters für jede IP.
            *   Die Methoden `initContent()`, `renderList()`, `renderForm()` werden hier typischerweise überschrieben, um die Anzeige und Formulare anzupassen.
            *   Er ist der `ban`-Datenbanktabelle zugeordnet (oder ähnlich, wie durch das `BanIpPro`-Modell definiert, falls es existierte).

    2.  `banippro/controllers/admin/index.php`
        *   **Verantwortlichkeit:** Dies ist eine standardmäßige leere `index.php`-Datei, die oft in PrestaShop-Modulunterverzeichnissen zu finden ist. Ihr Hauptzweck ist es, aus Sicherheitsgründen die Verzeichnisauflistung auf Webservern zu verhindern. Sie enthält keine funktionale Logik für das Modul.

### 4.3 Kernklassen & Modelle (`classes/`)
Die Modulbeschreibung weist auf keine benutzerdefinierten Klassen im Verzeichnis `classes/` hin. Die `BanIpPro`-Entität (für blockierte IPs) wird wahrscheinlich direkt im `AdminBanIpProController` und der Hauptdatei `banippro.php` verwaltet, möglicherweise unter Verwendung einer einfachen `Db`-Klasseninteraktion oder einer internen Array-Struktur, falls sie nicht vollständig `ObjectModel`-konform ist. Wenn ein `ObjectModel` verwendet würde, würde es typischerweise `BanIpPro` heißen und sich in `classes/BanIpPro.php` befinden.

Angesichts der Tatsache, dass der `AdminBanIpProController` eine "ban"-Entität verwaltet, impliziert dies eine zugrunde liegende Datenstruktur. Wenn es sich nicht um ein dediziertes `ObjectModel` handelt, wären es direkte Datenbankabfragen.

### 4.4 JavaScript-Assets (`views/js/`)
Die Modulbeschreibung weist auf keine benutzerdefinierten JavaScript-Dateien hin. Interaktive Elemente im Back Office (wie Umschalter oder Formularvalidierung) werden wahrscheinlich von PrestaShops Kern-JS oder Inline-Skripten innerhalb von Templates behandelt.

### 4.5 CSS-Stylesheets (`views/css/`)
Die Modulbeschreibung weist auf keine benutzerdefinierten CSS-Dateien hin. Das Styling für die Back-Office-Konfiguration und die IP-Verwaltungsbildschirme basiert vollständig auf dem Standard-Back-Office-Theme-CSS von PrestaShop.

### 4.6 Smarty-Template-Struktur (`views/templates/`)
Die Modulbeschreibung weist auf keine benutzerdefinierten Template-Dateien hin.
-   **Hook-Templates**: Das Front-Office-Verhalten des Moduls (Blockierung/Umleitung) wird programmatisch im Hook behandelt, nicht über ein Template.
-   **Admin-Templates**: Das Konfigurationsformular für `getContent()` und die Listen-/Formularansichten für `AdminBanIpProController` werden wahrscheinlich mit PrestaShops Standard-Hilfsklassen (`HelperForm`, `HelperList`) gerendert, die direkt HTML generieren, oder basieren auf sehr minimalen Inline-Templates, falls vorhanden.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:
    Das Modul erstellt während der Installation mindestens eine benutzerdefinierte Tabelle, um die blockierten IP-Adressen zu speichern.
    -   `ps_banippro` (oder ähnlich, z.B. `ps_ban_ip_pro`):
        *   `id_banippro` (Primärschlüssel, INT)
        *   `ip_address` (VARCHAR, speichert die zu blockierende IP-Adresse)
        *   `comment` (TEXT, für Admin-Notizen)
        *   `views` (INT, Zähler, wie oft diese IP blockiert wurde)
        *   `active` (TINYINT(1), 0 oder 1, zum Aktivieren/Deaktivieren der Blockierung)

    Konfigurationseinstellungen (`mypresta_updates`, `banippro_msg`, `banippro_redirect`, `banippro_url`) werden in der Tabelle `ps_configuration` gespeichert.

-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
|---|---|---|
| `actionFrontControllerAfterInit` | Wird ausgeführt, nachdem der Front-Controller initialisiert wurde, aber bevor Inhalte gerendert werden. | **KRITISCH:** Hier führt das Modul seine Kernfunktion aus: Überprüfung der IP des Besuchers mit der Sperrliste. Wenn eine Übereinstimmung gefunden wird, wird entweder die benutzerdefinierte Nachricht angezeigt oder eine Umleitung durchgeführt, wodurch die weitere Seitenausführung effektiv gestoppt wird. |
| `displayHome` | Rendert Inhalte auf der Startseite. | Wahrscheinlich für Update-Benachrichtigungen oder andere modulspezifische Inhalte verwendet, falls das Modul eine Front-Office-Komponente hätte. Im Kontext dieses Moduls könnte es ein Legacy-Hook sein oder für sehr spezifische, nicht-blockierende Logik verwendet werden. |
| `home` | Alias für `displayHome` in einigen Kontexten. | Wie `displayHome`. |
| `header` | Rendert Inhalte innerhalb des `<head>`-Abschnitts des HTML. | Wird zum Hinzufügen von CSS, JavaScript oder Meta-Tags verwendet. In diesem Modul könnte es für Update-Benachrichtigungen oder zur Sicherstellung des frühen Ladens von Skripten/Stilen verwendet werden, falls erforderlich. |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin-Controller seine Medien (CSS/JS) einstellt. | Wird vom Modul verwendet, um spezifische CSS- oder JavaScript-Dateien hinzuzufügen, die für seine Back-Office-Konfigurationsseiten (z.B. für `AdminBanIpProController`) erforderlich sind. |
| `ActionAdminControllerSetMedia` | (Duplikat des obigen, Groß-/Kleinschreibung-Unterschied) | Wie `actionAdminControllerSetMedia`. PrestaShop-Hooks sind im Allgemeinen nicht zwischen Groß- und Kleinschreibung zu unterscheiden, aber Module registrieren manchmal beide zur Kompatibilität. |
| `displayHeader` | Rendert Inhalte innerhalb des `<header>`-Abschnitts des HTML (oft im `<body>` vor dem Hauptinhalt). | Ähnlich wie `header`, aber typischerweise für sichtbare Elemente. In diesem Modul ist es aufgrund seiner blockierenden Natur weniger wahrscheinlich, dass es einen direkten Front-Office-Einfluss hat. |

## 5. Offizieller Support & Updates
Für die neuesten Modul-Updates, Fehlerbehebungen und professionellen Support wenden Sie sich bitte an Ihr Kundenkonto bei MyPresta.eu. Unser Team ist bestrebt, zeitnahe Unterstützung zu leisten und sicherzustellen, dass Ihr Modul reibungslos funktioniert.
-   **MyPresta.eu Bestellhistorie & Downloads:** [https://mypresta.eu/my-account/orders/](https://mypresta.eu/my-account/orders/)
-   **MyPresta.eu Support-Kontakt:** [https://mypresta.eu/contact](https://mypresta.eu/contact)
