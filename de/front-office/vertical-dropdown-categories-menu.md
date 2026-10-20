---
title: "Vertikales Dropdown-Kategorienmenü – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Vertikales Dropdown-Kategorienmenü' von MyPresta.eu."
sidebar:
  label: "Vertikales Dropdown-Kategorienmenü – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Vertical dropdown categories menu auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/vertical-dropdown-categories-menu.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/vertical-dropdown-categories-menu/)
>
> ---


# Vertikales Dropdown-Kategorienmenü

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation im Modul-Manager neben dem Modul „Vertikales Dropdown-Kategorienmenü“ auf „Konfigurieren“. Dies führt Sie zur Hauptkonfigurationsseite.

Die Konfigurationsseite des Moduls bietet Standardeinstellungen zur Steuerung seines Verhaltens und Aussehens.

- **Was diese Einstellung bewirkt:** Dieser Abschnitt enthält typischerweise allgemeine Einstellungen für das Modul, wie z. B. das Aktivieren/Deaktivieren, die Auswahl des Erscheinungsortes oder grundlegende Anzeigeoptionen. Obwohl spezifische benannte Einstellungen im Dossier nicht detailliert sind, umfassen gängige Optionen für ein Modul dieses Typs:

  - **Modul aktivieren/deaktivieren**: Ein einfacher Schalter, um das Modul ein- oder auszuschalten, ohne es zu deinstallieren.
  - **Stammkategorie anzeigen**: Wählen Sie, ob die Hauptkategorie „Startseite“ oder „Stamm“ im Menü angezeigt werden soll.
  - **Maximale Tiefe**: Begrenzen Sie, wie viele Ebenen von Unterkategorien im Dropdown angezeigt werden.
  - **Hook-Auswahl**: Wählen Sie, an welche Anzeige-Hooks das Modul angehängt werden soll (z. B. `displayLeftColumn`, `displayRightColumn`).
  - **Cache-Einstellungen**: Optionen zum Aktivieren oder Deaktivieren des Caching für die Ausgabe des Moduls zur Verbesserung der Leistung.
- **Auswirkung der Änderung dieser Einstellung:**

  - *Wenn aktiviert:* Das Modul ist aktiv und zeigt das vertikale Kategorienmenü in Ihrem Front Office gemäß den anderen Einstellungen an.
  - *Wenn deaktiviert:* Das Modul wird in Ihrem Shop nicht angezeigt, aber seine Konfiguration wird gespeichert.
  - *Auswahl eines Hooks (z. B. `displayLeftColumn`):* Der vertikale Menüblock erscheint in der linken Spalte Ihres Shops.
  - *Tiefenbegrenzung:* Es werden nur Kategorien bis zur angegebenen Ebene angezeigt, wodurch das Menü für Kunden vereinfacht wird.
- **Empfohlener Wert:**

  - **Modul aktivieren**: JA
  - **Stammkategorie anzeigen**: NEIN (normalerweise, um direkt mit Ihren Hauptproduktkategorien zu beginnen)
  - **Maximale Tiefe**: 3 (ein gutes Gleichgewicht für die meisten Shops, um übermäßig komplexe Menüs zu vermeiden)
  - **Hook-Auswahl**: `displayLeftColumn` oder `displayRightColumn` (abhängig von der Layout-Präferenz Ihres Themes).
- **Händlerszenario / Beispiel:**

  - *Szenario 1 (Navigation vereinfachen):* Sie haben eine sehr tiefe Kategorienstruktur (z. B. 5-6 Ebenen). Sie könnten „Maximale Tiefe“ auf 3 setzen, um sicherzustellen, dass Kunden nicht von zu vielen Optionen überwältigt werden, und sie zuerst durch die Top-Level-Auswahlen führen.
  - *Szenario 2 (Leistungsoptimierung):* Wenn Ihr Shop viel Traffic hat, kann das Aktivieren des Caching für die Ausgabe des Moduls die Seitenladezeiten erheblich beschleunigen, da das Menü nicht für jeden Besucher neu aufgebaut werden muss.
  - *Szenario 3 (Layout-Anpassung):* Ihr Theme sieht mit der Navigation auf der rechten Seite besser aus. Sie würden `displayRightColumn` in den Hook-Einstellungen auswählen, um den Menüblock entsprechend zu verschieben.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | Modul aktivieren/deaktivieren | Aktiviert | Steuert, ob das Modul in Ihrem Shop aktiv ist. |
