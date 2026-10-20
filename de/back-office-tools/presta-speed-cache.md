---
title: "Presta Speed Cache - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das Presta Speed Cache PrestaShop-Modul von MyPresta.eu."
sidebar:
  label: "Presta Speed Cache - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Presta Speed Cache auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/presta-speed-cache.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/presta-speed-cache/)
>
> ---


# Presta Speed Cache

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5 (Das Modul ist so konzipiert, dass es in diesem Bereich funktioniert und eine breite Kompatibilität bei gleichzeitiger Unterstützung der neuesten stabilen PHP-Versionen gewährleistet.)
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen wie cURL, JSON und OpenSSL sind erforderlich, die typischerweise in den meisten modernen Hosting-Umgebungen verfügbar sind. Für erweiterte Caching-Methoden wie Redis oder Memcached müssen diese Dienste auf Ihrem Server installiert und konfiguriert sein.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbereich für Presta Speed Cache. Hier finden Sie verschiedene Einstellungen, um die Funktionsweise des Caches Ihres Shops zu optimieren.

#### Registerkarte Allgemeine Einstellungen

-   **Cache aktivieren:**

    *   **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für das Modul. Er schaltet die Caching-Funktionalität für Ihren gesamten Shop ein oder aus.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Das Modul beginnt, Seiten zu cachen und schnell bereitzustellen. Die Leistung Ihres Shops wird sich erheblich verbessern.
        *   *Wenn deaktiviert:* Das Modul stoppt das Caching, und Ihr Shop kehrt zur Standard-PrestaShop-Geschwindigkeit zurück, die typischerweise langsamer ist.
    *   **Empfohlener Wert:** **JA**. Dies ist die Kernfunktion des Moduls.
    *   **Händlerszenario / Beispiel:** Sie haben das Modul gerade installiert und möchten die Geschwindigkeitsvorteile aktivieren. Setzen Sie dies auf JA. Wenn Sie ein anderes Modul beheben und vermuten, dass Caching stören könnte, können Sie es vorübergehend deaktivieren.
-   **Cache-Lebensdauer (Minuten):**

    *   **Was diese Einstellung bewirkt:** Bestimmt, wie lange eine gecachte Seite gültig bleibt, bevor das Modul sie als „veraltet“ betrachtet und neu aufbaut.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Höherer Wert (z. B. 1440 für 24 Stunden):* Seiten werden länger aus dem Cache bereitgestellt, was die Serverlast reduziert, aber möglicherweise leicht veraltete Inhalte anzeigt, wenn Sie häufig Änderungen vornehmen (z. B. Preisaktualisierungen).
        *   *Niedrigerer Wert (z. B. 60 für 1 Stunde):* Seiten werden häufiger neu aufgebaut, was frischere Inhalte gewährleistet, aber die Serverlast leicht erhöht.
    *   **Empfohlener Wert:** Beginnen Sie mit **1440** (24 Stunden). Passen Sie dies an, je nachdem, wie häufig sich Ihre Produktdaten ändern.
    *   **Händlerszenario / Beispiel:** Wenn Sie Produktpreise oder -beschreibungen täglich aktualisieren, ist eine Lebensdauer von 24 Stunden in Ordnung. Wenn Sie Blitzverkäufe mit stündlichen Preisänderungen durchführen, können Sie dies auf 60 oder 120 Minuten reduzieren oder sich auf die automatischen Invalidierungsfunktionen verlassen.
-   **Cache-Speichermethode:**

    *   **Was diese Einstellung bewirkt:** Wählt aus, wo die gecachten Seiten gespeichert werden. Verschiedene Methoden bieten unterschiedliche Leistungsniveaus und erfordern spezifische Server-Setups.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Dateisystem (Standard):* Cacht Seiten als Dateien auf der Festplatte Ihres Servers. Am einfachsten einzurichten, gut für die meisten Shops.
        *   *Redis:* Speichert den Cache im Speicher mit dem Redis-Server. Viel schneller als das Dateisystem, ideal für Shops mit hohem Traffic. Erfordert, dass Redis auf Ihrem Server installiert und konfiguriert ist.
        *   *Memcached:* Speichert den Cache im Speicher mit dem Memcached-Server. Ähnlich wie Redis in den Leistungsvorteilen, erfordert ebenfalls eine Server-Einrichtung.
    *   **Empfohlener Wert:** Beginnen Sie mit **Dateisystem**. Wenn Sie einen Shop mit hohem Traffic haben und Ihr Hosting dies unterstützt, ziehen Sie **Redis** oder **Memcached** für maximale Leistung in Betracht.
    *   **Händlerszenario / Beispiel:** Ihr Shop wächst schnell, und Sie erleben gelegentliche Verlangsamungen. Ihr Host bietet Redis an. Der Wechsel zu Redis kann die Leistung dramatisch verbessern.
-   **URLs vom Cache ausschließen:**

    *   **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, bestimmte Seiten oder Abschnitte Ihres Shops anzugeben, die *niemals* gecacht werden sollen. Dies ist nützlich für Seiten mit hochdynamischen oder sensiblen Inhalten.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Hinzufügen von URLs:* Diese Seiten werden immer frisch von PrestaShop generiert, wodurch sichergestellt wird, dass ihr Inhalt immer auf dem neuesten Stand ist, aber die Geschwindigkeit für diese spezifischen Seiten geopfert wird.
        *   *Leer lassen:* Alle berechtigten Seiten werden gecacht.
    *   **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben spezifische Bedürfnisse. Mit Vorsicht verwenden.
    *   **Händlerszenario / Beispiel:** Sie haben eine benutzerdefinierte „Angebotsanfrage“-Seite, die einzigartige Formulare basierend auf Benutzereingaben generiert, oder eine Seite mit Echtzeit-Lagerbestandsaktualisierungen von einer externen API. Sie würden `/module/yourmodule/quotepage` oder `/stock-updates` zu dieser Liste hinzufügen.
-   **Cache aufwärmen:**

    *   **Was diese Einstellung bewirkt:** „Besucht“ die Seiten Ihres Shops automatisch im Hintergrund, um den Cache vorab zu füllen, wodurch sichergestellt wird, dass auch der erste Besucher einer Seite die Geschwindigkeitsvorteile erlebt.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Ihr Cache wird proaktiv gefüllt, was zu schnelleren Ladezeiten für alle Besucher führt, auch für diejenigen, die eine Seite zum ersten Mal nach der Cache-Invalidierung besuchen. Dies kann die Serverlast während des Aufwärmvorgangs leicht erhöhen.
        *   *Wenn deaktiviert:* Seiten werden erst nach dem ersten Kundenbesuch gecacht.
    *   **Empfohlener Wert:** **JA**. Dies gewährleistet maximale Geschwindigkeitsvorteile für alle Benutzer.
    *   **Händlerszenario / Beispiel:** Sie haben gerade Ihren Cache geleert oder viele Produkte aktualisiert. Das Aktivieren des Aufwärmens stellt sicher, dass Ihr Shop sofort schnell für Kunden ist, anstatt darauf zu warten, dass sie jede Seite zuerst besuchen.
