---
title: "EU-Cookie-Gesetz - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „EU-Cookie-Gesetz“ von MyPresta.eu."
sidebar:
  label: "EU-Cookie-Gesetz - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul European Union Cookie Law auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/european-union-cookie-law.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/european-union-cookie-law/)
>
> ---


# EU-Cookie-Gesetz

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Haupt- und einzige Konfigurationsbildschirm für das Modul „EU-Cookie-Gesetz“. Hier finden Sie alle Einstellungen zur Anpassung Ihrer Cookie-Benachrichtigung.

#### **Modul aktivieren / deaktivieren**

- **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter, um die Cookie-Benachrichtigung in Ihrem gesamten Shop ein- oder auszuschalten.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Die Cookie-Benachrichtigungsleiste wird in Ihrem Front Office gemäß Ihren anderen Einstellungen angezeigt.
  - *Wenn deaktiviert:* Die Cookie-Benachrichtigungsleiste wird keinem Besucher angezeigt.
- **Empfohlener Wert:** JA (es sei denn, Sie haben eine andere Methode zur Cookie-Konformität).
- **Händlerszenario / Beispiel:** Sie haben das Modul gerade installiert und möchten den Cookie-Hinweis aktivieren. Stellen Sie dies auf „JA“. Wenn Sie es vorübergehend für Wartungsarbeiten oder Tests ausblenden müssen, können Sie es auf „NEIN“ setzen.

#### **Cookie-Text**

- **Was diese Einstellung bewirkt:** Dies ist die eigentliche Nachricht, die Ihren Kunden bezüglich der Cookie-Nutzung angezeigt wird. Sie unterstützt mehrere Sprachen, sodass Sie für jede in Ihrem Shop aktivierte Sprache eine lokalisierte Nachricht bereitstellen können.
- **Auswirkung der Änderung dieser Einstellung:** Der hier eingegebene Text wird in der Cookie-Benachrichtigungsleiste angezeigt. Sie können den Rich-Text-Editor verwenden, um den Text zu formatieren, Links hinzuzufügen (z. B. zu Ihrer vollständigen Datenschutzrichtlinie) und wichtige Informationen hervorzuheben.
- **Empfohlener Wert:** Eine klare, prägnante Nachricht, die Benutzer über Cookies informiert und idealerweise einen Link zu Ihrer vollständigen Datenschutzrichtlinie oder Cookie-Richtlinienseite enthält.
- **Händlerszenario / Beispiel:** Sie könnten schreiben: „Diese Website verwendet Cookies, um sicherzustellen, dass Sie die beste Erfahrung auf unserer Website erhalten. [Link zur Datenschutzrichtlinie]“. Stellen Sie sicher, dass Sie dies in alle aktiven Sprachen Ihres Shops übersetzen.

#### **Schaltflächentext**

- **Was diese Einstellung bewirkt:** Dies definiert den Text, der auf der Schaltfläche angezeigt wird, die Kunden anklicken, um die Cookie-Richtlinie zu bestätigen oder zu akzeptieren. Wie der Cookie-Text unterstützt er mehrere Sprachen.
- **Auswirkung der Änderung dieser Einstellung:** Die Schaltfläche zeigt den von Ihnen angegebenen Text an. Durch Klicken auf diese Schaltfläche wird die Cookie-Benachrichtigung für den Benutzer geschlossen.
- **Empfohlener Wert:** „Ich verstehe“, „Akzeptieren“, „Verstanden“, „Weiter“ oder „OK“.
- **Händlerszenario / Beispiel:** Um deutlich zu machen, dass Benutzer die Richtlinie bestätigen, könnten Sie dies auf „Ich verstehe und akzeptiere“ setzen.

#### **Position**

- **Was diese Einstellung bewirkt:** Bestimmt, wo die Cookie-Benachrichtigungsleiste auf Ihrer Website erscheint.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Oben:* Die Leiste erscheint fest am oberen Rand des Browserfensters.
  - *Unten:* Die Leiste erscheint fest am unteren Rand des Browserfensters.
