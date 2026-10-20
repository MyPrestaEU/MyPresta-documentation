---
title: "Zopim Chat Free - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Zopim Chat Free von MyPresta.eu."
sidebar:
  label: "Zopim Chat Free - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Zopim Chat Free auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/zopim-chat-free.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/zopim-chat-free/)
>
> ---


# Zopim Chat Free

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst und alle externen API-Integrationen, einschließlich Zendesk Chat, erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren > Zopim Chat Free)

Dies ist der Haupt- und einzige Konfigurationsbildschirm für das Modul Zopim Chat Free. Hier geben Sie Ihren Zendesk Chat (Zopim)-Kontoschlüssel ein und entscheiden, wo das Chat-Widget-Skript in Ihrem Shop geladen werden soll.

#### **Zopim-Kontoschlüssel**

- **Was diese Einstellung bewirkt:** Dies ist die wichtigste Einstellung. Hier geben Sie den eindeutigen Bezeichner ein, den Zendesk Chat (Zopim) für Ihr Live-Chat-Widget bereitstellt. Dieser Schlüssel teilt dem Modul mit, welches Chat-Widget auf Ihrer Website geladen werden soll. Sie finden diesen Schlüssel in Ihrem Zendesk Chat-Dashboard (normalerweise unter Einstellungen > Widget > Embed Code).
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn ein gültiger Schlüssel eingegeben wird:* Das Zopim-Chat-Widget, das mit Ihrem Zendesk Chat-Konto verknüpft ist, erscheint im Front-Office Ihres Shops, sodass Kunden Chats initiieren können.
  - *Wenn leer gelassen oder ein ungültiger Schlüssel eingegeben wird:* Das Zopim-Chat-Widget erscheint nicht in Ihrem Shop, und die Live-Chat-Funktionalität ist nicht verfügbar.
- **Empfohlener Wert:** Ihr eindeutiger Zendesk Chat (Zopim)-Kontoschlüssel.
- **Händlerszenario / Beispiel:** Nach der Anmeldung bei Zendesk Chat erhalten Sie einen Code-Snippet. Innerhalb dieses Codes finden Sie eine spezifische Zeichenfolge (z. B. `zopim.setAndDefer('account', 'IHR_KONTOSCHLÜSSEL');`). Kopieren Sie `IHR_KONTOSCHLÜSSEL` und fügen Sie ihn hier ein.

#### **Zopim Chat in Hook laden**

- **Was diese Einstellung bewirkt:** Diese Option bestimmt, wo im Code Ihres PrestaShop-Stores das Zopim-Chat-Skript eingefügt wird. Während das Chat-Widget selbst normalerweise auf dem Bildschirm schwebt, kann die Platzierung des Skripts manchmal die Ladegeschwindigkeit oder die Kompatibilität mit bestimmten Themes beeinflussen.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn auf `displayHeader` (Header) eingestellt:* Das Chat-Skript wird sehr früh geladen, typischerweise vor den meisten Ihrer Seiteninhalte. Dies kann dazu führen, dass das Chat-Widget schnell erscheint.
  - *Wenn auf `displayRightColumn` (Rechte Spalte) eingestellt:* Das Skript wird mit dem Inhalt der rechten Spalte geladen. Dies ist für Chat-Widgets weniger üblich und möglicherweise nicht ideal, wenn Ihr Theme nicht immer eine rechte Spalte anzeigt.
  - *Wenn auf `displayLeftColumn` (Linke Spalte) eingestellt:* Ähnlich wie bei der rechten Spalte wird das Skript mit dem Inhalt der linken Spalte geladen.
  - *Wenn auf `displayProductButtons` (Produktseiten-Buttons) eingestellt:* Das Skript wird speziell auf Produktseiten, in der Nähe des „In den Warenkorb“-Bereichs, geladen. Dies kann nützlich sein, wenn Sie hauptsächlich Chat-Support auf Produktseiten wünschen.
  - *Wenn auf `displayFooter` (Footer) eingestellt:* Das Skript wird ganz am Ende Ihres Seiteninhalts geladen. Dies kann die wahrgenommene anfängliche Seitenladegeschwindigkeit für den Benutzer verbessern, da der Hauptinhalt zuerst geladen wird und das Chat-Widget danach.
- **Empfohlener Wert:** `displayHeader` oder `displayFooter`. Für die meisten Shops stellt `displayHeader` sicher, dass der Chat schnell geladen wird. Wenn Sie Konflikte erleben oder die Inhaltsladung priorisieren möchten, ist `displayFooter` eine gute Alternative.
- **Händlerszenario / Beispiel:** Wenn Ihre Kunden häufig Fragen stellen, *bevor* sie überhaupt Produkte durchsuchen, stellt das Laden des Chats im `displayHeader` sicher, dass er sofort verfügbar ist. Wenn Sie feststellen, dass Ihre Seite langsam lädt und das Chat-Skript vermuten, könnte das Umschalten auf `displayFooter` helfen, da der Chat nach dem Hauptseiteninhalt geladen wird.

#### Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modul-Konfigurationsseite | Zopim-Kontoschlüssel | Ihr eindeutiger Zendesk Chat-Schlüssel | Verbindet Ihren Shop mit Ihrem Zendesk Chat-Konto. Wesentlich, damit das Widget erscheint. |
| Modul-Konfigurationsseite | Zopim Chat in Hook laden | `displayHeader` oder `displayFooter` | Bestimmt, wo das Chat-Skript eingefügt wird (Header, Spalten, Produkt, Footer). Beeinflusst die Lade-Reihenfolge und potenzielle Theme-Kompatibilität. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Das Zopim-Chat-Widget erscheint nicht in meinem Shop. Was soll ich tun?**
A1:

1.  **Überprüfen Sie Ihren Zopim-Kontoschlüssel:** Gehen Sie zur Modulkonfigurationsseite und stellen Sie sicher, dass Ihr Zopim-Kontoschlüssel korrekt eingegeben ist. Schon ein einziger Tippfehler verhindert das Laden.
2.  **Überprüfen Sie den Zendesk Chat-Status:** Melden Sie sich in Ihrem Zendesk Chat-Dashboard an. Ist Ihr Widget aktiv? Sind Ihre Agenten online?
3.  **PrestaShop-Cache leeren:** Gehen Sie in Ihrem PrestaShop-Backoffice zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal verhindern alte Cache-Dateien, dass neue Moduländerungen angezeigt werden.
4.  **Auf Theme-Konflikte prüfen:** Wechseln Sie vorübergehend zum Standard-PrestaShop-Theme (z. B. Classic) und prüfen Sie, ob das Widget erscheint. Wenn ja, könnte Ihr benutzerdefiniertes Theme einen Konflikt verursachen. Kontaktieren Sie Ihren Theme-Entwickler oder einen Webmaster.
5.  **Browser-Konsole überprüfen:** Öffnen Sie die Entwicklertools Ihres Browsers (F12) und überprüfen Sie den Tab „Konsole“ auf JavaScript-Fehler. Dies kann Hinweise geben, wenn das Skript nicht geladen werden kann.

**F2: Das Chat-Widget lädt, sieht aber seltsam aus oder ist falsch positioniert.**
A2: Das Modul fügt das Zopim-Skript ein, aber die visuelle Gestaltung und die genaue Positionierung des Widgets werden weitgehend durch Ihre Zendesk Chat-Kontoeinstellungen und das CSS Ihres Shops gesteuert.

1.  **Zendesk Chat-Dashboard:** Melden Sie sich in Ihrem Zendesk Chat-Dashboard an und überprüfen Sie Ihre Widget-Erscheinungseinstellungen (z. B. Position, Farben, Größe).
2.  **Theme-CSS:** Das CSS Ihres benutzerdefinierten Themes könnte einige Standard-Zopim-Stile überschreiben. Ein Webmaster kann das Element mit den Browser-Entwicklertools untersuchen und widersprüchliche CSS-Regeln identifizieren.

**F3: Kann ich den Text des Chat-Widgets in verschiedene Sprachen übersetzen?**
A3: Das Modul Zopim Chat Free selbst übernimmt keine Übersetzungen für die Benutzeroberfläche des Widgets. Diese Funktionalität wird direkt in Ihren Zendesk Chat-Kontoeinstellungen verwaltet. Zendesk Chat unterstützt mehrere Sprachen, und Sie können das Widget so konfigurieren, dass es in der bevorzugten Sprache des Kunden angezeigt wird, basierend auf dessen Browsereinstellungen oder Ihrer Zendesk Chat-Einrichtung.

**F4: Wird dieses Modul meine Website verlangsamen?**
A4: Das Modul Zopim Chat Free fügt nur das notwendige Zendesk Chat-Skript ein. Die Leistungsbeeinträchtigung hängt hauptsächlich vom Zendesk Chat-Dienst selbst und Ihrer Internetverbindung ab. Sie können versuchen, die Option „Zopim Chat in Hook laden“ auf `displayFooter` einzustellen, um sicherzustellen, dass der Hauptinhalt Ihrer Seite vor dem Chat-Skript geladen wird, was die wahrgenommene Seitenladegeschwindigkeit verbessern kann.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen technischen Überblick für Entwickler und Webmaster, die mit dem Modul Zopim Chat Free arbeiten.