-   **HTML-Optimierung:**

    *   **Was diese Einstellung bewirkt:** Minifiziert die HTML-Ausgabe Ihrer Seiten, indem unnötige Leerzeichen, Kommentare und Zeilenumbrüche entfernt werden. Dies verkleinert die Dateigröße der Seite, was zu schnelleren Downloads führt.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Der HTML-Code Ihrer Seite wird kompakter, wodurch die Bandbreitennutzung reduziert und das Rendern der Seite leicht beschleunigt wird. Dies ist im Allgemeinen sicher.
        *   *Wenn deaktiviert:* HTML wird so bereitgestellt, wie es von PrestaShop generiert wurde, ohne Minifizierung.
    *   **Empfohlener Wert:** **JA**. Es ist eine einfache, sichere Leistungssteigerung.
    *   **Händlerszenario / Beispiel:** Sie möchten jede Leistungsreserve aus Ihrem Shop herausholen. Das Aktivieren dieser Option macht Ihr HTML schlanker.

#### Registerkarte Dynamische Blöcke

Dieser Abschnitt ermöglicht es Ihnen, Teile Ihrer Seite zu definieren, die *nicht* gecacht, sondern dynamisch geladen werden sollen, nachdem die Hauptseite geladen wurde. Dies ist entscheidend für personalisierte Inhalte wie den Warenkorb, den Anmeldestatus oder spezifische Modulausgaben.

-   **Dynamische Blöcke aktivieren:**

    *   **Was diese Einstellung bewirkt:** Aktiviert die Möglichkeit, spezifische Bereiche Ihrer Seite zu definieren, die separat und dynamisch geladen werden, auch wenn der Rest der Seite aus dem Cache bereitgestellt wird.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Sie können spezifische Module oder Inhaltsbereiche so konfigurieren, dass sie dynamisch bleiben, wodurch sichergestellt wird, dass personalisierte Inhalte immer aktuell sind.
        *   *Wenn deaktiviert:* Alle Inhalte werden gecacht, was möglicherweise zu veralteten dynamischen Inhalten führt (z. B. ein leerer Warenkorb, der angezeigt wird, obwohl Artikel hinzugefügt wurden).
    *   **Empfohlener Wert:** **JA**. Dies ist für einen funktionsfähigen gecachten Shop unerlässlich.
    *   **Händlerszenario / Beispiel:** Sie möchten, dass der Warenkorb Ihres Kunden immer die richtige Anzahl von Artikeln anzeigt, auch wenn die Produktseite selbst gecacht ist.
-   **Liste der dynamischen Module:**

    *   **Was diese Einstellung bewirkt:** Dies ist eine Liste, in der Sie auswählen, welche Module *immer* dynamisch gerendert werden sollen, auch wenn sie in eine gecachte Seite eingehängt sind.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Hinzufügen eines Moduls:* Die Ausgabe dieses Moduls wird für jeden Benutzer frisch abgerufen, wodurch sichergestellt wird, dass sein Inhalt immer aktuell ist (z. B. Warenkorbblock, Benutzerinformationsblock).
        *   *Entfernen eines Moduls:* Die Ausgabe des Moduls wird zusammen mit dem Rest der Seite gecacht, wodurch möglicherweise veraltete Daten angezeigt werden.
    *   **Empfohlener Wert:** Fügen Sie Module wie `ps_shoppingcart`, `ps_customeraccountlinks`, `ps_languageselector`, `ps_currencyselector` und jedes andere Modul hinzu, das benutzerspezifische oder Echtzeitinformationen anzeigt.
    *   **Händlerszenario / Beispiel:** Sie installieren ein neues „Live-Chat“-Modul, das die Echtzeitverfügbarkeit anzeigen muss. Sie würden es dieser Liste hinzufügen, um sicherzustellen, dass es immer dynamisch ist.

#### Registerkarte Invalidierung & Löschen

Dieser Abschnitt verwaltet, wie und wann der Cache geleert oder aktualisiert wird, um sicherzustellen, dass Ihre Kunden immer die neuesten Produktinformationen sehen.

-   **Automatische Cache-Invalidierung:**

    *   **Was diese Einstellung bewirkt:** Wenn aktiviert, löscht das Modul automatisch relevante gecachte Seiten, wenn Sie Änderungen in Ihrem PrestaShop-Backoffice vornehmen (z. B. ein Produkt, eine Kategorie oder eine CMS-Seite aktualisieren).
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Sie müssen den Cache nach jeder Änderung nicht manuell leeren. Das Modul löscht intelligent nur die betroffenen Seiten, wodurch sichergestellt wird, dass Kunden Updates schnell sehen.
        *   *Wenn deaktiviert:* Sie müssten den gesamten Cache nach jeder größeren Änderung manuell leeren, oder Kunden könnten veraltete Inhalte sehen, bis die Cache-Lebensdauer abläuft.
    *   **Empfohlener Wert:** **JA**. Dies ist eine entscheidende „einmal einstellen und vergessen“-Funktion für die Datenaktualität.
    *   **Händlerszenario / Beispiel:** Sie aktualisieren den Preis eines Produkts. Mit der automatischen Invalidierung wird die gecachte Version dieser Produktseite (und möglicherweise ihrer Kategorieseiten) gelöscht, sodass Kunden den neuen Preis sofort sehen.
-   **Cache bei Produktaktualisierung löschen:**

    *   **Was diese Einstellung bewirkt:** Steuert speziell, ob der mit einem Produkt verbundene Cache gelöscht wird, wenn dieses Produkt aktualisiert wird.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Stellt sicher, dass jede Seite, die das aktualisierte Produkt anzeigt (Produktseite, Kategorieseite, Suchergebnisse), im Cache aktualisiert wird.
        *   *Wenn deaktiviert:* Produktaktualisierungen werden möglicherweise nicht auf gecachten Seiten angezeigt, bis die Cache-Lebensdauer abläuft oder Sie sie manuell leeren.
    *   **Empfohlener Wert:** **JA**. Wesentlich für genaue Produktinformationen.
    *   **Händlerszenario / Beispiel:** Sie ändern das Bild eines Produkts. Diese Einstellung stellt sicher, dass das neue Bild sofort auf der Produktseite erscheint.
-   **Cache bei Kategorieaktualisierung löschen:**

    *   **Was diese Einstellung bewirkt:** Steuert, ob der mit einer Kategorie verbundene Cache gelöscht wird, wenn diese Kategorie aktualisiert wird.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Stellt sicher, dass Kategorieseiten und möglicherweise Produktseiten innerhalb dieser Kategorie aktualisiert werden.
        *   *Wenn deaktiviert:* Kategorieaktualisierungen (z. B. Name, Beschreibung, zugewiesene Produkte) werden möglicherweise nicht auf gecachten Seiten angezeigt.
    *   **Empfohlener Wert:** **JA**. Wichtig für die Navigation und die Genauigkeit des Kategorieinhalts.
    *   **Händlerszenario / Beispiel:** Sie benennen eine Kategorie um. Dies stellt sicher, dass der neue Name in Ihrer Navigation und auf der Kategorieseite erscheint.
