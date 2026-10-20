---
title: "TikTok Pixel / Events API – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul TikTok Pixel / Events API von MyPresta.eu."
sidebar:
  label: "TikTok Pixel / Events API – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul TikTok Pixel / Events API auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/tiktok-pixel-events-api.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/tiktok-pixel-events-api/)
>
> ---


# TikTok Pixel / Events API

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind für die korrekte Funktion des Moduls erforderlich, insbesondere für die Events API (serverseitiges Tracking). Diese sind in den meisten modernen Hosting-Umgebungen typischerweise verfügbar.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbereich, in dem Sie Ihr TikTok Pixel und die Events API einrichten. Die Einstellungen sind intuitiv gestaltet und führen Sie durch den Prozess der Verbindung Ihres Shops mit TikTok Ads.

#### **Allgemeine Einstellungen**

-   **TikTok Pixel ID:**

    *   **Was diese Einstellung bewirkt:** Dies ist Ihre eindeutige Kennung, die vom TikTok Ads Manager bereitgestellt wird. Sie teilt TikTok mit, zu welchem Anzeigenkonto Ihre Website-Daten gehören.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn eingegeben:* Das Modul beginnt, Daten an Ihr angegebenes TikTok Pixel zu senden.
        *   *Wenn leer gelassen:* Es werden keine Daten über das Pixel an TikTok gesendet, und das Modul funktioniert nicht für das clientseitige Tracking.
    *   **Empfohlener Wert:** Ihre gültige TikTok Pixel ID.
    *   **Händlerszenario / Beispiel:** Sie erstellen ein TikTok Ads-Konto und richten ein Pixel ein. TikTok stellt Ihnen eine numerische ID zur Verfügung (z.B. `1234567890`). Sie geben diese ID hier ein, um Ihren Shop mit Ihrem TikTok-Konto zu verknüpfen.
-   **TikTok Access Token (für Events API):**

    *   **Was diese Einstellung bewirkt:** Dies ist ein sicheres Token, das in Ihrem TikTok Ads Manager generiert wird und Ihren PrestaShop-Shop autorisiert, Daten direkt über die Events API an die Server von TikTok zu senden. Es ist entscheidend für das serverseitige Tracking.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn eingegeben:* Aktiviert das serverseitige Tracking (Events API), das zuverlässiger und weniger von Werbeblockern betroffen ist.
        *   *Wenn leer gelassen:* Das serverseitige Tracking wird deaktiviert.
    *   **Empfohlener Wert:** Ihr gültiger TikTok Events API Access Token.
    *   **Händlerszenario / Beispiel:** Um die Datengenauigkeit zu verbessern und Browserbeschränkungen zu umgehen, entscheiden Sie sich für die Verwendung der Events API. Sie generieren einen Access Token im TikTok Ads Manager und fügen ihn hier ein.
-   **Tracking-Modus:**

    *   **Was diese Einstellung bewirkt:** Bestimmt, wie Daten an TikTok gesendet werden. Sie können zwischen Pixel (clientseitig), Events API (serverseitig) oder Dual-Modus (beides) wählen.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Nur Pixel:* Nur clientseitiges Tracking ist aktiv.
        *   *Nur Events API:* Nur serverseitiges Tracking ist aktiv.
        *   *Dual-Modus (Empfohlen):* Sowohl Pixel als auch Events API sind aktiv. Das Modul verwendet intelligent eine gemeinsame `event_id`, um Ereignisse in TikTok zu deduplizieren und so die Genauigkeit zu gewährleisten.
    *   **Empfohlener Wert:** `Dual-Modus` für maximale Datengenauigkeit und Widerstandsfähigkeit gegen Werbeblocker.
    *   **Händlerszenario / Beispiel:** Sie möchten das zuverlässigste Tracking. Sie wählen „Dual-Modus“, damit, wenn ein Kunde einen Werbeblocker verwendet, die serverseitige Events API die Konversion immer noch erfassen kann und TikTok sie nicht zweimal zählt, wenn beide Methoden erfolgreich sind.
-   **Debug-Modus aktivieren:**

    *   **Was diese Einstellung bewirkt:** Aktiviert einen speziellen Modus, der detaillierte Informationen über die gesendeten TikTok-Ereignisse direkt in der Entwicklerkonsole Ihres Browsers anzeigt. Dies ist von unschätzbarem Wert für die Fehlerbehebung.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Entwickler und fortgeschrittene Benutzer können genau sehen, welche Daten in Echtzeit an TikTok gesendet werden, was hilft, die korrekte Einrichtung zu überprüfen.
        *   *Wenn deaktiviert:* Es werden keine Debug-Informationen angezeigt.
    *   **Empfohlener Wert:** `Nein` für Live-Produktions-Shops. Nur vorübergehend zum Testen und Debuggen aktivieren.
    *   **Händlerszenario / Beispiel:** Sie haben das Modul gerade installiert und möchten sicherstellen, dass `AddToCart`-Ereignisse korrekt ausgelöst werden. Sie aktivieren den Debug-Modus, legen einen Artikel in Ihren Warenkorb und überprüfen Ihre Browserkonsole auf die TikTok-Ereignisdaten.

#### **Erweiterte Einstellungen**

