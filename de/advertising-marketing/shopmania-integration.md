---
title: "Shopmania Integration - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Shopmania Integration von MyPresta.eu."
sidebar:
  label: "Shopmania Integration"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Shopmania Integration auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/shopmania-integration.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/shopmania-integration/)
>
> ---


# Shopmania Integration

## 1. Anforderungen & Kompatibilität
- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für den allgemeinen PrestaShop-Betrieb erforderlich, aber dieses Modul hat minimale spezifische Anforderungen über eine Standard-PrestaShop-Hosting-Umgebung hinaus.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)
Klicken Sie nach der Installation im Modul-Manager neben dem Modul "Shopmania Integration" auf "Konfigurieren". Dies führt Sie zur Hauptkonfigurationsseite.

Das Shopmania Integration Modul ist sehr einfach gestaltet und erfordert oft nur minimale Konfiguration, da es sich hauptsächlich auf die Generierung eines Produktfeeds konzentriert.

| Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|
| **ShopMania Feed URL** | Automatisch generiert | Dies ist der direkte Link zum Produktfeed, der von Ihrem Modul generiert wird. Sie müssen diese URL kopieren und ShopMania zur Verfügung stellen, wenn Sie Ihr Händlerkonto bei ihnen einrichten. Diese URL wird von ShopMania verwendet, um Ihre Produktdaten regelmäßig abzurufen. |

**Was diese Einstellung bewirkt:**
Dieser Abschnitt zeigt die URL an, die ShopMania verwenden wird, um auf Ihren Produktdatenfeed zuzugreifen. Dieser Feed enthält alle notwendigen Informationen über Ihre Produkte (Name, Beschreibung, Preis, Bilder, Verfügbarkeit usw.) in einem Format, das ShopMania verstehen und auf ihrer Plattform anzeigen kann.

**Auswirkung einer Änderung dieser Einstellung:**
Sie können diese URL nicht direkt ändern. Sie wird vom Modul automatisch basierend auf der Domain Ihres Shops und der internen Logik des Moduls generiert.

**Empfohlener Wert:**
Kopieren Sie diese URL genau so, wie sie erscheint. Ändern Sie sie nicht.

**Händlerszenario / Beispiel:**
Nach der Installation und Konfiguration des Moduls melden Sie sich bei Ihrem ShopMania-Händlerkonto an (oder erstellen eines). ShopMania wird Sie nach der "Produkt-Feed-URL" oder "Daten-Feed-URL" fragen. Sie fügen dann die auf dieser Konfigurationsseite angegebene URL in das entsprechende Feld auf der ShopMania-Website ein. ShopMania wird diese URL dann regelmäßig besuchen, um Ihre Produktlisten auf ihrer Plattform zu aktualisieren.

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Produkte erscheinen nicht auf ShopMania. Was soll ich tun?**
A:
1.  **Überprüfen Sie die Feed-URL:** Stellen Sie sicher, dass Sie die genaue Feed-URL von der Konfigurationsseite des Moduls korrekt in die Einstellungen Ihres ShopMania-Händlerkontos kopiert und eingefügt haben.
2.  **ShopMania Verarbeitungszeit:** Es kann einige Zeit dauern (Stunden bis einige Tage), bis ShopMania Ihren Feed zum ersten Mal verarbeitet. Haben Sie Geduld.
3.  **Feed-Zugänglichkeit:** Versuchen Sie, die Feed-URL in Ihrem Webbrowser zu öffnen. Lädt sie? Zeigt sie Produktdaten an? Wenn ein Fehler oder eine leere Seite angezeigt wird, könnte ein serverseitiges Problem oder ein Problem mit dem Generierungsprozess des Moduls vorliegen. Kontaktieren Sie den MyPresta.eu-Support.
4.  **Produktsichtbarkeit:** Stellen Sie sicher, dass Ihre Produkte in Ihrem PrestaShop-Shop aktiv, auf Lager und sichtbar sind. Produkte, die deaktiviert oder nicht auf Lager sind, werden möglicherweise nicht in den Feed aufgenommen.

