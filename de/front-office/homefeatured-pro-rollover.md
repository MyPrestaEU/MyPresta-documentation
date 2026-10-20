---
title: "HomeFeatured Pro Rollover - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul HomeFeatured Pro Rollover von MyPresta.eu."
sidebar:
  label: "HomeFeatured Pro Rollover"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul HomeFeatured Pro Rollover auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/homefeatured-pro-rollover.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/homefeatured-pro-rollover/)
>
> ---


# HomeFeatured Pro Rollover

## 1. Anforderungen & Kompatibilität
- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend und auf den meisten Webhosting-Umgebungen vorinstalliert.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)
Klicken Sie nach der Installation im Modul-Manager neben "HomeFeatured Pro Rollover" auf "Konfigurieren", um auf die Einstellungen zuzugreifen.

#### 2.1.1 Anzahl der anzuzeigenden Produkte
-   **Was diese Einstellung bewirkt:** Dies steuert, wie viele ausgewählte Produkte im Bereich "Ausgewählte Produkte" auf Ihrer Homepage angezeigt werden.
-   **Auswirkungen einer Änderung dieser Einstellung:**
    -   *Wenn auf eine bestimmte Zahl eingestellt (z.B. 8):* Ihre Homepage zeigt genau diese Anzahl von Produkten aus Ihrer Kategorie "Home" (oder der Kategorie, die Sie für ausgewählte Produkte festgelegt haben) an.
    -   *Wenn auf eine andere Zahl eingestellt:* Die Anzahl der angezeigten Produkte ändert sich entsprechend. Wenn Sie sie zu hoch einstellen, kann Ihre Homepage sehr lang werden; wenn zu niedrig, zeigen Sie möglicherweise nicht genügend Produkte an.
-   **Empfohlener Wert:** Eine Zahl, die gut zu Ihrem Homepage-Layout passt, typischerweise zwischen 8 und 12 für ein Standardraster.
-   **Händlerszenario / Beispiel:** Wenn Sie Ihre Top 8 Bestseller auf der Homepage hervorheben möchten, würden Sie dies auf "8" setzen. Wenn Sie ein breiteres Layout haben und mehr Vielfalt zeigen möchten, könnten Sie es auf "12" erhöhen.

#### 2.1.2 Attribute auf der Produktseite anzeigen
-   **Was diese Einstellung bewirkt:** Dies ist eine Standard-PrestaShop-Einstellung, die steuert, ob Produktattribute (wie Größe, Farbe) auf der Produktseite selbst angezeigt werden. Obwohl dieses Modul hauptsächlich die Homepage betrifft, ist diese Einstellung oft in Modulen enthalten, die mit Produktanzeigen interagieren.
-   **Auswirkungen einer Änderung dieser Einstellung:**
    -   *Wenn aktiviert (Ja):* Produktattribute sind auf einzelnen Produktseiten sichtbar und wählbar.
    -   *Wenn deaktiviert (Nein):* Produktattribute werden auf Produktseiten nicht angezeigt, was die Seite möglicherweise vereinfacht, aber wichtige Auswahlmöglichkeiten für Kunden entfernt.
-   **Empfohlener Wert:** **Ja**. Die meisten Shops müssen Attribute für Produkte mit Variationen anzeigen.
-   **Händlerszenario / Beispiel:** Für einen Bekleidungsgeschäft müssen Kunden Größe und Farbe auswählen. Die Aktivierung dieser Option stellt sicher, dass diese Optionen auf der Produktseite erscheinen. Eine Deaktivierung würde es Kunden unmöglich machen, Variationen zu wählen.

#### 2.1.3 Standardsprache
-   **Was diese Einstellung bewirkt:** Diese Einstellung gibt die Standardsprache für Ihren Shop an. Es ist eine zentrale PrestaShop-Einstellung, die oft von Modulen referenziert wird, um eine korrekte Sprachbehandlung zu gewährleisten.
-   **Auswirkungen einer Änderung dieser Einstellung:**
    -   *Wenn auf Ihre primäre Sprache eingestellt (z.B. Deutsch):* Das Modul verwendet diese Sprache für alle sprachabhängigen Daten oder Fallbacks, falls Übersetzungen fehlen.
