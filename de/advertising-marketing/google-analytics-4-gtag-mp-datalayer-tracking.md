---
title: "Google Analytics 4 - gtag, MP & dataLayer Tracking - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Google Analytics 4 - gtag, MP & dataLayer Tracking von MyPresta.eu."
sidebar:
  label: "Google Analytics 4 - gtag, MP & dataLayer Tracking - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Google Analytics 4 - gtag, MP & dataLayer tracking auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/google-analytics-4-gtag-mp-datalayer-tracking.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/google-analytics-4-gtag-mp-datalayer-tracking/)
>
> ---


# Google Analytics 4 - gtag, MP & dataLayer Tracking

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen wie cURL, JSON und OpenSSL sind erforderlich, damit das Modul korrekt funktioniert, insbesondere für das serverseitige Measurement Protocol Tracking.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Das Modul „Google Analytics 4 - gtag, MP & dataLayer Tracking“ bietet eine umfassende Reihe von Konfigurationsoptionen, die über die Hauptkonfigurationsseite und spezielle Admin-Bildschirme zugänglich sind.

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der primäre Bildschirm, auf dem Sie Ihr GA4-Tracking einrichten. Das Modul verwendet eine assistentenähnliche Oberfläche, um Sie durch die Erstkonfiguration zu führen, aber Sie können die Einstellungen jederzeit erneut aufrufen und anpassen.

#### **Initialer Einrichtungsassistent**

Bei der ersten Konfiguration werden Sie wahrscheinlich von einem Assistenten begrüßt. Befolgen Sie dessen Schritte, um Ihre primäre GA4-Property schnell einzurichten.

- **Schritt 1: Tracking-Modus auswählen**

  - **Was diese Einstellung bewirkt:** Bestimmt, wie Ihr Shop Daten an Google Analytics 4 sendet. Dies ist eine entscheidende Entscheidung, die auf Ihrem technischen Setup und Ihren Datenschutzanforderungen basiert.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *`gtag.js` (Für die meisten empfohlen):* Dies ist das Standard-Google Analytics 4 Web-Tag. Es lädt eine JavaScript-Bibliothek (`gtag.js`) direkt auf Ihren Shop-Seiten, die dann Daten an GA4 sendet. Es ist einfach zu implementieren, basiert aber auf der clientseitigen Browserausführung und der Cookie-Zustimmung.
    - *`dataLayer` (Für Google Tag Manager-Benutzer):* Dieser Modus pusht alle GA4-Ereignisdaten in das `dataLayer`-Objekt, das Ihr Google Tag Manager (GTM)-Container dann liest und an GA4 sendet. Wählen Sie dies, wenn Sie GTM bereits für andere Tags verwenden und eine zentralisierte Tag-Verwaltung wünschen.
    - *`Measurement Protocol` (Erweitert, für maximale Datenwiederherstellung):* Dieser Modus sendet Daten direkt von Ihrem PrestaShop-Server an Google Analytics 4, wodurch der Browser vollständig umgangen wird. Dies ist ideal, um Daten wiederherzustellen, wenn `gtag.js` oder `dataLayer`-Tracking durch Ad-Blocker, Browsereinstellungen oder verweigerte Cookie-Zustimmung blockiert wird. Es ist komplexer, bietet aber die robusteste Datenerfassung.
  - **Empfohlener Wert:** `gtag.js` für Einfachheit, `dataLayer`, wenn Sie GTM verwenden, `Measurement Protocol`, wenn Datenintegrität von größter Bedeutung ist und Sie mit der erweiterten Einrichtung vertraut sind.
  - **Händlerszenario / Beispiel:** Wenn Sie schnell starten möchten und GTM nicht verwenden, ist `gtag.js` perfekt. Wenn Sie ein engagiertes Marketingteam haben, das GTM verwaltet, integriert sich `dataLayer` nahtlos. Wenn Sie erhebliche Diskrepanzen zwischen Ihren Verkäufen und GA4-Daten feststellen, kann `Measurement Protocol` helfen, diese Lücke zu schließen.
- **Schritt 2: Ihre GA4-Mess-ID(s) eingeben**

  - **Was diese Einstellung bewirkt:** Dies ist Ihre eindeutige Kennung für Ihre Google Analytics 4-Property (z. B. `G-XXXXXXXXXX`). Das Modul benötigt dies, um zu wissen, wohin Ihre Daten gesendet werden sollen. Sie können mehrere IDs hinzufügen, wenn Sie verschiedene Teile Ihres Shops in separaten GA4-Properties verfolgen.
  - **Auswirkung einer Änderung dieser Einstellung:** Daten werden an die angegebene GA4-Property gesendet. Falsche IDs bedeuten keine Daten oder Daten, die an den falschen Ort gesendet werden.
  - **Empfohlener Wert:** Ihre primäre GA4-Mess-ID.
  - **Händlerszenario / Beispiel:** Sie haben eine Haupt-GA4-Property `G-ABCDEF1234`. Geben Sie diese ID ein. Wenn Sie auch spezifische Produktdaten an eine separate Property `G-XYZW5678` senden möchten, können Sie diese ebenfalls hinzufügen.
- **Schritt 3: Einwilligungsverwaltung konfigurieren (falls zutreffend)**

  - **Was diese Einstellung bewirkt:** Integriert sich in die Cookie-Zustimmungslösung Ihres Shops, um sicherzustellen, dass das GA4-Tracking die Datenschutzentscheidungen der Benutzer respektiert.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Aktiviert:* GA4-Tags werden nur ausgelöst, wenn der Benutzer die Zustimmung für Analyse-Cookies erteilt hat.
    - *Deaktiviert:* GA4-Tags werden unabhängig von der Zustimmung ausgelöst (nicht empfohlen für GDPR/CCPA-Konformität).
  - **Empfohlener Wert:** Aktiviert, und stellen Sie sicher, dass Sie ein robustes Cookie-Zustimmungsmodul installiert und konfiguriert haben.
  - **Händlerszenario / Beispiel:** Ein Kunde besucht Ihren Shop und lehnt Analyse-Cookies ab. Mit aktivierter Einwilligungsverwaltung werden die `gtag.js`- oder `dataLayer`-Skripte nicht geladen, wodurch clientseitiges Tracking verhindert wird. Wenn Sie das Measurement Protocol verwenden, senden Sie möglicherweise weiterhin anonymisierte Kaufdaten serverseitig.

