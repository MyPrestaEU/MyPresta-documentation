---
title: "Facebook Produkt teilen + Rabattcode - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Facebook Produkt teilen + Rabattcode“ von MyPresta.eu."
sidebar:
  label: "Facebook Produkt teilen + Rabattcode"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Facebook product share + discount code auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/facebook-product-share-discount-code.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/facebook-product-share-discount-code/)
>
> ---


# Facebook Produkt teilen + Rabattcode

## 1. Anforderungen & Kompatibilität
-   **Unterstützte PrestaShop-Versionen**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x
-   **PHP-Kompatibilität**: PHP 5.6 - 8.5
-   **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop erforderlich und in den meisten Hosting-Umgebungen verfügbar.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)
Nach der Installation navigieren Sie zu **Module > Modul-Manager** und klicken Sie neben „Facebook Produkt teilen + Rabattcode“ auf „Konfigurieren“. Dieser Bildschirm ermöglicht es Ihnen, die Kernfunktionalität und das Erscheinungsbild des Moduls zu steuern.

#### **Allgemeine Einstellungen**

-   **Modul aktivieren / deaktivieren:**
    -   **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für das gesamte Modul.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Der Facebook-Teilen-Button wird auf den Produktseiten angezeigt, und die Rabattcode-Funktionalität ist aktiv.
        -   *Wenn deaktiviert:* Das Modul ist vollständig inaktiv. Der Teilen-Button wird nicht angezeigt, und es werden keine Rabattcodes generiert.
    -   **Empfohlener Wert:** JA (um die Funktionen des Moduls zu aktivieren).
    -   **Händlerszenario / Beispiel:** Wenn Sie das Modul zum ersten Mal einrichten oder Wartungsarbeiten durchführen, können Sie es vorübergehend deaktivieren. Sobald es bereit ist, aktivieren Sie es, um Freigaben und Rabatte zu generieren.

-   **Facebook App ID:**
    -   **Was diese Einstellung bewirkt:** Dieses Feld erfordert Ihre eindeutige Facebook-Anwendungs-ID. Diese ID ist entscheidend, damit Facebook Ihre Website korrekt identifizieren und Freigaben verfolgen kann. Sie müssen eine Facebook-App auf der Facebook-Entwicklerplattform (developers.facebook.com) erstellen, um diese ID zu erhalten.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Bei korrekter Eingabe:* Das Modul kommuniziert ordnungsgemäß mit Facebook, wodurch Freigaben verfolgt und der Rabattmechanismus funktionieren kann.
        -   *Bei falscher oder leerer Eingabe:* Die Facebook-Teilen-Funktionalität funktioniert möglicherweise nicht, oder Freigaben werden möglicherweise nicht verfolgt, wodurch die Ausgabe von Rabattcodes verhindert wird.
    -   **Empfohlener Wert:** Ihre gültige Facebook App ID (z.B. `123456789012345`).
    -   **Händlerszenario / Beispiel:** Sie haben eine Facebook-App für Ihren Shop erstellt. Kopieren Sie die App-ID aus Ihrem Facebook-Entwickler-Dashboard und fügen Sie sie hier ein. Dies ist eine einmalige Einrichtung.

-   **Rabatt-Typ:**
    -   **Was diese Einstellung bewirkt:** Bestimmt die Art des Rabatts, den Kunden nach dem Teilen erhalten.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn auf „Prozentsatz“ eingestellt:* Der Rabattcode bietet einen prozentualen Nachlass auf den Gesamtbestellwert (z.B. 10 % Rabatt).
        -   *Wenn auf „Betrag“ eingestellt:* Der Rabattcode bietet einen festen monetären Wert als Nachlass auf den Gesamtbestellwert (z.B. 5 € Rabatt).
    -   **Empfohlener Wert:** „Prozentsatz“ oder „Betrag“ basierend auf Ihrer Marketingstrategie.
    -   **Händlerszenario / Beispiel:** Wenn Sie größere Bestellungen fördern möchten, könnte ein prozentualer Rabatt ansprechender sein. Für kleinere, häufige Einkäufe könnte ein fester Betrag effektiver sein.

