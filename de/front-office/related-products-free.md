---
title: "Related Products Free - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Related Products Free von MyPresta.eu."
sidebar:
  label: "Related Products Free - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Related Products Free auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/related-products-free.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/related-products-free/)
>
> ---


# Related Products Free

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL), die typischerweise in den meisten PrestaShop-kompatiblen Hosting-Umgebungen verfügbar sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren > Related Products Free)

Dies ist der Haupt- und einzige Konfigurationsbildschirm für das Modul „Related Products Free“. Hier definieren Sie, wie sich der Block der verwandten Produkte verhält und welche Produkte er anzeigt.

#### **Verwandte Produkte aus Kategorie anzeigen**

- **Was diese Einstellung bewirkt:** Diese entscheidende Einstellung bestimmt, *welche* Produkte als „verwandt“ angezeigt werden. Anstatt Produkte für jeden Artikel manuell auszuwählen, vereinfacht dieses Modul die Dinge, indem es Ihnen ermöglicht, eine bestimmte Kategorie auszuwählen. Alle Produkte, die zu dieser ausgewählten Kategorie gehören, werden dann als verwandte Produkte auf *jeder* Produktseite in Ihrem Shop angezeigt.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn eine Kategorie ausgewählt ist (z.B. „Zubehör“):* Auf jeder Produktseite in Ihrem Shop erscheint ein Block, der Produkte anzeigt, die zur Kategorie „Zubehör“ gehören.
  - *Wenn „Keine“ oder keine Kategorie ausgewählt ist:* Das Modul zeigt keine verwandten Produkte an, da es nicht weiß, welche Produkte angezeigt werden sollen.
- **Empfohlener Wert:** Wählen Sie eine Kategorie, die allgemeine, ergänzende oder meistverkaufte Artikel enthält, die für eine breite Palette Ihrer Hauptprodukte relevant sein könnten. Wenn Sie beispielsweise Kleidung verkaufen, könnten „Zubehör“ oder „Sale-Artikel“ gute Optionen sein.
- **Händler-Szenario / Beispiel:** Sie verkaufen verschiedene Arten von Elektronik. Sie erstellen eine Kategorie namens „Must-Have Gadget Zubehör“ und fügen Artikel wie Universal-Ladegeräte, Displayschutzfolien und Kopfhörer hinzu. Durch die Auswahl dieser Kategorie hier zeigt jede Produktseite (z.B. für ein Smartphone, einen Laptop oder ein Tablet) diese „Must-Have Gadget Zubehör“ als verwandte Produkte an, was Cross-Selling fördert.

#### **Anzahl der anzuzeigenden Produkte**

- **Was diese Einstellung bewirkt:** Dies steuert, wie viele verwandte Produkte im Block auf Ihren Produktseiten angezeigt werden.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf „4“ eingestellt:* Das Modul zeigt vier Produkte aus Ihrer ausgewählten Kategorie an.
  - *Wenn auf „8“ eingestellt:* Das Modul zeigt acht Produkte an.
- **Empfohlener Wert:** 4 oder 5. Zu viele Produkte können den Kunden überfordern oder die Seite überladen wirken lassen, besonders auf Mobilgeräten. Eine kleinere, kuratierte Auswahl ist oft effektiver.
- **Händler-Szenario / Beispiel:** Sie möchten eine prägnante Auswahl verwandter Artikel anzeigen, ohne die Produktseite zu lang zu machen. Die Einstellung auf „4“ sorgt für ein sauberes Layout und bietet dennoch gute Cross-Selling-Möglichkeiten.

#### **Produkte nur aus ausgewählter Kategorie anzeigen**

- **Was diese Einstellung bewirkt:** Diese Einstellung bestimmt, ob die angezeigten verwandten Produkte *nur* aus der oben ausgewählten Kategorie stammen oder ob sie auch Produkte aus der *eigenen Kategorie des aktuellen Produkts* enthalten können.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Es werden nur Produkte aus der in „Verwandte Produkte aus Kategorie anzeigen“ ausgewählten Kategorie angezeigt.
  - *Wenn deaktiviert (NEIN):* Das Modul zeigt Produkte aus der ausgewählten Kategorie *und* potenziell Produkte aus der Kategorie des Produkts an, das der Kunde gerade ansieht. Dies kann zu relevanteren Vorschlägen führen, wenn die Kategorie des aktuellen Produkts auch gute Cross-Selling-Artikel enthält.