**F: Aktualisiert dieses Modul Preise und Lagerbestände auf ShopMania automatisch?**
A: Ja, der von diesem Modul generierte Feed spiegelt die aktuellen Preise und Lagerbestände Ihres PrestaShop-Shops wider. ShopMania ruft diesen Feed regelmäßig erneut ab, um seine Einträge aktuell zu halten. Die Häufigkeit der Aktualisierungen hängt vom Abrufplan von ShopMania ab, den Sie möglicherweise in Ihrem ShopMania-Händlerkonto konfigurieren können.

**F: Kann ich auswählen, welche Produkte in den Feed aufgenommen werden?**
A: Die Basisversion dieses Moduls enthält typischerweise alle aktiven und sichtbaren Produkte. Wenn Sie eine erweiterte Filterung benötigen (z.B. den Ausschluss bestimmter Kategorien oder Produkte), würde dies eine kundenspezifische Entwicklung oder ein fortschrittlicheres Feed-Management-Modul erfordern. Das Modul "Shopmania Integration" konzentriert sich auf eine unkomplizierte, vollständige Katalogintegration.

**F: Ich sehe einen Fehler, wenn ich versuche, das Modul zu konfigurieren.**
A:
1.  **Cache leeren:** Gehen Sie in Ihrem PrestaShop-Backoffice zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf "Cache leeren". Manchmal können alte Cache-Dateien die Modulkonfiguration stören.
2.  **Server-Fehlerprotokolle überprüfen:** Wenn das Problem weiterhin besteht, überprüfen Sie die PHP-Fehlerprotokolle Ihres Servers. Diese Protokolle können spezifische technische Details darüber liefern, was schiefgelaufen ist. Möglicherweise müssen Sie Ihren Hosting-Anbieter oder einen Entwickler kontaktieren.
3.  **Support kontaktieren:** Wenn Sie weiterhin Probleme haben, sammeln Sie alle Fehlermeldungen oder Screenshots und kontaktieren Sie den MyPresta.eu-Support für Unterstützung.

**F: Was ist, wenn mein benutzerdefiniertes Theme Anzeigeprobleme verursacht (obwohl dieses Modul keine Front-Office-Anzeige hat)?**
A: Da dieses Modul keine Front-Office-Anzeige hat, ist es höchst unwahrscheinlich, dass es visuelle Probleme mit Ihrem benutzerdefinierten Theme verursacht. Sein Betrieb ist rein Backend-basiert und generiert eine Datendatei.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)
Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht
Das Modul `Shopmania Integration` ist ein einfaches, einteiliges PrestaShop-Modul, das zur Generierung eines XML-Produktfeeds entwickelt wurde, der mit der ShopMania-Plattform kompatibel ist. Es folgt einer Standard-PrestaShop-Modulstruktur und verwendet hauptsächlich die Methoden `install()` und `uninstall()` für die Einrichtung sowie die Methode `getContent()` für seine Back-Office-Konfiguration, die in diesem Fall einfach die generierte Feed-URL anzeigt. Die Kernlogik befindet sich in der Hauptmoduldatei, die für die dynamische Generierung des XML-Feeds verantwortlich ist, wenn die spezifische Feed-URL aufgerufen wird. Es verwendet keine benutzerdefinierten Controller, Modelle oder dedizierten Template-Dateien für seine Kernfunktionalität, sondern verlässt sich auf die direkte Ausgabe für den Feed.

