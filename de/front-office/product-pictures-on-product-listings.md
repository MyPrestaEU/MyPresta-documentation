---
title: "Produktbilder in Produktlisten – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Produktbilder in Produktlisten“ von MyPresta.eu."
sidebar:
  label: "Produktbilder in Produktlisten – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Product pictures on product listings auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/product-pictures-on-product-listings.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/product-pictures-on-product-listings/)
>
> ---


# Produktbilder in Produktlisten

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind für PrestaShop selbst erforderlich und in der Regel in allen modernen Hosting-Umgebungen verfügbar.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul „Produktbilder in Produktlisten“. Sie können darauf zugreifen, indem Sie zu **Module > Modul-Manager** navigieren und neben dem Modulnamen auf „Konfigurieren“ klicken.

#### **Position des Moduls**

- **Was diese Einstellung bewirkt:** Dies bestimmt, wo die zusätzlichen Produktbilder relativ zum Hauptproduktbild auf den Listenseiten erscheinen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *displayProductAdditionalInfo:* Bilder erscheinen in einem gängigen Hook, der oft für zusätzliche Produktdetails verwendet wird.
  - *displayAfterProductThumbs:* Bilder erscheinen unmittelbar nach den Hauptproduktbild-Miniaturansichten (sofern Ihr Theme diese anzeigt).
  - *displayFooterProduct:* Bilder erscheinen im Fußbereich des Produktblocks auf der Listenseite.
  - *displayProductDeliveryTime:* Bilder erscheinen in der Nähe der Lieferzeitinformationen (sofern Ihr Theme diese anzeigt).
  - *displayHeader:* Dies ist eine weniger übliche Position für Produktbilder auf Listenseiten und erfordert möglicherweise benutzerdefiniertes Styling, um gut auszusehen.
  - *displayProductListReviews:* Bilder erscheinen in der Nähe von Produktbewertungssternen oder -anzahl (sofern Ihr Theme diese anzeigt).
- **Empfohlener Wert:** Experimentieren Sie zuerst mit `displayProductAdditionalInfo` oder `displayAfterProductThumbs`, da dies in der Regel gute visuelle Platzierungen sind.
- **Händlerszenario / Beispiel:** Wenn Ihr Theme ein klares Layout hat und Sie möchten, dass die Bilder subtil unter dem Hauptbild integriert werden, könnte `displayProductAdditionalInfo` am besten sein. Wenn Sie möchten, dass sie stärker hervorstechen, könnte `displayFooterProduct` funktionieren.

#### **Design des Moduls**

- **Was diese Einstellung bewirkt:** Hiermit können Sie zwischen verschiedenen visuellen Stilen für die Ausgabe des Moduls wählen, was hauptsächlich die Präsentation der Miniaturansichten beeinflusst.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Klassisches Theme:* Wendet Styling an, das oft mit älteren PrestaShop-Themes oder Themes, die den klassischen Look nachahmen, kompatibel ist.
  - *Universal:* Wendet ein moderneres, responsives Design an, das darauf abzielt, mit einer breiteren Palette zeitgenössischer Themes gut zu funktionieren.
- **Empfohlener Wert:** `Universal` für die meisten modernen PrestaShop-Shops (1.7.x, 8.x, 9.x). Verwenden Sie `Klassisches Theme`, wenn Sie ein älteres oder stark angepasstes Theme haben, das `Universal` nicht korrekt rendert.
- **Händlerszenario / Beispiel:** Wenn Ihr Shop ein Standard-PrestaShop 8-Theme verwendet, wird `Universal` wahrscheinlich nahtlos integriert. Wenn Sie PrestaShop 1.6 mit einem benutzerdefinierten Theme verwenden, ist `Klassisches Theme` möglicherweise die sicherere Wahl.

#### **Anzeigemethode**

- **Was diese Einstellung bewirkt:** Dies steuert, welche zusätzlichen Bilder für jedes Produkt auf der Listenseite angezeigt werden.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Bilder für Farbkombinationen:* Zeigt nur Bilder an, die speziell mit den Farbattributen eines Produkts verknüpft sind. Nützlich für Mode oder Produkte mit unterschiedlichen Farbvarianten.
  - *Bilder für jede Kombination:* Zeigt Bilder für alle Produktkombinationen an (z. B. Größe, Farbe, Material). Dies kann zu vielen Bildern führen, wenn Sie viele Kombinationen haben.
  - *Alle Produktbilder:* Zeigt alle mit dem Produkt verknüpften Bilder an, unabhängig von der Kombination. Dies ist die umfassendste Option.
