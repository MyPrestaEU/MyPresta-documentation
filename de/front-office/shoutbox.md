---
title: "Shoutbox - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das Shoutbox PrestaShop-Modul von MyPresta.eu."
sidebar:
  label: "Shoutbox - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Shoutbox auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/shoutbox.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/shoutbox/)
>
> ---


# Shoutbox

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 9.x, 8.x, 1.7.x, 1.6.x, 1.5.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Shoutbox-Modul, der direkt nach der Installation oder durch Navigieren zu **Module > Modul-Manager**, Suchen nach „Shoutbox“ und Klicken auf „Konfigurieren“ zugänglich ist.

| Einstellung / Option | Was diese Einstellung bewirkt | Auswirkung der Änderung dieser Einstellung | Empfohlener Wert | Händlerszenario / Beispiel |
| --- | --- | --- | --- | --- |
| **Shoutbox aktivieren** | Dies ist der Hauptschalter, um die gesamte Shoutbox-Funktion in Ihrem Shop ein- oder auszuschalten. | *Wenn aktiviert:* Die Shoutbox erscheint in Ihrem Front Office an den ausgewählten Hook-Positionen. Kunden können sie sehen und mit ihr interagieren.   *Wenn deaktiviert:* Die Shoutbox wird vollständig aus Ihrem Shop ausgeblendet, und es werden keine Nachrichten angezeigt oder akzeptiert. | **JA** | Sie möchten die Community-Chat-Funktion in Ihrem Shop aktivieren. Wenn Sie sie vorübergehend für Wartungsarbeiten oder Inhaltsüberprüfungen ausblenden müssen, würden Sie dies auf NEIN setzen. |
| **Shoutbox-Titel** | Dies legt den Überschriftentext fest, der oben im Shoutbox-Widget in Ihrem Shop-Front-Office erscheint. | *Wenn auf „Community-Chat“ gesetzt:* Ihre Kunden sehen „Community-Chat“ als Titel des Feldes.   *Wenn auf „Fragen Sie uns alles“ gesetzt:* Der Titel ändert sich zu „Fragen Sie uns alles“. | **Community-Chat** | Sie möchten das Chatfeld für Ihre Kunden klar kennzeichnen. Sie könnten es in „Produktdiskussionen“ ändern, wenn Sie es auf Produktseiten platzieren. |
| **Anzahl der anzuzeigenden Nachrichten** | Dies steuert, wie viele der neuesten Nachrichten jederzeit in der Shoutbox angezeigt werden. Ältere Nachrichten werden ausgeblendet. | *Wenn auf 10 gesetzt:* Nur die letzten 10 Nachrichten sind im Chatfeld sichtbar.   *Wenn auf 20 gesetzt:* Die letzten 20 Nachrichten werden angezeigt. | **10** | Um den Chat prägnant zu halten und zu verhindern, dass er zu lang wird, ist es in der Regel am besten, die letzten 10-15 Nachrichten anzuzeigen. Wenn Sie eine sehr aktive Community haben, könnten Sie dies erhöhen. |
| **Aktualisierungsintervall (Sekunden)** | Dies bestimmt, wie oft die Shoutbox automatisch nach neuen Nachrichten sucht und diese lädt, ohne dass der Kunde die Seite aktualisieren muss. | *Wenn auf 5 gesetzt:* Neue Nachrichten erscheinen alle 5 Sekunden.   *Wenn auf 15 gesetzt:* Neue Nachrichten erscheinen alle 15 Sekunden. | **10** | Ein kürzeres Intervall (z.B. 5 Sekunden) lässt den Chat in Echtzeit erscheinen, verbraucht aber mehr Serverressourcen. Ein längeres Intervall (z.B. 15-20 Sekunden) reduziert die Serverlast, aber Nachrichten erscheinen weniger sofort. 10 Sekunden ist ein guter Kompromiss. |
| **Gästen das Posten erlauben** | Diese Option steuert, ob Besucher, die nicht in einem Kundenkonto angemeldet sind, Nachrichten in der Shoutbox posten können. | *Wenn aktiviert:* Jeder Besucher Ihres Shops kann Nachrichten posten, auch wenn er sich nicht registriert oder angemeldet hat. Sie posten typischerweise als „Gast“.   *Wenn deaktiviert:* Nur registrierte und angemeldete Kunden können Nachrichten posten. Gäste sehen den Chat, können aber nicht dazu beitragen. | **NEIN** | Wenn Sie die Registrierung fördern und anonymen Spam verhindern möchten, deaktivieren Sie dies. Wenn Sie maximale Interaktion wünschen und anonyme Beiträge nicht stören, aktivieren Sie es. |
| **Shoutbox anzeigen in** | Diese entscheidende Einstellung bestimmt, wo das Shoutbox-Widget in Ihrem Shop-Front-Office erscheint. Sie können einen oder mehrere Standorte auswählen. | *Wenn „Linke Spalte“ ausgewählt ist:* Die Shoutbox erscheint in der linken Seitenleiste Ihres Shops.   *Wenn „Footer“ ausgewählt ist:* Die Shoutbox erscheint am unteren Rand Ihrer Shop-Seiten. | **Linke Spalte** (oder ein Ort, der zu Ihrem Thema passt) | Sie möchten, dass die Shoutbox gut sichtbar ist, aber nicht Ihre Hauptproduktinhalte stört. Die Platzierung in einer Spalte oder im Footer ist oft eine gute Wahl. |
| **Moderation erforderlich** | Wenn aktiviert, erscheinen neue Nachrichten erst in der Shoutbox, wenn ein Administrator sie im Back Office manuell genehmigt. | *Wenn aktiviert:* Alle neuen Nachrichten gehen in eine Warteschlange. Sie müssen jede Nachricht genehmigen, bevor sie für andere Kunden sichtbar wird.   *Wenn deaktiviert:* Nachrichten erscheinen sofort nach dem Posten. | **NEIN** (es sei denn, Sie erwarten Spam) | Wenn Sie Bedenken wegen Spam, unangemessener Inhalte haben oder eine strenge Kontrolle über die Konversation aufrechterhalten möchten, aktivieren Sie die Moderation. Für einen flüssigeren Echtzeit-Chat deaktivieren Sie sie. |
| **Alle Nachrichten löschen** | Dies ist eine Schaltfläche (kein Umschalter), die, wenn sie angeklickt wird, alle vorhandenen Nachrichten dauerhaft aus der Shoutbox löscht. | *Wenn angeklickt:* Alle historischen Nachrichten in der Shoutbox werden aus Ihrer Datenbank entfernt und nicht mehr angezeigt. Diese Aktion ist irreversibel. | **N/A** (Vorsicht geboten) | Sie könnten dies verwenden, wenn der Chat zu viele alte Nachrichten angesammelt hat oder wenn Sie eine neue Konversation für eine neue Aktion oder Veranstaltung beginnen möchten. |

