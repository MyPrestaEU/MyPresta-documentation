---
title: "Pinterest Tag & Conversions API – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Pinterest Tag & Conversions API von MyPresta.eu."
sidebar:
  label: "Pinterest Tag & Conversions API – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Pinterest Tag & Conversions API auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/pinterest-tag-conversions-api.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/pinterest-tag-conversions-api/)
>
> ---


# Pinterest Tag & Conversions API

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL). Ihr Server muss in der Lage sein, ausgehende HTTP-Anfragen an die API-Endpunkte von Pinterest zu stellen.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist die zentrale Anlaufstelle für die Einrichtung Ihres Pinterest-Trackings. Sie finden verschiedene Abschnitte und Registerkarten zur Verwaltung Ihres Pinterest Tags, der Conversions API und der Datenqualität.

#### Allgemeine Einstellungen & Tracking-Modus

- **Pinterest Tag ID (Erforderlich)**

  - **Was diese Einstellung bewirkt:** Dies ist Ihre eindeutige Kennung, die von Pinterest bereitgestellt wird. Sie teilt Pinterest mit, zu welchem Anzeigenkonto Ihre Website-Daten gehören.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Wenn eingegeben:* Ermöglicht dem Modul, Daten an Ihr Pinterest-Anzeigenkonto zu senden. Ohne sie kann kein Tracking erfolgen.
    - *Wenn leer:* Das Modul kann keine Daten an Pinterest senden.
  - **Empfohlener Wert:** Ihre Pinterest Tag ID. Sie finden diese in Ihrem Pinterest Ads Manager unter „Anzeigen“ > „Conversions“ > „Pinterest Tag“.
  - **Händlerszenario / Beispiel:** Sie haben gerade ein Pinterest Ads-Konto erstellt und müssen Ihren Shop damit verknüpfen. Kopieren Sie die Tag ID von Pinterest und fügen Sie sie hier ein.
- **Tracking-Modus**

  - **Was diese Einstellung bewirkt:** Bestimmt, wie Ihr Shop Daten an Pinterest sendet. Sie können zwischen dem traditionellen Pinterest Tag (browserseitig), der robusteren Conversions API (serverseitig) oder einer Kombination aus beidem wählen.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Pinterest Tag (Browser-seitig):* Daten werden direkt vom Browser des Kunden gesendet. Dies ist einfacher, kann aber durch Ad-Blocker oder Browser-Datenschutzeinstellungen beeinträchtigt werden.
    - *Conversions API (Server-seitig):* Daten werden direkt von Ihrem PrestaShop-Server an Pinterest gesendet. Dies ist zuverlässiger und weniger anfällig für Blockierungen, was eine bessere Datengenauigkeit bietet.
    - *Beide (Hybrid mit Deduplizierung):* Daten werden über beide Methoden gesendet. Das Modul fügt jedem Ereignis automatisch eine eindeutige `event_id` hinzu, sodass Pinterest doppelte Ereignisse identifizieren und ignorieren kann, um maximale Datenabdeckung ohne Überzählung zu gewährleisten.
  - **Empfohlener Wert:** **Beide (Hybrid mit Deduplizierung)** für die zuverlässigste und umfassendste Nachverfolgung.
  - **Händlerszenario / Beispiel:** Sie möchten sicherstellen, dass Ihre Pinterest-Kampagnen so genau wie möglich sind, auch bei zunehmenden Datenschutzmaßnahmen. Die Wahl von „Beide“ bietet das Beste aus beiden Welten.

#### Conversions API (CAPI) Einstellungen (Sichtbar, wenn CAPI oder Beide Modus ausgewählt ist)

- **Conversions API Access Token (Erforderlich für CAPI)**

  - **Was diese Einstellung bewirkt:** Dies ist ein sicheres Token, das Ihren Server authentifiziert, wenn Daten direkt an die Conversions API von Pinterest gesendet werden. Es ist wie ein Passwort für Ihren Server, um mit Pinterest zu kommunizieren.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Wenn eingegeben:* Ermöglicht Ihrem Server, Daten über die Conversions API zu senden.
    - *Wenn leer:* Das Conversions API-Tracking funktioniert nicht, selbst wenn es als Tracking-Modus ausgewählt ist.
  - **Empfohlener Wert:** Ihr Pinterest Conversions API Access Token. Generieren Sie diesen in Ihrem Pinterest Ads Manager unter „Anzeigen“ > „Conversions“ > „Conversions API“.
  - **Händlerszenario / Beispiel:** Sie haben sich für die Verwendung der Conversions API für eine zuverlässigere Nachverfolgung entschieden. Sie generieren dieses Token in Pinterest und fügen es hier ein.
- **Enhanced Match für CAPI aktivieren**

  - **Was diese Einstellung bewirkt:** Wenn aktiviert, sendet das Modul zusätzliche Kundeninformationen (wie E-Mail, Telefonnummer, Name, Adresse – alle aus Datenschutzgründen gehasht) mit Conversions API-Ereignissen. Dies hilft Pinterest, Ereignisse genauer bestimmten Benutzern zuzuordnen, auch wenn diese nicht bei Pinterest angemeldet sind.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Verbessert die Genauigkeit der Ereigniszuordnung auf Pinterest, was zu einer besseren Zielgruppenansprache und Kampagnenoptimierung führt.
    - *Wenn deaktiviert:* Es werden nur grundlegende Ereignisdaten gesendet, was die Zuordnungsgenauigkeit potenziell verringert.
  - **Empfohlener Wert:** **JA**. Dies verbessert die Datenqualität und Anzeigenleistung erheblich.
  - **Händlerszenario / Beispiel:** Sie möchten sicherstellen, dass Pinterest Verkäufe Ihren Anzeigen genau zuordnen kann, auch wenn Kunden verschiedene Geräte oder Browser verwenden. Enhanced Match hilft, diese Lücken zu schließen.

