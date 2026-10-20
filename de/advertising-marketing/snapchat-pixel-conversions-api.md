---
title: "Snapchat Pixel & Conversions API - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Snapchat Pixel & Conversions API von MyPresta.eu."
sidebar:
  label: "Snapchat Pixel & Conversions API - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Snapchat Pixel & Conversions API auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/snapchat-pixel-conversions-api.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/snapchat-pixel-conversions-api/)
>
> ---


# Snapchat Pixel & Conversions API

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind erforderlich. Diese sind in den meisten modernen Hosting-Umgebungen standardmäßig aktiviert.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie Ihr Snapchat Pixel und die Conversions API einrichten. Das Modul bietet eine benutzerfreundliche Oberfläche mit verschiedenen Abschnitten, die Sie durch die Einrichtung führen.

#### **1. Allgemeine Einstellungen & Tracking-Modus**

-   **Tracking-Modus:**
    *   **Was diese Einstellung bewirkt:** Legt fest, wie Ihr Shop Daten an Snapchat sendet. Sie können zwischen clientseitigem (Pixel), serverseitigem (Conversions API) oder einem Hybridansatz wählen.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Nur Pixel:* Nur das Snap Pixel (JavaScript-Code im Browser) verfolgt Ereignisse. Dies ist einfacher, aber anfälliger für Ad-Blocker und Browserbeschränkungen.
        *   *Nur Conversions API:* Es wird nur serverseitiges Tracking verwendet. Dies ist zuverlässiger für Datenschutz und Genauigkeit, erfordert aber eine robuste Server-Einrichtung.
        *   *Hybrid (Empfohlen):* Sowohl Pixel als auch CAPI verfolgen Ereignisse. Das Modul dedupliziert Ereignisse automatisch mithilfe einer gemeinsamen `event_id`, um eine genaue Berichterstattung zu gewährleisten und gleichzeitig die Datenerfassung zu maximieren. Dies ist im Allgemeinen die robusteste und empfohlene Option.
    *   **Empfohlener Wert:** `Hybrid`
    *   **Händlerszenario / Beispiel:** Wenn Sie gerade erst anfangen, ist „Nur Pixel“ schnell. Für ernsthafte Werbung bietet „Hybrid“ das Beste aus beiden Welten und stellt sicher, dass Sie so viele genaue Daten wie möglich für die Kampagnenoptimierung erfassen.
-   **Snap Pixel ID:**
    *   **Was diese Einstellung bewirkt:** Dies ist Ihre eindeutige Kennung für Ihr Snapchat Pixel. Sie teilt Snapchat mit, welchem Werbekonto die verfolgten Ereignisse zugeordnet werden sollen.
    *   **Auswirkung einer Änderung dieser Einstellung:** Wenn sie falsch oder leer ist, findet kein clientseitiges Tracking statt, und Ihre Snapchat-Anzeigen können keine Website-Besucher oder Konversionen verfolgen.
    *   **Empfohlener Wert:** Ihre Snap Pixel ID (z. B. `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`). Sie finden diese in Ihrem Snapchat Ads Manager.
    *   **Händlerszenario / Beispiel:** Sie haben ein Werbekonto auf Snapchat erstellt und müssen Ihren Shop damit verknüpfen. Geben Sie hier die von Snapchat bereitgestellte Pixel-ID ein.
-   **Conversions API Token:**
    *   **Was diese Einstellung bewirkt:** Dies ist ein sicherer Token, der es Ihrem Server ermöglicht, Daten direkt an die Conversions API von Snapchat zu senden. Er authentifiziert Ihre serverseitigen Anfragen.
    *   **Auswirkung einer Änderung dieser Einstellung:** Wenn sie falsch oder leer ist, findet kein serverseitiges Tracking statt. Das bedeutet, Sie verlieren die Vorteile der erhöhten Zuverlässigkeit und des Datenschutzes von CAPI.
    *   **Empfohlener Wert:** Ihr Conversions API Token. Sie generieren diesen in Ihrem Snapchat Ads Manager.
    *   **Händlerszenario / Beispiel:** Um sicherzustellen, dass Ihre Kaufdaten zuverlässig an Snapchat gesendet werden, auch wenn ein Kunde einen Ad-Blocker verwendet, müssen Sie Ihren CAPI-Token hier einrichten und eingeben.

#### **2. Ereignis-Tracking & Datenqualität**

-   **Erweitertes Matching aktivieren:**
    *   **Was diese Einstellung bewirkt:** Ermöglicht dem Modul, zusätzliche Kundendaten (wie E-Mail, Telefonnummer, Name) sicher gehasht an Snapchat zu senden, um das Ereignis-Matching und die Zielgruppenbildung zu verbessern.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Aktiviert:* Snapchat kann Website-Besucher genauer ihren Snapchat-Profilen zuordnen, was die Zielgruppenansprache und Anzeigenattribution verbessert.
        *   *Deaktiviert:* Es werden weniger Daten gesendet, was die Genauigkeit des Zielgruppen-Matchings und der Kampagnenoptimierung potenziell verringert.
    *   **Empfohlener Wert:** `JA` (es sei denn, Sie haben strenge Datenschutzbedenken, die die Vorteile überwiegen).
    *   **Händlerszenario / Beispiel:** Sie möchten, dass Snapchat so effektiv wie möglich Kunden findet, die Ihren bestehenden ähneln. Das Aktivieren dieser Option hilft Snapchat, Benutzer präziser zu identifizieren.
-   **Einwilligungsverwaltung-Integration:**
    *   **Was diese Einstellung bewirkt:** Integriert sich mit gängigen Cookie-Einwilligungsmodulen (z. B. DSGVO-Modulen), um sicherzustellen, dass das Snapchat-Tracking nur erfolgt, nachdem ein Kunde seine ausdrückliche Zustimmung gegeben hat.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Aktiviert:* Das Modul wartet auf die Zustimmung, bevor es das Snap Pixel initialisiert oder CAPI-Ereignisse sendet, die Benutzerdaten erfordern.
        *   *Deaktiviert:* Das Tracking erfolgt unabhängig von der Benutzerzustimmung, was in einigen Regionen zu Problemen mit der Einhaltung des Datenschutzes führen kann.
    *   **Empfohlener Wert:** `JA` (dringend empfohlen für DSGVO, CCPA und andere Datenschutzbestimmungen).
    *   **Händlerszenario / Beispiel:** Ihr Shop ist in der EU tätig und muss die DSGVO einhalten. Das Aktivieren dieser Option stellt sicher, dass Sie nur Benutzer verfolgen, die Ihrer Cookie-Richtlinie zugestimmt haben.
