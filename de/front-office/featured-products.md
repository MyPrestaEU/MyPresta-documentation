---
title: "Ausgewählte Produkte – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Ausgewählte Produkte“ von MyPresta.eu."
sidebar:
  label: "Ausgewählte Produkte – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Featured Products auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/featured-products.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/featured-products/)
>
> ---


# Ausgewählte Produkte

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständiger Konfigurations-Walkthrough (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Um auf die Konfiguration zuzugreifen, navigieren Sie zu **Module > Modul-Manager**, suchen Sie nach „Ausgewählte Produkte“ und klicken Sie auf „Konfigurieren“.

Dieser Bildschirm ermöglicht es Ihnen, zu definieren, welche Produkte angezeigt werden und wie sie auf Ihrer Startseite erscheinen.

#### Einstellungen & Optionen:

1. **Quellkategorie-ID**

   - **Was diese Einstellung bewirkt:** Dies ist die wichtigste Einstellung. Sie bestimmt, *welche* Produkte einer Kategorie als „ausgewählt“ auf Ihrer Startseite angezeigt werden. Sie müssen die numerische ID der Kategorie eingeben, die Sie präsentieren möchten.
   - **Auswirkung einer Änderung dieser Einstellung:**
     - *Wenn auf eine gültige Kategorie-ID eingestellt (z. B. `3` für „Kleidung“):* Das Modul ruft Produkte ab, die zu der Kategorie mit dieser ID gehören, und zeigt sie an.
     - *Wenn auf eine ungültige oder nicht existierende ID eingestellt:* Es werden keine Produkte angezeigt, oder es kann ein Fehler auftreten, wenn die ID fehlerhaft ist.
   - **Empfohlener Wert:** Die ID der Kategorie, die Sie bewerben möchten.
   - **Händlerszenario / Beispiel:** Wenn Sie Ihre Kategorie „Neuheiten“ (die beispielsweise die ID `12` hat) hervorheben möchten, würden Sie hier `12` eingeben. Um eine Kategorie-ID zu finden, gehen Sie im Back Office zu **Katalog > Kategorien**, klicken Sie bei einer Kategorie auf „Bearbeiten“ und schauen Sie sich die URL in Ihrem Browser an (z. B. `id_category=12`).
2. **Anzahl der Produkte**

   - **Was diese Einstellung bewirkt:** Dies steuert, wie viele Produkte aus Ihrer ausgewählten „Quellkategorie“ auf der Startseite angezeigt werden.
   - **Auswirkung einer Änderung dieser Einstellung:**
     - *Wenn auf `5` eingestellt:* Es werden nur die ersten 5 Produkte aus der ausgewählten Kategorie angezeigt.
     - *Wenn auf `10` eingestellt:* Es werden bis zu 10 Produkte angezeigt.
   - **Empfohlener Wert:** Eine angemessene Zahl wie `8` oder `12`, um die Startseite nicht zu überladen, aber genügend Vielfalt zu zeigen. Berücksichtigen Sie das Layout Ihres Themes.
   - **Händlerszenario / Beispiel:** Wenn Ihre Kategorie „Neuheiten“ 50 Produkte enthält, Sie aber nur die neuesten 8 auf der Startseite anzeigen möchten, würden Sie dies auf `8` einstellen.
3. **Platzierungsposition**

   - **Was diese Einstellung bewirkt:** Dies bestimmt, *wie* die ausgewählten Produkte auf Ihrer Startseite angezeigt werden: entweder direkt im Hauptinhaltsbereich (`displayHome`) oder innerhalb eines Tabs (`displayHomeTabContent`).
   - **Auswirkung einer Änderung dieser Einstellung:**
     - *Wenn auf `Startseiten-Tab` eingestellt:* Die Produkte erscheinen unter einem neuen Tab auf Ihrer Startseite (z. B. „Ausgewählte Produkte“). Dies erfordert, dass Ihr Theme Startseiten-Tabs unterstützt.
     - *Wenn auf `Startseite` eingestellt:* Die Produkte werden als eigenständiger Bereich direkt auf Ihrer Startseite angezeigt, ohne hinter einem Tab versteckt zu sein.
   - **Empfohlener Wert:**
     - Wählen Sie `Startseiten-Tab`, wenn Ihr Theme Tabs für Produktlisten verwendet (wie es bei Standard-PrestaShop-Themes oft der Fall ist) und Sie Ihre Startseite sauber halten möchten.
     - Wählen Sie `Startseite`, wenn Sie maximale Sichtbarkeit für diese Produkte wünschen und Ihr Theme ausreichend Platz im Hauptinhaltsbereich bietet.
   - **Händlerszenario / Beispiel:** Wenn Sie eine Sonderaktion durchführen und die Produkte sofort sichtbar sein sollen, ohne dass Kunden auf einen Tab klicken müssen, würden Sie `Startseite` auswählen. Wenn Sie viele Produkttypen auf Ihrer Startseite präsentieren und diese übersichtlich organisieren möchten, ist `Startseiten-Tab` die bessere Wahl.

#### Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Quellkategorie-ID | (Ihre Kategorie-ID) | Gibt an, welche Produkte einer Kategorie angezeigt werden. |
| Modulkonfiguration | Anzahl der Produkte | 8-12 | Begrenzt die Anzahl der angezeigten Produkte aus der ausgewählten Kategorie. |
| Modulkonfiguration | Platzierungsposition | Startseiten-Tab / Startseite | Bestimmt, ob Produkte in einem Tab oder direkt auf der Startseite erscheinen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine ausgewählten Produkte werden nicht auf der Startseite angezeigt.**
A:

1. **Überprüfen Sie die „Quellkategorie-ID“:** Stellen Sie sicher, dass Sie eine korrekte, existierende Kategorie-ID eingegeben haben. Gehen Sie zu **Katalog > Kategorien**, bearbeiten Sie die gewünschte Kategorie und finden Sie deren ID in der Browser-URL (z. B. `id_category=X`).
2. **Überprüfen Sie die „Anzahl der Produkte“:** Stellen Sie sicher, dass der Wert größer als 0 ist.
3. **Überprüfen Sie die „Platzierungsposition“:** Wenn auf „Startseiten-Tab“ eingestellt, stellen Sie sicher, dass Ihr Theme tatsächlich Startseiten-Tabs unterstützt und anzeigt. Einige benutzerdefinierte Themes tun dies möglicherweise nicht. Versuchen Sie, auf „Startseite“ umzuschalten, um zu sehen, ob sie als direkter Abschnitt erscheinen.
4. **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“. Manchmal verhindert der PrestaShop-Cache, dass Änderungen sofort angezeigt werden.

**F: Die Produkte werden angezeigt, sehen aber falsch ausgerichtet aus oder haben eine falsche Formatierung.**
A: Dies ist normalerweise ein Theme-bezogenes Problem.

1. **Theme-Kompatibilität:** Obwohl das Modul mit PrestaShop-Versionen kompatibel ist, kann seine visuelle Ausgabe mit stark angepassten Themes in Konflikt geraten.
2. **CSS-Konflikt:** Das CSS Ihres Themes könnte das Standard-Styling des Moduls überschreiben oder damit in Konflikt geraten. Möglicherweise benötigen Sie einen Webentwickler, um das CSS zu überprüfen und benutzerdefinierte Stile auf `featuredcategory.css` oder die benutzerdefinierte CSS-Datei Ihres Themes anzuwenden.

**F: Kann ich Produkte aus mehreren Kategorien hervorheben?**
A: Nicht direkt mit diesem Modul. Das Modul „Ausgewählte Produkte“ ist so konzipiert, dass es Produkte aus *einer* ausgewählten Kategorie gleichzeitig anzeigt. Wenn Sie Produkte aus mehreren Kategorien gleichzeitig hervorheben müssen, müssten Sie entweder:
a) Eine neue „Master-Auswahl“-Kategorie erstellen und Produkte aus verschiedenen Kategorien darin hinzufügen.
b) Mehrere Instanzen dieses Moduls installieren (wenn Ihr Theme dies zulässt) oder ein anderes Modul verwenden, das für die Anzeige mehrerer Kategorien konzipiert ist.