-   **Einwilligungsverwaltung (DSGVO/CCPA):**

    *   **Was diese Einstellung bewirkt:** Integriert sich in die Cookie-Einwilligungslösung Ihres Shops (falls vorhanden), um sicherzustellen, dass das TikTok-Tracking erst aktiviert wird, nachdem ein Kunde seine Einwilligung gegeben hat.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Der TikTok Pixel/Events API wird nur geladen und sendet Daten, wenn der Kunde Cookies akzeptiert hat.
        *   *Wenn deaktiviert:* Das Tracking erfolgt unabhängig von der Cookie-Einwilligung, was möglicherweise nicht mit Datenschutzbestimmungen wie der DSGVO oder CCPA konform ist.
    *   **Empfohlener Wert:** `Ja`, wenn Ihr Shop in Regionen mit strengen Datenschutzgesetzen (z.B. EU, Kalifornien) betrieben wird.
    *   **Händlerszenario / Beispiel:** Ihr Shop bedient Kunden in der Europäischen Union. Um die DSGVO einzuhalten, aktivieren Sie diese Einstellung, um sicherzustellen, dass das TikTok-Tracking die Datenschutzentscheidungen der Benutzer respektiert.
-   **Produkttyp-ID:**

    *   **Was diese Einstellung bewirkt:** Bestimmt, welcher Produktidentifikator (ID) an TikTok gesendet wird. Optionen umfassen typischerweise die interne Produkt-ID von PrestaShop, EAN13, UPC oder eine benutzerdefinierte Referenz. Dies ist entscheidend für den Abgleich von Produkten in Ihrem TikTok-Produktkatalog.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Änderung des Typs:* Stellt sicher, dass die an TikTok gesendeten Produkt-IDs mit den IDs in Ihrem TikTok-Produktkatalog übereinstimmen, was dynamische Produktanzeigen ermöglicht.
    *   **Empfohlener Wert:** Wählen Sie den ID-Typ, den Sie in Ihrem TikTok-Produktkatalog verwenden. Oft sind die `Produkt-ID` oder `EAN13` von PrestaShop gängige Optionen.
    *   **Händlerszenario / Beispiel:** Sie haben einen Produktkatalog mit den EAN13-Codes Ihrer Produkte auf TikTok hochgeladen. Sie wählen hier `EAN13`, um sicherzustellen, dass TikTok korrekt identifizieren kann, welche Produkte Kunden ansehen oder kaufen.
-   **Linker-Domains (für Cross-Domain-Tracking):**

    *   **Was diese Einstellung bewirkt:** Ermöglicht die Angabe zusätzlicher Domainnamen, wenn Ihre Kundenreise mehrere Domains umfasst (z.B. ein Hauptshop und ein separater Blog auf einer anderen Domain). Dies hilft TikTok, Benutzer nahtlos über diese Domains hinweg zu verfolgen.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Wenn Domains hinzugefügt werden:* TikTok kann die Konsistenz der Benutzerverfolgung über die aufgelisteten Domains hinweg aufrechterhalten.
        *   *Wenn leer gelassen:* Das Tracking könnte unterbrochen werden, wenn Kunden zwischen verschiedenen Domains navigieren, die Teil Ihres Geschäfts sind.
    *   **Empfohlener Wert:** Fügen Sie alle relevanten Subdomains oder verknüpften Domains hinzu, die Ihre Kunden besuchen könnten.
    *   **Händlerszenario / Beispiel:** Ihr Hauptshop ist `meinshop.com`, aber Sie haben einen Blog unter `blog.meinshop.com`, wo Sie auf Produkte verlinken. Das Hinzufügen von `blog.meinshop.com` hier stellt sicher, dass TikTok Benutzer vom Blog zu Ihrem Shop verfolgen kann.

#### **Datenqualität & Health Score**

Dieser Abschnitt bietet Einblicke in die Leistung und Genauigkeit Ihres TikTok-Trackings.

-   **Health Score:**

    *   **Was dies bewirkt:** Zeigt einen Wert an, der die allgemeine Gesundheit und Genauigkeit Ihrer Datenübertragung an TikTok angibt. Ein höherer Wert bedeutet eine bessere Datenqualität.
    *   **Auswirkung:** Hilft Ihnen, schnell zu erkennen, ob es Probleme mit Ihrer Tracking-Einrichtung gibt, die die Anzeigenleistung beeinträchtigen könnten.
    *   **Empfohlen:** Streben Sie einen hohen Wert an. Das Modul gibt Empfehlungen, wenn der Wert niedrig ist.
-   **Recovery Radar:**

    *   **Was dies bewirkt:** Überwacht abgebrochene Warenkörbe und bietet Einblicke in potenzielle verlorene Verkäufe, wodurch Sie Möglichkeiten für Retargeting-Kampagnen identifizieren können.
    *   **Auswirkung:** Gibt Ihnen einen schnellen Überblick darüber, wie viele Warenkörbe initiiert und wie viele abgeschlossen werden, und hebt Bereiche zur Verbesserung Ihres Checkout-Prozesses oder Ihrer Retargeting-Strategie hervor.
-   **Live-Statistiken:**

    *   **Was dies bewirkt:** Zeigt Echtzeitdaten zu den an TikTok gesendeten Ereignissen an, sodass Sie sehen können, ob Ereignisse wie erwartet ausgelöst werden.
    *   **Auswirkung:** Bietet sofortiges Feedback während des Testens und der laufenden Überwachung und bestätigt, dass Ihr Tracking aktiv und genau ist.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Das Modul erweitert das PrestaShop Back Office um mehrere dedizierte Bildschirme, die Ihnen helfen, Ihre TikTok-Integration zu verwalten und zu überwachen. Diese sind typischerweise über Registerkarten oder dedizierte Menüpunkte von der Konfigurationsseite des Moduls aus zugänglich.

#### **AdminMytiktokAjaxController (Ajax-Operationen)**