- **Empfohlener Wert:** `Alle Produktbilder` für die meisten allgemeinen Produkte. `Bilder für Farbkombinationen`, wenn Ihre Produkte stark von Farbvarianten abhängen und Sie die Bildanzahl überschaubar halten möchten.
- **Händlerszenario / Beispiel:** Für ein Bekleidungsgeschäft würde die Auswahl von `Bilder für Farbkombinationen` alle verfügbaren Farben für ein bestimmtes T-Shirt anzeigen. Für ein Möbelgeschäft würde `Alle Produktbilder` verschiedene Winkel und Nahaufnahmen eines Sofas zeigen.

#### **Nur auf Lager**

- **Was diese Einstellung bewirkt:** Diese Option filtert die angezeigten Bilder basierend auf der Produktverfügbarkeit.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Aktiviert:* Zeigt nur Bilder für Produktkombinationen an, die derzeit auf Lager sind. Wenn eine bestimmte Farbe nicht auf Lager ist, werden die zugehörigen Bilder nicht angezeigt.
  - *Deaktiviert:* Zeigt alle ausgewählten Bilder an, unabhängig vom Lagerstatus.
- **Empfohlener Wert:** `Aktiviert`, um Kunden keine Bilder von Produkten zu zeigen, die sie nicht sofort kaufen können, was zu Frustration führen kann.
- **Händlerszenario / Beispiel:** Wenn Sie Schuhe verkaufen und eine bestimmte Größen-/Farbkombination nicht auf Lager ist, verhindert die Aktivierung dieser Option, dass Kunden Bilder dieser spezifischen Variante sehen, und leitet sie zu verfügbaren Optionen.

#### **Farbfelder anstelle von Bildern anzeigen**

- **Was diese Einstellung bewirkt:** Anstatt kleine Bildminiaturansichten anzuzeigen, zeigt diese Option Farbfelder (Kästchen) für Produktkombinationen an.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Aktiviert:* Ersetzt Bildminiaturansichten durch kleine Farbfelder, die typischerweise die für das Produktattribut definierte Farbe verwenden.
  - *Deaktiviert:* Zeigt tatsächliche Bildminiaturansichten an.
- **Empfohlener Wert:** `Deaktiviert`, wenn Sie tatsächliche Produktbilder anzeigen möchten. `Aktiviert`, wenn Ihre Produkte klare Farbattribute haben und Sie ein saubereres, kompakteres Aussehen für die Farbauswahl bevorzugen.
- **Händlerszenario / Beispiel:** Für ein Farbengeschäft würde die Aktivierung dieser Option kleine farbige Quadrate anzeigen, die verschiedene Farben darstellen, was effizienter ist, als ein winziges Bild jeder Farbe zu zeigen.

#### **Hauptproduktcontainer in der Produktliste**

- **Was diese Einstellung bewirkt:** Dies ist eine technische Einstellung, die dem Modul hilft, den Hauptcontainer für jedes Produkt auf Ihren Listenseiten zu identifizieren. Sie erfordert einen CSS-Selektor.
- **Auswirkung der Änderung dieser Einstellung:** Wenn falsch eingestellt, kann das Modul möglicherweise nicht finden, wo die zusätzlichen Bilder eingefügt werden sollen, oder es könnte sie an der falschen Stelle einfügen.
- **Empfohlener Wert:** Dies hängt vollständig von Ihrem Theme ab. Gängige Werte sind `.product-miniature`, `.product-container` oder `.ajax_block_product`. Möglicherweise müssen Sie den HTML-Code Ihres Themes überprüfen, um den richtigen Selektor zu finden.
- **Händlerszenario / Beispiel:** Wenn Ihr Theme `<div class="product-item">` für jedes Produkt verwendet, würden Sie hier `.product-item` eingeben.

#### **CSS des Produkt-Titelbilds**

