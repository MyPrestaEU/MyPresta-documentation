---
title: "Produkte Notizblock - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Produkte Notizblock von MyPresta.eu."
sidebar:
  label: "Produkte Notizblock - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Products Notepad auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/products-notepad.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/products-notepad/)
>
> ---


# Produkte Notizblock

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für den allgemeinen PrestaShop-Betrieb erforderlich. Für dieses Modul sind keine spezifischen zusätzlichen Erweiterungen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation im Modul-Manager neben dem Modul „Produkte Notizblock“ auf „Konfigurieren“. Dies führt Sie zum Hauptkonfigurationsbildschirm.

#### Allgemeine Einstellungen

- **Was diese Einstellung bewirkt:** Dieser Abschnitt steuert das Kernverhalten und die Anzeige des Moduls Produkte Notizblock in Ihrem Shop.

  - **Produkte im Notizblock merken:**

    - **Was diese Einstellung bewirkt:** Bestimmt, ob die Produkte, die ein Kunde seinem Notizblock hinzufügt, über verschiedene Browsing-Sitzungen hinweg gespeichert werden oder ob der Notizblock geleert wird, wenn der Kunde seinen Browser schließt.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn aktiviert (JA):* Produkte, die dem Notizblock hinzugefügt wurden, bleiben erhalten, auch wenn der Kunde Ihre Website verlässt und später zurückkehrt (z. B. am nächsten Tag). Hierfür werden Browser-Cookies verwendet, um den Inhalt des Notizblocks zu speichern.
      - *Wenn deaktiviert (NEIN):* Der Notizblock wird geleert, wenn der Kunde seinen Browser schließt oder seine Cookies löscht. Jede neue Sitzung beginnt mit einem leeren Notizblock.
    - **Empfohlener Wert:** **JA**. Dies bietet ein viel besseres Kundenerlebnis, da Kunden eine Liste über die Zeit aufbauen können, ohne ihren Fortschritt zu verlieren.
    - **Händlerszenario / Beispiel:** Ein Kunde fügt am Montag mehrere Artikel zu seinem Notizblock hinzu. Wenn „Produkte merken“ auf JA steht, kann er am Mittwoch zurückkehren und seine Liste intakt vorfinden. Wenn NEIN, wäre die Liste leer.
  - **Anzahl der Produkte im Notizblock begrenzen:**

    - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, eine maximale Anzahl von Produkten festzulegen, die ein Kunde in seinem Notizblock speichern kann.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn aktiviert (JA):* Der Notizblock erlaubt nur eine bestimmte Anzahl von Produkten. Sobald das Limit erreicht ist, können Kunden keine weiteren Produkte hinzufügen, bis sie bestehende entfernen.
      - *Wenn deaktiviert (NEIN):* Kunden können eine unbegrenzte Anzahl von Produkten zu ihrem Notizblock hinzufügen.
    - **Empfohlener Wert:** **NEIN** (es sei denn, Sie haben einen spezifischen Grund, dies zu begrenzen, wie z. B. Leistungsprobleme bei extrem langen Listen). Eine unbegrenzte Anzahl von Artikeln gibt Kunden maximale Flexibilität.
    - **Händlerszenario / Beispiel:** Wenn Sie dies aktivieren und das Limit auf 10 setzen, erhält ein Kunde, der versucht, ein 11. Produkt hinzuzufügen, eine Meldung, dass der Notizblock voll ist.
  - **Limit-Wert:** (Erscheint nur, wenn „Anzahl der Produkte im Notizblock begrenzen“ auf JA gesetzt ist)

    - **Was diese Einstellung bewirkt:** Gibt die genaue maximale Anzahl der im Notizblock erlaubten Produkte an.
    - **Auswirkung der Änderung dieser Einstellung:** Legt die numerische Obergrenze für den Notizblock fest.
    - **Empfohlener Wert:** Wenn Sie sich für eine Begrenzung entscheiden, ist eine vernünftige Zahl wie **20-50** oft ausreichend, um die Flexibilität des Kunden mit potenziellen Leistungsproblemen in Einklang zu bringen.
    - **Händlerszenario / Beispiel:** Wenn „Anzahl der Produkte begrenzen“ auf JA und „Limit-Wert“ auf 25 steht, können Kunden bis zu 25 Produkte speichern.