-   **Bildschirmname & Menüpfad:** Dieser Controller verarbeitet hauptsächlich Hintergrund-AJAX-Anfragen von der Konfigurationsseite des Moduls. Sie navigieren nicht direkt zu einem „Bildschirm“ dafür, aber er steuert die dynamischen Aktualisierungen und den Datenabruf innerhalb der Hauptkonfigurationsregisterkarten des Moduls (z.B. Live-Statistiken, Health Score, Ereignisprotokolle).
-   **Verfügbare Aktionen & Einstellungen:** Er verarbeitet Anfragen für:
    *   Abrufen von Live-Ereignisdaten.
    *   Aktualisieren von Health Scores.
    *   Abrufen von Diagnoseinformationen.
    *   Speichern spezifischer Konfigurationsteile ohne vollständiges Neuladen der Seite.
-   **Auswirkung von Änderungen:** Interaktionen auf der Hauptkonfigurationsseite des Moduls (wie das Aktualisieren von Live-Statistiken oder das Ausführen von Diagnosen) lösen diesen Controller aus, um die relevanten Daten abzurufen und anzuzeigen.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Sie interagieren indirekt damit, indem Sie die verschiedenen Diagnose- und Überwachungstools nutzen, die auf der Hauptkonfigurationsseite des Moduls bereitgestellt werden.

#### **index.php (Haupt-Moduleinstiegspunkt)**

-   **Bildschirmname & Menüpfad:** Dies ist der primäre Einstiegspunkt für die Modulkonfiguration, zugänglich über **Back Office > Module > Modul-Manager > Konfigurieren (für TikTok Pixel / Events API)**.
-   **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm präsentiert alle in Abschnitt 4.1 beschriebenen allgemeinen und erweiterten Einstellungen, organisiert in logischen Registerkarten oder Abschnitten. Er beherbergt auch die verschiedenen Diagnosetools wie Health Score, Live-Statistiken und Recovery Radar.
-   **Auswirkung von Änderungen:** Alle auf diesem Bildschirm gespeicherten Änderungen wirken sich direkt darauf aus, wie Ihr TikTok Pixel und die Events API in Ihrem Shop funktionieren.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
    1.  **Ersteinrichtung:** Konfigurieren Sie Ihre Pixel-ID, Ihr Access Token und den Tracking-Modus.
    2.  **Regelmäßige Überwachung:** Überprüfen Sie regelmäßig die Registerkarten „Health Score“ und „Live-Statistiken“, um die Datenqualität und das Auslösen von Ereignissen sicherzustellen.
    3.  **Fehlerbehebung:** Verwenden Sie den „Debug-Modus“ (temporär) und „Live-Statistiken“, um Tracking-Probleme zu diagnostizieren.
    4.  **Optimierung:** Überprüfen Sie die Erkenntnisse des „Recovery Radar“, um Ihre Retargeting-Strategien zu informieren.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | TikTok Pixel ID | Ihre Pixel ID | Verknüpft Ihren Shop mit Ihrem TikTok Ad-Konto für Browser-Tracking. |
| Modulkonfiguration | TikTok Access Token | Ihr Access Token | Autorisiert serverseitiges Tracking über die Events API. |
| Modulkonfiguration | Tracking-Modus | Dual-Modus | Bestimmt, ob Pixel, Events API oder beides für das Tracking verwendet wird. Dual-Modus wird für Genauigkeit empfohlen. |
| Modulkonfiguration | Debug-Modus aktivieren | Nein (für Produktion) | Zeigt detaillierte Ereignisdaten in der Browserkonsole zur Fehlerbehebung an. |
| Modulkonfiguration | Einwilligungsverwaltung | Ja (für DSGVO/CCPA) | Stellt sicher, dass das Tracking die Cookie-Einwilligung des Benutzers respektiert. |
| Modulkonfiguration | Produkttyp-ID | Passend zu Ihrem Katalog | Wählt den Produktidentifikator, der für den Katalogabgleich an TikTok gesendet wird. |
| Modulkonfiguration | Linker-Domains | Leer (bei Bedarf hinzufügen) | Ermöglicht Cross-Domain-Tracking für komplexe Site-Strukturen. |
| Modulkonfiguration | Health Score | Hoher Wert | Zeigt die allgemeine Datenqualität und Tracking-Genauigkeit an. |
| Modulkonfiguration | Recovery Radar | Überwachen | Einblicke in abgebrochene Warenkörbe für Retargeting. |
| Modulkonfiguration | Live-Statistiken | Überwachen | Echtzeitansicht der an TikTok gesendeten Ereignisse. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe das Modul installiert, sehe aber keine Daten in meinem TikTok Ads Manager. Was soll ich tun?**

-   **A:** Überprüfen Sie zunächst, ob Ihre **TikTok Pixel ID** und Ihr **Access Token** in der Modulkonfiguration korrekt eingegeben wurden. Stellen Sie sicher, dass keine Tippfehler vorhanden sind.
-   Überprüfen Sie als Nächstes, ob Ihr **Tracking-Modus** auf „Dual-Modus“ oder „Pixel“ (wenn Sie nur das Pixel verwenden) eingestellt ist.
-   Aktivieren Sie den **Debug-Modus** in den Moduleinstellungen, besuchen Sie dann das Front Office Ihres Shops, führen Sie einige Aktionen aus (z.B. ein Produkt ansehen, in den Warenkorb legen) und überprüfen Sie die Entwicklerkonsole Ihres Browsers (normalerweise F12 > Registerkarte Konsole) auf TikTok-Ereignismeldungen.
-   Leeren Sie schließlich Ihren PrestaShop-Cache (**Erweiterte Parameter > Leistung > Cache leeren**).