- **Was diese Einstellung bewirkt:** Dies ist eine technische Einstellung, die dem Modul hilft, das Hauptproduktbildelement innerhalb jedes Produktcontainers zu identifizieren. Sie erfordert einen CSS-Selektor.
- **Auswirkung der Änderung dieser Einstellung:** Wenn falsch eingestellt, kann das Modul das Hauptproduktbild nicht wechseln, wenn eine Miniaturansicht angeklickt/gehovert wird.
- **Empfohlener Wert:** Dies hängt von Ihrem Theme ab. Gängige Werte sind `.product-thumbnail`, `.img-fluid` oder `img.replace-me`. Möglicherweise müssen Sie den HTML-Code Ihres Themes überprüfen.
- **Händlerszenario / Beispiel:** Wenn das Hauptproduktbild Ihres Themes die Klasse `product-image-thumb` hat, würden Sie hier `.product-image-thumb` eingeben.

#### **CSS des Ankers für das Produkt-Titelbild**

- **Was diese Einstellung bewirkt:** Dies ist eine technische Einstellung, die dem Modul hilft, den Link (Anker-Tag) zu identifizieren, der das Hauptproduktbild umschließt. Dies ist wichtig, um sicherzustellen, dass der Link nach dem Bildwechsel weiterhin korrekt funktioniert.
- **Auswirkung der Änderung dieser Einstellung:** Wenn falsch eingestellt, führt ein Klick auf das Hauptproduktbild möglicherweise nicht zur Produktseite, oder der Bildwechsel schlägt fehl.
- **Empfohlener Wert:** Dies hängt von Ihrem Theme ab. Gängige Werte sind `.product-thumbnail a`, `.product-image a` oder `a.product-cover`. Möglicherweise müssen Sie den HTML-Code Ihres Themes überprüfen.
- **Händlerszenario / Beispiel:** Wenn Ihr Theme das Hauptproduktbild in `<a class="product-link">` umschließt, würden Sie hier `a.product-link` eingeben.

#### **Anker des Produkttitels**

- **Was diese Einstellung bewirkt:** Dies ist eine technische Einstellung, um den Link (Anker-Tag) um den Produkttitel zu identifizieren.
- **Auswirkung der Änderung dieser Einstellung:** Diese Einstellung hilft dem Modul sicherzustellen, dass der Produkttitellink funktionsfähig bleibt und korrekt auf die Produktseite verweist.
- **Empfohlener Wert:** Dies hängt von Ihrem Theme ab. Gängige Werte sind `.product-title a`, `.product-name a` oder `h3 a`. Möglicherweise müssen Sie den HTML-Code Ihres Themes überprüfen.
- **Händlerszenario / Beispiel:** Wenn Ihre Produkttitel in `<h3 class="product-name"><a href="...">` umschlossen sind, würden Sie hier `h3.product-name a` eingeben.

#### **Zusätzliche Klasse für Miniatur-Anker**

- **Was diese Einstellung bewirkt:** Hiermit können Sie den Anker-Tags der vom Modul angezeigten Miniaturbilder eine zusätzliche CSS-Klasse hinzufügen. Dies ist nützlich für benutzerdefiniertes Styling.
- **Auswirkung der Änderung dieser Einstellung:** Die angegebene Klasse wird dem HTML-Code der Miniaturbild-Links hinzugefügt, sodass Sie sie mit benutzerdefinierten CSS-Regeln in Ihrem Theme ansprechen können.
- **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben spezifische benutzerdefinierte Styling-Anforderungen.
- **Händlerszenario / Beispiel:** Wenn Sie einen speziellen Rahmen für Ihre Miniaturbilder hinzufügen möchten, könnten Sie hier `my-custom-miniature-class` eingeben und dann CSS wie `.my-custom-miniature-class img { border: 1px solid blue; }` zu Ihrem Theme hinzufügen.

#### **Bildwechselmethode**

- **Was diese Einstellung bewirkt:** Dies steuert, wie sich das Hauptproduktbild ändert, wenn ein Kunde mit den zusätzlichen Miniaturansichten interagiert.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Beim Klick:* Das Hauptbild ändert sich nur, wenn ein Kunde auf eine Miniaturansicht klickt.
  - *Beim Hover:* Das Hauptbild ändert sich, wenn ein Kunde den Mauszeiger über eine Miniaturansicht bewegt (ohne zu klicken).
  - *Slider:* Das Modul zeigt einen kleinen Slider mit Navigationspfeilen an, mit denen Kunden durch die Bilder scrollen können. Dies impliziert oft ein „Beim Klick“-Verhalten für die Slider-Steuerelemente.