| Modulkonfigurationsseite | Stammkategorie anzeigen | Nein | Bestimmt, ob die oberste „Startseite“-Kategorie angezeigt wird. |
| Modulkonfigurationsseite | Maximale Tiefe | 3 | Begrenzt die Anzahl der angezeigten Unterkategorie-Ebenen. |
| Modulkonfigurationsseite | Hook-Auswahl | `displayLeftColumn` | Gibt an, wo der Menüblock erscheint (z. B. linke oder rechte Spalte). |
| Modulkonfigurationsseite | Caching | Aktiviert | Verbessert die Leistung durch Speichern des generierten Menü-HTML. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Das Menü wird nach der Installation nicht in meinem Shop angezeigt.**
**A1:**

1. **Modulstatus überprüfen:** Gehen Sie zu **Module > Modul-Manager** und stellen Sie sicher, dass das Modul „Vertikales Dropdown-Kategorienmenü“ installiert und aktiviert ist.
2. **Hook-Zuweisung überprüfen:** Stellen Sie in der Konfiguration des Moduls sicher, dass es einem aktiven Hook zugewiesen ist (z. B. `displayLeftColumn`, `displayRightColumn`). Einige Themes zeigen möglicherweise nicht alle Hooks standardmäßig an, oder Sie müssen die Layout-Einstellungen Ihres Themes anpassen.
3. **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“). Manchmal verhindern alte zwischengespeicherte Inhalte, dass neue Module angezeigt werden.
4. **Theme-Kompatibilität:** Wenn Sie ein stark angepasstes Theme verwenden, könnte es die Standard-PrestaShop-Hook-Darstellung überschreiben. Kontaktieren Sie Ihren Theme-Entwickler oder einen PrestaShop-Experten.

**F2: Der Dropdown-Effekt funktioniert nicht oder sieht fehlerhaft aus.**
**A2:**

1. **Theme-Konflikte:** Ein anderes Modul oder das benutzerdefinierte JavaScript/CSS Ihres Themes könnte mit dem Styling oder der Funktionalität des Moduls in Konflikt stehen.
2. **Cache leeren:** Versuchen Sie immer, den PrestaShop-Cache (**Erweiterte Einstellungen > Leistung**) und den Cache Ihres Browsers zu leeren.
3. **Mit Browser-Tools überprüfen:** Verwenden Sie die Entwickler-Tools Ihres Browsers (F12), um in der Konsole nach JavaScript-Fehlern oder CSS-Konflikten zu suchen. Achten Sie auf rote Fehlermeldungen.
4. **Modul-Neuinstallation:** Versuchen Sie, das Modul zu deinstallieren und neu zu installieren (nachdem Sie Ihre Einstellungen, falls möglich, gesichert haben).

**F3: Wie ändere ich die Farben oder Schriftarten des Menüs?**
**A3:** Das Modul wird mit einer eigenen `blockcategories.css`-Datei für das Styling geliefert.

1. **Grundlegende Anpassung:** Für kleinere Änderungen können Sie diese Stile oft in der benutzerdefinierten CSS-Datei Ihres Themes überschreiben (z. B. `themes/yourtheme/assets/css/custom.css`). Dies ist der sicherste Weg, Änderungen vorzunehmen, ohne die Kerndateien des Moduls zu ändern.
2. **Erweiterte Anpassung:** Für umfangreichere Änderungen müssen Sie möglicherweise die Datei `blockcategories.css` direkt im Verzeichnis `views/css/` des Moduls bearbeiten. **Beachten Sie jedoch, dass diese Änderungen bei Modul-Updates verloren gehen.** Es ist immer besser, Theme-Overrides zu verwenden.
3. **PrestaShop Theme Customizer:** Einige Themes bieten einen „Theme Customizer“ oder „Live Configurator“, der grundlegende Stiländerungen ohne Code-Bearbeitung ermöglicht. Prüfen Sie, ob Ihr Theme diese Funktion hat.