-   **Produkttyp-ID für Katalog-Matching:**
    *   **Was diese Einstellung bewirkt:** Gibt an, welche Produktkennung (z. B. Produkt-ID, Produktreferenz, EAN/UPC) das Modul an Snapchat senden soll, um den Produktkatalog abzugleichen. Dies ist entscheidend für dynamische Produktanzeigen.
    *   **Auswirkung einer Änderung dieser Einstellung:** Wenn der vom Modul gesendete ID-Typ nicht mit den IDs in Ihrem Snapchat-Produktkatalog übereinstimmt, werden Ihre dynamischen Anzeigen nicht die richtigen Produkte anzeigen.
    *   **Empfohlener Wert:** Wählen Sie den ID-Typ, den Sie konsistent in Ihrem Snapchat-Produktkatalog verwenden. Oft sind `Produkt-ID` oder `Produktreferenz` gute Optionen.
    *   **Händlerszenario / Beispiel:** Sie schalten dynamische Retargeting-Anzeigen auf Snapchat. Wenn Ihr Produktkatalog die „Produktreferenz“ als eindeutige Kennung verwendet, müssen Sie hier „Produktreferenz“ auswählen, damit die Anzeigen den Kunden die richtigen Produkte zeigen.
-   **Debug-Modus aktivieren:**
    *   **Was diese Einstellung bewirkt:** Aktiviert einen speziellen Modus, der detaillierte Informationen über die an Snapchat gesendeten Ereignisse direkt in der Entwicklerkonsole Ihres Browsers anzeigt.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Aktiviert:* Sie sehen Echtzeit-Feedback darüber, welche Daten gesendet werden, was Ihnen bei der Fehlerbehebung und Überprüfung Ihrer Einrichtung hilft. Dies ist nur für Sie (oder jeden, der Entwicklertools geöffnet hat) sichtbar.
        *   *Deaktiviert:* Es werden keine Debug-Informationen angezeigt.
    *   **Empfohlener Wert:** `NEIN` für Live-Shops. `JA` während der Ersteinrichtung und Fehlerbehebung.
    *   **Händlerszenario / Beispiel:** Nach der Installation des Moduls möchten Sie bestätigen, dass „In den Warenkorb legen“-Ereignisse korrekt ausgelöst werden. Sie aktivieren den Debug-Modus, legen ein Produkt in Ihren Warenkorb und überprüfen die Konsole auf die Ereignisdetails.

#### **3. Erweiterte Funktionen**

-   **Ghost Collector (ScCid Matching):**
    *   **Was diese Einstellung bewirkt:** Verbessert die Genauigkeit der Zuordnung von Benutzern über verschiedene Sitzungen und Geräte hinweg, indem eine eindeutige, anonyme Kennung (ScCid) erstellt und in einem Erstanbieter-Cookie gespeichert wird.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Aktiviert:* Bessere Attribution und Zielgruppenbildung, insbesondere in Szenarien, in denen Drittanbieter-Cookies eingeschränkt sind.
        *   *Deaktiviert:* Die Fähigkeit von Snapchat, Benutzer über Sitzungen hinweg zu verfolgen, könnte weniger genau sein.
    *   **Empfohlener Wert:** `JA`
    *   **Händlerszenario / Beispiel:** Ein Kunde besucht Ihren Shop, verlässt ihn und kehrt später von einem anderen Gerät zurück. Ghost Collector hilft Snapchat, ihn als denselben Benutzer zu erkennen, was Ihre Retargeting-Bemühungen verbessert.
-   **Linker-Domains (Cross-Domain Tracking):**
    *   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, zusätzliche Domains (z. B. einen separaten Blog, eine Subdomain für bestimmte Produkte) anzugeben, auf denen Sie ebenfalls Snapchat-Ereignisse verfolgen und Benutzersitzungen verknüpfen möchten.
    *   **Auswirkung einer Änderung dieser Einstellung:**
        *   *Konfiguriert:* Snapchat kann die Reise eines Benutzers nahtlos über Ihren Hauptshop und die angegebenen verknüpften Domains verfolgen.
        *   *Leer:* Das Tracking ist auf Ihre Hauptshop-Domain beschränkt.
    *   **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben mehrere Domains/Subdomains, die ein Cross-Tracking erfordern.
    *   **Händlerszenario / Beispiel:** Sie haben Ihren Hauptshop unter `mystore.com` und einen separaten Blog unter `blog.mystore.com`. Sie möchten Benutzer verfolgen, die beide besuchen. Sie würden `blog.mystore.com` zu dieser Einstellung hinzufügen.
-   **Cron Job URL für CAPI Sync:**
    *   **Was diese Einstellung bewirkt:** Bietet eine eindeutige URL, die Sie als Cron-Job auf Ihrem Server einrichten können. Dieser Cron-Job sendet periodisch alle in der Warteschlange befindlichen serverseitigen Ereignisse an Snapchat, um sicherzustellen, dass Daten auch bei vorübergehenden Netzwerkproblemen geliefert werden.
    *   **Auswirkung einer Änderung dieser Einstellung:** Dies ist ein schreibgeschütztes Feld. Das Einrichten des Cron-Jobs gewährleistet eine zuverlässige, asynchrone Zustellung von CAPI-Ereignissen. Wenn nicht eingerichtet, werden CAPI-Ereignisse möglicherweise nur in Echtzeit oder bei bestimmten Benutzeraktionen gesendet, wodurch möglicherweise einige Daten verloren gehen, wenn der Echtzeit-Versand fehlschlägt.
    *   **Empfohlener Wert:** Richten Sie einen Cron-Job auf Ihrem Server ein, um diese URL alle 5-15 Minuten auszuführen.
    *   **Händlerszenario / Beispiel:** Um sicherzustellen, dass alle Ihre Kaufdaten an Snapchat gesendet werden, auch wenn ein Kunde seinen Browser sofort nach dem Kauf schließt, richten Sie einen Cron-Job ein, um alle ausstehenden CAPI-Ereignisse regelmäßig zu verarbeiten.

#### **4. Datenqualität & Gesundheitsbewertung**

Dieser Abschnitt bietet in der Regel schreibgeschützte Einblicke und Empfehlungen basierend auf Ihrer aktuellen Konfiguration und den verfolgten Ereignissen.

-   **Gesundheitsbewertung:**
    *   **Was diese Einstellung bewirkt:** Zeigt eine Gesamtbewertung an, die die Qualität und Vollständigkeit Ihrer Snapchat-Tracking-Einrichtung angibt. Eine höhere Bewertung bedeutet bessere Daten.
    *   **Auswirkung einer Änderung dieser Einstellung:** Dies ist ein Diagnosewerkzeug. Die Verbesserung Ihrer Konfiguration (z. B. Aktivierung von CAPI, erweitertes Matching) erhöht diese Bewertung.
    *   **Empfohlener Wert:** Streben Sie die höchstmögliche Punktzahl an.
    *   **Händlerszenario / Beispiel:** Ihre Gesundheitsbewertung beträgt 60 %. Das Modul könnte vorschlagen, das erweiterte Matching zu aktivieren, um es zu verbessern, was auf einen potenziellen Bereich für eine bessere Datenqualität hinweist.
