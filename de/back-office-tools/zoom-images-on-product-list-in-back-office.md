---
title: "Bilder auf der Produktliste im Back Office zoomen - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Bilder auf der Produktliste im Back Office zoomen' von MyPresta.eu."
sidebar:
  label: "Bilder auf der Produktliste im Back Office zoomen - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Zoom images on product list in back office auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/zoom-images-on-product-list-in-back-office.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/zoom-images-on-product-list-in-back-office/)
>
> ---


# Bilder auf der Produktliste im Back Office zoomen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“ neben dem Modulnamen. Sie gelangen zum Hauptkonfigurationsbildschirm.

Dieses Modul hat eine sehr einfache Konfiguration, die typischerweise aus einem einzigen Schalter zum Aktivieren oder Deaktivieren seiner Funktionalität besteht.

- **Zoom auf Produktliste aktivieren:**
  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für das Modul. Er steuert, ob die Bild-Zoom-Funktion in Ihrer Back Office-Produktliste aktiv oder inaktiv ist.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Wenn Sie im Back Office zu **Katalog > Produkte** navigieren, wird beim Bewegen des Mauszeigers über eine Produktbild-Miniaturansicht in der Liste eine größere, gezoomte Version dieses Bildes angezeigt.
    - *Wenn deaktiviert (NEIN):* Die Zoom-Funktionalität wird ausgeschaltet. Das Bewegen des Mauszeigers über Produktbilder hat keine besondere Wirkung, und Sie sehen die standardmäßigen kleinen Miniaturansichten.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Wenn Sie die praktische Zoom-Funktion nutzen möchten, um Produktbilder schnell zu überprüfen, stellen Sie sicher, dass diese auf „JA“ eingestellt ist. Wenn Sie feststellen, dass sie mit einer anderen Back Office-Anpassung kollidiert oder Sie sie einfach nicht verwenden möchten, stellen Sie sie auf „NEIN“.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Zoom auf Produktliste aktivieren | JA | Aktiviert oder deaktiviert die Bild-Zoom-Funktion auf der Back Office-Produktliste. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul aktiviert, aber der Zoom funktioniert nicht in meiner Produktliste. Was soll ich tun?**
A:

1. **Cache leeren:** Gehen Sie in Ihrem Back Office zu **Erweiterte Einstellungen > Performance** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal kann der PrestaShop-Cache das Laden neuer JavaScript-Dateien verhindern.
2. **Browser-Konsole überprüfen:** Öffnen Sie die Entwicklertools Ihres Browsers (normalerweise F12) und suchen Sie im Tab „Konsole“ nach Fehlern. Dies könnte auf einen Konflikt mit einem anderen Modul oder Theme hinweisen.
3. **Modulkonflikte:** Deaktivieren Sie vorübergehend andere Module, die die Back Office-Produktliste ändern (falls vorhanden), um zu sehen, ob es einen Konflikt gibt.
4. **Theme-Overrides:** Wenn Sie ein stark angepasstes Back Office-Theme verwenden, könnte es die Standardstruktur der Produktliste überschreiben und das Modul daran hindern, sein JavaScript einzufügen. Kontaktieren Sie Ihren Theme-Entwickler oder den MyPresta.eu-Support.

**F: Das gezoomte Bild erscheint, sieht aber unscharf oder verpixelt aus.**
A: Das Modul zeigt das Bild an, das PrestaShop für die Produktliste bereitstellt. Wenn das ursprünglich für dieses Produkt hochgeladene Bild eine niedrige Auflösung hat, wird auch die gezoomte Version unscharf erscheinen. Stellen Sie sicher, dass Sie hochauflösende Bilder für Ihre Produkte hochladen.

**F: Verlangsamt dieses Modul mein Back Office?**
A: Nein, das Modul ist sehr leichtgewichtig. Es lädt nur eine kleine JavaScript-Bibliothek und wendet sie an, wenn Sie den Mauszeiger über ein Bild bewegen. Es führt keine schweren Operationen oder Datenbankabfragen durch, die die Leistung beeinträchtigen würden.