-   **Cache bei CMS-Seitenaktualisierung löschen:**

    *   **Was diese Einstellung bewirkt:** Steuert, ob der mit einer CMS-Seite verbundene Cache gelöscht wird, wenn diese Seite aktualisiert wird.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Stellt sicher, dass aktualisierte CMS-Seiten (z. B. „Über uns“, „Allgemeine Geschäftsbedingungen“) sofort aktualisiert werden.
        *   *Wenn deaktiviert:* Aktualisierungen von CMS-Seiten sind für Kunden möglicherweise erst sichtbar, wenn der Cache abläuft.
    *   **Empfohlener Wert:** **JA**. Wichtig für die Genauigkeit statischer Inhalte.
    *   **Händlerszenario / Beispiel:** Sie aktualisieren Ihre Seite „Versandrichtlinien“. Dies stellt sicher, dass Kunden die neueste Version sehen.

#### Registerkarte Erweiterte Einstellungen

-   **Debug-Modus aktivieren:**

    *   **Was diese Einstellung bewirkt:** Aktiviert einen speziellen Modus, der Informationen über den Cache-Status direkt auf Ihren Front-Office-Seiten anzeigt (nur für Sie als Administrator sichtbar).
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Sie sehen eine kleine Überlagerung auf Ihren Shop-Seiten, die anzeigt, ob die Seite aus dem Cache bereitgestellt wurde, wann sie gecacht wurde und andere diagnostische Details. Dies ist für die Fehlerbehebung von unschätzbarem Wert.
        *   *Wenn deaktiviert:* Es werden keine Debug-Informationen angezeigt.
    *   **Empfohlener Wert:** **NEIN** für Live-Produktionsshops. **JA** beim Einrichten oder Beheben von Problemen.
    *   **Händlerszenario / Beispiel:** Sie haben das Modul gerade konfiguriert und möchten überprüfen, ob Seiten tatsächlich korrekt gecacht werden. Aktivieren Sie den Debug-Modus, durchsuchen Sie Ihren Shop und überprüfen Sie die Überlagerung.
-   **Live-Debug aktivieren:**

    *   **Was diese Einstellung bewirkt:** Bietet ein Echtzeit-Dashboard im Back Office zur Überwachung von Cache-Hits, -Misses und anderen Leistungsmetriken.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Sie erhalten Zugriff auf ein leistungsstarkes Überwachungstool, um zu sehen, wie effektiv Ihr Cache funktioniert.
        *   *Wenn deaktiviert:* Es werden keine Live-Cache-Statistiken gesammelt oder angezeigt.
    *   **Empfohlener Wert:** **JA**, wenn Sie die Leistung aktiv überwachen möchten. Kann deaktiviert werden, wenn Sie minimalen Overhead bevorzugen.
    *   **Händlerszenario / Beispiel:** Sie möchten die Auswirkungen Ihrer Caching-Strategie im Laufe der Zeit sehen und beobachten, wie viele Anfragen aus dem Cache bedient werden, im Vergleich zu frisch generierten.
-   **SWR (Stale-While-Revalidate) aktivieren:**

    *   **Was diese Einstellung bewirkt:** Eine erweiterte Caching-Strategie, bei der, wenn eine gecachte Seite abgelaufen ist, das Modul sofort die *veraltete* (abgelaufene) Version an den Benutzer liefert, während gleichzeitig im Hintergrund eine frische Version neu aufgebaut wird.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Benutzer erhalten fast immer eine sofortige Seitenladung, auch wenn der Cache abgelaufen ist. Die Seite kann für einen Moment leicht veraltet sein, ist aber unglaublich schnell. Die frische Version ersetzt die veraltete für nachfolgende Besucher.
        *   *Wenn deaktiviert:* Wenn eine gecachte Seite abläuft, wartet der nächste Besucher, bis die Seite neu aufgebaut wird, was zu einer leichten Verzögerung führen kann.
    *   **Empfohlener Wert:** **JA**. Dies bietet das beste Gleichgewicht zwischen Geschwindigkeit und Aktualität für die meisten Shops.
    *   **Händlerszenario / Beispiel:** Sie möchten sicherstellen, dass Ihre Kunden niemals eine langsame Ladung erleben, auch wenn der Cache aktualisiert werden muss. SWR bietet dieses „immer schnelle“ Erlebnis.
-   **Cache für angemeldete Benutzer:**

    *   **Was diese Einstellung bewirkt:** Bestimmt, ob Seiten auch für Kunden, die in ihren Konten angemeldet sind, gecacht werden sollen.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Angemeldete Benutzer profitieren ebenfalls von gecachten Seiten, aber das Modul muss sehr intelligent mit dynamischen Blöcken umgehen, um sicherzustellen, dass personalisierte Inhalte (wie „Mein Konto“-Links, Bestellhistorie) korrekt bleiben.
        *   *Wenn deaktiviert:* Angemeldete Benutzer erhalten immer frische, ungecachte Seiten. Dies gewährleistet eine perfekte Personalisierung, opfert aber die Geschwindigkeit für diese Benutzer.
    *   **Empfohlener Wert:** **JA**, stellen Sie jedoch sicher, dass Ihre dynamischen Blöcke für Module wie `ps_customeraccountlinks` korrekt konfiguriert sind.
    *   **Händlerszenario / Beispiel:** Sie möchten, dass Ihre wiederkehrenden, angemeldeten Kunden ebenfalls ein superschnelles Erlebnis genießen, nicht nur Gäste.
-   **Cache für mobile Geräte:**

    *   **Was diese Einstellung bewirkt:** Steuert, ob separate gecachte Versionen von Seiten für mobile Geräte generiert und bereitgestellt werden.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Das Modul erstellt und liefert optimierte gecachte Seiten speziell für mobile Benutzer, was entscheidend ist, wenn Ihr Theme erhebliche Unterschiede zwischen Desktop- und mobilen Layouts aufweist.
        *   *Wenn deaktiviert:* Mobile Benutzer erhalten entweder die Desktop-Cache-Version (falls zutreffend) oder ungecachte Seiten, was möglicherweise zu langsameren oder falsch gerenderten Inhalten führt.
    *   **Empfohlener Wert:** **JA**, wenn Ihr Theme responsiv ist und für Mobilgeräte anders gerendert wird.
    *   **Händlerszenario / Beispiel:** Ihr Theme verwendet unterschiedliche Vorlagen oder CSS für Mobilgeräte. Das Caching für Mobilgeräte stellt sicher, dass sie die korrekte, schnelle Version erhalten.
-   **Edge Purge (Varnish/CDN) aktivieren:**

    *   **Was diese Einstellung bewirkt:** Integriert sich in externe Caching-Systeme wie Varnish oder Content Delivery Networks (CDNs), um Purge-Anfragen zu senden, wenn Ihr PrestaShop-Cache invalidiert wird. Dies stellt sicher, dass das CDN auch seine alten Inhalte löscht.
    *   **Auswirkung der Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Ihr CDN liefert nach Ihren Updates immer die aktuellsten Inhalte, wodurch verhindert wird, dass Kunden alte, vom CDN gespeicherte Versionen sehen.
        *   *Wenn deaktiviert:* Ihr CDN könnte weiterhin alte Inhalte bereitstellen, auch nachdem Ihr PrestaShop-Cache geleert wurde, was zu Inkonsistenzen führen kann.
    *   **Empfohlener Wert:** **JA**, wenn Sie Varnish oder ein CDN (wie Cloudflare, Akamai usw.) verwenden, das das Cache-Purging über API unterstützt.
    *   **Händlerszenario / Beispiel:** Sie verwenden Cloudflare für die Leistung. Wenn Sie ein Produkt aktualisieren, weist diese Einstellung Cloudflare an, seinen Cache für dieses Produkt zu leeren, sodass alle Benutzer die Aktualisierung sofort sehen.