-   **Datenqualitäts-Coach:**
    *   **Was diese Einstellung bewirkt:** Bietet spezifische Empfehlungen und Warnungen zu Ihrer Tracking-Einrichtung, wie z. B. fehlende CAPI-Token, nicht konfigurierte Produkttyp-IDs oder potenzielle Einwilligungsprobleme.
    *   **Auswirkung einer Änderung dieser Einstellung:** Dies ist ein Diagnosewerkzeug. Die Behebung der Empfehlungen verbessert Ihre Tracking-Genauigkeit.
    *   **Empfohlener Wert:** Überprüfen Sie alle Empfehlungen und handeln Sie danach.
    *   **Händlerszenario / Beispiel:** Der Coach teilt Ihnen mit, dass Ihr „Produkttyp-ID“ nicht mit Ihrem Katalog übereinstimmt. Sie gehen dann zurück zu den Einstellungen und passen ihn an.
-   **Katalog-Doktor:**
    *   **Was diese Einstellung bewirkt:** Hilft Ihnen, Probleme im Zusammenhang mit Ihrem Produktkatalog und dessen Abgleich mit Snapchat-Ereignissen zu diagnostizieren. Es überprüft die Konsistenz der Produktkennungen.
    *   **Auswirkung einer Änderung dieser Einstellung:** Dies ist ein Diagnosewerkzeug. Die Behebung von Problemen hier stellt sicher, dass Ihre dynamischen Produktanzeigen korrekt funktionieren.
    *   **Empfohlener Wert:** Verwenden Sie dieses Tool, wenn Sie Probleme mit dynamischen Produktanzeigen haben, die falsche Artikel anzeigen.
    *   **Händlerszenario / Beispiel:** Ihre dynamischen Anzeigen zeigen generische Produkte anstelle der vom Kunden angesehenen. Der Katalog-Doktor könnte aufdecken, dass Ihre Produkt-IDs inkonsistent sind.

#### **5. Live-Statistiken & Aktuelle Ereignisse**

-   **Live-Statistiken:**
    *   **Was diese Einstellung bewirkt:** Bietet eine Echtzeitübersicht über die an Snapchat gesendeten Ereignisse (z. B. Seitenaufrufe, In den Warenkorb legen, Käufe).
    *   **Auswirkung einer Änderung dieser Einstellung:** Dies ist ein Überwachungstool. Es hilft Ihnen, schnell zu überprüfen, ob Ereignisse wie erwartet ausgelöst werden.
    *   **Empfohlener Wert:** Überprüfen Sie diesen Abschnitt regelmäßig, um sicherzustellen, dass Ihr Tracking aktiv ist.
    *   **Händlerszenario / Beispiel:** Sie bringen ein neues Produkt auf den Markt und möchten sehen, ob „Inhalt anzeigen“-Ereignisse sofort verfolgt werden. Sie überprüfen die Live-Statistiken.
-   **Protokoll der letzten Ereignisse:**
    *   **Was diese Einstellung bewirkt:** Zeigt ein Protokoll der letzten an Snapchat gesendeten Ereignisse an, einschließlich Details wie Ereignistyp, Zeitstempel und ob es über Pixel oder CAPI gesendet wurde.
    *   **Auswirkung einer Änderung dieser Einstellung:** Dies ist ein detailliertes Protokollierungstool zur Überprüfung und Fehlerbehebung.
    *   **Empfohlener Wert:** Verwenden Sie dies, um bestimmte Ereignisse genauer zu untersuchen, wenn Sie ein Problem vermuten.
    *   **Händlerszenario / Beispiel:** Ein Kunde meldet ein Problem mit einem Kauf, und Sie möchten bestätigen, ob das „Kauf“-Ereignis für diese Bestellung erfolgreich an Snapchat gesendet wurde.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### **AdminMysnapapiAjaxController (Back Office > Module > Snapchat Pixel & Conversions API > [Interne AJAX-Aufrufe])**

Dieser Controller ist nicht direkt über ein Menüelement zugänglich, sondern verarbeitet Hintergrund-AJAX-Anfragen von der Konfigurationsseite des Moduls. Er ist verantwortlich für:

-   **Bildschirmname & Menüposition:** Nicht direkt im Menü sichtbar. Er verarbeitet Anfragen, die von der Hauptkonfigurationsseite des Moduls initiiert werden.
-   **Verfügbare Aktionen & Einstellungen:** Er verwaltet das dynamische Laden von Daten für die Abschnitte „Live-Statistiken“, „Aktuelle Ereignisse“, „Gesundheitsbewertung“, „Datenqualitäts-Coach“ und „Katalog-Doktor“. Er behandelt auch das Speichern spezifischer Konfigurationseinstellungen ohne vollständiges Neuladen der Seite.
-   **Auswirkung von Änderungen:** Wenn Sie mit dynamischen Elementen auf der Hauptkonfigurationsseite interagieren (z. B. Aktualisieren von Live-Statistiken, Speichern einer bestimmten Untereinstellung), verarbeitet dieser Controller die Anfrage und aktualisiert die angezeigten Informationen oder speichert die Daten.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Händler interagieren nicht direkt mit diesem Controller. Seine Funktionalität ist in die Hauptkonfigurationsseite des Moduls eingebettet.

#### **index.php (mysnapapi/controllers/admin/index.php)**

Diese Datei ist ein Platzhalter und enthält typischerweise keine direkte Funktionalität oder Benutzeroberfläche. In PrestaShop dienen `index.php`-Dateien in Controller-Verzeichnissen oft dazu, die Verzeichnisauflistung zu verhindern, anstatt spezifische Controller-Logik bereitzustellen.

-   **Bildschirmname & Menüposition:** Kein direkter Bildschirm.
-   **Verfügbare Aktionen & Einstellungen:** Keine.
-   **Auswirkung von Änderungen:** Keine direkte Händlerinteraktion oder Auswirkung.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Keine Interaktion erforderlich.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfigurationsseite** | Tracking-Modus | Hybrid | Definiert, wie Daten gesendet werden (Pixel, CAPI oder beides). Hybrid ist am robustesten. |
| | Snap Pixel ID | Ihre Pixel-ID | Eindeutige ID für clientseitiges Tracking. Wesentlich für Pixel. |
| | Conversions API Token | Ihr CAPI-Token | Sicherer Token für serverseitiges Tracking. Wesentlich für CAPI. |
| | Erweitertes Matching aktivieren | JA | Verbessert das Benutzer-Matching für besseres Anzeigen-Targeting. |
| | Einwilligungsverwaltung-Integration | JA | Gewährleistet die Einhaltung des Datenschutzes durch Respektierung der Benutzerzustimmung. |
| | Produkttyp-ID für Katalog-Matching | Produkt-ID / Referenz | Gleicht Produktkennungen für dynamische Anzeigen ab. |
| | Debug-Modus aktivieren | NEIN (JA für Einrichtung) | Zeigt Tracking-Informationen in der Browserkonsole zur Fehlerbehebung an. |
| | Ghost Collector (ScCid Matching) | JA | Verbessert das Benutzer-Matching über Sitzungen/Geräte hinweg. |
| | Linker-Domains | Leer (oder Ihre Domains) | Ermöglicht Cross-Domain-Tracking für mehrere verwandte Websites. |
| | Cron Job URL für CAPI Sync | (Schreibgeschützt) | URL für serverseitige Ereignisübermittlung, als Cron-Job eingerichtet. |
| | Gesundheitsbewertung | (Diagnose) | Gesamtqualität Ihrer Tracking-Einrichtung. Streben Sie eine hohe Punktzahl an. |
| | Datenqualitäts-Coach | (Diagnose) | Spezifische Empfehlungen zur Verbesserung der Datenqualität. |
| | Katalog-Doktor | (Diagnose) | Diagnostiziert Probleme beim Abgleich des Produktkatalogs. |
| | Live-Statistiken | (Überwachung) | Echtzeitübersicht der verfolgten Ereignisse. |
| | Protokoll der letzten Ereignisse | (Überwachung) | Detailliertes Protokoll der letzten Ereignisse zur Überprüfung. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Snapchat-Anzeigen zeigen keine Konversionen an, aber ich weiß, dass ich Verkäufe erziele. Was ist falsch?**
A1:

-   **Pixel-ID & CAPI-Token überprüfen:** Überprüfen Sie nochmals, ob Ihre Snap Pixel-ID und Ihr Conversions API-Token in der Modulkonfiguration korrekt eingegeben wurden. Schon ein einziger Tippfehler verhindert das Tracking.
-   **Tracking-Modus:** Stellen Sie sicher, dass Sie „Hybrid“ oder zumindest „Nur Pixel“ verwenden, wenn Sie clientseitiges Tracking erwarten.
-   **Debug-Modus:** Aktivieren Sie den „Debug-Modus“ in den Moduleinstellungen und öffnen Sie die Entwicklerkonsole Ihres Browsers (F12). Navigieren Sie in Ihrem Shop und führen Sie Aktionen aus (Produkt ansehen, in den Warenkorb legen, einen Testkauf abschließen). Suchen Sie nach Snapchat-Ereignissen, die in der Konsole protokolliert werden. Wenn Sie keine sehen, liegt ein grundlegendes Einrichtungsproblem vor.
-   **Cache leeren:** Leeren Sie immer Ihren PrestaShop-Cache (Erweiterte Parameter > Leistung), nachdem Sie Änderungen an der Modulkonfiguration vorgenommen haben.
-   **Ad-Blocker:** Testen Sie mit einem Inkognito-/privaten Browserfenster ohne aktivierte Ad-Blocker, da diese das Pixel-Tracking stören können.

**F2: Ich habe das Modul aktiviert, mache mir aber Sorgen um die DSGVO/CCPA-Konformität. Wie hilft dieses Modul dabei?**
A2:

-   Das Modul enthält eine Einstellung **„Einwilligungsverwaltung-Integration“**. Wenn diese aktiviert ist, wird es in Ihre bestehende Cookie-Einwilligungslösung (z. B. ein DSGVO-Modul) integriert. Das bedeutet, dass das Snapchat-Tracking erst *nachdem* ein Benutzer seine ausdrückliche Zustimmung über das Einwilligungsbanner Ihres Shops gegeben hat, aktiviert wird.
-   **Aktion:** Stellen Sie sicher, dass diese Einstellung aktiviert ist und dass Sie ein funktionierendes Cookie-Einwilligungsmodul in Ihrem PrestaShop-Shop haben.

**F3: Meine dynamischen Produktanzeigen auf Snapchat zeigen die falschen Produkte an oder funktionieren überhaupt nicht.**
A3:

-   **Produkttyp-ID:** Gehen Sie zur Modulkonfiguration und überprüfen Sie die Einstellung **„Produkttyp-ID für Katalog-Matching“**. Diese muss exakt mit der eindeutigen Kennung übereinstimmen, die Sie in Ihrem Snapchat-Produktkatalog verwenden (z. B. wenn Ihr Katalog `reference` verwendet, wählen Sie hier `Produktreferenz`).
-   **Katalog-Synchronisierung:** Stellen Sie sicher, dass Ihr Produktkatalog in Ihrem Snapchat Ads Manager korrekt synchronisiert und aktuell ist. Das Modul sendet die richtigen IDs, aber Snapchat muss diese IDs in seinem Katalog haben.
-   **Katalog-Doktor:** Verwenden Sie das Tool „Katalog-Doktor“ innerhalb der Modulkonfiguration, um potenzielle Inkonsistenzen zwischen den Produktdaten Ihres Shops und den Erwartungen von Snapchat zu diagnostizieren.

**F4: Ich sehe doppelte Ereignisse in meinem Snapchat Ads Manager (z. B. zwei „Kauf“-Ereignisse für eine Bestellung).**
A4:

-   Dies geschieht normalerweise, wenn Sie sowohl Pixel als auch CAPI ohne ordnungsgemäße Deduplizierung verwenden.
-   **Aktion:** Stellen Sie sicher, dass Ihr „Tracking-Modus“ auf **„Hybrid“** eingestellt ist. Dieses Modul ist so konzipiert, dass es die Ereignis-Deduplizierung im Hybrid-Modus automatisch handhabt, indem es eine gemeinsame `event_id` für clientseitige und serverseitige Ereignisse generiert. Wenn Sie Duplikate sehen, überprüfen Sie, ob das Modul korrekt für den Hybrid-Modus konfiguriert ist und dass kein anderer Snapchat-Tracking-Code auf Ihrer Website vorhanden ist.

**F5: Die Abschnitte „Live-Statistiken“ oder „Gesundheitsbewertung“ auf der Modulkonfigurationsseite werden nicht aktualisiert oder zeigen keine Daten an.**
A5:

-   **AJAX-Probleme:** Dies deutet normalerweise auf ein Problem mit der Fähigkeit Ihres Servers hin, AJAX-Anfragen zu verarbeiten, oder auf einen JavaScript-Fehler in Ihrem Back Office.
-   **Browserkonsole:** Öffnen Sie die Entwicklerkonsole Ihres Browsers (F12), während Sie sich auf der Modulkonfigurationsseite befinden, und suchen Sie nach roten Fehlermeldungen im Tab „Konsole“.
-   **Server-Logs:** Überprüfen Sie die PHP-Fehlerprotokolle Ihres Servers auf entsprechende Fehler.
-   **PrestaShop-Debug-Modus:** Aktivieren Sie vorübergehend den PrestaShop-Debug-Modus (Erweiterte Parameter > Leistung > Debug-Modus: JA), um zu sehen, ob detailliertere Fehler angezeigt werden.
-   **Support kontaktieren:** Wenn Sie das Problem nicht lösen können, sammeln Sie alle Fehlermeldungen und kontaktieren Sie den MyPresta.eu-Support.

