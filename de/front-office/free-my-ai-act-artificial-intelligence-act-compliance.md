---
title: "Free My AI Act - Artificial Intelligence Act Compliance - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Free My AI Act - Artificial Intelligence Act compliance“ von MyPresta.eu."
sidebar:
  label: "Free My AI Act - Artificial Intelligence Act compliance"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Free My AI Act - Artificial Intelligence Act compliance auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/free-my-ai-act-artificial-intelligence-act-compliance.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/free-my-ai-act-artificial-intelligence-act-compliance/)
>
> ---


# Free My AI Act - Artificial Intelligence Act compliance

## 1. Anforderungen & Kompatibilität
- **Unterstützte PrestaShop-Versionen**: PrestaShop 9.x
- **PHP-Kompatibilität**: PHP 7.4 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für eine PrestaShop-Installation erforderlich und ausreichend für dieses Modul.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)
Um auf die Konfiguration des Moduls zuzugreifen, navigieren Sie zu **Module > Modul-Manager**, suchen Sie nach „Free My AI Act“ und klicken Sie auf die Schaltfläche „Konfigurieren“.

Dieser Bildschirm bietet alle wesentlichen Einstellungen, um zu steuern, wie KI-Inhalte in Ihrem Shop offengelegt werden.

#### **Allgemeine Einstellungen**

-   **KI-Gesetz-Compliance aktivieren:**
    -   **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter, um die Funktionen des Moduls in Ihrem gesamten Shop zu aktivieren oder zu deaktivieren.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Alle konfigurierten KI-Offenlegungsfunktionen (Badges, Banner, Hinweise) werden in Ihrem Front Office aktiv.
        -   *Wenn deaktiviert:* Alle KI-Offenlegungsfunktionen werden ausgeblendet, und das Modul zeigt den Kunden keine KI-bezogenen Informationen an.
    -   **Empfohlener Wert:** JA
    -   **Händlerszenario / Beispiel:** Sie haben Ihre Einrichtung abgeschlossen und sind bereit, die KI-Gesetz-Compliance live zu schalten. Aktivieren Sie diese Einstellung. Wenn Sie alle Offenlegungen vorübergehend für Wartungsarbeiten deaktivieren müssen, stellen Sie sie auf NEIN.

#### **Optionen zur Offenlegung von KI-Inhalten**

-   **KI-Badge auf Produktbildern anzeigen:**
    -   **Was diese Einstellung bewirkt:** Steuert, ob ein kleines Badge (z. B. „KI-generiert“ oder ein Symbol) direkt auf Produktbildern in Kategorielisten und auf der Produktseite erscheint.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Ein visueller Indikator wird auf Produktbildern eingeblendet, die Sie als KI-generiert markiert haben.
        -   *Wenn deaktiviert:* Es erscheint kein Badge auf Produktbildern, selbst wenn diese als KI-generiert markiert sind.
    -   **Empfohlener Wert:** JA
    -   **Händlerszenario / Beispiel:** Sie verwenden KI, um viele Ihrer Produktfotos zu generieren oder zu verbessern. Die Aktivierung dieser Option bietet Kunden beim Stöbern eine sofortige visuelle Offenlegung.

-   **Zusätzlichen Info-Hinweis auf Produktseite anzeigen:**
    -   **Was diese Einstellung bewirkt:** Legt fest, ob ein spezieller Texthinweis auf einzelnen Produktseiten angezeigt wird, um Kunden über KI-generierte Inhalte (Text oder Bilder) für dieses spezifische Produkt zu informieren.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Ein anpassbarer Textblock erscheint auf Produktseiten, typischerweise unter der Beschreibung oder in einem neuen Tab, der die Verwendung von KI für den Inhalt dieses Produkts detailliert beschreibt.
        -   *Wenn deaktiviert:* Es wird kein spezifischer KI-Offenlegungshinweis auf Produktseiten angezeigt.
    -   **Empfohlener Wert:** JA
    -   **Händlerszenario / Beispiel:** Sie möchten eine detailliertere Erklärung zu den KI-Inhalten für jedes Produkt geben. Dieser Hinweis ermöglicht es Ihnen, über ein einfaches Badge hinauszugehen.