### 2.2 Kurzübersichtstabelle der Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Shoutbox aktivieren | JA | Aktiviert/deaktiviert die gesamte Shoutbox-Funktion. |
| Modulkonfiguration | Shoutbox-Titel | Community-Chat | Legt den sichtbaren Titel des Shoutbox-Widgets fest. |
| Modulkonfiguration | Anzahl der anzuzeigenden Nachrichten | 10 | Steuert, wie viele aktuelle Nachrichten angezeigt werden. |
| Modulkonfiguration | Aktualisierungsintervall (Sekunden) | 10 | Wie oft der Chat mit neuen Nachrichten aktualisiert wird. |
| Modulkonfiguration | Gästen das Posten erlauben | NEIN | Bestimmt, ob nicht angemeldete Benutzer Nachrichten posten können. |
| Modulkonfiguration | Shoutbox anzeigen in | Linke Spalte | Wählt die Front-Office-Position(en) für die Shoutbox aus. |
| Modulkonfiguration | Moderation erforderlich | NEIN | Erfordert die Genehmigung durch den Administrator, bevor Nachrichten erscheinen. |
| Modulkonfiguration | Alle Nachrichten löschen | N/A | Löscht alle Nachrichten dauerhaft aus der Shoutbox. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Die Shoutbox erscheint nicht in meinem Shop, obwohl ich sie aktiviert habe.**
**A1:**