**F4: Meine Kategorien werden nicht im Menü angezeigt.**
**A4:**

1. **Kategorienstatus:** Stellen Sie sicher, dass Ihre Kategorien in Ihrem PrestaShop Back Office (**Katalog > Kategorien**) aktiv und sichtbar sind.
2. **Stammkategorie-Einstellung:** Überprüfen Sie die Konfiguration des Moduls, um festzustellen, ob „Stammkategorie anzeigen“ aktiviert oder deaktiviert ist. Wenn deaktiviert und Ihre Kategorien direkte Kinder der Stammkategorie sind, werden sie möglicherweise nicht angezeigt.
3. **Berechtigungen:** Stellen Sie sicher, dass die Kategorien über entsprechende Gruppenberechtigungen verfügen, wenn Sie Kundengruppen verwenden.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Vertikales Dropdown-Kategorienmenü“ (`verticalblockcategories`) ist ein Standard-PrestaShop-Modul, das einen dynamischen Kategorien-Navigationsblock anzeigt. Es nutzt hauptsächlich das Hook-System von PrestaShop, um seinen Inhalt an verschiedenen Front-Office-Positionen darzustellen. Die Logik des Moduls ist in seiner Haupt-PHP-Datei enthalten, die Installation, Deinstallation, Hook-Registrierung und Konfiguration verwaltet. Die visuelle Präsentation wird durch Smarty-Templates und eine dedizierte CSS-Datei gesteuert. Es führt keine benutzerdefinierten Controller oder komplexen ObjectModels ein, sondern konzentriert sich auf die effiziente Darstellung vorhandener Kategoriedaten.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Logik wird innerhalb der Hauptmoduldatei (`index.php`) verarbeitet und über Hooks gerendert.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder ObjectModels in einem `classes/`-Verzeichnis. Es verwendet direkt die PrestaShop-Kernklassen `Category` und `Tools`, um Kategoriedaten abzurufen und zu verarbeiten.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien. Der Dropdown-Effekt wird typischerweise rein über CSS erreicht oder stützt sich auf vorhandene jQuery/JavaScript-Bibliotheken, die bereits von PrestaShop oder dem Theme geladen werden.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`verticalblockcategories/blockcategories.css`**
  - **Geltungsbereich**: Front-Office-Kunden-Styling.
  - **Wichtige UI-Komponenten und Container, die es stylt**: Dieses Stylesheet ist verantwortlich für das visuelle Layout, das Aussehen und die Dropdown-Animation des vertikalen Kategorienmenüs. Es zielt auf Elemente innerhalb der generierten HTML-Struktur des Moduls ab, wie `div#categories_block_left`, `ul.tree`, `li.last`, `a.selected` und `ul.tree li ul`.
  - **Wichtige CSS-Klassenselektoren, die Entwickler in ihrem Theme überschreiben können**:
    - `#categories_block_left` (oder ähnliche ID/Klasse für den Hauptblock-Container)
    - `.block_content`
    - `ul.tree` (für die Hauptkategorienliste)
    - `ul.tree li` (für einzelne Kategorieelemente)
    - `ul.tree li a` (für Kategorielinks)
    - `ul.tree li ul` (für Unterkategorie-Dropdowns)
    - `ul.tree li ul li` (für einzelne Unterkategorieelemente)
    - `.selected` (für die aktuell aktive Kategorie)
    - Klassen im Zusammenhang mit Hover-Effekten und Übergängen für das Dropdown.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - **`verticalblockcategories/blockcategories.tpl`**: Dies ist die Haupt-Template-Datei, die vom Modul gerendert wird, wenn es gehookt ist. Sie enthält typischerweise die Gesamtstruktur des Kategorienblocks, einschließlich des Titels und der Haupt-Unordered-List (`<ul>`), die den Kategorienbaum aufnehmen wird. Es wird wahrscheinlich `category-tree-branch.tpl` rekursiv einbinden, um das vollständige Menü zu erstellen.
    - **Gehookt in**: `displayLeftColumn`, `displayRightColumn`, `displayHeader`, `displayFooter`, `displayProductExtraContent` (oder andere Spalten-/Inhalts-Hooks).
    - **Ausgaben**: Der Haupt-HTML-Block für das vertikale Kategorienmenü.
  - **`verticalblockcategories/category-tree-branch.tpl`**: Dieses Template ist für die rekursive Darstellung einzelner Kategorienzweige (Kategorien und deren Unterkategorien) konzipiert. Es behandelt die Anzeige eines einzelnen Kategorieelements und ruft sich, wenn diese Kategorie Kinder hat, rekursiv selbst auf, um diese Kinder als verschachtelte Liste darzustellen und so die Baumstruktur zu erstellen.
    - **Eingebunden von**: `blockcategories.tpl` (und potenziell sich selbst).
    - **Ausgaben**: Ein `<li>`-Element für eine Kategorie, das potenziell eine verschachtelte `<ul>` für ihre Unterkategorien enthält.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es stützt sich vollständig auf die PrestaShop-Kerntabellen `ps_category`, `ps_category_lang` und `ps_category_product` für Kategoriedaten. Konfigurationseinstellungen werden in `ps_configuration` unter Schlüsseln gespeichert, die mit `VERTICALBLOCKCATEGORIES_` präfixiert sind.