-   **Shop-weiten KI-Richtlinien-Banner anzeigen:**
    -   **Was diese Einstellung bewirkt:** Aktiviert einen Banner, der konsistent über Ihren gesamten Shop (z. B. oben oder unten auf jeder Seite) erscheint, um Besucher über Ihre allgemeinen Richtlinien für KI-Inhalte zu informieren.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Ein anpassbarer Banner wird auf allen Seiten sichtbar sein, oft mit einem Link zu einer umfassenderen KI-Richtlinienseite.
        -   *Wenn deaktiviert:* Es wird kein shop-weiter Banner angezeigt.
    -   **Empfohlener Wert:** JA
    -   **Händlerszenario / Beispiel:** Sie möchten eine allgemeine Aussage über die Nutzung von KI in Ihrem Shop machen und Kunden für volle Transparenz auf eine spezielle Richtlinienseite verweisen.

-   **Link zur KI-Richtlinienseite (URL):**
    -   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, die URL einer CMS-Seite oder eines externen Links anzugeben, wo Kunden Ihre detaillierten KI-Inhaltsrichtlinien finden können. Dieser Link wird typischerweise im shop-weiten Banner oder in zusätzlichen Info-Hinweisen enthalten sein.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn eine URL eingegeben wird:* Der Banner und die Hinweise enthalten einen anklickbaren Link zu dieser Seite.
        -   *Wenn leer gelassen:* Es wird kein Link bereitgestellt, oder der Banner/Hinweis wird möglicherweise nicht angezeigt, wenn er von diesem Link abhängt.
    -   **Empfohlener Wert:** `[Ihre CMS-Seiten-URL, z. B. /content/10-ai-policy]`
    -   **Händlerszenario / Beispiel:** Sie haben eine spezielle CMS-Seite erstellt, die Ihre KI-Nutzung, Datenpraktiken und Ihr Engagement für Transparenz erklärt. Geben Sie hier die URL ein, damit Kunden leicht darauf zugreifen können.

#### **Inhaltsanpassung**

-   **KI-Badge-Text (z. B. „KI“):**
    -   **Was diese Einstellung bewirkt:** Definiert den kurzen Text, der auf dem KI-Badge erscheint, das auf Produktbildern eingeblendet wird.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Bei Änderung:* Der Text auf dem Badge wird entsprechend aktualisiert.
    -   **Empfohlener Wert:** KI
    -   **Händlerszenario / Beispiel:** Sie bevorzugen eine kürzere Bezeichnung wie „KI“ anstelle von „KI-generiert“, um das Badge prägnant zu halten.

-   **KI-Badge-Farbe:**
    -   **Was diese Einstellung bewirkt:** Legt die Hintergrundfarbe des KI-Badges fest.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Bei Änderung:* Die Hintergrundfarbe des Badges wird aktualisiert, sodass Sie sie an das Branding Ihres Shops anpassen können.
    -   **Empfohlener Wert:** #FF0000 (Rot) oder eine Farbe, die gut mit Ihren Produktbildern kontrastiert.
    -   **Händlerszenario / Beispiel:** Ihre Marke verwendet eine bestimmte Farbpalette. Sie können die Badge-Farbe auf einen kontrastierenden Farbton einstellen, der dennoch visuell ansprechend ist.

-   **KI-Badge-Textfarbe:**
    -   **Was diese Einstellung bewirkt:** Legt die Farbe des Textes innerhalb des KI-Badges fest.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Bei Änderung:* Die Textfarbe auf dem Badge wird aktualisiert.
    -   **Empfohlener Wert:** #FFFFFF (Weiß) oder eine Farbe, die gut mit dem gewählten Badge-Hintergrund kontrastiert.
    -   **Händlerszenario / Beispiel:** Wenn Ihr Badge-Hintergrund dunkel ist, möchten Sie weißen oder hellen Text für die Lesbarkeit.

