---
title: "Microsoft Advertising UET Tag & Conversions API - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Microsoft Advertising UET Tag & Conversions API von MyPresta.eu."
sidebar:
  label: "Microsoft Advertising UET Tag & Conversions API - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Microsoft Advertising UET Tag & Conversions API auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/microsoft-advertising-uet-tag-conversions-api.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/microsoft-advertising-uet-tag-conversions-api/)
>
> ---


# Microsoft Advertising UET Tag & Conversions API

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen wie cURL, JSON und OpenSSL sind für die korrekte Funktion des Moduls erforderlich, insbesondere für die Conversions API-Funktionen. Diese sind in den meisten modernen Hosting-Umgebungen standardmäßig aktiviert.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist die zentrale Anlaufstelle für die Einrichtung Ihres Microsoft Advertising Trackings. Sie finden eine Reihe von Registerkarten und Einstellungen, die Sie durch den Prozess führen sollen.

#### Hauptkonfigurations-Tab (Erstansicht)

- **Was diese Einstellung bewirkt:** Dieser Tab bietet typischerweise eine Übersicht und erste Einrichtungsoptionen, oft einschließlich eines Assistenten zur Vereinfachung der Erstkonfiguration.
- **Auswirkung einer Änderung dieser Einstellung:** Das Abschließen des Assistenten oder das Ausfüllen der anfänglichen Details aktiviert die grundlegende Tracking-Funktionalität und bereitet das Modul auf erweiterte Einstellungen vor.
- **Empfohlener Wert:** Befolgen Sie die Schritte des Assistenten sorgfältig.
- **Händlerszenario / Beispiel:** Wenn Sie das Modul zum ersten Mal installieren, fragt der Assistent nach Ihrer UET Tag ID und führt Sie durch die Auswahl Ihrer Tracking-Methode (UET Tag, Conversions API oder beides).

#### UET Tag ID

- **Was diese Einstellung bewirkt:** Dies ist Ihre eindeutige Kennung, die von Microsoft Advertising bereitgestellt wird. Sie teilt Microsoft mit, welchem Konto die Tracking-Daten zugeordnet werden sollen.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Bei korrekter Eingabe:* Das Modul bettet den UET Tag in Ihren Shop ein, sodass Microsoft Advertising das Nutzerverhalten verfolgen kann.
  - *Bei leerer oder falscher Eingabe:* Es findet kein UET Tag Tracking statt, und Ihre Microsoft Advertising-Kampagnen erhalten keine Front-Office-Konversionsdaten.
- **Empfohlener Wert:** Ihre exakte UET Tag ID aus Ihrem Microsoft Advertising-Konto.
- **Händlerszenario / Beispiel:** Sie haben ein Microsoft Advertising-Konto erstellt und einen UET Tag eingerichtet. Sie kopieren die ID (z.B. `12345678`) und fügen sie hier ein.

#### Tracking-Modus (UET Tag, Conversions API oder beides)

- **Was diese Einstellung bewirkt:** Bestimmt, wie Konversionsdaten an Microsoft Advertising gesendet werden.
  - **Nur UET Tag:** Traditionelles clientseitiges Tracking über JavaScript im Browser des Kunden.
  - **Nur Conversions API:** Serverseitiges Tracking, das Daten direkt von Ihrem PrestaShop-Server an Microsoft sendet. Widerstandsfähiger gegenüber Browser-Datenschutzeinstellungen.
  - **Beides (Hybrid):** Verwendet sowohl UET Tag als auch Conversions API, mit einem Mechanismus zur Deduplizierung von Ereignissen, um eine genaue Zählung zu gewährleisten, selbst wenn beide Methoden dieselbe Konversion melden.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Nur UET Tag:* Verlässt sich ausschließlich auf browserbasiertes Tracking, das von Ad-Blockern oder Datenschutzeinstellungen beeinträchtigt werden kann.
  - *Nur Conversions API:* Bietet ein robusteres Tracking, erfordert jedoch eine serverseitige Einrichtung und erfasst möglicherweise nicht alle clientseitigen Ereignisse (wie Seitenaufrufe) so einfach.
  - *Beides (Hybrid):* Bietet das umfassendste und zuverlässigste Tracking, indem es die Stärken beider Methoden kombiniert und gleichzeitig doppelte Konversionen verhindert.
- **Empfohlener Wert:** **Beides (Hybrid)** wird im Allgemeinen für maximale Genauigkeit und Widerstandsfähigkeit empfohlen.
- **Händlerszenario / Beispiel:** Sie möchten die genauesten Daten erhalten, daher wählen Sie „Beides (Hybrid)“, um sicherzustellen, dass Konversionen auch dann verfolgt werden, wenn ein Kunde einen Ad-Blocker verwendet.

#### Conversions API Access Token

- **Was diese Einstellung bewirkt:** Dies ist ein sicheres Token, das in Ihrem Microsoft Advertising-Konto generiert wird und Ihren PrestaShop-Shop autorisiert, Daten direkt über die Conversions API an die Server von Microsoft zu senden.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Bei korrekter Eingabe:* Aktiviert das serverseitige Tracking für die Conversions API.
  - *Bei leerer oder falscher Eingabe:* Die Conversions API funktioniert nicht, und serverseitige Konversionsdaten werden nicht gesendet.