- **Empfohlener Wert:** `Beim Hover` für ein schnelles, interaktives Erlebnis. `Beim Klick`, wenn Sie eine explizite Benutzeraktion bevorzugen. `Slider`, wenn Sie viele Bilder haben und eine kompaktere Präsentation wünschen.
- **Händlerszenario / Beispiel:** Für ein Modegeschäft ermöglicht `Beim Hover` Kunden, schnell verschiedene Looks vorab anzusehen. Für ein Produkt mit vielen detaillierten Bildern kann `Slider` die Listenseite sauber halten und dennoch vollen Zugriff auf alle visuellen Elemente bieten.

#### **Bilder für Farbkombinationen (doppelte Einstellung, wahrscheinlich ein Fehler oder veraltet)**

- **Was diese Einstellung bewirkt:** Dies scheint eine Duplizierung der Einstellung „Anzeigemethode“ zu sein, die speziell mit der Anzeige von Bildern für Farbkombinationen zusammenhängt.
- **Auswirkung der Änderung dieser Einstellung:** Es ist am besten, sich für diese Funktionalität auf die Einstellung „Anzeigemethode“ zu verlassen. Wenn dies eine separate Steuerung ist, könnte sie die Einstellung „Anzeigemethode“ überschreiben oder mit ihr in Konflikt geraten.
- **Empfohlener Wert:** Stellen Sie die Konsistenz mit der Einstellung „Anzeigemethode“ sicher.
- **Händlerszenario / Beispiel:** Wenn „Anzeigemethode“ auf „Bilder für Farbkombinationen“ eingestellt ist, sollte diese Einstellung ebenfalls aktiviert oder konsistent sein.

#### **Bilder für jede Kombination (doppelte Einstellung, wahrscheinlich ein Fehler oder veraltet)**

- **Was diese Einstellung bewirkt:** Ähnlich wie oben scheint dies eine Duplizierung der Einstellung „Anzeigemethode“ zu sein, die speziell mit der Anzeige von Bildern für alle Kombinationen zusammenhängt.
- **Auswirkung der Änderung dieser Einstellung:** Am besten verlassen Sie sich auf die Einstellung „Anzeigemethode“.
- **Empfohlener Wert:** Stellen Sie die Konsistenz mit der Einstellung „Anzeigemethode“ sicher.
- **Händlerszenario / Beispiel:** Wenn „Anzeigemethode“ auf „Bilder für jede Kombination“ eingestellt ist, sollte diese Einstellung ebenfalls aktiviert oder konsistent sein.

#### **Alle Produktbilder (doppelte Einstellung, wahrscheinlich ein Fehler oder veraltet)**

- **Was diese Einstellung bewirkt:** Ähnlich wie oben scheint dies eine Duplizierung der Einstellung „Anzeigemethode“ zu sein, die speziell mit der Anzeige aller Produktbilder zusammenhängt.
- **Auswirkung der Änderung dieser Einstellung:** Am besten verlassen Sie sich auf die Einstellung „Anzeigemethode“.
- **Empfohlener Wert:** Stellen Sie die Konsistenz mit der Einstellung „Anzeigemethode“ sicher.
- **Händlerszenario / Beispiel:** Wenn „Anzeigemethode“ auf „Alle Produktbilder“ eingestellt ist, sollte diese Einstellung ebenfalls aktiviert oder konsistent sein.