- **Empfohlener Wert:** „JA“, wenn Ihre ausgewählte „verwandte Produkte“-Kategorie sehr allgemein ist (wie „Zubehör“). „NEIN“, wenn Sie spezifischere verwandte Artikel aus der Kategorie des aktuellen Produkts mischen möchten. Testen Sie beides, um zu sehen, was für Ihren Shop am besten funktioniert.
- **Händler-Szenario / Beispiel:** Sie haben „Zubehör“ als Ihre verwandte Kategorie ausgewählt. Wenn Sie dies auf „JA“ setzen, wird nur Zubehör angezeigt. Wenn Sie es auf „NEIN“ setzen und ein Kunde ein „T-Shirt“ ansieht (das sich in der Kategorie „Oberteile“ befindet), zeigt das Modul möglicherweise sowohl „Zubehör“ als auch andere „Oberteile“ als verwandte Produkte an.

#### **Hook zum Anzeigen verwandter Produkte**

- **Was diese Einstellung bewirkt:** Hier entscheiden Sie, *wo* auf der Produktseite der Block der verwandten Produkte erscheinen soll. PrestaShop verwendet „Hooks“ als spezifische Punkte im Code der Seite, an denen Module ihre Inhalte einfügen können.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf `displayFooterProduct` eingestellt (Empfohlen):* Der Block der verwandten Produkte erscheint am Ende des Produktinformationsbereichs, normalerweise über dem Footer der gesamten Seite. Dies ist eine gängige und effektive Platzierung.
  - *Wenn auf `displayProductExtraContent` eingestellt (PrestaShop 1.7+):* Der Block kann innerhalb eines Tabs oder eines spezifischen Abschnitts des Hauptinhaltsbereichs der Produktseite erscheinen, abhängig von Ihrem Theme.
  - *Andere Hooks (z.B. `displayLeftColumnProduct`, `displayRightColumnProduct`):* Der Block erscheint in der linken oder rechten Seitenleiste der Produktseite, wenn Ihr Theme Seitenleisten auf Produktseiten unterstützt.
- **Empfohlener Wert:** `displayFooterProduct`. Dieser Hook wird von Themes weitgehend unterstützt und bietet eine klare, unaufdringliche Platzierung für verwandte Artikel. Experimentieren Sie mit anderen, wenn Sie ein bestimmtes Design im Sinn haben.
- **Händler-Szenario / Beispiel:** Sie möchten, dass die verwandten Produkte sichtbar sind, aber nicht die Hauptproduktbeschreibung und den „In den Warenkorb“-Button stören. Die Auswahl von `displayFooterProduct` platziert sie sauber unter dem primären Inhalt, sodass Kunden nach unten scrollen und mehr entdecken können.

#### **Produkte im Karussell anzeigen**

- **Was diese Einstellung bewirkt:** Dies bestimmt, ob die verwandten Produkte in einem statischen Raster (alle auf einmal sichtbar) oder in einem dynamischen, scrollbaren Karussell angezeigt werden (wo Kunden auf Pfeile klicken oder wischen können, um mehr zu sehen).
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Die verwandten Produkte werden in einem Karussellformat angezeigt, sodass Sie mehr Produkte auf kompaktem Raum präsentieren können.
  - *Wenn deaktiviert (NEIN):* Die Produkte werden in einem statischen Raster angezeigt, wobei alle ausgewählten Produkte auf einmal sichtbar sind (bis zum Limit der „Anzahl der anzuzeigenden Produkte“).