- **Empfohlener Wert:** Ihr exaktes Conversions API Access Token aus Ihrem Microsoft Advertising-Konto.
- **Händlerszenario / Beispiel:** Sie haben ein Access Token in Ihrem Microsoft Advertising-Konto generiert (z.B. unter „Tools“ > „Conversion-Tracking“ > „Conversions API“). Sie fügen diese lange Zeichenfolge hier ein.

#### Erweiterte Conversions aktivieren

- **Was diese Einstellung bewirkt:** Wenn aktiviert, sendet diese Funktion gehashte Kundendaten (wie E-Mail-Adressen) zusammen mit Konversionsereignissen. Dies hilft Microsoft, Konversionen genauer zuzuordnen, insbesondere wenn Cookies eingeschränkt sind, und verbessert die Leistung Ihrer Kampagne.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Genauere Konversionszuordnung, was potenziell zu einer besseren Optimierung Ihrer Werbekampagnen führt.
  - *Wenn deaktiviert:* Konversionen verlassen sich ausschließlich auf Standard-Tracking-Methoden, die in bestimmten datenschutzorientierten Browserumgebungen weniger genau sein könnten.
- **Empfohlener Wert:** **JA** (Aktiviert), da dies die Datenzuordnung erheblich verbessert.
- **Händlerszenario / Beispiel:** Sie möchten Microsoft Advertising die bestmöglichen Daten zur Optimierung Ihrer Kampagnen zur Verfügung stellen, daher aktivieren Sie Erweiterte Conversions.

#### Integration des Einwilligungsmanagements

- **Was diese Einstellung bewirkt:** Dieses Modul kann sich in bestehende Cookie-Einwilligungsmodule (wie DSGVO-Module) integrieren, um sicherzustellen, dass der UET Tag nur ausgelöst wird, nachdem ein Kunde seine Einwilligung gegeben hat.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn aktiviert und integriert:* Der UET Tag respektiert die Einwilligungsentscheidungen des Kunden. Wenn ein Kunde Tracking-Cookies ablehnt, wird der UET Tag nicht geladen.
  - *Wenn deaktiviert oder nicht integriert:* Der UET Tag könnte unabhängig von der Einwilligung geladen werden, was möglicherweise zu Compliance-Problemen führt.
- **Empfohlener Wert:** **JA** (Aktiviert), wenn Sie ein Cookie-Einwilligungsmodul verwenden und Datenschutzbestimmungen (z.B. DSGVO, CCPA) einhalten müssen.
- **Händlerszenario / Beispiel:** Ihr Shop verwendet ein DSGVO-Modul. Sie aktivieren diese Einstellung, um sicherzustellen, dass Ihr Microsoft Advertising Tracking den Datenschutzgesetzen entspricht.

#### Debug-Modus

- **Was diese Einstellung bewirkt:** Aktiviert einen speziellen Modus, der detaillierte Informationen über den UET Tag und Conversions API-Ereignisse direkt auf Ihren Front-Office-Seiten anzeigt (nur für Sie, den Administrator, oder bestimmte IP-Adressen sichtbar). Dies ist von unschätzbarem Wert, um zu überprüfen, ob das Tracking korrekt eingerichtet ist.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Sie sehen ein Debug-Overlay oder Konsolenmeldungen im Front-Office Ihres Shops, die zeigen, welche Ereignisse verfolgt werden und welche Daten gesendet werden.
  - *Wenn deaktiviert:* Das Modul arbeitet still, ohne sichtbare Debug-Informationen.
- **Empfohlener Wert:** **NEIN** (Deaktiviert) für Live-Produktions-Shops. **JA** (Aktiviert) vorübergehend während der Einrichtung und Fehlerbehebung.
- **Händlerszenario / Beispiel:** Sie haben das Modul gerade installiert und möchten bestätigen, dass „In den Warenkorb“-Ereignisse korrekt gesendet werden. Sie aktivieren den Debug-Modus, legen ein Produkt in Ihren Warenkorb und überprüfen die Debug-Ausgabe.

#### Ereigniszuordnung (Erweitert)

- **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, anzupassen, wie spezifische PrestaShop-Aktionen (z.B. „Produkt in den Warenkorb gelegt“) Microsoft Advertising-Ereignisnamen (z.B. „add\_to\_cart“) zugeordnet werden. Sie können auch benutzerdefinierte Parameter definieren, die mit jedem Ereignis gesendet werden sollen.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Bei Konfiguration:* Stellt sicher, dass Ihre Ereignisse in Microsoft Advertising korrekt kategorisiert und mit relevanten Daten angereichert werden.
  - *Bei Fehlkonfiguration:* Ereignisse werden möglicherweise nicht verfolgt, oder die gesendeten Daten sind ungenau, was zu einer schlechten Kampagnenoptimierung führt.