#### Registerkarte Tools

Diese Registerkarte bietet manuelle Aktionen zur Verwaltung Ihres Caches.

-   **Gesamten Cache leeren:**

    *   **Was diese Einstellung bewirkt:** Diese Schaltfläche löscht sofort alle vom Presta Speed Cache generierten gecachten Seiten.
    *   **Auswirkung der Änderung dieser Einstellung:** Alle gecachten Inhalte werden entfernt. Wenn eine Seite das nächste Mal besucht wird, wird sie frisch von PrestaShop generiert und dann erneut gecacht. Dies verlangsamt Ihre Website vorübergehend, bis der Cache neu aufgebaut ist.
    *   **Empfohlener Wert:** Nur bei Bedarf verwenden (z. B. nach einem größeren Theme-Update, einer Modulinstallation oder wenn Sie Cache-Probleme vermuten).
    *   **Händlerszenario / Beispiel:** Sie haben umfangreiche Änderungen am CSS Ihres Themes vorgenommen und möchten sicherstellen, dass alle Besucher das neue Design sofort sehen. Klicken Sie auf „Gesamten Cache leeren“.
-   **Cache-Aufwärmen starten:**

    *   **Was diese Einstellung bewirkt:** Löst manuell den Cache-Aufwärmprozess aus, der die Seiten Ihres Shops besucht, um den Cache vorab zu füllen.
    *   **Auswirkung der Änderung dieser Einstellung:** Das Modul beginnt, gecachte Versionen Ihrer Seiten im Hintergrund zu generieren. Dies kann je nach Größe Ihres Shops einige Zeit dauern und während des Prozesses Serverressourcen verbrauchen.
    *   **Empfohlener Wert:** Nach dem Leeren des Caches oder nach größeren Produkt-/Kategorieimporten verwenden, um den Cache schnell neu aufzubauen.
    *   **Händlerszenario / Beispiel:** Sie haben gerade den Cache geleert und möchten, dass Ihr Shop so schnell wie möglich für Kunden ist.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### 2.2.1 Cache-Verwaltung (Back Office > Presta Speed Cache > Cache-Verwaltung)

Dieser Bildschirm bietet eine detaillierte Übersicht und Verwaltungsoberfläche für Ihre gecachten Seiten.

-   **Bildschirmname & Menüpfad:** Sie finden dies, indem Sie im Hauptmenü Ihres PrestaShop-Backoffices zu **Presta Speed Cache** navigieren und dann **Cache-Verwaltung** auswählen.
-   **Verfügbare Aktionen & Einstellungen:**
    *   **Cache-Listenraster:** Diese Tabelle zeigt eine Liste der aktuell gecachten Seiten, einschließlich Details wie URL, wann sie zuletzt gecacht wurde, ihre Größe und ihr aktueller Status (z. B. aktiv, abgelaufen).
    *   **Filtern und Suchen:** Sie können die Liste nach URL, Status oder anderen Kriterien filtern, um bestimmte Cache-Einträge zu finden.
    *   **Ausgewählten Cache leeren:** Ermöglicht es Ihnen, bestimmte gecachte Seiten aus der Liste auszuwählen und einzeln zu leeren.
    *   **Gesamten Cache leeren (Schaltfläche):** Eine prominente Schaltfläche zum Leeren des gesamten Caches, ähnlich der auf der Hauptkonfigurationsseite.
    *   **Aufwärmen starten (Schaltfläche):** Eine prominente Schaltfläche zum manuellen Starten des Cache-Aufwärmprozesses.
-   **Auswirkung von Änderungen:**
    *   *Löschen einzelner Einträge:* Nur die ausgewählten Seiten werden aus dem Cache entfernt, sodass sie beim nächsten Besuch neu aufgebaut werden können. Dies ist nützlich für gezielte Updates, ohne den gesamten Shop zu beeinflussen.
    *   *Löschen des gesamten Caches:* Setzt den gesamten Cache zurück und zwingt alle Seiten zum Neuaufbau.
    *   *Aufwärmen starten:* Füllt den Cache proaktiv, um schnellere Ladezeiten für nachfolgende Besucher zu gewährleisten.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Verwenden Sie diesen Bildschirm, um Ihren Cache zu überwachen, Seiten zu identifizieren, die möglicherweise nicht korrekt gecacht werden, oder um gezielte Cache-Löschungen durchzuführen, wenn Sie ein sehr spezifisches Update vorgenommen haben, das die automatische Invalidierung möglicherweise übersehen hat.

#### 2.2.2 Dashboard (Back Office > Presta Speed Cache > Dashboard)

Dieser Bildschirm bietet eine visuelle Übersicht über Ihre Cache-Leistung und -Statistiken.

-   **Bildschirmname & Menüpfad:** Sie finden dies, indem Sie im Hauptmenü Ihres PrestaShop-Backoffices zu **Presta Speed Cache** navigieren und dann **Dashboard** auswählen.
-   **Verfügbare Aktionen & Einstellungen:**
    *   **Leistungsmetriken:** Zeigt Diagramme und Statistiken zu Cache-Hits, Cache-Misses, durchschnittlichen Seitenladezeiten (mit und ohne Cache) und anderen relevanten Leistungsindikatoren an.
    *   **Cache-Zustandsstatus:** Bietet einen schnellen Überblick über den Zustand des Cache-Systems und zeigt an, ob es Probleme gibt oder ob es optimal funktioniert.
    *   **Jüngste Invalidierungsereignisse:** Zeigt ein Protokoll der jüngsten Cache-Invalidierungen an, das Ihnen hilft, zu verfolgen, wann und warum Teile Ihres Caches geleert wurden.