**F: Kann ich die Größe des Zoom-Feldes oder den Zoomfaktor anpassen?**
A: Das Modul verwendet ein Standard-„elevateZoom“-Tool, das einige Standardverhaltensweisen hat. Während das Modul selbst keine Konfigurationsoptionen für diese spezifischen visuellen Aspekte bietet, könnte ein Entwickler potenziell die Datei `zplb.js` ändern, um diese Parameter anzupassen. Dies würde eine benutzerdefinierte Codierung erfordern.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Bilder auf der Produktliste im Back Office zoomen“ (`zplb`) ist ein einfaches, aber effektives PrestaShop-Modul, das hauptsächlich dazu dient, clientseitiges JavaScript in die Back Office-Produktliste einzufügen. Es nutzt das PrestaShop-Hook-System, um seine Assets zu laden, und stützt sich auf eine JavaScript-Bibliothek eines Drittanbieters (elevateZoom, obwohl in `zplb.js` integriert), um die Zoom-Funktionalität bereitzustellen. Es führt keine neuen Datenbanktabellen oder komplexe Geschäftslogik ein.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Dieses Modul ist ausschließlich für das Back Office.
- **Back-Office-Admin-Controller**: Keine. Die Konfiguration des Moduls wird direkt in der `getContent()`-Methode der Hauptmoduldatei gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

- Keine. Das Modul definiert keine benutzerdefinierten Klassen oder `ObjectModel`-Instanzen. Die gesamte Logik ist in der Hauptdatei `zplb/index.php` enthalten.

### 4.4 JavaScript-Assets (`views/js/`)

- `zplb/lib/js/zplb.js`
  - **Geltungsbereich:** Back Office. Dieses Skript wird speziell auf der Back Office-Produktlistenseite geladen.
  - **Funktionalität:** Diese Datei enthält die Kern-JavaScript-Logik für die Zoom-Funktion. Sie enthält oder integriert wahrscheinlich die „elevateZoom“-Bibliothek. Sie zielt auf die Produktbildelemente innerhalb der Back Office-Produktlistentabelle ab (z. B. `img.img-thumbnail` oder ähnliche Selektoren, die von PrestaShops Produktliste verwendet werden). Sie bindet Mouseover-/Hover-Ereignisse an diese Bilder und initialisiert die Zoom-Funktionalität, wodurch die vergrößerte Ansicht erstellt wird.

### 4.5 CSS-Stylesheets (`views/css/`)

- Keine. Das Modul enthält keine benutzerdefinierten CSS-Dateien. Das Styling für das Zoom-Feld wird typischerweise von der JavaScript-Bibliothek selbst gehandhabt, oft durch das Einfügen von Inline-Stilen oder die Verwendung minimaler Standardstile, die sich gut in das PrestaShop Back Office integrieren.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- Keine. Das Modul verwendet keine `.tpl`-Dateien. Seine Funktionalität wird direkt über JavaScript in die vorhandene HTML-Struktur der Back Office-Produktliste eingefügt.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  - Das Modul erstellt keine benutzerdefinierten Datenbanktabellen.
  - Es speichert seine Konfiguration (z. B. die Einstellung „Zoom aktivieren“) in der Tabelle `ps_configuration` unter Verwendung eines Schlüssels wie `ZPLB_ENABLED`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayBackOfficeHeader` | Wird im `<head>`-Abschnitt jeder Back Office-Seite ausgeführt. | Wird verwendet, um das `zplb.js`-Skript nur dann bedingt zu laden, wenn die aktuelle Back Office-Seite die Produktliste (`AdminProducts`) ist. Dies stellt sicher, dass das Skript nicht unnötig auf anderen Admin-Seiten geladen wird, was die Leistung optimiert. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Bilder auf der Produktliste im Back Office zoomen“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.