### 4.1 Architekturübersicht

Das Modul `ZopimFree` ist ein unkompliziertes PrestaShop-Modul, das zur Integration des Zendesk Chat (ehemals Zopim)-Widgets entwickelt wurde. Es funktioniert hauptsächlich, indem es das Zendesk Chat-Einbettungsskript in das Front-Office des PrestaShop-Stores injiziert. Das Modul folgt einer Standard-PrestaShop-Modulstruktur und verwendet die `Module`-Klasse für Installation, Deinstallation und Konfigurationsverwaltung über `getContent()`. Es registriert einen einzelnen Hook (`displayHeader` standardmäßig, aber konfigurierbar), um das notwendige JavaScript auszugeben.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Das Modul injiziert Inhalte direkt in Hooks.
- **Back-Office-Admin-Controller**: Keine. Die gesamte Konfiguration wird innerhalb der `getContent()`-Methode des Hauptmoduls behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

- In diesem Modul sind keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen vorhanden. Die gesamte Logik befindet sich in der Hauptdatei `zopimfree.php`.

### 4.4 JavaScript-Assets (`views/js/`)

- In diesem Modul sind keine benutzerdefinierten JavaScript-Dateien enthalten. Das Modul gibt das Zendesk Chat-Einbettungsskript direkt in das Template aus, das dann das notwendige JS vom Zendesk CDN lädt.

### 4.5 CSS-Stylesheets (`views/css/`)

- In diesem Modul sind keine benutzerdefinierten CSS-Dateien enthalten. Die Gestaltung des Chat-Widgets wird vom Zendesk Chat-Dienst selbst übernommen, mit potenziellen Überschreibungen durch das aktive PrestaShop-Theme.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - `zopimfree/header-new-widget.tpl`
    - **Hook:** Dieses Template ist dafür konzipiert, innerhalb eines PrestaShop-Hooks gerendert zu werden, insbesondere des in der Modulkonfiguration gewählten (z. B. `displayHeader`, `displayFooter`).
    - **Zweck:** Es enthält das `<script>`-Tag, das für die Einbettung des Zendesk Chat-Widgets verantwortlich ist. Es fügt den `ZOPIMFREE_ACCOUNT_KEY` aus der Modulkonfiguration dynamisch in das Zendesk Chat-Initialisierungsskript ein.
    - **Ausgabe:** Gibt den Standard-Zendesk Chat-Einbettungscode aus, der dann das Chat-Widget von den Zendesk-Servern lädt.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfigurationseinstellungen in der Tabelle `ps_configuration`:
    - `ZOPIMFREE_ACCOUNT_KEY`: Speichert den Zendesk Chat-Kontoschlüssel.
    - `ZOPIMFREE_HOOK`: Speichert den Namen des Hooks, in den das Skript eingefügt werden soll (z. B. `displayHeader`, `displayFooter`).
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Wird im `<head>`-Bereich jeder Seite ausgeführt. | Standard-Hook zum frühen Einfügen des Zendesk Chat-Skripts beim Seitenaufbau. |
| `displayRightColumn` | Wird in der rechten Spalte von Seiten ausgeführt, auf denen sie aktiv ist. | Alternativer Hook für die Skriptinjektion, weniger üblich für Chat-Widgets. |
| `displayLeftColumn` | Wird in der linken Spalte von Seiten ausgeführt, auf denen sie aktiv ist. | Alternativer Hook für die Skriptinjektion, weniger üblich für Chat-Widgets. |
| `displayProductButtons` | Wird auf Produktseiten ausgeführt, typischerweise in der Nähe des „In den Warenkorb“-Buttons. | Spezifischer Hook zum Einfügen des Chat-Skripts nur auf Produktseiten. |
| `displayFooter` | Wird direkt vor dem schließenden `</body>`-Tag ausgeführt. | Alternativer Hook zum späteren Einfügen des Zendesk Chat-Skripts beim Seitenaufbau, was die wahrgenommene anfängliche Seitenladegeschwindigkeit verbessern kann. |

Das Modul registriert diese Hooks dynamisch basierend auf dem Konfigurationswert `ZOPIMFREE_HOOK`. Die Methode `install()` registriert alle potenziellen Hooks, und `uninstall()` hebt deren Registrierung auf. Die Methode `hook{HookName}` prüft dann die Konfiguration, um zu entscheiden, ob das Template gerendert werden soll.

## 5. Offizieller Support & Updates

Für offizielle Updates, Fehlerbehebungen und Entwickler-Support für das Modul Zopim Chat Free verweisen wir auf Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/). Stellen Sie sicher, dass Sie die neueste Version herunterladen, die mit Ihrer PrestaShop-Installation kompatibel ist.