## 4. Entwickler- & Webmaster-Leitfaden (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul `Snapchat Pixel & Conversions API` (`mysnapapi`) implementiert eine robuste Tracking-Lösung, die sowohl clientseitiges (Snap Pixel) als auch serverseitiges (Conversions API - CAPI) Ereignis-Tracking nutzt. Es folgt einem modularen, objektorientierten Ansatz, der, wo anwendbar, dem PrestaShop MVC-Muster entspricht.

Wichtige Architekturkomponenten:

-   **Hybrid-Tracking:** Das Modul unterstützt Pixel-only, CAPI-only und einen empfohlenen Hybrid-Modus. Im Hybrid-Modus generiert es eine eindeutige `event_id` für jedes Ereignis, die zwischen den Pixel- und CAPI-Payloads geteilt wird, um die Deduplizierung auf Snapchat-Seite zu gewährleisten.
-   **Ereignis-Mapping:** Eine umfassende Zuordnung von PrestaShop-Aktionen (z. B. `actionCartSave`, `actionValidateOrder`) zu Standard-Snapchat-Ereignissen (`ADD_CART`, `PURCHASE`, `VIEW_CONTENT`, `PAGE_VIEW`).
-   **Einwilligungsverwaltung:** Integrationspunkte für gängige Einwilligungsmodule zur Sicherstellung der DSGVO/CCPA-Konformität.
-   **Datenqualitätstools:** Integrierte Diagnosetools wie Gesundheitsbewertung, Datenqualitäts-Coach und Katalog-Doktor zur Unterstützung bei Einrichtung und Fehlerbehebung.
-   **Asynchrone CAPI:** CAPI-Ereignisse werden oft in eine Warteschlange gestellt und asynchron gesendet, entweder in Echtzeit oder über einen Cron-Job, um Leistung und Zuverlässigkeit zu verbessern.
-   **Erstanbieterdaten:** Verwendet einen „Ghost Collector“, um Erstanbieter-Cookies für das `ScCid`-Matching zu erstellen, was die Benutzeridentifikation in einer datenschutzorientierten Umgebung verbessert.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

-   `mysnapapi/controllers/front/ajax.php`
    *   **Klassenname & Elternklasse:** `MysnapapiAjaxModuleFrontController` erweitert `ModuleFrontController`.
    *   **Verantwortlichkeit:** Verarbeitet verschiedene AJAX-Anfragen vom Front-Office, hauptsächlich für die „Ghost Collector“ (ScCid)-Funktionalität. Es kann anonyme Benutzerdaten sammeln oder Erstanbieter-Cookies ohne vollständiges Neuladen der Seite aktualisieren.
-   `mysnapapi/controllers/front/cron.php`
    *   **Klassenname & Elternklasse:** `MysnapapiCronModuleFrontController` erweitert `ModuleFrontController`.
    *   **Verantwortlichkeit:** Dieser Controller ist so konzipiert, dass er von einem externen Cron-Job aufgerufen wird. Seine Hauptaufgabe ist die Verarbeitung aller in der Warteschlange befindlichen serverseitigen (CAPI) Ereignisse, die nicht in Echtzeit gesendet wurden. Er stellt sicher, dass alle CAPI-Daten schließlich an Snapchat geliefert werden, was die Zuverlässigkeit verbessert.
-   `mysnapapi/controllers/front/index.php`
    *   **Klassenname & Elternklasse:** `MysnapapiIndexModuleFrontController` erweitert `ModuleFrontController`.
    *   **Verantwortlichkeit:** Typischerweise ein Platzhalter oder ein Standard-Einstiegspunkt. Er könnte grundlegende Modulinitialisierungen handhaben oder umleiten, wenn er direkt aufgerufen wird. Oft verhindert `index.php` in einem Controller-Verzeichnis die Verzeichnisauflistung.
-   `mysnapapi/controllers/front/sync.php`
    *   **Klassenname & Elternklasse:** `MysnapapiSyncModuleFrontController` erweitert `ModuleFrontController`.
    *   **Verantwortlichkeit:** Behandelt wahrscheinlich spezifische Datensynchronisierungsaufgaben, möglicherweise im Zusammenhang mit Produktkatalogaktualisierungen oder anderem Datenaustausch mit der Snapchat-API, getrennt vom Haupt-Ereignis-Tracking.

#### Back-Office-Admin-Controller

-   `mysnapapi/controllers/admin/AdminMysnapapiAjaxController.php`
    *   **Klassenname & Elternklasse:** `AdminMysnapapiAjaxController` erweitert `AdminController`.
    *   **Tab-Name und verwaltete Entität:** Kein direkter Menü-Tab. Dieser Controller verarbeitet AJAX-Anfragen, die von der Hauptkonfigurationsseite des Moduls (`getContent()`-Methode von `mysnapapi.php`) stammen. Er ist verantwortlich für das dynamische Laden von Daten für die verschiedenen Diagnosetools (Live-Statistiken, Gesundheitsbewertung usw.) und das Speichern spezifischer Konfigurationseinstellungen ohne vollständiges Neuladen der Seite.
-   `mysnapapi/controllers/admin/index.php`
    *   **Klassenname & Elternklasse:** Kein funktionaler Controller.
    *   **Tab-Name und verwaltete Entität:** Platzhalter. Verhindert die Verzeichnisauflistung.

### 4.3 Kernklassen & Modelle (`classes/`)

-   `mysnapapi/classes/autoload.php`: Standard-PrestaShop-Autoload-Datei.
-   `mysnapapi/classes/index.php`: Platzhalter zur Verhinderung der Verzeichnisauflistung.
-   `mysnapapi/classes/MysnapapiCapiClient.php`:
    *   **Interagiert mit:** Snapchat Conversions API-Endpunkt.
    *   **Erweitert ObjectModel:** Nein.
    *   **Schlüsselmethoden:** Handhabt das Senden serverseitiger Ereignisse an Snapchat. Kapselt die API-Anfragelogik, Authentifizierung (mittels CAPI-Token) und Fehlerbehandlung.
-   `mysnapapi/classes/MysnapapiCapiTracker.php`:
    *   **Interagiert mit:** `ps_configuration` (für CAPI-Token), `MysnapapiCapiClient`.
    *   **Erweitert ObjectModel:** Nein.
    *   **Schlüsselmethoden:** Verantwortlich für die Vorbereitung und das Senden von Ereignisdaten speziell für die Conversions API. Formatiert Ereignis-Payloads gemäß den CAPI-Spezifikationen von Snapchat.
-   `mysnapapi/classes/MysnapapiCatalogDoctor.php`:
    *   **Interagiert mit:** Produktdaten (aus `Product` und `ProductSupplier` ObjectModels).
    *   **Erweitert ObjectModel:** Nein.
    *   **Schlüsselmethoden:** Bietet Diagnose-Logik zur Überprüfung der Konsistenz und Probleme im Zusammenhang mit Produktkennungen, die für das Katalog-Matching verwendet werden (z. B. `id_product`, `reference`, `ean13`).