#### Datenschutz & Einwilligung

- **Mit Cookie-Einwilligungsmodul integrieren**
  - **Was diese Einstellung bewirkt:** Wenn Sie ein separates Cookie-Einwilligungsmodul verwenden (z. B. ein DSGVO-Konformitätsmodul), stellt die Aktivierung dieser Option sicher, dass das Pinterest-Tracking erst ausgelöst wird, nachdem der Kunde seine Einwilligung erteilt hat.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Pinterest-Tracking respektiert die Einwilligung des Kunden aus Ihrem Cookie-Modul. Wenn die Einwilligung verweigert wird, werden keine Pinterest-Daten gesendet.
    - *Wenn deaktiviert:* Das Pinterest-Tracking wird unabhängig von anderen Cookie-Einwilligungseinstellungen ausgelöst, was möglicherweise zu Compliance-Problemen führt.
  - **Empfohlener Wert:** **JA**, wenn Sie ein Cookie-Einwilligungsmodul verwenden. **NEIN**, wenn Sie keines verwenden oder die Einwilligung manuell handhaben.
  - **Händlerszenario / Beispiel:** Ihr Shop muss DSGVO-konform sein. Durch die Aktivierung dieser Option stellen Sie sicher, dass das Pinterest-Tracking die Datenschutzpräferenzen Ihrer Kunden einhält.

#### Erweiterte Einstellungen & Debugging

- **Debug-Modus aktivieren**

  - **Was diese Einstellung bewirkt:** Aktiviert einen speziellen Modus, der detaillierte Informationen über die gesendeten Pinterest-Ereignisse direkt in der Entwicklerkonsole Ihres Browsers anzeigt. Dies ist nützlich, um zu überprüfen, ob Ihr Tracking korrekt funktioniert.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Entwickler und Webmaster können Echtzeit-Pinterest-Ereignisdaten in der Browserkonsole sehen. Dies sollte **niemals** in einem Live-Produktionsshop für die allgemeine Öffentlichkeit aktiviert werden.
    - *Wenn deaktiviert:* Es werden keine Debug-Informationen angezeigt.
  - **Empfohlener Wert:** **NEIN** für einen Live-Produktionsshop. **JA** nur während der Einrichtung und des Tests.
  - **Händlerszenario / Beispiel:** Sie haben das Modul gerade installiert und möchten bestätigen, dass „In den Warenkorb“-Ereignisse korrekt ausgelöst werden. Sie aktivieren den Debug-Modus, legen ein Produkt in Ihren Warenkorb und überprüfen die Browserkonsole auf die Ereignisdaten.
- **Linker-Domains (für Cross-Domain-Tracking)**

  - **Was diese Einstellung bewirkt:** Wenn Ihr Shop mehrere Subdomains verwendet oder während des Checkout-Prozesses auf eine andere Domain umleitet (z. B. eine separate Zahlungs-Gateway-Domain), können Sie diese Domains hier auflisten. Dies hilft Pinterest, Aktionen über verschiedene Domains hinweg korrekt zuzuordnen.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Wenn Domains aufgeführt sind:* Pinterest kann die Tracking-Kontinuität über diese Domains hinweg aufrechterhalten und Datenverlust verhindern.
    - *Wenn leer:* Das Tracking könnte unterbrochen werden, wenn Kunden während ihrer Reise zwischen verschiedenen Domains navigieren, was zu unvollständigen Daten führt.
  - **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben spezifische Anforderungen an das Cross-Domain-Tracking. Wenn ja, geben Sie jede Domain in einer neuen Zeile ein.
  - **Händlerszenario / Beispiel:** Ihr Hauptshop ist `shop.example.com`, aber Ihr Blog ist `blog.example.com` und Sie möchten Benutzer verfolgen, die beide besuchen. Sie würden hier `blog.example.com` hinzufügen.

#### Datenqualität & Health Score (Informationsbereiche)

Diese Abschnitte bieten Einblicke in Ihre Tracking-Einrichtung und sind keine direkten Konfigurationseinstellungen, sondern vom Modul generierte Berichte.

- **Health Score**: Zeigt eine Gesamtpunktzahl an, die die Qualität und Vollständigkeit Ihrer Pinterest-Tracking-Einrichtung angibt. Eine höhere Punktzahl bedeutet zuverlässigere Daten.
- **Katalog-Doktor**: Hilft bei der Identifizierung potenzieller Probleme mit Ihren Produktkatalogdaten, die die Fähigkeit von Pinterest beeinträchtigen könnten, Produkte für dynamische Anzeigen zuzuordnen.
- **Datenqualitäts-Coach**: Bietet Empfehlungen und Warnungen zu Ihren Ereignisdaten, wie z. B. fehlende Parameter oder falsche Formatierung, um Ihnen bei der Verbesserung der Genauigkeit zu helfen.
- **Live-Statistiken**: Zeigt die neuesten an Pinterest gesendeten Ereignisse an, sodass Sie die Aktivität in Echtzeit überwachen können.
- **Neueste Ereignisse**: Ein Protokoll der neuesten vom Modul verarbeiteten Ereignisse.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### 2.2.1 AdminMypinterestAjaxController (Back Office > Module > Pinterest Tag & Conversions API > Live-Statistiken / Health Score / Datenqualitäts-Coach)

