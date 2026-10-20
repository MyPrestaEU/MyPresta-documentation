---
title: "Block der neuen Produkte auf der Startseite – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Block der neuen Produkte auf der Startseite“ von MyPresta.eu."
sidebar:
  label: "Block der neuen Produkte auf der Startseite – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Home new products block auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/home-new-products-block.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/home-new-products-block/)
>
> ---


# Block der neuen Produkte auf der Startseite

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise ausreichend. Es sind keine speziellen Serverkonfigurationen über eine Standard-PrestaShop-Hosting-Umgebung hinaus erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation neben dem Modul „Block der neuen Produkte auf der Startseite“ auf „Konfigurieren“, um auf dessen Einstellungen zuzugreifen.

#### Einstellung: Anzahl der anzuzeigenden Produkte

- **Was diese Einstellung bewirkt:** Dieses Feld ermöglicht es Ihnen zu steuern, wie viele Ihrer neuesten Produkte im Block auf Ihrer Startseite angezeigt werden.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Bei Einstellung auf eine höhere Zahl (z. B. 10):* Mehr neue Produkte werden im Block sichtbar sein, was Kunden eine größere Auswahl Ihrer neuesten Artikel bietet. Dies könnte den Block länger machen oder mehr Scrollen erfordern.
  - *Bei Einstellung auf eine niedrigere Zahl (z. B. 4):* Weniger neue Produkte werden angezeigt, wodurch der Block kompakter wird. Dies kann nützlich sein, wenn Sie begrenzten Platz haben oder nur die absolut frischesten Artikel hervorheben möchten.
- **Empfohlener Wert:** Ein guter Ausgangspunkt sind `8` oder `12` Produkte. Dies bietet eine anständige Auswahl, ohne die Seite zu überladen.
- **Händlerszenario / Beispiel:** Wenn Sie ein Modegeschäft betreiben und jede Woche 20 neue Artikel hinzufügen, stellt die Einstellung auf `12` sicher, dass immer eine gute Vielfalt sichtbar ist. Wenn Sie nur wenige neue handwerkliche Produkte pro Monat hinzufügen, könnten `4` oder `6` angemessener sein, um den Block prägnant zu halten.

#### Einstellung: Auf Startseite anzeigen

- **Was diese Einstellung bewirkt:** Dies ist ein einfacher EIN/AUS-Schalter, der steuert, ob der „Block der neuen Produkte auf der Startseite“ auf der Startseite Ihres Shops sichtbar ist.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Der Block mit Ihren neuen Produkten erscheint auf Ihrer Startseite, wie in Abschnitt 2 beschrieben.
  - *Wenn deaktiviert (NEIN):* Der Block wird von Ihrer Startseite ausgeblendet. Dies kann nützlich sein, wenn Sie ihn vorübergehend entfernen möchten, ohne das Modul zu deinstallieren, oder wenn Sie andere Methoden bevorzugen, um neue Produkte zu präsentieren.
- **Empfohlener Wert:** `JA` (Aktiviert). Der Hauptzweck dieses Moduls ist es, neue Produkte auf der Startseite anzuzeigen.
- **Händlerszenario / Beispiel:** Sie könnten es vorübergehend deaktivieren, wenn Sie eine spezielle saisonale Kampagne durchführen, die den gesamten Startseitenbereich für Werbebanner benötigt, und es dann nach Beendigung der Kampagne wieder aktivieren.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | Anzahl der anzuzeigenden Produkte | 8-12 | Steuert, wie viele neue Produkte im Block erscheinen. Eine höhere Zahl zeigt mehr, eine niedrigere Zahl macht ihn kompakter. |
| Modulkonfigurationsseite | Auf Startseite anzeigen | JA | Schaltet die Sichtbarkeit des Blocks der neuen Produkte auf Ihrer Startseite um. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Mein Block der neuen Produkte wird nach der Installation nicht auf der Startseite angezeigt.**
A:

1. **Modulkonfiguration prüfen:** Gehen Sie zu **Module > Modul-Manager**, suchen Sie „Block der neuen Produkte auf der Startseite“ und klicken Sie auf „Konfigurieren“. Stellen Sie sicher, dass „Auf Startseite anzeigen“ auf `JA` eingestellt ist.
2. **Cache leeren:** Manchmal verhindert der PrestaShop-Cache, dass Änderungen sofort angezeigt werden. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie oben rechts auf „Cache leeren“.
3. **Hook-Position prüfen:** Obwohl das Modul so konzipiert ist, dass es sich automatisch einhakt, können manchmal Theme-Konflikte oder andere Module stören. Gehen Sie zu **Design > Positionen**. Suchen Sie nach `displayHome` (oder `displayHomeTabContent`, wenn Ihr Theme Tabs verwendet). Stellen Sie sicher, dass `home-new-products-block` in einem dieser Hooks aufgeführt und aktiviert ist. Falls nicht, müssen Sie möglicherweise ein Modul zu `displayHome` „transplantieren“.

**F: Der Block zeigt alte Produkte an, nicht neue.**
A: Das Modul zeigt Produkte basierend auf ihrem „Hinzufügedatum“ in PrestaShop an. Stellen Sie sicher, dass beim Hinzufügen neuer Produkte deren Erstellungsdatum korrekt auf das aktuelle Datum eingestellt ist. Wenn Sie Produkte mit alten Daten importiert haben, werden sie möglicherweise nicht als „neu“ angezeigt. Sie müssen möglicherweise das Feld `date_add` für diese Produkte manuell in Ihrer Datenbank aktualisieren (fortgeschrittene Aufgabe, konsultieren Sie einen Entwickler) oder sie erneut hinzufügen.

**F: Ich möchte ändern, wo der Block auf meiner Startseite erscheint (z. B. weiter oben oder in einer Spalte).**
A: Sie können die Position des Moduls mit der integrierten „Live Edit“-Funktion von PrestaShop anpassen.

1. Gehen Sie zu **Design > Positionen**.
2. Klicken Sie auf die Schaltfläche „Live Edit starten“ (normalerweise oben rechts).
3. Navigieren Sie zu Ihrer Startseite.
4. Sie sollten Umrisse um verschiedene Modulblöcke sehen. Suchen Sie den „Block der neuen Produkte auf der Startseite“ und ziehen Sie ihn an die gewünschte Position. Sie können auch die Schaltfläche „Modul transplantieren“ verwenden, um es an einen anderen Hook zu verschieben (z. B. `displayLeftColumn`, `displayRightColumn`, `displayFooter`).

**F: Der Block sieht seltsam aus oder passt nicht zum Styling meines Themes.**
A: Dieses Modul verwendet Standard-PrestaShop-Produktanzeigevorlagen, die die meisten Styling-Merkmale Ihres Themes übernehmen sollten. Wenn es seltsam aussieht:

1. **Cache leeren:** Wie oben beschrieben, leeren Sie Ihren PrestaShop-Cache.
2. **Theme-Overrides:** Ihr Theme könnte spezifisches CSS haben, das Konflikte verursacht. Dies erfordert normalerweise einen Webentwickler, um das CSS Ihrer Website zu überprüfen und möglicherweise benutzerdefinierte Stile zur `custom.css`-Datei Ihres Themes oder einer ähnlichen Datei hinzuzufügen, um die Standardeinstellungen zu überschreiben.
3. **Modul-Update:** Stellen Sie sicher, dass Sie die neueste Version des Moduls von MyPresta.eu haben.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Block der neuen Produkte auf der Startseite“ ist ein unkompliziertes PrestaShop-Modul, das der Standardmodulstruktur folgt. Es verwendet hauptsächlich die `Module`-Klasse, um seinen Lebenszyklus (Installation, Deinstallation) zu verwalten, und `hook`-Methoden, um Inhalte im Front Office zu rendern. Es ruft Produktdaten direkt aus den PrestaShop-Kerndatenbanktabellen ab und nutzt bestehende `Product`- und `Category`-Funktionalitäten. Es gibt keine benutzerdefinierten Controller oder komplexen ObjectModels, was es leichtgewichtig und einfach zu integrieren macht.

### 4.2 Controller (`controllers/`)

- Dieses Modul enthält **keine** benutzerdefinierten Front-Office- oder Back-Office-Controller. Die gesamte Logik ist in der Hauptmoduldatei gekapselt und wird über Hooks ausgeführt.

### 4.3 Kernklassen & Modelle (`classes/`)