#### **Allgemeine Einstellungen (nach dem Assistenten)**

Sobald der Assistent abgeschlossen ist, sehen Sie eine detailliertere Konfigurationsoberfläche, die oft in Registerkarten organisiert ist.

- **Verwaltung der Mess-IDs**

  - **Was diese Einstellung bewirkt:** Ermöglicht das Hinzufügen, Bearbeiten oder Entfernen mehrerer GA4-Mess-IDs (`G-XXXXXXXXXX`) und deren Zuordnung zu bestimmten Tracking-Modi.
  - **Auswirkung einer Änderung dieser Einstellung:** Bestimmt, welche GA4-Properties Daten von Ihrem Shop erhalten.
  - **Empfohlener Wert:** Behalten Sie nur die notwendigen GA4-Properties bei.
  - **Händlerszenario / Beispiel:** Sie haben eine neue GA4-Property für eine bestimmte Marketingkampagne erstellt. Sie können deren ID hier hinzufügen, um die kampagnenspezifische Leistung zu verfolgen.
- **Linker-Domains (für Cross-Domain-Tracking)**

  - **Was diese Einstellung bewirkt:** Wenn Ihr Shop über mehrere Domains betrieben wird (z. B. `shop.example.com` und `blog.example.com`), hilft diese Einstellung Google Analytics zu verstehen, dass diese Teil derselben Benutzerreise sind, und verhindert, dass neue Sitzungen gestartet werden, wenn ein Benutzer zwischen ihnen navigiert.
  - **Auswirkung einer Änderung dieser Einstellung:** Gewährleistet eine genaue Verfolgung der Benutzerreise über verwandte Domains hinweg. Ohne sie könnten Benutzer, die zwischen Ihren Domains wechseln, als neue Benutzer oder neue Sitzungen gezählt werden.
  - **Empfohlener Wert:** Fügen Sie alle verwandten Domains hinzu, die ein Benutzer im Rahmen seiner Reise auf Ihrer Website besuchen könnte.
  - **Händlerszenario / Beispiel:** Ihr Hauptshop ist `mystore.com` und Ihr Blog ist `blog.mystore.com`. Fügen Sie `blog.mystore.com` zur Liste der Linker-Domains hinzu.
- **Debug-Modus**

  - **Was diese Einstellung bewirkt:** Aktiviert eine spezielle Debug-Ansicht im Front Office und sendet Debug-Ereignisse an GA4, sodass Sie überprüfen können, ob Ihr Tracking korrekt funktioniert.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Aktiviert:* Ein kleines Debug-Panel erscheint im Front Office Ihres Shops und zeigt an, welche GA4-Ereignisse gesendet werden. Ereignisse erscheinen auch in der GA4 DebugView.
    - *Deaktiviert:* Kein Debug-Panel, normales Tracking.
  - **Empfohlener Wert:** Nur während des Testens und der Fehlerbehebung aktivieren. Für Live-Produktionsshops deaktivieren.
  - **Händlerszenario / Beispiel:** Sie haben das Modul gerade installiert und möchten bestätigen, dass `add_to_cart`-Ereignisse korrekt ausgelöst werden. Aktivieren Sie den Debug-Modus, legen Sie ein Produkt in Ihren Warenkorb und überprüfen Sie das Debug-Panel und die GA4 DebugView.
- **Datenqualitäts-Coach**

  - **Was diese Einstellung bewirkt:** Bietet Einblicke und Empfehlungen zur Verbesserung der Qualität und Vollständigkeit Ihrer GA4-Daten. Es überprüft häufige Probleme wie fehlende Produkt-IDs, falsche Währungsformate usw.
  - **Auswirkung einer Änderung dieser Einstellung:** Dies ist ein Diagnosetool; es ändert nicht direkt das Front-Office-Verhalten, hilft Ihnen aber, Probleme zu identifizieren und zu beheben, die zu ungenauen Analysen führen könnten.
  - **Empfohlener Wert:** Überprüfen Sie die Empfehlungen regelmäßig.
  - **Händlerszenario / Beispiel:** Der Coach könnte Ihnen mitteilen, dass einigen Produkten EAN/UPC-Codes fehlen, die für GA4-Produktdaten wertvoll sind. Sie können dann Ihren Produktkatalog aktualisieren.
- **Katalog-Doktor**

  - **Was diese Einstellung bewirkt:** Analysiert Ihren Produktkatalog auf potenzielle Probleme, die das GA4-Tracking beeinträchtigen könnten, wie z. B. Produkte ohne Preise, Bilder oder gültige Kategorien.
  - **Auswirkung einer Änderung dieser Einstellung:** Ähnlich wie der Datenqualitäts-Coach ist dies ein Diagnosetool, um sicherzustellen, dass Ihre Produktdaten für GA4 robust sind.
  - **Empfohlener Wert:** Führen Sie diese Überprüfung regelmäßig durch.
  - **Händlerszenario / Beispiel:** Der Doktor könnte Produkte kennzeichnen, die nicht auf Lager, aber immer noch sichtbar sind, was das GA4-Tracking von Produktansichten verwirren könnte.
- **Live-Statistiken**

  - **Was diese Einstellung bewirkt:** Zeigt Echtzeit-Ereignisdaten an, die von Ihrem Shop an GA4 gesendet werden, direkt in Ihrem PrestaShop Back Office.
  - **Auswirkung einer Änderung dieser Einstellung:** Bietet einen sofortigen Überblick über die jüngsten Benutzerinteraktionen und Ereignisse.
  - **Empfohlener Wert:** Nützlich zur Überwachung, insbesondere nach Änderungen oder während Spitzenverkehrszeiten.
  - **Händlerszenario / Beispiel:** Sie haben gerade ein neues Produkt eingeführt. Sie können die Live-Statistiken beobachten, um `view_item`- und `add_to_cart`-Ereignisse in Echtzeit zu sehen.