- **Empfohlener Wert:** Unten (oft weniger aufdringlich als oben, was manchmal Header-Elemente stören kann).
- **Händlerszenario / Beispiel:** Sie möchten, dass der Cookie-Hinweis sichtbar ist, aber Ihre Hauptnavigation oder Ihr Logo nicht verdeckt. Die Wahl von „Unten“ ist in der Regel ein guter Kompromiss.

#### **Hintergrundfarbe**

- **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Auswahl der Hintergrundfarbe der Cookie-Benachrichtigungsleiste. Dies hilft, die Leiste visuell in das Design Ihres Shops zu integrieren.
- **Auswirkung der Änderung dieser Einstellung:** Der Hintergrund der Cookie-Leiste ändert sich in die ausgewählte Farbe. Ein Farbwähler-Tool wird normalerweise zur einfachen Auswahl bereitgestellt.
- **Empfohlener Wert:** Eine Farbe, die gut mit Ihrer Textfarbe kontrastiert und das Branding Ihres Shops ergänzt.
- **Händlerszenario / Beispiel:** Ihr Shop verwendet viel Blau. Sie könnten ein helles Blau oder ein dezentes Grau für den Hintergrund wählen, um zu Ihrem Thema zu passen.

#### **Textfarbe**

- **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Auswahl der Farbe des Textes innerhalb der Cookie-Benachrichtigungsleiste.
- **Auswirkung der Änderung dieser Einstellung:** Der Text in der Cookie-Leiste ändert sich in die ausgewählte Farbe.
- **Empfohlener Wert:** Eine Farbe, die einen guten Kontrast zu Ihrer gewählten Hintergrundfarbe bietet, um die Lesbarkeit zu gewährleisten.
- **Händlerszenario / Beispiel:** Wenn Ihre Hintergrundfarbe dunkel ist, wählen Sie eine helle Textfarbe (z. B. Weiß, Hellgrau). Wenn Ihr Hintergrund hell ist, wählen Sie eine dunkle Textfarbe (z. B. Schwarz, Dunkelgrau).

#### **Linkfarbe**

- **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Auswahl der Farbe von Links, die in Ihrem „Cookie-Text“ enthalten sind (z. B. ein Link zu Ihrer Datenschutzrichtlinie).
- **Auswirkung der Änderung dieser Einstellung:** Alle `<a>`-Tags innerhalb des Textes der Cookie-Leiste werden in dieser Farbe angezeigt.
- **Empfohlener Wert:** Eine Farbe, die sich von der Haupttextfarbe abhebt, aber immer noch zu Ihrer Marke passt.
- **Händlerszenario / Beispiel:** Sie möchten, dass der Link zu Ihrer Datenschutzrichtlinie leicht erkennbar ist. Sie könnten die Akzentfarbe Ihrer Marke für den Link wählen.

#### **Schaltflächen-Hintergrundfarbe**

- **Was diese Einstellung bewirkt:** Legt die Hintergrundfarbe der Schaltfläche „Schaltflächentext“ fest.
- **Auswirkung der Änderung dieser Einstellung:** Die Schaltfläche hat die ausgewählte Hintergrundfarbe.
- **Empfohlener Wert:** Eine Farbe, die die Schaltfläche hervorhebt und Klicks fördert, oft passend zur Farbe der primären Call-to-Action-Schaltfläche Ihres Shops.
- **Händlerszenario / Beispiel:** Die „In den Warenkorb“-Schaltflächen Ihres Shops sind grün. Sie könnten Grün für den Hintergrund der Cookie-Schaltfläche wählen, um die Konsistenz zu wahren.

#### **Schaltflächen-Textfarbe**

- **Was diese Einstellung bewirkt:** Legt die Farbe des Textes auf der Schaltfläche „Schaltflächentext“ fest.
- **Auswirkung der Änderung dieser Einstellung:** Der Schaltflächentext wird in dieser Farbe angezeigt.
- **Empfohlener Wert:** Eine Farbe, die einen guten Kontrast zur Hintergrundfarbe der Schaltfläche bietet, um die Lesbarkeit zu gewährleisten.
- **Händlerszenario / Beispiel:** Wenn Ihr Schaltflächenhintergrund dunkelgrün ist, wählen Sie Weiß oder eine sehr helle Farbe für den Schaltflächentext.