#### **Konfigurations-Kurzübersichtstabelle**

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Position des Moduls | `displayProductAdditionalInfo` | Bestimmt, wo zusätzliche Bilder in Produktlisten erscheinen. |
| Modulkonfiguration | Design des Moduls | `Universal` | Legt den visuellen Stil für die Bildminiaturansichten fest (Klassisch vs. Modern). |
| Modulkonfiguration | Anzeigemethode | `Alle Produktbilder` | Steuert, welche Bilder angezeigt werden (Farbkombinationen, alle Kombinationen oder alle Produktbilder). |
| Modulkonfiguration | Nur auf Lager | `Aktiviert` | Filtert Bilder, um nur für vorrätige Produktkombinationen anzuzeigen. |
| Modulkonfiguration | Farbfelder anstelle von Bildern anzeigen | `Deaktiviert` | Ersetzt Bildminiaturansichten durch Farbfelder, wenn aktiviert. |
| Modulkonfiguration | Hauptproduktcontainer in der Produktliste | `.product-miniature` (oder themenspezifisch) | CSS-Selektor für den Hauptproduktblock auf Listenseiten. |
| Modulkonfiguration | CSS des Produkt-Titelbilds | `.product-thumbnail` (oder themenspezifisch) | CSS-Selektor für das Hauptproduktbildelement. |
| Modulkonfiguration | CSS des Ankers für das Produkt-Titelbild | `.product-thumbnail a` (oder themenspezifisch) | CSS-Selektor für den Link, der das Hauptproduktbild umschließt. |
| Modulkonfiguration | Anker des Produkttitels | `h3 a` (oder themenspezifisch) | CSS-Selektor für den Link, der den Produkttitel umschließt. |
| Modulkonfiguration | Zusätzliche Klasse für Miniatur-Anker | Leer lassen | Fügt den Miniaturbild-Links eine benutzerdefinierte CSS-Klasse für das Styling hinzu. |
| Modulkonfiguration | Bildwechselmethode | `Beim Hover` | Definiert, wie sich das Hauptbild ändert (Klick, Hover oder Slider). |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Die zusätzlichen Bilder werden in meinen Produktlisten nicht angezeigt.**

- **A:** Überprüfen Sie zunächst Ihre Modulkonfiguration:
  - Stellen Sie sicher, dass „Position des Moduls“ auf einen Hook eingestellt ist, den Ihr Theme tatsächlich rendert (z. B. `displayProductAdditionalInfo`). Wenn Ihr Theme stark angepasst ist, müssen Sie möglicherweise verschiedene Positionen ausprobieren oder einen Entwickler konsultieren.
  - Überprüfen Sie die Einstellungen „Hauptproduktcontainer in der Produktliste“, „CSS des Produkt-Titelbilds“, „CSS des Ankers für das Produkt-Titelbild“ und „Anker des Produkttitels“. Dies sind entscheidende CSS-Selektoren, die mit der HTML-Struktur Ihres Themes übereinstimmen müssen. Verwenden Sie die Entwicklertools Ihres Browsers (F12), um die Elemente auf Ihrer Kategorieseite zu überprüfen und die richtigen Klassen/IDs zu finden.
  - Stellen Sie sicher, dass die Produkte tatsächlich mehrere Bilder in ihren Produkteinstellungen im Back Office hochgeladen haben.
- **A:** Leeren Sie Ihren PrestaShop-Cache: Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie oben rechts auf „Cache leeren“. Leeren Sie auch den Cache Ihres Browsers.

**F2: Die Bilder erscheinen, aber sie wechseln nicht, wenn ich darüberfahre/klicke.**

- **A:** Dies deutet normalerweise auf ein Problem mit den CSS-Selektoren für das Hauptproduktbild oder dessen Container hin.
  - Überprüfen Sie „CSS des Produkt-Titelbilds“ und „CSS des Ankers für das Produkt-Titelbild“ noch einmal. Diese müssen das Hauptbild und seinen umschließenden Link genau ansprechen.
  - Stellen Sie sicher, dass auf Ihrer Seite keine JavaScript-Fehler auftreten, die die Ausführung des Modulskripts verhindern könnten. Überprüfen Sie die Entwicklerkonsole Ihres Browsers (F12 > Registerkarte „Konsole“).
  - Wenn Sie andere Module haben, die Produktlisten ändern, könnte es zu einem Konflikt kommen. Versuchen Sie, andere Front-Office-Module vorübergehend zu deaktivieren, um das Problem zu isolieren.

**F3: Die Bilder sehen verzerrt aus oder das Styling stimmt nicht.**

- **A:**
  - Versuchen Sie, die Einstellung „Design des Moduls“ zwischen `Klassisches Theme` und `Universal` zu wechseln, um zu sehen, ob eines besser zu Ihrem Theme passt.
  - Ihr Theme könnte widersprüchliche CSS-Regeln haben. Sie können die Einstellung „Zusätzliche Klasse für Miniatur-Anker“ verwenden, um eine benutzerdefinierte Klasse hinzuzufügen, und dann benutzerdefiniertes CSS in Ihrem Theme verwenden, um widersprüchliche Stile zu überschreiben.
  - Stellen Sie sicher, dass Ihre hochgeladenen Produktbilder von gleichbleibender Qualität und Seitenverhältnis sind.