#### Anzeigeeinstellungen

- **Was diese Einstellung bewirkt:** Dieser Abschnitt steuert, wo der Notizblock-Block im Front Office Ihres Shops erscheint.

  - **In linker Spalte anzeigen:**

    - **Was diese Einstellung bewirkt:** Steuert, ob der Notizblock-Zusammenfassungsblock in der linken Spalte Ihres Shops angezeigt wird.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn aktiviert (JA):* Der Notizblock-Block erscheint in der linken Spalte auf Seiten, die eine linke Spalte haben (z. B. Kategorieseiten, Produktseiten, CMS-Seiten).
      - *Wenn deaktiviert (NEIN):* Der Notizblock-Block wird nicht in der linken Spalte angezeigt.
    - **Empfohlener Wert:** **JA** (oder rechte Spalte), da Spalten ein üblicher Ort für solche Utility-Blöcke sind.
    - **Händlerszenario / Beispiel:** Ein Kunde, der eine Kategorieseite durchsucht, sieht seine Notizblock-Zusammenfassung in der linken Seitenleiste, wodurch sie leicht zugänglich ist.
  - **In rechter Spalte anzeigen:**

    - **Was diese Einstellung bewirkt:** Steuert, ob der Notizblock-Zusammenfassungsblock in der rechten Spalte Ihres Shops angezeigt wird.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn aktiviert (JA):* Der Notizblock-Block erscheint in der rechten Spalte auf Seiten, die eine rechte Spalte haben.
      - *Wenn deaktiviert (NEIN):* Der Notizblock-Block wird nicht in der rechten Spalte angezeigt.
    - **Empfohlener Wert:** **JA** (oder linke Spalte). Wählen Sie eine oder beide basierend auf dem Layout Ihres Themes und anderen Modulen, die Sie haben.
    - **Händlerszenario / Beispiel:** Wenn Ihr Theme die rechte Spalte für Werbeaktionen verwendet, könnten Sie den Notizblock dort platzieren, um die linke Spalte für die Navigation freizuhalten.
  - **Im Footer anzeigen:**

    - **Was diese Einstellung bewirkt:** Steuert, ob der Notizblock-Zusammenfassungsblock im Footer-Bereich Ihres Shops angezeigt wird.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn aktiviert (JA):* Der Notizblock-Block erscheint am unteren Rand jeder Seite, typischerweise als Teil des allgemeinen Footer-Inhalts.
      - *Wenn deaktiviert (NEIN):* Der Notizblock-Block wird nicht im Footer angezeigt.
    - **Empfohlener Wert:** **NEIN** (es sei denn, Ihr Theme hat einen sehr prominenten Footer-Bereich für Utility-Blöcke). Spalten sind für diese Art von Funktion im Allgemeinen besser sichtbar.
    - **Händlerszenario / Beispiel:** Wenn Ihr Footer bereits mit Links und rechtlichen Informationen überladen ist, könnte das Hinzufügen des Notizblocks dort dazu führen, dass er weniger auffällt.
  - **Im Header anzeigen:**

    - **Was diese Einstellung bewirkt:** Steuert, ob der Notizblock-Zusammenfassungsblock im Header-Bereich Ihres Shops angezeigt wird.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn aktiviert (JA):* Der Notizblock-Block erscheint oben auf jeder Seite, oft in der Nähe der Warenkorb- oder Kontolinks.
      - *Wenn deaktiviert (NEIN):* Der Notizblock-Block wird nicht im Header angezeigt.
    - **Empfohlener Wert:** **NEIN** (es sei denn, Ihr Theme bietet ausreichend Platz und ein spezifisches Design dafür). Header sind oft für kritische Navigation und den Warenkorb reserviert.
    - **Händlerszenario / Beispiel:** Ein kompaktes Symbol im Header könnte funktionieren, aber ein vollständiger Block könnte den Header überladen.
  - **Auf Produktseite anzeigen:**

    - **Was diese Einstellung bewirkt:** Steuert, ob der „Zum Notizblock hinzufügen“-Button und potenziell eine kleine Notizblock-Zusammenfassung direkt auf einzelnen Produktseiten angezeigt werden.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Wenn aktiviert (JA):* Kunden sehen den „Zum Notizblock hinzufügen“-Button auf jeder Produktseite, was das Speichern von Artikeln beim Browsen erleichtert.
      - *Wenn deaktiviert (NEIN):* Der „Zum Notizblock hinzufügen“-Button erscheint nicht auf Produktseiten, wodurch die Funktion weniger zugänglich wird.
    - **Empfohlener Wert:** **JA**. Dies ist eine entscheidende Platzierung, damit die Funktion effektiv ist.
    - **Händlerszenario / Beispiel:** Ein Kunde, der ein Produkt ansieht, kann es sofort seinem Notizblock hinzufügen, um es später mit anderen Produkten zu vergleichen.