### 4.2 Controller (`controllers/`)
-   **Front-Office-Controller**: Keine. Der Produktfeed wird direkt von der Hauptdatei des Moduls generiert, wenn seine spezifische URL aufgerufen wird, anstatt über einen dedizierten `ModuleFrontController`.
-   **Back-Office-Admin-Controller**: Keine. Die gesamte Konfiguration (Anzeige der Feed-URL) wird innerhalb der Methode `getContent()` der Hauptmodulklasse behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)
-   In diesem Modul sind keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen vorhanden. Die gesamte Logik ist in der Klasse `ShopmaniaIntegration` in der Hauptmoduldatei enthalten.

### 4.4 JavaScript-Assets (`views/js/`)
-   Es sind keine JavaScript-Dateien in diesem Modul enthalten oder werden verwendet.

### 4.5 CSS-Stylesheets (`views/css/`)
-   Es sind keine CSS-Dateien in diesem Modul enthalten oder werden verwendet.

### 4.6 Smarty-Template-Struktur (`views/templates/`)
-   Es werden keine benutzerdefinierten Smarty-Template-Dateien (`.tpl`) von diesem Modul verwendet. Die Methode `getContent()` gibt den HTML-Code für die Konfigurationsseite direkt aus, und der Produktfeed wird als reines XML generiert.

### 4.7 Datenbankschema & Hooks-Map
-   **Datenbanktabellen**: Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es speichert seine Konfiguration (falls über die Feed-URL hinaus erforderlich) in der Standardtabelle `ps_configuration`, obwohl für dieses Modul die Feed-URL dynamisch generiert und nicht als Konfigurationswert gespeichert wird.
-   **Registrierte Hooks-Tabelle**:
    Dieses Modul registriert keine Hooks explizit in der Methode `install()` für die Front-Office-Anzeige oder Aktion. Seine Hauptfunktion besteht darin, auf eine direkte URL-Anfrage für den XML-Feed zu reagieren. Obwohl die Funktionsbeschreibung "Front-Office Hooks: Header, Columns, Product, or Footer" erwähnt, ist dies wahrscheinlich eine generische Beschreibung für Module, die diese *nutzen könnten*, aber dieses spezifische Modul implementiert keine visuellen Front-Office-Komponenten. Seine Integration basiert rein auf Datenfeeds.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
|---|---|---|
| `displayBackOfficeHeader` | Wird beim Rendern des Back Office-Headers ausgeführt. | Wird verwendet, um modulspezifisches CSS/JS für die Konfigurationsseite einzubinden (obwohl dieses Modul keine verwendet). |
| `displayHeader` | Wird im `<head>`-Abschnitt der Front-Office-Seiten ausgeführt. | (Wird von diesem Modul nicht für die visuelle Ausgabe verwendet, könnte aber bei Bedarf für Meta-Tags oder Skripte verwendet werden). |
| `displayRightColumn` | Wird in der rechten Spalte der Front-Office-Seiten ausgeführt. | (Wird von diesem Modul nicht verwendet). |
| `displayLeftColumn` | Wird in der linken Spalte der Front-Office-Seiten ausgeführt. | (Wird von diesem Modul nicht verwendet). |
| `displayProductAdditionalInfo` | Wird auf der Produktseite ausgeführt. | (Wird von diesem Modul nicht verwendet). |
| `displayFooter` | Wird im Footer der Front-Office-Seiten ausgeführt. | (Wird von diesem Modul nicht verwendet). |

Die Kernfunktionalität des Moduls (Generierung des XML-Feeds) wird ausgelöst, wenn die spezifische Feed-URL (z.B. `ihrshop.com/modules/shopmania-integration/shopmania-feed.php` oder ähnlich, abhängig vom PrestaShop-Routing) aufgerufen wird. Dies ist kein Standard-PrestaShop-Hook, sondern eine direkte HTTP-Anfrage an einen modulspezifischen Endpunkt.

## 5. Offizieller Support & Updates
Für offizielle Updates, technischen Support und weitere Unterstützung zum Shopmania Integration Modul wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei modulbezogenen Problemen zur Seite und sorgt für einen reibungslosen Ablauf Ihrer Integration.
