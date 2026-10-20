---
title: "Amazon Ads Tag Conversions API – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Amazon Ads Tag Conversions API von MyPresta.eu."
sidebar:
  label: "Amazon Ads Tag Conversions API – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Amazon Ads Tag Conversions API auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/amazon-ads-tag-conversions-api.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/amazon-ads-tag-conversions-api/)
>
> ---


# Amazon Ads Tag Conversions API

## 1. Anforderungen & Kompatibilität

-   **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
-   **PHP-Kompatibilität**: PHP 7.1 - 8.5
-   **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind erforderlich, damit das Modul korrekt funktioniert, insbesondere für die Conversions API (CAPI), die auf sicherer Server-zu-Server-Kommunikation basiert. Ihre Hosting-Umgebung sollte auch ausgehende Verbindungen zu den Amazon-API-Endpunkten zulassen.

## 2. Vollständige Konfigurationsübersicht (Jede Einstellung nach Bildschirm gruppiert)

Dieser Abschnitt führt Sie durch jede Einstellung des Moduls „Amazon Ads Tag Conversions API“.

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie Ihr Amazon Ads Tracking einrichten.

**Zugriff:** Navigieren Sie zu **Module > Modul-Manager**, suchen Sie dann „Amazon Ads Tag Conversions API“ und klicken Sie auf **Konfigurieren**.

#### **Auswahl des Tracking-Modus**

Dieser Abschnitt bestimmt, wie Ihr Shop Daten an Amazon sendet.

-   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Auswahl zwischen drei primären Methoden zum Senden von Konversionsdaten an Amazon: Amazon Ads Tag (clientseitig), Conversions API (serverseitig) oder eine Kombination aus beiden.
-   **Auswirkung einer Änderung dieser Einstellung:**
    -   *Wenn auf „Amazon Ads Tag (Client-Side)“ eingestellt:* Das Modul verlässt sich hauptsächlich auf den JavaScript-Tag, der im Browser des Kunden platziert ist, um Daten zu senden. Dies ist anfällig für Ad-Blocker.
    -   *Wenn auf „Conversions API (Server-Side)“ eingestellt:* Das Modul sendet Daten direkt von Ihrem PrestaShop-Server an die Server von Amazon. Dies ist zuverlässiger und umgeht Ad-Blocker.
    -   *Wenn auf „Dual Mode (Hybrid)“ eingestellt:* Das Modul sendet Daten sowohl über den Amazon Ads Tag als auch über die Conversions API. Dies bietet maximale Datenresilienz und Genauigkeit.
-   **Empfohlener Wert:** **„Dual Mode (Hybrid)“** für das robusteste und genaueste Tracking. Wenn Sie großen Wert auf den Datenschutz legen und clientseitige Skripte minimieren möchten, ist „Conversions API (Server-Side)“ eine starke Alternative.
-   **Händlerszenario / Beispiel:** Wenn Sie eine Diskrepanz zwischen den von Amazon Ads gemeldeten Konversionen und Ihren tatsächlichen PrestaShop-Verkäufen festgestellt haben, kann das Umschalten auf „Dual Mode“ oder „Conversions API“ die Genauigkeit erheblich verbessern, indem Konversionen wiederhergestellt werden, die durch Ad-Blocker verloren gegangen sind.

#### **Amazon Ads Tag ID**

-   **Was diese Einstellung bewirkt:** Dies ist Ihre eindeutige Kennung, die von Amazon Ads für Ihren Tracking-Tag bereitgestellt wird. Sie teilt Amazon mit, welchem Konto die Konversionsdaten zugeordnet werden sollen.
-   **Auswirkung einer Änderung dieser Einstellung:**
    -   *Wenn eine gültige ID eingegeben wird:* Der Amazon Ads Tag (falls in Ihrem Tracking-Modus aktiviert) sendet Daten korrekt an Ihr Amazon Ads-Konto.
    -   *Wenn leer gelassen oder eine ungültige ID eingegeben wird:* Das clientseitige Tracking funktioniert nicht, und Daten werden nicht über den Tag an Ihr Amazon Ads-Konto gesendet.
-   **Empfohlener Wert:** Ihre spezifische Amazon Ads Tag ID. Diese finden Sie in Ihrem Amazon Ads-Konto unter „Events Manager“ oder „Audiences“.
-   **Händlerszenario / Beispiel:** Sie haben gerade eine neue Amazon Ads-Kampagne eingerichtet. Die Eingabe der korrekten Tag ID hier ist der erste Schritt, um sicherzustellen, dass Ihre Kampagnenleistung verfolgt wird.

#### **Amazon Conversions API Access Token**

-   **Was diese Einstellung bewirkt:** Dies ist ein sicheres Token, das von Amazon Ads bereitgestellt wird und Ihren Server beim Senden von Daten über die Conversions API authentifiziert. Es stellt sicher, dass nur autorisierte Quellen Daten an Ihr Amazon Ads-Konto senden können.
-   **Auswirkung einer Änderung dieser Einstellung:**
    -   *Wenn ein gültiges Token eingegeben wird:* Ihr PrestaShop-Server kann Konversionsdaten sicher direkt über die Conversions API an Amazon senden (falls in Ihrem Tracking-Modus aktiviert).
    -   *Wenn leer gelassen oder ein ungültiges Token eingegeben wird:* Das serverseitige Tracking über die Conversions API funktioniert nicht, und Daten werden nicht über CAPI an Ihr Amazon Ads-Konto gesendet.
-   **Empfohlener Wert:** Ihr spezifisches Amazon Conversions API Access Token. Dieses wird in Ihrem Amazon Ads-Konto generiert, typischerweise unter „Events Manager“ oder „Data Sources“. Behandeln Sie dieses Token wie ein Passwort; bewahren Sie es sicher auf.
-   **Händlerszenario / Beispiel:** Sie möchten die Zuverlässigkeit Ihres Konversionstrackings durch die Verwendung der Conversions API verbessern. Nachdem Sie das Token in Amazon Ads generiert haben, fügen Sie es hier ein, um die serverseitige Datenübertragung zu aktivieren.

#### **Debug-Modus aktivieren**

