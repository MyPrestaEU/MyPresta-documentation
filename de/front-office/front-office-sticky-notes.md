---
title: "Front office Sticky Notes - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Front office Sticky Notes von MyPresta.eu."
sidebar:
  label: "Front office Sticky Notes - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Front office Sticky Notes auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/front-office-sticky-notes.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/front-office-sticky-notes/)
>
> ---


# Front office Sticky Notes

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst erforderlich und in jeder modernen Hosting-Umgebung verfügbar.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zur Hauptkonfigurationsseite des Moduls Front office Sticky Notes. Hier verwalten Sie alle Ihre Haftnotizen.

Die Konfigurationsseite zeigt eine Liste aller von Ihnen erstellten Haftnotizen an. Von hier aus können Sie:

- **Neue Haftnotiz hinzufügen:** Klicken Sie auf eine Schaltfläche (normalerweise „Neu hinzufügen“ oder ein Plus-Symbol), um eine neue Notiz zu erstellen.
- **Bestehende Haftnotiz bearbeiten:** Klicken Sie auf ein „Bearbeiten“-Symbol neben einer Notiz in der Liste, um deren Einstellungen zu ändern.
- **Haftnotiz löschen:** Klicken Sie auf ein „Löschen“-Symbol neben einer Notiz, um sie aus Ihrem Shop zu entfernen.

Beim Hinzufügen oder Bearbeiten einer Haftnotiz sehen Sie typischerweise ein Formular mit den folgenden Einstellungen:

- **Notizinhalt (Text):**

  - **Was diese Einstellung bewirkt:** Dies ist die eigentliche Nachricht oder der Text, der in Ihrer Haftnotiz erscheint. Sie können grundlegende HTML-Tags (wie `<b>` für fett, `<i>` für kursiv, `<br>` für Zeilenumbrüche oder `<a>` für Links) verwenden, um Ihren Text zu formatieren und anklickbare Links einzufügen.
  - **Auswirkung der Änderung dieser Einstellung:** Der hier eingegebene Text wird Ihren Kunden angezeigt.
  - **Empfohlener Wert:** Halten Sie ihn prägnant und wirkungsvoll. Zum Beispiel: „Begrenzter Lagerbestand!“, „Neuheiten!“, „Kostenloser Versand ab 75 €!“.
  - **Händlerszenario / Beispiel:** Sie möchten einen Flash Sale ankündigen. Sie würden eingeben: `<b>Flash Sale!</b> 20% Rabatt auf alle Kleider! <a href="/20-off-dresses">Jetzt shoppen!</a>`
- **Notizfarbe (Hintergrundfarbe):**

  - **Was diese Einstellung bewirkt:** Hier können Sie die Hintergrundfarbe Ihrer Haftnotiz auswählen. Ein Farbwähler-Tool wird normalerweise zur einfachen Auswahl bereitgestellt.
  - **Auswirkung der Änderung dieser Einstellung:** Die Haftnotiz erscheint mit der gewählten Hintergrundfarbe. Dies ist entscheidend, um sie hervorzuheben oder an Ihre Marke anzupassen.
  - **Empfohlener Wert:** Wählen Sie eine Farbe, die gut mit dem Hintergrund Ihres Shops und der Textfarbe kontrastiert, um die Notiz leicht lesbar und auffällig zu machen. Helle, warme Farben (Gelb, Orange, Hellgrün) wirken oft gut, um Aufmerksamkeit zu erregen.
  - **Händlerszenario / Beispiel:** Für eine Warnmeldung könnten Sie ein helles Rot oder Orange wählen. Für eine allgemeine Ankündigung ein klassisches Gelb oder Hellblau.
