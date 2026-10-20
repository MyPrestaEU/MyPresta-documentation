---
title: "Zubehör auf Produktliste - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Zubehör auf Produktliste' von MyPresta.eu."
sidebar:
  label: "Zubehör auf Produktliste - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Accessories on list of products auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/accessories-on-list-of-products.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/accessories-on-list-of-products/)
>
> ---


# Zubehör auf Produktliste

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) werden typischerweise von PrestaShop selbst benötigt und sind für dieses Modul ausreichend.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation im Modul-Manager neben dem Modul „Zubehör auf Produktliste“ auf die Schaltfläche „Konfigurieren“. Dies führt Sie zum Hauptkonfigurationsbildschirm.

| Einstellung / Option | Was diese Einstellung bewirkt | Auswirkung der Änderung dieser Einstellung | Empfohlener Wert | Händlerszenario / Beispiel |
| --- | --- | --- | --- | --- |
| **Classic Theme Bug beheben** | Diese Einstellung behebt ein spezifisches Anzeigeproblem, das beim Standard-PrestaShop Classic Theme oder darauf basierenden Themes auftreten kann, bei dem Zubehör möglicherweise nicht korrekt gerendert wird. | *Wenn aktiviert:* Das Modul wendet eine Korrektur an, um sicherzustellen, dass Zubehör auf Produktlisten korrekt angezeigt wird, insbesondere mit dem Classic Theme. *Wenn deaktiviert:* Die Korrektur wird nicht angewendet. Wenn Sie das Classic Theme oder ein Derivat verwenden, wird Zubehör möglicherweise nicht korrekt angezeigt oder weist Layoutprobleme auf. | **JA** (Wenn Sie das Classic Theme oder ein darauf basierendes Theme verwenden) / **NEIN** (Wenn Sie ein vollständig benutzerdefiniertes Theme verwenden und keine Probleme auftreten) | Wenn Sie das Modul installiert haben und Zubehör auf Ihren Kategorieseiten nicht angezeigt wird oder fehlerhaft aussieht, ist die Aktivierung dieser Einstellung der erste Schritt zur Fehlerbehebung, insbesondere wenn Sie das Classic Theme verwenden. Wenn Ihr Theme stark angepasst ist und diesen Fehler nicht aufweist, können Sie es deaktiviert lassen, um potenzielle Konflikte zu vermeiden, obwohl es im Allgemeinen sicher ist, es zu aktivieren. |
| **Aktiviert / Deaktiviert** | Dies ist der Hauptschalter zum Aktivieren oder Deaktivieren der Modulfunktionalität in Ihrem gesamten Shop. | *Wenn aktiviert:* Das Modul zeigt Zubehör auf Produktlistenseiten wie beschrieben aktiv an. *Wenn deaktiviert:* Die Funktionalität des Moduls ist vollständig ausgeschaltet, und es wird kein Zubehör auf Produktlisten angezeigt. | **Aktiviert** | Sie haben die Einrichtung Ihres Zubehörs für Produkte abgeschlossen und möchten, dass es in Ihrem Live-Shop angezeigt wird. Sie würden dies aktivieren. Wenn Sie Zubehör vorübergehend für Wartungsarbeiten oder eine spezielle Kampagne ausblenden müssen, würden Sie es deaktivieren. |

### 2.2 Kurzübersicht der Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | Classic Theme Bug beheben | JA (für Classic Theme Benutzer) | Behebt Anzeigeprobleme für Zubehör auf Produktlisten mit dem Classic Theme. |
| Modulkonfigurationsseite | Aktiviert / Deaktiviert | Aktiviert | Schaltet die Kernfunktionalität des Moduls ein oder aus. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Zubehör wird auf meinen Produktlistenseiten nicht angezeigt.**
A:

1. **Modulstatus überprüfen**: Stellen Sie sicher, dass das Modul in seiner Konfiguration „Aktiviert“ ist.
2. **Zubehörzuweisung überprüfen**: Vergewissern Sie sich, dass den Hauptprodukten tatsächlich Zubehör auf der PrestaShop-Produktbearbeitungsseite (unter dem Tab „Zubehör“) zugewiesen ist.
3. **Theme-Kompatibilität**: Wenn Sie ein benutzerdefiniertes Theme verwenden, könnte es die Standard-Produktlistenvorlage so überschreiben, dass das Modul nicht korrekt eingehängt werden kann. Versuchen Sie, die Einstellung „Classic Theme Bug beheben“ zu aktivieren, auch wenn Sie nicht das Classic Theme verwenden, da dies einige allgemeine Anzeigeprobleme lösen könnte.
4. **Cache leeren**: Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal muss der PrestaShop-Cache aktualisiert werden, um neue Moduländerungen widerzuspiegeln.

**F: Das Zubehör sieht seltsam aus oder ist in meinem Shop falsch ausgerichtet.**
A:

1. **„Classic Theme Bug beheben“**: Versuchen Sie, diese Einstellung in der Modulkonfiguration zu aktivieren. Sie behebt speziell Layoutprobleme.
2. **Theme-CSS-Konflikt**: Das CSS Ihres Themes könnte mit dem Styling des Moduls in Konflikt stehen. Dies erfordert oft, dass ein Webmaster oder Entwickler das CSS überprüft und Anpassungen vornimmt.
3. **Cache leeren**: Leeren Sie immer Ihren PrestaShop-Cache, nachdem Sie Konfigurationsänderungen vorgenommen haben.

**F: Kann ich steuern, welches Zubehör für bestimmte Produkte angezeigt wird?**
A: Ja, das Modul verwendet die native Zubehörzuweisungsfunktion von PrestaShop. Um Zubehör für ein Produkt hinzuzufügen oder zu entfernen, gehen Sie zu **Katalog > Produkte**, bearbeiten Sie das gewünschte Produkt und navigieren Sie zum Tab „Zubehör“. Hier können Sie zugehörige Produkte suchen und hinzufügen/entfernen.

**F: Verlangsamt dieses Modul meinen Shop?**
A: Das Modul ist auf Effizienz ausgelegt. Es nutzt die vorhandenen Zubehördaten von PrestaShop. Wenn Sie jedoch Tausende von Produkten mit jeweils Dutzenden von Zubehörteilen haben und Ihre Serverressourcen begrenzt sind, kann jede zusätzliche Datenladung einen geringfügigen Einfluss haben. Für die meisten Shops ist der Leistungseinfluss vernachlässigbar.

## 4. Entwickler- & Webmaster-Leitfaden (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Zubehör auf Produktliste“ (`accol`) ist ein Standard-PrestaShop-Modul, das sich hauptsächlich auf die Front-Office-Anzeige konzentriert. Es erweitert `Module` und nutzt das Hook-System von PrestaShop, um Zubehördaten und -rendering in bestehende Produktlistenvorlagen einzufügen. Es führt keine neuen Datenbanktabellen oder komplexen benutzerdefinierten Controller ein, wodurch es leichtgewichtig und auf seinen Anzeigezweck fokussiert ist. Die Modullogik ist in seiner Haupt-PHP-Datei enthalten, mit zugehörigem JS und CSS für Styling und Interaktion.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Das Modul fügt seinen Inhalt direkt über Hooks in bestehende Produktlistenvorlagen ein.
- **Back-Office-Admin-Controller**: Keine. Die Konfiguration wird direkt über die Methode `getContent()` in der Hauptmoduldatei gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

- Das Modul definiert keine benutzerdefinierten Klassen im Verzeichnis `classes/`. Die gesamte Kernlogik befindet sich in der Hauptmoduldatei `accol.php`.
- Es interagiert mit den Standard-PrestaShop-Methoden `Product` und `Product::getAccessories()`, um Zubehördaten abzurufen.

### 4.4 JavaScript-Assets (`views/js/`)