Dieser Controller steuert die dynamischen, interaktiven Abschnitte innerhalb der Hauptkonfigurationsseite des Moduls, insbesondere für Funktionen wie Live-Statistiken, Health Score und Datenqualitäts-Coach.

- **Bildschirmname & Menüposition:** Dies sind keine eigenständigen Menüpunkte, sondern interaktive Panels innerhalb der Hauptkonfigurationsseite des Moduls (Back Office > Module > Modul-Manager > „Pinterest Tag & Conversions API“ konfigurieren).
- **Verfügbare Aktionen & Einstellungen:** Dieser Controller verarbeitet AJAX-Anfragen, um Echtzeitdaten und Berichte abzurufen und anzuzeigen.
  - **Live-Statistiken**: Zeigt einen Echtzeit-Feed von Ereignissen (z. B. PageView, AddToCart, Purchase) an, während sie an Pinterest gesendet werden, einschließlich der Information, ob sie über Tag, CAPI oder beides gesendet wurden. Dies ermöglicht Ihnen eine schnelle Überprüfung, ob Ereignisse ausgelöst werden.
  - **Health Score**: Zeigt eine Zusammenfassung des Zustands Ihrer Tracking-Einrichtung an und hebt Bereiche hervor, die verbessert werden müssen (z. B. fehlendes CAPI-Token, geringe Ereignis-Match-Qualität).
  - **Datenqualitäts-Coach**: Bietet spezifische Empfehlungen zur Verbesserung der Qualität der an Pinterest gesendeten Daten, z. B. die Sicherstellung, dass alle erforderlichen Parameter für jeden Ereignistyp enthalten sind.
  - **Katalog-Doktor**: Analysiert Ihren Produktkatalog-Feed (falls Sie einen für Pinterest verwenden) und weist auf potenzielle Probleme hin, die dynamische Produktanzeigen behindern könnten.
- **Auswirkungen von Änderungen:** Die Interaktion mit diesen Panels (z. B. das Aktualisieren der Live-Statistiken) löst AJAX-Aufrufe aus, die die neuesten Daten von Ihrem Server oder der Pinterest-API abrufen und aktuelle Einblicke liefern, ohne die gesamte Seite neu zu laden.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Überprüfen Sie regelmäßig den Health Score und den Datenqualitäts-Coach, um sicherzustellen, dass Ihr Tracking optimal bleibt. Verwenden Sie Live-Statistiken während des Tests oder nach Änderungen, um zu überprüfen, ob Ereignisse korrekt ausgelöst werden.

#### 2.2.2 index.php (mypinterest/controllers/admin/index.php)

Diese Datei ist ein Platzhalter und dient typischerweise als Sicherheitsmaßnahme, um das direkte Auflisten von Verzeichnissen in PrestaShop-Admin-Ordnern zu verhindern. Sie stellt keinen konfigurierbaren Bildschirm oder eine verwaltete Entität selbst dar.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Pinterest Tag ID | Ihre Tag ID | Verknüpft Ihren Shop mit Ihrem Pinterest-Anzeigenkonto für das Tracking. |
| Modulkonfiguration | Tracking-Modus | Beide (Hybrid) | Sendet Daten über Browser (Tag) und Server (CAPI) für maximale Zuverlässigkeit. |
| Modulkonfiguration | Conversions API Access Token | Ihr CAPI Token | Authentifiziert das serverseitige Senden von Daten an Pinterest. |
| Modulkonfiguration | Enhanced Match für CAPI aktivieren | JA | Verbessert die Genauigkeit der Ereigniszuordnung auf Pinterest für besseres Targeting. |
| Modulkonfiguration | Mit Cookie-Einwilligungsmodul integrieren | JA (falls zutreffend) | Stellt sicher, dass das Pinterest-Tracking die Datenschutzentscheidungen des Kunden respektiert. |
| Modulkonfiguration | Debug-Modus aktivieren | NEIN (im Live-Shop) | Zeigt detaillierte Tracking-Informationen in der Browserkonsole zum Testen an. |
| Modulkonfiguration | Linker-Domains | Leer (falls nicht benötigt) | Erhält die Tracking-Kontinuität über mehrere verwandte Domains hinweg. |
| Live-Statistiken Panel | N/A | N/A | Zeigt Echtzeit-Pinterest-Ereignisse zur Überprüfung an. |
| Health Score Panel | N/A | N/A | Bietet eine Gesamtbewertung der Qualität Ihrer Tracking-Einrichtung. |
| Datenqualitäts-Coach Panel | N/A | N/A | Bietet Empfehlungen zur Verbesserung der Ereignisdaten-Genauigkeit. |
| Katalog-Doktor Panel | N/A | N/A | Identifiziert Probleme in Ihrem Produktkatalog für Pinterest-Anzeigen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe das Modul installiert, sehe aber keine Daten in meinem Pinterest Ads Manager. Was soll ich tun?**
A1: Überprüfen Sie zunächst, ob Ihre **Pinterest Tag ID** und Ihr **Conversions API Access Token** (falls Sie CAPI verwenden) in der Modulkonfiguration korrekt eingegeben wurden. Stellen Sie sicher, dass keine Tippfehler vorhanden sind. Leeren Sie anschließend Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Leistung > Cache leeren**). Besuchen Sie dann das Front Office Ihres Shops und führen Sie einige Aktionen aus (ein Produkt ansehen, in den Warenkorb legen, einen Testkauf abschließen). Wenn Sie den „Debug-Modus“ im Modul aktiviert haben, überprüfen Sie die Entwicklerkonsole Ihres Browsers auf Pinterest-Ereignisse. Wenn immer noch keine Daten angezeigt werden, überprüfen Sie Ihre Pinterest Ads Manager-Einrichtung und stellen Sie sicher, dass Ihr Konto aktiv ist.