-   **Auswirkung von Änderungen:** Dieser Bildschirm dient hauptsächlich der Überwachung und Berichterstattung. Es werden hier keine direkten Änderungen an der Cache-Konfiguration vorgenommen, aber er hilft Ihnen, die Auswirkungen Ihrer Einstellungen zu verstehen.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Überprüfen Sie regelmäßig das Dashboard, um sicherzustellen, dass Ihr Cache wie erwartet funktioniert. Achten Sie auf hohe Cache-Hit-Raten und niedrige Ladezeiten. Wenn Sie einen plötzlichen Rückgang der Cache-Hits oder eine Zunahme der Ladezeiten feststellen, könnte dies auf ein Konfigurationsproblem oder ein Problem mit Ihrem Server hinweisen.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | Cache aktivieren | JA | Hauptschalter für das Caching. JA = schnellerer Shop. |
| | Cache-Lebensdauer (Minuten) | 1440 (24 Stunden) | Wie lange eine Seite gecacht bleibt. Höher = weniger Serverlast, potenziell ältere Inhalte. |
| | Cache-Speichermethode | Dateisystem | Wo der Cache gespeichert wird. Dateisystem (einfach), Redis/Memcached (schneller, erfordert Server-Setup). |
| | URLs vom Cache ausschließen | Leer | URLs, die niemals gecacht werden sollen (z. B. hochdynamische Seiten). |
| | Cache aufwärmen | JA | Baut den Cache proaktiv im Hintergrund auf. JA = schneller für Erstbesucher. |
| | HTML-Optimierung | JA | Minifiziert HTML für kleinere Seitengrößen. JA = leichte Geschwindigkeitssteigerung. |
| | Dynamische Blöcke aktivieren | JA | Ermöglicht es, dass bestimmte Inhalte (Warenkorb, Login) dynamisch bleiben. JA = unerlässlich für personalisierte Inhalte. |
| | Liste der dynamischen Module | `ps_shoppingcart`, `ps_customeraccountlinks`, etc. | Module, deren Ausgabe immer dynamisch sein sollte. |
| | Automatische Cache-Invalidierung | JA | Löscht relevanten Cache bei Back-Office-Änderungen. JA = frische Inhalte ohne manuelles Eingreifen. |
| | Cache bei Produktaktualisierung löschen | JA | Löscht produktbezogenen Cache, wenn Produkte aktualisiert werden. |
| | Cache bei Kategorieaktualisierung löschen | JA | Löscht kategoriebezogenen Cache, wenn Kategorien aktualisiert werden. |
| | Cache bei CMS-Seitenaktualisierung löschen | JA | Löscht CMS-seitenbezogenen Cache, wenn CMS-Seiten aktualisiert werden. |
| | Debug-Modus aktivieren | NEIN (JA zur Fehlerbehebung) | Zeigt Cache-Informationen im Front Office an. |
| | Live-Debug aktivieren | JA | Bietet Echtzeit-Cache-Statistiken im BO. |
| | SWR (Stale-While-Revalidate) aktivieren | JA | Liefert veralteten Cache aus, während frischer neu aufgebaut wird. JA = immer schnell. |
| | Cache für angemeldete Benutzer | JA | Cacht Seiten für angemeldete Benutzer. |
| | Cache für mobile Geräte | JA | Cacht separate Versionen für Mobilgeräte. |
| | Edge Purge (Varnish/CDN) aktivieren | NEIN (JA bei Verwendung von CDN) | Integriert sich mit externen CDN/Varnish für Cache-Purging. |
| | Gesamten Cache leeren (Schaltfläche) | Bei Bedarf verwenden | Löscht den gesamten Cache manuell. |
| | Cache-Aufwärmen starten (Schaltfläche) | Bei Bedarf verwenden | Löst die manuelle Cache-Vorbefüllung aus. |
| **Cache-Verwaltungsbildschirm** | Cache-Listenraster | N/A | Zeigt einzelne gecachte Seiten an und ermöglicht deren Verwaltung. |
| | Ausgewählten Cache leeren | N/A | Löscht spezifische Cache-Einträge. |
| **Dashboard-Bildschirm** | Leistungsmetriken | N/A | Visualisiert Cache-Hits, -Misses und Ladezeiten. |
| | Cache-Zustandsstatus | N/A | Zeigt den Gesamtzustand des Caching-Systems an. |

## 3. Fehlerbehebung für Händler & Häufig gestellte Fragen (FAQ)

**F: Mein Shop sieht kaputt aus oder zeigt alte Inhalte an, nachdem ich den Cache aktiviert habe. Was soll ich tun?**
A: Versuchen Sie zuerst, Ihren gesamten Cache mit der Schaltfläche „Gesamten Cache leeren“ in der Modulkonfiguration oder im Bildschirm „Cache-Verwaltung“ zu leeren. Leeren Sie auch den Cache Ihres Browsers. Wenn das Problem weiterhin besteht, überprüfen Sie Ihre „Liste der dynamischen Module“, um sicherzustellen, dass alle Module, die personalisierte oder Echtzeitinhalte anzeigen, enthalten sind. Deaktivieren Sie vorübergehend die „HTML-Optimierung“, um zu sehen, ob sie Konflikte verursacht.

**F: Mein Warenkorb wird nicht korrekt aktualisiert, oder Benutzer scheinen manchmal abgemeldet zu sein.**
A: Dies liegt fast immer daran, dass dynamische Inhalte nicht ordnungsgemäß vom Caching ausgeschlossen wurden. Gehen Sie zur Registerkarte „Dynamische Blöcke“ und stellen Sie sicher, dass Module wie `ps_shoppingcart`, `ps_customeraccountlinks`, `ps_languageselector` und `ps_currencyselector` zur „Liste der dynamischen Module“ hinzugefügt wurden. Wenn Sie andere benutzerdefinierte Module haben, die benutzerspezifische Daten anzeigen, fügen Sie diese ebenfalls hinzu.

**F: Meine Website ist immer noch langsam, obwohl das Modul aktiviert ist.**
A:

1.  **Debug-Modus überprüfen:** Aktivieren Sie den „Debug-Modus“ (in den erweiterten Einstellungen) und durchsuchen Sie Ihr Front Office. Zeigt es an, dass Seiten aus dem Cache bereitgestellt werden („Cache HIT“)? Wenn Sie „Cache MISS“ sehen, werden die Seiten nicht gecacht.
2.  **Cache-Hit-Rate überprüfen:** Überprüfen Sie im „Dashboard“ Ihre Cache-Hit-Rate. Wenn sie niedrig ist, überprüfen Sie Ihre Einstellungen für „Cache-Lebensdauer“ und „URLs ausschließen“.
3.  **Serverressourcen:** Obwohl Caching die Last reduziert, benötigt Ihr Server immer noch ausreichende Ressourcen. Überprüfen Sie Ihren Hosting-Plan und die Serverprotokolle auf andere Engpässe.
4.  **Andere Optimierungen:** Caching ist ein Teil der Geschwindigkeit. Stellen Sie sicher, dass Ihre Bilder optimiert sind, Ihr Theme effizient ist und Sie nicht zu viele schwere, unoptimierte Module ausführen.

**F: Wie stelle ich sicher, dass mein mehrsprachiger oder mehrwährungsfähiger Shop korrekt mit Caching funktioniert?**
A: Presta Speed Cache ist so konzipiert, dass es mehrsprachige und mehrwährungsfähige Shops durch die Generierung separater Cache-Einträge für jede Kombination verarbeitet. Stellen Sie sicher, dass Ihre Sprach- und Währungsauswahlmodule zur „Liste der dynamischen Module“ hinzugefügt wurden. Wenn Sie Probleme bemerken, aktivieren Sie gegebenenfalls „Cache für angemeldete Benutzer“ und „Cache für mobile Geräte“, da diese auch beeinflussen können, wie verschiedene Versionen von Seiten gecacht werden.

**F: Ich habe ein Produkt aktualisiert, aber die alten Informationen werden immer noch im Front Office angezeigt.**
A:

1.  **Automatische Invalidierung:** Stellen Sie sicher, dass „Automatische Cache-Invalidierung“ und „Cache bei Produktaktualisierung löschen“ auf der Registerkarte „Invalidierung & Löschen“ aktiviert sind.
2.  **Manuelles Leeren:** Wenn die Einstellungen korrekt sind, versuchen Sie, den Cache für diese spezifische Produktseite manuell über den Bildschirm „Cache-Verwaltung“ zu leeren oder den gesamten Cache zu leeren.
3.  **CDN/Varnish:** Wenn Sie ein CDN oder Varnish verwenden, stellen Sie sicher, dass „Edge Purge aktivieren“ korrekt konfiguriert ist, da Ihr CDN möglicherweise eine alte Version bereitstellt.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Presta Speed Cache ist eine hochoptimierte Caching-Lösung für PrestaShop, die eine ausgeklügelte Architektur verwendet, um Geschwindigkeit ohne Kompromisse bei dynamischen Inhalten zu liefern. Es nutzt das MVC-Muster von PrestaShop, indem es Kernklassen (`Controller`, `FrontController`, `Dispatcher`, `Hook`) überschreibt, um Anfragen und Antworten abzufangen und gecachtes HTML bereitzustellen, wenn verfügbar. Es verwendet eine flexible Speicher-Engine (Datei, Redis, Memcached) und implementiert erweiterte Funktionen wie SWR (Stale-While-Revalidate), dynamisches Block-Rendering über AJAX und intelligente Cache-Invalidierung. Das Design des Moduls konzentriert sich auf minimalen Overhead und maximale Kompatibilität und bietet eine robuste und erweiterbare Caching-Schicht.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

Diese Controller verarbeiten spezifische AJAX-Anfragen oder Hintergrundaufgaben im Zusammenhang mit dem Caching.

-   `prestaspeedcache/controllers/front/api.php`
    *   **Klassenname & Elternklasse:** `PrestaSpeedCacheApiModuleFrontController` erweitert `ModuleFrontController`.
    *   **Verantwortlichkeit:** Verarbeitet API-Anfragen, hauptsächlich zum Abrufen dynamischer Inhalte. Wenn eine gecachte Seite bereitgestellt wird und dynamische Blöcke enthält, ist dieser Controller für die Bereitstellung des frischen HTML für diese Blöcke über AJAX verantwortlich. Er empfängt Parameter, die das Modul und den Hook identifizieren, rendert das Modul und gibt das HTML zurück.
-   `prestaspeedcache/controllers/front/cron.php`
    *   **Klassenname & Elternklasse:** `PrestaSpeedCacheCronModuleFrontController` erweitert `ModuleFrontController`.
    *   **Verantwortlichkeit:** Entwickelt, um von einem serverseitigen Cron-Job aufgerufen zu werden. Er löst Hintergrundaufgaben wie Cache-Aufwärmen, Verarbeitung der Invalidierungswarteschlange und andere Wartungsoperationen aus. Dies entlastet Benutzeranfragen von schwerer Verarbeitung.
-   `prestaspeedcache/controllers/front/dynamic.php`
    *   **Klassenname & Elternklasse:** `PrestaSpeedCacheDynamicModuleFrontController` erweitert `ModuleFrontController`.
    *   **Verantwortlichkeit:** Ähnlich wie `api.php` verarbeitet dieser Controller speziell Anfragen für dynamische Inhaltsblöcke, die asynchron in gecachte Seiten geladen werden. Er stellt sicher, dass personalisierte Elemente wie der Warenkorb oder Benutzerinformationen immer aktuell sind.
-   `prestaspeedcache/controllers/front/index.php`
    *   **Klassenname & Elternklasse:** `PrestaSpeedCacheIndexModuleFrontController` erweitert `ModuleFrontController`.
    *   **Verantwortlichkeit:** Ein Platzhalter oder Fallback-Front-Controller. In vielen Modulen dient `index.php` in `controllers/front` als Standard-Einstiegspunkt, wenn kein anderer spezifischer Controller übereinstimmt. Er könnte grundlegendes Routing auf Modulebene verwalten oder einfach weiterleiten.

#### Back-Office-Admin-Controller

Diese Controller verwalten die Konfiguration und Daten des Moduls im PrestaShop Back Office.

-   `prestaspeedcache/controllers/admin/AdminPrestaSpeedCacheController.php`
    *   **Klassenname & Elternklasse:** `AdminPrestaSpeedCacheController` erweitert `ModuleAdminController`.
    *   **Registerkartenname und verwaltete Entität:** Dies ist der primäre administrative Controller für das Modul, der die Cache-Einträge verwaltet und die Ansichten „Cache-Verwaltung“ und „Dashboard“ bereitstellt. Er verarbeitet das Auflisten, Filtern und Löschen von Cache-Einträgen. Er verwaltet keine spezifische `ObjectModel`-Entität direkt, sondern interagiert mit dem `PscCacheRepository` für Cache-Operationen.
-   `prestaspeedcache/controllers/admin/index.php`
    *   **Klassenname & Elternklasse:** `AdminPrestaSpeedCacheIndexController` erweitert `ModuleAdminController`.
    *   **Registerkartenname und verwaltete Entität:** Ähnlich wie das Front-Office `index.php` ist dies wahrscheinlich ein Platzhalter oder Standard-Controller für den Admin-Bereich des Moduls, der einen gültigen Einstiegspunkt gewährleistet, wenn keine spezifische Aktion angefordert wird.

### 4.3 Kernklassen & Modelle (`classes/`)

Das `classes/`-Verzeichnis des Moduls enthält die Kernlogik, Dienste und Datenstrukturen.