**F4: Ich verwende ein benutzerdefiniertes Theme, und das Modul scheint überhaupt nicht zu funktionieren.**

- **A:** Benutzerdefinierte Themes verwenden oft andere HTML-Strukturen und CSS-Klassen als Standard-PrestaShop-Themes.
  - Sie müssen fast sicher die CSS-Selektoren für „Hauptproduktcontainer in der Produktliste“, „CSS des Produkt-Titelbilds“, „CSS des Ankers für das Produkt-Titelbild“ und „Anker des Produkttitels“ an das spezifische Markup Ihres Themes anpassen. Dies erfordert in der Regel grundlegende Kenntnisse der HTML-/CSS-Inspektion mit Browser-Entwicklertools.
  - Ihr benutzerdefiniertes Theme ruft möglicherweise nicht die Standard-PrestaShop-Hooks auf, die das Modul verwendet. Möglicherweise müssen Sie die Hook-Aufrufe des Moduls manuell zu den `.tpl`-Dateien Ihres Themes hinzufügen (konsultieren Sie hierfür Ihren Theme-Entwickler oder einen PrestaShop-Entwickler).

**F5: Das Modul verlangsamt meine Seitenladezeit.**

- **A:** Obwohl das Modul optimiert ist, kann die Anzeige vieler zusätzlicher Bilder die Seitenladezeit natürlich erhöhen.
  - Stellen Sie sicher, dass Ihre Produktbilder für das Web optimiert sind (komprimiert, entsprechende Abmessungen).
  - Erwägen Sie die Verwendung der Option „Nur auf Lager“, um die Anzahl der geladenen Bilder für nicht vorrätige Artikel zu reduzieren.
  - Wenn Sie viele Bilder pro Produkt haben, sollten Sie die `Slider`-Methode verwenden, die Bilder oft effizienter oder verzögert lädt.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten Einblick in die technische Struktur des Moduls „Produktbilder in Produktlisten“, der für Entwickler, Webmaster und technische Agenturen bestimmt ist.

### 4.1 Architekturübersicht

Das Modul `productlistpics` ist primär ein Front-Office-Funktionsmodul, das entwickelt wurde, um zusätzliche Produktbildfunktionen in bestehende Produktlistenvorlagen zu integrieren. Es nutzt das Hook-System von PrestaShop, um seinen Inhalt zu rendern, und verwendet JavaScript, um dynamische Bildwechsel (Hover/Klick) oder Slider-Funktionen zu handhaben. Die Konfiguration wird über die Standardmethode `getContent()` in der Hauptmodulklasse verwaltet, wobei die Einstellungen in `ps_configuration` gespeichert werden. Das Modul führt keine benutzerdefinierten Datenbanktabellen oder komplexen `ObjectModel`-Entitäten ein.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält **keine** benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Logik ist in der Hauptmodulklasse und den zugehörigen Vorlagen und Assets gekapselt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul enthält **keine** benutzerdefinierten Klassen oder `ObjectModel`-Entitäten im Verzeichnis `classes/`. Die gesamte Kernlogik befindet sich in `productlistpics.php`.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul enthält mehrere JavaScript-Dateien, hauptsächlich zur Handhabung von Bildwechseln und Slider-Funktionen.

- `productlistpics/js/owl-carousel/owl.carousel.js`:
  - **Umfang:** Front-Office.
  - **Beschreibung:** Dies ist die Kernbibliothek von Owl Carousel, einem beliebten Touch-fähigen jQuery-Plugin für responsive Karussells. Es bietet die grundlegende Funktionalität zum Erstellen von Bild-Slidern.
- `productlistpics/js/owl-carousel/owl.run.js`:
  - **Umfang:** Front-Office.
  - **Beschreibung:** Dieses Skript enthält wahrscheinlich den Initialisierungs- und Konfigurationscode für Owl Carousel-Instanzen, die vom Modul verwendet werden. Es richtet das Slider-Verhalten, die Responsivität und die Navigationsoptionen basierend auf den Moduleinstellungen ein.