#### Konfigurations-Schnellreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Produkte im Notizblock merken | JA | Speichert Notizblock-Artikel über Sitzungen hinweg für bessere UX. |
| Modulkonfiguration | Anzahl der Produkte im Notizblock begrenzen | NEIN | Ermöglicht unbegrenzte Produkte im Notizblock, maximiert die Kundenauswahl. |
| Modulkonfiguration | Limit-Wert | (N/A, wenn Limit NEIN ist) | Legt die maximale Anzahl der Produkte fest, wenn die Begrenzung aktiviert ist. |
| Modulkonfiguration | In linker Spalte anzeigen | JA | Zeigt die Notizblock-Zusammenfassung in der linken Seitenleiste an. |
| Modulkonfiguration | In rechter Spalte anzeigen | JA | Zeigt die Notizblock-Zusammenfassung in der rechten Seitenleiste an. |
| Modulkonfiguration | Im Footer anzeigen | NEIN | Vermeidet Überladen des Footers, weniger sichtbar. |
| Modulkonfiguration | Im Header anzeigen | NEIN | Vermeidet Überladen des Headers, weniger sichtbar. |
| Modulkonfiguration | Auf Produktseite anzeigen | JA | Wesentlich, damit Kunden Produkte einfach zum Notizblock hinzufügen können. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Der Notizblock wird in meinem Shop nicht angezeigt. Was soll ich tun?**
A1: Überprüfen Sie zunächst die Modulkonfiguration in Ihrem Back Office (**Module > Modul-Manager > Produkte Notizblock > Konfigurieren**). Stellen Sie sicher, dass mindestens eine Anzeigeoption (z. B. „In linker Spalte anzeigen“ oder „Auf Produktseite anzeigen“) auf JA gesetzt ist. Wenn es immer noch nicht angezeigt wird, versuchen Sie, Ihren PrestaShop-Cache zu leeren (**Erweiterte Einstellungen > Leistung > Cache leeren**). Manchmal können auch Theme-Konflikte die Anzeige von Modulen verhindern; wechseln Sie vorübergehend zum Standard-PrestaShop-Theme, um dies auszuschließen.

**F2: Produkte werden nach dem Schließen des Browsers durch einen Kunden nicht im Notizblock gespeichert.**
A2: Gehen Sie zur Modulkonfigurationsseite (**Module > Modul-Manager > Produkte Notizblock > Konfigurieren**) und stellen Sie sicher, dass die Einstellung „Produkte im Notizblock merken“ auf **JA** gesetzt ist. Diese Option verwendet Browser-Cookies, um den Notizblock-Inhalt zu speichern. Stellen Sie daher sicher, dass Kunden Cookies in ihrem Browser nicht deaktiviert haben.