- **Empfohlener Wert:** Verwenden Sie die Standardzuordnungen, es sei denn, Sie haben einen spezifischen Grund, diese basierend auf Ihrer Microsoft Advertising-Einrichtung zu ändern.
- **Händlerszenario / Beispiel:** Sie möchten die Marke des Produkts als benutzerdefinierten Parameter mit jedem „view\_item“-Ereignis senden. Sie würden diese Zuordnung hier konfigurieren.

#### Linker-Domains (Erweitert)

- **Was diese Einstellung bewirkt:** Wenn Sie mehrere Subdomains oder verwandte Websites haben, die denselben UET Tag teilen, hilft diese Einstellung sicherzustellen, dass Benutzersitzungen über diese Domains hinweg korrekt verknüpft werden.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Bei Konfiguration:* Ermöglicht eine nahtlose Verfolgung von Benutzerreisen über mehrere Domains unter Ihrer Kontrolle.
  - *Bei Nicht-Konfiguration (und Bedarf):* Benutzersitzungen könnten unterbrochen werden, was zu einer ungenauen Konversionszuordnung führt.
- **Empfohlener Wert:** Leer lassen, es sei denn, Sie betreiben mehrere Subdomains oder verwandte Websites, die ein Cross-Domain-Tracking benötigen.
- **Händlerszenario / Beispiel:** Sie haben Ihren Hauptshop unter `shop.example.com` und einen Blog unter `blog.example.com`, die beide denselben UET Tag verwenden. Sie würden `blog.example.com` zur Liste der Linker-Domains hinzufügen.

#### Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Hauptkonfiguration | UET Tag ID | Ihre Tag ID | Aktiviert UET Tag Tracking. Wesentlich für clientseitige Daten. |
| Hauptkonfiguration | Tracking-Modus | Beides (Hybrid) | Wählt UET Tag, Conversions API oder beides für die Datenübertragung. Hybrid ist am robustesten. |
| Hauptkonfiguration | Conversions API Access Token | Ihr Access Token | Autorisiert das serverseitige Senden von Daten an Microsoft. |
| Hauptkonfiguration | Erweiterte Conversions aktivieren | JA | Verbessert die Genauigkeit der Konversionszuordnung durch Senden gehashter Kundendaten. |
| Hauptkonfiguration | Integration des Einwilligungsmanagements | JA (falls zutreffend) | Stellt sicher, dass der UET Tag die Datenschutzentscheidungen des Kunden respektiert (DSGVO, CCPA). |
| Hauptkonfiguration | Debug-Modus | NEIN (JA zum Testen) | Zeigt Tracking-Daten im Front-Office zur Überprüfung an. |
| Hauptkonfiguration | Ereigniszuordnung | Standard | Passt an, wie PrestaShop-Aktionen Microsoft-Ereignissen zugeordnet werden. |
| Hauptkonfiguration | Linker-Domains | Leer (falls nicht benötigt) | Ermöglicht Cross-Domain-Tracking für verwandte Websites. |

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### 2.2.1 AdminMybingAjaxController (Back Office > Module > Microsoft Advertising UET Tag & Conversions API > Live-Statistiken / Gesundheitswert / Doktor / Datenqualität)

Dieser Controller steuert die dynamischen, interaktiven Bereiche der Modulkonfiguration und bietet Echtzeit-Einblicke und Diagnosewerkzeuge. Sie navigieren nicht zu einem separaten Menüpunkt dafür, sondern interagieren mit spezifischen Tabs innerhalb der Hauptmodulkonfiguration.

- **Bildschirmname & Menüpfad:** Dies sind typischerweise Unter-Tabs innerhalb der Hauptmodulkonfigurationsseite (z.B. „Live-Statistiken“, „Gesundheitswert“, „Datenqualitäts-Coach“, „Katalog-Doktor“).
- **Verfügbare Aktionen & Einstellungen:**
  - **Live-Statistiken:** Zeigt kürzlich an Microsoft Advertising gesendete Ereignisse an, wie Seitenaufrufe, In-den-Warenkorb-Legungen, Käufe usw., nahezu in Echtzeit. Dies hilft Ihnen zu bestätigen, dass Ereignisse korrekt ausgelöst werden.
  - **Gesundheitswert:** Analysiert Ihre Tracking-Einrichtung und vergibt eine Punktzahl basierend auf Best Practices, wobei potenzielle Probleme oder Verbesserungsmöglichkeiten hervorgehoben werden.
  - **Datenqualitäts-Coach:** Bietet spezifische Empfehlungen zur Verbesserung der Qualität und Vollständigkeit der Daten, die Sie an Microsoft senden, insbesondere für Erweiterte Conversions.
  - **Katalog-Doktor:** Hilft bei der Diagnose von Problemen mit Ihren Produktdaten, die die Produktfeed-Werbung oder das dynamische Remarketing beeinträchtigen könnten.
- **Auswirkung von Änderungen:** Die Interaktion mit diesen Bildschirmen liefert hauptsächlich Informationen und diagnostisches Feedback. Es gibt hier keine direkten „Einstellungen“ zu ändern, aber die gewonnenen Erkenntnisse fließen in Anpassungen ein, die Sie in der Hauptkonfiguration oder Ihrem Produktkatalog vornehmen könnten.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  - Überprüfen Sie regelmäßig die **Live-Statistiken**, nachdem Sie Änderungen vorgenommen oder neue Kampagnen gestartet haben, um sicherzustellen, dass Ereignisse verfolgt werden.
  - Überprüfen Sie regelmäßig den **Gesundheitswert** und den **Datenqualitäts-Coach** auf Empfehlungen zur Optimierung Ihrer Tracking-Einrichtung.
  - Wenn Sie Probleme mit produktbezogenen Anzeigen haben, konsultieren Sie den **Katalog-Doktor**.