- **Textfarbe:**

  - **Was diese Einstellung bewirkt:** Dies legt die Farbe des Textes in Ihrer Haftnotiz fest.
  - **Auswirkung der Änderung dieser Einstellung:** Der Text wird in der ausgewählten Farbe angezeigt.
  - **Empfohlener Wert:** Wählen Sie immer eine Farbe, die einen hohen Kontrast zur gewählten Hintergrundfarbe bietet, um eine optimale Lesbarkeit zu gewährleisten. Schwarz oder Dunkelgrau auf hellem Hintergrund oder Weiß auf dunklem Hintergrund sind in der Regel am besten.
  - **Händlerszenario / Beispiel:** Wenn der Hintergrund Ihrer Notiz gelb ist, würden Sie Schwarz oder Dunkelgrau für den Text wählen. Wenn der Hintergrund dunkelblau ist, wäre weißer Text ideal.
- **Position (X-Koordinate / Linker Versatz):**

  - **Was diese Einstellung bewirkt:** Dies bestimmt die horizontale Position der Haftnotiz auf der Seite, gemessen vom linken Rand des Bildschirms oder ihres übergeordneten Containers. Sie wird normalerweise in Pixeln (px) angegeben.
  - **Auswirkung der Änderung dieser Einstellung:** Ein höherer Wert verschiebt die Notiz weiter nach rechts. Ein niedrigerer Wert verschiebt sie näher nach links.
  - **Empfohlener Wert:** Experimentieren Sie, um eine Position zu finden, die wichtige Inhalte nicht verdeckt, aber dennoch sichtbar ist. Beginnen Sie mit Werten wie `20px` oder `50px` und passen Sie sie an.
  - **Händlerszenario / Beispiel:** Sie möchten, dass eine Notiz leicht rechts von Ihrem Hauptlogo im Header erscheint. Sie könnten dies auf `200px` einstellen.
- **Position (Y-Koordinate / Oberer Versatz):**

  - **Was diese Einstellung bewirkt:** Dies bestimmt die vertikale Position der Haftnotiz auf der Seite, gemessen vom oberen Rand des Bildschirms oder ihres übergeordneten Containers. Sie wird normalerweise in Pixeln (px) angegeben.
  - **Auswirkung der Änderung dieser Einstellung:** Ein höherer Wert verschiebt die Notiz weiter nach unten auf der Seite. Ein niedrigerer Wert verschiebt sie näher nach oben.
  - **Empfohlener Wert:** Überlegen Sie, wo die Notiz am effektivsten ist, ohne aufdringlich zu wirken. Für Header-Nachrichten könnte ein kleiner Wert wie `10px` oder `20px` funktionieren. Für Notizen auf Produktseiten müssen Sie möglicherweise nach unten scrollen, um den Effekt zu sehen.
  - **Händlerszenario / Beispiel:** Sie möchten, dass eine Notiz direkt unter Ihrer Hauptnavigationsleiste erscheint. Sie könnten dies auf `100px` einstellen.
- **Breite:**

  - **Was diese Einstellung bewirkt:** Dies steuert die Breite des Haftnotiz-Containers. Sie wird normalerweise in Pixeln (px) angegeben.
  - **Auswirkung der Änderung dieser Einstellung:** Eine größere Breite ermöglicht mehr Text in einer einzelnen Zeile, während eine kleinere Breite dazu führt, dass der Text häufiger umbrochen wird.
  - **Empfohlener Wert:** Wählen Sie eine Breite, die Ihre Nachricht bequem aufnimmt, ohne übermäßig groß oder zu schmal zu sein. `200px` bis `300px` ist ein üblicher Bereich.
  - **Händlerszenario / Beispiel:** Wenn Ihre Nachricht kurz ist, könnten `200px` ausreichen. Wenn es sich um einen etwas längeren Satz handelt, könnten `280px` besser sein.