- **Ereigniszuordnung & Anpassung**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Anpassung, wie PrestaShop-Aktionen GA4-Ereignissen und deren Parametern zugeordnet werden. Zum Beispiel möchten Sie möglicherweise einen benutzerdefinierten Parameter mit dem `purchase`-Ereignis senden.
  - **Auswirkung einer Änderung dieser Einstellung:** Feinabstimmung der an GA4 gesendeten Daten, wodurch spezifischere Berichte und Zielgruppenbildung ermöglicht werden.
  - **Empfohlener Wert:** Nur ändern, wenn Sie spezifische GA4-Berichtsanforderungen haben.
  - **Händlerszenario / Beispiel:** Sie möchten einen benutzerdefinierten Parameter `loyalty_program_status` mit jedem `purchase`-Ereignis aufnehmen. Sie können diese Zuordnung hier konfigurieren.
- **Multi-Property-Regeln**

  - **Was diese Einstellung bewirkt:** Definiert Regeln für das Senden spezifischer Ereignisse oder Daten an verschiedene GA4-Properties. Zum Beispiel könnten Sie alle Ereignisse an Ihre Haupt-Property senden, aber nur „Kauf“-Ereignisse für eine bestimmte Kategorie an eine separate Property.
  - **Auswirkung einer Änderung dieser Einstellung:** Ermöglicht eine erweiterte Segmentierung Ihrer Analysedaten über mehrere GA4-Properties hinweg.
  - **Empfohlener Wert:** Verwenden Sie dies, wenn Sie komplexe Tracking-Anforderungen mit mehreren GA4-Properties haben.
  - **Händlerszenario / Beispiel:** Sie haben eine Haupt-GA4-Property für Ihren gesamten Shop, aber auch eine separate Property für Ihre „Premium-Produkte“-Linie. Sie können eine Regel festlegen, um `purchase`-Ereignisse für Produkte in der Kategorie „Premium-Produkte“ an beide Properties zu senden.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Das Modul bietet auch dedizierte Bildschirme für erweiterte Verwaltung und Diagnose.

#### **AdminMyanalyticsAjaxController (Back Office > Module > Google Analytics 4 > [Verschiedene Tabs])**

Dieser Controller verarbeitet viele der interaktiven Elemente und Datenanzeigen innerhalb der Modulkonfiguration, insbesondere für die Diagnosetools und Live-Statistiken. Sie navigieren nicht direkt zu diesem Controller; er versorgt die dynamischen Inhalte auf der Hauptkonfigurationsseite.

- **Bildschirmname & Menüpfad:** Dieser Controller ist kein eigenständiger Menüpunkt. Er bedient die AJAX-Anfragen für die verschiedenen Tabs und Abschnitte innerhalb der Hauptkonfigurationsseite des Moduls (z. B. „Datenqualitäts-Coach“, „Katalog-Doktor“, „Live-Statistiken“).
- **Verfügbare Aktionen & Einstellungen:**
  - **Datenqualitäts-Coach-Raster:** Zeigt eine Tabelle der erkannten Datenqualitätsprobleme an, oft mit Lösungsvorschlägen.
  - **Katalog-Doktor-Bericht:** Zeigt einen Bericht zur Produkt-Datenintegrität an.
  - **Live-Ereignis-Stream:** Ein Echtzeit-Feed der an GA4 gesendeten Ereignisse.
  - **Assistenten-Schritte:** Verwaltet den Fortschritt und die Datenübermittlung für den initialen Einrichtungsassistenten.
- **Auswirkung von Änderungen:** Die Interaktion mit diesen Elementen (z. B. Klicken auf „Überprüfung starten“ für den Datenqualitäts-Coach) löst Hintergrundprozesse aus, die Ihre Shop-Daten analysieren und die angezeigten Informationen aktualisieren. Es hilft Ihnen, Probleme zu diagnostizieren und zu beheben, ändert aber nicht direkt das Front-Office-Verhalten.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Überprüfen Sie regelmäßig die Tabs „Datenqualitäts-Coach“ und „Katalog-Doktor“, um sicherzustellen, dass Ihre GA4-Daten korrekt bleiben. Überwachen Sie die „Live-Statistiken“ während kritischer Perioden oder nach größeren Shop-Änderungen.

#### **index.php (Back Office > Module > Google Analytics 4)**

Dies ist der Haupteinstiegspunkt für die Modulkonfiguration im Back Office. Obwohl es `index.php` genannt wird, ist es der Kern der `getContent()`-Methode, die die gesamte Konfigurationsoberfläche rendert, einschließlich aller in Abschnitt 4.1 beschriebenen Tabs und Einstellungen.