-   **Rabattwert:**
    -   **Was diese Einstellung bewirkt:** Legt den tatsächlichen Wert des Rabatts fest.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn „Rabatt-Typ“ Prozentsatz ist:* Geben Sie den Prozentwert ein (z.B. `10` für 10 %).
        -   *Wenn „Rabatt-Typ“ Betrag ist:* Geben Sie den monetären Wert ein (z.B. `5.00` für 5 €).
    -   **Empfohlener Wert:** Ein Wert, der für Kunden attraktiv, aber auch profitabel für Ihr Geschäft ist (z.B. `10` für 10 % Rabatt oder `5.00` für 5 € Rabatt).
    -   **Händlerszenario / Beispiel:** Sie beschließen, einen Rabatt von 15 % für das Teilen anzubieten. Sie würden „Rabatt-Typ“ auf „Prozentsatz“ und „Rabattwert“ auf `15` setzen.

-   **Mindestbetrag für Rabatt:**
    -   **Was diese Einstellung bewirkt:** Legt einen Mindestbestellwert (vor Versand) fest, den ein Kunde erreichen muss, um den generierten Rabattcode verwenden zu können.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn ein Wert eingegeben wird (z.B. `50.00`):* Der Rabattcode ist nur gültig, wenn der Warenkorbwert des Kunden diesem Betrag entspricht oder höher ist.
        -   *Wenn leer gelassen oder auf `0` gesetzt:* Der Rabattcode kann für jede Bestellung verwendet werden, unabhängig von ihrem Gesamtwert.
    -   **Empfohlener Wert:** Ein Wert, der Kunden dazu anregt, mehr Artikel in ihren Warenkorb zu legen, oder `0`, wenn Sie keinen Mindestbetrag wünschen.
    -   **Händlerszenario / Beispiel:** Um zu verhindern, dass Kunden einen 10 %-Rabatt auf einen 1-Euro-Artikel verwenden, könnten Sie einen Mindestbetrag von `25.00 €` festlegen.

-   **Gültigkeit des Rabattcodes (in Tagen):**
    -   **Was diese Einstellung bewirkt:** Definiert, wie viele Tage der generierte Rabattcode ab dem Zeitpunkt seiner Ausstellung gültig ist.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn ein Wert eingegeben wird (z.B. `7`):* Der Rabattcode läuft nach 7 Tagen ab, was ein Gefühl der Dringlichkeit erzeugt.
        -   *Wenn leer gelassen oder auf `0` gesetzt:* Der Rabattcode hat kein Ablaufdatum (nicht empfohlen, da dies die Dringlichkeit verringert).
    -   **Empfohlener Wert:** `7` bis `30` Tage, um eine schnelle Nutzung zu fördern.
    -   **Händlerszenario / Beispiel:** Sie möchten, dass Kunden ihren Rabatt schnell nutzen. Wenn Sie dies auf `7` Tage einstellen, werden sie dazu angehalten, innerhalb einer Woche einen Kauf zu tätigen.

-   **Rabattcode-Präfix:**
    -   **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, allen generierten Rabattcodes ein benutzerdefiniertes Präfix hinzuzufügen. Dies hilft Ihnen, von diesem Modul generierte Codes in Ihrer PrestaShop-Rabattverwaltung zu identifizieren.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn ein Präfix eingegeben wird (z.B. `FBSHARE-`):* Alle generierten Codes beginnen mit diesem Präfix (z.B. `FBSHARE-XYZ123`).
        -   *Wenn leer gelassen:* Codes werden ohne ein spezifisches Präfix generiert.
    -   **Empfohlener Wert:** Ein kurzes, beschreibendes Präfix (z.B. `FB-`, `SHARE-`, `SOCIAL-`).
    -   **Händlerszenario / Beispiel:** Um den Erfolg Ihrer Facebook-Sharing-Kampagne einfach zu verfolgen, könnten Sie `FB2023-` als Präfix verwenden.

