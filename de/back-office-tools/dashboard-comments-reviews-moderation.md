---
title: "Dashboard-Kommentare / Bewertungen Moderation - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Dashboard comments / reviews moderation' von MyPresta.eu."
sidebar:
  label: "Dashboard-Kommentare / Bewertungen Moderation"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Dashboard comments / reviews moderation auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/dashboard-comments-reviews-moderation.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/dashboard-comments-reviews-moderation/)
>
> ---


# Dashboard-Kommentare / Bewertungen Moderation

## 1. Anforderungen & Kompatibilität
- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind für PrestaShop selbst erforderlich und typischerweise in allen modernen Hosting-Umgebungen verfügbar.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf "Konfigurieren" zur Hauptkonfigurationsseite des Moduls. Dieses Modul ist sehr einfach gehalten, mit minimalen Einstellungen, da seine Hauptfunktion darin besteht, Informationen auf Ihrem Dashboard anzuzeigen.

**Bildschirmname:** Dashboard-Kommentare / Bewertungen Moderation Konfiguration

**Menüpfad:** Back Office > Module > Modul-Manager > Dashboard-Kommentare / Bewertungen Moderation > Konfigurieren

| Einstellung / Option | Was diese Einstellung bewirkt | Auswirkung einer Änderung dieser Einstellung | Empfohlener Wert | Händlerszenario / Beispiel |
|---|---|---|---|---|
| **MyPresta.eu Updates** | Dieser Abschnitt bezieht sich typischerweise auf die Überprüfung von Updates für MyPresta.eu-Module. Er könnte Optionen zum Aktivieren/Deaktivieren von Update-Prüfungen oder zum Anzeigen von Update-Benachrichtigungen enthalten. | *Wenn aktiviert:* Das Modul prüft regelmäßig MyPresta.eu auf neuere Versionen und benachrichtigt Sie im Back Office, wenn ein Update verfügbar ist. Dies hilft Ihnen, Ihr Modul mit den neuesten Funktionen und Fehlerbehebungen aktuell zu halten. *Wenn deaktiviert:* Das Modul prüft nicht automatisch auf Updates. Sie müssten manuell auf MyPresta.eu nach Updates suchen. | **Aktiviert (Ja)** | Wenn dies aktiviert ist, sind Sie immer über neue Versionen informiert und können von Verbesserungen und Sicherheitsupdates profitieren, ohne manuelle Prüfungen durchführen zu müssen. |
| **Update_ (Intern)** | Dies ist eine interne Einstellung, die wahrscheinlich mit dem Update-Mechanismus selbst zusammenhängt. Sie ist normalerweise nicht für die direkte Interaktion des Händlers gedacht. | Eine Änderung dieser Einstellung wird nicht empfohlen, da sie die Fähigkeit des Moduls beeinträchtigen könnte, Updates zu prüfen und anzuwenden. | **Als Standard belassen** | Dies ist eine technische Einstellung; Shop-Betreiber sollten sie nicht ändern. |
| **Updatev_ (Intern)** | Ähnlich wie `update_` ist dies eine interne versionsbezogene Einstellung für den Update-Mechanismus. | Eine Änderung dieser Einstellung wird nicht empfohlen, da sie die Fähigkeit des Moduls beeinträchtigen könnte, Updates zu prüfen und anzuwenden. | **Als Standard belassen** | Dies ist eine technische Einstellung; Shop-Betreiber sollten sie nicht ändern. |

**Wichtiger Hinweis:** Die Kernfunktionalität der Anzeige von Kommentaren und Bewertungen auf Ihrem Dashboard erfordert keine umfangreiche Konfiguration. Nach der Installation integriert sich das Modul automatisch in Ihr Dashboard, um ausstehende Bewertungen und gemeldete Kommentare anzuzeigen, vorausgesetzt, Sie haben das Standard-PrestaShop-Modul "Produktkommentare" (oder eine kompatible Alternative) installiert und aktiviert.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten
Dieses Modul führt **keine** neuen dedizierten Admin-Bildschirme oder benutzerdefinierten Controller-Ansichten ein. Seine Funktionalität ist direkt in das bestehende PrestaShop-Dashboard integriert.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| Modul-Konfigurationsseite | MyPresta.eu Updates | Aktiviert (Ja) | Ermöglicht automatische Prüfungen auf Modul-Updates von MyPresta.eu. |
| Modul-Konfigurationsseite | Update_ | Als Standard belassen | Interne Einstellung für den Update-Mechanismus. |
| Modul-Konfigurationsseite | Updatev_ | Als Standard belassen | Interne Einstellung für den Update-Mechanismus. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe das Modul installiert, sehe aber keine Kommentare/Bewertungen auf meinem Dashboard.**
**A1:**
*   **"Produktkommentare"-Modul prüfen:** Dieses Modul ist auf das Standard-PrestaShop-Modul "Produktkommentare" (oder ein kompatibles Drittanbieter-Bewertungsmodul) angewiesen, um zu funktionieren. Stellen Sie sicher, dass das Modul "Produktkommentare" in Ihrem Shop installiert, aktiviert und korrekt konfiguriert ist.
*   **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Performance** und klicken Sie oben rechts auf "Cache leeren". Manchmal muss der PrestaShop-Cache aktualisiert werden, damit neue Dashboard-Elemente erscheinen.
*   **Auf ausstehende Bewertungen prüfen:** Haben Sie tatsächlich Bewertungen, die auf Moderation warten, oder Kommentare, die als missbräuchlich gemeldet wurden? Das Modul zeigt nur Inhalte an, die Ihre Aufmerksamkeit erfordern. Wenn es keine solchen Elemente gibt, kann der Dashboard-Block leer erscheinen oder nicht angezeigt werden, wenn nichts anzuzeigen ist.