**F2: Mein TikTok Health Score ist niedrig. Wie kann ich ihn verbessern?**

-   **A:** Ein niedriger Health Score weist oft auf Probleme mit der Datenqualität oder der Ereignisübermittlung hin.
-   **Auf fehlende Daten prüfen:** Stellen Sie sicher, dass alle erforderlichen Produktinformationen (Preis, Währung, Name) für Ihre Produkte vollständig sind.
-   **Einwilligung überprüfen:** Wenn Sie die „Einwilligungsverwaltung“ aktiviert haben, stellen Sie sicher, dass Ihr Cookie-Einwilligungsbanner korrekt funktioniert und Benutzer Cookies akzeptieren.
-   **Live-Statistiken überprüfen:** Suchen Sie im Abschnitt „Live-Statistiken“ des Moduls nach Fehlern oder fehlenden Ereignissen.
-   Das Modul selbst bietet oft spezifische Empfehlungen im Abschnitt Health Score, um Sie zu leiten.

**F3: Wird dieses Modul meine Website verlangsamen?**

-   **A:** Das Modul ist leichtgewichtig und effizient konzipiert. Das clientseitige Pixel-Tracking kann eine geringe, vernachlässigbare Last hinzufügen, ähnlich wie jedes andere Analyse-Skript. Die serverseitige Events API hat praktisch keine Auswirkungen auf die Ladezeiten des Front Office, da Daten direkt von Ihrem Server gesendet werden. Wir empfehlen die Verwendung des „Dual-Modus“ für optimale Leistung und Datengenauigkeit.

**F4: Ich habe ein benutzerdefiniertes Theme. Wird das Modul korrekt funktionieren?**

-   **A:** Ja, das Modul ist so konzipiert, dass es sich nahtlos in Standard-PrestaShop-Themes und die meisten benutzerdefinierten Themes integriert. Es verwendet das offizielle Hook-System von PrestaShop, um seine Skripte und den Tracking-Code einzufügen.
-   Wenn Sie Probleme mit einem stark angepassten Theme haben, insbesondere wenn es die Kern-PrestaShop-Vorlagen für Produktseiten oder den Checkout erheblich verändert, müssen Sie möglicherweise einen Entwickler konsultieren, um sicherzustellen, dass die Hooks noch vorhanden und korrekt gerendert werden.

**F5: Wie geht das Modul mit mehrsprachigen und mehrwährungsfähigen Shops um?**

-   **A:** Das Modul ist vollständig kompatibel mit den Mehrsprachigkeits- und Mehrwährungsfunktionen von PrestaShop. Es erkennt automatisch die aktive Sprache und Währung im Front Office und sendet diese Informationen an TikTok, wodurch sichergestellt wird, dass Ihre Ereignisdaten genau und lokalisiert sind. Produktnamen und -werte werden im Kontext der vom Kunden ausgewählten Sprache und Währung gesendet.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen tiefen Einblick in die technische Struktur des TikTok Pixel / Events API-Moduls, gedacht für Entwickler, Webmaster und technische Agenturen.

### 4.1 Architekturübersicht

Das Modul `mytiktok` folgt einer Standard-PrestaShop-Modularchitektur und nutzt das MVC-Muster, wo immer dies angebracht ist. Es fungiert hauptsächlich als Ereignis-Tracker, indem es JavaScript für clientseitiges (Pixel) Tracking injiziert und serverseitige Logik für die Events API verwendet. Zu den Schlüsselkomponenten gehören:

-   **Hauptmodulklasse (`index.php`):** Verwaltet Installation, Deinstallation, Konfiguration und Hook-Registrierung.
-   **Controller:** Front-Controller für AJAX-Anfragen und Admin-Controller für die Back-Office-Verwaltung.
-   **Kernklassen:** Eine robuste Reihe von Klassen (`classes/`) zur Verwaltung von API-Kommunikation, Ereigniszuordnung, Datenqualität, Einwilligung und verschiedenen Tracking-Strategien (Pixel, CAPI, Hybrid).
-   **Templates:** Smarty-Templates sowohl für die Front-Office-Hook-Injektion als auch für die Back-Office-Konfigurationsansichten.
-   **Assets:** Dedizierte JS und CSS für Admin-Oberflächen und Front-Office-Debugging/Tracking.

Das Modul implementiert ein `MytiktokTrackerInterface` und verwendet eine `MytiktokTrackerFactory`, um verschiedene Tracking-Modi (Pixel, CAPI, Hybrid) zu abstrahieren, was ein sauberes und erweiterbares Design fördert. Es enthält auch ausgeklügelte Tools zur Datenqualität und Gesundheitsüberwachung.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

-   `mytiktok/controllers/front/ajax.php`
    *   **Klassenname & Elternklasse:** `MytiktokAjaxModuleFrontController` erweitert `ModuleFrontController`.
    *   **Verantwortlichkeit:** Verarbeitet asynchrone Anfragen vom Front Office, hauptsächlich für serverseitiges Ereignis-Tracking (Events API) oder Datenerfassung, die kein vollständiges Neuladen der Seite erfordert. Es kann von JavaScript übermittelte Daten verarbeiten und an die TikTok Events API weiterleiten.
-   `mytiktok/controllers/front/index.php`
    *   **Klassenname & Elternklasse:** `MytiktokIndexModuleFrontController` erweitert `ModuleFrontController`.
    *   **Verantwortlichkeit:** Dieser Controller könnte als Fallback oder als spezifischer Endpunkt für bestimmte Front-Office-Interaktionen dienen, obwohl `ajax.php` typischerweise aktiver für die Ereignisbehandlung ist. Er könnte bei Bedarf für spezifische Weiterleitungen oder Initialisierungen verwendet werden.