-   **Zusätzlicher Info-Hinweis-Text:**
    -   **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, den vollständigen Text anzupassen, der im „Zusätzlichen Info-Hinweis“ auf Produktseiten angezeigt wird.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Bei Änderung:* Der Inhalt des Hinweises auf Produktseiten wird Ihren benutzerdefinierten Text widerspiegeln.
    -   **Empfohlener Wert:** „Bitte beachten Sie: Teile dieser Produktbeschreibung und/oder Bilder wurden möglicherweise mithilfe von Künstlicher Intelligenz generiert oder verbessert, um Ihnen umfassende Informationen zu bieten.“
    -   **Händlerszenario / Beispiel:** Sie möchten klar angeben, dass sowohl Text als auch Bilder KI-generiert sein könnten und erklären, warum (z. B. für umfassende Informationen).

-   **Shop-weiter Banner-Text:**
    -   **Was diese Einstellung bewirkt:** Passt die Nachricht an, die im shop-weiten KI-Richtlinien-Banner angezeigt wird.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Bei Änderung:* Der Text im Banner auf allen Seiten wird aktualisiert.
    -   **Empfohlener Wert:** „Unser Shop verwendet KI zur Verbesserung von Inhalten. Erfahren Sie mehr über unsere KI-Richtlinien.“
    -   **Händlerszenario / Beispiel:** Sie möchten eine prägnante Nachricht im Banner, die Kunden dazu ermutigt, auf den Link für weitere Details zu klicken.

#### **Produktspezifische KI-Kennzeichnung**

Dieses Modul integriert sich auch direkt in Ihre Produktbearbeitungsseite. Wenn Sie ein Produkt im Back Office bearbeiten (**Katalog > Produkte > Produkt bearbeiten**), finden Sie einen neuen Tab oder Abschnitt zum Thema „KI-Gesetz-Compliance“.

-   **Produktinhalt als KI-generiert markieren:**
    -   **Was diese Einstellung bewirkt:** Ein Kontrollkästchen oder Schalter auf der Produktbearbeitungsseite, mit dem Sie den Textinhalt eines bestimmten Produkts (Beschreibung, Kurzbeschreibung, Merkmale) individuell als KI-generiert markieren können.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn für ein Produkt aktiviert:* Der „Zusätzliche Info-Hinweis“ (sofern in der Modulkonfiguration aktiviert) erscheint auf der Seite dieses Produkts, und alle anderen textbasierten KI-Offenlegungen werden aktiviert.
        -   *Wenn für ein Produkt deaktiviert:* Für dieses spezifische Produkt werden keine textbasierten KI-Offenlegungen angezeigt.
    -   **Empfohlener Wert:** Aktivieren Sie dies für jedes Produkt, bei dem KI für Text verwendet wurde.
    -   **Händlerszenario / Beispiel:** Sie haben einen KI-Schreibassistenten verwendet, um die lange Beschreibung für ein neues Produkt zu erstellen. Sie würden diese Einstellung für dieses spezifische Produkt aktivieren.

-   **Produktbilder als KI-generiert markieren:**
    -   **Was diese Einstellung bewirkt:** Ein Kontrollkästchen oder Schalter auf der Produktbearbeitungsseite, mit dem Sie die Bilder eines bestimmten Produkts individuell als KI-generiert oder KI-verbessert markieren können.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn für ein Produkt aktiviert:* Das „KI-Badge“ (sofern in der Modulkonfiguration aktiviert) erscheint auf den Bildern dieses Produkts, und der „Zusätzliche Info-Hinweis“ wird ebenfalls aktiviert.
        -   *Wenn für ein Produkt deaktiviert:* Für dieses spezifische Produkt erscheint kein KI-Badge auf den Bildern.
    -   **Empfohlener Wert:** Aktivieren Sie dies für jedes Produkt, bei dem KI für Bilder verwendet wurde.
    -   **Händlerszenario / Beispiel:** Sie haben einen KI-Bildgenerator oder -Verbesserer für das Hauptproduktbild verwendet. Sie würden diese Einstellung für dieses spezifische Produkt aktivieren.