#### 2.2.2 index.php (Back Office > Module > Microsoft Advertising UET Tag & Conversions API)

Dies bezieht sich auf den Haupteinstiegspunkt für die Back-Office-Oberfläche des Moduls, d.h. die Konfigurationsseite selbst. Alle in Abschnitt 4.1 beschriebenen Einstellungen werden über diese Hauptansicht verwaltet. Es gibt keinen separaten „index.php“-Bildschirm, zu dem man navigieren müsste, abgesehen von der anfänglichen Modulkonfiguration.

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Conversions werden in Microsoft Advertising nicht angezeigt. Was soll ich tun?**
A:

1. **UET Tag ID & Access Token überprüfen:** Überprüfen Sie nochmals, ob Ihre UET Tag ID und Ihr Conversions API Access Token in der Modulkonfiguration korrekt eingegeben wurden. Schon ein einziger Tippfehler kann das Tracking verhindern.
2. **Tracking-Modus überprüfen:** Stellen Sie sicher, dass Ihr „Tracking-Modus“ auf „Beides (Hybrid)“ eingestellt ist, um maximale Zuverlässigkeit zu gewährleisten.
3. **Debug-Modus aktivieren:** Aktivieren Sie den „Debug-Modus“ in den Moduleinstellungen und führen Sie einen Testkauf in Ihrem Shop durch. Suchen Sie nach dem Debug-Overlay oder den Konsolenmeldungen, um zu sehen, ob Ereignisse ausgelöst werden.
4. **Cache leeren:** Gehen Sie im PrestaShop Back Office zu **Erweiterte Einstellungen > Leistung** und leeren Sie den Smarty-Cache sowie alle anderen Caches. Manchmal können alte Einstellungen bestehen bleiben.
5. **Microsoft Advertising-Konto überprüfen:** Melden Sie sich in Ihrem Microsoft Advertising-Konto an und überprüfen Sie den UET Tag-Status und die Einrichtung der Conversion-Ziele. Stellen Sie sicher, dass Ihre Conversion-Ziele korrekt konfiguriert sind, um den vom Modul gesendeten Ereignissen zu entsprechen (z.B. „Kauf“).

**F: Das Modul meldet „Einwilligungsmanagement-Integration“ ist aktiviert, aber ich habe kein DSGVO-Modul. Ist das ein Problem?**
A: Wenn Sie kein dediziertes Cookie-Einwilligungsmodul installiert und konfiguriert haben, hat diese Einstellung keine praktische Auswirkung. Das Modul geht standardmäßig von einer Einwilligung aus. Für die rechtliche Compliance (z.B. DSGVO, CCPA) wird jedoch dringend empfohlen, ein geeignetes Cookie-Einwilligungsmodul zu verwenden. Wenn Sie später eines installieren, integriert sich dieses Modul automatisch damit.

**F: Mein benutzerdefiniertes Theme sieht nach der Installation des Moduls etwas seltsam aus, oder ich sehe eine leere Seite.**
A: Dieses Modul arbeitet hauptsächlich im Hintergrund und sollte das visuelle Erscheinungsbild Ihres Themes nicht beeinträchtigen.

1. **Cache leeren:** Die häufigste Lösung für Anzeigeprobleme nach der Modulinstallation ist das Leeren Ihres PrestaShop-Caches (**Erweiterte Einstellungen > Leistung**).
2. **Auf Konflikte prüfen:** Wenn das Problem weiterhin besteht, deaktivieren Sie vorübergehend andere kürzlich installierte Module, um nach Konflikten zu suchen.
3. **PHP-Fehler:** Wenn Sie eine leere Seite sehen, aktivieren Sie die PHP-Fehlerberichterstattung auf Ihrem Server (oder überprüfen Sie die Fehlerprotokolle Ihres Servers), um kritische Fehler zu identifizieren.
   Wenn das Problem weiterhin besteht, wenden Sie sich an den MyPresta.eu-Support mit Details zu Ihrem Theme und eventuellen Fehlermeldungen.

**F: Wie übersetze ich die Texte des Moduls in andere Sprachen?**
A:

1. Gehen Sie im PrestaShop Back Office zu **International > Übersetzungen**.
2. Wählen Sie „Übersetzungen installierter Module“ als Übersetzungstyp.
3. Wählen Sie Ihr Theme, die Sprache, in die Sie übersetzen möchten, und dann „Microsoft Advertising UET Tag & Conversions API“ aus der Modulliste.
4. Sie können dann alle sichtbaren Zeichenfolgen übersetzen, die vom Modul verwendet werden.

**F: Warum zeigt der „Datenqualitäts-Coach“ oder „Gesundheitswert“ Warnungen an?**
A: Diese Tools sollen Ihnen helfen, Ihr Tracking zu optimieren. Warnungen weisen oft auf Folgendes hin:

- **Fehlende erweiterte Konversionsdaten:** Stellen Sie sicher, dass Kundendaten (wie E-Mail) verfügbar sind und gesendet werden.
- **Produktdatenprobleme:** Ihr Produktkatalog könnte fehlende GTINs, MPNs oder andere Identifikatoren aufweisen, die für die Produktfeed-Werbung entscheidend sind.
- **Geringes Ereignisvolumen:** Wenn Ihr Shop sehr wenig Traffic hat, haben die Tools möglicherweise nicht genügend Daten, um eine umfassende Analyse zu liefern.
  Beheben Sie die spezifischen Empfehlungen der Tools, um Ihre Datenqualität und Tracking-Gesundheit zu verbessern.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul `Microsoft Advertising UET Tag & Conversions API` (`mybing`) ist nach dem MVC-Muster (Model-View-Controller) von PrestaShop aufgebaut, mit einem starken Fokus auf Modularität und Erweiterbarkeit. Es verwendet ein Factory-Muster für die Tracker-Instanziierung (`MybingTrackerFactory`), um verschiedene Tracking-Modi (UET, CAPI, Hybrid) zu unterstützen, und nutzt ein robustes Ereignissystem (`MybingEvents`), um verschiedene E-Commerce-Aktionen zu erfassen. Datenqualität und Diagnose werden von dedizierten Klassen (`MybingHealthScore`, `MybingDataQualityCoach`, `MybingCatalogDoctor`) behandelt. Das Modul integriert sich in das Hook-System von PrestaShop für die Front-Office-Ereignisinjektion und verwendet dedizierte Admin-Controller für seine erweiterten Konfigurations- und Diagnosewerkzeuge.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `mybing/controllers/front/ajax.php`
  - **Klassenname:** `MybingAjaxModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Behandelt AJAX-Anfragen vom Front-Office, hauptsächlich zum Senden clientseitiger Ereignisse oder Daten, die nicht direkt vom UET-Tag verarbeitet werden können (z.B. für die Integration des Einwilligungsmanagements oder spezifische Datenerfassung vor einer Seitenumleitung). Es kann auch zum Senden von CAPI-Ereignissen verwendet werden, die clientseitig ausgelöst werden, aber eine serverseitige Verarbeitung erfordern.
- `mybing/controllers/front/cron.php`
  - **Klassenname:** `MybingCronModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Bietet einen Endpunkt für einen Cron-Job. Dies wird typischerweise für serverseitige Aufgaben verwendet, die regelmäßig ausgeführt werden müssen, wie das Senden verzögerter Conversions API-Ereignisse, das Synchronisieren von Daten oder das Ausführen von Wartungsaufgaben im Zusammenhang mit der Funktionalität des Moduls.