- **Höhe:**

  - **Was diese Einstellung bewirkt:** Dies steuert die Höhe des Haftnotiz-Containers. Sie wird normalerweise in Pixeln (px) angegeben.
  - **Auswirkung der Änderung dieser Einstellung:** Eine größere Höhe ermöglicht mehr Textzeilen. Wenn der Text die Höhe überschreitet, kann er abgeschnitten werden oder überlaufen, abhängig vom CSS Ihres Themes.
  - **Empfohlener Wert:** Oft können Sie dies leer lassen oder auf `auto` setzen, wenn das Modul dies unterstützt, damit sich die Höhe an den Inhalt anpasst. Wenn Sie eine feste Größe benötigen, ist `100px` bis `150px` ein üblicher Bereich.
  - **Händlerszenario / Beispiel:** Wenn Sie eine mehrzeilige Nachricht haben, müssen Sie möglicherweise die Höhe erhöhen, um sicherzustellen, dass der gesamte Text sichtbar ist.
- **Rotation (Winkel):**

  - **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, die Haftnotiz um einen bestimmten Grad zu drehen, um ihr ein natürlicheres „angeklebtes“ Aussehen zu verleihen.
  - **Auswirkung der Änderung dieser Einstellung:** Die Notiz erscheint um den angegebenen Winkel geneigt. Positive Werte drehen im Uhrzeigersinn, negative Werte gegen den Uhrzeigersinn.
  - **Empfohlener Wert:** Kleine Rotationen wie `3deg`, `-5deg` oder `7deg` sehen oft am besten aus und bieten einen subtilen, realistischen Effekt, ohne den Text schwer lesbar zu machen.
  - **Händlerszenario / Beispiel:** Um eine Notiz so aussehen zu lassen, als wäre sie beiläufig auf die Seite geklebt, könnten Sie dies auf `5deg` einstellen.
- **Z-Index:**

  - **Was diese Einstellung bewirkt:** Diese CSS-Eigenschaft bestimmt die Stapelreihenfolge von Elementen. Ein Element mit einem höheren Z-Index-Wert wird vor Elementen mit niedrigeren Werten platziert.
  - **Auswirkung der Änderung dieser Einstellung:** Wenn Ihre Haftnotiz hinter anderen Elementen (wie Pop-ups, Menüs oder Bannern) erscheint, wird sie durch Erhöhen ihres Z-Index in den Vordergrund gebracht.
  - **Empfohlener Wert:** Beginnen Sie mit einem relativ hohen Wert wie `999` oder `9999`. Wenn sie immer noch ausgeblendet ist, erhöhen Sie sie weiter.
  - **Händlerszenario / Beispiel:** Ihre Haftnotiz ist hinter einem Cookie-Zustimmungsbanner versteckt. Sie würden ihren Z-Index auf `9999` erhöhen, um sicherzustellen, dass sie immer oben liegt.
- **Aktiv / Aktiviert:**

  - **Was diese Einstellung bewirkt:** Dies ist ein einfacher Umschalter (Ja/Nein-Schalter), um die Haftnotiz zu aktivieren oder zu deaktivieren, ohne sie zu löschen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Haftnotiz ist in Ihrem Front Office gemäß ihren anderen Einstellungen sichtbar.
    - *Wenn deaktiviert:* Die Haftnotiz wird in Ihrem Front Office ausgeblendet, aber ihre Konfiguration wird gespeichert, sodass Sie sie später wieder aktivieren können.
  - **Empfohlener Wert:** „Ja“, wenn die Notiz sichtbar sein soll; „Nein“, wenn Sie sie vorübergehend ausblenden möchten.
  - **Händlerszenario / Beispiel:** Sie haben eine Notiz für eine saisonale Aktion. Sie können sie nach Saisonende deaktivieren und im nächsten Jahr wieder aktivieren, ohne sie neu erstellen zu müssen.