-   **Was diese Einstellung bewirkt:** Aktiviert einen speziellen Modus, der detaillierte Informationen über die an Amazon gesendeten Daten anzeigt, die nur für Sie (oder jeden, der Entwicklertools geöffnet hat) in der Browserkonsole sichtbar sind. Dies ist für die Fehlerbehebung von unschätzbarem Wert.
-   **Auswirkung einer Änderung dieser Einstellung:**
    -   *Wenn aktiviert:* Sie sehen Konsolenprotokolle und möglicherweise Bildschirmüberlagerungen (abhängig von der spezifischen Debug-Implementierung), die zeigen, welche Ereignisse ausgelöst werden und welche Daten an Amazon gesendet werden. Dies ist für normale Kunden nicht sichtbar.
    -   *Wenn deaktiviert:* Es werden keine Debug-Informationen angezeigt.
-   **Empfohlener Wert:** **„NEIN“** für Live-Produktionsshops. Nur vorübergehend beim Einrichten oder bei der Fehlerbehebung aktivieren.
-   **Händlerszenario / Beispiel:** Sie haben das Modul konfiguriert, aber Konversionen werden nicht in Ihrem Amazon Ads-Konto angezeigt. Das Aktivieren des Debug-Modus kann Ihnen helfen zu sehen, ob die Ereignisse auf Ihrer Website korrekt ausgelöst werden und ob die Datenlast korrekt aussieht.

#### **Integration des Zustimmungsmanagements**

-   **Was diese Einstellung bewirkt:** Ermöglicht dem Modul die Integration mit der Cookie-Zustimmungslösung Ihres Shops. Dies stellt sicher, dass das Amazon Ads Tracking nur aktiviert wird, nachdem ein Kunde seine ausdrückliche Zustimmung gegeben hat, und entspricht so Datenschutzbestimmungen wie der DSGVO oder CCPA.
-   **Auswirkung einer Änderung dieser Einstellung:**
    -   *Wenn aktiviert und in ein Zustimmungsmodul integriert:* Der Amazon Ads Tag (clientseitig) wird nur geladen und löst Ereignisse aus, wenn der Kunde Tracking-Cookies akzeptiert hat. Serverseitige CAPI kann weiterhin anonymisierte Daten senden oder auf die Zustimmung warten, abhängig von Ihrer spezifischen Einrichtung und Ihren Datenschutzrichtlinien.
    -   *Wenn deaktiviert:* Das Modul versucht, Ereignisse ohne explizite Zustimmungsprüfungen zu verfolgen, was in bestimmten Regionen möglicherweise nicht den Datenschutzgesetzen entspricht.
-   **Empfohlener Wert:** **„JA“**, wenn Ihr Shop in Regionen mit strengen Datenschutzgesetzen (z. B. EU, Kalifornien) tätig ist und Sie ein Cookie-Zustimmungsmodul verwenden.
-   **Händlerszenario / Beispiel:** Ihr Shop bedient Kunden in Europa, und Sie verwenden ein DSGVO-konformes Cookie-Banner. Das Aktivieren dieser Einstellung stellt sicher, dass Ihr Amazon Ads Tracking die Datenschutzentscheidungen der Kunden respektiert.

#### **Erweiterte Einstellungen (z. B. Data Layer, Event Mapping, Produkt-ID-Auflösung)**

Das Modul kann erweiterte Einstellungen enthalten, die eine Feinabstimmung der Datenerfassung und -übertragung ermöglichen. Diese sind typischerweise für technisch versiertere Benutzer oder spezifische Szenarien gedacht.

-   **Data Layer Tracking:**
    -   **Was diese Einstellung bewirkt:** Bestimmt, ob das Modul einen standardisierten „Data Layer“ verwenden soll, um Informationen aus Ihrem Shop zu sammeln. Dies wird oft für die Kompatibilität mit anderen Tracking-Tools oder benutzerdefinierten Implementierungen verwendet.
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Das Modul sucht nach einem `dataLayer` JavaScript-Objekt und pusht Daten dorthin, was für das Debugging oder die Integration mit Google Tag Manager nützlich sein kann.
        -   *Wenn deaktiviert:* Das Modul sammelt Daten direkt aus den internen Variablen von PrestaShop.
    -   **Empfohlener Wert:** **„JA“**, wenn Sie Google Tag Manager oder andere Tools verwenden, die auf einem Data Layer basieren. Andernfalls ist „NEIN“ in der Regel in Ordnung.
-   **Event Mapping:**
    -   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Anpassung, wie bestimmte PrestaShop-Aktionen (z. B. „In den Warenkorb legen“) Amazon Ads-Ereignisnamen zugeordnet werden.
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Wenn angepasst:* Sie können andere Ereignisnamen an Amazon senden als die Standardeinstellung des Moduls, was für bestimmte Amazon Ads-Kampagneneinstellungen nützlich sein kann.
        -   *Wenn Standard:* Das Modul verwendet seine vordefinierte Zuordnung.
    -   **Empfohlener Wert:** Belassen Sie die Standardeinstellung, es sei denn, Sie haben einen spezifischen Grund, sie basierend auf der Amazon Ads-Dokumentation zu ändern.
-   **Produkt-ID-Auflösung:**
    -   **Was diese Einstellung bewirkt:** Definiert, welche Produktkennung (z. B. Produkt-ID, EAN, UPC, SKU) das Modul für produktbezogene Ereignisse an Amazon senden soll.
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Wenn auf Produkt-ID eingestellt:* Amazon erhält die interne Produkt-ID von PrestaShop.
        -   *Wenn auf EAN/UPC/SKU eingestellt:* Amazon erhält die entsprechende Produktkennung. Dies ist entscheidend für den Abgleich von Produkten in Ihrem Amazon-Produktkatalog.
    -   **Empfohlener Wert:** Wählen Sie die Kennung, die am konsistentesten mit den Produkt-IDs übereinstimmt, die Sie in Ihren Amazon-Produktfeeds oder Ihrem Katalog verwenden. **EAN/UPC** wird oft für Einzelhandelsprodukte bevorzugt.
-   **Linker-Domains:**
    -   **Was diese Einstellung bewirkt:** Gibt zusätzliche Domains an, die in das Cross-Domain-Tracking einbezogen werden sollen. Dies ist wichtig, wenn Ihr Checkout-Prozess oder andere Teile Ihrer Customer Journey mehrere Domains umfassen (z. B. eine separate Subdomain für einen Blog oder ein Zahlungs-Gateway, das weiterleitet).
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Wenn konfiguriert:* Der Amazon Ads Tag kann die Tracking-Kontinuität über verschiedene Domains hinweg aufrechterhalten und den Verlust der Attribution verhindern.
        -   *Wenn nicht für mehrere Domains konfiguriert:* Konversionen können falsch zugeordnet oder verloren gehen, wenn der Kunde während seiner Reise zwischen Domains navigiert.
    -   **Empfohlener Wert:** Fügen Sie alle Domains oder Subdomains hinzu, die Teil der Customer Journey sind.