- **`accol/js/accol.js`**
  - **Umfang**: Front-Office.
  - **Zweck**: Dieses Skript ist für die dynamische Anzeige und potenzielle Interaktionen mit den Zubehörlisten verantwortlich. Es könnte Logik für responsive Karussells (falls implementiert), das Ein- / Ausblenden von Zubehörblöcken oder AJAX-Aufrufe zum Hinzufügen von Zubehör zum Warenkorb enthalten (obwohl die primäre Funktion des Moduls die Anzeige ist, nicht das direkte AJAX-Hinzufügen zum Warenkorb). Es wird wahrscheinlich über den `displayHeader`- oder `header`-Hook geladen.
  - **Details**: Es kann Event-Listener an Zubehörelemente binden, deren Sichtbarkeit verwalten oder Drittanbieterbibliotheken für Karussells oder Slider initialisieren, falls das Modul solche Funktionen zur Zubehöranzeige implementiert.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`accol/css/accol.css`**
  - **Umfang**: Front-Office-Kundenstyling.
  - **Zweck**: Dieses Stylesheet stellt das notwendige visuelle Styling für die auf Produktseiten angezeigten Zubehörlisten bereit.
  - **Haupt-UI-Komponenten und Container**: Es stylt den Container für Zubehör, einzelne Zubehörartikel (Bilder, Namen, Preise) und potenziell Navigationselemente (wie Pfeile für Karussells).
  - **Wichtige CSS-Klassenselektoren**: Entwickler können Selektoren wie `.accol-accessories-list`, `.accol-accessory-item`, `.accol-accessory-image`, `.accol-accessory-name` usw. erwarten, die in der `custom.css` oder `theme.css` eines benutzerdefinierten Themes überschrieben werden können, um der Ästhetik des Themes zu entsprechen.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

- **Hook-Vorlagen (`views/templates/hook/`)**:
  - `accol/accol.tpl`: Dies ist die primäre Front-Office-Vorlage, die für das Rendern der Zubehörliste für ein bestimmtes Produkt verantwortlich ist. Sie wird wahrscheinlich in `displayProductListReviews` oder einen ähnlichen Hook eingehängt, der das Einfügen von Inhalten in die Produktlistenelement-Schleife ermöglicht. Sie empfängt ein Array von Zubehörprodukten und iteriert diese, um deren Bilder, Namen und potenziell Preise anzuzeigen.
- **Admin-Vorlagen (`views/templates/admin/`)**:
  - `accol/admin.tpl`: Diese Vorlage wird für die Konfigurationsseite des Moduls im PrestaShop Back Office verwendet. Sie enthält die HTML-Formularelemente für die Einstellungen „Classic Theme Bug beheben“ und „Aktiviert/Deaktiviert“ sowie alle Informationsmeldungen oder Speicherbuttons.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es stützt sich auf die native PrestaShop-Tabelle `ps_product_accessory` (die Produkte mit ihrem Zubehör verknüpft) und `ps_configuration` für seine eigenen Einstellungen (`ACCOL_FIX`).
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Wird verwendet, um CSS (`accol.css`) und JavaScript (`accol.js`) Assets für die Front-Office-Anzeige zu laden. |
| `displayProductListReviews` | Innerhalb der Produktlistenelement-Schleife, typischerweise unterhalb der Hauptinformationen des Produkts. | Der primäre Hook, der verwendet wird, um die `accol.tpl`-Vorlage einzufügen und das Zubehör für jedes Produkt in der Liste zu rendern. Dieser Hook ist oft in `product-list.tpl` oder ähnlichen Vorlagen verfügbar. |
| `header` | (Alias für `displayHeader` in vielen Kontexten, insbesondere älteren PrestaShop-Versionen). | Gleicher Zweck wie `displayHeader` – Laden von Assets. |
| `actionFrontControllerSetMedia` | Wird ausgeführt, wenn ein Front-Controller seine Medien-Assets festlegt. | Kann verwendet werden, um CSS/JS bedingt basierend auf dem aktuellen Seitenkontext hinzuzufügen, um sicherzustellen, dass Assets nur bei Bedarf geladen werden. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Zubehör auf Produktliste“ besuchen Sie bitte Ihr Kundenkonto bei MyPresta.eu. Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.