-   **Teilen-Button anzeigen auf:**
    -   **Was diese Einstellung bewirkt:** Bestimmt, wo der Facebook-Teilen-Button auf Ihren Produktseiten angezeigt wird. Dies ist typischerweise eine Dropdown- oder Radiobutton-Auswahl.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Header:* Button erscheint im Header des Shops (weniger üblich für produktspezifische Freigaben).
        -   *Spalten (Links/Rechts):* Button erscheint in einer der Seitenleisten.
        -   *Produktseite (Hauptinhalt):* Button erscheint im Hauptbereich der Produktinformationen (am häufigsten und empfohlen).
        -   *Footer:* Button erscheint im Footer des Shops.
    -   **Empfohlener Wert:** „Produktseite (Hauptinhalt)“ für maximale Sichtbarkeit und Relevanz.
    -   **Händlerszenario / Beispiel:** Sie möchten, dass der Teilen-Button direkt neben dem Produktbild und der Beschreibung gut sichtbar ist. Die Auswahl von „Produktseite (Hauptinhalt)“ stellt dies sicher.

-   **Text für Teilen-Button:**
    -   **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, den auf dem Facebook-Teilen-Button angezeigten Text anzupassen.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn Text eingegeben wird (z.B. „Teilen & Rabatt erhalten!“):* Der Button zeigt Ihren benutzerdefinierten Text an.
        -   *Wenn leer gelassen:* Ein Standardtext (z.B. „Auf Facebook teilen“) wird verwendet.
    -   **Empfohlener Wert:** Klarer, handlungsorientierter Text, der den Vorteil hervorhebt (z.B. „Teilen für einen Rabatt!“, „X% Rabatt erhalten – Jetzt teilen!“).
    -   **Händlerszenario / Beispiel:** Um Kunden anzulocken, könnten Sie den Button-Text in „Teilen & Ihren Rabatt freischalten!“ ändern.

-   **Titel der Popup-Nachricht:**
    -   **Was diese Einstellung bewirkt:** Legt den Titel des Popup-Fensters fest, das nach einer erfolgreichen Freigabe erscheint und den Rabattcode anzeigt.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn ein Titel eingegeben wird (z.B. „Herzlichen Glückwunsch!“):* Das Popup zeigt Ihren benutzerdefinierten Titel an.
        -   *Wenn leer gelassen:* Ein Standardtitel wird verwendet.
    -   **Empfohlener Wert:** Ein freundlicher und gratulierender Titel (z.B. „Ihr Rabattcode!“, „Vielen Dank für das Teilen!“).
    -   **Händlerszenario / Beispiel:** Sie möchten, dass sich der Kunde belohnt fühlt, also setzen Sie den Titel auf „Hier ist Ihr exklusiver Rabatt!“.

-   **Inhalt der Popup-Nachricht:**
    -   **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, den Haupttextinhalt im Rabattcode-Popup anzupassen. Sie können Anweisungen oder zusätzliche Nachrichten hinzufügen.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn Inhalt eingegeben wird:* Das Popup zeigt Ihre benutzerdefinierte Nachricht an.
        -   *Wenn leer gelassen:* Eine Standardnachricht wird verwendet.
    -   **Empfohlener Wert:** Eine klare Nachricht, die den Kunden anweist, den Code zu kopieren und wie er ihn verwendet (z.B. „Kopieren Sie diesen Code und wenden Sie ihn an der Kasse an, um Ihren Rabatt zu erhalten.“).
    -   **Händlerszenario / Beispiel:** Sie möchten Kunden daran erinnern, wo sie den Code verwenden sollen: „Vielen Dank für das Teilen! Verwenden Sie den untenstehenden Code an der Kasse für Ihre Ersparnisse.“

#### **Erweiterte Einstellungen (falls verfügbar)**