- **Bildschirmname & Menüpfad:** **Module > Modul-Manager > Google Analytics 4 - gtag, MP & dataLayer Tracking > Konfigurieren**.
- **Verfügbare Aktionen & Einstellungen:** Alle in Abschnitt 4.1 genannten Einstellungen, Tabs und Assistenten-Schritte werden über diese Hauptkonfigurationsansicht gerendert und verwaltet.
- **Auswirkung von Änderungen:** Alle auf diesem Bildschirm gespeicherten Änderungen wirken sich direkt darauf aus, wie Ihr GA4-Tracking implementiert wird und welche Daten an Google Analytics gesendet werden.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Hier richten Sie das Modul initial ein und kehren für größere Änderungen an Ihren GA4-Properties, Tracking-Modi oder erweiterten Regeln zurück.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Hauptkonfiguration | **Tracking-Modus** | `gtag.js` | Definiert, wie Daten gesendet werden (clientseitig, GTM oder serverseitig). Entscheidend für Datenintegrität und Datenschutz. |
| Hauptkonfiguration | **Mess-ID(s)** | Ihre GA4-ID (`G-XXXXXXXXXX`) | Gibt an, welche GA4-Property Daten empfängt. Falsche IDs bedeuten keine Daten. |
| Hauptkonfiguration | **Einwilligungsverwaltung** | Aktiviert (wenn Einwilligungsmodul verwendet wird) | Stellt sicher, dass das GA4-Tracking die Datenschutzentscheidungen der Benutzer respektiert. |
| Hauptkonfiguration | **Linker-Domains** | Leer (hinzufügen, wenn Cross-Domain) | Ermöglicht eine genaue Benutzerverfolgung über mehrere verwandte Domains hinweg. |
| Hauptkonfiguration | **Debug-Modus** | Deaktiviert (für Tests aktivieren) | Zeigt ein Front-Office-Debug-Panel an und sendet Debug-Ereignisse an GA4. |
| Hauptkonfiguration | **Datenqualitäts-Coach** | N/A (Diagnosetool) | Identifiziert und schlägt Lösungen für GA4-Datenqualitätsprobleme vor. |
| Hauptkonfiguration | **Katalog-Doktor** | N/A (Diagnosetool) | Analysiert den Produktkatalog auf GA4-Tracking-Bereitschaft. |
| Hauptkonfiguration | **Live-Statistiken** | N/A (Überwachungstool) | Zeigt Echtzeit-GA4-Ereignisse im Back Office an. |
| Hauptkonfiguration | **Ereigniszuordnung** | Standard (für benutzerdefinierte Anforderungen ändern) | Passt an, wie PrestaShop-Aktionen GA4-Ereignissen und Parametern zugeordnet werden. |
| Hauptkonfiguration | **Multi-Property-Regeln** | Keine (für erweitertes Tracking hinzufügen) | Definiert Regeln für das Senden spezifischer Daten an verschiedene GA4-Properties. |
| AdminMyanalyticsAjaxController | (Verschiedene AJAX-gesteuerte Ansichten) | N/A | Versorgt dynamische Inhalte für Diagnosetools und Live-Statistiken. |
| index.php | (Hauptkonfigurationsseite) | N/A | Rendert die gesamte Modulkonfigurationsoberfläche. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe das Modul installiert, sehe aber keine Daten in meiner Google Analytics 4-Property.**

- **A:** Stellen Sie zunächst sicher, dass Sie die korrekte GA4-Mess-ID (beginnend mit `G-`) in der Modulkonfiguration eingegeben haben.
- **A:** Überprüfen Sie die „DebugView“ Ihrer GA4-Property (in Google Analytics unter Verwaltung > DebugView), während Sie Ihren Shop durchsuchen. Wenn Sie dort Ereignisse sehen, werden Daten gesendet.
- **A:** Leeren Sie Ihren PrestaShop Smarty-Cache (Erweiterte Einstellungen > Leistung > Cache leeren).
- **A:** Wenn Sie `gtag.js` oder `dataLayer` verwenden, überprüfen Sie die Entwicklerkonsole Ihres Browsers (F12) auf JavaScript-Fehler. Stellen Sie außerdem sicher, dass Sie Analyse-Cookies akzeptiert haben, wenn Sie ein Einwilligungsmodul verwenden.
- **A:** Wenn Sie das Measurement Protocol verwenden, stellen Sie sicher, dass Ihr Server `cURL` aktiviert hat und keine Firewall-Regeln ausgehende Verbindungen zu Googles Servern blockieren.

**F2: Meine GA4-Kaufdaten stimmen nicht mit meinen PrestaShop-Bestelldaten überein.**

- **A:** Dies ist ein häufiges Problem, oft aufgrund von Ad-Blockern, Browser-Datenschutzeinstellungen oder der Verweigerung der Cookie-Zustimmung durch Benutzer.
- **A:** **Erwägen Sie dringend, das Measurement Protocol für Kaufereignisse zu aktivieren.** Dies sendet Kaufdaten direkt von Ihrem Server und umgeht clientseitige Browserprobleme.
- **A:** Verwenden Sie den „Datenqualitäts-Coach“ und den „Katalog-Doktor“ des Moduls, um Dateninkonsistenzen zu identifizieren, die Probleme verursachen könnten.
- **A:** Stellen Sie sicher, dass Ihre Bestellbestätigungsseite nach einem erfolgreichen Kauf immer von den Kunden erreicht wird. Wenn Kunden woandershin weitergeleitet werden oder den Browser zu früh schließen, werden clientseitige Kaufereignisse möglicherweise nicht ausgelöst.

**F3: Das Debug-Panel des Moduls wird nicht angezeigt, oder ich sehe keine Ereignisse in der GA4 DebugView.**

- **A:** Stellen Sie sicher, dass der „Debug-Modus“ in der Modulkonfiguration explizit aktiviert ist.
- **A:** Leeren Sie Ihren Browser-Cache und den PrestaShop Smarty-Cache.
- **A:** Stellen Sie sicher, dass Sie als Administrator in Ihrem PrestaShop Back Office angemeldet sind und das Front Office in derselben Browsersitzung durchsuchen.
- **A:** Überprüfen Sie die Entwicklerkonsole Ihres Browsers auf JavaScript-Fehler, die das Laden des Debug-Panels verhindern könnten.

**F4: Wie stelle ich sicher, dass das Modul mein Cookie-Zustimmungsmodul respektiert?**

- **A:** Das Modul ist so konzipiert, dass es sich in Standard-Cookie-Zustimmungsmechanismen integriert. In der Modulkonfiguration sollte es eine Einstellung für „Einwilligungsverwaltung“ geben. Stellen Sie sicher, dass diese aktiviert ist.
- **A:** Überprüfen Sie, ob Ihr Cookie-Zustimmungsmodul Analyse-Cookies korrekt kategorisiert und ob die Entscheidungen der Benutzer gespeichert und respektiert werden. Das GA4-Modul lädt dann clientseitige Tags (`gtag.js`, `dataLayer`) nur, wenn die Zustimmung erteilt wurde.
- **A:** Für maximale Datenwiederherstellung sollten Sie das Measurement Protocol für kritische Ereignisse wie `purchase` in Betracht ziehen, da es oft clientseitige Zustimmungsprobleme umgehen kann (obwohl Sie Benutzer weiterhin über die Datenverarbeitung informieren sollten).

**F5: Ich möchte benutzerdefinierte Ereignisse oder Parameter verfolgen, die nicht von der Standardeinrichtung abgedeckt werden.**