- Dieses Modul enthält **keine** benutzerdefinierten Klassen oder ObjectModels in einem `classes/`-Verzeichnis. Es stützt sich auf die PrestaShop-Kernklassen `Product` und `Category` für den Datenabruf.

### 4.4 JavaScript-Assets (`views/js/`)

- Dieses Modul enthält **keine** benutzerdefinierten JavaScript-Dateien. Jedes dynamische Verhalten (z. B. Karussells) würde typischerweise vom vorhandenen JS des Themes oder einem separaten Modul gehandhabt.

### 4.5 CSS-Stylesheets (`views/css/`)

- Dieses Modul enthält **keine** benutzerdefinierten CSS-Dateien. Es stützt sich auf das Standard-Styling des Themes für Produktlisten und -raster. Entwickler, die diesen Block speziell gestalten möchten, sollten seine HTML-Struktur (z. B. `div#home_new_products`) in der `custom.css`-Datei ihres Themes oder einer ähnlichen Datei ansprechen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- Dieses Modul verwendet hauptsächlich eine einzige Template-Datei zum Rendern seines Inhalts.

  - **Hook-Templates (`views/templates/hook/`)**:
    - `views/templates/hook/home-new-products-block.tpl`: Dies ist die Haupt-Template-Datei, die für das Rendern des Blocks der neuen Produkte auf der Startseite verantwortlich ist.
      - **Hook:** Primär für `displayHome` (oder `displayHomeTabContent` in einigen Themes) vorgesehen.
      - **Zweck:** Es iteriert durch die `$products`-Variable (ein Array von `Product`-Objekten), die von der `hookDisplayHome`-Methode übergeben wird, und zeigt das Bild, den Namen, den Preis und den „In den Warenkorb“-Button jedes Produkts an, typischerweise unter Verwendung einer Schleife und einschließlich einer Standard-Produktlistenelement-Vorlage (z. B. `product-miniature.tpl` oder ähnliches, abhängig von der PrestaShop-Version und dem Theme).

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt **keine** benutzerdefinierten Datenbanktabellen.
  - Es speichert seine Konfigurationseinstellungen (z. B. `HOME_NEW_PRODUCTS_NBR`, `HOME_NEW_PRODUCTS_DISPLAY`) in der Standardtabelle `ps_configuration`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHome` | Rendert Inhalte im Hauptbereich der Startseite. | Zeigt den Block der neuen Produkte auf der Startseite des Shops an. |
| `displayHeader` | Wird im `<head>`-Bereich jeder Seite ausgeführt. | Wird verwendet, um Assets (CSS/JS) zu registrieren, falls vorhanden, obwohl dieses Modul es dafür nicht verwendet. Könnte für Meta-Tags oder andere globale Elemente verwendet werden. |
| `displayLeftColumn` | Rendert Inhalte in der linken Seitenleiste. | Ermöglicht das Verschieben des Blocks der neuen Produkte in die linke Spalte über „Design > Positionen“. |
| `displayRightColumn` | Rendert Inhalte in der rechten Seitenleiste. | Ermöglicht das Verschieben des Blocks der neuen Produkte in die rechte Spalte über „Design > Positionen“. |
| `displayFooter` | Rendert Inhalte in der Fußzeile des Shops. | Ermöglicht das Verschieben des Blocks der neuen Produkte in die Fußzeile über „Design > Positionen“. |
| `actionProductAdd` | Wird nach dem Hinzufügen eines neuen Produkts ausgeführt. | Könnte zum Leeren des Caches oder zur Neuindizierung verwendet werden, obwohl dieses Modul es nicht explizit verwendet. |
| `actionProductUpdate` | Wird nach dem Aktualisieren eines Produkts ausgeführt. | Könnte zum Leeren des Caches oder zur Neuindizierung verwendet werden, obwohl dieses Modul es nicht explizit verwendet. |
| `actionProductDelete` | Wird nach dem Löschen eines Produkts ausgeführt. | Könnte zum Leeren des Caches oder zur Neuindizierung verwendet werden, obwohl dieses Modul es nicht explizit verwendet. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Block der neuen Produkte auf der Startseite“ besuchen Sie bitte Ihr MyPresta.eu-Kundenkonto. Sie können die neuesten Versionen herunterladen und direkt auf Support-Ressourcen von [MyPresta.eu](https://mypresta.eu) zugreifen.