**F2: Mein Pinterest Tag scheint von Ad-Blockern blockiert zu werden. Wie kann ich sicherstellen, dass meine Daten trotzdem erfasst werden?**
A2: Genau deshalb ist die Conversions API (CAPI) so wichtig! Stellen Sie sicher, dass Ihr „Tracking-Modus“ auf **„Beide (Hybrid mit Deduplizierung)“** eingestellt ist. Auf diese Weise sendet Ihr PrestaShop-Server die Ereignisdaten direkt an Pinterest über die Conversions API, selbst wenn der browserseitige Pinterest Tag blockiert ist, wodurch Ihr Tracking robust bleibt.

**F3: Wie geht dieses Modul mit dem Datenschutz und der DSGVO/CCPA um?**
A3: Das Modul enthält eine Option zur **„Integration mit Cookie-Einwilligungsmodul“**. Wenn Sie ein separates Cookie-Einwilligungsmodul installiert haben (was für die Einhaltung des Datenschutzes dringend empfohlen wird), aktivieren Sie diese Einstellung. Das Pinterest-Tracking wird dann erst aktiviert, wenn der Kunde seine Einwilligung über Ihre bestehende Einwilligungslösung erteilt hat. Das Modul hasht auch sensible Kundendaten, bevor sie über Enhanced Match für CAPI gesendet werden, was eine zusätzliche Datenschutzebene hinzufügt.

**F4: Ich sehe einen niedrigen „Health Score“ oder Warnungen im „Datenqualitäts-Coach“. Was bedeuten diese?**
A4: Diese Abschnitte sollen Ihnen helfen, Ihr Tracking zu optimieren. Ein niedriger Health Score oder Warnungen weisen normalerweise darauf hin, dass einige Datenparameter fehlen oder falsch formatiert sind oder dass Ihre Einrichtung nicht vollständig optimiert ist (z. B. CAPI nicht aktiviert). Überprüfen Sie die spezifischen Empfehlungen in den Panels „Datenqualitäts-Coach“ und „Katalog-Doktor“. Sie werden Sie anleiten, wie Sie Ihre Datenqualität verbessern können, was sich direkt auf die Effektivität Ihrer Pinterest-Anzeigen auswirkt.

**F5: Wird dieses Modul meine Website verlangsamen?**
A5: Das Modul ist hochoptimiert. Der browserseitige Pinterest Tag wird asynchron geladen, was bedeutet, dass er das Laden Ihrer Seite nicht blockiert. Die serverseitigen Conversions API-Aufrufe erfolgen im Hintergrund und wirken sich nicht auf die Ladezeiten der Front-Office-Seite aus. Sie sollten keine spürbaren Verlangsamungen aufgrund dieses Moduls feststellen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul `Pinterest Tag & Conversions API` (`mypinterest`) implementiert eine hybride Tracking-Strategie für Pinterest, die den traditionellen browserseitigen Pinterest Tag mit der serverseitigen Conversions API (CAPI) kombiniert. Es folgt dem MVC-Muster von PrestaShop, wo anwendbar, und nutzt Hooks für die Ereignisinjektion im Front Office und dedizierte Admin-Controller für Konfiguration und Datenberichterstattung. Zu den wichtigsten Architekturkomponenten gehören:

- **Tracker Factory**: Instanziiert dynamisch den geeigneten Tracking-Mechanismus (Tag, CAPI oder Hybrid) basierend auf der Modulkonfiguration.
- **Ereigniszuordnung**: Übersetzt die internen Ereignisse von PrestaShop (z. B. `actionCartSave`, `actionValidateOrder`) in die Standard-Ereignisnamen und -parameter von Pinterest.
- **Datenqualitätstools**: Dedizierte Klassen für Health Scoring, Katalogdiagnose und Datenqualitäts-Coaching, die umsetzbare Erkenntnisse im Back Office liefern.
- **Einwilligungsmanagement**: Integration mit Drittanbieter-Cookie-Einwilligungsmodulen zur Sicherstellung der DSGVO/CCPA-Konformität.
- **Live-Statistiken**: Echtzeit-Ereignisüberwachung über AJAX zur Fehlerbehebung und Verifizierung.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `controllers/front/ajax.php`
  - **Klassenname & Elternklasse**: `MypinterestAjaxModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit**: Verarbeitet AJAX-Anfragen vom Front Office, hauptsächlich zum Senden serverseitiger Ereignisse (CAPI), die durch clientseitige Aktionen ausgelöst werden, aber sicher auf dem Server verarbeitet werden müssen. Dies kann Ereignisse umfassen, die rein clientseitig schwer zu verfolgen sind, oder für Deduplizierungszwecke. Es empfängt wahrscheinlich Ereignisdaten von `mypinterest.js` und leitet sie an den CAPI-Client weiter.
- `controllers/front/cron.php`
  - **Klassenname & Elternklasse**: `MypinterestCronModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit**: Bietet einen Endpunkt für einen Cron-Job. Dies könnte für Aufgaben wie das Senden verzögerter CAPI-Ereignisse, das Synchronisieren von Produktkatalogen oder das Durchführen regelmäßiger Datenqualitätsprüfungen ohne direkte Benutzerinteraktion verwendet werden.