#### Back-Office-Admin-Controller

-   `mytiktok/controllers/admin/AdminMytiktokAjaxController.php`
    *   **Klassenname & Elternklasse:** `AdminMytiktokAjaxController` erweitert `ModuleAdminController`.
    *   **Registerkartenname und verwaltete Entität:** Dieser Controller ist nicht direkt als Menüregisterkarte zugänglich. Er verarbeitet AJAX-Anfragen, die von der Hauptkonfigurationsseite des Moduls (`index.php`) im Back Office stammen. Er ist verantwortlich für dynamische Aktualisierungen, das Abrufen von Live-Statistiken, Health Scores, Ereignisprotokollen und anderen Diagnosedaten, ohne dass eine vollständige Seitenaktualisierung erforderlich ist.
-   `mytiktok/controllers/admin/index.php`
    *   **Klassenname & Elternklasse:** `AdminMytiktokController` erweitert `ModuleAdminController`.
    *   **Registerkartenname und verwaltete Entität:** Dies ist der primäre Admin-Controller für die Modulkonfiguration. Es ist der Controller, an den `index.php` (die Hauptmoduldatei) weiterleitet, wenn die Schaltfläche „Konfigurieren“ geklickt wird. Er verwaltet die Anzeige aller Konfigurationsformulare, Registerkarten (z.B. Allgemeine Einstellungen, Datenqualität, Live-Statistiken) und die Speicherung der Moduleinstellungen.

### 4.3 Kernklassen & Modelle (`classes/`)

-   `mytiktok/classes/autoload.php`: Standard-PrestaShop-Autoload-Datei, die sicherstellt, dass Modulklassen korrekt geladen werden.
-   `mytiktok/classes/index.php`: Leere Datei, oft verwendet, um das Auflisten von Verzeichnissen zu verhindern.
-   `mytiktok/classes/MytiktokCapiClient.php`:
    *   **Datenbanktabelle:** Keine direkt.
    *   **Erweitert ObjectModel:** Nein.
    *   **Wichtige öffentliche Methoden:** Handhabt die Kommunikation mit der TikTok Events API (CAPI). Enthält Methoden zum Senden von Ereignisdaten, zur Verwaltung der Authentifizierung mit dem Access Token und zur Verarbeitung von API-Antworten.
-   `mytiktok/classes/MytiktokCapiTracker.php`:
    *   **Datenbanktabelle:** Keine direkt.
    *   **Erweitert ObjectModel:** Nein.
    *   **Wichtige öffentliche Methoden:** Implementiert `MytiktokTrackerInterface`. Verantwortlich für die Vorbereitung und das Senden von serverseitigen Ereignissen an TikTok über `MytiktokCapiClient`.
-   `mytiktok/classes/MytiktokCatalogDoctor.php`:
    *   **Datenbanktabelle:** Keine direkt.
    *   **Erweitert ObjectModel:** Nein.
    *   **Wichtige öffentliche Methoden:** Bietet Diagnosetools und Empfehlungen im Zusammenhang mit Produktkatalogdaten, um sicherzustellen, dass Produkt-IDs und Attribute für TikTok korrekt formatiert sind.
-   `mytiktok/classes/MytiktokConsent.php`:
    *   **Datenbanktabelle:** Keine direkt.
    *   **Erweitert ObjectModel:** Nein.
    *   **Wichtige öffentliche Methoden:** Verwaltet die Cookie-Einwilligungslogik und integriert sich in die Einwilligungsmechanismen von PrestaShop oder benutzerdefinierte Einwilligungsmodule, um die Einhaltung der DSGVO/CCPA zu gewährleisten.
-   `mytiktok/classes/MytiktokCurrencyHelper.php`:
    *   **Datenbanktabelle:** Keine direkt.
    *   **Erweitert ObjectModel:** Nein.
    *   **Wichtige öffentliche Methoden:** Dienstprogrammklasse zur Handhabung der Währungsformatierung und -umrechnung, um sicherzustellen, dass Ereigniswerte im richtigen Format und in der richtigen Währung an TikTok gesendet werden.
-   `mytiktok/classes/MytiktokDataQualityCoach.php`:
    *   **Datenbanktabelle:** Keine direkt.
    *   **Erweitert ObjectModel:** Nein.
    *   **Wichtige öffentliche Methoden:** Analysiert die Qualität und Vollständigkeit der an TikTok gesendeten Daten und liefert Einblicke und Verbesserungsvorschläge.
-   `mytiktok/classes/MytiktokEventId.php`:
    *   **Datenbanktabelle:** Keine direkt.
    *   **Erweitert ObjectModel:** Nein.
    *   **Wichtige öffentliche Methoden:** Generiert und verwaltet eindeutige `event_id`-Werte für Ereignisse, entscheidend für die Deduplizierung im Dual-Modus-Tracking.
-   `mytiktok/classes/MytiktokEventMap.php`:
    *   **Datenbanktabelle:** Keine direkt.
    *   **Erweitert ObjectModel:** Nein.
    *   **Wichtige öffentliche Methoden:** Ordnet PrestaShop-Aktionen und -Daten standardmäßigen TikTok-Ereignisnamen und -Eigenschaften zu (z.B. `ViewContent`, `AddToCart`, `CompletePayment`).