**F: Wie übersetze ich den Titel des „Ausgewählte Produkte“-Tabs?**
A: Wenn Sie die Platzierung „Startseiten-Tab“ verwenden, wird der Tab-Titel normalerweise vom Modul generiert.

1. Gehen Sie zu **International > Übersetzungen**.
2. Wählen Sie „Übersetzungen installierter Module“, Ihr Theme und Ihre Sprache aus.
3. Suchen Sie nach dem Modul „Ausgewählte Produkte“. Dort sollten Sie den Textstring für den Tab-Titel finden und ihn übersetzen können.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen gedacht, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul `Featured Products` ist ein unkompliziertes PrestaShop-Modul, das hauptsächlich dazu dient, eine Liste von Produkten aus einer bestimmten Kategorie auf der Startseite anzuzeigen. Es nutzt das Hook-System von PrestaShop (`displayHome`, `displayHomeTab`, `displayHomeTabContent`), um seinen Inhalt einzufügen. Die Modullogik ist in der Haupt-PHP-Datei `featuredcategory.php` enthalten, die Konfiguration, Installation und Inhaltsrendering übernimmt. Es führt keine benutzerdefinierten Controller, Modelle oder komplexes JavaScript ein, was es zu einer leichtgewichtigen und einfach zu wartenden Lösung macht.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Das gesamte Front-Office-Inhaltsrendering wird direkt über Hooks in der Hauptdatei `featuredcategory.php` und den zugehörigen Smarty-Templates abgewickelt.
- **Back-Office-Admin-Controller**: Keine. Die Modulkonfiguration wird über die Standardmethode `getContent()` in der Hauptmoduldatei verwaltet.