#### 2.1.1 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| Modulkonfiguration | KI-Gesetz-Compliance aktivieren | JA | Hauptschalter für alle Modulfunktionen. |
| Modulkonfiguration | KI-Badge auf Produktbildern anzeigen | JA | Zeigt „KI“-Badge auf als KI-gekennzeichneten Produktbildern an. |
| Modulkonfiguration | Zusätzlichen Info-Hinweis auf Produktseite anzeigen | JA | Zeigt einen Texthinweis auf als KI-gekennzeichneten Produktseiten an. |
| Modulkonfiguration | Shop-weiten KI-Richtlinien-Banner anzeigen | JA | Zeigt einen Banner auf allen Seiten für die allgemeine Richtlinie an. |
| Modulkonfiguration | Link zur KI-Richtlinienseite (URL) | `/content/10-ai-policy` | URL für Ihre detaillierte KI-Richtlinienseite. |
| Modulkonfiguration | KI-Badge-Text | KI | Text, der auf dem Produktbild-Badge angezeigt wird. |
| Modulkonfiguration | KI-Badge-Farbe | `#FF0000` (Rot) | Hintergrundfarbe des KI-Badges. |
| Modulkonfiguration | KI-Badge-Textfarbe | `#FFFFFF` (Weiß) | Textfarbe des KI-Badges. |
| Modulkonfiguration | Zusätzlicher Info-Hinweis-Text | Anpassbar | Vollständiger Text für den Hinweis auf der Produktseite. |
| Modulkonfiguration | Shop-weiter Banner-Text | Anpassbar | Vollständiger Text für den shop-weiten Banner. |
| Produktbearbeitungsseite | Produktinhalt als KI-generiert markieren | N/A (pro Produkt) | Kennzeichnet Produkttextinhalte als KI-generiert. |
| Produktbearbeitungsseite | Produktbilder als KI-generiert markieren | N/A (pro Produkt) | Kennzeichnet Produktbilder als KI-generiert. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe das Modul aktiviert und die Einstellungen konfiguriert, sehe aber keine KI-Badges oder Banner in meinem Shop.**
**A1:**
1.  **„KI-Gesetz-Compliance aktivieren“ prüfen:** Stellen Sie sicher, dass der Hauptschalter in der Modulkonfiguration auf JA steht.
2.  **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Ihr Browser-Cache muss möglicherweise ebenfalls geleert werden (Strg+F5 oder Cmd+R).
3.  **Individuelle Produkteinstellungen prüfen:** Für Badges und Produktseitenhinweise stellen Sie sicher, dass Sie die spezifischen Produkte auf ihren jeweiligen Produktbearbeitungsseiten individuell als KI-generierte Inhalte/Bilder markiert haben.
4.  **Theme-Kompatibilität:** Obwohl das Modul für PrestaShop 9.x entwickelt wurde, können benutzerdefinierte Themes manchmal stören. Wenn Probleme weiterhin bestehen, wechseln Sie vorübergehend zum Standard-PrestaShop-Theme, um einen Theme-Konflikt auszuschließen.

**F2: Das KI-Badge oder der Banner sieht auf meinem benutzerdefinierten Theme seltsam aus oder ist falsch platziert.**
**A2:** Dies ist oft ein CSS-Konflikt mit Ihrem Theme.
1.  **Element untersuchen:** Verwenden Sie die Entwicklertools Ihres Browsers (F12), um das KI-Badge/Banner zu untersuchen. Suchen Sie nach widersprüchlichen CSS-Regeln.
2.  **Benutzerdefiniertes CSS:** Möglicherweise müssen Sie benutzerdefiniertes CSS in das Stylesheet Ihres Themes (oder über ein benutzerdefiniertes CSS-Modul) einfügen, um die Positionierung oder das Styling anzupassen. Die CSS-Klassen des Moduls sind normalerweise gut definiert (z. B. `.myaiactfree-badge`, `.myaiactfree-banner`).
3.  **Support kontaktieren:** Wenn Sie mit CSS nicht vertraut sind, wenden Sie sich an den MyPresta.eu-Support oder Ihren Webentwickler.