-   `mysnapapi/classes/MysnapapiConsent.php`:
    *   **Interagiert mit:** `ps_configuration` (für Einwilligungseinstellungen), potenziell andere Einwilligungsmodule.
    *   **Erweitert ObjectModel:** Nein.
    *   **Schlüsselmethoden:** Verwaltet den Einwilligungsstatus. Überprüft, ob die Benutzerzustimmung erforderlich ist und ob sie erteilt wurde, bevor Tracking-Skripte oder CAPI-Ereignisse ausgelöst werden dürfen.
-   `mysnapapi/classes/MysnapapiCurrencyHelper.php`:
    *   **Interagiert mit:** PrestaShops `Currency`-Klasse.
    *   **Erweitert ObjectModel:** Nein.
    *   **Schlüsselmethoden:** Bietet Hilfsfunktionen für die Währungsformatierung und -konvertierung, um sicherzustellen, dass Ereigniswerte im richtigen Format und Währungscode an Snapchat gesendet werden.
-   `mysnapapi/classes/MysnapapiDataQualityCoach.php`:
    *   **Interagiert mit:** Modulkonfigurationseinstellungen.
    *   **Erweitert ObjectModel:** Nein.
    *   **Schlüsselmethoden:** Analysiert die Modulkonfiguration und gibt Empfehlungen oder Warnungen zur Verbesserung der Datenqualität und Tracking-Effektivität.
-   `mysnapapi/classes/MysnapapiEventId.php`:
    *   **Interagiert mit:** Sitzung, Cookies.
    *   **Erweitert ObjectModel:** Nein.
    *   **Schlüsselmethoden:** Generiert und verwaltet eindeutige `event_id`-Werte für jedes verfolgte Ereignis. Entscheidend für die Deduplizierung bei Verwendung des Hybrid-Tracking-Modus.
-   `mysnapapi/classes/MysnapapiEventMap.php`:
    *   **Interagiert mit:** N/A.
    *   **Erweitert ObjectModel:** Nein.
    *   **Schlüsselmethoden:** Definiert die Zuordnung zwischen PrestaShops internen Ereignissen/Daten und Snapchats Standard-Ereignisnamen und -parametern.
-   `mysnapapi/classes/MysnapapiEvents.php`:
    *   **Interagiert mit:** Verschiedene PrestaShop-Kernklassen (z. B. `Cart`, `Product`, `Order`).
    *   **Erweitert ObjectModel:** Nein.
    *   **Schlüsselmethoden:** Zentralisierte Klasse zum Sammeln und Formatieren von Ereignisdaten (z. B. `PageView`, `ViewContent`, `AddToCart`, `Purchase`) aus dem PrestaShop-Kontext in eine Snapchat-kompatible Struktur.
-   `mysnapapi/classes/MysnapapiHealthScore.php`:
    *   **Interagiert mit:** Modulkonfiguration, potenziell Live-Ereignisdaten.
    *   **Erweitert ObjectModel:** Nein.
    *   **Schlüsselmethoden:** Berechnet eine Gesamt-„Gesundheitsbewertung“ für die Tracking-Einrichtung basierend auf konfigurierten Optionen und erkannten Problemen.
-   `mysnapapi/classes/MysnapapiHybridTracker.php`:
    *   **Interagiert mit:** `MysnapapiPixelTracker`, `MysnapapiCapiTracker`, `MysnapapiEventId`.
    *   **Erweitert ObjectModel:** Nein.
    *   **Schlüsselmethoden:** Orchestriert das Tracking im „Hybrid“-Modus und stellt sicher, dass sowohl Pixel- als auch CAPI-Ereignisse mit derselben `event_id` zur Deduplizierung gesendet werden.
-   `mysnapapi/classes/MysnapapiLiveStats.php`:
    *   **Interagiert mit:** Potenziell ein temporäres Protokoll der letzten Ereignisse oder Echtzeitdaten.
    *   **Erweitert ObjectModel:** Nein.
    *   **Schlüsselmethoden:** Sammelt und präsentiert Echtzeitstatistiken zu verfolgten Ereignissen für das Admin-Panel.
-   `mysnapapi/classes/MysnapapiPixelTracker.php`:
    *   **Interagiert mit:** `ps_configuration` (für Pixel-ID).
    *   **Erweitert ObjectModel:** Nein.
    *   **Schlüsselmethoden:** Verantwortlich für die Generierung des JavaScript-Codes für das Snap Pixel und dessen Einbettung in das Front-Office, einschließlich Ereignisdaten.
-   `mysnapapi/classes/MysnapapiProductIdResolver.php`:
    *   **Interagiert mit:** Produktdaten.
    *   **Erweitert ObjectModel:** Nein.
    *   **Schlüsselmethoden:** Bestimmt die korrekte Produktkennung (z. B. `id_product`, `reference`, `ean13`), die basierend auf der Modulkonfiguration für das Katalog-Matching verwendet werden soll.
-   `mysnapapi/classes/MysnapapiPropertyRules.php`:
    *   **Interagiert mit:** N/A.
    *   **Erweitert ObjectModel:** Nein.
    *   **Schlüsselmethoden:** Definiert Regeln und Validierungen für Ereigniseigenschaften, um sicherzustellen, dass die an Snapchat gesendeten Daten deren API-Spezifikationen entsprechen.
-   `mysnapapi/classes/MysnapapiTrackerFactory.php`:
    *   **Interagiert mit:** Modulkonfiguration (Tracking-Modus).
    *   **Erweitert ObjectModel:** Nein.
    *   **Schlüsselmethoden:** Factory-Muster zur Instanziierung der korrekten Tracker-Klasse (`MysnapapiPixelTracker`, `MysnapapiCapiTracker` oder `MysnapapiHybridTracker`) basierend auf dem konfigurierten Tracking-Modus des Moduls.
-   `mysnapapi/classes/MysnapapiTrackerInterface.php`:
    *   **Interagiert mit:** N/A.
    *   **Erweitert ObjectModel:** Nein.
    *   **Schlüsselmethoden:** Definiert eine gemeinsame Schnittstelle für alle Tracker-Klassen, um konsistente Methodensignaturen für das Ereignis-Tracking zu gewährleisten.
-   `mysnapapi/classes/MysnapapiUserData.php`:
    *   **Interagiert mit:** Kundendaten (aus `Customer` ObjectModel), Sitzung, Cookies.
    *   **Erweitert ObjectModel:** Nein.
    *   **Schlüsselmethoden:** Sammelt und formatiert benutzerspezifische Daten (z. B. E-Mail, Telefon, IP-Adresse, User-Agent) für erweitertes Matching, um sicherzustellen, dass die Daten gehasht und konform sind.

### 4.4 JavaScript-Assets (`views/js/`)

-   `mysnapapi/tools/console-simulate-bo-ui.js`:
    *   **Umfang:** Back-Office (Entwicklertool).
    *   **Beschreibung:** Ein Dienstprogramm-Skript, wahrscheinlich für Entwicklung/Debugging, um die Back-Office-Benutzeroberfläche von der Browserkonsole aus zu simulieren oder mit ihr zu interagieren.