-   **Währungshilfe:**
    -   **Was diese Einstellung bewirkt:** Stellt sicher, dass die an Amazon gesendeten Währungswerte korrekt formatiert sind und mit der in Ihrem Amazon Ads-Konto verwendeten Währung übereinstimmen.
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Wenn korrekt konfiguriert:* Amazon erhält genaue Währungswerte.
        -   *Wenn falsch konfiguriert:* Währungswerte können von Amazon falsch interpretiert werden, was zu falschen Berichten führt.
    -   **Empfohlener Wert:** Stellen Sie sicher, dass dies mit der primären Währung Ihres Shops und der Währung Ihres Amazon Ads-Kontos übereinstimmt.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Das Modul bietet mehrere dedizierte Bildschirme, die Ihnen helfen, Ihr Amazon Ads Tracking zu überwachen und zu optimieren. Diese sind typischerweise über Registerkarten oder Unterabschnitte innerhalb der Hauptmodulkonfiguration zugänglich.

#### **4.2.1 Live-Statistiken**

-   **Bildschirmname & Menüpfad:** Normalerweise eine Registerkarte innerhalb der Hauptmodulkonfiguration (z. B. „Live-Statistiken“).
-   **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm zeigt Echtzeit- oder nahezu Echtzeitdaten über die an Amazon gesendeten Ereignisse an. Er kann anzeigen:
    -   Aktuelle Ereignisse (z. B. PageView, AddToCart, Purchase) mit Zeitstempeln.
    -   Ereignistypen und deren Häufigkeit.
    -   Datenqualitätswerte.
    -   Visualisierungen der Tracking-Aktivität.
-   **Auswirkung von Änderungen:** Dies ist ein Berichts-Bildschirm; es gibt hier keine direkten Einstellungen zu ändern. Er spiegelt die gesendeten Daten basierend auf Ihrer Hauptkonfiguration wider.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Überprüfen Sie diesen Bildschirm regelmäßig, um sicherzustellen, dass Ereignisse wie erwartet ausgelöst werden, insbesondere nach Änderungen an Ihrem Shop oder dem Start neuer Kampagnen. Es ist Ihre erste Verteidigungslinie zur Identifizierung von Tracking-Problemen.

#### **4.2.2 Health Score & Recovery Radar**

-   **Bildschirmname & Menüpfad:** Oft eine Registerkarte innerhalb der Hauptmodulkonfiguration (z. B. „Health Score“ oder „Diagnose“).
-   **Verfügbare Aktionen & Einstellungen:** Dieser Abschnitt bietet einen Gesamt-Health Score für Ihr Amazon Ads Tracking und identifiziert potenzielle Probleme oder „verlorene“ Konversionen. Er kann enthalten:
    -   Einen prozentualen Wert, der die Tracking-Gesundheit angibt.
    -   Empfehlungen zur Verbesserung der Datenqualität.
    -   Ein „Recovery Radar“, das geschätzte Konversionen anzeigt, die aufgrund von Ad-Blockern oder anderen Problemen möglicherweise verpasst wurden, und wie CAPI hilft, diese wiederherzustellen.
    -   Warnungen zu fehlenden Tag IDs, Access Tokens oder Zustimmungsproblemen.
-   **Auswirkung von Änderungen:** Wie bei den Live-Statistiken ist dies hauptsächlich ein Berichts- und Diagnosebildschirm. Maßnahmen, die Sie aufgrund seiner Empfehlungen ergreifen (z. B. Aktualisieren einer fehlenden Tag ID), verbessern Ihr Tracking.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Überprüfen Sie regelmäßig Ihren Health Score. Ein niedriger Wert oder ein aktiver „Recovery Radar“ weist auf Bereiche hin, in denen Ihr Tracking verbessert werden könnte, was potenziell zu einer besseren Anzeigenleistung führt.

#### **4.2.3 Data Quality Coach / Catalog Doctor**

-   **Bildschirmname & Menüpfad:** Potenziell eine Registerkarte innerhalb der Hauptmodulkonfiguration (z. B. „Datenqualität“ oder „Katalog-Doktor“).
-   **Verfügbare Aktionen & Einstellungen:** Diese Tools helfen Ihnen sicherzustellen, dass die Daten, die Sie an Amazon senden, von hoher Qualität und korrekt formatiert sind. Sie können:
    -   Nach häufigen Datenproblemen suchen (z. B. fehlende Produkt-IDs, falsche Währungsformate).
    -   Vorschläge zur Verbesserung Ihrer Produktkatalogdaten machen, um den Anforderungen von Amazon besser zu entsprechen.
    -   Diskrepanzen zwischen clientseitigen und serverseitigen Daten hervorheben.
-   **Auswirkung von Änderungen:** Dieser Bildschirm bietet umsetzbare Erkenntnisse. Die Behebung der hier hervorgehobenen Probleme (z. B. Aktualisieren von Produkt-EANs in Ihrem PrestaShop-Katalog) verbessert direkt die Qualität und die Abgleichmöglichkeiten Ihrer Konversionsdaten in Amazon Ads.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Wenn Sie Probleme mit dem Produktabgleich in Amazon Ads haben oder Warnungen in Ihrem Health Score sehen, konsultieren Sie diese Tools, um Ihre Daten zu verfeinern.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Hauptkonfiguration | **Tracking-Modus** | Dual-Modus (Hybrid) | Bestimmt, ob das Tracking clientseitig, serverseitig oder beides ist. Der Dual-Modus bietet maximale Widerstandsfähigkeit. |
| Hauptkonfiguration | **Amazon Ads Tag ID** | Ihre Amazon Tag ID | Wesentlich für clientseitiges Tracking. Verknüpft Daten mit Ihrem Amazon Ads-Konto. |
| Hauptkonfiguration | **Amazon Conversions API Access Token** | Ihr CAPI Access Token | Wesentlich für serverseitiges Tracking. Authentifiziert Ihren Server bei Amazon. |
| Hauptkonfiguration | **Debug-Modus aktivieren** | NEIN | Zeigt Tracking-Daten in der Browserkonsole zur Fehlerbehebung an. Auf Live-Shops deaktivieren. |
| Hauptkonfiguration | **Integration des Zustimmungsmanagements** | JA (falls zutreffend) | Stellt sicher, dass das Tracking die Privatsphäre der Kunden und die Cookie-Zustimmung respektiert. |
| Hauptkonfiguration | **Data Layer Tracking** | JA (bei Verwendung von GTM) | Verwendet einen Data Layer zur Ereigniserfassung, nützlich für GTM oder benutzerdefinierte Integrationen. |
| Hauptkonfiguration | **Produkt-ID-Auflösung** | EAN/UPC | Definiert, welche Produktkennung an Amazon zum Abgleich gesendet wird. Entscheidend für den Katalogabgleich. |
| Hauptkonfiguration | **Linker-Domains** | Leer (bei Bedarf hinzufügen) | Behält das Tracking über mehrere Domains in Ihrer Customer Journey bei. |
| Live-Statistiken | (Nur Berichterstattung) | N/A | Zeigt Echtzeit-Ereignisdaten an und hilft Ihnen zu überprüfen, ob das Tracking aktiv ist. |
| Health Score | (Nur Berichterstattung) | N/A | Bietet eine Gesamtbewertung der Tracking-Gesundheit und identifiziert Probleme. |
| Datenqualität | (Nur Berichterstattung) | N/A | Hilft, Datenqualitätsprobleme in Ihrem Produktkatalog für einen besseren Amazon-Abgleich zu identifizieren und zu beheben. |