**F3: Wie übersetze ich den KI-Badge-Text, Banner-Text oder den zusätzlichen Info-Hinweis in andere Sprachen?**
**A3:**
1.  Gehen Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**.
2.  Wählen Sie „Übersetzungen installierter Module“ für den „Übersetzungstyp“.
3.  Wählen Sie Ihr Theme und die Sprache, in die Sie übersetzen möchten.
4.  Suchen Sie das Modul „Free My AI Act“ in der Liste. Sie können die von Ihnen konfigurierten Textfelder (KI-Badge-Text, Zusätzlicher Info-Hinweis-Text, Shop-weiter Banner-Text) direkt dort übersetzen.
5.  Speichern Sie Ihre Änderungen.

**F4: Was ist der Unterschied zwischen diesem „kostenlosen“ Modul und „My AI Act Pro“?**
**A4:** Das Modul „Free My AI Act“ bietet wesentliche Offenlegungsfunktionen für die grundlegende Compliance. „My AI Act Pro“ (ein separates, kostenpflichtiges Modul) bietet erweiterte Funktionen wie KI-Studio-Integration, API-Zugriff für automatische Kennzeichnung, Audit-Trails und erweiterte Wasserzeichenfunktionen für Bilder. Die kostenlose Version ist ein großartiger Ausgangspunkt, und Sie können auf Pro upgraden, wenn Ihre Anforderungen komplexer werden.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen technischen Überblick für Entwickler und Webmaster, die das Modul „Free My AI Act“ verstehen, erweitern oder Fehler beheben möchten.

### 4.1 Architekturübersicht
Das Modul `myaiactfree` folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich Hooks für die Front-Office-Anzeige und `getContent()` für die Back-Office-Konfiguration nutzt. Es integriert sich direkt in die Produktbearbeitungsoberfläche, indem es sich in `displayAdminProductsExtra` einklinkt, um produktspezifische KI-Kennzeichnungsoptionen bereitzustellen. Die Konfiguration wird in `ps_configuration` gespeichert, und die Front-Office-Darstellung wird durch Smarty-Templates und eine dedizierte JavaScript-Datei für dynamische Interaktionen erreicht.

### 4.2 Controller (`controllers/`)
Dieses Modul enthält keine dedizierten Front-Office- oder Back-Office-Controller. Die gesamte Front-Office-Logik wird über Hooks innerhalb der Hauptmoduldatei abgewickelt, und die Back-Office-Konfiguration wird von der Methode `getContent()` verwaltet.

### 4.3 Kernklassen & Modelle (`classes/`)
Dieses Modul definiert keine benutzerdefinierten Klassen oder `ObjectModel`-Instanzen. Alle Daten werden direkt über `Configuration` für globale Einstellungen und `Product`-Eigenschaften für produktspezifische Flags verwaltet.

### 4.4 JavaScript-Assets (`views/js/`)

-   **`myaiactfree/views/js/front.js`**
    *   **Geltungsbereich:** Front-Office.
    *   **Verantwortlichkeit:** Dieses Skript ist wahrscheinlich für jedes dynamische Front-Office-Verhalten im Zusammenhang mit den KI-Offenlegungselementen verantwortlich. Dies könnte umfassen:
        *   Initialisierung der KI-Badge-Anzeige auf Produktbildern, nachdem das DOM bereit ist.
        *   Behandlung von Klickereignissen auf dem KI-Richtlinien-Banner (wenn es ausblendbar ist oder interaktive Elemente hat).
        *   Sicherstellung der korrekten Positionierung und Responsivität des KI-Badges oder Banners, insbesondere wenn Bilder dynamisch geladen oder in der Größe geändert werden.
        *   Potenzielles Hinzufügen von Tooltips oder Popovers beim Überfahren von KI-Badges.
        *   Bindung an `prestashop.on`-Ereignisse für dynamische Inhaltsaktualisierungen (z. B. `updateProduct` auf der Produktseite).

