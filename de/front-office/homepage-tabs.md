---
title: "Homepage-Tabs – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Homepage-Tabs“ von MyPresta.eu."
sidebar:
  label: "Homepage-Tabs – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Homepage tabs auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/homepage-tabs.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/homepage-tabs/)
>
> ---


# Homepage-Tabs

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise ausreichend. Es sind keine ungewöhnlichen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation im Modul-Manager neben dem Modul „Homepage-Tabs“ auf „Konfigurieren“. Dies führt Sie zum Hauptkonfigurationsbildschirm.

Die Konfigurationsseite des Moduls ist unkompliziert und konzentriert sich hauptsächlich darauf, sicherzustellen, dass das Modul Updates empfangen kann.

- **Was diese Einstellung bewirkt:** Dieser Abschnitt verwaltet die Fähigkeit des Moduls, nach Updates von MyPresta.eu zu suchen und diese zu empfangen. Die Aktualisierung Ihrer Module ist entscheidend für Sicherheit, Leistung und Kompatibilität mit neuen PrestaShop-Versionen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (Standard):* Das Modul sucht regelmäßig auf MyPresta.eu nach neuen Versionen. Wenn ein Update verfügbar ist, werden Sie in Ihrem PrestaShop Back Office benachrichtigt, sodass Sie die neueste Version einfach herunterladen und installieren können. Dies stellt sicher, dass Ihr Modul kompatibel bleibt und von den neuesten Funktionen und Fehlerbehebungen profitiert.
  - *Wenn deaktiviert:* Das Modul sucht nicht nach Updates. Sie werden nicht über neue Versionen benachrichtigt und verpassen möglicherweise wichtige Verbesserungen, Sicherheitspatches oder Kompatibilitätskorrekturen. Sie müssten manuell auf MyPresta.eu nach Updates suchen.
- **Empfohlener Wert:** **JA (Aktiviert)**. Es wird dringend empfohlen, diese Einstellung aktiviert zu lassen, um sicherzustellen, dass Ihr Modul immer aktuell und sicher ist.
- **Händlerszenario / Beispiel:** Stellen Sie sich vor, PrestaShop veröffentlicht eine neue Nebenversion (z. B. 8.1.5). Ein Update für das Modul „Homepage-Tabs“ könnte veröffentlicht werden, um die volle Kompatibilität zu gewährleisten. Mit aktivierten Updates würden Sie benachrichtigt und könnten einfach aktualisieren, wodurch potenzielle Probleme vermieden werden. Wenn deaktiviert, könnten Ihre Tabs nach dem PrestaShop-Update nicht mehr richtig funktionieren, und Sie wüssten nicht warum, bis Sie manuell nach Modul-Updates suchen.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | Update-Prüfungen (mypresta\_updates, update\_, updatev\_) | JA (Aktiviert) | Ermöglicht automatische Prüfungen auf Modul-Updates von MyPresta.eu, um Kompatibilität, Sicherheit und Zugang zu neuen Funktionen zu gewährleisten. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Homepage-Tabs werden nach der Installation nicht angezeigt.**
A:

1. **Modulposition überprüfen:** Gehen Sie in Ihrem PrestaShop Back Office zu **Design > Positionen**. Suchen Sie nach `displayHome`. Stellen Sie sicher, dass das Modul „Homepage-Tabs“ an `displayHome` gehookt ist. Falls nicht, verwenden Sie die Schaltfläche „Modul transplantieren“, um es hinzuzufügen.
2. **Cache leeren:** Leeren Sie immer Ihren PrestaShop-Cache, nachdem Sie Module installiert oder konfiguriert haben. Gehen Sie zu **Erweiterte Parameter > Leistung** und klicken Sie oben rechts auf „Cache leeren“.
3. **Auf Theme-Konflikte prüfen:** Einige benutzerdefinierte Themes können den `displayHome`-Hook überschreiben oder spezifische Stile haben, die das Modul ausblenden. Wechseln Sie vorübergehend zum Standard-PrestaShop-Theme (Classic), um zu sehen, ob die Tabs erscheinen. Wenn ja, erfordert Ihr Theme benutzerdefinierte CSS- oder Template-Anpassungen.