## 3. Fehlerbehebung für Händler & Häufig gestellte Fragen (FAQ)

**F1: Meine Amazon Ads-Konversionen stimmen nicht mit meinen PrestaShop-Verkäufen überein. Was soll ich tun?**
A1: Dies ist ein häufiges Problem, oft aufgrund von Ad-Blockern.
\* **Tracking-Modus überprüfen:** Stellen Sie sicher, dass Sie in den Moduleinstellungen „Dual-Modus (Hybrid)“ oder „Conversions API (Server-Side)“ verwenden. Dies ist der effektivste Weg, verlorene Konversionen wiederherzustellen.
\* **IDs/Tokens überprüfen:** Überprüfen Sie nochmals, ob Ihre Amazon Ads Tag ID und Ihr Conversions API Access Token korrekt in der Modulkonfiguration eingegeben wurden.
\* **Debug-Modus verwenden:** Aktivieren Sie vorübergehend den „Debug-Modus“ und führen Sie einen Testkauf durch. Überprüfen Sie Ihre Browserkonsole und die „Live-Statistiken“ des Moduls, um zu sehen, ob Ereignisse ausgelöst werden.
\* **Cache leeren:** Gehen Sie in Ihrem PrestaShop-Back Office zu **Erweiterte Parameter > Leistung** und leeren Sie den Smarty-Cache und andere Caches. Manchmal kann alter Modulcode bestehen bleiben.

**F2: Ich sehe Warnungen zu „Datenqualität“ oder „Fehlenden Produkt-IDs“ im Health Score des Moduls. Wie behebe ich das?**
A2: Amazon ist auf hochwertige Produktdaten für einen genauen Abgleich angewiesen.
\* **Produkt-ID-Auflösung:** Stellen Sie in der Modulkonfiguration sicher, dass Ihre Einstellung „Produkt-ID-Auflösung“ (z. B. EAN, UPC, SKU) mit der primären Kennung übereinstimmt, die in Ihrem Amazon-Produktfeed verwendet wird.
\* **Produktdaten aktualisieren:** Gehen Sie in Ihrem PrestaShop-Back Office zu **Katalog > Produkte**. Bearbeiten Sie die vom „Datenqualitäts-Coach“ gekennzeichneten Produkte und stellen Sie sicher, dass sie vollständige und genaue EANs, UPCs oder SKUs enthalten, wie erforderlich.
\* **Konsistenz:** Stellen Sie sicher, dass die Produktkennungen in Ihrem PrestaShop-Shop mit denen übereinstimmen, die Sie Amazon in Ihren Produktfeeds bereitstellen.

**F3: Meine Website verwendet ein Cookie-Zustimmungsbanner. Wird dieses Modul die Kundenentscheidungen respektieren?**
A3: Ja, wenn korrekt konfiguriert.
\* **Zustimmungsintegration aktivieren:** Stellen Sie in der Modulkonfiguration sicher, dass „Integration des Zustimmungsmanagements“ aktiviert ist.
\* **Kompatibilität mit Cookie-Modulen:** Dieses Modul ist so konzipiert, dass es sich in Standard-PrestaShop-Cookie-Zustimmungsmodule integriert. Wenn Sie eine benutzerdefinierte Lösung verwenden, müssen Sie möglicherweise sicherstellen, dass sie die `prestashop.on('updateProduct', ...)` oder ähnliche Ereignisse, auf die Module bei Zustimmungsänderungen hören, korrekt auslöst.
\* **CAPI vs. Tag:** Denken Sie daran, dass die Conversions API (serverseitig) weniger von clientseitigen Zustimmungsbannern betroffen ist als der Amazon Ads Tag (clientseitig), da sie Daten direkt von Ihrem Server sendet. Es ist jedoch immer noch Best Practice, persönlich identifizierbare Informationen (PII) nur nach Zustimmung über CAPI zu senden.

**F4: Das Modul scheint meine Website zu verlangsamen. Was kann ich tun?**
A4: Dieses Modul ist auf Leistung optimiert, aber hier sind einige Überprüfungen:
\* **Debug-Modus deaktivieren:** Stellen Sie sicher, dass der „Debug-Modus“ in Ihrem Live-Shop deaktiviert ist, da er zusätzliche Konsolenprotokollierung hinzufügt.
\* **Serverleistung:** Die Conversions API (CAPI) führt Server-zu-Server-Aufrufe durch. Obwohl sie im Allgemeinen schnell sind, stellen Sie sicher, dass Ihr Hosting-Server über ausreichende Ressourcen und eine stabile Internetverbindung verfügt.
\* **Andere Module:** Überprüfen Sie, ob andere ressourcenintensive Tracking- oder Werbemodule gleichzeitig ausgeführt werden. Zu viele clientseitige Skripte können die Leistung beeinträchtigen.
\* **Cache leeren:** Leeren Sie immer den PrestaShop-Cache, nachdem Sie Konfigurationsänderungen vorgenommen haben.