#### 2.1.1 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Notizinhalt (Text) | Variiert | Die auf der Haftnotiz angezeigte Nachricht. Unterstützt grundlegendes HTML. |
| Modulkonfiguration | Notizfarbe (Hintergrund) | Variiert (z. B. Gelb) | Legt die Hintergrundfarbe der Notiz fest. Für Kontrast wählen. |
| Modulkonfiguration | Textfarbe | Variiert (z. B. Schwarz) | Legt die Farbe des Textes fest. Hohen Kontrast zum Hintergrund sicherstellen. |
| Modulkonfiguration | Position (X-Koordinate) | Variiert (z. B. 50px) | Horizontale Position von links. Für Platzierung anpassen. |
| Modulkonfiguration | Position (Y-Koordinate) | Variiert (z. B. 50px) | Vertikale Position von oben. Für Platzierung anpassen. |
| Modulkonfiguration | Breite | Variiert (z. B. 250px) | Breite der Haftnotiz. Beeinflusst den Textumbruch. |
| Modulkonfiguration | Höhe | Variiert (z. B. auto oder 120px) | Höhe der Haftnotiz. Beeinflusst die Sichtbarkeit des Inhalts. |
| Modulkonfiguration | Rotation (Winkel) | Variiert (z. B. 5deg) | Neigt die Notiz für einen realistischen „angeklebten“ Effekt. |
| Modulkonfiguration | Z-Index | Variiert (z. B. 9999) | Stapelreihenfolge. Höhere Werte erscheinen über anderen Elementen. |
| Modulkonfiguration | Aktiv / Aktiviert | Ja | Schaltet die Sichtbarkeit der Haftnotiz im Front Office um. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Haftnotiz wird im Front Office nicht angezeigt.**
A:

1.  **Status „Aktiv“ prüfen:** Gehen Sie zur Modulkonfiguration und stellen Sie sicher, dass der Schalter „Aktiv“ für diese spezifische Notiz auf „Ja“ steht.
2.  **Cache leeren:** PrestaShop speichert Inhalte oft im Cache. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“.
3.  **Z-Index:** Wenn der Z-Index der Notiz zu niedrig ist, könnte sie hinter anderen Elementen verborgen sein. Versuchen Sie, den Z-Index-Wert zu erhöhen (z. B. auf `9999`).
4.  **Positionierung:** Überprüfen Sie die X- und Y-Koordinaten. Wenn sie sehr hoch sind, könnte die Notiz außerhalb des Bildschirms liegen. Versuchen Sie, kleine Werte wie `10px` für beide einzustellen, um zu sehen, ob sie erscheint.
5.  **Modulinstallation:** Stellen Sie sicher, dass das Modul korrekt installiert und in **Module > Modul-Manager** aktiviert ist.

**F: Mein Haftnotiztext ist abgeschnitten oder läuft über.**
A:

1.  **Breite/Höhe anpassen:** Erhöhen Sie die Einstellungen für „Breite“ und/oder „Höhe“ für diese spezifische Haftnotiz in der Modulkonfiguration.
2.  **HTML prüfen:** Wenn Sie HTML verwenden, stellen Sie sicher, dass alle Tags korrekt geschlossen sind (z. B. `<b>` hat ein entsprechendes `</b>`). Falsches HTML kann manchmal die Darstellung stören.

**F: Die Haftnotiz sieht auf Mobilgeräten anders aus als auf dem Desktop.**
A: Das Modul strebt Responsivität an, aber die genaue Platzierung kann aufgrund unterschiedlicher Bildschirmgrößen und des CSS Ihres Themes variieren.

1.  **Auf dem Gerät testen:** Testen Sie das Aussehen der Notiz immer auf tatsächlichen Mobilgeräten oder verwenden Sie die Entwicklertools Ihres Browsers (F12), um mobile Ansichten zu simulieren.
2.  **Positionierung anpassen:** Möglicherweise müssen Sie die X- und Y-Koordinaten für die mobil-spezifische Platzierung anpassen, obwohl das Modul möglicherweise keine separaten mobilen Einstellungen bietet. Wenn es ein größeres Problem ist, überlegen Sie, ob die Notiz auf Mobilgeräten wirklich unerlässlich ist oder ob ein anderer Ansatz erforderlich ist.
3.  **Theme-Konflikte:** Gelegentlich kann das CSS Ihres Themes Konflikte verursachen. Wenn Sie dies vermuten, wenden Sie sich mit Details zu Ihrem Theme an den MyPresta.eu-Support.