-   `mytiktok/classes/MytiktokEvents.php`:
    *   **Datenbanktabelle:** Keine direkt.
    *   **Erweitert ObjectModel:** Nein.
    *   **Wichtige öffentliche Methoden:** Zentrale Klasse zum Auslösen und Verwalten verschiedener TikTok-Ereignisse basierend auf Benutzeraktionen in PrestaShop.
-   `mytiktok/classes/MytiktokHealthScore.php`:
    *   **Datenbanktabelle:** Keine direkt.
    *   **Erweitert ObjectModel:** Nein.
    *   **Wichtige öffentliche Methoden:** Berechnet und zeigt den Gesamt-Health Score der TikTok-Integration basierend auf Datenqualität, Ereignisübermittlung und Konfiguration an.
-   `mytiktok/classes/MytiktokHybridTracker.php`:
    *   **Datenbanktabelle:** Keine direkt.
    *   **Erweitert ObjectModel:** Nein.
    *   **Wichtige öffentliche Methoden:** Implementiert `MytiktokTrackerInterface`. Orchestriert das Dual-Modus-Tracking, indem Ereignisse sowohl über Pixel als auch über CAPI mit `event_id`-Deduplizierung gesendet werden.
-   `mytiktok/classes/MytiktokLiveStats.php`:
    *   **Datenbanktabelle:** Keine direkt.
    *   **Erweitert ObjectModel:** Nein.
    *   **Wichtige öffentliche Methoden:** Sammelt und zeigt Echtzeitstatistiken der an TikTok gesendeten Ereignisse zu Überwachungszwecken an.
-   `mytiktok/classes/MytiktokPixelTracker.php`:
    *   **Datenbanktabelle:** Keine direkt.
    *   **Erweitert ObjectModel:** Nein.
    *   **Wichtige öffentliche Methoden:** Implementiert `MytiktokTrackerInterface`. Verantwortlich für das Injizieren und Verwalten von clientseitigen TikTok Pixel-Ereignissen.
-   `mytiktok/classes/MytiktokProductIdResolver.php`:
    *   **Datenbanktabelle:** Keine direkt.
    *   **Erweitert ObjectModel:** Nein.
    *   **Wichtige öffentliche Methoden:** Löst die korrekte Produkt-ID basierend auf der Modulkonfiguration (z.B. PrestaShop ID, EAN13, UPC) zur Übermittlung an TikTok auf.
-   `mytiktok/classes/MytiktokPropertyRules.php`:
    *   **Datenbanktabelle:** Keine direkt.
    *   **Erweitert ObjectModel:** Nein.
    *   **Wichtige öffentliche Methoden:** Definiert und erzwingt Regeln für Ereigniseigenschaften, um sicherzustellen, dass die an TikTok gesendeten Daten dessen Spezifikationen entsprechen.
-   `mytiktok/classes/MytiktokTrackerFactory.php`:
    *   **Datenbanktabelle:** Keine direkt.
    *   **Erweitert ObjectModel:** Nein.
    *   **Wichtige öffentliche Methoden:** Factory-Muster zur Instanziierung der korrekten Tracker-Klasse (`MytiktokPixelTracker`, `MytiktokCapiTracker` oder `MytiktokHybridTracker`) basierend auf der „Tracking-Modus“-Konfiguration des Moduls.
-   `mytiktok/classes/MytiktokTrackerInterface.php`:
    *   **Datenbanktabelle:** Keine direkt.
    *   **Erweitert ObjectModel:** Nein.
    *   **Wichtige öffentliche Methoden:** Definiert den Vertrag für alle Tracker-Klassen, um eine konsistente Schnittstelle zum Senden von Ereignissen zu gewährleisten.
-   `mytiktok/classes/MytiktokTrans.php`:
    *   **Datenbanktabelle:** Keine direkt.
    *   **Erweitert ObjectModel:** Nein.
    *   **Wichtige öffentliche Methoden:** Dienstprogrammklasse zur Handhabung von Modulübersetzungen.
-   `mytiktok/classes/MytiktokUserData.php`:
    *   **Datenbanktabelle:** Keine direkt.
    *   **Erweitert ObjectModel:** Nein.
    *   **Wichtige öffentliche Methoden:** Sammelt und formatiert Benutzerdaten (z.B. E-Mail, Telefon, IP-Adresse) für eine verbesserte Übereinstimmung in der TikTok Events API.

### 4.4 JavaScript-Assets (`views/js/`)

-   `mytiktok/views/js/mytiktok-admin.js`:
    *   **Geltungsbereich:** Back Office.
    *   **Beschreibung:** Handhabt interaktive Elemente und AJAX-Aufrufe innerhalb der Administrationsseiten des Moduls. Dies umfasst die Verwaltung von Registerkarten, die Aktualisierung von Live-Statistiken, die Bearbeitung von Formularübermittlungen und Assistentenschritte.
-   `mytiktok/views/js/mytiktok-debug.js`:
    *   **Geltungsbereich:** Front Office (wenn der Debug-Modus aktiviert ist).
    *   **Beschreibung:** Fügt Debugging-Informationen in die Browserkonsole ein, protokolliert TikTok-Ereignisse, deren Eigenschaften und potenzielle Probleme. Wesentlich zur Überprüfung des korrekten Auslösens von Ereignissen.
-   `mytiktok/views/js/mytiktok-ghost.js`:
    *   **Geltungsbereich:** Front Office.
    *   **Beschreibung:** Handhabt potenziell „Ghost“- oder versteckte Tracking-Mechanismen, möglicherweise im Zusammenhang mit der serverseitigen Ereignisinitiierung oder spezifischen Benutzerinteraktionen, die ohne direkte Pixel-Interaktion erfasst werden müssen.