- **Hook-Auswahl überprüfen:** Gehen Sie zur Modulkonfiguration und stellen Sie sicher, dass Sie mindestens einen „Shoutbox anzeigen in“-Ort ausgewählt haben (z.B. Linke Spalte, Footer).
- **Cache leeren:** Der PrestaShop-Cache kann manchmal verhindern, dass neue Module angezeigt werden. Gehen Sie zu **Erweiterte Einstellungen > Performance** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen).
- **Theme-Kompatibilität:** Einige stark angepasste Themes rendern Standard-Modul-Hooks möglicherweise nicht korrekt. Wenn das Leeren des Caches nicht funktioniert, versuchen Sie, vorübergehend zum Standard-PrestaShop-Theme zu wechseln, um zu sehen, ob die Shoutbox erscheint. Wenn ja, benötigt Ihr Theme wahrscheinlich eine kleine Anpassung (kontaktieren Sie Ihren Theme-Entwickler oder einen Webmaster).

**F2: Neue Nachrichten erscheinen nicht in Echtzeit; ich muss die Seite aktualisieren.**
**A2:**

- **Aktualisierungsintervall überprüfen:** Stellen Sie in der Modulkonfiguration sicher, dass „Aktualisierungsintervall (Sekunden)“ auf eine angemessene Zahl (z.B. 5-15 Sekunden) und nicht auf 0 oder eine sehr hohe Zahl eingestellt ist.
- **JavaScript-Konflikte:** Ein anderes Modul oder das JavaScript Ihres Themes könnte einen Konflikt verursachen. Überprüfen Sie die Entwicklerkonsole Ihres Browsers (F12-Taste, dann den Tab „Konsole“) auf JavaScript-Fehler. Wenn Fehler auftreten, versuchen Sie, andere kürzlich installierte Module nacheinander zu deaktivieren, um den Übeltäter zu identifizieren.

**F3: Ich erhalte viele Spam-Nachrichten in der Shoutbox.**
**A3:**

- **Moderation aktivieren:** Gehen Sie zur Modulkonfiguration und setzen Sie „Moderation erforderlich“ auf JA. Dadurch werden alle neuen Nachrichten in einen ausstehenden Zustand versetzt, sodass Sie sie genehmigen können, bevor sie live gehen.
- **Gäste-Posting deaktivieren:** Wenn Spam von anonymen Benutzern stammt, setzen Sie „Gästen das Posten erlauben“ auf NEIN. Dies erfordert, dass Benutzer in einem Kundenkonto angemeldet sind, um zu posten, was oft Spam reduziert.

**F4: Wie übersetze ich den Shoutbox-Titel oder andere Texte in verschiedene Sprachen?**
**A4:**

- Navigieren Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**.
- Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann Ihre Sprache.
- Suchen Sie das Modul „Shoutbox“ in der Liste, und Sie können die übersetzbaren Zeichenfolgen, einschließlich des Shoutbox-Titels, bearbeiten.

**F5: Die Shoutbox sieht etwas seltsam aus oder passt nicht zum Styling meines Themes.**
**A5:**

- Das Modul verwendet grundlegendes Styling. Für ein benutzerdefiniertes Erscheinungsbild benötigen Sie einen Webmaster oder Entwickler, der benutzerdefinierte CSS-Regeln zum Stylesheet Ihres Themes hinzufügt. Sie können die Elemente der Shoutbox ansprechen und Farben, Schriftarten, Ränder usw. anpassen, um sie perfekt an Ihre Marke anzupassen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten Einblick in die technische Struktur des Shoutbox-Moduls, der für Entwickler, Webmaster und technische Agenturen bestimmt ist.

### 4.1 Architekturübersicht

Das Shoutbox-Modul folgt einer klassischen PrestaShop-Modulstruktur, die Front-Controller für AJAX-Interaktionen und die Hauptmoduldatei (`index.php`) für Konfiguration und Hook-Registrierung nutzt. Es ist ein leichtgewichtiges Modul, das sich hauptsächlich auf das Anzeigen und Übermitteln von Nachrichten über AJAX konzentriert, ohne komplexe Objektmodelle oder dedizierte Datenbanktabellen über `ps_configuration` für Einstellungen hinaus. Die Kernfunktionalität basiert auf direkter Datenbankinteraktion zur Nachrichtenspeicherung und -abfrage.

### 4.2 Controller (`controllers/`)

Das Modul verwendet Front-Controller, um AJAX-Anfragen zum Laden und Einfügen von Nachrichten zu verarbeiten und so eine dynamische Benutzererfahrung ohne vollständige Seitenneuladungen zu gewährleisten.