**F3: Der „Zum Notizblock hinzufügen“-Button sieht seltsam aus oder ist auf meinen Produktseiten nicht richtig gestylt.**
A3: Dies ist oft ein CSS-Konflikt mit Ihrem benutzerdefinierten Theme. Das Modul bietet seine eigene grundlegende Formatierung, aber die Stile Ihres Themes könnten diese überschreiben. Sie können entweder:
1. Ihren Theme-Entwickler um Hilfe bitten.
2. Den PrestaShop Live Theme Editor (falls in Ihrer Version verfügbar) oder Browser-Entwicklertools (F12) verwenden, um den Button zu untersuchen und benutzerdefinierte CSS-Überschreibungen in der `custom.css`-Datei Ihres Themes anzuwenden.
3. Den MyPresta.eu-Support um Anleitung bitten.

**F4: Können Kunden ihren Notizblock mit anderen teilen?**
A4: Nein, dieses Modul ist für die individuelle Nutzung durch Kunden konzipiert und beinhaltet keine Freigabefunktion. Es ist eine persönliche Browsing-Hilfe, kein kollaborativer Wunschzettel.

**F5: Funktioniert der Notizblock mit mehrsprachigen Shops?**
A5: Ja, das Modul ist so konzipiert, dass es mit den mehrsprachigen Funktionen von PrestaShop kompatibel ist. Jeder vom Modul angezeigte Text (wie Button-Beschriftungen oder Blocktitel) kann über die PrestaShop-Übersetzungsoberfläche (**International > Übersetzungen > Übersetzungen installierter Module**) übersetzt werden.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul Produkte Notizblock ist ein Standard-PrestaShop-Modul, das einem MVC-ähnlichen Muster folgt. Es verwendet hauptsächlich Front-Controller für AJAX-Interaktionen und Rendering sowie Smarty-Templates für seine Front-Office-Anzeige. Es stützt sich auf Browser-Cookies für die Persistenz, wenn es so konfiguriert ist, dass Produkte gespeichert werden. Die Hauptlogik des Moduls befindet sich in `notepad.php` und den zugehörigen Front-Controllern.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `controllers/front/ajaxload.php`
    - **Klassenname & Elternklasse**: `NotepadAjaxloadModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit**: Dieser Controller verarbeitet alle AJAX-Anfragen im Zusammenhang mit der Notizblock-Funktionalität. Er ist verantwortlich für das Hinzufügen von Produkten zum Notizblock, deren Entfernung und potenziell die Aktualisierung der Notizblock-Anzeige. Er verarbeitet Daten, die über POST oder GET gesendet werden, und gibt JSON-Antworten an das Front-End-JavaScript zurück.
  - `controllers/front/index.php`
    - **Klassenname & Elternklasse**: `NotepadIndexModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit**: Dieser Controller dient wahrscheinlich als Fallback oder als dedizierte Seite für den Notizblock, wenn eine vollständige Seitenansicht implementiert ist. Angesichts der primären AJAX-Natur des Moduls könnte dies ein seltener genutzter Einstiegspunkt sein, der möglicherweise eine vollständige Notizblock-Ansicht umleitet oder rendert.
- **Back-Office-Admin-Controller**: Keine. Die gesamte Konfiguration wird über die `getContent()`-Methode des Hauptmoduls abgewickelt.

### 4.3 Kernklassen & Modelle (`classes/`)

In diesem Modul sind keine benutzerdefinierten `ObjectModel`-Klassen definiert. Produktdaten werden wahrscheinlich direkt in Browser-Cookies oder Session-Variablen gespeichert, die von der Hauptklasse des Moduls und den Front-Controllern abgerufen und verarbeitet werden.

### 4.4 JavaScript-Assets (`views/js/`)

- `admin.js`
  - **Umfang**: Back-Office.
  - **Beschreibung**: Dieses Skript verarbeitet wahrscheinlich Interaktionen auf der Konfigurationsseite des Moduls im PrestaShop Back Office. Es könnte die Sichtbarkeit von Einstellungen (z. B. `notepad_limit_value` basierend auf `notepad_limit`), Formularübermittlungen oder Validierungen verwalten.