- `mybing/controllers/front/index.php`
  - **Klassenname:** `MybingIndexModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Ein generischer Front-Controller, oft als Fallback oder für einfache, nicht-AJAX-Front-Office-Interaktionen verwendet. In diesem Modul könnte er für spezifische Weiterleitungen oder zur Bearbeitung anfänglicher Anfragen im Zusammenhang mit der Tracking-Einrichtung verwendet werden.

#### Back-Office-Admin-Controller

- `mybing/controllers/admin/AdminMybingAjaxController.php`
  - **Klassenname:** `AdminMybingAjaxController` (erweitert `AdminController`)
  - **Tab-Name:** Kein eigenständiger Tab, sondern ein AJAX-Endpunkt für die Hauptmodulkonfiguration.
  - **Verwaltete Entität:** Behandelt das dynamische Laden und Verarbeiten von Daten für die Diagnose- und Statistik-Tabs des Moduls (Live-Statistiken, Gesundheitswert, Datenqualitäts-Coach, Katalog-Doktor). Es verarbeitet Anfragen für Ereignisprotokolle, Gesundheitsprüfungen und Datenqualitätsberichte und gibt JSON-Antworten an das Admin-JavaScript zurück.
- `mybing/controllers/admin/index.php`
  - **Klassenname:** `AdminMybingIndexController` (erweitert `AdminController`)
  - **Tab-Name:** Kein eigenständiger Tab. Dies ist ein Platzhalter oder ein generischer Admin-Controller, der für spezifische interne Weiterleitungen oder Aktionen innerhalb der Admin-Oberfläche des Moduls verwendet werden könnte, aber die primäre Konfiguration wird durch die `getContent()`-Methode der Hauptmodulklasse gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

- `mybing/classes/autoload.php`: Standard-PrestaShop-Autoload-Datei, die sicherstellt, dass Modulklassen korrekt geladen werden.
- `mybing/classes/index.php`: Platzhalterdatei, oft um das Auflisten von Verzeichnissen zu verhindern.
- `mybing/classes/MybingCapiClient.php`: Verwaltet die Kommunikation mit dem Microsoft Advertising Conversions API-Endpunkt. Kapselt HTTP-Anfragen, Authentifizierung (Access Token) und Datenformatierung für die serverseitige Ereignisübermittlung.
- `mybing/classes/MybingCapiTracker.php`: Implementiert `MybingTrackerInterface` für serverseitiges (Conversions API) Tracking. Verantwortlich für das Sammeln von Ereignisdaten, deren Vorbereitung für den CAPI-Client und das Senden.
- `mybing/classes/MybingCatalogDoctor.php`: Bietet Diagnoselogik zur Analyse der Produktdatenqualität und zur Identifizierung von Problemen, die Produktfeeds oder dynamisches Remarketing in Microsoft Advertising beeinträchtigen könnten.
- `mybing/classes/MybingConsent.php`: Verwaltet die Integration mit Cookie-Einwilligungsmodulen. Bestimmt, ob die Benutzerzustimmung für das Tracking erteilt wurde und steuert entsprechend das Auslösen des UET-Tags.
- `mybing/classes/MybingCurrencyHelper.php`: Dienstprogrammklasse zur Handhabung von Währungsumrechnungen und -formatierungen, um sicherzustellen, dass Ereigniswerte korrekt an Microsoft Advertising gesendet werden.
- `mybing/classes/MybingDataQualityCoach.php`: Analysiert die Qualität und Vollständigkeit der für Ereignisse gesendeten Daten, insbesondere für erweiterte Conversions, und gibt Empfehlungen zur Verbesserung.
- `mybing/classes/MybingEventId.php`: Generiert und verwaltet eindeutige Ereignis-IDs zur Deduplizierung, entscheidend für hybrides Tracking (UET + CAPI).
- `mybing/classes/MybingEventMap.php`: Definiert die Zuordnung zwischen PrestaShop-Aktionen (z.B. `actionCartSave`) und Microsoft Advertising-Ereignisnamen (z.B. `add_to_cart`), einschließlich benutzerdefinierter Parameter.
- `mybing/classes/MybingEvents.php`: Zentrale Klasse zum Definieren und Auslösen aller verfolgten E-Commerce-Ereignisse (z.B. `PageView`, `AddToCart`, `Purchase`). Sie fungiert als Ereignis-Dispatcher innerhalb des Moduls.
- `mybing/classes/MybingHealthScore.php`: Berechnet einen „Gesundheitswert“ für die gesamte Tracking-Einrichtung, der die Konfiguration, Datenqualität und das Auslösen von Ereignissen bewertet.
- `mybing/classes/MybingHybridTracker.php`: Implementiert `MybingTrackerInterface` für hybrides Tracking. Orchestriert sowohl UET Tag- als auch Conversions API-Tracking und stellt die Ereignis-Deduplizierung mithilfe von `event_id` sicher.
- `mybing/classes/MybingLiveStats.php`: Sammelt und liefert Echtzeitstatistiken zu verfolgten Ereignissen, die in der Admin-Oberfläche angezeigt werden.
- `mybing/classes/MybingProductIdResolver.php`: Hilft bei der Auflösung und Formatierung von Produkt-IDs gemäß den Anforderungen von Microsoft Advertising (z.B. GTIN, MPN, custom\_label).
- `mybing/classes/MybingPropertyRules.php`: Definiert Regeln und Logik zum Extrahieren und Formatieren verschiedener Ereigniseigenschaften (z.B. Produktpreis, Menge, Kategorie) für Microsoft Advertising.
- `mybing/classes/MybingTrackerFactory.php`: Factory-Klasse, die für die Erstellung der geeigneten Tracker-Instanz (`MybingUetTracker`, `MybingCapiTracker` oder `MybingHybridTracker`) basierend auf der Modulkonfiguration verantwortlich ist.
- `mybing/classes/MybingTrackerInterface.php`: Definiert den Vertrag für alle Tracker-Klassen, um eine konsistente Schnittstelle für Ereignis-Tracking-Methoden zu gewährleisten.
- `mybing/classes/MybingUetTracker.php`: Implementiert `MybingTrackerInterface` für clientseitiges (UET Tag) Tracking. Verantwortlich für die Generierung des JavaScript-Codes, der in das Front-Office injiziert werden soll.
- `mybing/classes/MybingUserData.php`: Sammelt und formatiert benutzerspezifische Daten (z.B. E-Mail, Telefon, Adresse) für erweiterte Conversions, einschließlich Hashing.

### 4.4 JavaScript-Assets (`views/js/`)

- `mybing/views/js/mybing-admin.js`: Back-Office-JavaScript für allgemeine Admin-Funktionalität, Formularinteraktionen und dynamische Updates innerhalb der Modulkonfigurationsseite.
- `mybing/views/js/mybing-debug.js`: Front-Office-JavaScript speziell für den Debug-Modus, das Tracking-Informationen und Ereignis-Payloads für den Administrator anzeigt.
- `mybing/views/js/mybing-ghost.js`: Front-Office-JavaScript, potenziell zur Handhabung von „Ghost“-Ereignissen oder spezifischen clientseitigen Interaktionen, die ohne direkte Benutzeraktion verfolgt werden müssen.
- `mybing/views/js/mybing-live.js`: Back-Office-JavaScript für den Tab „Live-Statistiken“, das AJAX-Anfragen an `AdminMybingAjaxController` verarbeitet und den Live-Ereignis-Feed aktualisiert.
- `mybing/views/js/mybing-tcf.js`: Front-Office-JavaScript zur Integration mit dem Transparency and Consent Framework (TCF) oder anderen Einwilligungsmanagement-Plattformen, um sicherzustellen, dass der UET Tag nur mit Einwilligung ausgelöst wird.
- `mybing/views/js/mybing-wizard.js`: Back-Office-JavaScript für den initialen Einrichtungsassistenten, der den Händler durch die Konfigurationsschritte führt.
- `mybing/views/js/mybing.js`: Haupt-Front-Office-JavaScript-Datei. Enthält die Kernlogik zur Initialisierung des UET Tags, zur Erfassung clientseitiger Ereignisse (z.B. `add_to_cart`) und zum Senden von Daten an den UET Tag oder den AJAX-Controller des Moduls zur CAPI-Verarbeitung. Es bindet an verschiedene DOM-Ereignisse und PrestaShops `prestashop.on`-Ereignisse.

### 4.5 CSS-Stylesheets (`views/css/`)

- `mybing/views/css/mybing-admin.css`: Back-Office-CSS zur Gestaltung der Konfigurationsseite des Moduls, der Diagnosetools und des Assistenten, um eine konsistente und benutzerfreundliche Admin-Oberfläche zu gewährleisten.
- `mybing/views/css/mybing-debug.css`: Front-Office-CSS zur Gestaltung des Debug-Overlays, das Tracking-Informationen für den Administrator deutlich sichtbar macht, ohne das Design des Shops zu stören.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

- `mybing/views/templates/hook/capi-pageview.tpl`: Rendert ein verstecktes Element oder Skript, um ein serverseitiges PageView-Ereignis über CAPI auszulösen, oft verwendet, wenn der UET-Tag blockiert sein könnte.
- `mybing/views/templates/hook/debug.tpl`: Rendert die HTML-Struktur für das Front-Office-Debug-Overlay, das Ereignisdaten anzeigt.
- `mybing/views/templates/hook/displayOrderConfirmation.tpl`: Wird in den `displayOrderConfirmation`-Hook injiziert. Rendert das UET Tag-Kaufereignisskript und/oder löst das CAPI-Kaufereignis nach einer erfolgreichen Bestellung aus.
- `mybing/views/templates/hook/ghost.tpl`: Rendert ein verstecktes Skript oder Element für „Ghost“-Tracking, potenziell für spezifische Hintergrundereignisse oder Datenerfassung.
- `mybing/views/templates/hook/header.tpl`: Wird in den `displayHeader`-Hook injiziert. Rendert das Haupt-UET Tag-Basisskript, die Integration des Einwilligungsmanagements und initiale PageView-Ereignisse.
- `mybing/views/templates/hook/payment.tpl`: Potenziell für die Verfolgung von Ereignissen im Zusammenhang mit der Auswahl oder Initiierung einer Zahlungsmethode verwendet, obwohl `displayOrderConfirmation` für den endgültigen Kauf häufiger ist.
- `mybing/views/templates/hook/product-details.tpl`: Wird in einen Produktdetailseiten-Hook injiziert (z.B. `displayProductButtons` oder `displayProductExtraContent`). Rendert Skripte für `view_item`-Ereignisse und `add_to_cart`-Ereignis-Listener.

#### Admin-Templates (`views/templates/admin/`)

- `mybing/views/templates/admin/consent-guide.tpl`: Zeigt Anleitungen und Informationen zur Integration des Einwilligungsmanagements an.
- `mybing/views/templates/admin/doctor.tpl`: Rendert die Oberfläche für das Diagnosewerkzeug „Katalog-Doktor“.
- `mybing/views/templates/admin/dq.tpl`: Rendert die Oberfläche für die Empfehlungen des „Datenqualitäts-Coachs“.
- `mybing/views/templates/admin/health.tpl`: Rendert die Oberfläche für die Übersicht des „Gesundheitswerts“.
- `mybing/views/templates/admin/linker-domains.tpl`: Rendert das Eingabefeld und die Erklärung zur Konfiguration von Linker-Domains.
- `mybing/views/templates/admin/live-maintain.tpl`: Rendert eine Wartungsmeldung oder den Status für die Live-Statistikfunktion.
- `mybing/views/templates/admin/live.tpl`: Rendert die Oberfläche für „Live-Statistiken“, die aktuelle Ereignisse anzeigt.
- `mybing/views/templates/admin/mode-context.tpl`: Bietet kontextbezogene Informationen zum gewählten Tracking-Modus.
- `mybing/views/templates/admin/mode-note-both.tpl`: Zeigt eine spezifische Notiz oder Erklärung an, wenn der Modus „Beides (Hybrid)“ ausgewählt ist.
- `mybing/views/templates/admin/mode-note-capi.tpl`: Zeigt eine spezifische Notiz oder Erklärung an, wenn der Modus „Nur Conversions API“ ausgewählt ist.
- `mybing/views/templates/admin/mode-note-uet.tpl`: Zeigt eine spezifische Notiz oder Erklärung an, wenn der Modus „Nur UET Tag“ ausgewählt ist.
- `mybing/views/templates/admin/mode-picker.tpl`: Rendert die Optionsfelder oder das Dropdown zur Auswahl des Tracking-Modus.
- `mybing/views/templates/admin/properties-list.tpl`: Rendert eine Liste oder Tabelle von Ereigniseigenschaften und deren Werten zur Konfiguration oder Anzeige.
- `mybing/views/templates/admin/recent-events.tpl`: Rendert eine Tabelle oder Liste der kürzlich verfolgten Ereignisse, oft Teil der „Live-Statistiken“.
- `mybing/views/templates/admin/tabs.tpl`: Rendert die Tab-Navigationsstruktur für die Konfigurationsseite des Moduls (z.B. Allgemein, Live-Statistiken, Gesundheitswert).
- `mybing/views/templates/admin/tag-chips.tpl`: Rendert visuelle „Chips“ oder Indikatoren für konfigurierte UET Tag IDs.
- `mybing/views/templates/admin/tag-ids.tpl`: Rendert das Eingabefeld für UET Tag IDs.
- `mybing/views/templates/admin/wizard.tpl`: Rendert die schrittweise Oberfläche für den initialen Einrichtungsassistenten.

#### Front-Office-Templates (`views/templates/front/`)

- Keine dedizierten eigenständigen Seitenvorlagen identifiziert. Die Front-Office-Darstellung erfolgt hauptsächlich über Hook-Templates.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Das Modul erstellt keine explizit benutzerdefinierten SQL-Tabellen basierend auf dem bereitgestellten Inventar. Konfigurationseinträge werden in der `ps_configuration`-Tabelle von PrestaShop gespeichert, wobei Schlüssel mit `MYBING_` präfixiert sind (z.B. `MYBING_UET_ID`, `MYBING_CAPI_TOKEN`, `MYBING_TRACKING_MODE`).

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Injiziert das Basis-UET Tag-JavaScript, initialisiert das Einwilligungsmanagement und löst `PageView`-Ereignisse aus. |
| `displayOrderConfirmation` | Auf der Bestellbestätigungsseite nach einem erfolgreichen Kauf. | Löst `Purchase`-Ereignisse für UET Tag und Conversions API aus, einschließlich Bestelldetails. |
| `actionFrontControllerSetMedia` | Wenn ein Front-Controller seine Medien-Assets festlegt. | Injiziert modulspezifisches JavaScript und CSS in das Front-Office. |
| `actionCartSave` | Wenn ein Produkt zum Warenkorb hinzugefügt oder daraus entfernt wird. | Löst `AddToCart`- oder `RemoveFromCart`-Ereignisse aus. |
| `actionProductAdd` | Wenn ein Produkt zum Warenkorb hinzugefügt wird (spezifisch für einige Themes/Module). | Alternativer oder ergänzender Hook für `AddToCart`-Ereignisse. |
| `actionProductUpdate` | Wenn ein Produkt im Back Office aktualisiert wird. | Potenziell für den `Catalog Doctor` verwendet, um die Produktdatenqualität neu zu bewerten. |
| `actionObjectProductUpdateAfter` | Nachdem ein Produkt-`ObjectModel` aktualisiert wurde. | Ähnlich wie `actionProductUpdate`, für Datenqualitätsprüfungen oder Cache-Invalidierung. |
| `actionObjectOrderAddAfter` | Nachdem ein Bestell-`ObjectModel` hinzugefügt wurde. | Löst serverseitige `Purchase`-Ereignisse über die Conversions API aus, um ein robustes Tracking zu gewährleisten. |
| `actionObjectOrderUpdateAfter` | Nachdem ein Bestell-`ObjectModel` aktualisiert wurde. | Potenziell für die Verfolgung von Bestellstatusänderungen (z.B. Rückerstattung, Stornierung), falls in Microsoft Ads konfiguriert. |
| `displayProductExtraContent` | Auf der Produktseite, oft unterhalb des Hauptinhalts. | Kann verwendet werden, um produktspezifische Tracking-Skripte oder Daten für `ViewItem`-Ereignisse zu injizieren. |
| `displayFooter` | Am Ende des `<body>`-Abschnitts auf jeder Front-Office-Seite. | Kann für verzögertes Skriptladen oder zusätzliche Tracking-Elemente verwendet werden. |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller seine Medien-Assets festlegt. | Injiziert modulspezifisches JavaScript und CSS in das Back Office für die Konfigurationsseite. |
| `actionAdminMybingAjaxController` | Benutzerdefinierter Hook für `AdminMybingAjaxController` zur Handhabung spezifischer AJAX-Aktionen. | Intern für dynamische Updates und Datenabrufe in den Diagnose-Tabs des Moduls verwendet. |
| `actionModuleInstall` | Während der Modulinstallation. | Führt die initiale Einrichtung durch, erstellt Konfigurationseinträge und registriert Hooks. |
| `actionModuleUninstall` | Während der Moduldeinstallation. | Bereinigt Konfigurationseinträge und deregistriert Hooks. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Entwickler-Support besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei technischen Problemen oder Fragen zur Funktionalität des Moduls gerne zur Verfügung.