-   **Empfohlener Wert:** **Die primäre Sprache Ihres Shops.** Dies sollte mit der Standardsprache übereinstimmen, die Sie in den PrestaShop-Lokalisierungseinstellungen festgelegt haben.
-   **Händlerszenario / Beispiel:** Wenn die Hauptzielgruppe Ihres Shops in Deutschland ist, würden Sie dies auf "Deutsch" setzen, um sicherzustellen, dass alle Standardtexte und Produktinformationen korrekt auf Deutsch angezeigt werden.

#### 2.1.4 Anzahl der anzuzeigenden Produkte (Duplikat von 4.1.1)
-   **Was diese Einstellung bewirkt:** Dies ist ein Duplikat der Einstellung "Anzahl der anzuzeigenden Produkte" (`HOME_FEATURED_PRO_NBR`). Es steuert denselben Aspekt: wie viele ausgewählte Produkte auf Ihrer Homepage erscheinen.
-   **Auswirkungen einer Änderung dieser Einstellung:** Eine Änderung dieser Einstellung wirkt sich direkt auf die Anzahl der im vorgestellten Bereich angezeigten Produkte aus.
-   **Empfohlener Wert:** Siehe Abschnitt 4.1.1.
-   **Händlerszenario / Beispiel:** Siehe Abschnitt 4.1.1.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| Modulkonfiguration | Anzahl der anzuzeigenden Produkte (`HOME_FEATURED_PRO_NBR`) | 8-12 (abhängig vom Layout) | Legt die Anzahl der ausgewählten Produkte auf der Homepage fest. |
| Modulkonfiguration | Attribute auf der Produktseite anzeigen (`PS_ATTRIBUTE_CATEGORY_DISPLAY`) | Ja | Steuert die Sichtbarkeit von Produktattributen auf Produktseiten. |
| Modulkonfiguration | Standardsprache (`PS_LANG_DEFAULT`) | Primäre Sprache Ihres Shops | Gibt die Standardsprache für den Shop an. |
| Modulkonfiguration | Anzahl der anzuzeigenden Produkte (`HOME_FEATURED_NBR`) | Gleich wie `HOME_FEATURED_PRO_NBR` | Duplizierte Einstellung für die Anzahl der ausgewählten Produkte. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Der Rollover-Effekt funktioniert auf meiner Homepage nicht.**
A:
1.  **Modulstatus prüfen:** Stellen Sie sicher, dass das Modul "HomeFeatured Pro Rollover" unter **Module > Modul-Manager** installiert und aktiviert ist.
2.  **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf "Cache leeren" (oder "Smarty-Cache leeren" in älteren Versionen). Manchmal verhindern alte Cache-Dateien, dass neue Moduländerungen angezeigt werden.
3.  **Produktbilder:** Überprüfen Sie, ob die ausgewählten Produkte tatsächlich *mindestens zwei* Bilder in ihren Produkteinstellungen (**Katalog > Produkte > [Produkt bearbeiten] > Bilder-Tab**) hochgeladen haben. Das Modul benötigt ein zweites Bild, um es beim Hover anzuzeigen.
4.  **Theme-Kompatibilität:** Obwohl das Modul für eine breite Kompatibilität ausgelegt ist, erfordern stark angepasste Themes möglicherweise geringfügige CSS-Anpassungen. Wenn das Problem weiterhin besteht, wenden Sie sich an den MyPresta.eu-Support.

**F: Meine Homepage sieht nach der Installation kaputt aus.**
A:
1.  **Sofortmaßnahme:** Wenn Ihr Shop unbrauchbar wird, deaktivieren Sie das Modul sofort unter **Module > Modul-Manager**.
2.  **PrestaShop-Version prüfen:** Stellen Sie sicher, dass Sie die richtige Modulversion für Ihre PrestaShop-Installation heruntergeladen haben (z.B. PS 8.x-Version für PrestaShop 8.x).
3.  **Theme-Konflikte:** Einige Themes haben möglicherweise eine eigene "Featured Products"-Logik, die Konflikte verursacht. Versuchen Sie, vorübergehend zum Standard-PrestaShop-Theme (Classic) zu wechseln, um zu sehen, ob das Problem behoben wird. Wenn ja, ist das Problem theme-bezogen.
4.  **Support kontaktieren:** Geben Sie dem MyPresta.eu-Support Details zu Ihrer PrestaShop-Version, Ihrem Theme und eventuellen Fehlermeldungen, die Sie sehen.