**F: Wie mache ich den Text zu einem Link?**
A: Sie können Standard-HTML-Anker-Tags im Feld „Notizinhalt“ verwenden.
Beispiel: `<a href="https://ihrshop.com/neue-produkte">Klicken Sie hier für Neuheiten!</a>`
Denken Sie daran, die vollständige URL, einschließlich `https://`, anzugeben.

**F: Kann ich verschiedene Haftnotizen für verschiedene Sprachen haben?**
A: Ja, das Modul unterstützt die Mehrsprachigkeitsfunktionen von PrestaShop. Beim Bearbeiten einer Haftnotiz sollten Sie Sprachregisterkarten neben dem Feld „Notizinhalt“ (und möglicherweise anderen textbasierten Feldern) sehen. Wählen Sie die gewünschte Sprachregisterkarte aus und geben Sie den übersetzten Inhalt für diese Notiz ein.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Übersicht)

Dieser Abschnitt bietet einen technischen Überblick für Entwickler und Webmaster, die das Modul „Front office Sticky Notes“ verstehen, anpassen oder debuggen möchten.

### 4.1 Architekturübersicht

Das Modul „Front office Sticky Notes“ folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich die `Module`-Klasse für ihre Kernfunktionalität und `ModuleFrontController` für AJAX-Interaktionen nutzt. Es speichert Konfigurationsdaten direkt in `ps_configuration` und rendert seinen Inhalt über ein Smarty-Template, das in das Front Office eingehängt ist. Das Modul verwendet clientseitiges JavaScript für dynamisches Verhalten und eine dedizierte CSS-Datei für die Gestaltung.

### 4.2 Controller (`controllers/`)

Das Modul verwendet Front-Controller, um AJAX-Anfragen im Zusammenhang mit der Verwaltung von Haftnotizen (Hinzufügen, Bearbeiten, Löschen) zu verarbeiten. Dies sind keine vollständigen Seiten-Controller, sondern Endpunkte für dynamische Interaktionen.

- **Front-Office-Controller**:

  - `controllers/front/add.php`
    - **Klassenname & Elternklasse**: `StickynotesfoAddModuleFrontController` erweitert `ModuleFrontController`
    - **Verantwortlichkeit**: Verarbeitet AJAX-Anfragen zum Hinzufügen einer neuen Haftnotiz. Es empfängt wahrscheinlich POST-Daten mit Notizinhalt, Position, Farben usw., validiert diese und speichert sie in der Datenbank (über die `Configuration`-Klasse oder ein benutzerdefiniertes `ObjectModel`, falls vorhanden). Gibt eine JSON-Antwort zurück, die den Erfolg oder Misserfolg anzeigt.
  - `controllers/front/delete.php`
    - **Klassenname & Elternklasse**: `StickynotesfoDeleteModuleFrontController` erweitert `ModuleFrontController`
    - **Verantwortlichkeit**: Verarbeitet AJAX-Anfragen zum Löschen einer vorhandenen Haftnotiz. Es erwartet einen Bezeichner (z. B. `id_note`) in der Anfrage, entfernt die entsprechenden Daten aus der Datenbank und gibt eine JSON-Antwort zurück.
  - `controllers/front/edit.php`
    - **Klassenname & Elternklasse**: `StickynotesfoEditModuleFrontController` erweitert `ModuleFrontController`
    - **Verantwortlichkeit**: Verarbeitet AJAX-Anfragen zum Aktualisieren einer vorhandenen Haftnotiz. Es empfängt POST-Daten mit der ID der Notiz und aktualisierten Eigenschaften, ändert den Datenbankeintrag und gibt eine JSON-Antwort zurück.
  - `controllers/front/index.php`
    - **Klassenname & Elternklasse**: `StickynotesfoIndexModuleFrontController` erweitert `ModuleFrontController`
    - **Verantwortlichkeit**: Dieser Controller könnte als allgemeiner Einstiegspunkt für AJAX-Anfragen dienen oder ein Fallback sein. Angesichts der spezifischen `add`-, `delete`-, `edit`-Controller könnte `index.php` das Auflisten von Notizen oder andere allgemeine Interaktionen behandeln, die nicht von den spezifischen CRUD-Operationen abgedeckt werden.