-   **CSS-Stylesheet für Button/Popup:**
    -   **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, benutzerdefiniertes CSS auszuwählen oder einzugeben, um den Teilen-Button und/oder das Rabatt-Popup besser an Ihr Theme anzupassen.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn benutzerdefiniertes CSS angewendet wird:* Das visuelle Erscheinungsbild (Farben, Schriftarten, Größen) des Buttons und des Popups ändert sich gemäß Ihren Stilen.
        -   *Wenn Standard verwendet wird:* Das Modul verwendet seine integrierte Formatierung.
    -   **Empfohlener Wert:** Zunächst leer lassen, dann anpassen, wenn die Standardformatierung nicht zu Ihrer Marke passt.
    -   **Händlerszenario / Beispiel:** Ihr Shop verwendet einen bestimmten Blauton für Buttons. Sie können hier eine CSS-Regel hinzufügen, um die Hintergrundfarbe des Teilen-Buttons in diesen Farbton zu ändern.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Modulkonfiguration | Modul aktivieren / deaktivieren | JA | Aktiviert/deaktiviert alle Modulfunktionen. |
| | Facebook App ID | Ihre App ID | Verknüpft Ihren Shop mit Ihrer Facebook App zur Verfolgung von Freigaben. |
| | Rabatt-Typ | Prozentsatz | Definiert, ob der Rabatt ein Prozentsatz oder ein fester Betrag ist. |
| | Rabattwert | z.B. 10 (für 10%) | Der tatsächliche Wert des angebotenen Rabatts. |
| | Mindestbetrag für Rabatt | 0 (kein Minimum) | Legt einen Mindestbestellwert für die Nutzung des Rabattcodes fest. |
| | Gültigkeit des Rabattcodes (in Tagen) | 7-30 Tage | Legt eine Ablaufperiode für generierte Rabattcodes fest. |
| | Rabattcode-Präfix | FB- | Fügt generierten Codes ein benutzerdefiniertes Präfix zur einfachen Identifizierung hinzu. |
| | Teilen-Button anzeigen auf | Produktseite (Hauptinhalt) | Steuert die Platzierung des Teilen-Buttons auf Produktseiten. |
| | Text für Teilen-Button | Teilen für einen Rabatt! | Passt den auf dem Teilen-Button angezeigten Text an. |
| | Titel der Popup-Nachricht | Ihr Rabattcode! | Legt den Titel des Rabattcode-Popups fest. |
| | Inhalt der Popup-Nachricht | Kopieren Sie diesen Code... | Passt die Hauptnachricht im Rabattcode-Popup an. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Der Facebook-Teilen-Button wird auf meinen Produktseiten nicht angezeigt.**
**A1:**
*   **Modulstatus prüfen:** Stellen Sie sicher, dass das Modul in den Konfigurationseinstellungen aktiviert ist.
*   **Facebook App ID überprüfen:** Überprüfen Sie nochmals, ob Ihre Facebook App ID in der Modulkonfiguration korrekt eingegeben wurde. Eine falsche oder fehlende ID verhindert das Laden des Buttons.
*   **Button-Platzierung prüfen:** Bestätigen Sie, dass die Einstellung „Teilen-Button anzeigen auf“ korrekt gewählt ist (z.B. „Produktseite (Hauptinhalt)“). Wenn Ihr Theme stark angepasste Hooks hat, müssen Sie möglicherweise verschiedene Platzierungen ausprobieren oder einen Entwickler konsultieren.
*   **Cache leeren:** Gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Einstellungen > Performance** und leeren Sie den Smarty-Cache und alle Caches. Manchmal verhindern alte Cache-Dateien, dass neue Modulelemente angezeigt werden.

**F2: Kunden teilen, erhalten aber keinen Rabattcode.**
**A2:**
*   **Facebook App ID:** Dies ist die häufigste Ursache. Das Modul verlässt sich auf die Facebook App ID, um erfolgreiche Freigaben zu verfolgen. Stellen Sie sicher, dass sie korrekt ist und dass Ihre Facebook App ordnungsgemäß konfiguriert ist (z.B. Website-URL hinzugefügt).
*   **Facebook-Berechtigungen/Datenschutz:** Manchmal können die Facebook-Datenschutzeinstellungen eines Kunden oder Browser-Werbeblocker die Freigabeverfolgung stören. Dies ist seltener, kann aber vorkommen.
*   **Modulkonfiguration:** Überprüfen Sie alle rabattbezogenen Einstellungen (Rabatt-Typ, Wert, Gültigkeit). Stellen Sie sicher, dass sie auf gültige Werte eingestellt sind.
*   **PrestaShop-Gutscheineinstellungen:** Stellen Sie sicher, dass die allgemeinen Gutschein-/Warenkorbregel-Einstellungen Ihres PrestaShop-Shops die Erstellung neuer Codes nicht verhindern (z.B. maximale Anzahl von Gutscheinen erreicht, obwohl dies selten ist).