**F: Die Produkte in den Tabs sehen nicht richtig aus (z. B. falsche Größe, falsch ausgerichtet).**
A: Dies ist typischerweise ein Styling-Problem, das mit dem Theme Ihres Shops zusammenhängt. Das Modul selbst liefert die Produktdaten, aber Ihr Theme bestimmt, wie Produktlisten angezeigt werden.

1. **Cache leeren:** Leeren Sie erneut Ihren PrestaShop-Cache.
2. **Theme-CSS:** Das CSS Ihres Themes könnte mit dem Standard-Styling des Moduls in Konflikt stehen. Ein Webentwickler kann die Elemente mit den Browser-Entwicklertools überprüfen und benutzerdefinierte CSS-Überschreibungen in der `custom.css`-Datei Ihres Themes anwenden, um das Erscheinungsbild zu korrigieren.

**F: Kann ich die Reihenfolge der Tabs oder welche Produkte darin erscheinen, ändern?**
A: Dieses Modul stellt die *Funktionalität* der Homepage-Tabs (Beliebt, Neu, Bestseller, Im Angebot) wieder her. Die spezifischen angezeigten Produkttypen (z. B. „Beliebte Produkte“) werden durch die Kernlogik von PrestaShop für diese Kategorien bestimmt. Dieses Modul bietet keine Optionen, um Produkte für jeden Tab manuell auszuwählen oder die Tabs selbst über seine Konfiguration neu anzuordnen. Für erweiterte Anpassungen wie benutzerdefinierte Produktauswahlen oder Tab-Reihenfolge benötigen Sie typischerweise ein fortschrittlicheres Modul oder eine benutzerdefinierte Entwicklung.

**F: Das Modul ist installiert, aber ich sehe keine Konfigurationsoptionen außer den Update-Einstellungen.**
A: Dieses Modul wurde entwickelt, um die entfernte Kernfunktion der PrestaShop-Homepage-Tabs wieder zu aktivieren. Seine Hauptfunktion besteht darin, die Tabs wieder erscheinen zu lassen, wobei die Standardlogik von PrestaShop für „Beliebte“, „Neue“, „Bestseller“ und „Im Angebot“ Produkte verwendet wird. Daher verfügt es nicht über umfangreiche Konfigurationsoptionen für die Inhaltsverwaltung innerhalb der Tabs selbst, da diese Logik vom PrestaShop-Kern gehandhabt wird.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Homepage-Tabs“ (`homepagetabs`) ist ein leichtgewichtiges PrestaShop-Modul, das entwickelt wurde, um eine zentrale Front-Office-Funktion wieder zu aktivieren, die in neueren PrestaShop-Versionen entfernt wurde. Es funktioniert hauptsächlich durch das Hooking in `displayHome`, um die Produkt-Tabs zu rendern, und `displayHeader`, um notwendige Assets einzubinden. Es nutzt die bestehenden PrestaShop-Produktabrufmechanismen für „Beliebte“, „Neue“, „Bestseller“ und „Im Angebot“ Produkte und fungiert effektiv als Brücke zur Wiederherstellung der visuellen Komponente. Das Modul folgt einem Standard-PrestaShop-MVC-Muster, obwohl seine primäre Logik für das Rendering innerhalb der Hauptmodulklasse (`homepagetabs.php`) liegt.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Die Front-Office-Anzeigelogik des Moduls wird vollständig von der Moduldatei `homepagetabs.php` über Hooks gehandhabt.
- **Back-Office-Admin-Controller**: Keine. Alle Konfigurationen werden direkt in der Methode `getContent()` der Hauptmodulklasse gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

- Keine. Das Modul definiert keine benutzerdefinierten Klassen oder `ObjectModel`-Instanzen. Es verlässt sich auf die Kernklassen von PrestaShop für den Abruf von Produktdaten.

### 4.4 JavaScript-Assets (`views/js/`)