**F5: Ich erhalte eine Fehlermeldung, wenn ich versuche, die Modulkonfiguration zu speichern.**
A5:
\* **Berechtigungen überprüfen:** Stellen Sie sicher, dass der Modulordner (`/modules/myamazon/`) und seine Unterordner die richtigen Schreibberechtigungen haben (normalerweise 755 für Ordner, 644 für Dateien).
\* **Serverprotokolle:** Überprüfen Sie die PHP-Fehlerprotokolle Ihres Servers auf detailliertere Informationen zum Fehler. Dies kann oft in Ihrem Hosting-Kontrollpanel gefunden oder durch Kontaktaufnahme mit Ihrem Host erfragt werden.
\* **PrestaShop Debug-Modus:** Aktivieren Sie vorübergehend den PrestaShop-Debug-Modus (ändern Sie in `config/defines.inc.php` `define('_PS_MODE_DEV_', false);` in `define('_PS_MODE_DEV_', true);`), um detailliertere Fehlermeldungen auf dem Bildschirm anzuzeigen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen tiefen Einblick in die technische Struktur des Moduls „Amazon Ads Tag Conversions API“, der für Entwickler und Webmaster gedacht ist.

### 4.1 Architekturübersicht

Das Modul `myamazon` ist nach dem MVC-Muster (Model-View-Controller) von PrestaShop aufgebaut, mit einem starken Fokus auf Modularität und ereignisgesteuertes Tracking. Es nutzt sowohl clientseitige (Amazon Ads Tag) als auch serverseitige (Conversions API) Mechanismen, oft in einem hybriden Ansatz.

Wichtige Architekturkomponenten:

-   **Hauptmodulklasse (`myamazon/index.php`):** Verwaltet Installation, Deinstallation, Hook-Registrierung und die primäre `getContent()`-Methode für die Back-Office-Konfiguration.
-   **Controller:** Dedizierte Front-Controller für AJAX-Interaktionen und Admin-Controller zur Verwaltung von Moduleinstellungen und Diagnoseansichten.
-   **Kernklassen (`classes/`):** Eine robuste Reihe von Klassen verwaltet verschiedene Aspekte:
    -   **Tracking-Logik:** `MyamazonAatTracker.php` (clientseitig), `MyamazonCapiTracker.php` (serverseitig), `MyamazonHybridTracker.php` (Dual-Modus), `MyamazonTrackerFactory.php` (instanziiert Tracker).
    -   **Datenverarbeitung:** `MyamazonUserData.php` (Kundendaten), `MyamazonEventMap.php` (Ereignisübersetzung), `MyamazonProductIdResolver.php` (Produkt-ID-Logik), `MyamazonCurrencyHelper.php`.
    -   **API-Client:** `MyamazonCapiClient.php` (handhabt die Kommunikation mit der Amazon CAPI).
    -   **Diagnose & Gesundheit:** `MyamazonHealthScore.php`, `MyamazonCatalogDoctor.php`, `MyamazonDataQualityCoach.php`, `MyamazonLiveStats.php`.
    -   **Zustimmung:** `MyamazonConsent.php` (integriert sich in Zustimmungsmechanismen).
-   **Hooks:** Umfangreiche Nutzung von PrestaShop-Hooks, um JavaScript einzufügen, Ereignisse zu erfassen und Daten an kritischen Punkten der Customer Journey zu senden.
-   **Smarty-Templates:** Werden zum Rendern von Back-Office-Konfigurationsansichten und Front-Office-Tracking-Skripten verwendet.
-   **JavaScript:** Verwaltet clientseitige Tag-Injektion, Ereignisüberwachung und Data-Layer-Interaktionen.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

-   `controllers/front/ajax.php`
    -   **Klassenname:** `MyamazonAjaxModuleFrontController` (erweitert `ModuleFrontController`)
    -   **Verantwortlichkeit:** Behandelt asynchrone (AJAX) Anfragen vom Front-Office. Dies wird typischerweise für serverseitige Ereignissendungen über CAPI verwendet, die nicht direkt im Browser durchgeführt werden können (z. B. Post-Purchase-Ereignisse, bei denen der Browser möglicherweise geschlossen ist, oder Ereignisse, die eine serverseitige Datenverarbeitung erfordern). Es empfängt Daten von clientseitigem JavaScript und leitet sie an den `MyamazonCapiTracker` weiter.
-   `controllers/front/index.php`
    -   **Klassenname:** `MyamazonIndexModuleFrontController` (erweitert `ModuleFrontController`)
    -   **Verantwortlichkeit:** Dieser Controller könnte als Fallback oder einfacher Einstiegspunkt dienen, obwohl sein primärer Anwendungsfall minimal sein könnte, wenn `ajax.php` die meisten Front-End-Interaktionen abwickelt. Er könnte für spezifische Weiterleitungen oder einfache Datenanzeigen verwendet werden, dient aber oft als Platzhalter.

#### Back-Office-Admin-Controller

-   `controllers/admin/AdminMyamazonAjaxController.php`
    -   **Klassenname:** `AdminMyamazonAjaxController` (erweitert `ModuleAdminController`)
    -   **Tab-Name:** Nicht direkt ein Menü-Tab, sondern ein AJAX-Endpunkt für die Admin-Oberfläche.
    -   **Verantwortlichkeit:** Behandelt AJAX-Anfragen, die von den Back-Office-Konfigurationsseiten des Moduls stammen. Dies umfasst das Abrufen von Daten für Live-Statistiken, Health Scores oder die Durchführung von Hintergrundprüfungen (z. B. API-Token-Validierung) ohne Neuladen der gesamten Seite. Es interagiert mit Klassen wie `MyamazonLiveStats`, `MyamazonHealthScore` und `MyamazonCapiClient`.
-   `controllers/admin/index.php`
    -   **Klassenname:** `AdminMyamazonIndexController` (erweitert `ModuleAdminController`)
    -   **Tab-Name:** Kein direkter Menü-Tab.
    -   **Verantwortlichkeit:** Ähnlich wie der Front-Office `index.php` könnte dies ein Platzhalter sein oder sehr spezifische, nicht-AJAX-Admin-Interaktionen behandeln. Die primäre Konfigurationslogik befindet sich in der `getContent()`-Methode des Hauptmoduls.

### 4.3 Kernklassen & Modelle (`classes/`)

-   `classes/autoload.php`: Standard-PrestaShop-Autoload-Datei.
-   `classes/index.php`: Platzhalterdatei, üblich in leeren Verzeichnissen.
-   `classes/MyamazonAatTracker.php`:
    -   **Verantwortlichkeit:** Implementiert die Logik für clientseitiges Amazon Ads Tag Tracking. Generiert das notwendige JavaScript für `aa.js` und pusht Ereignisse in den Data Layer des Browsers oder direkt an den Amazon Ads Tag.