-   `mytiktok/views/js/mytiktok-live.js`:
    *   **Geltungsbereich:** Back Office.
    *   **Beschreibung:** Treibt die Funktion „Live-Statistiken“ im Admin-Panel an, indem periodisch Echtzeit-Ereignisdaten abgerufen und angezeigt werden.
-   `mytiktok/views/js/mytiktok-tcf.js`:
    *   **Geltungsbereich:** Front Office.
    *   **Beschreibung:** Integriert sich in das Transparency and Consent Framework (TCF) oder andere Cookie-Einwilligungslösungen, um die Benutzerzustimmung vor der Initialisierung des TikTok Pixels zu verwalten.
-   `mytiktok/views/js/mytiktok-wizard.js`:
    *   **Geltungsbereich:** Back Office.
    *   **Beschreibung:** Verwaltet den Schritt-für-Schritt-Einrichtungsassistenten für die anfängliche Modulkonfiguration und führt den Händler durch die wesentlichen Einstellungen.
-   `mytiktok/views/js/mytiktok.js`:
    *   **Geltungsbereich:** Front Office.
    *   **Beschreibung:** Die Haupt-JavaScript-Datei des Front Office. Sie initialisiert den TikTok Pixel, löst Standardereignisse (PageView, ViewContent, AddToCart, InitiateCheckout) aus und sammelt die notwendigen Daten aus dem DOM, um sie an TikTok zu senden. Sie handhabt auch die `event_id`-Generierung zur Deduplizierung.

### 4.5 CSS-Stylesheets (`views/css/`)

-   `mytiktok/views/css/mytiktok-admin.css`:
    *   **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
    *   **Beschreibung:** Gestaltet die Konfigurationsseite des Moduls, einschließlich Registerkarten, Eingabefeldern, Schaltflächen und Diagnoseanzeigen (Health Score, Live-Statistiken usw.), um eine konsistente und benutzerfreundliche Oberfläche innerhalb des PrestaShop Back Office zu gewährleisten.
-   `mytiktok/views/css/mytiktok-debug.css`:
    *   **Geltungsbereich:** Front-Office-Kunden-Styling (nur wenn der Debug-Modus aktiv ist).
    *   **Beschreibung:** Bietet minimale Gestaltung für alle visuellen Debugging-Elemente, die im Front Office erscheinen könnten, wenn der Debug-Modus aktiviert ist (z.B. ein kleines Overlay oder Banner, das den Debug-Status anzeigt).

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

-   `mytiktok/views/templates/hook/capi-pageview.tpl`:
    *   **Hook:** Potenziell `displayHeader` oder `displayBeforeBodyClosingTag`.
    *   **Ausgabe:** Rendert das serverseitige `PageView`-Ereignis für die Events API. Dieses Template könnte versteckte Felder oder Datenstrukturen enthalten, die von der serverseitigen Logik verwendet werden, um das CAPI PageView-Ereignis zu initiieren.
-   `mytiktok/views/templates/hook/debug.tpl`:
    *   **Hook:** `displayHeader` oder `displayBeforeBodyClosingTag`.
    *   **Ausgabe:** Rendert einen kleinen HTML-Block oder Script-Tag zu Debugging-Zwecken, oft einschließlich `mytiktok-debug.js` und anfänglicher Debug-Daten.
-   `mytiktok/views/templates/hook/displayOrderConfirmation.tpl`:
    *   **Hook:** `displayOrderConfirmation`.
    *   **Ausgabe:** Rendert die `CompletePayment`-Ereignisdaten, einschließlich Bestellwert, Währung und Produktdetails, die nach einem erfolgreichen Kauf an TikTok Pixel und/oder Events API gesendet werden sollen.
-   `mytiktok/views/templates/hook/ghost.tpl`:
    *   **Hook:** Verschiedene Front-Office-Hooks.
    *   **Ausgabe:** Rendert versteckte Elemente oder Skripte für „Ghost“-Tracking, möglicherweise im Zusammenhang mit serverseitigen Ereignisauslösern oder erweiterter Datenerfassung.
-   `mytiktok/views/templates/hook/header.tpl`:
    *   **Hook:** `displayHeader`.
    *   **Ausgabe:** Fügt den Haupt-TikTok-Pixel-Basiscodes, `mytiktok.js` und anfängliche Konfigurationsvariablen in den `<head>`-Bereich aller Front-Office-Seiten ein. Hier wird der Pixel initialisiert.
-   `mytiktok/views/templates/hook/payment.tpl`:
    *   **Hook:** Potenziell `displayPaymentTop` oder `displayPaymentOptions`.
    *   **Ausgabe:** Kann `InitiateCheckout`-Ereignisdaten oder zugehörige Skripte rendern, wenn ein Kunde während des Checkouts den Schritt zur Zahlungsauswahl erreicht.
-   `mytiktok/views/templates/hook/product-details.tpl`:
    *   **Hook:** `displayProductAdditionalInfo` oder ähnlicher Produktseiten-Hook.
    *   **Ausgabe:** Rendert die `ViewContent`-Ereignisdaten, einschließlich Produkt-ID, Name, Preis und Kategorie, für das aktuell angezeigte Produkt.

#### Admin-Templates (`views/templates/admin/`)