- **Back-Office-Admin-Controller**: Keine erkannt. Die gesamte Back-Office-Konfiguration wird innerhalb der `getContent()`-Methode der Hauptmoduldatei behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Es wurden keine benutzerdefinierten `classes/` oder `ObjectModel`-Definitionen erkannt. Das Modul speichert seine Konfiguration wahrscheinlich direkt in der PrestaShop-Tabelle `ps_configuration` und verwendet eindeutige Schlüssel für die Eigenschaften jeder Haftnotiz. Dieser Ansatz ist üblich für einfachere Module, die eine begrenzte Anzahl von Einstellungen verwalten.

### 4.4 JavaScript-Assets (`views/js/`)

- `js/advajax.js`
  - **Geltungsbereich**: Wahrscheinlich Front-Office.
  - **Beschreibung**: Diese Datei deutet auf ein benutzerdefiniertes oder Drittanbieter-AJAX-Dienstprogramm-Skript hin. Es bietet wahrscheinlich Hilfsfunktionen zum Senden asynchroner Anfragen an die Front-Controller des Moduls (`add.php`, `delete.php`, `edit.php`). Es könnte gängige AJAX-Muster, Fehlerbehandlung oder Daten-Serialisierung kapseln. Entwickler sollten diese Datei überprüfen, um zu verstehen, wie AJAX-Aufrufe innerhalb des Moduls strukturiert und initiiert werden.
- `js/jscolor/jscolor.js`
  - **Geltungsbereich**: Back-Office (für die Konfiguration).
  - **Beschreibung**: Dies ist eine JavaScript-Bibliothek eines Drittanbieters für einen Farbwähler. Sie wird im Back-Office-Konfigurationsformular des Moduls verwendet, um eine benutzerfreundliche Oberfläche zur Auswahl von Notiz- und Textfarben bereitzustellen. Sie bindet sich an Eingabefelder einer bestimmten Klasse oder ID und verwandelt diese in interaktive Farbauswahlwerkzeuge.

### 4.5 CSS-Stylesheets (`views/css/`)