- **Empfohlener Wert:** „JA“, wenn Sie Platz sparen oder mehr Produkte anzeigen möchten, als bequem in eine einzelne Reihe passen. „NEIN“, wenn Sie es vorziehen, dass alle Produkte sofort ohne Interaktion sichtbar sind.
- **Händler-Szenario / Beispiel:** Sie möchten 8 verwandte Produkte anzeigen, aber die Anzeige aller in einem Raster macht die Seite zu lang. Durch die Aktivierung des Karussells können Sie 8 Produkte anzeigen, während nur der Platz von 4 belegt wird, wobei Kunden scrollen, um den Rest zu sehen.

#### **Produkte in zufälliger Reihenfolge anzeigen**

- **Was diese Einstellung bewirkt:** Dies steuert die Reihenfolge, in der die verwandten Produkte aus Ihrer ausgewählten Kategorie angezeigt werden.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Jedes Mal, wenn ein Kunde eine Produktseite besucht, erscheinen die verwandten Produkte in einer anderen, zufälligen Reihenfolge.
  - *Wenn deaktiviert (NEINE):* Die Produkte erscheinen in einer konsistenten Reihenfolge, normalerweise basierend auf ihrer ID oder Position innerhalb der ausgewählten Kategorie.
- **Empfohlener Wert:** „JA“. Das Zufallsprinzip stellt sicher, dass alle Produkte in Ihrer ausgewählten Kategorie im Laufe der Zeit eine Chance erhalten, gesehen zu werden, und verhindert, dass immer dieselben wenigen Produkte ganz oben stehen.
- **Händler-Szenario / Beispiel:** Sie haben 20 Produkte in Ihrer Kategorie „Zubehör“, zeigen aber nur 5 an. Wenn die Reihenfolge immer gleich ist, werden nur die ersten 5 jemals gesehen. Durch die Aktivierung der zufälligen Reihenfolge erscheinen jedes Mal andere Zubehörteile, was die Sichtbarkeit für alle erhöht.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Verwandte Produkte aus Kategorie anzeigen | Eine relevante Kategorie auswählen | Definiert die Quellkategorie für verwandte Produkte. |
| Modulkonfiguration | Anzahl der anzuzeigenden Produkte | 4-5 | Steuert, wie viele verwandte Produkte angezeigt werden. |
| Modulkonfiguration | Produkte nur aus ausgewählter Kategorie anzeigen | JA / NEIN (Beides testen) | Bestimmt, ob nur Produkte der ausgewählten Kategorie angezeigt werden oder ob die Kategorie des aktuellen Produkts ebenfalls beitragen kann. |
| Modulkonfiguration | Hook zum Anzeigen verwandter Produkte | `displayFooterProduct` | Legt den Speicherort des Blocks für verwandte Produkte auf der Produktseite fest. |
| Modulkonfiguration | Produkte im Karussell anzeigen | JA | Zeigt verwandte Produkte in einem scrollbaren Karussell für eine kompakte Anzeige an. |
| Modulkonfiguration | Produkte in zufälliger Reihenfolge anzeigen | JA | Zufällige Reihenfolge der angezeigten verwandten Produkte für eine abwechslungsreiche Präsentation. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul konfiguriert, sehe aber keine verwandten Produkte auf meinen Produktseiten.**
A:

1. **Kategorieauswahl prüfen:** Stellen Sie sicher, dass Sie in der Einstellung „Verwandte Produkte aus Kategorie anzeigen“ eine gültige Kategorie ausgewählt haben und dass diese Kategorie tatsächlich Produkte enthält.
2. **Produktstatus prüfen:** Stellen Sie sicher, dass die Produkte in Ihrer ausgewählten Kategorie aktiv, auf Lager und in Ihrem Shop sichtbar sind.
3. **Cache leeren:** Gehen Sie im PrestaShop Back Office zu **Erweiterte Einstellungen > Performance** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“). Manchmal benötigt PrestaShop eine Cache-Aktualisierung, um neue Modulinhalte anzuzeigen.
4. **Theme-Kompatibilität:** Obwohl das Modul Standard-PrestaShop-Hooks verwendet, können einige stark angepasste Themes spezifische Overrides haben. Versuchen Sie, vorübergehend zum Standard-PrestaShop-Theme zu wechseln, um zu sehen, ob der Block erscheint. Wenn ja, benötigt Ihr Theme möglicherweise geringfügige Anpassungen.