- **A:** Das Modul enthält einen Abschnitt „Ereigniszuordnung & Anpassung“. Hier können Sie definieren, wie PrestaShop-Aktionen GA4-Ereignissen zugeordnet werden und benutzerdefinierte Parameter hinzufügen.
- **A:** Für hochkomplexes benutzerdefiniertes Tracking, insbesondere mit `dataLayer`, müssen Sie möglicherweise die Funktionen dieses Moduls mit benutzerdefinierten Skripten in Ihrem Google Tag Manager-Container kombinieren.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen gedacht, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul `myanalytics` für PrestaShop wurde entwickelt, um eine robuste und flexible Google Analytics 4-Integration zu ermöglichen. Es folgt einem modularen, objektorientierten Ansatz und nutzt das MVC-Muster und das Hook-System von PrestaShop.

Wichtige Architekturkomponenten:

- **Hauptmodulklasse (`Myanalytics`):** Verwaltet Installation, Deinstallation, Hook-Registrierung und die primäre `getContent()`-Methode für die Back-Office-Konfiguration.
- **Tracker-Factory (`MyanalyticsTrackerFactory`):** Instanziiert dynamisch den geeigneten Tracking-Mechanismus (`gtag.js`, `dataLayer` oder `Measurement Protocol`) basierend auf der Modulkonfiguration.
- **Dedizierte Tracker-Klassen:** Jede Tracking-Methode (`MyanalyticsGtagTracker`, `MyanalyticsDataLayerTracker`, `MyanalyticsMpTracker`) implementiert `MyanalyticsTrackerInterface` und kapselt die Logik zum Senden von GA4-Ereignissen über ihre spezifische Methode.
- **Ereigniszuordnung & Data Layer Management:** Klassen wie `MyanalyticsEvents` und `MyanalyticsDataLayerTracker` sind für die Übersetzung von PrestaShop-Aktionen (z. B. Produktansicht, In den Warenkorb legen) in GA4-konforme Ereignisnamen und -parameter verantwortlich.
- **Diagnosetools:** Klassen wie `MyanalyticsDataQualityCoach`, `MyanalyticsCatalogDoctor` und `MyanalyticsHealthScore` bieten Back-Office-Einblicke in die Datenintegrität und den Tracking-Zustand.
- **Admin-Controller:** Verarbeiten AJAX-Anfragen für dynamische Inhalte im Back Office (z. B. Live-Statistiken, Diagnoseberichte).
- **Front-Controller:** Werden hauptsächlich für AJAX-Endpunkte verwendet, insbesondere für Measurement Protocol-Fallback oder zustimmungsbezogene Aktionen.
- **Smarty-Templates:** Werden zum Rendern sowohl der Back-Office-Konfigurationsansichten als auch der Front-Office-Tracking-Skripte verwendet, die über Hooks injiziert werden.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `controllers/front/ajax.php`
  - **Klassenname & Elternklasse:** `MyanalyticsAjaxModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Verarbeitet AJAX-Anfragen vom Front Office. Dies kann das Senden von Measurement Protocol-Ereignissen in bestimmten Szenarien (z. B. wenn clientseitiges Tracking blockiert ist), das Aktualisieren des Zustimmungsstatus oder andere dynamische Interaktionen umfassen, die keinen vollständigen Seiten-Reload erfordern. Es gibt typischerweise JSON-Antworten zurück.
- `controllers/front/index.php`
  - **Klassenname & Elternklasse:** `MyanalyticsIndexModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller könnte als Fallback oder als spezifischer Endpunkt für bestimmte Modulfunktionalitäten dienen, obwohl oft die Hauptmodulklasse die meisten Front-Office-Skriptinjektionen über Hooks handhabt. Er könnte für spezifische Weiterleitungen oder Datenverarbeitung verwendet werden, falls erforderlich.

#### Back-Office-Admin-Controller

- `controllers/admin/AdminMyanalyticsAjaxController.php`
  - **Klassenname & Elternklasse:** `AdminMyanalyticsAjaxController` erweitert `AdminController`.
  - **Tab-Name und verwaltete Entität:** Dieser Controller ist nicht direkt als Menü-Tab zugänglich. Er bedient AJAX-Anfragen von der Hauptkonfigurationsseite des Moduls (`getContent()`). Er verarbeitet dynamische Updates für Abschnitte wie den Datenqualitäts-Coach, den Katalog-Doktor, Live-Statistiken und die Schritte des Einrichtungsassistenten.
  - **Verantwortlichkeit:** Verarbeitet Anfragen für Diagnoseberichte, Live-Ereignisdaten und Assistenten-Schritt-Übermittlungen und gibt JSON-Daten zurück, um die Back-Office-Benutzeroberfläche zu aktualisieren.
- `controllers/admin/index.php`
  - **Klassenname & Elternklasse:** `AdminMyanalyticsIndexController` erweitert `AdminController`.
  - **Tab-Name und verwaltete Entität:** Ähnlich wie `AdminMyanalyticsAjaxController` ist dies wahrscheinlich ein interner Controller oder ein Platzhalter. Die primäre Back-Office-Konfiguration wird von der `getContent()`-Methode der Hauptmodulklasse `Myanalytics` gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

- `classes/autoload.php`: Standard-PrestaShop-Autoload-Datei für Modulklassen.
- `classes/index.php`: Leere Datei, gängige Praxis, um das Auflisten von Verzeichnissen zu verhindern.
- `classes/MyanalyticsCatalogDoctor.php`
  - **Was es tut:** Analysiert den PrestaShop-Produktkatalog auf Datenqualitätsprobleme, die für das GA4-Tracking relevant sind (z. B. fehlende Preise, Bilder, ungültige Kategorien).
  - **Wichtige öffentliche Methoden:** Methoden zum Ausführen von Überprüfungen und zum Abrufen von Berichten zur Kataloggesundheit.
- `classes/MyanalyticsConsent.php`
  - **Was es tut:** Verwaltet und interagiert mit Cookie-Zustimmungsmechanismen, um festzustellen, ob Analyse-Tracking basierend auf Benutzerentscheidungen zulässig ist.
  - **Wichtige öffentliche Methoden:** Methoden zum Überprüfen des Zustimmungsstatus, zum Festlegen der Zustimmung und zur potenziellen Integration mit Drittanbieter-Zustimmungsmodulen.