- `jscolor.js`
  - **Umfang**: Back-Office (wahrscheinlich).
  - **Beschreibung**: Eine Drittanbieter-JavaScript-Bibliothek für Farbwähler. Wenn das Modul Optionen zur Farbanpassung für die Notizblock-Anzeige hätte, würde dieses Skript die Benutzeroberfläche zur Farbauswahl im Admin-Panel bereitstellen. (Basierend auf dem Inventar ist es vorhanden, könnte aber ein Überbleibsel oder für zukünftige Verwendung sein, wenn derzeit keine Farbeinstellungen verfügbar sind).
- `lib/searchTool/views/js/autocomplete.js`
  - **Umfang**: Front-Office (potenziell Back-Office, wenn für die Produktauswahl verwendet).
  - **Beschreibung**: Dieses Skript bietet eine Autocomplete-Funktionalität, wahrscheinlich für die Produktsuche. Wenn der Notizblock eine Funktion zum Hinzufügen von Produkten durch Suche hätte oder wenn es Teil einer breiteren „Suchwerkzeug“-Bibliothek ist, die mit dem Modul geliefert wird, würde dies die AJAX-Aufrufe und die Anzeige von Suchvorschlägen verwalten.
- `notepad.js`
  - **Umfang**: Front-Office.
  - **Beschreibung**: Dies ist das zentrale Front-Office-JavaScript für die Notizblock-Funktionalität.
    - **Event-Listener**: Bindet Klick-Events an „Zum Notizblock hinzufügen“-Buttons (z. B. auf Produktseiten, Produktlisten), „Aus Notizblock entfernen“-Links/Buttons innerhalb des Notizblock-Blocks und potenziell den Notizblock-Block-Header selbst, um dessen Sichtbarkeit umzuschalten oder zu einer vollständigen Ansicht zu navigieren.
    - **AJAX-Aufrufe**: Führt asynchrone Anfragen an `controllers/front/ajaxload.php` aus, um Notizblock-Inhalte hinzuzufügen, zu entfernen oder abzurufen.
    - **DOM-Manipulation**: Aktualisiert den Notizblock-Anzeigeblock (z. B. Produktanzahl, Produktliste), zeigt Erfolgs-/Fehlermeldungen an und rendert Produkteinträge dynamisch innerhalb des Notizblocks.
    - **Cookie-Verwaltung**: Interagiert mit Browser-Cookies, um Notizblock-Produkt-IDs zu speichern und abzurufen, wenn die Option „Produkte merken“ aktiviert ist.

### 4.5 CSS-Stylesheets (`views/css/`)

- `css/admincss.css`
  - **Umfang**: Styling des Back-Office-Admin-Formulars.
  - **Beschreibung**: Stile für die Konfigurationsseite des Moduls im PrestaShop Back Office, um ein konsistentes Erscheinungsbild mit dem PrestaShop Admin-Theme zu gewährleisten.
- `css/css.css`
  - **Umfang**: Styling für Kunden im Front-Office.
  - **Beschreibung**: Enthält die primären Stile für den Notizblock-Anzeigeblock, den „Zum Notizblock hinzufügen“-Button und alle zugehörigen Elemente im Shop.
  - **Wichtige CSS-Klassenselektoren**: Entwickler können den generierten HTML-Code nach Klassen wie `.notepad-block`, `.add-to-notepad`, `.notepad-product-item` untersuchen, um Stile in der `custom.css` oder `theme.css` ihres Themes zu überschreiben.