#### **Cookie-Ablauf (in Tagen)**

- **Was diese Einstellung bewirkt:** Bestimmt, wie lange die Cookie-Benachrichtigung ausgeblendet bleibt, nachdem ein Benutzer auf die Schaltfläche „Ich verstehe“ geklickt hat. Nach diesem Zeitraum wird die Benachrichtigung für den Benutzer erneut angezeigt.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Auf 30 gesetzt:* Die Benachrichtigung wird für diesen spezifischen Benutzer 30 Tage lang ausgeblendet.
  - *Auf 0 gesetzt:* Die Benachrichtigung könnte bei jedem Besuch oder jeder Sitzung erneut angezeigt werden, was im Allgemeinen nicht empfohlen wird, da es störend sein kann.
- **Empfohlener Wert:** 30 bis 365 Tage. Eine gängige Praxis sind 90 oder 180 Tage.
- **Händlerszenario / Beispiel:** Um wiederkehrende Kunden nicht wiederholt zu stören, setzen Sie dies auf „180“ Tage. Das bedeutet, dass ein Kunde, der die Richtlinie akzeptiert, die Leiste sechs Monate lang nicht wieder sieht.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | **Modul aktivieren / deaktivieren** | JA | Hauptschalter für die Sichtbarkeit der Cookie-Leiste. |
| Modulkonfiguration | **Cookie-Text** | Anpassbar | Die Hauptnachricht zur Cookie-Nutzung, unterstützt Rich Text & Mehrsprachigkeit. |
| Modulkonfiguration | **Schaltflächentext** | Anpassbar | Text auf der Schaltfläche zum Schließen des Hinweises, mehrsprachig. |
| Modulkonfiguration | **Position** | Unten | Wo die Leiste erscheint (Oben oder Unten auf dem Bildschirm). |
| Modulkonfiguration | **Hintergrundfarbe** | Anpassbar | Hintergrundfarbe der Cookie-Leiste. |
| Modulkonfiguration | **Textfarbe** | Anpassbar | Farbe des Haupttextes in der Cookie-Leiste. |
| Modulkonfiguration | **Linkfarbe** | Anpassbar | Farbe aller Links innerhalb des Cookie-Textes. |
| Modulkonfiguration | **Schaltflächen-Hintergrundfarbe** | Anpassbar | Hintergrundfarbe der Schließen-Schaltfläche. |
| Modulkonfiguration | **Schaltflächen-Textfarbe** | Anpassbar | Farbe des Textes auf der Schließen-Schaltfläche. |
| Modulkonfiguration | **Cookie-Ablauf (in Tagen)** | 180-365 Tage | Wie lange der Hinweis nach Benutzerakzeptanz ausgeblendet bleibt. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Die Cookie-Leiste wird in meinem Shop nicht angezeigt.**
A1:

- **„Modul aktivieren / deaktivieren“ prüfen:** Stellen Sie sicher, dass diese Einstellung in der Modulkonfiguration auf „JA“ gesetzt ist.
- **Cache leeren:** Gehen Sie zu **Erweiterte Parameter > Performance** und klicken Sie oben rechts auf „Cache leeren“. Manchmal verhindern alte zwischengespeicherte Inhalte, dass neue Moduländerungen angezeigt werden.
- **Auf Konflikte prüfen:** Deaktivieren Sie vorübergehend andere kürzlich installierte Module, um festzustellen, ob ein Konflikt vorliegt.
- **Browser-Cache:** Versuchen Sie, den Cache Ihres Browsers zu leeren oder Ihren Shop in einem Inkognito-/privaten Browsing-Fenster zu öffnen.

**F2: Ich habe den Text aktualisiert, aber er ändert sich nicht im Front Office.**
A2:

- **Änderungen speichern:** Stellen Sie sicher, dass Sie nach Änderungen in der Modulkonfiguration auf die Schaltfläche „Speichern“ geklickt haben.
- **PrestaShop-Cache leeren:** Wie oben erwähnt, ist das Leeren des Smarty-Caches (unter **Erweiterte Parameter > Performance**) oft notwendig, damit sich Vorlagen- und Textänderungen auswirken.
- **Sprache prüfen:** Stellen Sie sicher, dass Sie den Text für die richtige Sprache bearbeiten, wenn Ihr Shop mehrsprachig ist.