-   `mysnapapi/views/js/mp-collect.js`:
    *   **Umfang:** Front-Office.
    *   **Beschreibung:** Kern-Client-seitiges Datenerfassungsskript. Es könnte auf bestimmte DOM-Ereignisse oder Benutzerinteraktionen lauschen, um Snapchat Pixel-Ereignisse auszulösen.
-   `mysnapapi/views/js/mp-consent.js`:
    *   **Umfang:** Front-Office.
    *   **Beschreibung:** Handhabt die Integration mit Cookie-Einwilligungsmechanismen. Es überprüft den Einwilligungsstatus und lädt/initialisiert bedingt das Snapchat Pixel oder verwandtes Tracking. Kann mit `prestashop.on('updateConsent')` interagieren.
-   `mysnapapi/views/js/mp-front.js`:
    *   **Umfang:** Front-Office.
    *   **Beschreibung:** Allgemeines Front-Office-JavaScript für das Modul. Dies enthält wahrscheinlich die Hauptlogik zur Initialisierung des Snap Pixels, zum Pushen von Ereignissen an das `snap`-Objekt und zur Handhabung von Client-seitigen Ereignisauslösern.
-   `mysnapapi/views/js/mp-inspect.js`:
    *   **Umfang:** Front-Office (Debug-Modus).
    *   **Beschreibung:** Wird verwendet, wenn der Debug-Modus aktiviert ist. Es fängt Snapchat-Ereignisse ab und zeigt sie in der Browserkonsole an, was detaillierte Einblicke in die gesendeten Daten bietet.
-   `mysnapapi/views/js/mysnapapi-admin.js`:
    *   **Umfang:** Back-Office.
    *   **Beschreibung:** JavaScript für die Verwaltungsoberfläche des Moduls. Handhabt Formularinteraktionen, AJAX-Aufrufe an `AdminMysnapapiAjaxController`, dynamische Aktualisierungen von Diagnoseabschnitten (Live-Statistiken, Gesundheitsbewertung) und Assistentenschritte.
-   `mysnapapi/views/js/mysnapapi-debug.js`:
    *   **Umfang:** Front-Office (Debug-Modus).
    *   **Beschreibung:** Ähnlich wie `mp-inspect.js`, bietet zusätzliche Debugging-Dienstprogramme oder visuelle Overlays für Entwickler zur Überprüfung des Trackings.
-   `mysnapapi/views/js/mysnapapi-ghost.js`:
    *   **Umfang:** Front-Office.
    *   **Beschreibung:** Implementiert die „Ghost Collector“-Funktionalität. Es verwaltet die Erstellung und das Lesen von Erstanbieter-Cookies für das `ScCid` (Snapchat Click ID)-Matching, was die Benutzeridentifikation verbessert.
-   `mysnapapi/views/js/mysnapapi-live.js`:
    *   **Umfang:** Back-Office.
    *   **Beschreibung:** Treibt den Abschnitt „Live-Statistiken“ im Admin-Panel an, indem AJAX-Aufrufe getätigt werden, um Echtzeit-Ereignisdaten abzurufen und anzuzeigen.
-   `mysnapapi/views/js/mysnapapi-tcf.js`:
    *   **Umfang:** Front-Office.
    *   **Beschreibung:** Speziell für die Integration mit TCF (Transparency and Consent Framework)-konformen Einwilligungslösungen, um sicherzustellen, dass das Snapchat-Tracking den TCF-Signalen entspricht.
-   `mysnapapi/views/js/mysnapapi-wizard.js`:
    *   **Umfang:** Back-Office.
    *   **Beschreibung:** Bietet interaktive Logik für den Einrichtungsassistenten des Moduls, der den Händler durch die anfänglichen Konfigurationsschritte führt.
-   `mysnapapi/views/js/mysnapapi.js`:
    *   **Umfang:** Front-Office.
    *   **Beschreibung:** Haupt-Einstiegspunkt oder allgemeines Dienstprogramm-JavaScript für das Front-Office, das möglicherweise andere Skripte lädt oder globale modulspezifische Funktionen enthält.

### 4.5 CSS-Stylesheets (`views/css/`)

-   `mysnapapi/views/css/mp-inspect.css`:
    *   **Umfang:** Front-Office (Debug-Modus).
    *   **Beschreibung:** Stile für das Debug-Overlay oder die Konsolenausgabe, wenn `mp-inspect.js` aktiv ist.
-   `mysnapapi/views/css/mysnapapi-admin.css`:
    *   **Umfang:** Back-Office-Admin-Formular-Styling.
    *   **Beschreibung:** Stile für die Konfigurationsseite des Moduls, einschließlich Layout, Schaltflächen, Diagnoseabschnitte (Gesundheitsbewertung, Datenqualitäts-Coach) und Assistentenschritte.
-   `mysnapapi/views/css/mysnapapi-debug.css`:
    *   **Umfang:** Front-Office (Debug-Modus).
    *   **Beschreibung:** Zusätzliches Styling für Debug-Elemente, möglicherweise visuelle Indikatoren oder Rahmen für verfolgte Elemente.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

-   `mysnapapi/views/templates/hook/capi-pageview.tpl`:
    *   **Hook:** Potenziell `displayHeader` oder `displayFooter` (serverseitiger Kontext).
    *   **Ausgabe:** Rendert ein verstecktes Element oder einen serverseitigen Aufruf, um ein CAPI `PAGE_VIEW`-Ereignis auszulösen, oft als Fallback oder für den anfänglichen Seitenaufruf verwendet.
-   `mysnapapi/views/templates/hook/debug.tpl`:
    *   **Hook:** `displayHeader` oder `displayFooter` (abhängig vom Debug-Modus).
    *   **Ausgabe:** Rendert Debug-Informationen oder initialisiert Debug-Skripte im Front-Office.
-   `mysnapapi/views/templates/hook/displayOrderConfirmation.tpl`:
    *   **Hook:** `displayOrderConfirmation`.
    *   **Ausgabe:** Rendert das Snap Pixel `PURCHASE`-Ereignis und/oder löst das CAPI `PURCHASE`-Ereignis auf der Bestellbestätigungsseite aus, wobei Bestelldetails übergeben werden.
-   `mysnapapi/views/templates/hook/ghost.tpl`:
    *   **Hook:** `displayHeader` oder `displayFooter`.
    *   **Ausgabe:** Rendert das JavaScript für den „Ghost Collector“ zur Verwaltung von `ScCid`-Cookies.
-   `mysnapapi/views/templates/hook/header.tpl`:
    *   **Hook:** `displayHeader`.
    *   **Ausgabe:** Das primäre Template zur Initialisierung des Snap Pixel-Basiscodes, des `snap`-Objekts und potenziell von `PAGE_VIEW`-Ereignissen. Es lädt notwendige JavaScript-Dateien.
-   `mysnapapi/views/templates/hook/payment.tpl`:
    *   **Hook:** `displayPayment` oder `displayPaymentTop`.
    *   **Ausgabe:** Rendert `INITIATE_CHECKOUT` oder andere relevante Ereignisse während der Zahlungsauswahlphase des Checkouts.