-   `classes/MyamazonCapiClient.php`:
    -   **Verantwortlichkeit:** Handhabt die eigentlichen HTTP-Anfragen an die Conversions API-Endpunkte von Amazon. Kapselt cURL- oder Guzzle-Logik (falls verwendet), Authentifizierung mit dem Access Token und Fehlerbehandlung für die Server-zu-Server-Kommunikation.
-   `classes/MyamazonCapiTracker.php`:
    -   **Verantwortlichkeit:** Implementiert die Logik für serverseitiges Conversions API Tracking. Formatiert Ereignisdaten gemäß den CAPI-Spezifikationen von Amazon und verwendet `MyamazonCapiClient`, um sie zu senden.
-   `classes/MyamazonCatalogDoctor.php`:
    -   **Verantwortlichkeit:** Analysiert die Produktdaten des Shops auf potenzielle Probleme, die den Amazon-Produktabgleich beeinträchtigen könnten (z. B. fehlende EANs, falsche SKUs). Bietet diagnostisches Feedback für die Admin-Oberfläche.
-   `classes/MyamazonConsent.php`:
    -   **Verantwortlichkeit:** Verwaltet die Integration der Cookie-Zustimmung. Überprüft den Zustimmungsstatus des Kunden und aktiviert/deaktiviert clientseitige Tracking-Skripte bedingt. Integriert sich in das PrestaShop-Ereignis `prestashop.on('updateProduct', ...)` für Zustimmungsänderungen.
-   `classes/MyamazonCurrencyHelper.php`:
    -   **Verantwortlichkeit:** Bietet Dienstprogramm-Methoden zum korrekten Formatieren von Währungswerten für Amazon Ads, zur Handhabung von Dezimalstellen und Währungscodes.
-   `classes/MyamazonDataLayerTracker.php`:
    -   **Verantwortlichkeit:** Verwaltet das Pushen von Ereignisdaten an ein JavaScript `dataLayer`-Objekt, das oft für die Kompatibilität mit Google Tag Manager oder anderen Data-Layer-Konsumenten verwendet wird.
-   `classes/MyamazonDataQualityCoach.php`:
    -   **Verantwortlichkeit:** Bietet Einblicke und Empfehlungen zur Verbesserung der Gesamtqualität der an Amazon gesendeten Daten, die Aspekte über die Produkt-IDs hinaus abdecken.
-   `classes/MyamazonEventId.php`:
    -   **Verantwortlichkeit:** Generiert eindeutige Ereignis-IDs für jedes Ereignis, entscheidend für die Deduplizierung bei der Verwendung von Dual-Modus-Tracking (stellt sicher, dass Amazon dasselbe Ereignis nicht zweimal zählt, von clientseitig und serverseitig).
-   `classes/MyamazonEventMap.php`:
    -   **Verantwortlichkeit:** Definiert die Zuordnung zwischen den internen Ereignissen von PrestaShop (z. B. `actionCartSave`) und den Standard-Ereignisnamen von Amazon Ads (z. B. `AddToCart`). Ermöglicht die Anpassung dieser Zuordnungen.
-   `classes/MyamazonEvents.php`:
    -   **Verantwortlichkeit:** Eine zentrale Klasse oder Sammlung von Methoden zum Auslösen und Verwalten verschiedener Amazon Ads-Ereignisse (z. B. `PageView`, `ViewContent`, `AddToCart`, `Purchase`).
-   `classes/MyamazonHealthScore.php`:
    -   **Verantwortlichkeit:** Berechnet und präsentiert einen Gesamt-„Health Score“ für das Tracking des Moduls, identifiziert Konfigurationsprobleme, fehlende Daten oder potenzielle Tracking-Lücken.
-   `classes/MyamazonHybridTracker.php`:
    -   **Verantwortlichkeit:** Orchestriert das Dual-Modus-Tracking, indem `MyamazonAatTracker` und `MyamazonCapiTracker` kombiniert werden, um Ereignisse sowohl über clientseitige als auch serverseitige Methoden zu senden und die Deduplizierung zu handhaben.
-   `classes/MyamazonLiveStats.php`:
    -   **Verantwortlichkeit:** Sammelt und verarbeitet Echtzeit- oder nahezu Echtzeit-Ereignisdaten zur Anzeige in der Back-Office-Ansicht „Live-Statistiken“.
-   `classes/MyamazonProductIdResolver.php`:
    -   **Verantwortlichkeit:** Bestimmt, welche Produktkennung (ID, EAN, UPC, SKU) beim Senden von Produktdaten an Amazon verwendet werden soll, basierend auf der Modulkonfiguration.
-   `classes/MyamazonPropertyRules.php`:
    -   **Verantwortlichkeit:** Definiert Regeln und Validierungen für Ereigniseigenschaften, um sicherzustellen, dass die an Amazon gesendeten Daten deren API-Spezifikationen entsprechen.
-   `classes/MyamazonTrackerFactory.php`:
    -   **Verantwortlichkeit:** Eine Factory-Pattern-Klasse, die für die Instanziierung des korrekten Trackers (`AatTracker`, `CapiTracker` oder `HybridTracker`) basierend auf der Modulkonfiguration verantwortlich ist.
-   `classes/MyamazonTrackerInterface.php`:
    -   **Verantwortlichkeit:** Definiert eine gemeinsame Schnittstelle für alle Tracker-Klassen (`AatTracker`, `CapiTracker`, `HybridTracker`), um sicherzustellen, dass sie einen konsistenten Satz von Methoden für das Ereignis-Tracking implementieren.
-   `classes/MyamazonUserData.php`:
    -   **Verantwortlichkeit:** Sammelt und formatiert kundenbezogene Daten (z. B. E-Mail, Telefon, Adresse) zur Aufnahme in Amazon Ads-Ereignisse, insbesondere für die Conversions API, wo PII gehasht und gesendet werden kann.

### 4.4 JavaScript-Assets (`views/js/`)

-   `views/js/myamazon-admin.js`:
    -   **Geltungsbereich:** Back-Office.
    -   **Details:** Handhabt interaktive Elemente auf den Konfigurationsseiten des Moduls, wie z. B. Tab-Wechsel, AJAX-Aufrufe für Live-Statistiken, Formularvalidierung und dynamische Updates von Diagnosetools.