- **Front-Office-Controller**:

  - `controllers/front/ajaxload.php`
    - **Klassenname**: `ShoutboxAjaxloadModuleFrontController` (erweitert `ModuleFrontController`)
    - **Verantwortlichkeit**: Dieser Controller verarbeitet die AJAX-Anfrage zum Laden vorhandener Nachrichten. Er ruft typischerweise eine angegebene Anzahl der neuesten Nachrichten aus der Datenbank ab und gibt sie, wahrscheinlich als JSON oder Roh-HTML, zur Anzeige im Shoutbox-Widget zurück. Dies ist der Endpunkt für den Auto-Refresh-Mechanismus.
  - `controllers/front/index.php`
    - **Klassenname**: `ShoutboxIndexModuleFrontController` (erweitert `ModuleFrontController`)
    - **Verantwortlichkeit**: Dieser Controller könnte als Fallback oder als direkter Zugangspunkt zur Shoutbox dienen, falls diese eine dedizierte Seite hätte. Angesichts der Natur des Moduls ist es wahrscheinlicher ein Platzhalter oder behandelt die anfängliche Rendering-Logik, wenn die Shoutbox direkt und nicht über einen Hook eingebettet ist. In den meisten Fällen wird die Shoutbox über `shoutbox.tpl` in einem Hook gerendert.
  - `controllers/front/insert.php`
    - **Klassenname**: `ShoutboxInsertModuleFrontController` (erweitert `ModuleFrontController`)
    - **Verantwortlichkeit**: Dieser Controller verarbeitet die AJAX-Anfrage zum Übermitteln neuer Nachrichten. Er empfängt den Nachrichteninhalte (und potenziell Benutzer-ID/Name) vom Frontend, führt alle notwendigen Validierungen durch (z.B. Gast-Posting, Moderation), speichert die Nachricht in der Datenbank und gibt eine Erfolgs-/Fehlermeldung zurück.
- **Back-Office-Admin-Controller**:

  - Keine. Alle Konfigurationen werden innerhalb der `getContent()`-Methode der Hauptmoduldatei behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul definiert keine benutzerdefinierten Klassen oder `ObjectModel`s im Verzeichnis `classes/`. Die Nachrichtenspeicherung und -abfrage werden direkt innerhalb der PHP-Dateien des Moduls behandelt, wahrscheinlich unter Verwendung von `Db::getInstance()` für SQL-Abfragen. Dies impliziert, dass Nachrichten in einer benutzerdefinierten Tabelle gespeichert werden, die während der Installation erstellt wurde, oder direkt in `ps_configuration`, wenn die Nachrichten sehr wenige und einfach sind (obwohl eine dedizierte Tabelle für Chat-Nachrichten wahrscheinlicher ist).

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul basiert auf JavaScript für seine AJAX-Funktionalität und dynamische Updates.

- `js/advajax.js`
  - **Umfang**: Front-Office.
  - **Details**: Diese Datei enthält wahrscheinlich generische AJAX-Dienstprogramme oder Wrapper-Funktionen, die vom Modul verwendet werden. Sie könnte Cross-Browser-Kompatibilität für AJAX-Anfragen bieten oder den Prozess des Sendens und Empfangens von Daten von den Front-Controllern vereinfachen. Es könnte eine benutzerdefinierte Implementierung oder eine leichtgewichtige Bibliothek sein.
- `js/script.js`
  - **Umfang**: Front-Office.
  - **Details**: Dies ist die Haupt-JavaScript-Datei für die Front-End-Logik der Shoutbox.
    - **Ereignis-Listener**: Bindet an Formularübermittlungsereignisse zum Posten neuer Nachrichten und potenziell an Klickereignisse für Aktionen wie das Löschen von Nachrichten (falls im Frontend verfügbar).
    - **AJAX-Aufrufe**: Initiiert AJAX-Anfragen an `ajaxload.php` zum Aktualisieren von Nachrichten im angegebenen Intervall und an `insert.php` zum Übermitteln neuer Nachrichten.
    - **DOM-Manipulation**: Aktualisiert die Shoutbox-Anzeige mit neuen Nachrichten, scrollt zum Ende des Chats und behandelt das Leeren des Eingabefeldes.
    - **Timer**: Richtet `setInterval` für das periodische Laden von Nachrichten basierend auf der Einstellung „Aktualisierungsintervall“ ein.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul listet keine expliziten benutzerdefinierten CSS-Dateien im Verzeichnis `views/css/` auf. Dies deutet darauf hin, dass:

1. Das Modul auf Inline-Styles oder grundlegende Standard-Browser-Styles angewiesen ist.
2. Es möglicherweise so konzipiert ist, dass es das Styling direkt vom aktiven PrestaShop-Theme erbt und nur minimale benutzerdefinierte CSS-Anpassungen erfordert.
3. Jegliches Styling direkt in der Datei `shoutbox.tpl` oder im Hauptmodul-PHP eingebettet ist.
   Entwickler, die die Shoutbox gestalten möchten, müssen den generierten HTML-Code überprüfen und benutzerdefinierte CSS-Regeln zum Stylesheet ihres Themes hinzufügen, die auf die spezifischen IDs und Klassen der Shoutbox-Elemente abzielen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - `shoutbox/shoutbox.tpl`
    - **Gerenderte Hook(s)**: `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (oder ähnlicher Produktseiten-Hook). Der tatsächliche Hook hängt von der Konfiguration des Händlers im Back Office ab.
    - **Visuelle Blockausgabe**: Dieses Template rendert die vollständige HTML-Struktur des Shoutbox-Widgets. Dies umfasst:
      - Den Hauptcontainer für das Chatfeld.
      - Den Titel (z.B. „Community-Chat“).
      - Den Bereich, in dem Nachrichten angezeigt werden (ein scrollbarer Div).
      - Das Eingabefeld zum Eingeben neuer Nachrichten.
      - Die Schaltfläche „Senden“.
      - Bedingtes Rendering für Gast-Posting-Funktionen.
      - Es enthält auch das notwendige JavaScript und potenziell Inline-CSS.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul deklariert keine explizite benutzerdefinierte `ObjectModel` oder SQL-Datei. Die Nachrichtenspeicherung wird wahrscheinlich direkt über `Db::getInstance()` in der Hauptmoduldatei oder den Front-Controllern gehandhabt. Ein gängiges Muster für solche Module ist die Erstellung einer Tabelle wie `ps_shoutbox_messages` mit Feldern wie `id_shoutbox_message`, `id_customer`, `customer_name`, `message_content`, `date_add`, `ip_address`, `approved`.
  - **Konfigurationsdatensätze**: Moduleinstellungen (z.B. `SHOUTBOX_ENABLED`, `SHOUTBOX_TITLE`, `SHOUTBOX_NUM_MESSAGES`, `SHOUTBOX_REFRESH_INTERVAL`, `SHOUTBOX_ALLOW_GUEST`, `SHOUTBOX_MODERATION`, `SHOUTBOX_HOOK`) werden in der Tabelle `ps_configuration` gespeichert.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Rendert Inhalte im `<head>`-Bereich des HTML oder ganz oben im `<body>`. | Wird verwendet, um CSS-, JavaScript-Dateien oder das Shoutbox-Widget selbst einzufügen, wenn es für die Header-Anzeige konfiguriert ist. |
| `displayLeftColumn` | Rendert Inhalte in der linken Seitenleiste des Shops. | Häufiger Hook zum Anzeigen des Shoutbox-Widgets als Seitenleisten-Element. |
| `displayRightColumn` | Rendert Inhalte in der rechten Seitenleiste des Shops. | Häufiger Hook zum Anzeigen des Shoutbox-Widgets als Seitenleisten-Element. |
| `displayFooter` | Rendert Inhalte im Footer-Bereich des Shops. | Wird verwendet, um das Shoutbox-Widget am unteren Rand der Seite anzuzeigen. |
| `displayProductButtons` (oder ähnlicher Produktseiten-Hook) | Rendert Inhalte auf der Produktseite, oft in der Nähe der Schaltfläche „In den Warenkorb“ oder der Produktbeschreibung. | Wird verwendet, um die Shoutbox speziell auf Produktseiten für produktbezogene Diskussionen anzuzeigen. |
| `actionFrontControllerSetMedia` | Wird ausgeführt, wenn ein Front-Controller seine Medien (CSS/JS) festlegt. | Wird verwendet, um modulspezifisches JavaScript (`advajax.js`, `script.js`) und alle potenziellen CSS-Dateien zu registrieren, die im Front Office geladen werden sollen. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Shoutbox-Modul wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu). Unser engagiertes Support-Team steht Ihnen bei allen Problemen oder Fragen gerne zur Verfügung.