-   `prestaspeedcache/classes/PscAdminChips.php`: Verwaltet UI-Komponenten für die Admin-Oberfläche.
-   `prestaspeedcache/classes/PscAfterDefaults.php`: Behandelt Standardeinstellungen oder Konfigurationen nach der Installation.
-   `prestaspeedcache/classes/PscAutoload.php`: Benutzerdefinierter Autoloader für Modulklassen.
-   `prestaspeedcache/classes/PscCacheEngine.php`: Die Haupt-Caching-Engine, die Cache-Operationen orchestriert.
-   `prestaspeedcache/classes/PscCacheInvalidator.php`: Verwaltet die Logik zur Invalidierung gecachter Seiten basierend auf Back-Office-Aktionen.
-   `prestaspeedcache/classes/PscCacheKey.php`: Generiert eindeutige Schlüssel für gecachte Einträge basierend auf URL, Kontext usw.
-   `prestaspeedcache/classes/PscCacheLock.php`: Implementiert Sperrmechanismen, um Race Conditions während der Cache-Generierung zu verhindern.
-   `prestaspeedcache/classes/PscCacheRepository.php`: Verwaltet die Interaktion mit dem Cache-Speicher und bietet eine Abstraktionsschicht.
-   `prestaspeedcache/classes/PscCacheStorage.php`: Abstrakte Basisklasse oder Schnittstelle für Cache-Speicherimplementierungen.
-   `prestaspeedcache/classes/PscCacheTags.php`: Verwaltet Cache-Tags für eine granulare Invalidierung (z. B. alle Seiten, die mit Produkt-ID 123 zusammenhängen).
-   `prestaspeedcache/classes/PscConfig.php`: Verwaltet Modulkonfigurationseinstellungen (liest und schreibt in `ps_configuration`).
-   `prestaspeedcache/classes/PscDynamicBlocks.php`: Logik zum Identifizieren und Verarbeiten dynamischer Inhaltsblöcke.
-   `prestaspeedcache/classes/PscDynamicModules.php`: Verwaltet die Liste der Module, deren Ausgabe immer dynamisch sein sollte.
-   `prestaspeedcache/classes/PscEdgePurge.php`: Verwaltet die Integration mit externen Caching-Systemen (Varnish, CDN) zum Löschen.
-   `prestaspeedcache/classes/PscFrontAssign.php`: Verwaltet Smarty-Variablenzuweisungen für Front-Office-Vorlagen.
-   `prestaspeedcache/classes/PscFrontDebug.php`: Logik zum Anzeigen von Debug-Informationen im Front Office.
-   `prestaspeedcache/classes/PscHealth.php`: Bietet Methoden zur Überprüfung des Zustands und Status des Caching-Systems.
-   `prestaspeedcache/classes/PscHtmlOptimizer.php`: Implementiert die HTML-Minifizierungslogik.
-   `prestaspeedcache/classes/PscHttpProbe.php`: Wird für interne HTTP-Anfragen verwendet, z. B. zum Cache-Aufwärmen.
-   `prestaspeedcache/classes/PscInstaller.php`: Behandelt Modulinstallations- und Deinstallationsroutinen (Datenbanktabellen, Hooks, Standardkonfigurationen).
-   `prestaspeedcache/classes/PscInvalidationQueue.php`: Verwaltet eine Warteschlange von Seiten, die invalidiert werden müssen, oft von Cron verarbeitet.
-   `prestaspeedcache/classes/PscLiveDebug.php`: Bietet Echtzeit-Debugging- und Überwachungsfunktionen.
-   `prestaspeedcache/classes/PscMetrics.php`: Sammelt und meldet Leistungsmetriken für das Dashboard.
-   `prestaspeedcache/classes/PscOps.php`: Allgemeine Betriebs-Dienstprogramm-Methoden.
-   `prestaspeedcache/classes/PscPresets.php`: Verwaltet vordefinierte Caching-Konfigurationen oder Voreinstellungen.
-   `prestaspeedcache/classes/PscRequestGuard.php`: Schützt vor bösartigen Anfragen oder gewährleistet eine ordnungsgemäße Anfragenbehandlung.
-   `prestaspeedcache/classes/PscTiming.php`: Dienstprogramm zur Messung von Ausführungszeiten.
-   `prestaspeedcache/classes/PscTranslate.php`: Verwaltet Modulübersetzungen.
-   `prestaspeedcache/classes/PscWarmup.php`: Implementiert die Cache-Aufwärmlogik.
-   `prestaspeedcache/classes/PscWizard.php`: Führt Benutzer durch die Ersteinrichtung.
-   `prestaspeedcache/classes/storage/PscFileStorage.php`: Konkrete Implementierung für dateibasierten Cache-Speicher.
-   `prestaspeedcache/classes/storage/PscMemcachedStorage.php`: Konkrete Implementierung für Memcached-Cache-Speicher.
-   `prestaspeedcache/classes/storage/PscRedisStorage.php`: Konkrete Implementierung für Redis-Cache-Speicher.
-   `prestaspeedcache/classes/storage/PscStorageFactory.php`: Factory-Muster zum Erstellen geeigneter Cache-Speicherinstanzen.
-   `prestaspeedcache/classes/storage/PscStorageInterface.php`: Schnittstelle, die Methoden für Cache-Speicherimplementierungen definiert.

#### Überschreibungen

Das Modul verwendet Überschreibungen, um sich tief in das Kernverhalten von PrestaShop zu integrieren.

-   `prestaspeedcache/override/classes/controller/Controller.php`: Überschreibt die Basisklasse `Controller`, wodurch das Modul den Rendering-Prozess sowohl für das Front- als auch für das Back Office abfangen kann, um möglicherweise Caching-Logik oder dynamische Blockmarker einzufügen.
-   `prestaspeedcache/override/classes/controller/FrontController.php`: Überschreibt `FrontController`, um speziell Front-Office-Seitenanfragen zu verarbeiten, wodurch das Modul gecachte Inhalte bereitstellen oder Seiten für das Caching vorbereiten kann.
-   `prestaspeedcache/override/classes/Dispatcher.php`: Überschreibt den `Dispatcher`, um zu steuern, wie URLs geroutet und verarbeitet werden, möglicherweise zu gecachtem Inhalt umleiten oder die Cache-Generierung auslösen.
-   `prestaspeedcache/override/classes/Hook.php`: Überschreibt die Klasse `Hook`, um dynamisches Modul-Rendering innerhalb gecachter Seiten zu ermöglichen, wodurch sichergestellt wird, dass spezifische Hooks immer frisch ausgeführt werden.

### 4.4 JavaScript-Assets (`views/js/`)

Diese Skripte verbessern die Benutzererfahrung sowohl im Front- als auch im Back Office.

-   `prestaspeedcache/views/js/admin.js`:
    *   **Geltungsbereich:** Back-Office.
    *   **Details:** Behandelt interaktive Elemente in der Admin-Konfiguration des Moduls, wie z. B. Registerkartenwechsel, Formularübermittlungen, AJAX-Aufrufe zum Leeren des Caches, Starten des Aufwärmens und dynamische Aktualisierungen des Dashboards oder der Cache-Liste.
-   `prestaspeedcache/views/js/after/lang-currency.js`:
    *   **Geltungsbereich:** Front-Office.
    *   **Details:** Wahrscheinlich ein kleines Skript, das nach dem Laden der Hauptseite ausgeführt wird und speziell darauf ausgelegt ist, sicherzustellen, dass Sprach- und Währungsauswahlen (die oft dynamisch sind) in einem gecachten Seitenkontext korrekt funktionieren. Es könnte ihr Verhalten neu initialisieren oder sicherstellen, dass ihr Zustand konsistent ist.
-   `prestaspeedcache/views/js/dynamic.js`:
    *   **Geltungsbereich:** Front-Office.
    *   **Details:** Dies ist ein kritisches Skript für dynamische Blöcke. Es identifiziert Platzhalter für dynamische Inhalte innerhalb einer gecachten Seite, stellt AJAX-Anfragen (an `api.php` oder `dynamic.php` Controller), um das frische HTML für diese Blöcke abzurufen, und fügt den Inhalt dann wieder in das DOM ein. Es stellt sicher, dass Elemente wie der Warenkorb, der Anmeldestatus usw. immer aktuell sind.
-   `prestaspeedcache/views/js/fo_debug.js`:
    *   **Geltungsbereich:** Front-Office (nur für Administratoren sichtbar, wenn der Debug-Modus aktiviert ist).
    *   **Details:** Zeigt die Cache-Debug-Überlagerung im Front Office an. Es ruft Cache-Statusinformationen (Hit/Miss, Zeitstempel usw.) ab und rendert sie in einem sichtbaren, nicht aufdringlichen Element für Administratoren.
-   `prestaspeedcache/views/js/psc-dom-mock.js`:
    *   **Geltungsbereich:** Front-Office.
    *   **Details:** Potenziell ein Dienstprogramm-Skript, das eine leichte DOM-Manipulation oder Mocking-Schicht bereitstellt, möglicherweise während des dynamischen Block-Injektionsprozesses verwendet, um Kompatibilität zu gewährleisten oder das Rendering zu optimieren.

### 4.5 CSS-Stylesheets (`views/css/`)

-   `prestaspeedcache/views/css/admin.css`:
    *   **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
    *   **Details:** Gestaltet die Konfigurationsseiten, das Dashboard und die Cache-Verwaltungsraster des Moduls. Es sorgt für eine konsistente und benutzerfreundliche Oberfläche im PrestaShop Back Office.
    *   **Wichtige CSS-Klassenselektoren:** `prestaspeedcache-dashboard`, `prestaspeedcache-config-form`, `prestaspeedcache-table`, `psc-debug-overlay`.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