-   `views/js/myamazon-debug.js`:
    -   **Geltungsbereich:** Front-Office (wird bedingt geladen, wenn der Debug-Modus aktiv ist).
    -   **Details:** Bietet ausführliche Protokollierung in der Browserkonsole, zeigt die ausgelösten Ereignisse, die Daten-Payloads und den Status der Amazon Ads Tag- und CAPI-Aufrufe an. Kann visuelle Überlagerungen für schnelles Debugging enthalten.
-   `views/js/myamazon-ghost.js`:
    -   **Geltungsbereich:** Front-Office.
    -   **Details:** Wahrscheinlich im Zusammenhang mit „Ghost“- oder Hintergrund-Tracking-Mechanismen, möglicherweise zum Erfassen von Ereignissen, die sonst übersehen werden könnten, oder für spezifische zustimmungsbezogene Verzögerungen.
-   `views/js/myamazon-live.js`:
    -   **Geltungsbereich:** Back-Office.
    -   **Details:** Treibt das „Live-Statistiken“-Dashboard an, indem es AJAX-Anfragen an `AdminMyamazonAjaxController` sendet, um Echtzeit-Ereignisdaten abzurufen und anzuzeigen.
-   `views/js/myamazon-tcf.js`:
    -   **Geltungsbereich:** Front-Office.
    -   **Details:** Integriert sich in TCF (Transparency and Consent Framework)-konforme Cookie-Zustimmungslösungen, um sicherzustellen, dass clientseitiges Tracking den Benutzerzustimmungspräferenzen entspricht.
-   `views/js/myamazon-wizard.js`:
    -   **Geltungsbereich:** Back-Office.
    -   **Details:** Bietet interaktive Schritte für den anfänglichen Einrichtungsassistenten, der den Händler durch die wesentliche Konfiguration führt.
-   `views/js/myamazon.js`:
    -   **Geltungsbereich:** Front-Office.
    -   **Details:** Das Haupt-Client-Side-JavaScript für das Modul. Es injiziert den Amazon Ads Tag (`aa.js`), lauscht auf verschiedene DOM-Ereignisse (z. B. `click` auf In-den-Warenkorb-Buttons), erfasst Daten von der Seite, pusht Ereignisse in den Data Layer und führt möglicherweise AJAX-Aufrufe an `MyamazonAjaxModuleFrontController` für die serverseitige Verarbeitung durch. Es handhabt auch die Logik zur Ereignis-Deduplizierung.

### 4.5 CSS-Stylesheets (`views/css/`)

-   `myamazon/opis/sugestie/style1.css`, `myamazon/opis/sugestie/style2.css`, `myamazon/opis/sugestie/sugestie/style1.css`, `myamazon/opis/sugestie/sugestie/style2.css`, `myamazon/opis/sugestie/sugestie/tailwind-new-7.css`, `myamazon/opis/sugestie/tailwind-new-7.css`:
    -   **Geltungsbereich:** Back-Office.
    -   **Details:** Diese Dateien scheinen sich auf ein benutzerdefiniertes UI-Framework oder Styling für Vorschläge/Hinweise innerhalb der Back-Office-Konfiguration zu beziehen, möglicherweise für eine geführte Einrichtung oder diagnostisches Feedback. `tailwind-new-7.css` deutet auf die Verwendung von Tailwind CSS für Utility-First-Styling hin.
-   `views/css/myamazon-admin.css`:
    -   **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
    -   **Details:** Bietet spezifisches Styling für die Konfigurationsformulare, Registerkarten, Diagnosepanels und andere benutzerdefinierte UI-Elemente des Moduls innerhalb des PrestaShop-Back Office.
-   `views/css/myamazon-debug.css`:
    -   **Geltungsbereich:** Front-Office (wird bedingt geladen).
    -   **Details:** Stile für die Debug-Überlagerung oder Konsolenmeldungen, um sicherzustellen, dass sie lesbar und deutlich sind, wenn der Debug-Modus aktiv ist.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

-   `views/templates/hook/capi-pageview.tpl`:
    -   **Hook:** `displayHeader` (oder ähnlich).
    -   **Ausgabe:** Injiziert serverseitige (CAPI) PageView-Ereignisdaten, potenziell als verstecktes Eingabefeld oder JavaScript-Variable, die vom `ajax.php`-Controller zur serverseitigen Übertragung aufgenommen werden.
-   `views/templates/hook/debug.tpl`:
    -   **Hook:** `displayHeader` (bedingt).
    -   **Ausgabe:** Injiziert das Skript `myamazon-debug.js` und alle notwendigen anfänglichen Debug-Variablen, wenn der Debug-Modus aktiviert ist.
-   `views/templates/hook/displayOrderConfirmation.tpl`:
    -   **Hook:** `displayOrderConfirmation`.
    -   **Ausgabe:** Rendert die kritischen „Purchase“-Ereignisdaten, einschließlich Bestelldetails, Produkten und Kundeninformationen, sowohl für die clientseitige Tag- als auch für die serverseitige CAPI-Übertragung. Hier wird der Konversionswert erfasst.
-   `views/templates/hook/ghost.tpl`:
    -   **Hook:** `displayHeader` (oder ähnlich).
    -   **Ausgabe:** Bezogen auf den „Ghost“-Tracking-Mechanismus, möglicherweise für verzögertes Laden oder spezifische zustimmungsbezogene Logik.
-   `views/templates/hook/header.tpl`:
    -   **Hook:** `displayHeader`.
    -   **Ausgabe:** Das primäre Template zum Einfügen des Amazon Ads Tags (`aa.js`-Skript), `myamazon.js` und anfänglicher Konfigurationsvariablen in den `<head>`-Bereich jeder Seite.
-   `views/templates/hook/payment.tpl`:
    -   **Hook:** `displayPaymentTop` (oder ähnlich).
    -   **Ausgabe:** Kann verwendet werden, um „InitiateCheckout“ oder andere zahlungsbezogene Ereignisse vor der endgültigen Bestellbestätigung zu verfolgen.
-   `views/templates/hook/product-details.tpl`:
    -   **Hook:** `displayProductButtons` oder `displayProductExtraContent`.
    -   **Ausgabe:** Injiziert JavaScript, um „ViewContent“-Ereignisse zu verfolgen, wenn eine Produktseite geladen wird, und erfasst produktspezifische Daten.

#### Admin-Templates (`views/templates/admin/`)