### 4.3 Kernklassen & Modelle (`classes/`)

- In diesem Modul sind keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen vorhanden. Alle Datenabrufe (Produkte, Kategorien) erfolgen über die Kernklassen `Product` und `Category` von PrestaShop.

### 4.4 JavaScript-Assets (`views/js/`)

- Es sind keine benutzerdefinierten JavaScript-Dateien in diesem Modul enthalten.

### 4.5 CSS-Stylesheets (`views/css/`)

- `featuredcategory/css/featuredcategory.css`
  - **Umfang:** Front-Office-Kunden-Styling.
  - **Wichtige UI-Komponenten und Container, die gestylt werden:** Dieses Stylesheet bietet grundlegendes Styling für die vom Modul generierte Produktliste, um sicherzustellen, dass sie im Kontext der Startseite ansprechend aussieht. Es zielt wahrscheinlich auf generische Produktlisten-Container und einzelne Produktelemente ab.
  - **Wichtige CSS-Klassenselektoren, die Entwickler in ihrem Theme überschreiben können:** Entwickler können die HTML-Ausgabe des Moduls überprüfen, um spezifische Klassen (z. B. `.featuredcategory-products`, `.product-item`, `.product-name`) zu identifizieren und diese in der benutzerdefinierten CSS-Datei ihres Themes zu überschreiben, um sie an das Gesamtdesign des Shops anzupassen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul verwendet Smarty-Templates, um seinen Inhalt zu rendern, hauptsächlich für die Startseiten-Hooks.