- `homepagetabs/views/js/homepagetabs.js`
  - **Umfang**: Front-Office.
  - **Verantwortlichkeit**: Dieses Skript ist für das interaktive Verhalten der Homepage-Tabs verantwortlich. Es behandelt wahrscheinlich:
    - Das Binden von Klick-Ereignis-Listenern an die Tab-Header.
    - Das Umschalten der Sichtbarkeit von Produktinhaltsblöcken basierend auf dem aktiven Tab.
    - Das Hinzufügen/Entfernen aktiver CSS-Klassen zu Tab-Headern und -Inhalten.
    - Potenziell die Handhabung von AJAX-Anfragen, wenn Produktinhalte dynamisch geladen werden (obwohl es für dieses Modul wahrscheinlicher ein einfacher Show/Hide-Mechanismus für vorgerenderte Inhalte ist).
    - Sicherstellen, dass die Tabs auf verschiedenen Bildschirmgrößen und Geräten korrekt funktionieren.

### 4.5 CSS-Stylesheets (`views/css/`)

- `homepagetabs/views/css/homepagetabs.css`
  - **Umfang**: Front-Office-Kunden-Styling.
  - **Verantwortlichkeit**: Dieses Stylesheet bietet die Standard-visuelle Darstellung für die Homepage-Tabs und deren Inhalt. Es definiert Stile für:
    - Den Tab-Container selbst.
    - Einzelne Tab-Header (z. B. `ul.home-tabs li a`).
    - Den aktiven Tab-Zustand (z. B. `ul.home-tabs li.active a`).
    - Den Produktgitter-Container für jeden Tab (z. B. `.tab-content`).
    - Grundlegende responsive Anpassungen für verschiedene Bildschirmgrößen.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können**: Entwickler können Klassen wie `.home-tabs`, `.home-tabs li`, `.home-tabs li.active`, `.tab-content` und die Produktgitterelemente innerhalb von `.tab-content` ansprechen, um das Erscheinungsbild des Moduls nahtlos in ihr benutzerdefiniertes Theme zu integrieren.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - `homepagetabs/views/templates/hook/homepagetabs.tpl`
    - **Hook**: `displayHome`
    - **Zweck**: Dies ist das primäre Front-Office-Template, das für das Rendern des gesamten Homepage-Tabs-Blocks verantwortlich ist. Es enthält die HTML-Struktur für die Tab-Header (z. B. `<ul>` für Tab-Titel) und die entsprechenden Inhaltsbereiche (z. B. `<div>` für Produktlisten). Es iteriert durch die Produktdaten, die ihm von der `hookDisplayHome()`-Methode des Moduls übergeben werden, und zeigt „Beliebte“, „Neue“, „Bestseller“ und „Im Angebot“ Produkte in ihren jeweiligen Tab-Inhaltsbereichen an. Dieses Template ist der Ort, an dem die Produktkarten (Bilder, Namen, Preise, In-den-Warenkorb-Buttons) für jeden Produkttyp gerendert werden.
- **Admin-Templates (`views/templates/admin/`)**:
  - `homepagetabs/views/templates/admin/homepagetabs.tpl`
    - **Zweck**: Dieses Template rendert das Konfigurationsformular des Moduls im PrestaShop Back Office. Es zeigt die Einstellungen für Update-Prüfungen (`mypresta_updates`, `update_`, `updatev_`) und alle anderen Standard-Modulkonfigurationselemente an.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es speichert seine Konfigurationseinstellungen (z. B. `mypresta_updates`) in der Standardtabelle `ps_configuration`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHome` | Rendert Inhalte auf der Homepage des Shops. | Dieser Hook wird verwendet, um die gesamte HTML-Struktur der Homepage-Tabs auszugeben, einschließlich Tab-Headern und Produktlisten. |
| `displayHeader` | Wird im `<head>`-Bereich jeder Front-Office-Seite ausgeführt. | Dieser Hook wird verwendet, um die CSS- (`homepagetabs.css`) und JavaScript- (`homepagetabs.js`) Dateien des Moduls einzubinden, um die korrekte Gestaltung und interaktive Funktionalität der Tabs zu gewährleisten. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und weitere Unterstützung zum Modul „Homepage-Tabs“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Fragen oder Problemen zur Verfügung.