#### Admin-Vorlagen (`views/templates/admin/`)

Diese Vorlagen werden für die Back-Office-Oberfläche des Moduls verwendet.

-   `prestaspeedcache/views/templates/admin/cache_list.tpl`: Rendert die Tabelle und die Oberfläche zum Auflisten und Verwalten gecachter Seiten.
-   `prestaspeedcache/views/templates/admin/configure.tpl`: Das Hauptkonfigurationsformular für das Modul, das alle in Abschnitt 4.1 beschriebenen Einstellungen enthält.
-   `prestaspeedcache/views/templates/admin/dashboard.tpl`: Zeigt die Leistungsmetriken, Diagramme und den Cache-Zustandsstatus an.
-   `prestaspeedcache/views/templates/admin/dynamic_modules.tpl`: Die Oberfläche zum Auswählen und Verwalten von Modulen, die dynamisch gerendert werden sollen.
-   `prestaspeedcache/views/templates/admin/live_debug.tpl`: Rendert das Echtzeit-Debug-Informationspanel im Back Office.
-   `prestaspeedcache/views/templates/admin/ops.tpl`: Enthält wahrscheinlich Vorlagen für Betriebs-Tools oder Aktionen (z. B. manuelles Cache-Leeren, Aufwärmen).
-   `prestaspeedcache/views/templates/admin/tabs.tpl`: Rendert die Registerkarten-Navigationsstruktur für die Konfigurationsseiten des Moduls.
-   `prestaspeedcache/views/templates/admin/wizard.tpl`: Vorlage für den Ersteinrichtungsassistenten, der Benutzer durch die grundlegende Konfiguration führt.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Das Modul verwendet hauptsächlich die `ps_configuration`-Tabelle von PrestaShop für seine Einstellungen. Für die Cache-Speicherung verwendet es entweder das Dateisystem oder externe Dienste (Redis/Memcached). Es kann benutzerdefinierte Tabellen erstellen für:

-   `ps_prestaspeedcache_cache_tags`: Speichert Beziehungen zwischen gecachten Seiten und ihren zugehörigen Tags (z. B. Produkt-IDs, Kategorie-IDs) für eine effiziente Invalidierung.
-   `ps_prestaspeedcache_invalidation_queue`: Speichert eine Liste von Seiten oder Tags, die invalidiert werden müssen, asynchron verarbeitet.
-   `ps_prestaspeedcache_metrics`: Speichert Leistungsmetriken für das Dashboard.

#### Registrierte Hooks-Tabelle

Das Modul registriert verschiedene Hooks, um sich in den Lebenszyklus von PrestaShop zu integrieren.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Bevor Seiteninhalte im Header gerendert werden. | Einfügen von Front-Office-JavaScript (z. B. `dynamic.js`, `fo_debug.js`), Einrichten des anfänglichen Cache-Kontexts. |
| `displayFooter` | Vor dem schließenden `</body>`-Tag. | Einfügen zusätzlicher Skripte, Debug-Informationen oder Abschließen von Cache-Operationen. |
| `displayLeftColumn` | In der linken Spalte des Themes. | Potenziell für dynamisches Modul-Rendering verwendet, wenn ein Modul in der linken Spalte als dynamisch markiert ist. |
| `displayRightColumn` | In der rechten Spalte des Themes. | Potenziell für dynamisches Modul-Rendering verwendet, wenn ein Modul in der rechten Spalte als dynamisch markiert ist. |
| `displayProductAdditionalInfo` | Auf der Produktseite, unterhalb der Produktbeschreibung. | Wenn ein hier eingehängtes Modul dynamisch ist, werden seine Inhalte separat abgerufen. |
| `actionFrontControllerSetMedia` | Nachdem Medien (JS/CSS) vom Front-Controller gesetzt wurden. | Hinzufügen modulspezifischer JS/CSS zur Seite. |
| `actionFrontControllerInit` | Zu Beginn der Ausführung eines Front-Controllers. | Abfangen von Anfragen, um nach gecachtem Inhalt zu suchen oder für das Caching vorzubereiten. |
| `actionDispatcherBefore` | Bevor der Dispatcher die Anfrage verarbeitet. | Frühes Abfangen, um gecachte Inhalte bereitzustellen oder das Dispatching zu umgehen. |
| `actionDispatcherAfter` | Nachdem der Dispatcher die Anfrage verarbeitet hat. | Abschließen der Cache-Generierung für die aktuelle Seite. |
| `actionObjectUpdate` | Wenn ein `ObjectModel` aktualisiert wird (z. B. Produkt, Kategorie, CMS). | Auslösen der Cache-Invalidierung für betroffene Seiten. |
| `actionObjectAdd` | Wenn ein `ObjectModel` hinzugefügt wird. | Auslösen der Cache-Invalidierung für potenziell betroffene Seiten. |
| `actionObjectDelete` | Wenn ein `ObjectModel` gelöscht wird. | Auslösen der Cache-Invalidierung für betroffene Seiten. |
| `actionProductUpdate` | Spezifisch für Produktaktualisierungen. | Granulare Cache-Invalidierung für Produktseiten. |
| `actionCategoryUpdate` | Spezifisch für Kategorieaktualisierungen. | Granulare Cache-Invalidierung für Kategorieseiten. |
| `actionCmsUpdate` | Spezifisch für CMS-Seitenaktualisierungen. | Granulare Cache-Invalidierung für CMS-Seiten. |
| `actionClearCache` | Wenn der native Cache von PrestaShop geleert wird. | Synchronisierung des Modul-Cache-Leerens mit PrestaShop. |
| `actionModuleInstall` | Wenn ein Modul installiert wird. | Potenzielles Leeren des Caches oder Aktualisieren der dynamischen Modulliste. |
| `actionModuleUninstall` | Wenn ein Modul deinstalliert wird. | Leeren des Caches oder Entfernen des Moduls aus der dynamischen Liste. |
| `actionAdminControllerSetMedia` | In Admin-Controllern, nachdem Medien gesetzt wurden. | Einfügen von adminspezifischem JS/CSS. |
| `actionAdminControllerPreProcess` | Bevor ein Admin-Controller seine Anfrage verarbeitet. | Einrichten des Admin-Kontexts für das Modul. |
| `actionAdminControllerPostProcess` | Nachdem ein Admin-Controller seine Anfrage verarbeitet hat. | Handhabung der Nachbearbeitung für Admin-Aktionen. |
| `actionOutputHTMLBefore` | Bevor die endgültige HTML-Ausgabe an den Browser gesendet wird. | Durchführung der HTML-Optimierung (Minifizierung). |
| `actionOutputHTMLAfter` | Nachdem die endgültige HTML-Ausgabe gesendet wurde. | Abschließen der Cache-Speicherung. |
| `actionAjaxDie` | Wenn eine AJAX-Anfrage `die()` aufruft. | Sicherstellen der ordnungsgemäßen Cache-Behandlung für AJAX-Antworten. |
| `actionGetContent` | Für die Hauptkonfigurationsseite des Moduls. | Rendern des Konfigurationsformulars des Moduls. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, umfassende Unterstützung zu bieten, um sicherzustellen, dass Ihr Presta Speed Cache-Modul optimal funktioniert.