- `controllers/front/index.php`
  - **Klassenname & Elternklasse**: `MypinterestIndexModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit**: Ein Platzhalter-Front-Controller, der typischerweise verwendet wird, um das direkte Auflisten von Verzeichnissen zu verhindern oder als Fallback für modulspezifische Routen, die nicht zu anderen Controllern passen. In diesem Modul dient er wahrscheinlich einem minimalen Zweck oder leitet um.

#### Back-Office-Admin-Controller

- `controllers/admin/AdminMypinterestAjaxController.php`
  - **Klassenname & Elternklasse**: `AdminMypinterestAjaxController` erweitert `ModuleAdminController`.
  - **Tab-Name und verwaltete Entität**: Dieser Controller wird nicht direkt als Menü-Tab angezeigt, sondern dient als AJAX-Endpunkt für die Konfigurationsseite des Moduls. Er verarbeitet Anfragen für dynamische Daten, die in den Panels „Live-Statistiken“, „Health Score“, „Datenqualitäts-Coach“ und „Katalog-Doktor“ innerhalb der Hauptkonfiguration des Moduls angezeigt werden. Er ruft Echtzeit-Ereignisprotokolle, Gesundheitsmetriken und Diagnoseberichte ab.
- `controllers/admin/index.php`
  - **Klassenname & Elternklasse**: Kein funktionaler Controller.
  - **Tab-Name und verwaltete Entität**: Dies ist ein Sicherheitsplatzhalter, der das Auflisten von Verzeichnissen verhindert.

### 4.3 Kernklassen & Modelle (`classes/`)

- `classes/autoload.php`: Standard-PrestaShop-Autoload-Datei, die sicherstellt, dass Modulklassen korrekt geladen werden.
- `classes/MypinterestCapiClient.php`:
  - **Datenbanktabelle**: Keine direkt.
  - **Erweitert**: Kein `ObjectModel`.
  - **Wichtige öffentliche Methoden**: Verarbeitet die eigentlichen HTTP-Anfragen an den Conversions API-Endpunkt von Pinterest. Kapselt die Logik zum Erstellen von CAPI-Payloads, einschließlich Ereignisdaten, Benutzerdaten und Zugriffstoken.
- `classes/MypinterestCapiTracker.php`:
  - **Datenbanktabelle**: Keine.
  - **Erweitert**: Implementiert `MypinterestTrackerInterface`.
  - **Wichtige öffentliche Methoden**: Verwaltet die Logik zum Verfolgen von Ereignissen speziell über die Conversions API. Formatiert Daten für CAPI, behandelt die Ereignis-Deduplizierung (`event_id`) und delegiert das Senden an `MypinterestCapiClient`.
- `classes/MypinterestCatalogDoctor.php`:
  - **Datenbanktabelle**: Keine.
  - **Erweitert**: Kein `ObjectModel`.
  - **Wichtige öffentliche Methoden**: Enthält Logik zur Analyse von Produktdaten (z. B. aus Produkt-Feeds oder `Product`-Objekten) und zur Identifizierung potenzieller Probleme, die die Fähigkeit von Pinterest beeinträchtigen könnten, Produkte für dynamische Anzeigen zuzuordnen. Bietet Diagnoseberichte.
- `classes/MypinterestConsent.php`:
  - **Datenbanktabelle**: Keine.
  - **Erweitert**: Kein `ObjectModel`.
  - **Wichtige öffentliche Methoden**: Verwaltet die Integration mit Drittanbieter-Cookie-Einwilligungsmodulen. Überprüft den Benutzer-Einwilligungsstatus und bestimmt, ob das Pinterest-Tracking basierend auf der Einwilligung aktiviert oder deaktiviert werden soll.
- `classes/MypinterestCurrencyHelper.php`:
  - **Datenbanktabelle**: Keine.
  - **Erweitert**: Kein `ObjectModel`.
  - **Wichtige öffentliche Methoden**: Dienstprogrammklasse zur Handhabung der Währungsformatierung und -umrechnung, um sicherzustellen, dass Pinterest-Ereignisse Währungswerte im richtigen Format senden.
- `classes/MypinterestDataQualityCoach.php`:
  - **Datenbanktabelle**: Keine.
  - **Erweitert**: Kein `ObjectModel`.
  - **Wichtige öffentliche Methoden**: Analysiert die Qualität der gesendeten Ereignisdaten (z. B. Vorhandensein erforderlicher Parameter, korrekte Datentypen) und gibt Empfehlungen zur Verbesserung.
- `classes/MypinterestEventId.php`:
  - **Datenbanktabelle**: Keine.
  - **Erweitert**: Kein `ObjectModel`.
  - **Wichtige öffentliche Methoden**: Generiert und verwaltet eindeutige `event_id`-Werte für die Ereignis-Deduplizierung, entscheidend für das Hybrid-Tracking.
- `classes/MypinterestEventMap.php`:
  - **Datenbanktabelle**: Keine.
  - **Erweitert**: Kein `ObjectModel`.
  - **Wichtige öffentliche Methoden**: Definiert die Zuordnung zwischen PrestaShop-Aktionen/Daten und den Standard-Ereignisnamen von Pinterest sowie deren erforderlichen/empfohlenen Parametern.
- `classes/MypinterestEvents.php`:
  - **Datenbanktabelle**: Keine.
  - **Erweitert**: Kein `ObjectModel`.
  - **Wichtige öffentliche Methoden**: Zentralisiert die Logik zum Auslösen und Verwalten verschiedener Pinterest-Ereignisse (PageView, AddToCart, Purchase usw.) im gesamten Modul.
- `classes/MypinterestHealthScore.php`:
  - **Datenbanktabelle**: Keine.
  - **Erweitert**: Kein `ObjectModel`.
  - **Wichtige öffentliche Methoden**: Berechnet einen Gesamt-„Health Score“ für die Pinterest-Tracking-Einrichtung basierend auf verschiedenen Faktoren wie dem Vorhandensein des CAPI-Tokens, dem Tracking-Modus und der Datenqualität.
- `classes/MypinterestHybridTracker.php`:
  - **Datenbanktabelle**: Keine.
  - **Erweitert**: Implementiert `MypinterestTrackerInterface`.
  - **Wichtige öffentliche Methoden**: Orchestriert das Tracking, wenn der Modus „Beide“ ausgewählt ist. Ruft sowohl `MypinterestTagTracker` als auch `MypinterestCapiTracker` auf und stellt sicher, dass `event_id` für die Deduplizierung konsistent ist.
- `classes/MypinterestLiveStats.php`:
  - **Datenbanktabelle**: Speichert aktuelle Ereignisprotokolle (z. B. in `ps_configuration` oder einer benutzerdefinierten Tabelle).
  - **Erweitert**: Kein `ObjectModel`.
  - **Wichtige öffentliche Methoden**: Zeichnet aktuelle Pinterest-Ereignisse auf und ruft sie zur Anzeige im Panel „Live-Statistiken“ im Back Office ab.
- `classes/MypinterestProductIdResolver.php`:
  - **Datenbanktabelle**: Keine.
  - **Erweitert**: Kein `ObjectModel`.
  - **Wichtige öffentliche Methoden**: Hilft bei der Auflösung und Formatierung von Produkt-IDs, um den Kataloganforderungen von Pinterest zu entsprechen, wodurch eine genaue Produktzuordnung für dynamische Anzeigen gewährleistet wird.
- `classes/MypinterestPropertyRules.php`:
  - **Datenbanktabelle**: Keine.
  - **Erweitert**: Kein `ObjectModel`.
  - **Wichtige öffentliche Methoden**: Definiert Regeln und Validierungen für Pinterest-Ereigniseigenschaften, um sicherzustellen, dass die an Pinterest gesendeten Daten deren Spezifikationen entsprechen.
- `classes/MypinterestTagTracker.php`:
  - **Datenbanktabelle**: Keine.
  - **Erweitert**: Implementiert `MypinterestTrackerInterface`.
  - **Wichtige öffentliche Methoden**: Verwaltet die Logik zum Einfügen des browserseitigen Pinterest Tag-Skripts und zum Auslösen von Ereignissen über `pintrk()`-Aufrufe.
- `classes/MypinterestTrackerFactory.php`:
  - **Datenbanktabelle**: Keine.
  - **Erweitert**: Kein `ObjectModel`.
  - **Wichtige öffentliche Methoden**: Eine Factory-Pattern-Klasse, die für das Erstellen und Zurückgeben der richtigen Tracker-Instanz (`MypinterestTagTracker`, `MypinterestCapiTracker` oder `MypinterestHybridTracker`) basierend auf der Modulkonfiguration verantwortlich ist.
- `classes/MypinterestTrackerInterface.php`:
  - **Datenbanktabelle**: Keine.
  - **Erweitert**: Kein `ObjectModel`.
  - **Wichtige öffentliche Methoden**: Definiert die gemeinsame Schnittstelle für alle Pinterest-Tracker, um die Konsistenz bei der Behandlung von Ereignissen unabhängig von der zugrunde liegenden Tracking-Methode zu gewährleisten.
- `classes/MypinterestUserData.php`:
  - **Datenbanktabelle**: Keine.
  - **Erweitert**: Kein `ObjectModel`.
  - **Wichtige öffentliche Methoden**: Sammelt und formatiert Kundendaten (E-Mail, Telefon, Adresse usw.) für „Enhanced Match“, um sicherzustellen, dass sie gehasht und mit den Anforderungen von Pinterest konform sind.

### 4.4 JavaScript-Assets (`views/js/`)

- `mypinterest/views/js/mypinterest-admin.js`:
  - **Geltungsbereich**: Back Office.
  - **Beschreibung**: Enthält JavaScript für die Verwaltungsoberfläche des Moduls. Verarbeitet AJAX-Aufrufe an `AdminMypinterestAjaxController` zum Abrufen von Live-Statistiken, Health Scores und anderen dynamischen Inhalten. Verwaltet UI-Interaktionen auf der Konfigurationsseite.
- `mypinterest/views/js/mypinterest-debug.js`:
  - **Geltungsbereich**: Front Office.
  - **Beschreibung**: Wird geladen, wenn der „Debug-Modus“ aktiviert ist. Bietet Konsolenprotokollierung und visuelle Overlays, um Pinterest-Ereignisdaten beim Senden anzuzeigen, was bei der Fehlerbehebung und Verifizierung hilft.
- `mypinterest/views/js/mypinterest-ghost.js`:
  - **Geltungsbereich**: Front Office.
  - **Beschreibung**: Potenziell im Zusammenhang mit „Ghost“- oder verzögertem Tracking oder einem Fallback-Mechanismus für Ereignisse, die möglicherweise nicht sofort ausgelöst werden. Könnte für bestimmte Ereignistypen oder zustimmungsbezogene Verzögerungen verwendet werden.
- `mypinterest/views/js/mypinterest-live.js`:
  - **Geltungsbereich**: Back Office.
  - **Beschreibung**: Speziell für das Panel „Live-Statistiken“. Verwaltet die Echtzeitaktualisierung von Ereignisprotokollen, indem der Server über AJAX abgefragt wird, um aktuelle Pinterest-Ereignisse anzuzeigen.
- `mypinterest/views/js/mypinterest-tcf.js`:
  - **Geltungsbereich**: Front Office.
  - **Beschreibung**: Verwaltet die Integration mit TCF (Transparency and Consent Framework)-kompatiblen Cookie-Einwilligungsmodulen. Lauscht auf Einwilligungsereignisse und aktiviert/deaktiviert das Pinterest-Tracking entsprechend.
- `mypinterest/views/js/mypinterest-wizard.js`:
  - **Geltungsbereich**: Back Office.
  - **Beschreibung**: Steuert die Einrichtungsassistentenfunktion innerhalb der Modulkonfiguration. Führt den Händler durch die ersten Einrichtungsschritte, validiert Eingaben und gibt Feedback.
- `mypinterest/views/js/mypinterest.js`:
  - **Geltungsbereich**: Front Office.
  - **Beschreibung**: Das Haupt-Front-Office-JavaScript für den Pinterest Tag. Fügt die `pintrk()`-Bibliothek ein, initialisiert den Pinterest Tag und löst Standardereignisse (PageView, AddToCart, Checkout, Purchase) basierend auf DOM-Ereignissen oder PrestaShop-JavaScript-Hooks aus. Auch verantwortlich für die Generierung der `event_id` zur Deduplizierung und möglicherweise für das Senden von AJAX-Aufrufen an `controllers/front/ajax.php` für CAPI-Ereignisse.

### 4.5 CSS-Stylesheets (`views/css/`)

- `mypinterest/views/css/mypinterest-admin.css`:
  - **Geltungsbereich**: Back-Office-Admin-Formular-Styling.
  - **Beschreibung**: Stile für die Konfigurationsseite des Moduls, einschließlich Layout von Tabs, Eingabefeldern, Schaltflächen und den dynamischen Panels für Live-Statistiken, Health Score usw.
  - **Wichtige CSS-Klassenselektoren**: `.mypinterest-config`, `.mypinterest-tab-content`, `.mypinterest-health-score`, `.mypinterest-live-stats`.
- `mypinterest/views/css/mypinterest-debug.css`:
  - **Geltungsbereich**: Front-Office-Kunden-Styling (nur wenn der Debug-Modus aktiv ist).
  - **Beschreibung**: Bietet Styling für das Debug-Overlay oder die Konsolenausgabe, wodurch Debug-Informationen für Entwickler besser lesbar werden.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

- `mypinterest/views/templates/hook/capi-pageview.tpl`:
  - **Hook**: Wahrscheinlich `displayHeader` oder `displayFooter`.
  - **Ausgabe**: Rendert ein verstecktes Element oder ein kleines Skript, um ein serverseitiges PageView-Ereignis über CAPI auszulösen, oft für die anfängliche Seitenladeverfolgung oder als Fallback verwendet.
- `mypinterest/views/templates/hook/debug.tpl`:
  - **Hook**: `displayHeader` oder `displayFooter` (bedingt gerendert).
  - **Ausgabe**: Fügt das Skript `mypinterest-debug.js` und möglicherweise eine HTML-Struktur für ein Debug-Overlay ein, wenn der Debug-Modus aktiv ist.
- `mypinterest/views/templates/hook/displayOrderConfirmation.tpl`:
  - **Hook**: `displayOrderConfirmation`.
  - **Ausgabe**: Rendert das Pinterest-„Kauf“-Ereignisskript, einschließlich Bestelldetails (Wert, Währung, Bestell-ID, Produkte) sowohl für den Pinterest Tag als auch für CAPI (über AJAX-Aufruf).
- `mypinterest/views/templates/hook/ghost.tpl`:
  - **Hook**: `displayHeader` oder `displayFooter`.
  - **Ausgabe**: Potenziell im Zusammenhang mit dem Skript `mypinterest-ghost.js`, das für spezifische, möglicherweise verzögerte oder Hintergrund-Tracking-Mechanismen verwendet wird.
- `mypinterest/views/templates/hook/header.tpl`:
  - **Hook**: `displayHeader`.
  - **Ausgabe**: Fügt den Haupt-Pinterest Tag-Basiscodes (`pintrk()`) und das Skript `mypinterest.js` ein. Initialisiert den Pinterest Tag mit der Tag ID und löst möglicherweise das anfängliche „PageView“-Ereignis aus.
- `mypinterest/views/templates/hook/payment.tpl`:
  - **Hook**: `displayPayment` oder `displayPaymentTop`.
  - **Ausgabe**: Könnte verwendet werden, um den Beginn des Checkout-Prozesses oder die Auswahl einer Zahlungsmethode zu verfolgen, wodurch möglicherweise ein „Checkout“- oder „InitiateCheckout“-Ereignis ausgelöst wird.
- `mypinterest/views/templates/hook/product-details.tpl`:
  - **Hook**: `displayProductButtons` oder `displayFooterProduct`.
  - **Ausgabe**: Rendert JavaScript, um „ViewContent“-Ereignisse zu verfolgen, wenn eine Produktseite geladen wird, einschließlich Produkt-ID, Name, Preis und Kategorie. Enthält wahrscheinlich auch Logik für „In den Warenkorb“-Ereignisse.

#### Admin-Templates (`views/templates/admin/`)

- `mypinterest/views/templates/admin/consent-guide.tpl`: Zeigt Informationen und Anleitungen zur Integration mit Cookie-Einwilligungsmodulen an.
- `mypinterest/views/templates/admin/doctor.tpl`: Rendert das Panel „Katalog-Doktor“, das Diagnosen für Produktdaten anzeigt.
- `mypinterest/views/templates/admin/dq.tpl`: Rendert das Panel „Datenqualitäts-Coach“, das Empfehlungen zur Verbesserung der Ereignisdaten gibt.
- `mypinterest/views/templates/admin/health.tpl`: Rendert das Panel „Health Score“, das den allgemeinen Tracking-Zustand anzeigt.
- `mypinterest/views/templates/admin/linker-domains.tpl`: Template für das Eingabefeld „Linker-Domains“.
- `mypinterest/views/templates/admin/live-maintain.tpl`: Möglicherweise eine Wartungs- oder Statusmeldung für die Live-Statistikfunktion.
- `mypinterest/views/templates/admin/live.tpl`: Rendert das Panel „Live-Statistiken“, das Echtzeit-Ereignisprotokolle anzeigt.
- `mypinterest/views/templates/admin/mode-context.tpl`: Bietet Kontextinformationen zum ausgewählten Tracking-Modus.
- `mypinterest/views/templates/admin/mode-note-both.tpl`: Spezifische Notiz/Erklärung für den Tracking-Modus „Beide (Hybrid)“.
- `mypinterest/views/templates/admin/mode-note-capi.tpl`: Spezifische Notiz/Erklärung für den Tracking-Modus „Conversions API“.
- `mypinterest/views/templates/admin/mode-note-tag.tpl`: Spezifische Notiz/Erklärung für den Tracking-Modus „Pinterest Tag“.
- `mypinterest/views/templates/admin/mode-picker.tpl`: Rendert die Optionsfelder oder das Dropdown zur Auswahl des „Tracking-Modus“.
- `mypinterest/views/templates/admin/properties-list.tpl`: Zeigt eine Liste von Ereigniseigenschaften und deren Status (z. B. erforderlich, empfohlen) an.
- `mypinterest/views/templates/admin/recent-events.tpl`: Rendert eine Tabelle oder Liste der neuesten Ereignisse für das Panel „Live-Statistiken“.
- `mypinterest/views/templates/admin/tabs.tpl`: Rendert die Tab-Navigationsstruktur für die Konfigurationsseite des Moduls.
- `mypinterest/views/templates/admin/tag-chips.tpl`: Wahrscheinlich zur Anzeige von Pinterest Tag IDs in einem visuell ansprechenden „Chip“-Format.
- `mypinterest/views/templates/admin/tag-ids.tpl`: Rendert Eingabefelder für Pinterest Tag ID und CAPI Access Token.
- `mypinterest/views/templates/admin/wizard.tpl`: Rendert die Schritt-für-Schritt-Einrichtungsassistentenoberfläche.

#### Front-Office-Templates (`views/templates/front/`)

- `mypinterest/views/templates/front/index.tpl`: Ein Platzhalter-Template, das wahrscheinlich nicht direkt gerendert wird, sondern als Standard für den `MypinterestIndexModuleFrontController` dient.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul verwendet hauptsächlich `ps_configuration` zum Speichern seiner Einstellungen (z. B. `MYPINTEREST_TAG_ID`, `MYPINTEREST_TRACKING_MODE`, `MYPINTEREST_CAPI_TOKEN`).
  - Es kann auch eine benutzerdefinierte Tabelle (z. B. `ps_mypinterest_events_log`) verwenden, um aktuelle Ereignisdaten für die Funktion „Live-Statistiken“ zu speichern, obwohl dies auch in `ps_configuration` als serialisierte Daten gespeichert werden könnte. (Es wurden keine expliziten SQL-Dateien gefunden, daher wahrscheinlich `ps_configuration` oder dynamische Tabellenerstellung).
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Abschnitt jeder Seite. | Fügt das Basis-Pinterest Tag JavaScript, `mypinterest.js`, und potenziell anfängliche PageView-Ereignisse ein. |
| `displayOrderConfirmation` | Auf der Bestellbestätigungsseite nach einem erfolgreichen Kauf. | Löst das „Kauf“-Ereignis aus und sendet detaillierte Bestell- und Produktdaten an Pinterest. |
| `displayProductButtons` | Auf der Produktseite, in der Nähe der Schaltfläche „In den Warenkorb“. | Fügt JavaScript ein, um „ViewContent“-Ereignisse und „In den Warenkorb“-Ereignisse zu verfolgen. |
| `displayFooter` | Am Ende des `<body>`-Abschnitts jeder Seite. | Kann als alternative oder zusätzliche Position zum Einfügen von Skripten verwendet werden, insbesondere für Ereignisse, die das Seitenrendering nicht blockieren müssen. |
| `actionCartSave` | Wenn ein Warenkorb aktualisiert wird (z. B. Produkt hinzugefügt/entfernt). | Löst „AddToCart“- oder „RemoveFromCart“-Ereignisse aus, die oft serverseitig über CAPI oder clientseitig über AJAX verarbeitet werden. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | Löst das serverseitige „Kauf“-Ereignis über CAPI für maximale Zuverlässigkeit aus und ergänzt das clientseitige `displayOrderConfirmation`-Ereignis. |
| `actionFrontControllerSetMedia` | Wenn ein Front-Controller seine Medien (JS/CSS) einstellt. | Ermöglicht dem Modul, seine Front-Office-JavaScript- und CSS-Dateien zu registrieren. |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller seine Medien (JS/CSS) einstellt. | Ermöglicht dem Modul, seine Back-Office-JavaScript- und CSS-Dateien zu registrieren. |
| `actionObjectProductUpdateAfter` / `actionObjectProductAddAfter` | Nach der Aktualisierung oder Hinzufügung eines Produkts. | Potenziell zur Aktualisierung von Produktkatalogdaten oder zur Auslösung von Katalogdiagnosen verwendet. |
| `actionObjectProductDeleteAfter` | Nach dem Löschen eines Produkts. | Potenziell zur Aktualisierung von Produktkatalogdaten verwendet. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul Pinterest Tag & Conversions API besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei technischen Problemen oder Fragen zur Funktionalität des Moduls gerne zur Verfügung.