**F3: Das Rabattcode-Popup sieht seltsam aus oder passt nicht zum Design meines Shops.**
**A3:**
*   **Theme-Konflikte:** Ihr benutzerdefiniertes PrestaShop-Theme könnte widersprüchliche CSS-Stile haben.
*   **Modul-CSS:** Das Modul enthält sein eigenes CSS. Sie können versuchen, es zu überschreiben.
*   **Lösung:** Suchen Sie in der Modulkonfiguration nach Optionen für „Benutzerdefiniertes CSS“ oder „Stylesheet“. Möglicherweise müssen Sie dort benutzerdefinierte CSS-Regeln hinzufügen, um das Erscheinungsbild des Popups anzupassen. Wenn Sie mit CSS nicht vertraut sind, kann ein Webmaster oder Entwickler helfen. Das Leeren des Browser-Caches kann manchmal auch kleinere Anzeigeprobleme beheben.

**F4: Kann ich den Button-Text und die Popup-Nachrichten in andere Sprachen übersetzen?**
**A4:** Ja, das PrestaShop-Übersetzungssystem unterstützt Modulübersetzungen.
*   Gehen Sie in Ihrem Back Office zu **International > Übersetzungen**.
*   Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann Ihre Sprache.
*   Suchen Sie das Modul „Facebook Produkt teilen + Rabattcode“, und Sie können alle benutzerseitigen Texte, einschließlich des Button-Textes und der Popup-Nachrichten, übersetzen.

**F5: Was passiert, wenn ein Kunde ein Produkt mehrmals teilt? Erhält er mehrere Rabatte?**
**A5:** Das Modul ist so konzipiert, dass es pro *erfolgreichem Teilen-Ereignis* für einen bestimmten Benutzer einen einzigartigen Rabattcode ausgibt. Je nach genauer Implementierung kann ein Benutzer jedoch verschiedene Produkte teilen und mehrere Codes erhalten. Es ist im Allgemeinen Best Practice, einzigartige Freigaben für einzigartige Belohnungen zu fördern. Wenn Sie es auf einen Code pro Kunde beschränken möchten, unabhängig von den Freigaben, benötigen Sie möglicherweise eine benutzerdefinierte Entwicklung oder müssen generierte Gutscheine manuell verwalten.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)
Dieser Abschnitt bietet einen tiefen Einblick in die technische Struktur des Moduls „Facebook Produkt teilen + Rabattcode“ für Entwickler und Webmaster.

### 4.1 Architekturübersicht
Das Modul folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich die `Module`-Klasse für Installation, Deinstallation und Konfiguration nutzt. Es integriert sich über Hooks in das Front-Office, um den Teilen-Button anzuzeigen, und verwendet AJAX zur Handhabung der Rabattcode-Generierung nach dem Teilen. Die Kernlogik für die Gutscheinerstellung ist wahrscheinlich in der Hauptklasse des Moduls oder einem Helfer gekapselt.

### 4.2 Controller (`controllers/`)
Dieses Modul scheint basierend auf dem bereitgestellten Inventar keine dedizierten `ModuleFrontController`- oder `AdminController`-Dateien im Verzeichnis `controllers/` zu verwenden. Front-Office-AJAX-Interaktionen werden wahrscheinlich direkt in der Hauptmoduldatei (`ajax_productlike.php`) oder über einen generischen PrestaShop-AJAX-Dispatcher gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)
Basierend auf dem bereitgestellten Inventar sind keine benutzerdefinierten `ObjectModel`-Klassen in einem `classes/`-Verzeichnis definiert. Das Modul verwaltet seine Konfiguration wahrscheinlich direkt über `Configuration::get()` und `Configuration::updateValue()` und erstellt PrestaShop `CartRule`-Objekte für Rabatte.