### 4.5 CSS-Stylesheets (`views/css/`)

-   **`myaiactfree/views/css/admin.css`**
    *   **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
    *   **Verantwortlichkeit:** Bietet Styling für die Konfigurationsseite des Moduls (`configure.tpl`) und möglicherweise den benutzerdefinierten Tab/Abschnitt, der der Produktbearbeitungsseite (`product_tab.tpl`) hinzugefügt wird. Dies gewährleistet ein konsistentes und benutzerfreundliches Erscheinungsbild innerhalb des PrestaShop Back Office.
    *   **Wichtige CSS-Klassenselektoren:** Zielt wahrscheinlich auf Elemente innerhalb des Konfigurationsformulars des Moduls ab, wie z. B. spezifische Eingabefelder, Beschriftungen oder Informationsblöcke.

-   **`myaiactfree/views/css/front.css`**
    *   **Geltungsbereich:** Front-Office-Kunden-Styling.
    *   **Verantwortlichkeit:** Definiert das visuelle Erscheinungsbild aller KI-Offenlegungselemente, die für Kunden sichtbar sind. Dies umfasst:
        *   Styling für das KI-Badge (z. B. `.myaiactfree-badge`, `.myaiactfree-badge-text`, `.myaiactfree-badge-icon`), einschließlich seiner Position, Hintergrundfarbe, Textfarbe, Polsterung und Rahmenradius.
        *   Styling für den zusätzlichen Info-Hinweis auf Produktseiten (z. B. `.myaiactfree-additional-info`).
        *   Styling für den shop-weiten KI-Richtlinien-Banner (z. B. `.myaiactfree-banner`, `.myaiactfree-banner-text`, `.myaiactfree-banner-link`).
    *   **Wichtige CSS-Klassenselektoren:** Entwickler können diese Klassen im benutzerdefinierten CSS ihres Themes überschreiben, um sie an das Design ihrer Marke anzupassen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

-   **Hook-Templates (`views/templates/hook/`)**:
    *   **`myaiactfree/views/templates/hook/additional_info.tpl`**:
        *   **Hook:** Wahrscheinlich in `displayProductExtraContent` oder ähnlichen Produktseiten-Hooks gerendert.
        *   **Ausgabe:** Zeigt den anpassbaren Text des „Zusätzlichen Info-Hinweises“ auf der Produktseite an, wenn ein Produkt als KI-generiert gekennzeichnet ist.
    *   **`myaiactfree/views/templates/hook/ai_badge.tpl`**:
        *   **Hook:** Wahrscheinlich in `displayProductListReviews` (für Produktlisten) oder `displayProductAdditionalInfo` (für Produktseitenbild) gerendert.
        *   **Ausgabe:** Generiert die HTML-Struktur für das KI-Badge, das Produktbilder überlagert, einschließlich des anpassbaren Textes und Stylings.
    *   **`myaiactfree/views/templates/hook/banner.tpl`**:
        *   **Hook:** Wahrscheinlich in `displayHeader`, `displayTop`, `displayWrapperTop` oder `displayFooter` gerendert.
        *   **Ausgabe:** Rendert den shop-weiten KI-Richtlinien-Banner, einschließlich des anpassbaren Textes und eines Links zur KI-Richtlinienseite.