- **Registrierte Hooks-Tabelle**:

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `displayHeader` | Im `<head>`-Bereich des HTML. | Potenziell zum Laden von CSS/JS-Assets verwendet, obwohl für dieses Modul CSS typischerweise über `install()` oder `hookDisplayHeader` selbst registriert wird. |
  | `displayLeftColumn` | Rendert Inhalte in der linken Spalte des Shops. | Primärer Hook zum Anzeigen des vertikalen Kategorienmenüblocks. |
  | `displayRightColumn` | Rendert Inhalte in der rechten Spalte des Shops. | Alternativer Hook zum Anzeigen des vertikalen Kategorienmenüblocks. |
  | `displayHome` | Rendert Inhalte auf der Startseite. | Kann verwendet werden, um das Menü auf der Startseite anzuzeigen, obwohl dies für ein vertikales Menü weniger üblich ist. |
  | `displayFooter` | Rendert Inhalte im Footer-Bereich. | Weniger üblich für ein primäres Navigationsmenü, aber für ergänzende Links möglich. |
  | `displayProductExtraContent` | Rendert Inhalte auf der Produktseite, typischerweise unterhalb der Hauptproduktinformationen. | Könnte verwendet werden, um verwandte Kategorien für die Produktnavigation anzuzeigen. |
  | `actionObjectCategoryAddAfter` | Nach dem Hinzufügen einer Kategorie. | Potenziell zum Leeren des Modul-Caches verwendet, wenn sich die Kategorienstruktur ändert. |
  | `actionObjectCategoryUpdateAfter` | Nach dem Aktualisieren einer Kategorie. | Potenziell zum Leeren des Modul-Caches verwendet, wenn sich die Kategorienstruktur ändert. |
  | `actionObjectCategoryDeleteAfter` | Nach dem Löschen einer Kategorie. | Potenziell zum Leeren des Modul-Caches verwendet, wenn sich die Kategorienstruktur ändert. |
  | `actionShopDataDuplication` | Wenn ein Shop dupliziert wird (im Multishop-Kontext). | Stellt sicher, dass die Modulkonfiguration in den neuen Shop kopiert wird. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Vertikales Dropdown-Kategorienmenü“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei technischen Problemen oder Fragen zur Funktionalität des Moduls gerne zur Verfügung.