**F: Der Block der verwandten Produkte sieht auf meiner Website seltsam oder ungestylt aus.**
A: Dies ist normalerweise ein CSS (Styling)-Konflikt mit Ihrem Theme.

1. **Cache leeren:** Beginnen Sie immer damit, Ihren PrestaShop-Cache zu leeren.
2. **Theme-Overrides:** Ihr Theme hat möglicherweise eigene Stile für Produktlisten oder Karussells, die Konflikte verursachen. Möglicherweise benötigen Sie einen Webentwickler, um das CSS zu überprüfen und benutzerdefinierte Stile anzuwenden, damit es zum Design Ihres Themes passt. Das Modul bietet grundlegendes Styling, aber die Stile Ihres Themes haben oft Vorrang.

**F: Kann ich verschiedene verwandte Produkte für verschiedene Hauptprodukte haben?**
A: Das Modul „Related Products Free“ ist auf Einfachheit ausgelegt und zeigt Produkte aus einer *einzelnen ausgewählten Kategorie* auf allen Produktseiten an. Für fortgeschrittenere, produktspezifische Zuweisungen verwandter Produkte benötigen Sie ein umfassenderes (kostenpflichtiges) Modul.

**F: Das Karussell funktioniert nicht oder wird nicht korrekt angezeigt.**
A:

1. **JavaScript-Konflikte prüfen:** Ein anderes Modul oder Ihr Theme könnte widersprüchliches JavaScript haben, das die Initialisierung des Karussells verhindert. Überprüfen Sie die Entwicklerkonsole Ihres Browsers auf JavaScript-Fehler.
2. **Cache leeren:** Leeren Sie erneut Ihren PrestaShop-Cache.
3. **Deaktivieren & Reaktivieren:** Versuchen Sie, die Einstellung „Produkte im Karussell anzeigen“ zu deaktivieren, zu speichern, dann wieder zu aktivieren und erneut zu speichern.

**F: Wie übersetze ich den Titel des Moduls (z.B. „Verwandte Produkte“) in andere Sprachen?**
A:

1. Gehen Sie im PrestaShop Back Office zu **International > Übersetzungen**.
2. Wählen Sie „Übersetzungen installierter Module“ für den „Übersetzungstyp“.
3. Wählen Sie Ihr Theme (oder „Core“, wenn Ihr Theme nicht aufgeführt ist).
4. Wählen Sie die Sprache aus, in die Sie übersetzen möchten.
5. Suchen Sie das Modul „relatedfree“ in der Liste und übersetzen Sie die relevanten Zeichenketten.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen technischen Überblick für Entwickler und Webmaster, die mit dem Modul „Related Products Free“ arbeiten.

### 4.1 Architekturübersicht

Das Modul „Related Products Free“ ist ein unkompliziertes PrestaShop-Modul, das einem grundlegenden MVC-ähnlichen Muster im Rahmen des Moduls folgt. Es verwendet hauptsächlich die Methode `getContent()` der `Module`-Klasse für seine Back-Office-Konfiguration und registriert einen einzelnen Hook (standardmäßig `displayFooterProduct`, aber konfigurierbar), um seine Front-Office-Vorlage einzufügen. Es führt keine benutzerdefinierten Controller, ObjectModels oder komplexen JavaScript/CSS-Assets über seine Kernfunktionalität hinaus ein.

### 4.2 Controller (`controllers/`)

- Dieses Modul enthält **keine** benutzerdefinierten Front-Office- oder Back-Office-Controller. Die gesamte Konfiguration wird innerhalb der `getContent()`-Methode der Hauptmoduldatei behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

- Dieses Modul enthält **keine** benutzerdefinierten Klassen oder ObjectModels im Verzeichnis `classes/`. Die gesamte Logik ist in der Hauptklasse `RelatedFree` (definiert in `index.php`) gekapselt.

### 4.4 JavaScript-Assets (`views/js/`)