- `classes/MyanalyticsCurrencyHelper.php`
  - **Was es tut:** Bietet Hilfsfunktionen für die Handhabung der Währungsformatierung und -konvertierung, um sicherzustellen, dass GA4 Währungsdaten im richtigen Format erhält.
- `classes/MyanalyticsDataLayerTracker.php`
  - **Was es tut:** Implementiert `MyanalyticsTrackerInterface` für das `dataLayer`-Tracking. Es pusht GA4-Ereignisdaten in das JavaScript `dataLayer`-Array, wodurch sie für den Google Tag Manager verfügbar werden.
  - **Wichtige öffentliche Methoden:** Methoden zum Hinzufügen von Ereignissen zum dataLayer, zum Behandeln spezifischer E-Commerce-Ereignisse (z. B. `add_to_cart`, `purchase`).
- `classes/MyanalyticsDataQualityCoach.php`
  - **Was es tut:** Bietet ein Diagnosetool zur Identifizierung und Meldung potenzieller Datenqualitätsprobleme im GA4-Ereignisstrom oder in der Konfiguration.
  - **Wichtige öffentliche Methoden:** Methoden zum Ausführen von Datenqualitätsprüfungen und zum Generieren von Berichten.
- `classes/MyanalyticsEventId.php`
  - **Was es tut:** Wahrscheinlich eine Hilfsklasse zum Generieren eindeutiger Ereignis-IDs, die für die Deduplizierung in GA4 nützlich sein können, insbesondere mit dem Measurement Protocol.
- `classes/MyanalyticsEventMap.php`
  - **Was es tut:** Definiert die Zuordnung zwischen PrestaShop-Aktionen/Daten und Standard-GA4-Ereignisnamen und -parametern.
  - **Wichtige öffentliche Methoden:** Methoden zum Abrufen von Ereignisdefinitionen und Parameterzuordnungen.
- `classes/MyanalyticsEvents.php`
  - **Was es tut:** Eine zentrale Klasse zum Auslösen und Verwalten von GA4-Ereignissen innerhalb des Moduls. Sie orchestriert, welcher Tracker (gtag, datalayer, MP) welches Ereignis verarbeiten soll.
  - **Wichtige öffentliche Methoden:** Methoden wie `trackPageView()`, `trackAddToCart()`, `trackPurchase()` usw.
- `classes/MyanalyticsGtagTracker.php`
  - **Was es tut:** Implementiert `MyanalyticsTrackerInterface` für das `gtag.js`-Tracking. Es generiert und injiziert den notwendigen JavaScript-Code, um Ereignisse direkt über `gtag()` an GA4 zu senden.
  - **Wichtige öffentliche Methoden:** Methoden zum Generieren von `gtag()`-Aufrufen für verschiedene GA4-Ereignisse.
- `classes/MyanalyticsHealthScore.php`
  - **Was es tut:** Berechnet und zeigt einen „Gesundheits-Score“ für die GA4-Integration an, basierend auf verschiedenen Überprüfungen und Best Practices.
- `classes/MyanalyticsLiveStats.php`
  - **Was es tut:** Sammelt und liefert Echtzeitstatistiken über Ereignisse, die an GA4 gesendet werden, und zeigt sie im Back Office an.
- `classes/MyanalyticsMpClient.php`
  - **Was es tut:** Verarbeitet die eigentlichen HTTP-Anfragen zum Senden von Daten an Google Analytics 4 über das Measurement Protocol.
  - **Wichtige öffentliche Methoden:** Methoden zum Erstellen und Senden von Measurement Protocol-Payloads.
- `classes/MyanalyticsMpTracker.php`
  - **Was es tut:** Implementiert `MyanalyticsTrackerInterface` für das `Measurement Protocol`-Tracking. Es bereitet Ereignisdaten vor und verwendet `MyanalyticsMpClient`, um sie serverseitig zu senden.
  - **Wichtige öffentliche Methoden:** Methoden zum Formatieren und Senden serverseitiger Ereignisse.
- `classes/MyanalyticsProductIdResolver.php`
  - **Was es tut:** Löst verschiedene Produktkennungen (ID, Referenz, EAN, UPC) auf, um sicherzustellen, dass konsistente Produktdaten an GA4 gesendet werden.
- `classes/MyanalyticsPropertyRules.php`
  - **Was es tut:** Verwaltet die Logik für das Multi-Property-Tracking und definiert Regeln, welche Ereignisse an welche GA4-Properties gesendet werden.
- `classes/MyanalyticsTrackerFactory.php`
  - **Was es tut:** Eine Factory-Pattern-Klasse, die für die Erstellung und Rückgabe der korrekten `MyanalyticsTrackerInterface`-Implementierung basierend auf der Modulkonfiguration (gtag, datalayer oder MP) verantwortlich ist.
- `classes/MyanalyticsTrackerInterface.php`
  - **Was es tut:** Definiert die gemeinsame Schnittstelle, die alle GA4-Tracker-Klassen implementieren müssen, um Konsistenz bei der Behandlung von Ereignissen zu gewährleisten.
- `classes/MyanalyticsUserData.php`
  - **Was es tut:** Sammelt und formatiert benutzerspezifische Daten (z. B. Benutzer-ID, Demografie) für das GA4-Tracking unter Berücksichtigung der Datenschutzeinstellungen.

### 4.4 JavaScript-Assets (`views/js/`)

- `myanalytics/views/js/myanalytics-admin.js`
  - **Geltungsbereich:** Back Office.
  - **Was es tut:** Bietet interaktive Funktionen für die Back-Office-Konfigurationsseiten des Moduls. Dazu gehören die Verarbeitung von Formularübermittlungen, AJAX-Aufrufe für Diagnosetools (Datenqualitäts-Coach, Katalog-Doktor), die Aktualisierung von Live-Statistiken und die Verwaltung von Multi-Property-Regeln.
- `myanalytics/views/js/myanalytics-debug.js`
  - **Geltungsbereich:** Front Office (wenn der Debug-Modus aktiviert ist).
  - **Was es tut:** Injiziert ein Debug-Panel in das Front Office, das GA4-Ereignisse anzeigt, sobald sie ausgelöst werden. Es lauscht auf `gtag()`-Aufrufe oder `dataLayer.push()`-Ereignisse und rendert sie zur einfachen Überprüfung.