- `productlistpics/js/plp-replacement.js`:
  - **Umfang:** Front-Office.
  - **Beschreibung:** Dieses Skript ist wahrscheinlich für die Kernlogik des Ersetzens des Hauptproduktbilds verantwortlich, wenn eine Miniaturansicht interagiert wird. Es lauscht auf Ereignisse (Klick/Hover) auf den generierten Miniaturansichten und aktualisiert die `src`- und `srcset`-Attribute des Hauptproduktbilds, möglicherweise auch das `href` des Anker-Tags des Hauptbilds.
- `productlistpics/js/productlistpics-mouseover.js`:
  - **Umfang:** Front-Office.
  - **Beschreibung:** Dieses Skript implementiert speziell die Bildwechselmethode „Beim Hover“. Es fügt `mouseover`- und `mouseout`-Ereignis-Listener an die Miniaturbild-Anker an, um den Hauptbildersatz auszulösen.
- `productlistpics/js/productlistpics.js`:
  - **Umfang:** Front-Office.
  - **Beschreibung:** Dies ist wahrscheinlich der Haupt-JavaScript-Einstiegspunkt des Moduls für das Front-Office. Es könnte die Bildwechselmethode „Beim Klick“, allgemeine DOM-Manipulationen im Zusammenhang mit dem Einfügen der Miniaturansichten und möglicherweise die Orchestrierung des Ladens anderer Skripte basierend auf der Konfiguration handhaben.
- `productlistpics/js/slider-productlistpics-mouseover.js`:
  - **Umfang:** Front-Office.
  - **Beschreibung:** Dieses Skript kombiniert Slider-Funktionalität mit Hover-basiertem Bildwechsel. Es würde wahrscheinlich den Owl Carousel initialisieren und dann Hover-Listener zu den Slider-Elementen hinzufügen, um das Hauptproduktbild zu aktualisieren.
- `productlistpics/js/slider-productlistpics.js`:
  - **Umfang:** Front-Office.
  - **Beschreibung:** Dieses Skript integriert den Owl Carousel-Slider mit Klick-basiertem Bildwechsel. Es initialisiert den Slider und verarbeitet Klicks auf Slider-Elemente, um das Hauptproduktbild zu aktualisieren.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul enthält mehrere CSS-Dateien zum Stylen der eingefügten Elemente und des Owl Carousels.

- `productlistpics/css.css`:
  - **Umfang:** Front-Office.
  - **Beschreibung:** Allgemeines Styling für die Elemente des Moduls, wie den Container für zusätzliche Bilder, die Größe der Miniaturansichten und das grundlegende Layout.
- `productlistpics/js/owl-carousel/owl.carousel.css`:
  - **Umfang:** Front-Office.
  - **Beschreibung:** Basisstile für das Owl Carousel-Plugin, die die Struktur und das Standardaussehen des Sliders definieren.
- `productlistpics/js/owl-carousel/owl.theme.css`:
  - **Umfang:** Front-Office.
  - **Beschreibung:** Standard-Theme für Owl Carousel, das visuelles Styling für Navigationsschaltflächen, Punkte und die allgemeine Slider-Ästhetik bietet.
- `productlistpics/js/owl-carousel/owl.transitions.css`:
  - **Umfang:** Front-Office.
  - **Beschreibung:** CSS für verschiedene Übergangseffekte, die von Owl Carousel verwendet werden (z. B. Fade, Slide).
- `productlistpics/productlistpics-classic.css`:
  - **Umfang:** Front-Office.
  - **Beschreibung:** Spezifische Styling-Regeln, die angewendet werden, wenn die Designoption „Klassisches Theme“ in der Modulkonfiguration ausgewählt ist. Dies zielt auf ältere PrestaShop-Themes oder Themes ab, die den klassischen Look nachahmen.
- `productlistpics/productlistpics.css`:
  - **Umfang:** Front-Office.
  - **Beschreibung:** Hauptstyling für das Modul, das wahrscheinlich Regeln für die Designoption „Universal“ und allgemeine Überschreibungen oder Verbesserungen enthält.

**Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:**