**F: Wie ändere ich, welche Produkte "ausgewählt" sind?**
A: Das Modul verwendet den Standard-PrestaShop-Mechanismus für "Ausgewählte Produkte". Um zu ändern, welche Produkte angezeigt werden:
1.  Gehen Sie zu **Katalog > Kategorien**.
2.  Suchen Sie die Kategorie namens "Home" (oder die Kategorie, die Sie als Ihre Homepage-Kategorie festgelegt haben).
3.  Bearbeiten Sie diese Kategorie und gehen Sie zum Tab "Produkte".
4.  Sie können Produkte zu dieser Kategorie hinzufügen oder daraus entfernen, um zu steuern, was in Ihrem ausgewählten Bereich erscheint.

**F: Die Bilder sind während des Rollovers nicht perfekt ausgerichtet oder skaliert.**
A: Dies deutet normalerweise auf einen CSS-Konflikt mit Ihrem Theme hin.
1.  **Bildabmessungen:** Stellen Sie sicher, dass alle Produktbilder (insbesondere die ersten und zweiten) mit konsistenten Seitenverhältnissen und ähnlichen Abmessungen hochgeladen werden. PrestaShop passt sie automatisch an, aber große Unterschiede können zu Layoutverschiebungen führen.
2.  **Theme-Anpassung:** Das CSS Ihres Themes könnte das Styling des Moduls überschreiben. Ein Webmaster kann das Element mit den Browser-Entwicklertools überprüfen, um widersprüchliche CSS-Regeln zu identifizieren und eine Korrektur in der benutzerdefinierten CSS-Datei Ihres Themes anzuwenden.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht
Das Modul HomeFeatured Pro Rollover (`homefeaturedpro`) ist ein unkompliziertes PrestaShop-Modul, das entwickelt wurde, um die Funktionalität des Standardmoduls `homefeatured` zu überschreiben und zu erweitern. Es konzentriert sich hauptsächlich auf die Front-Office-Anzeige, insbesondere auf das Einfügen von JavaScript und CSS, um den Bild-Rollover-Effekt auf den ausgewählten Produkten der Homepage zu ermöglichen. Es nutzt das PrestaShop-Hook-System, um seine Logik und Templates zu integrieren. Das Modul führt keine neuen Datenbanktabellen oder komplexen ObjectModels ein, sondern greift auf vorhandene PrestaShop-Produktdaten zurück.

### 4.2 Controller (`controllers/`)
Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller ein. Die gesamte Konfiguration wird über die `getContent()`-Methode der Hauptmoduldatei abgewickelt.

### 4.3 Kernklassen & Modelle (`classes/`)
Dieses Modul führt keine benutzerdefinierten Klassen oder ObjectModels ein. Es arbeitet, indem es bestehende PrestaShop-Funktionalität erweitert und eigene Templates rendert.

### 4.4 JavaScript-Assets (`views/js/`)
Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien. Der Rollover-Effekt wird rein durch CSS erreicht.

### 4.5 CSS-Stylesheets (`views/css/`)
-   **`homefeaturedpro/homefeatured.css`**
    *   **Geltungsbereich:** Front-Office-Kunden-Styling.
    *   **Wichtige UI-Komponenten und Container, die es stylt:** Dieses Stylesheet enthält die Kern-CSS-Regeln, die für den Bild-Rollover-Effekt verantwortlich sind. Es zielt auf Produktbild-Container innerhalb des Bereichs der ausgewählten Produkte ab, wahrscheinlich unter Verwendung von Selektoren wie `.product-container .product-image`, `.product-image-container` oder ähnlichen, um das zweite Bild standardmäßig auszublenden und es beim Hover anzuzeigen.
    *   **Wichtige CSS-Klassenselektoren, die Entwickler in ihrem Theme überschreiben können:**
        *   `.product-image-container .img-hover`: Steuert wahrscheinlich die Sichtbarkeit und Positionierung des zweiten Bildes.
        *   `.product-image-container .img-primary`: Steuert das primäre Bild.
        *   Stile im Zusammenhang mit `transition`-Eigenschaften für sanfte Bildwechsel.
        *   `overflow: hidden` auf dem Bildcontainer zur Verwaltung des Bildwechsels.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