-   `mysnapapi/views/templates/hook/product-details.tpl`:
    *   **Hook:** `displayProductButtons` oder `displayFooterProduct`.
    *   **Ausgabe:** Rendert das Snap Pixel `VIEW_CONTENT`-Ereignis und `ADD_CART`-Ereignis (oder verwandtes JS) auf der Produktseite, wobei produktspezifische Daten übergeben werden.

#### Admin-Templates (`views/templates/admin/`)

-   `mysnapapi/views/templates/admin/consent-guide.tpl`: Zeigt Anleitungen zur Integration mit der Einwilligungsverwaltung an.
-   `mysnapapi/views/templates/admin/doctor.tpl`: Rendert die Oberfläche für das Diagnosewerkzeug „Katalog-Doktor“.
-   `mysnapapi/views/templates/admin/dq.tpl`: Rendert die Empfehlungen des „Datenqualitäts-Coach“.
-   `mysnapapi/views/templates/admin/health.tpl`: Zeigt die „Gesundheitsbewertung“ und verwandte Einblicke an.
-   `mysnapapi/views/templates/admin/linker-domains.tpl`: Eingabefeld und Erklärung für Cross-Domain-Tracking.
-   `mysnapapi/views/templates/admin/live-maintain.tpl`: Oberfläche zur Wartung oder zum Löschen von Live-Statistiken.
-   `mysnapapi/views/templates/admin/live.tpl`: Zeigt das „Live-Statistiken“-Dashboard an.
-   `mysnapapi/views/templates/admin/mode-context.tpl`: Bietet Kontext oder Erklärung für den gewählten Tracking-Modus.
-   `mysnapapi/views/templates/admin/mode-note-both.tpl`: Spezifische Anmerkung für den „Hybrid“-Tracking-Modus.
-   `mysnapapi/views/templates/admin/mode-note-capi.tpl`: Spezifische Anmerkung für den „Nur Conversions API“-Tracking-Modus.
-   `mysnapapi/views/templates/admin/mode-note-pixel.tpl`: Spezifische Anmerkung für den „Nur Pixel“-Tracking-Modus.
-   `mysnapapi/views/templates/admin/mode-picker.tpl`: Die Auswahl-Oberfläche zur Wahl des Tracking-Modus.
-   `mysnapapi/views/templates/admin/properties-list.tpl`: Zeigt eine Liste von Ereigniseigenschaften und deren Regeln an.
-   `mysnapapi/views/templates/admin/recent-events.tpl`: Tabelle oder Liste, die die letzten verfolgten Ereignisse anzeigt.
-   `mysnapapi/views/templates/admin/tabs.tpl`: Rendert die Tab-Navigationsstruktur für die Konfigurationsseite des Moduls.
-   `mysnapapi/views/templates/admin/tag-chips.tpl`: Visuelle Komponenten zur Anzeige von Tags oder Kennungen.
-   `mysnapapi/views/templates/admin/tag-ids.tpl`: Eingabefelder für Pixel-ID und CAPI-Token.
-   `mysnapapi/views/templates/admin/wizard.tpl`: Das Template für den Schritt-für-Schritt-Einrichtungsassistenten.

#### Front-Office-Templates (`views/templates/front/`)

(Keine dedizierten eigenständigen Seitentemplates, alle Front-Office-Templates sind Hook-basiert.)

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Das Modul verwendet hauptsächlich die `ps_configuration`-Tabelle von PrestaShop, um seine Einstellungen zu speichern.

-   `ps_configuration`: Speichert Schlüssel-Wert-Paare für Moduleinstellungen (z. B. `MYSNAPAPI_PIXEL_ID`, `MYSNAPAPI_CAPI_TOKEN`, `MYSNAPAPI_TRACKING_MODE`).
-   Es werden keine benutzerdefinierten SQL-Tabellen explizit vom Modul basierend auf dem bereitgestellten Inventar erstellt. CAPI-Ereignisse könnten vor dem Senden temporär im Speicher oder in einem dateibasierten System in die Warteschlange gestellt werden, anstatt in einer dedizierten Datenbanktabelle.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Rendert im `<head>`-Bereich jeder Front-Office-Seite. | Initialisiert den Snap Pixel-Basiscodes, lädt JS-Assets, löst `PAGE_VIEW`-Ereignisse aus und richtet `ScCid` (Ghost Collector) ein. |
| `displayFooter` | Rendert am Ende des `<body>`-Bereichs jeder Front-Office-Seite. | Kann verzögertes Skriptladen, zusätzliche Ereignisauslöser oder `ScCid`-Verwaltung umfassen. |
| `displayProductButtons` | Auf der Produktseite, in der Nähe des „In den Warenkorb legen“-Buttons. | Löst `VIEW_CONTENT`- und potenziell `ADD_CART`-Ereignisse mit Produktdetails aus. |
| `displayFooterProduct` | Auf der Produktseite, im Fußbereich. | Alternative oder zusätzliche Position für `VIEW_CONTENT`- und `ADD_CART`-Ereignisse. |
| `actionCartSave` | Wird ausgeführt, wenn ein Warenkorb geändert wird (Produkt hinzufügen, aktualisieren, entfernen). | Löst `ADD_CART`- oder `REMOVE_FROM_CART`-Ereignisse aus. |
| `actionValidateOrder` | Wird nach einer erfolgreichen Bestellung ausgeführt. | Löst das entscheidende `PURCHASE`-Ereignis aus und sendet vollständige Bestelldetails (Wert, Währung, Produkte). |
| `displayOrderConfirmation` | Auf der Bestellbestätigungsseite nach einem erfolgreichen Kauf. | Rendert das clientseitige `PURCHASE`-Ereignis für das Snap Pixel. |
| `displayPayment` | Vor der Auswahl der Zahlungsmethode. | Löst das `INITIATE_CHECKOUT`-Ereignis aus. |
| `displayPaymentTop` | Am oberen Rand der Zahlungsseiten. | Alternative oder zusätzliche Position für das `INITIATE_CHECKOUT`-Ereignis. |
| `actionFrontControllerSetMedia` | Wird ausgeführt, wenn ein Front-Controller seine Medien-Assets festlegt. | Fügt modulspezifische CSS- und JavaScript-Dateien in das Front-Office ein. |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin-Controller seine Medien-Assets festlegt. | Fügt modulspezifische CSS- und JavaScript-Dateien in die Back-Office-Konfigurationsseite ein. |
| `actionModuleInstall` | Wird ausgeführt, wenn das Modul installiert wird. | Setzt Standardkonfigurationswerte in `ps_configuration`. |
| `actionModuleUninstall` | Wird ausgeführt, wenn das Modul deinstalliert wird. | Bereinigt Konfigurationswerte aus `ps_configuration`. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und die neuesten Versionen des Snapchat Pixel & Conversions API-Moduls besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Fragen und Problemen bezüglich der Funktionalität und Integration des Moduls gerne zur Verfügung.