-   `views/templates/admin/consent-guide.tpl`: Zeigt Anleitungen zur Integration mit Cookie-Zustimmungsmodulen an.
-   `views/templates/admin/doctor.tpl`: Rendert die Diagnoseansicht „Katalog-Doktor“, die Probleme mit Produktdaten anzeigt.
-   `views/templates/admin/dq.tpl`: Rendert die Ansicht „Datenqualitäts-Coach“, die Einblicke in die Datenqualität bietet.
-   `views/templates/admin/health.tpl`: Zeigt den Gesamt-„Health Score“ und verwandte Diagnosen an.
-   `views/templates/admin/linker-domains.tpl`: Rendert das Eingabefeld zur Konfiguration von Linker-Domains.
-   `views/templates/admin/live-maintain.tpl`: Möglicherweise eine Wartungsansicht für Live-Statistiken.
-   `views/templates/admin/live.tpl`: Rendert das „Live-Statistiken“-Dashboard.
-   `views/templates/admin/mode-context.tpl`, `views/templates/admin/mode-note-aat.tpl`, `views/templates/admin/mode-note-both.tpl`, `views/templates/admin/mode-note-capi.tpl`, `views/templates/admin/mode-note-datalayer.tpl`, `views/templates/admin/mode-picker.tpl`: Diese Templates werden für den Abschnitt „Tracking-Modus-Auswahl“ verwendet und bieten Erklärungen sowie den Radiobutton/Dropdown zur Auswahl der Tracking-Methode.
-   `views/templates/admin/properties-list.tpl`: Zeigt eine Liste von Ereigniseigenschaften und deren Werten an, möglicherweise zum Debugging oder zur Konfiguration.
-   `views/templates/admin/recent-events.tpl`: Rendert eine Tabelle oder Liste der kürzlich verfolgten Ereignisse, Teil der „Live-Statistiken“.
-   `views/templates/admin/tabs.tpl`: Rendert die Tab-Navigationsstruktur für die Back-Office-Konfiguration des Moduls.
-   `views/templates/admin/tag-chips.tpl`: Zeigt visuelle „Chips“ oder Labels für konfigurierte Tags/Tokens an.
-   `views/templates/admin/tag-ids.tpl`: Rendert Eingabefelder für Amazon Ads Tag ID und CAPI Access Token.
-   `views/templates/admin/wizard.tpl`: Rendert die anfängliche Einrichtungsassistenten-Oberfläche.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Das Modul speichert seine Konfiguration hauptsächlich in der PrestaShop-Tabelle `ps_configuration`.

-   `ps_configuration`: Speichert Schlüssel-Wert-Paare für Moduleinstellungen (z. B. `MYAMAZON_TAG_ID`, `MYAMAZON_CAPI_TOKEN`, `MYAMAZON_TRACKING_MODE`).
    Basierend auf dem bereitgestellten Inventar werden von diesem Modul keine benutzerdefinierten SQL-Tabellen explizit erstellt.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Injiziert das Amazon Ads Tag-Skript (`aa.js`), `myamazon.js` und anfängliche Konfigurationsvariablen. Wird auch für `capi-pageview.tpl` und `debug.tpl` verwendet. |
| `displayOrderConfirmation` | Auf der Bestellbestätigungsseite nach einem erfolgreichen Kauf. | Erfasst und sendet „Purchase“-Ereignisdaten, einschließlich Bestelldetails und Produkten, an Amazon über clientseitige und serverseitige Methoden. |
| `actionCartSave` | Wenn ein Produkt zum Warenkorb hinzugefügt oder daraus entfernt wird oder sich die Warenkorbmenge ändert. | Löst „AddToCart“- oder „RemoveFromCart“-Ereignisse aus. |
| `actionProductAdd` | Wenn ein neues Produkt zum Katalog hinzugefügt wird. | Potenziell von `MyamazonCatalogDoctor` für Datenqualitätsprüfungen verwendet. |
| `actionProductUpdate` | Wenn ein bestehendes Produkt im Katalog aktualisiert wird. | Potenziell von `MyamazonCatalogDoctor` für Datenqualitätsprüfungen verwendet. |
| `actionFrontControllerSetMedia` | Bevor ein Front-Controller sein Template rendert, um das Hinzufügen von JS/CSS zu ermöglichen. | Injiziert modulspezifische JS/CSS-Dateien (`myamazon.js`, `myamazon-debug.js` usw.) in das Front Office. |
| `actionAdminControllerSetMedia` | Bevor ein Admin-Controller sein Template rendert. | Injiziert modulspezifische JS/CSS-Dateien (`myamazon-admin.js`, `myamazon-admin.css` usw.) in das Back Office. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert und in der Datenbank gespeichert wurde. | Entscheidend für das serverseitige Senden von „Purchase“-Ereignissen über CAPI, um sicherzustellen, dass Daten gesendet werden, auch wenn der Kunde den Browser schließt, bevor er die Bestätigungsseite erreicht. |
| `displayProductButtons` / `displayProductExtraContent` | Auf der Produktseite, in der Nähe des In-den-Warenkorb-Buttons oder der Produktbeschreibung. | Injiziert JavaScript, um „ViewContent“-Ereignisse zu verfolgen. |
| `displayPaymentTop` | Oben auf der Zahlungs-Auswahlseite während des Checkouts. | Potenziell verwendet, um „InitiateCheckout“-Ereignisse zu verfolgen. |
| `displayFooter` | Im Footer-Bereich jeder Seite. | Weniger üblich für das Kern-Tracking, könnte aber für verzögertes Skriptladen oder spezifische Zustimmungs-Popups verwendet werden. |
| `actionObjectCustomerAddAfter` | Nachdem ein neues Kundenkonto erstellt wurde. | Potenziell verwendet, um „SignUp“- oder „Lead“-Ereignisse an Amazon zu senden. |
| `actionObjectCustomerUpdateAfter` | Nachdem die Kundendaten aktualisiert wurden. | Könnte verwendet werden, um Kundendaten für CAPI zu aktualisieren. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support wenden Sie sich bitte an Ihr Kundenkonto bei MyPresta.eu.

-   **Modul-Updates:** Melden Sie sich in Ihrem Konto unter [MyPresta.eu Bestellhistorie & Downloads](https://mypresta.eu/my-account/orders/) an, um die neuesten Versionen des Moduls „Amazon Ads Tag Conversions API“ herunterzuladen.
-   **Technischer Support:** Wenn Sie Probleme haben oder Fragen zur Funktionalität, Konfiguration oder Integration des Moduls haben, eröffnen Sie bitte ein Support-Ticket über Ihr MyPresta.eu-Kundenkonto. Unser Expertenteam steht Ihnen gerne zur Verfügung.