-   `mytiktok/views/templates/admin/consent-guide.tpl`: Zeigt Anleitungen zur Einrichtung der Cookie-Einwilligung an.
-   `mytiktok/views/templates/admin/doctor.tpl`: Rendert die Diagnoseoberfläche des „Katalogdoktors“.
-   `mytiktok/views/templates/admin/dq.tpl`: Zeigt Einblicke und Empfehlungen zur Datenqualität an.
-   `mytiktok/views/templates/admin/health.tpl`: Rendert das „Health Score“-Dashboard.
-   `mytiktok/views/templates/admin/linker-domains.tpl`: Formularfeld zur Konfiguration von Linker-Domains.
-   `mytiktok/views/templates/admin/live-maintain.tpl`: Platzhalter- oder Wartungsansicht für Live-Statistiken.
-   `mytiktok/views/templates/admin/live.tpl`: Zeigt das „Live-Statistiken“-Dashboard an.
-   `mytiktok/views/templates/admin/mode-context.tpl`: Kontextinformationen zum ausgewählten Tracking-Modus.
-   `mytiktok/views/templates/admin/mode-note-both.tpl`: Hinweis/Erklärung für das „Dual-Modus“-Tracking.
-   `mytiktok/views/templates/admin/mode-note-capi.tpl`: Hinweis/Erklärung für das „Nur Events API“-Tracking.
-   `mytiktok/views/templates/admin/mode-note-pixel.tpl`: Hinweis/Erklärung für das „Nur Pixel“-Tracking.
-   `mytiktok/views/templates/admin/mode-picker.tpl`: Die Oberfläche zur Auswahl des Tracking-Modus (Pixel, CAPI, Dual).
-   `mytiktok/views/templates/admin/properties-list.tpl`: Zeigt eine Liste der Ereigniseigenschaften an.
-   `mytiktok/views/templates/admin/recent-events.tpl`: Zeigt ein Protokoll der zuletzt gesendeten Ereignisse an.
-   `mytiktok/views/templates/admin/tabs.tpl`: Struktur für die Registerkartenoberfläche auf der Modulkonfigurationsseite.
-   `mytiktok/views/templates/admin/tag-chips.tpl`: Visuelle Komponenten zur Anzeige von Tags oder IDs.
-   `mytiktok/views/templates/admin/tag-ids.tpl`: Eingabefelder für TikTok Pixel ID und Access Token.
-   `mytiktok/views/templates/admin/wizard.tpl`: Die Schritt-für-Schritt-Einrichtungsassistentenoberfläche.

#### Front-Office-Templates (`views/templates/front/`)

-   Es sind keine dedizierten eigenständigen Seitenvorlagen aufgeführt, da das Modul hauptsächlich Skripte und Daten über Hooks injiziert.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Das Modul speichert seine Konfigurationseinstellungen hauptsächlich in der `ps_configuration`-Tabelle von PrestaShop.

-   `ps_configuration`: Speichert Schlüssel-Wert-Paare für Moduleinstellungen, wie z.B. `MYTIKTOK_PIXEL_ID`, `MYTIKTOK_ACCESS_TOKEN`, `MYTIKTOK_TRACKING_MODE`, etc.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Initialisiert den TikTok Pixel-Basiscodes, lädt `mytiktok.js` und richtet globale Konfigurationsvariablen ein. |
| `displayBeforeBodyClosingTag` | Kurz vor dem `</body>`-Tag. | Kann zusätzliche Skripte oder Daten injizieren, die nach dem Laden des DOM ausgeführt werden müssen, oder für CAPI PageView-Ereignisse. |
| `displayProductAdditionalInfo` | Auf der Produktseite, typischerweise in der Nähe der Produktdetails. | Löst das `ViewContent`-Ereignis aus und übergibt produktspezifische Daten an TikTok. |
| `displayShoppingCartFooter` | Auf der Warenkorbseite, normalerweise unter der Warenkorbzusammenfassung. | Löst das `AddToCart`-Ereignis aus (falls nicht bereits durch AJAX behandelt) und potenziell `InitiateCheckout`. |
| `displayPaymentTop` | Oben auf der Zahlungsoptionsseite während des Checkouts. | Löst das `InitiateCheckout`-Ereignis aus. |
| `displayOrderConfirmation` | Auf der Bestellbestätigungsseite nach einem erfolgreichen Kauf. | Löst das entscheidende `CompletePayment`-Ereignis aus und sendet vollständige Bestelldetails (Wert, Produkte, Währung) an TikTok. |
| `actionFrontControllerSetMedia` | Wenn ein Front-Controller seine Medien-Assets festlegt. | Fügt modulspezifische JS/CSS-Dateien in das Front Office ein. |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller seine Medien-Assets festlegt. | Fügt modulspezifische JS/CSS-Dateien in das Back Office ein. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | Serverseitiger Trigger für das `CompletePayment`-Ereignis über die Events API, um eine zuverlässige Konversionsverfolgung zu gewährleisten. |
| `actionCartSave` | Wenn der Warenkorb aktualisiert wird (z.B. Produkt hinzufügen/entfernen). | Serverseitiger Trigger für `AddToCart`- oder `RemoveFromCart`-Ereignisse über die Events API. |
| `actionProductUpdate` | Wenn ein Produkt im Back Office aktualisiert wird. | Potenziell für Katalogsynchronisation oder Datenqualitätsprüfungen verwendet. |
| `actionObjectProductAddAfter` | Nachdem ein neues Produkt hinzugefügt wurde. | Potenziell für Katalogsynchronisation oder Datenqualitätsprüfungen verwendet. |
| `actionObjectProductUpdateAfter` | Nachdem ein Produkt aktualisiert wurde. | Potenziell für Katalogsynchronisation oder Datenqualitätsprüfungen verwendet. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „TikTok Pixel / Events API“ verweisen wir Sie auf Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser engagiertes Support-Team steht Ihnen bei technischen Problemen oder Fragen zur Funktionalität des Moduls gerne zur Verfügung.