- `myanalytics/views/js/myanalytics-ghost.js`
  - **Geltungsbereich:** Front Office.
  - **Was es tut:** Dieses Skript könnte mit „Ghost“- oder „Shadow“-Tracking zusammenhängen, möglicherweise für Measurement Protocol-Fallback oder um Ereignisse zu erfassen, die sonst möglicherweise übersehen würden. Es könnte das Lauschen auf spezifische DOM-Ereignisse und das Auslösen serverseitiger Aufrufe beinhalten.
- `myanalytics/views/js/myanalytics-live.js`
  - **Geltungsbereich:** Back Office.
  - **Was es tut:** Versorgt die Funktion „Live-Statistiken“ im Back Office. Es verwendet wahrscheinlich AJAX, um regelmäßig aktuelle GA4-Ereignisse vom Server abzurufen und die Anzeige in Echtzeit zu aktualisieren.
- `myanalytics/views/js/myanalytics-wizard.js`
  - **Geltungsbereich:** Back Office.
  - **Was es tut:** Bietet die interaktive Logik für den Einrichtungsassistenten des Moduls, der den Benutzer durch die initialen Konfigurationsschritte führt, Eingaben validiert und Daten über AJAX übermittelt.
- `myanalytics/views/js/myanalytics.js`
  - **Geltungsbereich:** Front Office.
  - **Was es tut:** Die Haupt-JavaScript-Datei des Front Office. Sie verarbeitet die Kernlogik des clientseitigen GA4-Trackings, einschließlich:
    - Initialisierung von `gtag.js` oder `dataLayer`.
    - Lauschen auf DOM-Ereignisse (z. B. Klicks auf „In den Warenkorb“-Schaltflächen, Produktbildansichten).
    - Sammeln relevanter Produkt- und Benutzerdaten.
    - Pushen von Ereignissen in den `dataLayer` oder Aufrufen von `gtag()`-Befehlen.
    - Potenzielle Handhabung der Cookie-Zustimmungs-Integration.

### 4.5 CSS-Stylesheets (`views/css/`)

- `myanalytics/views/css/myanalytics-admin.css`
  - **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
  - **Was es tut:** Gestaltet die Konfigurationsseite des Moduls, einschließlich Tabs, Eingabefelder, Schaltflächen, Diagnoseberichte und Live-Statistikanzeigen, um eine konsistente und benutzerfreundliche Oberfläche innerhalb des PrestaShop Back Office zu gewährleisten.
- `myanalytics/views/css/myanalytics-debug.css`
  - **Geltungsbereich:** Front-Office-Kunden-Styling (wenn der Debug-Modus aktiviert ist).
  - **Was es tut:** Gestaltet das Front-Office-Debug-Panel, um es visuell unterscheidbar und lesbar für Entwickler und Administratoren zu machen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

- `myanalytics/views/templates/hook/debug.tpl`
  - **Hook:** Wahrscheinlich über `displayHeader` oder `displayFooter` bedingt injiziert, wenn der Debug-Modus aktiv ist.
  - **Ausgabe:** Die HTML-Struktur für das Front-Office-Debug-Panel.
- `myanalytics/views/templates/hook/displayOrderConfirmation.tpl`
  - **Hook:** `displayOrderConfirmation`.
  - **Ausgabe:** Der notwendige JavaScript-Code oder `dataLayer`-Pushes für das `purchase`-Ereignis, typischerweise einschließlich Transaktionsdetails, Produktinformationen und potenziell Measurement Protocol-Parametern.
- `myanalytics/views/templates/hook/ghost.tpl`
  - **Hook:** Könnte `displayHeader` oder `displayFooter` sein.
  - **Ausgabe:** JavaScript-Code im Zusammenhang mit „Ghost“-Tracking, möglicherweise für Measurement Protocol-Fallback oder erweiterte Ereigniserfassung.
- `myanalytics/views/templates/hook/header.tpl`
  - **Hook:** `displayHeader`.
  - **Ausgabe:** Das primäre `gtag.js`- oder `dataLayer`-Initialisierungsskript, einschließlich der GA4-Mess-ID(s) und aller globalen Konfigurationseinstellungen. Dies ist entscheidend für die anfängliche Seitenansichtsverfolgung.
- `myanalytics/views/templates/hook/mp-pageview.tpl`
  - **Hook:** Wahrscheinlich `displayHeader` oder `displayFooter` (bedingt für Measurement Protocol).
  - **Ausgabe:** Serverseitig gerenderter Code zum Senden eines `page_view`-Ereignisses über das Measurement Protocol, besonders nützlich, wenn clientseitiges Tracking blockiert oder die Zustimmung verweigert wird.
- `myanalytics/views/templates/hook/payment.tpl`
  - **Hook:** `displayPaymentTop` oder ähnliche zahlungsbezogene Hooks.
  - **Ausgabe:** JavaScript- oder `dataLayer`-Pushes für `add_payment_info`- oder `begin_checkout`-Ereignisse, die die Auswahl der Zahlungsmethode erfassen.
- `myanalytics/views/templates/hook/product-details.tpl`
  - **Hook:** `displayProductButtons`, `displayProductExtraContent` oder ähnliche Produktseiten-Hooks.
  - **Ausgabe:** JavaScript- oder `dataLayer`-Pushes für `view_item`- und `add_to_cart`-Ereignisse, einschließlich detaillierter Produktinformationen.

#### Admin-Templates (`views/templates/admin/`)