### 4.4 JavaScript-Assets (`views/js/`)
Das Modul enthält mehrere JavaScript-Dateien, die clientseitige Logik für die Facebook-Interaktion und die Popup-Anzeige anzeigen.

-   `productlike/js/productlike.js`:
    *   **Umfang:** Front-Office.
    *   **Verantwortlichkeit:** Behandelt wahrscheinlich die Kernlogik zum Initiieren des Facebook-Teilen-Dialogs, zum Abhören des Teilen-Abschlussereignisses vom Facebook SDK und zum anschließenden Ausführen eines AJAX-Aufrufs an den PrestaShop-Shop, um den Rabattcode anzufordern. Es würde auch die Anzeige des Rabattcode-Popups verwalten.
    *   **Schlüsselfunktionalitäten:** Facebook SDK-Initialisierung, `FB.ui`-Methodenaufrufe zum Teilen, AJAX-Anfragen an das Backend des Moduls, DOM-Manipulation für die Popup-Anzeige.

-   `productlike/js/script.js`:
    *   **Umfang:** Front-Office.
    *   **Verantwortlichkeit:** Dies könnte ein allgemeines Dienstprogramm-Skript oder eine Fallback-/Alternative zu `productlike.js` sein. Es könnte Ereignis-Listener für den Klick auf den Teilen-Button enthalten oder die Anzeige-/Ausblendlogik für das Rabatt-Popup handhaben.
    *   **Schlüsselfunktionalitäten:** Ereignisbindung, potenziell einfache Animationen oder DOM-Manipulation.

-   `productlike/lib/voucherengine/script.js`:
    *   **Umfang:** Front-Office.
    *   **Verantwortlichkeit:** Deutet auf ein dediziertes Skript für die Gutscheinanzeige und -interaktion hin. Dies könnte das Kopieren des Gutscheincodes in die Zwischenablage, das Schließen des Popups oder andere Benutzeroberflächenelemente im Zusammenhang mit dem Rabatt handhaben.
    *   **Schlüsselfunktionalitäten:** Zwischenablage-API-Interaktion, Popup-Schließereignisse, UI-Feedback.

### 4.5 CSS-Stylesheets (`views/css/`)
Das Modul verwendet mehrere CSS-Dateien zur Gestaltung seiner Front-Office-Komponenten.

-   `productlike/css/css.css`:
    *   **Umfang:** Front-Office-Kundenstyling.
    *   **Verantwortlichkeit:** Enthält allgemeine Stile für den Facebook-Teilen-Button und potenziell das Rabattcode-Popup.
    *   **Schlüsselselektoren:** `.productlike-button`, `.productlike-popup`, `.productlike-voucher-code`. Entwickler können diese in der `custom.css` ihres Themes oder über die benutzerdefinierte CSS-Eingabe des Moduls überschreiben, falls verfügbar.

-   `productlike/css.css`:
    *   **Umfang:** Front-Office-Kundenstyling.
    *   **Verantwortlichkeit:** Potenziell ein älteres oder alternatives Stylesheet oder spezifische Stile für bestimmte Elemente, die nicht von `css.css` abgedeckt werden.
    *   **Schlüsselselektoren:** Ähnlich wie `css.css`, abhängig von seinem Inhalt.

-   `productlike/lib/voucherengine/ps16.css`:
    *   **Umfang:** Front-Office-Kundenstyling, speziell für PrestaShop 1.6-Kompatibilität.
    *   **Verantwortlichkeit:** Bietet Styling-Anpassungen, um sicherzustellen, dass das Gutschein-Popup und der Button auf PrestaShop 1.6-Themes korrekt aussehen, die möglicherweise unterschiedliche Standard-Elementstile haben.
    *   **Schlüsselselektoren:** Zielt wahrscheinlich auf gängige PrestaShop 1.6 UI-Elemente ab, um visuelle Konsistenz zu gewährleisten.