**F2: Der Dashboard-Block sieht seltsam aus oder ist nicht korrekt gestylt.**
**A2:**
*   **Browser-Cache leeren:** Manchmal speichert Ihr Webbrowser alte CSS-Dateien im Cache. Versuchen Sie, den Cache Ihres Browsers zu leeren oder Ihr Back Office in einem Inkognito-/privaten Fenster zu öffnen.
*   **Auf Theme-Konflikte prüfen:** Obwohl selten bei Dashboard-Modulen, könnte ein stark angepasstes Admin-Theme potenziell Konflikte verursachen. Wenn Sie dies vermuten, versuchen Sie, vorübergehend zum Standard-PrestaShop-Admin-Theme zu wechseln (falls möglich), um zu sehen, ob das Problem weiterhin besteht. Wenn es sich löst, wenden Sie sich an Ihren Theme-Entwickler.
*   **PrestaShop-Cache leeren:** Wie oben erwähnt, kann das Leeren des Smarty-Caches unter **Erweiterte Einstellungen > Performance** Anzeigeprobleme beheben.

**F3: Wie übersetze ich den Text des Moduls in eine andere Sprache?**
**A3:**
*   Navigieren Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**.
*   Wählen Sie "Übersetzungen installierter Module" für den "Übersetzungstyp".
*   Wählen Sie Ihr Theme (z.B. "Classic") und die Sprache, in die Sie übersetzen möchten.
*   Suchen Sie "Dashboard comments / reviews moderation" in der Liste, klicken Sie auf "Ändern", und Sie können dann alle verfügbaren Textzeichenfolgen übersetzen.

**F4: Ich habe auf "Konfigurieren" geklickt, sehe aber nur Update-Einstellungen, nicht die Moderationstools.**
**A4:** Die Schaltfläche "Konfigurieren" für dieses Modul führt zu seiner minimalen Einstellungsseite, hauptsächlich für die Update-Verwaltung. Die eigentlichen Moderationstools (die Liste der Kommentare/Bewertungen) werden direkt auf Ihrem Haupt-PrestaShop-Dashboard angezeigt, normalerweise in einem der "Dashboard-Zonen"-Bereiche. Navigieren Sie zu Ihrem Haupt-Dashboard (der ersten Seite, die Sie nach dem Einloggen sehen), um die Ausgabe des Moduls zu finden.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht
Das Modul "Dashboard comments / reviews moderation" (`dashcomments`) ist ein leichtgewichtiges PrestaShop-Modul, das zur Erweiterung des Back Office-Dashboards entwickelt wurde. Es nutzt das Hook-System von PrestaShop, um einen benutzerdefinierten Block in das Dashboard einzufügen, der ausstehende Produktbewertungen und gemeldete Kommentare anzeigt. Es führt keine neuen Datenbanktabellen oder komplexen `ObjectModel`-Strukturen ein, sondern stützt sich auf vorhandene Daten aus dem Modul `ps_product_comment`. Seine Hauptfunktion ist die Präsentation und Interaktion mit vorhandenen Daten über AJAX.

### 4.2 Controller (`controllers/`)
Dieses Modul enthält **keine** benutzerdefinierten Front-Office- oder Back-Office-Controller. Alle Interaktionen werden entweder direkt innerhalb der Hauptmodulklasse (`dashcomments.php`) oder über AJAX-Aufrufe verarbeitet, die von den `ajaxProcess`-Methoden des Moduls verarbeitet werden.

### 4.3 Kernklassen & Modelle (`classes/`)
Dieses Modul definiert **keine** benutzerdefinierten Klassen oder Modelle im Verzeichnis `classes/`. Es interagiert direkt mit den Kernfunktionen von PrestaShop und implizit mit der `ProductComment`-Klasse aus dem Modul `ps_product_comments` (falls installiert).

### 4.4 JavaScript-Assets (`views/js/`)