- `lib/searchTool/views/css/autocomplete.css`
  - **Umfang**: Front-Office (oder Back-Office, wenn das Suchwerkzeug dort verwendet wird).
  - **Beschreibung**: Stile für das Dropdown-Menü der Autocomplete-Suchergebnisse, wenn das `autocomplete.js`-Skript aktiv für eine Produktsuchfunktion innerhalb des Moduls verwendet wird.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - `extraleft.tpl`
    - **Hook**: Wahrscheinlich `displayLeftColumn` oder ähnlich.
    - **Zweck**: Rendert den Haupt-Notizblock-Zusammenfassungsblock, der in der linken Spalte erscheint. Dieser zeigt typischerweise einen Titel, die Anzahl der Artikel und eine kurze Liste oder einen Link zum vollständigen Notizblock.
  - `notepad.tpl`
    - **Hook**: Dies könnte ein allgemeines Template sein, das von anderen Templates eingebunden oder je nach Konfiguration direkt in `displayRightColumn`, `displayFooter` oder `displayHeader` eingehängt wird. Es enthält wahrscheinlich die Kernstruktur für den Notizblock-Block.
- **Admin-Templates (`views/templates/admin/`)**: Keine explizit aufgeführt, die Konfiguration wird wahrscheinlich direkt von `notepad.php` durch das Rendern von Formularelementen gehandhabt.
- **Front-Office-Templates (`views/templates/front/`)**:
  - `views/addToCart.tpl`
    - **Zweck**: Dieses Template wird auf Produktseiten (und potenziell Produktlisten) gerendert, um den „Zum Notizblock hinzufügen“-Button anzuzeigen. Es ist wahrscheinlich in `displayProductButtons` oder `displayProductActions` eingehängt.
  - `views/selectedProducts.tpl`
    - **Zweck**: Dieses Template wird verwendet, um die detaillierte Liste der Produkte innerhalb des Notizblocks anzuzeigen, entweder in einem Popup, einer dedizierten Seite oder innerhalb des erweiterten Spaltenblocks. Es iteriert über die im Notizblock gespeicherten Produkte und zeigt deren Bild, Namen, Preis und eine „Entfernen“-Option an.
  - `lib/searchTool/views/scripts.tpl`
    - **Zweck**: Dieses Template enthält wahrscheinlich die notwendigen JavaScript- und CSS-Dateien für die `searchTool`-Bibliothek, wie `autocomplete.js` und `autocomplete.css`, falls das Modul eine Suchfunktion verwendet. Es würde in `displayHeader` oder `displayFooter` eingehängt, um diese Assets zu laden.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Das Modul scheint keine benutzerdefinierten SQL-Tabellen zu erstellen. Produkt-IDs und zugehörige Daten für den Notizblock werden clientseitig verwaltet, hauptsächlich über Browser-Cookies oder Session-Variablen. Konfigurationseinstellungen werden in `ps_configuration` gespeichert (z. B. `NOTEPAD_REMEMBER`, `NOTEPAD_LIMIT`, `NOTEPAD_LIMIT_VALUE`).
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Zum Laden der CSS- und JS-Assets des Moduls (z. B. `notepad.js`, `css.css`) und potenziell zum Rendern einer kompakten Notizblock-Zusammenfassung, falls konfiguriert. |
| `displayLeftColumn` | In der linken Seitenleiste von Seiten, die eine haben. | Zum Anzeigen des Haupt-Notizblock-Zusammenfassungsblocks (`extraleft.tpl`). |
| `displayRightColumn` | In der rechten Seitenleiste von Seiten, die eine haben. | Zum Anzeigen des Haupt-Notizblock-Zusammenfassungsblocks (`notepad.tpl` oder ähnlich). |
| `displayFooter` | Im Footer-Bereich jeder Seite. | Zum Anzeigen des Notizblock-Zusammenfassungsblocks, falls konfiguriert, oder zum Laden verzögerter JS. |
| `displayProductButtons` / `displayProductActions` (oder ähnlicher Produktseiten-Hook) | Auf der Produktseite, in der Nähe des „In den Warenkorb“-Buttons. | Zum Rendern des „Zum Notizblock hinzufügen“-Buttons (`views/addToCart.tpl`). |
| `actionFrontControllerSetMedia` | Bevor der Front-Controller seine Ausgabe rendert. | Zum Registrieren der CSS- und JS-Dateien des Moduls für optimales Laden. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul Produkte Notizblock besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls gerne zur Verfügung.