- **Hook-Templates (`views/templates/hook/`)**:
  - `featuredcategory/views/templates/hook/featuredcategory17-tabContents.tpl`
    - **Hook:** `displayHomeTabContent`
    - **Zweck:** Dieses Template ist für das Rendern der eigentlichen Liste der ausgewählten Produkte verantwortlich, wenn die „Platzierungsposition“ auf „Startseiten-Tab“ eingestellt ist. Es enthält typischerweise die Schleife zum Iterieren durch Produkte und Anzeigen ihrer Details (Bild, Name, Preis, In den Warenkorb-Button).
  - `featuredcategory/views/templates/hook/featuredcategory17.tpl`
    - **Hook:** `displayHome`
    - **Zweck:** Dieses Template rendert die Liste der ausgewählten Produkte, wenn die „Platzierungsposition“ auf „Startseite“ eingestellt ist (d. h. nicht in einem Tab). Es gibt die gleiche Produktlistenstruktur wie `featuredcategory17-tabContents.tpl` aus, jedoch direkt in den `displayHome`-Hook.
  - `featuredcategory/views/templates/hook/tab.tpl`
    - **Hook:** `displayHomeTab`
    - **Zweck:** Dieses Template rendert den eigentlichen Tab-Titel (z. B. „Ausgewählte Produkte“), der auf der Startseite erscheint, wenn die „Platzierungsposition“ auf „Startseiten-Tab“ eingestellt ist. Es stellt das anklickbare Element bereit, das den Inhalt von `featuredcategory17-tabContents.tpl` enthüllt.
- **Admin-Templates (`views/templates/admin/`)**: Keine.
- **Front-Office-Templates (`views/templates/front/`)**: Keine.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es speichert seine Konfigurationseinstellungen in der PrestaShop-Tabelle `ps_configuration`.

  - `ps_configuration`-Einträge:
    - `CFEATURED_NBR`: Speichert die Einstellung „Anzahl der Produkte“.
    - `CFEATURED_ID`: Speichert die Einstellung „Quellkategorie-ID“.
    - `CFEATURED_WHERE`: Speichert die Einstellung „Platzierungsposition“ (z. B. 'tab' oder 'home').
    - `mypresta_updates`: Wird für Modul-Update-Prüfungen durch MyPresta.eu verwendet.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHomeTab` | Rendert Inhalt für einen neuen Tab auf der Startseite. | Gibt den HTML-Code für den Tab-Titel „Ausgewählte Produkte“ aus. |
| `displayHomeTabContent` | Rendert Inhalt für den ausgewählten Tab auf der Startseite. | Gibt den HTML-Code für die Liste der ausgewählten Produkte aus, wenn der Tab aktiv ist. |
| `displayHome` | Rendert Inhalt direkt im Hauptbereich der Startseite. | Gibt den HTML-Code für die Liste der ausgewählten Produkte aus, wenn keine Tabs verwendet werden. |
| `displayHeader` | Wird im `<head>`-Bereich jeder Seite ausgeführt. | Wird verwendet, um das CSS-Stylesheet des Moduls (`featuredcategory.css`) für die Front-Office-Anzeige einzubinden. |
| `actionProductDelete` | Wird nach dem Löschen eines Produkts ausgelöst. | Potenziell verwendet, um den Cache zu leeren oder ausgewählte Produkte neu zu bewerten, wenn das gelöschte Produkt in der ausgewählten Kategorie war. |
| `actionProductUpdate` | Wird nach dem Aktualisieren eines Produkts ausgelöst. | Potenziell verwendet, um den Cache zu leeren oder ausgewählte Produkte neu zu bewerten, wenn das aktualisierte Produkt in der ausgewählten Kategorie ist. |
| `actionProductAdd` | Wird nach dem Hinzufügen eines neuen Produkts ausgelöst. | Potenziell verwendet, um den Cache zu leeren oder ausgewählte Produkte neu zu bewerten, wenn das neue Produkt in der ausgewählten Kategorie ist. |
| `actionCategoryUpdate` | Wird nach dem Aktualisieren einer Kategorie ausgelöst. | Potenziell verwendet, um den Cache zu leeren oder ausgewählte Produkte neu zu bewerten, wenn die ausgewählte Kategorie selbst aktualisiert wird. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zum Modul „Ausgewählte Produkte“ zur Verfügung.