- `myanalytics/views/templates/admin/doctor.tpl`: Rendert die Oberfläche für den Katalog-Doktor, zeigt Berichte und Empfehlungen an.
- `myanalytics/views/templates/admin/dq.tpl`: Rendert die Oberfläche für den Datenqualitäts-Coach, zeigt Datenqualitätsprobleme an.
- `myanalytics/views/templates/admin/health.tpl`: Zeigt den Gesamt-Gesundheits-Score und verwandte Metriken für die GA4-Integration an.
- `myanalytics/views/templates/admin/linker-domains.tpl`: Rendert das Eingabefeld und die Liste zur Verwaltung von Cross-Domain-Linker-Domains.
- `myanalytics/views/templates/admin/live-maintain.tpl`: Wahrscheinlich ein Sub-Template für die Live-Statistiken, möglicherweise für Wartungsmeldungen oder Steuerelemente.
- `myanalytics/views/templates/admin/live.tpl`: Rendert die Hauptoberfläche für die Live-Statistiken-Funktion, zeigt Echtzeit-Ereignisdaten an.
- `myanalytics/views/templates/admin/measurement-ids.tpl`: Rendert den Abschnitt zur Verwaltung mehrerer GA4-Mess-IDs.
- `myanalytics/views/templates/admin/mode-context.tpl`: Bietet kontextbezogene Informationen oder Erklärungen für den gewählten Tracking-Modus.
- `myanalytics/views/templates/admin/mode-note-datalayer.tpl`: Spezifische Hinweise oder Anweisungen für den `dataLayer`-Tracking-Modus.
- `myanalytics/views/templates/admin/mode-note-gtag.tpl`: Spezifische Hinweise oder Anweisungen für den `gtag.js`-Tracking-Modus.
- `myanalytics/views/templates/admin/mode-note-mp.tpl`: Spezifische Hinweise oder Anweisungen für den `Measurement Protocol`-Tracking-Modus.
- `myanalytics/views/templates/admin/mode-picker.tpl`: Rendert die Optionsfelder oder das Dropdown zur Auswahl des GA4-Tracking-Modus.
- `myanalytics/views/templates/admin/properties-list.tpl`: Zeigt eine Liste der konfigurierten GA4-Properties an.
- `myanalytics/views/templates/admin/recent-events.tpl`: Ein Sub-Template zum Anzeigen einer Liste der letzten Ereignisse, oft in Live-Statistiken oder Debug-Ansichten verwendet.
- `myanalytics/views/templates/admin/tabs.tpl`: Rendert die Tab-Navigationsstruktur für die Konfigurationsseite des Moduls.
- `myanalytics/views/templates/admin/tag-chips.tpl`: Zeigt visuelle „Chips“ oder Labels für konfigurierte GA4-Tags/Properties an.
- `myanalytics/views/templates/admin/wizard.tpl`: Rendert die Gesamtstruktur und die Schritte des Einrichtungsassistenten des Moduls.

#### Front-Office-Templates (`views/templates/front/`)

Das Modul scheint keine dedizierten eigenständigen Front-Office-Seitentemplates zu haben, sondern verlässt sich stattdessen auf das Injizieren von Skripten und Daten über Hooks.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul speichert seine Konfiguration hauptsächlich in der `ps_configuration`-Tabelle von PrestaShop.
  - Es könnte auch benutzerdefinierte Tabellen erstellen für:
    - `ps_myanalytics_events`: Zum Protokollieren von Measurement Protocol-Ereignissen oder anderen internen Ereignisdaten für Debugging/Live-Statistiken.
    - `ps_myanalytics_properties`: Zum Speichern von Details zu mehreren GA4-Properties und deren zugehörigen Regeln.
    - `ps_myanalytics_consent`: Zum Speichern des Zustimmungsstatus oder zur Integration mit Zustimmungsmodulen.
    - `ps_myanalytics_health_log`: Zum Speichern von Ergebnissen aus Gesundheitsprüfungen und Datenqualitätsberichten.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Injiziert `gtag.js`- oder `dataLayer`-Initialisierungsskripte, globale GA4-Konfiguration und potenziell `page_view`-Ereignisse. |
| `displayFooter` | Vor dem schließenden `</body>`-Tag jeder Seite. | Injiziert zusätzliche Tracking-Skripte, Debug-Panels oder Fallback-Measurement Protocol-Aufrufe. |
| `displayOrderConfirmation` | Auf der Bestellbestätigungsseite nach einem erfolgreichen Kauf. | Sendet das entscheidende `purchase`-Ereignis an GA4, einschließlich Transaktionsdetails und Produktdaten. Hier wird oft das Measurement Protocol genutzt. |
| `displayProductButtons` | In der Nähe von Produktaktionsschaltflächen (z. B. „In den Warenkorb“) auf der Produktseite. | Injiziert JavaScript, um `add_to_cart`-Ereignisse zu erfassen. |
| `displayProductExtraContent` | Im zusätzlichen Inhaltsbereich der Produktseite. | Injiziert JavaScript für `view_item`-Ereignisse oder andere Interaktionen mit Produktdetails. |
| `displayPaymentTop` | Vor den Zahlungsoptionen auf der Checkout-Seite. | Erfasst `begin_checkout`- und `add_payment_info`-Ereignisse. |
| `actionFrontControllerSetMedia` | Wenn ein Front-Controller seine Medien-Assets festlegt. | Reiht modulspezifische JS/CSS-Dateien für das Front Office ein. |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller seine Medien-Assets festlegt. | Reiht modulspezifische JS/CSS-Dateien für das Back Office ein. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | Löst serverseitige Measurement Protocol `purchase`-Ereignisse aus, um die Datenerfassung auch bei clientseitigem Fehlschlag zu gewährleisten. |
| `actionObjectProductAddAfter` | Nachdem ein neues Produkt hinzugefügt wurde. | Löst potenziell Katalog-Doktor-Überprüfungen aus oder aktualisiert interne Produktdaten-Caches. |
| `actionObjectProductUpdateAfter` | Nachdem ein bestehendes Produkt aktualisiert wurde. | Ähnlich wie `actionObjectProductAddAfter`. |
| `actionObjectProductDeleteAfter` | Nachdem ein Produkt gelöscht wurde. | Bereinigt alle zugehörigen Tracking-Daten oder Caches. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und um sicherzustellen, dass Sie die neueste, kompatibelste Version des Moduls „Google Analytics 4 - gtag, MP & dataLayer Tracking“ verwenden, besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/).

MyPresta.eu bietet dedizierten Support für alle seine Module, um sicherzustellen, dass die Analyseintegration Ihres Shops robust und auf dem neuesten Stand der GA4-Standards und PrestaShop-Versionen bleibt.