- `.productlistpics-container`: Der Haupt-Wrapper für die zusätzlichen Bilder.
- `.productlistpics-thumb`: Einzelne Miniaturansichts-Container.
- `.productlistpics-thumb img`: Das eigentliche Bild innerhalb der Miniaturansicht.
- `.owl-carousel`, `.owl-item`, `.owl-nav`, `.owl-dots`: Standard-Owl Carousel-Selektoren für die Slider-Anpassung.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

Das Modul verwendet Smarty-Vorlagen, um seinen Inhalt innerhalb verschiedener PrestaShop-Hooks zu rendern.

- **Hook-Vorlagen (`views/templates/hook/`)**:
  - `productlistpics/header.tpl`:
    - **Hook:** `displayHeader` (oder ähnlich, typischerweise in `install()` registriert).
    - **Ausgabe:** Diese Vorlage ist dafür verantwortlich, die notwendigen CSS- und JavaScript-Assets für die Funktion des Moduls im Front-Office einzubinden. Sie lädt Skripte bedingt basierend auf der gewählten „Bildwechselmethode“ (z. B. `owl.carousel.js`, `productlistpics-mouseover.js`, `slider-productlistpics.js`).
  - `productlistpics/html.tpl`:
    - **Hook:** Dies ist eine generische Vorlage, die von anderen Vorlagen eingebunden oder für bestimmte Inhaltsblöcke verwendet werden könnte. Ihre genaue Verwendung hängt davon ab, wie die Haupt-PHP-Datei des Moduls Inhalte rendert.
    - **Ausgabe:** Enthält die HTML-Struktur zum Anzeigen der zusätzlichen Produktbilder, einschließlich Schleifen zum Iterieren durch Bilder und bedingter Logik zum Anzeigen von Farbfeldern oder Bildminiaturansichten.
  - `productlistpics/productFooter.tpl`:
    - **Hook:** `displayFooterProduct` (wie in „Position des Moduls“ konfiguriert).
    - **Ausgabe:** Rendert die zusätzlichen Produktbilder im Fußbereich eines Produktblocks auf Listenseiten. Es enthält wahrscheinlich `html.tpl` oder ähnliche Logik.
  - `productlistpics/productPage.tpl`:
    - **Hook:** Diese Vorlage wird wahrscheinlich für Hooks wie `displayProductAdditionalInfo`, `displayAfterProductThumbs`, `displayProductDeliveryTime`, `displayProductListReviews` verwendet (wie in „Position des Moduls“ konfiguriert).
    - **Ausgabe:** Rendert die zusätzlichen Produktbilder innerhalb des angegebenen Produktlisten-Hooks. Es enthält die Kernlogik zum Generieren der Bildminiaturansichten oder Farbfelder und zum Einrichten der notwendigen Datenattribute für die JavaScript-Interaktion.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Das Modul erstellt **keine** benutzerdefinierten Datenbanktabellen. Alle seine Konfigurationseinstellungen werden in der Tabelle `ps_configuration` unter Verwendung von Schlüsseln wie `PLP_TYPE`, `PLP_INSTOCK`, `PLP_METHOD`, `PLP_SWITCH`, `PLP_DESIGN`, `PLP_POSITION` und verschiedenen CSS-Selektor-Schlüsseln (`pls_product_miniature`, `pls_product_miniature_img` usw.) gespeichert.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Fügt CSS- und JavaScript-Assets ein, die vom Modul benötigt werden. |
| `displayProductAdditionalInfo` | Innerhalb des Produktminiaturblocks, oft unter dem Hauptbild oder Titel. | Rendert die zusätzlichen Produktbild-Miniaturansichten/Slider. |
| `displayAfterProductThumbs` | Nach den Hauptproduktbild-Miniaturansichten (falls vorhanden). | Rendert die zusätzlichen Produktbild-Miniaturansichten/Slider. |
| `displayFooterProduct` | Im Fußbereich jedes Produktminiaturblocks. | Rendert die zusätzlichen Produktbild-Miniaturansichten/Slider. |
| `displayProductDeliveryTime` | In der Nähe der Produktlieferzeitinformationen in der Produktminiatur. | Rendert die zusätzlichen Produktbild-Miniaturansichten/Slider. |
| `displayProductListReviews` | In der Nähe der Produktbewertungssterne/-anzahl in der Produktminiatur. | Rendert die zusätzlichen Produktbild-Miniaturansichten/Slider. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Produktbilder in Produktlisten“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.