-   **Admin-Templates (`views/templates/admin/`)**:
    *   **`myaiactfree/views/templates/admin/configure.tpl`**:
        *   **Zweck:** Dies ist das Haupttemplate für die Konfigurationsseite des Moduls, auf die über `getContent()` zugegriffen wird. Es rendert alle globalen Einstellungen (aktivieren/deaktivieren, Badge-Text, Banner-Text usw.), wie in Abschnitt 4.1 beschrieben.
    *   **`myaiactfree/views/templates/admin/configure_intro.tpl`**:
        *   **Zweck:** Zeigt wahrscheinlich eine einführende Nachricht oder Erklärung oben auf der Konfigurationsseite des Moduls an, vielleicht zur Erklärung des KI-Gesetzes oder des Zwecks des Moduls.
    *   **`myaiactfree/views/templates/admin/product_tab.tpl`**:
        *   **Hook:** Gerendert über `displayAdminProductsExtra`.
        *   **Zweck:** Dieses Template bietet die Schnittstelle innerhalb der Produktbearbeitungsseite (Back Office > Katalog > Produkte > Produkt bearbeiten), wo Händler den Inhalt und die Bilder eines Produkts individuell als KI-generiert markieren können. Es enthält die Kontrollkästchen oder Schalter für produktspezifische KI-Flags.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:
    *   Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen.
    *   Konfigurationseinstellungen werden in der Tabelle `ps_configuration` gespeichert, wobei die Schlüssel typischerweise mit `MYAIACTFREE_` beginnen. Beispiele:
        *   `MYAIACTFREE_ENABLED`
        *   `MYAIACTFREE_SHOW_BADGE`
        *   `MYAIACTFREE_BADGE_TEXT`
        *   `MYAIACTFREE_BADGE_COLOR`
        *   `MYAIACTFREE_BADGE_TEXT_COLOR`
        *   `MYAIACTFREE_SHOW_ADDITIONAL_INFO`
        *   `MYAIACTFREE_ADDITIONAL_INFO_TEXT`
        *   `MYAIACTFREE_SHOW_BANNER`
        *   `MYAIACTFREE_BANNER_TEXT`
        *   `MYAIACTFREE_POLICY_URL`
    *   Produktspezifische KI-Flags (für Inhalt und Bilder) werden wahrscheinlich als `Product`-Objekteigenschaften oder in einem benutzerdefinierten Feld, das der `Product`-Entität zugeordnet ist, gespeichert, möglicherweise durch `Configuration::updateValue` mit einem Produkt-ID-Suffix oder durch direkte Änderung der Daten des `Product`-Objekts.

-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
|---|---|---|
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | CSS/JS-Assets (`front.css`, `front.js`) und potenziell den shop-weiten Banner (`banner.tpl`) injizieren. |
| `displayTop` / `displayWrapperTop` | Oft ganz oben im Seiteninhalt. | Alternativer Hook für den shop-weiten Banner (`banner.tpl`). |
| `displayFooter` | Am unteren Ende jeder Seite. | Alternativer Hook für den shop-weiten Banner (`banner.tpl`). |
| `displayProductListReviews` | Auf Produktlistenseiten, in der Nähe von Produktbildern. | Das KI-Badge (`ai_badge.tpl`) auf Produkt-Thumbnails rendern. |
| `displayProductAdditionalInfo` | Auf der Produktseite, in der Nähe des Produktbild-/Preisblocks. | Das KI-Badge (`ai_badge.tpl`) auf dem Hauptproduktbild rendern. |
| `displayProductExtraContent` | Auf der Produktseite, typischerweise unter der Beschreibung oder in einem neuen Tab. | Den zusätzlichen Info-Hinweis (`additional_info.tpl`) rendern. |
| `displayAdminProductsExtra` | Auf der Produktbearbeitungsseite im Back Office. | Den benutzerdefinierten Tab/Abschnitt für produktspezifische KI-Kennzeichnung (`product_tab.tpl`) injizieren. |
| `actionProductUpdate` | Nach der Aktualisierung eines Produkts im Back Office. | Die produktspezifischen KI-Flags (Inhalt/Bild) in der Datenbank speichern. |
| `actionProductAdd` | Nach dem Hinzufügen eines neuen Produkts im Back Office. | Produktspezifische KI-Flags für neue Produkte initialisieren. |

## 5. Offizieller Support & Updates
Für offizielle Updates, technischen Support und den Zugriff auf die neuesten Versionen des Moduls „Free My AI Act - Artificial Intelligence Act compliance“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität oder Kompatibilität des Moduls zur Verfügung.