-   **`dashcomments/js/dashcomments.js`**
    *   **Geltungsbereich:** Back-Office (Dashboard).
    *   **Zweck:** Verwaltet AJAX-Interaktionen zur Moderation von Kommentaren und Bewertungen direkt über das Dashboard-Widget.
    *   **Hauptfunktionalität:**
        *   Bindet Klick-Event-Listener an die Schaltflächen "Genehmigen", "Ablehnen" und "Löschen" innerhalb des Dashboard-Widgets.
        *   Sendet AJAX-Anfragen an die `ajaxProcess`-Methoden des Moduls (z.B. `ajaxProcessApproveComment`, `ajaxProcessDisapproveComment`, `ajaxProcessDeleteComment`), um Moderationsaktionen durchzuführen.
        *   Aktualisiert das DOM (entfernt die moderierte Kommentarzeile, aktualisiert Zähler) nach erfolgreicher AJAX-Antwort.
        *   Kann Logik zur Handhabung von "als missbräuchlich melden"-Aktionen enthalten, falls für die Kommentare selbst implementiert.
        *   Verwendet `$.ajax` für die asynchrone Kommunikation.

### 4.5 CSS-Stylesheets (`views/css/`)

-   **`dashcomments/css/dashcomments.css`**
    *   **Geltungsbereich:** Back-Office (Dashboard).
    *   **Zweck:** Bietet Styling für das Dashboard-Widget, das ausstehende Kommentare und Bewertungen anzeigt.
    *   **Haupt-Styling:**
        *   Styles für die Kommentarliste, einzelne Kommentarzeilen, Aktionsschaltflächen (genehmigen, ablehnen, löschen) und potenziell Zähler für ausstehende Elemente.
        *   Stellt sicher, dass das Widget visuell in das PrestaShop 1.7+/8+ Back-Office-Theme integriert ist.
        *   **Wichtige CSS-Klassenselektoren:** Entwickler können den generierten HTML-Code auf spezifische Klassen (z.B. `.dashcomments-widget`, `.dashcomments-item`, `.dashcomments-actions`) überprüfen, um das Styling in ihren benutzerdefinierten Admin-Themes zu überschreiben oder zu erweitern.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

-   **`dashcomments/dashboardZoneOne.tpl`**
    *   **Geltungsbereich:** Back-Office (Dashboard).
    *   **Hook:** `displaydashboardZoneTwo` (oder `dashboardZoneTwo` in älteren Versionen).
    *   **Zweck:** Dieses Template ist für das Rendern der HTML-Struktur des Kommentare-/Bewertungsmoderations-Widgets auf dem PrestaShop-Dashboard verantwortlich.
    *   **Inhalt:**
        *   Zeigt eine Liste der Produktkommentare an, die auf Genehmigung warten.
        *   Zeigt eine Liste der Produktkommentare an, die als missbräuchlich gemeldet wurden.
        *   Für jeden Kommentar werden typischerweise der Produktname, der Kundenname, der Kommentarinhalt, die Bewertung und Aktionsschaltflächen (Genehmigen, Ablehnen, Löschen) angezeigt.
        *   Enthält Logik zum Iterieren über die vom Modul übergebenen Variablen `$pending_comments` und `$reported_comments`.
        *   Enthält die notwendigen HTML-Elemente und Datenattribute, damit das `dashcomments.js`-Skript seine Event-Listener anhängen und AJAX-Aktionen ausführen kann.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**: Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es stützt sich auf die Tabelle `ps_product_comment` (und verwandte Tabellen wie `ps_product_comment_grade`, `ps_product_comment_criterion`), die vom offiziellen Modul `ps_product_comments` erstellt werden.
-   **Konfigurationsdatensätze**:
    *   `PS_DASHCOMMENTS_UPDATES`: Speichert den Status der Update-Prüfungen.
    *   `PS_DASHCOMMENTS_UPDATE_`: Internes Update-Flag.
    *   `PS_DASHCOMMENTS_UPDATEV_`: Internes Versions-Flag für Updates.

-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
|---|---|---|
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin-Controller seine Medien-Assets (CSS/JS) einrichtet. | Wird verwendet, um die `dashcomments.js`- und `dashcomments.css`-Dateien des Moduls für das Back Office-Dashboard zu registrieren. |
| `displaydashboardZoneTwo` | Rendert Inhalte in der zweiten Zone des PrestaShop Back Office-Dashboards. | Dies ist der primäre Hook, der verwendet wird, um das Kommentare-/Bewertungsmoderations-Widget anzuzeigen. |
| `dashboardZoneTwo` | (Legacy-Hook, ähnlich `displaydashboardZoneTwo`) | Bietet Kompatibilität für ältere PrestaShop-Versionen oder alternative Dashboard-Layouts zur Anzeige des Widgets. |

## 5. Offizieller Support & Updates
Für offiziellen Support, Modul-Updates und weitere Unterstützung besuchen Sie bitte Ihr Kundenkonto auf [MyPresta.eu](https://mypresta.eu/). Sie können die neuesten Versionen des Moduls aus Ihrer Bestellhistorie herunterladen und unsere speziellen Support-Kanäle für technische Fragen oder Probleme nutzen.