- `css/stickynotes.css`
  - **Geltungsbereich**: Front-Office-Kunden-Styling.
  - **Beschreibung**: Dies ist das primäre Stylesheet für die im Front Office angezeigten Haftnotizen. Es definiert das visuelle Erscheinungsbild der Notizen, einschließlich:
    - Basis-Styling für den Haftnotiz-Container (z. B. `position: absolute;`, `background-color`, `border-radius`).
    - Text-Styling innerhalb der Notiz (`font-size`, `color`, `line-height`).
    - Der „abgezogene“ oder gedrehte Effekt (wahrscheinlich unter Verwendung von `transform: rotate()`).
    - `z-index` zur Sicherstellung der Sichtbarkeit.
    - Potenzielle responsive Anpassungen für verschiedene Bildschirmgrößen mithilfe von Media Queries.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können**: Entwickler sollten das gerenderte HTML überprüfen, um die Hauptcontainerklasse (z. B. `.sticky-note`, `.stickynotesfo-item`) und ihre Kindelemente zu identifizieren, um benutzerdefiniertes Styling in der `custom.css` oder `theme.css` ihres Themes anzuwenden.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/front/`)**:
  - `views/templates/front/sticky-notes-front-office.tpl`
    - **Hook**: Dieses Template wird wahrscheinlich in einem allgemeinen Front-Office-Hook wie `displayHeader`, `displayFooter` oder möglicherweise `displayBeforeBodyClosingTag` gerendert. Die Methode `hookDisplayHeader` oder `hookDisplayFooter` des Moduls würde typischerweise alle aktiven Haftnotizen aus der Datenbank abrufen und sie diesem Template zuweisen.
    - **Visuelle Blockausgabe**: Dieses Template ist dafür verantwortlich, die Liste der aktiven Haftnotizen zu durchlaufen und die HTML-Struktur für jede einzelne zu rendern. Es fügt den Inhalt, die Farben, Positionen, Breite, Höhe, Rotation und den Z-Index der Notiz dynamisch als Inline-Styles oder Datenattribute ein, die dann von `stickynotes.css` und möglicherweise `advajax.js` für dynamische Updates übernommen werden. Jede Notiz wird wahrscheinlich ein `div`-Element mit eindeutigen IDs oder Klassen sein.

### 4.7 Datenbankschema & Hooks-Übersicht

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen. Stattdessen speichert es seine Konfigurationsdaten in der PrestaShop-Tabelle `ps_configuration`. Die Eigenschaften jeder Haftnotiz (Inhalt, Farbe, Position usw.) werden als einzelne Konfigurationsschlüssel gespeichert, wahrscheinlich mit dem Präfix `STICKYNOTESFO_NOTE_` gefolgt von einem eindeutigen Bezeichner (z. B. `STICKYNOTESFO_NOTE_1_CONTENT`, `STICKYNOTESFO_NOTE_1_COLOR`). Mehrsprachige Felder würden `_LANG_ID`-Suffixe verwenden.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Wird am Ende des `<head>`-Abschnitts jeder Front-Office-Seite ausgeführt. | Ideal zum Einfügen von CSS, JavaScript und möglicherweise der anfänglichen HTML-Struktur der Haftnotizen, um sicherzustellen, dass sie frühzeitig im DOM verfügbar sind. |
| `displayFooter` | Wird am Ende des `<body>`-Abschnitts jeder Front-Office-Seite ausgeführt. | Kann verwendet werden, um den HTML-Code der Haftnotizen einzufügen, insbesondere wenn sie schwebend oder absolut relativ zum Viewport positioniert werden sollen. |
| `displayLeftColumn` | Wird innerhalb der linken Spalte von Seiten ausgeführt, die eine haben. | Ermöglicht die Platzierung von Haftnotizen speziell in der linken Seitenleiste. |
| `displayRightColumn` | Wird innerhalb der rechten Spalte von Seiten ausgeführt, die eine haben. | Ermöglicht die Platzierung von Haftnotizen speziell in der rechten Seitenleiste. |
| `displayProductAdditionalInfo` (oder ähnlicher Produktseiten-Hook) | Wird auf der Produktseite ausgeführt, typischerweise in der Nähe der Produktbeschreibung oder des In-den-Warenkorb-Buttons. | Ermöglicht die Platzierung von Haftnotizen, die spezifisch für einzelne Produktseiten sind. |
| `actionFrontControllerSetMedia` | Wird ausgeführt, wenn ein Front-Controller seine Medien (CSS/JS) einstellt. | Wird vom Modul verwendet, um seine `stickynotes.css`- und `advajax.js`-Dateien für die Front-Office-Anzeige zu registrieren. |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin-Controller seine Medien (CSS/JS) einstellt. | Wird vom Modul verwendet, um `jscolor.js` und alle anderen admin-spezifischen CSS/JS für seine Konfigurationsseite zu registrieren. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und weitere Unterstützung zum Modul „Front office Sticky Notes“ wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, zeitnahen Support zu leisten und sicherzustellen, dass Ihr Modul optimal funktioniert.