**F3: Die Cookie-Leiste sieht seltsam aus oder passt nicht zu meinem Thema.**
A3:

- **Farben anpassen:** Verwenden Sie die Einstellungen „Hintergrundfarbe“, „Textfarbe“, „Linkfarbe“, „Schaltflächen-Hintergrundfarbe“ und „Schaltflächen-Textfarbe“, um sie an die Farbpalette Ihres Themas anzupassen.
- **Themenkonflikte:** Einige benutzerdefinierte Themen können widersprüchliche CSS-Stile aufweisen. Wenn das Anpassen der Farben nicht hilft, benötigen Sie möglicherweise einen Webentwickler, um das CSS zu überprüfen und kleinere Anpassungen vorzunehmen.

**F4: Wie füge ich einen Link zu meiner Datenschutzrichtlinie in den Cookie-Text ein?**
A4:

- Verwenden Sie im Feld „Cookie-Text“ den Rich-Text-Editor. Geben Sie den Text ein, der ein Link sein soll (z. B. „Datenschutzrichtlinie“), wählen Sie ihn aus und klicken Sie dann auf das „Link“-Symbol in der Editor-Symbolleiste. Geben Sie die URL Ihrer Datenschutzrichtlinienseite ein.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler, Webmaster und Agenturen, die mit dem Modul „EU-Cookie-Gesetz“ arbeiten.

### 4.1 Architekturübersicht

Das Modul `uecookie` ist ein unkompliziertes PrestaShop-Modul, das hauptsächlich dazu dient, eine Front-Office-Vorlage in einen Display-Hook einzufügen, gesteuert durch eine Standard-Konfigurationsmethode `getContent()`. Es nutzt die `Module`-Klasse von PrestaShop für Installation, Deinstallation und Konfiguration und verwendet Smarty-Vorlagen für die Darstellung der Cookie-Benachrichtigung. Die clientseitige Logik zum Schließen der Cookie-Leiste wird über JavaScript gehandhabt.

### 4.2 Controller (`controllers/`)

- Dieses Modul enthält **keine** benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Funktionalität wird innerhalb der Hauptmoduldatei und der zugehörigen Vorlagen und Assets abgewickelt.

### 4.3 Kernklassen & Modelle (`classes/`)

- Dieses Modul enthält **keine** benutzerdefinierten Klassen oder `ObjectModel`-Definitionen. Alle Konfigurationen werden direkt in `ps_configuration` mithilfe von `Configuration::get()` und `Configuration::updateValue()` gespeichert.

### 4.4 JavaScript-Assets (`views/js/`)

- `uecookie/jscolor/jscolor.js`:
  - **Umfang:** Back-Office.
  - **Zweck:** Bietet eine JavaScript-Farbwählerfunktion für das Konfigurationsformular des Moduls, die es Administratoren ermöglicht, Farben für die Cookie-Leiste visuell auszuwählen.
- `uecookie/tinymce-original.js`:
  - **Umfang:** Back-Office.
  - **Zweck:** Eine vollständige Version des TinyMCE-Rich-Text-Editors, der für das Feld „Cookie-Text“ in der Modulkonfiguration verwendet wird. Dies ermöglicht Administratoren, Text zu formatieren, Links hinzuzufügen usw.
- `uecookie/tinymce16.inc.js`:
  - **Umfang:** Back-Office.
  - **Zweck:** Wahrscheinlich eine Include- oder Konfigurationsdatei für TinyMCE, die möglicherweise dessen Symbolleiste oder Optionen für die PrestaShop 1.6-Kompatibilität oder spezifische Modulanforderungen anpasst.