### 4.6 Smarty-Template-Struktur (`views/templates/`)
Das Modul verwendet Smarty-Templates zur Darstellung seiner Front-Office-Komponenten.

-   **Hook-Templates (`views/templates/hook/`)**:
    *   `productlike/header.tpl`:
        *   **Hook:** `displayHeader`
        *   **Zweck:** Dieses Template ist wahrscheinlich für die Initialisierung des Facebook JavaScript SDK, das Laden notwendiger JavaScript-Dateien und möglicherweise die Übergabe von Konfigurationsvariablen (wie der Facebook App ID) vom Backend des Moduls an das Front-End-JavaScript verantwortlich. Es stellt sicher, dass die Facebook API bereit ist, bevor der Teilen-Button gerendert wird.
    *   `productlike/share.tpl`:
        *   **Hook:** `displayProductButtons`, `displayRightColumnProduct`, `displayLeftColumnProduct`, `displayFooterProduct` (oder ähnliche Produktseiten-Hooks, je nach Konfiguration).
        *   **Zweck:** Rendert den eigentlichen „Auf Facebook teilen“-Button auf der Produktseite. Es enthält die HTML-Struktur für den Button und möglicherweise einen Platzhalter für das Rabattcode-Popup, das dann dynamisch von JavaScript gefüllt wird.

-   **Admin-Templates (`views/templates/admin/`)**: Keine explizit aufgeführt, was impliziert, dass die Konfiguration direkt von `getContent()` in der Hauptmoduldatei gehandhabt wird.

-   **Front-Office-Templates (`views/templates/front/`)**: Keine explizit aufgeführt, da die Hauptinteraktion über Hooks und Popups erfolgt.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:
    *   Das Modul erstellt wahrscheinlich keine benutzerdefinierten Datenbanktabellen.
    *   Konfigurationseinstellungen (Facebook App ID, Rabattwerte usw.) werden in der Tabelle `ps_configuration` unter Schlüsseln wie `PRODUCTLIKE_FACEBOOK_APP_ID`, `PRODUCTLIKE_DISCOUNT_TYPE`, `PRODUCTLIKE_DISCOUNT_VALUE` usw. gespeichert.
    *   Generierte Rabattcodes sind Standard-PrestaShop `CartRule`-Einträge, die in `ps_cart_rule` und verwandten Tabellen gespeichert werden.

-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| :-------- | :--------------- | :---------------- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Initialisiert das Facebook SDK, lädt Modul-JS/CSS, übergibt Konfigurationsvariablen. |
| `displayProductButtons` | Auf der Produktseite, typischerweise in der Nähe des „In den Warenkorb“-Buttons. | Rendert den Facebook-Teilen-Button. (Üblich für PS 1.7+) |
| `displayRightColumnProduct` | In der rechten Spalte der Produktseite. | Rendert den Facebook-Teilen-Button (falls konfiguriert). |
| `displayLeftColumnProduct` | In der linken Spalte der Produktseite. | Rendert den Facebook-Teilen-Button (falls konfiguriert). |
| `displayFooterProduct` | Im Footer-Bereich der Produktseite. | Rendert den Facebook-Teilen-Button (falls konfiguriert). |
| `displayProductExtraContent` | Auf der Produktseite, für zusätzliche Inhalts-Tabs/Blöcke. | Alternativer Hook für die Button-Platzierung (PS 1.7+). |
| `actionFrontControllerSetMedia` | Bevor der Front-Controller die Seite rendert. | Registriert die JS- und CSS-Dateien des Moduls. |
| `actionObjectCartRuleAddAfter` | Nachdem eine neue Warenkorbregel (Gutschein) hinzugefügt wurde. | Potenziell zur Protokollierung oder weiteren Verarbeitung generierter Gutscheine verwendet. |

## 5. Offizieller Support & Updates
Für die neuesten Updates, Fehlerbehebungen und professionellen Support für Ihr Modul „Facebook Produkt teilen + Rabattcode“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Team ist bestrebt, Unterstützung zu leisten und sicherzustellen, dass Ihr Modul optimal funktioniert.