- Dieses Modul enthält **keine** benutzerdefinierten JavaScript-Dateien. Wenn die Karussell-Option aktiviert ist, greift es auf die Kern-JavaScript-Bibliotheken von PrestaShop zurück (z.B. Owl Carousel, falls im Theme verfügbar, oder eine einfache benutzerdefinierte Implementierung innerhalb der TPL, falls nicht).

### 4.5 CSS-Stylesheets (`views/css/`)

- Dieses Modul enthält **keine** benutzerdefinierten CSS-Dateien. Das Styling wird voraussichtlich vom Theme übernommen oder basiert auf grundlegenden Inline-Stilen/Strukturen, die Themes typischerweise stylen. Entwickler sollten benutzerdefiniertes CSS anwenden, um die Ästhetik ihres Themes anzupassen.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

- **Admin-Vorlagen (`views/templates/admin/`)**:

  - `views/templates/admin/tabs.tpl`: Diese Vorlage wird verwendet, um das Konfigurationsformular des Moduls im Back Office zu rendern. Sie definiert die Struktur der Einstellungen, einschließlich Eingabefeldern für die Kategorieauswahl, die Anzahl der Produkte, die Hook-Auswahl und Umschalter für Karussell und zufällige Reihenfolge. Sie wird von `getContent()` in `index.php` gerendert.
- **Hook-Vorlagen (`views/templates/hook/`)**:

  - `views/templates/hook/productFooter.tpl`: Dies ist die primäre Front-Office-Vorlage. Sie wird gerendert, wenn das Modul gehookt ist (z.B. `displayFooterProduct`). Diese Vorlage enthält die HTML-Struktur für den Block der verwandten Produkte, einschließlich des Titels, und iteriert durch die Variable `$products` (vom Modul übergeben), um Bild, Name und Preis jedes verwandten Produkts anzuzeigen. Sie enthält auch die Logik zum Rendern eines Karussells, wenn die entsprechende Konfigurationsoption aktiviert ist.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Alle Konfigurationseinstellungen werden in der Tabelle `ps_configuration` unter Verwendung von Standard-PrestaShop-Konfigurationsschlüsseln gespeichert.

  - `PS_RELATEDFREE_CATEGORY`: Speichert die ID der ausgewählten Kategorie für verwandte Produkte.
  - `PS_RELATEDFREE_NUMBER`: Speichert die Anzahl der anzuzeigenden Produkte.
  - `PS_RELATEDFREE_ONLY_SELECTED`: Speichert einen booleschen Wert (0/1) für die Anzeige von Produkten nur aus der ausgewählten Kategorie.
  - `PS_RELATEDFREE_HOOK`: Speichert den Namen des Hooks, an dem das Modul angezeigt wird.
  - `PS_RELATEDFREE_CAROUSEL`: Speichert einen booleschen Wert (0/1) für die Aktivierung des Karussells.
  - `PS_RELATEDFREE_RANDOM`: Speichert einen booleschen Wert (0/1) für die Anzeige von Produkten in zufälliger Reihenfolge.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Wird zum Registrieren von Assets verwendet (obwohl dieses Modul es nicht für Assets verwendet). |
| `displayLeftColumn` | In der linken Seitenleiste von Seiten, die eine haben. | Alternative Platzierung für den Block der verwandten Produkte. |
| `displayRightColumn` | In der rechten Seitenleiste von Seiten, die eine haben. | Alternative Platzierung für den Block der verwandten Produkte. |
| `displayFooter` | Am Ende jeder Seite, vor dem schließenden `</body>`-Tag. | Alternative Platzierung für den Block der verwandten Produkte. |
| `displayProductExtraContent` | Innerhalb des Hauptproduktinhaltsbereichs, oft in Tabs (PrestaShop 1.7+). | Alternative Platzierung für den Block der verwandten Produkte. |
| `displayFooterProduct` | Am Ende des Produktinformationsbereichs auf Produktseiten. | **Primärer Hook, der vom Modul verwendet wird** zur Anzeige verwandter Produkte. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Related Products Free“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zur Funktionalität des Moduls gerne zur Verfügung.