- `uecookie/views/js/scripts.js`:
  - **Umfang:** Front-Office.
  - **Zweck:** Dieses Skript verarbeitet die clientseitige Logik für die Cookie-Benachrichtigungsleiste.
    - **Event-Listener:** Hört wahrscheinlich auf ein Klickereignis auf der Schaltfläche „Ich verstehe“.
    - **DOM-Manipulation:** Blendet das Cookie-Leisten-Element nach dem Schließen aus dem DOM aus.
    - **Cookie-Verwaltung:** Setzt ein Browser-Cookie (z. B. `uecookie_accepted`) mit einem Ablaufdatum (bestimmt durch die Einstellung „Cookie-Ablauf“), um zu verhindern, dass die Leiste für die angegebene Dauer erneut angezeigt wird.
    - **Erstprüfung:** Beim Laden der Seite wird das Vorhandensein des `uecookie_accepted`-Cookies überprüft, um zu bestimmen, ob die Leiste angezeigt werden soll oder nicht.

### 4.5 CSS-Stylesheets (`views/css/`)

- Dieses Modul enthält **keine** benutzerdefinierten CSS-Dateien in `views/css/`. Das Styling für die Cookie-Leiste ist wahrscheinlich inline oder wird dynamisch basierend auf den Farbeinstellungen generiert oder basiert auf minimalen Standard-Browserstilen. Entwickler, die das Erscheinungsbild weiter anpassen möchten, müssten die HTML-Struktur, die von `top.tpl` ausgegeben wird, mithilfe des benutzerdefinierten CSS ihres Themas ansprechen.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

- **Hook-Vorlagen (`views/templates/hook/`)**:
  - `uecookie/top.tpl`:
    - **Hook:** Diese Vorlage ist hauptsächlich dafür konzipiert, in einem Front-Office-Hook wie `displayHeader`, `displayFooter`, `displayTop` oder `displayBeforeBodyClosingTag` gerendert zu werden. Die `hookDisplayHeader`-Methode des Moduls ist typischerweise für die Registrierung und das Rendern dieser Vorlage verantwortlich.
    - **Ausgabe:** Sie gibt die HTML-Struktur für die Cookie-Benachrichtigungsleiste aus, einschließlich des anpassbaren Textes, der Schaltfläche und des dynamischen Stylings basierend auf den Konfigurationseinstellungen des Moduls (Hintergrundfarbe, Textfarbe usw.). Sie enthält auch das notwendige JavaScript (`scripts.js`), um das Schließen und Setzen von Cookies zu handhaben.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen.
  - Alle Konfigurationseinstellungen werden in der Tabelle `ps_configuration` gespeichert. Wichtige Konfigurationseinträge wären:
    - `UECOOKIE_ENABLED` (boolean)
    - `UECOOKIE_TEXT` (mehrsprachiger String)
    - `UECOOKIE_BUTTON_TEXT` (mehrsprachiger String)
    - `UECOOKIE_POSITION` (String: ‘top’ oder ‘bottom’)
    - `UECOOKIE_BG_COLOR` (String: Hex-Farbcode)
    - `UECOOKIE_TEXT_COLOR` (String: Hex-Farbcode)
    - `UECOOKIE_LINK_COLOR` (String: Hex-Farbcode)
    - `UECOOKIE_BUTTON_BG_COLOR` (String: Hex-Farbcode)
    - `UECOOKIE_BUTTON_TEXT_COLOR` (String: Hex-Farbcode)
    - `UECOOKIE_EXPIRATION` (Integer: Tage)
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Wird im `<head>`-Abschnitt jeder Front-Office-Seite ausgeführt. | Wird verwendet, um die CSS- (falls vorhanden) und JavaScript-Dateien des Moduls sowie potenziell die anfängliche HTML-Struktur der Cookie-Leiste, falls oben positioniert, einzufügen. |
| `displayFooter` | Wird am Ende jeder Front-Office-Seite, vor dem schließenden `</body>`-Tag, ausgeführt. | Kann verwendet werden, um die Cookie-Leisten-HTML und JavaScript einzufügen, insbesondere wenn sie unten positioniert ist. |
| `displayTop` | Wird im Header-Abschnitt des Themas, typischerweise über dem Hauptinhalt, ausgeführt. | Alternativer Hook zum Anzeigen der Cookie-Leiste oben. |
| `displayBeforeBodyClosingTag` | Wird direkt vor dem `</body>`-Tag ausgeführt. | Ein robuster Hook zum Einfügen von JavaScript- und HTML-Elementen, die ganz am Ende der Seite erscheinen sollen. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „EU-Cookie-Gesetz“ verweisen wir auf Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.