-   **`homefeaturedpro/homefeatured.tpl`**
    *   **Geltungsbereich:** Front-Office.
    *   **Hook:** Wird hauptsächlich in `displayHome` oder `Home` gerendert (abhängig von PrestaShop-Version und Theme-Konfiguration).
    *   **Zweck:** Dies ist das Haupttemplate, das für das Rendern des Rasters der ausgewählten Produkte auf der Homepage verantwortlich ist. Es iteriert über die Variable `$products` (die von der `hookDisplayHome`-Methode des Moduls übergeben wird) und generiert für jedes Produkt die HTML-Struktur, einschließlich der primären und sekundären Bilder, des Produktnamens, des Preises und anderer Details. Es ist für PrestaShop 1.7.x und neuere Versionen konzipiert. Die Logik innerhalb dieses Templates ist entscheidend für die Anzeige beider Bilder und die Anwendung der notwendigen CSS-Klassen für den Rollover-Effekt.

-   **`homefeaturedpro/homefeatured14.tpl`**
    *   **Geltungsbereich:** Front-Office.
    *   **Hook:** Wahrscheinlich für ältere PrestaShop-Versionen (z.B. 1.4.x, 1.5.x, 1.6.x) gedacht, falls das Modul diese unterstützt, oder als Alternative für spezifische Theme-Strukturen.
    *   **Zweck:** Dieses Template dient dem gleichen Zweck wie `homefeatured.tpl`, ist aber so strukturiert, dass es mit älteren PrestaShop-Template-Syntaxen und HTML-Strukturen kompatibel ist. Es würde auch über Produkte iterieren und die notwendigen Bildelemente für den Rollover-Effekt rendern. Für moderne PrestaShop-Versionen (1.7+) ist `homefeatured.tpl` das primäre verwendete Template.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:
    *   Das Modul erstellt keine benutzerdefinierten Datenbanktabellen.
    *   Es speichert seine Konfigurationseinstellungen in der Tabelle `ps_configuration` unter Verwendung der folgenden Schlüssel:
        *   `HOME_FEATURED_PRO_NBR`: Speichert die Anzahl der anzuzeigenden ausgewählten Produkte.
        *   `PS_ATTRIBUTE_CATEGORY_DISPLAY`: (Standard-PrestaShop-Konfiguration, möglicherweise vom Modul referenziert oder gesetzt).
        *   `PS_LANG_DEFAULT`: (Standard-PrestaShop-Konfiguration, möglicherweise vom Modul referenziert oder gesetzt).
        *   `HOME_FEATURED_NBR`: (Duplikat von `HOME_FEATURED_PRO_NBR`, wahrscheinlich für Abwärtskompatibilität oder interne Konsistenz).

-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
|---|---|---|
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Wird verwendet, um das CSS-Stylesheet des Moduls (`homefeatured.css`) einzubinden, um sicherzustellen, dass die Rollover-Stile vor dem Seiteninhalt geladen werden. |
| `header` | Alias für `displayHeader`. | Gleich wie `displayHeader`. |
| `Home` | Auf der Homepage, typischerweise im Hauptinhaltsbereich. | Rendert das Template der ausgewählten Produkte des Moduls (`homefeatured.tpl` oder `homefeatured14.tpl`) und übergibt die Produktdaten daran. |
| `displayHome` | Alias für `Home` in modernen PrestaShop-Versionen. | Gleich wie `Home`. |

## 5. Offizieller Support & Updates
Für offizielle Updates, technischen Support und weitere Unterstützung zum Modul HomeFeatured Pro Rollover besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen gerne zur Verfügung.
